# readIndexTable

- ea: `0x180027fd8`
- end: `0x180028155`
- name: `readIndexTable`
- size: `381`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011be8`

## callees

- `0x18000bae0`
- `0x180027fd8`
- `0x180028160`
- `0x18002820c`

## pseudocode

```c
__int64 __fastcall readIndexTable(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // r14
  int v4; // esi
  int v5; // ebp
  __int64 v6; // rcx
  unsigned int v8; // esi
  __int64 i; // rbp
  unsigned __int64 VLWordEsc; // rsi
  int v11; // ecx
  unsigned int *v12; // rax
  __int64 v13; // r9
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdx
  bool v16; // zf

  v1 = *(_QWORD *)(a1 + 34368);
  readIS(a1, v1);
  if ( *(_QWORD *)(a1 + 34480) )
  {
    v3 = *(_QWORD *)(a1 + 34376);
    v4 = *(_DWORD *)(a1 + 16604);
    v5 = *(_DWORD *)(a1 + 34480);
    if ( (unsigned int)getBit32(v1, 16) != 1 )
      return 0xFFFFFFFFLL;
    v8 = v5 * (v4 + 1);
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    {
      readIS(v6, v1);
      *(_QWORD *)(v3 + 8 * i) = GetVLWordEsc(v1);
    }
  }
  VLWordEsc = GetVLWordEsc(v1);
  v11 = (*(_BYTE *)(v1 + 8) + (-*(_BYTE *)(v1 + 8) & 7)) & 0xF;
  v12 = (unsigned int *)(*(int *)(v1 + 12)
                       & (*(_QWORD *)(v1 + 24)
                        + ((unsigned __int64)(*(_DWORD *)(v1 + 8) + (-*(_DWORD *)(v1 + 8) & 7u)) >> 3)));
  *(_DWORD *)(v1 + 8) = v11;
  *(_QWORD *)(v1 + 24) = v12;
  *(_DWORD *)(v1 + 4) = _byteswap_ulong(*v12) << v11;
  v13 = *(_QWORD *)(a1 + 34368);
  if ( VLWordEsc > 4 )
    VLWordEsc = 4;
  *(_QWORD *)(a1 + 34488) = VLWordEsc;
  v14 = (unsigned __int64)*(unsigned int *)(v13 + 8) >> 3;
  v15 = *(_QWORD *)(v13 + 16) - v14 - *(_QWORD *)(v13 + 24) + 0x2000;
  if ( *(_QWORD *)(v13 + 16) > *(_QWORD *)(v13 + 24) && v15 >= 0x2000 )
    v15 = *(_QWORD *)(v13 + 16) - v14 - *(_QWORD *)(v13 + 24);
  v16 = *(_DWORD *)(a1 + 160) == 0;
  *(_QWORD *)(a1 + 34488) = VLWordEsc + (unsigned int)(*(_DWORD *)(v13 + 40) - v15);
  if ( !v16 )
  {
    for ( *(_WORD *)(a1 + 33020) = -145; VLWordEsc >= 4; VLWordEsc -= 4LL )
    {
      *(_BYTE *)(a1 + 33020) = getBit32(v1, 8);
      *(_BYTE *)(a1 + 33021) = getBit32(v1, 8);
      getBit32(v1, 15);
      if ( (unsigned int)getBit32(v1, 1) )
        break;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180027fd8  push    rbx
0x180027fda  push    rbp
0x180027fdb  push    rsi
0x180027fdc  push    rdi
0x180027fdd  push    r14
0x180027fdf  sub     rsp, 20h
0x180027fe3  mov     rdi, [rcx+8640h]
0x180027fea  mov     rbx, rcx
0x180027fed  mov     rdx, rdi
0x180027ff0  call    readIS
0x180027ff5  cmp     qword ptr [rbx+86B0h], 0
0x180027ffd  jbe     short loc_180028051
0x180027fff  mov     r14, [rbx+8648h]
0x180028006  mov     edx, 10h
0x18002800b  mov     esi, [rbx+40DCh]
0x180028011  mov     rcx, rdi
0x180028014  mov     ebp, [rbx+86B0h]
0x18002801a  call    getBit32
0x18002801f  cmp     eax, 1
0x180028022  jz      short loc_18002802C
0x180028024  or      eax, 0FFFFFFFFh
0x180028027  jmp     loc_18002814A
0x18002802c  inc     esi
0x18002802e  imul    esi, ebp
0x180028031  xor     ebp, ebp
0x180028033  test    esi, esi
0x180028035  jz      short loc_180028051
0x180028037  mov     rdx, rdi
0x18002803a  call    readIS
0x18002803f  mov     rcx, rdi
0x180028042  call    GetVLWordEsc
0x180028047  mov     [r14+rbp*8], rax
0x18002804b  inc     ebp
0x18002804d  cmp     ebp, esi
0x18002804f  jb      short loc_180028037
0x180028051  mov     rcx, rdi
0x180028054  call    GetVLWordEsc
0x180028059  mov     ecx, [rdi+8]
0x18002805c  mov     rsi, rax
0x18002805f  movsxd  rdx, dword ptr [rdi+0Ch]
0x180028063  neg     ecx
0x180028065  and     ecx, 7
0x180028068  mov     ebp, 4
0x18002806d  add     ecx, [rdi+8]
0x180028070  mov     eax, ecx
0x180028072  and     ecx, 0Fh
0x180028075  shr     rax, 3
0x180028079  add     rax, [rdi+18h]
0x18002807d  and     rax, rdx
0x180028080  mov     [rdi+8], ecx
0x180028083  mov     [rdi+18h], rax
0x180028087  mov     eax, [rax]
0x180028089  bswap   eax
0x18002808b  shl     eax, cl
0x18002808d  mov     [rdi+4], eax
0x180028090  cmp     rsi, rbp
0x180028093  mov     r9, [rbx+8640h]
0x18002809a  cmova   rsi, rbp
0x18002809e  mov     [rbx+86B8h], rsi
0x1800280a5  mov     rcx, [r9+10h]
0x1800280a9  mov     eax, [r9+8]
0x1800280ad  mov     r8, rcx
0x1800280b0  shr     rax, 3
0x1800280b4  sub     r8, rax
0x1800280b7  sub     r8, [r9+18h]
0x1800280bb  lea     rdx, [r8+2000h]
0x1800280c2  cmp     rcx, [r9+18h]
0x1800280c6  jbe     short loc_1800280D3
0x1800280c8  cmp     rdx, 2000h
0x1800280cf  cmovnb  rdx, r8
0x1800280d3  mov     ecx, [r9+28h]
0x1800280d7  sub     ecx, edx
0x1800280d9  add     rcx, rsi
0x1800280dc  cmp     dword ptr [rbx+0A0h], 0
0x1800280e3  mov     [rbx+86B8h], rcx
0x1800280ea  jz      short loc_180028148
0x1800280ec  mov     word ptr [rbx+80FCh], 0FF6Fh
0x1800280f5  cmp     rsi, rbp
0x1800280f8  jb      short loc_180028148
0x1800280fa  mov     r14d, 8
0x180028100  mov     edx, r14d
0x180028103  mov     rcx, rdi
0x180028106  call    getBit32
0x18002810b  mov     edx, r14d
0x18002810e  mov     [rbx+80FCh], al
0x180028114  mov     rcx, rdi
0x180028117  call    getBit32
0x18002811c  mov     edx, 0Fh
0x180028121  mov     [rbx+80FDh], al
0x180028127  mov     rcx, rdi
0x18002812a  call    getBit32
0x18002812f  mov     edx, 1
0x180028134  mov     rcx, rdi
0x180028137  call    getBit32
0x18002813c  test    eax, eax
0x18002813e  jnz     short loc_180028148
0x180028140  sub     rsi, rbp
0x180028143  cmp     rsi, rbp
0x180028146  jnb     short loc_180028100
0x180028148  xor     eax, eax
0x18002814a  add     rsp, 20h
0x18002814e  pop     r14
0x180028150  pop     rdi
0x180028151  pop     rsi
0x180028152  pop     rbp
0x180028153  pop     rbx
0x180028154  retn
```
