# std::_Sort_unchecked<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> *,bool (*)(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> const &,std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> const &)>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> *,std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> *,__int64,bool (*)(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> const &,std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,web::json::value> const &))

- ea: `0x18002a57c`
- end: `0x18002a844`
- name: `??$_Sort_unchecked@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z`
- size: `712`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002a57c`
- `0x180030358`
- `0x180030844`

## callees

- `0x180029644`
- `0x180029d20`
- `0x180029fb0`
- `0x18002a300`
- `0x18002a57c`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 result; // rax
  __int64 v9; // r14
  __int64 v10; // r15
  __int64 v11; // rsi
  __int64 v12; // r14
  _QWORD *v13; // r13
  __int64 v14; // rax
  _QWORD *v15; // rdi
  _OWORD *v16; // rsi
  __int64 v17; // rax
  _QWORD *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // [rsp+30h] [rbp-48h] BYREF
  __int64 v21; // [rsp+38h] [rbp-40h]
  __int128 v22; // [rsp+40h] [rbp-38h] BYREF
  __int128 v23; // [rsp+50h] [rbp-28h]
  __int64 v24; // [rsp+60h] [rbp-18h]

  v6 = a2;
  v7 = a1;
  result = a2 - a1;
  if ( a2 - a1 < 1320 )
    return std::_Insertion_sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
             v7,
             v6,
             a4);
  while ( a3 > 0 )
  {
    std::_Partition_by_median_guess_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
      &v20,
      v7,
      v6,
      a4);
    a3 = (a3 >> 2) + (a3 >> 1);
    v9 = v21;
    v10 = v20;
    if ( (__int64)(0xCCCCCCCCCCCCCCCDuLL * ((v20 - v7) >> 3)) >= (__int64)(0xCCCCCCCCCCCCCCCDuLL * ((v6 - v21) >> 3)) )
    {
      std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        v21,
        v6,
        a3,
        a4);
      v6 = v10;
    }
    else
    {
      std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        v7,
        v20,
        a3,
        a4);
      v7 = v9;
    }
    result = v6 - v7;
    if ( v6 - v7 < 1320 )
      return std::_Insertion_sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
               v7,
               v6,
               a4);
  }
  v11 = v6 - v7;
  v12 = (__int64)(0xCCCCCCCCCCCCCCCDuLL * ((v6 - v7) >> 3)) >> 1;
  if ( v12 > 0 )
  {
    v13 = (_QWORD *)(v7 + 8 * (v12 + 4 * (v12 + 1)));
    do
    {
      --v12;
      v13 -= 5;
      v22 = *((_OWORD *)v13 - 2);
      v23 = *((_OWORD *)v13 - 1);
      *(v13 - 2) = 0;
      *(v13 - 1) = 7;
      *((_WORD *)v13 - 16) = 0;
      v14 = *v13;
      *v13 = 0;
      v24 = v14;
      std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        v7,
        v12,
        -858993459 * ((v6 - v7) >> 3),
        (unsigned int)&v22,
        a4);
      if ( v24 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 192LL))(v24, 1);
      result = std::wstring::_Tidy_deallocate(&v22);
    }
    while ( v12 > 0 );
  }
  if ( (__int64)(0xCCCCCCCCCCCCCCCDuLL * ((v6 - v7) >> 3)) >= 2 )
  {
    v15 = (_QWORD *)(v6 - 8);
    do
    {
      if ( (__int64)(0xCCCCCCCCCCCCCCCDuLL * (v11 >> 3)) >= 2 )
      {
        v16 = v15 - 4;
        v22 = *((_OWORD *)v15 - 2);
        v23 = *((_OWORD *)v15 - 1);
        *(v15 - 2) = 0;
        *(v15 - 1) = 7;
        *((_WORD *)v15 - 16) = 0;
        v17 = *v15;
        *v15 = 0;
        v24 = v17;
        if ( v15 - 4 != (_QWORD *)v7 )
        {
          std::wstring::_Tidy_deallocate(v15 - 4);
          *v16 = *(_OWORD *)v7;
          v16[1] = *(_OWORD *)(v7 + 16);
          *(_QWORD *)(v7 + 16) = 0;
          *(_QWORD *)(v7 + 24) = 7;
          *(_WORD *)v7 = 0;
        }
        v18 = (_QWORD *)(v7 + 32);
        if ( v15 != (_QWORD *)(v7 + 32) )
        {
          v19 = *v15;
          *v15 = *v18;
          *v18 = v19;
        }
        std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
          v7,
          0,
          -858993459 * (((__int64)v16 - v7) >> 3),
          (unsigned int)&v22,
          a4);
        if ( v24 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 192LL))(v24, 1);
        result = std::wstring::_Tidy_deallocate(&v22);
      }
      v15 -= 5;
      v11 = (__int64)v15 - v7 + 8;
    }
    while ( v11 >= 80 );
  }
  return result;
}

```

## disassembly

```asm
0x18002a57c  push    rbp
0x18002a57e  push    rbx
0x18002a57f  push    rsi
0x18002a580  push    rdi
0x18002a581  push    r12
0x18002a583  push    r13
0x18002a585  push    r14
0x18002a587  push    r15
0x18002a589  mov     rbp, rsp
0x18002a58c  sub     rsp, 78h
0x18002a590  mov     rax, cs:__security_cookie
0x18002a597  xor     rax, rsp
0x18002a59a  mov     [rbp+var_10], rax
0x18002a59e  mov     r12, r9
0x18002a5a1  mov     rsi, r8
0x18002a5a4  mov     rdi, rdx
0x18002a5a7  mov     rbx, rcx
0x18002a5aa  mov     rax, rdx
0x18002a5ad  sub     rax, rcx
0x18002a5b0  mov     r13d, 528h
0x18002a5b6  cmp     rax, r13
0x18002a5b9  jl      loc_18002A654
0x18002a5bf  xor     ecx, ecx
0x18002a5c1  test    rsi, rsi
0x18002a5c4  jle     loc_18002A67F
0x18002a5ca  mov     r9, r12
0x18002a5cd  mov     r8, rdi
0x18002a5d0  mov     rdx, rbx
0x18002a5d3  lea     rcx, [rbp+var_48]
0x18002a5d7  call    ??$_Partition_by_median_guess_unchecked@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YA?AU?$pair@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@PEAU12@@0@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@0P6A_NAEBU20@1@Z@Z; std::_Partition_by_median_guess_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x18002a5dc  mov     rcx, rsi
0x18002a5df  sar     rcx, 2
0x18002a5e3  sar     rsi, 1
0x18002a5e6  add     rsi, rcx
0x18002a5e9  mov     rdx, rdi
0x18002a5ec  mov     r14, [rbp+var_40]
0x18002a5f0  sub     rdx, r14
0x18002a5f3  sar     rdx, 3
0x18002a5f7  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18002a601  imul    rdx, rcx
0x18002a605  mov     r15, [rbp+var_48]
0x18002a609  mov     rax, r15
0x18002a60c  sub     rax, rbx
0x18002a60f  sar     rax, 3
0x18002a613  imul    rax, rcx
0x18002a617  mov     r9, r12
0x18002a61a  mov     r8, rsi
0x18002a61d  cmp     rax, rdx
0x18002a620  jge     short loc_18002A632
0x18002a622  mov     rdx, r15
0x18002a625  mov     rcx, rbx
0x18002a628  call    ??$_Sort_unchecked@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z; std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,__int64,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x18002a62d  mov     rbx, r14
0x18002a630  jmp     short loc_18002A640
0x18002a632  mov     rdx, rdi
0x18002a635  mov     rcx, r14
0x18002a638  call    ??$_Sort_unchecked@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z; std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,__int64,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x18002a63d  mov     rdi, r15
0x18002a640  mov     rax, rdi
0x18002a643  sub     rax, rbx
0x18002a646  cmp     rax, r13
0x18002a649  mov     ecx, 0
0x18002a64e  jge     loc_18002A5C1
0x18002a654  mov     r8, r12
0x18002a657  mov     rdx, rdi
0x18002a65a  mov     rcx, rbx
0x18002a65d  call    ??$_Insertion_sort_unchecked@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@QEAU10@0P6A_NAEBU10@1@Z@Z; std::_Insertion_sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x18002a662  mov     rcx, [rbp+var_10]
0x18002a666  xor     rcx, rsp; StackCookie
0x18002a669  call    __security_check_cookie
0x18002a66e  add     rsp, 78h
0x18002a672  pop     r15
0x18002a674  pop     r14
0x18002a676  pop     r13
0x18002a678  pop     r12
0x18002a67a  pop     rdi
0x18002a67b  pop     rsi
0x18002a67c  pop     rbx
0x18002a67d  pop     rbp
0x18002a67e  retn
0x18002a67f  mov     rsi, rdi
0x18002a682  sub     rsi, rbx
0x18002a685  mov     r15, rsi
0x18002a688  sar     r15, 3
0x18002a68c  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18002a696  imul    r15, r8
0x18002a69a  mov     r14, r15
0x18002a69d  sar     r14, 1
0x18002a6a0  test    r14, r14
0x18002a6a3  jle     loc_18002A73A
0x18002a6a9  lea     r13, [r14+1]
0x18002a6ad  lea     r13, [r14+r13*4]
0x18002a6b1  lea     r13, [rbx+r13*8]
0x18002a6b5  dec     r14
0x18002a6b8  lea     r13, [r13-28h]
0x18002a6bc  movups  xmm0, xmmword ptr [r13-20h]
0x18002a6c1  movups  [rbp+var_38], xmm0
0x18002a6c5  movups  xmm1, xmmword ptr [r13-10h]
0x18002a6ca  movups  [rbp+var_28], xmm1
0x18002a6ce  mov     [r13-10h], rcx
0x18002a6d2  mov     qword ptr [r13-8], 7
0x18002a6da  mov     [r13-20h], cx
0x18002a6df  mov     rax, [r13+0]
0x18002a6e3  mov     [r13+0], rcx
0x18002a6e7  mov     [rbp+var_18], rax
0x18002a6eb  mov     [rsp+78h+var_58], r12
0x18002a6f0  lea     r9, [rbp+var_38]
0x18002a6f4  mov     r8, r15
0x18002a6f7  mov     rdx, r14
0x18002a6fa  mov     rcx, rbx
0x18002a6fd  call    ??$_Pop_heap_hole_by_index@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@U12@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@_J1$$QEAU10@P6A_NAEBU10@3@Z@Z; std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,__int64,__int64,std::pair<std::wstring,web::json::value> &&,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x18002a702  nop
0x18002a703  mov     rcx, [rbp+var_18]
0x18002a707  test    rcx, rcx
0x18002a70a  jz      short loc_18002A720
0x18002a70c  mov     rax, [rcx]
0x18002a70f  mov     edx, 1
0x18002a714  mov     rax, [rax+0C0h]
0x18002a71b  call    _guard_dispatch_icall
0x18002a720  lea     rcx, [rbp+var_38]
0x18002a724  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a729  xor     ecx, ecx
0x18002a72b  test    r14, r14
0x18002a72e  jg      short loc_18002A6B5
0x18002a730  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18002a73a  cmp     r15, 2
0x18002a73e  jl      loc_18002A662
0x18002a744  add     rdi, 0FFFFFFFFFFFFFFF8h
0x18002a748  sar     rsi, 3
0x18002a74c  imul    rsi, r8
0x18002a750  cmp     rsi, 2
0x18002a754  jl      loc_18002A822
0x18002a75a  lea     rsi, [rdi-20h]
0x18002a75e  movups  xmm0, xmmword ptr [rsi]
0x18002a761  movups  [rbp+var_38], xmm0
0x18002a765  movups  xmm1, xmmword ptr [rsi+10h]
0x18002a769  movups  [rbp+var_28], xmm1
0x18002a76d  mov     [rdi-10h], rcx
0x18002a771  mov     qword ptr [rdi-8], 7
0x18002a779  mov     [rsi], cx
0x18002a77c  mov     rax, [rdi]
0x18002a77f  mov     [rdi], rcx
0x18002a782  mov     [rbp+var_18], rax
0x18002a786  cmp     rsi, rbx
0x18002a789  jz      short loc_18002A7BE
0x18002a78b  mov     rcx, rsi
0x18002a78e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a793  movups  xmm0, xmmword ptr [rbx]
0x18002a796  movups  xmmword ptr [rsi], xmm0
0x18002a799  movups  xmm1, xmmword ptr [rbx+10h]
0x18002a79d  movups  xmmword ptr [rsi+10h], xmm1
0x18002a7a1  xor     r14d, r14d
0x18002a7a4  mov     [rbx+10h], r14
0x18002a7a8  mov     qword ptr [rbx+18h], 7
0x18002a7b0  mov     [rbx], r14w
0x18002a7b4  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18002a7be  lea     rdx, [rbx+20h]
0x18002a7c2  cmp     rdi, rdx
0x18002a7c5  jz      short loc_18002A7D3
0x18002a7c7  mov     rcx, [rdi]
0x18002a7ca  mov     rax, [rdx]
0x18002a7cd  mov     [rdi], rax
0x18002a7d0  mov     [rdx], rcx
0x18002a7d3  sub     rsi, rbx
0x18002a7d6  sar     rsi, 3
0x18002a7da  imul    r8, rsi
0x18002a7de  mov     [rsp+78h+var_58], r12
0x18002a7e3  lea     r9, [rbp+var_38]
0x18002a7e7  xor     edx, edx
0x18002a7e9  mov     rcx, rbx
0x18002a7ec  call    ??$_Pop_heap_hole_by_index@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@U12@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@_J1$$QEAU10@P6A_NAEBU10@3@Z@Z; std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,__int64,__int64,std::pair<std::wstring,web::json::value> &&,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x18002a7f1  nop
0x18002a7f2  mov     rcx, [rbp+var_18]
0x18002a7f6  test    rcx, rcx
0x18002a7f9  jz      short loc_18002A80F
0x18002a7fb  mov     rax, [rcx]
0x18002a7fe  mov     edx, 1
0x18002a803  mov     rax, [rax+0C0h]
0x18002a80a  call    _guard_dispatch_icall
0x18002a80f  lea     rcx, [rbp+var_38]
0x18002a813  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a818  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18002a822  sub     rdi, 28h ; '('
0x18002a826  mov     rsi, rdi
0x18002a829  sub     rsi, rbx
0x18002a82c  add     rsi, 8
0x18002a830  cmp     rsi, 50h ; 'P'
0x18002a834  mov     ecx, 0
0x18002a839  jge     loc_18002A748
0x18002a83f  jmp     loc_18002A662
```
