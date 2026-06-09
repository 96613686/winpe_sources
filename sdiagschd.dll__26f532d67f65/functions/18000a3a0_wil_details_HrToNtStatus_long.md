# wil::details::HrToNtStatus(long)

- ea: `0x18000a3a0`
- end: `0x18000a569`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `457`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000876c`
- `0x180008824`
- `0x180008878`
- `0x18000892c`
- `0x180009990`
- `0x18000a570`

## callees

- `0x18000a3a0`

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
0x18000a3a0  mov     eax, 800700EAh
0x18000a3a5  mov     edx, ecx
0x18000a3a7  cmp     ecx, eax
0x18000a3a9  jg      loc_18000A47E
0x18000a3af  jz      loc_18000A474
0x18000a3b5  mov     eax, 80070057h
0x18000a3ba  cmp     ecx, eax
0x18000a3bc  jg      short loc_18000A428
0x18000a3be  jz      short loc_18000A41E
0x18000a3c0  cmp     ecx, 80004005h
0x18000a3c6  jz      short loc_18000A414
0x18000a3c8  cmp     ecx, 80070001h
0x18000a3ce  jz      short loc_18000A40A
0x18000a3d0  cmp     ecx, 80070002h
0x18000a3d6  jz      short loc_18000A400
0x18000a3d8  cmp     ecx, 80070003h
0x18000a3de  jz      short loc_18000A3F6
0x18000a3e0  cmp     ecx, 8007000Eh
0x18000a3e6  jnz     loc_18000A506
0x18000a3ec  mov     edx, 0C0000017h
0x18000a3f1  jmp     loc_18000A566
0x18000a3f6  mov     edx, 0C000003Ah
0x18000a3fb  jmp     loc_18000A566
0x18000a400  mov     edx, 0C0000034h
0x18000a405  jmp     loc_18000A566
0x18000a40a  mov     edx, 0C0000002h
0x18000a40f  jmp     loc_18000A566
0x18000a414  mov     edx, 0C0000001h
0x18000a419  jmp     loc_18000A566
0x18000a41e  mov     edx, 0C000000Dh
0x18000a423  jmp     loc_18000A566
0x18000a428  cmp     edx, 80070070h
0x18000a42e  jz      short loc_18000A46A
0x18000a430  cmp     edx, 8007007Ah
0x18000a436  jz      short loc_18000A460
0x18000a438  cmp     edx, 8007007Bh
0x18000a43e  jz      short loc_18000A456
0x18000a440  cmp     edx, 8007007Eh
0x18000a446  jnz     loc_18000A506
0x18000a44c  mov     edx, 0C0000135h
0x18000a451  jmp     loc_18000A566
0x18000a456  mov     edx, 0C0000033h
0x18000a45b  jmp     loc_18000A566
0x18000a460  mov     edx, 0C0000023h
0x18000a465  jmp     loc_18000A566
0x18000a46a  mov     edx, 0C000007Fh
0x18000a46f  jmp     loc_18000A566
0x18000a474  mov     edx, 80000005h
0x18000a479  jmp     loc_18000A566
0x18000a47e  mov     eax, 8007047Eh
0x18000a483  cmp     edx, eax
0x18000a485  jg      short loc_18000A4EA
0x18000a487  jz      short loc_18000A4E3
0x18000a489  cmp     edx, 80070216h
0x18000a48f  jz      short loc_18000A4D9
0x18000a491  cmp     edx, 8007023Eh
0x18000a497  jz      short loc_18000A4CF
0x18000a499  cmp     edx, 80070246h
0x18000a49f  jz      short loc_18000A4C5
0x18000a4a1  cmp     edx, 80070247h
0x18000a4a7  jz      short loc_18000A4BB
0x18000a4a9  cmp     edx, 80070272h
0x18000a4af  jnz     short loc_18000A506
0x18000a4b1  mov     edx, 0C0000273h
0x18000a4b6  jmp     loc_18000A566
0x18000a4bb  mov     edx, 0C0000163h
0x18000a4c0  jmp     loc_18000A566
0x18000a4c5  mov     edx, 0C0000161h
0x18000a4ca  jmp     loc_18000A566
0x18000a4cf  mov     edx, 0C0000025h
0x18000a4d4  jmp     loc_18000A566
0x18000a4d9  mov     edx, 0C0000095h
0x18000a4de  jmp     loc_18000A566
0x18000a4e3  mov     edx, 0C0000059h
0x18000a4e8  jmp     short loc_18000A566
0x18000a4ea  cmp     edx, 8007050Ch
0x18000a4f0  jz      short loc_18000A561
0x18000a4f2  cmp     edx, 8007054Fh
0x18000a4f8  jz      short loc_18000A55A
0x18000a4fa  cmp     edx, 800705B9h
0x18000a500  jz      short loc_18000A553
0x18000a502  test    edx, edx
0x18000a504  jz      short loc_18000A54F
0x18000a506  bt      edx, 1Ch
0x18000a50a  jnb     short loc_18000A512
0x18000a50c  btr     edx, 1Ch
0x18000a510  jmp     short loc_18000A566
0x18000a512  mov     eax, edx
0x18000a514  mov     ecx, 1FFF0000h
0x18000a519  and     eax, ecx
0x18000a51b  cmp     eax, 70000h
0x18000a520  jnz     short loc_18000A535
0x18000a522  movzx   ecx, dx
0x18000a525  mov     eax, ecx
0x18000a527  mov     edx, ecx
0x18000a529  or      eax, 0C0070000h
0x18000a52e  test    ecx, ecx
0x18000a530  cmovnz  edx, eax
0x18000a533  jmp     short loc_18000A566
0x18000a535  mov     eax, edx
0x18000a537  and     eax, ecx
0x18000a539  cmp     eax, 90000h
0x18000a53e  jnz     short loc_18000A55A
0x18000a540  test    edx, edx
0x18000a542  jle     short loc_18000A566
0x18000a544  movzx   edx, dx
0x18000a547  or      edx, 0C0090000h
0x18000a54d  jmp     short loc_18000A566
0x18000a54f  xor     edx, edx
0x18000a551  jmp     short loc_18000A566
0x18000a553  mov     edx, 0C000A083h
0x18000a558  jmp     short loc_18000A566
0x18000a55a  mov     edx, 0C00000E5h
0x18000a55f  jmp     short loc_18000A566
0x18000a561  mov     edx, 0C000042Bh
0x18000a566  mov     eax, edx
0x18000a568  retn
```
