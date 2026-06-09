# PnpInstallDriver

- ea: `0x1800027a0`
- end: `0x1800040e5`
- name: `PnpInstallDriver`
- size: `6469`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *, const wchar_t *Src, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000bc30`

## callees

- `0x1800024d0`
- `0x180002750`
- `0x1800027a0`
- `0x1800040f0`
- `0x180005540`
- `0x18000b360`
- `0x18000f5a0`
- `0x18000f82c`
- `0x18001002c`
- `0x1800101e8`
- `0x1800104d8`
- `0x1800117d4`
- `0x180011964`
- `0x1800132c0`
- `0x180013590`
- `0x18001621c`
- `0x1800167b0`
- `0x180016818`
- `0x180016cac`
- `0x180016d84`
- `0x180017058`
- `0x1800171b8`
- `0x18001725c`
- `0x180017408`
- `0x1800177e0`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800028d6`
- `msvcrt!wcsrchr` at `0x1800028d6`
- `ntdll!RtlFreeHeap` at `0x18000409c`
- `ntdll!RtlFreeHeap` at `0x1800040b3`
- `ntdll!RtlFreeHeap` at `0x18000409c`
- `ntdll!RtlFreeHeap` at `0x1800040b3`
- `ntdll!RtlAllocateHeap` at `0x180002a00`
- `ntdll!RtlAllocateHeap` at `0x180002a00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800038c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800038c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002b40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002b40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004085`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180003f47`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180003f47`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800038a2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800038a2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800038ef`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800038ef`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800028b0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180003e93`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800028b0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180003e93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b59`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x1800028a2`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x1800028a2`
- `DEVRTL!DevRtlWriteTextLog` at `0x180002899`
- `DEVRTL!DevRtlWriteTextLog` at `0x180002be2`
- `DEVRTL!DevRtlWriteTextLog` at `0x18000382f`
- `DEVRTL!DevRtlWriteTextLog` at `0x180003e81`
- `DEVRTL!DevRtlWriteTextLog` at `0x180002899`
- `DEVRTL!DevRtlWriteTextLog` at `0x180002be2`
- `DEVRTL!DevRtlWriteTextLog` at `0x18000382f`
- `DEVRTL!DevRtlWriteTextLog` at `0x180003e81`

## string_xrefs

- `0x180002bc9`: `{Plug and Play Service: Driver Install exit(%08x)}`
- `0x18000287f`: `{Plug and Play Service: Driver Install for %ws}`
- `0x180003810`: `Creating Install Process: %ws`
- `0x180003e68`: `Server install process exited with code 0x%08x`
- `0x180003ae7`: `Driver Install`

## pseudocode

```c
__int64 __fastcall PnpInstallDriver(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        const wchar_t *Src,
        unsigned int a6,
        _DWORD *a7)
{
  const WCHAR *v7; // rdi
  LPWSTR v8; // r13
  const WCHAR *v9; // r14
  wchar_t *v10; // rax
  bool v11; // zf
  WCHAR *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r14
  int v15; // eax
  void *v16; // rax
  const WCHAR *v17; // rbx
  __int64 v18; // rcx
  const WCHAR *v19; // rax
  __int64 v20; // rdi
  int v21; // eax
  WCHAR *v22; // r13
  __int64 v23; // r8
  WCHAR *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  unsigned __int64 v28; // r14
  __int64 v29; // r12
  WCHAR *Heap; // rax
  WCHAR *v31; // rdi
  WCHAR *v32; // rdx
  __int64 v33; // r15
  __int64 v34; // rcx
  unsigned __int64 v35; // r8
  WCHAR *v36; // r9
  WCHAR *v37; // rcx
  unsigned __int64 v38; // rcx
  WCHAR *v39; // rax
  unsigned __int64 v40; // r10
  int v41; // eax
  DWORD v42; // ebx
  const WCHAR *v43; // r14
  void *hProcess; // r15
  DWORD v45; // esi
  unsigned __int64 v47; // rdx
  const wchar_t *v48; // rsi
  __int64 v49; // rcx
  const wchar_t *v50; // r8
  WCHAR *v51; // r9
  WCHAR *v52; // rcx
  unsigned __int64 v53; // rcx
  WCHAR *v54; // rax
  int v55; // eax
  unsigned __int64 v56; // rdx
  __int64 v57; // rcx
  WCHAR *v58; // r8
  WCHAR *v59; // r9
  WCHAR *v60; // rcx
  unsigned __int64 v61; // rcx
  WCHAR *v62; // rax
  int v63; // eax
  unsigned __int64 v64; // rdx
  const wchar_t *v65; // rbx
  __int64 v66; // rcx
  const wchar_t *v67; // r8
  WCHAR *v68; // r9
  WCHAR *v69; // rcx
  unsigned __int64 v70; // rcx
  LPWSTR v71; // rax
  unsigned __int64 v72; // r10
  int v73; // eax
  unsigned __int64 v74; // rdx
  __int64 v75; // rcx
  WCHAR *v76; // r9
  const wchar_t *v77; // r8
  WCHAR *v78; // rcx
  LPWSTR v79; // r9
  unsigned __int64 v80; // rcx
  LPWSTR v81; // rax
  int v82; // eax
  unsigned __int64 v83; // r10
  int v84; // eax
  unsigned __int64 v85; // rdx
  __int64 v86; // rcx
  WCHAR *v87; // r9
  const wchar_t *v88; // r8
  WCHAR *v89; // rcx
  WCHAR *v90; // r11
  unsigned __int64 v91; // rdx
  __int64 v92; // rcx
  WCHAR *v93; // r8
  WCHAR *v94; // rcx
  LPWSTR v95; // r11
  unsigned __int64 v96; // rcx
  LPWSTR v97; // rax
  unsigned __int64 v98; // r10
  int v99; // eax
  unsigned __int64 v100; // rdx
  __int64 v101; // rcx
  WCHAR *v102; // r8
  WCHAR *v103; // r9
  WCHAR *v104; // rcx
  unsigned __int64 v105; // rcx
  LPWSTR v106; // rax
  int v107; // eax
  unsigned __int64 v108; // rdx
  __int64 v109; // rcx
  WCHAR *v110; // r9
  const wchar_t *v111; // r8
  WCHAR *v112; // rcx
  unsigned __int64 v113; // rcx
  LPWSTR v114; // rax
  unsigned __int64 v115; // rdx
  __int64 v116; // rcx
  WCHAR *v117; // r9
  const wchar_t *v118; // r8
  WCHAR *v119; // rcx
  unsigned __int64 v120; // rcx
  LPWSTR v121; // rax
  int v122; // eax
  unsigned __int64 v123; // rdx
  __int64 v124; // rcx
  WCHAR *v125; // r9
  const wchar_t *v126; // r8
  WCHAR *v127; // rcx
  unsigned __int64 v128; // rcx
  LPWSTR v129; // rax
  int v130; // eax
  unsigned __int64 v131; // rdx
  __int64 v132; // rcx
  WCHAR *v133; // r8
  WCHAR *v134; // r9
  WCHAR *v135; // rcx
  unsigned __int64 v136; // rcx
  LPWSTR v137; // rax
  int v138; // eax
  unsigned __int64 v139; // rdx
  __int64 v140; // rcx
  WCHAR *v141; // r9
  const wchar_t *v142; // r8
  WCHAR *v143; // rcx
  unsigned __int64 v144; // rcx
  LPWSTR v145; // rax
  int v146; // eax
  unsigned __int64 v147; // rdx
  __int64 v148; // rcx
  WCHAR *v149; // r9
  const wchar_t *v150; // r8
  WCHAR *v151; // rcx
  unsigned __int64 v152; // rdx
  __int64 v153; // rcx
  WCHAR *v154; // r8
  WCHAR *v155; // r9
  WCHAR *v156; // rcx
  unsigned __int64 v157; // rcx
  LPWSTR v158; // rax
  int v159; // eax
  unsigned __int64 v160; // rdx
  __int64 v161; // rcx
  WCHAR *v162; // r9
  const wchar_t *v163; // r8
  WCHAR *v164; // rcx
  unsigned __int64 v165; // rcx
  LPWSTR v166; // rax
  int v167; // eax
  unsigned __int64 v168; // rdx
  __int64 v169; // rcx
  WCHAR *v170; // r8
  const wchar_t *v171; // r9
  WCHAR *v172; // rcx
  unsigned __int64 v173; // rcx
  LPWSTR v174; // rax
  int v175; // eax
  unsigned __int64 v176; // rdx
  __int64 v177; // rcx
  WCHAR *v178; // r9
  WCHAR *v179; // r8
  WCHAR *v180; // rcx
  unsigned __int64 v181; // rcx
  LPWSTR v182; // rax
  int v183; // eax
  unsigned __int64 v184; // rdx
  __int64 v185; // rcx
  WCHAR *v186; // r8
  const wchar_t *v187; // r9
  WCHAR *v188; // rcx
  unsigned __int64 v189; // rcx
  LPWSTR v190; // rax
  int v191; // eax
  unsigned __int64 v192; // rdx
  __int64 v193; // rcx
  WCHAR *v194; // r8
  WCHAR *v195; // rcx
  unsigned __int64 v196; // rdx
  __int64 v197; // r8
  WCHAR *v198; // rax
  WCHAR *v199; // rcx
  unsigned __int64 v200; // rcx
  LPWSTR v201; // rax
  unsigned __int64 v202; // r8
  int v203; // eax
  unsigned __int64 v204; // r14
  bool v205; // cf
  WCHAR *v206; // rax
  WCHAR *v207; // rcx
  DWORD v208; // eax
  DWORD v209; // eax
  _QWORD *v210; // rcx
  __int64 v211; // rdx
  __int64 *v212; // rdi
  int v213; // r8d
  DWORD v214; // eax
  unsigned int v215; // eax
  void *v216; // rbx
  DWORD LastError; // edi
  __int64 v218; // rax
  __int64 v219; // rdx
  void *v220; // rsi
  DWORD v221; // eax
  _QWORD *v222; // rcx
  unsigned __int64 v223; // rbx
  __int64 v224; // rbx
  DWORD v225; // eax
  int LogStatus; // ebx
  int dwCreationFlags; // [rsp+30h] [rbp-D8h]
  int dwCreationFlagsa; // [rsp+30h] [rbp-D8h]
  DWORD ExitCode[2]; // [rsp+58h] [rbp-B0h] BYREF
  LPWSTR lpCommandLine; // [rsp+60h] [rbp-A8h]
  const WCHAR *v231; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v232; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v233; // [rsp+78h] [rbp-90h] BYREF
  const WCHAR *v234; // [rsp+80h] [rbp-88h]
  HANDLE hObject; // [rsp+88h] [rbp-80h]
  unsigned int v236; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+98h] [rbp-70h] BYREF
  WCHAR *v238; // [rsp+A0h] [rbp-68h]
  const WCHAR *v239; // [rsp+A8h] [rbp-60h]
  PVOID P; // [rsp+B0h] [rbp-58h]
  __int128 v241; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v242; // [rsp+C8h] [rbp-40h]
  __int128 v243; // [rsp+D8h] [rbp-30h]
  __int64 v244; // [rsp+E8h] [rbp-20h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v246; // [rsp+108h] [rbp+0h] BYREF
  int v247; // [rsp+118h] [rbp+10h]
  struct _STARTUPINFOW StartupInfo; // [rsp+128h] [rbp+20h] BYREF
  _WORD v249[24]; // [rsp+198h] [rbp+90h] BYREF
  wchar_t Str[264]; // [rsp+1C8h] [rbp+C0h] BYREF

  v7 = (const WCHAR *)a2;
  v8 = 0;
  v9 = a4;
  v234 = a4;
  v239 = (const WCHAR *)a2;
  v232 = a1;
  v231 = a4;
  v233 = a7;
  ExitCode[0] = 0;
  lpCommandLine = 0;
  P = 0;
  hObject = 0;
  memset(&StartupInfo, 0, 100);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  if ( a7 )
    *a7 = 0;
  v236 = 0;
  if ( v9 )
  {
    DevRtlWriteTextLog(v9, 0x2000000, 131076, "{Plug and Play Service: Driver Install for %ws}", v7);
  }
  else
  {
    v216 = 0;
    if ( !v7 || (v216 = (void *)pSetupUnicodeToMultiByte(v7)) != 0 )
    {
      v218 = pSetupUnicodeToMultiByte(L"Driver Install");
      v220 = (void *)v218;
      if ( v218 )
      {
        LastError = 0;
        v236 = pSetupCreateTextLogSectionA(v216, v219, v218, &v231);
        if ( !v236 )
          LastError = GetLastError();
        v9 = v231;
        v234 = v231;
      }
      else
      {
        LastError = 8;
      }
      if ( v216 )
        HeapFree(hHeap, 0, v216);
      if ( v220 )
        HeapFree(hHeap, 0, v220);
    }
    else
    {
      LastError = 8;
    }
    SetLastError(LastError);
    v7 = v239;
  }
  DevRtlSetThreadLogToken(v9);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( !GetDeviceInstallerFilename(Str) )
  {
    v42 = GetLastError();
    ExitCode[0] = v42;
    goto LABEL_386;
  }
  v10 = wcsrchr(Str, 0x5Cu);
  if ( !v10 )
    goto LABEL_365;
  v11 = v10 + 1 == 0;
  v12 = v10 + 1;
  v238 = v12;
  if ( v11 )
    goto LABEL_365;
  v13 = 0x7FFF;
  while ( *v12 )
  {
    ++v12;
    if ( !--v13 )
    {
      v14 = 0;
      v15 = -1073741811;
      goto LABEL_14;
    }
  }
  v15 = 0;
  v14 = 0x7FFF - v13;
LABEL_14:
  if ( v15 < 0 )
    goto LABEL_365;
  v16 = StringSearchAndReplace(v7);
  P = v16;
  if ( v16 )
  {
    v17 = (const WCHAR *)v16;
    v231 = (const WCHAR *)v16;
    goto LABEL_17;
  }
  ExitCode[0] = GetLastError();
  v42 = ExitCode[0];
  if ( ExitCode[0] )
  {
LABEL_386:
    v43 = v234;
    hProcess = 0;
    goto LABEL_51;
  }
  v17 = v7;
  v231 = v7;
  if ( !v7 )
  {
LABEL_365:
    v43 = v234;
    v42 = 13;
    hProcess = 0;
    ExitCode[0] = 13;
    goto LABEL_51;
  }
LABEL_17:
  v18 = 260;
  v19 = v17;
  while ( *v19 )
  {
    ++v19;
    if ( !--v18 )
    {
      v20 = 0;
      v21 = -1073741811;
      goto LABEL_22;
    }
  }
  v20 = 260 - v18;
  v231 = v17;
  v21 = 0;
LABEL_22:
  if ( v21 < 0 )
    goto LABEL_365;
  v22 = (WCHAR *)StringSearchAndReplace(Src);
  if ( v22 )
  {
    v23 = v14 + v20;
  }
  else
  {
    ExitCode[0] = GetLastError();
    v42 = ExitCode[0];
    if ( ExitCode[0] )
      goto LABEL_369;
    v22 = (WCHAR *)Src;
    if ( !Src )
    {
LABEL_368:
      v42 = 13;
      ExitCode[0] = 13;
LABEL_369:
      v8 = lpCommandLine;
      v43 = v234;
      hProcess = lpCommandLine;
      goto LABEL_51;
    }
    v17 = v231;
    v23 = v14 + v20;
  }
  v24 = v22;
  v25 = 522;
  while ( *v24 )
  {
    ++v24;
    if ( !--v25 )
    {
      v26 = 0;
      v27 = -1073741811;
      goto LABEL_30;
    }
  }
  v26 = 522 - v25;
  v231 = v17;
  v27 = 0;
LABEL_30:
  if ( v27 < 0 )
    goto LABEL_368;
  v28 = v23 + v26 + 74;
  v29 = 2 * v28;
  if ( 2 * v28 > 0xF42400 )
  {
    v8 = 0;
LABEL_393:
    v43 = v234;
    hProcess = hObject;
    v42 = 8;
    ExitCode[0] = 8;
    goto LABEL_51;
  }
  Heap = (WCHAR *)RtlAllocateHeap(PnpHeapHandle, 8u, 2 * v28);
  lpCommandLine = Heap;
  v31 = Heap;
  if ( !Heap )
  {
    v8 = 0;
    goto LABEL_393;
  }
  if ( !v28 )
  {
LABEL_395:
    v42 = 123;
    goto LABEL_50;
  }
  if ( v28 > 0x7FFFFFFF )
  {
    *Heap = 0;
    goto LABEL_395;
  }
  v32 = v238;
  v33 = 2147483646;
  v34 = 2147483646;
  v35 = v28;
  v36 = Heap;
  do
  {
    if ( !v34 )
      break;
    if ( !*v32 )
      break;
    *v36++ = *v32++;
    --v34;
    --v35;
  }
  while ( v35 );
  v37 = v36 - 1;
  if ( v35 )
    v37 = v36;
  *v37 = 0;
  if ( !v35 )
    goto LABEL_395;
  if ( (int)RtlStringCchPrintfW(v249, 17, L"%lx", 8) < 0 )
    goto LABEL_49;
  v38 = v28;
  v39 = v31;
  while ( *v39 )
  {
    ++v39;
    if ( !--v38 )
    {
      v40 = 0;
      v41 = -1073741811;
      goto LABEL_48;
    }
  }
  v231 = v17;
  v40 = v28 - v38;
  v41 = 0;
LABEL_48:
  if ( v41 < 0 )
    goto LABEL_49;
  v47 = v28 - v40;
  if ( v28 - v40 <= 1 )
    goto LABEL_397;
  v48 = L" \"";
  v49 = 2147483646;
  v50 = L" \"";
  v51 = &v31[v40];
  do
  {
    if ( !v49 )
      break;
    if ( !*v50 )
      break;
    *v51++ = *v50++;
    --v49;
    --v47;
  }
  while ( v47 );
  v52 = v51 - 1;
  if ( v47 )
    v52 = v51;
  *v52 = 0;
  if ( !v47 )
    goto LABEL_397;
  v53 = v28;
  v54 = v31;
  while ( *v54 )
  {
    ++v54;
    if ( !--v53 )
    {
      v40 = 0;
      v55 = -1073741811;
      goto LABEL_78;
    }
  }
  v231 = v17;
  v40 = v28 - v53;
  v55 = 0;
LABEL_78:
  if ( v55 < 0 )
    goto LABEL_49;
  v56 = v28 - v40;
  if ( v28 - v40 <= 1 )
  {
    if ( v249[0] )
      goto LABEL_397;
  }
  else
  {
    v57 = 2147483646;
    v58 = v249;
    v59 = &v31[v40];
    do
    {
      if ( !v57 )
        break;
      if ( !*v58 )
        break;
      *v59++ = *v58++;
      --v57;
      --v56;
    }
    while ( v56 );
    v60 = v59 - 1;
    if ( v56 )
      v60 = v59;
    *v60 = 0;
    if ( !v56 )
      goto LABEL_397;
  }
  v61 = v28;
  v62 = v31;
  while ( *v62 )
  {
    ++v62;
    if ( !--v61 )
    {
      v40 = 0;
      v63 = -1073741811;
      goto LABEL_92;
    }
  }
  v231 = v17;
  v40 = v28 - v61;
  v63 = 0;
LABEL_92:
  if ( v63 < 0 )
    goto LABEL_49;
  v64 = v28 - v40;
  if ( v28 - v40 <= 1 )
    goto LABEL_397;
  v65 = L"\"";
  v66 = 2147483646;
  v67 = L"\"";
  v68 = &v31[v40];
  do
  {
    if ( !v66 )
      break;
    if ( !*v67 )
      break;
    *v68++ = *v67++;
    --v66;
    --v64;
  }
  while ( v64 );
  v69 = v68 - 1;
  if ( v64 )
    v69 = v68;
  *v69 = 0;
  if ( !v64 )
  {
LABEL_397:
    RtlStringExHandleOtherFlagsW(v31, 2 * v28, v40, &v232, &v233, 2048);
LABEL_49:
    v42 = 13;
LABEL_50:
    v43 = v234;
    hProcess = hObject;
    v8 = v31;
    ExitCode[0] = v42;
    goto LABEL_51;
  }
  if ( (int)RtlStringCchPrintfW(v249, 17, L"%lx", a6) < 0 )
    goto LABEL_122;
  v70 = v28;
  v71 = lpCommandLine;
  while ( *v71 )
  {
    ++v71;
    if ( !--v70 )
    {
      v72 = 0;
      v73 = -1073741811;
      goto LABEL_107;
    }
  }
  v72 = v28 - v70;
  v73 = 0;
LABEL_107:
  if ( v73 < 0 )
    goto LABEL_122;
  v74 = v28 - v72;
  if ( v28 - v72 <= 1 )
    goto LABEL_399;
  v75 = 2147483646;
  v76 = &lpCommandLine[v72];
  v77 = L" \"";
  do
  {
    if ( !v75 )
      break;
    if ( !*v77 )
      break;
    *v76++ = *v77++;
    --v75;
    --v74;
  }
  while ( v74 );
  v78 = v76 - 1;
  if ( v74 )
    v78 = v76;
  *v78 = 0;
  if ( !v74 )
    goto LABEL_399;
  v79 = lpCommandLine;
  v80 = v28;
  v81 = lpCommandLine;
  while ( *v81 )
  {
    ++v81;
    if ( !--v80 )
    {
      v72 = 0;
      v82 = -1073741811;
      goto LABEL_145;
    }
  }
  v72 = v28 - v80;
  v82 = 0;
LABEL_145:
  if ( v82 < 0 )
    goto LABEL_122;
  v100 = v28 - v72;
  if ( v28 - v72 <= 1 )
  {
    if ( !v249[0] )
      goto LABEL_155;
LABEL_399:
    RtlStringExHandleOtherFlagsW(lpCommandLine, v29, v72, &v232, &v233, 2048);
    goto LABEL_122;
  }
  v101 = 2147483646;
  v102 = v249;
  v103 = &lpCommandLine[v72];
  do
  {
    if ( !v101 )
      break;
    if ( !*v102 )
      break;
    *v103++ = *v102++;
    --v101;
    --v100;
  }
  while ( v100 );
  v104 = v103 - 1;
  if ( v100 )
    v104 = v103;
  *v104 = 0;
  if ( !v100 )
    goto LABEL_399;
  v79 = lpCommandLine;
LABEL_155:
  v105 = v28;
  v106 = v79;
  while ( *v106 )
  {
    ++v106;
    if ( !--v105 )
    {
      v72 = 0;
      v107 = -1073741811;
      goto LABEL_160;
    }
  }
  v72 = v28 - v105;
  v107 = 0;
LABEL_160:
  if ( v107 < 0 )
    goto LABEL_122;
  v108 = v28 - v72;
  if ( v28 - v72 <= 1 )
    goto LABEL_399;
  v109 = 2147483646;
  v110 = &v79[v72];
  v111 = L"\"";
  do
  {
    if ( !v109 )
      break;
    if ( !*v111 )
      break;
    *v110++ = *v111++;
    --v109;
    --v108;
  }
  while ( v108 );
  v112 = v110 - 1;
  if ( v108 )
    v112 = v110;
  *v112 = 0;
  if ( !v108 )
    goto LABEL_399;
  v113 = v28;
  v114 = lpCommandLine;
  do
  {
    if ( !*v114 )
    {
      v83 = v28 - v113;
      v84 = 0;
      goto LABEL_121;
    }
    ++v114;
    --v113;
  }
  while ( v113 );
  v83 = 0;
  v84 = -1073741811;
LABEL_121:
  if ( v84 < 0 )
    goto LABEL_122;
  v85 = v28 - v83;
  if ( v28 - v83 <= 1 )
    goto LABEL_400;
  v86 = 2147483646;
  v87 = &lpCommandLine[v83];
  v88 = L" \"";
  do
  {
    if ( !v86 )
      break;
    if ( !*v88 )
      break;
    *v87++ = *v88++;
    --v86;
    --v85;
  }
  while ( v85 );
  v89 = v87 - 1;
  if ( v85 )
    v89 = v87;
  *v89 = 0;
  if ( !v85 )
  {
LABEL_400:
    dwCreationFlags = 2048;
LABEL_403:
    RtlStringExHandleOtherFlagsW(lpCommandLine, v29, v83, &v232, &v233, dwCreationFlags);
    goto LABEL_122;
  }
  v231 = 0;
  if ( (int)RtlStringLengthWorkerW(lpCommandLine, v28, &v231) < 0 )
    goto LABEL_122;
  v83 = (unsigned __int64)v231;
  v91 = v28 - (_QWORD)v231;
  if ( v28 - (unsigned __int64)v231 <= 1 )
  {
    if ( !*v90 )
      goto LABEL_140;
    goto LABEL_402;
  }
  v92 = 2147483646;
  v93 = &lpCommandLine[(_QWORD)v231];
  do
  {
    if ( !v92 )
      break;
    if ( !*v90 )
      break;
    *v93++ = *v90++;
    --v92;
    --v91;
  }
  while ( v91 );
  v94 = v93 - 1;
  if ( v91 )
    v94 = v93;
  *v94 = 0;
  if ( !v91 )
  {
LABEL_402:
    dwCreationFlags = 2304;
    goto LABEL_403;
  }
LABEL_140:
  v95 = lpCommandLine;
  v96 = v28;
  v97 = lpCommandLine;
  while ( *v97 )
  {
    ++v97;
    if ( !--v96 )
    {
      v98 = 0;
      v99 = -1073741811;
      goto LABEL_174;
    }
  }
  v98 = v28 - v96;
  v99 = 0;
LABEL_174:
  if ( v99 < 0 )
    goto LABEL_122;
  v115 = v28 - v98;
  if ( v28 - v98 <= 1 )
    goto LABEL_406;
  v116 = 2147483646;
  v117 = &lpCommandLine[v98];
  v118 = L"\"";
  do
  {
    if ( !v116 )
      break;
    if ( !*v118 )
      break;
    *v117++ = *v118++;
    --v116;
    --v115;
  }
  while ( v115 );
  v119 = v117 - 1;
  if ( v115 )
    v119 = v117;
  *v119 = 0;
  if ( !v115 )
  {
    dwCreationFlagsa = 2048;
LABEL_416:
    v202 = v98;
LABEL_417:
    RtlStringExHandleOtherFlagsW(v95, v29, v202, &v232, &v233, dwCreationFlagsa);
    goto LABEL_122;
  }
  if ( (int)RtlStringCchPrintfW(v249, 17, L"%hx", 0) < 0 )
    goto LABEL_122;
  v95 = lpCommandLine;
  v120 = v28;
  v121 = lpCommandLine;
  while ( *v121 )
  {
    ++v121;
    if ( !--v120 )
    {
      v98 = 0;
      v122 = -1073741811;
      goto LABEL_189;
    }
  }
  v98 = v28 - v120;
  v122 = 0;
LABEL_189:
  if ( v122 < 0 )
    goto LABEL_122;
  v123 = v28 - v98;
  if ( v28 - v98 <= 1 )
    goto LABEL_406;
  v124 = 2147483646;
  v125 = &lpCommandLine[v98];
  v126 = L" \"";
  do
  {
    if ( !v124 )
      break;
    if ( !*v126 )
      break;
    *v125++ = *v126++;
    --v124;
    --v123;
  }
  while ( v123 );
  v127 = v125 - 1;
  if ( v123 )
    v127 = v125;
  *v127 = 0;
  if ( !v123 )
    goto LABEL_406;
  v128 = v28;
  v129 = v95;
  while ( *v129 )
  {
    ++v129;
    if ( !--v128 )
    {
      v98 = 0;
      v130 = -1073741811;
      goto LABEL_203;
    }
  }
  v98 = v28 - v128;
  v130 = 0;
LABEL_203:
  if ( v130 < 0 )
    goto LABEL_122;
  v131 = v28 - v98;
  if ( v28 - v98 <= 1 )
  {
    if ( v249[0] )
      goto LABEL_406;
  }
  else
  {
    v132 = 2147483646;
    v133 = v249;
    v134 = &v95[v98];
    do
    {
      if ( !v132 )
        break;
      if ( !*v133 )
        break;
      *v134++ = *v133++;
      --v132;
      --v131;
    }
    while ( v131 );
    v135 = v134 - 1;
    if ( v131 )
      v135 = v134;
    *v135 = 0;
    if ( !v131 )
      goto LABEL_406;
  }
  v136 = v28;
  v137 = v95;
  while ( *v137 )
  {
    ++v137;
    if ( !--v136 )
    {
      v98 = 0;
      v138 = -1073741811;
      goto LABEL_217;
    }
  }
  v98 = v28 - v136;
  v138 = 0;
LABEL_217:
  if ( v138 < 0 )
    goto LABEL_122;
  v139 = v28 - v98;
  if ( v28 - v98 <= 1 )
    goto LABEL_406;
  v140 = 2147483646;
  v141 = &v95[v98];
  v142 = L"\"";
  do
  {
    if ( !v140 )
      break;
    if ( !*v142 )
      break;
    *v141++ = *v142++;
    --v140;
    --v139;
  }
  while ( v139 );
  v143 = v141 - 1;
  if ( v139 )
    v143 = v141;
  *v143 = 0;
  if ( !v139 )
  {
    dwCreationFlagsa = 2048;
    goto LABEL_416;
  }
  if ( (int)RtlStringCchPrintfW(v249, 17, L"%I64x", v234) < 0 )
    goto LABEL_122;
  v95 = lpCommandLine;
  v144 = v28;
  v145 = lpCommandLine;
  while ( *v145 )
  {
    ++v145;
    if ( !--v144 )
    {
      v98 = 0;
      v146 = -1073741811;
      goto LABEL_232;
    }
  }
  v98 = v28 - v144;
  v146 = 0;
LABEL_232:
  if ( v146 < 0 )
    goto LABEL_122;
  v147 = v28 - v98;
  if ( v28 - v98 <= 1 )
    goto LABEL_406;
  v148 = 2147483646;
  v149 = &lpCommandLine[v98];
  v150 = L" \"";
  do
  {
    if ( !v148 )
      break;
    if ( !*v150 )
      break;
    *v149++ = *v150++;
    --v148;
    --v147;
  }
  while ( v147 );
  v151 = v149 - 1;
  if ( v147 )
    v151 = v149;
  *v151 = 0;
  if ( !v147 )
    goto LABEL_406;
  v231 = 0;
  if ( (int)RtlStringLengthWorkerW(v95, v28, &v231) < 0 )
  {
LABEL_122:
    v8 = lpCommandLine;
    v43 = v234;
    v42 = 13;
    hProcess = hObject;
    ExitCode[0] = 13;
    goto LABEL_51;
  }
  v98 = (unsigned __int64)v231;
  v152 = v28 - (_QWORD)v231;
  if ( v28 - (unsigned __int64)v231 <= 1 )
  {
    if ( v249[0] )
      goto LABEL_415;
  }
  else
  {
    v153 = 2147483646;
    v154 = v249;
    v155 = &v95[(_QWORD)v231];
    do
    {
      if ( !v153 )
        break;
      if ( !*v154 )
        break;
      *v155++ = *v154++;
      --v153;
      --v152;
    }
    while ( v152 );
    v156 = v155 - 1;
    if ( v152 )
      v156 = v155;
    *v156 = 0;
    if ( !v152 )
      goto LABEL_415;
  }
  v157 = v28;
  v158 = v95;
  while ( *v158 )
  {
    ++v158;
    if ( !--v157 )
    {
      v98 = 0;
      v159 = -1073741811;
      goto LABEL_255;
    }
  }
  v98 = v28 - v157;
  v159 = 0;
LABEL_255:
  if ( v159 < 0 )
    goto LABEL_122;
  v160 = v28 - v98;
  if ( v28 - v98 <= 1 )
    goto LABEL_406;
  v161 = 2147483646;
  v162 = &v95[v98];
  v163 = L"\"";
  do
  {
    if ( !v161 )
      break;
    if ( !*v163 )
      break;
    *v162++ = *v163++;
    --v161;
    --v160;
  }
  while ( v160 );
  v164 = v162 - 1;
  if ( v160 )
    v164 = v162;
  *v164 = 0;
  if ( !v160 )
  {
    dwCreationFlagsa = 2048;
    goto LABEL_416;
  }
  if ( (int)RtlStringCchPrintfW(v249, 17, L"%p", v232) < 0 )
    goto LABEL_122;
  v95 = lpCommandLine;
  v165 = v28;
  v166 = lpCommandLine;
  while ( *v166 )
  {
    ++v166;
    if ( !--v165 )
    {
      v98 = 0;
      v167 = -1073741811;
      goto LABEL_270;
    }
  }
  v98 = v28 - v165;
  v167 = 0;
LABEL_270:
  if ( v167 < 0 )
    goto LABEL_122;
  v168 = v28 - v98;
  if ( v28 - v98 <= 1 )
    goto LABEL_406;
  v169 = 2147483646;
  v170 = &lpCommandLine[v98];
  v171 = L" \"";
  do
  {
    if ( !v169 )
      break;
    if ( !*v171 )
      break;
    *v170++ = *v171++;
    --v169;
    --v168;
  }
  while ( v168 );
  v172 = v170 - 1;
  if ( v168 )
    v172 = v170;
  *v172 = 0;
  if ( !v168 )
    goto LABEL_406;
  v173 = v28;
  v174 = v95;
  while ( *v174 )
  {
    ++v174;
    if ( !--v173 )
    {
      v98 = 0;
      v175 = -1073741811;
      goto LABEL_284;
    }
  }
  v98 = v28 - v173;
  v175 = 0;
LABEL_284:
  if ( v175 < 0 )
    goto LABEL_122;
  v176 = v28 - v98;
  if ( v28 - v98 <= 1 )
  {
    if ( !v249[0] )
      goto LABEL_293;
LABEL_406:
    dwCreationFlagsa = 2048;
    goto LABEL_416;
  }
  v177 = 2147483646;
  v178 = v249;
  v179 = &v95[v98];
  do
  {
    if ( !v177 )
      break;
    if ( !*v178 )
      break;
    *v179++ = *v178++;
    --v177;
    --v176;
  }
  while ( v176 );
  v180 = v179 - 1;
  if ( v176 )
    v180 = v179;
  *v180 = 0;
  if ( !v176 )
    goto LABEL_406;
LABEL_293:
  v181 = v28;
  v182 = v95;
  while ( *v182 )
  {
    ++v182;
    if ( !--v181 )
    {
      v98 = 0;
      v183 = -1073741811;
      goto LABEL_298;
    }
  }
  v98 = v28 - v181;
  v183 = 0;
LABEL_298:
  if ( v183 < 0 )
    goto LABEL_122;
  v184 = v28 - v98;
  if ( v28 - v98 <= 1 )
    goto LABEL_406;
  v185 = 2147483646;
  v186 = &v95[v98];
  v187 = L"\"";
  do
  {
    if ( !v185 )
      break;
    if ( !*v187 )
      break;
    *v186++ = *v187++;
    --v185;
    --v184;
  }
  while ( v184 );
  v188 = v186 - 1;
  if ( v184 )
    v188 = v186;
  *v188 = 0;
  if ( !v184 )
  {
    dwCreationFlagsa = 2048;
    goto LABEL_416;
  }
  v189 = v28;
  v190 = v95;
  while ( *v190 )
  {
    ++v190;
    if ( !--v189 )
    {
      v98 = 0;
      v191 = -1073741811;
      goto LABEL_312;
    }
  }
  v98 = v28 - v189;
  v191 = 0;
LABEL_312:
  if ( v191 < 0 )
    goto LABEL_122;
  v192 = v28 - v98;
  if ( v28 - v98 <= 1 )
    goto LABEL_406;
  v193 = 2147483646;
  v194 = &v95[v98];
  do
  {
    if ( !v193 )
      break;
    if ( !*v48 )
      break;
    *v194++ = *v48++;
    --v193;
    --v192;
  }
  while ( v192 );
  v195 = v194 - 1;
  if ( v192 )
    v195 = v194;
  *v195 = 0;
  if ( !v192 )
    goto LABEL_406;
  v231 = 0;
  if ( (int)RtlStringLengthWorkerW(v95, v28, &v231) < 0 )
    goto LABEL_122;
  v98 = (unsigned __int64)v231;
  v196 = v28 - (_QWORD)v231;
  if ( v28 - (unsigned __int64)v231 > 1 )
  {
    v197 = 2147483646;
    v198 = &v95[(_QWORD)v231];
    do
    {
      if ( !v197 )
        break;
      if ( !*v22 )
        break;
      *v198++ = *v22++;
      --v197;
      --v196;
    }
    while ( v196 );
    v199 = v198 - 1;
    if ( v196 )
      v199 = v198;
    *v199 = 0;
    if ( v196 )
      goto LABEL_330;
    goto LABEL_415;
  }
  if ( *v22 )
  {
LABEL_415:
    dwCreationFlagsa = 2304;
    goto LABEL_416;
  }
LABEL_330:
  v200 = v28;
  v201 = v95;
  while ( *v201 )
  {
    ++v201;
    if ( !--v200 )
    {
      v202 = 0;
      v203 = -1073741811;
      goto LABEL_335;
    }
  }
  v203 = 0;
  v202 = v28 - v200;
LABEL_335:
  if ( v203 < 0 )
    goto LABEL_122;
  v205 = v28 == v202;
  v204 = v28 - v202;
  if ( v205 || v204 == 1 )
    goto LABEL_418;
  v206 = &v95[v202];
  do
  {
    if ( !v33 )
      break;
    if ( !*v65 )
      break;
    *v206++ = *v65++;
    --v33;
    --v204;
  }
  while ( v204 );
  v207 = v206 - 1;
  if ( v204 )
    v207 = v206;
  *v207 = 0;
  if ( !v204 )
  {
LABEL_418:
    dwCreationFlagsa = 2048;
    goto LABEL_417;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, v95);
  v43 = v234;
  DevRtlWriteTextLog(v234, 0x2000000, 65542, "Creating Install Process: %ws", v238);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v8 = lpCommandLine;
  StartupInfo.lpDesktop = (LPWSTR)&qword_18001C3B0;
  StartupInfo.cb = 104;
  if ( CreateProcessW(Str, lpCommandLine, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    CloseHandle(ProcessInformation.hThread);
    hProcess = ProcessInformation.hProcess;
    v208 = WaitForSingleObjectEx(ProcessInformation.hProcess, 0xFFFFFFFF, 0);
    if ( v208 )
    {
      if ( v208 == 258 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, 258);
        }
        ExitCode[0] = 1460;
        if ( TerminateProcess(hProcess, 0x5B4u)
          || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
        {
          goto LABEL_428;
        }
        v224 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v225 = GetLastError();
        WPP_SF_d(v224, 45, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, v225);
        v42 = ExitCode[0];
      }
      else if ( v208 == -1 )
      {
        v209 = GetLastError();
        v42 = v209;
        ExitCode[0] = v209;
        v210 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          v211 = 46;
          goto LABEL_427;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, v208);
        }
        v42 = 13;
        ExitCode[0] = 13;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
      if ( GetExitCodeProcess(hProcess, ExitCode) )
      {
        v222 = WPP_GLOBAL_Control;
        v223 = UnbiasedTime / 0x2710;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              43,
              WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
              ExitCode[0]);
            v222 = WPP_GLOBAL_Control;
          }
          if ( v222 != &WPP_GLOBAL_Control && (*((_DWORD *)v222 + 7) & 0x40000) != 0 )
            WPP_SF_d(v222[2], 48, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, ExitCode[0]);
        }
        DevRtlWriteTextLog(v43, 0x2000000, 65542, "Server install process exited with code 0x%08x", ExitCode[0]);
        UnbiasedTime = 0;
        QueryUnbiasedInterruptTime(&UnbiasedTime);
        LogInstallDevice(8, a6, 0, (__int64)v239, 0, UnbiasedTime / 0x2710 - v223, ExitCode[0]);
        v42 = ExitCode[0];
        if ( ExitCode[0] == 3010 )
        {
          v42 = 0;
          ExitCode[0] = 0;
          if ( v233 )
            *v233 = 1;
        }
      }
      else
      {
        v209 = GetLastError();
        v42 = v209;
        ExitCode[0] = v209;
        v210 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          v211 = 42;
LABEL_427:
          WPP_SF_d(v210[2], v211, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, v209);
LABEL_428:
          v42 = ExitCode[0];
        }
      }
    }
  }
  else
  {
    v221 = GetLastError();
    v42 = v221;
    ExitCode[0] = v221;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, v221);
      v42 = ExitCode[0];
    }
    hProcess = 0;
  }
LABEL_51:
  if ( v236 )
  {
    v45 = GetLastError();
    v241 = 0;
    v244 = 0;
    v242 = 0;
    v247 = 0;
    v243 = 0;
    v236 = 0;
    v246 = 0;
    if ( g_sputils_LogInitialized || (unsigned int)pSpUtilsLogInitialize() )
    {
      v212 = &GlobalDevLogData;
      if ( ((unsigned __int8)v43 & 3) != 3 )
        v212 = (__int64 *)&GlobalAppLogData;
      if ( !(unsigned int)TextLogMapFile(v212, &v241, 512, 2) )
      {
        if ( (unsigned int)TextLogFindSection(&v241, (unsigned int)v43, &v246, &v236) )
        {
          if ( (TextLogWriteSectionFooter((unsigned int)&v241, (unsigned int)&v246, v213, 1, v42),
                TextLogDeleteCtlTag(&v241, v236),
                (_DWORD)v244)
            && (unsigned int)(DWORD2(v242) - v242) >= *((_DWORD *)v212 + 2)
            || (unsigned int)TextLogContainsPendingRenameTag(&v241) )
          {
            if ( (unsigned int)TextLogRequestLogFileRename(&v241) )
            {
              if ( (unsigned int)TextLogRenameLogFile(&v241) )
              {
                if ( (_DWORD)v244 )
                  TextLogDecayLogFileBackups(*(STRSAFE_LPCWSTR *)(v243 + 16));
                *((_DWORD *)v212 + 6) = 0;
              }
              else
              {
                v214 = GetLastError() - 1;
                if ( !v214 || v214 == 49 )
                {
                  v215 = 4;
                  *((_DWORD *)v212 + 6) = 4;
                }
                else
                {
                  v215 = ++*((_DWORD *)v212 + 6);
                }
                if ( (_DWORD)v244 && v215 >= 4 && (*((_DWORD *)v212 + 3) & 0x2000) == 0 )
                {
                  LogStatus = TextLogGetLogStatus(v212);
                  if ( (LogStatus & 0x2000) == 0 )
                  {
                    TextLogQueueLogFileBackup(*(LPCWSTR *)(v243 + 16));
                    TextLogSetLogStatus(v212, LogStatus | 0x2000u);
                  }
                  *((_DWORD *)v212 + 3) |= 0x2000u;
                }
              }
            }
          }
        }
        TextLogUnmapFile(&v241);
      }
    }
    else
    {
      GetLastError();
    }
    SetLastError(v45);
  }
  else
  {
    DevRtlWriteTextLog(v43, 0x2000000, 262148, "{Plug and Play Service: Driver Install exit(%08x)}", v42);
  }
  if ( hProcess )
    CloseHandle(hProcess);
  if ( v8 )
    RtlFreeHeap(PnpHeapHandle, 0, v8);
  if ( P )
    RtlFreeHeap(PnpHeapHandle, 0, P);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  return ExitCode[0];
}

```

## disassembly

```asm
0x1800027a0  mov     r11, rsp
0x1800027a3  push    rbp
0x1800027a4  lea     rbp, [r11-318h]
0x1800027ab  sub     rsp, 410h
0x1800027b2  mov     rax, cs:__security_cookie
0x1800027b9  xor     rax, rsp
0x1800027bc  mov     [rbp+310h+var_40], rax
0x1800027c3  xorps   xmm0, xmm0
0x1800027c6  mov     [r11+18h], rbx
0x1800027ca  mov     rbx, [rbp+310h+arg_30]
0x1800027d1  mov     [r11-18h], rdi
0x1800027d5  mov     rdi, rdx
0x1800027d8  mov     [r11-20h], r12
0x1800027dc  xor     r12d, r12d
0x1800027df  mov     [r11-28h], r13
0x1800027e3  xor     eax, eax
0x1800027e5  mov     [r11-30h], r14
0x1800027e9  mov     r13d, r12d
0x1800027ec  mov     [r11-38h], r15
0x1800027f0  mov     r14, r9
0x1800027f3  mov     r15, [rbp+310h+Src]
0x1800027fa  mov     dword ptr [rbp+310h+StartupInfo.hStdError], eax
0x180002800  mov     qword ptr [rbp+310h+ProcessInformation.dwProcessId], rax
0x180002804  mov     [rsp+410h+var_398], r9
0x180002809  mov     [rbp+310h+var_370], rdx
0x18000280d  mov     [rsp+410h+var_3A8], rcx
0x180002812  mov     [rsp+410h+var_3B0], r9
0x180002817  mov     [rsp+410h+var_3A0], rbx
0x18000281c  mov     [rsp+410h+ExitCode], r12d
0x180002821  mov     [rsp+410h+lpCommandLine], r12
0x180002826  mov     [rbp+310h+P], r12
0x18000282a  mov     [rbp+310h+hObject], r12
0x18000282e  movups  xmmword ptr [rbp+310h+StartupInfo.cb], xmm0
0x180002832  movups  xmmword ptr [rbp+310h+StartupInfo.lpDesktop], xmm0
0x180002836  movups  xmmword ptr [rbp+310h+StartupInfo.dwX], xmm0
0x18000283a  movups  xmmword ptr [rbp+310h+StartupInfo.dwXCountChars], xmm0
0x18000283e  movups  xmmword ptr [rbp+310h+StartupInfo.wShowWindow], xmm0
0x180002842  movups  xmmword ptr [rbp+310h+StartupInfo.hStdInput], xmm0
0x180002846  movups  xmmword ptr [rbp+310h+ProcessInformation.hProcess], xmm0
0x18000284a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002851  lea     rax, WPP_GLOBAL_Control
0x180002858  cmp     rcx, rax
0x18000285b  jnz     loc_180003A99
0x180002861  test    rbx, rbx
0x180002864  jnz     loc_180003AC0
0x18000286a  mov     [rsp+408h], rsi
0x180002872  mov     [rbp+310h+var_388], r12d
0x180002876  test    r14, r14
0x180002879  jz      loc_180003AC8
0x18000287f  lea     r9, aPlugAndPlaySer_2; "{Plug and Play Service: Driver Install "...
0x180002886  mov     qword ptr [rsp+410h+bInheritHandles], rdi
0x18000288b  mov     edx, 2000000h
0x180002890  mov     r8d, 20004h
0x180002896  mov     rcx, r14
0x180002899  call    cs:__imp_DevRtlWriteTextLog
0x18000289f  mov     rcx, r14
0x1800028a2  call    cs:__imp_DevRtlSetThreadLogToken
0x1800028a8  lea     rcx, [rbp+310h+UnbiasedTime]; UnbiasedTime
0x1800028ac  mov     [rbp+310h+UnbiasedTime], r12
0x1800028b0  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800028b6  lea     rcx, [rbp+310h+Str]
0x1800028bd  call    GetDeviceInstallerFilename
0x1800028c2  test    eax, eax
0x1800028c4  jz      loc_180003B64
0x1800028ca  mov     edx, 5Ch ; '\'; Ch
0x1800028cf  lea     rcx, [rbp+310h+Str]; Str
0x1800028d6  call    cs:__imp_wcsrchr
0x1800028dc  test    rax, rax
0x1800028df  jz      loc_180003A21
0x1800028e5  add     rax, 2
0x1800028e9  mov     [rbp+310h+var_378], rax
0x1800028ed  jz      loc_180003A21
0x1800028f3  mov     r14d, 7FFFh
0x1800028f9  mov     ecx, r14d
0x1800028fc  nop     dword ptr [rax+00h]
0x180002900  cmp     [rax], r13w
0x180002904  jz      short loc_18000291E
0x180002906  add     rax, 2
0x18000290a  sub     rcx, 1
0x18000290e  jnz     short loc_180002900
0x180002910  mov     r14, r12
0x180002913  mov     r12d, 0C000000Dh
0x180002919  mov     eax, r12d
0x18000291c  jmp     short loc_18000292A
0x18000291e  mov     eax, r12d
0x180002921  sub     r14, rcx
0x180002924  mov     r12d, 0C000000Dh
0x18000292a  test    eax, eax
0x18000292c  js      loc_180003A21
0x180002932  mov     rcx, rdi; Src
0x180002935  call    StringSearchAndReplace
0x18000293a  mov     [rbp+310h+P], rax
0x18000293e  test    rax, rax
0x180002941  jz      loc_180003B84
0x180002947  mov     rbx, rax
0x18000294a  mov     [rsp+410h+var_3B0], rax
0x18000294f  mov     edi, 104h
0x180002954  mov     rsi, r14
0x180002957  mov     ecx, edi
0x180002959  mov     rax, rbx
0x18000295c  nop     dword ptr [rax+00h]
0x180002960  cmp     [rax], r13w
0x180002964  jz      short loc_180002977
0x180002966  add     rax, 2
0x18000296a  sub     rcx, 1
0x18000296e  jnz     short loc_180002960
0x180002970  xor     edi, edi
0x180002972  mov     eax, r12d
0x180002975  jmp     short loc_180002981
0x180002977  sub     rdi, rcx
0x18000297a  mov     [rsp+410h+var_3B0], rbx
0x18000297f  xor     eax, eax
0x180002981  test    eax, eax
0x180002983  js      loc_180003A21
0x180002989  mov     rcx, r15; Src
0x18000298c  call    StringSearchAndReplace
0x180002991  mov     r13, rax
0x180002994  test    rax, rax
0x180002997  jz      loc_180003B99
0x18000299d  lea     r8, [r14+rdi]
0x1800029a1  mov     edx, 20Ah
0x1800029a6  mov     rax, r13
0x1800029a9  mov     ecx, edx
0x1800029ab  nop     dword ptr [rax+rax+00h]
0x1800029b0  cmp     word ptr [rax], 0
0x1800029b4  jz      short loc_1800029C7
0x1800029b6  add     rax, 2
0x1800029ba  sub     rcx, 1
0x1800029be  jnz     short loc_1800029B0
0x1800029c0  xor     edx, edx
0x1800029c2  mov     eax, r12d
0x1800029c5  jmp     short loc_1800029D1
0x1800029c7  sub     rdx, rcx
0x1800029ca  mov     [rsp+410h+var_3B0], rbx
0x1800029cf  xor     eax, eax
0x1800029d1  test    eax, eax
0x1800029d3  js      loc_180003A54
0x1800029d9  lea     r14, [rdx+4Ah]
0x1800029dd  add     r14, r8
0x1800029e0  lea     r12, [r14+r14]
0x1800029e4  cmp     r12, 0F42400h
0x1800029eb  ja      loc_180003BB2
0x1800029f1  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x1800029f8  mov     r8, r12; Size
0x1800029fb  mov     edx, 8; Flags
0x180002a00  call    cs:__imp_RtlAllocateHeap
0x180002a06  mov     [rsp+410h+lpCommandLine], rax
0x180002a0b  mov     rdi, rax
0x180002a0e  test    rax, rax
0x180002a11  jz      loc_180003BB7
0x180002a17  test    r14, r14
0x180002a1a  jz      loc_180003BDD
0x180002a20  cmp     r14, 7FFFFFFFh
0x180002a27  ja      loc_180003BD8
0x180002a2d  mov     rdx, [rbp+310h+var_378]
0x180002a31  mov     r15d, 7FFFFFFEh
0x180002a37  mov     ecx, r15d
0x180002a3a  mov     r8, r14
0x180002a3d  mov     r9, rax
0x180002a40  test    rcx, rcx
0x180002a43  jz      short loc_180002A62
0x180002a45  movzx   eax, word ptr [rdx]
0x180002a48  test    ax, ax
0x180002a4b  jz      short loc_180002A62
0x180002a4d  mov     [r9], ax
0x180002a51  add     rdx, 2
0x180002a55  add     r9, 2
0x180002a59  dec     rcx
0x180002a5c  sub     r8, 1
0x180002a60  jnz     short loc_180002A40
0x180002a62  test    r8, r8
0x180002a65  lea     rcx, [r9-2]
0x180002a69  cmovnz  rcx, r9
0x180002a6d  xor     eax, eax
0x180002a6f  mov     [rcx], ax
0x180002a72  test    r8, r8
0x180002a75  jz      loc_180003BDD
0x180002a7b  mov     r9d, 8
0x180002a81  lea     r8, aLx; "%lx"
0x180002a88  mov     edx, 11h
0x180002a8d  lea     rcx, [rbp+310h+var_280]
0x180002a94  call    RtlStringCchPrintfW
0x180002a99  test    eax, eax
0x180002a9b  js      short loc_180002AD2
0x180002a9d  mov     rcx, r14
0x180002aa0  mov     rax, rdi
0x180002aa3  cmp     word ptr [rax], 0
0x180002aa7  jz      short loc_180002ABD
0x180002aa9  add     rax, 2
0x180002aad  sub     rcx, 1
0x180002ab1  jnz     short loc_180002AA3
0x180002ab3  xor     r10d, r10d
0x180002ab6  mov     eax, 0C000000Dh
0x180002abb  jmp     short loc_180002ACA
0x180002abd  mov     r10, r14
0x180002ac0  mov     [rsp+410h+var_3B0], rbx
0x180002ac5  sub     r10, rcx
0x180002ac8  xor     eax, eax
0x180002aca  test    eax, eax
0x180002acc  jns     loc_180002BED
0x180002ad2  mov     ebx, 0Dh
0x180002ad7  mov     r14, [rsp+410h+var_398]
0x180002adc  lea     r12, WPP_GLOBAL_Control
0x180002ae3  mov     r15, [rbp+310h+hObject]
0x180002ae7  mov     r13, rdi
0x180002aea  mov     [rsp+410h+ExitCode], ebx
0x180002aee  cmp     [rbp+310h+var_388], 0
0x180002af2  jz      loc_180002BC9
0x180002af8  call    cs:__imp_GetLastError
0x180002afe  xorps   xmm0, xmm0
0x180002b01  mov     esi, eax
0x180002b03  xor     eax, eax
0x180002b05  cmp     cs:g_sputils_LogInitialized, eax
0x180002b0b  movups  [rbp+310h+var_360], xmm0
0x180002b0f  mov     [rbp+310h+var_330], rax
0x180002b13  movups  [rbp+310h+var_350], xmm0
0x180002b17  mov     [rbp+310h+var_300], eax
0x180002b1a  movups  [rbp+310h+var_340], xmm0
0x180002b1e  mov     [rbp+310h+var_388], eax
0x180002b21  movups  [rbp+310h+var_310], xmm0
0x180002b25  jnz     loc_180003930
0x180002b2b  call    _pSpUtilsLogInitialize
0x180002b30  test    eax, eax
0x180002b32  jnz     loc_180003930
0x180002b38  call    cs:__imp_GetLastError
0x180002b3e  mov     ecx, esi; dwErrCode
0x180002b40  call    cs:__imp_SetLastError
0x180002b46  mov     r14, [rsp+410h+var_28]
0x180002b4e  mov     rdi, [rsp+410h+var_10]
0x180002b56  mov     rsi, [rsp+408h]
0x180002b5e  mov     rbx, [rsp+410h+arg_10]
0x180002b66  test    r15, r15
0x180002b69  jnz     loc_180004082
0x180002b6f  mov     r15, [rsp+410h+var_30]
0x180002b77  test    r13, r13
0x180002b7a  jnz     loc_180004090
0x180002b80  mov     rax, [rbp+310h+P]
0x180002b84  mov     r13, [rsp+410h+var_20]
0x180002b8c  test    rax, rax
0x180002b8f  jnz     loc_1800040A7
0x180002b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b9c  cmp     rcx, r12
0x180002b9f  mov     r12, [rsp+410h+var_18]
0x180002ba7  jnz     loc_1800040BE
0x180002bad  mov     eax, [rsp+410h+ExitCode]
0x180002bb1  mov     rcx, [rbp+310h+var_40]
0x180002bb8  xor     rcx, rsp; StackCookie
0x180002bbb  call    __security_check_cookie
0x180002bc0  add     rsp, 410h
0x180002bc7  pop     rbp
0x180002bc8  retn
0x180002bc9  lea     r9, aPlugAndPlaySer_0; "{Plug and Play Service: Driver Install "...
0x180002bd0  mov     [rsp+410h+bInheritHandles], ebx
0x180002bd4  mov     edx, 2000000h
0x180002bd9  mov     r8d, 40004h
0x180002bdf  mov     rcx, r14
0x180002be2  call    cs:__imp_DevRtlWriteTextLog
0x180002be8  jmp     loc_180002B46
0x180002bed  mov     rdx, r14
0x180002bf0  sub     rdx, r10
0x180002bf3  cmp     rdx, 1
0x180002bf7  jbe     loc_180003BF5
0x180002bfd  lea     rsi, asc_18001C3A8; " \""
0x180002c04  mov     rcx, r15
0x180002c07  mov     r8, rsi
0x180002c0a  lea     r9, [rdi+r10*2]
0x180002c0e  xchg    ax, ax
0x180002c10  test    rcx, rcx
0x180002c13  jz      short loc_180002C33
0x180002c15  movzx   eax, word ptr [r8]
0x180002c19  test    ax, ax
0x180002c1c  jz      short loc_180002C33
0x180002c1e  mov     [r9], ax
0x180002c22  add     r8, 2
0x180002c26  add     r9, 2
0x180002c2a  dec     rcx
0x180002c2d  sub     rdx, 1
0x180002c31  jnz     short loc_180002C10
0x180002c33  test    rdx, rdx
0x180002c36  lea     rcx, [r9-2]
0x180002c3a  cmovnz  rcx, r9
0x180002c3e  xor     eax, eax
0x180002c40  mov     [rcx], ax
0x180002c43  test    rdx, rdx
0x180002c46  jz      loc_180003BF5
0x180002c4c  mov     rcx, r14
0x180002c4f  mov     rax, rdi
0x180002c52  cmp     word ptr [rax], 0
0x180002c56  jz      short loc_180002C6C
0x180002c58  add     rax, 2
0x180002c5c  sub     rcx, 1
0x180002c60  jnz     short loc_180002C52
0x180002c62  xor     r10d, r10d
0x180002c65  mov     eax, 0C000000Dh
0x180002c6a  jmp     short loc_180002C79
0x180002c6c  mov     r10, r14
0x180002c6f  mov     [rsp+410h+var_3B0], rbx
0x180002c74  sub     r10, rcx
0x180002c77  xor     eax, eax
0x180002c79  test    eax, eax
  ... truncated ...
```
