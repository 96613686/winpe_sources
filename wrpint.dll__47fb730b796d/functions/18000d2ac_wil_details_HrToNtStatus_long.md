# wil::details::HrToNtStatus(long)

- ea: `0x18000d2ac`
- end: `0x18000d468`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a87c`
- `0x18000a924`
- `0x18000a974`
- `0x18000aa34`
- `0x18000b058`
- `0x18000c868`
- `0x18000d470`

## callees

- `0x18000d2ac`

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
0x18000d2ac  mov     eax, 800700EAh
0x18000d2b1  cmp     ecx, eax
0x18000d2b3  jg      loc_18000D388
0x18000d2b9  jz      loc_18000D37E
0x18000d2bf  mov     eax, 80070057h
0x18000d2c4  cmp     ecx, eax
0x18000d2c6  jg      short loc_18000D332
0x18000d2c8  jz      short loc_18000D328
0x18000d2ca  cmp     ecx, 80004005h
0x18000d2d0  jz      short loc_18000D31E
0x18000d2d2  cmp     ecx, 80070001h
0x18000d2d8  jz      short loc_18000D314
0x18000d2da  cmp     ecx, 80070002h
0x18000d2e0  jz      short loc_18000D30A
0x18000d2e2  cmp     ecx, 80070003h
0x18000d2e8  jz      short loc_18000D300
0x18000d2ea  cmp     ecx, 8007000Eh
0x18000d2f0  jnz     loc_18000D40D
0x18000d2f6  mov     ecx, 0C0000017h
0x18000d2fb  jmp     loc_18000D465
0x18000d300  mov     ecx, 0C000003Ah
0x18000d305  jmp     loc_18000D465
0x18000d30a  mov     ecx, 0C0000034h
0x18000d30f  jmp     loc_18000D465
0x18000d314  mov     ecx, 0C0000002h
0x18000d319  jmp     loc_18000D465
0x18000d31e  mov     ecx, 0C0000001h
0x18000d323  jmp     loc_18000D465
0x18000d328  mov     ecx, 0C000000Dh
0x18000d32d  jmp     loc_18000D465
0x18000d332  cmp     ecx, 80070070h
0x18000d338  jz      short loc_18000D374
0x18000d33a  cmp     ecx, 8007007Ah
0x18000d340  jz      short loc_18000D36A
0x18000d342  cmp     ecx, 8007007Bh
0x18000d348  jz      short loc_18000D360
0x18000d34a  cmp     ecx, 8007007Eh
0x18000d350  jnz     loc_18000D40D
0x18000d356  mov     ecx, 0C0000135h
0x18000d35b  jmp     loc_18000D465
0x18000d360  mov     ecx, 0C0000033h
0x18000d365  jmp     loc_18000D465
0x18000d36a  mov     ecx, 0C0000023h
0x18000d36f  jmp     loc_18000D465
0x18000d374  mov     ecx, 0C000007Fh
0x18000d379  jmp     loc_18000D465
0x18000d37e  mov     ecx, 80000005h
0x18000d383  jmp     loc_18000D465
0x18000d388  mov     eax, 8007047Eh
0x18000d38d  cmp     ecx, eax
0x18000d38f  jg      short loc_18000D3F1
0x18000d391  jz      short loc_18000D3EA
0x18000d393  cmp     ecx, 80070216h
0x18000d399  jz      short loc_18000D3E3
0x18000d39b  cmp     ecx, 8007023Eh
0x18000d3a1  jz      short loc_18000D3D9
0x18000d3a3  cmp     ecx, 80070246h
0x18000d3a9  jz      short loc_18000D3CF
0x18000d3ab  cmp     ecx, 80070247h
0x18000d3b1  jz      short loc_18000D3C5
0x18000d3b3  cmp     ecx, 80070272h
0x18000d3b9  jnz     short loc_18000D40D
0x18000d3bb  mov     ecx, 0C0000273h
0x18000d3c0  jmp     loc_18000D465
0x18000d3c5  mov     ecx, 0C0000163h
0x18000d3ca  jmp     loc_18000D465
0x18000d3cf  mov     ecx, 0C0000161h
0x18000d3d4  jmp     loc_18000D465
0x18000d3d9  mov     ecx, 0C0000025h
0x18000d3de  jmp     loc_18000D465
0x18000d3e3  mov     ecx, 0C0000095h
0x18000d3e8  jmp     short loc_18000D465
0x18000d3ea  mov     ecx, 0C0000059h
0x18000d3ef  jmp     short loc_18000D465
0x18000d3f1  cmp     ecx, 8007050Ch
0x18000d3f7  jz      short loc_18000D460
0x18000d3f9  cmp     ecx, 8007054Fh
0x18000d3ff  jz      short loc_18000D459
0x18000d401  cmp     ecx, 800705B9h
0x18000d407  jz      short loc_18000D452
0x18000d409  test    ecx, ecx
0x18000d40b  jz      short loc_18000D44E
0x18000d40d  bt      ecx, 1Ch
0x18000d411  jnb     short loc_18000D419
0x18000d413  btr     ecx, 1Ch
0x18000d417  jmp     short loc_18000D465
0x18000d419  mov     eax, ecx
0x18000d41b  and     eax, 1FFF0000h
0x18000d420  cmp     eax, 70000h
0x18000d425  jnz     short loc_18000D438
0x18000d427  movzx   ecx, cx
0x18000d42a  mov     eax, ecx
0x18000d42c  or      eax, 0C0070000h
0x18000d431  test    ecx, ecx
0x18000d433  cmovnz  ecx, eax
0x18000d436  jmp     short loc_18000D465
0x18000d438  cmp     eax, 90000h
0x18000d43d  jnz     short loc_18000D459
0x18000d43f  test    ecx, ecx
0x18000d441  jle     short loc_18000D465
0x18000d443  movzx   ecx, cx
0x18000d446  or      ecx, 0C0090000h
0x18000d44c  jmp     short loc_18000D465
0x18000d44e  xor     ecx, ecx
0x18000d450  jmp     short loc_18000D465
0x18000d452  mov     ecx, 0C000A083h
0x18000d457  jmp     short loc_18000D465
0x18000d459  mov     ecx, 0C00000E5h
0x18000d45e  jmp     short loc_18000D465
0x18000d460  mov     ecx, 0C000042Bh
0x18000d465  mov     eax, ecx
0x18000d467  retn
```
