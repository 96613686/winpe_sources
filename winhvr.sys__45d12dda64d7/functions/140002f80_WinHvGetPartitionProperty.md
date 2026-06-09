# WinHvGetPartitionProperty

- ea: `0x140002f80`
- end: `0x1400030a4`
- name: `WinHvGetPartitionProperty`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140002f80`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140002ff6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002ff6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002fd3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002fd3`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003010`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003010`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000302c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000302c`

## pseudocode

```c
__int64 __fastcall WinHvGetPartitionProperty(__int64 a1, int a2, _QWORD *a3)
{
  __int64 LockArray_high; // r9
  __int64 *v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rbx
  int v10; // edi
  _QWORD v12[8]; // [rsp+20h] [rbp-40h] BYREF

  memset(v12, 0, sizeof(v12));
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v12[5] = 0;
  LOWORD(v12[4]) = *(_WORD *)(WinHvpProcessorToNode + 2 * LockArray_high);
  v7 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside
                                                                           + ((unsigned __int64)LOWORD(v12[4]) << 7)));
  v12[5] = v7;
  v12[7] = WinHvpReleasePoolBuffers;
  if ( !v7 )
  {
    LOBYTE(v12[6]) = KeGetCurrentIrql();
    if ( LOBYTE(v12[6]) >= 2u )
    {
      LOBYTE(v12[6]) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
      v7 = WinHvpFallbackBuffer;
    }
    else
    {
      ExAcquireFastMutex(&WinHvpFallbackMutex);
      v7 = WinHvpFallbackBuffer2;
    }
    v12[5] = v7;
    v12[7] = WinHvpReleaseFallbackBuffers;
  }
  v8 = v7[2];
  v12[1] = v8;
  v9 = (_QWORD *)v7[4];
  v12[0] = v12;
  v12[2] = v9;
  *(_QWORD *)v8 = a1;
  *(_DWORD *)(v8 + 8) = a2;
  v10 = WinHvpSimplePoolHypercall_CallViaMacro(v12[0], 68);
  if ( v10 >= 0 )
    *a3 = *v9;
  ((void (__fastcall *)(_QWORD))v12[7])(v12[0]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140002f80  push    rbp
0x140002f82  push    rbx
0x140002f83  push    rsi
0x140002f84  push    rdi
0x140002f85  push    r14
0x140002f87  mov     rbp, rsp
0x140002f8a  sub     rsp, 60h
0x140002f8e  mov     edi, edx
0x140002f90  mov     rsi, r8
0x140002f93  xor     edx, edx; Val
0x140002f95  mov     r14, rcx
0x140002f98  lea     rcx, [rbp+var_40]; void *
0x140002f9c  lea     r8d, [rdx+40h]; Size
0x140002fa0  call    memset
0x140002fa5  mov     eax, gs:1A4h
0x140002fad  mov     r9d, eax
0x140002fb0  mov     rax, cs:WinHvpProcessorToNode
0x140002fb7  mov     [rbp+var_18], 0
0x140002fbf  movzx   ecx, word ptr [rax+r9*2]
0x140002fc4  mov     [rbp+var_20], cx
0x140002fc8  shl     rcx, 7
0x140002fcc  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140002fd3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002fda  nop     dword ptr [rax+rax+00h]
0x140002fdf  mov     rcx, rax
0x140002fe2  mov     [rbp+var_18], rax
0x140002fe6  lea     rax, WinHvpReleasePoolBuffers
0x140002fed  mov     [rbp+var_8], rax
0x140002ff1  test    rcx, rcx
0x140002ff4  jnz     short loc_140003051
0x140002ff6  call    cs:__imp_KeGetCurrentIrql
0x140002ffd  nop     dword ptr [rax+rax+00h]
0x140003002  mov     [rbp+var_10], al
0x140003005  cmp     al, 2
0x140003007  jnb     short loc_140003025
0x140003009  lea     rcx, WinHvpFallbackMutex; FastMutex
0x140003010  call    cs:__imp_ExAcquireFastMutex
0x140003017  nop     dword ptr [rax+rax+00h]
0x14000301c  lea     rcx, WinHvpFallbackBuffer2
0x140003023  jmp     short loc_140003042
0x140003025  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x14000302c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003033  nop     dword ptr [rax+rax+00h]
0x140003038  mov     [rbp+var_10], al
0x14000303b  lea     rcx, WinHvpFallbackBuffer
0x140003042  lea     rax, WinHvpReleaseFallbackBuffers
0x140003049  mov     [rbp+var_18], rcx
0x14000304d  mov     [rbp+var_8], rax
0x140003051  mov     rax, [rcx+10h]
0x140003055  mov     edx, 44h ; 'D'
0x14000305a  mov     [rbp+var_38], rax
0x14000305e  mov     rbx, [rcx+20h]
0x140003062  lea     rcx, [rbp+var_40]
0x140003066  mov     [rbp+var_40], rcx
0x14000306a  mov     [rbp+var_30], rbx
0x14000306e  mov     [rax], r14
0x140003071  mov     [rax+8], edi
0x140003074  mov     rcx, [rbp+var_40]
0x140003078  call    WinHvpSimplePoolHypercall_CallViaMacro
0x14000307d  mov     edi, eax
0x14000307f  test    eax, eax
0x140003081  js      short loc_140003089
0x140003083  mov     rcx, [rbx]
0x140003086  mov     [rsi], rcx
0x140003089  mov     rcx, [rbp+var_40]
0x14000308d  mov     rax, [rbp+var_8]
0x140003091  call    _guard_dispatch_icall
0x140003096  mov     eax, edi
0x140003098  add     rsp, 60h
0x14000309c  pop     r14
0x14000309e  pop     rdi
0x14000309f  pop     rsi
0x1400030a0  pop     rbx
0x1400030a1  pop     rbp
0x1400030a2  retn
```
