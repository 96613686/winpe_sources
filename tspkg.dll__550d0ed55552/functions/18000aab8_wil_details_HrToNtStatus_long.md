# wil::details::HrToNtStatus(long)

- ea: `0x18000aab8`
- end: `0x18000ac74`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa34`
- `0x18000cb9c`
- `0x18000cc14`
- `0x18000cc64`
- `0x18000df18`
- `0x18000e9b8`

## callees

- `0x18000aab8`

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
0x18000aab8  mov     eax, 800700EAh
0x18000aabd  cmp     ecx, eax
0x18000aabf  jg      loc_18000AB94
0x18000aac5  jz      loc_18000AB8A
0x18000aacb  mov     eax, 80070057h
0x18000aad0  cmp     ecx, eax
0x18000aad2  jg      short loc_18000AB3E
0x18000aad4  jz      short loc_18000AB34
0x18000aad6  cmp     ecx, 80004005h
0x18000aadc  jz      short loc_18000AB2A
0x18000aade  cmp     ecx, 80070001h
0x18000aae4  jz      short loc_18000AB20
0x18000aae6  cmp     ecx, 80070002h
0x18000aaec  jz      short loc_18000AB16
0x18000aaee  cmp     ecx, 80070003h
0x18000aaf4  jz      short loc_18000AB0C
0x18000aaf6  cmp     ecx, 8007000Eh
0x18000aafc  jnz     loc_18000AC19
0x18000ab02  mov     ecx, 0C0000017h
0x18000ab07  jmp     loc_18000AC71
0x18000ab0c  mov     ecx, 0C000003Ah
0x18000ab11  jmp     loc_18000AC71
0x18000ab16  mov     ecx, 0C0000034h
0x18000ab1b  jmp     loc_18000AC71
0x18000ab20  mov     ecx, 0C0000002h
0x18000ab25  jmp     loc_18000AC71
0x18000ab2a  mov     ecx, 0C0000001h
0x18000ab2f  jmp     loc_18000AC71
0x18000ab34  mov     ecx, 0C000000Dh
0x18000ab39  jmp     loc_18000AC71
0x18000ab3e  cmp     ecx, 80070070h
0x18000ab44  jz      short loc_18000AB80
0x18000ab46  cmp     ecx, 8007007Ah
0x18000ab4c  jz      short loc_18000AB76
0x18000ab4e  cmp     ecx, 8007007Bh
0x18000ab54  jz      short loc_18000AB6C
0x18000ab56  cmp     ecx, 8007007Eh
0x18000ab5c  jnz     loc_18000AC19
0x18000ab62  mov     ecx, 0C0000135h
0x18000ab67  jmp     loc_18000AC71
0x18000ab6c  mov     ecx, 0C0000033h
0x18000ab71  jmp     loc_18000AC71
0x18000ab76  mov     ecx, 0C0000023h
0x18000ab7b  jmp     loc_18000AC71
0x18000ab80  mov     ecx, 0C000007Fh
0x18000ab85  jmp     loc_18000AC71
0x18000ab8a  mov     ecx, 80000005h
0x18000ab8f  jmp     loc_18000AC71
0x18000ab94  mov     eax, 8007047Eh
0x18000ab99  cmp     ecx, eax
0x18000ab9b  jg      short loc_18000ABFD
0x18000ab9d  jz      short loc_18000ABF6
0x18000ab9f  cmp     ecx, 80070216h
0x18000aba5  jz      short loc_18000ABEF
0x18000aba7  cmp     ecx, 8007023Eh
0x18000abad  jz      short loc_18000ABE5
0x18000abaf  cmp     ecx, 80070246h
0x18000abb5  jz      short loc_18000ABDB
0x18000abb7  cmp     ecx, 80070247h
0x18000abbd  jz      short loc_18000ABD1
0x18000abbf  cmp     ecx, 80070272h
0x18000abc5  jnz     short loc_18000AC19
0x18000abc7  mov     ecx, 0C0000273h
0x18000abcc  jmp     loc_18000AC71
0x18000abd1  mov     ecx, 0C0000163h
0x18000abd6  jmp     loc_18000AC71
0x18000abdb  mov     ecx, 0C0000161h
0x18000abe0  jmp     loc_18000AC71
0x18000abe5  mov     ecx, 0C0000025h
0x18000abea  jmp     loc_18000AC71
0x18000abef  mov     ecx, 0C0000095h
0x18000abf4  jmp     short loc_18000AC71
0x18000abf6  mov     ecx, 0C0000059h
0x18000abfb  jmp     short loc_18000AC71
0x18000abfd  cmp     ecx, 8007050Ch
0x18000ac03  jz      short loc_18000AC6C
0x18000ac05  cmp     ecx, 8007054Fh
0x18000ac0b  jz      short loc_18000AC65
0x18000ac0d  cmp     ecx, 800705B9h
0x18000ac13  jz      short loc_18000AC5E
0x18000ac15  test    ecx, ecx
0x18000ac17  jz      short loc_18000AC5A
0x18000ac19  bt      ecx, 1Ch
0x18000ac1d  jnb     short loc_18000AC25
0x18000ac1f  btr     ecx, 1Ch
0x18000ac23  jmp     short loc_18000AC71
0x18000ac25  mov     eax, ecx
0x18000ac27  and     eax, 1FFF0000h
0x18000ac2c  cmp     eax, 70000h
0x18000ac31  jnz     short loc_18000AC44
0x18000ac33  movzx   ecx, cx
0x18000ac36  mov     eax, ecx
0x18000ac38  or      eax, 0C0070000h
0x18000ac3d  test    ecx, ecx
0x18000ac3f  cmovnz  ecx, eax
0x18000ac42  jmp     short loc_18000AC71
0x18000ac44  cmp     eax, 90000h
0x18000ac49  jnz     short loc_18000AC65
0x18000ac4b  test    ecx, ecx
0x18000ac4d  jle     short loc_18000AC71
0x18000ac4f  movzx   ecx, cx
0x18000ac52  or      ecx, 0C0090000h
0x18000ac58  jmp     short loc_18000AC71
0x18000ac5a  xor     ecx, ecx
0x18000ac5c  jmp     short loc_18000AC71
0x18000ac5e  mov     ecx, 0C000A083h
0x18000ac63  jmp     short loc_18000AC71
0x18000ac65  mov     ecx, 0C00000E5h
0x18000ac6a  jmp     short loc_18000AC71
0x18000ac6c  mov     ecx, 0C000042Bh
0x18000ac71  mov     eax, ecx
0x18000ac73  retn
```
