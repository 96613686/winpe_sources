# PolicyRegistryHelper::CreateRedirectionMap(void)

- ea: `0x18002690c`
- end: `0x180026c17`
- name: `?CreateRedirectionMap@PolicyRegistryHelper@@CA?AV?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@XZ`
- size: `779`
- prototype: `void **()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800047f0`

## callees

- `0x18002690c`
- `0x1800272fc`
- `0x180030cb4`

## string_xrefs

- `0x1800269c4`: `UpdateOrchestratorCurrentVersionRoot`
- `0x180026a04`: `WindowsUpdateUXRoot`
- `0x180026a24`: `WindowsUpdate`
- `0x180026964`: `UpdateOrchestratorSharedRoot`
- `0x18002697a`: `Software\Microsoft\WindowsUpdate\Orchestrator\USOShared`
- `0x180026984`: `UpdateOrchestratorConfigurationRoot`
- `0x18002699a`: `Software\Microsoft\WindowsUpdate\Orchestrator\Configurations`
- `0x1800269a4`: `UpdateUxConfigurationRoot`
- `0x1800269ba`: `Software\Microsoft\Windows\CurrentVersion\UpdatePlatform\UX\Configurations`
- `0x1800269da`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Orchestrator`
- `0x1800269e4`: `UpdateOrchestratorRoot`
- `0x1800269fa`: `Software\Microsoft\WindowsUpdate\Orchestrator`
- `0x180026a1a`: `Software\Microsoft\WindowsUpdate\UX`
- `0x180026a3a`: `Software\Microsoft\WindowsUpdate`
- `0x180026a5a`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x180026a64`: `WindowsUpdatePolicies`
- `0x180026a7a`: `Software\Policies\Microsoft\Windows\WindowsUpdate`
- `0x180026a84`: `DeviceUpdate`
- `0x180026a9a`: `Software\Microsoft\Windows\CurrentVersion\DeviceUpdate`
- `0x180026ada`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\DTU`
- `0x180026b64`: `DynamicInstalledProducts`
- `0x180026b7a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x180026ba4`: `DeviceAccess`
- `0x180026bba`: `SOFTWARE\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x180026bda`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`

## pseudocode

```c
void **PolicyRegistryHelper::CreateRedirectionMap()
{
  _QWORD *v0; // rax
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r8
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned int v23; // r8d
  int v25; // [rsp+20h] [rbp-28h]
  __int64 v26; // [rsp+0h] [rbp-48h] BYREF
  const wchar_t *v27; // [rsp+20h] [rbp-28h] BYREF
  int v28; // [rsp+28h] [rbp-20h]
  void **v29; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v29 = &PolicyRegistryHelper::s_defaultRedirectionMap;
  PolicyRegistryHelper::s_defaultRedirectionMap = 0;
  qword_18004EFB8 = 0;
  v0 = operator new(0x30u);
  *v0 = v0;
  v0[1] = v0;
  v0[2] = v0;
  *((_WORD *)v0 + 12) = 257;
  PolicyRegistryHelper::s_defaultRedirectionMap = v0;
  v28 = 1;
  v27 = L"UpdateOrchestratorSharedRoot";
  try
  {
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](v1, &v27, v2) = L"Software\\Microsoft\\WindowsUpdate\\"
                                                                                      "Orchestrator\\USOShared";
    v27 = L"UpdateOrchestratorConfigurationRoot";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\USOShared",
                 &v27,
                 v3) = L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Configurations";
    v27 = L"UpdateUxConfigurationRoot";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Configurations",
                 &v27,
                 v4) = L"Software\\Microsoft\\Windows\\CurrentVersion\\UpdatePlatform\\UX\\Configurations";
    v27 = L"UpdateOrchestratorCurrentVersionRoot";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\UpdatePlatform\\UX\\Configurations",
                 &v27,
                 v5) = L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Orchestrator";
    v27 = L"UpdateOrchestratorRoot";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Orchestrator",
                 &v27,
                 v6) = L"Software\\Microsoft\\WindowsUpdate\\Orchestrator";
    v27 = L"WindowsUpdateUXRoot";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\WindowsUpdate\\Orchestrator",
                 &v27,
                 v7) = L"Software\\Microsoft\\WindowsUpdate\\UX";
    v27 = L"WindowsUpdate";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\WindowsUpdate\\UX",
                 &v27,
                 v8) = L"Software\\Microsoft\\WindowsUpdate";
    v27 = L"WUCurrentVersion";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](L"Software\\Microsoft\\WindowsUpdate", &v27, v9) = L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate";
    v27 = L"WindowsUpdatePolicies";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate",
                 &v27,
                 v10) = L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate";
    v27 = L"DeviceUpdate";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate",
                 &v27,
                 v11) = L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceUpdate";
    v27 = L"DtuSelfhost";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceUpdate",
                 &v27,
                 v12) = L"Software\\Microsoft\\DTU";
    v27 = L"Dtu";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](L"Software\\Microsoft\\DTU", &v27, v13) = L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\DTU";
    v27 = L"SystemSetup";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\DTU",
                 &v27,
                 v14) = L"System\\Setup";
    v27 = L"SystemVersions";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](L"System\\Setup", &v27, v15) = L"System\\Versions";
    v27 = L"UIXProductFeatures";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](L"System\\Versions", &v27, v16) = L"Software\\Microsoft\\UIX\\ProductFeatures";
    v27 = L"USO_Network";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"Software\\Microsoft\\UIX\\ProductFeatures",
                 &v27,
                 v17) = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Settings\\Network";
    v27 = L"DynamicInstalledProducts";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Settings\\Network",
                 &v27,
                 v18) = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\DynamicInstalled";
    v27 = L"ReserveManager";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\DynamicInstalled",
                 &v27,
                 v19) = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager";
    v27 = L"DeviceAccess";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                 &v27,
                 v20) = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess";
    v27 = L"CBSInterface";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
                 &v27,
                 v21) = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface";
    v27 = L"Sih";
    *(_QWORD *)std::map<wchar_t const *,wchar_t const *>::operator[](
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface",
                 &v27,
                 v22) = L"SOFTWARE\\Microsoft\\sih";
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_Hr(retaddr, &v26, v23, (const char *)0x8007000ELL, v25);
  }
  return &PolicyRegistryHelper::s_defaultRedirectionMap;
}

```

## disassembly

```asm
0x18002690c  push    rbx
0x18002690e  sub     rsp, 40h
0x180026912  mov     rax, [rsp+48h+var_28]
0x180026917  mov     [rsp+48h+var_18], rax
0x18002691c  xor     eax, eax
0x18002691e  mov     [rsp+48h+var_20], eax
0x180026922  lea     rbx, ?s_defaultRedirectionMap@PolicyRegistryHelper@@0V?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@A; std::map<wchar_t const *,wchar_t const *> PolicyRegistryHelper::s_defaultRedirectionMap
0x180026929  mov     [rsp+48h+var_18], rbx
0x18002692e  mov     cs:?s_defaultRedirectionMap@PolicyRegistryHelper@@0V?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@A, rax; std::map<wchar_t const *,wchar_t const *> PolicyRegistryHelper::s_defaultRedirectionMap
0x180026935  mov     cs:qword_18004EFB8, rax
0x18002693c  lea     ecx, [rax+30h]; Size
0x18002693f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026944  mov     [rax], rax
0x180026947  mov     [rax+8], rax
0x18002694b  mov     [rax+10h], rax
0x18002694f  mov     word ptr [rax+18h], 101h
0x180026955  mov     cs:?s_defaultRedirectionMap@PolicyRegistryHelper@@0V?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@A, rax; std::map<wchar_t const *,wchar_t const *> PolicyRegistryHelper::s_defaultRedirectionMap
0x18002695c  mov     [rsp+48h+var_20], 1
0x180026964  lea     rax, aUpdateorchestr_2; "UpdateOrchestratorSharedRoot"
0x18002696b  mov     [rsp+48h+var_28], rax
0x180026970  lea     rdx, [rsp+48h+var_28]
0x180026975  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x18002697a  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x180026981  mov     [rax], rcx
0x180026984  lea     rax, aUpdateorchestr; "UpdateOrchestratorConfigurationRoot"
0x18002698b  mov     [rsp+48h+var_28], rax
0x180026990  lea     rdx, [rsp+48h+var_28]
0x180026995  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x18002699a  lea     rcx, aSoftwareMicros_15; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x1800269a1  mov     [rax], rcx
0x1800269a4  lea     rax, aUpdateuxconfig; "UpdateUxConfigurationRoot"
0x1800269ab  mov     [rsp+48h+var_28], rax
0x1800269b0  lea     rdx, [rsp+48h+var_28]
0x1800269b5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x1800269ba  lea     rcx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800269c1  mov     [rax], rcx
0x1800269c4  lea     rax, aUpdateorchestr_1; "UpdateOrchestratorCurrentVersionRoot"
0x1800269cb  mov     [rsp+48h+var_28], rax
0x1800269d0  lea     rdx, [rsp+48h+var_28]
0x1800269d5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x1800269da  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800269e1  mov     [rax], rcx
0x1800269e4  lea     rax, aUpdateorchestr_0; "UpdateOrchestratorRoot"
0x1800269eb  mov     [rsp+48h+var_28], rax
0x1800269f0  lea     rdx, [rsp+48h+var_28]
0x1800269f5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x1800269fa  lea     rcx, aSoftwareMicros_6; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x180026a01  mov     [rax], rcx
0x180026a04  lea     rax, aWindowsupdateu; "WindowsUpdateUXRoot"
0x180026a0b  mov     [rsp+48h+var_28], rax
0x180026a10  lea     rdx, [rsp+48h+var_28]
0x180026a15  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026a1a  lea     rcx, aSoftwareMicros_18; "Software\\Microsoft\\WindowsUpdate\\UX"
0x180026a21  mov     [rax], rcx
0x180026a24  lea     rax, aWindowsupdate; "WindowsUpdate"
0x180026a2b  mov     [rsp+48h+var_28], rax
0x180026a30  lea     rdx, [rsp+48h+var_28]
0x180026a35  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026a3a  lea     rcx, aSoftwareMicros_11; "Software\\Microsoft\\WindowsUpdate"
0x180026a41  mov     [rax], rcx
0x180026a44  lea     rax, aWucurrentversi; "WUCurrentVersion"
0x180026a4b  mov     [rsp+48h+var_28], rax
0x180026a50  lea     rdx, [rsp+48h+var_28]
0x180026a55  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026a5a  lea     rcx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180026a61  mov     [rax], rcx
0x180026a64  lea     rax, aWindowsupdatep; "WindowsUpdatePolicies"
0x180026a6b  mov     [rsp+48h+var_28], rax
0x180026a70  lea     rdx, [rsp+48h+var_28]
0x180026a75  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026a7a  lea     rcx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x180026a81  mov     [rax], rcx
0x180026a84  lea     rax, aDeviceupdate; "DeviceUpdate"
0x180026a8b  mov     [rsp+48h+var_28], rax
0x180026a90  lea     rdx, [rsp+48h+var_28]
0x180026a95  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026a9a  lea     rcx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180026aa1  mov     [rax], rcx
0x180026aa4  lea     rax, aDtuselfhost; "DtuSelfhost"
0x180026aab  mov     [rsp+48h+var_28], rax
0x180026ab0  lea     rdx, [rsp+48h+var_28]
0x180026ab5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026aba  lea     rcx, aSoftwareMicros_14; "Software\\Microsoft\\DTU"
0x180026ac1  mov     [rax], rcx
0x180026ac4  lea     rax, aDtu; "Dtu"
0x180026acb  mov     [rsp+48h+var_28], rax
0x180026ad0  lea     rdx, [rsp+48h+var_28]
0x180026ad5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026ada  lea     rcx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180026ae1  mov     [rax], rcx
0x180026ae4  lea     rax, aSystemsetup; "SystemSetup"
0x180026aeb  mov     [rsp+48h+var_28], rax
0x180026af0  lea     rdx, [rsp+48h+var_28]
0x180026af5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026afa  lea     rcx, aSystemSetup; "System\\Setup"
0x180026b01  mov     [rax], rcx
0x180026b04  lea     rax, aSystemversions; "SystemVersions"
0x180026b0b  mov     [rsp+48h+var_28], rax
0x180026b10  lea     rdx, [rsp+48h+var_28]
0x180026b15  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026b1a  lea     rcx, aSystemVersions; "System\\Versions"
0x180026b21  mov     [rax], rcx
0x180026b24  lea     rax, aUixproductfeat; "UIXProductFeatures"
0x180026b2b  mov     [rsp+48h+var_28], rax
0x180026b30  lea     rdx, [rsp+48h+var_28]
0x180026b35  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026b3a  lea     rcx, aSoftwareMicros_5; "Software\\Microsoft\\UIX\\ProductFeatur"...
0x180026b41  mov     [rax], rcx
0x180026b44  lea     rax, aUsoNetwork; "USO_Network"
0x180026b4b  mov     [rsp+48h+var_28], rax
0x180026b50  lea     rdx, [rsp+48h+var_28]
0x180026b55  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026b5a  lea     rcx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026b61  mov     [rax], rcx
0x180026b64  lea     rax, aDynamicinstall; "DynamicInstalledProducts"
0x180026b6b  mov     [rsp+48h+var_28], rax
0x180026b70  lea     rdx, [rsp+48h+var_28]
0x180026b75  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026b7a  lea     rcx, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180026b81  mov     [rax], rcx
0x180026b84  lea     rax, aReservemanager; "ReserveManager"
0x180026b8b  mov     [rsp+48h+var_28], rax
0x180026b90  lea     rdx, [rsp+48h+var_28]
0x180026b95  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026b9a  lea     rcx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026ba1  mov     [rax], rcx
0x180026ba4  lea     rax, aDeviceaccess; "DeviceAccess"
0x180026bab  mov     [rsp+48h+var_28], rax
0x180026bb0  lea     rdx, [rsp+48h+var_28]
0x180026bb5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026bba  lea     rcx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026bc1  mov     [rax], rcx
0x180026bc4  lea     rax, aCbsinterface; "CBSInterface"
0x180026bcb  mov     [rsp+48h+var_28], rax
0x180026bd0  lea     rdx, [rsp+48h+var_28]
0x180026bd5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026bda  lea     rcx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026be1  mov     [rax], rcx
0x180026be4  lea     rax, aSih; "Sih"
0x180026beb  mov     [rsp+48h+var_28], rax
0x180026bf0  lea     rdx, [rsp+48h+var_28]
0x180026bf5  call    ??A?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::map<wchar_t const *,wchar_t const *>::operator[](wchar_t const * &&)
0x180026bfa  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\sih"
0x180026c01  mov     [rax], rcx
0x180026c04  jmp     short loc_180026C0D
0x180026c06  lea     rbx, ?s_defaultRedirectionMap@PolicyRegistryHelper@@0V?$map@PEB_WPEB_WU?$less@PEB_W@std@@V?$allocator@U?$pair@QEB_WPEB_W@std@@@2@@std@@A; std::map<wchar_t const *,wchar_t const *> PolicyRegistryHelper::s_defaultRedirectionMap
0x180026c0d  mov     rax, rbx
0x180026c10  add     rsp, 40h
0x180026c14  pop     rbx
0x180026c15  retn
```
