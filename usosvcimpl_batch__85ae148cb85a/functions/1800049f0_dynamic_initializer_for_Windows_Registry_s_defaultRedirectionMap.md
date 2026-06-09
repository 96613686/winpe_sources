# _dynamic_initializer_for__Windows::Registry::s_defaultRedirectionMap__

- ea: `0x1800049f0`
- end: `0x180005631`
- name: `_dynamic_initializer_for__Windows::Registry::s_defaultRedirectionMap__`
- size: `3137`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800049f0`
- `0x1800108b4`
- `0x180011320`
- `0x180038694`
- `0x180039074`
- `0x180085160`
- `0x1800dd954`
- `0x1800dddd4`
- `0x1800de12c`

## string_xrefs

- `0x180004a67`: `Software\Microsoft\WindowsUpdate\Orchestrator`
- `0x180004bba`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x180004abb`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Orchestrator`
- `0x180004b11`: `Software\Microsoft\WindowsUpdate\UX`
- `0x180004ce6`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`
- `0x180004d4e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x180004c1c`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x180004c81`: `Software\Microsoft\WindowsUpdate\Orchestrator\Configurations`
- `0x180004db5`: `Software\Microsoft\WindowsUpdate`
- `0x180004e1a`: `Software\Microsoft\Windows\CurrentVersion\UpdatePlatform\UX\Configurations`
- `0x180004f4b`: `Software\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`
- `0x1800051a6`: `Software\Microsoft\Windows\CurrentVersion\InstallService`
- `0x1800050df`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x180005144`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=60
int dynamic_initializer_for__Windows::Registry::s_defaultRedirectionMap__()
{
  __int64 v0; // rbx
  __int64 v1; // r8
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
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // rcx
  _QWORD *v29; // r14
  _BYTE *v30; // rsi
  __int64 v31; // rax
  __int128 v32; // xmm6
  __int64 v33; // rbx
  __int64 *v34; // rdi
  __int64 *v36; // [rsp+28h] [rbp-E0h]
  _QWORD v37[3]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v38; // [rsp+48h] [rbp-C0h]
  _BYTE v39[40]; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v40[2]; // [rsp+78h] [rbp-90h] BYREF
  _OWORD v41[2]; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v42[2]; // [rsp+B8h] [rbp-50h] BYREF
  _OWORD v43[2]; // [rsp+D8h] [rbp-30h] BYREF
  _OWORD v44[2]; // [rsp+F8h] [rbp-10h] BYREF
  _OWORD v45[2]; // [rsp+118h] [rbp+10h] BYREF
  _OWORD v46[2]; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v47[2]; // [rsp+158h] [rbp+50h] BYREF
  _OWORD v48[2]; // [rsp+178h] [rbp+70h] BYREF
  _OWORD v49[2]; // [rsp+198h] [rbp+90h] BYREF
  _OWORD v50[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  _OWORD v51[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  _OWORD v52[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  _OWORD v53[2]; // [rsp+218h] [rbp+110h] BYREF
  _OWORD v54[2]; // [rsp+238h] [rbp+130h] BYREF
  _OWORD v55[2]; // [rsp+258h] [rbp+150h] BYREF
  _OWORD v56[2]; // [rsp+278h] [rbp+170h] BYREF
  _OWORD v57[2]; // [rsp+298h] [rbp+190h] BYREF
  _OWORD v58[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  _OWORD v59[2]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _OWORD v60[2]; // [rsp+2F8h] [rbp+1F0h] BYREF
  _OWORD v61[2]; // [rsp+318h] [rbp+210h] BYREF
  _OWORD v62[2]; // [rsp+338h] [rbp+230h] BYREF
  _OWORD v63[2]; // [rsp+358h] [rbp+250h] BYREF
  _OWORD v64[2]; // [rsp+378h] [rbp+270h] BYREF
  _OWORD v65[2]; // [rsp+398h] [rbp+290h] BYREF
  _OWORD v66[2]; // [rsp+3B8h] [rbp+2B0h] BYREF
  _OWORD v67[2]; // [rsp+3D8h] [rbp+2D0h] BYREF
  _OWORD v68[2]; // [rsp+3F8h] [rbp+2F0h] BYREF
  _OWORD v69[2]; // [rsp+418h] [rbp+310h] BYREF
  _OWORD v70[2]; // [rsp+438h] [rbp+330h] BYREF
  _OWORD v71[2]; // [rsp+458h] [rbp+350h] BYREF
  _OWORD v72[2]; // [rsp+478h] [rbp+370h] BYREF
  _OWORD v73[2]; // [rsp+498h] [rbp+390h] BYREF
  _OWORD v74[2]; // [rsp+4B8h] [rbp+3B0h] BYREF
  _OWORD v75[2]; // [rsp+4D8h] [rbp+3D0h] BYREF
  _OWORD v76[2]; // [rsp+4F8h] [rbp+3F0h] BYREF
  _OWORD v77[2]; // [rsp+518h] [rbp+410h] BYREF
  _OWORD v78[2]; // [rsp+538h] [rbp+430h] BYREF
  _OWORD v79[2]; // [rsp+558h] [rbp+450h] BYREF
  _OWORD v80[2]; // [rsp+578h] [rbp+470h] BYREF
  _OWORD v81[2]; // [rsp+598h] [rbp+490h] BYREF
  _OWORD v82[2]; // [rsp+5B8h] [rbp+4B0h] BYREF
  _OWORD v83[2]; // [rsp+5D8h] [rbp+4D0h] BYREF
  _OWORD v84[2]; // [rsp+5F8h] [rbp+4F0h] BYREF
  _OWORD v85[2]; // [rsp+618h] [rbp+510h] BYREF
  _OWORD v86[2]; // [rsp+638h] [rbp+530h] BYREF
  _OWORD v87[2]; // [rsp+658h] [rbp+550h] BYREF
  _OWORD v88[2]; // [rsp+678h] [rbp+570h] BYREF
  _OWORD v89[2]; // [rsp+698h] [rbp+590h] BYREF
  _OWORD v90[2]; // [rsp+6B8h] [rbp+5B0h] BYREF
  _OWORD v91[2]; // [rsp+6D8h] [rbp+5D0h] BYREF
  _OWORD v92[2]; // [rsp+6F8h] [rbp+5F0h] BYREF
  _OWORD v93[2]; // [rsp+718h] [rbp+610h] BYREF
  _OWORD v94[2]; // [rsp+738h] [rbp+630h] BYREF
  _BYTE v95[48]; // [rsp+758h] [rbp+650h] BYREF

  memset(&v39[8], 0, 32);
  v0 = -1;
  v1 = -1;
  do
    ++v1;
  while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v1] );
  std::wstring::_Construct<1,wchar_t const *>(&v39[8], SystemInterface::Registry::USOROOT_REDIRECTION_ID);
  memset(v40, 0, sizeof(v40));
  std::wstring::_Construct<1,wchar_t const *>(v40, L"Software\\Microsoft\\WindowsUpdate\\Orchestrator");
  memset(v41, 0, sizeof(v41));
  v2 = -1;
  do
    ++v2;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v2] );
  std::wstring::_Construct<1,wchar_t const *>(v41, SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID);
  memset(v42, 0, sizeof(v42));
  std::wstring::_Construct<1,wchar_t const *>(
    v42,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Orchestrator");
  memset(v43, 0, sizeof(v43));
  v3 = -1;
  do
    ++v3;
  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v3] );
  std::wstring::_Construct<1,wchar_t const *>(v43, SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID);
  memset(v44, 0, sizeof(v44));
  std::wstring::_Construct<1,wchar_t const *>(v44, L"Software\\Microsoft\\WindowsUpdate\\UX");
  memset(v45, 0, sizeof(v45));
  v4 = -1;
  do
    ++v4;
  while ( SystemInterface::Registry::CURRENTVERSION_REDIRECTION_ID[v4] );
  std::wstring::_Construct<1,wchar_t const *>(v45, SystemInterface::Registry::CURRENTVERSION_REDIRECTION_ID);
  memset(v46, 0, sizeof(v46));
  std::wstring::_Construct<1,wchar_t const *>(v46, L"Software\\Microsoft\\Windows\\CurrentVersion");
  memset(v47, 0, sizeof(v47));
  v5 = -1;
  do
    ++v5;
  while ( SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID[v5] );
  std::wstring::_Construct<1,wchar_t const *>(v47, SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID);
  memset(v48, 0, sizeof(v48));
  std::wstring::_Construct<1,wchar_t const *>(v48, L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate");
  memset(v49, 0, sizeof(v49));
  v6 = -1;
  do
    ++v6;
  while ( SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID[v6] );
  std::wstring::_Construct<1,wchar_t const *>(v49, SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID);
  memset(v50, 0, sizeof(v50));
  std::wstring::_Construct<1,wchar_t const *>(
    v50,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\DynamicInstalled");
  memset(v51, 0, sizeof(v51));
  v7 = -1;
  do
    ++v7;
  while ( SystemInterface::Registry::USOCONFIGURATIONROOT_REDIRECTION_ID[v7] );
  std::wstring::_Construct<1,wchar_t const *>(v51, SystemInterface::Registry::USOCONFIGURATIONROOT_REDIRECTION_ID);
  memset(v52, 0, sizeof(v52));
  std::wstring::_Construct<1,wchar_t const *>(v52, L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Configurations");
  memset(v53, 0, sizeof(v53));
  v8 = -1;
  do
    ++v8;
  while ( SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID[v8] );
  std::wstring::_Construct<1,wchar_t const *>(v53, SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID);
  memset(v54, 0, sizeof(v54));
  std::wstring::_Construct<1,wchar_t const *>(
    v54,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface");
  memset(v55, 0, sizeof(v55));
  v9 = -1;
  do
    ++v9;
  while ( SystemInterface::Registry::DEVICEACCESS_REDIRECTION_ID[v9] );
  std::wstring::_Construct<1,wchar_t const *>(v55, SystemInterface::Registry::DEVICEACCESS_REDIRECTION_ID);
  memset(v56, 0, sizeof(v56));
  std::wstring::_Construct<1,wchar_t const *>(v56, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess");
  memset(v57, 0, sizeof(v57));
  v10 = -1;
  do
    ++v10;
  while ( SystemInterface::Registry::WU_REDIRECTION_ID[v10] );
  std::wstring::_Construct<1,wchar_t const *>(v57, SystemInterface::Registry::WU_REDIRECTION_ID);
  memset(v58, 0, sizeof(v58));
  std::wstring::_Construct<1,wchar_t const *>(v58, L"Software\\Microsoft\\WindowsUpdate");
  memset(v59, 0, sizeof(v59));
  v11 = -1;
  do
    ++v11;
  while ( SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID[v11] );
  std::wstring::_Construct<1,wchar_t const *>(v59, SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID);
  memset(v60, 0, sizeof(v60));
  std::wstring::_Construct<1,wchar_t const *>(
    v60,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\UpdatePlatform\\UX\\Configurations");
  memset(v61, 0, sizeof(v61));
  v12 = -1;
  do
    ++v12;
  while ( SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID[v12] );
  std::wstring::_Construct<1,wchar_t const *>(v61, SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID);
  memset(v62, 0, sizeof(v62));
  std::wstring::_Construct<1,wchar_t const *>(v62, L"Software\\Microsoft\\Windows\\CurrentVersion\\ReserveManager");
  memset(v63, 0, sizeof(v63));
  v13 = -1;
  do
    ++v13;
  while ( SystemInterface::Registry::LOGONUI_REDIRECTION_ID[v13] );
  std::wstring::_Construct<1,wchar_t const *>(v63, SystemInterface::Registry::LOGONUI_REDIRECTION_ID);
  memset(v64, 0, sizeof(v64));
  std::wstring::_Construct<1,wchar_t const *>(
    v64,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI");
  memset(v65, 0, sizeof(v65));
  v14 = -1;
  do
    ++v14;
  while ( SystemInterface::Registry::SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID[v14] );
  std::wstring::_Construct<1,wchar_t const *>(v65, SystemInterface::Registry::SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID);
  memset(v66, 0, sizeof(v66));
  std::wstring::_Construct<1,wchar_t const *>(
    v66,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData");
  memset(v67, 0, sizeof(v67));
  v15 = -1;
  do
    ++v15;
  while ( SystemInterface::Registry::SETUP_OOBE_REDIRECTION_ID[v15] );
  std::wstring::_Construct<1,wchar_t const *>(v67, SystemInterface::Registry::SETUP_OOBE_REDIRECTION_ID);
  memset(v68, 0, sizeof(v68));
  std::wstring::_Construct<1,wchar_t const *>(v68, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE");
  memset(v69, 0, sizeof(v69));
  v16 = -1;
  do
    ++v16;
  while ( SystemInterface::Registry::WINNTCURRENTVERSIONROOT_REDIRECTION_ID[v16] );
  std::wstring::_Construct<1,wchar_t const *>(v69, SystemInterface::Registry::WINNTCURRENTVERSIONROOT_REDIRECTION_ID);
  memset(v70, 0, sizeof(v70));
  std::wstring::_Construct<1,wchar_t const *>(v70, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion");
  memset(v71, 0, sizeof(v71));
  v17 = -1;
  do
    ++v17;
  while ( SystemInterface::Registry::SYSTEM_SETUP_REDIRECTIONID[v17] );
  std::wstring::_Construct<1,wchar_t const *>(v71, SystemInterface::Registry::SYSTEM_SETUP_REDIRECTIONID);
  memset(v72, 0, sizeof(v72));
  std::wstring::_Construct<1,wchar_t const *>(v72, L"SYSTEM\\Setup");
  memset(v73, 0, sizeof(v73));
  v18 = -1;
  do
    ++v18;
  while ( SystemInterface::Registry::WIN32_UNINSTALL_REDIRECTIONID[v18] );
  std::wstring::_Construct<1,wchar_t const *>(v73, SystemInterface::Registry::WIN32_UNINSTALL_REDIRECTIONID);
  memset(v74, 0, sizeof(v74));
  std::wstring::_Construct<1,wchar_t const *>(v74, L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall");
  memset(v75, 0, sizeof(v75));
  v19 = -1;
  do
    ++v19;
  while ( SystemInterface::Registry::WIN32_UNINSTALL_ALT_REDIRECTIONID[v19] );
  std::wstring::_Construct<1,wchar_t const *>(v75, SystemInterface::Registry::WIN32_UNINSTALL_ALT_REDIRECTIONID);
  memset(v76, 0, sizeof(v76));
  std::wstring::_Construct<1,wchar_t const *>(
    v76,
    L"Software\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall");
  memset(v77, 0, sizeof(v77));
  v20 = -1;
  do
    ++v20;
  while ( SystemInterface::Registry::INSTALLSERVICECURRENTVERSIONROOT_REDIRECTION_ID[v20] );
  std::wstring::_Construct<1,wchar_t const *>(
    v77,
    SystemInterface::Registry::INSTALLSERVICECURRENTVERSIONROOT_REDIRECTION_ID);
  memset(v78, 0, sizeof(v78));
  std::wstring::_Construct<1,wchar_t const *>(v78, L"Software\\Microsoft\\Windows\\CurrentVersion\\InstallService");
  memset(v79, 0, sizeof(v79));
  v21 = -1;
  do
    ++v21;
  while ( SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID[v21] );
  std::wstring::_Construct<1,wchar_t const *>(v79, SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID);
  memset(v80, 0, sizeof(v80));
  std::wstring::_Construct<1,wchar_t const *>(v80, L"SOFTWARE\\Policies\\Microsoft\\Windows");
  memset(v81, 0, sizeof(v81));
  v22 = -1;
  do
    ++v22;
  while ( SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID[v22] );
  std::wstring::_Construct<1,wchar_t const *>(v81, SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID);
  memset(v82, 0, sizeof(v82));
  std::wstring::_Construct<1,wchar_t const *>(v82, L"SYSTEM\\CurrentControlSet\\Control");
  memset(v83, 0, sizeof(v83));
  v23 = -1;
  do
    ++v23;
  while ( SystemInterface::Registry::POLICYMANAGER_CURRENT_DHM_ID[v23] );
  std::wstring::_Construct<1,wchar_t const *>(v83, SystemInterface::Registry::POLICYMANAGER_CURRENT_DHM_ID);
  memset(v84, 0, sizeof(v84));
  std::wstring::_Construct<1,wchar_t const *>(
    v84,
    L"SOFTWARE\\Microsoft\\PolicyManager\\current\\device\\DeviceHealthMonitoring");
  memset(v85, 0, sizeof(v85));
  v24 = -1;
  do
    ++v24;
  while ( SystemInterface::Registry::CURRENTVERSIONAPPX_REDIRECTION_ID[v24] );
  std::wstring::_Construct<1,wchar_t const *>(v85, SystemInterface::Registry::CURRENTVERSIONAPPX_REDIRECTION_ID);
  memset(v86, 0, sizeof(v86));
  std::wstring::_Construct<1,wchar_t const *>(v86, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx");
  memset(v87, 0, sizeof(v87));
  v25 = -1;
  do
    ++v25;
  while ( SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID[v25] );
  std::wstring::_Construct<1,wchar_t const *>(v87, SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID);
  memset(v88, 0, sizeof(v88));
  std::wstring::_Construct<1,wchar_t const *>(v88, L"SOFTWARE\\Microsoft\\PolicyManager\\current\\device");
  memset(v89, 0, sizeof(v89));
  v26 = -1;
  do
    ++v26;
  while ( SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID[v26] );
  std::wstring::_Construct<1,wchar_t const *>(
    v89,
    SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID);
  memset(v90, 0, sizeof(v90));
  std::wstring::_Construct<1,wchar_t const *>(v90, L"SOFTWARE\\Policies\\Microsoft\\WindowsStore");
  memset(v91, 0, sizeof(v91));
  v27 = -1;
  do
    ++v27;
  while ( SystemInterface::Registry::CURRENTVERSION_WINDOWSSTORE_REDIRECTION_ID[v27] );
  std::wstring::_Construct<1,wchar_t const *>(
    v91,
    SystemInterface::Registry::CURRENTVERSION_WINDOWSSTORE_REDIRECTION_ID);
  memset(v92, 0, sizeof(v92));
  std::wstring::_Construct<1,wchar_t const *>(v92, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsStore");
  memset(v93, 0, sizeof(v93));
  do
    ++v0;
  while ( SystemInterface::Registry::SOFTWARE_MICROSOFT_REDIRECTION_ID[v0] );
  std::wstring::_Construct<1,wchar_t const *>(v93, SystemInterface::Registry::SOFTWARE_MICROSOFT_REDIRECTION_ID);
  memset(v94, 0, sizeof(v94));
  std::wstring::_Construct<1,wchar_t const *>(v94, L"SOFTWARE\\Microsoft");
  Windows::Registry::s_defaultRedirectionMap = 0;
  qword_180150910 = 0;
  v29 = operator new(0x60u);
  *v29 = v29;
  v29[1] = v29;
  v29[2] = v29;
  *((_WORD *)v29 + 12) = 257;
  Windows::Registry::s_defaultRedirectionMap = (__int64)v29;
  v30 = &v39[8];
  do
  {
    v31 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_hint<std::wstring>(
            v28,
            v95,
            v29,
            v30,
            v36);
    v32 = *(_OWORD *)v31;
    v38 = *(_QWORD *)(v31 + 16);
    if ( !(_BYTE)v38 )
    {
      if ( qword_180150910 == 0x2AAAAAAAAAAAAAALL )
        std::_Throw_tree_length_error();
      v33 = Windows::Registry::s_defaultRedirectionMap;
      v36 = &Windows::Registry::s_defaultRedirectionMap;
      v34 = (__int64 *)operator new(0x60u);
      std::wstring::wstring(v34 + 4, v30);
      std::wstring::wstring(v34 + 8, v30 + 32);
      *v34 = v33;
      v34[1] = v33;
      v34[2] = v33;
      *((_WORD *)v34 + 12) = 0;
      *(_OWORD *)&v37[1] = v32;
      std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::hstring>>>::_Insert_node(
        &Windows::Registry::s_defaultRedirectionMap,
        &v37[1],
        v34);
    }
    v30 += 64;
  }
  while ( v30 != v95 );
  `eh vector destructor iterator'(
    &v39[8],
    0x40u,
    0x1Cu,
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::Registry::s_defaultRedirectionMap__);
}

```

## disassembly

```asm
0x1800049f0  mov     rax, rsp
0x1800049f3  mov     [rax+10h], rbx
0x1800049f7  mov     [rax+18h], rsi
0x1800049fb  mov     [rax+20h], rdi
0x1800049ff  push    rbp
0x180004a00  push    r12
0x180004a02  push    r13
0x180004a04  push    r14
0x180004a06  push    r15
0x180004a08  lea     rbp, [rax-6A8h]
0x180004a0f  sub     rsp, 780h
0x180004a16  movaps  xmmword ptr [rax-38h], xmm6
0x180004a1a  mov     rdx, cs:?USOROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOROOT_REDIRECTION_ID
0x180004a21  xorps   xmm0, xmm0
0x180004a24  movups  [rsp+7A0h+var_758+8], xmm0
0x180004a29  xorps   xmm1, xmm1
0x180004a2c  movdqa  [rsp+7A0h+var_748+8], xmm1
0x180004a32  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004a36  mov     r8, rbx
0x180004a39  xor     r15d, r15d
0x180004a3c  inc     r8
0x180004a3f  cmp     [rdx+r8*2], r15w
0x180004a44  jnz     short loc_180004A3C
0x180004a46  lea     rcx, [rsp+7A0h+var_758+8]
0x180004a4b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004a50  nop
0x180004a51  xorps   xmm0, xmm0
0x180004a54  movups  [rsp+7A0h+var_738+8], xmm0
0x180004a59  xorps   xmm1, xmm1
0x180004a5c  movdqa  [rbp+6A0h+var_720], xmm1
0x180004a61  mov     r8d, 2Dh ; '-'
0x180004a67  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x180004a6e  lea     rcx, [rsp+7A0h+var_738+8]
0x180004a73  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004a78  nop
0x180004a79  mov     rdx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x180004a80  xorps   xmm0, xmm0
0x180004a83  movups  [rbp+6A0h+var_710], xmm0
0x180004a87  xorps   xmm1, xmm1
0x180004a8a  movdqa  [rbp+6A0h+var_700], xmm1
0x180004a8f  mov     r8, rbx
0x180004a92  inc     r8
0x180004a95  cmp     [rdx+r8*2], r15w
0x180004a9a  jnz     short loc_180004A92
0x180004a9c  lea     rcx, [rbp+6A0h+var_710]
0x180004aa0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004aa5  nop
0x180004aa6  xorps   xmm0, xmm0
0x180004aa9  movups  [rbp+6A0h+var_6F0], xmm0
0x180004aad  xorps   xmm1, xmm1
0x180004ab0  movdqa  [rbp+6A0h+var_6E0], xmm1
0x180004ab5  mov     r8d, 44h ; 'D'
0x180004abb  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004ac2  lea     rcx, [rbp+6A0h+var_6F0]
0x180004ac6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004acb  nop
0x180004acc  mov     rdx, cs:?UPDATEUXROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID
0x180004ad3  xorps   xmm0, xmm0
0x180004ad6  movups  [rbp+6A0h+var_6D0], xmm0
0x180004ada  xorps   xmm1, xmm1
0x180004add  movdqa  [rbp+6A0h+var_6C0], xmm1
0x180004ae2  mov     r8, rbx
0x180004ae5  inc     r8
0x180004ae8  cmp     [rdx+r8*2], r15w
0x180004aed  jnz     short loc_180004AE5
0x180004aef  lea     rcx, [rbp+6A0h+var_6D0]
0x180004af3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004af8  nop
0x180004af9  xorps   xmm0, xmm0
0x180004afc  movups  [rbp+6A0h+var_6B0], xmm0
0x180004b00  xorps   xmm1, xmm1
0x180004b03  movdqa  [rbp+6A0h+var_6A0], xmm1
0x180004b08  mov     r14d, 23h ; '#'
0x180004b0e  mov     r8d, r14d
0x180004b11  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\WindowsUpdate\\UX"
0x180004b18  lea     rcx, [rbp+6A0h+var_6B0]
0x180004b1c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004b21  nop
0x180004b22  mov     rdx, cs:?CURRENTVERSION_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTVERSION_REDIRECTION_ID
0x180004b29  xorps   xmm0, xmm0
0x180004b2c  movups  [rbp+6A0h+var_690], xmm0
0x180004b30  xorps   xmm1, xmm1
0x180004b33  movdqa  [rbp+6A0h+var_680], xmm1
0x180004b38  mov     r8, rbx
0x180004b3b  inc     r8
0x180004b3e  cmp     [rdx+r8*2], r15w
0x180004b43  jnz     short loc_180004B3B
0x180004b45  lea     rcx, [rbp+6A0h+var_690]
0x180004b49  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004b4e  nop
0x180004b4f  xorps   xmm0, xmm0
0x180004b52  movups  [rbp+6A0h+var_670], xmm0
0x180004b56  xorps   xmm1, xmm1
0x180004b59  movdqa  [rbp+6A0h+var_660], xmm1
0x180004b5e  mov     r8d, 29h ; ')'
0x180004b64  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004b6b  lea     rcx, [rbp+6A0h+var_670]
0x180004b6f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004b74  nop
0x180004b75  mov     rdx, cs:?CURRENTVERSIONWU_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID
0x180004b7c  xorps   xmm0, xmm0
0x180004b7f  movups  [rbp+6A0h+var_650], xmm0
0x180004b83  xorps   xmm1, xmm1
0x180004b86  movdqa  [rbp+6A0h+var_640], xmm1
0x180004b8b  mov     r8, rbx
0x180004b8e  inc     r8
0x180004b91  cmp     [rdx+r8*2], r15w
0x180004b96  jnz     short loc_180004B8E
0x180004b98  lea     rcx, [rbp+6A0h+var_650]
0x180004b9c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004ba1  nop
0x180004ba2  xorps   xmm0, xmm0
0x180004ba5  movups  [rbp+6A0h+var_630], xmm0
0x180004ba9  xorps   xmm1, xmm1
0x180004bac  movdqa  [rbp+6A0h+var_620], xmm1
0x180004bb4  mov     r8d, 37h ; '7'
0x180004bba  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004bc1  lea     rcx, [rbp+6A0h+var_630]
0x180004bc5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004bca  nop
0x180004bcb  mov     rdx, cs:?UUP_DYN_INSTALLED_PROD_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID
0x180004bd2  xorps   xmm0, xmm0
0x180004bd5  movups  [rbp+6A0h+var_610], xmm0
0x180004bdc  xorps   xmm1, xmm1
0x180004bdf  movdqa  [rbp+6A0h+var_600], xmm1
0x180004be7  mov     r8, rbx
0x180004bea  inc     r8
0x180004bed  cmp     [rdx+r8*2], r15w
0x180004bf2  jnz     short loc_180004BEA
0x180004bf4  lea     rcx, [rbp+6A0h+var_610]
0x180004bfb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004c00  nop
0x180004c01  xorps   xmm0, xmm0
0x180004c04  movups  [rbp+6A0h+var_5F0], xmm0
0x180004c0b  xorps   xmm1, xmm1
0x180004c0e  movdqa  [rbp+6A0h+var_5E0], xmm1
0x180004c16  mov     r8d, 52h ; 'R'
0x180004c1c  lea     rdx, aSoftwareMicros_20; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180004c23  lea     rcx, [rbp+6A0h+var_5F0]
0x180004c2a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004c2f  nop
0x180004c30  mov     rdx, cs:?USOCONFIGURATIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCONFIGURATIONROOT_REDIRECTION_ID
0x180004c37  xorps   xmm0, xmm0
0x180004c3a  movups  [rbp+6A0h+var_5D0], xmm0
0x180004c41  xorps   xmm1, xmm1
0x180004c44  movdqa  [rbp+6A0h+var_5C0], xmm1
0x180004c4c  mov     r8, rbx
0x180004c4f  inc     r8
0x180004c52  cmp     [rdx+r8*2], r15w
0x180004c57  jnz     short loc_180004C4F
0x180004c59  lea     rcx, [rbp+6A0h+var_5D0]
0x180004c60  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004c65  nop
0x180004c66  xorps   xmm0, xmm0
0x180004c69  movups  [rbp+6A0h+var_5B0], xmm0
0x180004c70  xorps   xmm1, xmm1
0x180004c73  movdqa  [rbp+6A0h+var_5A0], xmm1
0x180004c7b  mov     r8d, 3Ch ; '<'
0x180004c81  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x180004c88  lea     rcx, [rbp+6A0h+var_5B0]
0x180004c8f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004c94  nop
0x180004c95  mov     rdx, cs:?CBSINTERFACE_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID
0x180004c9c  xorps   xmm0, xmm0
0x180004c9f  movups  [rbp+6A0h+var_590], xmm0
0x180004ca6  xorps   xmm1, xmm1
0x180004ca9  movdqa  [rbp+6A0h+var_580], xmm1
0x180004cb1  mov     r8, rbx
0x180004cb4  inc     r8
0x180004cb7  cmp     [rdx+r8*2], r15w
0x180004cbc  jnz     short loc_180004CB4
0x180004cbe  lea     rcx, [rbp+6A0h+var_590]
0x180004cc5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004cca  nop
0x180004ccb  xorps   xmm0, xmm0
0x180004cce  movups  [rbp+6A0h+var_570], xmm0
0x180004cd5  xorps   xmm1, xmm1
0x180004cd8  movdqa  [rbp+6A0h+var_560], xmm1
0x180004ce0  mov     r8d, 4Dh ; 'M'
0x180004ce6  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180004ced  lea     rcx, [rbp+6A0h+var_570]
0x180004cf4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004cf9  nop
0x180004cfa  mov     rdx, cs:?DEVICEACCESS_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::DEVICEACCESS_REDIRECTION_ID
0x180004d01  xorps   xmm0, xmm0
0x180004d04  movups  [rbp+6A0h+var_550], xmm0
0x180004d0b  xorps   xmm1, xmm1
0x180004d0e  movdqa  [rbp+6A0h+var_540], xmm1
0x180004d16  mov     r8, rbx
0x180004d19  inc     r8
0x180004d1c  cmp     [rdx+r8*2], r15w
0x180004d21  jnz     short loc_180004D19
0x180004d23  lea     rcx, [rbp+6A0h+var_550]
0x180004d2a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004d2f  nop
0x180004d30  xorps   xmm0, xmm0
0x180004d33  movups  [rbp+6A0h+var_530], xmm0
0x180004d3a  xorps   xmm1, xmm1
0x180004d3d  movdqa  [rbp+6A0h+var_520], xmm1
0x180004d45  mov     r12d, 36h ; '6'
0x180004d4b  mov     r8d, r12d
0x180004d4e  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180004d55  lea     rcx, [rbp+6A0h+var_530]
0x180004d5c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004d61  nop
0x180004d62  mov     rdx, cs:?WU_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::WU_REDIRECTION_ID
0x180004d69  xorps   xmm0, xmm0
0x180004d6c  movups  [rbp+6A0h+var_510], xmm0
0x180004d73  xorps   xmm1, xmm1
0x180004d76  movdqa  [rbp+6A0h+var_500], xmm1
0x180004d7e  mov     r8, rbx
0x180004d81  inc     r8
0x180004d84  cmp     [rdx+r8*2], r15w
0x180004d89  jnz     short loc_180004D81
0x180004d8b  lea     rcx, [rbp+6A0h+var_510]
0x180004d92  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004d97  nop
0x180004d98  xorps   xmm0, xmm0
0x180004d9b  movups  [rbp+6A0h+var_4F0], xmm0
0x180004da2  xorps   xmm1, xmm1
0x180004da5  movdqa  [rbp+6A0h+var_4E0], xmm1
0x180004dad  mov     esi, 20h ; ' '
0x180004db2  mov     r8d, esi
0x180004db5  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\WindowsUpdate"
0x180004dbc  lea     rcx, [rbp+6A0h+var_4F0]
0x180004dc3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004dc8  nop
0x180004dc9  mov     rdx, cs:?UXCONFIGURATIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID
0x180004dd0  xorps   xmm0, xmm0
0x180004dd3  movups  [rbp+6A0h+var_4D0], xmm0
0x180004dda  xorps   xmm1, xmm1
0x180004ddd  movdqa  [rbp+6A0h+var_4C0], xmm1
0x180004de5  mov     r8, rbx
0x180004de8  inc     r8
0x180004deb  cmp     [rdx+r8*2], r15w
0x180004df0  jnz     short loc_180004DE8
0x180004df2  lea     rcx, [rbp+6A0h+var_4D0]
0x180004df9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004dfe  nop
0x180004dff  xorps   xmm0, xmm0
0x180004e02  movups  [rbp+6A0h+var_4B0], xmm0
0x180004e09  xorps   xmm1, xmm1
0x180004e0c  movdqa  [rbp+6A0h+var_4A0], xmm1
0x180004e14  mov     r8d, 4Ah ; 'J'
0x180004e1a  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004e21  lea     rcx, [rbp+6A0h+var_4B0]
0x180004e28  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004e2d  nop
0x180004e2e  mov     rdx, cs:?RESERVEMANAGER_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID
0x180004e35  xorps   xmm0, xmm0
0x180004e38  movups  [rbp+6A0h+var_490], xmm0
0x180004e3f  xorps   xmm1, xmm1
0x180004e42  movdqa  [rbp+6A0h+var_480], xmm1
0x180004e4a  mov     r8, rbx
0x180004e4d  inc     r8
0x180004e50  cmp     [rdx+r8*2], r15w
0x180004e55  jnz     short loc_180004E4D
0x180004e57  lea     rcx, [rbp+6A0h+var_490]
0x180004e5e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004e63  nop
0x180004e64  xorps   xmm0, xmm0
0x180004e67  movups  [rbp+6A0h+var_470], xmm0
0x180004e6e  xorps   xmm1, xmm1
0x180004e71  movdqa  [rbp+6A0h+var_460], xmm1
0x180004e79  mov     edi, 38h ; '8'
0x180004e7e  mov     r8d, edi
0x180004e81  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004e88  lea     rcx, [rbp+6A0h+var_470]
0x180004e8f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004e94  nop
0x180004e95  mov     rdx, cs:?LOGONUI_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::LOGONUI_REDIRECTION_ID
0x180004e9c  xorps   xmm0, xmm0
0x180004e9f  movups  [rbp+6A0h+var_450], xmm0
0x180004ea6  xorps   xmm1, xmm1
0x180004ea9  movdqa  [rbp+6A0h+var_440], xmm1
0x180004eb1  mov     r8, rbx
0x180004eb4  inc     r8
0x180004eb7  cmp     [rdx+r8*2], r15w
0x180004ebc  jnz     short loc_180004EB4
0x180004ebe  lea     rcx, [rbp+6A0h+var_450]
0x180004ec5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004eca  nop
0x180004ecb  xorps   xmm0, xmm0
0x180004ece  movups  [rbp+6A0h+var_430], xmm0
0x180004ed5  xorps   xmm1, xmm1
0x180004ed8  movdqa  [rbp+6A0h+var_420], xmm1
0x180004ee0  mov     r8d, 40h ; '@'
0x180004ee6  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004eed  lea     rcx, [rbp+6A0h+var_430]
0x180004ef4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004ef9  nop
0x180004efa  mov     rdx, cs:?SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::SYSTEMPROTECTEDUSERDATA_REDIRECTION_ID
0x180004f01  xorps   xmm0, xmm0
0x180004f04  movups  [rbp+6A0h+var_410], xmm0
0x180004f0b  xorps   xmm1, xmm1
0x180004f0e  movdqa  [rbp+6A0h+var_400], xmm1
0x180004f16  mov     r8, rbx
0x180004f19  inc     r8
0x180004f1c  cmp     [rdx+r8*2], r15w
0x180004f21  jnz     short loc_180004F19
  ... truncated ...
```
