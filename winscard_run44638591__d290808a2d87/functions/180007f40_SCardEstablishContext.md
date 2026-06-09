# SCardEstablishContext

- ea: `0x180007f40`
- end: `0x180008d19`
- name: `SCardEstablishContext`
- size: `3545`
- prototype: `LONG __stdcall(DWORD dwScope, LPCVOID pvReserved1, LPCVOID pvReserved2, LPSCARDCONTEXT phContext)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180002e84`
- `0x180028ed8`

## callees

- `0x180002030`
- `0x180003698`
- `0x18000605c`
- `0x180006400`
- `0x180006890`
- `0x180006c80`
- `0x180007bc0`
- `0x180007f40`
- `0x180008d20`
- `0x180008f20`
- `0x180008f70`
- `0x1800093e4`
- `0x180009480`
- `0x18000ebe0`
- `0x180010898`
- `0x180014d40`
- `0x18001991c`
- `0x18001b9b8`
- `0x18001b9c4`
- `0x18001ba04`
- `0x18001c7a8`
- `0x1800239b8`
- `0x18002ef20`
- `0x18002ef38`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800082ca`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800082ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800081b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008288`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000831a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000834a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000840d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800081b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008288`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000831a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000834a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000840d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008201`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008258`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800082a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800082d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008335`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008376`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800084bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008201`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008258`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800082a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800082d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008335`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008376`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800084bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008225`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008225`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800083c0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800083c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800081d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800081e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180008212`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000836d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800089f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800081d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800081e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180008212`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000836d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800089f8`
- `ntdll!RtlDllShutdownInProgress` at `0x1800081a6`
- `ntdll!RtlDllShutdownInProgress` at `0x1800081c3`
- `ntdll!RtlDllShutdownInProgress` at `0x180008356`
- `ntdll!RtlDllShutdownInProgress` at `0x1800081a6`
- `ntdll!RtlDllShutdownInProgress` at `0x1800081c3`
- `ntdll!RtlDllShutdownInProgress` at `0x180008356`
- `WINSTA!WinStationRegisterCurrentSessionNotificationEvent` at `0x180008240`
- `WINSTA!WinStationRegisterCurrentSessionNotificationEvent` at `0x180008240`
- `WINSTA!WinStationUnRegisterNotificationEvent` at `0x1800081f4`
- `WINSTA!WinStationUnRegisterNotificationEvent` at `0x1800081f4`

## string_xrefs

- `0x1800082ee`: `SCard$AllReaders`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
LONG __stdcall SCardEstablishContext(DWORD dwScope, LPCVOID pvReserved1, LPCVOID pvReserved2, LPSCARDCONTEXT phContext)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v9; // rdx
  DWORD v10; // r9d
  int v11; // r10d
  int v12; // r8d
  unsigned int i; // eax
  bool v14; // zf
  int v15; // r10d
  char *v16; // rcx
  __int64 v17; // rdx
  char *v18; // rax
  __int64 v19; // rax
  const char *v20; // r9
  char *v21; // r8
  char v22; // r10
  char *v23; // rax
  unsigned int v24; // edx
  _DWORD *v25; // rsi
  __int64 v26; // rcx
  unsigned int v27; // ebx
  LPCRITICAL_SECTION v28; // rbx
  int v29; // r12d
  char v30; // r13
  LPCRITICAL_SECTION v31; // r15
  char v32; // r12
  HANDLE v33; // r15
  struct CSCardSubcontext *v34; // rax
  struct CSCardSubcontext *v35; // r15
  char *v36; // r12
  int SpinCount; // r12d
  CHandleList *v38; // r15
  struct _RTL_CRITICAL_SECTION *v39; // rbx
  unsigned int v40; // edx
  unsigned int v41; // eax
  __int64 v42; // r8
  int v43; // eax
  int v44; // r13d
  __int64 v45; // rax
  SCARDCONTEXT v46; // rsi
  int v47; // r12d
  __int64 v48; // r15
  DWORD v49; // eax
  unsigned __int64 v50; // rdx
  __int64 v51; // r9
  int v52; // r10d
  unsigned int k; // ecx
  bool v54; // zf
  int v55; // r11d
  char *v56; // rcx
  char *v57; // rax
  const char *v58; // rax
  char *v59; // r8
  char *v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rcx
  LONG v64; // ebx
  unsigned int v65; // r13d
  char *v66; // rax
  char *v67; // r12
  const void *v68; // rdx
  unsigned __int64 v69; // rdx
  int v70; // r10d
  int v71; // r11d
  int v72; // r9d
  __int64 v73; // rcx
  const void *v74; // r15
  __int64 v75; // rcx
  int v76; // r15d
  __int64 v77; // rcx
  int v78; // r9d
  int v79; // r11d
  LONG v80; // [rsp+30h] [rbp-B8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int j; // [rsp+40h] [rbp-A8h]
  int v83; // [rsp+44h] [rbp-A4h]
  __int64 v84; // [rsp+48h] [rbp-A0h]
  _DWORD *v85; // [rsp+50h] [rbp-98h]
  unsigned __int64 v86; // [rsp+58h] [rbp-90h] BYREF
  const int *v87; // [rsp+60h] [rbp-88h] BYREF
  void *v88; // [rsp+68h] [rbp-80h]
  __int64 v89; // [rsp+70h] [rbp-78h]
  ulong v90; // [rsp+78h] [rbp-70h] BYREF
  ulong v91; // [rsp+7Ch] [rbp-6Ch] BYREF
  ulong v92; // [rsp+80h] [rbp-68h] BYREF
  ulong v93; // [rsp+84h] [rbp-64h] BYREF
  unsigned int v94; // [rsp+88h] [rbp-60h] BYREF
  ulong v95; // [rsp+8Ch] [rbp-5Ch] BYREF
  ulong LastError; // [rsp+90h] [rbp-58h] BYREF
  ulong v97; // [rsp+94h] [rbp-54h] BYREF
  int v98; // [rsp+98h] [rbp-50h] BYREF
  ulong pExceptionObject; // [rsp+9Ch] [rbp-4Ch] BYREF
  ulong v100; // [rsp+A0h] [rbp-48h] BYREF
  ulong v101; // [rsp+A4h] [rbp-44h] BYREF
  ulong v102; // [rsp+A8h] [rbp-40h] BYREF
  ulong v103; // [rsp+ACh] [rbp-3Ch] BYREF
  char *v104; // [rsp+B8h] [rbp-30h]

  lpCriticalSection = 0;
  v87 = &CBuffer::`vftable';
  v88 = 0;
  v89 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v10 = CurrentThreadId;
  v11 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v11 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    dword_180045874 = 0;
    goto LABEL_14;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
  {
    v12 = -1;
    for ( i = 0; ; ++i )
    {
      v14 = i == 32;
      if ( i >= 0x20 )
        break;
      v9 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
      if ( (_DWORD)v9 == v10 )
      {
        v11 = i;
        `WppTraceIndent'::`2'::idxCurrentThread = i;
        v14 = i == 32;
        break;
      }
      if ( v12 == -1 && !(_DWORD)v9 )
        v12 = i;
    }
    if ( v14 )
    {
      if ( v12 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_106;
      }
      v11 = v12;
      `WppTraceIndent'::`2'::idxCurrentThread = v12;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v12) = v10;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v12 + 1) = 0;
    }
  }
  if ( v11 >= 0 )
  {
LABEL_14:
    v15 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v11 + 1);
    goto LABEL_15;
  }
LABEL_106:
  v15 = 0;
LABEL_15:
  v85 = 0;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  v16 = (char *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v15 >= 1 )
  {
    while ( !(unsigned int)StringCbCatA(v16, v9, "..") && v71 + 1 <= v70 )
      ;
    v16 = (char *)WPP_GLOBAL_Control;
  }
  v17 = 256;
  v18 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v18 )
  {
    ++v18;
    if ( !--v17 )
      goto LABEL_25;
  }
  v19 = 2147483646;
  v20 = ">";
  v21 = (char *)&`wil::SetLastError'::`5'::depth - v17;
  do
  {
    if ( !v19 )
      break;
    v22 = *v20;
    if ( !*v20 )
      break;
    ++v20;
    *v21++ = v22;
    --v19;
    --v17;
  }
  while ( v17 );
  v23 = v21 - 1;
  if ( v17 )
    v23 = v21;
  *v23 = 0;
LABEL_25:
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v16 != (char *)&WPP_GLOBAL_Control && (v16[28] & 2) != 0 && (unsigned __int8)v16[25] >= 5u )
    WPP_SF_s(*((_QWORD *)v16 + 2), 52, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
  if ( pvReserved1 )
  {
    v90 = -2146435055;
    throw &v90;
  }
  if ( pvReserved2 )
  {
    v91 = -2146435055;
    throw &v91;
  }
  if ( (dwScope & 0xFFFFFFFD) != 0 )
  {
    v92 = -2146435055;
    throw &v92;
  }
  *phContext = 0;
  v25 = operator new(0x98u);
  v86 = (unsigned __int64)v25;
  if ( v25 )
  {
    *(_QWORD *)v25 = &CHandle::`vftable';
    v25[2] = 0;
    v25[3] = 0x7FFFFFFF;
    v25[4] = 0;
    *(_QWORD *)v25 = &CSCardUserContext::`vftable';
    *((_QWORD *)v25 + 4) = 0;
    v25[10] = 0;
    *((_QWORD *)v25 + 6) = &CDynamicArray<CSCardSubcontext>::`vftable';
    v25[15] = 0;
    v25[14] = 0;
    *((_QWORD *)v25 + 8) = 0;
    CCriticalSectionObject::CCriticalSectionObject((CCriticalSectionObject *)(v25 + 18), v24);
    v25[7] = dwScope;
    *((_QWORD *)v25 + 16) = 0;
    *((_QWORD *)v25 + 18) = 0;
  }
  else
  {
    v25 = 0;
  }
  v85 = v25;
  if ( !v25 )
  {
    v93 = -2146435066;
    throw &v93;
  }
  if ( (*(unsigned int (__fastcall **)(_DWORD *))(*((_QWORD *)v25 + 9) + 16LL))(v25 + 18) )
  {
    (**(void (__fastcall ***)(void *, __int64))v25)(v25, 1);
    v85 = 0;
    WppTraceIndent(v62, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
    }
    v87 = &CBuffer::`vftable';
    v88 = 0;
    v89 = 0;
    return -2146435066;
  }
  v27 = RedirectionContextLookup((struct _REDIRECTION_CONTEXT **)&lpCriticalSection);
  v80 = v27;
  if ( v27 )
  {
    WppTraceIndent(v26, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
        v72,
        v27);
    }
    v94 = v27;
    throw (long *)&v94;
  }
  v28 = lpCriticalSection;
  v29 = 1;
  v83 = 1;
  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(v28[1].DebugInfo) || RtlDllShutdownInProgress() )
  {
LABEL_132:
    v29 = 0;
    v83 = 0;
    goto LABEL_45;
  }
  EnterCriticalSection(v28);
  if ( !LOBYTE(v28[1].DebugInfo) && !RtlDllShutdownInProgress() )
  {
    SetThreadpoolWait((PTP_WAIT)v28[2].OwningThread, 0, 0);
    SetThreadpoolWait((PTP_WAIT)v28[2].SpinCount, 0, 0);
  }
  if ( v28[3].DebugInfo )
  {
    WinStationUnRegisterNotificationEvent();
    v28[3].DebugInfo = 0;
  }
  LeaveCriticalSection(v28);
  SetThreadpoolWait((PTP_WAIT)v28[2].SpinCount, v28[2].LockSemaphore, 0);
  if ( !v28[3].DebugInfo )
  {
    if ( !WaitForSingleObject(*(HANDLE *)&v28[2].LockCount, 0) )
    {
      v29 = WinStationRegisterCurrentSessionNotificationEvent(v28[2].LockSemaphore, 15, &v28[3]);
      v83 = v29;
      if ( v29 )
        goto LABEL_45;
      goto LABEL_132;
    }
    SetThreadpoolWait((PTP_WAIT)v28[2].OwningThread, *(HANDLE *)&v28[2].LockCount, 0);
  }
LABEL_45:
  LeaveCriticalSection(v28);
  v25[6] = v29 != 0;
  UpdateConnectionStateForContext(v28);
  v30 = 0;
  v31 = v28;
  lpCriticalSection = v28;
  if ( !v28 )
  {
    if ( RedirectionContextLookup((struct _REDIRECTION_CONTEXT **)&lpCriticalSection) )
      goto LABEL_182;
    v30 = 1;
    v31 = lpCriticalSection;
  }
  EnterCriticalSection(v31);
  if ( !v31[3].DebugInfo )
    UpdateConnectionStateForContext(v31);
  v32 = BYTE2(v31[1].DebugInfo);
  LeaveCriticalSection(v31);
  if ( v30 )
    RedirectionContextRelease((struct _REDIRECTION_CONTEXT *)v31);
  if ( !v32 )
  {
LABEL_182:
    SetStartedEventWhenSCardSubsytemIsStarted((struct _REDIRECTION_CONTEXT *)v28);
    WppTraceIndent(v77, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
        v78,
        v28[1].SpinCount);
    }
    v103 = -2146435043;
    throw &v103;
  }
  EnterCriticalSection(v28);
  ResetEvent(v28[1].OwningThread);
  LeaveCriticalSection(v28);
  if ( RedirectionContextIsLocal(v28) )
  {
    ListReaders(2u, L"SCard$AllReaders", (struct CBuffer *)&v87);
    if ( (unsigned int)v89 <= 4 && !AllowServiceAccessWithNoReaders() )
    {
      WppTraceIndent(v61, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
      }
      pExceptionObject = -2146435043;
      throw &pExceptionObject;
    }
    if ( dword_180045A10 )
    {
      EnterCriticalSection(&CriticalSection);
      if ( !h )
        h = CreateSCEvent(0x3Du);
      LeaveCriticalSection(&CriticalSection);
      v33 = h;
      if ( h )
      {
        EnterCriticalSection(v28);
        if ( !LOBYTE(v28[1].DebugInfo) && !RtlDllShutdownInProgress() )
          SetThreadpoolWait((PTP_WAIT)v28[3].SpinCount, v33, 0);
        LeaveCriticalSection(v28);
      }
    }
    v34 = CSCardUserContext::AcquireSubcontext((CSCardUserContext *)v25, 0);
    v35 = v34;
    if ( !v34 )
    {
      v100 = -2146435066;
      throw &v100;
    }
    v36 = (char *)v34 + 48;
    v86 = (unsigned __int64)v34 + 48;
    (**((void (__fastcall ***)(__int64, _QWORD, _QWORD))v34 + 6))((__int64)v34 + 48, 0, 0);
    *((_DWORD *)v35 + 4) = *((_DWORD *)v35 + 5);
    *((_DWORD *)v35 + 5) = 0;
    if ( !SetEvent(*((HANDLE *)v35 + 3)) )
      GetLastError();
    (*(void (__fastcall **)(char *))(*(_QWORD *)v36 + 8LL))(v36);
    goto LABEL_65;
  }
  v86 = 0;
  if ( RedirectDisabled() )
  {
    WppTraceIndent(v73, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
    }
    v95 = -2146435043;
    throw &v95;
  }
  CSCardUserContext::AllocateMemory((CSCardUserContext *)v25, 0);
  v74 = (const void *)*((_QWORD *)v25 + 4);
  if ( !v74 )
  {
    LastError = GetLastError();
    throw &LastError;
  }
  if ( RedirectDisabled() )
  {
    v97 = GetLastError();
    throw &v97;
  }
  v76 = RedirectedSCardEstablishContext(dwScope, v74, v28, &v86);
  v80 = v76;
  if ( v76 == -2146435043 )
  {
    WppTraceIndent(v75, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
    }
    SetStartedEventWhenSCardSubsytemIsStarted((struct _REDIRECTION_CONTEXT *)v28);
LABEL_175:
    v98 = v76;
    throw (ulong *)&v98;
  }
  if ( v76 )
    goto LABEL_175;
  *((_QWORD *)v25 + 16) = v86;
LABEL_65:
  *((_QWORD *)v25 + 17) = v28;
  SpinCount = v28[1].SpinCount;
  LODWORD(lpCriticalSection) = SpinCount;
  v38 = g_phlContexts;
  j = 0;
  v84 = 0;
  v39 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
  v104 = (char *)g_phlContexts + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
  v40 = 0;
  for ( j = 0; ; j = v40 )
  {
    v41 = *((_DWORD *)v38 + 3);
    if ( v40 >= v41 )
      break;
    v42 = *((_QWORD *)v38 + 3) + 16LL * v40;
    v84 = v42;
    if ( !*(_QWORD *)v42 )
    {
      if ( *((_DWORD *)v38 + 4) <= v40 )
        *((_DWORD *)v38 + 4) = v40 + 1;
      goto LABEL_72;
    }
    v84 = 0;
    ++v40;
  }
  if ( v41 )
  {
    v65 = 2 * v41;
    if ( 2 * v41 > 0x7FFFFFFF )
    {
      v101 = 14;
      throw &v101;
    }
  }
  else
  {
    v65 = 4;
  }
  v66 = (char *)operator new[](saturated_mul(v65, 0x10u));
  v67 = v66;
  v84 = (__int64)v66;
  if ( !v66 )
  {
    v102 = 14;
    throw &v102;
  }
  v68 = (const void *)*((_QWORD *)v38 + 3);
  if ( v68 )
  {
    memcpy_0(v66, v68, 16LL * *((unsigned int *)v38 + 4));
    operator delete(*((void **)v38 + 3), v69);
  }
  memset_0(&v67[16 * *((unsigned int *)v38 + 4)], 0, 16LL * (v65 - *((_DWORD *)v38 + 4)));
  *((_QWORD *)v38 + 3) = v67;
  *((_DWORD *)v38 + 3) = v65;
  v40 = *((_DWORD *)v38 + 4);
  *((_DWORD *)v38 + 4) = v40 + 1;
  j = v40;
  v42 = (__int64)&v67[16 * v40];
  v84 = v42;
  SpinCount = (int)lpCriticalSection;
LABEL_72:
  *(_QWORD *)v42 = v25;
  v43 = *(_DWORD *)(v42 + 8);
  v44 = 1;
  if ( !v43 )
  {
    *(_DWORD *)(v42 + 8) = 1;
    v43 = 1;
  }
  *(_DWORD *)(v42 + 12) = SpinCount;
  v25[2] = v43 & 0xFFFFFF;
  v25[3] = v40;
  v45 = v40;
  LODWORD(v45) = v40 & 0x7FFFFFFF;
  v46 = v45 | ((*(_DWORD *)(v42 + 8) & 0xFFFFFF | ((unsigned __int64)*((unsigned int *)v38 + 2) << 24)) << 32);
  LeaveCriticalSection(v39);
  *phContext = v46;
  v47 = -1;
  v48 = 256;
  v49 = GetCurrentThreadId();
  v52 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v52 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v49;
    dword_180045874 = 0;
    goto LABEL_87;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v49 )
  {
    for ( k = 0; ; ++k )
    {
      v54 = k == 32;
      if ( k >= 0x20 )
        break;
      v50 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)k);
      if ( (_DWORD)v50 == v49 )
      {
        v52 = k;
        `WppTraceIndent'::`2'::idxCurrentThread = k;
        v54 = k == 32;
        break;
      }
      if ( v47 == -1 && !(_DWORD)v50 )
        v47 = k;
    }
    if ( v54 )
    {
      if ( v47 == -1 )
      {
        v52 = -2;
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_116;
      }
      v52 = v47;
      `WppTraceIndent'::`2'::idxCurrentThread = v47;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v47) = v49;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v47 + 1) = 0;
    }
  }
  if ( v52 < 0 )
  {
LABEL_116:
    v55 = 0;
    goto LABEL_88;
  }
LABEL_87:
  v55 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v52 + 1);
LABEL_88:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  v56 = (char *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v55 >= 1 )
  {
    do
    {
      if ( (unsigned int)StringCbCatA(v56, v50, "..") )
        break;
      ++v44;
    }
    while ( v44 <= v79 );
    v56 = (char *)WPP_GLOBAL_Control;
  }
  v57 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v57 )
  {
    ++v57;
    if ( !--v48 )
      goto LABEL_98;
  }
  v58 = "<";
  v59 = (char *)&`wil::SetLastError'::`5'::depth - v48;
  v51 = 2147483646;
  do
  {
    if ( !v51 )
      break;
    v50 = *(unsigned __int8 *)v58;
    if ( !(_BYTE)v50 )
      break;
    ++v58;
    *v59++ = v50;
    --v51;
    --v48;
  }
  while ( v48 );
  v60 = v59 - 1;
  if ( v48 )
    v60 = v59;
  *v60 = 0;
LABEL_98:
  if ( v52 >= 0 )
  {
    v50 = 8LL * v52;
    v14 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v50 + 4))-- == 1;
    if ( v14 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v50) = 0;
  }
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v56 != (char *)&WPP_GLOBAL_Control && (v56[28] & 2) != 0 )
  {
    v64 = v80;
    if ( (unsigned __int8)v56[25] >= 5u )
      WPP_SF_sd(*((_QWORD *)v56 + 2), 59, (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids, v51, v80);
  }
  else
  {
    v64 = v80;
  }
  v87 = &CBuffer::`vftable';
  if ( v88 )
    operator delete(v88, v50);
  v88 = 0;
  v89 = 0;
  return v64;
}

```

## disassembly

```asm
0x180007f40  mov     [rsp+arg_8], rbx
0x180007f45  mov     [rsp+arg_10], rsi
0x180007f4a  mov     [rsp+arg_18], r9
0x180007f4f  mov     [rsp+arg_0], ecx
0x180007f53  push    rdi
0x180007f54  push    r12
0x180007f56  push    r13
0x180007f58  push    r14
0x180007f5a  push    r15
0x180007f5c  sub     rsp, 0C0h
0x180007f63  mov     r13, r9
0x180007f66  mov     rsi, r8
0x180007f69  mov     rbx, rdx
0x180007f6c  mov     r12d, ecx
0x180007f6f  xor     edi, edi
0x180007f71  mov     [rsp+0E8h+lpCriticalSection], rdi
0x180007f76  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180007f7d  mov     [rsp+0E8h+var_88], rax
0x180007f82  mov     [rsp+0E8h+var_80], rdi
0x180007f87  mov     [rsp+0E8h+var_78], rdi
0x180007f8c  call    cs:__imp_GetCurrentThreadId
0x180007f92  mov     r9d, eax
0x180007f95  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180007f9c  lea     r14, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180007fa3  cmp     r10d, 0FFFFFFFFh
0x180007fa7  jz      loc_18000844F
0x180007fad  cmp     r10d, 0FFFFFFFEh
0x180007fb1  jz      short loc_180007FB9
0x180007fb3  cmp     [r14+r10*8], eax
0x180007fb7  jz      short loc_180007FF6
0x180007fb9  mov     r8d, 0FFFFFFFFh
0x180007fbf  mov     eax, edi
0x180007fc1  cmp     eax, 20h ; ' '
0x180007fc4  jnb     short loc_180007FF0
0x180007fc6  movsxd  rcx, eax
0x180007fc9  mov     edx, [r14+rcx*8]; unsigned __int64
0x180007fcd  cmp     edx, r9d
0x180007fd0  jz      short loc_180007FE4
0x180007fd2  cmp     r8d, 0FFFFFFFFh
0x180007fd6  jz      short loc_180007FDC
0x180007fd8  inc     eax
0x180007fda  jmp     short loc_180007FC1
0x180007fdc  test    edx, edx
0x180007fde  cmovz   r8d, eax
0x180007fe2  jmp     short loc_180007FD8
0x180007fe4  mov     r10d, eax
0x180007fe7  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180007fed  cmp     eax, 20h ; ' '
0x180007ff0  jz      loc_18000873E
0x180007ff6  test    r10d, r10d
0x180007ff9  js      loc_18000863E
0x180007fff  movsxd  rax, r10d
0x180008002  inc     dword ptr [r14+rax*8+4]
0x180008007  mov     r10d, [r14+rax*8+4]
0x18000800c  mov     [rsp+0E8h+var_98], rdi
0x180008011  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180008018  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x18000801f  test    byte ptr [rcx+1Ch], 2
0x180008023  jnz     loc_180008898
0x180008029  mov     edx, 100h
0x18000802e  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180008035  mov     rax, r10
0x180008038  cmp     byte ptr [rax], 0
0x18000803b  jnz     loc_180008874
0x180008041  mov     eax, 7FFFFFFEh
0x180008046  lea     r9, asc_1800382D0; ">"
0x18000804d  lea     r8, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008054  sub     r8, rdx
0x180008057  test    rdx, rdx
0x18000805a  jz      short loc_180008083
0x18000805c  test    rax, rax
0x18000805f  jz      short loc_18000807C
0x180008061  movzx   r10d, byte ptr [r9]
0x180008065  test    r10b, r10b
0x180008068  jz      short loc_18000807C
0x18000806a  inc     r9
0x18000806d  mov     [r8], r10b
0x180008070  inc     r8
0x180008073  dec     rax
0x180008076  sub     rdx, 1
0x18000807a  jnz     short loc_18000805C
0x18000807c  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180008083  lea     rax, [r8-1]
0x180008087  test    rdx, rdx
0x18000808a  cmovnz  rax, r8
0x18000808e  mov     byte ptr [rax], 0
0x180008091  mov     cs:?WPP_pszIndent@@3PEADEA, r10; char * WPP_pszIndent
0x180008098  lea     r15, WPP_GLOBAL_Control
0x18000809f  cmp     rcx, r15
0x1800080a2  jz      short loc_1800080AE
0x1800080a4  test    byte ptr [rcx+1Ch], 2
0x1800080a8  jnz     loc_1800088D5
0x1800080ae  test    rbx, rbx
0x1800080b1  jnz     loc_1800088F9
0x1800080b7  test    rsi, rsi
0x1800080ba  jnz     loc_180008912
0x1800080c0  test    r12d, 0FFFFFFFDh
0x1800080c7  jnz     loc_18000892B
0x1800080cd  mov     [r13+0], rdi
0x1800080d1  mov     ecx, 98h; Size
0x1800080d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800080db  mov     rsi, rax
0x1800080de  mov     [rsp+0E8h+var_90], rax
0x1800080e3  test    rax, rax
0x1800080e6  jz      loc_180008763
0x1800080ec  lea     rax, ??_7CHandle@@6B@; const CHandle::`vftable'
0x1800080f3  mov     [rsi], rax
0x1800080f6  mov     [rsi+8], edi
0x1800080f9  mov     dword ptr [rsi+0Ch], 7FFFFFFFh
0x180008100  mov     [rsi+10h], edi
0x180008103  lea     rax, ??_7CSCardUserContext@@6B@; const CSCardUserContext::`vftable'
0x18000810a  mov     [rsi], rax
0x18000810d  mov     [rsi+20h], rdi
0x180008111  mov     [rsi+28h], edi
0x180008114  lea     rax, ??_7?$CDynamicArray@VCSCardSubcontext@@@@6B@; const CDynamicArray<CSCardSubcontext>::`vftable'
0x18000811b  mov     [rsi+30h], rax
0x18000811f  mov     [rsi+3Ch], edi
0x180008122  mov     [rsi+38h], edi
0x180008125  mov     [rsi+40h], rdi
0x180008129  lea     rcx, [rsi+48h]; this
0x18000812d  call    ??0CCriticalSectionObject@@QEAA@K@Z; CCriticalSectionObject::CCriticalSectionObject(ulong)
0x180008132  nop
0x180008133  mov     [rsi+1Ch], r12d
0x180008137  mov     [rsi+80h], rdi
0x18000813e  mov     [rsi+90h], rdi
0x180008145  mov     [rsp+0E8h+var_98], rsi
0x18000814a  test    rsi, rsi
0x18000814d  jz      loc_18000894A
0x180008153  lea     rcx, [rsi+48h]
0x180008157  mov     rax, [rcx]
0x18000815a  mov     rax, [rax+10h]
0x18000815e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008163  test    eax, eax
0x180008165  jnz     loc_180008646
0x18000816b  lea     rcx, [rsp+0E8h+lpCriticalSection]; struct _REDIRECTION_CONTEXT **
0x180008170  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x180008175  mov     ebx, eax
0x180008177  mov     [rsp+0E8h+var_B8], eax
0x18000817b  test    eax, eax
0x18000817d  jnz     loc_180008997
0x180008183  mov     rbx, [rsp+0E8h+lpCriticalSection]
0x180008188  mov     r12d, 1
0x18000818e  mov     [rsp+0E8h+var_A4], r12d
0x180008193  mov     rcx, rbx; lpCriticalSection
0x180008196  call    cs:__imp_EnterCriticalSection
0x18000819c  cmp     byte ptr [rbx+28h], 0
0x1800081a0  jnz     loc_180008868
0x1800081a6  call    cs:__imp_RtlDllShutdownInProgress
0x1800081ac  test    al, al
0x1800081ae  jnz     loc_180008868
0x1800081b4  mov     rcx, rbx; lpCriticalSection
0x1800081b7  call    cs:__imp_EnterCriticalSection
0x1800081bd  cmp     byte ptr [rbx+28h], 0
0x1800081c1  jnz     short loc_1800081EB
0x1800081c3  call    cs:__imp_RtlDllShutdownInProgress
0x1800081c9  test    al, al
0x1800081cb  jnz     short loc_1800081EB
0x1800081cd  xor     r8d, r8d; pftTimeout
0x1800081d0  xor     edx, edx; h
0x1800081d2  mov     rcx, [rbx+60h]; pwa
0x1800081d6  call    cs:__imp_SetThreadpoolWait
0x1800081dc  xor     r8d, r8d; pftTimeout
0x1800081df  xor     edx, edx; h
0x1800081e1  mov     rcx, [rbx+70h]; pwa
0x1800081e5  call    cs:__imp_SetThreadpoolWait
0x1800081eb  mov     rcx, [rbx+78h]
0x1800081ef  test    rcx, rcx
0x1800081f2  jz      short loc_1800081FE
0x1800081f4  call    cs:__imp_WinStationUnRegisterNotificationEvent
0x1800081fa  mov     [rbx+78h], rdi
0x1800081fe  mov     rcx, rbx; lpCriticalSection
0x180008201  call    cs:__imp_LeaveCriticalSection
0x180008207  xor     r8d, r8d; pftTimeout
0x18000820a  mov     rdx, [rbx+68h]; h
0x18000820e  mov     rcx, [rbx+70h]; pwa
0x180008212  call    cs:__imp_SetThreadpoolWait
0x180008218  cmp     qword ptr [rbx+78h], 0
0x18000821d  jnz     short loc_180008255
0x18000821f  xor     edx, edx; dwMilliseconds
0x180008221  mov     rcx, [rbx+58h]; hHandle
0x180008225  call    cs:__imp_WaitForSingleObject
0x18000822b  test    eax, eax
0x18000822d  jnz     loc_1800089ED
0x180008233  lea     r8, [rbx+78h]
0x180008237  mov     edx, 0Fh
0x18000823c  mov     rcx, [rbx+68h]
0x180008240  call    cs:__imp_WinStationRegisterCurrentSessionNotificationEvent
0x180008246  mov     r12d, eax
0x180008249  mov     [rsp+0E8h+var_A4], eax
0x18000824d  test    eax, eax
0x18000824f  jz      loc_180008868
0x180008255  mov     rcx, rbx; lpCriticalSection
0x180008258  call    cs:__imp_LeaveCriticalSection
0x18000825e  mov     eax, edi
0x180008260  test    r12d, r12d
0x180008263  setnz   al
0x180008266  mov     [rsi+18h], eax
0x180008269  mov     rcx, rbx; lpCriticalSection
0x18000826c  call    ?UpdateConnectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateConnectionStateForContext(_REDIRECTION_CONTEXT *)
0x180008271  xor     r13b, r13b
0x180008274  mov     r15, rbx
0x180008277  mov     [rsp+0E8h+lpCriticalSection], rbx
0x18000827c  test    rbx, rbx
0x18000827f  jz      loc_180008A03
0x180008285  mov     rcx, r15; lpCriticalSection
0x180008288  call    cs:__imp_EnterCriticalSection
0x18000828e  cmp     qword ptr [r15+78h], 0
0x180008293  jnz     short loc_18000829D
0x180008295  mov     rcx, r15; lpCriticalSection
0x180008298  call    ?UpdateConnectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateConnectionStateForContext(_REDIRECTION_CONTEXT *)
0x18000829d  movzx   r12d, byte ptr [r15+2Ah]
0x1800082a2  mov     rcx, r15; lpCriticalSection
0x1800082a5  call    cs:__imp_LeaveCriticalSection
0x1800082ab  test    r13b, r13b
0x1800082ae  jnz     loc_180008A22
0x1800082b4  test    r12b, r12b
0x1800082b7  jz      loc_180008C31
0x1800082bd  mov     rcx, rbx; lpCriticalSection
0x1800082c0  call    cs:__imp_EnterCriticalSection
0x1800082c6  mov     rcx, [rbx+38h]; hEvent
0x1800082ca  call    cs:__imp_ResetEvent
0x1800082d0  mov     rcx, rbx; lpCriticalSection
0x1800082d3  call    cs:__imp_LeaveCriticalSection
0x1800082d9  mov     rcx, rbx; lpCriticalSection
0x1800082dc  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x1800082e1  test    al, al
0x1800082e3  jz      loc_180008A2F
0x1800082e9  lea     r8, [rsp+0E8h+var_88]; struct CBuffer *
0x1800082ee  lea     rdx, aScardAllreader; "SCard$AllReaders"
0x1800082f5  mov     ecx, 2; unsigned int
0x1800082fa  call    ?ListReaders@@YAXKPEBGAEAVCBuffer@@@Z; ListReaders(ulong,ushort const *,CBuffer &)
0x1800082ff  cmp     dword ptr [rsp+0E8h+var_78], 4
0x180008304  jbe     loc_1800085E0
0x18000830a  cmp     cs:dword_180045A10, 0
0x180008311  jz      short loc_18000837C
0x180008313  lea     rcx, CriticalSection; lpCriticalSection
0x18000831a  call    cs:__imp_EnterCriticalSection
0x180008320  cmp     cs:h, 0
0x180008328  jz      loc_180008BB9
0x18000832e  lea     rcx, CriticalSection; lpCriticalSection
0x180008335  call    cs:__imp_LeaveCriticalSection
0x18000833b  mov     r15, cs:h
0x180008342  test    r15, r15
0x180008345  jz      short loc_18000837C
0x180008347  mov     rcx, rbx; lpCriticalSection
0x18000834a  call    cs:__imp_EnterCriticalSection
0x180008350  cmp     byte ptr [rbx+28h], 0
0x180008354  jnz     short loc_180008373
0x180008356  call    cs:__imp_RtlDllShutdownInProgress
0x18000835c  test    al, al
0x18000835e  jnz     short loc_180008373
0x180008360  xor     r8d, r8d; pftTimeout
0x180008363  mov     rdx, r15; h
0x180008366  mov     rcx, [rbx+98h]; pwa
0x18000836d  call    cs:__imp_SetThreadpoolWait
0x180008373  mov     rcx, rbx; lpCriticalSection
0x180008376  call    cs:__imp_LeaveCriticalSection
0x18000837c  xor     edx, edx; int
0x18000837e  mov     rcx, rsi; this
0x180008381  call    ?AcquireSubcontext@CSCardUserContext@@QEAAPEAVCSCardSubcontext@@H@Z; CSCardUserContext::AcquireSubcontext(int)
0x180008386  mov     r15, rax
0x180008389  test    rax, rax
0x18000838c  jz      loc_180008BCF
0x180008392  lea     r12, [rax+30h]
0x180008396  mov     [rsp+0E8h+var_90], r12
0x18000839b  mov     rax, [r12]
0x18000839f  xor     r8d, r8d
0x1800083a2  xor     edx, edx
0x1800083a4  mov     rcx, r12
0x1800083a7  mov     rax, [rax]
0x1800083aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083af  nop
0x1800083b0  mov     eax, [r15+14h]
0x1800083b4  mov     [r15+10h], eax
0x1800083b8  mov     [r15+14h], edi
0x1800083bc  mov     rcx, [r15+18h]; hEvent
0x1800083c0  call    cs:__imp_SetEvent
0x1800083c6  test    eax, eax
0x1800083c8  jz      loc_180008BEF
0x1800083ce  mov     rax, [r12]
0x1800083d2  mov     rcx, r12
0x1800083d5  mov     rax, [rax+8]
0x1800083d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083de  mov     [rsi+88h], rbx
0x1800083e5  mov     r12d, [rbx+48h]
0x1800083e9  mov     dword ptr [rsp+0E8h+lpCriticalSection], r12d
0x1800083ee  mov     r15, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x1800083f5  mov     [rsp+0E8h+var_A8], edi
0x1800083f9  mov     [rsp+0E8h+var_A0], rdi
0x1800083fe  lea     rbx, [r15+20h]
0x180008402  mov     [rsp+0E8h+var_30], rbx
0x18000840a  mov     rcx, rbx; lpCriticalSection
0x18000840d  call    cs:__imp_EnterCriticalSection
0x180008413  nop
0x180008414  mov     edx, edi
0x180008416  mov     [rsp+0E8h+var_A8], edx
0x18000841a  nop     word ptr [rax+rax+00h]
0x180008420  mov     eax, [r15+0Ch]
0x180008424  cmp     edx, eax
0x180008426  jnb     loc_18000878C
  ... truncated ...
```
