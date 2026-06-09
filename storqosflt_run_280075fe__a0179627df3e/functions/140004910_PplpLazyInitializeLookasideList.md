# PplpLazyInitializeLookasideList

- ea: `0x140004910`
- end: `0x14000499f`
- name: `PplpLazyInitializeLookasideList`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001ab0`
- `0x140003790`

## callees

- `0x140004910`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x140004971`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140004971`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004989`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004989`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004923`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004923`

## pseudocode

```c
void __fastcall PplpLazyInitializeLookasideList(__int64 a1, __int64 a2)
{
  KIRQL v4; // si

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
0x140004910  push    rbx
0x140004912  push    rbp
0x140004913  push    rsi
0x140004914  push    rdi
0x140004915  sub     rsp, 48h
0x140004919  mov     rbp, rcx
0x14000491c  mov     rdi, rdx
0x14000491f  lea     rcx, [rdx+68h]; SpinLock
0x140004923  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000492a  nop     dword ptr [rax+rax+00h]
0x14000492f  cmp     byte ptr [rdi+70h], 0
0x140004933  movzx   esi, al
0x140004936  jnz     short loc_140004981
0x140004938  movzx   r8d, word ptr [rbp+24h]
0x14000493d  lea     rdx, PplpGenericAllocateFunction; Allocate
0x140004944  mov     ecx, [rbp+4]
0x140004947  mov     r9d, [rbp+20h]; PoolType
0x14000494b  mov     [rsp+68h+Depth], r8w; Depth
0x140004951  mov     r8d, [rbp+8]
0x140004955  mov     [rsp+68h+Tag], r8d; Tag
0x14000495a  mov     r8, [rbp+10h]
0x14000495e  mov     [rsp+68h+Size], r8; Size
0x140004963  lea     r8, PplpGenericFreeFunction; Free
0x14000496a  mov     [rsp+68h+Flags], ecx; Flags
0x14000496e  mov     rcx, rdi; Lookaside
0x140004971  call    cs:__imp_ExInitializeLookasideListEx
0x140004978  nop     dword ptr [rax+rax+00h]
0x14000497d  mov     byte ptr [rdi+70h], 1
0x140004981  movzx   edx, sil; NewIrql
0x140004985  lea     rcx, [rdi+68h]; SpinLock
0x140004989  call    cs:__imp_KeReleaseSpinLock
0x140004990  nop     dword ptr [rax+rax+00h]
0x140004995  add     rsp, 48h
0x140004999  pop     rdi
0x14000499a  pop     rsi
0x14000499b  pop     rbp
0x14000499c  pop     rbx
0x14000499d  retn
```
