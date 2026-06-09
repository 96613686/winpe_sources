# WscServiceStartup(int)

- ea: `0x18001d9e0`
- end: `0x18001f824`
- name: `?WscServiceStartup@@YAJH@Z`
- size: `7748`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d2f0`

## callees

- `0x180005220`
- `0x180008e48`
- `0x180016d50`
- `0x180017c60`
- `0x18001c6dc`
- `0x18001cb1c`
- `0x18001d9e0`
- `0x18001f97c`
- `0x18001fdd8`
- `0x1800202e8`
- `0x18002067c`
- `0x180021128`
- `0x180022678`
- `0x18002294c`
- `0x1800233a4`
- `0x180023960`
- `0x180026cec`
- `0x180027db4`
- `0x180028618`
- `0x1800292bc`
- `0x180029720`
- `0x180029a84`
- `0x180029adc`
- `0x180029e74`
- `0x18002a6b4`
- `0x18002eaf4`
- `0x1800305ec`
- `0x180031ff4`
- `0x1800326a8`
- `0x1800326f0`
- `0x180034aac`
- `0x1800357cc`
- `0x1800359b0`
- `0x18003608c`
- `0x180037460`
- `0x180039540`
- `0x180039614`
- `0x18003fbf2`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18001f6ff`
- `ntdll!RtlPublishWnfStateData` at `0x18001f73c`
- `ntdll!RtlPublishWnfStateData` at `0x18001f6ff`
- `ntdll!RtlPublishWnfStateData` at `0x18001f73c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e07a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f3f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e07a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f3f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ed95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ed95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e48a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e48a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f509`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e513`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e513`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f239`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f4d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f62e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f76f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f239`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f4d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f62e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f76f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f482`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f48b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f482`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f48b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001f4af`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001f4af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e4fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e6c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f242`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e4fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e6c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f242`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f58d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e2b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e87a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e9a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001eb48`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e2b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e87a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e9a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001eb48`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18001e41d`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18001e41d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001da6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001da6a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e225`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e376`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e560`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f138`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e225`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e376`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e560`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f138`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001db3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e26f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e477`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e65d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f1ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001db3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e26f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e477`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e65d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f1ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001dab8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001dab8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001daf9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f1a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001daf9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f1a1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001eafc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ec8b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001eafc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ec8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001dad1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f0f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f6e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f71e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001dad1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f0f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f6e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f71e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e467`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e5f9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e5f9`
- `ADVAPI32!RegisterEventSourceW` at `0x18001f785`
- `ADVAPI32!RegisterEventSourceW` at `0x18001f785`
- `ADVAPI32!DeregisterEventSource` at `0x18001f7d1`
- `ADVAPI32!DeregisterEventSource` at `0x18001f7d1`
- `ADVAPI32!ReportEventW` at `0x18001f7be`
- `ADVAPI32!ReportEventW` at `0x18001f7be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e3d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e3d9`

## string_xrefs

- `0x18001eb3a`: `SOFTWARE\Microsoft\Security Center\Provider\Av`
- `0x18001f77c`: `SecurityCenter`
- `0x18001da59`: `SOFTWARE\Microsoft\Security Center\Svc`
- `0x18001f12a`: `SOFTWARE\Microsoft\Security Center\Svc\Upgrade`
- `0x18001e86c`: `SOFTWARE\Microsoft\Security Center\Feature`
- `0x18001e217`: `SOFTWARE\Microsoft\Security Center\NCP`
- `0x18001e368`: `SOFTWARE\Microsoft\Security Center\NCP`
- `0x18001e552`: `SOFTWARE\Microsoft\Security Center\NCP`
- `0x18001e995`: `SOFTWARE\Microsoft\Security Center\Provider\Fw`
- `0x18001f25e`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaAvPathsExpiredSetup`
- `0x18001f252`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaAvPaths`

## pseudocode

```c
__int64 __fastcall WscServiceStartup(DWORD a1)
{
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  CCriticalSection *v3; // rcx
  HKEY v4; // r12
  WscServiceUtils::OneWayAMPPLEnablementAgent *v5; // rdi
  void *v6; // rcx
  unsigned int v7; // r8d
  const char *v8; // r9
  void *v9; // rcx
  void **v10; // rbx
  void **v11; // rcx
  void **v12; // rsi
  struct _RTL_CRITICAL_SECTION *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _DWORD *v16; // rax
  _DWORD *v17; // rax
  CSecureSettingsManager *v18; // rax
  _DWORD *v19; // rax
  HANDLE *v20; // rax
  HANDLE *v21; // rbx
  struct CSecurityVerificationManager *v22; // rax
  struct CSecurityVerificationManager *v23; // rax
  struct CSecurityVerificationManager *v24; // rax
  struct CFirewallManager *v25; // rdx
  CThirdPartyMonitoring *v26; // rcx
  signed int inited; // edi
  signed int LastError; // eax
  CThirdPartyManager *v29; // r10
  unsigned __int8 Variant; // al
  __int64 v31; // rdx
  _BOOL8 v32; // r9
  WscServiceUtils::OneWayAMPPLEnablementAgent *v33; // rax
  WscServiceUtils::OneWayAMPPLEnablementAgent *v34; // rbx
  int ValueW; // eax
  bool v36; // sf
  CThirdPartyManager *v37; // rcx
  __int64 v38; // rdx
  bool v39; // si
  bool v40; // sf
  int v41; // eax
  bool v42; // sf
  int v43; // eax
  CThirdPartyManager *v44; // rcx
  __int64 v45; // rdx
  bool v46; // sf
  wil::details *v47; // rcx
  HANDLE Mutex; // r14
  int LastErrorFailHr; // eax
  void *v50; // rsi
  DWORD v51; // r15d
  unsigned int v52; // r8d
  const char *v53; // r9
  LSTATUS v54; // eax
  signed int v55; // esi
  LSTATUS v56; // eax
  WscServiceUtils::OneWayAMPPLEnablementAgent *v57; // rsi
  void *v58; // rcx
  unsigned int v59; // r8d
  const char *v60; // r9
  void *v61; // rcx
  void **v62; // rbx
  void **v63; // rcx
  void **v64; // r14
  int v65; // ebx
  __int64 v66; // r9
  int v67; // ebx
  __int64 v68; // r9
  CSecureSettingsManager *v69; // rbx
  LPCRITICAL_SECTION v70; // r13
  _DWORD *v71; // rax
  int v72; // eax
  struct CWmiEventManager *v73; // r8
  char *LockSemaphore; // rsi
  _QWORD *v75; // r14
  _QWORD *i; // rax
  _QWORD **v77; // rbx
  struct _RTL_CRITICAL_SECTION *v78; // rcx
  DWORD dwLowDateTime; // esi
  struct CWmiEventManager *v80; // r8
  CSecureSettingsManager *v81; // rbx
  _QWORD *v82; // rax
  struct CWmiEventManager *v83; // r8
  struct CAntiVirusManager *v84; // r8
  struct CAntiSpywareManager *v85; // r9
  struct CFirewallManager *v86; // r8
  struct CAntiSpywareManager *v87; // r9
  int v88; // edi
  CThirdPartyManager *v89; // rcx
  int WmiInstances; // eax
  unsigned int v91; // ebx
  CThirdPartyManager *v92; // rcx
  __int64 v93; // rdx
  int DatastoreInstances; // eax
  int v95; // eax
  __int64 v96; // rdx
  CThirdPartyManager *v97; // rcx
  __int64 v98; // rdx
  int v99; // eax
  unsigned int v100; // eax
  unsigned int v101; // eax
  int v102; // ebx
  HANDLE Thread; // rax
  HKEY v104; // rcx
  HKEY v105; // rcx
  AMPPLWmiDataUtils *v106; // rcx
  struct CWmiEventManagerAvFw *v107; // rbx
  int IsAlerted; // eax
  int v109; // eax
  CThirdPartyManager *v110; // rcx
  __int64 v111; // rdx
  int v112; // eax
  int v113; // eax
  HANDLE EventW; // rsi
  signed int v115; // eax
  CThirdPartyManager *v116; // rcx
  LPHANDLE v117; // r14
  HANDLE CurrentProcess; // rbx
  HANDLE v119; // rax
  HANDLE v120; // rax
  signed int v121; // eax
  int v122; // eax
  signed int v123; // eax
  HANDLE v124; // rax
  void *v125; // rbx
  struct CAlertStatus *phkResult; // [rsp+20h] [rbp-E0h]
  struct CAlertStatus *phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  unsigned int pvData; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME v135; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  int v137; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp-68h] BYREF
  DWORD v139; // [rsp+9Ch] [rbp-64h] BYREF
  int v140; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v141; // [rsp+A4h] [rbp-5Ch] BYREF
  int v142; // [rsp+A8h] [rbp-58h] BYREF
  DWORD v143; // [rsp+ACh] [rbp-54h] BYREF
  int v144; // [rsp+B0h] [rbp-50h] BYREF
  DWORD v145; // [rsp+B4h] [rbp-4Ch] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B8h] [rbp-48h] BYREF
  EVENT_DESCRIPTOR v147; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE SystemTimeAsFileTime[24]; // [rsp+D8h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F0h] [rbp-10h] BYREF
  char *v150; // [rsp+100h] [rbp+0h]
  int v151; // [rsp+108h] [rbp+8h]
  int v152; // [rsp+10Ch] [rbp+Ch]
  int *v153; // [rsp+110h] [rbp+10h]
  __int64 v154; // [rsp+118h] [rbp+18h]
  unsigned int *v155; // [rsp+120h] [rbp+20h]
  __int64 v156; // [rsp+128h] [rbp+28h]
  int *v157; // [rsp+130h] [rbp+30h]
  __int64 v158; // [rsp+138h] [rbp+38h]
  struct _EVENT_DATA_DESCRIPTOR v159; // [rsp+140h] [rbp+40h] BYREF
  char *v160; // [rsp+150h] [rbp+50h]
  int v161; // [rsp+158h] [rbp+58h]
  int v162; // [rsp+15Ch] [rbp+5Ch]
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // [rsp+160h] [rbp+60h]
  __int64 v164; // [rsp+168h] [rbp+68h]
  DWORD *v165; // [rsp+170h] [rbp+70h]
  __int64 v166; // [rsp+178h] [rbp+78h]
  int *v167; // [rsp+180h] [rbp+80h]
  __int64 v168; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v135.dwLowDateTime = a1;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Security Center\\Svc", 0, 0x20007u, &hKey);
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids,
        (unsigned int)L"SOFTWARE\\Microsoft\\Security Center\\Svc",
        v1);
    }
  }
  else
  {
    cbData = 8;
    *(_QWORD *)Data = 0;
    Type = 11;
    if ( RegQueryValueExW(hKey, L"VistaSp1", 0, &Type, Data, &cbData) || Type != 11 )
    {
      *(_QWORD *)SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime((LPFILETIME)SystemTimeAsFileTime);
      v2 = RegSetValueExW(hKey, L"VistaSp1", 0, 0xBu, SystemTimeAsFileTime, 8u);
      if ( v2 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids,
            (unsigned int)L"SOFTWARE\\Microsoft\\Security Center\\Svc",
            (__int64)L"VistaSp1",
            v2);
        }
      }
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  v4 = 0;
  hKey = 0;
  g_OfflineScanInitiated = 0;
  g_pAlertStatus = 0;
  WscServiceUtils::g_pFirewallManager = 0;
  WscServiceUtils::g_pAntiVirusManager = 0;
  g_pSecureSettingsManager = 0;
  WscServiceUtils::g_pAntiSpywareManager = 0;
  g_pWmiEventManagerAvFw = 0;
  WscServiceUtils::g_pAntiSpywareVerificationManager = 0;
  WscServiceUtils::g_pAntiVirusVerificationManager = 0;
  WscServiceUtils::g_pFirewallVerificationManager = 0;
  g_pampplToastThrottler = 0;
  g_pregistryValuesStorage = 0;
  g_pWDSPNotificationFunctor = 0;
  v5 = g_pOneWayAMPPLEnablementAgent;
  g_pOneWayAMPPLEnablementAgent = 0;
  if ( v5 )
  {
    v6 = (void *)*((_QWORD *)v5 + 8);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
    v9 = (void *)*((_QWORD *)v5 + 2);
    if ( v9 )
    {
      operator delete(v9);
      *((_QWORD *)v5 + 2) = 0;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 4) = 0;
    }
    v10 = **(void ****)v5;
    **(_QWORD **)v5 = *(_QWORD *)v5;
    *(_QWORD *)(*(_QWORD *)v5 + 8LL) = *(_QWORD *)v5;
    *((_QWORD *)v5 + 1) = 0;
    v11 = *(void ***)v5;
    if ( v10 != *(void ***)v5 )
    {
      do
      {
        v12 = (void **)*v10;
        if ( (unsigned __int64)v10[5] >= 8 )
          operator delete(v10[2]);
        v10[5] = (void *)7;
        v10[4] = 0;
        *((_WORD *)v10 + 8) = 0;
        operator delete(v10);
        v10 = v12;
        v11 = *(void ***)v5;
      }
      while ( v12 != *(void ***)v5 );
    }
    operator delete(v11);
    operator delete(v5);
  }
  CCriticalSection::Initialize(v3);
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
  v13 = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v13;
  if ( v13 )
  {
    v13[1].DebugInfo = 0;
    *(_QWORD *)&v13[1].LockCount = 0;
    v13[1].OwningThread = (HANDLE)L"SOFTWARE\\Microsoft\\Security Center\\Svc";
    v13[1].LockSemaphore = 0;
  }
  else
  {
    v13 = 0;
  }
  g_pAlertStatus = v13;
  v14 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v14;
  if ( v14 )
  {
    *v14 = &CWmiEventSinkAvFw::`vftable';
    v14[1] = 0;
    v14[2] = 0;
    v14[4] = 0;
    *((_DWORD *)v14 + 20) = 0;
    *((_DWORD *)v14 + 21) = 1;
  }
  else
  {
    v14 = 0;
  }
  g_pWmiEventSinkAvFw = (struct CWmiEventSinkAvFw *)v14;
  v15 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v15;
  if ( v15 )
  {
    v15[1] = 0;
    v15[2] = 0;
    v15[3] = 0;
    v15[4] = 0;
    v15[5] = 0;
    v15[6] = 0;
    v15[7] = 0;
    v15[8] = 0;
    *((_DWORD *)v15 + 18) = 0;
    *v15 = &CWmiEventManagerAvFw::`vftable';
  }
  else
  {
    v15 = 0;
  }
  g_pWmiEventManagerAvFw = (struct CWmiEventManagerAvFw *)v15;
  v16 = operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v16;
  if ( v16 )
  {
    v16[2] = 0;
    *((_QWORD *)v16 + 7) = 0;
    *((_QWORD *)v16 + 8) = 0;
    *((_QWORD *)v16 + 9) = 0;
    *((_QWORD *)v16 + 10) = 0;
    *(_QWORD *)v16 = &CFirewallManager::`vftable';
    *((_QWORD *)v16 + 11) = 0;
  }
  else
  {
    v16 = 0;
  }
  WscServiceUtils::g_pFirewallManager = (CThirdPartyManager *)v16;
  v17 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v17;
  if ( v17 )
  {
    v17[2] = 0;
    *((_QWORD *)v17 + 7) = 0;
    *((_QWORD *)v17 + 8) = 0;
    *((_QWORD *)v17 + 9) = 0;
    *((_QWORD *)v17 + 10) = 0;
    *(_QWORD *)v17 = &CAntiVirusManager::`vftable';
  }
  else
  {
    v17 = 0;
  }
  WscServiceUtils::g_pAntiVirusManager = (CThirdPartyManager *)v17;
  v18 = (CSecureSettingsManager *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v18;
  if ( v18 )
    *(_QWORD *)v18 = 0;
  else
    v18 = 0;
  g_pSecureSettingsManager = v18;
  v19 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v19;
  if ( v19 )
  {
    v19[2] = 0;
    *((_QWORD *)v19 + 7) = 0;
    *((_QWORD *)v19 + 8) = 0;
    *((_QWORD *)v19 + 9) = 0;
    *((_QWORD *)v19 + 10) = 0;
    *(_QWORD *)v19 = &CAntiSpywareManager::`vftable';
  }
  else
  {
    v19 = 0;
  }
  WscServiceUtils::g_pAntiSpywareManager = (CThirdPartyManager *)v19;
  v20 = (HANDLE *)operator new(0x468u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v20;
  *(_QWORD *)SystemTimeAsFileTime = v20;
  if ( v20 )
  {
    *v20 = 0;
    v20[1] = 0;
    v20[2] = 0;
    v20[3] = 0;
    v20[4] = 0;
    v20[5] = 0;
    *((_DWORD *)v20 + 268) = 3;
    v20[135] = 0;
    v20[136] = 0;
    v20[137] = 0;
    v20[138] = 0;
    v20[139] = 0;
    memset_0(v20 + 6, 0, 0x200u);
    memset_0(v21 + 70, 0, 0x200u);
  }
  else
  {
    v21 = 0;
  }
  g_pThirdPartyMonitoring = v21;
  v22 = (struct CSecurityVerificationManager *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v22;
  if ( v22 )
  {
    *(_QWORD *)v22 = &CSecurityVerificationManagerAs::`vftable';
    *((_QWORD *)v22 + 1) = L"antispywareProductDisplayName";
    *((_QWORD *)v22 + 2) = L"antispywareProductExe";
  }
  else
  {
    v22 = 0;
  }
  WscServiceUtils::g_pAntiSpywareVerificationManager = v22;
  v23 = (struct CSecurityVerificationManager *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v23;
  if ( v23 )
  {
    *(_QWORD *)v23 = &CSecurityVerificationManagerAv::`vftable';
    *((_QWORD *)v23 + 1) = L"antivirusProductDisplayName";
    *((_QWORD *)v23 + 2) = L"antivirusProductExe";
  }
  else
  {
    v23 = 0;
  }
  WscServiceUtils::g_pAntiVirusVerificationManager = v23;
  v24 = (struct CSecurityVerificationManager *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)SystemTimeAsFileTime = v24;
  if ( v24 )
  {
    *(_QWORD *)v24 = &CSecurityVerificationManagerFw::`vftable';
    *((_QWORD *)v24 + 1) = L"firewallProductDisplayName";
    v26 = (CThirdPartyMonitoring *)L"firewallProductExe";
    *((_QWORD *)v24 + 2) = L"firewallProductExe";
  }
  else
  {
    v24 = 0;
  }
  WscServiceUtils::g_pFirewallVerificationManager = v24;
  if ( !g_pAlertStatus
    || !g_pWmiEventSinkAvFw
    || !g_pWmiEventManagerAvFw
    || !WscServiceUtils::g_pFirewallManager
    || !WscServiceUtils::g_pAntiVirusManager
    || !g_pSecureSettingsManager
    || !WscServiceUtils::g_pAntiSpywareManager
    || !g_pThirdPartyMonitoring
    || !WscServiceUtils::g_pAntiSpywareVerificationManager
    || !WscServiceUtils::g_pAntiVirusVerificationManager
    || !v24 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
      v29 = WPP_GLOBAL_Control;
    }
    inited = -2147024882;
LABEL_208:
    if ( v29 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v29 + 2), 85, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, g_bEnforceAmppl);
      v29 = WPP_GLOBAL_Control;
    }
    if ( inited < 0 )
      goto LABEL_266;
    goto LABEL_212;
  }
  g_hShutdownThreadNotify = CreateEventW(0, 1, 0, 0);
  inited = 0;
  if ( g_hShutdownThreadNotify )
  {
    v29 = WPP_GLOBAL_Control;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      inited = (unsigned __int16)LastError | 0x80070000;
    else
      inited = LastError;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
        (unsigned int)LastError);
      v29 = WPP_GLOBAL_Control;
    }
    if ( inited < 0 )
      goto LABEL_208;
  }
  if ( v29 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)v29 + 2), 77, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
  g_bEnforceAmppl = 0;
  g_bAmpplOneWayEnabled = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetImpl'::`2'::impl) )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
        g_bEnforceAmppl);
    }
    cbData = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Security Center\\Feature",
           L"DisableAvCheck",
           0x10u,
           0,
           &cbData,
           &pcbData) )
    {
      goto LABEL_200;
    }
    if ( cbData )
    {
      g_bEnforceAmppl = 0;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control )
        goto LABEL_212;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_208;
      v31 = 84;
      v32 = 0;
      goto LABEL_199;
    }
    g_bEnforceAmppl = 1;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control )
      goto LABEL_212;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_208;
    v31 = 83;
LABEL_198:
    v32 = 1;
LABEL_199:
    WPP_SF_d(*((_QWORD *)v29 + 2), v31, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v32);
LABEL_200:
    v29 = WPP_GLOBAL_Control;
    goto LABEL_208;
  }
  Variant = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetImpl'::`2'::impl);
  v26 = (CThirdPartyMonitoring *)((unsigned int)Variant - 1);
  if ( Variant == 1 )
  {
    g_bEnforceAmppl = 1;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control )
      goto LABEL_212;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_208;
    v31 = 78;
    goto LABEL_198;
  }
  if ( Variant != 2 )
  {
    g_bEnforceAmppl = 0;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control )
      goto LABEL_212;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_208;
    v31 = 81;
    v32 = 0;
    goto LABEL_199;
  }
  v33 = (WscServiceUtils::OneWayAMPPLEnablementAgent *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v34 = v33;
  *(_QWORD *)SystemTimeAsFileTime = v33;
  if ( !v33 )
  {
    v34 = 0;
    goto LABEL_168;
  }
  *(_QWORD *)Data = v33;
  *(_QWORD *)v33 = 0;
  *((_QWORD *)v33 + 1) = 0;
  *(_QWORD *)v33 = std::_List_alloc<0,std::_List_base_types<std::wstring>>::_Buynode0(v26, 0, 0);
  *((_QWORD *)v34 + 2) = 0;
  *((_QWORD *)v34 + 3) = 0;
  *((_QWORD *)v34 + 4) = 0;
  *((_DWORD *)v34 + 14) = 1065353216;
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(
    v34,
    8);
  *((_QWORD *)v34 + 8) = 0;
  *((_QWORD *)v34 + 10) = L"D:P(A;;FA;;;S-1-5-80-3232712927-1625117661-2590453128-1738570065-3637376297)";
  *(_QWORD *)Data = 0;
  cbData = 0;
  ValueW = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Security Center\\NCP",
             0,
             0,
             0,
             0xF003Fu,
             0,
             (PHKEY)Data,
             &cbData);
  v36 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v36 = ValueW < 0;
  }
  if ( v36 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_99;
    }
    v38 = 26;
LABEL_98:
    WPP_SF_d(*((_QWORD *)v37 + 2), v38, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, (unsigned int)ValueW);
LABEL_99:
    if ( *(_QWORD *)Data )
      RegCloseKey(*(HKEY *)Data);
    v39 = 0;
    goto LABEL_113;
  }
  pvData = 0;
  cbData = 4;
  ValueW = RegGetValueW(*(HKEY *)Data, 0, L"NumNCP", 0x10u, 0, &pvData, &cbData);
  v40 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v40 = ValueW < 0;
  }
  if ( v40 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_99;
    }
    v38 = 27;
    goto LABEL_98;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, pvData);
  v39 = pvData == 0;
  if ( *(_QWORD *)Data )
    RegCloseKey(*(HKEY *)Data);
LABEL_113:
  *((_BYTE *)v34 + 72) = v39;
  *(_QWORD *)Data = 0;
  cbData = 0;
  v41 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Security Center\\NCP",
          0,
          0,
          0,
          0xF003Fu,
          0,
          (PHKEY)Data,
          &cbData);
  v42 = v41 < 0;
  if ( v41 > 0 )
  {
    v41 = (unsigned __int16)v41 | 0x80070000;
    v42 = v41 < 0;
  }
  if ( v42 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
        (unsigned int)v41);
    }
    goto LABEL_134;
  }
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(*((LPCWSTR *)v34 + 10), 1u, &SecurityDescriptor, 0) )
  {
    v43 = RegSetKeySecurity(*(HKEY *)Data, 4u, SecurityDescriptor);
    v46 = v43 < 0;
    if ( v43 > 0 )
    {
      v43 = (unsigned __int16)v43 | 0x80070000;
      v46 = v43 < 0;
    }
    if ( !v46 )
      goto LABEL_132;
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_132;
    }
    v45 = 41;
  }
  else
  {
    v43 = GetLastError();
    if ( v43 > 0 )
      v43 = (unsigned __int16)v43 | 0x80070000;
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_132;
    }
    v45 = 40;
  }
  WPP_SF_d(*((_QWORD *)v44 + 2), v45, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, (unsigned int)v43);
LABEL_132:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
LABEL_134:
  if ( *(_QWORD *)Data )
    RegCloseKey(*(HKEY *)Data);
  Mutex = CreateMutexExW(0, 0, 0, 0x1F0001u);
  if ( Mutex )
  {
    GetLastError();
    v50 = (void *)*((_QWORD *)v34 + 8);
    if ( v50 )
    {
      v51 = GetLastError();
      if ( !CloseHandle(v50) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v52, v53);
      SetLastError(v51);
    }
    *((_QWORD *)v34 + 8) = Mutex;
LABEL_145:
    *(_QWORD *)SystemTimeAsFileTime = 0;
    dwDisposition = 0;
    v54 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Security Center\\NCP",
            0,
            0,
            0,
            0xF003Fu,
            0,
            (PHKEY)SystemTimeAsFileTime,
            &dwDisposition);
    v55 = v54;
    if ( v54 > 0 )
      v55 = (unsigned __int16)v54 | 0x80070000;
    if ( v55 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
          (unsigned int)v55);
        v29 = WPP_GLOBAL_Control;
      }
      v26 = *(CThirdPartyMonitoring **)SystemTimeAsFileTime;
      if ( *(_QWORD *)SystemTimeAsFileTime )
      {
        RegCloseKey(*(HKEY *)SystemTimeAsFileTime);
        v29 = WPP_GLOBAL_Control;
      }
      goto LABEL_163;
    }
    v137 = 0;
    v56 = RegSetKeyValueW(*(HKEY *)SystemTimeAsFileTime, 0, L"NumNCP", 4u, &v137, 4u);
    v55 = v56;
    if ( v56 > 0 )
      v55 = (unsigned __int16)v56 | 0x80070000;
    if ( v55 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_160:
        v26 = *(CThirdPartyMonitoring **)SystemTimeAsFileTime;
        if ( *(_QWORD *)SystemTimeAsFileTime )
        {
          RegCloseKey(*(HKEY *)SystemTimeAsFileTime);
          v29 = WPP_GLOBAL_Control;
        }
        if ( v55 >= 0 )
          goto LABEL_169;
LABEL_163:
        if ( v29 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)v29 + 2), 25, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, (unsigned int)v55);
        *((_BYTE *)v34 + 72) = 0;
        goto LABEL_168;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
        (unsigned int)v55);
    }
    v29 = WPP_GLOBAL_Control;
    goto LABEL_160;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v47);
  if ( LastErrorFailHr >= 0 )
    goto LABEL_145;
  v29 = WPP_GLOBAL_Control;
  v26 = (CThirdPartyMonitoring *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
      (unsigned int)LastErrorFailHr);
LABEL_168:
    v29 = WPP_GLOBAL_Control;
  }
LABEL_169:
  v57 = g_pOneWayAMPPLEnablementAgent;
  g_pOneWayAMPPLEnablementAgent = v34;
  if ( v57 )
  {
    v58 = (void *)*((_QWORD *)v57 + 8);
    if ( v58 && !CloseHandle(v58) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v59, v60);
    v61 = (void *)*((_QWORD *)v57 + 2);
    if ( v61 )
    {
      operator delete(v61);
      *((_QWORD *)v57 + 2) = 0;
      *((_QWORD *)v57 + 3) = 0;
      *((_QWORD *)v57 + 4) = 0;
    }
    v62 = **(void ****)v57;
    **(_QWORD **)v57 = *(_QWORD *)v57;
    *(_QWORD *)(*(_QWORD *)v57 + 8LL) = *(_QWORD *)v57;
    *((_QWORD *)v57 + 1) = 0;
    v63 = *(void ***)v57;
    if ( v62 != *(void ***)v57 )
    {
      do
      {
        v64 = (void **)*v62;
        if ( (unsigned __int64)v62[5] >= 8 )
          operator delete(v62[2]);
        v62[5] = (void *)7;
        v62[4] = 0;
        *((_WORD *)v62 + 8) = 0;
        operator delete(v62);
        v62 = v64;
        v63 = *(void ***)v57;
      }
      while ( v64 != *(void ***)v57 );
    }
    operator delete(v63);
    operator delete(v57);
    v29 = WPP_GLOBAL_Control;
    v34 = g_pOneWayAMPPLEnablementAgent;
  }
  if ( v34 )
  {
    g_bEnforceAmppl = *((_BYTE *)v34 + 72);
    g_bAmpplOneWayEnabled = g_bEnforceAmppl;
  }
  else
  {
    g_bEnforceAmppl = 0;
    if ( v29 == (CThirdPartyManager *)&WPP_GLOBAL_Control )
      goto LABEL_212;
    if ( (*((_BYTE *)v29 + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)v29 + 2), 79, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
      v29 = WPP_GLOBAL_Control;
    }
  }
  if ( v29 != (CThirdPartyManager *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v29 + 28) & 4) == 0 )
      goto LABEL_208;
    v32 = g_bEnforceAmppl;
    v31 = 80;
    goto LABEL_199;
  }
LABEL_212:
  g_dwFwMigrated = 0;
  pvData = 0;
  v139 = 4;
  v65 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Security Center\\Provider\\Fw",
          L"DataMigrated",
          0x10u,
          0,
          &pvData,
          &v139);
  if ( v65 )
  {
    v66 = g_dwFwMigrated;
  }
  else
  {
    v66 = pvData;
    g_dwFwMigrated = pvData;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v66);
  if ( (unsigned int)dword_180053218 > 5
    && (qword_180053228 & 0x400000000000LL) != 0
    && (qword_180053230 & 0x400000000000LL) == qword_180053230 )
  {
    if ( v65 > 0 )
      v65 = (unsigned __int16)v65 | 0x80070000;
    v140 = v65;
    v141 = pvData;
    v142 = 1;
    v157 = &v140;
    v158 = 4;
    v155 = &v141;
    v156 = 4;
    v153 = &v142;
    v154 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0x400000000000LL;
    UserData.Ptr = (ULONGLONG)off_180053220;
    UserData.Size = *(unsigned __int16 *)off_180053220;
    UserData.Reserved = 2;
    v150 = byte_18004C219;
    v151 = 74;
    v152 = 1;
    Type = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  g_dwAvMigrated = 0;
  Type = 0;
  v143 = 4;
  v67 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Security Center\\Provider\\Av",
          L"DataMigrated",
          0x10u,
          0,
          &Type,
          &v143);
  if ( v67 )
  {
    v68 = g_dwAvMigrated;
  }
  else
  {
    v68 = Type;
    g_dwAvMigrated = Type;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v68);
  if ( (unsigned int)dword_180053218 > 5
    && (qword_180053228 & 0x400000000000LL) != 0
    && (qword_180053230 & 0x400000000000LL) == qword_180053230 )
  {
    if ( v67 > 0 )
      v67 = (unsigned __int16)v67 | 0x80070000;
    v144 = v67;
    v145 = Type;
    LODWORD(SecurityDescriptor) = 0;
    v167 = &v144;
    v168 = 4;
    v165 = &v145;
    v166 = 4;
    p_SecurityDescriptor = &SecurityDescriptor;
    v164 = 4;
    *(_DWORD *)&v147.Id = 184549376;
    *(_DWORD *)&v147.Level = 5;
    v147.Keyword = 0x400000000000LL;
    v159.Ptr = (ULONGLONG)off_180053220;
    v159.Size = *(unsigned __int16 *)off_180053220;
    v159.Reserved = 2;
    v160 = byte_18004C1C3;
    v161 = 74;
    v162 = 1;
    *(_DWORD *)Data = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v147, 0, 0, 5u, &v159);
  }
  inited = CreateRemovedProductsList(&hKey);
  if ( inited < 0 )
    goto LABEL_264;
  v69 = g_pSecureSettingsManager;
  v70 = g_pAlertStatus;
  inited = CAlertStatus::InitCriticalSection((CAlertStatus *)g_pAlertStatus);
  if ( inited < 0 )
    goto LABEL_244;
  v71 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v71 )
  {
    v70[1].LockSemaphore = 0;
    inited = -2147024882;
LABEL_244:
    LockSemaphore = (char *)v70[1].LockSemaphore;
    if ( LockSemaphore )
    {
      if ( *(_DWORD *)LockSemaphore )
      {
        v75 = LockSemaphore + 56;
        while ( 1 )
        {
          for ( i = (_QWORD *)*v75; !i[2]; i = (_QWORD *)*i )
            ;
          v77 = 0;
          if ( i != v75 )
            v77 = (_QWORD **)i;
          v78 = (struct _RTL_CRITICAL_SECTION *)(LockSemaphore + 8);
          if ( !v77 )
            break;
          EnterCriticalSection(v78);
          *v77[1] = *v77;
          (*v77)[1] = v77[1];
          --*((_DWORD *)LockSemaphore + 12);
          LeaveCriticalSection((LPCRITICAL_SECTION)(LockSemaphore + 8));
          operator delete(v77);
        }
        *v75 = v75;
        *((_QWORD *)LockSemaphore + 8) = v75;
        DeleteCriticalSection(v78);
        *(_DWORD *)LockSemaphore = 0;
      }
      operator delete(LockSemaphore);
    }
    v70[1].LockSemaphore = 0;
    goto LABEL_264;
  }
  *v71 = 0;
  v71[12] = 0;
  *((_QWORD *)v71 + 7) = v71 + 14;
  *((_QWORD *)v71 + 8) = v71 + 14;
  *((_QWORD *)v71 + 9) = v71 + 14;
  v70[1].LockSemaphore = v71;
  v72 = CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::Initialize(v71);
  inited = v72;
  if ( v72 > 0 )
    inited = (unsigned __int16)v72 | 0x80070000;
  if ( inited < 0 )
    goto LABEL_244;
  v70[1].SpinCount = (ULONG_PTR)v69;
  dwLowDateTime = v135.dwLowDateTime;
  inited = CThirdPartyManager::Initialize(
             WscServiceUtils::g_pFirewallManager,
             WscServiceUtils::g_pFirewallVerificationManager,
             v73,
             v135.dwLowDateTime);
  if ( inited >= 0 )
  {
    inited = CThirdPartyManager::Initialize(
               WscServiceUtils::g_pAntiVirusManager,
               WscServiceUtils::g_pAntiVirusVerificationManager,
               v80,
               dwLowDateTime);
    if ( inited >= 0 )
    {
      v81 = g_pSecureSettingsManager;
      v82 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v82 )
      {
        *v82 = &CLuaSettingsChecktoid::`vftable';
        v82[1] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System";
        *(_QWORD *)v81 = v82;
        inited = CThirdPartyManager::Initialize(
                   WscServiceUtils::g_pAntiSpywareManager,
                   WscServiceUtils::g_pAntiSpywareVerificationManager,
                   v83,
                   dwLowDateTime);
        if ( inited >= 0 )
        {
          inited = CThirdPartyMonitoring::Initialize(v26, v25, v84, v85, phkResult);
          if ( inited >= 0 )
          {
            inited = CWmiEventSinkAvFw::Initialize(v26, v25, v86, v87, phkResulta);
            v4 = hKey;
            if ( inited >= 0 )
              goto LABEL_269;
            goto LABEL_265;
          }
        }
      }
      else
      {
        *(_QWORD *)v81 = 0;
        inited = -2147024882;
      }
    }
  }
LABEL_264:
  v4 = hKey;
LABEL_265:
  v29 = WPP_GLOBAL_Control;
LABEL_266:
  if ( v29 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v29 + 2), 88, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)inited);
LABEL_269:
  if ( inited < 0 )
    goto LABEL_411;
  v88 = CWmiEventManager::Initialize(v26, (struct IWbemObjectSink *)v25);
  if ( v88 < 0 )
  {
    v107 = g_pWmiEventManagerAvFw;
    if ( g_pWmiEventManagerAvFw )
    {
      CWmiEventManager::~CWmiEventManager(g_pWmiEventManagerAvFw);
      operator delete(v107);
    }
    g_pWmiEventManagerAvFw = 0;
    (*(void (__fastcall **)(struct CWmiEventSinkAvFw *))(*(_QWORD *)g_pWmiEventSinkAvFw + 16LL))(g_pWmiEventSinkAvFw);
    g_pWmiEventSinkAvFw = 0;
    EvtLog_LogErrorWithHresult(0xC0000003, v88);
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
        (unsigned int)v88);
    }
    goto LABEL_340;
  }
  if ( (int)CreateUpgradableProductsList(
              g_pWmiEventManagerAvFw,
              v4,
              &g_UpgradableProducts,
              &g_RemovedButNotUpgradableProducts) >= 0 )
    goto LABEL_275;
  v89 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
LABEL_275:
    v89 = WPP_GLOBAL_Control;
  }
  if ( g_dwFwMigrated )
  {
    if ( v89 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v89 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v89 + 2), 93, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    DatastoreInstances = CThirdPartyManager::LoadDatastoreInstances(WscServiceUtils::g_pFirewallManager, (__int64)v4);
    v91 = DatastoreInstances;
    if ( DatastoreInstances >= 0 )
      goto LABEL_292;
    EvtLog_LogErrorWithHresult(0xC0000012, DatastoreInstances);
    v92 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v93 = 94;
      goto LABEL_291;
    }
  }
  else
  {
    if ( v89 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v89 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v89 + 2), 91, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    WmiInstances = CThirdPartyManager::LoadWmiInstances(
                     WscServiceUtils::g_pFirewallManager,
                     SECURITY_PRODUCT_TYPE_FIREWALL);
    v91 = WmiInstances;
    if ( WmiInstances >= 0 )
      goto LABEL_292;
    EvtLog_LogErrorWithHresult(0xC0000004, WmiInstances);
    v92 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v93 = 92;
LABEL_291:
      WPP_SF_d(*((_QWORD *)v92 + 2), v93, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v91);
LABEL_292:
      v92 = WPP_GLOBAL_Control;
    }
  }
  if ( g_dwAvMigrated )
  {
    if ( v92 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v92 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v92 + 2), 97, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    v99 = CThirdPartyManager::LoadDatastoreInstances(WscServiceUtils::g_pAntiVirusManager, (__int64)v4);
    inited = v99;
    if ( v99 < 0 )
    {
      EvtLog_LogErrorWithHresult(0xC0000013, v99);
      v97 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_309;
      }
      v98 = 98;
      goto LABEL_308;
    }
  }
  else
  {
    if ( v92 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v92 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v92 + 2), 95, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    v95 = CThirdPartyManager::LoadWmiInstances(WscServiceUtils::g_pAntiVirusManager, SECURITY_PRODUCT_TYPE_ANTIVIRUS);
    inited = v95;
    if ( v95 < 0 )
    {
      EvtLog_LogErrorWithHresult(0xC0000005, v95);
      v97 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_309;
      }
      v98 = 96;
LABEL_308:
      WPP_SF_d(*((_QWORD *)v97 + 2), v98, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)inited);
LABEL_309:
      inited = 0;
    }
  }
  if ( v4 && *((int *)v4 + 12) > 0 )
  {
    if ( !*((_DWORD *)WscServiceUtils::g_pAntiVirusManager + 21) )
    {
LABEL_332:
      Thread = CreateThread(0, 0, WscEnableDefenderOnUpgradeThreadProc, 0, 0, 0);
      CloseHandle(Thread);
      EvtLog_LogInformational(0x4000000Cu);
      WscRemoveRegKey(v104, L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaAvPaths");
      WscRemoveRegKey(v105, L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaAvPathsExpiredSetup");
      goto LABEL_333;
    }
    hKey = 0;
    v135 = 0;
    *(_QWORD *)Data = 0;
    GetSystemTimeAsFileTime(&v135);
    *(struct _FILETIME *)Data = v135;
    v100 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Security Center\\Svc\\Upgrade",
             0,
             0,
             0,
             0x20007u,
             0,
             &hKey,
             0);
    inited = v100;
    if ( v100 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v100);
      }
      if ( inited <= 0 )
        goto LABEL_327;
      inited = (unsigned __int16)inited;
    }
    else
    {
      inited = 0;
      v101 = RegSetValueExW(hKey, L"UpgradeTime", 0, 0xBu, Data, 8u);
      v102 = v101;
      if ( !v101 )
        goto LABEL_327;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v101);
      }
      if ( v102 <= 0 )
      {
        inited = v102;
        goto LABEL_327;
      }
      inited = (unsigned __int16)v102;
    }
    inited |= 0x80070000;
LABEL_327:
    RegCloseKey(hKey);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
      }
      inited = 0;
    }
    goto LABEL_332;
  }
LABEL_333:
  LOBYTE(v96) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
    v96);
  AMPPLWmiDataUtils::CleanupAllAMPPLDataFromWMI(v106);
  if ( inited < 0 )
    goto LABEL_411;
LABEL_340:
  g_bRunning = 1;
  IsAlerted = CThirdPartyManager::IsAlerted(WscServiceUtils::g_pAntiVirusManager);
  v109 = CAlertStatus::SetComponentAlerted(g_pAlertStatus, 1u, IsAlerted);
  inited = v109;
  if ( v109 < 0 )
  {
    v110 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v111 = 100;
LABEL_406:
      WPP_SF_d(*((_QWORD *)v110 + 2), v111, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)v109);
      goto LABEL_411;
    }
    goto LABEL_411;
  }
  v112 = CThirdPartyManager::IsAlerted(WscServiceUtils::g_pFirewallManager);
  v109 = CAlertStatus::SetComponentAlerted(g_pAlertStatus, 2u, v112);
  inited = v109;
  if ( v109 >= 0 )
  {
    v113 = CThirdPartyManager::IsAlerted(WscServiceUtils::g_pAntiSpywareManager);
    v109 = CAlertStatus::SetComponentAlerted(g_pAlertStatus, 8u, v113);
    inited = v109;
    if ( v109 < 0 )
    {
      v110 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v111 = 102;
        goto LABEL_406;
      }
      goto LABEL_411;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      v116 = WPP_GLOBAL_Control;
    }
    else
    {
      v115 = GetLastError();
      if ( v115 > 0 )
        inited = (unsigned __int16)v115 | 0x80070000;
      else
        inited = v115;
      v116 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
          (unsigned int)v115);
        v116 = WPP_GLOBAL_Control;
      }
      if ( inited < 0 )
        goto LABEL_411;
    }
    if ( v116 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v116 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v116 + 2), 104, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
    v117 = g_pThirdPartyMonitoring;
    CurrentProcess = GetCurrentProcess();
    v119 = GetCurrentProcess();
    if ( DuplicateHandle(v119, EventW, CurrentProcess, v117, 0, 0, 2u) )
    {
      inited = 0;
      v120 = CreateThread(0, 0, CThirdPartyMonitoring::MonitoringThreadProcEntry, v117, 0, 0);
      v117[2] = v120;
      if ( v120 )
        goto LABEL_371;
    }
    else
    {
      *v117 = 0;
    }
    v121 = GetLastError();
    inited = v121;
    if ( v121 > 0 )
      inited = (unsigned __int16)v121 | 0x80070000;
LABEL_371:
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
          (unsigned int)inited);
      }
    }
    else if ( WaitForSingleObject(EventW, 0xEA60u) )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
          (unsigned int)inited);
      }
      inited = -2147467259;
    }
    if ( EventW )
      CloseHandle(EventW);
    if ( inited >= 0 )
    {
      v122 = StartupRpc();
      if ( v122 )
      {
        if ( v122 > 0 )
          inited = (unsigned __int16)v122 | 0x80070000;
        else
          inited = v122;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            107,
            WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
            (unsigned int)v122);
        }
      }
      else
      {
        WscNotifyRpcStateChange(1);
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
        }
        g_hThreadSystemMonitor = CreateThread(0, 0, SystemMonitoringThreadProc, 0, 0, 0);
        if ( g_hThreadSystemMonitor )
          goto LABEL_402;
        v123 = GetLastError();
        if ( v123 > 0 )
          inited = (unsigned __int16)v123 | 0x80070000;
        else
          inited = v123;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            109,
            WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
            (unsigned int)v123);
        }
        if ( inited >= 0 )
        {
LABEL_402:
          v109 = WscMonitorExpiredState();
          inited = v109;
          if ( v109 >= 0 )
          {
            if ( qword_180054068 )
            {
              *(_QWORD *)&SystemTimeAsFileTime[4] = 0;
              *(_DWORD *)SystemTimeAsFileTime = 4;
              GetSystemTimeAsFileTime((LPFILETIME)&SystemTimeAsFileTime[4]);
              RtlPublishWnfStateData(WNF_WSC_SECURITY_CENTER_USER_NOTIFICATION, 0, SystemTimeAsFileTime, 12, 0);
            }
            if ( qword_180054088 )
            {
              *(_QWORD *)&SystemTimeAsFileTime[4] = 0;
              *(_DWORD *)SystemTimeAsFileTime = 5;
              GetSystemTimeAsFileTime((LPFILETIME)&SystemTimeAsFileTime[4]);
              RtlPublishWnfStateData(WNF_WSC_SECURITY_CENTER_USER_NOTIFICATION, 0, SystemTimeAsFileTime, 12, 0);
            }
          }
          else
          {
            v110 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v111 = 110;
              goto LABEL_406;
            }
          }
        }
      }
    }
    goto LABEL_411;
  }
  v110 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v111 = 101;
    goto LABEL_406;
  }
LABEL_411:
  if ( v4 )
    DeleteRemovedProductsList(v4);
  if ( inited < 0 )
  {
    WscCleanup();
  }
  else
  {
    g_hInitSystem = CreateThread(0, 0, WscInitSystemOnBootThreadProc, 0, 0, 0);
    v124 = RegisterEventSourceW(0, L"SecurityCenter");
    v125 = v124;
    if ( v124 )
    {
      if ( !ReportEventW(v124, 4u, 0, 1u, 0, 0, 0, 0, 0) )
        GetLastError();
      DeregisterEventSource(v125);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001d9e0  push    rbp
0x18001d9e2  push    rbx
0x18001d9e3  push    rsi
0x18001d9e4  push    rdi
0x18001d9e5  push    r12
0x18001d9e7  push    r13
0x18001d9e9  push    r14
0x18001d9eb  push    r15
0x18001d9ed  lea     rbp, [rsp-0A8h]
0x18001d9f5  sub     rsp, 1A8h
0x18001d9fc  mov     rax, cs:__security_cookie
0x18001da03  xor     rax, rsp
0x18001da06  mov     [rbp+0E0h+var_50], rax
0x18001da0d  mov     [rbp+0E0h+var_160.dwLowDateTime], ecx
0x18001da10  xor     r15d, r15d
0x18001da13  lea     r14, WPP_GLOBAL_Control
0x18001da1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da21  cmp     rcx, r14
0x18001da24  jz      short loc_18001DA41
0x18001da26  test    byte ptr [rcx+1Ch], 4
0x18001da2a  jz      short loc_18001DA41
0x18001da2c  mov     edx, 47h ; 'G'
0x18001da31  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x18001da38  mov     rcx, [rcx+10h]
0x18001da3c  call    WPP_SF_
0x18001da41  mov     [rsp+1E0h+hKey], r15
0x18001da46  lea     rax, [rsp+1E0h+hKey]
0x18001da4b  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18001da50  mov     r9d, 20007h; samDesired
0x18001da56  xor     r8d, r8d; ulOptions
0x18001da59  lea     r13, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Security Center\\S"...
0x18001da60  mov     rdx, r13; lpSubKey
0x18001da63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001da6a  call    cs:__imp_RegOpenKeyExW
0x18001da70  test    eax, eax
0x18001da72  jnz     loc_18001DB48
0x18001da78  mov     [rsp+1E0h+cbData], 8
0x18001da80  mov     qword ptr [rsp+1E0h+Data], r15
0x18001da85  mov     [rsp+1E0h+Type], 0Bh
0x18001da8d  lea     rax, [rsp+1E0h+cbData]
0x18001da92  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x18001da97  lea     rax, [rsp+1E0h+Data]
0x18001da9c  mov     [rsp+1E0h+phkResult], rax; lpData
0x18001daa1  lea     r9, [rsp+1E0h+Type]; lpType
0x18001daa6  xor     r8d, r8d; lpReserved
0x18001daa9  lea     rbx, aVistasp1; "VistaSp1"
0x18001dab0  mov     rdx, rbx; lpValueName
0x18001dab3  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001dab8  call    cs:__imp_RegQueryValueExW
0x18001dabe  test    eax, eax
0x18001dac0  jnz     short loc_18001DAC9
0x18001dac2  cmp     [rsp+1E0h+Type], 0Bh
0x18001dac7  jz      short loc_18001DB36
0x18001dac9  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18001dacd  lea     rcx, [rbp+0E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001dad1  call    cs:__imp_GetSystemTimeAsFileTime
0x18001dad7  mov     dword ptr [rsp+1E0h+lpcbData], 8; cbData
0x18001dadf  lea     rax, [rbp+0E0h+SystemTimeAsFileTime]
0x18001dae3  mov     [rsp+1E0h+phkResult], rax; lpData
0x18001dae8  mov     r9d, 0Bh; dwType
0x18001daee  xor     r8d, r8d; Reserved
0x18001daf1  mov     rdx, rbx; lpValueName
0x18001daf4  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001daf9  call    cs:__imp_RegSetValueExW
0x18001daff  test    eax, eax
0x18001db01  jz      short loc_18001DB36
0x18001db03  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db0a  cmp     rcx, r14
0x18001db0d  jz      short loc_18001DB36
0x18001db0f  test    byte ptr [rcx+1Ch], 1
0x18001db13  jz      short loc_18001DB36
0x18001db15  mov     edx, 12h
0x18001db1a  mov     dword ptr [rsp+1E0h+lpcbData], eax
0x18001db1e  mov     [rsp+1E0h+phkResult], rbx
0x18001db23  mov     r9, r13
0x18001db26  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x18001db2d  mov     rcx, [rcx+10h]
0x18001db31  call    WPP_SF_SSd
0x18001db36  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001db3b  call    cs:__imp_RegCloseKey
0x18001db41  mov     [rsp+1E0h+hKey], r15
0x18001db46  jmp     short loc_18001DB76
0x18001db48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db4f  cmp     rcx, r14
0x18001db52  jz      short loc_18001DB76
0x18001db54  test    byte ptr [rcx+1Ch], 1
0x18001db58  jz      short loc_18001DB76
0x18001db5a  mov     edx, 13h
0x18001db5f  mov     dword ptr [rsp+1E0h+phkResult], eax
0x18001db63  mov     r9, r13
0x18001db66  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x18001db6d  mov     rcx, [rcx+10h]
0x18001db71  call    WPP_SF_Sd
0x18001db76  mov     r12, r15
0x18001db79  mov     [rsp+1E0h+hKey], r15
0x18001db7e  mov     cs:?g_OfflineScanInitiated@@3JC, r15d; long volatile g_OfflineScanInitiated
0x18001db85  mov     cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA, r15; CAlertStatus * g_pAlertStatus
0x18001db8c  mov     cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA, r15; CFirewallManager * WscServiceUtils::g_pFirewallManager
0x18001db93  mov     cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA, r15; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x18001db9a  mov     cs:?g_pSecureSettingsManager@@3PEAVCSecureSettingsManager@@EA, r15; CSecureSettingsManager * g_pSecureSettingsManager
0x18001dba1  mov     cs:?g_pAntiSpywareManager@WscServiceUtils@@3PEAVCAntiSpywareManager@@EA, r15; CAntiSpywareManager * WscServiceUtils::g_pAntiSpywareManager
0x18001dba8  mov     cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA, r15; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x18001dbaf  mov     cs:?g_pAntiSpywareVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAs@@EA, r15; CSecurityVerificationManagerAs * WscServiceUtils::g_pAntiSpywareVerificationManager
0x18001dbb6  mov     cs:?g_pAntiVirusVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAv@@EA, r15; CSecurityVerificationManagerAv * WscServiceUtils::g_pAntiVirusVerificationManager
0x18001dbbd  mov     cs:?g_pFirewallVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerFw@@EA, r15; CSecurityVerificationManagerFw * WscServiceUtils::g_pFirewallVerificationManager
0x18001dbc4  mov     cs:?g_pampplToastThrottler@@3PEAV?$NotificationThrottler@VRegistryValuesStorage@@VAMPPLToastData@@VSendAMPPLToastNotificationFunctor@@@Throttler@@EA, r15; Throttler::NotificationThrottler<RegistryValuesStorage,AMPPLToastData,SendAMPPLToastNotificationFunctor> * g_pampplToastThrottler
0x18001dbcb  mov     cs:?g_pregistryValuesStorage@@3PEAVRegistryValuesStorage@@EA, r15; RegistryValuesStorage * g_pregistryValuesStorage
0x18001dbd2  mov     cs:?g_pWDSPNotificationFunctor@@3PEAVSendAMPPLToastNotificationFunctor@@EA, r15; SendAMPPLToastNotificationFunctor * g_pWDSPNotificationFunctor
0x18001dbd9  mov     rdi, cs:?g_pOneWayAMPPLEnablementAgent@@3V?$unique_ptr@VOneWayAMPPLEnablementAgent@WscServiceUtils@@U?$default_delete@VOneWayAMPPLEnablementAgent@WscServiceUtils@@@wistd@@@wistd@@A; wistd::unique_ptr<WscServiceUtils::OneWayAMPPLEnablementAgent,wistd::default_delete<WscServiceUtils::OneWayAMPPLEnablementAgent>> g_pOneWayAMPPLEnablementAgent
0x18001dbe0  mov     cs:?g_pOneWayAMPPLEnablementAgent@@3V?$unique_ptr@VOneWayAMPPLEnablementAgent@WscServiceUtils@@U?$default_delete@VOneWayAMPPLEnablementAgent@WscServiceUtils@@@wistd@@@wistd@@A, r15; wistd::unique_ptr<WscServiceUtils::OneWayAMPPLEnablementAgent,wistd::default_delete<WscServiceUtils::OneWayAMPPLEnablementAgent>> g_pOneWayAMPPLEnablementAgent
0x18001dbe7  test    rdi, rdi
0x18001dbea  jz      loc_18001DC88
0x18001dbf0  mov     rcx, [rdi+40h]; hObject
0x18001dbf4  test    rcx, rcx
0x18001dbf7  jz      short loc_18001DC0E
0x18001dbf9  call    cs:__imp_CloseHandle
0x18001dbff  mov     rcx, [rbp+0E8h]; this
0x18001dc06  test    eax, eax
0x18001dc08  jz      loc_18001F80E
0x18001dc0e  mov     rcx, [rdi+10h]; Block
0x18001dc12  test    rcx, rcx
0x18001dc15  jz      short loc_18001DC28
0x18001dc17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dc1c  mov     [rdi+10h], r15
0x18001dc20  mov     [rdi+18h], r15
0x18001dc24  mov     [rdi+20h], r15
0x18001dc28  mov     rax, [rdi]
0x18001dc2b  mov     rbx, [rax]
0x18001dc2e  mov     [rax], rax
0x18001dc31  mov     rax, [rdi]
0x18001dc34  mov     [rax+8], rax
0x18001dc38  mov     [rdi+8], r15
0x18001dc3c  mov     rcx, [rdi]
0x18001dc3f  cmp     rbx, rcx
0x18001dc42  jz      short loc_18001DC7B
0x18001dc44  mov     rsi, [rbx]
0x18001dc47  cmp     qword ptr [rbx+28h], 8
0x18001dc4c  jb      short loc_18001DC57
0x18001dc4e  mov     rcx, [rbx+10h]; Block
0x18001dc52  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dc57  mov     qword ptr [rbx+28h], 7
0x18001dc5f  mov     [rbx+20h], r15
0x18001dc63  mov     [rbx+10h], r15w
0x18001dc68  mov     rcx, rbx; Block
0x18001dc6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dc70  mov     rbx, rsi
0x18001dc73  mov     rcx, [rdi]; Block
0x18001dc76  cmp     rsi, rcx
0x18001dc79  jnz     short loc_18001DC44
0x18001dc7b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dc80  mov     rcx, rdi; Block
0x18001dc83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dc88  call    ?Initialize@CCriticalSection@@QEAAJXZ; CCriticalSection::Initialize(void)
0x18001dc8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc94  cmp     rcx, r14
0x18001dc97  jz      short loc_18001DCB4
0x18001dc99  test    byte ptr [rcx+1Ch], 4
0x18001dc9d  jz      short loc_18001DCB4
0x18001dc9f  mov     edx, 49h ; 'I'
0x18001dca4  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x18001dcab  mov     rcx, [rcx+10h]
0x18001dcaf  call    WPP_SF_
0x18001dcb4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dcbb  mov     ecx, 50h ; 'P'; unsigned __int64
0x18001dcc0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001dcc5  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001dcc9  test    rax, rax
0x18001dccc  jz      short loc_18001DCE0
0x18001dcce  mov     [rax+28h], r15
0x18001dcd2  mov     [rax+30h], r15
0x18001dcd6  mov     [rax+38h], r13
0x18001dcda  mov     [rax+40h], r15
0x18001dcde  jmp     short loc_18001DCE3
0x18001dce0  mov     rax, r15
0x18001dce3  mov     cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA, rax; CAlertStatus * g_pAlertStatus
0x18001dcea  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dcf1  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001dcf6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001dcfb  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001dcff  test    rax, rax
0x18001dd02  jz      short loc_18001DD27
0x18001dd04  lea     rcx, ??_7CWmiEventSinkAvFw@@6B@; const CWmiEventSinkAvFw::`vftable'
0x18001dd0b  mov     [rax], rcx
0x18001dd0e  mov     [rax+8], r15
0x18001dd12  mov     [rax+10h], r15
0x18001dd16  mov     [rax+20h], r15
0x18001dd1a  mov     [rax+50h], r15d
0x18001dd1e  mov     dword ptr [rax+54h], 1
0x18001dd25  jmp     short loc_18001DD2A
0x18001dd27  mov     rax, r15
0x18001dd2a  mov     cs:?g_pWmiEventSinkAvFw@@3PEAVCWmiEventSinkAvFw@@EA, rax; CWmiEventSinkAvFw * g_pWmiEventSinkAvFw
0x18001dd31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dd38  mov     ecx, 50h ; 'P'; unsigned __int64
0x18001dd3d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001dd42  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001dd46  test    rax, rax
0x18001dd49  jz      short loc_18001DD7B
0x18001dd4b  mov     [rax+8], r15
0x18001dd4f  mov     [rax+10h], r15
0x18001dd53  mov     [rax+18h], r15
0x18001dd57  mov     [rax+20h], r15
0x18001dd5b  mov     [rax+28h], r15
0x18001dd5f  mov     [rax+30h], r15
0x18001dd63  mov     [rax+38h], r15
0x18001dd67  mov     [rax+40h], r15
0x18001dd6b  mov     [rax+48h], r15d
0x18001dd6f  lea     rcx, ??_7CWmiEventManagerAvFw@@6B@; const CWmiEventManagerAvFw::`vftable'
0x18001dd76  mov     [rax], rcx
0x18001dd79  jmp     short loc_18001DD7E
0x18001dd7b  mov     rax, r15
0x18001dd7e  mov     cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA, rax; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x18001dd85  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dd8c  mov     ecx, 60h ; '`'; unsigned __int64
0x18001dd91  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001dd96  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001dd9a  test    rax, rax
0x18001dd9d  jz      short loc_18001DDC3
0x18001dd9f  mov     [rax+8], r15d
0x18001dda3  mov     [rax+38h], r15
0x18001dda7  mov     [rax+40h], r15
0x18001ddab  mov     [rax+48h], r15
0x18001ddaf  mov     [rax+50h], r15
0x18001ddb3  lea     rcx, ??_7CFirewallManager@@6B@; const CFirewallManager::`vftable'
0x18001ddba  mov     [rax], rcx
0x18001ddbd  mov     [rax+58h], r15
0x18001ddc1  jmp     short loc_18001DDC6
0x18001ddc3  mov     rax, r15
0x18001ddc6  mov     cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA, rax; CFirewallManager * WscServiceUtils::g_pFirewallManager
0x18001ddcd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ddd4  mov     ecx, 68h ; 'h'; unsigned __int64
0x18001ddd9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ddde  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001dde2  test    rax, rax
0x18001dde5  jz      short loc_18001DE07
0x18001dde7  mov     [rax+8], r15d
0x18001ddeb  mov     [rax+38h], r15
0x18001ddef  mov     [rax+40h], r15
0x18001ddf3  mov     [rax+48h], r15
0x18001ddf7  mov     [rax+50h], r15
0x18001ddfb  lea     rcx, ??_7CAntiVirusManager@@6B@; const CAntiVirusManager::`vftable'
0x18001de02  mov     [rax], rcx
0x18001de05  jmp     short loc_18001DE0A
0x18001de07  mov     rax, r15
0x18001de0a  mov     cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA, rax; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x18001de11  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001de18  mov     ecx, 8; unsigned __int64
0x18001de1d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001de22  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001de26  test    rax, rax
0x18001de29  jz      short loc_18001DE30
0x18001de2b  mov     [rax], r15
0x18001de2e  jmp     short loc_18001DE33
0x18001de30  mov     rax, r15
0x18001de33  mov     cs:?g_pSecureSettingsManager@@3PEAVCSecureSettingsManager@@EA, rax; CSecureSettingsManager * g_pSecureSettingsManager
0x18001de3a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001de41  mov     ecx, 68h ; 'h'; unsigned __int64
0x18001de46  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001de4b  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001de4f  test    rax, rax
0x18001de52  jz      short loc_18001DE74
0x18001de54  mov     [rax+8], r15d
0x18001de58  mov     [rax+38h], r15
0x18001de5c  mov     [rax+40h], r15
0x18001de60  mov     [rax+48h], r15
0x18001de64  mov     [rax+50h], r15
0x18001de68  lea     rcx, ??_7CAntiSpywareManager@@6B@; const CAntiSpywareManager::`vftable'
0x18001de6f  mov     [rax], rcx
0x18001de72  jmp     short loc_18001DE77
0x18001de74  mov     rax, r15
0x18001de77  mov     cs:?g_pAntiSpywareManager@WscServiceUtils@@3PEAVCAntiSpywareManager@@EA, rax; CAntiSpywareManager * WscServiceUtils::g_pAntiSpywareManager
0x18001de7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001de85  mov     ecx, 468h; unsigned __int64
0x18001de8a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001de8f  mov     rbx, rax
0x18001de92  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001de96  test    rax, rax
0x18001de99  jz      short loc_18001DF06
0x18001de9b  mov     [rax], r15
0x18001de9e  mov     [rax+8], r15
0x18001dea2  mov     [rax+10h], r15
0x18001dea6  mov     [rax+18h], r15
0x18001deaa  mov     [rax+20h], r15
0x18001deae  mov     [rax+28h], r15
0x18001deb2  mov     dword ptr [rax+430h], 3
0x18001debc  mov     [rax+438h], r15
0x18001dec3  mov     [rax+440h], r15
0x18001deca  mov     [rax+448h], r15
0x18001ded1  mov     [rax+450h], r15
0x18001ded8  mov     [rax+458h], r15
0x18001dedf  lea     rcx, [rax+30h]; void *
0x18001dee3  xor     edx, edx; Val
0x18001dee5  mov     r8d, 200h; Size
0x18001deeb  call    memset_0
0x18001def0  lea     rcx, [rbx+230h]; void *
0x18001def7  xor     edx, edx; Val
0x18001def9  mov     r8d, 200h; Size
0x18001deff  call    memset_0
0x18001df04  jmp     short loc_18001DF09
0x18001df06  mov     rbx, r15
0x18001df09  mov     cs:?g_pThirdPartyMonitoring@@3PEAVCThirdPartyMonitoring@@EA, rbx; CThirdPartyMonitoring * g_pThirdPartyMonitoring
  ... truncated ...
```
