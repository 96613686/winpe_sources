# CSdController::_PerformScheduledBackup(void)

- ea: `0x180012948`
- end: `0x18001342e`
- name: `?_PerformScheduledBackup@CSdController@@AEAAJXZ`
- size: `2790`
- prototype: `__int64 __fastcall(CSdController *__hidden this)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010080`

## callees

- `0x1800113f0`
- `0x1800114b8`
- `0x1800115dc`
- `0x180011760`
- `0x180011b84`
- `0x180011ec4`
- `0x180011fd4`
- `0x1800120dc`
- `0x1800121bc`
- `0x180012408`
- `0x180012948`
- `0x1800138bc`
- `0x180013974`
- `0x180013a3c`
- `0x180013b80`
- `0x180013d3c`
- `0x180014088`
- `0x180014fd0`
- `0x18001586c`
- `0x180015974`
- `0x180015fc4`
- `0x1800171f4`
- `0x180017f18`
- `0x1800181f4`
- `0x18001bc1c`
- `0x18001eb28`
- `0x18002170a`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001300a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001330f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001300a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001330f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012fbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013176`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012fbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013176`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001338c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001338c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012a89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012a89`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180013305`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180013305`
- `ntdll!WinSqmAddToStream` at `0x1800132c3`
- `ntdll!WinSqmAddToStream` at `0x1800132c3`
- `ntdll!NtSetThreadExecutionState` at `0x180012a46`
- `ntdll!NtSetThreadExecutionState` at `0x18001331e`
- `ntdll!NtSetThreadExecutionState` at `0x180012a46`
- `ntdll!NtSetThreadExecutionState` at `0x18001331e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012bf4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012da5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012bf4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012da5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001334b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001334b`

## string_xrefs

- `0x180012978`: `CSdController::_PerformScheduledBackup`

## pseudocode

```c
__int64 __fastcall CSdController::_PerformScheduledBackup(CSdController *this)
{
  unsigned int v2; // r15^4
  unsigned int v3; // esi
  int v4; // eax
  bool v5; // sf
  __int16 v6; // ax
  CSdController *v7; // rcx
  int IsPathUNC; // ecx
  int ConfiguredNetworkCredentials; // eax
  CSdController *v10; // rcx
  int v11; // edi
  int IsCredentialsError; // eax
  CSdController *v13; // rcx
  CSdController *v14; // rcx
  LPVOID v15; // rcx
  CSdController *v16; // rcx
  int HasSRHappened; // edi
  int HasASRHappened; // eax
  CSdController *v19; // rcx
  CSdController *v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rax
  int v22; // eax
  struct _SID *v23; // r9
  CSdController *v24; // rcx
  struct ISdAsync2 *v25; // rdi
  struct ISdAsync2 **v26; // rsi
  int v27; // edi
  CSdController *v28; // rcx
  int v29; // eax
  CSdController *v30; // rcx
  __int64 v31; // r8
  int v32; // edx
  signed int v33; // ecx
  const unsigned __int16 **v34; // rdi
  __int64 v35; // rcx
  unsigned int v36; // ebx
  int updated; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v39; // [rsp+54h] [rbp-ACh]
  __int16 v40; // [rsp+56h] [rbp-AAh]
  struct ISdAsync2 *v41; // [rsp+88h] [rbp-78h] BYREF
  int v42; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v44; // [rsp+A0h] [rbp-60h] BYREF
  EXECUTION_STATE PreviousFlags; // [rsp+A4h] [rbp-5Ch] BYREF
  struct ISdBackup2 *v46; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v47; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v49; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v50; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+D8h] [rbp-28h]
  __int128 v52; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h]
  _DWORD v54[16]; // [rsp+100h] [rbp+0h] BYREF
  struct _GUID v55; // [rsp+140h] [rbp+40h] BYREF
  _DWORD v56[10]; // [rsp+150h] [rbp+50h] BYREF
  const unsigned __int16 *v57; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int16 *v58; // [rsp+180h] [rbp+80h]
  __int64 v59; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 *v60; // [rsp+258h] [rbp+158h]
  int v61; // [rsp+2D0h] [rbp+1D0h]
  int v62; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v63; // [rsp+2E8h] [rbp+1E8h]
  int v64; // [rsp+2F0h] [rbp+1F0h]
  __int64 v65; // [rsp+2F8h] [rbp+1F8h]
  int v66; // [rsp+300h] [rbp+200h]
  __int64 v67; // [rsp+308h] [rbp+208h]
  int v68; // [rsp+310h] [rbp+210h]
  __int64 v69; // [rsp+318h] [rbp+218h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&updated,
    "CSdController::_PerformScheduledBackup",
    0x827u,
    0);
  v2 = 0;
  memset_0(v56, 0, 0xF8u);
  memset_0(&v59, 0, 0x90u);
  ppv = 0;
  v46 = 0;
  v49 = 0;
  v53 = 0;
  v41 = 0;
  v50 = 0;
  v47 = 0;
  *(_OWORD *)pv = 0;
  v42 = 0;
  v52 = 0;
  v44 = 0;
  v62 = 1;
  v63 = 0;
  v64 = 1;
  v65 = 0;
  v66 = 1;
  v67 = 0;
  v68 = 1;
  v69 = 0;
  hKey = 0;
  PreviousFlags = 0;
  NtSetThreadExecutionState(0x80000001, &PreviousFlags);
  v3 = 7;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x20006u,
         &hKey);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  updated = v4;
  v5 = v4 < 0;
  v6 = 2127;
  if ( v5 )
    goto LABEL_79;
  v39 = 2127;
  updated = SxRegWriteDWORD(hKey, L"DisableMonitoring", 0);
  v6 = 2128;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2128;
  updated = CSdController::_UpdatePersistentStatus(this, 5, 0);
  v6 = 2136;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2136;
  updated = CSdController::_GetConfig(v7, (struct _SD_BACKUP_CONFIG *)v56);
  v6 = 2141;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2141;
  TraceBackupConfigFields((struct _SD_BACKUP_CONFIG *)v56);
  updated = CSdController::_UpdatePersistentStatus(this, 5, 0);
  v6 = 2156;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2156;
  updated = CSdController::_LogBackupStatus(this, &updated, 2, 0, 0, v57);
  v6 = 2157;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2157;
  updated = CoCreateInstance(&CLSID_SdEngine2, 0, 1u, &IID_ISdCommon2, &ppv);
  v6 = 2162;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2162;
  updated = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, struct ISdBackup2 **))(*(_QWORD *)ppv + 24LL))(
              ppv,
              1,
              &IID_ISdBackup2,
              &v46);
  v6 = 2163;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2163;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_54dd5ff1959335a765c661c9f9542d64_Traceguids,
      (_DWORD)v58,
      (__int64)v57);
  IsPathUNC = SdIsPathUNC(v58);
  updated = IsPathUNC;
  v6 = 2170;
  if ( IsPathUNC < 0 )
    goto LABEL_79;
  v39 = 2170;
  if ( !IsPathUNC )
  {
    v3 = 10;
    ConfiguredNetworkCredentials = CSdController::_GetConfiguredNetworkCredentials(this, v58);
    v11 = ConfiguredNetworkCredentials;
    if ( ConfiguredNetworkCredentials == -2147024843 )
    {
      CSdController::_ClearNetShareTargetSpaceInfo(v10);
      v6 = 2183;
      updated = -2130706426;
      goto LABEL_79;
    }
    if ( ConfiguredNetworkCredentials < 0 )
    {
      IsCredentialsError = CSdController::_FailureIsCredentialsError(v10, v58, ConfiguredNetworkCredentials);
      v13 = (CSdController *)(unsigned int)IsCredentialsError;
      updated = IsCredentialsError;
      v5 = IsCredentialsError < 0;
      v6 = 2189;
      if ( !v5 )
      {
        v39 = 2189;
        if ( (_DWORD)v13 )
        {
          updated = v11;
          v6 = 2197;
        }
        else
        {
          CSdController::_ClearNetShareTargetSpaceInfo(v13);
          v6 = 2194;
          updated = -2130706186;
        }
      }
      goto LABEL_79;
    }
    updated = ConfiguredNetworkCredentials;
    v39 = 2197;
  }
  v3 = 10;
  updated = CSdController::_EnsureBackupTarget(
              (HANDLE *)this,
              (struct ISdCommon2 *)ppv,
              &v57,
              (struct _SD_STORAGE_DEVICE_PROP *)&v59);
  v6 = 2204;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2204;
  if ( v61 )
  {
    v15 = v47;
    if ( !v47 )
    {
      updated = CoCreateInstance(&CLSID_CSdWhcNotifier, 0, 1u, &IID_ISdWhcNotifier, &v47);
      v6 = 2222;
      if ( updated < 0 )
        goto LABEL_79;
      v15 = v47;
      v39 = 2222;
    }
    updated = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v15 + 24LL))(v15, 6);
    v6 = 2224;
    if ( updated < 0 )
      goto LABEL_79;
    v39 = 2224;
  }
  v3 = 7;
  HasSRHappened = CSdController::_HasSRHappened(v14, (struct _SD_BACKUP_CONFIG *)v56);
  updated = HasSRHappened;
  v6 = 2236;
  if ( HasSRHappened < 0 )
    goto LABEL_79;
  v39 = 2236;
  HasASRHappened = CSdController::_HasASRHappened(v16, (const struct _SD_BACKUP_CONFIG *)v56);
  v19 = (CSdController *)(unsigned int)HasASRHappened;
  updated = HasASRHappened;
  v5 = HasASRHappened < 0;
  v6 = 2247;
  if ( v5 )
    goto LABEL_79;
  v39 = 2247;
  if ( !(_DWORD)v19 || !HasSRHappened )
  {
    updated = CSdController::_SetFullBackupFlag(v19);
    v6 = 2256;
    if ( updated < 0 )
      goto LABEL_79;
    v56[0] |= 1u;
    v39 = 2256;
    updated = CSdController::_SetStaleConfigFlag(v20);
    v6 = 2262;
    if ( updated < 0 )
      goto LABEL_79;
    v56[0] |= 0x20u;
    v39 = 2262;
  }
  updated = CSdController::_UpdateTarget(v19, (struct _SD_STORAGE_DEVICE_PROP *)&v59);
  v6 = 2274;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2274;
  updated = CSdController::_ConfigureEngine(this, v46, v60, (struct _SD_BACKUP_CONFIG *)v56, &v42);
  v6 = 2276;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2276;
  v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(CSdController *))(*(_QWORD *)this + 112LL))(this);
  updated = (**v21)(v21, &IID_ISdCallback2, &v49);
  v6 = 2281;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2281;
  updated = (*(__int64 (__fastcall **)(struct ISdBackup2 *, __int64, struct ISdAsync2 **))(*(_QWORD *)v46 + 40LL))(
              v46,
              v49,
              &v41);
  v6 = 2286;
  if ( updated < 0
    || (v39 = 2286,
        v22 = SdIsPathUNC(v60),
        v24 = (CSdController *)(unsigned int)v22,
        updated = v22,
        v5 = v22 < 0,
        v6 = 2291,
        v5) )
  {
LABEL_79:
    v40 = v6;
    goto LABEL_80;
  }
  v39 = 2291;
  if ( !(_DWORD)v24 )
  {
    updated = CSdController::_SetNetworkCredentials(v24, v41, *((void **)this + 19), v23);
    v6 = 2298;
    if ( updated < 0 )
    {
      v3 = 10;
      goto LABEL_79;
    }
    v39 = 2298;
  }
  updated = (*(__int64 (__fastcall **)(struct ISdAsync2 *))(*(_QWORD *)v41 + 24LL))(v41);
  v6 = 2309;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2309;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v25 = v41;
  v26 = (struct ISdAsync2 **)((char *)this + 136);
  *((_DWORD *)this + 27) = 2;
  if ( *((struct ISdAsync2 **)this + 17) != v25 && this != (CSdController *)-136LL )
  {
    if ( v25 )
      (*(void (__fastcall **)(struct ISdAsync2 *))(*(_QWORD *)v25 + 8LL))(v25);
    if ( *v26 )
      (*(void (__fastcall **)(struct ISdAsync2 *))(*(_QWORD *)*v26 + 16LL))(*v26);
    *v26 = v25;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v3 = 6;
  if ( *((_DWORD *)this + 32) )
  {
    updated = (*(__int64 (__fastcall **)(struct ISdAsync2 *))(*(_QWORD *)v41 + 32LL))(v41);
    v6 = 2339;
    if ( updated < 0 )
      goto LABEL_79;
    v39 = 2339;
  }
  v27 = 1;
  do
  {
    if ( v27 )
    {
      CleanupBackupProgressFields((struct SD_BACKUP_PROGRESS *)&v52);
      updated = (*(__int64 (__fastcall **)(struct ISdAsync2 *, __int128 *))(*(_QWORD *)v41 + 64LL))(v41, &v52);
      if ( updated < 0 )
      {
        v40 = 2360;
        goto LABEL_80;
      }
      v39 = 2360;
      if ( (_DWORD)v53 )
      {
        updated = CSdController::_ClearFullBackupFlag(v28);
        if ( updated < 0 )
        {
          v40 = 2363;
          goto LABEL_80;
        }
        v39 = 2363;
        v27 = 0;
      }
    }
    v29 = (*(__int64 (__fastcall **)(struct ISdAsync2 *, __int64))(*(_QWORD *)v41 + 40LL))(v41, 5000);
    updated = v29;
    if ( v29 < 0 )
    {
      v6 = 2368;
      goto LABEL_79;
    }
    v39 = 2368;
  }
  while ( v29 );
  updated = (*(__int64 (__fastcall **)(struct ISdAsync2 *, __int128 *))(*(_QWORD *)v41 + 72LL))(v41, &v50);
  v6 = 2372;
  if ( updated < 0 )
    goto LABEL_79;
  v39 = 2372;
  if ( v27 && LODWORD(pv[1]) )
    CSdController::_ClearFullBackupFlag(v30);
  v3 = v50;
  v2 = HIDWORD(pv[0]);
  updated = DWORD1(v50);
  v6 = 2400;
  if ( SDWORD1(v50) < 0 )
    goto LABEL_79;
  v39 = 2400;
  updated = (*(__int64 (__fastcall **)(struct ISdBackup2 *, unsigned int *))(*(_QWORD *)v46 + 56LL))(v46, &v44);
  if ( updated < 0 )
  {
    v6 = 2402;
    goto LABEL_79;
  }
  updated = 0;
  v39 = 2404;
LABEL_80:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v31 = (unsigned int)updated;
  if ( updated < 0 )
  {
    v54[0] = 1311;
    v32 = 0;
    v54[1] = 65;
    v54[2] = 1326;
    v54[3] = 121;
    v54[4] = 53;
    v54[5] = 1231;
    v54[6] = 59;
    v54[7] = 51;
    v54[8] = 64;
    v54[9] = 1251;
    v54[10] = 58;
    while ( 1 )
    {
      v33 = v54[v32];
      if ( v33 > 0 )
        v33 = (unsigned __int16)v33 | 0x80070000;
      if ( v33 == updated )
        break;
      if ( (unsigned int)++v32 >= 0xB )
        goto LABEL_88;
    }
    v42 = updated;
    v3 = 6;
    v31 = 2164260921LL;
    updated = -2130706375;
  }
LABEL_88:
  if ( v60 )
    v34 = (const unsigned __int16 **)&v59;
  else
    v34 = &v57;
  CSdController::_UpdatePersistentStatus(this, v3, v31);
  CSdController::_LogBackupStatus(this, &updated, v3, v44, __PAIR64__(v2, updated), *v34);
  LODWORD(v65) = 0;
  LODWORD(v67) = v3;
  LODWORD(v63) = v3 == 0;
  LODWORD(v69) = updated;
  WinSqmAddToStream(0, 4248, 4, &v62);
  v35 = *((_QWORD *)this + 17);
  if ( v35 )
  {
    *((_QWORD *)this + 17) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v55 = (struct _GUID)*((_OWORD *)this + 7);
  CSdController::_ReleaseUI(this, &v55);
  *((_DWORD *)this + 27) = 0;
  WakeAllConditionVariable((PCONDITION_VARIABLE)this + 7);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  NtSetThreadExecutionState(0x80000000, &PreviousFlags);
  CleanupBackupConfigFields((struct _SD_BACKUP_CONFIG *)v56);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v54, "CleanupBackupStatusFields", 0x21u, 1u);
  CoTaskMemFree(pv[0]);
  v50 = 0;
  *(_OWORD *)pv = 0;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v54);
  CleanupStorageDeviceProp((struct _SD_STORAGE_DEVICE_PROP *)&v59);
  CleanupBackupProgressFields((struct SD_BACKUP_PROGRESS *)&v52);
  v36 = updated;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v47 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v41 )
    (*(void (__fastcall **)(struct ISdAsync2 *))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  if ( v46 )
    (*(void (__fastcall **)(struct ISdBackup2 *))(*(_QWORD *)v46 + 16LL))(v46);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&updated);
  return v36;
}

```

## disassembly

```asm
0x180012948  push    rbp
0x18001294a  push    rbx
0x18001294b  push    rsi
0x18001294c  push    rdi
0x18001294d  push    r12
0x18001294f  push    r13
0x180012951  push    r14
0x180012953  push    r15
0x180012955  lea     rbp, [rsp-238h]
0x18001295d  sub     rsp, 338h
0x180012964  mov     rax, cs:__security_cookie
0x18001296b  xor     rax, rsp
0x18001296e  mov     [rbp+270h+var_50], rax
0x180012975  mov     rbx, rcx
0x180012978  lea     rdx, aCsdcontrollerP; "CSdController::_PerformScheduledBackup"
0x18001297f  lea     rcx, [rsp+370h+var_320]; this
0x180012984  xor     r9d, r9d; unsigned __int16
0x180012987  mov     r8d, 827h; unsigned __int16
0x18001298d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180012992  xor     r12d, r12d
0x180012995  lea     rcx, [rbp+270h+var_220]; void *
0x180012999  xor     edx, edx; Val
0x18001299b  mov     r8d, 0F8h; Size
0x1800129a1  mov     r15d, r12d
0x1800129a4  call    memset_0
0x1800129a9  xor     edx, edx; Val
0x1800129ab  lea     rcx, [rbp+270h+var_120]; void *
0x1800129b2  mov     r8d, 90h; Size
0x1800129b8  call    memset_0
0x1800129bd  xorps   xmm0, xmm0
0x1800129c0  mov     [rbp+270h+ppv], r12
0x1800129c4  xorps   xmm1, xmm1
0x1800129c7  mov     [rbp+270h+var_2C8], r12
0x1800129cb  xor     eax, eax
0x1800129cd  mov     [rbp+270h+var_2B0], r12
0x1800129d1  lea     rdx, [rbp+270h+PreviousFlags]; PreviousFlags
0x1800129d5  mov     [rbp+270h+var_278], rax
0x1800129d9  mov     ecx, 80000001h; esFlags
0x1800129de  mov     [rbp+270h+var_2E8], r12
0x1800129e2  movups  [rbp+270h+var_2A8], xmm0
0x1800129e6  mov     [rbp+270h+var_2C0], r12
0x1800129ea  movups  xmmword ptr [rbp+270h+pv], xmm0
0x1800129ee  mov     [rbp+270h+var_2E0], r12d
0x1800129f2  movups  [rbp+270h+var_288], xmm1
0x1800129f6  mov     [rbp+270h+var_2D0], r12d
0x1800129fa  mov     [rbp+270h+var_90], 1
0x180012a04  mov     [rbp+270h+var_88], r12
0x180012a0b  mov     [rbp+270h+var_80], 1
0x180012a15  mov     [rbp+270h+var_78], r12
0x180012a1c  mov     [rbp+270h+var_70], 1
0x180012a26  mov     [rbp+270h+var_68], r12
0x180012a2d  mov     [rbp+270h+var_60], 1
0x180012a37  mov     [rbp+270h+var_58], r12
0x180012a3e  mov     [rbp+270h+hKey], r12
0x180012a42  mov     [rbp+270h+PreviousFlags], r12d
0x180012a46  call    cs:__imp_NtSetThreadExecutionState
0x180012a4c  mov     rcx, [rbp+270h+hKey]; hKey
0x180012a50  lea     esi, [r12+7]
0x180012a55  lea     rax, [rcx-1]
0x180012a59  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012a5d  ja      short loc_180012A69
0x180012a5f  call    cs:__imp_RegCloseKey
0x180012a65  mov     [rbp+270h+hKey], r12
0x180012a69  lea     rax, [rbp+270h+hKey]
0x180012a6d  mov     r9d, 20006h; samDesired
0x180012a73  xor     r8d, r8d; ulOptions
0x180012a76  mov     [rsp+370h+phkResult], rax; phkResult
0x180012a7b  lea     rdx, c_wszSafedocsUser_Key; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180012a82  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012a89  call    cs:__imp_RegOpenKeyExW
0x180012a8f  test    eax, eax
0x180012a91  jle     short loc_180012A9B
0x180012a93  movzx   eax, ax
0x180012a96  or      eax, 80070000h
0x180012a9b  mov     [rsp+370h+var_320], eax
0x180012a9f  test    eax, eax
0x180012aa1  mov     eax, 84Fh
0x180012aa6  js      loc_18001316D
0x180012aac  mov     rcx, [rbp+270h+hKey]; hKey
0x180012ab0  lea     rdx, c_wszSafedocsDisableMonitoring; "DisableMonitoring"
0x180012ab7  xor     r8d, r8d; unsigned int
0x180012aba  mov     [rsp+370h+var_31C], ax
0x180012abf  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x180012ac4  mov     [rsp+370h+var_320], eax
0x180012ac8  test    eax, eax
0x180012aca  mov     eax, 850h
0x180012acf  js      loc_18001316D
0x180012ad5  mov     [rsp+370h+var_330], 1
0x180012add  xor     r9d, r9d
0x180012ae0  mov     [rsp+370h+var_338], r12
0x180012ae5  xor     r8d, r8d
0x180012ae8  mov     [rsp+370h+var_340], r12
0x180012aed  mov     rcx, rbx
0x180012af0  mov     [rsp+370h+var_348], r12
0x180012af5  lea     edi, [r9+5]
0x180012af9  mov     [rsp+370h+var_31C], ax
0x180012afe  mov     edx, edi
0x180012b00  mov     [rsp+370h+phkResult], r12
0x180012b05  call    ?_UpdatePersistentStatus@CSdController@@AEAAJW4_SD_BACKUP_RESULT@@JJPEBG111H@Z; CSdController::_UpdatePersistentStatus(_SD_BACKUP_RESULT,long,long,ushort const *,ushort const *,ushort const *,ushort const *,int)
0x180012b0a  mov     [rsp+370h+var_320], eax
0x180012b0e  test    eax, eax
0x180012b10  mov     eax, 858h
0x180012b15  js      loc_18001316D
0x180012b1b  lea     rdx, [rbp+270h+var_220]; struct _SD_BACKUP_CONFIG *
0x180012b1f  mov     [rsp+370h+var_31C], ax
0x180012b24  call    ?_GetConfig@CSdController@@AEAAJPEAU_SD_BACKUP_CONFIG@@@Z; CSdController::_GetConfig(_SD_BACKUP_CONFIG *)
0x180012b29  mov     [rsp+370h+var_320], eax
0x180012b2d  test    eax, eax
0x180012b2f  mov     eax, 85Dh
0x180012b34  js      loc_18001316D
0x180012b3a  lea     rcx, [rbp+270h+var_220]; struct _SD_BACKUP_CONFIG *
0x180012b3e  mov     [rsp+370h+var_31C], ax
0x180012b43  call    ?TraceBackupConfigFields@@YAJPEAU_SD_BACKUP_CONFIG@@@Z; TraceBackupConfigFields(_SD_BACKUP_CONFIG *)
0x180012b48  mov     rax, [rbp+270h+var_1E8]
0x180012b4f  xor     r9d, r9d
0x180012b52  mov     [rsp+370h+var_330], 1
0x180012b5a  xor     r8d, r8d
0x180012b5d  mov     [rsp+370h+var_338], rax
0x180012b62  mov     edx, edi
0x180012b64  mov     rax, [rbp+270h+var_1F8]
0x180012b68  mov     rcx, rbx
0x180012b6b  mov     [rsp+370h+var_340], rax
0x180012b70  mov     rax, [rbp+270h+var_1F0]
0x180012b77  mov     [rsp+370h+var_348], rax
0x180012b7c  mov     [rsp+370h+phkResult], r12
0x180012b81  call    ?_UpdatePersistentStatus@CSdController@@AEAAJW4_SD_BACKUP_RESULT@@JJPEBG111H@Z; CSdController::_UpdatePersistentStatus(_SD_BACKUP_RESULT,long,long,ushort const *,ushort const *,ushort const *,ushort const *,int)
0x180012b86  mov     [rsp+370h+var_320], eax
0x180012b8a  test    eax, eax
0x180012b8c  mov     eax, 86Ch
0x180012b91  js      loc_18001316D
0x180012b97  mov     [rsp+370h+var_31C], ax
0x180012b9c  lea     r13d, [rdi-3]
0x180012ba0  mov     rax, [rbp+270h+var_1F8]
0x180012ba4  lea     rdx, [rsp+370h+var_320]
0x180012ba9  mov     [rsp+370h+var_348], rax
0x180012bae  xor     r9d, r9d
0x180012bb1  mov     r8d, r13d
0x180012bb4  mov     dword ptr [rsp+370h+phkResult], r12d
0x180012bb9  mov     rcx, rbx
0x180012bbc  call    ?_LogBackupStatus@CSdController@@AEAAJPEAVCSxFunctionTracer@@W4_SD_BACKUP_RESULT@@HJPEBG@Z; CSdController::_LogBackupStatus(CSxFunctionTracer *,_SD_BACKUP_RESULT,int,long,ushort const *)
0x180012bc1  mov     [rsp+370h+var_320], eax
0x180012bc5  test    eax, eax
0x180012bc7  mov     eax, 86Dh
0x180012bcc  js      loc_18001316D
0x180012bd2  mov     [rsp+370h+var_31C], ax
0x180012bd7  lea     r9, IID_ISdCommon2; riid
0x180012bde  lea     rax, [rbp+270h+ppv]
0x180012be2  xor     edx, edx; pUnkOuter
0x180012be4  lea     r8d, [rdi-4]; dwClsContext
0x180012be8  mov     [rsp+370h+phkResult], rax; ppv
0x180012bed  lea     rcx, CLSID_SdEngine2; rclsid
0x180012bf4  call    cs:__imp_CoCreateInstance
0x180012bfa  mov     [rsp+370h+var_320], eax
0x180012bfe  test    eax, eax
0x180012c00  mov     eax, 872h
0x180012c05  js      loc_18001316D
0x180012c0b  mov     rcx, [rbp+270h+ppv]
0x180012c0f  lea     r9, [rbp+270h+var_2C8]
0x180012c13  mov     [rsp+370h+var_31C], ax
0x180012c18  lea     r8, IID_ISdBackup2
0x180012c1f  lea     edx, [rdi-4]
0x180012c22  mov     rax, [rcx]
0x180012c25  mov     rax, [rax+18h]
0x180012c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c2e  mov     [rsp+370h+var_320], eax
0x180012c32  test    eax, eax
0x180012c34  mov     eax, 873h
0x180012c39  js      loc_18001316D
0x180012c3f  mov     [rsp+370h+var_31C], ax
0x180012c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c4b  lea     rax, WPP_GLOBAL_Control
0x180012c52  cmp     rcx, rax
0x180012c55  jz      short loc_180012C80
0x180012c57  test    byte ptr [rcx+1Ch], 40h
0x180012c5b  jz      short loc_180012C80
0x180012c5d  mov     rax, [rbp+270h+var_1F8]
0x180012c61  lea     edx, [rdi+8]
0x180012c64  mov     r9, [rbp+270h+var_1F0]
0x180012c6b  lea     r8, WPP_54dd5ff1959335a765c661c9f9542d64_Traceguids
0x180012c72  mov     rcx, [rcx+10h]
0x180012c76  mov     [rsp+370h+phkResult], rax
0x180012c7b  call    WPP_SF_SS
0x180012c80  mov     rcx, [rbp+270h+var_1F0]; unsigned __int16 *
0x180012c87  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x180012c8c  mov     ecx, eax
0x180012c8e  mov     [rsp+370h+var_320], eax
0x180012c92  test    eax, eax
0x180012c94  mov     eax, 87Ah
0x180012c99  js      loc_18001316D
0x180012c9f  mov     [rsp+370h+var_31C], ax
0x180012ca4  mov     r14d, 0Ah
0x180012caa  test    ecx, ecx
0x180012cac  jnz     loc_180012D46
0x180012cb2  mov     rdx, [rbp+270h+var_1F0]; unsigned __int16 *
0x180012cb9  mov     rcx, rbx; this
0x180012cbc  mov     esi, r14d
0x180012cbf  call    ?_GetConfiguredNetworkCredentials@CSdController@@AEAAJPEBG@Z; CSdController::_GetConfiguredNetworkCredentials(ushort const *)
0x180012cc4  mov     edi, eax
0x180012cc6  cmp     eax, 80070035h
0x180012ccb  jnz     short loc_180012CE4
0x180012ccd  call    ?_ClearNetShareTargetSpaceInfo@CSdController@@AEAAJXZ; CSdController::_ClearNetShareTargetSpaceInfo(void)
0x180012cd2  mov     eax, 887h
0x180012cd7  mov     [rsp+370h+var_320], 81000006h
0x180012cdf  jmp     loc_18001316D
0x180012ce4  test    edi, edi
0x180012ce6  jns     short loc_180012D38
0x180012ce8  mov     rdx, [rbp+270h+var_1F0]; unsigned __int16 *
0x180012cef  mov     r8d, edi; int
0x180012cf2  call    ?_FailureIsCredentialsError@CSdController@@AEAAJPEBGJ@Z; CSdController::_FailureIsCredentialsError(ushort const *,long)
0x180012cf7  mov     ecx, eax; this
0x180012cf9  mov     [rsp+370h+var_320], eax
0x180012cfd  test    eax, eax
0x180012cff  mov     eax, 88Dh
0x180012d04  js      loc_18001316D
0x180012d0a  mov     [rsp+370h+var_31C], ax
0x180012d0f  test    ecx, ecx
0x180012d11  jnz     short loc_180012D2A
0x180012d13  call    ?_ClearNetShareTargetSpaceInfo@CSdController@@AEAAJXZ; CSdController::_ClearNetShareTargetSpaceInfo(void)
0x180012d18  mov     eax, 892h
0x180012d1d  mov     [rsp+370h+var_320], 810000F6h
0x180012d25  jmp     loc_18001316D
0x180012d2a  mov     [rsp+370h+var_320], edi
0x180012d2e  mov     eax, 895h
0x180012d33  jmp     loc_18001316D
0x180012d38  mov     eax, 895h
0x180012d3d  mov     [rsp+370h+var_320], edi
0x180012d41  mov     [rsp+370h+var_31C], ax
0x180012d46  mov     rdx, [rbp+270h+ppv]; struct ISdCommon2 *
0x180012d4a  lea     r9, [rbp+270h+var_120]; struct _SD_STORAGE_DEVICE_PROP *
0x180012d51  lea     r8, [rbp+270h+var_1F8]; struct _SD_STORAGE_DEVICE_PROP *
0x180012d55  mov     rcx, rbx; this
0x180012d58  mov     esi, r14d
0x180012d5b  call    ?_EnsureBackupTarget@CSdController@@AEAAJPEAUISdCommon2@@PEAU_SD_STORAGE_DEVICE_PROP@@1@Z; CSdController::_EnsureBackupTarget(ISdCommon2 *,_SD_STORAGE_DEVICE_PROP *,_SD_STORAGE_DEVICE_PROP *)
0x180012d60  mov     [rsp+370h+var_320], eax
0x180012d64  test    eax, eax
0x180012d66  mov     eax, 89Ch
0x180012d6b  js      loc_18001316D
0x180012d71  mov     [rsp+370h+var_31C], ax
0x180012d76  cmp     [rbp+270h+var_A0], r12d
0x180012d7d  jz      short loc_180012DEC
0x180012d7f  mov     rcx, [rbp+270h+var_2C0]
0x180012d83  test    rcx, rcx
0x180012d86  jnz     short loc_180012DC5
0x180012d88  lea     rax, [rbp+270h+var_2C0]
0x180012d8c  xor     edx, edx; pUnkOuter
0x180012d8e  lea     r8d, [rcx+1]; dwClsContext
0x180012d92  mov     [rsp+370h+phkResult], rax; ppv
0x180012d97  lea     rcx, CLSID_CSdWhcNotifier; rclsid
0x180012d9e  lea     r9, IID_ISdWhcNotifier; riid
0x180012da5  call    cs:__imp_CoCreateInstance
0x180012dab  mov     [rsp+370h+var_320], eax
0x180012daf  test    eax, eax
0x180012db1  mov     eax, 8AEh
0x180012db6  js      loc_18001316D
0x180012dbc  mov     rcx, [rbp+270h+var_2C0]
0x180012dc0  mov     [rsp+370h+var_31C], ax
0x180012dc5  mov     rax, [rcx]
0x180012dc8  mov     edx, 6
0x180012dcd  mov     rax, [rax+18h]
0x180012dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dd6  mov     [rsp+370h+var_320], eax
0x180012dda  test    eax, eax
0x180012ddc  mov     eax, 8B0h
0x180012de1  js      loc_18001316D
0x180012de7  mov     [rsp+370h+var_31C], ax
0x180012dec  lea     rdx, [rbp+270h+var_220]; struct _SD_BACKUP_CONFIG *
0x180012df0  mov     esi, 7
0x180012df5  call    ?_HasSRHappened@CSdController@@AEAAJPEAU_SD_BACKUP_CONFIG@@@Z; CSdController::_HasSRHappened(_SD_BACKUP_CONFIG *)
0x180012dfa  mov     edi, eax
0x180012dfc  mov     [rsp+370h+var_320], eax
0x180012e00  test    eax, eax
0x180012e02  mov     eax, 8BCh
0x180012e07  js      loc_18001316D
0x180012e0d  lea     rdx, [rbp+270h+var_220]; struct _SD_BACKUP_CONFIG *
0x180012e11  mov     [rsp+370h+var_31C], ax
0x180012e16  call    ?_HasASRHappened@CSdController@@AEAAJPEBU_SD_BACKUP_CONFIG@@@Z; CSdController::_HasASRHappened(_SD_BACKUP_CONFIG const *)
0x180012e1b  mov     ecx, eax; this
0x180012e1d  mov     [rsp+370h+var_320], eax
0x180012e21  test    eax, eax
0x180012e23  mov     eax, 8C7h
0x180012e28  js      loc_18001316D
0x180012e2e  mov     [rsp+370h+var_31C], ax
0x180012e33  test    ecx, ecx
0x180012e35  jz      short loc_180012E3B
0x180012e37  test    edi, edi
0x180012e39  jnz     short loc_180012E79
0x180012e3b  call    ?_SetFullBackupFlag@CSdController@@AEAAJXZ; CSdController::_SetFullBackupFlag(void)
0x180012e40  mov     [rsp+370h+var_320], eax
0x180012e44  test    eax, eax
0x180012e46  mov     eax, 8D0h
0x180012e4b  js      loc_18001316D
0x180012e51  or      [rbp+270h+var_220], 1
0x180012e55  mov     [rsp+370h+var_31C], ax
0x180012e5a  call    ?_SetStaleConfigFlag@CSdController@@AEAAJXZ; CSdController::_SetStaleConfigFlag(void)
0x180012e5f  mov     [rsp+370h+var_320], eax
0x180012e63  test    eax, eax
0x180012e65  mov     eax, 8D6h
0x180012e6a  js      loc_18001316D
0x180012e70  or      [rbp+270h+var_220], 20h
0x180012e74  mov     [rsp+370h+var_31C], ax
  ... truncated ...
```
