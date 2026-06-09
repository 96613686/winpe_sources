# CProcessDump::GenerateDump(IWerByteStream *,ulong,void *)

- ea: `0x18007fda8`
- end: `0x18008141b`
- name: `?GenerateDump@CProcessDump@@AEAAJPEAUIWerByteStream@@KPEAX@Z`
- size: `5747`
- prototype: `__int64 __fastcall(CProcessDump *__hidden this, struct IWerByteStream *, unsigned int, void *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007f868`
- `0x180081f40`

## callees

- `0x18000193c`
- `0x18000716c`
- `0x180007db4`
- `0x180007de0`
- `0x180009ad4`
- `0x18000c390`
- `0x18000dad0`
- `0x1800144f0`
- `0x18001f458`
- `0x18001fe24`
- `0x1800241a0`
- `0x18002c95c`
- `0x1800303dc`
- `0x1800306e4`
- `0x180036cb0`
- `0x18003bf14`
- `0x180045bdc`
- `0x18004c8ec`
- `0x180050db0`
- `0x1800517cc`
- `0x180051efc`
- `0x180051fa4`
- `0x18007fda8`
- `0x180081bb0`
- `0x1800821a0`
- `0x180095780`
- `0x1800958ec`
- `0x180095cb0`
- `0x180095dec`
- `0x18009d248`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008067d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800806c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080c30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008067d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800806c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080c30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800803e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800803f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800804cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800806db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080ae5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800812a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800812b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800803e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800803f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800804cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800806db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080ae5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800812a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800812b1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180080404`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800804a0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800812bf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180080404`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800804a0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800812bf`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800803ec`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800803ec`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180080adf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180080adf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800806f8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180080ad5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800806f8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180080ad5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008071b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008072d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008071b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008072d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008040e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800804ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800808b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008040e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800804ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800808b1`
- `ntdll!NtSetInformationThread` at `0x1800804e9`
- `ntdll!NtSetInformationThread` at `0x1800804e9`
- `ntdll!RtlEnableThreadProfiling` at `0x180080535`
- `ntdll!RtlEnableThreadProfiling` at `0x180080535`
- `ntdll!RtlReadThreadProfilingData` at `0x180080bc2`
- `ntdll!RtlReadThreadProfilingData` at `0x180080bc2`
- `ntdll!RtlDisableThreadProfiling` at `0x180080bcf`
- `ntdll!RtlDisableThreadProfiling` at `0x180080bcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081220`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180080727`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180080727`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18008120e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18008120e`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180080465`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180080465`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080693`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800806b2`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080c46`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080c75`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080693`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800806b2`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080c46`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080c75`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800806eb`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180080af5`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800806eb`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180080af5`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x1800806d2`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x180080bf5`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x1800806d2`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x180080bf5`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080863`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x1800808cb`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080f3a`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080fcc`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080ffd`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180081033`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080863`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x1800808cb`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080f3a`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080fcc`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080ffd`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180081033`
- `dbghelp!MiniDumpWriteDump` at `0x1800808a0`
- `dbghelp!MiniDumpWriteDump` at `0x1800808a0`

## string_xrefs

- `0x1800800cf`: `\\?\Wer:\Temp`
- `0x180080f5a`: `\\?\Wer:\Temp`
- `0x180080344`: `Failed to create memory-mapped stream for unencrypted dump: %08X.`
- `0x180080388`: `Failed to create temporary file for unencrypted dump: %08X.`
- `0x1800803c9`: `Failed to create transient file for dump: %08X.`
- `0x180080423`: `Failed to set debug thread priority %d: HRESULT %08X.`
- `0x180080549`: `Failed to enable thread profiling: Win32 error %u.`
- `0x180080cb3`: `MiniDumpWriteDump took:\n- Ticks     : %14u ms.\n- Cycles    : %14I64u.`
- `0x180080dd8`: `MiniDumpWriteDump I/O counters:\n- Reads     : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\n- Writes    : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\n- Other     : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\n`
- `0x180080e57`: `MiniDumpWriteDump read memory failures: %u.\n`
- `0x180080e89`: `Write buffer:\n- Buffer size           : %u bytes.\n- Flushes (full+partial): %u + %u.\n`
- `0x180080e97`: `Write buffer disabled.\n`
- `0x180080ed3`: `MiniDumpWriteDump failed: %08X.`
- `0x180080f76`: `Failed to create temporary file for encrypted dump: %08X.`
- `0x180081045`: `Failed to copy encrypted dump: %08X.`
- `0x1800811e5`: `Failed to copy transient dump: %08X.`

## pseudocode

```c
__int64 __fastcall CProcessDump::GenerateDump(CProcessDump *this, struct IWerByteStream *a2, unsigned int a3, void *a4)
{
  char v4; // r13
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // r14d
  int v10; // esi
  BOOL v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rdx
  char v14; // di
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  signed int v18; // r12d
  __int64 v19; // rcx
  int v20; // r13d
  MINIDUMP_TYPE v21; // r13d
  _QWORD *v22; // rbx
  unsigned int (__fastcall *v23)(_QWORD, _QWORD **); // rdi
  BOOL v24; // esi
  unsigned int v25; // edi
  int v26; // eax
  int New; // eax
  int v28; // eax
  HANDLE v29; // rax
  int v30; // ebx
  HANDLE v31; // rax
  DWORD v32; // eax
  void *v33; // r14
  HANDLE v34; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v37; // eax
  HANDLE v38; // rax
  NTSTATUS v39; // eax
  HANDLE v40; // rax
  unsigned int v41; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v43; // rax
  HANDLE v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  DWORD TickCount; // ebx
  DWORD v48; // eax
  void ***v49; // rdi
  struct IWerByteStream *p_hFile; // rbx
  int v51; // eax
  BOOL v52; // ebx
  __int64 v53; // rcx
  int FinalPathByHandle; // eax
  int v55; // edx
  int v56; // r8d
  int v57; // ecx
  int v58; // r9d
  HANDLE v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int16 *v62; // rax
  _OWORD *v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rcx
  int v66; // r14d
  BOOL v67; // edi
  HANDLE v68; // rax
  HANDLE v69; // rax
  HANDLE v70; // rbx
  unsigned __int64 v71; // r13
  __int64 v72; // rdx
  __int64 v73; // rcx
  ULONGLONG v74; // r14
  ULONGLONG v75; // rsi
  ULONGLONG v76; // rdi
  ULONGLONG v77; // rbx
  ULONGLONG v78; // r11
  ULONGLONG v79; // r10
  unsigned int v80; // r13d
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r9
  const wchar_t *v84; // r8
  int v85; // eax
  int v86; // eax
  __int64 v87; // rbx
  int v88; // eax
  int v89; // eax
  void ***v90; // rcx
  int v91; // eax
  int v92; // eax
  __int64 v93; // rdx
  __int64 v94; // rcx
  int v95; // ebx
  HANDLE v96; // rax
  int v97; // edx
  _QWORD *v98; // rbx
  void (__fastcall *v99)(_QWORD, _QWORD **); // rdi
  PMINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+20h] [rbp-E0h]
  PMINIDUMP_EXCEPTION_INFORMATION ExceptionParama; // [rsp+20h] [rbp-E0h]
  PMINIDUMP_USER_STREAM_INFORMATION UserStreamParam; // [rsp+28h] [rbp-D8h]
  unsigned int v104; // [rsp+60h] [rbp-A0h]
  char v105; // [rsp+64h] [rbp-9Ch]
  int v106; // [rsp+68h] [rbp-98h]
  BOOL v107; // [rsp+6Ch] [rbp-94h]
  BOOL v108; // [rsp+70h] [rbp-90h]
  BOOL ProcessMemoryInfo; // [rsp+74h] [rbp-8Ch]
  int v110; // [rsp+78h] [rbp-88h]
  BOOL v111; // [rsp+7Ch] [rbp-84h]
  void **v112; // [rsp+80h] [rbp-80h] BYREF
  struct IWerByteStream *v113; // [rsp+88h] [rbp-78h]
  int v114; // [rsp+90h] [rbp-70h]
  unsigned int v115; // [rsp+94h] [rbp-6Ch]
  int ThreadPriority; // [rsp+98h] [rbp-68h]
  __int64 v117; // [rsp+A0h] [rbp-60h] BYREF
  LARGE_INTEGER Frequency; // [rsp+A8h] [rbp-58h] BYREF
  struct IWerByteStream *v119; // [rsp+B0h] [rbp-50h]
  void **v120; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v121; // [rsp+C0h] [rbp-40h]
  void **v122; // [rsp+C8h] [rbp-38h] BYREF
  struct IWerByteStream *v123; // [rsp+D0h] [rbp-30h]
  MINIDUMP_TYPE v124; // [rsp+D8h] [rbp-28h] BYREF
  signed int v125; // [rsp+DCh] [rbp-24h] BYREF
  BOOL ProcessIoCounters; // [rsp+E0h] [rbp-20h]
  HANDLE v127; // [rsp+E8h] [rbp-18h]
  __int64 v128; // [rsp+F0h] [rbp-10h] BYREF
  CProcessDump *v129; // [rsp+F8h] [rbp-8h]
  __int64 v130; // [rsp+100h] [rbp+0h]
  char v131; // [rsp+108h] [rbp+8h]
  __int128 v132; // [rsp+110h] [rbp+10h] BYREF
  __int128 v133; // [rsp+120h] [rbp+20h]
  __int128 v134; // [rsp+130h] [rbp+30h]
  __int128 v135; // [rsp+140h] [rbp+40h]
  __int128 v136; // [rsp+150h] [rbp+50h]
  __int128 v137; // [rsp+160h] [rbp+60h]
  __int128 v138; // [rsp+170h] [rbp+70h]
  _QWORD *v139; // [rsp+180h] [rbp+80h] BYREF
  int v140; // [rsp+188h] [rbp+88h]
  int v141; // [rsp+18Ch] [rbp+8Ch]
  __int128 v142; // [rsp+190h] [rbp+90h]
  __int128 v143; // [rsp+1A0h] [rbp+A0h]
  __int128 v144; // [rsp+1B0h] [rbp+B0h]
  __int128 v145; // [rsp+1C0h] [rbp+C0h]
  __int128 v146; // [rsp+1D0h] [rbp+D0h]
  __int128 v147; // [rsp+1E0h] [rbp+E0h]
  CProcessDump *v148; // [rsp+1F0h] [rbp+F0h]
  LARGE_INTEGER v149; // [rsp+1F8h] [rbp+F8h] BYREF
  HANDLE Process; // [rsp+200h] [rbp+100h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int64 v152; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int64 CycleTime; // [rsp+218h] [rbp+118h] BYREF
  HANDLE v154; // [rsp+220h] [rbp+120h]
  __int128 v155; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v156[2]; // [rsp+238h] [rbp+138h] BYREF
  __int64 v157[2]; // [rsp+248h] [rbp+148h] BYREF
  _WORD v158[8]; // [rsp+258h] [rbp+158h] BYREF
  _QWORD v159[2]; // [rsp+268h] [rbp+168h] BYREF
  _WORD v160[8]; // [rsp+278h] [rbp+178h] BYREF
  __int64 v161; // [rsp+288h] [rbp+188h] BYREF
  struct _MINIDUMP_CALLBACK_INFORMATION CallbackParam; // [rsp+290h] [rbp+190h] BYREF
  __int64 v163; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v164; // [rsp+2A8h] [rbp+1A8h] BYREF
  HANDLE hObject[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v166; // [rsp+2C0h] [rbp+1C0h]
  __int128 v167; // [rsp+2D0h] [rbp+1D0h]
  LPCVOID lpBaseAddress[2]; // [rsp+2E0h] [rbp+1E0h]
  __int128 v169; // [rsp+2F0h] [rbp+1F0h]
  const wchar_t *v170; // [rsp+300h] [rbp+200h] BYREF
  void **hFile; // [rsp+308h] [rbp+208h] BYREF
  __int128 v172; // [rsp+310h] [rbp+210h]
  __int128 v173; // [rsp+320h] [rbp+220h]
  _QWORD v174[2]; // [rsp+330h] [rbp+230h] BYREF
  int v175; // [rsp+340h] [rbp+240h]
  _BYTE v176[288]; // [rsp+350h] [rbp+250h] BYREF
  struct _IO_COUNTERS v177; // [rsp+470h] [rbp+370h] BYREF
  _IO_COUNTERS IoCounters; // [rsp+4A0h] [rbp+3A0h] BYREF
  PROCESS_MEMORY_COUNTERS v179; // [rsp+4D0h] [rbp+3D0h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+520h] [rbp+420h] BYREF
  PROCESS_MEMORY_COUNTERS v181; // [rsp+570h] [rbp+470h] BYREF
  PROCESS_MEMORY_COUNTERS v182; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int16 v183; // [rsp+610h] [rbp+510h] BYREF
  char v184; // [rsp+612h] [rbp+512h]
  unsigned int v185; // [rsp+614h] [rbp+514h]

  v154 = a4;
  v4 = a3;
  v104 = a3;
  v119 = a2;
  v148 = this;
  CallbackParam = 0;
  v155 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  ThreadPriority = 0x7FFFFFFF;
  v112 = &CFileByteStream::`vftable';
  v113 = 0;
  memset_0(hObject, 0, 0x50u);
  v156[0] = &CByteStreamAdapter::`vftable';
  v156[1] = hObject;
  v174[0] = &CIStreamAdapter::`vftable';
  v174[1] = a2;
  v175 = 1;
  v120 = &CFileByteStream::`vftable';
  v121 = 0;
  v122 = &CFileByteStream::`vftable';
  v123 = 0;
  hFile = &CBufferedWriteStream::`vftable';
  v172 = 0;
  v173 = 0;
  memset_0(&v139, 0, 0x70u);
  Process = 0;
  v117 = 0;
  memset_0(&v183, 0, 0x120u);
  memset_0(&ppsmemCounters, 0, sizeof(ppsmemCounters));
  memset_0(&v179, 0, sizeof(v179));
  memset_0(&v181, 0, sizeof(v181));
  memset_0(&v182, 0, sizeof(v182));
  memset(&IoCounters, 0, sizeof(IoCounters));
  memset(&v177, 0, sizeof(v177));
  PerformanceCount.QuadPart = 0;
  v149.QuadPart = 0;
  Frequency.QuadPart = 0;
  CycleTime = 0;
  v152 = 0;
  if ( !*(_DWORD *)this )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( !*((_QWORD *)this + 14) && !*((_QWORD *)this + 96) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( !*((_DWORD *)this + 30) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  memset_0(&v132, 0, 0x50u);
  *(_OWORD *)hObject = v132;
  v166 = v133;
  v167 = v134;
  *(_OWORD *)lpBaseAddress = v135;
  v169 = v136;
  v9 = *((_DWORD *)this + 21);
  v110 = v9;
  if ( (*((_DWORD *)this + 44) & 0x40000000) != 0 && !*((_DWORD *)this + 17) && *((_DWORD *)this + 15) == 0x80000000 )
  {
    v106 = 1;
    v10 = 8;
  }
  else
  {
    v106 = 0;
    v10 = 0;
  }
  v11 = 0;
  v111 = 0;
  v12 = 0x80000;
  if ( *((_DWORD *)this + 20) != -1 )
    v12 = *((_DWORD *)this + 20);
  v115 = v12;
  if ( !(unsigned __int8)IsXerTransportEventUploadCompletePresent()
    || (v14 = 1, !CRegSetting::GetDwordData((CRegSetting *)(*((_QWORD *)this + 2) + 51680LL))) )
  {
    v14 = 0;
  }
  v105 = v14;
  if ( *((_DWORD *)this + 18) != -1 )
  {
    v11 = *((_DWORD *)this + 18) != 0;
    v111 = v11;
  }
  if ( v9 )
  {
    v15 = CProcessDump::InitializeDumpEncryptor(this);
    v18 = v15;
    if ( v15 < 0 )
    {
      CProcessDump::LogTrace(this, 0, L"Failed to initialize dump encryptor: %08X.", (unsigned int)v15);
      goto LABEL_210;
    }
    if ( v14 )
    {
      CFileByteStream::CreateNew((CFileByteStream *)&v112, L"\\\\?\\Wer:\\Temp", L".udf", 0, 0x4000100u, 0);
    }
    else if ( *((_QWORD *)this + 12) )
    {
      v26 = MmsCreate(hObject);
      v18 = v26;
      if ( v26 < 0 )
      {
        CProcessDump::LogTrace(
          this,
          0,
          L"Failed to create memory-mapped stream for unencrypted dump: %08X.",
          (unsigned int)v26);
        goto LABEL_210;
      }
    }
    else
    {
      if ( !*((_QWORD *)this + 13) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16);
      New = CFileByteStream::CreateNew((CFileByteStream *)&v112, 0, L".udf", 0, 0x4000100u, 0);
      v18 = New;
      if ( New < 0 )
      {
        CProcessDump::LogTrace(
          this,
          0,
          L"Failed to create temporary file for unencrypted dump: %08X.",
          (unsigned int)New);
        goto LABEL_210;
      }
    }
  }
  else if ( v11 )
  {
    v28 = CFileByteStream::CreateNew((CFileByteStream *)&v122, 0, L".tdf", 0, 0x4000100u, 0);
    v18 = v28;
    if ( v28 < 0 )
    {
      CProcessDump::LogTrace(this, 0, L"Failed to create transient file for dump: %08X.", (unsigned int)v28);
      goto LABEL_210;
    }
  }
  v114 = 50;
  v19 = *((unsigned int *)this + 43);
  if ( !(_DWORD)v19 )
  {
    v19 = *((unsigned int *)this + 52);
    if ( *((_DWORD *)this + 42) != 3 )
      LODWORD(v19) = v19 | 0x400;
  }
  v20 = v19 | 0x20000;
  if ( (v19 & 2) == 0 )
    v20 = v19;
  v21 = v20 & 0x5FFFFFF;
  LODWORD(v155) = *((_DWORD *)this + 48);
  *(_QWORD *)((char *)&v155 + 4) = *((_QWORD *)this + 228);
  HIDWORD(v155) = *((_DWORD *)this + 458);
  if ( !*((_QWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v19, v13);
  v22 = (_QWORD *)*((_QWORD *)this + 1);
  v23 = (unsigned int (__fastcall *)(_QWORD, _QWORD **))v22[2];
  if ( !v23 )
  {
    v24 = 0;
LABEL_58:
    v25 = v104;
    if ( v106 )
      goto LABEL_59;
    goto LABEL_49;
  }
  memset_0(&v132, 0, 0x70u);
  v141 = HIDWORD(v132);
  v142 = v133;
  v143 = v134;
  v144 = v135;
  v145 = v136;
  v146 = v137;
  v147 = v138;
  v139 = v22;
  v140 = 19;
  *(_QWORD *)&v142 = v22[8];
  *((_QWORD *)&v142 + 1) = *((_QWORD *)this + 95);
  *(_QWORD *)&v143 = __PAIR64__(HIDWORD(v148), (unsigned int)this);
  DWORD2(v143) = *((_DWORD *)this + 42);
  HIDWORD(v143) = v21;
  *(_QWORD *)&v144 = *(_QWORD *)((char *)this + 172);
  DWORD2(v144) = *((_DWORD *)this + 30);
  HIDWORD(v144) = *((_DWORD *)this + 48);
  LODWORD(v145) = *((_DWORD *)this + 31);
  *((_QWORD *)&v145 + 1) = (char *)this + 200;
  *(_QWORD *)&v146 = (char *)this + 1824;
  *((_QWORD *)&v146 + 1) = CProcessDump::static_vLogCallbackRoutine;
  *(_QWORD *)&v147 = __PAIR64__(HIDWORD(v148), (unsigned int)this);
  DWORD2(v147) = v10 | (v104 >> 4) & 2 | (v9 != 0 ? 4 : 0) | (*((_DWORD *)this + 32) != 0);
  v24 = 0;
  if ( !v23(v22[3], &v139) )
    goto LABEL_58;
  v25 = v104 & 0xFFFFFFDF | (32 * ((DWORD2(v147) >> 1) & 1));
  LOBYTE(v104) = v25;
  v110 = (DWORD2(v147) >> 2) & 1;
  if ( (BYTE8(v147) & 8) != 0 && !*((_DWORD *)this + 17) && *((_DWORD *)this + 15) == 0x80000000 )
  {
    v106 = 1;
LABEL_59:
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, 0x10000) )
    {
      v106 = 0;
      LastError = GetLastError();
      v37 = ERROR_HR_FROM_WIN32(LastError);
      CProcessDump::LogTrace(this, 1u, L"Failed to enable background priority: HRESULT %08X.", v37);
    }
    v38 = GetCurrentThread();
    v39 = NtSetInformationThread(v38, ThreadIoPriority, &unk_1800BF9F0, 4u);
    if ( v39 < 0 )
      CProcessDump::LogTrace(this, 1u, L"Failed to bump I/O priority to Low: NTSTATUS %08X.", (unsigned int)v39);
    goto LABEL_52;
  }
  v106 = 0;
LABEL_49:
  if ( *((_DWORD *)this + 15) != 0x80000000 )
  {
    v29 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v29);
    v30 = *((_DWORD *)this + 15);
    v31 = GetCurrentThread();
    if ( !SetThreadPriority(v31, v30) )
    {
      v32 = GetLastError();
      LODWORD(ExceptionParam) = ERROR_HR_FROM_WIN32(v32);
      CProcessDump::LogTrace(
        this,
        1u,
        L"Failed to set debug thread priority %d: HRESULT %08X.",
        *((unsigned int *)this + 15),
        ExceptionParam);
    }
  }
LABEL_52:
  v33 = (void *)*((_QWORD *)this + 96);
  if ( !v33 || (v25 & 0x20) != 0 )
  {
    v33 = (void *)*((_QWORD *)this + 14);
    v34 = v33;
  }
  else
  {
    v34 = 0;
    if ( !(unsigned int)PssQuerySnapshot(*((_QWORD *)this + 96), 1, &Process, 8) )
      v34 = Process;
  }
  v127 = v34;
  if ( *((_DWORD *)this + 16) )
  {
    v40 = GetCurrentThread();
    v41 = RtlEnableThreadProfiling(v40, 1, 0, &v117);
    v114 = v41;
    if ( v41 )
    {
      v117 = 0;
      CProcessDump::LogTrace(this, 1u, L"Failed to enable thread profiling: Win32 error %u.", v41);
    }
  }
  memset_0(&v132, 0, 0x48u);
  *(_OWORD *)&ppsmemCounters.cb = v132;
  *(_OWORD *)&ppsmemCounters.WorkingSetSize = v133;
  *(_OWORD *)&ppsmemCounters.QuotaPagedPoolUsage = v134;
  *(_OWORD *)&ppsmemCounters.QuotaNonPagedPoolUsage = v135;
  ppsmemCounters.PeakPagefileUsage = v136;
  memset_0(&v132, 0, 0x48u);
  *(_OWORD *)&v179.cb = v132;
  *(_OWORD *)&v179.WorkingSetSize = v133;
  *(_OWORD *)&v179.QuotaPagedPoolUsage = v134;
  *(_OWORD *)&v179.QuotaNonPagedPoolUsage = v135;
  v179.PeakPagefileUsage = v136;
  memset_0(&v132, 0, 0x48u);
  *(_OWORD *)&v181.cb = v132;
  *(_OWORD *)&v181.WorkingSetSize = v133;
  *(_OWORD *)&v181.QuotaPagedPoolUsage = v134;
  *(_OWORD *)&v181.QuotaNonPagedPoolUsage = v135;
  v181.PeakPagefileUsage = v136;
  memset_0(&v132, 0, 0x48u);
  *(_OWORD *)&v182.cb = v132;
  *(_OWORD *)&v182.WorkingSetSize = v133;
  *(_OWORD *)&v182.QuotaPagedPoolUsage = v134;
  *(_OWORD *)&v182.QuotaNonPagedPoolUsage = v135;
  v182.PeakPagefileUsage = v136;
  CurrentProcess = GetCurrentProcess();
  ProcessMemoryInfo = K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, 0x48u);
  if ( v34 )
    v107 = K32GetProcessMemoryInfo(v34, &v181, 0x48u);
  else
    v107 = 0;
  v43 = GetCurrentProcess();
  ProcessIoCounters = GetProcessIoCounters(v43, &IoCounters);
  v44 = GetCurrentThread();
  QueryThreadCycleTime(v44, &CycleTime);
  QueryPerformanceCounter(&PerformanceCount);
  if ( *((_DWORD *)this + 14) )
  {
    CProcessDump::LogTrace(this, 2u, L"Sleeping for %u ms.");
    TickCount = GetTickCount();
    Sleep(*((_DWORD *)this + 14));
    v48 = GetTickCount();
    CProcessDump::LogTrace(this, 2u, L"Woke up, slept for %u ms.", v48 - TickCount);
  }
  v129 = this;
  LODWORD(v130) = v25;
  CallbackParam.CallbackRoutine = (MINIDUMP_CALLBACK_ROUTINE)CProcessDump::static_MiniDumpCallback;
  CallbackParam.CallbackParam = &v128;
  if ( !v110 )
  {
    if ( !v111 )
    {
      v49 = (void ***)v119;
      p_hFile = v119;
      goto LABEL_89;
    }
    v49 = &v122;
    p_hFile = v123;
    if ( v123 )
    {
LABEL_87:
      v131 = 0;
      goto LABEL_90;
    }
LABEL_86:
    MicrosoftTelemetryAssertTriggeredNoArgs(v46, v45);
    goto LABEL_87;
  }
  if ( v105 )
  {
    if ( !*((_QWORD *)this + 13) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v46, v45);
    v49 = &v112;
    p_hFile = v113;
    if ( v113 )
      goto LABEL_87;
    goto LABEL_86;
  }
  if ( !*((_QWORD *)this + 12) )
  {
    if ( !*((_QWORD *)this + 13) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v46, v45);
    v49 = &v112;
    p_hFile = v113;
    if ( v113 )
      goto LABEL_87;
    goto LABEL_86;
  }
  v49 = (void ***)v156;
  p_hFile = (struct IWerByteStream *)v156;
LABEL_89:
  v131 = 1;
LABEL_90:
  v108 = 0;
  if ( v115 )
  {
    v51 = CBufferedWriteStream::Initialize((CBufferedWriteStream *)&hFile, (struct IWerByteStream *)v49, v115);
    v24 = v51 >= 0;
    v108 = v24;
    if ( v51 < 0 )
    {
      v108 = 0;
    }
    else
    {
      p_hFile = (struct IWerByteStream *)&hFile;
      v131 = 1;
    }
  }
  *((_QWORD *)this + 230) = 0;
  if ( *((_DWORD *)this + 19) )
  {
    v18 = -2147023773;
  }
  else
  {
    if ( (unsigned __int8)IsXerProgressCallbackPresent() )
      XerProgressCallback(3);
    v52 = MiniDumpWriteDump(
            v33,
            *((_DWORD *)this + 30),
            p_hFile,
            v21,
            (PMINIDUMP_EXCEPTION_INFORMATION)((unsigned __int64)&v155
                                            & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 228) >> 64)),
            0,
            &CallbackParam);
    if ( v52 )
      v18 = 0;
    else
      v18 = GetLastError();
    if ( (unsigned __int8)IsXerProgressCallbackPresent() )
      XerProgressCallback(4);
    v157[0] = (__int64)v158;
    v157[1] = (__int64)v158;
    v158[0] = 0;
    v53 = *((_QWORD *)this + 2);
    if ( v53 )
      CReport::GetUniqueIdentifier(v53, v157);
    else
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v157);
    v159[0] = v160;
    v159[1] = v160;
    v160[0] = 0;
    if ( v154 == (HANDLE)-1LL )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v159);
    }
    else
    {
      FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(v154);
      if ( FinalPathByHandle < 0
        && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_4909ce9a3d833966bf1277dfd490a226_Traceguids,
          (unsigned int)FinalPathByHandle);
      }
    }
    if ( (unsigned int)dword_1800D9000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 0x400000000000LL) )
    {
      v161 = v159[0];
      v124 = v21;
      v164 = v157[0];
      v170 = L"ProcessDump";
      v125 = v18;
      v163 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v57,
        (unsigned int)&unk_1800C90F9,
        v56,
        v58,
        (__int64)&v163,
        (__int64)&v125,
        (__int64)&v170,
        (__int64)&v164,
        (__int64)&v124,
        (__int64)&v161);
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, v56, v18, v157[0], v21);
    if ( !v52 && v18 >= 0 )
      v18 = -2147467259;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v159);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v157);
  }
  if ( v24 )
    CBufferedWriteStream::Flush((CBufferedWriteStream *)&hFile, *(void **)(*((_QWORD *)this + 1) + 64LL));
  QueryPerformanceCounter(&v149);
  QueryPerformanceFrequency(&Frequency);
  v59 = GetCurrentThread();
  QueryThreadCycleTime(v59, &v152);
  if ( !Frequency.QuadPart )
    MicrosoftTelemetryAssertTriggeredNoArgs(v61, v60);
  memset_0(v176, 0, sizeof(v176));
  v62 = &v183;
  v63 = v176;
  v64 = 2;
  do
  {
    *(_OWORD *)v62 = *v63;
    *((_OWORD *)v62 + 1) = v63[1];
    *((_OWORD *)v62 + 2) = v63[2];
    *((_OWORD *)v62 + 3) = v63[3];
    *((_OWORD *)v62 + 4) = v63[4];
    *((_OWORD *)v62 + 5) = v63[5];
    *((_OWORD *)v62 + 6) = v63[6];
    *((_OWORD *)v62 + 7) = v63[7];
    v62 += 64;
    v63 += 8;
    --v64;
  }
  while ( v64 );
  *(_OWORD *)v62 = *v63;
  *((_OWORD *)v62 + 1) = v63[1];
  v65 = v117;
  if ( v117 )
  {
    if ( !*((_DWORD *)this + 16) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v117, 0);
      v65 = v117;
    }
    v183 = 288;
    v184 = 1;
    v66 = RtlReadThreadProfilingData(v65, 1, &v183);
    RtlDisableThreadProfiling(v117);
  }
  else
  {
    v66 = v114;
  }
  v67 = ProcessIoCounters;
  if ( ProcessIoCounters )
  {
    v68 = GetCurrentProcess();
    v67 = GetProcessIoCounters(v68, &v177);
  }
  else
  {
    memset(&v177, 0, sizeof(v177));
  }
  if ( ProcessMemoryInfo )
  {
    v69 = GetCurrentProcess();
    ProcessMemoryInfo = K32GetProcessMemoryInfo(v69, &v179, 0x48u);
  }
  if ( v107 )
  {
    v70 = v127;
    if ( !v127 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v65, v64);
    v107 = K32GetProcessMemoryInfo(v70, &v182, 0x48u);
  }
  v71 = (unsigned __int64)(1000 * (v149.QuadPart - PerformanceCount.QuadPart)) / Frequency.QuadPart;
  CProcessDump::LogTrace(
    this,
    2u,
    L"MiniDumpWriteDump took:\r\n- Ticks     : %14u ms.\r\n- Cycles    : %14I64u.",
    (unsigned int)v71,
    v152 - CycleTime);
  if ( !v66 )
    CProcessDump::LogTrace(this, 0x40000002u, L"- CSwitches : %14u.", v185);
  if ( v67 )
  {
    v74 = v177.ReadOperationCount - IoCounters.ReadOperationCount;
    v177.ReadOperationCount -= IoCounters.ReadOperationCount;
    v75 = v177.ReadTransferCount - IoCounters.ReadTransferCount;
    v177.ReadTransferCount -= IoCounters.ReadTransferCount;
    v76 = v177.WriteOperationCount - IoCounters.WriteOperationCount;
    v177.WriteOperationCount -= IoCounters.WriteOperationCount;
    v77 = v177.WriteTransferCount - IoCounters.WriteTransferCount;
    v177.WriteTransferCount -= IoCounters.WriteTransferCount;
    v78 = v177.OtherOperationCount - IoCounters.OtherOperationCount;
    v177.OtherOperationCount -= IoCounters.OtherOperationCount;
    v79 = v177.OtherTransferCount - IoCounters.OtherTransferCount;
    v177.OtherTransferCount -= IoCounters.OtherTransferCount;
    v80 = (_DWORD)v71 << 10;
    if ( !v80 )
      v80 = 1;
    CProcessDump::LogTrace(
      this,
      2u,
      L"MiniDumpWriteDump I/O counters:\r\n"
       "- Reads     : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\r\n"
       "- Writes    : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\r\n"
       "- Other     : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\r\n",
      v74,
      v75,
      1000 * v75 / v80,
      v76,
      v77,
      1000 * v77 / v80,
      v78,
      v79,
      1000 * v79 / v80);
    v24 = v108;
  }
  if ( ProcessMemoryInfo )
    CProcessDump::LogTrace(this, 2u, L"Page faults (local) : %9u.", v179.PageFaultCount - ppsmemCounters.PageFaultCount);
  if ( v107 )
  {
    if ( !v127 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v73, v72);
    CProcessDump::LogTrace(this, 2u, L"Page faults (remote): %9u.", v182.PageFaultCount - v181.PageFaultCount);
  }
  CProcessDump::LogTrace(this, 2u, L"MiniDumpWriteDump read memory failures: %u.\r\n", HIDWORD(v130));
  if ( v24 )
  {
    LODWORD(UserStreamParam) = HIDWORD(v173);
    LODWORD(ExceptionParama) = DWORD2(v173);
    CProcessDump::LogTrace(
      this,
      2u,
      L"Write buffer:\r\n- Buffer size           : %u bytes.\r\n- Flushes (full+partial): %u + %u.\r\n",
      v115,
      ExceptionParama,
      UserStreamParam);
  }
  else
  {
    CProcessDump::LogTrace(this, 2u, L"Write buffer disabled.\r\n");
  }
  if ( v18 != -2147023673 )
  {
    if ( v18 < 0 )
    {
      v83 = (unsigned int)v18;
      v84 = L"MiniDumpWriteDump failed: %08X.";
LABEL_161:
      CProcessDump::LogTrace(this, 0, v84, v83);
      goto LABEL_209;
    }
    if ( v110 )
    {
      if ( !*((_QWORD *)this + 12) && !*((_QWORD *)this + 13) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v82, v81);
      if ( v105 )
      {
        if ( !*((_QWORD *)this + 13) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v82, v81);
        CProcessDump::LogTrace(this, 2u, L"Streaming-based encryption NOT supported.");
        if ( (unsigned __int8)IsXerProgressCallbackPresent() )
          XerProgressCallback(5);
        v85 = CFileByteStream::CreateNew((CFileByteStream *)&v120, L"\\\\?\\Wer:\\Temp", L".edf", 1u, 0x4000100u, 0);
        v18 = v85;
        if ( v85 < 0 )
        {
LABEL_172:
          CProcessDump::LogTrace(
            this,
            0,
            L"Failed to create temporary file for encrypted dump: %08X.",
            (unsigned int)v85);
          goto LABEL_209;
        }
        v86 = CFileByteStream::SetFilePointer((CFileByteStream *)&v112, 0, 0, 0);
        v18 = v86;
        if ( v86 < 0 )
        {
LABEL_174:
          v83 = (unsigned int)v86;
          v84 = L"Failed to rewind unencrypted dump stream: %08X.";
          goto LABEL_161;
        }
        v18 = (*((__int64 (__fastcall **)(struct IWerByteStream *, __int64))this + 13))(v113, v121);
        if ( (unsigned __int8)IsXerProgressCallbackPresent() )
          XerProgressCallback(6);
        if ( v18 < 0 )
        {
          v83 = (unsigned int)v18;
LABEL_179:
          v84 = L"Dump could not be encrypted: %08X.";
          goto LABEL_161;
        }
        CFileByteStream::Close((CFileByteStream *)&v112);
        if ( (unsigned __int8)IsXerProgressCallbackPresent() )
          XerProgressCallback(7);
        v18 = CByteStream::AlignedCopyTo((CByteStream *)&v120, v119, *(void **)(*((_QWORD *)this + 1) + 64LL), v154);
        if ( (unsigned __int8)IsXerProgressCallbackPresent() )
          XerProgressCallback(8);
        if ( v18 < 0 )
        {
          v83 = (unsigned int)v18;
LABEL_186:
          v84 = L"Failed to copy encrypted dump: %08X.";
          goto LABEL_161;
        }
LABEL_198:
        v90 = &v120;
LABEL_207:
        CFileByteStream::Close((CFileByteStream *)v90);
        goto LABEL_208;
      }
      if ( !*((_QWORD *)this + 12) )
      {
        if ( !*((_QWORD *)this + 13) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v82, v81);
        CProcessDump::LogTrace(this, 2u, L"Streaming-based encryption NOT supported.");
        v85 = CFileByteStream::CreateNew((CFileByteStream *)&v120, 0, L".edf", 1u, 0x4000100u, 0);
        v18 = v85;
        if ( v85 < 0 )
          goto LABEL_172;
        v86 = CFileByteStream::SetFilePointer((CFileByteStream *)&v112, 0, 0, 0);
        v18 = v86;
        if ( v86 < 0 )
          goto LABEL_174;
        v88 = (*((__int64 (__fastcall **)(struct IWerByteStream *, __int64))this + 13))(v113, v121);
        v18 = v88;
        if ( v88 >= 0 )
        {
          CFileByteStream::Close((CFileByteStream *)&v112);
          v89 = CByteStream::CopyTo((CByteStream *)&v120, v119, *(void **)(*((_QWORD *)this + 1) + 64LL));
          v18 = v89;
          if ( v89 < 0 )
          {
            v83 = (unsigned int)v89;
            goto LABEL_186;
          }
          goto LABEL_198;
        }
LABEL_190:
        v83 = (unsigned int)v88;
        goto LABEL_179;
      }
      v87 = v167;
      LODWORD(ExceptionParama) = v167;
      CProcessDump::LogTrace(
        this,
        2u,
        L"Streaming-based encryption supported. Dump size: %08X:%08X.",
        DWORD1(v167),
        ExceptionParama);
      v86 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD, _QWORD, _QWORD))hObject[0] + 5))(
              hObject,
              *(_QWORD *)&DOUBLE_0_0,
              0,
              0);
      v18 = v86;
      if ( v86 < 0 )
        goto LABEL_174;
      v88 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD *, __int64))this + 12))(hObject, v174, v87);
      v18 = v88;
      if ( v88 < 0 )
        goto LABEL_190;
    }
    else if ( v111 )
    {
      if ( !v123 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v82, v81);
      v91 = CFileByteStream::SetFilePointer((CFileByteStream *)&v122, 0, 0, 0);
      v18 = v91;
      if ( v91 < 0 )
      {
        v83 = (unsigned int)v91;
        v84 = L"Failed to rewind transient dump stream: %08X.";
        goto LABEL_161;
      }
      v92 = CByteStream::CopyTo((CByteStream *)&v122, v119, *(void **)(*((_QWORD *)this + 1) + 64LL));
      v18 = v92;
      if ( v92 < 0 )
      {
        v83 = (unsigned int)v92;
        v84 = L"Failed to copy transient dump: %08X.";
        goto LABEL_161;
      }
      v90 = &v122;
      goto LABEL_207;
    }
LABEL_208:
    v18 = 0;
    goto LABEL_209;
  }
  CProcessDump::LogTrace(this, 1u, L"Minidump generation canceled.");
  v18 = -2145681407;
LABEL_209:
  v4 = v104;
LABEL_210:
  if ( lpBaseAddress[1] )
    UnmapViewOfFile(lpBaseAddress[1]);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  memset_0(&v132, 0, 0x50u);
  *(_OWORD *)hObject = v132;
  v166 = v133;
  v167 = v134;
  *(_OWORD *)lpBaseAddress = v135;
  v169 = v136;
  if ( (!*((_QWORD *)this + 96) || (v4 & 0x20) != 0) && *((_QWORD *)this + 14) )
    CProcessDump::LogProcessTerminationState(this);
  v95 = ThreadPriority;
  if ( ThreadPriority == 0x7FFFFFFF )
  {
    if ( !v106 )
      goto LABEL_225;
    v96 = GetCurrentThread();
    v97 = 0x20000;
  }
  else
  {
    if ( v106 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v94, v93);
    v96 = GetCurrentThread();
    v97 = v95;
  }
  SetThreadPriority(v96, v97);
LABEL_225:
  if ( !*((_QWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v94, v93);
  v98 = (_QWORD *)*((_QWORD *)this + 1);
  v99 = (void (__fastcall *)(_QWORD, _QWORD **))v98[2];
  if ( v99 )
  {
    memset_0(&v132, 0, 0x70u);
    v141 = HIDWORD(v132);
    v142 = v133;
    v143 = v134;
    v144 = v135;
    v145 = v136;
    v146 = v137;
    v147 = v138;
    v139 = v98;
    v140 = 20;
    *(_QWORD *)&v142 = v98[8];
    *((_QWORD *)&v142 + 1) = *((_QWORD *)this + 95);
    *(_QWORD *)&v143 = __PAIR64__(HIDWORD(v148), (unsigned int)this);
    DWORD2(v143) = v18;
    *(_QWORD *)&v144 = CProcessDump::static_vLogCallbackRoutine;
    *((_QWORD *)&v144 + 1) = __PAIR64__(HIDWORD(v148), (unsigned int)this);
    v99(v98[3], &v139);
  }
  CBufferedWriteStream::~CBufferedWriteStream((CBufferedWriteStream *)&hFile);
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v122);
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v120);
  CIStreamAdapter::~CIStreamAdapter((CIStreamAdapter *)v174);
  v156[0] = &CByteStreamAdapter::`vftable';
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v112);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18007fda8  push    rbp
0x18007fdaa  push    rbx
0x18007fdab  push    rsi
0x18007fdac  push    rdi
0x18007fdad  push    r12
0x18007fdaf  push    r13
0x18007fdb1  push    r14
0x18007fdb3  push    r15
0x18007fdb5  lea     rbp, [rsp-648h]
0x18007fdbd  sub     rsp, 748h
0x18007fdc4  mov     rax, cs:__security_cookie
0x18007fdcb  xor     rax, rsp
0x18007fdce  mov     [rbp+680h+var_50], rax
0x18007fdd5  mov     [rbp+680h+var_560], r9
0x18007fddc  mov     r13d, r8d
0x18007fddf  mov     [rsp+780h+var_720], r8d
0x18007fde4  mov     rbx, rdx
0x18007fde7  mov     [rbp+680h+var_6D0], rdx
0x18007fdeb  mov     r15, rcx
0x18007fdee  mov     [rbp+680h+var_590], rcx
0x18007fdf5  xorps   xmm0, xmm0
0x18007fdf8  movups  xmmword ptr [rbp+680h+var_4F0.CallbackRoutine], xmm0
0x18007fdff  xorps   xmm1, xmm1
0x18007fe02  movups  [rbp+680h+var_558], xmm1
0x18007fe09  xor     r12d, r12d
0x18007fe0c  mov     [rbp+680h+var_690], r12
0x18007fe10  mov     [rbp+680h+var_688], r12
0x18007fe14  mov     [rbp+680h+var_680], r12
0x18007fe18  mov     [rbp+680h+var_678], r12b
0x18007fe1c  mov     [rbp+680h+var_6E8], 7FFFFFFFh
0x18007fe23  lea     rdi, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x18007fe2a  mov     [rbp+680h+var_700], rdi
0x18007fe2e  mov     [rbp+680h+var_6F8], r12
0x18007fe32  lea     esi, [r12+50h]
0x18007fe37  mov     r8d, esi; Size
0x18007fe3a  xor     edx, edx; Val
0x18007fe3c  lea     rcx, [rbp+680h+hObject]; void *
0x18007fe43  call    memset_0
0x18007fe48  lea     rax, ??_7CByteStreamAdapter@@6B@; const CByteStreamAdapter::`vftable'
0x18007fe4f  mov     [rbp+680h+var_548], rax
0x18007fe56  lea     rax, [rbp+680h+hObject]
0x18007fe5d  mov     [rbp+680h+var_540], rax
0x18007fe64  lea     rax, ??_7CIStreamAdapter@@6B@; const CIStreamAdapter::`vftable'
0x18007fe6b  mov     [rbp+680h+var_450], rax
0x18007fe72  mov     [rbp+680h+var_448], rbx
0x18007fe79  lea     ebx, [rsi-4Fh]
0x18007fe7c  mov     [rbp+680h+var_440], ebx
0x18007fe82  mov     [rbp+680h+var_6C8], rdi
0x18007fe86  mov     [rbp+680h+var_6C0], r12
0x18007fe8a  mov     [rbp+680h+var_6B8], rdi
0x18007fe8e  mov     [rbp+680h+var_6B0], r12
0x18007fe92  lea     rax, ??_7CBufferedWriteStream@@6B@; const CBufferedWriteStream::`vftable'
0x18007fe99  mov     [rbp+680h+hFile], rax
0x18007fea0  xorps   xmm0, xmm0
0x18007fea3  movdqu  [rbp+680h+var_470], xmm0
0x18007feab  movups  [rbp+680h+var_460], xmm0
0x18007feb2  xor     edx, edx; Val
0x18007feb4  lea     r8d, [r12+70h]; Size
0x18007feb9  lea     rcx, [rbp+680h+var_600]; void *
0x18007fec0  call    memset_0
0x18007fec5  mov     [rbp+680h+Process], r12
0x18007fecc  mov     [rbp+680h+var_6E0], r12
0x18007fed0  xor     edx, edx; Val
0x18007fed2  mov     r8d, 120h; Size
0x18007fed8  lea     rcx, [rbp+680h+var_170]; void *
0x18007fedf  call    memset_0
0x18007fee4  lea     edi, [rsi-8]
0x18007fee7  mov     r8d, edi; Size
0x18007feea  xor     edx, edx; Val
0x18007feec  lea     rcx, [rbp+680h+ppsmemCounters]; void *
0x18007fef3  call    memset_0
0x18007fef8  mov     r8d, edi; Size
0x18007fefb  xor     edx, edx; Val
0x18007fefd  lea     rcx, [rbp+680h+var_2B0]; void *
0x18007ff04  call    memset_0
0x18007ff09  mov     r8d, edi; Size
0x18007ff0c  xor     edx, edx; Val
0x18007ff0e  lea     rcx, [rbp+680h+var_210]; void *
0x18007ff15  call    memset_0
0x18007ff1a  mov     r8d, edi; Size
0x18007ff1d  xor     edx, edx; Val
0x18007ff1f  lea     rcx, [rbp+680h+var_1C0]; void *
0x18007ff26  call    memset_0
0x18007ff2b  xorps   xmm0, xmm0
0x18007ff2e  movups  xmmword ptr [rbp+680h+IoCounters.ReadOperationCount], xmm0
0x18007ff35  movups  xmmword ptr [rbp+680h+IoCounters.OtherOperationCount], xmm0
0x18007ff3c  movups  xmmword ptr [rbp+680h+IoCounters.WriteTransferCount], xmm0
0x18007ff43  xorps   xmm1, xmm1
0x18007ff46  movups  xmmword ptr [rbp+680h+var_310.ReadOperationCount], xmm1
0x18007ff4d  movups  xmmword ptr [rbp+680h+var_310.OtherOperationCount], xmm1
0x18007ff54  movups  xmmword ptr [rbp+680h+var_310.WriteTransferCount], xmm1
0x18007ff5b  mov     qword ptr [rbp+680h+PerformanceCount], r12
0x18007ff62  mov     qword ptr [rbp+680h+var_588], r12
0x18007ff69  mov     qword ptr [rbp+680h+Frequency], r12
0x18007ff6d  mov     [rbp+680h+CycleTime], r12
0x18007ff74  mov     [rbp+680h+var_570], r12
0x18007ff7b  cmp     [r15], r12d
0x18007ff7e  jnz     short loc_18007FF85
0x18007ff80  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007ff85  cmp     [r15+70h], r12
0x18007ff89  jnz     short loc_18007FF99
0x18007ff8b  cmp     [r15+300h], r12
0x18007ff92  jnz     short loc_18007FF99
0x18007ff94  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007ff99  cmp     [r15+78h], r12d
0x18007ff9d  jnz     short loc_18007FFA4
0x18007ff9f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007ffa4  mov     r8, rsi; Size
0x18007ffa7  xor     edx, edx; Val
0x18007ffa9  lea     rcx, [rbp+680h+var_670]; void *
0x18007ffad  call    memset_0
0x18007ffb2  movups  xmm0, [rbp+680h+var_670]
0x18007ffb6  movaps  xmmword ptr [rbp+680h+hObject], xmm0
0x18007ffbd  movups  xmm1, [rbp+680h+var_660]
0x18007ffc1  movaps  [rbp+680h+var_4C0], xmm1
0x18007ffc8  movups  xmm0, [rbp+680h+var_650]
0x18007ffcc  movaps  [rbp+680h+var_4B0], xmm0
0x18007ffd3  movups  xmm1, [rbp+680h+var_640]
0x18007ffd7  movaps  xmmword ptr [rbp+680h+lpBaseAddress], xmm1
0x18007ffde  movups  xmm0, [rbp+680h+var_630]
0x18007ffe2  movaps  [rbp+680h+var_490], xmm0
0x18007ffe9  mov     r14d, [r15+54h]
0x18007ffed  mov     [rsp+780h+var_708], r14d
0x18007fff2  test    dword ptr [r15+0B0h], 40000000h
0x18007fffd  jz      short loc_18008001A
0x18007ffff  cmp     [r15+44h], r12d
0x180080003  jnz     short loc_18008001A
0x180080005  cmp     dword ptr [r15+3Ch], 80000000h
0x18008000d  jnz     short loc_18008001A
0x18008000f  mov     [rsp+780h+var_718], ebx
0x180080013  mov     esi, 8
0x180080018  jmp     short loc_180080022
0x18008001a  mov     [rsp+780h+var_718], r12d
0x18008001f  mov     esi, r12d
0x180080022  mov     ebx, r12d
0x180080025  mov     [rsp+780h+var_704], ebx
0x180080029  mov     eax, 80000h
0x18008002e  cmp     dword ptr [r15+50h], 0FFFFFFFFh
0x180080033  cmovnz  eax, [r15+50h]
0x180080038  mov     [rbp+680h+var_6EC], eax
0x18008003b  call    IsXerTransportEventUploadCompletePresent
0x180080040  test    al, al
0x180080042  jz      short loc_18008005B
0x180080044  mov     rcx, [r15+10h]
0x180080048  add     rcx, 0C9E0h; this
0x18008004f  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180080054  test    eax, eax
0x180080056  mov     dil, 1
0x180080059  jnz     short loc_18008005E
0x18008005b  mov     dil, r12b
0x18008005e  mov     [rsp+780h+var_71C], dil
0x180080063  cmp     dword ptr [r15+48h], 0FFFFFFFFh
0x180080068  jz      short loc_180080078
0x18008006a  mov     ebx, r12d
0x18008006d  cmp     [r15+48h], r12d
0x180080071  setnz   bl
0x180080074  mov     [rsp+780h+var_704], ebx
0x180080078  test    r14d, r14d
0x18008007b  jz      loc_180080394
0x180080081  mov     rcx, r15; this
0x180080084  call    ?InitializeDumpEncryptor@CProcessDump@@AEAAJXZ; CProcessDump::InitializeDumpEncryptor(void)
0x180080089  mov     r12d, eax
0x18008008c  test    eax, eax
0x18008008e  jns     short loc_1800800AC
0x180080090  lea     r8, aFailedToInitia; "Failed to initialize dump encryptor: %0"...
0x180080097  mov     r9d, eax
0x18008009a  xor     edx, edx; unsigned int
0x18008009c  mov     rcx, r15; this
0x18008009f  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x1800800a4  xor     r14d, r14d
0x1800800a7  jmp     loc_180081202
0x1800800ac  xor     r12d, r12d
0x1800800af  test    dil, dil
0x1800800b2  jz      loc_180080327
0x1800800b8  mov     [rsp+780h+UserStreamParam], r12; struct _SECURITY_ATTRIBUTES *
0x1800800bd  mov     dword ptr [rsp+780h+ExceptionParam], 4000100h; unsigned int
0x1800800c5  xor     r9d, r9d; unsigned int
0x1800800c8  lea     r8, aUdf; ".udf"
0x1800800cf  lea     rdx, aWerTemp; "\\\\?\\Wer:\\Temp"
0x1800800d6  lea     rcx, [rbp+680h+var_700]; this
0x1800800da  call    ?CreateNew@CFileByteStream@@UEAAJPEB_W0KKPEAU_SECURITY_ATTRIBUTES@@@Z; CFileByteStream::CreateNew(wchar_t const *,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x1800800df  mov     [rbp+680h+var_6F0], 32h ; '2'
0x1800800e6  mov     ecx, [r15+0ACh]
0x1800800ed  test    ecx, ecx
0x1800800ef  jnz     short loc_180080106
0x1800800f1  mov     ecx, [r15+0D0h]
0x1800800f8  cmp     dword ptr [r15+0A8h], 3
0x180080100  jz      short loc_180080106
0x180080102  bts     ecx, 0Ah
0x180080106  mov     r13d, ecx
0x180080109  bts     r13d, 11h
0x18008010e  test    cl, 2
0x180080111  cmovz   r13d, ecx
0x180080115  and     r13d, 5FFFFFFh
0x18008011c  mov     eax, [r15+0C0h]
0x180080123  mov     dword ptr [rbp+680h+var_558], eax
0x180080129  lea     r12, [r15+720h]
0x180080130  mov     rax, [r12]
0x180080134  mov     qword ptr [rbp+680h+var_558+4], rax
0x18008013b  mov     eax, [r15+728h]
0x180080142  mov     dword ptr [rbp+680h+var_558+0Ch], eax
0x180080148  cmp     qword ptr [r15+8], 0
0x18008014d  jnz     short loc_180080154
0x18008014f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180080154  mov     rbx, [r15+8]
0x180080158  mov     rdi, [rbx+10h]
0x18008015c  test    rdi, rdi
0x18008015f  jz      loc_18008047D
0x180080165  xor     edx, edx; Val
0x180080167  lea     r8d, [rdx+70h]; Size
0x18008016b  lea     rcx, [rbp+680h+var_670]; void *
0x18008016f  call    memset_0
0x180080174  movups  xmm0, [rbp+680h+var_670]
0x180080178  movaps  [rbp+680h+var_600], xmm0
0x18008017f  movups  xmm1, [rbp+680h+var_660]
0x180080183  movaps  [rbp+680h+var_5F0], xmm1
0x18008018a  movups  xmm0, [rbp+680h+var_650]
0x18008018e  movaps  [rbp+680h+var_5E0], xmm0
0x180080195  movups  xmm1, [rbp+680h+var_640]
0x180080199  movaps  [rbp+680h+var_5D0], xmm1
0x1800801a0  movups  xmm0, [rbp+680h+var_630]
0x1800801a4  movaps  [rbp+680h+var_5C0], xmm0
0x1800801ab  movups  xmm1, [rbp+680h+var_620]
0x1800801af  movaps  [rbp+680h+var_5B0], xmm1
0x1800801b6  movups  xmm0, [rbp+680h+var_610]
0x1800801ba  movaps  [rbp+680h+var_5A0], xmm0
0x1800801c1  mov     qword ptr [rbp+680h+var_600], rbx
0x1800801c8  mov     dword ptr [rbp+680h+var_600+8], 13h
0x1800801d2  mov     rax, [rbx+40h]
0x1800801d6  mov     qword ptr [rbp+680h+var_5F0], rax
0x1800801dd  lea     rcx, [r15+0C8h]
0x1800801e4  mov     rax, [rcx+230h]
0x1800801eb  mov     qword ptr [rbp+680h+var_5F0+8], rax
0x1800801f2  mov     dword ptr [rbp+680h+var_5E0], r15d
0x1800801f9  mov     edx, dword ptr [rbp+680h+var_590+4]
0x1800801ff  mov     dword ptr [rbp+680h+var_5E0+4], edx
0x180080205  mov     eax, [r15+0A8h]
0x18008020c  mov     dword ptr [rbp+680h+var_5E0+8], eax
0x180080212  mov     dword ptr [rbp+680h+var_5E0+0Ch], r13d
0x180080219  mov     eax, [r15+0ACh]
0x180080220  mov     dword ptr [rbp+680h+var_5D0], eax
0x180080226  mov     eax, [r15+0B0h]
0x18008022d  mov     dword ptr [rbp+680h+var_5D0+4], eax
0x180080233  mov     eax, [r15+78h]
0x180080237  mov     dword ptr [rbp+680h+var_5D0+8], eax
0x18008023d  mov     eax, [r15+0C0h]
0x180080244  mov     dword ptr [rbp+680h+var_5D0+0Ch], eax
0x18008024a  mov     eax, [r15+7Ch]
0x18008024e  mov     dword ptr [rbp+680h+var_5C0], eax
0x180080254  mov     qword ptr [rbp+680h+var_5C0+8], rcx
0x18008025b  mov     qword ptr [rbp+680h+var_5B0], r12
0x180080262  lea     rax, ?static_vLogCallbackRoutine@CProcessDump@@CAXPEAXKPEB_WPEAD@Z; CProcessDump::static_vLogCallbackRoutine(void *,ulong,wchar_t const *,char *)
0x180080269  mov     qword ptr [rbp+680h+var_5B0+8], rax
0x180080270  mov     dword ptr [rbp+680h+var_5A0], r15d
0x180080277  mov     dword ptr [rbp+680h+var_5A0+4], edx
0x18008027d  xor     r8d, r8d
0x180080280  cmp     [r15+80h], r8d
0x180080287  setnz   r8b
0x18008028b  mov     eax, r14d
0x18008028e  neg     eax
0x180080290  sbb     edx, edx
0x180080292  and     edx, 4
0x180080295  or      r8d, edx
0x180080298  mov     r14d, [rsp+780h+var_720]
0x18008029d  mov     edx, r14d
0x1800802a0  shr     edx, 4
0x1800802a3  and     edx, 2
0x1800802a6  or      r8d, edx
0x1800802a9  or      r8d, esi
0x1800802ac  mov     dword ptr [rbp+680h+var_5A0+8], r8d
0x1800802b3  lea     rdx, [rbp+680h+var_600]
0x1800802ba  mov     rcx, [rbx+18h]
0x1800802be  mov     rax, rdi
0x1800802c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800802c6  xor     esi, esi
0x1800802c8  test    eax, eax
0x1800802ca  jz      loc_18008047F
0x1800802d0  mov     edx, dword ptr [rbp+680h+var_5A0+8]
0x1800802d6  mov     edi, edx
0x1800802d8  shr     edi, 1
0x1800802da  lea     ebx, [rsi+1]
0x1800802dd  and     edi, ebx
0x1800802df  shl     edi, 5
0x1800802e2  mov     eax, r14d
0x1800802e5  and     eax, 0FFFFFFDFh
0x1800802e8  or      edi, eax
0x1800802ea  mov     [rsp+780h+var_720], edi
0x1800802ee  mov     r14d, edx
0x1800802f1  shr     r14d, 2
0x1800802f5  and     r14d, ebx
0x1800802f8  mov     [rsp+780h+var_708], r14d
0x1800802fd  test    dl, 8
0x180080300  jz      loc_1800803D5
0x180080306  cmp     [r15+44h], esi
0x18008030a  jnz     loc_1800803D5
0x180080310  cmp     dword ptr [r15+3Ch], 80000000h
0x180080318  jnz     loc_1800803D5
0x18008031e  mov     [rsp+780h+var_718], ebx
0x180080322  jmp     loc_180080492
0x180080327  cmp     [r15+60h], r12
  ... truncated ...
```
