# PnpDeleteDriverPackage

- ea: `0x180004180`
- end: `0x18000553a`
- name: `PnpDeleteDriverPackage`
- size: `5050`
- prototype: `__int64 __fastcall(__int64, void *, __int64, void *, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800146d0`

## callees

- `0x180001ec0`
- `0x1800024d0`
- `0x180002750`
- `0x1800040f0`
- `0x180004180`
- `0x180005540`
- `0x1800117d4`
- `0x180011964`
- `0x1800132c0`
- `0x180013590`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004279`
- `msvcrt!wcsrchr` at `0x180004279`
- `ntdll!RtlFreeHeap` at `0x180004528`
- `ntdll!RtlFreeHeap` at `0x180005500`
- `ntdll!RtlFreeHeap` at `0x180004528`
- `ntdll!RtlFreeHeap` at `0x180005500`
- `ntdll!RtlAllocateHeap` at `0x1800043a7`
- `ntdll!RtlAllocateHeap` at `0x1800043a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800052a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800052a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005486`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005294`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005294`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054ec`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180005433`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180005433`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800050e2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800050e2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800052e9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800052e9`
- `DEVRTL!DevRtlWriteTextLog` at `0x180004249`
- `DEVRTL!DevRtlWriteTextLog` at `0x18000507a`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800053b9`
- `DEVRTL!DevRtlWriteTextLog` at `0x180004249`
- `DEVRTL!DevRtlWriteTextLog` at `0x18000507a`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800053b9`

## string_xrefs

- `0x180004228`: `Delete flags: 0x%08X`
- `0x1800053a0`: `Driver store delete process exited with code 0x%08x`

## pseudocode

```c
__int64 __fastcall PnpDeleteDriverPackage(__int64 a1, void *a2, __int64 a3, void *a4, unsigned int a5, _DWORD *a6)
{
  __int64 v6; // r10
  void *v8; // r13
  wchar_t *v9; // rax
  bool v10; // zf
  WCHAR *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r14
  int v14; // eax
  void *v15; // rax
  __int64 v16; // rcx
  _WORD *v17; // rax
  __int64 v18; // rdi
  int v19; // eax
  __int64 v20; // r13
  __int64 v21; // r8
  _WORD *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  DWORD LastError; // ebx
  unsigned __int64 v27; // rdi
  WCHAR *Heap; // rax
  WCHAR *v29; // rsi
  WCHAR *v30; // rdx
  __int64 v31; // r12
  __int64 v32; // rcx
  unsigned __int64 v33; // r8
  WCHAR *v34; // r9
  WCHAR *v35; // rcx
  unsigned __int64 v36; // rcx
  WCHAR *v37; // rax
  _WORD *v38; // r11
  unsigned __int64 v39; // r10
  int v40; // eax
  unsigned __int64 v41; // rdx
  const wchar_t *v42; // r14
  __int64 v43; // rcx
  const wchar_t *v44; // r8
  WCHAR *v45; // r9
  WCHAR *v46; // rcx
  unsigned __int64 v47; // rcx
  WCHAR *v48; // rax
  int v49; // eax
  int v50; // eax
  unsigned __int64 v52; // rdx
  __int64 v53; // rcx
  WCHAR *v54; // r8
  const wchar_t *v55; // r9
  WCHAR *v56; // rcx
  unsigned __int64 v57; // rdx
  __int64 v58; // rcx
  WCHAR *v59; // r9
  WCHAR *v60; // r8
  WCHAR *v61; // rcx
  unsigned __int64 v62; // rcx
  WCHAR *v63; // rax
  int v64; // eax
  unsigned __int64 v65; // rdx
  __int64 v66; // rcx
  WCHAR *v67; // r8
  WCHAR *v68; // r9
  WCHAR *v69; // rcx
  unsigned __int64 v70; // rcx
  WCHAR *v71; // rax
  int v72; // eax
  unsigned __int64 v73; // rdx
  __int64 v74; // rcx
  const wchar_t *v75; // r8
  WCHAR *v76; // r9
  WCHAR *v77; // rcx
  unsigned __int64 v78; // rcx
  WCHAR *v79; // rax
  int v80; // eax
  unsigned __int64 v81; // rdx
  __int64 v82; // rcx
  WCHAR *v83; // r9
  const wchar_t *v84; // r8
  WCHAR *v85; // rcx
  unsigned __int64 v86; // rcx
  WCHAR *v87; // rax
  _WORD *v88; // r8
  int v89; // eax
  unsigned __int64 v90; // rdx
  __int64 v91; // rcx
  WCHAR *v92; // r9
  WCHAR *v93; // r8
  WCHAR *v94; // rcx
  unsigned __int64 v95; // rcx
  WCHAR *v96; // rax
  int v97; // eax
  unsigned __int64 v98; // rdx
  __int64 v99; // rcx
  const wchar_t *v100; // r8
  WCHAR *v101; // r9
  WCHAR *v102; // rcx
  unsigned __int64 v103; // rcx
  WCHAR *v104; // rax
  int v105; // eax
  unsigned __int64 v106; // rdx
  __int64 v107; // rcx
  WCHAR *v108; // r9
  const wchar_t *v109; // r8
  WCHAR *v110; // rcx
  int v111; // r11d
  unsigned __int64 v112; // rdx
  WCHAR *v113; // r8
  __int64 v114; // rcx
  WCHAR *v115; // r10
  WCHAR *v116; // rcx
  unsigned __int64 v117; // rcx
  WCHAR *v118; // rax
  int v119; // eax
  unsigned __int64 v120; // rdx
  __int64 v121; // rcx
  const wchar_t *v122; // r9
  WCHAR *v123; // r8
  WCHAR *v124; // rcx
  unsigned __int64 v125; // rcx
  WCHAR *v126; // rax
  int v127; // eax
  unsigned __int64 v128; // rdx
  __int64 v129; // rcx
  WCHAR *v130; // r8
  const wchar_t *v131; // r9
  WCHAR *v132; // rcx
  unsigned __int64 v133; // rcx
  WCHAR *v134; // rax
  int v135; // eax
  unsigned __int64 v136; // rdx
  __int64 v137; // rcx
  WCHAR *v138; // r9
  WCHAR *v139; // r8
  WCHAR *v140; // rcx
  unsigned __int64 v141; // rcx
  WCHAR *v142; // rax
  int v143; // eax
  unsigned __int64 v144; // rdx
  __int64 v145; // rcx
  const wchar_t *v146; // r9
  WCHAR *v147; // r8
  WCHAR *v148; // rcx
  unsigned __int64 v149; // rcx
  WCHAR *v150; // rax
  unsigned __int64 v151; // rdx
  __int64 v152; // rcx
  const wchar_t *v153; // r9
  WCHAR *v154; // r8
  WCHAR *v155; // rcx
  unsigned __int64 v156; // rcx
  WCHAR *v157; // rax
  int v158; // eax
  unsigned __int64 v159; // rdx
  __int64 v160; // r8
  WCHAR *v161; // rax
  const wchar_t *v162; // r9
  WCHAR *v163; // rcx
  unsigned __int64 v164; // rcx
  WCHAR *v165; // rax
  int v166; // eax
  unsigned __int64 v167; // rdx
  __int64 v168; // r8
  WCHAR *v169; // r9
  WCHAR *v170; // rax
  WCHAR *v171; // rcx
  unsigned __int64 v172; // rcx
  WCHAR *v173; // rax
  int v174; // eax
  unsigned __int64 v175; // rdx
  __int64 v176; // r8
  const wchar_t *v177; // r9
  WCHAR *v178; // rax
  WCHAR *v179; // rcx
  unsigned __int64 v180; // rcx
  WCHAR *v181; // rax
  unsigned __int64 v182; // r8
  int v183; // eax
  unsigned __int64 v184; // rdx
  WCHAR *v185; // rax
  WCHAR *v186; // rcx
  int v187; // r9d
  __int64 v188; // r14
  DWORD v189; // eax
  HANDLE hProcess; // rdi
  DWORD v191; // eax
  DWORD v192; // eax
  _QWORD *v193; // rcx
  __int64 v194; // rdx
  _QWORD *v195; // rcx
  __int64 v196; // rbx
  DWORD v197; // eax
  char bInheritHandles; // [rsp+28h] [rbp-E0h]
  char bInheritHandlesa; // [rsp+28h] [rbp-E0h]
  int dwCreationFlags; // [rsp+30h] [rbp-D8h]
  DWORD ExitCode[2]; // [rsp+58h] [rbp-B0h] BYREF
  _WORD *v202; // [rsp+60h] [rbp-A8h]
  __int64 v203; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD *v204; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v205; // [rsp+78h] [rbp-90h] BYREF
  __int64 v206; // [rsp+80h] [rbp-88h]
  WCHAR *v207; // [rsp+88h] [rbp-80h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-78h] BYREF
  PVOID P; // [rsp+A8h] [rbp-60h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B8h] [rbp-50h] BYREF
  _WORD v211[24]; // [rsp+128h] [rbp+20h] BYREF
  wchar_t Str[264]; // [rsp+158h] [rbp+50h] BYREF

  v6 = a3;
  v8 = a2;
  v206 = a3;
  v202 = a2;
  v203 = a1;
  v204 = a6;
  ExitCode[0] = 0;
  memset(&StartupInfo, 0, 100);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
    v6 = v206;
  }
  if ( a6 )
    *a6 = 0;
  DevRtlWriteTextLog(v6, 0x2000000, 4, "Delete flags: 0x%08X", a5);
  if ( !(unsigned int)GetDeviceInstallerFilename(Str) )
  {
    LastError = GetLastError();
    ExitCode[0] = LastError;
    goto LABEL_65;
  }
  v9 = wcsrchr(Str, 0x5Cu);
  if ( !v9 )
    goto LABEL_317;
  v10 = v9 + 1 == 0;
  v11 = v9 + 1;
  v207 = v11;
  if ( v10 )
    goto LABEL_317;
  v12 = 0x7FFF;
  while ( *v11 )
  {
    ++v11;
    if ( !--v12 )
    {
      v13 = 0;
      v14 = -1073741811;
      goto LABEL_12;
    }
  }
  v13 = 0x7FFF - v12;
  v14 = 0;
LABEL_12:
  if ( v14 < 0 )
  {
LABEL_317:
    LastError = 13;
    ExitCode[0] = 13;
    goto LABEL_65;
  }
  v15 = (void *)StringSearchAndReplace(v8);
  P = v15;
  if ( v15 )
  {
    v8 = v15;
    v202 = v15;
  }
  else
  {
    ExitCode[0] = GetLastError();
    LastError = ExitCode[0];
    if ( ExitCode[0] )
      goto LABEL_65;
    if ( !v8 )
      goto LABEL_320;
  }
  v16 = 260;
  v17 = v8;
  while ( *v17 )
  {
    ++v17;
    if ( !--v16 )
    {
      v18 = 0;
      v19 = -1073741811;
      goto LABEL_20;
    }
  }
  v18 = 260 - v16;
  v202 = v8;
  v19 = 0;
LABEL_20:
  if ( v19 < 0 )
  {
LABEL_320:
    LastError = 13;
LABEL_321:
    ExitCode[0] = LastError;
    goto LABEL_63;
  }
  v20 = StringSearchAndReplace(a4);
  if ( v20 )
  {
    v21 = v13 + v18;
LABEL_23:
    v22 = (_WORD *)v20;
    v23 = 522;
    while ( *v22 )
    {
      ++v22;
      if ( !--v23 )
      {
        v24 = 0;
        v25 = -1073741811;
        goto LABEL_28;
      }
    }
    v24 = 522 - v23;
    v25 = 0;
LABEL_28:
    if ( v25 >= 0 )
    {
      LastError = 8;
      v27 = v21 + v24 + 74;
      if ( 2 * v27 <= 0xF42400 )
      {
        Heap = (WCHAR *)RtlAllocateHeap(PnpHeapHandle, 8u, 2 * v27);
        v29 = Heap;
        if ( Heap )
        {
          if ( v27 )
          {
            if ( v27 > 0x7FFFFFFF )
            {
              *Heap = 0;
            }
            else
            {
              v30 = v207;
              v31 = 2147483646;
              v32 = 2147483646;
              v33 = v27;
              v34 = Heap;
              do
              {
                if ( !v32 )
                  break;
                if ( !*v30 )
                  break;
                *v34++ = *v30++;
                --v32;
                --v33;
              }
              while ( v33 );
              v35 = v34 - 1;
              if ( v33 )
                v35 = v34;
              *v35 = 0;
              if ( v33 )
              {
                if ( (int)RtlStringCchPrintfW(v211, 17, L"%lx", 5) < 0 )
                  goto LABEL_61;
                v36 = v27;
                v37 = v29;
                while ( *v37 )
                {
                  ++v37;
                  if ( !--v36 )
                  {
                    v38 = v202;
                    v39 = 0;
                    v40 = -1073741811;
                    goto LABEL_46;
                  }
                }
                v38 = v202;
                v39 = v27 - v36;
                v40 = 0;
LABEL_46:
                if ( v40 < 0 )
                  goto LABEL_61;
                v41 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v42 = L" \"";
                v43 = 2147483646;
                v44 = L" \"";
                v45 = &v29[v39];
                do
                {
                  if ( !v43 )
                    break;
                  if ( !*v44 )
                    break;
                  *v45++ = *v44++;
                  --v43;
                  --v41;
                }
                while ( v41 );
                v46 = v45 - 1;
                if ( v41 )
                  v46 = v45;
                *v46 = 0;
                if ( !v41 )
                  goto LABEL_333;
                v47 = v27;
                v48 = v29;
                while ( *v48 )
                {
                  ++v48;
                  if ( !--v47 )
                  {
                    v39 = 0;
                    v49 = -1073741811;
                    goto LABEL_89;
                  }
                }
                v202 = v38;
                v39 = v27 - v47;
                v49 = 0;
LABEL_89:
                if ( v49 < 0 )
                  goto LABEL_61;
                v65 = v27 - v39;
                if ( v27 - v39 <= 1 )
                {
                  if ( v211[0] )
                    goto LABEL_333;
                }
                else
                {
                  v66 = 2147483646;
                  v67 = v211;
                  v68 = &v29[v39];
                  do
                  {
                    if ( !v66 )
                      break;
                    if ( !*v67 )
                      break;
                    *v68++ = *v67++;
                    --v66;
                    --v65;
                  }
                  while ( v65 );
                  v69 = v68 - 1;
                  if ( v65 )
                    v69 = v68;
                  *v69 = 0;
                  if ( !v65 )
                    goto LABEL_333;
                }
                v70 = v27;
                v71 = v29;
                while ( *v71 )
                {
                  ++v71;
                  if ( !--v70 )
                  {
                    v39 = 0;
                    v72 = -1073741811;
                    goto LABEL_103;
                  }
                }
                v202 = v38;
                v39 = v27 - v70;
                v72 = 0;
LABEL_103:
                if ( v72 < 0 )
                  goto LABEL_61;
                v73 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v74 = 2147483646;
                v75 = L"\"";
                v76 = &v29[v39];
                do
                {
                  if ( !v74 )
                    break;
                  if ( !*v75 )
                    break;
                  *v76++ = *v75++;
                  --v74;
                  --v73;
                }
                while ( v73 );
                v77 = v76 - 1;
                if ( v73 )
                  v77 = v76;
                *v77 = 0;
                if ( !v73 )
                  goto LABEL_333;
                if ( (int)RtlStringCchPrintfW(v211, 17, L"%lx", a5) < 0 )
                  goto LABEL_61;
                v78 = v27;
                v79 = v29;
                while ( *v79 )
                {
                  ++v79;
                  if ( !--v78 )
                  {
                    v39 = 0;
                    v80 = -1073741811;
                    goto LABEL_118;
                  }
                }
                v39 = v27 - v78;
                v80 = 0;
LABEL_118:
                if ( v80 < 0 )
                  goto LABEL_61;
                v81 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v82 = 2147483646;
                v83 = &v29[v39];
                v84 = L" \"";
                do
                {
                  if ( !v82 )
                    break;
                  if ( !*v84 )
                    break;
                  *v83++ = *v84++;
                  --v82;
                  --v81;
                }
                while ( v81 );
                v85 = v83 - 1;
                if ( v81 )
                  v85 = v83;
                *v85 = 0;
                if ( !v81 )
                  goto LABEL_333;
                v86 = v27;
                v87 = v29;
                while ( *v87 )
                {
                  ++v87;
                  if ( !--v86 )
                  {
                    v88 = v202;
                    v39 = 0;
                    v89 = -1073741811;
                    goto LABEL_132;
                  }
                }
                v88 = v202;
                v39 = v27 - v86;
                v89 = 0;
LABEL_132:
                if ( v89 < 0 )
                  goto LABEL_61;
                v90 = v27 - v39;
                if ( v27 - v39 <= 1 )
                {
                  if ( v211[0] )
                    goto LABEL_333;
                }
                else
                {
                  v91 = 2147483646;
                  v92 = v211;
                  v93 = &v29[v39];
                  do
                  {
                    if ( !v91 )
                      break;
                    if ( !*v92 )
                      break;
                    *v93++ = *v92++;
                    --v91;
                    --v90;
                  }
                  while ( v90 );
                  v94 = v93 - 1;
                  if ( v90 )
                    v94 = v93;
                  *v94 = 0;
                  if ( !v90 )
                    goto LABEL_333;
                  v88 = v202;
                }
                v95 = v27;
                v96 = v29;
                while ( *v96 )
                {
                  ++v96;
                  if ( !--v95 )
                  {
                    v39 = 0;
                    v97 = -1073741811;
                    goto LABEL_147;
                  }
                }
                v202 = v88;
                v39 = v27 - v95;
                v97 = 0;
LABEL_147:
                if ( v97 < 0 )
                  goto LABEL_61;
                v98 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v99 = 2147483646;
                v100 = L"\"";
                v101 = &v29[v39];
                do
                {
                  if ( !v99 )
                    break;
                  if ( !*v100 )
                    break;
                  *v101++ = *v100++;
                  --v99;
                  --v98;
                }
                while ( v98 );
                v102 = v101 - 1;
                if ( v98 )
                  v102 = v101;
                *v102 = 0;
                if ( !v98 )
                  goto LABEL_333;
                v103 = v27;
                v104 = v29;
                while ( *v104 )
                {
                  ++v104;
                  if ( !--v103 )
                  {
                    v39 = 0;
                    v105 = -1073741811;
                    goto LABEL_161;
                  }
                }
                v39 = v27 - v103;
                v105 = 0;
LABEL_161:
                if ( v105 < 0 )
                  goto LABEL_61;
                v106 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v107 = 2147483646;
                v108 = &v29[v39];
                v109 = L" \"";
                do
                {
                  if ( !v107 )
                    break;
                  if ( !*v109 )
                    break;
                  *v108++ = *v109++;
                  --v107;
                  --v106;
                }
                while ( v106 );
                v110 = v108 - 1;
                if ( v106 )
                  v110 = v108;
                *v110 = 0;
                if ( !v106 )
                  goto LABEL_333;
                v205 = 0;
                if ( (int)RtlStringLengthWorkerW(v29, v27, &v205) < 0 )
                  goto LABEL_61;
                v39 = v205;
                v112 = v27 - v205;
                if ( v27 - v205 <= 1 )
                {
                  if ( *v202 )
                    goto LABEL_343;
                }
                else
                {
                  v113 = &v29[v205];
                  v114 = 2147483646;
                  v115 = v202;
                  do
                  {
                    if ( !v114 )
                      break;
                    if ( !*v115 )
                      break;
                    *v113++ = *v115++;
                    --v114;
                    --v112;
                  }
                  while ( v112 );
                  v39 = v205;
                  v116 = v113 - 1;
                  if ( v112 )
                    v116 = v113;
                  *v116 = 0;
                  if ( !v112 )
                  {
                    dwCreationFlags = 2304;
                    goto LABEL_334;
                  }
                }
                v117 = v27;
                v118 = v29;
                while ( *v118 )
                {
                  ++v118;
                  if ( !--v117 )
                  {
                    v39 = 0;
                    v119 = v111;
                    goto LABEL_184;
                  }
                }
                v39 = v27 - v117;
                v119 = 0;
LABEL_184:
                if ( v119 < 0 )
                  goto LABEL_61;
                v120 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v121 = 2147483646;
                v122 = L"\"";
                v123 = &v29[v39];
                do
                {
                  if ( !v121 )
                    break;
                  if ( !*v122 )
                    break;
                  *v123++ = *v122++;
                  --v121;
                  --v120;
                }
                while ( v120 );
                v124 = v123 - 1;
                if ( v120 )
                  v124 = v123;
                *v124 = 0;
                if ( !v120 )
                  goto LABEL_333;
                if ( (int)RtlStringCchPrintfW(v211, 17, L"%hx", 0) < 0 )
                  goto LABEL_61;
                v125 = v27;
                v126 = v29;
                while ( *v126 )
                {
                  ++v126;
                  if ( !--v125 )
                  {
                    v39 = 0;
                    v127 = -1073741811;
                    goto LABEL_199;
                  }
                }
                v39 = v27 - v125;
                v127 = 0;
LABEL_199:
                if ( v127 < 0 )
                  goto LABEL_61;
                v128 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v129 = 2147483646;
                v130 = &v29[v39];
                v131 = L" \"";
                do
                {
                  if ( !v129 )
                    break;
                  if ( !*v131 )
                    break;
                  *v130++ = *v131++;
                  --v129;
                  --v128;
                }
                while ( v128 );
                v132 = v130 - 1;
                if ( v128 )
                  v132 = v130;
                *v132 = 0;
                if ( !v128 )
                  goto LABEL_333;
                v133 = v27;
                v134 = v29;
                while ( *v134 )
                {
                  ++v134;
                  if ( !--v133 )
                  {
                    v39 = 0;
                    v135 = -1073741811;
                    goto LABEL_213;
                  }
                }
                v39 = v27 - v133;
                v135 = 0;
LABEL_213:
                if ( v135 < 0 )
                  goto LABEL_61;
                v136 = v27 - v39;
                if ( v27 - v39 <= 1 )
                {
                  if ( v211[0] )
                    goto LABEL_333;
                }
                else
                {
                  v137 = 2147483646;
                  v138 = v211;
                  v139 = &v29[v39];
                  do
                  {
                    if ( !v137 )
                      break;
                    if ( !*v138 )
                      break;
                    *v139++ = *v138++;
                    --v137;
                    --v136;
                  }
                  while ( v136 );
                  v140 = v139 - 1;
                  if ( v136 )
                    v140 = v139;
                  *v140 = 0;
                  if ( !v136 )
                    goto LABEL_333;
                }
                v141 = v27;
                v142 = v29;
                while ( *v142 )
                {
                  ++v142;
                  if ( !--v141 )
                  {
                    v39 = 0;
                    v143 = -1073741811;
                    goto LABEL_227;
                  }
                }
                v39 = v27 - v141;
                v143 = 0;
LABEL_227:
                if ( v143 < 0 )
                  goto LABEL_61;
                v144 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v145 = 2147483646;
                v146 = L"\"";
                v147 = &v29[v39];
                do
                {
                  if ( !v145 )
                    break;
                  if ( !*v146 )
                    break;
                  *v147++ = *v146++;
                  --v145;
                  --v144;
                }
                while ( v144 );
                v148 = v147 - 1;
                if ( v144 )
                  v148 = v147;
                *v148 = 0;
                if ( !v144 )
                  goto LABEL_333;
                if ( (int)RtlStringCchPrintfW(v211, 17, L"%I64x", v206) < 0 )
                  goto LABEL_61;
                v149 = v27;
                v150 = v29;
                do
                {
                  if ( !*v150 )
                  {
                    v39 = v27 - v149;
                    v50 = 0;
                    goto LABEL_60;
                  }
                  ++v150;
                  --v149;
                }
                while ( v149 );
                v39 = 0;
                v50 = -1073741811;
LABEL_60:
                if ( v50 < 0 )
                  goto LABEL_61;
                v52 = v27 - v39;
                if ( v27 - v39 <= 1 )
                  goto LABEL_333;
                v53 = 2147483646;
                v54 = &v29[v39];
                v55 = L" \"";
                do
                {
                  if ( !v53 )
                    break;
                  if ( !*v55 )
                    break;
                  *v54++ = *v55++;
                  --v53;
                  --v52;
                }
                while ( v52 );
                v56 = v54 - 1;
                if ( v52 )
                  v56 = v54;
                *v56 = 0;
                if ( !v52 )
                  goto LABEL_333;
                v205 = 0;
                if ( (int)RtlStringLengthWorkerW(v29, v27, &v205) < 0 )
                  goto LABEL_61;
                v39 = v205;
                v57 = v27 - v205;
                if ( v27 - v205 <= 1 )
                {
                  if ( !v211[0] )
                    goto LABEL_84;
                }
                else
                {
                  v58 = 2147483646;
                  v59 = v211;
                  v60 = &v29[v205];
                  do
                  {
                    if ( !v58 )
                      break;
                    if ( !*v59 )
                      break;
                    *v60++ = *v59++;
                    --v58;
                    --v57;
                  }
                  while ( v57 );
                  v61 = v60 - 1;
                  if ( v57 )
                    v61 = v60;
                  *v61 = 0;
                  if ( v57 )
                  {
LABEL_84:
                    v62 = v27;
                    v63 = v29;
                    while ( *v63 )
                    {
                      ++v63;
                      if ( !--v62 )
                      {
                        v39 = 0;
                        v64 = -1073741811;
                        goto LABEL_242;
                      }
                    }
                    v39 = v27 - v62;
                    v64 = 0;
LABEL_242:
                    if ( v64 < 0 )
                      goto LABEL_61;
                    v151 = v27 - v39;
                    if ( v27 - v39 > 1 )
                    {
                      v152 = 2147483646;
                      v153 = L"\"";
                      v154 = &v29[v39];
                      do
                      {
                        if ( !v152 )
                          break;
                        if ( !*v153 )
                          break;
                        *v154++ = *v153++;
                        --v152;
                        --v151;
                      }
                      while ( v151 );
                      v155 = v154 - 1;
                      if ( v151 )
                        v155 = v154;
                      *v155 = 0;
                      if ( v151 )
                      {
                        if ( (int)RtlStringCchPrintfW(v211, 17, L"%p", v203) < 0 )
                          goto LABEL_61;
                        v156 = v27;
                        v157 = v29;
                        while ( *v157 )
                        {
                          ++v157;
                          if ( !--v156 )
                          {
                            v39 = 0;
                            v158 = -1073741811;
                            goto LABEL_257;
                          }
                        }
                        v39 = v27 - v156;
                        v158 = 0;
LABEL_257:
                        if ( v158 < 0 )
                          goto LABEL_61;
                        v159 = v27 - v39;
                        if ( v27 - v39 > 1 )
                        {
                          v160 = 2147483646;
                          v161 = &v29[v39];
                          v162 = L" \"";
                          do
                          {
                            if ( !v160 )
                              break;
                            if ( !*v162 )
                              break;
                            *v161++ = *v162++;
                            --v160;
                            --v159;
                          }
                          while ( v159 );
                          v163 = v161 - 1;
                          if ( v159 )
                            v163 = v161;
                          *v163 = 0;
                          if ( v159 )
                          {
                            v164 = v27;
                            v165 = v29;
                            while ( *v165 )
                            {
                              ++v165;
                              if ( !--v164 )
                              {
                                v39 = 0;
                                v166 = -1073741811;
                                goto LABEL_271;
                              }
                            }
                            v39 = v27 - v164;
                            v166 = 0;
LABEL_271:
                            if ( v166 < 0 )
                              goto LABEL_61;
                            v167 = v27 - v39;
                            if ( v27 - v39 <= 1 )
                            {
                              if ( !v211[0] )
                              {
LABEL_280:
                                v172 = v27;
                                v173 = v29;
                                while ( *v173 )
                                {
                                  ++v173;
                                  if ( !--v172 )
                                  {
                                    v39 = 0;
                                    v174 = -1073741811;
                                    goto LABEL_285;
                                  }
                                }
                                v39 = v27 - v172;
                                v174 = 0;
LABEL_285:
                                if ( v174 < 0 )
                                  goto LABEL_61;
                                v175 = v27 - v39;
                                if ( v27 - v39 > 1 )
                                {
                                  v176 = 2147483646;
                                  v177 = L"\"";
                                  v178 = &v29[v39];
                                  do
                                  {
                                    if ( !v176 )
                                      break;
                                    if ( !*v177 )
                                      break;
                                    *v178++ = *v177++;
                                    --v176;
                                    --v175;
                                  }
                                  while ( v175 );
                                  v179 = v178 - 1;
                                  if ( v175 )
                                    v179 = v178;
                                  *v179 = 0;
                                  if ( v175 )
                                  {
                                    v180 = v27;
                                    v181 = v29;
                                    while ( *v181 )
                                    {
                                      ++v181;
                                      if ( !--v180 )
                                      {
                                        v182 = 0;
                                        v183 = -1073741811;
                                        goto LABEL_299;
                                      }
                                    }
                                    v182 = v27 - v180;
                                    v183 = 0;
LABEL_299:
                                    if ( v183 >= 0 )
                                    {
                                      v184 = v27 - v182;
                                      if ( v27 - v182 <= 1 )
                                        goto LABEL_346;
                                      v185 = &v29[v182];
                                      do
                                      {
                                        if ( !v31 )
                                          break;
                                        if ( !*v42 )
                                          break;
                                        *v185++ = *v42++;
                                        --v31;
                                        --v184;
                                      }
                                      while ( v184 );
                                      v186 = v185 - 1;
                                      if ( v184 )
                                        v186 = v185;
                                      *v186 = 0;
                                      if ( v184 )
                                      {
                                        if ( (int)RtlStringCchCatExW(
                                                    (_DWORD)v29,
                                                    v27,
                                                    v20,
                                                    (_DWORD)v177,
                                                    bInheritHandles,
                                                    2304) >= 0
                                          && (int)RtlStringCchCatExW(
                                                    (_DWORD)v29,
                                                    v27,
                                                    (unsigned int)L"\"",
                                                    v187,
                                                    bInheritHandlesa,
                                                    2048) >= 0 )
                                        {
                                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
                                          {
                                            WPP_SF_S(
                                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                                              25,
                                              WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                              v29);
                                          }
                                          v188 = v206;
                                          DevRtlWriteTextLog(v206, 0x2000000, 65542, "Creating process: %ws", v207);
                                          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
                                          memset_0(&StartupInfo, 0, sizeof(StartupInfo));
                                          StartupInfo.cb = 104;
                                          StartupInfo.lpDesktop = (LPWSTR)&qword_18001C3B0;
                                          if ( !CreateProcessW(
                                                  Str,
                                                  v29,
                                                  0,
                                                  0,
                                                  0,
                                                  8u,
                                                  0,
                                                  0,
                                                  &StartupInfo,
                                                  &ProcessInformation) )
                                          {
                                            v189 = GetLastError();
                                            ExitCode[0] = v189;
                                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                            {
                                              WPP_SF_d(
                                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                26,
                                                WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                                v189);
                                            }
                                            goto LABEL_62;
                                          }
                                          CloseHandle(ProcessInformation.hThread);
                                          hProcess = ProcessInformation.hProcess;
                                          v191 = WaitForSingleObjectEx(ProcessInformation.hProcess, 0xFFFFFFFF, 0);
                                          if ( v191 )
                                          {
                                            if ( v191 == 258 )
                                            {
                                              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                              {
                                                WPP_SF_d(
                                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                  30,
                                                  WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                                  258);
                                              }
                                              ExitCode[0] = 1460;
                                              if ( !TerminateProcess(hProcess, 0x5B4u)
                                                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                              {
                                                v196 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                                                v197 = GetLastError();
                                                WPP_SF_d(
                                                  v196,
                                                  31,
                                                  WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                                  v197);
                                              }
                                              goto LABEL_381;
                                            }
                                            if ( v191 != -1 )
                                            {
                                              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                              {
                                                WPP_SF_d(
                                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                  33,
                                                  WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                                  v191);
                                              }
                                              ExitCode[0] = 13;
                                              goto LABEL_381;
                                            }
                                            v192 = GetLastError();
                                            ExitCode[0] = v192;
                                            v193 = WPP_GLOBAL_Control;
                                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                            {
                                              v194 = 32;
                                              goto LABEL_355;
                                            }
                                          }
                                          else
                                          {
                                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                            {
                                              WPP_SF_(
                                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                27,
                                                WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
                                            }
                                            if ( GetExitCodeProcess(hProcess, ExitCode) )
                                            {
                                              v195 = WPP_GLOBAL_Control;
                                              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                                              {
                                                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                                {
                                                  WPP_SF_d(
                                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                    29,
                                                    WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                                    ExitCode[0]);
                                                  v195 = WPP_GLOBAL_Control;
                                                }
                                                if ( v195 != &WPP_GLOBAL_Control
                                                  && (*((_DWORD *)v195 + 7) & 0x40000) != 0 )
                                                {
                                                  WPP_SF_d(
                                                    v195[2],
                                                    34,
                                                    WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                                    ExitCode[0]);
                                                }
                                              }
                                              DevRtlWriteTextLog(
                                                v188,
                                                0x2000000,
                                                65542,
                                                "Driver store delete process exited with code 0x%08x",
                                                ExitCode[0]);
                                              if ( ExitCode[0] == 3010 )
                                              {
                                                ExitCode[0] = 0;
                                                if ( v204 )
                                                  *v204 = 1;
                                              }
                                              goto LABEL_381;
                                            }
                                            v192 = GetLastError();
                                            ExitCode[0] = v192;
                                            v193 = WPP_GLOBAL_Control;
                                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                            {
                                              v194 = 28;
LABEL_355:
                                              WPP_SF_d(
                                                v193[2],
                                                v194,
                                                WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids,
                                                v192);
                                            }
                                          }
LABEL_381:
                                          if ( hProcess )
                                            CloseHandle(hProcess);
                                          goto LABEL_62;
                                        }
                                      }
                                      else
                                      {
LABEL_346:
                                        RtlStringExHandleOtherFlagsW(v29, 2 * v27, v182, &v203, &v204, 2048);
                                      }
                                    }
LABEL_61:
                                    ExitCode[0] = 13;
LABEL_62:
                                    RtlFreeHeap(PnpHeapHandle, 0, v29);
                                    LastError = ExitCode[0];
                                    goto LABEL_63;
                                  }
                                }
                              }
                            }
                            else
                            {
                              v168 = 2147483646;
                              v169 = v211;
                              v170 = &v29[v39];
                              do
                              {
                                if ( !v168 )
                                  break;
                                if ( !*v169 )
                                  break;
                                *v170++ = *v169++;
                                --v168;
                                --v167;
                              }
                              while ( v167 );
                              v171 = v170 - 1;
                              if ( v167 )
                                v171 = v170;
                              *v171 = 0;
                              if ( v167 )
                                goto LABEL_280;
                            }
                          }
                        }
                      }
                    }
LABEL_333:
                    dwCreationFlags = 2048;
LABEL_334:
                    RtlStringExHandleOtherFlagsW(v29, 2 * v27, v39, &v203, &v204, dwCreationFlags);
                    goto LABEL_61;
                  }
                }
LABEL_343:
                dwCreationFlags = 2304;
                goto LABEL_334;
              }
            }
          }
          ExitCode[0] = 123;
          goto LABEL_62;
        }
      }
      goto LABEL_321;
    }
    goto LABEL_320;
  }
  ExitCode[0] = GetLastError();
  LastError = ExitCode[0];
  if ( !ExitCode[0] )
  {
    v20 = (__int64)a4;
    if ( !a4 )
      goto LABEL_320;
    v21 = v13 + v18;
    goto LABEL_23;
  }
LABEL_63:
  if ( P )
  {
    RtlFreeHeap(PnpHeapHandle, 0, P);
    LastError = ExitCode[0];
  }
LABEL_65:
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
    return LastError;
  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  return ExitCode[0];
}

```

## disassembly

```asm
0x180004180  mov     r11, rsp
0x180004183  push    rbp
0x180004184  push    rbx
0x180004185  lea     rbp, [r11-2B8h]
0x18000418c  sub     rsp, 3A8h
0x180004193  mov     rax, cs:__security_cookie
0x18000419a  xor     rax, rsp
0x18000419d  mov     [rbp+2B0h+var_50], rax
0x1800041a4  mov     rbx, [rbp+2B0h+arg_28]
0x1800041ab  xorps   xmm0, xmm0
0x1800041ae  mov     [r11-20h], rdi
0x1800041b2  mov     r10, r8
0x1800041b5  xor     edi, edi
0x1800041b7  mov     [r11-30h], r13
0x1800041bb  xor     eax, eax
0x1800041bd  mov     [r11-40h], r15
0x1800041c1  mov     dword ptr [rbp+2B0h+StartupInfo.hStdError], eax
0x1800041c4  mov     r15, r9
0x1800041c7  mov     qword ptr [rbp+2B0h+ProcessInformation.dwProcessId], rax
0x1800041cb  mov     r13, rdx
0x1800041ce  mov     [rsp+3B0h+var_338], r8
0x1800041d3  mov     [rsp+3B0h+var_358], rdx
0x1800041d8  mov     [rsp+3B0h+var_350], rcx
0x1800041dd  mov     [rsp+3B0h+var_348], rbx
0x1800041e2  mov     [rsp+3B0h+ExitCode], edi
0x1800041e6  movups  xmmword ptr [rbp+2B0h+StartupInfo.cb], xmm0
0x1800041ea  movups  xmmword ptr [rbp+2B0h+StartupInfo.lpDesktop], xmm0
0x1800041ee  movups  xmmword ptr [rbp+2B0h+StartupInfo.dwX], xmm0
0x1800041f2  movups  xmmword ptr [rbp+2B0h+StartupInfo.dwXCountChars], xmm0
0x1800041f6  movups  xmmword ptr [rbp+2B0h+StartupInfo.wShowWindow], xmm0
0x1800041fa  movups  xmmword ptr [rbp+2B0h+StartupInfo.hStdInput], xmm0
0x1800041fe  movups  xmmword ptr [rbp+2B0h+ProcessInformation.hProcess], xmm0
0x180004202  mov     rcx, cs:WPP_GLOBAL_Control
0x180004209  lea     rax, WPP_GLOBAL_Control
0x180004210  cmp     rcx, rax
0x180004213  jnz     loc_18000517B
0x180004219  test    rbx, rbx
0x18000421c  jnz     loc_1800051A7
0x180004222  mov     eax, [rbp+2B0h+arg_20]
0x180004228  lea     r9, aDeleteFlags0x0; "Delete flags: 0x%08X"
0x18000422f  mov     edx, 2000000h
0x180004234  mov     dword ptr [rsp+3B0h+bInheritHandles], eax
0x180004238  mov     r8d, 4
0x18000423e  mov     [rsp+3A0h], rsi
0x180004246  mov     rcx, r10
0x180004249  call    cs:__imp_DevRtlWriteTextLog
0x18000424f  lea     rcx, [rbp+2B0h+Str]
0x180004253  call    GetDeviceInstallerFilename
0x180004258  test    eax, eax
0x18000425a  jz      loc_180005142
0x180004260  mov     [rsp+3B0h+var_20], r12
0x180004268  lea     rcx, [rbp+2B0h+Str]; Str
0x18000426c  mov     edx, 5Ch ; '\'; Ch
0x180004271  mov     [rsp+3B0h+var_30], r14
0x180004279  call    cs:__imp_wcsrchr
0x18000427f  test    rax, rax
0x180004282  jz      loc_180005134
0x180004288  add     rax, 2
0x18000428c  mov     [rbp+2B0h+var_330], rax
0x180004290  jz      loc_180005134
0x180004296  mov     r14d, 7FFFh
0x18000429c  mov     ecx, r14d
0x18000429f  nop
0x1800042a0  cmp     [rax], di
0x1800042a3  jz      short loc_1800042BD
0x1800042a5  add     rax, 2
0x1800042a9  sub     rcx, 1
0x1800042ad  jnz     short loc_1800042A0
0x1800042af  mov     r12d, 0C000000Dh
0x1800042b5  mov     r14, rdi
0x1800042b8  mov     eax, r12d
0x1800042bb  jmp     short loc_1800042C8
0x1800042bd  sub     r14, rcx
0x1800042c0  mov     eax, edi
0x1800042c2  mov     r12d, 0C000000Dh
0x1800042c8  test    eax, eax
0x1800042ca  js      loc_180005134
0x1800042d0  mov     rcx, r13; Src
0x1800042d3  call    StringSearchAndReplace
0x1800042d8  mov     [rbp+2B0h+P], rax
0x1800042dc  test    rax, rax
0x1800042df  jz      loc_1800051AE
0x1800042e5  mov     r13, rax
0x1800042e8  mov     [rsp+3B0h+var_358], rax
0x1800042ed  mov     edi, 104h
0x1800042f2  mov     rsi, r14
0x1800042f5  mov     ecx, edi
0x1800042f7  mov     rax, r13
0x1800042fa  nop     word ptr [rax+rax+00h]
0x180004300  cmp     word ptr [rax], 0
0x180004304  jz      short loc_180004317
0x180004306  add     rax, 2
0x18000430a  sub     rcx, 1
0x18000430e  jnz     short loc_180004300
0x180004310  xor     edi, edi
0x180004312  mov     eax, r12d
0x180004315  jmp     short loc_180004321
0x180004317  sub     rdi, rcx
0x18000431a  mov     [rsp+3B0h+var_358], r13
0x18000431f  xor     eax, eax
0x180004321  test    eax, eax
0x180004323  js      loc_18000515C
0x180004329  mov     rcx, r15; Src
0x18000432c  call    StringSearchAndReplace
0x180004331  mov     r13, rax
0x180004334  test    rax, rax
0x180004337  jz      loc_1800051C4
0x18000433d  lea     r8, [r14+rdi]
0x180004341  mov     edx, 20Ah
0x180004346  mov     rax, r13
0x180004349  mov     ecx, edx
0x18000434b  nop     dword ptr [rax+rax+00h]
0x180004350  cmp     word ptr [rax], 0
0x180004354  jz      short loc_180004367
0x180004356  add     rax, 2
0x18000435a  sub     rcx, 1
0x18000435e  jnz     short loc_180004350
0x180004360  xor     edx, edx
0x180004362  mov     eax, r12d
0x180004365  jmp     short loc_180004376
0x180004367  sub     rdx, rcx
0x18000436a  mov     rcx, [rsp+3B0h+var_358]
0x18000436f  mov     [rsp+3B0h+var_358], rcx
0x180004374  xor     eax, eax
0x180004376  test    eax, eax
0x180004378  js      loc_18000515C
0x18000437e  lea     rdi, [rdx+4Ah]
0x180004382  mov     ebx, 8
0x180004387  add     rdi, r8
0x18000438a  lea     r15, [rdi+rdi]
0x18000438e  cmp     r15, 0F42400h
0x180004395  ja      loc_180005161
0x18000439b  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x1800043a2  mov     r8, r15; Size
0x1800043a5  mov     edx, ebx; Flags
0x1800043a7  call    cs:__imp_RtlAllocateHeap
0x1800043ad  mov     rsi, rax
0x1800043b0  test    rax, rax
0x1800043b3  jz      loc_180005161
0x1800043b9  test    rdi, rdi
0x1800043bc  jz      loc_1800051DF
0x1800043c2  cmp     rdi, 7FFFFFFFh
0x1800043c9  ja      loc_1800051DA
0x1800043cf  mov     rdx, [rbp+2B0h+var_330]
0x1800043d3  mov     r12d, 7FFFFFFEh
0x1800043d9  mov     ecx, r12d
0x1800043dc  mov     r8, rdi
0x1800043df  mov     r9, rax
0x1800043e2  test    rcx, rcx
0x1800043e5  jz      short loc_180004404
0x1800043e7  movzx   eax, word ptr [rdx]
0x1800043ea  test    ax, ax
0x1800043ed  jz      short loc_180004404
0x1800043ef  mov     [r9], ax
0x1800043f3  add     rdx, 2
0x1800043f7  add     r9, 2
0x1800043fb  dec     rcx
0x1800043fe  sub     r8, 1
0x180004402  jnz     short loc_1800043E2
0x180004404  test    r8, r8
0x180004407  lea     rcx, [r9-2]
0x18000440b  cmovnz  rcx, r9
0x18000440f  xor     eax, eax
0x180004411  mov     [rcx], ax
0x180004414  test    r8, r8
0x180004417  jz      loc_1800051DF
0x18000441d  mov     r9d, 5
0x180004423  lea     r8, aLx; "%lx"
0x18000442a  mov     edx, 11h
0x18000442f  lea     rcx, [rbp+2B0h+var_290]
0x180004433  call    RtlStringCchPrintfW
0x180004438  test    eax, eax
0x18000443a  js      loc_180004513
0x180004440  mov     rcx, rdi
0x180004443  mov     rax, rsi
0x180004446  cmp     word ptr [rax], 0
0x18000444a  jz      short loc_180004465
0x18000444c  add     rax, 2
0x180004450  sub     rcx, 1
0x180004454  jnz     short loc_180004446
0x180004456  mov     r11, [rsp+3B0h+var_358]
0x18000445b  xor     r10d, r10d
0x18000445e  mov     eax, 0C000000Dh
0x180004463  jmp     short loc_180004477
0x180004465  mov     r11, [rsp+3B0h+var_358]
0x18000446a  mov     r10, rdi
0x18000446d  sub     r10, rcx
0x180004470  mov     [rsp+3B0h+var_358], r11
0x180004475  xor     eax, eax
0x180004477  test    eax, eax
0x180004479  js      loc_180004513
0x18000447f  mov     rdx, rdi
0x180004482  sub     rdx, r10
0x180004485  cmp     rdx, 1
0x180004489  jbe     loc_1800051F7
0x18000448f  lea     r14, asc_18001C3A8; " \""
0x180004496  mov     rcx, r12
0x180004499  mov     r8, r14
0x18000449c  lea     r9, [rsi+r10*2]
0x1800044a0  test    rcx, rcx
0x1800044a3  jz      short loc_1800044C3
0x1800044a5  movzx   eax, word ptr [r8]
0x1800044a9  test    ax, ax
0x1800044ac  jz      short loc_1800044C3
0x1800044ae  mov     [r9], ax
0x1800044b2  add     r8, 2
0x1800044b6  add     r9, 2
0x1800044ba  dec     rcx
0x1800044bd  sub     rdx, 1
0x1800044c1  jnz     short loc_1800044A0
0x1800044c3  test    rdx, rdx
0x1800044c6  lea     rcx, [r9-2]
0x1800044ca  cmovnz  rcx, r9
0x1800044ce  xor     eax, eax
0x1800044d0  mov     [rcx], ax
0x1800044d3  test    rdx, rdx
0x1800044d6  jz      loc_1800051F7
0x1800044dc  mov     rcx, rdi
0x1800044df  mov     rax, rsi
0x1800044e2  cmp     word ptr [rax], 0
0x1800044e6  jz      loc_1800046A3
0x1800044ec  add     rax, 2
0x1800044f0  sub     rcx, 1
0x1800044f4  jnz     short loc_1800044E2
0x1800044f6  xor     r10d, r10d
0x1800044f9  mov     eax, 0C000000Dh
0x1800044fe  jmp     loc_1800046B0
0x180004503  mov     r10, rdi
0x180004506  sub     r10, rcx
0x180004509  xor     eax, eax
0x18000450b  test    eax, eax
0x18000450d  jns     loc_1800045A1
0x180004513  mov     ebx, 0Dh
0x180004518  mov     [rsp+3B0h+ExitCode], ebx
0x18000451c  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180004523  mov     r8, rsi; P
0x180004526  xor     edx, edx; Flags
0x180004528  call    cs:__imp_RtlFreeHeap
0x18000452e  mov     ebx, [rsp+3B0h+ExitCode]
0x180004532  mov     r8, [rbp+2B0h+P]; P
0x180004536  test    r8, r8
0x180004539  jnz     loc_1800054F7
0x18000453f  mov     r12, [rsp+3B0h+var_20]
0x180004547  mov     r14, [rsp+3B0h+var_30]
0x18000454f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004556  lea     rax, WPP_GLOBAL_Control
0x18000455d  mov     r15, [rsp+3B0h+var_38]
0x180004565  mov     r13, [rsp+3B0h+var_28]
0x18000456d  mov     rdi, [rsp+3B0h+var_18]
0x180004575  mov     rsi, [rsp+3A0h]
0x18000457d  cmp     rcx, rax
0x180004580  jnz     loc_18000550F
0x180004586  mov     eax, ebx
0x180004588  mov     rcx, [rbp+2B0h+var_50]
0x18000458f  xor     rcx, rsp; StackCookie
0x180004592  call    __security_check_cookie
0x180004597  add     rsp, 3A8h
0x18000459e  pop     rbx
0x18000459f  pop     rbp
0x1800045a0  retn
0x1800045a1  mov     rdx, rdi
0x1800045a4  sub     rdx, r10
0x1800045a7  cmp     rdx, 1
0x1800045ab  jbe     loc_1800051F7
0x1800045b1  mov     rcx, r12
0x1800045b4  lea     r8, [rsi+r10*2]
0x1800045b8  mov     r9, r14
0x1800045bb  nop     dword ptr [rax+rax+00h]
0x1800045c0  test    rcx, rcx
0x1800045c3  jz      short loc_1800045E3
0x1800045c5  movzx   eax, word ptr [r9]
0x1800045c9  test    ax, ax
0x1800045cc  jz      short loc_1800045E3
0x1800045ce  mov     [r8], ax
0x1800045d2  add     r9, 2
0x1800045d6  add     r8, 2
0x1800045da  dec     rcx
0x1800045dd  sub     rdx, 1
0x1800045e1  jnz     short loc_1800045C0
0x1800045e3  test    rdx, rdx
0x1800045e6  lea     rcx, [r8-2]
0x1800045ea  cmovnz  rcx, r8
0x1800045ee  xor     eax, eax
0x1800045f0  mov     [rcx], ax
0x1800045f3  test    rdx, rdx
0x1800045f6  jz      loc_1800051F7
0x1800045fc  lea     r8, [rsp+3B0h+var_340]
0x180004601  mov     [rsp+3B0h+var_340], rax
0x180004606  mov     rdx, rdi
0x180004609  mov     rcx, rsi
0x18000460c  call    RtlStringLengthWorkerW
0x180004611  test    eax, eax
0x180004613  js      loc_180004513
0x180004619  mov     r10, [rsp+3B0h+var_340]
0x18000461e  mov     rdx, rdi
0x180004621  sub     rdx, r10
0x180004624  cmp     rdx, 1
0x180004628  jbe     loc_180005255
0x18000462e  mov     rcx, r12
0x180004631  lea     r9, [rbp+2B0h+var_290]
  ... truncated ...
```
