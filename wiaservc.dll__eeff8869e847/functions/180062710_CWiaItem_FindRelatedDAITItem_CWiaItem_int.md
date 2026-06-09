# CWiaItem::FindRelatedDAITItem(CWiaItem * *,int)

- ea: `0x180062710`
- end: `0x180062a69`
- name: `?FindRelatedDAITItem@CWiaItem@@QEAAJPEAPEAV1@H@Z`
- size: `857`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, struct CWiaItem **, int)`
- caller_count: `14`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001d7c0`
- `0x180031180`
- `0x180062a70`
- `0x180066198`
- `0x18006649c`
- `0x1800671d0`
- `0x180067310`
- `0x180067650`
- `0x18006b040`
- `0x18006d220`
- `0x18006d5f0`
- `0x18006ea30`
- `0x180072210`
- `0x180072450`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180062710`
- `0x1800659c8`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18006283d`
- `ole32!PropVariantClear` at `0x18006283d`

## string_xrefs

- `0x180062a09`: `not in compatibility mode or called on non A-AIT item (0x%X)`
- `0x180062a2d`: `not in compatibility mode or called on non A-AIT item (0x%X)`
- `0x18006284a`: `warning: A-AIT root->ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)`
- `0x180062870`: `warning: A-AIT root->ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)`
- `0x1800629d9`: `corrupted compatibility mode indicator (0x%X)`
- `0x1800629fb`: `corrupted compatibility mode indicator (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::FindRelatedDAITItem(CWiaItem *this, struct CWiaItem **a2, int a3)
{
  int v6; // edi
  char ***v7; // rax
  char *v8; // rdx
  __int64 v9; // r8
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  CWiaItem *v15; // rcx
  int v16; // r8d
  __int64 v17; // rax
  struct CWiaItem *v18; // rax
  char v19; // bp
  int v20; // ebp
  char *v21; // rbx
  void *v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  char *v32; // rbx
  void *v33; // rdx
  char *v34; // rbx
  void *v35; // rdx
  char *v36; // rbx
  void *v37; // rdx
  const char *v38; // rcx
  char *v39; // rbx
  void *v40; // rdx
  char *v41; // rbx
  void *v42; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-C8h]
  _DWORD v45[4]; // [rsp+30h] [rbp-B8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-98h]
  _BYTE v48[136]; // [rsp+60h] [rbp-88h] BYREF

  v6 = 0;
  v7 = (char ***)WiaTrace_Trace("CWiaItem::FindRelatedDAITItem");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v48, v8, v9, (char **)"CWiaItem::FindRelatedDAITItem", lpMem, v7);
  if ( !a2 )
  {
    v6 = -2147467261;
    v10 = (char *)WiaTrace_TraceLog("NULL parameter (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::FindRelatedDAITItem", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void **)WiaTrace_Trace("NULL parameter (0x%X)", -2147467261);
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"CWiaItem::FindRelatedDAITItem", 1, v12);
  }
  if ( !*(_QWORD *)(*((_QWORD *)this + 26) + 64LL) || !(unsigned int)CWiaItem::IsCompatMode(this) )
  {
    v6 = -2147467263;
    v41 = (char *)WiaTrace_TraceLog("not in compatibility mode or called on non A-AIT item (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::FindRelatedDAITItem", v41);
    WiaTrcLib::Free((WiaTrcLib *)v41, v42);
    v38 = "not in compatibility mode or called on non A-AIT item (0x%X)";
    goto LABEL_27;
  }
  if ( v6 >= 0 )
  {
    v17 = *((_QWORD *)this + 26);
    if ( (CWiaItem *)v17 == this )
    {
      v18 = *(struct CWiaItem **)(v17 + 64);
LABEL_24:
      *a2 = v18;
      goto LABEL_29;
    }
    if ( *(_DWORD *)(v17 + 104) == 2 )
    {
      v45[0] = 1;
      v45[2] = 3088;
      *(_OWORD *)pvar = 0;
      v47 = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _DWORD *, PROPVARIANT *))(***(_QWORD ***)(v17 + 216) + 24LL))(
             **(_QWORD **)(v17 + 216),
             1,
             v45,
             pvar);
      if ( v6 < 0 )
      {
        v20 = 0;
        v21 = (char *)WiaTrace_TraceLog("warning: A-AIT root->ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::FindRelatedDAITItem", v21);
        WiaTrcLib::Free((WiaTrcLib *)v21, v22);
        v23 = (void **)WiaTrace_Trace(
                         "warning: A-AIT root->ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)",
                         v6);
        WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"CWiaItem::FindRelatedDAITItem", 1, v23);
      }
      else
      {
        v19 = (char)pvar[1];
        PropVariantClear(pvar);
        v20 = v19 & 1;
      }
      v26 = *(_QWORD *)(*((_QWORD *)this + 26) + 64LL);
      if ( v20 )
      {
        v18 = *(struct CWiaItem **)(v26 + 88);
        if ( v18 )
          goto LABEL_24;
        v6 = -2147467261;
        v27 = (char *)WiaTrace_TraceLog("NULL D-AIT LH feeder item pointer (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::FindRelatedDAITItem", v27);
        WiaTrcLib::Free((WiaTrcLib *)v27, v28);
        v29 = (void **)WiaTrace_Trace("NULL D-AIT LH feeder item pointer (0x%X)", 2147500035LL);
      }
      else
      {
        v18 = *(struct CWiaItem **)(v26 + 96);
        if ( v18 )
          goto LABEL_24;
        v6 = -2147467261;
        v32 = (char *)WiaTrace_TraceLog("NULL D-AIT LH flatbed item pointer (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::FindRelatedDAITItem", v32);
        WiaTrcLib::Free((WiaTrcLib *)v32, v33);
        v29 = (void **)WiaTrace_Trace("NULL D-AIT LH flatbed item pointer (0x%X)", 2147500035LL);
      }
LABEL_28:
      WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaItem::FindRelatedDAITItem", 1, v29);
      goto LABEL_29;
    }
    if ( *(_DWORD *)(v17 + 104) == 1 )
    {
      if ( !*(_QWORD *)(*(_QWORD *)(v17 + 64) + 80LL) )
      {
        v6 = v16;
        v34 = (char *)WiaTrace_TraceLog("NULL D-AIT XP item pointer (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::FindRelatedDAITItem", v34);
        WiaTrcLib::Free((WiaTrcLib *)v34, v35);
        v29 = (void **)WiaTrace_Trace("NULL D-AIT XP item pointer (0x%X)", 2147500035LL);
        goto LABEL_28;
      }
      if ( !a3 || (v6 = CWiaItem::SetLegacyItemContext(v15), v6 >= 0) )
      {
        v18 = *(struct CWiaItem **)(*(_QWORD *)(*((_QWORD *)this + 26) + 64LL) + 80LL);
        goto LABEL_24;
      }
      v36 = (char *)WiaTrace_TraceLog("cannot change the legacy D-AIT item context (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::FindRelatedDAITItem", v36);
      WiaTrcLib::Free((WiaTrcLib *)v36, v37);
      v38 = "cannot change the legacy D-AIT item context (0x%X)";
    }
    else
    {
      v6 = -2147467259;
      *a2 = 0;
      v39 = (char *)WiaTrace_TraceLog("corrupted compatibility mode indicator (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::FindRelatedDAITItem", v39);
      WiaTrcLib::Free((WiaTrcLib *)v39, v40);
      v38 = "corrupted compatibility mode indicator (0x%X)";
    }
LABEL_27:
    v29 = (void **)WiaTrace_Trace(v38, (unsigned int)v6);
    goto LABEL_28;
  }
LABEL_29:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v48);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180062710  push    rbx
0x180062712  push    rbp
0x180062713  push    rsi
0x180062714  push    rdi
0x180062715  push    r12
0x180062717  push    r13
0x180062719  push    r14
0x18006271b  sub     rsp, 0B0h
0x180062722  mov     rsi, rcx
0x180062725  lea     r12, aCwiaitemFindre; "CWiaItem::FindRelatedDAITItem"
0x18006272c  mov     rcx, r12
0x18006272f  mov     ebp, r8d
0x180062732  mov     r14, rdx
0x180062735  xor     edi, edi
0x180062737  call    WiaTrace_Trace
0x18006273c  mov     r9, r12; char *
0x18006273f  mov     [rsp+0E8h+var_C0], rax; struct tagWiaTraceData_Type *
0x180062744  lea     rcx, [rsp+0E8h+var_88]; this
0x180062749  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18006274e  lea     r13d, [rdi+1]
0x180062752  mov     r8d, 80004003h
0x180062758  test    r14, r14
0x18006275b  jnz     short loc_1800627A6
0x18006275d  mov     edx, r8d
0x180062760  lea     rcx, aNullParameter0; "NULL parameter (0x%X)"
0x180062767  mov     edi, r8d
0x18006276a  call    WiaTrace_TraceLog
0x18006276f  mov     rdx, rax; char *
0x180062772  mov     rcx, r12; char *
0x180062775  mov     rbx, rax
0x180062778  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006277d  mov     rcx, rbx; this
0x180062780  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180062785  mov     edx, edi
0x180062787  lea     rcx, aNullParameter0; "NULL parameter (0x%X)"
0x18006278e  call    WiaTrace_Trace
0x180062793  mov     r9d, r13d; int
0x180062796  mov     [rsp+0E8h+lpMem], rax; lpMem
0x18006279b  mov     r8, r12; int
0x18006279e  call    WiaTrace_ProcessTrace_Ex
0x1800627a3  mov     r8d, edi
0x1800627a6  mov     rax, [rsi+0D0h]
0x1800627ad  cmp     qword ptr [rax+40h], 0
0x1800627b2  jz      loc_180062A04
0x1800627b8  mov     rcx, rsi; this
0x1800627bb  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x1800627c0  test    eax, eax
0x1800627c2  jz      loc_180062A04
0x1800627c8  test    edi, edi
0x1800627ca  js      loc_180062A4B
0x1800627d0  mov     rax, [rsi+0D0h]
0x1800627d7  cmp     rax, rsi
0x1800627da  jnz     short loc_1800627E5
0x1800627dc  mov     rax, [rax+40h]
0x1800627e0  jmp     loc_1800629C3
0x1800627e5  cmp     dword ptr [rax+68h], 2
0x1800627e9  jnz     loc_180062927
0x1800627ef  mov     [rsp+0E8h+var_B8], r13d
0x1800627f4  lea     r9, [rsp+0E8h+pvar]
0x1800627f9  mov     [rsp+0E8h+var_B0], 0C10h
0x180062801  lea     r8, [rsp+0E8h+var_B8]
0x180062806  xor     ecx, ecx
0x180062808  xorps   xmm0, xmm0
0x18006280b  movups  xmmword ptr [rsp+0E8h+pvar], xmm0
0x180062810  mov     [rsp+0E8h+var_98], rcx
0x180062815  mov     edx, r13d
0x180062818  mov     rax, [rax+0D8h]
0x18006281f  mov     rcx, [rax]
0x180062822  mov     rax, [rcx]
0x180062825  mov     rax, [rax+18h]
0x180062829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006282e  mov     edi, eax
0x180062830  test    eax, eax
0x180062832  js      short loc_180062848
0x180062834  mov     ebp, dword ptr [rsp+0E8h+pvar+8]
0x180062838  lea     rcx, [rsp+0E8h+pvar]; pvar
0x18006283d  call    cs:__imp_PropVariantClear
0x180062843  and     ebp, r13d
0x180062846  jmp     short loc_18006288C
0x180062848  mov     edx, edi
0x18006284a  lea     rcx, aWarningAAitRoo; "warning: A-AIT root->ReadMultiple(WIA_D"...
0x180062851  xor     ebp, ebp
0x180062853  call    WiaTrace_TraceLog
0x180062858  mov     rdx, rax; char *
0x18006285b  mov     rcx, r12; char *
0x18006285e  mov     rbx, rax
0x180062861  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180062866  mov     rcx, rbx; this
0x180062869  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006286e  mov     edx, edi
0x180062870  lea     rcx, aWarningAAitRoo; "warning: A-AIT root->ReadMultiple(WIA_D"...
0x180062877  call    WiaTrace_Trace
0x18006287c  mov     r9d, r13d; int
0x18006287f  mov     [rsp+0E8h+lpMem], rax; lpMem
0x180062884  mov     r8, r12; int
0x180062887  call    WiaTrace_ProcessTrace_Ex
0x18006288c  mov     rax, [rsi+0D0h]
0x180062893  mov     rax, [rax+40h]
0x180062897  test    ebp, ebp
0x180062899  jz      short loc_1800628E1
0x18006289b  mov     rax, [rax+58h]
0x18006289f  test    rax, rax
0x1800628a2  jnz     loc_1800629C3
0x1800628a8  mov     esi, 80004003h
0x1800628ad  lea     rcx, aNullDAitLhFeed; "NULL D-AIT LH feeder item pointer (0x%X"...
0x1800628b4  mov     edx, esi
0x1800628b6  mov     edi, esi
0x1800628b8  call    WiaTrace_TraceLog
0x1800628bd  mov     rdx, rax; char *
0x1800628c0  mov     rcx, r12; char *
0x1800628c3  mov     rbx, rax
0x1800628c6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800628cb  mov     rcx, rbx; this
0x1800628ce  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800628d3  mov     edx, esi
0x1800628d5  lea     rcx, aNullDAitLhFeed; "NULL D-AIT LH feeder item pointer (0x%X"...
0x1800628dc  jmp     loc_180062A36
0x1800628e1  mov     rax, [rax+60h]
0x1800628e5  test    rax, rax
0x1800628e8  jnz     loc_1800629C3
0x1800628ee  mov     esi, 80004003h
0x1800628f3  lea     rcx, aNullDAitLhFlat; "NULL D-AIT LH flatbed item pointer (0x%"...
0x1800628fa  mov     edx, esi
0x1800628fc  mov     edi, esi
0x1800628fe  call    WiaTrace_TraceLog
0x180062903  mov     rdx, rax; char *
0x180062906  mov     rcx, r12; char *
0x180062909  mov     rbx, rax
0x18006290c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180062911  mov     rcx, rbx; this
0x180062914  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180062919  mov     edx, esi
0x18006291b  lea     rcx, aNullDAitLhFlat; "NULL D-AIT LH flatbed item pointer (0x%"...
0x180062922  jmp     loc_180062A36
0x180062927  cmp     [rax+68h], r13d
0x18006292b  jnz     loc_1800629CB
0x180062931  mov     rax, [rax+40h]
0x180062935  cmp     qword ptr [rax+50h], 0
0x18006293a  jnz     short loc_180062975
0x18006293c  mov     edx, r8d
0x18006293f  lea     rcx, aNullDAitXpItem; "NULL D-AIT XP item pointer (0x%X)"
0x180062946  mov     edi, r8d
0x180062949  call    WiaTrace_TraceLog
0x18006294e  mov     rdx, rax; char *
0x180062951  mov     rcx, r12; char *
0x180062954  mov     rbx, rax
0x180062957  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006295c  mov     rcx, rbx; this
0x18006295f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180062964  mov     edx, 80004003h
0x180062969  lea     rcx, aNullDAitXpItem; "NULL D-AIT XP item pointer (0x%X)"
0x180062970  jmp     loc_180062A36
0x180062975  test    ebp, ebp
0x180062977  jz      short loc_1800629B4
0x180062979  call    ?SetLegacyItemContext@CWiaItem@@QEAAJXZ; CWiaItem::SetLegacyItemContext(void)
0x18006297e  mov     edi, eax
0x180062980  test    eax, eax
0x180062982  jns     short loc_1800629B4
0x180062984  mov     edx, eax
0x180062986  lea     rcx, aCannotChangeTh; "cannot change the legacy D-AIT item con"...
0x18006298d  call    WiaTrace_TraceLog
0x180062992  mov     rdx, rax; char *
0x180062995  mov     rcx, r12; char *
0x180062998  mov     rbx, rax
0x18006299b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800629a0  mov     rcx, rbx; this
0x1800629a3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800629a8  lea     rcx, aCannotChangeTh; "cannot change the legacy D-AIT item con"...
0x1800629af  jmp     loc_180062A34
0x1800629b4  mov     rax, [rsi+0D0h]
0x1800629bb  mov     rcx, [rax+40h]
0x1800629bf  mov     rax, [rcx+50h]
0x1800629c3  mov     [r14], rax
0x1800629c6  jmp     loc_180062A4B
0x1800629cb  mov     edi, 80004005h
0x1800629d0  mov     qword ptr [r14], 0
0x1800629d7  mov     edx, edi
0x1800629d9  lea     rcx, aCorruptedCompa; "corrupted compatibility mode indicator "...
0x1800629e0  call    WiaTrace_TraceLog
0x1800629e5  mov     rdx, rax; char *
0x1800629e8  mov     rcx, r12; char *
0x1800629eb  mov     rbx, rax
0x1800629ee  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800629f3  mov     rcx, rbx; this
0x1800629f6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800629fb  lea     rcx, aCorruptedCompa; "corrupted compatibility mode indicator "...
0x180062a02  jmp     short loc_180062A34
0x180062a04  mov     edi, 80004001h
0x180062a09  lea     rcx, aNotInCompatibi_2; "not in compatibility mode or called on "...
0x180062a10  mov     edx, edi
0x180062a12  call    WiaTrace_TraceLog
0x180062a17  mov     rdx, rax; char *
0x180062a1a  mov     rcx, r12; char *
0x180062a1d  mov     rbx, rax
0x180062a20  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180062a25  mov     rcx, rbx; this
0x180062a28  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180062a2d  lea     rcx, aNotInCompatibi_2; "not in compatibility mode or called on "...
0x180062a34  mov     edx, edi
0x180062a36  call    WiaTrace_Trace
0x180062a3b  mov     r9d, r13d; int
0x180062a3e  mov     [rsp+0E8h+lpMem], rax; lpMem
0x180062a43  mov     r8, r12; int
0x180062a46  call    WiaTrace_ProcessTrace_Ex
0x180062a4b  lea     rcx, [rsp+0E8h+var_88]; this
0x180062a50  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180062a55  mov     eax, edi
0x180062a57  add     rsp, 0B0h
0x180062a5e  pop     r14
0x180062a60  pop     r13
0x180062a62  pop     r12
0x180062a64  pop     rdi
0x180062a65  pop     rsi
0x180062a66  pop     rbp
0x180062a67  pop     rbx
0x180062a68  retn
```
