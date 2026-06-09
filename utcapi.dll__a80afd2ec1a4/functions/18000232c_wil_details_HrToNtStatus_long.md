# wil::details::HrToNtStatus(long)

- ea: `0x18000232c`
- end: `0x1800024e8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d50`

## callees

- `0x18000232c`

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
0x18000232c  mov     eax, 800700EAh
0x180002331  cmp     ecx, eax
0x180002333  jg      loc_180002408
0x180002339  jz      loc_1800023FE
0x18000233f  mov     eax, 80070057h
0x180002344  cmp     ecx, eax
0x180002346  jg      short loc_1800023B2
0x180002348  jz      short loc_1800023A8
0x18000234a  cmp     ecx, 80004005h
0x180002350  jz      short loc_18000239E
0x180002352  cmp     ecx, 80070001h
0x180002358  jz      short loc_180002394
0x18000235a  cmp     ecx, 80070002h
0x180002360  jz      short loc_18000238A
0x180002362  cmp     ecx, 80070003h
0x180002368  jz      short loc_180002380
0x18000236a  cmp     ecx, 8007000Eh
0x180002370  jnz     loc_18000248D
0x180002376  mov     ecx, 0C0000017h
0x18000237b  jmp     loc_1800024E5
0x180002380  mov     ecx, 0C000003Ah
0x180002385  jmp     loc_1800024E5
0x18000238a  mov     ecx, 0C0000034h
0x18000238f  jmp     loc_1800024E5
0x180002394  mov     ecx, 0C0000002h
0x180002399  jmp     loc_1800024E5
0x18000239e  mov     ecx, 0C0000001h
0x1800023a3  jmp     loc_1800024E5
0x1800023a8  mov     ecx, 0C000000Dh
0x1800023ad  jmp     loc_1800024E5
0x1800023b2  cmp     ecx, 80070070h
0x1800023b8  jz      short loc_1800023F4
0x1800023ba  cmp     ecx, 8007007Ah
0x1800023c0  jz      short loc_1800023EA
0x1800023c2  cmp     ecx, 8007007Bh
0x1800023c8  jz      short loc_1800023E0
0x1800023ca  cmp     ecx, 8007007Eh
0x1800023d0  jnz     loc_18000248D
0x1800023d6  mov     ecx, 0C0000135h
0x1800023db  jmp     loc_1800024E5
0x1800023e0  mov     ecx, 0C0000033h
0x1800023e5  jmp     loc_1800024E5
0x1800023ea  mov     ecx, 0C0000023h
0x1800023ef  jmp     loc_1800024E5
0x1800023f4  mov     ecx, 0C000007Fh
0x1800023f9  jmp     loc_1800024E5
0x1800023fe  mov     ecx, 80000005h
0x180002403  jmp     loc_1800024E5
0x180002408  mov     eax, 8007047Eh
0x18000240d  cmp     ecx, eax
0x18000240f  jg      short loc_180002471
0x180002411  jz      short loc_18000246A
0x180002413  cmp     ecx, 80070216h
0x180002419  jz      short loc_180002463
0x18000241b  cmp     ecx, 8007023Eh
0x180002421  jz      short loc_180002459
0x180002423  cmp     ecx, 80070246h
0x180002429  jz      short loc_18000244F
0x18000242b  cmp     ecx, 80070247h
0x180002431  jz      short loc_180002445
0x180002433  cmp     ecx, 80070272h
0x180002439  jnz     short loc_18000248D
0x18000243b  mov     ecx, 0C0000273h
0x180002440  jmp     loc_1800024E5
0x180002445  mov     ecx, 0C0000163h
0x18000244a  jmp     loc_1800024E5
0x18000244f  mov     ecx, 0C0000161h
0x180002454  jmp     loc_1800024E5
0x180002459  mov     ecx, 0C0000025h
0x18000245e  jmp     loc_1800024E5
0x180002463  mov     ecx, 0C0000095h
0x180002468  jmp     short loc_1800024E5
0x18000246a  mov     ecx, 0C0000059h
0x18000246f  jmp     short loc_1800024E5
0x180002471  cmp     ecx, 8007050Ch
0x180002477  jz      short loc_1800024E0
0x180002479  cmp     ecx, 8007054Fh
0x18000247f  jz      short loc_1800024D9
0x180002481  cmp     ecx, 800705B9h
0x180002487  jz      short loc_1800024D2
0x180002489  test    ecx, ecx
0x18000248b  jz      short loc_1800024CE
0x18000248d  bt      ecx, 1Ch
0x180002491  jnb     short loc_180002499
0x180002493  btr     ecx, 1Ch
0x180002497  jmp     short loc_1800024E5
0x180002499  mov     eax, ecx
0x18000249b  and     eax, 1FFF0000h
0x1800024a0  cmp     eax, 70000h
0x1800024a5  jnz     short loc_1800024B8
0x1800024a7  movzx   ecx, cx
0x1800024aa  mov     eax, ecx
0x1800024ac  or      eax, 0C0070000h
0x1800024b1  test    ecx, ecx
0x1800024b3  cmovnz  ecx, eax
0x1800024b6  jmp     short loc_1800024E5
0x1800024b8  cmp     eax, 90000h
0x1800024bd  jnz     short loc_1800024D9
0x1800024bf  test    ecx, ecx
0x1800024c1  jle     short loc_1800024E5
0x1800024c3  movzx   ecx, cx
0x1800024c6  or      ecx, 0C0090000h
0x1800024cc  jmp     short loc_1800024E5
0x1800024ce  xor     ecx, ecx
0x1800024d0  jmp     short loc_1800024E5
0x1800024d2  mov     ecx, 0C000A083h
0x1800024d7  jmp     short loc_1800024E5
0x1800024d9  mov     ecx, 0C00000E5h
0x1800024de  jmp     short loc_1800024E5
0x1800024e0  mov     ecx, 0C000042Bh
0x1800024e5  mov     eax, ecx
0x1800024e7  retn
```
