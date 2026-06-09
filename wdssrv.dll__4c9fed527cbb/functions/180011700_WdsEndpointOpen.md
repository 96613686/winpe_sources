# WdsEndpointOpen

- ea: `0x180011700`
- end: `0x18001174e`
- name: `WdsEndpointOpen`
- size: `78`
- prototype: `unsigned int __fastcall(struct CWdsProvider *, struct tagWDS_ENDPOINT *, unsigned int, struct tagWDS_PROPERTY *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180011700`
- `0x18001385c`

## pseudocode

```c
unsigned int __fastcall WdsEndpointOpen(
        struct CWdsProvider *a1,
        struct tagWDS_ENDPOINT *a2,
        unsigned int a3,
        struct tagWDS_PROPERTY *a4,
        void **a5)
{
  if ( a1 && a2 && a5 && (!a3 || a4) )
    return CInterfaceHandler::OpenEndpoint((CInterfaceHandler *)&qword_180028C00, a1, a2, a3, a4, a5);
  else
    return 87;
}

```

## disassembly

```asm
0x180011700  sub     rsp, 38h
0x180011704  test    rcx, rcx
0x180011707  jz      short loc_180011743
0x180011709  test    rdx, rdx
0x18001170c  jz      short loc_180011743
0x18001170e  mov     rax, [rsp+38h+arg_20]
0x180011713  test    rax, rax
0x180011716  jz      short loc_180011743
0x180011718  test    r8d, r8d
0x18001171b  jz      short loc_180011722
0x18001171d  test    r9, r9
0x180011720  jz      short loc_180011743
0x180011722  mov     [rsp+38h+var_10], rax; void **
0x180011727  mov     [rsp+38h+var_18], r9; struct tagWDS_PROPERTY *
0x18001172c  mov     r9d, r8d; unsigned int
0x18001172f  mov     r8, rdx; struct tagWDS_ENDPOINT *
0x180011732  mov     rdx, rcx; struct CWdsProvider *
0x180011735  lea     rcx, qword_180028C00; this
0x18001173c  call    ?OpenEndpoint@CInterfaceHandler@@QEAAKPEAVCWdsProvider@@PEAUtagWDS_ENDPOINT@@KPEAUtagWDS_PROPERTY@@PEAPEAX@Z; CInterfaceHandler::OpenEndpoint(CWdsProvider *,tagWDS_ENDPOINT *,ulong,tagWDS_PROPERTY *,void * *)
0x180011741  jmp     short loc_180011748
0x180011743  mov     eax, 57h ; 'W'
0x180011748  add     rsp, 38h
0x18001174c  retn
```
