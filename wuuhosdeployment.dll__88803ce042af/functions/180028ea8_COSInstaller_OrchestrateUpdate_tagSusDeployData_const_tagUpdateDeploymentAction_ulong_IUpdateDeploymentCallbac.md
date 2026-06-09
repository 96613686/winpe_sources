# COSInstaller::OrchestrateUpdate(tagSusDeployData const &,tagUpdateDeploymentAction,ulong,IUpdateDeploymentCallback *,int *,tagAutoCommitStatus *,wchar_t * *,wchar_t * *,wchar_t const *)

- ea: `0x180028ea8`
- end: `0x180029f01`
- name: `?OrchestrateUpdate@COSInstaller@@AEAAJAEBUtagSusDeployData@@W4tagUpdateDeploymentAction@@KPEAUIUpdateDeploymentCallback@@PEAHPEAW4tagAutoCommitStatus@@PEAPEA_W5PEB_W@Z`
- size: `4185`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, _DWORD *, __int64, __int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800276d0`
- `0x180027d78`
- `0x180028268`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000a448`
- `0x18000a4f4`
- `0x18000b370`
- `0x18000b658`
- `0x18000c0b4`
- `0x18000fcfc`
- `0x180010f54`
- `0x180018f18`
- `0x180019330`
- `0x18001952c`
- `0x18001981c`
- `0x180019cc4`
- `0x180019e00`
- `0x18001a8b8`
- `0x18001d604`
- `0x180023548`
- `0x180026964`
- `0x180028ea8`
- `0x18002d530`
- `0x18002d8d0`
- `0x18002d95c`
- `0x180042630`
- `0x180042a24`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002972b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029dee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002972b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029dee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800295d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800295d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029216`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002925c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180029266`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002925c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180029266`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180029270`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180029270`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029e25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029e25`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029256`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e9d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029818`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029818`
- `RPCRT4!UuidFromStringW` at `0x180029089`
- `RPCRT4!UuidFromStringW` at `0x180029089`
- `OLEAUT32!__imp_SysStringLen` at `0x1800291b7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800291b7`

## string_xrefs

- `0x180029204`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x180029abf`: `WillUpdateAutoCommit`
- `0x180029ad4`: `WillUpdateAutoCommit`
- `0x18002997d`: `UpdatePriority`
- `0x18002915c`: `Install`
- `0x180029153`: `Commit`
- `0x18002909d`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800291d4`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180029438`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800294cd`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002959b`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800296f4`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002982a`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800298be`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180029d07`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180029dc5`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180029172`: `Preparing to %ws update ID: %ws.%d`
- `0x1800290ea`: `Skipping UUP on Prem language specific update ID: %ws`
- `0x18002940a`: `ParseHandlerXml`
- `0x1800299e2`: `Update agent does not support priority set capability`
- `0x180029b49`: `Update agent does not support autocommit query capability`
- `0x180029c14`: `Need to install the baseline update`
- `0x180029bde`: `Install failed for update ID: %ws.%d Error Info type is %lu`
- `0x180029d34`: `Invalid update operation`
- `0x180028fbe`: `OptionalSessionFlags for Commit to be passed to Update Agent = %lu`
- `0x180028f7f`: `OptionalSessionFlags for Install to be passed to Update Agent = %lu`
- `0x1800291fd`: `BreakOnHandlerInstallCall`

## pseudocode

```c
__int64 __fastcall COSInstaller::OrchestrateUpdate(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  char v10; // si
  wchar_t *v12; // r13
  unsigned int v13; // ebx
  __int64 v14; // r12
  int v15; // edi
  int v16; // eax
  void *v17; // rbx
  wchar_t *v18; // rsi
  __int64 v19; // rdi
  __int64 v20; // r14
  unsigned __int16 *v21; // rcx
  unsigned int v22; // eax
  const struct std::nothrow_t *v23; // rdx
  int FilesPerPatchType; // r15d
  OSDeploymentHelper *v25; // rax
  bool v26; // cl
  __int64 v27; // rcx
  int v28; // ebx
  __int64 v30; // r13
  struct tagDSUpdateMetadata *v31; // rbx
  wchar_t **v32; // r8
  int *v33; // r9
  __int64 v34; // rdx
  unsigned int v35; // eax
  char IsEnabled; // al
  unsigned int v37; // r9d
  __int64 v38; // rdx
  const wchar_t *v39; // rax
  int v40; // eax
  int v41; // eax
  __int64 (__fastcall *v42)(__int64, LPVOID *); // rbx
  int v43; // eax
  unsigned __int64 v44; // r9
  __int64 v45; // rdx
  struct tagDSUpdateMetadata *v46; // rbx
  HRESULT updated; // eax
  __int64 v48; // rdx
  int v49; // eax
  int v50; // eax
  __int64 v51; // rbx
  int v52; // eax
  int v53; // eax
  int v54; // edx
  int v55; // eax
  __int64 (__fastcall *v56)(__int64, __int64 *, _DWORD *); // rbx
  int v57; // eax
  int v58; // eax
  __int64 v59; // rcx
  int v60; // eax
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvc; // [rsp+20h] [rbp-E0h]
  const wchar_t *v66; // [rsp+28h] [rbp-D8h]
  unsigned int *v67; // [rsp+30h] [rbp-D0h]
  int v68; // [rsp+38h] [rbp-C8h]
  __int64 v69; // [rsp+38h] [rbp-C8h]
  bool v70; // [rsp+50h] [rbp-B0h]
  char v71; // [rsp+51h] [rbp-AFh] BYREF
  struct tagDSFile **v72; // [rsp+54h] [rbp-ACh] BYREF
  int v73; // [rsp+5Ch] [rbp-A4h]
  struct tagDSUpdateMetadata *v74; // [rsp+60h] [rbp-A0h]
  int v75; // [rsp+68h] [rbp-98h]
  _QWORD *v76; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v77; // [rsp+78h] [rbp-88h] BYREF
  __int64 v78; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v79; // [rsp+88h] [rbp-78h] BYREF
  void *v80; // [rsp+90h] [rbp-70h] BYREF
  __int64 v81; // [rsp+98h] [rbp-68h]
  __int64 v82; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v83; // [rsp+A8h] [rbp-58h]
  wchar_t *v84; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v85; // [rsp+B8h] [rbp-48h] BYREF
  OSDeploymentHelper *v86; // [rsp+C0h] [rbp-40h]
  const wchar_t *v87; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v88[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v89; // [rsp+D8h] [rbp-28h]
  __int64 v90; // [rsp+E0h] [rbp-20h]
  __int128 v91; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v92; // [rsp+F8h] [rbp-8h]
  __int64 v93; // [rsp+100h] [rbp+0h]
  __int64 v94; // [rsp+108h] [rbp+8h]
  __int64 v95; // [rsp+110h] [rbp+10h] BYREF
  GUID v96; // [rsp+118h] [rbp+18h]
  __int64 v97; // [rsp+128h] [rbp+28h]
  _QWORD v98[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v99[2]; // [rsp+150h] [rbp+50h] BYREF
  char v100; // [rsp+160h] [rbp+60h]
  IID rclsid; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v102[14]; // [rsp+180h] [rbp+80h] BYREF
  struct tagDSGlobalUpdateId *v103; // [rsp+1F0h] [rbp+F0h] BYREF
  int v104; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v105; // [rsp+200h] [rbp+100h] BYREF
  LPVOID v106; // [rsp+208h] [rbp+108h] BYREF
  LPVOID pv; // [rsp+210h] [rbp+110h] BYREF
  OSDeploymentHelper *v108; // [rsp+218h] [rbp+118h] BYREF
  HANDLE hObject; // [rsp+220h] [rbp+120h] BYREF
  __int128 v110; // [rsp+228h] [rbp+128h] BYREF
  UUID Uuid; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v112[112]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v10 = a3;
  v75 = a3;
  v81 = a1;
  LODWORD(v105) = a4;
  *(_QWORD *)&rclsid.Data1 = a5;
  v83 = a6;
  *(_QWORD *)&v110 = a7;
  v93 = a8;
  v94 = a9;
  v76 = a10;
  v74 = *(struct tagDSUpdateMetadata **)(a2 + 56);
  v103 = (struct tagDSGlobalUpdateId *)(a2 + 32);
  v12 = *(wchar_t **)(a2 + 16);
  v84 = v12;
  v108 = *(OSDeploymentHelper **)(a2 + 24);
  v13 = *(_DWORD *)(a2 + 80);
  v14 = 0;
  v15 = 0;
  v73 = 0;
  if ( (a3 & 1) != 0 )
  {
    v15 = (v13 >> 6) & 4;
    v73 = v15;
    ppv = 0;
    WUTrace(0, 0, 4096, 4);
  }
  if ( (v10 & 2) != 0 )
  {
    v16 = v15 | 1;
    if ( (v13 & 0x200) == 0 )
      v16 = v15;
    v73 = v16;
    ppv = 0;
    WUTrace(0, 0, 4096, 4);
  }
  *(_QWORD *)&v91 = *(_QWORD *)(a2 + 256);
  v89 = *(_QWORD *)(a2 + 104);
  v90 = *(_QWORD *)(a2 + 248);
  v85 = (wchar_t *)(a2 + 112);
  v87 = (const wchar_t *)a10;
  v79 = 0;
  v80 = 0;
  v72 = 0;
  v17 = 0;
  *(_QWORD *)v88 = 0;
  Uuid = 0;
  v18 = 0;
  v77 = 0;
  pv = 0;
  v19 = 0;
  v78 = 0;
  v20 = 0;
  v82 = 0;
  v106 = 0;
  v92 = 0;
  Trace::UpdateIdToString::UpdateIdToString(
    (Trace::UpdateIdToString *)v112,
    (struct tagDSUpdateMetadata *)((char *)v74 + 4));
  hObject = 0;
  v21 = *(unsigned __int16 **)a2;
  if ( *(_QWORD *)a2 )
  {
    if ( *v21 )
    {
      v22 = UuidFromStringW(v21, &Uuid);
      if ( v22 )
      {
        FilesPerPatchType = wil::details::in1diag3::Return_Win32(
                              retaddr,
                              (void *)0x37A,
                              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
                              (const char *)v22,
                              ppv);
        goto LABEL_152;
      }
    }
  }
  if ( IsUUPOnPremLangSpecificChildUpdate(v74, v103, &Uuid) )
  {
    Trace::UpdateIdToString::UpdateIdToString(
      (Trace::UpdateIdToString *)v102,
      (struct tagDSUpdateMetadata *)((char *)v74 + 4));
    WUTrace(0, 0, 4096, 4);
    FilesPerPatchType = 0;
    goto LABEL_152;
  }
  v68 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v102, (const struct _GUID *)((char *)v74 + 4));
  WUTrace(0, 0, 4096, 4);
  v25 = (OSDeploymentHelper *)v12;
  if ( v108 )
    v25 = v108;
  v86 = v25;
  if ( !SysStringLen(v12) )
  {
    FilesPerPatchType = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x394,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)0x80070057LL,
      0);
    goto LABEL_152;
  }
  *v83 = 0;
  if ( (unsigned int)AreTestKeysAllowed(v26) )
  {
    v28 = RegQueryDwordValueWithDefaultAndRangeCheck(
            v27,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            L"BreakOnHandlerInstallCall",
            0);
    if ( v28 )
    {
      v68 = v28;
      GetCurrentProcessId();
      WUTrace(0, 0, 4096, 3);
      while ( !IsDebuggerPresent() )
      {
        if ( !v28-- )
          break;
        Sleep(0x3E8u);
      }
      if ( IsDebuggerPresent() )
        DebugBreak();
    }
  }
  v98[3] = 1;
  v98[0] = &v106;
  v98[1] = &pv;
  v30 = v81;
  v98[2] = v81;
  v31 = v74;
  FilesPerPatchType = OSDeploymentHelper::GetFilesPerPatchType(
                        (OSDeploymentHelper *)*((unsigned int *)v74 + 116),
                        *((_QWORD *)v74 + 59),
                        (struct tagDSFile *const)&v79,
                        (const struct tagDSFile **)((char *)&v72 + 4),
                        (unsigned int *)&v80,
                        &v72,
                        v88);
  if ( FilesPerPatchType < 0 )
  {
    ppvb = FilesPerPatchType;
    WUTrace(0, 0, 4096, 2);
    v34 = 954;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)FilesPerPatchType,
      ppvb);
    goto LABEL_151;
  }
  v70 = v79 != 0;
  if ( !v79
    || (v104 = 0,
        FilesPerPatchType = OSDeploymentHelper::EvaluateFileInSandbox(
                              (const wchar_t *)v86,
                              (const wchar_t **)v79,
                              (const struct tagDSFile *)&v104,
                              v33),
        FilesPerPatchType >= 0)
    && (FilesPerPatchType = v104, v104 >= 0) )
  {
    if ( !v108 )
    {
      v35 = 0;
      LODWORD(v72) = 0;
      if ( HIDWORD(v72) )
      {
        while ( 1 )
        {
          v104 = 0;
          FilesPerPatchType = OSDeploymentHelper::EvaluateFileInSandbox(
                                (const wchar_t *)v86,
                                *((const wchar_t ***)v80 + v35),
                                (const struct tagDSFile *)&v104,
                                v33);
          if ( FilesPerPatchType < 0 )
          {
            ppvb = FilesPerPatchType;
            WUTrace(0, 0, 4096, 2);
            v34 = 991;
            goto LABEL_43;
          }
          if ( v104 < 0 )
            break;
          v35 = (_DWORD)v72 + 1;
          LODWORD(v72) = v35;
          if ( v35 >= HIDWORD(v72) )
          {
            v30 = v81;
            v31 = v74;
            goto LABEL_38;
          }
        }
        ppvb = v104;
        WUTrace(0, 0, 4096, 2);
        FilesPerPatchType = v104;
        if ( v104 >= 0 )
          goto LABEL_151;
        v34 = 1001;
        goto LABEL_43;
      }
    }
LABEL_38:
    FilesPerPatchType = OSDeploymentHelper::ParseHandlerXml(
                          (struct tagDSUpdateMetadata *)((char *)v31 + 544),
                          (const struct tagDSDataBlob *)&v77,
                          v32);
    if ( FilesPerPatchType < 0 )
    {
      WUTrace(0, 0, 4096, 2);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F3,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)FilesPerPatchType,
        FilesPerPatchType);
LABEL_46:
      v18 = v77;
      goto LABEL_151;
    }
    if ( *(_BYTE *)(v30 + 56) )
    {
      FilesPerPatchType = -2145116152;
      goto LABEL_46;
    }
    v95 = 0;
    v96 = GUID_NULL;
    v97 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl);
    v18 = v77;
    if ( IsEnabled )
    {
      FilesPerPatchType = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(
                            (struct _GUID *)&v95,
                            (GUID *)((char *)v31 + 4),
                            (void **)0x1B7740);
      if ( FilesPerPatchType < 0 )
      {
        v38 = 1020;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
          (const char *)(unsigned int)FilesPerPatchType,
          ppva);
LABEL_150:
        OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v95);
        goto LABEL_151;
      }
    }
    else
    {
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      FilesPerPatchType = OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(
                            (GUID *)((char *)v31 + 4),
                            (const struct _GUID *)&hObject,
                            (void **)0x1B7740,
                            v37);
      if ( FilesPerPatchType < 0 )
      {
        v38 = 1027;
        goto LABEL_54;
      }
    }
    v99[0] = &hObject;
    v99[1] = v103;
    v100 = 1;
    v81 = v30 + 64;
    if ( v30 != -64 )
      EnterCriticalSection((LPCRITICAL_SECTION)(v30 + 72));
    if ( *(_QWORD *)(v30 + 112) )
    {
      FilesPerPatchType = -2145124343;
LABEL_147:
      if ( v30 != -64 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v30 + 72));
      goto LABEL_149;
    }
    memset(v102, 0, 0x68u);
    v102[1] = v112;
    v102[2] = v89;
    v102[3] = v90;
    v102[0] = v91;
    v102[6] = v108;
    LODWORD(v102[8]) = v73;
    if ( v85 )
    {
      v39 = (const wchar_t *)v102[4];
      if ( *(_BYTE *)v85 )
        v39 = v85;
      v102[4] = v39;
    }
    if ( !v76 && v70 )
      v87 = (const wchar_t *)*((_QWORD *)v79 + 9);
    v76 = v102;
    v91 = xmmword_180076898;
    v40 = 0;
    if ( !v108 )
      v40 = HIDWORD(v72);
    LODWORD(v72) = v40;
    v85 = v18;
    v41 = Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,IDeploymentSession,wchar_t const * &,wchar_t * const,wchar_t *,unsigned long &,WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>> &,_GUID,unsigned long const &,tagOptionalSessionInfo5 *>(
            (_QWORD *)(v30 + 112),
            &v84,
            &v87,
            (const wchar_t **)&v85,
            (unsigned int *)&v72,
            (struct tagDSFile ***)&v80,
            (__int64)&v91,
            v68,
            (void **)&v76);
    FilesPerPatchType = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)v41,
        (int)ppvc);
      goto LABEL_147;
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v30 + 112) + 8LL))(*(_QWORD *)(v30 + 112));
    v14 = *(_QWORD *)(v30 + 112);
    v92 = v14;
    if ( v30 != -64 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v30 + 72));
    v42 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 24LL);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v43 = v42(v14, &pv);
    FilesPerPatchType = v43;
    if ( v43 < 0 )
    {
      v44 = (unsigned int)v43;
      v45 = 1106;
LABEL_144:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)v44,
        (int)ppvc);
      goto LABEL_149;
    }
    v84 = (wchar_t *)(v30 + 144);
    v76 = (_QWORD *)(v30 + 120);
    v46 = v74;
    updated = Microsoft::WRL::Details::MakeAndInitialize<COSInstallDeploymentProgress,COSInstallDeploymentProgress,tagDSGlobalUpdateId const &,tagDSGlobalUpdateId const &,CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>> *,CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>> *,IUpdateDeploymentCallback * &>(
                (unsigned int)&v78,
                (int)v74 + 4,
                (_DWORD)v103,
                (unsigned int)&v76,
                (__int64)&v84,
                (__int64)&rclsid);
    FilesPerPatchType = updated;
    if ( updated < 0 )
    {
      v48 = 1112;
LABEL_81:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v48,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)updated,
        (int)ppvc);
      v19 = v78;
LABEL_149:
      wil::details::lambda_call__lambda_8442dda86b2b3a16dab6fbc6b475eee9___::_lambda_call__lambda_8442dda86b2b3a16dab6fbc6b475eee9___(v99);
      goto LABEL_150;
    }
    if ( v106 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v106 + 16LL))(v106);
      v106 = 0;
    }
    rclsid = (IID)xmmword_180076898;
    updated = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_c8264914_c0d2_48da_a5cd_f47d74fda7f6, &v106);
    FilesPerPatchType = updated;
    if ( updated < 0 )
    {
      v48 = 1117;
      goto LABEL_81;
    }
    v19 = v78;
    v49 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64))(*(_QWORD *)v106 + 32LL))(v106, pv, v78);
    FilesPerPatchType = v49;
    if ( v49 < 0 )
    {
      v44 = (unsigned int)v49;
      v45 = 1119;
      goto LABEL_144;
    }
    v71 = 0;
    v50 = Microsoft::WRL::Details::MakeAndInitialize<CUHOSDeploymentInformation,CUHOSDeploymentInformation,bool,unsigned long &,unsigned long const &,tagDSFile * const &>(
            (unsigned int)&v82,
            (unsigned int)&v71,
            (unsigned int)&v105,
            (int)v46 + 464,
            (__int64)v46 + 472);
    FilesPerPatchType = v50;
    v51 = 0;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x466,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)v50,
        (int)ppvc);
      v20 = v82;
      goto LABEL_149;
    }
    v20 = v82;
    v52 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64))(*(_QWORD *)v106 + 24LL))(v106, pv, v82);
    FilesPerPatchType = v52;
    if ( v52 < 0 )
    {
      v44 = (unsigned int)v52;
      v45 = 1128;
      goto LABEL_144;
    }
    if ( v75 != 1 )
    {
      if ( v75 == 2 )
      {
        FilesPerPatchType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 48LL))(v14);
      }
      else if ( v75 == 4 )
      {
        v103 = 0;
        FilesPerPatchType = (**(__int64 (__fastcall ***)(__int64, GUID *, struct tagDSGlobalUpdateId **))v14)(
                              v14,
                              &GUID_347c6b31_7d10_4ada_9ede_ae9288f35f47,
                              &v103);
        if ( FilesPerPatchType >= 0 )
        {
          LODWORD(ppvc) = 0;
          WUTrace(0, 0, 4096, 4);
          FilesPerPatchType = (*(__int64 (__fastcall **)(struct tagDSGlobalUpdateId *, _DWORD *))(*(_QWORD *)v103 + 104LL))(
                                v103,
                                v83);
        }
        v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14);
        if ( v60 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4FC,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)v60,
            (int)ppvc);
        if ( v103 )
          (*(void (__fastcall **)(struct tagDSGlobalUpdateId *))(*(_QWORD *)v103 + 16LL))(v103);
      }
      else
      {
        LODWORD(ppvc) = 0;
        WUTrace(0, 0, 4096, 2);
        FilesPerPatchType = -2145112065;
      }
      goto LABEL_133;
    }
    v105 = 0;
    v103 = 0;
    v53 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct tagDSGlobalUpdateId **))v14)(
            v14,
            &GUID_57816c47_d685_423a_89c6_feefbd90ed47,
            &v103);
    if ( v53 >= 0 && v103 )
    {
      v54 = *(_DWORD *)(v30 + 168);
      if ( v54 )
      {
        if ( v54 == 1 )
          v51 = 2;
      }
      else
      {
        v51 = 1;
      }
      v55 = (*(__int64 (__fastcall **)(struct tagDSGlobalUpdateId *, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v103 + 168LL))(
              v103,
              0,
              L"UpdatePriority",
              v51);
      v69 = v51;
      v67 = (unsigned int *)L"UpdatePriority";
      if ( v55 < 0 )
      {
        v66 = L"Failed to set Attribute [%ws] value = %lld";
        LODWORD(ppvc) = v55;
      }
      else
      {
        v66 = L"Set attribute [%ws] value = %lld";
        ppvc = 0;
      }
      WUTrace(0, 0, 4096, 4);
    }
    else
    {
      v66 = L"Update agent does not support priority set capability";
      LODWORD(ppvc) = v53;
      WUTrace(0, 0, 4096, 3);
    }
    if ( v103 )
      (*(void (__fastcall **)(struct tagDSGlobalUpdateId *))(*(_QWORD *)v103 + 16LL))(v103);
    v56 = *(__int64 (__fastcall **)(__int64, __int64 *, _DWORD *))(*(_QWORD *)v14 + 40LL);
    if ( v105 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
      v105 = 0;
    }
    FilesPerPatchType = v56(v14, &v105, v83);
    if ( FilesPerPatchType < 0 )
    {
      v110 = 0;
      v59 = v105;
      if ( v105 )
      {
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v105 + 24LL))(v105, &v110);
        Trace::GuidToString::GuidToString((Trace::GuidToString *)v102, (const struct _GUID *)((char *)v74 + 4));
        LODWORD(ppvc) = FilesPerPatchType;
        WUTrace(0, 0, 4096, 2);
        v59 = v105;
      }
      if ( FilesPerPatchType != -2146498504 )
        goto LABEL_119;
      LODWORD(ppvc) = -2146498504;
      WUTrace(0, 0, 4096, 2);
      FilesPerPatchType = -2145116122;
    }
    else
    {
      v108 = 0;
      v57 = (**(__int64 (__fastcall ***)(__int64, GUID *, OSDeploymentHelper **))v14)(
              v14,
              &GUID_57816c47_d685_423a_89c6_feefbd90ed47,
              &v108);
      if ( v57 >= 0 && v108 )
      {
        v103 = 0;
        v58 = (*(__int64 (__fastcall **)(OSDeploymentHelper *, _QWORD, const wchar_t *, struct tagDSGlobalUpdateId **, LPVOID *, const wchar_t *, unsigned int *, __int64))(*(_QWORD *)v108 + 152LL))(
                v108,
                0,
                L"WillUpdateAutoCommit",
                &v103,
                ppvc,
                v66,
                v67,
                v69);
        if ( v58 < 0 )
        {
          LODWORD(ppvc) = v58;
          WUTrace(0, 0, 4096, 4);
        }
        else
        {
          LODWORD(ppvc) = 0;
          WUTrace(0, 0, 4096, 4);
          *(_DWORD *)v110 = 2 - (v103 != 0);
        }
      }
      else
      {
        LODWORD(ppvc) = v57;
        WUTrace(0, 0, 4096, 3);
      }
      if ( v108 )
        (*(void (__fastcall **)(OSDeploymentHelper *))(*(_QWORD *)v108 + 16LL))(v108);
    }
    v59 = v105;
LABEL_119:
    if ( v59 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
LABEL_133:
    if ( v70 && v93 )
      DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)v79 + 9), v93);
    if ( v94 )
      DuplicateOptionalString<wchar_t *,wchar_t *>(v18, v94);
    if ( FilesPerPatchType >= 0 )
    {
      FilesPerPatchType = 0;
      goto LABEL_149;
    }
    if ( FilesPerPatchType == -2145116147
      || FilesPerPatchType == -2147024894
      || FilesPerPatchType == -1047526943
      || (unsigned int)(FilesPerPatchType + 1047526898) <= 1 )
    {
      goto LABEL_149;
    }
    v44 = (unsigned int)FilesPerPatchType;
    v45 = 1307;
    goto LABEL_144;
  }
  ppvb = FilesPerPatchType;
  WUTrace(0, 0, 4096, 2);
  if ( FilesPerPatchType < 0 )
  {
    v34 = 972;
    goto LABEL_43;
  }
LABEL_151:
  wil::details::lambda_call__lambda_6b188daa3d3c97e193f917f682fa79c8___::_lambda_call__lambda_6b188daa3d3c97e193f917f682fa79c8___(v98);
  v17 = *(void **)v88;
LABEL_152:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v106 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v106 + 16LL))(v106);
    v106 = 0;
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v18 )
    CSusBaseAllocTag<942762101>::operator delete(v18);
  if ( v17 )
    operator delete(v17, v23);
  if ( v80 )
    operator delete(v80, v23);
  return (unsigned int)FilesPerPatchType;
}

```

## disassembly

```asm
0x180028ea8  mov     [rsp-8+arg_10], rbx
0x180028ead  push    rbp
0x180028eae  push    rsi
0x180028eaf  push    rdi
0x180028eb0  push    r12
0x180028eb2  push    r13
0x180028eb4  push    r14
0x180028eb6  push    r15
0x180028eb8  lea     rbp, [rsp-1D0h]
0x180028ec0  sub     rsp, 2D0h
0x180028ec7  mov     rax, cs:__security_cookie
0x180028ece  xor     rax, rsp
0x180028ed1  mov     [rbp+200h+var_40], rax
0x180028ed8  mov     esi, r8d
0x180028edb  mov     [rsp+300h+var_298], r8d
0x180028ee0  mov     r15, rdx
0x180028ee3  mov     [rbp+200h+var_268], rcx
0x180028ee7  mov     dword ptr [rbp+200h+var_100], r9d
0x180028eee  mov     rax, [rbp+200h+arg_20]
0x180028ef5  mov     qword ptr [rbp+200h+rclsid.Data1], rax
0x180028ef9  mov     rax, [rbp+200h+arg_28]
0x180028f00  mov     [rbp+200h+var_258], rax
0x180028f04  mov     rax, [rbp+200h+arg_30]
0x180028f0b  mov     qword ptr [rbp+200h+var_D8], rax
0x180028f12  mov     rcx, [rbp+200h+arg_38]
0x180028f19  mov     [rbp+200h+var_200], rcx
0x180028f1d  mov     rax, [rbp+200h+arg_40]
0x180028f24  mov     [rbp+200h+var_1F8], rax
0x180028f28  mov     r14, [rbp+200h+arg_48]
0x180028f2f  mov     [rsp+300h+var_290], r14
0x180028f34  mov     rax, [rdx+38h]
0x180028f38  mov     [rsp+300h+var_2A0], rax
0x180028f3d  lea     rax, [rdx+20h]
0x180028f41  mov     [rbp+200h+var_110], rax
0x180028f48  mov     r13, [rdx+10h]
0x180028f4c  mov     [rbp+200h+var_250], r13
0x180028f50  mov     rax, [rdx+18h]
0x180028f54  mov     [rbp+200h+var_E8], rax
0x180028f5b  mov     ebx, [rdx+50h]
0x180028f5e  xor     r12d, r12d
0x180028f61  mov     edi, r12d
0x180028f64  mov     [rsp+300h+var_2A4], r12d
0x180028f69  test    r8b, 1
0x180028f6d  jz      short loc_180028FA4
0x180028f6f  mov     edi, ebx
0x180028f71  shr     edi, 6
0x180028f74  and     edi, 4
0x180028f77  mov     [rsp+300h+var_2A4], edi
0x180028f7b  mov     dword ptr [rsp+300h+var_2D0], edi
0x180028f7f  lea     rax, aOptionalsessio_0; "OptionalSessionFlags for Install to be "...
0x180028f86  mov     [rsp+300h+var_2D8], rax
0x180028f8b  mov     [rsp+300h+ppv], r12
0x180028f90  xor     edx, edx
0x180028f92  xor     ecx, ecx
0x180028f94  lea     r9d, [r12+4]
0x180028f99  mov     r8d, 1000h
0x180028f9f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028fa4  test    sil, 2
0x180028fa8  jz      short loc_180028FE2
0x180028faa  mov     eax, edi
0x180028fac  or      eax, 1
0x180028faf  bt      ebx, 9
0x180028fb3  cmovnb  eax, edi
0x180028fb6  mov     [rsp+300h+var_2A4], eax
0x180028fba  mov     dword ptr [rsp+300h+var_2D0], eax
0x180028fbe  lea     rax, aOptionalsessio; "OptionalSessionFlags for Commit to be p"...
0x180028fc5  mov     [rsp+300h+var_2D8], rax
0x180028fca  mov     [rsp+300h+ppv], r12; unsigned int
0x180028fcf  xor     edx, edx
0x180028fd1  xor     ecx, ecx
0x180028fd3  lea     r9d, [rdx+4]
0x180028fd7  mov     r8d, 1000h
0x180028fdd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028fe2  mov     rax, [r15+100h]
0x180028fe9  mov     qword ptr [rbp+200h+var_218], rax
0x180028fed  mov     rax, [r15+68h]
0x180028ff1  mov     [rbp+200h+var_228], rax
0x180028ff5  mov     rax, [r15+0F8h]
0x180028ffc  mov     [rbp+200h+var_220], rax
0x180029000  lea     rax, [r15+70h]
0x180029004  mov     [rbp+200h+var_248], rax
0x180029008  mov     [rbp+200h+var_238], r14
0x18002900c  mov     [rbp+200h+var_278], r12
0x180029010  mov     dword ptr [rsp+300h+var_2AC+4], r12d
0x180029015  mov     [rbp+200h+var_270], r12
0x180029019  mov     dword ptr [rsp+300h+var_2AC], r12d
0x18002901e  mov     rbx, r12
0x180029021  mov     qword ptr [rbp+200h+var_230], rbx
0x180029025  xorps   xmm0, xmm0
0x180029028  movups  xmmword ptr [rbp+200h+Uuid.Data1], xmm0
0x18002902f  mov     rsi, r12
0x180029032  mov     [rsp+300h+var_288], r12
0x180029037  mov     [rbp+200h+pv], r12
0x18002903e  mov     rdi, r12
0x180029041  mov     [rbp+200h+var_280], r12
0x180029045  mov     r14, r12
0x180029048  mov     [rbp+200h+var_260], r12
0x18002904c  mov     [rbp+200h+var_F8], r12
0x180029053  mov     [rbp+200h+var_208], r12
0x180029057  mov     rdx, [rsp+300h+var_2A0]
0x18002905c  add     rdx, 4; struct tagDSGlobalUpdateId *
0x180029060  lea     rcx, [rbp+200h+var_B0]; this
0x180029067  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18002906c  xor     eax, eax
0x18002906e  mov     [rbp+200h+hObject], rax
0x180029075  mov     rcx, [r15]; StringUuid
0x180029078  test    rcx, rcx
0x18002907b  jz      short loc_1800290B6
0x18002907d  cmp     [rcx], ax
0x180029080  jz      short loc_1800290B6
0x180029082  lea     rdx, [rbp+200h+Uuid]; Uuid
0x180029089  call    cs:__imp_UuidFromStringW
0x18002908f  test    eax, eax
0x180029091  jz      short loc_1800290B6
0x180029093  mov     rcx, [rbp+208h]; this
0x18002909a  mov     r9d, eax; char *
0x18002909d  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800290a4  mov     edx, 37Ah; void *
0x1800290a9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800290ae  mov     r15d, eax
0x1800290b1  jmp     loc_180029E16
0x1800290b6  lea     r8, [rbp+200h+Uuid]; struct _GUID *
0x1800290bd  mov     rdx, [rbp+200h+var_110]; struct tagDSGlobalUpdateId *
0x1800290c4  mov     r15, [rsp+300h+var_2A0]
0x1800290c9  mov     rcx, r15; struct tagDSUpdateMetadata *
0x1800290cc  call    ?IsUUPOnPremLangSpecificChildUpdate@@YA_NAEBUtagDSUpdateMetadata@@AEBUtagDSGlobalUpdateId@@AEBU_GUID@@@Z; IsUUPOnPremLangSpecificChildUpdate(tagDSUpdateMetadata const &,tagDSGlobalUpdateId const &,_GUID const &)
0x1800290d1  test    al, al
0x1800290d3  jz      short loc_180029119
0x1800290d5  lea     rdx, [r15+4]; struct tagDSGlobalUpdateId *
0x1800290d9  lea     rcx, [rbp+200h+var_180]; this
0x1800290e0  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800290e5  mov     [rsp+300h+var_2D0], rax
0x1800290ea  lea     rax, aSkippingUupOnP; "Skipping UUP on Prem language specific "...
0x1800290f1  mov     [rsp+300h+var_2D8], rax
0x1800290f6  xor     r13d, r13d
0x1800290f9  mov     [rsp+300h+ppv], r13
0x1800290fe  xor     edx, edx
0x180029100  xor     ecx, ecx
0x180029102  lea     r9d, [r13+4]
0x180029106  mov     r8d, 1000h
0x18002910c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029111  mov     r15d, r13d
0x180029114  jmp     loc_180029E19
0x180029119  lea     rax, [r15+4]
0x18002911d  mov     r15d, [rax+10h]
0x180029121  mov     rdx, rax; struct _GUID *
0x180029124  lea     rcx, [rbp+200h+var_180]; this
0x18002912b  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180029130  lea     r8, aUnknown; "Unknown"
0x180029137  mov     edx, [rsp+300h+var_298]
0x18002913b  sub     edx, 1
0x18002913e  jz      short loc_18002915C
0x180029140  sub     edx, 1
0x180029143  jz      short loc_180029153
0x180029145  cmp     edx, 2
0x180029148  jnz     short loc_180029163
0x18002914a  lea     r8, aRevert_0; "Revert"
0x180029151  jmp     short loc_180029163
0x180029153  lea     r8, aCommit; "Commit"
0x18002915a  jmp     short loc_180029163
0x18002915c  lea     r8, aInstall; "Install"
0x180029163  mov     dword ptr [rsp+300h+var_2C0], r15d
0x180029168  mov     [rsp+300h+var_2C8], rax
0x18002916d  mov     [rsp+300h+var_2D0], r8
0x180029172  lea     rax, aPreparingToWsU; "Preparing to %ws update ID: %ws.%d"
0x180029179  mov     [rsp+300h+var_2D8], rax
0x18002917e  mov     [rsp+300h+ppv], 0; int
0x180029187  mov     r9d, 4
0x18002918d  mov     r15d, 1000h
0x180029193  mov     r8d, r15d
0x180029196  xor     edx, edx
0x180029198  xor     ecx, ecx
0x18002919a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002919f  mov     rax, r13
0x1800291a2  mov     rcx, [rbp+200h+var_E8]
0x1800291a9  test    rcx, rcx
0x1800291ac  cmovnz  rax, rcx
0x1800291b0  mov     [rbp+200h+var_240], rax
0x1800291b4  mov     rcx, r13; pbstr
0x1800291b7  call    cs:__imp_SysStringLen
0x1800291bd  xor     r13d, r13d
0x1800291c0  test    eax, eax
0x1800291c2  jnz     short loc_1800291EA
0x1800291c4  mov     rcx, [rbp+208h]; this
0x1800291cb  mov     r15d, 80070057h
0x1800291d1  mov     r9d, r15d; char *
0x1800291d4  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800291db  mov     edx, 394h; void *
0x1800291e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800291e5  jmp     loc_180029E19
0x1800291ea  mov     rax, [rbp+200h+var_258]
0x1800291ee  mov     [rax], r13d
0x1800291f1  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1800291f6  test    eax, eax
0x1800291f8  jz      short loc_180029276
0x1800291fa  xor     r9d, r9d
0x1800291fd  lea     r8, aBreakonhandler; "BreakOnHandlerInstallCall"
0x180029204  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002920b  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x180029210  mov     ebx, eax
0x180029212  test    eax, eax
0x180029214  jz      short loc_180029276
0x180029216  call    cs:__imp_GetCurrentProcessId
0x18002921c  mov     dword ptr [rsp+300h+var_2C8], ebx
0x180029220  mov     dword ptr [rsp+300h+var_2D0], eax
0x180029224  lea     rax, aPidLuWaitingLu; "PID:%lu - waiting %lu seconds for debug"...
0x18002922b  mov     [rsp+300h+var_2D8], rax
0x180029230  mov     [rsp+300h+ppv], r13
0x180029235  mov     r9d, 3
0x18002923b  mov     r8d, r15d
0x18002923e  xor     edx, edx
0x180029240  xor     ecx, ecx
0x180029242  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029247  jmp     short loc_18002925C
0x180029249  mov     eax, ebx
0x18002924b  dec     ebx
0x18002924d  test    eax, eax
0x18002924f  jz      short loc_180029266
0x180029251  mov     ecx, 3E8h; dwMilliseconds
0x180029256  call    cs:__imp_Sleep
0x18002925c  call    cs:__imp_IsDebuggerPresent
0x180029262  test    eax, eax
0x180029264  jz      short loc_180029249
0x180029266  call    cs:__imp_IsDebuggerPresent
0x18002926c  test    eax, eax
0x18002926e  jz      short loc_180029276
0x180029270  call    cs:__imp_DebugBreak
0x180029276  xorps   xmm0, xmm0
0x180029279  movups  [rbp+200h+var_1D0], xmm0
0x18002927d  movups  [rbp+200h+var_1C0], xmm0
0x180029281  lea     rax, [rbp+200h+var_F8]
0x180029288  mov     qword ptr [rbp+200h+var_1D0], rax
0x18002928c  lea     rax, [rbp+200h+pv]
0x180029293  mov     qword ptr [rbp+200h+var_1D0+8], rax
0x180029297  mov     r13, [rbp+200h+var_268]
0x18002929b  mov     qword ptr [rbp+200h+var_1C0], r13
0x18002929f  mov     byte ptr [rbp+200h+var_1C0+8], 1
0x1800292a3  lea     rax, [rbp+200h+var_230]
0x1800292a7  mov     [rsp+300h+var_2D0], rax; unsigned int *
0x1800292ac  lea     rax, [rsp+300h+var_2AC]
0x1800292b1  mov     [rsp+300h+var_2D8], rax; struct tagDSFile ***
0x1800292b6  lea     rax, [rbp+200h+var_270]
0x1800292ba  mov     [rsp+300h+ppv], rax; int
0x1800292bf  lea     r9, [rsp+300h+var_2AC+4]; struct tagDSFile **
0x1800292c4  lea     r8, [rbp+200h+var_278]; struct tagDSFile *
0x1800292c8  mov     rbx, [rsp+300h+var_2A0]
0x1800292cd  mov     rdx, [rbx+1D8h]; unsigned int
0x1800292d4  mov     ecx, [rbx+1D0h]; this
0x1800292da  call    ?GetFilesPerPatchType@OSDeploymentHelper@@YAJKQEAUtagDSFile@@PEAPEBU2@PEAKPEAPEAPEAU2@23@Z; OSDeploymentHelper::GetFilesPerPatchType(ulong,tagDSFile * const,tagDSFile const * *,ulong *,tagDSFile * * *,ulong *,tagDSFile * * *)
0x1800292df  mov     r15d, eax
0x1800292e2  xor     ecx, ecx
0x1800292e4  test    eax, eax
0x1800292e6  jns     short loc_180029314
0x1800292e8  lea     rax, aFailedToDeterm; "Failed to determine the servicing stack"...
0x1800292ef  mov     [rsp+300h+var_2D8], rax
0x1800292f4  mov     dword ptr [rsp+300h+ppv], r15d
0x1800292f9  xor     edx, edx
0x1800292fb  lea     r9d, [rcx+2]
0x1800292ff  mov     r8d, 1000h
0x180029305  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002930a  mov     edx, 3BAh
0x18002930f  jmp     loc_1800294CD
0x180029314  mov     rax, [rbp+200h+var_278]
0x180029318  test    rax, rax
0x18002931b  setnz   [rsp+300h+var_2B0]
0x180029320  test    rax, rax
0x180029323  jz      short loc_180029388
0x180029325  mov     [rbp+200h+var_108], ecx
0x18002932b  lea     r8, [rbp+200h+var_108]; struct tagDSFile *
0x180029332  mov     rdx, rax; wchar_t *
0x180029335  mov     rcx, [rbp+200h+var_240]; this
0x180029339  call    ?EvaluateFileInSandbox@OSDeploymentHelper@@YAJPEB_WAEBUtagDSFile@@PEAJ@Z; OSDeploymentHelper::EvaluateFileInSandbox(wchar_t const *,tagDSFile const &,long *)
0x18002933e  mov     r15d, eax
0x180029341  xor     ecx, ecx
0x180029343  test    eax, eax
0x180029345  js      short loc_180029353
0x180029347  mov     r15d, [rbp+200h+var_108]
0x18002934e  test    r15d, r15d
0x180029351  jns     short loc_180029388
0x180029353  lea     rax, aServicingStack; "Servicing stack cab validation failed"
0x18002935a  mov     [rsp+300h+var_2D8], rax
0x18002935f  mov     dword ptr [rsp+300h+ppv], r15d
0x180029364  xor     edx, edx
0x180029366  lea     r9d, [rdx+2]
0x18002936a  mov     r8d, 1000h
0x180029370  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029375  test    r15d, r15d
0x180029378  jns     loc_180029E09
0x18002937e  mov     edx, 3CCh
0x180029383  jmp     loc_1800294CD
0x180029388  cmp     [rbp+200h+var_E8], rcx
0x18002938f  jnz     short loc_1800293EE
0x180029391  mov     eax, ecx
0x180029393  mov     dword ptr [rsp+300h+var_2AC], ecx
0x180029397  cmp     dword ptr [rsp+300h+var_2AC+4], ecx
0x18002939b  jbe     short loc_1800293EE
0x18002939d  mov     [rbp+200h+var_108], ecx
0x1800293a3  mov     ebx, eax
0x1800293a5  mov     r13, [rbp+200h+var_270]
0x1800293a9  lea     r8, [rbp+200h+var_108]; struct tagDSFile *
  ... truncated ...
```
