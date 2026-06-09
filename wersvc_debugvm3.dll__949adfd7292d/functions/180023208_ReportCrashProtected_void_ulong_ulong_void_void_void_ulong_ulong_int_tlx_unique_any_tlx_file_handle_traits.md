# ReportCrashProtected(void *,ulong,ulong,void *,void *,void * *,ulong,ulong,int,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180023208`
- end: `0x180023d06`
- name: `?ReportCrashProtected@@YAJPEAXKK00PEAPEAXKKHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `2814`
- prototype: `__int64 __usercall@<rax>(HANDLE Process@<rcx>, __int64, __int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180022d54`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180002a24`
- `0x1800035e8`
- `0x180006134`
- `0x180006a80`
- `0x18000ce58`
- `0x180011ef8`
- `0x180011f38`
- `0x180013df4`
- `0x180023208`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800232d9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800232d9`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18002368d`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18002372e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18002368d`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18002372e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002357c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002357c`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180023a8d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180023a8d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180023889`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180023889`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800237ae`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800237ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002338e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002338e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023452`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023452`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002330c`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002330c`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1800233a2`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1800233a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800232fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023823`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800232fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023823`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cd4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180023c97`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180023c97`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800234b5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800234b5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180023486`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180023486`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180023427`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180023427`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180023931`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180023931`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ReportCrashProtected(
        HANDLE Process,
        DWORD a2,
        DWORD a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7,
        int a8,
        int a9,
        void **a10)
{
  char *v13; // rbx
  char *v14; // rdi
  unsigned int *v15; // r14
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  void *v24; // rcx
  signed int LastError; // eax
  bool v26; // sf
  UINT SystemWow64Directory2W; // eax
  unsigned __int64 v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  signed int v30; // esi
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  DWORD CurrentProcessId; // eax
  unsigned int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  char *v38; // r12
  __int64 v39; // rsi
  __int64 v40; // rsi
  signed int v41; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v42; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v43; // r15
  signed int v44; // eax
  _QWORD *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r9
  signed int v48; // eax
  _QWORD *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r9
  signed int v52; // eax
  DWORD v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
  signed int v58; // eax
  __int64 v59; // r9
  void *v60; // rcx
  signed int v61; // eax
  signed int v62; // eax
  signed int v63; // eax
  signed int v64; // eax
  signed int v65; // eax
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpName; // [rsp+28h] [rbp-D8h]
  char *v69; // [rsp+58h] [rbp-A8h]
  __int16 v70[2]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwProcessId; // [rsp+64h] [rbp-9Ch]
  struct _PROCESS_INFORMATION hObject; // [rsp+68h] [rbp-98h] BYREF
  DWORD v73; // [rsp+80h] [rbp-80h]
  ULONG_PTR Size; // [rsp+88h] [rbp-78h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+90h] [rbp-70h] BYREF
  char *v76; // [rsp+A8h] [rbp-58h]
  char *v77; // [rsp+B0h] [rbp-50h]
  unsigned int *v78; // [rsp+B8h] [rbp-48h]
  char *v79; // [rsp+C0h] [rbp-40h]
  char *v80; // [rsp+C8h] [rbp-38h]
  __int64 v81; // [rsp+D0h] [rbp-30h]
  void **v82; // [rsp+D8h] [rbp-28h]
  HANDLE Handles[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+F0h] [rbp-10h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v85; // [rsp+158h] [rbp+58h]
  _OWORD v86[5]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v87; // [rsp+1B0h] [rbp+B0h]
  __int128 Value; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v89; // [rsp+1D0h] [rbp+D0h]
  __int128 v90; // [rsp+1E0h] [rbp+E0h]
  WCHAR Buffer[264]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR CommandLine[264]; // [rsp+400h] [rbp+300h] BYREF

  v81 = a4;
  v73 = a3;
  dwProcessId = a2;
  v82 = a10;
  v70[0] = 0;
  v13 = 0;
  v76 = 0;
  v69 = 0;
  v14 = 0;
  v77 = 0;
  v15 = 0;
  v78 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  Size = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  memset(&hObject, 0, sizeof(hObject));
  Value = 0;
  v89 = 0;
  v90 = 0;
  *(_OWORD *)Handles = 0;
  if ( a7 > 5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16, v18, v19);
  if ( a3 != GetProcessId(Process) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v21, v20, v22, v23);
  v24 = *a10;
  *a10 = 0;
  if ( (unsigned __int64)v24 + 1 > 1 )
    CloseHandle(v24);
  if ( !(unsigned int)IsWow64Process2(Process, v70, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    v26 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v26 = LastError < 0;
    }
    if ( !v26 )
      LastError = -2147467259;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      84,
      WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
      (unsigned int)LastError);
  }
  if ( v70[0] == 332 || v70[0] == 452 )
    SystemWow64Directory2W = GetSystemWow64Directory2W(Buffer, 260);
  else
    SystemWow64Directory2W = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemWow64Directory2W - 1 > 0x102 || !Buffer[0] )
  {
    v65 = GetLastError();
    v30 = v65;
    if ( v65 > 0 )
      v30 = (unsigned __int16)v65 | 0x80070000;
    if ( v30 >= 0 )
      v30 = -2147467259;
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_158;
    v32 = 85;
    goto LABEL_157;
  }
  v30 = StringCchCatW(Buffer, v28, L"\\WerFaultSecure.exe");
  if ( v30 < 0 )
  {
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_158;
    v32 = 86;
LABEL_157:
    WPP_SF_d(v31[2], v32, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)v30);
LABEL_158:
    v38 = v69;
LABEL_159:
    v43 = 0;
    goto LABEL_160;
  }
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 1;
  v13 = (char *)OpenProcess(0x1000u, 1, dwProcessId);
  v79 = v13;
  v76 = v13;
  if ( v13 == (char *)-1LL || v13 + 1 == (char *)1 )
  {
    v64 = GetLastError();
    v30 = v64;
    if ( v64 > 0 )
      v30 = (unsigned __int16)v64 | 0x80070000;
    if ( v30 >= 0 )
      v30 = -2147467259;
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_158;
    v32 = 87;
    goto LABEL_157;
  }
  v69 = (char *)CreateEventW(&EventAttributes, 1, 0, 0);
  if ( v69 == (char *)-1LL || v69 + 1 == (char *)1 )
  {
    v63 = GetLastError();
    v30 = v63;
    if ( v63 > 0 )
      v30 = (unsigned __int16)v63 | 0x80070000;
    if ( v30 >= 0 )
      v30 = -2147467259;
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_158;
    v32 = 88;
    goto LABEL_157;
  }
  v14 = (char *)CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &EventAttributes, 4u, 0, 0x58u, 0);
  v80 = v14;
  v77 = v14;
  if ( v14 == (char *)-1LL || v14 + 1 == (char *)1 )
  {
    v62 = GetLastError();
    v30 = v62;
    if ( v62 > 0 )
      v30 = (unsigned __int16)v62 | 0x80070000;
    if ( v30 >= 0 )
      v30 = -2147467259;
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_158;
    v32 = 89;
    goto LABEL_157;
  }
  v15 = (unsigned int *)MapViewOfFile(v14, 2u, 0, 0, 0);
  v78 = v15;
  if ( !v15 )
  {
    v61 = GetLastError();
    v30 = v61;
    if ( v61 > 0 )
      v30 = (unsigned __int16)v61 | 0x80070000;
    if ( v30 >= 0 )
      v30 = -2147467259;
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_158;
    v32 = 90;
    goto LABEL_157;
  }
  memset_0(v86, 0, 0x58u);
  *(_OWORD *)v15 = v86[0];
  *((_OWORD *)v15 + 1) = v86[1];
  *((_OWORD *)v15 + 2) = v86[2];
  *((_OWORD *)v15 + 3) = v86[3];
  *((_OWORD *)v15 + 4) = v86[4];
  *((_QWORD *)v15 + 10) = v87;
  *v15 = a3;
  *((_QWORD *)v15 + 1) = v69;
  *((_QWORD *)v15 + 2) = a4;
  *((_QWORD *)v15 + 3) = a5;
  v15[1] = a8;
  CurrentProcessId = 0;
  v34 = 0;
  if ( a6 )
  {
    while ( v34 < a7 )
    {
      *(_QWORD *)&v15[2 * v34 + 8] = *(_QWORD *)(a6 + 8LL * v34);
      ++v34;
    }
    CurrentProcessId = 0;
  }
  v15[18] = -2147467259;
  if ( a9 )
    CurrentProcessId = GetCurrentProcessId();
  LODWORD(lpName) = dwProcessId;
  dwMaximumSizeLow[0] = v73;
  v30 = StringCchPrintfW(
          CommandLine,
          0x104u,
          L"\"%s\" -protectedcrash -p %u -i %u -h %u -j %u -s %u -d %u",
          Buffer,
          *(_QWORD *)dwMaximumSizeLow,
          lpName,
          (_DWORD)Process,
          (_DWORD)v13,
          (_DWORD)v14,
          CurrentProcessId);
  v29 = 0;
  if ( v30 < 0 )
  {
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_158;
    v32 = 91;
    goto LABEL_157;
  }
  StartupInfo.cb = 112;
  StartupInfo.lpDesktop = (LPWSTR)&dword_180039414;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = 0;
  *(_QWORD *)&Value = Process;
  *((_QWORD *)&Value + 1) = __PAIR64__(HIDWORD(v79), (unsigned int)v13);
  *(_QWORD *)&v89 = __PAIR64__(HIDWORD(v80), (unsigned int)v14);
  v38 = v69;
  *((_QWORD *)&v89 + 1) = v69;
  v39 = 4;
  if ( (a8 & 1) != 0 )
  {
    v40 = v81;
    if ( !v81 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v35, 0, v36, v37);
    *(_QWORD *)&v90 = v40;
    v39 = 5;
    if ( a5 )
    {
      *((_QWORD *)&v90 + 1) = a5;
      v39 = 6;
    }
  }
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && GetLastError() != 122 )
  {
    v41 = GetLastError();
    v30 = v41;
    if ( v41 > 0 )
      v30 = (unsigned __int16)v41 | 0x80070000;
    if ( v30 >= 0 )
      v30 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
        (unsigned int)v30);
    goto LABEL_159;
  }
  v42 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)operator new[](Size, (const struct std::nothrow_t *)&std::nothrow);
  v43 = v42;
  if ( v42 )
  {
    if ( !InitializeProcThreadAttributeList(v42, 1u, 0, &Size) )
    {
      v44 = GetLastError();
      v30 = v44;
      if ( v44 > 0 )
        v30 = (unsigned __int16)v44 | 0x80070000;
      if ( v30 >= 0 )
        v30 = -2147467259;
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v46 = 94;
        v47 = (unsigned int)v30;
LABEL_121:
        WPP_SF_d(v45[2], v46, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, v47);
        goto LABEL_160;
      }
      goto LABEL_160;
    }
    if ( UpdateProcThreadAttribute(v43, 0, 0x20002u, &Value, 8 * v39, 0, 0) )
    {
      v85 = v43;
      if ( hObject.hProcess )
        CloseHandle(hObject.hProcess);
      if ( hObject.hThread )
        CloseHandle(hObject.hThread);
      memset(&hObject, 0, sizeof(hObject));
      if ( CreateProcessW(Buffer, CommandLine, 0, 0, 1, 0xC0400u, 0, 0, &StartupInfo, &hObject) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids);
        Handles[0] = v69;
        Handles[1] = hObject.hProcess;
        v53 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
        if ( !v53 )
        {
          v59 = v15[18];
          if ( (int)v59 >= 0 )
          {
            if ( *((_QWORD *)v15 + 10) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids);
              v60 = *v82;
              *v82 = (void *)*((_QWORD *)v15 + 10);
              if ( (unsigned __int64)v60 + 1 > 1 )
                CloseHandle(v60);
              v30 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids);
              v30 = -2147024890;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, v59);
            v30 = v15[18];
          }
          goto LABEL_117;
        }
        if ( v53 == 1 )
        {
          v30 = -2147023829;
          v49 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_117;
          v50 = 101;
          v51 = 2147943467LL;
          goto LABEL_71;
        }
        if ( v53 != -1 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v55, v54, v56, v57);
          v30 = -2147418113;
          goto LABEL_117;
        }
        v58 = GetLastError();
        v30 = v58;
        if ( v58 > 0 )
          v30 = (unsigned __int16)v58 | 0x80070000;
        if ( v30 >= 0 )
          v30 = -2147467259;
        v49 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_117;
        v50 = 102;
      }
      else
      {
        v52 = GetLastError();
        v30 = v52;
        if ( v52 > 0 )
          v30 = (unsigned __int16)v52 | 0x80070000;
        if ( v30 >= 0 )
          v30 = -2147467259;
        v49 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_117;
        v50 = 96;
      }
    }
    else
    {
      v48 = GetLastError();
      v30 = v48;
      if ( v48 > 0 )
        v30 = (unsigned __int16)v48 | 0x80070000;
      if ( v30 >= 0 )
        v30 = -2147467259;
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_117;
      v50 = 95;
    }
    v51 = (unsigned int)v30;
LABEL_71:
    WPP_SF_d(v49[2], v50, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, v51);
LABEL_117:
    DeleteProcThreadAttributeList(v43);
    goto LABEL_160;
  }
  v30 = -2147024882;
  v45 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v46 = 93;
    v47 = 2147942414LL;
    goto LABEL_121;
  }
LABEL_160:
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( v43 )
    operator delete(v43, v29);
  if ( v15 )
    UnmapViewOfFile(v15);
  if ( (unsigned __int64)(v14 + 1) > 1 )
    CloseHandle(v14);
  if ( (unsigned __int64)(v38 + 1) > 1 )
    CloseHandle(v38);
  if ( (unsigned __int64)(v13 + 1) > 1 )
    CloseHandle(v13);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x180023208  mov     [rsp-8+arg_18], rbx
0x18002320d  push    rbp
0x18002320e  push    rsi
0x18002320f  push    rdi
0x180023210  push    r12
0x180023212  push    r13
0x180023214  push    r14
0x180023216  push    r15
0x180023218  lea     rbp, [rsp-520h]
0x180023220  sub     rsp, 620h
0x180023227  mov     rax, cs:__security_cookie
0x18002322e  xor     rax, rsp
0x180023231  mov     [rbp+550h+var_40], rax
0x180023238  mov     r13, r9
0x18002323b  mov     [rbp+550h+var_580], r9
0x18002323f  mov     r15d, r8d
0x180023242  mov     [rbp+550h+var_5D0], r8d
0x180023246  mov     [rsp+650h+dwProcessId], edx
0x18002324a  mov     r12, rcx
0x18002324d  mov     rsi, [rbp+550h+arg_48]
0x180023254  mov     [rbp+550h+var_578], rsi
0x180023258  xor     ecx, ecx
0x18002325a  mov     [rsp+650h+var_5F0], cx
0x18002325f  mov     ebx, ecx
0x180023261  mov     [rbp+550h+var_5A8], rcx
0x180023265  mov     [rsp+650h+var_5F8], rcx
0x18002326a  mov     edi, ecx
0x18002326c  mov     [rbp+550h+var_5A0], rcx
0x180023270  mov     r14d, ecx
0x180023273  mov     [rbp+550h+var_598], rcx
0x180023277  xorps   xmm0, xmm0
0x18002327a  xor     eax, eax
0x18002327c  movups  xmmword ptr [rbp+550h+EventAttributes.nLength], xmm0
0x180023280  mov     qword ptr [rbp+550h+EventAttributes.bInheritHandle], rax
0x180023284  mov     [rbp+550h+Size], rcx
0x180023288  mov     [rsp+650h+var_600], rcx
0x18002328d  mov     qword ptr [rbp+550h+StartupInfo.cb], rcx
0x180023291  xor     edx, edx; Val
0x180023293  lea     r8d, [rcx+68h]; Size
0x180023297  lea     rcx, [rbp+550h+StartupInfo.lpReserved]; void *
0x18002329b  call    memset_0
0x1800232a0  xorps   xmm0, xmm0
0x1800232a3  xor     eax, eax
0x1800232a5  movups  xmmword ptr [rsp+650h+hObject], xmm0
0x1800232aa  mov     [rsp+650h+var_5D8], rax
0x1800232af  movups  [rbp+550h+Value], xmm0
0x1800232b6  movups  [rbp+550h+var_480], xmm0
0x1800232bd  movups  [rbp+550h+var_470], xmm0
0x1800232c4  movups  xmmword ptr [rbp+550h+Handles], xmm0
0x1800232c8  cmp     [rbp+550h+arg_30], 5
0x1800232cf  jbe     short loc_1800232D6
0x1800232d1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800232d6  mov     rcx, r12; Process
0x1800232d9  call    cs:__imp_GetProcessId
0x1800232df  cmp     r15d, eax
0x1800232e2  jz      short loc_1800232E9
0x1800232e4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800232e9  mov     rcx, [rsi]; hObject
0x1800232ec  xor     edx, edx
0x1800232ee  mov     [rsi], rdx
0x1800232f1  lea     rax, [rcx+1]
0x1800232f5  cmp     rax, 1
0x1800232f9  jbe     short loc_180023301
0x1800232fb  call    cs:__imp_CloseHandle
0x180023301  xor     r8d, r8d
0x180023304  lea     rdx, [rsp+650h+var_5F0]
0x180023309  mov     rcx, r12
0x18002330c  call    cs:__imp_IsWow64Process2
0x180023312  lea     rcx, WPP_GLOBAL_Control
0x180023319  xor     esi, esi
0x18002331b  test    eax, eax
0x18002331d  jnz     short loc_18002336C
0x18002331f  mov     rax, cs:WPP_GLOBAL_Control
0x180023326  cmp     rax, rcx
0x180023329  jz      short loc_18002336C
0x18002332b  test    byte ptr [rax+1Ch], 2
0x18002332f  jz      short loc_18002336C
0x180023331  call    cs:__imp_GetLastError
0x180023337  test    eax, eax
0x180023339  jle     short loc_180023345
0x18002333b  movzx   eax, ax
0x18002333e  or      eax, 80070000h
0x180023343  test    eax, eax
0x180023345  mov     ecx, 80004005h
0x18002334a  cmovns  eax, ecx
0x18002334d  mov     edx, 54h ; 'T'
0x180023352  mov     r9d, eax
0x180023355  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18002335c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023363  mov     rcx, [rcx+10h]
0x180023367  call    WPP_SF_d
0x18002336c  movzx   r8d, [rsp+650h+var_5F0]
0x180023372  mov     ecx, r8d
0x180023375  sub     ecx, 14Ch
0x18002337b  jz      short loc_180023396
0x18002337d  cmp     ecx, 78h ; 'x'
0x180023380  jz      short loc_180023396
0x180023382  mov     edx, 104h; uSize
0x180023387  lea     rcx, [rbp+550h+Buffer]; lpBuffer
0x18002338e  call    cs:__imp_GetSystemDirectoryW
0x180023394  jmp     short loc_1800233A8
0x180023396  mov     edx, 104h
0x18002339b  lea     rcx, [rbp+550h+Buffer]
0x1800233a2  call    cs:__imp_GetSystemWow64Directory2W
0x1800233a8  dec     eax
0x1800233aa  cmp     eax, 102h
0x1800233af  ja      loc_180023BF8
0x1800233b5  cmp     [rbp+550h+Buffer], si
0x1800233bc  jz      loc_180023BF8
0x1800233c2  lea     r8, aWerfaultsecure; "\\WerFaultSecure.exe"
0x1800233c9  lea     rcx, [rbp+550h+Buffer]; wchar_t *
0x1800233d0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800233d5  mov     esi, eax
0x1800233d7  test    eax, eax
0x1800233d9  jns     short loc_180023406
0x1800233db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233e2  lea     rax, WPP_GLOBAL_Control
0x1800233e9  cmp     rcx, rax
0x1800233ec  jz      loc_180023C48
0x1800233f2  test    byte ptr [rcx+1Ch], 1
0x1800233f6  jz      loc_180023C48
0x1800233fc  mov     edx, 56h ; 'V'
0x180023401  jmp     loc_180023C35
0x180023406  mov     [rbp+550h+EventAttributes.nLength], 18h
0x18002340d  xor     esi, esi
0x18002340f  mov     [rbp+550h+EventAttributes.lpSecurityDescriptor], rsi
0x180023413  mov     [rbp+550h+EventAttributes.bInheritHandle], 1
0x18002341a  mov     r8d, [rsp+650h+dwProcessId]; dwProcessId
0x18002341f  lea     edx, [rsi+1]; bInheritHandle
0x180023422  mov     ecx, 1000h; dwDesiredAccess
0x180023427  call    cs:__imp_OpenProcess
0x18002342d  mov     rbx, rax
0x180023430  mov     [rbp+550h+var_590], rax
0x180023434  mov     [rbp+550h+var_5A8], rax
0x180023438  inc     rax
0x18002343b  cmp     rax, 1
0x18002343f  jbe     loc_180023BB9
0x180023445  xor     r9d, r9d; lpName
0x180023448  xor     r8d, r8d; bInitialState
0x18002344b  lea     edx, [rsi+1]; bManualReset
0x18002344e  lea     rcx, [rbp+550h+EventAttributes]; lpEventAttributes
0x180023452  call    cs:__imp_CreateEventW
0x180023458  mov     [rsp+650h+var_5F8], rax
0x18002345d  inc     rax
0x180023460  cmp     rax, 1
0x180023464  jbe     loc_180023B72
0x18002346a  mov     [rsp+650h+lpName], rsi; lpName
0x18002346f  mov     [rsp+650h+dwMaximumSizeLow], 58h ; 'X'; dwMaximumSizeLow
0x180023477  xor     r9d, r9d; dwMaximumSizeHigh
0x18002347a  lea     r8d, [rsi+4]; flProtect
0x18002347e  lea     rdx, [rbp+550h+EventAttributes]; lpFileMappingAttributes
0x180023482  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180023486  call    cs:__imp_CreateFileMappingW
0x18002348c  mov     rdi, rax
0x18002348f  mov     [rbp+550h+var_588], rax
0x180023493  mov     [rbp+550h+var_5A0], rax
0x180023497  inc     rax
0x18002349a  cmp     rax, 1
0x18002349e  jbe     loc_180023B28
0x1800234a4  mov     qword ptr [rsp+650h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x1800234a9  xor     r9d, r9d; dwFileOffsetLow
0x1800234ac  xor     r8d, r8d; dwFileOffsetHigh
0x1800234af  lea     edx, [rsi+2]; dwDesiredAccess
0x1800234b2  mov     rcx, rdi; hFileMappingObject
0x1800234b5  call    cs:__imp_MapViewOfFile
0x1800234bb  mov     r14, rax
0x1800234be  mov     [rbp+550h+var_598], rax
0x1800234c2  test    rax, rax
0x1800234c5  jz      loc_180023ADE
0x1800234cb  mov     rsi, [rbp+550h+arg_28]
0x1800234d2  xor     edx, edx; Val
0x1800234d4  lea     r8d, [rdx+58h]; Size
0x1800234d8  lea     rcx, [rbp+550h+var_4F0]; void *
0x1800234dc  call    memset_0
0x1800234e1  movaps  xmm0, [rbp+550h+var_4F0]
0x1800234e5  movups  xmmword ptr [r14], xmm0
0x1800234e9  movaps  xmm1, [rbp+550h+var_4E0]
0x1800234ed  movups  xmmword ptr [r14+10h], xmm1
0x1800234f2  movaps  xmm0, [rbp+550h+var_4D0]
0x1800234f9  movups  xmmword ptr [r14+20h], xmm0
0x1800234fe  movaps  xmm1, [rbp+550h+var_4C0]
0x180023505  movups  xmmword ptr [r14+30h], xmm1
0x18002350a  movaps  xmm0, [rbp+550h+var_4B0]
0x180023511  movups  xmmword ptr [r14+40h], xmm0
0x180023516  movsd   xmm1, [rbp+550h+var_4A0]
0x18002351e  movsd   qword ptr [r14+50h], xmm1
0x180023524  mov     [r14], r15d
0x180023527  mov     rax, [rsp+650h+var_5F8]
0x18002352c  mov     [r14+8], rax
0x180023530  mov     [r14+10h], r13
0x180023534  mov     r15, [rbp+550h+arg_20]
0x18002353b  mov     [r14+18h], r15
0x18002353f  mov     r13d, [rbp+550h+arg_38]
0x180023546  mov     [r14+4], r13d
0x18002354a  xor     eax, eax
0x18002354c  mov     edx, eax
0x18002354e  test    rsi, rsi
0x180023551  jz      short loc_18002356C
0x180023553  cmp     edx, [rbp+550h+arg_30]
0x180023559  jnb     short loc_18002356A
0x18002355b  mov     ecx, edx
0x18002355d  mov     rax, [rsi+rcx*8]
0x180023561  mov     [r14+rcx*8+20h], rax
0x180023566  inc     edx
0x180023568  jmp     short loc_180023553
0x18002356a  xor     eax, eax
0x18002356c  mov     dword ptr [r14+48h], 80004005h
0x180023574  cmp     [rbp+550h+arg_40], eax
0x18002357a  jz      short loc_180023582
0x18002357c  call    cs:__imp_GetCurrentProcessId
0x180023582  mov     dword ptr [rsp+650h+lpProcessInformation], eax
0x180023586  mov     dword ptr [rsp+650h+lpStartupInfo], edi
0x18002358a  mov     dword ptr [rsp+650h+lpCurrentDirectory], ebx
0x18002358e  mov     dword ptr [rsp+650h+lpReturnSize], r12d
0x180023593  mov     eax, [rsp+650h+dwProcessId]
0x180023597  mov     dword ptr [rsp+650h+lpName], eax
0x18002359b  mov     eax, [rbp+550h+var_5D0]
0x18002359e  mov     [rsp+650h+dwMaximumSizeLow], eax
0x1800235a2  lea     r9, [rbp+550h+Buffer]
0x1800235a9  lea     r8, aSProtectedcras; "\"%s\" -protectedcrash -p %u -i %u -h %"...
0x1800235b0  mov     edx, 104h; unsigned __int64
0x1800235b5  lea     rcx, [rbp+550h+CommandLine]; wchar_t *
0x1800235bc  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800235c1  mov     esi, eax
0x1800235c3  xor     edx, edx
0x1800235c5  test    eax, eax
0x1800235c7  jns     short loc_1800235F4
0x1800235c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235d0  lea     rax, WPP_GLOBAL_Control
0x1800235d7  cmp     rcx, rax
0x1800235da  jz      loc_180023C48
0x1800235e0  test    byte ptr [rcx+1Ch], 1
0x1800235e4  jz      loc_180023C48
0x1800235ea  mov     edx, 5Bh ; '['
0x1800235ef  jmp     loc_180023C35
0x1800235f4  mov     [rbp+550h+StartupInfo.cb], 70h ; 'p'
0x1800235fb  lea     rax, dword_180039414
0x180023602  mov     [rbp+550h+StartupInfo.lpDesktop], rax
0x180023606  mov     [rbp+550h+StartupInfo.dwFlags], 1
0x18002360d  mov     [rbp+550h+StartupInfo.wShowWindow], dx
0x180023611  mov     qword ptr [rbp+550h+Value], r12
0x180023618  mov     dword ptr [rbp+550h+Value+8], ebx
0x18002361e  mov     eax, dword ptr [rbp+550h+var_590+4]
0x180023621  mov     dword ptr [rbp+550h+Value+0Ch], eax
0x180023627  mov     dword ptr [rbp+550h+var_480], edi
0x18002362d  mov     eax, dword ptr [rbp+550h+var_588+4]
0x180023630  mov     dword ptr [rbp+550h+var_480+4], eax
0x180023636  mov     r12, [rsp+650h+var_5F8]
0x18002363b  mov     qword ptr [rbp+550h+var_480+8], r12
0x180023642  mov     esi, 4
0x180023647  test    r13b, 1
0x18002364b  jz      short loc_18002367D
0x18002364d  mov     rsi, [rbp+550h+var_580]
0x180023651  xor     r13d, r13d
0x180023654  test    rsi, rsi
0x180023657  jnz     short loc_18002365E
0x180023659  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002365e  mov     qword ptr [rbp+550h+var_470], rsi
0x180023665  mov     esi, 5
0x18002366a  test    r15, r15
0x18002366d  jz      short loc_180023680
0x18002366f  mov     qword ptr [rbp+550h+var_470+8], r15
0x180023676  mov     esi, 6
0x18002367b  jmp     short loc_180023680
0x18002367d  xor     r13d, r13d
0x180023680  lea     r9, [rbp+550h+Size]; lpSize
0x180023684  xor     r8d, r8d; dwFlags
0x180023687  lea     edx, [r8+1]; dwAttributeCount
0x18002368b  xor     ecx, ecx; lpAttributeList
0x18002368d  call    cs:__imp_InitializeProcThreadAttributeList
0x180023693  test    eax, eax
0x180023695  jnz     short loc_1800236FF
0x180023697  call    cs:__imp_GetLastError
0x18002369d  cmp     eax, 7Ah ; 'z'
0x1800236a0  jz      short loc_1800236FF
0x1800236a2  call    cs:__imp_GetLastError
0x1800236a8  mov     esi, eax
0x1800236aa  test    eax, eax
0x1800236ac  jle     short loc_1800236B7
0x1800236ae  movzx   esi, ax
0x1800236b1  or      esi, 80070000h
0x1800236b7  test    esi, esi
0x1800236b9  mov     eax, 80004005h
0x1800236be  cmovns  esi, eax
0x1800236c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236c8  lea     rax, WPP_GLOBAL_Control
0x1800236cf  cmp     rcx, rax
0x1800236d2  jz      loc_180023C4D
0x1800236d8  test    byte ptr [rcx+1Ch], 1
0x1800236dc  jz      loc_180023C4D
0x1800236e2  mov     edx, 5Ch ; '\'
0x1800236e7  mov     r9d, esi
0x1800236ea  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x1800236f1  mov     rcx, [rcx+10h]
0x1800236f5  call    WPP_SF_d
0x1800236fa  jmp     loc_180023C4D
0x1800236ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023706  mov     rcx, [rbp+550h+Size]; unsigned __int64
0x18002370a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002370f  mov     r15, rax
  ... truncated ...
```
