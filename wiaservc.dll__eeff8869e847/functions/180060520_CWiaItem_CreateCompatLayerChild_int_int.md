# CWiaItem::CreateCompatLayerChild(int,int)

- ea: `0x180060520`
- end: `0x180060aed`
- name: `?CreateCompatLayerChild@CWiaItem@@QEAAJHH@Z`
- size: `1485`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800552bc`

## callees

- `0x180004a7c`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x180013bfc`
- `0x18001750c`
- `0x180023288`
- `0x18002de18`
- `0x18002def8`
- `0x180033884`
- `0x180033cc0`
- `0x18005de14`
- `0x180060520`
- `0x180063434`
- `0x1800655b0`
- `0x1800656e0`
- `0x18006874c`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180060629`
- `OLEAUT32!__imp_SysAllocString` at `0x180060650`
- `OLEAUT32!__imp_SysAllocString` at `0x180060667`
- `OLEAUT32!__imp_SysAllocString` at `0x180060927`
- `OLEAUT32!__imp_SysAllocString` at `0x180060629`
- `OLEAUT32!__imp_SysAllocString` at `0x180060650`
- `OLEAUT32!__imp_SysAllocString` at `0x180060667`
- `OLEAUT32!__imp_SysAllocString` at `0x180060927`
- `OLEAUT32!__imp_SysFreeString` at `0x180060a92`
- `OLEAUT32!__imp_SysFreeString` at `0x180060aa0`
- `OLEAUT32!__imp_SysFreeString` at `0x180060a92`
- `OLEAUT32!__imp_SysFreeString` at `0x180060aa0`

## string_xrefs

- `0x180060554`: `CWiaItem::CreateCompatLayerChild`
- `0x18006077c`: `CWiaItem::CreateCompatLayerChild`
- `0x1800607aa`: `CWiaItem::CreateCompatLayerChild`
- `0x180060800`: `CWiaItem::CreateCompatLayerChild`
- `0x180060889`: `CWiaItem::CreateCompatLayerChild`
- `0x180060958`: `CWiaItem::CreateCompatLayerChild`
- `0x180060988`: `CWiaItem::CreateCompatLayerChild`
- `0x180060a07`: `CWiaItem::CreateCompatLayerChild`
- `0x180060a4e`: `CWiaItem::CreateCompatLayerChild`
- `0x180060a7e`: `CWiaItem::CreateCompatLayerChild`
- `0x1800607f1`: `cannot access IWiaPropertyStorage (0x%X)`
- `0x180060817`: `cannot access IWiaPropertyStorage (0x%X)`
- `0x1800606d8`: `requested child item exists already (0x%X)`
- `0x180060703`: `requested child item exists already (0x%X)`
- `0x180060949`: `InitManagedItemProperties failed (0x%X)`
- `0x180060971`: `InitManagedItemProperties failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::CreateCompatLayerChild(CWiaItem *this, int a2, int a3)
{
  char ***v6; // rax
  char *v7; // rdx
  __int64 v8; // r8
  int inited; // edi
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  unsigned int v17; // edx
  unsigned __int16 *v18; // r13
  CWiaItem **v19; // rsi
  int v20; // r12d
  BSTR v21; // r14
  __int64 v22; // rax
  char *v23; // rbx
  void *v24; // rdx
  void **v25; // rax
  void *v26; // rdx
  __int64 v27; // rcx
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  CWiaItem *v33; // rax
  CWiaItem *v34; // rax
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  struct IWiaPropertyStorage *v40; // rcx
  char *v41; // rbx
  void *v42; // rdx
  void **v43; // rax
  void *v44; // rdx
  __int64 v45; // rcx
  char *v46; // rbx
  void *v47; // rdx
  char *v48; // rbx
  void *v49; // rdx
  void **v50; // rax
  void *v51; // rdx
  __int64 v52; // rcx
  char *v53; // rbx
  void *v54; // rdx
  char *v55; // rbx
  void *v56; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  struct IWiaPropertyStorage *v59; // [rsp+40h] [rbp-C0h] BYREF
  int v60; // [rsp+48h] [rbp-B8h]
  _BYTE v61[80]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v62[38]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v63[38]; // [rsp+1D0h] [rbp+D0h] BYREF

  v60 = a2;
  v6 = (char ***)WiaTrace_Trace("CWiaItem::CreateCompatLayerChild");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v61, v7, v8, (char **)"CWiaItem::CreateCompatLayerChild", lpMem, v6);
  if ( !*((_QWORD *)this + 8) )
  {
    inited = -2147467263;
    v10 = (char *)WiaTrace_TraceLog("called on a non-A-AIT root item (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void **)WiaTrace_Trace("called on a non-A-AIT root item (0x%X)", 2147500033LL);
LABEL_5:
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"CWiaItem::CreateCompatLayerChild", 1, v12);
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    goto LABEL_16;
  }
  if ( !*((_QWORD *)this + 15) )
  {
    inited = -2147024809;
    v15 = (char *)WiaTrace_TraceLog("WIA item tree must be initialized first (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v12 = (void **)WiaTrace_Trace("WIA item tree must be initialized first (0x%X)", 2147942487LL);
    goto LABEL_5;
  }
  if ( a2 )
  {
    v21 = SysAllocString(L"Scan");
    v20 = 532483;
    v22 = 80;
  }
  else
  {
    v20 = 532483;
    if ( a3 )
    {
      v21 = SysAllocString(L"Feeder");
      v22 = 88;
    }
    else
    {
      v21 = SysAllocString(L"Flatbed");
      v22 = 96;
    }
  }
  v19 = (CWiaItem **)((char *)this + v22);
  if ( !v21 )
  {
    v23 = (char *)WiaTrace_TraceLog("Out of Memory!");
    WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v23);
    WiaTrcLib::Free((WiaTrcLib *)v23, v24);
    v25 = (void **)WiaTrace_Trace("Out of Memory!");
    WiaTrace_ProcessTrace_Ex(v27, v26, (void *)"CWiaItem::CreateCompatLayerChild", 1, v25);
    inited = -2147024882;
    v59 = 0;
LABEL_44:
    if ( *v19 )
    {
      CWiaItem::`scalar deleting destructor'(*v19, v17);
      *v19 = 0;
    }
    goto LABEL_46;
  }
  if ( !*v19 )
  {
    inited = 0;
    v18 = 0;
LABEL_16:
    v59 = 0;
    if ( inited < 0 )
      goto LABEL_39;
    v33 = (CWiaItem *)operator new(0x130u);
    if ( v33 )
    {
      v34 = CWiaItem::CWiaItem(v33);
      *v19 = v34;
      if ( v34 )
        goto LABEL_22;
    }
    else
    {
      *v19 = 0;
    }
    v35 = (char *)WiaTrace_TraceLog("Out of Memory!");
    WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v35);
    WiaTrcLib::Free((WiaTrcLib *)v35, v36);
    v37 = (void **)WiaTrace_Trace("Out of Memory!");
    WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"CWiaItem::CreateCompatLayerChild", 1, v37);
    inited = -2147024882;
LABEL_22:
    if ( *v19 )
    {
      inited = (**(__int64 (__fastcall ***)(CWiaItem *, GUID *, struct IWiaPropertyStorage **))*v19)(
                 *v19,
                 &IID_IWiaPropertyStorage,
                 &v59);
      if ( inited < 0 )
      {
LABEL_26:
        v41 = (char *)WiaTrace_TraceLog("cannot access IWiaPropertyStorage (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v41);
        WiaTrcLib::Free((WiaTrcLib *)v41, v42);
        v43 = (void **)WiaTrace_Trace("cannot access IWiaPropertyStorage (0x%X)", (unsigned int)inited);
        goto LABEL_38;
      }
      v40 = v59;
      if ( !v59 )
      {
        inited = -2147024882;
        goto LABEL_26;
      }
    }
    else
    {
      if ( inited < 0 )
        goto LABEL_39;
      v40 = v59;
    }
    inited = CWiaItem::InitializeWiaItem(
               *v19,
               1,
               v60 == 0,
               this,
               v40,
               *((struct USDWrapper **)this + 19),
               *((struct CWiaDrvItem **)this + 22),
               0);
    if ( inited >= 0 )
    {
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(
        (__int64)v63,
        *(const void **)(*((_QWORD *)this + 8) + 192LL));
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v62, L"\\");
      CSimpleStringBase<unsigned short>::Concat(v63, v62);
      v62[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v62);
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v62, v21);
      CSimpleStringBase<unsigned short>::Concat(v63, v62);
      v62[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v62);
      v18 = SysAllocString((const OLECHAR *)v63[33]);
      inited = CWiaItem::InitManagedItemProperties(*v19, v20, v21, v18);
      if ( inited < 0 )
      {
        v48 = (char *)WiaTrace_TraceLog("InitManagedItemProperties failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v48);
        WiaTrcLib::Free((WiaTrcLib *)v48, v49);
        v50 = (void **)WiaTrace_Trace("InitManagedItemProperties failed (0x%X)", inited);
        WiaTrace_ProcessTrace_Ex(v52, v51, (void *)"CWiaItem::CreateCompatLayerChild", 1, v50);
      }
      v63[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v63);
      v63[34] = 0;
      if ( inited < 0 )
      {
LABEL_39:
        if ( !v21 )
          goto LABEL_41;
        goto LABEL_40;
      }
      CWiaItem::SetAITLink(*v19, *((const struct CWiaItem **)this + 8), 1);
      CWiaItem::SetCompatMode(*v19, *((unsigned int *)this + 26));
      inited = CWiaItem::InitAAITItemTree(*v19, v20, v21, v18);
      if ( inited >= 0 )
      {
        inited = CWiaTree::AddItemToFolder(*((CWiaTree **)*v19 + 15), *((struct CWiaTree **)this + 15));
        if ( inited >= 0 )
          goto LABEL_39;
        v55 = (char *)WiaTrace_TraceLog("Call to CWiaTree::AddItemToFolder failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v55);
        WiaTrcLib::Free((WiaTrcLib *)v55, v56);
        v43 = (void **)WiaTrace_Trace("Call to CWiaTree::AddItemToFolder failed (0x%X)", (unsigned int)inited);
      }
      else
      {
        v53 = (char *)WiaTrace_TraceLog("InitAAITItemTree failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v53);
        WiaTrcLib::Free((WiaTrcLib *)v53, v54);
        v43 = (void **)WiaTrace_Trace("InitAAITItemTree failed (0x%X)", (unsigned int)inited);
      }
    }
    else
    {
      v46 = (char *)WiaTrace_TraceLog("Call to CWiaItem::Initialize failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v46);
      WiaTrcLib::Free((WiaTrcLib *)v46, v47);
      v43 = (void **)WiaTrace_Trace("Call to CWiaItem::Initialize failed (0x%X)", (unsigned int)inited);
    }
LABEL_38:
    WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"CWiaItem::CreateCompatLayerChild", 1, v43);
    goto LABEL_39;
  }
  inited = -2147024809;
  v28 = (char *)WiaTrace_TraceLog("requested child item exists already (0x%X)");
  WriteDbgTraceErrorWI("CWiaItem::CreateCompatLayerChild", v28);
  WiaTrcLib::Free((WiaTrcLib *)v28, v29);
  v30 = (void **)WiaTrace_Trace("requested child item exists already (0x%X)", -2147024809);
  WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"CWiaItem::CreateCompatLayerChild", 1, v30);
  v18 = 0;
  v59 = 0;
LABEL_40:
  SysFreeString(v21);
LABEL_41:
  if ( v18 )
    SysFreeString(v18);
  if ( inited < 0 )
    goto LABEL_44;
LABEL_46:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v61);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180060520  push    rbp
0x180060522  push    rbx
0x180060523  push    rsi
0x180060524  push    rdi
0x180060525  push    r12
0x180060527  push    r13
0x180060529  push    r14
0x18006052b  push    r15
0x18006052d  lea     rbp, [rsp-218h]
0x180060535  sub     rsp, 318h
0x18006053c  mov     rax, cs:__security_cookie
0x180060543  xor     rax, rsp
0x180060546  mov     [rbp+250h+var_50], rax
0x18006054d  mov     r15, rcx
0x180060550  mov     [rsp+350h+var_308], edx
0x180060554  lea     r13, aCwiaitemCreate_0; "CWiaItem::CreateCompatLayerChild"
0x18006055b  mov     ebx, r8d
0x18006055e  mov     rcx, r13
0x180060561  mov     edi, edx
0x180060563  call    WiaTrace_Trace
0x180060568  mov     r9, r13; char *
0x18006056b  mov     [rsp+350h+var_328], rax; struct tagWiaTraceData_Type *
0x180060570  lea     rcx, [rsp+350h+var_300]; this
0x180060575  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18006057a  cmp     qword ptr [r15+40h], 0
0x18006057f  mov     esi, 1
0x180060584  jnz     short loc_1800605BA
0x180060586  mov     edi, 80004001h
0x18006058b  lea     rcx, aCalledOnANonAA; "called on a non-A-AIT root item (0x%X)"
0x180060592  mov     edx, edi
0x180060594  call    WiaTrace_TraceLog
0x180060599  mov     rdx, rax; char *
0x18006059c  mov     rcx, r13; char *
0x18006059f  mov     rbx, rax
0x1800605a2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800605a7  mov     rcx, rbx; this
0x1800605aa  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800605af  mov     edx, edi
0x1800605b1  lea     rcx, aCalledOnANonAA; "called on a non-A-AIT root item (0x%X)"
0x1800605b8  jmp     short loc_1800605F9
0x1800605ba  cmp     qword ptr [r15+78h], 0
0x1800605bf  jnz     short loc_18006061E
0x1800605c1  mov     r12d, 80070057h
0x1800605c7  lea     rcx, aWiaItemTreeMus; "WIA item tree must be initialized first"...
0x1800605ce  mov     edx, r12d
0x1800605d1  mov     edi, r12d
0x1800605d4  call    WiaTrace_TraceLog
0x1800605d9  mov     rdx, rax; char *
0x1800605dc  mov     rcx, r13; char *
0x1800605df  mov     rbx, rax
0x1800605e2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800605e7  mov     rcx, rbx; this
0x1800605ea  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800605ef  mov     edx, r12d
0x1800605f2  lea     rcx, aWiaItemTreeMus; "WIA item tree must be initialized first"...
0x1800605f9  call    WiaTrace_Trace
0x1800605fe  mov     r9d, esi; int
0x180060601  mov     [rsp+350h+lpMem], rax; lpMem
0x180060606  mov     r8, r13; int
0x180060609  call    WiaTrace_ProcessTrace_Ex
0x18006060e  xor     r13d, r13d
0x180060611  xor     esi, esi
0x180060613  xor     r12d, r12d
0x180060616  xor     r14d, r14d
0x180060619  jmp     loc_180060734
0x18006061e  test    edi, edi
0x180060620  jz      short loc_18006063F
0x180060622  lea     rcx, aScan; "Scan"
0x180060629  call    cs:__imp_SysAllocString
0x18006062f  mov     r14, rax
0x180060632  mov     r12d, 82003h
0x180060638  mov     eax, 50h ; 'P'
0x18006063d  jmp     short loc_180060675
0x18006063f  mov     r12d, 82003h
0x180060645  test    ebx, ebx
0x180060647  jz      short loc_180060660
0x180060649  lea     rcx, aFeeder; "Feeder"
0x180060650  call    cs:__imp_SysAllocString
0x180060656  mov     r14, rax
0x180060659  mov     eax, 58h ; 'X'
0x18006065e  jmp     short loc_180060675
0x180060660  lea     rcx, aFlatbed; "Flatbed"
0x180060667  call    cs:__imp_SysAllocString
0x18006066d  mov     r14, rax
0x180060670  mov     eax, 60h ; '`'
0x180060675  lea     rsi, [rax+r15]
0x180060679  test    r14, r14
0x18006067c  jnz     short loc_1800606CC
0x18006067e  lea     rcx, aOutOfMemory_2; "Out of Memory!"
0x180060685  call    WiaTrace_TraceLog
0x18006068a  mov     rdx, rax; char *
0x18006068d  mov     rcx, r13; char *
0x180060690  mov     rbx, rax
0x180060693  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180060698  mov     rcx, rbx; this
0x18006069b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800606a0  lea     rcx, aOutOfMemory_2; "Out of Memory!"
0x1800606a7  call    WiaTrace_Trace
0x1800606ac  lea     r9d, [r14+1]; int
0x1800606b0  mov     [rsp+350h+lpMem], rax; lpMem
0x1800606b5  mov     r8, r13; int
0x1800606b8  call    WiaTrace_ProcessTrace_Ex
0x1800606bd  mov     edi, 8007000Eh
0x1800606c2  mov     [rsp+350h+var_310], r14
0x1800606c7  jmp     loc_180060AAA
0x1800606cc  cmp     qword ptr [rsi], 0
0x1800606d0  jz      short loc_18006072F
0x1800606d2  mov     r12d, 80070057h
0x1800606d8  lea     rcx, aRequestedChild; "requested child item exists already (0x"...
0x1800606df  mov     edx, r12d
0x1800606e2  mov     edi, r12d
0x1800606e5  call    WiaTrace_TraceLog
0x1800606ea  mov     rdx, rax; char *
0x1800606ed  mov     rcx, r13; char *
0x1800606f0  mov     rbx, rax
0x1800606f3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800606f8  mov     rcx, rbx; this
0x1800606fb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180060700  mov     edx, r12d
0x180060703  lea     rcx, aRequestedChild; "requested child item exists already (0x"...
0x18006070a  call    WiaTrace_Trace
0x18006070f  mov     r9d, 1; int
0x180060715  mov     [rsp+350h+lpMem], rax; lpMem
0x18006071a  mov     r8, r13; int
0x18006071d  call    WiaTrace_ProcessTrace_Ex
0x180060722  xor     r13d, r13d
0x180060725  mov     [rsp+350h+var_310], r13
0x18006072a  jmp     loc_180060A8F
0x18006072f  xor     edi, edi
0x180060731  xor     r13d, r13d
0x180060734  mov     [rsp+350h+var_310], 0
0x18006073d  test    edi, edi
0x18006073f  js      loc_180060A8A
0x180060745  mov     ecx, 130h; Size
0x18006074a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006074f  test    rax, rax
0x180060752  jz      short loc_180060766
0x180060754  mov     rcx, rax; this
0x180060757  call    ??0CWiaItem@@QEAA@XZ; CWiaItem::CWiaItem(void)
0x18006075c  mov     [rsi], rax
0x18006075f  test    rax, rax
0x180060762  jnz     short loc_1800607BB
0x180060764  jmp     short loc_18006076D
0x180060766  mov     qword ptr [rsi], 0
0x18006076d  lea     rcx, aOutOfMemory_2; "Out of Memory!"
0x180060774  call    WiaTrace_TraceLog
0x180060779  mov     rdx, rax; char *
0x18006077c  lea     rcx, aCwiaitemCreate_0; "CWiaItem::CreateCompatLayerChild"
0x180060783  mov     rbx, rax
0x180060786  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006078b  mov     rcx, rbx; this
0x18006078e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180060793  lea     rcx, aOutOfMemory_2; "Out of Memory!"
0x18006079a  call    WiaTrace_Trace
0x18006079f  mov     r9d, 1; int
0x1800607a5  mov     [rsp+350h+lpMem], rax; lpMem
0x1800607aa  lea     r8, aCwiaitemCreate_0; "CWiaItem::CreateCompatLayerChild"
0x1800607b1  call    WiaTrace_ProcessTrace_Ex
0x1800607b6  mov     edi, 8007000Eh
0x1800607bb  mov     rcx, [rsi]
0x1800607be  test    rcx, rcx
0x1800607c1  jz      short loc_180060823
0x1800607c3  mov     rax, [rcx]
0x1800607c6  lea     r8, [rsp+350h+var_310]
0x1800607cb  lea     rdx, IID_IWiaPropertyStorage
0x1800607d2  mov     rax, [rax]
0x1800607d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607da  mov     edi, eax
0x1800607dc  test    eax, eax
0x1800607de  js      short loc_1800607EF
0x1800607e0  mov     rcx, [rsp+350h+var_310]
0x1800607e5  test    rcx, rcx
0x1800607e8  jnz     short loc_180060830
0x1800607ea  mov     edi, 8007000Eh
0x1800607ef  mov     edx, edi
0x1800607f1  lea     rcx, aCannotAccessIw; "cannot access IWiaPropertyStorage (0x%X"...
0x1800607f8  call    WiaTrace_TraceLog
0x1800607fd  mov     rdx, rax; char *
0x180060800  lea     rcx, aCwiaitemCreate_0; "CWiaItem::CreateCompatLayerChild"
0x180060807  mov     rbx, rax
0x18006080a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006080f  mov     rcx, rbx; this
0x180060812  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180060817  lea     rcx, aCannotAccessIw; "cannot access IWiaPropertyStorage (0x%X"...
0x18006081e  jmp     loc_180060A6C
0x180060823  test    edi, edi
0x180060825  js      loc_180060A8A
0x18006082b  mov     rcx, [rsp+350h+var_310]
0x180060830  mov     rax, [r15+0B0h]
0x180060837  xor     r8d, r8d
0x18006083a  cmp     [rsp+350h+var_308], r8d
0x18006083f  mov     r9, r15; struct CWiaItem *
0x180060842  mov     [rsp+350h+var_318], 0; struct IUnknown *
0x18006084b  mov     edx, 1; int
0x180060850  mov     [rsp+350h+var_320], rax; struct CWiaDrvItem *
0x180060855  setz    r8b; int
0x180060859  mov     rax, [r15+98h]
0x180060860  mov     [rsp+350h+var_328], rax; struct USDWrapper *
0x180060865  mov     [rsp+350h+lpMem], rcx; struct IWiaPropertyStorage *
0x18006086a  mov     rcx, [rsi]; this
0x18006086d  call    ?InitializeWiaItem@CWiaItem@@QEAAJHHPEAV1@PEAUIWiaPropertyStorage@@PEAVUSDWrapper@@PEAVCWiaDrvItem@@PEAUIUnknown@@@Z; CWiaItem::InitializeWiaItem(int,int,CWiaItem *,IWiaPropertyStorage *,USDWrapper *,CWiaDrvItem *,IUnknown *)
0x180060872  mov     edi, eax
0x180060874  test    eax, eax
0x180060876  jns     short loc_1800608AC
0x180060878  mov     edx, eax
0x18006087a  lea     rcx, aCallToCwiaitem_0; "Call to CWiaItem::Initialize failed (0x"...
0x180060881  call    WiaTrace_TraceLog
0x180060886  mov     rdx, rax; char *
0x180060889  lea     rcx, aCwiaitemCreate_0; "CWiaItem::CreateCompatLayerChild"
0x180060890  mov     rbx, rax
0x180060893  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180060898  mov     rcx, rbx; this
0x18006089b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800608a0  lea     rcx, aCallToCwiaitem_0; "Call to CWiaItem::Initialize failed (0x"...
0x1800608a7  jmp     loc_180060A6C
0x1800608ac  mov     rdx, [r15+40h]
0x1800608b0  lea     rcx, [rbp+250h+var_180]
0x1800608b7  mov     rdx, [rdx+0C0h]
0x1800608be  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800608c3  lea     rdx, SubBlock; "\\"
0x1800608ca  lea     rcx, [rbp+250h+var_2B0]
0x1800608ce  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800608d3  lea     rdx, [rbp+250h+var_2B0]
0x1800608d7  lea     rcx, [rbp+250h+var_180]
0x1800608de  call    ?Concat@?$CSimpleStringBase@G@@QEAAXAEBV1@@Z; CSimpleStringBase<ushort>::Concat(CSimpleStringBase<ushort> const &)
0x1800608e3  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800608ea  lea     rcx, [rbp+250h+var_2B0]
0x1800608ee  mov     [rbp+250h+var_2B0], rbx
0x1800608f2  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800608f7  mov     rdx, r14
0x1800608fa  lea     rcx, [rbp+250h+var_2B0]
0x1800608fe  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180060903  lea     rdx, [rbp+250h+var_2B0]
0x180060907  lea     rcx, [rbp+250h+var_180]
0x18006090e  call    ?Concat@?$CSimpleStringBase@G@@QEAAXAEBV1@@Z; CSimpleStringBase<ushort>::Concat(CSimpleStringBase<ushort> const &)
0x180060913  lea     rcx, [rbp+250h+var_2B0]
0x180060917  mov     [rbp+250h+var_2B0], rbx
0x18006091b  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180060920  mov     rcx, [rbp+250h+psz]; psz
0x180060927  call    cs:__imp_SysAllocString
0x18006092d  mov     rcx, [rsi]; this
0x180060930  mov     r8, r14; unsigned __int16 *
0x180060933  mov     r9, rax; unsigned __int16 *
0x180060936  mov     edx, r12d; int
0x180060939  mov     r13, rax
0x18006093c  call    ?InitManagedItemProperties@CWiaItem@@QEAAJJPEAG0@Z; CWiaItem::InitManagedItemProperties(long,ushort *,ushort *)
0x180060941  mov     edi, eax
0x180060943  test    eax, eax
0x180060945  jns     short loc_18006099B
0x180060947  mov     edx, eax
0x180060949  lea     rcx, aInitmanagedite_0; "InitManagedItemProperties failed (0x%X)"
0x180060950  call    WiaTrace_TraceLog
0x180060955  mov     rdx, rax; char *
0x180060958  lea     rcx, aCwiaitemCreate_0; "CWiaItem::CreateCompatLayerChild"
0x18006095f  mov     rbx, rax
0x180060962  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180060967  mov     rcx, rbx; this
0x18006096a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006096f  mov     edx, edi
0x180060971  lea     rcx, aInitmanagedite_0; "InitManagedItemProperties failed (0x%X)"
0x180060978  call    WiaTrace_Trace
0x18006097d  mov     r9d, 1; int
0x180060983  mov     [rsp+350h+lpMem], rax; lpMem
0x180060988  lea     r8, aCwiaitemCreate_0; "CWiaItem::CreateCompatLayerChild"
0x18006098f  call    WiaTrace_ProcessTrace_Ex
0x180060994  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18006099b  lea     rcx, [rbp+250h+var_180]
0x1800609a2  mov     [rbp+250h+var_180], rbx
0x1800609a9  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800609ae  mov     [rbp+250h+var_70], 0
0x1800609b9  test    edi, edi
0x1800609bb  js      loc_180060A8A
0x1800609c1  mov     rdx, [r15+40h]; struct CWiaItem *
0x1800609c5  mov     r8d, 1; int
0x1800609cb  mov     rcx, [rsi]; this
0x1800609ce  call    ?SetAITLink@CWiaItem@@QEAAJPEBV1@H@Z; CWiaItem::SetAITLink(CWiaItem const *,int)
0x1800609d3  mov     edx, [r15+68h]
0x1800609d7  mov     rcx, [rsi]
0x1800609da  call    ?SetCompatMode@CWiaItem@@QEAAJW4WIA_COMPAT_MODE@@@Z; CWiaItem::SetCompatMode(WIA_COMPAT_MODE)
0x1800609df  mov     rcx, [rsi]; this
0x1800609e2  mov     r9, r13; unsigned __int16 *
0x1800609e5  mov     r8, r14; unsigned __int16 *
0x1800609e8  mov     edx, r12d; int
0x1800609eb  call    ?InitAAITItemTree@CWiaItem@@QEAAJJPEAG0@Z; CWiaItem::InitAAITItemTree(long,ushort *,ushort *)
0x1800609f0  mov     edi, eax
0x1800609f2  test    eax, eax
0x1800609f4  jns     short loc_180060A27
0x1800609f6  mov     edx, eax
0x1800609f8  lea     rcx, aInitaaititemtr_0; "InitAAITItemTree failed (0x%X)"
0x1800609ff  call    WiaTrace_TraceLog
0x180060a04  mov     rdx, rax; char *
0x180060a07  lea     rcx, aCwiaitemCreate_0; "CWiaItem::CreateCompatLayerChild"
0x180060a0e  mov     rbx, rax
0x180060a11  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180060a16  mov     rcx, rbx; this
0x180060a19  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180060a1e  lea     rcx, aInitaaititemtr_0; "InitAAITItemTree failed (0x%X)"
0x180060a25  jmp     short loc_180060A6C
0x180060a27  mov     rcx, [rsi]
0x180060a2a  mov     rdx, [r15+78h]; struct CWiaTree *
  ... truncated ...
```
