# wil::details::HrToNtStatus(long)

- ea: `0x140004afc`
- end: `0x140004cb8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002dc8`
- `0x140002e70`
- `0x140002ec0`
- `0x140002f78`
- `0x1400040c8`
- `0x140004cc0`

## callees

- `0x140004afc`

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
0x140004afc  mov     eax, 800700EAh
0x140004b01  cmp     ecx, eax
0x140004b03  jg      loc_140004BD8
0x140004b09  jz      loc_140004BCE
0x140004b0f  mov     eax, 80070057h
0x140004b14  cmp     ecx, eax
0x140004b16  jg      short loc_140004B82
0x140004b18  jz      short loc_140004B78
0x140004b1a  cmp     ecx, 80004005h
0x140004b20  jz      short loc_140004B6E
0x140004b22  cmp     ecx, 80070001h
0x140004b28  jz      short loc_140004B64
0x140004b2a  cmp     ecx, 80070002h
0x140004b30  jz      short loc_140004B5A
0x140004b32  cmp     ecx, 80070003h
0x140004b38  jz      short loc_140004B50
0x140004b3a  cmp     ecx, 8007000Eh
0x140004b40  jnz     loc_140004C5D
0x140004b46  mov     ecx, 0C0000017h
0x140004b4b  jmp     loc_140004CB5
0x140004b50  mov     ecx, 0C000003Ah
0x140004b55  jmp     loc_140004CB5
0x140004b5a  mov     ecx, 0C0000034h
0x140004b5f  jmp     loc_140004CB5
0x140004b64  mov     ecx, 0C0000002h
0x140004b69  jmp     loc_140004CB5
0x140004b6e  mov     ecx, 0C0000001h
0x140004b73  jmp     loc_140004CB5
0x140004b78  mov     ecx, 0C000000Dh
0x140004b7d  jmp     loc_140004CB5
0x140004b82  cmp     ecx, 80070070h
0x140004b88  jz      short loc_140004BC4
0x140004b8a  cmp     ecx, 8007007Ah
0x140004b90  jz      short loc_140004BBA
0x140004b92  cmp     ecx, 8007007Bh
0x140004b98  jz      short loc_140004BB0
0x140004b9a  cmp     ecx, 8007007Eh
0x140004ba0  jnz     loc_140004C5D
0x140004ba6  mov     ecx, 0C0000135h
0x140004bab  jmp     loc_140004CB5
0x140004bb0  mov     ecx, 0C0000033h
0x140004bb5  jmp     loc_140004CB5
0x140004bba  mov     ecx, 0C0000023h
0x140004bbf  jmp     loc_140004CB5
0x140004bc4  mov     ecx, 0C000007Fh
0x140004bc9  jmp     loc_140004CB5
0x140004bce  mov     ecx, 80000005h
0x140004bd3  jmp     loc_140004CB5
0x140004bd8  mov     eax, 8007047Eh
0x140004bdd  cmp     ecx, eax
0x140004bdf  jg      short loc_140004C41
0x140004be1  jz      short loc_140004C3A
0x140004be3  cmp     ecx, 80070216h
0x140004be9  jz      short loc_140004C33
0x140004beb  cmp     ecx, 8007023Eh
0x140004bf1  jz      short loc_140004C29
0x140004bf3  cmp     ecx, 80070246h
0x140004bf9  jz      short loc_140004C1F
0x140004bfb  cmp     ecx, 80070247h
0x140004c01  jz      short loc_140004C15
0x140004c03  cmp     ecx, 80070272h
0x140004c09  jnz     short loc_140004C5D
0x140004c0b  mov     ecx, 0C0000273h
0x140004c10  jmp     loc_140004CB5
0x140004c15  mov     ecx, 0C0000163h
0x140004c1a  jmp     loc_140004CB5
0x140004c1f  mov     ecx, 0C0000161h
0x140004c24  jmp     loc_140004CB5
0x140004c29  mov     ecx, 0C0000025h
0x140004c2e  jmp     loc_140004CB5
0x140004c33  mov     ecx, 0C0000095h
0x140004c38  jmp     short loc_140004CB5
0x140004c3a  mov     ecx, 0C0000059h
0x140004c3f  jmp     short loc_140004CB5
0x140004c41  cmp     ecx, 8007050Ch
0x140004c47  jz      short loc_140004CB0
0x140004c49  cmp     ecx, 8007054Fh
0x140004c4f  jz      short loc_140004CA9
0x140004c51  cmp     ecx, 800705B9h
0x140004c57  jz      short loc_140004CA2
0x140004c59  test    ecx, ecx
0x140004c5b  jz      short loc_140004C9E
0x140004c5d  bt      ecx, 1Ch
0x140004c61  jnb     short loc_140004C69
0x140004c63  btr     ecx, 1Ch
0x140004c67  jmp     short loc_140004CB5
0x140004c69  mov     eax, ecx
0x140004c6b  and     eax, 1FFF0000h
0x140004c70  cmp     eax, 70000h
0x140004c75  jnz     short loc_140004C88
0x140004c77  movzx   ecx, cx
0x140004c7a  mov     eax, ecx
0x140004c7c  or      eax, 0C0070000h
0x140004c81  test    ecx, ecx
0x140004c83  cmovnz  ecx, eax
0x140004c86  jmp     short loc_140004CB5
0x140004c88  cmp     eax, 90000h
0x140004c8d  jnz     short loc_140004CA9
0x140004c8f  test    ecx, ecx
0x140004c91  jle     short loc_140004CB5
0x140004c93  movzx   ecx, cx
0x140004c96  or      ecx, 0C0090000h
0x140004c9c  jmp     short loc_140004CB5
0x140004c9e  xor     ecx, ecx
0x140004ca0  jmp     short loc_140004CB5
0x140004ca2  mov     ecx, 0C000A083h
0x140004ca7  jmp     short loc_140004CB5
0x140004ca9  mov     ecx, 0C00000E5h
0x140004cae  jmp     short loc_140004CB5
0x140004cb0  mov     ecx, 0C000042Bh
0x140004cb5  mov     eax, ecx
0x140004cb7  retn
```
