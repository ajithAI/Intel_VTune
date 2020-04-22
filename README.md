# Intel_VTune
Useful commands for VTune
I ) Hotspots :

### I) System wide :

amplxe-cl -collect hotspots -knob sampling-mode=hw -knob enable-stack-collection=true --duration unlimited <br>
 
amplxe-cl -collect hotspots -knob enable-stack-collection=true -analyze-system -finalization-mode=full --duration unlimited
 
#### To RUN VTune Benchmarking for 100sec SystemWide :

amplxe-cl -collect hotspots -knob enable-stack-collection=true -analyze-system -finalization-mode=full --duration 100 
 
 ### II) Application wide : 

amplxe-cl -collect hotspots -knob sampling-mode=hw -knob enable-stack-collection=true -analyze-system -finalization-mode=full -app-working-dir C:\Users\asirra\AppData\Local\Programs\Python\Python35 -- C:\Users\asirra\AppData\Local\Programs\Python\Python35\python.exe C:\Users\asirra\Desktop\MayBeImp\resnet_inference.py

amplxe-cl -collect hotspots -knob sampling-mode=hw -knob enable-stack-collection=true -analyze-system -finalization-mode=full ./RUN_Application.sh

This RUN_Applications can contain such line -> "python3 resnet_inference.py"

### III ) General Exploration : 
 
amplxe-cl -collect uarch-exploration  -knob collect-memory-bandwidth=true -knob enable-stack-collection=true -knob sampling-interval=1 -analyze-system -finalization-mode=full --duration 100 -result-dir /opt/ajith/20190604_043733/h264_enc_rate_1_sess_20

If you want to skip descriptions of detected performance issues in the report,
enter: amplxe-cl -report summary -report-knob show-issues=false -r
<my_result_dir>. Alternatively, you may view the report in the csv format:
amplxe-cl -report <report_name> -format=csv.
amplxe: Executing actions 100 % done
