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
