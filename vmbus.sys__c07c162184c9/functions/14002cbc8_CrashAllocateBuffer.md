# CrashAllocateBuffer

- ea: `0x14002cbc8`
- end: `0x14002cc7a`
- name: `CrashAllocateBuffer`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002cc80`
- `0x14002d178`

## callees

- `0x140014a40`
- `0x14002cbc8`
- `0x14002cee0`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x14002cbf4`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x14002cbf4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002cc5a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002cc5a`

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
0x14002cbc8  mov     [rsp+arg_0], rbx
0x14002cbcd  push    rdi
0x14002cbce  sub     rsp, 30h
0x14002cbd2  mov     bl, r8b
0x14002cbd5  mov     [rsp+38h+Flags], 4; Flags
0x14002cbdd  mov     rdi, rcx
0x14002cbe0  mov     [rsp+38h+CacheType], 1; CacheType
0x14002cbe8  mov     r9, rdx; TotalBytes
0x14002cbeb  xor     ecx, ecx; LowAddress
0x14002cbed  xor     r8d, r8d; SkipBytes
0x14002cbf0  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x14002cbf4  call    cs:__imp_MmAllocatePagesForMdlEx
0x14002cbfb  nop     dword ptr [rax+rax+00h]
0x14002cc00  mov     [rdi], rax
0x14002cc03  test    rax, rax
0x14002cc06  jnz     short loc_14002CC17
0x14002cc08  mov     ebx, 0C000009Ah
0x14002cc0d  mov     rcx, rdi
0x14002cc10  call    CrashFreeBuffer
0x14002cc15  jmp     short loc_14002CC6C
0x14002cc17  test    bl, bl
0x14002cc19  jz      short loc_14002CC32
0x14002cc1b  mov     edx, 1
0x14002cc20  mov     rcx, rax
0x14002cc23  call    XPartVisMakeMdlHostVisible
0x14002cc28  mov     ebx, eax
0x14002cc2a  test    eax, eax
0x14002cc2c  js      short loc_14002CC0D
0x14002cc2e  mov     byte ptr [rdi+10h], 1
0x14002cc32  mov     rcx, [rdi]; MemoryDescriptorList
0x14002cc35  test    byte ptr [rcx+0Ah], 5
0x14002cc39  jz      short loc_14002CC41
0x14002cc3b  mov     rax, [rcx+18h]
0x14002cc3f  jmp     short loc_14002CC66
0x14002cc41  xor     r9d, r9d; RequestedAddress
0x14002cc44  mov     [rsp+38h+Flags], 40000010h; Priority
0x14002cc4c  xor     edx, edx; AccessMode
0x14002cc4e  mov     [rsp+38h+CacheType], 0; BugCheckOnFailure
0x14002cc56  lea     r8d, [r9+1]; CacheType
0x14002cc5a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002cc61  nop     dword ptr [rax+rax+00h]
0x14002cc66  mov     [rdi+8], rax
0x14002cc6a  xor     ebx, ebx
0x14002cc6c  mov     eax, ebx
0x14002cc6e  mov     rbx, [rsp+38h+arg_0]
0x14002cc73  add     rsp, 30h
0x14002cc77  pop     rdi
0x14002cc78  retn
```
