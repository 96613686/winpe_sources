# __imp_load_CoreUnregisterApplicationService

- ea: `0x140010a14`
- end: `0x140010a20`
- name: `__imp_load_CoreUnregisterApplicationService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x140010983`

## import_xrefs

- `twinapi.appcore!__imp_CoreUnregisterApplicationService` at `0x140010a14`

## pseudocode

```c
__int64 load_CoreUnregisterApplicationService()
{
  return _tailMerge_twinapi_appcore_dll();
}

```

## disassembly

```asm
0x140010a14  lea     rax, __imp_CoreUnregisterApplicationService
0x140010a1b  jmp     __tailMerge_twinapi_appcore_dll
```
