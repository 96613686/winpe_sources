# WinHvpAllocateHypervisorVisiblePages

- ea: `0x140005af8`
- end: `0x140005bdd`
- name: `WinHvpAllocateHypervisorVisiblePages`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005be4`

## callees

- `0x140005af8`
- `0x140005e60`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x140005b56`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x140005b73`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x140005b56`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x140005b73`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005b9f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005b9f`

## pseudocode

```c
struct _MDL *__fastcall WinHvpAllocateHypervisorVisiblePages(int a1)
{
  unsigned int v1; // ebp
  SIZE_T v2; // r15
  unsigned int v3; // r14d
  __int64 v4; // r13
  struct _MDL *PagesForMdl; // rsi

  if ( !WinHvpConnected )
    return 0;
  v1 = a1 << 12;
  v2 = (unsigned int)(a1 << 12);
  v3 = 0;
  v4 = 0;
  while ( v3 < 4 )
  {
    v4 += 0x40000000;
    ++v3;
    v2 = v1;
    PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)(v4 - 1), 0, v1, MmCached, 0x24u);
    if ( PagesForMdl )
      goto LABEL_7;
  }
  PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, v2, MmCached, 0x24u);
  if ( !PagesForMdl )
    return 0;
LABEL_7:
  if ( !MmMapLockedPagesSpecifyCache(PagesForMdl, 0, MmCached, 0, 0, 0x40000020u) )
  {
    WinHvpReclaimAndFreeHypervisorVisiblePages(PagesForMdl);
    return 0;
  }
  return PagesForMdl;
}

```

## disassembly

```asm
0x140005af8  push    rbx
0x140005afa  push    rbp
0x140005afb  push    rsi
0x140005afc  push    rdi
0x140005afd  push    r13
0x140005aff  push    r14
0x140005b01  push    r15
0x140005b03  sub     rsp, 30h
0x140005b07  cmp     cs:WinHvpConnected, 0
0x140005b0e  mov     ebp, ecx
0x140005b10  jz      loc_140005BCB
0x140005b16  shl     ebp, 0Ch
0x140005b19  xor     ebx, ebx
0x140005b1b  xor     edi, edi
0x140005b1d  mov     r15d, ebp
0x140005b20  xor     r14d, r14d
0x140005b23  xor     r13d, r13d
0x140005b26  mov     [rsp+68h+Flags], 24h ; '$'; Flags
0x140005b2e  mov     r8, rbx; SkipBytes
0x140005b31  mov     [rsp+68h+CacheType], 1; CacheType
0x140005b39  mov     rcx, rdi; LowAddress
0x140005b3c  cmp     r14d, 4
0x140005b40  jnb     short loc_140005B6C
0x140005b42  add     r13, 40000000h
0x140005b49  mov     r9d, ebp; TotalBytes
0x140005b4c  inc     r14d
0x140005b4f  mov     r15d, ebp
0x140005b52  lea     rdx, [r13-1]; HighAddress
0x140005b56  call    cs:__imp_MmAllocatePagesForMdlEx
0x140005b5d  nop     dword ptr [rax+rax+00h]
0x140005b62  mov     rsi, rax
0x140005b65  test    rax, rax
0x140005b68  jz      short loc_140005B26
0x140005b6a  jmp     short loc_140005B87
0x140005b6c  mov     r9, r15; TotalBytes
0x140005b6f  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x140005b73  call    cs:__imp_MmAllocatePagesForMdlEx
0x140005b7a  nop     dword ptr [rax+rax+00h]
0x140005b7f  mov     rsi, rax
0x140005b82  test    rax, rax
0x140005b85  jz      short loc_140005BCB
0x140005b87  xor     r9d, r9d; RequestedAddress
0x140005b8a  mov     [rsp+68h+Flags], 40000020h; Priority
0x140005b92  xor     edx, edx; AccessMode
0x140005b94  mov     [rsp+68h+CacheType], ebx; BugCheckOnFailure
0x140005b98  mov     rcx, rsi; MemoryDescriptorList
0x140005b9b  lea     r8d, [r9+1]; CacheType
0x140005b9f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140005ba6  nop     dword ptr [rax+rax+00h]
0x140005bab  test    rax, rax
0x140005bae  jnz     short loc_140005BC6
0x140005bb0  test    rsi, rsi
0x140005bb3  jz      short loc_140005BC6
0x140005bb5  mov     dl, [rsp+68h+arg_20]
0x140005bbc  mov     rcx, rsi; MemoryDescriptorList
0x140005bbf  call    WinHvpReclaimAndFreeHypervisorVisiblePages
0x140005bc4  xor     esi, esi
0x140005bc6  mov     rax, rsi
0x140005bc9  jmp     short loc_140005BCD
0x140005bcb  xor     eax, eax
0x140005bcd  add     rsp, 30h
0x140005bd1  pop     r15
0x140005bd3  pop     r14
0x140005bd5  pop     r13
0x140005bd7  pop     rdi
0x140005bd8  pop     rsi
0x140005bd9  pop     rbp
0x140005bda  pop     rbx
0x140005bdb  retn
```
