# xxxUserProcessCallout

- ea: `0x14014bc30`
- end: `0x14014c2b5`
- name: `xxxUserProcessCallout`
- size: `1669`
- prototype: `__int64 __fastcall(struct _W32PROCESS *)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x1400173d0`
- `0x14001bdf0`
- `0x14001e528`
- `0x14001e554`
- `0x140033364`
- `0x14006888c`
- `0x140074bf0`
- `0x140078090`
- `0x1400b1d40`
- `0x1400b22cc`
- `0x1400d34cc`
- `0x1400d4158`
- `0x14014bc30`
- `0x14014c2bc`
- `0x14014c4ec`
- `0x14014cd68`
- `0x140150af8`
- `0x1401a9f9c`
- `0x1401b8414`
- `0x140215890`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014be75`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014c03a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014be75`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014c03a`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14014bc88`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14014bc88`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14014bf96`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14014bf96`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14014bfce`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14014bfce`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14014be0b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14014bf1e`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14014be0b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14014bf1e`
- `ntoskrnl!PsGetProcessJob` at `0x14014bf4c`
- `ntoskrnl!PsGetProcessJob` at `0x14014c115`
- `ntoskrnl!PsGetProcessJob` at `0x14014bf4c`
- `ntoskrnl!PsGetProcessJob` at `0x14014c115`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x14014bf63`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x14014bf63`
- `ntoskrnl!PsGetJobLock` at `0x14014bf87`
- `ntoskrnl!PsGetJobLock` at `0x14014bfbf`
- `ntoskrnl!PsGetJobLock` at `0x14014bf87`
- `ntoskrnl!PsGetJobLock` at `0x14014bfbf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014c126`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014c14b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014c126`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014c14b`
- `WIN32K!W32GetSessionState` at `0x14014c1d5`
- `WIN32K!W32GetSessionState` at `0x14014c254`
- `WIN32K!W32GetSessionState` at `0x14014c1d5`
- `WIN32K!W32GetSessionState` at `0x14014c254`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014c0c1`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014c0d4`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014c0ec`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014c0c1`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014c0d4`
- `WIN32K!W32GetUserGdiSessionState` at `0x14014c0ec`
- `WIN32K!W32GetUserSessionState` at `0x14014bce2`
- `WIN32K!W32GetUserSessionState` at `0x14014bdb7`
- `WIN32K!W32GetUserSessionState` at `0x14014be1e`
- `WIN32K!W32GetUserSessionState` at `0x14014bfdf`
- `WIN32K!W32GetUserSessionState` at `0x14014c101`
- `WIN32K!W32GetUserSessionState` at `0x14014c17f`
- `WIN32K!W32GetUserSessionState` at `0x14014c195`
- `WIN32K!W32GetUserSessionState` at `0x14014c1ba`
- `WIN32K!W32GetUserSessionState` at `0x14014c1ea`
- `WIN32K!W32GetUserSessionState` at `0x14014c201`
- `WIN32K!W32GetUserSessionState` at `0x14014c238`
- `WIN32K!W32GetUserSessionState` at `0x14014bce2`
- `WIN32K!W32GetUserSessionState` at `0x14014bdb7`
- `WIN32K!W32GetUserSessionState` at `0x14014be1e`
- `WIN32K!W32GetUserSessionState` at `0x14014bfdf`
- `WIN32K!W32GetUserSessionState` at `0x14014c101`
- `WIN32K!W32GetUserSessionState` at `0x14014c17f`
- `WIN32K!W32GetUserSessionState` at `0x14014c195`
- `WIN32K!W32GetUserSessionState` at `0x14014c1ba`
- `WIN32K!W32GetUserSessionState` at `0x14014c1ea`
- `WIN32K!W32GetUserSessionState` at `0x14014c201`
- `WIN32K!W32GetUserSessionState` at `0x14014c238`

## pseudocode

```c
__int64 __fastcall xxxUserProcessCallout(struct _W32PROCESS *a1, PEPROCESS *a2)
{
  __int64 v4; // rcx
  char v5; // di
  PACCESS_TOKEN v7; // r15
  bool v8; // si
  int v9; // ebx
  __int64 v10; // rax
  int v11; // r8d
  int v12; // edx
  __int64 v13; // rcx
  int v14; // esi
  bool v15; // r14
  int v16; // ebx
  __int64 v17; // rax
  int v18; // r8d
  int v19; // edx
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  _QWORD *v24; // r14
  int inited; // r14d
  __int64 ProcessJob; // rax
  __int64 v27; // rsi
  struct _ERESOURCE *JobLock; // rax
  struct _ERESOURCE *v29; // rax
  __int64 UserSessionState; // rsi
  char v31; // di
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v36; // rax
  _QWORD *v37; // r14
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  int (*v42)(void); // rax
  __int64 v43; // rcx
  void (__fastcall *v44)(struct _W32PROCESS *); // rax
  __int64 v45; // rcx
  __int64 v46; // r14
  __int64 v47; // rbx
  __int64 v48; // rcx
  __int64 v49; // rcx
  unsigned __int64 i; // rsi
  __int64 v51; // rax
  __int64 SessionState; // rax
  __int64 v53; // rcx
  __int64 v54; // rcx
  _DWORD *v55; // rbx
  __int64 v56; // rcx
  _DWORD *v57; // rsi
  __int64 v58; // rax
  unsigned int v59; // [rsp+50h] [rbp-9h] BYREF
  __int64 v60; // [rsp+58h] [rbp-1h] BYREF
  __int128 v61; // [rsp+60h] [rbp+7h] BYREF
  __int128 v62; // [rsp+70h] [rbp+17h]
  __int64 v63; // [rsp+80h] [rbp+27h]
  PVOID v64; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (unsigned int)Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( a2 )
      return xxxUserProcessInitCallout(a1, a2);
    UserProcessDestroyCallout(a1);
    return 0;
  }
  if ( !a2 )
  {
    UserSessionState = W32GetUserSessionState(v4);
    v31 = 1;
    v32 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            UserSessionState,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(UserSessionState + 16) = v32;
    v34 = v32;
    if ( v32 )
    {
      v33 = 0;
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v32 + 520), 0, 0) & 0x1000000) != 0
        && *(char *)(v32 + 1360) >= 0 )
      {
        CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
        if ( CurrentProcessWin32Process )
        {
          if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
          {
            while ( 1 )
            {
              v37 = *(_QWORD **)(UserSessionState + 19544);
              if ( !v37 )
                break;
              *(_QWORD *)(UserSessionState + 19544) = v37[2];
              v36 = *v37;
              v37[2] = 0;
              if ( !*(_DWORD *)(v36 + 8) )
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
              HMUnlockObject(*v37);
            }
            DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
            DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
          }
        }
      }
    }
    if ( !*(_QWORD *)(W32GetUserGdiSessionState(v33, v34) + 40)
      || (v39 = *(_QWORD *)(W32GetUserGdiSessionState(v39, v38) + 40), *(_QWORD *)a1 != v39) )
    {
      v31 = 0;
    }
    v40 = *(_QWORD *)(W32GetUserGdiSessionState(v39, v38) + 40);
    if ( *(_QWORD *)a1 == v40 )
      W32GetUserSessionState(v40);
    if ( *(_QWORD *)a1 )
    {
      if ( ((__int64 (*)(void))PsGetProcessJob)() )
      {
        v42 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v41) + 48) + 608LL);
        if ( v42 )
        {
          if ( v42() >= 0 )
          {
            v44 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v43) + 48)
                                                              + 616LL);
            if ( v44 )
              v44(a1);
          }
        }
      }
    }
    if ( (unsigned int)DestroyProcessInfo(a1) )
    {
      v46 = W32GetUserSessionState(v45);
      v47 = *(_QWORD *)(v46 + 19720);
      for ( i = v47 + 32LL * *(unsigned int *)(W32GetUserSessionState(v48) + 19648);
            i > *(_QWORD *)(v46 + 19720) && !*(_BYTE *)(i + 24);
            i -= 32LL )
      {
        v51 = W32GetUserSessionState(v49);
        --*(_DWORD *)(v51 + 19648);
      }
      SessionState = W32GetSessionState(v49);
      GrepLockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88));
      v54 = *(_QWORD *)(W32GetUserSessionState(v53) + 56744);
      v55 = *(_DWORD **)(v54 + 24);
      if ( v55 != (_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v54) + 56744) + 24LL) )
      {
        do
        {
          v57 = *(_DWORD **)v55;
          if ( (v55[12] & 0x400000) != 0 )
            DestroyCacheDC(v55);
          v55 = v57;
          v56 = *(_QWORD *)(W32GetUserSessionState(v56) + 56744) + 24LL;
        }
        while ( v57 != (_DWORD *)v56 );
      }
      v58 = W32GetSessionState(v56);
      GrepUnlockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(v58 + 88));
      ApiSetEditionShowSystemCursor();
      if ( v31 )
        CloseWin32InputRelatedObHandles();
    }
    UserSessionSwitchLeaveCritWithNonPaged();
    return 0;
  }
  v5 = 1;
  if ( *((_BYTE *)a1 + 1200) == 1 )
    return 1073741851;
  v7 = PsReferencePrimaryToken(a2[2]);
  if ( v7 )
  {
    v59 = 0;
    LODWORD(v64) = 0;
    v60 = 0;
    v14 = UserProcessImmersiveType(
            (struct _WIN32_PROCESS_CALLOUT_PARAMETERS *)a2,
            v7,
            (enum _PROCESS_IMMERSIVE_TYPE *)&v59,
            &v64,
            (struct _PS_PKG_CLAIM *)&v60);
    if ( v14 >= 0 )
    {
      v20 = W32GetUserSessionState(v13);
      v21 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
              v20,
              1,
              0,
              _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
      *(_QWORD *)(v20 + 16) = v21;
      if ( v21 )
      {
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v21 + 520), 0, 0) & 0x1000000) != 0
          && *(char *)(v21 + 1360) >= 0 )
        {
          v22 = PsGetCurrentProcessWin32Process();
          if ( v22 )
          {
            if ( *(_QWORD *)v22 && *(_BYTE *)(v22 + 1200) == 1 )
            {
              while ( 1 )
              {
                v24 = *(_QWORD **)(v20 + 19544);
                if ( !v24 )
                  break;
                *(_QWORD *)(v20 + 19544) = v24[2];
                v23 = *v24;
                v24[2] = 0;
                if ( !*(_DWORD *)(v23 + 8) )
                  MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                HMUnlockObject(*v24);
              }
              DestroyDeferredUnlockObjectAssignmentList(v20 + 19576);
              DestroyDeferredUnlockObjectAssignmentList(v20 + 19560);
            }
          }
        }
      }
      inited = xxxInitProcessInfo(a1, v7, v59, (unsigned int)v64, (__int64)&v60);
      PsDereferencePrimaryToken(v7);
      if ( inited >= 0 )
      {
        UserSessionSwitchLeaveCritWithNonPaged();
        ProcessJob = PsGetProcessJob(*(_QWORD *)a1);
        v27 = ProcessJob;
        if ( ProcessJob && (unsigned int)PsGetJobUIRestrictionsClass(ProcessJob) )
        {
          v63 = 0;
          v61 = 0;
          v62 = 0;
          JobLock = (struct _ERESOURCE *)PsGetJobLock(v27);
          ExEnterCriticalRegionAndAcquireResourceExclusive(JobLock);
          v63 = *(_QWORD *)a1;
          *(_QWORD *)&v62 = v27;
          DWORD2(v62) = 1;
          inited = UserJobCallout(&v61);
          v29 = (struct _ERESOURCE *)PsGetJobLock(v27);
          ExReleaseResourceAndLeaveCriticalRegion(v29);
        }
      }
      else
      {
        DestroyProcessInfo(a1);
        UserSessionSwitchLeaveCritWithNonPaged();
      }
      return (unsigned int)inited;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (v13 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v13 & 0x80u) == 0LL)
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        v5 = 0;
      }
      v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = *((_DWORD *)a1 + 14);
        v17 = W32GetUserSessionState(v13);
        LOBYTE(v18) = v15;
        LOBYTE(v19) = v5;
        WPP_RECORDER_AND_TRACE_SF_dD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v19,
          v18,
          *(_QWORD *)(v17 + 69136),
          3,
          8,
          35,
          (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids,
          v14,
          v16);
      }
      PsDereferencePrimaryToken(v7);
      return (unsigned int)v14;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v5 = 0;
    }
    v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = *((_DWORD *)a1 + 14);
      v10 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v11) = v8;
      LOBYTE(v12) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        v11,
        *(_QWORD *)(v10 + 69136),
        3,
        8,
        34,
        (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids,
        v9);
    }
    return 3221225596LL;
  }
}

```

## disassembly

```asm
0x14014bc30  mov     [rsp-8+arg_0], rbx
0x14014bc35  mov     [rsp-8+arg_8], rsi
0x14014bc3a  push    rbp
0x14014bc3b  push    rdi
0x14014bc3c  push    r12
0x14014bc3e  push    r14
0x14014bc40  push    r15
0x14014bc42  lea     rbp, [rsp-37h]
0x14014bc47  sub     rsp, 90h
0x14014bc4e  mov     rsi, rdx
0x14014bc51  mov     rbx, rcx
0x14014bc54  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x14014bc59  test    eax, eax
0x14014bc5b  jnz     loc_14014C27F
0x14014bc61  test    rsi, rsi
0x14014bc64  jz      loc_14014BFDF
0x14014bc6a  mov     al, [rbx+4B0h]
0x14014bc70  mov     edi, 1
0x14014bc75  cmp     al, dil
0x14014bc78  jnz     short loc_14014BC84
0x14014bc7a  mov     eax, 4000001Bh
0x14014bc7f  jmp     loc_14014C298
0x14014bc84  mov     rcx, [rsi+10h]; Process
0x14014bc88  call    cs:__imp_PsReferencePrimaryToken
0x14014bc8f  nop     dword ptr [rax+rax+00h]
0x14014bc94  mov     r15, rax
0x14014bc97  test    rax, rax
0x14014bc9a  jnz     loc_14014BD39
0x14014bca0  mov     rcx, cs:WPP_GLOBAL_Control
0x14014bca7  lea     rax, WPP_GLOBAL_Control
0x14014bcae  cmp     rcx, rax
0x14014bcb1  jz      short loc_14014BCC0
0x14014bcb3  mov     eax, [rcx+2Ch]
0x14014bcb6  test    al, al
0x14014bcb8  jns     short loc_14014BCC0
0x14014bcba  cmp     byte ptr [rcx+29h], 3
0x14014bcbe  jnb     short loc_14014BCC3
0x14014bcc0  xor     dil, dil
0x14014bcc3  lea     rax, WPP_RECORDER_INITIALIZED
0x14014bcca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14014bcd1  setnz   sil
0x14014bcd5  test    dil, dil
0x14014bcd8  jnz     short loc_14014BCDF
0x14014bcda  test    sil, sil
0x14014bcdd  jz      short loc_14014BD2F
0x14014bcdf  mov     ebx, [rbx+38h]
0x14014bce2  call    cs:__imp_W32GetUserSessionState
0x14014bce9  nop     dword ptr [rax+rax+00h]
0x14014bcee  mov     rcx, cs:WPP_GLOBAL_Control
0x14014bcf5  mov     r8b, sil
0x14014bcf8  mov     [rsp+0B0h+var_70], ebx
0x14014bcfc  mov     dl, dil
0x14014bcff  mov     r9, [rax+10E10h]
0x14014bd06  lea     rax, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x14014bd0d  mov     rcx, [rcx+18h]
0x14014bd11  mov     [rsp+0B0h+var_78], rax
0x14014bd16  mov     [rsp+0B0h+var_80], 22h ; '"'
0x14014bd1d  mov     [rsp+0B0h+var_88], 8
0x14014bd25  mov     byte ptr [rsp+0B0h+var_90], 3
0x14014bd2a  call    WPP_RECORDER_AND_TRACE_SF_D
0x14014bd2f  mov     eax, 0C000007Ch
0x14014bd34  jmp     loc_14014C298
0x14014bd39  lea     rax, [rbp+57h+var_58]
0x14014bd3d  mov     [rbp+57h+var_60], 0
0x14014bd44  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x14014bd48  mov     [rsp+0B0h+var_90], rax; struct _PS_PKG_CLAIM *
0x14014bd4d  lea     r8, [rbp+57h+var_60]; enum _PROCESS_IMMERSIVE_TYPE *
0x14014bd51  mov     dword ptr [rbp+57h+arg_18], 0
0x14014bd58  mov     rdx, r15; void *
0x14014bd5b  mov     [rbp+57h+var_58], 0
0x14014bd63  mov     rcx, rsi; struct _WIN32_PROCESS_CALLOUT_PARAMETERS *
0x14014bd66  call    ?UserProcessImmersiveType@@YAJPEAU_WIN32_PROCESS_CALLOUT_PARAMETERS@@PEAXPEAW4_PROCESS_IMMERSIVE_TYPE@@PEAKPEAU_PS_PKG_CLAIM@@@Z; UserProcessImmersiveType(_WIN32_PROCESS_CALLOUT_PARAMETERS *,void *,_PROCESS_IMMERSIVE_TYPE *,ulong *,_PS_PKG_CLAIM *)
0x14014bd6b  mov     esi, eax
0x14014bd6d  test    eax, eax
0x14014bd6f  jns     loc_14014BE1E
0x14014bd75  mov     rdx, cs:WPP_GLOBAL_Control
0x14014bd7c  lea     rax, WPP_GLOBAL_Control
0x14014bd83  cmp     rdx, rax
0x14014bd86  jz      short loc_14014BD95
0x14014bd88  mov     ecx, [rdx+2Ch]
0x14014bd8b  test    cl, cl
0x14014bd8d  jns     short loc_14014BD95
0x14014bd8f  cmp     byte ptr [rdx+29h], 3
0x14014bd93  jnb     short loc_14014BD98
0x14014bd95  xor     dil, dil
0x14014bd98  lea     rax, WPP_RECORDER_INITIALIZED
0x14014bd9f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14014bda6  setnz   r14b
0x14014bdaa  test    dil, dil
0x14014bdad  jnz     short loc_14014BDB4
0x14014bdaf  test    r14b, r14b
0x14014bdb2  jz      short loc_14014BE08
0x14014bdb4  mov     ebx, [rbx+38h]
0x14014bdb7  call    cs:__imp_W32GetUserSessionState
0x14014bdbe  nop     dword ptr [rax+rax+00h]
0x14014bdc3  mov     rcx, cs:WPP_GLOBAL_Control
0x14014bdca  mov     r8b, r14b
0x14014bdcd  mov     [rsp+0B0h+var_68], ebx
0x14014bdd1  mov     dl, dil
0x14014bdd4  mov     [rsp+0B0h+var_70], esi
0x14014bdd8  mov     r9, [rax+10E10h]
0x14014bddf  lea     rax, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x14014bde6  mov     rcx, [rcx+18h]
0x14014bdea  mov     [rsp+0B0h+var_78], rax
0x14014bdef  mov     [rsp+0B0h+var_80], 23h ; '#'
0x14014bdf6  mov     [rsp+0B0h+var_88], 8
0x14014bdfe  mov     byte ptr [rsp+0B0h+var_90], 3
0x14014be03  call    WPP_RECORDER_AND_TRACE_SF_dD
0x14014be08  mov     rcx, r15; PrimaryToken
0x14014be0b  call    cs:__imp_PsDereferencePrimaryToken
0x14014be12  nop     dword ptr [rax+rax+00h]
0x14014be17  mov     eax, esi
0x14014be19  jmp     loc_14014C298
0x14014be1e  call    cs:__imp_W32GetUserSessionState
0x14014be25  nop     dword ptr [rax+rax+00h]
0x14014be2a  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14014be31  xor     r8d, r8d
0x14014be34  mov     rcx, rax
0x14014be37  mov     edx, edi
0x14014be39  mov     rsi, rax
0x14014be3c  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x14014be41  mov     [rsi+10h], rax
0x14014be45  mov     rdx, rax
0x14014be48  test    rax, rax
0x14014be4b  jz      loc_14014BEFC
0x14014be51  xor     ecx, ecx
0x14014be53  xor     eax, eax
0x14014be55  lock cmpxchg [rdx+208h], ecx
0x14014be5d  bt      eax, 18h
0x14014be61  jnb     loc_14014BEFC
0x14014be67  mov     al, [rdx+550h]
0x14014be6d  test    al, al
0x14014be6f  js      loc_14014BEFC
0x14014be75  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14014be7c  nop     dword ptr [rax+rax+00h]
0x14014be81  test    rax, rax
0x14014be84  jz      short loc_14014BEFC
0x14014be86  cmp     qword ptr [rax], 0
0x14014be8a  jz      short loc_14014BEFC
0x14014be8c  mov     al, [rax+4B0h]
0x14014be92  cmp     al, dil
0x14014be95  jz      short loc_14014BED8
0x14014be97  jmp     short loc_14014BEFC
0x14014be99  mov     rax, [r14+10h]
0x14014be9d  mov     [rsi+4C58h], rax
0x14014bea4  mov     rax, [r14]
0x14014bea7  mov     qword ptr [r14+10h], 0
0x14014beaf  cmp     [rax+8], edi
0x14014beb2  jnb     short loc_14014BED0
0x14014beb4  mov     [rbp+57h+arg_10], 20000h
0x14014bebb  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14014bec2  mov     edx, [rbp+57h+arg_10]
0x14014bec5  mov     r8d, 1236h
0x14014becb  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14014bed0  mov     rcx, [r14]
0x14014bed3  call    HMUnlockObject
0x14014bed8  mov     r14, [rsi+4C58h]
0x14014bedf  test    r14, r14
0x14014bee2  jnz     short loc_14014BE99
0x14014bee4  lea     rcx, [rsi+4C78h]
0x14014beeb  call    DestroyDeferredUnlockObjectAssignmentList
0x14014bef0  lea     rcx, [rsi+4C68h]
0x14014bef7  call    DestroyDeferredUnlockObjectAssignmentList
0x14014befc  mov     r9d, dword ptr [rbp+57h+arg_18]
0x14014bf00  lea     rax, [rbp+57h+var_58]
0x14014bf04  mov     r8d, [rbp+57h+var_60]
0x14014bf08  mov     rdx, r15; Token
0x14014bf0b  mov     rcx, rbx; struct _W32PROCESS *
0x14014bf0e  mov     [rsp+0B0h+var_90], rax; __int64
0x14014bf13  call    xxxInitProcessInfo
0x14014bf18  mov     rcx, r15; PrimaryToken
0x14014bf1b  mov     r14d, eax
0x14014bf1e  call    cs:__imp_PsDereferencePrimaryToken
0x14014bf25  nop     dword ptr [rax+rax+00h]
0x14014bf2a  test    r14d, r14d
0x14014bf2d  jns     short loc_14014BF44
0x14014bf2f  mov     rcx, rbx
0x14014bf32  call    DestroyProcessInfo
0x14014bf37  call    UserSessionSwitchLeaveCritWithNonPaged
0x14014bf3c  mov     eax, r14d
0x14014bf3f  jmp     loc_14014C298
0x14014bf44  call    UserSessionSwitchLeaveCritWithNonPaged
0x14014bf49  mov     rcx, [rbx]
0x14014bf4c  call    cs:__imp_PsGetProcessJob
0x14014bf53  nop     dword ptr [rax+rax+00h]
0x14014bf58  mov     rsi, rax
0x14014bf5b  test    rax, rax
0x14014bf5e  jz      short loc_14014BF3C
0x14014bf60  mov     rcx, rax
0x14014bf63  call    cs:__imp_PsGetJobUIRestrictionsClass
0x14014bf6a  nop     dword ptr [rax+rax+00h]
0x14014bf6f  test    eax, eax
0x14014bf71  jz      short loc_14014BF3C
0x14014bf73  xorps   xmm0, xmm0
0x14014bf76  xor     eax, eax
0x14014bf78  mov     rcx, rsi
0x14014bf7b  mov     [rbp+57h+var_30], rax
0x14014bf7f  movups  [rbp+57h+var_50], xmm0
0x14014bf83  movups  [rbp+57h+var_40], xmm0
0x14014bf87  call    cs:__imp_PsGetJobLock
0x14014bf8e  nop     dword ptr [rax+rax+00h]
0x14014bf93  mov     rcx, rax; Resource
0x14014bf96  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14014bf9d  nop     dword ptr [rax+rax+00h]
0x14014bfa2  mov     rax, [rbx]
0x14014bfa5  lea     rcx, [rbp+57h+var_50]
0x14014bfa9  mov     [rbp+57h+var_30], rax
0x14014bfad  mov     qword ptr [rbp+57h+var_40], rsi
0x14014bfb1  mov     dword ptr [rbp+57h+var_40+8], edi
0x14014bfb4  call    UserJobCallout
0x14014bfb9  mov     rcx, rsi
0x14014bfbc  mov     r14d, eax
0x14014bfbf  call    cs:__imp_PsGetJobLock
0x14014bfc6  nop     dword ptr [rax+rax+00h]
0x14014bfcb  mov     rcx, rax; Resource
0x14014bfce  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14014bfd5  nop     dword ptr [rax+rax+00h]
0x14014bfda  jmp     loc_14014BF3C
0x14014bfdf  call    cs:__imp_W32GetUserSessionState
0x14014bfe6  nop     dword ptr [rax+rax+00h]
0x14014bfeb  xor     r8d, r8d
0x14014bfee  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14014bff5  mov     rcx, rax
0x14014bff8  mov     rsi, rax
0x14014bffb  lea     edi, [r8+1]
0x14014bfff  mov     edx, edi
0x14014c001  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x14014c006  mov     [rsi+10h], rax
0x14014c00a  mov     rdx, rax
0x14014c00d  test    rax, rax
0x14014c010  jz      loc_14014C0C1
0x14014c016  xor     ecx, ecx
0x14014c018  xor     eax, eax
0x14014c01a  lock cmpxchg [rdx+208h], ecx
0x14014c022  bt      eax, 18h
0x14014c026  jnb     loc_14014C0C1
0x14014c02c  mov     al, [rdx+550h]
0x14014c032  test    al, al
0x14014c034  js      loc_14014C0C1
0x14014c03a  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14014c041  nop     dword ptr [rax+rax+00h]
0x14014c046  test    rax, rax
0x14014c049  jz      short loc_14014C0C1
0x14014c04b  cmp     qword ptr [rax], 0
0x14014c04f  jz      short loc_14014C0C1
0x14014c051  mov     al, [rax+4B0h]
0x14014c057  cmp     al, dil
0x14014c05a  jz      short loc_14014C09D
0x14014c05c  jmp     short loc_14014C0C1
0x14014c05e  mov     rax, [r14+10h]
0x14014c062  mov     [rsi+4C58h], rax
0x14014c069  mov     rax, [r14]
0x14014c06c  mov     qword ptr [r14+10h], 0
0x14014c074  cmp     [rax+8], edi
0x14014c077  jnb     short loc_14014C095
0x14014c079  mov     [rbp+57h+arg_10], 20000h
0x14014c080  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14014c087  mov     edx, [rbp+57h+arg_10]
0x14014c08a  mov     r8d, 1236h
0x14014c090  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14014c095  mov     rcx, [r14]
0x14014c098  call    HMUnlockObject
0x14014c09d  mov     r14, [rsi+4C58h]
0x14014c0a4  test    r14, r14
0x14014c0a7  jnz     short loc_14014C05E
0x14014c0a9  lea     rcx, [rsi+4C78h]
0x14014c0b0  call    DestroyDeferredUnlockObjectAssignmentList
0x14014c0b5  lea     rcx, [rsi+4C68h]
0x14014c0bc  call    DestroyDeferredUnlockObjectAssignmentList
0x14014c0c1  call    cs:__imp_W32GetUserGdiSessionState
0x14014c0c8  nop     dword ptr [rax+rax+00h]
0x14014c0cd  cmp     qword ptr [rax+28h], 0
0x14014c0d2  jz      short loc_14014C0E9
0x14014c0d4  call    cs:__imp_W32GetUserGdiSessionState
0x14014c0db  nop     dword ptr [rax+rax+00h]
0x14014c0e0  mov     rcx, [rax+28h]
0x14014c0e4  cmp     [rbx], rcx
0x14014c0e7  jz      short loc_14014C0EC
0x14014c0e9  xor     dil, dil
0x14014c0ec  call    cs:__imp_W32GetUserGdiSessionState
0x14014c0f3  nop     dword ptr [rax+rax+00h]
0x14014c0f8  mov     rcx, [rax+28h]
0x14014c0fc  cmp     [rbx], rcx
0x14014c0ff  jnz     short loc_14014C10D
0x14014c101  call    cs:__imp_W32GetUserSessionState
0x14014c108  nop     dword ptr [rax+rax+00h]
0x14014c10d  mov     rcx, [rbx]
0x14014c110  test    rcx, rcx
0x14014c113  jz      short loc_14014C16F
0x14014c115  call    cs:__imp_PsGetProcessJob
0x14014c11c  nop     dword ptr [rax+rax+00h]
0x14014c121  test    rax, rax
0x14014c124  jz      short loc_14014C16F
0x14014c126  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14014c12d  nop     dword ptr [rax+rax+00h]
0x14014c132  mov     rcx, [rax+30h]
0x14014c136  mov     rax, [rcx+260h]
0x14014c13d  test    rax, rax
0x14014c140  jz      short loc_14014C16F
0x14014c142  call    _guard_dispatch_icall
  ... truncated ...
```
