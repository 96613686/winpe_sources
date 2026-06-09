# xxxSetForegroundWindowWithOptions(tagWND *,ForegroundChangeAllowPolicy,SetForegroundBehaviors,SetForegroundEffects)

- ea: `0x1400ef954`
- end: `0x1400f06c9`
- name: `?xxxSetForegroundWindowWithOptions@@YA_NPEAUtagWND@@W4ForegroundChangeAllowPolicy@@W4SetForegroundBehaviors@@W4SetForegroundEffects@@@Z`
- size: `3445`
- prototype: ``
- caller_count: `17`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400c591c`
- `0x1400ed450`
- `0x1400ef8c0`
- `0x1400f06d0`
- `0x1400f0b20`
- `0x14010a2c0`
- `0x140178b7c`
- `0x140194824`
- `0x1401f4cd0`
- `0x14023b1b8`
- `0x14026e080`
- `0x140274a64`
- `0x140287d64`
- `0x14029b854`
- `0x1402bff10`
- `0x1402c7260`
- `0x1402e780c`

## callees

- `0x140004c3c`
- `0x140008690`
- `0x1400143c0`
- `0x140025930`
- `0x140028660`
- `0x14002bda0`
- `0x14002be7c`
- `0x140085998`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x1400e1ac0`
- `0x1400e3498`
- `0x1400e9a60`
- `0x1400ed244`
- `0x1400eec14`
- `0x1400ef954`
- `0x14017ca14`
- `0x1401fe734`
- `0x14020f7d8`
- `0x140240930`
- `0x140245eb4`
- `0x1402623cc`
- `0x14026e0fc`
- `0x1402913f0`
- `0x1402a89f4`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1400efa1b`
- `ntoskrnl!PsGetThreadId` at `0x1400efa30`
- `ntoskrnl!PsGetThreadId` at `0x1400eff96`
- `ntoskrnl!PsGetThreadId` at `0x1400effab`
- `ntoskrnl!PsGetThreadId` at `0x1400efa1b`
- `ntoskrnl!PsGetThreadId` at `0x1400efa30`
- `ntoskrnl!PsGetThreadId` at `0x1400eff96`
- `ntoskrnl!PsGetThreadId` at `0x1400effab`
- `win32kbase!UPDWORDPointer` at `0x1400f0114`
- `win32kbase!UPDWORDPointer` at `0x1400f0114`
- `WIN32K!W32GetUserSessionState` at `0x1400ef985`
- `WIN32K!W32GetUserSessionState` at `0x1400efa3f`
- `WIN32K!W32GetUserSessionState` at `0x1400efb29`
- `WIN32K!W32GetUserSessionState` at `0x1400efba2`
- `WIN32K!W32GetUserSessionState` at `0x1400efc0c`
- `WIN32K!W32GetUserSessionState` at `0x1400efc9b`
- `WIN32K!W32GetUserSessionState` at `0x1400efd88`
- `WIN32K!W32GetUserSessionState` at `0x1400efe2d`
- `WIN32K!W32GetUserSessionState` at `0x1400efeab`
- `WIN32K!W32GetUserSessionState` at `0x1400effba`
- `WIN32K!W32GetUserSessionState` at `0x1400f004a`
- `WIN32K!W32GetUserSessionState` at `0x1400f01a4`
- `WIN32K!W32GetUserSessionState` at `0x1400f025b`
- `WIN32K!W32GetUserSessionState` at `0x1400f02f9`
- `WIN32K!W32GetUserSessionState` at `0x1400f0389`
- `WIN32K!W32GetUserSessionState` at `0x1400f0452`
- `WIN32K!W32GetUserSessionState` at `0x1400f04f7`
- `WIN32K!W32GetUserSessionState` at `0x1400f058b`
- `WIN32K!W32GetUserSessionState` at `0x1400f0612`
- `WIN32K!W32GetUserSessionState` at `0x1400ef985`
- `WIN32K!W32GetUserSessionState` at `0x1400efa3f`
- `WIN32K!W32GetUserSessionState` at `0x1400efb29`
- `WIN32K!W32GetUserSessionState` at `0x1400efba2`
- `WIN32K!W32GetUserSessionState` at `0x1400efc0c`
- `WIN32K!W32GetUserSessionState` at `0x1400efc9b`
- `WIN32K!W32GetUserSessionState` at `0x1400efd88`
- `WIN32K!W32GetUserSessionState` at `0x1400efe2d`
- `WIN32K!W32GetUserSessionState` at `0x1400efeab`
- `WIN32K!W32GetUserSessionState` at `0x1400effba`
- `WIN32K!W32GetUserSessionState` at `0x1400f004a`
- `WIN32K!W32GetUserSessionState` at `0x1400f01a4`
- `WIN32K!W32GetUserSessionState` at `0x1400f025b`
- `WIN32K!W32GetUserSessionState` at `0x1400f02f9`
- `WIN32K!W32GetUserSessionState` at `0x1400f0389`
- `WIN32K!W32GetUserSessionState` at `0x1400f0452`
- `WIN32K!W32GetUserSessionState` at `0x1400f04f7`
- `WIN32K!W32GetUserSessionState` at `0x1400f058b`
- `WIN32K!W32GetUserSessionState` at `0x1400f0612`

## string_xrefs

- `0x1400efdaa`: `Remove`

## pseudocode

```c
char __fastcall xxxSetForegroundWindowWithOptions(struct tagWND *a1, __int64 a2, __int16 a3, char a4)
{
  char v4; // bp
  struct tagWND *v5; // r14
  char v6; // r13
  ULONG_PTR v7; // rcx
  __int64 v8; // rax
  struct tagTHREADINFO *v9; // rbx
  bool v10; // r15
  bool v11; // r12
  __int64 v12; // rcx
  __int64 UserSessionState; // rax
  int v14; // r8d
  int v15; // edx
  struct tagWND *v16; // rax
  struct MOVESIZEDATA *v17; // rcx
  __int64 v18; // r9
  struct tagWND *v19; // rsi
  bool v20; // r15
  bool v21; // r12
  __int64 v22; // rbx
  __int64 v23; // rdi
  __int64 v24; // rax
  int v25; // r8d
  int v26; // edx
  __int64 v27; // rax
  __int64 v28; // r15
  __int64 v29; // rsi
  bool v30; // bl
  bool v31; // di
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  bool v35; // bl
  bool v36; // di
  __int64 v37; // rax
  int v38; // r8d
  int v39; // edx
  __int64 v40; // r9
  const char *v41; // rax
  char v42; // si
  bool v43; // r15
  int v44; // esi
  __int16 v45; // r12
  bool v46; // di
  bool v47; // si
  __int64 v48; // rax
  int v49; // r8d
  int v50; // edx
  __int64 v51; // r9
  const char *v52; // rax
  bool v53; // bl
  bool v54; // di
  __int64 v55; // rax
  int v56; // r8d
  int v57; // edx
  ULONG_PTR v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 *v62; // rax
  bool v63; // r15
  bool v64; // r12
  char ThreadId; // di
  __int64 v66; // rsi
  char v67; // bl
  __int64 v68; // rcx
  __int64 v69; // rax
  int v70; // r8d
  int v71; // edx
  bool v72; // bl
  bool v73; // di
  __int64 v74; // rax
  int v75; // r8d
  int v76; // edx
  __int64 NonChildAncestor; // rax
  struct tagWND *TopLevelCreatorWindow; // rbx
  __int64 v79; // r9
  struct tagTHREADINFO *v80; // r15
  bool v81; // bl
  bool v82; // di
  __int64 v83; // rax
  int v84; // r8d
  int v85; // edx
  bool v86; // bl
  bool v87; // di
  __int64 v88; // rax
  int v89; // edx
  int v90; // r8d
  bool v91; // bl
  bool v92; // di
  __int64 v93; // rax
  int v94; // r8d
  int v95; // edx
  bool v96; // bl
  bool v97; // di
  __int64 v98; // rax
  int v99; // r8d
  int v100; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  char v102; // dl
  bool v103; // bl
  bool v104; // di
  __int64 v105; // rax
  int v106; // r8d
  int v107; // edx
  bool v108; // bl
  bool v109; // di
  __int64 v110; // rax
  int v111; // r8d
  int v112; // edx
  bool v113; // bl
  bool v114; // di
  __int64 v115; // rax
  int v116; // r8d
  int v117; // edx
  unsigned int v119; // [rsp+20h] [rbp-C8h]
  int v120; // [rsp+28h] [rbp-C0h]
  int v121; // [rsp+30h] [rbp-B8h]
  __int16 v122; // [rsp+30h] [rbp-B8h]
  int v123; // [rsp+38h] [rbp-B0h]
  bool v124; // [rsp+70h] [rbp-78h]
  char v125; // [rsp+71h] [rbp-77h]
  ULONG_PTR v126[2]; // [rsp+78h] [rbp-70h] BYREF
  struct tagTHREADINFO *v127; // [rsp+88h] [rbp-60h]
  ULONG_PTR BugCheckParameter3[11]; // [rsp+90h] [rbp-58h] BYREF
  __int64 v129; // [rsp+F0h] [rbp+8h]
  bool v130; // [rsp+F0h] [rbp+8h]

  v4 = 1;
  v5 = a1;
  v125 = 1;
  v6 = 0;
  v7 = *(_QWORD *)(W32GetUserSessionState(a1) + 18968);
  v8 = *((_QWORD *)v5 + 2);
  v126[0] = v7;
  v129 = *(_QWORD *)(v8 + 464);
  v124 = v129 == v7;
  v9 = PtiCurrent();
  v127 = v9;
  v10 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v11 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v10 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(**((PETHREAD **)v5 + 2));
    PsGetThreadId(*(PETHREAD *)v9);
    UserSessionState = W32GetUserSessionState(v12);
    LOBYTE(v14) = v11;
    LOBYTE(v15) = v10;
    WPP_RECORDER_AND_TRACE_SF_DqDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v15,
      v14,
      *(_QWORD *)(UserSessionState + 69152));
    v9 = v127;
  }
  BugCheckParameter3[1] = 0;
  BugCheckParameter3[0] = -1;
  v16 = _GhostWindowFromHungWindow(v5);
  v19 = v16;
  if ( v16 )
  {
    Win32HM_LockIntoThread<0>(v9, v16, BugCheckParameter3, v18);
    v17 = WPP_GLOBAL_Control;
    v20 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v21 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v20 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v22 = *(_QWORD *)v5;
      v23 = *(_QWORD *)v19;
      v24 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v25) = v21;
      LOBYTE(v26) = v20;
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v26,
        v25,
        *(_QWORD *)(v24 + 69152),
        4,
        2,
        73,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
        v23,
        v22);
      v9 = v127;
    }
    v5 = v19;
  }
  if ( v129 == v126[0] )
  {
    v27 = W32GetUserSessionState(v17);
    v28 = *((_QWORD *)v9 + 58);
    v29 = *(_QWORD *)(v27 + 18968);
    v130 = v29 == v28;
    v30 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v31 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v30 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v32 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v33) = v31;
      LOBYTE(v34) = v30;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v34,
        v33,
        *(_QWORD *)(v32 + 69152),
        4,
        2,
        74,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    v35 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v36 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v35 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v37 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v38) = v36;
      LOBYTE(v39) = v35;
      v40 = *(_QWORD *)(v37 + 69152);
      v41 = "Synchronously";
      if ( v29 != v28 )
        v41 = "Async";
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v39,
        v38,
        v40,
        4,
        2,
        75,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
        (__int64)v41);
    }
    v42 = v124;
    v43 = v130;
LABEL_106:
    v45 = a3;
    goto LABEL_107;
  }
  LODWORD(v126[0]) = anonymous_namespace_::CanSetForegroundWindow(v5);
  v44 = v126[0];
  if ( LODWORD(v126[0]) != 2 )
  {
    v125 = 0;
    v63 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v64 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v63 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      ThreadId = (unsigned __int8)PsGetThreadId(**((PETHREAD **)v5 + 2));
      v66 = *(_QWORD *)v5;
      v67 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)v9);
      v69 = W32GetUserSessionState(v68);
      LOBYTE(v70) = v64;
      LOBYTE(v71) = v63;
      WPP_RECORDER_AND_TRACE_SF_DqD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v71,
        v70,
        *(_QWORD *)(v69 + 69152),
        v119,
        v120,
        v121,
        v123,
        v67,
        v66,
        ThreadId);
      v44 = v126[0];
    }
    if ( (a4 & 1) != 0 )
    {
      v72 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v73 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v72 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v74 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v75) = v73;
        LOBYTE(v76) = v72;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v76,
          v75,
          *(_QWORD *)(v74 + 69152),
          4,
          2,
          79,
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
      }
      NonChildAncestor = GetNonChildAncestor(v5);
      TopLevelCreatorWindow = (struct tagWND *)anonymous_namespace_::DSW_GetTopLevelCreatorWindow(NonChildAncestor);
      if ( !(unsigned __int8)IsTrayWindow(TopLevelCreatorWindow, 1) )
        TopLevelCreatorWindow = v5;
      if ( *(_DWORD *)(*((_QWORD *)TopLevelCreatorWindow + 5) + 236LL) != 15 )
      {
        if ( !(unsigned int)IsImmersiveBandOrShellManaged(TopLevelCreatorWindow) )
        {
          v80 = v127;
          Win32HM_LockIntoThread<0>(v127, TopLevelCreatorWindow, v126, v79);
          UPDWORDPointer(8196);
          xxxFlashWindow(TopLevelCreatorWindow);
          Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v126);
LABEL_95:
          if ( v44 == 1 )
          {
            v42 = v124;
            v43 = 0;
          }
          else
          {
            v42 = 1;
            v43 = *((_QWORD *)v80 + 58) == *(_QWORD *)(*((_QWORD *)v5 + 2) + 464LL);
            v81 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            v82 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v81 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v83 = W32GetUserSessionState(WPP_GLOBAL_Control);
              LOBYTE(v84) = v82;
              LOBYTE(v85) = v81;
              WPP_RECORDER_AND_TRACE_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v85,
                v84,
                *(_QWORD *)(v83 + 69152),
                4,
                2,
                80,
                (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
            }
          }
          goto LABEL_106;
        }
        PostIAMShellHookMessage(0x22u, *(_QWORD *)TopLevelCreatorWindow);
      }
    }
    v80 = v127;
    goto LABEL_95;
  }
  v45 = a3;
  v46 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v47 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v46 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v48 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v49) = v47;
    LOBYTE(v50) = v46;
    v51 = *(_QWORD *)(v48 + 69152);
    v52 = "Remove";
    if ( (a3 & 0x1000) != 0 )
      v52 = "Preserve";
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v50,
      v49,
      v51,
      4,
      2,
      76,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
      (__int64)v52);
  }
  if ( (a3 & 0x1000) == 0 )
    anonymous_namespace_::RemoveForegroundActivate();
  v53 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v54 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v53 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v55 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v56) = v54;
    LOBYTE(v57) = v53;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v57,
      v56,
      *(_QWORD *)(v55 + 69152),
      4,
      2,
      77,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
  }
  v58 = (ULONG_PTR)v127;
  if ( (a3 & 0x400) != 0 )
    v58 = 0;
  if ( (unsigned int)xxxSetForegroundWindow2((ULONG_PTR *)v5, v58, a3 & 0x3FF) )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( *((_QWORD *)v127 + 61) != *(_QWORD *)(W32GetUserSessionState(v59) + 19216) )
    {
      v60 = *((_QWORD *)v5 + 5);
      if ( *(char *)(v60 + 19) >= 0 && *(_DWORD *)(v60 + 236) != 15 && (unsigned int)IsImmersiveBandOrShellManaged(v5) )
      {
        if ( (unsigned int)IAMThreadAccessGranted(v127) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2437);
        v61 = GetNonChildAncestor(v5);
        v62 = (__int64 *)anonymous_namespace_::DSW_GetTopLevelCreatorWindow(v61);
        PostIAMShellHookMessage(0x22u, *v62);
      }
    }
  }
  v42 = v124;
  v43 = 0;
LABEL_107:
  if ( (unsigned int)Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !v42 )
      goto LABEL_179;
    if ( (v45 & 0x400) != 0 )
    {
      v86 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v87 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v86 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v88 = W32GetUserSessionState(WPP_GLOBAL_Control);
        v122 = 81;
LABEL_118:
        LOBYTE(v90) = v87;
        LOBYTE(v89) = v86;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v89,
          v90,
          *(_QWORD *)(v88 + 69152),
          4,
          2,
          v122,
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
        goto LABEL_179;
      }
      goto LABEL_179;
    }
  }
  else if ( !v42 )
  {
    goto LABEL_179;
  }
  v91 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v92 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v91 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v93 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v94) = v92;
    LOBYTE(v95) = v91;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v95,
      v94,
      *(_QWORD *)(v93 + 69152),
      4,
      2,
      82,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
  }
  if ( !v43 )
  {
    if ( v5 != *(struct tagWND **)(*(_QWORD *)(*((_QWORD *)v5 + 2) + 464LL) + 128LL) )
    {
      if ( (*(_BYTE *)(*((_QWORD *)v5 + 5) + 31LL) & 0xC0) == 0x40 )
      {
        v108 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v109 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v108 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v110 = W32GetUserSessionState(WPP_GLOBAL_Control);
          LOBYTE(v111) = v109;
          LOBYTE(v112) = v108;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v112,
            v111,
            *(_QWORD *)(v110 + 69152),
            4,
            2,
            86,
            (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
        }
      }
      v113 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v114 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v113 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v115 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v116) = v114;
        LOBYTE(v117) = v113;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v117,
          v116,
          *(_QWORD *)(v115 + 69152),
          4,
          2,
          87,
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
      }
      v6 = (unsigned int)PostEventMessageEx(
                           *((struct tagTHREADINFO **)v5 + 2),
                           *(struct tagQ **)(*((_QWORD *)v5 + 2) + 464LL),
                           6u,
                           0,
                           0,
                           0,
                           *(_QWORD *)v5,
                           0) != 0;
      goto LABEL_179;
    }
    v103 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v104 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v103 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v105 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v106) = v104;
      LOBYTE(v107) = v103;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v107,
        v106,
        *(_QWORD *)(v105 + 69152),
        4,
        2,
        85,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
LABEL_160:
    v6 = 1;
    goto LABEL_179;
  }
  v96 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v97 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v96 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v98 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v99) = v97;
    LOBYTE(v100) = v96;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v100,
      v99,
      *(_QWORD *)(v98 + 69152),
      4,
      2,
      83,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
  }
  IsEnabledDeviceUsageNoInline = Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline();
  v102 = *(_BYTE *)(*((_QWORD *)v5 + 5) + 31LL) & 0xC0;
  if ( !IsEnabledDeviceUsageNoInline )
  {
    if ( v102 == 64 || !(unsigned __int8)anonymous_namespace_::xxxLocalActivateWindow(v5) )
    {
      v6 = 0;
      goto LABEL_179;
    }
    goto LABEL_160;
  }
  if ( v102 != 64 )
  {
    v6 = anonymous_namespace_::xxxLocalActivateWindow(v5);
    goto LABEL_179;
  }
  v86 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v87 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v86 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v88 = W32GetUserSessionState(WPP_GLOBAL_Control);
    v122 = 84;
    goto LABEL_118;
  }
LABEL_179:
  if ( !v125 || !v6 )
    v4 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  return v4;
}

```

## disassembly

```asm
0x1400ef954  mov     [rsp+arg_18], r9d
0x1400ef959  mov     [rsp+arg_10], r8d
0x1400ef95e  mov     [rsp+arg_8], edx
0x1400ef962  push    rbx
0x1400ef963  push    rbp
0x1400ef964  push    rsi
0x1400ef965  push    rdi
0x1400ef966  push    r12
0x1400ef968  push    r13
0x1400ef96a  push    r14
0x1400ef96c  push    r15
0x1400ef96e  sub     rsp, 0A8h
0x1400ef975  mov     ebp, 1
0x1400ef97a  mov     r14, rcx
0x1400ef97d  mov     [rsp+0E8h+var_77], bpl
0x1400ef982  xor     r13b, r13b
0x1400ef985  call    cs:__imp_W32GetUserSessionState
0x1400ef98c  nop     dword ptr [rax+rax+00h]
0x1400ef991  mov     rcx, [rax+4A18h]
0x1400ef998  mov     rax, [r14+10h]
0x1400ef99c  mov     [rsp+0E8h+var_70], rcx
0x1400ef9a1  mov     rax, [rax+1D0h]
0x1400ef9a8  cmp     rax, rcx
0x1400ef9ab  mov     [rsp+0E8h+arg_0], rax
0x1400ef9b3  setz    [rsp+0E8h+var_78]
0x1400ef9b8  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400ef9bd  mov     rbx, rax
0x1400ef9c0  mov     [rsp+0E8h+var_60], rax
0x1400ef9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ef9cf  lea     rax, WPP_GLOBAL_Control
0x1400ef9d6  lea     edi, [rbp+1]
0x1400ef9d9  cmp     rcx, rax
0x1400ef9dc  jz      short loc_1400EF9F1
0x1400ef9de  mov     eax, [rcx+2Ch]
0x1400ef9e1  test    dil, al
0x1400ef9e4  jz      short loc_1400EF9F1
0x1400ef9e6  cmp     byte ptr [rcx+29h], 4
0x1400ef9ea  jb      short loc_1400EF9F1
0x1400ef9ec  mov     r15b, bpl
0x1400ef9ef  jmp     short loc_1400EF9F4
0x1400ef9f1  xor     r15b, r15b
0x1400ef9f4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ef9fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400efa02  setnz   r12b
0x1400efa06  test    r15b, r15b
0x1400efa09  jnz     short loc_1400EFA14
0x1400efa0b  test    r12b, r12b
0x1400efa0e  jz      loc_1400EFA98
0x1400efa14  mov     rcx, [r14+10h]
0x1400efa18  mov     rcx, [rcx]; Thread
0x1400efa1b  call    cs:__imp_PsGetThreadId
0x1400efa22  nop     dword ptr [rax+rax+00h]
0x1400efa27  mov     rcx, [rbx]; Thread
0x1400efa2a  mov     rdi, rax
0x1400efa2d  mov     rsi, [r14]
0x1400efa30  call    cs:__imp_PsGetThreadId
0x1400efa37  nop     dword ptr [rax+rax+00h]
0x1400efa3c  mov     rbx, rax
0x1400efa3f  call    cs:__imp_W32GetUserSessionState
0x1400efa46  nop     dword ptr [rax+rax+00h]
0x1400efa4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efa52  mov     r8b, r12b
0x1400efa55  mov     dl, r15b
0x1400efa58  mov     r9, [rax+10E20h]
0x1400efa5f  mov     eax, [rsp+0E8h+arg_10]
0x1400efa66  mov     rcx, [rcx+18h]
0x1400efa6a  mov     [rsp+0E8h+var_88], eax
0x1400efa6e  mov     eax, [rsp+0E8h+arg_8]
0x1400efa75  mov     [rsp+0E8h+var_90], eax
0x1400efa79  mov     [rsp+0E8h+var_98], edi
0x1400efa7d  mov     [rsp+0E8h+var_A0], rsi
0x1400efa82  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x1400efa86  call    WPP_RECORDER_AND_TRACE_SF_DqDDD
0x1400efa8b  mov     rbx, [rsp+0E8h+var_60]
0x1400efa93  mov     edi, 2
0x1400efa98  mov     rcx, r14; struct tagWND *
0x1400efa9b  mov     [rsp+0E8h+var_50], 0
0x1400efaa7  mov     [rsp+0E8h+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x1400efab3  call    ?_GhostWindowFromHungWindow@@YAPEAUtagWND@@PEBU1@@Z; _GhostWindowFromHungWindow(tagWND const *)
0x1400efab8  lea     r12, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400efabf  mov     rsi, rax
0x1400efac2  test    rax, rax
0x1400efac5  jz      loc_1400EFB8F
0x1400efacb  lea     r8, [rsp+0E8h+BugCheckParameter3]
0x1400efad3  mov     rdx, rax
0x1400efad6  mov     rcx, rbx
0x1400efad9  call    ??$Win32HM_LockIntoThread@$0A@@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<0>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x1400efade  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efae5  lea     rax, WPP_GLOBAL_Control
0x1400efaec  cmp     rcx, rax
0x1400efaef  jz      short loc_1400EFB04
0x1400efaf1  mov     eax, [rcx+2Ch]
0x1400efaf4  test    dil, al
0x1400efaf7  jz      short loc_1400EFB04
0x1400efaf9  cmp     byte ptr [rcx+29h], 4
0x1400efafd  jb      short loc_1400EFB04
0x1400efaff  mov     r15b, bpl
0x1400efb02  jmp     short loc_1400EFB07
0x1400efb04  xor     r15b, r15b
0x1400efb07  lea     rax, WPP_RECORDER_INITIALIZED
0x1400efb0e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400efb15  setnz   r12b
0x1400efb19  test    r15b, r15b
0x1400efb1c  jnz     short loc_1400EFB23
0x1400efb1e  test    r12b, r12b
0x1400efb21  jz      short loc_1400EFB85
0x1400efb23  mov     rbx, [r14]
0x1400efb26  mov     rdi, [rsi]
0x1400efb29  call    cs:__imp_W32GetUserSessionState
0x1400efb30  nop     dword ptr [rax+rax+00h]
0x1400efb35  mov     [rsp+0E8h+var_A0], rbx
0x1400efb3a  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400efb41  mov     [rsp+0E8h+var_A8], rdi
0x1400efb46  mov     r8b, r12b
0x1400efb49  mov     [rsp+0E8h+var_B0], rcx
0x1400efb4e  mov     edi, 2
0x1400efb53  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efb5a  mov     dl, r15b
0x1400efb5d  mov     r9, [rax+10E20h]
0x1400efb64  mov     word ptr [rsp+0E8h+var_B8], 49h ; 'I'
0x1400efb6b  mov     dword ptr [rsp+0E8h+var_C0], edi
0x1400efb6f  mov     rcx, [rcx+18h]
0x1400efb73  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400efb78  call    WPP_RECORDER_AND_TRACE_SF_qq
0x1400efb7d  mov     rbx, [rsp+0E8h+var_60]
0x1400efb85  mov     r14, rsi
0x1400efb88  lea     r12, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400efb8f  mov     rax, [rsp+0E8h+arg_0]
0x1400efb97  cmp     rax, [rsp+0E8h+var_70]
0x1400efb9c  jnz     loc_1400EFD0C
0x1400efba2  call    cs:__imp_W32GetUserSessionState
0x1400efba9  nop     dword ptr [rax+rax+00h]
0x1400efbae  mov     r15, [rbx+1D0h]
0x1400efbb5  mov     rsi, [rax+4A18h]
0x1400efbbc  cmp     rsi, r15
0x1400efbbf  setz    al
0x1400efbc2  mov     byte ptr [rsp+0E8h+arg_0], al
0x1400efbc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efbd0  lea     rax, WPP_GLOBAL_Control
0x1400efbd7  cmp     rcx, rax
0x1400efbda  jz      short loc_1400EFBEF
0x1400efbdc  mov     eax, [rcx+2Ch]
0x1400efbdf  test    dil, al
0x1400efbe2  jz      short loc_1400EFBEF
0x1400efbe4  cmp     byte ptr [rcx+29h], 4
0x1400efbe8  jb      short loc_1400EFBEF
0x1400efbea  mov     bl, bpl
0x1400efbed  jmp     short loc_1400EFBF1
0x1400efbef  xor     bl, bl
0x1400efbf1  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400efbf8  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400efbff  setnz   dil
0x1400efc03  test    bl, bl
0x1400efc05  jnz     short loc_1400EFC0C
0x1400efc07  test    dil, dil
0x1400efc0a  jz      short loc_1400EFC59
0x1400efc0c  call    cs:__imp_W32GetUserSessionState
0x1400efc13  nop     dword ptr [rax+rax+00h]
0x1400efc18  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efc1f  mov     r8b, dil
0x1400efc22  mov     [rsp+0E8h+var_B0], r12
0x1400efc27  mov     dl, bl
0x1400efc29  mov     word ptr [rsp+0E8h+var_B8], 4Ah ; 'J'
0x1400efc30  mov     r12d, 2
0x1400efc36  mov     r9, [rax+10E20h]
0x1400efc3d  mov     rcx, [rcx+18h]
0x1400efc41  mov     dword ptr [rsp+0E8h+var_C0], r12d
0x1400efc46  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400efc4b  call    WPP_RECORDER_AND_TRACE_SF_
0x1400efc50  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400efc57  jmp     short loc_1400EFC5F
0x1400efc59  mov     r12d, 2
0x1400efc5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efc66  lea     rax, WPP_GLOBAL_Control
0x1400efc6d  cmp     rcx, rax
0x1400efc70  jz      short loc_1400EFC85
0x1400efc72  mov     eax, [rcx+2Ch]
0x1400efc75  test    r12b, al
0x1400efc78  jz      short loc_1400EFC85
0x1400efc7a  cmp     byte ptr [rcx+29h], 4
0x1400efc7e  jb      short loc_1400EFC85
0x1400efc80  mov     bl, bpl
0x1400efc83  jmp     short loc_1400EFC87
0x1400efc85  xor     bl, bl
0x1400efc87  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400efc8e  setnz   dil
0x1400efc92  test    bl, bl
0x1400efc94  jnz     short loc_1400EFC9B
0x1400efc96  test    dil, dil
0x1400efc99  jz      short loc_1400EFCFA
0x1400efc9b  call    cs:__imp_W32GetUserSessionState
0x1400efca2  nop     dword ptr [rax+rax+00h]
0x1400efca7  cmp     rsi, r15
0x1400efcaa  lea     rcx, aAsync_0; "Async"
0x1400efcb1  mov     r8b, dil
0x1400efcb4  mov     dl, bl
0x1400efcb6  mov     r9, [rax+10E20h]
0x1400efcbd  lea     rax, aSynchronously; "Synchronously"
0x1400efcc4  cmovnz  rax, rcx
0x1400efcc8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efccf  mov     [rsp+0E8h+var_A8], rax
0x1400efcd4  lea     rax, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400efcdb  mov     [rsp+0E8h+var_B0], rax
0x1400efce0  mov     word ptr [rsp+0E8h+var_B8], 4Bh ; 'K'
0x1400efce7  mov     rcx, [rcx+18h]
0x1400efceb  mov     dword ptr [rsp+0E8h+var_C0], r12d
0x1400efcf0  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400efcf5  call    WPP_RECORDER_AND_TRACE_SF_s
0x1400efcfa  mov     sil, [rsp+0E8h+var_78]
0x1400efcff  mov     r15b, byte ptr [rsp+0E8h+arg_0]
0x1400efd07  jmp     loc_1400F01EC
0x1400efd0c  mov     edx, [rsp+0E8h+arg_8]
0x1400efd13  xor     al, al
0x1400efd15  mov     rcx, r14; struct tagWND *
0x1400efd18  mov     byte ptr [rsp+0E8h+arg_0], al
0x1400efd1f  call    _anonymous_namespace___CanSetForegroundWindow
0x1400efd24  mov     dword ptr [rsp+0E8h+var_70], eax
0x1400efd28  mov     esi, eax
0x1400efd2a  cmp     eax, edi
0x1400efd2c  jnz     loc_1400EFF45
0x1400efd32  mov     r12d, [rsp+0E8h+arg_10]
0x1400efd3a  mov     ebx, r12d
0x1400efd3d  and     ebx, 1000h
0x1400efd43  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efd4a  lea     r15, WPP_GLOBAL_Control
0x1400efd51  cmp     rcx, r15
0x1400efd54  jz      short loc_1400EFD69
0x1400efd56  mov     eax, [rcx+2Ch]
0x1400efd59  test    dil, al
0x1400efd5c  jz      short loc_1400EFD69
0x1400efd5e  cmp     byte ptr [rcx+29h], 4
0x1400efd62  jb      short loc_1400EFD69
0x1400efd64  mov     dil, bpl
0x1400efd67  jmp     short loc_1400EFD6C
0x1400efd69  xor     dil, dil
0x1400efd6c  lea     r13, WPP_RECORDER_INITIALIZED
0x1400efd73  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400efd7a  setnz   sil
0x1400efd7e  test    dil, dil
0x1400efd81  jnz     short loc_1400EFD88
0x1400efd83  test    sil, sil
0x1400efd86  jz      short loc_1400EFDEA
0x1400efd88  call    cs:__imp_W32GetUserSessionState
0x1400efd8f  nop     dword ptr [rax+rax+00h]
0x1400efd94  test    ebx, ebx
0x1400efd96  lea     rcx, aPreserve; "Preserve"
0x1400efd9d  mov     r8b, sil
0x1400efda0  mov     dl, dil
0x1400efda3  mov     r9, [rax+10E20h]
0x1400efdaa  lea     rax, aRemove; "Remove"
0x1400efdb1  cmovnz  rax, rcx
0x1400efdb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efdbc  mov     [rsp+0E8h+var_A8], rax
0x1400efdc1  lea     rax, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400efdc8  mov     [rsp+0E8h+var_B0], rax
0x1400efdcd  mov     word ptr [rsp+0E8h+var_B8], 4Ch ; 'L'
0x1400efdd4  mov     rcx, [rcx+18h]
0x1400efdd8  mov     dword ptr [rsp+0E8h+var_C0], 2
0x1400efde0  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400efde5  call    WPP_RECORDER_AND_TRACE_SF_s
0x1400efdea  test    ebx, ebx
0x1400efdec  jnz     short loc_1400EFDF3
0x1400efdee  call    _anonymous_namespace___RemoveForegroundActivate
0x1400efdf3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efdfa  mov     esi, 2
0x1400efdff  cmp     rcx, r15
0x1400efe02  jz      short loc_1400EFE17
0x1400efe04  mov     eax, [rcx+2Ch]
0x1400efe07  test    sil, al
0x1400efe0a  jz      short loc_1400EFE17
0x1400efe0c  cmp     byte ptr [rcx+29h], 4
0x1400efe10  jb      short loc_1400EFE17
0x1400efe12  mov     bl, bpl
0x1400efe15  jmp     short loc_1400EFE19
0x1400efe17  xor     bl, bl
0x1400efe19  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400efe20  setnz   dil
0x1400efe24  test    bl, bl
0x1400efe26  jnz     short loc_1400EFE2D
0x1400efe28  test    dil, dil
0x1400efe2b  jz      short loc_1400EFE71
0x1400efe2d  call    cs:__imp_W32GetUserSessionState
0x1400efe34  nop     dword ptr [rax+rax+00h]
0x1400efe39  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400efe40  mov     r8b, dil
0x1400efe43  mov     [rsp+0E8h+var_B0], rcx
0x1400efe48  mov     dl, bl
0x1400efe4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efe51  mov     r9, [rax+10E20h]
0x1400efe58  mov     word ptr [rsp+0E8h+var_B8], 4Dh ; 'M'
0x1400efe5f  mov     dword ptr [rsp+0E8h+var_C0], esi
0x1400efe63  mov     rcx, [rcx+18h]
0x1400efe67  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400efe6c  call    WPP_RECORDER_AND_TRACE_SF_
0x1400efe71  mov     r15, [rsp+0E8h+var_60]
0x1400efe79  mov     eax, 0
0x1400efe7e  mov     r8d, r12d
0x1400efe81  bt      r12d, 0Ah
0x1400efe86  mov     rdx, r15
0x1400efe89  mov     rcx, r14
  ... truncated ...
```
