# wil::details::HrToNtStatus(long)

- ea: `0x1800120fc`
- end: `0x1800122b8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f8a0`
- `0x18000f940`
- `0x18000f990`
- `0x18000fa50`
- `0x1800116d8`
- `0x1800122c0`

## callees

- `0x1800120fc`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x8007054F:
          goto LABEL_53;
        case 0x800705B9:
          LODWORD(this) = -1073700733;
          return (unsigned int)this;
        case 0:
          LODWORD(this) = 0;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          LODWORD(this) = -1073741735;
          return (unsigned int)this;
        case 0x80070216:
          LODWORD(this) = -1073741675;
          return (unsigned int)this;
        case 0x8007023E:
          LODWORD(this) = -1073741787;
          return (unsigned int)this;
        case 0x80070246:
          LODWORD(this) = -1073741471;
          return (unsigned int)this;
        case 0x80070247:
          LODWORD(this) = -1073741469;
          return (unsigned int)this;
        case 0x80070272:
          LODWORD(this) = -1073741197;
          return (unsigned int)this;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
    {
      LODWORD(this) = -2147483643;
      return (unsigned int)this;
    }
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          LODWORD(this) = -1073741697;
          return (unsigned int)this;
        case 0x8007007A:
          LODWORD(this) = -1073741789;
          return (unsigned int)this;
        case 0x8007007B:
          LODWORD(this) = -1073741773;
          return (unsigned int)this;
        case 0x8007007E:
          LODWORD(this) = -1073741515;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          LODWORD(this) = -1073741811;
          return (unsigned int)this;
        case 0x80004005:
          LODWORD(this) = -1073741823;
          return (unsigned int)this;
        case 0x80070001:
          LODWORD(this) = -1073741822;
          return (unsigned int)this;
        case 0x80070002:
          LODWORD(this) = -1073741772;
          return (unsigned int)this;
        case 0x80070003:
          LODWORD(this) = -1073741766;
          return (unsigned int)this;
        case 0x8007000E:
          LODWORD(this) = -1073741801;
          return (unsigned int)this;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
  {
    LODWORD(this) = (unsigned int)this & 0xEFFFFFFF;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    LODWORD(this) = (unsigned __int16)this;
    if ( (_WORD)this )
      LODWORD(this) = (unsigned __int16)this | 0xC0070000;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
  {
LABEL_53:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (int)this > 0 )
    LODWORD(this) = (unsigned __int16)this | 0xC0090000;
  return (unsigned int)this;
}

```

## disassembly

```asm
0x1800120fc  mov     eax, 800700EAh
0x180012101  cmp     ecx, eax
0x180012103  jg      loc_1800121D8
0x180012109  jz      loc_1800121CE
0x18001210f  mov     eax, 80070057h
0x180012114  cmp     ecx, eax
0x180012116  jg      short loc_180012182
0x180012118  jz      short loc_180012178
0x18001211a  cmp     ecx, 80004005h
0x180012120  jz      short loc_18001216E
0x180012122  cmp     ecx, 80070001h
0x180012128  jz      short loc_180012164
0x18001212a  cmp     ecx, 80070002h
0x180012130  jz      short loc_18001215A
0x180012132  cmp     ecx, 80070003h
0x180012138  jz      short loc_180012150
0x18001213a  cmp     ecx, 8007000Eh
0x180012140  jnz     loc_18001225D
0x180012146  mov     ecx, 0C0000017h
0x18001214b  jmp     loc_1800122B5
0x180012150  mov     ecx, 0C000003Ah
0x180012155  jmp     loc_1800122B5
0x18001215a  mov     ecx, 0C0000034h
0x18001215f  jmp     loc_1800122B5
0x180012164  mov     ecx, 0C0000002h
0x180012169  jmp     loc_1800122B5
0x18001216e  mov     ecx, 0C0000001h
0x180012173  jmp     loc_1800122B5
0x180012178  mov     ecx, 0C000000Dh
0x18001217d  jmp     loc_1800122B5
0x180012182  cmp     ecx, 80070070h
0x180012188  jz      short loc_1800121C4
0x18001218a  cmp     ecx, 8007007Ah
0x180012190  jz      short loc_1800121BA
0x180012192  cmp     ecx, 8007007Bh
0x180012198  jz      short loc_1800121B0
0x18001219a  cmp     ecx, 8007007Eh
0x1800121a0  jnz     loc_18001225D
0x1800121a6  mov     ecx, 0C0000135h
0x1800121ab  jmp     loc_1800122B5
0x1800121b0  mov     ecx, 0C0000033h
0x1800121b5  jmp     loc_1800122B5
0x1800121ba  mov     ecx, 0C0000023h
0x1800121bf  jmp     loc_1800122B5
0x1800121c4  mov     ecx, 0C000007Fh
0x1800121c9  jmp     loc_1800122B5
0x1800121ce  mov     ecx, 80000005h
0x1800121d3  jmp     loc_1800122B5
0x1800121d8  mov     eax, 8007047Eh
0x1800121dd  cmp     ecx, eax
0x1800121df  jg      short loc_180012241
0x1800121e1  jz      short loc_18001223A
0x1800121e3  cmp     ecx, 80070216h
0x1800121e9  jz      short loc_180012233
0x1800121eb  cmp     ecx, 8007023Eh
0x1800121f1  jz      short loc_180012229
0x1800121f3  cmp     ecx, 80070246h
0x1800121f9  jz      short loc_18001221F
0x1800121fb  cmp     ecx, 80070247h
0x180012201  jz      short loc_180012215
0x180012203  cmp     ecx, 80070272h
0x180012209  jnz     short loc_18001225D
0x18001220b  mov     ecx, 0C0000273h
0x180012210  jmp     loc_1800122B5
0x180012215  mov     ecx, 0C0000163h
0x18001221a  jmp     loc_1800122B5
0x18001221f  mov     ecx, 0C0000161h
0x180012224  jmp     loc_1800122B5
0x180012229  mov     ecx, 0C0000025h
0x18001222e  jmp     loc_1800122B5
0x180012233  mov     ecx, 0C0000095h
0x180012238  jmp     short loc_1800122B5
0x18001223a  mov     ecx, 0C0000059h
0x18001223f  jmp     short loc_1800122B5
0x180012241  cmp     ecx, 8007050Ch
0x180012247  jz      short loc_1800122B0
0x180012249  cmp     ecx, 8007054Fh
0x18001224f  jz      short loc_1800122A9
0x180012251  cmp     ecx, 800705B9h
0x180012257  jz      short loc_1800122A2
0x180012259  test    ecx, ecx
0x18001225b  jz      short loc_18001229E
0x18001225d  bt      ecx, 1Ch
0x180012261  jnb     short loc_180012269
0x180012263  btr     ecx, 1Ch
0x180012267  jmp     short loc_1800122B5
0x180012269  mov     eax, ecx
0x18001226b  and     eax, 1FFF0000h
0x180012270  cmp     eax, 70000h
0x180012275  jnz     short loc_180012288
0x180012277  movzx   ecx, cx
0x18001227a  mov     eax, ecx
0x18001227c  or      eax, 0C0070000h
0x180012281  test    ecx, ecx
0x180012283  cmovnz  ecx, eax
0x180012286  jmp     short loc_1800122B5
0x180012288  cmp     eax, 90000h
0x18001228d  jnz     short loc_1800122A9
0x18001228f  test    ecx, ecx
0x180012291  jle     short loc_1800122B5
0x180012293  movzx   ecx, cx
0x180012296  or      ecx, 0C0090000h
0x18001229c  jmp     short loc_1800122B5
0x18001229e  xor     ecx, ecx
0x1800122a0  jmp     short loc_1800122B5
0x1800122a2  mov     ecx, 0C000A083h
0x1800122a7  jmp     short loc_1800122B5
0x1800122a9  mov     ecx, 0C00000E5h
0x1800122ae  jmp     short loc_1800122B5
0x1800122b0  mov     ecx, 0C000042Bh
0x1800122b5  mov     eax, ecx
0x1800122b7  retn
```
