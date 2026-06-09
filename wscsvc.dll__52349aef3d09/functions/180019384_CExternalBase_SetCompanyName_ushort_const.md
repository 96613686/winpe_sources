# CExternalBase::SetCompanyName(ushort const *)

- ea: `0x180019384`
- end: `0x18001950f`
- name: `?SetCompanyName@CExternalBase@@QEAAJPEBG@Z`
- size: `395`
- prototype: `__int64 __fastcall(CExternalBase *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018d70`
- `0x180024370`
- `0x18002698c`
- `0x180032054`
- `0x1800321f0`
- `0x18003aca0`

## callees

- `0x180008e48`
- `0x180019384`
- `0x1800202e8`
- `0x180029e74`
- `0x18002b1ac`
- `0x18002fbb4`

## pseudocode

```c
__int64 __fastcall CExternalBase::SetCompanyName(CExternalBase *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rbx
  void *v4; // rdi
  int v5; // ebx
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  size_t v9; // rax
  _WORD *v10; // rax
  void *v11; // rsi
  __int64 v12; // rcx
  bool v13; // zf
  _WORD *v14; // rcx
  void *v15; // rcx

  v2 = a2;
  if ( !a2 )
  {
    v4 = 0;
    v5 = 0;
LABEL_26:
    v15 = (void *)*((_QWORD *)this + 5);
    if ( v15 )
      operator delete(v15);
    *((_QWORD *)this + 5) = v4;
    return (unsigned int)v5;
  }
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = v6 + 1;
  v8 = 51;
  if ( v7 < 0x33 )
  {
    v8 = v7;
  }
  else if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
      (unsigned int)v7,
      51);
  }
  v9 = 2 * v8;
  if ( !is_mul_ok(v8, 2u) )
    v9 = -1;
  v10 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    if ( v8 )
    {
      v12 = 2147483646;
      do
      {
        if ( !v12 )
          break;
        if ( !*v2 )
          break;
        *v10++ = *v2++;
        --v12;
        --v8;
      }
      while ( v8 );
      v13 = v8 == 0;
      v14 = v10 - 1;
      v4 = v11;
      v5 = 0;
      if ( !v13 )
        v14 = v10;
      *v14 = 0;
    }
    else
    {
      v5 = -2147024809;
      v4 = 0;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids, 2147942487LL);
      }
      operator delete(v11);
    }
    if ( v5 >= 0 )
      goto LABEL_26;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180019384  push    rbx
0x180019386  push    rbp
0x180019387  push    rsi
0x180019388  push    rdi
0x180019389  push    r14
0x18001938b  push    r15
0x18001938d  sub     rsp, 38h
0x180019391  xor     r14d, r14d
0x180019394  mov     rbx, rdx
0x180019397  mov     rbp, rcx
0x18001939a  test    rdx, rdx
0x18001939d  jnz     short loc_1800193AA
0x18001939f  mov     edi, r14d
0x1800193a2  mov     ebx, r14d
0x1800193a5  jmp     loc_1800194C0
0x1800193aa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800193ae  mov     rax, rsi
0x1800193b1  inc     rax
0x1800193b4  cmp     [rdx+rax*2], r14w
0x1800193b9  jnz     short loc_1800193B1
0x1800193bb  inc     rax
0x1800193be  lea     r15, WPP_GLOBAL_Control
0x1800193c5  mov     edi, 33h ; '3'
0x1800193ca  cmp     rax, rdi
0x1800193cd  jb      short loc_1800193FD
0x1800193cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193d6  cmp     rcx, r15
0x1800193d9  jz      short loc_180019400
0x1800193db  test    byte ptr [rcx+1Ch], 4
0x1800193df  jz      short loc_180019400
0x1800193e1  mov     rcx, [rcx+10h]
0x1800193e5  lea     edx, [rdi-29h]
0x1800193e8  mov     r9d, eax
0x1800193eb  mov     [rsp+68h+var_48], edi
0x1800193ef  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x1800193f6  call    WPP_SF_dd
0x1800193fb  jmp     short loc_180019400
0x1800193fd  mov     rdi, rax
0x180019400  mov     eax, 2
0x180019405  mul     rdi
0x180019408  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001940f  cmovb   rax, rsi
0x180019413  mov     rcx, rax; unsigned __int64
0x180019416  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001941b  mov     rsi, rax
0x18001941e  test    rax, rax
0x180019421  jz      loc_1800194D4
0x180019427  test    rdi, rdi
0x18001942a  jz      short loc_180019479
0x18001942c  cmp     rdi, 7FFFFFFFh
0x180019433  jbe     short loc_18001943C
0x180019435  mov     ebx, 80070057h
0x18001943a  jmp     short loc_180019483
0x18001943c  mov     ecx, 7FFFFFFEh
0x180019441  test    rcx, rcx
0x180019444  jz      short loc_180019462
0x180019446  movzx   edx, word ptr [rbx]
0x180019449  test    dx, dx
0x18001944c  jz      short loc_180019462
0x18001944e  mov     [rax], dx
0x180019451  add     rbx, 2
0x180019455  add     rax, 2
0x180019459  dec     rcx
0x18001945c  sub     rdi, 1
0x180019460  jnz     short loc_180019441
0x180019462  test    rdi, rdi
0x180019465  lea     rcx, [rax-2]
0x180019469  mov     rdi, rsi
0x18001946c  mov     ebx, r14d
0x18001946f  cmovnz  rcx, rax
0x180019473  mov     [rcx], r14w
0x180019477  jmp     short loc_1800194BC
0x180019479  mov     ebx, 80070057h
0x18001947e  test    rdi, rdi
0x180019481  jz      short loc_180019487
0x180019483  mov     [rax], r14w
0x180019487  mov     rdi, r14
0x18001948a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019491  cmp     rcx, r15
0x180019494  jz      short loc_1800194B4
0x180019496  test    byte ptr [rcx+1Ch], 1
0x18001949a  jz      short loc_1800194B4
0x18001949c  mov     rcx, [rcx+10h]
0x1800194a0  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x1800194a7  mov     edx, 0Bh
0x1800194ac  mov     r9d, ebx
0x1800194af  call    WPP_SF_d
0x1800194b4  mov     rcx, rsi; Block
0x1800194b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800194bc  test    ebx, ebx
0x1800194be  js      short loc_180019500
0x1800194c0  mov     rcx, [rbp+28h]; Block
0x1800194c4  test    rcx, rcx
0x1800194c7  jz      short loc_1800194CE
0x1800194c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800194ce  mov     [rbp+28h], rdi
0x1800194d2  jmp     short loc_180019500
0x1800194d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194db  cmp     rcx, r15
0x1800194de  jz      short loc_1800194FB
0x1800194e0  test    byte ptr [rcx+1Ch], 1
0x1800194e4  jz      short loc_1800194FB
0x1800194e6  mov     rcx, [rcx+10h]
0x1800194ea  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x1800194f1  mov     edx, 0Ch
0x1800194f6  call    WPP_SF_
0x1800194fb  mov     ebx, 8007000Eh
0x180019500  mov     eax, ebx
0x180019502  add     rsp, 38h
0x180019506  pop     r15
0x180019508  pop     r14
0x18001950a  pop     rdi
0x18001950b  pop     rsi
0x18001950c  pop     rbp
0x18001950d  pop     rbx
0x18001950e  retn
```
