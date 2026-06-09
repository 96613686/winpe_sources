# CExec::ExecuteProcess(Schema::Process::ProcessParameters const &,void *,void *,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x140080ed8`
- end: `0x140081a6c`
- name: `?ExecuteProcess@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@PEAX11AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `2964`
- prototype: ``
- caller_count: `2`
- callee_count: `49`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400ac010`
- `0x140282704`

## callees

- `0x14001629c`
- `0x140017040`
- `0x14001d490`
- `0x140024030`
- `0x140024f6c`
- `0x1400421f0`
- `0x140042468`
- `0x140044974`
- `0x140075c9c`
- `0x140077dbc`
- `0x140080020`
- `0x140080180`
- `0x14008019c`
- `0x1400806a0`
- `0x140080750`
- `0x140080774`
- `0x1400807a0`
- `0x1400807cc`
- `0x1400807ec`
- `0x140080818`
- `0x140080848`
- `0x14008087c`
- `0x1400808a4`
- `0x140080d18`
- `0x140080e90`
- `0x140080eb0`
- `0x140080ed8`
- `0x140081a74`
- `0x140081b2c`
- `0x140081c1c`
- `0x140081ccc`
- `0x140082190`
- `0x140082278`
- `0x14008268c`
- `0x14008300c`
- `0x1400830c4`
- `0x1400ac560`
- `0x1400c40e0`
- `0x1400fe2c0`
- `0x1400fe710`
- `0x1401245e8`
- `0x1401332f0`
- `0x140133314`
- `0x140134048`
- `0x140281e58`
- `0x140282628`
- `0x1402828a8`
- `0x140285218`
- `0x14029e314`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400811ed`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400811ed`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400819c4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400819c4`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140081512`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14008156e`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400815bb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14008160a`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140081512`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14008156e`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400815bb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14008160a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1400817fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1400817fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008186f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008187e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008186f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008187e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140081965`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140081965`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400818a8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400818a8`
- `profapi!__imp_CreateEnvBlock` at `0x140081232`
- `profapi!__imp_CreateEnvBlock` at `0x140081232`
- `profapi!__imp_LoadProfileBasic` at `0x140081167`
- `profapi!__imp_LoadProfileBasic` at `0x140081167`
- `api-ms-win-core-console-internal-l1-1-0!CreatePseudoConsoleAsUser` at `0x14008136f`
- `api-ms-win-core-console-internal-l1-1-0!CreatePseudoConsoleAsUser` at `0x14008136f`

## string_xrefs

- `0x140081181`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140081204`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x14008124c`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140081389`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140081529`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140081585`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400815d2`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140081621`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140081811`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400818bf`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140081654`: `CreateProcessAsUserW`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
_QWORD *__fastcall CExec::ExecuteProcess(
        _QWORD *a1,
        __int64 a2,
        void *a3,
        void *a4,
        HANDLE hSourceHandle,
        ConsoleToPipeRedirector *a6,
        __int64 a7)
{
  int v10; // r8d
  const wchar_t *v11; // rcx
  wchar_t *v12; // rax
  const wchar_t *v13; // rax
  WCHAR *v14; // r14
  WCHAR *v15; // rax
  char v16; // r15
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int16 v19; // r13
  int ProfileBasic; // eax
  HANDLE v21; // r12
  const char *v22; // r9
  int v23; // eax
  ConsoleToPipeRedirector *v24; // r8
  __int64 v25; // rax
  bool v26; // r12
  ConsoleToPipeRedirector *v27; // r15
  HANDLE v28; // r13
  int PseudoConsoleAsUser; // eax
  __int64 Console; // rbx
  void *v31; // rbx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v32; // rcx
  const char *v33; // r9
  const char *v34; // r9
  const char *v35; // r9
  const char *v36; // r9
  const unsigned __int16 *v37; // rdx
  const wchar_t *lpCurrentDirectory; // rdi
  const wchar_t *v39; // rcx
  LPCWSTR v40; // rdx
  __int64 ApplicationName; // rbx
  _QWORD *lpEnvironment; // rax
  const char *v43; // r9
  HANDLE hProcess; // rbx
  _QWORD *v45; // r14
  HANDLE *v46; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE v48; // rax
  const char *v49; // r9
  __int64 v50; // rax
  struct _PROCESS_INFORMATION *v51; // rdx
  LPPROC_THREAD_ATTRIBUTE_LIST v52; // rcx
  int cbSize; // [rsp+20h] [rbp-E0h]
  char v55; // [rsp+60h] [rbp-A0h]
  __int16 v56; // [rsp+64h] [rbp-9Ch]
  __int64 v57; // [rsp+70h] [rbp-90h] BYREF
  int v58[2]; // [rsp+78h] [rbp-88h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v61[2]; // [rsp+98h] [rbp-68h] BYREF
  char v62; // [rsp+A9h] [rbp-57h]
  __int64 v63; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v66; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v67; // [rsp+D0h] [rbp-30h]
  _BYTE Src[32]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v69; // [rsp+F8h] [rbp-8h]
  WCHAR v70[32]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v71; // [rsp+140h] [rbp+40h] BYREF
  __int64 v72; // [rsp+148h] [rbp+48h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+150h] [rbp+50h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+170h] [rbp+70h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v75; // [rsp+1D8h] [rbp+D8h]
  HANDLE hToken; // [rsp+1E0h] [rbp+E0h] BYREF
  HANDLE v77; // [rsp+1E8h] [rbp+E8h] BYREF
  ConsoleToPipeRedirector *v78; // [rsp+1F0h] [rbp+F0h] BYREF
  HANDLE v79; // [rsp+1F8h] [rbp+F8h] BYREF
  PVOID lpValue; // [rsp+200h] [rbp+100h] BYREF
  HANDLE TargetHandle; // [rsp+208h] [rbp+108h] BYREF
  HANDLE v82; // [rsp+210h] [rbp+110h] BYREF
  HANDLE v83; // [rsp+218h] [rbp+118h] BYREF
  LPVOID v84; // [rsp+220h] [rbp+120h] BYREF
  __int128 v85; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v86[5]; // [rsp+238h] [rbp+138h] BYREF
  LPCWSTR lpApplicationName[4]; // [rsp+260h] [rbp+160h] BYREF
  _QWORD v88[4]; // [rsp+280h] [rbp+180h] BYREF
  _QWORD v89[42]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _QWORD v90[42]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _QWORD Value[3]; // [rsp+540h] [rbp+440h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  v66 = a1;
  v69 = a1;
  v78 = a6;
  v72 = a7;
  memset_0(v90, 0, sizeof(v90));
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v90);
  v90[0] = &CExec::Diagnostics::TraceProvider::ExecuteProcess::`vftable';
  CExec::Diagnostics::TraceProvider::ExecuteProcess::StartActivity((CExec::Diagnostics::TraceProvider::ExecuteProcess *)v90);
  v11 = L"pipe";
  v12 = L"pipe";
  if ( !hSourceHandle )
    v12 = L"<n/a>";
  v77 = v12;
  v13 = L"pipe";
  if ( !a4 )
    v13 = L"<n/a>";
  v79 = (HANDLE)v13;
  if ( !a3 )
    v11 = L"<n/a>";
  *(_QWORD *)v58 = v11;
  v14 = (WCHAR *)(a2 + 32);
  if ( *(_QWORD *)(a2 + 56) <= 7u )
    v15 = (WCHAR *)(a2 + 32);
  else
    v15 = *(WCHAR **)v14;
  v57 = (__int64)v15;
  VmEventWrite<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
    (_DWORD)v11,
    (unsigned int)L"<n/a>",
    v10,
    (unsigned int)&v57,
    (__int64)v58,
    (__int64)&v79,
    (__int64)&v77);
  v16 = *(_BYTE *)(a2 + 169);
  v55 = v16;
  TargetHandle = 0;
  CExec::ConnectStdDevicePipe(&TargetHandle, a3);
  v82 = 0;
  CExec::ConnectStdDevicePipe(&v82, a4);
  v83 = 0;
  CExec::ConnectStdDevicePipe(&v83, hSourceHandle);
  v63 = -1;
  v64 = -1;
  v65 = -1;
  v17 = -1;
  *(_QWORD *)v58 = -1;
  v18 = -1;
  v57 = -1;
  if ( v16 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      v58,
      &TargetHandle);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v57,
      &v82);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v83,
      -1);
    v17 = *(_QWORD *)v58;
    v18 = v57;
  }
  if ( *(_WORD *)(a2 + 174) )
    v56 = *(_WORD *)(a2 + 174);
  else
    v56 = 25;
  if ( *(_WORD *)(a2 + 176) )
    v19 = *(_WORD *)(a2 + 176);
  else
    v19 = 80;
  v79 = 0;
  hToken = 0;
  CExec::GetProcessToken(&hToken, a2);
  memset_0(v89, 0, sizeof(v89));
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v89);
  v89[0] = &CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable';
  CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StartActivity((CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile *)v89);
  ProfileBasic = LoadProfileBasic(hToken, 0);
  if ( ProfileBasic < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35D,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)(unsigned int)ProfileBasic,
      cbSize);
  v21 = hToken;
  v77 = hToken;
  hToken = 0;
  v79 = v77;
  v61[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CExec::UnloadAndClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CExec::UnloadAndClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v61);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v89);
  CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::~ExecuteProcess_LoadProfile((CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile *)v89);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  if ( !ImpersonateLoggedOnUser(v21) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v22);
  v62 = 1;
  v84 = 0;
  v23 = CreateEnvBlock(&v84, v21, 0);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x366,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)(unsigned int)v23,
      cbSize);
  std::wstring::wstring(v86);
  v85 = 0;
  CExec::EnvironmentBlockToMap(&v85, v84);
  v24 = v78;
  if ( *(_QWORD *)(a2 + 160) || *((_QWORD *)v78 + 2) )
  {
    CExec::UpdateEnvironmentMap(&v85, a2 + 152, v78);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
      &si128,
      &v85);
    v25 = CExec::EnvironmentMapToBlock(Src);
    std::wstring::operator=(v86, v25);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)Src);
  }
  v26 = v16 && (!*(_BYTE *)(a2 + 181) || !*(_BYTE *)(a2 + 180));
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v27 = 0;
  v78 = 0;
  lpValue = 0;
  if ( v26 )
  {
    LOWORD(hToken) = v19;
    WORD1(hToken) = v56;
    lpValue = 0;
    v28 = v77;
    PseudoConsoleAsUser = CreatePseudoConsoleAsUser(v77, (unsigned int)hToken, v17, v18);
    if ( PseudoConsoleAsUser < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x384,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        (const char *)(unsigned int)PseudoConsoleAsUser,
        0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v58,
      -1);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v57,
      -1);
  }
  else
  {
    Console = CreateConsole(v61, 0, v24);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &si128,
      Console);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &si128.m128i_u64[1],
      Console + 8);
    ConsoleDriverHandles::~ConsoleDriverHandles((ConsoleDriverHandles *)v61);
    v31 = operator new(0x180u);
    v61[0] = v31;
    memset_0(v31, 0, 0x180u);
    v27 = (ConsoleToPipeRedirector *)ConsoleToPipeRedirector::ConsoleToPipeRedirector(v31, v56, v19, v56, v19);
    v61[0] = 0;
    v78 = v27;
    std::unique_ptr<ConsoleToPipeRedirector>::~unique_ptr<ConsoleToPipeRedirector>(v61);
    v28 = v77;
  }
  *(_QWORD *)&StartupInfo.cb = 112;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  v75 = 0;
  CExec::MakeAttributeList(&lpAttributeList);
  v32 = lpAttributeList;
  v75 = lpAttributeList;
  Value[0] = TargetHandle;
  Value[1] = v82;
  Value[2] = v83;
  StartupInfo.dwFlags |= 0x100u;
  if ( !v55 )
  {
    StartupInfo.hStdInput = TargetHandle;
    StartupInfo.hStdOutput = v82;
    StartupInfo.hStdError = v83;
    if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, Value, 0x18u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3AE,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v33);
    v32 = lpAttributeList;
  }
  if ( v26 )
  {
    v71 = 0;
    if ( !UpdateProcThreadAttribute(v32, 0, 0x20016u, lpValue, 8u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3BB,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v34);
  }
  else
  {
    v71 = si128.m128i_i64[1];
    if ( !UpdateProcThreadAttribute(v32, 0, 0x2000Au, &v71, 8u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3C6,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v35);
  }
  if ( v72 != -1 && !UpdateProcThreadAttribute(lpAttributeList, 0, 0x2000Du, &v72, 8u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v36);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(v89, 0, sizeof(v89));
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v89);
  v89[0] = &CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::`vftable';
  CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StartActivity((CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *)v89);
  lpCurrentDirectory = (const wchar_t *)(a2 + 120);
  if ( *(_QWORD *)(a2 + 136) )
  {
    if ( *(_QWORD *)(a2 + 144) <= 7u )
      v39 = (const wchar_t *)(a2 + 120);
    else
      v39 = *(const wchar_t **)lpCurrentDirectory;
    CommonUtilities::CreateDirectoryW(v39, v37);
  }
  Schema::Containers::Definition::NamedPipeSymlink::NamedPipeSymlink((Schema::Containers::Definition::NamedPipeSymlink *)lpApplicationName);
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v40 = (LPCWSTR)a2;
  else
    v40 = *(LPCWSTR *)a2;
  if ( *(_QWORD *)(a2 + 56) > 7u )
    v14 = *(WCHAR **)v14;
  if ( !*v40 )
  {
    std::wstring::wstring(Src, L"PATH");
    std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring,>(
      &v85,
      v61,
      Src);
    lpCurrentDirectory = (const wchar_t *)(a2 + 120);
    ApplicationName = GetApplicationName(v70, (int)a2 + 32);
    std::wstring::operator=(lpApplicationName, ApplicationName);
    std::wstring::operator=(v88, ApplicationName + 32);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)v70);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)Src);
    v40 = (LPCWSTR)lpApplicationName;
    if ( lpApplicationName[3] > (LPCWSTR)7 )
      v40 = lpApplicationName[0];
    if ( v88[2] )
    {
      v14 = (WCHAR *)v88;
      if ( v88[3] > 7u )
        v14 = (WCHAR *)v88[0];
    }
  }
  if ( *(_QWORD *)(a2 + 136) )
  {
    if ( *((_QWORD *)lpCurrentDirectory + 3) > 7u )
      lpCurrentDirectory = *(const wchar_t **)lpCurrentDirectory;
  }
  else
  {
    lpCurrentDirectory = 0;
  }
  if ( v86[2] )
  {
    lpEnvironment = v86;
    if ( v86[3] > 7u )
      lpEnvironment = (_QWORD *)v86[0];
  }
  else
  {
    lpEnvironment = v84;
  }
  if ( !CreateProcessAsUserW(
          v28,
          v40,
          v14,
          0,
          0,
          1,
          0x80400u,
          lpEnvironment,
          lpCurrentDirectory,
          &StartupInfo,
          &ProcessInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F7,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v43);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v89);
  std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)lpApplicationName);
  CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::~CreateProcessAsUserW((CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *)v89);
  hProcess = ProcessInformation.hProcess;
  v77 = ProcessInformation.hProcess;
  ProcessInformation.hProcess = 0;
  v45 = v66;
  *v66 = 0;
  v46 = (HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(v45);
  CurrentProcess = GetCurrentProcess();
  v48 = GetCurrentProcess();
  if ( !DuplicateHandle(v48, hProcess, CurrentProcess, v46, 0x101041u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x405,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v49);
  if ( v27 )
  {
    CspReadNextConsoleIo(*(_QWORD *)v27);
    ConsoleToPipeRedirector::StartRead(v27);
  }
  v50 = std::make_shared<CExec::ProcessTracker,unsigned long &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::unique_ptr<ConsoleToPipeRedirector>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ClosePseudoConsole(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CExec::UnloadAndClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
          (unsigned int)&v66,
          (unsigned int)&ProcessInformation.dwProcessId,
          (unsigned int)&v77,
          (unsigned int)&v78,
          (__int64)&lpValue,
          (__int64)&v79);
  CExec::TrackProcess(ProcessInformation.dwProcessId, v50);
  if ( v67 )
    std::_Ref_count_base::_Decref(v67);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v90);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v77);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v51);
  v52 = lpAttributeList;
  lpAttributeList = 0;
  if ( v52 )
    LocalFree(v52);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ClosePseudoConsole(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ClosePseudoConsole(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpValue);
  std::unique_ptr<ConsoleToPipeRedirector>::~unique_ptr<ConsoleToPipeRedirector>(&v78);
  ConsoleDriverHandles::~ConsoleDriverHandles((ConsoleDriverHandles *)&si128);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    &v85,
    &v85);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v86);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v84);
  RevertToSelf();
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CExec::UnloadAndClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CExec::UnloadAndClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v79);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v57);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v58);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v65);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v64);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v63);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v83);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v82);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
  CExec::Diagnostics::TraceProvider::ExecuteProcess::~ExecuteProcess((CExec::Diagnostics::TraceProvider::ExecuteProcess *)v90);
  return v45;
}

```

## disassembly

```asm
0x140080ed8  push    rbp
0x140080eda  push    rbx
0x140080edb  push    rsi
0x140080edc  push    rdi
0x140080edd  push    r12
0x140080edf  push    r13
0x140080ee1  push    r14
0x140080ee3  push    r15
0x140080ee5  lea     rbp, [rsp-468h]
0x140080eed  sub     rsp, 568h
0x140080ef4  mov     rax, cs:__security_cookie
0x140080efb  xor     rax, rsp
0x140080efe  mov     [rbp+4A0h+var_48], rax
0x140080f05  mov     rdi, r9
0x140080f08  mov     rbx, r8
0x140080f0b  mov     rsi, rdx
0x140080f0e  mov     [rbp+4A0h+var_4D8], rcx
0x140080f12  mov     [rbp+4A0h+var_4A8], rcx
0x140080f16  mov     r12, [rbp+4A0h+hSourceHandle]
0x140080f1d  mov     rax, [rbp+4A0h+arg_28]
0x140080f24  mov     [rbp+4A0h+var_3B0], rax
0x140080f2b  mov     rax, [rbp+4A0h+arg_30]
0x140080f32  mov     [rbp+4A0h+var_458], rax
0x140080f36  xor     r13d, r13d
0x140080f39  mov     [rsp+5A0h+var_538], r13d
0x140080f3e  xor     edx, edx; Val
0x140080f40  mov     r8d, 150h; Size
0x140080f46  lea     rcx, [rbp+4A0h+var_1B0]; void *
0x140080f4d  call    memset_0
0x140080f52  lea     rdx, aExecuteprocess_0; "ExecuteProcess"
0x140080f59  lea     rcx, [rbp+4A0h+var_1B0]; struct wil::details::IFailureCallback *
0x140080f60  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140080f65  lea     rax, ??_7ExecuteProcess@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::ExecuteProcess::`vftable'
0x140080f6c  mov     [rbp+4A0h+var_1B0], rax
0x140080f73  lea     rcx, [rbp+4A0h+var_1B0]; this
0x140080f7a  call    ?StartActivity@ExecuteProcess@TraceProvider@Diagnostics@CExec@@QEAAXXZ; CExec::Diagnostics::TraceProvider::ExecuteProcess::StartActivity(void)
0x140080f7f  nop
0x140080f80  lea     rdx, aNA; "<n/a>"
0x140080f87  lea     rcx, aPipe_1; "pipe"
0x140080f8e  mov     rax, rcx
0x140080f91  test    r12, r12
0x140080f94  cmovz   rax, rdx
0x140080f98  mov     [rbp+4A0h+var_3B8], rax
0x140080f9f  mov     rax, rcx
0x140080fa2  test    rdi, rdi
0x140080fa5  cmovz   rax, rdx
0x140080fa9  mov     [rbp+4A0h+var_3A8], rax
0x140080fb0  test    rbx, rbx
0x140080fb3  cmovz   rcx, rdx
0x140080fb7  mov     qword ptr [rsp+5A0h+var_528], rcx
0x140080fbc  lea     r14, [rsi+20h]
0x140080fc0  cmp     qword ptr [r14+18h], 7
0x140080fc5  jbe     short loc_140080FCC
0x140080fc7  mov     rax, [r14]
0x140080fca  jmp     short loc_140080FCF
0x140080fcc  mov     rax, r14
0x140080fcf  mov     [rsp+5A0h+var_530], rax
0x140080fd4  lea     rax, [rbp+4A0h+var_3B8]
0x140080fdb  mov     [rsp+5A0h+lpReturnSize], rax
0x140080fe0  lea     rax, [rbp+4A0h+var_3A8]
0x140080fe7  mov     [rsp+5A0h+lpPreviousValue], rax
0x140080fec  lea     rax, [rsp+5A0h+var_528]
0x140080ff1  mov     [rsp+5A0h+cbSize], rax; int
0x140080ff6  lea     r9, [rsp+5A0h+var_530]
0x140080ffb  call    ??$VmEventWrite@PEBGPEBGPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG222@Z; VmEventWrite<ushort const *,ushort const *,ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &&)
0x140081000  mov     r15b, [rsi+0A9h]
0x140081007  mov     [rsp+5A0h+var_540], r15b
0x14008100c  mov     [rbp+4A0h+TargetHandle], r13
0x140081013  mov     r9b, r15b
0x140081016  mov     r8b, 1
0x140081019  mov     rdx, rbx; hSourceHandle
0x14008101c  lea     rcx, [rbp+4A0h+TargetHandle]; lpTargetHandle
0x140081023  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x140081028  nop
0x140081029  mov     [rbp+4A0h+var_390], r13
0x140081030  mov     r9b, r15b
0x140081033  xor     r8d, r8d
0x140081036  mov     rdx, rdi; hSourceHandle
0x140081039  lea     rcx, [rbp+4A0h+var_390]; lpTargetHandle
0x140081040  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x140081045  nop
0x140081046  mov     [rbp+4A0h+var_388], r13
0x14008104d  mov     r9b, r15b
0x140081050  xor     r8d, r8d
0x140081053  mov     rdx, r12; hSourceHandle
0x140081056  lea     rcx, [rbp+4A0h+var_388]; lpTargetHandle
0x14008105d  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x140081062  nop
0x140081063  or      r12, 0FFFFFFFFFFFFFFFFh
0x140081067  mov     [rbp+4A0h+var_4F0], r12
0x14008106b  mov     [rbp+4A0h+var_4E8], r12
0x14008106f  mov     [rbp+4A0h+var_4E0], r12
0x140081073  mov     rbx, r12
0x140081076  mov     qword ptr [rsp+5A0h+var_528], rbx
0x14008107b  mov     rdi, r12
0x14008107e  mov     [rsp+5A0h+var_530], r12
0x140081083  test    r15b, r15b
0x140081086  jz      short loc_1400810C3
0x140081088  lea     rdx, [rbp+4A0h+TargetHandle]
0x14008108f  lea     rcx, [rsp+5A0h+var_528]
0x140081094  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140081099  lea     rdx, [rbp+4A0h+var_390]
0x1400810a0  lea     rcx, [rsp+5A0h+var_530]
0x1400810a5  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400810aa  mov     rdx, r12
0x1400810ad  lea     rcx, [rbp+4A0h+var_388]
0x1400810b4  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400810b9  mov     rbx, qword ptr [rsp+5A0h+var_528]
0x1400810be  mov     rdi, [rsp+5A0h+var_530]
0x1400810c3  movzx   eax, word ptr [rsi+0AEh]
0x1400810ca  test    ax, ax
0x1400810cd  jnz     short loc_1400810D9
0x1400810cf  mov     dword ptr [rsp+5A0h+var_53C], 19h
0x1400810d7  jmp     short loc_1400810DE
0x1400810d9  mov     [rsp+5A0h+var_53C], ax
0x1400810de  movzx   eax, word ptr [rsi+0B0h]
0x1400810e5  test    ax, ax
0x1400810e8  jnz     short loc_1400810F2
0x1400810ea  mov     r13d, 50h ; 'P'
0x1400810f0  jmp     short loc_1400810F6
0x1400810f2  movzx   r13d, ax
0x1400810f6  mov     [rbp+4A0h+var_3A8], 0
0x140081101  mov     [rbp+4A0h+hToken], 0
0x14008110c  mov     rdx, rsi
0x14008110f  lea     rcx, [rbp+4A0h+hToken]
0x140081116  call    ?GetProcessToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@@Z; CExec::GetProcessToken(Schema::Process::ProcessParameters const &)
0x14008111b  nop
0x14008111c  xor     edx, edx; Val
0x14008111e  mov     r8d, 150h; Size
0x140081124  lea     rcx, [rbp+4A0h+var_300]; void *
0x14008112b  call    memset_0
0x140081130  lea     rdx, aExecuteprocess; "ExecuteProcess_LoadProfile"
0x140081137  lea     rcx, [rbp+4A0h+var_300]; struct wil::details::IFailureCallback *
0x14008113e  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140081143  lea     rax, ??_7ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable'
0x14008114a  mov     [rbp+4A0h+var_300], rax
0x140081151  lea     rcx, [rbp+4A0h+var_300]; this
0x140081158  call    ?StartActivity@ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@QEAAXXZ; CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StartActivity(void)
0x14008115d  nop
0x14008115e  xor     edx, edx
0x140081160  mov     rcx, [rbp+4A0h+hToken]
0x140081167  call    cs:__imp_LoadProfileBasic
0x14008116e  nop     dword ptr [rax+rax+00h]
0x140081173  mov     rcx, [rbp+4A8h]; this
0x14008117a  test    eax, eax
0x14008117c  jns     short loc_140081193
0x14008117e  mov     r9d, eax; char *
0x140081181  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140081188  mov     edx, 35Dh; void *
0x14008118d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140081193  mov     r12, [rbp+4A0h+hToken]
0x14008119a  mov     [rbp+4A0h+var_3B8], r12
0x1400811a1  mov     [rbp+4A0h+hToken], 0
0x1400811ac  mov     [rbp+4A0h+var_3A8], r12
0x1400811b3  mov     [rbp+4A0h+var_508], 0
0x1400811bb  lea     rcx, [rbp+4A0h+var_508]
0x1400811bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnloadAndClose@CExec@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CExec::UnloadAndClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CExec::UnloadAndClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400811c4  lea     rcx, [rbp+4A0h+var_300]
0x1400811cb  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400811d0  nop
0x1400811d1  lea     rcx, [rbp+4A0h+var_300]; this
0x1400811d8  call    ??1ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@QEAA@XZ; CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::~ExecuteProcess_LoadProfile(void)
0x1400811dd  nop
0x1400811de  lea     rcx, [rbp+4A0h+hToken]; void *
0x1400811e5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400811ea  mov     rcx, r12; hToken
0x1400811ed  call    cs:__imp_ImpersonateLoggedOnUser
0x1400811f4  nop     dword ptr [rax+rax+00h]
0x1400811f9  mov     rcx, [rbp+4A8h]; this
0x140081200  test    eax, eax
0x140081202  jnz     short loc_140081216
0x140081204  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14008120b  mov     edx, 362h; void *
0x140081210  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140081216  mov     [rbp+4A0h+var_4F7], 1
0x14008121a  mov     [rbp+4A0h+var_380], 0
0x140081225  xor     r8d, r8d
0x140081228  mov     rdx, r12
0x14008122b  lea     rcx, [rbp+4A0h+var_380]
0x140081232  call    cs:__imp_CreateEnvBlock
0x140081239  nop     dword ptr [rax+rax+00h]
0x14008123e  mov     rcx, [rbp+4A8h]; this
0x140081245  test    eax, eax
0x140081247  jns     short loc_14008125E
0x140081249  mov     r9d, eax; char *
0x14008124c  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140081253  mov     edx, 366h; void *
0x140081258  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008125e  lea     rcx, [rbp+4A0h+var_368]; void *
0x140081265  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14008126a  nop
0x14008126b  xorps   xmm0, xmm0
0x14008126e  movups  [rbp+4A0h+var_378], xmm0
0x140081275  mov     rdx, [rbp+4A0h+var_380]
0x14008127c  lea     rcx, [rbp+4A0h+var_378]
0x140081283  call    ?EnvironmentBlockToMap@CExec@@YA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBG@Z; CExec::EnvironmentBlockToMap(ushort const *)
0x140081288  nop
0x140081289  xor     edx, edx
0x14008128b  mov     r8, [rbp+4A0h+var_3B0]
0x140081292  cmp     [rsi+0A0h], rdx
0x140081299  jnz     short loc_1400812A1
0x14008129b  cmp     [r8+10h], rdx
0x14008129f  jz      short loc_1400812EB
0x1400812a1  lea     rdx, [rsi+98h]
0x1400812a8  lea     rcx, [rbp+4A0h+var_378]
0x1400812af  call    ?UpdateEnvironmentMap@CExec@@YAXAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; CExec::UpdateEnvironmentMap(std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>> &,std::map<std::wstring,std::wstring> const &,std::wstring const &)
0x1400812b4  lea     rdx, [rbp+4A0h+var_378]
0x1400812bb  lea     rcx, [rbp+4A0h+var_518]
0x1400812bf  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &&)
0x1400812c4  lea     rdx, [rbp+4A0h+var_518]
0x1400812c8  lea     rcx, [rbp+4A0h+Src]; Src
0x1400812cc  call    ?EnvironmentMapToBlock@CExec@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; CExec::EnvironmentMapToBlock(std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>)
0x1400812d1  mov     rdx, rax
0x1400812d4  lea     rcx, [rbp+4A0h+var_368]
0x1400812db  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400812e0  lea     rcx, [rbp+4A0h+Src]; this
0x1400812e4  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400812e9  xor     edx, edx
0x1400812eb  test    r15b, r15b
0x1400812ee  jz      short loc_140081305
0x1400812f0  cmp     [rsi+0B5h], dl
0x1400812f6  jz      short loc_140081300
0x1400812f8  cmp     [rsi+0B4h], dl
0x1400812fe  jnz     short loc_140081305
0x140081300  mov     r12b, 1
0x140081303  jmp     short loc_140081308
0x140081305  mov     r12b, dl
0x140081308  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140081310  movdqu  [rbp+4A0h+var_518], xmm0
0x140081315  mov     r15, rdx
0x140081318  mov     [rbp+4A0h+var_3B0], rdx
0x14008131f  mov     [rbp+4A0h+lpValue], rdx
0x140081326  test    r12b, r12b
0x140081329  jz      loc_1400813BC
0x14008132f  mov     word ptr [rbp+4A0h+hToken], r13w
0x140081337  mov     eax, dword ptr [rsp+5A0h+var_53C]
0x14008133b  mov     word ptr [rbp+4A0h+hToken+2], ax
0x140081342  mov     [rbp+4A0h+lpValue], rdx
0x140081349  lea     rax, [rbp+4A0h+lpValue]
0x140081350  mov     [rsp+5A0h+lpPreviousValue], rax
0x140081355  mov     dword ptr [rsp+5A0h+cbSize], edx; int
0x140081359  mov     r9, rdi
0x14008135c  mov     r8, rbx
0x14008135f  mov     edx, dword ptr [rbp+4A0h+hToken]
0x140081365  mov     r13, [rbp+4A0h+var_3B8]
0x14008136c  mov     rcx, r13
0x14008136f  call    cs:__imp_CreatePseudoConsoleAsUser
0x140081376  nop     dword ptr [rax+rax+00h]
0x14008137b  mov     rcx, [rbp+4A8h]; this
0x140081382  test    eax, eax
0x140081384  jns     short loc_14008139B
0x140081386  mov     r9d, eax; char *
0x140081389  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140081390  mov     edx, 384h; void *
0x140081395  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008139b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14008139f  lea     rcx, [rsp+5A0h+var_528]
0x1400813a4  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400813a9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400813ad  lea     rcx, [rsp+5A0h+var_530]
0x1400813b2  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400813b7  jmp     loc_140081465
0x1400813bc  lea     rcx, [rbp+4A0h+var_508]
0x1400813c0  call    ?CreateConsole@@YA?AUConsoleDriverHandles@@XZ; CreateConsole(void)
0x1400813c5  mov     rbx, rax
0x1400813c8  mov     rdx, rax
0x1400813cb  lea     rcx, [rbp+4A0h+var_518]
0x1400813cf  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400813d4  lea     rdx, [rbx+8]
0x1400813d8  lea     rcx, [rbp+4A0h+var_518+8]
0x1400813dc  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400813e1  lea     rcx, [rbp+4A0h+var_508]; this
0x1400813e5  call    ??1ConsoleDriverHandles@@QEAA@XZ; ConsoleDriverHandles::~ConsoleDriverHandles(void)
0x1400813ea  mov     edi, 180h
0x1400813ef  mov     ecx, edi; Size
0x1400813f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400813f6  mov     rbx, rax
0x1400813f9  mov     [rbp+4A0h+var_508], rax
0x1400813fd  mov     r8d, edi; Size
0x140081400  xor     edx, edx; Val
0x140081402  mov     rcx, rax; void *
0x140081405  call    memset_0
0x14008140a  mov     word ptr [rsp+5A0h+lpEnvironment], r13w; __int16
0x140081410  mov     eax, dword ptr [rsp+5A0h+var_53C]
0x140081414  mov     word ptr [rsp+5A0h+lpReturnSize], ax; __int16
0x140081419  mov     word ptr [rsp+5A0h+lpPreviousValue], r13w; __int16
0x14008141f  mov     word ptr [rsp+5A0h+cbSize], ax; __int16
0x140081424  lea     r9, [rsp+5A0h+var_530]
0x140081429  lea     r8, [rsp+5A0h+var_528]
0x14008142e  lea     rdx, [rbp+4A0h+var_518]
0x140081432  mov     rcx, rbx; pv
0x140081435  call    ??0ConsoleToPipeRedirector@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@00GGGG@Z; ConsoleToPipeRedirector::ConsoleToPipeRedirector(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ushort,ushort,ushort,ushort)
0x14008143a  mov     r15, rax
0x14008143d  mov     eax, 2
0x140081442  mov     [rsp+5A0h+var_538], eax
0x140081446  mov     [rbp+4A0h+var_508], 0
0x14008144e  mov     [rbp+4A0h+var_3B0], r15
0x140081455  lea     rcx, [rbp+4A0h+var_508]
0x140081459  call    ??1?$unique_ptr@VConsoleToPipeRedirector@@U?$default_delete@VConsoleToPipeRedirector@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConsoleToPipeRedirector>::~unique_ptr<ConsoleToPipeRedirector>(void)
0x14008145e  mov     r13, [rbp+4A0h+var_3B8]
  ... truncated ...
```
