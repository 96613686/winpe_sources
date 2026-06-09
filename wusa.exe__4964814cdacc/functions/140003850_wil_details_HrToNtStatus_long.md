# wil::details::HrToNtStatus(long)

- ea: `0x140003850`
- end: `0x140003a0c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001d90`
- `0x140001e38`
- `0x140001e88`
- `0x140001f48`
- `0x140002e28`
- `0x140003a14`

## callees

- `0x140003850`

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
0x140003850  mov     eax, 800700EAh
0x140003855  cmp     ecx, eax
0x140003857  jg      loc_14000392C
0x14000385d  jz      loc_140003922
0x140003863  mov     eax, 80070057h
0x140003868  cmp     ecx, eax
0x14000386a  jg      short loc_1400038D6
0x14000386c  jz      short loc_1400038CC
0x14000386e  cmp     ecx, 80004005h
0x140003874  jz      short loc_1400038C2
0x140003876  cmp     ecx, 80070001h
0x14000387c  jz      short loc_1400038B8
0x14000387e  cmp     ecx, 80070002h
0x140003884  jz      short loc_1400038AE
0x140003886  cmp     ecx, 80070003h
0x14000388c  jz      short loc_1400038A4
0x14000388e  cmp     ecx, 8007000Eh
0x140003894  jnz     loc_1400039B1
0x14000389a  mov     ecx, 0C0000017h
0x14000389f  jmp     loc_140003A09
0x1400038a4  mov     ecx, 0C000003Ah
0x1400038a9  jmp     loc_140003A09
0x1400038ae  mov     ecx, 0C0000034h
0x1400038b3  jmp     loc_140003A09
0x1400038b8  mov     ecx, 0C0000002h
0x1400038bd  jmp     loc_140003A09
0x1400038c2  mov     ecx, 0C0000001h
0x1400038c7  jmp     loc_140003A09
0x1400038cc  mov     ecx, 0C000000Dh
0x1400038d1  jmp     loc_140003A09
0x1400038d6  cmp     ecx, 80070070h
0x1400038dc  jz      short loc_140003918
0x1400038de  cmp     ecx, 8007007Ah
0x1400038e4  jz      short loc_14000390E
0x1400038e6  cmp     ecx, 8007007Bh
0x1400038ec  jz      short loc_140003904
0x1400038ee  cmp     ecx, 8007007Eh
0x1400038f4  jnz     loc_1400039B1
0x1400038fa  mov     ecx, 0C0000135h
0x1400038ff  jmp     loc_140003A09
0x140003904  mov     ecx, 0C0000033h
0x140003909  jmp     loc_140003A09
0x14000390e  mov     ecx, 0C0000023h
0x140003913  jmp     loc_140003A09
0x140003918  mov     ecx, 0C000007Fh
0x14000391d  jmp     loc_140003A09
0x140003922  mov     ecx, 80000005h
0x140003927  jmp     loc_140003A09
0x14000392c  mov     eax, 8007047Eh
0x140003931  cmp     ecx, eax
0x140003933  jg      short loc_140003995
0x140003935  jz      short loc_14000398E
0x140003937  cmp     ecx, 80070216h
0x14000393d  jz      short loc_140003987
0x14000393f  cmp     ecx, 8007023Eh
0x140003945  jz      short loc_14000397D
0x140003947  cmp     ecx, 80070246h
0x14000394d  jz      short loc_140003973
0x14000394f  cmp     ecx, 80070247h
0x140003955  jz      short loc_140003969
0x140003957  cmp     ecx, 80070272h
0x14000395d  jnz     short loc_1400039B1
0x14000395f  mov     ecx, 0C0000273h
0x140003964  jmp     loc_140003A09
0x140003969  mov     ecx, 0C0000163h
0x14000396e  jmp     loc_140003A09
0x140003973  mov     ecx, 0C0000161h
0x140003978  jmp     loc_140003A09
0x14000397d  mov     ecx, 0C0000025h
0x140003982  jmp     loc_140003A09
0x140003987  mov     ecx, 0C0000095h
0x14000398c  jmp     short loc_140003A09
0x14000398e  mov     ecx, 0C0000059h
0x140003993  jmp     short loc_140003A09
0x140003995  cmp     ecx, 8007050Ch
0x14000399b  jz      short loc_140003A04
0x14000399d  cmp     ecx, 8007054Fh
0x1400039a3  jz      short loc_1400039FD
0x1400039a5  cmp     ecx, 800705B9h
0x1400039ab  jz      short loc_1400039F6
0x1400039ad  test    ecx, ecx
0x1400039af  jz      short loc_1400039F2
0x1400039b1  bt      ecx, 1Ch
0x1400039b5  jnb     short loc_1400039BD
0x1400039b7  btr     ecx, 1Ch
0x1400039bb  jmp     short loc_140003A09
0x1400039bd  mov     eax, ecx
0x1400039bf  and     eax, 1FFF0000h
0x1400039c4  cmp     eax, 70000h
0x1400039c9  jnz     short loc_1400039DC
0x1400039cb  movzx   ecx, cx
0x1400039ce  mov     eax, ecx
0x1400039d0  or      eax, 0C0070000h
0x1400039d5  test    ecx, ecx
0x1400039d7  cmovnz  ecx, eax
0x1400039da  jmp     short loc_140003A09
0x1400039dc  cmp     eax, 90000h
0x1400039e1  jnz     short loc_1400039FD
0x1400039e3  test    ecx, ecx
0x1400039e5  jle     short loc_140003A09
0x1400039e7  movzx   ecx, cx
0x1400039ea  or      ecx, 0C0090000h
0x1400039f0  jmp     short loc_140003A09
0x1400039f2  xor     ecx, ecx
0x1400039f4  jmp     short loc_140003A09
0x1400039f6  mov     ecx, 0C000A083h
0x1400039fb  jmp     short loc_140003A09
0x1400039fd  mov     ecx, 0C00000E5h
0x140003a02  jmp     short loc_140003A09
0x140003a04  mov     ecx, 0C000042Bh
0x140003a09  mov     eax, ecx
0x140003a0b  retn
```
