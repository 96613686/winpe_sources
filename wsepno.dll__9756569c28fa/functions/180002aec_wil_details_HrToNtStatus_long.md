# wil::details::HrToNtStatus(long)

- ea: `0x180002aec`
- end: `0x180002ca8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180002688`
- `0x180002eb0`
- `0x1800041e8`
- `0x180004298`
- `0x1800042f0`
- `0x1800043b8`
- `0x180007a28`
- `0x18000da10`
- `0x18000da7b`
- `0x18000db44`
- `0x18000dbaf`

## callees

- `0x180002aec`

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
0x180002aec  mov     eax, 800700EAh
0x180002af1  cmp     ecx, eax
0x180002af3  jg      loc_180002BC8
0x180002af9  jz      loc_180002BBE
0x180002aff  mov     eax, 80070057h
0x180002b04  cmp     ecx, eax
0x180002b06  jg      short loc_180002B72
0x180002b08  jz      short loc_180002B68
0x180002b0a  cmp     ecx, 80004005h
0x180002b10  jz      short loc_180002B5E
0x180002b12  cmp     ecx, 80070001h
0x180002b18  jz      short loc_180002B54
0x180002b1a  cmp     ecx, 80070002h
0x180002b20  jz      short loc_180002B4A
0x180002b22  cmp     ecx, 80070003h
0x180002b28  jz      short loc_180002B40
0x180002b2a  cmp     ecx, 8007000Eh
0x180002b30  jnz     loc_180002C4D
0x180002b36  mov     ecx, 0C0000017h
0x180002b3b  jmp     loc_180002CA5
0x180002b40  mov     ecx, 0C000003Ah
0x180002b45  jmp     loc_180002CA5
0x180002b4a  mov     ecx, 0C0000034h
0x180002b4f  jmp     loc_180002CA5
0x180002b54  mov     ecx, 0C0000002h
0x180002b59  jmp     loc_180002CA5
0x180002b5e  mov     ecx, 0C0000001h
0x180002b63  jmp     loc_180002CA5
0x180002b68  mov     ecx, 0C000000Dh
0x180002b6d  jmp     loc_180002CA5
0x180002b72  cmp     ecx, 80070070h
0x180002b78  jz      short loc_180002BB4
0x180002b7a  cmp     ecx, 8007007Ah
0x180002b80  jz      short loc_180002BAA
0x180002b82  cmp     ecx, 8007007Bh
0x180002b88  jz      short loc_180002BA0
0x180002b8a  cmp     ecx, 8007007Eh
0x180002b90  jnz     loc_180002C4D
0x180002b96  mov     ecx, 0C0000135h
0x180002b9b  jmp     loc_180002CA5
0x180002ba0  mov     ecx, 0C0000033h
0x180002ba5  jmp     loc_180002CA5
0x180002baa  mov     ecx, 0C0000023h
0x180002baf  jmp     loc_180002CA5
0x180002bb4  mov     ecx, 0C000007Fh
0x180002bb9  jmp     loc_180002CA5
0x180002bbe  mov     ecx, 80000005h
0x180002bc3  jmp     loc_180002CA5
0x180002bc8  mov     eax, 8007047Eh
0x180002bcd  cmp     ecx, eax
0x180002bcf  jg      short loc_180002C31
0x180002bd1  jz      short loc_180002C2A
0x180002bd3  cmp     ecx, 80070216h
0x180002bd9  jz      short loc_180002C23
0x180002bdb  cmp     ecx, 8007023Eh
0x180002be1  jz      short loc_180002C19
0x180002be3  cmp     ecx, 80070246h
0x180002be9  jz      short loc_180002C0F
0x180002beb  cmp     ecx, 80070247h
0x180002bf1  jz      short loc_180002C05
0x180002bf3  cmp     ecx, 80070272h
0x180002bf9  jnz     short loc_180002C4D
0x180002bfb  mov     ecx, 0C0000273h
0x180002c00  jmp     loc_180002CA5
0x180002c05  mov     ecx, 0C0000163h
0x180002c0a  jmp     loc_180002CA5
0x180002c0f  mov     ecx, 0C0000161h
0x180002c14  jmp     loc_180002CA5
0x180002c19  mov     ecx, 0C0000025h
0x180002c1e  jmp     loc_180002CA5
0x180002c23  mov     ecx, 0C0000095h
0x180002c28  jmp     short loc_180002CA5
0x180002c2a  mov     ecx, 0C0000059h
0x180002c2f  jmp     short loc_180002CA5
0x180002c31  cmp     ecx, 8007050Ch
0x180002c37  jz      short loc_180002CA0
0x180002c39  cmp     ecx, 8007054Fh
0x180002c3f  jz      short loc_180002C99
0x180002c41  cmp     ecx, 800705B9h
0x180002c47  jz      short loc_180002C92
0x180002c49  test    ecx, ecx
0x180002c4b  jz      short loc_180002C8E
0x180002c4d  bt      ecx, 1Ch
0x180002c51  jnb     short loc_180002C59
0x180002c53  btr     ecx, 1Ch
0x180002c57  jmp     short loc_180002CA5
0x180002c59  mov     eax, ecx
0x180002c5b  and     eax, 1FFF0000h
0x180002c60  cmp     eax, 70000h
0x180002c65  jnz     short loc_180002C78
0x180002c67  movzx   ecx, cx
0x180002c6a  mov     eax, ecx
0x180002c6c  or      eax, 0C0070000h
0x180002c71  test    ecx, ecx
0x180002c73  cmovnz  ecx, eax
0x180002c76  jmp     short loc_180002CA5
0x180002c78  cmp     eax, 90000h
0x180002c7d  jnz     short loc_180002C99
0x180002c7f  test    ecx, ecx
0x180002c81  jle     short loc_180002CA5
0x180002c83  movzx   ecx, cx
0x180002c86  or      ecx, 0C0090000h
0x180002c8c  jmp     short loc_180002CA5
0x180002c8e  xor     ecx, ecx
0x180002c90  jmp     short loc_180002CA5
0x180002c92  mov     ecx, 0C000A083h
0x180002c97  jmp     short loc_180002CA5
0x180002c99  mov     ecx, 0C00000E5h
0x180002c9e  jmp     short loc_180002CA5
0x180002ca0  mov     ecx, 0C000042Bh
0x180002ca5  mov     eax, ecx
0x180002ca7  retn
```
