# SymCryptFdefRawSubAsm

- ea: `0x18000f7d0`
- end: `0x18000f81f`
- name: `SymCryptFdefRawSubAsm`
- size: `79`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180028790`
- `0x18002a4b0`
- `0x18002ad80`
- `0x18002b020`
- `0x18002b700`
- `0x18002bb90`
- `0x18002c690`

## callees

- `0x18000f7d0`

## pseudocode

```c
_BOOL8 __fastcall SymCryptFdefRawSubAsm(unsigned __int64 *a1, _QWORD *a2, _QWORD *a3, int a4)
{
  int v4; // r9d
  bool v5; // cf
  unsigned __int64 v6; // rtt
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rtt
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rtt
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rtt

  v4 = 2 * a4;
  v5 = 0;
  do
  {
    v6 = v5 + *a2;
    v5 = *a1 < v6;
    *a3 = *a1 - v6;
    v7 = a1[1];
    v8 = v5 + a2[1];
    v5 = v7 < v8;
    a3[1] = v7 - v8;
    v9 = a1[2];
    v10 = v5 + a2[2];
    v5 = v9 < v10;
    a3[2] = v9 - v10;
    v11 = a1[3];
    v12 = v5 + a2[3];
    v5 = v11 < v12;
    a3[3] = v11 - v12;
    a1 += 4;
    a2 += 4;
    a3 += 4;
    --v4;
  }
  while ( v4 );
  return v5;
}

```

## disassembly

```asm
0x18000f7d0  add     r9d, r9d
0x18000f7d3  xor     rax, rax
0x18000f7d6  mov     rax, [rcx]
0x18000f7d9  sbb     rax, [rdx]
0x18000f7dc  mov     [r8], rax
0x18000f7df  mov     rax, [rcx+8]
0x18000f7e3  sbb     rax, [rdx+8]
0x18000f7e7  mov     [r8+8], rax
0x18000f7eb  mov     rax, [rcx+10h]
0x18000f7ef  sbb     rax, [rdx+10h]
0x18000f7f3  mov     [r8+10h], rax
0x18000f7f7  mov     rax, [rcx+18h]
0x18000f7fb  sbb     rax, [rdx+18h]
0x18000f7ff  mov     [r8+18h], rax
0x18000f803  lea     rcx, [rcx+20h]
0x18000f807  lea     rdx, [rdx+20h]
0x18000f80b  lea     r8, [r8+20h]
0x18000f80f  dec     r9d
0x18000f812  jnz     short loc_18000F7D6
0x18000f814  mov     rax, 0
0x18000f81b  adc     rax, rax
0x18000f81e  retn
```
