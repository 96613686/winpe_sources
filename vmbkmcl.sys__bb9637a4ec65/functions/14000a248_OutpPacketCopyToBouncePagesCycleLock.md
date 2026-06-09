# OutpPacketCopyToBouncePagesCycleLock

- ea: `0x14000a248`
- end: `0x14000a2ee`
- name: `OutpPacketCopyToBouncePagesCycleLock`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400037e0`
- `0x140006700`

## callees

- `0x1400031c0`
- `0x14000a248`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000a2d8`
- `ntoskrnl!KeSetEvent` at `0x14000a2d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a2a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a2a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a272`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a272`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a2b2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a2b2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a280`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a280`

## pseudocode

```c
void __fastcall OutpPacketCopyToBouncePagesCycleLock(ULONG_PTR a1, __int64 a2, KIRQL *a3)
{
  KSPIN_LOCK *v3; // rdi
  KSPIN_LOCK *v7; // rcx
  struct _KEVENT *v9; // rcx

  ++*(_DWORD *)(a1 + 1048);
  v3 = (KSPIN_LOCK *)(a1 + 256);
  v7 = (KSPIN_LOCK *)(a1 + 256);
  if ( a3 )
    KeReleaseSpinLock(v7, *a3);
  else
    KeReleaseSpinLockFromDpcLevel(v7);
  OutpPacketCopyBouncePagesToMdl(a1, a2, 0);
  if ( a3 )
    *a3 = KeAcquireSpinLockRaiseToDpc(v3);
  else
    KeAcquireSpinLockAtDpcLevel(v3);
  if ( (*(_DWORD *)(a1 + 1048))-- == 1 )
  {
    v9 = *(struct _KEVENT **)(a1 + 1056);
    if ( v9 )
      KeSetEvent(v9, 0, 0);
  }
}

```

## disassembly

```asm
0x14000a248  push    rbx
0x14000a24a  push    rbp
0x14000a24b  push    rsi
0x14000a24c  push    rdi
0x14000a24d  sub     rsp, 28h
0x14000a251  inc     dword ptr [rcx+418h]
0x14000a257  lea     rdi, [rcx+100h]
0x14000a25e  mov     rbx, rcx
0x14000a261  mov     rsi, r8
0x14000a264  mov     rbp, rdx
0x14000a267  mov     rcx, rdi; SpinLock
0x14000a26a  test    r8, r8
0x14000a26d  jz      short loc_14000A280
0x14000a26f  mov     dl, [r8]; NewIrql
0x14000a272  call    cs:__imp_KeReleaseSpinLock
0x14000a279  nop     dword ptr [rax+rax+00h]
0x14000a27e  jmp     short loc_14000A28C
0x14000a280  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000a287  nop     dword ptr [rax+rax+00h]
0x14000a28c  xor     r8d, r8d
0x14000a28f  mov     rdx, rbp
0x14000a292  mov     rcx, rbx
0x14000a295  call    OutpPacketCopyBouncePagesToMdl
0x14000a29a  mov     rcx, rdi; SpinLock
0x14000a29d  test    rsi, rsi
0x14000a2a0  jz      short loc_14000A2B2
0x14000a2a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a2a9  nop     dword ptr [rax+rax+00h]
0x14000a2ae  mov     [rsi], al
0x14000a2b0  jmp     short loc_14000A2BE
0x14000a2b2  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000a2b9  nop     dword ptr [rax+rax+00h]
0x14000a2be  add     dword ptr [rbx+418h], 0FFFFFFFFh
0x14000a2c5  jnz     short loc_14000A2E4
0x14000a2c7  mov     rcx, [rbx+420h]; Event
0x14000a2ce  test    rcx, rcx
0x14000a2d1  jz      short loc_14000A2E4
0x14000a2d3  xor     r8d, r8d; Wait
0x14000a2d6  xor     edx, edx; Increment
0x14000a2d8  call    cs:__imp_KeSetEvent
0x14000a2df  nop     dword ptr [rax+rax+00h]
0x14000a2e4  add     rsp, 28h
0x14000a2e8  pop     rdi
0x14000a2e9  pop     rsi
0x14000a2ea  pop     rbp
0x14000a2eb  pop     rbx
0x14000a2ec  retn
```
