# wil::details::HrToNtStatus(long)

- ea: `0x1800060f0`
- end: `0x1800062ac`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180003040`
- `0x180003184`
- `0x1800033d0`
- `0x180003480`
- `0x1800034d8`
- `0x1800035fc`
- `0x18000574c`
- `0x180006468`
- `0x180008ea0`
- `0x18000f4e3`
- `0x18000f54e`
- `0x18000f617`
- `0x18000f682`

## callees

- `0x1800060f0`

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
0x1800060f0  mov     eax, 800700EAh
0x1800060f5  cmp     ecx, eax
0x1800060f7  jg      loc_1800061CC
0x1800060fd  jz      loc_1800061C2
0x180006103  mov     eax, 80070057h
0x180006108  cmp     ecx, eax
0x18000610a  jg      short loc_180006176
0x18000610c  jz      short loc_18000616C
0x18000610e  cmp     ecx, 80004005h
0x180006114  jz      short loc_180006162
0x180006116  cmp     ecx, 80070001h
0x18000611c  jz      short loc_180006158
0x18000611e  cmp     ecx, 80070002h
0x180006124  jz      short loc_18000614E
0x180006126  cmp     ecx, 80070003h
0x18000612c  jz      short loc_180006144
0x18000612e  cmp     ecx, 8007000Eh
0x180006134  jnz     loc_180006251
0x18000613a  mov     ecx, 0C0000017h
0x18000613f  jmp     loc_1800062A9
0x180006144  mov     ecx, 0C000003Ah
0x180006149  jmp     loc_1800062A9
0x18000614e  mov     ecx, 0C0000034h
0x180006153  jmp     loc_1800062A9
0x180006158  mov     ecx, 0C0000002h
0x18000615d  jmp     loc_1800062A9
0x180006162  mov     ecx, 0C0000001h
0x180006167  jmp     loc_1800062A9
0x18000616c  mov     ecx, 0C000000Dh
0x180006171  jmp     loc_1800062A9
0x180006176  cmp     ecx, 80070070h
0x18000617c  jz      short loc_1800061B8
0x18000617e  cmp     ecx, 8007007Ah
0x180006184  jz      short loc_1800061AE
0x180006186  cmp     ecx, 8007007Bh
0x18000618c  jz      short loc_1800061A4
0x18000618e  cmp     ecx, 8007007Eh
0x180006194  jnz     loc_180006251
0x18000619a  mov     ecx, 0C0000135h
0x18000619f  jmp     loc_1800062A9
0x1800061a4  mov     ecx, 0C0000033h
0x1800061a9  jmp     loc_1800062A9
0x1800061ae  mov     ecx, 0C0000023h
0x1800061b3  jmp     loc_1800062A9
0x1800061b8  mov     ecx, 0C000007Fh
0x1800061bd  jmp     loc_1800062A9
0x1800061c2  mov     ecx, 80000005h
0x1800061c7  jmp     loc_1800062A9
0x1800061cc  mov     eax, 8007047Eh
0x1800061d1  cmp     ecx, eax
0x1800061d3  jg      short loc_180006235
0x1800061d5  jz      short loc_18000622E
0x1800061d7  cmp     ecx, 80070216h
0x1800061dd  jz      short loc_180006227
0x1800061df  cmp     ecx, 8007023Eh
0x1800061e5  jz      short loc_18000621D
0x1800061e7  cmp     ecx, 80070246h
0x1800061ed  jz      short loc_180006213
0x1800061ef  cmp     ecx, 80070247h
0x1800061f5  jz      short loc_180006209
0x1800061f7  cmp     ecx, 80070272h
0x1800061fd  jnz     short loc_180006251
0x1800061ff  mov     ecx, 0C0000273h
0x180006204  jmp     loc_1800062A9
0x180006209  mov     ecx, 0C0000163h
0x18000620e  jmp     loc_1800062A9
0x180006213  mov     ecx, 0C0000161h
0x180006218  jmp     loc_1800062A9
0x18000621d  mov     ecx, 0C0000025h
0x180006222  jmp     loc_1800062A9
0x180006227  mov     ecx, 0C0000095h
0x18000622c  jmp     short loc_1800062A9
0x18000622e  mov     ecx, 0C0000059h
0x180006233  jmp     short loc_1800062A9
0x180006235  cmp     ecx, 8007050Ch
0x18000623b  jz      short loc_1800062A4
0x18000623d  cmp     ecx, 8007054Fh
0x180006243  jz      short loc_18000629D
0x180006245  cmp     ecx, 800705B9h
0x18000624b  jz      short loc_180006296
0x18000624d  test    ecx, ecx
0x18000624f  jz      short loc_180006292
0x180006251  bt      ecx, 1Ch
0x180006255  jnb     short loc_18000625D
0x180006257  btr     ecx, 1Ch
0x18000625b  jmp     short loc_1800062A9
0x18000625d  mov     eax, ecx
0x18000625f  and     eax, 1FFF0000h
0x180006264  cmp     eax, 70000h
0x180006269  jnz     short loc_18000627C
0x18000626b  movzx   ecx, cx
0x18000626e  mov     eax, ecx
0x180006270  or      eax, 0C0070000h
0x180006275  test    ecx, ecx
0x180006277  cmovnz  ecx, eax
0x18000627a  jmp     short loc_1800062A9
0x18000627c  cmp     eax, 90000h
0x180006281  jnz     short loc_18000629D
0x180006283  test    ecx, ecx
0x180006285  jle     short loc_1800062A9
0x180006287  movzx   ecx, cx
0x18000628a  or      ecx, 0C0090000h
0x180006290  jmp     short loc_1800062A9
0x180006292  xor     ecx, ecx
0x180006294  jmp     short loc_1800062A9
0x180006296  mov     ecx, 0C000A083h
0x18000629b  jmp     short loc_1800062A9
0x18000629d  mov     ecx, 0C00000E5h
0x1800062a2  jmp     short loc_1800062A9
0x1800062a4  mov     ecx, 0C000042Bh
0x1800062a9  mov     eax, ecx
0x1800062ab  retn
```
