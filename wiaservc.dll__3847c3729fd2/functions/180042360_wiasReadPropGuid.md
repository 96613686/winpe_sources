# wiasReadPropGuid

- ea: `0x180042360`
- end: `0x180042585`
- name: `wiasReadPropGuid`
- size: `549`
- prototype: `__int64 __usercall@<rax>(CWiaItem *this@<rcx>, int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800405b0`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800189cc`
- `0x180018ad8`
- `0x18001f614`
- `0x18002de18`
- `0x18002def8`
- `0x180042360`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1800424d9`
- `ole32!PropVariantClear` at `0x180042515`
- `ole32!PropVariantClear` at `0x1800424d9`
- `ole32!PropVariantClear` at `0x180042515`

## string_xrefs

- `0x180042385`: `::wiasReadPropGuid`
- `0x180042397`: `wiasReadPropGuid`
- `0x1800423bd`: `wiasReadPropGuid, invalid pItem`
- `0x1800423df`: `wiasReadPropGuid, invalid pItem`
- `0x180042408`: `wiasReadPropGuid, invalid plVal pointer`
- `0x18004242a`: `wiasReadPropGuid, invalid plVal pointer`

## pseudocode

```c
__int64 __fastcall wiasReadPropGuid(struct IWiaItem *this, PROPID a2, _OWORD *a3, _OWORD *a4, int a5)
{
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  int v12; // esi
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  int ItemPropStreams; // eax
  int v24; // ebx
  int v25; // esi
  unsigned int lpMem; // [rsp+20h] [rbp-61h]
  struct IPropertyStorage *v28; // [rsp+30h] [rbp-51h] BYREF
  struct tagPROPSPEC v29; // [rsp+38h] [rbp-49h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v31; // [rsp+58h] [rbp-29h]
  _BYTE v32[80]; // [rsp+60h] [rbp-21h] BYREF
  struct IPropertyStorage *v33; // [rsp+E0h] [rbp+5Fh] BYREF

  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasReadPropGuid");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v32, v10, v11, "wiasReadPropGuid", lpMem, v9);
  v12 = ValidateWiaItem(this);
  if ( v12 >= 0 )
  {
    if ( !a3 )
    {
      v18 = (char *)WiaTrace_TraceLog("wiasReadPropGuid, invalid plVal pointer");
      WriteDbgTraceErrorWI("wiasReadPropGuid", v18);
      WiaTrcLib::Free((WiaTrcLib *)v18, v19);
      v20 = (void **)WiaTrace_Trace("wiasReadPropGuid, invalid plVal pointer");
      WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"wiasReadPropGuid", 1, v20);
      v12 = -2147467261;
      goto LABEL_17;
    }
    v33 = 0;
    v28 = 0;
    ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v33, 0, 0, &v28);
    if ( ItemPropStreams < 0 )
    {
      v12 = ItemPropStreams;
      goto LABEL_17;
    }
    v31 = 0;
    v29 = 0;
    v29.ulKind = 1;
    v29.propid = a2;
    *(_OWORD *)pvar = 0;
    v24 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, PROPVARIANT *))v33->lpVtbl->ReadMultiple)(
            v33,
            1,
            &v29,
            pvar);
    if ( !v24 )
    {
      *a3 = *(_OWORD *)pvar[1];
      PropVariantClear(pvar);
      if ( !a4 )
      {
LABEL_16:
        v12 = v24;
        goto LABEL_17;
      }
      v24 = ((__int64 (__fastcall *)(struct IPropertyStorage *, _QWORD, struct tagPROPSPEC *, PROPVARIANT *))v28->lpVtbl->ReadMultiple)(
              v28,
              (unsigned int)(v24 + 1),
              &v29,
              pvar);
      if ( !v24 )
      {
        *a4 = *(_OWORD *)pvar[1];
        PropVariantClear(pvar);
        goto LABEL_16;
      }
    }
    v25 = a5;
    if ( v24 == 1 && a5 || v24 < 0 )
    {
      ReportReadWriteMultipleError(v24, "wiasReadPropGuid", 0, 1, 1u, &v29);
      if ( v25 )
        v24 = -2147024809;
    }
    goto LABEL_16;
  }
  v13 = (char *)WiaTrace_TraceLog("wiasReadPropGuid, invalid pItem");
  WriteDbgTraceErrorWI("wiasReadPropGuid", v13);
  WiaTrcLib::Free((WiaTrcLib *)v13, v14);
  v15 = (void **)WiaTrace_Trace("wiasReadPropGuid, invalid pItem");
  WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"wiasReadPropGuid", 1, v15);
LABEL_17:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v32);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180042360  mov     [rsp-8+arg_8], rbx
0x180042365  mov     [rsp-8+arg_10], rsi
0x18004236a  push    rbp
0x18004236b  push    r12
0x18004236d  push    r13
0x18004236f  push    r14
0x180042371  push    r15
0x180042373  lea     rbp, [rsp-2Fh]
0x180042378  sub     rsp, 0B0h
0x18004237f  mov     rbx, rcx
0x180042382  mov     r15, r9
0x180042385  lea     rcx, aWiasreadpropgu_3; "::wiasReadPropGuid"
0x18004238c  mov     r14, r8
0x18004238f  mov     r12d, edx
0x180042392  call    WiaTrace_Trace
0x180042397  lea     r13, aWiasreadpropgu_2; "wiasReadPropGuid"
0x18004239e  mov     [rsp+0D0h+var_A8], rax; struct tagWiaTraceData_Type *
0x1800423a3  mov     r9, r13; char *
0x1800423a6  lea     rcx, [rbp+4Fh+var_70]; this
0x1800423aa  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800423af  mov     rcx, rbx; struct IWiaItem *
0x1800423b2  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x1800423b7  mov     esi, eax
0x1800423b9  test    eax, eax
0x1800423bb  jns     short loc_180042403
0x1800423bd  lea     rcx, aWiasreadpropgu_0; "wiasReadPropGuid, invalid pItem"
0x1800423c4  call    WiaTrace_TraceLog
0x1800423c9  mov     rdx, rax; char *
0x1800423cc  mov     rcx, r13; char *
0x1800423cf  mov     rbx, rax
0x1800423d2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800423d7  mov     rcx, rbx; this
0x1800423da  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800423df  lea     rcx, aWiasreadpropgu_0; "wiasReadPropGuid, invalid pItem"
0x1800423e6  call    WiaTrace_Trace
0x1800423eb  mov     r9d, 1; int
0x1800423f1  mov     [rsp+0D0h+lpMem], rax; lpMem
0x1800423f6  mov     r8, r13; int
0x1800423f9  call    WiaTrace_ProcessTrace_Ex
0x1800423fe  jmp     loc_18004255D
0x180042403  test    r14, r14
0x180042406  jnz     short loc_180042451
0x180042408  lea     rcx, aWiasreadpropgu_1; "wiasReadPropGuid, invalid plVal pointer"
0x18004240f  call    WiaTrace_TraceLog
0x180042414  mov     rdx, rax; char *
0x180042417  mov     rcx, r13; char *
0x18004241a  mov     rbx, rax
0x18004241d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180042422  mov     rcx, rbx; this
0x180042425  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004242a  lea     rcx, aWiasreadpropgu_1; "wiasReadPropGuid, invalid plVal pointer"
0x180042431  call    WiaTrace_Trace
0x180042436  lea     r9d, [r14+1]; int
0x18004243a  mov     [rsp+0D0h+lpMem], rax; lpMem
0x18004243f  mov     r8, r13; int
0x180042442  call    WiaTrace_ProcessTrace_Ex
0x180042447  mov     esi, 80004003h
0x18004244c  jmp     loc_18004255D
0x180042451  lea     rax, [rbp+4Fh+var_A0]
0x180042455  mov     [rbp+4Fh+arg_0], 0
0x18004245d  xor     r9d, r9d; struct IPropertyStorage **
0x180042460  mov     [rsp+0D0h+lpMem], rax; struct IPropertyStorage **
0x180042465  xor     r8d, r8d; struct IPropertyStorage **
0x180042468  mov     [rbp+4Fh+var_A0], 0
0x180042470  lea     rdx, [rbp+4Fh+arg_0]; struct IPropertyStorage **
0x180042474  mov     rcx, rbx; this
0x180042477  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x18004247c  test    eax, eax
0x18004247e  jns     short loc_180042487
0x180042480  mov     esi, eax
0x180042482  jmp     loc_18004255D
0x180042487  mov     rcx, [rbp+4Fh+arg_0]
0x18004248b  lea     r9, [rbp+4Fh+pvar]
0x18004248f  xor     eax, eax
0x180042491  lea     r8, [rbp+4Fh+var_98]
0x180042495  mov     [rbp+4Fh+var_78], rax
0x180042499  xorps   xmm0, xmm0
0x18004249c  movups  xmmword ptr [rbp+4Fh+var_98.ulKind], xmm0
0x1800424a0  mov     [rbp+4Fh+var_98.ulKind], 1
0x1800424a7  mov     edx, 1
0x1800424ac  xorps   xmm1, xmm1
0x1800424af  mov     dword ptr [rbp+4Fh+var_98.8], r12d
0x1800424b3  movups  xmmword ptr [rbp+4Fh+pvar], xmm1
0x1800424b7  mov     rax, [rcx]
0x1800424ba  mov     rax, [rax+18h]
0x1800424be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424c3  mov     ebx, eax
0x1800424c5  test    eax, eax
0x1800424c7  jnz     short loc_18004251D
0x1800424c9  mov     rcx, [rbp+4Fh+pvar+8]
0x1800424cd  movups  xmm0, xmmword ptr [rcx]
0x1800424d0  lea     rcx, [rbp+4Fh+pvar]; pvar
0x1800424d4  movdqu  xmmword ptr [r14], xmm0
0x1800424d9  call    cs:__imp_PropVariantClear
0x1800424df  test    r15, r15
0x1800424e2  jz      short loc_18004255B
0x1800424e4  mov     rcx, [rbp+4Fh+var_A0]
0x1800424e8  lea     r9, [rbp+4Fh+pvar]
0x1800424ec  lea     r8, [rbp+4Fh+var_98]
0x1800424f0  lea     edx, [rbx+1]
0x1800424f3  mov     rax, [rcx]
0x1800424f6  mov     rax, [rax+18h]
0x1800424fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424ff  mov     ebx, eax
0x180042501  test    eax, eax
0x180042503  jnz     short loc_18004251D
0x180042505  mov     rax, [rbp+4Fh+pvar+8]
0x180042509  lea     rcx, [rbp+4Fh+pvar]; pvar
0x18004250d  movups  xmm0, xmmword ptr [rax]
0x180042510  movdqu  xmmword ptr [r15], xmm0
0x180042515  call    cs:__imp_PropVariantClear
0x18004251b  jmp     short loc_18004255B
0x18004251d  mov     esi, [rbp+4Fh+arg_20]
0x180042520  cmp     ebx, 1
0x180042523  jnz     short loc_180042529
0x180042525  test    esi, esi
0x180042527  jnz     short loc_18004252D
0x180042529  test    ebx, ebx
0x18004252b  jns     short loc_18004255B
0x18004252d  lea     rax, [rbp+4Fh+var_98]
0x180042531  mov     r9d, 1; int
0x180042537  mov     [rsp+0D0h+var_A8], rax; struct tagPROPSPEC *
0x18004253c  xor     r8d, r8d; char *
0x18004253f  mov     rdx, r13; char *
0x180042542  mov     dword ptr [rsp+0D0h+lpMem], 1; unsigned int
0x18004254a  mov     ecx, ebx; int
0x18004254c  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x180042551  test    esi, esi
0x180042553  mov     eax, 80070057h
0x180042558  cmovnz  ebx, eax
0x18004255b  mov     esi, ebx
0x18004255d  lea     rcx, [rbp+4Fh+var_70]; this
0x180042561  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180042566  lea     r11, [rsp+0D0h+var_20]
0x18004256e  mov     eax, esi
0x180042570  mov     rbx, [r11+38h]
0x180042574  mov     rsi, [r11+40h]
0x180042578  mov     rsp, r11
0x18004257b  pop     r15
0x18004257d  pop     r14
0x18004257f  pop     r13
0x180042581  pop     r12
0x180042583  pop     rbp
0x180042584  retn
```
