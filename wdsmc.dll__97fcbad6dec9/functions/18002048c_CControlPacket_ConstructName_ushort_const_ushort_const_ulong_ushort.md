# CControlPacket::ConstructName(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18002048c`
- end: `0x180020550`
- name: `?ConstructName@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z`
- size: `196`
- prototype: `unsigned int(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180020558`
- `0x18002061c`
- `0x180020840`
- `0x180020948`
- `0x1800209c8`
- `0x180020ab0`
- `0x180020bd0`
- `0x180020dc8`
- `0x180020ecc`
- `0x180020f9c`
- `0x18002105c`

## callees

- `0x18002048c`
- `0x1800244bc`
- `0x180024760`

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
      a3 = (const unsigned __int16 *)&qword_18002DA18;
    return FormatString(a5, v11 + v12 + 26, L"%s.%s[%u]", a2, a3, a4);
  }
}

```

## disassembly

```asm
0x18002048c  sub     rsp, 38h
0x180020490  xor     ecx, ecx
0x180020492  mov     r11d, r9d
0x180020495  mov     r10, rdx
0x180020498  cmp     r9d, 0FFFFFFFFh
0x18002049c  jz      short loc_1800204FA
0x18002049e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800204a2  test    r8, r8
0x1800204a5  jz      short loc_1800204B6
0x1800204a7  mov     r9, rax
0x1800204aa  inc     r9
0x1800204ad  cmp     [r8+r9*2], cx
0x1800204b2  jnz     short loc_1800204AA
0x1800204b4  jmp     short loc_1800204B9
0x1800204b6  mov     r9, rcx
0x1800204b9  inc     rax
0x1800204bc  cmp     [rdx+rax*2], cx
0x1800204c0  jnz     short loc_1800204B9
0x1800204c2  mov     rcx, [rsp+38h+arg_20]; unsigned __int16 **
0x1800204c7  lea     rdx, [r9+1Ah]
0x1800204cb  add     rdx, rax; unsigned __int64
0x1800204ce  mov     [rsp+38h+var_10], r11d
0x1800204d3  test    r8, r8
0x1800204d6  lea     rax, qword_18002DA18
0x1800204dd  mov     r9, r10
0x1800204e0  cmovz   r8, rax
0x1800204e4  mov     [rsp+38h+var_18], r8
0x1800204e9  lea     r8, aSSU; "%s.%s[%u]"
0x1800204f0  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x1800204f5  add     rsp, 38h
0x1800204f9  retn
0x1800204fa  test    r8, r8
0x1800204fd  jz      short loc_18002053E
0x1800204ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020503  mov     rdx, rax
0x180020506  inc     rdx
0x180020509  cmp     [r10+rdx*2], cx
0x18002050e  jnz     short loc_180020506
0x180020510  inc     rax
0x180020513  cmp     [r8+rax*2], cx
0x180020518  jnz     short loc_180020510
0x18002051a  mov     rcx, [rsp+38h+arg_20]; unsigned __int16 **
0x18002051f  add     rax, 6
0x180020523  mov     [rsp+38h+arg_20], r8
0x180020528  add     rdx, rax; unsigned __int64
0x18002052b  mov     r9, r10
0x18002052e  lea     r8, aSS; "%s.%s"
0x180020535  add     rsp, 38h
0x180020539  jmp     ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x18002053e  mov     rdx, [rsp+38h+arg_20]; unsigned __int16 **
0x180020543  mov     rcx, r10; unsigned __int16 *
0x180020546  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18002054b  add     rsp, 38h
0x18002054f  retn
```
