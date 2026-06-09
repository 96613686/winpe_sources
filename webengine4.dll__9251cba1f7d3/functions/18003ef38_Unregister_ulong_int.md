# Unregister(ulong,int)

- ea: `0x18003ef38`
- end: `0x18003f775`
- name: `?Unregister@@YAJKH@Z`
- size: `2109`
- prototype: `int(unsigned int, int)`
- caller_count: `2`
- callee_count: `53`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180040500`
- `0x1800413f0`

## callees

- `0x180007824`
- `0x18000b190`
- `0x18000b19c`
- `0x18000b1f8`
- `0x18000c534`
- `0x18000c598`
- `0x18000cfc4`
- `0x18000d1a8`
- `0x18000d1d4`
- `0x18000d25c`
- `0x18000d52c`
- `0x18000d9f0`
- `0x18000dd04`
- `0x180012b30`
- `0x18001c550`
- `0x1800269c8`
- `0x180026de0`
- `0x18002a454`
- `0x18002b0e0`
- `0x180031fd8`
- `0x180036aa0`
- `0x180037324`
- `0x1800376f8`
- `0x18003785c`
- `0x1800379dc`
- `0x1800393c4`
- `0x180039774`
- `0x180039d08`
- `0x18003a498`
- `0x18003a78c`
- `0x18003abe4`
- `0x18003acf0`
- `0x18003b900`
- `0x18003c630`
- `0x18003ca0c`
- `0x18003ccd4`
- `0x18003d160`
- `0x18003d288`
- `0x18003d858`
- `0x18003dd70`
- `0x18003e2e8`
- `0x18003e744`
- `0x18003e808`
- `0x18003ea5c`
- `0x18003ea8c`
- `0x18003ef38`
- `0x18003f800`
- `0x180040fa0`
- `0x180042d70`
- `0x18004d030`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003f54c`
- `KERNEL32!CloseHandle` at `0x18003f54c`
- `KERNEL32!CreateFileW` at `0x18003f53d`
- `KERNEL32!CreateFileW` at `0x18003f53d`
- `KERNEL32!FreeLibrary` at `0x18003f5c6`
- `KERNEL32!FreeLibrary` at `0x18003f5c6`
- `KERNEL32!GetProcAddress` at `0x18003f369`
- `KERNEL32!GetProcAddress` at `0x18003f38c`
- `KERNEL32!GetProcAddress` at `0x18003f45f`
- `KERNEL32!GetProcAddress` at `0x18003f571`
- `KERNEL32!GetProcAddress` at `0x18003f369`
- `KERNEL32!GetProcAddress` at `0x18003f38c`
- `KERNEL32!GetProcAddress` at `0x18003f45f`
- `KERNEL32!GetProcAddress` at `0x18003f571`
- `KERNEL32!LoadLibraryExW` at `0x18003f328`
- `KERNEL32!LoadLibraryExW` at `0x18003f328`

## string_xrefs

- `0x18003f5f5`: `StateService.Uninstall`
- `0x18003f455`: `InstallMOF`
- `0x18003f47e`: `InstallMOF`
- `0x18003f4a9`: `InstallMOF`
- `0x18003f1ec`: `XSP.UninstallPerVer`
- `0x18003f06d`: `AdminService.Uninstall`
- `0x18003f300`: `Loading previously installed ASP.NET isapi`
- `0x18003f330`: `Loading previously installed ASP.NET isapi`
- `0x18003f0f5`: `Exit because the current version is not installed.`
- `0x18003f113`: `Exit because the current version is not installed.`
- `0x18003f174`: `Disabling ASPNET account and removing ACLs`
- `0x18003f19a`: `Disabling ASPNET account and removing ACLs`
- `0x18003f249`: `Disabling ASPNET account and removing ACLs`
- `0x18003f271`: `Disabling ASPNET account and removing ACLs`
- `0x18003f2b6`: `Getting previously installed ASP.NET isapi information`
- `0x18003f35f`: `InstallServices`
- `0x18003f41f`: `InstallServices`
- `0x18003f446`: `InstallServices`
- `0x18003f418`: `Installing previously installed ASP.NET services`
- `0x18003f43d`: `Installing previously installed ASP.NET services`
- `0x18003f382`: `InstallStateService`
- `0x18003f3ce`: `InstallStateService`
- `0x18003f3f5`: `InstallStateService`
- `0x18003f3c4`: `Installing previously installed ASP.NET state service`
- `0x18003f3ec`: `Installing previously installed ASP.NET state service`
- `0x18003f46f`: `Installing previous ASP.NET MOF file`
- `0x18003f498`: `Installing previous ASP.NET MOF file`
- `0x18003f567`: `InstallMMCComComponents`
- `0x18003f616`: `XSP.UninstallAllVer`
- `0x18003f641`: `MmcAspNetExtCOMComponents.Uninstall`

## pseudocode

```c
__int64 __fastcall Unregister(unsigned int a1, int a2)
{
  int v4; // r13d
  BOOL v5; // r12d
  int v6; // eax
  unsigned int v7; // ecx
  unsigned int IsVerInstalled; // ebx
  int v9; // eax
  int v10; // r14d
  int v11; // eax
  int inited; // eax
  int v13; // eax
  int v14; // ecx
  int v15; // ebx
  HMODULE Library; // rsi
  __int64 (*ProcAddress)(void); // rbx
  __int64 (*v18)(void); // rbx
  int v19; // eax
  int v20; // eax
  __int64 (*v21)(void); // rbx
  int v22; // eax
  HANDLE FileW; // rax
  unsigned int (*v24)(void); // rax
  unsigned int v25; // r8d
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v33[16]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v34[2]; // [rsp+68h] [rbp-98h] BYREF
  char v35; // [rsp+7Ch] [rbp-84h]
  _BYTE v36[24]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpLibFileName; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v38; // [rsp+A8h] [rbp-58h]
  WCHAR FileName[520]; // [rsp+120h] [rbp+20h] BYREF

  v27 = 0;
  v28 = 0;
  CASPNET_VER_LIST::CASPNET_VER_LIST((CASPNET_VER_LIST *)v33);
  v30 = 0;
  v4 = 0;
  v5 = 0;
  XspLogEvent(0x40000403u);
  CSetupLogging::Init(1, a1);
  if ( (unsigned int)IsVista() )
  {
    v6 = IIS7UnRegister();
    v7 = v28;
    if ( v6 == 1 )
      v7 = 1;
    v28 = v7;
  }
  if ( a1 == 2 )
  {
    IsVerInstalled = UninstallAllUsingHighest(a2, (int *)&v29);
    if ( IsVerInstalled || v29 )
      goto LABEL_85;
  }
  else
  {
    IsVerInstalled = CRegInfo::IsVerInstalled((struct ASPNETVER *)&ASPNETVER::m_gThisVer, (int *)&v29);
    if ( IsVerInstalled )
      goto LABEL_85;
    if ( !v29 )
    {
      CSetupLogging::Log(1, "Unregister", 0, "Exit because the current version is not installed.", 0);
      CSetupLogging::Log(0, "Unregister", 0, "Exit because the current version is not installed.", 0);
      goto LABEL_85;
    }
  }
  if ( (unsigned int)IsVista() && a1 == 2 )
  {
    v4 = 1;
    a1 = 1;
  }
  IsCurrentHighest(&v30, (int *)&v31);
  if ( !(unsigned int)IsVista() )
  {
    GetServiceStatus(&v32, L"iisadmin");
    CheckIISState(&v28);
    GetServiceStatus(&v31, L"w3svc");
  }
  StopServiceByName(&v29, L"aspnet_state", 0);
  InstallInfSections(g_DllInstance, 1, L"AdminService.Uninstall", 0);
  CRegInfo::RegCleanup(1u);
  if ( v28 == 4 )
    UnregisterIIS(a1 == 2);
  if ( a1 == 2 )
  {
    CRegInfo::CRegInfo((CRegInfo *)v36);
    v9 = IsVista();
    CRegInfo::GetVerInfoList((CRegInfo *)v36, 0, (struct CASPNET_VER_LIST *)v33, 0, v9);
    CRegInfo::~CRegInfo((CRegInfo *)v36);
  }
  else
  {
    CASPNET_VER_LIST::Add(
      (CASPNET_VER_LIST *)v33,
      L"4.0.30319.0",
      0,
      &Names::s_wszIsapiFullPath,
      &Names::s_wszInstallDirectory);
  }
  RegisterSystemWebAssembly(0);
  SetDCOMKeys(0);
  v10 = v30;
  if ( a1 == 2 )
  {
    CSetupLogging::Log(1, "DisablingASPNETAccount", 0, "Disabling ASPNET account and removing ACLs", 0);
    v11 = CRegAccount::UndoReg(1, 1);
    CSetupLogging::Log(v11, "DisablingASPNETAccount", 0, "Disabling ASPNET account and removing ACLs", 0);
    RegisterAspNetMMC(0);
    SetAspNetMMCKeys(0);
    v27 = 1;
    goto LABEL_60;
  }
  UninstallPerfCounters(L"ASP.NET_4.0.30319", v30, 1);
  UninstallMOF();
  InstallInfSections(g_DllInstance, 1, L"XSP.UninstallPerVer", 0);
  if ( (unsigned int)IsVista() )
  {
    CRegInfo::CRegInfo((CRegInfo *)v36);
    inited = CRegInfo::InitHighestInfo((CRegInfo *)v36, 0);
    v27 = inited != 0;
    if ( inited )
      InstallV2MOF();
    CRegInfo::~CRegInfo((CRegInfo *)v36);
  }
  else
  {
    CRegInfo::IsAllVerDeleted(&v27);
  }
  if ( v27 )
  {
    CSetupLogging::Log(1, "DisablingASPNETAccount", 0, "Disabling ASPNET account and removing ACLs", 0);
    v13 = CRegAccount::UndoReg(0, v27);
    CSetupLogging::Log(v13, "DisablingASPNETAccount", 0, "Disabling ASPNET account and removing ACLs", 0);
  }
  if ( v10 )
  {
    if ( v27 )
      goto LABEL_60;
    CRegInfo::CRegInfo((CRegInfo *)v36);
    CSetupLogging::Log(1, "GetPreviousVersion", 0, "Getting previously installed ASP.NET isapi information", 0);
    v14 = CRegInfo::InitHighestInfo((CRegInfo *)v36, 0);
    v15 = v14;
    if ( (_WORD)v14 == 1168 )
      v14 = 0;
    CSetupLogging::Log(
      v14,
      "Getting previously installed ASP.NET isapi information",
      0,
      "Getting previously installed ASP.NET isapi information",
      0);
    if ( !v15 )
    {
      CSetupLogging::Log(1, "LoadIsapi", 0, "Loading previously installed ASP.NET isapi", 0);
      Library = LoadLibraryExW(lpLibFileName, 0, 8u);
      CSetupLogging::Log(0, "LoadIsapi", 0, "Loading previously installed ASP.NET isapi", 0);
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "InstallServices");
        if ( ProcAddress )
        {
          CSetupLogging::Log(1, "InstallServices", 0, "Installing previously installed ASP.NET services", 0);
          v20 = ProcAddress();
          CSetupLogging::Log(v20, "InstallServices", 0, "Installing previously installed ASP.NET services", 0);
        }
        else
        {
          GetLastWin32Error();
          v18 = GetProcAddress(Library, "InstallStateService");
          if ( v18 )
          {
            v35 &= 0xF8u;
            v34[0] = &CStateServerRegInfo::`vftable';
            CStateServerRegInfo::Read((CStateServerRegInfo *)v34);
            CSetupLogging::Log(1, "InstallStateService", 0, "Installing previously installed ASP.NET state service", 0);
            v19 = v18();
            CSetupLogging::Log(
              v19,
              "InstallStateService",
              0,
              "Installing previously installed ASP.NET state service",
              0);
            CStateServerRegInfo::Set((CStateServerRegInfo *)v34);
          }
          else
          {
            GetLastWin32Error();
          }
        }
        v21 = GetProcAddress(Library, "InstallMOF");
        if ( v21 )
        {
          CSetupLogging::Log(1, "InstallMOF", 0, "Installing previous ASP.NET MOF file", 0);
          v22 = v21();
          CSetupLogging::Log(v22, "InstallMOF", 0, "Installing previous ASP.NET MOF file", 0);
        }
        else
        {
          FileName[0] = 0;
          IsVerInstalled = StringCchCatW(FileName, 0x208u, v38);
          if ( IsVerInstalled
            || (IsVerInstalled = StringCchCatW(FileName, 0x208u, L"\\")) != 0
            || (IsVerInstalled = StringCchCatW(FileName, 0x208u, L"aspnet.mof")) != 0 )
          {
            CRegInfo::~CRegInfo((CRegInfo *)v36);
            goto LABEL_85;
          }
          FileW = CreateFileW(FileName, 0x80u, 1u, 0, 3u, 0, 0);
          if ( FileW != (HANDLE)-1LL )
          {
            CloseHandle(FileW);
            LaunchMofComp(1, FileName);
          }
        }
        if ( !(unsigned int)IsWow64() )
        {
          v24 = (unsigned int (*)(void))GetProcAddress(Library, "InstallMMCComComponents");
          if ( v24 )
          {
            if ( !v24() )
              v5 = 1;
          }
          else
          {
            GetLastWin32Error();
            ASPNETVER::ASPNETVER((ASPNETVER *)v34);
            if ( !(unsigned int)CRegInfo::GetHighestVersion((struct ASPNETVER *)v34)
              && (unsigned int)(LODWORD(v34[0]) - 2) <= 1 )
            {
              v5 = MakeMMCPointToV2() == 0;
            }
          }
        }
        FreeLibrary(Library);
      }
      else
      {
        GetLastWin32Error();
      }
    }
    CRegInfo::~CRegInfo((CRegInfo *)v36);
  }
  if ( v27 )
  {
LABEL_60:
    UninstallAllPerfCounters();
    CRegInfo::RemoveRelatedKeys(0);
    InstallInfSections(g_DllInstance, 1, L"StateService.Uninstall", 0);
    if ( !(unsigned int)IsVista() )
      InstallInfSections(g_DllInstance, 1, L"XSP.UninstallAllVer", 0);
  }
  if ( v10 && !(unsigned int)IsWow64() && !v5 )
    InstallInfSections(g_DllInstance, 1, L"MmcAspNetExtCOMComponents.Uninstall", 1);
  if ( v28 != 4 )
    goto LABEL_70;
  v25 = 0;
  if ( v27 )
    v25 = 4;
  IsVerInstalled = RemoveScriptFilesAndIISKeyForVersions(
                     WEBSITE_INFO::WszPathAllWebSites,
                     (struct CASPNET_VER_LIST *)v33,
                     v25);
  if ( !IsVerInstalled )
  {
LABEL_70:
    if ( !v27 )
      StartServiceByName(L"aspnet_state", v29);
    if ( !(unsigned int)IsVista() && a2 && v28 == 4 )
      RestartW3svc(v31, v32);
    CleanupTempDir((struct CASPNET_VER_LIST *)v33);
    CleanupBrowserCaps();
    if ( a1 == 2 && (unsigned int)RunningOn64Bit() )
      UnregisterOppositeBitnessIfPresent(a2);
    if ( v4 )
    {
      CallV2AndV11AspNetRegIISUnintall();
      if ( (unsigned int)RunningOn64Bit() )
        UnregisterOppositeBitnessIfPresent(a2);
    }
    IsVerInstalled = 0;
    if ( !(unsigned int)IsVista() && v28 != 4 )
      XspLogEvent(0x80000406);
  }
LABEL_85:
  XspLogEvent(0x40000405u);
  CSetupLogging::Close();
  CASPNET_VER_LIST::~CASPNET_VER_LIST((CASPNET_VER_LIST *)v33);
  return IsVerInstalled;
}

```

## disassembly

```asm
0x18003ef38  mov     [rsp-8+arg_10], rbx
0x18003ef3d  push    rbp
0x18003ef3e  push    rsi
0x18003ef3f  push    rdi
0x18003ef40  push    r12
0x18003ef42  push    r13
0x18003ef44  push    r14
0x18003ef46  push    r15
0x18003ef48  lea     rbp, [rsp-440h]
0x18003ef50  sub     rsp, 540h
0x18003ef57  mov     rax, cs:__security_cookie
0x18003ef5e  xor     rax, rsp
0x18003ef61  mov     [rbp+470h+var_40], rax
0x18003ef68  mov     edi, ecx
0x18003ef6a  xor     esi, esi
0x18003ef6c  lea     rcx, [rsp+570h+var_518]; this
0x18003ef71  mov     [rsp+570h+var_530], esi
0x18003ef75  mov     [rsp+570h+var_52C], esi
0x18003ef79  mov     r15d, edx
0x18003ef7c  call    ??0CASPNET_VER_LIST@@QEAA@XZ; CASPNET_VER_LIST::CASPNET_VER_LIST(void)
0x18003ef81  lea     r8, a40303190; "4.0.30319.0"
0x18003ef88  mov     [rsp+570h+var_524], esi
0x18003ef8c  lea     rdx, aS; "%s"
0x18003ef93  mov     ecx, 40000403h; dwEventID
0x18003ef98  mov     r13d, esi
0x18003ef9b  mov     r12d, esi
0x18003ef9e  call    XspLogEvent
0x18003efa3  lea     r14d, [rsi+1]
0x18003efa7  mov     edx, edi
0x18003efa9  mov     ecx, r14d
0x18003efac  call    ?Init@CSetupLogging@@SAXW4REGIIS_ACTION@@K@Z; CSetupLogging::Init(REGIIS_ACTION,ulong)
0x18003efb1  call    ?IsVista@@YAHXZ; IsVista(void)
0x18003efb6  test    eax, eax
0x18003efb8  jz      short loc_18003EFCE
0x18003efba  call    ?IIS7UnRegister@@YAJXZ; IIS7UnRegister(void)
0x18003efbf  mov     ecx, [rsp+570h+var_52C]
0x18003efc3  cmp     eax, r14d
0x18003efc6  cmovz   ecx, r14d
0x18003efca  mov     [rsp+570h+var_52C], ecx
0x18003efce  lea     rdx, [rsp+570h+var_528]; int *
0x18003efd3  cmp     edi, 2
0x18003efd6  jnz     loc_18003F0D5
0x18003efdc  mov     ecx, r15d; int
0x18003efdf  call    ?UninstallAllUsingHighest@@YAJHPEAH@Z; UninstallAllUsingHighest(int,int *)
0x18003efe4  mov     ebx, eax
0x18003efe6  test    eax, eax
0x18003efe8  jnz     loc_18003F71B
0x18003efee  cmp     [rsp+570h+var_528], esi
0x18003eff2  jnz     loc_18003F71B
0x18003eff8  call    ?IsVista@@YAHXZ; IsVista(void)
0x18003effd  mov     ebx, r14d
0x18003f000  test    eax, eax
0x18003f002  jz      short loc_18003F00E
0x18003f004  cmp     edi, 2
0x18003f007  jnz     short loc_18003F00E
0x18003f009  mov     r13d, ebx
0x18003f00c  mov     edi, ebx
0x18003f00e  lea     rdx, [rsp+570h+var_520]; int *
0x18003f013  lea     rcx, [rsp+570h+var_524]; int *
0x18003f018  call    ?IsCurrentHighest@@YAJPEAH0@Z; IsCurrentHighest(int *,int *)
0x18003f01d  call    ?IsVista@@YAHXZ; IsVista(void)
0x18003f022  test    eax, eax
0x18003f024  jnz     short loc_18003F052
0x18003f026  lea     rdx, aIisadmin; "iisadmin"
0x18003f02d  lea     rcx, [rsp+570h+var_51C]; unsigned int *
0x18003f032  call    ?GetServiceStatus@@YAJPEAKPEBG@Z; GetServiceStatus(ulong *,ushort const *)
0x18003f037  lea     rcx, [rsp+570h+var_52C]; unsigned int *
0x18003f03c  call    ?CheckIISState@@YAJPEAK@Z; CheckIISState(ulong *)
0x18003f041  lea     rdx, ServiceName; "w3svc"
0x18003f048  lea     rcx, [rsp+570h+var_520]; unsigned int *
0x18003f04d  call    ?GetServiceStatus@@YAJPEAKPEBG@Z; GetServiceStatus(ulong *,ushort const *)
0x18003f052  xor     r8d, r8d; int *
0x18003f055  lea     rdx, aAspnetState_0; "aspnet_state"
0x18003f05c  lea     rcx, [rsp+570h+var_528]; unsigned int *
0x18003f061  call    ?StopServiceByName@@YAJPEAKPEBGPEAH@Z; StopServiceByName(ulong *,ushort const *,int *)
0x18003f066  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18003f06d  lea     r8, aAdminserviceUn; "AdminService.Uninstall"
0x18003f074  xor     r9d, r9d
0x18003f077  mov     dl, bl
0x18003f079  call    InstallInfSections
0x18003f07e  mov     ecx, ebx; unsigned int
0x18003f080  call    ?RegCleanup@CRegInfo@@SAJK@Z; CRegInfo::RegCleanup(ulong)
0x18003f085  cmp     [rsp+570h+var_52C], 4
0x18003f08a  jnz     short loc_18003F099
0x18003f08c  cmp     edi, 2
0x18003f08f  mov     ecx, esi
0x18003f091  setz    cl; int
0x18003f094  call    ?UnregisterIIS@@YAJH@Z; UnregisterIIS(int)
0x18003f099  cmp     edi, 2
0x18003f09c  jnz     loc_18003F135
0x18003f0a2  lea     rcx, [rbp+470h+var_4F0]; this
0x18003f0a6  call    ??0CRegInfo@@QEAA@XZ; CRegInfo::CRegInfo(void)
0x18003f0ab  call    ?IsVista@@YAHXZ; IsVista(void)
0x18003f0b0  xor     r9d, r9d; unsigned int
0x18003f0b3  mov     [rsp+570h+dwCreationDisposition], eax; int
0x18003f0b7  lea     r8, [rsp+570h+var_518]; struct CASPNET_VER_LIST *
0x18003f0bc  xor     edx, edx; struct ASPNETVER *
0x18003f0be  lea     rcx, [rbp+470h+var_4F0]; this
0x18003f0c2  call    ?GetVerInfoList@CRegInfo@@QEAAJPEAVASPNETVER@@PEAVCASPNET_VER_LIST@@KH@Z; CRegInfo::GetVerInfoList(ASPNETVER *,CASPNET_VER_LIST *,ulong,int)
0x18003f0c7  lea     rcx, [rbp+470h+var_4F0]; this
0x18003f0cb  call    ??1CRegInfo@@QEAA@XZ; CRegInfo::~CRegInfo(void)
0x18003f0d0  jmp     loc_18003F15C
0x18003f0d5  lea     rcx, ?m_gThisVer@ASPNETVER@@0V1@A; struct ASPNETVER *
0x18003f0dc  call    ?IsVerInstalled@CRegInfo@@SAJPEAVASPNETVER@@PEAH@Z; CRegInfo::IsVerInstalled(ASPNETVER *,int *)
0x18003f0e1  mov     ebx, eax
0x18003f0e3  test    eax, eax
0x18003f0e5  jnz     loc_18003F71B
0x18003f0eb  cmp     [rsp+570h+var_528], esi
0x18003f0ef  jnz     loc_18003EFF8
0x18003f0f5  lea     r9, aExitBecauseThe; "Exit because the current version is not"...
0x18003f0fc  mov     qword ptr [rsp+570h+dwCreationDisposition], rsi; unsigned __int16 *
0x18003f101  xor     r8d, r8d; unsigned int
0x18003f104  lea     rdx, aUnregister_0; "Unregister"
0x18003f10b  mov     ecx, r14d; int
0x18003f10e  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f113  lea     r9, aExitBecauseThe; "Exit because the current version is not"...
0x18003f11a  mov     qword ptr [rsp+570h+dwCreationDisposition], rsi; unsigned __int16 *
0x18003f11f  xor     r8d, r8d; unsigned int
0x18003f122  lea     rdx, aUnregister_0; "Unregister"
0x18003f129  xor     ecx, ecx; int
0x18003f12b  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f130  jmp     loc_18003F71B
0x18003f135  lea     rax, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x18003f13c  xor     r8d, r8d; unsigned int
0x18003f13f  lea     r9, ?s_wszIsapiFullPath@Names@@0PAGA; unsigned __int16 *
0x18003f146  mov     qword ptr [rsp+570h+dwCreationDisposition], rax; unsigned __int16 *
0x18003f14b  lea     rdx, a40303190; "4.0.30319.0"
0x18003f152  lea     rcx, [rsp+570h+var_518]; this
0x18003f157  call    ?Add@CASPNET_VER_LIST@@QEAAJPEBGK00@Z; CASPNET_VER_LIST::Add(ushort const *,ulong,ushort const *,ushort const *)
0x18003f15c  xor     ecx, ecx; int
0x18003f15e  call    ?RegisterSystemWebAssembly@@YAJH@Z; RegisterSystemWebAssembly(int)
0x18003f163  xor     ecx, ecx; int
0x18003f165  call    ?SetDCOMKeys@@YAJH@Z; SetDCOMKeys(int)
0x18003f16a  mov     r14d, [rsp+570h+var_524]
0x18003f16f  cmp     edi, 2
0x18003f172  jnz     short loc_18003F1CE
0x18003f174  lea     r9, aDisablingAspne; "Disabling ASPNET account and removing A"...
0x18003f17b  mov     qword ptr [rsp+570h+dwCreationDisposition], rsi; unsigned __int16 *
0x18003f180  xor     r8d, r8d; unsigned int
0x18003f183  lea     rdx, aDisablingaspne; "DisablingASPNETAccount"
0x18003f18a  mov     ecx, ebx; int
0x18003f18c  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f191  mov     edx, ebx; int
0x18003f193  mov     ecx, ebx; int
0x18003f195  call    ?UndoReg@CRegAccount@@SAJHH@Z; CRegAccount::UndoReg(int,int)
0x18003f19a  lea     r9, aDisablingAspne; "Disabling ASPNET account and removing A"...
0x18003f1a1  mov     qword ptr [rsp+570h+dwCreationDisposition], rsi; unsigned __int16 *
0x18003f1a6  xor     r8d, r8d; unsigned int
0x18003f1a9  lea     rdx, aDisablingaspne; "DisablingASPNETAccount"
0x18003f1b0  mov     ecx, eax; int
0x18003f1b2  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f1b7  xor     ecx, ecx; int
0x18003f1b9  call    ?RegisterAspNetMMC@@YAJH@Z; RegisterAspNetMMC(int)
0x18003f1be  xor     ecx, ecx; int
0x18003f1c0  call    ?SetAspNetMMCKeys@@YAJH@Z; SetAspNetMMCKeys(int)
0x18003f1c5  mov     [rsp+570h+var_530], ebx
0x18003f1c9  jmp     loc_18003F5E2
0x18003f1ce  mov     r8d, ebx; int
0x18003f1d1  lea     rcx, aAspNet4030319; "ASP.NET_4.0.30319"
0x18003f1d8  mov     edx, r14d; int
0x18003f1db  call    ?UninstallPerfCounters@@YAJPEBGHH@Z; UninstallPerfCounters(ushort const *,int,int)
0x18003f1e0  call    ?UninstallMOF@@YAJXZ; UninstallMOF(void)
0x18003f1e5  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18003f1ec  lea     r8, aXspUninstallpe; "XSP.UninstallPerVer"
0x18003f1f3  xor     r9d, r9d
0x18003f1f6  mov     dl, bl
0x18003f1f8  call    InstallInfSections
0x18003f1fd  call    ?IsVista@@YAHXZ; IsVista(void)
0x18003f202  test    eax, eax
0x18003f204  jnz     short loc_18003F212
0x18003f206  lea     rcx, [rsp+570h+var_530]; int *
0x18003f20b  call    ?IsAllVerDeleted@CRegInfo@@SAJPEAH@Z; CRegInfo::IsAllVerDeleted(int *)
0x18003f210  jmp     short loc_18003F243
0x18003f212  lea     rcx, [rbp+470h+var_4F0]; this
0x18003f216  call    ??0CRegInfo@@QEAA@XZ; CRegInfo::CRegInfo(void)
0x18003f21b  xor     edx, edx; struct ASPNETVER *
0x18003f21d  lea     rcx, [rbp+470h+var_4F0]; this
0x18003f221  call    ?InitHighestInfo@CRegInfo@@QEAAJPEAVASPNETVER@@@Z; CRegInfo::InitHighestInfo(ASPNETVER *)
0x18003f226  test    eax, eax
0x18003f228  mov     ecx, esi
0x18003f22a  setnz   cl
0x18003f22d  mov     [rsp+570h+var_530], ecx
0x18003f231  test    eax, eax
0x18003f233  jz      short loc_18003F23A
0x18003f235  call    ?InstallV2MOF@@YAJXZ; InstallV2MOF(void)
0x18003f23a  lea     rcx, [rbp+470h+var_4F0]; this
0x18003f23e  call    ??1CRegInfo@@QEAA@XZ; CRegInfo::~CRegInfo(void)
0x18003f243  cmp     [rsp+570h+var_530], esi
0x18003f247  jz      short loc_18003F28E
0x18003f249  lea     r9, aDisablingAspne; "Disabling ASPNET account and removing A"...
0x18003f250  mov     qword ptr [rsp+570h+dwCreationDisposition], rsi; unsigned __int16 *
0x18003f255  xor     r8d, r8d; unsigned int
0x18003f258  lea     rdx, aDisablingaspne; "DisablingASPNETAccount"
0x18003f25f  mov     ecx, ebx; int
0x18003f261  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f266  mov     edx, [rsp+570h+var_530]; int
0x18003f26a  xor     ecx, ecx; int
0x18003f26c  call    ?UndoReg@CRegAccount@@SAJHH@Z; CRegAccount::UndoReg(int,int)
0x18003f271  lea     r9, aDisablingAspne; "Disabling ASPNET account and removing A"...
0x18003f278  mov     qword ptr [rsp+570h+dwCreationDisposition], rsi; unsigned __int16 *
0x18003f27d  xor     r8d, r8d; unsigned int
0x18003f280  lea     rdx, aDisablingaspne; "DisablingASPNETAccount"
0x18003f287  mov     ecx, eax; int
0x18003f289  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f28e  test    r14d, r14d
0x18003f291  jz      loc_18003F5DC
0x18003f297  cmp     [rsp+570h+var_530], esi
0x18003f29b  jnz     loc_18003F5E2
0x18003f2a1  lea     rcx, [rbp+470h+var_4F0]; this
0x18003f2a5  call    ??0CRegInfo@@QEAA@XZ; CRegInfo::CRegInfo(void)
0x18003f2aa  mov     qword ptr [rsp+570h+dwCreationDisposition], rsi; unsigned __int16 *
0x18003f2af  lea     rdx, aGetpreviousver; "GetPreviousVersion"
0x18003f2b6  lea     rsi, aGettingPreviou; "Getting previously installed ASP.NET is"...
0x18003f2bd  xor     r8d, r8d; unsigned int
0x18003f2c0  mov     r9, rsi; char *
0x18003f2c3  mov     ecx, ebx; int
0x18003f2c5  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f2ca  xor     edx, edx; struct ASPNETVER *
0x18003f2cc  lea     rcx, [rbp+470h+var_4F0]; this
0x18003f2d0  call    ?InitHighestInfo@CRegInfo@@QEAAJPEAVASPNETVER@@@Z; CRegInfo::InitHighestInfo(ASPNETVER *)
0x18003f2d5  mov     ecx, eax
0x18003f2d7  cmp     ax, 490h
0x18003f2db  mov     ebx, eax
0x18003f2dd  mov     r9, rsi; char *
0x18003f2e0  mov     rax, r12
0x18003f2e3  mov     rdx, rsi; char *
0x18003f2e6  cmovz   ecx, eax; int
0x18003f2e9  mov     qword ptr [rsp+570h+dwCreationDisposition], rax; unsigned __int16 *
0x18003f2ee  xor     r8d, r8d; unsigned int
0x18003f2f1  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f2f6  xor     esi, esi
0x18003f2f8  test    ebx, ebx
0x18003f2fa  jnz     loc_18003F5CE
0x18003f300  lea     r9, aLoadingPreviou_0; "Loading previously installed ASP.NET is"...
0x18003f307  mov     qword ptr [rsp+570h+dwCreationDisposition], rsi; unsigned __int16 *
0x18003f30c  xor     r8d, r8d; unsigned int
0x18003f30f  lea     rdx, aLoadisapi; "LoadIsapi"
0x18003f316  lea     ecx, [rsi+1]; int
0x18003f319  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f31e  mov     rcx, [rbp+470h+lpLibFileName]; lpLibFileName
0x18003f322  lea     r8d, [rsi+8]; dwFlags
0x18003f326  xor     edx, edx; hFile
0x18003f328  call    cs:__imp_LoadLibraryExW
0x18003f32e  xor     ebx, ebx
0x18003f330  lea     r9, aLoadingPreviou_0; "Loading previously installed ASP.NET is"...
0x18003f337  xor     r8d, r8d; unsigned int
0x18003f33a  mov     qword ptr [rsp+570h+dwCreationDisposition], rbx; unsigned __int16 *
0x18003f33f  lea     rdx, aLoadisapi; "LoadIsapi"
0x18003f346  xor     ecx, ecx; int
0x18003f348  mov     rsi, rax
0x18003f34b  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f350  test    rsi, rsi
0x18003f353  jnz     short loc_18003F35F
0x18003f355  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003f35a  jmp     loc_18003F5CC
0x18003f35f  lea     rdx, aInstallservice_1; "InstallServices"
0x18003f366  mov     rcx, rsi; hModule
0x18003f369  call    cs:__imp_GetProcAddress
0x18003f36f  mov     rbx, rax
0x18003f372  xor     eax, eax
0x18003f374  test    rbx, rbx
0x18003f377  jnz     loc_18003F410
0x18003f37d  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003f382  lea     rdx, aInstallstatese; "InstallStateService"
0x18003f389  mov     rcx, rsi; hModule
0x18003f38c  call    cs:__imp_GetProcAddress
0x18003f392  mov     rbx, rax
0x18003f395  test    rax, rax
0x18003f398  jnz     short loc_18003F3A4
0x18003f39a  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003f39f  jmp     loc_18003F455
0x18003f3a4  and     [rsp+570h+var_4F4], 0F8h
0x18003f3a9  lea     rax, ??_7CStateServerRegInfo@@6B@; const CStateServerRegInfo::`vftable'
0x18003f3b0  lea     rcx, [rsp+570h+var_508]; this
0x18003f3b5  mov     [rsp+570h+var_508], rax
0x18003f3ba  call    ?Read@CStateServerRegInfo@@UEAAXXZ; CStateServerRegInfo::Read(void)
0x18003f3bf  and     qword ptr [rsp+570h+dwCreationDisposition], r12
0x18003f3c4  lea     r9, aInstallingPrev_1; "Installing previously installed ASP.NET"...
0x18003f3cb  xor     r8d, r8d; unsigned int
0x18003f3ce  lea     rdx, aInstallstatese; "InstallStateService"
0x18003f3d5  lea     ecx, [r8+1]; int
0x18003f3d9  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f3de  mov     rax, rbx
0x18003f3e1  call    cs:__guard_dispatch_icall_fptr
0x18003f3e7  and     qword ptr [rsp+570h+dwCreationDisposition], r12
0x18003f3ec  lea     r9, aInstallingPrev_1; "Installing previously installed ASP.NET"...
0x18003f3f3  mov     ecx, eax; int
0x18003f3f5  lea     rdx, aInstallstatese; "InstallStateService"
0x18003f3fc  xor     r8d, r8d; unsigned int
0x18003f3ff  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f404  lea     rcx, [rsp+570h+var_508]; this
0x18003f409  call    ?Set@CStateServerRegInfo@@UEAAXXZ; CStateServerRegInfo::Set(void)
0x18003f40e  jmp     short loc_18003F455
0x18003f410  xor     r8d, r8d; unsigned int
0x18003f413  mov     qword ptr [rsp+570h+dwCreationDisposition], rax; unsigned __int16 *
0x18003f418  lea     r9, aInstallingPrev; "Installing previously installed ASP.NET"...
0x18003f41f  lea     rdx, aInstallservice_1; "InstallServices"
0x18003f426  lea     ecx, [r8+1]; int
0x18003f42a  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003f42f  mov     rax, rbx
  ... truncated ...
```
