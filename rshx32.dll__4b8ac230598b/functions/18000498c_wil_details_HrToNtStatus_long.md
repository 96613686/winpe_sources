# wil::details::HrToNtStatus(long)

- ea: `0x18000498c`
- end: `0x180004b48`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f00`
- `0x180002fa0`
- `0x180002ff0`
- `0x1800030b0`
- `0x180003f68`
- `0x180004b50`

## callees

- `0x18000498c`

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
0x18000498c  mov     eax, 800700EAh
0x180004991  cmp     ecx, eax
0x180004993  jg      loc_180004A68
0x180004999  jz      loc_180004A5E
0x18000499f  mov     eax, 80070057h
0x1800049a4  cmp     ecx, eax
0x1800049a6  jg      short loc_180004A12
0x1800049a8  jz      short loc_180004A08
0x1800049aa  cmp     ecx, 80004005h
0x1800049b0  jz      short loc_1800049FE
0x1800049b2  cmp     ecx, 80070001h
0x1800049b8  jz      short loc_1800049F4
0x1800049ba  cmp     ecx, 80070002h
0x1800049c0  jz      short loc_1800049EA
0x1800049c2  cmp     ecx, 80070003h
0x1800049c8  jz      short loc_1800049E0
0x1800049ca  cmp     ecx, 8007000Eh
0x1800049d0  jnz     loc_180004AED
0x1800049d6  mov     ecx, 0C0000017h
0x1800049db  jmp     loc_180004B45
0x1800049e0  mov     ecx, 0C000003Ah
0x1800049e5  jmp     loc_180004B45
0x1800049ea  mov     ecx, 0C0000034h
0x1800049ef  jmp     loc_180004B45
0x1800049f4  mov     ecx, 0C0000002h
0x1800049f9  jmp     loc_180004B45
0x1800049fe  mov     ecx, 0C0000001h
0x180004a03  jmp     loc_180004B45
0x180004a08  mov     ecx, 0C000000Dh
0x180004a0d  jmp     loc_180004B45
0x180004a12  cmp     ecx, 80070070h
0x180004a18  jz      short loc_180004A54
0x180004a1a  cmp     ecx, 8007007Ah
0x180004a20  jz      short loc_180004A4A
0x180004a22  cmp     ecx, 8007007Bh
0x180004a28  jz      short loc_180004A40
0x180004a2a  cmp     ecx, 8007007Eh
0x180004a30  jnz     loc_180004AED
0x180004a36  mov     ecx, 0C0000135h
0x180004a3b  jmp     loc_180004B45
0x180004a40  mov     ecx, 0C0000033h
0x180004a45  jmp     loc_180004B45
0x180004a4a  mov     ecx, 0C0000023h
0x180004a4f  jmp     loc_180004B45
0x180004a54  mov     ecx, 0C000007Fh
0x180004a59  jmp     loc_180004B45
0x180004a5e  mov     ecx, 80000005h
0x180004a63  jmp     loc_180004B45
0x180004a68  mov     eax, 8007047Eh
0x180004a6d  cmp     ecx, eax
0x180004a6f  jg      short loc_180004AD1
0x180004a71  jz      short loc_180004ACA
0x180004a73  cmp     ecx, 80070216h
0x180004a79  jz      short loc_180004AC3
0x180004a7b  cmp     ecx, 8007023Eh
0x180004a81  jz      short loc_180004AB9
0x180004a83  cmp     ecx, 80070246h
0x180004a89  jz      short loc_180004AAF
0x180004a8b  cmp     ecx, 80070247h
0x180004a91  jz      short loc_180004AA5
0x180004a93  cmp     ecx, 80070272h
0x180004a99  jnz     short loc_180004AED
0x180004a9b  mov     ecx, 0C0000273h
0x180004aa0  jmp     loc_180004B45
0x180004aa5  mov     ecx, 0C0000163h
0x180004aaa  jmp     loc_180004B45
0x180004aaf  mov     ecx, 0C0000161h
0x180004ab4  jmp     loc_180004B45
0x180004ab9  mov     ecx, 0C0000025h
0x180004abe  jmp     loc_180004B45
0x180004ac3  mov     ecx, 0C0000095h
0x180004ac8  jmp     short loc_180004B45
0x180004aca  mov     ecx, 0C0000059h
0x180004acf  jmp     short loc_180004B45
0x180004ad1  cmp     ecx, 8007050Ch
0x180004ad7  jz      short loc_180004B40
0x180004ad9  cmp     ecx, 8007054Fh
0x180004adf  jz      short loc_180004B39
0x180004ae1  cmp     ecx, 800705B9h
0x180004ae7  jz      short loc_180004B32
0x180004ae9  test    ecx, ecx
0x180004aeb  jz      short loc_180004B2E
0x180004aed  bt      ecx, 1Ch
0x180004af1  jnb     short loc_180004AF9
0x180004af3  btr     ecx, 1Ch
0x180004af7  jmp     short loc_180004B45
0x180004af9  mov     eax, ecx
0x180004afb  and     eax, 1FFF0000h
0x180004b00  cmp     eax, 70000h
0x180004b05  jnz     short loc_180004B18
0x180004b07  movzx   ecx, cx
0x180004b0a  mov     eax, ecx
0x180004b0c  or      eax, 0C0070000h
0x180004b11  test    ecx, ecx
0x180004b13  cmovnz  ecx, eax
0x180004b16  jmp     short loc_180004B45
0x180004b18  cmp     eax, 90000h
0x180004b1d  jnz     short loc_180004B39
0x180004b1f  test    ecx, ecx
0x180004b21  jle     short loc_180004B45
0x180004b23  movzx   ecx, cx
0x180004b26  or      ecx, 0C0090000h
0x180004b2c  jmp     short loc_180004B45
0x180004b2e  xor     ecx, ecx
0x180004b30  jmp     short loc_180004B45
0x180004b32  mov     ecx, 0C000A083h
0x180004b37  jmp     short loc_180004B45
0x180004b39  mov     ecx, 0C00000E5h
0x180004b3e  jmp     short loc_180004B45
0x180004b40  mov     ecx, 0C000042Bh
0x180004b45  mov     eax, ecx
0x180004b47  retn
```
