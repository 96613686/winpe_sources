# CWindowsLiveProvider::_AuthenticateIdentity(uchar *,ulong,void * *,bool)

- ea: `0x180025bbc`
- end: `0x1800267ba`
- name: `?_AuthenticateIdentity@CWindowsLiveProvider@@AEAAJPEAEKPEAPEAX_N@Z`
- size: `3070`
- prototype: `int(CWindowsLiveProvider *__hidden this, unsigned __int8 *, unsigned int, void **, bool)`
- caller_count: `3`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800238ec`
- `0x1800257c0`
- `0x180025a70`

## callees

- `0x180003990`
- `0x180004b44`
- `0x180005458`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18000e9f4`
- `0x18000ebc4`
- `0x18000fe40`
- `0x1800102d0`
- `0x180010b80`
- `0x1800130a4`
- `0x180013434`
- `0x180015238`
- `0x1800158a0`
- `0x1800158c4`
- `0x180016438`
- `0x1800189f4`
- `0x180023418`
- `0x18002520c`
- `0x180025bbc`
- `0x180044874`
- `0x18004a404`
- `0x18004b100`
- `0x18004bcb0`
- `0x18004be20`
- `0x180050528`
- `0x180050650`
- `0x180051198`

## string_xrefs

- `0x180025f99`: `hr = credBag.DeSerializeCredentials(reinterpret_cast<PBYTE>(AuthData.Buffer), AuthData.Length)`
- `0x180026137`: `hr = CWLIDCCHelper::GetDATokenParamsFromCredBag( &memoryManager, &credBag.GetCredentials(), &spDAToken, &spDATokenExpiryTime, &spDATokenCreationTime, &spSessionKey, &sessionKeyLengthBytes, &spFlowToken)`
- `0x180026324`: `hr = CredSerializationHelper::SerializePasswordCredentials( &execContextLite, spTempPassword, tempPasswordLengthChars, true, &credEncoded, &dwLength)`
- `0x18002644c`: `WLIDCCreateContextEx failed, hr=0x%X`
- `0x1800265a4`: `WLIDCUpdateToken failed, hr = 0x%x.`
- `0x1800265fb`: `hr = MakeServiceCall(hSvc, passwordProvided, spFlowToken, IsMigration)`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CWindowsLiveProvider::_AuthenticateIdentity(
        CWindowsLiveProvider *this,
        unsigned __int8 *a2,
        unsigned int a3,
        void **a4,
        bool a5)
{
  unsigned int v7; // r12d
  unsigned __int8 v8; // r14
  unsigned __int16 *v9; // r15
  unsigned __int16 *v10; // r13
  unsigned __int8 *v11; // rsi
  int AuthDataFromAuthIdEx2; // eax
  const unsigned __int16 *Buffer; // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  bool v17; // di
  unsigned int Length; // ebx
  int v19; // eax
  int v20; // eax
  int DATokenParamsFromCredBag; // eax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // ebx
  int v27; // eax
  __int64 v28; // r8
  int v29; // eax
  int v30; // eax
  int v31; // eax
  CWindowsLiveProvider *v32; // rcx
  void *const *v33; // rax
  int v34; // eax
  void *const *Handle; // rax
  int v36; // eax
  int v37; // eax
  void *v38; // rcx
  unsigned int v39; // ebx
  struct _UNICODE_STRING *v41; // [rsp+20h] [rbp-258h]
  struct _UNICODE_STRING *v42; // [rsp+20h] [rbp-258h]
  struct _UNICODE_STRING *v43; // [rsp+20h] [rbp-258h]
  unsigned int v44; // [rsp+60h] [rbp-218h] BYREF
  __int64 v45; // [rsp+68h] [rbp-210h] BYREF
  struct _GUID v46; // [rsp+70h] [rbp-208h] BYREF
  _QWORD *v47; // [rsp+80h] [rbp-1F8h] BYREF
  unsigned int v48; // [rsp+88h] [rbp-1F0h] BYREF
  unsigned __int8 *v49; // [rsp+90h] [rbp-1E8h] BYREF
  _QWORD v50[4]; // [rsp+98h] [rbp-1E0h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-1C0h] BYREF
  _QWORD v52[2]; // [rsp+C0h] [rbp-1B8h] BYREF
  int v53; // [rsp+D0h] [rbp-1A8h]
  struct _UNICODE_STRING v54; // [rsp+D8h] [rbp-1A0h] BYREF
  void *v55; // [rsp+E8h] [rbp-190h] BYREF
  _UNICODE_STRING v56; // [rsp+F0h] [rbp-188h] BYREF
  unsigned __int16 *v57; // [rsp+100h] [rbp-178h] BYREF
  __int64 v58; // [rsp+108h] [rbp-170h]
  _QWORD *v59; // [rsp+110h] [rbp-168h]
  unsigned __int16 *v60; // [rsp+118h] [rbp-160h] BYREF
  __int64 v61; // [rsp+120h] [rbp-158h]
  _QWORD *v62; // [rsp+128h] [rbp-150h]
  unsigned __int8 *v63; // [rsp+130h] [rbp-148h] BYREF
  __int64 v64; // [rsp+138h] [rbp-140h]
  _QWORD *v65; // [rsp+140h] [rbp-138h]
  unsigned __int16 *v66; // [rsp+148h] [rbp-130h] BYREF
  __int64 v67; // [rsp+150h] [rbp-128h]
  _QWORD *v68; // [rsp+158h] [rbp-120h]
  unsigned __int16 *v69; // [rsp+160h] [rbp-118h] BYREF
  __int64 v70; // [rsp+168h] [rbp-110h]
  _QWORD *v71; // [rsp+170h] [rbp-108h]
  unsigned __int16 *v72; // [rsp+178h] [rbp-100h] BYREF
  __int64 v73; // [rsp+180h] [rbp-F8h]
  _QWORD *v74; // [rsp+188h] [rbp-F0h]
  int v75; // [rsp+190h] [rbp-E8h] BYREF
  _BYTE v76[8]; // [rsp+198h] [rbp-E0h] BYREF
  _QWORD v77[4]; // [rsp+1A0h] [rbp-D8h] BYREF
  _QWORD v78[4]; // [rsp+1C0h] [rbp-B8h] BYREF
  _QWORD v79[4]; // [rsp+1E0h] [rbp-98h] BYREF
  unsigned int v80; // [rsp+200h] [rbp-78h]
  int v81; // [rsp+204h] [rbp-74h]
  unsigned __int8 *v82; // [rsp+208h] [rbp-70h]
  int v83; // [rsp+210h] [rbp-68h]
  int v84; // [rsp+214h] [rbp-64h]
  unsigned __int16 *v85; // [rsp+218h] [rbp-60h]
  unsigned __int16 *v86; // [rsp+220h] [rbp-58h]
  CPassportException *v87; // [rsp+230h] [rbp-48h] BYREF
  ATL::CAtlException *v88; // [rsp+238h] [rbp-40h] BYREF
  const wil::ResultException *v89; // [rsp+240h] [rbp-38h] BYREF
  int v90; // [rsp+280h] [rbp+8h] BYREF
  int v91; // [rsp+284h] [rbp+Ch]
  void **v92; // [rsp+298h] [rbp+20h]

  v92 = a4;
  v91 = HIDWORD(this);
  v7 = 0;
  v90 = 0;
  v56 = 0;
  v54 = 0;
  v46 = 0;
  v55 = 0;
  v45 = 0;
  v49 = 0;
  v44 = 0;
  ExecutionContextLite::ExecutionContextLite((ExecutionContextLite *)v77);
  v52[0] = &LocalAllocMemoryManager::`vftable';
  v52[1] = 0;
  v53 = 64;
  v8 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v51);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v76);
  v9 = 0;
  v72 = 0;
  v74 = v52;
  v73 = 0;
  v66 = 0;
  v68 = v52;
  v67 = 0;
  v10 = 0;
  v69 = 0;
  v71 = v52;
  v70 = 0;
  v11 = 0;
  v63 = 0;
  v65 = v52;
  v64 = 0;
  v48 = 0;
  v60 = 0;
  v62 = v52;
  v61 = 0;
  v50[0] = "CWindowsLiveProvider::_AuthenticateIdentity";
  v50[1] = &v90;
  v50[2] = 0;
  v50[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "CWindowsLiveProvider::_AuthenticateIdentity",
    (const char *)0xA15,
    0,
    &v41->Length);
  try
  {
    AuthDataFromAuthIdEx2 = CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2(a2, a3, &v56, &v46, &v54);
    v90 = AuthDataFromAuthIdEx2;
    if ( AuthDataFromAuthIdEx2 < 0 )
    {
      LODWORD(v42) = AuthDataFromAuthIdEx2;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
        0xA21u,
        L"Invalid SEC_WINNT_AUTH_IDENTITY_EX2 format, hr=0x%X",
        v42);
      CTraceFuncW<long>::~CTraceFuncW<long>(v50);
      goto LABEL_72;
    }
    if ( (unsigned int)InlineIsEqualGUID(&SEC_WINNT_AUTH_DATA_TYPE_PASSWORD, &v46) )
    {
      if ( !v56.Length || (Buffer = v56.Buffer) == 0 )
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
          0xA29u,
          L"Account name must be valid");
        v90 = -2147023581;
        CTraceFuncW<long>::~CTraceFuncW<long>(v50);
        goto LABEL_72;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v48,
        v54.Buffer);
      CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v51,
        &v48);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v48);
      v16 = CredSerializationHelper::SerializeCredentials(v77, v14, v15, v51, *(_DWORD *)(v51 - 16));
      v90 = v16;
      if ( v16 < 0 )
      {
        LODWORD(v43) = v16;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
          0xA39u,
          L"CredSerializationHelper::SerializePasswordCredentials Failed. (0x%x)",
          v43);
        CTraceFuncW<long>::~CTraceFuncW<long>(v50);
        goto LABEL_72;
      }
      v8 = 1;
      v17 = a5;
    }
    else
    {
      if ( !(unsigned int)InlineIsEqualGUID(&stru_180069B50, &v46) )
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
          0xA90u,
          L"Invalid CredType in SEC_WINNT_AUTH_IDENTITY_EX2");
        v90 = -2147024809;
        CTraceFuncW<long>::~CTraceFuncW<long>(v50);
        goto LABEL_72;
      }
      v47 = v77;
      v46 = 0;
      Length = v54.Length;
      v19 = CredSerializationHelper::DeSerializeCredentials(
              (struct WLIDCredentialBagSerializer *)&v47,
              (unsigned __int8 *)v54.Buffer,
              v54.Length,
              (struct _WLIDCredentialBag *)&v46);
      v90 = v19;
      if ( v19 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
          "CWindowsLiveProvider::_AuthenticateIdentity",
          0xA40u,
          v19,
          "hr = credBag.DeSerializeCredentials(reinterpret_cast<PBYTE>(AuthData.Buffer), AuthData.Length)");
        AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v46);
        CTraceFuncW<long>::~CTraceFuncW<long>(v50);
        goto LABEL_72;
      }
      v17 = a5;
      v20 = CWLIDCCHelper::ValidateCredUICredBag((const struct _WLIDCredentialBag *)&v46, a5);
      v90 = v20;
      if ( v20 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
          "CWindowsLiveProvider::_AuthenticateIdentity",
          0xA42u,
          v20,
          "hr = CWLIDCCHelper::ValidateCredUICredBag(&credBag.GetCredentials(), IsMigration)");
        AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v46);
        CTraceFuncW<long>::~CTraceFuncW<long>(v50);
        goto LABEL_72;
      }
      if ( v46.Data1 == 1 )
      {
        v8 = 1;
        v30 = CredSerializationHelper::EncryptBufferForSameLogon(
                (struct IWinApiLite *)v78,
                (unsigned __int8 *const)v54.Buffer,
                Length,
                &v49,
                &v44);
        v90 = v30;
        if ( v30 < 0 )
        {
          LODWORD(v43) = v30;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
            0xA80u,
            L"CredSerializationHelper::EncryptBufferForSameLogon failed. (0x%x)",
            v43);
          AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v46);
          CTraceFuncW<long>::~CTraceFuncW<long>(v50);
          goto LABEL_72;
        }
      }
      else
      {
        if ( v46.Data1 - 3 >= 2 )
        {
          LODWORD(v42) = v46.Data1;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
            0xA89u,
            L"Unexpected credBag type. credType=%d.",
            v42);
          v90 = -2147024809;
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
            "CWindowsLiveProvider::_AuthenticateIdentity",
            0xA8Au,
            -2147024809,
            "hr = E_INVALIDARG");
          AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v46);
          CTraceFuncW<long>::~CTraceFuncW<long>(v50);
          goto LABEL_72;
        }
        DATokenParamsFromCredBag = CWLIDCCHelper::GetDATokenParamsFromCredBag(
                                     (struct IMemoryManager *)v52,
                                     (const struct _WLIDCredentialBag *)&v46,
                                     &v72,
                                     &v66,
                                     &v69,
                                     &v63,
                                     &v48,
                                     &v60);
        v90 = DATokenParamsFromCredBag;
        if ( DATokenParamsFromCredBag < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
            "CWindowsLiveProvider::_AuthenticateIdentity",
            0xA51u,
            DATokenParamsFromCredBag,
            "hr = CWLIDCCHelper::GetDATokenParamsFromCredBag( &memoryManager, &credBag.GetCredentials(), &spDAToken, &spD"
            "ATokenExpiryTime, &spDATokenCreationTime, &spSessionKey, &sessionKeyLengthBytes, &spFlowToken)");
          AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v46);
          CTraceFuncW<long>::~CTraceFuncW<long>(v50);
          goto LABEL_72;
        }
        v9 = v72;
        v22 = -1;
        v23 = -1;
        do
          ++v23;
        while ( v72[v23] );
        v73 = 2 * v23 + 2;
        v24 = -1;
        do
          ++v24;
        while ( v66[v24] );
        v67 = 2 * v24 + 2;
        v10 = v69;
        v25 = -1;
        do
          ++v25;
        while ( v69[v25] );
        v70 = 2 * v25 + 2;
        v7 = v48;
        v64 = v48;
        do
          ++v22;
        while ( v60[v22] );
        v61 = 2 * v22 + 2;
        if ( v46.Data1 == 3 )
        {
          v57 = 0;
          v59 = v52;
          v58 = 0;
          v26 = *(_DWORD *)(*(_QWORD *)v46.Data4 + 8LL);
          v27 = CWLIDCCHelper::DuplicateString(
                  (struct IMemoryManager *)v52,
                  *(const unsigned __int16 **)(*(_QWORD *)v46.Data4 + 16LL),
                  2 * v26,
                  &v57);
          v90 = v27;
          v58 = 2LL * (unsigned int)(v26 + 1);
          if ( v27 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
              "CWindowsLiveProvider::_AuthenticateIdentity",
              0xA65u,
              v27,
              "hr");
            Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v57);
            AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v46);
            CTraceFuncW<long>::~CTraceFuncW<long>(v50);
            goto LABEL_72;
          }
          v29 = CredSerializationHelper::SerializeCredentials(v77, 2LL * (unsigned int)(v26 + 1), v28, v57, v26);
          v90 = v29;
          if ( v29 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
              "CWindowsLiveProvider::_AuthenticateIdentity",
              0xA6Eu,
              v29,
              "hr = CredSerializationHelper::SerializePasswordCredentials( &execContextLite, spTempPassword, tempPassword"
              "LengthChars, true, &credEncoded, &dwLength)");
            Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v57);
            AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v46);
            CTraceFuncW<long>::~CTraceFuncW<long>(v50);
            goto LABEL_72;
          }
          v8 = 1;
          Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v57);
        }
        v11 = v63;
      }
      AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v46);
      Buffer = v56.Buffer;
    }
    v31 = WLIDCCreateContextEx(Buffer, L"{2a2059e7-a58a-445c-befe-6a173ffe7ffd}", 0x800000, &v55);
    v90 = v31;
    if ( v31 >= 0 )
    {
      RefWLIDHandle::Attach((RefWLIDHandle *)&v45, v55);
      if ( v8 == 1
        && (v33 = RefWLIDHandle::GetHandle((RefWLIDHandle *)&v45),
            v34 = WLIDCSetAuthData(*v33, 0, v44, v49),
            v90 = v34,
            v34 < 0) )
      {
        LODWORD(v43) = v34;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
          0xAA3u,
          L"WLIDCSetAuthData failed, hr=0x%X",
          v43);
        CTraceFuncW<long>::~CTraceFuncW<long>(v50);
      }
      else
      {
        if ( !v9 )
          goto LABEL_51;
        v79[0] = 0;
        v79[1] = 0;
        v81 = 0;
        v84 = 0;
        v79[2] = L"http://Passport.NET/tb";
        v79[3] = v9;
        v80 = v7;
        v82 = v11;
        if ( !v7 || (v83 = 1, !v11) )
          v83 = 0;
        v85 = v10;
        v86 = v66;
        Handle = RefWLIDHandle::GetHandle((RefWLIDHandle *)&v45);
        v36 = WLIDCUpdateToken(*Handle, (const struct _WLIDTokenParams *)v79, 0);
        v90 = v36;
        if ( v36 < 0 )
        {
          LODWORD(v43) = v36;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
            0xAC1u,
            L"WLIDCUpdateToken failed, hr = 0x%x.",
            v43);
          CTraceFuncW<long>::~CTraceFuncW<long>(v50);
        }
        else
        {
LABEL_51:
          v37 = CWindowsLiveProvider::MakeServiceCall(v32, (struct RefWLIDHandle *)&v45, v8, v60, v17);
          v90 = v37;
          if ( v37 >= 0 )
          {
            if ( v45 )
            {
              v38 = *(void **)(v45 + 8);
              *(_QWORD *)(v45 + 8) = 0;
            }
            else
            {
              v38 = 0;
            }
            *v92 = v38;
            CTraceFuncW<long>::~CTraceFuncW<long>(v50);
          }
          else
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
              "CWindowsLiveProvider::_AuthenticateIdentity",
              0xAC6u,
              v37,
              "hr = MakeServiceCall(hSvc, passwordProvided, spFlowToken, IsMigration)");
            CTraceFuncW<long>::~CTraceFuncW<long>(v50);
          }
        }
      }
    }
    else
    {
      LODWORD(v43) = v31;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
        0xA98u,
        L"WLIDCCreateContextEx failed, hr=0x%X",
        v43);
      CTraceFuncW<long>::~CTraceFuncW<long>(v50);
    }
  }
  catch ( CPassportException *v87 )
  {
    v90 = *((_DWORD *)v87 + 2);
    if ( v90 >= 0 )
      v90 = -2147418113;
  }
  catch ( ATL::CAtlException *v88 )
  {
    v90 = *(_DWORD *)v88;
    if ( v90 >= 0 )
      v90 = -2147418113;
  }
  catch ( std::bad_alloc )
  {
    v90 = -2147024882;
  }
  catch ( long v75 )
  {
    v90 = v75;
    if ( v75 >= 0 )
      v90 = -2147418113;
  }
  catch ( const wil::ResultException *v89 )
  {
    v90 = *((_DWORD *)v89 + 8);
    if ( v90 >= 0 )
      v90 = -2147418113;
  }
LABEL_72:
  CWLIDCCHelper::FreeUnicodeString(&v56);
  CWLIDCCHelper::FreeUnicodeString(&v54);
  v39 = v90;
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v60);
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v63);
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v69);
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v66);
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v72);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v76);
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v51);
  v52[0] = &IMemoryFunctions::`vftable';
  v78[3] = &ISystemStoreLiteFunctions::`vftable';
  v78[2] = &IComFunctions::`vftable';
  v78[1] = &IComFunctions::`vftable';
  v78[0] = &IWinApiLite::`vftable';
  v77[3] = &IIdentityStorageFunctions::`vftable';
  v77[2] = &IRegistryFunctions::`vftable';
  v77[1] = &IMemoryFunctions::`vftable';
  v77[0] = &IExecutionContextLite::`vftable';
  CMIDLPtr<unsigned short *>::Clear(&v49);
  CAutoRefPtr<SmartWLIDHandle>::Deinit(&v45);
  return v39;
}

```

## disassembly

```asm
0x180025bbc  mov     rax, rsp
0x180025bbf  mov     [rax+10h], rbx
0x180025bc3  mov     [rax+18h], rsi
0x180025bc7  mov     [rax+20h], r9
0x180025bcb  mov     [rax+8], rcx
0x180025bcf  push    rdi
0x180025bd0  push    r12
0x180025bd2  push    r13
0x180025bd4  push    r14
0x180025bd6  push    r15
0x180025bd8  sub     rsp, 250h
0x180025bdf  mov     ebx, r8d
0x180025be2  mov     rdi, rdx
0x180025be5  xor     r12d, r12d
0x180025be8  mov     [rax+8], r12d
0x180025bec  xorps   xmm0, xmm0
0x180025bef  movups  xmmword ptr [rax-188h], xmm0
0x180025bf6  xorps   xmm1, xmm1
0x180025bf9  movups  xmmword ptr [rax-1A0h], xmm1
0x180025c00  movups  xmmword ptr [rsp+278h+var_208.Data1], xmm0
0x180025c05  mov     [rax-190h], r12
0x180025c0c  mov     [rsp+278h+var_210], r12
0x180025c11  mov     [rax-1E8h], r12
0x180025c18  mov     [rsp+278h+var_218], r12d
0x180025c1d  lea     rcx, [rax-0D8h]; this
0x180025c24  call    ??0ExecutionContextLite@@QEAA@XZ; ExecutionContextLite::ExecutionContextLite(void)
0x180025c29  nop
0x180025c2a  lea     rax, ??_7LocalAllocMemoryManager@@6B@; const LocalAllocMemoryManager::`vftable'
0x180025c31  mov     [rsp+278h+var_1B8], rax
0x180025c39  mov     [rsp+278h+var_1B0], r12
0x180025c41  mov     [rsp+278h+var_1A8], 40h ; '@'
0x180025c4c  mov     r14b, r12b
0x180025c4f  lea     rcx, [rsp+278h+var_1C0]; void *
0x180025c57  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180025c5c  nop
0x180025c5d  lea     rcx, [rsp+278h+var_E0]; void *
0x180025c65  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180025c6a  nop
0x180025c6b  mov     r15d, r12d
0x180025c6e  mov     [rsp+278h+var_100], r12
0x180025c76  lea     rax, [rsp+278h+var_1B8]
0x180025c7e  mov     [rsp+278h+var_F0], rax
0x180025c86  mov     [rsp+278h+var_F8], r12
0x180025c8e  mov     [rsp+278h+var_130], r12
0x180025c96  lea     rax, [rsp+278h+var_1B8]
0x180025c9e  mov     [rsp+278h+var_120], rax
0x180025ca6  mov     [rsp+278h+var_128], r12
0x180025cae  mov     r13d, r12d
0x180025cb1  mov     [rsp+278h+var_118], r12
0x180025cb9  lea     rax, [rsp+278h+var_1B8]
0x180025cc1  mov     [rsp+278h+var_108], rax
0x180025cc9  mov     [rsp+278h+var_110], r12
0x180025cd1  mov     esi, r12d
0x180025cd4  mov     [rsp+278h+var_148], r12
0x180025cdc  lea     rax, [rsp+278h+var_1B8]
0x180025ce4  mov     [rsp+278h+var_138], rax
0x180025cec  mov     [rsp+278h+var_140], r12
0x180025cf4  mov     [rsp+278h+var_1F0], r12d
0x180025cfc  xor     ecx, ecx
0x180025cfe  mov     [rsp+278h+var_160], rcx
0x180025d06  lea     rax, [rsp+278h+var_1B8]
0x180025d0e  mov     [rsp+278h+var_150], rax
0x180025d16  mov     [rsp+278h+var_158], rcx
0x180025d1e  lea     rdx, aCwindowslivepr_2; "CWindowsLiveProvider::_AuthenticateIden"...
0x180025d25  mov     [rsp+278h+var_1E0], rdx
0x180025d2d  lea     rax, [rsp+278h+arg_0]
0x180025d35  mov     [rsp+278h+var_1D8], rax
0x180025d3d  mov     [rsp+278h+var_1D0], rcx
0x180025d45  mov     [rsp+278h+var_1C8], rcx
0x180025d4d  xor     r9d, r9d; unsigned int
0x180025d50  mov     r8d, 0A15h; char *
0x180025d56  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180025d5d  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180025d62  nop
0x180025d63  lea     rax, [rsp+278h+var_1A0]
0x180025d6b  mov     [rsp+278h+var_258], rax; struct _UNICODE_STRING *
0x180025d70  lea     r9, [rsp+278h+var_208]; struct _GUID *
0x180025d75  lea     r8, [rsp+278h+var_188]; struct _UNICODE_STRING *
0x180025d7d  mov     edx, ebx; unsigned int
0x180025d7f  mov     rcx, rdi; unsigned __int8 *
0x180025d82  call    ?GetAuthDataFromAuthIdEx2@CWLIDCCHelperWithSsp@@SAJPEAEKPEAU_UNICODE_STRING@@PEAU_GUID@@1@Z; CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2(uchar *,ulong,_UNICODE_STRING *,_GUID *,_UNICODE_STRING *)
0x180025d87  mov     [rsp+278h+arg_0], eax
0x180025d8e  xor     edi, edi
0x180025d90  test    eax, eax
0x180025d92  jns     short loc_180025DC8
0x180025d94  mov     dword ptr [rsp+278h+var_258], eax
0x180025d98  lea     r9, aInvalidSecWinn; "Invalid SEC_WINNT_AUTH_IDENTITY_EX2 for"...
0x180025d9f  mov     r8d, 0A21h; unsigned int
0x180025da5  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180025dac  lea     ecx, [rdi+2]; unsigned __int8
0x180025daf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180025db4  nop
0x180025db5  lea     rcx, [rsp+278h+var_1E0]
0x180025dbd  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180025dc2  nop
0x180025dc3  jmp     loc_180026664
0x180025dc8  lea     rdx, [rsp+278h+var_208]; struct _GUID *
0x180025dcd  lea     rcx, SEC_WINNT_AUTH_DATA_TYPE_PASSWORD; struct _GUID *
0x180025dd4  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180025dd9  test    eax, eax
0x180025ddb  jz      loc_180025EFF
0x180025de1  cmp     [rsp+278h+var_188.Length], di
0x180025de9  jz      loc_180025EC3
0x180025def  mov     rbx, [rsp+278h+var_188.Buffer]
0x180025df7  test    rbx, rbx
0x180025dfa  jz      loc_180025EC3
0x180025e00  mov     rdx, [rsp+278h+var_1A0.Buffer]
0x180025e08  lea     rcx, [rsp+278h+var_1F0]
0x180025e10  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180025e15  nop
0x180025e16  lea     rdx, [rsp+278h+var_1F0]
0x180025e1e  lea     rcx, [rsp+278h+var_1C0]
0x180025e26  call    ??4?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@QEAAAEAV0@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180025e2b  nop
0x180025e2c  lea     rcx, [rsp+278h+var_1F0]; void *
0x180025e34  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180025e39  lea     rax, [rsp+278h+var_218]
0x180025e3e  mov     [rsp+278h+var_228], rax
0x180025e43  lea     rax, [rsp+278h+var_1E8]
0x180025e4b  mov     [rsp+278h+var_230], rax
0x180025e50  mov     [rsp+278h+var_238], 1
0x180025e55  mov     r9, [rsp+278h+var_1C0]
0x180025e5d  mov     eax, [r9-10h]
0x180025e61  mov     dword ptr [rsp+278h+var_258], eax
0x180025e65  lea     rcx, [rsp+278h+var_D8]
0x180025e6d  call    ?SerializeCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@W4_WLIDCredentialsType@@W4_WLIDCredentialAttribute@@PEBGK23K_NPEAPEAEPEAK@Z; CredSerializationHelper::SerializeCredentials(IExecutionContextLite *,_WLIDCredentialsType,_WLIDCredentialAttribute,ushort const *,ulong,_WLIDCredentialAttribute,ushort const *,ulong,bool,uchar * *,ulong *)
0x180025e72  mov     [rsp+278h+arg_0], eax
0x180025e79  test    eax, eax
0x180025e7b  jns     short loc_180025EB3
0x180025e7d  mov     dword ptr [rsp+278h+var_258], eax
0x180025e81  lea     r9, aCredserializat_1; "CredSerializationHelper::SerializePassw"...
0x180025e88  mov     r8d, 0A39h; unsigned int
0x180025e8e  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180025e95  mov     ecx, 2; unsigned __int8
0x180025e9a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180025e9f  nop
0x180025ea0  lea     rcx, [rsp+278h+var_1E0]
0x180025ea8  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180025ead  nop
0x180025eae  jmp     loc_180026664
0x180025eb3  mov     r14b, 1
0x180025eb6  mov     dil, [rsp+278h+arg_20]
0x180025ebe  jmp     loc_18002641E
0x180025ec3  lea     r9, aAccountNameMus; "Account name must be valid"
0x180025eca  mov     r8d, 0A29h; unsigned int
0x180025ed0  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180025ed7  mov     ecx, 2; unsigned __int8
0x180025edc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180025ee1  mov     [rsp+278h+arg_0], 80070523h
0x180025eec  lea     rcx, [rsp+278h+var_1E0]
0x180025ef4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180025ef9  nop
0x180025efa  jmp     loc_180026664
0x180025eff  lea     rdx, [rsp+278h+var_208]; struct _GUID *
0x180025f04  lea     rcx, stru_180069B50; struct _GUID *
0x180025f0b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180025f10  test    eax, eax
0x180025f12  jnz     short loc_180025F51
0x180025f14  lea     r9, aInvalidCredtyp; "Invalid CredType in SEC_WINNT_AUTH_IDEN"...
0x180025f1b  mov     r8d, 0A90h; unsigned int
0x180025f21  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180025f28  lea     ecx, [rax+2]; unsigned __int8
0x180025f2b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180025f30  mov     r9d, 80070057h
0x180025f36  mov     [rsp+278h+arg_0], r9d
0x180025f3e  lea     rcx, [rsp+278h+var_1E0]
0x180025f46  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180025f4b  nop
0x180025f4c  jmp     loc_180026664
0x180025f51  lea     rax, [rsp+278h+var_D8]
0x180025f59  mov     [rsp+278h+var_1F8], rax
0x180025f61  xorps   xmm0, xmm0
0x180025f64  movups  xmmword ptr [rsp+278h+var_208.Data1], xmm0
0x180025f69  movzx   ebx, [rsp+278h+var_1A0.Length]
0x180025f71  lea     r9, [rsp+278h+var_208]; pObject
0x180025f76  mov     r8d, ebx; DestinationSize
0x180025f79  mov     rdx, [rsp+278h+var_1A0.Buffer]; Source
0x180025f81  lea     rcx, [rsp+278h+var_1F8]; this
0x180025f89  call    ?DeSerializeCredentials@CredSerializationHelper@@SAJAEAVWLIDCredentialBagSerializer@@PEAEKPEAU_WLIDCredentialBag@@@Z; CredSerializationHelper::DeSerializeCredentials(WLIDCredentialBagSerializer &,uchar *,ulong,_WLIDCredentialBag *)
0x180025f8e  mov     [rsp+278h+arg_0], eax
0x180025f95  test    eax, eax
0x180025f97  jns     short loc_180025FE0
0x180025f99  lea     rcx, aHrCredbagDeser; "hr = credBag.DeSerializeCredentials(rei"...
0x180025fa0  mov     [rsp+278h+var_258], rcx; char *
0x180025fa5  mov     r9d, eax; int
0x180025fa8  mov     r8d, 0A40h; unsigned int
0x180025fae  lea     rdx, aCwindowslivepr_2; "CWindowsLiveProvider::_AuthenticateIden"...
0x180025fb5  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180025fbc  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180025fc1  nop
0x180025fc2  lea     rcx, [rsp+278h+var_208]; this
0x180025fc7  call    ??1AutoWLIDCredentialBag@@QEAA@XZ; AutoWLIDCredentialBag::~AutoWLIDCredentialBag(void)
0x180025fcc  nop
0x180025fcd  lea     rcx, [rsp+278h+var_1E0]
0x180025fd5  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180025fda  nop
0x180025fdb  jmp     loc_180026664
0x180025fe0  mov     dil, [rsp+278h+arg_20]
0x180025fe8  mov     dl, dil; bool
0x180025feb  lea     rcx, [rsp+278h+var_208]; struct _WLIDCredentialBag *
0x180025ff0  call    ?ValidateCredUICredBag@CWLIDCCHelper@@SAJPEBU_WLIDCredentialBag@@_N@Z; CWLIDCCHelper::ValidateCredUICredBag(_WLIDCredentialBag const *,bool)
0x180025ff5  mov     [rsp+278h+arg_0], eax
0x180025ffc  test    eax, eax
0x180025ffe  jns     short loc_180026047
0x180026000  lea     rcx, aHrCwlidcchelpe_0; "hr = CWLIDCCHelper::ValidateCredUICredB"...
0x180026007  mov     [rsp+278h+var_258], rcx; char *
0x18002600c  mov     r9d, eax; int
0x18002600f  mov     r8d, 0A42h; unsigned int
0x180026015  lea     rdx, aCwindowslivepr_2; "CWindowsLiveProvider::_AuthenticateIden"...
0x18002601c  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180026023  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180026028  nop
0x180026029  lea     rcx, [rsp+278h+var_208]; this
0x18002602e  call    ??1AutoWLIDCredentialBag@@QEAA@XZ; AutoWLIDCredentialBag::~AutoWLIDCredentialBag(void)
0x180026033  nop
0x180026034  lea     rcx, [rsp+278h+var_1E0]
0x18002603c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180026041  nop
0x180026042  jmp     loc_180026664
0x180026047  mov     edx, [rsp+278h+var_208.Data1]
0x18002604b  mov     ecx, edx
0x18002604d  sub     ecx, 1
0x180026050  jz      loc_180026393
0x180026056  sub     ecx, 2
0x180026059  jz      short loc_1800260D4
0x18002605b  cmp     ecx, 1
0x18002605e  jz      short loc_1800260D4
0x180026060  mov     dword ptr [rsp+278h+var_258], edx
0x180026064  lea     r9, aUnexpectedCred; "Unexpected credBag type. credType=%d."
0x18002606b  mov     r8d, 0A89h; unsigned int
0x180026071  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180026078  mov     ecx, 2; unsigned __int8
0x18002607d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180026082  mov     r9d, 80070057h; int
0x180026088  mov     [rsp+278h+arg_0], r9d
0x180026090  lea     rax, aHrEInvalidarg; "hr = E_INVALIDARG"
0x180026097  mov     [rsp+278h+var_258], rax; char *
0x18002609c  mov     r8d, 0A8Ah; unsigned int
0x1800260a2  lea     rdx, aCwindowslivepr_2; "CWindowsLiveProvider::_AuthenticateIden"...
0x1800260a9  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800260b0  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800260b5  nop
0x1800260b6  lea     rcx, [rsp+278h+var_208]; this
0x1800260bb  call    ??1AutoWLIDCredentialBag@@QEAA@XZ; AutoWLIDCredentialBag::~AutoWLIDCredentialBag(void)
0x1800260c0  nop
0x1800260c1  lea     rcx, [rsp+278h+var_1E0]
0x1800260c9  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800260ce  nop
0x1800260cf  jmp     loc_180026664
0x1800260d4  lea     rax, [rsp+278h+var_160]
0x1800260dc  mov     [rsp+278h+var_240], rax; unsigned __int16 **
0x1800260e1  lea     rax, [rsp+278h+var_1F0]
0x1800260e9  mov     [rsp+278h+var_248], rax; unsigned int *
0x1800260ee  lea     rax, [rsp+278h+var_148]
0x1800260f6  mov     [rsp+278h+var_250], rax; unsigned __int8 **
0x1800260fb  lea     rax, [rsp+278h+var_118]
0x180026103  mov     [rsp+278h+var_258], rax; unsigned __int16 **
0x180026108  lea     r9, [rsp+278h+var_130]; unsigned __int16 **
0x180026110  lea     r8, [rsp+278h+var_100]; unsigned __int16 **
0x180026118  lea     rdx, [rsp+278h+var_208]; struct _WLIDCredentialBag *
0x18002611d  lea     rcx, [rsp+278h+var_1B8]; struct IMemoryManager *
0x180026125  call    ?GetDATokenParamsFromCredBag@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBU_WLIDCredentialBag@@PEAPEAG22PEAPEAEPEAK2@Z; CWLIDCCHelper::GetDATokenParamsFromCredBag(IMemoryManager *,_WLIDCredentialBag const *,ushort * *,ushort * *,ushort * *,uchar * *,ulong *,ushort * *)
0x18002612a  mov     [rsp+278h+arg_0], eax
0x180026131  xor     esi, esi
0x180026133  test    eax, eax
0x180026135  jns     short loc_18002617E
0x180026137  lea     rcx, aHrCwlidcchelpe_1; "hr = CWLIDCCHelper::GetDATokenParamsFro"...
0x18002613e  mov     [rsp+278h+var_258], rcx; char *
0x180026143  mov     r9d, eax; int
0x180026146  mov     r8d, 0A51h; unsigned int
0x18002614c  lea     rdx, aCwindowslivepr_2; "CWindowsLiveProvider::_AuthenticateIden"...
0x180026153  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002615a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002615f  nop
0x180026160  lea     rcx, [rsp+278h+var_208]; this
0x180026165  call    ??1AutoWLIDCredentialBag@@QEAA@XZ; AutoWLIDCredentialBag::~AutoWLIDCredentialBag(void)
0x18002616a  nop
0x18002616b  lea     rcx, [rsp+278h+var_1E0]
0x180026173  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180026178  nop
0x180026179  jmp     loc_180026664
0x18002617e  mov     r15, [rsp+278h+var_100]
0x180026186  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002618a  mov     rax, rcx
0x18002618d  inc     rax
0x180026190  cmp     [r15+rax*2], si
0x180026195  jnz     short loc_18002618D
0x180026197  lea     rax, ds:2[rax*2]
0x18002619f  mov     [rsp+278h+var_F8], rax
0x1800261a7  mov     rax, rcx
0x1800261aa  mov     rdx, [rsp+278h+var_130]
0x1800261b2  inc     rax
0x1800261b5  cmp     [rdx+rax*2], si
0x1800261b9  jnz     short loc_1800261B2
0x1800261bb  lea     rax, ds:2[rax*2]
0x1800261c3  mov     [rsp+278h+var_128], rax
0x1800261cb  mov     r13, [rsp+278h+var_118]
0x1800261d3  mov     rax, rcx
0x1800261d6  inc     rax
0x1800261d9  cmp     [r13+rax*2+0], si
  ... truncated ...
```
