# CWerService::ReportCrashKernelMsg(_DBGKM_APIMSG *)

- ea: `0x180016ac0`
- end: `0x180017571`
- name: `?ReportCrashKernelMsg@CWerService@@AEAAJPEAU_DBGKM_APIMSG@@@Z`
- size: `2737`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _DBGKM_APIMSG *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019ef4`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006a80`
- `0x180011ef8`
- `0x180013df4`
- `0x180016ac0`
- `0x18001a6d8`
- `0x18001ad28`
- `0x18001e41c`
- `0x180024474`
- `0x18002c9dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180017529`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180017529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016e48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016ef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016fbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017067`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016e48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016ef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016fbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017067`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180017503`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180017503`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800174c2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800174c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180017050`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180017050`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800171a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800171a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017534`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800174b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800174b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016c99`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016c99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016da9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016de7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016edd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016da9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016de7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016edd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016e74`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016f22`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016fe2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180017093`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016e74`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016f22`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016fe2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180017093`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180016d94`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180016d94`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180016f9c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180016f9c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180016d22`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180016d22`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016b7a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016ba5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016bd9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016b7a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016ba5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016bd9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180017351`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180017351`
- `wer!WerpAddTerminationReason` at `0x180017519`
- `wer!WerpAddTerminationReason` at `0x180017519`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWerService::ReportCrashKernelMsg(CWerService *this, struct _DBGKM_APIMSG *a2)
{
  char *v3; // r15
  void *v4; // r12
  DWORD v5; // r14d
  char *v6; // rsi
  char *v7; // rbx
  signed int LastError; // eax
  signed int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  HANDLE v13; // rbx
  signed int v14; // eax
  signed int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  HANDLE CurrentProcess; // rax
  unsigned int v21; // r12d
  HANDLE *v22; // rbx
  signed int v23; // eax
  bool v24; // sf
  HANDLE v25; // rax
  signed int v26; // eax
  DWORD v27; // ebx
  HANDLE v28; // rax
  signed int v29; // eax
  bool v30; // sf
  HANDLE v31; // rax
  signed int v32; // eax
  bool v33; // sf
  signed int v34; // eax
  bool v35; // sf
  HANDLE v36; // rax
  int v37; // eax
  __int64 v38; // rdx
  CWerService *v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  HANDLE v42; // r9
  unsigned int v43; // ebx
  int v44; // eax
  HANDLE v45; // rax
  HANDLE v46; // r9
  unsigned __int64 v47; // rbx
  DWORD v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  signed int v53; // eax
  _QWORD *v54; // rcx
  __int64 v55; // rdx
  int v56; // eax
  unsigned int v57; // r15d
  DWORD v58; // r14d
  __int64 v59; // r8
  DWORD ProcessId; // eax
  signed int v61; // eax
  char *hSourceHandle; // [rsp+50h] [rbp-B0h]
  DWORD v63; // [rsp+58h] [rbp-A8h] BYREF
  void *v64; // [rsp+60h] [rbp-A0h]
  unsigned int v65; // [rsp+68h] [rbp-98h]
  DWORD ExitCode; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD dwThreadId; // [rsp+70h] [rbp-90h]
  HANDLE TargetHandle; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v69; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v70; // [rsp+88h] [rbp-78h] BYREF
  HANDLE v71; // [rsp+90h] [rbp-70h] BYREF
  LPCVOID lpBaseAddress; // [rsp+98h] [rbp-68h]
  struct _DBGKM_APIMSG *v73; // [rsp+A0h] [rbp-60h]
  HANDLE hObject; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v75; // [rsp+B0h] [rbp-50h]
  char *v76; // [rsp+B8h] [rbp-48h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+C0h] [rbp-40h] BYREF
  CWerService *v78; // [rsp+D8h] [rbp-28h]
  HANDLE Handles[2]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v80[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v81; // [rsp+100h] [rbp+0h]
  __int128 v82; // [rsp+110h] [rbp+10h]
  __int128 v83; // [rsp+120h] [rbp+20h]
  __int128 v84; // [rsp+130h] [rbp+30h]
  __int128 v85; // [rsp+140h] [rbp+40h]
  __int128 v86; // [rsp+150h] [rbp+50h]
  __int128 v87; // [rsp+160h] [rbp+60h]
  __int128 v88; // [rsp+170h] [rbp+70h]
  __int128 v89; // [rsp+180h] [rbp+80h]
  __int64 v90; // [rsp+190h] [rbp+90h]
  int v91; // [rsp+1A0h] [rbp+A0h]
  HANDLE v92; // [rsp+1A8h] [rbp+A8h]
  HANDLE v93; // [rsp+1B0h] [rbp+B0h]
  HANDLE v94; // [rsp+1C0h] [rbp+C0h]
  int v95; // [rsp+1D8h] [rbp+D8h]
  int v96; // [rsp+1DCh] [rbp+DCh]
  DWORD TickCount; // [rsp+1E0h] [rbp+E0h]
  _OWORD v98[2]; // [rsp+1F0h] [rbp+F0h] BYREF

  v73 = a2;
  v78 = this;
  v3 = 0;
  hSourceHandle = 0;
  v71 = 0;
  v4 = 0;
  v64 = 0;
  TargetHandle = 0;
  v69 = 0;
  v75 = 0;
  v70 = 0;
  hObject = 0;
  lpBaseAddress = 0;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 1;
  *(_OWORD *)Handles = 0;
  memset(v98, 0, sizeof(v98));
  v65 = *((_DWORD *)a2 + 2);
  v5 = v65;
  dwThreadId = *((_DWORD *)a2 + 4);
  *((_DWORD *)a2 + 11) = -2147418111;
  EventAttributes.lpSecurityDescriptor = 0;
  v6 = (char *)OpenProcess(0x100441u, 0, v5);
  v76 = v6;
  if ( (v6 == (char *)-1LL || v6 + 1 == (char *)1) && GetLastError() == 5 )
  {
    v6 = (char *)OpenProcess(0x101001u, 0, v5);
    v76 = v6;
    v7 = v6;
  }
  else
  {
    v7 = v6;
  }
  if ( (unsigned __int64)(v7 + 1) <= 1 && GetLastError() == 5 )
  {
    v6 = (char *)OpenProcess(0x1000u, 0, v5);
    v76 = v6;
    v7 = v6;
  }
  if ( (unsigned __int64)(v7 + 1) <= 1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v11 = 128;
    v12 = (unsigned int)v9;
    goto LABEL_16;
  }
  v63 = 0;
  UtilGetProtectedProcessInfo(v6, (enum _PS_PROTECTED_TYPE *)&v63, 0);
  v63 = (int)v63 > 0;
  if ( (*((_BYTE *)a2 + 264) & 4) != 0 )
  {
    *((_DWORD *)a2 + 11) = -2147418111;
    v9 = 0;
    goto LABEL_37;
  }
  v13 = CreateEventW(&EventAttributes, 1, 0, 0);
  v64 = v13;
  if ( (unsigned __int64)v13 + 1 <= 1
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      129,
      WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      (unsigned int)v14);
  }
  hSourceHandle = (char *)CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &EventAttributes, 4u, 0, 0xF8u, 0);
  if ( hSourceHandle == (char *)-1LL || hSourceHandle + 1 == (char *)1 )
  {
    v15 = GetLastError();
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v17 = 130;
    goto LABEL_33;
  }
  if ( v63 )
  {
    v21 = 0;
    ExitCode = 1;
    goto LABEL_73;
  }
  if ( (unsigned __int64)v13 + 1 <= 1 )
    goto LABEL_62;
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v13, v6, &TargetHandle, 0, 1, 2u) )
  {
    v23 = GetLastError();
    v24 = v23 < 0;
    if ( v23 > 0 )
    {
      v23 = (unsigned __int16)v23 | 0x80070000;
      v24 = v23 < 0;
    }
    if ( !v24 )
      v23 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        131,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)v23);
    v64 = 0;
    CloseHandle(v13);
    TargetHandle = 0;
LABEL_62:
    v22 = (HANDLE *)v98;
    v21 = 1;
    goto LABEL_63;
  }
  *(_QWORD *)&v98[0] = TargetHandle;
  v21 = 2;
  v22 = (HANDLE *)v98 + 1;
LABEL_63:
  v25 = GetCurrentProcess();
  if ( !DuplicateHandle(v25, hSourceHandle, v6, &v71, 0, 1, 2u) )
  {
    v26 = GetLastError();
    v9 = v26;
    if ( v26 > 0 )
      v9 = (unsigned __int16)v26 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v17 = 132;
    goto LABEL_33;
  }
  ExitCode = 0;
  *v22 = v71;
LABEL_73:
  lpBaseAddress = MapViewOfFile(hSourceHandle, 2u, 0, 0, 0);
  if ( !lpBaseAddress )
  {
    v61 = GetLastError();
    v9 = v61;
    if ( v61 > 0 )
      v9 = (unsigned __int16)v61 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v17 = 133;
LABEL_33:
    v18 = (unsigned int)v9;
    goto LABEL_34;
  }
  v27 = v63;
  if ( !v63 )
  {
    v28 = GetCurrentProcess();
    if ( DuplicateHandle(v28, v6, v6, &v69, 0x1FFFFFu, 1, 0) )
    {
      *((_QWORD *)v98 + v21++) = v69;
    }
    else
    {
      v29 = GetLastError();
      v30 = v29 < 0;
      if ( v29 > 0 )
      {
        v29 = (unsigned __int16)v29 | 0x80070000;
        v30 = v29 < 0;
      }
      if ( !v30 )
        v29 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
          (unsigned int)v29);
      v69 = 0;
    }
    v75 = OpenThread(0x1FFFFFu, 0, dwThreadId);
    if ( v75 == (HANDLE)-1LL || (char *)v75 + 1 == HANDLE_FLAG_INHERIT )
    {
      v34 = GetLastError();
      v35 = v34 < 0;
      if ( v34 > 0 )
      {
        v34 = (unsigned __int16)v34 | 0x80070000;
        v35 = v34 < 0;
      }
      if ( !v35 )
        v34 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          136,
          WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
          (unsigned int)v34);
    }
    else
    {
      v31 = GetCurrentProcess();
      if ( DuplicateHandle(v31, v75, v6, &v70, 0x1FFFFFu, 1, 0) )
      {
        *((_QWORD *)v98 + v21++) = v70;
      }
      else
      {
        v32 = GetLastError();
        v33 = v32 < 0;
        if ( v32 > 0 )
        {
          v32 = (unsigned __int16)v32 | 0x80070000;
          v33 = v32 < 0;
        }
        if ( !v33 )
          v32 = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            135,
            WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
            (unsigned int)v32);
        v70 = 0;
      }
    }
  }
  memset_0(v80, 0, 0xF8u);
  v80[0] = 248;
  v80[1] = v65;
  v80[2] = dwThreadId;
  v91 = -2147467259;
  v36 = 0;
  if ( v27 )
  {
    v92 = 0;
    v93 = 0;
  }
  else
  {
    v92 = v69;
    v93 = v70;
    v36 = TargetHandle;
  }
  v94 = v36;
  v95 = -1073741822;
  TickCount = GetTickCount();
  v96 |= 0x80000000;
  v81 = *((_OWORD *)v73 + 3);
  v82 = *((_OWORD *)v73 + 4);
  v83 = *((_OWORD *)v73 + 5);
  v84 = *((_OWORD *)v73 + 6);
  v85 = *((_OWORD *)v73 + 7);
  v86 = *((_OWORD *)v73 + 8);
  v87 = *((_OWORD *)v73 + 9);
  v88 = *((_OWORD *)v73 + 10);
  v89 = *((_OWORD *)v73 + 11);
  v90 = *((_QWORD *)v73 + 24);
  v37 = memcpySEH((void *)lpBaseAddress, v80, 0xF8u);
  v9 = v37;
  if ( v37 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v17 = 137;
    v18 = (unsigned int)v37;
LABEL_34:
    WPP_SF_d(v16[2], v17, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v18);
LABEL_35:
    v4 = v64;
    goto LABEL_36;
  }
  if ( v21 > 5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v39, v38, v40, v41);
  v42 = hSourceHandle;
  if ( !v63 )
    v42 = v71;
  v43 = v65;
  v44 = CWerService::TryCaptureSnapshot(v39, v65, v65, v42);
  if ( v44 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      138,
      WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      (unsigned int)v44);
  if ( v63 )
  {
    v45 = v64;
    v46 = hSourceHandle;
  }
  else
  {
    v45 = TargetHandle;
    v46 = v71;
  }
  v9 = CWerService::TryReportCrash(v78, v43, v43, v46, v45, v98, v21, ExitCode, 1, &hObject);
  if ( v9 < 0 )
    goto LABEL_35;
  v4 = v64;
  if ( (unsigned __int64)hObject + 1 <= 1 )
    goto LABEL_36;
  Handles[0] = hObject;
  Handles[1] = v64;
  v47 = (unsigned __int64)v64 + 1;
  v48 = WaitForMultipleObjects(((unsigned __int64)v64 + 1 > 1) + 1, Handles, 0, 0xFFFFFFFF);
  if ( v48 )
  {
    if ( v48 != 1 )
    {
      if ( v48 != -1 )
      {
        v9 = -2147467259;
        MicrosoftTelemetryAssertTriggeredNoArgs(v50, v49, v51, v52);
        goto LABEL_36;
      }
      v53 = GetLastError();
      v9 = v53;
      if ( v53 > 0 )
        v9 = (unsigned __int16)v53 | 0x80070000;
      if ( v9 >= 0 )
        v9 = -2147467259;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_36;
      v11 = 141;
      v12 = (unsigned int)v9;
      goto LABEL_16;
    }
    if ( v47 <= 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v50, v49, v51, v52);
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v55 = 140;
LABEL_142:
      WPP_SF_(v54[2], v55, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    }
  }
  else
  {
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v55 = 139;
      goto LABEL_142;
    }
  }
  v63 = 0;
  v56 = memcpySEH(&v63, (char *)lpBaseAddress + 176, 4u);
  v9 = v56;
  if ( v56 >= 0 )
  {
    if ( v63 == 1769472 )
    {
      *((_DWORD *)v73 + 11) = 65538;
    }
    else if ( v63 == -2145681404 )
    {
      v9 = -2145681404;
      ExitCode = 0;
      v57 = v65;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v65);
      v58 = WaitForSingleObject(v6, 0xEA60u);
      GetExitCodeProcess(v6, &ExitCode);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 2), ExitCode, v59, v57, v58, ExitCode);
    }
    else
    {
      ProcessId = GetProcessId(v6);
      WerpAddTerminationReason(ProcessId, 1, L"WerSvcKernelMsgDone");
      TerminateProcess(v6, *((_DWORD *)v73 + 12));
    }
    goto LABEL_36;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 142;
    v12 = (unsigned int)v56;
LABEL_16:
    WPP_SF_d(v10[2], v11, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v12);
  }
LABEL_36:
  v3 = hSourceHandle;
LABEL_37:
  if ( lpBaseAddress )
    UnmapViewOfFile(lpBaseAddress);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)v75 + 1 > 1 )
    CloseHandle(v75);
  if ( (unsigned __int64)(v6 + 1) > 1 )
    CloseHandle(v6);
  if ( (unsigned __int64)v4 + 1 > 1 )
    CloseHandle(v4);
  if ( (unsigned __int64)(v3 + 1) > 1 )
    CloseHandle(v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180016ac0  mov     [rsp-8+arg_10], rbx
0x180016ac5  push    rbp
0x180016ac6  push    rsi
0x180016ac7  push    rdi
0x180016ac8  push    r12
0x180016aca  push    r13
0x180016acc  push    r14
0x180016ace  push    r15
0x180016ad0  lea     rbp, [rsp-120h]
0x180016ad8  sub     rsp, 220h
0x180016adf  mov     rax, cs:__security_cookie
0x180016ae6  xor     rax, rsp
0x180016ae9  mov     [rbp+150h+var_40], rax
0x180016af0  mov     rdi, rdx
0x180016af3  mov     [rbp+150h+var_1B0], rdx
0x180016af7  mov     [rbp+150h+var_178], rcx
0x180016afb  xor     ecx, ecx
0x180016afd  mov     r15d, ecx
0x180016b00  mov     [rsp+250h+hSourceHandle], rcx
0x180016b05  mov     [rbp+150h+var_1C0], rcx
0x180016b09  mov     r12d, ecx
0x180016b0c  mov     [rsp+250h+var_1F0], rcx
0x180016b11  mov     [rsp+250h+TargetHandle], rcx
0x180016b16  mov     [rbp+150h+var_1D0], rcx
0x180016b1a  mov     [rbp+150h+var_1A0], rcx
0x180016b1e  mov     [rbp+150h+var_1C8], rcx
0x180016b22  mov     [rbp+150h+hObject], rcx
0x180016b26  mov     [rbp+150h+lpBaseAddress], rcx
0x180016b2a  mov     qword ptr [rbp+150h+EventAttributes.nLength], 18h
0x180016b32  mov     qword ptr [rbp+150h+EventAttributes.bInheritHandle], 1
0x180016b3a  xorps   xmm0, xmm0
0x180016b3d  movups  xmmword ptr [rbp+150h+Handles], xmm0
0x180016b41  xorps   xmm1, xmm1
0x180016b44  movups  [rbp+150h+var_60], xmm1
0x180016b4b  movups  [rbp+150h+var_50], xmm1
0x180016b52  mov     r14d, [rdx+8]
0x180016b56  mov     [rsp+250h+var_1E8], r14d
0x180016b5b  mov     eax, [rdx+10h]
0x180016b5e  mov     [rsp+250h+dwThreadId], eax
0x180016b62  mov     r13d, 80010001h
0x180016b68  mov     [rdx+2Ch], r13d
0x180016b6c  mov     [rbp+150h+EventAttributes.lpSecurityDescriptor], rcx
0x180016b70  mov     r8d, r14d; dwProcessId
0x180016b73  xor     edx, edx; bInheritHandle
0x180016b75  mov     ecx, 100441h; dwDesiredAccess
0x180016b7a  call    cs:__imp_OpenProcess
0x180016b80  mov     rsi, rax
0x180016b83  mov     [rbp+150h+var_198], rax
0x180016b87  inc     rax
0x180016b8a  cmp     rax, 1
0x180016b8e  ja      short loc_180016BB7
0x180016b90  call    cs:__imp_GetLastError
0x180016b96  cmp     eax, 5
0x180016b99  jnz     short loc_180016BB7
0x180016b9b  mov     r8d, r14d; dwProcessId
0x180016b9e  xor     edx, edx; bInheritHandle
0x180016ba0  mov     ecx, 101001h; dwDesiredAccess
0x180016ba5  call    cs:__imp_OpenProcess
0x180016bab  mov     rsi, rax
0x180016bae  mov     [rbp+150h+var_198], rax
0x180016bb2  mov     rbx, rax
0x180016bb5  jmp     short loc_180016BBA
0x180016bb7  mov     rbx, rsi
0x180016bba  lea     rax, [rbx+1]
0x180016bbe  cmp     rax, 1
0x180016bc2  ja      short loc_180016BE9
0x180016bc4  call    cs:__imp_GetLastError
0x180016bca  cmp     eax, 5
0x180016bcd  jnz     short loc_180016BE9
0x180016bcf  mov     r8d, r14d; dwProcessId
0x180016bd2  xor     edx, edx; bInheritHandle
0x180016bd4  mov     ecx, 1000h; dwDesiredAccess
0x180016bd9  call    cs:__imp_OpenProcess
0x180016bdf  mov     rsi, rax
0x180016be2  mov     [rbp+150h+var_198], rax
0x180016be6  mov     rbx, rax
0x180016be9  lea     rax, [rbx+1]
0x180016bed  cmp     rax, 1
0x180016bf1  ja      short loc_180016C52
0x180016bf3  call    cs:__imp_GetLastError
0x180016bf9  mov     ebx, eax
0x180016bfb  test    eax, eax
0x180016bfd  jle     short loc_180016C08
0x180016bff  movzx   ebx, ax
0x180016c02  or      ebx, 80070000h
0x180016c08  mov     r15d, 80004005h
0x180016c0e  test    ebx, ebx
0x180016c10  cmovns  ebx, r15d
0x180016c14  lea     rdi, WPP_GLOBAL_Control
0x180016c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c22  cmp     rcx, rdi
0x180016c25  jz      loc_180016D83
0x180016c2b  test    byte ptr [rcx+1Ch], 1
0x180016c2f  jz      loc_180016D83
0x180016c35  mov     edx, 80h
0x180016c3a  mov     r9d, ebx
0x180016c3d  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180016c44  mov     rcx, [rcx+10h]
0x180016c48  call    WPP_SF_d
0x180016c4d  jmp     loc_180016D83
0x180016c52  mov     [rsp+250h+var_1F8], 0
0x180016c5a  xor     r8d, r8d; enum _PS_PROTECTED_SIGNER *
0x180016c5d  lea     rdx, [rsp+250h+var_1F8]; enum _PS_PROTECTED_TYPE *
0x180016c62  mov     rcx, rsi; void *
0x180016c65  call    ?UtilGetProtectedProcessInfo@@YAJPEAXPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z; UtilGetProtectedProcessInfo(void *,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)
0x180016c6a  xor     eax, eax
0x180016c6c  cmp     [rsp+250h+var_1F8], eax
0x180016c70  setnle  al
0x180016c73  mov     [rsp+250h+var_1F8], eax
0x180016c77  test    byte ptr [rdi+108h], 4
0x180016c7e  jz      short loc_180016C8B
0x180016c80  mov     [rdi+2Ch], r13d
0x180016c84  xor     ebx, ebx
0x180016c86  jmp     loc_180016D88
0x180016c8b  xor     r9d, r9d; lpName
0x180016c8e  xor     r8d, r8d; bInitialState
0x180016c91  lea     edx, [r9+1]; bManualReset
0x180016c95  lea     rcx, [rbp+150h+EventAttributes]; lpEventAttributes
0x180016c99  call    cs:__imp_CreateEventW
0x180016c9f  mov     rbx, rax
0x180016ca2  mov     [rsp+250h+var_1F0], rax
0x180016ca7  lea     r12, [rax+1]
0x180016cab  mov     r13d, 80070000h
0x180016cb1  lea     r14, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180016cb8  lea     rdi, WPP_GLOBAL_Control
0x180016cbf  cmp     r12, 1
0x180016cc3  ja      short loc_180016D02
0x180016cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ccc  cmp     rcx, rdi
0x180016ccf  jz      short loc_180016D02
0x180016cd1  test    byte ptr [rcx+1Ch], 2
0x180016cd5  jz      short loc_180016D02
0x180016cd7  call    cs:__imp_GetLastError
0x180016cdd  test    eax, eax
0x180016cdf  jle     short loc_180016CE7
0x180016ce1  movzx   eax, ax
0x180016ce4  or      eax, r13d
0x180016ce7  mov     edx, 81h
0x180016cec  mov     r9d, eax
0x180016cef  mov     r8, r14
0x180016cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cf9  mov     rcx, [rcx+10h]
0x180016cfd  call    WPP_SF_d
0x180016d02  mov     [rsp+250h+lpName], 0; lpName
0x180016d0b  mov     [rsp+250h+dwMaximumSizeLow], 0F8h; dwMaximumSizeLow
0x180016d13  xor     r9d, r9d; dwMaximumSizeHigh
0x180016d16  lea     r8d, [r9+4]; flProtect
0x180016d1a  lea     rdx, [rbp+150h+EventAttributes]; lpFileMappingAttributes
0x180016d1e  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180016d22  call    cs:__imp_CreateFileMappingW
0x180016d28  mov     [rsp+250h+hSourceHandle], rax
0x180016d2d  inc     rax
0x180016d30  cmp     rax, 1
0x180016d34  ja      loc_180016E2D
0x180016d3a  call    cs:__imp_GetLastError
0x180016d40  mov     ebx, eax
0x180016d42  test    eax, eax
0x180016d44  jle     short loc_180016D4C
0x180016d46  movzx   ebx, ax
0x180016d49  or      ebx, r13d
0x180016d4c  mov     r15d, 80004005h
0x180016d52  test    ebx, ebx
0x180016d54  cmovns  ebx, r15d
0x180016d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d5f  cmp     rcx, rdi
0x180016d62  jz      short loc_180016D7E
0x180016d64  test    byte ptr [rcx+1Ch], 1
0x180016d68  jz      short loc_180016D7E
0x180016d6a  mov     edx, 82h
0x180016d6f  mov     r9d, ebx
0x180016d72  mov     r8, r14
0x180016d75  mov     rcx, [rcx+10h]
0x180016d79  call    WPP_SF_d
0x180016d7e  mov     r12, [rsp+250h+var_1F0]
0x180016d83  mov     r15, [rsp+250h+hSourceHandle]
0x180016d88  mov     rax, [rbp+150h+lpBaseAddress]
0x180016d8c  test    rax, rax
0x180016d8f  jz      short loc_180016D9B
0x180016d91  mov     rcx, rax; lpBaseAddress
0x180016d94  call    cs:__imp_UnmapViewOfFile
0x180016d9a  nop
0x180016d9b  mov     rcx, [rbp+150h+hObject]; hObject
0x180016d9f  lea     rax, [rcx+1]
0x180016da3  cmp     rax, 1
0x180016da7  jbe     short loc_180016DB0
0x180016da9  call    cs:__imp_CloseHandle
0x180016daf  nop
0x180016db0  mov     rcx, [rbp+150h+var_1A0]; hObject
0x180016db4  lea     rax, [rcx+1]
0x180016db8  cmp     rax, 1
0x180016dbc  jbe     short loc_180016DC5
0x180016dbe  call    cs:__imp_CloseHandle
0x180016dc4  nop
0x180016dc5  lea     rax, [rsi+1]
0x180016dc9  cmp     rax, 1
0x180016dcd  jbe     short loc_180016DD9
0x180016dcf  mov     rcx, rsi; hObject
0x180016dd2  call    cs:__imp_CloseHandle
0x180016dd8  nop
0x180016dd9  lea     rax, [r12+1]
0x180016dde  cmp     rax, 1
0x180016de2  jbe     short loc_180016DEE
0x180016de4  mov     rcx, r12; hObject
0x180016de7  call    cs:__imp_CloseHandle
0x180016ded  nop
0x180016dee  lea     rax, [r15+1]
0x180016df2  cmp     rax, 1
0x180016df6  jbe     short loc_180016E01
0x180016df8  mov     rcx, r15; hObject
0x180016dfb  call    cs:__imp_CloseHandle
0x180016e01  mov     eax, ebx
0x180016e03  mov     rcx, [rbp+150h+var_40]
0x180016e0a  xor     rcx, rsp; StackCookie
0x180016e0d  call    __security_check_cookie
0x180016e12  mov     rbx, [rsp+250h+arg_10]
0x180016e1a  add     rsp, 220h
0x180016e21  pop     r15
0x180016e23  pop     r14
0x180016e25  pop     r13
0x180016e27  pop     r12
0x180016e29  pop     rdi
0x180016e2a  pop     rsi
0x180016e2b  pop     rbp
0x180016e2c  retn
0x180016e2d  mov     r15d, 80004005h
0x180016e33  cmp     [rsp+250h+var_1F8], 0
0x180016e38  jnz     loc_180016F79
0x180016e3e  cmp     r12, 1
0x180016e42  jbe     loc_180016EE8
0x180016e48  call    cs:__imp_GetCurrentProcess
0x180016e4e  mov     [rsp+250h+dwOptions], 2; dwOptions
0x180016e56  mov     dword ptr [rsp+250h+lpName], 1; bInheritHandle
0x180016e5e  xor     r12d, r12d
0x180016e61  mov     [rsp+250h+dwMaximumSizeLow], r12d; dwDesiredAccess
0x180016e66  lea     r9, [rsp+250h+TargetHandle]; lpTargetHandle
0x180016e6b  mov     r8, rsi; hTargetProcessHandle
0x180016e6e  mov     rdx, rbx; hSourceHandle
0x180016e71  mov     rcx, rax; hSourceProcessHandle
0x180016e74  call    cs:__imp_DuplicateHandle
0x180016e7a  test    eax, eax
0x180016e7c  jz      short loc_180016E99
0x180016e7e  mov     rax, [rsp+250h+TargetHandle]
0x180016e83  mov     qword ptr [rbp+150h+var_60], rax
0x180016e8a  mov     r12d, 2
0x180016e90  lea     rbx, [rbp+150h+var_60+8]
0x180016e97  jmp     short loc_180016EF5
0x180016e99  call    cs:__imp_GetLastError
0x180016e9f  test    eax, eax
0x180016ea1  jle     short loc_180016EAB
0x180016ea3  movzx   eax, ax
0x180016ea6  or      eax, r13d
0x180016ea9  test    eax, eax
0x180016eab  cmovns  eax, r15d
0x180016eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016eb6  cmp     rcx, rdi
0x180016eb9  jz      short loc_180016ED5
0x180016ebb  test    byte ptr [rcx+1Ch], 2
0x180016ebf  jz      short loc_180016ED5
0x180016ec1  mov     edx, 83h
0x180016ec6  mov     r9d, eax
0x180016ec9  mov     r8, r14
0x180016ecc  mov     rcx, [rcx+10h]
0x180016ed0  call    WPP_SF_d
0x180016ed5  mov     [rsp+250h+var_1F0], r12
0x180016eda  mov     rcx, rbx; hObject
0x180016edd  call    cs:__imp_CloseHandle
0x180016ee3  mov     [rsp+250h+TargetHandle], r12
0x180016ee8  lea     rbx, [rbp+150h+var_60]
0x180016eef  mov     r12d, 1
0x180016ef5  call    cs:__imp_GetCurrentProcess
0x180016efb  mov     [rsp+250h+dwOptions], 2; dwOptions
0x180016f03  mov     dword ptr [rsp+250h+lpName], 1; bInheritHandle
0x180016f0b  mov     [rsp+250h+dwMaximumSizeLow], 0; dwDesiredAccess
0x180016f13  lea     r9, [rbp+150h+var_1C0]; lpTargetHandle
0x180016f17  mov     r8, rsi; hTargetProcessHandle
0x180016f1a  mov     rdx, [rsp+250h+hSourceHandle]; hSourceHandle
0x180016f1f  mov     rcx, rax; hSourceProcessHandle
0x180016f22  call    cs:__imp_DuplicateHandle
0x180016f28  test    eax, eax
0x180016f2a  jnz     short loc_180016F68
0x180016f2c  call    cs:__imp_GetLastError
0x180016f32  mov     ebx, eax
0x180016f34  test    eax, eax
0x180016f36  jle     short loc_180016F3E
0x180016f38  movzx   ebx, ax
0x180016f3b  or      ebx, r13d
0x180016f3e  test    ebx, ebx
0x180016f40  cmovns  ebx, r15d
0x180016f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f4b  cmp     rcx, rdi
0x180016f4e  jz      loc_180016D7E
0x180016f54  test    byte ptr [rcx+1Ch], 1
0x180016f58  jz      loc_180016D7E
0x180016f5e  mov     edx, 84h
0x180016f63  jmp     loc_180016D6F
0x180016f68  mov     [rsp+250h+ExitCode], 0
0x180016f70  mov     rax, [rbp+150h+var_1C0]
0x180016f74  mov     [rbx], rax
0x180016f77  jmp     short loc_180016F84
0x180016f79  xor     r12d, r12d
  ... truncated ...
```
