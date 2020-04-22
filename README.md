# Intel_VTune
Useful commands for VTune
I ) Hotspots :

### I) System wide :

#### HotStop Analysis

amplxe-cl -collect hotspots -knob sampling-mode=hw -knob enable-stack-collection=true --duration unlimited \
-result-dir < path-to-result-dir <br>
 
amplxe-cl -collect hotspots -knob enable-stack-collection=true -analyze-system -finalization-mode=full --duration unlimited \
-result-dir path-to-result-dir
 
#### To RUN VTune Benchmarking for 100sec SystemWide :

amplxe-cl -collect hotspots -knob enable-stack-collection=true -analyze-system -finalization-mode=full --duration 100 \
-result-dir path-to-result-dir
 
 #### General Exploration : 
 
amplxe-cl -collect uarch-exploration  -knob collect-memory-bandwidth=true -knob \
enable-stack-collection=true -knob sampling-interval=1 -analyze-system -finalization-mode=full --duration 100 \
-result-dir path-to-result-dir

 ### II) Application wide : 
 
 #### Windows 

amplxe-cl -collect hotspots -knob sampling-mode=hw -knob enable-stack-collection=true -analyze-system -finalization-mode=full -app-working-dir C:\Users\asirra\AppData\Local\Programs\Python\Python35 -- C:\Users\asirra\AppData\Local\Programs\Python\Python35\python.exe C:\Users\asirra\Desktop\MayBeImp\resnet_inference.py

#### Linux 

amplxe-cl -collect hotspots -knob sampling-mode=hw -knob enable-stack-collection=true -analyze-system -finalization-mode=full ./RUN_Application.sh

This RUN_Applications can contain such line -> "python3 resnet_inference.py"

If you want to skip descriptions of detected performance issues in the report,
enter: amplxe-cl -report summary -report-knob show-issues=false -r
<my_result_dir>. Alternatively, you may view the report in the csv format:
amplxe-cl -report <report_name> -format=csv.
amplxe: Executing actions 100 % done
