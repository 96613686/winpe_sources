# xxxSetForegroundWindow2(tagWND *,tagTHREADINFO *,SetForegroundBehaviors)

- ea: `0x140271cc4`
- end: `0x140272921`
- name: `?xxxSetForegroundWindow2@@YAHPEAUtagWND@@PEAUtagTHREADINFO@@W4SetForegroundBehaviors@@@Z`
- size: `3165`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `7`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140032784`
- `0x1400c7d84`
- `0x14016f3c4`
- `0x1401a8530`
- `0x1401c0f48`
- `0x14021c534`
- `0x1402ab58c`

## callees

- `0x140006824`
- `0x1400073ec`
- `0x1400114a4`
- `0x140019430`
- `0x14001b9c0`
- `0x14001c788`
- `0x140025b90`
- `0x14002e150`
- `0x14002ea00`
- `0x14002eb54`
- `0x1400bb904`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x14013dda8`
- `0x14016e684`
- `0x14017cc14`
- `0x140182d80`
- `0x140188eb8`
- `0x140189124`
- `0x1401895f8`
- `0x140203240`
- `0x1402070b0`
- `0x14020a2b8`
- `0x140213994`
- `0x1402256a0`
- `0x140227c4c`
- `0x140271448`
- `0x1402715ec`
- `0x140271cc4`
- `0x1402aadd4`
- `0x1402ab37c`
- `0x1402aecc4`
- `0x1402b2820`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140271f72`
- `ntoskrnl!PsGetThreadId` at `0x140271f8e`
- `ntoskrnl!PsGetThreadId` at `0x140272533`
- `ntoskrnl!PsGetThreadId` at `0x1402726b0`
- `ntoskrnl!PsGetThreadId` at `0x14027279c`
- `ntoskrnl!PsGetThreadId` at `0x1402728b3`
- `ntoskrnl!PsGetThreadId` at `0x140271f72`
- `ntoskrnl!PsGetThreadId` at `0x140271f8e`
- `ntoskrnl!PsGetThreadId` at `0x140272533`
- `ntoskrnl!PsGetThreadId` at `0x1402726b0`
- `ntoskrnl!PsGetThreadId` at `0x14027279c`
- `ntoskrnl!PsGetThreadId` at `0x1402728b3`
- `win32kbase!?ClearClip@CCursorClip@@QEAAXXZ` at `0x140272433`
- `win32kbase!?ClearClip@CCursorClip@@QEAAXXZ` at `0x140272433`
- `win32kbase!ClearKeyboardToggleStates` at `0x14027227b`
- `win32kbase!ClearKeyboardToggleStates` at `0x14027227b`
- `win32kbase!SetSystemInputSource` at `0x140271d4c`
- `win32kbase!SetSystemInputSource` at `0x140271d4c`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027226b`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027226b`
- `WIN32K!W32GetUserSessionState` at `0x140271d61`
- `WIN32K!W32GetUserSessionState` at `0x140271def`
- `WIN32K!W32GetUserSessionState` at `0x140271e88`
- `WIN32K!W32GetUserSessionState` at `0x140271fa7`
- `WIN32K!W32GetUserSessionState` at `0x140272034`
- `WIN32K!W32GetUserSessionState` at `0x14027207e`
- `WIN32K!W32GetUserSessionState` at `0x1402720ca`
- `WIN32K!W32GetUserSessionState` at `0x140272108`
- `WIN32K!W32GetUserSessionState` at `0x140272120`
- `WIN32K!W32GetUserSessionState` at `0x140272145`
- `WIN32K!W32GetUserSessionState` at `0x1402721c9`
- `WIN32K!W32GetUserSessionState` at `0x1402721de`
- `WIN32K!W32GetUserSessionState` at `0x1402721fa`
- `WIN32K!W32GetUserSessionState` at `0x140272216`
- `WIN32K!W32GetUserSessionState` at `0x14027222b`
- `WIN32K!W32GetUserSessionState` at `0x140272247`
- `WIN32K!W32GetUserSessionState` at `0x140272287`
- `WIN32K!W32GetUserSessionState` at `0x1402722a7`
- `WIN32K!W32GetUserSessionState` at `0x1402722f4`
- `WIN32K!W32GetUserSessionState` at `0x140272309`
- `WIN32K!W32GetUserSessionState` at `0x14027231c`
- `WIN32K!W32GetUserSessionState` at `0x140272331`
- `WIN32K!W32GetUserSessionState` at `0x14027234a`
- `WIN32K!W32GetUserSessionState` at `0x140272365`
- `WIN32K!W32GetUserSessionState` at `0x140272378`
- `WIN32K!W32GetUserSessionState` at `0x140272391`
- `WIN32K!W32GetUserSessionState` at `0x1402723a6`
- `WIN32K!W32GetUserSessionState` at `0x1402723bf`
- `WIN32K!W32GetUserSessionState` at `0x1402723dd`
- `WIN32K!W32GetUserSessionState` at `0x1402723f2`
- `WIN32K!W32GetUserSessionState` at `0x140272420`
- `WIN32K!W32GetUserSessionState` at `0x140272506`
- `WIN32K!W32GetUserSessionState` at `0x14027251d`
- `WIN32K!W32GetUserSessionState` at `0x1402727b5`
- `WIN32K!W32GetUserSessionState` at `0x140271d61`
- `WIN32K!W32GetUserSessionState` at `0x140271def`
- `WIN32K!W32GetUserSessionState` at `0x140271e88`
- `WIN32K!W32GetUserSessionState` at `0x140271fa7`
- `WIN32K!W32GetUserSessionState` at `0x140272034`
- `WIN32K!W32GetUserSessionState` at `0x14027207e`
- `WIN32K!W32GetUserSessionState` at `0x1402720ca`
- `WIN32K!W32GetUserSessionState` at `0x140272108`
- `WIN32K!W32GetUserSessionState` at `0x140272120`
- `WIN32K!W32GetUserSessionState` at `0x140272145`
- `WIN32K!W32GetUserSessionState` at `0x1402721c9`
- `WIN32K!W32GetUserSessionState` at `0x1402721de`
- `WIN32K!W32GetUserSessionState` at `0x1402721fa`
- `WIN32K!W32GetUserSessionState` at `0x140272216`
- `WIN32K!W32GetUserSessionState` at `0x14027222b`
- `WIN32K!W32GetUserSessionState` at `0x140272247`
- `WIN32K!W32GetUserSessionState` at `0x140272287`
- `WIN32K!W32GetUserSessionState` at `0x1402722a7`
- `WIN32K!W32GetUserSessionState` at `0x1402722f4`
- `WIN32K!W32GetUserSessionState` at `0x140272309`
- `WIN32K!W32GetUserSessionState` at `0x14027231c`
- `WIN32K!W32GetUserSessionState` at `0x140272331`
- `WIN32K!W32GetUserSessionState` at `0x14027234a`
- `WIN32K!W32GetUserSessionState` at `0x140272365`
- `WIN32K!W32GetUserSessionState` at `0x140272378`
- `WIN32K!W32GetUserSessionState` at `0x140272391`
- `WIN32K!W32GetUserSessionState` at `0x1402723a6`
- `WIN32K!W32GetUserSessionState` at `0x1402723bf`
- `WIN32K!W32GetUserSessionState` at `0x1402723dd`
- `WIN32K!W32GetUserSessionState` at `0x1402723f2`
- `WIN32K!W32GetUserSessionState` at `0x140272420`
- `WIN32K!W32GetUserSessionState` at `0x140272506`
- `WIN32K!W32GetUserSessionState` at `0x14027251d`
- `WIN32K!W32GetUserSessionState` at `0x1402727b5`

## pseudocode

```c
__int64 __fastcall xxxSetForegroundWindow2(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  bool v12; // bl
  bool v13; // si
  __int64 UserSessionState; // rax
  int v15; // r8d
  int v16; // edx
  bool v17; // bl
  bool v18; // si
  __int64 v19; // rax
  int v20; // r8d
  int v21; // edx
  __int64 v22; // rdx
  __int64 v23; // rdx
  bool v25; // al
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rax
  struct MOVESIZEDATA *v31; // rcx
  bool v32; // al
  __int64 v33; // rax
  int v34; // r8d
  int v35; // edx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  struct MOVESIZEDATA *v39; // rcx
  bool v40; // bl
  bool v41; // r14
  __int64 v42; // rax
  int v43; // r8d
  int v44; // edx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // r13
  __int64 v50; // r14
  __int64 v51; // r8
  __int64 v52; // r9
  struct tagTHREADINFO *v53; // rcx
  struct tagWND *v54; // rdx
  _QWORD **v55; // rdx
  _QWORD *v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 v67; // rdx
  __int64 v68; // rcx
  const struct tagUIPI_INFO *v69; // r8
  __int64 v70; // r9
  __int64 v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __m128i si128; // xmm0
  __m128i *v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rbx
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // rbx
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // r8
  __int64 v94; // r9
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // r9
  __int64 v102; // rax
  __int64 v103; // r8
  __int64 v104; // r9
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // r8
  __int64 v108; // r9
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 v111; // rdx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  __int64 v115; // r9
  __int64 v116; // rax
  __int64 v117; // rbx
  unsigned int v118; // ebx
  _BOOL8 IsHostThreadOf; // r13
  const struct tagWND *TopLevelWindow; // rax
  __int64 v121; // rdx
  __int64 v122; // r8
  __int64 v123; // r9
  __int64 v124; // rcx
  __int64 v125; // rdx
  __int64 v126; // r8
  __int64 v127; // r9
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // r9
  __int64 v131; // rax
  HANDLE ThreadId; // rax
  const struct tagTHREADINFO **v133; // rcx
  __int64 v134; // rdx
  __int64 v135; // r8
  __int64 v136; // rbx
  __int64 v137; // r8
  __int64 v138; // r13
  int v139; // eax
  __int64 v140; // rdx
  __int64 v141; // r8
  __int64 v142; // r9
  bool v143; // zf
  char v144; // r13
  __int64 v145; // r12
  void *v146; // rdx
  unsigned int v147; // ecx
  unsigned __int64 v148; // r9
  unsigned int v149; // eax
  const struct tagTHREADINFO **v150; // rcx
  __int16 v151; // dx
  __int16 v152; // bx
  unsigned int v153; // eax
  __int64 v154; // rdx
  __int64 v155; // rcx
  __int64 v156; // r8
  __int64 v157; // r9
  __int64 v158; // r8
  __int64 v159; // rdx
  __int64 v160; // r8
  __int64 v161; // r9
  __int64 v162; // rax
  char v163; // bl
  const struct tagWND *v164; // rax
  __int64 v165; // rdx
  __int64 v166; // r8
  __int64 v167; // r9
  const struct tagWND *v168; // r15
  unsigned int v169; // eax
  __int64 v170; // rdx
  __int64 v171; // rdx
  __int64 v172; // [rsp+20h] [rbp-E0h]
  char v173; // [rsp+70h] [rbp-90h]
  bool v174; // [rsp+70h] [rbp-90h]
  char v175; // [rsp+71h] [rbp-8Fh]
  bool v176; // [rsp+71h] [rbp-8Fh]
  struct tagWND *v178; // [rsp+80h] [rbp-80h]
  struct tagWND *v179; // [rsp+80h] [rbp-80h]
  unsigned int v180; // [rsp+80h] [rbp-80h]
  unsigned int v181; // [rsp+80h] [rbp-80h]
  struct tagQMSG *v183; // [rsp+90h] [rbp-70h]
  struct tagQMSG *v184; // [rsp+90h] [rbp-70h]
  __int64 v185; // [rsp+98h] [rbp-68h]
  __int64 v186; // [rsp+A0h] [rbp-60h] BYREF
  ULONG_PTR v187[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v188; // [rsp+B8h] [rbp-48h]
  ULONG_PTR v189[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v190; // [rsp+D0h] [rbp-30h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v192; // [rsp+E8h] [rbp-18h]
  __int64 v193; // [rsp+F0h] [rbp-10h] BYREF
  int v194; // [rsp+F8h] [rbp-8h]
  __int64 v195; // [rsp+100h] [rbp+0h] BYREF
  int v196; // [rsp+108h] [rbp+8h]

  *(_OWORD *)BugCheckParameter2 = 0;
  *(_OWORD *)v189 = 0;
  v192 = -1;
  v190 = -1;
  *(_OWORD *)v187 = 0;
  v188 = -1;
  v178 = PtiCurrent(-1, a2);
  v195 = 0;
  v196 = 0;
  v193 = 0;
  v194 = 0;
  v186 = 0;
  Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline();
  SetSystemInputSource(&v186);
  if ( !a1 )
    goto LABEL_22;
  if ( *(_QWORD *)(a1 + 24) == *(_QWORD *)(W32GetUserSessionState(v6, v5, v7, v8) + 19216)
    && *(char *)(*(_QWORD *)(a1 + 40) + 19LL) >= 0 )
  {
    if ( (unsigned int)IsWindowUnderActiveLockScreen(a1, v9, v10, v11) )
    {
      v12 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v13 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v12 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, v5, v7, v8);
        LOBYTE(v15) = v13;
        LOBYTE(v16) = v12;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v16,
          v15,
          *(_QWORD *)(UserSessionState + 69152),
          4,
          2,
          91,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      }
      goto LABEL_89;
    }
LABEL_22:
    if ( a2 )
      Win32RawLockedW32Thread::ManualLock(BugCheckParameter2, a2);
    v25 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v173 = v25;
    v175 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v25 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      PsGetThreadId(*(PETHREAD *)v178);
      v29 = a2;
      if ( a2 )
        PsGetThreadId(*(PETHREAD *)a2);
      v30 = W32GetUserSessionState(v29, v26, v27, v28);
      WPP_RECORDER_AND_TRACE_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v173,
        v175,
        *(_QWORD *)(v30 + 69152),
        v172,
        2u,
        0x5Cu,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v31 = WPP_GLOBAL_Control;
    v32 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v174 = v32;
    LOBYTE(v31) = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    v176 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v32 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v33 = W32GetUserSessionState(v31, v5, v7, v8);
      LOBYTE(v34) = v176;
      LOBYTE(v35) = v174;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v35,
        v34,
        *(_QWORD *)(v33 + 69152),
        4,
        2,
        93,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
        a3);
    }
    *(_QWORD *)(W32GetUserSessionState(v31, v5, v7, v8) + 18928) = 0;
    v39 = WPP_GLOBAL_Control;
    v40 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v41 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v40 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v42 = W32GetUserSessionState(WPP_GLOBAL_Control, v36, v37, v38);
      LOBYTE(v43) = v41;
      LOBYTE(v44) = v40;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v44,
        v43,
        *(_QWORD *)(v42 + 69152),
        4,
        2,
        94,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v49 = 0;
    if ( !*(_QWORD *)(W32GetUserSessionState(v39, v36, v37, v38) + 18984)
      || (v45 = *(_QWORD *)(W32GetUserSessionState(v46, v45, v47, v48) + 18984),
          (_InterlockedCompareExchange((volatile signed __int32 *)(v45 + 520), 0, 0) & 1) != 0) )
    {
      v50 = 0;
    }
    else
    {
      v50 = *(_QWORD *)(W32GetUserSessionState(0, v45, v47, v48) + 18984);
      Win32RawLockedW32Thread::ManualLock(v189, v50);
    }
    if ( a1 )
    {
      v185 = *(_QWORD *)(a1 + 16);
      SetNewForegroundQueue(*(_QWORD *)(v185 + 464), (a3 & 0x200 | 0x100) >> 8);
      Win32RawLockedW32Thread::ManualLock(v187, v185);
      v53 = *(struct tagTHREADINFO **)(a1 + 16);
      v54 = (struct tagWND *)a1;
    }
    else
    {
      v185 = 0;
      ResetForegroundQueue(1, v45, v47, v48);
      v53 = 0;
      v54 = 0;
    }
    xxxSetForegroundThreadWithWindowHint(v53, v54, v51, v52);
    if ( (a3 & 0x20) == 0 )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v56, v55, v57, v58) + 18968) )
      {
        v63 = *(_QWORD *)(W32GetUserSessionState(v60, v59, v61, v62) + 18968);
        LODWORD(v195) = *(_DWORD *)(v63 + 544);
        v60 = *(_QWORD *)(W32GetUserSessionState(v63, v64, v65, v66) + 18968);
        HIDWORD(v195) = *(_DWORD *)(v60 + 548);
      }
      if ( *(_QWORD *)(W32GetUserSessionState(v60, v59, v61, v62) + 18976) )
      {
        v71 = *(_QWORD *)(W32GetUserSessionState(v68, v67, v69, v70) + 18976);
        LODWORD(v193) = *(_DWORD *)(v71 + 544);
        HIDWORD(v193) = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v71, v72, v73, v74) + 18976) + 548LL);
      }
      if ( !UIPrivilegeIsolation::CheckAccess((UIPrivilegeIsolation *)&v195, (const struct tagUIPI_INFO *)&v193, v69) )
      {
        ClearKeyboardToggleStates();
        v56 = *(_QWORD **)(W32GetUserSessionState(v76, v75, v77, v78) + 19216);
        if ( *((_QWORD **)v178 + 61) == v56 )
        {
          v55 = (_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v56, v55, v57, v58) + 19216) + 176LL);
          v56 = *v55;
          if ( *v55 != v55 )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
            do
            {
              v80 = (__m128i *)*(v56 - 38);
              v80[20] = si128;
              v80[21] = si128;
              v80[31].m128i_i32[3] |= 1u;
              v56 = (_QWORD *)*v56;
            }
            while ( v56 != v55 );
          }
        }
      }
    }
    if ( *(_QWORD *)(W32GetUserSessionState(v56, v55, v57, v58) + 18968) )
    {
      v85 = *(_QWORD *)(W32GetUserSessionState(v82, v81, v83, v84) + 18968);
      if ( v85 != *(_QWORD *)(W32GetUserSessionState(v87, v86, v88, v89) + 18976) )
      {
        v82 = *(_QWORD *)(W32GetUserSessionState(v82, v81, v83, v84) + 18968);
        if ( *(_QWORD *)(v82 + 120) )
        {
          v82 = *(unsigned int *)(W32GetUserSessionState(v82, v81, v83, v84) + 66792);
          if ( (v82 & 0x80u) == 0LL )
            xxxApplyGlobalInputSettings();
        }
      }
    }
    v90 = *(_QWORD *)(W32GetUserSessionState(v82, v81, v83, v84) + 18968);
    if ( v90 == *(_QWORD *)(W32GetUserSessionState(v92, v91, v93, v94) + 18976) )
      goto LABEL_161;
    if ( *(_QWORD *)(W32GetUserSessionState(v95, v5, v96, v97) + 18976) )
    {
      v99 = *(_QWORD *)(W32GetUserSessionState(v99, v98, v100, v101) + 18976);
      if ( *(_QWORD *)(v99 + 120) )
      {
        v102 = W32GetUserSessionState(v99, v98, v100, v101);
        zzzInputFocusLostWindowEvent(*(_QWORD *)(*(_QWORD *)(v102 + 18976) + 120LL), 1, v103, v104);
      }
    }
    if ( *(_QWORD *)(W32GetUserSessionState(v99, v98, v100, v101) + 18968)
      && *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v106, v105, v107, v108) + 18968) + 120LL) )
    {
      zzzInputFocusReceivedWindowEvent(1, v109, v110, v108);
    }
    v111 = a2;
    if ( a2 )
    {
      xxxCancelTracking();
      v116 = W32GetUserSessionState(v113, v112, v114, v115);
      CCursorClip::ClearClip(*(CCursorClip **)(v116 + 36072));
      v111 = a2;
    }
    v117 = 0;
    if ( v50 && (_InterlockedCompareExchange((volatile signed __int32 *)(v50 + 520), 0, 0) & 1) == 0 )
      v117 = *(_QWORD *)(v50 + 464);
    if ( v111 )
      v49 = *(_QWORD *)(v111 + 464);
    v183 = 0;
    if ( v117 )
    {
      if ( v117 != v49 )
      {
        v183 = (struct tagQMSG *)AllocQEntryEx(v117 + 24, 0, 1, v108);
        if ( !v183 )
          goto LABEL_89;
      }
      if ( v117 != v49 )
      {
        IsHostThreadOf = 0;
        if ( a1 )
        {
          TopLevelWindow = (const struct tagWND *)GetTopLevelWindow(a1);
          v179 = TopLevelWindow;
          if ( TopLevelWindow )
          {
            if ( (unsigned int)CoreWindowProp::IsComponent(TopLevelWindow, v121, v122, v123) )
              IsHostThreadOf = CoreWindowProp::IsHostThreadOf((const struct tagTHREADINFO *)v50, v179);
          }
        }
        v124 = *(_QWORD *)(PtiKbdFromQ(v117) + 456);
        v180 = *(_DWORD *)(v124 + 268);
        if ( *(_QWORD *)(W32GetUserSessionState(v124, v125, v126, v127) + 18984) )
        {
          v131 = W32GetUserSessionState(v128, 0, v129, v130);
          ThreadId = PsGetThreadId(**(PETHREAD **)(v131 + 18984));
        }
        else
        {
          ThreadId = 0;
        }
        StoreQMessage(
          v183,
          0,
          0,
          (unsigned __int64)ThreadId,
          0,
          0,
          0,
          5u,
          IsHostThreadOf,
          0,
          (const struct tagINPUT_MESSAGE_SOURCE *)&v186,
          v180,
          0,
          0);
        if ( v50 )
        {
          *((_QWORD *)v183 + 13) = v50;
          SetWakeBit(v50, 0x2040u);
        }
        v133 = *(const struct tagTHREADINFO ***)(v117 + 128);
        if ( v133 && IsHungWindow(v133) )
          ProcessHungWindow(*(struct tagWND **)(v117 + 128), v134, v135, v108);
      }
    }
    v136 = 0;
    if ( v185 && (_InterlockedCompareExchange((volatile signed __int32 *)(v185 + 520), 0, 0) & 1) == 0 )
      v136 = *(_QWORD *)(v185 + 464);
    v137 = a2;
    v138 = 0;
    if ( a2 )
      v138 = *(_QWORD *)(a2 + 464);
    if ( v136 )
    {
      v184 = 0;
      if ( v136 != v138 )
      {
        v184 = (struct tagQMSG *)AllocQEntryEx(v136 + 24, 0, 1, v108);
        if ( !v184 )
        {
LABEL_89:
          v118 = 0;
LABEL_162:
          LOBYTE(v5) = 1;
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v187, v5);
          LOBYTE(v170) = 1;
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v189, v170);
          LOBYTE(v171) = 1;
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2, v171);
          return v118;
        }
      }
      v139 = anonymous_namespace_::RemoveEventMessage(v136, 5, -1);
      if ( v136 == v138 )
      {
        if ( a1 == *(_QWORD *)(v138 + 128) )
        {
          if ( a1 )
            v158 = *(_QWORD *)a1;
          else
            v158 = 0;
          anonymous_namespace_::xxxSendNCActivateMessage((struct tagWND *)a1, 1u, v158, v142);
          anonymous_namespace_::xxxUpdateTray((struct tagWND *)a1, v159, v160, v161);
          v144 = a3;
          if ( (a3 & 4) == 0 )
            xxxSetWindowPos((struct tagWND *)a1, 0, 0, 0, 0, 0, 3);
        }
        else
        {
          v144 = a3;
          if ( (a3 & 1) == 0 )
          {
            v151 = ~(16 * (_BYTE)a3) & 0x80 | 0x100;
            if ( (a3 & 0x100) == 0 )
              v151 = ~(16 * (_BYTE)a3) & 0x80;
            v152 = v151 | 2;
            if ( (a3 & 4) == 0 )
              v152 = v151;
            if ( v50 )
              v153 = (unsigned int)PsGetThreadId(*(PETHREAD *)v50);
            else
              v153 = 0;
            anonymous_namespace_::xxxLocalActivateWindow((struct tagWND *)a1, v153, v152);
            v5 = *(unsigned int *)(W32GetUserSessionState(v155, v154, v156, v157) + 66788);
            if ( (v5 & 1) != 0 )
              zzzActiveCursorTracking(a1);
            goto LABEL_161;
          }
        }
      }
      else
      {
        v143 = v138 == 0;
        v144 = a3;
        if ( !v143 || (a3 & 2) != 0 )
        {
          v145 = 0;
          if ( a1 )
            v145 = *(_QWORD *)a1;
        }
        else
        {
          v145 = 0;
        }
        if ( v139 )
          *(_DWORD *)(v136 + 508) |= 0x8000u;
        v147 = *(_DWORD *)(*(_QWORD *)(PtiKbdFromQ(v136) + 456) + 268LL);
        v181 = v147;
        if ( (a3 & 1) != 0 )
        {
          v148 = (unsigned __int64)v146;
        }
        else
        {
          if ( v50 )
          {
            v149 = (unsigned int)PsGetThreadId(*(PETHREAD *)v50);
            v147 = v181;
            v146 = 0;
          }
          else
          {
            v149 = (unsigned int)v146;
          }
          v148 = v149;
        }
        StoreQMessage(
          v184,
          0,
          (a3 >> 2) & 1,
          v148,
          v145,
          (unsigned int)v146,
          (unsigned __int64)v146,
          6u,
          (unsigned __int64)v146,
          (unsigned int)v146,
          (const struct tagINPUT_MESSAGE_SOURCE *)&v186,
          v147,
          v146,
          (struct tagUIPI_INFO *)v146);
        *((_QWORD *)v184 + 13) = v185;
        SetWakeBit(v185, 0x2040u);
        v150 = *(const struct tagTHREADINFO ***)(v136 + 128);
        if ( v150 && IsHungWindow(v150) )
          ProcessHungWindow(*(struct tagWND **)(v136 + 128), v140, v141, v142);
      }
      if ( (v144 & 0x40) == 0 )
        xxxDeliverRestoreFocusMessage((struct tagWND *)a1, v140, v141, v142);
      v137 = a2;
    }
    v5 = 0;
    if ( v50 && (_InterlockedCompareExchange((volatile signed __int32 *)(v50 + 520), 0, 0) & 1) == 0 )
      v5 = *(_QWORD *)(v50 + 464);
    v162 = 0;
    if ( v137 )
      v162 = *(_QWORD *)(v137 + 464);
    if ( v5 && v5 == v162 )
    {
      v163 = 0;
      if ( a1 )
      {
        v164 = (const struct tagWND *)GetTopLevelWindow(a1);
        v168 = v164;
        if ( v164 && (unsigned int)CoreWindowProp::IsComponent(v164, v165, v166, v167) )
          v163 = CoreWindowProp::IsHostThreadOf((const struct tagTHREADINFO *)v50, v168);
        v169 = (unsigned int)PsGetThreadId(**(PETHREAD **)(a1 + 16));
      }
      else
      {
        v169 = 0;
      }
      xxxDeactivate(a2, v169, v163);
    }
LABEL_161:
    v118 = 1;
    goto LABEL_162;
  }
  v17 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v18 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v17 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v19 = W32GetUserSessionState(WPP_GLOBAL_Control, v9, v10, v11);
    LOBYTE(v20) = v18;
    LOBYTE(v21) = v17;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v21,
      v20,
      *(_QWORD *)(v19 + 69152),
      4,
      2,
      90,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  LOBYTE(v9) = 1;
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v187, v9);
  LOBYTE(v22) = 1;
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v189, v22);
  LOBYTE(v23) = 1;
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2, v23);
  return 0;
}

```

## disassembly

```asm
0x140271cc4  mov     [rsp-8+arg_10], rbx
0x140271cc9  push    rbp
0x140271cca  push    rsi
0x140271ccb  push    rdi
0x140271ccc  push    r12
0x140271cce  push    r13
0x140271cd0  push    r14
0x140271cd2  push    r15
0x140271cd4  lea     rbp, [rsp-20h]
0x140271cd9  sub     rsp, 120h
0x140271ce0  mov     rax, cs:__security_cookie
0x140271ce7  xor     rax, rsp
0x140271cea  mov     [rbp+50h+var_40], rax
0x140271cee  xorps   xmm0, xmm0
0x140271cf1  mov     [rsp+150h+var_DC], r8d
0x140271cf6  movups  xmmword ptr [rbp+50h+BugCheckParameter2], xmm0
0x140271cfa  mov     [rbp+50h+var_C8], rdx
0x140271cfe  mov     rsi, rcx
0x140271d01  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140271d05  xorps   xmm0, xmm0
0x140271d08  movups  xmmword ptr [rbp+50h+var_90], xmm0
0x140271d0c  mov     [rbp+50h+var_68], rcx
0x140271d10  mov     rbx, rdx
0x140271d13  xorps   xmm0, xmm0
0x140271d16  mov     [rbp+50h+var_80], rcx
0x140271d1a  movups  xmmword ptr [rbp+50h+var_A8], xmm0
0x140271d1e  mov     [rbp+50h+var_98], rcx
0x140271d22  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ
0x140271d27  mov     [rbp+50h+var_D0], rax
0x140271d2b  xor     eax, eax
0x140271d2d  mov     [rbp+50h+var_50], rax
0x140271d31  mov     [rbp+50h+var_48], eax
0x140271d34  mov     [rbp+50h+var_60], rax
0x140271d38  mov     [rbp+50h+var_58], eax
0x140271d3b  mov     [rbp+50h+var_B0], 0
0x140271d43  call    Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline
0x140271d48  lea     rcx, [rbp+50h+var_B0]
0x140271d4c  call    cs:__imp_SetSystemInputSource
0x140271d53  nop     dword ptr [rax+rax+00h]
0x140271d58  test    rsi, rsi
0x140271d5b  jz      loc_140271EF8
0x140271d61  call    cs:__imp_W32GetUserSessionState
0x140271d68  nop     dword ptr [rax+rax+00h]
0x140271d6d  mov     rcx, [rax+4B10h]
0x140271d74  cmp     [rsi+18h], rcx
0x140271d78  jnz     loc_140271E39
0x140271d7e  mov     rax, [rsi+28h]
0x140271d82  cmp     byte ptr [rax+13h], 0
0x140271d86  jl      loc_140271E39
0x140271d8c  mov     rcx, rsi
0x140271d8f  call    IsWindowUnderActiveLockScreen
0x140271d94  test    eax, eax
0x140271d96  jz      loc_140271EF8
0x140271d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140271da3  lea     rbx, WPP_GLOBAL_Control
0x140271daa  mov     edi, 1
0x140271daf  mov     r12b, 4
0x140271db2  lea     r15d, [rdi+1]
0x140271db6  cmp     rcx, rbx
0x140271db9  jz      short loc_140271DCE
0x140271dbb  mov     eax, [rcx+2Ch]
0x140271dbe  test    r15b, al
0x140271dc1  jz      short loc_140271DCE
0x140271dc3  cmp     [rcx+29h], r12b
0x140271dc7  jb      short loc_140271DCE
0x140271dc9  mov     bl, dil
0x140271dcc  jmp     short loc_140271DD0
0x140271dce  xor     bl, bl
0x140271dd0  lea     r14, WPP_RECORDER_INITIALIZED
0x140271dd7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140271dde  setnz   sil
0x140271de2  test    bl, bl
0x140271de4  jnz     short loc_140271DEF
0x140271de6  test    sil, sil
0x140271de9  jz      loc_14027249E
0x140271def  call    cs:__imp_W32GetUserSessionState
0x140271df6  nop     dword ptr [rax+rax+00h]
0x140271dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140271e02  lea     r13, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x140271e09  mov     qword ptr [rsp+150h+var_118], r13
0x140271e0e  mov     r8b, sil
0x140271e11  mov     word ptr [rsp+150h+var_120], 5Bh ; '['
0x140271e18  mov     dl, bl
0x140271e1a  mov     r9, [rax+10E20h]
0x140271e21  mov     rcx, [rcx+18h]
0x140271e25  mov     [rsp+150h+var_128], r15d
0x140271e2a  mov     byte ptr [rsp+150h+var_130], r12b
0x140271e2f  call    WPP_RECORDER_AND_TRACE_SF_
0x140271e34  jmp     loc_14027249E
0x140271e39  mov     rcx, cs:WPP_GLOBAL_Control
0x140271e40  lea     rbx, WPP_GLOBAL_Control
0x140271e47  mov     edi, 1
0x140271e4c  mov     r12b, 4
0x140271e4f  lea     r15d, [rdi+1]
0x140271e53  cmp     rcx, rbx
0x140271e56  jz      short loc_140271E6B
0x140271e58  mov     eax, [rcx+2Ch]
0x140271e5b  test    r15b, al
0x140271e5e  jz      short loc_140271E6B
0x140271e60  cmp     [rcx+29h], r12b
0x140271e64  jb      short loc_140271E6B
0x140271e66  mov     bl, dil
0x140271e69  jmp     short loc_140271E6D
0x140271e6b  xor     bl, bl
0x140271e6d  lea     r14, WPP_RECORDER_INITIALIZED
0x140271e74  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140271e7b  setnz   sil
0x140271e7f  test    bl, bl
0x140271e81  jnz     short loc_140271E88
0x140271e83  test    sil, sil
0x140271e86  jz      short loc_140271ECD
0x140271e88  call    cs:__imp_W32GetUserSessionState
0x140271e8f  nop     dword ptr [rax+rax+00h]
0x140271e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140271e9b  lea     r13, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x140271ea2  mov     qword ptr [rsp+150h+var_118], r13
0x140271ea7  mov     r8b, sil
0x140271eaa  mov     word ptr [rsp+150h+var_120], 5Ah ; 'Z'
0x140271eb1  mov     dl, bl
0x140271eb3  mov     r9, [rax+10E20h]
0x140271eba  mov     rcx, [rcx+18h]
0x140271ebe  mov     [rsp+150h+var_128], r15d
0x140271ec3  mov     byte ptr [rsp+150h+var_130], r12b
0x140271ec8  call    WPP_RECORDER_AND_TRACE_SF_
0x140271ecd  mov     dl, dil
0x140271ed0  lea     rcx, [rbp+50h+var_A8]; BugCheckParameter2
0x140271ed4  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x140271ed9  mov     dl, dil
0x140271edc  lea     rcx, [rbp+50h+var_90]; BugCheckParameter2
0x140271ee0  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x140271ee5  mov     dl, dil
0x140271ee8  lea     rcx, [rbp+50h+BugCheckParameter2]; BugCheckParameter2
0x140271eec  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x140271ef1  xor     eax, eax
0x140271ef3  jmp     loc_1402728F9
0x140271ef8  mov     edi, 1
0x140271efd  test    rbx, rbx
0x140271f00  jz      short loc_140271F0E
0x140271f02  mov     rdx, rbx; BugCheckParameter3
0x140271f05  lea     rcx, [rbp+50h+BugCheckParameter2]; BugCheckParameter2
0x140271f09  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x140271f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140271f15  lea     rbx, WPP_GLOBAL_Control
0x140271f1c  mov     r12b, 4
0x140271f1f  mov     r15d, 2
0x140271f25  cmp     rcx, rbx
0x140271f28  jz      short loc_140271F3D
0x140271f2a  mov     eax, [rcx+2Ch]
0x140271f2d  test    r15b, al
0x140271f30  jz      short loc_140271F3D
0x140271f32  cmp     [rcx+29h], r12b
0x140271f36  jb      short loc_140271F3D
0x140271f38  mov     al, dil
0x140271f3b  jmp     short loc_140271F3F
0x140271f3d  xor     al, al
0x140271f3f  lea     r14, WPP_RECORDER_INITIALIZED
0x140271f46  mov     [rsp+150h+var_E0], al
0x140271f4a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140271f51  lea     r13, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x140271f58  setnz   cl
0x140271f5b  mov     [rsp+150h+var_DF], cl
0x140271f5f  test    al, al
0x140271f61  jnz     short loc_140271F6B
0x140271f63  test    cl, cl
0x140271f65  jz      loc_140271FF9
0x140271f6b  mov     rcx, [rbp+50h+var_D0]
0x140271f6f  mov     rcx, [rcx]; Thread
0x140271f72  call    cs:__imp_PsGetThreadId
0x140271f79  nop     dword ptr [rax+rax+00h]
0x140271f7e  mov     rcx, [rbp+50h+var_C8]
0x140271f82  mov     [rbp+50h+var_C0], rax
0x140271f86  test    rcx, rcx
0x140271f89  jz      short loc_140271FA0
0x140271f8b  mov     rcx, [rcx]; Thread
0x140271f8e  call    cs:__imp_PsGetThreadId
0x140271f95  nop     dword ptr [rax+rax+00h]
0x140271f9a  mov     [rbp+50h+var_B8], rax
0x140271f9e  jmp     short loc_140271FA7
0x140271fa0  mov     dword ptr [rbp+50h+var_B8], 0
0x140271fa7  call    cs:__imp_W32GetUserSessionState
0x140271fae  nop     dword ptr [rax+rax+00h]
0x140271fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140271fba  mov     r8b, [rsp+150h+var_DF]
0x140271fbf  mov     dl, [rsp+150h+var_E0]
0x140271fc3  mov     r9, [rax+10E20h]
0x140271fca  mov     rax, [rbp+50h+var_C0]
0x140271fce  mov     rcx, [rcx+18h]
0x140271fd2  mov     dword ptr [rsp+150h+var_100], eax
0x140271fd6  mov     rax, [rbp+50h+var_B8]
0x140271fda  mov     [rsp+150h+var_108], eax
0x140271fde  mov     [rsp+150h+var_110], rsi
0x140271fe3  mov     qword ptr [rsp+150h+var_118], r13
0x140271fe8  mov     word ptr [rsp+150h+var_120], 5Ch ; '\'
0x140271fef  mov     [rsp+150h+var_128], r15d
0x140271ff4  call    WPP_RECORDER_AND_TRACE_SF_qDD
0x140271ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x140272000  cmp     rcx, rbx
0x140272003  jz      short loc_140272018
0x140272005  mov     eax, [rcx+2Ch]
0x140272008  test    r15b, al
0x14027200b  jz      short loc_140272018
0x14027200d  cmp     [rcx+29h], r12b
0x140272011  jb      short loc_140272018
0x140272013  mov     al, dil
0x140272016  jmp     short loc_14027201A
0x140272018  xor     al, al
0x14027201a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140272021  mov     [rsp+150h+var_E0], al
0x140272025  setnz   cl
0x140272028  mov     [rsp+150h+var_DF], cl
0x14027202c  test    al, al
0x14027202e  jnz     short loc_140272034
0x140272030  test    cl, cl
0x140272032  jz      short loc_14027207E
0x140272034  call    cs:__imp_W32GetUserSessionState
0x14027203b  nop     dword ptr [rax+rax+00h]
0x140272040  mov     rcx, cs:WPP_GLOBAL_Control
0x140272047  mov     r8b, [rsp+150h+var_DF]
0x14027204c  mov     dl, [rsp+150h+var_E0]
0x140272050  mov     r9, [rax+10E20h]
0x140272057  mov     eax, [rsp+150h+var_DC]
0x14027205b  mov     rcx, [rcx+18h]
0x14027205f  mov     dword ptr [rsp+150h+var_110], eax
0x140272063  mov     qword ptr [rsp+150h+var_118], r13
0x140272068  mov     word ptr [rsp+150h+var_120], 5Dh ; ']'
0x14027206f  mov     [rsp+150h+var_128], r15d
0x140272074  mov     byte ptr [rsp+150h+var_130], r12b
0x140272079  call    WPP_RECORDER_AND_TRACE_SF_D
0x14027207e  call    cs:__imp_W32GetUserSessionState
0x140272085  nop     dword ptr [rax+rax+00h]
0x14027208a  mov     qword ptr [rax+49F0h], 0
0x140272095  mov     rcx, cs:WPP_GLOBAL_Control
0x14027209c  cmp     rcx, rbx
0x14027209f  jz      short loc_1402720B4
0x1402720a1  mov     eax, [rcx+2Ch]
0x1402720a4  test    r15b, al
0x1402720a7  jz      short loc_1402720B4
0x1402720a9  cmp     [rcx+29h], r12b
0x1402720ad  jb      short loc_1402720B4
0x1402720af  mov     bl, dil
0x1402720b2  jmp     short loc_1402720B6
0x1402720b4  xor     bl, bl
0x1402720b6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1402720bd  setnz   r14b
0x1402720c1  test    bl, bl
0x1402720c3  jnz     short loc_1402720CA
0x1402720c5  test    r14b, r14b
0x1402720c8  jz      short loc_140272108
0x1402720ca  call    cs:__imp_W32GetUserSessionState
0x1402720d1  nop     dword ptr [rax+rax+00h]
0x1402720d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1402720dd  mov     r8b, r14b
0x1402720e0  mov     qword ptr [rsp+150h+var_118], r13
0x1402720e5  mov     dl, bl
0x1402720e7  mov     word ptr [rsp+150h+var_120], 5Eh ; '^'
0x1402720ee  mov     r9, [rax+10E20h]
0x1402720f5  mov     rcx, [rcx+18h]
0x1402720f9  mov     [rsp+150h+var_128], r15d
0x1402720fe  mov     byte ptr [rsp+150h+var_130], r12b
0x140272103  call    WPP_RECORDER_AND_TRACE_SF_
0x140272108  call    cs:__imp_W32GetUserSessionState
0x14027210f  nop     dword ptr [rax+rax+00h]
0x140272114  xor     r13d, r13d
0x140272117  cmp     [rax+4A28h], r13
0x14027211e  jz      short loc_140272166
0x140272120  call    cs:__imp_W32GetUserSessionState
0x140272127  nop     dword ptr [rax+rax+00h]
0x14027212c  mov     ecx, r13d
0x14027212f  mov     rdx, [rax+4A28h]
0x140272136  xor     eax, eax
0x140272138  lock cmpxchg [rdx+208h], ecx
0x140272140  test    dil, al
0x140272143  jnz     short loc_140272166
0x140272145  call    cs:__imp_W32GetUserSessionState
0x14027214c  nop     dword ptr [rax+rax+00h]
0x140272151  lea     rcx, [rbp+50h+var_90]; BugCheckParameter2
0x140272155  mov     r14, [rax+4A28h]
0x14027215c  mov     rdx, r14; BugCheckParameter3
0x14027215f  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x140272164  jmp     short loc_140272169
0x140272166  mov     r14, r13
0x140272169  test    rsi, rsi
0x14027216c  jz      short loc_1402721A8
0x14027216e  mov     rbx, [rsi+10h]
0x140272172  mov     edx, [rsp+150h+var_DC]
0x140272176  and     edx, 200h
0x14027217c  mov     [rbp+50h+var_B8], rbx
0x140272180  bts     edx, 8
0x140272184  mov     rcx, [rbx+1D0h]
0x14027218b  shr     edx, 8
0x14027218e  call    ?SetNewForegroundQueue@@YAXPEAUtagQ@@W4SetFgQueueOption@@@Z
0x140272193  mov     rdx, rbx; BugCheckParameter3
0x140272196  lea     rcx, [rbp+50h+var_A8]; BugCheckParameter2
0x14027219a  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x14027219f  mov     rcx, [rsi+10h]
0x1402721a3  mov     rdx, rsi
0x1402721a6  jmp     short loc_1402721B9
0x1402721a8  mov     ecx, edi
0x1402721aa  mov     [rbp+50h+var_B8], r13
0x1402721ae  call    ?ResetForegroundQueue@@YAXW4SetFgQueueOption@@@Z
  ... truncated ...
```
