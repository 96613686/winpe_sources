# wil::details::HrToNtStatus(long)

- ea: `0x180004c6c`
- end: `0x180004e28`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032a4`
- `0x180003344`
- `0x180003394`
- `0x18000344c`
- `0x180004248`
- `0x180004e30`

## callees

- `0x180004c6c`

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
0x180004c6c  mov     eax, 800700EAh
0x180004c71  cmp     ecx, eax
0x180004c73  jg      loc_180004D48
0x180004c79  jz      loc_180004D3E
0x180004c7f  mov     eax, 80070057h
0x180004c84  cmp     ecx, eax
0x180004c86  jg      short loc_180004CF2
0x180004c88  jz      short loc_180004CE8
0x180004c8a  cmp     ecx, 80004005h
0x180004c90  jz      short loc_180004CDE
0x180004c92  cmp     ecx, 80070001h
0x180004c98  jz      short loc_180004CD4
0x180004c9a  cmp     ecx, 80070002h
0x180004ca0  jz      short loc_180004CCA
0x180004ca2  cmp     ecx, 80070003h
0x180004ca8  jz      short loc_180004CC0
0x180004caa  cmp     ecx, 8007000Eh
0x180004cb0  jnz     loc_180004DCD
0x180004cb6  mov     ecx, 0C0000017h
0x180004cbb  jmp     loc_180004E25
0x180004cc0  mov     ecx, 0C000003Ah
0x180004cc5  jmp     loc_180004E25
0x180004cca  mov     ecx, 0C0000034h
0x180004ccf  jmp     loc_180004E25
0x180004cd4  mov     ecx, 0C0000002h
0x180004cd9  jmp     loc_180004E25
0x180004cde  mov     ecx, 0C0000001h
0x180004ce3  jmp     loc_180004E25
0x180004ce8  mov     ecx, 0C000000Dh
0x180004ced  jmp     loc_180004E25
0x180004cf2  cmp     ecx, 80070070h
0x180004cf8  jz      short loc_180004D34
0x180004cfa  cmp     ecx, 8007007Ah
0x180004d00  jz      short loc_180004D2A
0x180004d02  cmp     ecx, 8007007Bh
0x180004d08  jz      short loc_180004D20
0x180004d0a  cmp     ecx, 8007007Eh
0x180004d10  jnz     loc_180004DCD
0x180004d16  mov     ecx, 0C0000135h
0x180004d1b  jmp     loc_180004E25
0x180004d20  mov     ecx, 0C0000033h
0x180004d25  jmp     loc_180004E25
0x180004d2a  mov     ecx, 0C0000023h
0x180004d2f  jmp     loc_180004E25
0x180004d34  mov     ecx, 0C000007Fh
0x180004d39  jmp     loc_180004E25
0x180004d3e  mov     ecx, 80000005h
0x180004d43  jmp     loc_180004E25
0x180004d48  mov     eax, 8007047Eh
0x180004d4d  cmp     ecx, eax
0x180004d4f  jg      short loc_180004DB1
0x180004d51  jz      short loc_180004DAA
0x180004d53  cmp     ecx, 80070216h
0x180004d59  jz      short loc_180004DA3
0x180004d5b  cmp     ecx, 8007023Eh
0x180004d61  jz      short loc_180004D99
0x180004d63  cmp     ecx, 80070246h
0x180004d69  jz      short loc_180004D8F
0x180004d6b  cmp     ecx, 80070247h
0x180004d71  jz      short loc_180004D85
0x180004d73  cmp     ecx, 80070272h
0x180004d79  jnz     short loc_180004DCD
0x180004d7b  mov     ecx, 0C0000273h
0x180004d80  jmp     loc_180004E25
0x180004d85  mov     ecx, 0C0000163h
0x180004d8a  jmp     loc_180004E25
0x180004d8f  mov     ecx, 0C0000161h
0x180004d94  jmp     loc_180004E25
0x180004d99  mov     ecx, 0C0000025h
0x180004d9e  jmp     loc_180004E25
0x180004da3  mov     ecx, 0C0000095h
0x180004da8  jmp     short loc_180004E25
0x180004daa  mov     ecx, 0C0000059h
0x180004daf  jmp     short loc_180004E25
0x180004db1  cmp     ecx, 8007050Ch
0x180004db7  jz      short loc_180004E20
0x180004db9  cmp     ecx, 8007054Fh
0x180004dbf  jz      short loc_180004E19
0x180004dc1  cmp     ecx, 800705B9h
0x180004dc7  jz      short loc_180004E12
0x180004dc9  test    ecx, ecx
0x180004dcb  jz      short loc_180004E0E
0x180004dcd  bt      ecx, 1Ch
0x180004dd1  jnb     short loc_180004DD9
0x180004dd3  btr     ecx, 1Ch
0x180004dd7  jmp     short loc_180004E25
0x180004dd9  mov     eax, ecx
0x180004ddb  and     eax, 1FFF0000h
0x180004de0  cmp     eax, 70000h
0x180004de5  jnz     short loc_180004DF8
0x180004de7  movzx   ecx, cx
0x180004dea  mov     eax, ecx
0x180004dec  or      eax, 0C0070000h
0x180004df1  test    ecx, ecx
0x180004df3  cmovnz  ecx, eax
0x180004df6  jmp     short loc_180004E25
0x180004df8  cmp     eax, 90000h
0x180004dfd  jnz     short loc_180004E19
0x180004dff  test    ecx, ecx
0x180004e01  jle     short loc_180004E25
0x180004e03  movzx   ecx, cx
0x180004e06  or      ecx, 0C0090000h
0x180004e0c  jmp     short loc_180004E25
0x180004e0e  xor     ecx, ecx
0x180004e10  jmp     short loc_180004E25
0x180004e12  mov     ecx, 0C000A083h
0x180004e17  jmp     short loc_180004E25
0x180004e19  mov     ecx, 0C00000E5h
0x180004e1e  jmp     short loc_180004E25
0x180004e20  mov     ecx, 0C000042Bh
0x180004e25  mov     eax, ecx
0x180004e27  retn
```
