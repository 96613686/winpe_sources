# CLI::detail::join_std::vector_std::unique_ptr_CLI::Option_std::default_delete_CLI::Option____std::allocator_std::unique_ptr_CLI::Option_std::default_delete_CLI::Option_________lambda_e7754a08b055c0594212749ce70f2336__void_

- ea: `0x140014e20`
- end: `0x1400150c2`
- name: `CLI::detail::join_std::vector_std::unique_ptr_CLI::Option_std::default_delete_CLI::Option____std::allocator_std::unique_ptr_CLI::Option_std::default_delete_CLI::Option_________lambda_e7754a08b055c0594212749ce70f2336__void_`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140025b40`

## callees

- `0x1400083f0`
- `0x14000c50c`
- `0x14000f7e0`
- `0x14000fab8`
- `0x140014e20`
- `0x140032850`
- `0x14004aa1c`
- `0x14004b384`

## import_xrefs

- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14001506c`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14001506c`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140015081`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140015081`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140015077`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140015077`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x140014e9a`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x140014e9a`
- `msvcp_win!?tellp@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x140014efd`
- `msvcp_win!?tellp@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x140014f1a`
- `msvcp_win!?tellp@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x140014efd`
- `msvcp_win!?tellp@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x140014f1a`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140014e78`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140014e78`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140014ece`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140014ece`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CLI::detail::join_std::vector_std::unique_ptr_CLI::Option_std::default_delete_CLI::Option____std::allocator_std::unique_ptr_CLI::Option_std::default_delete_CLI::Option_________lambda_e7754a08b055c0594212749ce70f2336__void_(
        __int64 a1,
        __int64 **a2,
        __int64 a3,
        _QWORD *a4)
{
  int v8; // r15d
  __int64 *v9; // rbx
  __int64 *v10; // rsi
  __int64 v11; // r9
  _QWORD *v12; // rdx
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // r8
  __int128 *v16; // rdx
  void *v17; // rcx
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int128 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h]
  __int128 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  int v24; // [rsp+5Ch] [rbp-A4h]
  __int64 *v25; // [rsp+60h] [rbp-A0h] BYREF
  void **v26; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v27[96]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-30h]
  int v29; // [rsp+D8h] [rbp-28h]
  _BYTE v30[104]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v31; // [rsp+150h] [rbp+50h]
  __int128 v32; // [rsp+158h] [rbp+58h] BYREF
  __int64 v33; // [rsp+168h] [rbp+68h]
  unsigned __int64 v34; // [rsp+170h] [rbp+70h]

  v31 = a4;
  v25 = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'};
  std::ios::ios(v30);
  v8 = 4;
  LODWORD(v19) = 4;
  std::ostream::ostream(&v25, &v26, 0, 0);
  *(__int64 **)((char *)&v25 + *((int *)v25 + 1)) = (__int64 *)&std::ostringstream::`vftable';
  *(int *)((char *)&v24 + *((int *)v25 + 1)) = *((_DWORD *)v25 + 1) - 136;
  std::streambuf::streambuf(&v26);
  v26 = &std::stringbuf::`vftable';
  v28 = 0;
  v29 = 4;
  v9 = *a2;
  v10 = a2[1];
  std::ostream::tellp(&v25, &v22);
  for ( ; v9 != v10; ++v9 )
  {
    std::ostream::tellp(&v25, &v20);
    if ( (_QWORD)v20 + *((_QWORD *)&v20 + 1) > (_QWORD)v22 + *((_QWORD *)&v22 + 1) )
    {
      if ( a4[3] <= 0xFu )
        v12 = a4;
      else
        v12 = (_QWORD *)*a4;
      std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v25, v12, a4[2]);
      v22 = v20;
      v23 = v21;
    }
    v13 = *v9;
    if ( *v9 == *(_QWORD *)(a3 + 528) || v13 == *(_QWORD *)(a3 + 536) )
    {
      v32 = 0;
      v15 = 0;
      v33 = 0;
      v14 = 15;
      v34 = 15;
      LOBYTE(v32) = 0;
    }
    else
    {
      LOBYTE(v11) = 1;
      CLI::Option::get_name(v13, &v32, 0, v11, v19, v20, *((_QWORD *)&v20 + 1));
      v14 = v34;
      v15 = v33;
    }
    v8 |= 2u;
    v16 = &v32;
    if ( v14 > 0xF )
      v16 = (__int128 *)v32;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v25, v16, v15);
    if ( v34 > 0xF )
    {
      v17 = (void *)v32;
      if ( v34 + 1 >= 0x1000 )
      {
        if ( (unsigned __int64)(v32 - *(_QWORD *)(v32 - 8) - 8) > 0x1F )
          __fastfail(5u);
        v17 = *(void **)(v32 - 8);
      }
      operator delete(v17);
    }
  }
  std::stringbuf::str(&v26, a1);
  *(__int64 **)((char *)&v25 + *((int *)v25 + 1)) = (__int64 *)&std::ostringstream::`vftable';
  *(int *)((char *)&v24 + *((int *)v25 + 1)) = *((_DWORD *)v25 + 1) - 136;
  v26 = &std::stringbuf::`vftable';
  std::stringbuf::_Tidy(&v26);
  std::streambuf::~streambuf<char,std::char_traits<char>>(&v26);
  std::ostream::~ostream<char,std::char_traits<char>>(v27);
  std::ios::~ios<char,std::char_traits<char>>(v30);
  std::string::_Tidy_deallocate(a4);
  return a1;
}

```

## disassembly

```asm
0x140014e20  mov     [rsp-8+arg_8], rbx
0x140014e25  mov     [rsp-8+arg_10], rsi
0x140014e2a  push    rbp
0x140014e2b  push    rdi
0x140014e2c  push    r12
0x140014e2e  push    r14
0x140014e30  push    r15
0x140014e32  lea     rbp, [rsp-80h]
0x140014e37  sub     rsp, 180h
0x140014e3e  mov     rax, cs:__security_cookie
0x140014e45  xor     rax, rsp
0x140014e48  mov     [rbp+0A0h+var_28], rax
0x140014e4c  mov     r14, r9
0x140014e4f  mov     rdi, r8
0x140014e52  mov     rsi, rdx
0x140014e55  mov     r12, rcx
0x140014e58  mov     [rbp+0A0h+var_50], rcx
0x140014e5c  mov     [rbp+0A0h+var_50], r9
0x140014e60  mov     dword ptr [rsp+1A0h+var_180], 0
0x140014e68  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_ostream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'}
0x140014e6f  mov     [rsp+1A0h+var_140], rax
0x140014e74  lea     rcx, [rbp+0A0h+var_B8]
0x140014e78  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x140014e7e  nop
0x140014e7f  mov     r15d, 4
0x140014e85  mov     dword ptr [rsp+1A0h+var_180], r15d
0x140014e8a  xor     r9d, r9d
0x140014e8d  xor     r8d, r8d
0x140014e90  lea     rdx, [rsp+1A0h+var_138]
0x140014e95  lea     rcx, [rsp+1A0h+var_140]
0x140014e9a  call    cs:__imp_??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::ostream::ostream(std::streambuf *,bool)
0x140014ea0  nop
0x140014ea1  mov     rax, [rsp+1A0h+var_140]
0x140014ea6  movsxd  rcx, dword ptr [rax+4]
0x140014eaa  lea     rax, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x140014eb1  mov     [rsp+rcx+1A0h+var_140], rax
0x140014eb6  mov     rax, [rsp+1A0h+var_140]
0x140014ebb  movsxd  rcx, dword ptr [rax+4]
0x140014ebf  lea     edx, [rcx-88h]
0x140014ec5  mov     [rsp+rcx+1A0h+var_144], edx
0x140014ec9  lea     rcx, [rsp+1A0h+var_138]
0x140014ece  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x140014ed4  lea     rax, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x140014edb  mov     [rsp+1A0h+var_138], rax
0x140014ee0  mov     [rbp+0A0h+var_D0], 0
0x140014ee8  mov     [rbp+0A0h+var_C8], r15d
0x140014eec  mov     rbx, [rsi]
0x140014eef  mov     rsi, [rsi+8]
0x140014ef3  lea     rdx, [rsp+1A0h+var_160]
0x140014ef8  lea     rcx, [rsp+1A0h+var_140]
0x140014efd  call    cs:__imp_?tellp@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::ostream::tellp(void)
0x140014f03  cmp     rbx, rsi
0x140014f06  jz      loc_140015019
0x140014f0c  nop     dword ptr [rax+00h]
0x140014f10  lea     rdx, [rsp+1A0h+var_178]
0x140014f15  lea     rcx, [rsp+1A0h+var_140]
0x140014f1a  call    cs:__imp_?tellp@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::ostream::tellp(void)
0x140014f20  mov     rdx, qword ptr [rsp+1A0h+var_160+8]
0x140014f25  add     rdx, qword ptr [rsp+1A0h+var_160]
0x140014f2a  mov     rcx, qword ptr [rsp+1A0h+var_178+8]
0x140014f2f  add     rcx, qword ptr [rsp+1A0h+var_178]
0x140014f34  cmp     rcx, rdx
0x140014f37  jle     short loc_140014F6C
0x140014f39  cmp     qword ptr [r14+18h], 0Fh
0x140014f3e  jbe     short loc_140014F45
0x140014f40  mov     rdx, [r14]
0x140014f43  jmp     short loc_140014F48
0x140014f45  mov     rdx, r14
0x140014f48  mov     r8, [r14+10h]
0x140014f4c  lea     rcx, [rsp+1A0h+var_140]
0x140014f51  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x140014f56  movups  xmm0, [rsp+1A0h+var_178]
0x140014f5b  movups  [rsp+1A0h+var_160], xmm0
0x140014f60  movsd   xmm1, [rsp+1A0h+var_168]
0x140014f66  movsd   [rsp+1A0h+var_150], xmm1
0x140014f6c  mov     rcx, [rbx]
0x140014f6f  cmp     rcx, [rdi+210h]
0x140014f76  jz      short loc_140014F9A
0x140014f78  cmp     rcx, [rdi+218h]
0x140014f7f  jz      short loc_140014F9A
0x140014f81  mov     r9b, 1
0x140014f84  xor     r8d, r8d
0x140014f87  lea     rdx, [rbp+0A0h+var_48]
0x140014f8b  call    ?get_name@Option@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N0@Z; CLI::Option::get_name(bool,bool)
0x140014f90  mov     rax, [rbp+0A0h+var_30]
0x140014f94  mov     r8, [rbp+0A0h+var_38]
0x140014f98  jmp     short loc_140014FB5
0x140014f9a  xorps   xmm0, xmm0
0x140014f9d  movups  [rbp+0A0h+var_48], xmm0
0x140014fa1  xor     r8d, r8d
0x140014fa4  mov     [rbp+0A0h+var_38], r8
0x140014fa8  mov     eax, 0Fh
0x140014fad  mov     [rbp+0A0h+var_30], rax
0x140014fb1  mov     byte ptr [rbp+0A0h+var_48], r8b
0x140014fb5  or      r15d, 2
0x140014fb9  lea     rdx, [rbp+0A0h+var_48]
0x140014fbd  cmp     rax, 0Fh
0x140014fc1  cmova   rdx, qword ptr [rbp+0A0h+var_48]
0x140014fc6  lea     rcx, [rsp+1A0h+var_140]
0x140014fcb  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x140014fd0  nop
0x140014fd1  mov     rdx, [rbp+0A0h+var_30]
0x140014fd5  cmp     rdx, 0Fh
0x140014fd9  jbe     short loc_14001500C
0x140014fdb  inc     rdx
0x140014fde  mov     rcx, qword ptr [rbp+0A0h+var_48]
0x140014fe2  cmp     rdx, 1000h
0x140014fe9  jb      short loc_140015007
0x140014feb  mov     rax, [rcx-8]
0x140014fef  sub     rcx, rax
0x140014ff2  sub     rcx, 8
0x140014ff6  cmp     rcx, 1Fh
0x140014ffa  ja      loc_1400150BB
0x140015000  add     rdx, 27h ; '''; unsigned __int64
0x140015004  mov     rcx, rax; void *
0x140015007  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001500c  add     rbx, 8
0x140015010  cmp     rbx, rsi
0x140015013  jnz     loc_140014F10
0x140015019  mov     rdx, r12
0x14001501c  lea     rcx, [rsp+1A0h+var_138]
0x140015021  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x140015026  nop
0x140015027  mov     rax, [rsp+1A0h+var_140]
0x14001502c  movsxd  rcx, dword ptr [rax+4]
0x140015030  lea     rax, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x140015037  mov     [rsp+rcx+1A0h+var_140], rax
0x14001503c  mov     rax, [rsp+1A0h+var_140]
0x140015041  movsxd  rdx, dword ptr [rax+4]
0x140015045  lea     r8d, [rdx-88h]
0x14001504c  mov     [rsp+rdx+1A0h+var_144], r8d
0x140015051  lea     rax, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x140015058  mov     [rsp+1A0h+var_138], rax
0x14001505d  lea     rcx, [rsp+1A0h+var_138]
0x140015062  call    ?_Tidy@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IEAAXXZ; std::stringbuf::_Tidy(void)
0x140015067  lea     rcx, [rsp+1A0h+var_138]
0x14001506c  call    cs:__imp_??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::streambuf::~streambuf<char,std::char_traits<char>>(void)
0x140015072  lea     rcx, [rsp+1A0h+var_130]
0x140015077  call    cs:__imp_??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ostream::~ostream<char,std::char_traits<char>>(void)
0x14001507d  lea     rcx, [rbp+0A0h+var_B8]
0x140015081  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x140015087  nop
0x140015088  mov     rcx, r14; void *
0x14001508b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140015090  mov     rax, r12
0x140015093  mov     rcx, [rbp+0A0h+var_28]
0x140015097  xor     rcx, rsp; StackCookie
0x14001509a  call    __security_check_cookie
0x14001509f  lea     r11, [rsp+1A0h+var_20]
0x1400150a7  mov     rbx, [r11+38h]
0x1400150ab  mov     rsi, [r11+40h]
0x1400150af  mov     rsp, r11
0x1400150b2  pop     r15
0x1400150b4  pop     r14
0x1400150b6  pop     r12
0x1400150b8  pop     rdi
0x1400150b9  pop     rbp
0x1400150ba  retn
0x1400150bb  mov     ecx, 5
0x1400150c0  int     29h; Win8: RtlFailFast(ecx)
```
