# WimFSFInitializeDecompressionWorkspace

- ea: `0x14002d004`
- end: `0x14002d1c9`
- name: `WimFSFInitializeDecompressionWorkspace`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002c53c`

## callees

- `0x14000cee8`
- `0x140011260`
- `0x14002d004`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d0b0`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d164`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d1a4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d0b0`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d164`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002d1a4`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14002d047`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14002d047`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002d0e6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002d12f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002d0e6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002d12f`

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
0x14002d004  mov     [rsp+arg_10], rbx
0x14002d009  push    rdi
0x14002d00a  sub     rsp, 40h
0x14002d00e  mov     eax, [rcx+60h]
0x14002d011  xor     ebx, ebx
0x14002d013  xor     r8d, r8d
0x14002d016  mov     rdi, rcx
0x14002d019  mov     [rsp+48h+CompressFragmentWorkSpaceSize], r8d
0x14002d01e  lea     ecx, [rbx+2]
0x14002d021  test    cl, al
0x14002d023  jz      loc_14002D1BB
0x14002d029  test    eax, 0FF000000h
0x14002d02e  jnz     short loc_14002D039
0x14002d030  bt      eax, 15h
0x14002d034  jnb     short loc_14002D064
0x14002d036  lea     ecx, [rbx+4]; CompressionFormatAndEngine
0x14002d039  lea     r8, [rsp+48h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14002d03e  mov     [rsp+48h+CompressBufferWorkSpaceSize], ebx
0x14002d042  lea     rdx, [rsp+48h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14002d047  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14002d04e  nop     dword ptr [rax+rax+00h]
0x14002d053  mov     ebx, eax
0x14002d055  test    eax, eax
0x14002d057  js      loc_14002D1BB
0x14002d05d  mov     r8d, [rsp+48h+CompressFragmentWorkSpaceSize]
0x14002d062  jmp     short loc_14002D085
0x14002d064  bt      eax, 12h
0x14002d068  jnb     short loc_14002D07B
0x14002d06a  mov     ecx, [rdi+68h]
0x14002d06d  call    LZX_GetDecodeBufferSize
0x14002d072  mov     r8d, eax
0x14002d075  mov     [rsp+48h+CompressFragmentWorkSpaceSize], eax
0x14002d079  jmp     short loc_14002D085
0x14002d07b  bt      eax, 11h
0x14002d07f  jnb     loc_14002D1B6
0x14002d085  mov     eax, [rdi+68h]
0x14002d088  lea     rcx, [rdi+80h]; Lookaside
0x14002d08f  add     eax, r8d
0x14002d092  mov     [rdi+70h], r8d
0x14002d096  xor     edx, edx; Allocate
0x14002d098  xor     r8d, r8d; Free
0x14002d09b  mov     [rsp+48h+Depth], dx; Depth
0x14002d0a0  xor     r9d, r9d; Flags
0x14002d0a3  mov     [rsp+48h+Tag], 77647077h; Tag
0x14002d0ab  mov     [rsp+48h+Size], rax; Size
0x14002d0b0  call    cs:__imp_ExInitializePagedLookasideList
0x14002d0b7  nop     dword ptr [rax+rax+00h]
0x14002d0bc  xor     eax, eax
0x14002d0be  lea     rcx, [rdi+280h]; Lookaside
0x14002d0c5  mov     [rsp+48h+Depth], ax; Depth
0x14002d0ca  mov     r9d, 200h; Flags
0x14002d0d0  mov     [rsp+48h+Tag], 69777077h; Tag
0x14002d0d8  xor     r8d, r8d; Free
0x14002d0db  xor     edx, edx; Allocate
0x14002d0dd  mov     [rsp+48h+Size], 80h; Size
0x14002d0e6  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002d0ed  nop     dword ptr [rax+rax+00h]
0x14002d0f2  mov     eax, [rdi+68h]
0x14002d0f5  mov     ecx, 8000h
0x14002d0fa  cmp     eax, ecx
0x14002d0fc  mov     r9d, 200h; Flags
0x14002d102  cmova   ecx, eax
0x14002d105  xor     eax, eax
0x14002d107  mov     [rsp+48h+Depth], ax; Depth
0x14002d10c  xor     r8d, r8d; Free
0x14002d10f  mov     [rdi+1C0h], ecx
0x14002d115  xor     edx, edx; Allocate
0x14002d117  mov     [rsp+48h+Tag], 78637077h; Tag
0x14002d11f  lea     rcx, [rdi+300h]; Lookaside
0x14002d126  mov     [rsp+48h+Size], 120h; Size
0x14002d12f  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002d136  nop     dword ptr [rax+rax+00h]
0x14002d13b  mov     edx, [rdi+1C0h]
0x14002d141  lea     rcx, [rdi+200h]; Lookaside
0x14002d148  xor     eax, eax
0x14002d14a  xor     r9d, r9d; Flags
0x14002d14d  mov     [rsp+48h+Depth], ax; Depth
0x14002d152  xor     r8d, r8d; Free
0x14002d155  mov     [rsp+48h+Tag], 64727077h; Tag
0x14002d15d  mov     [rsp+48h+Size], rdx; Size
0x14002d162  xor     edx, edx; Allocate
0x14002d164  call    cs:__imp_ExInitializePagedLookasideList
0x14002d16b  nop     dword ptr [rax+rax+00h]
0x14002d170  call    XpressDecodeAllocationSize
0x14002d175  mov     edx, eax
0x14002d177  lea     rcx, [rdi+140h]; Lookaside
0x14002d17e  mov     [rdi+100h], edx
0x14002d184  xor     eax, eax
0x14002d186  add     rdx, 4
0x14002d18a  mov     [rsp+48h+Depth], ax; Depth
0x14002d18f  mov     [rsp+48h+Tag], 70787077h; Tag
0x14002d197  xor     r9d, r9d; Flags
0x14002d19a  mov     [rsp+48h+Size], rdx; Size
0x14002d19f  xor     r8d, r8d; Free
0x14002d1a2  xor     edx, edx; Allocate
0x14002d1a4  call    cs:__imp_ExInitializePagedLookasideList
0x14002d1ab  nop     dword ptr [rax+rax+00h]
0x14002d1b0  or      dword ptr [rdi+64h], 1
0x14002d1b4  jmp     short loc_14002D1BB
0x14002d1b6  mov     ebx, 0C000025Fh
0x14002d1bb  mov     eax, ebx
0x14002d1bd  mov     rbx, [rsp+48h+arg_10]
0x14002d1c2  add     rsp, 40h
0x14002d1c6  pop     rdi
0x14002d1c7  retn
```
