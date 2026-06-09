# wil::details::HrToNtStatus(long)

- ea: `0x180019ef0`
- end: `0x18001a0ac`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180017a5c`
- `0x180017ad4`
- `0x180017b24`
- `0x180017be4`
- `0x180019458`
- `0x18001a1f8`

## callees

- `0x180019ef0`

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
0x180019ef0  mov     eax, 800700EAh
0x180019ef5  cmp     ecx, eax
0x180019ef7  jg      loc_180019FCC
0x180019efd  jz      loc_180019FC2
0x180019f03  mov     eax, 80070057h
0x180019f08  cmp     ecx, eax
0x180019f0a  jg      short loc_180019F76
0x180019f0c  jz      short loc_180019F6C
0x180019f0e  cmp     ecx, 80004005h
0x180019f14  jz      short loc_180019F62
0x180019f16  cmp     ecx, 80070001h
0x180019f1c  jz      short loc_180019F58
0x180019f1e  cmp     ecx, 80070002h
0x180019f24  jz      short loc_180019F4E
0x180019f26  cmp     ecx, 80070003h
0x180019f2c  jz      short loc_180019F44
0x180019f2e  cmp     ecx, 8007000Eh
0x180019f34  jnz     loc_18001A051
0x180019f3a  mov     ecx, 0C0000017h
0x180019f3f  jmp     loc_18001A0A9
0x180019f44  mov     ecx, 0C000003Ah
0x180019f49  jmp     loc_18001A0A9
0x180019f4e  mov     ecx, 0C0000034h
0x180019f53  jmp     loc_18001A0A9
0x180019f58  mov     ecx, 0C0000002h
0x180019f5d  jmp     loc_18001A0A9
0x180019f62  mov     ecx, 0C0000001h
0x180019f67  jmp     loc_18001A0A9
0x180019f6c  mov     ecx, 0C000000Dh
0x180019f71  jmp     loc_18001A0A9
0x180019f76  cmp     ecx, 80070070h
0x180019f7c  jz      short loc_180019FB8
0x180019f7e  cmp     ecx, 8007007Ah
0x180019f84  jz      short loc_180019FAE
0x180019f86  cmp     ecx, 8007007Bh
0x180019f8c  jz      short loc_180019FA4
0x180019f8e  cmp     ecx, 8007007Eh
0x180019f94  jnz     loc_18001A051
0x180019f9a  mov     ecx, 0C0000135h
0x180019f9f  jmp     loc_18001A0A9
0x180019fa4  mov     ecx, 0C0000033h
0x180019fa9  jmp     loc_18001A0A9
0x180019fae  mov     ecx, 0C0000023h
0x180019fb3  jmp     loc_18001A0A9
0x180019fb8  mov     ecx, 0C000007Fh
0x180019fbd  jmp     loc_18001A0A9
0x180019fc2  mov     ecx, 80000005h
0x180019fc7  jmp     loc_18001A0A9
0x180019fcc  mov     eax, 8007047Eh
0x180019fd1  cmp     ecx, eax
0x180019fd3  jg      short loc_18001A035
0x180019fd5  jz      short loc_18001A02E
0x180019fd7  cmp     ecx, 80070216h
0x180019fdd  jz      short loc_18001A027
0x180019fdf  cmp     ecx, 8007023Eh
0x180019fe5  jz      short loc_18001A01D
0x180019fe7  cmp     ecx, 80070246h
0x180019fed  jz      short loc_18001A013
0x180019fef  cmp     ecx, 80070247h
0x180019ff5  jz      short loc_18001A009
0x180019ff7  cmp     ecx, 80070272h
0x180019ffd  jnz     short loc_18001A051
0x180019fff  mov     ecx, 0C0000273h
0x18001a004  jmp     loc_18001A0A9
0x18001a009  mov     ecx, 0C0000163h
0x18001a00e  jmp     loc_18001A0A9
0x18001a013  mov     ecx, 0C0000161h
0x18001a018  jmp     loc_18001A0A9
0x18001a01d  mov     ecx, 0C0000025h
0x18001a022  jmp     loc_18001A0A9
0x18001a027  mov     ecx, 0C0000095h
0x18001a02c  jmp     short loc_18001A0A9
0x18001a02e  mov     ecx, 0C0000059h
0x18001a033  jmp     short loc_18001A0A9
0x18001a035  cmp     ecx, 8007050Ch
0x18001a03b  jz      short loc_18001A0A4
0x18001a03d  cmp     ecx, 8007054Fh
0x18001a043  jz      short loc_18001A09D
0x18001a045  cmp     ecx, 800705B9h
0x18001a04b  jz      short loc_18001A096
0x18001a04d  test    ecx, ecx
0x18001a04f  jz      short loc_18001A092
0x18001a051  bt      ecx, 1Ch
0x18001a055  jnb     short loc_18001A05D
0x18001a057  btr     ecx, 1Ch
0x18001a05b  jmp     short loc_18001A0A9
0x18001a05d  mov     eax, ecx
0x18001a05f  and     eax, 1FFF0000h
0x18001a064  cmp     eax, 70000h
0x18001a069  jnz     short loc_18001A07C
0x18001a06b  movzx   ecx, cx
0x18001a06e  mov     eax, ecx
0x18001a070  or      eax, 0C0070000h
0x18001a075  test    ecx, ecx
0x18001a077  cmovnz  ecx, eax
0x18001a07a  jmp     short loc_18001A0A9
0x18001a07c  cmp     eax, 90000h
0x18001a081  jnz     short loc_18001A09D
0x18001a083  test    ecx, ecx
0x18001a085  jle     short loc_18001A0A9
0x18001a087  movzx   ecx, cx
0x18001a08a  or      ecx, 0C0090000h
0x18001a090  jmp     short loc_18001A0A9
0x18001a092  xor     ecx, ecx
0x18001a094  jmp     short loc_18001A0A9
0x18001a096  mov     ecx, 0C000A083h
0x18001a09b  jmp     short loc_18001A0A9
0x18001a09d  mov     ecx, 0C00000E5h
0x18001a0a2  jmp     short loc_18001A0A9
0x18001a0a4  mov     ecx, 0C000042Bh
0x18001a0a9  mov     eax, ecx
0x18001a0ab  retn
```
