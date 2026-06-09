# xxxUserProcessCallout

- ea: `0x14014da60`
- end: `0x14014e0e5`
- name: `xxxUserProcessCallout`
- size: `1669`
- prototype: `__int64 __fastcall(struct _W32PROCESS *)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x140022c58`
- `0x140029710`
- `0x14002ad88`
- `0x14002adb4`
- `0x140037420`
- `0x14004c020`
- `0x14004f4c0`
- `0x1400701d4`
- `0x1400a5ba0`
- `0x1400a612c`
- `0x1400e51ec`
- `0x1400e546c`
- `0x14014da60`
- `0x14014e0ec`
- `0x14014e31c`
- `0x14014ed3c`
- `0x1401530e8`
- `0x1401aab9c`
- `0x1401b953c`
- `0x140216140`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014dca5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014de6a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014dca5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014de6a`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14014dab8`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14014dab8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14014ddc6`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14014ddc6`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14014ddfe`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14014ddfe`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14014dc3b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14014dd4e`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14014dc3b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14014dd4e`
- `ntoskrnl!PsGetProcessJob` at `0x14014dd7c`
- `ntoskrnl!PsGetProcessJob` at `0x14014df45`
- `ntoskrnl!PsGetProcessJob` at `0x14014dd7c`
- `ntoskrnl!PsGetProcessJob` at `0x14014df45`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x14014dd93`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x14014dd93`
- `ntoskrnl!PsGetJobLock` at `0x14014ddb7`
- `ntoskrnl!PsGetJobLock` at `0x14014ddef`
- `ntoskrnl!PsGetJobLock` at `0x14014ddb7`
- `ntoskrnl!PsGetJobLock` at `0x14014ddef`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014df56`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014df7b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014df56`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014df7b`
- `WIN32K!W32GetSessionState` at `0x14014e005`
- `WIN32K!W32GetSessionState` at `0x14014e084`
- `WIN32K!W32GetSessionState` at `0x14014e005`
- `WIN32K!W32GetSessionState` at `0x14014e084`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014def1`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014df04`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014df1c`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014def1`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014df04`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014df1c`
- `WIN32K!W32GetUserSessionState` at `0x14014db12`
- `WIN32K!W32GetUserSessionState` at `0x14014dbe7`
- `WIN32K!W32GetUserSessionState` at `0x14014dc4e`
- `WIN32K!W32GetUserSessionState` at `0x14014de0f`
- `WIN32K!W32GetUserSessionState` at `0x14014df31`
- `WIN32K!W32GetUserSessionState` at `0x14014dfaf`
- `WIN32K!W32GetUserSessionState` at `0x14014dfc5`
- `WIN32K!W32GetUserSessionState` at `0x14014dfea`
- `WIN32K!W32GetUserSessionState` at `0x14014e01a`
- `WIN32K!W32GetUserSessionState` at `0x14014e031`
- `WIN32K!W32GetUserSessionState` at `0x14014e068`
- `WIN32K!W32GetUserSessionState` at `0x14014db12`
- `WIN32K!W32GetUserSessionState` at `0x14014dbe7`
- `WIN32K!W32GetUserSessionState` at `0x14014dc4e`
- `WIN32K!W32GetUserSessionState` at `0x14014de0f`
- `WIN32K!W32GetUserSessionState` at `0x14014df31`
- `WIN32K!W32GetUserSessionState` at `0x14014dfaf`
- `WIN32K!W32GetUserSessionState` at `0x14014dfc5`
- `WIN32K!W32GetUserSessionState` at `0x14014dfea`
- `WIN32K!W32GetUserSessionState` at `0x14014e01a`
- `WIN32K!W32GetUserSessionState` at `0x14014e031`
- `WIN32K!W32GetUserSessionState` at `0x14014e068`

## pseudocode

```c
__int64 __fastcall xxxUserProcessCallout(struct _W32PROCESS *a1, PEPROCESS *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  char v7; // di
  __int64 v9; // rdx
  __int64 v10; // r8
  PACCESS_TOKEN v11; // r15
  bool v12; // si
  int v13; // ebx
  __int64 v14; // rax
  int v15; // r8d
  int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // esi
  __int64 v20; // r8
  bool v21; // r14
  int v22; // ebx
  __int64 v23; // rax
  int v24; // r8d
  int v25; // edx
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // r14
  int inited; // r14d
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 ProcessJob; // rax
  __int64 v35; // rsi
  struct _ERESOURCE *JobLock; // rax
  struct _ERESOURCE *v37; // rax
  __int64 UserSessionState; // rsi
  char v39; // di
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v44; // rax
  _QWORD *v45; // r14
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 v52; // rcx
  int (*v53)(void); // rax
  __int64 v54; // rdx
  __int64 v55; // rcx
  void (__fastcall *v56)(struct _W32PROCESS *); // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r14
  __int64 v61; // rbx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // rcx
  unsigned __int64 i; // rsi
  __int64 v68; // r8
  __int64 v69; // rax
  __int64 SessionState; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  __int64 v74; // rcx
  _DWORD *v75; // rbx
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  _DWORD *v81; // rsi
  __int64 v82; // rax
  unsigned int v83; // [rsp+50h] [rbp-9h] BYREF
  __int64 v84; // [rsp+58h] [rbp-1h] BYREF
  __int128 v85; // [rsp+60h] [rbp+7h] BYREF
  __int128 v86; // [rsp+70h] [rbp+17h]
  __int64 v87; // [rsp+80h] [rbp+27h]
  PVOID v88; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (unsigned int)Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( a2 )
      return xxxUserProcessInitCallout(a1, a2);
    UserProcessDestroyCallout(a1);
    return 0;
  }
  if ( !a2 )
  {
    UserSessionState = W32GetUserSessionState(v5, v4, v6);
    v39 = 1;
    v40 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            UserSessionState,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(UserSessionState + 16) = v40;
    v42 = v40;
    if ( v40 )
    {
      v41 = 0;
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v40 + 520), 0, 0) & 0x1000000) != 0
        && *(char *)(v40 + 1360) >= 0 )
      {
        CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
        if ( CurrentProcessWin32Process )
        {
          if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
          {
            while ( 1 )
            {
              v45 = *(_QWORD **)(UserSessionState + 19544);
              if ( !v45 )
                break;
              *(_QWORD *)(UserSessionState + 19544) = v45[2];
              v44 = *v45;
              v45[2] = 0;
              if ( !*(_DWORD *)(v44 + 8) )
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
              HMUnlockObject(*v45);
            }
            DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
            DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
          }
        }
      }
    }
    if ( !*(_QWORD *)(W32GetUserGdiSessionState(v41, v42) + 40)
      || (v47 = *(_QWORD *)(W32GetUserGdiSessionState(v47, v46) + 40), *(_QWORD *)a1 != v47) )
    {
      v39 = 0;
    }
    v49 = *(_QWORD *)(W32GetUserGdiSessionState(v47, v46) + 40);
    if ( *(_QWORD *)a1 == v49 )
      W32GetUserSessionState(v49, v48, v50);
    if ( *(_QWORD *)a1 )
    {
      if ( ((__int64 (*)(void))PsGetProcessJob)() )
      {
        v53 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v52, v51) + 48) + 608LL);
        if ( v53 )
        {
          if ( v53() >= 0 )
          {
            v56 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v55, v54) + 48)
                                                              + 616LL);
            if ( v56 )
              v56(a1);
          }
        }
      }
    }
    if ( (unsigned int)DestroyProcessInfo(a1) )
    {
      v60 = W32GetUserSessionState(v58, v57, v59);
      v61 = *(_QWORD *)(v60 + 19720);
      for ( i = v61 + 32LL * *(unsigned int *)(W32GetUserSessionState(v63, v62, v64) + 19648);
            i > *(_QWORD *)(v60 + 19720) && !*(_BYTE *)(i + 24);
            i -= 32LL )
      {
        v69 = W32GetUserSessionState(v66, v65, v68);
        --*(_DWORD *)(v69 + 19648);
      }
      SessionState = W32GetSessionState(v66);
      GrepLockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88));
      v74 = *(_QWORD *)(W32GetUserSessionState(v72, v71, v73) + 56744);
      v75 = *(_DWORD **)(v74 + 24);
      v78 = *(_QWORD *)(W32GetUserSessionState(v74, v76, v77) + 56744) + 24LL;
      if ( v75 != (_DWORD *)v78 )
      {
        do
        {
          v81 = *(_DWORD **)v75;
          if ( (v75[12] & 0x400000) != 0 )
            DestroyCacheDC(v75);
          v75 = v81;
          v79 = *(_QWORD *)(W32GetUserSessionState(v79, v78, v80) + 56744) + 24LL;
        }
        while ( v81 != (_DWORD *)v79 );
      }
      v82 = W32GetSessionState(v79);
      GrepUnlockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(v82 + 88));
      ApiSetEditionShowSystemCursor();
      if ( v39 )
        CloseWin32InputRelatedObHandles();
    }
    UserSessionSwitchLeaveCritWithNonPaged(v58);
    return 0;
  }
  v7 = 1;
  if ( *((_BYTE *)a1 + 1200) == 1 )
    return 1073741851;
  v11 = PsReferencePrimaryToken(a2[2]);
  if ( v11 )
  {
    v83 = 0;
    LODWORD(v88) = 0;
    v84 = 0;
    v19 = UserProcessImmersiveType(
            (struct _WIN32_PROCESS_CALLOUT_PARAMETERS *)a2,
            v11,
            (enum _PROCESS_IMMERSIVE_TYPE *)&v83,
            &v88,
            (struct _PS_PKG_CLAIM *)&v84);
    if ( v19 >= 0 )
    {
      v26 = W32GetUserSessionState(v18, v17, v20);
      v27 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
              v26,
              1,
              0,
              _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
      *(_QWORD *)(v26 + 16) = v27;
      if ( v27 )
      {
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v27 + 520), 0, 0) & 0x1000000) != 0
          && *(char *)(v27 + 1360) >= 0 )
        {
          v28 = PsGetCurrentProcessWin32Process();
          if ( v28 )
          {
            if ( *(_QWORD *)v28 && *(_BYTE *)(v28 + 1200) == 1 )
            {
              while ( 1 )
              {
                v30 = *(_QWORD **)(v26 + 19544);
                if ( !v30 )
                  break;
                *(_QWORD *)(v26 + 19544) = v30[2];
                v29 = *v30;
                v30[2] = 0;
                if ( !*(_DWORD *)(v29 + 8) )
                  MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                HMUnlockObject(*v30);
              }
              DestroyDeferredUnlockObjectAssignmentList(v26 + 19576);
              DestroyDeferredUnlockObjectAssignmentList(v26 + 19560);
            }
          }
        }
      }
      inited = xxxInitProcessInfo(a1, v11, v83, (unsigned int)v88, (__int64)&v84);
      PsDereferencePrimaryToken(v11);
      if ( inited >= 0 )
      {
        UserSessionSwitchLeaveCritWithNonPaged(v32);
        ProcessJob = PsGetProcessJob(*(_QWORD *)a1);
        v35 = ProcessJob;
        if ( ProcessJob && (unsigned int)PsGetJobUIRestrictionsClass(ProcessJob) )
        {
          v87 = 0;
          v85 = 0;
          v86 = 0;
          JobLock = (struct _ERESOURCE *)PsGetJobLock(v35);
          ExEnterCriticalRegionAndAcquireResourceExclusive(JobLock);
          v87 = *(_QWORD *)a1;
          *(_QWORD *)&v86 = v35;
          DWORD2(v86) = 1;
          inited = UserJobCallout(&v85);
          v37 = (struct _ERESOURCE *)PsGetJobLock(v35);
          ExReleaseResourceAndLeaveCriticalRegion(v37);
        }
      }
      else
      {
        DestroyProcessInfo(a1);
        UserSessionSwitchLeaveCritWithNonPaged(v33);
      }
      return (unsigned int)inited;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (v18 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v18 & 0x80u) == 0LL)
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        v7 = 0;
      }
      v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = *((_DWORD *)a1 + 14);
        v23 = W32GetUserSessionState(v18, WPP_GLOBAL_Control, v20);
        LOBYTE(v24) = v21;
        LOBYTE(v25) = v7;
        WPP_RECORDER_AND_TRACE_SF_dD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v25,
          v24,
          *(_QWORD *)(v23 + 69136),
          3,
          8,
          35,
          (__int64)WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids,
          v19,
          v22);
      }
      PsDereferencePrimaryToken(v11);
      return (unsigned int)v19;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v7 = 0;
    }
    v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = *((_DWORD *)a1 + 14);
      v14 = W32GetUserSessionState(WPP_GLOBAL_Control, v9, v10);
      LOBYTE(v15) = v12;
      LOBYTE(v16) = v7;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v16,
        v15,
        *(_QWORD *)(v14 + 69136),
        3,
        8,
        34,
        (__int64)WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids,
        v13);
    }
    return 3221225596LL;
  }
}

```

## disassembly

```asm
0x14014da60  mov     [rsp-8+arg_0], rbx
0x14014da65  mov     [rsp-8+arg_8], rsi
0x14014da6a  push    rbp
0x14014da6b  push    rdi
0x14014da6c  push    r12
0x14014da6e  push    r14
0x14014da70  push    r15
0x14014da72  lea     rbp, [rsp-37h]
0x14014da77  sub     rsp, 90h
0x14014da7e  mov     rsi, rdx
0x14014da81  mov     rbx, rcx
0x14014da84  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x14014da89  test    eax, eax
0x14014da8b  jnz     loc_14014E0AF
0x14014da91  test    rsi, rsi
0x14014da94  jz      loc_14014DE0F
0x14014da9a  mov     al, [rbx+4B0h]
0x14014daa0  mov     edi, 1
0x14014daa5  cmp     al, dil
0x14014daa8  jnz     short loc_14014DAB4
0x14014daaa  mov     eax, 4000001Bh
0x14014daaf  jmp     loc_14014E0C8
0x14014dab4  mov     rcx, [rsi+10h]; Process
0x14014dab8  call    cs:__imp_PsReferencePrimaryToken
0x14014dabf  nop     dword ptr [rax+rax+00h]
0x14014dac4  mov     r15, rax
0x14014dac7  test    rax, rax
0x14014daca  jnz     loc_14014DB69
0x14014dad0  mov     rcx, cs:WPP_GLOBAL_Control
0x14014dad7  lea     rax, WPP_GLOBAL_Control
0x14014dade  cmp     rcx, rax
0x14014dae1  jz      short loc_14014DAF0
0x14014dae3  mov     eax, [rcx+2Ch]
0x14014dae6  test    al, al
0x14014dae8  jns     short loc_14014DAF0
0x14014daea  cmp     byte ptr [rcx+29h], 3
0x14014daee  jnb     short loc_14014DAF3
0x14014daf0  xor     dil, dil
0x14014daf3  lea     rax, WPP_RECORDER_INITIALIZED
0x14014dafa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14014db01  setnz   sil
0x14014db05  test    dil, dil
0x14014db08  jnz     short loc_14014DB0F
0x14014db0a  test    sil, sil
0x14014db0d  jz      short loc_14014DB5F
0x14014db0f  mov     ebx, [rbx+38h]
0x14014db12  call    cs:__imp_W32GetUserSessionState
0x14014db19  nop     dword ptr [rax+rax+00h]
0x14014db1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14014db25  mov     r8b, sil
0x14014db28  mov     [rsp+0B0h+var_70], ebx
0x14014db2c  mov     dl, dil
0x14014db2f  mov     r9, [rax+10E10h]
0x14014db36  lea     rax, WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids
0x14014db3d  mov     rcx, [rcx+18h]
0x14014db41  mov     [rsp+0B0h+var_78], rax
0x14014db46  mov     [rsp+0B0h+var_80], 22h ; '"'
0x14014db4d  mov     [rsp+0B0h+var_88], 8
0x14014db55  mov     byte ptr [rsp+0B0h+var_90], 3
0x14014db5a  call    WPP_RECORDER_AND_TRACE_SF_D
0x14014db5f  mov     eax, 0C000007Ch
0x14014db64  jmp     loc_14014E0C8
0x14014db69  lea     rax, [rbp+57h+var_58]
0x14014db6d  mov     [rbp+57h+var_60], 0
0x14014db74  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x14014db78  mov     [rsp+0B0h+var_90], rax; struct _PS_PKG_CLAIM *
0x14014db7d  lea     r8, [rbp+57h+var_60]; enum _PROCESS_IMMERSIVE_TYPE *
0x14014db81  mov     dword ptr [rbp+57h+arg_18], 0
0x14014db88  mov     rdx, r15; void *
0x14014db8b  mov     [rbp+57h+var_58], 0
0x14014db93  mov     rcx, rsi; struct _WIN32_PROCESS_CALLOUT_PARAMETERS *
0x14014db96  call    ?UserProcessImmersiveType@@YAJPEAU_WIN32_PROCESS_CALLOUT_PARAMETERS@@PEAXPEAW4_PROCESS_IMMERSIVE_TYPE@@PEAKPEAU_PS_PKG_CLAIM@@@Z; UserProcessImmersiveType(_WIN32_PROCESS_CALLOUT_PARAMETERS *,void *,_PROCESS_IMMERSIVE_TYPE *,ulong *,_PS_PKG_CLAIM *)
0x14014db9b  mov     esi, eax
0x14014db9d  test    eax, eax
0x14014db9f  jns     loc_14014DC4E
0x14014dba5  mov     rdx, cs:WPP_GLOBAL_Control
0x14014dbac  lea     rax, WPP_GLOBAL_Control
0x14014dbb3  cmp     rdx, rax
0x14014dbb6  jz      short loc_14014DBC5
0x14014dbb8  mov     ecx, [rdx+2Ch]
0x14014dbbb  test    cl, cl
0x14014dbbd  jns     short loc_14014DBC5
0x14014dbbf  cmp     byte ptr [rdx+29h], 3
0x14014dbc3  jnb     short loc_14014DBC8
0x14014dbc5  xor     dil, dil
0x14014dbc8  lea     rax, WPP_RECORDER_INITIALIZED
0x14014dbcf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14014dbd6  setnz   r14b
0x14014dbda  test    dil, dil
0x14014dbdd  jnz     short loc_14014DBE4
0x14014dbdf  test    r14b, r14b
0x14014dbe2  jz      short loc_14014DC38
0x14014dbe4  mov     ebx, [rbx+38h]
0x14014dbe7  call    cs:__imp_W32GetUserSessionState
0x14014dbee  nop     dword ptr [rax+rax+00h]
0x14014dbf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14014dbfa  mov     r8b, r14b
0x14014dbfd  mov     [rsp+0B0h+var_68], ebx
0x14014dc01  mov     dl, dil
0x14014dc04  mov     [rsp+0B0h+var_70], esi
0x14014dc08  mov     r9, [rax+10E10h]
0x14014dc0f  lea     rax, WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids
0x14014dc16  mov     rcx, [rcx+18h]
0x14014dc1a  mov     [rsp+0B0h+var_78], rax
0x14014dc1f  mov     [rsp+0B0h+var_80], 23h ; '#'
0x14014dc26  mov     [rsp+0B0h+var_88], 8
0x14014dc2e  mov     byte ptr [rsp+0B0h+var_90], 3
0x14014dc33  call    WPP_RECORDER_AND_TRACE_SF_dD
0x14014dc38  mov     rcx, r15; PrimaryToken
0x14014dc3b  call    cs:__imp_PsDereferencePrimaryToken
0x14014dc42  nop     dword ptr [rax+rax+00h]
0x14014dc47  mov     eax, esi
0x14014dc49  jmp     loc_14014E0C8
0x14014dc4e  call    cs:__imp_W32GetUserSessionState
0x14014dc55  nop     dword ptr [rax+rax+00h]
0x14014dc5a  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14014dc61  xor     r8d, r8d
0x14014dc64  mov     rcx, rax
0x14014dc67  mov     edx, edi
0x14014dc69  mov     rsi, rax
0x14014dc6c  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x14014dc71  mov     [rsi+10h], rax
0x14014dc75  mov     rdx, rax
0x14014dc78  test    rax, rax
0x14014dc7b  jz      loc_14014DD2C
0x14014dc81  xor     ecx, ecx
0x14014dc83  xor     eax, eax
0x14014dc85  lock cmpxchg [rdx+208h], ecx
0x14014dc8d  bt      eax, 18h
0x14014dc91  jnb     loc_14014DD2C
0x14014dc97  mov     al, [rdx+550h]
0x14014dc9d  test    al, al
0x14014dc9f  js      loc_14014DD2C
0x14014dca5  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14014dcac  nop     dword ptr [rax+rax+00h]
0x14014dcb1  test    rax, rax
0x14014dcb4  jz      short loc_14014DD2C
0x14014dcb6  cmp     qword ptr [rax], 0
0x14014dcba  jz      short loc_14014DD2C
0x14014dcbc  mov     al, [rax+4B0h]
0x14014dcc2  cmp     al, dil
0x14014dcc5  jz      short loc_14014DD08
0x14014dcc7  jmp     short loc_14014DD2C
0x14014dcc9  mov     rax, [r14+10h]
0x14014dccd  mov     [rsi+4C58h], rax
0x14014dcd4  mov     rax, [r14]
0x14014dcd7  mov     qword ptr [r14+10h], 0
0x14014dcdf  cmp     [rax+8], edi
0x14014dce2  jnb     short loc_14014DD00
0x14014dce4  mov     [rbp+57h+arg_10], 20000h
0x14014dceb  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14014dcf2  mov     edx, [rbp+57h+arg_10]
0x14014dcf5  mov     r8d, 1236h
0x14014dcfb  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14014dd00  mov     rcx, [r14]
0x14014dd03  call    HMUnlockObject
0x14014dd08  mov     r14, [rsi+4C58h]
0x14014dd0f  test    r14, r14
0x14014dd12  jnz     short loc_14014DCC9
0x14014dd14  lea     rcx, [rsi+4C78h]
0x14014dd1b  call    DestroyDeferredUnlockObjectAssignmentList
0x14014dd20  lea     rcx, [rsi+4C68h]
0x14014dd27  call    DestroyDeferredUnlockObjectAssignmentList
0x14014dd2c  mov     r9d, dword ptr [rbp+57h+arg_18]
0x14014dd30  lea     rax, [rbp+57h+var_58]
0x14014dd34  mov     r8d, [rbp+57h+var_60]
0x14014dd38  mov     rdx, r15
0x14014dd3b  mov     rcx, rbx; struct _W32PROCESS *
0x14014dd3e  mov     [rsp+0B0h+var_90], rax; __int64
0x14014dd43  call    xxxInitProcessInfo
0x14014dd48  mov     rcx, r15; PrimaryToken
0x14014dd4b  mov     r14d, eax
0x14014dd4e  call    cs:__imp_PsDereferencePrimaryToken
0x14014dd55  nop     dword ptr [rax+rax+00h]
0x14014dd5a  test    r14d, r14d
0x14014dd5d  jns     short loc_14014DD74
0x14014dd5f  mov     rcx, rbx
0x14014dd62  call    DestroyProcessInfo
0x14014dd67  call    UserSessionSwitchLeaveCritWithNonPaged
0x14014dd6c  mov     eax, r14d
0x14014dd6f  jmp     loc_14014E0C8
0x14014dd74  call    UserSessionSwitchLeaveCritWithNonPaged
0x14014dd79  mov     rcx, [rbx]
0x14014dd7c  call    cs:__imp_PsGetProcessJob
0x14014dd83  nop     dword ptr [rax+rax+00h]
0x14014dd88  mov     rsi, rax
0x14014dd8b  test    rax, rax
0x14014dd8e  jz      short loc_14014DD6C
0x14014dd90  mov     rcx, rax
0x14014dd93  call    cs:__imp_PsGetJobUIRestrictionsClass
0x14014dd9a  nop     dword ptr [rax+rax+00h]
0x14014dd9f  test    eax, eax
0x14014dda1  jz      short loc_14014DD6C
0x14014dda3  xorps   xmm0, xmm0
0x14014dda6  xor     eax, eax
0x14014dda8  mov     rcx, rsi
0x14014ddab  mov     [rbp+57h+var_30], rax
0x14014ddaf  movups  [rbp+57h+var_50], xmm0
0x14014ddb3  movups  [rbp+57h+var_40], xmm0
0x14014ddb7  call    cs:__imp_PsGetJobLock
0x14014ddbe  nop     dword ptr [rax+rax+00h]
0x14014ddc3  mov     rcx, rax; Resource
0x14014ddc6  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14014ddcd  nop     dword ptr [rax+rax+00h]
0x14014ddd2  mov     rax, [rbx]
0x14014ddd5  lea     rcx, [rbp+57h+var_50]
0x14014ddd9  mov     [rbp+57h+var_30], rax
0x14014dddd  mov     qword ptr [rbp+57h+var_40], rsi
0x14014dde1  mov     dword ptr [rbp+57h+var_40+8], edi
0x14014dde4  call    UserJobCallout
0x14014dde9  mov     rcx, rsi
0x14014ddec  mov     r14d, eax
0x14014ddef  call    cs:__imp_PsGetJobLock
0x14014ddf6  nop     dword ptr [rax+rax+00h]
0x14014ddfb  mov     rcx, rax; Resource
0x14014ddfe  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14014de05  nop     dword ptr [rax+rax+00h]
0x14014de0a  jmp     loc_14014DD6C
0x14014de0f  call    cs:__imp_W32GetUserSessionState
0x14014de16  nop     dword ptr [rax+rax+00h]
0x14014de1b  xor     r8d, r8d
0x14014de1e  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14014de25  mov     rcx, rax
0x14014de28  mov     rsi, rax
0x14014de2b  lea     edi, [r8+1]
0x14014de2f  mov     edx, edi
0x14014de31  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x14014de36  mov     [rsi+10h], rax
0x14014de3a  mov     rdx, rax
0x14014de3d  test    rax, rax
0x14014de40  jz      loc_14014DEF1
0x14014de46  xor     ecx, ecx
0x14014de48  xor     eax, eax
0x14014de4a  lock cmpxchg [rdx+208h], ecx
0x14014de52  bt      eax, 18h
0x14014de56  jnb     loc_14014DEF1
0x14014de5c  mov     al, [rdx+550h]
0x14014de62  test    al, al
0x14014de64  js      loc_14014DEF1
0x14014de6a  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14014de71  nop     dword ptr [rax+rax+00h]
0x14014de76  test    rax, rax
0x14014de79  jz      short loc_14014DEF1
0x14014de7b  cmp     qword ptr [rax], 0
0x14014de7f  jz      short loc_14014DEF1
0x14014de81  mov     al, [rax+4B0h]
0x14014de87  cmp     al, dil
0x14014de8a  jz      short loc_14014DECD
0x14014de8c  jmp     short loc_14014DEF1
0x14014de8e  mov     rax, [r14+10h]
0x14014de92  mov     [rsi+4C58h], rax
0x14014de99  mov     rax, [r14]
0x14014de9c  mov     qword ptr [r14+10h], 0
0x14014dea4  cmp     [rax+8], edi
0x14014dea7  jnb     short loc_14014DEC5
0x14014dea9  mov     [rbp+57h+arg_10], 20000h
0x14014deb0  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14014deb7  mov     edx, [rbp+57h+arg_10]
0x14014deba  mov     r8d, 1236h
0x14014dec0  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14014dec5  mov     rcx, [r14]
0x14014dec8  call    HMUnlockObject
0x14014decd  mov     r14, [rsi+4C58h]
0x14014ded4  test    r14, r14
0x14014ded7  jnz     short loc_14014DE8E
0x14014ded9  lea     rcx, [rsi+4C78h]
0x14014dee0  call    DestroyDeferredUnlockObjectAssignmentList
0x14014dee5  lea     rcx, [rsi+4C68h]
0x14014deec  call    DestroyDeferredUnlockObjectAssignmentList
0x14014def1  call    cs:__imp_W32GetUserGdiSessionState
0x14014def8  nop     dword ptr [rax+rax+00h]
0x14014defd  cmp     qword ptr [rax+28h], 0
0x14014df02  jz      short loc_14014DF19
0x14014df04  call    cs:__imp_W32GetUserGdiSessionState
0x14014df0b  nop     dword ptr [rax+rax+00h]
0x14014df10  mov     rcx, [rax+28h]
0x14014df14  cmp     [rbx], rcx
0x14014df17  jz      short loc_14014DF1C
0x14014df19  xor     dil, dil
0x14014df1c  call    cs:__imp_W32GetUserGdiSessionState
0x14014df23  nop     dword ptr [rax+rax+00h]
0x14014df28  mov     rcx, [rax+28h]
0x14014df2c  cmp     [rbx], rcx
0x14014df2f  jnz     short loc_14014DF3D
0x14014df31  call    cs:__imp_W32GetUserSessionState
0x14014df38  nop     dword ptr [rax+rax+00h]
0x14014df3d  mov     rcx, [rbx]
0x14014df40  test    rcx, rcx
0x14014df43  jz      short loc_14014DF9F
0x14014df45  call    cs:__imp_PsGetProcessJob
0x14014df4c  nop     dword ptr [rax+rax+00h]
0x14014df51  test    rax, rax
0x14014df54  jz      short loc_14014DF9F
0x14014df56  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14014df5d  nop     dword ptr [rax+rax+00h]
0x14014df62  mov     rcx, [rax+30h]
0x14014df66  mov     rax, [rcx+260h]
0x14014df6d  test    rax, rax
0x14014df70  jz      short loc_14014DF9F
0x14014df72  call    _guard_dispatch_icall
  ... truncated ...
```
