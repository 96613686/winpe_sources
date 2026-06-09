# SkciCheckNtHeaderForCompliance

- ea: `0x18004b8a0`
- end: `0x18004b93f`
- name: `SkciCheckNtHeaderForCompliance`
- size: `159`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011ef0`

## callees

- `0x18004b8a0`

## pseudocode

```c
__int64 __fastcall SkciCheckNtHeaderForCompliance(__int64 a1)
{
  int v2; // edx
  unsigned int v3; // r11d
  __int64 v4; // r9
  unsigned int v5; // r8d
  unsigned int i; // r10d
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // r8d

  if ( ((*(_WORD *)(a1 + 24) - 267) & 0xFEFF) != 0 )
    return 3221225595LL;
  v2 = *(_DWORD *)(a1 + 56);
  if ( !v2 || (v2 & 0xFFF) != 0 )
    return 3221226016LL;
  v3 = *(unsigned __int16 *)(a1 + 6);
  v4 = a1 + *(unsigned __int16 *)(a1 + 20) + 24LL;
  v5 = (*(_DWORD *)(a1 + 84) >> 12) + ((*(_DWORD *)(a1 + 84) & 0xFFF) != 0);
  for ( i = 0; i < v3; ++i )
  {
    v7 = *(_DWORD *)(v4 + 12);
    if ( ((v2 - 1) & v7) != 0 )
      return 3221226016LL;
    v8 = v7 >> 12;
    if ( v8 < v5 )
      return 3221225595LL;
    v9 = *(_DWORD *)(v4 + 8);
    v4 += 40;
    v5 = v8 + ((v9 & 0xFFF) != 0) + (v9 >> 12);
  }
  return 0;
}

```

## disassembly

```asm
0x18004b8a0  movzx   eax, word ptr [rcx+18h]
0x18004b8a4  mov     edx, 10Bh
0x18004b8a9  sub     ax, dx
0x18004b8ac  mov     edx, 0FEFFh
0x18004b8b1  test    dx, ax
0x18004b8b4  jz      short loc_18004B8BD
0x18004b8b6  mov     eax, 0C000007Bh
0x18004b8bb  retn
0x18004b8bd  mov     edx, [rcx+38h]
0x18004b8c0  test    edx, edx
0x18004b8c2  jz      short loc_18004B939
0x18004b8c4  test    edx, 0FFFh
0x18004b8ca  jnz     short loc_18004B939
0x18004b8cc  mov     eax, [rcx+54h]
0x18004b8cf  mov     r8d, 0
0x18004b8d5  movzx   r9d, word ptr [rcx+14h]
0x18004b8da  movzx   r11d, word ptr [rcx+6]
0x18004b8df  add     r9, 18h
0x18004b8e3  add     r9, rcx
0x18004b8e6  test    eax, 0FFFh
0x18004b8eb  setnz   r8b
0x18004b8ef  shr     eax, 0Ch
0x18004b8f2  add     r8d, eax
0x18004b8f5  xor     r10d, r10d
0x18004b8f8  cmp     r10d, r11d
0x18004b8fb  jnb     short loc_18004B935
0x18004b8fd  mov     ecx, [r9+0Ch]
0x18004b901  lea     eax, [rdx-1]
0x18004b904  test    ecx, eax
0x18004b906  jnz     short loc_18004B939
0x18004b908  shr     ecx, 0Ch
0x18004b90b  cmp     ecx, r8d
0x18004b90e  jb      short loc_18004B8B6
0x18004b910  mov     r8d, [r9+8]
0x18004b914  mov     eax, 0
0x18004b919  test    r8d, 0FFFh
0x18004b920  setnz   al
0x18004b923  shr     r8d, 0Ch
0x18004b927  add     eax, ecx
0x18004b929  add     r9, 28h ; '('
0x18004b92d  add     r8d, eax
0x18004b930  inc     r10d
0x18004b933  jmp     short loc_18004B8F8
0x18004b935  xor     eax, eax
0x18004b937  retn
0x18004b939  mov     eax, 0C0000220h
0x18004b93e  retn
```
