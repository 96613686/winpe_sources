# wil::details::HrToNtStatus(long)

- ea: `0x18001ccd8`
- end: `0x18001ce94`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001454c`
- `0x1800145c4`
- `0x180014614`
- `0x1800146cc`
- `0x18001b064`
- `0x18001d4e4`

## callees

- `0x18001ccd8`

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
0x18001ccd8  mov     eax, 800700EAh
0x18001ccdd  cmp     ecx, eax
0x18001ccdf  jg      loc_18001CDB4
0x18001cce5  jz      loc_18001CDAA
0x18001cceb  mov     eax, 80070057h
0x18001ccf0  cmp     ecx, eax
0x18001ccf2  jg      short loc_18001CD5E
0x18001ccf4  jz      short loc_18001CD54
0x18001ccf6  cmp     ecx, 80004005h
0x18001ccfc  jz      short loc_18001CD4A
0x18001ccfe  cmp     ecx, 80070001h
0x18001cd04  jz      short loc_18001CD40
0x18001cd06  cmp     ecx, 80070002h
0x18001cd0c  jz      short loc_18001CD36
0x18001cd0e  cmp     ecx, 80070003h
0x18001cd14  jz      short loc_18001CD2C
0x18001cd16  cmp     ecx, 8007000Eh
0x18001cd1c  jnz     loc_18001CE39
0x18001cd22  mov     ecx, 0C0000017h
0x18001cd27  jmp     loc_18001CE91
0x18001cd2c  mov     ecx, 0C000003Ah
0x18001cd31  jmp     loc_18001CE91
0x18001cd36  mov     ecx, 0C0000034h
0x18001cd3b  jmp     loc_18001CE91
0x18001cd40  mov     ecx, 0C0000002h
0x18001cd45  jmp     loc_18001CE91
0x18001cd4a  mov     ecx, 0C0000001h
0x18001cd4f  jmp     loc_18001CE91
0x18001cd54  mov     ecx, 0C000000Dh
0x18001cd59  jmp     loc_18001CE91
0x18001cd5e  cmp     ecx, 80070070h
0x18001cd64  jz      short loc_18001CDA0
0x18001cd66  cmp     ecx, 8007007Ah
0x18001cd6c  jz      short loc_18001CD96
0x18001cd6e  cmp     ecx, 8007007Bh
0x18001cd74  jz      short loc_18001CD8C
0x18001cd76  cmp     ecx, 8007007Eh
0x18001cd7c  jnz     loc_18001CE39
0x18001cd82  mov     ecx, 0C0000135h
0x18001cd87  jmp     loc_18001CE91
0x18001cd8c  mov     ecx, 0C0000033h
0x18001cd91  jmp     loc_18001CE91
0x18001cd96  mov     ecx, 0C0000023h
0x18001cd9b  jmp     loc_18001CE91
0x18001cda0  mov     ecx, 0C000007Fh
0x18001cda5  jmp     loc_18001CE91
0x18001cdaa  mov     ecx, 80000005h
0x18001cdaf  jmp     loc_18001CE91
0x18001cdb4  mov     eax, 8007047Eh
0x18001cdb9  cmp     ecx, eax
0x18001cdbb  jg      short loc_18001CE1D
0x18001cdbd  jz      short loc_18001CE16
0x18001cdbf  cmp     ecx, 80070216h
0x18001cdc5  jz      short loc_18001CE0F
0x18001cdc7  cmp     ecx, 8007023Eh
0x18001cdcd  jz      short loc_18001CE05
0x18001cdcf  cmp     ecx, 80070246h
0x18001cdd5  jz      short loc_18001CDFB
0x18001cdd7  cmp     ecx, 80070247h
0x18001cddd  jz      short loc_18001CDF1
0x18001cddf  cmp     ecx, 80070272h
0x18001cde5  jnz     short loc_18001CE39
0x18001cde7  mov     ecx, 0C0000273h
0x18001cdec  jmp     loc_18001CE91
0x18001cdf1  mov     ecx, 0C0000163h
0x18001cdf6  jmp     loc_18001CE91
0x18001cdfb  mov     ecx, 0C0000161h
0x18001ce00  jmp     loc_18001CE91
0x18001ce05  mov     ecx, 0C0000025h
0x18001ce0a  jmp     loc_18001CE91
0x18001ce0f  mov     ecx, 0C0000095h
0x18001ce14  jmp     short loc_18001CE91
0x18001ce16  mov     ecx, 0C0000059h
0x18001ce1b  jmp     short loc_18001CE91
0x18001ce1d  cmp     ecx, 8007050Ch
0x18001ce23  jz      short loc_18001CE8C
0x18001ce25  cmp     ecx, 8007054Fh
0x18001ce2b  jz      short loc_18001CE85
0x18001ce2d  cmp     ecx, 800705B9h
0x18001ce33  jz      short loc_18001CE7E
0x18001ce35  test    ecx, ecx
0x18001ce37  jz      short loc_18001CE7A
0x18001ce39  bt      ecx, 1Ch
0x18001ce3d  jnb     short loc_18001CE45
0x18001ce3f  btr     ecx, 1Ch
0x18001ce43  jmp     short loc_18001CE91
0x18001ce45  mov     eax, ecx
0x18001ce47  and     eax, 1FFF0000h
0x18001ce4c  cmp     eax, 70000h
0x18001ce51  jnz     short loc_18001CE64
0x18001ce53  movzx   ecx, cx
0x18001ce56  mov     eax, ecx
0x18001ce58  or      eax, 0C0070000h
0x18001ce5d  test    ecx, ecx
0x18001ce5f  cmovnz  ecx, eax
0x18001ce62  jmp     short loc_18001CE91
0x18001ce64  cmp     eax, 90000h
0x18001ce69  jnz     short loc_18001CE85
0x18001ce6b  test    ecx, ecx
0x18001ce6d  jle     short loc_18001CE91
0x18001ce6f  movzx   ecx, cx
0x18001ce72  or      ecx, 0C0090000h
0x18001ce78  jmp     short loc_18001CE91
0x18001ce7a  xor     ecx, ecx
0x18001ce7c  jmp     short loc_18001CE91
0x18001ce7e  mov     ecx, 0C000A083h
0x18001ce83  jmp     short loc_18001CE91
0x18001ce85  mov     ecx, 0C00000E5h
0x18001ce8a  jmp     short loc_18001CE91
0x18001ce8c  mov     ecx, 0C000042Bh
0x18001ce91  mov     eax, ecx
0x18001ce93  retn
```
