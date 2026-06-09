# wil::details::HrToNtStatus(long)

- ea: `0x180008558`
- end: `0x180008714`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180006cb4`
- `0x180006d2c`
- `0x180006dac`
- `0x180006dfc`
- `0x180007bbc`
- `0x180008748`
- `0x180008ed0`
- `0x18000ccc8`
- `0x18000cd13`
- `0x18000cdd6`
- `0x18000ce21`

## callees

- `0x180008558`

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
0x180008558  mov     eax, 800700EAh
0x18000855d  cmp     ecx, eax
0x18000855f  jg      loc_180008634
0x180008565  jz      loc_18000862A
0x18000856b  mov     eax, 80070057h
0x180008570  cmp     ecx, eax
0x180008572  jg      short loc_1800085DE
0x180008574  jz      short loc_1800085D4
0x180008576  cmp     ecx, 80004005h
0x18000857c  jz      short loc_1800085CA
0x18000857e  cmp     ecx, 80070001h
0x180008584  jz      short loc_1800085C0
0x180008586  cmp     ecx, 80070002h
0x18000858c  jz      short loc_1800085B6
0x18000858e  cmp     ecx, 80070003h
0x180008594  jz      short loc_1800085AC
0x180008596  cmp     ecx, 8007000Eh
0x18000859c  jnz     loc_1800086B9
0x1800085a2  mov     ecx, 0C0000017h
0x1800085a7  jmp     loc_180008711
0x1800085ac  mov     ecx, 0C000003Ah
0x1800085b1  jmp     loc_180008711
0x1800085b6  mov     ecx, 0C0000034h
0x1800085bb  jmp     loc_180008711
0x1800085c0  mov     ecx, 0C0000002h
0x1800085c5  jmp     loc_180008711
0x1800085ca  mov     ecx, 0C0000001h
0x1800085cf  jmp     loc_180008711
0x1800085d4  mov     ecx, 0C000000Dh
0x1800085d9  jmp     loc_180008711
0x1800085de  cmp     ecx, 80070070h
0x1800085e4  jz      short loc_180008620
0x1800085e6  cmp     ecx, 8007007Ah
0x1800085ec  jz      short loc_180008616
0x1800085ee  cmp     ecx, 8007007Bh
0x1800085f4  jz      short loc_18000860C
0x1800085f6  cmp     ecx, 8007007Eh
0x1800085fc  jnz     loc_1800086B9
0x180008602  mov     ecx, 0C0000135h
0x180008607  jmp     loc_180008711
0x18000860c  mov     ecx, 0C0000033h
0x180008611  jmp     loc_180008711
0x180008616  mov     ecx, 0C0000023h
0x18000861b  jmp     loc_180008711
0x180008620  mov     ecx, 0C000007Fh
0x180008625  jmp     loc_180008711
0x18000862a  mov     ecx, 80000005h
0x18000862f  jmp     loc_180008711
0x180008634  mov     eax, 8007047Eh
0x180008639  cmp     ecx, eax
0x18000863b  jg      short loc_18000869D
0x18000863d  jz      short loc_180008696
0x18000863f  cmp     ecx, 80070216h
0x180008645  jz      short loc_18000868F
0x180008647  cmp     ecx, 8007023Eh
0x18000864d  jz      short loc_180008685
0x18000864f  cmp     ecx, 80070246h
0x180008655  jz      short loc_18000867B
0x180008657  cmp     ecx, 80070247h
0x18000865d  jz      short loc_180008671
0x18000865f  cmp     ecx, 80070272h
0x180008665  jnz     short loc_1800086B9
0x180008667  mov     ecx, 0C0000273h
0x18000866c  jmp     loc_180008711
0x180008671  mov     ecx, 0C0000163h
0x180008676  jmp     loc_180008711
0x18000867b  mov     ecx, 0C0000161h
0x180008680  jmp     loc_180008711
0x180008685  mov     ecx, 0C0000025h
0x18000868a  jmp     loc_180008711
0x18000868f  mov     ecx, 0C0000095h
0x180008694  jmp     short loc_180008711
0x180008696  mov     ecx, 0C0000059h
0x18000869b  jmp     short loc_180008711
0x18000869d  cmp     ecx, 8007050Ch
0x1800086a3  jz      short loc_18000870C
0x1800086a5  cmp     ecx, 8007054Fh
0x1800086ab  jz      short loc_180008705
0x1800086ad  cmp     ecx, 800705B9h
0x1800086b3  jz      short loc_1800086FE
0x1800086b5  test    ecx, ecx
0x1800086b7  jz      short loc_1800086FA
0x1800086b9  bt      ecx, 1Ch
0x1800086bd  jnb     short loc_1800086C5
0x1800086bf  btr     ecx, 1Ch
0x1800086c3  jmp     short loc_180008711
0x1800086c5  mov     eax, ecx
0x1800086c7  and     eax, 1FFF0000h
0x1800086cc  cmp     eax, 70000h
0x1800086d1  jnz     short loc_1800086E4
0x1800086d3  movzx   ecx, cx
0x1800086d6  mov     eax, ecx
0x1800086d8  or      eax, 0C0070000h
0x1800086dd  test    ecx, ecx
0x1800086df  cmovnz  ecx, eax
0x1800086e2  jmp     short loc_180008711
0x1800086e4  cmp     eax, 90000h
0x1800086e9  jnz     short loc_180008705
0x1800086eb  test    ecx, ecx
0x1800086ed  jle     short loc_180008711
0x1800086ef  movzx   ecx, cx
0x1800086f2  or      ecx, 0C0090000h
0x1800086f8  jmp     short loc_180008711
0x1800086fa  xor     ecx, ecx
0x1800086fc  jmp     short loc_180008711
0x1800086fe  mov     ecx, 0C000A083h
0x180008703  jmp     short loc_180008711
0x180008705  mov     ecx, 0C00000E5h
0x18000870a  jmp     short loc_180008711
0x18000870c  mov     ecx, 0C000042Bh
0x180008711  mov     eax, ecx
0x180008713  retn
```
