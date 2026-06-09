# NtUserGetHDevName

- ea: `0x14001ba50`
- end: `0x14001bde0`
- name: `NtUserGetHDevName`
- size: `912`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14001ba50`
- `0x14001bf30`
- `0x14001bf60`
- `0x14001c110`
- `0x14001c2a0`
- `0x14001c2d4`
- `0x14001c350`
- `0x140033268`
- `0x140238160`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001bdb4`
- `ntoskrnl!KeBugCheckEx` at `0x14001bdb4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bd1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bd1a`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001bdcf`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001bdcf`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001bc87`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001bc87`
- `ntoskrnl!ProbeForWrite` at `0x14001bb91`
- `ntoskrnl!ProbeForWrite` at `0x14001bb91`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14001bd88`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14001bd88`
- `ntoskrnl!ExReleaseFastResource` at `0x14001bd0e`
- `ntoskrnl!ExReleaseFastResource` at `0x14001bd0e`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140238bb4`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140238bb4`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001bca8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001bca8`
- `WIN32K!W32GetUserSessionState` at `0x14001baad`
- `WIN32K!W32GetUserSessionState` at `0x14001bac6`
- `WIN32K!W32GetUserSessionState` at `0x14001bad5`
- `WIN32K!W32GetUserSessionState` at `0x14001baf6`
- `WIN32K!W32GetUserSessionState` at `0x14001bc60`
- `WIN32K!W32GetUserSessionState` at `0x14001bc99`
- `WIN32K!W32GetUserSessionState` at `0x14001baad`
- `WIN32K!W32GetUserSessionState` at `0x14001bac6`
- `WIN32K!W32GetUserSessionState` at `0x14001bad5`
- `WIN32K!W32GetUserSessionState` at `0x14001baf6`
- `WIN32K!W32GetUserSessionState` at `0x14001bc60`
- `WIN32K!W32GetUserSessionState` at `0x14001bc99`

## pseudocode

```c
__int64 __fastcall NtUserGetHDevName(int a1, volatile void *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int16 *v9; // r8
  __int64 UserSessionState; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // r15
  __int64 v20; // r12
  _WORD *v21; // rcx
  int v22; // r14d
  __int64 v23; // rax
  int v24; // r11d
  __int64 v25; // r10
  __int16 v26; // r9
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // r8
  __int64 v32; // rsi
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax
  __int64 v37; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v38[48]; // [rsp+80h] [rbp-78h] BYREF
  __int128 v39; // [rsp+B0h] [rbp-48h]

  memset(v38, 0, sizeof(v38));
  v39 = 0;
  EnterLeaveCritShared::EnterLeaveCritShared(&v37, 1);
  v3 = 0;
  v8 = *(_QWORD *)(W32GetUserSessionState(v5, v4, v6) + 19704);
  if ( (unsigned __int64)(unsigned __int16)a1 < *(_QWORD *)(v8 + 8) )
  {
    UserSessionState = W32GetUserSessionState(v8, v7, v9);
    v14 = *(_DWORD *)(W32GetUserSessionState(v12, v11, v13) + 19728) * (unsigned int)(unsigned __int16)a1;
    v15 = v14 + *(_QWORD *)(UserSessionState + 19720);
    v18 = W32GetUserSessionState(v14, v16, v17);
    v19 = *(_QWORD *)(v18 + 19720);
    v20 = *(_QWORD *)(v18 + 19664);
    LOWORD(a1) = HIWORD(a1) & 0x7FFF;
    if ( ((HIWORD(a1) & 0x7FFF) == *(_WORD *)(v15 + 26)
       || (_WORD)a1 == 0x7FFF
       || !(_WORD)a1 && PsGetCurrentProcessWow64Process())
      && (*(_BYTE *)(v15 + 25) & 1) == 0
      && *(_BYTE *)(v15 + 24) == 12 )
    {
      v3 = *(_QWORD *)(v20 + 40LL * (unsigned int)((v15 - v19) >> 5));
    }
  }
  if ( !v3 )
  {
    UserSetLastError(1461);
    goto LABEL_30;
  }
  v21 = *(_WORD **)(v3 + 88);
  if ( !v21 )
  {
LABEL_30:
    v22 = 0;
    goto LABEL_18;
  }
  v22 = 0;
  if ( (unsigned int)DrvGetHdevName(v21, v38) )
  {
    HIWORD(v39) = 0;
    v22 = 1;
    ProbeForWrite(a2, 0x40u, 4u);
    v21 = a2;
    v7 = 2147483646;
    v9 = (__int16 *)v38;
    v23 = 32;
    v24 = 0;
    v25 = 0;
    while ( v23 )
    {
      if ( !v7 )
        goto LABEL_16;
      v26 = *v9;
      if ( !*v9 )
        goto LABEL_16;
      ++v9;
      *v21++ = v26;
      --v23;
      --v7;
      ++v25;
    }
    --v21;
    v24 = -2147483643;
LABEL_16:
    *v21 = 0;
    if ( v24 < 0 )
      v22 = 0;
  }
LABEL_18:
  v27 = W32GetUserSessionState(v21, v7, v9);
  v30 = v27;
  v31 = *(unsigned int *)(v27 + 68864);
  if ( (_DWORD)v31 )
  {
    KeReleaseSemaphore(*(PRKSEMAPHORE *)(v27 + 68856), 0, v31, 0);
    *(_DWORD *)(v30 + 68864) = 0;
  }
  v32 = W32GetUserSessionState(v29, v28, v31);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread();
  if ( (CurrentThreadWin32Thread[6] & 0xC) == 8 )
  {
    UpdateDirtyVisRgnTrackers();
    *(_DWORD *)(v32 + 19620) = 0;
    *(_QWORD *)(v32 + 19600) = 0;
    DestroyExclusiveUserCritDeferredUnlockList();
    *(_QWORD *)(v32 + 16) = 0;
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
  ExReleaseFastResource(*(_QWORD *)v32, CurrentThreadWin32Thread + 8);
  KeLeaveCriticalRegion();
  return v22;
}

```

## disassembly

```asm
0x14001ba50  mov     r11, rsp
0x14001ba53  mov     [r11+18h], rbx
0x14001ba57  push    rsi
0x14001ba58  push    rdi
0x14001ba59  push    r12
0x14001ba5b  push    r14
0x14001ba5d  push    r15
0x14001ba5f  sub     rsp, 0D0h
0x14001ba66  mov     rax, cs:__security_cookie
0x14001ba6d  xor     rax, rsp
0x14001ba70  mov     [rsp+0F8h+var_38], rax
0x14001ba78  mov     r14, rcx
0x14001ba7b  mov     [rsp+0F8h+Address], rdx
0x14001ba80  xorps   xmm0, xmm0
0x14001ba83  movups  xmmword ptr [r11-78h], xmm0
0x14001ba88  movups  xmmword ptr [r11-68h], xmm0
0x14001ba8d  movups  xmmword ptr [r11-58h], xmm0
0x14001ba92  movups  xmmword ptr [r11-48h], xmm0
0x14001ba97  mov     edx, 1
0x14001ba9c  lea     rcx, [r11-80h]
0x14001baa0  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x14001baa5  xor     edi, edi
0x14001baa7  mov     esi, edi
0x14001baa9  movzx   r15d, r14w
0x14001baad  call    cs:__imp_W32GetUserSessionState
0x14001bab4  nop     dword ptr [rax+rax+00h]
0x14001bab9  mov     rcx, [rax+4CF8h]
0x14001bac0  cmp     r15, [rcx+8]
0x14001bac4  jnb     short loc_14001BB45
0x14001bac6  call    cs:__imp_W32GetUserSessionState
0x14001bacd  nop     dword ptr [rax+rax+00h]
0x14001bad2  mov     rbx, rax
0x14001bad5  call    cs:__imp_W32GetUserSessionState
0x14001badc  nop     dword ptr [rax+rax+00h]
0x14001bae1  imul    r15d, [rax+4D10h]
0x14001bae9  mov     ecx, r15d
0x14001baec  mov     rbx, [rbx+4D08h]
0x14001baf3  add     rbx, rcx
0x14001baf6  call    cs:__imp_W32GetUserSessionState
0x14001bafd  nop     dword ptr [rax+rax+00h]
0x14001bb02  mov     r15, [rax+4D08h]
0x14001bb09  mov     r12, [rax+4CD0h]
0x14001bb10  shr     r14, 10h
0x14001bb14  mov     eax, 7FFFh
0x14001bb19  and     r14w, ax
0x14001bb1d  cmp     r14w, [rbx+1Ah]
0x14001bb22  jnz     loc_14001BD74
0x14001bb28  test    byte ptr [rbx+19h], 1
0x14001bb2c  jnz     short loc_14001BB45
0x14001bb2e  cmp     byte ptr [rbx+18h], 0Ch
0x14001bb32  jnz     short loc_14001BB45
0x14001bb34  sub     rbx, r15
0x14001bb37  sar     rbx, 5
0x14001bb3b  mov     eax, ebx
0x14001bb3d  lea     rcx, [rax+rax*4]
0x14001bb41  mov     rsi, [r12+rcx*8]
0x14001bb45  test    rsi, rsi
0x14001bb48  jz      loc_14001BD62
0x14001bb4e  mov     rcx, [rsi+58h]
0x14001bb52  test    rcx, rcx
0x14001bb55  jz      loc_14001BD6C
0x14001bb5b  mov     r14d, edi
0x14001bb5e  lea     rdx, [rsp+0F8h+var_78]
0x14001bb66  call    DrvGetHdevName
0x14001bb6b  test    eax, eax
0x14001bb6d  jz      loc_14001BC60
0x14001bb73  mov     [rsp+0F8h+var_3A], di
0x14001bb7b  mov     r14d, 1
0x14001bb81  mov     edx, 40h ; '@'; Length
0x14001bb86  mov     r8d, 4; Alignment
0x14001bb8c  mov     rcx, [rsp+0F8h+Address]; Address
0x14001bb91  call    cs:__imp_ProbeForWrite
0x14001bb98  nop     dword ptr [rax+rax+00h]
0x14001bb9d  mov     rcx, [rsp+0F8h+Address]
0x14001bba2  mov     [rsp+0F8h+var_C8], edi
0x14001bba6  mov     [rsp+0F8h+var_C8], edi
0x14001bbaa  mov     edx, 7FFFFFFEh
0x14001bbaf  mov     [rsp+0F8h+var_88], rdx
0x14001bbb4  lea     r8, [rsp+0F8h+var_78]
0x14001bbbc  mov     [rsp+0F8h+var_98], r8
0x14001bbc1  mov     eax, 20h ; ' '
0x14001bbc6  mov     [rsp+0F8h+var_90], rax
0x14001bbcb  mov     [rsp+0F8h+var_A8], rcx
0x14001bbd0  mov     r11d, edi
0x14001bbd3  mov     r10, rdi
0x14001bbd6  mov     [rsp+0F8h+var_A0], rdi
0x14001bbdb  nop     dword ptr [rax+rax+00h]
0x14001bbe0  test    rax, rax
0x14001bbe3  jz      short loc_14001BC29
0x14001bbe5  test    rdx, rdx
0x14001bbe8  jz      short loc_14001BC24
0x14001bbea  movzx   r9d, word ptr [r8]
0x14001bbee  test    r9w, r9w
0x14001bbf2  jz      short loc_14001BC24
0x14001bbf4  add     r8, 2
0x14001bbf8  mov     [rsp+0F8h+var_98], r8
0x14001bbfd  mov     [rcx], r9w
0x14001bc01  add     rcx, 2
0x14001bc05  mov     [rsp+0F8h+var_A8], rcx
0x14001bc0a  dec     rax
0x14001bc0d  mov     [rsp+0F8h+var_90], rax
0x14001bc12  dec     rdx
0x14001bc15  mov     [rsp+0F8h+var_88], rdx
0x14001bc1a  inc     r10
0x14001bc1d  mov     [rsp+0F8h+var_A0], r10
0x14001bc22  jmp     short loc_14001BBE0
0x14001bc24  test    rax, rax
0x14001bc27  jnz     short loc_14001BC40
0x14001bc29  sub     rcx, 2
0x14001bc2d  mov     [rsp+0F8h+var_A8], rcx
0x14001bc32  dec     r10
0x14001bc35  mov     [rsp+0F8h+var_A0], r10
0x14001bc3a  mov     r11d, 80000005h
0x14001bc40  mov     [rcx], di
0x14001bc43  mov     [rsp+0F8h+var_C8], r11d
0x14001bc48  test    r11d, r11d
0x14001bc4b  cmovs   r14d, edi
0x14001bc4f  mov     [rsp+0F8h+var_B4], r14d
0x14001bc54  jmp     short loc_14001BC60
0x14001bc56  xor     r14d, r14d
0x14001bc59  mov     [rsp+0F8h+var_B4], r14d
0x14001bc5e  xor     edi, edi
0x14001bc60  call    cs:__imp_W32GetUserSessionState
0x14001bc67  nop     dword ptr [rax+rax+00h]
0x14001bc6c  mov     rbx, rax
0x14001bc6f  mov     r8d, [rax+10D00h]; Adjustment
0x14001bc76  test    r8d, r8d
0x14001bc79  jz      short loc_14001BC99
0x14001bc7b  xor     r9d, r9d; Wait
0x14001bc7e  xor     edx, edx; Increment
0x14001bc80  mov     rcx, [rax+10CF8h]; Semaphore
0x14001bc87  call    cs:__imp_KeReleaseSemaphore
0x14001bc8e  nop     dword ptr [rax+rax+00h]
0x14001bc93  mov     [rbx+10D00h], edi
0x14001bc99  call    cs:__imp_W32GetUserSessionState
0x14001bca0  nop     dword ptr [rax+rax+00h]
0x14001bca5  mov     rsi, rax
0x14001bca8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001bcaf  nop     dword ptr [rax+rax+00h]
0x14001bcb4  mov     rbx, rax
0x14001bcb7  mov     ecx, [rax+18h]
0x14001bcba  and     cl, 0Ch
0x14001bcbd  cmp     cl, 8
0x14001bcc0  jnz     short loc_14001BCDE
0x14001bcc2  call    UpdateDirtyVisRgnTrackers
0x14001bcc7  lea     rcx, [rsi+4C40h]
0x14001bcce  mov     [rcx+64h], edi
0x14001bcd1  mov     [rcx+50h], rdi
0x14001bcd5  call    DestroyExclusiveUserCritDeferredUnlockList
0x14001bcda  mov     [rsi+10h], rdi
0x14001bcde  mov     rcx, [rbx]
0x14001bce1  test    rcx, rcx
0x14001bce4  jnz     short loc_14001BD52
0x14001bce6  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x14001bceb  test    eax, eax
0x14001bced  jnz     loc_14001BDA2
0x14001bcf3  call    EtwTraceReleaseUserCrit
0x14001bcf8  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x14001bcfc  mov     eax, [rbx+18h]
0x14001bcff  test    al, 10h
0x14001bd01  jnz     loc_14001BDC1
0x14001bd07  lea     rdx, [rbx+20h]
0x14001bd0b  mov     rcx, [rsi]
0x14001bd0e  call    cs:__imp_ExReleaseFastResource
0x14001bd15  nop     dword ptr [rax+rax+00h]
0x14001bd1a  call    cs:__imp_KeLeaveCriticalRegion
0x14001bd21  nop     dword ptr [rax+rax+00h]
0x14001bd26  movsxd  rax, r14d
0x14001bd29  mov     rcx, [rsp+0F8h+var_38]
0x14001bd31  xor     rcx, rsp; StackCookie
0x14001bd34  call    __security_check_cookie
0x14001bd39  mov     rbx, [rsp+0F8h+arg_10]
0x14001bd41  add     rsp, 0D0h
0x14001bd48  pop     r15
0x14001bd4a  pop     r14
0x14001bd4c  pop     r12
0x14001bd4e  pop     rdi
0x14001bd4f  pop     rsi
0x14001bd50  retn
0x14001bd52  mov     eax, [rbx+18h]
0x14001bd55  test    al, 2
0x14001bd57  jnz     short loc_14001BCE6
0x14001bd59  mov     byte ptr [rcx+6ACh], 0
0x14001bd60  jmp     short loc_14001BCE6
0x14001bd62  mov     ecx, 5B5h
0x14001bd67  call    UserSetLastError
0x14001bd6c  mov     r14d, edi
0x14001bd6f  jmp     loc_14001BC60
0x14001bd74  cmp     r14w, ax
0x14001bd78  jz      loc_14001BB28
0x14001bd7e  test    r14w, r14w
0x14001bd82  jnz     loc_14001BB45
0x14001bd88  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14001bd8f  nop     dword ptr [rax+rax+00h]
0x14001bd94  test    rax, rax
0x14001bd97  jz      loc_14001BB45
0x14001bd9d  jmp     loc_14001BB28
0x14001bda2  mov     edx, eax; BugCheckParameter1
0x14001bda4  mov     [rsp+0F8h+BugCheckParameter4], rdi; BugCheckParameter4
0x14001bda9  xor     r9d, r9d; BugCheckParameter3
0x14001bdac  xor     r8d, r8d; BugCheckParameter2
0x14001bdaf  mov     ecx, 160h; BugCheckCode
0x14001bdb4  call    cs:__imp_KeBugCheckEx
0x14001bdc1  mov     rcx, gs:188h
0x14001bdca  mov     r8, rbx
0x14001bdcd  xor     edx, edx
0x14001bdcf  call    cs:__imp_PsSetThreadWin32Thread
0x14001bdd6  nop     dword ptr [rax+rax+00h]
0x14001bddb  jmp     loc_14001BD07
0x140238ba0  push    rbp
0x140238ba2  sub     rsp, 30h
0x140238ba6  mov     rbp, rdx
0x140238ba9  mov     rax, [rcx]
0x140238bac  mov     ecx, [rax]
0x140238bae  mov     [rbp+38h], ecx
0x140238bb1  mov     ecx, [rbp+38h]; Status
0x140238bb4  call    cs:__imp_RtlNtStatusToDosError
0x140238bbb  nop     dword ptr [rax+rax+00h]
0x140238bc0  mov     ecx, eax
0x140238bc2  call    UserSetLastError
0x140238bc7  mov     dword ptr [rbp+40h], 1
0x140238bce  mov     eax, [rbp+40h]
0x140238bd1  add     rsp, 30h
0x140238bd5  pop     rbp
0x140238bd6  retn
```
