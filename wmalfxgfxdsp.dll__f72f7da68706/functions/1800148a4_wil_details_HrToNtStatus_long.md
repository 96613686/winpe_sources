# wil::details::HrToNtStatus(long)

- ea: `0x1800148a4`
- end: `0x180014a60`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d2c`
- `0x180014d7c`
- `0x18007617c`
- `0x1800761ec`
- `0x180076268`
- `0x18007832c`

## callees

- `0x1800148a4`

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
        case 0x8007054F:
          goto LABEL_53;
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
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
0x1800148a4  mov     eax, 800700EAh
0x1800148a9  cmp     ecx, eax
0x1800148ab  jg      loc_180014980
0x1800148b1  jz      loc_180014976
0x1800148b7  mov     eax, 80070057h
0x1800148bc  cmp     ecx, eax
0x1800148be  jg      short loc_18001492A
0x1800148c0  jz      short loc_180014920
0x1800148c2  cmp     ecx, 80004005h
0x1800148c8  jz      short loc_180014916
0x1800148ca  cmp     ecx, 80070001h
0x1800148d0  jz      short loc_18001490C
0x1800148d2  cmp     ecx, 80070002h
0x1800148d8  jz      short loc_180014902
0x1800148da  cmp     ecx, 80070003h
0x1800148e0  jz      short loc_1800148F8
0x1800148e2  cmp     ecx, 8007000Eh
0x1800148e8  jnz     loc_180014A05
0x1800148ee  mov     ecx, 0C0000017h
0x1800148f3  jmp     loc_180014A5D
0x1800148f8  mov     ecx, 0C000003Ah
0x1800148fd  jmp     loc_180014A5D
0x180014902  mov     ecx, 0C0000034h
0x180014907  jmp     loc_180014A5D
0x18001490c  mov     ecx, 0C0000002h
0x180014911  jmp     loc_180014A5D
0x180014916  mov     ecx, 0C0000001h
0x18001491b  jmp     loc_180014A5D
0x180014920  mov     ecx, 0C000000Dh
0x180014925  jmp     loc_180014A5D
0x18001492a  cmp     ecx, 80070070h
0x180014930  jz      short loc_18001496C
0x180014932  cmp     ecx, 8007007Ah
0x180014938  jz      short loc_180014962
0x18001493a  cmp     ecx, 8007007Bh
0x180014940  jz      short loc_180014958
0x180014942  cmp     ecx, 8007007Eh
0x180014948  jnz     loc_180014A05
0x18001494e  mov     ecx, 0C0000135h
0x180014953  jmp     loc_180014A5D
0x180014958  mov     ecx, 0C0000033h
0x18001495d  jmp     loc_180014A5D
0x180014962  mov     ecx, 0C0000023h
0x180014967  jmp     loc_180014A5D
0x18001496c  mov     ecx, 0C000007Fh
0x180014971  jmp     loc_180014A5D
0x180014976  mov     ecx, 80000005h
0x18001497b  jmp     loc_180014A5D
0x180014980  mov     eax, 8007047Eh
0x180014985  cmp     ecx, eax
0x180014987  jg      short loc_1800149E9
0x180014989  jz      short loc_1800149E2
0x18001498b  cmp     ecx, 80070216h
0x180014991  jz      short loc_1800149DB
0x180014993  cmp     ecx, 8007023Eh
0x180014999  jz      short loc_1800149D1
0x18001499b  cmp     ecx, 80070246h
0x1800149a1  jz      short loc_1800149C7
0x1800149a3  cmp     ecx, 80070247h
0x1800149a9  jz      short loc_1800149BD
0x1800149ab  cmp     ecx, 80070272h
0x1800149b1  jnz     short loc_180014A05
0x1800149b3  mov     ecx, 0C0000273h
0x1800149b8  jmp     loc_180014A5D
0x1800149bd  mov     ecx, 0C0000163h
0x1800149c2  jmp     loc_180014A5D
0x1800149c7  mov     ecx, 0C0000161h
0x1800149cc  jmp     loc_180014A5D
0x1800149d1  mov     ecx, 0C0000025h
0x1800149d6  jmp     loc_180014A5D
0x1800149db  mov     ecx, 0C0000095h
0x1800149e0  jmp     short loc_180014A5D
0x1800149e2  mov     ecx, 0C0000059h
0x1800149e7  jmp     short loc_180014A5D
0x1800149e9  cmp     ecx, 8007054Fh
0x1800149ef  jz      short loc_180014A51
0x1800149f1  cmp     ecx, 8007050Ch
0x1800149f7  jz      short loc_180014A58
0x1800149f9  cmp     ecx, 800705B9h
0x1800149ff  jz      short loc_180014A4A
0x180014a01  test    ecx, ecx
0x180014a03  jz      short loc_180014A46
0x180014a05  bt      ecx, 1Ch
0x180014a09  jnb     short loc_180014A11
0x180014a0b  btr     ecx, 1Ch
0x180014a0f  jmp     short loc_180014A5D
0x180014a11  mov     eax, ecx
0x180014a13  and     eax, 1FFF0000h
0x180014a18  cmp     eax, 70000h
0x180014a1d  jnz     short loc_180014A30
0x180014a1f  movzx   ecx, cx
0x180014a22  mov     eax, ecx
0x180014a24  or      eax, 0C0070000h
0x180014a29  test    ecx, ecx
0x180014a2b  cmovnz  ecx, eax
0x180014a2e  jmp     short loc_180014A5D
0x180014a30  cmp     eax, 90000h
0x180014a35  jnz     short loc_180014A51
0x180014a37  test    ecx, ecx
0x180014a39  jle     short loc_180014A5D
0x180014a3b  movzx   ecx, cx
0x180014a3e  or      ecx, 0C0090000h
0x180014a44  jmp     short loc_180014A5D
0x180014a46  xor     ecx, ecx
0x180014a48  jmp     short loc_180014A5D
0x180014a4a  mov     ecx, 0C000A083h
0x180014a4f  jmp     short loc_180014A5D
0x180014a51  mov     ecx, 0C00000E5h
0x180014a56  jmp     short loc_180014A5D
0x180014a58  mov     ecx, 0C000042Bh
0x180014a5d  mov     eax, ecx
0x180014a5f  retn
```
