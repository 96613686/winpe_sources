# CSearchJob::InitBeginSearch(ulong,CUpdateSession *,_GUID const &,wchar_t *)

- ea: `0x1800313b0`
- end: `0x180031719`
- name: `?InitBeginSearch@CSearchJob@@UEAAJKPEAVCUpdateSession@@AEBU_GUID@@PEA_W@Z`
- size: `873`
- prototype: `int(CSearchJob *__hidden this, unsigned int, struct CUpdateSession *, const struct _GUID *, wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001c770`

## callees

- `0x18000588c`
- `0x180006ac4`
- `0x180016e70`
- `0x180016e9c`
- `0x1800313b0`
- `0x180081a38`
- `0x18008d480`
- `0x1800940b4`
- `0x180096b10`
- `0x180096bb0`
- `0x180099ae8`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003146c`
- `OLEAUT32!__imp_SysAllocString` at `0x18003146c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003142a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003145b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003142a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003145b`

## string_xrefs

- `0x18003140e`: `C:\__w\1\s\src\Client\comapi\SearchJob.cpp`
- `0x18003164f`: `C:\__w\1\s\src\Client\comapi\SearchJob.cpp`
- `0x1800316f8`: `C:\__w\1\s\src\Client\comapi\SearchJob.cpp`
- `0x18003155e`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x180031593`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x1800315e7`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x1800316a7`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x1800316d9`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CSearchJob::InitBeginSearch(
        CSearchJob *this,
        unsigned int a2,
        struct CUpdateSession *a3,
        const struct _GUID *a4,
        wchar_t *strIn)
{
  wchar_t **v8; // rbx
  int v9; // edi
  __int64 v10; // rdx
  const OLECHAR *v11; // rdi
  BSTR v12; // rax
  const wchar_t *v13; // rdx
  int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rsi
  int v17; // r12d
  __int64 v18; // r15
  int v19; // eax
  int v20; // eax
  int RegionString; // eax
  void *v22; // rbx
  char v23; // al
  int v24; // eax
  int v26; // eax
  int v27; // eax
  void *lpMem; // [rsp+20h] [rbp-50h] BYREF
  const struct _GUID *v29; // [rsp+28h] [rbp-48h]
  char *v30; // [rsp+30h] [rbp-40h]
  CSearchJob *v31; // [rsp+38h] [rbp-38h]
  __int64 v32; // [rsp+40h] [rbp-30h]
  char *v33; // [rsp+48h] [rbp-28h]
  __int64 v34; // [rsp+50h] [rbp-20h]
  __int64 v35; // [rsp+58h] [rbp-18h]
  char v36; // [rsp+60h] [rbp-10h] BYREF
  char v37; // [rsp+61h] [rbp-Fh] BYREF
  int v38; // [rsp+64h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v29 = a4;
  v37 = 1;
  v38 = 0;
  v32 = 1;
  v30 = &v37;
  v31 = this;
  if ( strIn && *strIn )
  {
    v8 = (wchar_t **)((char *)this + 488);
    SysFreeString(*((BSTR *)this + 61));
    *v8 = 0;
    v9 = SusCopyBSTR(strIn, v8);
    if ( v9 < 0 )
    {
      v10 = 59;
LABEL_34:
      v15 = (unsigned int)v9;
      goto LABEL_35;
    }
  }
  else
  {
    v8 = (wchar_t **)((char *)this + 488);
    v11 = (const OLECHAR *)*((_QWORD *)&xmmword_1800EF1F0 + 1);
    SysFreeString(*((BSTR *)this + 61));
    *v8 = 0;
    if ( v11 )
    {
      v12 = SysAllocString(v11);
      *v8 = v12;
      if ( !v12 )
      {
        v9 = -2147024882;
        v10 = 55;
        goto LABEL_34;
      }
    }
  }
  if ( (unsigned int)AreTestKeysAllowed(1) && TestRegUtil::IsClientBlocked(*v8, v13) )
  {
    v9 = -2145124351;
    wil::details::in1diag3::Return_HrSuppressTelemetry(
      retaddr,
      (void *)0x41,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchJob.cpp",
      (const char *)0x80240001LL,
      (int)lpMem);
LABEL_36:
    v23 = v37;
    goto LABEL_23;
  }
  *((_QWORD *)this + 55) = a3;
  (*(void (__fastcall **)(char *))(*((_QWORD *)a3 + 3) + 8LL))((char *)a3 + 24);
  v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)(*((_QWORD *)this + 55) + 48LL) + 120LL))(
          *((_QWORD *)this + 55) + 48LL,
          &v38);
  v9 = v14;
  if ( v14 < 0 )
  {
    v15 = (unsigned int)v14;
    v10 = 74;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchJob.cpp",
      (const char *)v15,
      (int)lpMem);
    goto LABEL_36;
  }
  v16 = *((_QWORD *)this + 54);
  v17 = v38;
  v18 = *((_QWORD *)this + 55);
  v36 = 1;
  lpMem = 0;
  v35 = 1;
  v33 = &v36;
  v34 = v16;
  v19 = SusCopyBSTR(*v8, (wchar_t **)(v16 + 480));
  v9 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)(unsigned int)v19,
      (int)lpMem);
    if ( v36 )
    {
      v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF4,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
          (const char *)(unsigned int)v20,
          (int)lpMem);
    }
LABEL_33:
    v10 = 75;
    goto LABEL_34;
  }
  *(_QWORD *)(v16 + 344) = v18;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v18 + 24) + 8LL))(v18 + 24);
  *(_DWORD *)(v16 + 488) = v17;
  RegionString = GetRegionString((wchar_t **)&lpMem);
  v22 = lpMem;
  if ( RegionString >= 0 )
  {
    v26 = SusSysAllocString((const wchar_t *)lpMem, (wchar_t **)(v16 + 496));
    v9 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x105,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
        (const char *)(unsigned int)v26,
        (int)lpMem);
      if ( v36 )
      {
        v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
        if ( v27 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xF4,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
            (const char *)(unsigned int)v27,
            (int)lpMem);
      }
      if ( v22 )
        SusFree(v22);
      goto LABEL_33;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)(unsigned int)RegionString,
      (int)lpMem);
  }
  CUpdateLockdownInner::LockDown((CUpdateLockdownInner *)(v16 + 288), a2);
  v36 = 0;
  if ( v22 )
    SusFree(v22);
  *(struct _GUID *)((char *)this + 472) = *v29;
  v23 = 0;
  v37 = 0;
  v9 = 0;
LABEL_23:
  if ( v23 )
  {
    v24 = (*(__int64 (__fastcall **)(CSearchJob *))(*(_QWORD *)this + 40LL))(this);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchJob.cpp",
        (const char *)(unsigned int)v24,
        (int)lpMem);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800313b0  mov     [rsp-38h+arg_10], rbx
0x1800313b5  push    rbp
0x1800313b6  push    rsi
0x1800313b7  push    rdi
0x1800313b8  push    r12
0x1800313ba  push    r13
0x1800313bc  push    r14
0x1800313be  push    r15
0x1800313c0  mov     rbp, rsp
0x1800313c3  sub     rsp, 70h
0x1800313c7  mov     rax, cs:__security_cookie
0x1800313ce  xor     rax, rsp
0x1800313d1  mov     [rbp+var_8], rax
0x1800313d5  mov     [rbp+var_48], r9
0x1800313d9  mov     rsi, r8
0x1800313dc  mov     r13d, edx
0x1800313df  mov     r14, rcx
0x1800313e2  mov     rdi, [rbp+strIn]
0x1800313e6  mov     [rbp+var_F], 1
0x1800313ea  xor     r15d, r15d
0x1800313ed  mov     [rbp+var_C], r15d
0x1800313f1  xorps   xmm0, xmm0
0x1800313f4  xor     eax, eax
0x1800313f6  movups  [rbp+var_40], xmm0
0x1800313fa  mov     [rbp+var_30], rax
0x1800313fe  lea     rax, [rbp+var_F]
0x180031402  mov     qword ptr [rbp+var_40], rax
0x180031406  mov     qword ptr [rbp+var_40+8], rcx
0x18003140a  mov     byte ptr [rbp+var_30], 1
0x18003140e  lea     r12, aCW1SSrcClientC_73; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180031415  test    rdi, rdi
0x180031418  jz      short loc_18003144A
0x18003141a  cmp     [rdi], r15w
0x18003141e  jz      short loc_18003144A
0x180031420  lea     rbx, [rcx+1E8h]
0x180031427  mov     rcx, [rbx]; bstrString
0x18003142a  call    cs:__imp_SysFreeString
0x180031430  mov     [rbx], r15
0x180031433  mov     rdx, rbx; wchar_t **
0x180031436  mov     rcx, rdi; strIn
0x180031439  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x18003143e  mov     edi, eax
0x180031440  test    eax, eax
0x180031442  jns     short loc_18003148A
0x180031444  lea     edx, [r15+3Bh]
0x180031448  jmp     short loc_180031482
0x18003144a  lea     rbx, [rcx+1E8h]
0x180031451  mov     rdi, qword ptr cs:xmmword_1800EF1F0+8
0x180031458  mov     rcx, [rbx]; bstrString
0x18003145b  call    cs:__imp_SysFreeString
0x180031461  mov     [rbx], r15
0x180031464  test    rdi, rdi
0x180031467  jz      short loc_18003148A
0x180031469  mov     rcx, rdi; psz
0x18003146c  call    cs:__imp_SysAllocString
0x180031472  mov     [rbx], rax
0x180031475  test    rax, rax
0x180031478  jnz     short loc_18003148A
0x18003147a  mov     edi, 8007000Eh
0x18003147f  lea     edx, [rax+37h]
0x180031482  mov     r8, r12
0x180031485  jmp     loc_180031704
0x18003148a  mov     cl, 1; bool
0x18003148c  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x180031491  test    eax, eax
0x180031493  jz      short loc_1800314BF
0x180031495  mov     rcx, [rbx]; lpString1
0x180031498  call    ?IsClientBlocked@TestRegUtil@@YA_NPEB_W@Z; TestRegUtil::IsClientBlocked(wchar_t const *)
0x18003149d  test    al, al
0x18003149f  jz      short loc_1800314BF
0x1800314a1  mov     rcx, [rbp+38h]; this
0x1800314a5  mov     edi, 80240001h
0x1800314aa  mov     r9d, edi; char *
0x1800314ad  mov     r8, r12; unsigned int
0x1800314b0  mov     edx, 41h ; 'A'; void *
0x1800314b5  call    ?Return_HrSuppressTelemetry@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_HrSuppressTelemetry(void *,uint,char const *,long)
0x1800314ba  jmp     loc_180031710
0x1800314bf  mov     [r14+1B8h], rsi
0x1800314c6  lea     rcx, [rsi+18h]
0x1800314ca  mov     rax, [rcx]
0x1800314cd  mov     rax, [rax+8]
0x1800314d1  call    _guard_dispatch_icall
0x1800314d6  mov     rcx, [r14+1B8h]
0x1800314dd  add     rcx, 30h ; '0'
0x1800314e1  mov     rax, [rcx]
0x1800314e4  lea     rdx, [rbp+var_C]
0x1800314e8  mov     rax, [rax+78h]
0x1800314ec  call    _guard_dispatch_icall
0x1800314f1  mov     edi, eax
0x1800314f3  test    eax, eax
0x1800314f5  jns     short loc_180031507
0x1800314f7  mov     r9d, eax
0x1800314fa  mov     r8, r12
0x1800314fd  mov     edx, 4Ah ; 'J'
0x180031502  jmp     loc_180031707
0x180031507  mov     rsi, [r14+1B0h]
0x18003150e  mov     r12d, [rbp+var_C]
0x180031512  mov     r15, [r14+1B8h]
0x180031519  mov     [rbp+var_10], 1
0x18003151d  mov     [rbp+lpMem], 0
0x180031525  xorps   xmm0, xmm0
0x180031528  xor     eax, eax
0x18003152a  movups  [rbp+var_28], xmm0
0x18003152e  mov     [rbp+var_18], rax
0x180031532  lea     rax, [rbp+var_10]
0x180031536  mov     qword ptr [rbp+var_28], rax
0x18003153a  mov     qword ptr [rbp+var_28+8], rsi
0x18003153e  mov     byte ptr [rbp+var_18], 1
0x180031542  lea     rdx, [rsi+1E0h]; wchar_t **
0x180031549  mov     rcx, [rbx]; strIn
0x18003154c  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x180031551  mov     edi, eax
0x180031553  test    eax, eax
0x180031555  jns     short loc_1800315AA
0x180031557  mov     rcx, [rbp+38h]; this
0x18003155b  mov     r9d, eax; char *
0x18003155e  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180031565  mov     edx, 0FDh; void *
0x18003156a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003156f  nop
0x180031570  xor     r15d, r15d
0x180031573  cmp     [rbp+var_10], r15b
0x180031577  jz      short loc_1800315A5
0x180031579  mov     rax, [rsi]
0x18003157c  mov     rcx, rsi
0x18003157f  mov     rax, [rax+18h]
0x180031583  call    _guard_dispatch_icall
0x180031588  mov     rcx, [rbp+38h]; this
0x18003158c  test    eax, eax
0x18003158e  jns     short loc_1800315A5
0x180031590  mov     r9d, eax; char *
0x180031593  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x18003159a  mov     edx, 0F4h; void *
0x18003159f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800315a4  nop
0x1800315a5  jmp     loc_1800316F8
0x1800315aa  mov     [rsi+158h], r15
0x1800315b1  lea     rcx, [r15+18h]
0x1800315b5  mov     rax, [rcx]
0x1800315b8  mov     rax, [rax+8]
0x1800315bc  call    _guard_dispatch_icall
0x1800315c1  mov     [rsi+1E8h], r12d
0x1800315c8  lea     rcx, [rbp+lpMem]; wchar_t **
0x1800315cc  call    ?GetRegionString@@YAJPEAPEA_W@Z; GetRegionString(wchar_t * *)
0x1800315d1  mov     rcx, [rbp+38h]; this
0x1800315d5  mov     rbx, [rbp+lpMem]
0x1800315d9  xor     r15d, r15d
0x1800315dc  test    eax, eax
0x1800315de  jns     loc_180031687
0x1800315e4  mov     r9d, eax; char *
0x1800315e7  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x1800315ee  mov     edx, 103h; void *
0x1800315f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800315f8  lea     rcx, [rsi+120h]; this
0x1800315ff  mov     edx, r13d; unsigned int
0x180031602  call    ?LockDown@CUpdateLockdownInner@@QEAAJK@Z; CUpdateLockdownInner::LockDown(ulong)
0x180031607  mov     [rbp+var_10], r15b
0x18003160b  test    rbx, rbx
0x18003160e  jz      short loc_180031618
0x180031610  mov     rcx, rbx; lpMem
0x180031613  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180031618  mov     rax, [rbp+var_48]
0x18003161c  movups  xmm0, xmmword ptr [rax]
0x18003161f  movdqu  xmmword ptr [r14+1D8h], xmm0
0x180031628  mov     al, r15b
0x18003162b  mov     [rbp+var_F], al
0x18003162e  mov     edi, r15d
0x180031631  test    al, al
0x180031633  jz      short loc_180031661
0x180031635  mov     rax, [r14]
0x180031638  mov     rcx, r14
0x18003163b  mov     rax, [rax+28h]
0x18003163f  call    _guard_dispatch_icall
0x180031644  mov     rcx, [rbp+38h]; this
0x180031648  test    eax, eax
0x18003164a  jns     short loc_180031661
0x18003164c  mov     r9d, eax; char *
0x18003164f  lea     r8, aCW1SSrcClientC_73; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180031656  mov     edx, 31h ; '1'; void *
0x18003165b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031660  nop
0x180031661  mov     eax, edi
0x180031663  mov     rcx, [rbp+var_8]
0x180031667  xor     rcx, rsp; StackCookie
0x18003166a  call    __security_check_cookie
0x18003166f  mov     rbx, [rsp+70h+arg_10]
0x180031677  add     rsp, 70h
0x18003167b  pop     r15
0x18003167d  pop     r14
0x18003167f  pop     r13
0x180031681  pop     r12
0x180031683  pop     rdi
0x180031684  pop     rsi
0x180031685  pop     rbp
0x180031686  retn
0x180031687  lea     rdx, [rsi+1F0h]; wchar_t **
0x18003168e  mov     rcx, rbx; wchar_t *
0x180031691  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x180031696  mov     edi, eax
0x180031698  test    eax, eax
0x18003169a  jns     loc_1800315F8
0x1800316a0  mov     rcx, [rbp+38h]; this
0x1800316a4  mov     r9d, eax; char *
0x1800316a7  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x1800316ae  mov     edx, 105h; void *
0x1800316b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800316b8  nop
0x1800316b9  cmp     [rbp+var_10], r15b
0x1800316bd  jz      short loc_1800316EB
0x1800316bf  mov     rax, [rsi]
0x1800316c2  mov     rcx, rsi
0x1800316c5  mov     rax, [rax+18h]
0x1800316c9  call    _guard_dispatch_icall
0x1800316ce  mov     rcx, [rbp+38h]; this
0x1800316d2  test    eax, eax
0x1800316d4  jns     short loc_1800316EB
0x1800316d6  mov     r9d, eax; char *
0x1800316d9  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x1800316e0  mov     edx, 0F4h; void *
0x1800316e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800316ea  nop
0x1800316eb  test    rbx, rbx
0x1800316ee  jz      short loc_1800316F8
0x1800316f0  mov     rcx, rbx; lpMem
0x1800316f3  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800316f8  lea     r8, aCW1SSrcClientC_73; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x1800316ff  mov     edx, 4Bh ; 'K'; void *
0x180031704  mov     r9d, edi; char *
0x180031707  mov     rcx, [rbp+38h]; this
0x18003170b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031710  mov     al, [rbp+var_F]
0x180031713  jmp     loc_180031631
```
