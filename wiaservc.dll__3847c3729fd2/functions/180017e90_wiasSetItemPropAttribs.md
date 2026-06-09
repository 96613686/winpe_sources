# wiasSetItemPropAttribs

- ea: `0x180017e90`
- end: `0x18001817a`
- name: `wiasSetItemPropAttribs`
- size: `746`
- prototype: `__int64 __fastcall(CWiaItem *this)`
- caller_count: `5`
- callee_count: `12`
- tags: ``

## callers

- `0x18001901c`
- `0x180019eac`
- `0x180063688`
- `0x180064a6c`
- `0x180064fc0`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x180017e90`
- `0x180018180`
- `0x1800185a0`
- `0x1800189cc`
- `0x18002de18`
- `0x18002def8`
- `0x1800649a0`

## import_xrefs

- `ole32!PropVariantClear` at `0x1800180ef`
- `ole32!PropVariantClear` at `0x1800180ef`

## string_xrefs

- `0x180017eb4`: `::wiasSetItemPropAttribs`
- `0x180017ec6`: `wiasSetItemPropAttribs`
- `0x180018114`: `wiasSetItemPropAttribs`
- `0x180018137`: `wiasSetItemPropAttribs`
- `0x180017fa6`: `CWiaItem::GetItemPropStreams`
- `0x180017ef0`: `wiasSetItemPropAttribs, invalid pItem`
- `0x180017f12`: `wiasSetItemPropAttribs, invalid pItem`
- `0x180017f2b`: `wiasSetItemPropAttribs, bad pPropSpec parameter`
- `0x180017f4d`: `wiasSetItemPropAttribs, bad pPropSpec parameter`
- `0x180017f7b`: `wiasSetItemPropAttribs, bad pwpi parameter`
- `0x180017f9d`: `wiasSetItemPropAttribs, bad pwpi parameter`
- `0x180018105`: `wiasSetItemPropAttribs, call to wiasSetPropertyAttributes failed`
- `0x18001812b`: `wiasSetItemPropAttribs, call to wiasSetPropertyAttributes failed`

## pseudocode

```c
__int64 __fastcall wiasSetItemPropAttribs(struct IWiaItem *this, int a2, __int64 a3, __int64 a4)
{
  int v7; // r14d
  struct tagWiaTraceData_Type *v8; // rax
  char *v9; // rdx
  unsigned int v10; // r8d
  int inited; // edi
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  char *v22; // rbx
  void *v23; // rdx
  struct tagWiaTraceData_Type *v24; // rax
  char *v25; // rdx
  unsigned int v26; // r8d
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  int i; // ebx
  char *v38; // rbx
  void *v39; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-F8h]
  unsigned int lpMema; // [rsp+20h] [rbp-F8h]
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v44[80]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v45[80]; // [rsp+A0h] [rbp-78h] BYREF

  v7 = a2;
  v8 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasSetItemPropAttribs");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v45, v9, v10, "wiasSetItemPropAttribs", lpMem, v8);
  inited = ValidateWiaItem(this);
  if ( inited < 0 )
  {
    v12 = (char *)WiaTrace_TraceLog("wiasSetItemPropAttribs, invalid pItem");
    WriteDbgTraceErrorWI("wiasSetItemPropAttribs", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("wiasSetItemPropAttribs, invalid pItem");
LABEL_20:
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"wiasSetItemPropAttribs", 1, v14);
    goto LABEL_21;
  }
  if ( !a3 )
  {
    v17 = (char *)WiaTrace_TraceLog("wiasSetItemPropAttribs, bad pPropSpec parameter");
    WriteDbgTraceErrorWI("wiasSetItemPropAttribs", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v19 = (void **)WiaTrace_Trace("wiasSetItemPropAttribs, bad pPropSpec parameter");
LABEL_5:
    WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"wiasSetItemPropAttribs", 1, v19);
    inited = -2147467261;
    goto LABEL_21;
  }
  if ( !a4 )
  {
    v22 = (char *)WiaTrace_TraceLog("wiasSetItemPropAttribs, bad pwpi parameter");
    WriteDbgTraceErrorWI("wiasSetItemPropAttribs", v22);
    WiaTrcLib::Free((WiaTrcLib *)v22, v23);
    v19 = (void **)WiaTrace_Trace("wiasSetItemPropAttribs, bad pwpi parameter");
    goto LABEL_5;
  }
  v24 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::GetItemPropStreams");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v44, v25, v26, "CWiaItem::GetItemPropStreams", lpMema, v24);
  if ( this[27].lpVtbl )
  {
    inited = 0;
    if ( !LODWORD(this[16].lpVtbl) )
    {
      inited = CWiaItem::InitLazyProps((CWiaItem *)this);
      if ( inited < 0 )
      {
        v32 = (char *)WiaTrace_TraceLog("InitLazyProps failed");
        WriteDbgTraceErrorWI("CWiaItem::GetItemPropStreams", v32);
        WiaTrcLib::Free((WiaTrcLib *)v32, v33);
        v34 = (void **)WiaTrace_Trace("InitLazyProps failed");
        WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"CWiaItem::GetItemPropStreams", 1, v34);
      }
    }
  }
  else
  {
    v27 = (char *)WiaTrace_TraceLog("NULL internal property storage pointer");
    WriteDbgTraceErrorWI("CWiaItem::GetItemPropStreams", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v29 = (void **)WiaTrace_Trace("NULL internal property storage pointer");
    WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaItem::GetItemPropStreams", 1, v29);
    inited = -2147467259;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v44);
  if ( inited >= 0 )
  {
    for ( i = 0; i < v7; ++i )
    {
      memset(&pvar, 0, sizeof(pvar));
      inited = WiaPropertyInfoToPropVariant((struct _WIA_PROPERTY_INFO *)(a4 + 40LL * i), &pvar);
      if ( inited < 0 )
        break;
      inited = wiasSetPropertyAttributes((CWiaItem *)this, (__int64)&pvar);
      PropVariantClear((PROPVARIANT *)&pvar);
      if ( inited < 0 )
      {
        v38 = (char *)WiaTrace_TraceLog("wiasSetItemPropAttribs, call to wiasSetPropertyAttributes failed");
        WriteDbgTraceErrorWI("wiasSetItemPropAttribs", v38);
        WiaTrcLib::Free((WiaTrcLib *)v38, v39);
        v14 = (void **)WiaTrace_Trace("wiasSetItemPropAttribs, call to wiasSetPropertyAttributes failed");
        goto LABEL_20;
      }
      v7 = a2;
    }
  }
LABEL_21:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v45);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180017e90  mov     [rsp+arg_0], rbx
0x180017e95  mov     [rsp+arg_10], rbp
0x180017e9a  mov     [rsp+arg_8], edx
0x180017e9e  push    rdi
0x180017e9f  push    r12
0x180017ea1  push    r13
0x180017ea3  push    r14
0x180017ea5  push    r15
0x180017ea7  sub     rsp, 0F0h
0x180017eae  mov     rbp, rcx
0x180017eb1  mov     r12, r9
0x180017eb4  lea     rcx, aWiassetitempro_10; "::wiasSetItemPropAttribs"
0x180017ebb  mov     r13, r8
0x180017ebe  mov     r14d, edx
0x180017ec1  call    WiaTrace_Trace
0x180017ec6  lea     r15, aWiassetitempro_4; "wiasSetItemPropAttribs"
0x180017ecd  mov     [rsp+118h+var_F0], rax; struct tagWiaTraceData_Type *
0x180017ed2  mov     r9, r15; char *
0x180017ed5  lea     rcx, [rsp+118h+var_78]; this
0x180017edd  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180017ee2  mov     rcx, rbp; struct IWiaItem *
0x180017ee5  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180017eea  mov     edi, eax
0x180017eec  test    eax, eax
0x180017eee  jns     short loc_180017F26
0x180017ef0  lea     rcx, aWiassetitempro_5; "wiasSetItemPropAttribs, invalid pItem"
0x180017ef7  call    WiaTrace_TraceLog
0x180017efc  mov     rdx, rax; char *
0x180017eff  mov     rcx, r15; char *
0x180017f02  mov     rbx, rax
0x180017f05  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017f0a  mov     rcx, rbx; this
0x180017f0d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017f12  lea     rcx, aWiassetitempro_5; "wiasSetItemPropAttribs, invalid pItem"
0x180017f19  call    WiaTrace_Trace
0x180017f1e  mov     r8, r15
0x180017f21  jmp     loc_18001813E
0x180017f26  test    r13, r13
0x180017f29  jnz     short loc_180017F76
0x180017f2b  lea     rcx, aWiassetitempro_11; "wiasSetItemPropAttribs, bad pPropSpec p"...
0x180017f32  call    WiaTrace_TraceLog
0x180017f37  mov     rdx, rax; char *
0x180017f3a  mov     rcx, r15; char *
0x180017f3d  mov     rbx, rax
0x180017f40  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017f45  mov     rcx, rbx; this
0x180017f48  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017f4d  lea     rcx, aWiassetitempro_11; "wiasSetItemPropAttribs, bad pPropSpec p"...
0x180017f54  call    WiaTrace_Trace
0x180017f59  mov     r9d, 1; int
0x180017f5f  mov     [rsp+118h+lpMem], rax; lpMem
0x180017f64  mov     r8, r15; int
0x180017f67  call    WiaTrace_ProcessTrace_Ex
0x180017f6c  mov     edi, 80004003h
0x180017f71  jmp     loc_18001814E
0x180017f76  test    r12, r12
0x180017f79  jnz     short loc_180017FA6
0x180017f7b  lea     rcx, aWiassetitempro_8; "wiasSetItemPropAttribs, bad pwpi parame"...
0x180017f82  call    WiaTrace_TraceLog
0x180017f87  mov     rdx, rax; char *
0x180017f8a  mov     rcx, r15; char *
0x180017f8d  mov     rbx, rax
0x180017f90  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017f95  mov     rcx, rbx; this
0x180017f98  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017f9d  lea     rcx, aWiassetitempro_8; "wiasSetItemPropAttribs, bad pwpi parame"...
0x180017fa4  jmp     short loc_180017F54
0x180017fa6  lea     r15, aCwiaitemGetite; "CWiaItem::GetItemPropStreams"
0x180017fad  mov     rcx, r15
0x180017fb0  call    WiaTrace_Trace
0x180017fb5  mov     r9, r15; char *
0x180017fb8  mov     [rsp+118h+var_F0], rax; struct tagWiaTraceData_Type *
0x180017fbd  lea     rcx, [rsp+118h+var_C8]; this
0x180017fc2  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180017fc7  cmp     qword ptr [rbp+0D8h], 0
0x180017fcf  jnz     short loc_180018019
0x180017fd1  lea     rcx, aNullInternalPr; "NULL internal property storage pointer"
0x180017fd8  call    WiaTrace_TraceLog
0x180017fdd  mov     rdx, rax; char *
0x180017fe0  mov     rcx, r15; char *
0x180017fe3  mov     rbx, rax
0x180017fe6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017feb  mov     rcx, rbx; this
0x180017fee  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017ff3  lea     rcx, aNullInternalPr; "NULL internal property storage pointer"
0x180017ffa  call    WiaTrace_Trace
0x180017fff  mov     r9d, 1; int
0x180018005  mov     [rsp+118h+lpMem], rax; lpMem
0x18001800a  mov     r8, r15; int
0x18001800d  call    WiaTrace_ProcessTrace_Ex
0x180018012  mov     edi, 80004005h
0x180018017  jmp     short loc_180018072
0x180018019  xor     edi, edi
0x18001801b  cmp     [rbp+80h], edi
0x180018021  jnz     short loc_180018072
0x180018023  mov     rcx, rbp; this
0x180018026  call    ?InitLazyProps@CWiaItem@@QEAAJXZ; CWiaItem::InitLazyProps(void)
0x18001802b  mov     edi, eax
0x18001802d  test    eax, eax
0x18001802f  jns     short loc_180018072
0x180018031  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x180018038  call    WiaTrace_TraceLog
0x18001803d  mov     rdx, rax; char *
0x180018040  mov     rcx, r15; char *
0x180018043  mov     rbx, rax
0x180018046  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001804b  mov     rcx, rbx; this
0x18001804e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018053  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x18001805a  call    WiaTrace_Trace
0x18001805f  mov     r9d, 1; int
0x180018065  mov     [rsp+118h+lpMem], rax; lpMem
0x18001806a  mov     r8, r15; int
0x18001806d  call    WiaTrace_ProcessTrace_Ex
0x180018072  lea     rcx, [rsp+118h+var_C8]; this
0x180018077  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18001807c  test    edi, edi
0x18001807e  js      loc_18001814E
0x180018084  xor     ebx, ebx
0x180018086  cmp     ebx, r14d
0x180018089  jge     loc_18001814E
0x18001808f  xor     eax, eax
0x180018091  movsxd  r14, ebx
0x180018094  mov     [rsp+118h+var_D8], rax
0x180018099  lea     rdx, [rsp+118h+pvar]; struct tagPROPVARIANT *
0x18001809e  xorps   xmm0, xmm0
0x1800180a1  movups  xmmword ptr [rsp+118h+pvar], xmm0
0x1800180a6  lea     rax, [r14+r14*4]
0x1800180aa  lea     r15, [r12+rax*8]
0x1800180ae  mov     rcx, r15; struct _WIA_PROPERTY_INFO *
0x1800180b1  call    ?WiaPropertyInfoToPropVariant@@YAJPEAU_WIA_PROPERTY_INFO@@PEAUtagPROPVARIANT@@@Z; WiaPropertyInfoToPropVariant(_WIA_PROPERTY_INFO *,tagPROPVARIANT *)
0x1800180b6  mov     edi, eax
0x1800180b8  test    eax, eax
0x1800180ba  js      loc_18001814E
0x1800180c0  lea     rax, [rsp+118h+pvar]
0x1800180c5  add     r14, r14
0x1800180c8  mov     r9, r15
0x1800180cb  mov     [rsp+118h+lpMem], rax; __int64
0x1800180d0  mov     edx, 1
0x1800180d5  mov     rcx, rbp; this
0x1800180d8  lea     r8, ds:0[r14*8]
0x1800180e0  add     r8, r13
0x1800180e3  call    wiasSetPropertyAttributes
0x1800180e8  lea     rcx, [rsp+118h+pvar]; pvar
0x1800180ed  mov     edi, eax
0x1800180ef  call    cs:__imp_PropVariantClear
0x1800180f5  test    edi, edi
0x1800180f7  js      short loc_180018105
0x1800180f9  mov     r14d, [rsp+118h+arg_8]
0x180018101  inc     ebx
0x180018103  jmp     short loc_180018086
0x180018105  lea     rcx, aWiassetitempro_3; "wiasSetItemPropAttribs, call to wiasSet"...
0x18001810c  call    WiaTrace_TraceLog
0x180018111  mov     rdx, rax; char *
0x180018114  lea     rcx, aWiassetitempro_4; "wiasSetItemPropAttribs"
0x18001811b  mov     rbx, rax
0x18001811e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018123  mov     rcx, rbx; this
0x180018126  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001812b  lea     rcx, aWiassetitempro_3; "wiasSetItemPropAttribs, call to wiasSet"...
0x180018132  call    WiaTrace_Trace
0x180018137  lea     r8, aWiassetitempro_4; "wiasSetItemPropAttribs"
0x18001813e  mov     r9d, 1; int
0x180018144  mov     [rsp+118h+lpMem], rax; lpMem
0x180018149  call    WiaTrace_ProcessTrace_Ex
0x18001814e  lea     rcx, [rsp+118h+var_78]; this
0x180018156  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18001815b  lea     r11, [rsp+118h+var_28]
0x180018163  mov     eax, edi
0x180018165  mov     rbx, [r11+30h]
0x180018169  mov     rbp, [r11+40h]
0x18001816d  mov     rsp, r11
0x180018170  pop     r15
0x180018172  pop     r14
0x180018174  pop     r13
0x180018176  pop     r12
0x180018178  pop     rdi
0x180018179  retn
```
