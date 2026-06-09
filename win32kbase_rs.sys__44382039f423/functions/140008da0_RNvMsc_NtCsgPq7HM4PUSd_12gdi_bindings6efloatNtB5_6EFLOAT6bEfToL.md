# _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL

- ea: `0x140008da0`
- end: `0x140008e0a`
- name: `_RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL`
- size: `106`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001c40`
- `0x140002b00`
- `0x140002c60`
- `0x140007c90`
- `0x140008030`
- `0x140008210`

## callees

- `0x140008da0`

## pseudocode

```c
bool __fastcall RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(int *a1, int *a2)
{
  int v2; // eax
  unsigned int v3; // r8d
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // r9
  unsigned __int64 v6; // r9
  int v7; // ecx

  v2 = *a1;
  v3 = (unsigned __int8)((unsigned int)*a1 >> 23);
  if ( v3 <= 0x9E )
  {
    v4 = v2 & 0x7FFFFF | 0x800000LL;
    if ( v3 <= 0x75 )
    {
      if ( v3 >= 0x37 )
        v5 = v4 >> (118 - (unsigned __int8)v3);
      else
        v5 = 0;
    }
    else
    {
      v5 = v4 << ((unsigned __int8)v3 - 118);
    }
    v6 = (v5 + 0x80000000) >> 32;
    v7 = -(int)v6;
    if ( v2 >= 0 )
      v7 = v6;
    *a2 = v7;
  }
  return v3 < 0x9F;
}

```

## disassembly

```asm
0x140008da0  mov     eax, [rcx]
0x140008da2  mov     ecx, eax
0x140008da4  shr     ecx, 17h
0x140008da7  movzx   r8d, cl
0x140008dab  cmp     r8d, 9Eh
0x140008db2  ja      short loc_140008DFF
0x140008db4  mov     r9d, eax
0x140008db7  and     r9d, 7FFFFFh
0x140008dbe  or      r9, 800000h
0x140008dc5  cmp     r8d, 75h ; 'u'
0x140008dc9  jbe     short loc_140008DD4
0x140008dcb  lea     ecx, [r8-76h]
0x140008dcf  shl     r9, cl
0x140008dd2  jmp     short loc_140008DE7
0x140008dd4  cmp     r8d, 37h ; '7'
0x140008dd8  jnb     short loc_140008DDF
0x140008dda  xor     r9d, r9d
0x140008ddd  jmp     short loc_140008DE7
0x140008ddf  mov     cl, 76h ; 'v'
0x140008de1  sub     cl, r8b
0x140008de4  shr     r9, cl
0x140008de7  sub     r9, 0FFFFFFFF80000000h
0x140008dee  shr     r9, 20h
0x140008df2  mov     ecx, r9d
0x140008df5  neg     ecx
0x140008df7  test    eax, eax
0x140008df9  cmovns  ecx, r9d
0x140008dfd  mov     [rdx], ecx
0x140008dff  cmp     r8d, 9Fh
0x140008e06  setb    al
0x140008e09  retn
```
