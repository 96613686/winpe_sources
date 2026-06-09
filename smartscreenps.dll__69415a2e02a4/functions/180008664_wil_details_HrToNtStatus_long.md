# wil::details::HrToNtStatus(long)

- ea: `0x180008664`
- end: `0x180008820`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180006cc4`
- `0x180006d3c`
- `0x180006dbc`
- `0x180006e0c`
- `0x180007c48`
- `0x180008858`
- `0x180009030`
- `0x18000cfa8`
- `0x18000cff3`
- `0x18000d0b6`
- `0x18000d101`

## callees

- `0x180008664`

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
0x180008664  mov     eax, 800700EAh
0x180008669  cmp     ecx, eax
0x18000866b  jg      loc_180008740
0x180008671  jz      loc_180008736
0x180008677  mov     eax, 80070057h
0x18000867c  cmp     ecx, eax
0x18000867e  jg      short loc_1800086EA
0x180008680  jz      short loc_1800086E0
0x180008682  cmp     ecx, 80004005h
0x180008688  jz      short loc_1800086D6
0x18000868a  cmp     ecx, 80070001h
0x180008690  jz      short loc_1800086CC
0x180008692  cmp     ecx, 80070002h
0x180008698  jz      short loc_1800086C2
0x18000869a  cmp     ecx, 80070003h
0x1800086a0  jz      short loc_1800086B8
0x1800086a2  cmp     ecx, 8007000Eh
0x1800086a8  jnz     loc_1800087C5
0x1800086ae  mov     ecx, 0C0000017h
0x1800086b3  jmp     loc_18000881D
0x1800086b8  mov     ecx, 0C000003Ah
0x1800086bd  jmp     loc_18000881D
0x1800086c2  mov     ecx, 0C0000034h
0x1800086c7  jmp     loc_18000881D
0x1800086cc  mov     ecx, 0C0000002h
0x1800086d1  jmp     loc_18000881D
0x1800086d6  mov     ecx, 0C0000001h
0x1800086db  jmp     loc_18000881D
0x1800086e0  mov     ecx, 0C000000Dh
0x1800086e5  jmp     loc_18000881D
0x1800086ea  cmp     ecx, 80070070h
0x1800086f0  jz      short loc_18000872C
0x1800086f2  cmp     ecx, 8007007Ah
0x1800086f8  jz      short loc_180008722
0x1800086fa  cmp     ecx, 8007007Bh
0x180008700  jz      short loc_180008718
0x180008702  cmp     ecx, 8007007Eh
0x180008708  jnz     loc_1800087C5
0x18000870e  mov     ecx, 0C0000135h
0x180008713  jmp     loc_18000881D
0x180008718  mov     ecx, 0C0000033h
0x18000871d  jmp     loc_18000881D
0x180008722  mov     ecx, 0C0000023h
0x180008727  jmp     loc_18000881D
0x18000872c  mov     ecx, 0C000007Fh
0x180008731  jmp     loc_18000881D
0x180008736  mov     ecx, 80000005h
0x18000873b  jmp     loc_18000881D
0x180008740  mov     eax, 8007047Eh
0x180008745  cmp     ecx, eax
0x180008747  jg      short loc_1800087A9
0x180008749  jz      short loc_1800087A2
0x18000874b  cmp     ecx, 80070216h
0x180008751  jz      short loc_18000879B
0x180008753  cmp     ecx, 8007023Eh
0x180008759  jz      short loc_180008791
0x18000875b  cmp     ecx, 80070246h
0x180008761  jz      short loc_180008787
0x180008763  cmp     ecx, 80070247h
0x180008769  jz      short loc_18000877D
0x18000876b  cmp     ecx, 80070272h
0x180008771  jnz     short loc_1800087C5
0x180008773  mov     ecx, 0C0000273h
0x180008778  jmp     loc_18000881D
0x18000877d  mov     ecx, 0C0000163h
0x180008782  jmp     loc_18000881D
0x180008787  mov     ecx, 0C0000161h
0x18000878c  jmp     loc_18000881D
0x180008791  mov     ecx, 0C0000025h
0x180008796  jmp     loc_18000881D
0x18000879b  mov     ecx, 0C0000095h
0x1800087a0  jmp     short loc_18000881D
0x1800087a2  mov     ecx, 0C0000059h
0x1800087a7  jmp     short loc_18000881D
0x1800087a9  cmp     ecx, 8007050Ch
0x1800087af  jz      short loc_180008818
0x1800087b1  cmp     ecx, 8007054Fh
0x1800087b7  jz      short loc_180008811
0x1800087b9  cmp     ecx, 800705B9h
0x1800087bf  jz      short loc_18000880A
0x1800087c1  test    ecx, ecx
0x1800087c3  jz      short loc_180008806
0x1800087c5  bt      ecx, 1Ch
0x1800087c9  jnb     short loc_1800087D1
0x1800087cb  btr     ecx, 1Ch
0x1800087cf  jmp     short loc_18000881D
0x1800087d1  mov     eax, ecx
0x1800087d3  and     eax, 1FFF0000h
0x1800087d8  cmp     eax, 70000h
0x1800087dd  jnz     short loc_1800087F0
0x1800087df  movzx   ecx, cx
0x1800087e2  mov     eax, ecx
0x1800087e4  or      eax, 0C0070000h
0x1800087e9  test    ecx, ecx
0x1800087eb  cmovnz  ecx, eax
0x1800087ee  jmp     short loc_18000881D
0x1800087f0  cmp     eax, 90000h
0x1800087f5  jnz     short loc_180008811
0x1800087f7  test    ecx, ecx
0x1800087f9  jle     short loc_18000881D
0x1800087fb  movzx   ecx, cx
0x1800087fe  or      ecx, 0C0090000h
0x180008804  jmp     short loc_18000881D
0x180008806  xor     ecx, ecx
0x180008808  jmp     short loc_18000881D
0x18000880a  mov     ecx, 0C000A083h
0x18000880f  jmp     short loc_18000881D
0x180008811  mov     ecx, 0C00000E5h
0x180008816  jmp     short loc_18000881D
0x180008818  mov     ecx, 0C000042Bh
0x18000881d  mov     eax, ecx
0x18000881f  retn
```
