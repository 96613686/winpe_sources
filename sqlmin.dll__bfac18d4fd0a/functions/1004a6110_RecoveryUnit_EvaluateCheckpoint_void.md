# RecoveryUnit::EvaluateCheckpoint(void)

- ea: `0x1004a6110`
- end: `0x1004a6a63`
- name: `?EvaluateCheckpoint@RecoveryUnit@@QEAA?AW4CkptReqType@@XZ`
- size: `2387`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1004a74a0`
- `0x101cf2090`

## callees

- `0x100401490`
- `0x100402000`
- `0x100402d60`
- `0x100403030`
- `0x100432e60`
- `0x10044ddd0`
- `0x10044de00`
- `0x10044de50`
- `0x1004a5850`
- `0x1004a6070`
- `0x1004a6110`
- `0x1004a6a70`
- `0x1004a6ca0`
- `0x1005f1f00`
- `0x10064e040`
- `0x10064e1f0`
- `0x10064e3a0`
- `0x10064e550`
- `0x10064e700`
- `0x10072d4d0`
- `0x10072d690`
- `0x101c10070`
- `0x101c11120`
- `0x101c14060`
- `0x101d01080`
- `0x101d01360`
- `0x101d01e80`
- `0x101d021a0`
- `0x1023ae3e0`
- `0x1023aee60`
- `0x1023af450`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101d02ca1`
- `KERNEL32!QueryPerformanceCounter` at `0x101d02ced`
- `KERNEL32!QueryPerformanceCounter` at `0x101d02ca1`
- `KERNEL32!QueryPerformanceCounter` at `0x101d02ced`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004a65b2`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101d02c3d`
- `sqldk!?SOS_OS_MemoryModel@@3W4SOS_MemoryModel@@A` at `0x1004a6257`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101d02cb1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101d02c8b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101d02cdb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1005f8e5b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d0246b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d024de`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d030c4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d0311c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1005f8e5b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d0246b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d024de`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d030c4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d0311c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d035d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d035d8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d0253b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02587`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02708`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d0275c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d027b0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d0286e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d028c2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02916`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02ad7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02b2b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02b7f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02dac`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02e5a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02e73`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03412`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03466`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d034b2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d037b9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d037cf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d039b8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03a0c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03a58`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03b37`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03b83`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03cf3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03e4b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03e9f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03eeb`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d04083`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d0409c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d040b5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d0253b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02587`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02708`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d0275c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d027b0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d0286e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d028c2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02916`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02ad7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02b2b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02b7f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02dac`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02e5a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d02e73`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03412`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03466`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d034b2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d037b9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d037cf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d039b8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03a0c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03a58`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03b37`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03b83`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03cf3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03e4b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03e9f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d03eeb`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d04083`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d0409c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d040b5`
- `sqldk!SystemThread_TlsIndex` at `0x1004a669e`
- `sqldk!SystemThread_TlsIndex` at `0x1004a66e4`
- `sqldk!SystemThread_TlsIndex` at `0x1004a6729`
- `sqldk!SystemThread_TlsIndex` at `0x1004a6893`
- `sqldk!SystemThread_TlsIndex` at `0x1004a68d8`
- `sqldk!SystemThread_TlsIndex` at `0x1004a8034`
- `sqldk!SystemThread_TlsIndex` at `0x100573149`
- `sqldk!SystemThread_TlsIndex` at `0x10057318e`
- `sqldk!SystemThread_TlsIndex` at `0x1005731cf`
- `sqldk!SystemThread_TlsIndex` at `0x101d0250b`
- `sqldk!SystemThread_TlsIndex` at `0x101d02557`
- `sqldk!SystemThread_TlsIndex` at `0x101d026d8`
- `sqldk!SystemThread_TlsIndex` at `0x101d0272c`
- `sqldk!SystemThread_TlsIndex` at `0x101d02780`
- `sqldk!SystemThread_TlsIndex` at `0x101d0283e`
- `sqldk!SystemThread_TlsIndex` at `0x101d02892`
- `sqldk!SystemThread_TlsIndex` at `0x101d028de`
- `sqldk!SystemThread_TlsIndex` at `0x101d02aa7`
- `sqldk!SystemThread_TlsIndex` at `0x101d02afb`
- `sqldk!SystemThread_TlsIndex` at `0x101d02b47`
- `sqldk!SystemThread_TlsIndex` at `0x101d02c5d`
- `sqldk!SystemThread_TlsIndex` at `0x101d033e1`
- `sqldk!SystemThread_TlsIndex` at `0x101d03436`
- `sqldk!SystemThread_TlsIndex` at `0x101d03482`
- `sqldk!SystemThread_TlsIndex` at `0x101d03988`
- `sqldk!SystemThread_TlsIndex` at `0x101d039dc`
- `sqldk!SystemThread_TlsIndex` at `0x101d03a28`
- `sqldk!SystemThread_TlsIndex` at `0x101d03b07`
- `sqldk!SystemThread_TlsIndex` at `0x101d03b53`
- `sqldk!SystemThread_TlsIndex` at `0x101d03e1b`
- `sqldk!SystemThread_TlsIndex` at `0x101d03e6f`
- `sqldk!SystemThread_TlsIndex` at `0x101d03ebb`
- `sqldk!SystemThread_TlsOffset` at `0x1004a66a8`
- `sqldk!SystemThread_TlsOffset` at `0x1004a66ed`
- `sqldk!SystemThread_TlsOffset` at `0x1004a6732`
- `sqldk!SystemThread_TlsOffset` at `0x1004a689c`
- `sqldk!SystemThread_TlsOffset` at `0x1004a68e1`
- `sqldk!SystemThread_TlsOffset` at `0x1004a803d`
- `sqldk!SystemThread_TlsOffset` at `0x100573152`
- `sqldk!SystemThread_TlsOffset` at `0x100573197`
- `sqldk!SystemThread_TlsOffset` at `0x1005731d8`
- `sqldk!SystemThread_TlsOffset` at `0x101d02514`
- `sqldk!SystemThread_TlsOffset` at `0x101d02560`
- `sqldk!SystemThread_TlsOffset` at `0x101d026e1`
- `sqldk!SystemThread_TlsOffset` at `0x101d02735`
- `sqldk!SystemThread_TlsOffset` at `0x101d02789`
- `sqldk!SystemThread_TlsOffset` at `0x101d02847`
- `sqldk!SystemThread_TlsOffset` at `0x101d0289b`
- `sqldk!SystemThread_TlsOffset` at `0x101d028e7`
- `sqldk!SystemThread_TlsOffset` at `0x101d02ab0`
- `sqldk!SystemThread_TlsOffset` at `0x101d02b04`
- `sqldk!SystemThread_TlsOffset` at `0x101d02b50`
- `sqldk!SystemThread_TlsOffset` at `0x101d02c66`
- `sqldk!SystemThread_TlsOffset` at `0x101d033eb`
- `sqldk!SystemThread_TlsOffset` at `0x101d0343f`
- `sqldk!SystemThread_TlsOffset` at `0x101d0348b`
- `sqldk!SystemThread_TlsOffset` at `0x101d03991`
- `sqldk!SystemThread_TlsOffset` at `0x101d039e5`
- `sqldk!SystemThread_TlsOffset` at `0x101d03a31`
- `sqldk!SystemThread_TlsOffset` at `0x101d03b10`
- `sqldk!SystemThread_TlsOffset` at `0x101d03b5c`
- `sqldk!SystemThread_TlsOffset` at `0x101d03e24`
- `sqldk!SystemThread_TlsOffset` at `0x101d03e78`
- `sqldk!SystemThread_TlsOffset` at `0x101d03ec4`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101d02d40`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101d02d40`

## string_xrefs

- `0x101d03a95`: `RU::EvaluateCheckpoint DB %d:%d give a slice back to data after %d evals. new Pie %I64d:%I64d:%I64d, recent force writes %d.`
- `0x101d03f28`: `RU::EvaluateCheckpoint DB %d:%d give a slice back to data after %d evals. new Pie %I64d:%I64d:%I64d, recent force writes %d.`

## pseudocode

```c
__int64 __fastcall RecoveryUnit::EvaluateCheckpoint(__int64 a1)
{
  __int16 v1; // r15
  int v2; // edi
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r14
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r10
  unsigned __int64 v10; // r11
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // bl
  __int64 v15; // r15
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  unsigned __int64 v20; // r12
  __int64 v21; // r13
  unsigned __int64 v22; // r14
  __int64 v23; // rcx
  unsigned __int16 v24; // r15
  __int64 v25; // rbx
  _DWORD *v26; // rax
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // r14
  unsigned __int64 v29; // r12
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // r15
  __int64 v34; // r13
  unsigned __int64 v35; // r8
  unsigned __int64 v36; // rax
  unsigned __int128 v37; // rax
  unsigned __int64 v38; // kr10_8
  unsigned __int64 v39; // rcx
  __int64 v40; // r12
  __int64 v41; // r14
  __int64 v42; // rax
  DirtyPageMgr *QuadPart; // rbx
  __int64 v44; // r15
  signed __int64 UniqueThread_low; // r12
  LSN v46; // xmm0_8
  __int64 v47; // rbx
  __int64 v48; // r12
  __int64 v49; // rax
  __int64 v50; // rcx
  unsigned __int64 v51; // r15
  unsigned __int64 v52; // rbx
  __int64 v53; // rax
  struct CSessionTraceFlags *v54; // rcx
  __int64 v55; // rax
  struct CSessionTraceFlags *v56; // rcx
  __int64 v57; // rax
  struct CSessionTraceFlags *v58; // rcx
  unsigned __int64 v59; // r15
  DWORD LowPart; // r8d
  DWORD v61; // eax
  DWORD v62; // r11d
  unsigned __int16 v63; // bx
  unsigned int HighPart; // r10d
  unsigned int v65; // r9d
  unsigned __int64 v66; // r12
  unsigned __int64 v67; // rdx
  unsigned __int64 v68; // r14
  __int64 v69; // rax
  struct CSessionTraceFlags *v70; // rcx
  __int64 v71; // rax
  struct CSessionTraceFlags *v72; // rcx
  unsigned __int64 v73; // rbx
  unsigned int v74; // r13d
  unsigned __int64 v75; // rbx
  unsigned __int64 v76; // rdi
  unsigned __int64 v77; // r14
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  struct CSessionTraceFlags *v82; // rcx
  _DWORD *v83; // rax
  unsigned __int8 v84; // r14
  __int64 v85; // rax
  struct CSessionTraceFlags *v86; // rcx
  __int64 v87; // rax
  struct CSessionTraceFlags *v88; // rcx
  __int64 v89; // rax
  struct CSessionTraceFlags *v90; // rcx
  __int64 v91; // rax
  struct CSessionTraceFlags *v92; // rcx
  __int64 v93; // rax
  struct CSessionTraceFlags *v94; // rcx
  double v95; // xmm3_8
  unsigned __int64 v96; // rax
  __int64 v97; // rbx
  __int64 v98; // rcx
  __int64 v99; // rcx
  unsigned __int64 v100; // rax
  unsigned __int64 v101; // rcx
  unsigned __int64 v102; // r12
  __int64 v103; // rax
  DirtyPageMgr *v104; // rcx
  __int64 v105; // rax
  struct CSessionTraceFlags *v106; // rcx
  __int64 v107; // rax
  struct CSessionTraceFlags *v108; // rcx
  __int64 v109; // rax
  struct CSessionTraceFlags *v110; // rcx
  unsigned __int64 v111; // rax
  unsigned __int128 v112; // rax
  unsigned __int64 v113; // kr30_8
  unsigned __int64 v114; // rcx
  char v115; // bl
  __int64 v116; // rax
  struct CSessionTraceFlags *v117; // rcx
  __int64 v118; // rax
  struct CSessionTraceFlags *v119; // rcx
  __int64 v120; // rax
  struct CSessionTraceFlags *v121; // rcx
  double v122; // xmm0_8
  double v123; // xmm0_8
  double v124; // xmm1_8
  const wchar_t *v125; // r9
  double v126; // xmm1_8
  unsigned __int64 i; // rbx
  __int64 v128; // rax
  struct CSessionTraceFlags *v129; // rcx
  __int64 v130; // rax
  struct CSessionTraceFlags *v131; // rcx
  __int64 v132; // rax
  struct CSessionTraceFlags *v133; // rcx
  double v134; // xmm0_8
  double v135; // xmm0_8
  double v136; // xmm3_8
  __int64 v137; // r14
  __int64 v138; // r8
  __int64 v139; // rcx
  DirtyPageMgr *v140; // rcx
  signed __int64 v141; // rax
  int v142; // r8d
  __int64 v143; // rcx
  __int64 v144; // rax
  __int64 v145; // rcx
  __int64 v146; // r15
  unsigned int v147; // r12d
  SQLServerLogMgr *v148; // r13
  unsigned __int64 v149; // rbx
  DWORD v150; // r14d
  unsigned __int16 v151; // bx
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  struct CSessionTraceFlags *v157; // rcx
  __int64 v158; // rax
  struct CSessionTraceFlags *v159; // rcx
  __int64 v160; // rax
  struct CSessionTraceFlags *v161; // rcx
  struct LFCB *LFCB; // r8
  __int64 v163; // rax
  __int64 v164; // rcx
  unsigned __int64 v165; // rax
  unsigned __int64 v166; // rax
  unsigned __int64 v167; // rax
  unsigned __int64 v168; // rax
  __int64 v169; // r10
  unsigned __int64 v170; // r8
  __int64 v171; // rcx
  unsigned __int64 v172; // r9
  __int64 v173; // r10
  unsigned __int64 v174; // rax
  int v175; // r9d
  __int64 v176; // rax
  double v177; // xmm4_8
  double v178; // xmm4_8
  double v179; // xmm3_8
  double v180; // xmm3_8
  double v181; // xmm2_8
  double v182; // xmm2_8
  double v183; // xmm0_8
  double v184; // xmm0_8
  double v185; // xmm1_8
  __int64 v186; // rax
  struct CSessionTraceFlags *v187; // rcx
  __int64 v188; // rax
  struct CSessionTraceFlags *v189; // rcx
  __int64 v190; // rax
  struct CSessionTraceFlags *v191; // rcx
  __int64 v192; // rax
  struct CSessionTraceFlags *v193; // rcx
  __int64 v194; // rax
  struct CSessionTraceFlags *v195; // rcx
  __int64 v196; // rax
  __int64 v197; // rax
  struct CSessionTraceFlags *v198; // rcx
  __int64 v199; // rax
  struct CSessionTraceFlags *v200; // rcx
  __int64 v201; // rax
  struct CSessionTraceFlags *v202; // rcx
  LSN *v203; // [rsp+20h] [rbp-F0h]
  LSN *v204; // [rsp+28h] [rbp-E8h]
  unsigned __int64 v205; // [rsp+30h] [rbp-E0h]
  unsigned __int64 v206; // [rsp+38h] [rbp-D8h]
  LSN *v207; // [rsp+40h] [rbp-D0h]
  char v208; // [rsp+90h] [rbp-80h]
  char v209; // [rsp+91h] [rbp-7Fh]
  char v210; // [rsp+92h] [rbp-7Eh]
  __int16 v211; // [rsp+94h] [rbp-7Ch]
  unsigned __int64 v212; // [rsp+98h] [rbp-78h]
  unsigned __int64 v213; // [rsp+A0h] [rbp-70h]
  unsigned int v214; // [rsp+A8h] [rbp-68h] BYREF
  unsigned __int64 v215; // [rsp+B0h] [rbp-60h]
  int v216[2]; // [rsp+B8h] [rbp-58h]
  int v217[2]; // [rsp+C0h] [rbp-50h]
  int v218[2]; // [rsp+C8h] [rbp-48h]
  unsigned __int64 v219; // [rsp+D0h] [rbp-40h]
  unsigned __int64 v220; // [rsp+D8h] [rbp-38h]
  __int64 v221[2]; // [rsp+E0h] [rbp-30h] BYREF
  __int128 v222; // [rsp+F0h] [rbp-20h]
  unsigned __int64 v223; // [rsp+100h] [rbp-10h]
  __int64 v224; // [rsp+108h] [rbp-8h]
  LSN v225; // [rsp+110h] [rbp+0h]
  unsigned __int64 v226; // [rsp+120h] [rbp+10h]
  unsigned __int64 v227; // [rsp+128h] [rbp+18h]
  __int64 v228; // [rsp+130h] [rbp+20h]
  unsigned __int64 v229; // [rsp+138h] [rbp+28h]
  _DWORD v230[2]; // [rsp+140h] [rbp+30h] BYREF
  __int16 v231; // [rsp+148h] [rbp+38h]
  unsigned __int64 v232; // [rsp+150h] [rbp+40h]
  unsigned __int64 v233; // [rsp+158h] [rbp+48h]
  _BYTE v234[6]; // [rsp+160h] [rbp+50h] BYREF
  __int16 v235; // [rsp+166h] [rbp+56h]
  __int64 v236; // [rsp+168h] [rbp+58h]
  __int64 v237; // [rsp+178h] [rbp+68h]
  unsigned int v238; // [rsp+188h] [rbp+78h] BYREF
  unsigned int v239; // [rsp+18Ch] [rbp+7Ch] BYREF
  unsigned int v240; // [rsp+190h] [rbp+80h] BYREF
  unsigned int v241; // [rsp+194h] [rbp+84h] BYREF
  __int64 v242; // [rsp+198h] [rbp+88h]
  LARGE_INTEGER v243; // [rsp+1A0h] [rbp+90h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+1A8h] [rbp+98h] BYREF
  __int64 v245; // [rsp+1B0h] [rbp+A0h]
  __int64 v246; // [rsp+1B8h] [rbp+A8h]
  char v247[8]; // [rsp+1C0h] [rbp+B0h] BYREF
  int v248; // [rsp+1C8h] [rbp+B8h]
  int v249; // [rsp+1D0h] [rbp+C0h]
  int **v250; // [rsp+1D8h] [rbp+C8h]
  char *v251; // [rsp+1E0h] [rbp+D0h]
  __int64 v252; // [rsp+1E8h] [rbp+D8h]
  int *v253; // [rsp+1F0h] [rbp+E0h] BYREF
  int v254; // [rsp+1F8h] [rbp+E8h]
  int v255; // [rsp+1FCh] [rbp+ECh]
  wchar_t *v256; // [rsp+200h] [rbp+F0h]
  int v257; // [rsp+208h] [rbp+F8h]
  int v258; // [rsp+20Ch] [rbp+FCh]
  wchar_t *v259; // [rsp+210h] [rbp+100h]
  int v260; // [rsp+218h] [rbp+108h]
  int v261; // [rsp+21Ch] [rbp+10Ch]
  wchar_t *v262; // [rsp+220h] [rbp+110h]
  int v263; // [rsp+228h] [rbp+118h]
  int v264; // [rsp+22Ch] [rbp+11Ch]
  wchar_t *v265; // [rsp+230h] [rbp+120h]
  int v266; // [rsp+238h] [rbp+128h]
  int v267; // [rsp+23Ch] [rbp+12Ch]
  wchar_t *v268; // [rsp+240h] [rbp+130h]
  int v269; // [rsp+248h] [rbp+138h]
  int v270; // [rsp+24Ch] [rbp+13Ch]
  char v271; // [rsp+250h] [rbp+140h] BYREF
  __int64 v272; // [rsp+410h] [rbp+300h]
  __int64 v273; // [rsp+418h] [rbp+308h]
  int v274; // [rsp+420h] [rbp+310h] BYREF
  __int64 v275; // [rsp+424h] [rbp+314h]
  unsigned __int64 v276; // [rsp+42Ch] [rbp+31Ch]
  unsigned __int64 v277; // [rsp+434h] [rbp+324h]
  unsigned __int64 v278; // [rsp+43Ch] [rbp+32Ch]
  __int64 v279; // [rsp+444h] [rbp+334h]
  char v280[8]; // [rsp+480h] [rbp+370h] BYREF
  int v281; // [rsp+488h] [rbp+378h]
  int v282; // [rsp+490h] [rbp+380h]
  int **v283; // [rsp+498h] [rbp+388h]
  char *v284; // [rsp+4A0h] [rbp+390h]
  __int64 v285; // [rsp+4A8h] [rbp+398h]
  int *v286; // [rsp+4B0h] [rbp+3A0h] BYREF
  int v287; // [rsp+4B8h] [rbp+3A8h]
  int v288; // [rsp+4BCh] [rbp+3ACh]
  wchar_t *v289; // [rsp+4C0h] [rbp+3B0h]
  int v290; // [rsp+4C8h] [rbp+3B8h]
  int v291; // [rsp+4CCh] [rbp+3BCh]
  wchar_t *v292; // [rsp+4D0h] [rbp+3C0h]
  int v293; // [rsp+4D8h] [rbp+3C8h]
  int v294; // [rsp+4DCh] [rbp+3CCh]
  char v295; // [rsp+4E0h] [rbp+3D0h] BYREF
  __int64 v296; // [rsp+6D0h] [rbp+5C0h]
  __int64 v297; // [rsp+6D8h] [rbp+5C8h]
  int v298; // [rsp+6E0h] [rbp+5D0h] BYREF
  char v299[8]; // [rsp+700h] [rbp+5F0h] BYREF
  int v300; // [rsp+708h] [rbp+5F8h]
  int v301; // [rsp+710h] [rbp+600h]
  int **v302; // [rsp+718h] [rbp+608h]
  char *v303; // [rsp+720h] [rbp+610h]
  __int64 v304; // [rsp+728h] [rbp+618h]
  int *v305; // [rsp+730h] [rbp+620h] BYREF
  int v306; // [rsp+738h] [rbp+628h]
  int v307; // [rsp+73Ch] [rbp+62Ch]
  wchar_t *v308; // [rsp+740h] [rbp+630h]
  int v309; // [rsp+748h] [rbp+638h]
  int v310; // [rsp+74Ch] [rbp+63Ch]
  wchar_t *v311; // [rsp+750h] [rbp+640h]
  int v312; // [rsp+758h] [rbp+648h]
  int v313; // [rsp+75Ch] [rbp+64Ch]
  char v314; // [rsp+760h] [rbp+650h] BYREF
  __int64 v315; // [rsp+950h] [rbp+840h]
  __int64 v316; // [rsp+958h] [rbp+848h]
  int v317; // [rsp+960h] [rbp+850h] BYREF
  char v318[8]; // [rsp+980h] [rbp+870h] BYREF
  int v319; // [rsp+988h] [rbp+878h]
  int v320; // [rsp+990h] [rbp+880h]
  _QWORD *v321; // [rsp+998h] [rbp+888h]
  char *v322; // [rsp+9A0h] [rbp+890h]
  __int64 v323; // [rsp+9A8h] [rbp+898h]
  _QWORD v324[2]; // [rsp+9B0h] [rbp+8A0h] BYREF
  char v325; // [rsp+9C0h] [rbp+8B0h] BYREF
  __int64 v326; // [rsp+BD0h] [rbp+AC0h]
  __int64 v327; // [rsp+BD8h] [rbp+AC8h]
  int v328; // [rsp+BE0h] [rbp+AD0h] BYREF
  unsigned __int64 v329; // [rsp+BE4h] [rbp+AD4h]
  unsigned __int64 v330; // [rsp+BECh] [rbp+ADCh]
  unsigned __int64 v331; // [rsp+BF4h] [rbp+AE4h]
  unsigned __int64 v332; // [rsp+BFCh] [rbp+AECh]
  __int64 v333; // [rsp+C04h] [rbp+AF4h]
  unsigned __int64 v334; // [rsp+C0Ch] [rbp+AFCh]
  char v335[8]; // [rsp+C20h] [rbp+B10h] BYREF
  int v336; // [rsp+C28h] [rbp+B18h]
  int v337; // [rsp+C30h] [rbp+B20h]
  _QWORD *v338; // [rsp+C38h] [rbp+B28h]
  char *v339; // [rsp+C40h] [rbp+B30h]
  __int64 v340; // [rsp+C48h] [rbp+B38h]
  _QWORD v341[2]; // [rsp+C50h] [rbp+B40h] BYREF
  char v342; // [rsp+C60h] [rbp+B50h] BYREF
  __int64 v343; // [rsp+E70h] [rbp+D60h]
  __int64 v344; // [rsp+E78h] [rbp+D68h]
  int v345; // [rsp+E80h] [rbp+D70h] BYREF
  unsigned __int64 v346; // [rsp+E84h] [rbp+D74h]
  unsigned __int64 v347; // [rsp+E8Ch] [rbp+D7Ch]
  unsigned __int64 v348; // [rsp+E94h] [rbp+D84h]
  unsigned __int64 v349; // [rsp+E9Ch] [rbp+D8Ch]
  __int64 v350; // [rsp+EA4h] [rbp+D94h]
  unsigned __int64 v351; // [rsp+EACh] [rbp+D9Ch]
  char v352[8]; // [rsp+EC0h] [rbp+DB0h] BYREF
  int v353; // [rsp+EC8h] [rbp+DB8h]
  int v354; // [rsp+ED0h] [rbp+DC0h]
  _QWORD *v355; // [rsp+ED8h] [rbp+DC8h]
  char *v356; // [rsp+EE0h] [rbp+DD0h]
  __int64 v357; // [rsp+EE8h] [rbp+DD8h]
  _QWORD v358[2]; // [rsp+EF0h] [rbp+DE0h] BYREF
  char v359; // [rsp+F00h] [rbp+DF0h] BYREF
  __int64 v360; // [rsp+1110h] [rbp+1000h]
  __int64 v361; // [rsp+1118h] [rbp+1008h]
  int v362; // [rsp+1120h] [rbp+1010h] BYREF
  unsigned __int64 v363; // [rsp+1124h] [rbp+1014h]
  __int64 v364; // [rsp+112Ch] [rbp+101Ch]
  __int64 v365; // [rsp+1134h] [rbp+1024h]
  LSN v366; // [rsp+1140h] [rbp+1030h] BYREF
  int v367; // [rsp+1148h] [rbp+1038h]
  LSN v368; // [rsp+114Ch] [rbp+103Ch] BYREF
  int v369; // [rsp+1154h] [rbp+1044h]
  LSN v370; // [rsp+1158h] [rbp+1048h] BYREF
  unsigned __int16 v371; // [rsp+1160h] [rbp+1050h]
  __int16 v372; // [rsp+1162h] [rbp+1052h]
  LSN v373; // [rsp+1168h] [rbp+1058h] BYREF
  unsigned __int16 v374; // [rsp+1170h] [rbp+1060h]
  LSN v375; // [rsp+1178h] [rbp+1068h] BYREF
  int v376; // [rsp+1180h] [rbp+1070h]
  wchar_t v377[48]; // [rsp+1190h] [rbp+1080h] BYREF
  wchar_t v378[48]; // [rsp+11F0h] [rbp+10E0h] BYREF
  wchar_t v379[48]; // [rsp+1250h] [rbp+1140h] BYREF
  wchar_t v380[48]; // [rsp+12B0h] [rbp+11A0h] BYREF
  wchar_t v381[48]; // [rsp+1310h] [rbp+1200h] BYREF
  wchar_t v382[48]; // [rsp+1370h] [rbp+1260h] BYREF
  wchar_t v383[48]; // [rsp+13D0h] [rbp+12C0h] BYREF
  wchar_t v384[48]; // [rsp+1430h] [rbp+1320h] BYREF
  wchar_t v385[48]; // [rsp+1490h] [rbp+1380h] BYREF

  v1 = *(_WORD *)(a1 + 1720);
  v2 = 0;
  v3 = *(_QWORD *)(a1 + 1880);
  v221[0] = 0;
  v222 = 0u;
  v4 = 0;
  v5 = 32;
  v221[1] = 0;
  v366.QuadPart = 0;
  if ( v1 == 2 )
    v5 = 0;
  v367 = 0;
  v7 = 0;
  v372 = 0;
  v8 = 0;
  v368.QuadPart = 0;
  v9 = 0;
  v369 = 0;
  v211 = v1;
  v10 = 0;
  v235 = 0;
  v11 = 0;
  v209 = 0;
  v210 = 0;
  do
  {
    v12 = *(_QWORD *)(v3 + 280);
    v11 += 192;
    ++v10;
    v7 += *(_QWORD *)(v11 + v12 - 72);
    v221[0] = v7;
    v4 += *(_QWORD *)(v11 + v12 - 64);
    v221[1] = v4;
    v8 += *(_QWORD *)(v11 + v12 - 56);
    *(_QWORD *)&v222 = v8;
    v9 += *(_QWORD *)(v11 + v12 - 48);
    *((_QWORD *)&v222 + 1) = v9;
  }
  while ( v10 <= *(int *)(v3 + 252) );
  v13 = *(_QWORD *)(v3 + 272);
  v14 = 1;
  *(_QWORD *)(v13 + 27312) = v4;
  if ( v1 == 2 )
  {
    v15 = 0;
  }
  else
  {
    if ( *((_QWORD *)&v222 + 1) >= 0x2710u
      && 5000LL * *((_QWORD *)&v222 + 1) >= (unsigned __int64)v222
      && SOS_OS_MemoryModel != 1 )
    {
      if ( (unsigned int)(SOS_OS_MemoryModel - 2) <= 1 )
      {
        v15 = 16;
        goto LABEL_11;
      }
      utassert_fail(
        1u,
        "FALSE",
        "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\trans\\\\DPTracking.cpp\"",
        1686,
        "Invalid switch value");
    }
    v15 = 8;
  }
LABEL_11:
  v16 = *(_QWORD *)(a1 + 1904);
  *(_QWORD *)v217 = v15;
  v17 = 128 - v15 - v5;
  v233 = v17 - 1;
  if ( v16 >= v17 - 1 )
    v16 = v17 - 1;
  *(_QWORD *)(a1 + 1904) = v16;
  *(_QWORD *)v218 = v5 + v16;
  v18 = 128 - (v5 + v16) - v15;
  *(_QWORD *)v216 = v18;
  if ( !v18 || v18 > v17 )
    utassert_fail(1u, "dataSlices > 0 && dataSlices <= StartDataSlices", "recoveryunit.cpp", 14598, 0);
  v19 = *(_QWORD *)(a1 + 1880);
  ++*(_DWORD *)(a1 + 1916);
  v20 = 0;
  v21 = *(_QWORD *)(a1 + 1696);
  v22 = 0;
  v23 = *(unsigned int *)(v19 + 260);
  HIDWORD(v206) = 0;
  LODWORD(v205) = 0;
  if ( !*(_DWORD *)(v19 + 260) )
    v23 = 1;
  v208 = 1;
  v242 = 1000000 * v23;
  v219 = (unsigned __int64)(1000000 * v23) >> 7;
  v203 = 0;
  v228 = v15 * v219;
  v226 = v21 + 48;
  LatchBase::AcquireInternal(v21 + 48, 4, 0xFFFFFFFFLL);
  v24 = 1;
  if ( *(_WORD *)(v21 + 116) )
  {
    do
    {
      v25 = *(_QWORD *)(*(_QWORD *)(v21 + 80) + 8LL * v24 - 8);
      if ( v25
        && (*(_BYTE *)(v25 + 100) & 0x40) == 0
        && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v25 + 128LL))(v25) )
      {
        ++v20;
        if ( *(_BYTE *)(v25 + 88) || !*(_DWORD *)(v25 + 4304) )
        {
          ++v22;
        }
        else
        {
          v26 = *(_DWORD **)(v25 + 648);
          v208 = 0;
          if ( v26 )
            v22 += *v26 - 1;
        }
      }
      ++v24;
    }
    while ( v24 <= *(_WORD *)(v21 + 116) );
    v14 = v208;
  }
  LatchBase::ReleaseInternal(v226, 4);
  if ( byte_10316EA3F || (qword_10317AD29 & 0x100000000000LL) != 0 || v14 )
    v22 = v20;
  if ( v22 )
  {
    v27 = v20;
    if ( v211 != 2 )
      v27 = v22;
    v28 = v20 * v20;
    v29 = 5 * v20;
    v226 = v27;
    v227 = v29;
    v229 = v219 * v28;
    v30 = *(_QWORD *)v216 * v219 * v28;
    if ( v27 < v29 )
      v31 = v27;
    else
      v31 = v29;
  }
  else
  {
    v227 = 5;
    v27 = 1;
    v226 = 1;
    v28 = 1;
    v29 = 5;
    v31 = 1;
    v229 = v219;
    v30 = *(_QWORD *)v216 * v219;
  }
  v32 = v30 % v31;
  v33 = dword_10318850C * (v30 / v31);
  v215 = v33;
  if ( !v33 )
    utassert_fail(1u, "dataSliceMicroSec", "recoveryunit.cpp", 14652, 0, 0, 0, 0, 0);
  v34 = -1;
  *(_QWORD *)(*(_QWORD *)(a1 + 1880) + 16LL) = v33;
  v35 = v221[0];
  if ( v221[0] )
  {
    v36 = v29;
    if ( v27 < v29 )
      v36 = v27;
    v38 = v36;
    v37 = v221[0] / (unsigned __int64)dword_10318850C * (unsigned __int128)v36;
    v39 = -1;
    v245 = *((_QWORD *)&v37 + 1);
    if ( is_mul_ok(v221[0] / (unsigned __int64)dword_10318850C, v38) )
      v39 = v37;
    v32 = v39 % v28;
    v223 = v39 / v28;
  }
  else
  {
    v223 = 0;
  }
  if ( *(int *)(a1 + 1648) >= 4 )
  {
    if ( v221[0] > v33 )
      *(_BYTE *)(a1 + 1920) = 1;
    if ( *(_DWORD *)(a1 + 1912) > 2u )
    {
      v96 = *(_QWORD *)(a1 + 1904);
      if ( v96 < v233 && v35 < v33 && *(_DWORD *)(a1 + 1916) > 0x10u )
      {
        v97 = 1;
        v98 = *(_QWORD *)v216;
        if ( !*(_BYTE *)(a1 + 1920) && *(_QWORD *)v216 > 0x10u )
          v97 = 16;
        *(_QWORD *)(a1 + 1912) = 0;
        *(_QWORD *)(a1 + 1904) = v97 + v96;
        v99 = v98 - v97;
        v100 = v99 * v229;
        *(_QWORD *)v216 = v99;
        v101 = v29;
        v102 = v226;
        if ( v226 < v227 )
          v101 = v226;
        v33 = dword_10318850C * (v100 / v101);
        v103 = *(_QWORD *)(a1 + 1880);
        v215 = v33;
        *(_QWORD *)(v103 + 16) = v33;
        v104 = *(DirtyPageMgr **)(a1 + 1880);
        *(_OWORD *)v221 = 0;
        v222 = 0;
        DirtyPageMgr::EvaluateRecovery(v104, (struct DirtyPageCounts *)v221, 0);
        if ( v221[0] )
        {
          v111 = v227;
          if ( v102 < v227 )
            v111 = v102;
          v113 = v111;
          v112 = v221[0] / (unsigned __int64)dword_10318850C * (unsigned __int128)v111;
          v114 = -1;
          v246 = *((_QWORD *)&v112 + 1);
          if ( is_mul_ok(v221[0] / (unsigned __int64)dword_10318850C, v113) )
            v114 = v112;
          v223 = v114 / v28;
        }
        else
        {
          v223 = 0;
        }
        if ( (qword_10317AD29 & 0x20000000000LL) != 0
          || (v105 = *(_QWORD *)(SystemThread_TlsOffset
                               + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v106 = **(struct CSessionTraceFlags ***)(v105 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v106, 0xD71u)
          || (qword_10317AD33 & 2) != 0
          || (v107 = *(_QWORD *)(SystemThread_TlsOffset
                               + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v108 = **(struct CSessionTraceFlags ***)(v107 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v108, 0xD99u)
          || (qword_10317AD29 & 0x40000000000LL) != 0
          || (v32 = SystemThread_TlsIndex,
              (v109 = *(_QWORD *)(SystemThread_TlsOffset
                                + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0)
          && (v110 = **(struct CSessionTraceFlags ***)(v109 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v110, 0xD72u)
          || (dword_10317F6CC & 1) != 0 )
        {
          _mm_lfence();
          v40 = *(_QWORD *)v218;
          TraceRecoveryTargetResetEvent(
            *(unsigned __int16 *)(a1 + 1720),
            *(unsigned __int16 *)(a1 + 1632),
            (unsigned int)L"too big data slice",
            v217[0],
            *(__int64 *)v216,
            v97 + *(_QWORD *)v218,
            v205,
            v33,
            (__int64)v221);
          v35 = v221[0];
          goto LABEL_48;
        }
        v35 = v221[0];
      }
    }
    v40 = *(_QWORD *)v218;
LABEL_48:
    if ( !*(_BYTE *)(a1 + 8273) && v35 > v33 + (v33 >> 4) )
    {
      v115 = 0;
      if ( !*(_BYTE *)(a1 + 7383) )
      {
        *(_BYTE *)(a1 + 7383) = 1;
        v115 = 1;
      }
      if ( (qword_10317AD29 & 0x20000000000LL) != 0
        || (v116 = *(_QWORD *)(SystemThread_TlsOffset
                             + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
        && (v117 = **(struct CSessionTraceFlags ***)(v116 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v117, 0xD71u)
        || (qword_10317AD33 & 2) != 0
        || (v118 = *(_QWORD *)(SystemThread_TlsOffset
                             + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
        && (v119 = **(struct CSessionTraceFlags ***)(v118 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v119, 0xD99u)
        || (qword_10317AD29 & 0x40000000000LL) != 0
        || (v32 = SystemThread_TlsIndex,
            (v120 = *(_QWORD *)(SystemThread_TlsOffset
                              + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0)
        && (v121 = **(struct CSessionTraceFlags ***)(v120 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v121, 0xD72u) )
      {
        _mm_lfence();
        if ( v221[0] < 0 )
          v122 = (double)(int)(v221[0] & 1 | ((unsigned __int64)v221[0] >> 1))
               + (double)(int)(v221[0] & 1 | ((unsigned __int64)v221[0] >> 1));
        else
          v122 = (double)SLODWORD(v221[0]);
        v123 = v122 / 1000000.0;
        if ( (v33 & 0x8000000000000000uLL) != 0LL )
          v124 = (double)(int)(v33 & 1 | (v33 >> 1)) + (double)(int)(v33 & 1 | (v33 >> 1));
        else
          v124 = (double)(int)v33;
        v125 = L"in";
        v206 = v223 / 0xF4240;
        v126 = v124 / 1000000.0;
        if ( v115 )
          v125 = L"start";
        LODWORD(v205) = v221[1];
        LogSystemMetadata(
          L"RU::EvaluateCheckpoint DB %d:%d %ls catchup mode. data allowance %.2lf s, current %.2lf s (%I64d pages), recov"
           "ery_data_est %I64d s.",
          *(unsigned __int16 *)(a1 + 1720),
          *(unsigned __int16 *)(a1 + 1632),
          v125,
          v126,
          v123);
      }
      if ( *(_BYTE *)(a1 + 7384) )
      {
        for ( i = 0; i < *(_QWORD *)(a1 + 7424); ++i )
          PartitionedCounter::SetCounter((PartitionedCounter *)(a1 + 7408), 0, i);
      }
      goto LABEL_51;
    }
    if ( *(_BYTE *)(a1 + 7383) )
    {
      *(_BYTE *)(a1 + 7383) = 0;
      if ( (qword_10317AD29 & 0x20000000000LL) == 0 )
      {
        v128 = *(_QWORD *)(SystemThread_TlsOffset
                         + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
        if ( (!v128
           || (v129 = **(struct CSessionTraceFlags ***)(v128 + 56)) == 0
           || !CSessionTraceFlags::CheckSessionTraceInternal(v129, 0xD71u))
          && (qword_10317AD33 & 2) == 0 )
        {
          v130 = *(_QWORD *)(SystemThread_TlsOffset
                           + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
          if ( (!v130
             || (v131 = **(struct CSessionTraceFlags ***)(v130 + 56)) == 0
             || !CSessionTraceFlags::CheckSessionTraceInternal(v131, 0xD99u))
            && (qword_10317AD29 & 0x40000000000LL) == 0 )
          {
            v32 = SystemThread_TlsIndex;
            v132 = *(_QWORD *)(SystemThread_TlsOffset
                             + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
            if ( !v132 )
              goto LABEL_51;
            v133 = **(struct CSessionTraceFlags ***)(v132 + 56);
            if ( !v133 || !CSessionTraceFlags::CheckSessionTraceInternal(v133, 0xD72u) )
              goto LABEL_51;
          }
        }
        v35 = v221[0];
      }
      if ( (v35 & 0x8000000000000000uLL) != 0LL )
        v134 = (double)(int)(v35 & 1 | (v35 >> 1)) + (double)(int)(v35 & 1 | (v35 >> 1));
      else
        v134 = (double)(int)v35;
      v135 = v134 / 1000000.0;
      if ( (v33 & 0x8000000000000000uLL) != 0LL )
        v136 = (double)(int)(v33 & 1 | (v33 >> 1)) + (double)(int)(v33 & 1 | (v33 >> 1));
      else
        v136 = (double)(int)v33;
      v205 = v223 / 0xF4240;
      LogSystemMetadata(
        L"RU::EvaluateCheckpoint DB %d:%d out of catchup mode. data allowance %.2lf s, current %.2lf s (%I64d pages), reco"
         "very_data_est %I64d s.",
        *(unsigned __int16 *)(a1 + 1720),
        *(unsigned __int16 *)(a1 + 1632),
        v136 / 1000000.0,
        v135,
        v221[1]);
    }
LABEL_51:
    v41 = v40 * v219;
    v212 = v40 * v219;
    v42 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(a1 + 1736) + 96LL))(
            *(_QWORD *)(a1 + 1736),
            v32);
    QuadPart = 0;
    v44 = *(_QWORD *)(a1 + 1712);
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v224 = v42;
    v213 = v42;
    if ( *(_DWORD *)(v44 + 5376)
      || _InterlockedCompareExchange64((volatile signed __int64 *)(v44 + 5376), UniqueThread_low, 0) )
    {
      v137 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v138 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v138 && *(_QWORD *)(v138 + 272) == v138 )
          v137 = *(_QWORD *)(v138 + 256);
        if ( v137 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
          }
          else
          {
            QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      v139 = v44 + 5376;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v139, UniqueThread_low);
      else
        Spinlock<148,10,258>::SpinToAcquireOptimistic(v139, v137, UniqueThread_low);
      if ( v137 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v243);
          v140 = (DirtyPageMgr *)v243.QuadPart;
        }
        else
        {
          v140 = MEMORY[0x7FFE0008];
        }
        v141 = 0;
        if ( v140 >= QuadPart )
          v141 = v140 - QuadPart;
        *(_QWORD *)(v137 + 3192) += v141;
      }
      v41 = v212;
    }
    v46 = *(LSN *)(a1 + 2180);
    v47 = *(_QWORD *)(a1 + 1712);
    v371 = *(_WORD *)(a1 + 2188);
    v376 = *(_DWORD *)(a1 + 2200);
    v370 = v46;
    v375 = *(LSN *)(a1 + 2192);
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v142 = rand();
      v143 = (unsigned int)(5 * (v142 / 5));
      if ( v142 == (_DWORD)v143 )
        Spinlock<148,10,258>::UpdateStatSnapshot(v143);
    }
    *(_QWORD *)(v47 + 5376) = 0;
    (*(void (__fastcall **)(_QWORD, LSN *))(**(_QWORD **)(a1 + 1736) + 40LL))(*(_QWORD *)(a1 + 1736), &v368);
    DirtyPageMgr::GetOldestDirtyLSN(*(DirtyPageMgr **)(a1 + 1880), (struct AlignedLSN *)&v366, 0, 0);
    if ( v211 == 2 )
    {
      v366 = v368;
      v367 = v369;
    }
    v48 = 0;
    if ( v375.LowPart < v370.LowPart
      || v375.LowPart == v370.LowPart
      && (v375.HighPart < (unsigned int)v370.HighPart || v375.HighPart == v370.HighPart && (unsigned __int16)v376 < v371) )
    {
      v144 = (*(__int64 (__fastcall **)(_QWORD, LSN *, LSN *, __int64, LSN *))(**(_QWORD **)(a1 + 1736) + 120LL))(
               *(_QWORD *)(a1 + 1736),
               &v375,
               &v370,
               1,
               v203);
      v50 = v224;
      v48 = v144;
      v49 = v224 + v144;
      v213 = v49;
    }
    else
    {
      v49 = v213;
      v50 = v213;
    }
    v51 = v223;
    v52 = (v50 + v49) / (unsigned __int64)dword_103188510;
    v220 = v52;
    v232 = v228 + v223 + v52;
    if ( (qword_10317AD29 & 0x20000000000LL) != 0
      || (v53 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
      && (v54 = **(struct CSessionTraceFlags ***)(v53 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v54, 0xD71u)
      || (qword_10317AD33 & 2) != 0
      || (v55 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
      && (v56 = **(struct CSessionTraceFlags ***)(v55 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v56, 0xD99u)
      || (qword_10317AD29 & 0x40000000000LL) != 0
      || (v57 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
      && (v58 = **(struct CSessionTraceFlags ***)(v57 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v58, 0xD72u)
      || dword_10317F6C8 < 0 )
    {
      v207 = (LSN *)v51;
      v59 = v215;
      TraceRecoveryCheckpointEvaluationEvent(
        *(unsigned __int16 *)(a1 + 1720),
        v217[0],
        v216[0],
        v218[0],
        v228,
        v215,
        v41,
        v52,
        (__int64)v207,
        v242,
        (__int64)v221,
        v213,
        *(_BYTE *)(a1 + 7383),
        &v370,
        &v375,
        &v368,
        &v366);
    }
    else
    {
      v59 = v215;
    }
    LowPart = v366.LowPart;
    v61 = v368.LowPart;
    if ( *(_DWORD *)(a1 + 2164) == 2 && v366.LowPart != v368.LowPart )
    {
      v209 = 1;
      if ( (dword_10317F6CC & 4) != 0 )
      {
        LSN::FormatAsHexString(&v368, v383, &v238);
        LSN::FormatAsHexString(&v366, v377, &v239);
        if ( (dword_10317F6CC & 4) != 0 )
        {
          v281 = 196608;
          v283 = &v286;
          v282 = 0;
          v284 = &v295;
          v286 = &v298;
          v298 = *(unsigned __int16 *)(a1 + 1720);
          v79 = -1;
          v296 = 0;
          v285 = 0;
          v297 = 0;
          v287 = 20;
          v288 = 2;
          do
            ++v79;
          while ( v383[v79] );
          v291 = 1;
          v290 = 2 * v79;
          v289 = v383;
          v80 = -1;
          do
            ++v80;
          while ( v377[v80] );
          v294 = 2;
          v292 = v377;
          v293 = 2 * v80;
          XeSqlPkg::recovery_simple_log_truncate::Publish((XeSqlPkg::recovery_simple_log_truncate *)v280);
        }
        v61 = v368.LowPart;
        LowPart = v366.LowPart;
      }
    }
    v62 = v370.LowPart;
    v63 = v367;
    HighPart = v366.HighPart;
    if ( !(_WORD)v369 && !v61 && !v368.HighPart )
      goto LABEL_81;
    if ( !(_WORD)v367 && !LowPart && !v366.HighPart || LowPart > v61 )
      goto LABEL_288;
    if ( LowPart != v61 )
      goto LABEL_84;
    if ( v366.HighPart > (unsigned int)v368.HighPart
      || v366.HighPart == v368.HighPart && (unsigned __int16)v367 > (unsigned __int16)v369 )
    {
LABEL_288:
      LOWORD(v367) = v369;
      v63 = v369;
      HighPart = v368.HighPart;
      v366.QuadPart = __PAIR64__(v368.HighPart, v61);
      LowPart = v61;
    }
    else
    {
LABEL_81:
      if ( LowPart != v61 )
        goto LABEL_84;
    }
    if ( v375.LowPart != LowPart || v370.LowPart != v61 )
    {
      v84 = 1;
      LOBYTE(v2) = v211 == 2;
      v74 = v2 + 1;
      if ( v211 != 2 )
      {
        v75 = v215;
LABEL_326:
        v66 = v212;
        goto LABEL_327;
      }
      if ( (qword_10317AD29 & 0x20000000000LL) != 0
        || (v85 = *(_QWORD *)(SystemThread_TlsOffset
                            + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
        && (v86 = **(struct CSessionTraceFlags ***)(v85 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v86, 0xD71u)
        || (qword_10317AD33 & 2) != 0
        || (v87 = *(_QWORD *)(SystemThread_TlsOffset
                            + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
        && (v88 = **(struct CSessionTraceFlags ***)(v87 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v88, 0xD99u)
        || (qword_10317AD29 & 0x40000000000LL) != 0
        || (v89 = *(_QWORD *)(SystemThread_TlsOffset
                            + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
        && (v90 = **(struct CSessionTraceFlags ***)(v89 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v90, 0xD72u)
        || (dword_10317F6CC & 0x400) != 0 )
      {
        TraceRecoveryQueueLogTruncationEvent(
          *(unsigned __int16 *)(a1 + 1720),
          *(unsigned __int16 *)(a1 + 1632),
          v59,
          (int)v221,
          &v370,
          &v368,
          v224);
      }
LABEL_114:
      v75 = v215;
      goto LABEL_115;
    }
LABEL_84:
    if ( (unsigned __int64)v224 < 0x3C000 )
    {
      v74 = 3;
      goto LABEL_114;
    }
    if ( v211 == 2 )
    {
      v77 = v212;
      if ( (dword_10317F6CC & 0x20) != 0 )
      {
        v320 = 0;
        v321 = v324;
        v326 = 0;
        v322 = &v325;
        v324[0] = &v328;
        v328 = *(unsigned __int16 *)(a1 + 1720);
        v329 = v213;
        v323 = 0;
        v327 = 0;
        v76 = v220;
        v319 = 0x10000;
        v330 = v220 >> 10;
        v331 = v212 >> 10;
        v332 = (unsigned __int64)v221[0] >> 10;
        v333 = v221[1];
        v334 = v59 >> 10;
        v324[1] = 52;
        XeSqlPkg::recovery_skip_checkpoint::Publish((XeSqlPkg::recovery_skip_checkpoint *)v318);
        v75 = v215;
        v74 = 3;
      }
      else
      {
        v76 = v220;
        v74 = 3;
        v75 = v215;
      }
LABEL_117:
      DirtyPageMgr::ReportStats(
        *(DirtyPageMgr **)(a1 + 1880),
        (const struct DirtyPageCounts *)v221,
        v75,
        v223,
        v77,
        v76,
        v213,
        v232,
        &v368,
        &v366);
      if ( v210 )
      {
        DirtyPageMgr::ForceWriteOldPages(*(DirtyPageMgr **)(a1 + 1880), (struct AlignedPageId *)v234);
        ++*(_DWORD *)(a1 + 1912);
      }
      else if ( v209 )
      {
        DirtyPageMgr::QueueWriteOldPages(*(DirtyPageMgr **)(a1 + 1880), (struct AlignedPageId *)v234);
      }
      DirtyPageMgr::DiagWrites(*(DirtyPageMgr **)(a1 + 1880));
      return v74;
    }
    v65 = v370.HighPart;
    if ( (LowPart < v370.LowPart
       || LowPart == v370.LowPart && (HighPart < v370.HighPart || HighPart == v370.HighPart && v63 < v371))
      && dword_103188514
      && v213 >= (__int64)dword_103188514 << 20 )
    {
      v145 = *(_QWORD *)(a1 + 1736);
      v374 = 0;
      v236 = 0;
      v373.QuadPart = 0;
      if ( (*(__int64 (__fastcall **)(__int64, LSN *, LSN *, __int64))(*(_QWORD *)v145 + 120LL))(v145, &v366, &v368, 1) >= (unsigned __int64)((__int64)dword_103188514 << 20) )
      {
        v146 = (unsigned int)v368.HighPart;
        v147 = v368.LowPart;
        v148 = *(SQLServerLogMgr **)(a1 + 1736);
        v149 = (unsigned __int64)(unsigned int)(dword_103188514 << 10) << 9;
        v237 = 0;
        v225.QuadPart = 0;
        LOWORD(v214) = 0;
        if ( (unsigned int)(dword_103188514 << 10) > v368.HighPart )
        {
          SQLServerLogMgr::GetLFMAccess(v148);
          LFCB = SQLServerLogMgr::FindLFCB(v148, v147);
          if ( LFCB )
          {
            v165 = v146 << 9;
            while ( 1 )
            {
              LFCB = *(struct LFCB **)LFCB;
              v149 -= v165;
              if ( LFCB == (SQLServerLogMgr *)((char *)v148 + 2792) || !LFCB )
                break;
              v165 = *((_QWORD *)LFCB + 6);
              if ( v149 <= v165 )
              {
                v150 = *((_DWORD *)LFCB + 16);
                v166 = (v165 - v149) >> 9;
                v151 = 0;
                v225.QuadPart = __PAIR64__(v166, v150);
                goto LABEL_344;
              }
            }
          }
          else
          {
            SQLServerLogMgr::ReleaseLFMAccess(v148);
            v163 = *((_QWORD *)v148 + 1);
            v230[0] = v147;
            v230[1] = v146;
            v231 = 0;
            v164 = *(_QWORD *)(v163 + 1712);
            LODWORD(v204) = *(_DWORD *)(v164 + 928);
            ex_raise(90, 3, 20, 17, v230, v204, v164 + 936);
          }
          v151 = v214;
          v150 = v225.LowPart;
LABEL_344:
          SQLServerLogMgr::ReleaseLFMAccess(v148);
          LODWORD(v146) = v368.HighPart;
          v147 = v368.LowPart;
        }
        else
        {
          v225.LowPart = v368.LowPart;
          v150 = v368.LowPart;
          v225.HighPart = v368.HighPart - (dword_103188514 << 10);
          v151 = 0;
        }
        v373 = v225;
        v374 = v151;
        if ( v150 <= v366.LowPart
          && (v150 != v366.LowPart
           || v225.HighPart <= (unsigned int)v366.HighPart
           && (v225.HighPart != v366.HighPart || v151 <= (unsigned __int16)v367)) )
        {
          utassert_fail(1u, "forceFlushLsn > newDirtyLSN", "recoveryunit.cpp", 14984, 0);
          LODWORD(v146) = v368.HighPart;
          v147 = v368.LowPart;
        }
        if ( v373.LowPart >= v147
          && (v373.LowPart != v147
           || v373.HighPart >= (unsigned int)v146 && (v373.HighPart != (_DWORD)v146 || v374 >= (unsigned __int16)v369)) )
        {
          utassert_fail(1u, "forceFlushLsn < newCkptLSN", "recoveryunit.cpp", 14985, 0);
        }
        v34 = -1;
      }
      if ( (dword_10317F6CC & 0x10) != 0 )
      {
        LSN::FormatAsHexString(&v368, v378, &v214);
        LSN::FormatAsHexString(&v366, v379, &v214);
        LSN::FormatAsHexString(&v370, v380, &v214);
        LSN::FormatAsHexString(&v375, v381, &v214);
        LSN::FormatAsHexString(&v373, v382, &v214);
        v75 = v215;
        if ( (dword_10317F6CC & 0x10) != 0 )
        {
          v248 = 393216;
          v250 = &v253;
          v249 = 0;
          v251 = &v271;
          v253 = &v274;
          v274 = *(unsigned __int16 *)(a1 + 1720);
          v275 = v221[1];
          v276 = (unsigned __int64)v221[0] >> 10;
          v277 = v215 >> 10;
          v278 = v213;
          v279 = (__int64)dword_103188514 << 20;
          v152 = -1;
          v272 = 0;
          v252 = 0;
          v273 = 0;
          v254 = 84;
          v255 = 5;
          do
            ++v152;
          while ( v378[v152] );
          v258 = 6;
          v257 = 2 * v152;
          v256 = v378;
          v153 = -1;
          do
            ++v153;
          while ( v379[v153] );
          v261 = 7;
          v260 = 2 * v153;
          v259 = v379;
          v154 = -1;
          do
            ++v154;
          while ( v380[v154] );
          v264 = 8;
          v263 = 2 * v154;
          v262 = v380;
          v155 = -1;
          do
            ++v155;
          while ( v381[v155] );
          v267 = 9;
          v266 = 2 * v155;
          v265 = v381;
          do
            ++v34;
          while ( v382[v34] );
          v270 = 10;
          v269 = 2 * v34;
          v268 = v382;
          XeSqlPkg::recovery_force_flush_checkpoint::Publish((XeSqlPkg::recovery_force_flush_checkpoint *)v247);
        }
      }
      else
      {
        v75 = v215;
      }
      if ( v374 || v373.QuadPart )
        DirtyPageMgr::ForceCatchupToLSN(*(DirtyPageMgr **)(a1 + 1880), (const struct UntrustedLSN *)&v373, 0, 0);
      v74 = 1;
      v84 = 1;
      goto LABEL_326;
    }
    if ( v375.LowPart >= v370.LowPart
      && (v375.LowPart != v370.LowPart
       || v375.HighPart >= (unsigned int)v370.HighPart
       && (v375.HighPart != v370.HighPart || (unsigned __int16)v376 >= v371)) )
    {
      v66 = v212;
LABEL_96:
      v67 = v219;
LABEL_97:
      v68 = v220;
      if ( v220 >= v66 )
      {
        if ( v221[0] <= v67 + v59 || *(_DWORD *)(a1 + 1916) <= 0x10u || v220 >= v67 + v66 )
        {
          v74 = 1;
        }
        else
        {
          if ( *(_QWORD *)(a1 + 1904) )
          {
            if ( (qword_10317AD29 & 0x20000000000LL) != 0
              || (v197 = *(_QWORD *)(SystemThread_TlsOffset
                                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
              && (v198 = **(struct CSessionTraceFlags ***)(v197 + 56)) != 0
              && CSessionTraceFlags::CheckSessionTraceInternal(v198, 0xD71u)
              || (qword_10317AD33 & 2) != 0
              || (v199 = *(_QWORD *)(SystemThread_TlsOffset
                                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
              && (v200 = **(struct CSessionTraceFlags ***)(v199 + 56)) != 0
              && CSessionTraceFlags::CheckSessionTraceInternal(v200, 0xD99u)
              || (qword_10317AD29 & 0x40000000000LL) != 0
              || (v201 = *(_QWORD *)(SystemThread_TlsOffset
                                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
              && (v202 = **(struct CSessionTraceFlags ***)(v201 + 56)) != 0
              && CSessionTraceFlags::CheckSessionTraceInternal(v202, 0xD72u) )
            {
              _mm_lfence();
              LODWORD(v206) = *(_DWORD *)(a1 + 1912);
              LogSystemMetadata(
                L"RU::EvaluateCheckpoint DB %d:%d give a slice back to data after %d evals. new Pie %I64d:%I64d:%I64d, rec"
                 "ent force writes %d.",
                *(unsigned __int16 *)(a1 + 1720),
                *(unsigned __int16 *)(a1 + 1632),
                *(unsigned int *)(a1 + 1916),
                *(_QWORD *)v217,
                *(_QWORD *)v216 + 1LL,
                *(_QWORD *)v218 - 1LL,
                v206);
            }
            --*(_QWORD *)(a1 + 1904);
            v63 = v367;
            HighPart = v366.HighPart;
            LowPart = v366.LowPart;
            v65 = v370.HighPart;
            v62 = v370.LowPart;
            *(_QWORD *)(a1 + 1912) = 0;
          }
          v74 = 1;
          v209 = 1;
          if ( (dword_10317F6CC & 2) != 0 )
          {
            v353 = 0x10000;
            v355 = v358;
            v354 = 0;
            v356 = &v359;
            v358[0] = &v362;
            v362 = *(unsigned __int16 *)(a1 + 1720);
            v364 = v221[0];
            v365 = v221[1];
            v360 = 0;
            v357 = 0;
            v361 = 0;
            v358[1] = 28;
            v363 = v59;
            XeSqlPkg::recovery_target_miss::Publish((XeSqlPkg::recovery_target_miss *)v352);
            HighPart = v366.HighPart;
            LowPart = v366.LowPart;
            v65 = v370.HighPart;
            v62 = v370.LowPart;
            v63 = v367;
          }
        }
        if ( LowPart < v62 || LowPart == v62 && (HighPart < v65 || HighPart == v65 && v63 < v371) )
          v210 = 1;
        v75 = v215;
        v84 = 0;
LABEL_327:
        if ( (qword_10317AD29 & 0x20000000000LL) != 0
          || (v156 = *(_QWORD *)(SystemThread_TlsOffset
                               + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v157 = **(struct CSessionTraceFlags ***)(v156 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v157, 0xD71u)
          || (qword_10317AD33 & 2) != 0
          || (v158 = *(_QWORD *)(SystemThread_TlsOffset
                               + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v159 = **(struct CSessionTraceFlags ***)(v158 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v159, 0xD99u)
          || (qword_10317AD29 & 0x40000000000LL) != 0
          || (v160 = *(_QWORD *)(SystemThread_TlsOffset
                               + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v161 = **(struct CSessionTraceFlags ***)(v160 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v161, 0xD72u)
          || (dword_10317F6CC & 0x800) != 0 )
        {
          v76 = v220;
          TraceRecoveryIndirectCheckpointEvent(
            *(unsigned __int16 *)(a1 + 1720),
            *(unsigned __int16 *)(a1 + 1632),
            v84,
            v228,
            v75,
            v66,
            v220,
            v223,
            v213,
            v224,
            (__int64)v221,
            *(_QWORD *)(a1 + 9552),
            *(_QWORD *)(a1 + 9560),
            (__int64)&v370,
            (__int64)&v375,
            (__int64)&v368,
            (__int64)&v366);
          goto LABEL_116;
        }
LABEL_115:
        v76 = v220;
LABEL_116:
        v77 = v212;
        goto LABEL_117;
      }
      if ( (qword_10317AD33 & 2) != 0
        || (v69 = *(_QWORD *)(SystemThread_TlsOffset
                            + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
        && (v70 = **(struct CSessionTraceFlags ***)(v69 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v70, 0xD99u)
        || (qword_10317AD29 & 0x40000000000LL) != 0
        || (v71 = *(_QWORD *)(SystemThread_TlsOffset
                            + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
        && (v72 = **(struct CSessionTraceFlags ***)(v71 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v72, 0xD72u) )
      {
        _mm_lfence();
        if ( v221[0] < 0 )
          v177 = (double)(int)(v221[0] & 1 | ((unsigned __int64)v221[0] >> 1))
               + (double)(int)(v221[0] & 1 | ((unsigned __int64)v221[0] >> 1));
        else
          v177 = (double)SLODWORD(v221[0]);
        v178 = v177 / 1000000.0;
        if ( (v59 & 0x8000000000000000uLL) != 0LL )
          v179 = (double)(int)(v59 & 1 | (v59 >> 1)) + (double)(int)(v59 & 1 | (v59 >> 1));
        else
          v179 = (double)(int)v59;
        v73 = v213;
        v180 = v179 / 1000000.0;
        if ( (v213 & 0x8000000000000000uLL) != 0LL )
          v181 = (double)(int)(v213 & 1 | (v213 >> 1)) + (double)(int)(v213 & 1 | (v213 >> 1));
        else
          v181 = (double)(int)v213;
        v182 = v181 * 0.00000095367431640625;
        if ( (v220 & 0x8000000000000000uLL) != 0LL )
          v183 = (double)(int)(v220 & 1 | (v220 >> 1)) + (double)(int)(v220 & 1 | (v220 >> 1));
        else
          v183 = (double)(int)v220;
        v184 = v183 / 1000000.0;
        if ( (v66 & 0x8000000000000000uLL) != 0LL )
          v185 = (double)(int)(v66 & 1 | (v66 >> 1)) + (double)(int)(v66 & 1 | (v66 >> 1));
        else
          v185 = (double)(int)v66;
        traceprint(
          L"RU::EvaluateCheckpoint DB %d:%d log under slice. Pie %I64d:%I64d:%I64d, log allowance %.2lf s, log scan %.2lf "
           "s, log %.2lf MB, data allowance %.2lf s, current %.2lf s (%I64d pages).",
          *(unsigned __int16 *)(a1 + 1720),
          *(unsigned __int16 *)(a1 + 1632),
          *(_QWORD *)v217,
          *(_QWORD *)v216,
          *(_QWORD *)v218,
          v185 / 1000000.0,
          v184,
          v182,
          v180,
          v178,
          v221[1]);
      }
      else
      {
        v73 = v213;
      }
      if ( *(_QWORD *)(a1 + 1904) && *(_DWORD *)(a1 + 1916) > 0x10u && v220 < v66 - v219 )
      {
        if ( (qword_10317AD29 & 0x20000000000LL) != 0
          || (v186 = *(_QWORD *)(SystemThread_TlsOffset
                               + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v187 = **(struct CSessionTraceFlags ***)(v186 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v187, 0xD71u)
          || (qword_10317AD33 & 2) != 0
          || (v188 = *(_QWORD *)(SystemThread_TlsOffset
                               + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v189 = **(struct CSessionTraceFlags ***)(v188 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v189, 0xD99u)
          || (qword_10317AD29 & 0x40000000000LL) != 0
          || (v190 = *(_QWORD *)(SystemThread_TlsOffset
                               + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v191 = **(struct CSessionTraceFlags ***)(v190 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v191, 0xD72u) )
        {
          _mm_lfence();
          LODWORD(v206) = *(_DWORD *)(a1 + 1912);
          LogSystemMetadata(
            L"RU::EvaluateCheckpoint DB %d:%d give a slice back to data after %d evals. new Pie %I64d:%I64d:%I64d, recent "
             "force writes %d.",
            *(unsigned __int16 *)(a1 + 1720),
            *(unsigned __int16 *)(a1 + 1632),
            *(unsigned int *)(a1 + 1916),
            *(_QWORD *)v217,
            *(_QWORD *)v216 + 1LL,
            *(_QWORD *)v218 - 1LL,
            v206);
        }
        --*(_QWORD *)(a1 + 1904);
        *(_QWORD *)(a1 + 1912) = 0;
        *(_BYTE *)(a1 + 1920) = 1;
      }
      if ( v366.LowPart < v368.LowPart
        || v366.LowPart == v368.LowPart
        && (v366.HighPart < (unsigned int)v368.HighPart
         || v366.HighPart == v368.HighPart && (unsigned __int16)v367 < (unsigned __int16)v369) )
      {
        v213 = (*(__int64 (__fastcall **)(_QWORD, LSN *, LSN *, __int64))(**(_QWORD **)(a1 + 1736) + 120LL))(
                 *(_QWORD *)(a1 + 1736),
                 &v366,
                 &v368,
                 1)
             + v73;
        v68 = v213 / dword_103188510;
        v220 = v68;
        if ( v68 > v66 >> 1 )
        {
          v209 = 1;
          if ( (qword_10317AD33 & 2) != 0
            || (v192 = *(_QWORD *)(SystemThread_TlsOffset
                                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
            && (v193 = **(struct CSessionTraceFlags ***)(v192 + 56)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v193, 0xD99u)
            || (qword_10317AD29 & 0x40000000000LL) != 0
            || (v194 = *(_QWORD *)(SystemThread_TlsOffset
                                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
            && (v195 = **(struct CSessionTraceFlags ***)(v194 + 56)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v195, 0xD72u) )
          {
            traceprint(
              L"RU::EvaluateCheckpoint DB %d:%d need to catch up with the current LSN.",
              *(unsigned __int16 *)(a1 + 1720),
              *(unsigned __int16 *)(a1 + 1632));
          }
          if ( (dword_10317F6CC & 8) != 0 )
          {
            LSN::FormatAsHexString(&v368, v385, &v241);
            LSN::FormatAsHexString(&v366, v384, &v240);
            if ( (dword_10317F6CC & 8) != 0 )
            {
              v300 = 196608;
              v302 = &v305;
              v301 = 0;
              v303 = &v314;
              v305 = &v317;
              v317 = *(unsigned __int16 *)(a1 + 1720);
              v196 = -1;
              v315 = 0;
              v304 = 0;
              v316 = 0;
              v306 = 20;
              v307 = 2;
              do
                ++v196;
              while ( v385[v196] );
              v310 = 1;
              v309 = 2 * v196;
              v308 = v385;
              do
                ++v34;
              while ( v384[v34] );
              v313 = 2;
              v312 = 2 * v34;
              v311 = v384;
              XeSqlPkg::recovery_catch_checkpoint::Publish((XeSqlPkg::recovery_catch_checkpoint *)v299);
            }
          }
        }
      }
      if ( v370.LowPart != v368.LowPart )
      {
        if ( (byte_10317ACF7 & 1) != 0
          || (v81 = *(_QWORD *)(SystemThread_TlsOffset
                              + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
          && (v82 = **(struct CSessionTraceFlags ***)(v81 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v82, 0xBB8u)
          || byte_10316EAEA
          && (byte_10317ACFD & 0x40) == 0
          && (*(_QWORD *)(*(_QWORD *)(a1 + 1712) + 640LL)
           || (v83 = *(_DWORD **)(a1 + 1736), !v83[801]) && !v83[799] && !v83[800]) )
        {
          v75 = v215;
          v84 = 1;
          v74 = 1;
          goto LABEL_327;
        }
      }
      if ( (dword_10317F6CC & 0x20) != 0 )
      {
        v336 = 0x10000;
        v338 = v341;
        v337 = 0;
        v339 = &v342;
        v341[0] = &v345;
        v345 = *(unsigned __int16 *)(a1 + 1720);
        v346 = v213;
        v347 = v68 >> 10;
        v348 = v66 >> 10;
        v349 = (unsigned __int64)v221[0] >> 10;
        v350 = v221[1];
        v351 = v59 >> 10;
        v343 = 0;
        v340 = 0;
        v344 = 0;
        v341[1] = 52;
        XeSqlPkg::recovery_skip_checkpoint::Publish((XeSqlPkg::recovery_skip_checkpoint *)v335);
      }
      v74 = 3;
      goto LABEL_114;
    }
    v167 = v48;
    v66 = v212;
    v168 = v167 / dword_103188510;
    v67 = v219;
    if ( v168 <= v212 )
      goto LABEL_97;
    v210 = 1;
    if ( v168 <= v212 + 2 * v219 || *(_QWORD *)(a1 + 1904) >= v233 || v221[0] >= v59 )
      goto LABEL_97;
    _mm_lfence();
    v169 = *(_QWORD *)v216;
    v170 = 1;
    if ( !*(_BYTE *)(a1 + 1920) && *(_QWORD *)v216 > 0x10u )
    {
      v171 = *(_QWORD *)v216;
      if ( v221[0] / (v59 / *(_QWORD *)v216) < *(_QWORD *)v216 )
        v171 = v221[0] / (v59 / *(_QWORD *)v216);
      v170 = *(_QWORD *)v216 - v171;
      if ( (unsigned __int64)(*(_QWORD *)v216 - v171) <= 1 )
      {
        v170 = 1;
      }
      else if ( v170 > 0x10 )
      {
        v170 = 16;
        goto LABEL_362;
      }
      *(_BYTE *)(a1 + 1920) = 1;
    }
LABEL_362:
    *(_QWORD *)(a1 + 1904) += v170;
    v172 = v227;
    v173 = v169 - v170;
    if ( v226 < v227 )
      v172 = v226;
    v174 = v173 * v229 / v172;
    v175 = v217[0];
    *(_QWORD *)(a1 + 1912) = 0;
    v59 = dword_10318850C * v174;
    v176 = *(_QWORD *)(a1 + 1880);
    *(_QWORD *)v216 = v173;
    v215 = v59;
    *(_QWORD *)(v176 + 16) = v59;
    TraceRecoveryTargetResetEvent(
      *(unsigned __int16 *)(a1 + 1720),
      *(unsigned __int16 *)(a1 + 1632),
      (unsigned int)L"log behind",
      v175,
      v173,
      v170 + *(_QWORD *)v218,
      v205,
      v59,
      (__int64)v221);
    HighPart = v366.HighPart;
    LowPart = v366.LowPart;
    v65 = v370.HighPart;
    v62 = v370.LowPart;
    v63 = v367;
    goto LABEL_96;
  }
  if ( (qword_10317AD33 & 2) != 0
    || (v91 = *(_QWORD *)(SystemThread_TlsOffset
                        + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
    && (v92 = **(struct CSessionTraceFlags ***)(v91 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v92, 0xD99u)
    || (qword_10317AD29 & 0x40000000000LL) != 0
    || (v93 = *(_QWORD *)(SystemThread_TlsOffset
                        + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
    && (v94 = **(struct CSessionTraceFlags ***)(v93 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v94, 0xD72u) )
  {
    if ( (v33 & 0x8000000000000000uLL) != 0LL )
      v95 = (double)(int)(v33 & 1 | (v33 >> 1)) + (double)(int)(v33 & 1 | (v33 >> 1));
    else
      v95 = (double)(int)v33;
    traceprint(
      L"RU::EvaluateCheckpoint DB %d:%d. initial data allowance %.2lf s.",
      *(unsigned __int16 *)(a1 + 1720),
      *(unsigned __int16 *)(a1 + 1632),
      v95 / 1000000.0,
      v203);
  }
  return 3;
}

```

## disassembly

```asm
0x1004a6110  mov     [rsp-8+arg_8], rbx
0x1004a6115  mov     [rsp-8+arg_10], rsi
0x1004a611a  mov     [rsp-8+arg_18], rdi
0x1004a611f  push    rbp
0x1004a6120  push    r12
0x1004a6122  push    r13
0x1004a6124  push    r14
0x1004a6126  push    r15
0x1004a6128  lea     rbp, [rsp-1400h]
0x1004a6130  mov     eax, 1510h
0x1004a6135  call    _alloca_probe
0x1004a613a  sub     rsp, rax
0x1004a613d  mov     rax, cs:__security_cookie
0x1004a6144  xor     rax, rsp
0x1004a6147  mov     [rbp+1420h+var_40], rax
0x1004a614e  movzx   r15d, word ptr [rcx+6B8h]
0x1004a6156  xor     edi, edi
0x1004a6158  mov     rbx, [rcx+758h]
0x1004a615f  xor     al, al
0x1004a6161  mov     r13d, 2
0x1004a6167  mov     [rbp+1420h+var_1450], rdi
0x1004a616b  cmp     r13w, r15w
0x1004a616f  mov     qword ptr [rbp+1420h+var_1440], rdi
0x1004a6173  mov     edx, edi
0x1004a6175  mov     qword ptr [rbp+1420h+var_1440+8], rdi
0x1004a6179  mov     r14d, 20h ; ' '
0x1004a617f  mov     [rbp+1420h+var_1450+8], rdx
0x1004a6183  mov     rsi, rcx
0x1004a6186  mov     qword ptr [rbp+1420h+var_3F0], rdi
0x1004a618d  cmovz   r14d, edi
0x1004a6191  mov     [rbp+1420h+var_3E8], edi
0x1004a6197  mov     r8d, edi
0x1004a619a  mov     [rbp+1420h+var_3CE], di
0x1004a61a1  mov     r9d, edi
0x1004a61a4  mov     qword ptr [rbp+1420h+var_3E4], rdi
0x1004a61ab  mov     r10d, edi
0x1004a61ae  mov     [rbp+1420h+var_3DC], edi
0x1004a61b4  mov     [rbp+1420h+var_149C], r15w
0x1004a61b9  mov     r11d, edi
0x1004a61bc  mov     [rbp+1420h+var_13CA], di
0x1004a61c0  mov     ecx, edi
0x1004a61c2  mov     [rbp+1420h+var_149F], al
0x1004a61c5  mov     [rbp+1420h+var_149E], al
0x1004a61c8  nop     dword ptr [rax+rax+00000000h]
0x1004a61d0  mov     rax, [rbx+118h]
0x1004a61d7  lea     rcx, [rcx+0C0h]
0x1004a61de  inc     r11
0x1004a61e1  add     r8, [rcx+rax-48h]
0x1004a61e6  mov     [rbp+1420h+var_1450], r8
0x1004a61ea  add     rdx, [rcx+rax-40h]
0x1004a61ef  mov     [rbp+1420h+var_1450+8], rdx
0x1004a61f3  add     r9, [rcx+rax-38h]
0x1004a61f8  mov     qword ptr [rbp+1420h+var_1440], r9
0x1004a61fc  add     r10, [rcx+rax-30h]
0x1004a6201  mov     qword ptr [rbp+1420h+var_1440+8], r10
0x1004a6205  movsxd  rax, dword ptr [rbx+0FCh]
0x1004a620c  cmp     r11, rax
0x1004a620f  jbe     short loc_1004A61D0
0x1004a6211  mov     rax, [rbx+110h]
0x1004a6218  mov     ebx, 1
0x1004a621d  mov     [rax+6AB0h], rdx
0x1004a6224  lea     r8d, [rbx+0Fh]
0x1004a6228  lea     r12d, [rbx+7]
0x1004a622c  cmp     r13w, r15w
0x1004a6230  jz      loc_1004A6AE6
0x1004a6236  mov     rax, qword ptr [rbp+1420h+var_1440+8]
0x1004a623a  cmp     rax, 2710h
0x1004a6240  jb      loc_1005F8E61
0x1004a6246  imul    rax, 1388h
0x1004a624d  cmp     rax, qword ptr [rbp+1420h+var_1440]
0x1004a6251  jb      loc_1005F8E61
0x1004a6257  mov     rcx, cs:__imp_?SOS_OS_MemoryModel@@3W4SOS_MemoryModel@@A; SOS_MemoryModel SOS_OS_MemoryModel
0x1004a625e  mov     edx, [rcx]
0x1004a6260  sub     edx, ebx
0x1004a6262  jz      loc_1005F8E61
0x1004a6268  sub     edx, ebx
0x1004a626a  jz      short loc_1004A6274
0x1004a626c  cmp     edx, ebx
0x1004a626e  jnz     loc_1005F8E39
0x1004a6274  mov     r15, r8
0x1004a6277  jmp     short loc_1004A627A
0x1004a627a  mov     rax, [rsi+770h]
0x1004a6281  mov     edx, 80h
0x1004a6286  mov     ecx, edx
0x1004a6288  mov     qword ptr [rbp+1420h+var_1470], r15
0x1004a628c  sub     rcx, r15
0x1004a628f  sub     rcx, r14
0x1004a6292  lea     r8, [rcx-1]
0x1004a6296  cmp     rax, r8
0x1004a6299  mov     [rbp+1420h+var_13D8], r8
0x1004a629d  cmovnb  rax, r8
0x1004a62a1  mov     [rsi+770h], rax
0x1004a62a8  add     rax, r14
0x1004a62ab  sub     rdx, rax
0x1004a62ae  mov     qword ptr [rbp+1420h+var_1468], rax
0x1004a62b2  sub     rdx, r15
0x1004a62b5  mov     qword ptr [rbp+1420h+var_1478], rdx
0x1004a62b9  jz      loc_101D02450
0x1004a62bf  cmp     rdx, rcx
0x1004a62c2  ja      loc_101D02450
0x1004a62c8  mov     rax, [rsi+758h]
0x1004a62cf  mov     r8d, 0FFFFFFFFh
0x1004a62d5  inc     dword ptr [rsi+77Ch]
0x1004a62db  mov     r12, rdi
0x1004a62de  mov     r13, [rsi+6A0h]
0x1004a62e5  mov     r14, rdi
0x1004a62e8  mov     dword ptr [rsp+1530h+var_14F0], edi
0x1004a62ec  mov     ecx, [rax+104h]
0x1004a62f2  test    rcx, rcx
0x1004a62f5  mov     [rsp+1530h+var_14F8], rdi
0x1004a62fa  mov     [rsp+1530h+var_1500], rdi
0x1004a62ff  cmovz   rcx, rbx
0x1004a6303  mov     dword ptr [rsp+1530h+var_1508], edi
0x1004a6307  imul    rax, rcx, 0F4240h
0x1004a630e  xor     r9d, r9d
0x1004a6311  mov     [rbp+1420h+var_14A0], bl
0x1004a6314  mov     [rbp+1420h+var_1398], rax
0x1004a631b  shr     rax, 7
0x1004a631f  mov     [rbp+1420h+var_1460], rax
0x1004a6323  imul    rax, r15
0x1004a6327  lea     edx, [r9+4]
0x1004a632b  mov     [rsp+1530h+var_1510], rdi
0x1004a6330  mov     [rbp+1420h+var_1400], rax
0x1004a6334  lea     rax, [r13+30h]
0x1004a6338  mov     rcx, rax
0x1004a633b  mov     [rbp+1420h+var_1410], rax
0x1004a633f  call    ?AcquireInternal@LatchBase@@AEAA?AW4AcquireResult@1@W4LATCH_TYPE@1@KPEAVLatchSuspendInfo@@PEAUSubLatchInfo@1@W4Releasor@1@PEA_KPEAVSOS_LsAccessCache@@W4LatchYieldBehavior@1@@Z; LatchBase::AcquireInternal(LatchBase::LATCH_TYPE,ulong,LatchSuspendInfo *,LatchBase::SubLatchInfo *,LatchBase::Releasor,unsigned __int64 *,SOS_LsAccessCache *,LatchBase::LatchYieldBehavior)
0x1004a6344  mov     eax, 1
0x1004a6349  movzx   r15d, ax
0x1004a634d  cmp     ax, [r13+74h]
0x1004a6352  ja      short loc_1004A63D0
0x1004a6354  nop
0x1004a6355  nop     word ptr [rax+rax+00000000h]
0x1004a6360  mov     rax, [r13+50h]
0x1004a6364  movzx   ecx, r15w
0x1004a6368  mov     rbx, [rax+rcx*8-8]
0x1004a636d  test    rbx, rbx
0x1004a6370  jz      short loc_1004A63C1
0x1004a6372  test    byte ptr [rbx+64h], 40h
0x1004a6376  jnz     short loc_1004A63C1
0x1004a6378  mov     rax, [rbx]
0x1004a637b  mov     rcx, rbx
0x1004a637e  call    qword ptr [rax+80h]
0x1004a6384  test    eax, eax
0x1004a6386  jz      short loc_1004A63C1
0x1004a6388  inc     r12
0x1004a638b  cmp     [rbx+58h], dil
0x1004a638f  jnz     loc_101D02485
0x1004a6395  cmp     [rbx+10D0h], edi
0x1004a639b  jz      loc_101D02485
0x1004a63a1  mov     rax, [rbx+288h]
0x1004a63a8  mov     [rbp+1420h+var_14A0], dil
0x1004a63ac  test    rax, rax
0x1004a63af  jz      loc_101D02478
0x1004a63b5  mov     eax, [rax]
0x1004a63b7  dec     eax
0x1004a63b9  cdqe
0x1004a63bb  add     r14, rax
0x1004a63be  jmp     short loc_1004A63C1
0x1004a63c1  inc     r15w
0x1004a63c5  cmp     r15w, [r13+74h]
0x1004a63ca  jbe     short loc_1004A6360
0x1004a63cc  movzx   ebx, [rbp+1420h+var_14A0]
0x1004a63d0  mov     rcx, [rbp+1420h+var_1410]
0x1004a63d4  mov     edx, 4
0x1004a63d9  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x1004a63de  cmp     cs:byte_10316EA3F, dil
0x1004a63e5  jnz     loc_101D0248E
0x1004a63eb  test    byte ptr cs:qword_10317AD29+5, 10h
0x1004a63f2  jnz     loc_101D0248E
0x1004a63f8  test    bl, bl
0x1004a63fa  jnz     loc_101D0248E
0x1004a6400  mov     edx, 5
0x1004a6405  test    r14, r14
0x1004a6408  jz      loc_101D02497
0x1004a640e  mov     eax, 2
0x1004a6413  mov     rbx, r12
0x1004a6416  cmp     ax, [rbp+1420h+var_149C]
0x1004a641a  cmovnz  rbx, r14
0x1004a641e  mov     r14, r12
0x1004a6421  imul    r14, r12
0x1004a6425  lea     r12, [r12+r12*4]
0x1004a6429  mov     [rbp+1420h+var_1410], rbx
0x1004a642d  mov     rdx, r14
0x1004a6430  mov     [rbp+1420h+var_1408], r12
0x1004a6434  imul    rdx, [rbp+1420h+var_1460]
0x1004a6439  mov     rax, rdx
0x1004a643c  mov     [rbp+1420h+var_13F8], rdx
0x1004a6440  imul    rax, qword ptr [rbp+1420h+var_1478]
0x1004a6445  cmp     rbx, r12
0x1004a6448  jb      loc_1004A6AEF
0x1004a644e  mov     rcx, r12
0x1004a6451  xor     edx, edx
0x1004a6453  div     rcx
0x1004a6456  mov     r15, rax
0x1004a6459  movsxd  rax, cs:dword_10318850C
0x1004a6460  imul    r15, rax
0x1004a6464  mov     [rbp+1420h+var_1480], r15
0x1004a6468  test    r15, r15
0x1004a646b  jz      loc_101D024C1
0x1004a6471  mov     rax, [rsi+758h]
0x1004a6478  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1004a647f  mov     [rax+10h], r15
0x1004a6483  mov     r8, [rbp+1420h+var_1450]
0x1004a6487  test    r8, r8
0x1004a648a  jz      loc_101D024EB
0x1004a6490  movsxd  rcx, cs:dword_10318850C
0x1004a6497  xor     edx, edx
0x1004a6499  mov     rax, r8
0x1004a649c  div     rcx
0x1004a649f  cmp     rbx, r12
0x1004a64a2  mov     rcx, rax
0x1004a64a5  mov     rax, r12
0x1004a64a8  cmovb   rax, rbx
0x1004a64ac  mul     rcx
0x1004a64af  mov     rcx, r13
0x1004a64b2  test    rdx, rdx
0x1004a64b5  mov     [rbp+1420h+var_1380], rdx
0x1004a64bc  cmovz   rcx, rax
0x1004a64c0  xor     edx, edx
0x1004a64c2  mov     rax, rcx
0x1004a64c5  div     r14
0x1004a64c8  mov     [rbp+1420h+var_1430], rax
0x1004a64cc  cmp     dword ptr [rsi+670h], 4
0x1004a64d3  jl      loc_101D024F5
0x1004a64d9  movaps  [rsp+1530h+var_30], xmm6
0x1004a64e1  cmp     r8, r15
0x1004a64e4  ja      loc_101D025ED
0x1004a64ea  cmp     dword ptr [rsi+778h], 2
0x1004a64f1  ja      loc_101D025FA
0x1004a64f7  mov     r12, qword ptr [rbp+1420h+var_1468]
0x1004a64fb  movsd   xmm6, cs:__real@412e848000000000
0x1004a6503  cmp     [rsi+2051h], dil
0x1004a650a  jnz     short loc_1004A651F
0x1004a650c  mov     rax, r15
0x1004a650f  shr     rax, 4
0x1004a6513  add     rax, r15
0x1004a6516  cmp     r8, rax
0x1004a6519  ja      loc_101D02815
0x1004a651f  cmp     [rsi+1CD7h], dil
0x1004a6526  jnz     loc_101D02A8A
0x1004a652c  mov     rcx, [rsi+6C8h]
0x1004a6533  mov     r14, [rbp+1420h+var_1460]
0x1004a6537  imul    r14, r12
0x1004a653b  mov     rax, [rcx]
0x1004a653e  mov     [rbp+1420h+var_1498], r14
0x1004a6542  call    qword ptr [rax+60h]
0x1004a6545  mov     ecx, gs:48h
0x1004a654d  mov     rbx, rdi
0x1004a6550  mov     r15, [rsi+6B0h]
0x1004a6557  mov     r12d, ecx
0x1004a655a  mov     [rbp+1420h+var_1428], rax
0x1004a655e  mov     [rbp+1420h+var_1490], rax
0x1004a6562  mov     ecx, [r15+1500h]
0x1004a6569  test    ecx, ecx
0x1004a656b  jnz     loc_101D02C3D
0x1004a6571  xor     eax, eax
0x1004a6573  lock cmpxchg [r15+1500h], r12
0x1004a657c  mov     eax, edi
0x1004a657e  setz    al
0x1004a6581  test    eax, eax
0x1004a6583  jz      loc_101D02C3D
0x1004a6589  movzx   eax, word ptr [rsi+88Ch]
0x1004a6590  movsd   xmm0, qword ptr [rsi+884h]
0x1004a6598  mov     rbx, [rsi+6B0h]
0x1004a659f  mov     [rbp+1420h+var_3D0], ax
0x1004a65a6  mov     eax, [rsi+898h]
0x1004a65ac  mov     [rbp+1420h+var_3B0], eax
0x1004a65b2  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004a65b9  movsd   qword ptr [rbp+1420h+var_3D8], xmm0
0x1004a65c1  movsd   xmm0, qword ptr [rsi+890h]
0x1004a65c9  movsd   qword ptr [rbp+1420h+var_3B8], xmm0
0x1004a65d1  cmp     [rax], dil
0x1004a65d4  jnz     loc_101D02D40
0x1004a65da  mov     [rbx+1500h], rdi
0x1004a65e1  lea     rdx, [rbp+1420h+var_3E4]
0x1004a65e8  mov     rcx, [rsi+6C8h]
0x1004a65ef  mov     rax, [rcx]
0x1004a65f2  call    qword ptr [rax+28h]
0x1004a65f5  mov     rcx, [rsi+758h]; this
0x1004a65fc  lea     rdx, [rbp+1420h+var_3F0]; struct AlignedLSN *
0x1004a6603  xor     r9d, r9d; bool
0x1004a6606  xor     r8d, r8d; struct PageId *
0x1004a6609  call    ?GetOldestDirtyLSN@DirtyPageMgr@@QEAA_NAEAVAlignedLSN@@PEAVPageId@@_N@Z; DirtyPageMgr::GetOldestDirtyLSN(AlignedLSN &,PageId *,bool)
0x1004a660e  mov     eax, 2
0x1004a6613  cmp     ax, [rbp+1420h+var_149C]
0x1004a6617  jz      loc_1004A6AF8
0x1004a661d  mov     eax, dword ptr [rbp+1420h+var_3B8]
0x1004a6623  mov     r12, rdi
0x1004a6626  cmp     eax, dword ptr [rbp+1420h+var_3D8]
0x1004a662c  jb      loc_101D02D72
0x1004a6632  jnz     short loc_1004A665C
0x1004a6634  mov     eax, dword ptr [rbp+1420h+var_3B8+4]
0x1004a663a  cmp     eax, dword ptr [rbp+1420h+var_3D8+4]
0x1004a6640  jb      loc_101D02D72
0x1004a6646  jnz     short loc_1004A665C
0x1004a6648  movzx   eax, [rbp+1420h+var_3D0]
0x1004a664f  cmp     word ptr [rbp+1420h+var_3B0], ax
0x1004a6656  jb      loc_101D02D72
0x1004a665c  mov     rax, [rbp+1420h+var_1490]
  ... truncated ...
```
