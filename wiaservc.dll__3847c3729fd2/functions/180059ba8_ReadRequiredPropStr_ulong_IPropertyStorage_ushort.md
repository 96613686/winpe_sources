# ReadRequiredPropStr(ulong,IPropertyStorage *,ushort * *)

- ea: `0x180059ba8`
- end: `0x180059d2d`
- name: `?ReadRequiredPropStr@@YAJKPEAUIPropertyStorage@@PEAPEAG@Z`
- size: `389`
- prototype: `__int64 __fastcall(unsigned int, struct IPropertyStorage *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180070270`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x180059ba8`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180059c3c`
- `OLEAUT32!__imp_SysAllocString` at `0x180059c3c`
- `ole32!PropVariantClear` at `0x180059c92`
- `ole32!PropVariantClear` at `0x180059c92`

## string_xrefs

- `0x180059cd1`: `ReadMultiple of propid: %d, failed`
- `0x180059cf3`: `ReadMultiple of propid: %d, failed`
- `0x180059bcc`: `ReadRequiredPropStr`
- `0x180059ca1`: `ReadMultiple failed to read required property, propid: %d`
- `0x180059cc8`: `ReadMultiple failed to read required property, propid: %d`
- `0x180059bbd`: `::ReadRequiredPropStr`

## pseudocode

```c
__int64 __fastcall ReadRequiredPropStr(unsigned int a1, struct IPropertyStorage *a2, unsigned __int16 **a3)
{
  struct tagWiaTraceData_Type *v6; // rax
  char *v7; // rdx
  unsigned int v8; // r8d
  struct IPropertyStorageVtbl *lpVtbl; // rax
  unsigned int v10; // eax
  unsigned int v11; // edi
  const OLECHAR *v12; // rcx
  unsigned __int16 *v13; // rax
  char *v14; // rbx
  void *v15; // rdx
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  char *v24; // rbx
  void *v25; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-C8h]
  _DWORD v28[4]; // [rsp+30h] [rbp-B8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-98h]
  _BYTE v31[136]; // [rsp+60h] [rbp-88h] BYREF

  v6 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::ReadRequiredPropStr");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v31, v7, v8, "ReadRequiredPropStr", lpMem, v6);
  v28[3] = 0;
  v30 = 0;
  *a3 = 0;
  v28[2] = a1;
  lpVtbl = a2->lpVtbl;
  *(_OWORD *)pvar = 0;
  v28[0] = 1;
  v10 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, _DWORD *, PROPVARIANT *))lpVtbl->ReadMultiple)(
          a2,
          1,
          v28,
          pvar);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 == 1 )
    {
      v11 = -2147024809;
      v19 = (char *)WiaTrace_TraceLog("ReadMultiple failed to read required property, propid: %d");
      WriteDbgTraceErrorWI("ReadRequiredPropStr", v19);
      WiaTrcLib::Free((WiaTrcLib *)v19, v20);
      v21 = (void **)WiaTrace_Trace("ReadMultiple failed to read required property, propid: %d", a1);
    }
    else
    {
      v24 = (char *)WiaTrace_TraceLog("ReadMultiple of propid: %d, failed");
      WriteDbgTraceErrorWI("ReadRequiredPropStr", v24);
      WiaTrcLib::Free((WiaTrcLib *)v24, v25);
      v21 = (void **)WiaTrace_Trace("ReadMultiple of propid: %d, failed", a1);
    }
    WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"ReadRequiredPropStr", 1, v21);
  }
  else
  {
    v12 = (const OLECHAR *)pvar[1];
    if ( !pvar[1] )
      v12 = &Class;
    v13 = SysAllocString(v12);
    *a3 = v13;
    if ( !v13 )
    {
      v14 = (char *)WiaTrace_TraceLog("SysAllocString failed");
      WriteDbgTraceErrorWI("ReadRequiredPropStr", v14);
      WiaTrcLib::Free((WiaTrcLib *)v14, v15);
      v16 = (void **)WiaTrace_Trace("SysAllocString failed");
      WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"ReadRequiredPropStr", 1, v16);
      v11 = -2147024882;
    }
    PropVariantClear(pvar);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v31);
  return v11;
}

```

## disassembly

```asm
0x180059ba8  push    rbx
0x180059baa  push    rbp
0x180059bab  push    rsi
0x180059bac  push    rdi
0x180059bad  push    r14
0x180059baf  push    r15
0x180059bb1  sub     rsp, 0B8h
0x180059bb8  mov     esi, ecx
0x180059bba  mov     r14, r8
0x180059bbd  lea     rcx, aReadrequiredpr_1; "::ReadRequiredPropStr"
0x180059bc4  mov     rbx, rdx
0x180059bc7  call    WiaTrace_Trace
0x180059bcc  lea     rbp, aReadrequiredpr; "ReadRequiredPropStr"
0x180059bd3  mov     [rsp+0E8h+var_C0], rax; struct tagWiaTraceData_Type *
0x180059bd8  mov     r9, rbp; char *
0x180059bdb  lea     rcx, [rsp+0E8h+var_88]; this
0x180059be0  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180059be5  xor     eax, eax
0x180059be7  lea     r9, [rsp+0E8h+pvar]
0x180059bec  mov     [rsp+0E8h+var_B0], rax
0x180059bf1  lea     r8, [rsp+0E8h+var_B8]
0x180059bf6  mov     [rsp+0E8h+var_98], rax
0x180059bfb  xorps   xmm0, xmm0
0x180059bfe  mov     [r14], rax
0x180059c01  mov     rcx, rbx
0x180059c04  lea     r15d, [rax+1]
0x180059c08  mov     dword ptr [rsp+0E8h+var_B0], esi
0x180059c0c  mov     rax, [rbx]
0x180059c0f  mov     edx, r15d
0x180059c12  movups  xmmword ptr [rsp+0E8h+pvar], xmm0
0x180059c17  mov     [rsp+0E8h+var_B8], r15d
0x180059c1c  mov     rax, [rax+18h]
0x180059c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c25  mov     edi, eax
0x180059c27  test    eax, eax
0x180059c29  jnz     short loc_180059C9A
0x180059c2b  mov     rcx, [rsp+0E8h+pvar+8]
0x180059c30  test    rcx, rcx
0x180059c33  jnz     short loc_180059C3C
0x180059c35  lea     rcx, Class; psz
0x180059c3c  call    cs:__imp_SysAllocString
0x180059c42  mov     [r14], rax
0x180059c45  test    rax, rax
0x180059c48  jnz     short loc_180059C8D
0x180059c4a  lea     rcx, aSysallocstring; "SysAllocString failed"
0x180059c51  call    WiaTrace_TraceLog
0x180059c56  mov     rdx, rax; char *
0x180059c59  mov     rcx, rbp; char *
0x180059c5c  mov     rbx, rax
0x180059c5f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180059c64  mov     rcx, rbx; this
0x180059c67  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180059c6c  lea     rcx, aSysallocstring; "SysAllocString failed"
0x180059c73  call    WiaTrace_Trace
0x180059c78  mov     r9d, r15d; int
0x180059c7b  mov     [rsp+0E8h+lpMem], rax; lpMem
0x180059c80  mov     r8, rbp; int
0x180059c83  call    WiaTrace_ProcessTrace_Ex
0x180059c88  mov     edi, 8007000Eh
0x180059c8d  lea     rcx, [rsp+0E8h+pvar]; pvar
0x180059c92  call    cs:__imp_PropVariantClear
0x180059c98  jmp     short loc_180059D11
0x180059c9a  mov     edx, esi
0x180059c9c  cmp     eax, r15d
0x180059c9f  jnz     short loc_180059CD1
0x180059ca1  lea     rcx, aReadmultipleFa_0; "ReadMultiple failed to read required pr"...
0x180059ca8  mov     edi, 80070057h
0x180059cad  call    WiaTrace_TraceLog
0x180059cb2  mov     rdx, rax; char *
0x180059cb5  mov     rcx, rbp; char *
0x180059cb8  mov     rbx, rax
0x180059cbb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180059cc0  mov     rcx, rbx; this
0x180059cc3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180059cc8  lea     rcx, aReadmultipleFa_0; "ReadMultiple failed to read required pr"...
0x180059ccf  jmp     short loc_180059CFA
0x180059cd1  lea     rcx, aReadmultipleOf; "ReadMultiple of propid: %d, failed"
0x180059cd8  call    WiaTrace_TraceLog
0x180059cdd  mov     rdx, rax; char *
0x180059ce0  mov     rcx, rbp; char *
0x180059ce3  mov     rbx, rax
0x180059ce6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180059ceb  mov     rcx, rbx; this
0x180059cee  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180059cf3  lea     rcx, aReadmultipleOf; "ReadMultiple of propid: %d, failed"
0x180059cfa  mov     edx, esi
0x180059cfc  call    WiaTrace_Trace
0x180059d01  mov     r9d, r15d; int
0x180059d04  mov     [rsp+0E8h+lpMem], rax; lpMem
0x180059d09  mov     r8, rbp; int
0x180059d0c  call    WiaTrace_ProcessTrace_Ex
0x180059d11  lea     rcx, [rsp+0E8h+var_88]; this
0x180059d16  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180059d1b  mov     eax, edi
0x180059d1d  add     rsp, 0B8h
0x180059d24  pop     r15
0x180059d26  pop     r14
0x180059d28  pop     rdi
0x180059d29  pop     rsi
0x180059d2a  pop     rbp
0x180059d2b  pop     rbx
0x180059d2c  retn
```
