# NtUserGetHDevName

- ea: `0x1400128e0`
- end: `0x140012c70`
- name: `NtUserGetHDevName`
- size: `912`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400128e0`
- `0x140012dc0`
- `0x140012df0`
- `0x140012fa0`
- `0x140013130`
- `0x140013164`
- `0x1400131e0`
- `0x140029fe8`
- `0x140238b10`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140012c44`
- `ntoskrnl!KeBugCheckEx` at `0x140012c44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012baa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012baa`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012c5f`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012c5f`
- `ntoskrnl!KeReleaseSemaphore` at `0x140012b17`
- `ntoskrnl!KeReleaseSemaphore` at `0x140012b17`
- `ntoskrnl!ProbeForWrite` at `0x140012a21`
- `ntoskrnl!ProbeForWrite` at `0x140012a21`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140012c18`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140012c18`
- `ntoskrnl!ExReleaseFastResource` at `0x140012b9e`
- `ntoskrnl!ExReleaseFastResource` at `0x140012b9e`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140239534`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140239534`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012b38`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012b38`
- `WIN32K!W32GetUserSessionState` at `0x14001293d`
- `WIN32K!W32GetUserSessionState` at `0x140012956`
- `WIN32K!W32GetUserSessionState` at `0x140012965`
- `WIN32K!W32GetUserSessionState` at `0x140012986`
- `WIN32K!W32GetUserSessionState` at `0x140012af0`
- `WIN32K!W32GetUserSessionState` at `0x140012b29`
- `WIN32K!W32GetUserSessionState` at `0x14001293d`
- `WIN32K!W32GetUserSessionState` at `0x140012956`
- `WIN32K!W32GetUserSessionState` at `0x140012965`
- `WIN32K!W32GetUserSessionState` at `0x140012986`
- `WIN32K!W32GetUserSessionState` at `0x140012af0`
- `WIN32K!W32GetUserSessionState` at `0x140012b29`

## pseudocode

```c
__int64 __fastcall NtUserGetHDevName(int a1, volatile void *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 UserSessionState; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r15
  __int64 v12; // r12
  _WORD *v13; // rcx
  int v14; // r14d
  __int64 v15; // rdx
  __int16 *v16; // r8
  __int64 v17; // rax
  int v18; // r11d
  __int64 v19; // r10
  __int16 v20; // r9
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rbx
  LONG v24; // r8d
  __int64 v25; // rsi
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax
  __int64 v30; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v31[48]; // [rsp+80h] [rbp-78h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-48h]

  memset(v31, 0, sizeof(v31));
  v32 = 0;
  EnterLeaveCritShared::EnterLeaveCritShared(&v30, 1);
  v3 = 0;
  v5 = *(_QWORD *)(W32GetUserSessionState(v4) + 19704);
  if ( (unsigned __int64)(unsigned __int16)a1 < *(_QWORD *)(v5 + 8) )
  {
    UserSessionState = W32GetUserSessionState(v5);
    v8 = *(_DWORD *)(W32GetUserSessionState(v7) + 19728) * (unsigned int)(unsigned __int16)a1;
    v9 = v8 + *(_QWORD *)(UserSessionState + 19720);
    v10 = W32GetUserSessionState(v8);
    v11 = *(_QWORD *)(v10 + 19720);
    v12 = *(_QWORD *)(v10 + 19664);
    LOWORD(a1) = HIWORD(a1) & 0x7FFF;
    if ( ((HIWORD(a1) & 0x7FFF) == *(_WORD *)(v9 + 26)
       || (_WORD)a1 == 0x7FFF
       || !(_WORD)a1 && PsGetCurrentProcessWow64Process())
      && (*(_BYTE *)(v9 + 25) & 1) == 0
      && *(_BYTE *)(v9 + 24) == 12 )
    {
      v3 = *(_QWORD *)(v12 + 40LL * (unsigned int)((v9 - v11) >> 5));
    }
  }
  if ( !v3 )
  {
    UserSetLastError(1461);
    goto LABEL_30;
  }
  v13 = *(_WORD **)(v3 + 88);
  if ( !v13 )
  {
LABEL_30:
    v14 = 0;
    goto LABEL_18;
  }
  v14 = 0;
  if ( (unsigned int)DrvGetHdevName(v13, v31) )
  {
    HIWORD(v32) = 0;
    v14 = 1;
    ProbeForWrite(a2, 0x40u, 4u);
    v13 = a2;
    v15 = 2147483646;
    v16 = (__int16 *)v31;
    v17 = 32;
    v18 = 0;
    v19 = 0;
    while ( v17 )
    {
      if ( !v15 )
        goto LABEL_16;
      v20 = *v16;
      if ( !*v16 )
        goto LABEL_16;
      ++v16;
      *v13++ = v20;
      --v17;
      --v15;
      ++v19;
    }
    --v13;
    v18 = -2147483643;
LABEL_16:
    *v13 = 0;
    if ( v18 < 0 )
      v14 = 0;
  }
LABEL_18:
  v21 = W32GetUserSessionState(v13);
  v23 = v21;
  v24 = *(_DWORD *)(v21 + 68864);
  if ( v24 )
  {
    KeReleaseSemaphore(*(PRKSEMAPHORE *)(v21 + 68856), 0, v24, 0);
    *(_DWORD *)(v23 + 68864) = 0;
  }
  v25 = W32GetUserSessionState(v22);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread();
  if ( (CurrentThreadWin32Thread[6] & 0xC) == 8 )
  {
    UpdateDirtyVisRgnTrackers();
    *(_DWORD *)(v25 + 19620) = 0;
    *(_QWORD *)(v25 + 19600) = 0;
    DestroyExclusiveUserCritDeferredUnlockList();
    *(_QWORD *)(v25 + 16) = 0;
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
  ExReleaseFastResource(*(_QWORD *)v25, CurrentThreadWin32Thread + 8);
  KeLeaveCriticalRegion();
  return v14;
}

```

## disassembly

```asm
0x1400128e0  mov     r11, rsp
0x1400128e3  mov     [r11+18h], rbx
0x1400128e7  push    rsi
0x1400128e8  push    rdi
0x1400128e9  push    r12
0x1400128eb  push    r14
0x1400128ed  push    r15
0x1400128ef  sub     rsp, 0D0h
0x1400128f6  mov     rax, cs:__security_cookie
0x1400128fd  xor     rax, rsp
0x140012900  mov     [rsp+0F8h+var_38], rax
0x140012908  mov     r14, rcx
0x14001290b  mov     [rsp+0F8h+Address], rdx
0x140012910  xorps   xmm0, xmm0
0x140012913  movups  xmmword ptr [r11-78h], xmm0
0x140012918  movups  xmmword ptr [r11-68h], xmm0
0x14001291d  movups  xmmword ptr [r11-58h], xmm0
0x140012922  movups  xmmword ptr [r11-48h], xmm0
0x140012927  mov     edx, 1
0x14001292c  lea     rcx, [r11-80h]
0x140012930  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x140012935  xor     edi, edi
0x140012937  mov     esi, edi
0x140012939  movzx   r15d, r14w
0x14001293d  call    cs:__imp_W32GetUserSessionState
0x140012944  nop     dword ptr [rax+rax+00h]
0x140012949  mov     rcx, [rax+4CF8h]
0x140012950  cmp     r15, [rcx+8]
0x140012954  jnb     short loc_1400129D5
0x140012956  call    cs:__imp_W32GetUserSessionState
0x14001295d  nop     dword ptr [rax+rax+00h]
0x140012962  mov     rbx, rax
0x140012965  call    cs:__imp_W32GetUserSessionState
0x14001296c  nop     dword ptr [rax+rax+00h]
0x140012971  imul    r15d, [rax+4D10h]
0x140012979  mov     ecx, r15d
0x14001297c  mov     rbx, [rbx+4D08h]
0x140012983  add     rbx, rcx
0x140012986  call    cs:__imp_W32GetUserSessionState
0x14001298d  nop     dword ptr [rax+rax+00h]
0x140012992  mov     r15, [rax+4D08h]
0x140012999  mov     r12, [rax+4CD0h]
0x1400129a0  shr     r14, 10h
0x1400129a4  mov     eax, 7FFFh
0x1400129a9  and     r14w, ax
0x1400129ad  cmp     r14w, [rbx+1Ah]
0x1400129b2  jnz     loc_140012C04
0x1400129b8  test    byte ptr [rbx+19h], 1
0x1400129bc  jnz     short loc_1400129D5
0x1400129be  cmp     byte ptr [rbx+18h], 0Ch
0x1400129c2  jnz     short loc_1400129D5
0x1400129c4  sub     rbx, r15
0x1400129c7  sar     rbx, 5
0x1400129cb  mov     eax, ebx
0x1400129cd  lea     rcx, [rax+rax*4]
0x1400129d1  mov     rsi, [r12+rcx*8]
0x1400129d5  test    rsi, rsi
0x1400129d8  jz      loc_140012BF2
0x1400129de  mov     rcx, [rsi+58h]
0x1400129e2  test    rcx, rcx
0x1400129e5  jz      loc_140012BFC
0x1400129eb  mov     r14d, edi
0x1400129ee  lea     rdx, [rsp+0F8h+var_78]
0x1400129f6  call    DrvGetHdevName
0x1400129fb  test    eax, eax
0x1400129fd  jz      loc_140012AF0
0x140012a03  mov     [rsp+0F8h+var_3A], di
0x140012a0b  mov     r14d, 1
0x140012a11  mov     edx, 40h ; '@'; Length
0x140012a16  mov     r8d, 4; Alignment
0x140012a1c  mov     rcx, [rsp+0F8h+Address]; Address
0x140012a21  call    cs:__imp_ProbeForWrite
0x140012a28  nop     dword ptr [rax+rax+00h]
0x140012a2d  mov     rcx, [rsp+0F8h+Address]
0x140012a32  mov     [rsp+0F8h+var_C8], edi
0x140012a36  mov     [rsp+0F8h+var_C8], edi
0x140012a3a  mov     edx, 7FFFFFFEh
0x140012a3f  mov     [rsp+0F8h+var_88], rdx
0x140012a44  lea     r8, [rsp+0F8h+var_78]
0x140012a4c  mov     [rsp+0F8h+var_98], r8
0x140012a51  mov     eax, 20h ; ' '
0x140012a56  mov     [rsp+0F8h+var_90], rax
0x140012a5b  mov     [rsp+0F8h+var_A8], rcx
0x140012a60  mov     r11d, edi
0x140012a63  mov     r10, rdi
0x140012a66  mov     [rsp+0F8h+var_A0], rdi
0x140012a6b  nop     dword ptr [rax+rax+00h]
0x140012a70  test    rax, rax
0x140012a73  jz      short loc_140012AB9
0x140012a75  test    rdx, rdx
0x140012a78  jz      short loc_140012AB4
0x140012a7a  movzx   r9d, word ptr [r8]
0x140012a7e  test    r9w, r9w
0x140012a82  jz      short loc_140012AB4
0x140012a84  add     r8, 2
0x140012a88  mov     [rsp+0F8h+var_98], r8
0x140012a8d  mov     [rcx], r9w
0x140012a91  add     rcx, 2
0x140012a95  mov     [rsp+0F8h+var_A8], rcx
0x140012a9a  dec     rax
0x140012a9d  mov     [rsp+0F8h+var_90], rax
0x140012aa2  dec     rdx
0x140012aa5  mov     [rsp+0F8h+var_88], rdx
0x140012aaa  inc     r10
0x140012aad  mov     [rsp+0F8h+var_A0], r10
0x140012ab2  jmp     short loc_140012A70
0x140012ab4  test    rax, rax
0x140012ab7  jnz     short loc_140012AD0
0x140012ab9  sub     rcx, 2
0x140012abd  mov     [rsp+0F8h+var_A8], rcx
0x140012ac2  dec     r10
0x140012ac5  mov     [rsp+0F8h+var_A0], r10
0x140012aca  mov     r11d, 80000005h
0x140012ad0  mov     [rcx], di
0x140012ad3  mov     [rsp+0F8h+var_C8], r11d
0x140012ad8  test    r11d, r11d
0x140012adb  cmovs   r14d, edi
0x140012adf  mov     [rsp+0F8h+var_B4], r14d
0x140012ae4  jmp     short loc_140012AF0
0x140012ae6  xor     r14d, r14d
0x140012ae9  mov     [rsp+0F8h+var_B4], r14d
0x140012aee  xor     edi, edi
0x140012af0  call    cs:__imp_W32GetUserSessionState
0x140012af7  nop     dword ptr [rax+rax+00h]
0x140012afc  mov     rbx, rax
0x140012aff  mov     r8d, [rax+10D00h]; Adjustment
0x140012b06  test    r8d, r8d
0x140012b09  jz      short loc_140012B29
0x140012b0b  xor     r9d, r9d; Wait
0x140012b0e  xor     edx, edx; Increment
0x140012b10  mov     rcx, [rax+10CF8h]; Semaphore
0x140012b17  call    cs:__imp_KeReleaseSemaphore
0x140012b1e  nop     dword ptr [rax+rax+00h]
0x140012b23  mov     [rbx+10D00h], edi
0x140012b29  call    cs:__imp_W32GetUserSessionState
0x140012b30  nop     dword ptr [rax+rax+00h]
0x140012b35  mov     rsi, rax
0x140012b38  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140012b3f  nop     dword ptr [rax+rax+00h]
0x140012b44  mov     rbx, rax
0x140012b47  mov     ecx, [rax+18h]
0x140012b4a  and     cl, 0Ch
0x140012b4d  cmp     cl, 8
0x140012b50  jnz     short loc_140012B6E
0x140012b52  call    UpdateDirtyVisRgnTrackers
0x140012b57  lea     rcx, [rsi+4C40h]
0x140012b5e  mov     [rcx+64h], edi
0x140012b61  mov     [rcx+50h], rdi
0x140012b65  call    DestroyExclusiveUserCritDeferredUnlockList
0x140012b6a  mov     [rsi+10h], rdi
0x140012b6e  mov     rcx, [rbx]
0x140012b71  test    rcx, rcx
0x140012b74  jnz     short loc_140012BE2
0x140012b76  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x140012b7b  test    eax, eax
0x140012b7d  jnz     loc_140012C32
0x140012b83  call    EtwTraceReleaseUserCrit
0x140012b88  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x140012b8c  mov     eax, [rbx+18h]
0x140012b8f  test    al, 10h
0x140012b91  jnz     loc_140012C51
0x140012b97  lea     rdx, [rbx+20h]
0x140012b9b  mov     rcx, [rsi]
0x140012b9e  call    cs:__imp_ExReleaseFastResource
0x140012ba5  nop     dword ptr [rax+rax+00h]
0x140012baa  call    cs:__imp_KeLeaveCriticalRegion
0x140012bb1  nop     dword ptr [rax+rax+00h]
0x140012bb6  movsxd  rax, r14d
0x140012bb9  mov     rcx, [rsp+0F8h+var_38]
0x140012bc1  xor     rcx, rsp; StackCookie
0x140012bc4  call    __security_check_cookie
0x140012bc9  mov     rbx, [rsp+0F8h+arg_10]
0x140012bd1  add     rsp, 0D0h
0x140012bd8  pop     r15
0x140012bda  pop     r14
0x140012bdc  pop     r12
0x140012bde  pop     rdi
0x140012bdf  pop     rsi
0x140012be0  retn
0x140012be2  mov     eax, [rbx+18h]
0x140012be5  test    al, 2
0x140012be7  jnz     short loc_140012B76
0x140012be9  mov     byte ptr [rcx+6ACh], 0
0x140012bf0  jmp     short loc_140012B76
0x140012bf2  mov     ecx, 5B5h
0x140012bf7  call    UserSetLastError
0x140012bfc  mov     r14d, edi
0x140012bff  jmp     loc_140012AF0
0x140012c04  cmp     r14w, ax
0x140012c08  jz      loc_1400129B8
0x140012c0e  test    r14w, r14w
0x140012c12  jnz     loc_1400129D5
0x140012c18  call    cs:__imp_PsGetCurrentProcessWow64Process
0x140012c1f  nop     dword ptr [rax+rax+00h]
0x140012c24  test    rax, rax
0x140012c27  jz      loc_1400129D5
0x140012c2d  jmp     loc_1400129B8
0x140012c32  mov     edx, eax; BugCheckParameter1
0x140012c34  mov     [rsp+0F8h+BugCheckParameter4], rdi; BugCheckParameter4
0x140012c39  xor     r9d, r9d; BugCheckParameter3
0x140012c3c  xor     r8d, r8d; BugCheckParameter2
0x140012c3f  mov     ecx, 160h; BugCheckCode
0x140012c44  call    cs:__imp_KeBugCheckEx
0x140012c51  mov     rcx, gs:188h
0x140012c5a  mov     r8, rbx
0x140012c5d  xor     edx, edx
0x140012c5f  call    cs:__imp_PsSetThreadWin32Thread
0x140012c66  nop     dword ptr [rax+rax+00h]
0x140012c6b  jmp     loc_140012B97
0x140239520  push    rbp
0x140239522  sub     rsp, 30h
0x140239526  mov     rbp, rdx
0x140239529  mov     rax, [rcx]
0x14023952c  mov     ecx, [rax]
0x14023952e  mov     [rbp+38h], ecx
0x140239531  mov     ecx, [rbp+38h]; Status
0x140239534  call    cs:__imp_RtlNtStatusToDosError
0x14023953b  nop     dword ptr [rax+rax+00h]
0x140239540  mov     ecx, eax
0x140239542  call    UserSetLastError
0x140239547  mov     dword ptr [rbp+40h], 1
0x14023954e  mov     eax, [rbp+40h]
0x140239551  add     rsp, 30h
0x140239555  pop     rbp
0x140239556  retn
```
