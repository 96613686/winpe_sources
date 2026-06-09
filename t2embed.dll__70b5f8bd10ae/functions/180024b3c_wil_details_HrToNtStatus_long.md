# wil::details::HrToNtStatus(long)

- ea: `0x180024b3c`
- end: `0x180024cf8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800235b4`
- `0x180023624`
- `0x18002369c`
- `0x1800236ec`
- `0x180023750`
- `0x180024d0c`

## callees

- `0x180024b3c`

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
0x180024b3c  mov     eax, 800700EAh
0x180024b41  cmp     ecx, eax
0x180024b43  jg      loc_180024C18
0x180024b49  jz      loc_180024C0E
0x180024b4f  mov     eax, 80070057h
0x180024b54  cmp     ecx, eax
0x180024b56  jg      short loc_180024BC2
0x180024b58  jz      short loc_180024BB8
0x180024b5a  cmp     ecx, 80004005h
0x180024b60  jz      short loc_180024BAE
0x180024b62  cmp     ecx, 80070001h
0x180024b68  jz      short loc_180024BA4
0x180024b6a  cmp     ecx, 80070002h
0x180024b70  jz      short loc_180024B9A
0x180024b72  cmp     ecx, 80070003h
0x180024b78  jz      short loc_180024B90
0x180024b7a  cmp     ecx, 8007000Eh
0x180024b80  jnz     loc_180024C9D
0x180024b86  mov     ecx, 0C0000017h
0x180024b8b  jmp     loc_180024CF5
0x180024b90  mov     ecx, 0C000003Ah
0x180024b95  jmp     loc_180024CF5
0x180024b9a  mov     ecx, 0C0000034h
0x180024b9f  jmp     loc_180024CF5
0x180024ba4  mov     ecx, 0C0000002h
0x180024ba9  jmp     loc_180024CF5
0x180024bae  mov     ecx, 0C0000001h
0x180024bb3  jmp     loc_180024CF5
0x180024bb8  mov     ecx, 0C000000Dh
0x180024bbd  jmp     loc_180024CF5
0x180024bc2  cmp     ecx, 80070070h
0x180024bc8  jz      short loc_180024C04
0x180024bca  cmp     ecx, 8007007Ah
0x180024bd0  jz      short loc_180024BFA
0x180024bd2  cmp     ecx, 8007007Bh
0x180024bd8  jz      short loc_180024BF0
0x180024bda  cmp     ecx, 8007007Eh
0x180024be0  jnz     loc_180024C9D
0x180024be6  mov     ecx, 0C0000135h
0x180024beb  jmp     loc_180024CF5
0x180024bf0  mov     ecx, 0C0000033h
0x180024bf5  jmp     loc_180024CF5
0x180024bfa  mov     ecx, 0C0000023h
0x180024bff  jmp     loc_180024CF5
0x180024c04  mov     ecx, 0C000007Fh
0x180024c09  jmp     loc_180024CF5
0x180024c0e  mov     ecx, 80000005h
0x180024c13  jmp     loc_180024CF5
0x180024c18  mov     eax, 8007047Eh
0x180024c1d  cmp     ecx, eax
0x180024c1f  jg      short loc_180024C81
0x180024c21  jz      short loc_180024C7A
0x180024c23  cmp     ecx, 80070216h
0x180024c29  jz      short loc_180024C73
0x180024c2b  cmp     ecx, 8007023Eh
0x180024c31  jz      short loc_180024C69
0x180024c33  cmp     ecx, 80070246h
0x180024c39  jz      short loc_180024C5F
0x180024c3b  cmp     ecx, 80070247h
0x180024c41  jz      short loc_180024C55
0x180024c43  cmp     ecx, 80070272h
0x180024c49  jnz     short loc_180024C9D
0x180024c4b  mov     ecx, 0C0000273h
0x180024c50  jmp     loc_180024CF5
0x180024c55  mov     ecx, 0C0000163h
0x180024c5a  jmp     loc_180024CF5
0x180024c5f  mov     ecx, 0C0000161h
0x180024c64  jmp     loc_180024CF5
0x180024c69  mov     ecx, 0C0000025h
0x180024c6e  jmp     loc_180024CF5
0x180024c73  mov     ecx, 0C0000095h
0x180024c78  jmp     short loc_180024CF5
0x180024c7a  mov     ecx, 0C0000059h
0x180024c7f  jmp     short loc_180024CF5
0x180024c81  cmp     ecx, 8007050Ch
0x180024c87  jz      short loc_180024CF0
0x180024c89  cmp     ecx, 8007054Fh
0x180024c8f  jz      short loc_180024CE9
0x180024c91  cmp     ecx, 800705B9h
0x180024c97  jz      short loc_180024CE2
0x180024c99  test    ecx, ecx
0x180024c9b  jz      short loc_180024CDE
0x180024c9d  bt      ecx, 1Ch
0x180024ca1  jnb     short loc_180024CA9
0x180024ca3  btr     ecx, 1Ch
0x180024ca7  jmp     short loc_180024CF5
0x180024ca9  mov     eax, ecx
0x180024cab  and     eax, 1FFF0000h
0x180024cb0  cmp     eax, 70000h
0x180024cb5  jnz     short loc_180024CC8
0x180024cb7  movzx   ecx, cx
0x180024cba  mov     eax, ecx
0x180024cbc  or      eax, 0C0070000h
0x180024cc1  test    ecx, ecx
0x180024cc3  cmovnz  ecx, eax
0x180024cc6  jmp     short loc_180024CF5
0x180024cc8  cmp     eax, 90000h
0x180024ccd  jnz     short loc_180024CE9
0x180024ccf  test    ecx, ecx
0x180024cd1  jle     short loc_180024CF5
0x180024cd3  movzx   ecx, cx
0x180024cd6  or      ecx, 0C0090000h
0x180024cdc  jmp     short loc_180024CF5
0x180024cde  xor     ecx, ecx
0x180024ce0  jmp     short loc_180024CF5
0x180024ce2  mov     ecx, 0C000A083h
0x180024ce7  jmp     short loc_180024CF5
0x180024ce9  mov     ecx, 0C00000E5h
0x180024cee  jmp     short loc_180024CF5
0x180024cf0  mov     ecx, 0C000042Bh
0x180024cf5  mov     eax, ecx
0x180024cf7  retn
```
