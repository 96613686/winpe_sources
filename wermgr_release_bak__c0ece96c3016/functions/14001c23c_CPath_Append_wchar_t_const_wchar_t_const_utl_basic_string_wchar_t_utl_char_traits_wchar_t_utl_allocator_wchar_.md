# CPath::Append(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x14001c23c`
- end: `0x14001c4a1`
- name: `?Append@CPath@@SAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001c4a8`

## callees

- `0x14000db44`
- `0x14000dc18`
- `0x14000e020`
- `0x14000e340`
- `0x1400189c4`
- `0x14001c23c`

## pseudocode

```c
__int64 __fastcall CPath::Append(_WORD *a1, _WORD *a2, __int64 a3)
{
  _WORD *v4; // rbp
  __int64 v6; // rbx
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  _WORD *v13; // rcx
  BOOL v14; // r12d

  v4 = a2;
  if ( !a1 || !*a1 || !a2 || !a3 )
  {
    v9 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 10;
      v12 = 2147942487LL;
      goto LABEL_43;
    }
    return v9;
  }
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  do
    ++v6;
  while ( a2[v6] );
  v8 = v7 + v6;
  if ( v7 + v6 < v7 )
  {
    v9 = -2147024362;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 11;
LABEL_12:
      v12 = 2147942934LL;
LABEL_43:
      WPP_SF_d(v10[2], v11, WPP_74b024c659e0370c20fde454c384f757_Traceguids, v12);
      return v9;
    }
    return v9;
  }
  if ( v8 >= 0xFFFFFFFFFFFFFFFEuLL )
  {
    v9 = -2147024362;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 12;
      goto LABEL_12;
    }
    return v9;
  }
  v13 = *(_WORD **)a3;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a3;
  *v13 = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(
                           a3,
                           v8 + 2) )
  {
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v9;
    v11 = 13;
    goto LABEL_21;
  }
  v14 = 0;
  if ( v7 )
    v14 = a1[v7 - 1] == 92;
  while ( *v4 == 92 )
  {
    ++v4;
    --v6;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           a3,
                           a1,
                           v7) )
  {
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v9;
    v11 = 14;
    goto LABEL_21;
  }
  if ( !v14
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(a3, 92) )
  {
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v9;
    v11 = 15;
LABEL_21:
    v12 = 2147942414LL;
    goto LABEL_43;
  }
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(a3, v4, v6) )
    return 0;
  v9 = -2147024882;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 16;
    goto LABEL_21;
  }
  return v9;
}

```

## disassembly

```asm
0x14001c23c  push    rbx
0x14001c23e  push    rbp
0x14001c23f  push    rsi
0x14001c240  push    rdi
0x14001c241  push    r12
0x14001c243  push    r13
0x14001c245  push    r14
0x14001c247  push    r15
0x14001c249  sub     rsp, 28h
0x14001c24d  xor     r13d, r13d
0x14001c250  mov     r14, r8
0x14001c253  mov     rbp, rdx
0x14001c256  mov     r15, rcx
0x14001c259  test    rcx, rcx
0x14001c25c  jz      loc_14001C452
0x14001c262  cmp     [rcx], r13w
0x14001c266  jz      loc_14001C452
0x14001c26c  test    rdx, rdx
0x14001c26f  jz      loc_14001C452
0x14001c275  test    r8, r8
0x14001c278  jz      loc_14001C452
0x14001c27e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001c282  mov     rsi, rbx
0x14001c285  inc     rsi
0x14001c288  cmp     [rcx+rsi*2], r13w
0x14001c28d  jnz     short loc_14001C285
0x14001c28f  inc     rbx
0x14001c292  cmp     [rdx+rbx*2], r13w
0x14001c297  jnz     short loc_14001C28F
0x14001c299  lea     rax, [rsi+rbx]
0x14001c29d  cmp     rax, rsi
0x14001c2a0  jnb     short loc_14001C2DB
0x14001c2a2  mov     ebx, 80070216h
0x14001c2a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2ae  lea     rax, WPP_GLOBAL_Control
0x14001c2b5  cmp     rcx, rax
0x14001c2b8  jz      loc_14001C48E
0x14001c2be  mov     edi, 1
0x14001c2c3  test    [rcx+1Ch], dil
0x14001c2c7  jz      loc_14001C48E
0x14001c2cd  lea     edx, [rdi+0Ah]
0x14001c2d0  mov     r9d, 80070216h
0x14001c2d6  jmp     loc_14001C47E
0x14001c2db  lea     rdx, [rax+2]
0x14001c2df  cmp     rdx, 2
0x14001c2e3  jnb     short loc_14001C315
0x14001c2e5  mov     ebx, 80070216h
0x14001c2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2f1  lea     rax, WPP_GLOBAL_Control
0x14001c2f8  cmp     rcx, rax
0x14001c2fb  jz      loc_14001C48E
0x14001c301  mov     edi, 1
0x14001c306  test    [rcx+1Ch], dil
0x14001c30a  jz      loc_14001C48E
0x14001c310  lea     edx, [rdi+0Bh]
0x14001c313  jmp     short loc_14001C2D0
0x14001c315  mov     rcx, [r8]
0x14001c318  mov     [r8+8], rcx
0x14001c31c  mov     [rcx], r13w
0x14001c320  mov     rcx, r14
0x14001c323  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x14001c328  test    al, al
0x14001c32a  jnz     short loc_14001C365
0x14001c32c  mov     ebx, 8007000Eh
0x14001c331  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c338  lea     rax, WPP_GLOBAL_Control
0x14001c33f  cmp     rcx, rax
0x14001c342  jz      loc_14001C48E
0x14001c348  mov     edi, 1
0x14001c34d  test    [rcx+1Ch], dil
0x14001c351  jz      loc_14001C48E
0x14001c357  lea     edx, [rdi+0Ch]
0x14001c35a  mov     r9d, 8007000Eh
0x14001c360  jmp     loc_14001C47E
0x14001c365  mov     edi, 1
0x14001c36a  mov     r12d, r13d
0x14001c36d  lea     eax, [rdi+5Bh]
0x14001c370  test    rsi, rsi
0x14001c373  jz      short loc_14001C388
0x14001c375  cmp     [r15+rsi*2-2], ax
0x14001c37b  cmovz   r12d, edi
0x14001c37f  jmp     short loc_14001C388
0x14001c381  add     rbp, 2
0x14001c385  sub     rbx, rdi
0x14001c388  cmp     [rbp+0], ax
0x14001c38c  jz      short loc_14001C381
0x14001c38e  mov     r8, rsi
0x14001c391  mov     rdx, r15
0x14001c394  mov     rcx, r14
0x14001c397  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14001c39c  test    al, al
0x14001c39e  jnz     short loc_14001C3CD
0x14001c3a0  mov     ebx, 8007000Eh
0x14001c3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3ac  lea     rax, WPP_GLOBAL_Control
0x14001c3b3  cmp     rcx, rax
0x14001c3b6  jz      loc_14001C48E
0x14001c3bc  test    [rcx+1Ch], dil
0x14001c3c0  jz      loc_14001C48E
0x14001c3c6  mov     edx, 0Eh
0x14001c3cb  jmp     short loc_14001C35A
0x14001c3cd  test    r12d, r12d
0x14001c3d0  jnz     short loc_14001C413
0x14001c3d2  lea     edx, [r12+5Ch]
0x14001c3d7  mov     rcx, r14
0x14001c3da  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14001c3df  test    al, al
0x14001c3e1  jnz     short loc_14001C413
0x14001c3e3  mov     ebx, 8007000Eh
0x14001c3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3ef  lea     rax, WPP_GLOBAL_Control
0x14001c3f6  cmp     rcx, rax
0x14001c3f9  jz      loc_14001C48E
0x14001c3ff  test    [rcx+1Ch], dil
0x14001c403  jz      loc_14001C48E
0x14001c409  lea     edx, [r12+0Fh]
0x14001c40e  jmp     loc_14001C35A
0x14001c413  mov     r8, rbx
0x14001c416  mov     rdx, rbp
0x14001c419  mov     rcx, r14
0x14001c41c  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14001c421  test    al, al
0x14001c423  jnz     short loc_14001C44D
0x14001c425  mov     ebx, 8007000Eh
0x14001c42a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c431  lea     rax, WPP_GLOBAL_Control
0x14001c438  cmp     rcx, rax
0x14001c43b  jz      short loc_14001C48E
0x14001c43d  test    [rcx+1Ch], dil
0x14001c441  jz      short loc_14001C48E
0x14001c443  mov     edx, 10h
0x14001c448  jmp     loc_14001C35A
0x14001c44d  mov     ebx, r13d
0x14001c450  jmp     short loc_14001C48E
0x14001c452  mov     ebx, 80070057h
0x14001c457  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c45e  lea     rax, WPP_GLOBAL_Control
0x14001c465  cmp     rcx, rax
0x14001c468  jz      short loc_14001C48E
0x14001c46a  mov     edi, 1
0x14001c46f  test    [rcx+1Ch], dil
0x14001c473  jz      short loc_14001C48E
0x14001c475  lea     edx, [rdi+9]
0x14001c478  mov     r9d, 80070057h
0x14001c47e  mov     rcx, [rcx+10h]
0x14001c482  lea     r8, WPP_74b024c659e0370c20fde454c384f757_Traceguids
0x14001c489  call    WPP_SF_d
0x14001c48e  mov     eax, ebx
0x14001c490  add     rsp, 28h
0x14001c494  pop     r15
0x14001c496  pop     r14
0x14001c498  pop     r13
0x14001c49a  pop     r12
0x14001c49c  pop     rdi
0x14001c49d  pop     rsi
0x14001c49e  pop     rbp
0x14001c49f  pop     rbx
0x14001c4a0  retn
```
