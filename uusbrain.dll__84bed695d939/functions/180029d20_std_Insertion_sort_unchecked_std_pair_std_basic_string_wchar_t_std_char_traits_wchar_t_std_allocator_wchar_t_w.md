# std::_Insertion_sort_unchecked<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> *,bool (*)(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> const &,std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> const &)>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> * const,std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> * const,bool (*)(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> const &,std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> const &))

- ea: `0x180029d20`
- end: `0x180029fa9`
- name: `??$_Insertion_sort_unchecked@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@QEAU10@0P6A_NAEBU10@1@Z@Z`
- size: `649`
- prototype: `_OWORD *__fastcall(__int64, _OWORD *, unsigned __int8 (__fastcall *)(__int128 *, __int128 *))`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002a57c`

## callees

- `0x180029644`
- `0x180029d20`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
_OWORD *__fastcall std::_Insertion_sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        __int64 a1,
        _OWORD *a2,
        unsigned __int8 (__fastcall *a3)(__int128 *, __int128 *))
{
  _OWORD *v4; // r12
  _OWORD *v6; // r14
  __int64 *v7; // rbx
  __m128i si128; // xmm6
  __int128 *v9; // rdi
  __int64 v10; // rax
  __int128 *v11; // r15
  __int64 *v12; // rbx
  __int64 *v13; // rdx
  __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // rcx
  __int128 *v17; // r15
  __int64 *v18; // rdi
  __int64 v19; // rcx
  __int64 *v20; // rdi
  __int64 *v23; // [rsp+28h] [rbp-48h]
  __int128 v24; // [rsp+30h] [rbp-40h] BYREF
  __m128i v25; // [rsp+40h] [rbp-30h]
  __int64 v26; // [rsp+50h] [rbp-20h] BYREF

  v4 = a2;
  if ( (_OWORD *)a1 != a2 )
  {
    v6 = (_OWORD *)(a1 + 40);
    if ( (_OWORD *)(a1 + 40) != a2 )
    {
      v7 = (__int64 *)(a1 + 32);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v9 = v6;
        v24 = *v6;
        v25 = *((__m128i *)v6 + 1);
        v7[3] = 0;
        v7[4] = 7;
        *(_WORD *)v6 = 0;
        v23 = v7 + 5;
        v10 = v7[5];
        v7[5] = 0;
        v26 = v10;
        if ( a3(&v24, (__int128 *)a1) )
        {
          v11 = (__int128 *)(v7 + 6);
          if ( (_OWORD *)a1 != v6 )
          {
            v12 = v7 + 10;
            do
            {
              v9 = (__int128 *)((char *)v9 - 40);
              v11 = (__int128 *)((char *)v11 - 40);
              v12 -= 5;
              if ( v11 != v9 )
              {
                std::wstring::_Tidy_deallocate(v11);
                *v11 = *v9;
                v11[1] = v9[1];
                *((_QWORD *)v9 + 2) = 0;
                *((_QWORD *)v9 + 3) = 7;
                *(_WORD *)v9 = 0;
              }
              v13 = (__int64 *)(v9 + 2);
              if ( v12 != (__int64 *)(v9 + 2) )
              {
                v14 = *v12;
                *v12 = *v13;
                *v13 = v14;
              }
            }
            while ( (__int128 *)a1 != v9 );
            v4 = a2;
          }
          if ( (__int128 *)a1 != &v24 )
          {
            std::wstring::_Tidy_deallocate(a1);
            *(_OWORD *)a1 = v24;
            *(__m128i *)(a1 + 16) = v25;
            v25 = si128;
            LOWORD(v24) = 0;
          }
          v15 = (__int64 *)(a1 + 32);
          if ( (__int64 *)(a1 + 32) == &v26 )
            goto LABEL_29;
          v16 = *v15;
          *v15 = v26;
        }
        else
        {
          v17 = (__int128 *)(v7 - 4);
          if ( a3(&v24, (__int128 *)v7 - 2) )
          {
            do
            {
              if ( v9 != v17 )
              {
                std::wstring::_Tidy_deallocate(v9);
                *v9 = *v17;
                v9[1] = v17[1];
                *(v7 - 2) = 0;
                *(v7 - 1) = 7;
                *(_WORD *)v17 = 0;
              }
              v18 = (__int64 *)(v9 + 2);
              if ( v18 != v7 )
              {
                v19 = *v18;
                *v18 = *v7;
                *v7 = v19;
              }
              v9 = v17;
              v17 = (__int128 *)((char *)v17 - 40);
              v7 -= 5;
            }
            while ( a3(&v24, v17) );
            v4 = a2;
          }
          if ( v9 != &v24 )
          {
            std::wstring::_Tidy_deallocate(v9);
            *v9 = v24;
            v9[1] = (__int128)v25;
            v25 = si128;
            LOWORD(v24) = 0;
          }
          v20 = (__int64 *)(v9 + 2);
          if ( v20 == &v26 )
          {
LABEL_29:
            v16 = v26;
            goto LABEL_30;
          }
          v16 = *v20;
          *v20 = v26;
        }
        v26 = v16;
LABEL_30:
        if ( v16 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 192LL))(v16, 1);
        std::wstring::_Tidy_deallocate(&v24);
        v6 = (_OWORD *)((char *)v6 + 40);
        v7 = v23;
      }
      while ( v6 != v4 );
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180029d20  mov     [rsp-38h+arg_8], rbx
0x180029d25  push    rbp
0x180029d26  push    rsi
0x180029d27  push    rdi
0x180029d28  push    r12
0x180029d2a  push    r13
0x180029d2c  push    r14
0x180029d2e  push    r15
0x180029d30  mov     rbp, rsp
0x180029d33  sub     rsp, 70h
0x180029d37  movaps  [rsp+70h+var_10], xmm6
0x180029d3c  mov     rax, cs:__security_cookie
0x180029d43  xor     rax, rsp
0x180029d46  mov     [rbp+var_18], rax
0x180029d4a  mov     r13, r8
0x180029d4d  mov     r12, rdx
0x180029d50  mov     [rbp+var_50], rdx
0x180029d54  mov     rsi, rcx
0x180029d57  cmp     rcx, rdx
0x180029d5a  jz      loc_180029F7D
0x180029d60  lea     r14, [rcx+28h]
0x180029d64  cmp     r14, rdx
0x180029d67  jz      loc_180029F7D
0x180029d6d  lea     rbx, [r14-8]
0x180029d71  xor     r15d, r15d
0x180029d74  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180029d7c  mov     rdi, r14
0x180029d7f  movups  xmm1, xmmword ptr [r14]
0x180029d83  movups  [rbp+var_40], xmm1
0x180029d87  movups  xmm0, xmmword ptr [r14+10h]
0x180029d8c  movups  [rbp+var_30], xmm0
0x180029d90  mov     [rbx+18h], r15
0x180029d94  mov     qword ptr [rbx+20h], 7
0x180029d9c  mov     [r14], r15w
0x180029da0  lea     rcx, [rbx+28h]
0x180029da4  mov     [rbp+var_48], rcx
0x180029da8  mov     rax, [rcx]
0x180029dab  mov     [rcx], r15
0x180029dae  mov     [rbp+var_20], rax
0x180029db2  mov     rdx, rsi
0x180029db5  lea     rcx, [rbp+var_40]
0x180029db9  mov     rax, r13
0x180029dbc  call    _guard_dispatch_icall
0x180029dc1  test    al, al
0x180029dc3  jz      loc_180029E7F
0x180029dc9  lea     r15, [rbx+30h]
0x180029dcd  cmp     rsi, r14
0x180029dd0  jz      short loc_180029E30
0x180029dd2  add     rbx, 50h ; 'P'
0x180029dd6  xor     r12d, r12d
0x180029dd9  add     rdi, 0FFFFFFFFFFFFFFD8h
0x180029ddd  sub     r15, 28h ; '('
0x180029de1  sub     rbx, 28h ; '('
0x180029de5  cmp     r15, rdi
0x180029de8  jz      short loc_180029E12
0x180029dea  mov     rcx, r15
0x180029ded  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029df2  movups  xmm0, xmmword ptr [rdi]
0x180029df5  movups  xmmword ptr [r15], xmm0
0x180029df9  movups  xmm1, xmmword ptr [rdi+10h]
0x180029dfd  movups  xmmword ptr [r15+10h], xmm1
0x180029e02  mov     [rdi+10h], r12
0x180029e06  mov     qword ptr [rdi+18h], 7
0x180029e0e  mov     [rdi], r12w
0x180029e12  lea     rdx, [rdi+20h]
0x180029e16  cmp     rbx, rdx
0x180029e19  jz      short loc_180029E27
0x180029e1b  mov     rcx, [rbx]
0x180029e1e  mov     rax, [rdx]
0x180029e21  mov     [rbx], rax
0x180029e24  mov     [rdx], rcx
0x180029e27  cmp     rsi, rdi
0x180029e2a  jnz     short loc_180029DD9
0x180029e2c  mov     r12, [rbp+var_50]
0x180029e30  lea     rax, [rbp+var_40]
0x180029e34  cmp     rsi, rax
0x180029e37  jz      short loc_180029E5B
0x180029e39  mov     rcx, rsi
0x180029e3c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029e41  movups  xmm0, [rbp+var_40]
0x180029e45  movups  xmmword ptr [rsi], xmm0
0x180029e48  movups  xmm1, [rbp+var_30]
0x180029e4c  movups  xmmword ptr [rsi+10h], xmm1
0x180029e50  movdqu  [rbp+var_30], xmm6
0x180029e55  xor     ecx, ecx
0x180029e57  mov     word ptr [rbp+var_40], cx
0x180029e5b  lea     rdx, [rsi+20h]
0x180029e5f  lea     rax, [rbp+var_20]
0x180029e63  cmp     rdx, rax
0x180029e66  jz      loc_180029F44
0x180029e6c  mov     rcx, [rdx]
0x180029e6f  mov     rax, [rbp+var_20]
0x180029e73  mov     [rdx], rax
0x180029e76  mov     [rbp+var_20], rcx
0x180029e7a  jmp     loc_180029F48
0x180029e7f  lea     r15, [rbx-20h]
0x180029e83  mov     rdx, r15
0x180029e86  lea     rcx, [rbp+var_40]
0x180029e8a  mov     rax, r13
0x180029e8d  call    _guard_dispatch_icall
0x180029e92  test    al, al
0x180029e94  jz      short loc_180029EFD
0x180029e96  xor     r12d, r12d
0x180029e99  cmp     rdi, r15
0x180029e9c  jz      short loc_180029EC6
0x180029e9e  mov     rcx, rdi
0x180029ea1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029ea6  movups  xmm0, xmmword ptr [r15]
0x180029eaa  movups  xmmword ptr [rdi], xmm0
0x180029ead  movups  xmm1, xmmword ptr [r15+10h]
0x180029eb2  movups  xmmword ptr [rdi+10h], xmm1
0x180029eb6  mov     [rbx-10h], r12
0x180029eba  mov     qword ptr [rbx-8], 7
0x180029ec2  mov     [r15], r12w
0x180029ec6  add     rdi, 20h ; ' '
0x180029eca  cmp     rdi, rbx
0x180029ecd  jz      short loc_180029EDB
0x180029ecf  mov     rcx, [rdi]
0x180029ed2  mov     rax, [rbx]
0x180029ed5  mov     [rdi], rax
0x180029ed8  mov     [rbx], rcx
0x180029edb  mov     rdi, r15
0x180029ede  sub     r15, 28h ; '('
0x180029ee2  sub     rbx, 28h ; '('
0x180029ee6  mov     rdx, r15
0x180029ee9  lea     rcx, [rbp+var_40]
0x180029eed  mov     rax, r13
0x180029ef0  call    _guard_dispatch_icall
0x180029ef5  test    al, al
0x180029ef7  jnz     short loc_180029E99
0x180029ef9  mov     r12, [rbp+var_50]
0x180029efd  lea     rax, [rbp+var_40]
0x180029f01  cmp     rdi, rax
0x180029f04  jz      short loc_180029F28
0x180029f06  mov     rcx, rdi
0x180029f09  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029f0e  movups  xmm0, [rbp+var_40]
0x180029f12  movups  xmmword ptr [rdi], xmm0
0x180029f15  movups  xmm1, [rbp+var_30]
0x180029f19  movups  xmmword ptr [rdi+10h], xmm1
0x180029f1d  movdqu  [rbp+var_30], xmm6
0x180029f22  xor     eax, eax
0x180029f24  mov     word ptr [rbp+var_40], ax
0x180029f28  add     rdi, 20h ; ' '
0x180029f2c  lea     rax, [rbp+var_20]
0x180029f30  cmp     rdi, rax
0x180029f33  jz      short loc_180029F44
0x180029f35  mov     rcx, [rdi]
0x180029f38  mov     rax, [rbp+var_20]
0x180029f3c  mov     [rdi], rax
0x180029f3f  jmp     loc_180029E76
0x180029f44  mov     rcx, [rbp+var_20]
0x180029f48  xor     r15d, r15d
0x180029f4b  test    rcx, rcx
0x180029f4e  jz      short loc_180029F63
0x180029f50  mov     rax, [rcx]
0x180029f53  lea     edx, [r15+1]
0x180029f57  mov     rax, [rax+0C0h]
0x180029f5e  call    _guard_dispatch_icall
0x180029f63  lea     rcx, [rbp+var_40]
0x180029f67  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029f6c  add     r14, 28h ; '('
0x180029f70  mov     rbx, [rbp+var_48]
0x180029f74  cmp     r14, r12
0x180029f77  jnz     loc_180029D7C
0x180029f7d  mov     rax, r12
0x180029f80  mov     rcx, [rbp+var_18]
0x180029f84  xor     rcx, rsp; StackCookie
0x180029f87  call    __security_check_cookie
0x180029f8c  mov     rbx, [rsp+70h+arg_8]
0x180029f94  movaps  xmm6, [rsp+70h+var_10]
0x180029f99  add     rsp, 70h
0x180029f9d  pop     r15
0x180029f9f  pop     r14
0x180029fa1  pop     r13
0x180029fa3  pop     r12
0x180029fa5  pop     rdi
0x180029fa6  pop     rsi
0x180029fa7  pop     rbp
0x180029fa8  retn
```
