# VsmmPhuStoreItemRemoveAndFree

- ea: `0x1400b273c`
- end: `0x1400b27d5`
- name: `VsmmPhuStoreItemRemoveAndFree`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140077b7c`
- `0x1400a1be0`
- `0x1400b6994`
- `0x1400b7f18`

## callees

- `0x140034554`
- `0x140034914`
- `0x1400b249c`
- `0x1400b8954`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400b275b`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b2772`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b275b`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b2772`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b27b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b27b0`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreItemRemoveAndFree(__int64 a1, char *a2)
{
  VidObjectLockAcquireExclusive(a1);
  RtlRbRemoveNode(a1 + 1264, a2);
  RtlRbRemoveNode(a1 + 1280, a2 + 24);
  --*(_QWORD *)(a1 + 1296);
  VidObjectLockRelease(a1);
  VsmmPhuStoreItemDataSet(a1, (__int64)a2, 0, 0, 1, 1);
  ExFreePoolWithTag(a2, 0x6D4D6456u);
  return VsmmPhuStorepSerializationChargeDecrease(a1, 64);
}

```

## disassembly

```asm
0x1400b273c  mov     [rsp+arg_0], rbx
0x1400b2741  push    rdi
0x1400b2742  sub     rsp, 30h
0x1400b2746  mov     rbx, rdx
0x1400b2749  mov     rdi, rcx
0x1400b274c  call    VidObjectLockAcquireExclusive
0x1400b2751  lea     rcx, [rdi+4F0h]
0x1400b2758  mov     rdx, rbx
0x1400b275b  call    cs:__imp_RtlRbRemoveNode
0x1400b2762  nop     dword ptr [rax+rax+00h]
0x1400b2767  lea     rdx, [rbx+18h]
0x1400b276b  lea     rcx, [rdi+500h]
0x1400b2772  call    cs:__imp_RtlRbRemoveNode
0x1400b2779  nop     dword ptr [rax+rax+00h]
0x1400b277e  dec     qword ptr [rdi+510h]
0x1400b2785  mov     rcx, rdi
0x1400b2788  call    VidObjectLockRelease
0x1400b278d  xor     r9d, r9d
0x1400b2790  mov     [rsp+38h+var_10], 1
0x1400b2795  xor     r8d, r8d
0x1400b2798  mov     [rsp+38h+var_18], 1
0x1400b279d  mov     rdx, rbx
0x1400b27a0  mov     rcx, rdi
0x1400b27a3  call    VsmmPhuStoreItemDataSet
0x1400b27a8  mov     edx, 6D4D6456h; Tag
0x1400b27ad  mov     rcx, rbx; P
0x1400b27b0  call    cs:__imp_ExFreePoolWithTag
0x1400b27b7  nop     dword ptr [rax+rax+00h]
0x1400b27bc  mov     edx, 40h ; '@'
0x1400b27c1  mov     rcx, rdi
0x1400b27c4  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b27c9  mov     rbx, [rsp+38h+arg_0]
0x1400b27ce  add     rsp, 30h
0x1400b27d2  pop     rdi
0x1400b27d3  retn
```
