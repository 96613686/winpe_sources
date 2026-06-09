# ComputeService::VmCommonHelpers::VirtualGpu::SetupGpus(ushort const *,ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment &)

- ea: `0x140048514`
- end: `0x14004896c`
- name: `?SetupGpus@VirtualGpu@VmCommonHelpers@ComputeService@@YAXPEBGAEAUGpuEnvironment@123@@Z`
- size: `1112`
- prototype: `void __fastcall(ComputeService::VmCommonHelpers::VirtualGpu *__hidden this, const unsigned __int16 *, struct ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140098ed0`
- `0x140287a94`

## callees

- `0x140017040`
- `0x140017840`
- `0x14001bce0`
- `0x14001d4d0`
- `0x140022e84`
- `0x140033a7c`
- `0x140048514`
- `0x140048974`
- `0x140048f3c`
- `0x1400942e0`
- `0x1400c40e0`
- `0x1400c4154`
- `0x1400e8154`
- `0x1400e821c`
- `0x1400e832c`
- `0x1400e9584`
- `0x1400e9660`
- `0x1400e96b8`
- `0x140106b48`
- `0x1401332f0`
- `0x140134048`
- `0x1401eeaf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140048794`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140048794`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400488d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400488d3`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x140048688`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x140048688`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14004862e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400486a3`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140048755`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14004862e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400486a3`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140048755`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x140048740`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x140048740`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x140048617`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x140048617`

## string_xrefs

- `0x1400487d1`: `ComputeSystem_ConfigureGpu`
- `0x1400485af`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`
- `0x140048648`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`
- `0x1400486bd`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`
- `0x14004876f`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`
- `0x140048566`: `ComputeSystem_EnumerateGpu`

## pseudocode

```c

```
