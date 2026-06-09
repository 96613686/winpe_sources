# wil::details::HrToNtStatus(long)

- ea: `0x18000cb7c`
- end: `0x18000cd38`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800085a0`
- `0x180008640`
- `0x180008690`
- `0x180008750`
- `0x18000b648`
- `0x18000dee8`

## callees

- `0x18000cb7c`

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
0x18000cb7c  mov     eax, 800700EAh
0x18000cb81  cmp     ecx, eax
0x18000cb83  jg      loc_18000CC58
0x18000cb89  jz      loc_18000CC4E
0x18000cb8f  mov     eax, 80070057h
0x18000cb94  cmp     ecx, eax
0x18000cb96  jg      short loc_18000CC02
0x18000cb98  jz      short loc_18000CBF8
0x18000cb9a  cmp     ecx, 80004005h
0x18000cba0  jz      short loc_18000CBEE
0x18000cba2  cmp     ecx, 80070001h
0x18000cba8  jz      short loc_18000CBE4
0x18000cbaa  cmp     ecx, 80070002h
0x18000cbb0  jz      short loc_18000CBDA
0x18000cbb2  cmp     ecx, 80070003h
0x18000cbb8  jz      short loc_18000CBD0
0x18000cbba  cmp     ecx, 8007000Eh
0x18000cbc0  jnz     loc_18000CCDD
0x18000cbc6  mov     ecx, 0C0000017h
0x18000cbcb  jmp     loc_18000CD35
0x18000cbd0  mov     ecx, 0C000003Ah
0x18000cbd5  jmp     loc_18000CD35
0x18000cbda  mov     ecx, 0C0000034h
0x18000cbdf  jmp     loc_18000CD35
0x18000cbe4  mov     ecx, 0C0000002h
0x18000cbe9  jmp     loc_18000CD35
0x18000cbee  mov     ecx, 0C0000001h
0x18000cbf3  jmp     loc_18000CD35
0x18000cbf8  mov     ecx, 0C000000Dh
0x18000cbfd  jmp     loc_18000CD35
0x18000cc02  cmp     ecx, 80070070h
0x18000cc08  jz      short loc_18000CC44
0x18000cc0a  cmp     ecx, 8007007Ah
0x18000cc10  jz      short loc_18000CC3A
0x18000cc12  cmp     ecx, 8007007Bh
0x18000cc18  jz      short loc_18000CC30
0x18000cc1a  cmp     ecx, 8007007Eh
0x18000cc20  jnz     loc_18000CCDD
0x18000cc26  mov     ecx, 0C0000135h
0x18000cc2b  jmp     loc_18000CD35
0x18000cc30  mov     ecx, 0C0000033h
0x18000cc35  jmp     loc_18000CD35
0x18000cc3a  mov     ecx, 0C0000023h
0x18000cc3f  jmp     loc_18000CD35
0x18000cc44  mov     ecx, 0C000007Fh
0x18000cc49  jmp     loc_18000CD35
0x18000cc4e  mov     ecx, 80000005h
0x18000cc53  jmp     loc_18000CD35
0x18000cc58  mov     eax, 8007047Eh
0x18000cc5d  cmp     ecx, eax
0x18000cc5f  jg      short loc_18000CCC1
0x18000cc61  jz      short loc_18000CCBA
0x18000cc63  cmp     ecx, 80070216h
0x18000cc69  jz      short loc_18000CCB3
0x18000cc6b  cmp     ecx, 8007023Eh
0x18000cc71  jz      short loc_18000CCA9
0x18000cc73  cmp     ecx, 80070246h
0x18000cc79  jz      short loc_18000CC9F
0x18000cc7b  cmp     ecx, 80070247h
0x18000cc81  jz      short loc_18000CC95
0x18000cc83  cmp     ecx, 80070272h
0x18000cc89  jnz     short loc_18000CCDD
0x18000cc8b  mov     ecx, 0C0000273h
0x18000cc90  jmp     loc_18000CD35
0x18000cc95  mov     ecx, 0C0000163h
0x18000cc9a  jmp     loc_18000CD35
0x18000cc9f  mov     ecx, 0C0000161h
0x18000cca4  jmp     loc_18000CD35
0x18000cca9  mov     ecx, 0C0000025h
0x18000ccae  jmp     loc_18000CD35
0x18000ccb3  mov     ecx, 0C0000095h
0x18000ccb8  jmp     short loc_18000CD35
0x18000ccba  mov     ecx, 0C0000059h
0x18000ccbf  jmp     short loc_18000CD35
0x18000ccc1  cmp     ecx, 8007050Ch
0x18000ccc7  jz      short loc_18000CD30
0x18000ccc9  cmp     ecx, 8007054Fh
0x18000cccf  jz      short loc_18000CD29
0x18000ccd1  cmp     ecx, 800705B9h
0x18000ccd7  jz      short loc_18000CD22
0x18000ccd9  test    ecx, ecx
0x18000ccdb  jz      short loc_18000CD1E
0x18000ccdd  bt      ecx, 1Ch
0x18000cce1  jnb     short loc_18000CCE9
0x18000cce3  btr     ecx, 1Ch
0x18000cce7  jmp     short loc_18000CD35
0x18000cce9  mov     eax, ecx
0x18000cceb  and     eax, 1FFF0000h
0x18000ccf0  cmp     eax, 70000h
0x18000ccf5  jnz     short loc_18000CD08
0x18000ccf7  movzx   ecx, cx
0x18000ccfa  mov     eax, ecx
0x18000ccfc  or      eax, 0C0070000h
0x18000cd01  test    ecx, ecx
0x18000cd03  cmovnz  ecx, eax
0x18000cd06  jmp     short loc_18000CD35
0x18000cd08  cmp     eax, 90000h
0x18000cd0d  jnz     short loc_18000CD29
0x18000cd0f  test    ecx, ecx
0x18000cd11  jle     short loc_18000CD35
0x18000cd13  movzx   ecx, cx
0x18000cd16  or      ecx, 0C0090000h
0x18000cd1c  jmp     short loc_18000CD35
0x18000cd1e  xor     ecx, ecx
0x18000cd20  jmp     short loc_18000CD35
0x18000cd22  mov     ecx, 0C000A083h
0x18000cd27  jmp     short loc_18000CD35
0x18000cd29  mov     ecx, 0C00000E5h
0x18000cd2e  jmp     short loc_18000CD35
0x18000cd30  mov     ecx, 0C000042Bh
0x18000cd35  mov     eax, ecx
0x18000cd37  retn
```
