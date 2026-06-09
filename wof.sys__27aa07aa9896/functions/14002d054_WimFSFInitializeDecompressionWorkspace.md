# WimFSFInitializeDecompressionWorkspace

- ea: `0x14002d054`
- end: `0x14002d219`
- name: `WimFSFInitializeDecompressionWorkspace`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002c58c`

## callees

- `0x14000cee8`
- `0x140011260`
- `0x14002d054`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d100`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d1b4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d1f4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d100`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d1b4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d1f4`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14002d097`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14002d097`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002d136`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002d17f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002d136`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002d17f`

## pseudocode

```c
__int64 __fastcall WimFSFInitializeDecompressionWorkspace(__int64 a1)
{
  int v1; // eax
  unsigned int CompressionWorkSpaceSize; // ebx
  ULONG DecodeBufferSize; // r8d
  USHORT v5; // cx
  SIZE_T Size; // rax
  int v7; // ecx
  unsigned int v8; // eax
  ULONG CompressFragmentWorkSpaceSize; // [rsp+50h] [rbp+8h] BYREF
  ULONG CompressBufferWorkSpaceSize; // [rsp+58h] [rbp+10h] BYREF

  v1 = *(_DWORD *)(a1 + 96);
  CompressionWorkSpaceSize = 0;
  DecodeBufferSize = 0;
  CompressFragmentWorkSpaceSize = 0;
  v5 = 2;
  if ( (v1 & 2) == 0 )
    return CompressionWorkSpaceSize;
  if ( (v1 & 0xFF000000) != 0 )
    goto LABEL_5;
  if ( (v1 & 0x200000) != 0 )
  {
    v5 = 4;
LABEL_5:
    CompressBufferWorkSpaceSize = 0;
    CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                                 v5,
                                 &CompressBufferWorkSpaceSize,
                                 &CompressFragmentWorkSpaceSize);
    if ( (CompressionWorkSpaceSize & 0x80000000) != 0 )
      return CompressionWorkSpaceSize;
    DecodeBufferSize = CompressFragmentWorkSpaceSize;
    goto LABEL_10;
  }
  if ( (v1 & 0x40000) != 0 )
  {
    DecodeBufferSize = LZX_GetDecodeBufferSize(*(unsigned int *)(a1 + 104));
    CompressFragmentWorkSpaceSize = DecodeBufferSize;
  }
  else if ( (v1 & 0x20000) == 0 )
  {
    return (unsigned int)-1073741217;
  }
LABEL_10:
  Size = DecodeBufferSize + *(_DWORD *)(a1 + 104);
  *(_DWORD *)(a1 + 112) = DecodeBufferSize;
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 128), 0, 0, 0, Size, 0x77647077u, 0);
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 640), 0, 0, 0x200u, 0x80u, 0x69777077u, 0);
  v7 = 0x8000;
  if ( *(_DWORD *)(a1 + 104) > 0x8000u )
    v7 = *(_DWORD *)(a1 + 104);
  *(_DWORD *)(a1 + 448) = v7;
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 768), 0, 0, 0x200u, 0x120u, 0x78637077u, 0);
  ExInitializePagedLookasideList(
    (PPAGED_LOOKASIDE_LIST)(a1 + 512),
    0,
    0,
    0,
    *(unsigned int *)(a1 + 448),
    0x64727077u,
    0);
  v8 = XpressDecodeAllocationSize();
  *(_DWORD *)(a1 + 256) = v8;
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 320), 0, 0, 0, v8 + 4LL, 0x70787077u, 0);
  *(_DWORD *)(a1 + 100) |= 1u;
  return CompressionWorkSpaceSize;
}

```

## disassembly

```asm
0x14002d054  mov     [rsp+arg_10], rbx
0x14002d059  push    rdi
0x14002d05a  sub     rsp, 40h
0x14002d05e  mov     eax, [rcx+60h]
0x14002d061  xor     ebx, ebx
0x14002d063  xor     r8d, r8d
0x14002d066  mov     rdi, rcx
0x14002d069  mov     [rsp+48h+CompressFragmentWorkSpaceSize], r8d
0x14002d06e  lea     ecx, [rbx+2]
0x14002d071  test    cl, al
0x14002d073  jz      loc_14002D20B
0x14002d079  test    eax, 0FF000000h
0x14002d07e  jnz     short loc_14002D089
0x14002d080  bt      eax, 15h
0x14002d084  jnb     short loc_14002D0B4
0x14002d086  lea     ecx, [rbx+4]; CompressionFormatAndEngine
0x14002d089  lea     r8, [rsp+48h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14002d08e  mov     [rsp+48h+CompressBufferWorkSpaceSize], ebx
0x14002d092  lea     rdx, [rsp+48h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14002d097  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14002d09e  nop     dword ptr [rax+rax+00h]
0x14002d0a3  mov     ebx, eax
0x14002d0a5  test    eax, eax
0x14002d0a7  js      loc_14002D20B
0x14002d0ad  mov     r8d, [rsp+48h+CompressFragmentWorkSpaceSize]
0x14002d0b2  jmp     short loc_14002D0D5
0x14002d0b4  bt      eax, 12h
0x14002d0b8  jnb     short loc_14002D0CB
0x14002d0ba  mov     ecx, [rdi+68h]
0x14002d0bd  call    LZX_GetDecodeBufferSize
0x14002d0c2  mov     r8d, eax
0x14002d0c5  mov     [rsp+48h+CompressFragmentWorkSpaceSize], eax
0x14002d0c9  jmp     short loc_14002D0D5
0x14002d0cb  bt      eax, 11h
0x14002d0cf  jnb     loc_14002D206
0x14002d0d5  mov     eax, [rdi+68h]
0x14002d0d8  lea     rcx, [rdi+80h]; Lookaside
0x14002d0df  add     eax, r8d
0x14002d0e2  mov     [rdi+70h], r8d
0x14002d0e6  xor     edx, edx; Allocate
0x14002d0e8  xor     r8d, r8d; Free
0x14002d0eb  mov     [rsp+48h+Depth], dx; Depth
0x14002d0f0  xor     r9d, r9d; Flags
0x14002d0f3  mov     [rsp+48h+Tag], 77647077h; Tag
0x14002d0fb  mov     [rsp+48h+Size], rax; Size
0x14002d100  call    cs:__imp_ExInitializePagedLookasideList
0x14002d107  nop     dword ptr [rax+rax+00h]
0x14002d10c  xor     eax, eax
0x14002d10e  lea     rcx, [rdi+280h]; Lookaside
0x14002d115  mov     [rsp+48h+Depth], ax; Depth
0x14002d11a  mov     r9d, 200h; Flags
0x14002d120  mov     [rsp+48h+Tag], 69777077h; Tag
0x14002d128  xor     r8d, r8d; Free
0x14002d12b  xor     edx, edx; Allocate
0x14002d12d  mov     [rsp+48h+Size], 80h; Size
0x14002d136  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002d13d  nop     dword ptr [rax+rax+00h]
0x14002d142  mov     eax, [rdi+68h]
0x14002d145  mov     ecx, 8000h
0x14002d14a  cmp     eax, ecx
0x14002d14c  mov     r9d, 200h; Flags
0x14002d152  cmova   ecx, eax
0x14002d155  xor     eax, eax
0x14002d157  mov     [rsp+48h+Depth], ax; Depth
0x14002d15c  xor     r8d, r8d; Free
0x14002d15f  mov     [rdi+1C0h], ecx
0x14002d165  xor     edx, edx; Allocate
0x14002d167  mov     [rsp+48h+Tag], 78637077h; Tag
0x14002d16f  lea     rcx, [rdi+300h]; Lookaside
0x14002d176  mov     [rsp+48h+Size], 120h; Size
0x14002d17f  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002d186  nop     dword ptr [rax+rax+00h]
0x14002d18b  mov     edx, [rdi+1C0h]
0x14002d191  lea     rcx, [rdi+200h]; Lookaside
0x14002d198  xor     eax, eax
0x14002d19a  xor     r9d, r9d; Flags
0x14002d19d  mov     [rsp+48h+Depth], ax; Depth
0x14002d1a2  xor     r8d, r8d; Free
0x14002d1a5  mov     [rsp+48h+Tag], 64727077h; Tag
0x14002d1ad  mov     [rsp+48h+Size], rdx; Size
0x14002d1b2  xor     edx, edx; Allocate
0x14002d1b4  call    cs:__imp_ExInitializePagedLookasideList
0x14002d1bb  nop     dword ptr [rax+rax+00h]
0x14002d1c0  call    XpressDecodeAllocationSize
0x14002d1c5  mov     edx, eax
0x14002d1c7  lea     rcx, [rdi+140h]; Lookaside
0x14002d1ce  mov     [rdi+100h], edx
0x14002d1d4  xor     eax, eax
0x14002d1d6  add     rdx, 4
0x14002d1da  mov     [rsp+48h+Depth], ax; Depth
0x14002d1df  mov     [rsp+48h+Tag], 70787077h; Tag
0x14002d1e7  xor     r9d, r9d; Flags
0x14002d1ea  mov     [rsp+48h+Size], rdx; Size
0x14002d1ef  xor     r8d, r8d; Free
0x14002d1f2  xor     edx, edx; Allocate
0x14002d1f4  call    cs:__imp_ExInitializePagedLookasideList
0x14002d1fb  nop     dword ptr [rax+rax+00h]
0x14002d200  or      dword ptr [rdi+64h], 1
0x14002d204  jmp     short loc_14002D20B
0x14002d206  mov     ebx, 0C000025Fh
0x14002d20b  mov     eax, ebx
0x14002d20d  mov     rbx, [rsp+48h+arg_10]
0x14002d212  add     rsp, 40h
0x14002d216  pop     rdi
0x14002d217  retn
```
