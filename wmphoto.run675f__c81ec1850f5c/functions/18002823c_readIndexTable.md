# readIndexTable

- ea: `0x18002823c`
- end: `0x1800283ba`
- name: `readIndexTable`
- size: `382`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011de8`

## callees

- `0x18000bbf0`
- `0x18002823c`
- `0x1800283c0`
- `0x180028470`

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
0x18002823c  push    rbx
0x18002823e  push    rbp
0x18002823f  push    rsi
0x180028240  push    rdi
0x180028241  push    r14
0x180028243  sub     rsp, 20h
0x180028247  mov     rdi, [rcx+8640h]
0x18002824e  mov     rbx, rcx
0x180028251  mov     rdx, rdi
0x180028254  call    readIS
0x180028259  cmp     qword ptr [rbx+86B0h], 0
0x180028261  jbe     short loc_1800282B5
0x180028263  mov     r14, [rbx+8648h]
0x18002826a  mov     edx, 10h
0x18002826f  mov     esi, [rbx+40DCh]
0x180028275  mov     rcx, rdi
0x180028278  mov     ebp, [rbx+86B0h]
0x18002827e  call    getBit32
0x180028283  cmp     eax, 1
0x180028286  jz      short loc_180028290
0x180028288  or      eax, 0FFFFFFFFh
0x18002828b  jmp     loc_1800283AE
0x180028290  inc     esi
0x180028292  imul    esi, ebp
0x180028295  xor     ebp, ebp
0x180028297  test    esi, esi
0x180028299  jz      short loc_1800282B5
0x18002829b  mov     rdx, rdi
0x18002829e  call    readIS
0x1800282a3  mov     rcx, rdi
0x1800282a6  call    GetVLWordEsc
0x1800282ab  mov     [r14+rbp*8], rax
0x1800282af  inc     ebp
0x1800282b1  cmp     ebp, esi
0x1800282b3  jb      short loc_18002829B
0x1800282b5  mov     rcx, rdi
0x1800282b8  call    GetVLWordEsc
0x1800282bd  mov     ecx, [rdi+8]
0x1800282c0  mov     rsi, rax
0x1800282c3  movsxd  rdx, dword ptr [rdi+0Ch]
0x1800282c7  neg     ecx
0x1800282c9  and     ecx, 7
0x1800282cc  mov     ebp, 4
0x1800282d1  add     ecx, [rdi+8]
0x1800282d4  mov     eax, ecx
0x1800282d6  and     ecx, 0Fh
0x1800282d9  shr     rax, 3
0x1800282dd  add     rax, [rdi+18h]
0x1800282e1  and     rax, rdx
0x1800282e4  mov     [rdi+8], ecx
0x1800282e7  mov     [rdi+18h], rax
0x1800282eb  mov     eax, [rax]
0x1800282ed  bswap   eax
0x1800282ef  shl     eax, cl
0x1800282f1  mov     [rdi+4], eax
0x1800282f4  cmp     rsi, rbp
0x1800282f7  mov     r9, [rbx+8640h]
0x1800282fe  cmova   rsi, rbp
0x180028302  mov     [rbx+86B8h], rsi
0x180028309  mov     rcx, [r9+10h]
0x18002830d  mov     eax, [r9+8]
0x180028311  mov     r8, rcx
0x180028314  shr     rax, 3
0x180028318  sub     r8, rax
0x18002831b  sub     r8, [r9+18h]
0x18002831f  lea     rdx, [r8+2000h]
0x180028326  cmp     rcx, [r9+18h]
0x18002832a  jbe     short loc_180028337
0x18002832c  cmp     rdx, 2000h
0x180028333  cmovnb  rdx, r8
0x180028337  mov     ecx, [r9+28h]
0x18002833b  sub     ecx, edx
0x18002833d  add     rcx, rsi
0x180028340  cmp     dword ptr [rbx+0A0h], 0
0x180028347  mov     [rbx+86B8h], rcx
0x18002834e  jz      short loc_1800283AC
0x180028350  mov     word ptr [rbx+80FCh], 0FF6Fh
0x180028359  cmp     rsi, rbp
0x18002835c  jb      short loc_1800283AC
0x18002835e  mov     r14d, 8
0x180028364  mov     edx, r14d
0x180028367  mov     rcx, rdi
0x18002836a  call    getBit32
0x18002836f  mov     edx, r14d
0x180028372  mov     [rbx+80FCh], al
0x180028378  mov     rcx, rdi
0x18002837b  call    getBit32
0x180028380  mov     edx, 0Fh
0x180028385  mov     [rbx+80FDh], al
0x18002838b  mov     rcx, rdi
0x18002838e  call    getBit32
0x180028393  mov     edx, 1
0x180028398  mov     rcx, rdi
0x18002839b  call    getBit32
0x1800283a0  test    eax, eax
0x1800283a2  jnz     short loc_1800283AC
0x1800283a4  sub     rsi, rbp
0x1800283a7  cmp     rsi, rbp
0x1800283aa  jnb     short loc_180028364
0x1800283ac  xor     eax, eax
0x1800283ae  add     rsp, 20h
0x1800283b2  pop     r14
0x1800283b4  pop     rdi
0x1800283b5  pop     rsi
0x1800283b6  pop     rbp
0x1800283b7  pop     rbx
0x1800283b8  retn
```
