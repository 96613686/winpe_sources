# xxxInterSendMsgEx

- ea: `0x14001d1b4`
- end: `0x14001e884`
- name: `xxxInterSendMsgEx`
- size: `5840`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, __int64, ULONG_PTR, int, __int64, __int64, int, int)`
- caller_count: `8`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000583c`
- `0x14001cb60`
- `0x140022c54`
- `0x14002f410`
- `0x14002f530`
- `0x1400ea7ac`
- `0x14018f810`
- `0x14019be9c`

## callees

- `0x14000a3ec`
- `0x14001d1b4`
- `0x14002c2b0`
- `0x14002ea00`
- `0x14002f78c`
- `0x140035d14`
- `0x140082c38`
- `0x140094860`
- `0x140094910`
- `0x140096200`
- `0x1400bdb18`
- `0x1400c2a94`
- `0x1400e2cb0`
- `0x1400e6604`
- `0x1400e8c20`
- `0x1400eb8c4`
- `0x1400eb95c`
- `0x140128a00`
- `0x140144ae0`
- `0x140153f50`
- `0x14018935c`
- `0x14018c2b4`
- `0x1401ac2b8`
- `0x1401ad1bc`
- `0x1401b4070`
- `0x1402a96d4`
- `0x1402aae84`
- `0x1402b2e50`
- `0x140342fa0`
- `0x140343200`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x14001d2c1`
- `ntoskrnl!IoGetStackLimits` at `0x14001d2c1`
- `ntoskrnl!PsGetProcessCommonJob` at `0x14001d692`
- `ntoskrnl!PsGetProcessCommonJob` at `0x14001d692`
- `ntoskrnl!MmIsKernelAddress` at `0x14001d974`
- `ntoskrnl!MmIsKernelAddress` at `0x14001daac`
- `ntoskrnl!MmIsKernelAddress` at `0x14001db2a`
- `ntoskrnl!MmIsKernelAddress` at `0x14001db5c`
- `ntoskrnl!MmIsKernelAddress` at `0x14001d974`
- `ntoskrnl!MmIsKernelAddress` at `0x14001daac`
- `ntoskrnl!MmIsKernelAddress` at `0x14001db2a`
- `ntoskrnl!MmIsKernelAddress` at `0x14001db5c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001e02e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001e02e`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14001d247`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14001d247`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001d680`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001d680`
- `win32kbase!?ReferenceMsgDataExternal@CTouchProcessor@@QEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z` at `0x14001e24e`
- `win32kbase!?ReferenceMsgDataExternal@CTouchProcessor@@QEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z` at `0x14001e24e`
- `win32kbase!UserCheckForMessageAccessWithWindowCapability` at `0x14001d5d0`
- `win32kbase!UserCheckForMessageAccessWithWindowCapability` at `0x14001d5d0`
- `win32kbase!EtwTraceBeginSendMessage` at `0x14001e268`
- `win32kbase!EtwTraceBeginSendMessage` at `0x14001e268`
- `win32kbase!EtwTraceEndSendMessage` at `0x14001e28b`
- `win32kbase!EtwTraceEndSendMessage` at `0x14001e743`
- `win32kbase!EtwTraceEndSendMessage` at `0x14001e28b`
- `win32kbase!EtwTraceEndSendMessage` at `0x14001e743`
- `win32kbase!EtwTraceConvertTimeOutToBlocking` at `0x14001e4a2`
- `win32kbase!EtwTraceConvertTimeOutToBlocking` at `0x14001e4a2`
- `win32kbase!EtwTraceUIPIMsgError` at `0x14001d5aa`
- `win32kbase!EtwTraceUIPIMsgError` at `0x14001d5aa`
- `win32kbase!?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ` at `0x14001d62a`
- `win32kbase!?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ` at `0x14001d62a`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x14001d3b1`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x14001d3b1`
- `win32kbase!Win32AllocateFromPagedLookasideList` at `0x14001d713`
- `win32kbase!Win32AllocateFromPagedLookasideList` at `0x14001d713`
- `win32kbase!HMChangeOwnerThread` at `0x14001e156`
- `win32kbase!HMChangeOwnerThread` at `0x14001e156`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14001e0bd`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14001e0bd`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14001d53d`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14001d53d`
- `win32kbase!IsWindowDesktopComposed` at `0x14001defa`
- `win32kbase!IsWindowDesktopComposed` at `0x14001e637`
- `win32kbase!IsWindowDesktopComposed` at `0x14001e704`
- `win32kbase!IsWindowDesktopComposed` at `0x14001defa`
- `win32kbase!IsWindowDesktopComposed` at `0x14001e637`
- `win32kbase!IsWindowDesktopComposed` at `0x14001e704`
- `win32kbase!_HMObjectFromHandle` at `0x14001e136`
- `win32kbase!_HMObjectFromHandle` at `0x14001e136`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14001dbb3`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14001dbb3`
- `win32kbase!HMAssignmentLock` at `0x14001df79`
- `win32kbase!HMAssignmentLock` at `0x14001df79`
- `win32kbase!Win32FreePool` at `0x14001e841`
- `win32kbase!Win32FreePool` at `0x14001e841`
- `WIN32K!W32GetUserGdiSessionState` at `0x14001d3c1`
- `WIN32K!W32GetUserGdiSessionState` at `0x14001d4d4`
- `WIN32K!W32GetUserGdiSessionState` at `0x14001d3c1`
- `WIN32K!W32GetUserGdiSessionState` at `0x14001d4d4`
- `WIN32K!W32GetUserSessionState` at `0x14001d343`
- `WIN32K!W32GetUserSessionState` at `0x14001d700`
- `WIN32K!W32GetUserSessionState` at `0x14001e059`
- `WIN32K!W32GetUserSessionState` at `0x14001e22d`
- `WIN32K!W32GetUserSessionState` at `0x14001d343`
- `WIN32K!W32GetUserSessionState` at `0x14001d700`
- `WIN32K!W32GetUserSessionState` at `0x14001e059`
- `WIN32K!W32GetUserSessionState` at `0x14001e22d`

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
  __int64 v12; // rbx
  __int64 CurrentProcessWin32Process; // rax
  _DWORD *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  _DWORD *v18; // rbx
  UIPrivilegeIsolation *v19; // rcx
  int v20; // eax
  __int64 v21; // rsi
  int v22; // ebx
  int v23; // ebx
  const struct tagUIPI_INFO *v24; // r8
  const struct tagUIPI_INFO *v25; // rdx
  bool v26; // al
  __int64 v27; // r15
  struct tagWND *v28; // rsi
  void **v29; // r14
  __int64 v30; // rbx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r15
  __int64 v34; // rbx
  __int64 CurrentProcess; // rax
  __int64 UserSessionState; // rax
  __int64 v37; // rax
  void **v38; // rdx
  _OWORD *v39; // r9
  char *v40; // r12
  void **v41; // r15
  unsigned int v42; // esi
  unsigned __int64 v43; // rcx
  __int64 v44; // r8
  bool v45; // zf
  int v47; // eax
  bool v48; // zf
  bool v49; // zf
  unsigned __int64 v50; // rax
  void *v51; // rcx
  size_t v52; // r8
  const void *v53; // rdx
  __int64 v54; // rcx
  _OWORD *v55; // rax
  bool v56; // zf
  unsigned int v57; // edx
  size_t v58; // r8
  __int64 v59; // rbx
  void *v60; // rbx
  size_t v61; // r8
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
  __int64 v73; // rdx
  int v74; // ecx
  __int64 v75; // rax
  _QWORD *v76; // rcx
  __int64 v77; // rdx
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
  __int64 v95; // rdx
  __int64 v96; // r8
  __int64 v97; // r9
  _QWORD *v98; // r9
  __int16 *v99; // rdx
  unsigned int v100; // ecx
  __int16 v101; // ax
  void *v102; // r14
  _QWORD *v103; // r15
  struct tagWND *v104; // r14
  __int128 *v105; // rax
  __int128 v106; // xmm0
  __int64 v107; // rcx
  __int64 v108; // rdx
  struct tagWND *v109; // r14
  __int64 v110; // rdx
  __int64 v111; // r14
  int v112; // eax
  _QWORD *v113; // rdx
  __int64 v114; // rcx
  _QWORD *v115; // rax
  int v116; // ecx
  unsigned int Size; // [rsp+44h] [rbp-174h]
  __int64 v119; // [rsp+58h] [rbp-160h]
  void **v120; // [rsp+60h] [rbp-158h]
  void *v121; // [rsp+60h] [rbp-158h]
  void **v122; // [rsp+68h] [rbp-150h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+70h] [rbp-148h] BYREF
  struct tagWND *v124; // [rsp+80h] [rbp-138h]
  __int64 v125; // [rsp+88h] [rbp-130h]
  unsigned __int64 LowLimit; // [rsp+90h] [rbp-128h] BYREF
  unsigned int v127; // [rsp+98h] [rbp-120h]
  unsigned __int64 v128; // [rsp+A0h] [rbp-118h]
  unsigned int v129; // [rsp+A8h] [rbp-110h]
  int v130; // [rsp+ACh] [rbp-10Ch]
  char *v131; // [rsp+B0h] [rbp-108h] BYREF
  void *Src[2]; // [rsp+B8h] [rbp-100h] BYREF
  void *v133; // [rsp+C8h] [rbp-F0h]
  unsigned int v134; // [rsp+D0h] [rbp-E8h]
  int v135; // [rsp+D8h] [rbp-E0h]
  __int64 v136; // [rsp+E0h] [rbp-D8h] BYREF
  unsigned __int64 HighLimit; // [rsp+E8h] [rbp-D0h] BYREF
  void *v138; // [rsp+F0h] [rbp-C8h]
  __int64 v139; // [rsp+F8h] [rbp-C0h]
  void **v140; // [rsp+100h] [rbp-B8h]
  __int16 *v141; // [rsp+108h] [rbp-B0h]
  void *v142; // [rsp+110h] [rbp-A8h]
  char *v143; // [rsp+118h] [rbp-A0h]
  __int64 v144; // [rsp+120h] [rbp-98h]
  char *v145; // [rsp+128h] [rbp-90h]
  _DWORD *v146; // [rsp+130h] [rbp-88h]
  _BYTE v147[24]; // [rsp+148h] [rbp-70h] BYREF
  __int64 v148; // [rsp+160h] [rbp-58h] BYREF
  struct tagWND *v149; // [rsp+168h] [rbp-50h]

  v9 = a4;
  BugCheckParameter3[0] = a4;
  v124 = a1;
  v125 = a7;
  v136 = a3;
  v122 = (void **)a4;
  v12 = a6;
  v144 = a7;
  *(_OWORD *)Src = 0;
  v130 = 0;
  v135 = 0;
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
  v14 = (_DWORD *)CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
    v14 = (_DWORD *)(-(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process);
  v128 = (unsigned __int64)PtiCurrent();
  v15 = v128 & -(__int64)(a5 != 0);
  v119 = v15;
  if ( v15 && (_InterlockedCompareExchange((volatile signed __int32 *)(v15 + 520), 0, 0) & 1) != 0 )
    return 0;
  HighLimit = 0;
  LowLimit = 0;
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( (unsigned __int64)&HighLimit - LowLimit < 0x2000 )
    return 0;
  if ( a1 )
  {
    v18 = *(_DWORD **)(*((_QWORD *)a1 + 2) + 456LL);
    if ( v18 == v14 )
      goto LABEL_33;
    if ( a2 > 0xD0 )
    {
      if ( a2 == 272 )
        goto LABEL_30;
      if ( a2 != 353 && a2 != 424 && a2 != 563 && a2 != 648 )
        goto LABEL_29;
    }
    else if ( a2 != 208 && a2 != 12 )
    {
      if ( a2 == 13 )
        goto LABEL_16;
      if ( a2 != 78 )
      {
        if ( a2 != 188 )
        {
          if ( a2 == 196 || a2 == 204 )
          {
LABEL_16:
            v16 = *(_QWORD *)(W32GetUserSessionState(v17, v16) + 19704);
            if ( *(_WORD *)(v16 + 870) == *(_WORD *)(*(_QWORD *)(*((_QWORD *)a1 + 17) + 8LL) + 2LL)
              && (*(_BYTE *)(*((_QWORD *)a1 + 5) + 28LL) & 0x20) != 0 )
            {
              UserSetLastError(5);
LABEL_32:
              UserSetLastError(5);
              return 0;
            }
          }
LABEL_29:
          v20 = 0;
          goto LABEL_31;
        }
        goto LABEL_24;
      }
LABEL_30:
      v20 = 1;
LABEL_31:
      if ( v20 )
        goto LABEL_32;
      goto LABEL_33;
    }
LABEL_24:
    if ( !(unsigned int)Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline()
      && (!UIPrivilegeIsolation::Enforced(v19) || *(_QWORD *)v18 == *(_QWORD *)(W32GetUserGdiSessionState() + 40)) )
    {
      if ( v18[191] != v14[191] || v18[192] != v14[192] )
        goto LABEL_32;
      goto LABEL_29;
    }
LABEL_33:
    v12 = a6;
  }
  if ( a8 )
    goto LABEL_66;
  if ( a1 )
  {
    v21 = *(_QWORD *)(*((_QWORD *)a1 + 2) + 456LL);
  }
  else
  {
    v21 = 0;
    if ( v12 )
      v21 = *(_QWORD *)(v12 + 456);
  }
  if ( (_DWORD *)v21 == v14 )
    goto LABEL_66;
  if ( a2 == 717 )
    goto LABEL_64;
  v22 = IsMessageAllowedAcrossILByReceiver((struct tagPROCESSINFO *)v21, v124, a2);
  if ( !v22 )
    v22 = IsMessageAlwaysAllowedAcrossIL(a2);
  if ( v22 )
    goto LABEL_66;
  if ( a2 != 274 || ((a3 - 61472) & 0xFFFFFFFFFFFFFEBFuLL) != 0 || a3 == 61792 )
  {
    if ( (unsigned int)Feature_MsgUseCSRSSTrueIL__private_IsEnabledDeviceUsageNoInline() )
    {
      v25 = (const struct tagUIPI_INFO *)(v21 + 864);
    }
    else
    {
      v148 = 0;
      LODWORD(v149) = 0;
      if ( *(_QWORD *)v21 == *(_QWORD *)(W32GetUserGdiSessionState() + 40) )
      {
        v148 = 0x2000;
        LODWORD(v149) = 0;
      }
      else
      {
        v148 = *(_QWORD *)(v21 + 864);
        LODWORD(v149) = *(_DWORD *)(v21 + 872);
      }
      v25 = (const struct tagUIPI_INFO *)&v148;
    }
    v26 = UIPrivilegeIsolation::CheckAccess((UIPrivilegeIsolation *)(v14 + 216), v25, v24);
    v23 = v26;
    if ( v26 )
      goto LABEL_66;
    if ( v124 && a2 == 793 )
    {
      v27 = *((_QWORD *)v124 + 2);
      if ( *(struct tagWND **)(v27 + 1584) == v124 && *(_QWORD *)(v27 + 464) == *((_QWORD *)PtiCurrent() + 58) )
        v23 = 1;
      v9 = BugCheckParameter3[0];
    }
    if ( v23 )
      goto LABEL_66;
    EtwTraceUIPIMsgError(v14, v21, a2, a3, v9);
    UserSetLastError(5);
  }
  else
  {
    v23 = 1;
  }
  if ( v23 )
  {
LABEL_66:
    v28 = v124;
    goto LABEL_67;
  }
LABEL_64:
  v28 = v124;
  if ( !UserCheckForMessageAccessWithWindowCapability(v124, a2) )
    return 0;
LABEL_67:
  v29 = (void **)BugCheckParameter3[0];
  if ( a2 == 576 )
  {
    LOBYTE(v16) = 20;
  }
  else
  {
    if ( a2 != 281 )
      goto LABEL_72;
    LOBYTE(v16) = 21;
  }
  if ( !HMValidateHandleWithDescriptor(BugCheckParameter3[0], v16) )
    return 0;
LABEL_72:
  v30 = a6;
  if ( !tagPROCESSINFO::SyncAndTestFreeze(*(tagPROCESSINFO **)(a6 + 456)) )
    goto LABEL_87;
  v32 = v125;
  if ( v125 )
  {
    if ( (*(_DWORD *)(v125 + 32) & 0x40) != 0 )
    {
      v33 = v119;
      goto LABEL_81;
    }
    if ( *(_DWORD *)v125 == 2 && *(_DWORD *)(v125 + 36) )
      return 0;
  }
  v33 = v119;
  if ( v119 )
  {
    v34 = **(_QWORD **)(a6 + 456);
    CurrentProcess = PsGetCurrentProcess();
    if ( !PsGetProcessCommonJob(CurrentProcess, v34) )
      return 0;
    v32 = v125;
    v30 = a6;
LABEL_81:
    if ( v33 )
      goto LABEL_87;
  }
  if ( !v32 && (a2 == 537 || !(unsigned int)ProcessSuspendedSendMessage(v30, v28, a2, a3, BugCheckParameter3[0]))
    || !v33 && *(_DWORD *)(v30 + 568) > 0x2710u )
  {
    return 0;
  }
LABEL_87:
  UserSessionState = W32GetUserSessionState(v32, v31);
  v37 = Win32AllocateFromPagedLookasideList(*(_QWORD *)(UserSessionState + 69080));
  v40 = (char *)v37;
  v131 = (char *)v37;
  if ( !v37 )
    return 0;
  v139 = v37;
  LowLimit = 0;
  v41 = 0;
  v133 = 0;
  *(_QWORD *)(v37 + 120) = 0;
  Size = 0;
  v42 = 0;
  v120 = v29;
  v43 = v128;
  *(_DWORD *)(v37 + 128) = *(_DWORD *)(v128 + 1604);
  v44 = v125;
  if ( !v125 || *(_DWORD *)v125 != 33 )
  {
    if ( a2 > 0x14D )
    {
      if ( a2 > 0x1A2 )
      {
        if ( a2 == 536 )
        {
          if ( v29 && (a3 & 0x8000) != 0 && (!(unsigned __int8)MmIsKernelAddress(v29) || !v119) )
          {
            v42 = *((_DWORD *)v29 + 4) + 20;
            if ( *((_DWORD *)v29 + 4) >= 0xFFFFFFEC )
              goto LABEL_144;
          }
          goto LABEL_183;
        }
        if ( a2 != 537 )
        {
          if ( a2 == 544 )
          {
            v42 = (*((_DWORD *)v29 + 15) & 0x7FFFFFFF) + (*((_DWORD *)v29 + 19) & 0x7FFFFFFF);
            v41 = v29;
            goto LABEL_183;
          }
          if ( a2 == 643 )
          {
            if ( a3 == 24 )
              v42 = (*(_DWORD *)v29 << 9) + 4;
            goto LABEL_183;
          }
          if ( a2 == 780 )
            goto LABEL_166;
          if ( a2 == 833 )
          {
            v47 = 104;
          }
          else
          {
            if ( a2 == 834 )
            {
              v42 = 80;
              goto LABEL_184;
            }
            if ( a2 != 836 )
            {
              if ( a2 == 838 )
                v42 = 96;
              goto LABEL_183;
            }
            v47 = 1204;
          }
          v42 = v47;
LABEL_113:
          Size = v47;
          goto LABEL_183;
        }
        if ( !v29 || (a3 & 0x8000) == 0 || (unsigned __int8)MmIsKernelAddress(v29) && v119 )
          goto LABEL_183;
        goto LABEL_176;
      }
      if ( a2 == 418 )
        goto LABEL_139;
      if ( a2 > 0x18D )
      {
        if ( a2 != 399 )
        {
          if ( a2 != 401 && a2 != 402 )
          {
            v45 = a2 == 406;
LABEL_160:
            if ( !v45 )
              goto LABEL_183;
            goto LABEL_141;
          }
          goto LABEL_121;
        }
LABEL_139:
        v48 = *(_DWORD *)(v43 + 1604) == 1;
LABEL_140:
        if ( v48 )
          goto LABEL_183;
        goto LABEL_141;
      }
      if ( a2 != 397 )
      {
        if ( a2 == 344 || a2 == 384 || a2 == 385 )
          goto LABEL_139;
        if ( a2 == 393 )
          goto LABEL_166;
        v49 = a2 == 396;
        goto LABEL_138;
      }
    }
    else
    {
      if ( a2 == 333 )
        goto LABEL_139;
      if ( a2 <= 0x53 )
      {
        if ( a2 != 83 )
        {
          if ( a2 <= 0x38 )
          {
            if ( a2 == 56 )
            {
              v42 = *(unsigned __int16 *)v29;
              goto LABEL_183;
            }
            if ( a2 != 1 )
            {
              if ( a2 != 12 )
              {
                if ( a2 != 13 )
                {
                  if ( a2 != 26 )
                  {
                    v45 = a2 == 27;
                    goto LABEL_160;
                  }
                  goto LABEL_122;
                }
LABEL_166:
                *(_OWORD *)Src = *(_OWORD *)v29;
                v130 = (SHIDWORD(Src[0]) >= 0) + 1;
                v135 = v130;
                v29 = Src;
                BugCheckParameter3[0] = (ULONG_PTR)Src;
                v122 = Src;
                if ( !(unsigned __int8)MmIsKernelAddress(_mm_srli_si128(*(__m128i *)Src, 8).m128i_u64[0]) || !v119 )
                  v42 = HIDWORD(Src[0]) & 0x7FFFFFFF;
                goto LABEL_183;
              }
LABEL_122:
              v48 = v29 == 0;
              goto LABEL_140;
            }
LABEL_124:
            UserSetLastError(5);
            FreeSMS(v40, 1);
            return 0;
          }
          if ( a2 != 70 && a2 != 71 )
          {
            if ( a2 == 73 )
            {
              v42 = a3;
            }
            else if ( a2 == 74 )
            {
              LowLimit = (unsigned __int64)v29;
              if ( v29[2] )
              {
                v42 = *((_DWORD *)v29 + 2) + 24;
                if ( v42 < 0x18 )
                {
                  FreeSMS(v37, 1);
                  return 0;
                }
              }
              else
              {
                v42 = 24;
              }
            }
            goto LABEL_183;
          }
          v42 = 40;
          goto LABEL_112;
        }
LABEL_176:
        v42 = *(_DWORD *)v29;
        goto LABEL_183;
      }
      if ( a2 <= 0x143 )
      {
        if ( a2 != 323 )
        {
          switch ( a2 )
          {
            case 0x81u:
              goto LABEL_124;
            case 0x83u:
              v42 = a3 != 0 ? 96 : 16;
LABEL_112:
              v47 = v42;
              goto LABEL_113;
            case 0xC2u:
              goto LABEL_122;
            case 0xC4u:
              goto LABEL_166;
          }
          if ( a2 != 203 )
            goto LABEL_183;
LABEL_121:
          v42 = 4 * a3;
          goto LABEL_183;
        }
        goto LABEL_139;
      }
      if ( a2 != 325 )
      {
        if ( a2 == 328 )
          goto LABEL_166;
        if ( a2 == 330 )
          goto LABEL_139;
        v49 = a2 == 332;
LABEL_138:
        if ( !v49 )
          goto LABEL_183;
        goto LABEL_139;
      }
    }
LABEL_141:
    *(_OWORD *)Src = *(_OWORD *)v29;
    if ( !(unsigned __int8)MmIsKernelAddress(_mm_srli_si128(*(__m128i *)Src, 8).m128i_u64[0]) || !v119 )
    {
      v42 = LODWORD(Src[0]) + 18;
      if ( (unsigned int)(LODWORD(Src[0]) + 18) < LODWORD(Src[0]) )
      {
LABEL_144:
        FreeSMS(v40, 1);
        return 8;
      }
    }
LABEL_183:
    if ( !v42 )
      goto LABEL_216;
LABEL_184:
    v39 = (_OWORD *)Win32AllocPoolWithQuotaZInit(v42, 1668510549);
    *((_QWORD *)v40 + 15) = v39;
    if ( !v39 )
      goto LABEL_216;
    v133 = v29;
    v140 = v29;
    if ( a2 > 0x14C )
    {
      if ( a2 > 0x18D )
      {
        switch ( a2 )
        {
          case 0x18Fu:
            goto LABEL_214;
          case 0x191u:
            Size = v42;
            break;
          case 0x196u:
          case 0x1A2u:
            goto LABEL_214;
          case 0x220u:
            v38 = (void **)v41[10];
            if ( v38 )
            {
              v58 = *((unsigned int *)v41 + 19);
              LODWORD(v58) = v58 & 0x7FFFFFFF;
              memmove(v39, v38, v58);
              *v41 = (void *)*((_QWORD *)v40 + 15);
            }
            if ( *((_DWORD *)v41 + 14) )
            {
              v59 = *((unsigned int *)v41 + 19);
              LODWORD(v59) = v59 & 0x7FFFFFFF;
              v60 = (void *)(*((_QWORD *)v40 + 15) + v59);
              v61 = *((unsigned int *)v41 + 15);
              LODWORD(v61) = v61 & 0x7FFFFFFF;
              memmove(v60, v41[8], v61);
              v41[1] = v60;
            }
            goto LABEL_216;
          case 0x30Cu:
            goto LABEL_225;
        }
LABEL_231:
        v38 = v120;
        goto LABEL_232;
      }
      if ( a2 == 397 || a2 == 333 || a2 == 344 || a2 == 384 || a2 == 385 )
        goto LABEL_214;
      if ( a2 == 393 )
        goto LABEL_225;
      v56 = a2 == 396;
    }
    else
    {
      if ( a2 == 332 )
        goto LABEL_214;
      if ( a2 <= 0x83 )
      {
        if ( a2 == 131 )
        {
          v38 = v120;
          if ( a3 )
          {
            *v39 = *(_OWORD *)v120;
            v39[1] = *((_OWORD *)v120 + 1);
            v39[2] = *((_OWORD *)v120 + 2);
            *((_QWORD *)v39 + 6) = v120[6];
            v54 = *((_QWORD *)v40 + 15) + 56LL;
            *((_QWORD *)v39 + 6) = v54;
            v55 = v120[6];
            *(_OWORD *)v54 = *v55;
            *(_OWORD *)(v54 + 16) = v55[1];
            *(_QWORD *)(v54 + 32) = *((_QWORD *)v55 + 4);
LABEL_233:
            v29 = (void **)*((_QWORD *)v40 + 15);
            BugCheckParameter3[0] = (ULONG_PTR)v29;
            v122 = v29;
LABEL_216:
            if ( v42 && !*((_QWORD *)v40 + 15) )
            {
              FreeSMS(v40, 1);
              return 0;
            }
            if ( a9
              && v124
              && (unsigned int)IsWindowDesktopComposed(v124, v38, v44, v39)
              && !(unsigned int)IsPointerInputMessage(a2) )
            {
              TransformMessageBetweenCoordinateSpaces(
                v62,
                1,
                (unsigned int)&v136,
                (unsigned int)&v122,
                (__int64)v124,
                0);
              v29 = v122;
              BugCheckParameter3[0] = (ULONG_PTR)v122;
            }
            goto LABEL_239;
          }
LABEL_232:
          memmove(v39, v38, v42);
          goto LABEL_233;
        }
        if ( a2 == 12 )
          goto LABEL_214;
        if ( a2 != 13 )
        {
          if ( a2 != 26 && a2 != 27 )
          {
            if ( a2 == 74 )
            {
              v29 = (void **)v39;
              BugCheckParameter3[0] = (ULONG_PTR)v39;
              v122 = (void **)v39;
              v50 = LowLimit;
              *v39 = *(_OWORD *)LowLimit;
              *((_QWORD *)v39 + 2) = *(_QWORD *)(v50 + 16);
              if ( !*(_QWORD *)(v50 + 16) )
                goto LABEL_216;
              v51 = (char *)v39 + 24;
              *((_QWORD *)v39 + 2) = (char *)v39 + 24;
              v52 = *(unsigned int *)(v50 + 8);
              v53 = *(const void **)(v50 + 16);
              goto LABEL_215;
            }
            goto LABEL_231;
          }
LABEL_214:
          v29 = (void **)v39;
          BugCheckParameter3[0] = (ULONG_PTR)v39;
          v122 = (void **)v39;
          v57 = *((_DWORD *)v39 + 1) & 0x7FFFFFFF | HIDWORD(Src[0]) & 0x80000000;
          *((_DWORD *)v39 + 1) = v57;
          *(_DWORD *)v39 = Src[0];
          v51 = v39 + 1;
          *((_QWORD *)v39 + 1) = v39 + 1;
          v52 = v57 ^ (v57 ^ (v42 - 16)) & 0x7FFFFFFF;
          *((_DWORD *)v39 + 1) = v52;
          LODWORD(v52) = v52 & 0x7FFFFFFF;
          v53 = Src[1];
LABEL_215:
          memmove(v51, v53, v52);
          goto LABEL_216;
        }
        goto LABEL_225;
      }
      switch ( a2 )
      {
        case 0xC2u:
          goto LABEL_214;
        case 0xC4u:
          *(_WORD *)v39 = *(_WORD *)Src[1];
          goto LABEL_225;
        case 0x143u:
        case 0x145u:
          goto LABEL_214;
        case 0x148u:
LABEL_225:
          Size = v42;
          v133 = Src[1];
          v140 = (void **)Src[1];
          Src[1] = *((void **)v40 + 15);
          goto LABEL_216;
      }
      v56 = a2 == 330;
    }
    if ( v56 )
      goto LABEL_214;
    goto LABEL_231;
  }
LABEL_239:
  *((_QWORD *)v40 + 14) = 0;
  v63 = v40 + 16;
  LowLimit = (unsigned __int64)(v40 + 16);
  *((_QWORD *)v40 + 2) = 0;
  v148 = (__int64)(v40 + 112);
  v149 = v124;
  HMAssignmentLock(&v148, 0);
  *((_DWORD *)v40 + 26) = a2;
  *((_QWORD *)v40 + 11) = a3;
  *((_QWORD *)v40 + 12) = v29;
  v66 = (int *)(v40 + 84);
  v143 = v40 + 84;
  *((_DWORD *)v40 + 21) = 0;
  *((_QWORD *)v40 + 9) = 0;
  if ( a2 == 576 || a2 == 281 )
  {
    v75 = _HMObjectFromHandle(v29);
    if ( v75 )
    {
      v70 = a6;
      HMChangeOwnerThread(v75, a6);
      goto LABEL_249;
    }
  }
  else if ( a2 == 255 )
  {
    LOBYTE(v64) = 18;
    v67 = (struct tagHIDDATA *)HMValidateHandleNoSecure(v29, v64);
    if ( v67 )
    {
      v65 = (struct tagWND *)v128;
      if ( *(struct tagHIDDATA **)(v128 + 1136) == v67 )
      {
        v65 = v124;
        if ( v124 )
        {
          v68 = CopyHidData(v67);
          v69 = (ULONG_PTR *)v68;
          if ( v68 )
          {
            *(_DWORD *)(v68 + 48) &= ~1u;
            ExpInterlockedPushEntrySList((PSLIST_HEADER)(a6 + 1152), (PSLIST_ENTRY)(v68 + 32));
            BugCheckParameter3[0] = *v69;
            v122 = (void **)BugCheckParameter3[0];
            *((_QWORD *)v40 + 12) = BugCheckParameter3[0];
          }
          v63 = (_QWORD *)LowLimit;
        }
      }
    }
  }
  v70 = a6;
LABEL_249:
  v71 = W32GetUserSessionState(v65, v64) + 69048;
  v72 = *(_QWORD *)v71;
  if ( *(_QWORD *)(*(_QWORD *)v71 + 8LL) != v71 )
    goto LABEL_355;
  *(_QWORD *)v40 = v72;
  *((_QWORD *)v40 + 1) = v71;
  *(_QWORD *)(v72 + 8) = v40;
  *(_QWORD *)v71 = v40;
  *((_DWORD *)v40 + 20) = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  *((_QWORD *)v40 + 5) = v70;
  *((_QWORD *)v40 + 4) = v119;
  *((_DWORD *)v40 + 33) = W32GetCurrentThreadDpiAwarenessContext();
  *((_QWORD *)v40 + 8) = 0;
  v73 = v125;
  if ( v125 && (*(_DWORD *)v125 & 1) != 0 )
  {
    *v66 |= (*(_DWORD *)v125 & 0x100) != 0 ? 1024 : 2048;
    v74 = *v66;
    *((_QWORD *)v40 + 6) = *(_QWORD *)(v73 + 8);
    *((_QWORD *)v40 + 7) = *(_QWORD *)(v73 + 16);
    if ( (*(_DWORD *)v73 & 0x20) != 0 )
    {
      *v66 = v74 | 0x200;
      *((_QWORD *)v40 + 9) = *(_QWORD *)(v73 + 24);
    }
    else
    {
      *v66 = v74 | 0x100;
      *((_QWORD *)v40 + 8) = v128;
    }
  }
  if ( a9 )
    *v66 |= 0x10000u;
  v76 = *(_QWORD **)(a6 + 560);
  if ( *v76 != a6 + 552 )
    goto LABEL_355;
  *v63 = a6 + 552;
  v148 = (__int64)(v63 + 1);
  v63[1] = v76;
  *v76 = v63;
  *(_QWORD *)(a6 + 560) = v63;
  v146 = (_DWORD *)(a6 + 568);
  ++*(_DWORD *)(a6 + 568);
  if ( v119 )
  {
    v121 = *(void **)(v119 + 536);
    v138 = v121;
    *(_QWORD *)(v119 + 536) = v40;
  }
  else
  {
    v121 = 0;
    v138 = 0;
    *v66 |= 8u;
  }
  if ( (*v66 & 0x200) == 0
    && ((unsigned int)IsPointerInputMessageWithState(a2) || (unsigned int)IsPointerParentNotify(a2, a3)) )
  {
    v79 = W32GetUserSessionState(v78, v77);
    CTouchProcessor::ReferenceMsgDataExternal(*(_QWORD *)(v79 + 3208), BugCheckParameter3[0], 6, v40);
  }
  EtwTraceBeginSendMessage(v40, v119, v125);
  if ( !v119 )
  {
    SetWakeBit(a6, 64);
    EtwTraceEndSendMessage(v40);
    return 1;
  }
  v145 = v40 + 72;
  v80 = 0;
  LODWORD(v128) = 0;
  SetWakeBit(a6, 64);
  if ( v125 )
  {
    v127 = *(_DWORD *)(v125 + 36);
    v81 = ((*(_DWORD *)(v125 + 32) & 1) << 15) + 512;
  }
  else
  {
    v127 = 0;
    v81 = 512;
  }
  v129 = v81;
  CKernelStackSwapAuto::CKernelStackSwapAuto((CKernelStackSwapAuto *)v147);
  if ( *(_QWORD *)(v119 + 464) == *(_QWORD *)(a6 + 464)
    && (_InterlockedCompareExchange((volatile signed __int32 *)(v119 + 520), 0, 0) & 0x10000) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(v119 + 520), 0x10000u);
    LODWORD(v128) = 1;
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
        *((_QWORD *)v40 + 15) = *(_QWORD *)v82;
      }
    }
  }
  if ( (*v66 & 1) == 0 )
  {
    while ( 1 )
    {
      if ( v80 )
      {
LABEL_306:
        v40 = v131;
        goto LABEL_307;
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
      v87 = xxxSleepThread(v81, v127, 0, 0);
      v88 = v87;
      v80 = v87 == 0;
      if ( v84 )
        break;
LABEL_295:
      if ( !v88 && v125 )
      {
        v93 = *(_DWORD *)(v125 + 32);
        v94 = *v66;
        if ( ((v93 & 0x10) != 0 || (v94 & 0x20) != 0) && (v94 & 0x10) != 0 )
        {
          v127 = 0;
          v80 = 0;
        }
        if ( (v93 & 8) != 0 )
          v80 &= -IsThreadHung((const struct tagTHREADINFO *)a6);
        if ( !v80 )
          EtwTraceConvertTimeOutToBlocking();
      }
      Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)BugCheckParameter3);
      v81 = v129;
      if ( (*v66 & 1) != 0 )
        goto LABEL_306;
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
        goto LABEL_294;
      if ( ++*(_BYTE *)(v82 + 97) <= 0xAu )
        goto LABEL_294;
      v91 = v90 | 0x10;
    }
    *(_DWORD *)(v82 + 64) = v91;
LABEL_294:
    v92 = PtiCurrent();
    Win32HM_UnlockFromThread<1>((ULONG_PTR)v92, (ULONG_PTR)BugCheckParameter3);
    BugCheckParameter3[1] = 0;
    BugCheckParameter3[0] = -1;
    goto LABEL_295;
  }
LABEL_307:
  CKernelStackSwapAuto::~CKernelStackSwapAuto((CKernelStackSwapAuto *)v147);
  if ( (_DWORD)v128 )
  {
    _InterlockedAnd((volatile signed __int32 *)(v119 + 520), 0xFFFEFFFF);
    MergeDeferredMessagesOfThreadOnQueue(v119);
  }
  SetWakeBit(v119, 512);
  if ( v80 )
    goto LABEL_335;
  if ( !Size )
  {
    if ( a2 == 831 )
    {
      if ( a9 )
      {
        v109 = v124;
        if ( v124 )
        {
          if ( (unsigned int)IsWindowDesktopComposed(v124, v95, v96, v97) )
            TransformMessageBetweenCoordinateSpaces(831, 1, (unsigned int)&v136, (unsigned int)&v122, 0, (__int64)v109);
        }
      }
    }
    goto LABEL_335;
  }
  v98 = v133;
  v131 = (char *)v133;
  if ( a2 == 131 )
  {
    if ( a9 )
    {
      v104 = v124;
      if ( v124 )
      {
        if ( (unsigned int)IsWindowDesktopComposed(v124, v95, v96, v133) )
        {
          TransformMessageBetweenCoordinateSpaces(131, 1, (unsigned int)&v136, (unsigned int)&v131, 0, (__int64)v104);
          v98 = v131;
        }
        else
        {
          v98 = v133;
        }
      }
    }
    v105 = (__int128 *)*((_QWORD *)v40 + 15);
    v106 = *v105;
    if ( a3 )
    {
      v107 = v98[6];
      *(_OWORD *)v98 = v106;
      *((_OWORD *)v98 + 1) = v105[1];
      *((_OWORD *)v98 + 2) = v105[2];
      v98[6] = v107;
      v108 = *((_QWORD *)v105 + 6);
      if ( v108 )
      {
        *(_OWORD *)v107 = *(_OWORD *)v108;
        *(_OWORD *)(v107 + 16) = *(_OWORD *)(v108 + 16);
        *(_QWORD *)(v107 + 32) = *(_QWORD *)(v108 + 32);
      }
    }
    else
    {
      *(_OWORD *)v98 = v106;
    }
LABEL_335:
    v103 = v40 + 72;
    v102 = v121;
    goto LABEL_336;
  }
  v99 = (__int16 *)*((_QWORD *)v40 + 15);
  if ( v130 )
  {
    if ( v130 == 1 )
    {
      strncpycch(v133, v99, Size);
    }
    else
    {
      v100 = Size >> 1;
      v134 = Size >> 1;
      v141 = v99;
      v142 = v133;
      while ( v100 )
      {
        v101 = *v99++;
        v141 = v99;
        *(_WORD *)v98 = v101;
        v98 = (_QWORD *)((char *)v98 + 2);
        v142 = v98;
        if ( !v101 )
          break;
        v134 = --v100;
      }
    }
  }
  else
  {
    memmove(v133, v99, Size);
  }
  v102 = v121;
  v103 = v40 + 72;
LABEL_336:
  EtwTraceEndSendMessage(v40);
  *(_QWORD *)(v119 + 536) = v102;
  v110 = v125;
  if ( v125 )
  {
    **(_QWORD **)(v125 + 40) = *v103;
    if ( (*(_DWORD *)(v110 + 32) & 0x20) != 0 && (*v66 & 0x8000) != 0 )
    {
      v111 = 0;
      UserSetLastError(1400);
      v110 = v125;
    }
    else
    {
      v111 = v80 == 0;
    }
  }
  else
  {
    v111 = *v103;
  }
  if ( (v110 || v80) && (*v66 & 1) == 0 )
  {
    v112 = *v66 | 1;
    *v66 = v112;
    if ( (v112 & 0x4000) != 0 )
    {
      *v66 = v112 | 8;
      goto LABEL_350;
    }
    --*v146;
    v113 = (_QWORD *)LowLimit;
    v114 = *(_QWORD *)LowLimit;
    if ( *(_QWORD *)(*(_QWORD *)LowLimit + 8LL) == LowLimit )
    {
      v115 = *(_QWORD **)v148;
      if ( **(_QWORD **)v148 == LowLimit )
      {
        *v115 = v114;
        *(_QWORD *)(v114 + 8) = v115;
        *v113 = 0;
        *v66 |= 0x10u;
        goto LABEL_350;
      }
    }
LABEL_355:
    __fastfail(3u);
  }
LABEL_350:
  *v66 &= ~0x20000u;
  v116 = *v66;
  if ( (*v66 & 0x4010) != 0x10 )
  {
    v116 |= 8u;
    *v66 = v116;
  }
  if ( (v116 & 0x8008) != 8 )
    UnlinkSendListSms(v40);
  return v111;
}

```

## disassembly

```asm
0x14001d1b4  push    rbx
0x14001d1b6  push    rsi
0x14001d1b7  push    rdi
0x14001d1b8  push    r12
0x14001d1ba  push    r13
0x14001d1bc  push    r14
0x14001d1be  push    r15
0x14001d1c0  sub     rsp, 180h
0x14001d1c7  mov     rax, cs:__security_cookie
0x14001d1ce  xor     rax, rsp
0x14001d1d1  mov     [rsp+1B8h+var_48], rax
0x14001d1d9  mov     r15, r9
0x14001d1dc  mov     [rsp+1B8h+BugCheckParameter3], r9
0x14001d1e1  mov     [rsp+1B8h+var_168], r8
0x14001d1e6  mov     r13d, edx
0x14001d1e9  mov     rsi, rcx
0x14001d1ec  mov     [rsp+1B8h+var_138], rcx
0x14001d1f4  mov     rax, [rsp+1B8h+arg_30]
0x14001d1fc  mov     [rsp+1B8h+var_130], rax
0x14001d204  mov     [rsp+1B8h+var_D8], r8
0x14001d20c  mov     [rsp+1B8h+var_150], r9
0x14001d211  mov     rbx, [rsp+1B8h+arg_28]
0x14001d219  mov     [rsp+1B8h+var_180], rbx
0x14001d21e  mov     [rsp+1B8h+var_98], rax
0x14001d226  xor     edi, edi
0x14001d228  mov     [rsp+1B8h+var_178], edi
0x14001d22c  xorps   xmm0, xmm0
0x14001d22f  movups  xmmword ptr [rsp+1B8h+Src], xmm0
0x14001d237  mov     eax, edi
0x14001d239  mov     [rsp+1B8h+var_10C], eax
0x14001d240  mov     [rsp+1B8h+var_E0], eax
0x14001d247  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14001d24e  nop     dword ptr [rax+rax+00h]
0x14001d253  mov     r14, rax
0x14001d256  test    rax, rax
0x14001d259  jz      short loc_14001D267
0x14001d25b  mov     rax, [rax]
0x14001d25e  neg     rax
0x14001d261  sbb     rcx, rcx
0x14001d264  and     r14, rcx
0x14001d267  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001d26c  mov     [rsp+1B8h+var_118], rax
0x14001d274  neg     [rsp+1B8h+arg_20]
0x14001d27b  sbb     rcx, rcx
0x14001d27e  and     rcx, rax
0x14001d281  mov     [rsp+1B8h+var_160], rcx
0x14001d286  mov     r12d, 1
0x14001d28c  jz      short loc_14001D2A1
0x14001d28e  xor     eax, eax
0x14001d290  lock cmpxchg [rcx+208h], edi
0x14001d298  test    r12b, al
0x14001d29b  jnz     loc_14001E85E
0x14001d2a1  mov     [rsp+1B8h+HighLimit], rdi
0x14001d2a9  mov     [rsp+1B8h+LowLimit], rdi
0x14001d2b1  lea     rdx, [rsp+1B8h+HighLimit]; HighLimit
0x14001d2b9  lea     rcx, [rsp+1B8h+LowLimit]; LowLimit
0x14001d2c1  call    cs:__imp_IoGetStackLimits
0x14001d2c8  nop     dword ptr [rax+rax+00h]
0x14001d2cd  lea     rax, [rsp+1B8h+HighLimit]
0x14001d2d5  sub     rax, [rsp+1B8h+LowLimit]
0x14001d2dd  cmp     rax, 2000h
0x14001d2e3  jb      loc_14001E85E
0x14001d2e9  test    rsi, rsi
0x14001d2ec  jz      loc_14001D413
0x14001d2f2  mov     rax, [rsi+10h]
0x14001d2f6  mov     rbx, [rax+1C8h]
0x14001d2fd  cmp     rbx, r14
0x14001d300  jz      loc_14001D40E
0x14001d306  mov     eax, 0D0h
0x14001d30b  cmp     r13d, eax
0x14001d30e  ja      short loc_14001D388
0x14001d310  jz      loc_14001D3A8
0x14001d316  mov     eax, r13d
0x14001d319  sub     eax, 0Ch
0x14001d31c  jz      loc_14001D3A8
0x14001d322  sub     eax, 1
0x14001d325  jz      short loc_14001D343
0x14001d327  sub     eax, 41h ; 'A'
0x14001d32a  jz      loc_14001D3F8
0x14001d330  sub     eax, 6Eh ; 'n'
0x14001d333  jz      short loc_14001D3A8
0x14001d335  sub     eax, 8
0x14001d338  jz      short loc_14001D343
0x14001d33a  cmp     eax, 8
0x14001d33d  jnz     loc_14001D3F4
0x14001d343  call    cs:__imp_W32GetUserSessionState
0x14001d34a  nop     dword ptr [rax+rax+00h]
0x14001d34f  mov     rdx, [rax+4CF8h]
0x14001d356  mov     rax, [rsi+88h]
0x14001d35d  mov     rcx, [rax+8]
0x14001d361  movzx   eax, word ptr [rcx+2]
0x14001d365  cmp     [rdx+366h], ax
0x14001d36c  jnz     loc_14001D3F4
0x14001d372  mov     rax, [rsi+28h]
0x14001d376  test    byte ptr [rax+1Ch], 20h
0x14001d37a  jz      short loc_14001D3F4
0x14001d37c  mov     ecx, 5
0x14001d381  call    UserSetLastError
0x14001d386  jmp     short loc_14001D3FF
0x14001d388  mov     eax, r13d
0x14001d38b  sub     eax, 110h
0x14001d390  jz      short loc_14001D3F8
0x14001d392  sub     eax, 51h ; 'Q'
0x14001d395  jz      short loc_14001D3A8
0x14001d397  sub     eax, 47h ; 'G'
0x14001d39a  jz      short loc_14001D3A8
0x14001d39c  sub     eax, 8Bh
0x14001d3a1  jz      short loc_14001D3A8
0x14001d3a3  cmp     eax, 55h ; 'U'
0x14001d3a6  jnz     short loc_14001D3F4
0x14001d3a8  call    Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline
0x14001d3ad  test    eax, eax
0x14001d3af  jnz     short loc_14001D40E
0x14001d3b1  call    cs:__imp_?Enforced@UIPrivilegeIsolation@@YA_NXZ; UIPrivilegeIsolation::Enforced(void)
0x14001d3b8  nop     dword ptr [rax+rax+00h]
0x14001d3bd  test    al, al
0x14001d3bf  jz      short loc_14001D3D6
0x14001d3c1  call    cs:__imp_W32GetUserGdiSessionState
0x14001d3c8  nop     dword ptr [rax+rax+00h]
0x14001d3cd  mov     rcx, [rax+28h]
0x14001d3d1  cmp     [rbx], rcx
0x14001d3d4  jnz     short loc_14001D40E
0x14001d3d6  mov     eax, [r14+2FCh]
0x14001d3dd  cmp     [rbx+2FCh], eax
0x14001d3e3  jnz     short loc_14001D3FF
0x14001d3e5  mov     eax, [r14+300h]
0x14001d3ec  cmp     [rbx+300h], eax
0x14001d3f2  jnz     short loc_14001D3FF
0x14001d3f4  mov     eax, edi
0x14001d3f6  jmp     short loc_14001D3FB
0x14001d3f8  mov     eax, r12d
0x14001d3fb  test    eax, eax
0x14001d3fd  jz      short loc_14001D40E
0x14001d3ff  mov     ecx, 5
0x14001d404  call    UserSetLastError
0x14001d409  jmp     loc_14001E85E
0x14001d40e  mov     rbx, [rsp+1B8h+var_180]
0x14001d413  cmp     [rsp+1B8h+arg_38], edi
0x14001d41a  jnz     loc_14001D5E6
0x14001d420  test    rsi, rsi
0x14001d423  jz      short loc_14001D432
0x14001d425  mov     rax, [rsi+10h]
0x14001d429  mov     rsi, [rax+1C8h]
0x14001d430  jmp     short loc_14001D441
0x14001d432  mov     rsi, rdi
0x14001d435  test    rbx, rbx
0x14001d438  jz      short loc_14001D441
0x14001d43a  mov     rsi, [rbx+1C8h]
0x14001d441  cmp     rsi, r14
0x14001d444  jz      loc_14001D5E6
0x14001d44a  cmp     r13d, 2CDh
0x14001d451  jz      loc_14001D5C2
0x14001d457  mov     r8d, r13d; unsigned int
0x14001d45a  mov     rdx, [rsp+1B8h+var_138]; struct tagWND *
0x14001d462  mov     rcx, rsi; struct tagPROCESSINFO *
0x14001d465  call    ?IsMessageAllowedAcrossILByReceiver@@YAHPEAUtagPROCESSINFO@@PEAUtagWND@@I@Z; IsMessageAllowedAcrossILByReceiver(tagPROCESSINFO *,tagWND *,uint)
0x14001d46a  mov     ebx, eax
0x14001d46c  test    eax, eax
0x14001d46e  jnz     short loc_14001D47A
0x14001d470  mov     ecx, r13d; unsigned int
0x14001d473  call    ?IsMessageAlwaysAllowedAcrossIL@@YAHI@Z; IsMessageAlwaysAllowedAcrossIL(uint)
0x14001d478  mov     ebx, eax
0x14001d47a  test    ebx, ebx
0x14001d47c  jnz     loc_14001D5E6
0x14001d482  cmp     r13d, 112h
0x14001d489  jnz     short loc_14001D4B0
0x14001d48b  mov     rcx, [rsp+1B8h+var_168]
0x14001d490  lea     rax, [rcx-0F020h]
0x14001d497  test    rax, 0FFFFFFFFFFFFFEBFh
0x14001d49d  jnz     short loc_14001D4B0
0x14001d49f  cmp     rcx, 0F160h
0x14001d4a6  jz      short loc_14001D4B0
0x14001d4a8  mov     ebx, r12d
0x14001d4ab  jmp     loc_14001D5BE
0x14001d4b0  mov     ebx, edi
0x14001d4b2  test    ebx, ebx
0x14001d4b4  jnz     loc_14001D5E6
0x14001d4ba  call    Feature_MsgUseCSRSSTrueIL__private_IsEnabledDeviceUsageNoInline
0x14001d4bf  test    eax, eax
0x14001d4c1  jnz     short loc_14001D52F
0x14001d4c3  xor     eax, eax
0x14001d4c5  mov     [rsp+1B8h+var_58], rax
0x14001d4cd  mov     dword ptr [rsp+1B8h+var_50], eax
0x14001d4d4  call    cs:__imp_W32GetUserGdiSessionState
0x14001d4db  nop     dword ptr [rax+rax+00h]
0x14001d4e0  mov     rcx, [rax+28h]
0x14001d4e4  cmp     [rsi], rcx
0x14001d4e7  jnz     short loc_14001D4FE
0x14001d4e9  mov     [rsp+1B8h+var_58], 2000h
0x14001d4f5  mov     dword ptr [rsp+1B8h+var_50], edi
0x14001d4fc  jmp     short loc_14001D525
0x14001d4fe  mov     eax, [rsi+360h]
0x14001d504  mov     dword ptr [rsp+1B8h+var_58], eax
0x14001d50b  mov     eax, [rsi+364h]
0x14001d511  mov     dword ptr [rsp+1B8h+var_58+4], eax
0x14001d518  mov     eax, [rsi+368h]
0x14001d51e  mov     dword ptr [rsp+1B8h+var_50], eax
0x14001d525  lea     rdx, [rsp+1B8h+var_58]
0x14001d52d  jmp     short loc_14001D536
0x14001d52f  lea     rdx, [rsi+360h]
0x14001d536  lea     rcx, [r14+360h]
0x14001d53d  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x14001d544  nop     dword ptr [rax+rax+00h]
0x14001d549  movzx   ebx, al
0x14001d54c  test    ebx, ebx
0x14001d54e  jnz     loc_14001D5E6
0x14001d554  mov     rax, [rsp+1B8h+var_138]
0x14001d55c  test    rax, rax
0x14001d55f  jz      short loc_14001D593
0x14001d561  cmp     r13d, 319h
0x14001d568  jnz     short loc_14001D593
0x14001d56a  mov     r15, [rax+10h]
0x14001d56e  cmp     [r15+630h], rax
0x14001d575  jnz     short loc_14001D58E
0x14001d577  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001d57c  mov     rax, [rax+1D0h]
0x14001d583  cmp     [r15+1D0h], rax
0x14001d58a  cmovz   ebx, r12d
0x14001d58e  mov     r15, [rsp+1B8h+BugCheckParameter3]
0x14001d593  test    ebx, ebx
0x14001d595  jnz     short loc_14001D5E6
0x14001d597  mov     [rsp+1B8h+var_198], r15
0x14001d59c  mov     r9, [rsp+1B8h+var_168]
0x14001d5a1  mov     r8d, r13d
0x14001d5a4  mov     rdx, rsi
0x14001d5a7  mov     rcx, r14
0x14001d5aa  call    cs:__imp_EtwTraceUIPIMsgError
0x14001d5b1  nop     dword ptr [rax+rax+00h]
0x14001d5b6  lea     ecx, [rbx+5]
0x14001d5b9  call    UserSetLastError
0x14001d5be  test    ebx, ebx
0x14001d5c0  jnz     short loc_14001D5E6
0x14001d5c2  mov     edx, r13d
0x14001d5c5  mov     rsi, [rsp+1B8h+var_138]
0x14001d5cd  mov     rcx, rsi
0x14001d5d0  call    cs:__imp_?UserCheckForMessageAccessWithWindowCapability@@YAHPEAUtagWND@@I@Z; UserCheckForMessageAccessWithWindowCapability(tagWND *,uint)
0x14001d5d7  nop     dword ptr [rax+rax+00h]
0x14001d5dc  test    eax, eax
0x14001d5de  jz      loc_14001E85E
0x14001d5e4  jmp     short loc_14001D5EE
0x14001d5e6  mov     rsi, [rsp+1B8h+var_138]
0x14001d5ee  lea     eax, [r13-240h]
0x14001d5f5  mov     r14, [rsp+1B8h+BugCheckParameter3]
0x14001d5fa  test    eax, eax
0x14001d5fc  jnz     short loc_14001D602
0x14001d5fe  mov     dl, 14h
0x14001d600  jmp     short loc_14001D60D
0x14001d602  cmp     r13d, 119h
0x14001d609  jnz     short loc_14001D61E
0x14001d60b  mov     dl, 15h
0x14001d60d  mov     rcx, r14
0x14001d610  call    HMValidateHandleWithDescriptor
0x14001d615  test    rax, rax
0x14001d618  jz      loc_14001E85E
0x14001d61e  mov     rbx, [rsp+1B8h+var_180]
0x14001d623  mov     rcx, [rbx+1C8h]
0x14001d62a  call    cs:__imp_?SyncAndTestFreeze@tagPROCESSINFO@@QEAA_NXZ; tagPROCESSINFO::SyncAndTestFreeze(void)
0x14001d631  nop     dword ptr [rax+rax+00h]
0x14001d636  test    al, al
0x14001d638  jz      loc_14001D700
0x14001d63e  mov     rcx, [rsp+1B8h+var_130]
0x14001d646  test    rcx, rcx
0x14001d649  jz      short loc_14001D66C
0x14001d64b  mov     eax, [rcx+20h]
0x14001d64e  test    al, 40h
0x14001d650  jz      short loc_14001D659
0x14001d652  mov     r15, [rsp+1B8h+var_160]
0x14001d657  jmp     short loc_14001D6B4
0x14001d659  test    rcx, rcx
0x14001d65c  jz      short loc_14001D66C
0x14001d65e  cmp     dword ptr [rcx], 2
0x14001d661  jnz     short loc_14001D66C
0x14001d663  cmp     [rcx+24h], edi
0x14001d666  jnz     loc_14001E85E
0x14001d66c  mov     r15, [rsp+1B8h+var_160]
0x14001d671  test    r15, r15
0x14001d674  jz      short loc_14001D6B9
0x14001d676  mov     rax, [rbx+1C8h]
0x14001d67d  mov     rbx, [rax]
0x14001d680  call    cs:__imp_PsGetCurrentProcess
0x14001d687  nop     dword ptr [rax+rax+00h]
0x14001d68c  mov     rdx, rbx
0x14001d68f  mov     rcx, rax
0x14001d692  call    cs:__imp_PsGetProcessCommonJob
0x14001d699  nop     dword ptr [rax+rax+00h]
0x14001d69e  test    rax, rax
0x14001d6a1  jz      loc_14001E85E
0x14001d6a7  mov     rcx, [rsp+1B8h+var_130]
0x14001d6af  mov     rbx, [rsp+1B8h+var_180]
0x14001d6b4  test    r15, r15
0x14001d6b7  jnz     short loc_14001D700
0x14001d6b9  test    rcx, rcx
0x14001d6bc  jnz     short loc_14001D6EB
0x14001d6be  cmp     r13d, 219h
0x14001d6c5  jz      loc_14001E85E
0x14001d6cb  mov     [rsp+1B8h+var_198], r14
0x14001d6d0  mov     r9, [rsp+1B8h+var_168]
0x14001d6d5  mov     r8d, r13d
0x14001d6d8  mov     rdx, rsi
0x14001d6db  mov     rcx, rbx
  ... truncated ...
```
