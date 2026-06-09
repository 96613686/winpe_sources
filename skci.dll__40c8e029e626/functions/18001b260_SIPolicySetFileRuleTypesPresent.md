# SIPolicySetFileRuleTypesPresent

- ea: `0x18001b260`
- end: `0x18001b320`
- name: `SIPolicySetFileRuleTypesPresent`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x18001e674`

## callees

- `0x18001b260`

## pseudocode

```c
__int64 __fastcall SIPolicySetFileRuleTypesPresent(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // r10
  unsigned int v4; // r11d
  __int64 v5; // r9
  __int64 v6; // rsi
  __int64 v7; // rbx
  int v8; // edx
  int v9; // ecx
  unsigned int v10; // edx
  __int64 result; // rax

  *(_DWORD *)(a1 + 672) &= ~2u;
  v1 = *(_DWORD *)(a1 + 168);
  *(_QWORD *)(a1 + 680) = 0;
  if ( v1 )
  {
    v3 = *(_QWORD *)(a1 + 184);
    v4 = 0;
    v5 = 0;
    v6 = 0;
    do
    {
      v7 = 168 * v6;
      v8 = (*(_WORD *)(168 * v6 + v3 + 8) != 0) | 2;
      if ( !*(_WORD *)(168 * v6 + v3 + 24) )
        v8 = *(_WORD *)(168 * v6 + v3 + 8) != 0;
      v9 = v8 | 4;
      if ( !*(_WORD *)(v7 + v3 + 40) )
        v9 = v8;
      v10 = v9 | 8;
      if ( !*(_WORD *)(v7 + v3 + 56) )
        v10 = v9;
      if ( *(_WORD *)(v7 + v3 + 88) )
      {
        v10 |= 0x10u;
        if ( *(_DWORD *)(v7 + v3) == 1 )
          *(_DWORD *)(a1 + 672) |= 2u;
      }
      if ( *(_WORD *)(v7 + v3 + 72) )
      {
        v10 |= 0x20u;
        *(_DWORD *)(a1 + 672) |= 4u;
      }
      result = v10;
      ++v4;
      v5 |= 1LL << v10;
      ++v6;
      *(_QWORD *)(a1 + 680) = v5;
    }
    while ( v4 < v1 );
  }
  return result;
}

```

## disassembly

```asm
0x18001b260  push    rbx
0x18001b262  push    rbp
0x18001b263  push    rsi
0x18001b264  push    rdi
0x18001b265  and     dword ptr [rcx+2A0h], 0FFFFFFFDh
0x18001b26c  xor     ebp, ebp
0x18001b26e  mov     edi, [rcx+0A8h]
0x18001b274  mov     r8, rcx
0x18001b277  mov     [rcx+2A8h], rbp
0x18001b27e  test    edi, edi
0x18001b280  jz      loc_18001B31A
0x18001b286  mov     r10, [rcx+0B8h]
0x18001b28d  mov     r11d, ebp
0x18001b290  mov     r9d, ebp
0x18001b293  mov     esi, ebp
0x18001b295  imul    rbx, rsi, 0A8h
0x18001b29c  mov     ecx, ebp
0x18001b29e  cmp     [rbx+r10+8], bp
0x18001b2a4  setnbe  cl
0x18001b2a7  mov     edx, ecx
0x18001b2a9  or      edx, 2
0x18001b2ac  cmp     [rbx+r10+18h], bp
0x18001b2b2  cmovz   edx, ecx
0x18001b2b5  mov     ecx, edx
0x18001b2b7  or      ecx, 4
0x18001b2ba  cmp     [rbx+r10+28h], bp
0x18001b2c0  cmovz   ecx, edx
0x18001b2c3  mov     edx, ecx
0x18001b2c5  or      edx, 8
0x18001b2c8  cmp     [rbx+r10+38h], bp
0x18001b2ce  cmovz   edx, ecx
0x18001b2d1  cmp     [rbx+r10+58h], bp
0x18001b2d7  jbe     short loc_18001B2EB
0x18001b2d9  or      edx, 10h
0x18001b2dc  cmp     dword ptr [rbx+r10], 1
0x18001b2e1  jnz     short loc_18001B2EB
0x18001b2e3  or      dword ptr [r8+2A0h], 2
0x18001b2eb  cmp     [rbx+r10+48h], bp
0x18001b2f1  jbe     short loc_18001B2FE
0x18001b2f3  or      edx, 20h
0x18001b2f6  or      dword ptr [r8+2A0h], 4
0x18001b2fe  mov     eax, edx
0x18001b300  inc     r11d
0x18001b303  bts     r9, rax
0x18001b307  inc     rsi
0x18001b30a  mov     [r8+2A8h], r9
0x18001b311  cmp     r11d, edi
0x18001b314  jb      loc_18001B295
0x18001b31a  pop     rdi
0x18001b31b  pop     rsi
0x18001b31c  pop     rbp
0x18001b31d  pop     rbx
0x18001b31e  retn
```
