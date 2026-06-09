# xxxInterSendMsgEx

- ea: `0x140022384`
- end: `0x1400239eb`
- name: `xxxInterSendMsgEx`
- size: `5735`
- prototype: `__int64 __usercall@<rax>(struct tagWND *@<rcx>, unsigned int@<edx>, int, __int64, __int64, int, int)`
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
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rsi
  int v20; // ebx
  int v21; // ebx
  __int64 v22; // rcx
  const struct tagUIPI_INFO *v23; // r8
  const struct tagUIPI_INFO *v24; // rdx
  bool v25; // al
  __int64 v26; // r15
  void **v27; // r14
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rsi
  __int64 v31; // rbx
  __int64 CurrentProcess; // rax
  __int64 UserSessionState; // rax
  __int64 v34; // rax
  __int64 v35; // r9
  char *v36; // r12
  void **v37; // r15
  unsigned int v38; // esi
  unsigned __int64 v39; // rcx
  __int64 v40; // r8
  bool v41; // zf
  int v43; // eax
  bool v44; // zf
  bool v45; // zf
  _OWORD *v46; // r9
  unsigned __int64 v47; // rax
  void *v48; // rcx
  size_t v49; // r8
  const void *v50; // rdx
  void **v51; // rdx
  __int64 v52; // rcx
  _OWORD *v53; // rax
  bool v54; // zf
  unsigned int v55; // edx
  const void *v56; // rdx
  size_t v57; // r8
  __int64 v58; // rbx
  void *v59; // rbx
  size_t v60; // r8
  __int64 v61; // rsi
  int v62; // ecx
  _QWORD *v63; // rsi
  __int64 v64; // rdx
  struct tagWND *v65; // rcx
  int *v66; // rbx
  struct tagHIDDATA *v67; // rax
  __int64 v68; // rax
  ULONG_PTR *v69; // rsi
  __int64 v70; // r14
  __int64 v71; // rax
  __int64 v72; // rcx
  unsigned __int64 v73; // rcx
  __int64 v74; // rdx
  int v75; // ecx
  __int64 v76; // rax
  _QWORD *v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rax
  int v80; // esi
  unsigned int v81; // r15d
  __int64 v82; // r14
  __int64 v83; // r8
  char v84; // r12
  __int64 v85; // rdx
  struct tagTHREADINFO *v86; // rax
  int v87; // eax
  int v88; // r15d
  int v89; // ecx
  int v90; // ecx
  unsigned int v91; // ecx
  struct tagTHREADINFO *v92; // rax
  int v93; // ecx
  int v94; // eax
  _QWORD *v95; // r9
  __int16 *v96; // rdx
  unsigned int v97; // ecx
  __int16 v98; // ax
  void *v99; // r14
  _QWORD *v100; // r15
  __int64 v101; // r14
  __int128 *v102; // rax
  __int128 v103; // xmm0
  __int64 v104; // rcx
  __int64 v105; // rdx
  __int64 v106; // r14
  __int64 v107; // rdx
  __int64 v108; // r14
  int v109; // eax
  _QWORD *v110; // rdx
  __int64 v111; // rcx
  _QWORD *v112; // rax
  int v113; // ecx
  unsigned int Size; // [rsp+44h] [rbp-174h]
  __int64 v116; // [rsp+58h] [rbp-160h]
  void **v117; // [rsp+60h] [rbp-158h]
  void *v118; // [rsp+60h] [rbp-158h]
  void **v119; // [rsp+68h] [rbp-150h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+70h] [rbp-148h] BYREF
  __int64 v121; // [rsp+80h] [rbp-138h]
  unsigned __int64 LowLimit; // [rsp+88h] [rbp-130h] BYREF
  struct tagWND *v123; // [rsp+90h] [rbp-128h]
  unsigned int v124; // [rsp+98h] [rbp-120h]
  unsigned __int64 v125; // [rsp+A0h] [rbp-118h]
  unsigned int v126; // [rsp+A8h] [rbp-110h]
  int v127; // [rsp+ACh] [rbp-10Ch]
  char *v128; // [rsp+B0h] [rbp-108h] BYREF
  void *Src[2]; // [rsp+B8h] [rbp-100h] BYREF
  void *v130; // [rsp+C8h] [rbp-F0h]
  unsigned int v131; // [rsp+D0h] [rbp-E8h]
  int v132; // [rsp+D8h] [rbp-E0h]
  __int64 v133; // [rsp+E0h] [rbp-D8h] BYREF
  unsigned __int64 HighLimit; // [rsp+E8h] [rbp-D0h] BYREF
  void *v135; // [rsp+F0h] [rbp-C8h]
  __int64 v136; // [rsp+F8h] [rbp-C0h]
  void **v137; // [rsp+100h] [rbp-B8h]
  __int16 *v138; // [rsp+108h] [rbp-B0h]
  void *v139; // [rsp+110h] [rbp-A8h]
  char *v140; // [rsp+118h] [rbp-A0h]
  __int64 v141; // [rsp+120h] [rbp-98h]
  char *v142; // [rsp+128h] [rbp-90h]
  _DWORD *v143; // [rsp+130h] [rbp-88h]
  _BYTE v144[24]; // [rsp+148h] [rbp-70h] BYREF
  __int64 v145; // [rsp+160h] [rbp-58h] BYREF
  struct tagWND *v146; // [rsp+168h] [rbp-50h]

  v9 = a4;
  BugCheckParameter3[0] = a4;
  v11 = a1;
  v123 = a1;
  v121 = a7;
  v133 = a3;
  v119 = (void **)a4;
  v141 = a7;
  *(_OWORD *)Src = 0;
  v127 = 0;
  v132 = 0;
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
  v13 = CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
    v13 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
  v125 = (unsigned __int64)PtiCurrent();
  v14 = v125 & -(__int64)(a5 != 0);
  v116 = v14;
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
      v15 = *(_QWORD *)(W32GetUserSessionState(v16) + 19704);
      if ( *(_WORD *)(v15 + 870) == *(_WORD *)(*(_QWORD *)(*((_QWORD *)v11 + 17) + 8LL) + 2LL)
        && (*(_BYTE *)(*((_QWORD *)v11 + 5) + 28LL) & 0x20) != 0 )
      {
        UserSetLastError(5);
LABEL_27:
        UserSetLastError(5);
        return 0;
      }
LABEL_24:
      v17 = 0;
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
  v17 = 1;
LABEL_26:
  if ( v17 )
    goto LABEL_27;
LABEL_28:
  if ( a8 )
    goto LABEL_60;
  if ( v11 )
  {
    v18 = *((_QWORD *)v11 + 2);
  }
  else
  {
    v19 = 0;
    v18 = a6;
    if ( !a6 )
      goto LABEL_33;
  }
  v19 = *(_QWORD *)(v18 + 456);
LABEL_33:
  if ( v19 == v13 )
    goto LABEL_60;
  if ( a2 != 717 )
  {
    v20 = IsMessageAllowedAcrossILByReceiver((struct tagPROCESSINFO *)v19, v11, a2);
    if ( !v20 )
      v20 = IsMessageAlwaysAllowedAcrossIL(a2);
    if ( v20 )
      goto LABEL_60;
    if ( a2 != 274 || ((a3 - 61472) & 0xFFFFFFFFFFFFFEBFuLL) != 0 || a3 == 61792 )
    {
      if ( (unsigned int)Feature_MsgUseCSRSSTrueIL__private_IsEnabledDeviceUsageNoInline() )
      {
        v24 = (const struct tagUIPI_INFO *)(v19 + 864);
      }
      else
      {
        v145 = 0;
        LODWORD(v146) = 0;
        if ( *(_QWORD *)v19 == *(_QWORD *)(W32GetUserGdiSessionState(v22) + 40) )
        {
          v145 = 0x2000;
          LODWORD(v146) = 0;
        }
        else
        {
          v145 = *(_QWORD *)(v19 + 864);
          LODWORD(v146) = *(_DWORD *)(v19 + 872);
        }
        v24 = (const struct tagUIPI_INFO *)&v145;
      }
      v25 = UIPrivilegeIsolation::CheckAccess((UIPrivilegeIsolation *)(v13 + 864), v24, v23);
      v21 = v25;
      if ( v25 )
        goto LABEL_60;
      if ( v123 && a2 == 793 )
      {
        v26 = *((_QWORD *)v123 + 2);
        if ( *(struct tagWND **)(v26 + 1584) == v123 && *(_QWORD *)(v26 + 464) == *((_QWORD *)PtiCurrent() + 58) )
          v21 = 1;
        v9 = BugCheckParameter3[0];
      }
      if ( v21 )
        goto LABEL_60;
      EtwTraceUIPIMsgError(v13, v19, a2, a3, v9);
      UserSetLastError(5);
    }
    else
    {
      v21 = 1;
    }
    if ( v21 )
      goto LABEL_60;
    v11 = v123;
  }
  if ( !UserCheckForMessageAccessWithWindowCapability(v11, a2) )
    return 0;
LABEL_60:
  v27 = (void **)BugCheckParameter3[0];
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
  v28 = a6;
  if ( !tagPROCESSINFO::SyncAndTestFreeze(*(tagPROCESSINFO **)(a6 + 456)) )
    goto LABEL_80;
  v29 = v121;
  if ( v121 )
  {
    if ( (*(_DWORD *)(v121 + 32) & 0x40) != 0 )
    {
      v30 = v116;
      goto LABEL_74;
    }
    if ( *(_DWORD *)v121 == 2 && *(_DWORD *)(v121 + 36) )
      return 0;
  }
  v30 = v116;
  if ( v116 )
  {
    v31 = **(_QWORD **)(a6 + 456);
    CurrentProcess = PsGetCurrentProcess();
    if ( !PsGetProcessCommonJob(CurrentProcess, v31) )
      return 0;
    v29 = v121;
    v28 = a6;
LABEL_74:
    if ( v30 )
      goto LABEL_80;
  }
  if ( !v29 && (a2 == 537 || !(unsigned int)ProcessSuspendedSendMessage(v28, v123, a2, a3, BugCheckParameter3[0]))
    || !v30 && *(_DWORD *)(v28 + 568) > 0x2710u )
  {
    return 0;
  }
LABEL_80:
  UserSessionState = W32GetUserSessionState(v29);
  v34 = Win32AllocateFromPagedLookasideList(*(_QWORD *)(UserSessionState + 69080));
  v36 = (char *)v34;
  v128 = (char *)v34;
  if ( !v34 )
    return 0;
  v136 = v34;
  LowLimit = 0;
  v37 = 0;
  v130 = 0;
  *(_QWORD *)(v34 + 120) = 0;
  Size = 0;
  v38 = 0;
  v117 = v27;
  v39 = v125;
  *(_DWORD *)(v34 + 128) = *(_DWORD *)(v125 + 1604);
  v40 = v121;
  if ( !v121 || *(_DWORD *)v121 != 33 )
  {
    if ( a2 > 0x14D )
    {
      if ( a2 > 0x1A2 )
      {
        if ( a2 == 536 )
        {
          if ( v27 && (a3 & 0x8000) != 0 && (!(unsigned __int8)MmIsKernelAddress(v27) || !v116) )
          {
            v38 = *((_DWORD *)v27 + 4) + 20;
            if ( *((_DWORD *)v27 + 4) >= 0xFFFFFFEC )
              goto LABEL_137;
          }
          goto LABEL_176;
        }
        if ( a2 != 537 )
        {
          if ( a2 == 544 )
          {
            v38 = (*((_DWORD *)v27 + 15) & 0x7FFFFFFF) + (*((_DWORD *)v27 + 19) & 0x7FFFFFFF);
            v37 = v27;
            goto LABEL_176;
          }
          if ( a2 == 643 )
          {
            if ( a3 == 24 )
              v38 = (*(_DWORD *)v27 << 9) + 4;
            goto LABEL_176;
          }
          if ( a2 == 780 )
            goto LABEL_159;
          if ( a2 == 833 )
          {
            v43 = 104;
          }
          else
          {
            if ( a2 == 834 )
            {
              v38 = 80;
              goto LABEL_177;
            }
            if ( a2 != 836 )
            {
              if ( a2 == 838 )
                v38 = 96;
              goto LABEL_176;
            }
            v43 = 1204;
          }
          v38 = v43;
LABEL_106:
          Size = v43;
          goto LABEL_176;
        }
        if ( !v27 || (a3 & 0x8000) == 0 || (unsigned __int8)MmIsKernelAddress(v27) && v116 )
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
            v41 = a2 == 406;
LABEL_153:
            if ( !v41 )
              goto LABEL_176;
            goto LABEL_134;
          }
          goto LABEL_114;
        }
LABEL_132:
        v44 = *(_DWORD *)(v39 + 1604) == 1;
LABEL_133:
        if ( v44 )
          goto LABEL_176;
        goto LABEL_134;
      }
      if ( a2 != 397 )
      {
        if ( a2 == 344 || a2 == 384 || a2 == 385 )
          goto LABEL_132;
        if ( a2 == 393 )
          goto LABEL_159;
        v45 = a2 == 396;
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
              v38 = *(unsigned __int16 *)v27;
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
                    v41 = a2 == 27;
                    goto LABEL_153;
                  }
                  goto LABEL_115;
                }
LABEL_159:
                *(_OWORD *)Src = *(_OWORD *)v27;
                v127 = (SHIDWORD(Src[0]) >= 0) + 1;
                v132 = v127;
                v27 = Src;
                BugCheckParameter3[0] = (ULONG_PTR)Src;
                v119 = Src;
                if ( !(unsigned __int8)MmIsKernelAddress(_mm_srli_si128(*(__m128i *)Src, 8).m128i_u64[0]) || !v116 )
                  v38 = HIDWORD(Src[0]) & 0x7FFFFFFF;
                goto LABEL_176;
              }
LABEL_115:
              v44 = v27 == 0;
              goto LABEL_133;
            }
LABEL_117:
            UserSetLastError(5);
            FreeSMS(v36, 1);
            return 0;
          }
          if ( a2 != 70 && a2 != 71 )
          {
            if ( a2 == 73 )
            {
              v38 = a3;
            }
            else if ( a2 == 74 )
            {
              LowLimit = (unsigned __int64)v27;
              if ( v27[2] )
              {
                v38 = *((_DWORD *)v27 + 2) + 24;
                if ( v38 < 0x18 )
                {
                  FreeSMS(v34, 1);
                  return 0;
                }
              }
              else
              {
                v38 = 24;
              }
            }
            goto LABEL_176;
          }
          v38 = 40;
          goto LABEL_105;
        }
LABEL_169:
        v38 = *(_DWORD *)v27;
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
              v38 = a3 != 0 ? 96 : 16;
LABEL_105:
              v43 = v38;
              goto LABEL_106;
            case 0xC2u:
              goto LABEL_115;
            case 0xC4u:
              goto LABEL_159;
          }
          if ( a2 != 203 )
            goto LABEL_176;
LABEL_114:
          v38 = 4 * a3;
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
        v45 = a2 == 332;
LABEL_131:
        if ( !v45 )
          goto LABEL_176;
        goto LABEL_132;
      }
    }
LABEL_134:
    *(_OWORD *)Src = *(_OWORD *)v27;
    if ( !(unsigned __int8)MmIsKernelAddress(_mm_srli_si128(*(__m128i *)Src, 8).m128i_u64[0]) || !v116 )
    {
      v38 = LODWORD(Src[0]) + 18;
      if ( (unsigned int)(LODWORD(Src[0]) + 18) < LODWORD(Src[0]) )
      {
LABEL_137:
        FreeSMS(v36, 1);
        return 8;
      }
    }
LABEL_176:
    if ( !v38 )
      goto LABEL_209;
LABEL_177:
    v46 = (_OWORD *)Win32AllocPoolWithQuotaZInit(v38, 1668510549, v40, v35);
    *((_QWORD *)v36 + 15) = v46;
    if ( !v46 )
      goto LABEL_209;
    v130 = v27;
    v137 = v27;
    if ( a2 > 0x14C )
    {
      if ( a2 > 0x18D )
      {
        switch ( a2 )
        {
          case 0x18Fu:
            goto LABEL_207;
          case 0x191u:
            Size = v38;
            break;
          case 0x196u:
          case 0x1A2u:
            goto LABEL_207;
          case 0x220u:
            v56 = v37[10];
            if ( v56 )
            {
              v57 = *((unsigned int *)v37 + 19);
              LODWORD(v57) = v57 & 0x7FFFFFFF;
              memmove(v46, v56, v57);
              *v37 = (void *)*((_QWORD *)v36 + 15);
            }
            if ( *((_DWORD *)v37 + 14) )
            {
              v58 = *((unsigned int *)v37 + 19);
              LODWORD(v58) = v58 & 0x7FFFFFFF;
              v59 = (void *)(*((_QWORD *)v36 + 15) + v58);
              v60 = *((unsigned int *)v37 + 15);
              LODWORD(v60) = v60 & 0x7FFFFFFF;
              memmove(v59, v37[8], v60);
              v37[1] = v59;
            }
            goto LABEL_209;
          case 0x30Cu:
            goto LABEL_218;
        }
LABEL_224:
        v51 = v117;
        goto LABEL_225;
      }
      if ( a2 == 397 || a2 == 333 || a2 == 344 || a2 == 384 || a2 == 385 )
        goto LABEL_207;
      if ( a2 == 393 )
        goto LABEL_218;
      v54 = a2 == 396;
    }
    else
    {
      if ( a2 == 332 )
        goto LABEL_207;
      if ( a2 <= 0x83 )
      {
        if ( a2 == 131 )
        {
          v51 = v117;
          if ( a3 )
          {
            *v46 = *(_OWORD *)v117;
            v46[1] = *((_OWORD *)v117 + 1);
            v46[2] = *((_OWORD *)v117 + 2);
            *((_QWORD *)v46 + 6) = v117[6];
            v52 = *((_QWORD *)v36 + 15) + 56LL;
            *((_QWORD *)v46 + 6) = v52;
            v53 = v117[6];
            *(_OWORD *)v52 = *v53;
            *(_OWORD *)(v52 + 16) = v53[1];
            *(_QWORD *)(v52 + 32) = *((_QWORD *)v53 + 4);
LABEL_226:
            v27 = (void **)*((_QWORD *)v36 + 15);
            BugCheckParameter3[0] = (ULONG_PTR)v27;
            v119 = v27;
LABEL_209:
            if ( v38 && !*((_QWORD *)v36 + 15) )
            {
              FreeSMS(v36, 1);
              return 0;
            }
            if ( a9 )
            {
              v61 = (__int64)v123;
              if ( v123 )
              {
                if ( (unsigned int)IsWindowDesktopComposed(v123) && !(unsigned int)IsPointerInputMessage(a2) )
                {
                  TransformMessageBetweenCoordinateSpaces(v62, 1, (unsigned int)&v133, (unsigned int)&v119, v61, 0);
                  v27 = v119;
                  BugCheckParameter3[0] = (ULONG_PTR)v119;
                }
              }
            }
            goto LABEL_232;
          }
LABEL_225:
          memmove(v46, v51, v38);
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
              v27 = (void **)v46;
              BugCheckParameter3[0] = (ULONG_PTR)v46;
              v119 = (void **)v46;
              v47 = LowLimit;
              *v46 = *(_OWORD *)LowLimit;
              *((_QWORD *)v46 + 2) = *(_QWORD *)(v47 + 16);
              if ( !*(_QWORD *)(v47 + 16) )
                goto LABEL_209;
              v48 = (char *)v46 + 24;
              *((_QWORD *)v46 + 2) = (char *)v46 + 24;
              v49 = *(unsigned int *)(v47 + 8);
              v50 = *(const void **)(v47 + 16);
              goto LABEL_208;
            }
            goto LABEL_224;
          }
LABEL_207:
          v27 = (void **)v46;
          BugCheckParameter3[0] = (ULONG_PTR)v46;
          v119 = (void **)v46;
          v55 = HIDWORD(Src[0]) & 0x80000000 | *((_DWORD *)v46 + 1) & 0x7FFFFFFF;
          *((_DWORD *)v46 + 1) = v55;
          *(_DWORD *)v46 = Src[0];
          v48 = v46 + 1;
          *((_QWORD *)v46 + 1) = v46 + 1;
          v49 = v55 ^ (v55 ^ (v38 - 16)) & 0x7FFFFFFF;
          *((_DWORD *)v46 + 1) = v49;
          LODWORD(v49) = v49 & 0x7FFFFFFF;
          v50 = Src[1];
LABEL_208:
          memmove(v48, v50, v49);
          goto LABEL_209;
        }
        goto LABEL_218;
      }
      switch ( a2 )
      {
        case 0xC2u:
          goto LABEL_207;
        case 0xC4u:
          *(_WORD *)v46 = *(_WORD *)Src[1];
          goto LABEL_218;
        case 0x143u:
        case 0x145u:
          goto LABEL_207;
        case 0x148u:
LABEL_218:
          Size = v38;
          v130 = Src[1];
          v137 = (void **)Src[1];
          Src[1] = *((void **)v36 + 15);
          goto LABEL_209;
      }
      v54 = a2 == 330;
    }
    if ( v54 )
      goto LABEL_207;
    goto LABEL_224;
  }
LABEL_232:
  *((_QWORD *)v36 + 14) = 0;
  v63 = v36 + 16;
  LowLimit = (unsigned __int64)(v36 + 16);
  *((_QWORD *)v36 + 2) = 0;
  v145 = (__int64)(v36 + 112);
  v146 = v123;
  HMAssignmentLock(&v145, 0);
  *((_DWORD *)v36 + 26) = a2;
  *((_QWORD *)v36 + 11) = a3;
  *((_QWORD *)v36 + 12) = v27;
  v66 = (int *)(v36 + 84);
  v140 = v36 + 84;
  *((_DWORD *)v36 + 21) = 0;
  *((_QWORD *)v36 + 9) = 0;
  if ( a2 == 576 || a2 == 281 )
  {
    v76 = _HMObjectFromHandle(v27);
    if ( v76 )
    {
      v70 = a6;
      HMChangeOwnerThread(v76, a6);
      goto LABEL_242;
    }
  }
  else if ( a2 == 255 )
  {
    LOBYTE(v64) = 18;
    v67 = (struct tagHIDDATA *)HMValidateHandleNoSecure(v27, v64);
    if ( v67 )
    {
      v65 = (struct tagWND *)v125;
      if ( *(struct tagHIDDATA **)(v125 + 1136) == v67 )
      {
        v65 = v123;
        if ( v123 )
        {
          v68 = CopyHidData(v67);
          v69 = (ULONG_PTR *)v68;
          if ( v68 )
          {
            *(_DWORD *)(v68 + 48) &= ~1u;
            ExpInterlockedPushEntrySList((PSLIST_HEADER)(a6 + 1152), (PSLIST_ENTRY)(v68 + 32));
            BugCheckParameter3[0] = *v69;
            v119 = (void **)BugCheckParameter3[0];
            *((_QWORD *)v36 + 12) = BugCheckParameter3[0];
          }
          v63 = (_QWORD *)LowLimit;
        }
      }
    }
  }
  v70 = a6;
LABEL_242:
  v71 = W32GetUserSessionState(v65) + 69048;
  v72 = *(_QWORD *)v71;
  if ( *(_QWORD *)(*(_QWORD *)v71 + 8LL) != v71 )
    goto LABEL_348;
  *(_QWORD *)v36 = v72;
  *((_QWORD *)v36 + 1) = v71;
  *(_QWORD *)(v72 + 8) = v36;
  *(_QWORD *)v71 = v36;
  v73 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  *((_DWORD *)v36 + 20) = v73;
  *((_QWORD *)v36 + 5) = v70;
  *((_QWORD *)v36 + 4) = v116;
  *((_DWORD *)v36 + 33) = W32GetCurrentThreadDpiAwarenessContext(v73);
  *((_QWORD *)v36 + 8) = 0;
  v74 = v121;
  if ( v121 && (*(_DWORD *)v121 & 1) != 0 )
  {
    *v66 |= (*(_DWORD *)v121 & 0x100) != 0 ? 1024 : 2048;
    v75 = *v66;
    *((_QWORD *)v36 + 6) = *(_QWORD *)(v74 + 8);
    *((_QWORD *)v36 + 7) = *(_QWORD *)(v74 + 16);
    if ( (*(_DWORD *)v74 & 0x20) != 0 )
    {
      *v66 = v75 | 0x200;
      *((_QWORD *)v36 + 9) = *(_QWORD *)(v74 + 24);
    }
    else
    {
      *v66 = v75 | 0x100;
      *((_QWORD *)v36 + 8) = v125;
    }
  }
  if ( a9 )
    *v66 |= 0x10000u;
  v77 = *(_QWORD **)(a6 + 560);
  if ( *v77 != a6 + 552 )
    goto LABEL_348;
  *v63 = a6 + 552;
  v145 = (__int64)(v63 + 1);
  v63[1] = v77;
  *v77 = v63;
  *(_QWORD *)(a6 + 560) = v63;
  v143 = (_DWORD *)(a6 + 568);
  ++*(_DWORD *)(a6 + 568);
  if ( v116 )
  {
    v118 = *(void **)(v116 + 536);
    v135 = v118;
    *(_QWORD *)(v116 + 536) = v36;
  }
  else
  {
    v118 = 0;
    v135 = 0;
    *v66 |= 8u;
  }
  if ( (*v66 & 0x200) == 0
    && ((unsigned int)IsPointerInputMessageWithState(a2) || (unsigned int)IsPointerParentNotify(a2, a3)) )
  {
    v79 = W32GetUserSessionState(v78);
    CTouchProcessor::ReferenceMsgDataExternal(*(_QWORD *)(v79 + 3208), BugCheckParameter3[0], 6, v36);
  }
  EtwTraceBeginSendMessage(v36, v116, v121);
  if ( !v116 )
  {
    SetWakeBit(a6, 64);
    EtwTraceEndSendMessage(v36);
    return 1;
  }
  v142 = v36 + 72;
  v80 = 0;
  LODWORD(v125) = 0;
  SetWakeBit(a6, 64);
  if ( v121 )
  {
    v124 = *(_DWORD *)(v121 + 36);
    v81 = ((*(_DWORD *)(v121 + 32) & 1) << 15) + 512;
  }
  else
  {
    v124 = 0;
    v81 = 512;
  }
  v126 = v81;
  CKernelStackSwapAuto::CKernelStackSwapAuto((CKernelStackSwapAuto *)v144);
  if ( *(_QWORD *)(v116 + 464) == *(_QWORD *)(a6 + 464)
    && (_InterlockedCompareExchange((volatile signed __int32 *)(v116 + 520), 0, 0) & 0x10000) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(v116 + 520), 0x10000u);
    LODWORD(v125) = 1;
  }
  v82 = 0;
  if ( a2 == 788 )
  {
    if ( BugCheckParameter3[0] )
    {
      v82 = *(_QWORD *)BugCheckParameter3[0];
      if ( (*(_DWORD *)(BugCheckParameter3[0] + 24) & 1) != 0 )
      {
        *v66 |= 0x60000u;
        *((_QWORD *)v36 + 15) = *(_QWORD *)v82;
      }
    }
  }
  if ( (*v66 & 1) == 0 )
  {
    while ( 1 )
    {
      if ( v80 )
      {
LABEL_299:
        v36 = v128;
        goto LABEL_300;
      }
      Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3);
      v84 = 0;
      _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(v85 + 480) + 4LL), 0xFFFFFDFF);
      if ( v82
        && (*(_DWORD *)(v82 + 48) == 13 || *(_DWORD *)(v82 + 48) == 14)
        && *(_DWORD *)(v83 + 664) <= 0x501u
        && *(_DWORD *)(v83 + 680) )
      {
        v86 = PtiCurrent();
        Win32HM_LockIntoThread<1>(v86, v82, BugCheckParameter3);
        v84 = 1;
      }
      v87 = xxxSleepThread(v81, v124, 0, 0);
      v88 = v87;
      v80 = v87 == 0;
      if ( v84 )
        break;
LABEL_288:
      if ( !v88 && v121 )
      {
        v93 = *(_DWORD *)(v121 + 32);
        v94 = *v66;
        if ( ((v93 & 0x10) != 0 || (v94 & 0x20) != 0) && (v94 & 0x10) != 0 )
        {
          v124 = 0;
          v80 = 0;
        }
        if ( (v93 & 8) != 0 )
          v80 &= -IsThreadHung((const struct tagTHREADINFO *)a6);
        if ( !v80 )
          EtwTraceConvertTimeOutToBlocking();
      }
      Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)BugCheckParameter3);
      v81 = v126;
      if ( (*v66 & 1) != 0 )
        goto LABEL_299;
    }
    v89 = *(_DWORD *)(v82 + 64);
    if ( v87 )
    {
      v91 = v89 & 0xFFFFBFFF;
    }
    else
    {
      v90 = v89 | 0x4000;
      *(_DWORD *)(v82 + 64) = v90;
      if ( (v90 & 0x10) != 0 )
        goto LABEL_287;
      if ( ++*(_BYTE *)(v82 + 97) <= 0xAu )
        goto LABEL_287;
      v91 = v90 | 0x10;
    }
    *(_DWORD *)(v82 + 64) = v91;
LABEL_287:
    v92 = PtiCurrent();
    Win32HM_UnlockFromThread<1>((ULONG_PTR)v92, (ULONG_PTR)BugCheckParameter3);
    BugCheckParameter3[1] = 0;
    BugCheckParameter3[0] = -1;
    goto LABEL_288;
  }
LABEL_300:
  CKernelStackSwapAuto::~CKernelStackSwapAuto((CKernelStackSwapAuto *)v144);
  if ( (_DWORD)v125 )
  {
    _InterlockedAnd((volatile signed __int32 *)(v116 + 520), 0xFFFEFFFF);
    MergeDeferredMessagesOfThreadOnQueue(v116);
  }
  SetWakeBit(v116, 512);
  if ( v80 )
    goto LABEL_328;
  if ( !Size )
  {
    if ( a2 == 831 )
    {
      if ( a9 )
      {
        v106 = (__int64)v123;
        if ( v123 )
        {
          if ( (unsigned int)IsWindowDesktopComposed(v123) )
            TransformMessageBetweenCoordinateSpaces(831, 1, (unsigned int)&v133, (unsigned int)&v119, 0, v106);
        }
      }
    }
    goto LABEL_328;
  }
  v95 = v130;
  v128 = (char *)v130;
  if ( a2 == 131 )
  {
    if ( a9 )
    {
      v101 = (__int64)v123;
      if ( v123 )
      {
        if ( (unsigned int)IsWindowDesktopComposed(v123) )
        {
          TransformMessageBetweenCoordinateSpaces(131, 1, (unsigned int)&v133, (unsigned int)&v128, 0, v101);
          v95 = v128;
        }
        else
        {
          v95 = v130;
        }
      }
    }
    v102 = (__int128 *)*((_QWORD *)v36 + 15);
    v103 = *v102;
    if ( a3 )
    {
      v104 = v95[6];
      *(_OWORD *)v95 = v103;
      *((_OWORD *)v95 + 1) = v102[1];
      *((_OWORD *)v95 + 2) = v102[2];
      v95[6] = v104;
      v105 = *((_QWORD *)v102 + 6);
      if ( v105 )
      {
        *(_OWORD *)v104 = *(_OWORD *)v105;
        *(_OWORD *)(v104 + 16) = *(_OWORD *)(v105 + 16);
        *(_QWORD *)(v104 + 32) = *(_QWORD *)(v105 + 32);
      }
    }
    else
    {
      *(_OWORD *)v95 = v103;
    }
LABEL_328:
    v100 = v36 + 72;
    v99 = v118;
    goto LABEL_329;
  }
  v96 = (__int16 *)*((_QWORD *)v36 + 15);
  if ( v127 )
  {
    if ( v127 == 1 )
    {
      strncpycch(v130, v96, Size);
    }
    else
    {
      v97 = Size >> 1;
      v131 = Size >> 1;
      v138 = v96;
      v139 = v130;
      while ( v97 )
      {
        v98 = *v96++;
        v138 = v96;
        *(_WORD *)v95 = v98;
        v95 = (_QWORD *)((char *)v95 + 2);
        v139 = v95;
        if ( !v98 )
          break;
        v131 = --v97;
      }
    }
  }
  else
  {
    memmove(v130, v96, Size);
  }
  v99 = v118;
  v100 = v36 + 72;
LABEL_329:
  EtwTraceEndSendMessage(v36);
  *(_QWORD *)(v116 + 536) = v99;
  v107 = v121;
  if ( v121 )
  {
    **(_QWORD **)(v121 + 40) = *v100;
    if ( (*(_DWORD *)(v107 + 32) & 0x20) != 0 && (*v66 & 0x8000) != 0 )
    {
      v108 = 0;
      UserSetLastError(1400);
      v107 = v121;
    }
    else
    {
      v108 = v80 == 0;
    }
  }
  else
  {
    v108 = *v100;
  }
  if ( (v107 || v80) && (*v66 & 1) == 0 )
  {
    v109 = *v66 | 1;
    *v66 = v109;
    if ( (v109 & 0x4000) != 0 )
    {
      *v66 = v109 | 8;
      goto LABEL_343;
    }
    --*v143;
    v110 = (_QWORD *)LowLimit;
    v111 = *(_QWORD *)LowLimit;
    if ( *(_QWORD *)(*(_QWORD *)LowLimit + 8LL) == LowLimit )
    {
      v112 = *(_QWORD **)v145;
      if ( **(_QWORD **)v145 == LowLimit )
      {
        *v112 = v111;
        *(_QWORD *)(v111 + 8) = v112;
        *v110 = 0;
        *v66 |= 0x10u;
        goto LABEL_343;
      }
    }
LABEL_348:
    __fastfail(3u);
  }
LABEL_343:
  *v66 &= ~0x20000u;
  v113 = *v66;
  if ( (*v66 & 0x4010) != 0x10 )
  {
    v113 |= 8u;
    *v66 = v113;
  }
  if ( (v113 & 0x8008) != 8 )
    UnlinkSendListSms(v36);
  return v108;
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
