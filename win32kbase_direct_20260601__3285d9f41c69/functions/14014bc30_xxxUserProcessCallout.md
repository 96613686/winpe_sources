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
  __int64 ProcessJob; // rax
  __int64 v33; // rsi
  struct _ERESOURCE *JobLock; // rax
  struct _ERESOURCE *v35; // rax
  __int64 UserSessionState; // rsi
  char v37; // di
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v42; // rax
  _QWORD *v43; // r14
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // rcx
  int (*v51)(void); // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  void (__fastcall *v54)(struct _W32PROCESS *); // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r14
  __int64 v59; // rbx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 v64; // rcx
  unsigned __int64 i; // rsi
  __int64 v66; // r8
  __int64 v67; // rax
  __int64 SessionState; // rax
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // rcx
  _DWORD *v73; // rbx
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  _DWORD *v79; // rsi
  __int64 v80; // rax
  unsigned int v81; // [rsp+50h] [rbp-9h] BYREF
  __int64 v82; // [rsp+58h] [rbp-1h] BYREF
  __int128 v83; // [rsp+60h] [rbp+7h] BYREF
  __int128 v84; // [rsp+70h] [rbp+17h]
  __int64 v85; // [rsp+80h] [rbp+27h]
  PVOID v86; // [rsp+D8h] [rbp+7Fh] BYREF

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
    v37 = 1;
    v38 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            UserSessionState,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(UserSessionState + 16) = v38;
    v40 = v38;
    if ( v38 )
    {
      v39 = 0;
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v38 + 520), 0, 0) & 0x1000000) != 0
        && *(char *)(v38 + 1360) >= 0 )
      {
        CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
        if ( CurrentProcessWin32Process )
        {
          if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
          {
            while ( 1 )
            {
              v43 = *(_QWORD **)(UserSessionState + 19544);
              if ( !v43 )
                break;
              *(_QWORD *)(UserSessionState + 19544) = v43[2];
              v42 = *v43;
              v43[2] = 0;
              if ( !*(_DWORD *)(v42 + 8) )
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
              HMUnlockObject(*v43);
            }
            DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
            DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
          }
        }
      }
    }
    if ( !*(_QWORD *)(W32GetUserGdiSessionState(v39, v40) + 40)
      || (v45 = *(_QWORD *)(W32GetUserGdiSessionState(v45, v44) + 40), *(_QWORD *)a1 != v45) )
    {
      v37 = 0;
    }
    v47 = *(_QWORD *)(W32GetUserGdiSessionState(v45, v44) + 40);
    if ( *(_QWORD *)a1 == v47 )
      W32GetUserSessionState(v47, v46, v48);
    if ( *(_QWORD *)a1 )
    {
      if ( ((__int64 (*)(void))PsGetProcessJob)() )
      {
        v51 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v50, v49) + 48) + 608LL);
        if ( v51 )
        {
          if ( v51() >= 0 )
          {
            v54 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v53, v52) + 48)
                                                              + 616LL);
            if ( v54 )
              v54(a1);
          }
        }
      }
    }
    if ( (unsigned int)DestroyProcessInfo(a1) )
    {
      v58 = W32GetUserSessionState(v56, v55, v57);
      v59 = *(_QWORD *)(v58 + 19720);
      for ( i = v59 + 32LL * *(unsigned int *)(W32GetUserSessionState(v61, v60, v62) + 19648);
            i > *(_QWORD *)(v58 + 19720) && !*(_BYTE *)(i + 24);
            i -= 32LL )
      {
        v67 = W32GetUserSessionState(v64, v63, v66);
        --*(_DWORD *)(v67 + 19648);
      }
      SessionState = W32GetSessionState(v64);
      GrepLockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88));
      v72 = *(_QWORD *)(W32GetUserSessionState(v70, v69, v71) + 56744);
      v73 = *(_DWORD **)(v72 + 24);
      v76 = *(_QWORD *)(W32GetUserSessionState(v72, v74, v75) + 56744) + 24LL;
      if ( v73 != (_DWORD *)v76 )
      {
        do
        {
          v79 = *(_DWORD **)v73;
          if ( (v73[12] & 0x400000) != 0 )
            DestroyCacheDC(v73);
          v73 = v79;
          v77 = *(_QWORD *)(W32GetUserSessionState(v77, v76, v78) + 56744) + 24LL;
        }
        while ( v79 != (_DWORD *)v77 );
      }
      v80 = W32GetSessionState(v77);
      GrepUnlockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(v80 + 88));
      ApiSetEditionShowSystemCursor();
      if ( v37 )
        CloseWin32InputRelatedObHandles();
    }
    UserSessionSwitchLeaveCritWithNonPaged();
    return 0;
  }
  v7 = 1;
  if ( *((_BYTE *)a1 + 1200) == 1 )
    return 1073741851;
  v11 = PsReferencePrimaryToken(a2[2]);
  if ( v11 )
  {
    v81 = 0;
    LODWORD(v86) = 0;
    v82 = 0;
    v19 = UserProcessImmersiveType(
            (struct _WIN32_PROCESS_CALLOUT_PARAMETERS *)a2,
            v11,
            (enum _PROCESS_IMMERSIVE_TYPE *)&v81,
            &v86,
            (struct _PS_PKG_CLAIM *)&v82);
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
      inited = xxxInitProcessInfo(a1, v11, v81, (unsigned int)v86, (__int64)&v82);
      PsDereferencePrimaryToken(v11);
      if ( inited >= 0 )
      {
        UserSessionSwitchLeaveCritWithNonPaged();
        ProcessJob = PsGetProcessJob(*(_QWORD *)a1);
        v33 = ProcessJob;
        if ( ProcessJob && (unsigned int)PsGetJobUIRestrictionsClass(ProcessJob) )
        {
          v85 = 0;
          v83 = 0;
          v84 = 0;
          JobLock = (struct _ERESOURCE *)PsGetJobLock(v33);
          ExEnterCriticalRegionAndAcquireResourceExclusive(JobLock);
          v85 = *(_QWORD *)a1;
          *(_QWORD *)&v84 = v33;
          DWORD2(v84) = 1;
          inited = UserJobCallout(&v83);
          v35 = (struct _ERESOURCE *)PsGetJobLock(v33);
          ExReleaseResourceAndLeaveCriticalRegion(v35);
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
          (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids,
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
        (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids,
        v13);
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
