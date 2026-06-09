# __imp_load_SwDeviceCreate

- ea: `0x180001b74`
- end: `0x180001b80`
- name: `__imp_load_SwDeviceCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001af5`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180001b74`

## pseudocode

```c
__int64 load_SwDeviceCreate()
{
  return _tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001b74  lea     rax, __imp_SwDeviceCreate
0x180001b7b  jmp     __tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll
```
