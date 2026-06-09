# ComputeService::ContainerDevice::GetPortNameFromDeviceID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400db850`
- end: `0x1400dba28`
- name: `?GetPortNameFromDeviceID@ContainerDevice@ComputeService@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z`
- size: `472`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400c9964`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x140006098`
- `0x1400068e0`
- `0x14001bfa4`
- `0x1400db850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400db8f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400db8f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400db8e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400db8e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400db8eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400db9fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400db8eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400db9fc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400db9a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400db9a6`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1400db919`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1400db919`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1400db8a5`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1400db8a5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400db8b6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400db8b6`

## pseudocode

```c

```
