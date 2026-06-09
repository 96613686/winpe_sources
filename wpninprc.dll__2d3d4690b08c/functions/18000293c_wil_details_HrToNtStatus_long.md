# wil::details::HrToNtStatus(long)

- ea: `0x18000293c`
- end: `0x180002af8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024d8`
- `0x180003818`
- `0x1800038b8`
- `0x180003908`
- `0x1800039c0`
- `0x180004d2c`

## callees

- `0x18000293c`

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
0x18000293c  mov     eax, 800700EAh
0x180002941  cmp     ecx, eax
0x180002943  jg      loc_180002A18
0x180002949  jz      loc_180002A0E
0x18000294f  mov     eax, 80070057h
0x180002954  cmp     ecx, eax
0x180002956  jg      short loc_1800029C2
0x180002958  jz      short loc_1800029B8
0x18000295a  cmp     ecx, 80004005h
0x180002960  jz      short loc_1800029AE
0x180002962  cmp     ecx, 80070001h
0x180002968  jz      short loc_1800029A4
0x18000296a  cmp     ecx, 80070002h
0x180002970  jz      short loc_18000299A
0x180002972  cmp     ecx, 80070003h
0x180002978  jz      short loc_180002990
0x18000297a  cmp     ecx, 8007000Eh
0x180002980  jnz     loc_180002A9D
0x180002986  mov     ecx, 0C0000017h
0x18000298b  jmp     loc_180002AF5
0x180002990  mov     ecx, 0C000003Ah
0x180002995  jmp     loc_180002AF5
0x18000299a  mov     ecx, 0C0000034h
0x18000299f  jmp     loc_180002AF5
0x1800029a4  mov     ecx, 0C0000002h
0x1800029a9  jmp     loc_180002AF5
0x1800029ae  mov     ecx, 0C0000001h
0x1800029b3  jmp     loc_180002AF5
0x1800029b8  mov     ecx, 0C000000Dh
0x1800029bd  jmp     loc_180002AF5
0x1800029c2  cmp     ecx, 80070070h
0x1800029c8  jz      short loc_180002A04
0x1800029ca  cmp     ecx, 8007007Ah
0x1800029d0  jz      short loc_1800029FA
0x1800029d2  cmp     ecx, 8007007Bh
0x1800029d8  jz      short loc_1800029F0
0x1800029da  cmp     ecx, 8007007Eh
0x1800029e0  jnz     loc_180002A9D
0x1800029e6  mov     ecx, 0C0000135h
0x1800029eb  jmp     loc_180002AF5
0x1800029f0  mov     ecx, 0C0000033h
0x1800029f5  jmp     loc_180002AF5
0x1800029fa  mov     ecx, 0C0000023h
0x1800029ff  jmp     loc_180002AF5
0x180002a04  mov     ecx, 0C000007Fh
0x180002a09  jmp     loc_180002AF5
0x180002a0e  mov     ecx, 80000005h
0x180002a13  jmp     loc_180002AF5
0x180002a18  mov     eax, 8007047Eh
0x180002a1d  cmp     ecx, eax
0x180002a1f  jg      short loc_180002A81
0x180002a21  jz      short loc_180002A7A
0x180002a23  cmp     ecx, 80070216h
0x180002a29  jz      short loc_180002A73
0x180002a2b  cmp     ecx, 8007023Eh
0x180002a31  jz      short loc_180002A69
0x180002a33  cmp     ecx, 80070246h
0x180002a39  jz      short loc_180002A5F
0x180002a3b  cmp     ecx, 80070247h
0x180002a41  jz      short loc_180002A55
0x180002a43  cmp     ecx, 80070272h
0x180002a49  jnz     short loc_180002A9D
0x180002a4b  mov     ecx, 0C0000273h
0x180002a50  jmp     loc_180002AF5
0x180002a55  mov     ecx, 0C0000163h
0x180002a5a  jmp     loc_180002AF5
0x180002a5f  mov     ecx, 0C0000161h
0x180002a64  jmp     loc_180002AF5
0x180002a69  mov     ecx, 0C0000025h
0x180002a6e  jmp     loc_180002AF5
0x180002a73  mov     ecx, 0C0000095h
0x180002a78  jmp     short loc_180002AF5
0x180002a7a  mov     ecx, 0C0000059h
0x180002a7f  jmp     short loc_180002AF5
0x180002a81  cmp     ecx, 8007050Ch
0x180002a87  jz      short loc_180002AF0
0x180002a89  cmp     ecx, 8007054Fh
0x180002a8f  jz      short loc_180002AE9
0x180002a91  cmp     ecx, 800705B9h
0x180002a97  jz      short loc_180002AE2
0x180002a99  test    ecx, ecx
0x180002a9b  jz      short loc_180002ADE
0x180002a9d  bt      ecx, 1Ch
0x180002aa1  jnb     short loc_180002AA9
0x180002aa3  btr     ecx, 1Ch
0x180002aa7  jmp     short loc_180002AF5
0x180002aa9  mov     eax, ecx
0x180002aab  and     eax, 1FFF0000h
0x180002ab0  cmp     eax, 70000h
0x180002ab5  jnz     short loc_180002AC8
0x180002ab7  movzx   ecx, cx
0x180002aba  mov     eax, ecx
0x180002abc  or      eax, 0C0070000h
0x180002ac1  test    ecx, ecx
0x180002ac3  cmovnz  ecx, eax
0x180002ac6  jmp     short loc_180002AF5
0x180002ac8  cmp     eax, 90000h
0x180002acd  jnz     short loc_180002AE9
0x180002acf  test    ecx, ecx
0x180002ad1  jle     short loc_180002AF5
0x180002ad3  movzx   ecx, cx
0x180002ad6  or      ecx, 0C0090000h
0x180002adc  jmp     short loc_180002AF5
0x180002ade  xor     ecx, ecx
0x180002ae0  jmp     short loc_180002AF5
0x180002ae2  mov     ecx, 0C000A083h
0x180002ae7  jmp     short loc_180002AF5
0x180002ae9  mov     ecx, 0C00000E5h
0x180002aee  jmp     short loc_180002AF5
0x180002af0  mov     ecx, 0C000042Bh
0x180002af5  mov     eax, ecx
0x180002af7  retn
```
