# wil::details::HrToNtStatus(long)

- ea: `0x180005aec`
- end: `0x180005ca8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d64`
- `0x180002e04`
- `0x180002e54`
- `0x180002f14`
- `0x1800050c8`
- `0x1800060c4`

## callees

- `0x180005aec`

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
0x180005aec  mov     eax, 800700EAh
0x180005af1  cmp     ecx, eax
0x180005af3  jg      loc_180005BC8
0x180005af9  jz      loc_180005BBE
0x180005aff  mov     eax, 80070057h
0x180005b04  cmp     ecx, eax
0x180005b06  jg      short loc_180005B72
0x180005b08  jz      short loc_180005B68
0x180005b0a  cmp     ecx, 80004005h
0x180005b10  jz      short loc_180005B5E
0x180005b12  cmp     ecx, 80070001h
0x180005b18  jz      short loc_180005B54
0x180005b1a  cmp     ecx, 80070002h
0x180005b20  jz      short loc_180005B4A
0x180005b22  cmp     ecx, 80070003h
0x180005b28  jz      short loc_180005B40
0x180005b2a  cmp     ecx, 8007000Eh
0x180005b30  jnz     loc_180005C4D
0x180005b36  mov     ecx, 0C0000017h
0x180005b3b  jmp     loc_180005CA5
0x180005b40  mov     ecx, 0C000003Ah
0x180005b45  jmp     loc_180005CA5
0x180005b4a  mov     ecx, 0C0000034h
0x180005b4f  jmp     loc_180005CA5
0x180005b54  mov     ecx, 0C0000002h
0x180005b59  jmp     loc_180005CA5
0x180005b5e  mov     ecx, 0C0000001h
0x180005b63  jmp     loc_180005CA5
0x180005b68  mov     ecx, 0C000000Dh
0x180005b6d  jmp     loc_180005CA5
0x180005b72  cmp     ecx, 80070070h
0x180005b78  jz      short loc_180005BB4
0x180005b7a  cmp     ecx, 8007007Ah
0x180005b80  jz      short loc_180005BAA
0x180005b82  cmp     ecx, 8007007Bh
0x180005b88  jz      short loc_180005BA0
0x180005b8a  cmp     ecx, 8007007Eh
0x180005b90  jnz     loc_180005C4D
0x180005b96  mov     ecx, 0C0000135h
0x180005b9b  jmp     loc_180005CA5
0x180005ba0  mov     ecx, 0C0000033h
0x180005ba5  jmp     loc_180005CA5
0x180005baa  mov     ecx, 0C0000023h
0x180005baf  jmp     loc_180005CA5
0x180005bb4  mov     ecx, 0C000007Fh
0x180005bb9  jmp     loc_180005CA5
0x180005bbe  mov     ecx, 80000005h
0x180005bc3  jmp     loc_180005CA5
0x180005bc8  mov     eax, 8007047Eh
0x180005bcd  cmp     ecx, eax
0x180005bcf  jg      short loc_180005C31
0x180005bd1  jz      short loc_180005C2A
0x180005bd3  cmp     ecx, 80070216h
0x180005bd9  jz      short loc_180005C23
0x180005bdb  cmp     ecx, 8007023Eh
0x180005be1  jz      short loc_180005C19
0x180005be3  cmp     ecx, 80070246h
0x180005be9  jz      short loc_180005C0F
0x180005beb  cmp     ecx, 80070247h
0x180005bf1  jz      short loc_180005C05
0x180005bf3  cmp     ecx, 80070272h
0x180005bf9  jnz     short loc_180005C4D
0x180005bfb  mov     ecx, 0C0000273h
0x180005c00  jmp     loc_180005CA5
0x180005c05  mov     ecx, 0C0000163h
0x180005c0a  jmp     loc_180005CA5
0x180005c0f  mov     ecx, 0C0000161h
0x180005c14  jmp     loc_180005CA5
0x180005c19  mov     ecx, 0C0000025h
0x180005c1e  jmp     loc_180005CA5
0x180005c23  mov     ecx, 0C0000095h
0x180005c28  jmp     short loc_180005CA5
0x180005c2a  mov     ecx, 0C0000059h
0x180005c2f  jmp     short loc_180005CA5
0x180005c31  cmp     ecx, 8007050Ch
0x180005c37  jz      short loc_180005CA0
0x180005c39  cmp     ecx, 8007054Fh
0x180005c3f  jz      short loc_180005C99
0x180005c41  cmp     ecx, 800705B9h
0x180005c47  jz      short loc_180005C92
0x180005c49  test    ecx, ecx
0x180005c4b  jz      short loc_180005C8E
0x180005c4d  bt      ecx, 1Ch
0x180005c51  jnb     short loc_180005C59
0x180005c53  btr     ecx, 1Ch
0x180005c57  jmp     short loc_180005CA5
0x180005c59  mov     eax, ecx
0x180005c5b  and     eax, 1FFF0000h
0x180005c60  cmp     eax, 70000h
0x180005c65  jnz     short loc_180005C78
0x180005c67  movzx   ecx, cx
0x180005c6a  mov     eax, ecx
0x180005c6c  or      eax, 0C0070000h
0x180005c71  test    ecx, ecx
0x180005c73  cmovnz  ecx, eax
0x180005c76  jmp     short loc_180005CA5
0x180005c78  cmp     eax, 90000h
0x180005c7d  jnz     short loc_180005C99
0x180005c7f  test    ecx, ecx
0x180005c81  jle     short loc_180005CA5
0x180005c83  movzx   ecx, cx
0x180005c86  or      ecx, 0C0090000h
0x180005c8c  jmp     short loc_180005CA5
0x180005c8e  xor     ecx, ecx
0x180005c90  jmp     short loc_180005CA5
0x180005c92  mov     ecx, 0C000A083h
0x180005c97  jmp     short loc_180005CA5
0x180005c99  mov     ecx, 0C00000E5h
0x180005c9e  jmp     short loc_180005CA5
0x180005ca0  mov     ecx, 0C000042Bh
0x180005ca5  mov     eax, ecx
0x180005ca7  retn
```
