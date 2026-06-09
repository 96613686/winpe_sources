# EnableTimeZoneAutoUpdate

- ea: `0x18000bf20`
- end: `0x18000c3af`
- name: `EnableTimeZoneAutoUpdate`
- size: `1167`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010cac`

## callees

- `0x1800011e4`
- `0x18000166c`
- `0x1800031fc`
- `0x180003348`
- `0x1800045d4`
- `0x1800051f0`
- `0x180006844`
- `0x18000883c`
- `0x18000885c`
- `0x18000af24`
- `0x18000bc30`
- `0x18000bf20`
- `0x18000c3c0`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000c234`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000c234`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000c171`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000c171`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000c1b5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000c1b5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000c21b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000c21b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000bf9e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000bf9e`

## string_xrefs

- `0x18000c1ab`: `tzautoupdate`
- `0x18000bfae`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c062`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c0dc`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c184`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c1d0`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c2c7`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c387`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c263`: `tzautoupdate enabled via API.`
- `0x18000c0b0`: `Windows.Devices.Enumeration.DeviceAccessInformation`
- `0x18000bf77`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`

## pseudocode

```c
__int64 EnableTimeZoneAutoUpdate()
{
  __int64 v0; // rbx
  int ActivationFactory; // eax
  unsigned int LastError; // ebx
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, _QWORD, __int64 *); // rbx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  bool v10; // bl
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, __int64 *); // rbx
  SC_HANDLE v15; // rax
  const char *v16; // r9
  SC_HANDLE v17; // rax
  const char *v18; // r9
  SC_HANDLE v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  __int64 v27; // rdx
  int updated; // eax
  __int64 v30; // rdx
  int lpBinaryPathName; // [rsp+20h] [rbp-89h]
  int lpBinaryPathNamea; // [rsp+20h] [rbp-89h]
  SC_HANDLE v33; // [rsp+60h] [rbp-49h] BYREF
  int v34; // [rsp+68h] [rbp-41h] BYREF
  int v35; // [rsp+6Ch] [rbp-3Dh] BYREF
  SC_HANDLE v36; // [rsp+70h] [rbp-39h] BYREF
  __int64 v37; // [rsp+78h] [rbp-31h] BYREF
  __int64 v38; // [rsp+80h] [rbp-29h] BYREF
  __int64 v39; // [rsp+88h] [rbp-21h] BYREF
  __int64 v40; // [rsp+90h] [rbp-19h] BYREF
  __int64 v41; // [rsp+98h] [rbp-11h] BYREF
  const wchar_t *v42; // [rsp+A0h] [rbp-9h] BYREF
  int v43[2]; // [rsp+A8h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v45; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v41 = 0;
  v34 = 0;
  v40 = 0;
  v35 = 0;
  v45 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix52931714>::GetImpl'::`2'::impl) )
  {
    v38 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Devices.Enumeration.DeviceAccessInformation",
      0x34u,
      0x33u);
    v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>(
            v45,
            &v38);
    LastError = v11;
    if ( v11 >= 0 )
    {
      v13 = v38;
      v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v38 + 64LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      v11 = v14(v13, 6, &v40);
      LastError = v11;
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 64LL))(v40, &v35);
        LastError = v11;
        if ( v11 >= 0 )
        {
          v10 = v35 == 1;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
          goto LABEL_21;
        }
        v12 = 249;
      }
      else
      {
        v12 = 248;
      }
    }
    else
    {
      v12 = 246;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
      (const char *)(unsigned int)v11,
      lpBinaryPathName);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    goto LABEL_50;
  }
  v39 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
    0x46u,
    0x45u);
  v0 = v45;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  ActivationFactory = RoGetActivationFactory(v0, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v39);
  LastError = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v3 = v39;
    v37 = 0;
    v4 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v39 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18001EDF0);
    v6 = v4(v3, *(_QWORD *)(v5 + 24), &v37);
    LastError = v6;
    if ( v6 < 0 )
    {
      v7 = 236;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
        (const char *)(unsigned int)v6,
        lpBinaryPathName);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      goto LABEL_11;
    }
    v8 = v37;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    v6 = v9(v8, &v41);
    LastError = v6;
    if ( v6 < 0 )
    {
      v7 = 238;
      goto LABEL_10;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 88LL))(v41, &v34);
    LastError = v6;
    if ( v6 < 0 )
    {
      v7 = 239;
      goto LABEL_10;
    }
    v10 = v34 == 1;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
LABEL_21:
    if ( v10 )
    {
      v15 = OpenSCManagerW(0, 0, 0xF003Fu);
      v33 = v15;
      if ( !v15 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x100,
                      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
                      v16);
LABEL_24:
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v33);
        goto LABEL_50;
      }
      v17 = OpenServiceW(v15, L"tzautoupdate", 0xF01FFu);
      v36 = v17;
      v19 = v17;
      if ( !v17 )
      {
        v20 = 259;
LABEL_27:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v20,
                      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
                      v18);
LABEL_28:
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v36);
        goto LABEL_24;
      }
      if ( !ChangeServiceConfigW(v17, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        v20 = 272;
        goto LABEL_27;
      }
      if ( !StartServiceW(v19, 0, 0) )
      {
        v20 = 274;
        goto LABEL_27;
      }
      if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v21, 0x400000000000LL, v22) )
      {
        *(_QWORD *)v43 = 0x1000000;
        v42 = L"tzautoupdate enabled via API.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v23,
          (unsigned int)&word_18002826E,
          v24,
          v25,
          (__int64)v43,
          (__int64)&v42);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix52931714>::GetImpl'::`2'::impl) )
      {
        v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 88LL))(v41, &v34);
        LastError = v26;
        if ( v26 < 0 )
        {
          v27 = 287;
LABEL_39:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
            (const char *)(unsigned int)v26,
            lpBinaryPathNamea);
          goto LABEL_28;
        }
        if ( v34 != 1 )
        {
          v26 = DisableTimeZoneAutoUpdate();
          LastError = v26;
          if ( v26 < 0 )
          {
            v27 = 290;
            goto LABEL_39;
          }
        }
      }
      else
      {
        v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 64LL))(v40, &v35);
        LastError = v26;
        if ( v26 < 0 )
        {
          v27 = 295;
          goto LABEL_39;
        }
        if ( v35 != 1 )
        {
          v26 = DisableTimeZoneAutoUpdate();
          LastError = v26;
          if ( v26 < 0 )
          {
            v27 = 298;
            goto LABEL_39;
          }
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v36);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v33);
LABEL_49:
      LastError = 0;
      goto LABEL_50;
    }
    LODWORD(v33) = 0;
    updated = IsTimeZoneAutoUpdateEnabled(&v33);
    LastError = updated;
    if ( updated >= 0 )
    {
      if ( !(_DWORD)v33 )
        goto LABEL_49;
      updated = DisableTimeZoneAutoUpdate();
      LastError = updated;
      if ( updated >= 0 )
        goto LABEL_49;
      v30 = 310;
    }
    else
    {
      v30 = 305;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
      (const char *)(unsigned int)updated,
      lpBinaryPathName);
    goto LABEL_50;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE9,
    (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
    (const char *)(unsigned int)ActivationFactory,
    lpBinaryPathName);
LABEL_11:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
  return LastError;
}

```

## disassembly

```asm
0x18000bf20  push    rbp
0x18000bf22  push    rbx
0x18000bf23  push    rsi
0x18000bf24  push    rdi
0x18000bf25  lea     rbp, [rsp-3Fh]
0x18000bf2a  sub     rsp, 0E8h
0x18000bf31  mov     rax, cs:__security_cookie
0x18000bf38  xor     rax, rsp
0x18000bf3b  mov     [rbp+57h+var_30], rax
0x18000bf3f  xor     esi, esi
0x18000bf41  mov     [rbp+57h+var_68], rsi
0x18000bf45  mov     [rbp+57h+var_98], esi
0x18000bf48  mov     [rbp+57h+var_70], rsi
0x18000bf4c  mov     [rbp+57h+var_94], esi
0x18000bf4f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix52931714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix52931714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714> `wil::Feature<__WilFeatureTraits_Feature_BugFix52931714>::GetImpl(void)'::`2'::impl
0x18000bf56  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix52931714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::__private_IsEnabled(void)
0x18000bf5b  mov     [rbp+57h+var_38], rsi
0x18000bf5f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000bf63  test    al, al
0x18000bf65  jz      loc_18000C0A6
0x18000bf6b  lea     r9d, [rsi+45h]; unsigned int
0x18000bf6f  mov     [rbp+57h+var_78], rsi
0x18000bf73  lea     r8d, [rsi+46h]; unsigned int
0x18000bf77  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x18000bf7e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000bf83  mov     rbx, [rbp+57h+var_38]
0x18000bf87  lea     rcx, [rbp+57h+var_78]
0x18000bf8b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000bf90  lea     r8, [rbp+57h+var_78]
0x18000bf94  mov     rcx, rbx
0x18000bf97  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x18000bf9e  call    cs:__imp_RoGetActivationFactory
0x18000bfa4  mov     ebx, eax
0x18000bfa6  test    eax, eax
0x18000bfa8  jns     short loc_18000BFC7
0x18000bfaa  mov     rcx, [rbp+5Fh]; this
0x18000bfae  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000bfb5  mov     r9d, eax; char *
0x18000bfb8  mov     edx, 0E9h; void *
0x18000bfbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bfc2  jmp     loc_18000C07A
0x18000bfc7  mov     rdi, [rbp+57h+var_78]
0x18000bfcb  lea     rcx, [rbp+57h+var_88]
0x18000bfcf  mov     [rbp+57h+var_88], rsi
0x18000bfd3  mov     rax, [rdi]
0x18000bfd6  mov     rbx, [rax+30h]
0x18000bfda  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000bfdf  lea     rdx, off_18001EDF0; "location"
0x18000bfe6  lea     rcx, [rbp+57h+hstringHeader]
0x18000bfea  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18000bfef  lea     r8, [rbp+57h+var_88]
0x18000bff3  mov     rcx, rdi
0x18000bff6  mov     rdx, [rax+18h]
0x18000bffa  mov     rax, rbx
0x18000bffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c002  mov     ebx, eax
0x18000c004  test    eax, eax
0x18000c006  jns     short loc_18000C00F
0x18000c008  mov     edx, 0ECh
0x18000c00d  jmp     short loc_18000C05E
0x18000c00f  mov     rdi, [rbp+57h+var_88]
0x18000c013  lea     rcx, [rbp+57h+var_68]
0x18000c017  mov     rax, [rdi]
0x18000c01a  mov     rbx, [rax+30h]
0x18000c01e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c023  lea     rdx, [rbp+57h+var_68]
0x18000c027  mov     rcx, rdi
0x18000c02a  mov     rax, rbx
0x18000c02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c032  mov     ebx, eax
0x18000c034  test    eax, eax
0x18000c036  jns     short loc_18000C03F
0x18000c038  mov     edx, 0EEh
0x18000c03d  jmp     short loc_18000C05E
0x18000c03f  mov     rcx, [rbp+57h+var_68]
0x18000c043  lea     rdx, [rbp+57h+var_98]
0x18000c047  mov     rax, [rcx]
0x18000c04a  mov     rax, [rax+58h]
0x18000c04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c053  mov     ebx, eax
0x18000c055  test    eax, eax
0x18000c057  jns     short loc_18000C088
0x18000c059  mov     edx, 0EFh; void *
0x18000c05e  mov     rcx, [rbp+5Fh]; this
0x18000c062  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c069  mov     r9d, eax; char *
0x18000c06c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c071  lea     rcx, [rbp+57h+var_88]
0x18000c075  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c07a  lea     rcx, [rbp+57h+var_78]
0x18000c07e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c083  jmp     loc_18000C340
0x18000c088  cmp     [rbp+57h+var_98], 1
0x18000c08c  lea     rcx, [rbp+57h+var_88]
0x18000c090  setz    bl
0x18000c093  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c098  lea     rcx, [rbp+57h+var_78]
0x18000c09c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c0a1  jmp     loc_18000C15F
0x18000c0a6  mov     r9d, 33h ; '3'; unsigned int
0x18000c0ac  mov     [rbp+57h+var_80], rsi
0x18000c0b0  lea     rdx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceAccessInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceAcces"...
0x18000c0b7  lea     r8d, [r9+1]; unsigned int
0x18000c0bb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000c0c0  mov     rcx, [rbp+57h+var_38]
0x18000c0c4  lea     rdx, [rbp+57h+var_80]
0x18000c0c8  call    ??$GetActivationFactory@V?$ComPtr@UIDeviceAccessInformationStatics@Enumeration@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDeviceAccessInformationStatics@Enumeration@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>)
0x18000c0cd  mov     ebx, eax
0x18000c0cf  test    eax, eax
0x18000c0d1  jns     short loc_18000C0F9
0x18000c0d3  mov     edx, 0F6h; void *
0x18000c0d8  mov     rcx, [rbp+5Fh]; this
0x18000c0dc  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c0e3  mov     r9d, eax; char *
0x18000c0e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c0eb  lea     rcx, [rbp+57h+var_80]
0x18000c0ef  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c0f4  jmp     loc_18000C340
0x18000c0f9  mov     rdi, [rbp+57h+var_80]
0x18000c0fd  lea     rcx, [rbp+57h+var_70]
0x18000c101  mov     rax, [rdi]
0x18000c104  mov     rbx, [rax+40h]
0x18000c108  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c10d  lea     r8, [rbp+57h+var_70]
0x18000c111  mov     edx, 6
0x18000c116  mov     rcx, rdi
0x18000c119  mov     rax, rbx
0x18000c11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c121  mov     ebx, eax
0x18000c123  test    eax, eax
0x18000c125  jns     short loc_18000C12E
0x18000c127  mov     edx, 0F8h
0x18000c12c  jmp     short loc_18000C0D8
0x18000c12e  mov     rcx, [rbp+57h+var_70]
0x18000c132  lea     rdx, [rbp+57h+var_94]
0x18000c136  mov     rax, [rcx]
0x18000c139  mov     rax, [rax+40h]
0x18000c13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c142  mov     ebx, eax
0x18000c144  test    eax, eax
0x18000c146  jns     short loc_18000C14F
0x18000c148  mov     edx, 0F9h
0x18000c14d  jmp     short loc_18000C0D8
0x18000c14f  cmp     [rbp+57h+var_94], 1
0x18000c153  lea     rcx, [rbp+57h+var_80]
0x18000c157  setz    bl
0x18000c15a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c15f  test    bl, bl
0x18000c161  jz      loc_18000C36C
0x18000c167  xor     edx, edx; lpDatabaseName
0x18000c169  xor     ecx, ecx; lpMachineName
0x18000c16b  mov     r8d, 0F003Fh; dwDesiredAccess
0x18000c171  call    cs:__imp_OpenSCManagerW
0x18000c177  mov     [rbp+57h+var_A0], rax
0x18000c17b  test    rax, rax
0x18000c17e  jnz     short loc_18000C1A5
0x18000c180  mov     rcx, [rbp+5Fh]; this
0x18000c184  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c18b  mov     edx, 100h; void *
0x18000c190  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c195  mov     ebx, eax
0x18000c197  lea     rcx, [rbp+57h+var_A0]
0x18000c19b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c1a0  jmp     loc_18000C340
0x18000c1a5  mov     r8d, 0F01FFh; dwDesiredAccess
0x18000c1ab  lea     rdx, ServiceName; "tzautoupdate"
0x18000c1b2  mov     rcx, rax; hSCManager
0x18000c1b5  call    cs:__imp_OpenServiceW
0x18000c1bb  mov     [rbp+57h+var_90], rax
0x18000c1bf  mov     rbx, rax
0x18000c1c2  test    rax, rax
0x18000c1c5  jnz     short loc_18000C1E9
0x18000c1c7  mov     edx, 103h; void *
0x18000c1cc  mov     rcx, [rbp+5Fh]; this
0x18000c1d0  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c1d7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c1dc  mov     ebx, eax
0x18000c1de  lea     rcx, [rbp+57h+var_90]
0x18000c1e2  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c1e7  jmp     short loc_18000C197
0x18000c1e9  mov     [rsp+100h+lpDisplayName], rsi; lpDisplayName
0x18000c1ee  or      edx, 0FFFFFFFFh; dwServiceType
0x18000c1f1  mov     [rsp+100h+lpPassword], rsi; lpPassword
0x18000c1f6  mov     r9d, edx; dwErrorControl
0x18000c1f9  mov     [rsp+100h+lpServiceStartName], rsi; lpServiceStartName
0x18000c1fe  mov     r8d, 3; dwStartType
0x18000c204  mov     [rsp+100h+lpDependencies], rsi; lpDependencies
0x18000c209  mov     rcx, rbx; hService
0x18000c20c  mov     [rsp+100h+lpdwTagId], rsi; lpdwTagId
0x18000c211  mov     [rsp+100h+lpLoadOrderGroup], rsi; lpLoadOrderGroup
0x18000c216  mov     [rsp+100h+lpBinaryPathName], rsi; lpBinaryPathName
0x18000c21b  call    cs:__imp_ChangeServiceConfigW
0x18000c221  test    eax, eax
0x18000c223  jnz     short loc_18000C22C
0x18000c225  mov     edx, 110h
0x18000c22a  jmp     short loc_18000C1CC
0x18000c22c  xor     r8d, r8d; lpServiceArgVectors
0x18000c22f  xor     edx, edx; dwNumServiceArgs
0x18000c231  mov     rcx, rbx; hService
0x18000c234  call    cs:__imp_StartServiceW
0x18000c23a  test    eax, eax
0x18000c23c  jnz     short loc_18000C245
0x18000c23e  mov     edx, 112h
0x18000c243  jmp     short loc_18000C1CC
0x18000c245  mov     eax, cs:dword_180030000
0x18000c24b  cmp     eax, 5
0x18000c24e  jbe     short loc_18000C294
0x18000c250  mov     rdx, 400000000000h
0x18000c25a  call    _tlgKeywordOn
0x18000c25f  test    al, al
0x18000c261  jz      short loc_18000C294
0x18000c263  lea     rax, aTzautoupdateEn; "tzautoupdate enabled via API."
0x18000c26a  mov     qword ptr [rbp+57h+var_58], 1000000h
0x18000c272  mov     [rbp+57h+var_60], rax
0x18000c276  lea     rdx, word_18002826E
0x18000c27d  lea     rax, [rbp+57h+var_60]
0x18000c281  mov     [rsp+100h+lpLoadOrderGroup], rax
0x18000c286  lea     rax, [rbp+57h+var_58]
0x18000c28a  mov     [rsp+100h+lpBinaryPathName], rax; int
0x18000c28f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000c294  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix52931714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix52931714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714> `wil::Feature<__WilFeatureTraits_Feature_BugFix52931714>::GetImpl(void)'::`2'::impl
0x18000c29b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix52931714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::__private_IsEnabled(void)
0x18000c2a0  test    al, al
0x18000c2a2  jz      short loc_18000C2F3
0x18000c2a4  mov     rcx, [rbp+57h+var_68]
0x18000c2a8  lea     rdx, [rbp+57h+var_98]
0x18000c2ac  mov     rax, [rcx]
0x18000c2af  mov     rax, [rax+58h]
0x18000c2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2b8  mov     ebx, eax
0x18000c2ba  test    eax, eax
0x18000c2bc  jns     short loc_18000C2DB
0x18000c2be  mov     edx, 11Fh; void *
0x18000c2c3  mov     rcx, [rbp+5Fh]; this
0x18000c2c7  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c2ce  mov     r9d, eax; char *
0x18000c2d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c2d6  jmp     loc_18000C1DE
0x18000c2db  cmp     [rbp+57h+var_98], 1
0x18000c2df  jz      short loc_18000C32C
0x18000c2e1  call    DisableTimeZoneAutoUpdate
0x18000c2e6  mov     ebx, eax
0x18000c2e8  test    eax, eax
0x18000c2ea  jns     short loc_18000C32C
0x18000c2ec  mov     edx, 122h
0x18000c2f1  jmp     short loc_18000C2C3
0x18000c2f3  mov     rcx, [rbp+57h+var_70]
0x18000c2f7  lea     rdx, [rbp+57h+var_94]
0x18000c2fb  mov     rax, [rcx]
0x18000c2fe  mov     rax, [rax+40h]
0x18000c302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c307  mov     ebx, eax
0x18000c309  test    eax, eax
0x18000c30b  jns     short loc_18000C314
0x18000c30d  mov     edx, 127h
0x18000c312  jmp     short loc_18000C2C3
0x18000c314  cmp     [rbp+57h+var_94], 1
0x18000c318  jz      short loc_18000C32C
0x18000c31a  call    DisableTimeZoneAutoUpdate
0x18000c31f  mov     ebx, eax
0x18000c321  test    eax, eax
0x18000c323  jns     short loc_18000C32C
0x18000c325  mov     edx, 12Ah
0x18000c32a  jmp     short loc_18000C2C3
0x18000c32c  lea     rcx, [rbp+57h+var_90]
0x18000c330  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c335  lea     rcx, [rbp+57h+var_A0]
0x18000c339  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c33e  mov     ebx, esi
0x18000c340  lea     rcx, [rbp+57h+var_70]
0x18000c344  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c349  lea     rcx, [rbp+57h+var_68]
0x18000c34d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c352  mov     eax, ebx
0x18000c354  mov     rcx, [rbp+57h+var_30]
0x18000c358  xor     rcx, rsp; StackCookie
0x18000c35b  call    __security_check_cookie
0x18000c360  add     rsp, 0E8h
0x18000c367  pop     rdi
0x18000c368  pop     rsi
0x18000c369  pop     rbx
0x18000c36a  pop     rbp
0x18000c36b  retn
0x18000c36c  lea     rcx, [rbp+57h+var_A0]
0x18000c370  mov     dword ptr [rbp+57h+var_A0], esi
0x18000c373  call    IsTimeZoneAutoUpdateEnabled
0x18000c378  mov     ebx, eax
0x18000c37a  test    eax, eax
0x18000c37c  jns     short loc_18000C398
0x18000c37e  mov     edx, 131h; void *
0x18000c383  mov     rcx, [rbp+5Fh]; this
0x18000c387  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c38e  mov     r9d, eax; char *
0x18000c391  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c396  jmp     short loc_18000C340
0x18000c398  cmp     dword ptr [rbp+57h+var_A0], esi
0x18000c39b  jz      short loc_18000C33E
0x18000c39d  call    DisableTimeZoneAutoUpdate
0x18000c3a2  mov     ebx, eax
0x18000c3a4  test    eax, eax
  ... truncated ...
```
