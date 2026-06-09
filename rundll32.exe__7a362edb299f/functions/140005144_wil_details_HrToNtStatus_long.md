# wil::details::HrToNtStatus(long)

- ea: `0x140005144`
- end: `0x140005300`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000302c`
- `0x1400030cc`
- `0x14000311c`
- `0x1400031dc`
- `0x140004538`
- `0x140005408`

## callees

- `0x140005144`

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
0x140005144  mov     eax, 800700EAh
0x140005149  cmp     ecx, eax
0x14000514b  jg      loc_140005220
0x140005151  jz      loc_140005216
0x140005157  mov     eax, 80070057h
0x14000515c  cmp     ecx, eax
0x14000515e  jg      short loc_1400051CA
0x140005160  jz      short loc_1400051C0
0x140005162  cmp     ecx, 80004005h
0x140005168  jz      short loc_1400051B6
0x14000516a  cmp     ecx, 80070001h
0x140005170  jz      short loc_1400051AC
0x140005172  cmp     ecx, 80070002h
0x140005178  jz      short loc_1400051A2
0x14000517a  cmp     ecx, 80070003h
0x140005180  jz      short loc_140005198
0x140005182  cmp     ecx, 8007000Eh
0x140005188  jnz     loc_1400052A5
0x14000518e  mov     ecx, 0C0000017h
0x140005193  jmp     loc_1400052FD
0x140005198  mov     ecx, 0C000003Ah
0x14000519d  jmp     loc_1400052FD
0x1400051a2  mov     ecx, 0C0000034h
0x1400051a7  jmp     loc_1400052FD
0x1400051ac  mov     ecx, 0C0000002h
0x1400051b1  jmp     loc_1400052FD
0x1400051b6  mov     ecx, 0C0000001h
0x1400051bb  jmp     loc_1400052FD
0x1400051c0  mov     ecx, 0C000000Dh
0x1400051c5  jmp     loc_1400052FD
0x1400051ca  cmp     ecx, 80070070h
0x1400051d0  jz      short loc_14000520C
0x1400051d2  cmp     ecx, 8007007Ah
0x1400051d8  jz      short loc_140005202
0x1400051da  cmp     ecx, 8007007Bh
0x1400051e0  jz      short loc_1400051F8
0x1400051e2  cmp     ecx, 8007007Eh
0x1400051e8  jnz     loc_1400052A5
0x1400051ee  mov     ecx, 0C0000135h
0x1400051f3  jmp     loc_1400052FD
0x1400051f8  mov     ecx, 0C0000033h
0x1400051fd  jmp     loc_1400052FD
0x140005202  mov     ecx, 0C0000023h
0x140005207  jmp     loc_1400052FD
0x14000520c  mov     ecx, 0C000007Fh
0x140005211  jmp     loc_1400052FD
0x140005216  mov     ecx, 80000005h
0x14000521b  jmp     loc_1400052FD
0x140005220  mov     eax, 8007047Eh
0x140005225  cmp     ecx, eax
0x140005227  jg      short loc_140005289
0x140005229  jz      short loc_140005282
0x14000522b  cmp     ecx, 80070216h
0x140005231  jz      short loc_14000527B
0x140005233  cmp     ecx, 8007023Eh
0x140005239  jz      short loc_140005271
0x14000523b  cmp     ecx, 80070246h
0x140005241  jz      short loc_140005267
0x140005243  cmp     ecx, 80070247h
0x140005249  jz      short loc_14000525D
0x14000524b  cmp     ecx, 80070272h
0x140005251  jnz     short loc_1400052A5
0x140005253  mov     ecx, 0C0000273h
0x140005258  jmp     loc_1400052FD
0x14000525d  mov     ecx, 0C0000163h
0x140005262  jmp     loc_1400052FD
0x140005267  mov     ecx, 0C0000161h
0x14000526c  jmp     loc_1400052FD
0x140005271  mov     ecx, 0C0000025h
0x140005276  jmp     loc_1400052FD
0x14000527b  mov     ecx, 0C0000095h
0x140005280  jmp     short loc_1400052FD
0x140005282  mov     ecx, 0C0000059h
0x140005287  jmp     short loc_1400052FD
0x140005289  cmp     ecx, 8007050Ch
0x14000528f  jz      short loc_1400052F8
0x140005291  cmp     ecx, 8007054Fh
0x140005297  jz      short loc_1400052F1
0x140005299  cmp     ecx, 800705B9h
0x14000529f  jz      short loc_1400052EA
0x1400052a1  test    ecx, ecx
0x1400052a3  jz      short loc_1400052E6
0x1400052a5  bt      ecx, 1Ch
0x1400052a9  jnb     short loc_1400052B1
0x1400052ab  btr     ecx, 1Ch
0x1400052af  jmp     short loc_1400052FD
0x1400052b1  mov     eax, ecx
0x1400052b3  and     eax, 1FFF0000h
0x1400052b8  cmp     eax, 70000h
0x1400052bd  jnz     short loc_1400052D0
0x1400052bf  movzx   ecx, cx
0x1400052c2  mov     eax, ecx
0x1400052c4  or      eax, 0C0070000h
0x1400052c9  test    ecx, ecx
0x1400052cb  cmovnz  ecx, eax
0x1400052ce  jmp     short loc_1400052FD
0x1400052d0  cmp     eax, 90000h
0x1400052d5  jnz     short loc_1400052F1
0x1400052d7  test    ecx, ecx
0x1400052d9  jle     short loc_1400052FD
0x1400052db  movzx   ecx, cx
0x1400052de  or      ecx, 0C0090000h
0x1400052e4  jmp     short loc_1400052FD
0x1400052e6  xor     ecx, ecx
0x1400052e8  jmp     short loc_1400052FD
0x1400052ea  mov     ecx, 0C000A083h
0x1400052ef  jmp     short loc_1400052FD
0x1400052f1  mov     ecx, 0C00000E5h
0x1400052f6  jmp     short loc_1400052FD
0x1400052f8  mov     ecx, 0C000042Bh
0x1400052fd  mov     eax, ecx
0x1400052ff  retn
```
