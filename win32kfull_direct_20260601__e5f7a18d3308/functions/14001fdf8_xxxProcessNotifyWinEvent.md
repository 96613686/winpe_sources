# xxxProcessNotifyWinEvent

- ea: `0x14001fdf8`
- end: `0x140020227`
- name: `xxxProcessNotifyWinEvent`
- size: `1071`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ef90`
- `0x140097760`
- `0x1400c6fb4`

## callees

- `0x140005a18`
- `0x14001fdf8`
- `0x140020840`
- `0x140023570`
- `0x1400c0e10`
- `0x1400c7ad0`
- `0x1400db7b0`
- `0x1400e2cb0`
- `0x1400e759c`
- `0x14018dd64`
- `0x1401a3748`
- `0x1401b60e4`
- `0x1402aae84`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsWow64GetProcessMachine` at `0x14001ffe6`
- `ntoskrnl!PsWow64GetProcessMachine` at `0x14001fff8`
- `ntoskrnl!PsWow64GetProcessMachine` at `0x14001ffe6`
- `ntoskrnl!PsWow64GetProcessMachine` at `0x14001fff8`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140020169`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140020169`
- `ntoskrnl!PsGetProcessMachine` at `0x14001fecb`
- `ntoskrnl!PsGetProcessMachine` at `0x14001fedd`
- `ntoskrnl!PsGetProcessMachine` at `0x14001fecb`
- `ntoskrnl!PsGetProcessMachine` at `0x14001fedd`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14001fe43`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14001fe43`
- `win32kbase!IsRestricted` at `0x14001fea3`
- `win32kbase!IsRestricted` at `0x14001fea3`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1400201d5`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140020205`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1400201d5`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140020205`
- `win32kbase!EtwTraceUIPIEventHookError` at `0x14001ff46`
- `win32kbase!EtwTraceUIPIEventHookError` at `0x14001ff46`
- `win32kbase!IsImmersiveBroker` at `0x1400200fc`
- `win32kbase!IsImmersiveBroker` at `0x1400200fc`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x14002007e`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x14002007e`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14001ff0c`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14001ff0c`
- `win32kbase!IsImmersiveAppRestricted` at `0x140020136`
- `win32kbase!IsImmersiveAppRestricted` at `0x140020136`
- `WIN32K!W32GetUserSessionState` at `0x14001fe30`
- `WIN32K!W32GetUserSessionState` at `0x14001ff70`
- `WIN32K!W32GetUserSessionState` at `0x14001fe30`
- `WIN32K!W32GetUserSessionState` at `0x14001ff70`

## pseudocode

```c
__int64 __fastcall xxxProcessNotifyWinEvent(__int64 a1)
{
  struct tagTHREADINFO *v2; // r14
  int v3; // r12d
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 UserSessionState; // rax
  __int64 v7; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdi
  __int16 v11; // bx
  __int64 v12; // rdx
  struct tagQ *v13; // r13
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // eax
  signed __int32 v19; // edx
  __int64 v20; // rbx
  __int16 ProcessMachine; // di
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  void (*EventProc)(HWINEVENTHOOK, unsigned int, HWND, int, int, unsigned int, unsigned int); // rdi
  unsigned int v29; // ebx
  __int64 ProcessInformation; // [rsp+40h] [rbp-39h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v32[48]; // [rsp+58h] [rbp-21h] BYREF

  v2 = PtiCurrent();
  v3 = 0;
  UserSessionState = W32GetUserSessionState(v5, v4);
  if ( ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(UserSessionState + 42144)) != 1 )
    __int2c();
  v7 = *(_QWORD *)(a1 + 16);
  IsEnabledDeviceUsageNoInline = Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline();
  if ( (*(_DWORD *)(a1 + 56) & 0xC) == 4 )
    goto LABEL_11;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v2 + 130, 0, 0) & 0xD) != 0 )
    {
LABEL_11:
      v12 = *(_QWORD *)(v7 + 16);
      ProcessInformation = *(_QWORD *)(v7 + 24);
      v13 = *(struct tagQ **)(v12 + 464);
      if ( v3 )
        EtwTraceUIPIEventHookError(a1, v12, v2);
      LOBYTE(BugCheckParameter3[0]) = 0;
      BugCheckParameter3[1] = 0;
      AtomicExecutionCheck::Arm((AtomicExecutionCheck *)BugCheckParameter3);
      *(_DWORD *)(a1 + 56) |= 0xCu;
      if ( !v13
        || (v16 = W32GetUserSessionState(v15, v14), v17 = *(_QWORD *)(v7 + 16), v17 == *(_QWORD *)(v16 + 18752))
        || (v18 = *(_DWORD *)(v7 + 40), (v18 & 1) != 0)
        || (v18 & 0x10) != 0
        && ((v19 = _InterlockedCompareExchange((volatile signed __int32 *)(v17 + 520), 0, 0),
             ((v19 ^ _InterlockedCompareExchange((volatile signed __int32 *)v2 + 130, 0, 0)) & 0x100) != 0)
         || (_InterlockedCompareExchange((volatile signed __int32 *)v2 + 130, 0, 0) & 0x100) != 0
         && (v20 = **((_QWORD **)v2 + 57),
             ProcessMachine = PsWow64GetProcessMachine(**(_QWORD **)(*(_QWORD *)(v7 + 16) + 456LL)),
             (unsigned __int16)PsWow64GetProcessMachine(v20) != ProcessMachine))
        || !(unsigned int)PostEventMessageEx(*(struct tagTHREADINFO **)(v7 + 16), v13, 0xCu, 0, 0, 0, a1, 0) )
      {
        DestroyNotify(a1);
      }
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)BugCheckParameter3);
      return ProcessInformation;
    }
  }
  else
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v2 + 130, 0, 0) & 0xD) != 0 )
      goto LABEL_11;
    if ( !UIPrivilegeIsolation::Enforced(0) )
    {
      v23 = *((_QWORD *)v2 + 57);
      v24 = *(_QWORD *)(*(_QWORD *)(v7 + 16) + 456LL);
      if ( (*(_DWORD *)(v24 + 764) != *(_DWORD *)(v23 + 764) || *(_DWORD *)(v24 + 768) != *(_DWORD *)(v23 + 768))
        && (_InterlockedCompareExchange((volatile signed __int32 *)v2 + 130, 0, 0) & 0x400000) == 0 )
      {
        goto LABEL_11;
      }
    }
  }
  v9 = *(_QWORD **)(v7 + 16);
  if ( v9[57] != *((_QWORD *)v2 + 57) && (unsigned __int8)IsRestricted(*v9) )
    goto LABEL_11;
  v10 = **(_QWORD **)(*(_QWORD *)(v7 + 16) + 456LL);
  v11 = PsGetProcessMachine(**((_QWORD **)v2 + 57));
  if ( v11 != (unsigned __int16)PsGetProcessMachine(v10) )
    goto LABEL_11;
  if ( !UIPrivilegeIsolation::CheckAccess(
          (UIPrivilegeIsolation *)(*(_QWORD *)(*(_QWORD *)(v7 + 16) + 456LL) + 864LL),
          (const struct tagUIPI_INFO *)(*((_QWORD *)v2 + 57) + 864LL),
          (const struct tagUIPI_INFO *)0x360) )
  {
    v3 = 1;
    goto LABEL_11;
  }
  if ( (!*(_DWORD *)(v7 + 56) || !*(_QWORD *)(v7 + 48))
    && !(unsigned int)IsImmersiveBroker(*(_QWORD *)(*(_QWORD *)(v7 + 16) + 456LL)) )
  {
    v25 = *(_QWORD *)(*(_QWORD *)(v7 + 16) + 456LL);
    if ( *(int *)(v25 + 12) >= 0 )
    {
      v26 = *((_QWORD *)v2 + 57);
      if ( v25 != v26 && (*(_DWORD *)(v25 + 808) & 0x100LL) == 0 )
      {
        if ( (unsigned int)IsImmersiveAppRestricted(v26) )
          goto LABEL_11;
        ProcessInformation = 6;
        if ( ZwQueryInformationProcess(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               ProcessCookie|ProcessUserModeIOPL,
               &ProcessInformation,
               8u,
               0) < 0
          || (ProcessInformation & 0x100000000LL) != 0 )
        {
          goto LABEL_11;
        }
      }
    }
  }
  if ( (*(_DWORD *)(v7 + 40) & 1) != 0 )
  {
    v27 = *(_QWORD *)(v7 + 24);
  }
  else
  {
    Win32HM_LockIntoThread<0>(v2, v7, BugCheckParameter3);
    *(_QWORD *)(a1 + 64) = v2;
    if ( (*(_DWORD *)(v7 + 40) & 8) != 0 )
      EventProc = xxxGetEventProc((struct tagEVENTHOOK *)v7);
    else
      EventProc = *(void (**)(HWINEVENTHOOK, unsigned int, HWND, int, int, unsigned int, unsigned int))(v7 + 64);
    if ( EventProc )
    {
      v29 = W32SetCurrentThreadDpiAwarenessContext(*(unsigned int *)(v7 + 76));
      UnlockDomainShared<>::UnlockDomainExclusive<DLT_WINEVENT>::UnlockObjectLock<>::UnlockObjectLock<>(v32);
      xxxClientCallWinEventProc((__int64)EventProc, (__int64 *)v7, a1);
      UnlockDomainShared<>::UnlockDomainExclusive<DLT_CLIENTLIB>::UnlockObjectLock<>::~UnlockObjectLock<>(v32);
      W32SetCurrentThreadDpiAwarenessContext(v29);
    }
    *(_QWORD *)(a1 + 64) = 0;
    v27 = *(_QWORD *)(v7 + 24);
    Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
  }
  DestroyNotify(a1);
  return v27;
}

```

## disassembly

```asm
0x14001fdf8  push    rbp
0x14001fdfa  push    rbx
0x14001fdfb  push    rsi
0x14001fdfc  push    rdi
0x14001fdfd  push    r12
0x14001fdff  push    r13
0x14001fe01  push    r14
0x14001fe03  push    r15
0x14001fe05  lea     rbp, [rsp-1Fh]
0x14001fe0a  sub     rsp, 98h
0x14001fe11  mov     rax, cs:__security_cookie
0x14001fe18  xor     rax, rsp
0x14001fe1b  mov     [rbp+57h+var_48], rax
0x14001fe1f  mov     r15, rcx
0x14001fe22  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001fe27  xor     r13d, r13d
0x14001fe2a  mov     r14, rax
0x14001fe2d  mov     r12d, r13d
0x14001fe30  call    cs:__imp_W32GetUserSessionState
0x14001fe37  nop     dword ptr [rax+rax+00h]
0x14001fe3c  mov     rcx, [rax+0A4A0h]; Resource
0x14001fe43  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14001fe4a  nop     dword ptr [rax+rax+00h]
0x14001fe4f  cmp     al, 1
0x14001fe51  jz      short loc_14001FE55
0x14001fe53  int     2Ch; Windows NT - assertion failure
0x14001fe55  mov     rsi, [r15+10h]
0x14001fe59  call    Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline
0x14001fe5e  mov     ecx, [r15+38h]
0x14001fe62  and     cl, 0Ch
0x14001fe65  cmp     cl, 4
0x14001fe68  jz      loc_14001FF26
0x14001fe6e  mov     ecx, r13d
0x14001fe71  test    eax, eax
0x14001fe73  jz      loc_14002006B
0x14001fe79  xor     eax, eax
0x14001fe7b  lock cmpxchg [r14+208h], ecx
0x14001fe84  test    al, 0Dh
0x14001fe86  jnz     loc_14001FF26
0x14001fe8c  mov     rcx, [rsi+10h]
0x14001fe90  mov     rax, [r14+1C8h]
0x14001fe97  cmp     [rcx+1C8h], rax
0x14001fe9e  jz      short loc_14001FEB3
0x14001fea0  mov     rcx, [rcx]
0x14001fea3  call    cs:__imp_IsRestricted
0x14001feaa  nop     dword ptr [rax+rax+00h]
0x14001feaf  test    al, al
0x14001feb1  jnz     short loc_14001FF26
0x14001feb3  mov     rax, [rsi+10h]
0x14001feb7  mov     rcx, [rax+1C8h]
0x14001febe  mov     rax, [r14+1C8h]
0x14001fec5  mov     rdi, [rcx]
0x14001fec8  mov     rcx, [rax]
0x14001fecb  call    cs:__imp_PsGetProcessMachine
0x14001fed2  nop     dword ptr [rax+rax+00h]
0x14001fed7  mov     rcx, rdi
0x14001feda  movzx   ebx, ax
0x14001fedd  call    cs:__imp_PsGetProcessMachine
0x14001fee4  nop     dword ptr [rax+rax+00h]
0x14001fee9  cmp     bx, ax
0x14001feec  jnz     short loc_14001FF26
0x14001feee  mov     rax, [rsi+10h]
0x14001fef2  mov     r8d, 360h
0x14001fef8  mov     rdx, [r14+1C8h]
0x14001feff  add     rdx, r8
0x14001ff02  mov     rcx, [rax+1C8h]
0x14001ff09  add     rcx, r8
0x14001ff0c  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x14001ff13  nop     dword ptr [rax+rax+00h]
0x14001ff18  test    al, al
0x14001ff1a  jnz     loc_1400200E1
0x14001ff20  mov     r12d, 1
0x14001ff26  mov     rdx, [rsi+10h]
0x14001ff2a  xor     ebx, ebx
0x14001ff2c  mov     rax, [rsi+18h]
0x14001ff30  mov     [rbp+57h+ProcessInformation], rax
0x14001ff34  mov     r13, [rdx+1D0h]
0x14001ff3b  test    r12d, r12d
0x14001ff3e  jz      short loc_14001FF52
0x14001ff40  mov     r8, r14
0x14001ff43  mov     rcx, r15
0x14001ff46  call    cs:__imp_EtwTraceUIPIEventHookError
0x14001ff4d  nop     dword ptr [rax+rax+00h]
0x14001ff52  lea     rcx, [rbp+57h+BugCheckParameter3]; this
0x14001ff56  mov     byte ptr [rbp+57h+BugCheckParameter3], bl
0x14001ff59  mov     [rbp+57h+var_80], rbx
0x14001ff5d  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Arm(void)
0x14001ff62  or      dword ptr [r15+38h], 0Ch
0x14001ff67  test    r13, r13
0x14001ff6a  jz      loc_140020035
0x14001ff70  call    cs:__imp_W32GetUserSessionState
0x14001ff77  nop     dword ptr [rax+rax+00h]
0x14001ff7c  mov     rdx, [rsi+10h]
0x14001ff80  cmp     rdx, [rax+4940h]
0x14001ff87  jz      loc_140020035
0x14001ff8d  mov     eax, [rsi+28h]
0x14001ff90  test    al, 1
0x14001ff92  jnz     loc_140020035
0x14001ff98  test    al, 10h
0x14001ff9a  jz      short loc_14002000B
0x14001ff9c  mov     ecx, ebx
0x14001ff9e  xor     eax, eax
0x14001ffa0  lock cmpxchg [rdx+208h], ecx
0x14001ffa8  mov     edx, eax
0x14001ffaa  xor     eax, eax
0x14001ffac  lock cmpxchg [r14+208h], ecx
0x14001ffb5  xor     eax, edx
0x14001ffb7  bt      eax, 8
0x14001ffbb  jb      short loc_140020035
0x14001ffbd  xor     eax, eax
0x14001ffbf  lock cmpxchg [r14+208h], ecx
0x14001ffc8  bt      eax, 8
0x14001ffcc  jnb     short loc_14002000B
0x14001ffce  mov     rax, [rsi+10h]
0x14001ffd2  mov     rcx, [rax+1C8h]
0x14001ffd9  mov     rax, [r14+1C8h]
0x14001ffe0  mov     rcx, [rcx]
0x14001ffe3  mov     rbx, [rax]
0x14001ffe6  call    cs:__imp_PsWow64GetProcessMachine
0x14001ffed  nop     dword ptr [rax+rax+00h]
0x14001fff2  mov     rcx, rbx
0x14001fff5  movzx   edi, ax
0x14001fff8  call    cs:__imp_PsWow64GetProcessMachine
0x14001ffff  nop     dword ptr [rax+rax+00h]
0x140020004  cmp     ax, di
0x140020007  jnz     short loc_140020035
0x140020009  xor     ebx, ebx
0x14002000b  mov     rcx, [rsi+10h]; struct tagTHREADINFO *
0x14002000f  xor     r9d, r9d; struct tagWND *
0x140020012  mov     [rsp+0D0h+var_98], rbx; struct tagINPUT_MESSAGE_SOURCE *
0x140020017  mov     rdx, r13; struct tagQ *
0x14002001a  mov     [rsp+0D0h+var_A0], r15; __int64
0x14002001f  mov     [rsp+0D0h+var_A8], rbx; unsigned __int64
0x140020024  lea     r8d, [r9+0Ch]; unsigned int
0x140020028  mov     dword ptr [rsp+0D0h+ReturnLength], ebx; unsigned int
0x14002002c  call    ?PostEventMessageEx@@YAHPEAUtagTHREADINFO@@PEAUtagQ@@KPEAUtagWND@@I_K_JPEAUtagINPUT_MESSAGE_SOURCE@@@Z; PostEventMessageEx(tagTHREADINFO *,tagQ *,ulong,tagWND *,uint,unsigned __int64,__int64,tagINPUT_MESSAGE_SOURCE *)
0x140020031  test    eax, eax
0x140020033  jnz     short loc_14002003D
0x140020035  mov     rcx, r15
0x140020038  call    DestroyNotify
0x14002003d  lea     rcx, [rbp+57h+BugCheckParameter3]; this
0x140020041  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x140020046  mov     rax, [rbp+57h+ProcessInformation]
0x14002004a  mov     rcx, [rbp+57h+var_48]
0x14002004e  xor     rcx, rsp; StackCookie
0x140020051  call    __security_check_cookie
0x140020056  add     rsp, 98h
0x14002005d  pop     r15
0x14002005f  pop     r14
0x140020061  pop     r13
0x140020063  pop     r12
0x140020065  pop     rdi
0x140020066  pop     rsi
0x140020067  pop     rbx
0x140020068  pop     rbp
0x140020069  retn
0x14002006b  xor     eax, eax
0x14002006d  lock cmpxchg [r14+208h], ecx
0x140020076  test    al, 0Dh
0x140020078  jnz     loc_14001FF26
0x14002007e  call    cs:__imp_?Enforced@UIPrivilegeIsolation@@YA_NXZ; UIPrivilegeIsolation::Enforced(void)
0x140020085  nop     dword ptr [rax+rax+00h]
0x14002008a  test    al, al
0x14002008c  jnz     loc_14001FE8C
0x140020092  mov     rax, [rsi+10h]
0x140020096  mov     rcx, [r14+1C8h]
0x14002009d  mov     rdx, [rax+1C8h]
0x1400200a4  mov     eax, [rcx+2FCh]
0x1400200aa  cmp     [rdx+2FCh], eax
0x1400200b0  jnz     short loc_1400200C4
0x1400200b2  mov     eax, [rcx+300h]
0x1400200b8  cmp     [rdx+300h], eax
0x1400200be  jz      loc_14001FE8C
0x1400200c4  mov     ecx, r13d
0x1400200c7  xor     eax, eax
0x1400200c9  lock cmpxchg [r14+208h], ecx
0x1400200d2  bt      eax, 16h
0x1400200d6  jnb     loc_14001FF26
0x1400200dc  jmp     loc_14001FE8C
0x1400200e1  cmp     [rsi+38h], r13d
0x1400200e5  jz      short loc_1400200F1
0x1400200e7  cmp     [rsi+30h], r13
0x1400200eb  jnz     loc_140020187
0x1400200f1  mov     rcx, [rsi+10h]
0x1400200f5  mov     rcx, [rcx+1C8h]
0x1400200fc  call    cs:__imp_IsImmersiveBroker
0x140020103  nop     dword ptr [rax+rax+00h]
0x140020108  test    eax, eax
0x14002010a  jnz     short loc_140020187
0x14002010c  mov     rax, [rsi+10h]
0x140020110  mov     rax, [rax+1C8h]
0x140020117  cmp     [rax+0Ch], r13d
0x14002011b  jl      short loc_140020187
0x14002011d  mov     rcx, [r14+1C8h]
0x140020124  cmp     rax, rcx
0x140020127  jz      short loc_140020187
0x140020129  mov     eax, [rax+328h]
0x14002012f  bt      rax, 8
0x140020134  jb      short loc_140020187
0x140020136  call    cs:__imp_IsImmersiveAppRestricted
0x14002013d  nop     dword ptr [rax+rax+00h]
0x140020142  test    eax, eax
0x140020144  jnz     loc_14001FF26
0x14002014a  mov     [rbp+57h+ProcessInformation], r13
0x14002014e  lea     r9d, [rax+8]; ProcessInformationLength
0x140020152  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x140020156  mov     dword ptr [rbp+57h+ProcessInformation], 6
0x14002015d  lea     edx, [rax+34h]; ProcessInformationClass
0x140020160  mov     [rsp+0D0h+ReturnLength], r13; ReturnLength
0x140020165  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140020169  call    cs:__imp_ZwQueryInformationProcess
0x140020170  nop     dword ptr [rax+rax+00h]
0x140020175  test    eax, eax
0x140020177  js      loc_14001FF26
0x14002017d  test    byte ptr [rbp+57h+ProcessInformation+4], 1
0x140020181  jnz     loc_14001FF26
0x140020187  mov     eax, [rsi+28h]
0x14002018a  test    al, 1
0x14002018c  jz      short loc_1400201A2
0x14002018e  mov     rbx, [rsi+18h]
0x140020192  mov     rcx, r15
0x140020195  call    DestroyNotify
0x14002019a  mov     rax, rbx
0x14002019d  jmp     loc_14002004A
0x1400201a2  lea     r8, [rbp+57h+BugCheckParameter3]
0x1400201a6  mov     rdx, rsi
0x1400201a9  mov     rcx, r14
0x1400201ac  call    ??$Win32HM_LockIntoThread@$0A@@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<0>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x1400201b1  mov     [r15+40h], r14
0x1400201b5  mov     eax, [rsi+28h]
0x1400201b8  test    al, 8
0x1400201ba  jnz     short loc_1400201C2
0x1400201bc  mov     rdi, [rsi+40h]
0x1400201c0  jmp     short loc_1400201CD
0x1400201c2  mov     rcx, rsi; struct tagEVENTHOOK *
0x1400201c5  call    ?xxxGetEventProc@@YAP6AXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@ZPEAUtagEVENTHOOK@@@Z; xxxGetEventProc(tagEVENTHOOK *)
0x1400201ca  mov     rdi, rax
0x1400201cd  test    rdi, rdi
0x1400201d0  jz      short loc_140020211
0x1400201d2  mov     ecx, [rsi+4Ch]
0x1400201d5  call    cs:__imp_W32SetCurrentThreadDpiAwarenessContext
0x1400201dc  nop     dword ptr [rax+rax+00h]
0x1400201e1  lea     rcx, [rbp+57h+var_78]
0x1400201e5  mov     ebx, eax
0x1400201e7  call    ??0?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@VDLT_WINEVENT@@@?$UnlockDomainShared@$$V@@QEAA@XZ; UnlockDomainShared<>::UnlockDomainExclusive<DLT_WINEVENT>::UnlockObjectLock<>::UnlockObjectLock<>(void)
0x1400201ec  mov     r8, r15
0x1400201ef  mov     rdx, rsi
0x1400201f2  mov     rcx, rdi
0x1400201f5  call    xxxClientCallWinEventProc
0x1400201fa  lea     rcx, [rbp+57h+var_78]
0x1400201fe  call    ??1?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@VDLT_CLIENTLIB@@@?$UnlockDomainShared@$$V@@QEAA@XZ; UnlockDomainShared<>::UnlockDomainExclusive<DLT_CLIENTLIB>::UnlockObjectLock<>::~UnlockObjectLock<>(void)
0x140020203  mov     ecx, ebx
0x140020205  call    cs:__imp_W32SetCurrentThreadDpiAwarenessContext
0x14002020c  nop     dword ptr [rax+rax+00h]
0x140020211  mov     [r15+40h], r13
0x140020215  lea     rcx, [rbp+57h+BugCheckParameter3]; BugCheckParameter3
0x140020219  mov     rbx, [rsi+18h]
0x14002021d  call    ??1?$Win32HMThreadLockAlways@UtagWND@@@@QEAA@XZ; Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>(void)
0x140020222  jmp     loc_140020192
```
