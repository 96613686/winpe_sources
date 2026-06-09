# PplpLazyInitializeLookasideList

- ea: `0x140012538`
- end: `0x1400125c6`
- name: `PplpLazyInitializeLookasideList`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400020e0`
- `0x1400091a4`

## callees

- `0x140012538`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400125b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400125b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001254b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001254b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140012599`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140012599`

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
0x140012538  push    rbx
0x14001253a  push    rbp
0x14001253b  push    rsi
0x14001253c  push    rdi
0x14001253d  sub     rsp, 48h
0x140012541  mov     rdi, rcx
0x140012544  mov     rbx, rdx
0x140012547  lea     rcx, [rdx+68h]; SpinLock
0x14001254b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012552  nop     dword ptr [rax+rax+00h]
0x140012557  cmp     byte ptr [rbx+70h], 0
0x14001255b  mov     bpl, al
0x14001255e  jnz     short loc_1400125A9
0x140012560  movzx   r8d, word ptr [rdi+24h]
0x140012565  mov     rcx, rbx; Lookaside
0x140012568  mov     edx, [rdi+4]
0x14001256b  mov     r9d, [rdi+20h]; PoolType
0x14001256f  mov     [rsp+68h+Depth], r8w; Depth
0x140012575  mov     r8d, [rdi+8]
0x140012579  mov     [rsp+68h+Tag], r8d; Tag
0x14001257e  mov     r8, [rdi+10h]
0x140012582  mov     [rsp+68h+Size], r8; Size
0x140012587  lea     r8, PplpGenericFreeFunction; Free
0x14001258e  mov     [rsp+68h+Flags], edx; Flags
0x140012592  lea     rdx, PplpGenericAllocateFunction; Allocate
0x140012599  call    cs:__imp_ExInitializeLookasideListEx
0x1400125a0  nop     dword ptr [rax+rax+00h]
0x1400125a5  mov     byte ptr [rbx+70h], 1
0x1400125a9  mov     dl, bpl; NewIrql
0x1400125ac  lea     rcx, [rbx+68h]; SpinLock
0x1400125b0  call    cs:__imp_KeReleaseSpinLock
0x1400125b7  nop     dword ptr [rax+rax+00h]
0x1400125bc  add     rsp, 48h
0x1400125c0  pop     rdi
0x1400125c1  pop     rsi
0x1400125c2  pop     rbp
0x1400125c3  pop     rbx
0x1400125c4  retn
```
