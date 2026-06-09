# wil::details::HrToNtStatus(long)

- ea: `0x180007fbc`
- end: `0x180008178`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002138`
- `0x1800021e0`
- `0x180002230`
- `0x1800022e8`
- `0x180004bf4`
- `0x180008b20`

## callees

- `0x180007fbc`

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
0x180007fbc  mov     eax, 800700EAh
0x180007fc1  cmp     ecx, eax
0x180007fc3  jg      loc_180008098
0x180007fc9  jz      loc_18000808E
0x180007fcf  mov     eax, 80070057h
0x180007fd4  cmp     ecx, eax
0x180007fd6  jg      short loc_180008042
0x180007fd8  jz      short loc_180008038
0x180007fda  cmp     ecx, 80004005h
0x180007fe0  jz      short loc_18000802E
0x180007fe2  cmp     ecx, 80070001h
0x180007fe8  jz      short loc_180008024
0x180007fea  cmp     ecx, 80070002h
0x180007ff0  jz      short loc_18000801A
0x180007ff2  cmp     ecx, 80070003h
0x180007ff8  jz      short loc_180008010
0x180007ffa  cmp     ecx, 8007000Eh
0x180008000  jnz     loc_18000811D
0x180008006  mov     ecx, 0C0000017h
0x18000800b  jmp     loc_180008175
0x180008010  mov     ecx, 0C000003Ah
0x180008015  jmp     loc_180008175
0x18000801a  mov     ecx, 0C0000034h
0x18000801f  jmp     loc_180008175
0x180008024  mov     ecx, 0C0000002h
0x180008029  jmp     loc_180008175
0x18000802e  mov     ecx, 0C0000001h
0x180008033  jmp     loc_180008175
0x180008038  mov     ecx, 0C000000Dh
0x18000803d  jmp     loc_180008175
0x180008042  cmp     ecx, 80070070h
0x180008048  jz      short loc_180008084
0x18000804a  cmp     ecx, 8007007Ah
0x180008050  jz      short loc_18000807A
0x180008052  cmp     ecx, 8007007Bh
0x180008058  jz      short loc_180008070
0x18000805a  cmp     ecx, 8007007Eh
0x180008060  jnz     loc_18000811D
0x180008066  mov     ecx, 0C0000135h
0x18000806b  jmp     loc_180008175
0x180008070  mov     ecx, 0C0000033h
0x180008075  jmp     loc_180008175
0x18000807a  mov     ecx, 0C0000023h
0x18000807f  jmp     loc_180008175
0x180008084  mov     ecx, 0C000007Fh
0x180008089  jmp     loc_180008175
0x18000808e  mov     ecx, 80000005h
0x180008093  jmp     loc_180008175
0x180008098  mov     eax, 8007047Eh
0x18000809d  cmp     ecx, eax
0x18000809f  jg      short loc_180008101
0x1800080a1  jz      short loc_1800080FA
0x1800080a3  cmp     ecx, 80070216h
0x1800080a9  jz      short loc_1800080F3
0x1800080ab  cmp     ecx, 8007023Eh
0x1800080b1  jz      short loc_1800080E9
0x1800080b3  cmp     ecx, 80070246h
0x1800080b9  jz      short loc_1800080DF
0x1800080bb  cmp     ecx, 80070247h
0x1800080c1  jz      short loc_1800080D5
0x1800080c3  cmp     ecx, 80070272h
0x1800080c9  jnz     short loc_18000811D
0x1800080cb  mov     ecx, 0C0000273h
0x1800080d0  jmp     loc_180008175
0x1800080d5  mov     ecx, 0C0000163h
0x1800080da  jmp     loc_180008175
0x1800080df  mov     ecx, 0C0000161h
0x1800080e4  jmp     loc_180008175
0x1800080e9  mov     ecx, 0C0000025h
0x1800080ee  jmp     loc_180008175
0x1800080f3  mov     ecx, 0C0000095h
0x1800080f8  jmp     short loc_180008175
0x1800080fa  mov     ecx, 0C0000059h
0x1800080ff  jmp     short loc_180008175
0x180008101  cmp     ecx, 8007050Ch
0x180008107  jz      short loc_180008170
0x180008109  cmp     ecx, 8007054Fh
0x18000810f  jz      short loc_180008169
0x180008111  cmp     ecx, 800705B9h
0x180008117  jz      short loc_180008162
0x180008119  test    ecx, ecx
0x18000811b  jz      short loc_18000815E
0x18000811d  bt      ecx, 1Ch
0x180008121  jnb     short loc_180008129
0x180008123  btr     ecx, 1Ch
0x180008127  jmp     short loc_180008175
0x180008129  mov     eax, ecx
0x18000812b  and     eax, 1FFF0000h
0x180008130  cmp     eax, 70000h
0x180008135  jnz     short loc_180008148
0x180008137  movzx   ecx, cx
0x18000813a  mov     eax, ecx
0x18000813c  or      eax, 0C0070000h
0x180008141  test    ecx, ecx
0x180008143  cmovnz  ecx, eax
0x180008146  jmp     short loc_180008175
0x180008148  cmp     eax, 90000h
0x18000814d  jnz     short loc_180008169
0x18000814f  test    ecx, ecx
0x180008151  jle     short loc_180008175
0x180008153  movzx   ecx, cx
0x180008156  or      ecx, 0C0090000h
0x18000815c  jmp     short loc_180008175
0x18000815e  xor     ecx, ecx
0x180008160  jmp     short loc_180008175
0x180008162  mov     ecx, 0C000A083h
0x180008167  jmp     short loc_180008175
0x180008169  mov     ecx, 0C00000E5h
0x18000816e  jmp     short loc_180008175
0x180008170  mov     ecx, 0C000042Bh
0x180008175  mov     eax, ecx
0x180008177  retn
```
