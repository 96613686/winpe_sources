# CSingleIdentity::GetJWTCredential(CSingleIdentity *,ushort const *,ISystemStoreLiteFunctions *,ushort const *,long *)

- ea: `0x18008d7c4`
- end: `0x18008dd9e`
- name: `?GetJWTCredential@CSingleIdentity@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV1@PEBGPEAVISystemStoreLiteFunctions@@1PEAJ@Z`
- size: `1498`
- prototype: `__int64 __usercall@<rax>(CSingleIdentity *this@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bdb00`

## callees

- `0x180009e98`
- `0x18000a36c`
- `0x18000ed04`
- `0x180011f38`
- `0x1800151c4`
- `0x180015860`
- `0x180018f80`
- `0x1800191c0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x180024a94`
- `0x1800277c0`
- `0x180037288`
- `0x180040798`
- `0x180052ca8`
- `0x180083078`
- `0x180084374`
- `0x18008d4bc`
- `0x18008d7c4`
- `0x18008dda4`
- `0x1800964c0`
- `0x18009fa98`
- `0x1800a3b60`
- `0x1800d7078`
- `0x1800d7194`
- `0x180110800`
- `0x1801146a4`
- `0x180114b40`
- `0x180114e68`
- `0x180115310`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008da38`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008db57`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008da38`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008db57`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18008d976`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18008d976`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008dd4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008dd4f`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x18008dbc5`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x18008dbc5`

## string_xrefs

- `0x18008d847`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18008d904`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18008d925`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18008da86`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18008daa9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18008d8f7`: `Auth token is unavailable.`
- `0x18008da79`: `Auth token is unavailable.`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
_QWORD *__fastcall CSingleIdentity::GetJWTCredential(
        CSingleIdentity *this,
        _QWORD *a2,
        CSingleIdentity *a3,
        __int64 a4,
        __int64 *a5,
        _WORD *a6,
        _DWORD *a7)
{
  __int64 v11; // rax
  char v12; // si
  unsigned __int64 v13; // rdi
  void *v14; // rdx
  __int64 v15; // rbx
  unsigned int v16; // ebx
  unsigned __int64 v17; // rdi
  ATL::Checked *v18; // rdx
  __int64 v19; // rbx
  unsigned int v20; // ebx
  __int64 v21; // rax
  __int64 RefreshTokenXTokenCredential; // rax
  CSecureString *v23; // rcx
  __int64 RefreshTokenCredential; // rax
  HLOCAL v25; // rcx
  int *v27; // [rsp+20h] [rbp-E0h]
  int *v28; // [rsp+20h] [rbp-E0h]
  int ServiceToken; // [rsp+40h] [rbp-C0h] BYREF
  void **v30; // [rsp+48h] [rbp-B8h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  const BYTE *v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35[2]; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  int v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL *p_hMem; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h] BYREF
  int v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h] BYREF
  int *v43[4]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v44[5]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v45[36]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 *v46; // [rsp+190h] [rbp+90h]
  _BYTE v47[176]; // [rsp+1B0h] [rbp+B0h] BYREF
  void *Block; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v49[264]; // [rsp+268h] [rbp+168h] BYREF
  ATL::Checked *v50; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v51[264]; // [rsp+378h] [rbp+278h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v44[4] = a2;
  v37 = 0;
  ServiceToken = 0;
  v44[0] = "CSingleIdentity::GetJWTCredential";
  v44[1] = &ServiceToken;
  v44[2] = 0;
  v44[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    "CSingleIdentity::GetJWTCredential",
    (const char *)0x501,
    0,
    (const unsigned __int16 *)v27);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v43,
    "CSingleIdentity::GetJWTCredential",
    &ServiceToken,
    0xEu,
    (const int *)&qword_180171C28);
  hMem = 0;
  v11 = *a5;
  p_hMem = &hMem;
  v40 = 0;
  LOBYTE(v41) = 1;
  (*(void (__fastcall **)(__int64 *, __int64 *))(v11 + 32))(a5, &v40);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  v31 = 0;
  (*(void (__fastcall **)(__int64 *, HLOCAL, __int64, int *))(*a5 + 40))(a5, hMem, a4, &v31);
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)v45);
  ServiceToken = CSingleIdentity::GetServiceToken(a3, L"http://Passport.NET/tb", (struct CPPCRLToken *)v45);
  if ( ServiceToken < 0 )
  {
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x517u,
      L"Auth token is unavailable.");
    ServiceToken = -2147186591;
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x518,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      (const char *)0x80048861LL,
      (int)v28);
  }
  v40 = 0;
  LODWORD(p_hMem) = 0;
  v41 = 0;
  CBytePtr::Attach((CBytePtr *)&p_hMem, v46, v45[34], 0);
  v35[0] = (unsigned int)p_hMem;
  v35[1] = v40;
  if ( !v40 && (_DWORD)p_hMem )
  {
    _o_terminate();
    __debugbreak();
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)this + 80LL))(this) )
  {
    v12 = 0;
    v13 = *(_QWORD *)CPPCRLToken::GetToken(v45, &v30);
    Block = v49;
    if ( v13 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v13 + 2 * v15) );
      v16 = v15 + 1;
      ATL::AtlConvAllocMemory<unsigned short>(&Block, v16, v49);
      ATL::Checked::memcpy_s(
        (ATL::Checked *)Block,
        (void *)(2LL * (int)v16),
        v13,
        (const void *)(2LL * (int)v16),
        (unsigned __int64)v28);
      v14 = Block;
    }
    else
    {
      v14 = 0;
      Block = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v33, v14);
    if ( Block != v49 )
      free(Block);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v30);
  }
  else
  {
    CPPCRLToken::CPPCRLToken((CPPCRLToken *)v47);
    ServiceToken = CSingleIdentity::GetServiceToken(this, L"http://Passport.NET/tb", (struct CPPCRLToken *)v47);
    if ( ServiceToken < 0 )
    {
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        0x529u,
        L"Auth token is unavailable.");
      ServiceToken = -2147186591;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x52A,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        (const char *)0x80048861LL,
        (int)v28);
    }
    v12 = 1;
    v17 = *(_QWORD *)CPPCRLToken::GetToken(v47, &v30);
    v50 = (ATL::Checked *)v51;
    if ( v17 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v17 + 2 * v19) );
      v20 = v19 + 1;
      ATL::AtlConvAllocMemory<unsigned short>(&v50, v20, v51);
      ATL::Checked::memcpy_s(v50, (void *)(2LL * (int)v20), v17, (const void *)(2LL * (int)v20), (unsigned __int64)v28);
      v18 = v50;
    }
    else
    {
      v18 = 0;
      v50 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v33, v18);
    if ( v50 != (ATL::Checked *)v51 )
      free(v50);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v30);
    CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v47);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v38,
    a6);
  StringUtility::ParseNavigationUrlHostName(&v34, &v38);
  v21 = StringUtility::ParseNavigationUrlNonce(&v42, &v38);
  StringUtility::UrlDecode(&v32, v21);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(a2);
  v37 = 1;
  if ( (unsigned int)MsaDevice_UseXTokenBasedSessionKey() )
  {
    if ( *((_DWORD *)v32 - 4) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        v35,
        &qword_18013DE20);
      NonceCache::CacheNonceInRegistry(&v34, &v32, v35);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v35);
    }
    v30 = &CXboxSignatureProvider::`vftable';
    if ( v12 )
      RefreshTokenXTokenCredential = JWTHelper::MakeRefreshTokenXTokenCredential(
                                       (unsigned int)v35,
                                       (unsigned int)&v34,
                                       (unsigned int)&v33,
                                       (unsigned int)&v31,
                                       (__int64)&v32,
                                       (__int64)&v30);
    else
      RefreshTokenXTokenCredential = JWTHelper::MakeDeviceXTokenCredential(
                                       (unsigned int)v35,
                                       (unsigned int)&v34,
                                       (unsigned int)&v33,
                                       (unsigned int)&v32,
                                       (__int64)&v30);
    ATL::CSimpleStringT<unsigned short,0>::operator=(a2, RefreshTokenXTokenCredential);
    v23 = (CSecureString *)v35;
  }
  else
  {
    if ( v12 )
      RefreshTokenCredential = JWTHelper::MakeRefreshTokenCredential(
                                 (unsigned int)&v30,
                                 v45[0],
                                 (unsigned int)v35,
                                 (unsigned int)&v34,
                                 (__int64)&v33,
                                 (__int64)&v31,
                                 (__int64)&v32);
    else
      RefreshTokenCredential = JWTHelper::MakeDeviceCredential(
                                 (unsigned int)&v30,
                                 v45[0],
                                 (unsigned int)v35,
                                 (unsigned int)&v34,
                                 (__int64)&v33,
                                 (__int64)&v32);
    ATL::CSimpleStringT<unsigned short,0>::operator=(a2, RefreshTokenCredential);
    v23 = (CSecureString *)&v30;
  }
  CSecureString::~CSecureString(v23);
  if ( a7 )
    *a7 = GetTimeSkew();
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v34);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  CSecureString::~CSecureString((CSecureString *)&v33);
  CBytePtr::Empty((CBytePtr *)&p_hMem);
  CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v45);
  v25 = hMem;
  hMem = 0;
  if ( v25 )
    LocalFree(v25);
  ErrorVerifier::CheckAgainstList((const char *)v43[3], *v43[2], (unsigned __int64)v43[1], v43[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v44);
  return a2;
}

```

## disassembly

```asm
0x18008d7c4  push    rbp
0x18008d7c6  push    rbx
0x18008d7c7  push    rsi
0x18008d7c8  push    rdi
0x18008d7c9  push    r12
0x18008d7cb  push    r13
0x18008d7cd  push    r14
0x18008d7cf  push    r15
0x18008d7d1  lea     rbp, [rsp-398h]
0x18008d7d9  sub     rsp, 498h
0x18008d7e0  mov     rax, cs:__security_cookie
0x18008d7e7  xor     rax, rsp
0x18008d7ea  mov     [rbp+3D0h+var_50], rax
0x18008d7f1  mov     rdi, r9
0x18008d7f4  mov     rsi, r8
0x18008d7f7  mov     r14, rdx
0x18008d7fa  mov     r15, rcx
0x18008d7fd  mov     [rbp+3D0h+var_3D8], rdx
0x18008d801  mov     rbx, [rbp+3D0h+arg_20]
0x18008d808  mov     r13, [rbp+3D0h+arg_28]
0x18008d80f  mov     r12, [rbp+3D0h+arg_30]
0x18008d816  xor     edx, edx
0x18008d818  mov     [rbp+3D0h+var_448], edx
0x18008d81b  mov     [rsp+4D0h+var_490], edx
0x18008d81f  lea     rcx, aCsingleidentit_31; "CSingleIdentity::GetJWTCredential"
0x18008d826  mov     [rbp+3D0h+var_3F8], rcx
0x18008d82a  lea     rax, [rsp+4D0h+var_490]
0x18008d82f  mov     [rbp+3D0h+var_3F0], rax
0x18008d833  mov     [rbp+3D0h+var_3E8], rdx
0x18008d837  mov     [rbp+3D0h+var_3E0], rdx
0x18008d83b  xor     r9d, r9d; unsigned int
0x18008d83e  mov     r8d, 501h; char *
0x18008d844  mov     rdx, rcx; char *
0x18008d847  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008d84e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18008d853  nop
0x18008d854  lea     rax, qword_180171C28
0x18008d85b  mov     [rsp+4D0h+var_4B0], rax; unsigned __int64
0x18008d860  mov     r9d, 0Eh; unsigned __int64
0x18008d866  lea     r8, [rsp+4D0h+var_490]; int *
0x18008d86b  lea     rdx, aCsingleidentit_31; "CSingleIdentity::GetJWTCredential"
0x18008d872  lea     rcx, [rbp+3D0h+var_418]; this
0x18008d876  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18008d87b  nop
0x18008d87c  xor     edx, edx
0x18008d87e  mov     [rbp+3D0h+hMem], rdx
0x18008d882  mov     rax, [rbx]
0x18008d885  lea     rcx, [rbp+3D0h+hMem]
0x18008d889  mov     [rbp+3D0h+var_438], rcx
0x18008d88d  mov     [rbp+3D0h+var_430], rdx
0x18008d891  mov     byte ptr [rbp+3D0h+var_428], 1
0x18008d895  lea     rdx, [rbp+3D0h+var_430]
0x18008d899  mov     rcx, rbx
0x18008d89c  mov     rax, [rax+20h]
0x18008d8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8a5  nop
0x18008d8a6  lea     rcx, [rbp+3D0h+var_438]
0x18008d8aa  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18008d8af  xor     eax, eax
0x18008d8b1  mov     [rsp+4D0h+var_480], eax
0x18008d8b5  mov     rax, [rbx]
0x18008d8b8  lea     r9, [rsp+4D0h+var_480]
0x18008d8bd  mov     r8, rdi
0x18008d8c0  mov     rdx, [rbp+3D0h+hMem]
0x18008d8c4  mov     rcx, rbx
0x18008d8c7  mov     rax, [rax+28h]
0x18008d8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8d0  lea     rcx, [rbp+3D0h+var_3D0]; this
0x18008d8d4  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x18008d8d9  nop
0x18008d8da  lea     r8, [rbp+3D0h+var_3D0]; struct CPPCRLToken *
0x18008d8de  lea     rdx, aHttpPassportNe_2; "http://Passport.NET/tb"
0x18008d8e5  mov     rcx, rsi; this
0x18008d8e8  call    ?GetServiceToken@CSingleIdentity@@QEAAJPEBGAEAVCPPCRLToken@@@Z; CSingleIdentity::GetServiceToken(ushort const *,CPPCRLToken &)
0x18008d8ed  mov     [rsp+4D0h+var_490], eax
0x18008d8f1  xor     ebx, ebx
0x18008d8f3  test    eax, eax
0x18008d8f5  jns     short loc_18008D937
0x18008d8f7  lea     r9, aAuthTokenIsUna; "Auth token is unavailable."
0x18008d8fe  mov     r8d, 517h; unsigned int
0x18008d904  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008d90b  lea     ecx, [rbx+2]; unsigned __int8
0x18008d90e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18008d913  mov     r9d, 80048861h; char *
0x18008d919  mov     [rsp+4D0h+var_490], r9d
0x18008d91e  mov     rcx, [rbp+3D8h]; this
0x18008d925  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008d92c  mov     edx, 518h; void *
0x18008d931  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008d937  mov     [rbp+3D0h+var_430], rbx
0x18008d93b  mov     dword ptr [rbp+3D0h+var_438], ebx
0x18008d93e  mov     [rbp+3D0h+var_428], ebx
0x18008d941  xor     r9d, r9d; bool
0x18008d944  mov     r8d, [rbp+3D0h+var_348]; unsigned int
0x18008d94b  mov     rdx, [rbp+3D0h+var_340]; unsigned __int8 *
0x18008d952  lea     rcx, [rbp+3D0h+var_438]; this
0x18008d956  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x18008d95b  mov     ecx, dword ptr [rbp+3D0h+var_438]
0x18008d95e  mov     [rsp+4D0h+var_460], rcx
0x18008d963  mov     rax, [rbp+3D0h+var_430]
0x18008d967  mov     [rsp+4D0h+var_458], rax
0x18008d96c  test    rax, rax
0x18008d96f  jnz     short loc_18008D97D
0x18008d971  test    rcx, rcx
0x18008d974  jz      short loc_18008D97D
0x18008d976  call    cs:__imp__o_terminate
0x18008d97c  int     3; Trap to Debugger
0x18008d97d  lea     rcx, [rsp+4D0h+var_470]
0x18008d982  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008d987  nop
0x18008d988  mov     rax, [r15]
0x18008d98b  mov     rcx, r15
0x18008d98e  mov     rax, [rax+50h]
0x18008d992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d997  test    eax, eax
0x18008d999  jz      loc_18008DA4E
0x18008d99f  mov     sil, bl
0x18008d9a2  lea     rdx, [rsp+4D0h+var_488]
0x18008d9a7  lea     rcx, [rbp+3D0h+var_3D0]
0x18008d9ab  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x18008d9b0  nop
0x18008d9b1  mov     rdi, [rax]
0x18008d9b4  lea     rax, [rbp+3D0h+var_268]
0x18008d9bb  mov     [rbp+3D0h+Block], rax
0x18008d9c2  test    rdi, rdi
0x18008d9c5  jnz     short loc_18008D9D3
0x18008d9c7  mov     rdx, rbx
0x18008d9ca  mov     [rbp+3D0h+Block], rbx
0x18008d9d1  jmp     short loc_18008DA1A
0x18008d9d3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008d9d7  xor     eax, eax
0x18008d9d9  inc     rbx
0x18008d9dc  cmp     [rdi+rbx*2], ax
0x18008d9e0  jnz     short loc_18008D9D9
0x18008d9e2  inc     ebx
0x18008d9e4  lea     r8, [rbp+3D0h+var_268]
0x18008d9eb  mov     edx, ebx
0x18008d9ed  lea     rcx, [rbp+3D0h+Block]
0x18008d9f4  call    ??$AtlConvAllocMemory@G@ATL@@YAXPEAPEAGHPEAGH@Z; ATL::AtlConvAllocMemory<ushort>(ushort * *,int,ushort *,int)
0x18008d9f9  movsxd  rdx, ebx
0x18008d9fc  add     rdx, rdx; void *
0x18008d9ff  mov     r9, rdx; void *
0x18008da02  mov     r8, rdi; unsigned __int64
0x18008da05  mov     rcx, [rbp+3D0h+Block]; this
0x18008da0c  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18008da11  mov     rdx, [rbp+3D0h+Block]
0x18008da18  xor     ebx, ebx
0x18008da1a  lea     rcx, [rsp+4D0h+var_470]
0x18008da1f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18008da24  nop
0x18008da25  mov     rcx, [rbp+3D0h+Block]; Block
0x18008da2c  lea     rax, [rbp+3D0h+var_268]
0x18008da33  cmp     rcx, rax
0x18008da36  jz      short loc_18008DA3F
0x18008da38  call    cs:__imp_free
0x18008da3e  nop
0x18008da3f  lea     rcx, [rsp+4D0h+var_488]
0x18008da44  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008da49  jmp     loc_18008DB75
0x18008da4e  lea     rcx, [rbp+3D0h+var_320]; this
0x18008da55  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x18008da5a  nop
0x18008da5b  lea     r8, [rbp+3D0h+var_320]; struct CPPCRLToken *
0x18008da62  lea     rdx, aHttpPassportNe_2; "http://Passport.NET/tb"
0x18008da69  mov     rcx, r15; this
0x18008da6c  call    ?GetServiceToken@CSingleIdentity@@QEAAJPEBGAEAVCPPCRLToken@@@Z; CSingleIdentity::GetServiceToken(ushort const *,CPPCRLToken &)
0x18008da71  mov     [rsp+4D0h+var_490], eax
0x18008da75  test    eax, eax
0x18008da77  jns     short loc_18008DABB
0x18008da79  lea     r9, aAuthTokenIsUna; "Auth token is unavailable."
0x18008da80  mov     r8d, 529h; unsigned int
0x18008da86  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008da8d  mov     ecx, 2; unsigned __int8
0x18008da92  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18008da97  mov     r9d, 80048861h; char *
0x18008da9d  mov     [rsp+4D0h+var_490], r9d
0x18008daa2  mov     rcx, [rbp+3D8h]; this
0x18008daa9  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008dab0  mov     edx, 52Ah; void *
0x18008dab5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008dabb  mov     sil, 1
0x18008dabe  lea     rdx, [rsp+4D0h+var_488]
0x18008dac3  lea     rcx, [rbp+3D0h+var_320]
0x18008daca  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x18008dacf  nop
0x18008dad0  mov     rdi, [rax]
0x18008dad3  lea     rax, [rbp+3D0h+var_158]
0x18008dada  mov     [rbp+3D0h+var_160], rax
0x18008dae1  test    rdi, rdi
0x18008dae4  jnz     short loc_18008DAF2
0x18008dae6  mov     rdx, rbx
0x18008dae9  mov     [rbp+3D0h+var_160], rbx
0x18008daf0  jmp     short loc_18008DB39
0x18008daf2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008daf6  xor     eax, eax
0x18008daf8  inc     rbx
0x18008dafb  cmp     [rdi+rbx*2], ax
0x18008daff  jnz     short loc_18008DAF8
0x18008db01  inc     ebx
0x18008db03  lea     r8, [rbp+3D0h+var_158]
0x18008db0a  mov     edx, ebx
0x18008db0c  lea     rcx, [rbp+3D0h+var_160]
0x18008db13  call    ??$AtlConvAllocMemory@G@ATL@@YAXPEAPEAGHPEAGH@Z; ATL::AtlConvAllocMemory<ushort>(ushort * *,int,ushort *,int)
0x18008db18  movsxd  rdx, ebx
0x18008db1b  add     rdx, rdx; void *
0x18008db1e  mov     r9, rdx; void *
0x18008db21  mov     r8, rdi; unsigned __int64
0x18008db24  mov     rcx, [rbp+3D0h+var_160]; this
0x18008db2b  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18008db30  mov     rdx, [rbp+3D0h+var_160]
0x18008db37  xor     ebx, ebx
0x18008db39  lea     rcx, [rsp+4D0h+var_470]
0x18008db3e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18008db43  nop
0x18008db44  mov     rcx, [rbp+3D0h+var_160]; Block
0x18008db4b  lea     rax, [rbp+3D0h+var_158]
0x18008db52  cmp     rcx, rax
0x18008db55  jz      short loc_18008DB5E
0x18008db57  call    cs:__imp_free
0x18008db5d  nop
0x18008db5e  lea     rcx, [rsp+4D0h+var_488]
0x18008db63  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008db68  nop
0x18008db69  lea     rcx, [rbp+3D0h+var_320]; this
0x18008db70  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x18008db75  mov     rdx, r13
0x18008db78  lea     rcx, [rbp+3D0h+var_440]
0x18008db7c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18008db81  nop
0x18008db82  lea     rdx, [rbp+3D0h+var_440]
0x18008db86  lea     rcx, [rsp+4D0h+var_468]
0x18008db8b  call    ?ParseNavigationUrlHostName@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@@Z; StringUtility::ParseNavigationUrlHostName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18008db90  nop
0x18008db91  lea     rdx, [rbp+3D0h+var_440]
0x18008db95  lea     rcx, [rbp+3D0h+var_420]
0x18008db99  call    ?ParseNavigationUrlNonce@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@@Z; StringUtility::ParseNavigationUrlNonce(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18008db9e  nop
0x18008db9f  mov     rdx, rax
0x18008dba2  lea     rcx, [rsp+4D0h+var_478]
0x18008dba7  call    ?UrlDecode@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@@Z; StringUtility::UrlDecode(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18008dbac  nop
0x18008dbad  lea     rcx, [rbp+3D0h+var_420]
0x18008dbb1  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008dbb6  mov     rcx, r14
0x18008dbb9  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008dbbe  mov     [rbp+3D0h+var_448], 1
0x18008dbc5  call    cs:__imp_MsaDevice_UseXTokenBasedSessionKey
0x18008dbcb  test    eax, eax
0x18008dbcd  jz      loc_18008DC81
0x18008dbd3  mov     rax, [rsp+4D0h+var_478]
0x18008dbd8  cmp     [rax-10h], ebx
0x18008dbdb  jz      short loc_18008DC0E
0x18008dbdd  lea     rdx, qword_18013DE20
0x18008dbe4  lea     rcx, [rsp+4D0h+var_460]
0x18008dbe9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18008dbee  nop
0x18008dbef  lea     r8, [rsp+4D0h+var_460]
0x18008dbf4  lea     rdx, [rsp+4D0h+var_478]
0x18008dbf9  lea     rcx, [rsp+4D0h+var_468]
0x18008dbfe  call    ?CacheNonceInRegistry@NonceCache@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; NonceCache::CacheNonceInRegistry(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18008dc03  nop
0x18008dc04  lea     rcx, [rsp+4D0h+var_460]
0x18008dc09  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008dc0e  lea     rax, ??_7CXboxSignatureProvider@@6B@; const CXboxSignatureProvider::`vftable'
0x18008dc15  mov     [rsp+4D0h+var_488], rax
0x18008dc1a  lea     rax, [rsp+4D0h+var_488]
0x18008dc1f  lea     r8, [rsp+4D0h+var_470]
0x18008dc24  lea     rdx, [rsp+4D0h+var_468]
0x18008dc29  lea     rcx, [rsp+4D0h+var_460]
0x18008dc2e  test    sil, sil
0x18008dc31  jz      short loc_18008DC63
0x18008dc33  mov     [rsp+4D0h+var_4A8], rax
0x18008dc38  lea     rax, [rsp+4D0h+var_478]
0x18008dc3d  mov     [rsp+4D0h+var_4B0], rax
0x18008dc42  lea     r9, [rsp+4D0h+var_480]
0x18008dc47  call    ?MakeRefreshTokenXTokenCredential@JWTHelper@@SA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV2@AEBW4ReportingAccountType@@0AEBVIXboxSignatureProvider@LiteCryptUtilities@@@Z; JWTHelper::MakeRefreshTokenXTokenCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CSecureString const &,ReportingAccountType const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,LiteCryptUtilities::IXboxSignatureProvider const &)
0x18008dc4c  nop
0x18008dc4d  mov     rdx, rax
0x18008dc50  mov     rcx, r14
0x18008dc53  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18008dc58  nop
0x18008dc59  lea     rcx, [rsp+4D0h+var_460]
0x18008dc5e  jmp     loc_18008DCF0
0x18008dc63  mov     [rsp+4D0h+var_4B0], rax
0x18008dc68  lea     r9, [rsp+4D0h+var_478]
0x18008dc6d  call    ?MakeDeviceXTokenCredential@JWTHelper@@SA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV2@0AEBVIXboxSignatureProvider@LiteCryptUtilities@@@Z; JWTHelper::MakeDeviceXTokenCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,LiteCryptUtilities::IXboxSignatureProvider const &)
0x18008dc72  nop
0x18008dc73  mov     rdx, rax
0x18008dc76  mov     rcx, r14
0x18008dc79  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18008dc7e  nop
0x18008dc7f  jmp     short loc_18008DC59
0x18008dc81  lea     rax, [rsp+4D0h+var_478]
0x18008dc86  lea     r9, [rsp+4D0h+var_468]
0x18008dc8b  lea     r8, [rsp+4D0h+var_460]
0x18008dc90  mov     edx, [rbp+3D0h+var_3D0]
0x18008dc93  lea     rcx, [rsp+4D0h+var_488]
0x18008dc98  test    sil, sil
0x18008dc9b  jz      short loc_18008DCCA
0x18008dc9d  mov     [rsp+4D0h+var_4A0], rax
  ... truncated ...
```
