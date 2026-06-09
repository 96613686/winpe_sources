# winrt::Windows::Internal::Shell::implementation::CloudPCComponent::HandlePhysicalDeviceAccess(void)

- ea: `0x18063ce50`
- end: `0x18063d189`
- name: `?HandlePhysicalDeviceAccess@CloudPCComponent@implementation@Shell@Internal@Windows@winrt@@AEAAXXZ`
- size: `825`
- prototype: `void __fastcall(winrt::Windows::Internal::Shell::implementation::CloudPCComponent *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18063f0a0`

## callees

- `0x1800d55f0`
- `0x1800d7c50`
- `0x18026bb3c`
- `0x1802882f8`
- `0x180356360`
- `0x1803bc514`
- `0x1803d1b7c`
- `0x18063a1a0`
- `0x18063b35c`
- `0x18063b51c`
- `0x18063b58c`
- `0x18063c838`
- `0x18063ce50`
- `0x18063d2c4`
- `0x18063e1a4`
- `0x18063f5b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18063ced4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18063ced4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18063ceaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18063ceaa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18063d02f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18063d02f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18063d0a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18063d0dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18063d0a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18063d0dc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18063cf9b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18063cf9b`
- `ext-ms-win-ntuser-misc-l1-1-0!ExitWindowsEx` at `0x18063cf06`
- `ext-ms-win-ntuser-misc-l1-1-0!ExitWindowsEx` at `0x18063cf06`

## string_xrefs

- `0x18063d097`: `PhysicalDeviceAccessConfigured`
- `0x18063ce9c`: `Software\Microsoft\Windows\BootToCloud\PhysicalDeviceAccess`
- `0x18063cf8d`: `Software\Microsoft\Windows\BootToCloud\PhysicalDeviceAccess`
- `0x18063d021`: `Software\Microsoft\Windows\BootToCloud\PhysicalDeviceAccess`
- `0x18063cec8`: `SignOutConfiguredForPhysicalDeviceAccess`
- `0x18063d0d0`: `PhysicalDeviceAccessed`
- `0x18063ceeb`: `pcshell\twinui\cloudpc\lib\cloudpccomponent.cpp`
- `0x18063d0f3`: `pcshell\twinui\cloudpc\lib\cloudpccomponent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Shell::implementation::CloudPCComponent::HandlePhysicalDeviceAccess(
        winrt::Windows::Internal::Shell::implementation::CloudPCComponent *this)
{
  __int64 v2; // rdx
  CloudPCHelpers *v3; // rcx
  HKEY *v4; // rax
  unsigned int v5; // eax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rdx
  bool IsPhysicalDeviceAccessConfigured; // al
  const char *v9; // r9
  const unsigned __int16 *v10; // r8
  unsigned int Key; // eax
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rdx
  HKEY *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-2B8h]
  __int64 v20; // [rsp+50h] [rbp-288h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-280h] BYREF
  HKEY v22[2]; // [rsp+60h] [rbp-278h] BYREF
  _BYTE v23[56]; // [rsp+70h] [rbp-268h] BYREF
  __int64 v24; // [rsp+A8h] [rbp-230h]
  _BYTE pvData[528]; // [rsp+B0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( CloudPCHelpers::IsSignOutConfiguredForPhysicalDeviceAccess(this) )
  {
    hKey = 0;
    v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                   &hKey,
                   v2);
    v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\BootToCloud\\PhysicalDeviceAccess", 0, 2u, v4);
    if ( v5 != 2 )
    {
      v6 = retaddr;
      if ( v5 )
      {
        v7 = 388;
      }
      else
      {
        v5 = RegDeleteValueW(hKey, L"SignOutConfiguredForPhysicalDeviceAccess");
        v6 = retaddr;
        if ( !v5 )
        {
          ExitWindowsEx(4u, 0x80000000);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return;
        }
        v7 = 390;
      }
      wil::details::in1diag3::_Log_Win32(
        v6,
        (void *)v7,
        (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\cloudpccomponent.cpp",
        (const char *)v5,
        phkResult);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  IsPhysicalDeviceAccessConfigured = CloudPCHelpers::IsPhysicalDeviceAccessConfigured(v3);
  try
  {
    if ( !IsPhysicalDeviceAccessConfigured )
    {
      if ( *((_DWORD *)this + 30) == 1 )
        winrt::Windows::Internal::Shell::implementation::CloudPCComponent::SubscribeToAccessPhysicalDevice(this);
      return;
    }
    v20 = 0;
    tip2::tip_test<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::start_and_watch_errors(
      &v20,
      v23);
    wil::com_ptr_t<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>,wil::err_returncode_policy>(&v20);
    LODWORD(hKey) = 1;
    v22[0] = 0;
    CloudPCHelpers::GetCorrelationId(pvData, (wchar_t *)L"SystemId_boot", v10);
    CloudPCTelemetryCore::PhysicalDeviceAccessed<unsigned short (&)[260]>(pvData);
    Key = RegDeleteKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\BootToCloud\\PhysicalDeviceAccess", 0, 0);
    v12 = retaddr;
    if ( Key )
    {
      v13 = 409;
    }
    else
    {
      v14 = v24;
      v20 = v24;
      if ( v24 )
        _InterlockedIncrement((volatile signed __int32 *)(v24 + 280));
      tip2::details::shared_data<1,0,0>::begin_update(v14 + 8);
      *(_BYTE *)(v14 + 272) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>(&v20);
      v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                      v22,
                      v15);
      Key = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\BootToCloud\\PhysicalDeviceAccess",
              0,
              0,
              1u,
              0x20006u,
              0,
              v16,
              0);
      v12 = retaddr;
      if ( Key )
      {
        v13 = 412;
      }
      else
      {
        v17 = v24;
        v20 = v24;
        if ( v24 )
          _InterlockedIncrement((volatile signed __int32 *)(v24 + 280));
        tip2::details::shared_data<1,0,0>::begin_update(v17 + 8);
        *(_BYTE *)(v17 + 273) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>(&v20);
        Key = RegSetValueExW(v22[0], L"PhysicalDeviceAccessConfigured", 0, 4u, (const BYTE *)&hKey, 4u);
        v12 = retaddr;
        if ( Key )
        {
          v13 = 415;
        }
        else
        {
          Key = RegSetValueExW(v22[0], L"PhysicalDeviceAccessed", 0, 4u, (const BYTE *)&hKey, 4u);
          v12 = retaddr;
          if ( !Key )
          {
            v18 = v24;
            v20 = v24;
            if ( v24 )
              _InterlockedIncrement((volatile signed __int32 *)(v24 + 280));
            tip2::details::shared_data<1,0,0>::begin_update(v18 + 8);
            *(_BYTE *)(v18 + 274) = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>(&v20);
            goto LABEL_28;
          }
          v13 = 417;
        }
      }
    }
    wil::details::in1diag3::_Log_Win32(
      v12,
      (void *)v13,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\cloudpccomponent.cpp",
      (const char *)Key,
      phkResult);
LABEL_28:
    tip2::details::shared_data<1,0,0>::complete_without_lock(v24 + 8);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
    tip2::test_watcher<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::~test_watcher<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>(v23);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\cloudpccomponent.cpp",
      v9);
  }
}

```

## disassembly

```asm
0x18063ce50  push    rbx
0x18063ce52  sub     rsp, 2D0h
0x18063ce59  mov     rax, cs:__security_cookie
0x18063ce60  xor     rax, rsp
0x18063ce63  mov     [rsp+2D8h+var_18], rax
0x18063ce6b  mov     rbx, rcx
0x18063ce6e  call    ?IsSignOutConfiguredForPhysicalDeviceAccess@CloudPCHelpers@@YA_NXZ; CloudPCHelpers::IsSignOutConfiguredForPhysicalDeviceAccess(void)
0x18063ce73  test    al, al
0x18063ce75  jz      loc_18063CF25
0x18063ce7b  mov     [rsp+2D8h+hKey], 0
0x18063ce84  lea     rcx, [rsp+2D8h+hKey]
0x18063ce89  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18063ce8e  mov     [rsp+2D8h+phkResult], rax; unsigned int
0x18063ce93  mov     r9d, 2; samDesired
0x18063ce99  xor     r8d, r8d; ulOptions
0x18063ce9c  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\BootToClo"...
0x18063cea3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18063ceaa  call    cs:__imp_RegOpenKeyExW
0x18063ceb0  cmp     eax, 2
0x18063ceb3  jz      short loc_18063CF1B
0x18063ceb5  mov     rcx, [rsp+2D8h]
0x18063cebd  test    eax, eax
0x18063cebf  jz      short loc_18063CEC8
0x18063cec1  mov     edx, 184h
0x18063cec6  jmp     short loc_18063CEEB
0x18063cec8  lea     rdx, aSignoutconfigu; "SignOutConfiguredForPhysicalDeviceAcces"...
0x18063cecf  mov     rcx, [rsp+2D8h+hKey]; hKey
0x18063ced4  call    cs:__imp_RegDeleteValueW
0x18063ceda  mov     rcx, [rsp+2D8h]; this
0x18063cee2  test    eax, eax
0x18063cee4  jz      short loc_18063CEFC
0x18063cee6  mov     edx, 186h; void *
0x18063ceeb  lea     r8, aPcshellTwinuiC_10; "pcshell\\twinui\\cloudpc\\lib\\cloudpcc"...
0x18063cef2  mov     r9d, eax; char *
0x18063cef5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18063cefa  jmp     short loc_18063CF1B
0x18063cefc  mov     edx, 80000000h; dwReason
0x18063cf01  mov     ecx, 4; uFlags
0x18063cf06  call    cs:__imp_ExitWindowsEx
0x18063cf0c  lea     rcx, [rsp+2D8h+hKey]
0x18063cf11  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18063cf16  jmp     loc_18063D16F
0x18063cf1b  lea     rcx, [rsp+2D8h+hKey]
0x18063cf20  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18063cf25  call    ?IsPhysicalDeviceAccessConfigured@CloudPCHelpers@@YA_NXZ; CloudPCHelpers::IsPhysicalDeviceAccessConfigured(void)
0x18063cf2a  test    al, al
0x18063cf2c  jz      loc_18063D160
0x18063cf32  mov     [rsp+2D8h+var_288], 0
0x18063cf3b  lea     rdx, [rsp+2D8h+var_268]
0x18063cf40  lea     rcx, [rsp+2D8h+var_288]
0x18063cf45  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_MakePhysicalDeviceAccessKeyVolatileTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_MakePhysicalDeviceAccessKeyVolatileTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::start_and_watch_errors(void)
0x18063cf4a  lea     rcx, [rsp+2D8h+var_288]
0x18063cf4f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_MakePhysicalDeviceAccessKeyVolatileTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>,wil::err_returncode_policy>(void)
0x18063cf54  nop
0x18063cf55  mov     dword ptr [rsp+2D8h+hKey], 1
0x18063cf5d  mov     [rsp+2D8h+var_278], 0
0x18063cf66  lea     rdx, aSystemidBoot; "SystemId_boot"
0x18063cf6d  lea     rcx, [rsp+2D8h+pvData]; pvData
0x18063cf75  call    ?GetCorrelationId@CloudPCHelpers@@YAXPEAGPEBG@Z; CloudPCHelpers::GetCorrelationId(ushort *,ushort const *)
0x18063cf7a  lea     rcx, [rsp+2D8h+pvData]
0x18063cf82  call    ??$PhysicalDeviceAccessed@AEAY0BAE@G@CloudPCTelemetryCore@@SAXAEAY0BAE@G@Z; CloudPCTelemetryCore::PhysicalDeviceAccessed<ushort (&)[260]>(ushort (&)[260])
0x18063cf87  xor     r9d, r9d; Reserved
0x18063cf8a  xor     r8d, r8d; samDesired
0x18063cf8d  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\BootToClo"...
0x18063cf94  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18063cf9b  call    cs:__imp_RegDeleteKeyExW
0x18063cfa1  mov     rcx, [rsp+2D8h]
0x18063cfa9  test    eax, eax
0x18063cfab  jz      short loc_18063CFB7
0x18063cfad  mov     edx, 199h
0x18063cfb2  jmp     loc_18063D0F3
0x18063cfb7  mov     rbx, [rsp+2D8h+var_230]
0x18063cfbf  mov     [rsp+2D8h+var_288], rbx
0x18063cfc4  test    rbx, rbx
0x18063cfc7  jz      short loc_18063CFD0
0x18063cfc9  lock inc dword ptr [rbx+118h]
0x18063cfd0  lea     rcx, [rbx+8]
0x18063cfd4  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18063cfd9  mov     byte ptr [rbx+110h], 1
0x18063cfe0  lea     rcx, [rsp+2D8h+var_288]
0x18063cfe5  call    ??1?$test_data_control@V?$merged_data@U_tip_MakePhysicalDeviceAccessKeyVolatileTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>(void)
0x18063cfea  lea     rcx, [rsp+2D8h+var_278]
0x18063cfef  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18063cff4  mov     [rsp+2D8h+lpdwDisposition], 0; lpdwDisposition
0x18063cffd  mov     [rsp+2D8h+var_2A0], rax; phkResult
0x18063d002  mov     [rsp+2D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18063d00b  mov     [rsp+2D8h+samDesired], 20006h; samDesired
0x18063d013  mov     dword ptr [rsp+2D8h+phkResult], 1; dwOptions
0x18063d01b  xor     r9d, r9d; lpClass
0x18063d01e  xor     r8d, r8d; Reserved
0x18063d021  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\BootToClo"...
0x18063d028  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18063d02f  call    cs:__imp_RegCreateKeyExW
0x18063d035  mov     rcx, [rsp+2D8h]
0x18063d03d  test    eax, eax
0x18063d03f  jz      short loc_18063D04B
0x18063d041  mov     edx, 19Ch
0x18063d046  jmp     loc_18063D0F3
0x18063d04b  mov     rbx, [rsp+2D8h+var_230]
0x18063d053  mov     [rsp+2D8h+var_288], rbx
0x18063d058  test    rbx, rbx
0x18063d05b  jz      short loc_18063D064
0x18063d05d  lock inc dword ptr [rbx+118h]
0x18063d064  lea     rcx, [rbx+8]
0x18063d068  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18063d06d  mov     byte ptr [rbx+111h], 1
0x18063d074  lea     rcx, [rsp+2D8h+var_288]
0x18063d079  call    ??1?$test_data_control@V?$merged_data@U_tip_MakePhysicalDeviceAccessKeyVolatileTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>(void)
0x18063d07e  mov     ebx, 4
0x18063d083  mov     [rsp+2D8h+samDesired], ebx; cbData
0x18063d087  lea     rax, [rsp+2D8h+hKey]
0x18063d08c  mov     [rsp+2D8h+phkResult], rax; lpData
0x18063d091  mov     r9d, ebx; dwType
0x18063d094  xor     r8d, r8d; Reserved
0x18063d097  lea     rdx, aPhysicaldevice; "PhysicalDeviceAccessConfigured"
0x18063d09e  mov     rcx, [rsp+2D8h+var_278]; hKey
0x18063d0a3  call    cs:__imp_RegSetValueExW
0x18063d0a9  mov     rcx, [rsp+2D8h]
0x18063d0b1  test    eax, eax
0x18063d0b3  jz      short loc_18063D0BC
0x18063d0b5  mov     edx, 19Fh
0x18063d0ba  jmp     short loc_18063D0F3
0x18063d0bc  mov     [rsp+2D8h+samDesired], ebx; cbData
0x18063d0c0  lea     rax, [rsp+2D8h+hKey]
0x18063d0c5  mov     [rsp+2D8h+phkResult], rax; unsigned int
0x18063d0ca  mov     r9d, ebx; dwType
0x18063d0cd  xor     r8d, r8d; Reserved
0x18063d0d0  lea     rdx, aPhysicaldevice_0; "PhysicalDeviceAccessed"
0x18063d0d7  mov     rcx, [rsp+2D8h+var_278]; hKey
0x18063d0dc  call    cs:__imp_RegSetValueExW
0x18063d0e2  mov     rcx, [rsp+2D8h]; this
0x18063d0ea  test    eax, eax
0x18063d0ec  jz      short loc_18063D104
0x18063d0ee  mov     edx, 1A1h; void *
0x18063d0f3  lea     r8, aPcshellTwinuiC_10; "pcshell\\twinui\\cloudpc\\lib\\cloudpcc"...
0x18063d0fa  mov     r9d, eax; char *
0x18063d0fd  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18063d102  jmp     short loc_18063D137
0x18063d104  mov     rbx, [rsp+2D8h+var_230]
0x18063d10c  mov     [rsp+2D8h+var_288], rbx
0x18063d111  test    rbx, rbx
0x18063d114  jz      short loc_18063D11D
0x18063d116  lock inc dword ptr [rbx+118h]
0x18063d11d  lea     rcx, [rbx+8]
0x18063d121  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18063d126  mov     byte ptr [rbx+112h], 1
0x18063d12d  lea     rcx, [rsp+2D8h+var_288]
0x18063d132  call    ??1?$test_data_control@V?$merged_data@U_tip_MakePhysicalDeviceAccessKeyVolatileTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>(void)
0x18063d137  mov     rcx, [rsp+2D8h+var_230]
0x18063d13f  add     rcx, 8
0x18063d143  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18063d148  nop
0x18063d149  lea     rcx, [rsp+2D8h+var_278]
0x18063d14e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18063d153  nop
0x18063d154  lea     rcx, [rsp+2D8h+var_268]
0x18063d159  call    ??1?$test_watcher@V?$merged_data@U_tip_MakePhysicalDeviceAccessKeyVolatileTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>::~test_watcher<tip2::details::merged_data<_tip_MakePhysicalDeviceAccessKeyVolatileTipTest,_tip_MakePhysicalDeviceAccessKeyVolatileTipTest>>(void)
0x18063d15e  jmp     short loc_18063D16F
0x18063d160  cmp     dword ptr [rbx+78h], 1
0x18063d164  jnz     short loc_18063D16F
0x18063d166  mov     rcx, rbx; this
0x18063d169  call    ?SubscribeToAccessPhysicalDevice@CloudPCComponent@implementation@Shell@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::Shell::implementation::CloudPCComponent::SubscribeToAccessPhysicalDevice(void)
0x18063d16e  nop
0x18063d16f  mov     rcx, [rsp+2D8h+var_18]
0x18063d177  xor     rcx, rsp; StackCookie
0x18063d17a  call    __security_check_cookie
0x18063d17f  add     rsp, 2D0h
0x18063d186  pop     rbx
0x18063d187  retn
```
