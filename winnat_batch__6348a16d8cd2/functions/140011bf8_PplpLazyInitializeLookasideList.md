# PplpLazyInitializeLookasideList

- ea: `0x140011bf8`
- end: `0x140011c86`
- name: `PplpLazyInitializeLookasideList`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400020e0`
- `0x1400091a4`

## callees

- `0x140011bf8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140011c70`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c0b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140011c59`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140011c59`

## pseudocode

```c
void __fastcall PplpLazyInitializeLookasideList(__int64 a1, __int64 a2)
{
  KIRQL v4; // bp

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 104));
  if ( !*(_BYTE *)(a2 + 112) )
  {
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)a2,
      PplpGenericAllocateFunction,
      PplpGenericFreeFunction,
      *(POOL_TYPE *)(a1 + 32),
      *(_DWORD *)(a1 + 4),
      *(_QWORD *)(a1 + 16),
      *(_DWORD *)(a1 + 8),
      *(_WORD *)(a1 + 36));
    *(_BYTE *)(a2 + 112) = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 104), v4);
}

```

## disassembly

```asm
0x140011bf8  push    rbx
0x140011bfa  push    rbp
0x140011bfb  push    rsi
0x140011bfc  push    rdi
0x140011bfd  sub     rsp, 48h
0x140011c01  mov     rdi, rcx
0x140011c04  mov     rbx, rdx
0x140011c07  lea     rcx, [rdx+68h]; SpinLock
0x140011c0b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011c12  nop     dword ptr [rax+rax+00h]
0x140011c17  cmp     byte ptr [rbx+70h], 0
0x140011c1b  mov     bpl, al
0x140011c1e  jnz     short loc_140011C69
0x140011c20  movzx   r8d, word ptr [rdi+24h]
0x140011c25  mov     rcx, rbx; Lookaside
0x140011c28  mov     edx, [rdi+4]
0x140011c2b  mov     r9d, [rdi+20h]; PoolType
0x140011c2f  mov     [rsp+68h+Depth], r8w; Depth
0x140011c35  mov     r8d, [rdi+8]
0x140011c39  mov     [rsp+68h+Tag], r8d; Tag
0x140011c3e  mov     r8, [rdi+10h]
0x140011c42  mov     [rsp+68h+Size], r8; Size
0x140011c47  lea     r8, PplpGenericFreeFunction; Free
0x140011c4e  mov     [rsp+68h+Flags], edx; Flags
0x140011c52  lea     rdx, PplpGenericAllocateFunction; Allocate
0x140011c59  call    cs:__imp_ExInitializeLookasideListEx
0x140011c60  nop     dword ptr [rax+rax+00h]
0x140011c65  mov     byte ptr [rbx+70h], 1
0x140011c69  mov     dl, bpl; NewIrql
0x140011c6c  lea     rcx, [rbx+68h]; SpinLock
0x140011c70  call    cs:__imp_KeReleaseSpinLock
0x140011c77  nop     dword ptr [rax+rax+00h]
0x140011c7c  add     rsp, 48h
0x140011c80  pop     rdi
0x140011c81  pop     rsi
0x140011c82  pop     rbp
0x140011c83  pop     rbx
0x140011c84  retn
```
