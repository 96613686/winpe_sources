# wil::details::HrToNtStatus(long)

- ea: `0x140004b0c`
- end: `0x140004cc8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002ca4`
- `0x140002d44`
- `0x140002d94`
- `0x140002e54`
- `0x1400040d8`
- `0x140004f10`

## callees

- `0x140004b0c`

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
0x140004b0c  mov     eax, 800700EAh
0x140004b11  cmp     ecx, eax
0x140004b13  jg      loc_140004BE8
0x140004b19  jz      loc_140004BDE
0x140004b1f  mov     eax, 80070057h
0x140004b24  cmp     ecx, eax
0x140004b26  jg      short loc_140004B92
0x140004b28  jz      short loc_140004B88
0x140004b2a  cmp     ecx, 80004005h
0x140004b30  jz      short loc_140004B7E
0x140004b32  cmp     ecx, 80070001h
0x140004b38  jz      short loc_140004B74
0x140004b3a  cmp     ecx, 80070002h
0x140004b40  jz      short loc_140004B6A
0x140004b42  cmp     ecx, 80070003h
0x140004b48  jz      short loc_140004B60
0x140004b4a  cmp     ecx, 8007000Eh
0x140004b50  jnz     loc_140004C6D
0x140004b56  mov     ecx, 0C0000017h
0x140004b5b  jmp     loc_140004CC5
0x140004b60  mov     ecx, 0C000003Ah
0x140004b65  jmp     loc_140004CC5
0x140004b6a  mov     ecx, 0C0000034h
0x140004b6f  jmp     loc_140004CC5
0x140004b74  mov     ecx, 0C0000002h
0x140004b79  jmp     loc_140004CC5
0x140004b7e  mov     ecx, 0C0000001h
0x140004b83  jmp     loc_140004CC5
0x140004b88  mov     ecx, 0C000000Dh
0x140004b8d  jmp     loc_140004CC5
0x140004b92  cmp     ecx, 80070070h
0x140004b98  jz      short loc_140004BD4
0x140004b9a  cmp     ecx, 8007007Ah
0x140004ba0  jz      short loc_140004BCA
0x140004ba2  cmp     ecx, 8007007Bh
0x140004ba8  jz      short loc_140004BC0
0x140004baa  cmp     ecx, 8007007Eh
0x140004bb0  jnz     loc_140004C6D
0x140004bb6  mov     ecx, 0C0000135h
0x140004bbb  jmp     loc_140004CC5
0x140004bc0  mov     ecx, 0C0000033h
0x140004bc5  jmp     loc_140004CC5
0x140004bca  mov     ecx, 0C0000023h
0x140004bcf  jmp     loc_140004CC5
0x140004bd4  mov     ecx, 0C000007Fh
0x140004bd9  jmp     loc_140004CC5
0x140004bde  mov     ecx, 80000005h
0x140004be3  jmp     loc_140004CC5
0x140004be8  mov     eax, 8007047Eh
0x140004bed  cmp     ecx, eax
0x140004bef  jg      short loc_140004C51
0x140004bf1  jz      short loc_140004C4A
0x140004bf3  cmp     ecx, 80070216h
0x140004bf9  jz      short loc_140004C43
0x140004bfb  cmp     ecx, 8007023Eh
0x140004c01  jz      short loc_140004C39
0x140004c03  cmp     ecx, 80070246h
0x140004c09  jz      short loc_140004C2F
0x140004c0b  cmp     ecx, 80070247h
0x140004c11  jz      short loc_140004C25
0x140004c13  cmp     ecx, 80070272h
0x140004c19  jnz     short loc_140004C6D
0x140004c1b  mov     ecx, 0C0000273h
0x140004c20  jmp     loc_140004CC5
0x140004c25  mov     ecx, 0C0000163h
0x140004c2a  jmp     loc_140004CC5
0x140004c2f  mov     ecx, 0C0000161h
0x140004c34  jmp     loc_140004CC5
0x140004c39  mov     ecx, 0C0000025h
0x140004c3e  jmp     loc_140004CC5
0x140004c43  mov     ecx, 0C0000095h
0x140004c48  jmp     short loc_140004CC5
0x140004c4a  mov     ecx, 0C0000059h
0x140004c4f  jmp     short loc_140004CC5
0x140004c51  cmp     ecx, 8007050Ch
0x140004c57  jz      short loc_140004CC0
0x140004c59  cmp     ecx, 8007054Fh
0x140004c5f  jz      short loc_140004CB9
0x140004c61  cmp     ecx, 800705B9h
0x140004c67  jz      short loc_140004CB2
0x140004c69  test    ecx, ecx
0x140004c6b  jz      short loc_140004CAE
0x140004c6d  bt      ecx, 1Ch
0x140004c71  jnb     short loc_140004C79
0x140004c73  btr     ecx, 1Ch
0x140004c77  jmp     short loc_140004CC5
0x140004c79  mov     eax, ecx
0x140004c7b  and     eax, 1FFF0000h
0x140004c80  cmp     eax, 70000h
0x140004c85  jnz     short loc_140004C98
0x140004c87  movzx   ecx, cx
0x140004c8a  mov     eax, ecx
0x140004c8c  or      eax, 0C0070000h
0x140004c91  test    ecx, ecx
0x140004c93  cmovnz  ecx, eax
0x140004c96  jmp     short loc_140004CC5
0x140004c98  cmp     eax, 90000h
0x140004c9d  jnz     short loc_140004CB9
0x140004c9f  test    ecx, ecx
0x140004ca1  jle     short loc_140004CC5
0x140004ca3  movzx   ecx, cx
0x140004ca6  or      ecx, 0C0090000h
0x140004cac  jmp     short loc_140004CC5
0x140004cae  xor     ecx, ecx
0x140004cb0  jmp     short loc_140004CC5
0x140004cb2  mov     ecx, 0C000A083h
0x140004cb7  jmp     short loc_140004CC5
0x140004cb9  mov     ecx, 0C00000E5h
0x140004cbe  jmp     short loc_140004CC5
0x140004cc0  mov     ecx, 0C000042Bh
0x140004cc5  mov     eax, ecx
0x140004cc7  retn
```
