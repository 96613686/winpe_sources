# RtlAcquireScalableReadLock

- ea: `0x140004990`
- end: `0x140004a35`
- name: `RtlAcquireScalableReadLock`
- size: `165`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004648`
- `0x140019790`
- `0x14001a7c0`
- `0x14001b150`

## callees

- `0x140004990`

## import_xrefs

- `ntoskrnl!KeTestSpinLock` at `0x1400049e7`
- `ntoskrnl!KeTestSpinLock` at `0x1400049e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140004a13`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140004a13`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004a27`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004a27`
- `ntoskrnl!KfRaiseIrql` at `0x1400049aa`
- `ntoskrnl!KfRaiseIrql` at `0x1400049aa`

## pseudocode

```c
void __fastcall RtlAcquireScalableReadLock(PKSPIN_LOCK SpinLock, unsigned int *a2, KIRQL *a3)
{
  unsigned int LockArray_high; // eax
  KSPIN_LOCK v6; // rdi
  volatile signed __int32 *v7; // rdi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  *a3 = KfRaiseIrql(2u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v6 = LockArray_high & (_DWORD)SpinLock[1];
  *a2 = LockArray_high;
  v7 = (volatile signed __int32 *)&SpinLock[8 * v6 + 8];
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement(v7);
  if ( !KeTestSpinLock(SpinLock) )
  {
    _InterlockedDecrement(v7);
    KeAcquireInStackQueuedSpinLockAtDpcLevel(SpinLock, &LockHandle);
    _InterlockedIncrement(v7);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
}

```

## disassembly

```asm
0x140004990  mov     [rsp+arg_0], rbx
0x140004995  mov     [rsp+arg_8], rsi
0x14000499a  push    rdi
0x14000499b  sub     rsp, 40h
0x14000499f  mov     rbx, rcx
0x1400049a2  mov     rdi, r8
0x1400049a5  mov     cl, 2; NewIrql
0x1400049a7  mov     rsi, rdx
0x1400049aa  call    cs:__imp_KfRaiseIrql
0x1400049b1  nop     dword ptr [rax+rax+00h]
0x1400049b6  mov     [rdi], al
0x1400049b8  xor     ecx, ecx
0x1400049ba  mov     eax, gs:1A4h
0x1400049c2  xorps   xmm0, xmm0
0x1400049c5  mov     edi, [rbx+8]
0x1400049c8  and     rdi, rax
0x1400049cb  mov     [rsi], eax
0x1400049cd  inc     rdi
0x1400049d0  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rcx
0x1400049d5  shl     rdi, 6
0x1400049d9  add     rdi, rbx
0x1400049dc  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x1400049e1  lock inc dword ptr [rdi]
0x1400049e4  mov     rcx, rbx; SpinLock
0x1400049e7  call    cs:__imp_KeTestSpinLock
0x1400049ee  nop     dword ptr [rax+rax+00h]
0x1400049f3  test    al, al
0x1400049f5  jz      short loc_140004A08
0x1400049f7  mov     rbx, [rsp+48h+arg_0]
0x1400049fc  mov     rsi, [rsp+48h+arg_8]
0x140004a01  add     rsp, 40h
0x140004a05  pop     rdi
0x140004a06  retn
0x140004a08  lock dec dword ptr [rdi]
0x140004a0b  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140004a10  mov     rcx, rbx; SpinLock
0x140004a13  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140004a1a  nop     dword ptr [rax+rax+00h]
0x140004a1f  lock inc dword ptr [rdi]
0x140004a22  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140004a27  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140004a2e  nop     dword ptr [rax+rax+00h]
0x140004a33  jmp     short loc_1400049F7
```
