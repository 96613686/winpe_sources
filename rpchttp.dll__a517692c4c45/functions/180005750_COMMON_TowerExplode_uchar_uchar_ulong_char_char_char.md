# COMMON_TowerExplode(uchar *,uchar *,ulong,char * *,char * *,char * *)

- ea: `0x180005750`
- end: `0x180005780`
- name: `?COMMON_TowerExplode@@YAJPEAE0KPEAPEAD11@Z`
- size: `48`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned int, char **, char **, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall COMMON_TowerExplode(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        __int64 a3,
        char **a4,
        char **a5,
        char **a6)
{
  return (*((__int64 (__fastcall **)(unsigned __int8 *, unsigned __int8 *, __int64, char **, char **, char **))pRuntimeImportTable
          + 81))(
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
0x180005750  sub     rsp, 48h
0x180005754  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000575b  mov     r10, [rsp+48h+arg_28]
0x180005760  mov     [rsp+48h+var_20], r10
0x180005765  mov     r10, [rsp+48h+arg_20]
0x18000576a  mov     rax, [rax+288h]
0x180005771  mov     [rsp+48h+var_28], r10
0x180005776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000577b  add     rsp, 48h
0x18000577f  retn
```
