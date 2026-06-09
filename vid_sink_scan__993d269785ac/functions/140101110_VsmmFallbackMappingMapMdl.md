# VsmmFallbackMappingMapMdl

- ea: `0x140101110`
- end: `0x140101183`
- name: `VsmmFallbackMappingMapMdl`
- size: `115`
- prototype: `PVOID __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400d4fcc`
- `0x1400d50e0`
- `0x1400e2398`
- `0x1400e832c`

## callees

- `0x1400087b8`
- `0x140101110`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14010113d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14010113d`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14010116b`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14010116b`

## pseudocode

```c
PVOID __fastcall VsmmFallbackMappingMapMdl(_QWORD *a1)
{
  struct _MDL *v1; // rdi
  PVOID result; // rax

  v1 = (struct _MDL *)a1[2];
  result = MmMapLockedPagesSpecifyCache(v1, 0, MmCached, 0, 0, 0x40000010u);
  if ( !result )
  {
    VidPushLockAcquireExclusive(*a1);
    return MmMapLockedPagesWithReservedMapping(*(PVOID *)(*a1 + 16LL), 0x6D4D6456u, v1, MmCached);
  }
  return result;
}

```

## disassembly

```asm
0x140101110  mov     [rsp+arg_0], rbx
0x140101115  push    rdi
0x140101116  sub     rsp, 30h
0x14010111a  mov     rdi, [rcx+10h]
0x14010111e  xor     r9d, r9d; RequestedAddress
0x140101121  mov     rbx, rcx
0x140101124  mov     [rsp+38h+Priority], 40000010h; Priority
0x14010112c  xor     edx, edx; AccessMode
0x14010112e  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140101136  mov     rcx, rdi; MemoryDescriptorList
0x140101139  lea     r8d, [r9+1]; CacheType
0x14010113d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140101144  nop     dword ptr [rax+rax+00h]
0x140101149  test    rax, rax
0x14010114c  jnz     short loc_140101177
0x14010114e  mov     rcx, [rbx]
0x140101151  call    VidPushLockAcquireExclusive
0x140101156  mov     rcx, [rbx]
0x140101159  mov     r9d, 1; CacheType
0x14010115f  mov     r8, rdi; MemoryDescriptorList
0x140101162  mov     edx, 6D4D6456h; PoolTag
0x140101167  mov     rcx, [rcx+10h]; MappingAddress
0x14010116b  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140101172  nop     dword ptr [rax+rax+00h]
0x140101177  mov     rbx, [rsp+38h+arg_0]
0x14010117c  add     rsp, 30h
0x140101180  pop     rdi
0x140101181  retn
```
