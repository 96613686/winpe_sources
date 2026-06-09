# RtlAcquireScalableReadLockAtDpcLevel

- ea: `0x140004d20`
- end: `0x140004d9a`
- name: `RtlAcquireScalableReadLockAtDpcLevel`
- size: `122`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140003830`
- `0x140006764`
- `0x140006f04`
- `0x14000b404`
- `0x14000fb40`
- `0x140010610`
- `0x14001da9c`

## callees

- `0x140004d20`

## import_xrefs

- `ntoskrnl!KeTestSpinLock` at `0x140004d51`
- `ntoskrnl!KeTestSpinLock` at `0x140004d51`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140004d78`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140004d78`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004d8c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140004d8c`

## pseudocode

```c
void __fastcall RtlAcquireScalableReadLockAtDpcLevel(PKSPIN_LOCK SpinLock, unsigned int a2)
{
  volatile signed __int32 *v3; // rdi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v3 = (volatile signed __int32 *)&SpinLock[8 * (a2 & (_DWORD)SpinLock[1]) + 8];
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement(v3);
  if ( !KeTestSpinLock(SpinLock) )
  {
    _InterlockedDecrement(v3);
    KeAcquireInStackQueuedSpinLockAtDpcLevel(SpinLock, &LockHandle);
    _InterlockedIncrement(v3);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
}

```

## disassembly

```asm
0x140004d20  mov     [rsp+arg_0], rbx
0x140004d25  push    rdi
0x140004d26  sub     rsp, 40h
0x140004d2a  mov     edi, [rcx+8]
0x140004d2d  xor     eax, eax
0x140004d2f  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140004d34  xorps   xmm0, xmm0
0x140004d37  mov     eax, edx
0x140004d39  mov     rbx, rcx
0x140004d3c  and     rdi, rax
0x140004d3f  inc     rdi
0x140004d42  shl     rdi, 6
0x140004d46  add     rdi, rcx
0x140004d49  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140004d4e  lock inc dword ptr [rdi]
0x140004d51  call    cs:__imp_KeTestSpinLock
0x140004d58  nop     dword ptr [rax+rax+00h]
0x140004d5d  test    al, al
0x140004d5f  jz      short loc_140004D6D
0x140004d61  mov     rbx, [rsp+48h+arg_0]
0x140004d66  add     rsp, 40h
0x140004d6a  pop     rdi
0x140004d6b  retn
0x140004d6d  lock dec dword ptr [rdi]
0x140004d70  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140004d75  mov     rcx, rbx; SpinLock
0x140004d78  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140004d7f  nop     dword ptr [rax+rax+00h]
0x140004d84  lock inc dword ptr [rdi]
0x140004d87  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140004d8c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140004d93  nop     dword ptr [rax+rax+00h]
0x140004d98  jmp     short loc_140004D61
```
