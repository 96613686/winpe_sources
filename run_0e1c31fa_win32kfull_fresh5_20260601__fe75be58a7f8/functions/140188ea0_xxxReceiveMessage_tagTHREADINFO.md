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
  int *v7; // r12
  PVOID *v8; // r13
  bool v9; // cf
  _QWORD *v10; // rax
  struct tagTHREADINFO *v11; // rax
  int v12; // eax
  struct tagTHREADINFO *v13; // r14
  _DWORD *v14; // rdx
  int v15; // r15d
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(int, int, int, int, __int64, __int64); // rbx
  __int64 v20; // rax
  unsigned int *v21; // rdx
  unsigned int v22; // ecx
  __int64 *v23; // rax
  __int64 v24; // rcx
  _DWORD *v25; // rax
  _QWORD *v26; // rbx
  __int64 v27; // r15
  int v28; // r13d
  char v29; // dl
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  __int64 *v33; // r9
  unsigned int v34; // edx
  struct tagHOOK *v35; // rbx
  __int64 v36; // rcx
  struct MOVESIZEDATA *v37; // rcx
  int v38; // ebx
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  int v42; // r13d
  int v43; // r13d
  const struct tagUIPI_INFO *v44; // rdx
  const struct tagUIPI_INFO *v45; // r8
  const struct tagUIPI_INFO *v46; // rdx
  const struct tagUIPI_INFO *v47; // r8
  __int64 CurrentProcessWin32Process; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // r8
  struct tagWND **v56; // r15
  int v57; // ebx
  int v58; // ecx
  int v59; // ecx
  int v60; // eax
  __int64 v61; // r8
  unsigned int *v62; // rdx
  unsigned int v63; // ecx
  unsigned int *v64; // rdx
  unsigned int v65; // ecx
  __int64 v66; // rax
  struct tagHIDDATA *v67; // rax
  int v68; // ebx
  __int64 v69; // rcx
  ULONG_PTR v70; // rbx
  __int64 v71; // rcx
  __int64 v72; // rbx
  __int64 v73; // rcx
  unsigned int v74; // r13d
  __int64 v75; // rax
  __int64 v76; // rdx
  char v77; // r13
  __int64 v78; // rdx
  int v79; // eax
  __int64 v80; // rcx
  unsigned __int64 v81; // rax
  __int64 v82; // rax
  int v83; // ebx
  struct tagTHREADINFO *v84; // rax
  int v85; // ebx
  struct tagTHREADINFO *v86; // rax
  __int64 v87; // rax
  struct tagHOOK *v88; // r14
  char v89; // r15
  bool v90; // r13
  int v91; // ebx
  __int64 UserSessionState; // rax
  int v93; // r8d
  int v94; // edx
  int v95; // ecx
  char v96; // [rsp+50h] [rbp-138h]
  char v97; // [rsp+50h] [rbp-138h]
  bool v98; // [rsp+51h] [rbp-137h]
  bool v99; // [rsp+51h] [rbp-137h]
  int v100; // [rsp+54h] [rbp-134h]
  struct tagHOOK *v101; // [rsp+58h] [rbp-130h]
  __int64 v102; // [rsp+60h] [rbp-128h] BYREF
  _QWORD *v103; // [rsp+68h] [rbp-120h]
  PVOID *v104; // [rsp+70h] [rbp-118h]
  char *v105; // [rsp+78h] [rbp-110h]
  PVOID *v106; // [rsp+80h] [rbp-108h]
  _QWORD *v107; // [rsp+88h] [rbp-100h]
  ULONG_PTR v108[2]; // [rsp+90h] [rbp-F8h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v110; // [rsp+B0h] [rbp-D8h]
  __int128 v111; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 v112; // [rsp+D0h] [rbp-B8h]
  int v113; // [rsp+D8h] [rbp-B0h]
  __int64 v114; // [rsp+E0h] [rbp-A8h]
  __int64 v115[2]; // [rsp+F0h] [rbp-98h] BYREF
  __int128 v116; // [rsp+100h] [rbp-88h]
  __int128 v117; // [rsp+110h] [rbp-78h]
  _BYTE v118[56]; // [rsp+120h] [rbp-68h] BYREF

  v102 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v108);
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
  v103 = v2 - 2;
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  *v2 = 0;
  EtwTraceBeginRetrieveSendMessage(v2 - 2);
  v7 = (int *)v5 + 21;
  v105 = (char *)v5 + 84;
  *((_DWORD *)v5 + 21) |= 0x4010u;
  if ( *((struct tagTHREADINFO **)a1 + 69) == (struct tagTHREADINFO *)((char *)a1 + 552) )
  {
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 8LL), 0xFFFFFFBF);
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)a1 + 60) + 4LL), 0xFFFFFFBF);
  }
  v8 = (PVOID *)v5[4];
  v104 = v8;
  v106 = v8;
  if ( v8 )
  {
    v9 = (_InterlockedCompareExchange((volatile signed __int32 *)v8 + 130, 0, 0) & 0x100) != 0;
    v10 = (_QWORD *)*((_QWORD *)a1 + 64);
    if ( v9 )
      *v10 |= 0x1000uLL;
    else
      *v10 &= ~0x1000uLL;
  }
  if ( *((_DWORD *)v5 + 26) == 255 && (*v7 & 0x200) == 0 )
  {
    v11 = PtiCurrent();
    FlushPostedRawInput(v11);
  }
  v12 = *v7;
  if ( (*v7 & 0x200) == 0 )
  {
    if ( (v12 & 7) != 0 )
    {
      if ( (v12 & 0x20004) == 0x20004 )
      {
        LOBYTE(v6) = 5;
        v87 = HMValidateHandleNoSecure(v5[15], v6);
        v88 = (struct tagHOOK *)v87;
        if ( v87 )
        {
          if ( (*(_DWORD *)(v87 + 64) & 0x2000) != 0 )
          {
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (v89 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              v89 = 0;
            }
            v90 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v89 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v91 = *(_DWORD *)(v87 + 48);
              UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
              LOBYTE(v93) = v90;
              LOBYTE(v94) = v89;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v94,
                v93,
                *(_QWORD *)(UserSessionState + 69152),
                4,
                5,
                12,
                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                v91);
            }
            DeBoostHook(v88);
          }
        }
      }
      goto LABEL_158;
    }
    v25 = (_DWORD *)*((_QWORD *)a1 + 60);
    LODWORD(v106) = *v25;
    v114 = *((_QWORD *)a1 + 68);
    *((_QWORD *)a1 + 68) = v5;
    *v25 |= 2u;
    **((_DWORD **)a1 + 60) |= 8u;
    if ( !v8 )
      Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(v108, v5[14]);
    if ( *((_DWORD *)v5 + 26) == 788 )
    {
      *(_OWORD *)v115 = 0;
      v116 = 0;
      *(_QWORD *)&v117 = 0;
      v105 = 0;
      v110 = 0;
      v103 = 0;
      *(_QWORD *)&v111 = 0;
      v26 = (_QWORD *)v5[12];
      v27 = v26[2];
      v28 = *(_DWORD *)(*v26 + 48LL);
      v107 = (_QWORD *)*((_QWORD *)a1 + 196);
      switch ( v28 )
      {
        case 2:
          goto LABEL_41;
        case 7:
          if ( v27 )
          {
            *(_OWORD *)v115 = *(_OWORD *)v27;
            v116 = *(_OWORD *)(v27 + 16);
            *(_QWORD *)&v117 = *(_QWORD *)(v27 + 32);
            CurrentProcessWin32Process = PsGetCurrentProcessWin32Process((unsigned int)(v28 - 7));
            if ( CurrentProcessWin32Process )
              CurrentProcessWin32Process &= -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
            if ( (((unsigned __int16)(*((_DWORD *)v5 + 33) >> 8)
                 ^ (unsigned __int16)(*(_DWORD *)(CurrentProcessWin32Process + 268) >> 8))
                & 0x1FF) != 0 )
            {
              LogicalToPhysicalDPIPoint(v115, v115, *((unsigned int *)v5 + 33), 0);
              v50 = PsGetCurrentProcessWin32Process(v49);
              v51 = v50;
              if ( v50 )
                v51 = -(__int64)(*(_QWORD *)v50 != 0) & v50;
              PhysicalToLogicalDPIPoint(v115, v115, *(unsigned int *)(v51 + 268), 0);
            }
          }
          goto LABEL_42;
        case 10:
          goto LABEL_41;
        case 13:
          InputTraceLogging::Keyboard::ProcessLowLevelHook();
          if ( v27 )
          {
            v115[0] = *(_QWORD *)v27;
            v115[1] = *(_QWORD *)(v27 + 8);
            *(_QWORD *)&v116 = *(_QWORD *)(v27 + 16);
            if ( UIPrivilegeIsolation::IsUIPIInfoValid((UIPrivilegeIsolation *)((char *)v26 + 28), v46)
              && !UIPrivilegeIsolation::CheckAccess(
                    (UIPrivilegeIsolation *)((char *)v26 + 28),
                    (const struct tagUIPI_INFO *)(*((_QWORD *)a1 + 57) + 864LL),
                    v47) )
            {
              LODWORD(v115[1]) |= 2u;
            }
          }
          break;
        case 14:
          InputTraceLogging::Mouse::HandleLowLevelHook();
          if ( v27 )
          {
            v115[0] = *(_QWORD *)v27;
            v115[1] = *(_QWORD *)(v27 + 8);
            v116 = *(_OWORD *)(v27 + 16);
            if ( UIPrivilegeIsolation::IsUIPIInfoValid((UIPrivilegeIsolation *)((char *)v26 + 28), v44)
              && !UIPrivilegeIsolation::CheckAccess(
                    (UIPrivilegeIsolation *)((char *)v26 + 28),
                    (const struct tagUIPI_INFO *)(*((_QWORD *)a1 + 57) + 864LL),
                    v45) )
            {
              HIDWORD(v115[1]) |= 2u;
            }
          }
          break;
        default:
          UserSetLastError(87);
LABEL_41:
          v27 = 0;
LABEL_42:
          v101 = (struct tagHOOK *)*v26;
          Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, a1, *v26);
          if ( (*((_DWORD *)v101 + 16) & 0x2000) != 0 )
          {
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (v29 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              v29 = 0;
            }
            v96 = v29;
            v98 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v29 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v30 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
              LOBYTE(v31) = v98;
              LOBYTE(v32) = v96;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v32,
                v31,
                *(_QWORD *)(v30 + 69152),
                4,
                5,
                10,
                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                v28);
            }
          }
          if ( (*v7 & 4) != 0 )
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4114);
          v33 = v115;
          if ( !v27 )
            v33 = (__int64 *)v26[2];
          v34 = *((_DWORD *)v26 + 2);
          v35 = v101;
          v102 = xxxCallHook2((__int64)v101, v34, v5[11], (__int64)v33, 0);
          if ( (unsigned int)(v28 - 13) <= 1 )
          {
            *((_QWORD *)a1 + 193) = v110;
            *((_DWORD *)a1 + 388) = (_DWORD)v105;
            *(_QWORD *)((char *)a1 + 1556) = v111;
            *((_DWORD *)a1 + 391) = (_DWORD)v103;
            *((_QWORD *)a1 + 196) = v107;
          }
          v36 = 131076;
          if ( (*v7 & 0x20004) == 0x20004 && (*((_DWORD *)v101 + 16) & 0x2000) != 0 )
          {
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || (LOBYTE(v37) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
            {
              LOBYTE(v37) = 0;
            }
            v97 = (char)v37;
            v99 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v37 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v38 = *((_DWORD *)v101 + 12);
              v39 = W32GetUserSessionState(v37);
              LOBYTE(v40) = v99;
              LOBYTE(v41) = v97;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v41,
                v40,
                *(_QWORD *)(v39 + 69152),
                4,
                5,
                11,
                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                v38);
              v35 = v101;
            }
            DeBoostHook(v35);
          }
          if ( (*v7 & 5) == 0 && v27 )
          {
            v42 = v28 - 7;
            if ( v42 )
            {
              v43 = v42 - 6;
              if ( v43 )
              {
                if ( v43 == 1 )
                {
                  *(_QWORD *)v27 = v115[0];
                  *(_QWORD *)(v27 + 8) = v115[1];
                  *(_OWORD *)(v27 + 16) = v116;
                }
              }
              else
              {
                *(_QWORD *)v27 = v115[0];
                *(_QWORD *)(v27 + 8) = v115[1];
                *(_QWORD *)(v27 + 16) = v116;
              }
            }
            else
            {
              v52 = PsGetCurrentProcessWin32Process(v36);
              if ( v52 )
                v52 &= -(__int64)(*(_QWORD *)v52 != 0);
              v53 = *(_DWORD *)(v52 + 268) >> 8;
              LOWORD(v53) = (*((_DWORD *)v5 + 33) >> 8) ^ v53;
              if ( (v53 & 0x1FF) != 0 )
              {
                v54 = PsGetCurrentProcessWin32Process(v53);
                v55 = v54;
                if ( v54 )
                  v55 = -(__int64)(*(_QWORD *)v54 != 0) & v54;
                LogicalToPhysicalDPIPoint(v115, v115, *(unsigned int *)(v55 + 268), 0);
                PhysicalToLogicalDPIPoint(v115, v115, *((unsigned int *)v5 + 33), 0);
              }
              *(_OWORD *)v27 = *(_OWORD *)v115;
              *(_OWORD *)(v27 + 16) = v116;
              *(_QWORD *)(v27 + 32) = v117;
            }
          }
          Win32HMThreadLockAlways<tagACCELTABLE>::~Win32HMThreadLockAlways<tagACCELTABLE>(BugCheckParameter3);
          v56 = (struct tagWND **)(v5 + 14);
LABEL_97:
          v8 = v104;
LABEL_98:
          v57 = (unsigned __int8)v106 & 8;
          v58 = *v7;
          if ( (*v7 & 0x101) == 0x100 )
          {
            HIDWORD(v115[0]) = 0;
            v117 = 0;
            v59 = v58 | 1;
            *v7 = v59;
            if ( (v59 & 4) == 0 )
            {
              v60 = 33;
              if ( (v59 & 0x400) != 0 )
                v60 = 289;
              LODWORD(v115[0]) = v60;
              v115[1] = v5[6];
              *(_QWORD *)&v116 = v5[7];
              *((_QWORD *)&v116 + 1) = v102;
              Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3);
              xxxInterSendMsgEx(*v56, *((_DWORD *)v5 + 26), 0, 0, 0, v5[8], (__int64)v115, 1, *v7 & 0x10000);
              Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
            }
          }
          if ( !v8 )
            Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v108);
          v61 = v114;
          *((_QWORD *)a1 + 68) = v114;
          v62 = (unsigned int *)*((_QWORD *)a1 + 60);
          v63 = *v62 | 2;
          if ( !v61 )
            v63 = *v62 & 0xFFFFFFFD;
          *v62 = v63;
          v64 = (unsigned int *)*((_QWORD *)a1 + 60);
          v65 = *v64 | 8;
          if ( !v57 )
            v65 = *v64 & 0xFFFFFFF7;
          *v64 = v65;
          if ( *((_DWORD *)v5 + 26) == 255 )
          {
            LOBYTE(v64) = 18;
            v66 = HMValidateHandleNoSecure(v5[12], v64);
            if ( v66 )
            {
              if ( *(struct tagTHREADINFO **)(v66 + 16) == a1 )
              {
                v67 = UnlinkHidData(a1, (struct tagHIDDATA *)v66, 0);
                if ( v67 )
                  FreeHidData(v67);
              }
              else
              {
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4410);
              }
            }
          }
          goto LABEL_158;
      }
      v110 = *((_QWORD *)a1 + 193);
      LODWORD(v105) = *((_DWORD *)a1 + 388);
      *(_QWORD *)&v111 = *(_QWORD *)((char *)a1 + 1556);
      LODWORD(v103) = *((_DWORD *)a1 + 391);
      *((_QWORD *)a1 + 193) = *(_QWORD *)((char *)v26 + 28);
      *((_DWORD *)a1 + 388) = *((_DWORD *)v26 + 9);
      *(_QWORD *)((char *)a1 + 1556) = v26[5];
      *((_DWORD *)a1 + 391) = *((_DWORD *)v26 + 12);
      *((_QWORD *)a1 + 196) = v115;
      goto LABEL_42;
    }
    v100 = *((_DWORD *)PtiCurrent() + 401);
    v68 = *((_DWORD *)v5 + 32);
    *((_DWORD *)PtiCurrent() + 401) = v68;
    SharedUserCritOnly::DomainShared<DLT_HOOK>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v118);
    v56 = (struct tagWND **)(v5 + 14);
    if ( ShouldCallWndProcHook(a1, 0x20u, *((_DWORD *)v5 + 26), (struct tagWND *)v5[14]) )
    {
      *(_OWORD *)v115 = 0;
      v116 = 0;
      *(_QWORD *)&v117 = 0;
      if ( *v56 )
        *((_QWORD *)&v116 + 1) = *(_QWORD *)*v56;
      LODWORD(v116) = *((_DWORD *)v5 + 26);
      v115[1] = v5[11];
      v115[0] = v5[12];
      *(_QWORD *)&v117 = v5;
      xxxCallHook(0, 1, (__int64)v115, 4);
    }
    SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v118);
    FreeDelayedHooks();
    if ( (*((_DWORD *)v5 + 21) & 7) != 0 )
      goto LABEL_98;
    v107 = v5 + 14;
    if ( !*v56 )
      goto LABEL_98;
    v70 = 0;
    v103 = *(_QWORD **)*v56;
    v113 = (unsigned __int16)v103;
    v71 = *(_QWORD *)(W32GetUserSessionState(v69) + 19704);
    if ( (unsigned __int64)(unsigned __int16)v103 >= *(_QWORD *)(v71 + 8)
      || (v72 = W32GetUserSessionState(v71),
          v74 = *(_DWORD *)(W32GetUserSessionState(v73) + 19728) * (unsigned __int16)v103,
          v70 = v74 + *(_QWORD *)(v72 + 19720),
          v75 = W32GetUserSessionState(v74),
          v76 = v5[14],
          *(_QWORD *)(*(_QWORD *)(v75 + 19664) + 40LL * (unsigned __int16)v103) != v76)
      || *(_BYTE *)(v70 + 24) != 1 )
    {
      KeBugCheckEx(0x197u, 1u, (ULONG_PTR)*v56, v70, 1u);
    }
    if ( (*(_BYTE *)(*(_QWORD *)(v76 + 40) + 18LL) & 4) == 0 )
    {
      Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3);
      v83 = **((_DWORD **)PtiCurrent() + 60);
      v84 = PtiCurrent();
      **((_DWORD **)v84 + 60) |= 0x10u;
      xxxSendMessageToClient(*v56, *((_DWORD *)v5 + 26), v5[11], v5[12], (struct tagSMS *)v5, 1, &v102);
      v85 = (**((_DWORD **)PtiCurrent() + 60) ^ v83) & 0x10;
      v86 = PtiCurrent();
      **((_DWORD **)v86 + 60) ^= v85;
LABEL_139:
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
      SharedUserCritOnly::DomainShared<DLT_HOOK>::DomainExclusive<>::ObjectLock<>::ObjectLock<>(v118);
      if ( (*v7 & 4) == 0 && ShouldCallWndProcHook(a1, 0x2000u, *((_DWORD *)v5 + 26), *v56) )
      {
        *(_OWORD *)v115 = 0;
        v116 = 0;
        v117 = 0;
        if ( *v56 )
          *(_QWORD *)&v117 = *(_QWORD *)*v56;
        DWORD2(v116) = *((_DWORD *)v5 + 26);
        *(_QWORD *)&v116 = v5[11];
        v115[1] = v5[12];
        v115[0] = v102;
        *((_QWORD *)&v117 + 1) = v5;
        xxxCallHook(0, 1, (__int64)v115, 12);
      }
      SharedUserCritOnly::DomainShared<>::DomainExclusive<DLT_HANDLEMANAGER>::ObjectLock<>::~ObjectLock<>(v118);
      FreeDelayedHooks();
      *((_DWORD *)PtiCurrent() + 401) = v100;
      goto LABEL_97;
    }
    v111 = 0;
    v112 = 0;
    v77 = 0;
    Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3);
    v78 = *((unsigned int *)v5 + 26);
    if ( (unsigned int)v78 >= 0x400 )
    {
      v79 = 0;
    }
    else
    {
      if ( !_bittest16(&MessageTable[v78], 9u) && ((_DWORD)v78 != 537 || (v5[11] & 0x8000LL) == 0) )
      {
LABEL_133:
        v80 = v5[14];
        v81 = *(_QWORD *)(*(_QWORD *)(v80 + 40) + 120LL);
        if ( v81 < 4 )
          v82 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))(&gServerHandlers)[v81])(
                  v80,
                  v78,
                  v5[11],
                  v5[12]);
        else
          v82 = 0;
        v102 = v82;
        if ( v77 )
          PopAndFreeW32ThreadLock(&v111);
        goto LABEL_139;
      }
      v79 = 1;
    }
    if ( v79 )
    {
      *((_DWORD *)v5 + 21) |= 0x20u;
      if ( v104 )
      {
        v77 = 1;
        LockKernelStack(*v104, (struct _TL *)&v111);
        v78 = *((unsigned int *)v5 + 26);
      }
    }
    goto LABEL_133;
  }
  if ( !v8 )
    Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(v108, v5[14]);
  if ( (*v7 & 0x400) != 0 )
  {
    v13 = PtiCurrent();
    v14 = (_DWORD *)*((_QWORD *)v13 + 60);
    v15 = *v14 & 8;
    *v14 |= 4u;
    **((_DWORD **)v13 + 60) |= 8u;
    v16 = *((_DWORD *)v5 + 26);
    if ( v16 == 576 || v16 == 281 )
    {
      v18 = (unsigned __int8)MessageTable[(unsigned __int16)v16];
      v19 = gapfnScSendMessage[v18];
      v20 = W32GetUserSessionState(v18);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, _QWORD))v19)(
        v5[14],
        *((unsigned int *)v5 + 26),
        v5[7],
        v5[9],
        v5[6],
        *(_QWORD *)(*(_QWORD *)(v20 + 19704) + 752LL),
        1,
        0);
    }
    else
    {
      v17 = W32GetUserSessionState((unsigned int)(v16 - 576));
      SfnDWORD(v5[14], *((_DWORD *)v5 + 26), v5[7], v5[9], v5[6], *(_QWORD *)(*(_QWORD *)(v17 + 19704) + 752LL));
    }
    **((_DWORD **)v13 + 60) &= ~4u;
    v21 = (unsigned int *)*((_QWORD *)v13 + 60);
    v22 = *v21 | 8;
    if ( !v15 )
      v22 = *v21 & 0xFFFFFFF7;
    *v21 = v22;
  }
  else
  {
    v23 = (__int64 *)v5[14];
    v24 = 0;
    if ( v23 )
      v24 = *v23;
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))v5[6])(v24, *((unsigned int *)v5 + 26), v5[7], v5[9]);
  }
  if ( !v8 )
    Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v108);
LABEL_158:
  EtwTraceEndRetrieveSendMessage(v5);
  *v7 &= ~0x4000u;
  v95 = *v7;
  if ( (*v7 & 8) != 0 )
  {
    UnlinkSendListSms(v5);
  }
  else if ( (v95 & 1) == 0 )
  {
    v5[9] = v102;
    *v7 = v95 | 1;
    if ( v104 )
      SetWakeBit(v104, 512);
  }
LABEL_3:
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v108);
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
