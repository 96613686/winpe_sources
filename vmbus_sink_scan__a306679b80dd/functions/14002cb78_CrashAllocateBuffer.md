# CrashAllocateBuffer

- ea: `0x14002cb78`
- end: `0x14002cc2a`
- name: `CrashAllocateBuffer`
- size: `178`
- prototype: `__int64 __fastcall(__int64, SIZE_T, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002cc30`
- `0x14002d128`

## callees

- `0x140014a40`
- `0x14002cb78`
- `0x14002ce90`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x14002cba4`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x14002cba4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002cc0a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002cc0a`

## pseudocode

```c
__int64 __fastcall CrashAllocateBuffer(__int64 a1, SIZE_T a2, char a3)
{
  __int64 *PagesForMdl; // rax
  int MdlHostVisible; // ebx
  struct _MDL *v7; // rcx
  PVOID MappedSystemVa; // rax

  PagesForMdl = (__int64 *)MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, a2, MmCached, 4u);
  *(_QWORD *)a1 = PagesForMdl;
  if ( !PagesForMdl )
  {
    MdlHostVisible = -1073741670;
LABEL_3:
    CrashFreeBuffer(a1);
    return (unsigned int)MdlHostVisible;
  }
  if ( a3 )
  {
    MdlHostVisible = XPartVisMakeMdlHostVisible(PagesForMdl, 1);
    if ( MdlHostVisible < 0 )
      goto LABEL_3;
    *(_BYTE *)(a1 + 16) = 1;
  }
  v7 = *(struct _MDL **)a1;
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 10LL) & 5) != 0 )
    MappedSystemVa = v7->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000010u);
  *(_QWORD *)(a1 + 8) = MappedSystemVa;
  return 0;
}

```

## disassembly

```asm
0x14002cb78  mov     [rsp+arg_0], rbx
0x14002cb7d  push    rdi
0x14002cb7e  sub     rsp, 30h
0x14002cb82  mov     bl, r8b
0x14002cb85  mov     [rsp+38h+Flags], 4; Flags
0x14002cb8d  mov     rdi, rcx
0x14002cb90  mov     [rsp+38h+CacheType], 1; CacheType
0x14002cb98  mov     r9, rdx; TotalBytes
0x14002cb9b  xor     ecx, ecx; LowAddress
0x14002cb9d  xor     r8d, r8d; SkipBytes
0x14002cba0  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x14002cba4  call    cs:__imp_MmAllocatePagesForMdlEx
0x14002cbab  nop     dword ptr [rax+rax+00h]
0x14002cbb0  mov     [rdi], rax
0x14002cbb3  test    rax, rax
0x14002cbb6  jnz     short loc_14002CBC7
0x14002cbb8  mov     ebx, 0C000009Ah
0x14002cbbd  mov     rcx, rdi
0x14002cbc0  call    CrashFreeBuffer
0x14002cbc5  jmp     short loc_14002CC1C
0x14002cbc7  test    bl, bl
0x14002cbc9  jz      short loc_14002CBE2
0x14002cbcb  mov     edx, 1
0x14002cbd0  mov     rcx, rax
0x14002cbd3  call    XPartVisMakeMdlHostVisible
0x14002cbd8  mov     ebx, eax
0x14002cbda  test    eax, eax
0x14002cbdc  js      short loc_14002CBBD
0x14002cbde  mov     byte ptr [rdi+10h], 1
0x14002cbe2  mov     rcx, [rdi]; MemoryDescriptorList
0x14002cbe5  test    byte ptr [rcx+0Ah], 5
0x14002cbe9  jz      short loc_14002CBF1
0x14002cbeb  mov     rax, [rcx+18h]
0x14002cbef  jmp     short loc_14002CC16
0x14002cbf1  xor     r9d, r9d; RequestedAddress
0x14002cbf4  mov     [rsp+38h+Flags], 40000010h; Priority
0x14002cbfc  xor     edx, edx; AccessMode
0x14002cbfe  mov     [rsp+38h+CacheType], 0; BugCheckOnFailure
0x14002cc06  lea     r8d, [r9+1]; CacheType
0x14002cc0a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002cc11  nop     dword ptr [rax+rax+00h]
0x14002cc16  mov     [rdi+8], rax
0x14002cc1a  xor     ebx, ebx
0x14002cc1c  mov     eax, ebx
0x14002cc1e  mov     rbx, [rsp+38h+arg_0]
0x14002cc23  add     rsp, 30h
0x14002cc27  pop     rdi
0x14002cc28  retn
```
