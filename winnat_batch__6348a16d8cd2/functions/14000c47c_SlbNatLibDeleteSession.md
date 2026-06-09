# SlbNatLibDeleteSession

- ea: `0x14000c47c`
- end: `0x14000c54b`
- name: `SlbNatLibDeleteSession`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006764`
- `0x14001515c`

## callees

- `0x140006b40`
- `0x14000ae68`
- `0x14000c47c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000c4c3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000c4c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000c517`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000c517`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000c4ae`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000c4ae`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000c526`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000c526`

## pseudocode

```c
void __fastcall SlbNatLibDeleteSession(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // r14
  KSPIN_LOCK *v4; // rbp
  char v5; // si
  int i; // edx
  char v7; // al
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  v2 = a2 - 8;
  v3 = a1 + 128;
  v4 = (KSPIN_LOCK *)(a2 - 8 + 240);
  v5 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireSpinLockAtDpcLevel(v4);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 64), &LockHandle);
  for ( i = 0; i <= *(_DWORD *)(v3 + 72); ++i )
  {
    while ( *(_DWORD *)(((__int64)i << 6) + v3 + 128) )
      ;
  }
  v7 = *(_BYTE *)(v2 + 132);
  if ( (v7 & 1) == 0 )
  {
    *(_BYTE *)(v2 + 132) = v7 | 1;
    WinNatDeleteSessionEntryUnderLock(v3, v2);
    v5 = 1;
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  KeReleaseSpinLockFromDpcLevel(v4);
  if ( v5 )
    WinNatLibDereferenceSession(v2);
}

```

## disassembly

```asm
0x14000c47c  push    rbx
0x14000c47e  push    rbp
0x14000c47f  push    rsi
0x14000c480  push    rdi
0x14000c481  push    r14
0x14000c483  sub     rsp, 40h
0x14000c487  lea     rbx, [rdx-8]
0x14000c48b  xorps   xmm0, xmm0
0x14000c48e  lea     r14, [rcx+80h]
0x14000c495  xor     eax, eax
0x14000c497  lea     rbp, [rbx+0F0h]
0x14000c49e  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x14000c4a3  mov     rcx, rbp; SpinLock
0x14000c4a6  xor     sil, sil
0x14000c4a9  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14000c4ae  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000c4b5  nop     dword ptr [rax+rax+00h]
0x14000c4ba  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x14000c4bf  lea     rcx, [r14+40h]; SpinLock
0x14000c4c3  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000c4ca  nop     dword ptr [rax+rax+00h]
0x14000c4cf  xor     edx, edx
0x14000c4d1  cmp     [r14+48h], edx
0x14000c4d5  jl      short loc_14000C4F2
0x14000c4d7  movsxd  rcx, edx
0x14000c4da  shl     rcx, 6
0x14000c4de  mov     eax, [rcx+r14+80h]
0x14000c4e6  test    eax, eax
0x14000c4e8  jnz     short loc_14000C4DE
0x14000c4ea  inc     edx
0x14000c4ec  cmp     edx, [r14+48h]
0x14000c4f0  jle     short loc_14000C4D7
0x14000c4f2  mov     al, [rbx+84h]
0x14000c4f8  test    al, 1
0x14000c4fa  jnz     short loc_14000C512
0x14000c4fc  or      al, 1
0x14000c4fe  mov     rdx, rbx
0x14000c501  mov     rcx, r14
0x14000c504  mov     [rbx+84h], al
0x14000c50a  call    WinNatDeleteSessionEntryUnderLock
0x14000c50f  mov     sil, 1
0x14000c512  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14000c517  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000c51e  nop     dword ptr [rax+rax+00h]
0x14000c523  mov     rcx, rbp; SpinLock
0x14000c526  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000c52d  nop     dword ptr [rax+rax+00h]
0x14000c532  test    sil, sil
0x14000c535  jz      short loc_14000C53F
0x14000c537  mov     rcx, rbx
0x14000c53a  call    WinNatLibDereferenceSession
0x14000c53f  add     rsp, 40h
0x14000c543  pop     r14
0x14000c545  pop     rdi
0x14000c546  pop     rsi
0x14000c547  pop     rbp
0x14000c548  pop     rbx
0x14000c549  retn
```
