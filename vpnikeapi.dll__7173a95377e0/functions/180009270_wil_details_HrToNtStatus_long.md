# wil::details::HrToNtStatus(long)

- ea: `0x180009270`
- end: `0x18000942c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006e94`
- `0x180006f0c`
- `0x180006f5c`
- `0x18000701c`
- `0x180008858`
- `0x180009654`

## callees

- `0x180009270`

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
0x180009270  mov     eax, 800700EAh
0x180009275  cmp     ecx, eax
0x180009277  jg      loc_18000934C
0x18000927d  jz      loc_180009342
0x180009283  mov     eax, 80070057h
0x180009288  cmp     ecx, eax
0x18000928a  jg      short loc_1800092F6
0x18000928c  jz      short loc_1800092EC
0x18000928e  cmp     ecx, 80004005h
0x180009294  jz      short loc_1800092E2
0x180009296  cmp     ecx, 80070001h
0x18000929c  jz      short loc_1800092D8
0x18000929e  cmp     ecx, 80070002h
0x1800092a4  jz      short loc_1800092CE
0x1800092a6  cmp     ecx, 80070003h
0x1800092ac  jz      short loc_1800092C4
0x1800092ae  cmp     ecx, 8007000Eh
0x1800092b4  jnz     loc_1800093D1
0x1800092ba  mov     ecx, 0C0000017h
0x1800092bf  jmp     loc_180009429
0x1800092c4  mov     ecx, 0C000003Ah
0x1800092c9  jmp     loc_180009429
0x1800092ce  mov     ecx, 0C0000034h
0x1800092d3  jmp     loc_180009429
0x1800092d8  mov     ecx, 0C0000002h
0x1800092dd  jmp     loc_180009429
0x1800092e2  mov     ecx, 0C0000001h
0x1800092e7  jmp     loc_180009429
0x1800092ec  mov     ecx, 0C000000Dh
0x1800092f1  jmp     loc_180009429
0x1800092f6  cmp     ecx, 80070070h
0x1800092fc  jz      short loc_180009338
0x1800092fe  cmp     ecx, 8007007Ah
0x180009304  jz      short loc_18000932E
0x180009306  cmp     ecx, 8007007Bh
0x18000930c  jz      short loc_180009324
0x18000930e  cmp     ecx, 8007007Eh
0x180009314  jnz     loc_1800093D1
0x18000931a  mov     ecx, 0C0000135h
0x18000931f  jmp     loc_180009429
0x180009324  mov     ecx, 0C0000033h
0x180009329  jmp     loc_180009429
0x18000932e  mov     ecx, 0C0000023h
0x180009333  jmp     loc_180009429
0x180009338  mov     ecx, 0C000007Fh
0x18000933d  jmp     loc_180009429
0x180009342  mov     ecx, 80000005h
0x180009347  jmp     loc_180009429
0x18000934c  mov     eax, 8007047Eh
0x180009351  cmp     ecx, eax
0x180009353  jg      short loc_1800093B5
0x180009355  jz      short loc_1800093AE
0x180009357  cmp     ecx, 80070216h
0x18000935d  jz      short loc_1800093A7
0x18000935f  cmp     ecx, 8007023Eh
0x180009365  jz      short loc_18000939D
0x180009367  cmp     ecx, 80070246h
0x18000936d  jz      short loc_180009393
0x18000936f  cmp     ecx, 80070247h
0x180009375  jz      short loc_180009389
0x180009377  cmp     ecx, 80070272h
0x18000937d  jnz     short loc_1800093D1
0x18000937f  mov     ecx, 0C0000273h
0x180009384  jmp     loc_180009429
0x180009389  mov     ecx, 0C0000163h
0x18000938e  jmp     loc_180009429
0x180009393  mov     ecx, 0C0000161h
0x180009398  jmp     loc_180009429
0x18000939d  mov     ecx, 0C0000025h
0x1800093a2  jmp     loc_180009429
0x1800093a7  mov     ecx, 0C0000095h
0x1800093ac  jmp     short loc_180009429
0x1800093ae  mov     ecx, 0C0000059h
0x1800093b3  jmp     short loc_180009429
0x1800093b5  cmp     ecx, 8007050Ch
0x1800093bb  jz      short loc_180009424
0x1800093bd  cmp     ecx, 8007054Fh
0x1800093c3  jz      short loc_18000941D
0x1800093c5  cmp     ecx, 800705B9h
0x1800093cb  jz      short loc_180009416
0x1800093cd  test    ecx, ecx
0x1800093cf  jz      short loc_180009412
0x1800093d1  bt      ecx, 1Ch
0x1800093d5  jnb     short loc_1800093DD
0x1800093d7  btr     ecx, 1Ch
0x1800093db  jmp     short loc_180009429
0x1800093dd  mov     eax, ecx
0x1800093df  and     eax, 1FFF0000h
0x1800093e4  cmp     eax, 70000h
0x1800093e9  jnz     short loc_1800093FC
0x1800093eb  movzx   ecx, cx
0x1800093ee  mov     eax, ecx
0x1800093f0  or      eax, 0C0070000h
0x1800093f5  test    ecx, ecx
0x1800093f7  cmovnz  ecx, eax
0x1800093fa  jmp     short loc_180009429
0x1800093fc  cmp     eax, 90000h
0x180009401  jnz     short loc_18000941D
0x180009403  test    ecx, ecx
0x180009405  jle     short loc_180009429
0x180009407  movzx   ecx, cx
0x18000940a  or      ecx, 0C0090000h
0x180009410  jmp     short loc_180009429
0x180009412  xor     ecx, ecx
0x180009414  jmp     short loc_180009429
0x180009416  mov     ecx, 0C000A083h
0x18000941b  jmp     short loc_180009429
0x18000941d  mov     ecx, 0C00000E5h
0x180009422  jmp     short loc_180009429
0x180009424  mov     ecx, 0C000042Bh
0x180009429  mov     eax, ecx
0x18000942b  retn
```
