# COMMON_TowerConstruct(char *,char *,char *,ushort *,ulong *,uchar * *)

- ea: `0x180005710`
- end: `0x180005740`
- name: `?COMMON_TowerConstruct@@YAJPEAD00PEAGPEAKPEAPEAE@Z`
- size: `48`
- prototype: `__int64 __fastcall(char *, char *, char *, unsigned __int16 *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall COMMON_TowerConstruct(
        char *a1,
        char *a2,
        char *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  return (*((__int64 (__fastcall **)(char *, char *, char *, unsigned __int16 *, unsigned int *, unsigned __int8 **))pRuntimeImportTable
          + 80))(
           a1,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180005710  sub     rsp, 48h
0x180005714  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000571b  mov     r10, [rsp+48h+arg_28]
0x180005720  mov     [rsp+48h+var_20], r10
0x180005725  mov     r10, [rsp+48h+arg_20]
0x18000572a  mov     rax, [rax+280h]
0x180005731  mov     [rsp+48h+var_28], r10
0x180005736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000573b  add     rsp, 48h
0x18000573f  retn
```
