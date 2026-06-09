# web::json::details::JSON_Parser<wchar_t>::CompleteNumberLiteral(wchar_t,web::json::details::JSON_Parser<wchar_t>::Token &)

- ea: `0x18002f1a4`
- end: `0x18002f69c`
- name: `?CompleteNumberLiteral@?$JSON_Parser@_W@details@json@web@@AEAA_N_WAEAUToken@1234@@Z`
- size: `1272`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e198`

## callees

- `0x18000f6a0`
- `0x18001bd64`
- `0x1800293d4`
- `0x18002f1a4`
- `0x180030cf4`
- `0x180030ff0`
- `0x180031a04`
- `0x180031b14`
- `0x180042628`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall web::json::details::JSON_Parser<wchar_t>::CompleteNumberLiteral(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3)
{
  unsigned __int16 v4; // bx
  char v6; // r13
  char v7; // di
  __int16 v8; // ax
  unsigned __int64 v9; // r14
  unsigned __int16 v10; // ax
  __int64 v11; // rbx
  char v12; // bl
  unsigned __int64 v13; // rax
  wchar_t v14; // r15
  __int64 v15; // rcx
  __int64 v17; // rax
  __crt_locale_pointers *Locale; // rax
  int v19; // eax
  char v20; // bl
  wchar_t *v21; // rdx
  wchar_t v22; // ax
  wchar_t v23; // cx
  wchar_t v24; // ax
  wchar_t *v25; // rdx
  wchar_t v26; // ax
  wchar_t *v27; // rbx
  struct __crt_locale_pointers *v28; // rax
  double v29; // xmm0_8
  __int16 v30; // [rsp+30h] [rbp-30h] BYREF
  char v31; // [rsp+32h] [rbp-2Eh]
  wchar_t *Buffer[2]; // [rsp+38h] [rbp-28h] BYREF
  wchar_t *v33; // [rsp+48h] [rbp-18h]
  __int64 v34; // [rsp+50h] [rbp-10h] BYREF

  v4 = a2;
  v6 = 0;
  if ( a2 == 45 )
  {
    v7 = 1;
    v31 = 1;
    v4 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
  }
  else
  {
    v7 = 0;
    v31 = 0;
  }
  if ( (unsigned __int16)(v4 - 48) > 9u )
    return 0;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v4 == 48 && v8 == 48 )
    return 0;
  v9 = v4 - 48LL;
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v10 >= 0x30u )
  {
    while ( v10 <= 0x39u )
    {
      v11 = (unsigned int)v10 - 48;
      if ( v9 > 0x1999999999999999LL || v9 == 0x1999999999999999LL && (unsigned int)v11 > 5 )
      {
        v12 = 0;
        goto LABEL_14;
      }
      (**(void (__fastcall ***)(__int64))a1)(a1);
      v9 = v11 + 10 * v9;
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      if ( v10 < 0x30u )
        break;
    }
  }
  v12 = 1;
LABEL_14:
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v14 = v13;
  if ( v12 )
  {
    LOWORD(v13) = v13 - 46;
    if ( (unsigned __int16)v13 > 0x37u || (v15 = 0x80000000800001LL, !_bittest64(&v15, v13)) )
    {
      if ( v7 )
      {
        *(_BYTE *)(a3 + 64) = 1;
        if ( v9 <= 0x8000000000000000uLL )
        {
          *(_QWORD *)(a3 + 56) = -(__int64)v9;
          *(_DWORD *)a3 = 9;
        }
        else
        {
          *(double *)(a3 + 56) = 0.0 - ((double)(int)(v9 & 1 | (v9 >> 1)) + (double)(int)(v9 & 1 | (v9 >> 1)));
          *(_DWORD *)a3 = 8;
        }
      }
      else
      {
        *(_QWORD *)(a3 + 56) = v9;
        *(_DWORD *)a3 = 9;
        *(_BYTE *)(a3 + 64) = 0;
      }
      return 1;
    }
  }
  v17 = std::_Allocate<16,std::_Default_allocate_traits>(48);
  Buffer[0] = (wchar_t *)v17;
  v33 = (wchar_t *)(v17 + 48);
  *(_OWORD *)v17 = 0;
  *(_OWORD *)(v17 + 16) = 0;
  *(_OWORD *)(v17 + 32) = 0;
  Buffer[1] = (wchar_t *)(v17 + 48);
  v34 = 0;
  std::_Tidy_guard<std::vector<wchar_t>>::~_Tidy_guard<std::vector<wchar_t>>(&v34);
  Locale = utility::details::scoped_c_thread_locale::c_locale();
  v19 = snwprintf_s_l(Buffer[0], Buffer[1] - Buffer[0], 0xFFFFFFFFFFFFFFFFuLL, L"%I64u", Locale, v9);
  std::vector<wchar_t>::resize(Buffer, v19);
  v20 = 0;
  if ( v14 == 0xFFFF )
    goto LABEL_59;
  while ( 1 )
  {
    if ( (unsigned __int16)(v14 - 48) <= 9u )
    {
      v30 = v14;
      v21 = Buffer[1];
      if ( Buffer[1] == v33 )
        goto LABEL_37;
      *Buffer[1] = v14;
      goto LABEL_36;
    }
    if ( v14 != 46 )
      break;
    if ( v20 )
      goto LABEL_65;
    v20 = 1;
    v30 = 46;
    if ( Buffer[1] == v33 )
      std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(Buffer, Buffer[1], &v30);
    else
      *Buffer[1]++ = 46;
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    if ( (unsigned __int16)(v22 - 48) > 9u )
      goto LABEL_65;
    v30 = v22;
    v21 = Buffer[1];
    if ( Buffer[1] == v33 )
    {
LABEL_37:
      std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(Buffer, v21, &v30);
      goto LABEL_38;
    }
    *Buffer[1] = v22;
LABEL_36:
    ++Buffer[1];
LABEL_38:
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    if ( v14 == 0xFFFF )
      goto LABEL_59;
  }
  if ( ((v14 - 69) & 0xFFDF) != 0 )
    goto LABEL_59;
  v30 = v14;
  if ( Buffer[1] == v33 )
    std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(Buffer, Buffer[1], &v30);
  else
    *Buffer[1]++ = v14;
  (**(void (__fastcall ***)(__int64))a1)(a1);
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v24 = 43;
  if ( v23 == 43 || (v24 = 45, v23 == 45) )
  {
    v30 = v24;
    if ( Buffer[1] == v33 )
      std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(Buffer, Buffer[1], &v30);
    else
      *Buffer[1]++ = v24;
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( (unsigned __int16)(v23 - 48) <= 9u )
  {
    v30 = v23;
    v25 = Buffer[1];
    if ( Buffer[1] == v33 )
      goto LABEL_57;
    *Buffer[1] = v23;
LABEL_56:
    ++Buffer[1];
    while ( 1 )
    {
      (**(void (__fastcall ***)(__int64))a1)(a1);
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      if ( v26 < 0x30u || v26 > 0x39u )
        break;
      v30 = v26;
      v25 = Buffer[1];
      if ( Buffer[1] != v33 )
      {
        *Buffer[1] = v26;
        goto LABEL_56;
      }
LABEL_57:
      std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(Buffer, v25, &v30);
    }
LABEL_59:
    v30 = 0;
    if ( Buffer[1] == v33 )
      std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(Buffer, Buffer[1], &v30);
    else
      *Buffer[1]++ = 0;
    v27 = Buffer[0];
    v28 = utility::details::scoped_c_thread_locale::c_locale();
    v29 = o__wcstod_l_0(v27, 0, v28);
    *(double *)(a3 + 56) = v29;
    if ( v31 )
      *(_QWORD *)(a3 + 56) = *(_QWORD *)&v29 ^ _xmm;
    *(_DWORD *)a3 = 8;
    v6 = 1;
  }
LABEL_65:
  std::vector<wchar_t>::~vector<wchar_t>(Buffer);
  return v6;
}

```

## disassembly

```asm
0x18002f1a4  mov     [rsp-38h+arg_18], rbx
0x18002f1a9  push    rbp
0x18002f1aa  push    rsi
0x18002f1ab  push    rdi
0x18002f1ac  push    r12
0x18002f1ae  push    r13
0x18002f1b0  push    r14
0x18002f1b2  push    r15
0x18002f1b4  mov     rbp, rsp
0x18002f1b7  sub     rsp, 60h
0x18002f1bb  mov     r12, r8
0x18002f1be  movzx   ebx, dx
0x18002f1c1  mov     rsi, rcx
0x18002f1c4  xor     r13d, r13d
0x18002f1c7  lea     eax, [r13+2Dh]
0x18002f1cb  cmp     dx, ax
0x18002f1ce  jnz     short loc_18002F1E7
0x18002f1d0  mov     dil, 1
0x18002f1d3  mov     [rbp+var_2E], dil
0x18002f1d7  mov     rax, [rcx]
0x18002f1da  mov     rax, [rax]
0x18002f1dd  call    _guard_dispatch_icall
0x18002f1e2  movzx   ebx, ax
0x18002f1e5  jmp     short loc_18002F1EE
0x18002f1e7  mov     dil, r13b
0x18002f1ea  mov     [rbp+var_2E], r13b
0x18002f1ee  movzx   eax, bx
0x18002f1f1  mov     r15d, 30h ; '0'
0x18002f1f7  sub     ax, r15w
0x18002f1fb  lea     ecx, [r15-27h]
0x18002f1ff  cmp     ax, cx
0x18002f202  ja      loc_18002F682
0x18002f208  mov     rax, [rsi]
0x18002f20b  mov     rcx, rsi
0x18002f20e  mov     rax, [rax+8]
0x18002f212  call    _guard_dispatch_icall
0x18002f217  cmp     bx, r15w
0x18002f21b  jnz     short loc_18002F227
0x18002f21d  cmp     ax, r15w
0x18002f221  jz      loc_18002F682
0x18002f227  movzx   r14d, bx
0x18002f22b  sub     r14, r15
0x18002f22e  mov     rax, [rsi]
0x18002f231  mov     rcx, rsi
0x18002f234  mov     rax, [rax+8]
0x18002f238  call    _guard_dispatch_icall
0x18002f23d  cmp     ax, r15w
0x18002f241  jb      short loc_18002F2A2
0x18002f243  mov     rcx, 1999999999999999h
0x18002f24d  cmp     ax, 39h ; '9'
0x18002f251  ja      short loc_18002F2A2
0x18002f253  movzx   ebx, ax
0x18002f256  sub     ebx, r15d
0x18002f259  cmp     r14, rcx
0x18002f25c  ja      loc_18002F30A
0x18002f262  jnz     short loc_18002F26D
0x18002f264  cmp     ebx, 5
0x18002f267  ja      loc_18002F30A
0x18002f26d  mov     rax, [rsi]
0x18002f270  mov     rcx, rsi
0x18002f273  mov     rax, [rax]
0x18002f276  call    _guard_dispatch_icall
0x18002f27b  lea     rcx, [r14+r14*4]
0x18002f27f  lea     r14, [rbx+rcx*2]
0x18002f283  mov     rax, [rsi]
0x18002f286  mov     rcx, rsi
0x18002f289  mov     rax, [rax+8]
0x18002f28d  call    _guard_dispatch_icall
0x18002f292  cmp     ax, r15w
0x18002f296  mov     rcx, 1999999999999999h
0x18002f2a0  jnb     short loc_18002F24D
0x18002f2a2  mov     bl, 1
0x18002f2a4  mov     rax, [rsi]
0x18002f2a7  mov     rcx, rsi
0x18002f2aa  mov     rax, [rax+8]
0x18002f2ae  call    _guard_dispatch_icall
0x18002f2b3  movzx   r15d, ax
0x18002f2b7  mov     ecx, 2Eh ; '.'
0x18002f2bc  test    bl, bl
0x18002f2be  jz      loc_18002F368
0x18002f2c4  sub     ax, cx
0x18002f2c7  cmp     ax, 37h ; '7'
0x18002f2cb  ja      short loc_18002F2E1
0x18002f2cd  mov     rcx, 80000000800001h
0x18002f2d7  bt      rcx, rax
0x18002f2db  jb      loc_18002F368
0x18002f2e1  test    dil, dil
0x18002f2e4  jz      short loc_18002F354
0x18002f2e6  mov     byte ptr [r12+40h], 1
0x18002f2ec  mov     rax, 8000000000000000h
0x18002f2f6  cmp     r14, rax
0x18002f2f9  jbe     short loc_18002F342
0x18002f2fb  xorps   xmm1, xmm1
0x18002f2fe  test    r14, r14
0x18002f301  js      short loc_18002F30F
0x18002f303  cvtsi2sd xmm1, r14
0x18002f308  jmp     short loc_18002F325
0x18002f30a  mov     bl, r13b
0x18002f30d  jmp     short loc_18002F2A4
0x18002f30f  mov     rcx, r14
0x18002f312  shr     rcx, 1
0x18002f315  and     r14d, 1
0x18002f319  or      rcx, r14
0x18002f31c  cvtsi2sd xmm1, rcx
0x18002f321  addsd   xmm1, xmm1
0x18002f325  xorps   xmm0, xmm0
0x18002f328  subsd   xmm0, xmm1
0x18002f32c  movsd   qword ptr [r12+38h], xmm0
0x18002f333  mov     dword ptr [r12], 8
0x18002f33b  mov     al, 1
0x18002f33d  jmp     loc_18002F684
0x18002f342  neg     r14
0x18002f345  mov     [r12+38h], r14
0x18002f34a  mov     dword ptr [r12], 9
0x18002f352  jmp     short loc_18002F33B
0x18002f354  mov     [r12+38h], r14
0x18002f359  mov     dword ptr [r12], 9
0x18002f361  mov     [r12+40h], r13b
0x18002f366  jmp     short loc_18002F33B
0x18002f368  xorps   xmm1, xmm1
0x18002f36b  movdqu  xmmword ptr [rbp+Buffer], xmm1
0x18002f370  mov     [rbp+var_18], r13
0x18002f374  mov     ecx, 30h ; '0'
0x18002f379  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002f37e  mov     [rbp+Buffer], rax
0x18002f382  lea     rcx, [rax+30h]
0x18002f386  mov     [rbp+var_18], rcx
0x18002f38a  xorps   xmm0, xmm0
0x18002f38d  movups  xmmword ptr [rax], xmm0
0x18002f390  movups  xmmword ptr [rax+10h], xmm0
0x18002f394  movups  xmmword ptr [rax+20h], xmm0
0x18002f398  mov     [rbp+Buffer+8], rcx
0x18002f39c  mov     [rbp+var_10], r13
0x18002f3a0  lea     rcx, [rbp+var_10]
0x18002f3a4  call    ??1?$_Tidy_guard@V?$vector@_WV?$allocator@_W@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<wchar_t>>::~_Tidy_guard<std::vector<wchar_t>>(void)
0x18002f3a9  nop
0x18002f3aa  mov     rdi, [rbp+Buffer]
0x18002f3ae  mov     rbx, [rbp+Buffer+8]
0x18002f3b2  sub     rbx, rdi
0x18002f3b5  sar     rbx, 1
0x18002f3b8  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x18002f3bd  mov     [rsp+60h+var_38], r14
0x18002f3c2  mov     [rsp+60h+Locale], rax; Locale
0x18002f3c7  lea     r9, aI64u_0; "%I64u"
0x18002f3ce  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002f3d2  mov     rdx, rbx; BufferCount
0x18002f3d5  mov     rcx, rdi; Buffer
0x18002f3d8  call    _snwprintf_s_l
0x18002f3dd  movsxd  rdx, eax
0x18002f3e0  lea     rcx, [rbp+Buffer]
0x18002f3e4  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_K@Z; std::vector<wchar_t>::resize(unsigned __int64)
0x18002f3e9  mov     bl, r13b
0x18002f3ec  mov     eax, 0FFFFh
0x18002f3f1  cmp     r15w, ax
0x18002f3f5  jz      loc_18002F611
0x18002f3fb  mov     edi, 30h ; '0'
0x18002f400  lea     r14d, [rdi-27h]
0x18002f404  movzx   eax, r15w
0x18002f408  sub     ax, di
0x18002f40b  cmp     ax, r14w
0x18002f40f  ja      short loc_18002F42A
0x18002f411  mov     [rbp+var_30], r15w
0x18002f416  mov     rdx, [rbp+Buffer+8]
0x18002f41a  cmp     rdx, [rbp+var_18]
0x18002f41e  jz      loc_18002F4AD
0x18002f424  mov     [rdx], r15w
0x18002f428  jmp     short loc_18002F4A6
0x18002f42a  mov     eax, 2Eh ; '.'
0x18002f42f  cmp     r15w, ax
0x18002f433  jnz     loc_18002F4EF
0x18002f439  test    bl, bl
0x18002f43b  jnz     loc_18002F674
0x18002f441  mov     bl, 1
0x18002f443  mov     [rbp+var_30], ax
0x18002f447  mov     rdx, [rbp+Buffer+8]
0x18002f44b  cmp     rdx, [rbp+var_18]
0x18002f44f  jz      short loc_18002F45B
0x18002f451  mov     [rdx], ax
0x18002f454  add     [rbp+Buffer+8], 2
0x18002f459  jmp     short loc_18002F468
0x18002f45b  lea     r8, [rbp+var_30]
0x18002f45f  lea     rcx, [rbp+Buffer]
0x18002f463  call    ??$_Emplace_reallocate@_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_W$$QEA_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(wchar_t * const,wchar_t &&)
0x18002f468  mov     rax, [rsi]
0x18002f46b  mov     rcx, rsi
0x18002f46e  mov     rax, [rax]
0x18002f471  call    _guard_dispatch_icall
0x18002f476  mov     rax, [rsi]
0x18002f479  mov     rcx, rsi
0x18002f47c  mov     rax, [rax+8]
0x18002f480  call    _guard_dispatch_icall
0x18002f485  movzx   ecx, ax
0x18002f488  sub     cx, di
0x18002f48b  cmp     cx, r14w
0x18002f48f  ja      loc_18002F674
0x18002f495  mov     [rbp+var_30], ax
0x18002f499  mov     rdx, [rbp+Buffer+8]
0x18002f49d  cmp     rdx, [rbp+var_18]
0x18002f4a1  jz      short loc_18002F4AD
0x18002f4a3  mov     [rdx], ax
0x18002f4a6  add     [rbp+Buffer+8], 2
0x18002f4ab  jmp     short loc_18002F4BA
0x18002f4ad  lea     r8, [rbp+var_30]
0x18002f4b1  lea     rcx, [rbp+Buffer]
0x18002f4b5  call    ??$_Emplace_reallocate@_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_W$$QEA_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(wchar_t * const,wchar_t &&)
0x18002f4ba  mov     rax, [rsi]
0x18002f4bd  mov     rcx, rsi
0x18002f4c0  mov     rax, [rax]
0x18002f4c3  call    _guard_dispatch_icall
0x18002f4c8  mov     rax, [rsi]
0x18002f4cb  mov     rcx, rsi
0x18002f4ce  mov     rax, [rax+8]
0x18002f4d2  call    _guard_dispatch_icall
0x18002f4d7  movzx   r15d, ax
0x18002f4db  mov     eax, 0FFFFh
0x18002f4e0  cmp     r15w, ax
0x18002f4e4  jnz     loc_18002F404
0x18002f4ea  jmp     loc_18002F611
0x18002f4ef  lea     eax, [r15-45h]
0x18002f4f3  mov     ecx, 0FFDFh
0x18002f4f8  test    cx, ax
0x18002f4fb  jnz     loc_18002F611
0x18002f501  mov     [rbp+var_30], r15w
0x18002f506  mov     rdx, [rbp+Buffer+8]
0x18002f50a  cmp     rdx, [rbp+var_18]
0x18002f50e  jz      short loc_18002F51B
0x18002f510  mov     [rdx], r15w
0x18002f514  add     [rbp+Buffer+8], 2
0x18002f519  jmp     short loc_18002F528
0x18002f51b  lea     r8, [rbp+var_30]
0x18002f51f  lea     rcx, [rbp+Buffer]
0x18002f523  call    ??$_Emplace_reallocate@_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_W$$QEA_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(wchar_t * const,wchar_t &&)
0x18002f528  mov     rax, [rsi]
0x18002f52b  mov     rcx, rsi
0x18002f52e  mov     rax, [rax]
0x18002f531  call    _guard_dispatch_icall
0x18002f536  mov     rax, [rsi]
0x18002f539  mov     rcx, rsi
0x18002f53c  mov     rax, [rax+8]
0x18002f540  call    _guard_dispatch_icall
0x18002f545  movzx   ecx, ax
0x18002f548  mov     eax, 2Bh ; '+'
0x18002f54d  cmp     cx, ax
0x18002f550  jz      short loc_18002F55C
0x18002f552  mov     eax, 2Dh ; '-'
0x18002f557  cmp     cx, ax
0x18002f55a  jnz     short loc_18002F5A1
0x18002f55c  mov     [rbp+var_30], ax
0x18002f560  mov     rdx, [rbp+Buffer+8]
0x18002f564  cmp     rdx, [rbp+var_18]
0x18002f568  jz      short loc_18002F574
0x18002f56a  mov     [rdx], ax
0x18002f56d  add     [rbp+Buffer+8], 2
0x18002f572  jmp     short loc_18002F581
0x18002f574  lea     r8, [rbp+var_30]
0x18002f578  lea     rcx, [rbp+Buffer]
0x18002f57c  call    ??$_Emplace_reallocate@_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_W$$QEA_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(wchar_t * const,wchar_t &&)
0x18002f581  mov     rax, [rsi]
0x18002f584  mov     rcx, rsi
0x18002f587  mov     rax, [rax]
0x18002f58a  call    _guard_dispatch_icall
0x18002f58f  mov     rax, [rsi]
0x18002f592  mov     rcx, rsi
0x18002f595  mov     rax, [rax+8]
0x18002f599  call    _guard_dispatch_icall
0x18002f59e  movzx   ecx, ax
0x18002f5a1  movzx   eax, cx
0x18002f5a4  sub     ax, di
0x18002f5a7  cmp     ax, r14w
0x18002f5ab  ja      loc_18002F674
0x18002f5b1  mov     [rbp+var_30], cx
0x18002f5b5  mov     rdx, [rbp+Buffer+8]
0x18002f5b9  cmp     rdx, [rbp+var_18]
0x18002f5bd  jz      short loc_18002F5E2
0x18002f5bf  mov     [rdx], cx
0x18002f5c2  jmp     short loc_18002F5DB
0x18002f5c4  cmp     ax, 39h ; '9'
0x18002f5c8  ja      short loc_18002F611
0x18002f5ca  mov     [rbp+var_30], ax
0x18002f5ce  mov     rdx, [rbp+Buffer+8]
0x18002f5d2  cmp     rdx, [rbp+var_18]
0x18002f5d6  jz      short loc_18002F5E2
0x18002f5d8  mov     [rdx], ax
0x18002f5db  add     [rbp+Buffer+8], 2
0x18002f5e0  jmp     short loc_18002F5EF
0x18002f5e2  lea     r8, [rbp+var_30]
0x18002f5e6  lea     rcx, [rbp+Buffer]
0x18002f5ea  call    ??$_Emplace_reallocate@_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_W$$QEA_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(wchar_t * const,wchar_t &&)
0x18002f5ef  mov     rax, [rsi]
0x18002f5f2  mov     rcx, rsi
0x18002f5f5  mov     rax, [rax]
0x18002f5f8  call    _guard_dispatch_icall
0x18002f5fd  mov     rax, [rsi]
0x18002f600  mov     rcx, rsi
0x18002f603  mov     rax, [rax+8]
0x18002f607  call    _guard_dispatch_icall
0x18002f60c  cmp     ax, di
0x18002f60f  jnb     short loc_18002F5C4
0x18002f611  mov     [rbp+var_30], r13w
0x18002f616  mov     rdx, [rbp+Buffer+8]
  ... truncated ...
```
