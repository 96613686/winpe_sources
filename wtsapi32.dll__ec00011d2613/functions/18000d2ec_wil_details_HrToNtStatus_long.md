# wil::details::HrToNtStatus(long)

- ea: `0x18000d2ec`
- end: `0x18000d4a8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b5d0`
- `0x18000b640`
- `0x18000b6c0`
- `0x18000b710`
- `0x18000b774`
- `0x18000d590`

## callees

- `0x18000d2ec`

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
0x18000d2ec  mov     eax, 800700EAh
0x18000d2f1  cmp     ecx, eax
0x18000d2f3  jg      loc_18000D3C8
0x18000d2f9  jz      loc_18000D3BE
0x18000d2ff  mov     eax, 80070057h
0x18000d304  cmp     ecx, eax
0x18000d306  jg      short loc_18000D372
0x18000d308  jz      short loc_18000D368
0x18000d30a  cmp     ecx, 80004005h
0x18000d310  jz      short loc_18000D35E
0x18000d312  cmp     ecx, 80070001h
0x18000d318  jz      short loc_18000D354
0x18000d31a  cmp     ecx, 80070002h
0x18000d320  jz      short loc_18000D34A
0x18000d322  cmp     ecx, 80070003h
0x18000d328  jz      short loc_18000D340
0x18000d32a  cmp     ecx, 8007000Eh
0x18000d330  jnz     loc_18000D44D
0x18000d336  mov     ecx, 0C0000017h
0x18000d33b  jmp     loc_18000D4A5
0x18000d340  mov     ecx, 0C000003Ah
0x18000d345  jmp     loc_18000D4A5
0x18000d34a  mov     ecx, 0C0000034h
0x18000d34f  jmp     loc_18000D4A5
0x18000d354  mov     ecx, 0C0000002h
0x18000d359  jmp     loc_18000D4A5
0x18000d35e  mov     ecx, 0C0000001h
0x18000d363  jmp     loc_18000D4A5
0x18000d368  mov     ecx, 0C000000Dh
0x18000d36d  jmp     loc_18000D4A5
0x18000d372  cmp     ecx, 80070070h
0x18000d378  jz      short loc_18000D3B4
0x18000d37a  cmp     ecx, 8007007Ah
0x18000d380  jz      short loc_18000D3AA
0x18000d382  cmp     ecx, 8007007Bh
0x18000d388  jz      short loc_18000D3A0
0x18000d38a  cmp     ecx, 8007007Eh
0x18000d390  jnz     loc_18000D44D
0x18000d396  mov     ecx, 0C0000135h
0x18000d39b  jmp     loc_18000D4A5
0x18000d3a0  mov     ecx, 0C0000033h
0x18000d3a5  jmp     loc_18000D4A5
0x18000d3aa  mov     ecx, 0C0000023h
0x18000d3af  jmp     loc_18000D4A5
0x18000d3b4  mov     ecx, 0C000007Fh
0x18000d3b9  jmp     loc_18000D4A5
0x18000d3be  mov     ecx, 80000005h
0x18000d3c3  jmp     loc_18000D4A5
0x18000d3c8  mov     eax, 8007047Eh
0x18000d3cd  cmp     ecx, eax
0x18000d3cf  jg      short loc_18000D431
0x18000d3d1  jz      short loc_18000D42A
0x18000d3d3  cmp     ecx, 80070216h
0x18000d3d9  jz      short loc_18000D423
0x18000d3db  cmp     ecx, 8007023Eh
0x18000d3e1  jz      short loc_18000D419
0x18000d3e3  cmp     ecx, 80070246h
0x18000d3e9  jz      short loc_18000D40F
0x18000d3eb  cmp     ecx, 80070247h
0x18000d3f1  jz      short loc_18000D405
0x18000d3f3  cmp     ecx, 80070272h
0x18000d3f9  jnz     short loc_18000D44D
0x18000d3fb  mov     ecx, 0C0000273h
0x18000d400  jmp     loc_18000D4A5
0x18000d405  mov     ecx, 0C0000163h
0x18000d40a  jmp     loc_18000D4A5
0x18000d40f  mov     ecx, 0C0000161h
0x18000d414  jmp     loc_18000D4A5
0x18000d419  mov     ecx, 0C0000025h
0x18000d41e  jmp     loc_18000D4A5
0x18000d423  mov     ecx, 0C0000095h
0x18000d428  jmp     short loc_18000D4A5
0x18000d42a  mov     ecx, 0C0000059h
0x18000d42f  jmp     short loc_18000D4A5
0x18000d431  cmp     ecx, 8007050Ch
0x18000d437  jz      short loc_18000D4A0
0x18000d439  cmp     ecx, 8007054Fh
0x18000d43f  jz      short loc_18000D499
0x18000d441  cmp     ecx, 800705B9h
0x18000d447  jz      short loc_18000D492
0x18000d449  test    ecx, ecx
0x18000d44b  jz      short loc_18000D48E
0x18000d44d  bt      ecx, 1Ch
0x18000d451  jnb     short loc_18000D459
0x18000d453  btr     ecx, 1Ch
0x18000d457  jmp     short loc_18000D4A5
0x18000d459  mov     eax, ecx
0x18000d45b  and     eax, 1FFF0000h
0x18000d460  cmp     eax, 70000h
0x18000d465  jnz     short loc_18000D478
0x18000d467  movzx   ecx, cx
0x18000d46a  mov     eax, ecx
0x18000d46c  or      eax, 0C0070000h
0x18000d471  test    ecx, ecx
0x18000d473  cmovnz  ecx, eax
0x18000d476  jmp     short loc_18000D4A5
0x18000d478  cmp     eax, 90000h
0x18000d47d  jnz     short loc_18000D499
0x18000d47f  test    ecx, ecx
0x18000d481  jle     short loc_18000D4A5
0x18000d483  movzx   ecx, cx
0x18000d486  or      ecx, 0C0090000h
0x18000d48c  jmp     short loc_18000D4A5
0x18000d48e  xor     ecx, ecx
0x18000d490  jmp     short loc_18000D4A5
0x18000d492  mov     ecx, 0C000A083h
0x18000d497  jmp     short loc_18000D4A5
0x18000d499  mov     ecx, 0C00000E5h
0x18000d49e  jmp     short loc_18000D4A5
0x18000d4a0  mov     ecx, 0C000042Bh
0x18000d4a5  mov     eax, ecx
0x18000d4a7  retn
```
