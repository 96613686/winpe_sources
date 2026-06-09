# wil::details::HrToNtStatus(long)

- ea: `0x1800074c0`
- end: `0x18000767c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f44`
- `0x180002ff4`
- `0x18000304c`
- `0x180003114`
- `0x1800062f8`
- `0x18000776c`
- `0x18000a650`
- `0x180019b59`
- `0x180019bc4`
- `0x180019c8d`
- `0x180019cf8`

## callees

- `0x1800074c0`

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
0x1800074c0  mov     eax, 800700EAh
0x1800074c5  cmp     ecx, eax
0x1800074c7  jg      loc_18000759C
0x1800074cd  jz      loc_180007592
0x1800074d3  mov     eax, 80070057h
0x1800074d8  cmp     ecx, eax
0x1800074da  jg      short loc_180007546
0x1800074dc  jz      short loc_18000753C
0x1800074de  cmp     ecx, 80004005h
0x1800074e4  jz      short loc_180007532
0x1800074e6  cmp     ecx, 80070001h
0x1800074ec  jz      short loc_180007528
0x1800074ee  cmp     ecx, 80070002h
0x1800074f4  jz      short loc_18000751E
0x1800074f6  cmp     ecx, 80070003h
0x1800074fc  jz      short loc_180007514
0x1800074fe  cmp     ecx, 8007000Eh
0x180007504  jnz     loc_180007621
0x18000750a  mov     ecx, 0C0000017h
0x18000750f  jmp     loc_180007679
0x180007514  mov     ecx, 0C000003Ah
0x180007519  jmp     loc_180007679
0x18000751e  mov     ecx, 0C0000034h
0x180007523  jmp     loc_180007679
0x180007528  mov     ecx, 0C0000002h
0x18000752d  jmp     loc_180007679
0x180007532  mov     ecx, 0C0000001h
0x180007537  jmp     loc_180007679
0x18000753c  mov     ecx, 0C000000Dh
0x180007541  jmp     loc_180007679
0x180007546  cmp     ecx, 80070070h
0x18000754c  jz      short loc_180007588
0x18000754e  cmp     ecx, 8007007Ah
0x180007554  jz      short loc_18000757E
0x180007556  cmp     ecx, 8007007Bh
0x18000755c  jz      short loc_180007574
0x18000755e  cmp     ecx, 8007007Eh
0x180007564  jnz     loc_180007621
0x18000756a  mov     ecx, 0C0000135h
0x18000756f  jmp     loc_180007679
0x180007574  mov     ecx, 0C0000033h
0x180007579  jmp     loc_180007679
0x18000757e  mov     ecx, 0C0000023h
0x180007583  jmp     loc_180007679
0x180007588  mov     ecx, 0C000007Fh
0x18000758d  jmp     loc_180007679
0x180007592  mov     ecx, 80000005h
0x180007597  jmp     loc_180007679
0x18000759c  mov     eax, 8007047Eh
0x1800075a1  cmp     ecx, eax
0x1800075a3  jg      short loc_180007605
0x1800075a5  jz      short loc_1800075FE
0x1800075a7  cmp     ecx, 80070216h
0x1800075ad  jz      short loc_1800075F7
0x1800075af  cmp     ecx, 8007023Eh
0x1800075b5  jz      short loc_1800075ED
0x1800075b7  cmp     ecx, 80070246h
0x1800075bd  jz      short loc_1800075E3
0x1800075bf  cmp     ecx, 80070247h
0x1800075c5  jz      short loc_1800075D9
0x1800075c7  cmp     ecx, 80070272h
0x1800075cd  jnz     short loc_180007621
0x1800075cf  mov     ecx, 0C0000273h
0x1800075d4  jmp     loc_180007679
0x1800075d9  mov     ecx, 0C0000163h
0x1800075de  jmp     loc_180007679
0x1800075e3  mov     ecx, 0C0000161h
0x1800075e8  jmp     loc_180007679
0x1800075ed  mov     ecx, 0C0000025h
0x1800075f2  jmp     loc_180007679
0x1800075f7  mov     ecx, 0C0000095h
0x1800075fc  jmp     short loc_180007679
0x1800075fe  mov     ecx, 0C0000059h
0x180007603  jmp     short loc_180007679
0x180007605  cmp     ecx, 8007050Ch
0x18000760b  jz      short loc_180007674
0x18000760d  cmp     ecx, 8007054Fh
0x180007613  jz      short loc_18000766D
0x180007615  cmp     ecx, 800705B9h
0x18000761b  jz      short loc_180007666
0x18000761d  test    ecx, ecx
0x18000761f  jz      short loc_180007662
0x180007621  bt      ecx, 1Ch
0x180007625  jnb     short loc_18000762D
0x180007627  btr     ecx, 1Ch
0x18000762b  jmp     short loc_180007679
0x18000762d  mov     eax, ecx
0x18000762f  and     eax, 1FFF0000h
0x180007634  cmp     eax, 70000h
0x180007639  jnz     short loc_18000764C
0x18000763b  movzx   ecx, cx
0x18000763e  mov     eax, ecx
0x180007640  or      eax, 0C0070000h
0x180007645  test    ecx, ecx
0x180007647  cmovnz  ecx, eax
0x18000764a  jmp     short loc_180007679
0x18000764c  cmp     eax, 90000h
0x180007651  jnz     short loc_18000766D
0x180007653  test    ecx, ecx
0x180007655  jle     short loc_180007679
0x180007657  movzx   ecx, cx
0x18000765a  or      ecx, 0C0090000h
0x180007660  jmp     short loc_180007679
0x180007662  xor     ecx, ecx
0x180007664  jmp     short loc_180007679
0x180007666  mov     ecx, 0C000A083h
0x18000766b  jmp     short loc_180007679
0x18000766d  mov     ecx, 0C00000E5h
0x180007672  jmp     short loc_180007679
0x180007674  mov     ecx, 0C000042Bh
0x180007679  mov     eax, ecx
0x18000767b  retn
```
