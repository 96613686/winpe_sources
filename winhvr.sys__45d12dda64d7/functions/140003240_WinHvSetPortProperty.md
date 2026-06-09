# WinHvSetPortProperty

- ea: `0x140003240`
- end: `0x140003364`
- name: `WinHvSetPortProperty`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140003240`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140003304`
- `ntoskrnl!KeGetCurrentIrql` at `0x140003304`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003294`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003294`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000331e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000331e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000333a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000333a`

## pseudocode

```c
__int64 __fastcall WinHvSetPortProperty(__int64 a1, int a2, int a3, __int64 a4)
{
  __int64 LockArray_high; // rdx
  __int64 *v9; // rax
  __int64 v10; // rax
  unsigned int v11; // ebx
  _QWORD v13[8]; // [rsp+20h] [rbp-40h] BYREF

  memset(v13, 0, sizeof(v13));
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v13[5] = 0;
  LOWORD(v13[4]) = *(_WORD *)(WinHvpProcessorToNode + 2 * LockArray_high);
  v9 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside
                                                                           + ((unsigned __int64)LOWORD(v13[4]) << 7)));
  v13[5] = v9;
  v13[7] = WinHvpReleasePoolBuffers;
  if ( !v9 )
  {
    LOBYTE(v13[6]) = KeGetCurrentIrql();
    if ( LOBYTE(v13[6]) >= 2u )
    {
      LOBYTE(v13[6]) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
      v9 = WinHvpFallbackBuffer;
    }
    else
    {
      ExAcquireFastMutex(&WinHvpFallbackMutex);
      v9 = WinHvpFallbackBuffer2;
    }
    v13[5] = v9;
    v13[7] = WinHvpReleaseFallbackBuffers;
  }
  v10 = v9[2];
  v13[0] = v13;
  v13[1] = v10;
  v13[2] = 0;
  *(_QWORD *)v10 = a1;
  *(_DWORD *)(v10 + 8) = a2;
  *(_DWORD *)(v10 + 16) = a3;
  *(_QWORD *)(v10 + 24) = a4;
  v11 = WinHvpSimplePoolHypercall_CallViaMacro(v13[0], 112);
  ((void (__fastcall *)(_QWORD))v13[7])(v13[0]);
  return v11;
}

```

## disassembly

```asm
0x140003240  push    rbp
0x140003242  push    rbx
0x140003243  push    rsi
0x140003244  push    rdi
0x140003245  push    r14
0x140003247  mov     rbp, rsp
0x14000324a  sub     rsp, 60h
0x14000324e  mov     ebx, edx
0x140003250  mov     esi, r8d
0x140003253  xor     edx, edx; Val
0x140003255  mov     r14, rcx
0x140003258  lea     rcx, [rbp+var_40]; void *
0x14000325c  mov     rdi, r9
0x14000325f  lea     r8d, [rdx+40h]; Size
0x140003263  call    memset
0x140003268  mov     eax, gs:1A4h
0x140003270  mov     edx, eax
0x140003272  mov     rax, cs:WinHvpProcessorToNode
0x140003279  mov     [rbp+var_18], 0
0x140003281  movzx   ecx, word ptr [rax+rdx*2]
0x140003285  mov     [rbp+var_20], cx
0x140003289  shl     rcx, 7
0x14000328d  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140003294  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000329b  nop     dword ptr [rax+rax+00h]
0x1400032a0  mov     [rbp+var_18], rax
0x1400032a4  lea     rcx, WinHvpReleasePoolBuffers
0x1400032ab  mov     [rbp+var_8], rcx
0x1400032af  test    rax, rax
0x1400032b2  jz      short loc_140003304
0x1400032b4  mov     rax, [rax+10h]
0x1400032b8  lea     rcx, [rbp+var_40]
0x1400032bc  mov     [rbp+var_40], rcx
0x1400032c0  mov     edx, 70h ; 'p'
0x1400032c5  mov     [rbp+var_38], rax
0x1400032c9  mov     [rbp+var_30], 0
0x1400032d1  mov     [rax], r14
0x1400032d4  mov     [rax+8], ebx
0x1400032d7  mov     [rax+10h], esi
0x1400032da  mov     [rax+18h], rdi
0x1400032de  mov     rcx, [rbp+var_40]
0x1400032e2  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400032e7  mov     rcx, [rbp+var_40]
0x1400032eb  mov     ebx, eax
0x1400032ed  mov     rax, [rbp+var_8]
0x1400032f1  call    _guard_dispatch_icall
0x1400032f6  mov     eax, ebx
0x1400032f8  add     rsp, 60h
0x1400032fc  pop     r14
0x1400032fe  pop     rdi
0x1400032ff  pop     rsi
0x140003300  pop     rbx
0x140003301  pop     rbp
0x140003302  retn
0x140003304  call    cs:__imp_KeGetCurrentIrql
0x14000330b  nop     dword ptr [rax+rax+00h]
0x140003310  mov     [rbp+var_10], al
0x140003313  cmp     al, 2
0x140003315  jnb     short loc_140003333
0x140003317  lea     rcx, WinHvpFallbackMutex; FastMutex
0x14000331e  call    cs:__imp_ExAcquireFastMutex
0x140003325  nop     dword ptr [rax+rax+00h]
0x14000332a  lea     rax, WinHvpFallbackBuffer2
0x140003331  jmp     short loc_140003350
0x140003333  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x14000333a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003341  nop     dword ptr [rax+rax+00h]
0x140003346  mov     [rbp+var_10], al
0x140003349  lea     rax, WinHvpFallbackBuffer
0x140003350  lea     rcx, WinHvpReleaseFallbackBuffers
0x140003357  mov     [rbp+var_18], rax
0x14000335b  mov     [rbp+var_8], rcx
0x14000335f  jmp     loc_1400032B4
```
