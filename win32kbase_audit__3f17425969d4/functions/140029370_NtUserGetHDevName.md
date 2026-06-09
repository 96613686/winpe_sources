# NtUserGetHDevName

- ea: `0x140029370`
- end: `0x140029700`
- name: `NtUserGetHDevName`
- size: `912`
- prototype: `__int64 __fastcall(int, volatile void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140029370`
- `0x140029850`
- `0x140029880`
- `0x140029a30`
- `0x140029bc0`
- `0x140029bf4`
- `0x140029c70`
- `0x1400700d8`
- `0x1402388e0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400296d4`
- `ntoskrnl!KeBugCheckEx` at `0x1400296d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002963a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002963a`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400296ef`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400296ef`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400295a7`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400295a7`
- `ntoskrnl!ProbeForWrite` at `0x1400294b1`
- `ntoskrnl!ProbeForWrite` at `0x1400294b1`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400296a8`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400296a8`
- `ntoskrnl!ExReleaseFastResource` at `0x14002962e`
- `ntoskrnl!ExReleaseFastResource` at `0x14002962e`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140239334`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140239334`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400295c8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400295c8`
- `WIN32K!W32GetUserSessionState` at `0x1400293cd`
- `WIN32K!W32GetUserSessionState` at `0x1400293e6`
- `WIN32K!W32GetUserSessionState` at `0x1400293f5`
- `WIN32K!W32GetUserSessionState` at `0x140029416`
- `WIN32K!W32GetUserSessionState` at `0x140029580`
- `WIN32K!W32GetUserSessionState` at `0x1400295b9`
- `WIN32K!W32GetUserSessionState` at `0x1400293cd`
- `WIN32K!W32GetUserSessionState` at `0x1400293e6`
- `WIN32K!W32GetUserSessionState` at `0x1400293f5`
- `WIN32K!W32GetUserSessionState` at `0x140029416`
- `WIN32K!W32GetUserSessionState` at `0x140029580`
- `WIN32K!W32GetUserSessionState` at `0x1400295b9`

## pseudocode

```c
__int64 __fastcall NtUserGetHDevName(int a1, volatile void *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 UserSessionState; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r15
  __int64 v17; // r12
  _WORD *v18; // rcx
  int v19; // r14d
  __int16 *v20; // r8
  __int64 v21; // rax
  int v22; // r11d
  __int64 v23; // r10
  __int16 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rbx
  LONG v29; // r8d
  __int64 v30; // rsi
  __int64 v31; // rcx
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax
  __int64 v36; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v37[48]; // [rsp+80h] [rbp-78h] BYREF
  __int128 v38; // [rsp+B0h] [rbp-48h]

  memset(v37, 0, sizeof(v37));
  v38 = 0;
  EnterLeaveCritShared::EnterLeaveCritShared(&v36, 1);
  v3 = 0;
  v7 = *(_QWORD *)(W32GetUserSessionState(v5, v4) + 19704);
  if ( (unsigned __int64)(unsigned __int16)a1 < *(_QWORD *)(v7 + 8) )
  {
    UserSessionState = W32GetUserSessionState(v7, v6);
    v11 = *(_DWORD *)(W32GetUserSessionState(v10, v9) + 19728) * (unsigned int)(unsigned __int16)a1;
    v12 = v11 + *(_QWORD *)(UserSessionState + 19720);
    v14 = W32GetUserSessionState(v11, v13);
    v16 = *(_QWORD *)(v14 + 19720);
    v17 = *(_QWORD *)(v14 + 19664);
    LOWORD(a1) = HIWORD(a1) & 0x7FFF;
    if ( ((HIWORD(a1) & 0x7FFF) == *(_WORD *)(v12 + 26)
       || (_WORD)a1 == 0x7FFF
       || !(_WORD)a1 && PsGetCurrentProcessWow64Process(v15))
      && (*(_BYTE *)(v12 + 25) & 1) == 0
      && *(_BYTE *)(v12 + 24) == 12 )
    {
      v3 = *(_QWORD *)(v17 + 40LL * (unsigned int)((v12 - v16) >> 5));
    }
  }
  if ( !v3 )
  {
    UserSetLastError(1461);
    goto LABEL_30;
  }
  v18 = *(_WORD **)(v3 + 88);
  if ( !v18 )
  {
LABEL_30:
    v19 = 0;
    goto LABEL_18;
  }
  v19 = 0;
  if ( (unsigned int)DrvGetHdevName(v18, v37) )
  {
    HIWORD(v38) = 0;
    v19 = 1;
    ProbeForWrite(a2, 0x40u, 4u);
    v18 = a2;
    v6 = 2147483646;
    v20 = (__int16 *)v37;
    v21 = 32;
    v22 = 0;
    v23 = 0;
    while ( v21 )
    {
      if ( !v6 )
        goto LABEL_16;
      v24 = *v20;
      if ( !*v20 )
        goto LABEL_16;
      ++v20;
      *v18++ = v24;
      --v21;
      --v6;
      ++v23;
    }
    --v18;
    v22 = -2147483643;
LABEL_16:
    *v18 = 0;
    if ( v22 < 0 )
      v19 = 0;
  }
LABEL_18:
  v25 = W32GetUserSessionState(v18, v6);
  v28 = v25;
  v29 = *(_DWORD *)(v25 + 68864);
  if ( v29 )
  {
    KeReleaseSemaphore(*(PRKSEMAPHORE *)(v25 + 68856), 0, v29, 0);
    *(_DWORD *)(v28 + 68864) = 0;
  }
  v30 = W32GetUserSessionState(v27, v26);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread(v31);
  if ( (CurrentThreadWin32Thread[6] & 0xC) == 8 )
  {
    UpdateDirtyVisRgnTrackers();
    *(_DWORD *)(v30 + 19620) = 0;
    *(_QWORD *)(v30 + 19600) = 0;
    DestroyExclusiveUserCritDeferredUnlockList();
    *(_QWORD *)(v30 + 16) = 0;
  }
  if ( *(_QWORD *)CurrentThreadWin32Thread && (CurrentThreadWin32Thread[6] & 2) == 0 )
    *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 0;
  Count = AtomicExecutionCheck::GetCount();
  if ( Count )
    KeBugCheckEx(0x160u, Count, 0, 0, 0);
  EtwTraceReleaseUserCrit();
  CurrentThreadWin32Thread[6] &= 0xFFFFFFF1;
  if ( (CurrentThreadWin32Thread[6] & 0x10) != 0 )
    PsSetThreadWin32Thread(KeGetCurrentThread(), 0, CurrentThreadWin32Thread);
  ExReleaseFastResource(*(_QWORD *)v30, CurrentThreadWin32Thread + 8);
  KeLeaveCriticalRegion();
  return v19;
}

```

## disassembly

```asm
0x140029370  mov     r11, rsp
0x140029373  mov     [r11+18h], rbx
0x140029377  push    rsi
0x140029378  push    rdi
0x140029379  push    r12
0x14002937b  push    r14
0x14002937d  push    r15
0x14002937f  sub     rsp, 0D0h
0x140029386  mov     rax, cs:__security_cookie
0x14002938d  xor     rax, rsp
0x140029390  mov     [rsp+0F8h+var_38], rax
0x140029398  mov     r14, rcx
0x14002939b  mov     [rsp+0F8h+Address], rdx
0x1400293a0  xorps   xmm0, xmm0
0x1400293a3  movups  xmmword ptr [r11-78h], xmm0
0x1400293a8  movups  xmmword ptr [r11-68h], xmm0
0x1400293ad  movups  xmmword ptr [r11-58h], xmm0
0x1400293b2  movups  xmmword ptr [r11-48h], xmm0
0x1400293b7  mov     edx, 1
0x1400293bc  lea     rcx, [r11-80h]
0x1400293c0  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x1400293c5  xor     edi, edi
0x1400293c7  mov     esi, edi
0x1400293c9  movzx   r15d, r14w
0x1400293cd  call    cs:__imp_W32GetUserSessionState
0x1400293d4  nop     dword ptr [rax+rax+00h]
0x1400293d9  mov     rcx, [rax+4CF8h]
0x1400293e0  cmp     r15, [rcx+8]
0x1400293e4  jnb     short loc_140029465
0x1400293e6  call    cs:__imp_W32GetUserSessionState
0x1400293ed  nop     dword ptr [rax+rax+00h]
0x1400293f2  mov     rbx, rax
0x1400293f5  call    cs:__imp_W32GetUserSessionState
0x1400293fc  nop     dword ptr [rax+rax+00h]
0x140029401  imul    r15d, [rax+4D10h]
0x140029409  mov     ecx, r15d
0x14002940c  mov     rbx, [rbx+4D08h]
0x140029413  add     rbx, rcx
0x140029416  call    cs:__imp_W32GetUserSessionState
0x14002941d  nop     dword ptr [rax+rax+00h]
0x140029422  mov     r15, [rax+4D08h]
0x140029429  mov     r12, [rax+4CD0h]
0x140029430  shr     r14, 10h
0x140029434  mov     eax, 7FFFh
0x140029439  and     r14w, ax
0x14002943d  cmp     r14w, [rbx+1Ah]
0x140029442  jnz     loc_140029694
0x140029448  test    byte ptr [rbx+19h], 1
0x14002944c  jnz     short loc_140029465
0x14002944e  cmp     byte ptr [rbx+18h], 0Ch
0x140029452  jnz     short loc_140029465
0x140029454  sub     rbx, r15
0x140029457  sar     rbx, 5
0x14002945b  mov     eax, ebx
0x14002945d  lea     rcx, [rax+rax*4]
0x140029461  mov     rsi, [r12+rcx*8]
0x140029465  test    rsi, rsi
0x140029468  jz      loc_140029682
0x14002946e  mov     rcx, [rsi+58h]
0x140029472  test    rcx, rcx
0x140029475  jz      loc_14002968C
0x14002947b  mov     r14d, edi
0x14002947e  lea     rdx, [rsp+0F8h+var_78]
0x140029486  call    DrvGetHdevName
0x14002948b  test    eax, eax
0x14002948d  jz      loc_140029580
0x140029493  mov     [rsp+0F8h+var_3A], di
0x14002949b  mov     r14d, 1
0x1400294a1  mov     edx, 40h ; '@'; Length
0x1400294a6  mov     r8d, 4; Alignment
0x1400294ac  mov     rcx, [rsp+0F8h+Address]; Address
0x1400294b1  call    cs:__imp_ProbeForWrite
0x1400294b8  nop     dword ptr [rax+rax+00h]
0x1400294bd  mov     rcx, [rsp+0F8h+Address]
0x1400294c2  mov     [rsp+0F8h+var_C8], edi
0x1400294c6  mov     [rsp+0F8h+var_C8], edi
0x1400294ca  mov     edx, 7FFFFFFEh
0x1400294cf  mov     [rsp+0F8h+var_88], rdx
0x1400294d4  lea     r8, [rsp+0F8h+var_78]
0x1400294dc  mov     [rsp+0F8h+var_98], r8
0x1400294e1  mov     eax, 20h ; ' '
0x1400294e6  mov     [rsp+0F8h+var_90], rax
0x1400294eb  mov     [rsp+0F8h+var_A8], rcx
0x1400294f0  mov     r11d, edi
0x1400294f3  mov     r10, rdi
0x1400294f6  mov     [rsp+0F8h+var_A0], rdi
0x1400294fb  nop     dword ptr [rax+rax+00h]
0x140029500  test    rax, rax
0x140029503  jz      short loc_140029549
0x140029505  test    rdx, rdx
0x140029508  jz      short loc_140029544
0x14002950a  movzx   r9d, word ptr [r8]
0x14002950e  test    r9w, r9w
0x140029512  jz      short loc_140029544
0x140029514  add     r8, 2
0x140029518  mov     [rsp+0F8h+var_98], r8
0x14002951d  mov     [rcx], r9w
0x140029521  add     rcx, 2
0x140029525  mov     [rsp+0F8h+var_A8], rcx
0x14002952a  dec     rax
0x14002952d  mov     [rsp+0F8h+var_90], rax
0x140029532  dec     rdx
0x140029535  mov     [rsp+0F8h+var_88], rdx
0x14002953a  inc     r10
0x14002953d  mov     [rsp+0F8h+var_A0], r10
0x140029542  jmp     short loc_140029500
0x140029544  test    rax, rax
0x140029547  jnz     short loc_140029560
0x140029549  sub     rcx, 2
0x14002954d  mov     [rsp+0F8h+var_A8], rcx
0x140029552  dec     r10
0x140029555  mov     [rsp+0F8h+var_A0], r10
0x14002955a  mov     r11d, 80000005h
0x140029560  mov     [rcx], di
0x140029563  mov     [rsp+0F8h+var_C8], r11d
0x140029568  test    r11d, r11d
0x14002956b  cmovs   r14d, edi
0x14002956f  mov     [rsp+0F8h+var_B4], r14d
0x140029574  jmp     short loc_140029580
0x140029576  xor     r14d, r14d
0x140029579  mov     [rsp+0F8h+var_B4], r14d
0x14002957e  xor     edi, edi
0x140029580  call    cs:__imp_W32GetUserSessionState
0x140029587  nop     dword ptr [rax+rax+00h]
0x14002958c  mov     rbx, rax
0x14002958f  mov     r8d, [rax+10D00h]; Adjustment
0x140029596  test    r8d, r8d
0x140029599  jz      short loc_1400295B9
0x14002959b  xor     r9d, r9d; Wait
0x14002959e  xor     edx, edx; Increment
0x1400295a0  mov     rcx, [rax+10CF8h]; Semaphore
0x1400295a7  call    cs:__imp_KeReleaseSemaphore
0x1400295ae  nop     dword ptr [rax+rax+00h]
0x1400295b3  mov     [rbx+10D00h], edi
0x1400295b9  call    cs:__imp_W32GetUserSessionState
0x1400295c0  nop     dword ptr [rax+rax+00h]
0x1400295c5  mov     rsi, rax
0x1400295c8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400295cf  nop     dword ptr [rax+rax+00h]
0x1400295d4  mov     rbx, rax
0x1400295d7  mov     ecx, [rax+18h]
0x1400295da  and     cl, 0Ch
0x1400295dd  cmp     cl, 8
0x1400295e0  jnz     short loc_1400295FE
0x1400295e2  call    UpdateDirtyVisRgnTrackers
0x1400295e7  lea     rcx, [rsi+4C40h]
0x1400295ee  mov     [rcx+64h], edi
0x1400295f1  mov     [rcx+50h], rdi
0x1400295f5  call    DestroyExclusiveUserCritDeferredUnlockList
0x1400295fa  mov     [rsi+10h], rdi
0x1400295fe  mov     rcx, [rbx]
0x140029601  test    rcx, rcx
0x140029604  jnz     short loc_140029672
0x140029606  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x14002960b  test    eax, eax
0x14002960d  jnz     loc_1400296C2
0x140029613  call    EtwTraceReleaseUserCrit
0x140029618  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x14002961c  mov     eax, [rbx+18h]
0x14002961f  test    al, 10h
0x140029621  jnz     loc_1400296E1
0x140029627  lea     rdx, [rbx+20h]
0x14002962b  mov     rcx, [rsi]
0x14002962e  call    cs:__imp_ExReleaseFastResource
0x140029635  nop     dword ptr [rax+rax+00h]
0x14002963a  call    cs:__imp_KeLeaveCriticalRegion
0x140029641  nop     dword ptr [rax+rax+00h]
0x140029646  movsxd  rax, r14d
0x140029649  mov     rcx, [rsp+0F8h+var_38]
0x140029651  xor     rcx, rsp; StackCookie
0x140029654  call    __security_check_cookie
0x140029659  mov     rbx, [rsp+0F8h+arg_10]
0x140029661  add     rsp, 0D0h
0x140029668  pop     r15
0x14002966a  pop     r14
0x14002966c  pop     r12
0x14002966e  pop     rdi
0x14002966f  pop     rsi
0x140029670  retn
0x140029672  mov     eax, [rbx+18h]
0x140029675  test    al, 2
0x140029677  jnz     short loc_140029606
0x140029679  mov     byte ptr [rcx+6ACh], 0
0x140029680  jmp     short loc_140029606
0x140029682  mov     ecx, 5B5h
0x140029687  call    UserSetLastError
0x14002968c  mov     r14d, edi
0x14002968f  jmp     loc_140029580
0x140029694  cmp     r14w, ax
0x140029698  jz      loc_140029448
0x14002969e  test    r14w, r14w
0x1400296a2  jnz     loc_140029465
0x1400296a8  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400296af  nop     dword ptr [rax+rax+00h]
0x1400296b4  test    rax, rax
0x1400296b7  jz      loc_140029465
0x1400296bd  jmp     loc_140029448
0x1400296c2  mov     edx, eax; BugCheckParameter1
0x1400296c4  mov     [rsp+0F8h+BugCheckParameter4], rdi; BugCheckParameter4
0x1400296c9  xor     r9d, r9d; BugCheckParameter3
0x1400296cc  xor     r8d, r8d; BugCheckParameter2
0x1400296cf  mov     ecx, 160h; BugCheckCode
0x1400296d4  call    cs:__imp_KeBugCheckEx
0x1400296e1  mov     rcx, gs:188h
0x1400296ea  mov     r8, rbx
0x1400296ed  xor     edx, edx
0x1400296ef  call    cs:__imp_PsSetThreadWin32Thread
0x1400296f6  nop     dword ptr [rax+rax+00h]
0x1400296fb  jmp     loc_140029627
0x140239320  push    rbp
0x140239322  sub     rsp, 30h
0x140239326  mov     rbp, rdx
0x140239329  mov     rax, [rcx]
0x14023932c  mov     ecx, [rax]
0x14023932e  mov     [rbp+38h], ecx
0x140239331  mov     ecx, [rbp+38h]; Status
0x140239334  call    cs:__imp_RtlNtStatusToDosError
0x14023933b  nop     dword ptr [rax+rax+00h]
0x140239340  mov     ecx, eax
0x140239342  call    UserSetLastError
0x140239347  mov     dword ptr [rbp+40h], 1
0x14023934e  mov     eax, [rbp+40h]
0x140239351  add     rsp, 30h
0x140239355  pop     rbp
0x140239356  retn
```
