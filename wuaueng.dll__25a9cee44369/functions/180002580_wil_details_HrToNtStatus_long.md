# wil::details::HrToNtStatus(long)

- ea: `0x180002580`
- end: `0x18000273f`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `447`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002130`
- `0x180003190`
- `0x180003280`
- `0x180004440`
- `0x180004580`
- `0x180004814`
- `0x180004864`
- `0x180008c38`
- `0x180016554`
- `0x1800165ca`
- `0x18001668d`
- `0x180016703`

## callees

- `0x180002580`

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
0x180002580  mov     eax, 800700EAh
0x180002585  cmp     ecx, eax
0x180002587  jg      loc_18000265C
0x18000258d  jz      loc_180002652
0x180002593  mov     eax, 80070057h
0x180002598  cmp     ecx, eax
0x18000259a  jg      short loc_180002606
0x18000259c  jz      short loc_1800025FC
0x18000259e  cmp     ecx, 80004005h
0x1800025a4  jz      short loc_1800025F2
0x1800025a6  cmp     ecx, 80070001h
0x1800025ac  jz      short loc_1800025E8
0x1800025ae  cmp     ecx, 80070002h
0x1800025b4  jz      short loc_1800025DE
0x1800025b6  cmp     ecx, 80070003h
0x1800025bc  jz      short loc_1800025D4
0x1800025be  cmp     ecx, 8007000Eh
0x1800025c4  jnz     loc_1800026E1
0x1800025ca  mov     ecx, 0C0000017h
0x1800025cf  jmp     loc_18000273C
0x1800025d4  mov     ecx, 0C000003Ah
0x1800025d9  jmp     loc_18000273C
0x1800025de  mov     ecx, 0C0000034h
0x1800025e3  jmp     loc_18000273C
0x1800025e8  mov     ecx, 0C0000002h
0x1800025ed  jmp     loc_18000273C
0x1800025f2  mov     ecx, 0C0000001h
0x1800025f7  jmp     loc_18000273C
0x1800025fc  mov     ecx, 0C000000Dh
0x180002601  jmp     loc_18000273C
0x180002606  cmp     ecx, 80070070h
0x18000260c  jz      short loc_180002648
0x18000260e  cmp     ecx, 8007007Ah
0x180002614  jz      short loc_18000263E
0x180002616  cmp     ecx, 8007007Bh
0x18000261c  jz      short loc_180002634
0x18000261e  cmp     ecx, 8007007Eh
0x180002624  jnz     loc_1800026E1
0x18000262a  mov     ecx, 0C0000135h
0x18000262f  jmp     loc_18000273C
0x180002634  mov     ecx, 0C0000033h
0x180002639  jmp     loc_18000273C
0x18000263e  mov     ecx, 0C0000023h
0x180002643  jmp     loc_18000273C
0x180002648  mov     ecx, 0C000007Fh
0x18000264d  jmp     loc_18000273C
0x180002652  mov     ecx, 80000005h
0x180002657  jmp     loc_18000273C
0x18000265c  mov     eax, 8007047Eh
0x180002661  cmp     ecx, eax
0x180002663  jg      short loc_1800026C5
0x180002665  jz      short loc_1800026BE
0x180002667  cmp     ecx, 80070216h
0x18000266d  jz      short loc_1800026B7
0x18000266f  cmp     ecx, 8007023Eh
0x180002675  jz      short loc_1800026AD
0x180002677  cmp     ecx, 80070246h
0x18000267d  jz      short loc_1800026A3
0x18000267f  cmp     ecx, 80070247h
0x180002685  jz      short loc_180002699
0x180002687  cmp     ecx, 80070272h
0x18000268d  jnz     short loc_1800026E1
0x18000268f  mov     ecx, 0C0000273h
0x180002694  jmp     loc_18000273C
0x180002699  mov     ecx, 0C0000163h
0x18000269e  jmp     loc_18000273C
0x1800026a3  mov     ecx, 0C0000161h
0x1800026a8  jmp     loc_18000273C
0x1800026ad  mov     ecx, 0C0000025h
0x1800026b2  jmp     loc_18000273C
0x1800026b7  mov     ecx, 0C0000095h
0x1800026bc  jmp     short loc_18000273C
0x1800026be  mov     ecx, 0C0000059h
0x1800026c3  jmp     short loc_18000273C
0x1800026c5  cmp     ecx, 8007050Ch
0x1800026cb  jz      short loc_180002737
0x1800026cd  cmp     ecx, 8007054Fh
0x1800026d3  jz      short loc_180002730
0x1800026d5  cmp     ecx, 800705B9h
0x1800026db  jz      short loc_180002729
0x1800026dd  test    ecx, ecx
0x1800026df  jz      short loc_180002725
0x1800026e1  bt      ecx, 1Ch
0x1800026e5  jnb     short loc_1800026ED
0x1800026e7  btr     ecx, 1Ch
0x1800026eb  jmp     short loc_18000273C
0x1800026ed  mov     eax, ecx
0x1800026ef  and     eax, 1FFF0000h
0x1800026f4  cmp     eax, 70000h
0x1800026f9  jnz     short loc_18000270D
0x1800026fb  movzx   eax, cx
0x1800026fe  mov     ecx, eax
0x180002700  or      ecx, 0C0070000h
0x180002706  test    eax, eax
0x180002708  cmovz   ecx, eax
0x18000270b  jmp     short loc_18000273C
0x18000270d  cmp     eax, 90000h
0x180002712  jnz     short loc_180002730
0x180002714  movzx   eax, cx
0x180002717  or      eax, 0C0090000h
0x18000271c  test    ecx, ecx
0x18000271e  cmovle  eax, ecx
0x180002721  mov     ecx, eax
0x180002723  jmp     short loc_18000273C
0x180002725  xor     ecx, ecx
0x180002727  jmp     short loc_18000273C
0x180002729  mov     ecx, 0C000A083h
0x18000272e  jmp     short loc_18000273C
0x180002730  mov     ecx, 0C00000E5h
0x180002735  jmp     short loc_18000273C
0x180002737  mov     ecx, 0C000042Bh
0x18000273c  mov     eax, ecx
0x18000273e  retn
```
