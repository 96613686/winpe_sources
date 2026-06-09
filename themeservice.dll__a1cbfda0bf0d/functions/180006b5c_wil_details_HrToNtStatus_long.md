# wil::details::HrToNtStatus(long)

- ea: `0x180006b5c`
- end: `0x180006d18`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ad8`
- `0x180008168`
- `0x1800081e0`
- `0x180008230`
- `0x180008294`
- `0x180009398`

## callees

- `0x180006b5c`

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
0x180006b5c  mov     eax, 800700EAh
0x180006b61  cmp     ecx, eax
0x180006b63  jg      loc_180006C38
0x180006b69  jz      loc_180006C2E
0x180006b6f  mov     eax, 80070057h
0x180006b74  cmp     ecx, eax
0x180006b76  jg      short loc_180006BE2
0x180006b78  jz      short loc_180006BD8
0x180006b7a  cmp     ecx, 80004005h
0x180006b80  jz      short loc_180006BCE
0x180006b82  cmp     ecx, 80070001h
0x180006b88  jz      short loc_180006BC4
0x180006b8a  cmp     ecx, 80070002h
0x180006b90  jz      short loc_180006BBA
0x180006b92  cmp     ecx, 80070003h
0x180006b98  jz      short loc_180006BB0
0x180006b9a  cmp     ecx, 8007000Eh
0x180006ba0  jnz     loc_180006CBD
0x180006ba6  mov     ecx, 0C0000017h
0x180006bab  jmp     loc_180006D15
0x180006bb0  mov     ecx, 0C000003Ah
0x180006bb5  jmp     loc_180006D15
0x180006bba  mov     ecx, 0C0000034h
0x180006bbf  jmp     loc_180006D15
0x180006bc4  mov     ecx, 0C0000002h
0x180006bc9  jmp     loc_180006D15
0x180006bce  mov     ecx, 0C0000001h
0x180006bd3  jmp     loc_180006D15
0x180006bd8  mov     ecx, 0C000000Dh
0x180006bdd  jmp     loc_180006D15
0x180006be2  cmp     ecx, 80070070h
0x180006be8  jz      short loc_180006C24
0x180006bea  cmp     ecx, 8007007Ah
0x180006bf0  jz      short loc_180006C1A
0x180006bf2  cmp     ecx, 8007007Bh
0x180006bf8  jz      short loc_180006C10
0x180006bfa  cmp     ecx, 8007007Eh
0x180006c00  jnz     loc_180006CBD
0x180006c06  mov     ecx, 0C0000135h
0x180006c0b  jmp     loc_180006D15
0x180006c10  mov     ecx, 0C0000033h
0x180006c15  jmp     loc_180006D15
0x180006c1a  mov     ecx, 0C0000023h
0x180006c1f  jmp     loc_180006D15
0x180006c24  mov     ecx, 0C000007Fh
0x180006c29  jmp     loc_180006D15
0x180006c2e  mov     ecx, 80000005h
0x180006c33  jmp     loc_180006D15
0x180006c38  mov     eax, 8007047Eh
0x180006c3d  cmp     ecx, eax
0x180006c3f  jg      short loc_180006CA1
0x180006c41  jz      short loc_180006C9A
0x180006c43  cmp     ecx, 80070216h
0x180006c49  jz      short loc_180006C93
0x180006c4b  cmp     ecx, 8007023Eh
0x180006c51  jz      short loc_180006C89
0x180006c53  cmp     ecx, 80070246h
0x180006c59  jz      short loc_180006C7F
0x180006c5b  cmp     ecx, 80070247h
0x180006c61  jz      short loc_180006C75
0x180006c63  cmp     ecx, 80070272h
0x180006c69  jnz     short loc_180006CBD
0x180006c6b  mov     ecx, 0C0000273h
0x180006c70  jmp     loc_180006D15
0x180006c75  mov     ecx, 0C0000163h
0x180006c7a  jmp     loc_180006D15
0x180006c7f  mov     ecx, 0C0000161h
0x180006c84  jmp     loc_180006D15
0x180006c89  mov     ecx, 0C0000025h
0x180006c8e  jmp     loc_180006D15
0x180006c93  mov     ecx, 0C0000095h
0x180006c98  jmp     short loc_180006D15
0x180006c9a  mov     ecx, 0C0000059h
0x180006c9f  jmp     short loc_180006D15
0x180006ca1  cmp     ecx, 8007050Ch
0x180006ca7  jz      short loc_180006D10
0x180006ca9  cmp     ecx, 8007054Fh
0x180006caf  jz      short loc_180006D09
0x180006cb1  cmp     ecx, 800705B9h
0x180006cb7  jz      short loc_180006D02
0x180006cb9  test    ecx, ecx
0x180006cbb  jz      short loc_180006CFE
0x180006cbd  bt      ecx, 1Ch
0x180006cc1  jnb     short loc_180006CC9
0x180006cc3  btr     ecx, 1Ch
0x180006cc7  jmp     short loc_180006D15
0x180006cc9  mov     eax, ecx
0x180006ccb  and     eax, 1FFF0000h
0x180006cd0  cmp     eax, 70000h
0x180006cd5  jnz     short loc_180006CE8
0x180006cd7  movzx   ecx, cx
0x180006cda  mov     eax, ecx
0x180006cdc  or      eax, 0C0070000h
0x180006ce1  test    ecx, ecx
0x180006ce3  cmovnz  ecx, eax
0x180006ce6  jmp     short loc_180006D15
0x180006ce8  cmp     eax, 90000h
0x180006ced  jnz     short loc_180006D09
0x180006cef  test    ecx, ecx
0x180006cf1  jle     short loc_180006D15
0x180006cf3  movzx   ecx, cx
0x180006cf6  or      ecx, 0C0090000h
0x180006cfc  jmp     short loc_180006D15
0x180006cfe  xor     ecx, ecx
0x180006d00  jmp     short loc_180006D15
0x180006d02  mov     ecx, 0C000A083h
0x180006d07  jmp     short loc_180006D15
0x180006d09  mov     ecx, 0C00000E5h
0x180006d0e  jmp     short loc_180006D15
0x180006d10  mov     ecx, 0C000042Bh
0x180006d15  mov     eax, ecx
0x180006d17  retn
```
