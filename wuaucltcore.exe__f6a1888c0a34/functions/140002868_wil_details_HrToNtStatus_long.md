# wil::details::HrToNtStatus(long)

- ea: `0x140002868`
- end: `0x140002a27`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `447`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140001d30`
- `0x1400021b8`
- `0x140002a30`
- `0x140002a5c`
- `0x140003c60`
- `0x1400052cc`
- `0x140005554`
- `0x14000b344`
- `0x14000c49c`
- `0x14000d1e8`
- `0x140014874`
- `0x140021284`
- `0x1400212fa`
- `0x1400213bd`
- `0x140021433`

## callees

- `0x140002868`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // ecx
  int v2; // eax
  unsigned int v3; // eax

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
    v2 = (unsigned __int16)this;
    v1 = (unsigned __int16)this | 0xC0070000;
    if ( !v2 )
      return 0;
    return v1;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
    return (unsigned int)-1073741595;
  v3 = (unsigned __int16)this | 0xC0090000;
  if ( (int)this <= 0 )
    return (unsigned int)this;
  return v3;
}

```

## disassembly

```asm
0x140002868  mov     eax, 800700EAh
0x14000286d  cmp     ecx, eax
0x14000286f  jg      loc_140002944
0x140002875  jz      loc_14000293A
0x14000287b  mov     eax, 80070057h
0x140002880  cmp     ecx, eax
0x140002882  jg      short loc_1400028EE
0x140002884  jz      short loc_1400028E4
0x140002886  cmp     ecx, 80004005h
0x14000288c  jz      short loc_1400028DA
0x14000288e  cmp     ecx, 80070001h
0x140002894  jz      short loc_1400028D0
0x140002896  cmp     ecx, 80070002h
0x14000289c  jz      short loc_1400028C6
0x14000289e  cmp     ecx, 80070003h
0x1400028a4  jz      short loc_1400028BC
0x1400028a6  cmp     ecx, 8007000Eh
0x1400028ac  jnz     loc_1400029C9
0x1400028b2  mov     ecx, 0C0000017h
0x1400028b7  jmp     loc_140002A24
0x1400028bc  mov     ecx, 0C000003Ah
0x1400028c1  jmp     loc_140002A24
0x1400028c6  mov     ecx, 0C0000034h
0x1400028cb  jmp     loc_140002A24
0x1400028d0  mov     ecx, 0C0000002h
0x1400028d5  jmp     loc_140002A24
0x1400028da  mov     ecx, 0C0000001h
0x1400028df  jmp     loc_140002A24
0x1400028e4  mov     ecx, 0C000000Dh
0x1400028e9  jmp     loc_140002A24
0x1400028ee  cmp     ecx, 80070070h
0x1400028f4  jz      short loc_140002930
0x1400028f6  cmp     ecx, 8007007Ah
0x1400028fc  jz      short loc_140002926
0x1400028fe  cmp     ecx, 8007007Bh
0x140002904  jz      short loc_14000291C
0x140002906  cmp     ecx, 8007007Eh
0x14000290c  jnz     loc_1400029C9
0x140002912  mov     ecx, 0C0000135h
0x140002917  jmp     loc_140002A24
0x14000291c  mov     ecx, 0C0000033h
0x140002921  jmp     loc_140002A24
0x140002926  mov     ecx, 0C0000023h
0x14000292b  jmp     loc_140002A24
0x140002930  mov     ecx, 0C000007Fh
0x140002935  jmp     loc_140002A24
0x14000293a  mov     ecx, 80000005h
0x14000293f  jmp     loc_140002A24
0x140002944  mov     eax, 8007047Eh
0x140002949  cmp     ecx, eax
0x14000294b  jg      short loc_1400029AD
0x14000294d  jz      short loc_1400029A6
0x14000294f  cmp     ecx, 80070216h
0x140002955  jz      short loc_14000299F
0x140002957  cmp     ecx, 8007023Eh
0x14000295d  jz      short loc_140002995
0x14000295f  cmp     ecx, 80070246h
0x140002965  jz      short loc_14000298B
0x140002967  cmp     ecx, 80070247h
0x14000296d  jz      short loc_140002981
0x14000296f  cmp     ecx, 80070272h
0x140002975  jnz     short loc_1400029C9
0x140002977  mov     ecx, 0C0000273h
0x14000297c  jmp     loc_140002A24
0x140002981  mov     ecx, 0C0000163h
0x140002986  jmp     loc_140002A24
0x14000298b  mov     ecx, 0C0000161h
0x140002990  jmp     loc_140002A24
0x140002995  mov     ecx, 0C0000025h
0x14000299a  jmp     loc_140002A24
0x14000299f  mov     ecx, 0C0000095h
0x1400029a4  jmp     short loc_140002A24
0x1400029a6  mov     ecx, 0C0000059h
0x1400029ab  jmp     short loc_140002A24
0x1400029ad  cmp     ecx, 8007050Ch
0x1400029b3  jz      short loc_140002A1F
0x1400029b5  cmp     ecx, 8007054Fh
0x1400029bb  jz      short loc_140002A18
0x1400029bd  cmp     ecx, 800705B9h
0x1400029c3  jz      short loc_140002A11
0x1400029c5  test    ecx, ecx
0x1400029c7  jz      short loc_140002A0D
0x1400029c9  bt      ecx, 1Ch
0x1400029cd  jnb     short loc_1400029D5
0x1400029cf  btr     ecx, 1Ch
0x1400029d3  jmp     short loc_140002A24
0x1400029d5  mov     eax, ecx
0x1400029d7  and     eax, 1FFF0000h
0x1400029dc  cmp     eax, 70000h
0x1400029e1  jnz     short loc_1400029F5
0x1400029e3  movzx   eax, cx
0x1400029e6  mov     ecx, eax
0x1400029e8  or      ecx, 0C0070000h
0x1400029ee  test    eax, eax
0x1400029f0  cmovz   ecx, eax
0x1400029f3  jmp     short loc_140002A24
0x1400029f5  cmp     eax, 90000h
0x1400029fa  jnz     short loc_140002A18
0x1400029fc  movzx   eax, cx
0x1400029ff  or      eax, 0C0090000h
0x140002a04  test    ecx, ecx
0x140002a06  cmovle  eax, ecx
0x140002a09  mov     ecx, eax
0x140002a0b  jmp     short loc_140002A24
0x140002a0d  xor     ecx, ecx
0x140002a0f  jmp     short loc_140002A24
0x140002a11  mov     ecx, 0C000A083h
0x140002a16  jmp     short loc_140002A24
0x140002a18  mov     ecx, 0C00000E5h
0x140002a1d  jmp     short loc_140002A24
0x140002a1f  mov     ecx, 0C000042Bh
0x140002a24  mov     eax, ecx
0x140002a26  retn
```
