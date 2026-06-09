# UbpmpHostLaunchTaskExe(_UBPM_TASK_LAUNCH_INPUT_PARAMS *,void * *,_UBPM_TASK_HOST_CONTEXT_BLOCK * *,_UBPM_TASK_HOST_TASK_CONTEXT * *)

- ea: `0x180021060`
- end: `0x18002204b`
- name: `?UbpmpHostLaunchTaskExe@@YAKPEAU_UBPM_TASK_LAUNCH_INPUT_PARAMS@@PEAPEAXPEAPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_UBPM_TASK_HOST_TASK_CONTEXT@@@Z`
- size: `4075`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *, void **, struct _UBPM_TASK_HOST_CONTEXT_BLOCK **, struct _UBPM_TASK_HOST_TASK_CONTEXT **)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006650`
- `0x180017e88`

## callees

- `0x180004a30`
- `0x180007460`
- `0x180009750`
- `0x18000ae40`
- `0x18000c248`
- `0x18000d578`
- `0x18000e660`
- `0x18001e9f4`
- `0x180020328`
- `0x1800203d0`
- `0x18002046c`
- `0x1800204cc`
- `0x1800207e8`
- `0x1800208bc`
- `0x180020900`
- `0x180020cc0`
- `0x180020e90`
- `0x180021060`
- `0x180022054`
- `0x180023350`
- `0x180030cec`
- `0x180032e38`
- `0x1800347bc`
- `0x18003bfac`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180021f00`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180021f00`
- `ntdll!NtQueryInformationProcess` at `0x180021221`
- `ntdll!NtQueryInformationProcess` at `0x180021221`
- `ntdll!EtwEventWrite` at `0x18002174a`
- `ntdll!EtwEventWrite` at `0x18002174a`
- `ntdll!EtwEventEnabled` at `0x18002168b`
- `ntdll!EtwEventEnabled` at `0x18002168b`
- `ntdll!RtlFreeHeap` at `0x180021386`
- `ntdll!RtlFreeHeap` at `0x1800213a4`
- `ntdll!RtlFreeHeap` at `0x180021419`
- `ntdll!RtlFreeHeap` at `0x180021386`
- `ntdll!RtlFreeHeap` at `0x1800213a4`
- `ntdll!RtlFreeHeap` at `0x180021419`
- `ntdll!RtlNtStatusToDosError` at `0x18002198d`
- `ntdll!RtlNtStatusToDosError` at `0x18002198d`
- `ntdll!RtlReleaseSRWLockShared` at `0x180021914`
- `ntdll!RtlReleaseSRWLockShared` at `0x180021914`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800218f9`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800218f9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800214a5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002157a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002181b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180021ce2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800214a5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002157a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002181b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180021ce2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021552`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021642`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002186e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021d32`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021f3b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021552`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021642`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002186e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021d32`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180021f3b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180021c7a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180021c7a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021a6b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021e1b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021a6b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021e1b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800217b0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800217b0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180021fb9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180021fb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800214ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021ce8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800214ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021ce8`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x180021655`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x180021655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002142e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002142e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021fc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021fe8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ff3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021fc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021fe8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ff3`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18002161c`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18002161c`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18002184a`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18002184a`
- `profapi!__imp_UnloadProfileBasic` at `0x180022013`
- `profapi!__imp_UnloadProfileBasic` at `0x180022013`

## string_xrefs

- `0x180021784`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18002175d`: `EventWrite error`
- `0x180021ad6`: `taskhostw.exe`

## pseudocode

```c
__int64 __fastcall UbpmpHostLaunchTaskExe(
        struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *a1,
        void **a2,
        struct _UBPM_TASK_HOST_CONTEXT_BLOCK **a3,
        struct _UBPM_TASK_HOST_TASK_CONTEXT **a4)
{
  __int64 v4; // rax
  _DWORD *v6; // r12
  _DWORD *v7; // rcx
  bool v8; // zf
  int v9; // r14d
  int v10; // esi
  bool v11; // r13
  __int16 v12; // r15
  int v13; // r9d
  const unsigned __int16 *v14; // r8
  wchar_t *v15; // r15
  struct _UBPM_ACTION_EXE_LAUNCH_PARAMS *v16; // rdx
  const unsigned __int16 *v17; // rcx
  int v18; // esi
  void *v19; // r9
  unsigned int Host; // edi
  int v21; // eax
  int v22; // edi
  DWORD *v23; // rdx
  _QWORD *v24; // rcx
  void **v25; // rsi
  __int64 v27; // rax
  unsigned int v28; // r13d
  PVOID v29; // r12
  PVOID v30; // r15
  HANDLE v31; // r14
  unsigned int v32; // esi
  HANDLE v33; // rdi
  DWORD CurrentThreadId; // eax
  _QWORD *v35; // rcx
  char *v36; // rdx
  unsigned __int64 v37; // rax
  void **v38; // rsi
  unsigned int *v39; // rsi
  DWORD v40; // eax
  struct _LIST_ENTRY *Flink; // rcx
  unsigned int v42; // eax
  struct _LIST_ENTRY **p_Blink; // rdi
  __int64 v44; // rcx
  int v45; // eax
  DWORD PriorityClass; // eax
  int *v47; // rdi
  EventManager *v48; // rsi
  __int64 v49; // rcx
  __int64 v50; // rax
  unsigned int v51; // eax
  EventManager *v52; // rcx
  signed int v53; // edi
  __int64 v54; // r8
  HINSTANCE v55; // rdx
  void *v56; // rax
  void *v57; // rsi
  int v58; // r12d
  _DWORD *v59; // rdi
  __int64 v60; // rax
  char *v61; // rcx
  void *v62; // rcx
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v63; // rax
  __int64 v64; // r9
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v65; // rcx
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v66; // rax
  int v67; // edx
  __int64 v68; // r9
  int v69; // ecx
  char v70; // al
  _QWORD *v71; // rcx
  __int64 v72; // rdx
  int v73; // edx
  DWORD v74; // eax
  struct _LIST_ENTRY *v75; // rdi
  _QWORD *v76; // rcx
  __int64 v77; // rdx
  char *v78; // rcx
  void *v79; // rcx
  int v80; // [rsp+30h] [rbp-108h]
  int v81; // [rsp+40h] [rbp-F8h]
  size_t Size; // [rsp+50h] [rbp-E8h]
  unsigned int Sizea; // [rsp+50h] [rbp-E8h]
  const unsigned __int16 *Src; // [rsp+58h] [rbp-E0h]
  void *v85; // [rsp+B8h] [rbp-80h] BYREF
  __int64 v86; // [rsp+C0h] [rbp-78h] BYREF
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v87; // [rsp+C8h] [rbp-70h] BYREF
  unsigned int v88; // [rsp+D0h] [rbp-68h] BYREF
  int v89; // [rsp+D8h] [rbp-60h] BYREF
  HANDLE ProcessHandle; // [rsp+E0h] [rbp-58h] BYREF
  struct _LIST_ENTRY **v91; // [rsp+E8h] [rbp-50h] BYREF
  unsigned int v92; // [rsp+F0h] [rbp-48h] BYREF
  struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT *v93; // [rsp+F8h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+100h] [rbp-38h] BYREF
  int ProcessInformation; // [rsp+108h] [rbp-30h] BYREF
  int v96; // [rsp+10Ch] [rbp-2Ch]
  int v97; // [rsp+110h] [rbp-28h]
  void **v98; // [rsp+118h] [rbp-20h]
  HKEY v99; // [rsp+120h] [rbp-18h] BYREF
  PVOID v100; // [rsp+128h] [rbp-10h] BYREF
  PVOID P; // [rsp+130h] [rbp-8h] BYREF
  PVOID v102; // [rsp+138h] [rbp+0h] BYREF
  char *v103; // [rsp+140h] [rbp+8h]
  unsigned __int64 v104; // [rsp+148h] [rbp+10h] BYREF
  HANDLE hThread; // [rsp+150h] [rbp+18h] BYREF
  wchar_t *v106; // [rsp+158h] [rbp+20h]
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK **v107; // [rsp+160h] [rbp+28h]
  struct _UBPM_TASK_HOST_TASK_CONTEXT **v108; // [rsp+168h] [rbp+30h]
  char *v109; // [rsp+170h] [rbp+38h]
  _QWORD *v110; // [rsp+178h] [rbp+40h]
  HANDLE EventW; // [rsp+180h] [rbp+48h]
  PVOID v112; // [rsp+188h] [rbp+50h]
  unsigned __int64 v113; // [rsp+190h] [rbp+58h]
  struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT *v114; // [rsp+198h] [rbp+60h]
  HKEY v115; // [rsp+1A0h] [rbp+68h]
  int *v116; // [rsp+1A8h] [rbp+70h] BYREF
  __int64 v117; // [rsp+1B0h] [rbp+78h]
  int *v118; // [rsp+1B8h] [rbp+80h]
  __int64 v119; // [rsp+1C0h] [rbp+88h]
  struct _LIST_ENTRY ***v120; // [rsp+1C8h] [rbp+90h]
  __int64 v121; // [rsp+1D0h] [rbp+98h]
  int *v122; // [rsp+1D8h] [rbp+A0h]
  __int64 v123; // [rsp+1E0h] [rbp+A8h]

  v4 = *(_QWORD *)a1;
  v98 = a2;
  v6 = (_DWORD *)((char *)a1 + 80);
  v85 = 0;
  ProcessHandle = 0;
  v88 = 0;
  hObject = 0;
  hThread = 0;
  v100 = 0;
  v7 = *(_DWORD **)(v4 + 24);
  v108 = a4;
  v107 = a3;
  v8 = *v7 == 2;
  v103 = (char *)a1 + 80;
  if ( v8 || *v6 )
  {
    v103 = (char *)a1 + 80;
    v9 = 1;
  }
  else
  {
    v9 = 0;
  }
  v10 = v7[12];
  v11 = 0;
  v89 = v9;
  v12 = 0;
  v87 = 0;
  LODWORD(v86) = 0;
  v99 = 0;
  P = 0;
  v92 = 0;
  v102 = 0;
  v93 = 0;
  v104 = 0;
  ProcessInformation = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      LOBYTE(a4) = *v6 == 0;
      Host = UbpmpFindHost(
               *((_QWORD *)a1 + 3),
               *(_QWORD *)(*(_QWORD *)a1 + 24LL),
               *((_DWORD *)a1 + 14),
               (int)a4,
               *((PSID *)a1 + 8),
               (__int64)&v85,
               (__int64)&v86);
      if ( Host )
        break;
      RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
      while ( (*((_BYTE *)v85 + 104) & 0x20) != 0 )
        SleepConditionVariableSRW(&g_cvHostStartedup, &g_TaskHostContextListLock, 0xFFFFFFFF, 1u);
      RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
      if ( (_DWORD)v86 )
      {
        UbpmpDecrementRefAndDelete(&v85, 1);
        v85 = 0;
        Sleep(0x64u);
        if ( (unsigned __int16)++v12 >= 0x2BCu )
        {
          Host = 1235;
          v76 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_13;
          v77 = 34;
          goto LABEL_150;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids);
      }
      else
      {
        v64 = 2;
        if ( *v6 )
          LOWORD(v64) = 4;
        Host = UbpmpSendCommandGetResponse(v85, a1, &v87, v64);
        if ( !Host )
        {
          v65 = v87;
          v66 = (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)v85;
          *v108 = v87;
          *v107 = v66;
          if ( !*v6 )
            v11 = v65 == 0;
          v85 = 0;
          v87 = 0;
          goto LABEL_13;
        }
        if ( Host != 1237 )
        {
          v71 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_13;
          v72 = 36;
LABEL_128:
          WPP_SF_dd(v71[2], v72, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, *((unsigned int *)v85 + 8), Host);
          goto LABEL_13;
        }
        UbpmpDecrementRefAndDelete(&v85, 1);
        v85 = 0;
        Sleep(0x64u);
        if ( (unsigned __int16)++v12 >= 0x2BCu )
        {
          Host = 1235;
          v76 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_13;
          v77 = 37;
          goto LABEL_150;
        }
      }
    }
    if ( Host != 1168 )
    {
      v76 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v77 = 38;
LABEL_150:
      WPP_SF_d(v76[2], v77, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, Host);
      goto LABEL_13;
    }
    v14 = L"{222A245B-E637-4AE9-A93F-A59CA119A75E}";
    v15 = L"taskhostw.exe";
    v13 = *((unsigned __int8 *)v85 + 432);
    if ( !*((_BYTE *)v85 + 432) )
      v14 = 0;
  }
  else
  {
    v13 = 0;
    v14 = (const unsigned __int16 *)*((_QWORD *)a1 + 12);
    v15 = *(wchar_t **)(*(_QWORD *)(v4 + 24) + 8LL);
  }
  v16 = *(struct _UBPM_ACTION_EXE_LAUNCH_PARAMS **)(*(_QWORD *)a1 + 24LL);
  Src = (const unsigned __int16 *)*((_QWORD *)a1 + 18);
  Sizea = *((_DWORD *)a1 + 34);
  v17 = (const unsigned __int16 *)*((_QWORD *)a1 + 3);
  v81 = v10;
  v18 = (int)v98;
  v80 = v13;
  v19 = (void *)*((_QWORD *)a1 + 9);
  v106 = v15;
  LODWORD(v86) = UbpmpLaunchAction(
                   v17,
                   v16,
                   v98,
                   v19,
                   v15,
                   v80,
                   0,
                   v81,
                   v14,
                   Sizea,
                   Src,
                   &ProcessHandle,
                   &v88,
                   &hObject,
                   &hThread,
                   &v100,
                   &v99,
                   &P,
                   &v92,
                   (void ***)&v102,
                   &v104,
                   &v93);
  Host = v86;
  if ( (_DWORD)v86 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v67 = 39;
    goto LABEL_164;
  }
  v21 = NtQueryInformationProcess(ProcessHandle, ProcessSessionInformation, &ProcessInformation, 4u, 0);
  if ( v21 < 0 )
  {
    Host = RtlNtStatusToDosError(v21);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v67 = 40;
    goto LABEL_164;
  }
  v22 = ProcessInformation;
  LODWORD(v91) = ProcessInformation;
  if ( v9 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      Host = GetLastError();
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v67 = 41;
      goto LABEL_164;
    }
    v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 32LL);
    if ( v27 )
    {
      v69 = *(_DWORD *)(v27 + 32);
      LODWORD(v27) = *(_DWORD *)(v27 + 36);
      v97 = v69;
    }
    else
    {
      v97 = 0;
    }
    v28 = v92;
    v29 = P;
    v30 = v100;
    v31 = hObject;
    v32 = v88;
    v33 = ProcessHandle;
    v96 = v27;
    v114 = v93;
    v113 = v104;
    v112 = v102;
    v115 = v99;
    v110 = v85;
    v109 = (char *)v85 + 64;
    RtlAcquireSRWLockExclusive((char *)v85 + 64);
    CurrentThreadId = GetCurrentThreadId();
    v35 = v110;
    v36 = v109;
    *((_DWORD *)v109 + 2) = CurrentThreadId;
    v35[6] = EventW;
    *((_DWORD *)v35 + 66) = v96;
    *((_DWORD *)v35 + 67) = v97;
    *((_DWORD *)v35 + 48) = (_DWORD)v91;
    v35[50] = v112;
    v37 = v113;
    *((_DWORD *)v35 + 8) = v32;
    v38 = v98;
    v35[48] = v37;
    v35[53] = v114;
    v35[3] = v33;
    v35[32] = v31;
    v35[22] = v30;
    v35[23] = v29;
    *((_DWORD *)v35 + 98) = v28;
    if ( v38 )
    {
      v35[30] = v115;
      v35[31] = *v38;
      *v38 = 0;
    }
    *((_DWORD *)v36 + 2) = 0;
    RtlReleaseSRWLockExclusive(v36);
    v9 = v89;
    v11 = 0;
    v15 = v106;
    v6 = v103;
  }
  else
  {
    v23 = *(DWORD **)(*(_QWORD *)a1 + 32LL);
    if ( v23 )
      UbpmpSetProcessPriorities(ProcessHandle, v23[4], v23[6], v23[7]);
    LODWORD(v86) = UbpmpCreateTaskHostContextBlock(
                     0,
                     v18,
                     (_DWORD)a1,
                     (_DWORD)ProcessHandle,
                     v88,
                     v22,
                     (__int64)hObject,
                     (__int64)v100,
                     (__int64)P,
                     (__int64)v99,
                     v92,
                     (__int64)v102,
                     v104,
                     (__int64)v93,
                     (__int64)&v85);
    Host = v86;
    if ( (_DWORD)v86 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v67 = 42;
      goto LABEL_164;
    }
  }
  v39 = (unsigned int *)v85;
  v91 = 0;
  RtlAcquireSRWLockExclusive(&g_TaskHostJobObjectLock);
  v40 = GetCurrentThreadId();
  Flink = g_leJobObjectContextsHead.Flink;
  dword_18004CF88 = v40;
  while ( Flink != &g_leJobObjectContextsHead )
  {
    v42 = v39[48];
    p_Blink = &Flink[-1].Blink;
    v91 = &Flink[-1].Blink;
    if ( LODWORD(Flink[1].Blink) == v42 )
    {
      if ( v9 )
      {
        if ( v9 == 1 )
        {
          v70 = *((_BYTE *)v39 + 432);
          if ( v70 == 1 && *((_DWORD *)p_Blink + 9) == 1 )
            goto LABEL_57;
          if ( !v70 && *((_DWORD *)p_Blink + 9) == 2 )
            goto LABEL_57;
        }
      }
      else if ( !*((_DWORD *)p_Blink + 9) )
      {
        goto LABEL_57;
      }
    }
    Flink = Flink->Flink;
  }
  if ( v9 )
    v44 = 2 - (unsigned int)(*((_BYTE *)v39 + 432) != 0);
  else
    v44 = 0;
  v45 = CreateJobObjectContext(v44, v39[48], &v91);
  p_Blink = v91;
  if ( v45 )
    goto LABEL_52;
LABEL_57:
  if ( AssignProcessToJobObject(p_Blink[3], *((HANDLE *)v39 + 3)) )
  {
    *((_QWORD *)v39 + 52) = p_Blink;
    ++*(_DWORD *)p_Blink;
    goto LABEL_59;
  }
  GetLastError();
LABEL_52:
  if ( p_Blink && !*(_DWORD *)p_Blink && !*((_DWORD *)p_Blink + 1) )
    DestroyJobObjectContext(p_Blink);
LABEL_59:
  dword_18004CF88 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostJobObjectLock);
  if ( ProcessHandle )
  {
    PriorityClass = GetPriorityClass(ProcessHandle);
    v47 = (int *)*((_QWORD *)a1 + 2);
    if ( !v47 )
      v47 = (int *)*((_QWORD *)a1 + 3);
    v48 = g_hTaskEventManager;
    v89 = PriorityClass;
    LODWORD(v91) = v88;
    if ( *(_QWORD *)g_hTaskEventManager )
    {
      if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_hTaskEventManager, CREATED_TASK_PROCESS) )
        goto LABEL_120;
      v49 = -1;
      if ( v47 )
      {
        v116 = v47;
        v50 = -1;
        do
          v8 = *((_WORD *)v47 + ++v50) == 0;
        while ( !v8 );
        v117 = (unsigned int)(2 * v50 + 2);
      }
      else
      {
        v116 = &dword_1800405F4;
        v117 = 2;
      }
      if ( v15 )
      {
        v118 = (int *)v15;
        do
          v8 = v15[++v49] == 0;
        while ( !v8 );
        v119 = (unsigned int)(2 * v49 + 2);
      }
      else
      {
        v118 = &dword_1800405F4;
        v119 = 2;
      }
      v120 = &v91;
      v121 = 4;
      v123 = 4;
      v122 = &v89;
      v51 = EtwEventWrite(*(_QWORD *)v48, CREATED_TASK_PROCESS, 4, &v116);
      v53 = v51;
      if ( v51 )
      {
        EventManager::LogIt(v52, L"EventWrite error", v51);
        if ( v53 > 0 )
          v53 = (unsigned __int16)v53 | 0x80070000;
      }
      else
      {
LABEL_120:
        v53 = 0;
      }
    }
    else
    {
      v53 = 1;
    }
    v54 = (unsigned __int16)v53;
    if ( v53 >= 0 )
      v54 = 0;
    TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", CREATED_TASK_PROCESS, v54);
  }
  ProcessHandle = 0;
  v100 = 0;
  P = 0;
  v99 = 0;
  v102 = 0;
  hObject = 0;
  v93 = 0;
  ResumeThread(hThread);
  if ( v9 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)v85 + 12);
    Host = UbpmUtilsSubmitThreadPoolWork(
             (void (*)(void *, unsigned __int8, void *))UbpmpConsumeHostCommandActionCallback,
             v85,
             1,
             0,
             0);
    if ( !Host )
    {
      v68 = 2;
      if ( *v6 )
        LOWORD(v68) = 4;
      LODWORD(v86) = UbpmpSendCommandGetResponse(v85, a1, &v87, v68);
      Host = v86;
      if ( (_DWORD)v86 )
      {
        v71 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v72 = 44;
        goto LABEL_128;
      }
      if ( !*v6 )
        v11 = v87 == 0;
      goto LABEL_79;
    }
    UbpmpDecrementRefAndDelete(&v85, 1);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v67 = 43;
LABEL_164:
    WPP_SF_Sd(v24[2], v67, (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, (_DWORD)v15, Host);
    goto LABEL_13;
  }
LABEL_79:
  if ( **(_DWORD **)(*(_QWORD *)a1 + 24LL) != 2 )
    goto LABEL_82;
  v56 = v85;
  v57 = (void *)*((_QWORD *)v85 + 23);
  if ( !v57 )
    goto LABEL_83;
  v58 = *((_DWORD *)v85 + 8);
  if ( UbpmUtilsSidSupportsHardening(*((PSID *)v85 + 23)) )
  {
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    v74 = GetCurrentThreadId();
    v75 = g_leTaskHostHardeningListHead.Flink;
    for ( dword_18004CF18 = v74; v75 != &g_leTaskHostHardeningListHead; v75 = v75->Flink )
    {
      if ( !v75[3].Flink && EqualSid(v57, v75[1].Blink) && !LODWORD(v75[3].Blink) )
        LODWORD(v75[3].Blink) = v58;
    }
    dword_18004CF18 = 0;
    RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
    v56 = v85;
  }
  else
  {
LABEL_82:
    v56 = v85;
  }
LABEL_83:
  if ( !v9 && (*((_DWORD *)a1 + 34) & 0x200000) != 0 )
  {
    UbpmUtilsSystemPowerOn(*((const unsigned __int16 **)a1 + 2), v55, (void **)v56 + 51);
    v56 = v85;
  }
  _InterlockedIncrement64((volatile signed __int64 *)v56 + 12);
  v59 = v85;
  RtlAcquireSRWLockExclusive((char *)v85 + 64);
  v59[18] = GetCurrentThreadId();
  v60 = RegisterWaitForSingleObjectEx(*((_QWORD *)v85 + 3), UbpmpTaskHostDead, v85, 0xFFFFFFFFLL, 8);
  *((_QWORD *)v85 + 5) = v60;
  if ( *((_QWORD *)v85 + 5) )
  {
    v61 = (char *)v85 + 64;
    *((_DWORD *)v85 + 18) = 0;
    RtlReleaseSRWLockExclusive(v61);
    v62 = v85;
    v63 = v87;
    *v107 = (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)v85;
    *v108 = v63;
    UbpmpHostStartStateActions(v62, 1);
    Host = v86;
    v85 = 0;
    v87 = 0;
    goto LABEL_13;
  }
  Host = GetLastError();
  v78 = (char *)v85 + 64;
  *((_DWORD *)v85 + 18) = 0;
  RtlReleaseSRWLockExclusive(v78);
  if ( **(_DWORD **)(*(_QWORD *)a1 + 24LL) == 2 )
    UbpmpInitPidInHardeningList(*((PSID *)v85 + 23));
  v79 = (void *)*((_QWORD *)v85 + 51);
  if ( v79 )
  {
    UbpmUtilsSystemPowerOff(v79);
    *((_QWORD *)v85 + 51) = 0;
  }
  v87 = 0;
  UbpmpDecrementRefAndDelete(&v85, 1);
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v67 = 45;
    goto LABEL_164;
  }
LABEL_13:
  if ( ProcessHandle )
  {
    TerminateProcess(ProcessHandle, Host);
    CloseHandle(ProcessHandle);
  }
  v25 = v98;
  if ( v93 )
    UbpmpDecrementAppContainerRefAndDelete(&v93);
  if ( hObject )
    CloseHandle(hObject);
  if ( hThread )
    CloseHandle(hThread);
  if ( v99 && v25 && *v25 )
    UnloadProfileBasic();
  if ( v85 )
  {
    UbpmpHostStartStateActions(v85, Host == 0);
    UbpmpDecrementRefAndDelete(&v85, 1);
  }
  if ( v100 != pSid && v100 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v102 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v102);
  if ( v87 )
    UbpmpDecrementTaskRefAndDelete(&v87);
  if ( v11 || Host )
  {
    v73 = *((unsigned __int16 *)a1 + 22);
    if ( (_WORD)v73 )
    {
      LODWORD(Size) = *((_DWORD *)a1 + 27);
      UbpmRunNextSerializedAction(
        *((_QWORD *)a1 + 1),
        v73,
        *((_QWORD *)a1 + 4),
        *((_DWORD *)a1 + 10),
        *((_QWORD *)a1 + 6),
        *((_DWORD *)a1 + 14),
        *((PSID *)a1 + 8),
        *((_QWORD *)a1 + 11),
        *((_DWORD *)a1 + 26),
        Size,
        *((void **)a1 + 14),
        *((_BYTE *)a1 + 120),
        *((unsigned __int16 ***)a1 + 16),
        *((_DWORD *)a1 + 34),
        *((_BYTE *)a1 + 152),
        *((unsigned __int16 ***)a1 + 20));
    }
  }
  return Host;
}

```

## disassembly

```asm
0x180021060  mov     r11, rsp
0x180021063  push    rbp
0x180021064  push    rbx
0x180021065  lea     rbp, [r11-108h]
0x18002106c  sub     rsp, 228h
0x180021073  mov     rax, cs:__security_cookie
0x18002107a  xor     rax, rsp
0x18002107d  mov     [rbp+100h+var_50], rax
0x180021084  mov     rax, [rcx]
0x180021087  mov     rbx, rcx
0x18002108a  mov     [r11-18h], rsi
0x18002108e  mov     [r11-28h], r12
0x180021092  mov     [r11-30h], r13
0x180021096  mov     [rbp+100h+var_120], rdx
0x18002109a  lea     r12, [rbx+50h]
0x18002109e  xor     edx, edx
0x1800210a0  mov     [r11-38h], r14
0x1800210a4  mov     [rbp+100h+var_180], rdx
0x1800210a8  mov     [rbp+100h+ProcessHandle], rdx
0x1800210ac  mov     [rbp+100h+var_168], edx
0x1800210af  mov     [rbp+100h+hObject], rdx
0x1800210b3  mov     [rbp+100h+hThread], rdx
0x1800210b7  mov     [rbp+100h+var_110], rdx
0x1800210bb  mov     rcx, [rax+18h]
0x1800210bf  mov     [r11-40h], r15
0x1800210c3  mov     [rbp+100h+var_D0], r9
0x1800210c7  mov     [rbp+100h+var_D8], r8
0x1800210cb  cmp     dword ptr [rcx], 2
0x1800210ce  mov     [rbp+100h+var_F8], r12
0x1800210d2  jz      loc_1800213F2
0x1800210d8  cmp     [r12], edx
0x1800210dc  jnz     loc_1800213F2
0x1800210e2  mov     r14d, edx
0x1800210e5  mov     esi, [rcx+30h]
0x1800210e8  xor     r13b, r13b
0x1800210eb  mov     [rbp+100h+var_160], r14d
0x1800210ef  mov     r15d, edx
0x1800210f2  mov     [rsp+230h+var_18], rdi
0x1800210fa  mov     [rbp+100h+var_170], rdx
0x1800210fe  mov     dword ptr [rbp+100h+var_178], edx
0x180021101  mov     [rbp+100h+var_118], rdx
0x180021105  mov     [rbp+100h+P], rdx
0x180021109  mov     [rbp+100h+var_148], edx
0x18002110c  mov     [rbp+100h+var_100], rdx
0x180021110  mov     [rbp+100h+var_140], rdx
0x180021114  mov     [rbp+100h+var_F0], rdx
0x180021118  mov     [rbp+100h+ProcessInformation], edx
0x18002111b  test    r14d, r14d
0x18002111e  jnz     loc_1800218B0
0x180021124  mov     rcx, [rax+18h]
0x180021128  mov     r9d, edx
0x18002112b  mov     r8, [rbx+60h]
0x18002112f  mov     r15, [rcx+8]
0x180021133  mov     ecx, [rbx+88h]
0x180021139  lea     r10, [rbp+100h+var_140]
0x18002113d  mov     rax, [rbx+90h]
0x180021144  mov     rdx, [rbx]
0x180021147  mov     [rsp+0A8h], r10; struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT **
0x18002114f  lea     r10, [rbp+100h+var_F0]
0x180021153  mov     [rsp+230h+var_190], r10; unsigned __int64 *
0x18002115b  lea     r10, [rbp+100h+var_100]
0x18002115f  mov     [rsp+230h+var_198], r10; void ***
0x180021167  lea     r10, [rbp+100h+var_148]
0x18002116b  mov     rdx, [rdx+18h]; struct _UBPM_ACTION_EXE_LAUNCH_PARAMS *
0x18002116f  mov     [rsp+230h+var_1A0], r10; unsigned int *
0x180021177  lea     r10, [rbp+100h+P]
0x18002117b  mov     [rsp+230h+var_1A8], r10; void **
0x180021183  lea     r10, [rbp+100h+var_118]
0x180021187  mov     [rsp+230h+var_1B0], r10; HKEY *
0x18002118f  lea     r10, [rbp+100h+var_110]
0x180021193  mov     [rsp+230h+var_1B8], r10; void **
0x180021198  lea     r10, [rbp+100h+hThread]
0x18002119c  mov     [rsp+230h+var_1C0], r10; void **
0x1800211a1  lea     r10, [rbp+100h+hObject]
0x1800211a5  mov     [rsp+230h+var_1C8], r10; void **
0x1800211aa  lea     r10, [rbp+100h+var_168]
0x1800211ae  mov     [rsp+230h+var_1D0], r10; unsigned int *
0x1800211b3  lea     r10, [rbp+100h+ProcessHandle]
0x1800211b7  mov     [rsp+230h+var_1D8], r10; void **
0x1800211bc  mov     [rsp+230h+Src], rax; unsigned __int16 *
0x1800211c1  mov     dword ptr [rsp+230h+Size], ecx; unsigned int
0x1800211c5  mov     rcx, [rbx+18h]; unsigned __int16 *
0x1800211c9  mov     [rsp+230h+var_1F0], r8; unsigned __int16 *
0x1800211ce  mov     dword ptr [rsp+230h+var_1F8], esi; int
0x1800211d2  mov     rsi, [rbp+100h+var_120]
0x1800211d6  mov     dword ptr [rsp+230h+pSid], 0; int
0x1800211de  mov     r8, rsi; void **
0x1800211e1  mov     dword ptr [rsp+230h+var_208], r9d; int
0x1800211e6  mov     r9, [rbx+48h]; void *
0x1800211ea  mov     [rbp+100h+var_E0], r15
0x1800211ee  mov     [rsp+230h+ReturnLength], r15; Str
0x1800211f3  call    ?UbpmpLaunchAction@@YAKPEBGPEAU_UBPM_ACTION_EXE_LAUNCH_PARAMS@@PEAPEAXPEAX0HHH0K02PEAK222PEAPEAUHKEY__@@24PEAPEAPEAXPEA_KPEAPEAU_UBPM_TASK_HOST_APPCONTAINER_CONTEXT@@@Z; UbpmpLaunchAction(ushort const *,_UBPM_ACTION_EXE_LAUNCH_PARAMS *,void * *,void *,ushort const *,int,int,int,ushort const *,ulong,ushort const *,void * *,ulong *,void * *,void * *,void * *,HKEY__ * *,void * *,ulong *,void * * *,unsigned __int64 *,_UBPM_TASK_HOST_APPCONTAINER_CONTEXT * *)
0x1800211f8  mov     dword ptr [rbp+100h+var_178], eax
0x1800211fb  mov     edi, eax
0x1800211fd  test    eax, eax
0x1800211ff  jnz     loc_180021AF9
0x180021205  mov     rcx, [rbp+100h+ProcessHandle]; ProcessHandle
0x180021209  lea     r8, [rbp+100h+ProcessInformation]; ProcessInformation
0x18002120d  mov     r9d, 4; ProcessInformationLength
0x180021213  mov     [rsp+230h+ReturnLength], 0; ReturnLength
0x18002121c  mov     edx, 18h; ProcessInformationClass
0x180021221  call    cs:__imp_NtQueryInformationProcess
0x180021227  test    eax, eax
0x180021229  js      loc_18002198B
0x18002122f  mov     edi, [rbp+100h+ProcessInformation]
0x180021232  mov     dword ptr [rbp+100h+var_150], edi
0x180021235  test    r14d, r14d
0x180021238  jnz     loc_180021424
0x18002123e  mov     rax, [rbx]
0x180021241  mov     rdx, [rax+20h]
0x180021245  test    rdx, rdx
0x180021248  jz      short loc_18002125E
0x18002124a  mov     r9d, [rdx+1Ch]; unsigned int
0x18002124e  mov     r8d, [rdx+18h]; unsigned int
0x180021252  mov     edx, [rdx+10h]; dwPriorityClass
0x180021255  mov     rcx, [rbp+100h+ProcessHandle]; Process
0x180021259  call    ?UbpmpSetProcessPriorities@@YAXPEAXKKK@Z; UbpmpSetProcessPriorities(void *,ulong,ulong,ulong)
0x18002125e  mov     r9, [rbp+100h+ProcessHandle]
0x180021262  lea     rax, [rbp+100h+var_180]
0x180021266  mov     [rsp+230h+var_1C0], rax
0x18002126b  mov     r8, rbx
0x18002126e  mov     rax, [rbp+100h+var_140]
0x180021272  mov     rdx, rsi
0x180021275  mov     [rsp+230h+var_1C8], rax
0x18002127a  xor     ecx, ecx
0x18002127c  mov     rax, [rbp+100h+var_F0]
0x180021280  mov     [rsp+230h+var_1D0], rax
0x180021285  mov     rax, [rbp+100h+var_100]
0x180021289  mov     [rsp+230h+var_1D8], rax
0x18002128e  mov     eax, [rbp+100h+var_148]
0x180021291  mov     dword ptr [rsp+230h+Src], eax
0x180021295  mov     rax, [rbp+100h+var_118]
0x180021299  mov     [rsp+230h+Size], rax
0x18002129e  mov     rax, [rbp+100h+P]
0x1800212a2  mov     [rsp+230h+var_1F0], rax
0x1800212a7  mov     rax, [rbp+100h+var_110]
0x1800212ab  mov     [rsp+230h+var_1F8], rax
0x1800212b0  mov     rax, [rbp+100h+hObject]
0x1800212b4  mov     [rsp+230h+pSid], rax
0x1800212b9  mov     eax, [rbp+100h+var_168]
0x1800212bc  mov     dword ptr [rsp+230h+var_208], edi
0x1800212c0  mov     dword ptr [rsp+230h+ReturnLength], eax
0x1800212c4  call    UbpmpCreateTaskHostContextBlock
0x1800212c9  mov     dword ptr [rbp+100h+var_178], eax
0x1800212cc  mov     edi, eax
0x1800212ce  test    eax, eax
0x1800212d0  jz      loc_180021567
0x1800212d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212dd  lea     rax, WPP_GLOBAL_Control
0x1800212e4  cmp     rcx, rax
0x1800212e7  jnz     loc_180021EE0
0x1800212ed  mov     rcx, [rbp+100h+ProcessHandle]; hProcess
0x1800212f1  mov     r15, [rsp+230h+var_38]
0x1800212f9  mov     r14, [rsp+230h+var_30]
0x180021301  mov     r12, [rsp+230h+var_20]
0x180021309  test    rcx, rcx
0x18002130c  jnz     loc_180021FB7
0x180021312  cmp     [rbp+100h+var_140], 0
0x180021317  mov     rsi, [rbp+100h+var_120]
0x18002131b  jnz     loc_180021FCE
0x180021321  mov     rcx, [rbp+100h+hObject]; hObject
0x180021325  test    rcx, rcx
0x180021328  jnz     loc_180021FE8
0x18002132e  mov     rcx, [rbp+100h+hThread]; hObject
0x180021332  test    rcx, rcx
0x180021335  jnz     loc_180021FF3
0x18002133b  mov     rdx, [rbp+100h+var_118]
0x18002133f  test    rdx, rdx
0x180021342  jnz     loc_180021FFE
0x180021348  mov     rcx, [rbp+100h+var_180]
0x18002134c  mov     rsi, [rsp+220h]
0x180021354  test    rcx, rcx
0x180021357  jnz     loc_18002201E
0x18002135d  mov     r8, [rbp+100h+var_110]; P
0x180021361  cmp     r8, cs:pSid
0x180021368  jnz     loc_180021401
0x18002136e  mov     r8, [rbp+100h+P]; P
0x180021372  test    r8, r8
0x180021375  jz      short loc_18002138C
0x180021377  mov     rcx, gs:60h
0x180021380  xor     edx, edx; Flags
0x180021382  mov     rcx, [rcx+30h]; HeapHandle
0x180021386  call    cs:__imp_RtlFreeHeap
0x18002138c  mov     r8, [rbp+100h+var_100]; P
0x180021390  test    r8, r8
0x180021393  jz      short loc_1800213AA
0x180021395  mov     rcx, gs:60h
0x18002139e  xor     edx, edx; Flags
0x1800213a0  mov     rcx, [rcx+30h]; HeapHandle
0x1800213a4  call    cs:__imp_RtlFreeHeap
0x1800213aa  cmp     [rbp+100h+var_170], 0
0x1800213af  jnz     loc_18002203D
0x1800213b5  cmp     r13b, 1
0x1800213b9  mov     r13, [rsp+230h+var_28]
0x1800213c1  jz      loc_180021BB6
0x1800213c7  test    edi, edi
0x1800213c9  jnz     loc_180021BB6
0x1800213cf  mov     eax, edi
0x1800213d1  mov     rdi, [rsp+230h+var_18]
0x1800213d9  mov     rcx, [rbp+100h+var_50]
0x1800213e0  xor     rcx, rsp; StackCookie
0x1800213e3  call    __security_check_cookie
0x1800213e8  add     rsp, 228h
0x1800213ef  pop     rbx
0x1800213f0  pop     rbp
0x1800213f1  retn
0x1800213f2  mov     [rbp+100h+var_F8], r12
0x1800213f6  mov     r14d, 1
0x1800213fc  jmp     loc_1800210E5
0x180021401  test    r8, r8
0x180021404  jz      loc_18002136E
0x18002140a  mov     rcx, gs:60h
0x180021413  xor     edx, edx; Flags
0x180021415  mov     rcx, [rcx+30h]; HeapHandle
0x180021419  call    cs:__imp_RtlFreeHeap
0x18002141f  jmp     loc_18002136E
0x180021424  xor     r9d, r9d; lpName
0x180021427  xor     r8d, r8d; bInitialState
0x18002142a  xor     edx, edx; bManualReset
0x18002142c  xor     ecx, ecx; lpEventAttributes
0x18002142e  call    cs:__imp_CreateEventW
0x180021434  mov     [rbp+100h+var_B8], rax
0x180021438  test    rax, rax
0x18002143b  jz      loc_180021D41
0x180021441  mov     rax, [rbx]
0x180021444  mov     rcx, [rax+18h]
0x180021448  mov     rax, [rcx+20h]
0x18002144c  test    rax, rax
0x18002144f  jnz     loc_180021B24
0x180021455  mov     [rbp+100h+var_128], eax
0x180021458  mov     r13d, [rbp+100h+var_148]
0x18002145c  mov     r12, [rbp+100h+P]
0x180021460  mov     r15, [rbp+100h+var_110]
0x180021464  mov     r14, [rbp+100h+hObject]
0x180021468  mov     esi, [rbp+100h+var_168]
0x18002146b  mov     rdi, [rbp+100h+ProcessHandle]
0x18002146f  mov     [rbp+100h+var_12C], eax
0x180021472  mov     rax, [rbp+100h+var_140]
0x180021476  mov     [rbp+100h+var_A0], rax
0x18002147a  mov     rax, [rbp+100h+var_F0]
0x18002147e  mov     [rbp+100h+var_A8], rax
0x180021482  mov     rax, [rbp+100h+var_100]
0x180021486  mov     [rbp+100h+var_B0], rax
0x18002148a  mov     rax, [rbp+100h+var_118]
0x18002148e  mov     [rbp+100h+var_98], rax
0x180021492  mov     rax, [rbp+100h+var_180]
0x180021496  mov     [rbp+100h+var_C0], rax
0x18002149a  add     rax, 40h ; '@'
0x18002149e  mov     rcx, rax
0x1800214a1  mov     [rbp+100h+var_C8], rax
0x1800214a5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800214ab  call    cs:__imp_GetCurrentThreadId
0x1800214b1  mov     rcx, [rbp+100h+var_C0]
0x1800214b5  mov     rdx, [rbp+100h+var_C8]
0x1800214b9  mov     [rdx+8], eax
0x1800214bc  mov     rax, [rbp+100h+var_B8]
0x1800214c0  mov     [rcx+30h], rax
0x1800214c4  mov     eax, [rbp+100h+var_12C]
0x1800214c7  mov     [rcx+108h], eax
0x1800214cd  mov     eax, [rbp+100h+var_128]
0x1800214d0  mov     [rcx+10Ch], eax
0x1800214d6  mov     eax, dword ptr [rbp+100h+var_150]
0x1800214d9  mov     [rcx+0C0h], eax
0x1800214df  mov     rax, [rbp+100h+var_B0]
0x1800214e3  mov     [rcx+190h], rax
0x1800214ea  mov     rax, [rbp+100h+var_A8]
0x1800214ee  mov     [rcx+20h], esi
0x1800214f1  mov     rsi, [rbp+100h+var_120]
0x1800214f5  mov     [rcx+180h], rax
0x1800214fc  mov     rax, [rbp+100h+var_A0]
0x180021500  mov     [rcx+1A8h], rax
0x180021507  mov     [rcx+18h], rdi
0x18002150b  mov     [rcx+100h], r14
0x180021512  mov     [rcx+0B0h], r15
0x180021519  mov     [rcx+0B8h], r12
0x180021520  mov     [rcx+188h], r13d
0x180021527  test    rsi, rsi
0x18002152a  jz      short loc_180021548
0x18002152c  mov     rax, [rbp+100h+var_98]
0x180021530  mov     [rcx+0F0h], rax
0x180021537  mov     rax, [rsi]
0x18002153a  mov     [rcx+0F8h], rax
0x180021541  mov     qword ptr [rsi], 0
0x180021548  mov     rcx, rdx
0x18002154b  mov     dword ptr [rdx+8], 0
0x180021552  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180021558  mov     r14d, [rbp+100h+var_160]
0x18002155c  xor     r13b, r13b
0x18002155f  mov     r15, [rbp+100h+var_E0]
0x180021563  mov     r12, [rbp+100h+var_F8]
0x180021567  mov     rsi, [rbp+100h+var_180]
0x18002156b  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x180021572  mov     [rbp+100h+var_150], 0
0x18002157a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180021580  call    cs:__imp_GetCurrentThreadId
0x180021586  mov     rcx, cs:?g_leJobObjectContextsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leJobObjectContextsHead
0x18002158d  lea     rdx, ?g_leJobObjectContextsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leJobObjectContextsHead
0x180021594  mov     cs:dword_18004CF88, eax
0x18002159a  cmp     rcx, rdx
0x18002159d  jz      short loc_1800215C6
  ... truncated ...
```
