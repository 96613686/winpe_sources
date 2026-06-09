# wil::details::HrToNtStatus(long)

- ea: `0x180005fd4`
- end: `0x180006190`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004574`
- `0x18000461c`
- `0x18000466c`
- `0x180004724`
- `0x1800055c8`
- `0x180006198`

## callees

- `0x180005fd4`

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
0x180005fd4  mov     eax, 800700EAh
0x180005fd9  cmp     ecx, eax
0x180005fdb  jg      loc_1800060B0
0x180005fe1  jz      loc_1800060A6
0x180005fe7  mov     eax, 80070057h
0x180005fec  cmp     ecx, eax
0x180005fee  jg      short loc_18000605A
0x180005ff0  jz      short loc_180006050
0x180005ff2  cmp     ecx, 80004005h
0x180005ff8  jz      short loc_180006046
0x180005ffa  cmp     ecx, 80070001h
0x180006000  jz      short loc_18000603C
0x180006002  cmp     ecx, 80070002h
0x180006008  jz      short loc_180006032
0x18000600a  cmp     ecx, 80070003h
0x180006010  jz      short loc_180006028
0x180006012  cmp     ecx, 8007000Eh
0x180006018  jnz     loc_180006135
0x18000601e  mov     ecx, 0C0000017h
0x180006023  jmp     loc_18000618D
0x180006028  mov     ecx, 0C000003Ah
0x18000602d  jmp     loc_18000618D
0x180006032  mov     ecx, 0C0000034h
0x180006037  jmp     loc_18000618D
0x18000603c  mov     ecx, 0C0000002h
0x180006041  jmp     loc_18000618D
0x180006046  mov     ecx, 0C0000001h
0x18000604b  jmp     loc_18000618D
0x180006050  mov     ecx, 0C000000Dh
0x180006055  jmp     loc_18000618D
0x18000605a  cmp     ecx, 80070070h
0x180006060  jz      short loc_18000609C
0x180006062  cmp     ecx, 8007007Ah
0x180006068  jz      short loc_180006092
0x18000606a  cmp     ecx, 8007007Bh
0x180006070  jz      short loc_180006088
0x180006072  cmp     ecx, 8007007Eh
0x180006078  jnz     loc_180006135
0x18000607e  mov     ecx, 0C0000135h
0x180006083  jmp     loc_18000618D
0x180006088  mov     ecx, 0C0000033h
0x18000608d  jmp     loc_18000618D
0x180006092  mov     ecx, 0C0000023h
0x180006097  jmp     loc_18000618D
0x18000609c  mov     ecx, 0C000007Fh
0x1800060a1  jmp     loc_18000618D
0x1800060a6  mov     ecx, 80000005h
0x1800060ab  jmp     loc_18000618D
0x1800060b0  mov     eax, 8007047Eh
0x1800060b5  cmp     ecx, eax
0x1800060b7  jg      short loc_180006119
0x1800060b9  jz      short loc_180006112
0x1800060bb  cmp     ecx, 80070216h
0x1800060c1  jz      short loc_18000610B
0x1800060c3  cmp     ecx, 8007023Eh
0x1800060c9  jz      short loc_180006101
0x1800060cb  cmp     ecx, 80070246h
0x1800060d1  jz      short loc_1800060F7
0x1800060d3  cmp     ecx, 80070247h
0x1800060d9  jz      short loc_1800060ED
0x1800060db  cmp     ecx, 80070272h
0x1800060e1  jnz     short loc_180006135
0x1800060e3  mov     ecx, 0C0000273h
0x1800060e8  jmp     loc_18000618D
0x1800060ed  mov     ecx, 0C0000163h
0x1800060f2  jmp     loc_18000618D
0x1800060f7  mov     ecx, 0C0000161h
0x1800060fc  jmp     loc_18000618D
0x180006101  mov     ecx, 0C0000025h
0x180006106  jmp     loc_18000618D
0x18000610b  mov     ecx, 0C0000095h
0x180006110  jmp     short loc_18000618D
0x180006112  mov     ecx, 0C0000059h
0x180006117  jmp     short loc_18000618D
0x180006119  cmp     ecx, 8007050Ch
0x18000611f  jz      short loc_180006188
0x180006121  cmp     ecx, 8007054Fh
0x180006127  jz      short loc_180006181
0x180006129  cmp     ecx, 800705B9h
0x18000612f  jz      short loc_18000617A
0x180006131  test    ecx, ecx
0x180006133  jz      short loc_180006176
0x180006135  bt      ecx, 1Ch
0x180006139  jnb     short loc_180006141
0x18000613b  btr     ecx, 1Ch
0x18000613f  jmp     short loc_18000618D
0x180006141  mov     eax, ecx
0x180006143  and     eax, 1FFF0000h
0x180006148  cmp     eax, 70000h
0x18000614d  jnz     short loc_180006160
0x18000614f  movzx   ecx, cx
0x180006152  mov     eax, ecx
0x180006154  or      eax, 0C0070000h
0x180006159  test    ecx, ecx
0x18000615b  cmovnz  ecx, eax
0x18000615e  jmp     short loc_18000618D
0x180006160  cmp     eax, 90000h
0x180006165  jnz     short loc_180006181
0x180006167  test    ecx, ecx
0x180006169  jle     short loc_18000618D
0x18000616b  movzx   ecx, cx
0x18000616e  or      ecx, 0C0090000h
0x180006174  jmp     short loc_18000618D
0x180006176  xor     ecx, ecx
0x180006178  jmp     short loc_18000618D
0x18000617a  mov     ecx, 0C000A083h
0x18000617f  jmp     short loc_18000618D
0x180006181  mov     ecx, 0C00000E5h
0x180006186  jmp     short loc_18000618D
0x180006188  mov     ecx, 0C000042Bh
0x18000618d  mov     eax, ecx
0x18000618f  retn
```
