# ComputeService::ContainerDevice::GetPortNameFromDeviceID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400a930c`
- end: `0x1400a9491`
- name: `?GetPortNameFromDeviceID@ContainerDevice@ComputeService@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z`
- size: `389`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400d6abc`

## callees

- `0x14002fa20`
- `0x1400a930c`
- `0x1400a94dc`
- `0x1400a97c8`
- `0x1400e4f40`
- `0x1400f4da8`
- `0x1401332f0`
- `0x140211694`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a942b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a942b`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1400a935e`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1400a935e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400a9375`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400a9375`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1400a93bf`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1400a93bf`

## pseudocode

```c

```
