# wil::details::HrToNtStatus(long)

- ea: `0x180018a90`
- end: `0x180018c4c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180016814`
- `0x18001688c`
- `0x1800168dc`
- `0x18001699c`
- `0x180018078`
- `0x180018d94`

## callees

- `0x180018a90`

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
0x180018a90  mov     eax, 800700EAh
0x180018a95  cmp     ecx, eax
0x180018a97  jg      loc_180018B6C
0x180018a9d  jz      loc_180018B62
0x180018aa3  mov     eax, 80070057h
0x180018aa8  cmp     ecx, eax
0x180018aaa  jg      short loc_180018B16
0x180018aac  jz      short loc_180018B0C
0x180018aae  cmp     ecx, 80004005h
0x180018ab4  jz      short loc_180018B02
0x180018ab6  cmp     ecx, 80070001h
0x180018abc  jz      short loc_180018AF8
0x180018abe  cmp     ecx, 80070002h
0x180018ac4  jz      short loc_180018AEE
0x180018ac6  cmp     ecx, 80070003h
0x180018acc  jz      short loc_180018AE4
0x180018ace  cmp     ecx, 8007000Eh
0x180018ad4  jnz     loc_180018BF1
0x180018ada  mov     ecx, 0C0000017h
0x180018adf  jmp     loc_180018C49
0x180018ae4  mov     ecx, 0C000003Ah
0x180018ae9  jmp     loc_180018C49
0x180018aee  mov     ecx, 0C0000034h
0x180018af3  jmp     loc_180018C49
0x180018af8  mov     ecx, 0C0000002h
0x180018afd  jmp     loc_180018C49
0x180018b02  mov     ecx, 0C0000001h
0x180018b07  jmp     loc_180018C49
0x180018b0c  mov     ecx, 0C000000Dh
0x180018b11  jmp     loc_180018C49
0x180018b16  cmp     ecx, 80070070h
0x180018b1c  jz      short loc_180018B58
0x180018b1e  cmp     ecx, 8007007Ah
0x180018b24  jz      short loc_180018B4E
0x180018b26  cmp     ecx, 8007007Bh
0x180018b2c  jz      short loc_180018B44
0x180018b2e  cmp     ecx, 8007007Eh
0x180018b34  jnz     loc_180018BF1
0x180018b3a  mov     ecx, 0C0000135h
0x180018b3f  jmp     loc_180018C49
0x180018b44  mov     ecx, 0C0000033h
0x180018b49  jmp     loc_180018C49
0x180018b4e  mov     ecx, 0C0000023h
0x180018b53  jmp     loc_180018C49
0x180018b58  mov     ecx, 0C000007Fh
0x180018b5d  jmp     loc_180018C49
0x180018b62  mov     ecx, 80000005h
0x180018b67  jmp     loc_180018C49
0x180018b6c  mov     eax, 8007047Eh
0x180018b71  cmp     ecx, eax
0x180018b73  jg      short loc_180018BD5
0x180018b75  jz      short loc_180018BCE
0x180018b77  cmp     ecx, 80070216h
0x180018b7d  jz      short loc_180018BC7
0x180018b7f  cmp     ecx, 8007023Eh
0x180018b85  jz      short loc_180018BBD
0x180018b87  cmp     ecx, 80070246h
0x180018b8d  jz      short loc_180018BB3
0x180018b8f  cmp     ecx, 80070247h
0x180018b95  jz      short loc_180018BA9
0x180018b97  cmp     ecx, 80070272h
0x180018b9d  jnz     short loc_180018BF1
0x180018b9f  mov     ecx, 0C0000273h
0x180018ba4  jmp     loc_180018C49
0x180018ba9  mov     ecx, 0C0000163h
0x180018bae  jmp     loc_180018C49
0x180018bb3  mov     ecx, 0C0000161h
0x180018bb8  jmp     loc_180018C49
0x180018bbd  mov     ecx, 0C0000025h
0x180018bc2  jmp     loc_180018C49
0x180018bc7  mov     ecx, 0C0000095h
0x180018bcc  jmp     short loc_180018C49
0x180018bce  mov     ecx, 0C0000059h
0x180018bd3  jmp     short loc_180018C49
0x180018bd5  cmp     ecx, 8007050Ch
0x180018bdb  jz      short loc_180018C44
0x180018bdd  cmp     ecx, 8007054Fh
0x180018be3  jz      short loc_180018C3D
0x180018be5  cmp     ecx, 800705B9h
0x180018beb  jz      short loc_180018C36
0x180018bed  test    ecx, ecx
0x180018bef  jz      short loc_180018C32
0x180018bf1  bt      ecx, 1Ch
0x180018bf5  jnb     short loc_180018BFD
0x180018bf7  btr     ecx, 1Ch
0x180018bfb  jmp     short loc_180018C49
0x180018bfd  mov     eax, ecx
0x180018bff  and     eax, 1FFF0000h
0x180018c04  cmp     eax, 70000h
0x180018c09  jnz     short loc_180018C1C
0x180018c0b  movzx   ecx, cx
0x180018c0e  mov     eax, ecx
0x180018c10  or      eax, 0C0070000h
0x180018c15  test    ecx, ecx
0x180018c17  cmovnz  ecx, eax
0x180018c1a  jmp     short loc_180018C49
0x180018c1c  cmp     eax, 90000h
0x180018c21  jnz     short loc_180018C3D
0x180018c23  test    ecx, ecx
0x180018c25  jle     short loc_180018C49
0x180018c27  movzx   ecx, cx
0x180018c2a  or      ecx, 0C0090000h
0x180018c30  jmp     short loc_180018C49
0x180018c32  xor     ecx, ecx
0x180018c34  jmp     short loc_180018C49
0x180018c36  mov     ecx, 0C000A083h
0x180018c3b  jmp     short loc_180018C49
0x180018c3d  mov     ecx, 0C00000E5h
0x180018c42  jmp     short loc_180018C49
0x180018c44  mov     ecx, 0C000042Bh
0x180018c49  mov     eax, ecx
0x180018c4b  retn
```
