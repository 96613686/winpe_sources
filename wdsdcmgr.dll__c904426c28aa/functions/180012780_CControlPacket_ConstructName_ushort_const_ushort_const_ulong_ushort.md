# CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180012780`
- end: `0x180012844`
- name: `?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z`
- size: `196`
- prototype: `unsigned int __fastcall(CControlPacket *this, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 **, __int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18001284c`
- `0x1800129e4`
- `0x180012ac8`
- `0x180012bb4`

## callees

- `0x180012780`
- `0x180013dcc`
- `0x180013ea4`

## pseudocode

```c
unsigned int __fastcall CControlPacket::ConstructName(
        CControlPacket *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v14; // rax
  __int64 v15; // rdx

  if ( a4 == -1 )
  {
    if ( a3 )
    {
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( a2[v15] );
      do
        ++v14;
      while ( a3[v14] );
      return FormatString(a5, v14 + 6 + v15, L"%s.%s", a2, a3, a6, a7, a8, a9);
    }
    else
    {
      return DuplicateStringW(a2, a5);
    }
  }
  else
  {
    v11 = -1;
    if ( a3 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
    }
    else
    {
      v12 = 0;
    }
    do
      ++v11;
    while ( a2[v11] );
    if ( !a3 )
      a3 = &word_18001870C;
    return FormatString(a5, v11 + v12 + 26, L"%s.%s[%u]", a2, a3, a4);
  }
}

```

## disassembly

```asm
0x180012780  sub     rsp, 38h
0x180012784  xor     ecx, ecx
0x180012786  mov     r11d, r9d
0x180012789  mov     r10, rdx
0x18001278c  cmp     r9d, 0FFFFFFFFh
0x180012790  jz      short loc_1800127EE
0x180012792  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012796  test    r8, r8
0x180012799  jz      short loc_1800127AA
0x18001279b  mov     r9, rax
0x18001279e  inc     r9
0x1800127a1  cmp     [r8+r9*2], cx
0x1800127a6  jnz     short loc_18001279E
0x1800127a8  jmp     short loc_1800127AD
0x1800127aa  mov     r9, rcx
0x1800127ad  inc     rax
0x1800127b0  cmp     [rdx+rax*2], cx
0x1800127b4  jnz     short loc_1800127AD
0x1800127b6  mov     rcx, [rsp+38h+arg_20]; unsigned __int16 **
0x1800127bb  lea     rdx, [r9+1Ah]
0x1800127bf  add     rdx, rax; unsigned __int64
0x1800127c2  mov     [rsp+38h+var_10], r11d
0x1800127c7  test    r8, r8
0x1800127ca  lea     rax, word_18001870C
0x1800127d1  mov     r9, r10
0x1800127d4  cmovz   r8, rax
0x1800127d8  mov     [rsp+38h+var_18], r8
0x1800127dd  lea     r8, aSSU; "%s.%s[%u]"
0x1800127e4  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x1800127e9  add     rsp, 38h
0x1800127ed  retn
0x1800127ee  test    r8, r8
0x1800127f1  jz      short loc_180012832
0x1800127f3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800127f7  mov     rdx, rax
0x1800127fa  inc     rdx
0x1800127fd  cmp     [r10+rdx*2], cx
0x180012802  jnz     short loc_1800127FA
0x180012804  inc     rax
0x180012807  cmp     [r8+rax*2], cx
0x18001280c  jnz     short loc_180012804
0x18001280e  mov     rcx, [rsp+38h+arg_20]; unsigned __int16 **
0x180012813  add     rax, 6
0x180012817  mov     [rsp+38h+arg_20], r8
0x18001281c  add     rdx, rax; unsigned __int64
0x18001281f  mov     r9, r10
0x180012822  lea     r8, aSS; "%s.%s"
0x180012829  add     rsp, 38h
0x18001282d  jmp     ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x180012832  mov     rdx, [rsp+38h+arg_20]; unsigned __int16 **
0x180012837  mov     rcx, r10; unsigned __int16 *
0x18001283a  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18001283f  add     rsp, 38h
0x180012843  retn
```
