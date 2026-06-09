# xxxSetForegroundWindow2(tagWND *,tagTHREADINFO *,SetForegroundBehaviors)

- ea: `0x14026e0fc`
- end: `0x14026ed59`
- name: `?xxxSetForegroundWindow2@@YAHPEAUtagWND@@PEAUtagTHREADINFO@@W4SetForegroundBehaviors@@@Z`
- size: `3165`
- prototype: ``
- caller_count: `7`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140036e04`
- `0x1400ef954`
- `0x140121b54`
- `0x140194824`
- `0x1401aa130`
- `0x1401c4bb8`
- `0x1402a914c`

## callees

- `0x140020d30`
- `0x140021958`
- `0x14002ac60`
- `0x1400327d0`
- `0x140033080`
- `0x1400331d4`
- `0x140085c00`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x1400d3f74`
- `0x1400de254`
- `0x1400e4a20`
- `0x1400ec110`
- `0x1400eec14`
- `0x140147de8`
- `0x140175bb0`
- `0x14017c0b8`
- `0x14017c324`
- `0x14017c7f8`
- `0x1401eb068`
- `0x1401eb600`
- `0x1401ebcd8`
- `0x1401ebe2c`
- `0x1402028d0`
- `0x140206610`
- `0x140209b64`
- `0x140243010`
- `0x14026df58`
- `0x14026e0fc`
- `0x1402a89f4`
- `0x1402a8f3c`
- `0x1402ac8dc`
- `0x1402b0e70`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14026e3aa`
- `ntoskrnl!PsGetThreadId` at `0x14026e3c6`
- `ntoskrnl!PsGetThreadId` at `0x14026e96b`
- `ntoskrnl!PsGetThreadId` at `0x14026eae8`
- `ntoskrnl!PsGetThreadId` at `0x14026ebd4`
- `ntoskrnl!PsGetThreadId` at `0x14026eceb`
- `ntoskrnl!PsGetThreadId` at `0x14026e3aa`
- `ntoskrnl!PsGetThreadId` at `0x14026e3c6`
- `ntoskrnl!PsGetThreadId` at `0x14026e96b`
- `ntoskrnl!PsGetThreadId` at `0x14026eae8`
- `ntoskrnl!PsGetThreadId` at `0x14026ebd4`
- `ntoskrnl!PsGetThreadId` at `0x14026eceb`
- `win32kbase!?ClearClip@CCursorClip@@QEAAXXZ` at `0x14026e86b`
- `win32kbase!?ClearClip@CCursorClip@@QEAAXXZ` at `0x14026e86b`
- `win32kbase!ClearKeyboardToggleStates` at `0x14026e6b3`
- `win32kbase!ClearKeyboardToggleStates` at `0x14026e6b3`
- `win32kbase!SetSystemInputSource` at `0x14026e184`
- `win32kbase!SetSystemInputSource` at `0x14026e184`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14026e6a3`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14026e6a3`
- `WIN32K!W32GetUserSessionState` at `0x14026e199`
- `WIN32K!W32GetUserSessionState` at `0x14026e227`
- `WIN32K!W32GetUserSessionState` at `0x14026e2c0`
- `WIN32K!W32GetUserSessionState` at `0x14026e3df`
- `WIN32K!W32GetUserSessionState` at `0x14026e46c`
- `WIN32K!W32GetUserSessionState` at `0x14026e4b6`
- `WIN32K!W32GetUserSessionState` at `0x14026e502`
- `WIN32K!W32GetUserSessionState` at `0x14026e540`
- `WIN32K!W32GetUserSessionState` at `0x14026e558`
- `WIN32K!W32GetUserSessionState` at `0x14026e57d`
- `WIN32K!W32GetUserSessionState` at `0x14026e601`
- `WIN32K!W32GetUserSessionState` at `0x14026e616`
- `WIN32K!W32GetUserSessionState` at `0x14026e632`
- `WIN32K!W32GetUserSessionState` at `0x14026e64e`
- `WIN32K!W32GetUserSessionState` at `0x14026e663`
- `WIN32K!W32GetUserSessionState` at `0x14026e67f`
- `WIN32K!W32GetUserSessionState` at `0x14026e6bf`
- `WIN32K!W32GetUserSessionState` at `0x14026e6df`
- `WIN32K!W32GetUserSessionState` at `0x14026e72c`
- `WIN32K!W32GetUserSessionState` at `0x14026e741`
- `WIN32K!W32GetUserSessionState` at `0x14026e754`
- `WIN32K!W32GetUserSessionState` at `0x14026e769`
- `WIN32K!W32GetUserSessionState` at `0x14026e782`
- `WIN32K!W32GetUserSessionState` at `0x14026e79d`
- `WIN32K!W32GetUserSessionState` at `0x14026e7b0`
- `WIN32K!W32GetUserSessionState` at `0x14026e7c9`
- `WIN32K!W32GetUserSessionState` at `0x14026e7de`
- `WIN32K!W32GetUserSessionState` at `0x14026e7f7`
- `WIN32K!W32GetUserSessionState` at `0x14026e815`
- `WIN32K!W32GetUserSessionState` at `0x14026e82a`
- `WIN32K!W32GetUserSessionState` at `0x14026e858`
- `WIN32K!W32GetUserSessionState` at `0x14026e93e`
- `WIN32K!W32GetUserSessionState` at `0x14026e955`
- `WIN32K!W32GetUserSessionState` at `0x14026ebed`
- `WIN32K!W32GetUserSessionState` at `0x14026e199`
- `WIN32K!W32GetUserSessionState` at `0x14026e227`
- `WIN32K!W32GetUserSessionState` at `0x14026e2c0`
- `WIN32K!W32GetUserSessionState` at `0x14026e3df`
- `WIN32K!W32GetUserSessionState` at `0x14026e46c`
- `WIN32K!W32GetUserSessionState` at `0x14026e4b6`
- `WIN32K!W32GetUserSessionState` at `0x14026e502`
- `WIN32K!W32GetUserSessionState` at `0x14026e540`
- `WIN32K!W32GetUserSessionState` at `0x14026e558`
- `WIN32K!W32GetUserSessionState` at `0x14026e57d`
- `WIN32K!W32GetUserSessionState` at `0x14026e601`
- `WIN32K!W32GetUserSessionState` at `0x14026e616`
- `WIN32K!W32GetUserSessionState` at `0x14026e632`
- `WIN32K!W32GetUserSessionState` at `0x14026e64e`
- `WIN32K!W32GetUserSessionState` at `0x14026e663`
- `WIN32K!W32GetUserSessionState` at `0x14026e67f`
- `WIN32K!W32GetUserSessionState` at `0x14026e6bf`
- `WIN32K!W32GetUserSessionState` at `0x14026e6df`
- `WIN32K!W32GetUserSessionState` at `0x14026e72c`
- `WIN32K!W32GetUserSessionState` at `0x14026e741`
- `WIN32K!W32GetUserSessionState` at `0x14026e754`
- `WIN32K!W32GetUserSessionState` at `0x14026e769`
- `WIN32K!W32GetUserSessionState` at `0x14026e782`
- `WIN32K!W32GetUserSessionState` at `0x14026e79d`
- `WIN32K!W32GetUserSessionState` at `0x14026e7b0`
- `WIN32K!W32GetUserSessionState` at `0x14026e7c9`
- `WIN32K!W32GetUserSessionState` at `0x14026e7de`
- `WIN32K!W32GetUserSessionState` at `0x14026e7f7`
- `WIN32K!W32GetUserSessionState` at `0x14026e815`
- `WIN32K!W32GetUserSessionState` at `0x14026e82a`
- `WIN32K!W32GetUserSessionState` at `0x14026e858`
- `WIN32K!W32GetUserSessionState` at `0x14026e93e`
- `WIN32K!W32GetUserSessionState` at `0x14026e955`
- `WIN32K!W32GetUserSessionState` at `0x14026ebed`

## pseudocode

```c
__int64 __fastcall xxxSetForegroundWindow2(ULONG_PTR *a1, ULONG_PTR a2, unsigned int a3)
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
  bool v23; // al
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  ULONG_PTR v27; // rcx
  __int64 v28; // rax
  int v29; // r8d
  int v30; // edx
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
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  ULONG_PTR v53; // r14
  struct tagTHREADINFO *v54; // rcx
  struct tagWND *v55; // rdx
  _QWORD **v56; // rdx
  _QWORD *v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rdx
  __int64 v69; // rcx
  const struct tagUIPI_INFO *v70; // r8
  __int64 v71; // r9
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 v79; // r9
  __m128i si128; // xmm0
  __m128i *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // rbx
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  __int64 v90; // r9
  __int64 v91; // rbx
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // r8
  __int64 v95; // r9
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // r9
  __int64 v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // r8
  __int64 v108; // r9
  ULONG_PTR v109; // rdx
  __int64 v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // r8
  __int64 v113; // r9
  __int64 v114; // rax
  __int64 v115; // rbx
  unsigned int v116; // ebx
  unsigned __int64 v117; // r13
  const struct tagWND *TopLevelWindow; // rax
  __int64 v119; // rcx
  __int64 v120; // rdx
  __int64 v121; // r8
  __int64 v122; // r9
  __int64 v123; // rcx
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 v126; // rax
  HANDLE ThreadId; // rax
  const struct tagWND *v128; // rcx
  __int64 v129; // rbx
  ULONG_PTR v130; // r8
  __int64 v131; // r13
  int v132; // eax
  bool v133; // zf
  char v134; // r13
  __int64 v135; // r12
  void *v136; // rdx
  unsigned int v137; // ecx
  unsigned __int64 v138; // r9
  unsigned int v139; // eax
  const struct tagWND *v140; // rcx
  __int64 v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // r8
  __int64 v144; // r9
  __int64 v145; // rdx
  __int64 v146; // rax
  BOOL v147; // ebx
  const struct tagWND *v148; // rax
  const struct tagWND *v149; // r15
  unsigned int v150; // eax
  bool v151; // [rsp+70h] [rbp-90h]
  bool v152; // [rsp+70h] [rbp-90h]
  bool v153; // [rsp+71h] [rbp-8Fh]
  bool v154; // [rsp+71h] [rbp-8Fh]
  struct tagWND *v156; // [rsp+80h] [rbp-80h]
  struct tagWND *v157; // [rsp+80h] [rbp-80h]
  unsigned int v158; // [rsp+80h] [rbp-80h]
  unsigned int v159; // [rsp+80h] [rbp-80h]
  struct tagQMSG *v161; // [rsp+90h] [rbp-70h]
  struct tagQMSG *v162; // [rsp+90h] [rbp-70h]
  ULONG_PTR v163; // [rsp+98h] [rbp-68h]
  __int64 v164; // [rsp+A0h] [rbp-60h] BYREF
  ULONG_PTR v165[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v166; // [rsp+B8h] [rbp-48h]
  ULONG_PTR v167[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v168; // [rsp+D0h] [rbp-30h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v170; // [rsp+E8h] [rbp-18h]
  __int64 v171; // [rsp+F0h] [rbp-10h] BYREF
  int v172; // [rsp+F8h] [rbp-8h]
  __int64 v173; // [rsp+100h] [rbp+0h] BYREF
  int v174; // [rsp+108h] [rbp+8h]

  *(_OWORD *)BugCheckParameter2 = 0;
  *(_OWORD *)v167 = 0;
  v170 = -1;
  v168 = -1;
  *(_OWORD *)v165 = 0;
  v166 = -1;
  v156 = PtiCurrent();
  v173 = 0;
  v174 = 0;
  v171 = 0;
  v172 = 0;
  v164 = 0;
  Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline();
  SetSystemInputSource(&v164);
  if ( !a1 )
    goto LABEL_22;
  if ( a1[3] == *(_QWORD *)(W32GetUserSessionState(v6, v5, v7, v8) + 19216) && *(char *)(a1[5] + 19) >= 0 )
  {
    if ( (unsigned int)IsWindowUnderActiveLockScreen(a1) )
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
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
      }
      goto LABEL_89;
    }
LABEL_22:
    if ( a2 )
      Win32RawLockedW32Thread::ManualLock((ULONG_PTR)BugCheckParameter2, a2);
    v23 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v151 = v23;
    v153 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v23 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      PsGetThreadId(*(PETHREAD *)v156);
      v27 = a2;
      if ( a2 )
        PsGetThreadId(*(PETHREAD *)a2);
      v28 = W32GetUserSessionState(v27, v24, v25, v26);
      LOBYTE(v29) = v153;
      LOBYTE(v30) = v151;
      WPP_RECORDER_AND_TRACE_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v30, v29, *(_QWORD *)(v28 + 69152));
    }
    v31 = WPP_GLOBAL_Control;
    v32 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v152 = v32;
    LOBYTE(v31) = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    v154 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v32 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v33 = W32GetUserSessionState(v31, v5, v7, v8);
      LOBYTE(v34) = v154;
      LOBYTE(v35) = v152;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v35,
        v34,
        *(_QWORD *)(v33 + 69152),
        4,
        2,
        93,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
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
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    v49 = 0;
    if ( !*(_QWORD *)(W32GetUserSessionState(v39, v36, v37, v38) + 18984)
      || (v50 = *(_QWORD *)(W32GetUserSessionState(v46, v45, v47, v48) + 18984),
          (_InterlockedCompareExchange((volatile signed __int32 *)(v50 + 520), 0, 0) & 1) != 0) )
    {
      v53 = 0;
    }
    else
    {
      v53 = *(_QWORD *)(W32GetUserSessionState(0, v50, v51, v52) + 18984);
      Win32RawLockedW32Thread::ManualLock((ULONG_PTR)v167, v53);
    }
    if ( a1 )
    {
      v163 = a1[2];
      SetNewForegroundQueue(*(_QWORD *)(v163 + 464), (a3 & 0x200 | 0x100) >> 8);
      Win32RawLockedW32Thread::ManualLock((ULONG_PTR)v165, v163);
      v54 = (struct tagTHREADINFO *)a1[2];
      v55 = (struct tagWND *)a1;
    }
    else
    {
      v163 = 0;
      ResetForegroundQueue(1);
      v54 = 0;
      v55 = 0;
    }
    xxxSetForegroundThreadWithWindowHint(v54, v55);
    if ( (a3 & 0x20) == 0 )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v57, v56, v58, v59) + 18968) )
      {
        v64 = *(_QWORD *)(W32GetUserSessionState(v61, v60, v62, v63) + 18968);
        LODWORD(v173) = *(_DWORD *)(v64 + 544);
        v61 = *(_QWORD *)(W32GetUserSessionState(v64, v65, v66, v67) + 18968);
        HIDWORD(v173) = *(_DWORD *)(v61 + 548);
      }
      if ( *(_QWORD *)(W32GetUserSessionState(v61, v60, v62, v63) + 18976) )
      {
        v72 = *(_QWORD *)(W32GetUserSessionState(v69, v68, v70, v71) + 18976);
        LODWORD(v171) = *(_DWORD *)(v72 + 544);
        HIDWORD(v171) = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v72, v73, v74, v75) + 18976) + 548LL);
      }
      if ( !UIPrivilegeIsolation::CheckAccess((UIPrivilegeIsolation *)&v173, (const struct tagUIPI_INFO *)&v171, v70) )
      {
        ClearKeyboardToggleStates();
        v57 = *(_QWORD **)(W32GetUserSessionState(v77, v76, v78, v79) + 19216);
        if ( *((_QWORD **)v156 + 61) == v57 )
        {
          v56 = (_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v57, v56, v58, v59) + 19216) + 176LL);
          v57 = *v56;
          if ( *v56 != v56 )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
            do
            {
              v81 = (__m128i *)*(v57 - 38);
              v81[20] = si128;
              v81[21] = si128;
              v81[31].m128i_i32[3] |= 1u;
              v57 = (_QWORD *)*v57;
            }
            while ( v57 != v56 );
          }
        }
      }
    }
    if ( *(_QWORD *)(W32GetUserSessionState(v57, v56, v58, v59) + 18968) )
    {
      v86 = *(_QWORD *)(W32GetUserSessionState(v83, v82, v84, v85) + 18968);
      if ( v86 != *(_QWORD *)(W32GetUserSessionState(v88, v87, v89, v90) + 18976) )
      {
        v83 = *(_QWORD *)(W32GetUserSessionState(v83, v82, v84, v85) + 18968);
        if ( *(_QWORD *)(v83 + 120) )
        {
          v83 = *(unsigned int *)(W32GetUserSessionState(v83, v82, v84, v85) + 66792);
          if ( (v83 & 0x80u) == 0LL )
            xxxApplyGlobalInputSettings(v83);
        }
      }
    }
    v91 = *(_QWORD *)(W32GetUserSessionState(v83, v82, v84, v85) + 18968);
    if ( v91 == *(_QWORD *)(W32GetUserSessionState(v93, v92, v94, v95) + 18976) )
      goto LABEL_153;
    if ( *(_QWORD *)(W32GetUserSessionState(v97, v96, v98, v99) + 18976) )
    {
      v101 = *(_QWORD *)(W32GetUserSessionState(v101, v100, v102, v103) + 18976);
      if ( *(_QWORD *)(v101 + 120) )
      {
        v104 = W32GetUserSessionState(v101, v100, v102, v103);
        zzzInputFocusLostWindowEvent(*(_QWORD *)(*(_QWORD *)(v104 + 18976) + 120LL), 1);
      }
    }
    if ( *(_QWORD *)(W32GetUserSessionState(v101, v100, v102, v103) + 18968)
      && *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v106, v105, v107, v108) + 18968) + 120LL) )
    {
      zzzInputFocusReceivedWindowEvent(1);
    }
    v109 = a2;
    if ( a2 )
    {
      xxxCancelTracking();
      v114 = W32GetUserSessionState(v111, v110, v112, v113);
      CCursorClip::ClearClip(*(CCursorClip **)(v114 + 36072));
      v109 = a2;
    }
    v115 = 0;
    if ( v53 && (_InterlockedCompareExchange((volatile signed __int32 *)(v53 + 520), 0, 0) & 1) == 0 )
      v115 = *(_QWORD *)(v53 + 464);
    if ( v109 )
      v49 = *(_QWORD *)(v109 + 464);
    v161 = 0;
    if ( v115 )
    {
      if ( v115 != v49 )
      {
        v161 = (struct tagQMSG *)AllocQEntryEx(v115 + 24, 0, 1);
        if ( !v161 )
          goto LABEL_89;
      }
      if ( v115 != v49 )
      {
        v117 = 0;
        if ( a1 )
        {
          TopLevelWindow = (const struct tagWND *)GetTopLevelWindow(a1);
          v157 = TopLevelWindow;
          if ( TopLevelWindow )
          {
            if ( (unsigned int)CoreWindowProp::IsComponent(TopLevelWindow) )
              v117 = CoreWindowProp::IsHostThreadOf((const struct tagTHREADINFO *)v53, v157) != 0;
          }
        }
        v119 = *(_QWORD *)(PtiKbdFromQ(v115) + 456);
        v158 = *(_DWORD *)(v119 + 268);
        if ( *(_QWORD *)(W32GetUserSessionState(v119, v120, v121, v122) + 18984) )
        {
          v126 = W32GetUserSessionState(v123, 0, v124, v125);
          ThreadId = PsGetThreadId(**(PETHREAD **)(v126 + 18984));
        }
        else
        {
          ThreadId = 0;
        }
        StoreQMessage(
          v161,
          0,
          0,
          (unsigned __int64)ThreadId,
          0,
          0,
          0,
          5u,
          v117,
          0,
          (const struct tagINPUT_MESSAGE_SOURCE *)&v164,
          v158,
          0,
          0);
        if ( v53 )
        {
          *((_QWORD *)v161 + 13) = v53;
          SetWakeBit(v53, 8256);
        }
        v128 = *(const struct tagWND **)(v115 + 128);
        if ( v128 && IsHungWindow(v128) )
          ProcessHungWindow(*(struct tagWND **)(v115 + 128));
      }
    }
    v129 = 0;
    if ( v163 && (_InterlockedCompareExchange((volatile signed __int32 *)(v163 + 520), 0, 0) & 1) == 0 )
      v129 = *(_QWORD *)(v163 + 464);
    v130 = a2;
    v131 = 0;
    if ( a2 )
      v131 = *(_QWORD *)(a2 + 464);
    if ( v129 )
    {
      v162 = 0;
      if ( v129 != v131 )
      {
        v162 = (struct tagQMSG *)AllocQEntryEx(v129 + 24, 0, 1);
        if ( !v162 )
        {
LABEL_89:
          v116 = 0;
LABEL_154:
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v165);
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v167);
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
          return v116;
        }
      }
      v132 = anonymous_namespace_::RemoveEventMessage(v129, 5);
      if ( v129 == v131 )
      {
        if ( a1 == *(ULONG_PTR **)(v131 + 128) )
        {
          anonymous_namespace_::xxxSendNCActivateMessage((struct tagWND *)a1);
          anonymous_namespace_::xxxUpdateTray((struct tagWND *)a1);
          v134 = a3;
          if ( (a3 & 4) == 0 )
            xxxSetWindowPos((struct tagWND *)a1, 0, 0, 3);
        }
        else
        {
          v134 = a3;
          if ( (a3 & 1) == 0 )
          {
            if ( v53 )
              PsGetThreadId(*(PETHREAD *)v53);
            anonymous_namespace_::xxxLocalActivateWindow((struct tagWND *)a1);
            if ( (*(_DWORD *)(W32GetUserSessionState(v142, v141, v143, v144) + 66788) & 1) != 0 )
              zzzActiveCursorTracking(a1);
            goto LABEL_153;
          }
        }
      }
      else
      {
        v133 = v131 == 0;
        v134 = a3;
        if ( !v133 || (a3 & 2) != 0 )
        {
          v135 = 0;
          if ( a1 )
            v135 = *a1;
        }
        else
        {
          v135 = 0;
        }
        if ( v132 )
          *(_DWORD *)(v129 + 508) |= 0x8000u;
        v137 = *(_DWORD *)(*(_QWORD *)(PtiKbdFromQ(v129) + 456) + 268LL);
        v159 = v137;
        if ( (a3 & 1) != 0 )
        {
          v138 = (unsigned __int64)v136;
        }
        else
        {
          if ( v53 )
          {
            v139 = (unsigned int)PsGetThreadId(*(PETHREAD *)v53);
            v137 = v159;
            v136 = 0;
          }
          else
          {
            v139 = (unsigned int)v136;
          }
          v138 = v139;
        }
        StoreQMessage(
          v162,
          0,
          (a3 >> 2) & 1,
          v138,
          v135,
          (unsigned int)v136,
          (unsigned __int64)v136,
          6u,
          (unsigned __int64)v136,
          (unsigned int)v136,
          (const struct tagINPUT_MESSAGE_SOURCE *)&v164,
          v137,
          v136,
          (struct tagUIPI_INFO *)v136);
        *((_QWORD *)v162 + 13) = v163;
        SetWakeBit(v163, 8256);
        v140 = *(const struct tagWND **)(v129 + 128);
        if ( v140 && IsHungWindow(v140) )
          ProcessHungWindow(*(struct tagWND **)(v129 + 128));
      }
      if ( (v134 & 0x40) == 0 )
        xxxDeliverRestoreFocusMessage((struct tagWND *)a1);
      v130 = a2;
    }
    v145 = 0;
    if ( v53 && (_InterlockedCompareExchange((volatile signed __int32 *)(v53 + 520), 0, 0) & 1) == 0 )
      v145 = *(_QWORD *)(v53 + 464);
    v146 = 0;
    if ( v130 )
      v146 = *(_QWORD *)(v130 + 464);
    if ( v145 && v145 == v146 )
    {
      v147 = 0;
      if ( a1 )
      {
        v148 = (const struct tagWND *)GetTopLevelWindow(a1);
        v149 = v148;
        if ( v148 && (unsigned int)CoreWindowProp::IsComponent(v148) )
          v147 = CoreWindowProp::IsHostThreadOf((const struct tagTHREADINFO *)v53, v149) != 0;
        v150 = (unsigned int)PsGetThreadId(*(PETHREAD *)a1[2]);
      }
      else
      {
        v150 = 0;
      }
      xxxDeactivate(a2, v150, v147);
    }
LABEL_153:
    v116 = 1;
    goto LABEL_154;
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
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
  }
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v165);
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v167);
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  return 0;
}

```

## disassembly

```asm
0x14026e0fc  mov     [rsp-8+arg_10], rbx
0x14026e101  push    rbp
0x14026e102  push    rsi
0x14026e103  push    rdi
0x14026e104  push    r12
0x14026e106  push    r13
0x14026e108  push    r14
0x14026e10a  push    r15
0x14026e10c  lea     rbp, [rsp-20h]
0x14026e111  sub     rsp, 120h
0x14026e118  mov     rax, cs:__security_cookie
0x14026e11f  xor     rax, rsp
0x14026e122  mov     [rbp+50h+var_40], rax
0x14026e126  xorps   xmm0, xmm0
0x14026e129  mov     [rsp+150h+var_DC], r8d
0x14026e12e  movups  xmmword ptr [rbp+50h+BugCheckParameter2], xmm0
0x14026e132  mov     [rbp+50h+var_C8], rdx
0x14026e136  mov     rsi, rcx
0x14026e139  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14026e13d  xorps   xmm0, xmm0
0x14026e140  movups  xmmword ptr [rbp+50h+var_90], xmm0
0x14026e144  mov     [rbp+50h+var_68], rcx
0x14026e148  mov     rbx, rdx
0x14026e14b  xorps   xmm0, xmm0
0x14026e14e  mov     [rbp+50h+var_80], rcx
0x14026e152  movups  xmmword ptr [rbp+50h+var_A8], xmm0
0x14026e156  mov     [rbp+50h+var_98], rcx
0x14026e15a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ
0x14026e15f  mov     [rbp+50h+var_D0], rax
0x14026e163  xor     eax, eax
0x14026e165  mov     [rbp+50h+var_50], rax
0x14026e169  mov     [rbp+50h+var_48], eax
0x14026e16c  mov     [rbp+50h+var_60], rax
0x14026e170  mov     [rbp+50h+var_58], eax
0x14026e173  mov     [rbp+50h+var_B0], 0
0x14026e17b  call    Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline
0x14026e180  lea     rcx, [rbp+50h+var_B0]
0x14026e184  call    cs:__imp_SetSystemInputSource
0x14026e18b  nop     dword ptr [rax+rax+00h]
0x14026e190  test    rsi, rsi
0x14026e193  jz      loc_14026E330
0x14026e199  call    cs:__imp_W32GetUserSessionState
0x14026e1a0  nop     dword ptr [rax+rax+00h]
0x14026e1a5  mov     rcx, [rax+4B10h]
0x14026e1ac  cmp     [rsi+18h], rcx
0x14026e1b0  jnz     loc_14026E271
0x14026e1b6  mov     rax, [rsi+28h]
0x14026e1ba  cmp     byte ptr [rax+13h], 0
0x14026e1be  jl      loc_14026E271
0x14026e1c4  mov     rcx, rsi
0x14026e1c7  call    IsWindowUnderActiveLockScreen
0x14026e1cc  test    eax, eax
0x14026e1ce  jz      loc_14026E330
0x14026e1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e1db  lea     rbx, WPP_GLOBAL_Control
0x14026e1e2  mov     edi, 1
0x14026e1e7  mov     r12b, 4
0x14026e1ea  lea     r15d, [rdi+1]
0x14026e1ee  cmp     rcx, rbx
0x14026e1f1  jz      short loc_14026E206
0x14026e1f3  mov     eax, [rcx+2Ch]
0x14026e1f6  test    r15b, al
0x14026e1f9  jz      short loc_14026E206
0x14026e1fb  cmp     [rcx+29h], r12b
0x14026e1ff  jb      short loc_14026E206
0x14026e201  mov     bl, dil
0x14026e204  jmp     short loc_14026E208
0x14026e206  xor     bl, bl
0x14026e208  lea     r14, WPP_RECORDER_INITIALIZED
0x14026e20f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14026e216  setnz   sil
0x14026e21a  test    bl, bl
0x14026e21c  jnz     short loc_14026E227
0x14026e21e  test    sil, sil
0x14026e221  jz      loc_14026E8D6
0x14026e227  call    cs:__imp_W32GetUserSessionState
0x14026e22e  nop     dword ptr [rax+rax+00h]
0x14026e233  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e23a  lea     r13, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x14026e241  mov     qword ptr [rsp+150h+var_118], r13
0x14026e246  mov     r8b, sil
0x14026e249  mov     word ptr [rsp+150h+var_120], 5Bh ; '['
0x14026e250  mov     dl, bl
0x14026e252  mov     r9, [rax+10E20h]
0x14026e259  mov     rcx, [rcx+18h]
0x14026e25d  mov     [rsp+150h+var_128], r15d
0x14026e262  mov     byte ptr [rsp+150h+var_130], r12b
0x14026e267  call    WPP_RECORDER_AND_TRACE_SF_
0x14026e26c  jmp     loc_14026E8D6
0x14026e271  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e278  lea     rbx, WPP_GLOBAL_Control
0x14026e27f  mov     edi, 1
0x14026e284  mov     r12b, 4
0x14026e287  lea     r15d, [rdi+1]
0x14026e28b  cmp     rcx, rbx
0x14026e28e  jz      short loc_14026E2A3
0x14026e290  mov     eax, [rcx+2Ch]
0x14026e293  test    r15b, al
0x14026e296  jz      short loc_14026E2A3
0x14026e298  cmp     [rcx+29h], r12b
0x14026e29c  jb      short loc_14026E2A3
0x14026e29e  mov     bl, dil
0x14026e2a1  jmp     short loc_14026E2A5
0x14026e2a3  xor     bl, bl
0x14026e2a5  lea     r14, WPP_RECORDER_INITIALIZED
0x14026e2ac  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14026e2b3  setnz   sil
0x14026e2b7  test    bl, bl
0x14026e2b9  jnz     short loc_14026E2C0
0x14026e2bb  test    sil, sil
0x14026e2be  jz      short loc_14026E305
0x14026e2c0  call    cs:__imp_W32GetUserSessionState
0x14026e2c7  nop     dword ptr [rax+rax+00h]
0x14026e2cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e2d3  lea     r13, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x14026e2da  mov     qword ptr [rsp+150h+var_118], r13
0x14026e2df  mov     r8b, sil
0x14026e2e2  mov     word ptr [rsp+150h+var_120], 5Ah ; 'Z'
0x14026e2e9  mov     dl, bl
0x14026e2eb  mov     r9, [rax+10E20h]
0x14026e2f2  mov     rcx, [rcx+18h]
0x14026e2f6  mov     [rsp+150h+var_128], r15d
0x14026e2fb  mov     byte ptr [rsp+150h+var_130], r12b
0x14026e300  call    WPP_RECORDER_AND_TRACE_SF_
0x14026e305  mov     dl, dil
0x14026e308  lea     rcx, [rbp+50h+var_A8]; BugCheckParameter2
0x14026e30c  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x14026e311  mov     dl, dil
0x14026e314  lea     rcx, [rbp+50h+var_90]; BugCheckParameter2
0x14026e318  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x14026e31d  mov     dl, dil
0x14026e320  lea     rcx, [rbp+50h+BugCheckParameter2]; BugCheckParameter2
0x14026e324  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x14026e329  xor     eax, eax
0x14026e32b  jmp     loc_14026ED31
0x14026e330  mov     edi, 1
0x14026e335  test    rbx, rbx
0x14026e338  jz      short loc_14026E346
0x14026e33a  mov     rdx, rbx; BugCheckParameter3
0x14026e33d  lea     rcx, [rbp+50h+BugCheckParameter2]; BugCheckParameter2
0x14026e341  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x14026e346  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e34d  lea     rbx, WPP_GLOBAL_Control
0x14026e354  mov     r12b, 4
0x14026e357  mov     r15d, 2
0x14026e35d  cmp     rcx, rbx
0x14026e360  jz      short loc_14026E375
0x14026e362  mov     eax, [rcx+2Ch]
0x14026e365  test    r15b, al
0x14026e368  jz      short loc_14026E375
0x14026e36a  cmp     [rcx+29h], r12b
0x14026e36e  jb      short loc_14026E375
0x14026e370  mov     al, dil
0x14026e373  jmp     short loc_14026E377
0x14026e375  xor     al, al
0x14026e377  lea     r14, WPP_RECORDER_INITIALIZED
0x14026e37e  mov     [rsp+150h+var_E0], al
0x14026e382  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14026e389  lea     r13, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x14026e390  setnz   cl
0x14026e393  mov     [rsp+150h+var_DF], cl
0x14026e397  test    al, al
0x14026e399  jnz     short loc_14026E3A3
0x14026e39b  test    cl, cl
0x14026e39d  jz      loc_14026E431
0x14026e3a3  mov     rcx, [rbp+50h+var_D0]
0x14026e3a7  mov     rcx, [rcx]; Thread
0x14026e3aa  call    cs:__imp_PsGetThreadId
0x14026e3b1  nop     dword ptr [rax+rax+00h]
0x14026e3b6  mov     rcx, [rbp+50h+var_C8]
0x14026e3ba  mov     [rbp+50h+var_C0], rax
0x14026e3be  test    rcx, rcx
0x14026e3c1  jz      short loc_14026E3D8
0x14026e3c3  mov     rcx, [rcx]; Thread
0x14026e3c6  call    cs:__imp_PsGetThreadId
0x14026e3cd  nop     dword ptr [rax+rax+00h]
0x14026e3d2  mov     [rbp+50h+var_B8], rax
0x14026e3d6  jmp     short loc_14026E3DF
0x14026e3d8  mov     dword ptr [rbp+50h+var_B8], 0
0x14026e3df  call    cs:__imp_W32GetUserSessionState
0x14026e3e6  nop     dword ptr [rax+rax+00h]
0x14026e3eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e3f2  mov     r8b, [rsp+150h+var_DF]
0x14026e3f7  mov     dl, [rsp+150h+var_E0]
0x14026e3fb  mov     r9, [rax+10E20h]
0x14026e402  mov     rax, [rbp+50h+var_C0]
0x14026e406  mov     rcx, [rcx+18h]
0x14026e40a  mov     dword ptr [rsp+150h+var_100], eax
0x14026e40e  mov     rax, [rbp+50h+var_B8]
0x14026e412  mov     [rsp+150h+var_108], eax
0x14026e416  mov     [rsp+150h+var_110], rsi
0x14026e41b  mov     qword ptr [rsp+150h+var_118], r13
0x14026e420  mov     word ptr [rsp+150h+var_120], 5Ch ; '\'
0x14026e427  mov     [rsp+150h+var_128], r15d
0x14026e42c  call    WPP_RECORDER_AND_TRACE_SF_qDD
0x14026e431  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e438  cmp     rcx, rbx
0x14026e43b  jz      short loc_14026E450
0x14026e43d  mov     eax, [rcx+2Ch]
0x14026e440  test    r15b, al
0x14026e443  jz      short loc_14026E450
0x14026e445  cmp     [rcx+29h], r12b
0x14026e449  jb      short loc_14026E450
0x14026e44b  mov     al, dil
0x14026e44e  jmp     short loc_14026E452
0x14026e450  xor     al, al
0x14026e452  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14026e459  mov     [rsp+150h+var_E0], al
0x14026e45d  setnz   cl
0x14026e460  mov     [rsp+150h+var_DF], cl
0x14026e464  test    al, al
0x14026e466  jnz     short loc_14026E46C
0x14026e468  test    cl, cl
0x14026e46a  jz      short loc_14026E4B6
0x14026e46c  call    cs:__imp_W32GetUserSessionState
0x14026e473  nop     dword ptr [rax+rax+00h]
0x14026e478  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e47f  mov     r8b, [rsp+150h+var_DF]
0x14026e484  mov     dl, [rsp+150h+var_E0]
0x14026e488  mov     r9, [rax+10E20h]
0x14026e48f  mov     eax, [rsp+150h+var_DC]
0x14026e493  mov     rcx, [rcx+18h]
0x14026e497  mov     dword ptr [rsp+150h+var_110], eax
0x14026e49b  mov     qword ptr [rsp+150h+var_118], r13
0x14026e4a0  mov     word ptr [rsp+150h+var_120], 5Dh ; ']'
0x14026e4a7  mov     [rsp+150h+var_128], r15d
0x14026e4ac  mov     byte ptr [rsp+150h+var_130], r12b
0x14026e4b1  call    WPP_RECORDER_AND_TRACE_SF_D
0x14026e4b6  call    cs:__imp_W32GetUserSessionState
0x14026e4bd  nop     dword ptr [rax+rax+00h]
0x14026e4c2  mov     qword ptr [rax+49F0h], 0
0x14026e4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e4d4  cmp     rcx, rbx
0x14026e4d7  jz      short loc_14026E4EC
0x14026e4d9  mov     eax, [rcx+2Ch]
0x14026e4dc  test    r15b, al
0x14026e4df  jz      short loc_14026E4EC
0x14026e4e1  cmp     [rcx+29h], r12b
0x14026e4e5  jb      short loc_14026E4EC
0x14026e4e7  mov     bl, dil
0x14026e4ea  jmp     short loc_14026E4EE
0x14026e4ec  xor     bl, bl
0x14026e4ee  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14026e4f5  setnz   r14b
0x14026e4f9  test    bl, bl
0x14026e4fb  jnz     short loc_14026E502
0x14026e4fd  test    r14b, r14b
0x14026e500  jz      short loc_14026E540
0x14026e502  call    cs:__imp_W32GetUserSessionState
0x14026e509  nop     dword ptr [rax+rax+00h]
0x14026e50e  mov     rcx, cs:WPP_GLOBAL_Control
0x14026e515  mov     r8b, r14b
0x14026e518  mov     qword ptr [rsp+150h+var_118], r13
0x14026e51d  mov     dl, bl
0x14026e51f  mov     word ptr [rsp+150h+var_120], 5Eh ; '^'
0x14026e526  mov     r9, [rax+10E20h]
0x14026e52d  mov     rcx, [rcx+18h]
0x14026e531  mov     [rsp+150h+var_128], r15d
0x14026e536  mov     byte ptr [rsp+150h+var_130], r12b
0x14026e53b  call    WPP_RECORDER_AND_TRACE_SF_
0x14026e540  call    cs:__imp_W32GetUserSessionState
0x14026e547  nop     dword ptr [rax+rax+00h]
0x14026e54c  xor     r13d, r13d
0x14026e54f  cmp     [rax+4A28h], r13
0x14026e556  jz      short loc_14026E59E
0x14026e558  call    cs:__imp_W32GetUserSessionState
0x14026e55f  nop     dword ptr [rax+rax+00h]
0x14026e564  mov     ecx, r13d
0x14026e567  mov     rdx, [rax+4A28h]
0x14026e56e  xor     eax, eax
0x14026e570  lock cmpxchg [rdx+208h], ecx
0x14026e578  test    dil, al
0x14026e57b  jnz     short loc_14026E59E
0x14026e57d  call    cs:__imp_W32GetUserSessionState
0x14026e584  nop     dword ptr [rax+rax+00h]
0x14026e589  lea     rcx, [rbp+50h+var_90]; BugCheckParameter2
0x14026e58d  mov     r14, [rax+4A28h]
0x14026e594  mov     rdx, r14; BugCheckParameter3
0x14026e597  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x14026e59c  jmp     short loc_14026E5A1
0x14026e59e  mov     r14, r13
0x14026e5a1  test    rsi, rsi
0x14026e5a4  jz      short loc_14026E5E0
0x14026e5a6  mov     rbx, [rsi+10h]
0x14026e5aa  mov     edx, [rsp+150h+var_DC]
0x14026e5ae  and     edx, 200h
0x14026e5b4  mov     [rbp+50h+var_B8], rbx
0x14026e5b8  bts     edx, 8
0x14026e5bc  mov     rcx, [rbx+1D0h]
0x14026e5c3  shr     edx, 8
0x14026e5c6  call    ?SetNewForegroundQueue@@YAXPEAUtagQ@@W4SetFgQueueOption@@@Z
0x14026e5cb  mov     rdx, rbx; BugCheckParameter3
0x14026e5ce  lea     rcx, [rbp+50h+var_A8]; BugCheckParameter2
0x14026e5d2  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x14026e5d7  mov     rcx, [rsi+10h]
0x14026e5db  mov     rdx, rsi
0x14026e5de  jmp     short loc_14026E5F1
0x14026e5e0  mov     ecx, edi
0x14026e5e2  mov     [rbp+50h+var_B8], r13
0x14026e5e6  call    ?ResetForegroundQueue@@YAXW4SetFgQueueOption@@@Z
  ... truncated ...
```
