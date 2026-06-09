# HexToString(uchar const *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180024228`
- end: `0x18002429e`
- name: `?HexToString@@YAKPEBE_KPEAG1@Z`
- size: `118`
- prototype: `unsigned int __fastcall(const unsigned __int8 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b560`
- `0x18000b8e8`
- `0x18000bb0c`
- `0x18000bdd4`
- `0x18000f688`
- `0x180018240`
- `0x18001853c`
- `0x180018770`
- `0x18001b9f8`
- `0x18001ed10`
- `0x180024168`

## callees

- `0x180024228`

## pseudocode

```c
__int64 __fastcall HexToString(const unsigned __int8 *a1, __int64 a2, unsigned __int16 *a3, unsigned __int64 a4)
{
  unsigned int v4; // r10d
  __int16 v6; // cx

  v4 = 0;
  if ( a4 >= 2 * a2 + 1 )
  {
    for ( ; a2; --a2 )
    {
      *a3 = (*a1 >> 4) + 55 + ((unsigned __int8)(*a1 >> 4) < 0xAu ? 0xFFF9 : 0);
      v6 = *a1++ & 0xF;
      a3[1] = v6 + ((unsigned __int8)v6 < 0xAu ? 48 : 55);
      a3 += 2;
    }
    *a3 = 0;
  }
  else
  {
    return 122;
  }
  return v4;
}

```

## disassembly

```asm
0x180024228  xor     r10d, r10d
0x18002422b  lea     rax, ds:1[rdx*2]
0x180024233  mov     r11, rcx
0x180024236  cmp     r9, rax
0x180024239  jnb     short loc_180024243
0x18002423b  mov     r10d, 7Ah ; 'z'
0x180024241  jmp     short loc_18002429A
0x180024243  test    rdx, rdx
0x180024246  jz      short loc_180024296
0x180024248  mov     r9w, 0FFF9h
0x18002424d  mov     al, [r11]
0x180024250  shr     al, 4
0x180024253  movzx   ecx, al
0x180024256  cmp     cl, 0Ah
0x180024259  sbb     ax, ax
0x18002425c  add     cx, 37h ; '7'
0x180024260  and     ax, r9w
0x180024264  add     ax, cx
0x180024267  mov     [r8], ax
0x18002426b  mov     al, [r11]
0x18002426e  and     al, 0Fh
0x180024270  movzx   ecx, al
0x180024273  cmp     cl, 0Ah
0x180024276  sbb     ax, ax
0x180024279  inc     r11
0x18002427c  and     ax, r9w
0x180024280  add     ax, 37h ; '7'
0x180024284  add     ax, cx
0x180024287  mov     [r8+2], ax
0x18002428c  add     r8, 4
0x180024290  sub     rdx, 1
0x180024294  jnz     short loc_18002424D
0x180024296  mov     [r8], r10w
0x18002429a  mov     eax, r10d
0x18002429d  retn
```
