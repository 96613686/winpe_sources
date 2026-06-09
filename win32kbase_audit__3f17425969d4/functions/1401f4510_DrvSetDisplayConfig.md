# DrvSetDisplayConfig

- ea: `0x1401f4510`
- end: `0x1401f5d07`
- name: `DrvSetDisplayConfig`
- size: `6135`
- prototype: `__int64 __fastcall(unsigned int, struct DISPLAYCONFIG_PATH_INFO_INTERNAL *, __int64, __int64, void *, char, __int64, struct _DISPLAYCONFIG_CDS_REQUEST *, struct _MDEV *, struct _MDEV **, unsigned int *, int *, char *, _BYTE *, _BYTE *, __int64, __int64)`
- caller_count: `5`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140112574`
- `0x140197a80`
- `0x1401bf420`
- `0x1401c0540`
- `0x1401d1494`

## callees

- `0x14006e970`
- `0x1400962b0`
- `0x1400a3120`
- `0x1400f08ac`
- `0x14010d428`
- `0x14015db38`
- `0x140164040`
- `0x140178620`
- `0x14017f600`
- `0x14019ce90`
- `0x1401ae124`
- `0x1401af5e0`
- `0x1401b0394`
- `0x1401ce6fc`
- `0x1401ced54`
- `0x1401e9ccc`
- `0x1401e9f08`
- `0x1401ea13c`
- `0x1401eab9c`
- `0x1401eaf40`
- `0x1401eb4c8`
- `0x1401ee650`
- `0x1401ee8c0`
- `0x1401eef10`
- `0x1401f010c`
- `0x1401f08a8`
- `0x1401f19cc`
- `0x1401f1f5c`
- `0x1401f2120`
- `0x1401f4510`
- `0x1402388e0`
- `0x1402389c0`

## import_xrefs

- `watchdog!DisplayScenarioJournalSetResult` at `0x1401f5c8e`
- `watchdog!DisplayScenarioJournalSetResult` at `0x1401f5c8e`
- `watchdog!DisplayScenarioJournalSetUniqueness` at `0x1401f5c62`
- `watchdog!DisplayScenarioJournalSetUniqueness` at `0x1401f5c62`
- `watchdog!DisplayScenarioJounralSetTSDDDState` at `0x1401f5b2a`
- `watchdog!DisplayScenarioJounralSetTSDDDState` at `0x1401f5b2a`
- `watchdog!DisplayScenarioJournalRetry` at `0x1401f56de`
- `watchdog!DisplayScenarioJournalRetry` at `0x1401f5738`
- `watchdog!DisplayScenarioJournalRetry` at `0x1401f56de`
- `watchdog!DisplayScenarioJournalRetry` at `0x1401f5738`
- `watchdog!DisplayScenarioJournalSetExpectedPathModality` at `0x1401f5392`
- `watchdog!DisplayScenarioJournalSetExpectedPathModality` at `0x1401f5392`
- `watchdog!WdDiagNotifyUser` at `0x1401f4706`
- `watchdog!WdDiagNotifyUser` at `0x1401f4706`
- `watchdog!DisplayScenarioJournalSetActualPathModality` at `0x1401f58ea`
- `watchdog!DisplayScenarioJournalSetActualPathModality` at `0x1401f58ea`
- `watchdog!WdLogSingleEntry0` at `0x1401f46d2`
- `watchdog!WdLogSingleEntry0` at `0x1401f47b6`
- `watchdog!WdLogSingleEntry0` at `0x1401f4b6b`
- `watchdog!WdLogSingleEntry0` at `0x1401f4b8a`
- `watchdog!WdLogSingleEntry0` at `0x1401f4c36`
- `watchdog!WdLogSingleEntry0` at `0x1401f4d16`
- `watchdog!WdLogSingleEntry0` at `0x1401f4d43`
- `watchdog!WdLogSingleEntry0` at `0x1401f4d8d`
- `watchdog!WdLogSingleEntry0` at `0x1401f4dfc`
- `watchdog!WdLogSingleEntry0` at `0x1401f5415`
- `watchdog!WdLogSingleEntry0` at `0x1401f543a`
- `watchdog!WdLogSingleEntry0` at `0x1401f5463`
- `watchdog!WdLogSingleEntry0` at `0x1401f5490`
- `watchdog!WdLogSingleEntry0` at `0x1401f54bc`
- `watchdog!WdLogSingleEntry0` at `0x1401f5592`
- `watchdog!WdLogSingleEntry0` at `0x1401f55e5`
- `watchdog!WdLogSingleEntry0` at `0x1401f56fe`
- `watchdog!WdLogSingleEntry0` at `0x1401f5720`
- `watchdog!WdLogSingleEntry0` at `0x1401f5758`
- `watchdog!WdLogSingleEntry0` at `0x1401f582c`
- `watchdog!WdLogSingleEntry0` at `0x1401f5864`
- `watchdog!WdLogSingleEntry0` at `0x1401f5a00`
- `watchdog!WdLogSingleEntry0` at `0x1401f5bbd`
- `watchdog!WdLogSingleEntry0` at `0x1401f46d2`
- `watchdog!WdLogSingleEntry0` at `0x1401f47b6`
- `watchdog!WdLogSingleEntry0` at `0x1401f4b6b`
- `watchdog!WdLogSingleEntry0` at `0x1401f4b8a`
- `watchdog!WdLogSingleEntry0` at `0x1401f4c36`
- `watchdog!WdLogSingleEntry0` at `0x1401f4d16`
- `watchdog!WdLogSingleEntry0` at `0x1401f4d43`
- `watchdog!WdLogSingleEntry0` at `0x1401f4d8d`
- `watchdog!WdLogSingleEntry0` at `0x1401f4dfc`
- `watchdog!WdLogSingleEntry0` at `0x1401f5415`
- `watchdog!WdLogSingleEntry0` at `0x1401f543a`
- `watchdog!WdLogSingleEntry0` at `0x1401f5463`
- `watchdog!WdLogSingleEntry0` at `0x1401f5490`
- `watchdog!WdLogSingleEntry0` at `0x1401f54bc`
- `watchdog!WdLogSingleEntry0` at `0x1401f5592`
- `watchdog!WdLogSingleEntry0` at `0x1401f55e5`
- `watchdog!WdLogSingleEntry0` at `0x1401f56fe`
- `watchdog!WdLogSingleEntry0` at `0x1401f5720`
- `watchdog!WdLogSingleEntry0` at `0x1401f5758`
- `watchdog!WdLogSingleEntry0` at `0x1401f582c`
- `watchdog!WdLogSingleEntry0` at `0x1401f5864`
- `watchdog!WdLogSingleEntry0` at `0x1401f5a00`
- `watchdog!WdLogSingleEntry0` at `0x1401f5bbd`
- `watchdog!WdLogSingleEntry1` at `0x1401f463a`
- `watchdog!WdLogSingleEntry1` at `0x1401f4ab6`
- `watchdog!WdLogSingleEntry1` at `0x1401f4c6b`
- `watchdog!WdLogSingleEntry1` at `0x1401f4ed2`
- `watchdog!WdLogSingleEntry1` at `0x1401f5195`
- `watchdog!WdLogSingleEntry1` at `0x1401f5553`
- `watchdog!WdLogSingleEntry1` at `0x1401f5640`
- `watchdog!WdLogSingleEntry1` at `0x1401f566c`
- `watchdog!WdLogSingleEntry1` at `0x1401f5cb4`
- `watchdog!WdLogSingleEntry1` at `0x1401f463a`
- `watchdog!WdLogSingleEntry1` at `0x1401f4ab6`
- `watchdog!WdLogSingleEntry1` at `0x1401f4c6b`
- `watchdog!WdLogSingleEntry1` at `0x1401f4ed2`
- `watchdog!WdLogSingleEntry1` at `0x1401f5195`
- `watchdog!WdLogSingleEntry1` at `0x1401f5553`
- `watchdog!WdLogSingleEntry1` at `0x1401f5640`
- `watchdog!WdLogSingleEntry1` at `0x1401f566c`
- `watchdog!WdLogSingleEntry1` at `0x1401f5cb4`
- `watchdog!DisplayScenarioJournalSetSpecializedData` at `0x1401f5bfa`
- `watchdog!DisplayScenarioJournalSetSpecializedData` at `0x1401f5bfa`
- `watchdog!DisplayScenarioJournalFinalize` at `0x1401f5ca0`
- `watchdog!DisplayScenarioJournalFinalize` at `0x1401f5ca0`
- `watchdog!DisplayScenarioJournalCCDRetrieval` at `0x1401f4dad`
- `watchdog!DisplayScenarioJournalCCDRetrieval` at `0x1401f4dad`
- `watchdog!DisplayScenarioJournalSetSDCPathsAndModes` at `0x1401f469b`
- `watchdog!DisplayScenarioJournalSetSDCPathsAndModes` at `0x1401f469b`
- `watchdog!DisplayScenarioJournalBegin` at `0x1401f4681`
- `watchdog!DisplayScenarioJournalBegin` at `0x1401f4681`
- `watchdog!WdLogSingleEntry2` at `0x1401f4b0d`
- `watchdog!WdLogSingleEntry2` at `0x1401f5166`
- `watchdog!WdLogSingleEntry2` at `0x1401f51ca`
- `watchdog!WdLogSingleEntry2` at `0x1401f526d`
- `watchdog!WdLogSingleEntry2` at `0x1401f55bf`
- `watchdog!WdLogSingleEntry2` at `0x1401f4b0d`
- `watchdog!WdLogSingleEntry2` at `0x1401f5166`
- `watchdog!WdLogSingleEntry2` at `0x1401f51ca`
- `watchdog!WdLogSingleEntry2` at `0x1401f526d`
- `watchdog!WdLogSingleEntry2` at `0x1401f55bf`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f4812`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f486a`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f48d8`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f495e`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f49b0`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f49d8`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f4a17`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f4a8c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f4f86`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f50e8`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f512c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f5231`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f52fe`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f551a`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f5a29`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f4812`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f486a`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f48d8`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f495e`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f49b0`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f49d8`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f4a17`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f4a8c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f4f86`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f50e8`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f512c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f5231`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f52fe`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f551a`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f5a29`
- `WIN32K!W32GetSessionState` at `0x1401f45d4`
- `WIN32K!W32GetSessionState` at `0x1401f45d4`
- `WIN32K!W32GetUserSessionState` at `0x1401f4667`
- `WIN32K!W32GetUserSessionState` at `0x1401f4667`

## pseudocode

```c
__int64 __fastcall DrvSetDisplayConfig(
        unsigned int a1,
        struct DISPLAYCONFIG_PATH_INFO_INTERNAL *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        char a6,
        __int64 a7,
        struct _DISPLAYCONFIG_CDS_REQUEST *a8,
        struct _MDEV *a9,
        struct _MDEV **a10,
        unsigned int *a11,
        int *a12,
        char *a13,
        _BYTE *a14,
        _BYTE *a15,
        __int64 a16,
        __int64 a17)
{
  unsigned int v17; // r12d
  struct _MDEV *v18; // r14
  struct _MDEV **v19; // rbx
  unsigned int v20; // r15d
  int v21; // r13d
  __int64 v22; // rcx
  int v23; // esi
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 UserSessionState; // rax
  __int64 v28; // rax
  struct _DISPLAYCONFIG_CDS_REQUEST *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rdi
  int v35; // ebx
  __int64 DxgkWin32kInterface; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // ebx
  char v41; // r14
  char v42; // r12
  int v43; // ebx
  char v44; // r14
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rbx
  __int64 v53; // rax
  int v54; // eax
  bool v55; // bl
  __int64 v56; // r14
  unsigned int v57; // r12d
  __int64 v58; // rbx
  __int64 v59; // rcx
  const struct RETRY_MODE *v60; // rbx
  int PathsModality; // eax
  int v62; // eax
  __int64 v63; // rcx
  __int16 v64; // r13
  int v65; // ebx
  bool v66; // si
  int CurrentMode; // eax
  __int64 v68; // rcx
  __int16 v69; // ax
  char v70; // r13
  unsigned int v71; // ebx
  __int64 v72; // rcx
  int v73; // ebx
  int v74; // eax
  struct _DISPLAYCONFIG_CDS_REQUEST *v75; // rbx
  int v76; // eax
  int PathPersistentMonitorsIfNeeded; // eax
  __int64 v78; // rcx
  int v79; // eax
  __int64 v80; // rcx
  __int64 v81; // rax
  int v82; // eax
  __int64 v83; // rcx
  unsigned int v84; // r12d
  __int64 v85; // rax
  __int64 v86; // rax
  int v87; // eax
  unsigned int CcdRawmodeFlag; // eax
  struct _DISPLAYCONFIG_CDS_REQUEST *v89; // rcx
  __int16 v90; // di
  int v91; // eax
  unsigned int v92; // ebx
  __int64 v93; // rax
  __int64 v94; // rcx
  __int64 (__fastcall *v95)(__int64, PVOID); // rax
  int v96; // eax
  __int64 v97; // rcx
  unsigned int v98; // ebx
  __int64 v99; // rax
  __int64 v100; // r9
  int v101; // edi
  __int64 v102; // rcx
  bool v103; // zf
  unsigned int v104; // eax
  int v105; // r8d
  struct _MDEV **v106; // rbx
  int v107; // eax
  int v108; // r13d
  __int64 v109; // rax
  int v110; // eax
  unsigned int v111; // eax
  __int64 v112; // rcx
  int v113; // eax
  int v114; // eax
  char v115; // al
  struct _MDEV *v116; // rbx
  char *v117; // rcx
  __int64 v118; // rdx
  __int64 v119; // rax
  int v120; // eax
  __int64 v121; // rcx
  __int64 v122; // rax
  __int64 v123; // rcx
  PVOID v124; // rdx
  char v125; // r9
  unsigned int v126; // ecx
  __int64 v127; // r8
  __int64 v128; // rax
  int v129; // eax
  __int64 v130; // rcx
  __int64 v131; // rcx
  __int64 v132; // rcx
  char v133; // al
  char v134; // r12
  char v135; // bl
  struct _DISPLAYCONFIG_CDS_REQUEST *v136; // rax
  __int64 v137; // rsi
  unsigned int v138; // ebx
  __int64 v139; // rcx
  int v141; // [rsp+20h] [rbp-E0h]
  int v142; // [rsp+28h] [rbp-D8h]
  char v143; // [rsp+60h] [rbp-A0h]
  int v144; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 v145; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 v146; // [rsp+69h] [rbp-97h]
  char v147; // [rsp+6Ah] [rbp-96h]
  char v148; // [rsp+6Bh] [rbp-95h]
  char v149; // [rsp+6Ch] [rbp-94h]
  char v150; // [rsp+6Dh] [rbp-93h]
  char v151; // [rsp+6Eh] [rbp-92h] BYREF
  bool v152; // [rsp+6Fh] [rbp-91h]
  char v153[4]; // [rsp+70h] [rbp-90h] BYREF
  bool v154[4]; // [rsp+74h] [rbp-8Ch] BYREF
  int v155; // [rsp+78h] [rbp-88h] BYREF
  char v156; // [rsp+7Ch] [rbp-84h]
  char v157; // [rsp+7Dh] [rbp-83h]
  int v158; // [rsp+80h] [rbp-80h]
  int v159; // [rsp+84h] [rbp-7Ch]
  unsigned int v160; // [rsp+88h] [rbp-78h]
  unsigned int v161; // [rsp+8Ch] [rbp-74h]
  unsigned int v162; // [rsp+90h] [rbp-70h]
  unsigned int v163; // [rsp+94h] [rbp-6Ch]
  unsigned int v164; // [rsp+98h] [rbp-68h]
  struct _MDEV **v165; // [rsp+A0h] [rbp-60h]
  unsigned int v166; // [rsp+A8h] [rbp-58h]
  struct _MDEV *v167; // [rsp+B0h] [rbp-50h]
  struct DISPLAYCONFIG_PATH_INFO_INTERNAL *v168; // [rsp+B8h] [rbp-48h]
  int v169; // [rsp+C0h] [rbp-40h]
  struct _DISPLAYCONFIG_CDS_REQUEST *v170; // [rsp+C8h] [rbp-38h]
  int v171; // [rsp+D0h] [rbp-30h]
  __int64 v172; // [rsp+D8h] [rbp-28h]
  _QWORD v173[6]; // [rsp+E0h] [rbp-20h] BYREF
  PVOID Buffer[2]; // [rsp+110h] [rbp+10h] BYREF
  struct D3DKMT_GETPATHSMODALITY *v175; // [rsp+120h] [rbp+20h] BYREF
  char v176; // [rsp+128h] [rbp+28h]
  void *v177; // [rsp+130h] [rbp+30h] BYREF
  void *v178; // [rsp+140h] [rbp+40h]
  __int64 v179; // [rsp+148h] [rbp+48h]
  __int64 v180; // [rsp+150h] [rbp+50h]
  void *v181; // [rsp+158h] [rbp+58h] BYREF
  __int64 v182; // [rsp+160h] [rbp+60h]
  unsigned int *v183; // [rsp+168h] [rbp+68h]
  int *v184; // [rsp+170h] [rbp+70h]
  _BYTE *v185; // [rsp+178h] [rbp+78h]
  _BYTE *v186; // [rsp+180h] [rbp+80h]
  __int64 v187; // [rsp+188h] [rbp+88h]
  char *v188; // [rsp+190h] [rbp+90h]
  int v189; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v190[12]; // [rsp+19Ch] [rbp+9Ch]
  __int128 v191; // [rsp+1A8h] [rbp+A8h]
  void *retaddr; // [rsp+208h] [rbp+108h]

  v17 = a4;
  v18 = a9;
  v19 = a10;
  v178 = a5;
  v170 = a8;
  v183 = a11;
  v184 = a12;
  v188 = a13;
  v186 = a15;
  v180 = a16;
  v161 = a1;
  v182 = a17;
  v160 = a4;
  v20 = a3;
  v168 = a2;
  v167 = a9;
  v165 = a10;
  v185 = a14;
  v171 = 2;
  v162 = 0;
  v21 = 0;
  v149 = 0;
  v22 = *(_QWORD *)(W32GetSessionState(a14, a2, a3, a4) + 88);
  v23 = -5;
  v153[0] = 0;
  v172 = v22;
  v146 = 0;
  v24 = *(_DWORD *)(v22 + 1148);
  v145 = 0;
  v152 = v24 != 0;
  v150 = 0;
  v144 = 0;
  v159 = -5;
  v155 = -5;
  v157 = 0;
  v163 = v24 != 0 ? 3 : 0;
  WdLogSingleEntry1(4, v20);
  WdLogGlobalForLineNumber = 15310;
  v187 = DrvDxgkLogCodePointPacket(120, 0, 0);
  UserSessionState = W32GetUserSessionState(v26, v25);
  DisplayScenarioJournalBegin(v20, v17, *(unsigned __int16 *)(UserSessionState + 68736));
  DisplayScenarioJournalSetSDCPathsAndModes(216 * v161, v161, v168);
  v181 = retaddr;
  AUTO_STATUS_CHANGE_NOTIFY<2,3>::NotifyStatusChange(&v181, 4);
  v28 = v172;
  *a10 = 0;
  if ( *(_DWORD *)(v28 + 1220) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 15357;
  }
  if ( (v20 & 0x1000) != 0 && a6 )
    WdDiagNotifyUser(40, 3, 0, 0);
  if ( (v17 & 2) == 0 || (v148 = 1, (v20 & 0x88F) != 0x88F) )
    v148 = 0;
  AUTO_TGO::AUTO_TGO((AUTO_TGO *)v173);
  v173[0] = &off_14024B988;
  v175 = 0;
  v176 = 0;
  v177 = 0;
  *(_OWORD *)Buffer = 0;
  if ( !(unsigned int)UserIsWddmConnectedSession() || !(unsigned int)DrvIsWddmDriverPresent() || (v17 & 1) != 0 )
  {
    if ( (v17 & 0x20) != 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 15425;
    }
    v113 = DrvChangeDisplayFallback(
             v178,
             BYTE1(v20) & 1,
             v17 & 1,
             a9,
             v165,
             (enum _DXGK_DIAG_SDC_STAGE *)&v144,
             &v145,
             &v155);
    v23 = v155;
    LODWORD(v34) = v113;
    if ( v113 >= 0 )
    {
      v114 = v144;
      if ( (v17 & 1) != 0 )
        v114 = 30;
      v144 = v114;
    }
    v146 = v145;
    goto LABEL_248;
  }
  if ( (v20 & 0x40000000) != 0 )
  {
    if ( DrvIsModeChangeHandledByDispBroker() || (v20 & 0x10000) != 0 )
    {
      LODWORD(v34) = -1073741811;
      v144 = 37;
      goto LABEL_254;
    }
    if ( *(_DWORD *)(v172 + 1148) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 15463;
    }
    LODWORD(v34) = GetPathsModality(v30, Buffer, 15);
    if ( (int)v34 < 0 )
    {
      v144 = 2;
      goto LABEL_248;
    }
    v35 = *((_DWORD *)Buffer[0] + 8) & 0xF;
    if ( v35 == 1 || v35 == 8 )
    {
      LODWORD(v34) = -1073741637;
      v144 = 25;
      goto LABEL_253;
    }
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v33);
    LOBYTE(v37) = 1;
    LOBYTE(v38) = v35 == 4;
    (*(void (__fastcall **)(__int64, __int64))(DxgkWin32kInterface + 528))(v37, v38);
    if ( v35 == 4 )
    {
      v40 = 0;
      v144 = 26;
      LODWORD(v34) = 0;
      v41 = 1;
      goto LABEL_268;
    }
    v20 = 132;
    v147 = 1;
    v42 = 1;
    v158 = 0;
    v43 = 128;
    v169 = 128;
    goto LABEL_24;
  }
  if ( (v20 & 0x80000000) != 0 )
  {
    if ( DrvIsModeChangeHandledByDispBroker() || (v20 & 0x10000) != 0 )
    {
      LODWORD(v34) = -1073741811;
      v144 = 38;
      goto LABEL_254;
    }
    v47 = DxDdGetDxgkWin32kInterface(v46);
    v40 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(v47 + 528))(0, 0) )
    {
      LODWORD(v34) = 0;
      v144 = 18;
      v41 = 1;
      goto LABEL_268;
    }
    v147 = 0;
    v20 = 2191;
    v158 = 0;
    v44 = -113;
    v42 = 0;
    v43 = 128;
    v169 = 128;
    goto LABEL_25;
  }
  if ( (v20 & 0xF) != 0xF )
  {
    v29 = v170;
LABEL_42:
    if ( (v20 & 0x200) != 0
      || (v17 & 0x20) != 0 && (*((_DWORD *)v29 + 3) & 1) != 0
      || (v20 & 0x1F) != 0 && (v20 & 0x40) == 0 )
    {
      v42 = 0;
      v147 = 0;
      v50 = DxDdGetDxgkWin32kInterface(v29);
      (*(void (__fastcall **)(_QWORD, _QWORD))(v50 + 528))(0, 0);
    }
    else
    {
      v49 = DxDdGetDxgkWin32kInterface(v29);
      v42 = (*(__int64 (**)(void))(v49 + 536))();
      v147 = v42;
    }
    goto LABEL_49;
  }
  if ( (v17 & 0x20) != 0 )
  {
    v29 = v170;
    if ( (*((_DWORD *)v170 + 3) & 1) != 0 )
      goto LABEL_42;
  }
  v48 = DxDdGetDxgkWin32kInterface(v29);
  v147 = (*(__int64 (**)(void))(v48 + 536))();
  v42 = v147;
  if ( v147 )
    v20 = v20 & 0xFFFFFFF0 | 4;
LABEL_49:
  v43 = v20 & 0x80;
  v158 = v20 & 0x10000;
  v169 = (unsigned __int8)v43;
  if ( (v20 & 0x10000) != 0 )
  {
    v51 = DxDdGetDxgkWin32kInterface(v39);
    LODWORD(v34) = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(v51 + 728))(
                     a7,
                     v43 != 0 ? 2031616 : 0x20000,
                     &v177);
    if ( (int)v34 < 0 )
    {
      v144 = 42;
      goto LABEL_248;
    }
  }
LABEL_24:
  v44 = v20;
LABEL_25:
  v45 = DxDdGetDxgkWin32kInterface(v39);
  LODWORD(v34) = (*(__int64 (**)(void))(v45 + 272))();
  if ( (int)v34 < 0 )
  {
    v144 = 12;
    v21 = 6;
    goto LABEL_248;
  }
  v156 = 0;
  v176 = 1;
  v164 = 0;
  if ( v43 )
  {
    v52 = 1;
    if ( !v42 && (v20 & 0xF) != 0 && (v160 & 0x20) == 0 )
      v52 = 3;
    v53 = DxDdGetDxgkWin32kInterface(1);
    v54 = (*(__int64 (__fastcall **)(__int64))(v53 + 296))(v52);
    LODWORD(v34) = v54;
    if ( v54 < 0 )
    {
      WdLogSingleEntry1(4, v54);
      WdLogGlobalForLineNumber = 15669;
      DrvDxgkLogCodePointPacket(4, (unsigned int)v34, 0);
      LODWORD(v34) = 0;
    }
  }
  v55 = (v20 & 0x240) == 512;
  v166 = v44 & 0xF;
  v143 = v55;
  while ( 1 )
  {
    v56 = v162;
    v179 = v162;
    WdLogSingleEntry2(4, v162, (int)v34);
    WdLogGlobalForLineNumber = 15692;
    v57 = 0;
    v150 = 0;
    v151 = 0;
    v146 = 0;
    v145 = 0;
    v153[0] = 0;
    FreePathsModality(Buffer[0]);
    FreePathsModality(Buffer[1]);
    Buffer[1] = 0;
    Buffer[0] = 0;
    if ( v152 )
      break;
    if ( !v166 )
    {
      if ( (v20 & 0x10) != 0 )
      {
        if ( !DrvIsModeChangeHandledByDispBroker() && !v158 )
        {
          LODWORD(v34) = AllocatePathModalityForDisplayConfig(v161, v168, (struct D3DKMT_GETPATHSMODALITY **)Buffer);
          if ( (int)v34 < 0 )
          {
            v144 = 3;
            goto LABEL_227;
          }
          LODWORD(v34) = ConvertDisplayConfigToPathModality(v161, v168, (struct D3DKMT_GETPATHSMODALITY *)Buffer[0], 0);
          if ( (int)v34 < 0 )
          {
            v144 = 4;
            goto LABEL_227;
          }
          v81 = DxDdGetDxgkWin32kInterface(v80);
          LODWORD(v34) = (*(__int64 (__fastcall **)(_QWORD, PVOID, _QWORD))(v81 + 144))(
                           v20 & 0x2000 | 0x2F,
                           Buffer[0],
                           0);
          if ( (int)v34 < 0 )
          {
            v144 = 5;
            goto LABEL_227;
          }
          if ( v147 || (v20 & 0x40) != 0 )
          {
            v55 = 0;
            v143 = 0;
          }
          else
          {
            v55 = 1;
            v143 = 1;
          }
          goto LABEL_118;
        }
        v144 = 40;
LABEL_226:
        LODWORD(v34) = -1073741811;
        goto LABEL_227;
      }
      if ( (v20 & 0x20) == 0 )
      {
        WdLogSingleEntry1(1, v20);
        WdLogGlobalForLineNumber = 16089;
        v144 = 9;
        goto LABEL_226;
      }
      v154[0] = 0;
      if ( (v160 & 8) != 0 )
      {
        v82 = SetDisplayConfigHandleOnlyProvidedPath(
                v168,
                (struct D3DKMT_GETPATHSMODALITY **)Buffer,
                v154,
                (enum _DXGK_DIAG_SDC_STAGE *)&v144);
LABEL_143:
        LODWORD(v34) = v82;
        if ( v82 < 0 )
          goto LABEL_227;
      }
      else
      {
        if ( v158 )
        {
          v82 = SetDisplayConfigHandleBrokerProvidedPaths(
                  v177,
                  0,
                  v161,
                  v168,
                  (struct D3DKMT_GETPATHSMODALITY **)Buffer,
                  v154,
                  (enum _DXGK_DIAG_SDC_STAGE *)&v144);
          goto LABEL_143;
        }
        v84 = v161;
        LODWORD(v34) = AllocatePathModalityForDisplayConfig(v161, v168, (struct D3DKMT_GETPATHSMODALITY **)Buffer);
        if ( (int)v34 < 0 )
        {
          v144 = 6;
          goto LABEL_227;
        }
        LODWORD(v34) = ConvertDisplayConfigToPathModality(v84, v168, (struct D3DKMT_GETPATHSMODALITY *)Buffer[0], v154);
        if ( (int)v34 < 0 )
        {
          v144 = 7;
          goto LABEL_227;
        }
      }
      if ( v154[0] )
      {
        if ( DrvIsModeChangeHandledByDispBroker() )
        {
          v144 = 41;
          goto LABEL_226;
        }
        LODWORD(v34) = SetDisplayConfigHandlePreferredScaling(
                         (struct D3DKMT_GETPATHSMODALITY *)Buffer[0],
                         (enum _DXGK_DIAG_SDC_STAGE *)&v144);
        if ( (int)v34 < 0 )
          goto LABEL_227;
      }
      v85 = DxDdGetDxgkWin32kInterface(v83);
      LODWORD(v34) = (*(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(v85 + 144))(256, Buffer[0], 0);
      if ( (int)v34 < 0 )
      {
        v144 = 8;
        goto LABEL_227;
      }
      v57 = 1;
      goto LABEL_118;
    }
    if ( DrvIsModeChangeHandledByDispBroker() && (v20 & 0xA8F) != 0x88F || v158 )
    {
      v144 = 39;
      goto LABEL_226;
    }
    v64 = v160;
    v65 = v160 & 0x20;
    v66 = (v160 & 0x20) != 0 && *((_QWORD *)v170 + 2);
    if ( v147 || (v143 = 1, (v20 & 0x40) != 0) )
      v143 = 0;
    CurrentMode = DispBrokerGetCurrentMode();
    v68 = 0;
    if ( CurrentMode )
    {
      v143 = 0;
      if ( v66 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 15835;
      }
      if ( (unsigned int)UserIsConsoleConnection(v68) && (v64 & 0xC00) == 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 15836;
      }
      DrvDxgkLogCodePointPacket(127, 0, 0);
      v69 = v64;
      v70 = v148;
      v71 = (v69 & 0x800) != 0 ? 0x10000000 : 64;
      if ( !v148 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 15854;
      }
      v156 = v70;
      DisplayScenarioJournalCCDRetrieval(16);
    }
    else
    {
      v73 = v65 != 0 ? 0x9000 : 0;
      if ( !v66 || (*((_DWORD *)v170 + 3) & 1) != 0 )
      {
        v72 = v166;
        v74 = v166;
      }
      else
      {
        v72 = v166;
        v74 = 0x2000000;
      }
      v71 = v74 | v73;
      if ( (v71 & 0x2000000) != 0 && (_DWORD)v72 != 15 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 15880;
      }
    }
    LODWORD(v34) = GetPathsModality(v72, Buffer, v71);
    if ( (int)v34 < 0 )
      goto LABEL_106;
    if ( !*((_WORD *)Buffer[0] + 10) )
    {
      LODWORD(v34) = -1071774922;
LABEL_106:
      v144 = 2;
      v21 = 7;
LABEL_107:
      v23 = v159;
LABEL_72:
      v55 = v143;
      goto LABEL_227;
    }
    DrvSetDisplayConfigApplyDeviceHack((struct D3DKMT_GETPATHSMODALITY *)Buffer[0]);
    if ( v66 )
    {
      v75 = v170;
      v76 = *((_DWORD *)v170 + 3);
      if ( (v76 & 1) == 0 || (v143 = 1, (v76 & 2) == 0) )
        v143 = 0;
      LODWORD(v34) = DrvValidateAndApplyDevMode(v170, (struct D3DKMT_GETPATHSMODALITY **)Buffer);
      if ( (int)v34 < 0 )
      {
        v23 = *((_DWORD *)v75 + 8);
        v79 = 2;
        v21 = *((_DWORD *)v75 + 9);
        v159 = v23;
        v155 = v23;
        if ( (_DWORD)v34 == -1073741266 )
          v79 = 23;
        v144 = v79;
        goto LABEL_72;
      }
      v57 = *((_DWORD *)v75 + 3) & 1;
    }
    v23 = v159;
    v21 = 10;
LABEL_117:
    v55 = v143;
LABEL_118:
    if ( (v20 & 0x800) != 0 )
    {
      *(_WORD *)v154 = 0;
      PathPersistentMonitorsIfNeeded = CreatePathPersistentMonitorsIfNeeded(
                                         v63,
                                         (const struct D3DKMT_GETPATHSMODALITY *)Buffer[0],
                                         (unsigned __int16 *)v154);
      LODWORD(v34) = PathPersistentMonitorsIfNeeded;
      if ( PathPersistentMonitorsIfNeeded < 0 )
      {
        WdLogSingleEntry1(2, PathPersistentMonitorsIfNeeded);
        WdLogGlobalForLineNumber = 16106;
        v144 = 10;
        goto LABEL_227;
      }
      v86 = DxDdGetDxgkWin32kInterface(v78);
      v87 = (*(__int64 (__fastcall **)(__int64, PVOID))(v86 + 176))(0x80000000LL, Buffer[0]);
      LODWORD(v34) = v87;
      if ( v87 == -1073741266 )
      {
        WdLogSingleEntry2(4, v56, -1073741266);
        WdLogGlobalForLineNumber = 16118;
        v144 = 23;
        goto LABEL_227;
      }
      if ( v87 < 0 )
      {
        WdLogSingleEntry1(2, v87);
        WdLogGlobalForLineNumber = 16126;
        v144 = 22;
        goto LABEL_227;
      }
      if ( *(_WORD *)v154 )
      {
        WdLogSingleEntry2(3, v56, v87);
        WdLogGlobalForLineNumber = 16141;
        LODWORD(v34) = -1073741266;
        goto LABEL_227;
      }
    }
    if ( *((_WORD *)Buffer[0] + 10) )
    {
      CcdRawmodeFlag = GetCcdRawmodeFlag();
      v90 = v160;
      v91 = CcdRawmodeFlag | 0x8000;
      if ( (v160 & 0x20) != 0 )
      {
        v89 = v170;
        if ( !*((_QWORD *)v170 + 2)
          || (v89 = (struct _DISPLAYCONFIG_CDS_REQUEST *)*((unsigned int *)v170 + 3), ((unsigned __int8)v89 & 4) != 0) )
        {
          v91 |= 0x20000u;
        }
      }
      v92 = v91 | 0x1000000;
      if ( !v158 )
        v92 = v91;
      v93 = DxDdGetDxgkWin32kInterface(v89);
      v94 = v92;
      LODWORD(v94) = v92 | 0x20000000;
      v95 = *(__int64 (__fastcall **)(__int64, PVOID))(v93 + 152);
      if ( (v90 & 0x800) == 0 )
        v94 = v92;
      v96 = v95(v94, Buffer[0]);
      LODWORD(v34) = v96;
      if ( v96 < 0 )
      {
        WdLogSingleEntry2(4, Buffer[0], v96);
        WdLogGlobalForLineNumber = 16186;
        v144 = 11;
LABEL_172:
        v21 = 7;
        goto LABEL_72;
      }
    }
    v144 = 18;
    v21 = 10;
    if ( v169 )
    {
      *(_DWORD *)v154 = GetPathsModality(v63, &Buffer[1], 1048640);
      LODWORD(v34) = *(_DWORD *)v154;
      if ( *(int *)v154 < 0 )
      {
        v144 = 13;
        goto LABEL_172;
      }
      v98 = (16 * (v20 & 0x1000)) | 0x4000;
      if ( (v20 & 0x1100) == 0 )
        v98 = 16 * (v20 & 0x1000);
      if ( v98 )
      {
        v99 = DxDdGetDxgkWin32kInterface(v97);
        LODWORD(v34) = (*(__int64 (__fastcall **)(_QWORD, PVOID, _QWORD))(v99 + 144))(v98, Buffer[0], 0);
        *(_DWORD *)v154 = v34;
        if ( (int)v34 < 0 )
        {
          v144 = 14;
          goto LABEL_107;
        }
      }
      if ( (v160 & 0x10) != 0 )
        v98 |= 0x400000u;
      v100 = 0;
      v101 = v98 | 0x1000000;
      if ( !v158 )
        v101 = v98;
      v102 = *(_QWORD *)(v172 + 1184);
      while ( v102 )
      {
        v103 = (*(_DWORD *)(v102 + 160) & 0x800000) == 0;
        v104 = v100 + 1;
        v102 = *(_QWORD *)(v102 + 128);
        if ( v103 )
          v104 = v100;
        v100 = v104;
      }
      DisplayScenarioJournalSetExpectedPathModality(
        296 * (unsigned int)*((unsigned __int16 *)Buffer[0] + 10),
        *((unsigned __int16 *)Buffer[0] + 10),
        (char *)Buffer[0] + 56,
        v100);
      LOBYTE(v105) = (v20 & 0x1100) != 0;
      v106 = v165;
      v107 = ApplyPathsModality(
               Buffer[0],
               v101,
               v105,
               (_DWORD)v178,
               v167,
               (unsigned __int8)&v151,
               (__int64)v153,
               v165,
               (__int64)v154,
               (enum _DXGK_DIAG_SDC_STAGE *)&v144,
               v180);
      v63 = 0;
      v171 = v107;
      v159 = v107;
      v108 = v107;
      v155 = v107;
      v23 = v107;
      if ( v107 < 0 )
      {
        v21 = 5;
        LODWORD(v34) = *(_DWORD *)v154;
        v150 = v151;
        goto LABEL_72;
      }
      if ( v107 == 1 )
      {
        WdLogSingleEntry0(1);
        v63 = 0;
        WdLogGlobalForLineNumber = 16292;
      }
      LODWORD(v34) = *(_DWORD *)v154;
      if ( *(int *)v154 < 0 )
      {
        WdLogSingleEntry0(1);
        v63 = 0;
        WdLogGlobalForLineNumber = 16293;
      }
      v150 = v151;
      if ( v151 )
      {
        WdLogSingleEntry0(1);
        v63 = 0;
        WdLogGlobalForLineNumber = 16294;
      }
      if ( v108 == 2 )
      {
        if ( (v20 & 0x1100) != 0 || *v106 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 16298;
        }
        v146 = 1;
        v145 = 1;
      }
      else
      {
        if ( !*v106 )
        {
          WdLogSingleEntry0(1);
          v63 = 0;
          WdLogGlobalForLineNumber = 16309;
        }
        v167 = 0;
      }
      v56 = v179;
      goto LABEL_209;
    }
    if ( (v20 & 0x40) == 0 )
    {
      WdLogSingleEntry1(1, v20);
      v55 = v143;
      WdLogGlobalForLineNumber = 16328;
      v144 = 21;
      goto LABEL_226;
    }
    v23 = 0;
    v159 = 0;
    v155 = 0;
LABEL_209:
    v55 = v143;
    v21 = 10;
    if ( v143 )
    {
      v109 = DxDdGetDxgkWin32kInterface(v63);
      v110 = (*(__int64 (__fastcall **)(_QWORD, PVOID))(v109 + 176))(v57, Buffer[0]);
      LODWORD(v34) = v110;
      if ( a6 )
      {
        if ( v110 == -1073741266 )
        {
          if ( (v20 & 0x10) != 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 16354;
          }
          WdLogSingleEntry2(4, v56, -1073741266);
          WdLogGlobalForLineNumber = 16358;
          if ( !v146 )
          {
            if ( v167 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 16366;
            }
            v149 = 1;
            v167 = *v165;
            *v165 = 0;
          }
          v144 = 24;
          v21 = 9;
        }
        else
        {
          v21 = 10;
          if ( v110 < 0 )
          {
            v144 = 29;
            v21 = 9;
            LODWORD(v34) = 0;
          }
        }
      }
      else
      {
        if ( v110 < 0 )
        {
          WdLogSingleEntry1(2, v110);
          WdLogGlobalForLineNumber = 16347;
          LODWORD(v34) = 0;
        }
        v21 = 10;
      }
    }
LABEL_227:
    v111 = ++v162;
    if ( v156 )
    {
      if ( !v148 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 16398;
      }
      DisplayScenarioJournalRetry((unsigned int)v34);
      goto LABEL_248;
    }
    if ( (_DWORD)v34 == -1073741266 )
    {
      if ( !v152 && v111 < 4 )
      {
        v112 = 3221226030LL;
        goto LABEL_235;
      }
    }
    else if ( (int)v34 >= 0 )
    {
      goto LABEL_257;
    }
    if ( !v148 )
      goto LABEL_248;
    v55 = 0;
    v152 = 1;
    v143 = 0;
    v112 = (unsigned int)v34;
LABEL_235:
    DisplayScenarioJournalRetry(v112);
  }
  if ( v166 != 15 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 15714;
  }
  if ( v55 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 15715;
  }
  if ( v163 < 6 )
  {
    v58 = 3LL * v163;
    DrvDxgkLogCodePointPacket(
      75,
      *((unsigned int *)qword_1402663A0 + 3 * v163 + 1),
      *((unsigned int *)&qword_1402663A0[1] + 3 * v163));
    v60 = (const struct RETRY_MODE *)((char *)qword_1402663A0 + 4 * v58);
    if ( *(_BYTE *)v60 )
    {
      PathsModality = GetPathsModality(v59, Buffer, 15);
      ++v163;
      LODWORD(v34) = PathsModality;
      v164 = 0;
      if ( PathsModality < 0 )
        goto LABEL_71;
    }
    else
    {
      LODWORD(v34) = DrvCreatePathModalityFromAllPaths(&v175, v164, (struct D3DKMT_GETPATHSMODALITY **)Buffer);
      if ( (int)v34 < 0 )
      {
        ++v163;
        v164 = 0;
LABEL_71:
        v144 = 2;
        goto LABEL_72;
      }
      ++v164;
      if ( *((_WORD *)Buffer[0] + 10) != 1 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 15767;
      }
    }
    v62 = DrvFunctionalizeBaseVidMode(v60, (struct D3DKMT_GETPATHSMODALITY *)Buffer[0]);
    LODWORD(v34) = v62;
    if ( v62 < 0 )
    {
      WdLogSingleEntry1(2, v62);
      WdLogGlobalForLineNumber = 15786;
      goto LABEL_71;
    }
    goto LABEL_117;
  }
  if ( (int)v34 < 0 )
    goto LABEL_249;
  WdLogSingleEntry0(1);
  WdLogGlobalForLineNumber = 15722;
LABEL_248:
  if ( (int)v34 >= 0 )
  {
LABEL_257:
    v115 = v149;
LABEL_258:
    if ( v115 && !*v165 )
    {
      v116 = v167;
      if ( !v167 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 16447;
      }
      *v165 = v116;
      if ( v23 == 2 )
        v23 = 0;
      v155 = v23;
    }
LABEL_265:
    v41 = v146;
    v40 = 0;
    goto LABEL_266;
  }
LABEL_249:
  v115 = v149;
  if ( v149 )
  {
    v144 = 29;
    LODWORD(v34) = 0;
    v21 = 9;
    v155 = 0;
    v23 = 0;
  }
  if ( (int)v34 >= 0 )
    goto LABEL_258;
  v18 = v167;
LABEL_253:
  v19 = v165;
LABEL_254:
  if ( !v148 )
    goto LABEL_265;
  if ( a6 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 16465;
  }
  v120 = DrvChangeDisplayFallback(v178, BYTE1(v20) & 1, 1u, v18, v19, (enum _DXGK_DIAG_SDC_STAGE *)&v144, &v145, &v155);
  v40 = 0;
  v34 = v120;
  if ( v120 >= 0 )
  {
    v21 = 10;
    v144 = 31;
    goto LABEL_279;
  }
  WdLogSingleEntry0(1);
  WdLogGlobalForLineNumber = 16484;
  if ( *(_BYTE *)(v172 + 1352) )
  {
LABEL_279:
    v41 = v145;
    v23 = v155;
  }
  else
  {
    *(_BYTE *)(v172 + 1352) = 1;
    v122 = DxDdGetDxgkWin32kInterface(v121);
    v23 = v155;
    LOBYTE(v142) = 0;
    (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD, int))(v122 + 720))(
      400,
      22,
      v34,
      v155,
      v144,
      v142);
    v41 = v145;
  }
LABEL_266:
  if ( (_DWORD)v34 == -1073741811 )
    goto LABEL_300;
  v17 = v160;
LABEL_268:
  FreePathsModality(Buffer[1]);
  Buffer[1] = 0;
  if ( (int)SetDisplayConfigGetActualPathsModality((struct D3DKMT_GETPATHSMODALITY **)&Buffer[1]) < 0 )
    goto LABEL_296;
  DisplayScenarioJournalSetActualPathModality(
    296 * (unsigned int)*((unsigned __int16 *)Buffer[1] + 10),
    *((unsigned __int16 *)Buffer[1] + 10),
    (char *)Buffer[1] + 56);
  v117 = (char *)Buffer[1];
  if ( !*((_WORD *)Buffer[1] + 10) )
    goto LABEL_283;
  while ( 2 )
  {
    v118 = 296LL * v40;
    v119 = *(_QWORD *)&v117[v118 + 56];
    if ( v119 >= 0 || (v119 & 0x1000000000LL) != 0 )
    {
LABEL_275:
      if ( ++v40 >= *((unsigned __int16 *)v117 + 10) )
        goto LABEL_283;
      continue;
    }
    break;
  }
  *(_QWORD *)&v190[4] = 0;
  v191 = 0;
  v189 = 9;
  *(_DWORD *)v190 = 32;
  *(_QWORD *)&v190[4] = *(_QWORD *)&v117[v118 + 72];
  LODWORD(v191) = *(_DWORD *)&v117[v118 + 84];
  if ( (int)DrvDisplayConfigGetDeviceInfoInternal((struct DISPLAYCONFIG_DEVICE_INFO_HEADER *)&v189, 0) < 0
    || (BYTE4(v191) & 1) == 0 )
  {
    v117 = (char *)Buffer[1];
    goto LABEL_275;
  }
  v157 = 1;
LABEL_283:
  if ( !(unsigned int)Feature_ForceConnectionDetectionOnDcToAc__private_IsEnabledDeviceUsageNoInline()
    && (v20 & 0x80u) != 0
    && (unsigned int)UserIsConsoleConnection(v123) )
  {
    v124 = Buffer[1];
    v125 = 0;
    v126 = 0;
    if ( *((_WORD *)Buffer[1] + 10) )
    {
      while ( 1 )
      {
        v127 = 296LL * v126;
        v128 = *(_QWORD *)((char *)Buffer[1] + v127 + 56);
        if ( v128 < 0 && (v128 & 0x1800000000000000LL) == 0 )
        {
          v129 = *(_DWORD *)((char *)Buffer[1] + v127 + 144);
          if ( v129 != 0x80000000 && v129 != 11 && v129 != 13 )
            break;
        }
        if ( ++v126 >= *((unsigned __int16 *)Buffer[1] + 10) )
          goto LABEL_295;
      }
      v125 = 1;
    }
LABEL_295:
    LOBYTE(v124) = v125;
    v130 = v17 >> 11;
    LOBYTE(v130) = (v17 & 0x800) != 0;
    UserNotifyExternalMonitorConnectedStatus(v130, v124);
  }
LABEL_296:
  if ( *v165 )
  {
    v131 = *((_QWORD *)*v165 + 5);
    if ( v131 )
    {
      v132 = *(_QWORD *)(v131 + 2568);
      if ( ((v132 + 4) & 0xFFFFFFFFFFFFFFFBuLL) != 0 )
        DisplayScenarioJounralSetTSDDDState((*(_DWORD *)(v132 + 160) & 0x2000000) != 0);
    }
  }
LABEL_300:
  if ( v183 )
    *v183 = v162;
  if ( v184 )
    *v184 = v144;
  if ( v188 )
  {
    if ( v149 || (v133 = 1, !v41) )
      v133 = 0;
    *v188 = v133;
  }
  v134 = v150;
  if ( v185 )
    *v185 = v150;
  if ( v186 )
    *v186 = v153[0];
  v135 = v160;
  if ( (v160 & 0x20) != 0 )
  {
    v136 = v170;
    *((_DWORD *)v170 + 8) = v23;
    *((_DWORD *)v136 + 9) = v21;
    if ( (int)v34 >= 0 != v23 >= 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 16618;
    }
    *(_QWORD *)v190 = 20;
    v189 = 0;
    *(_DWORD *)&v190[8] = v23;
    LODWORD(v191) = v21;
    DisplayScenarioJournalSetSpecializedData(&v189);
  }
  v137 = v182;
  v103 = (v135 & 0x40) == 0;
  v138 = v162;
  if ( v103 )
    LogDiagSDC(v161, (_DWORD)v168, v20, v34, v162, v144, v187, v41, v182);
  v139 = *(_QWORD *)(v172 + 1856);
  if ( v139 )
    DisplayScenarioJournalSetUniqueness(*(unsigned int *)(v139 + 1573024), *(unsigned int *)(v139 + 1573008));
  LOBYTE(v32) = v134;
  LOBYTE(v31) = v41;
  LOBYTE(v141) = v157;
  DisplayScenarioJournalSetResult((unsigned int)v144, v138, v31, v32, v141, v171, v137);
  DisplayScenarioJournalFinalize(v180, (unsigned int)v34);
  WdLogSingleEntry1(4, (int)v34);
  WdLogGlobalForLineNumber = 16649;
  DrvSetDisplayConfig_::_2_::_AUTO::__AUTO((AUTO_TGO *)v173);
  AUTO_STATUS_CHANGE_NOTIFY<2,3>::NotifyStatusChange(&v181, 5);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x1401f4510  push    rbp
0x1401f4512  push    rbx
0x1401f4513  push    rsi
0x1401f4514  push    rdi
0x1401f4515  push    r12
0x1401f4517  push    r13
0x1401f4519  push    r14
0x1401f451b  push    r15
0x1401f451d  lea     rbp, [rsp-0C8h]
0x1401f4525  sub     rsp, 1C8h
0x1401f452c  mov     rax, cs:__security_cookie
0x1401f4533  xor     rax, rsp
0x1401f4536  mov     [rbp+100h+var_48], rax
0x1401f453d  mov     rax, [rbp+100h+arg_20]
0x1401f4544  mov     r12d, r9d
0x1401f4547  mov     r14, [rbp+100h+arg_40]
0x1401f454e  mov     rbx, [rbp+100h+arg_48]
0x1401f4555  mov     rdi, [rbp+100h+arg_30]
0x1401f455c  mov     [rbp+100h+var_C0], rax
0x1401f4560  mov     rax, [rbp+100h+arg_38]
0x1401f4567  mov     [rbp+100h+var_138], rax
0x1401f456b  mov     rax, [rbp+100h+arg_50]
0x1401f4572  mov     [rbp+100h+var_98], rax
0x1401f4576  mov     rax, [rbp+100h+arg_58]
0x1401f457d  mov     [rbp+100h+var_90], rax
0x1401f4581  mov     rax, [rbp+100h+arg_60]
0x1401f4588  mov     [rbp+100h+var_70], rax
0x1401f458f  mov     rax, [rbp+100h+arg_70]
0x1401f4596  mov     [rbp+100h+var_80], rax
0x1401f459d  mov     rax, [rbp+100h+arg_78]
0x1401f45a4  mov     [rbp+100h+var_B0], rax
0x1401f45a8  mov     rax, [rbp+100h+arg_80]
0x1401f45af  mov     [rbp+100h+var_174], ecx
0x1401f45b2  mov     rcx, [rbp+100h+arg_68]
0x1401f45b9  mov     [rbp+100h+var_A0], rax
0x1401f45bd  mov     [rbp+100h+var_178], r9d
0x1401f45c1  mov     r15d, r8d
0x1401f45c4  mov     [rbp+100h+var_148], rdx
0x1401f45c8  mov     [rbp+100h+var_150], r14
0x1401f45cc  mov     [rbp+100h+var_160], rbx
0x1401f45d0  mov     [rbp+100h+var_88], rcx
0x1401f45d4  call    cs:__imp_W32GetSessionState
0x1401f45db  nop     dword ptr [rax+rax+00h]
0x1401f45e0  xor     edx, edx
0x1401f45e2  mov     [rbp+100h+var_130], 2
0x1401f45e9  mov     [rbp+100h+var_170], edx
0x1401f45ec  mov     r13d, edx
0x1401f45ef  mov     [rsp+200h+var_194], dl
0x1401f45f3  mov     rcx, [rax+58h]
0x1401f45f7  lea     esi, [rdx-5]
0x1401f45fa  mov     [rsp+200h+var_190], dl
0x1401f45fe  mov     [rbp+100h+var_128], rcx
0x1401f4602  mov     [rsp+200h+var_197], dl
0x1401f4606  mov     eax, [rcx+47Ch]
0x1401f460c  test    eax, eax
0x1401f460e  mov     [rsp+200h+var_198], dl
0x1401f4612  setnz   [rsp+200h+var_191]
0x1401f4617  mov     [rsp+200h+var_193], dl
0x1401f461b  neg     eax
0x1401f461d  mov     [rsp+200h+var_19C], edx
0x1401f4621  mov     [rbp+100h+var_17C], esi
0x1401f4624  sbb     eax, eax
0x1401f4626  mov     [rsp+200h+var_188], esi
0x1401f462a  and     eax, 3
0x1401f462d  mov     [rsp+200h+var_183], dl
0x1401f4631  mov     [rbp+100h+var_16C], eax
0x1401f4634  mov     edx, r15d
0x1401f4637  lea     ecx, [rsi+9]
0x1401f463a  call    cs:__imp_WdLogSingleEntry1
0x1401f4641  nop     dword ptr [rax+rax+00h]
0x1401f4646  xor     r9d, r9d
0x1401f4649  mov     cs:WdLogGlobalForLineNumber, 3BCEh
0x1401f4653  xor     r8d, r8d
0x1401f4656  lea     ecx, [rsi+7Dh]
0x1401f4659  xor     edx, edx
0x1401f465b  call    DrvDxgkLogCodePointPacket
0x1401f4660  mov     [rbp+100h+var_78], rax
0x1401f4667  call    cs:__imp_W32GetUserSessionState
0x1401f466e  nop     dword ptr [rax+rax+00h]
0x1401f4673  mov     edx, r12d
0x1401f4676  mov     ecx, r15d
0x1401f4679  movzx   r8d, word ptr [rax+10C80h]
0x1401f4681  call    cs:__imp_DisplayScenarioJournalBegin
0x1401f4688  nop     dword ptr [rax+rax+00h]
0x1401f468d  imul    ecx, [rbp+100h+var_174], 0D8h
0x1401f4694  mov     r8, [rbp+100h+var_148]
0x1401f4698  mov     edx, [rbp+100h+var_174]
0x1401f469b  call    cs:__imp_DisplayScenarioJournalSetSDCPathsAndModes
0x1401f46a2  nop     dword ptr [rax+rax+00h]
0x1401f46a7  mov     rcx, [rbp+108h]
0x1401f46ae  lea     edx, [rsi+9]
0x1401f46b1  mov     [rbp+100h+var_A8], rcx
0x1401f46b5  lea     rcx, [rbp+100h+var_A8]
0x1401f46b9  call    ?NotifyStatusChange@?$AUTO_STATUS_CHANGE_NOTIFY@$01$02@@AEAAXW4D3DKMT_STATE_NOTIFICATION_TYPE@@@Z; AUTO_STATUS_CHANGE_NOTIFY<2,3>::NotifyStatusChange(D3DKMT_STATE_NOTIFICATION_TYPE)
0x1401f46be  mov     rax, [rbp+100h+var_128]
0x1401f46c2  xor     ecx, ecx
0x1401f46c4  mov     [rbx], rcx
0x1401f46c7  cmp     [rax+4C4h], ecx
0x1401f46cd  jz      short loc_1401F46EA
0x1401f46cf  lea     ecx, [rsi+6]
0x1401f46d2  call    cs:__imp_WdLogSingleEntry0
0x1401f46d9  nop     dword ptr [rax+rax+00h]
0x1401f46de  xor     ecx, ecx
0x1401f46e0  mov     cs:WdLogGlobalForLineNumber, 3BFDh
0x1401f46ea  bt      r15d, 0Ch
0x1401f46ef  jnb     short loc_1401F4712
0x1401f46f1  cmp     [rbp+100h+arg_28], cl
0x1401f46f7  jz      short loc_1401F4712
0x1401f46f9  xor     r8d, r8d
0x1401f46fc  xor     r9d, r9d
0x1401f46ff  lea     edx, [r8+3]
0x1401f4703  lea     ecx, [rdx+25h]
0x1401f4706  call    cs:__imp_WdDiagNotifyUser
0x1401f470d  nop     dword ptr [rax+rax+00h]
0x1401f4712  mov     ecx, 88Fh
0x1401f4717  test    r12b, 2
0x1401f471b  jz      short loc_1401F472B
0x1401f471d  mov     eax, r15d
0x1401f4720  mov     [rsp+200h+var_195], 1
0x1401f4725  and     eax, ecx
0x1401f4727  cmp     eax, ecx
0x1401f4729  jz      short loc_1401F4730
0x1401f472b  mov     [rsp+200h+var_195], r13b
0x1401f4730  lea     rcx, [rbp+100h+var_120]; this
0x1401f4734  call    ??0AUTO_TGO@@IEAA@XZ; AUTO_TGO::AUTO_TGO(void)
0x1401f4739  lea     rax, off_14024B988
0x1401f4740  xorps   xmm0, xmm0
0x1401f4743  mov     [rbp+100h+var_120], rax
0x1401f4747  xor     eax, eax
0x1401f4749  mov     [rbp+100h+var_E0], rax
0x1401f474d  mov     [rbp+100h+var_D8], al
0x1401f4750  mov     [rbp+100h+var_D0], rax
0x1401f4754  movdqa  xmmword ptr [rbp+100h+Buffer], xmm0
0x1401f4759  call    UserIsWddmConnectedSession
0x1401f475e  test    eax, eax
0x1401f4760  jz      loc_1401F5749
0x1401f4766  call    DrvIsWddmDriverPresent
0x1401f476b  xor     edx, edx
0x1401f476d  lea     r8d, [rdx+1]
0x1401f4771  test    eax, eax
0x1401f4773  jz      loc_1401F574F
0x1401f4779  test    r8b, r12b
0x1401f477c  jnz     loc_1401F574F
0x1401f4782  bt      r15d, 1Eh
0x1401f4787  jnb     loc_1401F48C3
0x1401f478d  call    ?DrvIsModeChangeHandledByDispBroker@@YA_NXZ; DrvIsModeChangeHandledByDispBroker(void)
0x1401f4792  test    al, al
0x1401f4794  jnz     loc_1401F48B1
0x1401f479a  bt      r15d, 10h
0x1401f479f  jb      loc_1401F48B1
0x1401f47a5  mov     rax, [rbp+100h+var_128]
0x1401f47a9  xor     ebx, ebx
0x1401f47ab  cmp     [rax+47Ch], ebx
0x1401f47b1  jz      short loc_1401F47CC
0x1401f47b3  lea     ecx, [rbx+1]
0x1401f47b6  call    cs:__imp_WdLogSingleEntry0
0x1401f47bd  nop     dword ptr [rax+rax+00h]
0x1401f47c2  mov     cs:WdLogGlobalForLineNumber, 3C67h
0x1401f47cc  xor     r9d, r9d
0x1401f47cf  lea     rdx, [rbp+100h+Buffer]
0x1401f47d3  lea     r8d, [r9+0Fh]
0x1401f47d7  call    GetPathsModality
0x1401f47dc  mov     edi, eax
0x1401f47de  test    eax, eax
0x1401f47e0  jns     short loc_1401F47F2
0x1401f47e2  mov     [rsp+200h+var_19C], 2
0x1401f47ea  xor     r14d, r14d
0x1401f47ed  jmp     loc_1401F57DC
0x1401f47f2  mov     rax, [rbp+100h+Buffer]
0x1401f47f6  mov     edi, 1
0x1401f47fb  mov     ebx, [rax+20h]
0x1401f47fe  and     ebx, 0Fh
0x1401f4801  cmp     ebx, edi
0x1401f4803  jz      loc_1401F489F
0x1401f4809  cmp     ebx, 8
0x1401f480c  jz      loc_1401F489F
0x1401f4812  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x1401f4819  nop     dword ptr [rax+rax+00h]
0x1401f481e  cmp     ebx, 4
0x1401f4821  mov     cl, dil
0x1401f4824  setz    dl
0x1401f4827  mov     rax, [rax+210h]
0x1401f482e  call    _guard_dispatch_icall
0x1401f4833  cmp     ebx, 4
0x1401f4836  jnz     short loc_1401F484C
0x1401f4838  xor     ebx, ebx
0x1401f483a  mov     [rsp+200h+var_19C], 1Ah
0x1401f4842  mov     edi, ebx
0x1401f4844  mov     r14b, 1
0x1401f4847  jmp     loc_1401F58B9
0x1401f484c  mov     r15d, 84h
0x1401f4852  mov     [rsp+200h+var_196], dil
0x1401f4857  mov     r12b, dil
0x1401f485a  mov     [rbp+100h+var_180], r13d
0x1401f485e  lea     eax, [r15-4]
0x1401f4862  mov     ebx, eax
0x1401f4864  mov     [rbp+100h+var_140], eax
0x1401f4867  mov     r14d, r15d
0x1401f486a  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x1401f4871  nop     dword ptr [rax+rax+00h]
0x1401f4876  mov     rax, [rax+110h]
0x1401f487d  call    _guard_dispatch_icall
0x1401f4882  mov     edi, eax
0x1401f4884  xor     eax, eax
0x1401f4886  test    edi, edi
0x1401f4888  jns     loc_1401F4A62
0x1401f488e  mov     [rsp+200h+var_19C], 0Ch
0x1401f4896  lea     r13d, [rax+6]
0x1401f489a  jmp     loc_1401F47EA
0x1401f489f  mov     edi, 0C00000BBh
0x1401f48a4  mov     [rsp+200h+var_19C], 19h
0x1401f48ac  jmp     loc_1401F5809
0x1401f48b1  mov     edi, 0C000000Dh
0x1401f48b6  mov     [rsp+200h+var_19C], 25h ; '%'
0x1401f48be  jmp     loc_1401F580D
0x1401f48c3  test    r15d, r15d
0x1401f48c6  jns     short loc_1401F4942
0x1401f48c8  call    ?DrvIsModeChangeHandledByDispBroker@@YA_NXZ; DrvIsModeChangeHandledByDispBroker(void)
0x1401f48cd  test    al, al
0x1401f48cf  jnz     short loc_1401F4930
0x1401f48d1  bt      r15d, 10h
0x1401f48d6  jb      short loc_1401F4930
0x1401f48d8  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x1401f48df  nop     dword ptr [rax+rax+00h]
0x1401f48e4  xor     edx, edx
0x1401f48e6  xor     ecx, ecx
0x1401f48e8  mov     rax, [rax+210h]
0x1401f48ef  call    _guard_dispatch_icall
0x1401f48f4  xor     ebx, ebx
0x1401f48f6  test    al, al
0x1401f48f8  jz      short loc_1401F491E
0x1401f48fa  mov     eax, 88Fh
0x1401f48ff  mov     [rsp+200h+var_196], bl
0x1401f4903  mov     r15d, eax
0x1401f4906  mov     [rbp+100h+var_180], ebx
0x1401f4909  mov     r14d, eax
0x1401f490c  mov     r12b, bl
0x1401f490f  mov     eax, 80h
0x1401f4914  mov     ebx, eax
0x1401f4916  mov     [rbp+100h+var_140], eax
0x1401f4919  jmp     loc_1401F486A
0x1401f491e  mov     edi, ebx
0x1401f4920  mov     [rsp+200h+var_19C], 12h
0x1401f4928  mov     r14b, 1
0x1401f492b  jmp     loc_1401F58B9
0x1401f4930  mov     edi, 0C000000Dh
0x1401f4935  mov     [rsp+200h+var_19C], 26h ; '&'
0x1401f493d  jmp     loc_1401F580D
0x1401f4942  mov     eax, r15d
0x1401f4945  and     eax, 0Fh
0x1401f4948  cmp     al, 0Fh
0x1401f494a  jnz     short loc_1401F498B
0x1401f494c  test    r12b, 20h
0x1401f4950  jz      short loc_1401F495E
0x1401f4952  mov     rcx, [rbp+100h+var_138]
0x1401f4956  mov     eax, [rcx+0Ch]
0x1401f4959  test    r8b, al
0x1401f495c  jnz     short loc_1401F498F
0x1401f495e  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x1401f4965  nop     dword ptr [rax+rax+00h]
0x1401f496a  mov     rax, [rax+218h]
0x1401f4971  call    _guard_dispatch_icall
0x1401f4976  mov     [rsp+200h+var_196], al
0x1401f497a  mov     r12b, al
0x1401f497d  test    al, al
0x1401f497f  jz      short loc_1401F49F4
0x1401f4981  and     r15d, 0FFFFFFF4h
0x1401f4985  or      r15d, 4
0x1401f4989  jmp     short loc_1401F49F4
0x1401f498b  mov     rcx, [rbp+100h+var_138]
0x1401f498f  bt      r15d, 9
0x1401f4994  jb      short loc_1401F49D1
0x1401f4996  test    r12b, 20h
0x1401f499a  jz      short loc_1401F49A4
0x1401f499c  mov     eax, [rcx+0Ch]
0x1401f499f  test    r8b, al
0x1401f49a2  jnz     short loc_1401F49D1
0x1401f49a4  test    r15b, 1Fh
0x1401f49a8  jz      short loc_1401F49B0
0x1401f49aa  test    r15b, 40h
0x1401f49ae  jz      short loc_1401F49D1
0x1401f49b0  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x1401f49b7  nop     dword ptr [rax+rax+00h]
0x1401f49bc  mov     rax, [rax+218h]
0x1401f49c3  call    _guard_dispatch_icall
0x1401f49c8  mov     r12b, al
0x1401f49cb  mov     [rsp+200h+var_196], al
0x1401f49cf  jmp     short loc_1401F49F4
0x1401f49d1  mov     r12b, dl
0x1401f49d4  mov     [rsp+200h+var_196], dl
0x1401f49d8  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x1401f49df  nop     dword ptr [rax+rax+00h]
0x1401f49e4  xor     edx, edx
0x1401f49e6  xor     ecx, ecx
0x1401f49e8  mov     rax, [rax+210h]
0x1401f49ef  call    _guard_dispatch_icall
0x1401f49f4  mov     r14d, r15d
0x1401f49f7  mov     ebx, r15d
0x1401f49fa  and     r14d, 10000h
0x1401f4a01  and     ebx, 80h
  ... truncated ...
```
