# wil::details::HrToNtStatus(long)

- ea: `0x180006bdc`
- end: `0x180006da5`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `457`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002980`
- `0x180002a38`
- `0x180002a8c`
- `0x180002b48`
- `0x1800060f4`
- `0x18000796c`

## callees

- `0x180006bdc`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // edx

  v1 = (unsigned int)this;
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          return (unsigned int)-1073740757;
        case 0x8007054F:
          return (unsigned int)-1073741595;
        case 0x800705B9:
          return (unsigned int)-1073700733;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          return (unsigned int)-1073741735;
        case 0x80070216:
          return (unsigned int)-1073741675;
        case 0x8007023E:
          return (unsigned int)-1073741787;
        case 0x80070246:
          return (unsigned int)-1073741471;
        case 0x80070247:
          return (unsigned int)-1073741469;
        case 0x80070272:
          return (unsigned int)-1073741197;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
      return (unsigned int)-2147483643;
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          return (unsigned int)-1073741697;
        case 0x8007007A:
          return (unsigned int)-1073741789;
        case 0x8007007B:
          return (unsigned int)-1073741773;
        case 0x8007007E:
          return (unsigned int)-1073741515;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          return (unsigned int)-1073741811;
        case 0x80004005:
          return (unsigned int)-1073741823;
        case 0x80070001:
          return (unsigned int)-1073741822;
        case 0x80070002:
          return (unsigned int)-1073741772;
        case 0x80070003:
          return (unsigned int)-1073741766;
        case 0x8007000E:
          return (unsigned int)-1073741801;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
    return (unsigned int)this & 0xEFFFFFFF;
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    v1 = (unsigned __int16)this;
    if ( (_WORD)this )
      return (unsigned __int16)this | 0xC0070000;
    return v1;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
    return (unsigned int)-1073741595;
  if ( (int)this > 0 )
    return (unsigned __int16)this | 0xC0090000;
  return v1;
}

```

## disassembly

```asm
0x180006bdc  mov     eax, 800700EAh
0x180006be1  mov     edx, ecx
0x180006be3  cmp     ecx, eax
0x180006be5  jg      loc_180006CBA
0x180006beb  jz      loc_180006CB0
0x180006bf1  mov     eax, 80070057h
0x180006bf6  cmp     ecx, eax
0x180006bf8  jg      short loc_180006C64
0x180006bfa  jz      short loc_180006C5A
0x180006bfc  cmp     ecx, 80004005h
0x180006c02  jz      short loc_180006C50
0x180006c04  cmp     ecx, 80070001h
0x180006c0a  jz      short loc_180006C46
0x180006c0c  cmp     ecx, 80070002h
0x180006c12  jz      short loc_180006C3C
0x180006c14  cmp     ecx, 80070003h
0x180006c1a  jz      short loc_180006C32
0x180006c1c  cmp     ecx, 8007000Eh
0x180006c22  jnz     loc_180006D42
0x180006c28  mov     edx, 0C0000017h
0x180006c2d  jmp     loc_180006DA2
0x180006c32  mov     edx, 0C000003Ah
0x180006c37  jmp     loc_180006DA2
0x180006c3c  mov     edx, 0C0000034h
0x180006c41  jmp     loc_180006DA2
0x180006c46  mov     edx, 0C0000002h
0x180006c4b  jmp     loc_180006DA2
0x180006c50  mov     edx, 0C0000001h
0x180006c55  jmp     loc_180006DA2
0x180006c5a  mov     edx, 0C000000Dh
0x180006c5f  jmp     loc_180006DA2
0x180006c64  cmp     edx, 80070070h
0x180006c6a  jz      short loc_180006CA6
0x180006c6c  cmp     edx, 8007007Ah
0x180006c72  jz      short loc_180006C9C
0x180006c74  cmp     edx, 8007007Bh
0x180006c7a  jz      short loc_180006C92
0x180006c7c  cmp     edx, 8007007Eh
0x180006c82  jnz     loc_180006D42
0x180006c88  mov     edx, 0C0000135h
0x180006c8d  jmp     loc_180006DA2
0x180006c92  mov     edx, 0C0000033h
0x180006c97  jmp     loc_180006DA2
0x180006c9c  mov     edx, 0C0000023h
0x180006ca1  jmp     loc_180006DA2
0x180006ca6  mov     edx, 0C000007Fh
0x180006cab  jmp     loc_180006DA2
0x180006cb0  mov     edx, 80000005h
0x180006cb5  jmp     loc_180006DA2
0x180006cba  mov     eax, 8007047Eh
0x180006cbf  cmp     edx, eax
0x180006cc1  jg      short loc_180006D26
0x180006cc3  jz      short loc_180006D1F
0x180006cc5  cmp     edx, 80070216h
0x180006ccb  jz      short loc_180006D15
0x180006ccd  cmp     edx, 8007023Eh
0x180006cd3  jz      short loc_180006D0B
0x180006cd5  cmp     edx, 80070246h
0x180006cdb  jz      short loc_180006D01
0x180006cdd  cmp     edx, 80070247h
0x180006ce3  jz      short loc_180006CF7
0x180006ce5  cmp     edx, 80070272h
0x180006ceb  jnz     short loc_180006D42
0x180006ced  mov     edx, 0C0000273h
0x180006cf2  jmp     loc_180006DA2
0x180006cf7  mov     edx, 0C0000163h
0x180006cfc  jmp     loc_180006DA2
0x180006d01  mov     edx, 0C0000161h
0x180006d06  jmp     loc_180006DA2
0x180006d0b  mov     edx, 0C0000025h
0x180006d10  jmp     loc_180006DA2
0x180006d15  mov     edx, 0C0000095h
0x180006d1a  jmp     loc_180006DA2
0x180006d1f  mov     edx, 0C0000059h
0x180006d24  jmp     short loc_180006DA2
0x180006d26  cmp     edx, 8007050Ch
0x180006d2c  jz      short loc_180006D9D
0x180006d2e  cmp     edx, 8007054Fh
0x180006d34  jz      short loc_180006D96
0x180006d36  cmp     edx, 800705B9h
0x180006d3c  jz      short loc_180006D8F
0x180006d3e  test    edx, edx
0x180006d40  jz      short loc_180006D8B
0x180006d42  bt      edx, 1Ch
0x180006d46  jnb     short loc_180006D4E
0x180006d48  btr     edx, 1Ch
0x180006d4c  jmp     short loc_180006DA2
0x180006d4e  mov     eax, edx
0x180006d50  mov     ecx, 1FFF0000h
0x180006d55  and     eax, ecx
0x180006d57  cmp     eax, 70000h
0x180006d5c  jnz     short loc_180006D71
0x180006d5e  movzx   ecx, dx
0x180006d61  mov     eax, ecx
0x180006d63  mov     edx, ecx
0x180006d65  or      eax, 0C0070000h
0x180006d6a  test    ecx, ecx
0x180006d6c  cmovnz  edx, eax
0x180006d6f  jmp     short loc_180006DA2
0x180006d71  mov     eax, edx
0x180006d73  and     eax, ecx
0x180006d75  cmp     eax, 90000h
0x180006d7a  jnz     short loc_180006D96
0x180006d7c  test    edx, edx
0x180006d7e  jle     short loc_180006DA2
0x180006d80  movzx   edx, dx
0x180006d83  or      edx, 0C0090000h
0x180006d89  jmp     short loc_180006DA2
0x180006d8b  xor     edx, edx
0x180006d8d  jmp     short loc_180006DA2
0x180006d8f  mov     edx, 0C000A083h
0x180006d94  jmp     short loc_180006DA2
0x180006d96  mov     edx, 0C00000E5h
0x180006d9b  jmp     short loc_180006DA2
0x180006d9d  mov     edx, 0C000042Bh
0x180006da2  mov     eax, edx
0x180006da4  retn
```
