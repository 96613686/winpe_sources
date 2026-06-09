# Microsoft::Diagnostics::RunExeHelperDef::RunExecutable(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::ScenarioInst const &,Microsoft::Diagnostics::EscalationWorkItemState &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,bool,unsigned __int64 *)

- ea: `0x18030ce0c`
- end: `0x18030f767`
- name: `?RunExecutable@RunExeHelperDef@Diagnostics@Microsoft@@IEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVScenarioInst@23@AEAVEscalationWorkItemState@23@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@_NPEA_K@Z`
- size: `10587`
- prototype: `__int64 __fastcall(int, int, int, int, Microsoft::Diagnostics::ScenarioDef::EscalationProperties *, int, PULONG64 CycleTime)`
- caller_count: `1`
- callee_count: `57`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ad1a0`

## callees

- `0x180001bf4`
- `0x180003a00`
- `0x180004a24`
- `0x18000cae8`
- `0x18001d160`
- `0x18001d200`
- `0x18001d5ac`
- `0x18001e638`
- `0x18001ee94`
- `0x180020fbc`
- `0x180026ecc`
- `0x180030a50`
- `0x1800333b0`
- `0x180034d94`
- `0x180035698`
- `0x180048ff4`
- `0x180049380`
- `0x1800498f0`
- `0x18004be40`
- `0x180053a84`
- `0x180054ca4`
- `0x18005b050`
- `0x18005b974`
- `0x18005d050`
- `0x18007fae8`
- `0x180080054`
- `0x1800827b8`
- `0x180082b70`
- `0x180089d90`
- `0x18008bd1c`
- `0x18009c900`
- `0x18009db28`
- `0x1800a1e24`
- `0x1800a5324`
- `0x1800a6020`
- `0x1800a60e4`
- `0x1800a8324`
- `0x1800a8e5c`
- `0x1800a9250`
- `0x1800a9344`
- `0x1800b1a08`
- `0x1800d0d7c`
- `0x1800d0d9c`
- `0x1800d6620`
- `0x180108864`
- `0x18012de40`
- `0x18012eb08`
- `0x180170014`
- `0x180172d70`
- `0x180173510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18030e8cd`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18030e8cd`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18030e77d`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18030e77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18030d232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18030e1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18030e5ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18030d232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18030e1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18030e5ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18030d200`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18030d200`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18030e5ae`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18030e5ae`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18030cf30`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18030d030`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18030cf30`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18030d030`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18030d21c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18030d21c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18030d0fd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18030d0fd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18030efe4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18030efe4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18030e9d4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18030e9d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18030e1ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18030e1ce`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030ec36`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030eef2`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030f032`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030f3db`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030f5b5`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030ec36`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030eef2`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030f032`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030f3db`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18030f5b5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18030ea62`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18030ea62`
- `USERENV!DestroyEnvironmentBlock` at `0x18030d590`
- `USERENV!DestroyEnvironmentBlock` at `0x18030f69a`
- `USERENV!DestroyEnvironmentBlock` at `0x18030d590`
- `USERENV!DestroyEnvironmentBlock` at `0x18030f69a`
- `USERENV!CreateEnvironmentBlock` at `0x18030d412`
- `USERENV!CreateEnvironmentBlock` at `0x18030d412`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18030d376`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18030d376`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18030e023`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18030e023`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18030e58f`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18030e58f`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18030ea9a`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18030ed22`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18030f11f`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18030ea9a`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18030ed22`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18030f11f`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18030deef`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18030deef`

## string_xrefs

- `0x18030d785`: `ExpandedCommandLine`
- `0x18030dd53`: `Action is running as SYSTEM and targets %temp%.  Redirecting to UTC temp path.\n`
- `0x18030d97e`: `Redirecting CiDiag output to UTC temp path.\n`
- `0x18030ce6c`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030d258`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030d38e`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030d42a`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030d829`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030d84a`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030da33`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030dbdb`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030df2b`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030e042`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030e364`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030e388`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030e5d9`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030e7ab`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030e8e9`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030ebd6`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030ebf7`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030ee92`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030eeb3`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030f000`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030f37b`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030f3aa`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030f746`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030f756`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18030e200`: `RunExeWithArgsAction_FailedToCreateProcess_0`
- `0x18030eaa6`: `RunExeWithArgsAction_ExeTerminated_ServiceShuttingDown_0`
- `0x18030e536`: `IsValid(childProcessMainThread)`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall Microsoft::Diagnostics::RunExeHelperDef::RunExecutable(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties *a5,
        int a6,
        PULONG64 CycleTime)
{
  __int64 result; // rax
  _QWORD *v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  int v12; // ecx
  int v13; // r8d
  const char *v14; // r9
  ULONG_PTR v15; // rdx
  Microsoft::Diagnostics::LifetimeManager *v16; // rcx
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rax
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  const char *v21; // r9
  Microsoft::Diagnostics::LifetimeManager *v22; // rcx
  Microsoft::Diagnostics::TelemetryAssert *v23; // rax
  int v24; // eax
  char v25; // bl
  __int64 v26; // r13
  int v27; // eax
  void *v28; // r8
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v31; // ebx
  const char *v32; // r9
  const char *v33; // r9
  unsigned int v34; // ebx
  const char *v35; // r9
  unsigned int v36; // ebx
  _OWORD *v37; // rax
  __int64 v38; // rbx
  const char *v39; // r9
  _QWORD *v40; // rax
  int v41; // eax
  __int64 v42; // r13
  __int64 v43; // r8
  int v44; // eax
  unsigned int v45; // ebx
  _QWORD *v46; // rax
  int v47; // eax
  unsigned int v48; // ebx
  int v49; // r8d
  int v50; // r9d
  WCHAR *v51; // rax
  _QWORD *v52; // rax
  void *appended; // rax
  void *v54; // r8
  void *v55; // rax
  void *v56; // rax
  void *v57; // r8
  HANDLE JobObjectW; // rax
  const char *v59; // r9
  HANDLE v60; // rbx
  unsigned int v61; // ebx
  __int64 v62; // r13
  unsigned int v63; // ebx
  WCHAR *v64; // r8
  const WCHAR *v65; // rdx
  int v66; // eax
  int v67; // eax
  DWORD v68; // ebx
  Microsoft::Diagnostics::LifetimeManager *v69; // rcx
  int v70; // r8d
  int v71; // r9d
  Microsoft::Diagnostics::TelemetryAssert *v72; // rax
  Microsoft::Diagnostics::LifetimeManager *v73; // rcx
  Microsoft::Diagnostics::TelemetryAssert *v74; // rax
  DWORD v75; // eax
  unsigned int v76; // ebx
  HANDLE WaitableTimer; // rdi
  const char *v78; // r9
  unsigned int v79; // ebx
  DWORD v80; // eax
  const char *v81; // r9
  unsigned int v82; // ebx
  __int64 v83; // rdi
  __int64 *v84; // rcx
  DWORD v85; // eax
  int v86; // eax
  int v87; // eax
  const char *v88; // r9
  unsigned int v89; // ebx
  int v90; // ecx
  int v91; // r8d
  int v92; // r9d
  __int128 *v93; // rax
  WCHAR *v94; // rax
  __int64 v95; // rax
  void *v96; // rax
  int v97; // eax
  _QWORD *v98; // rdx
  int cbSize; // [rsp+20h] [rbp-878h]
  unsigned int cbSizea; // [rsp+20h] [rbp-878h]
  int cbSizeb; // [rsp+20h] [rbp-878h]
  unsigned int cbSizec; // [rsp+20h] [rbp-878h]
  int cbSized; // [rsp+20h] [rbp-878h]
  int cbSizee; // [rsp+20h] [rbp-878h]
  int cbSizef; // [rsp+20h] [rbp-878h]
  int cbSizeg; // [rsp+20h] [rbp-878h]
  __m128i v107; // [rsp+60h] [rbp-838h] BYREF
  DWORD ExitCode; // [rsp+70h] [rbp-828h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-820h] BYREF
  void *phNewToken; // [rsp+80h] [rbp-818h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+88h] [rbp-810h] BYREF
  _BYTE Value[8]; // [rsp+90h] [rbp-808h] BYREF
  HANDLE hProcess; // [rsp+98h] [rbp-800h] BYREF
  LPVOID Environment[2]; // [rsp+A0h] [rbp-7F8h] BYREF
  LARGE_INTEGER DueTime[2]; // [rsp+B0h] [rbp-7E8h] BYREF
  __int128 v116; // [rsp+C0h] [rbp-7D8h] BYREF
  __int64 v117; // [rsp+D0h] [rbp-7C8h]
  ULONG_PTR Size; // [rsp+D8h] [rbp-7C0h] BYREF
  _BYTE v119[16]; // [rsp+E0h] [rbp-7B8h] BYREF
  __int128 v120; // [rsp+F0h] [rbp-7A8h] BYREF
  _QWORD v121[2]; // [rsp+100h] [rbp-798h] BYREF
  _QWORD v122[2]; // [rsp+110h] [rbp-788h] BYREF
  char v123; // [rsp+120h] [rbp-778h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+128h] [rbp-770h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+140h] [rbp-758h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v126; // [rsp+1A8h] [rbp-6F0h]
  _BYTE v127[72]; // [rsp+1B0h] [rbp-6E8h] BYREF
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties *v128; // [rsp+1F8h] [rbp-6A0h]
  WCHAR v129[4]; // [rsp+200h] [rbp-698h] BYREF
  unsigned __int64 v130; // [rsp+218h] [rbp-680h]
  _QWORD Src[2]; // [rsp+220h] [rbp-678h] BYREF
  __int64 v132; // [rsp+230h] [rbp-668h]
  unsigned __int64 v133; // [rsp+238h] [rbp-660h]
  WCHAR v134[12]; // [rsp+240h] [rbp-658h] BYREF
  unsigned __int64 v135; // [rsp+258h] [rbp-640h]
  HANDLE hJob[4]; // [rsp+260h] [rbp-638h] BYREF
  LPCWSTR lpApplicationName[4]; // [rsp+280h] [rbp-618h] BYREF
  __int128 v138; // [rsp+2A0h] [rbp-5F8h] BYREF
  __m128i v139; // [rsp+2B0h] [rbp-5E8h]
  LPWSTR lpCommandLine[2]; // [rsp+2C0h] [rbp-5D8h] BYREF
  __m128i si128; // [rsp+2D0h] [rbp-5C8h]
  _QWORD v142[4]; // [rsp+2F0h] [rbp-5A8h] BYREF
  WCHAR JobObjectInformation[8]; // [rsp+310h] [rbp-588h] BYREF
  int v144; // [rsp+320h] [rbp-578h]
  char v145; // [rsp+350h] [rbp-548h]
  _QWORD v146[7]; // [rsp+360h] [rbp-538h] BYREF
  _QWORD *v147; // [rsp+398h] [rbp-500h]
  _BYTE v148[1128]; // [rsp+3A0h] [rbp-4F8h] BYREF
  _BYTE v149[56]; // [rsp+808h] [rbp-90h] BYREF
  HANDLE Handles[2]; // [rsp+840h] [rbp-58h] BYREF
  __int64 v151; // [rsp+850h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+898h] [rbp+0h]

  v121[0] = a4;
  *(_QWORD *)&v120 = a1;
  v128 = a5;
  if ( !a2[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
      (const char *)0x8007010BLL,
      cbSize);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
    return 2147942667LL;
  }
  try
  {
    std::wstring::wstring((__int64)Src, a2);
    Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(Src);
    v9 = Src;
    if ( v133 > 7 )
      v9 = (_QWORD *)Src[0];
    if ( *((_WORD *)v9 + v132 - 1) == 92 )
    {
      v10 = --v132;
      v11 = Src;
      if ( v133 > 7 )
        v11 = (_QWORD *)Src[0];
      *((_WORD *)v11 + v10) = 0;
    }
    ExitCode = 0;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      Value,
      &ExitCode);
    Size = 0;
    InitializeProcThreadAttributeList(0, 1u, 0, &Size);
    v15 = Size;
    if ( Size )
      goto LABEL_16;
    if ( (unsigned int)dword_18042D328 > 2 )
    {
      Environment[0] = "RunExecutable";
      TokenHandle = "attributesSize > 0";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)&unk_1803DFD6E,
        v13,
        (_DWORD)v14,
        (__int64)&TokenHandle,
        (__int64)Environment);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v16);
      Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
    }
    v15 = Size;
    if ( Size )
LABEL_16:
      v18 = 1;
    else
      v18 = 0;
    if ( !v18 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        v14);
    std::make_unique<unsigned char [0],0>(&lpAttributeList, v15);
    InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, &Size);
    if ( Size )
      goto LABEL_25;
    if ( (unsigned int)dword_18042D328 > 2 )
    {
      Environment[0] = "RunExecutable";
      TokenHandle = "attributesSize > 0";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v19,
        (unsigned int)&unk_1803DFDE3,
        v20,
        (_DWORD)v21,
        (__int64)&TokenHandle,
        (__int64)Environment);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      v23 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v22);
      Microsoft::Diagnostics::TelemetryAssert::Assert(v23);
    }
    if ( Size )
LABEL_25:
      v24 = 1;
    else
      v24 = 0;
    if ( !v24 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        v21);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      Value,
      0);
    UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, Value, 8u, 0, 0);
    v25 = 0;
    memset_0(&StartupInfo, 0, 0x70u);
    StartupInfo.cb = 112;
    StartupInfo.dwFlags = 256;
    v126 = lpAttributeList;
    phNewToken = 0;
    v116 = 0;
    v117 = 0;
    v26 = v120 + 128;
    v107 = *(__m128i *)&Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath;
    *(_OWORD *)hJob = *(_OWORD *)std::wstring::operator std::wstring_view(v120 + 128, DueTime);
    v27 = Microsoft::Diagnostics::Utils::String::ICompare(hJob, &v107);
    v28 = 0;
    if ( !v27 )
    {
      if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
      {
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18042D328,
          &unk_1803DFDA9);
        v28 = 0;
      }
      v25 = 1;
    }
    TokenHandle = v28;
    if ( !v25 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
      {
        LastError = GetLastError();
        if ( LastError != 1008 )
        {
          if ( LastError )
          {
            v31 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x67,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                    (const char *)LastError,
                    cbSizea);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            std::vector<wchar_t>::_Tidy(&v116);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
            return v31;
          }
          else
          {
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            std::vector<wchar_t>::_Tidy(&v116);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
            return 0;
          }
        }
      }
    }
    Environment[0] = 0;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &phNewToken,
        0);
      if ( !DuplicateTokenEx(TokenHandle, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &phNewToken) )
      {
        v34 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x79,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                v33);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        std::vector<wchar_t>::_Tidy(&v116);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
        return v34;
      }
    }
    if ( !CreateEnvironmentBlock(Environment, phNewToken, 0) )
    {
      v36 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x7C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v35);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
      return v36;
    }
    v107.m128i_i64[0] = (__int64)Environment;
    v107.m128i_i8[8] = 1;
    *(_OWORD *)hJob = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v122);
    v37 = (_OWORD *)std::wstring::operator std::wstring_view(&unk_18043C388, v119);
    try
    {
      *(_OWORD *)&DueTime[0].LowPart = *v37;
      v38 = Microsoft::Diagnostics::Utils::String::AddEnvironmentVariableToBlock(v142);
      if ( &v116 == (__int128 *)v38 )
      {
        DueTime[0].QuadPart = v116;
      }
      else
      {
        std::vector<wchar_t>::_Tidy(&v116);
        DueTime[0] = *(LARGE_INTEGER *)v38;
        *(LARGE_INTEGER *)&v116 = DueTime[0];
        *((_QWORD *)&v116 + 1) = *(_QWORD *)(v38 + 8);
        v117 = *(_QWORD *)(v38 + 16);
        *(_QWORD *)v38 = 0;
        *(_QWORD *)(v38 + 8) = 0;
        *(_QWORD *)(v38 + 16) = 0;
      }
      std::vector<wchar_t>::_Tidy(v142);
      DestroyEnvironmentBlock(Environment[0]);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    catch ( ... )
    {
      DueTime[0].LowPart = wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x86,
                             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                             v39);
      DestroyEnvironmentBlock(Environment[0]);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(v128);
      return DueTime[0].LowPart;
    }
    std::wstring::wstring((__int64)lpApplicationName, &Microsoft::Diagnostics::RunExeHelperDef::k_runExeHelperPath);
    std::wstring::wstring(v134, v26);
    std::wstring::wstring(v129, a5);
    Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)lpCommandLine);
    v107 = *(__m128i *)&Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath;
    *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(v26, v119);
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(Environment, &v107) )
    {
      v107 = *(__m128i *)std::wstring::operator std::wstring_view(v129, v119);
      v40 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a3, JobObjectInformation, &v107);
      std::wstring::operator=(v129, v40);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)JobObjectInformation);
      ExitCode = Microsoft::Diagnostics::AgentManager::ResolveContainerId(v129);
      if ( (ExitCode & 0x80000000) != 0 )
      {
        v107.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_FailedToResolveContainerId";
        v107.m128i_i64[1] = 47;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v148,
          (unsigned int)&v107,
          0x1000000,
          0,
          0,
          0,
          0);
        v107.m128i_i64[0] = (__int64)L"ExeName";
        v107.m128i_i64[1] = 7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v148, (unsigned int)v149);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
        v107.m128i_i64[0] = (__int64)L"ScenarioId";
        v107.m128i_i64[1] = 10;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
        v107.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
        v107.m128i_i64[1] = 18;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
        v107.m128i_i64[0] = (__int64)L"ExpandedCommandLine";
        v107.m128i_i64[1] = 19;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v148, (unsigned int)v149);
        v107.m128i_i64[0] = (__int64)L"ErrorCode";
        v107.m128i_i64[1] = 9;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v148, (unsigned int)v149);
        v107 = 0;
        Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
          DueTime,
          &v107);
        v41 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v148);
        if ( v41 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA6,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
            (const char *)(unsigned int)v41,
            cbSizeb);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C51036LL,
          cbSizeb);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v148);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v116);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
        return 2277838902LL;
      }
    }
    v42 = v121[0];
    if ( ((*(_QWORD *)(v121[0] + 224LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v107 = *(__m128i *)&Microsoft::Diagnostics::RunExeHelperDef::k_cidiagCommandLineNoOutputPath;
      *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(v129, v119);
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(Environment, &v107) )
      {
        v43 = -1;
        do
          ++v43;
        while ( Microsoft::Diagnostics::RunExeHelperDef::k_cidiagCommandLineWithOutputPath[v43] );
        std::wstring::_Assign<wchar_t>(
          (char **)v129,
          Microsoft::Diagnostics::RunExeHelperDef::k_cidiagCommandLineWithOutputPath,
          (char *)v43);
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v42 + 168));
      }
    }
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpApplicationName);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v134);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v129);
    v107 = *(__m128i *)std::wstring::operator std::wstring_view(Src, v119);
    *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043C3A8, v122);
    v44 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(v129);
    v45 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        (const char *)(unsigned int)v44,
        cbSizea);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
      return v45;
    }
    v107 = *(__m128i *)std::wstring::operator std::wstring_view(v129, v119);
    v46 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a3, JobObjectInformation, &v107);
    std::wstring::operator=(v129, v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)JobObjectInformation);
    if ( ((*(_QWORD *)(v42 + 224) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      std::wstring::wstring(v142, v129);
      Microsoft::Diagnostics::Utils::FileSystem::GetWindowsTemporaryPath(JobObjectInformation);
      Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath((LPCWSTR)hJob);
      v107 = *(__m128i *)std::wstring::operator std::wstring_view(hJob, v119);
      *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(JobObjectInformation, v122);
      v47 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(v129);
      v48 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v47,
          cbSizea);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)hJob);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)JobObjectInformation);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v142);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v116);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
        return v48;
      }
      if ( (unsigned __int8)std::operator!=<wchar_t>(v129, v142) )
      {
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
        {
          v51 = v129;
          if ( v130 > 7 )
            v51 = *(WCHAR **)v129;
          Environment[0] = v51;
          v52 = v142;
          if ( v142[3] > 7u )
            v52 = (_QWORD *)v142[0];
          TokenHandle = v52;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            (unsigned int)&dword_18042D328,
            (unsigned int)&unk_1803DFD02,
            v49,
            v50,
            (__int64)&TokenHandle,
            (__int64)Environment);
        }
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v42 + 168));
      }
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)hJob);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)JobObjectInformation);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v142);
    }
    v107 = *(__m128i *)std::wstring::operator std::wstring_view(lpApplicationName, v119);
    appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpCommandLine);
    Microsoft::Diagnostics::WideStringStream::operator<<(appended);
    if ( std::wstring::find_first_of(v134, 32, 0) == -1 )
    {
      v107 = *(__m128i *)std::wstring::operator std::wstring_view(v134, v119);
      v56 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpCommandLine);
    }
    else
    {
      Microsoft::Diagnostics::WideStringStream::operator<<(lpCommandLine);
      v107 = *(__m128i *)std::wstring::operator std::wstring_view(v134, v119);
      v55 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v54);
      v56 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v55);
    }
    Microsoft::Diagnostics::WideStringStream::operator<<(v56);
    v107 = *(__m128i *)std::wstring::operator std::wstring_view(v129, v122);
    Microsoft::Diagnostics::WideStringStream::AppendString(v57);
    hJob[0] = 0;
    JobObjectW = CreateJobObjectW(0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      hJob,
      JobObjectW);
    v60 = hJob[0];
    if ( (((unsigned __int64)hJob[0] + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v61 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xF0,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v59);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
      return v61;
    }
    memset_0(JobObjectInformation, 0, 0x40u);
    v62 = v120;
    *(_QWORD *)JobObjectInformation = 10000LL * *(_QWORD *)(v120 + 160);
    v144 = 2;
    if ( !SetInformationJobObject(v60, JobObjectBasicLimitInformation, JobObjectInformation, 0x40u) )
    {
      v63 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xFD,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              0);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
      return v63;
    }
    v138 = *(_OWORD *)lpCommandLine;
    v139 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpCommandLine[0]) = 0;
    hProcess = 0;
    TokenHandle = 0;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    v64 = (WCHAR *)&v138;
    if ( _mm_srli_si128(v139, 8).m128i_u64[0] > 7 )
      v64 = (WCHAR *)v138;
    v65 = (const WCHAR *)lpApplicationName;
    if ( lpApplicationName[3] > (LPCWSTR)7 )
      v65 = lpApplicationName[0];
    if ( !CreateProcessAsUserW(
            phNewToken,
            v65,
            v64,
            0,
            0,
            1,
            0x8080404u,
            (LPVOID)DueTime[0].QuadPart,
            0,
            &StartupInfo,
            &ProcessInformation) )
    {
      v66 = GetLastError();
      if ( v66 > 0 )
        v66 = (unsigned __int16)v66 | 0x80070000;
      ExitCode = v66;
      v107.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_FailedToCreateProcess_0";
      v107.m128i_i64[1] = 44;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v148,
        (unsigned int)&v107,
        0x1000000,
        0,
        0,
        0,
        0);
      v107.m128i_i64[0] = (__int64)L"ExeName";
      v107.m128i_i64[1] = 7;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v148, (unsigned int)v149);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
      v107.m128i_i64[0] = (__int64)L"ScenarioId";
      v107.m128i_i64[1] = 10;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
      v107.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
      v107.m128i_i64[1] = 18;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
      v107.m128i_i64[0] = (__int64)L"ErrorCode";
      v107.m128i_i64[1] = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v148, (unsigned int)v149);
      v107 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(DueTime, &v107);
      v67 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v148);
      if ( v67 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x11F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v67,
          cbSized);
      v68 = ExitCode;
      if ( (ExitCode & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)ExitCode,
          cbSized);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
      return v68;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hProcess,
      ProcessInformation.hProcess);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      ProcessInformation.hThread);
    if ( (((unsigned __int64)hProcess + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned int)dword_18042D328 > 2 )
      {
        Environment[0] = "RunExecutable";
        DueTime[0].QuadPart = (LONGLONG)"IsValid(childProcess)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v69,
          (unsigned int)&unk_1803DFC2B,
          v70,
          v71,
          (__int64)DueTime,
          (__int64)Environment);
      }
      if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
      {
        v72 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v69);
        Microsoft::Diagnostics::TelemetryAssert::Assert(v72);
      }
    }
    if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned int)dword_18042D328 > 2 )
      {
        Environment[0] = "RunExecutable";
        DueTime[0].QuadPart = (LONGLONG)"IsValid(childProcessMainThread)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v69,
          (unsigned int)&unk_1803DFC66,
          v70,
          v71,
          (__int64)DueTime,
          (__int64)Environment);
      }
      if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
      {
        v74 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v73);
        Microsoft::Diagnostics::TelemetryAssert::Assert(v74);
      }
    }
    if ( !AssignProcessToJobObject(v60, hProcess) )
    {
      TerminateProcess(ProcessInformation.hProcess, 1u);
      v75 = GetLastError();
      if ( v75 )
      {
        v76 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x133,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                (const char *)v75,
                cbSizec);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v116);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
        return v76;
      }
      else
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v116);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
        return 0;
      }
    }
    WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
    Environment[0] = WaitableTimer;
    if ( (((unsigned __int64)WaitableTimer + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v79 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x139,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v78);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
      return v79;
    }
    v80 = -10000 * *(_DWORD *)(v62 + 160);
    DueTime[0].HighPart = (-10000LL * (unsigned __int64)*(unsigned int *)(v62 + 160)) >> 32;
    DueTime[0].LowPart = v80;
    if ( !SetWaitableTimer(WaitableTimer, DueTime, 0, 0, 0, 0) )
    {
      v82 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x140,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v81);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
      return v82;
    }
    ResumeThread(ProcessInformation.hThread);
    v151 = 0;
    Handles[0] = hProcess;
    Handles[1] = WaitableTimer;
    v83 = v121[0];
    v84 = *(__int64 **)(v121[0] + 216LL);
    v151 = *v84;
    LODWORD(v84) = (*v84 != 0) + 2;
    v122[0] = &CycleTime;
    v122[1] = &hProcess;
    v123 = 1;
    v85 = WaitForMultipleObjects((DWORD)v84, Handles, 0, 0xFFFFFFFF);
    if ( v85 == 2 )
    {
      if ( !Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(hProcess, 0x1388u) )
      {
        TerminateJobObject(v60, 1u);
        v107.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_ExeTerminated_ServiceShuttingDown_0";
        v107.m128i_i64[1] = 56;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v148,
          (unsigned int)&v107,
          0x1000000,
          0,
          0,
          0,
          0);
        v107.m128i_i64[0] = (__int64)L"ExeName";
        v107.m128i_i64[1] = 7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v148, (unsigned int)v149);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
        v107.m128i_i64[0] = (__int64)L"ScenarioId";
        v107.m128i_i64[1] = 10;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
        v107.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
        v107.m128i_i64[1] = 18;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
        v107 = 0;
        Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
          DueTime,
          &v107);
        v86 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v148);
        if ( v86 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
            (const char *)(unsigned int)v86,
            cbSizef);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C5101ALL,
          cbSizef);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v148);
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
LABEL_117:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v116);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
        return 2277838874LL;
      }
    }
    else if ( v85 == 1 )
    {
      TerminateJobObject(v60, 1u);
      v107.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_ExeTerminated_0";
      v107.m128i_i64[1] = 36;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v148,
        (unsigned int)&v107,
        0x1000000,
        0,
        0,
        0,
        0);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
      v107.m128i_i64[0] = (__int64)L"ScenarioId";
      v107.m128i_i64[1] = 10;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
      v107.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
      v107.m128i_i64[1] = 18;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
      v107.m128i_i64[0] = (__int64)L"ExpandedExeName";
      v107.m128i_i64[1] = 15;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v148, (unsigned int)v149);
      v107.m128i_i64[0] = (__int64)L"MaximumRuntimeMs";
      v107.m128i_i64[1] = 16;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v148, (unsigned int)v149);
      v107 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(DueTime, &v107);
      v87 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v148);
      if ( v87 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v87,
          cbSizeg);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        (const char *)0x87C5101ALL,
        cbSizeg);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v148);
      if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        QueryProcessCycleTime(hProcess, CycleTime);
      goto LABEL_117;
    }
    ExitCode = 0;
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      if ( ExitCode == 259 )
      {
        TerminateJobObject(v60, 1u);
        ExitCode = 0;
      }
      if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
      {
        DueTime[0].LowPart = ExitCode;
        v93 = &v138;
        if ( v139.m128i_i64[1] > 7uLL )
          v93 = (__int128 *)v138;
        v121[0] = v93;
        v94 = v134;
        if ( v135 > 7 )
          v94 = *(WCHAR **)v134;
        v107.m128i_i64[0] = (__int64)v94;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v90,
          (unsigned int)&unk_1803DFCA1,
          v91,
          v92,
          (__int64)&v107,
          (__int64)v121,
          (__int64)DueTime);
      }
      v95 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v83 + 168));
      v96 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v95, ExitCode);
      Microsoft::Diagnostics::WideStringStream::operator<<(v96);
      if ( ExitCode )
      {
        if ( !*(_BYTE *)(v120 + 56) )
        {
          v107.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_ProcessReturnedNonZeroExitCode";
          v107.m128i_i64[1] = 51;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
            (unsigned int)v148,
            (unsigned int)&v107,
            0x1000000,
            0,
            0,
            0,
            0);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
          v107.m128i_i64[0] = (__int64)L"ScenarioId";
          v107.m128i_i64[1] = 10;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
          v107.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
          v107.m128i_i64[1] = 18;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v148, (unsigned int)v149);
          v107.m128i_i64[0] = (__int64)L"ExpandedExeName";
          v107.m128i_i64[1] = 15;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v148, (unsigned int)v149);
          v107.m128i_i64[0] = (__int64)L"ExitCode";
          v107.m128i_i64[1] = 8;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v148, (unsigned int)v149);
          v107 = 0;
          Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
            DueTime,
            &v107);
          v97 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v148);
          if ( v97 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1B1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              (const char *)(unsigned int)v97,
              cbSizee);
          Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v148);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C5101DLL,
          cbSizee);
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v116);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
        result = 2277838877LL;
      }
      else
      {
        v145 = 0;
        v127[64] = 0;
        v146[0] = off_18035C910;
        v146[1] = v83;
        v147 = v146;
        v107.m128i_i64[0] = (__int64)L"*";
        v107.m128i_i64[1] = 1;
        v121[0] = L"*";
        v121[1] = 1;
        v120 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v119);
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileAndDirectoryRecursivelyInPattern(
          (unsigned int)&v120,
          (unsigned int)v121,
          (unsigned int)&v107,
          (unsigned int)v146,
          (__int64)v127,
          (__int64)JobObjectInformation);
        if ( v147 )
        {
          v98 = v146;
          LOBYTE(v98) = v147 != v146;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v147 + 32LL))(v147, v98);
        }
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v116);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
        result = 0;
      }
    }
    else
    {
      v89 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x189,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v88);
      if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        QueryProcessCycleTime(hProcess, CycleTime);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v138);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v129);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v116);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpAttributeList);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(a5);
      result = v89;
    }
  }
  catch ( ... )
  {
    DueTime[0].LowPart = wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1C5,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                           v32);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(v128);
    return DueTime[0].LowPart;
  }
  return result;
}

```

## disassembly

```asm
0x18030ce0c  push    rbx
0x18030ce0e  push    rsi
0x18030ce0f  push    rdi
0x18030ce10  push    r12
0x18030ce12  push    r13
0x18030ce14  push    r14
0x18030ce16  push    r15
0x18030ce18  sub     rsp, 860h
0x18030ce1f  mov     rax, cs:__security_cookie
0x18030ce26  xor     rax, rsp
0x18030ce29  mov     [rsp+898h+var_40], rax
0x18030ce31  mov     [rsp+898h+var_798], r9
0x18030ce39  mov     r15, r8
0x18030ce3c  mov     qword ptr [rsp+898h+var_7A8], rcx
0x18030ce44  mov     rsi, [rsp+898h+arg_20]
0x18030ce4c  mov     [rsp+898h+var_6A0], rsi
0x18030ce54  xor     ebx, ebx
0x18030ce56  cmp     [rdx+8], rbx
0x18030ce5a  jnz     short loc_18030CE8D
0x18030ce5c  mov     rcx, [rsp+898h]; this
0x18030ce64  mov     ebx, 8007010Bh
0x18030ce69  mov     r9d, ebx; char *
0x18030ce6c  lea     r8, aOnecoreBaseTel_91; "onecore\\base\\telemetry\\utc\\service"...
0x18030ce73  mov     edx, 1Dh; void *
0x18030ce78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18030ce7d  nop
0x18030ce7e  mov     rcx, rsi; this
0x18030ce81  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18030ce86  mov     eax, ebx
0x18030ce88  jmp     loc_18030F722
0x18030ce8d  lea     rcx, [rsp+898h+Src]
0x18030ce95  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18030ce9a  nop
0x18030ce9b  lea     rcx, [rsp+898h+Src]; Src
0x18030cea3  call    ?PrependLongPathUnicodePrefix@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(std::wstring &)
0x18030cea8  lea     rax, [rsp+898h+Src]
0x18030ceb0  cmp     [rsp+898h+var_660], 7
0x18030ceb9  cmova   rax, [rsp+898h+Src]
0x18030cec2  mov     rdx, [rsp+898h+var_668]
0x18030ceca  mov     r14d, 1
0x18030ced0  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x18030ced6  jnz     short loc_18030CF01
0x18030ced8  sub     rdx, r14
0x18030cedb  mov     [rsp+898h+var_668], rdx
0x18030cee3  lea     rcx, [rsp+898h+Src]
0x18030ceeb  cmp     [rsp+898h+var_660], 7
0x18030cef4  cmova   rcx, [rsp+898h+Src]
0x18030cefd  mov     [rcx+rdx*2], bx
0x18030cf01  mov     [rsp+898h+ExitCode], ebx
0x18030cf05  lea     rdx, [rsp+898h+ExitCode]
0x18030cf0a  lea     rcx, [rsp+898h+Value]
0x18030cf12  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18030cf17  nop
0x18030cf18  mov     [rsp+898h+Size], rbx
0x18030cf20  lea     r9, [rsp+898h+Size]; lpSize
0x18030cf28  xor     r8d, r8d; dwFlags
0x18030cf2b  mov     edx, r14d; dwAttributeCount
0x18030cf2e  xor     ecx, ecx; lpAttributeList
0x18030cf30  call    cs:__imp_InitializeProcThreadAttributeList
0x18030cf37  nop     dword ptr [rax+rax+00h]
0x18030cf3c  mov     rdx, [rsp+898h+Size]
0x18030cf44  mov     r12d, 2
0x18030cf4a  test    rdx, rdx
0x18030cf4d  jnz     loc_18030CFE4
0x18030cf53  mov     eax, cs:dword_18042D328
0x18030cf59  cmp     eax, r12d
0x18030cf5c  jbe     short loc_18030CF9E
0x18030cf5e  lea     r13, aRunexecutable; "RunExecutable"
0x18030cf65  mov     [rsp+898h+Environment], r13
0x18030cf6d  lea     rbx, aAttributessize; "attributesSize > 0"
0x18030cf74  mov     [rsp+898h+TokenHandle], rbx
0x18030cf79  lea     rax, [rsp+898h+Environment]
0x18030cf81  mov     [rsp+898h+lpPreviousValue], rax
0x18030cf86  lea     rax, [rsp+898h+TokenHandle]
0x18030cf8b  mov     [rsp+898h+cbSize], rax
0x18030cf90  lea     rdx, unk_1803DFD6E
0x18030cf97  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18030cf9c  jmp     short loc_18030CFAC
0x18030cf9e  lea     r13, aRunexecutable; "RunExecutable"
0x18030cfa5  lea     rbx, aAttributessize; "attributesSize > 0"
0x18030cfac  lea     rdi, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x18030cfb3  mov     rcx, rdi; this
0x18030cfb6  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x18030cfbb  xor     r8d, r8d
0x18030cfbe  test    al, al
0x18030cfc0  jz      short loc_18030CFD2
0x18030cfc2  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x18030cfc7  mov     rcx, rax; this
0x18030cfca  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x18030cfcf  xor     r8d, r8d
0x18030cfd2  mov     rdx, [rsp+898h+Size]
0x18030cfda  test    rdx, rdx
0x18030cfdd  jnz     short loc_18030CFF9
0x18030cfdf  mov     eax, r8d
0x18030cfe2  jmp     short loc_18030CFFC
0x18030cfe4  lea     r13, aRunexecutable; "RunExecutable"
0x18030cfeb  lea     rbx, aAttributessize; "attributesSize > 0"
0x18030cff2  lea     rdi, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x18030cff9  mov     eax, r14d
0x18030cffc  mov     rcx, [rsp+898h]; this
0x18030d004  test    eax, eax
0x18030d006  jz      loc_18030F746
0x18030d00c  lea     rcx, [rsp+898h+lpAttributeList]
0x18030d014  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18030d019  nop
0x18030d01a  lea     r9, [rsp+898h+Size]; lpSize
0x18030d022  xor     r8d, r8d; dwFlags
0x18030d025  mov     edx, r14d; dwAttributeCount
0x18030d028  mov     rcx, [rsp+898h+lpAttributeList]; lpAttributeList
0x18030d030  call    cs:__imp_InitializeProcThreadAttributeList
0x18030d037  nop     dword ptr [rax+rax+00h]
0x18030d03c  cmp     [rsp+898h+Size], 0
0x18030d045  ja      short loc_18030D0AD
0x18030d047  mov     eax, cs:dword_18042D328
0x18030d04d  cmp     eax, r12d
0x18030d050  jbe     short loc_18030D082
0x18030d052  mov     [rsp+898h+Environment], r13
0x18030d05a  mov     [rsp+898h+TokenHandle], rbx
0x18030d05f  lea     rax, [rsp+898h+Environment]
0x18030d067  mov     [rsp+898h+lpPreviousValue], rax
0x18030d06c  lea     rax, [rsp+898h+TokenHandle]
0x18030d071  mov     [rsp+898h+cbSize], rax
0x18030d076  lea     rdx, unk_1803DFDE3
0x18030d07d  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18030d082  mov     rcx, rdi; this
0x18030d085  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x18030d08a  xor     r13d, r13d
0x18030d08d  test    al, al
0x18030d08f  jz      short loc_18030D09E
0x18030d091  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x18030d096  mov     rcx, rax; this
0x18030d099  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x18030d09e  cmp     [rsp+898h+Size], r13
0x18030d0a6  ja      short loc_18030D0B0
0x18030d0a8  mov     eax, r13d
0x18030d0ab  jmp     short loc_18030D0B3
0x18030d0ad  xor     r13d, r13d
0x18030d0b0  mov     eax, r14d
0x18030d0b3  mov     rcx, [rsp+898h]; this
0x18030d0bb  test    eax, eax
0x18030d0bd  jz      loc_18030F756
0x18030d0c3  xor     edx, edx
0x18030d0c5  lea     rcx, [rsp+898h+Value]
0x18030d0cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18030d0d2  mov     [rsp+898h+lpReturnSize], r13; lpReturnSize
0x18030d0d7  mov     [rsp+898h+lpPreviousValue], r13; lpPreviousValue
0x18030d0dc  mov     [rsp+898h+cbSize], 8; int
0x18030d0e5  lea     r9, [rsp+898h+Value]; lpValue
0x18030d0ed  xor     edx, edx; dwFlags
0x18030d0ef  mov     r8d, 20002h; Attribute
0x18030d0f5  mov     rcx, [rsp+898h+lpAttributeList]; lpAttributeList
0x18030d0fd  call    cs:__imp_UpdateProcThreadAttribute
0x18030d104  nop     dword ptr [rax+rax+00h]
0x18030d109  mov     ebx, 70h ; 'p'
0x18030d10e  mov     r8d, ebx; Size
0x18030d111  xor     edx, edx; Val
0x18030d113  lea     rcx, [rsp+898h+StartupInfo]; void *
0x18030d11b  call    memset_0
0x18030d120  mov     [rsp+898h+StartupInfo.cb], ebx
0x18030d127  mov     [rsp+898h+StartupInfo.dwFlags], 100h
0x18030d132  mov     rax, [rsp+898h+lpAttributeList]
0x18030d13a  mov     [rsp+898h+var_6F0], rax
0x18030d142  mov     [rsp+898h+phNewToken], r13
0x18030d14a  xorps   xmm0, xmm0
0x18030d14d  movdqu  [rsp+898h+var_7D8], xmm0
0x18030d156  mov     [rsp+898h+var_7C8], r13
0x18030d15e  mov     bl, r13b
0x18030d161  mov     r13, qword ptr [rsp+898h+var_7A8]
0x18030d169  sub     r13, 0FFFFFFFFFFFFFF80h
0x18030d16d  movups  xmm0, xmmword ptr cs:?k_hcsdiagPath@RunExeHelperDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath
0x18030d174  movdqu  [rsp+898h+var_838], xmm0
0x18030d17a  lea     rdx, [rsp+898h+DueTime]
0x18030d182  mov     rcx, r13
0x18030d185  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18030d18a  movups  xmm0, xmmword ptr [rax]
0x18030d18d  movdqu  xmmword ptr [rsp+898h+hJob], xmm0
0x18030d196  lea     rdx, [rsp+898h+var_838]
0x18030d19b  lea     rcx, [rsp+898h+hJob]
0x18030d1a3  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18030d1a8  xor     r8d, r8d
0x18030d1ab  test    eax, eax
0x18030d1ad  jnz     short loc_18030D1E7
0x18030d1af  mov     eax, cs:dword_18042D328
0x18030d1b5  cmp     eax, 4
0x18030d1b8  jbe     short loc_18030D1E4
0x18030d1ba  lea     edx, [r8+4]
0x18030d1be  lea     rcx, dword_18042D328
0x18030d1c5  call    _tlgKeywordOn
0x18030d1ca  test    al, al
0x18030d1cc  jz      short loc_18030D1E4
0x18030d1ce  lea     rdx, unk_1803DFDA9
0x18030d1d5  lea     rcx, dword_18042D328
0x18030d1dc  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18030d1e1  xor     r8d, r8d
0x18030d1e4  mov     bl, r14b
0x18030d1e7  mov     [rsp+898h+TokenHandle], r8
0x18030d1ec  test    bl, bl
0x18030d1ee  jnz     loc_18030D329
0x18030d1f4  xor     edx, edx
0x18030d1f6  lea     rcx, [rsp+898h+TokenHandle]
0x18030d1fb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18030d200  call    cs:__imp_GetCurrentThread
0x18030d207  nop     dword ptr [rax+rax+00h]
0x18030d20c  lea     r9, [rsp+898h+TokenHandle]; TokenHandle
0x18030d211  mov     r8d, r14d; OpenAsSelf
0x18030d214  mov     edx, 0F01FFh; DesiredAccess
0x18030d219  mov     rcx, rax; ThreadHandle
0x18030d21c  call    cs:__imp_OpenThreadToken
0x18030d223  nop     dword ptr [rax+rax+00h]
0x18030d228  xor     ebx, ebx
0x18030d22a  test    eax, eax
0x18030d22c  jnz     loc_18030D32B
0x18030d232  call    cs:__imp_GetLastError
0x18030d239  nop     dword ptr [rax+rax+00h]
0x18030d23e  cmp     eax, 3F0h
0x18030d243  jz      loc_18030D32B
0x18030d249  test    eax, eax
0x18030d24b  jz      short loc_18030D2C9
0x18030d24d  mov     rcx, [rsp+898h]; this
0x18030d255  mov     r9d, eax; char *
0x18030d258  lea     r8, aOnecoreBaseTel_91; "onecore\\base\\telemetry\\utc\\service"...
0x18030d25f  lea     edx, [rbx+67h]; void *
0x18030d262  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18030d267  mov     ebx, eax
0x18030d269  lea     rcx, [rsp+898h+TokenHandle]
0x18030d26e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18030d273  nop
0x18030d274  lea     rcx, [rsp+898h+var_7D8]
0x18030d27c  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18030d281  nop
0x18030d282  lea     rcx, [rsp+898h+phNewToken]
0x18030d28a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18030d28f  nop
0x18030d290  lea     rcx, [rsp+898h+lpAttributeList]
0x18030d298  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18030d29d  nop
0x18030d29e  lea     rcx, [rsp+898h+Value]
0x18030d2a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18030d2ab  nop
0x18030d2ac  lea     rcx, [rsp+898h+Src]; this
0x18030d2b4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18030d2b9  nop
0x18030d2ba  mov     rcx, rsi; this
0x18030d2bd  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18030d2c2  mov     eax, ebx
0x18030d2c4  jmp     loc_18030F722
0x18030d2c9  lea     rcx, [rsp+898h+TokenHandle]
0x18030d2ce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18030d2d3  nop
0x18030d2d4  lea     rcx, [rsp+898h+var_7D8]
0x18030d2dc  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18030d2e1  nop
0x18030d2e2  lea     rcx, [rsp+898h+phNewToken]
0x18030d2ea  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18030d2ef  nop
0x18030d2f0  lea     rcx, [rsp+898h+lpAttributeList]
0x18030d2f8  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18030d2fd  nop
0x18030d2fe  lea     rcx, [rsp+898h+Value]
0x18030d306  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18030d30b  nop
0x18030d30c  lea     rcx, [rsp+898h+Src]; this
0x18030d314  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18030d319  nop
0x18030d31a  mov     rcx, rsi; this
0x18030d31d  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18030d322  xor     eax, eax
0x18030d324  jmp     loc_18030F722
0x18030d329  xor     ebx, ebx
0x18030d32b  mov     [rsp+898h+Environment], rbx
0x18030d333  mov     rax, [rsp+898h+TokenHandle]
0x18030d338  dec     rax
0x18030d33b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18030d33f  ja      loc_18030D3FF
0x18030d345  xor     edx, edx
0x18030d347  lea     rcx, [rsp+898h+phNewToken]
0x18030d34f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18030d354  lea     rax, [rsp+898h+phNewToken]
0x18030d35c  mov     [rsp+898h+lpPreviousValue], rax; phNewToken
0x18030d361  mov     dword ptr [rsp+898h+cbSize], r14d; TokenType
0x18030d366  mov     r9d, r12d; ImpersonationLevel
0x18030d369  xor     r8d, r8d; lpTokenAttributes
0x18030d36c  mov     edx, 0F01FFh; dwDesiredAccess
0x18030d371  mov     rcx, [rsp+898h+TokenHandle]; hExistingToken
0x18030d376  call    cs:__imp_DuplicateTokenEx
0x18030d37d  nop     dword ptr [rax+rax+00h]
0x18030d382  test    eax, eax
0x18030d384  jnz     short loc_18030D3FF
0x18030d386  mov     rcx, [rsp+898h]; this
0x18030d38e  lea     r8, aOnecoreBaseTel_91; "onecore\\base\\telemetry\\utc\\service"...
0x18030d395  lea     edx, [rax+79h]; void *
0x18030d398  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18030d39d  mov     ebx, eax
0x18030d39f  lea     rcx, [rsp+898h+TokenHandle]
0x18030d3a4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18030d3a9  nop
0x18030d3aa  lea     rcx, [rsp+898h+var_7D8]
0x18030d3b2  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18030d3b7  nop
0x18030d3b8  lea     rcx, [rsp+898h+phNewToken]
  ... truncated ...
```
