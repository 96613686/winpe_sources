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
  _DWORD *v17; // rbx
  UIPrivilegeIsolation *v18; // rcx
  int v19; // eax
  __int64 v20; // rsi
  int v21; // ebx
  int v22; // ebx
  const struct tagUIPI_INFO *v23; // r8
  const struct tagUIPI_INFO *v24; // rdx
  bool v25; // al
  __int64 v26; // r15
  struct tagWND *v27; // rsi
  void **v28; // r14
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // r15
  __int64 v32; // rbx
  __int64 CurrentProcess; // rax
  __int64 UserSessionState; // rax
  __int64 v35; // rax
  void **v36; // rdx
  _OWORD *v37; // r9
  char *v38; // r12
  void **v39; // r15
  unsigned int v40; // esi
  unsigned __int64 v41; // rcx
  __int64 v42; // r8
  bool v43; // zf
  int v45; // eax
  bool v46; // zf
  bool v47; // zf
  unsigned __int64 v48; // rax
  void *v49; // rcx
  size_t v50; // r8
  const void *v51; // rdx
  __int64 v52; // rcx
  _OWORD *v53; // rax
  bool v54; // zf
  unsigned int v55; // edx
  size_t v56; // r8
  __int64 v57; // rbx
  void *v58; // rbx
  size_t v59; // r8
  int v60; // ecx
  _QWORD *v61; // rsi
  __int64 v62; // rdx
  int *v63; // rbx
  struct tagHIDDATA *v64; // rax
  __int64 v65; // rax
  ULONG_PTR *v66; // rsi
  __int64 v67; // r14
  __int64 v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rdx
  int v71; // ecx
  __int64 v72; // rax
  _QWORD *v73; // rcx
  __int64 v74; // rax
  int v75; // esi
  unsigned int v76; // r15d
  __int64 v77; // r14
  __int64 v78; // r8
  char v79; // r12
  __int64 v80; // rdx
  struct tagTHREADINFO *v81; // rax
  int v82; // eax
  int v83; // r15d
  int v84; // ecx
  int v85; // ecx
  unsigned int v86; // ecx
  struct tagTHREADINFO *v87; // rax
  int v88; // ecx
  int v89; // eax
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r9
  _QWORD *v93; // r9
  __int16 *v94; // rdx
  unsigned int v95; // ecx
  __int16 v96; // ax
  void *v97; // r14
  _QWORD *v98; // r15
  struct tagWND *v99; // r14
  __int128 *v100; // rax
  __int128 v101; // xmm0
  __int64 v102; // rcx
  __int64 v103; // rdx
  struct tagWND *v104; // r14
  __int64 v105; // rdx
  __int64 v106; // r14
  int v107; // eax
  _QWORD *v108; // rdx
  __int64 v109; // rcx
  _QWORD *v110; // rax
  int v111; // ecx
  unsigned int Size; // [rsp+44h] [rbp-174h]
  __int64 v114; // [rsp+58h] [rbp-160h]
  void **v115; // [rsp+60h] [rbp-158h]
  void *v116; // [rsp+60h] [rbp-158h]
  void **v117; // [rsp+68h] [rbp-150h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+70h] [rbp-148h] BYREF
  struct tagWND *v119; // [rsp+80h] [rbp-138h]
  __int64 v120; // [rsp+88h] [rbp-130h]
  unsigned __int64 LowLimit; // [rsp+90h] [rbp-128h] BYREF
  unsigned int v122; // [rsp+98h] [rbp-120h]
  unsigned __int64 v123; // [rsp+A0h] [rbp-118h]
  unsigned int v124; // [rsp+A8h] [rbp-110h]
  int v125; // [rsp+ACh] [rbp-10Ch]
  char *v126; // [rsp+B0h] [rbp-108h] BYREF
  void *Src[2]; // [rsp+B8h] [rbp-100h] BYREF
  void *v128; // [rsp+C8h] [rbp-F0h]
  unsigned int v129; // [rsp+D0h] [rbp-E8h]
  int v130; // [rsp+D8h] [rbp-E0h]
  __int64 v131; // [rsp+E0h] [rbp-D8h] BYREF
  unsigned __int64 HighLimit; // [rsp+E8h] [rbp-D0h] BYREF
  void *v133; // [rsp+F0h] [rbp-C8h]
  __int64 v134; // [rsp+F8h] [rbp-C0h]
  void **v135; // [rsp+100h] [rbp-B8h]
  __int16 *v136; // [rsp+108h] [rbp-B0h]
  void *v137; // [rsp+110h] [rbp-A8h]
  char *v138; // [rsp+118h] [rbp-A0h]
  __int64 v139; // [rsp+120h] [rbp-98h]
  char *v140; // [rsp+128h] [rbp-90h]
  _DWORD *v141; // [rsp+130h] [rbp-88h]
  _BYTE v142[24]; // [rsp+148h] [rbp-70h] BYREF
  __int64 v143; // [rsp+160h] [rbp-58h] BYREF
  struct tagWND *v144; // [rsp+168h] [rbp-50h]

  v9 = a4;
  BugCheckParameter3[0] = a4;
  v119 = a1;
  v120 = a7;
  v131 = a3;
  v117 = (void **)a4;
  v12 = a6;
  v139 = a7;
  *(_OWORD *)Src = 0;
  v125 = 0;
  v130 = 0;
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
  v14 = (_DWORD *)CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
    v14 = (_DWORD *)(-(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process);
  v123 = (unsigned __int64)PtiCurrent();
  v15 = v123 & -(__int64)(a5 != 0);
  v114 = v15;
  if ( v15 && (_InterlockedCompareExchange((volatile signed __int32 *)(v15 + 520), 0, 0) & 1) != 0 )
    return 0;
  HighLimit = 0;
  LowLimit = 0;
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( (unsigned __int64)&HighLimit - LowLimit < 0x2000 )
    return 0;
  if ( a1 )
  {
    v17 = *(_DWORD **)(*((_QWORD *)a1 + 2) + 456LL);
    if ( v17 == v14 )
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
            v16 = *(_QWORD *)(W32GetUserSessionState() + 19704);
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
          v19 = 0;
          goto LABEL_31;
        }
        goto LABEL_24;
      }
LABEL_30:
      v19 = 1;
LABEL_31:
      if ( v19 )
        goto LABEL_32;
      goto LABEL_33;
    }
LABEL_24:
    if ( !(unsigned int)Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline()
      && (!UIPrivilegeIsolation::Enforced(v18) || *(_QWORD *)v17 == *(_QWORD *)(W32GetUserGdiSessionState() + 40)) )
    {
      if ( v17[191] != v14[191] || v17[192] != v14[192] )
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
    v20 = *(_QWORD *)(*((_QWORD *)a1 + 2) + 456LL);
  }
  else
  {
    v20 = 0;
    if ( v12 )
      v20 = *(_QWORD *)(v12 + 456);
  }
  if ( (_DWORD *)v20 == v14 )
    goto LABEL_66;
  if ( a2 == 717 )
    goto LABEL_64;
  v21 = IsMessageAllowedAcrossILByReceiver((struct tagPROCESSINFO *)v20, v119, a2);
  if ( !v21 )
    v21 = IsMessageAlwaysAllowedAcrossIL(a2);
  if ( v21 )
    goto LABEL_66;
  if ( a2 != 274 || ((a3 - 61472) & 0xFFFFFFFFFFFFFEBFuLL) != 0 || a3 == 61792 )
  {
    if ( (unsigned int)Feature_MsgUseCSRSSTrueIL__private_IsEnabledDeviceUsageNoInline() )
    {
      v24 = (const struct tagUIPI_INFO *)(v20 + 864);
    }
    else
    {
      v143 = 0;
      LODWORD(v144) = 0;
      if ( *(_QWORD *)v20 == *(_QWORD *)(W32GetUserGdiSessionState() + 40) )
      {
        v143 = 0x2000;
        LODWORD(v144) = 0;
      }
      else
      {
        v143 = *(_QWORD *)(v20 + 864);
        LODWORD(v144) = *(_DWORD *)(v20 + 872);
      }
      v24 = (const struct tagUIPI_INFO *)&v143;
    }
    v25 = UIPrivilegeIsolation::CheckAccess((UIPrivilegeIsolation *)(v14 + 216), v24, v23);
    v22 = v25;
    if ( v25 )
      goto LABEL_66;
    if ( v119 && a2 == 793 )
    {
      v26 = *((_QWORD *)v119 + 2);
      if ( *(struct tagWND **)(v26 + 1584) == v119 && *(_QWORD *)(v26 + 464) == *((_QWORD *)PtiCurrent() + 58) )
        v22 = 1;
      v9 = BugCheckParameter3[0];
    }
    if ( v22 )
      goto LABEL_66;
    EtwTraceUIPIMsgError(v14, v20, a2, a3, v9);
    UserSetLastError(5);
  }
  else
  {
    v22 = 1;
  }
  if ( v22 )
  {
LABEL_66:
    v27 = v119;
    goto LABEL_67;
  }
LABEL_64:
  v27 = v119;
  if ( !UserCheckForMessageAccessWithWindowCapability(v119, a2) )
    return 0;
LABEL_67:
  v28 = (void **)BugCheckParameter3[0];
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
  v29 = a6;
  if ( !tagPROCESSINFO::SyncAndTestFreeze(*(tagPROCESSINFO **)(a6 + 456)) )
    goto LABEL_87;
  v30 = v120;
  if ( v120 )
  {
    if ( (*(_DWORD *)(v120 + 32) & 0x40) != 0 )
    {
      v31 = v114;
      goto LABEL_81;
    }
    if ( *(_DWORD *)v120 == 2 && *(_DWORD *)(v120 + 36) )
      return 0;
  }
  v31 = v114;
  if ( v114 )
  {
    v32 = **(_QWORD **)(a6 + 456);
    CurrentProcess = PsGetCurrentProcess();
    if ( !PsGetProcessCommonJob(CurrentProcess, v32) )
      return 0;
    v30 = v120;
    v29 = a6;
LABEL_81:
    if ( v31 )
      goto LABEL_87;
  }
  if ( !v30 && (a2 == 537 || !(unsigned int)ProcessSuspendedSendMessage(v29, v27, a2, a3, BugCheckParameter3[0]))
    || !v31 && *(_DWORD *)(v29 + 568) > 0x2710u )
  {
    return 0;
  }
LABEL_87:
  UserSessionState = W32GetUserSessionState();
  v35 = Win32AllocateFromPagedLookasideList(*(_QWORD *)(UserSessionState + 69080));
  v38 = (char *)v35;
  v126 = (char *)v35;
  if ( !v35 )
    return 0;
  v134 = v35;
  LowLimit = 0;
  v39 = 0;
  v128 = 0;
  *(_QWORD *)(v35 + 120) = 0;
  Size = 0;
  v40 = 0;
  v115 = v28;
  v41 = v123;
  *(_DWORD *)(v35 + 128) = *(_DWORD *)(v123 + 1604);
  v42 = v120;
  if ( !v120 || *(_DWORD *)v120 != 33 )
  {
    if ( a2 > 0x14D )
    {
      if ( a2 > 0x1A2 )
      {
        if ( a2 == 536 )
        {
          if ( v28 && (a3 & 0x8000) != 0 && (!(unsigned __int8)MmIsKernelAddress(v28) || !v114) )
          {
            v40 = *((_DWORD *)v28 + 4) + 20;
            if ( *((_DWORD *)v28 + 4) >= 0xFFFFFFEC )
              goto LABEL_144;
          }
          goto LABEL_183;
        }
        if ( a2 != 537 )
        {
          if ( a2 == 544 )
          {
            v40 = (*((_DWORD *)v28 + 15) & 0x7FFFFFFF) + (*((_DWORD *)v28 + 19) & 0x7FFFFFFF);
            v39 = v28;
            goto LABEL_183;
          }
          if ( a2 == 643 )
          {
            if ( a3 == 24 )
              v40 = (*(_DWORD *)v28 << 9) + 4;
            goto LABEL_183;
          }
          if ( a2 == 780 )
            goto LABEL_166;
          if ( a2 == 833 )
          {
            v45 = 104;
          }
          else
          {
            if ( a2 == 834 )
            {
              v40 = 80;
              goto LABEL_184;
            }
            if ( a2 != 836 )
            {
              if ( a2 == 838 )
                v40 = 96;
              goto LABEL_183;
            }
            v45 = 1204;
          }
          v40 = v45;
LABEL_113:
          Size = v45;
          goto LABEL_183;
        }
        if ( !v28 || (a3 & 0x8000) == 0 || (unsigned __int8)MmIsKernelAddress(v28) && v114 )
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
            v43 = a2 == 406;
LABEL_160:
            if ( !v43 )
              goto LABEL_183;
            goto LABEL_141;
          }
          goto LABEL_121;
        }
LABEL_139:
        v46 = *(_DWORD *)(v41 + 1604) == 1;
LABEL_140:
        if ( v46 )
          goto LABEL_183;
        goto LABEL_141;
      }
      if ( a2 != 397 )
      {
        if ( a2 == 344 || a2 == 384 || a2 == 385 )
          goto LABEL_139;
        if ( a2 == 393 )
          goto LABEL_166;
        v47 = a2 == 396;
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
              v40 = *(unsigned __int16 *)v28;
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
                    v43 = a2 == 27;
                    goto LABEL_160;
                  }
                  goto LABEL_122;
                }
LABEL_166:
                *(_OWORD *)Src = *(_OWORD *)v28;
                v125 = (SHIDWORD(Src[0]) >= 0) + 1;
                v130 = v125;
                v28 = Src;
                BugCheckParameter3[0] = (ULONG_PTR)Src;
                v117 = Src;
                if ( !(unsigned __int8)MmIsKernelAddress(_mm_srli_si128(*(__m128i *)Src, 8).m128i_u64[0]) || !v114 )
                  v40 = HIDWORD(Src[0]) & 0x7FFFFFFF;
                goto LABEL_183;
              }
LABEL_122:
              v46 = v28 == 0;
              goto LABEL_140;
            }
LABEL_124:
            UserSetLastError(5);
            FreeSMS(v38, 1);
            return 0;
          }
          if ( a2 != 70 && a2 != 71 )
          {
            if ( a2 == 73 )
            {
              v40 = a3;
            }
            else if ( a2 == 74 )
            {
              LowLimit = (unsigned __int64)v28;
              if ( v28[2] )
              {
                v40 = *((_DWORD *)v28 + 2) + 24;
                if ( v40 < 0x18 )
                {
                  FreeSMS(v35, 1);
                  return 0;
                }
              }
              else
              {
                v40 = 24;
              }
            }
            goto LABEL_183;
          }
          v40 = 40;
          goto LABEL_112;
        }
LABEL_176:
        v40 = *(_DWORD *)v28;
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
              v40 = a3 != 0 ? 96 : 16;
LABEL_112:
              v45 = v40;
              goto LABEL_113;
            case 0xC2u:
              goto LABEL_122;
            case 0xC4u:
              goto LABEL_166;
          }
          if ( a2 != 203 )
            goto LABEL_183;
LABEL_121:
          v40 = 4 * a3;
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
        v47 = a2 == 332;
LABEL_138:
        if ( !v47 )
          goto LABEL_183;
        goto LABEL_139;
      }
    }
LABEL_141:
    *(_OWORD *)Src = *(_OWORD *)v28;
    if ( !(unsigned __int8)MmIsKernelAddress(_mm_srli_si128(*(__m128i *)Src, 8).m128i_u64[0]) || !v114 )
    {
      v40 = LODWORD(Src[0]) + 18;
      if ( (unsigned int)(LODWORD(Src[0]) + 18) < LODWORD(Src[0]) )
      {
LABEL_144:
        FreeSMS(v38, 1);
        return 8;
      }
    }
LABEL_183:
    if ( !v40 )
      goto LABEL_216;
LABEL_184:
    v37 = (_OWORD *)Win32AllocPoolWithQuotaZInit(v40, 1668510549);
    *((_QWORD *)v38 + 15) = v37;
    if ( !v37 )
      goto LABEL_216;
    v128 = v28;
    v135 = v28;
    if ( a2 > 0x14C )
    {
      if ( a2 > 0x18D )
      {
        switch ( a2 )
        {
          case 0x18Fu:
            goto LABEL_214;
          case 0x191u:
            Size = v40;
            break;
          case 0x196u:
          case 0x1A2u:
            goto LABEL_214;
          case 0x220u:
            v36 = (void **)v39[10];
            if ( v36 )
            {
              v56 = *((unsigned int *)v39 + 19);
              LODWORD(v56) = v56 & 0x7FFFFFFF;
              memmove(v37, v36, v56);
              *v39 = (void *)*((_QWORD *)v38 + 15);
            }
            if ( *((_DWORD *)v39 + 14) )
            {
              v57 = *((unsigned int *)v39 + 19);
              LODWORD(v57) = v57 & 0x7FFFFFFF;
              v58 = (void *)(*((_QWORD *)v38 + 15) + v57);
              v59 = *((unsigned int *)v39 + 15);
              LODWORD(v59) = v59 & 0x7FFFFFFF;
              memmove(v58, v39[8], v59);
              v39[1] = v58;
            }
            goto LABEL_216;
          case 0x30Cu:
            goto LABEL_225;
        }
LABEL_231:
        v36 = v115;
        goto LABEL_232;
      }
      if ( a2 == 397 || a2 == 333 || a2 == 344 || a2 == 384 || a2 == 385 )
        goto LABEL_214;
      if ( a2 == 393 )
        goto LABEL_225;
      v54 = a2 == 396;
    }
    else
    {
      if ( a2 == 332 )
        goto LABEL_214;
      if ( a2 <= 0x83 )
      {
        if ( a2 == 131 )
        {
          v36 = v115;
          if ( a3 )
          {
            *v37 = *(_OWORD *)v115;
            v37[1] = *((_OWORD *)v115 + 1);
            v37[2] = *((_OWORD *)v115 + 2);
            *((_QWORD *)v37 + 6) = v115[6];
            v52 = *((_QWORD *)v38 + 15) + 56LL;
            *((_QWORD *)v37 + 6) = v52;
            v53 = v115[6];
            *(_OWORD *)v52 = *v53;
            *(_OWORD *)(v52 + 16) = v53[1];
            *(_QWORD *)(v52 + 32) = *((_QWORD *)v53 + 4);
LABEL_233:
            v28 = (void **)*((_QWORD *)v38 + 15);
            BugCheckParameter3[0] = (ULONG_PTR)v28;
            v117 = v28;
LABEL_216:
            if ( v40 && !*((_QWORD *)v38 + 15) )
            {
              FreeSMS(v38, 1);
              return 0;
            }
            if ( a9
              && v119
              && (unsigned int)IsWindowDesktopComposed(v119, v36, v42, v37)
              && !(unsigned int)IsPointerInputMessage(a2) )
            {
              TransformMessageBetweenCoordinateSpaces(
                v60,
                1,
                (unsigned int)&v131,
                (unsigned int)&v117,
                (__int64)v119,
                0);
              v28 = v117;
              BugCheckParameter3[0] = (ULONG_PTR)v117;
            }
            goto LABEL_239;
          }
LABEL_232:
          memmove(v37, v36, v40);
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
              v28 = (void **)v37;
              BugCheckParameter3[0] = (ULONG_PTR)v37;
              v117 = (void **)v37;
              v48 = LowLimit;
              *v37 = *(_OWORD *)LowLimit;
              *((_QWORD *)v37 + 2) = *(_QWORD *)(v48 + 16);
              if ( !*(_QWORD *)(v48 + 16) )
                goto LABEL_216;
              v49 = (char *)v37 + 24;
              *((_QWORD *)v37 + 2) = (char *)v37 + 24;
              v50 = *(unsigned int *)(v48 + 8);
              v51 = *(const void **)(v48 + 16);
              goto LABEL_215;
            }
            goto LABEL_231;
          }
LABEL_214:
          v28 = (void **)v37;
          BugCheckParameter3[0] = (ULONG_PTR)v37;
          v117 = (void **)v37;
          v55 = *((_DWORD *)v37 + 1) & 0x7FFFFFFF | HIDWORD(Src[0]) & 0x80000000;
          *((_DWORD *)v37 + 1) = v55;
          *(_DWORD *)v37 = Src[0];
          v49 = v37 + 1;
          *((_QWORD *)v37 + 1) = v37 + 1;
          v50 = v55 ^ (v55 ^ (v40 - 16)) & 0x7FFFFFFF;
          *((_DWORD *)v37 + 1) = v50;
          LODWORD(v50) = v50 & 0x7FFFFFFF;
          v51 = Src[1];
LABEL_215:
          memmove(v49, v51, v50);
          goto LABEL_216;
        }
        goto LABEL_225;
      }
      switch ( a2 )
      {
        case 0xC2u:
          goto LABEL_214;
        case 0xC4u:
          *(_WORD *)v37 = *(_WORD *)Src[1];
          goto LABEL_225;
        case 0x143u:
        case 0x145u:
          goto LABEL_214;
        case 0x148u:
LABEL_225:
          Size = v40;
          v128 = Src[1];
          v135 = (void **)Src[1];
          Src[1] = *((void **)v38 + 15);
          goto LABEL_216;
      }
      v54 = a2 == 330;
    }
    if ( v54 )
      goto LABEL_214;
    goto LABEL_231;
  }
LABEL_239:
  *((_QWORD *)v38 + 14) = 0;
  v61 = v38 + 16;
  LowLimit = (unsigned __int64)(v38 + 16);
  *((_QWORD *)v38 + 2) = 0;
  v143 = (__int64)(v38 + 112);
  v144 = v119;
  HMAssignmentLock(&v143, 0);
  *((_DWORD *)v38 + 26) = a2;
  *((_QWORD *)v38 + 11) = a3;
  *((_QWORD *)v38 + 12) = v28;
  v63 = (int *)(v38 + 84);
  v138 = v38 + 84;
  *((_DWORD *)v38 + 21) = 0;
  *((_QWORD *)v38 + 9) = 0;
  if ( a2 == 576 || a2 == 281 )
  {
    v72 = _HMObjectFromHandle(v28);
    if ( v72 )
    {
      v67 = a6;
      HMChangeOwnerThread(v72, a6);
      goto LABEL_249;
    }
  }
  else if ( a2 == 255 )
  {
    LOBYTE(v62) = 18;
    v64 = (struct tagHIDDATA *)HMValidateHandleNoSecure(v28, v62);
    if ( v64 )
    {
      if ( *(struct tagHIDDATA **)(v123 + 1136) == v64 && v119 )
      {
        v65 = CopyHidData(v64);
        v66 = (ULONG_PTR *)v65;
        if ( v65 )
        {
          *(_DWORD *)(v65 + 48) &= ~1u;
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(a6 + 1152), (PSLIST_ENTRY)(v65 + 32));
          BugCheckParameter3[0] = *v66;
          v117 = (void **)BugCheckParameter3[0];
          *((_QWORD *)v38 + 12) = BugCheckParameter3[0];
        }
        v61 = (_QWORD *)LowLimit;
      }
    }
  }
  v67 = a6;
LABEL_249:
  v68 = W32GetUserSessionState() + 69048;
  v69 = *(_QWORD *)v68;
  if ( *(_QWORD *)(*(_QWORD *)v68 + 8LL) != v68 )
    goto LABEL_355;
  *(_QWORD *)v38 = v69;
  *((_QWORD *)v38 + 1) = v68;
  *(_QWORD *)(v69 + 8) = v38;
  *(_QWORD *)v68 = v38;
  *((_DWORD *)v38 + 20) = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  *((_QWORD *)v38 + 5) = v67;
  *((_QWORD *)v38 + 4) = v114;
  *((_DWORD *)v38 + 33) = W32GetCurrentThreadDpiAwarenessContext();
  *((_QWORD *)v38 + 8) = 0;
  v70 = v120;
  if ( v120 && (*(_DWORD *)v120 & 1) != 0 )
  {
    *v63 |= (*(_DWORD *)v120 & 0x100) != 0 ? 1024 : 2048;
    v71 = *v63;
    *((_QWORD *)v38 + 6) = *(_QWORD *)(v70 + 8);
    *((_QWORD *)v38 + 7) = *(_QWORD *)(v70 + 16);
    if ( (*(_DWORD *)v70 & 0x20) != 0 )
    {
      *v63 = v71 | 0x200;
      *((_QWORD *)v38 + 9) = *(_QWORD *)(v70 + 24);
    }
    else
    {
      *v63 = v71 | 0x100;
      *((_QWORD *)v38 + 8) = v123;
    }
  }
  if ( a9 )
    *v63 |= 0x10000u;
  v73 = *(_QWORD **)(a6 + 560);
  if ( *v73 != a6 + 552 )
    goto LABEL_355;
  *v61 = a6 + 552;
  v143 = (__int64)(v61 + 1);
  v61[1] = v73;
  *v73 = v61;
  *(_QWORD *)(a6 + 560) = v61;
  v141 = (_DWORD *)(a6 + 568);
  ++*(_DWORD *)(a6 + 568);
  if ( v114 )
  {
    v116 = *(void **)(v114 + 536);
    v133 = v116;
    *(_QWORD *)(v114 + 536) = v38;
  }
  else
  {
    v116 = 0;
    v133 = 0;
    *v63 |= 8u;
  }
  if ( (*v63 & 0x200) == 0
    && ((unsigned int)IsPointerInputMessageWithState(a2) || (unsigned int)IsPointerParentNotify(a2, a3)) )
  {
    v74 = W32GetUserSessionState();
    CTouchProcessor::ReferenceMsgDataExternal(*(_QWORD *)(v74 + 3208), BugCheckParameter3[0], 6, v38);
  }
  EtwTraceBeginSendMessage(v38, v114, v120);
  if ( !v114 )
  {
    SetWakeBit(a6, 64);
    EtwTraceEndSendMessage(v38);
    return 1;
  }
  v140 = v38 + 72;
  v75 = 0;
  LODWORD(v123) = 0;
  SetWakeBit(a6, 64);
  if ( v120 )
  {
    v122 = *(_DWORD *)(v120 + 36);
    v76 = ((*(_DWORD *)(v120 + 32) & 1) << 15) + 512;
  }
  else
  {
    v122 = 0;
    v76 = 512;
  }
  v124 = v76;
  CKernelStackSwapAuto::CKernelStackSwapAuto((CKernelStackSwapAuto *)v142);
  if ( *(_QWORD *)(v114 + 464) == *(_QWORD *)(a6 + 464)
    && (_InterlockedCompareExchange((volatile signed __int32 *)(v114 + 520), 0, 0) & 0x10000) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(v114 + 520), 0x10000u);
    LODWORD(v123) = 1;
  }
  v77 = 0;
  if ( a2 == 788 )
  {
    if ( BugCheckParameter3[0] )
    {
      v77 = *(_QWORD *)BugCheckParameter3[0];
      if ( (*(_DWORD *)(BugCheckParameter3[0] + 24) & 1) != 0 )
      {
        *v63 |= 0x60000u;
        *((_QWORD *)v38 + 15) = *(_QWORD *)v77;
      }
    }
  }
  if ( (*v63 & 1) == 0 )
  {
    while ( 1 )
    {
      if ( v75 )
      {
LABEL_306:
        v38 = v126;
        goto LABEL_307;
      }
      Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3);
      v79 = 0;
      _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(v80 + 480) + 4LL), 0xFFFFFDFF);
      if ( v77
        && (*(_DWORD *)(v77 + 48) == 13 || *(_DWORD *)(v77 + 48) == 14)
        && *(_DWORD *)(v78 + 664) <= 0x501u
        && *(_DWORD *)(v78 + 680) )
      {
        v81 = PtiCurrent();
        Win32HM_LockIntoThread<1>(v81, v77, BugCheckParameter3);
        v79 = 1;
      }
      v82 = xxxSleepThread(v76, v122, 0, 0);
      v83 = v82;
      v75 = v82 == 0;
      if ( v79 )
        break;
LABEL_295:
      if ( !v83 && v120 )
      {
        v88 = *(_DWORD *)(v120 + 32);
        v89 = *v63;
        if ( ((v88 & 0x10) != 0 || (v89 & 0x20) != 0) && (v89 & 0x10) != 0 )
        {
          v122 = 0;
          v75 = 0;
        }
        if ( (v88 & 8) != 0 )
          v75 &= -IsThreadHung((const struct tagTHREADINFO *)a6);
        if ( !v75 )
          EtwTraceConvertTimeOutToBlocking();
      }
      Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)BugCheckParameter3);
      v76 = v124;
      if ( (*v63 & 1) != 0 )
        goto LABEL_306;
    }
    v84 = *(_DWORD *)(v77 + 64);
    if ( v82 )
    {
      v86 = v84 & 0xFFFFBFFF;
    }
    else
    {
      v85 = v84 | 0x4000;
      *(_DWORD *)(v77 + 64) = v85;
      if ( (v85 & 0x10) != 0 )
        goto LABEL_294;
      if ( ++*(_BYTE *)(v77 + 97) <= 0xAu )
        goto LABEL_294;
      v86 = v85 | 0x10;
    }
    *(_DWORD *)(v77 + 64) = v86;
LABEL_294:
    v87 = PtiCurrent();
    Win32HM_UnlockFromThread<1>((ULONG_PTR)v87, (ULONG_PTR)BugCheckParameter3);
    BugCheckParameter3[1] = 0;
    BugCheckParameter3[0] = -1;
    goto LABEL_295;
  }
LABEL_307:
  CKernelStackSwapAuto::~CKernelStackSwapAuto((CKernelStackSwapAuto *)v142);
  if ( (_DWORD)v123 )
  {
    _InterlockedAnd((volatile signed __int32 *)(v114 + 520), 0xFFFEFFFF);
    MergeDeferredMessagesOfThreadOnQueue(v114);
  }
  SetWakeBit(v114, 512);
  if ( v75 )
    goto LABEL_335;
  if ( !Size )
  {
    if ( a2 == 831 )
    {
      if ( a9 )
      {
        v104 = v119;
        if ( v119 )
        {
          if ( (unsigned int)IsWindowDesktopComposed(v119, v90, v91, v92) )
            TransformMessageBetweenCoordinateSpaces(831, 1, (unsigned int)&v131, (unsigned int)&v117, 0, (__int64)v104);
        }
      }
    }
    goto LABEL_335;
  }
  v93 = v128;
  v126 = (char *)v128;
  if ( a2 == 131 )
  {
    if ( a9 )
    {
      v99 = v119;
      if ( v119 )
      {
        if ( (unsigned int)IsWindowDesktopComposed(v119, v90, v91, v128) )
        {
          TransformMessageBetweenCoordinateSpaces(131, 1, (unsigned int)&v131, (unsigned int)&v126, 0, (__int64)v99);
          v93 = v126;
        }
        else
        {
          v93 = v128;
        }
      }
    }
    v100 = (__int128 *)*((_QWORD *)v38 + 15);
    v101 = *v100;
    if ( a3 )
    {
      v102 = v93[6];
      *(_OWORD *)v93 = v101;
      *((_OWORD *)v93 + 1) = v100[1];
      *((_OWORD *)v93 + 2) = v100[2];
      v93[6] = v102;
      v103 = *((_QWORD *)v100 + 6);
      if ( v103 )
      {
        *(_OWORD *)v102 = *(_OWORD *)v103;
        *(_OWORD *)(v102 + 16) = *(_OWORD *)(v103 + 16);
        *(_QWORD *)(v102 + 32) = *(_QWORD *)(v103 + 32);
      }
    }
    else
    {
      *(_OWORD *)v93 = v101;
    }
LABEL_335:
    v98 = v38 + 72;
    v97 = v116;
    goto LABEL_336;
  }
  v94 = (__int16 *)*((_QWORD *)v38 + 15);
  if ( v125 )
  {
    if ( v125 == 1 )
    {
      strncpycch(v128, v94, Size);
    }
    else
    {
      v95 = Size >> 1;
      v129 = Size >> 1;
      v136 = v94;
      v137 = v128;
      while ( v95 )
      {
        v96 = *v94++;
        v136 = v94;
        *(_WORD *)v93 = v96;
        v93 = (_QWORD *)((char *)v93 + 2);
        v137 = v93;
        if ( !v96 )
          break;
        v129 = --v95;
      }
    }
  }
  else
  {
    memmove(v128, v94, Size);
  }
  v97 = v116;
  v98 = v38 + 72;
LABEL_336:
  EtwTraceEndSendMessage(v38);
  *(_QWORD *)(v114 + 536) = v97;
  v105 = v120;
  if ( v120 )
  {
    **(_QWORD **)(v120 + 40) = *v98;
    if ( (*(_DWORD *)(v105 + 32) & 0x20) != 0 && (*v63 & 0x8000) != 0 )
    {
      v106 = 0;
      UserSetLastError(1400);
      v105 = v120;
    }
    else
    {
      v106 = v75 == 0;
    }
  }
  else
  {
    v106 = *v98;
  }
  if ( (v105 || v75) && (*v63 & 1) == 0 )
  {
    v107 = *v63 | 1;
    *v63 = v107;
    if ( (v107 & 0x4000) != 0 )
    {
      *v63 = v107 | 8;
      goto LABEL_350;
    }
    --*v141;
    v108 = (_QWORD *)LowLimit;
    v109 = *(_QWORD *)LowLimit;
    if ( *(_QWORD *)(*(_QWORD *)LowLimit + 8LL) == LowLimit )
    {
      v110 = *(_QWORD **)v143;
      if ( **(_QWORD **)v143 == LowLimit )
      {
        *v110 = v109;
        *(_QWORD *)(v109 + 8) = v110;
        *v108 = 0;
        *v63 |= 0x10u;
        goto LABEL_350;
      }
    }
LABEL_355:
    __fastfail(3u);
  }
LABEL_350:
  *v63 &= ~0x20000u;
  v111 = *v63;
  if ( (*v63 & 0x4010) != 0x10 )
  {
    v111 |= 8u;
    *v63 = v111;
  }
  if ( (v111 & 0x8008) != 8 )
    UnlinkSendListSms(v38);
  return v106;
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
