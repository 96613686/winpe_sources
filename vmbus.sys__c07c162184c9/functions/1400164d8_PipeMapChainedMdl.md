# PipeMapChainedMdl

- ea: `0x1400164d8`
- end: `0x140016534`
- name: `PipeMapChainedMdl`
- size: `92`
- prototype: `__int64 __fastcall(PMDL MemoryDescriptorList)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001560`
- `0x140016ab0`

## callees

- `0x1400164d8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001650e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001650e`

## pseudocode

```c
__int64 __fastcall PipeMapChainedMdl(PMDL MemoryDescriptorList)
{
  PVOID MappedSystemVa; // rax

  while ( MemoryDescriptorList )
  {
    if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
      MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
      return 3221225626LL;
    MemoryDescriptorList = MemoryDescriptorList->Next;
  }
  return 0;
}

```

## disassembly

```asm
0x1400164d8  push    rbx
0x1400164da  sub     rsp, 30h
0x1400164de  mov     rbx, rcx
0x1400164e1  test    rbx, rbx
0x1400164e4  jz      short loc_14001652B
0x1400164e6  test    byte ptr [rbx+0Ah], 5
0x1400164ea  jz      short loc_1400164F2
0x1400164ec  mov     rax, [rbx+18h]
0x1400164f0  jmp     short loc_14001651A
0x1400164f2  xor     r9d, r9d; RequestedAddress
0x1400164f5  mov     [rsp+38h+Priority], 40000010h; Priority
0x1400164fd  xor     edx, edx; AccessMode
0x1400164ff  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140016507  mov     rcx, rbx; MemoryDescriptorList
0x14001650a  lea     r8d, [r9+1]; CacheType
0x14001650e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140016515  nop     dword ptr [rax+rax+00h]
0x14001651a  test    rax, rax
0x14001651d  jz      short loc_140016524
0x14001651f  mov     rbx, [rbx]
0x140016522  jmp     short loc_1400164E1
0x140016524  mov     eax, 0C000009Ah
0x140016529  jmp     short loc_14001652D
0x14001652b  xor     eax, eax
0x14001652d  add     rsp, 30h
0x140016531  pop     rbx
0x140016532  retn
```
