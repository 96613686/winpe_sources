# wil::details::HrToNtStatus(long)

- ea: `0x180009b0c`
- end: `0x180009cd5`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `457`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006708`
- `0x1800067c0`
- `0x180006814`
- `0x1800068d0`
- `0x180008c30`
- `0x18000a414`

## callees

- `0x180009b0c`

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
0x180009b0c  mov     eax, 800700EAh
0x180009b11  mov     edx, ecx
0x180009b13  cmp     ecx, eax
0x180009b15  jg      loc_180009BEA
0x180009b1b  jz      loc_180009BE0
0x180009b21  mov     eax, 80070057h
0x180009b26  cmp     ecx, eax
0x180009b28  jg      short loc_180009B94
0x180009b2a  jz      short loc_180009B8A
0x180009b2c  cmp     ecx, 80004005h
0x180009b32  jz      short loc_180009B80
0x180009b34  cmp     ecx, 80070001h
0x180009b3a  jz      short loc_180009B76
0x180009b3c  cmp     ecx, 80070002h
0x180009b42  jz      short loc_180009B6C
0x180009b44  cmp     ecx, 80070003h
0x180009b4a  jz      short loc_180009B62
0x180009b4c  cmp     ecx, 8007000Eh
0x180009b52  jnz     loc_180009C72
0x180009b58  mov     edx, 0C0000017h
0x180009b5d  jmp     loc_180009CD2
0x180009b62  mov     edx, 0C000003Ah
0x180009b67  jmp     loc_180009CD2
0x180009b6c  mov     edx, 0C0000034h
0x180009b71  jmp     loc_180009CD2
0x180009b76  mov     edx, 0C0000002h
0x180009b7b  jmp     loc_180009CD2
0x180009b80  mov     edx, 0C0000001h
0x180009b85  jmp     loc_180009CD2
0x180009b8a  mov     edx, 0C000000Dh
0x180009b8f  jmp     loc_180009CD2
0x180009b94  cmp     edx, 80070070h
0x180009b9a  jz      short loc_180009BD6
0x180009b9c  cmp     edx, 8007007Ah
0x180009ba2  jz      short loc_180009BCC
0x180009ba4  cmp     edx, 8007007Bh
0x180009baa  jz      short loc_180009BC2
0x180009bac  cmp     edx, 8007007Eh
0x180009bb2  jnz     loc_180009C72
0x180009bb8  mov     edx, 0C0000135h
0x180009bbd  jmp     loc_180009CD2
0x180009bc2  mov     edx, 0C0000033h
0x180009bc7  jmp     loc_180009CD2
0x180009bcc  mov     edx, 0C0000023h
0x180009bd1  jmp     loc_180009CD2
0x180009bd6  mov     edx, 0C000007Fh
0x180009bdb  jmp     loc_180009CD2
0x180009be0  mov     edx, 80000005h
0x180009be5  jmp     loc_180009CD2
0x180009bea  mov     eax, 8007047Eh
0x180009bef  cmp     edx, eax
0x180009bf1  jg      short loc_180009C56
0x180009bf3  jz      short loc_180009C4F
0x180009bf5  cmp     edx, 80070216h
0x180009bfb  jz      short loc_180009C45
0x180009bfd  cmp     edx, 8007023Eh
0x180009c03  jz      short loc_180009C3B
0x180009c05  cmp     edx, 80070246h
0x180009c0b  jz      short loc_180009C31
0x180009c0d  cmp     edx, 80070247h
0x180009c13  jz      short loc_180009C27
0x180009c15  cmp     edx, 80070272h
0x180009c1b  jnz     short loc_180009C72
0x180009c1d  mov     edx, 0C0000273h
0x180009c22  jmp     loc_180009CD2
0x180009c27  mov     edx, 0C0000163h
0x180009c2c  jmp     loc_180009CD2
0x180009c31  mov     edx, 0C0000161h
0x180009c36  jmp     loc_180009CD2
0x180009c3b  mov     edx, 0C0000025h
0x180009c40  jmp     loc_180009CD2
0x180009c45  mov     edx, 0C0000095h
0x180009c4a  jmp     loc_180009CD2
0x180009c4f  mov     edx, 0C0000059h
0x180009c54  jmp     short loc_180009CD2
0x180009c56  cmp     edx, 8007050Ch
0x180009c5c  jz      short loc_180009CCD
0x180009c5e  cmp     edx, 8007054Fh
0x180009c64  jz      short loc_180009CC6
0x180009c66  cmp     edx, 800705B9h
0x180009c6c  jz      short loc_180009CBF
0x180009c6e  test    edx, edx
0x180009c70  jz      short loc_180009CBB
0x180009c72  bt      edx, 1Ch
0x180009c76  jnb     short loc_180009C7E
0x180009c78  btr     edx, 1Ch
0x180009c7c  jmp     short loc_180009CD2
0x180009c7e  mov     eax, edx
0x180009c80  mov     ecx, 1FFF0000h
0x180009c85  and     eax, ecx
0x180009c87  cmp     eax, 70000h
0x180009c8c  jnz     short loc_180009CA1
0x180009c8e  movzx   ecx, dx
0x180009c91  mov     eax, ecx
0x180009c93  mov     edx, ecx
0x180009c95  or      eax, 0C0070000h
0x180009c9a  test    ecx, ecx
0x180009c9c  cmovnz  edx, eax
0x180009c9f  jmp     short loc_180009CD2
0x180009ca1  mov     eax, edx
0x180009ca3  and     eax, ecx
0x180009ca5  cmp     eax, 90000h
0x180009caa  jnz     short loc_180009CC6
0x180009cac  test    edx, edx
0x180009cae  jle     short loc_180009CD2
0x180009cb0  movzx   edx, dx
0x180009cb3  or      edx, 0C0090000h
0x180009cb9  jmp     short loc_180009CD2
0x180009cbb  xor     edx, edx
0x180009cbd  jmp     short loc_180009CD2
0x180009cbf  mov     edx, 0C000A083h
0x180009cc4  jmp     short loc_180009CD2
0x180009cc6  mov     edx, 0C00000E5h
0x180009ccb  jmp     short loc_180009CD2
0x180009ccd  mov     edx, 0C000042Bh
0x180009cd2  mov     eax, edx
0x180009cd4  retn
```
