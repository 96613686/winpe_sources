# wil::details::HrToNtStatus(long)

- ea: `0x180009144`
- end: `0x180009300`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090c0`
- `0x18000b0d8`
- `0x18000b148`
- `0x18000b198`
- `0x18000b1fc`
- `0x18000c6a0`

## callees

- `0x180009144`

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
0x180009144  mov     eax, 800700EAh
0x180009149  cmp     ecx, eax
0x18000914b  jg      loc_180009220
0x180009151  jz      loc_180009216
0x180009157  mov     eax, 80070057h
0x18000915c  cmp     ecx, eax
0x18000915e  jg      short loc_1800091CA
0x180009160  jz      short loc_1800091C0
0x180009162  cmp     ecx, 80004005h
0x180009168  jz      short loc_1800091B6
0x18000916a  cmp     ecx, 80070001h
0x180009170  jz      short loc_1800091AC
0x180009172  cmp     ecx, 80070002h
0x180009178  jz      short loc_1800091A2
0x18000917a  cmp     ecx, 80070003h
0x180009180  jz      short loc_180009198
0x180009182  cmp     ecx, 8007000Eh
0x180009188  jnz     loc_1800092A5
0x18000918e  mov     ecx, 0C0000017h
0x180009193  jmp     loc_1800092FD
0x180009198  mov     ecx, 0C000003Ah
0x18000919d  jmp     loc_1800092FD
0x1800091a2  mov     ecx, 0C0000034h
0x1800091a7  jmp     loc_1800092FD
0x1800091ac  mov     ecx, 0C0000002h
0x1800091b1  jmp     loc_1800092FD
0x1800091b6  mov     ecx, 0C0000001h
0x1800091bb  jmp     loc_1800092FD
0x1800091c0  mov     ecx, 0C000000Dh
0x1800091c5  jmp     loc_1800092FD
0x1800091ca  cmp     ecx, 80070070h
0x1800091d0  jz      short loc_18000920C
0x1800091d2  cmp     ecx, 8007007Ah
0x1800091d8  jz      short loc_180009202
0x1800091da  cmp     ecx, 8007007Bh
0x1800091e0  jz      short loc_1800091F8
0x1800091e2  cmp     ecx, 8007007Eh
0x1800091e8  jnz     loc_1800092A5
0x1800091ee  mov     ecx, 0C0000135h
0x1800091f3  jmp     loc_1800092FD
0x1800091f8  mov     ecx, 0C0000033h
0x1800091fd  jmp     loc_1800092FD
0x180009202  mov     ecx, 0C0000023h
0x180009207  jmp     loc_1800092FD
0x18000920c  mov     ecx, 0C000007Fh
0x180009211  jmp     loc_1800092FD
0x180009216  mov     ecx, 80000005h
0x18000921b  jmp     loc_1800092FD
0x180009220  mov     eax, 8007047Eh
0x180009225  cmp     ecx, eax
0x180009227  jg      short loc_180009289
0x180009229  jz      short loc_180009282
0x18000922b  cmp     ecx, 80070216h
0x180009231  jz      short loc_18000927B
0x180009233  cmp     ecx, 8007023Eh
0x180009239  jz      short loc_180009271
0x18000923b  cmp     ecx, 80070246h
0x180009241  jz      short loc_180009267
0x180009243  cmp     ecx, 80070247h
0x180009249  jz      short loc_18000925D
0x18000924b  cmp     ecx, 80070272h
0x180009251  jnz     short loc_1800092A5
0x180009253  mov     ecx, 0C0000273h
0x180009258  jmp     loc_1800092FD
0x18000925d  mov     ecx, 0C0000163h
0x180009262  jmp     loc_1800092FD
0x180009267  mov     ecx, 0C0000161h
0x18000926c  jmp     loc_1800092FD
0x180009271  mov     ecx, 0C0000025h
0x180009276  jmp     loc_1800092FD
0x18000927b  mov     ecx, 0C0000095h
0x180009280  jmp     short loc_1800092FD
0x180009282  mov     ecx, 0C0000059h
0x180009287  jmp     short loc_1800092FD
0x180009289  cmp     ecx, 8007050Ch
0x18000928f  jz      short loc_1800092F8
0x180009291  cmp     ecx, 8007054Fh
0x180009297  jz      short loc_1800092F1
0x180009299  cmp     ecx, 800705B9h
0x18000929f  jz      short loc_1800092EA
0x1800092a1  test    ecx, ecx
0x1800092a3  jz      short loc_1800092E6
0x1800092a5  bt      ecx, 1Ch
0x1800092a9  jnb     short loc_1800092B1
0x1800092ab  btr     ecx, 1Ch
0x1800092af  jmp     short loc_1800092FD
0x1800092b1  mov     eax, ecx
0x1800092b3  and     eax, 1FFF0000h
0x1800092b8  cmp     eax, 70000h
0x1800092bd  jnz     short loc_1800092D0
0x1800092bf  movzx   ecx, cx
0x1800092c2  mov     eax, ecx
0x1800092c4  or      eax, 0C0070000h
0x1800092c9  test    ecx, ecx
0x1800092cb  cmovnz  ecx, eax
0x1800092ce  jmp     short loc_1800092FD
0x1800092d0  cmp     eax, 90000h
0x1800092d5  jnz     short loc_1800092F1
0x1800092d7  test    ecx, ecx
0x1800092d9  jle     short loc_1800092FD
0x1800092db  movzx   ecx, cx
0x1800092de  or      ecx, 0C0090000h
0x1800092e4  jmp     short loc_1800092FD
0x1800092e6  xor     ecx, ecx
0x1800092e8  jmp     short loc_1800092FD
0x1800092ea  mov     ecx, 0C000A083h
0x1800092ef  jmp     short loc_1800092FD
0x1800092f1  mov     ecx, 0C00000E5h
0x1800092f6  jmp     short loc_1800092FD
0x1800092f8  mov     ecx, 0C000042Bh
0x1800092fd  mov     eax, ecx
0x1800092ff  retn
```
