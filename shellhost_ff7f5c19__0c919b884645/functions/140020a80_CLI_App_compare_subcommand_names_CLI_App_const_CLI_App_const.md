# CLI::App::_compare_subcommand_names(CLI::App const &,CLI::App const &)

- ea: `0x140020a80`
- end: `0x140020e96`
- name: `?_compare_subcommand_names@App@CLI@@IEBAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@0@Z`
- size: `1046`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140020a80`
- `0x140028cd0`
- `0x1400355b0`

## callees

- `0x140008a50`
- `0x14000f804`
- `0x14000fa98`
- `0x14000fc7c`
- `0x14000fce4`
- `0x140010614`
- `0x140020a80`
- `0x14002a0c0`
- `0x14004a9e0`
- `0x14004aaac`

## pseudocode

```c
void **__fastcall CLI::App::_compare_subcommand_names(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v5; // r12
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // r15
  bool v10; // cc
  __int128 *v11; // r14
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rbx
  size_t v14; // rax
  size_t v15; // rcx
  void *v16; // rax
  void *v17; // rax
  void *v18; // rcx
  __int64 v19; // r15
  __int128 *v20; // r14
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rbx
  size_t v23; // rax
  size_t v24; // rcx
  _QWORD *v25; // rax
  void *v26; // rax
  void *v27; // rcx
  void **result; // rax
  __int128 v29; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int64 v30; // [rsp+30h] [rbp-30h]
  __int64 v31; // [rsp+38h] [rbp-28h]
  _QWORD *v33; // [rsp+88h] [rbp+28h]

  if ( dword_1400835F8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1400835F8);
    if ( dword_1400835F8 == -1 )
    {
      atexit(CLI::App::_compare_subcommand_names_::_2_::_dynamic_atexit_destructor_for__estring__);
      Init_thread_footer(&dword_1400835F8);
    }
  }
  if ( !*(_BYTE *)(a2 + 77) )
  {
    v5 = *(_QWORD **)(a3 + 768);
    v33 = *(_QWORD **)(a3 + 776);
    while ( v5 != v33 )
    {
      if ( *v5 != a2 && !*(_BYTE *)(*v5 + 77LL) )
      {
        if ( *(_QWORD *)(a2 + 24) )
        {
          v6 = std::string::string(&v29, a2 + 8);
          if ( (unsigned __int8)CLI::App::check_name(*v5, v6) )
            return (void **)(a2 + 8);
        }
        if ( *(_QWORD *)(*v5 + 24LL) )
        {
          v7 = std::string::string(&v29, *v5 + 8LL);
          if ( (unsigned __int8)CLI::App::check_name(a2, v7) )
            return (void **)(*v5 + 8LL);
        }
        v8 = *(_QWORD *)(a2 + 880);
        v9 = *(_QWORD *)(a2 + 888);
        if ( v8 != v9 )
        {
          while ( 1 )
          {
            v10 = *(_QWORD *)(v8 + 24) <= 0xFu;
            v29 = 0;
            v30 = 0;
            v31 = 0;
            if ( v10 )
              v11 = (__int128 *)v8;
            else
              v11 = *(__int128 **)v8;
            v12 = *(_QWORD *)(v8 + 16);
            if ( v12 > 0x7FFFFFFFFFFFFFFFLL )
              std::_Xlen_string();
            if ( v12 <= 0xF )
            {
              v30 = *(_QWORD *)(v8 + 16);
              v31 = 15;
              v29 = *v11;
              goto LABEL_29;
            }
            v13 = v12 | 0xF;
            if ( (v12 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
              break;
            if ( v13 < 0x16 )
              v13 = 22;
            v15 = v13 + 1;
            if ( v13 == -1 )
            {
              v16 = 0;
            }
            else
            {
              if ( v15 >= 0x1000 )
              {
                v14 = v13 + 40;
                if ( v13 + 40 < v13 + 1 )
                  std::_Throw_bad_array_new_length();
                goto LABEL_25;
              }
              v16 = operator new(v15);
            }
LABEL_28:
            *(_QWORD *)&v29 = v16;
            v30 = v12;
            v31 = v13;
            memcpy_0(v16, v11, v12 + 1);
LABEL_29:
            if ( (unsigned __int8)CLI::App::check_name(*v5, &v29) )
              return (void **)v8;
            v8 += 32;
            if ( v8 == v9 )
              goto LABEL_31;
          }
          v13 = 0x7FFFFFFFFFFFFFFFLL;
          v14 = 0x8000000000000027uLL;
LABEL_25:
          v17 = operator new(v14);
          v18 = v17;
          if ( !v17 )
LABEL_62:
            __fastfail(5u);
          v16 = (void *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v16 - 1) = v18;
          goto LABEL_28;
        }
LABEL_31:
        v8 = *(_QWORD *)(*v5 + 880LL);
        v19 = *(_QWORD *)(*v5 + 888LL);
        if ( v8 != v19 )
        {
          while ( 1 )
          {
            v10 = *(_QWORD *)(v8 + 24) <= 0xFu;
            v29 = 0;
            v30 = 0;
            v31 = 0;
            if ( v10 )
              v20 = (__int128 *)v8;
            else
              v20 = *(__int128 **)v8;
            v21 = *(_QWORD *)(v8 + 16);
            if ( v21 > 0x7FFFFFFFFFFFFFFFLL )
              std::_Xlen_string();
            if ( v21 > 0xF )
              break;
            v30 = *(_QWORD *)(v8 + 16);
            v31 = 15;
            v29 = *v20;
LABEL_50:
            if ( (unsigned __int8)CLI::App::check_name(a2, &v29) )
              return (void **)v8;
            v8 += 32;
            if ( v8 == v19 )
              goto LABEL_52;
          }
          v22 = v21 | 0xF;
          if ( (v21 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
          {
            v22 = 0x7FFFFFFFFFFFFFFFLL;
            v23 = 0x8000000000000027uLL;
            goto LABEL_46;
          }
          if ( v22 < 0x16 )
            v22 = 22;
          v24 = v22 + 1;
          if ( v22 == -1 )
          {
            v25 = 0;
          }
          else if ( v24 < 0x1000 )
          {
            v25 = operator new(v24);
          }
          else
          {
            v23 = v22 + 40;
            if ( v22 + 40 < v22 + 1 )
              std::_Throw_bad_array_new_length();
LABEL_46:
            v26 = operator new(v23);
            v27 = v26;
            if ( !v26 )
              goto LABEL_62;
            v25 = (_QWORD *)(((unsigned __int64)v26 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v25 - 1) = v27;
          }
          *(_QWORD *)&v29 = v25;
          v30 = v21;
          v31 = v22;
          memcpy_0(v25, v20, v21 + 1);
          goto LABEL_50;
        }
LABEL_52:
        if ( !*(_QWORD *)(*v5 + 24LL) )
        {
          result = (void **)CLI::App::_compare_subcommand_names(a1, a2, *v5);
          if ( result[2] )
            return result;
        }
        if ( !*(_QWORD *)(a2 + 24) )
        {
          result = (void **)CLI::App::_compare_subcommand_names(a1, *v5, a2);
          if ( result[2] )
            return result;
        }
      }
      v5 += 2;
    }
  }
  return &qword_140082E10;
}

```

## disassembly

```asm
0x140020a80  mov     [rsp-18h+arg_0], rcx
0x140020a85  push    rbp
0x140020a86  push    rbx
0x140020a87  push    r13
0x140020a89  mov     rbp, rsp
0x140020a8c  sub     rsp, 60h
0x140020a90  mov     r9d, cs:_tls_index
0x140020a97  mov     rbx, r8
0x140020a9a  mov     rax, gs:58h
0x140020aa3  mov     r13, rdx
0x140020aa6  mov     ecx, 4
0x140020aab  mov     rax, [rax+r9*8]
0x140020aaf  mov     eax, [rcx+rax]
0x140020ab2  cmp     cs:dword_1400835F8, eax
0x140020ab8  jg      loc_140020E54
0x140020abe  cmp     byte ptr [r13+4Dh], 0
0x140020ac3  mov     [rsp+60h+arg_10], rsi
0x140020acb  mov     [rsp+60h+var_8], rdi
0x140020ad0  mov     [rsp+60h+var_10], r12
0x140020ad5  mov     [rsp+60h+var_18], r14
0x140020ada  mov     [rsp+60h+var_20], r15
0x140020adf  jnz     loc_140020E00
0x140020ae5  mov     rax, [rbx+308h]
0x140020aec  mov     r12, [rbx+300h]
0x140020af3  mov     [rbp+arg_8], rax
0x140020af7  cmp     r12, rax
0x140020afa  jz      loc_140020E00
0x140020b00  xor     ebx, ebx
0x140020b02  mov     rax, [r12]
0x140020b06  cmp     rax, r13
0x140020b09  jz      loc_140020DF2
0x140020b0f  cmp     byte ptr [rax+4Dh], 0
0x140020b13  jnz     loc_140020DF2
0x140020b19  cmp     qword ptr [r13+18h], 0
0x140020b1e  jz      short loc_140020B43
0x140020b20  lea     rdx, [r13+8]
0x140020b24  lea     rcx, [rbp+var_40]
0x140020b28  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140020b2d  mov     rcx, [r12]
0x140020b31  mov     rdx, rax
0x140020b34  call    ?check_name@App@CLI@@QEBA_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::App::check_name(std::string)
0x140020b39  test    al, al
0x140020b3b  jnz     loc_140020E2C
0x140020b41  xor     ebx, ebx
0x140020b43  mov     rdx, [r12]
0x140020b47  cmp     qword ptr [rdx+18h], 0
0x140020b4c  jz      short loc_140020B6E
0x140020b4e  add     rdx, 8
0x140020b52  lea     rcx, [rbp+var_40]
0x140020b56  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140020b5b  mov     rdx, rax
0x140020b5e  mov     rcx, r13
0x140020b61  call    ?check_name@App@CLI@@QEBA_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::App::check_name(std::string)
0x140020b66  test    al, al
0x140020b68  jnz     loc_140020E32
0x140020b6e  mov     rdi, [r13+370h]
0x140020b75  mov     r15, [r13+378h]
0x140020b7c  cmp     rdi, r15
0x140020b7f  jz      loc_140020C95
0x140020b85  nop     word ptr [rax+rax+00000000h]
0x140020b90  cmp     qword ptr [rdi+18h], 0Fh
0x140020b95  xorps   xmm0, xmm0
0x140020b98  movups  [rbp+var_40], xmm0
0x140020b9c  mov     [rbp+var_30], rbx
0x140020ba0  mov     [rbp+var_28], rbx
0x140020ba4  jbe     short loc_140020BAB
0x140020ba6  mov     r14, [rdi]
0x140020ba9  jmp     short loc_140020BAE
0x140020bab  mov     r14, rdi
0x140020bae  mov     rsi, [rdi+10h]
0x140020bb2  mov     rax, 7FFFFFFFFFFFFFFFh
0x140020bbc  cmp     rsi, rax
0x140020bbf  ja      loc_140020E90
0x140020bc5  cmp     rsi, 0Fh
0x140020bc9  ja      short loc_140020BE4
0x140020bcb  mov     [rbp+var_30], rsi
0x140020bcf  mov     [rbp+var_28], 0Fh
0x140020bd7  movups  xmm0, xmmword ptr [r14]
0x140020bdb  movups  [rbp+var_40], xmm0
0x140020bdf  jmp     loc_140020C73
0x140020be4  mov     rbx, rsi
0x140020be7  or      rbx, 0Fh
0x140020beb  cmp     rbx, rax
0x140020bee  jbe     short loc_140020BFF
0x140020bf0  mov     rbx, rax
0x140020bf3  mov     rax, 8000000000000027h
0x140020bfd  jmp     short loc_140020C2F
0x140020bff  cmp     rbx, 16h
0x140020c03  mov     eax, 16h
0x140020c08  cmovb   rbx, rax
0x140020c0c  lea     rcx, [rbx+1]; Size
0x140020c10  test    rcx, rcx
0x140020c13  jnz     short loc_140020C19
0x140020c15  xor     eax, eax
0x140020c17  jmp     short loc_140020C56
0x140020c19  cmp     rcx, 1000h
0x140020c20  jb      short loc_140020C51
0x140020c22  lea     rax, [rcx+27h]
0x140020c26  cmp     rax, rcx
0x140020c29  jbe     loc_140020E8A
0x140020c2f  mov     rcx, rax; Size
0x140020c32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140020c37  mov     rcx, rax
0x140020c3a  test    rax, rax
0x140020c3d  jz      loc_140020E41
0x140020c43  add     rax, 27h ; '''
0x140020c47  and     rax, 0FFFFFFFFFFFFFFE0h
0x140020c4b  mov     [rax-8], rcx
0x140020c4f  jmp     short loc_140020C56
0x140020c51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140020c56  lea     r8, [rsi+1]; Size
0x140020c5a  mov     qword ptr [rbp+var_40], rax
0x140020c5e  mov     rdx, r14; Src
0x140020c61  mov     [rbp+var_30], rsi
0x140020c65  mov     rcx, rax; void *
0x140020c68  mov     [rbp+var_28], rbx
0x140020c6c  call    memcpy_0
0x140020c71  xor     ebx, ebx
0x140020c73  mov     rcx, [r12]
0x140020c77  lea     rdx, [rbp+var_40]
0x140020c7b  call    ?check_name@App@CLI@@QEBA_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::App::check_name(std::string)
0x140020c80  test    al, al
0x140020c82  jnz     loc_140020E3C
0x140020c88  add     rdi, 20h ; ' '
0x140020c8c  cmp     rdi, r15
0x140020c8f  jnz     loc_140020B90
0x140020c95  mov     rax, [r12]
0x140020c99  mov     rdi, [rax+370h]
0x140020ca0  mov     r15, [rax+378h]
0x140020ca7  cmp     rdi, r15
0x140020caa  jz      loc_140020DB4
0x140020cb0  cmp     qword ptr [rdi+18h], 0Fh
0x140020cb5  xorps   xmm0, xmm0
0x140020cb8  movups  [rbp+var_40], xmm0
0x140020cbc  mov     [rbp+var_30], rbx
0x140020cc0  mov     [rbp+var_28], rbx
0x140020cc4  jbe     short loc_140020CCB
0x140020cc6  mov     r14, [rdi]
0x140020cc9  jmp     short loc_140020CCE
0x140020ccb  mov     r14, rdi
0x140020cce  mov     rsi, [rdi+10h]
0x140020cd2  mov     rax, 7FFFFFFFFFFFFFFFh
0x140020cdc  cmp     rsi, rax
0x140020cdf  ja      loc_140020E4E
0x140020ce5  cmp     rsi, 0Fh
0x140020ce9  ja      short loc_140020D04
0x140020ceb  mov     [rbp+var_30], rsi
0x140020cef  mov     [rbp+var_28], 0Fh
0x140020cf7  movups  xmm0, xmmword ptr [r14]
0x140020cfb  movups  [rbp+var_40], xmm0
0x140020cff  jmp     loc_140020D93
0x140020d04  mov     rbx, rsi
0x140020d07  or      rbx, 0Fh
0x140020d0b  cmp     rbx, rax
0x140020d0e  jbe     short loc_140020D1F
0x140020d10  mov     rbx, rax
0x140020d13  mov     rax, 8000000000000027h
0x140020d1d  jmp     short loc_140020D4F
0x140020d1f  cmp     rbx, 16h
0x140020d23  mov     eax, 16h
0x140020d28  cmovb   rbx, rax
0x140020d2c  lea     rcx, [rbx+1]; Size
0x140020d30  test    rcx, rcx
0x140020d33  jnz     short loc_140020D39
0x140020d35  xor     eax, eax
0x140020d37  jmp     short loc_140020D76
0x140020d39  cmp     rcx, 1000h
0x140020d40  jb      short loc_140020D71
0x140020d42  lea     rax, [rcx+27h]
0x140020d46  cmp     rax, rcx
0x140020d49  jbe     loc_140020E48
0x140020d4f  mov     rcx, rax; Size
0x140020d52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140020d57  mov     rcx, rax
0x140020d5a  test    rax, rax
0x140020d5d  jz      loc_140020E41
0x140020d63  add     rax, 27h ; '''
0x140020d67  and     rax, 0FFFFFFFFFFFFFFE0h
0x140020d6b  mov     [rax-8], rcx
0x140020d6f  jmp     short loc_140020D76
0x140020d71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140020d76  lea     r8, [rsi+1]; Size
0x140020d7a  mov     qword ptr [rbp+var_40], rax
0x140020d7e  mov     rdx, r14; Src
0x140020d81  mov     [rbp+var_30], rsi
0x140020d85  mov     rcx, rax; void *
0x140020d88  mov     [rbp+var_28], rbx
0x140020d8c  call    memcpy_0
0x140020d91  xor     ebx, ebx
0x140020d93  lea     rdx, [rbp+var_40]
0x140020d97  mov     rcx, r13
0x140020d9a  call    ?check_name@App@CLI@@QEBA_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::App::check_name(std::string)
0x140020d9f  test    al, al
0x140020da1  jnz     loc_140020E3C
0x140020da7  add     rdi, 20h ; ' '
0x140020dab  cmp     rdi, r15
0x140020dae  jnz     loc_140020CB0
0x140020db4  mov     r8, [r12]
0x140020db8  mov     rdi, [rbp+arg_0]
0x140020dbc  cmp     qword ptr [r8+18h], 0
0x140020dc1  jnz     short loc_140020DD5
0x140020dc3  mov     rdx, r13
0x140020dc6  mov     rcx, rdi
0x140020dc9  call    ?_compare_subcommand_names@App@CLI@@IEBAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@0@Z; CLI::App::_compare_subcommand_names(CLI::App const &,CLI::App const &)
0x140020dce  cmp     qword ptr [rax+10h], 0
0x140020dd3  jnz     short loc_140020E07
0x140020dd5  cmp     qword ptr [r13+18h], 0
0x140020dda  jnz     short loc_140020DF2
0x140020ddc  mov     rdx, [r12]
0x140020de0  mov     r8, r13
0x140020de3  mov     rcx, rdi
0x140020de6  call    ?_compare_subcommand_names@App@CLI@@IEBAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@0@Z; CLI::App::_compare_subcommand_names(CLI::App const &,CLI::App const &)
0x140020deb  cmp     qword ptr [rax+10h], 0
0x140020df0  jnz     short loc_140020E07
0x140020df2  add     r12, 10h
0x140020df6  cmp     r12, [rbp+arg_8]
0x140020dfa  jnz     loc_140020B02
0x140020e00  lea     rax, qword_140082E10
0x140020e07  mov     r15, [rsp+60h+var_20]
0x140020e0c  mov     r14, [rsp+60h+var_18]
0x140020e11  mov     r12, [rsp+60h+var_10]
0x140020e16  mov     rdi, [rsp+60h+var_8]
0x140020e1b  mov     rsi, [rsp+60h+arg_10]
0x140020e23  add     rsp, 60h
0x140020e27  pop     r13
0x140020e29  pop     rbx
0x140020e2a  pop     rbp
0x140020e2b  retn
0x140020e2c  lea     rax, [r13+8]
0x140020e30  jmp     short loc_140020E07
0x140020e32  mov     rax, [r12]
0x140020e36  add     rax, 8
0x140020e3a  jmp     short loc_140020E07
0x140020e3c  mov     rax, rdi
0x140020e3f  jmp     short loc_140020E07
0x140020e41  mov     ecx, 5
0x140020e46  int     29h; Win8: RtlFailFast(ecx)
0x140020e48  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x140020e4e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140020e54  lea     rcx, dword_1400835F8
0x140020e5b  call    _Init_thread_header
0x140020e60  cmp     cs:dword_1400835F8, 0FFFFFFFFh
0x140020e67  jnz     loc_140020ABE
0x140020e6d  lea     rcx, _CLI__App___compare_subcommand_names____2____dynamic_atexit_destructor_for__estring__; void (__cdecl *)()
0x140020e74  call    atexit
0x140020e79  lea     rcx, dword_1400835F8
0x140020e80  call    _Init_thread_footer
0x140020e85  jmp     loc_140020ABE
0x140020e8a  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x140020e90  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
