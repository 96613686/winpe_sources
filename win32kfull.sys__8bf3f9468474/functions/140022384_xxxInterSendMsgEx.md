# xxxInterSendMsgEx

- ea: `0x140022384`
- end: `0x1400239eb`
- name: `xxxInterSendMsgEx`
- size: `5735`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, __int64, ULONG_PTR, int, __int64, __int64, int, int)`
- caller_count: `8`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140021d30`
- `0x140027d44`
- `0x140033a90`
- `0x140033bb0`
- `0x1400c459c`
- `0x140188ea0`
- `0x140197ffc`
- `0x140199ef4`

## callees

- `0x140004cbc`
- `0x140011784`
- `0x14001cb40`
- `0x14001cbf0`
- `0x14001ec90`
- `0x140022384`
- `0x140030930`
- `0x140033080`
- `0x140033e0c`
- `0x1400ba610`
- `0x1400bcaa0`
- `0x1400c03f4`
- `0x1400c2a10`
- `0x1400c55ac`
- `0x1400c5644`
- `0x14010a278`
- `0x140121f70`
- `0x14014eb20`
- `0x140163460`
- `0x14017c55c`
- `0x14017ee14`
- `0x1401b0fec`
- `0x1401b20d0`
- `0x1401b7db0`
- `0x1401ec2fc`
- `0x1402a72f4`
- `0x1402b14a0`
- `0x140341ff0`
- `0x140342240`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x140022491`
- `ntoskrnl!IoGetStackLimits` at `0x140022491`
- `ntoskrnl!PsGetProcessCommonJob` at `0x1400227f5`
- `ntoskrnl!PsGetProcessCommonJob` at `0x1400227f5`
- `ntoskrnl!MmIsKernelAddress` at `0x140022adc`
- `ntoskrnl!MmIsKernelAddress` at `0x140022c14`
- `ntoskrnl!MmIsKernelAddress` at `0x140022c92`
- `ntoskrnl!MmIsKernelAddress` at `0x140022cc4`
- `ntoskrnl!MmIsKernelAddress` at `0x140022adc`
- `ntoskrnl!MmIsKernelAddress` at `0x140022c14`
- `ntoskrnl!MmIsKernelAddress` at `0x140022c92`
- `ntoskrnl!MmIsKernelAddress` at `0x140022cc4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140023195`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140023195`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140022417`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140022417`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400227e3`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400227e3`
- `win32kbase!?ReferenceMsgDataExternal@CTouchProcessor@@QEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z` at `0x1400233b5`
- `win32kbase!?ReferenceMsgDataExternal@CTouchProcessor@@QEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z` at `0x1400233b5`
- `win32kbase!UserCheckForMessageAccessWithWindowCapability` at `0x14002273d`
- `win32kbase!UserCheckForMessageAccessWithWindowCapability` at `0x14002273d`
- `win32kbase!EtwTraceBeginSendMessage` at `0x1400233cf`
- `win32kbase!EtwTraceBeginSendMessage` at `0x1400233cf`
- `win32kbase!EtwTraceEndSendMessage` at `0x1400233f2`
- `win32kbase!EtwTraceEndSendMessage` at `0x1400238aa`
- `win32kbase!EtwTraceEndSendMessage` at `0x1400233f2`
- `win32kbase!EtwTraceEndSendMessage` at `0x1400238aa`
- `win32kbase!EtwTraceConvertTimeOutToBlocking` at `0x140023609`
- `win32kbase!EtwTraceConvertTimeOutToBlocking` at `0x140023609`
- `win32kbase!EtwTraceUIPIMsgError` at `0x140022717`
- `win32kbase!EtwTraceUIPIMsgError` at `0x140022717`
- `win32kbase!?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ` at `0x14002278d`
- `win32kbase!?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ` at `0x14002278d`
- `win32kbase!Win32AllocateFromPagedLookasideList` at `0x14002287b`
- `win32kbase!Win32AllocateFromPagedLookasideList` at `0x14002287b`
- `win32kbase!HMChangeOwnerThread` at `0x1400232bd`
- `win32kbase!HMChangeOwnerThread` at `0x1400232bd`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140023224`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140023224`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400226aa`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400226aa`
- `win32kbase!IsWindowDesktopComposed` at `0x140023061`
- `win32kbase!IsWindowDesktopComposed` at `0x14002379e`
- `win32kbase!IsWindowDesktopComposed` at `0x14002386b`
- `win32kbase!IsWindowDesktopComposed` at `0x140023061`
- `win32kbase!IsWindowDesktopComposed` at `0x14002379e`
- `win32kbase!IsWindowDesktopComposed` at `0x14002386b`
- `win32kbase!_HMObjectFromHandle` at `0x14002329d`
- `win32kbase!_HMObjectFromHandle` at `0x14002329d`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x140022d1b`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x140022d1b`
- `win32kbase!HMAssignmentLock` at `0x1400230e0`
- `win32kbase!HMAssignmentLock` at `0x1400230e0`
- `win32kbase!Win32FreePool` at `0x1400239a8`
- `win32kbase!Win32FreePool` at `0x1400239a8`
- `WIN32K!W32GetUserGdiSessionState` at `0x140022641`
- `WIN32K!W32GetUserGdiSessionState` at `0x140022641`
- `WIN32K!W32GetUserSessionState` at `0x14002250c`
- `WIN32K!W32GetUserSessionState` at `0x140022868`
- `WIN32K!W32GetUserSessionState` at `0x1400231c0`
- `WIN32K!W32GetUserSessionState` at `0x140023394`
- `WIN32K!W32GetUserSessionState` at `0x14002250c`
- `WIN32K!W32GetUserSessionState` at `0x140022868`
- `WIN32K!W32GetUserSessionState` at `0x1400231c0`
- `WIN32K!W32GetUserSessionState` at `0x140023394`

## pseudocode

```c
__int64 __fastcall xxxInterSendMsgEx(
        struct tagWND *a1,
        unsigned int a2,
        __int64 a3,
        ULONG_PTR a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9)
{
  ULONG_PTR v9; // r15
  struct tagWND *v11; // rbx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rsi
  int v22; // ebx
  int v23; // ebx
  const struct tagUIPI_INFO *v24; // r8
  const struct tagUIPI_INFO *v25; // rdx
  bool v26; // al
  __int64 v27; // r15
  void **v28; // r14
  __int64 v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rsi
  __int64 v35; // rbx
  __int64 CurrentProcess; // rax
  __int64 UserSessionState; // rax
  __int64 v38; // rax
  char *v39; // r12
  void **v40; // r15
  unsigned int v41; // esi
  unsigned __int64 v42; // rcx
  bool v43; // zf
  int v45; // eax
  bool v46; // zf
  bool v47; // zf
  _OWORD *v48; // r9
  unsigned __int64 v49; // rax
  void *v50; // rcx
  size_t v51; // r8
  const void *v52; // rdx
  void **v53; // rdx
  __int64 v54; // rcx
  _OWORD *v55; // rax
  bool v56; // zf
  unsigned int v57; // edx
  const void *v58; // rdx
  size_t v59; // r8
  __int64 v60; // rbx
  void *v61; // rbx
  size_t v62; // r8
  __int64 v63; // rsi
  int v64; // ecx
  _QWORD *v65; // rsi
  __int64 v66; // rdx
  struct tagWND *v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  int *v70; // rbx
  struct tagHIDDATA *v71; // rax
  __int64 v72; // rax
  ULONG_PTR *v73; // rsi
  __int64 v74; // r14
  __int64 v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rdx
  int v78; // ecx
  __int64 v79; // rax
  _QWORD *v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rax
  int v86; // esi
  unsigned int v87; // r15d
  __int64 v88; // r14
  __int64 v89; // r8
  char v90; // r12
  __int64 v91; // rdx
  struct tagTHREADINFO *v92; // rax
  int v93; // eax
  int v94; // r15d
  int v95; // ecx
  int v96; // ecx
  unsigned int v97; // ecx
  struct tagTHREADINFO *v98; // rax
  int v99; // ecx
  int v100; // eax
  _QWORD *v101; // r9
  __int16 *v102; // rdx
  unsigned int v103; // ecx
  __int16 v104; // ax
  void *v105; // r14
  _QWORD *v106; // r15
  __int64 v107; // r14
  __int128 *v108; // rax
  __int128 v109; // xmm0
  __int64 v110; // rcx
  __int64 v111; // rdx
  __int64 v112; // r14
  __int64 v113; // rdx
  __int64 v114; // r14
  int v115; // eax
  _QWORD *v116; // rdx
  __int64 v117; // rcx
  _QWORD *v118; // rax
  int v119; // ecx
  unsigned int Size; // [rsp+44h] [rbp-174h]
  __int64 v122; // [rsp+58h] [rbp-160h]
  void **v123; // [rsp+60h] [rbp-158h]
  void *v124; // [rsp+60h] [rbp-158h]
  void **v125; // [rsp+68h] [rbp-150h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+70h] [rbp-148h] BYREF
  __int64 v127; // [rsp+80h] [rbp-138h]
  unsigned __int64 LowLimit; // [rsp+88h] [rbp-130h] BYREF
  struct tagWND *v129; // [rsp+90h] [rbp-128h]
  unsigned int v130; // [rsp+98h] [rbp-120h]
  unsigned __int64 v131; // [rsp+A0h] [rbp-118h]
  unsigned int v132; // [rsp+A8h] [rbp-110h]
  int v133; // [rsp+ACh] [rbp-10Ch]
  char *v134; // [rsp+B0h] [rbp-108h] BYREF
  void *Src[2]; // [rsp+B8h] [rbp-100h] BYREF
  void *v136; // [rsp+C8h] [rbp-F0h]
  unsigned int v137; // [rsp+D0h] [rbp-E8h]
  int v138; // [rsp+D8h] [rbp-E0h]
  __int64 v139; // [rsp+E0h] [rbp-D8h] BYREF
  unsigned __int64 HighLimit; // [rsp+E8h] [rbp-D0h] BYREF
  void *v141; // [rsp+F0h] [rbp-C8h]
  __int64 v142; // [rsp+F8h] [rbp-C0h]
  void **v143; // [rsp+100h] [rbp-B8h]
  __int16 *v144; // [rsp+108h] [rbp-B0h]
  void *v145; // [rsp+110h] [rbp-A8h]
  char *v146; // [rsp+118h] [rbp-A0h]
  __int64 v147; // [rsp+120h] [rbp-98h]
  char *v148; // [rsp+128h] [rbp-90h]
  _DWORD *v149; // [rsp+130h] [rbp-88h]
  _BYTE v150[24]; // [rsp+148h] [rbp-70h] BYREF
  __int64 v151; // [rsp+160h] [rbp-58h] BYREF
  struct tagWND *v152; // [rsp+168h] [rbp-50h]

  v9 = a4;
  BugCheckParameter3[0] = a4;
  v11 = a1;
  v129 = a1;
  v127 = a7;
  v139 = a3;
  v125 = (void **)a4;
  v147 = a7;
  *(_OWORD *)Src = 0;
  v133 = 0;
  v138 = 0;
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
  v13 = CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
    v13 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
  v131 = (unsigned __int64)PtiCurrent();
  v14 = v131 & -(__int64)(a5 != 0);
  v122 = v14;
  if ( v14 && (_InterlockedCompareExchange((volatile signed __int32 *)(v14 + 520), 0, 0) & 1) != 0 )
    return 0;
  HighLimit = 0;
  LowLimit = 0;
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( (unsigned __int64)&HighLimit - LowLimit < 0x2000 )
    return 0;
  if ( !v11 || *(_QWORD *)(*((_QWORD *)v11 + 2) + 456LL) == v13 )
    goto LABEL_28;
  if ( a2 > 0xD0 )
  {
    if ( a2 != 272 )
    {
      if ( a2 == 353 || a2 == 424 || a2 == 563 || a2 == 648 )
        goto LABEL_28;
      goto LABEL_24;
    }
  }
  else
  {
    if ( a2 == 208 || a2 == 12 )
      goto LABEL_28;
    if ( a2 == 13 )
    {
LABEL_16:
      v15 = *(_QWORD *)(W32GetUserSessionState(v16, v15, v17, v18) + 19704);
      if ( *(_WORD *)(v15 + 870) == *(_WORD *)(*(_QWORD *)(*((_QWORD *)v11 + 17) + 8LL) + 2LL)
        && (*(_BYTE *)(*((_QWORD *)v11 + 5) + 28LL) & 0x20) != 0 )
      {
        UserSetLastError(5);
LABEL_27:
        UserSetLastError(5);
        return 0;
      }
LABEL_24:
      v19 = 0;
      goto LABEL_26;
    }
    if ( a2 != 78 )
    {
      if ( a2 == 188 )
        goto LABEL_28;
      if ( a2 != 196 && a2 != 204 )
        goto LABEL_24;
      goto LABEL_16;
    }
  }
  v19 = 1;
LABEL_26:
  if ( v19 )
    goto LABEL_27;
LABEL_28:
  if ( a8 )
    goto LABEL_60;
  if ( v11 )
  {
    v20 = *((_QWORD *)v11 + 2);
  }
  else
  {
    v21 = 0;
    v20 = a6;
    if ( !a6 )
      goto LABEL_33;
  }
  v21 = *(_QWORD *)(v20 + 456);
LABEL_33:
  if ( v21 == v13 )
    goto LABEL_60;
  if ( a2 != 717 )
  {
    v22 = IsMessageAllowedAcrossILByReceiver((struct tagPROCESSINFO *)v21, v11, a2);
    if ( !v22 )
      v22 = IsMessageAlwaysAllowedAcrossIL(a2);
    if ( v22 )
      goto LABEL_60;
    if ( a2 != 274 || ((a3 - 61472) & 0xFFFFFFFFFFFFFEBFuLL) != 0 || a3 == 61792 )
    {
      if ( (unsigned int)Feature_MsgUseCSRSSTrueIL__private_IsEnabledDeviceUsageNoInline() )
      {
        v25 = (const struct tagUIPI_INFO *)(v21 + 864);
      }
      else
      {
        v151 = 0;
        LODWORD(v152) = 0;
        if ( *(_QWORD *)v21 == *(_QWORD *)(W32GetUserGdiSessionState() + 40) )
        {
          v151 = 0x2000;
          LODWORD(v152) = 0;
        }
        else
        {
          v151 = *(_QWORD *)(v21 + 864);
          LODWORD(v152) = *(_DWORD *)(v21 + 872);
        }
        v25 = (const struct tagUIPI_INFO *)&v151;
      }
      v26 = UIPrivilegeIsolation::CheckAccess((UIPrivilegeIsolation *)(v13 + 864), v25, v24);
      v23 = v26;
      if ( v26 )
        goto LABEL_60;
      if ( v129 && a2 == 793 )
      {
        v27 = *((_QWORD *)v129 + 2);
        if ( *(struct tagWND **)(v27 + 1584) == v129 && *(_QWORD *)(v27 + 464) == *((_QWORD *)PtiCurrent() + 58) )
          v23 = 1;
        v9 = BugCheckParameter3[0];
      }
      if ( v23 )
        goto LABEL_60;
      EtwTraceUIPIMsgError(v13, v21, a2, a3, v9);
      UserSetLastError(5);
    }
    else
    {
      v23 = 1;
    }
    if ( v23 )
      goto LABEL_60;
    v11 = v129;
  }
  if ( !UserCheckForMessageAccessWithWindowCapability(v11, a2) )
    return 0;
LABEL_60:
  v28 = (void **)BugCheckParameter3[0];
  if ( a2 == 576 )
  {
    LOBYTE(v15) = 20;
  }
  else
  {
    if ( a2 != 281 )
      goto LABEL_65;
    LOBYTE(v15) = 21;
  }
  if ( !HMValidateHandleWithDescriptor(BugCheckParameter3[0], v15) )
    return 0;
LABEL_65:
  v29 = a6;
  if ( !tagPROCESSINFO::SyncAndTestFreeze(*(tagPROCESSINFO **)(a6 + 456)) )
    goto LABEL_80;
  v31 = v127;
  if ( v127 )
  {
    if ( (*(_DWORD *)(v127 + 32) & 0x40) != 0 )
    {
      v34 = v122;
      goto LABEL_74;
    }
    if ( *(_DWORD *)v127 == 2 && *(_DWORD *)(v127 + 36) )
      return 0;
  }
  v34 = v122;
  if ( v122 )
  {
    v35 = **(_QWORD **)(a6 + 456);
    CurrentProcess = PsGetCurrentProcess();
    if ( !PsGetProcessCommonJob(CurrentProcess, v35) )
      return 0;
    v31 = v127;
    v29 = a6;
LABEL_74:
    if ( v34 )
      goto LABEL_80;
  }
  if ( !v31 && (a2 == 537 || !(unsigned int)ProcessSuspendedSendMessage(v29, v129, a2, a3, BugCheckParameter3[0]))
    || !v34 && *(_DWORD *)(v29 + 568) > 0x2710u )
  {
    return 0;
  }
LABEL_80:
  UserSessionState = W32GetUserSessionState(v31, v30, v32, v33);
  v38 = Win32AllocateFromPagedLookasideList(*(_QWORD *)(UserSessionState + 69080));
  v39 = (char *)v38;
  v134 = (char *)v38;
  if ( !v38 )
    return 0;
  v142 = v38;
  LowLimit = 0;
  v40 = 0;
  v136 = 0;
  *(_QWORD *)(v38 + 120) = 0;
  Size = 0;
  v41 = 0;
  v123 = v28;
  v42 = v131;
  *(_DWORD *)(v38 + 128) = *(_DWORD *)(v131 + 1604);
  if ( !v127 || *(_DWORD *)v127 != 33 )
  {
    if ( a2 > 0x14D )
    {
      if ( a2 > 0x1A2 )
      {
        if ( a2 == 536 )
        {
          if ( v28 && (a3 & 0x8000) != 0 && (!(unsigned __int8)MmIsKernelAddress(v28) || !v122) )
          {
            v41 = *((_DWORD *)v28 + 4) + 20;
            if ( *((_DWORD *)v28 + 4) >= 0xFFFFFFEC )
              goto LABEL_137;
          }
          goto LABEL_176;
        }
        if ( a2 != 537 )
        {
          if ( a2 == 544 )
          {
            v41 = (*((_DWORD *)v28 + 15) & 0x7FFFFFFF) + (*((_DWORD *)v28 + 19) & 0x7FFFFFFF);
            v40 = v28;
            goto LABEL_176;
          }
          if ( a2 == 643 )
          {
            if ( a3 == 24 )
              v41 = (*(_DWORD *)v28 << 9) + 4;
            goto LABEL_176;
          }
          if ( a2 == 780 )
            goto LABEL_159;
          if ( a2 == 833 )
          {
            v45 = 104;
          }
          else
          {
            if ( a2 == 834 )
            {
              v41 = 80;
              goto LABEL_177;
            }
            if ( a2 != 836 )
            {
              if ( a2 == 838 )
                v41 = 96;
              goto LABEL_176;
            }
            v45 = 1204;
          }
          v41 = v45;
LABEL_106:
          Size = v45;
          goto LABEL_176;
        }
        if ( !v28 || (a3 & 0x8000) == 0 || (unsigned __int8)MmIsKernelAddress(v28) && v122 )
          goto LABEL_176;
        goto LABEL_169;
      }
      if ( a2 == 418 )
        goto LABEL_132;
      if ( a2 > 0x18D )
      {
        if ( a2 != 399 )
        {
          if ( a2 != 401 && a2 != 402 )
          {
            v43 = a2 == 406;
LABEL_153:
            if ( !v43 )
              goto LABEL_176;
            goto LABEL_134;
          }
          goto LABEL_114;
        }
LABEL_132:
        v46 = *(_DWORD *)(v42 + 1604) == 1;
LABEL_133:
        if ( v46 )
          goto LABEL_176;
        goto LABEL_134;
      }
      if ( a2 != 397 )
      {
        if ( a2 == 344 || a2 == 384 || a2 == 385 )
          goto LABEL_132;
        if ( a2 == 393 )
          goto LABEL_159;
        v47 = a2 == 396;
        goto LABEL_131;
      }
    }
    else
    {
      if ( a2 == 333 )
        goto LABEL_132;
      if ( a2 <= 0x53 )
      {
        if ( a2 != 83 )
        {
          if ( a2 <= 0x38 )
          {
            if ( a2 == 56 )
            {
              v41 = *(unsigned __int16 *)v28;
              goto LABEL_176;
            }
            if ( a2 != 1 )
            {
              if ( a2 != 12 )
              {
                if ( a2 != 13 )
                {
                  if ( a2 != 26 )
                  {
                    v43 = a2 == 27;
                    goto LABEL_153;
                  }
                  goto LABEL_115;
                }
LABEL_159:
                *(_OWORD *)Src = *(_OWORD *)v28;
                v133 = (SHIDWORD(Src[0]) >= 0) + 1;
                v138 = v133;
                v28 = Src;
                BugCheckParameter3[0] = (ULONG_PTR)Src;
                v125 = Src;
                if ( !(unsigned __int8)MmIsKernelAddress(_mm_srli_si128(*(__m128i *)Src, 8).m128i_u64[0]) || !v122 )
                  v41 = HIDWORD(Src[0]) & 0x7FFFFFFF;
                goto LABEL_176;
              }
LABEL_115:
              v46 = v28 == 0;
              goto LABEL_133;
            }
LABEL_117:
            UserSetLastError(5);
            FreeSMS(v39, 1);
            return 0;
          }
          if ( a2 != 70 && a2 != 71 )
          {
            if ( a2 == 73 )
            {
              v41 = a3;
            }
            else if ( a2 == 74 )
            {
              LowLimit = (unsigned __int64)v28;
              if ( v28[2] )
              {
                v41 = *((_DWORD *)v28 + 2) + 24;
                if ( v41 < 0x18 )
                {
                  FreeSMS(v38, 1);
                  return 0;
                }
              }
              else
              {
                v41 = 24;
              }
            }
            goto LABEL_176;
          }
          v41 = 40;
          goto LABEL_105;
        }
LABEL_169:
        v41 = *(_DWORD *)v28;
        goto LABEL_176;
      }
      if ( a2 <= 0x143 )
      {
        if ( a2 != 323 )
        {
          switch ( a2 )
          {
            case 0x81u:
              goto LABEL_117;
            case 0x83u:
              v41 = a3 != 0 ? 96 : 16;
LABEL_105:
              v45 = v41;
              goto LABEL_106;
            case 0xC2u:
              goto LABEL_115;
            case 0xC4u:
              goto LABEL_159;
          }
          if ( a2 != 203 )
            goto LABEL_176;
LABEL_114:
          v41 = 4 * a3;
          goto LABEL_176;
        }
        goto LABEL_132;
      }
      if ( a2 != 325 )
      {
        if ( a2 == 328 )
          goto LABEL_159;
        if ( a2 == 330 )
          goto LABEL_132;
        v47 = a2 == 332;
LABEL_131:
        if ( !v47 )
          goto LABEL_176;
        goto LABEL_132;
      }
    }
LABEL_134:
    *(_OWORD *)Src = *(_OWORD *)v28;
    if ( !(unsigned __int8)MmIsKernelAddress(_mm_srli_si128(*(__m128i *)Src, 8).m128i_u64[0]) || !v122 )
    {
      v41 = LODWORD(Src[0]) + 18;
      if ( (unsigned int)(LODWORD(Src[0]) + 18) < LODWORD(Src[0]) )
      {
LABEL_137:
        FreeSMS(v39, 1);
        return 8;
      }
    }
LABEL_176:
    if ( !v41 )
      goto LABEL_209;
LABEL_177:
    v48 = (_OWORD *)Win32AllocPoolWithQuotaZInit(v41, 1668510549);
    *((_QWORD *)v39 + 15) = v48;
    if ( !v48 )
      goto LABEL_209;
    v136 = v28;
    v143 = v28;
    if ( a2 > 0x14C )
    {
      if ( a2 > 0x18D )
      {
        switch ( a2 )
        {
          case 0x18Fu:
            goto LABEL_207;
          case 0x191u:
            Size = v41;
            break;
          case 0x196u:
          case 0x1A2u:
            goto LABEL_207;
          case 0x220u:
            v58 = v40[10];
            if ( v58 )
            {
              v59 = *((unsigned int *)v40 + 19);
              LODWORD(v59) = v59 & 0x7FFFFFFF;
              memmove(v48, v58, v59);
              *v40 = (void *)*((_QWORD *)v39 + 15);
            }
            if ( *((_DWORD *)v40 + 14) )
            {
              v60 = *((unsigned int *)v40 + 19);
              LODWORD(v60) = v60 & 0x7FFFFFFF;
              v61 = (void *)(*((_QWORD *)v39 + 15) + v60);
              v62 = *((unsigned int *)v40 + 15);
              LODWORD(v62) = v62 & 0x7FFFFFFF;
              memmove(v61, v40[8], v62);
              v40[1] = v61;
            }
            goto LABEL_209;
          case 0x30Cu:
            goto LABEL_218;
        }
LABEL_224:
        v53 = v123;
        goto LABEL_225;
      }
      if ( a2 == 397 || a2 == 333 || a2 == 344 || a2 == 384 || a2 == 385 )
        goto LABEL_207;
      if ( a2 == 393 )
        goto LABEL_218;
      v56 = a2 == 396;
    }
    else
    {
      if ( a2 == 332 )
        goto LABEL_207;
      if ( a2 <= 0x83 )
      {
        if ( a2 == 131 )
        {
          v53 = v123;
          if ( a3 )
          {
            *v48 = *(_OWORD *)v123;
            v48[1] = *((_OWORD *)v123 + 1);
            v48[2] = *((_OWORD *)v123 + 2);
            *((_QWORD *)v48 + 6) = v123[6];
            v54 = *((_QWORD *)v39 + 15) + 56LL;
            *((_QWORD *)v48 + 6) = v54;
            v55 = v123[6];
            *(_OWORD *)v54 = *v55;
            *(_OWORD *)(v54 + 16) = v55[1];
            *(_QWORD *)(v54 + 32) = *((_QWORD *)v55 + 4);
LABEL_226:
            v28 = (void **)*((_QWORD *)v39 + 15);
            BugCheckParameter3[0] = (ULONG_PTR)v28;
            v125 = v28;
LABEL_209:
            if ( v41 && !*((_QWORD *)v39 + 15) )
            {
              FreeSMS(v39, 1);
              return 0;
            }
            if ( a9 )
            {
              v63 = (__int64)v129;
              if ( v129 )
              {
                if ( (unsigned int)IsWindowDesktopComposed(v129) && !(unsigned int)IsPointerInputMessage(a2) )
                {
                  TransformMessageBetweenCoordinateSpaces(v64, 1, (unsigned int)&v139, (unsigned int)&v125, v63, 0);
                  v28 = v125;
                  BugCheckParameter3[0] = (ULONG_PTR)v125;
                }
              }
            }
            goto LABEL_232;
          }
LABEL_225:
          memmove(v48, v53, v41);
          goto LABEL_226;
        }
        if ( a2 == 12 )
          goto LABEL_207;
        if ( a2 != 13 )
        {
          if ( a2 != 26 && a2 != 27 )
          {
            if ( a2 == 74 )
            {
              v28 = (void **)v48;
              BugCheckParameter3[0] = (ULONG_PTR)v48;
              v125 = (void **)v48;
              v49 = LowLimit;
              *v48 = *(_OWORD *)LowLimit;
              *((_QWORD *)v48 + 2) = *(_QWORD *)(v49 + 16);
              if ( !*(_QWORD *)(v49 + 16) )
                goto LABEL_209;
              v50 = (char *)v48 + 24;
              *((_QWORD *)v48 + 2) = (char *)v48 + 24;
              v51 = *(unsigned int *)(v49 + 8);
              v52 = *(const void **)(v49 + 16);
              goto LABEL_208;
            }
            goto LABEL_224;
          }
LABEL_207:
          v28 = (void **)v48;
          BugCheckParameter3[0] = (ULONG_PTR)v48;
          v125 = (void **)v48;
          v57 = HIDWORD(Src[0]) & 0x80000000 | *((_DWORD *)v48 + 1) & 0x7FFFFFFF;
          *((_DWORD *)v48 + 1) = v57;
          *(_DWORD *)v48 = Src[0];
          v50 = v48 + 1;
          *((_QWORD *)v48 + 1) = v48 + 1;
          v51 = v57 ^ (v57 ^ (v41 - 16)) & 0x7FFFFFFF;
          *((_DWORD *)v48 + 1) = v51;
          LODWORD(v51) = v51 & 0x7FFFFFFF;
          v52 = Src[1];
LABEL_208:
          memmove(v50, v52, v51);
          goto LABEL_209;
        }
        goto LABEL_218;
      }
      switch ( a2 )
      {
        case 0xC2u:
          goto LABEL_207;
        case 0xC4u:
          *(_WORD *)v48 = *(_WORD *)Src[1];
          goto LABEL_218;
        case 0x143u:
        case 0x145u:
          goto LABEL_207;
        case 0x148u:
LABEL_218:
          Size = v41;
          v136 = Src[1];
          v143 = (void **)Src[1];
          Src[1] = *((void **)v39 + 15);
          goto LABEL_209;
      }
      v56 = a2 == 330;
    }
    if ( v56 )
      goto LABEL_207;
    goto LABEL_224;
  }
LABEL_232:
  *((_QWORD *)v39 + 14) = 0;
  v65 = v39 + 16;
  LowLimit = (unsigned __int64)(v39 + 16);
  *((_QWORD *)v39 + 2) = 0;
  v151 = (__int64)(v39 + 112);
  v152 = v129;
  HMAssignmentLock(&v151, 0);
  *((_DWORD *)v39 + 26) = a2;
  *((_QWORD *)v39 + 11) = a3;
  *((_QWORD *)v39 + 12) = v28;
  v70 = (int *)(v39 + 84);
  v146 = v39 + 84;
  *((_DWORD *)v39 + 21) = 0;
  *((_QWORD *)v39 + 9) = 0;
  if ( a2 == 576 || a2 == 281 )
  {
    v79 = _HMObjectFromHandle(v28);
    if ( v79 )
    {
      v74 = a6;
      HMChangeOwnerThread(v79, a6);
      goto LABEL_242;
    }
  }
  else if ( a2 == 255 )
  {
    LOBYTE(v66) = 18;
    v71 = (struct tagHIDDATA *)HMValidateHandleNoSecure(v28, v66);
    if ( v71 )
    {
      v67 = (struct tagWND *)v131;
      if ( *(struct tagHIDDATA **)(v131 + 1136) == v71 )
      {
        v67 = v129;
        if ( v129 )
        {
          v72 = CopyHidData(v71);
          v73 = (ULONG_PTR *)v72;
          if ( v72 )
          {
            *(_DWORD *)(v72 + 48) &= ~1u;
            ExpInterlockedPushEntrySList((PSLIST_HEADER)(a6 + 1152), (PSLIST_ENTRY)(v72 + 32));
            BugCheckParameter3[0] = *v73;
            v125 = (void **)BugCheckParameter3[0];
            *((_QWORD *)v39 + 12) = BugCheckParameter3[0];
          }
          v65 = (_QWORD *)LowLimit;
        }
      }
    }
  }
  v74 = a6;
LABEL_242:
  v75 = W32GetUserSessionState(v67, v66, v68, v69) + 69048;
  v76 = *(_QWORD *)v75;
  if ( *(_QWORD *)(*(_QWORD *)v75 + 8LL) != v75 )
    goto LABEL_348;
  *(_QWORD *)v39 = v76;
  *((_QWORD *)v39 + 1) = v75;
  *(_QWORD *)(v76 + 8) = v39;
  *(_QWORD *)v75 = v39;
  *((_DWORD *)v39 + 20) = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  *((_QWORD *)v39 + 5) = v74;
  *((_QWORD *)v39 + 4) = v122;
  *((_DWORD *)v39 + 33) = W32GetCurrentThreadDpiAwarenessContext();
  *((_QWORD *)v39 + 8) = 0;
  v77 = v127;
  if ( v127 && (*(_DWORD *)v127 & 1) != 0 )
  {
    *v70 |= (*(_DWORD *)v127 & 0x100) != 0 ? 1024 : 2048;
    v78 = *v70;
    *((_QWORD *)v39 + 6) = *(_QWORD *)(v77 + 8);
    *((_QWORD *)v39 + 7) = *(_QWORD *)(v77 + 16);
    if ( (*(_DWORD *)v77 & 0x20) != 0 )
    {
      *v70 = v78 | 0x200;
      *((_QWORD *)v39 + 9) = *(_QWORD *)(v77 + 24);
    }
    else
    {
      *v70 = v78 | 0x100;
      *((_QWORD *)v39 + 8) = v131;
    }
  }
  if ( a9 )
    *v70 |= 0x10000u;
  v80 = *(_QWORD **)(a6 + 560);
  if ( *v80 != a6 + 552 )
    goto LABEL_348;
  *v65 = a6 + 552;
  v151 = (__int64)(v65 + 1);
  v65[1] = v80;
  *v80 = v65;
  *(_QWORD *)(a6 + 560) = v65;
  v149 = (_DWORD *)(a6 + 568);
  ++*(_DWORD *)(a6 + 568);
  if ( v122 )
  {
    v124 = *(void **)(v122 + 536);
    v141 = v124;
    *(_QWORD *)(v122 + 536) = v39;
  }
  else
  {
    v124 = 0;
    v141 = 0;
    *v70 |= 8u;
  }
  if ( (*v70 & 0x200) == 0
    && ((unsigned int)IsPointerInputMessageWithState(a2) || (unsigned int)IsPointerParentNotify(a2, a3)) )
  {
    v85 = W32GetUserSessionState(v82, v81, v83, v84);
    CTouchProcessor::ReferenceMsgDataExternal(*(_QWORD *)(v85 + 3208), BugCheckParameter3[0], 6, v39);
  }
  EtwTraceBeginSendMessage(v39, v122, v127);
  if ( !v122 )
  {
    SetWakeBit(a6, 64);
    EtwTraceEndSendMessage(v39);
    return 1;
  }
  v148 = v39 + 72;
  v86 = 0;
  LODWORD(v131) = 0;
  SetWakeBit(a6, 64);
  if ( v127 )
  {
    v130 = *(_DWORD *)(v127 + 36);
    v87 = ((*(_DWORD *)(v127 + 32) & 1) << 15) + 512;
  }
  else
  {
    v130 = 0;
    v87 = 512;
  }
  v132 = v87;
  CKernelStackSwapAuto::CKernelStackSwapAuto((CKernelStackSwapAuto *)v150);
  if ( *(_QWORD *)(v122 + 464) == *(_QWORD *)(a6 + 464)
    && (_InterlockedCompareExchange((volatile signed __int32 *)(v122 + 520), 0, 0) & 0x10000) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(v122 + 520), 0x10000u);
    LODWORD(v131) = 1;
  }
  v88 = 0;
  if ( a2 == 788 )
  {
    if ( BugCheckParameter3[0] )
    {
      v88 = *(_QWORD *)BugCheckParameter3[0];
      if ( (*(_DWORD *)(BugCheckParameter3[0] + 24) & 1) != 0 )
      {
        *v70 |= 0x60000u;
        *((_QWORD *)v39 + 15) = *(_QWORD *)v88;
      }
    }
  }
  if ( (*v70 & 1) == 0 )
  {
    while ( 1 )
    {
      if ( v86 )
      {
LABEL_299:
        v39 = v134;
        goto LABEL_300;
      }
      Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3);
      v90 = 0;
      _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(v91 + 480) + 4LL), 0xFFFFFDFF);
      if ( v88
        && (*(_DWORD *)(v88 + 48) == 13 || *(_DWORD *)(v88 + 48) == 14)
        && *(_DWORD *)(v89 + 664) <= 0x501u
        && *(_DWORD *)(v89 + 680) )
      {
        v92 = PtiCurrent();
        Win32HM_LockIntoThread<1>(v92, v88, BugCheckParameter3);
        v90 = 1;
      }
      v93 = xxxSleepThread(v87, v130, 0, 0);
      v94 = v93;
      v86 = v93 == 0;
      if ( v90 )
        break;
LABEL_288:
      if ( !v94 && v127 )
      {
        v99 = *(_DWORD *)(v127 + 32);
        v100 = *v70;
        if ( ((v99 & 0x10) != 0 || (v100 & 0x20) != 0) && (v100 & 0x10) != 0 )
        {
          v130 = 0;
          v86 = 0;
        }
        if ( (v99 & 8) != 0 )
          v86 &= -IsThreadHung((const struct tagTHREADINFO *)a6);
        if ( !v86 )
          EtwTraceConvertTimeOutToBlocking();
      }
      Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)BugCheckParameter3);
      v87 = v132;
      if ( (*v70 & 1) != 0 )
        goto LABEL_299;
    }
    v95 = *(_DWORD *)(v88 + 64);
    if ( v93 )
    {
      v97 = v95 & 0xFFFFBFFF;
    }
    else
    {
      v96 = v95 | 0x4000;
      *(_DWORD *)(v88 + 64) = v96;
      if ( (v96 & 0x10) != 0 )
        goto LABEL_287;
      if ( ++*(_BYTE *)(v88 + 97) <= 0xAu )
        goto LABEL_287;
      v97 = v96 | 0x10;
    }
    *(_DWORD *)(v88 + 64) = v97;
LABEL_287:
    v98 = PtiCurrent();
    Win32HM_UnlockFromThread<1>((ULONG_PTR)v98, (ULONG_PTR)BugCheckParameter3);
    BugCheckParameter3[1] = 0;
    BugCheckParameter3[0] = -1;
    goto LABEL_288;
  }
LABEL_300:
  CKernelStackSwapAuto::~CKernelStackSwapAuto((CKernelStackSwapAuto *)v150);
  if ( (_DWORD)v131 )
  {
    _InterlockedAnd((volatile signed __int32 *)(v122 + 520), 0xFFFEFFFF);
    MergeDeferredMessagesOfThreadOnQueue(v122);
  }
  SetWakeBit(v122, 512);
  if ( v86 )
    goto LABEL_328;
  if ( !Size )
  {
    if ( a2 == 831 )
    {
      if ( a9 )
      {
        v112 = (__int64)v129;
        if ( v129 )
        {
          if ( (unsigned int)IsWindowDesktopComposed(v129) )
            TransformMessageBetweenCoordinateSpaces(831, 1, (unsigned int)&v139, (unsigned int)&v125, 0, v112);
        }
      }
    }
    goto LABEL_328;
  }
  v101 = v136;
  v134 = (char *)v136;
  if ( a2 == 131 )
  {
    if ( a9 )
    {
      v107 = (__int64)v129;
      if ( v129 )
      {
        if ( (unsigned int)IsWindowDesktopComposed(v129) )
        {
          TransformMessageBetweenCoordinateSpaces(131, 1, (unsigned int)&v139, (unsigned int)&v134, 0, v107);
          v101 = v134;
        }
        else
        {
          v101 = v136;
        }
      }
    }
    v108 = (__int128 *)*((_QWORD *)v39 + 15);
    v109 = *v108;
    if ( a3 )
    {
      v110 = v101[6];
      *(_OWORD *)v101 = v109;
      *((_OWORD *)v101 + 1) = v108[1];
      *((_OWORD *)v101 + 2) = v108[2];
      v101[6] = v110;
      v111 = *((_QWORD *)v108 + 6);
      if ( v111 )
      {
        *(_OWORD *)v110 = *(_OWORD *)v111;
        *(_OWORD *)(v110 + 16) = *(_OWORD *)(v111 + 16);
        *(_QWORD *)(v110 + 32) = *(_QWORD *)(v111 + 32);
      }
    }
    else
    {
      *(_OWORD *)v101 = v109;
    }
LABEL_328:
    v106 = v39 + 72;
    v105 = v124;
    goto LABEL_329;
  }
  v102 = (__int16 *)*((_QWORD *)v39 + 15);
  if ( v133 )
  {
    if ( v133 == 1 )
    {
      strncpycch(v136, v102, Size);
    }
    else
    {
      v103 = Size >> 1;
      v137 = Size >> 1;
      v144 = v102;
      v145 = v136;
      while ( v103 )
      {
        v104 = *v102++;
        v144 = v102;
        *(_WORD *)v101 = v104;
        v101 = (_QWORD *)((char *)v101 + 2);
        v145 = v101;
        if ( !v104 )
          break;
        v137 = --v103;
      }
    }
  }
  else
  {
    memmove(v136, v102, Size);
  }
  v105 = v124;
  v106 = v39 + 72;
LABEL_329:
  EtwTraceEndSendMessage(v39);
  *(_QWORD *)(v122 + 536) = v105;
  v113 = v127;
  if ( v127 )
  {
    **(_QWORD **)(v127 + 40) = *v106;
    if ( (*(_DWORD *)(v113 + 32) & 0x20) != 0 && (*v70 & 0x8000) != 0 )
    {
      v114 = 0;
      UserSetLastError(1400);
      v113 = v127;
    }
    else
    {
      v114 = v86 == 0;
    }
  }
  else
  {
    v114 = *v106;
  }
  if ( (v113 || v86) && (*v70 & 1) == 0 )
  {
    v115 = *v70 | 1;
    *v70 = v115;
    if ( (v115 & 0x4000) != 0 )
    {
      *v70 = v115 | 8;
      goto LABEL_343;
    }
    --*v149;
    v116 = (_QWORD *)LowLimit;
    v117 = *(_QWORD *)LowLimit;
    if ( *(_QWORD *)(*(_QWORD *)LowLimit + 8LL) == LowLimit )
    {
      v118 = *(_QWORD **)v151;
      if ( **(_QWORD **)v151 == LowLimit )
      {
        *v118 = v117;
        *(_QWORD *)(v117 + 8) = v118;
        *v116 = 0;
        *v70 |= 0x10u;
        goto LABEL_343;
      }
    }
LABEL_348:
    __fastfail(3u);
  }
LABEL_343:
  *v70 &= ~0x20000u;
  v119 = *v70;
  if ( (*v70 & 0x4010) != 0x10 )
  {
    v119 |= 8u;
    *v70 = v119;
  }
  if ( (v119 & 0x8008) != 8 )
    UnlinkSendListSms(v39);
  return v114;
}

```

## disassembly

```asm
0x140022384  push    rbx
0x140022386  push    rsi
0x140022387  push    rdi
0x140022388  push    r12
0x14002238a  push    r13
0x14002238c  push    r14
0x14002238e  push    r15
0x140022390  sub     rsp, 180h
0x140022397  mov     rax, cs:__security_cookie
0x14002239e  xor     rax, rsp
0x1400223a1  mov     [rsp+1B8h+var_48], rax
0x1400223a9  mov     r15, r9
0x1400223ac  mov     [rsp+1B8h+BugCheckParameter3], r9
0x1400223b1  mov     [rsp+1B8h+var_168], r8
0x1400223b6  mov     r13d, edx
0x1400223b9  mov     rbx, rcx
0x1400223bc  mov     [rsp+1B8h+var_128], rcx
0x1400223c4  mov     rax, [rsp+1B8h+arg_30]
0x1400223cc  mov     [rsp+1B8h+var_138], rax
0x1400223d4  mov     [rsp+1B8h+var_D8], r8
0x1400223dc  mov     [rsp+1B8h+var_150], r9
0x1400223e1  mov     rcx, [rsp+1B8h+arg_28]
0x1400223e9  mov     [rsp+1B8h+var_180], rcx
0x1400223ee  mov     [rsp+1B8h+var_98], rax
0x1400223f6  xor     edi, edi
0x1400223f8  mov     [rsp+1B8h+var_178], edi
0x1400223fc  xorps   xmm0, xmm0
0x1400223ff  movups  xmmword ptr [rsp+1B8h+Src], xmm0
0x140022407  mov     eax, edi
0x140022409  mov     [rsp+1B8h+var_10C], eax
0x140022410  mov     [rsp+1B8h+var_E0], eax
0x140022417  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14002241e  nop     dword ptr [rax+rax+00h]
0x140022423  mov     r14, rax
0x140022426  test    rax, rax
0x140022429  jz      short loc_140022437
0x14002242b  mov     rax, [rax]
0x14002242e  neg     rax
0x140022431  sbb     rcx, rcx
0x140022434  and     r14, rcx
0x140022437  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002243c  mov     [rsp+1B8h+var_118], rax
0x140022444  neg     [rsp+1B8h+arg_20]
0x14002244b  sbb     rcx, rcx
0x14002244e  and     rcx, rax
0x140022451  mov     [rsp+1B8h+var_160], rcx
0x140022456  mov     r12d, 1
0x14002245c  jz      short loc_140022471
0x14002245e  xor     eax, eax
0x140022460  lock cmpxchg [rcx+208h], edi
0x140022468  test    r12b, al
0x14002246b  jnz     loc_1400239C5
0x140022471  mov     [rsp+1B8h+HighLimit], rdi
0x140022479  mov     [rsp+1B8h+LowLimit], rdi
0x140022481  lea     rdx, [rsp+1B8h+HighLimit]; HighLimit
0x140022489  lea     rcx, [rsp+1B8h+LowLimit]; LowLimit
0x140022491  call    cs:__imp_IoGetStackLimits
0x140022498  nop     dword ptr [rax+rax+00h]
0x14002249d  lea     rax, [rsp+1B8h+HighLimit]
0x1400224a5  sub     rax, [rsp+1B8h+LowLimit]
0x1400224ad  cmp     rax, 2000h
0x1400224b3  jb      loc_1400239C5
0x1400224b9  test    rbx, rbx
0x1400224bc  jz      loc_140022587
0x1400224c2  mov     rax, [rbx+10h]
0x1400224c6  cmp     [rax+1C8h], r14
0x1400224cd  jz      loc_140022587
0x1400224d3  mov     eax, 0D0h
0x1400224d8  cmp     r13d, eax
0x1400224db  ja      short loc_14002254D
0x1400224dd  jz      loc_140022587
0x1400224e3  mov     eax, r13d
0x1400224e6  sub     eax, 0Ch
0x1400224e9  jz      loc_140022587
0x1400224ef  sub     eax, 1
0x1400224f2  jz      short loc_14002250C
0x1400224f4  sub     eax, 41h ; 'A'
0x1400224f7  jz      short loc_140022571
0x1400224f9  sub     eax, 6Eh ; 'n'
0x1400224fc  jz      loc_140022587
0x140022502  sub     eax, 8
0x140022505  jz      short loc_14002250C
0x140022507  cmp     eax, 8
0x14002250a  jnz     short loc_14002256D
0x14002250c  call    cs:__imp_W32GetUserSessionState
0x140022513  nop     dword ptr [rax+rax+00h]
0x140022518  mov     rdx, [rax+4CF8h]
0x14002251f  mov     rax, [rbx+88h]
0x140022526  mov     rcx, [rax+8]
0x14002252a  movzx   eax, word ptr [rcx+2]
0x14002252e  cmp     [rdx+366h], ax
0x140022535  jnz     short loc_14002256D
0x140022537  mov     rax, [rbx+28h]
0x14002253b  test    byte ptr [rax+1Ch], 20h
0x14002253f  jz      short loc_14002256D
0x140022541  mov     ecx, 5
0x140022546  call    UserSetLastError
0x14002254b  jmp     short loc_140022578
0x14002254d  mov     eax, r13d
0x140022550  sub     eax, 110h
0x140022555  jz      short loc_140022571
0x140022557  sub     eax, 51h ; 'Q'
0x14002255a  jz      short loc_140022587
0x14002255c  sub     eax, 47h ; 'G'
0x14002255f  jz      short loc_140022587
0x140022561  sub     eax, 8Bh
0x140022566  jz      short loc_140022587
0x140022568  cmp     eax, 55h ; 'U'
0x14002256b  jz      short loc_140022587
0x14002256d  mov     eax, edi
0x14002256f  jmp     short loc_140022574
0x140022571  mov     eax, r12d
0x140022574  test    eax, eax
0x140022576  jz      short loc_140022587
0x140022578  mov     ecx, 5
0x14002257d  call    UserSetLastError
0x140022582  jmp     loc_1400239C5
0x140022587  cmp     [rsp+1B8h+arg_38], edi
0x14002258e  jnz     loc_140022751
0x140022594  test    rbx, rbx
0x140022597  jz      short loc_14002259F
0x140022599  mov     rax, [rbx+10h]
0x14002259d  jmp     short loc_1400225AC
0x14002259f  mov     rsi, rdi
0x1400225a2  mov     rax, [rsp+1B8h+var_180]
0x1400225a7  test    rax, rax
0x1400225aa  jz      short loc_1400225B3
0x1400225ac  mov     rsi, [rax+1C8h]
0x1400225b3  cmp     rsi, r14
0x1400225b6  jz      loc_140022751
0x1400225bc  cmp     r13d, 2CDh
0x1400225c3  jz      loc_140022737
0x1400225c9  mov     r8d, r13d; unsigned int
0x1400225cc  mov     rdx, rbx; struct tagWND *
0x1400225cf  mov     rcx, rsi; struct tagPROCESSINFO *
0x1400225d2  call    ?IsMessageAllowedAcrossILByReceiver@@YAHPEAUtagPROCESSINFO@@PEAUtagWND@@I@Z; IsMessageAllowedAcrossILByReceiver(tagPROCESSINFO *,tagWND *,uint)
0x1400225d7  mov     ebx, eax
0x1400225d9  test    eax, eax
0x1400225db  jnz     short loc_1400225E7
0x1400225dd  mov     ecx, r13d; unsigned int
0x1400225e0  call    ?IsMessageAlwaysAllowedAcrossIL@@YAHI@Z; IsMessageAlwaysAllowedAcrossIL(uint)
0x1400225e5  mov     ebx, eax
0x1400225e7  test    ebx, ebx
0x1400225e9  jnz     loc_140022751
0x1400225ef  cmp     r13d, 112h
0x1400225f6  jnz     short loc_14002261D
0x1400225f8  mov     rcx, [rsp+1B8h+var_168]
0x1400225fd  lea     rax, [rcx-0F020h]
0x140022604  test    rax, 0FFFFFFFFFFFFFEBFh
0x14002260a  jnz     short loc_14002261D
0x14002260c  cmp     rcx, 0F160h
0x140022613  jz      short loc_14002261D
0x140022615  mov     ebx, r12d
0x140022618  jmp     loc_14002272B
0x14002261d  mov     ebx, edi
0x14002261f  test    ebx, ebx
0x140022621  jnz     loc_140022751
0x140022627  call    Feature_MsgUseCSRSSTrueIL__private_IsEnabledDeviceUsageNoInline
0x14002262c  test    eax, eax
0x14002262e  jnz     short loc_14002269C
0x140022630  xor     eax, eax
0x140022632  mov     [rsp+1B8h+var_58], rax
0x14002263a  mov     dword ptr [rsp+1B8h+var_50], eax
0x140022641  call    cs:__imp_W32GetUserGdiSessionState
0x140022648  nop     dword ptr [rax+rax+00h]
0x14002264d  mov     rcx, [rax+28h]
0x140022651  cmp     [rsi], rcx
0x140022654  jnz     short loc_14002266B
0x140022656  mov     [rsp+1B8h+var_58], 2000h
0x140022662  mov     dword ptr [rsp+1B8h+var_50], edi
0x140022669  jmp     short loc_140022692
0x14002266b  mov     eax, [rsi+360h]
0x140022671  mov     dword ptr [rsp+1B8h+var_58], eax
0x140022678  mov     eax, [rsi+364h]
0x14002267e  mov     dword ptr [rsp+1B8h+var_58+4], eax
0x140022685  mov     eax, [rsi+368h]
0x14002268b  mov     dword ptr [rsp+1B8h+var_50], eax
0x140022692  lea     rdx, [rsp+1B8h+var_58]
0x14002269a  jmp     short loc_1400226A3
0x14002269c  lea     rdx, [rsi+360h]
0x1400226a3  lea     rcx, [r14+360h]
0x1400226aa  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1400226b1  nop     dword ptr [rax+rax+00h]
0x1400226b6  movzx   ebx, al
0x1400226b9  test    ebx, ebx
0x1400226bb  jnz     loc_140022751
0x1400226c1  mov     rax, [rsp+1B8h+var_128]
0x1400226c9  test    rax, rax
0x1400226cc  jz      short loc_140022700
0x1400226ce  cmp     r13d, 319h
0x1400226d5  jnz     short loc_140022700
0x1400226d7  mov     r15, [rax+10h]
0x1400226db  cmp     [r15+630h], rax
0x1400226e2  jnz     short loc_1400226FB
0x1400226e4  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400226e9  mov     rax, [rax+1D0h]
0x1400226f0  cmp     [r15+1D0h], rax
0x1400226f7  cmovz   ebx, r12d
0x1400226fb  mov     r15, [rsp+1B8h+BugCheckParameter3]
0x140022700  test    ebx, ebx
0x140022702  jnz     short loc_140022751
0x140022704  mov     [rsp+1B8h+var_198], r15
0x140022709  mov     r9, [rsp+1B8h+var_168]
0x14002270e  mov     r8d, r13d
0x140022711  mov     rdx, rsi
0x140022714  mov     rcx, r14
0x140022717  call    cs:__imp_EtwTraceUIPIMsgError
0x14002271e  nop     dword ptr [rax+rax+00h]
0x140022723  lea     ecx, [rbx+5]
0x140022726  call    UserSetLastError
0x14002272b  test    ebx, ebx
0x14002272d  jnz     short loc_140022751
0x14002272f  mov     rbx, [rsp+1B8h+var_128]
0x140022737  mov     edx, r13d
0x14002273a  mov     rcx, rbx
0x14002273d  call    cs:__imp_?UserCheckForMessageAccessWithWindowCapability@@YAHPEAUtagWND@@I@Z; UserCheckForMessageAccessWithWindowCapability(tagWND *,uint)
0x140022744  nop     dword ptr [rax+rax+00h]
0x140022749  test    eax, eax
0x14002274b  jz      loc_1400239C5
0x140022751  lea     eax, [r13-240h]
0x140022758  mov     r14, [rsp+1B8h+BugCheckParameter3]
0x14002275d  test    eax, eax
0x14002275f  jnz     short loc_140022765
0x140022761  mov     dl, 14h
0x140022763  jmp     short loc_140022770
0x140022765  cmp     r13d, 119h
0x14002276c  jnz     short loc_140022781
0x14002276e  mov     dl, 15h
0x140022770  mov     rcx, r14
0x140022773  call    HMValidateHandleWithDescriptor
0x140022778  test    rax, rax
0x14002277b  jz      loc_1400239C5
0x140022781  mov     rbx, [rsp+1B8h+var_180]
0x140022786  mov     rcx, [rbx+1C8h]
0x14002278d  call    cs:__imp_?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ; tagPROCESSINFO::SyncAndTestFreeze(void)
0x140022794  nop     dword ptr [rax+rax+00h]
0x140022799  test    al, al
0x14002279b  jz      loc_140022868
0x1400227a1  mov     rcx, [rsp+1B8h+var_138]
0x1400227a9  test    rcx, rcx
0x1400227ac  jz      short loc_1400227CF
0x1400227ae  mov     eax, [rcx+20h]
0x1400227b1  test    al, 40h
0x1400227b3  jz      short loc_1400227BC
0x1400227b5  mov     rsi, [rsp+1B8h+var_160]
0x1400227ba  jmp     short loc_140022817
0x1400227bc  test    rcx, rcx
0x1400227bf  jz      short loc_1400227CF
0x1400227c1  cmp     dword ptr [rcx], 2
0x1400227c4  jnz     short loc_1400227CF
0x1400227c6  cmp     [rcx+24h], edi
0x1400227c9  jnz     loc_1400239C5
0x1400227cf  mov     rsi, [rsp+1B8h+var_160]
0x1400227d4  test    rsi, rsi
0x1400227d7  jz      short loc_14002281C
0x1400227d9  mov     rax, [rbx+1C8h]
0x1400227e0  mov     rbx, [rax]
0x1400227e3  call    cs:__imp_PsGetCurrentProcess
0x1400227ea  nop     dword ptr [rax+rax+00h]
0x1400227ef  mov     rdx, rbx
0x1400227f2  mov     rcx, rax
0x1400227f5  call    cs:__imp_PsGetProcessCommonJob
0x1400227fc  nop     dword ptr [rax+rax+00h]
0x140022801  test    rax, rax
0x140022804  jz      loc_1400239C5
0x14002280a  mov     rcx, [rsp+1B8h+var_138]
0x140022812  mov     rbx, [rsp+1B8h+var_180]
0x140022817  test    rsi, rsi
0x14002281a  jnz     short loc_140022868
0x14002281c  test    rcx, rcx
0x14002281f  jnz     short loc_140022853
0x140022821  cmp     r13d, 219h
0x140022828  jz      loc_1400239C5
0x14002282e  mov     [rsp+1B8h+var_198], r14
0x140022833  mov     r9, [rsp+1B8h+var_168]
0x140022838  mov     r8d, r13d
0x14002283b  mov     rdx, [rsp+1B8h+var_128]
0x140022843  mov     rcx, rbx
0x140022846  call    ProcessSuspendedSendMessage
0x14002284b  test    eax, eax
0x14002284d  jz      loc_1400239C5
0x140022853  test    rsi, rsi
0x140022856  jnz     short loc_140022868
0x140022858  cmp     dword ptr [rbx+238h], 2710h
0x140022862  ja      loc_1400239C5
0x140022868  call    cs:__imp_W32GetUserSessionState
0x14002286f  nop     dword ptr [rax+rax+00h]
0x140022874  mov     rcx, [rax+10DD8h]
0x14002287b  call    cs:__imp_Win32AllocateFromPagedLookasideList
0x140022882  nop     dword ptr [rax+rax+00h]
0x140022887  mov     r12, rax
0x14002288a  mov     [rsp+1B8h+var_108], rax
0x140022892  test    rax, rax
0x140022895  jz      loc_1400239C5
0x14002289b  mov     [rsp+1B8h+var_C0], rax
0x1400228a3  mov     [rsp+1B8h+LowLimit], rdi
0x1400228ab  mov     r15, rdi
0x1400228ae  mov     [rsp+1B8h+var_F0], rdi
0x1400228b6  mov     [rax+78h], rdi
0x1400228ba  mov     eax, edi
  ... truncated ...
```
