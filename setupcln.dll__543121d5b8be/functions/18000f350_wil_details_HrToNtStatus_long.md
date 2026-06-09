# wil::details::HrToNtStatus(long)

- ea: `0x18000f350`
- end: `0x18000f50c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000caa4`
- `0x18000cb1c`
- `0x18000cb6c`
- `0x18000cc2c`
- `0x18000e6e8`
- `0x18000f650`

## callees

- `0x18000f350`

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
0x18000f350  mov     eax, 800700EAh
0x18000f355  cmp     ecx, eax
0x18000f357  jg      loc_18000F42C
0x18000f35d  jz      loc_18000F422
0x18000f363  mov     eax, 80070057h
0x18000f368  cmp     ecx, eax
0x18000f36a  jg      short loc_18000F3D6
0x18000f36c  jz      short loc_18000F3CC
0x18000f36e  cmp     ecx, 80004005h
0x18000f374  jz      short loc_18000F3C2
0x18000f376  cmp     ecx, 80070001h
0x18000f37c  jz      short loc_18000F3B8
0x18000f37e  cmp     ecx, 80070002h
0x18000f384  jz      short loc_18000F3AE
0x18000f386  cmp     ecx, 80070003h
0x18000f38c  jz      short loc_18000F3A4
0x18000f38e  cmp     ecx, 8007000Eh
0x18000f394  jnz     loc_18000F4B1
0x18000f39a  mov     ecx, 0C0000017h
0x18000f39f  jmp     loc_18000F509
0x18000f3a4  mov     ecx, 0C000003Ah
0x18000f3a9  jmp     loc_18000F509
0x18000f3ae  mov     ecx, 0C0000034h
0x18000f3b3  jmp     loc_18000F509
0x18000f3b8  mov     ecx, 0C0000002h
0x18000f3bd  jmp     loc_18000F509
0x18000f3c2  mov     ecx, 0C0000001h
0x18000f3c7  jmp     loc_18000F509
0x18000f3cc  mov     ecx, 0C000000Dh
0x18000f3d1  jmp     loc_18000F509
0x18000f3d6  cmp     ecx, 80070070h
0x18000f3dc  jz      short loc_18000F418
0x18000f3de  cmp     ecx, 8007007Ah
0x18000f3e4  jz      short loc_18000F40E
0x18000f3e6  cmp     ecx, 8007007Bh
0x18000f3ec  jz      short loc_18000F404
0x18000f3ee  cmp     ecx, 8007007Eh
0x18000f3f4  jnz     loc_18000F4B1
0x18000f3fa  mov     ecx, 0C0000135h
0x18000f3ff  jmp     loc_18000F509
0x18000f404  mov     ecx, 0C0000033h
0x18000f409  jmp     loc_18000F509
0x18000f40e  mov     ecx, 0C0000023h
0x18000f413  jmp     loc_18000F509
0x18000f418  mov     ecx, 0C000007Fh
0x18000f41d  jmp     loc_18000F509
0x18000f422  mov     ecx, 80000005h
0x18000f427  jmp     loc_18000F509
0x18000f42c  mov     eax, 8007047Eh
0x18000f431  cmp     ecx, eax
0x18000f433  jg      short loc_18000F495
0x18000f435  jz      short loc_18000F48E
0x18000f437  cmp     ecx, 80070216h
0x18000f43d  jz      short loc_18000F487
0x18000f43f  cmp     ecx, 8007023Eh
0x18000f445  jz      short loc_18000F47D
0x18000f447  cmp     ecx, 80070246h
0x18000f44d  jz      short loc_18000F473
0x18000f44f  cmp     ecx, 80070247h
0x18000f455  jz      short loc_18000F469
0x18000f457  cmp     ecx, 80070272h
0x18000f45d  jnz     short loc_18000F4B1
0x18000f45f  mov     ecx, 0C0000273h
0x18000f464  jmp     loc_18000F509
0x18000f469  mov     ecx, 0C0000163h
0x18000f46e  jmp     loc_18000F509
0x18000f473  mov     ecx, 0C0000161h
0x18000f478  jmp     loc_18000F509
0x18000f47d  mov     ecx, 0C0000025h
0x18000f482  jmp     loc_18000F509
0x18000f487  mov     ecx, 0C0000095h
0x18000f48c  jmp     short loc_18000F509
0x18000f48e  mov     ecx, 0C0000059h
0x18000f493  jmp     short loc_18000F509
0x18000f495  cmp     ecx, 8007050Ch
0x18000f49b  jz      short loc_18000F504
0x18000f49d  cmp     ecx, 8007054Fh
0x18000f4a3  jz      short loc_18000F4FD
0x18000f4a5  cmp     ecx, 800705B9h
0x18000f4ab  jz      short loc_18000F4F6
0x18000f4ad  test    ecx, ecx
0x18000f4af  jz      short loc_18000F4F2
0x18000f4b1  bt      ecx, 1Ch
0x18000f4b5  jnb     short loc_18000F4BD
0x18000f4b7  btr     ecx, 1Ch
0x18000f4bb  jmp     short loc_18000F509
0x18000f4bd  mov     eax, ecx
0x18000f4bf  and     eax, 1FFF0000h
0x18000f4c4  cmp     eax, 70000h
0x18000f4c9  jnz     short loc_18000F4DC
0x18000f4cb  movzx   ecx, cx
0x18000f4ce  mov     eax, ecx
0x18000f4d0  or      eax, 0C0070000h
0x18000f4d5  test    ecx, ecx
0x18000f4d7  cmovnz  ecx, eax
0x18000f4da  jmp     short loc_18000F509
0x18000f4dc  cmp     eax, 90000h
0x18000f4e1  jnz     short loc_18000F4FD
0x18000f4e3  test    ecx, ecx
0x18000f4e5  jle     short loc_18000F509
0x18000f4e7  movzx   ecx, cx
0x18000f4ea  or      ecx, 0C0090000h
0x18000f4f0  jmp     short loc_18000F509
0x18000f4f2  xor     ecx, ecx
0x18000f4f4  jmp     short loc_18000F509
0x18000f4f6  mov     ecx, 0C000A083h
0x18000f4fb  jmp     short loc_18000F509
0x18000f4fd  mov     ecx, 0C00000E5h
0x18000f502  jmp     short loc_18000F509
0x18000f504  mov     ecx, 0C000042Bh
0x18000f509  mov     eax, ecx
0x18000f50b  retn
```
