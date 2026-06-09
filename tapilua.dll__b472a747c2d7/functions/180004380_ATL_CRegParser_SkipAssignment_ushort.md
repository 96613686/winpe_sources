# ATL::CRegParser::SkipAssignment(ushort *)

- ea: `0x180004380`
- end: `0x18000441d`
- name: `?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038f0`

## callees

- `0x180002f30`
- `0x180004380`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000440c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000440c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004394`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004394`
- `USER32!CharNextW` at `0x1800043da`
- `USER32!CharNextW` at `0x1800043da`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::SkipAssignment(LPCWSTR *this, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rbp
  int Token; // ebx

  v4 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v4 )
    return 2147942414LL;
  if ( *a2 != 61 )
    goto LABEL_12;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token >= 0 )
  {
    while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
      *this = CharNextW(*this);
    Token = ATL::CRegParser::NextToken(this, v4);
    if ( Token >= 0 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token >= 0 )
LABEL_12:
        Token = 0;
    }
  }
  free(v4);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180004380  push    rbx
0x180004382  push    rbp
0x180004383  push    rsi
0x180004384  push    rdi
0x180004385  sub     rsp, 28h
0x180004389  mov     rdi, rcx
0x18000438c  mov     rsi, rdx
0x18000438f  mov     ecx, 2000h; Size
0x180004394  call    cs:__imp_malloc
0x18000439a  mov     rbp, rax
0x18000439d  test    rax, rax
0x1800043a0  jnz     short loc_1800043A9
0x1800043a2  mov     eax, 8007000Eh
0x1800043a7  jmp     short loc_180004414
0x1800043a9  cmp     word ptr [rsi], 3Dh ; '='
0x1800043ad  jnz     short loc_180004407
0x1800043af  mov     rdx, rsi; unsigned __int16 *
0x1800043b2  mov     rcx, rdi; this
0x1800043b5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800043ba  mov     ebx, eax
0x1800043bc  test    eax, eax
0x1800043be  js      short loc_180004409
0x1800043c0  mov     rcx, [rdi]; lpsz
0x1800043c3  movzx   edx, word ptr [rcx]
0x1800043c6  sub     edx, 9
0x1800043c9  jz      short loc_1800043DA
0x1800043cb  sub     edx, 1
0x1800043ce  jz      short loc_1800043DA
0x1800043d0  sub     edx, 3
0x1800043d3  jz      short loc_1800043DA
0x1800043d5  cmp     edx, 13h
0x1800043d8  jnz     short loc_1800043E5
0x1800043da  call    cs:__imp_CharNextW
0x1800043e0  mov     [rdi], rax
0x1800043e3  jmp     short loc_1800043C0
0x1800043e5  mov     rdx, rbp; unsigned __int16 *
0x1800043e8  mov     rcx, rdi; this
0x1800043eb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800043f0  mov     ebx, eax
0x1800043f2  test    eax, eax
0x1800043f4  js      short loc_180004409
0x1800043f6  mov     rdx, rsi; unsigned __int16 *
0x1800043f9  mov     rcx, rdi; this
0x1800043fc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004401  mov     ebx, eax
0x180004403  test    eax, eax
0x180004405  js      short loc_180004409
0x180004407  xor     ebx, ebx
0x180004409  mov     rcx, rbp; Block
0x18000440c  call    cs:__imp_free
0x180004412  mov     eax, ebx
0x180004414  add     rsp, 28h
0x180004418  pop     rdi
0x180004419  pop     rsi
0x18000441a  pop     rbp
0x18000441b  pop     rbx
0x18000441c  retn
```
