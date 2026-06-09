# __imp_load_StartServiceA

- ea: `0x18001f4c8`
- end: `0x18001f4d4`
- name: `__imp_load_StartServiceA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001ec1c`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x18001f4c8`

## pseudocode

```c
__int64 load_StartServiceA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001f4c8  lea     rax, __imp_StartServiceA
0x18001f4cf  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
