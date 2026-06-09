# DispatchIOHelper(LOADABLE_TRANSPORT *,uint,long,void *,uint,uchar *,void *)

- ea: `0x1800099ec`
- end: `0x180009a2e`
- name: `?DispatchIOHelper@@YAXPEAVLOADABLE_TRANSPORT@@IJPEAXIPEAE1@Z`
- size: `66`
- prototype: `void __fastcall(struct LOADABLE_TRANSPORT *, unsigned int, int, void *, unsigned int, unsigned __int8 *, void *)`
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000aee0`
- `0x18000afe0`
- `0x18000b100`
- `0x18000b1d0`
- `0x18000b400`
- `0x18000baa0`
- `0x18000bb50`
- `0x18000bc50`

## callees

- `0x180025010`

## pseudocode

```c
void __fastcall DispatchIOHelper(
        struct LOADABLE_TRANSPORT *a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        void *a7)
{
  (*((void (__fastcall **)(struct LOADABLE_TRANSPORT *, __int64, __int64, void *, unsigned int, unsigned __int8 *, void *))pRuntimeImportTable
   + 93))(
    gLoadableTransport,
    a2,
    a3,
    a4,
    a5,
    a6,
    a7);
}

```

## disassembly

```asm
0x1800099ec  sub     rsp, 48h
0x1800099f0  mov     rcx, [rsp+48h+arg_30]
0x1800099f8  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800099ff  mov     [rsp+48h+var_18], rcx
0x180009a04  mov     rcx, [rsp+48h+arg_28]
0x180009a09  mov     [rsp+48h+var_20], rcx
0x180009a0e  mov     ecx, [rsp+48h+arg_20]
0x180009a12  mov     rax, [rax+2E8h]
0x180009a19  mov     [rsp+48h+var_28], ecx
0x180009a1d  mov     rcx, cs:?gLoadableTransport@@3PEAVLOADABLE_TRANSPORT@@EA; LOADABLE_TRANSPORT * gLoadableTransport
0x180009a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a29  add     rsp, 48h
0x180009a2d  retn
```
