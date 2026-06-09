# xxxReceiveMessage(tagTHREADINFO *)

- ea: `0x14018f810`
- end: `0x1401908e2`
- name: `?xxxReceiveMessage@@YAXPEAUtagTHREADINFO@@@Z`
- size: `4306`
- prototype: `void __fastcall(struct tagTHREADINFO *)`
- caller_count: `2`
- callee_count: `104`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400e9390`
- `0x14018f7d4`

## callees

- `0x14000a3ec`
- `0x14001d1b4`
- `0x14001eb04`
- `0x14001eb60`
- `0x14001ecd0`
- `0x14001ed90`
- `0x1400235ec`
- `0x1400241fc`
- `0x140026568`
- `0x14002ea00`
- `0x14002f78c`
- `0x140033e08`
- `0x140035d14`
- `0x140082c80`
- `0x1400844b0`
- `0x140095638`
- `0x140096200`
- `0x1400ba260`
- `0x1400ba780`
- `0x1400ba7e0`
- `0x1400ba960`
- `0x1400bae20`
- `0x1400bbc70`
- `0x1400bbd30`
- `0x1400bbda0`
- `0x1400ceb20`
- `0x1400cf1d0`
- `0x1400dc6cc`
- `0x1400de0b0`
- `0x1400de310`
- `0x1400de560`
- `0x1400decc0`
- `0x1400df330`
- `0x1400df5b0`
- `0x1400df8a0`
- `0x1400dfc60`
- `0x1400dff60`
- `0x1400e0460`
- `0x1400e1d60`
- `0x1400e2cb0`
- `0x1400e2de0`
- `0x1400e3d30`
- `0x1400e4250`
- `0x1400e8c20`
- `0x1400ea480`
- `0x1400ea7ac`
- `0x14013b060`
- `0x14013eb50`
- `0x14017cc14`
- `0x14018f810`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140190030`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140190093`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140190110`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019014c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140190030`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140190093`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140190110`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019014c`
- `ntoskrnl!KeBugCheckEx` at `0x14019074f`
- `ntoskrnl!KeBugCheckEx` at `0x14019074f`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x14018fecc`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x14018ff47`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x14018fecc`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x14018ff47`
- `win32kbase!EtwTraceBeginRetrieveSendMessage` at `0x14018f8c9`
- `win32kbase!EtwTraceBeginRetrieveSendMessage` at `0x14018f8c9`
- `win32kbase!EtwTraceEndRetrieveSendMessage` at `0x140190850`
- `win32kbase!EtwTraceEndRetrieveSendMessage` at `0x140190850`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1401900cd`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1401901ac`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1401900cd`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1401901ac`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140190087`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140190186`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140190087`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140190186`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14018fef2`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14018ff69`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14018fef2`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14018ff69`
- `WIN32K!W32GetUserSessionState` at `0x14018f9e9`
- `WIN32K!W32GetUserSessionState` at `0x14018fa51`
- `WIN32K!W32GetUserSessionState` at `0x14018fc65`
- `WIN32K!W32GetUserSessionState` at `0x14018fdc7`
- `WIN32K!W32GetUserSessionState` at `0x140190482`
- `WIN32K!W32GetUserSessionState` at `0x14019049f`
- `WIN32K!W32GetUserSessionState` at `0x1401904ae`
- `WIN32K!W32GetUserSessionState` at `0x1401904cf`
- `WIN32K!W32GetUserSessionState` at `0x1401907f8`
- `WIN32K!W32GetUserSessionState` at `0x14018f9e9`
- `WIN32K!W32GetUserSessionState` at `0x14018fa51`
- `WIN32K!W32GetUserSessionState` at `0x14018fc65`
- `WIN32K!W32GetUserSessionState` at `0x14018fdc7`
- `WIN32K!W32GetUserSessionState` at `0x140190482`
- `WIN32K!W32GetUserSessionState` at `0x14019049f`
- `WIN32K!W32GetUserSessionState` at `0x1401904ae`
- `WIN32K!W32GetUserSessionState` at `0x1401904cf`
- `WIN32K!W32GetUserSessionState` at `0x1401907f8`

## pseudocode

```c
void __fastcall xxxReceiveMessage(struct tagTHREADINFO *a1)
{
  __int64 v2; // rdx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  _QWORD *v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // rcx
  int *v9; // r12
  PVOID *v10; // r13
  bool v11; // cf
  _QWORD *v12; // rax
  struct tagTHREADINFO *v13; // rax
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  struct tagTHREADINFO *v17; // r14
  _DWORD *v18; // rdx
  int v19; // r15d
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 (__fastcall *v23)(int, int, int, int, __int64, __int64); // rbx
  __int64 v24; // rax
  unsigned int *v25; // rdx
  unsigned int v26; // ecx
  __int64 *v27; // rax
  __int64 v28; // rcx
  _DWORD *v29; // rax
  __int64 v30; // rcx
  _QWORD *v31; // rbx
  __int64 v32; // r15
  int v33; // r13d
  __int64 v34; // r8
  __int64 v35; // r9
  struct MOVESIZEDATA **v36; // rdx
  __int64 v37; // rax
  int v38; // r8d
  int v39; // edx
  __int64 *v40; // r9
  __int64 v41; // rdx
  struct tagHOOK *v42; // rbx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rcx
  struct MOVESIZEDATA *v46; // rcx
  unsigned int *v47; // rdx
  int v48; // ebx
  __int64 v49; // rax
  int v50; // r8d
  int v51; // edx
  int v52; // r13d
  int v53; // r13d
  const struct tagUIPI_INFO *v54; // rdx
  const struct tagUIPI_INFO *v55; // r8
  const struct tagUIPI_INFO *v56; // rdx
  const struct tagUIPI_INFO *v57; // r8
  __int64 CurrentProcessWin32Process; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 *v67; // r15
  int v68; // ebx
  int v69; // ecx
  int v70; // ecx
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // r8
  unsigned int *v74; // rdx
  unsigned int v75; // ecx
  unsigned int *v76; // rdx
  unsigned int v77; // ecx
  __int64 v78; // rax
  struct tagHIDDATA *v79; // rax
  int v80; // ebx
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // r9
  ULONG_PTR v86; // rbx
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  __int64 v90; // r9
  __int64 v91; // rbx
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // r8
  __int64 v95; // r9
  unsigned int v96; // r13d
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 v100; // rax
  __int64 v101; // rdx
  char v102; // r13
  __int64 v103; // rdx
  int v104; // eax
  __int64 v105; // rcx
  unsigned __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rdx
  __int64 v109; // rcx
  int *v110; // rcx
  int v111; // ebx
  __int64 v112; // rdx
  struct tagTHREADINFO *v113; // rax
  __int64 v114; // rdx
  __int64 v115; // rcx
  _DWORD *v116; // rcx
  int v117; // ebx
  __int64 v118; // rdx
  struct tagTHREADINFO *v119; // rax
  __int64 v120; // rdx
  __int64 v121; // rcx
  __int64 v122; // rax
  __int64 v123; // rdx
  __int64 v124; // r8
  __int64 v125; // r9
  struct tagHOOK *v126; // r14
  char v127; // r15
  bool v128; // r13
  int v129; // ebx
  __int64 UserSessionState; // rax
  int v131; // r8d
  int v132; // edx
  __int64 v133; // r8
  __int64 v134; // r9
  int v135; // ecx
  char v136; // [rsp+50h] [rbp-138h]
  char v137; // [rsp+50h] [rbp-138h]
  bool v138; // [rsp+51h] [rbp-137h]
  bool v139; // [rsp+51h] [rbp-137h]
  int v140; // [rsp+54h] [rbp-134h]
  struct tagHOOK *v141; // [rsp+58h] [rbp-130h]
  __int64 v142; // [rsp+60h] [rbp-128h] BYREF
  _QWORD *v143; // [rsp+68h] [rbp-120h]
  PVOID *v144; // [rsp+70h] [rbp-118h]
  char *v145; // [rsp+78h] [rbp-110h]
  PVOID *v146; // [rsp+80h] [rbp-108h]
  _QWORD *v147; // [rsp+88h] [rbp-100h]
  ULONG_PTR v148[2]; // [rsp+90h] [rbp-F8h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v150; // [rsp+B0h] [rbp-D8h]
  __int128 v151; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 v152; // [rsp+D0h] [rbp-B8h]
  int v153; // [rsp+D8h] [rbp-B0h]
  __int64 v154; // [rsp+E0h] [rbp-A8h]
  __int64 v155[2]; // [rsp+F0h] [rbp-98h] BYREF
  __int128 v156; // [rsp+100h] [rbp-88h]
  __int128 v157; // [rsp+110h] [rbp-78h]
  _BYTE v158[56]; // [rsp+120h] [rbp-68h] BYREF

  v142 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v148);
  v3 = (_QWORD *)*((_QWORD *)a1 + 69);
  if ( v3 == (_QWORD *)((char *)a1 + 552) )
  {
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 8LL), 0xFFFFFFBF);
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 4LL), 0xFFFFFFBF);
    goto LABEL_3;
  }
  --*((_DWORD *)a1 + 142);
  v4 = *v3;
  if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
    __fastfail(3u);
  v6 = v3 - 2;
  v143 = v3 - 2;
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  *v3 = 0;
  EtwTraceBeginRetrieveSendMessage(v3 - 2);
  v9 = (int *)v6 + 21;
  v145 = (char *)v6 + 84;
  *((_DWORD *)v6 + 21) |= 0x4010u;
  if ( *((struct tagTHREADINFO **)a1 + 69) == (struct tagTHREADINFO *)((char *)a1 + 552) )
  {
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 8LL), 0xFFFFFFBF);
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 4LL), 0xFFFFFFBF);
  }
  v10 = (PVOID *)v6[4];
  v144 = v10;
  v146 = v10;
  if ( v10 )
  {
    v11 = (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x100) != 0;
    v12 = (_QWORD *)*((_QWORD *)a1 + 64);
    if ( v11 )
      *v12 |= 0x1000uLL;
    else
      *v12 &= ~0x1000uLL;
  }
  if ( *((_DWORD *)v6 + 26) == 255 && (*v9 & 0x200) == 0 )
  {
    v13 = PtiCurrent(v8, v7);
    FlushPostedRawInput(v13);
  }
  v14 = *v9;
  if ( (*v9 & 0x200) == 0 )
  {
    if ( (v14 & 7) != 0 )
    {
      if ( (v14 & 0x20004) == 0x20004 )
      {
        LOBYTE(v7) = 5;
        v122 = HMValidateHandleNoSecure(v6[15], v7);
        v126 = (struct tagHOOK *)v122;
        if ( v122 )
        {
          if ( (*(_DWORD *)(v122 + 64) & 0x2000) != 0 )
          {
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (v127 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              v127 = 0;
            }
            v128 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v127 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v129 = *(_DWORD *)(v122 + 48);
              UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v123, v124, v125);
              LOBYTE(v131) = v128;
              LOBYTE(v132) = v127;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v132,
                v131,
                *(_QWORD *)(UserSessionState + 69152),
                4,
                5,
                12,
                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                v129);
            }
            DeBoostHook(v126, v123, v124, v125);
          }
        }
      }
      goto LABEL_158;
    }
    v29 = (_DWORD *)*((_QWORD *)a1 + 60);
    LODWORD(v146) = *v29;
    v30 = *((_QWORD *)a1 + 68);
    v154 = v30;
    *((_QWORD *)a1 + 68) = v6;
    *v29 |= 2u;
    **((_DWORD **)a1 + 60) |= 8u;
    if ( !v10 )
      Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>((__int64 *)v148, v6[14]);
    if ( *((_DWORD *)v6 + 26) == 788 )
    {
      *(_OWORD *)v155 = 0;
      v156 = 0;
      *(_QWORD *)&v157 = 0;
      v145 = 0;
      v150 = 0;
      v143 = 0;
      *(_QWORD *)&v151 = 0;
      v31 = (_QWORD *)v6[12];
      v32 = v31[2];
      v33 = *(_DWORD *)(*v31 + 48LL);
      v147 = (_QWORD *)*((_QWORD *)a1 + 196);
      switch ( v33 )
      {
        case 2:
          goto LABEL_41;
        case 7:
          if ( v32 )
          {
            *(_OWORD *)v155 = *(_OWORD *)v32;
            v156 = *(_OWORD *)(v32 + 16);
            *(_QWORD *)&v157 = *(_QWORD *)(v32 + 32);
            CurrentProcessWin32Process = PsGetCurrentProcessWin32Process((unsigned int)(v33 - 7));
            if ( CurrentProcessWin32Process )
              CurrentProcessWin32Process &= -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
            if ( (((unsigned __int16)(*((_DWORD *)v6 + 33) >> 8)
                 ^ (unsigned __int16)(*(_DWORD *)(CurrentProcessWin32Process + 268) >> 8))
                & 0x1FF) != 0 )
            {
              LogicalToPhysicalDPIPoint(v155, v155, *((unsigned int *)v6 + 33), 0);
              v60 = PsGetCurrentProcessWin32Process(v59);
              v61 = v60;
              if ( v60 )
                v61 = -(__int64)(*(_QWORD *)v60 != 0) & v60;
              PhysicalToLogicalDPIPoint(v155, v155, *(unsigned int *)(v61 + 268), 0);
            }
          }
          goto LABEL_42;
        case 10:
          goto LABEL_41;
        case 13:
          InputTraceLogging::Keyboard::ProcessLowLevelHook();
          if ( v32 )
          {
            v155[0] = *(_QWORD *)v32;
            v155[1] = *(_QWORD *)(v32 + 8);
            *(_QWORD *)&v156 = *(_QWORD *)(v32 + 16);
            if ( UIPrivilegeIsolation::IsUIPIInfoValid((UIPrivilegeIsolation *)((char *)v31 + 28), v56)
              && !UIPrivilegeIsolation::CheckAccess(
                    (UIPrivilegeIsolation *)((char *)v31 + 28),
                    (const struct tagUIPI_INFO *)(*((_QWORD *)a1 + 57) + 864LL),
                    v57) )
            {
              LODWORD(v155[1]) |= 2u;
            }
          }
          break;
        case 14:
          InputTraceLogging::Mouse::HandleLowLevelHook();
          if ( v32 )
          {
            v155[0] = *(_QWORD *)v32;
            v155[1] = *(_QWORD *)(v32 + 8);
            v156 = *(_OWORD *)(v32 + 16);
            if ( UIPrivilegeIsolation::IsUIPIInfoValid((UIPrivilegeIsolation *)((char *)v31 + 28), v54)
              && !UIPrivilegeIsolation::CheckAccess(
                    (UIPrivilegeIsolation *)((char *)v31 + 28),
                    (const struct tagUIPI_INFO *)(*((_QWORD *)a1 + 57) + 864LL),
                    v55) )
            {
              HIDWORD(v155[1]) |= 2u;
            }
          }
          break;
        default:
          UserSetLastError(87);
LABEL_41:
          v32 = 0;
LABEL_42:
          v141 = (struct tagHOOK *)*v31;
          Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, (__int64)a1, *v31);
          if ( (*((_DWORD *)v141 + 16) & 0x2000) != 0 )
          {
            v36 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (LOBYTE(v36) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              LOBYTE(v36) = 0;
            }
            v136 = (char)v36;
            v138 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v36 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v37 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v36, v34, v35);
              LOBYTE(v38) = v138;
              LOBYTE(v39) = v136;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v39,
                v38,
                *(_QWORD *)(v37 + 69152),
                4,
                5,
                10,
                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                v33);
            }
          }
          if ( (*v9 & 4) != 0 )
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4114);
          v40 = v155;
          if ( !v32 )
            v40 = (__int64 *)v31[2];
          v41 = *((unsigned int *)v31 + 2);
          v42 = v141;
          v142 = xxxCallHook2((__int64)v141, v41, v6[11], (__int64)v40, 0);
          if ( (unsigned int)(v33 - 13) <= 1 )
          {
            *((_QWORD *)a1 + 193) = v150;
            *((_DWORD *)a1 + 388) = (_DWORD)v145;
            *(_QWORD *)((char *)a1 + 1556) = v151;
            *((_DWORD *)a1 + 391) = (_DWORD)v143;
            *((_QWORD *)a1 + 196) = v147;
          }
          v45 = 131076;
          if ( (*v9 & 0x20004) == 0x20004 && (*((_DWORD *)v141 + 16) & 0x2000) != 0 )
          {
            v46 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (LOBYTE(v46) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              LOBYTE(v46) = 0;
            }
            v137 = (char)v46;
            v47 = &WPP_RECORDER_INITIALIZED;
            v139 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v46 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v48 = *((_DWORD *)v141 + 12);
              v49 = W32GetUserSessionState(v46, &WPP_RECORDER_INITIALIZED, v43, v44);
              LOBYTE(v50) = v139;
              LOBYTE(v51) = v137;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v51,
                v50,
                *(_QWORD *)(v49 + 69152),
                4,
                5,
                11,
                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                v48);
              v42 = v141;
            }
            DeBoostHook(v42, (__int64)v47, v43, v44);
          }
          if ( (*v9 & 5) == 0 && v32 )
          {
            v52 = v33 - 7;
            if ( v52 )
            {
              v53 = v52 - 6;
              if ( v53 )
              {
                if ( v53 == 1 )
                {
                  *(_QWORD *)v32 = v155[0];
                  *(_QWORD *)(v32 + 8) = v155[1];
                  *(_OWORD *)(v32 + 16) = v156;
                }
              }
              else
              {
                *(_QWORD *)v32 = v155[0];
                *(_QWORD *)(v32 + 8) = v155[1];
                *(_QWORD *)(v32 + 16) = v156;
              }
            }
            else
            {
              v62 = PsGetCurrentProcessWin32Process(v45);
              if ( v62 )
                v62 &= -(__int64)(*(_QWORD *)v62 != 0);
              v63 = *(_DWORD *)(v62 + 268) >> 8;
              LOWORD(v63) = (*((_DWORD *)v6 + 33) >> 8) ^ v63;
              if ( (v63 & 0x1FF) != 0 )
              {
                v64 = PsGetCurrentProcessWin32Process(v63);
                v65 = v64;
                if ( v64 )
                  v65 = -(__int64)(*(_QWORD *)v64 != 0) & v64;
                LogicalToPhysicalDPIPoint(v155, v155, *(unsigned int *)(v65 + 268), 0);
                PhysicalToLogicalDPIPoint(v155, v155, *((unsigned int *)v6 + 33), 0);
              }
              *(_OWORD *)v32 = *(_OWORD *)v155;
              *(_OWORD *)(v32 + 16) = v156;
              *(_QWORD *)(v32 + 32) = v157;
            }
          }
          Win32HMThreadLockAlways<tagACCELTABLE>::~Win32HMThreadLockAlways<tagACCELTABLE>(BugCheckParameter3);
          v67 = v6 + 14;
LABEL_97:
          v10 = v144;
LABEL_98:
          v68 = (unsigned __int8)v146 & 8;
          v69 = *v9;
          if ( (*v9 & 0x101) == 0x100 )
          {
            HIDWORD(v155[0]) = 0;
            v157 = 0;
            v70 = v69 | 1;
            *v9 = v70;
            if ( (v70 & 4) == 0 )
            {
              v71 = 33;
              if ( (v70 & 0x400) != 0 )
                v71 = 289;
              LODWORD(v155[0]) = v71;
              v155[1] = v6[6];
              *(_QWORD *)&v156 = v6[7];
              *((_QWORD *)&v156 + 1) = v142;
              Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, *v67);
              xxxInterSendMsgEx(
                (struct tagWND *)*v67,
                *((_DWORD *)v6 + 26),
                0,
                0,
                0,
                v6[8],
                (__int64)v155,
                1,
                *v9 & 0x10000);
              Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((__int64 *)BugCheckParameter3, v72);
            }
          }
          if ( !v10 )
            Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(v148, v66);
          v73 = v154;
          *((_QWORD *)a1 + 68) = v154;
          v74 = (unsigned int *)*((_QWORD *)a1 + 60);
          v75 = *v74 | 2;
          if ( !v73 )
            v75 = *v74 & 0xFFFFFFFD;
          *v74 = v75;
          v76 = (unsigned int *)*((_QWORD *)a1 + 60);
          v77 = *v76 | 8;
          if ( !v68 )
            v77 = *v76 & 0xFFFFFFF7;
          *v76 = v77;
          if ( *((_DWORD *)v6 + 26) == 255 )
          {
            LOBYTE(v76) = 18;
            v78 = HMValidateHandleNoSecure(v6[12], (__int64)v76);
            if ( v78 )
            {
              if ( *(struct tagTHREADINFO **)(v78 + 16) == a1 )
              {
                v79 = UnlinkHidData(a1, (struct tagHIDDATA *)v78, 0);
                if ( v79 )
                  FreeHidData((__int64)v79);
              }
              else
              {
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4410);
              }
            }
          }
          goto LABEL_158;
      }
      v150 = *((_QWORD *)a1 + 193);
      LODWORD(v145) = *((_DWORD *)a1 + 388);
      *(_QWORD *)&v151 = *(_QWORD *)((char *)a1 + 1556);
      LODWORD(v143) = *((_DWORD *)a1 + 391);
      *((_QWORD *)a1 + 193) = *(_QWORD *)((char *)v31 + 28);
      *((_DWORD *)a1 + 388) = *((_DWORD *)v31 + 9);
      *(_QWORD *)((char *)a1 + 1556) = v31[5];
      *((_DWORD *)a1 + 391) = *((_DWORD *)v31 + 12);
      *((_QWORD *)a1 + 196) = v155;
      goto LABEL_42;
    }
    v140 = *((_DWORD *)PtiCurrent(v30, 2) + 401);
    v80 = *((_DWORD *)v6 + 32);
    *((_DWORD *)PtiCurrent(v82, v81) + 401) = v80;
    SharedUserCritOnly::DomainShared<DLT_HOOK>::DomainExclusive<>::ObjectLock<>::ObjectLock<>((__int64)v158);
    v67 = v6 + 14;
    if ( ShouldCallWndProcHook(a1, 32, *((_DWORD *)v6 + 26), (struct tagWND *)v6[14]) )
    {
      *(_OWORD *)v155 = 0;
      v156 = 0;
      *(_QWORD *)&v157 = 0;
      if ( *v67 )
        *((_QWORD *)&v156 + 1) = *(_QWORD *)*v67;
      LODWORD(v156) = *((_DWORD *)v6 + 26);
      v155[1] = v6[11];
      v155[0] = v6[12];
      *(_QWORD *)&v157 = v6;
      xxxCallHook(0, 1, (__int64)v155, 4);
    }
    SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>((__int64)v158);
    FreeDelayedHooks();
    if ( (*((_DWORD *)v6 + 21) & 7) != 0 )
      goto LABEL_98;
    v147 = v6 + 14;
    if ( !*v67 )
      goto LABEL_98;
    v86 = 0;
    v143 = *(_QWORD **)*v67;
    v153 = (unsigned __int16)v143;
    v88 = *(_QWORD *)(W32GetUserSessionState(v83, v66, v84, v85) + 19704);
    if ( (unsigned __int64)(unsigned __int16)v143 >= *(_QWORD *)(v88 + 8)
      || (v91 = W32GetUserSessionState(v88, v87, v89, v90),
          v96 = *(_DWORD *)(W32GetUserSessionState(v93, v92, v94, v95) + 19728) * (unsigned __int16)v143,
          v86 = v96 + *(_QWORD *)(v91 + 19720),
          v100 = W32GetUserSessionState(v96, v97, v98, v99),
          v101 = v6[14],
          *(_QWORD *)(*(_QWORD *)(v100 + 19664) + 40LL * (unsigned __int16)v143) != v101)
      || *(_BYTE *)(v86 + 24) != 1 )
    {
      KeBugCheckEx(0x197u, 1u, *v67, v86, 1u);
    }
    if ( (*(_BYTE *)(*(_QWORD *)(v101 + 40) + 18LL) & 4) == 0 )
    {
      Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, v101);
      v110 = (int *)*((_QWORD *)PtiCurrent(v109, v108) + 60);
      v111 = *v110;
      v113 = PtiCurrent((__int64)v110, v112);
      **((_DWORD **)v113 + 60) |= 0x10u;
      xxxSendMessageToClient((struct tagWND *)*v67, *((_DWORD *)v6 + 26), v6[11], v6[12], (struct tagSMS *)v6, 1, &v142);
      v116 = (_DWORD *)*((_QWORD *)PtiCurrent(v115, v114) + 60);
      v117 = (*v116 ^ v111) & 0x10;
      v119 = PtiCurrent((__int64)v116, v118);
      **((_DWORD **)v119 + 60) ^= v117;
LABEL_139:
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((__int64 *)BugCheckParameter3, v103);
      SharedUserCritOnly::DomainShared<DLT_HOOK>::DomainExclusive<>::ObjectLock<>::ObjectLock<>((__int64)v158);
      if ( (*v9 & 4) == 0 && ShouldCallWndProcHook(a1, 0x2000, *((_DWORD *)v6 + 26), (struct tagWND *)*v67) )
      {
        *(_OWORD *)v155 = 0;
        v156 = 0;
        v157 = 0;
        if ( *v67 )
          *(_QWORD *)&v157 = *(_QWORD *)*v67;
        DWORD2(v156) = *((_DWORD *)v6 + 26);
        *(_QWORD *)&v156 = v6[11];
        v155[1] = v6[12];
        v155[0] = v142;
        *((_QWORD *)&v157 + 1) = v6;
        xxxCallHook(0, 1, (__int64)v155, 12);
      }
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>((__int64)v158);
      FreeDelayedHooks();
      *((_DWORD *)PtiCurrent(v121, v120) + 401) = v140;
      goto LABEL_97;
    }
    v151 = 0;
    v152 = 0;
    v102 = 0;
    Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, v101);
    v103 = *((unsigned int *)v6 + 26);
    if ( (unsigned int)v103 >= 0x400 )
    {
      v104 = 0;
    }
    else
    {
      if ( !_bittest16(&MessageTable[v103], 9u) && ((_DWORD)v103 != 537 || (v6[11] & 0x8000LL) == 0) )
      {
LABEL_133:
        v105 = v6[14];
        v106 = *(_QWORD *)(*(_QWORD *)(v105 + 40) + 120LL);
        if ( v106 < 4 )
          v107 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))(&gServerHandlers)[v106])(
                   v105,
                   v103,
                   v6[11],
                   v6[12]);
        else
          v107 = 0;
        v142 = v107;
        if ( v102 )
          PopAndFreeW32ThreadLock((__int64)&v151, v103);
        goto LABEL_139;
      }
      v104 = 1;
    }
    if ( v104 )
    {
      *((_DWORD *)v6 + 21) |= 0x20u;
      if ( v144 )
      {
        v102 = 1;
        LockKernelStack(*v144, (struct _TL *)&v151);
        v103 = *((unsigned int *)v6 + 26);
      }
    }
    goto LABEL_133;
  }
  if ( !v10 )
    Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>((__int64 *)v148, v6[14]);
  if ( (*v9 & 0x400) != 0 )
  {
    v17 = PtiCurrent(v8, v7);
    v18 = (_DWORD *)*((_QWORD *)v17 + 60);
    v19 = *v18 & 8;
    *v18 |= 4u;
    **((_DWORD **)v17 + 60) |= 8u;
    v20 = *((_DWORD *)v6 + 26);
    if ( v20 == 576 || v20 == 281 )
    {
      v22 = (unsigned __int8)MessageTable[(unsigned __int16)v20];
      v23 = gapfnScSendMessage[v22];
      v24 = W32GetUserSessionState(v22, v18, v15, v16);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, _QWORD))v23)(
        v6[14],
        *((unsigned int *)v6 + 26),
        v6[7],
        v6[9],
        v6[6],
        *(_QWORD *)(*(_QWORD *)(v24 + 19704) + 752LL),
        1,
        0);
    }
    else
    {
      v21 = W32GetUserSessionState((unsigned int)(v20 - 576), v18, v15, v16);
      SfnDWORD(
        (__int64 *)v6[14],
        *((_DWORD *)v6 + 26),
        v6[7],
        v6[9],
        v6[6],
        *(_QWORD *)(*(_QWORD *)(v21 + 19704) + 752LL));
    }
    **((_DWORD **)v17 + 60) &= ~4u;
    v25 = (unsigned int *)*((_QWORD *)v17 + 60);
    v26 = *v25 | 8;
    if ( !v19 )
      v26 = *v25 & 0xFFFFFFF7;
    *v25 = v26;
  }
  else
  {
    v27 = (__int64 *)v6[14];
    v28 = 0;
    if ( v27 )
      v28 = *v27;
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))v6[6])(v28, *((unsigned int *)v6 + 26), v6[7], v6[9]);
  }
  if ( !v10 )
    Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(v148, (__int64)v25);
LABEL_158:
  EtwTraceEndRetrieveSendMessage(v6);
  *v9 &= ~0x4000u;
  v135 = *v9;
  if ( (*v9 & 8) != 0 )
  {
    UnlinkSendListSms(v6, v2, v133, v134);
  }
  else if ( (v135 & 1) == 0 )
  {
    v6[9] = v142;
    *v9 = v135 | 1;
    if ( v144 )
      SetWakeBit((__int64)v144, 0x200u);
  }
LABEL_3:
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(v148, v2);
}

```

## disassembly

```asm
0x14018f810  mov     [rsp+arg_8], rbx
0x14018f815  mov     [rsp+arg_10], rsi
0x14018f81a  push    rdi
0x14018f81b  push    r12
0x14018f81d  push    r13
0x14018f81f  push    r14
0x14018f821  push    r15
0x14018f823  sub     rsp, 160h
0x14018f82a  mov     rax, cs:__security_cookie
0x14018f831  xor     rax, rsp
0x14018f834  mov     [rsp+188h+var_30], rax
0x14018f83c  mov     r14, rcx
0x14018f83f  mov     [rsp+188h+var_130], rcx
0x14018f844  xor     edi, edi
0x14018f846  mov     [rsp+188h+var_128], rdi
0x14018f84b  lea     rcx, [rsp+188h+var_F8]
0x14018f853  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x14018f858  lea     rbx, [r14+228h]
0x14018f85f  mov     rax, [rbx]
0x14018f862  cmp     rax, rbx
0x14018f865  jnz     short loc_14018F892
0x14018f867  mov     rax, [r14+1E0h]
0x14018f86e  lock and dword ptr [rax+8], 0FFFFFFBFh
0x14018f873  mov     rax, [r14+1E0h]
0x14018f87a  lock and dword ptr [rax+4], 0FFFFFFBFh
0x14018f87f  lea     rcx, [rsp+188h+var_F8]; BugCheckParameter3
0x14018f887  call    ??1?$Win32HMOptionalThreadLock@UtagHOOK@@@@QEAA@XZ; Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(void)
0x14018f88c  jmp     loc_1401908B5
0x14018f892  dec     dword ptr [r14+238h]
0x14018f899  mov     rdx, [rax]
0x14018f89c  cmp     [rdx+8], rax
0x14018f8a0  jnz     loc_1401908AE
0x14018f8a6  mov     rcx, [rax+8]
0x14018f8aa  cmp     [rcx], rax
0x14018f8ad  jnz     loc_1401908AE
0x14018f8b3  lea     rsi, [rax-10h]
0x14018f8b7  mov     [rsp+188h+var_120], rsi
0x14018f8bc  mov     [rcx], rdx
0x14018f8bf  mov     [rdx+8], rcx
0x14018f8c3  mov     [rax], rdi
0x14018f8c6  mov     rcx, rsi
0x14018f8c9  call    cs:__imp_EtwTraceBeginRetrieveSendMessage
0x14018f8d0  nop     dword ptr [rax+rax+00h]
0x14018f8d5  lea     r12, [rsi+54h]
0x14018f8d9  mov     [rsp+188h+var_110], r12
0x14018f8de  or      dword ptr [r12], 4010h
0x14018f8e6  cmp     [rbx], rbx
0x14018f8e9  jnz     short loc_14018F903
0x14018f8eb  mov     rax, [r14+1E0h]
0x14018f8f2  lock and dword ptr [rax+8], 0FFFFFFBFh
0x14018f8f7  mov     rax, [r14+1E0h]
0x14018f8fe  lock and dword ptr [rax+4], 0FFFFFFBFh
0x14018f903  mov     r13, [rsi+20h]
0x14018f907  mov     [rsp+188h+var_118], r13
0x14018f90c  mov     [rsp+188h+var_108], r13
0x14018f914  test    r13, r13
0x14018f917  jz      short loc_14018F95D
0x14018f919  xor     eax, eax
0x14018f91b  lock cmpxchg [r13+208h], edi
0x14018f924  bt      eax, 8
0x14018f928  mov     rax, [r14+200h]
0x14018f92f  jnb     short loc_14018F938
0x14018f931  bts     qword ptr [rax], 0Ch
0x14018f936  jmp     short loc_14018F93D
0x14018f938  btr     qword ptr [rax], 0Ch
0x14018f93d  jmp     short loc_14018F95D
0x14018f93f  xor     edi, edi
0x14018f941  mov     r14, [rsp+188h+var_130]
0x14018f946  mov     rsi, [rsp+188h+var_120]
0x14018f94b  mov     r12, [rsp+188h+var_110]
0x14018f950  mov     r13, [rsp+188h+var_108]
0x14018f958  mov     [rsp+188h+var_118], r13
0x14018f95d  mov     ebx, 200h
0x14018f962  cmp     dword ptr [rsi+68h], 0FFh
0x14018f969  jnz     short loc_14018F97E
0x14018f96b  test    [r12], ebx
0x14018f96f  jnz     short loc_14018F97E
0x14018f971  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14018f976  mov     rcx, rax; struct tagTHREADINFO *
0x14018f979  call    ?FlushPostedRawInput@@YAXPEAUtagTHREADINFO@@@Z; FlushPostedRawInput(tagTHREADINFO *)
0x14018f97e  mov     eax, [r12]
0x14018f982  test    ebx, eax
0x14018f984  jz      loc_14018FB03
0x14018f98a  test    r13, r13
0x14018f98d  jnz     short loc_14018F9A0
0x14018f98f  mov     rdx, [rsi+70h]
0x14018f993  lea     rcx, [rsp+188h+var_F8]
0x14018f99b  call    ??$ManualLock@X@?$Win32HMThreadLockBase@UtagMENU@@$00$00@@QEAAXPEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(tagMENU *)
0x14018f9a0  test    dword ptr [r12], 400h
0x14018f9a8  jz      loc_14018FAC2
0x14018f9ae  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14018f9b3  mov     r14, rax
0x14018f9b6  mov     rdx, [rax+1E0h]
0x14018f9bd  mov     ecx, [rdx]
0x14018f9bf  mov     r15d, ecx
0x14018f9c2  and     r15d, 8
0x14018f9c6  or      ecx, 4
0x14018f9c9  mov     [rdx], ecx
0x14018f9cb  mov     rcx, [rax+1E0h]
0x14018f9d2  or      dword ptr [rcx], 8
0x14018f9d5  mov     eax, [rsi+68h]
0x14018f9d8  lea     ecx, [rax-240h]
0x14018f9de  test    ecx, ecx
0x14018f9e0  jz      short loc_14018FA34
0x14018f9e2  cmp     eax, 119h
0x14018f9e7  jz      short loc_14018FA34
0x14018f9e9  call    cs:__imp_W32GetUserSessionState
0x14018f9f0  nop     dword ptr [rax+rax+00h]
0x14018f9f5  mov     rcx, [rax+4CF8h]
0x14018f9fc  mov     rax, [rcx+2F0h]
0x14018fa03  mov     [rsp+188h+var_150], rdi
0x14018fa08  mov     dword ptr [rsp+188h+var_158], 1
0x14018fa10  mov     qword ptr [rsp+188h+var_160], rax
0x14018fa15  mov     rax, [rsi+30h]
0x14018fa19  mov     [rsp+188h+BugCheckParameter4], rax
0x14018fa1e  mov     r9, [rsi+48h]
0x14018fa22  mov     r8, [rsi+38h]
0x14018fa26  mov     edx, [rsi+68h]
0x14018fa29  mov     rcx, [rsi+70h]
0x14018fa2d  call    SfnDWORD
0x14018fa32  jmp     short loc_14018FA9D
0x14018fa34  movzx   eax, ax
0x14018fa37  lea     rbx, cs:140000000h
0x14018fa3e  movzx   eax, ds:rva MessageTable[rbx+rax*2]
0x14018fa46  movzx   ecx, al
0x14018fa49  mov     rbx, ds:(gapfnScSendMessage - 140000000h)[rbx+rcx*8]
0x14018fa51  call    cs:__imp_W32GetUserSessionState
0x14018fa58  nop     dword ptr [rax+rax+00h]
0x14018fa5d  mov     rcx, [rax+4CF8h]
0x14018fa64  mov     rdx, [rcx+2F0h]
0x14018fa6b  mov     [rsp+188h+var_150], rdi
0x14018fa70  mov     dword ptr [rsp+188h+var_158], 1
0x14018fa78  mov     qword ptr [rsp+188h+var_160], rdx
0x14018fa7d  mov     rcx, [rsi+30h]
0x14018fa81  mov     [rsp+188h+BugCheckParameter4], rcx
0x14018fa86  mov     r9, [rsi+48h]
0x14018fa8a  mov     r8, [rsi+38h]
0x14018fa8e  mov     edx, [rsi+68h]
0x14018fa91  mov     rcx, [rsi+70h]
0x14018fa95  mov     rax, rbx
0x14018fa98  call    _guard_dispatch_icall
0x14018fa9d  mov     rax, [r14+1E0h]
0x14018faa4  and     dword ptr [rax], 0FFFFFFFBh
0x14018faa7  mov     rdx, [r14+1E0h]
0x14018faae  mov     ecx, [rdx]
0x14018fab0  mov     eax, ecx
0x14018fab2  and     eax, 0FFFFFFF7h
0x14018fab5  or      ecx, 8
0x14018fab8  test    r15d, r15d
0x14018fabb  cmovz   ecx, eax
0x14018fabe  mov     [rdx], ecx
0x14018fac0  jmp     short loc_14018FAE8
0x14018fac2  mov     r10, [rsi+30h]
0x14018fac6  mov     r9, [rsi+48h]
0x14018faca  mov     r8, [rsi+38h]
0x14018face  mov     edx, [rsi+68h]
0x14018fad1  mov     rax, [rsi+70h]
0x14018fad5  test    rax, rax
0x14018fad8  mov     rcx, rdi
0x14018fadb  jz      short loc_14018FAE0
0x14018fadd  mov     rcx, [rax]
0x14018fae0  mov     rax, r10
0x14018fae3  call    _guard_dispatch_icall
0x14018fae8  test    r13, r13
0x14018faeb  jnz     loc_14019084D
0x14018faf1  lea     rcx, [rsp+188h+var_F8]; BugCheckParameter3
0x14018faf9  call    ??$ManualUnlock@X@?$Win32HMThreadLockBase@UtagCURSOR@@$00$00@@QEAAPEAUtagCURSOR@@XZ; Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(void)
0x14018fafe  jmp     loc_14019084D
0x14018fb03  test    al, 7
0x14018fb05  jnz     loc_14019077F
0x14018fb0b  mov     rax, [r14+1E0h]
0x14018fb12  mov     ecx, [rax]
0x14018fb14  mov     dword ptr [rsp+188h+var_108], ecx
0x14018fb1b  mov     rcx, [r14+220h]
0x14018fb22  mov     [rsp+188h+var_A8], rcx
0x14018fb2a  mov     [r14+220h], rsi
0x14018fb31  mov     edx, 2
0x14018fb36  or      [rax], edx
0x14018fb38  mov     rax, [r14+1E0h]
0x14018fb3f  or      dword ptr [rax], 8
0x14018fb42  test    r13, r13
0x14018fb45  jnz     short loc_14018FB5C
0x14018fb47  mov     rdx, [rsi+70h]
0x14018fb4b  lea     rcx, [rsp+188h+var_F8]
0x14018fb53  call    ??$ManualLock@X@?$Win32HMThreadLockBase@UtagMENU@@$00$00@@QEAAXPEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(tagMENU *)
0x14018fb58  lea     edx, [r13+2]
0x14018fb5c  cmp     dword ptr [rsi+68h], 314h
0x14018fb63  jnz     loc_140190374
0x14018fb69  xorps   xmm0, xmm0
0x14018fb6c  xor     eax, eax
0x14018fb6e  movups  xmmword ptr [rsp+188h+var_98], xmm0
0x14018fb76  movups  [rsp+188h+var_88], xmm0
0x14018fb7e  mov     qword ptr [rsp+188h+var_78], rax
0x14018fb86  mov     [rsp+188h+var_110], rax
0x14018fb8b  mov     [rsp+188h+var_D8], rax
0x14018fb93  mov     [rsp+188h+var_120], rax
0x14018fb98  mov     qword ptr [rsp+188h+var_C8], rax
0x14018fba0  mov     rbx, [rsi+60h]
0x14018fba4  mov     r15, [rbx+10h]
0x14018fba8  mov     rax, [rbx]
0x14018fbab  mov     r13d, [rax+30h]
0x14018fbaf  mov     rax, [r14+620h]
0x14018fbb6  mov     [rsp+188h+var_100], rax
0x14018fbbe  mov     ecx, r13d
0x14018fbc1  sub     ecx, edx
0x14018fbc3  jz      short loc_14018FBEF
0x14018fbc5  sub     ecx, 5
0x14018fbc8  jz      loc_14018FFFF
0x14018fbce  sub     ecx, 3
0x14018fbd1  jz      short loc_14018FBEF
0x14018fbd3  sub     ecx, 3
0x14018fbd6  jz      loc_14018FF0C
0x14018fbdc  cmp     ecx, 1
0x14018fbdf  jz      loc_14018FE8B
0x14018fbe5  mov     ecx, 57h ; 'W'
0x14018fbea  call    UserSetLastError
0x14018fbef  mov     r15, rdi
0x14018fbf2  mov     rax, [rbx]
0x14018fbf5  mov     [rsp+188h+var_130], rax
0x14018fbfa  mov     r8, rax
0x14018fbfd  mov     rdx, r14
0x14018fc00  lea     rcx, [rsp+188h+BugCheckParameter3]
0x14018fc08  call    ??0?$Win32HMThreadLockAlways@UtagHOOK@@@@QEAA@PEAUtagTHREADINFO@@PEAUtagHOOK@@@Z; Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(tagTHREADINFO *,tagHOOK *)
0x14018fc0d  mov     rax, [rsp+188h+var_130]
0x14018fc12  test    dword ptr [rax+40h], 2000h
0x14018fc19  jz      loc_14018FCB6
0x14018fc1f  lea     rdx, WPP_GLOBAL_Control
0x14018fc26  mov     rcx, cs:WPP_GLOBAL_Control
0x14018fc2d  cmp     rcx, rdx
0x14018fc30  jz      short loc_14018FC41
0x14018fc32  mov     eax, [rcx+2Ch]
0x14018fc35  test    al, 10h
0x14018fc37  jz      short loc_14018FC41
0x14018fc39  cmp     byte ptr [rcx+29h], 4
0x14018fc3d  mov     dl, 1
0x14018fc3f  jnb     short loc_14018FC44
0x14018fc41  mov     dl, dil
0x14018fc44  mov     [rsp+188h+var_138], dl
0x14018fc48  lea     rcx, WPP_RECORDER_INITIALIZED
0x14018fc4f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14018fc56  setnz   al
0x14018fc59  mov     [rsp+188h+var_137], al
0x14018fc5d  test    dl, dl
0x14018fc5f  jnz     short loc_14018FC65
0x14018fc61  test    al, al
0x14018fc63  jz      short loc_14018FCB6
0x14018fc65  call    cs:__imp_W32GetUserSessionState
0x14018fc6c  nop     dword ptr [rax+rax+00h]
0x14018fc71  mov     r9, [rax+10E20h]
0x14018fc78  mov     [rsp+188h+var_148], r13d
0x14018fc7d  lea     rax, WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids
0x14018fc84  mov     [rsp+188h+var_150], rax
0x14018fc89  mov     word ptr [rsp+188h+var_158], 0Ah
0x14018fc90  mov     [rsp+188h+var_160], 5
0x14018fc98  mov     byte ptr [rsp+188h+BugCheckParameter4], 4
0x14018fc9d  mov     r8b, [rsp+188h+var_137]
0x14018fca2  mov     dl, [rsp+188h+var_138]
0x14018fca6  mov     rcx, cs:WPP_GLOBAL_Control
0x14018fcad  mov     rcx, [rcx+18h]
0x14018fcb1  call    WPP_RECORDER_AND_TRACE_SF_D
0x14018fcb6  mov     eax, [r12]
0x14018fcba  test    al, 4
0x14018fcbc  jz      short loc_14018FCDC
0x14018fcbe  mov     [rsp+188h+var_134], 20000h
0x14018fcc6  mov     r8d, 1012h
0x14018fccc  mov     edx, [rsp+188h+var_134]
0x14018fcd0  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14018fcd7  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14018fcdc  test    r15, r15
0x14018fcdf  lea     r9, [rsp+188h+var_98]
0x14018fce7  jnz     short loc_14018FCED
0x14018fce9  mov     r9, [rbx+10h]
0x14018fced  mov     dword ptr [rsp+188h+BugCheckParameter4], edi
0x14018fcf1  mov     r8, [rsi+58h]
0x14018fcf5  mov     edx, [rbx+8]
0x14018fcf8  mov     rbx, [rsp+188h+var_130]
0x14018fcfd  mov     rcx, rbx
0x14018fd00  call    ?xxxCallHook2@@YA_JPEAUtagHOOK@@H_K_JW4CallHookHints@@@Z; xxxCallHook2(tagHOOK *,int,unsigned __int64,__int64,CallHookHints)
0x14018fd05  mov     [rsp+188h+var_128], rax
0x14018fd0a  lea     eax, [r13-0Dh]
0x14018fd0e  cmp     eax, 1
0x14018fd11  ja      short loc_14018FD5E
0x14018fd13  movsd   xmm0, [rsp+188h+var_D8]
0x14018fd1c  movsd   qword ptr [r14+608h], xmm0
0x14018fd25  mov     rax, [rsp+188h+var_110]
0x14018fd2a  mov     [r14+610h], eax
0x14018fd31  movsd   xmm0, qword ptr [rsp+188h+var_C8]
0x14018fd3a  movsd   qword ptr [r14+614h], xmm0
0x14018fd43  mov     rax, [rsp+188h+var_120]
0x14018fd48  mov     [r14+61Ch], eax
0x14018fd4f  mov     rax, [rsp+188h+var_100]
0x14018fd57  mov     [r14+620h], rax
0x14018fd5e  mov     eax, [r12]
0x14018fd62  mov     ecx, 20004h
0x14018fd67  and     eax, ecx
0x14018fd69  cmp     eax, ecx
0x14018fd6b  jnz     loc_14018FE24
0x14018fd71  test    dword ptr [rbx+40h], 2000h
0x14018fd78  jz      loc_14018FE24
0x14018fd7e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
