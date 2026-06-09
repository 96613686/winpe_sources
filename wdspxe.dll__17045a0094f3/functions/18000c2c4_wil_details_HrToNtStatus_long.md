# wil::details::HrToNtStatus(long)

- ea: `0x18000c2c4`
- end: `0x18000c48d`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `457`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180009240`
- `0x1800092f8`
- `0x18000934c`
- `0x180009408`
- `0x18000b5e0`
- `0x18000c7f4`

## callees

- `0x18000c2c4`

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
0x18000c2c4  mov     eax, 800700EAh
0x18000c2c9  mov     edx, ecx
0x18000c2cb  cmp     ecx, eax
0x18000c2cd  jg      loc_18000C3A2
0x18000c2d3  jz      loc_18000C398
0x18000c2d9  mov     eax, 80070057h
0x18000c2de  cmp     ecx, eax
0x18000c2e0  jg      short loc_18000C34C
0x18000c2e2  jz      short loc_18000C342
0x18000c2e4  cmp     ecx, 80004005h
0x18000c2ea  jz      short loc_18000C338
0x18000c2ec  cmp     ecx, 80070001h
0x18000c2f2  jz      short loc_18000C32E
0x18000c2f4  cmp     ecx, 80070002h
0x18000c2fa  jz      short loc_18000C324
0x18000c2fc  cmp     ecx, 80070003h
0x18000c302  jz      short loc_18000C31A
0x18000c304  cmp     ecx, 8007000Eh
0x18000c30a  jnz     loc_18000C42A
0x18000c310  mov     edx, 0C0000017h
0x18000c315  jmp     loc_18000C48A
0x18000c31a  mov     edx, 0C000003Ah
0x18000c31f  jmp     loc_18000C48A
0x18000c324  mov     edx, 0C0000034h
0x18000c329  jmp     loc_18000C48A
0x18000c32e  mov     edx, 0C0000002h
0x18000c333  jmp     loc_18000C48A
0x18000c338  mov     edx, 0C0000001h
0x18000c33d  jmp     loc_18000C48A
0x18000c342  mov     edx, 0C000000Dh
0x18000c347  jmp     loc_18000C48A
0x18000c34c  cmp     edx, 80070070h
0x18000c352  jz      short loc_18000C38E
0x18000c354  cmp     edx, 8007007Ah
0x18000c35a  jz      short loc_18000C384
0x18000c35c  cmp     edx, 8007007Bh
0x18000c362  jz      short loc_18000C37A
0x18000c364  cmp     edx, 8007007Eh
0x18000c36a  jnz     loc_18000C42A
0x18000c370  mov     edx, 0C0000135h
0x18000c375  jmp     loc_18000C48A
0x18000c37a  mov     edx, 0C0000033h
0x18000c37f  jmp     loc_18000C48A
0x18000c384  mov     edx, 0C0000023h
0x18000c389  jmp     loc_18000C48A
0x18000c38e  mov     edx, 0C000007Fh
0x18000c393  jmp     loc_18000C48A
0x18000c398  mov     edx, 80000005h
0x18000c39d  jmp     loc_18000C48A
0x18000c3a2  mov     eax, 8007047Eh
0x18000c3a7  cmp     edx, eax
0x18000c3a9  jg      short loc_18000C40E
0x18000c3ab  jz      short loc_18000C407
0x18000c3ad  cmp     edx, 80070216h
0x18000c3b3  jz      short loc_18000C3FD
0x18000c3b5  cmp     edx, 8007023Eh
0x18000c3bb  jz      short loc_18000C3F3
0x18000c3bd  cmp     edx, 80070246h
0x18000c3c3  jz      short loc_18000C3E9
0x18000c3c5  cmp     edx, 80070247h
0x18000c3cb  jz      short loc_18000C3DF
0x18000c3cd  cmp     edx, 80070272h
0x18000c3d3  jnz     short loc_18000C42A
0x18000c3d5  mov     edx, 0C0000273h
0x18000c3da  jmp     loc_18000C48A
0x18000c3df  mov     edx, 0C0000163h
0x18000c3e4  jmp     loc_18000C48A
0x18000c3e9  mov     edx, 0C0000161h
0x18000c3ee  jmp     loc_18000C48A
0x18000c3f3  mov     edx, 0C0000025h
0x18000c3f8  jmp     loc_18000C48A
0x18000c3fd  mov     edx, 0C0000095h
0x18000c402  jmp     loc_18000C48A
0x18000c407  mov     edx, 0C0000059h
0x18000c40c  jmp     short loc_18000C48A
0x18000c40e  cmp     edx, 8007050Ch
0x18000c414  jz      short loc_18000C485
0x18000c416  cmp     edx, 8007054Fh
0x18000c41c  jz      short loc_18000C47E
0x18000c41e  cmp     edx, 800705B9h
0x18000c424  jz      short loc_18000C477
0x18000c426  test    edx, edx
0x18000c428  jz      short loc_18000C473
0x18000c42a  bt      edx, 1Ch
0x18000c42e  jnb     short loc_18000C436
0x18000c430  btr     edx, 1Ch
0x18000c434  jmp     short loc_18000C48A
0x18000c436  mov     eax, edx
0x18000c438  mov     ecx, 1FFF0000h
0x18000c43d  and     eax, ecx
0x18000c43f  cmp     eax, 70000h
0x18000c444  jnz     short loc_18000C459
0x18000c446  movzx   ecx, dx
0x18000c449  mov     eax, ecx
0x18000c44b  mov     edx, ecx
0x18000c44d  or      eax, 0C0070000h
0x18000c452  test    ecx, ecx
0x18000c454  cmovnz  edx, eax
0x18000c457  jmp     short loc_18000C48A
0x18000c459  mov     eax, edx
0x18000c45b  and     eax, ecx
0x18000c45d  cmp     eax, 90000h
0x18000c462  jnz     short loc_18000C47E
0x18000c464  test    edx, edx
0x18000c466  jle     short loc_18000C48A
0x18000c468  movzx   edx, dx
0x18000c46b  or      edx, 0C0090000h
0x18000c471  jmp     short loc_18000C48A
0x18000c473  xor     edx, edx
0x18000c475  jmp     short loc_18000C48A
0x18000c477  mov     edx, 0C000A083h
0x18000c47c  jmp     short loc_18000C48A
0x18000c47e  mov     edx, 0C00000E5h
0x18000c483  jmp     short loc_18000C48A
0x18000c485  mov     edx, 0C000042Bh
0x18000c48a  mov     eax, edx
0x18000c48c  retn
```
