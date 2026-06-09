# wil::details::HrToNtStatus(long)

- ea: `0x1400044a0`
- end: `0x14000465c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000304c`
- `0x1400030ec`
- `0x14000313c`
- `0x1400031fc`
- `0x140003fb0`
- `0x140004664`

## callees

- `0x1400044a0`

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
0x1400044a0  mov     eax, 800700EAh
0x1400044a5  cmp     ecx, eax
0x1400044a7  jg      loc_14000457C
0x1400044ad  jz      loc_140004572
0x1400044b3  mov     eax, 80070057h
0x1400044b8  cmp     ecx, eax
0x1400044ba  jg      short loc_140004526
0x1400044bc  jz      short loc_14000451C
0x1400044be  cmp     ecx, 80004005h
0x1400044c4  jz      short loc_140004512
0x1400044c6  cmp     ecx, 80070001h
0x1400044cc  jz      short loc_140004508
0x1400044ce  cmp     ecx, 80070002h
0x1400044d4  jz      short loc_1400044FE
0x1400044d6  cmp     ecx, 80070003h
0x1400044dc  jz      short loc_1400044F4
0x1400044de  cmp     ecx, 8007000Eh
0x1400044e4  jnz     loc_140004601
0x1400044ea  mov     ecx, 0C0000017h
0x1400044ef  jmp     loc_140004659
0x1400044f4  mov     ecx, 0C000003Ah
0x1400044f9  jmp     loc_140004659
0x1400044fe  mov     ecx, 0C0000034h
0x140004503  jmp     loc_140004659
0x140004508  mov     ecx, 0C0000002h
0x14000450d  jmp     loc_140004659
0x140004512  mov     ecx, 0C0000001h
0x140004517  jmp     loc_140004659
0x14000451c  mov     ecx, 0C000000Dh
0x140004521  jmp     loc_140004659
0x140004526  cmp     ecx, 80070070h
0x14000452c  jz      short loc_140004568
0x14000452e  cmp     ecx, 8007007Ah
0x140004534  jz      short loc_14000455E
0x140004536  cmp     ecx, 8007007Bh
0x14000453c  jz      short loc_140004554
0x14000453e  cmp     ecx, 8007007Eh
0x140004544  jnz     loc_140004601
0x14000454a  mov     ecx, 0C0000135h
0x14000454f  jmp     loc_140004659
0x140004554  mov     ecx, 0C0000033h
0x140004559  jmp     loc_140004659
0x14000455e  mov     ecx, 0C0000023h
0x140004563  jmp     loc_140004659
0x140004568  mov     ecx, 0C000007Fh
0x14000456d  jmp     loc_140004659
0x140004572  mov     ecx, 80000005h
0x140004577  jmp     loc_140004659
0x14000457c  mov     eax, 8007047Eh
0x140004581  cmp     ecx, eax
0x140004583  jg      short loc_1400045E5
0x140004585  jz      short loc_1400045DE
0x140004587  cmp     ecx, 80070216h
0x14000458d  jz      short loc_1400045D7
0x14000458f  cmp     ecx, 8007023Eh
0x140004595  jz      short loc_1400045CD
0x140004597  cmp     ecx, 80070246h
0x14000459d  jz      short loc_1400045C3
0x14000459f  cmp     ecx, 80070247h
0x1400045a5  jz      short loc_1400045B9
0x1400045a7  cmp     ecx, 80070272h
0x1400045ad  jnz     short loc_140004601
0x1400045af  mov     ecx, 0C0000273h
0x1400045b4  jmp     loc_140004659
0x1400045b9  mov     ecx, 0C0000163h
0x1400045be  jmp     loc_140004659
0x1400045c3  mov     ecx, 0C0000161h
0x1400045c8  jmp     loc_140004659
0x1400045cd  mov     ecx, 0C0000025h
0x1400045d2  jmp     loc_140004659
0x1400045d7  mov     ecx, 0C0000095h
0x1400045dc  jmp     short loc_140004659
0x1400045de  mov     ecx, 0C0000059h
0x1400045e3  jmp     short loc_140004659
0x1400045e5  cmp     ecx, 8007050Ch
0x1400045eb  jz      short loc_140004654
0x1400045ed  cmp     ecx, 8007054Fh
0x1400045f3  jz      short loc_14000464D
0x1400045f5  cmp     ecx, 800705B9h
0x1400045fb  jz      short loc_140004646
0x1400045fd  test    ecx, ecx
0x1400045ff  jz      short loc_140004642
0x140004601  bt      ecx, 1Ch
0x140004605  jnb     short loc_14000460D
0x140004607  btr     ecx, 1Ch
0x14000460b  jmp     short loc_140004659
0x14000460d  mov     eax, ecx
0x14000460f  and     eax, 1FFF0000h
0x140004614  cmp     eax, 70000h
0x140004619  jnz     short loc_14000462C
0x14000461b  movzx   ecx, cx
0x14000461e  mov     eax, ecx
0x140004620  or      eax, 0C0070000h
0x140004625  test    ecx, ecx
0x140004627  cmovnz  ecx, eax
0x14000462a  jmp     short loc_140004659
0x14000462c  cmp     eax, 90000h
0x140004631  jnz     short loc_14000464D
0x140004633  test    ecx, ecx
0x140004635  jle     short loc_140004659
0x140004637  movzx   ecx, cx
0x14000463a  or      ecx, 0C0090000h
0x140004640  jmp     short loc_140004659
0x140004642  xor     ecx, ecx
0x140004644  jmp     short loc_140004659
0x140004646  mov     ecx, 0C000A083h
0x14000464b  jmp     short loc_140004659
0x14000464d  mov     ecx, 0C00000E5h
0x140004652  jmp     short loc_140004659
0x140004654  mov     ecx, 0C000042Bh
0x140004659  mov     eax, ecx
0x14000465b  retn
```
