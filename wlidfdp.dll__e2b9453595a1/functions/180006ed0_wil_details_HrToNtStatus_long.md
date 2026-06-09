# wil::details::HrToNtStatus(long)

- ea: `0x180006ed0`
- end: `0x18000708c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004910`
- `0x180004980`
- `0x1800049fc`
- `0x180004a4c`
- `0x1800065e8`
- `0x180007480`

## callees

- `0x180006ed0`

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
0x180006ed0  mov     eax, 800700EAh
0x180006ed5  cmp     ecx, eax
0x180006ed7  jg      loc_180006FAC
0x180006edd  jz      loc_180006FA2
0x180006ee3  mov     eax, 80070057h
0x180006ee8  cmp     ecx, eax
0x180006eea  jg      short loc_180006F56
0x180006eec  jz      short loc_180006F4C
0x180006eee  cmp     ecx, 80004005h
0x180006ef4  jz      short loc_180006F42
0x180006ef6  cmp     ecx, 80070001h
0x180006efc  jz      short loc_180006F38
0x180006efe  cmp     ecx, 80070002h
0x180006f04  jz      short loc_180006F2E
0x180006f06  cmp     ecx, 80070003h
0x180006f0c  jz      short loc_180006F24
0x180006f0e  cmp     ecx, 8007000Eh
0x180006f14  jnz     loc_180007031
0x180006f1a  mov     ecx, 0C0000017h
0x180006f1f  jmp     loc_180007089
0x180006f24  mov     ecx, 0C000003Ah
0x180006f29  jmp     loc_180007089
0x180006f2e  mov     ecx, 0C0000034h
0x180006f33  jmp     loc_180007089
0x180006f38  mov     ecx, 0C0000002h
0x180006f3d  jmp     loc_180007089
0x180006f42  mov     ecx, 0C0000001h
0x180006f47  jmp     loc_180007089
0x180006f4c  mov     ecx, 0C000000Dh
0x180006f51  jmp     loc_180007089
0x180006f56  cmp     ecx, 80070070h
0x180006f5c  jz      short loc_180006F98
0x180006f5e  cmp     ecx, 8007007Ah
0x180006f64  jz      short loc_180006F8E
0x180006f66  cmp     ecx, 8007007Bh
0x180006f6c  jz      short loc_180006F84
0x180006f6e  cmp     ecx, 8007007Eh
0x180006f74  jnz     loc_180007031
0x180006f7a  mov     ecx, 0C0000135h
0x180006f7f  jmp     loc_180007089
0x180006f84  mov     ecx, 0C0000033h
0x180006f89  jmp     loc_180007089
0x180006f8e  mov     ecx, 0C0000023h
0x180006f93  jmp     loc_180007089
0x180006f98  mov     ecx, 0C000007Fh
0x180006f9d  jmp     loc_180007089
0x180006fa2  mov     ecx, 80000005h
0x180006fa7  jmp     loc_180007089
0x180006fac  mov     eax, 8007047Eh
0x180006fb1  cmp     ecx, eax
0x180006fb3  jg      short loc_180007015
0x180006fb5  jz      short loc_18000700E
0x180006fb7  cmp     ecx, 80070216h
0x180006fbd  jz      short loc_180007007
0x180006fbf  cmp     ecx, 8007023Eh
0x180006fc5  jz      short loc_180006FFD
0x180006fc7  cmp     ecx, 80070246h
0x180006fcd  jz      short loc_180006FF3
0x180006fcf  cmp     ecx, 80070247h
0x180006fd5  jz      short loc_180006FE9
0x180006fd7  cmp     ecx, 80070272h
0x180006fdd  jnz     short loc_180007031
0x180006fdf  mov     ecx, 0C0000273h
0x180006fe4  jmp     loc_180007089
0x180006fe9  mov     ecx, 0C0000163h
0x180006fee  jmp     loc_180007089
0x180006ff3  mov     ecx, 0C0000161h
0x180006ff8  jmp     loc_180007089
0x180006ffd  mov     ecx, 0C0000025h
0x180007002  jmp     loc_180007089
0x180007007  mov     ecx, 0C0000095h
0x18000700c  jmp     short loc_180007089
0x18000700e  mov     ecx, 0C0000059h
0x180007013  jmp     short loc_180007089
0x180007015  cmp     ecx, 8007050Ch
0x18000701b  jz      short loc_180007084
0x18000701d  cmp     ecx, 8007054Fh
0x180007023  jz      short loc_18000707D
0x180007025  cmp     ecx, 800705B9h
0x18000702b  jz      short loc_180007076
0x18000702d  test    ecx, ecx
0x18000702f  jz      short loc_180007072
0x180007031  bt      ecx, 1Ch
0x180007035  jnb     short loc_18000703D
0x180007037  btr     ecx, 1Ch
0x18000703b  jmp     short loc_180007089
0x18000703d  mov     eax, ecx
0x18000703f  and     eax, 1FFF0000h
0x180007044  cmp     eax, 70000h
0x180007049  jnz     short loc_18000705C
0x18000704b  movzx   ecx, cx
0x18000704e  mov     eax, ecx
0x180007050  or      eax, 0C0070000h
0x180007055  test    ecx, ecx
0x180007057  cmovnz  ecx, eax
0x18000705a  jmp     short loc_180007089
0x18000705c  cmp     eax, 90000h
0x180007061  jnz     short loc_18000707D
0x180007063  test    ecx, ecx
0x180007065  jle     short loc_180007089
0x180007067  movzx   ecx, cx
0x18000706a  or      ecx, 0C0090000h
0x180007070  jmp     short loc_180007089
0x180007072  xor     ecx, ecx
0x180007074  jmp     short loc_180007089
0x180007076  mov     ecx, 0C000A083h
0x18000707b  jmp     short loc_180007089
0x18000707d  mov     ecx, 0C00000E5h
0x180007082  jmp     short loc_180007089
0x180007084  mov     ecx, 0C000042Bh
0x180007089  mov     eax, ecx
0x18000708b  retn
```
