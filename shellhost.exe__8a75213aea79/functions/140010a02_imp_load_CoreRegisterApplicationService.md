# __imp_load_CoreRegisterApplicationService

- ea: `0x140010a02`
- end: `0x140010a0e`
- name: `__imp_load_CoreRegisterApplicationService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x140010983`

## import_xrefs

- `twinapi.appcore!__imp_CoreRegisterApplicationService` at `0x140010a02`

## pseudocode

```c
__int64 load_CoreRegisterApplicationService()
{
  return _tailMerge_twinapi_appcore_dll();
}

```

## disassembly

```asm
0x140010a02  lea     rax, __imp_CoreRegisterApplicationService
0x140010a09  jmp     __tailMerge_twinapi_appcore_dll
```
