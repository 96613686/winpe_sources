# FindExtInPathext

- ea: `0x180006d04`
- end: `0x180006d8f`
- name: `FindExtInPathext`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006df0`

## callees

- `0x180006d04`

## pseudocode

```c
__int64 __fastcall FindExtInPathext(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  int v4; // r10d
  int v5; // r9d
  int i; // r11d

  v2 = -1;
  if ( a1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_BYTE *)(a1 + v3) );
  }
  else
  {
    LODWORD(v3) = 0;
  }
  if ( a2 )
  {
    do
      ++v2;
    while ( *(_BYTE *)(a2 + v2) );
  }
  else
  {
    LODWORD(v2) = 0;
  }
  v4 = 0;
  v5 = v3 - v2;
  while ( 2 )
  {
    if ( v4 >= v5 + 1 )
      return 0;
    for ( i = 0; i < (int)v2; ++i )
    {
      if ( *(_BYTE *)(i + v4 + a1) != *(_BYTE *)(i + a2) )
        goto LABEL_18;
    }
    if ( v4 != v5 && *(_BYTE *)(v4 + (int)v2 + a1) != 59 )
    {
LABEL_18:
      ++v4;
      continue;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180006d04  push    rbx
0x180006d06  push    rsi
0x180006d07  push    rdi
0x180006d08  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006d0c  mov     rdi, rdx
0x180006d0f  mov     rbx, rcx
0x180006d12  test    rcx, rcx
0x180006d15  jz      short loc_180006D26
0x180006d17  mov     r9, r8
0x180006d1a  inc     r9
0x180006d1d  cmp     byte ptr [rcx+r9], 0
0x180006d22  jnz     short loc_180006D1A
0x180006d24  jmp     short loc_180006D29
0x180006d26  xor     r9d, r9d
0x180006d29  test    rdi, rdi
0x180006d2c  jz      short loc_180006D3A
0x180006d2e  inc     r8
0x180006d31  cmp     byte ptr [rdx+r8], 0
0x180006d36  jnz     short loc_180006D2E
0x180006d38  jmp     short loc_180006D3D
0x180006d3a  xor     r8d, r8d
0x180006d3d  xor     r10d, r10d
0x180006d40  sub     r9d, r8d
0x180006d43  lea     esi, [r9+1]
0x180006d47  cmp     r10d, esi
0x180006d4a  jge     short loc_180006D89
0x180006d4c  xor     r11d, r11d
0x180006d4f  cmp     r11d, r8d
0x180006d52  jge     short loc_180006D6B
0x180006d54  lea     eax, [r11+r10]
0x180006d58  movsxd  rdx, eax
0x180006d5b  movsxd  rax, r11d
0x180006d5e  mov     cl, [rax+rdi]
0x180006d61  cmp     [rdx+rbx], cl
0x180006d64  jnz     short loc_180006D7D
0x180006d66  inc     r11d
0x180006d69  jmp     short loc_180006D4F
0x180006d6b  cmp     r10d, r9d
0x180006d6e  jz      short loc_180006D82
0x180006d70  lea     eax, [r10+r8]
0x180006d74  movsxd  rcx, eax
0x180006d77  cmp     byte ptr [rcx+rbx], 3Bh ; ';'
0x180006d7b  jz      short loc_180006D82
0x180006d7d  inc     r10d
0x180006d80  jmp     short loc_180006D47
0x180006d82  mov     eax, 1
0x180006d87  jmp     short loc_180006D8B
0x180006d89  xor     eax, eax
0x180006d8b  pop     rdi
0x180006d8c  pop     rsi
0x180006d8d  pop     rbx
0x180006d8e  retn
```
