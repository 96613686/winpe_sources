# UserIdKeyManagerImplementation::ProvisionUserIdKeyInternal(IIdentityProviderExecutionContext *,HWND__ *,ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x18002bef0`
- end: `0x18002c976`
- name: `?ProvisionUserIdKeyInternal@UserIdKeyManagerImplementation@@AEAAJPEAVIIdentityProviderExecutionContext@@PEAUHWND__@@KPEBG22@Z`
- size: `2694`
- prototype: `int(UserIdKeyManagerImplementation *__hidden this, struct IIdentityProviderExecutionContext *, HWND, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002bca0`

## callees

- `0x180003990`
- `0x1800090c0`
- `0x180009630`
- `0x18000ebc4`
- `0x180010b80`
- `0x1800130a4`
- `0x180013434`
- `0x180016758`
- `0x18001c124`
- `0x1800277b4`
- `0x1800281c4`
- `0x180028578`
- `0x18002859c`
- `0x180028630`
- `0x180028650`
- `0x180028e08`
- `0x180028e74`
- `0x18002a554`
- `0x18002ae68`
- `0x18002aed4`
- `0x18002b05c`
- `0x18002b96c`
- `0x18002bef0`
- `0x18002f70c`
- `0x180039460`
- `0x18004de84`
- `0x180050ff4`
- `0x180058010`

## import_xrefs

- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalRemoveCredential` at `0x18002c77b`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalRemoveCredential` at `0x18002c77b`

## string_xrefs

- `0x18002c5d9`: `login.live.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall UserIdKeyManagerImplementation::ProvisionUserIdKeyInternal(
        UserIdKeyManagerImplementation *this,
        struct IIdentityProviderExecutionContext *a2,
        HWND a3,
        int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  char v9; // r15
  bool IsNullOrEmpty; // al
  bool v11; // r14
  __int64 v12; // r13
  int v13; // eax
  int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // r8
  int v21; // eax
  int v22; // r15d
  int v23; // eax
  struct ILiveIdNtService *v24; // r15
  __int64 (__fastcall *v25)(struct ILiveIdNtService *, const unsigned __int16 *, const unsigned __int16 *, __int64); // rbx
  unsigned int Handle; // eax
  const unsigned __int16 *v27; // rdx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 (__fastcall *v31)(struct ILiveIdNtService *, void *, const unsigned __int16 *, unsigned __int16 **); // rbx
  void **v32; // rax
  unsigned __int16 *v33; // rdx
  int v34; // eax
  __int64 v35; // rdx
  __int64 (__fastcall *v36)(struct ILiveIdNtService *, void *, const wchar_t *, unsigned __int16 **); // rbx
  void **v37; // rax
  __int64 v38; // rax
  UserIdKeyManagerImplementation *v39; // rcx
  unsigned __int64 v40; // r9
  __int64 v41; // rdx
  int IsLocalConnected; // eax
  __int64 v43; // rcx
  int MessageForPinPrompt; // eax
  __int64 v45; // rdx
  char v46; // bl
  __int64 (__fastcall *v47)(__int64, _QWORD *, const unsigned __int16 *, HWND); // r10
  HWND v48; // r9
  int v49; // ecx
  int v51; // ebx
  unsigned int v52; // r8d
  int v53; // eax
  int v54; // eax
  UserIdKeyManagerImplementation *v55; // rcx
  int v56; // eax
  void **v57; // rax
  bool *v59; // [rsp+20h] [rbp-E0h]
  int v60; // [rsp+20h] [rbp-E0h]
  int v61; // [rsp+20h] [rbp-E0h]
  int v62; // [rsp+20h] [rbp-E0h]
  int v63; // [rsp+20h] [rbp-E0h]
  int v64; // [rsp+60h] [rbp-A0h] BYREF
  bool v65; // [rsp+64h] [rbp-9Ch] BYREF
  char v66; // [rsp+65h] [rbp-9Bh]
  char v67; // [rsp+66h] [rbp-9Ah] BYREF
  const unsigned __int16 *v68; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+70h] [rbp-90h] BYREF
  int v70; // [rsp+78h] [rbp-88h] BYREF
  int v71[2]; // [rsp+80h] [rbp-80h] BYREF
  int v72; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v73; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v74; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v75[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v76; // [rsp+B8h] [rbp-48h] BYREF
  struct Windows::Foundation::IAsyncAction *v77; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v78[4]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 **v79; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v80; // [rsp+F0h] [rbp-10h] BYREF
  char v81; // [rsp+F8h] [rbp-8h]
  __int64 v82; // [rsp+100h] [rbp+0h] BYREF
  __int64 v83; // [rsp+108h] [rbp+8h] BYREF
  __int64 v84; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v85[5]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v86[10]; // [rsp+140h] [rbp+40h] BYREF
  char v87; // [rsp+190h] [rbp+90h]
  _QWORD v88[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v89[5]; // [rsp+1B8h] [rbp+B8h] BYREF
  char v90; // [rsp+1E0h] [rbp+E0h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]
  UserIdKeyManagerImplementation *v92; // [rsp+230h] [rbp+130h] BYREF
  char v93; // [rsp+240h] [rbp+140h] BYREF
  int v94; // [rsp+248h] [rbp+148h] BYREF

  v94 = a4;
  v92 = this;
  v64 = 0;
  v70 = 0;
  v72 = 0;
  v93 = 0;
  v65 = 0;
  v74 = 0;
  v84 = 0;
  v83 = 0;
  if ( (a4 & 2) != 0 )
  {
    LOBYTE(v92) = 1;
LABEL_4:
    v9 = 1;
    goto LABEL_5;
  }
  LOBYTE(v92) = 0;
  v9 = 0;
  if ( (a4 & 1) != 0 )
    goto LABEL_4;
LABEL_5:
  v66 = v9;
  v67 = BYTE1(a4) & 1;
  v85[0] = "UserIdKeyManagerImplementation::ProvisionUserIdKeyInternal";
  v85[1] = &v64;
  v85[2] = 0;
  v85[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
    "UserIdKeyManagerImplementation::ProvisionUserIdKeyInternal",
    (const char *)0x58,
    0,
    (const unsigned __int16 *)v59);
  v86[0] = &v64;
  v86[1] = &v65;
  v86[2] = &v92;
  v86[3] = &v70;
  v86[4] = &v67;
  v86[5] = &v94;
  v86[6] = &v74;
  v86[7] = &v72;
  v86[8] = &v84;
  v86[9] = &v83;
  v87 = 1;
  IsNullOrEmpty = CWLIDCCHelper::IsNullOrEmpty(a5);
  if ( !a3 || (v11 = !IsNullOrEmpty, !IsNullOrEmpty == CWLIDCCHelper::IsNullOrEmpty(a6)) )
  {
    v14 = -2147024809;
    v64 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
      (const char *)0x80070057LL,
      v60);
    v87 = 0;
    goto LABEL_91;
  }
  v12 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 48LL))(a2);
  v13 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v12 + 8LL))(v12, &v72, 0);
  v14 = v13;
  v64 = v13;
  if ( v13 >= 0 )
  {
    if ( !v72 && !v11 )
    {
      v14 = -2147024846;
      v64 = -2147024846;
      v15 = 2147942450LL;
      v16 = 139;
      goto LABEL_12;
    }
    memset(v75, 0, sizeof(v75));
    if ( CWLIDCCHelper::IsNullOrEmpty(a7) )
    {
      v18 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 64LL))(a2);
      v61 = v94;
      LOBYTE(v19) = (_BYTE)v92;
      LOBYTE(v20) = v9;
      v21 = (*(__int64 (__fastcall **)(__int64, HWND, __int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, a3, v20, v19);
      v22 = v21;
      v64 = v21;
      if ( v21 < 0 )
      {
        v14 = -2147023673;
        if ( v21 != -2147023673 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9F,
            (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
            (const char *)(unsigned int)v21,
            v61);
          Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(v75);
          v14 = v22;
          goto LABEL_89;
        }
LABEL_88:
        Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(v75);
        goto LABEL_89;
      }
    }
    else
    {
      v23 = DuplicateString(v17);
      v14 = v23;
      v64 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA3,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
          (const char *)(unsigned int)v23,
          v60);
        goto LABEL_88;
      }
    }
    v24 = (struct ILiveIdNtService *)(*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 32LL))(a2);
    v69 = 0;
    v25 = *(__int64 (__fastcall **)(struct ILiveIdNtService *, const unsigned __int16 *, const unsigned __int16 *, __int64))(*(_QWORD *)v24 + 48LL);
    Handle = (unsigned int)RefWLIDHandle::GetHandle((RefWLIDHandle *)&v69);
    v27 = a5;
    if ( !v11 )
      v27 = &qword_180063440;
    v62 = Handle;
    v28 = v25(v24, v27, L"{2a2059e7-a58a-445c-befe-6a173ffe7ffd}", 0x800000);
    v14 = v28;
    v64 = v28;
    if ( v28 < 0 )
    {
      v29 = 171;
LABEL_23:
      v30 = (unsigned int)v28;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
        (const char *)v30,
        v62);
LABEL_87:
      CAutoRefPtr<SmartWLIDHandle>::Deinit(&v69);
      goto LABEL_88;
    }
    v31 = *(__int64 (__fastcall **)(struct ILiveIdNtService *, void *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v24 + 152LL);
    v32 = RefWLIDHandle::GetHandle((RefWLIDHandle *)&v69);
    v28 = v31(v24, *v32, L"CID", &v74);
    v14 = v28;
    v64 = v28;
    if ( v28 < 0 )
    {
      v29 = 172;
      goto LABEL_23;
    }
    if ( CWLIDCCHelper::IsNullOrEmpty(v74) )
    {
      v14 = -2147023728;
      v64 = -2147023728;
      v30 = 2147943568LL;
      v29 = 176;
      goto LABEL_24;
    }
    v78[0] = v33;
    v78[2] = v33;
    v78[1] = v33;
    if ( v11 )
    {
      v34 = DuplicateString(a5);
      v14 = v34;
      v64 = v34;
      if ( v34 < 0 )
      {
        v35 = 182;
LABEL_32:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
          (const char *)(unsigned int)v34,
          v62);
LABEL_86:
        Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(v78);
        goto LABEL_87;
      }
    }
    else
    {
      v36 = *(__int64 (__fastcall **)(struct ILiveIdNtService *, void *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v24 + 152LL);
      v37 = RefWLIDHandle::GetHandle((RefWLIDHandle *)&v69);
      v34 = v36(v24, *v37, L"AuthMembername", v78);
      v14 = v34;
      v64 = v34;
      if ( v34 < 0 )
      {
        v35 = 186;
        goto LABEL_32;
      }
    }
    v68 = 0;
    v38 = *(_QWORD *)v12;
    v79 = (unsigned __int16 **)&v68;
    v80 = 0;
    v81 = 1;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v38 + 32))(v12, &v80);
    v64 = v14;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v79);
    if ( v14 < 0 )
    {
      v40 = (unsigned int)v14;
      v41 = 190;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
        (const char *)v40,
        v62);
LABEL_85:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
      goto LABEL_86;
    }
    IsLocalConnected = UserIdKeyManagerImplementation::IsLocalConnected(v39, a2, v78[0], v68, &v65);
    v14 = IsLocalConnected;
    v64 = IsLocalConnected;
    if ( IsLocalConnected < 0 )
    {
      v40 = (unsigned int)IsLocalConnected;
      v41 = 191;
      goto LABEL_37;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v71);
    MessageForPinPrompt = UserIdKeyManagerImplementation::GetMessageForPinPrompt(v43, a2, v78[0], v71);
    v14 = MessageForPinPrompt;
    v64 = MessageForPinPrompt;
    if ( MessageForPinPrompt < 0 )
    {
      v45 = 194;
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
        (const char *)(unsigned int)MessageForPinPrompt,
        v62);
LABEL_84:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v71);
      goto LABEL_85;
    }
    v76 = 0;
    v76 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 72LL))(a2);
    v78[3] = 0;
    v62 = (int)a3;
    MessageForPinPrompt = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v76 + 24LL))(
                            v76,
                            v68,
                            0,
                            0);
    v14 = MessageForPinPrompt;
    v64 = MessageForPinPrompt;
    if ( MessageForPinPrompt == -2146893809 )
    {
      if ( (_BYTE)v92 != 1 )
      {
        v46 = v93;
        goto LABEL_56;
      }
      MessageForPinPrompt = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v76 + 16LL))(
                              v76,
                              v68,
                              4);
      v14 = MessageForPinPrompt;
      v64 = MessageForPinPrompt;
      if ( MessageForPinPrompt < 0 )
      {
        v45 = 217;
        goto LABEL_42;
      }
      v62 = (int)a3;
      MessageForPinPrompt = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v76 + 24LL))(
                              v76,
                              v68,
                              0,
                              0);
      v14 = MessageForPinPrompt;
      v64 = MessageForPinPrompt;
      if ( MessageForPinPrompt < 0 )
      {
        if ( MessageForPinPrompt != -2146893770 )
        {
          v45 = 229;
          goto LABEL_42;
        }
LABEL_53:
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v71);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
        Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(v78);
        CAutoRefPtr<SmartWLIDHandle>::Deinit(&v69);
        Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(v75);
        v14 = -2146893770;
        goto LABEL_89;
      }
    }
    else if ( MessageForPinPrompt < 0 )
    {
      if ( MessageForPinPrompt != -2146893770 )
      {
        v45 = 236;
        goto LABEL_42;
      }
      goto LABEL_53;
    }
    v46 = 1;
    v93 = 1;
LABEL_56:
    v73 = 0;
    v82 = 0;
    v89[0] = &v64;
    v89[1] = &v93;
    v89[2] = &v92;
    v89[3] = &v68;
    v89[4] = &v76;
    v90 = 1;
    v88[1] = 0;
    v88[2] = v74;
    v88[0] = L"login.live.com";
    v47 = *(__int64 (__fastcall **)(__int64, _QWORD *, const unsigned __int16 *, HWND))(*(_QWORD *)v76 + 32LL);
    v79 = &v73;
    v80 = 0;
    v81 = 1;
    v48 = a3;
    if ( v46 == 1 )
      v48 = 0;
    v63 = v71[0];
    v64 = v47(v76, v88, v68, v48);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v79);
    v49 = v64;
    if ( (int)(v64 + 0x80000000) >= 0 && v64 != -2146893770 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x12B,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
        (const char *)(unsigned int)v64,
        v63);
      v49 = v64;
    }
    if ( v49 >= 0 )
    {
      LOBYTE(v63) = v66;
      v51 = (*(__int64 (__fastcall **)(struct ILiveIdNtService *, unsigned __int16 *, _QWORD, unsigned __int16 *))(*(_QWORD *)v24 + 240LL))(
              v24,
              v78[0],
              v75[0],
              v73);
      if ( v51 < 0 )
      {
        if ( !v93 )
        {
          v53 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v76 + 64LL))(v76, v73);
          if ( v53 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x13C,
              (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
              (const char *)(unsigned int)v53,
              v63);
        }
        v64 = v51;
        wil::details::in1diag3::Log_Hr(retaddr, (void *)0x13F, v52, (const char *)(unsigned int)v51, v63);
      }
    }
    v90 = 0;
    lambda_aa442755310e56a344c5f0d5e5e2ef3a_::operator()(v89);
    v14 = v64;
    if ( v64 >= 0 )
    {
      if ( !v65 )
      {
LABEL_81:
        v57 = RefWLIDHandle::GetHandle((RefWLIDHandle *)&v69);
        AccountRestorationWlidprovUtil::GetAccountCompletionTimesAndUpdateTimeStamps(v24, *v57, &v84, &v83);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v71);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
        Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(v78);
        CAutoRefPtr<SmartWLIDHandle>::Deinit(&v69);
        Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(v75);
        v87 = 0;
        lambda_fa913c277e03c13e2bcc6e9e0ff22eb6_::operator()(v86);
        CTraceFuncW<long>::~CTraceFuncW<long>(v85);
        CMIDLPtr<unsigned short *>::Clear(&v74);
        return 0;
      }
      if ( (unsigned __int8)IsNgcLocalRemoveCredentialPresent() )
      {
        v54 = NgcLocalRemoveCredential(v68, 0);
        v70 = v54;
        if ( v54 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
            (const char *)(unsigned int)v54,
            v63);
          v70 = 0;
        }
      }
      v77 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
      v56 = UserIdKeyManagerImplementation::PrimeNgcLogonCacheAsync(v55, v78[0], v68, v73, &v82, &v77);
      v70 = v56;
      if ( (_BYTE)v92 != 1 && v67 != 1
        || v56 >= 0
        && (v70 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v77),
            v70 >= 0)
        && (v70 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IAsyncAction *))(*(_QWORD *)v77 + 64LL))(v77),
            v70 >= 0) )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
        goto LABEL_81;
      }
      v14 = 297138;
      v64 = 297138;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
    goto LABEL_84;
  }
  v15 = (unsigned int)v13;
  v16 = 134;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
    (const char *)v15,
    v60);
LABEL_89:
  v87 = 0;
LABEL_91:
  lambda_fa913c277e03c13e2bcc6e9e0ff22eb6_::operator()(v86);
  CTraceFuncW<long>::~CTraceFuncW<long>(v85);
  CMIDLPtr<unsigned short *>::Clear(&v74);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002bef0  mov     [rsp-8+arg_18], r9d
0x18002bef5  mov     [rsp-8+arg_0], rcx
0x18002befa  push    rbp
0x18002befb  push    rbx
0x18002befc  push    rsi
0x18002befd  push    r12
0x18002beff  push    r13
0x18002bf01  push    r14
0x18002bf03  push    r15
0x18002bf05  lea     rbp, [rsp-0F0h]
0x18002bf0d  sub     rsp, 1F0h
0x18002bf14  mov     r12, r8
0x18002bf17  mov     rsi, rdx
0x18002bf1a  xor     r13d, r13d
0x18002bf1d  mov     dword ptr [rsp+220h+var_1C0], r13d
0x18002bf22  mov     [rsp+220h+var_1A8], r13d
0x18002bf27  mov     [rbp+120h+var_198], r13d
0x18002bf2b  mov     [rbp+120h+arg_10], r13b
0x18002bf32  mov     byte ptr [rsp+220h+var_1C0+4], r13b
0x18002bf37  mov     [rbp+120h+var_188], r13
0x18002bf3b  mov     [rbp+120h+var_110], r13
0x18002bf3f  mov     [rbp+120h+var_118], r13
0x18002bf43  test    r9b, 2
0x18002bf47  jz      short loc_18002BF52
0x18002bf49  mov     byte ptr [rbp+120h+arg_0], 1
0x18002bf50  jmp     short loc_18002BF62
0x18002bf52  mov     byte ptr [rbp+120h+arg_0], r13b
0x18002bf59  test    r9b, 1
0x18002bf5d  mov     r15b, r13b
0x18002bf60  jz      short loc_18002BF65
0x18002bf62  mov     r15b, 1
0x18002bf65  mov     byte ptr [rsp+220h+var_1C0+5], r15b
0x18002bf6a  shr     r9d, 8
0x18002bf6e  and     r9b, 1
0x18002bf72  mov     byte ptr [rsp+220h+var_1C0+6], r9b
0x18002bf77  lea     rdx, aUseridkeymanag_1; "UserIdKeyManagerImplementation::Provisi"...
0x18002bf7e  mov     [rbp+120h+var_108], rdx
0x18002bf82  lea     rax, [rsp+220h+var_1C0]
0x18002bf87  mov     [rbp+120h+var_100], rax
0x18002bf8b  mov     [rbp+120h+var_F8], r13
0x18002bf8f  mov     [rbp+120h+var_F0], r13
0x18002bf93  xor     r9d, r9d; unsigned int
0x18002bf96  lea     r8d, [r9+58h]; char *
0x18002bf9a  lea     rcx, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002bfa1  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18002bfa6  nop
0x18002bfa7  lea     rax, [rsp+220h+var_1C0]
0x18002bfac  mov     [rbp+120h+var_E0], rax
0x18002bfb0  lea     rax, [rsp+220h+var_1C0+4]
0x18002bfb5  mov     [rbp+120h+var_D8], rax
0x18002bfb9  lea     rax, [rbp+120h+arg_0]
0x18002bfc0  mov     [rbp+120h+var_D0], rax
0x18002bfc4  lea     rax, [rsp+220h+var_1A8]
0x18002bfc9  mov     [rbp+120h+var_C8], rax
0x18002bfcd  lea     rax, [rsp+220h+var_1C0+6]
0x18002bfd2  mov     [rbp+120h+var_C0], rax
0x18002bfd6  lea     rax, [rbp+120h+arg_18]
0x18002bfdd  mov     [rbp+120h+var_B8], rax
0x18002bfe1  lea     rax, [rbp+120h+var_188]
0x18002bfe5  mov     [rbp+120h+var_B0], rax
0x18002bfe9  lea     rax, [rbp+120h+var_198]
0x18002bfed  mov     [rbp+120h+var_A8], rax
0x18002bff1  lea     rax, [rbp+120h+var_110]
0x18002bff5  mov     [rbp+120h+var_A0], rax
0x18002bffc  lea     rax, [rbp+120h+var_118]
0x18002c000  mov     [rbp+120h+var_98], rax
0x18002c007  mov     [rbp+120h+var_90], 1
0x18002c00e  mov     rcx, [rbp+120h+arg_20]; unsigned __int16 *
0x18002c015  call    ?IsNullOrEmpty@CWLIDCCHelper@@SA_NPEBG@Z; CWLIDCCHelper::IsNullOrEmpty(ushort const *)
0x18002c01a  mov     r14b, al
0x18002c01d  test    r12, r12
0x18002c020  jz      loc_18002C918
0x18002c026  xor     r14b, 1
0x18002c02a  mov     rcx, [rbp+120h+arg_28]; unsigned __int16 *
0x18002c031  call    ?IsNullOrEmpty@CWLIDCCHelper@@SA_NPEBG@Z; CWLIDCCHelper::IsNullOrEmpty(ushort const *)
0x18002c036  cmp     r14b, al
0x18002c039  jz      loc_18002C918
0x18002c03f  mov     rax, [rsi]
0x18002c042  mov     rcx, rsi
0x18002c045  mov     rax, [rax+30h]
0x18002c049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c04e  mov     r13, rax
0x18002c051  mov     rcx, [rax]
0x18002c054  mov     rax, [rcx+8]
0x18002c058  xor     r8d, r8d
0x18002c05b  lea     rdx, [rbp+120h+var_198]
0x18002c05f  mov     rcx, r13
0x18002c062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c067  mov     ebx, eax
0x18002c069  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c06d  test    eax, eax
0x18002c06f  jns     short loc_18002C07B
0x18002c071  mov     r9d, eax
0x18002c074  mov     edx, 86h
0x18002c079  jmp     short loc_18002C098
0x18002c07b  xor     ebx, ebx
0x18002c07d  cmp     [rbp+120h+var_198], ebx
0x18002c080  jnz     short loc_18002C0B0
0x18002c082  test    r14b, r14b
0x18002c085  jnz     short loc_18002C0B0
0x18002c087  mov     ebx, 80070032h
0x18002c08c  mov     dword ptr [rsp+220h+var_1C0], ebx
0x18002c090  mov     r9d, ebx; char *
0x18002c093  mov     edx, 8Bh; void *
0x18002c098  lea     r8, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002c09f  mov     rcx, [rbp+128h]; this
0x18002c0a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c0ab  jmp     loc_18002C90F
0x18002c0b0  mov     [rbp+120h+var_180], rbx
0x18002c0b4  mov     [rbp+120h+var_170], rbx
0x18002c0b8  mov     [rbp+120h+var_178], rbx
0x18002c0bc  mov     rcx, [rbp+120h+arg_30]; unsigned __int16 *
0x18002c0c3  call    ?IsNullOrEmpty@CWLIDCCHelper@@SA_NPEBG@Z; CWLIDCCHelper::IsNullOrEmpty(ushort const *)
0x18002c0c8  test    al, al
0x18002c0ca  jz      loc_18002C160
0x18002c0d0  mov     rax, [rsi]
0x18002c0d3  mov     rcx, rsi
0x18002c0d6  mov     rax, [rax+40h]
0x18002c0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0df  mov     r10, rax
0x18002c0e2  mov     rcx, [rax]
0x18002c0e5  mov     rax, [rcx+8]
0x18002c0e9  mov     [rsp+220h+var_1E8], rbx
0x18002c0ee  mov     [rsp+220h+var_1F0], rbx
0x18002c0f3  lea     rcx, [rbp+120h+var_180]
0x18002c0f7  mov     [rsp+220h+var_1F8], rcx
0x18002c0fc  mov     ecx, [rbp+120h+arg_18]
0x18002c102  mov     dword ptr [rsp+220h+var_200], ecx; int
0x18002c106  mov     r9b, byte ptr [rbp+120h+arg_0]
0x18002c10d  mov     r8b, r15b
0x18002c110  mov     rdx, r12
0x18002c113  mov     rcx, r10
0x18002c116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c11b  mov     r15d, eax
0x18002c11e  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c122  test    eax, eax
0x18002c124  jns     short loc_18002C195
0x18002c126  mov     ebx, 800704C7h
0x18002c12b  cmp     eax, ebx
0x18002c12d  jz      loc_18002C905
0x18002c133  mov     rcx, [rbp+128h]; this
0x18002c13a  mov     r9d, eax; char *
0x18002c13d  lea     r8, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002c144  mov     edx, 9Fh; void *
0x18002c149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c14e  nop
0x18002c14f  lea     rcx, [rbp+120h+var_180]
0x18002c153  call    ??1?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>(void)
0x18002c158  mov     ebx, r15d
0x18002c15b  jmp     loc_18002C90F
0x18002c160  lea     rdx, [rbp+120h+var_180]
0x18002c164  call    ?DuplicateString@@YAJPEBGAEAV?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@@Z; DuplicateString(ushort const *,Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext> &)
0x18002c169  mov     ebx, eax
0x18002c16b  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c16f  test    eax, eax
0x18002c171  jns     short loc_18002C193
0x18002c173  mov     rcx, [rbp+128h]; this
0x18002c17a  mov     r9d, eax; char *
0x18002c17d  lea     r8, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002c184  mov     edx, 0A3h; void *
0x18002c189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c18e  jmp     loc_18002C905
0x18002c193  xor     ebx, ebx
0x18002c195  mov     rax, [rsi]
0x18002c198  mov     rcx, rsi
0x18002c19b  mov     rax, [rax+20h]
0x18002c19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1a4  mov     r15, rax
0x18002c1a7  mov     [rsp+220h+var_1B0], rbx
0x18002c1ac  mov     rcx, [rax]
0x18002c1af  mov     rbx, [rcx+30h]
0x18002c1b3  lea     rcx, [rsp+220h+var_1B0]; this
0x18002c1b8  call    ?GetHandle@RefWLIDHandle@@AEAAPEAPEAXXZ; RefWLIDHandle::GetHandle(void)
0x18002c1bd  lea     rcx, qword_180063440
0x18002c1c4  mov     rdx, [rbp+120h+arg_20]
0x18002c1cb  test    r14b, r14b
0x18002c1ce  cmovz   rdx, rcx
0x18002c1d2  mov     [rsp+220h+var_200], rax; int
0x18002c1d7  mov     r9d, 800000h
0x18002c1dd  lea     r8, a2a2059e7A58a44; "{2a2059e7-a58a-445c-befe-6a173ffe7ffd}"
0x18002c1e4  mov     rcx, r15
0x18002c1e7  mov     rax, rbx
0x18002c1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1ef  mov     ebx, eax
0x18002c1f1  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c1f5  test    eax, eax
0x18002c1f7  jns     short loc_18002C219
0x18002c1f9  mov     edx, 0ABh; void *
0x18002c1fe  mov     r9d, eax; char *
0x18002c201  mov     rcx, [rbp+128h]; this
0x18002c208  lea     r8, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002c20f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c214  jmp     loc_18002C8FA
0x18002c219  mov     rax, [r15]
0x18002c21c  mov     rbx, [rax+98h]
0x18002c223  lea     rcx, [rsp+220h+var_1B0]; this
0x18002c228  call    ?GetHandle@RefWLIDHandle@@AEAAPEAPEAXXZ; RefWLIDHandle::GetHandle(void)
0x18002c22d  lea     r9, [rbp+120h+var_188]
0x18002c231  lea     r8, aCid; "CID"
0x18002c238  mov     rdx, [rax]
0x18002c23b  mov     rcx, r15
0x18002c23e  mov     rax, rbx
0x18002c241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c246  mov     ebx, eax
0x18002c248  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c24c  xor     edx, edx
0x18002c24e  test    eax, eax
0x18002c250  jns     short loc_18002C259
0x18002c252  mov     edx, 0ACh
0x18002c257  jmp     short loc_18002C1FE
0x18002c259  mov     rcx, [rbp+120h+var_188]; unsigned __int16 *
0x18002c25d  call    ?IsNullOrEmpty@CWLIDCCHelper@@SA_NPEBG@Z; CWLIDCCHelper::IsNullOrEmpty(ushort const *)
0x18002c262  test    al, al
0x18002c264  jz      short loc_18002C279
0x18002c266  mov     ebx, 80070490h
0x18002c26b  mov     dword ptr [rsp+220h+var_1C0], ebx
0x18002c26f  mov     r9d, ebx
0x18002c272  mov     edx, 0B0h
0x18002c277  jmp     short loc_18002C201
0x18002c279  mov     [rbp+120h+var_158], rdx
0x18002c27d  mov     [rbp+120h+var_148], rdx
0x18002c281  mov     [rbp+120h+var_150], rdx
0x18002c285  cmp     r14b, 1
0x18002c289  jnz     short loc_18002C2C5
0x18002c28b  lea     rdx, [rbp+120h+var_158]
0x18002c28f  mov     rcx, [rbp+120h+arg_20]; unsigned __int16 *
0x18002c296  call    ?DuplicateString@@YAJPEBGAEAV?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@@Z; DuplicateString(ushort const *,Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext> &)
0x18002c29b  mov     ebx, eax
0x18002c29d  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c2a1  test    eax, eax
0x18002c2a3  jns     short loc_18002C303
0x18002c2a5  mov     edx, 0B6h; void *
0x18002c2aa  lea     r8, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002c2b1  mov     r9d, eax; char *
0x18002c2b4  mov     rcx, [rbp+128h]; this
0x18002c2bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c2c0  jmp     loc_18002C8F0
0x18002c2c5  mov     rax, [r15]
0x18002c2c8  mov     rbx, [rax+98h]
0x18002c2cf  lea     rcx, [rsp+220h+var_1B0]; this
0x18002c2d4  call    ?GetHandle@RefWLIDHandle@@AEAAPEAPEAXXZ; RefWLIDHandle::GetHandle(void)
0x18002c2d9  lea     r9, [rbp+120h+var_158]
0x18002c2dd  lea     r8, aAuthmembername; "AuthMembername"
0x18002c2e4  mov     rdx, [rax]
0x18002c2e7  mov     rcx, r15
0x18002c2ea  mov     rax, rbx
0x18002c2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2f2  mov     ebx, eax
0x18002c2f4  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c2f8  test    eax, eax
0x18002c2fa  jns     short loc_18002C303
0x18002c2fc  mov     edx, 0BAh
0x18002c301  jmp     short loc_18002C2AA
0x18002c303  mov     [rsp+220h+var_1B8], 0
0x18002c30c  mov     rax, [r13+0]
0x18002c310  lea     rcx, [rsp+220h+var_1B8]
0x18002c315  mov     [rbp+120h+var_138], rcx
0x18002c319  mov     [rbp+120h+var_130], 0
0x18002c321  mov     [rbp+120h+var_128], 1
0x18002c325  lea     rdx, [rbp+120h+var_130]
0x18002c329  mov     rcx, r13
0x18002c32c  mov     rax, [rax+20h]
0x18002c330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c335  mov     ebx, eax
0x18002c337  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c33b  lea     rcx, [rbp+120h+var_138]
0x18002c33f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18002c344  test    ebx, ebx
0x18002c346  jns     short loc_18002C368
0x18002c348  mov     r9d, ebx; char *
0x18002c34b  mov     edx, 0BEh; void *
0x18002c350  lea     r8, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002c357  mov     rcx, [rbp+128h]; this
0x18002c35e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c363  jmp     loc_18002C8E5
0x18002c368  lea     rax, [rsp+220h+var_1C0+4]
0x18002c36d  mov     [rsp+220h+var_200], rax; int
0x18002c372  mov     r9, [rsp+220h+var_1B8]; unsigned __int16 *
0x18002c377  mov     r8, [rbp+120h+var_158]; unsigned __int16 *
0x18002c37b  mov     rdx, rsi; struct IIdentityProviderExecutionContext *
0x18002c37e  call    ?IsLocalConnected@UserIdKeyManagerImplementation@@AEAAJPEAVIIdentityProviderExecutionContext@@PEBG1AEA_N@Z; UserIdKeyManagerImplementation::IsLocalConnected(IIdentityProviderExecutionContext *,ushort const *,ushort const *,bool &)
0x18002c383  mov     ebx, eax
0x18002c385  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c389  test    eax, eax
0x18002c38b  jns     short loc_18002C397
0x18002c38d  mov     r9d, eax
0x18002c390  mov     edx, 0BFh
0x18002c395  jmp     short loc_18002C350
0x18002c397  lea     rcx, [rbp+120h+var_1A0]; void *
0x18002c39b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002c3a0  nop
0x18002c3a1  lea     r9, [rbp+120h+var_1A0]
0x18002c3a5  mov     r8, [rbp+120h+var_158]
0x18002c3a9  mov     rdx, rsi
0x18002c3ac  call    ?GetMessageForPinPrompt@UserIdKeyManagerImplementation@@AEAAJPEAVIIdentityProviderExecutionContext@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UserIdKeyManagerImplementation::GetMessageForPinPrompt(IIdentityProviderExecutionContext *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002c3b1  mov     ebx, eax
0x18002c3b3  mov     dword ptr [rsp+220h+var_1C0], eax
0x18002c3b7  test    eax, eax
0x18002c3b9  jns     short loc_18002C3DB
0x18002c3bb  mov     edx, 0C2h; void *
  ... truncated ...
```
