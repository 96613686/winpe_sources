# wil::details::HrToNtStatus(long)

- ea: `0x180004c34`
- end: `0x180004df0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004bb0`
- `0x180006798`
- `0x180006810`
- `0x180006860`
- `0x180007e6c`
- `0x180008f6c`

## callees

- `0x180004c34`

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
0x180004c34  mov     eax, 800700EAh
0x180004c39  cmp     ecx, eax
0x180004c3b  jg      loc_180004D10
0x180004c41  jz      loc_180004D06
0x180004c47  mov     eax, 80070057h
0x180004c4c  cmp     ecx, eax
0x180004c4e  jg      short loc_180004CBA
0x180004c50  jz      short loc_180004CB0
0x180004c52  cmp     ecx, 80004005h
0x180004c58  jz      short loc_180004CA6
0x180004c5a  cmp     ecx, 80070001h
0x180004c60  jz      short loc_180004C9C
0x180004c62  cmp     ecx, 80070002h
0x180004c68  jz      short loc_180004C92
0x180004c6a  cmp     ecx, 80070003h
0x180004c70  jz      short loc_180004C88
0x180004c72  cmp     ecx, 8007000Eh
0x180004c78  jnz     loc_180004D95
0x180004c7e  mov     ecx, 0C0000017h
0x180004c83  jmp     loc_180004DED
0x180004c88  mov     ecx, 0C000003Ah
0x180004c8d  jmp     loc_180004DED
0x180004c92  mov     ecx, 0C0000034h
0x180004c97  jmp     loc_180004DED
0x180004c9c  mov     ecx, 0C0000002h
0x180004ca1  jmp     loc_180004DED
0x180004ca6  mov     ecx, 0C0000001h
0x180004cab  jmp     loc_180004DED
0x180004cb0  mov     ecx, 0C000000Dh
0x180004cb5  jmp     loc_180004DED
0x180004cba  cmp     ecx, 80070070h
0x180004cc0  jz      short loc_180004CFC
0x180004cc2  cmp     ecx, 8007007Ah
0x180004cc8  jz      short loc_180004CF2
0x180004cca  cmp     ecx, 8007007Bh
0x180004cd0  jz      short loc_180004CE8
0x180004cd2  cmp     ecx, 8007007Eh
0x180004cd8  jnz     loc_180004D95
0x180004cde  mov     ecx, 0C0000135h
0x180004ce3  jmp     loc_180004DED
0x180004ce8  mov     ecx, 0C0000033h
0x180004ced  jmp     loc_180004DED
0x180004cf2  mov     ecx, 0C0000023h
0x180004cf7  jmp     loc_180004DED
0x180004cfc  mov     ecx, 0C000007Fh
0x180004d01  jmp     loc_180004DED
0x180004d06  mov     ecx, 80000005h
0x180004d0b  jmp     loc_180004DED
0x180004d10  mov     eax, 8007047Eh
0x180004d15  cmp     ecx, eax
0x180004d17  jg      short loc_180004D79
0x180004d19  jz      short loc_180004D72
0x180004d1b  cmp     ecx, 80070216h
0x180004d21  jz      short loc_180004D6B
0x180004d23  cmp     ecx, 8007023Eh
0x180004d29  jz      short loc_180004D61
0x180004d2b  cmp     ecx, 80070246h
0x180004d31  jz      short loc_180004D57
0x180004d33  cmp     ecx, 80070247h
0x180004d39  jz      short loc_180004D4D
0x180004d3b  cmp     ecx, 80070272h
0x180004d41  jnz     short loc_180004D95
0x180004d43  mov     ecx, 0C0000273h
0x180004d48  jmp     loc_180004DED
0x180004d4d  mov     ecx, 0C0000163h
0x180004d52  jmp     loc_180004DED
0x180004d57  mov     ecx, 0C0000161h
0x180004d5c  jmp     loc_180004DED
0x180004d61  mov     ecx, 0C0000025h
0x180004d66  jmp     loc_180004DED
0x180004d6b  mov     ecx, 0C0000095h
0x180004d70  jmp     short loc_180004DED
0x180004d72  mov     ecx, 0C0000059h
0x180004d77  jmp     short loc_180004DED
0x180004d79  cmp     ecx, 8007050Ch
0x180004d7f  jz      short loc_180004DE8
0x180004d81  cmp     ecx, 8007054Fh
0x180004d87  jz      short loc_180004DE1
0x180004d89  cmp     ecx, 800705B9h
0x180004d8f  jz      short loc_180004DDA
0x180004d91  test    ecx, ecx
0x180004d93  jz      short loc_180004DD6
0x180004d95  bt      ecx, 1Ch
0x180004d99  jnb     short loc_180004DA1
0x180004d9b  btr     ecx, 1Ch
0x180004d9f  jmp     short loc_180004DED
0x180004da1  mov     eax, ecx
0x180004da3  and     eax, 1FFF0000h
0x180004da8  cmp     eax, 70000h
0x180004dad  jnz     short loc_180004DC0
0x180004daf  movzx   ecx, cx
0x180004db2  mov     eax, ecx
0x180004db4  or      eax, 0C0070000h
0x180004db9  test    ecx, ecx
0x180004dbb  cmovnz  ecx, eax
0x180004dbe  jmp     short loc_180004DED
0x180004dc0  cmp     eax, 90000h
0x180004dc5  jnz     short loc_180004DE1
0x180004dc7  test    ecx, ecx
0x180004dc9  jle     short loc_180004DED
0x180004dcb  movzx   ecx, cx
0x180004dce  or      ecx, 0C0090000h
0x180004dd4  jmp     short loc_180004DED
0x180004dd6  xor     ecx, ecx
0x180004dd8  jmp     short loc_180004DED
0x180004dda  mov     ecx, 0C000A083h
0x180004ddf  jmp     short loc_180004DED
0x180004de1  mov     ecx, 0C00000E5h
0x180004de6  jmp     short loc_180004DED
0x180004de8  mov     ecx, 0C000042Bh
0x180004ded  mov     eax, ecx
0x180004def  retn
```
