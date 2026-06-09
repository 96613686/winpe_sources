# SymCryptFdef369MaskedCopyAsm

- ea: `0x180010720`
- end: `0x180010770`
- name: `SymCryptFdef369MaskedCopyAsm`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002bdd0`
- `0x18002c060`

## callees

- `0x180010720`

## pseudocode

```c
__int64 __fastcall SymCryptFdef369MaskedCopyAsm(_QWORD *a1, _QWORD *a2, int a3, int a4)
{
  int v4; // r8d
  __int64 result; // rax

  v4 = a3 + 1;
  do
  {
    *a2 ^= a4 & (*a2 ^ *a1);
    a2[1] ^= a4 & (a2[1] ^ a1[1]);
    result = a2[2] ^ a4 & (a2[2] ^ a1[2]);
    a2[2] = result;
    a1 += 3;
    a2 += 3;
    --v4;
  }
  while ( v4 );
  return result;
}

```

## disassembly

```asm
0x180010720  inc     r8d
0x180010723  movsxd  r9, r9d
0x180010726  mov     rax, [rcx]
0x180010729  mov     r10, [rdx]
0x18001072c  xor     rax, r10
0x18001072f  and     rax, r9
0x180010732  xor     rax, r10
0x180010735  mov     [rdx], rax
0x180010738  mov     rax, [rcx+8]
0x18001073c  mov     r10, [rdx+8]
0x180010740  xor     rax, r10
0x180010743  and     rax, r9
0x180010746  xor     rax, r10
0x180010749  mov     [rdx+8], rax
0x18001074d  mov     rax, [rcx+10h]
0x180010751  mov     r10, [rdx+10h]
0x180010755  xor     rax, r10
0x180010758  and     rax, r9
0x18001075b  xor     rax, r10
0x18001075e  mov     [rdx+10h], rax
0x180010762  add     rcx, 18h
0x180010766  add     rdx, 18h
0x18001076a  dec     r8d
0x18001076d  jnz     short loc_180010726
0x18001076f  retn
```
