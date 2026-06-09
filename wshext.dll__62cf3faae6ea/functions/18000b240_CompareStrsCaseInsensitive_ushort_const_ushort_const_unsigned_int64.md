# CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)

- ea: `0x18000b240`
- end: `0x18000b2fd`
- name: `?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z`
- size: `189`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800072c4`
- `0x18000bbdc`

## callees

- `0x18000b240`

## pseudocode

```c
__int64 __fastcall CompareStrsCaseInsensitive(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // r9
  const unsigned __int16 *v3; // r10
  unsigned __int64 v4; // r8
  unsigned __int64 v5; // rax
  unsigned __int16 v6; // dx
  unsigned __int16 v7; // r11
  unsigned __int16 v8; // cx

  v2 = a2;
  v3 = a1;
  if ( a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
  }
  else
  {
    v4 = 0;
  }
  if ( a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
  }
  else
  {
    v5 = 0;
  }
  if ( v4 <= v5 )
    v4 = v5;
  while ( v4 )
  {
    v6 = *v2;
    if ( *v3 == *v2 )
    {
      if ( !*v3 )
        return 0;
    }
    else
    {
      if ( !*v3 )
        return 0xFFFFFFFFLL;
      if ( !v6 )
        return 1;
      v7 = *v3;
      if ( (unsigned __int16)(*v3 - 65) <= 0x19u )
        v7 += 32;
      v8 = v6 + 32;
      if ( (unsigned __int16)(v6 - 65) > 0x19u )
        v8 = *v2;
      if ( v7 != v8 )
        return v6 < *v3 ? 1 : -1;
    }
    --v4;
    ++v3;
    ++v2;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b240  mov     [rsp+arg_0], rbx
0x18000b245  xor     ebx, ebx
0x18000b247  mov     r9, rdx
0x18000b24a  mov     r10, rcx
0x18000b24d  test    rcx, rcx
0x18000b250  jz      short loc_18000B262
0x18000b252  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b256  inc     r8
0x18000b259  cmp     [rcx+r8*2], bx
0x18000b25e  jnz     short loc_18000B256
0x18000b260  jmp     short loc_18000B265
0x18000b262  mov     r8, rbx
0x18000b265  test    rdx, rdx
0x18000b268  jz      short loc_18000B279
0x18000b26a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b26e  inc     rax
0x18000b271  cmp     [rdx+rax*2], bx
0x18000b275  jnz     short loc_18000B26E
0x18000b277  jmp     short loc_18000B27C
0x18000b279  mov     rax, rbx
0x18000b27c  cmp     r8, rax
0x18000b27f  cmovbe  r8, rax
0x18000b283  cmp     r8, 1
0x18000b287  jb      short loc_18000B2F5
0x18000b289  movzx   edx, word ptr [r9]
0x18000b28d  cmp     [r10], dx
0x18000b291  jz      short loc_18000B2D6
0x18000b293  cmp     bx, [r10]
0x18000b297  jz      short loc_18000B2F0
0x18000b299  cmp     bx, dx
0x18000b29c  jz      short loc_18000B2E9
0x18000b29e  movzx   eax, word ptr [r10]
0x18000b2a2  movzx   r11d, word ptr [r10]
0x18000b2a6  sub     ax, 41h ; 'A'
0x18000b2aa  cmp     ax, 19h
0x18000b2ae  ja      short loc_18000B2B5
0x18000b2b0  add     r11w, 20h ; ' '
0x18000b2b5  lea     eax, [rdx-41h]
0x18000b2b8  cmp     ax, 19h
0x18000b2bc  lea     ecx, [rdx+20h]
0x18000b2bf  cmova   cx, dx
0x18000b2c3  cmp     r11w, cx
0x18000b2c7  jz      short loc_18000B2DC
0x18000b2c9  cmp     dx, [r10]
0x18000b2cd  sbb     eax, eax
0x18000b2cf  and     eax, 2
0x18000b2d2  dec     eax
0x18000b2d4  jmp     short loc_18000B2F7
0x18000b2d6  cmp     bx, [r10]
0x18000b2da  jz      short loc_18000B2F5
0x18000b2dc  dec     r8
0x18000b2df  add     r10, 2
0x18000b2e3  add     r9, 2
0x18000b2e7  jmp     short loc_18000B283
0x18000b2e9  mov     eax, 1
0x18000b2ee  jmp     short loc_18000B2F7
0x18000b2f0  or      eax, 0FFFFFFFFh
0x18000b2f3  jmp     short loc_18000B2F7
0x18000b2f5  xor     eax, eax
0x18000b2f7  mov     rbx, [rsp+arg_0]
0x18000b2fc  retn
```
