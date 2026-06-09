# CLI::Formatter::make_subcommand(CLI::App const *)

- ea: `0x140039830`
- end: `0x140039c37`
- name: `?make_subcommand@Formatter@CLI@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBVApp@2@@Z`
- size: `1031`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140005200`
- `0x140008a50`
- `0x14000f7e0`
- `0x14000fab8`
- `0x14002d910`
- `0x1400312f0`
- `0x1400326b0`
- `0x140039830`
- `0x14004aa1c`
- `0x14004b384`
- `0x14005e4d8`

## import_xrefs

- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140039bfa`
- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140039bfa`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140039bef`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140039bef`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140039c04`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140039c04`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x1400398ae`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x1400398ae`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140039892`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140039892`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x1400398e2`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x1400398e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CLI::Formatter::make_subcommand(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 label; // rax
  __int64 v7; // rax
  void **v8; // rdi
  int v9; // ebx
  int v10; // ebx
  __int64 v11; // r8
  __int64 display_name; // rax
  int v13; // ebx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  _BYTE *v18; // rcx
  unsigned __int8 v20; // [rsp+24h] [rbp-DCh]
  __int128 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  _QWORD v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v26; // [rsp+60h] [rbp-A0h] BYREF
  void **v27; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v28[96]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  _BYTE v31[104]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v32[32]; // [rsp+150h] [rbp+50h] BYREF
  void *v33[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v34; // [rsp+180h] [rbp+80h]
  unsigned __int64 v35; // [rsp+188h] [rbp+88h]
  void *v36[3]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 v37; // [rsp+1A8h] [rbp+A8h]
  void *v38[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v39; // [rsp+1C0h] [rbp+C0h]
  void *v40[3]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v41; // [rsp+1E8h] [rbp+E8h]
  void *v42; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int64 v43; // [rsp+208h] [rbp+108h]

  v25[0] = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'};
  v26 = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'};
  std::ios::ios(v31);
  std::iostream::basic_iostream<char>(v25, &v27, 0);
  *(_QWORD *)((char *)v25 + *(int *)(v25[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
  *(_DWORD *)((char *)&v24 + *(int *)(v25[0] + 4LL) + 4) = *(_DWORD *)(v25[0] + 4LL) - 152;
  std::streambuf::streambuf(&v27);
  v27 = &std::stringbuf::`vftable';
  v29 = 0;
  v30 = 0;
  if ( *(_BYTE *)(a3 + 76) )
  {
    *((_QWORD *)&v22 + 1) = 0;
    v23 = 8;
    v24 = 15;
    strcpy((char *)&v22, "REQUIRED");
    label = CLI::FormatterBase::get_label(a1, &v42, &v22);
    v7 = std::string::insert(label, 0, " ");
    *(_OWORD *)v38 = *(_OWORD *)v7;
    v39 = *(_OWORD *)(v7 + 16);
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 24) = 15;
    *(_BYTE *)v7 = 0;
    v8 = v38;
    v9 = 275;
  }
  else
  {
    *(_OWORD *)v33 = 0;
    v34 = 0;
    v35 = 15;
    LOBYTE(v33[0]) = 0;
    v8 = v33;
    v9 = 20;
  }
  std::string::string(v40, a3 + 40);
  v10 = v9 | 0x20;
  LOBYTE(v11) = 1;
  display_name = CLI::App::get_display_name(a3, v36, v11);
  std::string::string(v32, v20, display_name, v8, v10, a2);
  v13 = v10 | 0x40;
  CLI::detail::format_help(&v26, v32, v40, *(_QWORD *)(a1 + 8), v13);
  if ( v37 > 0xF )
  {
    if ( v37 + 1 < 0x1000 )
    {
      v14 = v36[0];
    }
    else
    {
      v14 = (void *)*((_QWORD *)v36[0] - 1);
      if ( (unsigned __int64)((char *)v36[0] - (char *)v14 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v14);
  }
  v36[2] = 0;
  v37 = 15;
  LOBYTE(v36[0]) = 0;
  if ( v41 > 0xF )
  {
    if ( v41 + 1 < 0x1000 )
    {
      v15 = v40[0];
    }
    else
    {
      v15 = (void *)*((_QWORD *)v40[0] - 1);
      if ( (unsigned __int64)((char *)v40[0] - (char *)v15 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v15);
  }
  if ( (v13 & 4) != 0 )
  {
    LOBYTE(v13) = v13 & 0xFB;
    if ( v35 > 0xF )
    {
      if ( v35 + 1 < 0x1000 )
      {
        v16 = v33[0];
      }
      else
      {
        v16 = (void *)*((_QWORD *)v33[0] - 1);
        if ( (unsigned __int64)((char *)v33[0] - (char *)v16 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v16);
    }
  }
  if ( (v13 & 2) != 0 )
  {
    LOBYTE(v13) = v13 & 0xFD;
    if ( *((_QWORD *)&v39 + 1) > 0xFu )
    {
      if ( (unsigned __int64)(*((_QWORD *)&v39 + 1) + 1LL) < 0x1000 )
      {
        v17 = v38[0];
      }
      else
      {
        v17 = (void *)*((_QWORD *)v38[0] - 1);
        if ( (unsigned __int64)((char *)v38[0] - (char *)v17 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v17);
    }
  }
  if ( (v13 & 1) != 0 && v43 > 0xF )
  {
    if ( v43 + 1 < 0x1000 )
    {
      v18 = v42;
    }
    else
    {
      v18 = (_BYTE *)*((_QWORD *)v42 - 1);
      if ( (unsigned __int64)((_BYTE *)v42 - v18 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v18);
  }
  std::stringbuf::str(&v27, a2);
  *(_QWORD *)((char *)v25 + *(int *)(v25[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
  *(_DWORD *)((char *)&v24 + *(int *)(v25[0] + 4LL) + 4) = *(_DWORD *)(v25[0] + 4LL) - 152;
  v27 = &std::stringbuf::`vftable';
  std::stringbuf::_Tidy(&v27);
  std::streambuf::~streambuf<char,std::char_traits<char>>(&v27);
  std::iostream::~basic_iostream<char,std::char_traits<char>>(v28);
  std::ios::~ios<char,std::char_traits<char>>(v31);
  return a2;
}

```

## disassembly

```asm
0x140039830  mov     [rsp-8+arg_18], rbx
0x140039835  push    rbp
0x140039836  push    rsi
0x140039837  push    rdi
0x140039838  push    r12
0x14003983a  push    r13
0x14003983c  push    r14
0x14003983e  push    r15
0x140039840  lea     rbp, [rsp-120h]
0x140039848  sub     rsp, 220h
0x14003984f  mov     rax, cs:__security_cookie
0x140039856  xor     rax, rsp
0x140039859  mov     [rbp+150h+var_40], rax
0x140039860  mov     r14, r8
0x140039863  mov     r15, rdx
0x140039866  mov     rsi, rcx
0x140039869  mov     [rsp+250h+var_228], rdx
0x14003986e  xor     r12d, r12d
0x140039871  mov     [rsp+250h+var_230], r12d
0x140039876  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_istream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'}
0x14003987d  mov     [rsp+250h+var_200], rax
0x140039882  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_ostream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'}
0x140039889  mov     [rsp+250h+var_1F0], rax
0x14003988e  lea     rcx, [rbp+150h+var_168]
0x140039892  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x140039898  nop
0x140039899  mov     [rsp+250h+var_230], 10h
0x1400398a1  xor     r8d, r8d
0x1400398a4  lea     rdx, [rsp+250h+var_1E8]
0x1400398a9  lea     rcx, [rsp+250h+var_200]
0x1400398ae  call    cs:__imp_??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z; std::iostream::basic_iostream<char>(std::streambuf *)
0x1400398b4  nop
0x1400398b5  mov     rax, [rsp+250h+var_200]
0x1400398ba  movsxd  rcx, dword ptr [rax+4]
0x1400398be  lea     rax, ??_7?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable'
0x1400398c5  mov     [rsp+rcx+250h+var_200], rax
0x1400398ca  mov     rax, [rsp+250h+var_200]
0x1400398cf  movsxd  rcx, dword ptr [rax+4]
0x1400398d3  lea     edx, [rcx-98h]
0x1400398d9  mov     [rsp+rcx+250h+var_204], edx
0x1400398dd  lea     rcx, [rsp+250h+var_1E8]
0x1400398e2  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x1400398e8  lea     r13, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x1400398ef  mov     [rsp+250h+var_1E8], r13
0x1400398f4  mov     [rbp+150h+var_180], r12
0x1400398f8  mov     [rbp+150h+var_178], r12d
0x1400398fc  xorps   xmm0, xmm0
0x1400398ff  cmp     [r14+4Ch], r12b
0x140039903  jz      loc_140039991
0x140039909  movups  [rsp+250h+var_220], xmm0
0x14003990e  mov     [rsp+250h+var_210], 8
0x140039917  mov     qword ptr [rsp+48h], 0Fh
0x140039920  mov     rax, qword ptr cs:aRequired; "REQUIRED"
0x140039927  mov     qword ptr [rsp+250h+var_220], rax
0x14003992c  mov     byte ptr [rsp+250h+var_220+8], r12b
0x140039931  lea     r8, [rsp+250h+var_220]
0x140039936  lea     rdx, [rbp+150h+var_60]
0x14003993d  mov     rcx, rsi
0x140039940  call    ?get_label@FormatterBase@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V34@@Z; CLI::FormatterBase::get_label(std::string)
0x140039945  nop
0x140039946  mov     [rsp+250h+var_230], 11h
0x14003994e  lea     r8, asc_14006CB48; " "
0x140039955  xor     edx, edx
0x140039957  mov     rcx, rax
0x14003995a  call    ?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KQEBD@Z; std::string::insert(unsigned __int64,char const * const)
0x14003995f  movups  xmm0, xmmword ptr [rax]
0x140039962  movups  xmmword ptr [rbp+150h+var_A0], xmm0
0x140039969  movups  xmm1, xmmword ptr [rax+10h]
0x14003996d  movups  [rbp+150h+var_90], xmm1
0x140039974  mov     [rax+10h], r12
0x140039978  mov     qword ptr [rax+18h], 0Fh
0x140039980  mov     [rax], r12b
0x140039983  lea     rdi, [rbp+150h+var_A0]
0x14003998a  mov     ebx, 113h
0x14003998f  jmp     short loc_1400399B4
0x140039991  movups  xmmword ptr [rbp+150h+var_E0], xmm0
0x140039995  mov     [rbp+150h+var_D0], r12
0x14003999c  mov     [rbp+150h+var_C8], 0Fh
0x1400399a7  mov     byte ptr [rbp+150h+var_E0], 0
0x1400399ab  lea     rdi, [rbp+150h+var_E0]
0x1400399af  mov     ebx, 14h
0x1400399b4  mov     [rsp+250h+var_230], ebx
0x1400399b8  lea     rdx, [r14+28h]
0x1400399bc  lea     rcx, [rbp+150h+var_80]
0x1400399c3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1400399c8  or      ebx, 20h
0x1400399cb  mov     [rsp+250h+var_230], ebx
0x1400399cf  mov     r8b, 1
0x1400399d2  lea     rdx, [rbp+150h+var_C0]
0x1400399d9  mov     rcx, r14
0x1400399dc  call    ?get_display_name@App@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; CLI::App::get_display_name(bool)
0x1400399e1  nop
0x1400399e2  mov     r9, rdi
0x1400399e5  mov     r8, rax
0x1400399e8  movzx   edx, [rsp+250h+var_22C]
0x1400399ed  lea     rcx, [rbp+150h+var_100]
0x1400399f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1400399f6  or      ebx, 40h
0x1400399f9  mov     [rsp+250h+var_230], ebx
0x1400399fd  mov     r9, [rsi+8]
0x140039a01  lea     r8, [rbp+150h+var_80]
0x140039a08  lea     rdx, [rbp+150h+var_100]
0x140039a0c  lea     rcx, [rsp+250h+var_1F0]
0x140039a11  call    ?format_help@detail@CLI@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@AEAV34@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@AEBV54@_K@Z; CLI::detail::format_help(std::ostream &,std::string,std::string const &,unsigned __int64)
0x140039a16  nop
0x140039a17  mov     rdx, [rbp+150h+var_A8]
0x140039a1e  cmp     rdx, 0Fh
0x140039a22  jbe     short loc_140039A5D
0x140039a24  mov     rax, [rbp+150h+var_C0]
0x140039a2b  inc     rdx; unsigned __int64
0x140039a2e  cmp     rdx, 1000h
0x140039a35  jb      short loc_140039A55
0x140039a37  mov     rcx, [rax-8]
0x140039a3b  sub     rax, rcx
0x140039a3e  sub     rax, 8
0x140039a42  cmp     rax, 1Fh
0x140039a46  ja      short loc_140039A4E
0x140039a48  add     rdx, 27h ; '''
0x140039a4c  jmp     short loc_140039A58
0x140039a4e  mov     ecx, 5
0x140039a53  int     29h; Win8: RtlFailFast(ecx)
0x140039a55  mov     rcx, rax; void *
0x140039a58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140039a5d  mov     [rbp+150h+var_B0], r12
0x140039a64  mov     [rbp+150h+var_A8], 0Fh
0x140039a6f  mov     byte ptr [rbp+150h+var_C0], 0
0x140039a76  mov     rdx, [rbp+150h+var_68]
0x140039a7d  cmp     rdx, 0Fh
0x140039a81  jbe     short loc_140039ABD
0x140039a83  mov     rax, [rbp+150h+var_80]
0x140039a8a  inc     rdx; unsigned __int64
0x140039a8d  cmp     rdx, 1000h
0x140039a94  jb      short loc_140039AB4
0x140039a96  mov     rcx, [rax-8]
0x140039a9a  sub     rax, rcx
0x140039a9d  sub     rax, 8
0x140039aa1  cmp     rax, 1Fh
0x140039aa5  ja      short loc_140039AAD
0x140039aa7  add     rdx, 27h ; '''
0x140039aab  jmp     short loc_140039AB7
0x140039aad  mov     ecx, 5
0x140039ab2  int     29h; Win8: RtlFailFast(ecx)
0x140039ab4  mov     rcx, rax; void *
0x140039ab7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140039abc  nop
0x140039abd  test    bl, 4
0x140039ac0  jz      short loc_140039B09
0x140039ac2  and     ebx, 0FFFFFFFBh
0x140039ac5  mov     rdx, [rbp+150h+var_C8]
0x140039acc  cmp     rdx, 0Fh
0x140039ad0  jbe     short loc_140039B09
0x140039ad2  mov     rax, [rbp+150h+var_E0]
0x140039ad6  inc     rdx; unsigned __int64
0x140039ad9  cmp     rdx, 1000h
0x140039ae0  jb      short loc_140039B00
0x140039ae2  mov     rcx, [rax-8]
0x140039ae6  sub     rax, rcx
0x140039ae9  sub     rax, 8
0x140039aed  cmp     rax, 1Fh
0x140039af1  ja      short loc_140039AF9
0x140039af3  add     rdx, 27h ; '''
0x140039af7  jmp     short loc_140039B03
0x140039af9  mov     ecx, 5
0x140039afe  int     29h; Win8: RtlFailFast(ecx)
0x140039b00  mov     rcx, rax; void *
0x140039b03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140039b08  nop
0x140039b09  test    bl, 2
0x140039b0c  jz      short loc_140039B58
0x140039b0e  and     ebx, 0FFFFFFFDh
0x140039b11  mov     rdx, qword ptr [rbp+150h+var_90+8]
0x140039b18  cmp     rdx, 0Fh
0x140039b1c  jbe     short loc_140039B58
0x140039b1e  mov     rax, [rbp+150h+var_A0]
0x140039b25  inc     rdx; unsigned __int64
0x140039b28  cmp     rdx, 1000h
0x140039b2f  jb      short loc_140039B4F
0x140039b31  mov     rcx, [rax-8]
0x140039b35  sub     rax, rcx
0x140039b38  sub     rax, 8
0x140039b3c  cmp     rax, 1Fh
0x140039b40  ja      short loc_140039B48
0x140039b42  add     rdx, 27h ; '''
0x140039b46  jmp     short loc_140039B52
0x140039b48  mov     ecx, 5
0x140039b4d  int     29h; Win8: RtlFailFast(ecx)
0x140039b4f  mov     rcx, rax; void *
0x140039b52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140039b57  nop
0x140039b58  test    bl, 1
0x140039b5b  jz      short loc_140039BA3
0x140039b5d  mov     rdx, [rbp+150h+var_48]
0x140039b64  cmp     rdx, 0Fh
0x140039b68  jbe     short loc_140039BA3
0x140039b6a  mov     rax, [rbp+150h+var_60]
0x140039b71  inc     rdx; unsigned __int64
0x140039b74  cmp     rdx, 1000h
0x140039b7b  jb      short loc_140039B9B
0x140039b7d  mov     rcx, [rax-8]
0x140039b81  sub     rax, rcx
0x140039b84  sub     rax, 8
0x140039b88  cmp     rax, 1Fh
0x140039b8c  ja      short loc_140039B94
0x140039b8e  add     rdx, 27h ; '''
0x140039b92  jmp     short loc_140039B9E
0x140039b94  mov     ecx, 5
0x140039b99  int     29h; Win8: RtlFailFast(ecx)
0x140039b9b  mov     rcx, rax; void *
0x140039b9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140039ba3  mov     rdx, r15
0x140039ba6  lea     rcx, [rsp+250h+var_1E8]
0x140039bab  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x140039bb0  nop
0x140039bb1  mov     rax, [rsp+250h+var_200]
0x140039bb6  movsxd  rcx, dword ptr [rax+4]
0x140039bba  lea     rax, ??_7?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable'
0x140039bc1  mov     [rsp+rcx+250h+var_200], rax
0x140039bc6  mov     rcx, [rsp+250h+var_200]
0x140039bcb  movsxd  rdx, dword ptr [rcx+4]
0x140039bcf  lea     r8d, [rdx-98h]
0x140039bd6  mov     [rsp+rdx+250h+var_204], r8d
0x140039bdb  mov     [rsp+250h+var_1E8], r13
0x140039be0  lea     rcx, [rsp+250h+var_1E8]
0x140039be5  call    ?_Tidy@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IEAAXXZ; std::stringbuf::_Tidy(void)
0x140039bea  lea     rcx, [rsp+250h+var_1E8]
0x140039bef  call    cs:__imp_??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::streambuf::~streambuf<char,std::char_traits<char>>(void)
0x140039bf5  lea     rcx, [rsp+250h+var_1E0]
0x140039bfa  call    cs:__imp_??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::iostream::~basic_iostream<char,std::char_traits<char>>(void)
0x140039c00  lea     rcx, [rbp+150h+var_168]
0x140039c04  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x140039c0a  mov     rax, r15
0x140039c0d  mov     rcx, [rbp+150h+var_40]
0x140039c14  xor     rcx, rsp; StackCookie
0x140039c17  call    __security_check_cookie
0x140039c1c  mov     rbx, [rsp+250h+arg_18]
0x140039c24  add     rsp, 220h
0x140039c2b  pop     r15
0x140039c2d  pop     r14
0x140039c2f  pop     r13
0x140039c31  pop     r12
0x140039c33  pop     rdi
0x140039c34  pop     rsi
0x140039c35  pop     rbp
0x140039c36  retn
```
