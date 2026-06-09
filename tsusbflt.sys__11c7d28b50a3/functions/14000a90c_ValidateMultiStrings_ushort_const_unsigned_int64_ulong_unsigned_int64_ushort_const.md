# ValidateMultiStrings(ushort const *,unsigned __int64,ulong *,unsigned __int64 *,ushort const * * *)

- ea: `0x14000a90c`
- end: `0x14000a9d8`
- name: `?ValidateMultiStrings@@YAJPEBG_KPEAKPEA_KPEAPEAPEBG@Z`
- size: `204`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned int *, unsigned __int64 *, const unsigned __int16 ***)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e80`
- `0x140005a54`
- `0x14000711c`

## callees

- `0x14000a90c`

## pseudocode

```c
__int64 __fastcall ValidateMultiStrings(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  bool v5; // cf
  unsigned int v7; // edx
  const unsigned __int16 *v8; // r11
  unsigned int v9; // r9d
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rcx
  const unsigned __int16 *i; // rax
  unsigned __int64 v13; // rbx
  __int64 v14; // r10
  __int64 result; // rax

  v5 = a2 < 2;
  v7 = -1073741811;
  v8 = a1;
  if ( !v5 )
  {
    v9 = 0;
    v10 = a2;
    if ( *a1 )
    {
      while ( 1 )
      {
        v11 = v10 >> 1;
        if ( v10 >> 1 > 0x7FFFFFFF )
          break;
        for ( i = v8; v11; --v11 )
        {
          if ( !*i )
            break;
          ++i;
        }
        if ( v11 )
          v13 = (v10 >> 1) - v11;
        else
          v13 = 0;
        if ( !v11 )
        {
          v7 = -1073741811;
          break;
        }
        ++v9;
        v8 += ((2 * v13) >> 1) + 1;
        v10 += -2LL - 2 * v13;
        if ( !*v8 )
          goto LABEL_12;
      }
    }
    else
    {
LABEL_12:
      if ( v9 )
      {
        v7 = 0;
        v14 = a2 - v10 + 2;
        goto LABEL_16;
      }
    }
  }
  v14 = 0;
  v9 = 0;
LABEL_16:
  *a3 = v9;
  result = v7;
  *a4 = v14;
  return result;
}

```

## disassembly

```asm
0x14000a90c  push    rbx
0x14000a90e  push    rbp
0x14000a90f  push    rsi
0x14000a910  push    rdi
0x14000a911  push    r14
0x14000a913  xor     ebp, ebp
0x14000a915  mov     r10, rdx
0x14000a918  cmp     rdx, 2
0x14000a91c  mov     rsi, r9
0x14000a91f  mov     edx, 0C000000Dh
0x14000a924  mov     r14, r8
0x14000a927  mov     r11, rcx
0x14000a92a  jb      loc_14000A9B2
0x14000a930  mov     r9d, ebp
0x14000a933  mov     rdi, r10
0x14000a936  cmp     [rcx], bp
0x14000a939  jz      short loc_14000A9AD
0x14000a93b  mov     rcx, rdi
0x14000a93e  shr     rcx, 1
0x14000a941  cmp     rcx, 7FFFFFFFh
0x14000a948  ja      short loc_14000A9B2
0x14000a94a  mov     rax, r11
0x14000a94d  mov     rbx, rcx
0x14000a950  test    rcx, rcx
0x14000a953  jz      short loc_14000A964
0x14000a955  cmp     [rax], bp
0x14000a958  jz      short loc_14000A964
0x14000a95a  add     rax, 2
0x14000a95e  sub     rcx, 1
0x14000a962  jnz     short loc_14000A955
0x14000a964  mov     rax, rcx
0x14000a967  neg     rax
0x14000a96a  sbb     r8d, r8d
0x14000a96d  not     r8d
0x14000a970  and     r8d, edx
0x14000a973  test    rcx, rcx
0x14000a976  jz      short loc_14000A97D
0x14000a978  sub     rbx, rcx
0x14000a97b  jmp     short loc_14000A980
0x14000a97d  mov     rbx, rbp
0x14000a980  test    rcx, rcx
0x14000a983  jz      short loc_14000A9BA
0x14000a985  lea     rcx, [rbx+rbx]
0x14000a989  inc     r9d
0x14000a98c  mov     rax, rcx
0x14000a98f  shr     rax, 1
0x14000a992  lea     r11, [r11+rax*2]
0x14000a996  mov     rax, 0FFFFFFFFFFFFFFFEh
0x14000a99d  sub     rax, rcx
0x14000a9a0  add     r11, 2
0x14000a9a4  add     rdi, rax
0x14000a9a7  cmp     [r11], bp
0x14000a9ab  jnz     short loc_14000A93B
0x14000a9ad  test    r9d, r9d
0x14000a9b0  jnz     short loc_14000A9BF
0x14000a9b2  mov     r10, rbp
0x14000a9b5  mov     r9d, ebp
0x14000a9b8  jmp     short loc_14000A9C8
0x14000a9ba  mov     edx, r8d
0x14000a9bd  jmp     short loc_14000A9B2
0x14000a9bf  mov     edx, ebp
0x14000a9c1  sub     r10, rdi
0x14000a9c4  add     r10, 2
0x14000a9c8  mov     [r14], r9d
0x14000a9cb  mov     eax, edx
0x14000a9cd  mov     [rsi], r10
0x14000a9d0  pop     r14
0x14000a9d2  pop     rdi
0x14000a9d3  pop     rsi
0x14000a9d4  pop     rbp
0x14000a9d5  pop     rbx
0x14000a9d6  retn
```
