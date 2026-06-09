# CWiaItem::DetectCompatLHChildren(int *,int *)

- ea: `0x180032764`
- end: `0x180032b3a`
- name: `?DetectCompatLHChildren@CWiaItem@@QEAAJPEAH0@Z`
- size: `982`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, int *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800552bc`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x180032764`
- `0x180061cb4`
- `0x1800775fc`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x180032982`
- `ole32!PropVariantClear` at `0x180032982`

## string_xrefs

- `0x180032780`: `CWiaItem::DetectCompatLHChildren`
- `0x18003288a`: `CWiaItem::DetectCompatLHChildren`
- `0x1800328b7`: `CWiaItem::DetectCompatLHChildren`
- `0x1800329e9`: `CWiaItem::DetectCompatLHChildren`
- `0x180032a19`: `CWiaItem::DetectCompatLHChildren`
- `0x180032a66`: `CWiaItem::DetectCompatLHChildren`
- `0x180032a96`: `CWiaItem::DetectCompatLHChildren`
- `0x1800329da`: `ReadMultiple(WIA_IPA_CATEGORY) failed (0x%X)`
- `0x180032a02`: `ReadMultiple(WIA_IPA_CATEGORY) failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::DetectCompatLHChildren(CWiaItem *this, int *a2, int *a3)
{
  struct tagWiaTraceData_Type *v6; // rax
  char *v7; // rdx
  unsigned int v8; // r8d
  __int64 v9; // rbx
  int v10; // edi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  int v16; // r14d
  __int64 *v17; // r8
  GUID *v18; // rdx
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r13
  __int64 v25; // rcx
  __int64 *v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  char *v30; // rbx
  void *v31; // rdx
  void **v32; // rax
  void *v33; // rdx
  __int64 v34; // rcx
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-99h]
  __int64 v42; // [rsp+30h] [rbp-89h] BYREF
  __int64 v43; // [rsp+38h] [rbp-81h] BYREF
  __int64 v44; // [rsp+40h] [rbp-79h]
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-71h] BYREF
  __int64 v46; // [rsp+58h] [rbp-61h]
  _DWORD v47[4]; // [rsp+60h] [rbp-59h] BYREF
  __int128 Buf1; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v49[144]; // [rsp+80h] [rbp-39h] BYREF
  int v50; // [rsp+120h] [rbp+67h] BYREF
  __int64 v51; // [rsp+128h] [rbp+6Fh] BYREF
  struct IUnknown *v52; // [rsp+130h] [rbp+77h] BYREF
  __int64 v53; // [rsp+138h] [rbp+7Fh] BYREF

  v6 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::DetectCompatLHChildren");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v49, v7, v8, "CWiaItem::DetectCompatLHChildren", lpMem, v6);
  v9 = 0;
  if ( a2 && a3 )
  {
    v10 = 0;
    *((_QWORD *)this + 10) = 0;
  }
  else
  {
    v10 = -2147467261;
    v11 = (char *)WiaTrace_TraceLog("NULL pointer parameter (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::DetectCompatLHChildren", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void **)WiaTrace_Trace("NULL pointer parameter (0x%X)", -2147467261);
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CWiaItem::DetectCompatLHChildren", 1, v13);
    v9 = 0;
  }
  v16 = *((_DWORD *)this + 56);
  *a3 = 0;
  *a2 = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  v52 = 0;
  v42 = 0;
  v53 = 0;
  if ( v10 >= 0 )
  {
    v10 = CWiaItem::EnumChildren(this, &v52, 0);
    if ( v10 < 0 )
    {
      v19 = (char *)WiaTrace_TraceLog("unable to get IEnumWiaItemX interface (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::DetectCompatLHChildren", v19);
      WiaTrcLib::Free((WiaTrcLib *)v19, v20);
      v21 = (void **)WiaTrace_Trace("unable to get IEnumWiaItemX interface (0x%X)", v10);
      WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"CWiaItem::DetectCompatLHChildren", 1, v21);
      v9 = 0;
    }
    else
    {
      if ( v16 == 2 )
      {
        v17 = &v53;
        v18 = &IID_IEnumWiaItem2;
      }
      else
      {
        v17 = &v42;
        v18 = &IID_IEnumWiaItem;
      }
      v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v52->lpVtbl->QueryInterface)(v52, v18, v17);
    }
  }
  v24 = 0;
  v44 = 0;
  while ( !v10 )
  {
    v43 = 0;
    v51 = 0;
    v50 = 0;
    if ( v16 == 2 )
    {
      v25 = v53;
      v26 = &v51;
    }
    else
    {
      v25 = v42;
      v26 = &v43;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v25 + 24LL))(v25, 1, v26, &v50);
    if ( v10 )
    {
      if ( v10 == 1 )
      {
        v10 = 0;
        break;
      }
      v35 = (char *)WiaTrace_TraceLog("Call to IEnumWiaItem::Next failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::DetectCompatLHChildren", v35);
      WiaTrcLib::Free((WiaTrcLib *)v35, v36);
      v37 = (void **)WiaTrace_Trace("Call to IEnumWiaItem::Next failed (0x%X)", v10);
      WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"CWiaItem::DetectCompatLHChildren", 1, v37);
      v9 = 0;
    }
    else
    {
      v27 = v51;
      if ( v16 == 2 )
      {
        if ( v51 )
          v9 = v51 - 56;
      }
      else
      {
        v9 = v43;
      }
      if ( v9 )
      {
        v47[2] = 4125;
        v46 = 0;
        v28 = *(_QWORD *)(v9 + 8);
        *(_OWORD *)pvar = 0;
        v47[0] = 1;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *, PROPVARIANT *))(v28 + 24))(v9 + 8, 1, v47, pvar);
        if ( v10 )
        {
          v30 = (char *)WiaTrace_TraceLog("ReadMultiple(WIA_IPA_CATEGORY) failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::DetectCompatLHChildren", v30);
          WiaTrcLib::Free((WiaTrcLib *)v30, v31);
          v32 = (void **)WiaTrace_Trace("ReadMultiple(WIA_IPA_CATEGORY) failed (0x%X)", v10);
          WiaTrace_ProcessTrace_Ex(v34, v33, (void *)"CWiaItem::DetectCompatLHChildren", 1, v32);
          goto LABEL_29;
        }
        Buf1 = *(_OWORD *)pvar[1];
        PropVariantClear(pvar);
        if ( !memcmp_0(&Buf1, &WIA_CATEGORY_FLATBED, 0x10u) )
        {
          *a2 = 1;
          v24 = v9;
LABEL_29:
          v27 = v51;
          goto LABEL_30;
        }
        v29 = memcmp_0(&Buf1, &WIA_CATEGORY_FEEDER, 0x10u);
        v27 = v51;
        if ( !v29 )
        {
          *a3 = 1;
          v44 = v9;
        }
      }
LABEL_30:
      if ( v16 != 2 )
        v27 = v43;
      v9 = 0;
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
  }
  if ( v16 == 2 )
  {
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
  }
  else if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v52 )
  {
    ((void (__fastcall *)(struct IUnknown *))v52->lpVtbl->Release)(v52);
    v52 = 0;
  }
  if ( v10 >= 0 )
  {
    if ( *a3 )
      *((_QWORD *)this + 11) = v44;
    if ( *a2 )
      *((_QWORD *)this + 12) = v24;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v49);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180032764  push    rbp
0x180032766  push    rbx
0x180032767  push    rsi
0x180032768  push    rdi
0x180032769  push    r12
0x18003276b  push    r13
0x18003276d  push    r14
0x18003276f  push    r15
0x180032771  lea     rbp, [rsp-1Fh]
0x180032776  sub     rsp, 0D8h
0x18003277d  mov     rsi, rcx
0x180032780  lea     r14, aCwiaitemDetect; "CWiaItem::DetectCompatLHChildren"
0x180032787  mov     rcx, r14
0x18003278a  mov     r15, r8
0x18003278d  mov     r12, rdx
0x180032790  call    WiaTrace_Trace
0x180032795  mov     r9, r14; char *
0x180032798  mov     [rsp+110h+var_E8], rax; struct tagWiaTraceData_Type *
0x18003279d  lea     rcx, [rbp+57h+var_90]; this
0x1800327a1  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800327a6  xor     ebx, ebx
0x1800327a8  lea     r13d, [rbx+1]
0x1800327ac  test    r12, r12
0x1800327af  jz      short loc_1800327BE
0x1800327b1  test    r15, r15
0x1800327b4  jz      short loc_1800327BE
0x1800327b6  mov     edi, ebx
0x1800327b8  mov     [rsi+50h], rbx
0x1800327bc  jmp     short loc_180032807
0x1800327be  mov     edi, 80004003h
0x1800327c3  lea     rcx, aNullPointerPar; "NULL pointer parameter (0x%X)"
0x1800327ca  mov     edx, edi
0x1800327cc  call    WiaTrace_TraceLog
0x1800327d1  mov     rdx, rax; char *
0x1800327d4  mov     rcx, r14; char *
0x1800327d7  mov     rbx, rax
0x1800327da  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800327df  mov     rcx, rbx; this
0x1800327e2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800327e7  mov     edx, edi
0x1800327e9  lea     rcx, aNullPointerPar; "NULL pointer parameter (0x%X)"
0x1800327f0  call    WiaTrace_Trace
0x1800327f5  mov     r9d, r13d; int
0x1800327f8  mov     [rsp+110h+lpMem], rax; lpMem
0x1800327fd  mov     r8, r14; int
0x180032800  call    WiaTrace_ProcessTrace_Ex
0x180032805  xor     ebx, ebx
0x180032807  mov     r14d, [rsi+0E0h]
0x18003280e  mov     [r15], ebx
0x180032811  mov     [r12], ebx
0x180032815  mov     [rsi+58h], rbx
0x180032819  mov     [rsi+60h], rbx
0x18003281d  mov     [rbp+57h+arg_10], rbx
0x180032821  mov     [rsp+110h+var_E0], rbx
0x180032826  mov     [rbp+57h+arg_18], rbx
0x18003282a  test    edi, edi
0x18003282c  js      loc_1800328C5
0x180032832  xor     r8d, r8d; struct _GUID *
0x180032835  lea     rdx, [rbp+57h+arg_10]; struct IUnknown **
0x180032839  mov     rcx, rsi; this
0x18003283c  call    ?EnumChildren@CWiaItem@@AEAAJPEAPEAUIUnknown@@PEBU_GUID@@@Z; CWiaItem::EnumChildren(IUnknown * *,_GUID const *)
0x180032841  mov     edi, eax
0x180032843  test    eax, eax
0x180032845  js      short loc_180032879
0x180032847  mov     rcx, [rbp+57h+arg_10]
0x18003284b  mov     rax, [rcx]
0x18003284e  mov     rax, [rax]
0x180032851  cmp     r14d, 2
0x180032855  jnz     short loc_180032864
0x180032857  lea     r8, [rbp+57h+arg_18]
0x18003285b  lea     rdx, IID_IEnumWiaItem2
0x180032862  jmp     short loc_180032870
0x180032864  lea     r8, [rsp+110h+var_E0]
0x180032869  lea     rdx, IID_IEnumWiaItem
0x180032870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032875  mov     edi, eax
0x180032877  jmp     short loc_1800328C5
0x180032879  mov     edx, edi
0x18003287b  lea     rcx, aUnableToGetIen; "unable to get IEnumWiaItemX interface ("...
0x180032882  call    WiaTrace_TraceLog
0x180032887  mov     rdx, rax; char *
0x18003288a  lea     rcx, aCwiaitemDetect; "CWiaItem::DetectCompatLHChildren"
0x180032891  mov     rbx, rax
0x180032894  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180032899  mov     rcx, rbx; this
0x18003289c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800328a1  mov     edx, edi
0x1800328a3  lea     rcx, aUnableToGetIen; "unable to get IEnumWiaItemX interface ("...
0x1800328aa  call    WiaTrace_Trace
0x1800328af  mov     r9d, r13d; int
0x1800328b2  mov     [rsp+110h+lpMem], rax; lpMem
0x1800328b7  lea     r8, aCwiaitemDetect; "CWiaItem::DetectCompatLHChildren"
0x1800328be  call    WiaTrace_ProcessTrace_Ex
0x1800328c3  xor     ebx, ebx
0x1800328c5  mov     r13, rbx
0x1800328c8  mov     [rbp+57h+var_D0], rbx
0x1800328cc  test    edi, edi
0x1800328ce  jnz     loc_180032AAB
0x1800328d4  mov     [rsp+110h+var_D8], rbx
0x1800328d9  lea     r9, [rbp+57h+arg_0]
0x1800328dd  mov     [rbp+57h+arg_8], rbx
0x1800328e1  lea     edx, [rdi+1]
0x1800328e4  mov     [rbp+57h+arg_0], ebx
0x1800328e7  cmp     r14d, 2
0x1800328eb  jnz     short loc_1800328F7
0x1800328ed  mov     rcx, [rbp+57h+arg_18]
0x1800328f1  lea     r8, [rbp+57h+arg_8]
0x1800328f5  jmp     short loc_180032901
0x1800328f7  mov     rcx, [rsp+110h+var_E0]
0x1800328fc  lea     r8, [rsp+110h+var_D8]
0x180032901  mov     rax, [rcx]
0x180032904  mov     rax, [rax+18h]
0x180032908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003290d  mov     edi, eax
0x18003290f  test    eax, eax
0x180032911  jnz     loc_180032A50
0x180032917  mov     rcx, [rbp+57h+arg_8]
0x18003291b  cmp     r14d, 2
0x18003291f  jnz     short loc_18003292C
0x180032921  test    rcx, rcx
0x180032924  jz      short loc_180032931
0x180032926  lea     rbx, [rcx-38h]
0x18003292a  jmp     short loc_180032931
0x18003292c  mov     rbx, [rsp+110h+var_D8]
0x180032931  test    rbx, rbx
0x180032934  jz      loc_180032A29
0x18003293a  xor     eax, eax
0x18003293c  mov     [rbp+57h+var_A8], 101Dh
0x180032943  mov     [rbp+57h+var_B8], rax
0x180032947  lea     rcx, [rbx+8]
0x18003294b  xorps   xmm0, xmm0
0x18003294e  lea     r9, [rbp+57h+pvar]
0x180032952  lea     r8, [rbp+57h+var_B0]
0x180032956  lea     edx, [rax+1]
0x180032959  mov     rax, [rcx]
0x18003295c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180032960  mov     [rbp+57h+var_B0], edx
0x180032963  mov     rax, [rax+18h]
0x180032967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003296c  mov     edi, eax
0x18003296e  test    eax, eax
0x180032970  jnz     short loc_1800329D8
0x180032972  mov     rax, [rbp+57h+pvar+8]
0x180032976  lea     rcx, [rbp+57h+pvar]; pvar
0x18003297a  movups  xmm0, xmmword ptr [rax]
0x18003297d  movdqu  [rbp+57h+Buf1], xmm0
0x180032982  call    cs:__imp_PropVariantClear
0x180032988  lea     r8d, [rdi+10h]; Size
0x18003298c  lea     rdx, WIA_CATEGORY_FLATBED; Buf2
0x180032993  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180032997  call    memcmp_0
0x18003299c  test    eax, eax
0x18003299e  jnz     short loc_1800329AD
0x1800329a0  mov     dword ptr [r12], 1
0x1800329a8  mov     r13, rbx
0x1800329ab  jmp     short loc_180032A25
0x1800329ad  mov     r8d, 10h; Size
0x1800329b3  lea     rdx, WIA_CATEGORY_FEEDER; Buf2
0x1800329ba  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800329be  call    memcmp_0
0x1800329c3  mov     rcx, [rbp+57h+arg_8]
0x1800329c7  test    eax, eax
0x1800329c9  jnz     short loc_180032A29
0x1800329cb  mov     dword ptr [r15], 1
0x1800329d2  mov     [rbp+57h+var_D0], rbx
0x1800329d6  jmp     short loc_180032A29
0x1800329d8  mov     edx, edi
0x1800329da  lea     rcx, aReadmultipleWi; "ReadMultiple(WIA_IPA_CATEGORY) failed ("...
0x1800329e1  call    WiaTrace_TraceLog
0x1800329e6  mov     rdx, rax; char *
0x1800329e9  lea     rcx, aCwiaitemDetect; "CWiaItem::DetectCompatLHChildren"
0x1800329f0  mov     rbx, rax
0x1800329f3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800329f8  mov     rcx, rbx; this
0x1800329fb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180032a00  mov     edx, edi
0x180032a02  lea     rcx, aReadmultipleWi; "ReadMultiple(WIA_IPA_CATEGORY) failed ("...
0x180032a09  call    WiaTrace_Trace
0x180032a0e  mov     r9d, 1; int
0x180032a14  mov     [rsp+110h+lpMem], rax; lpMem
0x180032a19  lea     r8, aCwiaitemDetect; "CWiaItem::DetectCompatLHChildren"
0x180032a20  call    WiaTrace_ProcessTrace_Ex
0x180032a25  mov     rcx, [rbp+57h+arg_8]
0x180032a29  cmp     r14d, 2
0x180032a2d  jz      short loc_180032A34
0x180032a2f  mov     rcx, [rsp+110h+var_D8]
0x180032a34  xor     ebx, ebx
0x180032a36  test    rcx, rcx
0x180032a39  jz      loc_1800328CC
0x180032a3f  mov     rax, [rcx]
0x180032a42  mov     rax, [rax+10h]
0x180032a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a4b  jmp     loc_1800328CC
0x180032a50  cmp     edi, 1
0x180032a53  jz      short loc_180032AA9
0x180032a55  mov     edx, edi
0x180032a57  lea     rcx, aCallToIenumwia; "Call to IEnumWiaItem::Next failed (0x%X"...
0x180032a5e  call    WiaTrace_TraceLog
0x180032a63  mov     rdx, rax; char *
0x180032a66  lea     rcx, aCwiaitemDetect; "CWiaItem::DetectCompatLHChildren"
0x180032a6d  mov     rbx, rax
0x180032a70  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180032a75  mov     rcx, rbx; this
0x180032a78  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180032a7d  mov     edx, edi
0x180032a7f  lea     rcx, aCallToIenumwia; "Call to IEnumWiaItem::Next failed (0x%X"...
0x180032a86  call    WiaTrace_Trace
0x180032a8b  mov     r9d, 1; int
0x180032a91  mov     [rsp+110h+lpMem], rax; lpMem
0x180032a96  lea     r8, aCwiaitemDetect; "CWiaItem::DetectCompatLHChildren"
0x180032a9d  call    WiaTrace_ProcessTrace_Ex
0x180032aa2  xor     ebx, ebx
0x180032aa4  jmp     loc_1800328CC
0x180032aa9  mov     edi, ebx
0x180032aab  cmp     r14d, 2
0x180032aaf  jnz     short loc_180032ACC
0x180032ab1  mov     rcx, [rbp+57h+arg_18]
0x180032ab5  test    rcx, rcx
0x180032ab8  jz      short loc_180032AE7
0x180032aba  mov     rax, [rcx]
0x180032abd  mov     rax, [rax+10h]
0x180032ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ac6  mov     [rbp+57h+arg_18], rbx
0x180032aca  jmp     short loc_180032AE7
0x180032acc  mov     rcx, [rsp+110h+var_E0]
0x180032ad1  test    rcx, rcx
0x180032ad4  jz      short loc_180032AE7
0x180032ad6  mov     rax, [rcx]
0x180032ad9  mov     rax, [rax+10h]
0x180032add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ae2  mov     [rsp+110h+var_E0], rbx
0x180032ae7  mov     rcx, [rbp+57h+arg_10]
0x180032aeb  test    rcx, rcx
0x180032aee  jz      short loc_180032B00
0x180032af0  mov     rax, [rcx]
0x180032af3  mov     rax, [rax+10h]
0x180032af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032afc  mov     [rbp+57h+arg_10], rbx
0x180032b00  test    edi, edi
0x180032b02  js      short loc_180032B1B
0x180032b04  cmp     [r15], ebx
0x180032b07  jz      short loc_180032B11
0x180032b09  mov     rax, [rbp+57h+var_D0]
0x180032b0d  mov     [rsi+58h], rax
0x180032b11  cmp     [r12], ebx
0x180032b15  jz      short loc_180032B1B
0x180032b17  mov     [rsi+60h], r13
0x180032b1b  lea     rcx, [rbp+57h+var_90]; this
0x180032b1f  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180032b24  mov     eax, edi
0x180032b26  add     rsp, 0D8h
0x180032b2d  pop     r15
0x180032b2f  pop     r14
0x180032b31  pop     r13
0x180032b33  pop     r12
0x180032b35  pop     rdi
0x180032b36  pop     rsi
0x180032b37  pop     rbx
0x180032b38  pop     rbp
0x180032b39  retn
```
