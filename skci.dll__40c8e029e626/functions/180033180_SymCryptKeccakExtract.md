# SymCryptKeccakExtract

- ea: `0x180033180`
- end: `0x180033304`
- name: `SymCryptKeccakExtract`
- size: `388`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18002697c`
- `0x180026bf8`
- `0x1800270d4`
- `0x18002d018`
- `0x18002d48c`
- `0x18002dc00`
- `0x18002ddc4`
- `0x18002dea8`
- `0x18002ef30`

## callees

- `0x180009780`
- `0x180033180`
- `0x18003330c`

## pseudocode

```c
void __fastcall SymCryptKeccakExtract(__int64 a1, _BYTE *a2, unsigned __int64 a3, char a4)
{
  unsigned __int64 v4; // r12
  int *v5; // rbx
  _DWORD *v6; // r15
  unsigned int v11; // r8d
  int v12; // ecx
  __int64 v13; // rdx
  unsigned __int64 v14; // rbp
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // r8d
  __int64 v19; // rdx

  v4 = 0;
  v5 = (int *)(a1 + 204);
  v6 = (_DWORD *)(a1 + 200);
  if ( !*(_BYTE *)(a1 + 209) )
  {
    *(_QWORD *)(a1 + 8 * ((unsigned __int64)(unsigned int)*v5 >> 3)) ^= (unsigned __int64)*(unsigned __int8 *)(a1 + 208) << (8 * (*v5 & 7u));
    *(_QWORD *)(a1 + 8 * ((unsigned __int64)(unsigned int)*v6 >> 3) - 8) ^= 0x8000000000000000uLL;
    SymCryptKeccakPermute(a1);
    *v5 = 0;
    *(_BYTE *)(a1 + 209) = 1;
  }
  if ( a3 )
  {
    if ( *v5 == *v6 )
    {
      SymCryptKeccakPermute(a1);
      *v5 = 0;
    }
    do
    {
      v11 = *v5;
      v12 = *v5 & 7;
      if ( !v12 )
        break;
      v13 = *(_QWORD *)(a1 + 8 * ((unsigned __int64)v11 >> 3)) >> (8 * (unsigned __int8)v12);
      *v5 = v11 + 1;
      *a2++ = v13;
      --a3;
    }
    while ( a3 );
  }
  v14 = a3 >> 3;
  if ( a3 >> 3 )
  {
    v15 = *v5;
    v16 = (unsigned int)*v5 >> 3;
    do
    {
      if ( v15 == *v6 )
      {
        SymCryptKeccakPermute(a1);
        v16 = 0;
        *v5 = 0;
      }
      v17 = *(_QWORD *)(a1 + 8 * v16);
      v16 = (unsigned int)(v16 + 1);
      *(_QWORD *)&a2[8 * v4++] = v17;
      v15 = *v5 + 8;
      *v5 = v15;
    }
    while ( v4 < v14 );
    a2 += 8 * v14;
    a3 -= 8 * v14;
  }
  for ( ; a3; --a3 )
  {
    v18 = *v5;
    if ( *v5 == *v6 )
    {
      SymCryptKeccakPermute(a1);
      v18 = 0;
      *v5 = 0;
    }
    v19 = *(_QWORD *)(a1 + 8 * ((unsigned __int64)v18 >> 3)) >> (8 * (v18 & 7));
    *v5 = v18 + 1;
    *a2++ = v19;
  }
  if ( a4 )
  {
    SymCryptWipeAsm(a1, 0xC8u);
    *v5 = 0;
    *(_BYTE *)(a1 + 209) = 0;
  }
}

```

## disassembly

```asm
0x180033180  push    rbx
0x180033182  push    rbp
0x180033183  push    rsi
0x180033184  push    rdi
0x180033185  push    r12
0x180033187  push    r13
0x180033189  push    r14
0x18003318b  push    r15
0x18003318d  sub     rsp, 28h
0x180033191  xor     r12d, r12d
0x180033194  lea     rbx, [rcx+0CCh]
0x18003319b  lea     r15, [rcx+0C8h]
0x1800331a2  mov     r13b, r9b
0x1800331a5  mov     rsi, r8
0x1800331a8  mov     r14, rdx
0x1800331ab  mov     rdi, rcx
0x1800331ae  cmp     [rcx+0D1h], r12b
0x1800331b5  jnz     short loc_1800331FB
0x1800331b7  mov     ecx, [rbx]
0x1800331b9  movzx   eax, byte ptr [rdi+0D0h]
0x1800331c0  mov     edx, ecx
0x1800331c2  and     ecx, 7
0x1800331c5  shr     rdx, 3
0x1800331c9  shl     ecx, 3
0x1800331cc  shl     rax, cl
0x1800331cf  mov     rcx, 8000000000000000h
0x1800331d9  xor     [rdi+rdx*8], rax
0x1800331dd  mov     eax, [r15]
0x1800331e0  shr     rax, 3
0x1800331e4  xor     [rdi+rax*8-8], rcx
0x1800331e9  mov     rcx, rdi
0x1800331ec  call    SymCryptKeccakPermute
0x1800331f1  mov     [rbx], r12d
0x1800331f4  mov     byte ptr [rdi+0D1h], 1
0x1800331fb  test    rsi, rsi
0x1800331fe  jz      short loc_180033240
0x180033200  mov     eax, [r15]
0x180033203  cmp     [rbx], eax
0x180033205  jnz     short loc_180033212
0x180033207  mov     rcx, rdi
0x18003320a  call    SymCryptKeccakPermute
0x18003320f  mov     [rbx], r12d
0x180033212  mov     r8d, [rbx]
0x180033215  mov     ecx, r8d
0x180033218  and     ecx, 7
0x18003321b  jz      short loc_180033240
0x18003321d  shl     ecx, 3
0x180033220  mov     eax, r8d
0x180033223  shr     rax, 3
0x180033227  mov     rdx, [rdi+rax*8]
0x18003322b  lea     eax, [r8+1]
0x18003322f  shr     rdx, cl
0x180033232  mov     [rbx], eax
0x180033234  mov     [r14], dl
0x180033237  inc     r14
0x18003323a  sub     rsi, 1
0x18003323e  jnz     short loc_180033212
0x180033240  mov     rbp, rsi
0x180033243  shr     rbp, 3
0x180033247  test    rbp, rbp
0x18003324a  jz      short loc_180033292
0x18003324c  mov     eax, [rbx]
0x18003324e  mov     edx, eax
0x180033250  shr     edx, 3
0x180033253  cmp     eax, [r15]
0x180033256  jnz     short loc_180033268
0x180033258  mov     rcx, rdi
0x18003325b  call    SymCryptKeccakPermute
0x180033260  xor     edx, edx
0x180033262  mov     dword ptr [rbx], 0
0x180033268  mov     rcx, [rdi+rdx*8]
0x18003326c  inc     edx
0x18003326e  mov     [r14+r12*8], rcx
0x180033272  inc     r12
0x180033275  mov     eax, [rbx]
0x180033277  add     eax, 8
0x18003327a  mov     [rbx], eax
0x18003327c  cmp     r12, rbp
0x18003327f  jb      short loc_180033253
0x180033281  lea     rax, ds:0[rbp*8]
0x180033289  add     r14, rax
0x18003328c  sub     rsi, rax
0x18003328f  xor     r12d, r12d
0x180033292  test    rsi, rsi
0x180033295  jz      short loc_1800332D6
0x180033297  mov     r8d, [rbx]
0x18003329a  cmp     r8d, [r15]
0x18003329d  jnz     short loc_1800332AD
0x18003329f  mov     rcx, rdi
0x1800332a2  call    SymCryptKeccakPermute
0x1800332a7  mov     r8d, r12d
0x1800332aa  mov     [rbx], r12d
0x1800332ad  mov     eax, r8d
0x1800332b0  mov     ecx, r8d
0x1800332b3  shr     rax, 3
0x1800332b7  and     ecx, 7
0x1800332ba  shl     ecx, 3
0x1800332bd  mov     rdx, [rdi+rax*8]
0x1800332c1  lea     eax, [r8+1]
0x1800332c5  shr     rdx, cl
0x1800332c8  mov     [rbx], eax
0x1800332ca  mov     [r14], dl
0x1800332cd  inc     r14
0x1800332d0  sub     rsi, 1
0x1800332d4  jnz     short loc_180033297
0x1800332d6  test    r13b, r13b
0x1800332d9  jz      short loc_1800332F2
0x1800332db  mov     edx, 0C8h
0x1800332e0  mov     rcx, rdi
0x1800332e3  call    SymCryptWipeAsm
0x1800332e8  mov     [rbx], r12d
0x1800332eb  mov     [rdi+0D1h], r12b
0x1800332f2  add     rsp, 28h
0x1800332f6  pop     r15
0x1800332f8  pop     r14
0x1800332fa  pop     r13
0x1800332fc  pop     r12
0x1800332fe  pop     rdi
0x1800332ff  pop     rsi
0x180033300  pop     rbp
0x180033301  pop     rbx
0x180033302  retn
```
