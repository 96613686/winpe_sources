# __imp_load_SamIUpdateLogonStatistics

- ea: `0x180013947`
- end: `0x180013953`
- name: `__imp_load_SamIUpdateLogonStatistics`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180013892`

## import_xrefs

- `SAMSRV!SamIUpdateLogonStatistics` at `0x180013947`

## pseudocode

```c
__int64 load_SamIUpdateLogonStatistics()
{
  return _tailMerge_samsrv_dll();
}

```

## disassembly

```asm
0x180013947  lea     rax, __imp_SamIUpdateLogonStatistics
0x18001394e  jmp     __tailMerge_samsrv_dll
```
