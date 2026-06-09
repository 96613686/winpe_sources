# ScDispatcherLoop(void * *)

- ea: `0x18000bfb0`
- end: `0x18000c867`
- name: `?ScDispatcherLoop@@YAXPEAPEAX@Z`
- size: `2231`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a780`
- `0x18003aa70`

## callees

- `0x18000a9f8`
- `0x18000b460`
- `0x18000bfb0`
- `0x18000f130`
- `0x180011340`
- `0x180016bc0`
- `0x180017068`
- `0x180017584`
- `0x18001869c`
- `0x18003a764`
- `0x18003a84c`
- `0x18004b170`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18000c24f`
- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18000c24f`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18000c635`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18000c69b`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18000c635`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18000c69b`
- `ntdll!DbgPrintEx` at `0x18000c720`
- `ntdll!DbgPrintEx` at `0x18000c720`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c5f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c5f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c75f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c75f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c6df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c6df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c515`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c515`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c846`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c6f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c6f3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c466`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c466`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000c4a2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000c4e1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000c50c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000c4a2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000c4e1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000c50c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c4c6`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c4c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c006`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c006`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c27a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c313`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c27a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c054`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c08f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c114`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c609`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c769`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c78d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c82e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c054`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c08f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c114`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c609`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c769`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c78d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c82e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c0ef`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c0ef`

## string_xrefs

- `0x18000c6fe`: `[SC-CLIENT] !! Service timeout: Service %ws, PID 0x%08lx, OpCode 0x%08lx, Timeout 0x%08lx took %I64d msec !!\n`

## pseudocode

```c
void __fastcall ScDispatcherLoop(void **a1)
{
  struct _INTERNAL_DISPATCH_ENTRY *v1; // rsi
  unsigned int v2; // r13d
  unsigned int *v3; // r14
  DWORD LastError; // edi
  unsigned int v5; // r12d
  unsigned int DispatchEntry; // r15d
  unsigned __int64 v7; // rbx
  unsigned int v8; // eax
  HLOCAL v9; // rcx
  int v10; // eax
  _OWORD *v11; // rax
  __int128 v12; // xmm2
  __int128 v13; // xmm3
  __int128 v14; // xmm4
  __int128 v15; // xmm5
  __int128 v16; // xmm6
  __int128 v17; // xmm7
  char *v18; // rax
  bool v19; // zf
  __int64 v20; // rdx
  unsigned __int16 *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  unsigned __int64 v25; // r12
  int *v26; // rax
  int *v27; // rbx
  int v28; // eax
  char *v29; // r14
  unsigned __int16 *v30; // rcx
  __int64 v31; // r11
  __int64 v32; // rcx
  __int64 v33; // r14
  char *v34; // rcx
  __int64 v35; // rdx
  int v36; // r12d
  struct SC_HANDLE__ *v37; // rcx
  HANDLE v38; // rbx
  struct SC_HANDLE__ *v39; // rax
  const WCHAR *v40; // rax
  void (*v41)(void); // rbx
  __int64 v42; // rcx
  __int64 v43; // r14
  __int64 v44; // r9
  int v45; // eax
  int v46; // r14d
  __int64 v47; // r12
  int v48; // r13d
  unsigned __int64 v49; // rbx
  unsigned __int64 v50; // rax
  int v51; // ecx
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-E0h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-D8h]
  unsigned int *v54; // [rsp+30h] [rbp-D0h]
  int v55; // [rsp+50h] [rbp-B0h]
  HLOCAL v56; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v58; // [rsp+68h] [rbp-98h]
  struct _INTERNAL_DISPATCH_ENTRY *v59; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v60; // [rsp+78h] [rbp-88h]
  unsigned int *v61; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v62[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v63; // [rsp+98h] [rbp-68h]
  HLOCAL hMem[2]; // [rsp+A8h] [rbp-58h]
  DWORD ThreadId; // [rsp+B8h] [rbp-48h] BYREF
  void **v66; // [rsp+C0h] [rbp-40h]
  HANDLE hObject; // [rsp+C8h] [rbp-38h]
  __int64 v68; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v69; // [rsp+D8h] [rbp-28h]

  v66 = a1;
  v56 = 0;
  v59 = 0;
  ThreadId = 0;
  v1 = 0;
  v2 = 0;
  *(_OWORD *)v62 = 0;
  v3 = 0;
  v63 = 0;
  *(_OWORD *)hMem = 0;
  hObject = CreateEventA(0, 0, 0, 0);
  if ( !hObject )
  {
    GetLastError();
    return;
  }
  LastError = 0;
  v5 = 0;
  DispatchEntry = 0;
LABEL_4:
  LocalFree(hMem[1]);
  while ( 1 )
  {
    v7 = v62[1];
    *(_OWORD *)v62 = 0;
    if ( DispatchEntry )
      LastError = DispatchEntry;
    v63 = 0;
    *(_OWORD *)hMem = 0;
    LocalFree(v56);
    v56 = 0;
    while ( 1 )
    {
      v8 = ScSendResponseReceiveControls(
             *v66,
             hObject,
             LastError,
             v5,
             v7,
             v2,
             v3,
             (unsigned __int16 **)&v56,
             (struct _SC_CONTROL_MESSAGE_OUT_PARAMS *)v62);
      DispatchEntry = v8;
      if ( v8 == 1067 )
      {
        v9 = v56;
        goto LABEL_109;
      }
      if ( !v8 )
        break;
      Sleep(0x14u);
    }
    v5 = 1235;
    LastError = 0;
    v58 = 0;
    v2 = 0;
    LODWORD(phModule) = 0;
    LocalFree(v3);
    v3 = 0;
    v60 = 0;
    v61 = 0;
    if ( LODWORD(v62[0]) == 82 )
      goto LABEL_23;
    v9 = v56;
    if ( !*(_WORD *)v56 && LODWORD(v62[0]) == 32 )
      break;
    DispatchEntry = ScGetDispatchEntry(&v59, (unsigned __int16 *)v56);
    if ( !DispatchEntry )
    {
      v1 = v59;
      if ( LODWORD(v62[0]) == 81 )
      {
        v10 = *((_DWORD *)v59 + 14);
        if ( (v10 & 1) == 0 )
        {
          *((_DWORD *)v59 + 14) = v10 | 1;
          v11 = (char *)::hMem + 8;
          if ( v1 != (struct _INTERNAL_DISPATCH_ENTRY *)((char *)::hMem + 8) )
          {
            v12 = *(_OWORD *)v1;
            v13 = *((_OWORD *)v1 + 1);
            v14 = *((_OWORD *)v1 + 2);
            v15 = *((_OWORD *)v1 + 3);
            v16 = *((_OWORD *)v1 + 4);
            v17 = *((_OWORD *)v1 + 5);
            *(_OWORD *)v1 = *v11;
            *((_OWORD *)v1 + 1) = v11[1];
            *((_OWORD *)v1 + 2) = v11[2];
            *((_OWORD *)v1 + 3) = v11[3];
            *((_OWORD *)v1 + 4) = v11[4];
            *((_OWORD *)v1 + 5) = v11[5];
            v18 = (char *)::hMem;
            *(_OWORD *)((char *)::hMem + 8) = v12;
            *(_OWORD *)(v18 + 24) = v13;
            *(_OWORD *)(v18 + 40) = v14;
            *(_OWORD *)(v18 + 56) = v15;
            *(_OWORD *)(v18 + 72) = v16;
            *(_OWORD *)(v18 + 88) = v17;
            v1 = (struct _INTERNAL_DISPATCH_ENTRY *)((char *)::hMem + 8);
            goto LABEL_22;
          }
        }
      }
      goto LABEL_23;
    }
    if ( LODWORD(v62[0]) != 81 )
    {
      v1 = v59;
      LocalFree(hMem[1]);
      continue;
    }
    DispatchEntry = 0;
    v1 = (struct _INTERNAL_DISPATCH_ENTRY *)((char *)::hMem + 8);
    *((_DWORD *)::hMem + 16) |= 1u;
LABEL_22:
    v59 = v1;
LABEL_23:
    if ( LODWORD(v62[0]) == 80 || LODWORD(v62[0]) == 81 )
    {
      *((_DWORD *)v1 + 14) &= ~0x10u;
      v19 = (*((_BYTE *)v1 + 56) & 1) == 0;
      LODWORD(phModule) = 0;
      if ( !v19 && _wcsicmp(*((const wchar_t **)v1 + 1), (const wchar_t *)v56) )
      {
        v20 = -1;
        do
          v19 = *((_WORD *)v56 + ++v20) == 0;
        while ( !v19 );
        v21 = (unsigned __int16 *)LocalAlloc(0, 2 * v20 + 2);
        *((_QWORD *)v1 + 2) = v21;
        if ( !v21 )
        {
          LastError = 8;
          *((_QWORD *)v1 + 2) = *((_QWORD *)v1 + 1);
          LocalFree(hMem[1]);
          continue;
        }
        v22 = -1;
        do
          v19 = *((_WORD *)v56 + ++v22) == 0;
        while ( !v19 );
        StringCbCopyW(v21, 2 * v22 + 2, (const unsigned __int16 *)v56);
        LastError = ScCheckServiceSids();
        if ( !LastError )
          goto LABEL_33;
        goto LABEL_4;
      }
LABEL_33:
      v23 = -1;
      do
        v19 = *((_WORD *)v56 + ++v23) == 0;
      while ( !v19 );
      if ( hMem[1] )
        v24 = 8LL * *(unsigned int *)hMem[1];
      else
        v24 = 0;
      v25 = (unsigned int)(2 * v23 + 2);
      v26 = (int *)LocalAlloc(0x40u, v25 + v24 + 32);
      v27 = v26;
      if ( !v26 )
      {
        LastError = 8;
        v5 = 1235;
        LocalFree(hMem[1]);
        continue;
      }
      *((_QWORD *)v26 + 1) = *((_QWORD *)v1 + 4);
      v26[1] = DWORD1(v63);
      if ( hMem[1] )
        v28 = *(_DWORD *)hMem[1] + 1;
      else
        v28 = 1;
      *v27 = v28;
      *((HLOCAL *)v27 + 2) = hMem[1];
      *((_DWORD *)v1 + 22) = HIDWORD(v63);
      v29 = (char *)hMem[1];
      if ( hMem[1] )
        v29 = (char *)hMem[1] + 8;
      v30 = (unsigned __int16 *)&v27[2 * *v27 + 6];
      *((_QWORD *)v27 + 3) = v30;
      StringCbCopyW(v30, v25, (const unsigned __int16 *)v56);
      v31 = 0;
      if ( *v27 != 1 )
      {
        do
        {
          v32 = 2 * v31;
          v31 = (unsigned int)(v31 + 1);
          *(_QWORD *)&v27[v32 + 8] = *(_QWORD *)&v29[v32 * 4];
        }
        while ( (unsigned int)v31 < *v27 - 1 );
      }
      *((_DWORD *)v1 + 18) = DWORD1(v63);
      if ( dword_18007C5C0 )
      {
        v33 = 0;
        if ( *v27 )
        {
          do
          {
            v34 = *(char **)&v27[2 * v33 + 6];
            v35 = -1;
            do
              v19 = *(_WORD *)&v34[2 * v35++ + 2] == 0;
            while ( !v19 );
            if ( !ScConvertUnicodeToAnsi(v34, 2 * v35 + 2, *(const unsigned __int16 **)&v27[2 * v33 + 6]) )
              LastError = 8;
            v33 = (unsigned int)(v33 + 1);
          }
          while ( (unsigned int)v33 < *v27 );
          v2 = v58;
        }
        v5 = 1235;
        if ( LastError )
          goto LABEL_5;
      }
      v36 = 0;
      LastError = ScAdjustSidState(v1, 1, (int *)&phModule);
      if ( LastError )
        goto LABEL_69;
      v38 = CreateThread(0, 0, ScSvcctrlThreadA, v27, 4u, &ThreadId);
      if ( !v38 )
      {
        LastError = 1054;
        goto LABEL_69;
      }
      v39 = I_ScOpenServiceStatusHandle(v37, (unsigned __int16 *)v56, v62[1]);
      *((_QWORD *)v1 + 6) = v39;
      if ( v39 )
      {
        v36 = 1;
      }
      else
      {
        LastError = GetLastError();
        TerminateThread(v38, LastError);
        CloseHandle(v38);
        if ( LastError )
          goto LABEL_69;
      }
      if ( (v63 & 1) == 0 )
      {
        if ( ResumeThread(v38) == -1 )
        {
          LastError = GetLastError();
          TerminateThread(v38, 0x41Eu);
        }
        CloseHandle(v38);
        if ( !LastError )
          goto LABEL_71;
        goto LABEL_69;
      }
      LastError = ScLowerThreadPriorityAndResume(v38, v1);
      if ( LastError )
      {
        TerminateThread(v38, 0x41Eu);
        CloseHandle(v38);
LABEL_69:
        if ( (_DWORD)phModule == 1 )
          ScAdjustSidState(v1, 0, 0);
      }
LABEL_71:
      v3 = v60;
      v19 = v36 == 0;
      v5 = 1235;
      if ( !v19 && LastError )
      {
        CloseServiceHandle(*((SC_HANDLE *)v1 + 6));
        *((_QWORD *)v1 + 6) = 0;
LABEL_5:
        v3 = v60;
        continue;
      }
    }
    else
    {
      if ( LODWORD(v62[0]) == 82 )
      {
        LastError = ScGetServiceTagsReferencingModule((LPCWSTR)v56, (unsigned int *)&phModule, &v61);
        v2 = (unsigned int)phModule;
        v3 = v61;
        LocalFree(hMem[1]);
        continue;
      }
      if ( LODWORD(v62[0]) == 96 )
      {
        if ( g_NotificationCallback )
        {
          v68 = 0;
          v69 = 0;
          v68 = **((_QWORD **)hMem[1] + 1);
          if ( g_NotificationCallback(
                 0x60u,
                 *((const unsigned __int16 **)v1 + 1),
                 (struct _SC_SVCHOST_NOTIFICATION *)&v68)
            || !(_DWORD)v69 )
          {
            goto LABEL_4;
          }
        }
      }
      v40 = (const WCHAR *)_InterlockedCompareExchange64((volatile signed __int64 *)v1 + 5, 0, 0);
      v41 = (void (*)(void))v40;
      if ( v40 )
      {
        phModule = 0;
        if ( (*((_BYTE *)v1 + 56) & 4) == 0 && !GetModuleHandleExW(4u, v40, &phModule) )
        {
          LastError = 1061;
          LocalFree(hMem[1]);
          continue;
        }
        v42 = *((unsigned int *)v1 + 18);
        v61 = (unsigned int *)((((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                              * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64);
        v43 = RtlSetThreadSubProcessTag(v42);
        if ( (*((_BYTE *)v1 + 56) & 2) != 0 )
        {
          v44 = *((_QWORD *)v1 + 8);
          if ( hMem[1] )
            v45 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))v41)(
                    LODWORD(v62[0]),
                    *(unsigned int *)hMem[1],
                    *((_QWORD *)hMem[1] + 1),
                    v44);
          else
            v45 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))v41)(LODWORD(v62[0]), 0, 0, v44);
LABEL_92:
          v55 = v45;
        }
        else
        {
          if ( (unsigned int)(LODWORD(v62[0]) - 1) <= 9 || (unsigned int)(LODWORD(v62[0]) - 128) <= 0x7F )
          {
            v41();
            v45 = 0;
            goto LABEL_92;
          }
          v55 = 120;
        }
        RtlSetThreadSubProcessTag(v43);
        v46 = DWORD2(v63);
        v47 = *((_QWORD *)v1 + 2);
        v48 = v62[0];
        if ( DWORD2(v63) )
        {
          v49 = ((((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64)
              - (_QWORD)v61;
          v50 = DWORD2(v63);
          LODWORD(v50) = DWORD2(v63) & 0x7FFFFFFF;
          if ( v49 >= v50 && !IsDebuggerPresent() && MEMORY[0x7FFE02D4] )
          {
            LODWORD(v54) = v46;
            LODWORD(lpThreadId) = v48;
            dwCreationFlags[0] = GetCurrentProcessId();
            DbgPrintEx(
              0x26u,
              0x80000001,
              "[SC-CLIENT] !! Service timeout: Service %ws, PID 0x%08lx, OpCode 0x%08lx, Timeout 0x%08lx took %I64d msec !!\n",
              v47,
              *(_QWORD *)dwCreationFlags,
              lpThreadId,
              v54,
              v49);
          }
        }
        if ( LODWORD(v62[0]) <= 0xF )
        {
          v51 = 32802;
          if ( _bittest(&v51, v62[0]) )
          {
            _InterlockedExchange64((volatile __int64 *)v1 + 5, 0);
            *((_DWORD *)v1 + 14) |= 0x10u;
          }
        }
        v3 = v60;
        v5 = v55;
        v2 = v58;
        if ( phModule )
        {
          FreeLibrary(phModule);
          LocalFree(hMem[1]);
          continue;
        }
        goto LABEL_4;
      }
      LastError = 1061;
      if ( (*((_BYTE *)v1 + 56) & 0x10) == 0 )
        goto LABEL_4;
      v5 = 0x80000000;
      LocalFree(hMem[1]);
    }
  }
LABEL_109:
  if ( v9 )
  {
    LocalFree(v9);
    v56 = 0;
  }
  ScCloseServiceChannelHandle(v66);
  CloseHandle(hObject);
}

```

## disassembly

```asm
0x18000bfb0  push    rbp
0x18000bfb2  push    rbx
0x18000bfb3  push    rsi
0x18000bfb4  push    r13
0x18000bfb6  push    r14
0x18000bfb8  lea     rbp, [rsp-10h]
0x18000bfbd  sub     rsp, 110h
0x18000bfc4  mov     rax, cs:__security_cookie
0x18000bfcb  xor     rax, rsp
0x18000bfce  mov     [rbp+30h+var_50], rax
0x18000bfd2  xor     ebx, ebx
0x18000bfd4  mov     [rbp+30h+var_70], rcx
0x18000bfd8  xorps   xmm0, xmm0
0x18000bfdb  mov     [rsp+130h+var_D8], rbx
0x18000bfe0  xor     ecx, ecx; lpEventAttributes
0x18000bfe2  mov     [rsp+130h+var_C0], rbx
0x18000bfe7  xor     r9d, r9d; lpName
0x18000bfea  mov     [rbp+30h+ThreadId], ebx
0x18000bfed  xor     r8d, r8d; bInitialState
0x18000bff0  xor     edx, edx; bManualReset
0x18000bff2  mov     esi, ebx
0x18000bff4  mov     r13d, ebx
0x18000bff7  movups  xmmword ptr [rbp+30h+var_A8], xmm0
0x18000bffb  mov     r14d, ebx
0x18000bffe  movups  [rbp+30h+var_98], xmm0
0x18000c002  movups  xmmword ptr [rbp+30h+hMem], xmm0
0x18000c006  call    cs:__imp_CreateEventA
0x18000c00c  mov     [rbp+30h+hObject], rax
0x18000c010  test    rax, rax
0x18000c013  jnz     short loc_18000C020
0x18000c015  call    cs:__imp_GetLastError
0x18000c01b  jmp     loc_18000C84C
0x18000c020  mov     [rsp+130h+arg_8], rdi
0x18000c028  mov     edi, ebx
0x18000c02a  mov     [rsp+130h+arg_10], r12
0x18000c032  mov     r12d, ebx
0x18000c035  mov     [rsp+130h+arg_18], r15
0x18000c03d  mov     r15d, ebx
0x18000c040  movaps  [rsp+130h+var_30], xmm6
0x18000c048  movaps  [rsp+130h+var_40], xmm7
0x18000c050  mov     rcx, [rbp+30h+hMem+8]; hMem
0x18000c054  call    cs:__imp_LocalFree
0x18000c05a  jmp     short loc_18000C070
0x18000c060  mov     r14, [rsp+130h+var_B8]
0x18000c065  nop     word ptr [rax+rax+00000000h]
0x18000c070  mov     rbx, [rbp+30h+var_A8+8]
0x18000c074  xorps   xmm0, xmm0
0x18000c077  mov     rcx, [rsp+130h+var_D8]; hMem
0x18000c07c  test    r15d, r15d
0x18000c07f  movups  xmmword ptr [rbp+30h+var_A8], xmm0
0x18000c083  cmovnz  edi, r15d
0x18000c087  movups  [rbp+30h+var_98], xmm0
0x18000c08b  movups  xmmword ptr [rbp+30h+hMem], xmm0
0x18000c08f  call    cs:__imp_LocalFree
0x18000c095  mov     [rsp+130h+var_D8], 0
0x18000c09e  xchg    ax, ax
0x18000c0a0  mov     rdx, [rbp+30h+hObject]; void *
0x18000c0a4  lea     rax, [rbp+30h+var_A8]
0x18000c0a8  mov     [rsp+130h+var_F0], rax; struct _SC_CONTROL_MESSAGE_OUT_PARAMS *
0x18000c0ad  mov     r9d, r12d; unsigned int
0x18000c0b0  lea     rax, [rsp+130h+var_D8]
0x18000c0b5  mov     r8d, edi; unsigned int
0x18000c0b8  mov     [rsp+130h+var_F8], rax; unsigned __int16 **
0x18000c0bd  mov     rax, [rbp+30h+var_70]
0x18000c0c1  mov     [rsp+130h+var_100], r14; unsigned int *
0x18000c0c6  mov     dword ptr [rsp+130h+lpThreadId], r13d; unsigned int
0x18000c0cb  mov     qword ptr [rsp+130h+dwCreationFlags], rbx; unsigned __int64
0x18000c0d0  mov     rcx, [rax]; void *
0x18000c0d3  call    ?ScSendResponseReceiveControls@@YAKPEAX0KK_KKPEAKPEAPEAGPEAU_SC_CONTROL_MESSAGE_OUT_PARAMS@@@Z; ScSendResponseReceiveControls(void *,void *,ulong,ulong,unsigned __int64,ulong,ulong *,ushort * *,_SC_CONTROL_MESSAGE_OUT_PARAMS *)
0x18000c0d8  mov     r15d, eax
0x18000c0db  cmp     eax, 42Bh
0x18000c0e0  jz      loc_18000C7FA
0x18000c0e6  test    eax, eax
0x18000c0e8  jz      short loc_18000C0F7
0x18000c0ea  mov     ecx, 14h; dwMilliseconds
0x18000c0ef  call    cs:__imp_Sleep
0x18000c0f5  jmp     short loc_18000C0A0
0x18000c0f7  xor     ebx, ebx
0x18000c0f9  mov     r12d, 4D3h
0x18000c0ff  mov     rcx, r14; hMem
0x18000c102  mov     [rsp+130h+var_E0], r12d
0x18000c107  mov     edi, ebx
0x18000c109  mov     [rsp+130h+var_C8], ebx
0x18000c10d  mov     r13d, ebx
0x18000c110  mov     dword ptr [rsp+130h+phModule], ebx
0x18000c114  call    cs:__imp_LocalFree
0x18000c11a  mov     eax, dword ptr [rbp+30h+var_A8]
0x18000c11d  mov     r14d, ebx
0x18000c120  mov     [rsp+130h+var_B8], rbx
0x18000c125  mov     [rbp+30h+var_B0], rbx
0x18000c129  cmp     eax, 52h ; 'R'
0x18000c12c  jz      loc_18000C223
0x18000c132  mov     rcx, [rsp+130h+var_D8]
0x18000c137  cmp     [rcx], bx
0x18000c13a  jnz     short loc_18000C145
0x18000c13c  cmp     eax, 20h ; ' '
0x18000c13f  jz      loc_18000C801
0x18000c145  mov     rdx, rcx; unsigned __int16 *
0x18000c148  lea     rcx, [rsp+130h+var_C0]; struct _INTERNAL_DISPATCH_ENTRY **
0x18000c14d  call    ?ScGetDispatchEntry@@YAKPEAPEAU_INTERNAL_DISPATCH_ENTRY@@PEAG@Z; ScGetDispatchEntry(_INTERNAL_DISPATCH_ENTRY * *,ushort *)
0x18000c152  mov     r15d, eax
0x18000c155  test    eax, eax
0x18000c157  jnz     loc_18000C202
0x18000c15d  cmp     dword ptr [rbp+30h+var_A8], 51h ; 'Q'
0x18000c161  mov     rsi, [rsp+130h+var_C0]
0x18000c166  jnz     loc_18000C223
0x18000c16c  mov     eax, [rsi+38h]
0x18000c16f  test    al, 1
0x18000c171  jnz     loc_18000C223
0x18000c177  or      eax, 1
0x18000c17a  mov     [rsi+38h], eax
0x18000c17d  mov     rax, cs:hMem
0x18000c184  add     rax, 8
0x18000c188  cmp     rsi, rax
0x18000c18b  jz      loc_18000C223
0x18000c191  movups  xmm0, xmmword ptr [rax]
0x18000c194  movups  xmm2, xmmword ptr [rsi]
0x18000c197  movups  xmm3, xmmword ptr [rsi+10h]
0x18000c19b  movups  xmm4, xmmword ptr [rsi+20h]
0x18000c19f  movups  xmm5, xmmword ptr [rsi+30h]
0x18000c1a3  movups  xmm6, xmmword ptr [rsi+40h]
0x18000c1a7  movups  xmm7, xmmword ptr [rsi+50h]
0x18000c1ab  movups  xmmword ptr [rsi], xmm0
0x18000c1ae  movups  xmm1, xmmword ptr [rax+10h]
0x18000c1b2  movups  xmmword ptr [rsi+10h], xmm1
0x18000c1b6  movups  xmm0, xmmword ptr [rax+20h]
0x18000c1ba  movups  xmmword ptr [rsi+20h], xmm0
0x18000c1be  movups  xmm1, xmmword ptr [rax+30h]
0x18000c1c2  movups  xmmword ptr [rsi+30h], xmm1
0x18000c1c6  movups  xmm0, xmmword ptr [rax+40h]
0x18000c1ca  movups  xmmword ptr [rsi+40h], xmm0
0x18000c1ce  movups  xmm1, xmmword ptr [rax+50h]
0x18000c1d2  movups  xmmword ptr [rsi+50h], xmm1
0x18000c1d6  mov     rax, cs:hMem
0x18000c1dd  movups  xmmword ptr [rax+8], xmm2
0x18000c1e1  movups  xmmword ptr [rax+18h], xmm3
0x18000c1e5  movups  xmmword ptr [rax+28h], xmm4
0x18000c1e9  movups  xmmword ptr [rax+38h], xmm5
0x18000c1ed  movups  xmmword ptr [rax+48h], xmm6
0x18000c1f1  movups  xmmword ptr [rax+58h], xmm7
0x18000c1f5  mov     rsi, cs:hMem
0x18000c1fc  add     rsi, 8
0x18000c200  jmp     short loc_18000C21E
0x18000c202  cmp     dword ptr [rbp+30h+var_A8], 51h ; 'Q'
0x18000c206  jnz     loc_18000C560
0x18000c20c  mov     rsi, cs:hMem
0x18000c213  mov     r15d, ebx
0x18000c216  add     rsi, 8
0x18000c21a  or      dword ptr [rsi+38h], 1
0x18000c21e  mov     [rsp+130h+var_C0], rsi
0x18000c223  mov     eax, dword ptr [rbp+30h+var_A8]
0x18000c226  sub     eax, 50h ; 'P'
0x18000c229  jz      short loc_18000C234
0x18000c22b  sub     eax, 1
0x18000c22e  jnz     loc_18000C574
0x18000c234  and     dword ptr [rsi+38h], 0FFFFFFEFh
0x18000c238  test    byte ptr [rsi+38h], 1
0x18000c23c  mov     dword ptr [rsp+130h+phModule], ebx
0x18000c240  jz      loc_18000C2CB
0x18000c246  mov     rdx, [rsp+130h+var_D8]; String2
0x18000c24b  mov     rcx, [rsi+8]; String1
0x18000c24f  call    cs:__imp__wcsicmp
0x18000c255  test    eax, eax
0x18000c257  jz      short loc_18000C2CB
0x18000c259  mov     rax, [rsp+130h+var_D8]
0x18000c25e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000c265  cmp     [rax+rdx*2+2], bx
0x18000c26a  lea     rdx, [rdx+1]
0x18000c26e  jnz     short loc_18000C265
0x18000c270  lea     rdx, ds:2[rdx*2]; uBytes
0x18000c278  xor     ecx, ecx; uFlags
0x18000c27a  call    cs:__imp_LocalAlloc
0x18000c280  mov     [rsi+10h], rax
0x18000c284  test    rax, rax
0x18000c287  jz      loc_18000C7C5
0x18000c28d  mov     r8, [rsp+130h+var_D8]; unsigned __int16 *
0x18000c292  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000c299  nop     dword ptr [rax+00000000h]
0x18000c2a0  cmp     [r8+rdx*2+2], bx
0x18000c2a6  lea     rdx, [rdx+1]
0x18000c2aa  jnz     short loc_18000C2A0
0x18000c2ac  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000c2b4  mov     rcx, rax; unsigned __int16 *
0x18000c2b7  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c2bc  call    ?ScCheckServiceSids@@YAKXZ; ScCheckServiceSids(void)
0x18000c2c1  mov     edi, eax
0x18000c2c3  test    eax, eax
0x18000c2c5  jnz     loc_18000C050
0x18000c2cb  mov     rcx, [rsp+130h+var_D8]
0x18000c2d0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c2d7  nop     word ptr [rax+rax+00000000h]
0x18000c2e0  cmp     [rcx+rax*2+2], bx
0x18000c2e5  lea     rax, [rax+1]
0x18000c2e9  jnz     short loc_18000C2E0
0x18000c2eb  mov     rcx, [rbp+30h+hMem+8]
0x18000c2ef  test    rcx, rcx
0x18000c2f2  jz      short loc_18000C2FC
0x18000c2f4  mov     ecx, [rcx]
0x18000c2f6  shl     rcx, 3
0x18000c2fa  jmp     short loc_18000C2FF
0x18000c2fc  mov     rcx, rbx
0x18000c2ff  lea     rdx, [rcx+20h]
0x18000c303  mov     ecx, 40h ; '@'; uFlags
0x18000c308  lea     r12d, ds:2[rax*2]
0x18000c310  add     rdx, r12; uBytes
0x18000c313  call    cs:__imp_LocalAlloc
0x18000c319  mov     rbx, rax
0x18000c31c  test    rax, rax
0x18000c31f  jz      loc_18000C7E1
0x18000c325  mov     rax, [rsi+20h]
0x18000c329  mov     [rbx+8], rax
0x18000c32d  mov     eax, dword ptr [rbp+30h+var_98+4]
0x18000c330  mov     [rbx+4], eax
0x18000c333  mov     rax, [rbp+30h+hMem+8]
0x18000c337  test    rax, rax
0x18000c33a  jz      short loc_18000C342
0x18000c33c  mov     eax, [rax]
0x18000c33e  inc     eax
0x18000c340  jmp     short loc_18000C347
0x18000c342  mov     eax, 1
0x18000c347  mov     [rbx], eax
0x18000c349  mov     rax, [rbp+30h+hMem+8]
0x18000c34d  mov     [rbx+10h], rax
0x18000c351  mov     eax, dword ptr [rbp+30h+var_98+0Ch]
0x18000c354  mov     [rsi+58h], eax
0x18000c357  mov     r14, [rbp+30h+hMem+8]
0x18000c35b  test    r14, r14
0x18000c35e  jz      short loc_18000C364
0x18000c360  add     r14, 8
0x18000c364  mov     eax, [rbx]
0x18000c366  mov     rdx, r12; unsigned __int64
0x18000c369  add     rax, 3
0x18000c36d  lea     rcx, [rbx+rax*8]; unsigned __int16 *
0x18000c371  mov     [rbx+18h], rcx
0x18000c375  mov     r8, [rsp+130h+var_D8]; unsigned __int16 *
0x18000c37a  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c37f  xor     r11d, r11d
0x18000c382  cmp     dword ptr [rbx], 1
0x18000c385  jz      short loc_18000C3AD
0x18000c387  nop     word ptr [rax+rax+00000000h]
0x18000c390  lea     rcx, ds:0[r11*8]
0x18000c398  inc     r11d
0x18000c39b  mov     rax, [rcx+r14]
0x18000c39f  mov     [rbx+rcx+20h], rax
0x18000c3a4  mov     eax, [rbx]
0x18000c3a6  dec     eax
0x18000c3a8  cmp     r11d, eax
0x18000c3ab  jb      short loc_18000C390
0x18000c3ad  mov     eax, dword ptr [rbp+30h+var_98+4]
0x18000c3b0  mov     [rsi+48h], eax
0x18000c3b3  cmp     cs:dword_18007C5C0, r13d
0x18000c3ba  jz      short loc_18000C425
0x18000c3bc  xor     r14d, r14d
0x18000c3bf  cmp     [rbx], r13d
0x18000c3c2  jbe     short loc_18000C40F
0x18000c3c4  mov     r13d, 8
0x18000c3ca  nop     word ptr [rax+rax+00h]
0x18000c3d0  mov     rcx, [rbx+r14*8+18h]; char *
0x18000c3d5  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000c3dc  nop     dword ptr [rax+00h]
0x18000c3e0  cmp     word ptr [rcx+rdx*2+2], 0
0x18000c3e6  lea     rdx, [rdx+1]
0x18000c3ea  jnz     short loc_18000C3E0
0x18000c3ec  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000c3f4  mov     r8, rcx; unsigned __int16 *
0x18000c3f7  call    ?ScConvertUnicodeToAnsi@@YAHPEAD_KPEBG@Z; ScConvertUnicodeToAnsi(char *,unsigned __int64,ushort const *)
0x18000c3fc  test    eax, eax
0x18000c3fe  cmovz   edi, r13d
0x18000c402  inc     r14d
0x18000c405  cmp     r14d, [rbx]
0x18000c408  jb      short loc_18000C3D0
0x18000c40a  mov     r13d, [rsp+130h+var_C8]
0x18000c40f  mov     r12d, [rsp+130h+var_E0]
0x18000c414  lea     r14, ?ScSvcctrlThreadA@@YAKPEAU_THREAD_STARTUP_PARMSA@@@Z; ScSvcctrlThreadA(_THREAD_STARTUP_PARMSA *)
0x18000c41b  test    edi, edi
0x18000c41d  jnz     loc_18000C060
0x18000c423  jmp     short loc_18000C42C
0x18000c425  lea     r14, ?ScSvcctrlThreadA@@YAKPEAU_THREAD_STARTUP_PARMSA@@@Z; ScSvcctrlThreadA(_THREAD_STARTUP_PARMSA *)
0x18000c42c  lea     r8, [rsp+130h+phModule]; int *
0x18000c431  mov     edx, 1; int
0x18000c436  mov     rcx, rsi; struct _INTERNAL_DISPATCH_ENTRY *
0x18000c439  xor     r12d, r12d
0x18000c43c  call    ?ScAdjustSidState@@YAKPEAU_INTERNAL_DISPATCH_ENTRY@@HPEAH@Z; ScAdjustSidState(_INTERNAL_DISPATCH_ENTRY *,int,int *)
0x18000c441  mov     edi, eax
0x18000c443  test    eax, eax
0x18000c445  jnz     loc_18000C51B
0x18000c44b  lea     rax, [rbp+30h+ThreadId]
0x18000c44f  mov     r9, rbx; lpParameter
0x18000c452  mov     [rsp+130h+lpThreadId], rax; lpThreadId
0x18000c457  mov     r8, r14; lpStartAddress
0x18000c45a  xor     edx, edx; dwStackSize
0x18000c45c  mov     [rsp+130h+dwCreationFlags], 4; dwCreationFlags
0x18000c464  xor     ecx, ecx; lpThreadAttributes
0x18000c466  call    cs:__imp_CreateThread
0x18000c46c  mov     rbx, rax
0x18000c46f  test    rax, rax
0x18000c472  jnz     short loc_18000C47E
0x18000c474  mov     edi, 41Eh
0x18000c479  jmp     loc_18000C51B
0x18000c47e  mov     r8, [rbp+30h+var_A8+8]; unsigned __int64
  ... truncated ...
```
