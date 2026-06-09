# wil::details::HrToNtStatus(long)

- ea: `0x180004d50`
- end: `0x180004f0f`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `447`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049e0`
- `0x180005960`
- `0x180005a50`
- `0x180006bb4`
- `0x180006cf4`
- `0x180006f88`
- `0x180006fe0`
- `0x18000bc80`
- `0x18000be54`
- `0x180015625`
- `0x18001569b`
- `0x18001575e`
- `0x1800157d4`

## callees

- `0x180004d50`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // ecx
  int v2; // eax
  unsigned int v3; // eax

  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          return (unsigned int)-1073740757;
        case 0x8007054F:
          return (unsigned int)-1073741595;
        case 0x800705B9:
          return (unsigned int)-1073700733;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          return (unsigned int)-1073741735;
        case 0x80070216:
          return (unsigned int)-1073741675;
        case 0x8007023E:
          return (unsigned int)-1073741787;
        case 0x80070246:
          return (unsigned int)-1073741471;
        case 0x80070247:
          return (unsigned int)-1073741469;
        case 0x80070272:
          return (unsigned int)-1073741197;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
      return (unsigned int)-2147483643;
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          return (unsigned int)-1073741697;
        case 0x8007007A:
          return (unsigned int)-1073741789;
        case 0x8007007B:
          return (unsigned int)-1073741773;
        case 0x8007007E:
          return (unsigned int)-1073741515;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          return (unsigned int)-1073741811;
        case 0x80004005:
          return (unsigned int)-1073741823;
        case 0x80070001:
          return (unsigned int)-1073741822;
        case 0x80070002:
          return (unsigned int)-1073741772;
        case 0x80070003:
          return (unsigned int)-1073741766;
        case 0x8007000E:
          return (unsigned int)-1073741801;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
    return (unsigned int)this & 0xEFFFFFFF;
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    v2 = (unsigned __int16)this;
    v1 = (unsigned __int16)this | 0xC0070000;
    if ( !v2 )
      return 0;
    return v1;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
    return (unsigned int)-1073741595;
  v3 = (unsigned __int16)this | 0xC0090000;
  if ( (int)this <= 0 )
    return (unsigned int)this;
  return v3;
}

```

## disassembly

```asm
0x180004d50  mov     eax, 800700EAh
0x180004d55  cmp     ecx, eax
0x180004d57  jg      loc_180004E2C
0x180004d5d  jz      loc_180004E22
0x180004d63  mov     eax, 80070057h
0x180004d68  cmp     ecx, eax
0x180004d6a  jg      short loc_180004DD6
0x180004d6c  jz      short loc_180004DCC
0x180004d6e  cmp     ecx, 80004005h
0x180004d74  jz      short loc_180004DC2
0x180004d76  cmp     ecx, 80070001h
0x180004d7c  jz      short loc_180004DB8
0x180004d7e  cmp     ecx, 80070002h
0x180004d84  jz      short loc_180004DAE
0x180004d86  cmp     ecx, 80070003h
0x180004d8c  jz      short loc_180004DA4
0x180004d8e  cmp     ecx, 8007000Eh
0x180004d94  jnz     loc_180004EB1
0x180004d9a  mov     ecx, 0C0000017h
0x180004d9f  jmp     loc_180004F0C
0x180004da4  mov     ecx, 0C000003Ah
0x180004da9  jmp     loc_180004F0C
0x180004dae  mov     ecx, 0C0000034h
0x180004db3  jmp     loc_180004F0C
0x180004db8  mov     ecx, 0C0000002h
0x180004dbd  jmp     loc_180004F0C
0x180004dc2  mov     ecx, 0C0000001h
0x180004dc7  jmp     loc_180004F0C
0x180004dcc  mov     ecx, 0C000000Dh
0x180004dd1  jmp     loc_180004F0C
0x180004dd6  cmp     ecx, 80070070h
0x180004ddc  jz      short loc_180004E18
0x180004dde  cmp     ecx, 8007007Ah
0x180004de4  jz      short loc_180004E0E
0x180004de6  cmp     ecx, 8007007Bh
0x180004dec  jz      short loc_180004E04
0x180004dee  cmp     ecx, 8007007Eh
0x180004df4  jnz     loc_180004EB1
0x180004dfa  mov     ecx, 0C0000135h
0x180004dff  jmp     loc_180004F0C
0x180004e04  mov     ecx, 0C0000033h
0x180004e09  jmp     loc_180004F0C
0x180004e0e  mov     ecx, 0C0000023h
0x180004e13  jmp     loc_180004F0C
0x180004e18  mov     ecx, 0C000007Fh
0x180004e1d  jmp     loc_180004F0C
0x180004e22  mov     ecx, 80000005h
0x180004e27  jmp     loc_180004F0C
0x180004e2c  mov     eax, 8007047Eh
0x180004e31  cmp     ecx, eax
0x180004e33  jg      short loc_180004E95
0x180004e35  jz      short loc_180004E8E
0x180004e37  cmp     ecx, 80070216h
0x180004e3d  jz      short loc_180004E87
0x180004e3f  cmp     ecx, 8007023Eh
0x180004e45  jz      short loc_180004E7D
0x180004e47  cmp     ecx, 80070246h
0x180004e4d  jz      short loc_180004E73
0x180004e4f  cmp     ecx, 80070247h
0x180004e55  jz      short loc_180004E69
0x180004e57  cmp     ecx, 80070272h
0x180004e5d  jnz     short loc_180004EB1
0x180004e5f  mov     ecx, 0C0000273h
0x180004e64  jmp     loc_180004F0C
0x180004e69  mov     ecx, 0C0000163h
0x180004e6e  jmp     loc_180004F0C
0x180004e73  mov     ecx, 0C0000161h
0x180004e78  jmp     loc_180004F0C
0x180004e7d  mov     ecx, 0C0000025h
0x180004e82  jmp     loc_180004F0C
0x180004e87  mov     ecx, 0C0000095h
0x180004e8c  jmp     short loc_180004F0C
0x180004e8e  mov     ecx, 0C0000059h
0x180004e93  jmp     short loc_180004F0C
0x180004e95  cmp     ecx, 8007050Ch
0x180004e9b  jz      short loc_180004F07
0x180004e9d  cmp     ecx, 8007054Fh
0x180004ea3  jz      short loc_180004F00
0x180004ea5  cmp     ecx, 800705B9h
0x180004eab  jz      short loc_180004EF9
0x180004ead  test    ecx, ecx
0x180004eaf  jz      short loc_180004EF5
0x180004eb1  bt      ecx, 1Ch
0x180004eb5  jnb     short loc_180004EBD
0x180004eb7  btr     ecx, 1Ch
0x180004ebb  jmp     short loc_180004F0C
0x180004ebd  mov     eax, ecx
0x180004ebf  and     eax, 1FFF0000h
0x180004ec4  cmp     eax, 70000h
0x180004ec9  jnz     short loc_180004EDD
0x180004ecb  movzx   eax, cx
0x180004ece  mov     ecx, eax
0x180004ed0  or      ecx, 0C0070000h
0x180004ed6  test    eax, eax
0x180004ed8  cmovz   ecx, eax
0x180004edb  jmp     short loc_180004F0C
0x180004edd  cmp     eax, 90000h
0x180004ee2  jnz     short loc_180004F00
0x180004ee4  movzx   eax, cx
0x180004ee7  or      eax, 0C0090000h
0x180004eec  test    ecx, ecx
0x180004eee  cmovle  eax, ecx
0x180004ef1  mov     ecx, eax
0x180004ef3  jmp     short loc_180004F0C
0x180004ef5  xor     ecx, ecx
0x180004ef7  jmp     short loc_180004F0C
0x180004ef9  mov     ecx, 0C000A083h
0x180004efe  jmp     short loc_180004F0C
0x180004f00  mov     ecx, 0C00000E5h
0x180004f05  jmp     short loc_180004F0C
0x180004f07  mov     ecx, 0C000042Bh
0x180004f0c  mov     eax, ecx
0x180004f0e  retn
```
