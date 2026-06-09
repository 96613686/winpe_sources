# SmbCompressionRtlCompressHelper

- ea: `0x14002111c`
- end: `0x1400211f7`
- name: `SmbCompressionRtlCompressHelper`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020658`

## callees

- `0x140020484`
- `0x1400204a8`
- `0x14002111c`

## import_xrefs

- `ntoskrnl!RtlCompressBuffer` at `0x1400211b9`
- `ntoskrnl!RtlCompressBuffer` at `0x1400211b9`

## pseudocode

```c
__int64 __fastcall SmbCompressionRtlCompressHelper(
        __int16 *a1,
        char a2,
        UCHAR *a3,
        ULONG a4,
        UCHAR *CompressedBuffer,
        ULONG CompressedBufferSize,
        ULONG *FinalCompressedSize)
{
  __int16 v7; // ax
  USHORT v10; // bx
  void *WorkSpace; // rax
  void *v12; // rdi
  unsigned int v13; // ebx
  NTSTATUS v14; // eax
  __int64 v15; // rcx

  v7 = 2;
  if ( (a2 & 2) != 0 )
  {
    v10 = 3;
  }
  else
  {
    v10 = 4;
    if ( (a2 & 4) != 0 )
    {
      v7 = 3;
    }
    else if ( (a2 & 1) != 0 )
    {
      v10 = 2;
      v7 = 1;
    }
    else
    {
      if ( (a2 & 0x10) == 0 )
        return (unsigned int)-1073741217;
      v10 = 6;
      v7 = 5;
    }
  }
  *a1 = v7;
  WorkSpace = (void *)PplAllocateFromLookasideList();
  v12 = WorkSpace;
  if ( WorkSpace )
  {
    v14 = RtlCompressBuffer(
            v10,
            a3,
            a4,
            CompressedBuffer,
            CompressedBufferSize,
            0x1000u,
            FinalCompressedSize,
            WorkSpace);
    v13 = 0;
    if ( v14 != 279 )
      v13 = v14;
    if ( v13 == -1073741217 )
      v13 = -1073741811;
    PplFreeToLookasideList(v15, v12);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v13;
}

```

## disassembly

```asm
0x14002111c  push    rbx
0x14002111e  push    rbp
0x14002111f  push    rsi
0x140021120  push    rdi
0x140021121  sub     rsp, 48h
0x140021125  mov     eax, 2
0x14002112a  mov     esi, r9d
0x14002112d  mov     rbp, r8
0x140021130  test    al, dl
0x140021132  jz      short loc_140021139
0x140021134  lea     ebx, [rax+1]
0x140021137  jmp     short loc_14002116C
0x140021139  mov     ebx, 4
0x14002113e  test    bl, dl
0x140021140  jz      short loc_140021147
0x140021142  lea     eax, [rbx-1]
0x140021145  jmp     short loc_14002116C
0x140021147  mov     r8d, 1
0x14002114d  test    r8b, dl
0x140021150  jz      short loc_14002115B
0x140021152  movzx   ebx, ax
0x140021155  movzx   eax, r8w
0x140021159  jmp     short loc_14002116C
0x14002115b  test    dl, 10h
0x14002115e  jz      loc_1400211E6
0x140021164  mov     ebx, 6
0x140021169  lea     eax, [rbx-1]
0x14002116c  mov     [rcx], ax
0x14002116f  call    PplAllocateFromLookasideList
0x140021174  mov     rdi, rax
0x140021177  test    rax, rax
0x14002117a  jnz     short loc_140021183
0x14002117c  mov     ebx, 0C000009Ah
0x140021181  jmp     short loc_1400211EB
0x140021183  mov     rax, [rsp+68h+arg_30]
0x14002118b  mov     r8d, esi; UncompressedBufferSize
0x14002118e  mov     r9, [rsp+68h+CompressedBuffer]; CompressedBuffer
0x140021196  mov     rdx, rbp; UncompressedBuffer
0x140021199  mov     [rsp+68h+WorkSpace], rdi; WorkSpace
0x14002119e  movzx   ecx, bx; CompressionFormatAndEngine
0x1400211a1  mov     [rsp+68h+FinalCompressedSize], rax; FinalCompressedSize
0x1400211a6  mov     eax, [rsp+68h+arg_28]
0x1400211ad  mov     [rsp+68h+UncompressedChunkSize], 1000h; UncompressedChunkSize
0x1400211b5  mov     [rsp+68h+CompressedBufferSize], eax; CompressedBufferSize
0x1400211b9  call    cs:__imp_RtlCompressBuffer
0x1400211c0  nop     dword ptr [rax+rax+00h]
0x1400211c5  xor     ebx, ebx
0x1400211c7  cmp     eax, 117h
0x1400211cc  cmovnz  ebx, eax
0x1400211cf  cmp     ebx, 0C000025Fh
0x1400211d5  jnz     short loc_1400211DC
0x1400211d7  mov     ebx, 0C000000Dh
0x1400211dc  mov     rdx, rdi
0x1400211df  call    PplFreeToLookasideList
0x1400211e4  jmp     short loc_1400211EB
0x1400211e6  mov     ebx, 0C000025Fh
0x1400211eb  mov     eax, ebx
0x1400211ed  add     rsp, 48h
0x1400211f1  pop     rdi
0x1400211f2  pop     rsi
0x1400211f3  pop     rbp
0x1400211f4  pop     rbx
0x1400211f5  retn
```
