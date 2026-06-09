# winrt::Windows::Internal::Shell::implementation::RemoteSessionPersistenceHelper::SaveHostProcessDataToStorage(std::shared_ptr<winrt::Windows::Internal::Shell::implementation::HostProcessData>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)

- ea: `0x1806579d0`
- end: `0x180657e18`
- name: `?SaveHostProcessDataToStorage@RemoteSessionPersistenceHelper@implementation@Shell@Internal@Windows@winrt@@AEAAXV?$shared_ptr@UHostProcessData@implementation@Shell@Internal@Windows@winrt@@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1096`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180657e20`

## callees

- `0x18001b3d4`
- `0x180043f00`
- `0x180066030`
- `0x180299a70`
- `0x1803bc514`
- `0x1803e06a0`
- `0x180649238`
- `0x180657944`
- `0x1806579d0`
- `0x18065ada8`
- `0x18065adcc`
- `0x18065ae14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657a7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657adf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657b27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657b67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657c47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657c94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657ce1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657d2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657d9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657a7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657adf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657b27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657b67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657c47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657c94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657ce1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657d2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180657d9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Windows::Internal::Shell::implementation::RemoteSessionPersistenceHelper::SaveHostProcessDataToStorage(
        winrt::Windows::Internal::Shell::implementation::RemoteSessionPersistenceHelper *a1,
        unsigned int **a2,
        HKEY *a3)
{
  unsigned int *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  const BYTE *v8; // rax
  DWORD cbData; // edx
  const BYTE *v10; // rax
  DWORD v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  const char *v15; // r9
  unsigned int v16; // eax
  __int64 v17; // rdx
  winrt::Windows::Internal::Shell::implementation::HostProcessData *v18; // rcx
  winrt::Windows::Internal::Shell::implementation::HostProcessData *v19; // rcx
  const WCHAR *v20; // rax
  unsigned int v21; // eax
  const WCHAR *v22; // rax
  unsigned int v23; // eax
  const WCHAR *v24; // rax
  unsigned int v25; // eax
  const WCHAR *v26; // rax
  unsigned int v27; // eax
  const WCHAR *v28; // rax
  unsigned int v29; // eax
  std::_Ref_count_base *v30; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-78h]
  unsigned int lpDataa; // [rsp+20h] [rbp-78h]
  unsigned int lpDatab; // [rsp+20h] [rbp-78h]
  unsigned int lpDatac; // [rsp+20h] [rbp-78h]
  unsigned int lpDatad; // [rsp+20h] [rbp-78h]
  unsigned int lpDatae; // [rsp+20h] [rbp-78h]
  __int64 v37; // [rsp+30h] [rbp-68h] BYREF
  __int64 v38; // [rsp+38h] [rbp-60h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-58h] BYREF
  BYTE v40[4]; // [rsp+44h] [rbp-54h] BYREF
  BYTE v41[4]; // [rsp+48h] [rbp-50h] BYREF
  BYTE v42[4]; // [rsp+4Ch] [rbp-4Ch] BYREF
  unsigned __int64 v43; // [rsp+50h] [rbp-48h] BYREF
  BYTE v44[8]; // [rsp+58h] [rbp-40h] BYREF
  int v45; // [rsp+60h] [rbp-38h] BYREF
  __int128 v46; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  unsigned int **v49; // [rsp+A8h] [rbp+10h] BYREF
  BOOL IsCapabilitySupported; // [rsp+B8h] [rbp+20h] BYREF

  v49 = a2;
  winrt::Windows::Internal::Shell::implementation::HostProcessData::RemoteDesktopId(*a2, &v37);
  winrt::Windows::Internal::Shell::implementation::HostProcessData::CorrelationId(*a2, &v38);
  v5 = *a2;
  *(_DWORD *)Data = (*a2)[6];
  *(_DWORD *)v40 = *((_BYTE *)v5 + 28) != 0;
  LOBYTE(v6) = 3;
  LOBYTE(v7) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudPCCommon_v3>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CloudPCCommon_v3>::GetImpl'::`2'::impl,
    v7,
    v6);
  v45 = 0;
  v46 = 0;
  v8 = (const BYTE *)winrt::hstring::c_str((winrt::hstring *)&v37);
  RegSetValueExW(*a3, L"remoteDesktopId", 0, 1u, v8, cbData);
  try
  {
    ((void (*)(void))winrt::check_win32<unsigned long>)();
    v45 = 0;
    v46 = 0;
    v10 = (const BYTE *)winrt::hstring::c_str((winrt::hstring *)&v38);
    v12 = RegSetValueExW(*a3, L"correlationId", 0, 1u, v10, v11);
    winrt::check_win32<unsigned long>(v12, &v45);
    v45 = 0;
    v46 = 0;
    v13 = RegSetValueExW(*a3, L"cloudPCMode", 0, 4u, Data, 4u);
    winrt::check_win32<unsigned long>(v13, &v45);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x88,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\remotesessionpersistencehelper.cpp",
      v15);
    LOBYTE(IsCapabilitySupported) = 1;
    v43 = **v49;
    winrt::Windows::Internal::Shell::implementation::RemoteSessionPersistenceHelper::DeleteIdFromStorage(
      a1,
      &v43,
      (const struct winrt::hstring *)&v37,
      (const bool *)&IsCapabilitySupported);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v38);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v37);
    v30 = (std::_Ref_count_base *)v49[1];
    goto LABEL_15;
  }
  LOBYTE(v14) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_BluetoothSupportForB2CAndSwitch_BugFixes>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_W365Boot_BluetoothSupportForB2CAndSwitch_BugFixes>::GetImpl'::`2'::impl,
    v14);
  v16 = RegSetValueExW(*a3, L"supportBluetoothSettings", 0, 4u, v40, 4u);
  if ( v16 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x9A,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\remotesessionpersistencehelper.cpp",
      (const char *)v16,
      lpData);
  LOBYTE(v17) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_ManagedPCSettings>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_W365Boot_ManagedPCSettings>::GetImpl'::`2'::impl,
    v17);
  LODWORD(v49) = 1;
  IsCapabilitySupported = winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(
                            (winrt::Windows::Internal::Shell::implementation::HostProcessData *)*a2,
                            (const enum winrt::Windows::Internal::Shell::LocalCapabilities *)&v49);
  LODWORD(v49) = 2;
  *(_DWORD *)v41 = winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(
                     (winrt::Windows::Internal::Shell::implementation::HostProcessData *)*a2,
                     (const enum winrt::Windows::Internal::Shell::LocalCapabilities *)&v49);
  LODWORD(v49) = 4;
  *(_DWORD *)v42 = winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(
                     v18,
                     (const enum winrt::Windows::Internal::Shell::LocalCapabilities *)&v49);
  LODWORD(v49) = 3;
  LODWORD(v43) = winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(
                   v19,
                   (const enum winrt::Windows::Internal::Shell::LocalCapabilities *)&v49);
  v20 = winrt::hstring::c_str((winrt::hstring *)&c_supportSystemSoundSettings);
  v21 = RegSetValueExW(*a3, v20, 0, 4u, (const BYTE *)&IsCapabilitySupported, 4u);
  if ( v21 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xA9,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\remotesessionpersistencehelper.cpp",
      (const char *)v21,
      lpDataa);
  v22 = winrt::hstring::c_str((winrt::hstring *)&c_supportSystemDisplaySettings);
  v23 = RegSetValueExW(*a3, v22, 0, 4u, v41, 4u);
  if ( v23 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xAB,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\remotesessionpersistencehelper.cpp",
      (const char *)v23,
      lpDatab);
  v24 = winrt::hstring::c_str((winrt::hstring *)&c_supportSystemSettings);
  v25 = RegSetValueExW(*a3, v24, 0, 4u, v42, 4u);
  if ( v25 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xAD,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\remotesessionpersistencehelper.cpp",
      (const char *)v25,
      lpDatac);
  v26 = winrt::hstring::c_str((winrt::hstring *)&c_supportSystemAccountSettings);
  v27 = RegSetValueExW(*a3, v26, 0, 4u, (const BYTE *)&v43, 4u);
  if ( v27 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xAF,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\remotesessionpersistencehelper.cpp",
      (const char *)v27,
      lpDatad);
  LODWORD(v49) = 5;
  *(_DWORD *)v44 = winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(
                     (winrt::Windows::Internal::Shell::implementation::HostProcessData *)*a2,
                     (const enum winrt::Windows::Internal::Shell::LocalCapabilities *)&v49);
  v28 = winrt::hstring::c_str((winrt::hstring *)&c_supportBlendedDisplaySettings);
  v29 = RegSetValueExW(*a3, v28, 0, 4u, v44, 4u);
  if ( v29 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xB4,
      (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\remotesessionpersistencehelper.cpp",
      (const char *)v29,
      lpDatae);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v38);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v37);
  v30 = (std::_Ref_count_base *)a2[1];
LABEL_15:
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
}

```

## disassembly

```asm
0x1806579d0  mov     [rsp+arg_8], rdx
0x1806579d5  mov     [rsp+arg_0], rcx
0x1806579da  push    rsi
0x1806579db  push    rdi
0x1806579dc  push    r14
0x1806579de  sub     rsp, 80h
0x1806579e5  mov     rdi, r8
0x1806579e8  mov     rsi, rdx
0x1806579eb  lea     rdx, [rsp+98h+var_68]
0x1806579f0  mov     rcx, [rsi]
0x1806579f3  call    ?RemoteDesktopId@HostProcessData@implementation@Shell@Internal@Windows@winrt@@QEAA?AUhstring@6@XZ; winrt::Windows::Internal::Shell::implementation::HostProcessData::RemoteDesktopId(void)
0x1806579f8  nop
0x1806579f9  lea     rdx, [rsp+98h+var_60]
0x1806579fe  mov     rcx, [rsi]
0x180657a01  call    ?CorrelationId@HostProcessData@implementation@Shell@Internal@Windows@winrt@@QEAA?AUhstring@6@XZ; winrt::Windows::Internal::Shell::implementation::HostProcessData::CorrelationId(void)
0x180657a06  nop
0x180657a07  mov     rcx, [rsi]
0x180657a0a  mov     eax, [rcx+18h]
0x180657a0d  mov     dword ptr [rsp+98h+Data], eax
0x180657a11  xor     eax, eax
0x180657a13  cmp     [rcx+1Ch], al
0x180657a16  setnz   al
0x180657a19  mov     dword ptr [rsp+98h+var_54], eax
0x180657a1d  mov     r8b, 3
0x180657a20  mov     dl, 1
0x180657a22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudPCCommon_v3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudPCCommon_v3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudPCCommon_v3> `wil::Feature<__WilFeatureTraits_Feature_CloudPCCommon_v3>::GetImpl(void)'::`2'::impl
0x180657a29  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudPCCommon_v3@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudPCCommon_v3>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180657a2e  nop
0x180657a2f  mov     [rsp+98h+var_38], 0
0x180657a37  xorps   xmm0, xmm0
0x180657a3a  movdqu  [rsp+98h+var_30], xmm0
0x180657a40  mov     rax, [rsp+98h+var_68]
0x180657a45  test    rax, rax
0x180657a48  jz      short loc_180657A4F
0x180657a4a  mov     edx, [rax+4]
0x180657a4d  jmp     short loc_180657A51
0x180657a4f  xor     edx, edx
0x180657a51  lea     edx, ds:2[rdx*2]
0x180657a58  lea     rcx, [rsp+98h+var_68]; this
0x180657a5d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180657a62  mov     [rsp+98h+cbData], edx; cbData
0x180657a66  mov     [rsp+98h+lpData], rax; lpData
0x180657a6b  mov     r9d, 1; dwType
0x180657a71  xor     r8d, r8d; Reserved
0x180657a74  lea     rdx, aRemotedesktopi; "remoteDesktopId"
0x180657a7b  mov     rcx, [rdi]; hKey
0x180657a7e  call    cs:__imp_RegSetValueExW
0x180657a84  lea     rdx, [rsp+98h+var_38]
0x180657a89  mov     ecx, eax
0x180657a8b  call    ??$check_win32@K@winrt@@YAXKAEBUslim_source_location@impl@0@@Z; winrt::check_win32<ulong>(ulong,winrt::impl::slim_source_location const &)
0x180657a90  mov     [rsp+98h+var_38], 0
0x180657a98  xorps   xmm0, xmm0
0x180657a9b  movdqu  [rsp+98h+var_30], xmm0
0x180657aa1  mov     rax, [rsp+98h+var_60]
0x180657aa6  test    rax, rax
0x180657aa9  jz      short loc_180657AB0
0x180657aab  mov     edx, [rax+4]
0x180657aae  jmp     short loc_180657AB2
0x180657ab0  xor     edx, edx
0x180657ab2  lea     edx, ds:2[rdx*2]
0x180657ab9  lea     rcx, [rsp+98h+var_60]; this
0x180657abe  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180657ac3  mov     [rsp+98h+cbData], edx; cbData
0x180657ac7  mov     [rsp+98h+lpData], rax; lpData
0x180657acc  mov     r9d, 1; dwType
0x180657ad2  xor     r8d, r8d; Reserved
0x180657ad5  lea     rdx, aCorrelationid_2; "correlationId"
0x180657adc  mov     rcx, [rdi]; hKey
0x180657adf  call    cs:__imp_RegSetValueExW
0x180657ae5  lea     rdx, [rsp+98h+var_38]
0x180657aea  mov     ecx, eax
0x180657aec  call    ??$check_win32@K@winrt@@YAXKAEBUslim_source_location@impl@0@@Z; winrt::check_win32<ulong>(ulong,winrt::impl::slim_source_location const &)
0x180657af1  mov     [rsp+98h+var_38], 0
0x180657af9  xorps   xmm0, xmm0
0x180657afc  movdqu  [rsp+98h+var_30], xmm0
0x180657b02  mov     r14d, 4
0x180657b08  mov     [rsp+98h+cbData], r14d; cbData
0x180657b0d  lea     rax, [rsp+98h+Data]
0x180657b12  mov     [rsp+98h+lpData], rax; lpData
0x180657b17  mov     r9d, r14d; dwType
0x180657b1a  xor     r8d, r8d; Reserved
0x180657b1d  lea     rdx, aCloudpcmode; "cloudPCMode"
0x180657b24  mov     rcx, [rdi]; hKey
0x180657b27  call    cs:__imp_RegSetValueExW
0x180657b2d  lea     rdx, [rsp+98h+var_38]
0x180657b32  mov     ecx, eax
0x180657b34  call    ??$check_win32@K@winrt@@YAXKAEBUslim_source_location@impl@0@@Z; winrt::check_win32<ulong>(ulong,winrt::impl::slim_source_location const &)
0x180657b39  nop
0x180657b3a  mov     dl, 1
0x180657b3c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_W365Boot_BluetoothSupportForB2CAndSwitch_BugFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_W365Boot_BluetoothSupportForB2CAndSwitch_BugFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_BluetoothSupportForB2CAndSwitch_BugFixes> `wil::Feature<__WilFeatureTraits_Feature_W365Boot_BluetoothSupportForB2CAndSwitch_BugFixes>::GetImpl(void)'::`2'::impl
0x180657b43  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_W365Boot_BluetoothSupportForB2CAndSwitch_BugFixes@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_BluetoothSupportForB2CAndSwitch_BugFixes>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180657b48  mov     [rsp+98h+cbData], r14d; cbData
0x180657b4d  lea     rax, [rsp+98h+var_54]
0x180657b52  mov     [rsp+98h+lpData], rax; unsigned int
0x180657b57  mov     r9d, r14d; dwType
0x180657b5a  xor     r8d, r8d; Reserved
0x180657b5d  lea     rdx, aSupportbluetoo; "supportBluetoothSettings"
0x180657b64  mov     rcx, [rdi]; hKey
0x180657b67  call    cs:__imp_RegSetValueExW
0x180657b6d  mov     rcx, [rsp+98h]; this
0x180657b75  test    eax, eax
0x180657b77  jz      short loc_180657B8D
0x180657b79  mov     r9d, eax; char *
0x180657b7c  lea     r8, aPcshellTwinuiC_11; "pcshell\\twinui\\cloudpc\\lib\\remotese"...
0x180657b83  mov     edx, 9Ah; void *
0x180657b88  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180657b8d  mov     dl, 1
0x180657b8f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_W365Boot_ManagedPCSettings@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_W365Boot_ManagedPCSettings@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_ManagedPCSettings> `wil::Feature<__WilFeatureTraits_Feature_W365Boot_ManagedPCSettings>::GetImpl(void)'::`2'::impl
0x180657b96  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_W365Boot_ManagedPCSettings@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_ManagedPCSettings>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180657b9b  mov     dword ptr [rsp+98h+arg_8], 1
0x180657ba6  lea     rdx, [rsp+98h+arg_8]; enum winrt::Windows::Internal::Shell::LocalCapabilities *
0x180657bae  mov     rcx, [rsi]; this
0x180657bb1  call    ?IsCapabilitySupported@HostProcessData@implementation@Shell@Internal@Windows@winrt@@QEAA_NAEBW4LocalCapabilities@3456@@Z; winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(winrt::Windows::Internal::Shell::LocalCapabilities const &)
0x180657bb6  movzx   ecx, al
0x180657bb9  mov     [rsp+98h+arg_18], ecx
0x180657bc0  mov     dword ptr [rsp+98h+arg_8], 2
0x180657bcb  lea     rdx, [rsp+98h+arg_8]; enum winrt::Windows::Internal::Shell::LocalCapabilities *
0x180657bd3  mov     rcx, [rsi]; this
0x180657bd6  call    ?IsCapabilitySupported@HostProcessData@implementation@Shell@Internal@Windows@winrt@@QEAA_NAEBW4LocalCapabilities@3456@@Z; winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(winrt::Windows::Internal::Shell::LocalCapabilities const &)
0x180657bdb  movzx   edx, al
0x180657bde  mov     dword ptr [rsp+98h+var_50], edx
0x180657be2  mov     dword ptr [rsp+98h+arg_8], r14d
0x180657bea  lea     rdx, [rsp+98h+arg_8]; enum winrt::Windows::Internal::Shell::LocalCapabilities *
0x180657bf2  call    ?IsCapabilitySupported@HostProcessData@implementation@Shell@Internal@Windows@winrt@@QEAA_NAEBW4LocalCapabilities@3456@@Z; winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(winrt::Windows::Internal::Shell::LocalCapabilities const &)
0x180657bf7  movzx   edx, al
0x180657bfa  mov     dword ptr [rsp+98h+var_4C], edx
0x180657bfe  mov     dword ptr [rsp+98h+arg_8], 3
0x180657c09  lea     rdx, [rsp+98h+arg_8]; enum winrt::Windows::Internal::Shell::LocalCapabilities *
0x180657c11  call    ?IsCapabilitySupported@HostProcessData@implementation@Shell@Internal@Windows@winrt@@QEAA_NAEBW4LocalCapabilities@3456@@Z; winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(winrt::Windows::Internal::Shell::LocalCapabilities const &)
0x180657c16  movzx   ecx, al
0x180657c19  mov     dword ptr [rsp+98h+var_48], ecx
0x180657c1d  lea     rcx, ?c_supportSystemSoundSettings@@3Uhstring@winrt@@B; this
0x180657c24  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180657c29  mov     [rsp+98h+cbData], r14d; cbData
0x180657c2e  lea     rcx, [rsp+98h+arg_18]
0x180657c36  mov     [rsp+98h+lpData], rcx; unsigned int
0x180657c3b  mov     r9d, r14d; dwType
0x180657c3e  xor     r8d, r8d; Reserved
0x180657c41  mov     rdx, rax; lpValueName
0x180657c44  mov     rcx, [rdi]; hKey
0x180657c47  call    cs:__imp_RegSetValueExW
0x180657c4d  mov     rcx, [rsp+98h]; this
0x180657c55  test    eax, eax
0x180657c57  jz      short loc_180657C6D
0x180657c59  mov     r9d, eax; char *
0x180657c5c  lea     r8, aPcshellTwinuiC_11; "pcshell\\twinui\\cloudpc\\lib\\remotese"...
0x180657c63  mov     edx, 0A9h; void *
0x180657c68  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180657c6d  lea     rcx, ?c_supportSystemDisplaySettings@@3Uhstring@winrt@@B; this
0x180657c74  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180657c79  mov     [rsp+98h+cbData], r14d; cbData
0x180657c7e  lea     rcx, [rsp+98h+var_50]
0x180657c83  mov     [rsp+98h+lpData], rcx; unsigned int
0x180657c88  mov     r9d, r14d; dwType
0x180657c8b  xor     r8d, r8d; Reserved
0x180657c8e  mov     rdx, rax; lpValueName
0x180657c91  mov     rcx, [rdi]; hKey
0x180657c94  call    cs:__imp_RegSetValueExW
0x180657c9a  mov     rcx, [rsp+98h]; this
0x180657ca2  test    eax, eax
0x180657ca4  jz      short loc_180657CBA
0x180657ca6  mov     r9d, eax; char *
0x180657ca9  lea     r8, aPcshellTwinuiC_11; "pcshell\\twinui\\cloudpc\\lib\\remotese"...
0x180657cb0  mov     edx, 0ABh; void *
0x180657cb5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180657cba  lea     rcx, ?c_supportSystemSettings@@3Uhstring@winrt@@B; this
0x180657cc1  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180657cc6  mov     [rsp+98h+cbData], r14d; cbData
0x180657ccb  lea     rcx, [rsp+98h+var_4C]
0x180657cd0  mov     [rsp+98h+lpData], rcx; unsigned int
0x180657cd5  mov     r9d, r14d; dwType
0x180657cd8  xor     r8d, r8d; Reserved
0x180657cdb  mov     rdx, rax; lpValueName
0x180657cde  mov     rcx, [rdi]; hKey
0x180657ce1  call    cs:__imp_RegSetValueExW
0x180657ce7  mov     rcx, [rsp+98h]; this
0x180657cef  test    eax, eax
0x180657cf1  jz      short loc_180657D07
0x180657cf3  mov     r9d, eax; char *
0x180657cf6  lea     r8, aPcshellTwinuiC_11; "pcshell\\twinui\\cloudpc\\lib\\remotese"...
0x180657cfd  mov     edx, 0ADh; void *
0x180657d02  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180657d07  lea     rcx, ?c_supportSystemAccountSettings@@3Uhstring@winrt@@B; this
0x180657d0e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180657d13  mov     [rsp+98h+cbData], r14d; cbData
0x180657d18  lea     rcx, [rsp+98h+var_48]
0x180657d1d  mov     [rsp+98h+lpData], rcx; unsigned int
0x180657d22  mov     r9d, r14d; dwType
0x180657d25  xor     r8d, r8d; Reserved
0x180657d28  mov     rdx, rax; lpValueName
0x180657d2b  mov     rcx, [rdi]; hKey
0x180657d2e  call    cs:__imp_RegSetValueExW
0x180657d34  mov     rcx, [rsp+98h]; this
0x180657d3c  test    eax, eax
0x180657d3e  jz      short loc_180657D54
0x180657d40  mov     r9d, eax; char *
0x180657d43  lea     r8, aPcshellTwinuiC_11; "pcshell\\twinui\\cloudpc\\lib\\remotese"...
0x180657d4a  mov     edx, 0AFh; void *
0x180657d4f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180657d54  mov     dword ptr [rsp+98h+arg_8], 5
0x180657d5f  lea     rdx, [rsp+98h+arg_8]; enum winrt::Windows::Internal::Shell::LocalCapabilities *
0x180657d67  mov     rcx, [rsi]; this
0x180657d6a  call    ?IsCapabilitySupported@HostProcessData@implementation@Shell@Internal@Windows@winrt@@QEAA_NAEBW4LocalCapabilities@3456@@Z; winrt::Windows::Internal::Shell::implementation::HostProcessData::IsCapabilitySupported(winrt::Windows::Internal::Shell::LocalCapabilities const &)
0x180657d6f  movzx   ecx, al
0x180657d72  mov     dword ptr [rsp+98h+var_40], ecx
0x180657d76  lea     rcx, ?c_supportBlendedDisplaySettings@@3Uhstring@winrt@@B; this
0x180657d7d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180657d82  mov     [rsp+98h+cbData], r14d; cbData
0x180657d87  lea     rcx, [rsp+98h+var_40]
0x180657d8c  mov     [rsp+98h+lpData], rcx; unsigned int
0x180657d91  mov     r9d, r14d; dwType
0x180657d94  xor     r8d, r8d; Reserved
0x180657d97  mov     rdx, rax; lpValueName
0x180657d9a  mov     rcx, [rdi]; hKey
0x180657d9d  call    cs:__imp_RegSetValueExW
0x180657da3  mov     rcx, [rsp+98h]; this
0x180657dab  test    eax, eax
0x180657dad  jz      short loc_180657DC4
0x180657daf  mov     r9d, eax; char *
0x180657db2  lea     r8, aPcshellTwinuiC_11; "pcshell\\twinui\\cloudpc\\lib\\remotese"...
0x180657db9  mov     edx, 0B4h; void *
0x180657dbe  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180657dc3  nop
0x180657dc4  lea     rcx, [rsp+98h+var_60]
0x180657dc9  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180657dce  nop
0x180657dcf  lea     rcx, [rsp+98h+var_68]
0x180657dd4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180657dd9  nop
0x180657dda  mov     rcx, [rsi+8]
0x180657dde  jmp     short loc_180657E02
0x180657de0  lea     rcx, [rsp+98h+var_60]
0x180657de5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180657dea  nop
0x180657deb  lea     rcx, [rsp+98h+var_68]
0x180657df0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180657df5  nop
0x180657df6  mov     rax, [rsp+98h+arg_8]
0x180657dfe  mov     rcx, [rax+8]; this
0x180657e02  test    rcx, rcx
0x180657e05  jz      short loc_180657E0C
0x180657e07  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180657e0c  add     rsp, 80h
0x180657e13  pop     r14
0x180657e15  pop     rdi
0x180657e16  pop     rsi
0x180657e17  retn
```
