# EmbedCompressedFont

- ea: `0x1800205bc`
- end: `0x18002077b`
- name: `EmbedCompressedFont`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180021394`

## callees

- `0x180019014`
- `0x180019dc0`
- `0x180020588`
- `0x1800205bc`
- `0x180021020`
- `0x180021aa4`
- `0x180021d54`
- `0x18002a566`

## pseudocode

```c
__int64 __fastcall EmbedCompressedFont(
        int a1,
        int a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        _DWORD *a7,
        __int64 a8,
        int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  void *v18; // rbx
  int v19; // esi
  __int64 result; // rax
  int v21; // eax
  unsigned int AllocEmbedHeaderData; // esi
  unsigned int v23; // ebx
  unsigned int v24; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+74h] [rbp-8Ch] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  void *v27; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[272]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v28, 0, 0xD0u);
  v18 = 0;
  v19 = 0;
  v27 = 0;
  v25 = 0;
  lpMem = 0;
  v24 = 0;
  result = CompressBuffer(a1, a2, (unsigned int)&lpMem, (unsigned int)&v24, a14);
  if ( !(_DWORD)result )
  {
    if ( a3 )
    {
      v21 = CompressBuffer(a3, a4, (unsigned int)&v27, (unsigned int)&v25, a14);
      v18 = v27;
      v19 = v25;
      if ( v21 )
        v18 = 0;
    }
    AllocEmbedHeaderData = GetAllocEmbedHeaderData(
                             a1,
                             a2,
                             v24,
                             (_DWORD)v18,
                             v19,
                             a5,
                             a5,
                             a6,
                             a8,
                             a9,
                             a10,
                             a13,
                             (__int64)v28);
    if ( AllocEmbedHeaderData )
      goto LABEL_6;
    AllocEmbedHeaderData = WriteEmbeddedHeader(a11, a12, (__int64)v28);
    if ( AllocEmbedHeaderData )
    {
      DeallocEmbedHeaderData(v28);
LABEL_6:
      T2free(v18);
      T2free(lpMem);
      return AllocEmbedHeaderData;
    }
    if ( v18 )
    {
      *a7 |= 2u;
      T2free(v18);
    }
    v23 = WriteFontImage(lpMem, v24, a5 & 0x10000000, a11, a12);
    DeallocEmbedHeaderData(v28);
    T2free(lpMem);
    return v23;
  }
  return result;
}

```

## disassembly

```asm
0x1800205bc  push    rbp
0x1800205be  push    rbx
0x1800205bf  push    rsi
0x1800205c0  push    rdi
0x1800205c1  push    r12
0x1800205c3  push    r13
0x1800205c5  push    r14
0x1800205c7  push    r15
0x1800205c9  lea     rbp, [rsp-68h]
0x1800205ce  sub     rsp, 168h
0x1800205d5  mov     rdi, r8
0x1800205d8  mov     r12d, edx
0x1800205db  mov     r13, rcx
0x1800205de  xor     edx, edx; Val
0x1800205e0  mov     r8d, 0D0h; Size
0x1800205e6  lea     rcx, [rbp+0A0h+var_110]; void *
0x1800205ea  mov     r15d, r9d
0x1800205ed  call    memset_0
0x1800205f2  mov     r14, [rbp+0A0h+arg_68]
0x1800205f9  lea     r9, [rsp+1A0h+var_130]
0x1800205fe  xor     ebx, ebx
0x180020600  mov     [rsp+1A0h+var_180], r14
0x180020605  xor     esi, esi
0x180020607  mov     [rbp+0A0h+var_120], rbx
0x18002060b  lea     r8, [rsp+1A0h+lpMem]
0x180020610  mov     [rsp+1A0h+var_12C], esi
0x180020614  mov     edx, r12d
0x180020617  mov     [rsp+1A0h+lpMem], rbx
0x18002061c  mov     rcx, r13
0x18002061f  mov     [rsp+1A0h+var_130], 0
0x180020627  call    CompressBuffer
0x18002062c  test    eax, eax
0x18002062e  jnz     loc_180020767
0x180020634  test    rdi, rdi
0x180020637  jz      short loc_180020662
0x180020639  lea     r9, [rsp+1A0h+var_12C]
0x18002063e  mov     [rsp+1A0h+var_180], r14
0x180020643  lea     r8, [rbp+0A0h+var_120]
0x180020647  mov     edx, r15d
0x18002064a  mov     rcx, rdi
0x18002064d  call    CompressBuffer
0x180020652  mov     rbx, [rbp+0A0h+var_120]
0x180020656  xor     ecx, ecx
0x180020658  mov     esi, [rsp+1A0h+var_12C]
0x18002065c  test    eax, eax
0x18002065e  cmovnz  rbx, rcx
0x180020662  mov     edi, [rbp+0A0h+arg_20]
0x180020668  lea     rax, [rbp+0A0h+var_110]
0x18002066c  mov     r8d, [rsp+1A0h+var_130]
0x180020671  mov     r9, rbx
0x180020674  mov     [rsp+1A0h+var_140], rax
0x180020679  mov     edx, r12d
0x18002067c  mov     rax, [rbp+0A0h+arg_60]
0x180020683  mov     rcx, r13
0x180020686  mov     [rsp+1A0h+var_148], rax
0x18002068b  mov     rax, [rbp+0A0h+arg_48]
0x180020692  mov     [rsp+1A0h+var_150], rax
0x180020697  mov     eax, [rbp+0A0h+arg_40]
0x18002069d  mov     [rsp+1A0h+var_158], eax
0x1800206a1  mov     rax, [rbp+0A0h+arg_38]
0x1800206a8  mov     [rsp+1A0h+var_160], rax
0x1800206ad  mov     eax, [rbp+0A0h+arg_28]
0x1800206b3  mov     [rsp+1A0h+var_168], eax
0x1800206b7  mov     [rsp+1A0h+var_170], edi
0x1800206bb  mov     [rsp+1A0h+var_178], edi
0x1800206bf  mov     dword ptr [rsp+1A0h+var_180], esi
0x1800206c3  call    GetAllocEmbedHeaderData
0x1800206c8  mov     esi, eax
0x1800206ca  test    eax, eax
0x1800206cc  jz      short loc_1800206E7
0x1800206ce  mov     rcx, rbx; lpMem
0x1800206d1  call    T2free
0x1800206d6  mov     rcx, [rsp+1A0h+lpMem]; lpMem
0x1800206db  call    T2free
0x1800206e0  mov     eax, esi
0x1800206e2  jmp     loc_180020767
0x1800206e7  mov     r14, [rbp+0A0h+arg_58]
0x1800206ee  lea     r8, [rbp+0A0h+var_110]
0x1800206f2  mov     rcx, [rbp+0A0h+arg_50]
0x1800206f9  mov     rdx, r14
0x1800206fc  call    WriteEmbeddedHeader
0x180020701  mov     esi, eax
0x180020703  test    eax, eax
0x180020705  jz      short loc_180020712
0x180020707  lea     rcx, [rbp+0A0h+var_110]
0x18002070b  call    DeallocEmbedHeaderData
0x180020710  jmp     short loc_1800206CE
0x180020712  test    rbx, rbx
0x180020715  jz      short loc_180020729
0x180020717  mov     rax, [rbp+0A0h+arg_30]
0x18002071e  mov     rcx, rbx; lpMem
0x180020721  or      dword ptr [rax], 2
0x180020724  call    T2free
0x180020729  mov     r9, [rbp+0A0h+arg_50]
0x180020730  and     edi, 10000000h
0x180020736  mov     edx, [rsp+1A0h+var_130]
0x18002073a  mov     r8d, edi
0x18002073d  mov     rcx, [rsp+1A0h+lpMem]
0x180020742  mov     [rsp+1A0h+var_180], r14
0x180020747  call    WriteFontImage
0x18002074c  mov     ebx, eax
0x18002074e  test    eax, eax
0x180020750  jnz     short $+2
0x180020752  lea     rcx, [rbp+0A0h+var_110]
0x180020756  call    DeallocEmbedHeaderData
0x18002075b  mov     rcx, [rsp+1A0h+lpMem]; lpMem
0x180020760  call    T2free
0x180020765  mov     eax, ebx
0x180020767  add     rsp, 168h
0x18002076e  pop     r15
0x180020770  pop     r14
0x180020772  pop     r13
0x180020774  pop     r12
0x180020776  pop     rdi
0x180020777  pop     rsi
0x180020778  pop     rbx
0x180020779  pop     rbp
0x18002077a  retn
```
