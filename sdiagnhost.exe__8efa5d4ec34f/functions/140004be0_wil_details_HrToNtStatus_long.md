# wil::details::HrToNtStatus(long)

- ea: `0x140004be0`
- end: `0x140004d9c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f38`
- `0x140002fe0`
- `0x140003030`
- `0x1400030e8`
- `0x140004248`
- `0x140004da4`

## callees

- `0x140004be0`

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
0x140004be0  mov     eax, 800700EAh
0x140004be5  cmp     ecx, eax
0x140004be7  jg      loc_140004CBC
0x140004bed  jz      loc_140004CB2
0x140004bf3  mov     eax, 80070057h
0x140004bf8  cmp     ecx, eax
0x140004bfa  jg      short loc_140004C66
0x140004bfc  jz      short loc_140004C5C
0x140004bfe  cmp     ecx, 80004005h
0x140004c04  jz      short loc_140004C52
0x140004c06  cmp     ecx, 80070001h
0x140004c0c  jz      short loc_140004C48
0x140004c0e  cmp     ecx, 80070002h
0x140004c14  jz      short loc_140004C3E
0x140004c16  cmp     ecx, 80070003h
0x140004c1c  jz      short loc_140004C34
0x140004c1e  cmp     ecx, 8007000Eh
0x140004c24  jnz     loc_140004D41
0x140004c2a  mov     ecx, 0C0000017h
0x140004c2f  jmp     loc_140004D99
0x140004c34  mov     ecx, 0C000003Ah
0x140004c39  jmp     loc_140004D99
0x140004c3e  mov     ecx, 0C0000034h
0x140004c43  jmp     loc_140004D99
0x140004c48  mov     ecx, 0C0000002h
0x140004c4d  jmp     loc_140004D99
0x140004c52  mov     ecx, 0C0000001h
0x140004c57  jmp     loc_140004D99
0x140004c5c  mov     ecx, 0C000000Dh
0x140004c61  jmp     loc_140004D99
0x140004c66  cmp     ecx, 80070070h
0x140004c6c  jz      short loc_140004CA8
0x140004c6e  cmp     ecx, 8007007Ah
0x140004c74  jz      short loc_140004C9E
0x140004c76  cmp     ecx, 8007007Bh
0x140004c7c  jz      short loc_140004C94
0x140004c7e  cmp     ecx, 8007007Eh
0x140004c84  jnz     loc_140004D41
0x140004c8a  mov     ecx, 0C0000135h
0x140004c8f  jmp     loc_140004D99
0x140004c94  mov     ecx, 0C0000033h
0x140004c99  jmp     loc_140004D99
0x140004c9e  mov     ecx, 0C0000023h
0x140004ca3  jmp     loc_140004D99
0x140004ca8  mov     ecx, 0C000007Fh
0x140004cad  jmp     loc_140004D99
0x140004cb2  mov     ecx, 80000005h
0x140004cb7  jmp     loc_140004D99
0x140004cbc  mov     eax, 8007047Eh
0x140004cc1  cmp     ecx, eax
0x140004cc3  jg      short loc_140004D25
0x140004cc5  jz      short loc_140004D1E
0x140004cc7  cmp     ecx, 80070216h
0x140004ccd  jz      short loc_140004D17
0x140004ccf  cmp     ecx, 8007023Eh
0x140004cd5  jz      short loc_140004D0D
0x140004cd7  cmp     ecx, 80070246h
0x140004cdd  jz      short loc_140004D03
0x140004cdf  cmp     ecx, 80070247h
0x140004ce5  jz      short loc_140004CF9
0x140004ce7  cmp     ecx, 80070272h
0x140004ced  jnz     short loc_140004D41
0x140004cef  mov     ecx, 0C0000273h
0x140004cf4  jmp     loc_140004D99
0x140004cf9  mov     ecx, 0C0000163h
0x140004cfe  jmp     loc_140004D99
0x140004d03  mov     ecx, 0C0000161h
0x140004d08  jmp     loc_140004D99
0x140004d0d  mov     ecx, 0C0000025h
0x140004d12  jmp     loc_140004D99
0x140004d17  mov     ecx, 0C0000095h
0x140004d1c  jmp     short loc_140004D99
0x140004d1e  mov     ecx, 0C0000059h
0x140004d23  jmp     short loc_140004D99
0x140004d25  cmp     ecx, 8007050Ch
0x140004d2b  jz      short loc_140004D94
0x140004d2d  cmp     ecx, 8007054Fh
0x140004d33  jz      short loc_140004D8D
0x140004d35  cmp     ecx, 800705B9h
0x140004d3b  jz      short loc_140004D86
0x140004d3d  test    ecx, ecx
0x140004d3f  jz      short loc_140004D82
0x140004d41  bt      ecx, 1Ch
0x140004d45  jnb     short loc_140004D4D
0x140004d47  btr     ecx, 1Ch
0x140004d4b  jmp     short loc_140004D99
0x140004d4d  mov     eax, ecx
0x140004d4f  and     eax, 1FFF0000h
0x140004d54  cmp     eax, 70000h
0x140004d59  jnz     short loc_140004D6C
0x140004d5b  movzx   ecx, cx
0x140004d5e  mov     eax, ecx
0x140004d60  or      eax, 0C0070000h
0x140004d65  test    ecx, ecx
0x140004d67  cmovnz  ecx, eax
0x140004d6a  jmp     short loc_140004D99
0x140004d6c  cmp     eax, 90000h
0x140004d71  jnz     short loc_140004D8D
0x140004d73  test    ecx, ecx
0x140004d75  jle     short loc_140004D99
0x140004d77  movzx   ecx, cx
0x140004d7a  or      ecx, 0C0090000h
0x140004d80  jmp     short loc_140004D99
0x140004d82  xor     ecx, ecx
0x140004d84  jmp     short loc_140004D99
0x140004d86  mov     ecx, 0C000A083h
0x140004d8b  jmp     short loc_140004D99
0x140004d8d  mov     ecx, 0C00000E5h
0x140004d92  jmp     short loc_140004D99
0x140004d94  mov     ecx, 0C000042Bh
0x140004d99  mov     eax, ecx
0x140004d9b  retn
```
