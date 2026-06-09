# DesktopAppXActivator::InnerActivate(HSTRING__ *,ushort const *,ushort const *,ulong,ulong,IInspectable *,ushort const *,DesktopAppXProvider::Activation,int)

- ea: `0x180006f30`
- end: `0x18000783c`
- name: `?InnerActivate@DesktopAppXActivator@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@PEBG1KKPEAUIInspectable@@1VActivation@DesktopAppXProvider@@H@Z`
- size: `2316`
- prototype: `HANDLE *__fastcall(DesktopAppXActivator *this, HANDLE *, HSTRING, const WCHAR *, const WCHAR *, unsigned int, unsigned int, __int64, const WCHAR *, __int64, int)`
- caller_count: `1`
- callee_count: `50`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180006420`

## callees

- `0x180003d24`
- `0x1800040e0`
- `0x180006cf0`
- `0x180006f30`
- `0x180007844`
- `0x18000790c`
- `0x180007970`
- `0x1800079e4`
- `0x180007ce0`
- `0x180007f40`
- `0x1800080dc`
- `0x180008134`
- `0x180008188`
- `0x1800083f0`
- `0x18000843c`
- `0x180008470`
- `0x180008734`
- `0x18000876c`
- `0x180008820`
- `0x1800093ec`
- `0x18000d010`
- `0x1800121f8`
- `0x18001675c`
- `0x18001699c`
- `0x180016b88`
- `0x180017cd0`
- `0x1800192a8`
- `0x1800195b0`
- `0x18001a214`
- `0x180021c94`
- `0x180021e14`
- `0x180025de8`
- `0x180026b00`
- `0x180027150`
- `0x18002b1b0`
- `0x18002d89c`
- `0x180033d5c`
- `0x180035dc0`
- `0x180035e80`
- `0x1800361ec`
- `0x18003679c`
- `0x180036dc4`
- `0x180037558`
- `0x180037cc0`
- `0x180038e18`
- `0x180039c70`
- `0x180039f74`
- `0x18003a184`
- `0x18003a1a8`
- `0x180085010`

## import_xrefs

- `Windows.Storage!ShellExecuteExW` at `0x1800074ac`
- `Windows.Storage!ShellExecuteExW` at `0x1800074ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800071fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800072eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007321`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800071fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800072eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007321`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007220`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007358`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800075ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007220`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007358`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800075ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007835`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800076b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000774f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800076b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000774f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800076ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800076ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000701b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800070d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800073cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000701b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800070d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800073cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007679`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180007177`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180007177`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000716a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000716a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000708d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000708d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007744`
- `ext-ms-win-core-storelicensing-l1-1-0!BeginAcquireStoreLicenseForPackageActivation` at `0x1800070ea`
- `ext-ms-win-core-storelicensing-l1-1-0!BeginAcquireStoreLicenseForPackageActivation` at `0x1800070ea`

## pseudocode

```c
HANDLE *__fastcall DesktopAppXActivator::InnerActivate(
        DesktopAppXActivator *this,
        HANDLE *a2,
        HSTRING a3,
        const WCHAR *a4,
        const WCHAR *a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        const WCHAR *a9,
        __int64 a10,
        int a11)
{
  char v14; // r13
  volatile int *v15; // rdx
  __int64 v16; // rcx
  WCHAR *v17; // rdi
  WCHAR **WorkingDirectory; // rsi
  struct IUnknown *v19; // r15
  PCWSTR StringRawBuffer; // rax
  int v21; // eax
  void *v22; // rdx
  unsigned int v23; // r8d
  HMONITOR TargetMonitorFromSite; // rcx
  ULONG fMask; // eax
  DWORD CurrentProcessId; // eax
  const char *v27; // r9
  struct IUnknown *v28; // r14
  struct IUnknown *v29; // rbx
  struct IUnknownVtbl *lpVtbl; // r15
  struct IUnknownVtbl *v31; // rbx
  unsigned int v32; // r13d
  int v33; // esi
  unsigned int v34; // r13d
  struct IUnknown *v35; // rcx
  LPVOID v36; // r14
  PCWSTR v37; // rax
  const WCHAR *v38; // rsi
  unsigned __int64 v39; // rbx
  unsigned int v40; // eax
  int v41; // eax
  int v42; // eax
  const unsigned __int16 *v43; // rdx
  const unsigned __int16 *v44; // rdx
  DesktopAppXActivator *v45; // rcx
  DWORD LastError; // edi
  const WCHAR *v47; // rbx
  const WCHAR *v48; // rax
  unsigned __int16 *v49; // rdx
  DesktopAppXActivator *v50; // rcx
  unsigned int v51; // r8d
  DesktopAppXActivator *v52; // rcx
  struct IUnknown *v53; // rcx
  char v54; // bl
  signed int v55; // eax
  __int64 v56; // rdx
  const unsigned __int16 *v57; // rax
  int updated; // eax
  struct IUnknownVtbl *v59; // rbx
  __int64 v60; // rcx
  int v61; // eax
  HANDLE *v62; // rbx
  volatile signed __int32 *v63; // r8
  signed __int32 i; // edx
  int v66; // [rsp+20h] [rbp-E0h]
  unsigned int v67; // [rsp+20h] [rbp-E0h]
  char v68[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pSessionId; // [rsp+34h] [rbp-CCh] BYREF
  struct IUnknown *v70; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int hInstApp; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v72; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v74[2]; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v75[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v76; // [rsp+70h] [rbp-90h]
  WCHAR *v77; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v79; // [rsp+88h] [rbp-78h] BYREF
  HSTRING newString; // [rsp+90h] [rbp-70h] BYREF
  char v81; // [rsp+98h] [rbp-68h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE *v83; // [rsp+110h] [rbp+10h]
  unsigned int v84; // [rsp+118h] [rbp+18h]
  DesktopAppXActivator *v85; // [rsp+120h] [rbp+20h]
  struct IUnknown *v86; // [rsp+128h] [rbp+28h]
  char v87; // [rsp+130h] [rbp+30h]
  __int64 v88; // [rsp+138h] [rbp+38h]
  HSTRING_HEADER hstringHeader; // [rsp+140h] [rbp+40h] BYREF
  __int64 v90; // [rsp+158h] [rbp+58h]
  void **v91; // [rsp+160h] [rbp+60h] BYREF
  char v92[40]; // [rsp+168h] [rbp+68h] BYREF
  char v93[192]; // [rsp+190h] [rbp+90h] BYREF
  char v94[32]; // [rsp+250h] [rbp+150h] BYREF
  _DWORD *v95; // [rsp+270h] [rbp+170h]
  _DWORD *v96; // [rsp+278h] [rbp+178h] BYREF
  char v97[24]; // [rsp+280h] [rbp+180h] BYREF
  int v98; // [rsp+298h] [rbp+198h]
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v79 = a4;
  v75[0] = a3;
  v83 = a2;
  *(_QWORD *)v74 = a2;
  v14 = a6;
  hInstApp = a6;
  v88 = a10;
  v76 = 0;
  v66 = a8;
  ApplicationIdentityInfo::Create(&v70, a3, a6, a7);
  ApplicationIdentityInfo::GetProcessPath(v70, &string, a4);
  memset(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.nShow = a11;
  if ( (a6 & 1) != 0 )
  {
    pv = (LPVOID)WindowsGetStringRawBuffer((HSTRING)v70[14].lpVtbl, 0);
    DesktopAppXProvider::Activation::CentennialElevation<unsigned short const *>(a10, &pv);
    pExecInfo.lpVerb = L"runas";
  }
  v17 = 0;
  v77 = 0;
  if ( a9 )
  {
    pExecInfo.lpDirectory = a9;
  }
  else
  {
    WorkingDirectory = (WCHAR **)DesktopAppXActivator::GetWorkingDirectory(v16, &pv, a3);
    if ( &v77 != WorkingDirectory )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v77,
        *WorkingDirectory);
      *WorkingDirectory = 0;
      v17 = v77;
    }
    if ( pv )
      CoTaskMemFree(pv);
    pExecInfo.lpDirectory = v17;
  }
  v19 = v70;
  *(_QWORD *)v74 = v70;
  if ( v70 )
    Microsoft::WRL::Details::SafeUnknownIncrementReference(
      (Microsoft::WRL::Details *)((char *)&v70[11].lpVtbl + 4),
      v15);
  v84 = a6;
  v85 = this;
  v86 = v19;
  v87 = 1;
  if ( (unsigned __int8)IsBeginAcquireStoreLicenseForPackageActivationPresent() )
  {
    if ( (a6 & 0x40) == 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v70[14].lpVtbl, 0);
      v21 = BeginAcquireStoreLicenseForPackageActivation(StringRawBuffer, 1, 0);
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_NtStatus(retaddr, v22, v23, (const char *)(unsigned int)v21, a8);
    }
  }
  pExecInfo.fMask |= 0x8800040u;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialActivationUsesShellExecuteNoHooksMask>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CentennialActivationUsesShellExecuteNoHooksMask>::GetImpl'::`2'::impl) )
    pExecInfo.fMask |= 0x2000u;
  pExecInfo.lpFile = WindowsGetStringRawBuffer(string, 0);
  pExecInfo.lpParameters = a5;
  TargetMonitorFromSite = DesktopAppXActivator::GetTargetMonitorFromSite(this);
  fMask = pExecInfo.fMask;
  if ( TargetMonitorFromSite )
  {
    fMask = pExecInfo.fMask | 0x200000;
    pExecInfo.fMask |= 0x200000u;
    pExecInfo.hIcon = TargetMonitorFromSite;
  }
  if ( (a6 & 8) != 0 )
  {
    pExecInfo.fMask = fMask | 0x400;
  }
  else
  {
    pSessionId = 0;
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x24D,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        v27);
    if ( !pSessionId )
      pExecInfo.fMask |= 0x400u;
  }
  if ( DesktopAppXActivator::GetLogUsageFromSite(this) )
    pExecInfo.fMask |= 0x4000000u;
  v28 = v70;
  v72 = 0;
  v76 = 128;
  (*(void (__fastcall **)(char *, GUID *, struct IUnknown **))(*((_QWORD *)this + 1) + 32LL))(
    (char *)this + 8,
    &GUID_00000000_0000_0000_c000_000000000046,
    &v72);
  v29 = v72;
  if ( !v72 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)&v28[2]);
    lpVtbl = v28[4].lpVtbl;
    v28[4].lpVtbl = 0;
    v31 = lpVtbl;
    pv = lpVtbl;
    v32 = (unsigned int)v28[3].lpVtbl;
    LODWORD(v28[3].lpVtbl) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)&v28[2]);
    if ( v32 )
    {
      GlobalInterfaceTable::Revoke(v32);
    }
    else if ( lpVtbl )
    {
      v31 = 0;
      pv = 0;
      (*((void (__fastcall **)(struct IUnknownVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
    }
    v33 = 0;
    if ( v31 )
      (*((void (__fastcall **)(struct IUnknownVtbl *))v31->QueryInterface + 2))(v31);
    v19 = *(struct IUnknown **)v74;
LABEL_36:
    v14 = hInstApp;
    goto LABEL_37;
  }
  if ( !IsAgile(v28) || IsAgile(v29) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)&v28[2]);
    if ( (struct IUnknown *)v28[4].lpVtbl != v29 )
    {
      ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->AddRef)(v29);
      *(struct IUnknown *)v74 = v28[4];
      v28[4].lpVtbl = (struct IUnknownVtbl *)v29;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v74);
    }
    ReleaseSRWLockExclusive((PSRWLOCK)&v28[2]);
    v33 = 0;
  }
  else
  {
    pSessionId = 0;
    v33 = GlobalInterfaceTable::s_Retrieve();
    if ( v33 >= 0 )
      v33 = ((__int64 (__fastcall *)(struct IGlobalInterfaceTable *, struct IUnknown *, GUID *, DWORD *))GlobalInterfaceTable::s_pGlobalInterfaceTable->lpVtbl->RegisterInterfaceInGlobal)(
              GlobalInterfaceTable::s_pGlobalInterfaceTable,
              v29,
              &GUID_00000000_0000_0000_c000_000000000046,
              &pSessionId);
    if ( v33 >= 0 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)&v28[2]);
      v34 = (unsigned int)v28[3].lpVtbl;
      LODWORD(v28[3].lpVtbl) = pSessionId;
      ReleaseSRWLockExclusive((PSRWLOCK)&v28[2]);
      if ( v34 )
        GlobalInterfaceTable::Revoke(v34);
      goto LABEL_36;
    }
  }
LABEL_37:
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v33,
      v66);
  v35 = v72;
  if ( v72 )
  {
    v72 = 0;
    ((void (__fastcall *)(struct IUnknown *))v35->lpVtbl->Release)(v35);
  }
  pExecInfo.hInstApp = (HINSTANCE)v70;
  DesktopAppXProvider::ActivationShellExec::Start<>((DesktopAppXProvider::ActivationShellExec *)&v91);
  wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(&pv);
  v72 = 0;
  v36 = pv;
  *(_QWORD *)v74 = *(_QWORD *)pv;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  v37 = WindowsGetStringRawBuffer((HSTRING)v70[14].lpVtbl, 0);
  v38 = v37;
  v90 = 0;
  v39 = -1;
  do
    ++v39;
  while ( v37[v39] );
  if ( v39 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x18000783BLL);
  }
  v40 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v39);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v38, v40, v39);
  v41 = (*(__int64 (__fastcall **)(LPVOID, __int64, struct IUnknown **))(*(_QWORD *)v74 + 176LL))(v36, v90, &v72);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x265,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v41,
      v66);
  v68[0] = 0;
  v42 = ((__int64 (__fastcall *)(struct IUnknown *, char *))v72->lpVtbl[13].AddRef)(v72, v68);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x267,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v42,
      v66);
  if ( v68[0] && !DesktopAppXActivator::IsServiceRunning(retaddr, v43) )
  {
    DesktopAppXProvider::Activation::GamingServicesNotRunningDuringMSIXVCActivation();
    DesktopAppXActivator::StartGSService(v45, v44);
  }
  if ( !ShellExecuteExW(&pExecInfo) )
  {
    LastError = GetLastError();
    pSessionId = LastError;
    v47 = &pszDefault;
    if ( pExecInfo.lpFile )
      v48 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath();
    else
      v48 = &pszDefault;
    *(_QWORD *)v74 = v48;
    hInstApp = (unsigned int)pExecInfo.hInstApp;
    if ( v79 )
      v47 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath();
    v79 = v47;
    v75[0] = (HSTRING)WindowsGetStringRawBuffer(v75[0], 0);
    DesktopAppXProvider::Activation::ActivationShellExecuteError<unsigned short const *,unsigned short const *,int,unsigned long &,unsigned short const *>(
      (unsigned int)v75,
      (unsigned int)&v79,
      (unsigned int)&hInstApp,
      (unsigned int)&pSessionId,
      (__int64)v74);
    if ( v68[0] )
    {
      if ( !DesktopAppXActivator::IsServiceRunning(v50, v49) )
        DesktopAppXActivator::EnsureGSIsRegisteredIfBlocked(v52, v49);
    }
    wil::details::in1diag3::Throw_Win32(retaddr, v49, v51, (const char *)LastError, v67);
  }
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v91);
  v87 = 0;
  v53 = v72;
  if ( v72 )
  {
    v72 = 0;
    ((void (__fastcall *)(struct IUnknown *))v53->lpVtbl->Release)(v53);
  }
  if ( pv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  v91 = &DesktopAppXProvider::ActivationShellExec::`vftable';
  if ( !v96 )
    goto LABEL_82;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v91, v75);
  if ( !v96 || (v54 = 1, *v96 != 1) )
  {
    v54 = 0;
    wil::details::shared_object<wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopAppXProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v96);
  }
  if ( v75[0] )
    ReleaseSRWLockExclusive((PSRWLOCK)v75[0]);
  if ( v54 )
  {
LABEL_82:
    if ( *v95 == 1 )
    {
      v55 = v95[22];
      pSessionId = v55;
      v56 = 2147942974LL;
      if ( v55 < 0 )
        v56 = (unsigned int)v55;
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopAppXProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v95,
        v56,
        &pSessionId);
      wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v91);
    }
  }
  if ( v98 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v97);
  wil::details::shared_object<wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopAppXProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v96);
  wil::details::shared_buffer::reset((wil::details::shared_buffer *)v94);
  wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)v93);
  _TlgActivityBase<wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopAppXProvider,_TlgReflectorTag_Param0IsProviderType>,0,5>::~_TlgActivityBase<wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopAppXProvider,_TlgReflectorTag_Param0IsProviderType>,0,5>(v92);
  if ( (v14 & 0x40) == 0 )
  {
    v57 = WindowsGetStringRawBuffer((HSTRING)v70[14].lpVtbl, 0);
    updated = DesktopAppXActivator::TriggerAppInstallerUpdateIfNeeded(v57);
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x28E,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)(unsigned int)updated,
        v66);
  }
  newString = 0;
  v81 = 0;
  v59 = v70[14].lpVtbl;
  WindowsDeleteString(0);
  newString = 0;
  if ( WindowsDuplicateString((HSTRING)v59, &newString) >= 0 )
  {
    _lambda_d34c682e754bdacf457b900fc9d42113_::_lambda_d34c682e754bdacf457b900fc9d42113_(v75, &newString);
    v61 = Windows::Internal::ComTaskPool::QueueTask<_lambda_d34c682e754bdacf457b900fc9d42113_ &>(v60, v75);
    if ( v61 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x29F,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)(unsigned int)v61,
        v66);
    _lambda_d34c682e754bdacf457b900fc9d42113_::~_lambda_d34c682e754bdacf457b900fc9d42113_((_lambda_d34c682e754bdacf457b900fc9d42113_ *)v75);
  }
  v62 = v83;
  *v83 = pExecInfo.hProcess;
  WindowsDeleteString(newString);
  newString = 0;
  if ( v19 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithGITSite,IServiceProvider,IApplicationIdentityInfo,Microsoft::WRL::FtmBase>::Release(v19);
  if ( v17 )
    CoTaskMemFree(v17);
  WindowsDeleteString(string);
  string = 0;
  v63 = (volatile signed __int32 *)v70;
  if ( v70 )
  {
    v70 = 0;
    for ( i = *((_DWORD *)v63 + 23); i != 0x7FFFFFFF; i = *((_DWORD *)v63 + 23) )
    {
      if ( i == _InterlockedCompareExchange(v63 + 23, i - 1, i) )
        break;
    }
    if ( i == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v63 + 40LL))(v63, 1);
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
    }
  }
  *(_QWORD *)a10 = &DesktopAppXProvider::Activation::`vftable';
  wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(a10);
  if ( *(_DWORD *)(a10 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a10 + 288));
  wil::details::shared_object<wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopAppXProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(a10 + 280);
  wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopAppXProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DesktopAppXProvider,_TlgReflectorTag_Param0IsProviderType>(a10 + 8);
  return v62;
}

```

## disassembly

```asm
0x180006f30  push    rbp
0x180006f32  push    rbx
0x180006f33  push    rsi
0x180006f34  push    rdi
0x180006f35  push    r12
0x180006f37  push    r13
0x180006f39  push    r14
0x180006f3b  push    r15
0x180006f3d  lea     rbp, [rsp-1C8h]
0x180006f45  sub     rsp, 2C8h
0x180006f4c  mov     rax, cs:__security_cookie
0x180006f53  xor     rax, rsp
0x180006f56  mov     [rbp+200h+var_50], rax
0x180006f5d  mov     rdi, r9
0x180006f60  mov     [rbp+200h+var_278], r9
0x180006f64  mov     r15, r8
0x180006f67  mov     [rsp+300h+var_2A0], r8
0x180006f6c  mov     [rbp+200h+var_1F0], rdx
0x180006f70  mov     rbx, rcx
0x180006f73  mov     qword ptr [rsp+300h+var_2A8], rdx
0x180006f78  mov     r14, [rbp+200h+arg_20]
0x180006f7f  mov     r13d, [rbp+200h+arg_28]
0x180006f86  mov     [rsp+300h+var_2C0], r13d
0x180006f8b  mov     rax, [rbp+200h+arg_38]
0x180006f92  mov     rsi, [rbp+200h+arg_40]
0x180006f99  mov     r12, [rbp+200h+arg_48]
0x180006fa0  mov     [rbp+200h+var_1C8], r12
0x180006fa4  mov     [rsp+300h+var_290], 0
0x180006fac  mov     qword ptr [rsp+300h+var_2E0], rax; int
0x180006fb1  mov     r9d, [rbp+200h+arg_30]
0x180006fb8  mov     r8d, r13d
0x180006fbb  mov     rdx, r15
0x180006fbe  lea     rcx, [rsp+300h+var_2C8]
0x180006fc3  call    ?Create@ApplicationIdentityInfo@@SA?AV?$ComPtr@VApplicationIdentityInfo@@@WRL@Microsoft@@PEAUHSTRING__@@KKPEAUIInspectable@@@Z; ApplicationIdentityInfo::Create(HSTRING__ *,ulong,ulong,IInspectable *)
0x180006fc8  nop
0x180006fc9  mov     r8, rdi
0x180006fcc  lea     rdx, [rbp+200h+string]
0x180006fd0  mov     rcx, [rsp+300h+var_2C8]
0x180006fd5  call    ?GetProcessPath@ApplicationIdentityInfo@@QEBA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; ApplicationIdentityInfo::GetProcessPath(ushort const *)
0x180006fda  nop
0x180006fdb  xorps   xmm0, xmm0
0x180006fde  movups  xmmword ptr [rbp+200h+pExecInfo.cbSize], xmm0
0x180006fe2  movups  xmmword ptr [rbp+200h+pExecInfo.lpVerb], xmm0
0x180006fe6  movups  xmmword ptr [rbp+200h+pExecInfo.lpParameters], xmm0
0x180006fea  movups  xmmword ptr [rbp+200h+pExecInfo.nShow], xmm0
0x180006fee  movups  xmmword ptr [rbp+200h+pExecInfo.lpIDList], xmm0
0x180006ff2  movups  xmmword ptr [rbp+200h+pExecInfo.hkeyClass], xmm0
0x180006ff6  movups  xmmword ptr [rbp+200h+pExecInfo.60h], xmm0
0x180006ffa  mov     [rbp+200h+pExecInfo.cbSize], 70h ; 'p'
0x180007001  mov     eax, [rbp+200h+arg_50]
0x180007007  mov     [rbp+200h+pExecInfo.nShow], eax
0x18000700a  test    r13b, 1
0x18000700e  jz      short loc_18000703E
0x180007010  xor     edx, edx; length
0x180007012  mov     rcx, [rsp+300h+var_2C8]
0x180007017  mov     rcx, [rcx+70h]; string
0x18000701b  call    cs:__imp_WindowsGetStringRawBuffer
0x180007021  mov     [rsp+300h+pv], rax
0x180007026  lea     rdx, [rsp+300h+pv]
0x18000702b  mov     rcx, r12
0x18000702e  call    ??$CentennialElevation@PEBG@Activation@DesktopAppXProvider@@QEAAX$$QEAPEBG@Z; DesktopAppXProvider::Activation::CentennialElevation<ushort const *>(ushort const * &&)
0x180007033  lea     rax, aRunas; "runas"
0x18000703a  mov     [rbp+200h+pExecInfo.lpVerb], rax
0x18000703e  xor     edi, edi
0x180007040  mov     [rsp+300h+var_288], rdi
0x180007045  test    rsi, rsi
0x180007048  jz      short loc_180007050
0x18000704a  mov     [rbp+200h+pExecInfo.lpDirectory], rsi
0x18000704e  jmp     short loc_180007097
0x180007050  mov     r8, r15
0x180007053  lea     rdx, [rsp+300h+pv]
0x180007058  call    ?GetWorkingDirectory@DesktopAppXActivator@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@@Z; DesktopAppXActivator::GetWorkingDirectory(HSTRING__ *)
0x18000705d  mov     rsi, rax
0x180007060  lea     rax, [rsp+300h+var_288]
0x180007065  cmp     rax, rsi
0x180007068  jz      short loc_180007083
0x18000706a  mov     rdx, [rsi]
0x18000706d  lea     rcx, [rsp+300h+var_288]
0x180007072  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180007077  mov     qword ptr [rsi], 0
0x18000707e  mov     rdi, [rsp+300h+var_288]
0x180007083  mov     rcx, [rsp+300h+pv]; pv
0x180007088  test    rcx, rcx
0x18000708b  jz      short loc_180007093
0x18000708d  call    cs:__imp_CoTaskMemFree
0x180007093  mov     [rbp+200h+pExecInfo.lpDirectory], rdi
0x180007097  mov     r15, [rsp+300h+var_2C8]
0x18000709c  mov     qword ptr [rsp+300h+var_2A8], r15
0x1800070a1  test    r15, r15
0x1800070a4  jz      short loc_1800070AF
0x1800070a6  lea     rcx, [r15+5Ch]; this
0x1800070aa  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1800070af  mov     [rbp+200h+var_1E8], r13d
0x1800070b3  mov     [rbp+200h+var_1E0], rbx
0x1800070b7  mov     [rbp+200h+var_1D8], r15
0x1800070bb  mov     [rbp+200h+var_1D0], 1
0x1800070bf  call    IsBeginAcquireStoreLicenseForPackageActivationPresent
0x1800070c4  test    al, al
0x1800070c6  jz      short loc_180007103
0x1800070c8  test    r13b, 40h
0x1800070cc  jnz     short loc_180007103
0x1800070ce  xor     edx, edx; length
0x1800070d0  mov     rcx, [rsp+300h+var_2C8]
0x1800070d5  mov     rcx, [rcx+70h]; string
0x1800070d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800070df  xor     r8d, r8d
0x1800070e2  mov     edx, 1
0x1800070e7  mov     rcx, rax
0x1800070ea  call    cs:__imp_BeginAcquireStoreLicenseForPackageActivation
0x1800070f0  mov     rcx, [rbp+208h]; this
0x1800070f7  test    eax, eax
0x1800070f9  jns     short loc_180007103
0x1800070fb  mov     r9d, eax; char *
0x1800070fe  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180007103  or      [rbp+200h+pExecInfo.fMask], 8800040h
0x18000710a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialActivationUsesShellExecuteNoHooksMask@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialActivationUsesShellExecuteNoHooksMask@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialActivationUsesShellExecuteNoHooksMask> `wil::Feature<__WilFeatureTraits_Feature_CentennialActivationUsesShellExecuteNoHooksMask>::GetImpl(void)'::`2'::impl
0x180007111  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialActivationUsesShellExecuteNoHooksMask@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialActivationUsesShellExecuteNoHooksMask>::__private_IsEnabled(void)
0x180007116  test    al, al
0x180007118  jz      short loc_180007121
0x18000711a  or      [rbp+200h+pExecInfo.fMask], 2000h
0x180007121  xor     edx, edx; length
0x180007123  mov     rcx, [rbp+200h+string]; string
0x180007127  call    cs:__imp_WindowsGetStringRawBuffer
0x18000712d  mov     [rbp+200h+pExecInfo.lpFile], rax
0x180007131  mov     [rbp+200h+pExecInfo.lpParameters], r14
0x180007135  mov     rcx, rbx; this
0x180007138  call    ?GetTargetMonitorFromSite@DesktopAppXActivator@@AEAAPEAUHMONITOR__@@XZ; DesktopAppXActivator::GetTargetMonitorFromSite(void)
0x18000713d  mov     rcx, rax
0x180007140  test    rax, rax
0x180007143  mov     eax, [rbp+200h+pExecInfo.fMask]
0x180007146  jz      short loc_180007153
0x180007148  bts     eax, 15h
0x18000714c  mov     [rbp+200h+pExecInfo.fMask], eax
0x18000714f  mov     qword ptr [rbp+200h+pExecInfo.60h], rcx
0x180007153  test    r13b, 8
0x180007157  jz      short loc_180007164
0x180007159  bts     eax, 0Ah
0x18000715d  mov     [rbp+200h+pExecInfo.fMask], eax
0x180007160  xor     esi, esi
0x180007162  jmp     short loc_1800071A7
0x180007164  xor     esi, esi
0x180007166  mov     [rsp+300h+pSessionId], esi
0x18000716a  call    cs:__imp_GetCurrentProcessId
0x180007170  mov     ecx, eax; dwProcessId
0x180007172  lea     rdx, [rsp+300h+pSessionId]; pSessionId
0x180007177  call    cs:__imp_ProcessIdToSessionId
0x18000717d  test    eax, eax
0x18000717f  jnz     short loc_18000719A
0x180007181  mov     rcx, [rbp+208h]; this
0x180007188  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x18000718f  mov     edx, 24Dh; void *
0x180007194  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000719a  cmp     [rsp+300h+pSessionId], esi
0x18000719e  jnz     short loc_1800071A7
0x1800071a0  or      [rbp+200h+pExecInfo.fMask], 400h
0x1800071a7  mov     rcx, rbx; this
0x1800071aa  call    ?GetLogUsageFromSite@DesktopAppXActivator@@AEAA_NXZ; DesktopAppXActivator::GetLogUsageFromSite(void)
0x1800071af  test    al, al
0x1800071b1  jz      short loc_1800071BA
0x1800071b3  or      [rbp+200h+pExecInfo.fMask], 4000000h
0x1800071ba  mov     r14, [rsp+300h+var_2C8]
0x1800071bf  lea     rcx, [rbx+8]
0x1800071c3  mov     [rsp+300h+var_2B8], rsi
0x1800071c8  mov     [rsp+300h+var_290], 80h
0x1800071d0  mov     rax, [rcx]
0x1800071d3  lea     r8, [rsp+300h+var_2B8]
0x1800071d8  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800071df  mov     rax, [rax+20h]
0x1800071e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e8  nop
0x1800071e9  mov     rbx, [rsp+300h+var_2B8]
0x1800071ee  test    rbx, rbx
0x1800071f1  jnz     loc_180007298
0x1800071f7  lea     rcx, [r14+10h]; SRWLock
0x1800071fb  call    cs:__imp_AcquireSRWLockExclusive
0x180007201  nop
0x180007202  mov     r15, [r14+20h]
0x180007206  xor     eax, eax
0x180007208  mov     [r14+20h], rax
0x18000720c  mov     rbx, r15
0x18000720f  mov     [rsp+300h+pv], rbx
0x180007214  mov     r13d, [r14+18h]
0x180007218  mov     [r14+18h], eax
0x18000721c  lea     rcx, [r14+10h]; SRWLock
0x180007220  call    cs:__imp_ReleaseSRWLockExclusive
0x180007226  test    r13d, r13d
0x180007229  jz      short loc_180007235
0x18000722b  mov     ecx, r13d; unsigned int
0x18000722e  call    ?Revoke@GlobalInterfaceTable@@SAXK@Z; GlobalInterfaceTable::Revoke(ulong)
0x180007233  jmp     short loc_180007251
0x180007235  test    r15, r15
0x180007238  jz      short loc_180007251
0x18000723a  xor     ebx, ebx
0x18000723c  mov     [rsp+300h+pv], rbx
0x180007241  mov     rax, [r15]
0x180007244  mov     rcx, r15
0x180007247  mov     rax, [rax+10h]
0x18000724b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007250  nop
0x180007251  xor     esi, esi
0x180007253  test    rbx, rbx
0x180007256  jz      short loc_180007268
0x180007258  mov     rax, [rbx]
0x18000725b  mov     rcx, rbx
0x18000725e  mov     rax, [rax+10h]
0x180007262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007267  nop
0x180007268  mov     r15, qword ptr [rsp+300h+var_2A8]
0x18000726d  mov     r13d, [rsp+300h+var_2C0]
0x180007272  xor     ebx, ebx
0x180007274  mov     rcx, [rbp+208h]; this
0x18000727b  test    esi, esi
0x18000727d  jns     loc_180007367
0x180007283  mov     r9d, esi; char *
0x180007286  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x18000728d  mov     edx, 25Bh; void *
0x180007292  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007298  mov     rcx, r14; struct IUnknown *
0x18000729b  call    ?IsAgile@@YA_NPEAUIUnknown@@@Z; IsAgile(IUnknown *)
0x1800072a0  test    al, al
0x1800072a2  jz      short loc_18000731D
0x1800072a4  mov     rcx, rbx; struct IUnknown *
0x1800072a7  call    ?IsAgile@@YA_NPEAUIUnknown@@@Z; IsAgile(IUnknown *)
0x1800072ac  test    al, al
0x1800072ae  jnz     short loc_18000731D
0x1800072b0  mov     [rsp+300h+pSessionId], esi
0x1800072b4  call    ?s_Retrieve@GlobalInterfaceTable@@CAJXZ; GlobalInterfaceTable::s_Retrieve(void)
0x1800072b9  mov     esi, eax
0x1800072bb  test    eax, eax
0x1800072bd  js      short loc_1800072E3
0x1800072bf  mov     rcx, cs:?s_pGlobalInterfaceTable@GlobalInterfaceTable@@0PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * GlobalInterfaceTable::s_pGlobalInterfaceTable
0x1800072c6  mov     rax, [rcx]
0x1800072c9  lea     r9, [rsp+300h+pSessionId]
0x1800072ce  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x1800072d5  mov     rdx, rbx
0x1800072d8  mov     rax, [rax+18h]
0x1800072dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e1  mov     esi, eax
0x1800072e3  test    esi, esi
0x1800072e5  js      short loc_180007272
0x1800072e7  lea     rcx, [r14+10h]; SRWLock
0x1800072eb  call    cs:__imp_AcquireSRWLockExclusive
0x1800072f1  mov     r13d, [r14+18h]
0x1800072f5  mov     eax, [rsp+300h+pSessionId]
0x1800072f9  mov     [r14+18h], eax
0x1800072fd  lea     rcx, [r14+10h]; SRWLock
0x180007301  call    cs:__imp_ReleaseSRWLockExclusive
0x180007307  test    r13d, r13d
0x18000730a  jz      loc_18000726D
0x180007310  mov     ecx, r13d; unsigned int
0x180007313  call    ?Revoke@GlobalInterfaceTable@@SAXK@Z; GlobalInterfaceTable::Revoke(ulong)
0x180007318  jmp     loc_18000726D
0x18000731d  lea     rcx, [r14+10h]; SRWLock
0x180007321  call    cs:__imp_AcquireSRWLockExclusive
0x180007327  cmp     [r14+20h], rbx
0x18000732b  jz      short loc_180007354
0x18000732d  mov     rax, [rbx]
0x180007330  mov     rcx, rbx
0x180007333  mov     rax, [rax+8]
0x180007337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000733c  nop
0x18000733d  mov     rax, [r14+20h]
0x180007341  mov     qword ptr [rsp+300h+var_2A8], rax
0x180007346  mov     [r14+20h], rbx
0x18000734a  lea     rcx, [rsp+300h+var_2A8]
0x18000734f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007354  lea     rcx, [r14+10h]; SRWLock
0x180007358  call    cs:__imp_ReleaseSRWLockExclusive
0x18000735e  xor     ebx, ebx
0x180007360  mov     esi, ebx
0x180007362  jmp     loc_180007274
0x180007367  mov     rcx, [rsp+300h+var_2B8]
0x18000736c  test    rcx, rcx
0x18000736f  jz      short loc_180007383
0x180007371  mov     [rsp+300h+var_2B8], rbx
0x180007376  mov     rax, [rcx]
0x180007379  mov     rax, [rax+10h]
0x18000737d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007382  nop
0x180007383  mov     eax, dword ptr [rsp+300h+var_2C8]
0x180007387  mov     dword ptr [rbp+200h+pExecInfo.hInstApp], eax
0x18000738a  mov     eax, dword ptr [rsp+300h+var_2C8+4]
0x18000738e  mov     dword ptr [rbp+200h+pExecInfo.hInstApp+4], eax
0x180007391  lea     rcx, [rbp+200h+var_1A0]; this
0x180007395  call    ??$Start@$$V@ActivationShellExec@DesktopAppXProvider@@SA?AV01@XZ; DesktopAppXProvider::ActivationShellExec::Start<>(void)
0x18000739a  nop
0x18000739b  lea     rcx, [rsp+300h+pv]
0x1800073a0  call    ??$GetActivationFactory@UIPackageStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(ushort const *)
0x1800073a5  nop
0x1800073a6  mov     [rsp+300h+var_2B8], rbx
0x1800073ab  mov     r14, [rsp+300h+pv]
0x1800073b0  mov     rax, [r14]
0x1800073b3  mov     qword ptr [rsp+300h+var_2A8], rax
0x1800073b8  lea     rcx, [rsp+300h+var_2B8]
0x1800073bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800073c2  xor     edx, edx; length
0x1800073c4  mov     rcx, [rsp+300h+var_2C8]
0x1800073c9  mov     rcx, [rcx+70h]; string
0x1800073cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800073d3  mov     rsi, rax
  ... truncated ...
```
