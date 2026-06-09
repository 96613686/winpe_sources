# __imp_load_I_ScSetServiceBitsW

- ea: `0x18001ff57`
- end: `0x18001ff63`
- name: `__imp_load_I_ScSetServiceBitsW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001fed8`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18001ff57`

## pseudocode

```c
__int64 load_I_ScSetServiceBitsW()
{
  return _tailMerge_api_ms_win_service_private_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001ff57  lea     rax, __imp_I_ScSetServiceBitsW
0x18001ff5e  jmp     __tailMerge_api_ms_win_service_private_l1_1_0_dll
```
