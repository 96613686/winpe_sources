# ComputeCNsToBeNotified

- ea: `0x180002bec`
- end: `0x180002c56`
- name: `ComputeCNsToBeNotified`
- size: `106`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`
- `0x18000d9d0`

## callees

- `0x180002bec`

## pseudocode

```c
__int64 __fastcall ComputeCNsToBeNotified(__int64 a1, int a2, __int64 a3)
{
  int v5; // r9d
  unsigned int v7; // edx
  __int64 v8; // r8
  unsigned int v9; // ecx
  int v10; // ebx
  __int64 i; // r11

  v5 = a2 | ~*(_DWORD *)(a1 + 868);
  if ( !v5 )
    return 0;
  v7 = 0;
  v8 = 0;
  do
  {
    v9 = *(_DWORD *)(a3 + 4 * v8);
    v10 = 0;
    for ( i = 0; v9; v9 >>= 1 )
    {
      if ( (v9 & 1) != 0 )
        v10 |= *(_DWORD *)(a1 + 4 * i + 872);
      i = (unsigned int)(i + 1);
    }
    v7 |= v10 & *(_DWORD *)(a1 + 4 * v8 + 1000);
    if ( v7 == *(_DWORD *)(a1 + 864) )
      break;
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (unsigned int)v8 < 3 );
  return v5 & v7;
}

```

## disassembly

```asm
0x180002bec  push    rbx
0x180002bee  push    rsi
0x180002bef  push    rdi
0x180002bf0  mov     r9d, [rcx+364h]
0x180002bf7  mov     rsi, r8
0x180002bfa  not     r9d
0x180002bfd  mov     r10, rcx
0x180002c00  or      r9d, edx
0x180002c03  jnz     short loc_180002C09
0x180002c05  xor     eax, eax
0x180002c07  jmp     short loc_180002C52
0x180002c09  xor     edx, edx
0x180002c0b  xor     r8d, r8d
0x180002c0e  mov     ecx, [rsi+r8*4]
0x180002c12  xor     ebx, ebx
0x180002c14  xor     r11d, r11d
0x180002c17  test    ecx, ecx
0x180002c19  jz      short loc_180002C2F
0x180002c1b  test    cl, 1
0x180002c1e  jz      short loc_180002C28
0x180002c20  or      ebx, [r10+r11*4+368h]
0x180002c28  inc     r11d
0x180002c2b  shr     ecx, 1
0x180002c2d  jnz     short loc_180002C1B
0x180002c2f  mov     ecx, [r10+r8*4+3E8h]
0x180002c37  and     ecx, ebx
0x180002c39  or      edx, ecx
0x180002c3b  cmp     edx, [r10+360h]
0x180002c42  jz      short loc_180002C4D
0x180002c44  inc     r8d
0x180002c47  cmp     r8d, 3
0x180002c4b  jb      short loc_180002C0E
0x180002c4d  and     edx, r9d
0x180002c50  mov     eax, edx
0x180002c52  pop     rdi
0x180002c53  pop     rsi
0x180002c54  pop     rbx
0x180002c55  retn
```
