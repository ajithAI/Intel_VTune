# Intel_VTune
Useful commands for VTune
I ) Hotspots :

System wide : 

amplxe-cl -collect hotspots -knob sampling-mode=hw -knob enable-stack-collection=true --duration unlimited <br>
 
amplxe-cl -collect hotspots -knob enable-stack-collection=true -analyze-system -finalization-mode=full --duration unlimited
 
 Application wide : 

amplxe-cl -collect hotspots -knob sampling-mode=hw -knob enable-stack-collection=true -analyze-system -finalization-mode=full -app-working-dir C:\Users\asirra\AppData\Local\Programs\Python\Python35 -- C:\Users\asirra\AppData\Local\Programs\Python\Python35\python.exe C:\Users\asirra\Desktop\MayBeImp\resnet_inference.py



II ) General Exploration : 
 
amplxe-cl -collect uarch-exploration  -knob collect-memory-bandwidth=true -knob enable-stack-collection=true -knob sampling-interval=1 -analyze-system -finalization-mode=full --duration 100 -result-dir /opt/ajith/20190604_043733/h264_enc_rate_1_sess_20
