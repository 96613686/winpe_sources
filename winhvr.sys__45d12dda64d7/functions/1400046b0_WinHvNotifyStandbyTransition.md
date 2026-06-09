# WinHvNotifyStandbyTransition

- ea: `0x1400046b0`
- end: `0x1400047cd`
- name: `WinHvNotifyStandbyTransition`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140003610`
- `0x1400046b0`
- `0x140009c90`
- `0x14000a040`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140004724`
- `ntoskrnl!KeGetCurrentIrql` at `0x140004724`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140004704`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140004704`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000473e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000473e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000475a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000475a`

## pseudocode

```c
__int64 __fastcall WinHvNotifyStandbyTransition(char a1, char a2)
{
  __int64 LockArray_high; // r8
  __int64 *v5; // rax
  _BYTE *v6; // rax
  unsigned int v7; // ebx
  _QWORD v9[8]; // [rsp+20h] [rbp-40h] BYREF

  memset(v9, 0, sizeof(v9));
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v9[5] = 0;
  LOWORD(v9[4]) = *(_WORD *)(WinHvpProcessorToNode + 2 * LockArray_high);
  v5 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside
                                                                           + ((unsigned __int64)LOWORD(v9[4]) << 7)));
  v9[5] = v5;
  v9[7] = WinHvpReleasePoolBuffers;
  if ( !v5 )
  {
    LOBYTE(v9[6]) = KeGetCurrentIrql();
    if ( LOBYTE(v9[6]) >= 2u )
    {
      LOBYTE(v9[6]) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
      v5 = WinHvpFallbackBuffer;
    }
    else
    {
      ExAcquireFastMutex(&WinHvpFallbackMutex);
      v5 = WinHvpFallbackBuffer2;
    }
    v9[5] = v5;
    v9[7] = WinHvpReleaseFallbackBuffers;
  }
  v6 = (_BYTE *)v5[2];
  v9[0] = v9;
  v9[1] = v6;
  v9[2] = 0;
  *v6 = a1;
  v6[1] = a2;
  v7 = WinHvpSimplePoolHypercall_CallViaMacro(v9[0], 133);
  ((void (__fastcall *)(_QWORD))v9[7])(v9[0]);
  return v7;
}

```

## disassembly

```asm
0x1400046b0  mov     [rsp-8+arg_0], rbx
0x1400046b5  mov     [rsp-8+arg_8], rdi
0x1400046ba  push    rbp
0x1400046bb  mov     rbp, rsp
0x1400046be  sub     rsp, 60h
0x1400046c2  mov     bl, dl
0x1400046c4  mov     dil, cl
0x1400046c7  xor     edx, edx; Val
0x1400046c9  lea     rcx, [rbp+var_40]; void *
0x1400046cd  lea     r8d, [rdx+40h]; Size
0x1400046d1  call    memset
0x1400046d6  mov     eax, gs:1A4h
0x1400046de  mov     r8d, eax
0x1400046e1  mov     rax, cs:WinHvpProcessorToNode
0x1400046e8  mov     [rbp+var_18], 0
0x1400046f0  movzx   ecx, word ptr [rax+r8*2]
0x1400046f5  mov     [rbp+var_20], cx
0x1400046f9  shl     rcx, 7
0x1400046fd  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140004704  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000470b  nop     dword ptr [rax+rax+00h]
0x140004710  mov     [rbp+var_18], rax
0x140004714  lea     rcx, WinHvpReleasePoolBuffers
0x14000471b  mov     [rbp+var_8], rcx
0x14000471f  test    rax, rax
0x140004722  jnz     short loc_14000477F
0x140004724  call    cs:__imp_KeGetCurrentIrql
0x14000472b  nop     dword ptr [rax+rax+00h]
0x140004730  mov     [rbp+var_10], al
0x140004733  cmp     al, 2
0x140004735  jnb     short loc_140004753
0x140004737  lea     rcx, WinHvpFallbackMutex; FastMutex
0x14000473e  call    cs:__imp_ExAcquireFastMutex
0x140004745  nop     dword ptr [rax+rax+00h]
0x14000474a  lea     rax, WinHvpFallbackBuffer2
0x140004751  jmp     short loc_140004770
0x140004753  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x14000475a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004761  nop     dword ptr [rax+rax+00h]
0x140004766  mov     [rbp+var_10], al
0x140004769  lea     rax, WinHvpFallbackBuffer
0x140004770  lea     rcx, WinHvpReleaseFallbackBuffers
0x140004777  mov     [rbp+var_18], rax
0x14000477b  mov     [rbp+var_8], rcx
0x14000477f  mov     rax, [rax+10h]
0x140004783  lea     rcx, [rbp+var_40]
0x140004787  mov     [rbp+var_40], rcx
0x14000478b  mov     edx, 85h
0x140004790  mov     [rbp+var_38], rax
0x140004794  mov     [rbp+var_30], 0
0x14000479c  mov     [rax], dil
0x14000479f  mov     [rax+1], bl
0x1400047a2  mov     rcx, [rbp+var_40]
0x1400047a6  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400047ab  mov     rcx, [rbp+var_40]
0x1400047af  mov     ebx, eax
0x1400047b1  mov     rax, [rbp+var_8]
0x1400047b5  call    _guard_dispatch_icall
0x1400047ba  mov     rdi, [rsp+60h+arg_8]
0x1400047bf  mov     eax, ebx
0x1400047c1  mov     rbx, [rsp+60h+arg_0]
0x1400047c6  add     rsp, 60h
0x1400047ca  pop     rbp
0x1400047cb  retn
```
