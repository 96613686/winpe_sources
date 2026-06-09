# wil::details::HrToNtStatus(long)

- ea: `0x18001b05c`
- end: `0x18001b218`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180019048`
- `0x1800190e8`
- `0x180019138`
- `0x1800191f0`
- `0x18001a538`
- `0x18001b220`

## callees

- `0x18001b05c`

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
0x18001b05c  mov     eax, 800700EAh
0x18001b061  cmp     ecx, eax
0x18001b063  jg      loc_18001B138
0x18001b069  jz      loc_18001B12E
0x18001b06f  mov     eax, 80070057h
0x18001b074  cmp     ecx, eax
0x18001b076  jg      short loc_18001B0E2
0x18001b078  jz      short loc_18001B0D8
0x18001b07a  cmp     ecx, 80004005h
0x18001b080  jz      short loc_18001B0CE
0x18001b082  cmp     ecx, 80070001h
0x18001b088  jz      short loc_18001B0C4
0x18001b08a  cmp     ecx, 80070002h
0x18001b090  jz      short loc_18001B0BA
0x18001b092  cmp     ecx, 80070003h
0x18001b098  jz      short loc_18001B0B0
0x18001b09a  cmp     ecx, 8007000Eh
0x18001b0a0  jnz     loc_18001B1BD
0x18001b0a6  mov     ecx, 0C0000017h
0x18001b0ab  jmp     loc_18001B215
0x18001b0b0  mov     ecx, 0C000003Ah
0x18001b0b5  jmp     loc_18001B215
0x18001b0ba  mov     ecx, 0C0000034h
0x18001b0bf  jmp     loc_18001B215
0x18001b0c4  mov     ecx, 0C0000002h
0x18001b0c9  jmp     loc_18001B215
0x18001b0ce  mov     ecx, 0C0000001h
0x18001b0d3  jmp     loc_18001B215
0x18001b0d8  mov     ecx, 0C000000Dh
0x18001b0dd  jmp     loc_18001B215
0x18001b0e2  cmp     ecx, 80070070h
0x18001b0e8  jz      short loc_18001B124
0x18001b0ea  cmp     ecx, 8007007Ah
0x18001b0f0  jz      short loc_18001B11A
0x18001b0f2  cmp     ecx, 8007007Bh
0x18001b0f8  jz      short loc_18001B110
0x18001b0fa  cmp     ecx, 8007007Eh
0x18001b100  jnz     loc_18001B1BD
0x18001b106  mov     ecx, 0C0000135h
0x18001b10b  jmp     loc_18001B215
0x18001b110  mov     ecx, 0C0000033h
0x18001b115  jmp     loc_18001B215
0x18001b11a  mov     ecx, 0C0000023h
0x18001b11f  jmp     loc_18001B215
0x18001b124  mov     ecx, 0C000007Fh
0x18001b129  jmp     loc_18001B215
0x18001b12e  mov     ecx, 80000005h
0x18001b133  jmp     loc_18001B215
0x18001b138  mov     eax, 8007047Eh
0x18001b13d  cmp     ecx, eax
0x18001b13f  jg      short loc_18001B1A1
0x18001b141  jz      short loc_18001B19A
0x18001b143  cmp     ecx, 80070216h
0x18001b149  jz      short loc_18001B193
0x18001b14b  cmp     ecx, 8007023Eh
0x18001b151  jz      short loc_18001B189
0x18001b153  cmp     ecx, 80070246h
0x18001b159  jz      short loc_18001B17F
0x18001b15b  cmp     ecx, 80070247h
0x18001b161  jz      short loc_18001B175
0x18001b163  cmp     ecx, 80070272h
0x18001b169  jnz     short loc_18001B1BD
0x18001b16b  mov     ecx, 0C0000273h
0x18001b170  jmp     loc_18001B215
0x18001b175  mov     ecx, 0C0000163h
0x18001b17a  jmp     loc_18001B215
0x18001b17f  mov     ecx, 0C0000161h
0x18001b184  jmp     loc_18001B215
0x18001b189  mov     ecx, 0C0000025h
0x18001b18e  jmp     loc_18001B215
0x18001b193  mov     ecx, 0C0000095h
0x18001b198  jmp     short loc_18001B215
0x18001b19a  mov     ecx, 0C0000059h
0x18001b19f  jmp     short loc_18001B215
0x18001b1a1  cmp     ecx, 8007050Ch
0x18001b1a7  jz      short loc_18001B210
0x18001b1a9  cmp     ecx, 8007054Fh
0x18001b1af  jz      short loc_18001B209
0x18001b1b1  cmp     ecx, 800705B9h
0x18001b1b7  jz      short loc_18001B202
0x18001b1b9  test    ecx, ecx
0x18001b1bb  jz      short loc_18001B1FE
0x18001b1bd  bt      ecx, 1Ch
0x18001b1c1  jnb     short loc_18001B1C9
0x18001b1c3  btr     ecx, 1Ch
0x18001b1c7  jmp     short loc_18001B215
0x18001b1c9  mov     eax, ecx
0x18001b1cb  and     eax, 1FFF0000h
0x18001b1d0  cmp     eax, 70000h
0x18001b1d5  jnz     short loc_18001B1E8
0x18001b1d7  movzx   ecx, cx
0x18001b1da  mov     eax, ecx
0x18001b1dc  or      eax, 0C0070000h
0x18001b1e1  test    ecx, ecx
0x18001b1e3  cmovnz  ecx, eax
0x18001b1e6  jmp     short loc_18001B215
0x18001b1e8  cmp     eax, 90000h
0x18001b1ed  jnz     short loc_18001B209
0x18001b1ef  test    ecx, ecx
0x18001b1f1  jle     short loc_18001B215
0x18001b1f3  movzx   ecx, cx
0x18001b1f6  or      ecx, 0C0090000h
0x18001b1fc  jmp     short loc_18001B215
0x18001b1fe  xor     ecx, ecx
0x18001b200  jmp     short loc_18001B215
0x18001b202  mov     ecx, 0C000A083h
0x18001b207  jmp     short loc_18001B215
0x18001b209  mov     ecx, 0C00000E5h
0x18001b20e  jmp     short loc_18001B215
0x18001b210  mov     ecx, 0C000042Bh
0x18001b215  mov     eax, ecx
0x18001b217  retn
```
