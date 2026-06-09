# CClientSingleIdentity::AcquireTokenFromSvc(void *)

- ea: `0x18001ca08`
- end: `0x18001d0e3`
- name: `?AcquireTokenFromSvc@CClientSingleIdentity@@QEAAJPEAX@Z`
- size: `1755`
- prototype: `__int64 __fastcall(CClientSingleIdentity *__hidden this, void *)`
- caller_count: `3`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d0f0`
- `0x18001d458`
- `0x18001e664`

## callees

- `0x180003298`
- `0x18000a870`
- `0x18000b0bc`
- `0x18000ba8c`
- `0x18000cc48`
- `0x18000cc9c`
- `0x18000e870`
- `0x18000e9a4`
- `0x1800104dc`
- `0x180010eec`
- `0x1800114b0`
- `0x180012998`
- `0x18001c3c0`
- `0x18001c46c`
- `0x18001c550`
- `0x18001c6ec`
- `0x18001c87c`
- `0x18001ca08`
- `0x18001d720`
- `0x18001dd50`
- `0x18001e2f0`
- `0x18001eb78`
- `0x18001f920`
- `0x18001f980`
- `0x180020848`
- `0x1800378a8`
- `0x180046f0c`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d028`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d028`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001d097`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001d097`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001cba4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001cba4`

## string_xrefs

- `0x18001ca3b`: `CClientSingleIdentity::AcquireTokenFromSvc`
- `0x18001cd51`: `GetServiceToken on DA ticket failed (0x%x).`
- `0x18001d065`: `No token bag for identity.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CClientSingleIdentity::AcquireTokenFromSvc(CClientSingleIdentity *this, void *a2)
{
  void *v2; // rdi
  CClientSingleIdentity *v3; // r13
  __int64 v4; // rcx
  void *v5; // r14
  unsigned int v6; // r15d
  unsigned __int64 v7; // r12
  void **v8; // rbx
  int v9; // edx
  void *v10; // rcx
  int v11; // ebx
  int v12; // r8d
  int v13; // ebx
  int v14; // r8d
  int v15; // eax
  __int64 v16; // rax
  int ServiceToken; // eax
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // r12d
  __int64 v21; // rbx
  HINSTANCE v22; // r15
  int v23; // r14d
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rsi
  _QWORD *v27; // rax
  int v28; // eax
  int v29; // r12d
  int v30; // r13d
  int v31; // r15d
  __int64 v32; // rdx
  __int64 v33; // r14
  const WCHAR *v34; // rdx
  __int64 v35; // rsi
  int v36; // edi
  int v37; // ebx
  _QWORD *v38; // rax
  int v39; // eax
  __int64 *v40; // rax
  _QWORD *v41; // rax
  int v42; // ebx
  bool v43; // dl
  bool v44; // cl
  unsigned int v45; // ebx
  unsigned __int16 *v47; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v48; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v49; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v50; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v51; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v52; // [rsp+20h] [rbp-E0h]
  int *v53; // [rsp+28h] [rbp-D8h]
  int *v54; // [rsp+28h] [rbp-D8h]
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  MsaTracingInternal *v56; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+84h] [rbp-7Ch] BYREF
  int v59; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v60; // [rsp+8Ch] [rbp-74h]
  __int64 v61; // [rsp+90h] [rbp-70h]
  void **v62; // [rsp+98h] [rbp-68h] BYREF
  struct _WLIDRequestParams *v63[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v64; // [rsp+B8h] [rbp-48h]
  int v65; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+D0h] [rbp-30h]
  char v68[8]; // [rsp+D8h] [rbp-28h] BYREF
  char v69[8]; // [rsp+E0h] [rbp-20h] BYREF
  char v70[8]; // [rsp+E8h] [rbp-18h] BYREF
  char v71[8]; // [rsp+F0h] [rbp-10h] BYREF
  char v72[8]; // [rsp+F8h] [rbp-8h] BYREF
  char v73[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v74; // [rsp+108h] [rbp+8h] BYREF
  __int64 v75; // [rsp+110h] [rbp+10h] BYREF
  __int64 v76; // [rsp+118h] [rbp+18h]
  _QWORD v77[3]; // [rsp+120h] [rbp+20h] BYREF
  int v78; // [rsp+138h] [rbp+38h]
  _QWORD v79[10]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v80[240]; // [rsp+190h] [rbp+90h] BYREF
  int v83; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v84; // [rsp+2A8h] [rbp+1A8h] BYREF

  v2 = a2;
  v3 = this;
  v83 = 0;
  v79[0] = "CClientSingleIdentity::AcquireTokenFromSvc";
  v79[1] = &v83;
  v79[2] = 0;
  v79[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
    "CClientSingleIdentity::AcquireTokenFromSvc",
    (const char *)0x1A3,
    0,
    v47);
  memset(v63, 0, sizeof(v63));
  v64 = 0;
  Block = 0;
  memset(v77, 0, sizeof(v77));
  v78 = 0;
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)v80);
  v59 = 0;
  v56 = (MsaTracingInternal *)*((_QWORD *)v3 + 64);
  v57 = 0;
  v58 = 0;
  v84 = 0;
  v83 = ConstructRequest(v4, v2, v63, v77);
  if ( v83 >= 0 )
  {
    v5 = (void *)*((_QWORD *)v3 + 73);
    v6 = *((_DWORD *)v2 + 2);
    v7 = *((_QWORD *)v2 + 4);
    v8 = (void **)*((_QWORD *)v3 + 8);
    if ( !v8 )
    {
      v8 = (void **)operator new(0x28u);
      v62 = v8;
      v8[1] = 0;
      *((_DWORD *)v8 + 6) = 1;
      *v8 = &SmartWLIDHandle::`vftable'{for `SmartObj<void *>'};
      v8[2] = &SmartWLIDHandle::`vftable'{for `CRefCounted'};
      v8[4] = 0;
      CAutoRefPtr<SmartWLIDHandle>::Deinit((char *)v3 + 64);
      *((_QWORD *)v3 + 8) = v8;
    }
    v9 = WLIDCAcquireTokens(
           v8[1],
           v7,
           v6,
           v63[0],
           &v57,
           &v58,
           &v84,
           (struct _WLIDResponseParams **)&Block,
           &v59,
           v5,
           v56 != 0);
    v83 = v9;
    v10 = (void *)*((_QWORD *)v3 + 73);
    if ( v10 )
    {
      ResetEvent(v10);
      v9 = v83;
    }
    if ( v9 >= 0 )
    {
      *((_DWORD *)g_pPPCRL + 229) = v59;
      LODWORD(v48) = v57;
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
        0x1DAu,
        L"hrAuthState (0x%x).",
        v48);
      LODWORD(v49) = v58;
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
        0x1DBu,
        L"hrAuthRequired (0x%x).",
        v49);
      LODWORD(v50) = v84;
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
        0x1DCu,
        L"hrRequestStatus (0x%x).",
        v50);
      v11 = v57;
      LODWORD(v53) = v57;
      CTraceFuncVoidW::CTraceFuncVoidW(
        (CTraceFuncVoidW *)&v56,
        "clientcore\\ds\\ext\\Live\\identity\\api\\classic\\idcrlcredstore.h",
        0x91u,
        "CClientSingleIdentity::SetAuthenticationState",
        L"hrAuthState = 0x%x",
        v53);
      *((_DWORD *)v3 + 42) = v11;
      MsaTracingInternal::TraceFunctionExit(v56, 0, v12);
      v13 = v58;
      LODWORD(v54) = v58;
      CTraceFuncVoidW::CTraceFuncVoidW(
        (CTraceFuncVoidW *)&v56,
        "clientcore\\ds\\ext\\Live\\identity\\api\\classic\\idcrlcredstore.h",
        0x97u,
        "CClientSingleIdentity::SetAuthenticationRequired",
        L"hrAuthRequired = 0x%x",
        v54);
      *((_DWORD *)v3 + 43) = v13;
      MsaTracingInternal::TraceFunctionExit(v56, 0, v14);
      CClientSingleIdentity::SetRequestStatus(v3, v84);
      v15 = *((_DWORD *)v2 + 2);
      if ( v15 )
      {
        v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)&v56,
                *((_QWORD *)Block + 17 * (unsigned int)(v15 - 1) + 7));
        CClientSingleIdentity::SetAuthWebFlowURL(v3, v16);
      }
      ServiceToken = CClientSingleIdentity::GetServiceToken(
                       v3,
                       L"http://Passport.NET/tb",
                       (struct CPPCRLToken *)v80,
                       1,
                       0);
      v83 = ServiceToken;
      if ( ServiceToken < 0 )
      {
        LODWORD(v51) = ServiceToken;
        TracePrintW(
          2u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
          0x1EEu,
          L"GetServiceToken on DA ticket failed (0x%x).",
          v51);
        v83 = 0;
      }
      v18 = CClientSingleIdentity::SetSessionCookiesFromExtProperties(v3);
      v83 = v18;
      if ( v18 < 0 )
      {
        LODWORD(v51) = v18;
        TracePrintW(
          2u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
          0x1F5u,
          L"SetSessionCookiesFromExtProperties failed (0x%x).",
          v51);
        v83 = 0;
      }
      v19 = 0;
      while ( 1 )
      {
        v60 = v19;
        if ( v19 >= *((_DWORD *)v2 + 2) )
          break;
        v20 = v19;
        v56 = (MsaTracingInternal *)v19;
        v21 = 136LL * v19;
        v61 = v21;
        if ( *(_DWORD *)((char *)Block + v21 + 32) == 2 )
        {
          v22 = g_pPPCRL;
          v23 = *(_DWORD *)(ATL::CAtlArray<_WLIDRequestParams,ATL::CElementTraits<_WLIDRequestParams>>::operator[](
                              v63,
                              v19)
                          + 24);
          v24 = *(_QWORD *)((char *)Block + v21 + 88);
          v25 = *(_QWORD *)((char *)Block + v21 + 104);
          v26 = *(_QWORD *)((char *)Block + v61 + 40);
          v27 = (_QWORD *)ATL::CAtlArray<_WLIDRequestParams,ATL::CElementTraits<_WLIDRequestParams>>::operator[](
                            v63,
                            v20);
          v28 = CClientCertManager::PutCertWithKey(v22 + 162, v3, *v27, v26, v25, v24, v23);
          v83 = v28;
          if ( v28 < 0 )
          {
            LODWORD(v52) = v28;
            TracePrintW(
              2u,
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
              0x206u,
              L"PutCert failed (0x%x).",
              v52);
            CClientSingleIdentity::SetRequestStatus(v3, -2147186452);
            v83 = 0;
          }
          v21 = v61;
        }
        if ( !*((_QWORD *)v3 + 9) )
        {
          TracePrintW(
            2u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
            0x225u,
            L"No token bag for identity.");
          v83 = -2147188685;
          break;
        }
        v66 = 0;
        v65 = 0;
        v67 = 0;
        CBytePtr::Attach(
          (CBytePtr *)&v65,
          *(unsigned __int8 **)((char *)Block + v21 + 16),
          *(_DWORD *)((char *)Block + v21 + 8),
          0);
        v76 = *((_QWORD *)v3 + 9);
        v79[4] = v68;
        v61 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v68,
                *(_QWORD *)((char *)Block + v21 + 56));
        v29 = *(_DWORD *)((char *)Block + v21 + 4);
        v30 = *(_DWORD *)((char *)Block + v21);
        v31 = IDCRLTokenType(*(unsigned int *)((char *)Block + v21 + 32));
        v74 = *(_QWORD *)(v21 + v32 + 104);
        v75 = *(_QWORD *)(v21 + v32 + 96);
        v79[5] = v69;
        v33 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v69,
                *(_QWORD *)(v21 + v32 + 80));
        v79[6] = v70;
        v34 = &String;
        if ( *(_QWORD *)((char *)Block + v21 + 48) )
          v34 = *(const WCHAR **)((char *)Block + v21 + 48);
        v35 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v70,
                (__int64)v34);
        v79[7] = v71;
        v36 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v71,
                (__int64)&String);
        v79[8] = v72;
        v37 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)v72,
                *(_QWORD *)((char *)Block + v21 + 40));
        v38 = (_QWORD *)ATL::CAtlArray<_WLIDRequestParams,ATL::CElementTraits<_WLIDRequestParams>>::operator[](v63, v56);
        v39 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                v73,
                *v38);
        v83 = CClientIdentityTokenBag::StoreToken(
                v76,
                v39,
                v37,
                v36,
                v35,
                v33,
                (__int64)&v75,
                (__int64)&v74,
                (__int64)&v65,
                v31,
                v30,
                v29,
                v61);
        if ( v83 < 0 )
        {
          CBytePtr::Empty((CBytePtr *)&v65);
          break;
        }
        CBytePtr::Empty((CBytePtr *)&v65);
        v40 = (__int64 *)ATL::CAtlArray<_WLIDRequestParams,ATL::CElementTraits<_WLIDRequestParams>>::operator[](
                           v63,
                           v56);
        v41 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                          (__int64)&v62,
                          *v40);
        v42 = _o__wcsicmp(*v41, L"http://Passport.NET/tb");
        ATL::CStringData::Release((ATL::CStringData *)(v62 - 3));
        if ( !v42 )
          SetPrefBinCookieAsync(v44, v43);
        v19 = v60 + 1;
        v3 = this;
        v2 = a2;
      }
    }
    else
    {
      if ( v9 == -2147023673 )
      {
        v9 = -2147186462;
        v83 = -2147186462;
      }
      if ( v84 < 0 )
        v9 = v84;
      CClientSingleIdentity::SetRequestStatus(v3, v9);
    }
  }
  if ( Block )
    free(Block);
  v45 = v83;
  CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v80);
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(v77);
  ATL::CAtlArray<IDCRL::_IDCRLCertInfo,ATL::CElementTraits<IDCRL::_IDCRLCertInfo>>::~CAtlArray<IDCRL::_IDCRLCertInfo,ATL::CElementTraits<IDCRL::_IDCRLCertInfo>>(v63);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v79);
  return v45;
}

```

## disassembly

```asm
0x18001ca08  mov     [rsp-8+arg_8], rdx
0x18001ca0d  mov     [rsp-8+arg_0], rcx
0x18001ca12  push    rbp
0x18001ca13  push    rbx
0x18001ca14  push    rsi
0x18001ca15  push    rdi
0x18001ca16  push    r12
0x18001ca18  push    r13
0x18001ca1a  push    r14
0x18001ca1c  push    r15
0x18001ca1e  lea     rbp, [rsp-148h]
0x18001ca26  sub     rsp, 248h
0x18001ca2d  mov     rdi, rdx
0x18001ca30  mov     r13, rcx
0x18001ca33  xor     esi, esi
0x18001ca35  mov     [rbp+180h+arg_10], esi
0x18001ca3b  lea     rdx, aCclientsinglei_1; "CClientSingleIdentity::AcquireTokenFrom"...
0x18001ca42  mov     [rbp+180h+var_140], rdx
0x18001ca46  lea     rax, [rbp+180h+arg_10]
0x18001ca4d  mov     [rbp+180h+var_138], rax
0x18001ca51  mov     [rbp+180h+var_130], rsi
0x18001ca55  mov     [rbp+180h+var_128], rsi
0x18001ca59  xor     r9d, r9d; unsigned int
0x18001ca5c  mov     r8d, 1A3h; char *
0x18001ca62  lea     rcx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001ca69  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001ca6e  nop
0x18001ca6f  mov     [rbp+180h+var_1E0], rsi
0x18001ca73  mov     [rbp+180h+var_1D8], rsi
0x18001ca77  mov     [rbp+180h+var_1D0], rsi
0x18001ca7b  mov     [rbp+180h+var_1C8], esi
0x18001ca7e  mov     [rsp+280h+Block], rsi
0x18001ca83  mov     [rbp+180h+var_160], rsi
0x18001ca87  mov     [rbp+180h+var_158], rsi
0x18001ca8b  mov     [rbp+180h+var_150], rsi
0x18001ca8f  mov     [rbp+180h+var_148], esi
0x18001ca92  lea     rcx, [rbp+180h+var_F0]; this
0x18001ca99  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x18001ca9e  nop
0x18001ca9f  mov     [rbp+180h+var_1F8], esi
0x18001caa2  mov     rax, [r13+200h]
0x18001caa9  mov     [rsp+280h+var_208], rax
0x18001caae  mov     [rbp+180h+var_200], esi
0x18001cab1  mov     [rbp+180h+var_1FC], esi
0x18001cab4  mov     [rbp+180h+arg_18], esi
0x18001caba  lea     r9, [rbp+180h+var_160]
0x18001cabe  lea     r8, [rbp+180h+var_1E0]
0x18001cac2  mov     rdx, rdi
0x18001cac5  call    ?ConstructRequest@@YAJPEAVCClientSingleIdentity@@PEAU_AcquireTokenParam@@AEAV?$CAtlArray@U_WLIDRequestParams@@V?$CElementTraits@U_WLIDRequestParams@@@ATL@@@ATL@@AEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@4@@Z; ConstructRequest(CClientSingleIdentity *,_AcquireTokenParam *,ATL::CAtlArray<_WLIDRequestParams,ATL::CElementTraits<_WLIDRequestParams>> &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18001caca  mov     [rbp+180h+arg_10], eax
0x18001cad0  test    eax, eax
0x18001cad2  js      loc_18001D08D
0x18001cad8  mov     r14, [r13+248h]
0x18001cadf  mov     r15d, [rdi+8]
0x18001cae3  mov     r12, [rdi+20h]
0x18001cae7  lea     rsi, [r13+40h]
0x18001caeb  mov     rbx, [rsi]
0x18001caee  test    rbx, rbx
0x18001caf1  jnz     short loc_18001CB37
0x18001caf3  lea     ecx, [rbx+28h]; Size
0x18001caf6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cafb  mov     rbx, rax
0x18001cafe  mov     [rbp+180h+var_1E8], rax
0x18001cb02  xor     eax, eax
0x18001cb04  mov     [rbx+8], rax
0x18001cb08  mov     dword ptr [rbx+18h], 1
0x18001cb0f  lea     rax, ??_7SmartWLIDHandle@@6B?$SmartObj@PEAX@@@; const SmartWLIDHandle::`vftable'{for `SmartObj<void *>'}
0x18001cb16  mov     [rbx], rax
0x18001cb19  lea     rax, ??_7SmartWLIDHandle@@6BCRefCounted@@@; const SmartWLIDHandle::`vftable'{for `CRefCounted'}
0x18001cb20  mov     [rbx+10h], rax
0x18001cb24  mov     qword ptr [rbx+20h], 0
0x18001cb2c  mov     rcx, rsi
0x18001cb2f  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18001cb34  mov     [rsi], rbx
0x18001cb37  xor     esi, esi
0x18001cb39  mov     eax, esi
0x18001cb3b  cmp     [rsp+280h+var_208], rsi
0x18001cb40  setnz   al
0x18001cb43  mov     [rsp+280h+var_230], eax; int
0x18001cb47  mov     [rsp+280h+var_238], r14; void *
0x18001cb4c  lea     rax, [rbp+180h+var_1F8]
0x18001cb50  mov     [rsp+280h+var_240], rax; int *
0x18001cb55  lea     rax, [rsp+280h+Block]
0x18001cb5a  mov     [rsp+280h+var_248], rax; struct _WLIDResponseParams **
0x18001cb5f  lea     rax, [rbp+180h+arg_18]
0x18001cb66  mov     [rsp+280h+var_250], rax; int *
0x18001cb6b  lea     rax, [rbp+180h+var_1FC]
0x18001cb6f  mov     [rsp+280h+var_258], rax; int *
0x18001cb74  lea     rax, [rbp+180h+var_200]
0x18001cb78  mov     [rsp+280h+var_260], rax; int *
0x18001cb7d  mov     r9, [rbp+180h+var_1E0]; struct _WLIDRequestParams *
0x18001cb81  mov     r8d, r15d; unsigned int
0x18001cb84  mov     rdx, r12; unsigned __int64
0x18001cb87  mov     rcx, [rbx+8]; void *
0x18001cb8b  call    ?WLIDCAcquireTokens@@YAJQEAX_KKQEAU_WLIDRequestParams@@PEAJ33PEAPEAU_WLIDResponseParams@@3PEAXH@Z; WLIDCAcquireTokens(void * const,unsigned __int64,ulong,_WLIDRequestParams * const,long *,long *,long *,_WLIDResponseParams * *,long *,void *,int)
0x18001cb90  mov     edx, eax
0x18001cb92  mov     [rbp+180h+arg_10], eax
0x18001cb98  mov     rcx, [r13+248h]; hEvent
0x18001cb9f  test    rcx, rcx
0x18001cba2  jz      short loc_18001CBB0
0x18001cba4  call    cs:__imp_ResetEvent
0x18001cbaa  mov     edx, [rbp+180h+arg_10]
0x18001cbb0  test    edx, edx
0x18001cbb2  jns     short loc_18001CBDF
0x18001cbb4  cmp     edx, 800704C7h
0x18001cbba  jnz     short loc_18001CBC7
0x18001cbbc  mov     edx, 800488E2h
0x18001cbc1  mov     [rbp+180h+arg_10], edx
0x18001cbc7  mov     eax, [rbp+180h+arg_18]
0x18001cbcd  test    eax, eax
0x18001cbcf  cmovs   edx, eax; int
0x18001cbd2  mov     rcx, r13; this
0x18001cbd5  call    ?SetRequestStatus@CClientSingleIdentity@@QEAAXJ@Z; CClientSingleIdentity::SetRequestStatus(long)
0x18001cbda  jmp     loc_18001D08D
0x18001cbdf  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x18001cbe6  mov     eax, [rbp+180h+var_1F8]
0x18001cbe9  mov     [rcx+394h], eax
0x18001cbef  mov     eax, [rbp+180h+var_200]
0x18001cbf2  mov     dword ptr [rsp+280h+var_260], eax
0x18001cbf6  lea     r9, aHrauthstate0xX; "hrAuthState (0x%x)."
0x18001cbfd  mov     r8d, 1DAh; unsigned int
0x18001cc03  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001cc0a  mov     ebx, 5
0x18001cc0f  mov     ecx, ebx; unsigned __int8
0x18001cc11  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cc16  mov     eax, [rbp+180h+var_1FC]
0x18001cc19  mov     dword ptr [rsp+280h+var_260], eax
0x18001cc1d  lea     r9, aHrauthrequired; "hrAuthRequired (0x%x)."
0x18001cc24  mov     r8d, 1DBh; unsigned int
0x18001cc2a  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001cc31  mov     ecx, ebx; unsigned __int8
0x18001cc33  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cc38  mov     eax, [rbp+180h+arg_18]
0x18001cc3e  mov     dword ptr [rsp+280h+var_260], eax
0x18001cc42  lea     r9, aHrrequeststatu_0; "hrRequestStatus (0x%x)."
0x18001cc49  mov     r8d, 1DCh; unsigned int
0x18001cc4f  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001cc56  mov     ecx, ebx; unsigned __int8
0x18001cc58  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cc5d  mov     ebx, [rbp+180h+var_200]
0x18001cc60  mov     dword ptr [rsp+280h+var_258], ebx
0x18001cc64  lea     rax, aHrauthstate0xX_0; "hrAuthState = 0x%x"
0x18001cc6b  mov     [rsp+280h+var_260], rax; unsigned __int16 *
0x18001cc70  lea     r9, aCclientsinglei_9; "CClientSingleIdentity::SetAuthenticatio"...
0x18001cc77  mov     r8d, 91h; unsigned int
0x18001cc7d  lea     rdx, aClientcoreDsEx_21; "clientcore\\ds\\ext\\Live\\identity\\ap"...
0x18001cc84  lea     rcx, [rsp+280h+var_208]; this
0x18001cc89  call    ??0CTraceFuncVoidW@@QEAA@PEBDK0PEBGZZ; CTraceFuncVoidW::CTraceFuncVoidW(char const *,ulong,char const *,ushort const *,...)
0x18001cc8e  mov     [r13+0A8h], ebx
0x18001cc95  xor     edx, edx; char *
0x18001cc97  mov     rcx, [rsp+280h+var_208]; this
0x18001cc9c  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18001cca1  mov     ebx, [rbp+180h+var_1FC]
0x18001cca4  mov     dword ptr [rsp+280h+var_258], ebx
0x18001cca8  lea     rax, aHrauthrequired_0; "hrAuthRequired = 0x%x"
0x18001ccaf  mov     [rsp+280h+var_260], rax; unsigned __int16 *
0x18001ccb4  lea     r9, aCclientsinglei_7; "CClientSingleIdentity::SetAuthenticatio"...
0x18001ccbb  mov     r8d, 97h; unsigned int
0x18001ccc1  lea     rdx, aClientcoreDsEx_21; "clientcore\\ds\\ext\\Live\\identity\\ap"...
0x18001ccc8  lea     rcx, [rsp+280h+var_208]; this
0x18001cccd  call    ??0CTraceFuncVoidW@@QEAA@PEBDK0PEBGZZ; CTraceFuncVoidW::CTraceFuncVoidW(char const *,ulong,char const *,ushort const *,...)
0x18001ccd2  mov     [r13+0ACh], ebx
0x18001ccd9  xor     edx, edx; char *
0x18001ccdb  mov     rcx, [rsp+280h+var_208]; this
0x18001cce0  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18001cce5  mov     edx, [rbp+180h+arg_18]; int
0x18001cceb  mov     rcx, r13; this
0x18001ccee  call    ?SetRequestStatus@CClientSingleIdentity@@QEAAXJ@Z; CClientSingleIdentity::SetRequestStatus(long)
0x18001ccf3  mov     eax, [rdi+8]
0x18001ccf6  test    eax, eax
0x18001ccf8  jz      short loc_18001CD23
0x18001ccfa  lea     ecx, [rax-1]
0x18001ccfd  imul    rax, rcx, 88h
0x18001cd04  mov     rdx, [rsp+280h+Block]
0x18001cd09  mov     rdx, [rax+rdx+38h]
0x18001cd0e  lea     rcx, [rsp+280h+var_208]
0x18001cd13  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001cd18  mov     rdx, rax
0x18001cd1b  mov     rcx, r13
0x18001cd1e  call    ?SetAuthWebFlowURL@CClientSingleIdentity@@QEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CClientSingleIdentity::SetAuthWebFlowURL(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18001cd23  mov     dword ptr [rsp+280h+var_260], esi; unsigned int
0x18001cd27  mov     r9d, 1; int
0x18001cd2d  lea     r8, [rbp+180h+var_F0]; struct CPPCRLToken *
0x18001cd34  lea     rdx, aHttpPassportNe; "http://Passport.NET/tb"
0x18001cd3b  mov     rcx, r13; this
0x18001cd3e  call    ?GetServiceToken@CClientSingleIdentity@@QEAAJPEBGAEAVCPPCRLToken@@HK@Z; CClientSingleIdentity::GetServiceToken(ushort const *,CPPCRLToken &,int,ulong)
0x18001cd43  mov     [rbp+180h+arg_10], eax
0x18001cd49  test    eax, eax
0x18001cd4b  jns     short loc_18001CD75
0x18001cd4d  mov     dword ptr [rsp+280h+var_260], eax
0x18001cd51  lea     r9, aGetservicetoke; "GetServiceToken on DA ticket failed (0x"...
0x18001cd58  mov     r8d, 1EEh; unsigned int
0x18001cd5e  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001cd65  mov     ecx, 2; unsigned __int8
0x18001cd6a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cd6f  mov     [rbp+180h+arg_10], esi
0x18001cd75  mov     rcx, r13; this
0x18001cd78  call    ?SetSessionCookiesFromExtProperties@CClientSingleIdentity@@QEAAJXZ; CClientSingleIdentity::SetSessionCookiesFromExtProperties(void)
0x18001cd7d  mov     [rbp+180h+arg_10], eax
0x18001cd83  test    eax, eax
0x18001cd85  jns     short loc_18001CDAF
0x18001cd87  mov     dword ptr [rsp+280h+var_260], eax
0x18001cd8b  lea     r9, aSetsessioncook; "SetSessionCookiesFromExtProperties fail"...
0x18001cd92  mov     r8d, 1F5h; unsigned int
0x18001cd98  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001cd9f  mov     ecx, 2; unsigned __int8
0x18001cda4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cda9  mov     [rbp+180h+arg_10], esi
0x18001cdaf  mov     eax, esi
0x18001cdb1  mov     [rbp+180h+var_1F4], eax
0x18001cdb4  cmp     eax, [rdi+8]
0x18001cdb7  jnb     loc_18001D08D
0x18001cdbd  mov     r12d, eax
0x18001cdc0  mov     [rsp+280h+var_208], r12
0x18001cdc5  imul    rbx, r12, 88h
0x18001cdcc  mov     [rbp+180h+var_1F0], rbx
0x18001cdd0  mov     rax, [rsp+280h+Block]
0x18001cdd5  cmp     dword ptr [rbx+rax+20h], 2
0x18001cdda  jnz     loc_18001CE82
0x18001cde0  mov     r15, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x18001cde7  mov     edx, r12d
0x18001cdea  lea     rcx, [rbp+180h+var_1E0]
0x18001cdee  call    ??A?$CAtlArray@U_WLIDRequestParams@@V?$CElementTraits@U_WLIDRequestParams@@@ATL@@@ATL@@QEAAAEAU_WLIDRequestParams@@_K@Z; ATL::CAtlArray<_WLIDRequestParams,ATL::CElementTraits<_WLIDRequestParams>>::operator[](unsigned __int64)
0x18001cdf3  mov     r14d, [rax+18h]
0x18001cdf7  mov     rax, [rsp+280h+Block]
0x18001cdfc  mov     rdi, [rbx+rax+58h]
0x18001ce01  mov     rbx, [rbx+rax+68h]
0x18001ce06  mov     rsi, [rbp+180h+var_1F0]
0x18001ce0a  mov     rsi, [rsi+rax+28h]
0x18001ce0f  mov     edx, r12d
0x18001ce12  lea     rcx, [rbp+180h+var_1E0]
0x18001ce16  call    ??A?$CAtlArray@U_WLIDRequestParams@@V?$CElementTraits@U_WLIDRequestParams@@@ATL@@@ATL@@QEAAAEAU_WLIDRequestParams@@_K@Z; ATL::CAtlArray<_WLIDRequestParams,ATL::CElementTraits<_WLIDRequestParams>>::operator[](unsigned __int64)
0x18001ce1b  mov     dword ptr [rsp+280h+var_250], r14d
0x18001ce20  mov     [rsp+280h+var_258], rdi
0x18001ce25  mov     [rsp+280h+var_260], rbx
0x18001ce2a  mov     r9, rsi
0x18001ce2d  mov     r8, [rax]
0x18001ce30  mov     rdx, r13
0x18001ce33  lea     rcx, [r15+288h]
0x18001ce3a  call    ?PutCertWithKey@CClientCertManager@@QEAAJPEAXPEBG1VCTime@ATL@@1K@Z; CClientCertManager::PutCertWithKey(void *,ushort const *,ushort const *,ATL::CTime,ushort const *,ulong)
0x18001ce3f  mov     [rbp+180h+arg_10], eax
0x18001ce45  xor     esi, esi
0x18001ce47  test    eax, eax
0x18001ce49  jns     short loc_18001CE7E
0x18001ce4b  mov     dword ptr [rsp+280h+var_260], eax
0x18001ce4f  lea     r9, aPutcertFailed0; "PutCert failed (0x%x)."
0x18001ce56  mov     r8d, 206h; unsigned int
0x18001ce5c  lea     rdx, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001ce63  lea     ecx, [rsi+2]; unsigned __int8
0x18001ce66  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001ce6b  mov     edx, 800488ECh; int
0x18001ce70  mov     rcx, r13; this
0x18001ce73  call    ?SetRequestStatus@CClientSingleIdentity@@QEAAXJ@Z; CClientSingleIdentity::SetRequestStatus(long)
0x18001ce78  mov     [rbp+180h+arg_10], esi
0x18001ce7e  mov     rbx, [rbp+180h+var_1F0]
0x18001ce82  cmp     [r13+48h], rsi
0x18001ce86  jz      loc_18001D065
0x18001ce8c  mov     [rbp+180h+var_1B8], rsi
0x18001ce90  mov     [rbp+180h+var_1C0], esi
0x18001ce93  mov     [rbp+180h+var_1B0], esi
0x18001ce96  mov     rdx, [rsp+280h+Block]
0x18001ce9b  xor     r9d, r9d; bool
0x18001ce9e  mov     r8d, [rbx+rdx+8]; unsigned int
0x18001cea3  mov     rdx, [rbx+rdx+10h]; unsigned __int8 *
0x18001cea8  lea     rcx, [rbp+180h+var_1C0]; this
0x18001ceac  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x18001ceb1  mov     rax, [r13+48h]
0x18001ceb5  mov     [rbp+180h+var_168], rax
0x18001ceb9  lea     rcx, [rbp+180h+var_1A8]
0x18001cebd  mov     [rbp+180h+var_120], rcx
0x18001cec1  mov     rdx, [rsp+280h+Block]
0x18001cec6  mov     rdx, [rbx+rdx+38h]
0x18001cecb  lea     rcx, [rbp+180h+var_1A8]
0x18001cecf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001ced4  mov     [rbp+180h+var_1F0], rax
0x18001ced8  mov     rdx, [rsp+280h+Block]
0x18001cedd  mov     r12d, [rbx+rdx+4]
0x18001cee2  mov     r13d, [rbx+rdx]
0x18001cee6  mov     ecx, [rbx+rdx+20h]
0x18001ceea  call    ?IDCRLTokenType@@YA?AW4TokenFormat@@K@Z; IDCRLTokenType(ulong)
0x18001ceef  mov     r15d, eax
0x18001cef2  mov     rcx, [rbx+rdx+68h]
0x18001cef7  mov     [rbp+180h+var_178], rcx
0x18001cefb  mov     rcx, [rbx+rdx+60h]
0x18001cf00  mov     [rbp+180h+var_170], rcx
0x18001cf04  lea     rax, [rbp+180h+var_1A0]
0x18001cf08  mov     [rbp+180h+var_118], rax
0x18001cf0c  mov     rdx, [rbx+rdx+50h]
0x18001cf11  lea     rcx, [rbp+180h+var_1A0]
0x18001cf15  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001cf1a  mov     r14, rax
0x18001cf1d  lea     rax, [rbp+180h+var_198]
0x18001cf21  mov     [rbp+180h+var_110], rax
0x18001cf25  mov     rcx, [rsp+280h+Block]
0x18001cf2a  mov     r8, [rbx+rcx+30h]
0x18001cf2f  lea     rdx, String
0x18001cf36  test    r8, r8
0x18001cf39  cmovnz  rdx, r8
0x18001cf3d  lea     rcx, [rbp+180h+var_198]
0x18001cf41  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
  ... truncated ...
```
