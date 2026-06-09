# RequestKey(ushort const *,CAutoRefPtr<CSingleIdentity>,IIdentityWrapper const *,IRequestWrapper const *)

- ea: `0x18002d838`
- end: `0x18002df95`
- name: `?RequestKey@@YAJPEBGV?$CAutoRefPtr@VCSingleIdentity@@@@PEBVIIdentityWrapper@@PEBVIRequestWrapper@@@Z`
- size: `1885`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180058c30`
- `0x18005942c`

## callees

- `0x18000fd04`
- `0x180010fb8`
- `0x180013448`
- `0x180013488`
- `0x1800151c4`
- `0x180015430`
- `0x180015fb0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18002d36c`
- `0x18002d838`
- `0x18002df9c`
- `0x18002dfcc`
- `0x18002e11c`
- `0x18002e17c`
- `0x18002eae8`
- `0x18002ed50`
- `0x18003c814`
- `0x18004f99c`
- `0x1800a3b60`
- `0x1800a400c`
- `0x1800aee98`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002d8c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002d8c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dad9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dad9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de5c`

## string_xrefs

- `0x18002d8a2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002daa4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002dd03`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002dd73`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002dda9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002ddef`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002de3d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002dedd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002df28`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall RequestKey(__int64 a1, struct CSingleIdentity **a2, __int64 a3, __int64 a4)
{
  unsigned __int16 v8; // di
  __int64 v9; // rbx
  __int64 *v10; // rax
  const unsigned __int16 *v11; // rbx
  int v12; // eax
  int v13; // r15d
  int v14; // eax
  int v15; // eax
  int v16; // ebx
  int v17; // ecx
  int v18; // edx
  int v19; // eax
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  const unsigned __int16 *v25; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v26; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+28h] [rbp-D8h]
  __int64 v28; // [rsp+30h] [rbp-D0h]
  char v29[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v30[3]; // [rsp+44h] [rbp-BCh] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v32; // [rsp+58h] [rbp-A8h]
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  char v34; // [rsp+68h] [rbp-98h]
  _QWORD v35[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-50h]
  __int64 v40; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v41[5]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v42[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v43; // [rsp+130h] [rbp+30h]
  __int64 v44; // [rsp+140h] [rbp+40h]
  int v45; // [rsp+148h] [rbp+48h]
  int v46; // [rsp+150h] [rbp+50h]
  struct CSingleIdentity **v47; // [rsp+160h] [rbp+60h]
  __int16 v48; // [rsp+170h] [rbp+70h] BYREF
  __int64 v49; // [rsp+178h] [rbp+78h]
  __int64 v50; // [rsp+180h] [rbp+80h]
  __int64 v51; // [rsp+188h] [rbp+88h]
  __int16 v52; // [rsp+190h] [rbp+90h]
  void *Block; // [rsp+198h] [rbp+98h]
  int v54; // [rsp+1A0h] [rbp+A0h]
  __int64 v55; // [rsp+1A8h] [rbp+A8h]
  int v56; // [rsp+1B0h] [rbp+B0h]
  __int128 v57; // [rsp+1B8h] [rbp+B8h]
  __int128 v58; // [rsp+1C8h] [rbp+C8h]
  __int64 v59; // [rsp+1D8h] [rbp+D8h]
  __int16 v60; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v61; // [rsp+1E8h] [rbp+E8h]
  __int64 v62; // [rsp+1F0h] [rbp+F0h]
  __int64 v63; // [rsp+1F8h] [rbp+F8h]
  __int16 v64; // [rsp+200h] [rbp+100h]
  __int64 v65; // [rsp+208h] [rbp+108h]
  int v66; // [rsp+210h] [rbp+110h]
  __int64 v67; // [rsp+218h] [rbp+118h]
  int v68; // [rsp+220h] [rbp+120h]
  __int128 v69; // [rsp+228h] [rbp+128h]
  __int128 v70; // [rsp+238h] [rbp+138h]
  __int64 v71; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v47 = a2;
  v30[0] = 0;
  v41[0] = "RequestKey";
  v41[1] = v30;
  v41[2] = 0;
  v41[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "RequestKey",
    (const char *)0x278B,
    0,
    v25);
  v8 = 0;
  while ( 1 )
  {
    v29[0] = 0;
    if ( !(unsigned int)_o__wcsicmp(a1, L"StrongCredentialKey") )
      break;
    CPPCRLBaseRequest::CPPCRLBaseRequest((CPPCRLBaseRequest *)v42);
    v42[0] = &CGetUserKeyDataRequest::`vftable';
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v71 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, struct CSingleIdentity *))(*(_QWORD *)a3 + 8LL))(a3, *a2);
    v34 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 16LL))(a3, &v33);
    v30[0] = v16;
    if ( v16 < 0 )
    {
      v22 = 10176;
LABEL_52:
      v23 = (unsigned int)v16;
      goto LABEL_53;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, struct CSingleIdentity *, _QWORD *))(*(_QWORD *)a4 + 8LL))(a4, *a2, v42);
    v16 = v19;
    v30[0] = v19;
    if ( v19 < 0 )
    {
      v22 = 10177;
LABEL_50:
      v23 = (unsigned int)v19;
LABEL_53:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        (const char *)v23,
        (int)v26);
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
      CTransport::~CTransport((CTransport *)&v60);
      CGetUserKeyDataRequest::~CGetUserKeyDataRequest((CGetUserKeyDataRequest *)v42);
      goto LABEL_54;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a4 + 16LL))(a4, v42, a1);
    v16 = v19;
    v30[0] = v19;
    if ( v19 < 0 )
    {
      v22 = 10178;
      goto LABEL_50;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a4 + 24LL))(a4, v42);
    v16 = v19;
    v30[0] = v19;
    if ( v19 < 0 )
    {
      v22 = 10179;
      goto LABEL_50;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int16 *, _QWORD *))(*(_QWORD *)a4 + 32LL))(a4, &v60, v42);
    v16 = v19;
    v30[0] = v19;
    if ( v19 < 0 )
    {
      v22 = 10180;
      goto LABEL_50;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, char *))(*(_QWORD *)a4 + 48LL))(a4, v42, ++v8, v29);
    v16 = v19;
    v30[0] = v19;
    if ( v19 < 0 )
    {
      v22 = 10181;
      goto LABEL_50;
    }
    v30[0] = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a4 + 40LL))(a4, v42);
    LODWORD(v26) = v30[0];
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x27C8u,
      L"GetUserKeyData Request result: hr = 0x%x, requestCount = %u, resendRequest = %u");
    if ( !v29[0] )
    {
      v16 = v30[0];
      if ( v30[0] < 0 )
      {
        v22 = 10187;
        goto LABEL_52;
      }
    }
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
    CTransport::~CTransport((CTransport *)&v60);
    CGetUserKeyDataRequest::~CGetUserKeyDataRequest((CGetUserKeyDataRequest *)v42);
LABEL_28:
    if ( v29[0] != 1 || v8 > 3u )
    {
      v16 = v30[0];
      if ( v30[0] < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27D0,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          (const char *)v30[0],
          (int)v26);
      goto LABEL_54;
    }
  }
  *(_QWORD *)&v30[1] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v9 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)*a2 + 8LL))(*a2);
  v10 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v40,
          L"ps:SingleUseCode");
  if ( (int)CIdentityCredentialBag::RetrieveCredential(v9, v10, &v30[1], 1) < 0
    || (v11 = *(const unsigned __int16 **)&v30[1], !*(_DWORD *)(*(_QWORD *)&v30[1] - 16LL)) )
  {
    v16 = -2138701818;
    v30[0] = -2138701818;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27B7,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      (const char *)0x80860006LL,
      (int)v26);
    goto LABEL_37;
  }
  CPPCRLBaseRequest::CPPCRLBaseRequest((CPPCRLBaseRequest *)v35);
  v35[0] = &StrongCredentialKeyDataRequest::`vftable';
  v39 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  Block = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)(*(__int64 (__fastcall **)(__int64, struct CSingleIdentity *))(*(_QWORD *)a3 + 8LL))(
                                            a3,
                                            *a2);
  v32 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, LPCRITICAL_SECTION *))(*(_QWORD *)a3 + 16LL))(a3, &lpCriticalSection);
  v13 = v12;
  v30[0] = v12;
  if ( v12 >= 0 )
  {
    v14 = CPPCRLBaseRequest::InitializeBase((CPPCRLBaseRequest *)v35, *a2);
    v13 = v14;
    v30[0] = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27A4,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        (const char *)(unsigned int)v14,
        (int)v26);
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&lpCriticalSection);
      CTransport::~CTransport((CTransport *)&v48);
      CPPCRLBaseRequest::~CPPCRLBaseRequest((CPPCRLBaseRequest *)v35);
      CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v30[1]);
      goto LABEL_39;
    }
    v15 = StrongCredentialKeyDataRequest::BuildRequest((StrongCredentialKeyDataRequest *)v35, v11);
    v16 = v15;
    v30[0] = v15;
    if ( v15 < 0 )
    {
      v21 = 10149;
LABEL_35:
      v20 = (unsigned int)v15;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        (const char *)v20,
        (int)v26);
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&lpCriticalSection);
      CTransport::~CTransport((CTransport *)&v48);
      CPPCRLBaseRequest::~CPPCRLBaseRequest((CPPCRLBaseRequest *)v35);
LABEL_37:
      CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v30[1]);
      goto LABEL_54;
    }
    v15 = CTransport::SendRequest((CTransport *)&v48, (struct CPPCRLBaseRequest *)v35, 0);
    v16 = v15;
    v30[0] = v15;
    if ( v15 < 0 )
    {
      v21 = 10150;
      goto LABEL_35;
    }
    ++v8;
    v29[0] = 0;
    v17 = v39;
    v18 = 0;
    if ( (_DWORD)v39 == -2147186596 )
    {
      if ( v8 <= 1u )
      {
        v29[0] = 1;
        v18 = 1;
      }
    }
    else if ( (_DWORD)v39 == -2147186459 )
    {
      v17 = -2138701818;
    }
    v30[0] = v17;
    LODWORD(v28) = v18;
    LODWORD(v27) = v8;
    LODWORD(v26) = v17;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x27AEu,
      L"Strong Credential GetUserKeyData Request result: hr = 0x%x, requestCount = %u, resendRequest = %u",
      v26,
      v27,
      v28);
    if ( !v29[0] )
    {
      v16 = v30[0];
      if ( v30[0] < 0 )
      {
        v20 = v30[0];
        v21 = 10161;
        goto LABEL_36;
      }
    }
    if ( v32 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v32 = 0;
    }
    CTransport::CloseAllInternet((CTransport *)&v48, 1);
    operator delete(Block);
    Block = 0;
    v35[0] = &CPPCRLBaseRequest::`vftable';
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v38);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
    CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)v36);
    CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::SetZeroMemory(&v30[1]);
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)&v30[1] - 24LL));
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x27A3,
    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    (const char *)(unsigned int)v12,
    (int)v26);
  if ( v32 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v32 = 0;
  }
  CTransport::CloseAllInternet((CTransport *)&v48, 1);
  operator delete(Block);
  Block = 0;
  v35[0] = &CPPCRLBaseRequest::`vftable';
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)v36);
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::SetZeroMemory(&v30[1]);
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)&v30[1] - 24LL));
LABEL_39:
  v16 = v13;
LABEL_54:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
  CAutoRefPtr<CSingleIdentity>::Deinit(a2);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18002d838  push    rbp
0x18002d83a  push    rbx
0x18002d83b  push    rsi
0x18002d83c  push    rdi
0x18002d83d  push    r12
0x18002d83f  push    r13
0x18002d841  push    r14
0x18002d843  push    r15
0x18002d845  lea     rbp, [rsp-168h]
0x18002d84d  sub     rsp, 268h
0x18002d854  mov     rax, cs:__security_cookie
0x18002d85b  xor     rax, rsp
0x18002d85e  mov     [rbp+1A0h+var_50], rax
0x18002d865  mov     rsi, r9
0x18002d868  mov     r12, r8
0x18002d86b  mov     r14, rdx
0x18002d86e  mov     r13, rcx
0x18002d871  mov     [rbp+1A0h+var_140], rdx
0x18002d875  xor     r15d, r15d
0x18002d878  mov     dword ptr [rsp+2A0h+var_25C], r15d
0x18002d87d  lea     rdx, aRequestkey; "RequestKey"
0x18002d884  mov     [rbp+1A0h+var_1D8], rdx
0x18002d888  lea     rax, [rsp+2A0h+var_25C]
0x18002d88d  mov     [rbp+1A0h+var_1D0], rax
0x18002d891  mov     [rbp+1A0h+var_1C8], r15
0x18002d895  mov     [rbp+1A0h+var_1C0], r15
0x18002d899  xor     r9d, r9d; unsigned int
0x18002d89c  mov     r8d, 278Bh; char *
0x18002d8a2  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002d8a9  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18002d8ae  nop
0x18002d8af  mov     edi, r15d
0x18002d8b2  mov     [rsp+2A0h+var_260], r15b
0x18002d8b7  lea     rdx, aStrongcredenti_0; "StrongCredentialKey"
0x18002d8be  mov     rcx, r13
0x18002d8c1  call    cs:__imp__o__wcsicmp
0x18002d8c7  test    eax, eax
0x18002d8c9  jnz     loc_18002DB48
0x18002d8cf  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002d8d6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002d8dd  mov     rax, [rax+18h]
0x18002d8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8e6  add     rax, 18h
0x18002d8ea  mov     qword ptr [rsp+2A0h+var_25C+4], rax
0x18002d8ef  mov     rcx, [r14]
0x18002d8f2  mov     rax, [rcx]
0x18002d8f5  mov     rax, [rax+8]
0x18002d8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8fe  mov     rbx, rax
0x18002d901  lea     rdx, aPsSingleusecod; "ps:SingleUseCode"
0x18002d908  lea     rcx, [rbp+1A0h+var_1E0]
0x18002d90c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002d911  mov     r9d, 1
0x18002d917  lea     r8, [rsp+2A0h+var_25C+4]
0x18002d91c  mov     rdx, rax
0x18002d91f  mov     rcx, rbx
0x18002d922  call    ?RetrieveCredential@CIdentityCredentialBag@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@H@Z; CIdentityCredentialBag::RetrieveCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int)
0x18002d927  test    eax, eax
0x18002d929  js      loc_18002DECA
0x18002d92f  mov     rbx, qword ptr [rsp+2A0h+var_25C+4]
0x18002d934  cmp     [rbx-10h], r15d
0x18002d938  jz      loc_18002DECA
0x18002d93e  lea     rcx, [rsp+2A0h+var_230]; this
0x18002d943  call    ??0CPPCRLBaseRequest@@QEAA@XZ; CPPCRLBaseRequest::CPPCRLBaseRequest(void)
0x18002d948  lea     rax, ??_7StrongCredentialKeyDataRequest@@6B@; const StrongCredentialKeyDataRequest::`vftable'
0x18002d94f  mov     [rsp+2A0h+var_230], rax
0x18002d954  mov     [rbp+1A0h+var_1F0], 0
0x18002d95c  mov     [rbp+1A0h+var_130], 0
0x18002d962  mov     [rbp+1A0h+var_128], r15
0x18002d966  mov     [rbp+1A0h+var_120], r15
0x18002d96d  mov     [rbp+1A0h+var_118], 0
0x18002d978  mov     [rbp+1A0h+var_110], r15w
0x18002d980  mov     [rbp+1A0h+Block], r15
0x18002d987  mov     [rbp+1A0h+var_100], r15d
0x18002d98e  mov     [rbp+1A0h+var_F8], r15
0x18002d995  mov     [rbp+1A0h+var_F0], r15d
0x18002d99c  xorps   xmm0, xmm0
0x18002d99f  xor     eax, eax
0x18002d9a1  movups  [rbp+1A0h+var_E8], xmm0
0x18002d9a8  movups  [rbp+1A0h+var_D8], xmm0
0x18002d9af  mov     [rbp+1A0h+var_C8], rax
0x18002d9b6  mov     rax, [r12]
0x18002d9ba  mov     rdx, [r14]
0x18002d9bd  mov     rcx, r12
0x18002d9c0  mov     rax, [rax+8]
0x18002d9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9c9  mov     [rsp+2A0h+lpCriticalSection], rax
0x18002d9ce  mov     [rsp+2A0h+var_248], r15b
0x18002d9d3  mov     rax, [r12]
0x18002d9d7  lea     rdx, [rsp+2A0h+lpCriticalSection]
0x18002d9dc  mov     rcx, r12
0x18002d9df  mov     rax, [rax+10h]
0x18002d9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9e8  mov     r15d, eax
0x18002d9eb  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002d9ef  test    eax, eax
0x18002d9f1  js      loc_18002DE33
0x18002d9f7  mov     rdx, [r14]; struct CSingleIdentity *
0x18002d9fa  lea     rcx, [rsp+2A0h+var_230]; this
0x18002d9ff  call    ?InitializeBase@CPPCRLBaseRequest@@QEAAJPEAVCSingleIdentity@@@Z; CPPCRLBaseRequest::InitializeBase(CSingleIdentity *)
0x18002da04  mov     r15d, eax
0x18002da07  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002da0b  test    eax, eax
0x18002da0d  js      loc_18002DDE5
0x18002da13  mov     rdx, rbx; unsigned __int16 *
0x18002da16  lea     rcx, [rsp+2A0h+var_230]; this
0x18002da1b  call    ?BuildRequest@StrongCredentialKeyDataRequest@@QEAAJPEBG@Z; StrongCredentialKeyDataRequest::BuildRequest(ushort const *)
0x18002da20  mov     ebx, eax
0x18002da22  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002da26  xor     r15d, r15d
0x18002da29  test    eax, eax
0x18002da2b  js      loc_18002DD9A
0x18002da31  xor     r8d, r8d; bool
0x18002da34  lea     rdx, [rsp+2A0h+var_230]; struct CPPCRLBaseRequest *
0x18002da39  lea     rcx, [rbp+1A0h+var_130]; this
0x18002da3d  call    ?SendRequest@CTransport@@QEAAJPEAVCPPCRLBaseRequest@@_N@Z; CTransport::SendRequest(CPPCRLBaseRequest *,bool)
0x18002da42  mov     ebx, eax
0x18002da44  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002da48  test    eax, eax
0x18002da4a  js      loc_18002DD93
0x18002da50  lea     ebx, [r15+1]
0x18002da54  add     di, bx
0x18002da57  mov     [rsp+2A0h+var_260], r15b
0x18002da5c  mov     ecx, dword ptr [rbp+1A0h+var_1F0]
0x18002da5f  mov     edx, r15d
0x18002da62  cmp     ecx, 8004885Ch
0x18002da68  jnz     short loc_18002DA77
0x18002da6a  cmp     di, bx
0x18002da6d  ja      short loc_18002DA84
0x18002da6f  mov     [rsp+2A0h+var_260], bl
0x18002da73  mov     edx, ebx
0x18002da75  jmp     short loc_18002DA84
0x18002da77  cmp     ecx, 800488E5h
0x18002da7d  jnz     short loc_18002DA84
0x18002da7f  mov     ecx, 80860006h
0x18002da84  mov     dword ptr [rsp+2A0h+var_25C], ecx
0x18002da88  movzx   eax, di
0x18002da8b  mov     [rsp+2A0h+var_270], edx
0x18002da8f  mov     dword ptr [rsp+2A0h+var_278], eax
0x18002da93  mov     dword ptr [rsp+2A0h+var_280], ecx
0x18002da97  lea     r9, aStrongCredenti; "Strong Credential GetUserKeyData Reques"...
0x18002da9e  mov     r8d, 27AEh; unsigned int
0x18002daa4  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002daab  mov     ecx, 5; unsigned __int8
0x18002dab0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002dab5  cmp     [rsp+2A0h+var_260], r15b
0x18002daba  jnz     short loc_18002DACD
0x18002dabc  mov     ebx, dword ptr [rsp+2A0h+var_25C]
0x18002dac0  test    ebx, ebx
0x18002dac2  js      loc_18002DD89
0x18002dac8  mov     ebx, 1
0x18002dacd  cmp     [rsp+2A0h+var_248], r15b
0x18002dad2  jz      short loc_18002DAE4
0x18002dad4  mov     rcx, [rsp+2A0h+lpCriticalSection]; lpCriticalSection
0x18002dad9  call    cs:__imp_LeaveCriticalSection
0x18002dadf  mov     [rsp+2A0h+var_248], r15b
0x18002dae4  mov     dl, bl; bool
0x18002dae6  lea     rcx, [rbp+1A0h+var_130]; this
0x18002daea  call    ?CloseAllInternet@CTransport@@AEAAJ_N@Z; CTransport::CloseAllInternet(bool)
0x18002daef  mov     rcx, [rbp+1A0h+Block]; Block
0x18002daf6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002dafb  mov     [rbp+1A0h+Block], r15
0x18002db02  lea     rax, ??_7CPPCRLBaseRequest@@6B@; const CPPCRLBaseRequest::`vftable'
0x18002db09  mov     [rsp+2A0h+var_230], rax
0x18002db0e  lea     rcx, [rbp+1A0h+var_200]
0x18002db12  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002db17  lea     rcx, [rbp+1A0h+var_208]
0x18002db1b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002db20  lea     rcx, [rbp+1A0h+var_210]
0x18002db24  call    ??1?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002db29  nop
0x18002db2a  lea     rcx, [rsp+2A0h+var_25C+4]
0x18002db2f  call    ?SetZeroMemory@?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@QEAAXXZ; CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::SetZeroMemory(void)
0x18002db34  mov     rcx, qword ptr [rsp+2A0h+var_25C+4]
0x18002db39  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002db3d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002db42  nop
0x18002db43  jmp     loc_18002DD4D
0x18002db48  lea     rcx, [rbp+1A0h+var_1B0]; this
0x18002db4c  call    ??0CPPCRLBaseRequest@@QEAA@XZ; CPPCRLBaseRequest::CPPCRLBaseRequest(void)
0x18002db51  lea     rax, ??_7CGetUserKeyDataRequest@@6B@; const CGetUserKeyDataRequest::`vftable'
0x18002db58  mov     [rbp+1A0h+var_1B0], rax
0x18002db5c  xorps   xmm0, xmm0
0x18002db5f  movdqa  [rbp+1A0h+var_170], xmm0
0x18002db64  mov     [rbp+1A0h+var_160], r15
0x18002db68  mov     [rbp+1A0h+var_158], r15d
0x18002db6c  mov     [rbp+1A0h+var_150], r15d
0x18002db70  mov     [rbp+1A0h+var_C0], 0
0x18002db79  mov     [rbp+1A0h+var_B8], r15
0x18002db80  mov     [rbp+1A0h+var_B0], r15
0x18002db87  mov     [rbp+1A0h+var_A8], 0
0x18002db92  mov     [rbp+1A0h+var_A0], r15w
0x18002db9a  mov     [rbp+1A0h+var_98], r15
0x18002dba1  mov     [rbp+1A0h+var_90], r15d
0x18002dba8  mov     [rbp+1A0h+var_88], r15
0x18002dbaf  mov     [rbp+1A0h+var_80], r15d
0x18002dbb6  xor     eax, eax
0x18002dbb8  movups  [rbp+1A0h+var_78], xmm0
0x18002dbbf  movups  [rbp+1A0h+var_68], xmm0
0x18002dbc6  mov     [rbp+1A0h+var_58], rax
0x18002dbcd  mov     rax, [r12]
0x18002dbd1  mov     rdx, [r14]
0x18002dbd4  mov     rcx, r12
0x18002dbd7  mov     rax, [rax+8]
0x18002dbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbe0  mov     [rsp+2A0h+var_240], rax
0x18002dbe5  mov     [rsp+2A0h+var_238], r15b
0x18002dbea  mov     rax, [r12]
0x18002dbee  lea     rdx, [rsp+2A0h+var_240]
0x18002dbf3  mov     rcx, r12
0x18002dbf6  mov     rax, [rax+10h]
0x18002dbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbff  mov     ebx, eax
0x18002dc01  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002dc05  test    eax, eax
0x18002dc07  js      loc_18002DF20
0x18002dc0d  mov     rax, [rsi]
0x18002dc10  lea     r8, [rbp+1A0h+var_1B0]
0x18002dc14  mov     rdx, [r14]
0x18002dc17  mov     rcx, rsi
0x18002dc1a  mov     rax, [rax+8]
0x18002dc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc23  mov     ebx, eax
0x18002dc25  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002dc29  test    eax, eax
0x18002dc2b  js      loc_18002DF16
0x18002dc31  mov     rax, [rsi]
0x18002dc34  mov     r8, r13
0x18002dc37  lea     rdx, [rbp+1A0h+var_1B0]
0x18002dc3b  mov     rcx, rsi
0x18002dc3e  mov     rax, [rax+10h]
0x18002dc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc47  mov     ebx, eax
0x18002dc49  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002dc4d  test    eax, eax
0x18002dc4f  js      loc_18002DF0F
0x18002dc55  mov     rax, [rsi]
0x18002dc58  lea     rdx, [rbp+1A0h+var_1B0]
0x18002dc5c  mov     rcx, rsi
0x18002dc5f  mov     rax, [rax+18h]
0x18002dc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc68  mov     ebx, eax
0x18002dc6a  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002dc6e  test    eax, eax
0x18002dc70  js      loc_18002DF08
0x18002dc76  mov     rax, [rsi]
0x18002dc79  lea     r8, [rbp+1A0h+var_1B0]
0x18002dc7d  lea     rdx, [rbp+1A0h+var_C0]
0x18002dc84  mov     rcx, rsi
0x18002dc87  mov     rax, [rax+20h]
0x18002dc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc90  mov     ebx, eax
0x18002dc92  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002dc96  test    eax, eax
0x18002dc98  js      loc_18002DF01
0x18002dc9e  inc     di
0x18002dca1  mov     rax, [rsi]
0x18002dca4  lea     r9, [rsp+2A0h+var_260]
0x18002dca9  movzx   r8d, di
0x18002dcad  lea     rdx, [rbp+1A0h+var_1B0]
0x18002dcb1  mov     rcx, rsi
0x18002dcb4  mov     rax, [rax+30h]
0x18002dcb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcbd  mov     ebx, eax
0x18002dcbf  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002dcc3  test    eax, eax
0x18002dcc5  js      loc_18002DEFA
0x18002dccb  mov     rax, [rsi]
0x18002dcce  lea     rdx, [rbp+1A0h+var_1B0]
0x18002dcd2  mov     rcx, rsi
0x18002dcd5  mov     rax, [rax+28h]
0x18002dcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcde  mov     dword ptr [rsp+2A0h+var_25C], eax
0x18002dce2  movzx   ecx, [rsp+2A0h+var_260]
0x18002dce7  movzx   edx, di
0x18002dcea  mov     [rsp+2A0h+var_270], ecx
0x18002dcee  mov     dword ptr [rsp+2A0h+var_278], edx
0x18002dcf2  mov     dword ptr [rsp+2A0h+var_280], eax; int
0x18002dcf6  lea     r9, aGetuserkeydata_0; "GetUserKeyData Request result: hr = 0x%"...
0x18002dcfd  mov     r8d, 27C8h; unsigned int
0x18002dd03  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002dd0a  mov     ecx, 5; unsigned __int8
0x18002dd0f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002dd14  cmp     [rsp+2A0h+var_260], r15b
0x18002dd19  jnz     short loc_18002DD27
0x18002dd1b  mov     ebx, dword ptr [rsp+2A0h+var_25C]
0x18002dd1f  test    ebx, ebx
0x18002dd21  js      loc_18002DEF3
0x18002dd27  lea     rcx, [rsp+2A0h+var_240]
0x18002dd2c  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18002dd31  nop
0x18002dd32  lea     rcx, [rbp+1A0h+var_C0]; this
0x18002dd39  call    ??1CTransport@@QEAA@XZ; CTransport::~CTransport(void)
0x18002dd3e  nop
0x18002dd3f  lea     rcx, [rbp+1A0h+var_1B0]; this
0x18002dd43  call    ??1CGetUserKeyDataRequest@@UEAA@XZ; CGetUserKeyDataRequest::~CGetUserKeyDataRequest(void)
0x18002dd48  mov     ebx, 1
0x18002dd4d  cmp     [rsp+2A0h+var_260], bl
0x18002dd51  jnz     short loc_18002DD5D
0x18002dd53  cmp     di, 3
  ... truncated ...
```
