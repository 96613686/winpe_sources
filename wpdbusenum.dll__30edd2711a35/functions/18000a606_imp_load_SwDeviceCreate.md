# __imp_load_SwDeviceCreate

- ea: `0x18000a606`
- end: `0x18000a612`
- name: `__imp_load_SwDeviceCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a587`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000a606`

## pseudocode

```c
__int64 load_SwDeviceCreate()
{
  return _tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a606  lea     rax, __imp_SwDeviceCreate
0x18000a60d  jmp     __tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll
```
