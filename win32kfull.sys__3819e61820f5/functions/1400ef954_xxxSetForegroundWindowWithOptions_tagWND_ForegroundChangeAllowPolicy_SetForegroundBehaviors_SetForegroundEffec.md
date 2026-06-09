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
char __fastcall xxxSetForegroundWindowWithOptions(struct tagWND *a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // bp
  struct tagWND *v5; // r14
  char v6; // r13
  ULONG_PTR v7; // rcx
  __int64 v8; // rax
  struct tagTHREADINFO *v9; // rbx
  bool v10; // r15
  bool v11; // r12
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 UserSessionState; // rax
  int v17; // r8d
  int v18; // edx
  struct tagWND *v19; // rax
  __int64 v20; // rdx
  struct MOVESIZEDATA *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  struct tagWND *v24; // rsi
  bool v25; // r15
  bool v26; // r12
  __int64 v27; // rbx
  __int64 v28; // rdi
  __int64 v29; // rax
  int v30; // r8d
  int v31; // edx
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r15
  __int64 v36; // rsi
  bool v37; // bl
  bool v38; // di
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  bool v42; // bl
  bool v43; // di
  __int64 v44; // rax
  int v45; // r8d
  int v46; // edx
  __int64 v47; // r9
  const char *v48; // rax
  char v49; // si
  bool v50; // r15
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  int v54; // esi
  __int16 v55; // r12
  bool v56; // di
  bool v57; // si
  __int64 v58; // rax
  int v59; // r8d
  int v60; // edx
  __int64 v61; // r9
  const char *v62; // rax
  bool v63; // bl
  bool v64; // di
  __int64 v65; // rax
  int v66; // r8d
  int v67; // edx
  ULONG_PTR v68; // rdx
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 *v75; // rax
  struct MOVESIZEDATA **v76; // rdx
  bool v77; // r15
  unsigned int *v78; // r8
  bool v79; // r12
  char ThreadId; // di
  __int64 v81; // rsi
  char v82; // bl
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // rax
  int v88; // r8d
  int v89; // edx
  bool v90; // bl
  bool v91; // di
  __int64 v92; // rax
  int v93; // r8d
  int v94; // edx
  __int64 NonChildAncestor; // rax
  struct tagWND *TopLevelCreatorWindow; // rbx
  struct tagTHREADINFO *v97; // r15
  bool v98; // bl
  bool v99; // di
  __int64 v100; // rax
  int v101; // r8d
  int v102; // edx
  __int64 v103; // rdx
  __int64 v104; // r8
  __int64 v105; // r9
  bool v106; // bl
  bool v107; // di
  __int64 v108; // rax
  int v109; // edx
  int v110; // r8d
  bool v111; // bl
  bool v112; // di
  __int64 v113; // rax
  int v114; // r8d
  int v115; // edx
  bool v116; // bl
  bool v117; // di
  __int64 v118; // rax
  int v119; // r8d
  int v120; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v122; // r8
  __int64 v123; // r9
  __int64 v124; // rdx
  bool v125; // bl
  bool v126; // di
  __int64 v127; // rax
  int v128; // r8d
  int v129; // edx
  bool v130; // bl
  bool v131; // di
  __int64 v132; // rax
  int v133; // r8d
  int v134; // edx
  bool v135; // bl
  bool v136; // di
  __int64 v137; // rax
  int v138; // r8d
  int v139; // edx
  unsigned int v141; // [rsp+20h] [rbp-C8h]
  int v142; // [rsp+28h] [rbp-C0h]
  int v143; // [rsp+30h] [rbp-B8h]
  __int16 v144; // [rsp+30h] [rbp-B8h]
  int v145; // [rsp+38h] [rbp-B0h]
  bool v146; // [rsp+70h] [rbp-78h]
  char v147; // [rsp+71h] [rbp-77h]
  ULONG_PTR v148[2]; // [rsp+78h] [rbp-70h] BYREF
  struct tagTHREADINFO *v149; // [rsp+88h] [rbp-60h]
  ULONG_PTR BugCheckParameter3[11]; // [rsp+90h] [rbp-58h] BYREF
  __int64 v151; // [rsp+F0h] [rbp+8h]
  bool v152; // [rsp+F0h] [rbp+8h]
  __int16 v153; // [rsp+100h] [rbp+18h]
  char v154; // [rsp+108h] [rbp+20h]

  v154 = a4;
  v153 = a3;
  v4 = 1;
  v5 = a1;
  v147 = 1;
  v6 = 0;
  v7 = *(_QWORD *)(W32GetUserSessionState(a1, a2, a3, a4) + 18968);
  v8 = *((_QWORD *)v5 + 2);
  v148[0] = v7;
  v151 = *(_QWORD *)(v8 + 464);
  v146 = v151 == v7;
  v9 = PtiCurrent();
  v149 = v9;
  v10 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v11 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v10 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(**((PETHREAD **)v5 + 2));
    PsGetThreadId(*(PETHREAD *)v9);
    UserSessionState = W32GetUserSessionState(v13, v12, v14, v15);
    LOBYTE(v17) = v11;
    LOBYTE(v18) = v10;
    WPP_RECORDER_AND_TRACE_SF_DqDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v18,
      v17,
      *(_QWORD *)(UserSessionState + 69152));
    v9 = v149;
  }
  BugCheckParameter3[1] = 0;
  BugCheckParameter3[0] = -1;
  v19 = _GhostWindowFromHungWindow(v5);
  v24 = v19;
  if ( v19 )
  {
    Win32HM_LockIntoThread<0>(v9, v19, BugCheckParameter3);
    v21 = WPP_GLOBAL_Control;
    v25 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v26 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v25 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v27 = *(_QWORD *)v5;
      v28 = *(_QWORD *)v24;
      v29 = W32GetUserSessionState(WPP_GLOBAL_Control, v20, v22, v23);
      LOBYTE(v30) = v26;
      LOBYTE(v31) = v25;
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v31,
        v30,
        *(_QWORD *)(v29 + 69152),
        4,
        2,
        73,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
        v28,
        v27);
      v9 = v149;
    }
    v5 = v24;
  }
  if ( v151 == v148[0] )
  {
    v32 = W32GetUserSessionState(v21, v20, v22, v23);
    v35 = *((_QWORD *)v9 + 58);
    v36 = *(_QWORD *)(v32 + 18968);
    v152 = v36 == v35;
    v37 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v38 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v37 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v39 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v33, v34);
      LOBYTE(v40) = v38;
      LOBYTE(v41) = v37;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v41,
        v40,
        *(_QWORD *)(v39 + 69152),
        4,
        2,
        74,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    v42 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v43 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v42 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v44 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v33, v34);
      LOBYTE(v45) = v43;
      LOBYTE(v46) = v42;
      v47 = *(_QWORD *)(v44 + 69152);
      v48 = "Synchronously";
      if ( v36 != v35 )
        v48 = "Async";
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v46,
        v45,
        v47,
        4,
        2,
        75,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
        (__int64)v48);
    }
    v49 = v146;
    v50 = v152;
LABEL_106:
    v55 = v153;
    goto LABEL_107;
  }
  LODWORD(v148[0]) = anonymous_namespace_::CanSetForegroundWindow(v5);
  v54 = v148[0];
  if ( LODWORD(v148[0]) != 2 )
  {
    v147 = 0;
    v76 = &WPP_GLOBAL_Control;
    v77 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v78 = &WPP_RECORDER_INITIALIZED;
    v79 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v77 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      ThreadId = (unsigned __int8)PsGetThreadId(**((PETHREAD **)v5 + 2));
      v81 = *(_QWORD *)v5;
      v82 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)v9);
      v87 = W32GetUserSessionState(v84, v83, v85, v86);
      LOBYTE(v88) = v79;
      LOBYTE(v89) = v77;
      WPP_RECORDER_AND_TRACE_SF_DqD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v89,
        v88,
        *(_QWORD *)(v87 + 69152),
        v141,
        v142,
        v143,
        v145,
        v82,
        v81,
        ThreadId);
      v54 = v148[0];
      v76 = &WPP_GLOBAL_Control;
      v78 = &WPP_RECORDER_INITIALIZED;
    }
    if ( (v154 & 1) != 0 )
    {
      v90 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v91 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v90 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v92 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v53);
        LOBYTE(v93) = v91;
        LOBYTE(v94) = v90;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v94,
          v93,
          *(_QWORD *)(v92 + 69152),
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
          v97 = v149;
          Win32HM_LockIntoThread<0>(v149, TopLevelCreatorWindow, v148);
          UPDWORDPointer(8196);
          xxxFlashWindow(TopLevelCreatorWindow);
          Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v148);
LABEL_95:
          if ( v54 == 1 )
          {
            v49 = v146;
            v50 = 0;
          }
          else
          {
            v49 = 1;
            v50 = *((_QWORD *)v97 + 58) == *(_QWORD *)(*((_QWORD *)v5 + 2) + 464LL);
            v98 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            v99 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v98 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v100 = W32GetUserSessionState(WPP_GLOBAL_Control, v76, v78, v53);
              LOBYTE(v101) = v99;
              LOBYTE(v102) = v98;
              WPP_RECORDER_AND_TRACE_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v102,
                v101,
                *(_QWORD *)(v100 + 69152),
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
    v97 = v149;
    goto LABEL_95;
  }
  v55 = v153;
  v56 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v57 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v56 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v58 = W32GetUserSessionState(WPP_GLOBAL_Control, v51, v52, v53);
    LOBYTE(v59) = v57;
    LOBYTE(v60) = v56;
    v61 = *(_QWORD *)(v58 + 69152);
    v62 = "Remove";
    if ( (v153 & 0x1000) != 0 )
      v62 = "Preserve";
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v60,
      v59,
      v61,
      4,
      2,
      76,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
      (__int64)v62);
  }
  if ( (v153 & 0x1000) == 0 )
    anonymous_namespace_::RemoveForegroundActivate();
  v63 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v64 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v63 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v65 = W32GetUserSessionState(WPP_GLOBAL_Control, v51, v52, v53);
    LOBYTE(v66) = v64;
    LOBYTE(v67) = v63;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v67,
      v66,
      *(_QWORD *)(v65 + 69152),
      4,
      2,
      77,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
  }
  v68 = (ULONG_PTR)v149;
  if ( (v153 & 0x400) != 0 )
    v68 = 0;
  if ( (unsigned int)xxxSetForegroundWindow2((ULONG_PTR *)v5, v68, v153 & 0x3FF) )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( *((_QWORD *)v149 + 61) != *(_QWORD *)(W32GetUserSessionState(v70, v69, v71, v72) + 19216) )
    {
      v73 = *((_QWORD *)v5 + 5);
      if ( *(char *)(v73 + 19) >= 0 && *(_DWORD *)(v73 + 236) != 15 && (unsigned int)IsImmersiveBandOrShellManaged(v5) )
      {
        if ( (unsigned int)IAMThreadAccessGranted(v149) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2437);
        v74 = GetNonChildAncestor(v5);
        v75 = (__int64 *)anonymous_namespace_::DSW_GetTopLevelCreatorWindow(v74);
        PostIAMShellHookMessage(0x22u, *v75);
      }
    }
  }
  v49 = v146;
  v50 = 0;
LABEL_107:
  if ( (unsigned int)Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !v49 )
      goto LABEL_179;
    if ( (v55 & 0x400) != 0 )
    {
      v106 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v107 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v106 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v108 = W32GetUserSessionState(WPP_GLOBAL_Control, v103, v104, v105);
        v144 = 81;
LABEL_118:
        LOBYTE(v110) = v107;
        LOBYTE(v109) = v106;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v109,
          v110,
          *(_QWORD *)(v108 + 69152),
          4,
          2,
          v144,
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
        goto LABEL_179;
      }
      goto LABEL_179;
    }
  }
  else if ( !v49 )
  {
    goto LABEL_179;
  }
  v111 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v112 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v111 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v113 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v105);
    LOBYTE(v114) = v112;
    LOBYTE(v115) = v111;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v115,
      v114,
      *(_QWORD *)(v113 + 69152),
      4,
      2,
      82,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
  }
  if ( !v50 )
  {
    if ( v5 != *(struct tagWND **)(*(_QWORD *)(*((_QWORD *)v5 + 2) + 464LL) + 128LL) )
    {
      if ( (*(_BYTE *)(*((_QWORD *)v5 + 5) + 31LL) & 0xC0) == 0x40 )
      {
        v130 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v131 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v130 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v132 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v105);
          LOBYTE(v133) = v131;
          LOBYTE(v134) = v130;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v134,
            v133,
            *(_QWORD *)(v132 + 69152),
            4,
            2,
            86,
            (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
        }
      }
      v135 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v136 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v135 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v137 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v105);
        LOBYTE(v138) = v136;
        LOBYTE(v139) = v135;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v139,
          v138,
          *(_QWORD *)(v137 + 69152),
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
    v125 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v126 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v125 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v127 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v105);
      LOBYTE(v128) = v126;
      LOBYTE(v129) = v125;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v129,
        v128,
        *(_QWORD *)(v127 + 69152),
        4,
        2,
        85,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
LABEL_160:
    v6 = 1;
    goto LABEL_179;
  }
  v116 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v117 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v116 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v118 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v105);
    LOBYTE(v119) = v117;
    LOBYTE(v120) = v116;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v120,
      v119,
      *(_QWORD *)(v118 + 69152),
      4,
      2,
      83,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
  }
  IsEnabledDeviceUsageNoInline = Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline();
  LOBYTE(v124) = *(_BYTE *)(*((_QWORD *)v5 + 5) + 31LL) & 0xC0;
  if ( !IsEnabledDeviceUsageNoInline )
  {
    if ( (_BYTE)v124 == 64 || !(unsigned __int8)anonymous_namespace_::xxxLocalActivateWindow(v5) )
    {
      v6 = 0;
      goto LABEL_179;
    }
    goto LABEL_160;
  }
  if ( (_BYTE)v124 != 64 )
  {
    v6 = anonymous_namespace_::xxxLocalActivateWindow(v5);
    goto LABEL_179;
  }
  v106 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v107 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v106 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v108 = W32GetUserSessionState(WPP_GLOBAL_Control, v124, v122, v123);
    v144 = 84;
    goto LABEL_118;
  }
LABEL_179:
  if ( !v147 || !v6 )
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
