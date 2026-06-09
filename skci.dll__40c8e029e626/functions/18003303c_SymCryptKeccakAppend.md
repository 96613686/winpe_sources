# SymCryptKeccakAppend

- ea: `0x18003303c`
- end: `0x180033179`
- name: `SymCryptKeccakAppend`
- size: `317`
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
- `0x18003303c`
- `0x18003330c`

## pseudocode

```c
__int64 __fastcall SymCryptKeccakAppend(__int64 a1, unsigned __int8 *a2, unsigned __int64 a3)
{
  unsigned int v6; // edx
  __int64 result; // rax
  char v8; // cl
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  __int64 v12; // rdx
  unsigned __int64 v13; // rbp
  int v14; // eax
  unsigned __int64 i; // r8
  __int64 v16; // rax
  unsigned __int64 v17; // rcx

  if ( *(_BYTE *)(a1 + 209) )
  {
    SymCryptWipeAsm(a1, 0xC8u);
    v6 = 0;
    *(_DWORD *)(a1 + 204) = 0;
    result = 0;
    *(_BYTE *)(a1 + 209) = 0;
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 204);
    result = v6;
  }
  for ( ; a3; --a3 )
  {
    v6 = result;
    v8 = result & 7;
    if ( (result & 7) == 0 )
      break;
    v9 = (unsigned int)result;
    v10 = *a2++;
    *(_QWORD *)(a1 + 8 * (v9 >> 3)) ^= v10 << (8 * v8);
    result = (unsigned int)++*(_DWORD *)(a1 + 204);
    v6 = *(_DWORD *)(a1 + 204);
  }
  if ( v6 == *(_DWORD *)(a1 + 200) )
  {
    result = SymCryptKeccakPermute(a1);
    v6 = 0;
    *(_DWORD *)(a1 + 204) = 0;
  }
  v11 = a3 >> 3;
  if ( a3 >> 3 )
  {
    v12 = v6 >> 3;
    v13 = 0;
    do
    {
      *(_QWORD *)(a1 + 8 * v12) ^= *(_QWORD *)&a2[8 * v13];
      v14 = *(_DWORD *)(a1 + 204) + 8;
      *(_DWORD *)(a1 + 204) = v14;
      if ( v14 == *(_DWORD *)(a1 + 200) )
      {
        SymCryptKeccakPermute(a1);
        v12 = 0;
        *(_DWORD *)(a1 + 204) = 0;
      }
      else
      {
        v12 = (unsigned int)(v12 + 1);
      }
      ++v13;
    }
    while ( v13 < v11 );
    result = 8 * v11;
    a2 += 8 * v11;
    a3 -= 8 * v11;
  }
  for ( i = 0; i < a3; *(_QWORD *)(a1 + 8 * (v17 >> 3)) ^= result )
  {
    v16 = a2[i];
    v17 = i + *(unsigned int *)(a1 + 204);
    ++i;
    result = v16 << (8 * ((unsigned __int8)v17 & 7u));
  }
  *(_DWORD *)(a1 + 204) += a3;
  return result;
}

```

## disassembly

```asm
0x18003303c  push    rbx
0x18003303e  push    rbp
0x18003303f  push    rsi
0x180033040  push    rdi
0x180033041  push    r14
0x180033043  sub     rsp, 20h
0x180033047  cmp     byte ptr [rcx+0D1h], 0
0x18003304e  mov     rdi, r8
0x180033051  mov     r14, rdx
0x180033054  mov     rbx, rcx
0x180033057  jz      short loc_18003307A
0x180033059  mov     edx, 0C8h
0x18003305e  call    SymCryptWipeAsm
0x180033063  xor     edx, edx
0x180033065  mov     dword ptr [rbx+0CCh], 0
0x18003306f  xor     eax, eax
0x180033071  mov     byte ptr [rbx+0D1h], 0
0x180033078  jmp     short loc_180033082
0x18003307a  mov     edx, [rcx+0CCh]
0x180033080  mov     eax, edx
0x180033082  test    rdi, rdi
0x180033085  jz      short loc_1800330BB
0x180033087  mov     ecx, eax
0x180033089  mov     edx, eax
0x18003308b  and     ecx, 7
0x18003308e  jz      short loc_1800330BB
0x180033090  mov     edx, eax
0x180033092  movzx   eax, byte ptr [r14]
0x180033096  inc     r14
0x180033099  shr     rdx, 3
0x18003309d  shl     ecx, 3
0x1800330a0  shl     rax, cl
0x1800330a3  xor     [rbx+rdx*8], rax
0x1800330a7  inc     dword ptr [rbx+0CCh]
0x1800330ad  mov     eax, [rbx+0CCh]
0x1800330b3  mov     edx, eax
0x1800330b5  sub     rdi, 1
0x1800330b9  jnz     short loc_180033087
0x1800330bb  cmp     edx, [rbx+0C8h]
0x1800330c1  jnz     short loc_1800330D7
0x1800330c3  mov     rcx, rbx
0x1800330c6  call    SymCryptKeccakPermute
0x1800330cb  xor     edx, edx
0x1800330cd  mov     dword ptr [rbx+0CCh], 0
0x1800330d7  mov     rsi, rdi
0x1800330da  shr     rsi, 3
0x1800330de  test    rsi, rsi
0x1800330e1  jz      short loc_180033135
0x1800330e3  shr     edx, 3
0x1800330e6  xor     ebp, ebp
0x1800330e8  mov     rax, [r14+rbp*8]
0x1800330ec  xor     [rbx+rdx*8], rax
0x1800330f0  mov     eax, [rbx+0CCh]
0x1800330f6  add     eax, 8
0x1800330f9  mov     [rbx+0CCh], eax
0x1800330ff  cmp     eax, [rbx+0C8h]
0x180033105  jnz     short loc_18003311D
0x180033107  mov     rcx, rbx
0x18003310a  call    SymCryptKeccakPermute
0x18003310f  xor     edx, edx
0x180033111  mov     dword ptr [rbx+0CCh], 0
0x18003311b  jmp     short loc_18003311F
0x18003311d  inc     edx
0x18003311f  inc     rbp
0x180033122  cmp     rbp, rsi
0x180033125  jb      short loc_1800330E8
0x180033127  lea     rax, ds:0[rsi*8]
0x18003312f  add     r14, rax
0x180033132  sub     rdi, rax
0x180033135  xor     r8d, r8d
0x180033138  test    rdi, rdi
0x18003313b  jz      short loc_180033167
0x18003313d  movzx   eax, byte ptr [r14+r8]
0x180033142  mov     ecx, [rbx+0CCh]
0x180033148  add     rcx, r8
0x18003314b  inc     r8
0x18003314e  mov     rdx, rcx
0x180033151  and     cl, 7
0x180033154  shr     rdx, 3
0x180033158  shl     cl, 3
0x18003315b  shl     rax, cl
0x18003315e  xor     [rbx+rdx*8], rax
0x180033162  cmp     r8, rdi
0x180033165  jb      short loc_18003313D
0x180033167  add     [rbx+0CCh], edi
0x18003316d  add     rsp, 20h
0x180033171  pop     r14
0x180033173  pop     rdi
0x180033174  pop     rsi
0x180033175  pop     rbp
0x180033176  pop     rbx
0x180033177  retn
```
