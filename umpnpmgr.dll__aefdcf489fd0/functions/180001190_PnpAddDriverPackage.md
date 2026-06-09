# PnpAddDriverPackage

- ea: `0x180001190`
- end: `0x180001ead`
- name: `PnpAddDriverPackage`
- size: `3357`
- prototype: `__int64 __fastcall(__int64, void *, void *, unsigned __int16, _WORD *, _DWORD *, __int64, void *Src, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800144b0`

## callees

- `0x1800010e0`
- `0x180001110`
- `0x180001190`
- `0x180001ec0`
- `0x1800024d0`
- `0x1800040f0`
- `0x180005540`
- `0x18000e810`
- `0x1800117d4`
- `0x180011964`
- `0x180013590`
- `0x180015498`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000138a`
- `msvcrt!wcsrchr` at `0x18000138a`
- `ntdll!RtlFreeHeap` at `0x180001e3f`
- `ntdll!RtlFreeHeap` at `0x180001e56`
- `ntdll!RtlFreeHeap` at `0x180001e3f`
- `ntdll!RtlFreeHeap` at `0x180001e56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180001b72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180001b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800012c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800012c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d8c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180001308`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180001308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001324`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000132f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001324`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000132f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e28`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001d3b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001d3b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180001b0e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180001b0e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180001bb2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180001bb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800012d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800012df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800012d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800012df`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180001351`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180001351`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180001e18`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180001e18`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800012b2`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800012b2`
- `DEVRTL!DevRtlWriteTextLog` at `0x18000128a`
- `DEVRTL!DevRtlWriteTextLog` at `0x180001a97`
- `DEVRTL!DevRtlWriteTextLog` at `0x180001c8f`
- `DEVRTL!DevRtlWriteTextLog` at `0x18000128a`
- `DEVRTL!DevRtlWriteTextLog` at `0x180001a97`
- `DEVRTL!DevRtlWriteTextLog` at `0x180001c8f`

## pseudocode

```c
__int64 __fastcall PnpAddDriverPackage(
        __int64 a1,
        void *a2,
        void *a3,
        unsigned __int16 a4,
        _WORD *a5,
        _DWORD *a6,
        __int64 a7,
        void *Src,
        unsigned int a9)
{
  void *v10; // r15
  WCHAR *v11; // r12
  void *v12; // r14
  HANDLE FileMappingW; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v15; // rax
  wchar_t *v16; // rax
  bool v17; // zf
  _WORD *v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  _WORD *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r14
  int v25; // eax
  __int64 v26; // r15
  _WORD *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rbx
  int v30; // eax
  int v31; // esi
  __int64 v32; // rdi
  _WORD *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rbx
  __int64 v38; // rax
  _WORD *v39; // r14
  int v40; // r9d
  int v41; // r9d
  int v42; // r9d
  int v43; // r9d
  int v44; // r9d
  int v45; // r9d
  int v46; // r9d
  int v47; // r9d
  int v48; // r9d
  int v49; // r9d
  int v50; // r9d
  int v51; // r9d
  int v52; // r9d
  int v53; // r9d
  int v54; // r9d
  int v55; // r9d
  int v56; // r9d
  int v57; // r9d
  int v58; // r9d
  int v59; // r9d
  int v60; // r9d
  int v61; // r9d
  int v62; // r9d
  int v63; // r9d
  __int64 v64; // rsi
  int v65; // r9d
  int v66; // r9d
  int v67; // r9d
  int v68; // r9d
  int v69; // r9d
  int v70; // r9d
  DWORD LastError; // eax
  HANDLE hProcess; // rdi
  DWORD v73; // eax
  DWORD v74; // eax
  _QWORD *v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r9
  LPCVOID v79; // r15
  _QWORD *v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rbx
  _WORD *v83; // rsi
  __int64 v84; // rbx
  DWORD v85; // eax
  char dwMaximumSizeLow; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowa; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowb; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowc; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowd; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowe; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowf; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowg; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowh; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowi; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowj; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowk; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowl; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowm; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLown; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowo; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowp; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowq; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowr; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLows; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowt; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowu; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowv; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLoww; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowx; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowy; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowz; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowba; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowbb; // [rsp+20h] [rbp-E0h]
  char dwMaximumSizeLowbc; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  LPCVOID lpBaseAddress; // [rsp+58h] [rbp-A8h]
  void *v119; // [rsp+60h] [rbp-A0h]
  __int64 v120; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v121; // [rsp+70h] [rbp-90h]
  unsigned int v122; // [rsp+74h] [rbp-8Ch]
  HANDLE TargetHandle; // [rsp+78h] [rbp-88h] BYREF
  __int64 v124; // [rsp+80h] [rbp-80h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-78h] BYREF
  _WORD *v126; // [rsp+A0h] [rbp-60h]
  __int64 v127; // [rsp+A8h] [rbp-58h]
  _WORD *v128; // [rsp+B0h] [rbp-50h]
  _DWORD *v129; // [rsp+B8h] [rbp-48h]
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v131[48]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t Str[264]; // [rsp+160h] [rbp+60h] BYREF

  v10 = a2;
  v120 = (__int64)a2;
  v127 = a1;
  v128 = a5;
  v129 = a6;
  v11 = 0;
  *(&StartupInfo.cb + 1) = 0;
  v12 = 0;
  v121 = a4;
  ExitCode = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  TargetHandle = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  v122 = *a6;
  *a5 = 0;
  *a6 = 1;
  DevRtlWriteTextLog(a7, 0x2000000, 4, "Import flags: 0x%08X", a9);
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 2 * v122, 0);
  if ( FileMappingW )
  {
    CurrentProcess = GetCurrentProcess();
    v15 = GetCurrentProcess();
    if ( !DuplicateHandle(v15, FileMappingW, CurrentProcess, &TargetHandle, 0, 1, 2u) )
    {
      TargetHandle = 0;
      ExitCode = GetLastError();
      CloseHandle(FileMappingW);
      goto LABEL_144;
    }
    CloseHandle(FileMappingW);
    lpBaseAddress = MapViewOfFile(TargetHandle, 0xF001Fu, 0, 0, 2 * v122);
    if ( lpBaseAddress )
    {
      if ( !(unsigned int)GetDeviceInstallerFilename(Str) )
      {
        ExitCode = GetLastError();
LABEL_142:
        v79 = lpBaseAddress;
LABEL_143:
        UnmapViewOfFile(v79);
        goto LABEL_144;
      }
      v16 = wcsrchr(Str, 0x5Cu);
      if ( v16 )
      {
        v17 = v16 + 1 == 0;
        v18 = v16 + 1;
        v126 = v18;
        if ( !v17 )
        {
          v19 = 0x7FFF;
          while ( *v18 )
          {
            ++v18;
            if ( !--v19 )
            {
              v124 = 0;
              v20 = -1073741811;
              goto LABEL_19;
            }
          }
          v124 = 0x7FFF - v19;
          v20 = 0;
LABEL_19:
          if ( v20 >= 0 )
          {
            v21 = StringSearchAndReplace(v10);
            v119 = (void *)v21;
            v12 = (void *)v21;
            if ( v21 )
            {
              v10 = (void *)v21;
              v120 = v21;
              goto LABEL_24;
            }
            ExitCode = GetLastError();
            if ( ExitCode )
              goto LABEL_142;
            if ( v10 )
            {
LABEL_24:
              v22 = v10;
              v23 = 260;
              while ( *v22 )
              {
                ++v22;
                if ( !--v23 )
                {
                  v24 = 0;
                  v25 = -1073741811;
                  goto LABEL_29;
                }
              }
              v24 = 260 - v23;
              v120 = (__int64)v10;
              v25 = 0;
LABEL_29:
              if ( v25 < 0 )
                goto LABEL_140;
              v26 = StringSearchAndReplace(Src);
              if ( !v26 )
              {
                ExitCode = GetLastError();
                if ( ExitCode )
                  goto LABEL_50;
                v26 = (__int64)Src;
                if ( !Src )
                  goto LABEL_140;
              }
              v27 = (_WORD *)v26;
              v28 = 522;
              while ( *v27 )
              {
                ++v27;
                if ( !--v28 )
                {
                  v29 = 0;
                  v30 = -1073741811;
                  goto LABEL_38;
                }
              }
              v29 = 522 - v28;
              v30 = 0;
LABEL_38:
              v31 = v120;
              if ( v30 < 0 )
                goto LABEL_140;
              v32 = StringSearchAndReplace(a3);
              if ( v32 )
                goto LABEL_42;
              ExitCode = GetLastError();
              if ( !ExitCode )
              {
                v32 = (__int64)a3;
                if ( a3 )
                {
LABEL_42:
                  v33 = (_WORD *)v32;
                  v34 = 260;
                  while ( *v33 )
                  {
                    ++v33;
                    if ( !--v34 )
                    {
                      v35 = 0;
                      v36 = -1073741811;
                      goto LABEL_47;
                    }
                  }
                  v35 = 260 - v34;
                  v36 = 0;
LABEL_47:
                  v120 = v35;
                  if ( v36 >= 0 )
                  {
                    v37 = v35 + 107 + v24 + v124 + v29;
                    v38 = PnpHeapAlloc(2 * v37);
                    v11 = (WCHAR *)v38;
                    if ( !v38 )
                    {
                      ExitCode = 8;
                      goto LABEL_50;
                    }
                    v39 = v126;
                    if ( (int)RtlStringCchCopyW(v38, v37, v126) < 0 )
                    {
                      v12 = v119;
                      ExitCode = 123;
                      goto LABEL_142;
                    }
                    if ( (int)RtlStringCchPrintfW(v131, 17, L"%lx", 4) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v40, dwMaximumSizeLow, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)v131, v41, dwMaximumSizeLowa, 2304) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v42, dwMaximumSizeLowb, 2048) >= 0
                      && (int)RtlStringCchPrintfW(v131, 17, L"%lx", a9) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v43, dwMaximumSizeLowc, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)v131, v44, dwMaximumSizeLowd, 2304) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v45, dwMaximumSizeLowe, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v46, dwMaximumSizeLowf, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, v31, v47, dwMaximumSizeLowg, 2304) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v48, dwMaximumSizeLowh, 2048) >= 0
                      && (int)RtlStringCchPrintfW(v131, 17, L"%hx", v121) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v49, dwMaximumSizeLowi, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)v131, v50, dwMaximumSizeLowj, 2304) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v51, dwMaximumSizeLowk, 2048) >= 0
                      && (int)RtlStringCchPrintfW(v131, 17, L"%I64x", a7) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v52, dwMaximumSizeLowl, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)v131, v53, dwMaximumSizeLowm, 2304) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v54, dwMaximumSizeLown, 2048) >= 0
                      && (int)RtlStringCchPrintfW(v131, 17, L"%p", v127) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v55, dwMaximumSizeLowo, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)v131, v56, dwMaximumSizeLowp, 2304) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v57, dwMaximumSizeLowq, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v58, dwMaximumSizeLowr, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, v26, v59, dwMaximumSizeLows, 2304) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v60, dwMaximumSizeLowt, 2048) >= 0
                      && (int)RtlStringCchPrintfW(v131, 17, L"%p", TargetHandle) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v61, dwMaximumSizeLowu, 2048) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)v131, v62, dwMaximumSizeLowv, 2304) >= 0
                      && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v63, dwMaximumSizeLoww, 2048) >= 0 )
                    {
                      v64 = v122;
                      if ( (int)RtlStringCchPrintfW(v131, 17, L"%lx", 2 * v122) >= 0
                        && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L" \"", v65, dwMaximumSizeLowx, 2048) >= 0
                        && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)v131, v66, dwMaximumSizeLowy, 2304) >= 0
                        && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v67, dwMaximumSizeLowz, 2048) >= 0
                        && (int)RtlStringCchCatExW(
                                  (_DWORD)v11,
                                  v37,
                                  (unsigned int)L" \"",
                                  v68,
                                  dwMaximumSizeLowba,
                                  2048) >= 0
                        && (int)RtlStringCchCatExW((_DWORD)v11, v37, v32, v69, dwMaximumSizeLowbb, 2304) >= 0
                        && (int)RtlStringCchCatExW((_DWORD)v11, v37, (unsigned int)L"\"", v70, dwMaximumSizeLowbc, 2048) >= 0 )
                      {
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
                        {
                          WPP_SF_S(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            11,
                            WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                            v11);
                        }
                        DevRtlWriteTextLog(a7, 0x2000000, 65542, "Creating process: %ws", v39);
                        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
                        memset_0(&StartupInfo, 0, sizeof(StartupInfo));
                        StartupInfo.cb = 104;
                        StartupInfo.lpDesktop = (LPWSTR)&qword_18001C3B0;
                        if ( !CreateProcessW(Str, v11, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
                        {
                          LastError = GetLastError();
                          ExitCode = LastError;
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              12,
                              WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                              LastError);
                          }
                          v12 = v119;
                          goto LABEL_142;
                        }
                        CloseHandle(ProcessInformation.hThread);
                        hProcess = ProcessInformation.hProcess;
                        v73 = WaitForSingleObjectEx(ProcessInformation.hProcess, 0xFFFFFFFF, 0);
                        if ( v73 )
                        {
                          if ( v73 == 258 )
                          {
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                16,
                                WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                258);
                            }
                            ExitCode = 1460;
                            if ( TerminateProcess(hProcess, 0x5B4u)
                              || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
                            {
                              goto LABEL_108;
                            }
                            v84 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                            v85 = GetLastError();
                            v76 = 17;
                            v78 = v85;
                            v77 = v84;
                            goto LABEL_107;
                          }
                          if ( v73 == -1 )
                          {
                            v74 = GetLastError();
                            ExitCode = v74;
                            v75 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
                            {
                              goto LABEL_108;
                            }
                            v76 = 18;
LABEL_106:
                            v77 = v75[2];
                            v78 = v74;
LABEL_107:
                            WPP_SF_d(v77, v76, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, v78);
LABEL_108:
                            v79 = lpBaseAddress;
LABEL_109:
                            if ( hProcess )
                              CloseHandle(hProcess);
                            v12 = v119;
                            goto LABEL_143;
                          }
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              19,
                              WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                              v73);
                          }
                          v79 = lpBaseAddress;
                        }
                        else
                        {
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                          {
                            WPP_SF_(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              13,
                              WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
                          }
                          if ( !GetExitCodeProcess(hProcess, &ExitCode) )
                          {
                            v74 = GetLastError();
                            ExitCode = v74;
                            v75 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
                            {
                              goto LABEL_108;
                            }
                            v76 = 14;
                            goto LABEL_106;
                          }
                          v80 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                          {
                            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                15,
                                WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                ExitCode);
                              v80 = WPP_GLOBAL_Control;
                            }
                            if ( v80 != &WPP_GLOBAL_Control && (*((_DWORD *)v80 + 7) & 0x40000) != 0 )
                              WPP_SF_d(v80[2], 20, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, ExitCode);
                          }
                          DevRtlWriteTextLog(
                            a7,
                            0x2000000,
                            65542,
                            "Driver store add process exited with code 0x%08x",
                            ExitCode);
                          if ( ExitCode && ExitCode != 3010 )
                            goto LABEL_108;
                          v79 = lpBaseAddress;
                          v81 = v64;
                          v82 = v64;
                          v83 = v128;
                          if ( (int)RtlStringCchCopyExW(v128, v81, lpBaseAddress) >= 0
                            && (int)RtlUnalignedStringCchLengthW(v83, v82, &v120) >= 0 )
                          {
                            *v129 = v120 + 1;
                            goto LABEL_109;
                          }
                        }
                        ExitCode = 13;
                        goto LABEL_109;
                      }
                    }
                  }
                }
LABEL_140:
                v12 = v119;
                goto LABEL_141;
              }
LABEL_50:
              v12 = v119;
              goto LABEL_142;
            }
          }
        }
      }
LABEL_141:
      ExitCode = 13;
      goto LABEL_142;
    }
  }
  ExitCode = GetLastError();
LABEL_144:
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v11 )
    RtlFreeHeap(PnpHeapHandle, 0, v11);
  if ( v12 )
    RtlFreeHeap(PnpHeapHandle, 0, v12);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  return ExitCode;
}

```

## disassembly

```asm
0x180001190  push    rbp
0x180001192  push    rbx
0x180001193  push    rsi
0x180001194  push    rdi
0x180001195  push    r12
0x180001197  push    r13
0x180001199  push    r14
0x18000119b  push    r15
0x18000119d  lea     rbp, [rsp-288h]
0x1800011a5  sub     rsp, 388h
0x1800011ac  mov     rax, cs:__security_cookie
0x1800011b3  xor     rax, rsp
0x1800011b6  mov     [rbp+2C0h+var_50], rax
0x1800011bd  mov     rdi, [rbp+2C0h+arg_20]
0x1800011c4  mov     r13, r8
0x1800011c7  mov     rbx, [rbp+2C0h+arg_28]
0x1800011ce  mov     r15, rdx
0x1800011d1  mov     rsi, [rbp+2C0h+Src]
0x1800011d8  xor     eax, eax
0x1800011da  mov     [rsp+3C0h+var_358], rdx
0x1800011df  mov     r8d, 64h ; 'd'; Size
0x1800011e5  mov     [rbp+2C0h+var_318], rcx
0x1800011e9  xor     edx, edx; Val
0x1800011eb  lea     rcx, [rbp+2C0h+StartupInfo]; void *
0x1800011ef  mov     [rbp+2C0h+var_310], rdi
0x1800011f3  mov     [rbp+2C0h+var_308], rbx
0x1800011f7  xor     r12d, r12d
0x1800011fa  mov     dword ptr [rbp+2C0h+StartupInfo+4], eax
0x1800011fd  xor     r14d, r14d
0x180001200  mov     [rsp+3C0h+var_350], r9w
0x180001206  mov     [rsp+3C0h+ExitCode], 0
0x18000120e  call    memset_0
0x180001213  xor     eax, eax
0x180001215  xorps   xmm0, xmm0
0x180001218  movups  xmmword ptr [rbp+2C0h+ProcessInformation.hProcess], xmm0
0x18000121c  mov     qword ptr [rbp+2C0h+ProcessInformation.dwProcessId], rax
0x180001220  mov     [rsp+3C0h+TargetHandle], rax
0x180001225  mov     rcx, cs:WPP_GLOBAL_Control
0x18000122c  lea     rax, WPP_GLOBAL_Control
0x180001233  cmp     rcx, rax
0x180001236  jz      short loc_180001256
0x180001238  test    dword ptr [rcx+1Ch], 10000000h
0x18000123f  jz      short loc_180001256
0x180001241  mov     rcx, [rcx+10h]
0x180001245  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x18000124c  mov     edx, 0Ah
0x180001251  call    WPP_SF_
0x180001256  mov     eax, [rbx]
0x180001258  lea     r9, aImportFlags0x0; "Import flags: 0x%08X"
0x18000125f  mov     rcx, [rbp+2C0h+arg_30]
0x180001266  mov     edx, 2000000h
0x18000126b  mov     [rsp+3C0h+var_34C], eax
0x18000126f  mov     r8d, 4
0x180001275  xor     eax, eax
0x180001277  mov     [rdi], ax
0x18000127a  mov     eax, [rbp+2C0h+arg_40]
0x180001280  mov     [rsp+3C0h+dwMaximumSizeLow], eax
0x180001284  mov     dword ptr [rbx], 1
0x18000128a  call    cs:__imp_DevRtlWriteTextLog
0x180001290  mov     ecx, [rsp+3C0h+var_34C]
0x180001294  xor     r9d, r9d; dwMaximumSizeHigh
0x180001297  mov     [rsp+3C0h+lpName], r12; lpName
0x18000129c  xor     edx, edx; lpFileMappingAttributes
0x18000129e  mov     r8d, 4; flProtect
0x1800012a4  lea     eax, [rcx+rcx]
0x1800012a7  mov     rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800012ae  mov     [rsp+3C0h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x1800012b2  call    cs:__imp_CreateFileMappingW
0x1800012b8  mov     rdi, rax
0x1800012bb  test    rax, rax
0x1800012be  jnz     short loc_1800012D6
0x1800012c0  call    cs:__imp_GetLastError
0x1800012c6  mov     [rsp+3C0h+ExitCode], eax
0x1800012ca  lea     r13, WPP_GLOBAL_Control
0x1800012d1  jmp     loc_180001E1E
0x1800012d6  call    cs:__imp_GetCurrentProcess
0x1800012dc  mov     rbx, rax
0x1800012df  call    cs:__imp_GetCurrentProcess
0x1800012e5  mov     [rsp+3C0h+dwOptions], 2; dwOptions
0x1800012ed  lea     r9, [rsp+3C0h+TargetHandle]; lpTargetHandle
0x1800012f2  mov     rcx, rax; hSourceProcessHandle
0x1800012f5  mov     dword ptr [rsp+3C0h+lpName], 1; bInheritHandle
0x1800012fd  mov     r8, rbx; hTargetProcessHandle
0x180001300  mov     [rsp+3C0h+dwMaximumSizeLow], r12d; dwDesiredAccess
0x180001305  mov     rdx, rdi; hSourceHandle
0x180001308  call    cs:__imp_DuplicateHandle
0x18000130e  test    eax, eax
0x180001310  jnz     short loc_18000132C
0x180001312  mov     [rsp+3C0h+TargetHandle], r12
0x180001317  call    cs:__imp_GetLastError
0x18000131d  mov     rcx, rdi; hObject
0x180001320  mov     [rsp+3C0h+ExitCode], eax
0x180001324  call    cs:__imp_CloseHandle
0x18000132a  jmp     short loc_1800012CA
0x18000132c  mov     rcx, rdi; hObject
0x18000132f  call    cs:__imp_CloseHandle
0x180001335  mov     edx, [rsp+3C0h+var_34C]
0x180001339  xor     r9d, r9d; dwFileOffsetLow
0x18000133c  mov     rcx, [rsp+3C0h+TargetHandle]; hFileMappingObject
0x180001341  xor     r8d, r8d; dwFileOffsetHigh
0x180001344  lea     eax, [rdx+rdx]
0x180001347  mov     edx, 0F001Fh; dwDesiredAccess
0x18000134c  mov     qword ptr [rsp+3C0h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x180001351  call    cs:__imp_MapViewOfFile
0x180001357  mov     [rsp+3C0h+lpBaseAddress], rax
0x18000135c  test    rax, rax
0x18000135f  jz      loc_1800012C0
0x180001365  lea     rcx, [rbp+2C0h+Str]
0x180001369  call    GetDeviceInstallerFilename
0x18000136e  test    eax, eax
0x180001370  jnz     short loc_180001381
0x180001372  call    cs:__imp_GetLastError
0x180001378  mov     [rsp+3C0h+ExitCode], eax
0x18000137c  jmp     loc_180001E09
0x180001381  mov     edx, 5Ch ; '\'; Ch
0x180001386  lea     rcx, [rbp+2C0h+Str]; Str
0x18000138a  call    cs:__imp_wcsrchr
0x180001390  test    rax, rax
0x180001393  jz      loc_180001E01
0x180001399  add     rax, 2
0x18000139d  mov     [rbp+2C0h+var_320], rax
0x1800013a1  jz      loc_180001E01
0x1800013a7  mov     edx, 7FFFh
0x1800013ac  mov     ecx, edx
0x1800013ae  xchg    ax, ax
0x1800013b0  cmp     [rax], r12w
0x1800013b4  jz      short loc_1800013CD
0x1800013b6  add     rax, 2
0x1800013ba  sub     rcx, 1
0x1800013be  jnz     short loc_1800013B0
0x1800013c0  mov     edi, 0C000000Dh
0x1800013c5  mov     [rbp+2C0h+var_340], r12
0x1800013c9  mov     eax, edi
0x1800013cb  jmp     short loc_1800013DB
0x1800013cd  sub     rdx, rcx
0x1800013d0  mov     edi, 0C000000Dh
0x1800013d5  mov     [rbp+2C0h+var_340], rdx
0x1800013d9  xor     eax, eax
0x1800013db  test    eax, eax
0x1800013dd  js      loc_180001E01
0x1800013e3  mov     rcx, r15; Src
0x1800013e6  call    StringSearchAndReplace
0x1800013eb  mov     [rsp+3C0h+var_360], rax
0x1800013f0  mov     r14, rax
0x1800013f3  test    rax, rax
0x1800013f6  jz      short loc_180001402
0x1800013f8  mov     r15, rax
0x1800013fb  mov     [rsp+3C0h+var_358], rax
0x180001400  jmp     short loc_18000141D
0x180001402  call    cs:__imp_GetLastError
0x180001408  mov     [rsp+3C0h+ExitCode], eax
0x18000140c  test    eax, eax
0x18000140e  jnz     loc_180001E09
0x180001414  test    r15, r15
0x180001417  jz      loc_180001E01
0x18000141d  mov     r14d, 104h
0x180001423  mov     rax, r15
0x180001426  mov     ecx, r14d
0x180001429  nop     dword ptr [rax+00000000h]
0x180001430  cmp     [rax], r12w
0x180001434  jz      short loc_180001447
0x180001436  add     rax, 2
0x18000143a  sub     rcx, 1
0x18000143e  jnz     short loc_180001430
0x180001440  xor     r14d, r14d
0x180001443  mov     eax, edi
0x180001445  jmp     short loc_180001451
0x180001447  sub     r14, rcx
0x18000144a  mov     [rsp+3C0h+var_358], r15
0x18000144f  xor     eax, eax
0x180001451  test    eax, eax
0x180001453  js      loc_180001DFC
0x180001459  mov     rcx, rsi; Src
0x18000145c  call    StringSearchAndReplace
0x180001461  mov     r15, rax
0x180001464  test    rax, rax
0x180001467  jnz     short loc_180001487
0x180001469  call    cs:__imp_GetLastError
0x18000146f  mov     [rsp+3C0h+ExitCode], eax
0x180001473  test    eax, eax
0x180001475  jnz     loc_180001542
0x18000147b  mov     r15, rsi
0x18000147e  test    rsi, rsi
0x180001481  jz      loc_180001DFC
0x180001487  mov     ebx, 20Ah
0x18000148c  mov     rax, r15
0x18000148f  mov     ecx, ebx
0x180001491  cmp     [rax], r12w
0x180001495  jz      short loc_1800014A7
0x180001497  add     rax, 2
0x18000149b  sub     rcx, 1
0x18000149f  jnz     short loc_180001491
0x1800014a1  xor     ebx, ebx
0x1800014a3  mov     eax, edi
0x1800014a5  jmp     short loc_1800014AC
0x1800014a7  sub     rbx, rcx
0x1800014aa  xor     eax, eax
0x1800014ac  mov     rsi, [rsp+3C0h+var_358]
0x1800014b1  test    eax, eax
0x1800014b3  js      loc_180001DFC
0x1800014b9  mov     rcx, r13; Src
0x1800014bc  call    StringSearchAndReplace
0x1800014c1  mov     rdi, rax
0x1800014c4  test    rax, rax
0x1800014c7  jnz     short loc_1800014E3
0x1800014c9  call    cs:__imp_GetLastError
0x1800014cf  mov     [rsp+3C0h+ExitCode], eax
0x1800014d3  test    eax, eax
0x1800014d5  jnz     short loc_180001542
0x1800014d7  mov     rdi, r13
0x1800014da  test    r13, r13
0x1800014dd  jz      loc_180001DFC
0x1800014e3  mov     edx, 104h
0x1800014e8  mov     rax, rdi
0x1800014eb  mov     ecx, edx
0x1800014ed  nop     dword ptr [rax]
0x1800014f0  cmp     [rax], r12w
0x1800014f4  jz      short loc_180001509
0x1800014f6  add     rax, 2
0x1800014fa  sub     rcx, 1
0x1800014fe  jnz     short loc_1800014F0
0x180001500  xor     edx, edx
0x180001502  mov     eax, 0C000000Dh
0x180001507  jmp     short loc_18000150E
0x180001509  sub     rdx, rcx
0x18000150c  xor     eax, eax
0x18000150e  mov     [rsp+3C0h+var_358], rdx
0x180001513  test    eax, eax
0x180001515  js      loc_180001DFC
0x18000151b  add     rbx, [rbp+2C0h+var_340]
0x18000151f  add     rdx, 6Bh ; 'k'
0x180001523  add     rbx, r14
0x180001526  add     rbx, rdx
0x180001529  lea     rcx, [rbx+rbx]
0x18000152d  call    PnpHeapAlloc
0x180001532  mov     r12, rax
0x180001535  test    rax, rax
0x180001538  jnz     short loc_18000154C
0x18000153a  mov     [rsp+3C0h+ExitCode], 8
0x180001542  mov     r14, [rsp+3C0h+var_360]
0x180001547  jmp     loc_180001E09
0x18000154c  mov     r14, [rbp+2C0h+var_320]
0x180001550  mov     rdx, rbx
0x180001553  mov     r8, r14
0x180001556  mov     rcx, r12
0x180001559  call    RtlStringCchCopyW
0x18000155e  test    eax, eax
0x180001560  jns     short loc_180001574
0x180001562  mov     r14, [rsp+3C0h+var_360]
0x180001567  mov     [rsp+3C0h+ExitCode], 7Bh ; '{'
0x18000156f  jmp     loc_180001E09
0x180001574  mov     r9d, 4
0x18000157a  lea     r8, aLx; "%lx"
0x180001581  mov     edx, 11h
0x180001586  lea     rcx, [rbp+2C0h+var_290]
0x18000158a  call    RtlStringCchPrintfW
0x18000158f  test    eax, eax
0x180001591  js      loc_180001DFC
0x180001597  lea     r8, asc_18001C3A8; " \""
0x18000159e  mov     dword ptr [rsp+3C0h+lpName], 800h
0x1800015a6  mov     rdx, rbx
0x1800015a9  mov     rcx, r12
0x1800015ac  call    RtlStringCchCatExW
0x1800015b1  test    eax, eax
0x1800015b3  js      loc_180001DFC
0x1800015b9  lea     r8, [rbp+2C0h+var_290]
0x1800015bd  mov     dword ptr [rsp+3C0h+lpName], 900h
0x1800015c5  mov     rdx, rbx
0x1800015c8  mov     rcx, r12
0x1800015cb  call    RtlStringCchCatExW
0x1800015d0  test    eax, eax
0x1800015d2  js      loc_180001DFC
0x1800015d8  lea     r8, SubStr; "\""
0x1800015df  mov     dword ptr [rsp+3C0h+lpName], 800h
0x1800015e7  mov     rdx, rbx
0x1800015ea  mov     rcx, r12
0x1800015ed  call    RtlStringCchCatExW
0x1800015f2  test    eax, eax
0x1800015f4  js      loc_180001DFC
0x1800015fa  mov     r9d, [rbp+2C0h+arg_40]
0x180001601  lea     r8, aLx; "%lx"
0x180001608  mov     edx, 11h
0x18000160d  lea     rcx, [rbp+2C0h+var_290]
0x180001611  call    RtlStringCchPrintfW
0x180001616  test    eax, eax
0x180001618  js      loc_180001DFC
0x18000161e  lea     r8, asc_18001C3A8; " \""
0x180001625  mov     dword ptr [rsp+3C0h+lpName], 800h
0x18000162d  mov     rdx, rbx
0x180001630  mov     rcx, r12
0x180001633  call    RtlStringCchCatExW
0x180001638  test    eax, eax
0x18000163a  js      loc_180001DFC
0x180001640  lea     r8, [rbp+2C0h+var_290]
0x180001644  mov     dword ptr [rsp+3C0h+lpName], 900h
0x18000164c  mov     rdx, rbx
0x18000164f  mov     rcx, r12
0x180001652  call    RtlStringCchCatExW
0x180001657  test    eax, eax
0x180001659  js      loc_180001DFC
  ... truncated ...
```
