# CBrokeredLauncher::CLaunchHelper::_IsUriLaunchAllowed(IShellItem *,ushort const *,ushort const *,ushort const *)

- ea: `0x180057b4c`
- end: `0x180058340`
- name: `?_IsUriLaunchAllowed@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIShellItem@@PEBG11@Z`
- size: `2036`
- prototype: `__int64 __fastcall(CBrokeredLauncher::CLaunchHelper *this, struct IShellItem *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *wszServerName)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180057574`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18003f59c`
- `0x18004966c`
- `0x1800528cc`
- `0x180054774`
- `0x180057b4c`
- `0x1800591d4`
- `0x1800595c8`
- `0x180068e34`
- `0x18006c02c`
- `0x1800717d0`
- `0x18007322c`
- `0x180073ab0`
- `0x180076b2c`
- `0x18008a030`
- `0x18008a9d8`
- `0x1800a1670`
- `0x1800e8594`
- `0x1800ea2d0`
- `0x1800ec7c0`
- `0x1800ee2f0`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057f26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057f26`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057ece`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057ece`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180057f07`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180057f07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057d49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057d49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058024`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180057dff`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180057dff`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180057d6d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180057d6d`
- `api-ms-win-net-isolation-l1-1-0!NetworkIsolationDiagnoseConnectFailureAndGetInfo` at `0x180057d9e`
- `api-ms-win-net-isolation-l1-1-0!NetworkIsolationDiagnoseConnectFailureAndGetInfo` at `0x180057d9e`

## string_xrefs

- `0x180058057`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005806c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800580c3`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800580d8`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800580ed`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058101`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058116`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005812a`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058181`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800581d8`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005822f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058286`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800582dd`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800582f2`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058306`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005832d`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
__int64 __fastcall CBrokeredLauncher::CLaunchHelper::_IsUriLaunchAllowed(
        CBrokeredLauncher::CLaunchHelper *this,
        struct IShellItem *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *wszServerName)
{
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  char v9; // r13
  int v10; // eax
  struct IAssociationArray *v11; // rbx
  int IsFileLaunchAllowed; // eax
  HRESULT v13; // eax
  int Error; // eax
  signed int Info; // eax
  signed int v16; // esi
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  HANDLE FileW; // rsi
  HRESULT (__stdcall *BindToHandler)(IShellItem *, IBindCtx *, const GUID *const, const IID *const, void **); // rbx
  int v22; // eax
  const unsigned __int16 *v23; // rdx
  CBrokeredLauncher::CLaunchHelper *v24; // rcx
  int v25; // eax
  const char *v26; // r9
  __int64 result; // rax
  HINSTANCE ModuleHINSTANCE; // rax
  __int64 v29; // rcx
  unsigned int v30; // eax
  HINSTANCE v31; // rax
  unsigned int v32; // eax
  HINSTANCE v33; // rax
  unsigned int v34; // eax
  HINSTANCE v35; // rax
  unsigned int v36; // eax
  HINSTANCE v37; // rax
  unsigned int v38; // eax
  HINSTANCE v39; // rax
  unsigned int v40; // eax
  unsigned int v41; // eax
  int ppv; // [rsp+20h] [rbp-148h]
  int ppva; // [rsp+20h] [rbp-148h]
  char v44; // [rsp+40h] [rbp-128h]
  int v45; // [rsp+44h] [rbp-124h] BYREF
  struct IAssociationArray *v46; // [rsp+48h] [rbp-120h] BYREF
  NETISO_ERROR_TYPE netIsoError[2]; // [rsp+50h] [rbp-118h] BYREF
  LPVOID v48; // [rsp+58h] [rbp-110h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-108h] BYREF
  unsigned __int16 *v50; // [rsp+68h] [rbp-100h] BYREF
  __int64 v51; // [rsp+70h] [rbp-F8h]
  __int64 v52; // [rsp+78h] [rbp-F0h]
  PROPERTYKEY v53; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE FileInformation[128]; // [rsp+A0h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v46 = this;
  try
  {
    if ( IsLaunchApiDisabledByLockdown() )
    {
      v41 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7F1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)v41,
        ppv);
    }
    lpFileName = 0;
    GetDisplayName = a2->lpVtbl->GetDisplayName;
    CoTaskMemFree(0);
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPCWSTR *))GetDisplayName)(a2, 2147844096LL, &lpFileName) < 0 )
    {
      v9 = 0;
    }
    else
    {
      v9 = 1;
      if ( !(unsigned int)IShellItem_IsFolder(a2) )
      {
        *(_QWORD *)netIsoError = 0;
        v10 = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(netIsoError, a2, 8);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x756,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)v10,
            ppv);
        v50 = 0;
        v51 = 0;
        v52 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
        v51 = -1;
        v52 = -1;
        v53 = PKEY_FileExtension;
        if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(netIsoError, &v53, &v50) < 0
          || !v50
          || !*v50 )
        {
          LauncherDesktopProvider::MissingFileExtension();
          ModuleHINSTANCE = GetModuleHINSTANCE();
          OriginateErrorWithResourceString(-2147024809, ModuleHINSTANCE, 0x2CF0u);
          if ( (byte_1801613C1 & 1) != 0 )
            McTemplateU0_EventWriteTransfer(v29, AssociationLaunch_UriLaunch_MissingFileExtension);
          v30 = wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x764,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)v30,
            ppv);
        }
        v11 = v46;
        IsFileLaunchAllowed = CBrokeredLauncher::CLaunchHelper::_IsFileLaunchAllowed(
                                v46,
                                a2,
                                v50,
                                *((_BYTE *)v46 + 88),
                                1);
        if ( IsFileLaunchAllowed < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x75D,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)IsFileLaunchAllowed,
            ppv);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
        if ( *(_QWORD *)netIsoError )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)netIsoError + 16LL))(*(_QWORD *)netIsoError);
LABEL_14:
        if ( CBrokeredLauncher::CLaunchHelper::_StringEquals(a4, L"http")
          || CBrokeredLauncher::CLaunchHelper::_StringEquals(a4, L"https")
          || CBrokeredLauncher::CLaunchHelper::_StringEquals(a4, L"ftp") )
        {
          v44 = 1;
        }
        else
        {
          v44 = 0;
          if ( !v9 )
          {
LABEL_18:
            v48 = 0;
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v48);
            v13 = CoCreateInstance(
                    &CLSID_InternetSecurityManager,
                    0,
                    1u,
                    &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                    &v48);
            if ( v13 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x788,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                (const char *)(unsigned int)v13,
                ppva);
            v45 = 0;
            v17 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, int *, __int64))(*(_QWORD *)v48 + 40LL))(
                    v48,
                    a3,
                    &v45,
                    8193);
            if ( v17 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x792,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                (const char *)(unsigned int)v17,
                ppva);
            v18 = v45;
            if ( ((v45 - 2) & 0xFFFFFFFD) == 0 )
            {
              v19 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, int *, __int64))(*(_QWORD *)v48 + 40LL))(
                      v48,
                      a3,
                      &v45,
                      24577);
              if ( v19 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x799,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                  (const char *)(unsigned int)v19,
                  ppva);
              v18 = v45;
            }
            if ( !v18 )
            {
              v31 = GetModuleHINSTANCE();
              OriginateErrorWithResourceString(-2147024891, v31, 0x2CF4u);
              if ( (byte_1801613C1 & 1) != 0 )
                McTemplateU0z_EventWriteTransfer(
                  MICROSOFT_TWINUI_PUBLISHER_Context,
                  AssociationLaunch_UriLaunch_LocalZoneBlocked,
                  a3);
              v32 = wil::verify_hresult<long>(2147942405LL);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x7A0,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                (const char *)v32,
                ppva);
            }
            if ( v18 == 1 )
            {
              if ( v9 )
              {
                FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
                if ( FileW != (HANDLE)-1LL )
                {
                  memset_0(FileInformation, 0, 0x74u);
                  if ( !GetFileInformationByHandleEx(FileW, FileRemoteProtocolInfo, FileInformation, 0x74u) )
                  {
                    v37 = GetModuleHINSTANCE();
                    OriginateErrorWithResourceString(-2147024891, v37, 0x2CF4u);
                    if ( (byte_1801613C1 & 1) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        MICROSOFT_TWINUI_PUBLISHER_Context,
                        AssociationLaunch_UriLaunch_LocalZoneBlocked,
                        a3);
                    v38 = wil::verify_hresult<long>(2147942405LL);
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7C4,
                      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                      (const char *)v38,
                      ppva);
                  }
                  if ( (FileInformation[16] & 1) != 0 )
                  {
                    v33 = GetModuleHINSTANCE();
                    OriginateErrorWithResourceString(-2147024891, v33, 0x2CF4u);
                    if ( (byte_1801613C1 & 1) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        MICROSOFT_TWINUI_PUBLISHER_Context,
                        AssociationLaunch_UriLaunch_LocalZoneBlocked,
                        a3);
                    v34 = wil::verify_hresult<long>(2147942405LL);
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7BC,
                      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                      (const char *)v34,
                      ppva);
                  }
                  CloseHandle(FileW);
                }
              }
              if ( !v44 && !*((_BYTE *)v46 + 80) )
              {
                v35 = GetModuleHINSTANCE();
                OriginateErrorWithResourceString(-2147024891, v35, 0x2CF3u);
                if ( (byte_1801613C1 & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(
                    MICROSOFT_TWINUI_PUBLISHER_Context,
                    AssociationLaunch_UriLaunch_MissingIntranetCapability,
                    a3);
                v36 = wil::verify_hresult<long>(2147942405LL);
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x7D3,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                  (const char *)v36,
                  ppva);
              }
            }
            else if ( v9 )
            {
              v39 = GetModuleHINSTANCE();
              OriginateErrorWithResourceString(-2147024891, v39, 0x2CF5u);
              if ( (byte_1801613C1 & 1) != 0 )
                McTemplateU0z_EventWriteTransfer(
                  MICROSOFT_TWINUI_PUBLISHER_Context,
                  AssociationLaunch_UriLaunch_UntrustedFileBlocked,
                  a3);
              v40 = wil::verify_hresult<long>(2147942405LL);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x7E2,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                (const char *)v40,
                ppva);
            }
            if ( !CBrokeredLauncher::CLaunchHelper::_StringEquals(a4, L"http")
              && !CBrokeredLauncher::CLaunchHelper::_StringEquals(a4, L"https")
              && !CBrokeredLauncher::CLaunchHelper::_StringEquals(a4, L"mailto") )
            {
              v46 = 0;
              BindToHandler = a2->lpVtbl->BindToHandler;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
              v22 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *))BindToHandler)(
                      a2,
                      0,
                      &BHID_AssociationArray,
                      &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f);
              if ( v22 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x7E9,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                  (const char *)(unsigned int)v22,
                  (int)&v46);
              if ( IsVerbHandlerAppxPackaged(v46, v23) )
                v25 = 0;
              else
                v25 = CBrokeredLauncher::CLaunchHelper::_CheckElevatedLaunchAllowed(v24, 0);
              if ( v25 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x7EA,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                  (const char *)(unsigned int)v25,
                  (int)&v46);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
            }
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v48);
            CoTaskMemFree((LPVOID)lpFileName);
            return 0;
          }
        }
        if ( ImpersonateLoggedOnUser(*((HANDLE *)v11 + 6)) )
          Error = 0;
        else
          Error = ResultFromKnownLastError();
        if ( Error < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x773,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)Error,
            ppv);
        netIsoError[0] = NETISO_ERROR_TYPE_NONE;
        Info = NetworkIsolationDiagnoseConnectFailureAndGetInfo(wszServerName, netIsoError);
        v16 = Info;
        if ( Info > 0 )
          v16 = (unsigned __int16)Info | 0x80070000;
        if ( v16 >= 0 && netIsoError[0] == NETISO_ERROR_TYPE_PRIVATE_NETWORK )
        {
          v16 = -2147024891;
          OriginateErrorWithResourceString(-2147024891, &_ImageBase, 0x2CF3u);
          if ( (byte_1801613C1 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              MICROSOFT_TWINUI_PUBLISHER_Context,
              AssociationLaunch_UriLaunch_MissingIntranetCapability,
              a3);
        }
        RevertToSelf();
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x77E,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)v16,
            ppv);
        goto LABEL_18;
      }
    }
    v11 = v46;
    goto LABEL_14;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7F4,
                           (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x180057b4c  push    rbx
0x180057b4e  push    rsi
0x180057b4f  push    r12
0x180057b51  push    r13
0x180057b53  push    r14
0x180057b55  push    r15
0x180057b57  sub     rsp, 138h
0x180057b5e  mov     rax, cs:__security_cookie
0x180057b65  xor     rax, rsp
0x180057b68  mov     [rsp+168h+var_48], rax
0x180057b70  mov     r15, r9
0x180057b73  mov     r14, r8
0x180057b76  mov     r12, rdx
0x180057b79  mov     [rsp+168h+var_120], rcx
0x180057b7e  mov     rsi, [rsp+168h+wszServerName]
0x180057b86  call    ?IsLaunchApiDisabledByLockdown@@YA_NXZ; IsLaunchApiDisabledByLockdown(void)
0x180057b8b  xor     ecx, ecx; pv
0x180057b8d  test    al, al
0x180057b8f  jnz     loc_180058318
0x180057b95  mov     [rsp+168h+lpFileName], rcx
0x180057b9a  mov     rax, [r12]
0x180057b9e  mov     rbx, [rax+28h]
0x180057ba2  call    cs:__imp_CoTaskMemFree
0x180057ba8  lea     r8, [rsp+168h+lpFileName]
0x180057bad  mov     edx, 80058000h
0x180057bb2  mov     rcx, r12
0x180057bb5  mov     rax, rbx
0x180057bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bbd  xor     ebx, ebx
0x180057bbf  test    eax, eax
0x180057bc1  js      loc_180057CCB
0x180057bc7  mov     r13b, 1
0x180057bca  mov     rcx, r12; struct IShellItem *
0x180057bcd  call    ?IShellItem_IsFolder@@YAHPEAUIShellItem@@@Z; IShellItem_IsFolder(IShellItem *)
0x180057bd2  test    eax, eax
0x180057bd4  jnz     loc_180057CCE
0x180057bda  mov     qword ptr [rsp+168h+netIsoError], rbx
0x180057bdf  lea     r8d, [rbx+8]
0x180057be3  mov     rdx, r12
0x180057be6  lea     rcx, [rsp+168h+netIsoError]
0x180057beb  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x180057bf0  mov     rcx, [rsp+168h]; this
0x180057bf8  test    eax, eax
0x180057bfa  js      loc_180058054
0x180057c00  mov     [rsp+168h+var_100], rbx
0x180057c05  mov     [rsp+168h+var_F8], rbx
0x180057c0a  mov     [rsp+168h+var_F0], rbx
0x180057c0f  lea     rcx, [rsp+168h+var_100]
0x180057c14  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180057c19  mov     [rsp+168h+var_F8], 0FFFFFFFFFFFFFFFFh
0x180057c22  mov     [rsp+168h+var_F0], 0FFFFFFFFFFFFFFFFh
0x180057c2b  movups  xmm0, xmmword ptr cs:PKEY_FileExtension.fmtid.Data1
0x180057c32  movaps  [rsp+168h+var_E8], xmm0
0x180057c3a  mov     eax, cs:PKEY_FileExtension.pid
0x180057c40  mov     [rsp+168h+var_D8], eax
0x180057c47  lea     r8, [rsp+168h+var_100]
0x180057c4c  lea     rdx, [rsp+168h+var_E8]
0x180057c54  lea     rcx, [rsp+168h+netIsoError]
0x180057c59  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180057c5e  test    eax, eax
0x180057c60  js      loc_18005807D
0x180057c66  mov     r8, [rsp+168h+var_100]; unsigned __int16 *
0x180057c6b  test    r8, r8
0x180057c6e  jz      loc_18005807D
0x180057c74  cmp     [r8], bx
0x180057c78  jz      loc_18005807D
0x180057c7e  mov     byte ptr [rsp+168h+ppv], 1; int
0x180057c83  mov     rbx, [rsp+168h+var_120]
0x180057c88  mov     r9b, [rbx+58h]; bool
0x180057c8c  mov     rdx, r12; struct IShellItem *
0x180057c8f  mov     rcx, rbx; this
0x180057c92  call    ?_IsFileLaunchAllowed@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIShellItem@@PEBG_N2@Z; CBrokeredLauncher::CLaunchHelper::_IsFileLaunchAllowed(IShellItem *,ushort const *,bool,bool)
0x180057c97  mov     rcx, [rsp+168h]; this
0x180057c9f  test    eax, eax
0x180057ca1  js      loc_180058069
0x180057ca7  lea     rcx, [rsp+168h+var_100]
0x180057cac  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180057cb1  nop
0x180057cb2  mov     rcx, qword ptr [rsp+168h+netIsoError]
0x180057cb7  test    rcx, rcx
0x180057cba  jz      short loc_180057CC9
0x180057cbc  mov     rax, [rcx]
0x180057cbf  mov     rax, [rax+10h]
0x180057cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057cc8  nop
0x180057cc9  jmp     short loc_180057CD3
0x180057ccb  mov     r13b, bl
0x180057cce  mov     rbx, [rsp+168h+var_120]
0x180057cd3  lea     rdx, pszStr2; "http"
0x180057cda  mov     rcx, r15; lpString1
0x180057cdd  call    ?_StringEquals@CLaunchHelper@CBrokeredLauncher@@CA_NPEBG0@Z; CBrokeredLauncher::CLaunchHelper::_StringEquals(ushort const *,ushort const *)
0x180057ce2  test    al, al
0x180057ce4  jnz     short loc_180057D64
0x180057ce6  lea     rdx, aHttps_0; "https"
0x180057ced  mov     rcx, r15; lpString1
0x180057cf0  call    ?_StringEquals@CLaunchHelper@CBrokeredLauncher@@CA_NPEBG0@Z; CBrokeredLauncher::CLaunchHelper::_StringEquals(ushort const *,ushort const *)
0x180057cf5  test    al, al
0x180057cf7  jnz     short loc_180057D64
0x180057cf9  lea     rdx, aFtp; "ftp"
0x180057d00  mov     rcx, r15; lpString1
0x180057d03  call    ?_StringEquals@CLaunchHelper@CBrokeredLauncher@@CA_NPEBG0@Z; CBrokeredLauncher::CLaunchHelper::_StringEquals(ushort const *,ushort const *)
0x180057d08  test    al, al
0x180057d0a  jnz     short loc_180057D64
0x180057d0c  mov     [rsp+168h+var_128], al
0x180057d10  test    r13b, r13b
0x180057d13  jnz     short loc_180057D69
0x180057d15  mov     ebx, 80070005h
0x180057d1a  xor     esi, esi
0x180057d1c  mov     [rsp+168h+var_110], rsi
0x180057d21  lea     rcx, [rsp+168h+var_110]
0x180057d26  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180057d2b  lea     rax, [rsp+168h+var_110]
0x180057d30  mov     [rsp+168h+ppv], rax; int
0x180057d35  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180057d3c  xor     edx, edx; pUnkOuter
0x180057d3e  lea     r8d, [rsi+1]; dwClsContext
0x180057d42  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180057d49  call    cs:__imp_CoCreateInstance
0x180057d4f  mov     rcx, [rsp+168h]; this
0x180057d57  test    eax, eax
0x180057d59  js      loc_1800580D5
0x180057d5f  jmp     loc_180057E1A
0x180057d64  mov     [rsp+168h+var_128], 1
0x180057d69  mov     rcx, [rbx+30h]; hToken
0x180057d6d  call    cs:__imp_ImpersonateLoggedOnUser
0x180057d73  xor     ebx, ebx
0x180057d75  test    eax, eax
0x180057d77  jz      short loc_180057D7D
0x180057d79  mov     eax, ebx
0x180057d7b  jmp     short loc_180057D82
0x180057d7d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180057d82  mov     rcx, [rsp+168h]; this
0x180057d8a  test    eax, eax
0x180057d8c  js      loc_1800580EA
0x180057d92  mov     [rsp+168h+netIsoError], ebx
0x180057d96  lea     rdx, [rsp+168h+netIsoError]; netIsoError
0x180057d9b  mov     rcx, rsi; wszServerName
0x180057d9e  call    cs:__imp_NetworkIsolationDiagnoseConnectFailureAndGetInfo
0x180057da4  mov     esi, eax
0x180057da6  test    eax, eax
0x180057da8  jle     short loc_180057DB3
0x180057daa  movzx   esi, ax
0x180057dad  or      esi, 80070000h
0x180057db3  test    esi, esi
0x180057db5  js      short loc_180057DFA
0x180057db7  cmp     [rsp+168h+netIsoError], 1
0x180057dbc  jnz     short loc_180057DFA
0x180057dbe  mov     ebx, 80070005h
0x180057dc3  mov     esi, ebx
0x180057dc5  mov     r8d, 2CF3h; unsigned int
0x180057dcb  lea     rdx, __ImageBase; HINSTANCE
0x180057dd2  mov     ecx, ebx; int
0x180057dd4  call    ?OriginateErrorWithResourceString@@YAXJPEAUHINSTANCE__@@I@Z; OriginateErrorWithResourceString(long,HINSTANCE__ *,uint)
0x180057dd9  test    cs:byte_1801613C1, 1
0x180057de0  jz      short loc_180057DFF
0x180057de2  mov     r8, r14
0x180057de5  lea     rdx, AssociationLaunch_UriLaunch_MissingIntranetCapability
0x180057dec  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x180057df3  call    McTemplateU0z_EventWriteTransfer
0x180057df8  jmp     short loc_180057DFF
0x180057dfa  mov     ebx, 80070005h
0x180057dff  call    cs:__imp_RevertToSelf
0x180057e05  mov     rcx, [rsp+168h]; this
0x180057e0d  test    esi, esi
0x180057e0f  js      loc_1800580FE
0x180057e15  jmp     loc_180057D1A
0x180057e1a  mov     [rsp+168h+var_124], esi
0x180057e1e  mov     rcx, [rsp+168h+var_110]
0x180057e23  mov     rax, [rcx]
0x180057e26  mov     r9d, 2001h
0x180057e2c  lea     r8, [rsp+168h+var_124]
0x180057e31  mov     rdx, r14
0x180057e34  mov     rax, [rax+28h]
0x180057e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e3d  mov     rcx, [rsp+168h]; this
0x180057e45  test    eax, eax
0x180057e47  js      loc_180058113
0x180057e4d  mov     ecx, [rsp+168h+var_124]
0x180057e51  lea     eax, [rcx-2]
0x180057e54  test    eax, 0FFFFFFFDh
0x180057e59  jnz     short loc_180057E8E
0x180057e5b  mov     rcx, [rsp+168h+var_110]
0x180057e60  mov     rax, [rcx]
0x180057e63  mov     r9d, 6001h
0x180057e69  lea     r8, [rsp+168h+var_124]
0x180057e6e  mov     rdx, r14
0x180057e71  mov     rax, [rax+28h]
0x180057e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e7a  mov     rcx, [rsp+168h]; this
0x180057e82  test    eax, eax
0x180057e84  js      loc_180058127
0x180057e8a  mov     ecx, [rsp+168h+var_124]
0x180057e8e  test    ecx, ecx
0x180057e90  jz      loc_18005813B
0x180057e96  cmp     ecx, 1
0x180057e99  jnz     loc_180057F46
0x180057e9f  test    r13b, r13b
0x180057ea2  jz      loc_180057F2E
0x180057ea8  mov     [rsp+168h+hTemplateFile], rsi; hTemplateFile
0x180057ead  mov     [rsp+168h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180057eb5  mov     dword ptr [rsp+168h+ppv], 3; int
0x180057ebd  xor     r9d, r9d; lpSecurityAttributes
0x180057ec0  mov     edx, 80000000h; dwDesiredAccess
0x180057ec5  lea     r8d, [rcx+6]; dwShareMode
0x180057ec9  mov     rcx, [rsp+168h+lpFileName]; lpFileName
0x180057ece  call    cs:__imp_CreateFileW
0x180057ed4  mov     rsi, rax
0x180057ed7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180057edb  jz      short loc_180057F2C
0x180057edd  mov     r13d, 74h ; 't'
0x180057ee3  mov     r8d, r13d; Size
0x180057ee6  xor     edx, edx; Val
0x180057ee8  lea     rcx, [rsp+168h+FileInformation]; void *
0x180057ef0  call    memset_0
0x180057ef5  mov     r9d, r13d; dwBufferSize
0x180057ef8  lea     r8, [rsp+168h+FileInformation]; lpFileInformation
0x180057f00  lea     edx, [r13-67h]; FileInformationClass
0x180057f04  mov     rcx, rsi; hFile
0x180057f07  call    cs:__imp_GetFileInformationByHandleEx
0x180057f0d  test    eax, eax
0x180057f0f  jz      loc_180058240
0x180057f15  test    [rsp+168h+var_B8], 1
0x180057f1d  jnz     loc_180058192
0x180057f23  mov     rcx, rsi; hObject
0x180057f26  call    cs:__imp_CloseHandle
0x180057f2c  xor     esi, esi
0x180057f2e  cmp     [rsp+168h+var_128], sil
0x180057f33  jnz     short loc_180057F4F
0x180057f35  mov     rcx, [rsp+168h+var_120]
0x180057f3a  cmp     [rcx+50h], sil
0x180057f3e  jz      loc_1800581E9
0x180057f44  jmp     short loc_180057F4F
0x180057f46  test    r13b, r13b
0x180057f49  jnz     loc_180058297
0x180057f4f  lea     rdx, pszStr2; "http"
0x180057f56  mov     rcx, r15; lpString1
0x180057f59  call    ?_StringEquals@CLaunchHelper@CBrokeredLauncher@@CA_NPEBG0@Z; CBrokeredLauncher::CLaunchHelper::_StringEquals(ushort const *,ushort const *)
0x180057f5e  test    al, al
0x180057f60  jnz     loc_180058014
0x180057f66  lea     rdx, aHttps_0; "https"
0x180057f6d  mov     rcx, r15; lpString1
0x180057f70  call    ?_StringEquals@CLaunchHelper@CBrokeredLauncher@@CA_NPEBG0@Z; CBrokeredLauncher::CLaunchHelper::_StringEquals(ushort const *,ushort const *)
0x180057f75  test    al, al
0x180057f77  jnz     loc_180058014
0x180057f7d  lea     rdx, aMailto; "mailto"
0x180057f84  mov     rcx, r15; lpString1
0x180057f87  call    ?_StringEquals@CLaunchHelper@CBrokeredLauncher@@CA_NPEBG0@Z; CBrokeredLauncher::CLaunchHelper::_StringEquals(ushort const *,ushort const *)
0x180057f8c  test    al, al
0x180057f8e  jnz     loc_180058014
0x180057f94  mov     [rsp+168h+var_120], rsi
0x180057f99  mov     rax, [r12]
0x180057f9d  mov     rbx, [rax+18h]
0x180057fa1  lea     rcx, [rsp+168h+var_120]
0x180057fa6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180057fab  lea     rax, [rsp+168h+var_120]
0x180057fb0  mov     [rsp+168h+ppv], rax; int
0x180057fb5  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x180057fbc  lea     r8, BHID_AssociationArray
0x180057fc3  xor     edx, edx
0x180057fc5  mov     rcx, r12
0x180057fc8  mov     rax, rbx
0x180057fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fd0  mov     rcx, [rsp+168h]; this
0x180057fd8  test    eax, eax
0x180057fda  js      loc_1800582EF
0x180057fe0  mov     rcx, [rsp+168h+var_120]; struct IAssociationArray *
0x180057fe5  call    ?IsVerbHandlerAppxPackaged@@YA_NPEAUIAssociationArray@@PEBG@Z; IsVerbHandlerAppxPackaged(IAssociationArray *,ushort const *)
0x180057fea  test    al, al
0x180057fec  jz      short loc_180057FF2
0x180057fee  mov     eax, esi
0x180057ff0  jmp     short loc_180057FF9
0x180057ff2  xor     edx, edx; bool
0x180057ff4  call    ?_CheckElevatedLaunchAllowed@CLaunchHelper@CBrokeredLauncher@@AEAAJ_N@Z; CBrokeredLauncher::CLaunchHelper::_CheckElevatedLaunchAllowed(bool)
0x180057ff9  mov     rcx, [rsp+168h]; this
0x180058001  test    eax, eax
0x180058003  js      loc_180058303
0x180058009  lea     rcx, [rsp+168h+var_120]
0x18005800e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058013  nop
0x180058014  lea     rcx, [rsp+168h+var_110]
0x180058019  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005801e  nop
0x18005801f  mov     rcx, [rsp+168h+lpFileName]; pv
0x180058024  call    cs:__imp_CoTaskMemFree
0x18005802a  xor     eax, eax
0x18005802c  jmp     short loc_180058032
0x18005802e  mov     eax, [rsp+168h+netIsoError]
0x180058032  mov     rcx, [rsp+168h+var_48]
0x18005803a  xor     rcx, rsp; StackCookie
0x18005803d  call    __security_check_cookie
0x180058042  add     rsp, 138h
0x180058049  pop     r15
0x18005804b  pop     r14
0x18005804d  pop     r13
0x18005804f  pop     r12
0x180058051  pop     rsi
0x180058052  pop     rbx
0x180058053  retn
0x180058054  mov     r9d, eax; char *
0x180058057  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
  ... truncated ...
```
