# wiasReadPropStr

- ea: `0x180042590`
- end: `0x180042875`
- name: `wiasReadPropStr`
- size: `741`
- prototype: `__int64 __usercall@<rax>(CWiaItem *this@<rcx>, int)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800408f0`
- `0x180041570`

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
- `0x180042590`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004271b`
- `OLEAUT32!__imp_SysAllocString` at `0x180042769`
- `OLEAUT32!__imp_SysAllocString` at `0x18004271b`
- `OLEAUT32!__imp_SysAllocString` at `0x180042769`
- `OLEAUT32!__imp_SysFreeString` at `0x180042789`
- `OLEAUT32!__imp_SysFreeString` at `0x180042789`
- `ole32!PropVariantClear` at `0x180042728`
- `ole32!PropVariantClear` at `0x180042776`
- `ole32!PropVariantClear` at `0x180042728`
- `ole32!PropVariantClear` at `0x180042776`

## string_xrefs

- `0x1800425b4`: `::wiasReadPropStr`
- `0x1800425c6`: `wiasReadPropStr`
- `0x180042625`: `wiasReadPropStr`
- `0x180042672`: `wiasReadPropStr`
- `0x1800427a5`: `wiasReadPropStr`
- `0x1800427d0`: `wiasReadPropStr`
- `0x1800427f2`: `wiasReadPropStr`
- `0x18004282d`: `wiasReadPropStr`
- `0x1800425ec`: `wiasReadPropStr, invalid pItem`
- `0x18004260e`: `wiasReadPropStr, invalid pItem`
- `0x18004263b`: `wiasReadPropStr, invalid pbstr pointer`
- `0x18004265d`: `wiasReadPropStr, invalid pbstr pointer`
- `0x18004278f`: `wiasReadPropStr, run out of memory`
- `0x1800427bc`: `wiasReadPropStr, run out of memory`
- `0x1800427e3`: `wiasReadPropStr, out of memory error`
- `0x180042809`: `wiasReadPropStr, out of memory error`

## pseudocode

```c
__int64 __fastcall wiasReadPropStr(struct IWiaItem *this, PROPID a2, BSTR *a3, BSTR *a4, int a5)
{
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  int v12; // edi
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
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  char *v30; // rbx
  void *v31; // rdx
  int v32; // edi
  unsigned int lpMem; // [rsp+20h] [rbp-61h]
  struct IPropertyStorage *v35; // [rsp+30h] [rbp-51h] BYREF
  struct tagPROPSPEC v36; // [rsp+38h] [rbp-49h] BYREF
  OLECHAR *psz[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v38; // [rsp+58h] [rbp-29h]
  _BYTE v39[80]; // [rsp+60h] [rbp-21h] BYREF
  struct IPropertyStorage *v40; // [rsp+E0h] [rbp+5Fh] BYREF

  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasReadPropStr");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v39, v10, v11, "wiasReadPropStr", lpMem, v9);
  v12 = ValidateWiaItem(this);
  if ( v12 < 0 )
  {
    v13 = (char *)WiaTrace_TraceLog("wiasReadPropStr, invalid pItem");
    WriteDbgTraceErrorWI("wiasReadPropStr", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void **)WiaTrace_Trace("wiasReadPropStr, invalid pItem");
    WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"wiasReadPropStr", 1, v15);
    goto LABEL_25;
  }
  if ( !a3 )
  {
    v18 = (char *)WiaTrace_TraceLog("wiasReadPropStr, invalid pbstr pointer");
    WriteDbgTraceErrorWI("wiasReadPropStr", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    v20 = (void **)WiaTrace_Trace("wiasReadPropStr, invalid pbstr pointer");
    WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"wiasReadPropStr", 1, v20);
    v12 = -2147467261;
    goto LABEL_25;
  }
  v40 = 0;
  v35 = 0;
  ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v40, 0, 0, &v35);
  if ( ItemPropStreams < 0 )
  {
    v12 = ItemPropStreams;
    goto LABEL_25;
  }
  v38 = 0;
  v36 = 0;
  v36.propid = a2;
  v36.ulKind = 1;
  *(_OWORD *)psz = 0;
  v24 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, OLECHAR **))v40->lpVtbl->ReadMultiple)(
          v40,
          1,
          &v36,
          psz);
  if ( v24 )
    goto LABEL_19;
  if ( psz[1] )
  {
    *a3 = SysAllocString(psz[1]);
    PropVariantClear((PROPVARIANT *)psz);
    if ( !*a3 )
    {
      v30 = (char *)WiaTrace_TraceLog("wiasReadPropStr, out of memory error");
      WriteDbgTraceErrorWI("wiasReadPropStr", v30);
      WiaTrcLib::Free((WiaTrcLib *)v30, v31);
      v27 = (void **)WiaTrace_Trace("wiasReadPropStr, out of memory error");
      goto LABEL_17;
    }
    if ( !a4 )
    {
LABEL_24:
      v12 = v24;
      goto LABEL_25;
    }
    v24 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, OLECHAR **))v35->lpVtbl->ReadMultiple)(
            v35,
            1,
            &v36,
            psz);
    if ( !v24 )
    {
      *a4 = SysAllocString(psz[1]);
      PropVariantClear((PROPVARIANT *)psz);
      if ( !*a4 )
      {
        SysFreeString(*a3);
        *a3 = 0;
        v25 = (char *)WiaTrace_TraceLog("wiasReadPropStr, run out of memory");
        WriteDbgTraceErrorWI("wiasReadPropStr", v25);
        WiaTrcLib::Free((WiaTrcLib *)v25, v26);
        v27 = (void **)WiaTrace_Trace("wiasReadPropStr, run out of memory");
LABEL_17:
        WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"wiasReadPropStr", 1, v27);
        v12 = -2147024882;
        goto LABEL_25;
      }
      goto LABEL_24;
    }
LABEL_19:
    v32 = a5;
    if ( v24 == 1 && a5 || v24 < 0 )
    {
      ReportReadWriteMultipleError(v24, "wiasReadPropStr", 0, 1, 1u, &v36);
      if ( v32 )
        v24 = -2147024809;
    }
    goto LABEL_24;
  }
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v12 = 0;
LABEL_25:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v39);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180042590  mov     [rsp-8+arg_8], rbx
0x180042595  mov     [rsp-8+arg_10], rsi
0x18004259a  push    rbp
0x18004259b  push    rdi
0x18004259c  push    r12
0x18004259e  push    r14
0x1800425a0  push    r15
0x1800425a2  lea     rbp, [rsp-2Fh]
0x1800425a7  sub     rsp, 0B0h
0x1800425ae  mov     rbx, rcx
0x1800425b1  mov     r14, r9
0x1800425b4  lea     rcx, aWiasreadpropst_2; "::wiasReadPropStr"
0x1800425bb  mov     r15, r8
0x1800425be  mov     r12d, edx
0x1800425c1  call    WiaTrace_Trace
0x1800425c6  lea     rsi, aWiasreadpropst_4; "wiasReadPropStr"
0x1800425cd  mov     [rsp+0D0h+var_A8], rax; struct tagWiaTraceData_Type *
0x1800425d2  mov     r9, rsi; char *
0x1800425d5  lea     rcx, [rbp+4Fh+var_70]; this
0x1800425d9  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800425de  mov     rcx, rbx; struct IWiaItem *
0x1800425e1  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x1800425e6  mov     edi, eax
0x1800425e8  test    eax, eax
0x1800425ea  jns     short loc_180042636
0x1800425ec  lea     rcx, aWiasreadpropst_3; "wiasReadPropStr, invalid pItem"
0x1800425f3  call    WiaTrace_TraceLog
0x1800425f8  mov     rdx, rax; char *
0x1800425fb  mov     rcx, rsi; char *
0x1800425fe  mov     rbx, rax
0x180042601  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180042606  mov     rcx, rbx; this
0x180042609  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004260e  lea     rcx, aWiasreadpropst_3; "wiasReadPropStr, invalid pItem"
0x180042615  call    WiaTrace_Trace
0x18004261a  mov     r9d, 1; int
0x180042620  mov     [rsp+0D0h+lpMem], rax; lpMem
0x180042625  lea     r8, aWiasreadpropst_4; "wiasReadPropStr"
0x18004262c  call    WiaTrace_ProcessTrace_Ex
0x180042631  jmp     loc_18004284E
0x180042636  test    r15, r15
0x180042639  jnz     short loc_180042688
0x18004263b  lea     rcx, aWiasreadpropst_0; "wiasReadPropStr, invalid pbstr pointer"
0x180042642  call    WiaTrace_TraceLog
0x180042647  mov     rdx, rax; char *
0x18004264a  mov     rcx, rsi; char *
0x18004264d  mov     rbx, rax
0x180042650  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180042655  mov     rcx, rbx; this
0x180042658  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004265d  lea     rcx, aWiasreadpropst_0; "wiasReadPropStr, invalid pbstr pointer"
0x180042664  call    WiaTrace_Trace
0x180042669  lea     r9d, [r15+1]; int
0x18004266d  mov     [rsp+0D0h+lpMem], rax; lpMem
0x180042672  lea     r8, aWiasreadpropst_4; "wiasReadPropStr"
0x180042679  call    WiaTrace_ProcessTrace_Ex
0x18004267e  mov     edi, 80004003h
0x180042683  jmp     loc_18004284E
0x180042688  lea     rax, [rbp+4Fh+var_A0]
0x18004268c  mov     [rbp+4Fh+arg_0], 0
0x180042694  xor     r9d, r9d; struct IPropertyStorage **
0x180042697  mov     [rsp+0D0h+lpMem], rax; struct IPropertyStorage **
0x18004269c  xor     r8d, r8d; struct IPropertyStorage **
0x18004269f  mov     [rbp+4Fh+var_A0], 0
0x1800426a7  lea     rdx, [rbp+4Fh+arg_0]; struct IPropertyStorage **
0x1800426ab  mov     rcx, rbx; this
0x1800426ae  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x1800426b3  test    eax, eax
0x1800426b5  jns     short loc_1800426BE
0x1800426b7  mov     edi, eax
0x1800426b9  jmp     loc_18004284E
0x1800426be  mov     rcx, [rbp+4Fh+arg_0]
0x1800426c2  lea     r9, [rbp+4Fh+psz]
0x1800426c6  xor     eax, eax
0x1800426c8  lea     r8, [rbp+4Fh+var_98]
0x1800426cc  mov     [rbp+4Fh+var_78], rax
0x1800426d0  xorps   xmm0, xmm0
0x1800426d3  movups  xmmword ptr [rbp+4Fh+var_98.ulKind], xmm0
0x1800426d7  mov     dword ptr [rbp+4Fh+var_98.8], r12d
0x1800426db  lea     esi, [rax+1]
0x1800426de  xorps   xmm1, xmm1
0x1800426e1  mov     [rbp+4Fh+var_98.ulKind], esi
0x1800426e4  mov     edx, esi
0x1800426e6  movups  xmmword ptr [rbp+4Fh+psz], xmm1
0x1800426ea  mov     rax, [rcx]
0x1800426ed  mov     rax, [rax+18h]
0x1800426f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426f6  mov     ebx, eax
0x1800426f8  test    eax, eax
0x1800426fa  jnz     loc_180042812
0x180042700  mov     rcx, [rbp+4Fh+psz+8]; psz
0x180042704  test    rcx, rcx
0x180042707  jnz     short loc_18004271B
0x180042709  mov     [r15], rcx
0x18004270c  test    r14, r14
0x18004270f  jz      short loc_180042714
0x180042711  mov     [r14], rcx
0x180042714  xor     edi, edi
0x180042716  jmp     loc_18004284E
0x18004271b  call    cs:__imp_SysAllocString
0x180042721  lea     rcx, [rbp+4Fh+psz]; pvar
0x180042725  mov     [r15], rax
0x180042728  call    cs:__imp_PropVariantClear
0x18004272e  cmp     qword ptr [r15], 0
0x180042732  jz      loc_1800427E3
0x180042738  test    r14, r14
0x18004273b  jz      loc_18004284C
0x180042741  mov     rcx, [rbp+4Fh+var_A0]
0x180042745  lea     r9, [rbp+4Fh+psz]
0x180042749  lea     r8, [rbp+4Fh+var_98]
0x18004274d  mov     edx, esi
0x18004274f  mov     rax, [rcx]
0x180042752  mov     rax, [rax+18h]
0x180042756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004275b  mov     ebx, eax
0x18004275d  test    eax, eax
0x18004275f  jnz     loc_180042812
0x180042765  mov     rcx, [rbp+4Fh+psz+8]; psz
0x180042769  call    cs:__imp_SysAllocString
0x18004276f  lea     rcx, [rbp+4Fh+psz]; pvar
0x180042773  mov     [r14], rax
0x180042776  call    cs:__imp_PropVariantClear
0x18004277c  cmp     qword ptr [r14], 0
0x180042780  jnz     loc_18004284C
0x180042786  mov     rcx, [r15]; bstrString
0x180042789  call    cs:__imp_SysFreeString
0x18004278f  lea     rcx, aWiasreadpropst_5; "wiasReadPropStr, run out of memory"
0x180042796  mov     qword ptr [r15], 0
0x18004279d  call    WiaTrace_TraceLog
0x1800427a2  mov     rdx, rax; char *
0x1800427a5  lea     rcx, aWiasreadpropst_4; "wiasReadPropStr"
0x1800427ac  mov     rbx, rax
0x1800427af  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800427b4  mov     rcx, rbx; this
0x1800427b7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800427bc  lea     rcx, aWiasreadpropst_5; "wiasReadPropStr, run out of memory"
0x1800427c3  call    WiaTrace_Trace
0x1800427c8  mov     r9d, esi; int
0x1800427cb  mov     [rsp+0D0h+lpMem], rax; lpMem
0x1800427d0  lea     r8, aWiasreadpropst_4; "wiasReadPropStr"
0x1800427d7  call    WiaTrace_ProcessTrace_Ex
0x1800427dc  mov     edi, 8007000Eh
0x1800427e1  jmp     short loc_18004284E
0x1800427e3  lea     rcx, aWiasreadpropst_1; "wiasReadPropStr, out of memory error"
0x1800427ea  call    WiaTrace_TraceLog
0x1800427ef  mov     rdx, rax; char *
0x1800427f2  lea     rcx, aWiasreadpropst_4; "wiasReadPropStr"
0x1800427f9  mov     rbx, rax
0x1800427fc  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180042801  mov     rcx, rbx; this
0x180042804  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180042809  lea     rcx, aWiasreadpropst_1; "wiasReadPropStr, out of memory error"
0x180042810  jmp     short loc_1800427C3
0x180042812  mov     edi, [rbp+4Fh+arg_20]
0x180042815  cmp     ebx, esi
0x180042817  jnz     short loc_18004281D
0x180042819  test    edi, edi
0x18004281b  jnz     short loc_180042821
0x18004281d  test    ebx, ebx
0x18004281f  jns     short loc_18004284C
0x180042821  lea     rax, [rbp+4Fh+var_98]
0x180042825  mov     r9d, esi; int
0x180042828  mov     [rsp+0D0h+var_A8], rax; struct tagPROPSPEC *
0x18004282d  lea     rdx, aWiasreadpropst_4; "wiasReadPropStr"
0x180042834  xor     r8d, r8d; char *
0x180042837  mov     dword ptr [rsp+0D0h+lpMem], esi; unsigned int
0x18004283b  mov     ecx, ebx; int
0x18004283d  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x180042842  test    edi, edi
0x180042844  mov     eax, 80070057h
0x180042849  cmovnz  ebx, eax
0x18004284c  mov     edi, ebx
0x18004284e  lea     rcx, [rbp+4Fh+var_70]; this
0x180042852  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180042857  lea     r11, [rsp+0D0h+var_20]
0x18004285f  mov     eax, edi
0x180042861  mov     rbx, [r11+38h]
0x180042865  mov     rsi, [r11+40h]
0x180042869  mov     rsp, r11
0x18004286c  pop     r15
0x18004286e  pop     r14
0x180042870  pop     r12
0x180042872  pop     rdi
0x180042873  pop     rbp
0x180042874  retn
```
