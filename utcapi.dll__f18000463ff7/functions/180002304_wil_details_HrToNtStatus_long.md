# wil::details::HrToNtStatus(long)

- ea: `0x180002304`
- end: `0x1800024c0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d48`

## callees

- `0x180002304`

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
0x180002304  mov     eax, 800700EAh
0x180002309  cmp     ecx, eax
0x18000230b  jg      loc_1800023E0
0x180002311  jz      loc_1800023D6
0x180002317  mov     eax, 80070057h
0x18000231c  cmp     ecx, eax
0x18000231e  jg      short loc_18000238A
0x180002320  jz      short loc_180002380
0x180002322  cmp     ecx, 80004005h
0x180002328  jz      short loc_180002376
0x18000232a  cmp     ecx, 80070001h
0x180002330  jz      short loc_18000236C
0x180002332  cmp     ecx, 80070002h
0x180002338  jz      short loc_180002362
0x18000233a  cmp     ecx, 80070003h
0x180002340  jz      short loc_180002358
0x180002342  cmp     ecx, 8007000Eh
0x180002348  jnz     loc_180002465
0x18000234e  mov     ecx, 0C0000017h
0x180002353  jmp     loc_1800024BD
0x180002358  mov     ecx, 0C000003Ah
0x18000235d  jmp     loc_1800024BD
0x180002362  mov     ecx, 0C0000034h
0x180002367  jmp     loc_1800024BD
0x18000236c  mov     ecx, 0C0000002h
0x180002371  jmp     loc_1800024BD
0x180002376  mov     ecx, 0C0000001h
0x18000237b  jmp     loc_1800024BD
0x180002380  mov     ecx, 0C000000Dh
0x180002385  jmp     loc_1800024BD
0x18000238a  cmp     ecx, 80070070h
0x180002390  jz      short loc_1800023CC
0x180002392  cmp     ecx, 8007007Ah
0x180002398  jz      short loc_1800023C2
0x18000239a  cmp     ecx, 8007007Bh
0x1800023a0  jz      short loc_1800023B8
0x1800023a2  cmp     ecx, 8007007Eh
0x1800023a8  jnz     loc_180002465
0x1800023ae  mov     ecx, 0C0000135h
0x1800023b3  jmp     loc_1800024BD
0x1800023b8  mov     ecx, 0C0000033h
0x1800023bd  jmp     loc_1800024BD
0x1800023c2  mov     ecx, 0C0000023h
0x1800023c7  jmp     loc_1800024BD
0x1800023cc  mov     ecx, 0C000007Fh
0x1800023d1  jmp     loc_1800024BD
0x1800023d6  mov     ecx, 80000005h
0x1800023db  jmp     loc_1800024BD
0x1800023e0  mov     eax, 8007047Eh
0x1800023e5  cmp     ecx, eax
0x1800023e7  jg      short loc_180002449
0x1800023e9  jz      short loc_180002442
0x1800023eb  cmp     ecx, 80070216h
0x1800023f1  jz      short loc_18000243B
0x1800023f3  cmp     ecx, 8007023Eh
0x1800023f9  jz      short loc_180002431
0x1800023fb  cmp     ecx, 80070246h
0x180002401  jz      short loc_180002427
0x180002403  cmp     ecx, 80070247h
0x180002409  jz      short loc_18000241D
0x18000240b  cmp     ecx, 80070272h
0x180002411  jnz     short loc_180002465
0x180002413  mov     ecx, 0C0000273h
0x180002418  jmp     loc_1800024BD
0x18000241d  mov     ecx, 0C0000163h
0x180002422  jmp     loc_1800024BD
0x180002427  mov     ecx, 0C0000161h
0x18000242c  jmp     loc_1800024BD
0x180002431  mov     ecx, 0C0000025h
0x180002436  jmp     loc_1800024BD
0x18000243b  mov     ecx, 0C0000095h
0x180002440  jmp     short loc_1800024BD
0x180002442  mov     ecx, 0C0000059h
0x180002447  jmp     short loc_1800024BD
0x180002449  cmp     ecx, 8007050Ch
0x18000244f  jz      short loc_1800024B8
0x180002451  cmp     ecx, 8007054Fh
0x180002457  jz      short loc_1800024B1
0x180002459  cmp     ecx, 800705B9h
0x18000245f  jz      short loc_1800024AA
0x180002461  test    ecx, ecx
0x180002463  jz      short loc_1800024A6
0x180002465  bt      ecx, 1Ch
0x180002469  jnb     short loc_180002471
0x18000246b  btr     ecx, 1Ch
0x18000246f  jmp     short loc_1800024BD
0x180002471  mov     eax, ecx
0x180002473  and     eax, 1FFF0000h
0x180002478  cmp     eax, 70000h
0x18000247d  jnz     short loc_180002490
0x18000247f  movzx   ecx, cx
0x180002482  mov     eax, ecx
0x180002484  or      eax, 0C0070000h
0x180002489  test    ecx, ecx
0x18000248b  cmovnz  ecx, eax
0x18000248e  jmp     short loc_1800024BD
0x180002490  cmp     eax, 90000h
0x180002495  jnz     short loc_1800024B1
0x180002497  test    ecx, ecx
0x180002499  jle     short loc_1800024BD
0x18000249b  movzx   ecx, cx
0x18000249e  or      ecx, 0C0090000h
0x1800024a4  jmp     short loc_1800024BD
0x1800024a6  xor     ecx, ecx
0x1800024a8  jmp     short loc_1800024BD
0x1800024aa  mov     ecx, 0C000A083h
0x1800024af  jmp     short loc_1800024BD
0x1800024b1  mov     ecx, 0C00000E5h
0x1800024b6  jmp     short loc_1800024BD
0x1800024b8  mov     ecx, 0C000042Bh
0x1800024bd  mov     eax, ecx
0x1800024bf  retn
```
