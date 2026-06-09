# wil::details::HrToNtStatus(long)

- ea: `0x18000510c`
- end: `0x1800052c8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003324`
- `0x1800033cc`
- `0x18000341c`
- `0x1800034dc`
- `0x1800046d8`
- `0x1800052d0`

## callees

- `0x18000510c`

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
0x18000510c  mov     eax, 800700EAh
0x180005111  cmp     ecx, eax
0x180005113  jg      loc_1800051E8
0x180005119  jz      loc_1800051DE
0x18000511f  mov     eax, 80070057h
0x180005124  cmp     ecx, eax
0x180005126  jg      short loc_180005192
0x180005128  jz      short loc_180005188
0x18000512a  cmp     ecx, 80004005h
0x180005130  jz      short loc_18000517E
0x180005132  cmp     ecx, 80070001h
0x180005138  jz      short loc_180005174
0x18000513a  cmp     ecx, 80070002h
0x180005140  jz      short loc_18000516A
0x180005142  cmp     ecx, 80070003h
0x180005148  jz      short loc_180005160
0x18000514a  cmp     ecx, 8007000Eh
0x180005150  jnz     loc_18000526D
0x180005156  mov     ecx, 0C0000017h
0x18000515b  jmp     loc_1800052C5
0x180005160  mov     ecx, 0C000003Ah
0x180005165  jmp     loc_1800052C5
0x18000516a  mov     ecx, 0C0000034h
0x18000516f  jmp     loc_1800052C5
0x180005174  mov     ecx, 0C0000002h
0x180005179  jmp     loc_1800052C5
0x18000517e  mov     ecx, 0C0000001h
0x180005183  jmp     loc_1800052C5
0x180005188  mov     ecx, 0C000000Dh
0x18000518d  jmp     loc_1800052C5
0x180005192  cmp     ecx, 80070070h
0x180005198  jz      short loc_1800051D4
0x18000519a  cmp     ecx, 8007007Ah
0x1800051a0  jz      short loc_1800051CA
0x1800051a2  cmp     ecx, 8007007Bh
0x1800051a8  jz      short loc_1800051C0
0x1800051aa  cmp     ecx, 8007007Eh
0x1800051b0  jnz     loc_18000526D
0x1800051b6  mov     ecx, 0C0000135h
0x1800051bb  jmp     loc_1800052C5
0x1800051c0  mov     ecx, 0C0000033h
0x1800051c5  jmp     loc_1800052C5
0x1800051ca  mov     ecx, 0C0000023h
0x1800051cf  jmp     loc_1800052C5
0x1800051d4  mov     ecx, 0C000007Fh
0x1800051d9  jmp     loc_1800052C5
0x1800051de  mov     ecx, 80000005h
0x1800051e3  jmp     loc_1800052C5
0x1800051e8  mov     eax, 8007047Eh
0x1800051ed  cmp     ecx, eax
0x1800051ef  jg      short loc_180005251
0x1800051f1  jz      short loc_18000524A
0x1800051f3  cmp     ecx, 80070216h
0x1800051f9  jz      short loc_180005243
0x1800051fb  cmp     ecx, 8007023Eh
0x180005201  jz      short loc_180005239
0x180005203  cmp     ecx, 80070246h
0x180005209  jz      short loc_18000522F
0x18000520b  cmp     ecx, 80070247h
0x180005211  jz      short loc_180005225
0x180005213  cmp     ecx, 80070272h
0x180005219  jnz     short loc_18000526D
0x18000521b  mov     ecx, 0C0000273h
0x180005220  jmp     loc_1800052C5
0x180005225  mov     ecx, 0C0000163h
0x18000522a  jmp     loc_1800052C5
0x18000522f  mov     ecx, 0C0000161h
0x180005234  jmp     loc_1800052C5
0x180005239  mov     ecx, 0C0000025h
0x18000523e  jmp     loc_1800052C5
0x180005243  mov     ecx, 0C0000095h
0x180005248  jmp     short loc_1800052C5
0x18000524a  mov     ecx, 0C0000059h
0x18000524f  jmp     short loc_1800052C5
0x180005251  cmp     ecx, 8007050Ch
0x180005257  jz      short loc_1800052C0
0x180005259  cmp     ecx, 8007054Fh
0x18000525f  jz      short loc_1800052B9
0x180005261  cmp     ecx, 800705B9h
0x180005267  jz      short loc_1800052B2
0x180005269  test    ecx, ecx
0x18000526b  jz      short loc_1800052AE
0x18000526d  bt      ecx, 1Ch
0x180005271  jnb     short loc_180005279
0x180005273  btr     ecx, 1Ch
0x180005277  jmp     short loc_1800052C5
0x180005279  mov     eax, ecx
0x18000527b  and     eax, 1FFF0000h
0x180005280  cmp     eax, 70000h
0x180005285  jnz     short loc_180005298
0x180005287  movzx   ecx, cx
0x18000528a  mov     eax, ecx
0x18000528c  or      eax, 0C0070000h
0x180005291  test    ecx, ecx
0x180005293  cmovnz  ecx, eax
0x180005296  jmp     short loc_1800052C5
0x180005298  cmp     eax, 90000h
0x18000529d  jnz     short loc_1800052B9
0x18000529f  test    ecx, ecx
0x1800052a1  jle     short loc_1800052C5
0x1800052a3  movzx   ecx, cx
0x1800052a6  or      ecx, 0C0090000h
0x1800052ac  jmp     short loc_1800052C5
0x1800052ae  xor     ecx, ecx
0x1800052b0  jmp     short loc_1800052C5
0x1800052b2  mov     ecx, 0C000A083h
0x1800052b7  jmp     short loc_1800052C5
0x1800052b9  mov     ecx, 0C00000E5h
0x1800052be  jmp     short loc_1800052C5
0x1800052c0  mov     ecx, 0C000042Bh
0x1800052c5  mov     eax, ecx
0x1800052c7  retn
```
