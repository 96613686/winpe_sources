# TdxHashRemoveIrp

- ea: `0x140002294`
- end: `0x14000239e`
- name: `TdxHashRemoveIrp`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010b0`
- `0x140001a70`

## callees

- `0x140002294`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400022c5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400022c5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000232f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140002385`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000232f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140002385`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400022e9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400022e9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000230a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000230a`

## pseudocode

```c
_QWORD *__fastcall TdxHashRemoveIrp(__int64 a1)
{
  __int64 v2; // rsi
  _QWORD *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // r14
  int v6; // ebx
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-58h] BYREF

  v2 = (unsigned __int8)*(_DWORD *)(a1 + 8);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLockAtDpcLevel(&TdxAcceptIrpHashTableLock, &LockHandle);
  v3 = (_QWORD *)TdxAcceptIrpHashTable[v2];
  if ( v3 )
  {
    while ( 1 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v3[2] + 8LL));
      v4 = v3[2];
      v5 = *(_QWORD *)(v4 + 248);
      v6 = *(_DWORD *)(v4 + 256);
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v4 + 8));
      if ( v6 == *(_DWORD *)(a1 + 8) && v5 == *(_QWORD *)a1 )
        break;
      v3 = (_QWORD *)*v3;
      if ( v3 == (_QWORD *)TdxAcceptIrpHashTable[v2] )
        goto LABEL_5;
    }
    if ( (_QWORD *)*v3 == v3 )
    {
      TdxAcceptIrpHashTable[v2] = 0;
    }
    else
    {
      if ( (_QWORD *)TdxAcceptIrpHashTable[v2] == v3 )
        TdxAcceptIrpHashTable[v2] = *v3;
      v8 = (_QWORD *)*v3;
      if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v9 = (_QWORD *)v3[1], (_QWORD *)*v9 != v3) )
        __fastfail(3u);
      *v9 = v8;
      v8[1] = v9;
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    return v3 - 15;
  }
  else
  {
LABEL_5:
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x140002294  push    rbx
0x140002296  push    rbp
0x140002297  push    rsi
0x140002298  push    rdi
0x140002299  push    r14
0x14000229b  push    r15
0x14000229d  sub     rsp, 48h
0x1400022a1  xor     eax, eax
0x1400022a3  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400022a8  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1400022ad  mov     rbp, rcx
0x1400022b0  mov     eax, [rcx+8]
0x1400022b3  xorps   xmm0, xmm0
0x1400022b6  lea     rcx, TdxAcceptIrpHashTableLock; SpinLock
0x1400022bd  movzx   esi, al
0x1400022c0  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400022c5  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400022cc  nop     dword ptr [rax+rax+00h]
0x1400022d1  lea     r15, TdxAcceptIrpHashTable
0x1400022d8  mov     rdi, [r15+rsi*8]
0x1400022dc  test    rdi, rdi
0x1400022df  jz      short loc_14000232A
0x1400022e1  mov     rcx, [rdi+10h]
0x1400022e5  add     rcx, 8; SpinLock
0x1400022e9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400022f0  nop     dword ptr [rax+rax+00h]
0x1400022f5  mov     rcx, [rdi+10h]
0x1400022f9  mov     r14, [rcx+0F8h]
0x140002300  mov     ebx, [rcx+100h]
0x140002306  add     rcx, 8; SpinLock
0x14000230a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002311  nop     dword ptr [rax+rax+00h]
0x140002316  cmp     ebx, [rbp+8]
0x140002319  jnz     short loc_140002321
0x14000231b  cmp     r14, [rbp+0]
0x14000231f  jz      short loc_14000234B
0x140002321  mov     rdi, [rdi]
0x140002324  cmp     rdi, [r15+rsi*8]
0x140002328  jnz     short loc_1400022E1
0x14000232a  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000232f  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140002336  nop     dword ptr [rax+rax+00h]
0x14000233b  xor     eax, eax
0x14000233d  add     rsp, 48h
0x140002341  pop     r15
0x140002343  pop     r14
0x140002345  pop     rdi
0x140002346  pop     rsi
0x140002347  pop     rbp
0x140002348  pop     rbx
0x140002349  retn
0x14000234b  mov     rax, [rdi]
0x14000234e  cmp     rax, rdi
0x140002351  jnz     short loc_14000235D
0x140002353  mov     qword ptr [r15+rsi*8], 0
0x14000235b  jmp     short loc_140002380
0x14000235d  cmp     [r15+rsi*8], rdi
0x140002361  jnz     short loc_140002367
0x140002363  mov     [r15+rsi*8], rax
0x140002367  mov     rax, [rdi]
0x14000236a  cmp     [rax+8], rdi
0x14000236e  jnz     short loc_140002397
0x140002370  mov     rcx, [rdi+8]
0x140002374  cmp     [rcx], rdi
0x140002377  jnz     short loc_140002397
0x140002379  mov     [rcx], rax
0x14000237c  mov     [rax+8], rcx
0x140002380  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140002385  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000238c  nop     dword ptr [rax+rax+00h]
0x140002391  lea     rax, [rdi-78h]
0x140002395  jmp     short loc_14000233D
0x140002397  mov     ecx, 3
0x14000239c  int     29h; Win8: RtlFailFast(ecx)
```
