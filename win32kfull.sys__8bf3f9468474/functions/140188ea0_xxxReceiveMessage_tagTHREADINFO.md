# xxxReceiveMessage(tagTHREADINFO *)

- ea: `0x140188ea0`
- end: `0x140189f72`
- name: `?xxxReceiveMessage@@YAXPEAUtagTHREADINFO@@@Z`
- size: `4306`
- prototype: `void __fastcall(struct tagTHREADINFO *)`
- caller_count: `2`
- callee_count: `104`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400c31e0`
- `0x140188e64`

## callees

- `0x140004cbc`
- `0x14000aa40`
- `0x14000b0f0`
- `0x14001ec90`
- `0x140022384`
- `0x140023c74`
- `0x140023cd0`
- `0x140023e40`
- `0x140023f00`
- `0x1400286dc`
- `0x1400292ec`
- `0x14002b638`
- `0x140033080`
- `0x140033e0c`
- `0x1400a82e0`
- `0x1400aec3c`
- `0x1400af078`
- `0x1400b643c`
- `0x1400b7e20`
- `0x1400b8080`
- `0x1400b82d0`
- `0x1400b8a30`
- `0x1400b90a0`
- `0x1400b9320`
- `0x1400b9610`
- `0x1400b99d0`
- `0x1400b9cd0`
- `0x1400ba1d0`
- `0x1400ba610`
- `0x1400bbb50`
- `0x1400bcaa0`
- `0x1400bcbd0`
- `0x1400bdb20`
- `0x1400be040`
- `0x1400c2a10`
- `0x1400c4270`
- `0x1400c459c`
- `0x1400d28d0`
- `0x1400d2df0`
- `0x1400d2e50`
- `0x1400d2fd0`
- `0x1400d3490`
- `0x1400d42e0`
- `0x1400d43a0`
- `0x1400ec110`
- `0x14010a2c0`
- `0x14010baf0`
- `0x1401450a0`
- `0x140148b90`
- `0x140188ea0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401896c0`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140189723`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401897a0`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401897dc`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401896c0`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140189723`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401897a0`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401897dc`
- `ntoskrnl!KeBugCheckEx` at `0x140189ddf`
- `ntoskrnl!KeBugCheckEx` at `0x140189ddf`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x14018955c`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401895d7`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x14018955c`
- `win32kbase!?IsUIPIInfoValid@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401895d7`
- `win32kbase!EtwTraceBeginRetrieveSendMessage` at `0x140188f59`
- `win32kbase!EtwTraceBeginRetrieveSendMessage` at `0x140188f59`
- `win32kbase!EtwTraceEndRetrieveSendMessage` at `0x140189ee0`
- `win32kbase!EtwTraceEndRetrieveSendMessage` at `0x140189ee0`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x14018975d`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x14018983c`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x14018975d`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x14018983c`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140189717`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140189816`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140189717`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140189816`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x140189582`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401895f9`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x140189582`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401895f9`
- `WIN32K!W32GetUserSessionState` at `0x140189079`
- `WIN32K!W32GetUserSessionState` at `0x1401890e1`
- `WIN32K!W32GetUserSessionState` at `0x1401892f5`
- `WIN32K!W32GetUserSessionState` at `0x140189457`
- `WIN32K!W32GetUserSessionState` at `0x140189b12`
- `WIN32K!W32GetUserSessionState` at `0x140189b2f`
- `WIN32K!W32GetUserSessionState` at `0x140189b3e`
- `WIN32K!W32GetUserSessionState` at `0x140189b5f`
- `WIN32K!W32GetUserSessionState` at `0x140189e88`
- `WIN32K!W32GetUserSessionState` at `0x140189079`
- `WIN32K!W32GetUserSessionState` at `0x1401890e1`
- `WIN32K!W32GetUserSessionState` at `0x1401892f5`
- `WIN32K!W32GetUserSessionState` at `0x140189457`
- `WIN32K!W32GetUserSessionState` at `0x140189b12`
- `WIN32K!W32GetUserSessionState` at `0x140189b2f`
- `WIN32K!W32GetUserSessionState` at `0x140189b3e`
- `WIN32K!W32GetUserSessionState` at `0x140189b5f`
- `WIN32K!W32GetUserSessionState` at `0x140189e88`

## pseudocode

```c
void __fastcall xxxReceiveMessage(struct tagTHREADINFO *a1)
{
  _QWORD *v2; // rax
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  _QWORD *v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
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
  _QWORD *v30; // rbx
  __int64 v31; // r15
  int v32; // r13d
  __int64 v33; // r8
  __int64 v34; // r9
  struct MOVESIZEDATA **v35; // rdx
  __int64 v36; // rax
  int v37; // r8d
  int v38; // edx
  __int64 *v39; // r9
  __int64 v40; // rdx
  struct tagHOOK *v41; // rbx
  __int64 v42; // rdx
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
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // r8
  struct tagWND **v72; // r15
  int v73; // ebx
  int v74; // ecx
  int v75; // ecx
  int v76; // eax
  __int64 v77; // r8
  unsigned int *v78; // rdx
  unsigned int v79; // ecx
  unsigned int *v80; // rdx
  unsigned int v81; // ecx
  __int64 v82; // rax
  struct tagHIDDATA *v83; // rax
  int v84; // ebx
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r9
  ULONG_PTR v89; // rbx
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // r8
  __int64 v93; // r9
  __int64 v94; // rbx
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // r8
  __int64 v98; // r9
  unsigned int v99; // r13d
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  __int64 v103; // rax
  __int64 v104; // rdx
  char v105; // r13
  __int64 v106; // rdx
  int v107; // eax
  __int64 v108; // rcx
  unsigned __int64 v109; // rax
  __int64 v110; // rax
  int v111; // ebx
  struct tagTHREADINFO *v112; // rax
  int v113; // ebx
  struct tagTHREADINFO *v114; // rax
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // r9
  struct tagHOOK *v119; // r14
  char v120; // r15
  bool v121; // r13
  int v122; // ebx
  __int64 UserSessionState; // rax
  int v124; // r8d
  int v125; // edx
  int v126; // ecx
  char v127; // [rsp+50h] [rbp-138h]
  char v128; // [rsp+50h] [rbp-138h]
  bool v129; // [rsp+51h] [rbp-137h]
  bool v130; // [rsp+51h] [rbp-137h]
  int v131; // [rsp+54h] [rbp-134h]
  struct tagHOOK *v132; // [rsp+58h] [rbp-130h]
  __int64 v133; // [rsp+60h] [rbp-128h] BYREF
  _QWORD *v134; // [rsp+68h] [rbp-120h]
  PVOID *v135; // [rsp+70h] [rbp-118h]
  char *v136; // [rsp+78h] [rbp-110h]
  PVOID *v137; // [rsp+80h] [rbp-108h]
  _QWORD *v138; // [rsp+88h] [rbp-100h]
  ULONG_PTR v139[2]; // [rsp+90h] [rbp-F8h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v141; // [rsp+B0h] [rbp-D8h]
  __int128 v142; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 v143; // [rsp+D0h] [rbp-B8h]
  int v144; // [rsp+D8h] [rbp-B0h]
  __int64 v145; // [rsp+E0h] [rbp-A8h]
  __int64 v146[2]; // [rsp+F0h] [rbp-98h] BYREF
  __int128 v147; // [rsp+100h] [rbp-88h]
  __int128 v148; // [rsp+110h] [rbp-78h]
  _BYTE v149[56]; // [rsp+120h] [rbp-68h] BYREF

  v133 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v139);
  v2 = (_QWORD *)*((_QWORD *)a1 + 69);
  if ( v2 == (_QWORD *)((char *)a1 + 552) )
  {
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 8LL), 0xFFFFFFBF);
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 4LL), 0xFFFFFFBF);
    goto LABEL_3;
  }
  --*((_DWORD *)a1 + 142);
  v3 = *v2;
  if ( *(_QWORD **)(*v2 + 8LL) != v2 || (v4 = (_QWORD *)v2[1], (_QWORD *)*v4 != v2) )
    __fastfail(3u);
  v5 = v2 - 2;
  v134 = v2 - 2;
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  *v2 = 0;
  EtwTraceBeginRetrieveSendMessage(v2 - 2);
  v9 = (int *)v5 + 21;
  v136 = (char *)v5 + 84;
  *((_DWORD *)v5 + 21) |= 0x4010u;
  if ( *((struct tagTHREADINFO **)a1 + 69) == (struct tagTHREADINFO *)((char *)a1 + 552) )
  {
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 8LL), 0xFFFFFFBF);
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 4LL), 0xFFFFFFBF);
  }
  v10 = (PVOID *)v5[4];
  v135 = v10;
  v137 = v10;
  if ( v10 )
  {
    v11 = (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x100) != 0;
    v12 = (_QWORD *)*((_QWORD *)a1 + 64);
    if ( v11 )
      *v12 |= 0x1000uLL;
    else
      *v12 &= ~0x1000uLL;
  }
  if ( *((_DWORD *)v5 + 26) == 255 && (*v9 & 0x200) == 0 )
  {
    v13 = PtiCurrent();
    FlushPostedRawInput(v13);
  }
  v14 = *v9;
  if ( (*v9 & 0x200) == 0 )
  {
    if ( (v14 & 7) != 0 )
    {
      if ( (v14 & 0x20004) == 0x20004 )
      {
        LOBYTE(v6) = 5;
        v115 = HMValidateHandleNoSecure(v5[15], v6);
        v119 = (struct tagHOOK *)v115;
        if ( v115 )
        {
          if ( (*(_DWORD *)(v115 + 64) & 0x2000) != 0 )
          {
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (v120 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              v120 = 0;
            }
            v121 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v120 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v122 = *(_DWORD *)(v115 + 48);
              UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v116, v117, v118);
              LOBYTE(v124) = v121;
              LOBYTE(v125) = v120;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v125,
                v124,
                *(_QWORD *)(UserSessionState + 69152),
                4,
                5,
                12,
                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                v122);
            }
            DeBoostHook(v119, v116, v117, v118);
          }
        }
      }
      goto LABEL_158;
    }
    v29 = (_DWORD *)*((_QWORD *)a1 + 60);
    LODWORD(v137) = *v29;
    v145 = *((_QWORD *)a1 + 68);
    *((_QWORD *)a1 + 68) = v5;
    *v29 |= 2u;
    **((_DWORD **)a1 + 60) |= 8u;
    if ( !v10 )
      Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(v139, v5[14]);
    if ( *((_DWORD *)v5 + 26) == 788 )
    {
      *(_OWORD *)v146 = 0;
      v147 = 0;
      *(_QWORD *)&v148 = 0;
      v136 = 0;
      v141 = 0;
      v134 = 0;
      *(_QWORD *)&v142 = 0;
      v30 = (_QWORD *)v5[12];
      v31 = v30[2];
      v32 = *(_DWORD *)(*v30 + 48LL);
      v138 = (_QWORD *)*((_QWORD *)a1 + 196);
      switch ( v32 )
      {
        case 2:
          goto LABEL_41;
        case 7:
          if ( v31 )
          {
            *(_OWORD *)v146 = *(_OWORD *)v31;
            v147 = *(_OWORD *)(v31 + 16);
            *(_QWORD *)&v148 = *(_QWORD *)(v31 + 32);
            CurrentProcessWin32Process = PsGetCurrentProcessWin32Process((unsigned int)(v32 - 7), 2, v7, v8);
            if ( CurrentProcessWin32Process )
              CurrentProcessWin32Process &= -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
            if ( (((unsigned __int16)(*((_DWORD *)v5 + 33) >> 8)
                 ^ (unsigned __int16)(*(_DWORD *)(CurrentProcessWin32Process + 268) >> 8))
                & 0x1FF) != 0 )
            {
              LogicalToPhysicalDPIPoint(v146, v146, *((unsigned int *)v5 + 33), 0);
              v63 = PsGetCurrentProcessWin32Process(v60, v59, v61, v62);
              v64 = v63;
              if ( v63 )
                v64 = -(__int64)(*(_QWORD *)v63 != 0) & v63;
              PhysicalToLogicalDPIPoint(v146, v146, *(unsigned int *)(v64 + 268), 0);
            }
          }
          goto LABEL_42;
        case 10:
          goto LABEL_41;
        case 13:
          InputTraceLogging::Keyboard::ProcessLowLevelHook();
          if ( v31 )
          {
            v146[0] = *(_QWORD *)v31;
            v146[1] = *(_QWORD *)(v31 + 8);
            *(_QWORD *)&v147 = *(_QWORD *)(v31 + 16);
            if ( UIPrivilegeIsolation::IsUIPIInfoValid((UIPrivilegeIsolation *)((char *)v30 + 28), v56)
              && !UIPrivilegeIsolation::CheckAccess(
                    (UIPrivilegeIsolation *)((char *)v30 + 28),
                    (const struct tagUIPI_INFO *)(*((_QWORD *)a1 + 57) + 864LL),
                    v57) )
            {
              LODWORD(v146[1]) |= 2u;
            }
          }
          break;
        case 14:
          InputTraceLogging::Mouse::HandleLowLevelHook();
          if ( v31 )
          {
            v146[0] = *(_QWORD *)v31;
            v146[1] = *(_QWORD *)(v31 + 8);
            v147 = *(_OWORD *)(v31 + 16);
            if ( UIPrivilegeIsolation::IsUIPIInfoValid((UIPrivilegeIsolation *)((char *)v30 + 28), v54)
              && !UIPrivilegeIsolation::CheckAccess(
                    (UIPrivilegeIsolation *)((char *)v30 + 28),
                    (const struct tagUIPI_INFO *)(*((_QWORD *)a1 + 57) + 864LL),
                    v55) )
            {
              HIDWORD(v146[1]) |= 2u;
            }
          }
          break;
        default:
          UserSetLastError(87);
LABEL_41:
          v31 = 0;
LABEL_42:
          v132 = (struct tagHOOK *)*v30;
          Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, a1, *v30);
          if ( (*((_DWORD *)v132 + 16) & 0x2000) != 0 )
          {
            v35 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (LOBYTE(v35) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              LOBYTE(v35) = 0;
            }
            v127 = (char)v35;
            v129 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v35 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v36 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v35, v33, v34);
              LOBYTE(v37) = v129;
              LOBYTE(v38) = v127;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v38,
                v37,
                *(_QWORD *)(v36 + 69152),
                4,
                5,
                10,
                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                v32);
            }
          }
          if ( (*v9 & 4) != 0 )
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4114);
          v39 = v146;
          if ( !v31 )
            v39 = (__int64 *)v30[2];
          v40 = *((unsigned int *)v30 + 2);
          v41 = v132;
          v133 = xxxCallHook2((__int64)v132, v40, v5[11], (__int64)v39, 0);
          if ( (unsigned int)(v32 - 13) <= 1 )
          {
            *((_QWORD *)a1 + 193) = v141;
            *((_DWORD *)a1 + 388) = (_DWORD)v136;
            *(_QWORD *)((char *)a1 + 1556) = v142;
            *((_DWORD *)a1 + 391) = (_DWORD)v134;
            *((_QWORD *)a1 + 196) = v138;
          }
          v45 = 131076;
          if ( (*v9 & 0x20004) == 0x20004 && (*((_DWORD *)v132 + 16) & 0x2000) != 0 )
          {
            v46 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (LOBYTE(v46) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              LOBYTE(v46) = 0;
            }
            v128 = (char)v46;
            v47 = &WPP_RECORDER_INITIALIZED;
            v130 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v46 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v48 = *((_DWORD *)v132 + 12);
              v49 = W32GetUserSessionState(v46, &WPP_RECORDER_INITIALIZED, v43, v44);
              LOBYTE(v50) = v130;
              LOBYTE(v51) = v128;
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
              v41 = v132;
            }
            DeBoostHook(v41, (__int64)v47, v43, v44);
          }
          if ( (*v9 & 5) == 0 && v31 )
          {
            v52 = v32 - 7;
            if ( v52 )
            {
              v53 = v52 - 6;
              if ( v53 )
              {
                if ( v53 == 1 )
                {
                  *(_QWORD *)v31 = v146[0];
                  *(_QWORD *)(v31 + 8) = v146[1];
                  *(_OWORD *)(v31 + 16) = v147;
                }
              }
              else
              {
                *(_QWORD *)v31 = v146[0];
                *(_QWORD *)(v31 + 8) = v146[1];
                *(_QWORD *)(v31 + 16) = v147;
              }
            }
            else
            {
              v65 = PsGetCurrentProcessWin32Process(v45, v42, v43, v44);
              if ( v65 )
              {
                v66 = -(__int64)(*(_QWORD *)v65 != 0);
                v65 &= v66;
              }
              v69 = *(_DWORD *)(v65 + 268) >> 8;
              LOWORD(v69) = (*((_DWORD *)v5 + 33) >> 8) ^ v69;
              if ( (v69 & 0x1FF) != 0 )
              {
                v70 = PsGetCurrentProcessWin32Process(v69, v66, v67, v68);
                v71 = v70;
                if ( v70 )
                  v71 = -(__int64)(*(_QWORD *)v70 != 0) & v70;
                LogicalToPhysicalDPIPoint(v146, v146, *(unsigned int *)(v71 + 268), 0);
                PhysicalToLogicalDPIPoint(v146, v146, *((unsigned int *)v5 + 33), 0);
              }
              *(_OWORD *)v31 = *(_OWORD *)v146;
              *(_OWORD *)(v31 + 16) = v147;
              *(_QWORD *)(v31 + 32) = v148;
            }
          }
          Win32HMThreadLockAlways<tagACCELTABLE>::~Win32HMThreadLockAlways<tagACCELTABLE>(BugCheckParameter3);
          v72 = (struct tagWND **)(v5 + 14);
LABEL_97:
          v10 = v135;
LABEL_98:
          v73 = (unsigned __int8)v137 & 8;
          v74 = *v9;
          if ( (*v9 & 0x101) == 0x100 )
          {
            HIDWORD(v146[0]) = 0;
            v148 = 0;
            v75 = v74 | 1;
            *v9 = v75;
            if ( (v75 & 4) == 0 )
            {
              v76 = 33;
              if ( (v75 & 0x400) != 0 )
                v76 = 289;
              LODWORD(v146[0]) = v76;
              v146[1] = v5[6];
              *(_QWORD *)&v147 = v5[7];
              *((_QWORD *)&v147 + 1) = v133;
              Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, *v72);
              xxxInterSendMsgEx(*v72, *((_DWORD *)v5 + 26), 0, 0, 0, v5[8], (__int64)v146, 1, *v9 & 0x10000);
              Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
            }
          }
          if ( !v10 )
            Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v139);
          v77 = v145;
          *((_QWORD *)a1 + 68) = v145;
          v78 = (unsigned int *)*((_QWORD *)a1 + 60);
          v79 = *v78 | 2;
          if ( !v77 )
            v79 = *v78 & 0xFFFFFFFD;
          *v78 = v79;
          v80 = (unsigned int *)*((_QWORD *)a1 + 60);
          v81 = *v80 | 8;
          if ( !v73 )
            v81 = *v80 & 0xFFFFFFF7;
          *v80 = v81;
          if ( *((_DWORD *)v5 + 26) == 255 )
          {
            LOBYTE(v80) = 18;
            v82 = HMValidateHandleNoSecure(v5[12], v80);
            if ( v82 )
            {
              if ( *(struct tagTHREADINFO **)(v82 + 16) == a1 )
              {
                v83 = UnlinkHidData(a1, (struct tagHIDDATA *)v82, 0);
                if ( v83 )
                  FreeHidData(v83);
              }
              else
              {
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4410);
              }
            }
          }
          goto LABEL_158;
      }
      v141 = *((_QWORD *)a1 + 193);
      LODWORD(v136) = *((_DWORD *)a1 + 388);
      *(_QWORD *)&v142 = *(_QWORD *)((char *)a1 + 1556);
      LODWORD(v134) = *((_DWORD *)a1 + 391);
      *((_QWORD *)a1 + 193) = *(_QWORD *)((char *)v30 + 28);
      *((_DWORD *)a1 + 388) = *((_DWORD *)v30 + 9);
      *(_QWORD *)((char *)a1 + 1556) = v30[5];
      *((_DWORD *)a1 + 391) = *((_DWORD *)v30 + 12);
      *((_QWORD *)a1 + 196) = v146;
      goto LABEL_42;
    }
    v131 = *((_DWORD *)PtiCurrent() + 401);
    v84 = *((_DWORD *)v5 + 32);
    *((_DWORD *)PtiCurrent() + 401) = v84;
    SharedUserCritOnly::DomainShared<DLT_HOOK>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v149);
    v72 = (struct tagWND **)(v5 + 14);
    if ( ShouldCallWndProcHook(a1, 0x20u, *((_DWORD *)v5 + 26), (struct tagWND *)v5[14]) )
    {
      *(_OWORD *)v146 = 0;
      v147 = 0;
      *(_QWORD *)&v148 = 0;
      if ( *v72 )
        *((_QWORD *)&v147 + 1) = *(_QWORD *)*v72;
      LODWORD(v147) = *((_DWORD *)v5 + 26);
      v146[1] = v5[11];
      v146[0] = v5[12];
      *(_QWORD *)&v148 = v5;
      xxxCallHook(0, 1u, (__int64)v146, 4);
    }
    SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v149);
    FreeDelayedHooks();
    if ( (*((_DWORD *)v5 + 21) & 7) != 0 )
      goto LABEL_98;
    v138 = v5 + 14;
    if ( !*v72 )
      goto LABEL_98;
    v89 = 0;
    v134 = *(_QWORD **)*v72;
    v144 = (unsigned __int16)v134;
    v91 = *(_QWORD *)(W32GetUserSessionState(v86, v85, v87, v88) + 19704);
    if ( (unsigned __int64)(unsigned __int16)v134 >= *(_QWORD *)(v91 + 8)
      || (v94 = W32GetUserSessionState(v91, v90, v92, v93),
          v99 = *(_DWORD *)(W32GetUserSessionState(v96, v95, v97, v98) + 19728) * (unsigned __int16)v134,
          v89 = v99 + *(_QWORD *)(v94 + 19720),
          v103 = W32GetUserSessionState(v99, v100, v101, v102),
          v104 = v5[14],
          *(_QWORD *)(*(_QWORD *)(v103 + 19664) + 40LL * (unsigned __int16)v134) != v104)
      || *(_BYTE *)(v89 + 24) != 1 )
    {
      KeBugCheckEx(0x197u, 1u, (ULONG_PTR)*v72, v89, 1u);
    }
    if ( (*(_BYTE *)(*(_QWORD *)(v104 + 40) + 18LL) & 4) == 0 )
    {
      Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, v104);
      v111 = **((_DWORD **)PtiCurrent() + 60);
      v112 = PtiCurrent();
      **((_DWORD **)v112 + 60) |= 0x10u;
      xxxSendMessageToClient(*v72, *((_DWORD *)v5 + 26), v5[11], v5[12], (struct tagSMS *)v5, 1, &v133);
      v113 = (**((_DWORD **)PtiCurrent() + 60) ^ v111) & 0x10;
      v114 = PtiCurrent();
      **((_DWORD **)v114 + 60) ^= v113;
LABEL_139:
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
      SharedUserCritOnly::DomainShared<DLT_HOOK>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v149);
      if ( (*v9 & 4) == 0 && ShouldCallWndProcHook(a1, 0x2000u, *((_DWORD *)v5 + 26), *v72) )
      {
        *(_OWORD *)v146 = 0;
        v147 = 0;
        v148 = 0;
        if ( *v72 )
          *(_QWORD *)&v148 = *(_QWORD *)*v72;
        DWORD2(v147) = *((_DWORD *)v5 + 26);
        *(_QWORD *)&v147 = v5[11];
        v146[1] = v5[12];
        v146[0] = v133;
        *((_QWORD *)&v148 + 1) = v5;
        xxxCallHook(0, 1u, (__int64)v146, 12);
      }
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v149);
      FreeDelayedHooks();
      *((_DWORD *)PtiCurrent() + 401) = v131;
      goto LABEL_97;
    }
    v142 = 0;
    v143 = 0;
    v105 = 0;
    Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, v104);
    v106 = *((unsigned int *)v5 + 26);
    if ( (unsigned int)v106 >= 0x400 )
    {
      v107 = 0;
    }
    else
    {
      if ( !_bittest16(&MessageTable[v106], 9u) && ((_DWORD)v106 != 537 || (v5[11] & 0x8000LL) == 0) )
      {
LABEL_133:
        v108 = v5[14];
        v109 = *(_QWORD *)(*(_QWORD *)(v108 + 40) + 120LL);
        if ( v109 < 4 )
          v110 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))(&gServerHandlers)[v109])(
                   v108,
                   v106,
                   v5[11],
                   v5[12]);
        else
          v110 = 0;
        v133 = v110;
        if ( v105 )
          PopAndFreeW32ThreadLock(&v142);
        goto LABEL_139;
      }
      v107 = 1;
    }
    if ( v107 )
    {
      *((_DWORD *)v5 + 21) |= 0x20u;
      if ( v135 )
      {
        v105 = 1;
        LockKernelStack(*v135, (struct _TL *)&v142);
        v106 = *((unsigned int *)v5 + 26);
      }
    }
    goto LABEL_133;
  }
  if ( !v10 )
    Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(v139, v5[14]);
  if ( (*v9 & 0x400) != 0 )
  {
    v17 = PtiCurrent();
    v18 = (_DWORD *)*((_QWORD *)v17 + 60);
    v19 = *v18 & 8;
    *v18 |= 4u;
    **((_DWORD **)v17 + 60) |= 8u;
    v20 = *((_DWORD *)v5 + 26);
    if ( v20 == 576 || v20 == 281 )
    {
      v22 = (unsigned __int8)MessageTable[(unsigned __int16)v20];
      v23 = gapfnScSendMessage[v22];
      v24 = W32GetUserSessionState(v22, v18, v15, v16);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, _QWORD))v23)(
        v5[14],
        *((unsigned int *)v5 + 26),
        v5[7],
        v5[9],
        v5[6],
        *(_QWORD *)(*(_QWORD *)(v24 + 19704) + 752LL),
        1,
        0);
    }
    else
    {
      v21 = W32GetUserSessionState((unsigned int)(v20 - 576), v18, v15, v16);
      SfnDWORD(v5[14], *((_DWORD *)v5 + 26), v5[7], v5[9], v5[6], *(_QWORD *)(*(_QWORD *)(v21 + 19704) + 752LL));
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
    v27 = (__int64 *)v5[14];
    v28 = 0;
    if ( v27 )
      v28 = *v27;
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))v5[6])(v28, *((unsigned int *)v5 + 26), v5[7], v5[9]);
  }
  if ( !v10 )
    Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v139);
LABEL_158:
  EtwTraceEndRetrieveSendMessage(v5);
  *v9 &= ~0x4000u;
  v126 = *v9;
  if ( (*v9 & 8) != 0 )
  {
    UnlinkSendListSms(v5);
  }
  else if ( (v126 & 1) == 0 )
  {
    v5[9] = v133;
    *v9 = v126 | 1;
    if ( v135 )
      SetWakeBit(v135, 512);
  }
LABEL_3:
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v139);
}

```

## disassembly

```asm
0x140188ea0  mov     [rsp+arg_8], rbx
0x140188ea5  mov     [rsp+arg_10], rsi
0x140188eaa  push    rdi
0x140188eab  push    r12
0x140188ead  push    r13
0x140188eaf  push    r14
0x140188eb1  push    r15
0x140188eb3  sub     rsp, 160h
0x140188eba  mov     rax, cs:__security_cookie
0x140188ec1  xor     rax, rsp
0x140188ec4  mov     [rsp+188h+var_30], rax
0x140188ecc  mov     r14, rcx
0x140188ecf  mov     [rsp+188h+var_130], rcx
0x140188ed4  xor     edi, edi
0x140188ed6  mov     [rsp+188h+var_128], rdi
0x140188edb  lea     rcx, [rsp+188h+var_F8]
0x140188ee3  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x140188ee8  lea     rbx, [r14+228h]
0x140188eef  mov     rax, [rbx]
0x140188ef2  cmp     rax, rbx
0x140188ef5  jnz     short loc_140188F22
0x140188ef7  mov     rax, [r14+1E0h]
0x140188efe  lock and dword ptr [rax+8], 0FFFFFFBFh
0x140188f03  mov     rax, [r14+1E0h]
0x140188f0a  lock and dword ptr [rax+4], 0FFFFFFBFh
0x140188f0f  lea     rcx, [rsp+188h+var_F8]; BugCheckParameter3
0x140188f17  call    ??1?$Win32HMOptionalThreadLock@UtagHOOK@@@@QEAA@XZ; Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(void)
0x140188f1c  jmp     loc_140189F45
0x140188f22  dec     dword ptr [r14+238h]
0x140188f29  mov     rdx, [rax]
0x140188f2c  cmp     [rdx+8], rax
0x140188f30  jnz     loc_140189F3E
0x140188f36  mov     rcx, [rax+8]
0x140188f3a  cmp     [rcx], rax
0x140188f3d  jnz     loc_140189F3E
0x140188f43  lea     rsi, [rax-10h]
0x140188f47  mov     [rsp+188h+var_120], rsi
0x140188f4c  mov     [rcx], rdx
0x140188f4f  mov     [rdx+8], rcx
0x140188f53  mov     [rax], rdi
0x140188f56  mov     rcx, rsi
0x140188f59  call    cs:__imp_EtwTraceBeginRetrieveSendMessage
0x140188f60  nop     dword ptr [rax+rax+00h]
0x140188f65  lea     r12, [rsi+54h]
0x140188f69  mov     [rsp+188h+var_110], r12
0x140188f6e  or      dword ptr [r12], 4010h
0x140188f76  cmp     [rbx], rbx
0x140188f79  jnz     short loc_140188F93
0x140188f7b  mov     rax, [r14+1E0h]
0x140188f82  lock and dword ptr [rax+8], 0FFFFFFBFh
0x140188f87  mov     rax, [r14+1E0h]
0x140188f8e  lock and dword ptr [rax+4], 0FFFFFFBFh
0x140188f93  mov     r13, [rsi+20h]
0x140188f97  mov     [rsp+188h+var_118], r13
0x140188f9c  mov     [rsp+188h+var_108], r13
0x140188fa4  test    r13, r13
0x140188fa7  jz      short loc_140188FED
0x140188fa9  xor     eax, eax
0x140188fab  lock cmpxchg [r13+208h], edi
0x140188fb4  bt      eax, 8
0x140188fb8  mov     rax, [r14+200h]
0x140188fbf  jnb     short loc_140188FC8
0x140188fc1  bts     qword ptr [rax], 0Ch
0x140188fc6  jmp     short loc_140188FCD
0x140188fc8  btr     qword ptr [rax], 0Ch
0x140188fcd  jmp     short loc_140188FED
0x140188fcf  xor     edi, edi
0x140188fd1  mov     r14, [rsp+188h+var_130]
0x140188fd6  mov     rsi, [rsp+188h+var_120]
0x140188fdb  mov     r12, [rsp+188h+var_110]
0x140188fe0  mov     r13, [rsp+188h+var_108]
0x140188fe8  mov     [rsp+188h+var_118], r13
0x140188fed  mov     ebx, 200h
0x140188ff2  cmp     dword ptr [rsi+68h], 0FFh
0x140188ff9  jnz     short loc_14018900E
0x140188ffb  test    [r12], ebx
0x140188fff  jnz     short loc_14018900E
0x140189001  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140189006  mov     rcx, rax; struct tagTHREADINFO *
0x140189009  call    ?FlushPostedRawInput@@YAXPEAUtagTHREADINFO@@@Z; FlushPostedRawInput(tagTHREADINFO *)
0x14018900e  mov     eax, [r12]
0x140189012  test    ebx, eax
0x140189014  jz      loc_140189193
0x14018901a  test    r13, r13
0x14018901d  jnz     short loc_140189030
0x14018901f  mov     rdx, [rsi+70h]
0x140189023  lea     rcx, [rsp+188h+var_F8]
0x14018902b  call    ??$ManualLock@X@?$Win32HMThreadLockBase@UtagMENU@@$00$00@@QEAAXPEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(tagMENU *)
0x140189030  test    dword ptr [r12], 400h
0x140189038  jz      loc_140189152
0x14018903e  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140189043  mov     r14, rax
0x140189046  mov     rdx, [rax+1E0h]
0x14018904d  mov     ecx, [rdx]
0x14018904f  mov     r15d, ecx
0x140189052  and     r15d, 8
0x140189056  or      ecx, 4
0x140189059  mov     [rdx], ecx
0x14018905b  mov     rcx, [rax+1E0h]
0x140189062  or      dword ptr [rcx], 8
0x140189065  mov     eax, [rsi+68h]
0x140189068  lea     ecx, [rax-240h]
0x14018906e  test    ecx, ecx
0x140189070  jz      short loc_1401890C4
0x140189072  cmp     eax, 119h
0x140189077  jz      short loc_1401890C4
0x140189079  call    cs:__imp_W32GetUserSessionState
0x140189080  nop     dword ptr [rax+rax+00h]
0x140189085  mov     rcx, [rax+4CF8h]
0x14018908c  mov     rax, [rcx+2F0h]
0x140189093  mov     qword ptr [rsp+188h+var_150], rdi
0x140189098  mov     dword ptr [rsp+188h+var_158], 1
0x1401890a0  mov     [rsp+188h+var_160], rax
0x1401890a5  mov     rax, [rsi+30h]
0x1401890a9  mov     [rsp+188h+BugCheckParameter4], rax
0x1401890ae  mov     r9, [rsi+48h]
0x1401890b2  mov     r8, [rsi+38h]
0x1401890b6  mov     edx, [rsi+68h]
0x1401890b9  mov     rcx, [rsi+70h]
0x1401890bd  call    SfnDWORD
0x1401890c2  jmp     short loc_14018912D
0x1401890c4  movzx   eax, ax
0x1401890c7  lea     rbx, cs:140000000h
0x1401890ce  movzx   eax, ds:rva MessageTable[rbx+rax*2]
0x1401890d6  movzx   ecx, al
0x1401890d9  mov     rbx, ds:(gapfnScSendMessage - 140000000h)[rbx+rcx*8]
0x1401890e1  call    cs:__imp_W32GetUserSessionState
0x1401890e8  nop     dword ptr [rax+rax+00h]
0x1401890ed  mov     rcx, [rax+4CF8h]
0x1401890f4  mov     rdx, [rcx+2F0h]
0x1401890fb  mov     qword ptr [rsp+188h+var_150], rdi
0x140189100  mov     dword ptr [rsp+188h+var_158], 1
0x140189108  mov     [rsp+188h+var_160], rdx
0x14018910d  mov     rcx, [rsi+30h]
0x140189111  mov     [rsp+188h+BugCheckParameter4], rcx
0x140189116  mov     r9, [rsi+48h]
0x14018911a  mov     r8, [rsi+38h]
0x14018911e  mov     edx, [rsi+68h]
0x140189121  mov     rcx, [rsi+70h]
0x140189125  mov     rax, rbx
0x140189128  call    _guard_dispatch_icall
0x14018912d  mov     rax, [r14+1E0h]
0x140189134  and     dword ptr [rax], 0FFFFFFFBh
0x140189137  mov     rdx, [r14+1E0h]
0x14018913e  mov     ecx, [rdx]
0x140189140  mov     eax, ecx
0x140189142  and     eax, 0FFFFFFF7h
0x140189145  or      ecx, 8
0x140189148  test    r15d, r15d
0x14018914b  cmovz   ecx, eax
0x14018914e  mov     [rdx], ecx
0x140189150  jmp     short loc_140189178
0x140189152  mov     r10, [rsi+30h]
0x140189156  mov     r9, [rsi+48h]
0x14018915a  mov     r8, [rsi+38h]
0x14018915e  mov     edx, [rsi+68h]
0x140189161  mov     rax, [rsi+70h]
0x140189165  test    rax, rax
0x140189168  mov     rcx, rdi
0x14018916b  jz      short loc_140189170
0x14018916d  mov     rcx, [rax]
0x140189170  mov     rax, r10
0x140189173  call    _guard_dispatch_icall
0x140189178  test    r13, r13
0x14018917b  jnz     loc_140189EDD
0x140189181  lea     rcx, [rsp+188h+var_F8]; BugCheckParameter3
0x140189189  call    ??$ManualUnlock@X@?$Win32HMThreadLockBase@UtagCURSOR@@$00$00@@QEAAPEAUtagCURSOR@@XZ; Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(void)
0x14018918e  jmp     loc_140189EDD
0x140189193  test    al, 7
0x140189195  jnz     loc_140189E0F
0x14018919b  mov     rax, [r14+1E0h]
0x1401891a2  mov     ecx, [rax]
0x1401891a4  mov     dword ptr [rsp+188h+var_108], ecx
0x1401891ab  mov     rcx, [r14+220h]
0x1401891b2  mov     [rsp+188h+var_A8], rcx
0x1401891ba  mov     [r14+220h], rsi
0x1401891c1  mov     edx, 2
0x1401891c6  or      [rax], edx
0x1401891c8  mov     rax, [r14+1E0h]
0x1401891cf  or      dword ptr [rax], 8
0x1401891d2  test    r13, r13
0x1401891d5  jnz     short loc_1401891EC
0x1401891d7  mov     rdx, [rsi+70h]
0x1401891db  lea     rcx, [rsp+188h+var_F8]
0x1401891e3  call    ??$ManualLock@X@?$Win32HMThreadLockBase@UtagMENU@@$00$00@@QEAAXPEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(tagMENU *)
0x1401891e8  lea     edx, [r13+2]
0x1401891ec  cmp     dword ptr [rsi+68h], 314h
0x1401891f3  jnz     loc_140189A04
0x1401891f9  xorps   xmm0, xmm0
0x1401891fc  xor     eax, eax
0x1401891fe  movups  xmmword ptr [rsp+188h+var_98], xmm0
0x140189206  movups  [rsp+188h+var_88], xmm0
0x14018920e  mov     qword ptr [rsp+188h+var_78], rax
0x140189216  mov     [rsp+188h+var_110], rax
0x14018921b  mov     [rsp+188h+var_D8], rax
0x140189223  mov     [rsp+188h+var_120], rax
0x140189228  mov     qword ptr [rsp+188h+var_C8], rax
0x140189230  mov     rbx, [rsi+60h]
0x140189234  mov     r15, [rbx+10h]
0x140189238  mov     rax, [rbx]
0x14018923b  mov     r13d, [rax+30h]
0x14018923f  mov     rax, [r14+620h]
0x140189246  mov     [rsp+188h+var_100], rax
0x14018924e  mov     ecx, r13d
0x140189251  sub     ecx, edx
0x140189253  jz      short loc_14018927F
0x140189255  sub     ecx, 5
0x140189258  jz      loc_14018968F
0x14018925e  sub     ecx, 3
0x140189261  jz      short loc_14018927F
0x140189263  sub     ecx, 3
0x140189266  jz      loc_14018959C
0x14018926c  cmp     ecx, 1
0x14018926f  jz      loc_14018951B
0x140189275  mov     ecx, 57h ; 'W'
0x14018927a  call    UserSetLastError
0x14018927f  mov     r15, rdi
0x140189282  mov     rax, [rbx]
0x140189285  mov     [rsp+188h+var_130], rax
0x14018928a  mov     r8, rax
0x14018928d  mov     rdx, r14
0x140189290  lea     rcx, [rsp+188h+BugCheckParameter3]
0x140189298  call    ??0?$Win32HMThreadLockAlways@UtagHOOK@@@@QEAA@PEAUtagTHREADINFO@@PEAUtagHOOK@@@Z; Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(tagTHREADINFO *,tagHOOK *)
0x14018929d  mov     rax, [rsp+188h+var_130]
0x1401892a2  test    dword ptr [rax+40h], 2000h
0x1401892a9  jz      loc_140189346
0x1401892af  lea     rdx, WPP_GLOBAL_Control
0x1401892b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1401892bd  cmp     rcx, rdx
0x1401892c0  jz      short loc_1401892D1
0x1401892c2  mov     eax, [rcx+2Ch]
0x1401892c5  test    al, 10h
0x1401892c7  jz      short loc_1401892D1
0x1401892c9  cmp     byte ptr [rcx+29h], 4
0x1401892cd  mov     dl, 1
0x1401892cf  jnb     short loc_1401892D4
0x1401892d1  mov     dl, dil
0x1401892d4  mov     [rsp+188h+var_138], dl
0x1401892d8  lea     rcx, WPP_RECORDER_INITIALIZED
0x1401892df  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1401892e6  setnz   al
0x1401892e9  mov     [rsp+188h+var_137], al
0x1401892ed  test    dl, dl
0x1401892ef  jnz     short loc_1401892F5
0x1401892f1  test    al, al
0x1401892f3  jz      short loc_140189346
0x1401892f5  call    cs:__imp_W32GetUserSessionState
0x1401892fc  nop     dword ptr [rax+rax+00h]
0x140189301  mov     r9, [rax+10E20h]
0x140189308  mov     [rsp+188h+var_148], r13d
0x14018930d  lea     rax, WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids
0x140189314  mov     qword ptr [rsp+188h+var_150], rax
0x140189319  mov     word ptr [rsp+188h+var_158], 0Ah
0x140189320  mov     dword ptr [rsp+188h+var_160], 5
0x140189328  mov     byte ptr [rsp+188h+BugCheckParameter4], 4
0x14018932d  mov     r8b, [rsp+188h+var_137]
0x140189332  mov     dl, [rsp+188h+var_138]
0x140189336  mov     rcx, cs:WPP_GLOBAL_Control
0x14018933d  mov     rcx, [rcx+18h]
0x140189341  call    WPP_RECORDER_AND_TRACE_SF_D
0x140189346  mov     eax, [r12]
0x14018934a  test    al, 4
0x14018934c  jz      short loc_14018936C
0x14018934e  mov     [rsp+188h+var_134], 20000h
0x140189356  mov     r8d, 1012h
0x14018935c  mov     edx, [rsp+188h+var_134]
0x140189360  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140189367  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14018936c  test    r15, r15
0x14018936f  lea     r9, [rsp+188h+var_98]
0x140189377  jnz     short loc_14018937D
0x140189379  mov     r9, [rbx+10h]
0x14018937d  mov     dword ptr [rsp+188h+BugCheckParameter4], edi
0x140189381  mov     r8, [rsi+58h]
0x140189385  mov     edx, [rbx+8]
0x140189388  mov     rbx, [rsp+188h+var_130]
0x14018938d  mov     rcx, rbx
0x140189390  call    ?xxxCallHook2@@YA_JPEAUtagHOOK@@H_K_JW4CallHookHints@@@Z; xxxCallHook2(tagHOOK *,int,unsigned __int64,__int64,CallHookHints)
0x140189395  mov     [rsp+188h+var_128], rax
0x14018939a  lea     eax, [r13-0Dh]
0x14018939e  cmp     eax, 1
0x1401893a1  ja      short loc_1401893EE
0x1401893a3  movsd   xmm0, [rsp+188h+var_D8]
0x1401893ac  movsd   qword ptr [r14+608h], xmm0
0x1401893b5  mov     rax, [rsp+188h+var_110]
0x1401893ba  mov     [r14+610h], eax
0x1401893c1  movsd   xmm0, qword ptr [rsp+188h+var_C8]
0x1401893ca  movsd   qword ptr [r14+614h], xmm0
0x1401893d3  mov     rax, [rsp+188h+var_120]
0x1401893d8  mov     [r14+61Ch], eax
0x1401893df  mov     rax, [rsp+188h+var_100]
0x1401893e7  mov     [r14+620h], rax
0x1401893ee  mov     eax, [r12]
0x1401893f2  mov     ecx, 20004h
0x1401893f7  and     eax, ecx
0x1401893f9  cmp     eax, ecx
0x1401893fb  jnz     loc_1401894B4
0x140189401  test    dword ptr [rbx+40h], 2000h
0x140189408  jz      loc_1401894B4
0x14018940e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
