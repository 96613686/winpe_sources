# wil::details::HrToNtStatus(long)

- ea: `0x18000511c`
- end: `0x1800052d8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004cbc`
- `0x180014bd4`
- `0x180014c44`
- `0x180014cbc`
- `0x180014d0c`
- `0x180015cd8`

## callees

- `0x18000511c`

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
0x18000511c  mov     eax, 800700EAh
0x180005121  cmp     ecx, eax
0x180005123  jg      loc_1800051F8
0x180005129  jz      loc_1800051EE
0x18000512f  mov     eax, 80070057h
0x180005134  cmp     ecx, eax
0x180005136  jg      short loc_1800051A2
0x180005138  jz      short loc_180005198
0x18000513a  cmp     ecx, 80004005h
0x180005140  jz      short loc_18000518E
0x180005142  cmp     ecx, 80070001h
0x180005148  jz      short loc_180005184
0x18000514a  cmp     ecx, 80070002h
0x180005150  jz      short loc_18000517A
0x180005152  cmp     ecx, 80070003h
0x180005158  jz      short loc_180005170
0x18000515a  cmp     ecx, 8007000Eh
0x180005160  jnz     loc_18000527D
0x180005166  mov     ecx, 0C0000017h
0x18000516b  jmp     loc_1800052D5
0x180005170  mov     ecx, 0C000003Ah
0x180005175  jmp     loc_1800052D5
0x18000517a  mov     ecx, 0C0000034h
0x18000517f  jmp     loc_1800052D5
0x180005184  mov     ecx, 0C0000002h
0x180005189  jmp     loc_1800052D5
0x18000518e  mov     ecx, 0C0000001h
0x180005193  jmp     loc_1800052D5
0x180005198  mov     ecx, 0C000000Dh
0x18000519d  jmp     loc_1800052D5
0x1800051a2  cmp     ecx, 80070070h
0x1800051a8  jz      short loc_1800051E4
0x1800051aa  cmp     ecx, 8007007Ah
0x1800051b0  jz      short loc_1800051DA
0x1800051b2  cmp     ecx, 8007007Bh
0x1800051b8  jz      short loc_1800051D0
0x1800051ba  cmp     ecx, 8007007Eh
0x1800051c0  jnz     loc_18000527D
0x1800051c6  mov     ecx, 0C0000135h
0x1800051cb  jmp     loc_1800052D5
0x1800051d0  mov     ecx, 0C0000033h
0x1800051d5  jmp     loc_1800052D5
0x1800051da  mov     ecx, 0C0000023h
0x1800051df  jmp     loc_1800052D5
0x1800051e4  mov     ecx, 0C000007Fh
0x1800051e9  jmp     loc_1800052D5
0x1800051ee  mov     ecx, 80000005h
0x1800051f3  jmp     loc_1800052D5
0x1800051f8  mov     eax, 8007047Eh
0x1800051fd  cmp     ecx, eax
0x1800051ff  jg      short loc_180005261
0x180005201  jz      short loc_18000525A
0x180005203  cmp     ecx, 80070216h
0x180005209  jz      short loc_180005253
0x18000520b  cmp     ecx, 8007023Eh
0x180005211  jz      short loc_180005249
0x180005213  cmp     ecx, 80070246h
0x180005219  jz      short loc_18000523F
0x18000521b  cmp     ecx, 80070247h
0x180005221  jz      short loc_180005235
0x180005223  cmp     ecx, 80070272h
0x180005229  jnz     short loc_18000527D
0x18000522b  mov     ecx, 0C0000273h
0x180005230  jmp     loc_1800052D5
0x180005235  mov     ecx, 0C0000163h
0x18000523a  jmp     loc_1800052D5
0x18000523f  mov     ecx, 0C0000161h
0x180005244  jmp     loc_1800052D5
0x180005249  mov     ecx, 0C0000025h
0x18000524e  jmp     loc_1800052D5
0x180005253  mov     ecx, 0C0000095h
0x180005258  jmp     short loc_1800052D5
0x18000525a  mov     ecx, 0C0000059h
0x18000525f  jmp     short loc_1800052D5
0x180005261  cmp     ecx, 8007050Ch
0x180005267  jz      short loc_1800052D0
0x180005269  cmp     ecx, 8007054Fh
0x18000526f  jz      short loc_1800052C9
0x180005271  cmp     ecx, 800705B9h
0x180005277  jz      short loc_1800052C2
0x180005279  test    ecx, ecx
0x18000527b  jz      short loc_1800052BE
0x18000527d  bt      ecx, 1Ch
0x180005281  jnb     short loc_180005289
0x180005283  btr     ecx, 1Ch
0x180005287  jmp     short loc_1800052D5
0x180005289  mov     eax, ecx
0x18000528b  and     eax, 1FFF0000h
0x180005290  cmp     eax, 70000h
0x180005295  jnz     short loc_1800052A8
0x180005297  movzx   ecx, cx
0x18000529a  mov     eax, ecx
0x18000529c  or      eax, 0C0070000h
0x1800052a1  test    ecx, ecx
0x1800052a3  cmovnz  ecx, eax
0x1800052a6  jmp     short loc_1800052D5
0x1800052a8  cmp     eax, 90000h
0x1800052ad  jnz     short loc_1800052C9
0x1800052af  test    ecx, ecx
0x1800052b1  jle     short loc_1800052D5
0x1800052b3  movzx   ecx, cx
0x1800052b6  or      ecx, 0C0090000h
0x1800052bc  jmp     short loc_1800052D5
0x1800052be  xor     ecx, ecx
0x1800052c0  jmp     short loc_1800052D5
0x1800052c2  mov     ecx, 0C000A083h
0x1800052c7  jmp     short loc_1800052D5
0x1800052c9  mov     ecx, 0C00000E5h
0x1800052ce  jmp     short loc_1800052D5
0x1800052d0  mov     ecx, 0C000042Bh
0x1800052d5  mov     eax, ecx
0x1800052d7  retn
```
