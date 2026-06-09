# wil::details::HrToNtStatus(long)

- ea: `0x180004374`
- end: `0x180004530`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c24`
- `0x180002c98`
- `0x180002d1c`
- `0x180002d74`
- `0x180002dd8`
- `0x180004538`
- `0x180004e10`
- `0x180005f4c`
- `0x1800080ac`
- `0x180008220`
- `0x180009810`
- `0x180009918`
- `0x18000bd29`
- `0x18000bd74`
- `0x18000be37`
- `0x18000be82`

## callees

- `0x180004374`

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
0x180004374  mov     eax, 800700EAh
0x180004379  cmp     ecx, eax
0x18000437b  jg      loc_180004450
0x180004381  jz      loc_180004446
0x180004387  mov     eax, 80070057h
0x18000438c  cmp     ecx, eax
0x18000438e  jg      short loc_1800043FA
0x180004390  jz      short loc_1800043F0
0x180004392  cmp     ecx, 80004005h
0x180004398  jz      short loc_1800043E6
0x18000439a  cmp     ecx, 80070001h
0x1800043a0  jz      short loc_1800043DC
0x1800043a2  cmp     ecx, 80070002h
0x1800043a8  jz      short loc_1800043D2
0x1800043aa  cmp     ecx, 80070003h
0x1800043b0  jz      short loc_1800043C8
0x1800043b2  cmp     ecx, 8007000Eh
0x1800043b8  jnz     loc_1800044D5
0x1800043be  mov     ecx, 0C0000017h
0x1800043c3  jmp     loc_18000452D
0x1800043c8  mov     ecx, 0C000003Ah
0x1800043cd  jmp     loc_18000452D
0x1800043d2  mov     ecx, 0C0000034h
0x1800043d7  jmp     loc_18000452D
0x1800043dc  mov     ecx, 0C0000002h
0x1800043e1  jmp     loc_18000452D
0x1800043e6  mov     ecx, 0C0000001h
0x1800043eb  jmp     loc_18000452D
0x1800043f0  mov     ecx, 0C000000Dh
0x1800043f5  jmp     loc_18000452D
0x1800043fa  cmp     ecx, 80070070h
0x180004400  jz      short loc_18000443C
0x180004402  cmp     ecx, 8007007Ah
0x180004408  jz      short loc_180004432
0x18000440a  cmp     ecx, 8007007Bh
0x180004410  jz      short loc_180004428
0x180004412  cmp     ecx, 8007007Eh
0x180004418  jnz     loc_1800044D5
0x18000441e  mov     ecx, 0C0000135h
0x180004423  jmp     loc_18000452D
0x180004428  mov     ecx, 0C0000033h
0x18000442d  jmp     loc_18000452D
0x180004432  mov     ecx, 0C0000023h
0x180004437  jmp     loc_18000452D
0x18000443c  mov     ecx, 0C000007Fh
0x180004441  jmp     loc_18000452D
0x180004446  mov     ecx, 80000005h
0x18000444b  jmp     loc_18000452D
0x180004450  mov     eax, 8007047Eh
0x180004455  cmp     ecx, eax
0x180004457  jg      short loc_1800044B9
0x180004459  jz      short loc_1800044B2
0x18000445b  cmp     ecx, 80070216h
0x180004461  jz      short loc_1800044AB
0x180004463  cmp     ecx, 8007023Eh
0x180004469  jz      short loc_1800044A1
0x18000446b  cmp     ecx, 80070246h
0x180004471  jz      short loc_180004497
0x180004473  cmp     ecx, 80070247h
0x180004479  jz      short loc_18000448D
0x18000447b  cmp     ecx, 80070272h
0x180004481  jnz     short loc_1800044D5
0x180004483  mov     ecx, 0C0000273h
0x180004488  jmp     loc_18000452D
0x18000448d  mov     ecx, 0C0000163h
0x180004492  jmp     loc_18000452D
0x180004497  mov     ecx, 0C0000161h
0x18000449c  jmp     loc_18000452D
0x1800044a1  mov     ecx, 0C0000025h
0x1800044a6  jmp     loc_18000452D
0x1800044ab  mov     ecx, 0C0000095h
0x1800044b0  jmp     short loc_18000452D
0x1800044b2  mov     ecx, 0C0000059h
0x1800044b7  jmp     short loc_18000452D
0x1800044b9  cmp     ecx, 8007050Ch
0x1800044bf  jz      short loc_180004528
0x1800044c1  cmp     ecx, 8007054Fh
0x1800044c7  jz      short loc_180004521
0x1800044c9  cmp     ecx, 800705B9h
0x1800044cf  jz      short loc_18000451A
0x1800044d1  test    ecx, ecx
0x1800044d3  jz      short loc_180004516
0x1800044d5  bt      ecx, 1Ch
0x1800044d9  jnb     short loc_1800044E1
0x1800044db  btr     ecx, 1Ch
0x1800044df  jmp     short loc_18000452D
0x1800044e1  mov     eax, ecx
0x1800044e3  and     eax, 1FFF0000h
0x1800044e8  cmp     eax, 70000h
0x1800044ed  jnz     short loc_180004500
0x1800044ef  movzx   ecx, cx
0x1800044f2  mov     eax, ecx
0x1800044f4  or      eax, 0C0070000h
0x1800044f9  test    ecx, ecx
0x1800044fb  cmovnz  ecx, eax
0x1800044fe  jmp     short loc_18000452D
0x180004500  cmp     eax, 90000h
0x180004505  jnz     short loc_180004521
0x180004507  test    ecx, ecx
0x180004509  jle     short loc_18000452D
0x18000450b  movzx   ecx, cx
0x18000450e  or      ecx, 0C0090000h
0x180004514  jmp     short loc_18000452D
0x180004516  xor     ecx, ecx
0x180004518  jmp     short loc_18000452D
0x18000451a  mov     ecx, 0C000A083h
0x18000451f  jmp     short loc_18000452D
0x180004521  mov     ecx, 0C00000E5h
0x180004526  jmp     short loc_18000452D
0x180004528  mov     ecx, 0C000042Bh
0x18000452d  mov     eax, ecx
0x18000452f  retn
```
