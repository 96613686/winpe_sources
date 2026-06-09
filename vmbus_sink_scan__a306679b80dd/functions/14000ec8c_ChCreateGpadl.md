# ChCreateGpadl

- ea: `0x14000ec8c`
- end: `0x14000ed8a`
- name: `ChCreateGpadl`
- size: `254`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b70`
- `0x14000b4f0`
- `0x14002c780`

## callees

- `0x14000ec8c`
- `0x14000f158`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ed69`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ed69`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x14000ecf2`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x14000ecf2`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000ed58`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000ed58`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000ed49`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000ed49`

## pseudocode

```c
__int64 __fastcall ChCreateGpadl(__int64 a1, int a2, __int64 a3, __int64 a4, int a5)
{
  PMDL PagesForMdl; // rax
  PMDL v10; // rbx
  int GpadlFromNtmdl; // edi

  if ( (a5 & 0xFFFFFFFE) != 0 )
    return 3221225485LL;
  if ( *(_DWORD *)(a1 + 728) == 3 || *(_BYTE *)(a1 + 733) )
    return 3221226166LL;
  PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, (unsigned int)(a2 << 12), MmCached, 4u);
  v10 = PagesForMdl;
  if ( !PagesForMdl )
    return 3221225626LL;
  GpadlFromNtmdl = ChpCreateGpadlFromNtmdl(a1, PagesForMdl, 0, 0, a3, a4, 8 * (a5 & 1u) + 5);
  if ( GpadlFromNtmdl < 0 )
  {
    if ( (v10->MdlFlags & 1) != 0 )
      MmUnmapLockedPages(v10->MappedSystemVa, v10);
    MmFreePagesFromMdl(v10);
    ExFreePoolWithTag(v10, 0);
  }
  return (unsigned int)GpadlFromNtmdl;
}

```

## disassembly

```asm
0x14000ec8c  push    rbx
0x14000ec8e  push    rbp
0x14000ec8f  push    rsi
0x14000ec90  push    rdi
0x14000ec91  push    r14
0x14000ec93  sub     rsp, 40h
0x14000ec97  mov     esi, [rsp+68h+arg_20]
0x14000ec9e  mov     rbp, r9
0x14000eca1  mov     r14, r8
0x14000eca4  mov     rdi, rcx
0x14000eca7  test    esi, 0FFFFFFFEh
0x14000ecad  jz      short loc_14000ECB9
0x14000ecaf  mov     eax, 0C000000Dh
0x14000ecb4  jmp     loc_14000ED7E
0x14000ecb9  cmp     dword ptr [rcx+2D8h], 3
0x14000ecc0  jz      loc_14000ED79
0x14000ecc6  cmp     byte ptr [rcx+2DDh], 0
0x14000eccd  jnz     loc_14000ED79
0x14000ecd3  shl     edx, 0Ch
0x14000ecd6  xor     ecx, ecx; LowAddress
0x14000ecd8  mov     r9d, edx; TotalBytes
0x14000ecdb  xor     r8d, r8d; SkipBytes
0x14000ecde  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x14000ece2  mov     [rsp+68h+Flags], 4; Flags
0x14000ecea  mov     [rsp+68h+CacheType], 1; CacheType
0x14000ecf2  call    cs:__imp_MmAllocatePagesForMdlEx
0x14000ecf9  nop     dword ptr [rax+rax+00h]
0x14000ecfe  mov     rbx, rax
0x14000ed01  test    rax, rax
0x14000ed04  jnz     short loc_14000ED0D
0x14000ed06  mov     eax, 0C000009Ah
0x14000ed0b  jmp     short loc_14000ED7E
0x14000ed0d  and     esi, 1
0x14000ed10  xor     r9d, r9d
0x14000ed13  xor     r8d, r8d
0x14000ed16  mov     rdx, rbx
0x14000ed19  mov     rcx, rdi
0x14000ed1c  lea     eax, ds:5[rsi*8]
0x14000ed23  mov     [rsp+68h+var_38], eax
0x14000ed27  mov     qword ptr [rsp+68h+Flags], rbp
0x14000ed2c  mov     qword ptr [rsp+68h+CacheType], r14
0x14000ed31  call    ChpCreateGpadlFromNtmdl
0x14000ed36  mov     edi, eax
0x14000ed38  test    eax, eax
0x14000ed3a  jns     short loc_14000ED75
0x14000ed3c  test    byte ptr [rbx+0Ah], 1
0x14000ed40  jz      short loc_14000ED55
0x14000ed42  mov     rcx, [rbx+18h]; BaseAddress
0x14000ed46  mov     rdx, rbx; MemoryDescriptorList
0x14000ed49  call    cs:__imp_MmUnmapLockedPages
0x14000ed50  nop     dword ptr [rax+rax+00h]
0x14000ed55  mov     rcx, rbx; MemoryDescriptorList
0x14000ed58  call    cs:__imp_MmFreePagesFromMdl
0x14000ed5f  nop     dword ptr [rax+rax+00h]
0x14000ed64  xor     edx, edx; Tag
0x14000ed66  mov     rcx, rbx; P
0x14000ed69  call    cs:__imp_ExFreePoolWithTag
0x14000ed70  nop     dword ptr [rax+rax+00h]
0x14000ed75  mov     eax, edi
0x14000ed77  jmp     short loc_14000ED7E
0x14000ed79  mov     eax, 0C00002B6h
0x14000ed7e  add     rsp, 40h
0x14000ed82  pop     r14
0x14000ed84  pop     rdi
0x14000ed85  pop     rsi
0x14000ed86  pop     rbp
0x14000ed87  pop     rbx
0x14000ed88  retn
```
