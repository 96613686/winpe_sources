# wil::details::HrToNtStatus(long)

- ea: `0x140006fcc`
- end: `0x140007188`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140004540`
- `0x1400045e0`
- `0x140004630`
- `0x1400046f0`
- `0x1400065a8`
- `0x140007190`

## callees

- `0x140006fcc`

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
0x140006fcc  mov     eax, 800700EAh
0x140006fd1  cmp     ecx, eax
0x140006fd3  jg      loc_1400070A8
0x140006fd9  jz      loc_14000709E
0x140006fdf  mov     eax, 80070057h
0x140006fe4  cmp     ecx, eax
0x140006fe6  jg      short loc_140007052
0x140006fe8  jz      short loc_140007048
0x140006fea  cmp     ecx, 80004005h
0x140006ff0  jz      short loc_14000703E
0x140006ff2  cmp     ecx, 80070001h
0x140006ff8  jz      short loc_140007034
0x140006ffa  cmp     ecx, 80070002h
0x140007000  jz      short loc_14000702A
0x140007002  cmp     ecx, 80070003h
0x140007008  jz      short loc_140007020
0x14000700a  cmp     ecx, 8007000Eh
0x140007010  jnz     loc_14000712D
0x140007016  mov     ecx, 0C0000017h
0x14000701b  jmp     loc_140007185
0x140007020  mov     ecx, 0C000003Ah
0x140007025  jmp     loc_140007185
0x14000702a  mov     ecx, 0C0000034h
0x14000702f  jmp     loc_140007185
0x140007034  mov     ecx, 0C0000002h
0x140007039  jmp     loc_140007185
0x14000703e  mov     ecx, 0C0000001h
0x140007043  jmp     loc_140007185
0x140007048  mov     ecx, 0C000000Dh
0x14000704d  jmp     loc_140007185
0x140007052  cmp     ecx, 80070070h
0x140007058  jz      short loc_140007094
0x14000705a  cmp     ecx, 8007007Ah
0x140007060  jz      short loc_14000708A
0x140007062  cmp     ecx, 8007007Bh
0x140007068  jz      short loc_140007080
0x14000706a  cmp     ecx, 8007007Eh
0x140007070  jnz     loc_14000712D
0x140007076  mov     ecx, 0C0000135h
0x14000707b  jmp     loc_140007185
0x140007080  mov     ecx, 0C0000033h
0x140007085  jmp     loc_140007185
0x14000708a  mov     ecx, 0C0000023h
0x14000708f  jmp     loc_140007185
0x140007094  mov     ecx, 0C000007Fh
0x140007099  jmp     loc_140007185
0x14000709e  mov     ecx, 80000005h
0x1400070a3  jmp     loc_140007185
0x1400070a8  mov     eax, 8007047Eh
0x1400070ad  cmp     ecx, eax
0x1400070af  jg      short loc_140007111
0x1400070b1  jz      short loc_14000710A
0x1400070b3  cmp     ecx, 80070216h
0x1400070b9  jz      short loc_140007103
0x1400070bb  cmp     ecx, 8007023Eh
0x1400070c1  jz      short loc_1400070F9
0x1400070c3  cmp     ecx, 80070246h
0x1400070c9  jz      short loc_1400070EF
0x1400070cb  cmp     ecx, 80070247h
0x1400070d1  jz      short loc_1400070E5
0x1400070d3  cmp     ecx, 80070272h
0x1400070d9  jnz     short loc_14000712D
0x1400070db  mov     ecx, 0C0000273h
0x1400070e0  jmp     loc_140007185
0x1400070e5  mov     ecx, 0C0000163h
0x1400070ea  jmp     loc_140007185
0x1400070ef  mov     ecx, 0C0000161h
0x1400070f4  jmp     loc_140007185
0x1400070f9  mov     ecx, 0C0000025h
0x1400070fe  jmp     loc_140007185
0x140007103  mov     ecx, 0C0000095h
0x140007108  jmp     short loc_140007185
0x14000710a  mov     ecx, 0C0000059h
0x14000710f  jmp     short loc_140007185
0x140007111  cmp     ecx, 8007050Ch
0x140007117  jz      short loc_140007180
0x140007119  cmp     ecx, 8007054Fh
0x14000711f  jz      short loc_140007179
0x140007121  cmp     ecx, 800705B9h
0x140007127  jz      short loc_140007172
0x140007129  test    ecx, ecx
0x14000712b  jz      short loc_14000716E
0x14000712d  bt      ecx, 1Ch
0x140007131  jnb     short loc_140007139
0x140007133  btr     ecx, 1Ch
0x140007137  jmp     short loc_140007185
0x140007139  mov     eax, ecx
0x14000713b  and     eax, 1FFF0000h
0x140007140  cmp     eax, 70000h
0x140007145  jnz     short loc_140007158
0x140007147  movzx   ecx, cx
0x14000714a  mov     eax, ecx
0x14000714c  or      eax, 0C0070000h
0x140007151  test    ecx, ecx
0x140007153  cmovnz  ecx, eax
0x140007156  jmp     short loc_140007185
0x140007158  cmp     eax, 90000h
0x14000715d  jnz     short loc_140007179
0x14000715f  test    ecx, ecx
0x140007161  jle     short loc_140007185
0x140007163  movzx   ecx, cx
0x140007166  or      ecx, 0C0090000h
0x14000716c  jmp     short loc_140007185
0x14000716e  xor     ecx, ecx
0x140007170  jmp     short loc_140007185
0x140007172  mov     ecx, 0C000A083h
0x140007177  jmp     short loc_140007185
0x140007179  mov     ecx, 0C00000E5h
0x14000717e  jmp     short loc_140007185
0x140007180  mov     ecx, 0C000042Bh
0x140007185  mov     eax, ecx
0x140007187  retn
```
