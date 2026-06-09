# SmbCompressionLegacyCompress

- ea: `0x140020ba4`
- end: `0x140020c70`
- name: `SmbCompressionLegacyCompress`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140053a6c`

## callees

- `0x140020484`
- `0x1400204a8`
- `0x140020ba4`

## import_xrefs

- `ntoskrnl!RtlCompressBuffer` at `0x140020c36`
- `ntoskrnl!RtlCompressBuffer` at `0x140020c36`

## pseudocode

```c
__int64 __fastcall SmbCompressionLegacyCompress(int a1, UCHAR *a2, ULONG a3, UCHAR *a4, ULONG *FinalCompressedSize)
{
  unsigned int v8; // ebx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  USHORT v12; // bx
  void *WorkSpace; // rdi
  NTSTATUS v14; // eax
  __int64 v15; // rcx

  if ( !a1 )
    return (unsigned int)-1073741637;
  v9 = a1 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 != 2 )
          return (unsigned int)-1073741637;
        v12 = 6;
      }
      else
      {
        v12 = 4;
      }
    }
    else
    {
      v12 = 3;
    }
  }
  else
  {
    v12 = 2;
  }
  WorkSpace = (void *)PplAllocateFromLookasideList();
  if ( WorkSpace )
  {
    v14 = RtlCompressBuffer(v12, a2, a3, a4, a3, 0x1000u, FinalCompressedSize, WorkSpace);
    v8 = 0;
    if ( v14 != 279 )
      v8 = v14;
    if ( v8 == -1073741217 )
      v8 = -1073741811;
    PplFreeToLookasideList(v15, WorkSpace);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v8;
}

```

## disassembly

```asm
0x140020ba4  push    rbx
0x140020ba6  push    rbp
0x140020ba7  push    rsi
0x140020ba8  push    rdi
0x140020ba9  push    r14
0x140020bab  sub     rsp, 40h
0x140020baf  mov     rbp, r9
0x140020bb2  mov     esi, r8d
0x140020bb5  mov     r14, rdx
0x140020bb8  test    ecx, ecx
0x140020bba  jnz     short loc_140020BC6
0x140020bbc  mov     ebx, 0C00000BBh
0x140020bc1  jmp     loc_140020C62
0x140020bc6  sub     ecx, 1
0x140020bc9  jz      short loc_140020BF3
0x140020bcb  sub     ecx, 1
0x140020bce  jz      short loc_140020BEC
0x140020bd0  sub     ecx, 1
0x140020bd3  jz      short loc_140020BE5
0x140020bd5  mov     ebx, 2
0x140020bda  cmp     ecx, ebx
0x140020bdc  jnz     short loc_140020BBC
0x140020bde  mov     ebx, 6
0x140020be3  jmp     short loc_140020BF8
0x140020be5  mov     ebx, 4
0x140020bea  jmp     short loc_140020BF8
0x140020bec  mov     ebx, 3
0x140020bf1  jmp     short loc_140020BF8
0x140020bf3  mov     ebx, 2
0x140020bf8  call    PplAllocateFromLookasideList
0x140020bfd  mov     rdi, rax
0x140020c00  test    rax, rax
0x140020c03  jnz     short loc_140020C0C
0x140020c05  mov     ebx, 0C000009Ah
0x140020c0a  jmp     short loc_140020C62
0x140020c0c  mov     rax, [rsp+68h+arg_20]
0x140020c14  mov     r9, rbp; CompressedBuffer
0x140020c17  mov     [rsp+68h+WorkSpace], rdi; WorkSpace
0x140020c1c  mov     r8d, esi; UncompressedBufferSize
0x140020c1f  mov     [rsp+68h+FinalCompressedSize], rax; FinalCompressedSize
0x140020c24  mov     rdx, r14; UncompressedBuffer
0x140020c27  mov     [rsp+68h+UncompressedChunkSize], 1000h; UncompressedChunkSize
0x140020c2f  movzx   ecx, bx; CompressionFormatAndEngine
0x140020c32  mov     [rsp+68h+CompressedBufferSize], esi; CompressedBufferSize
0x140020c36  call    cs:__imp_RtlCompressBuffer
0x140020c3d  nop     dword ptr [rax+rax+00h]
0x140020c42  xor     ebx, ebx
0x140020c44  cmp     eax, 117h
0x140020c49  cmovnz  ebx, eax
0x140020c4c  mov     eax, 0C000000Dh
0x140020c51  cmp     ebx, 0C000025Fh
0x140020c57  cmovz   ebx, eax
0x140020c5a  mov     rdx, rdi
0x140020c5d  call    PplFreeToLookasideList
0x140020c62  mov     eax, ebx
0x140020c64  add     rsp, 40h
0x140020c68  pop     r14
0x140020c6a  pop     rdi
0x140020c6b  pop     rsi
0x140020c6c  pop     rbp
0x140020c6d  pop     rbx
0x140020c6e  retn
```
