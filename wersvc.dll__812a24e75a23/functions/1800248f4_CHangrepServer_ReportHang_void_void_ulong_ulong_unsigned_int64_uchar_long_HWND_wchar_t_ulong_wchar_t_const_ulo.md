# CHangrepServer::ReportHang(void *,void *,ulong *,ulong,unsigned __int64 *,uchar *,long *,HWND__ *,wchar_t *,ulong,wchar_t const *,ulong,HWND__ * *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x1800248f4`
- end: `0x1800254d5`
- name: `?ReportHang@CHangrepServer@@QEAAJPEAX0PEAKKPEA_KPEAEPEAJPEAUHWND__@@PEA_WKPEB_WKPEAPEAU2@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@99@Z`
- size: `3041`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, HANDLE Process, void *, unsigned int *, unsigned int, unsigned __int64 *, unsigned __int8 *, int *, HWND, void *, unsigned int, wchar_t *, unsigned int, _QWORD *, void **, void **, void **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b0b4`

## callees

- `0x1800029d0`
- `0x180003cf8`
- `0x180003d6c`
- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x180013df4`
- `0x180024784`
- `0x1800248f4`
- `0x180025568`
- `0x180025aa0`
- `0x180025b0c`
- `0x180025ce8`
- `0x1800261f8`
- `0x180027008`
- `0x180027260`
- `0x180027460`
- `0x18002f3f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024dd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800252a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024dd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800252a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025361`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180024a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180024a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180024cc7`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180024cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025396`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024afb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024d32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025419`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024afb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024d32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025419`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024d4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800250e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800251ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024d4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800250e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800251ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002510a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002511e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002517c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002532e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002546b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800254a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800254c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002510a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002511e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002517c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002532e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002546b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800254a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800254c1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180024dfe`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800252cf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002538c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180024dfe`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800252cf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002538c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180025485`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180025485`

## pseudocode

```c
__int64 __fastcall CHangrepServer::ReportHang(
        struct _RTL_CRITICAL_SECTION *this,
        HANDLE Process,
        void *a3,
        unsigned int *a4,
        unsigned int a5,
        unsigned __int64 *a6,
        unsigned __int8 *a7,
        int *a8,
        HWND a9,
        void *a10,
        unsigned int a11,
        wchar_t *a12,
        unsigned int a13,
        _QWORD *a14,
        void **a15,
        void **a16,
        void **a17)
{
  LPCRITICAL_SECTION v19; // r13
  char v20; // r15
  __int64 v21; // rdx
  __int64 v22; // r8
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  unsigned int v26; // r12d
  unsigned int v27; // ebx
  DWORD ProcessId; // eax
  int v29; // edx
  __int64 i; // rcx
  DWORD v31; // r8d
  int v32; // eax
  __int64 v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r9
  int v37; // eax
  HANDLE *v38; // rcx
  int v39; // eax
  HANDLE *v40; // rcx
  struct _RTL_CRITICAL_SECTION *HangrepInstanceForPid; // rsi
  char v42; // r12
  __int64 v43; // rbx
  ULONG_PTR SpinCount; // rax
  HANDLE v45; // rdi
  _BOOL8 v46; // rcx
  void **v47; // rbx
  HANDLE v48; // rdi
  HANDLE v49; // rax
  signed int v50; // eax
  _QWORD *v51; // rcx
  __int64 v52; // rdx
  HANDLE v53; // rcx
  unsigned int v54; // edx
  int v55; // ebx
  HANDLE v56; // r13
  DWORD v57; // edi
  HANDLE v58; // rcx
  _QWORD *v59; // rcx
  __int64 v60; // rdx
  int j; // edx
  HANDLE v62; // rcx
  unsigned int v63; // ebx
  __int64 v64; // rdi
  void *v65; // rdi
  int v67; // eax
  HANDLE *v68; // rax
  HANDLE v69; // rbx
  void **v70; // rbx
  HANDLE v71; // rax
  HANDLE *v72; // r9
  signed int v73; // eax
  void **v74; // rbx
  HANDLE v75; // rdi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  void **v78; // rax
  void *v79; // rcx
  HANDLE LockSemaphore; // rdx
  HANDLE v81; // rdx
  void *v82; // rcx
  HANDLE v83; // rax
  void *v84; // rcx
  char v85; // [rsp+70h] [rbp-90h]
  HANDLE hObject; // [rsp+78h] [rbp-88h]
  HANDLE hSourceHandle; // [rsp+80h] [rbp-80h] BYREF
  unsigned int Buffer; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v89; // [rsp+8Ch] [rbp-74h]
  HANDLE v90; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hTargetProcessHandle; // [rsp+98h] [rbp-68h]
  unsigned int ThreadId; // [rsp+A0h] [rbp-60h]
  HANDLE v93; // [rsp+A8h] [rbp-58h]
  HANDLE v94; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v95; // [rsp+B8h] [rbp-48h]
  HANDLE Thread; // [rsp+C0h] [rbp-40h]
  void **v97; // [rsp+C8h] [rbp-38h]
  HANDLE v98; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE v99; // [rsp+D8h] [rbp-28h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+E0h] [rbp-20h]
  wchar_t *v101; // [rsp+E8h] [rbp-18h]
  void **v102; // [rsp+F0h] [rbp-10h]
  void **v103; // [rsp+F8h] [rbp-8h]
  LPCRITICAL_SECTION v104; // [rsp+100h] [rbp+0h]
  char v105; // [rsp+108h] [rbp+8h]
  __int64 v106; // [rsp+110h] [rbp+10h]
  DWORD dwProcessId[4]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v108; // [rsp+128h] [rbp+28h]
  _OWORD v109[2]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v110[16]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v111[16]; // [rsp+1E0h] [rbp+E0h] BYREF

  Thread = a3;
  hTargetProcessHandle = Process;
  v19 = this;
  lpCriticalSection = this;
  v103 = a17;
  v102 = a16;
  v97 = a15;
  v93 = a10;
  v101 = a12;
  v99 = 0;
  v98 = 0;
  v20 = 0;
  `eh vector constructor iterator'(
    v111,
    8u,
    0xFu,
    tlx::unique_any<tlx::file_handle_traits>::unique_any<tlx::file_handle_traits>,
    (void (*)(void *))tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
  `eh vector constructor iterator'(
    v110,
    8u,
    0xFu,
    tlx::unique_any<tlx::file_handle_traits>::unique_any<tlx::file_handle_traits>,
    (void (*)(void *))tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
  Buffer = a5;
  *(_OWORD *)dwProcessId = 0;
  v108 = 0;
  memset(v109, 0, 28);
  v94 = 0;
  v90 = 0;
  hObject = 0;
  v106 = 0;
  v104 = v19;
  v23 = *a15;
  *a15 = 0;
  if ( (unsigned __int64)v23 + 1 > 1 )
    CloseHandle(v23);
  v24 = *a16;
  *a16 = 0;
  if ( (unsigned __int64)v24 + 1 > 1 )
    CloseHandle(v24);
  v25 = *a17;
  *a17 = 0;
  if ( (unsigned __int64)v25 + 1 > 1 )
    CloseHandle(v25);
  v26 = *a4;
  v95 = v26;
  if ( !v26 )
  {
    v27 = -2147024809;
    if ( Process )
      ProcessId = GetProcessId(Process);
    else
      ProcessId = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, ProcessId);
    goto LABEL_114;
  }
  v29 = 0;
  for ( i = 1; i != 16; ++i )
  {
    v31 = a4[i];
    if ( v31 )
      dwProcessId[v29++] = v31;
  }
  if ( !v19 )
    __int2c();
  EnterCriticalSection(v19);
  v85 = 1;
  v105 = 1;
  v32 = CHangrepServer::_LazyInitialize((CHangrepServer *)v19);
  v27 = v32;
  if ( v32 < 0 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_113;
    v35 = 25;
    v36 = (unsigned int)v32;
    goto LABEL_24;
  }
  ThreadId = 0;
  if ( Buffer )
    goto LABEL_32;
  if ( a9 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v33);
  v37 = ExtractThreadIdFromPeb(v26, &Buffer, (unsigned __int8)a11 & 0x80);
  if ( v37 >= 0 )
    goto LABEL_32;
  v38 = (HANDLE *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_33:
      if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 4) != 0 )
        WPP_SF_d(v38[2], 27, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, Buffer);
      goto LABEL_36;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids,
      (unsigned int)v37);
LABEL_32:
    v38 = (HANDLE *)WPP_GLOBAL_Control;
    goto LABEL_33;
  }
LABEL_36:
  if ( Process && Thread )
  {
    v39 = CHangrepServer::_CheckIfOKToReport((__int64)Thread, Process, Thread, v26, Buffer, 1u, &v98, &v99);
    v27 = v39;
    if ( v39 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids);
      goto LABEL_113;
    }
    if ( v39 == 1 )
    {
      v40 = (HANDLE *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids);
        v40 = (HANDLE *)WPP_GLOBAL_Control;
      }
      if ( a9 )
      {
        if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 8) != 0 )
          WPP_SF_(v40[2], 30, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids);
        ThreadId = GetThreadId(Thread);
      }
    }
  }
  v89 = 0;
  if ( a14 )
    *a14 = 0;
  HangrepInstanceForPid = (struct _RTL_CRITICAL_SECTION *)CHangrepServer::_FindHangrepInstanceForPid(
                                                            (CHangrepServer *)v19,
                                                            v26);
  if ( HangrepInstanceForPid )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v26);
    v42 = 1;
    if ( a14 )
    {
      v43 = 0;
      EnterCriticalSection(HangrepInstanceForPid);
      SpinCount = HangrepInstanceForPid[8].SpinCount;
      if ( SpinCount )
        v43 = *(_QWORD *)(SpinCount + 1448);
      LeaveCriticalSection(HangrepInstanceForPid);
      *a14 = v43;
    }
    goto LABEL_61;
  }
  if ( (unsigned int)CHangrepServer::IsCrashReportingInProgress(v26, &v90) )
  {
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v26);
    if ( (unsigned __int64)v90 + 1 <= 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v53);
    v42 = 1;
    goto LABEL_61;
  }
  v89 = 0;
  v54 = a11;
  if ( (a11 & 0x400C0) != 0 )
    v89 = (unsigned __int64)v19[1].LockSemaphore + 1 > 1;
  v55 = 0;
  v56 = hTargetProcessHandle;
  do
  {
    hSourceHandle = 0;
    v57 = dwProcessId[v55];
    if ( v57 )
    {
      if ( (unsigned int)CHangrepServer::IsCrashReportingInProgress(v57, &hSourceHandle) )
      {
        v58 = hSourceHandle;
        if ( (unsigned __int64)hSourceHandle + 1 <= 1 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(hSourceHandle);
          v58 = hSourceHandle;
        }
        hSourceHandle = 0;
        if ( (unsigned __int64)v58 + 1 > 1 )
          CloseHandle(v58);
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_101;
        v60 = 33;
        goto LABEL_100;
      }
      v54 = a11;
      if ( (a11 & 0x100000) != 0 )
      {
        if ( (int)CHangrepServer::_CheckIfOKToReport(
                    (__int64)&v111[v55],
                    v56,
                    Thread,
                    v57,
                    0,
                    0x100C51u,
                    (void **)&v111[v55],
                    (void **)&v110[v55]) >= 0 )
        {
          ++v55;
          goto LABEL_105;
        }
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_101:
          for ( j = v55 + 1; j < 15; ++j )
            dwProcessId[j - 1] = dwProcessId[j];
          DWORD2(v109[1]) = 0;
LABEL_105:
          v62 = hSourceHandle;
          if ( (unsigned __int64)hSourceHandle + 1 > 1 )
LABEL_106:
            CloseHandle(v62);
          v54 = a11;
          continue;
        }
        v60 = 34;
LABEL_100:
        WPP_SF_d(v59[2], v60, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v57);
        goto LABEL_101;
      }
      ++v55;
      v62 = hSourceHandle;
      if ( hSourceHandle != (HANDLE)-1LL && (char *)hSourceHandle + 1 != HANDLE_FLAG_INHERIT )
        goto LABEL_106;
    }
    else
    {
      ++v55;
    }
  }
  while ( v55 < 15 );
  v63 = 0;
  v19 = lpCriticalSection;
  if ( !LODWORD(lpCriticalSection[1].DebugInfo) )
    goto LABEL_112;
  while ( 1 )
  {
    v64 = 2456LL * v63;
    if ( (unsigned int)CHungApp::Acquire(
                         (LPCRITICAL_SECTION)(v64 + *(_QWORD *)&v19[1].LockCount),
                         v95,
                         Buffer,
                         dwProcessId,
                         a6,
                         a7,
                         a8,
                         a9,
                         (wchar_t *)v93,
                         v54,
                         hTargetProcessHandle,
                         ThreadId,
                         v101,
                         a13) )
      break;
    ++v63;
    v54 = a11;
    if ( v63 >= LODWORD(v19[1].DebugInfo) )
      goto LABEL_112;
  }
  v42 = 0;
  HangrepInstanceForPid = (struct _RTL_CRITICAL_SECTION *)(v64 + *(_QWORD *)&v19[1].LockCount);
  if ( !HangrepInstanceForPid )
  {
LABEL_112:
    v27 = -2147020576;
    goto LABEL_113;
  }
  LeaveCriticalSection(v19);
  v85 = 0;
  v105 = 0;
  v67 = CHungApp::Report((CHungApp *)HangrepInstanceForPid, v89);
  v27 = v67;
  if ( v67 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids,
        (unsigned int)v67);
      v20 = 0;
      v65 = 0;
      goto LABEL_115;
    }
LABEL_113:
    v20 = v85;
LABEL_114:
    v65 = hObject;
    goto LABEL_115;
  }
LABEL_61:
  if ( (a11 & 0x20) == 0 )
    goto LABEL_156;
  v45 = hTargetProcessHandle;
  if ( !hTargetProcessHandle )
    goto LABEL_156;
  v46 = (unsigned __int64)v90 + 1 > 1;
  if ( v46 == (HangrepInstanceForPid != 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v46);
  if ( !HangrepInstanceForPid )
  {
    if ( (unsigned __int64)v90 + 1 > 1 )
    {
      v74 = tlx::replace<tlx::file_handle_traits>(v97);
      v75 = v90;
      v90 = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(CurrentProcess, v75, hTargetProcessHandle, v74, 0x100000u, 0, 1u) )
      {
        LastError = GetLastError();
        v27 = LastError;
        if ( LastError > 0 )
          v27 = (unsigned __int16)LastError | 0x80070000;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_113;
        v35 = 38;
        v36 = v27;
LABEL_24:
        WPP_SF_d(v34[2], v35, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v36);
        goto LABEL_113;
      }
    }
LABEL_156:
    v69 = 0;
    goto LABEL_157;
  }
  CHungApp::HangrepCollectionCompleteEvent(HangrepInstanceForPid, &hSourceHandle);
  if ( (unsigned __int64)hSourceHandle + 1 > 1 )
  {
    v47 = tlx::replace<tlx::file_handle_traits>(v97);
    v48 = hSourceHandle;
    hSourceHandle = 0;
    v49 = GetCurrentProcess();
    if ( !DuplicateHandle(v49, v48, hTargetProcessHandle, v47, 0x100000u, 0, 1u) )
    {
      v50 = GetLastError();
      v27 = v50;
      if ( v50 > 0 )
        v27 = (unsigned __int16)v50 | 0x80070000;
      v51 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v52 = 36;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    v45 = hTargetProcessHandle;
  }
  v68 = (HANDLE *)CHungApp::HangrepInstanceHandle(HangrepInstanceForPid);
  v69 = *v68;
  hObject = *v68;
  *v68 = 0;
  if ( (unsigned __int64)v93 + 1 > 1 )
    CloseHandle(v93);
  if ( (unsigned __int64)v69 + 1 > 1 )
  {
    v70 = tlx::replace<tlx::file_handle_traits>(&v94);
    v71 = GetCurrentProcess();
    v72 = v70;
    v69 = hObject;
    if ( !DuplicateHandle(v71, hObject, v45, v72, 0x100000u, 0, 0) )
    {
      v73 = GetLastError();
      v27 = v73;
      if ( v73 > 0 )
        v27 = (unsigned __int16)v73 | 0x80070000;
      v51 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v52 = 37;
LABEL_73:
        WPP_SF_d(v51[2], v52, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v27);
      }
LABEL_74:
      if ( (unsigned __int64)hSourceHandle + 1 > 1 )
        CloseHandle(hSourceHandle);
      goto LABEL_113;
    }
  }
  if ( (unsigned __int64)hSourceHandle + 1 > 1 )
    CloseHandle(hSourceHandle);
LABEL_157:
  v20 = v85;
  if ( (a11 & 0xC0) != 0 && !v89 && HangrepInstanceForPid )
  {
    if ( !v85 )
    {
      if ( !v19 )
        __int2c();
      EnterCriticalSection(v19);
      v20 = 1;
    }
    if ( (unsigned __int64)v19[1].LockSemaphore + 1 <= 1 )
    {
      v78 = (void **)CHungApp::HangrepInstanceHandle(HangrepInstanceForPid);
      v79 = *v78;
      *v78 = 0;
      LockSemaphore = v19[1].LockSemaphore;
      v19[1].LockSemaphore = v79;
      if ( (unsigned __int64)LockSemaphore + 1 > 1 )
        CloseHandle(LockSemaphore);
      if ( (unsigned __int64)v93 + 1 > 1 )
        CloseHandle(v93);
      v81 = v19[1].LockSemaphore;
      if ( (unsigned __int64)v81 + 1 > 1 )
        SetThreadpoolWait((PTP_WAIT)v19[1].OwningThread, v81, 0);
    }
  }
  v65 = 0;
  v82 = *v102;
  *v102 = v69;
  if ( (unsigned __int64)v82 + 1 > 1 )
    CloseHandle(v82);
  v83 = v94;
  v94 = 0;
  v84 = *v103;
  *v103 = v83;
  if ( (unsigned __int64)v84 + 1 > 1 )
    CloseHandle(v84);
  v27 = v42 != 0;
LABEL_115:
  if ( v20 )
    LeaveCriticalSection(v19);
  if ( (unsigned __int64)v65 + 1 > 1 )
    CloseHandle(v65);
  if ( (unsigned __int64)v90 + 1 > 1 )
    CloseHandle(v90);
  if ( (unsigned __int64)v94 + 1 > 1 )
    CloseHandle(v94);
  `eh vector destructor iterator'(
    (char *)v110,
    8,
    15,
    (void (__fastcall *)(char *))tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
  `eh vector destructor iterator'(
    (char *)v111,
    8,
    15,
    (void (__fastcall *)(char *))tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
  if ( (unsigned __int64)v98 + 1 > 1 )
    CloseHandle(v98);
  if ( (unsigned __int64)v99 + 1 > 1 )
    CloseHandle(v99);
  return v27;
}

```

## disassembly

```asm
0x1800248f4  push    rbp
0x1800248f6  push    rbx
0x1800248f7  push    rsi
0x1800248f8  push    rdi
0x1800248f9  push    r12
0x1800248fb  push    r13
0x1800248fd  push    r14
0x1800248ff  push    r15
0x180024901  lea     rbp, [rsp-178h]
0x180024909  sub     rsp, 278h
0x180024910  mov     rax, cs:__security_cookie
0x180024917  xor     rax, rsp
0x18002491a  mov     [rbp+1B0h+var_50], rax
0x180024921  mov     rbx, r9
0x180024924  mov     [rbp+1B0h+Thread], r8
0x180024928  mov     rsi, rdx
0x18002492b  mov     [rbp+1B0h+hTargetProcessHandle], rdx
0x18002492f  mov     r13, rcx
0x180024932  mov     [rbp+1B0h+lpCriticalSection], rcx
0x180024936  mov     r14, [rbp+1B0h+arg_80]
0x18002493d  mov     [rbp+1B0h+var_1B8], r14
0x180024941  mov     r12, [rbp+1B0h+arg_78]
0x180024948  mov     [rbp+1B0h+var_1C0], r12
0x18002494c  mov     rcx, [rbp+1B0h+arg_70]
0x180024953  mov     [rbp+1B0h+var_1E8], rcx
0x180024957  mov     rax, [rbp+1B0h+arg_48]
0x18002495e  mov     [rbp+1B0h+var_208], rax
0x180024962  mov     rax, [rbp+1B0h+arg_58]
0x180024969  mov     [rbp+1B0h+var_1C8], rax
0x18002496d  mov     rdi, [rbp+1B0h+arg_68]
0x180024974  mov     [rbp+1B0h+var_1D8], 0
0x18002497c  mov     [rbp+1B0h+var_1E0], 0
0x180024984  lea     rax, ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002498b  mov     qword ptr [rsp+2B0h+dwDesiredAccess], rax; void (*)(void *)
0x180024990  lea     r9, ??0?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; void (*)(void *)
0x180024997  mov     r15d, 0Fh
0x18002499d  mov     r8d, r15d; unsigned __int64
0x1800249a0  lea     edx, [r15-7]; unsigned __int64
0x1800249a4  lea     rcx, [rbp+1B0h+var_D0]; void *
0x1800249ab  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800249b0  nop
0x1800249b1  lea     rax, ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800249b8  mov     qword ptr [rsp+2B0h+dwDesiredAccess], rax; void (*)(void *)
0x1800249bd  lea     r9, ??0?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; void (*)(void *)
0x1800249c4  mov     r8d, r15d; unsigned __int64
0x1800249c7  lea     edx, [r15-7]; unsigned __int64
0x1800249cb  lea     rcx, [rbp+1B0h+var_150]; void *
0x1800249cf  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800249d4  nop
0x1800249d5  mov     eax, [rbp+1B0h+arg_20]
0x1800249db  mov     [rbp+1B0h+Buffer], eax
0x1800249de  xorps   xmm0, xmm0
0x1800249e1  xor     eax, eax
0x1800249e3  movups  xmmword ptr [rbp+1B0h+dwProcessId], xmm0
0x1800249e7  movups  [rbp+1B0h+var_188], xmm0
0x1800249eb  movups  [rbp+1B0h+var_178], xmm0
0x1800249ef  movups  [rbp+1B0h+var_178+0Ch], xmm0
0x1800249f3  mov     [rbp+1B0h+var_200], rax
0x1800249f7  mov     [rbp+1B0h+var_220], rax
0x1800249fb  mov     [rsp+2B0h+hObject], rax
0x180024a00  mov     [rbp+1B0h+var_1A0], rax
0x180024a04  mov     [rbp+1B0h+var_1B0], r13
0x180024a08  xor     r15b, r15b
0x180024a0b  mov     rax, [rbp+1B0h+var_1E8]
0x180024a0f  mov     rcx, [rax]; hObject
0x180024a12  mov     qword ptr [rax], 0
0x180024a19  lea     rax, [rcx+1]
0x180024a1d  mov     r9d, 1
0x180024a23  cmp     rax, r9
0x180024a26  jbe     short loc_180024A34
0x180024a28  call    cs:__imp_CloseHandle
0x180024a2e  mov     r9d, 1
0x180024a34  mov     rcx, [r12]; hObject
0x180024a38  mov     qword ptr [r12], 0
0x180024a40  lea     rax, [rcx+1]
0x180024a44  cmp     rax, r9
0x180024a47  jbe     short loc_180024A55
0x180024a49  call    cs:__imp_CloseHandle
0x180024a4f  mov     r9d, 1
0x180024a55  mov     rcx, [r14]; hObject
0x180024a58  mov     qword ptr [r14], 0
0x180024a5f  lea     rax, [rcx+1]
0x180024a63  cmp     rax, r9
0x180024a66  jbe     short loc_180024A74
0x180024a68  call    cs:__imp_CloseHandle
0x180024a6e  mov     r9d, 1
0x180024a74  mov     r12d, [rbx]
0x180024a77  mov     [rbp+1B0h+var_1F8], r12d
0x180024a7b  test    r12d, r12d
0x180024a7e  jnz     short loc_180024ACF
0x180024a80  mov     ebx, 80070057h
0x180024a85  test    rsi, rsi
0x180024a88  jz      short loc_180024A95
0x180024a8a  mov     rcx, rsi; Process
0x180024a8d  call    cs:__imp_GetProcessId
0x180024a93  jmp     short loc_180024A97
0x180024a95  xor     eax, eax
0x180024a97  lea     r14, WPP_GLOBAL_Control
0x180024a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024aa5  cmp     rcx, r14
0x180024aa8  mov     r14d, 1
0x180024aae  jz      loc_1800250D6
0x180024ab4  test    [rcx+1Ch], r14b
0x180024ab8  jz      loc_1800250D6
0x180024abe  mov     r9d, eax
0x180024ac1  mov     rcx, [rcx+10h]
0x180024ac5  call    WPP_SF_dd
0x180024aca  jmp     loc_1800250D6
0x180024acf  xor     edx, edx
0x180024ad1  mov     rcx, r9
0x180024ad4  mov     r8d, [rbx+rcx*4]
0x180024ad8  test    r8d, r8d
0x180024adb  jz      short loc_180024AE8
0x180024add  movsxd  rax, edx
0x180024ae0  mov     [rbp+rax*4+1B0h+dwProcessId], r8d
0x180024ae5  add     edx, r9d
0x180024ae8  add     rcx, r9
0x180024aeb  cmp     rcx, 10h
0x180024aef  jnz     short loc_180024AD4
0x180024af1  test    r13, r13
0x180024af4  jnz     short loc_180024AF8
0x180024af6  int     2Ch; Windows NT - assertion failure
0x180024af8  mov     rcx, r13; lpCriticalSection
0x180024afb  call    cs:__imp_EnterCriticalSection
0x180024b01  mov     al, 1
0x180024b03  mov     [rsp+2B0h+var_240], al
0x180024b07  mov     [rbp+1B0h+var_1A8], al
0x180024b0a  mov     rcx, r13; this
0x180024b0d  call    ?_LazyInitialize@CHangrepServer@@AEAAJXZ; CHangrepServer::_LazyInitialize(void)
0x180024b12  mov     ebx, eax
0x180024b14  test    eax, eax
0x180024b16  jns     short loc_180024B5B
0x180024b18  lea     r14, WPP_GLOBAL_Control
0x180024b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b26  cmp     rcx, r14
0x180024b29  mov     r14d, 1
0x180024b2f  jz      loc_1800250D1
0x180024b35  test    [rcx+1Ch], r14b
0x180024b39  jz      loc_1800250D1
0x180024b3f  lea     edx, [r14+18h]
0x180024b43  mov     r9d, eax
0x180024b46  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180024b4d  mov     rcx, [rcx+10h]
0x180024b51  call    WPP_SF_d
0x180024b56  jmp     loc_1800250D1
0x180024b5b  mov     [rbp+1B0h+var_210], 0
0x180024b62  lea     r15, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180024b69  lea     r14, WPP_GLOBAL_Control
0x180024b70  cmp     [rbp+1B0h+Buffer], 0
0x180024b74  jnz     short loc_180024BC9
0x180024b76  cmp     [rbp+1B0h+arg_40], 0
0x180024b7e  jz      short loc_180024B85
0x180024b80  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024b85  mov     r8d, [rbp+1B0h+arg_50]
0x180024b8c  and     r8d, 80h; int
0x180024b93  lea     rdx, [rbp+1B0h+Buffer]; lpBuffer
0x180024b97  mov     ecx, r12d; dwProcessId
0x180024b9a  call    ?ExtractThreadIdFromPeb@@YAJKPEAKH@Z; ExtractThreadIdFromPeb(ulong,ulong *,int)
0x180024b9f  test    eax, eax
0x180024ba1  jns     short loc_180024BC9
0x180024ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180024baa  cmp     rcx, r14
0x180024bad  jz      short loc_180024BF0
0x180024baf  test    byte ptr [rcx+1Ch], 2
0x180024bb3  jz      short loc_180024BD0
0x180024bb5  mov     edx, 1Ah
0x180024bba  mov     r9d, eax
0x180024bbd  mov     r8, r15
0x180024bc0  mov     rcx, [rcx+10h]
0x180024bc4  call    WPP_SF_d
0x180024bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bd0  cmp     rcx, r14
0x180024bd3  jz      short loc_180024BF0
0x180024bd5  test    byte ptr [rcx+1Ch], 4
0x180024bd9  jz      short loc_180024BF0
0x180024bdb  mov     edx, 1Bh
0x180024be0  mov     r9d, [rbp+1B0h+Buffer]
0x180024be4  mov     r8, r15
0x180024be7  mov     rcx, [rcx+10h]
0x180024beb  call    WPP_SF_d
0x180024bf0  test    rsi, rsi
0x180024bf3  jz      loc_180024CD0
0x180024bf9  mov     rcx, [rbp+1B0h+Thread]
0x180024bfd  test    rcx, rcx
0x180024c00  jz      loc_180024CD0
0x180024c06  lea     rax, [rbp+1B0h+var_1D8]
0x180024c0a  mov     [rsp+2B0h+var_278], rax
0x180024c0f  lea     rax, [rbp+1B0h+var_1E0]
0x180024c13  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x180024c18  mov     [rsp+2B0h+bInheritHandle], 1
0x180024c20  mov     eax, [rbp+1B0h+Buffer]
0x180024c23  mov     [rsp+2B0h+dwDesiredAccess], eax
0x180024c27  mov     r9d, r12d
0x180024c2a  mov     r8, rcx
0x180024c2d  mov     rdx, rsi
0x180024c30  call    ?_CheckIfOKToReport@CHangrepServer@@AEAAJPEAX0KKKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@1@Z; CHangrepServer::_CheckIfOKToReport(void *,void *,ulong,ulong,ulong,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)
0x180024c35  mov     ebx, eax
0x180024c37  test    eax, eax
0x180024c39  jns     short loc_180024C70
0x180024c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c42  cmp     rcx, r14
0x180024c45  mov     r14d, 1
0x180024c4b  jz      loc_1800250D1
0x180024c51  test    [rcx+1Ch], r14b
0x180024c55  jz      loc_1800250D1
0x180024c5b  lea     edx, [r14+1Bh]
0x180024c5f  mov     r8, r15
0x180024c62  mov     rcx, [rcx+10h]
0x180024c66  call    WPP_SF_
0x180024c6b  jmp     loc_1800250D1
0x180024c70  cmp     eax, 1
0x180024c73  jnz     short loc_180024CD0
0x180024c75  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c7c  cmp     rcx, r14
0x180024c7f  jz      short loc_180024C9D
0x180024c81  test    byte ptr [rcx+1Ch], 4
0x180024c85  jz      short loc_180024C9D
0x180024c87  lea     edx, [rax+1Ch]
0x180024c8a  mov     r8, r15
0x180024c8d  mov     rcx, [rcx+10h]
0x180024c91  call    WPP_SF_
0x180024c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c9d  cmp     [rbp+1B0h+arg_40], 0
0x180024ca5  jz      short loc_180024CD0
0x180024ca7  cmp     rcx, r14
0x180024caa  jz      short loc_180024CC3
0x180024cac  test    byte ptr [rcx+1Ch], 8
0x180024cb0  jz      short loc_180024CC3
0x180024cb2  mov     edx, 1Eh
0x180024cb7  mov     r8, r15
0x180024cba  mov     rcx, [rcx+10h]
0x180024cbe  call    WPP_SF_
0x180024cc3  mov     rcx, [rbp+1B0h+Thread]; Thread
0x180024cc7  call    cs:__imp_GetThreadId
0x180024ccd  mov     [rbp+1B0h+var_210], eax
0x180024cd0  mov     [rbp+1B0h+var_224], 0
0x180024cd7  test    rdi, rdi
0x180024cda  jz      short loc_180024CE3
0x180024cdc  mov     qword ptr [rdi], 0
0x180024ce3  mov     edx, r12d; unsigned int
0x180024ce6  mov     rcx, r13; this
0x180024ce9  call    ?_FindHangrepInstanceForPid@CHangrepServer@@AEAAPEAVCHungApp@@K@Z; CHangrepServer::_FindHangrepInstanceForPid(ulong)
0x180024cee  mov     rsi, rax
0x180024cf1  test    rax, rax
0x180024cf4  jz      loc_180024E68
0x180024cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d01  cmp     rcx, r14
0x180024d04  jz      short loc_180024D20
0x180024d06  test    byte ptr [rcx+1Ch], 4
0x180024d0a  jz      short loc_180024D20
0x180024d0c  mov     edx, 1Fh
0x180024d11  mov     r9d, r12d
0x180024d14  mov     r8, r15
0x180024d17  mov     rcx, [rcx+10h]
0x180024d1b  call    WPP_SF_d
0x180024d20  mov     ebx, 1
0x180024d25  mov     r12b, bl
0x180024d28  test    rdi, rdi
0x180024d2b  jz      short loc_180024D5C
0x180024d2d  xor     ebx, ebx
0x180024d2f  mov     rcx, rsi; lpCriticalSection
0x180024d32  call    cs:__imp_EnterCriticalSection
0x180024d38  mov     rax, [rsi+160h]
0x180024d3f  test    rax, rax
0x180024d42  jz      short loc_180024D4B
0x180024d44  mov     rbx, [rax+5A8h]
0x180024d4b  mov     rcx, rsi; lpCriticalSection
0x180024d4e  call    cs:__imp_LeaveCriticalSection
0x180024d54  mov     [rdi], rbx
0x180024d57  mov     ebx, 1
0x180024d5c  test    byte ptr [rbp+1B0h+arg_50], 20h
0x180024d63  jz      loc_1800253DA
0x180024d69  mov     rdi, [rbp+1B0h+hTargetProcessHandle]
0x180024d6d  test    rdi, rdi
0x180024d70  jz      loc_1800253DA
0x180024d76  mov     rax, [rbp+1B0h+var_220]
0x180024d7a  inc     rax
0x180024d7d  xor     ecx, ecx
0x180024d7f  cmp     rax, rbx
0x180024d82  setnbe  cl
0x180024d85  xor     eax, eax
0x180024d87  test    rsi, rsi
0x180024d8a  setnz   al
0x180024d8d  cmp     ecx, eax
0x180024d8f  jnz     short loc_180024D96
0x180024d91  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024d96  test    rsi, rsi
0x180024d99  jz      loc_180025339
0x180024d9f  lea     rdx, [rbp+1B0h+hSourceHandle]
0x180024da3  mov     rcx, rsi; lpCriticalSection
0x180024da6  call    ?HangrepCollectionCompleteEvent@CHungApp@@QEAA?AV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@XZ; CHungApp::HangrepCollectionCompleteEvent(void)
0x180024dab  mov     rax, [rbp+1B0h+hSourceHandle]
0x180024daf  inc     rax
0x180024db2  cmp     rax, rbx
0x180024db5  jbe     loc_180025257
0x180024dbb  mov     rcx, [rbp+1B0h+var_1E8]
0x180024dbf  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180024dc4  mov     rbx, rax
0x180024dc7  mov     rdi, [rbp+1B0h+hSourceHandle]
0x180024dcb  mov     [rbp+1B0h+hSourceHandle], 0
  ... truncated ...
```
