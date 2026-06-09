# PplpLazyInitializeLookasideList

- ea: `0x14000f3dc`
- end: `0x14000f46a`
- name: `PplpLazyInitializeLookasideList`
- size: `142`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140002060`
- `0x1400022d0`
- `0x1400094e0`
- `0x140009fa0`

## callees

- `0x14000f3dc`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000f43d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000f43d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f454`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f454`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f3ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f3ef`

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
0x14000f3dc  push    rbx
0x14000f3de  push    rbp
0x14000f3df  push    rsi
0x14000f3e0  push    rdi
0x14000f3e1  sub     rsp, 48h
0x14000f3e5  mov     rdi, rcx
0x14000f3e8  mov     rbx, rdx
0x14000f3eb  lea     rcx, [rdx+68h]; SpinLock
0x14000f3ef  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f3f6  nop     dword ptr [rax+rax+00h]
0x14000f3fb  cmp     byte ptr [rbx+70h], 0
0x14000f3ff  mov     bpl, al
0x14000f402  jnz     short loc_14000F44D
0x14000f404  movzx   r8d, word ptr [rdi+24h]
0x14000f409  mov     rcx, rbx; Lookaside
0x14000f40c  mov     edx, [rdi+4]
0x14000f40f  mov     r9d, [rdi+20h]; PoolType
0x14000f413  mov     [rsp+68h+Depth], r8w; Depth
0x14000f419  mov     r8d, [rdi+8]
0x14000f41d  mov     [rsp+68h+Tag], r8d; Tag
0x14000f422  mov     r8, [rdi+10h]
0x14000f426  mov     [rsp+68h+Size], r8; Size
0x14000f42b  lea     r8, PplpGenericFreeFunction; Free
0x14000f432  mov     [rsp+68h+Flags], edx; Flags
0x14000f436  lea     rdx, PplpGenericAllocateFunction; Allocate
0x14000f43d  call    cs:__imp_ExInitializeLookasideListEx
0x14000f444  nop     dword ptr [rax+rax+00h]
0x14000f449  mov     byte ptr [rbx+70h], 1
0x14000f44d  mov     dl, bpl; NewIrql
0x14000f450  lea     rcx, [rbx+68h]; SpinLock
0x14000f454  call    cs:__imp_KeReleaseSpinLock
0x14000f45b  nop     dword ptr [rax+rax+00h]
0x14000f460  add     rsp, 48h
0x14000f464  pop     rdi
0x14000f465  pop     rsi
0x14000f466  pop     rbp
0x14000f467  pop     rbx
0x14000f468  retn
```
