# CrashMarkMdl

- ea: `0x14000a6b4`
- end: `0x14000a751`
- name: `CrashMarkMdl`
- size: `157`
- prototype: `void __fastcall(PMDL MemoryDescriptorList)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a760`

## callees

- `0x14000a6b4`

## import_xrefs

- `ntoskrnl!PoSetHiberRange` at `0x14000a6dc`
- `ntoskrnl!PoSetHiberRange` at `0x14000a732`
- `ntoskrnl!PoSetHiberRange` at `0x14000a6dc`
- `ntoskrnl!PoSetHiberRange` at `0x14000a732`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a710`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a710`

## pseudocode

```c
void __fastcall CrashMarkMdl(PMDL MemoryDescriptorList)
{
  PMDL v1; // rbx
  PVOID MappedSystemVa; // rax

  if ( MemoryDescriptorList )
  {
    v1 = MemoryDescriptorList;
    do
    {
      PoSetHiberRange(0, 0x10000u, v1, v1->Size, 0x73626D56u);
      if ( (v1->MdlFlags & 5) != 0 )
        MappedSystemVa = v1->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v1, 0, MmCached, 0, 0, 0x40000010u);
      PoSetHiberRange(0, 0x10000u, MappedSystemVa, v1->ByteCount, 0x73626D56u);
      v1 = v1->Next;
    }
    while ( v1 );
  }
}

```

## disassembly

```asm
0x14000a6b4  test    rcx, rcx
0x14000a6b7  jz      locret_14000A74F
0x14000a6bd  push    rbx
0x14000a6be  sub     rsp, 30h
0x14000a6c2  mov     rbx, rcx
0x14000a6c5  movsx   r9, word ptr [rbx+8]; Length
0x14000a6ca  mov     r8, rbx; Address
0x14000a6cd  mov     edx, 10000h; Flags
0x14000a6d2  mov     [rsp+38h+Tag], 73626D56h; Tag
0x14000a6da  xor     ecx, ecx; MemoryMap
0x14000a6dc  call    cs:__imp_PoSetHiberRange
0x14000a6e3  nop     dword ptr [rax+rax+00h]
0x14000a6e8  test    byte ptr [rbx+0Ah], 5
0x14000a6ec  jz      short loc_14000A6F4
0x14000a6ee  mov     rax, [rbx+18h]
0x14000a6f2  jmp     short loc_14000A71C
0x14000a6f4  xor     r9d, r9d; RequestedAddress
0x14000a6f7  mov     [rsp+38h+Priority], 40000010h; Priority
0x14000a6ff  xor     edx, edx; AccessMode
0x14000a701  mov     [rsp+38h+Tag], 0; BugCheckOnFailure
0x14000a709  mov     rcx, rbx; MemoryDescriptorList
0x14000a70c  lea     r8d, [r9+1]; CacheType
0x14000a710  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a717  nop     dword ptr [rax+rax+00h]
0x14000a71c  mov     r9d, [rbx+28h]; Length
0x14000a720  mov     r8, rax; Address
0x14000a723  mov     edx, 10000h; Flags
0x14000a728  mov     [rsp+38h+Tag], 73626D56h; Tag
0x14000a730  xor     ecx, ecx; MemoryMap
0x14000a732  call    cs:__imp_PoSetHiberRange
0x14000a739  nop     dword ptr [rax+rax+00h]
0x14000a73e  mov     rbx, [rbx]
0x14000a741  test    rbx, rbx
0x14000a744  jnz     loc_14000A6C5
0x14000a74a  add     rsp, 30h
0x14000a74e  pop     rbx
0x14000a74f  retn
```
