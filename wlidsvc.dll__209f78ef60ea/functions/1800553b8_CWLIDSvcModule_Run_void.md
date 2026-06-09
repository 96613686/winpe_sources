# CWLIDSvcModule::Run(void)

- ea: `0x1800553b8`
- end: `0x180055762`
- name: `?Run@CWLIDSvcModule@@AEAAXXZ`
- size: `938`
- prototype: `void __fastcall(CWLIDSvcModule *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f318`

## callees

- `0x18000141c`
- `0x180019690`
- `0x18003e600`
- `0x18004e484`
- `0x18004f058`
- `0x180050b10`
- `0x18005538c`
- `0x1800553b8`
- `0x1800a3b60`
- `0x1800bcff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005552f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005552f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180055721`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180055721`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800553e4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800553e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055521`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055521`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005549e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800554b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800555e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800555f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005549e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800554b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800555e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800555f1`

## string_xrefs

- `0x18005542f`: `onecoreuap\ds\ext\live\identity\ntservice\svc\wlidsvc.cpp`
- `0x18005546c`: `onecoreuap\ds\ext\live\identity\ntservice\svc\wlidsvc.cpp`
- `0x180055504`: `onecoreuap\ds\ext\live\identity\ntservice\svc\wlidsvc.cpp`
- `0x18005556e`: `onecoreuap\ds\ext\live\identity\ntservice\svc\wlidsvc.cpp`
- `0x18005563b`: `onecoreuap\ds\ext\live\identity\ntservice\svc\wlidsvc.cpp`
- `0x1800554f7`: `Time elapsed to start the service: %I64u.%I64u sec.`
- `0x180055561`: `Service initialization failed with: hr=0x%x`
- `0x18005562e`: `Time elapsed to stop the service: %I64u.%I64u sec.`

## pseudocode

```c

```
