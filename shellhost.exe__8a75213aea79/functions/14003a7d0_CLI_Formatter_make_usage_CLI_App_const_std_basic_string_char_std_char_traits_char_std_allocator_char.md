# CLI::Formatter::make_usage(CLI::App const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x14003a7d0`
- end: `0x14003b350`
- name: `?make_usage@Formatter@CLI@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBVApp@2@V34@@Z`
- size: `2944`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400083f0`
- `0x140008910`
- `0x14000c50c`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010614`
- `0x140010ad0`
- `0x1400324d0`
- `0x1400326b0`
- `0x140034640`
- `0x1400349d0`
- `0x140034ed0`
- `0x14003a7d0`
- `0x140044933`
- `0x140044d4c`
- `0x14004a9e0`
- `0x14004aa1c`
- `0x14004aaac`
- `0x14004b384`
- `0x14005063c`
- `0x14005d2e0`
- `0x140067010`

## import_xrefs

- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003b2d6`
- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003b2d6`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003b2cc`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003b2cc`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003b2e0`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003b2e0`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x14003a9ee`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x14003a9ee`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x14003a9d1`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x14003a9d1`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x14003aa1f`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x14003aa1f`

## string_xrefs

- `0x14003b04a`: `SUBCOMMAND`
- `0x14003b041`: `SUBCOMMANDS`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall CLI::Formatter::make_usage(__int64 a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v6; // rbx
  size_t v7; // rsi
  __int64 v8; // r15
  unsigned __int64 v9; // r13
  void **v10; // r12
  void *v11; // rdi
  size_t v12; // r14
  size_t v13; // rax
  void *v14; // rax
  size_t v15; // rcx
  _QWORD *v16; // rax
  unsigned __int64 v17; // rdx
  void *v18; // rcx
  _QWORD *v19; // rsi
  int v21; // r12d
  __int64 v22; // rdi
  __int64 i; // rsi
  _QWORD *label; // rax
  _QWORD *v25; // rdx
  __int64 v26; // rax
  const char *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rdx
  unsigned __int64 v31; // rdx
  void *v32; // rcx
  _QWORD *v33; // rbx
  __int64 v34; // rax
  _QWORD *v35; // rdx
  __int64 v36; // rax
  unsigned __int64 v37; // rdx
  void *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r8
  _QWORD *v41; // rbx
  _QWORD *v42; // r14
  unsigned __int64 v43; // rsi
  unsigned __int64 v44; // rbx
  void **v45; // rdi
  void *v46; // rax
  void **v47; // rax
  unsigned __int64 v48; // rdx
  char *v49; // rax
  unsigned __int64 v50; // rdx
  char *v51; // rcx
  unsigned __int64 v52; // rdx
  void *v53; // rcx
  _QWORD *v54; // rbx
  __int64 v55; // rax
  _QWORD *v56; // rdx
  unsigned __int64 v57; // rdx
  void *v58; // rcx
  _BYTE *v59; // rdi
  char *v60; // rsi
  char *j; // rbx
  unsigned __int64 v62; // rdx
  _BYTE *v63; // rcx
  __int64 *subcommands; // rax
  unsigned __int64 v65; // rdx
  __int64 v66; // rbx
  __int64 v67; // rdi
  unsigned __int64 v68; // rdx
  void *v69; // rax
  _QWORD *v70; // rdx
  unsigned __int64 v71; // rdi
  const char *v72; // rbx
  size_t v73; // rax
  _QWORD *v74; // rsi
  const char *v75; // r14
  const char *v76; // rbx
  __int64 v77; // rax
  __int64 v78; // rax
  _QWORD *v79; // rdx
  __int64 v80; // rax
  unsigned __int64 v81; // rdx
  void *v82; // rcx
  unsigned __int64 v83; // rdx
  void *v84; // rax
  unsigned __int64 v85; // rdx
  void *v86; // rax
  char *v87; // rbx
  char *v88; // rdi
  unsigned __int64 v89; // rdx
  void *v90; // rcx
  void *v91; // rcx
  void *v92[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v93; // [rsp+30h] [rbp-D0h]
  __int64 v94; // [rsp+38h] [rbp-C8h]
  _QWORD *v95; // [rsp+48h] [rbp-B8h]
  __int64 v96; // [rsp+50h] [rbp-B0h]
  int v97; // [rsp+58h] [rbp-A8h]
  __int128 v98; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v99; // [rsp+70h] [rbp-90h]
  __int128 v100; // [rsp+78h] [rbp-88h] BYREF
  __int64 v101; // [rsp+88h] [rbp-78h]
  void *v102[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v103; // [rsp+A0h] [rbp-60h]
  void *v104; // [rsp+A8h] [rbp-58h]
  void *Src[2]; // [rsp+B0h] [rbp-50h] BYREF
  size_t Size; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v107; // [rsp+C8h] [rbp-38h]
  _QWORD v108[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v109; // [rsp+E0h] [rbp-20h] BYREF
  void **v110; // [rsp+E8h] [rbp-18h] BYREF
  char v111[96]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v112; // [rsp+150h] [rbp+50h]
  int v113; // [rsp+158h] [rbp+58h]
  _BYTE v114[104]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v115[9]; // [rsp+1D0h] [rbp+D0h] BYREF
  void *v116[2]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v117; // [rsp+228h] [rbp+128h]
  unsigned __int64 v118; // [rsp+230h] [rbp+130h]
  __int128 v119; // [rsp+238h] [rbp+138h] BYREF
  __int128 v120; // [rsp+248h] [rbp+148h]
  void *v121[3]; // [rsp+258h] [rbp+158h] BYREF
  unsigned __int64 v122; // [rsp+270h] [rbp+170h]
  void **v123; // [rsp+290h] [rbp+190h]
  _QWORD v124[7]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _QWORD *v125; // [rsp+2D8h] [rbp+1D8h]

  v104 = a4;
  v6 = a2;
  v95 = a2;
  v96 = a1;
  v115[8] = a4;
  v97 = 0;
  CLI::App::get_usage(a3, Src);
  v7 = Size;
  if ( !Size )
  {
    v108[0] = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'};
    v109 = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'};
    std::ios::ios(v114);
    v21 = 4;
    v97 = 4;
    std::iostream::basic_iostream<char>(v108, &v110, 0);
    *(_QWORD *)((char *)v108 + *(int *)(v108[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
    *(_DWORD *)((char *)&v107 + *(int *)(v108[0] + 4LL) + 4) = *(_DWORD *)(v108[0] + 4LL) - 152;
    std::streambuf::streambuf(&v110);
    v110 = &std::stringbuf::`vftable';
    v112 = 0;
    v113 = 0;
    v22 = a4[2];
    *(_OWORD *)v92 = 0;
    v93 = 5;
    v94 = 15;
    LODWORD(v92[0]) = *(_DWORD *)"Usage";
    WORD2(v92[0]) = (unsigned __int8)aUsage[4];
    i = v96;
    label = (_QWORD *)CLI::FormatterBase::get_label(v96, v116, v92);
    if ( label[3] <= 0xFu )
      v25 = label;
    else
      v25 = (_QWORD *)*label;
    v26 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v109, v25, label[2]);
    v27 = " ";
    if ( !v22 )
      v27 = (const char *)&qword_14006D7D8;
    v28 = std::operator<<<std::char_traits<char>>(v26, ":");
    v29 = std::operator<<<std::char_traits<char>>(v28, v27);
    if ( a4[3] <= 0xFu )
      v30 = a4;
    else
      v30 = (_QWORD *)*a4;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v29, v30, a4[2]);
    if ( v118 > 0xF )
    {
      v31 = v118 + 1;
      if ( v118 + 1 < 0x1000 )
      {
        v32 = v116[0];
      }
      else
      {
        v32 = (void *)*((_QWORD *)v116[0] - 1);
        if ( (unsigned __int64)((char *)v116[0] - (char *)v32 - 8) > 0x1F )
          goto LABEL_147;
        v31 = v118 + 40;
      }
      operator delete(v32, v31);
    }
    CLI::App::get_groups(a3, v102);
    v121[0] = &std::_Func_impl_no_alloc<_lambda_09fcb96a0091d06c4d7a943ad5daa92b_,bool,CLI::Option const *>::`vftable';
    v123 = v121;
    CLI::App::get_options(a3, &v100, v121);
    if ( (_QWORD)v100 != *((_QWORD *)&v100 + 1) )
    {
      HIWORD(v92[1]) = 0;
      v93 = 7;
      v94 = 15;
      qmemcpy(v92, "OPTION", 6);
      *(void **)((char *)v92 + 6) = (void *)(unsigned __int8)aOptions_0[6];
      v33 = (_QWORD *)CLI::FormatterBase::get_label(i, v116, v92);
      v34 = std::operator<<<std::char_traits<char>>(&v109, " [");
      v35 = v33[3] <= 0xFu ? v33 : (_QWORD *)*v33;
      v36 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v34, v35, v33[2]);
      std::operator<<<std::char_traits<char>>(v36, "]");
      if ( v118 > 0xF )
      {
        v37 = v118 + 1;
        if ( v118 + 1 < 0x1000 )
        {
          v38 = v116[0];
        }
        else
        {
          v38 = (void *)*((_QWORD *)v116[0] - 1);
          if ( (unsigned __int64)((char *)v116[0] - (char *)v38 - 8) > 0x1F )
            goto LABEL_130;
          v37 = v118 + 40;
        }
        operator delete(v38, v37);
      }
    }
    v115[0] = &std::_Func_impl_no_alloc<_lambda_d3735f8d41378676cb846b861a0062b5_,bool,CLI::Option const *>::`vftable';
    v115[7] = v115;
    CLI::App::get_options(a3, &v98, v115);
    v41 = (_QWORD *)*((_QWORD *)&v98 + 1);
    v42 = (_QWORD *)v98;
    if ( (_QWORD)v98 != *((_QWORD *)&v98 + 1) )
    {
      v43 = (__int64)(*((_QWORD *)&v98 + 1) - v98) >> 3;
      *(_OWORD *)v92 = 0;
      v93 = 0;
      if ( v43 )
      {
        if ( v43 > 0x7FFFFFFFFFFFFFFLL )
          std::vector<void *>::_Xlength(0, v39, v40);
        v44 = 32 * v43;
        if ( 32 * v43 )
        {
          if ( v44 < 0x1000 )
          {
            v45 = (void **)operator new(32 * v43);
          }
          else
          {
            if ( v44 + 39 < v44 )
              std::_Throw_bad_array_new_length();
            v46 = operator new(v44 + 39);
            if ( !v46 )
              goto LABEL_123;
            v45 = (void **)(((unsigned __int64)v46 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v45 - 1) = v46;
          }
        }
        else
        {
          v45 = 0;
        }
        v92[0] = v45;
        v93 = (__int64)&v45[v44 / 8];
        v47 = v45;
        do
        {
          *(_OWORD *)v47 = 0;
          v47[2] = 0;
          v47[3] = (void *)15;
          *(_BYTE *)v47 = 0;
          v47 += 4;
          --v43;
        }
        while ( v43 );
        v92[1] = v47;
        v41 = (_QWORD *)*((_QWORD *)&v98 + 1);
        v42 = (_QWORD *)v98;
      }
      else
      {
        v45 = (void **)v92[0];
      }
      for ( i = v96; v42 != v41; v45 += 4 )
      {
        (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)i + 112LL))(i, &v119, *v42);
        v21 |= 0x10u;
        if ( v45 == (void **)&v119 )
        {
          if ( *((_QWORD *)&v120 + 1) > 0xFu )
          {
            v52 = *((_QWORD *)&v120 + 1) + 1LL;
            v53 = (void *)v119;
            if ( (unsigned __int64)(*((_QWORD *)&v120 + 1) + 1LL) >= 0x1000 )
            {
              if ( (unsigned __int64)(v119 - *(_QWORD *)(v119 - 8) - 8) > 0x1F )
                goto LABEL_88;
              v52 = *((_QWORD *)&v120 + 1) + 40LL;
              v53 = *(void **)(v119 - 8);
            }
            operator delete(v53, v52);
          }
        }
        else
        {
          v48 = (unsigned __int64)v45[3];
          if ( v48 > 0xF )
          {
            v49 = (char *)*v45;
            v50 = v48 + 1;
            if ( v50 < 0x1000 )
            {
              v51 = (char *)*v45;
            }
            else
            {
              v51 = (char *)*((_QWORD *)v49 - 1);
              if ( (unsigned __int64)(v49 - v51 - 8) > 0x1F )
                goto LABEL_88;
              v50 += 39LL;
            }
            operator delete(v51, v50);
          }
          *(_OWORD *)v45 = v119;
          *((_OWORD *)v45 + 1) = v120;
        }
        ++v42;
      }
      *(_OWORD *)v116 = 0;
      v117 = 1;
      v118 = 15;
      LOWORD(v116[0]) = (unsigned __int8)asc_14006CB48[0];
      v54 = (_QWORD *)CLI::detail::join<std::vector<std::string>>(v121, v92, v116);
      v55 = std::operator<<<std::char_traits<char>>(&v109, " ");
      if ( v54[3] <= 0xFu )
        v56 = v54;
      else
        v56 = (_QWORD *)*v54;
      std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v55, v56, v54[2]);
      if ( v122 > 0xF )
      {
        v57 = v122 + 1;
        if ( v122 + 1 < 0x1000 )
        {
          v58 = v121[0];
        }
        else
        {
          v58 = (void *)*((_QWORD *)v121[0] - 1);
          if ( (unsigned __int64)((char *)v121[0] - (char *)v58 - 8) > 0x1F )
LABEL_88:
            __fastfail(5u);
          v57 = v122 + 40;
        }
        operator delete(v58, v57);
      }
      v59 = v92[0];
      if ( v92[0] )
      {
        v60 = (char *)v92[1];
        for ( j = (char *)v92[0]; j != v60; j += 32 )
          std::string::_Tidy_deallocate(j);
        v62 = (v93 - (_QWORD)v59) & 0xFFFFFFFFFFFFFFE0uLL;
        if ( v62 < 0x1000 )
        {
          v63 = v59;
        }
        else
        {
          v63 = (_BYTE *)*((_QWORD *)v59 - 1);
          if ( (unsigned __int64)(v59 - v63 - 8) > 0x1F )
            goto LABEL_123;
          v62 += 39LL;
        }
        operator delete(v63, v62);
        i = v96;
      }
    }
    v124[0] = &std::_Func_impl_no_alloc<_lambda_14aa1979d0133804d20c1bba149a20fa_,bool,CLI::App const *>::`vftable';
    v125 = v124;
    subcommands = (__int64 *)CLI::App::get_subcommands(a3, v92, v124);
    v66 = *subcommands;
    v67 = subcommands[1];
    if ( v92[0] )
    {
      v68 = 8 * ((signed __int64)(v93 - (unsigned __int64)v92[0]) >> 3);
      if ( v68 < 0x1000 )
      {
        v69 = v92[0];
      }
      else
      {
        v69 = (void *)*((_QWORD *)v92[0] - 1);
        if ( (unsigned __int64)((char *)v92[0] - (char *)v69 - 8) > 0x1F )
          __fastfail(5u);
        v68 += 39LL;
      }
      operator delete(v69, v68);
      *(_OWORD *)v92 = 0;
      v93 = 0;
    }
    if ( v125 )
    {
      v70 = v124;
      LOBYTE(v70) = v125 != v124;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v125 + 32LL))(v125, v70);
    }
    if ( v66 == v67 )
      goto LABEL_126;
    v71 = *(_QWORD *)(a3 + 808);
    if ( *(_QWORD *)(a3 + 816) < 2u || (v72 = "SUBCOMMANDS", v71 > 1) )
      v72 = "SUBCOMMAND";
    *(_OWORD *)v116 = 0;
    v117 = 0;
    v118 = 0;
    v73 = strlen_0(v72);
    std::string::_Construct<1,char const *>(v116, v72, v73);
    v74 = (_QWORD *)CLI::FormatterBase::get_label(i, v121, v116);
    v75 = (const char *)&qword_14006D7D8;
    v76 = (const char *)&qword_14006D7D8;
    if ( !v71 )
      v76 = "[";
    v77 = std::operator<<<std::char_traits<char>>(&v109, " ");
    v78 = std::operator<<<std::char_traits<char>>(v77, v76);
    if ( v74[3] <= 0xFu )
      v79 = v74;
    else
      v79 = (_QWORD *)*v74;
    v80 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v78, v79, v74[2]);
    if ( !v71 )
      v75 = "]";
    std::operator<<<std::char_traits<char>>(v80, v75);
    v65 = v122;
    if ( v122 <= 0xF )
      goto LABEL_126;
    v81 = v122 + 1;
    if ( v122 + 1 < 0x1000 )
    {
      v82 = v121[0];
      goto LABEL_125;
    }
    v82 = (void *)*((_QWORD *)v121[0] - 1);
    if ( (unsigned __int64)((char *)v121[0] - (char *)v82 - 8) <= 0x1F )
    {
      v81 = v122 + 40;
LABEL_125:
      operator delete(v82, v81);
LABEL_126:
      LOBYTE(v65) = 10;
      std::operator<<<std::char_traits<char>>(&v109, v65);
      v19 = v95;
      std::stringbuf::str(&v110, v95);
      if ( !(_QWORD)v98 )
      {
LABEL_133:
        if ( (_QWORD)v100 )
        {
          v85 = 8 * ((v101 - (__int64)v100) >> 3);
          if ( v85 < 0x1000 )
          {
            v86 = (void *)v100;
          }
          else
          {
            v86 = *(void **)(v100 - 8);
            if ( (unsigned __int64)(v100 - (_QWORD)v86 - 8) > 0x1F )
              __fastfail(5u);
            v85 += 39LL;
          }
          operator delete(v86, v85);
          v100 = 0;
          v101 = 0;
        }
        v87 = (char *)v102[0];
        if ( !v102[0] )
          goto LABEL_150;
        v88 = (char *)v102[1];
        if ( v102[0] != v102[1] )
        {
          do
          {
            std::string::_Tidy_deallocate(v87);
            v87 += 32;
          }
          while ( v87 != v88 );
          v87 = (char *)v102[0];
        }
        v89 = (v103 - (_QWORD)v87) & 0xFFFFFFFFFFFFFFE0uLL;
        if ( v89 < 0x1000 )
        {
          v90 = v87;
          goto LABEL_149;
        }
        v90 = (void *)*((_QWORD *)v87 - 1);
        if ( (unsigned __int64)(v87 - (_BYTE *)v90 - 8) <= 0x1F )
        {
          v89 += 39LL;
LABEL_149:
          operator delete(v90, v89);
          *(_OWORD *)v102 = 0;
          v103 = 0;
LABEL_150:
          *(_QWORD *)((char *)v108 + *(int *)(v108[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
          *(_DWORD *)((char *)&v107 + *(int *)(v108[0] + 4LL) + 4) = *(_DWORD *)(v108[0] + 4LL) - 152;
          v110 = &std::stringbuf::`vftable';
          std::stringbuf::_Tidy(&v110);
          std::streambuf::~streambuf<char,std::char_traits<char>>(&v110);
          std::iostream::~basic_iostream<char,std::char_traits<char>>(v111);
          std::ios::~ios<char,std::char_traits<char>>(v114);
          if ( v107 <= 0xF )
            goto LABEL_27;
          if ( v107 + 1 < 0x1000 )
          {
            operator delete(Src[0], v107 + 1);
            goto LABEL_27;
          }
          v91 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v91 - 8) <= 0x1F )
          {
            operator delete(v91, v107 + 40);
            goto LABEL_27;
          }
          goto LABEL_154;
        }
LABEL_147:
        __fastfail(5u);
      }
      v83 = 8 * ((v99 - (__int64)v98) >> 3);
      if ( v83 < 0x1000 )
      {
        v84 = (void *)v98;
        goto LABEL_132;
      }
      v84 = *(void **)(v98 - 8);
      if ( (unsigned __int64)(v98 - (_QWORD)v84 - 8) <= 0x1F )
      {
        v83 += 39LL;
LABEL_132:
        operator delete(v84, v83);
        v98 = 0;
        v99 = 0;
        goto LABEL_133;
      }
LABEL_130:
      __fastfail(5u);
    }
LABEL_123:
    __fastfail(5u);
  }
  v8 = 0x7FFFFFFFFFFFFFFFLL;
  if ( Size == 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  v9 = v107;
  v10 = Src;
  v11 = Src[0];
  if ( v107 > 0xF )
    v10 = (void **)Src[0];
  *(_OWORD *)v6 = 0;
  v6[2] = 0;
  v6[3] = 0;
  v12 = v7 + 1;
  if ( v7 + 1 <= 0xF )
  {
    v8 = 15;
    v16 = v95;
  }
  else
  {
    if ( (v12 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v8 = v12 | 0xF;
      if ( (v12 | 0xF) < 0x16 )
        v8 = 22;
      v15 = v8 + 1;
      if ( v8 == -1 )
      {
        v6 = 0;
        v16 = v95;
        *v95 = 0;
        goto LABEL_20;
      }
      if ( v15 < 0x1000 )
      {
        v6 = operator new(v15);
        v16 = v95;
        *v95 = v6;
        goto LABEL_20;
      }
      v13 = v8 + 40;
      if ( v8 + 40 < (unsigned __int64)(v8 + 1) )
        std::_Throw_bad_array_new_length();
    }
    else
    {
      v13 = 0x8000000000000027uLL;
    }
    v14 = operator new(v13);
    if ( !v14 )
      __fastfail(5u);
    v6 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v6 - 1) = v14;
    v16 = v95;
    *v95 = v6;
  }
LABEL_20:
  v16[2] = v12;
  v16[3] = v8;
  memcpy_0(v6, v10, v7);
  *((_BYTE *)v6 + v7) = asc_14006C698[0];
  *((_BYTE *)v6 + v12) = 0;
  if ( v9 > 0xF )
  {
    v17 = v9 + 1;
    if ( v9 + 1 < 0x1000 )
    {
      v18 = v11;
      goto LABEL_25;
    }
    v18 = (void *)*((_QWORD *)v11 - 1);
    if ( (unsigned __int64)((_BYTE *)v11 - (_BYTE *)v18 - 8) <= 0x1F )
    {
      v17 = v9 + 40;
LABEL_25:
      operator delete(v18, v17);
      goto LABEL_26;
    }
LABEL_154:
    __fastfail(5u);
  }
LABEL_26:
  v19 = v95;
LABEL_27:
  std::string::_Tidy_deallocate(v104);
  return v19;
}

```

## disassembly

```asm
0x14003a7d0  push    rbp
0x14003a7d2  push    rbx
0x14003a7d3  push    rsi
0x14003a7d4  push    rdi
0x14003a7d5  push    r12
0x14003a7d7  push    r13
0x14003a7d9  push    r14
0x14003a7db  push    r15
0x14003a7dd  lea     rbp, [rsp-1F8h]
0x14003a7e5  sub     rsp, 2F8h
0x14003a7ec  mov     rax, cs:__security_cookie
0x14003a7f3  xor     rax, rsp
0x14003a7f6  mov     [rbp+230h+var_50], rax
0x14003a7fd  mov     r14, r9
0x14003a800  mov     [rbp+230h+var_288], r9
0x14003a804  mov     r13, r8
0x14003a807  mov     rbx, rdx
0x14003a80a  mov     [rsp+330h+var_2E8], rdx
0x14003a80f  mov     [rsp+330h+var_2E0], rcx
0x14003a814  mov     [rbp+230h+var_120], rdx
0x14003a81b  mov     [rbp+230h+var_120], r9
0x14003a822  xor     edi, edi
0x14003a824  mov     [rsp+330h+var_2D8], edi
0x14003a828  lea     rdx, [rbp+230h+Src]
0x14003a82c  mov     rcx, r8
0x14003a82f  call    ?get_usage@App@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CLI::App::get_usage(void)
0x14003a834  nop
0x14003a835  mov     rsi, [rbp+230h+Size]
0x14003a839  test    rsi, rsi
0x14003a83c  jz      loc_14003A9B7
0x14003a842  mov     r15, 7FFFFFFFFFFFFFFFh
0x14003a84c  mov     rax, r15
0x14003a84f  sub     rax, rsi
0x14003a852  cmp     rax, 1
0x14003a856  jb      loc_14003B344
0x14003a85c  mov     r13, [rbp+230h+var_268]
0x14003a860  lea     r12, [rbp+230h+Src]
0x14003a864  mov     rdi, [rbp+230h+Src]
0x14003a868  cmp     r13, 0Fh
0x14003a86c  cmova   r12, rdi
0x14003a870  xorps   xmm0, xmm0
0x14003a873  movups  xmmword ptr [rbx], xmm0
0x14003a876  xor     edx, edx
0x14003a878  mov     [rbx+10h], rdx
0x14003a87c  mov     [rbx+18h], rdx
0x14003a880  lea     r14, [rsi+1]
0x14003a884  cmp     r14, 0Fh
0x14003a888  jbe     loc_14003A91D
0x14003a88e  mov     rax, r14
0x14003a891  or      rax, 0Fh
0x14003a895  cmp     rax, r15
0x14003a898  jbe     short loc_14003A8B8
0x14003a89a  mov     rax, 8000000000000027h
0x14003a8a4  mov     rcx, rax; Size
0x14003a8a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003a8ac  test    rax, rax
0x14003a8af  jnz     short loc_14003A8F5
0x14003a8b1  mov     ecx, 5
0x14003a8b6  int     29h; Win8: RtlFailFast(ecx)
0x14003a8b8  mov     r15, rax
0x14003a8bb  mov     ecx, 16h
0x14003a8c0  cmp     rax, rcx
0x14003a8c3  cmovb   r15, rcx
0x14003a8c7  lea     rcx, [r15+1]; Size
0x14003a8cb  test    rcx, rcx
0x14003a8ce  jnz     short loc_14003A8DD
0x14003a8d0  mov     rbx, rdx
0x14003a8d3  mov     rax, [rsp+330h+var_2E8]
0x14003a8d8  mov     [rax], rdx
0x14003a8db  jmp     short loc_14003A928
0x14003a8dd  cmp     rcx, 1000h
0x14003a8e4  jb      short loc_14003A90B
0x14003a8e6  lea     rax, [rcx+27h]
0x14003a8ea  cmp     rax, rcx
0x14003a8ed  jbe     loc_14003B33E
0x14003a8f3  jmp     short loc_14003A8A4
0x14003a8f5  lea     rbx, [rax+27h]
0x14003a8f9  and     rbx, 0FFFFFFFFFFFFFFE0h
0x14003a8fd  mov     [rbx-8], rax
0x14003a901  mov     rax, [rsp+330h+var_2E8]
0x14003a906  mov     [rax], rbx
0x14003a909  jmp     short loc_14003A928
0x14003a90b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003a910  mov     rbx, rax
0x14003a913  mov     rax, [rsp+330h+var_2E8]
0x14003a918  mov     [rax], rbx
0x14003a91b  jmp     short loc_14003A928
0x14003a91d  mov     r15d, 0Fh
0x14003a923  mov     rax, [rsp+330h+var_2E8]
0x14003a928  mov     [rax+10h], r14
0x14003a92c  mov     [rax+18h], r15
0x14003a930  mov     r8, rsi; Size
0x14003a933  mov     rdx, r12; Src
0x14003a936  mov     rcx, rbx; void *
0x14003a939  call    memcpy_0
0x14003a93e  movzx   eax, word ptr cs:asc_14006C698; "\n"
0x14003a945  mov     [rbx+rsi], al
0x14003a948  mov     byte ptr [rbx+r14], 0
0x14003a94d  cmp     r13, 0Fh
0x14003a951  jbe     short loc_14003A983
0x14003a953  lea     rdx, [r13+1]; unsigned __int64
0x14003a957  cmp     rdx, 1000h
0x14003a95e  jb      short loc_14003A97B
0x14003a960  mov     rcx, [rdi-8]
0x14003a964  sub     rdi, rcx
0x14003a967  sub     rdi, 8
0x14003a96b  cmp     rdi, 1Fh
0x14003a96f  ja      loc_14003B324
0x14003a975  add     rdx, 27h ; '''
0x14003a979  jmp     short loc_14003A97E
0x14003a97b  mov     rcx, rdi; void *
0x14003a97e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003a983  mov     rsi, [rsp+330h+var_2E8]
0x14003a988  mov     rcx, [rbp+230h+var_288]; void *
0x14003a98c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14003a991  mov     rax, rsi
0x14003a994  mov     rcx, [rbp+230h+var_50]
0x14003a99b  xor     rcx, rsp; StackCookie
0x14003a99e  call    __security_check_cookie
0x14003a9a3  add     rsp, 2F8h
0x14003a9aa  pop     r15
0x14003a9ac  pop     r14
0x14003a9ae  pop     r13
0x14003a9b0  pop     r12
0x14003a9b2  pop     rdi
0x14003a9b3  pop     rsi
0x14003a9b4  pop     rbx
0x14003a9b5  pop     rbp
0x14003a9b6  retn
0x14003a9b7  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_istream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'}
0x14003a9be  mov     [rbp+230h+var_260], rax
0x14003a9c2  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_ostream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'}
0x14003a9c9  mov     [rbp+230h+var_250], rax
0x14003a9cd  lea     rcx, [rbp+230h+var_1C8]
0x14003a9d1  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x14003a9d7  nop
0x14003a9d8  mov     r12d, 4
0x14003a9de  mov     [rsp+330h+var_2D8], r12d
0x14003a9e3  xor     r8d, r8d
0x14003a9e6  lea     rdx, [rbp+230h+var_248]
0x14003a9ea  lea     rcx, [rbp+230h+var_260]
0x14003a9ee  call    cs:__imp_??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z; std::iostream::basic_iostream<char>(std::streambuf *)
0x14003a9f4  nop
0x14003a9f5  mov     rax, [rbp+230h+var_260]
0x14003a9f9  movsxd  rcx, dword ptr [rax+4]
0x14003a9fd  lea     rax, ??_7?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable'
0x14003aa04  mov     [rbp+rcx+230h+var_260], rax
0x14003aa09  mov     rax, [rbp+230h+var_260]
0x14003aa0d  movsxd  rcx, dword ptr [rax+4]
0x14003aa11  lea     edx, [rcx-98h]
0x14003aa17  mov     dword ptr [rbp+rcx+230h+var_268+4], edx
0x14003aa1b  lea     rcx, [rbp+230h+var_248]
0x14003aa1f  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x14003aa25  lea     rax, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x14003aa2c  mov     [rbp+230h+var_248], rax
0x14003aa30  mov     [rbp+230h+var_1E0], rdi
0x14003aa34  mov     [rbp+230h+var_1D8], edi
0x14003aa37  mov     rdi, [r14+10h]
0x14003aa3b  xorps   xmm0, xmm0
0x14003aa3e  movups  xmmword ptr [rsp+330h+var_310], xmm0
0x14003aa43  mov     [rsp+330h+var_300], 5
0x14003aa4c  mov     r15d, 0Fh
0x14003aa52  mov     [rsp+330h+var_2F8], r15
0x14003aa57  mov     eax, dword ptr cs:aUsage; "Usage"
0x14003aa5d  mov     dword ptr [rsp+330h+var_310], eax
0x14003aa61  movzx   eax, byte ptr cs:aUsage+4; "e"
0x14003aa68  mov     byte ptr [rsp+330h+var_310+4], al
0x14003aa6c  mov     byte ptr [rsp+330h+var_310+5], 0
0x14003aa71  lea     r8, [rsp+330h+var_310]
0x14003aa76  lea     rdx, [rbp+230h+var_118]
0x14003aa7d  mov     rsi, [rsp+330h+var_2E0]
0x14003aa82  mov     rcx, rsi
0x14003aa85  call    ?get_label@FormatterBase@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V34@@Z; CLI::FormatterBase::get_label(std::string)
0x14003aa8a  nop
0x14003aa8b  cmp     [rax+18h], r15
0x14003aa8f  jbe     short loc_14003AA96
0x14003aa91  mov     rdx, [rax]
0x14003aa94  jmp     short loc_14003AA99
0x14003aa96  mov     rdx, rax
0x14003aa99  mov     r8, [rax+10h]
0x14003aa9d  lea     rcx, [rbp+230h+var_250]
0x14003aaa1  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x14003aaa6  lea     rcx, qword_14006D7D8
0x14003aaad  lea     rbx, asc_14006CB48; " "
0x14003aab4  test    rdi, rdi
0x14003aab7  cmovz   rbx, rcx
0x14003aabb  lea     rdx, asc_14006CEEC; ":"
0x14003aac2  mov     rcx, rax
0x14003aac5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14003aaca  mov     rcx, rax
0x14003aacd  mov     rdx, rbx
0x14003aad0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14003aad5  cmp     qword ptr [r14+18h], 0Fh
0x14003aada  jbe     short loc_14003AAE1
0x14003aadc  mov     rdx, [r14]
0x14003aadf  jmp     short loc_14003AAE4
0x14003aae1  mov     rdx, r14
0x14003aae4  mov     r8, [r14+10h]
0x14003aae8  mov     rcx, rax
0x14003aaeb  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x14003aaf0  nop
0x14003aaf1  mov     rdx, [rbp+230h+var_100]
0x14003aaf8  cmp     rdx, 0Fh
0x14003aafc  jbe     short loc_14003AB34
0x14003aafe  mov     rax, [rbp+230h+var_118]
0x14003ab05  inc     rdx; unsigned __int64
0x14003ab08  cmp     rdx, 1000h
0x14003ab0f  jb      short loc_14003AB2C
0x14003ab11  mov     rcx, [rax-8]
0x14003ab15  sub     rax, rcx
0x14003ab18  sub     rax, 8
0x14003ab1c  cmp     rax, 1Fh
0x14003ab20  ja      loc_14003B273
0x14003ab26  add     rdx, 27h ; '''
0x14003ab2a  jmp     short loc_14003AB2F
0x14003ab2c  mov     rcx, rax; void *
0x14003ab2f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003ab34  lea     rdx, [rbp+230h+var_2A0]
0x14003ab38  mov     rcx, r13
0x14003ab3b  call    ?get_groups@App@CLI@@QEBA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ; CLI::App::get_groups(void)
0x14003ab40  nop
0x14003ab41  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_09fcb96a0091d06c4d7a943ad5daa92b_@@_NPEBVOption@CLI@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_09fcb96a0091d06c4d7a943ad5daa92b_,bool,CLI::Option const *>::`vftable'
0x14003ab48  mov     [rbp+230h+var_D8], rax
0x14003ab4f  lea     rax, [rbp+230h+var_D8]
0x14003ab56  mov     [rbp+230h+var_A0], rax
0x14003ab5d  lea     r8, [rbp+230h+var_D8]
0x14003ab64  lea     rdx, [rsp+330h+var_2B8]
0x14003ab69  mov     rcx, r13
0x14003ab6c  call    ?get_options@App@CLI@@QEBA?AV?$vector@PEBVOption@CLI@@V?$allocator@PEBVOption@CLI@@@std@@@std@@V?$function@$$A6A_NPEBVOption@CLI@@@Z@4@@Z; CLI::App::get_options(std::function<bool (CLI::Option const *)>)
0x14003ab71  nop
0x14003ab72  mov     rax, qword ptr [rsp+330h+var_2B8]
0x14003ab77  cmp     rax, qword ptr [rbp+230h+var_2B8+8]
0x14003ab7b  jz      loc_14003AC51
0x14003ab81  xor     edx, edx
0x14003ab83  mov     [rsp+330h+var_310+8], rdx
0x14003ab88  mov     [rsp+330h+var_300], 7
0x14003ab91  mov     [rsp+330h+var_2F8], r15
0x14003ab96  mov     rax, qword ptr cs:aOptions_0; "OPTIONS"
0x14003ab9d  mov     dword ptr [rsp+330h+var_310], eax
0x14003aba1  movzx   eax, word ptr cs:aOptions_0+4; "ONS"
0x14003aba8  mov     word ptr [rsp+330h+var_310+4], ax
0x14003abad  movzx   eax, byte ptr cs:aOptions_0+6; "S"
0x14003abb4  mov     byte ptr [rsp+330h+var_310+6], al
0x14003abb8  mov     byte ptr [rsp+330h+var_310+7], dl
0x14003abbc  lea     r8, [rsp+330h+var_310]
0x14003abc1  lea     rdx, [rbp+230h+var_118]
0x14003abc8  mov     rcx, rsi
0x14003abcb  call    ?get_label@FormatterBase@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V34@@Z; CLI::FormatterBase::get_label(std::string)
0x14003abd0  mov     rbx, rax
0x14003abd3  lea     rdx, asc_14006D300; " ["
0x14003abda  lea     rcx, [rbp+230h+var_250]
0x14003abde  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14003abe3  cmp     qword ptr [rbx+18h], 0Fh
0x14003abe8  jbe     short loc_14003ABEF
0x14003abea  mov     rdx, [rbx]
0x14003abed  jmp     short loc_14003ABF2
0x14003abef  mov     rdx, rbx
0x14003abf2  mov     r8, [rbx+10h]
0x14003abf6  mov     rcx, rax
0x14003abf9  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x14003abfe  lea     rdx, asc_14006DACC; "]"
0x14003ac05  mov     rcx, rax
0x14003ac08  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14003ac0d  nop
0x14003ac0e  mov     rdx, [rbp+230h+var_100]
0x14003ac15  cmp     rdx, 0Fh
0x14003ac19  jbe     short loc_14003AC51
0x14003ac1b  mov     rax, [rbp+230h+var_118]
0x14003ac22  inc     rdx; unsigned __int64
0x14003ac25  cmp     rdx, 1000h
0x14003ac2c  jb      short loc_14003AC49
0x14003ac2e  mov     rcx, [rax-8]
0x14003ac32  sub     rax, rcx
0x14003ac35  sub     rax, 8
0x14003ac39  cmp     rax, 1Fh
0x14003ac3d  ja      loc_14003B1A5
0x14003ac43  add     rdx, 27h ; '''
0x14003ac47  jmp     short loc_14003AC4C
0x14003ac49  mov     rcx, rax; void *
0x14003ac4c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003ac51  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d3735f8d41378676cb846b861a0062b5_@@_NPEBVOption@CLI@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d3735f8d41378676cb846b861a0062b5_,bool,CLI::Option const *>::`vftable'
0x14003ac58  mov     [rbp+230h+var_160], rax
0x14003ac5f  lea     rax, [rbp+230h+var_160]
0x14003ac66  mov     [rbp+230h+var_128], rax
0x14003ac6d  lea     r8, [rbp+230h+var_160]
0x14003ac74  lea     rdx, [rsp+330h+var_2D0]
0x14003ac79  mov     rcx, r13
0x14003ac7c  call    ?get_options@App@CLI@@QEBA?AV?$vector@PEBVOption@CLI@@V?$allocator@PEBVOption@CLI@@@std@@@std@@V?$function@$$A6A_NPEBVOption@CLI@@@Z@4@@Z; CLI::App::get_options(std::function<bool (CLI::Option const *)>)
0x14003ac81  nop
0x14003ac82  mov     r14, qword ptr [rsp+330h+var_2D0]
0x14003ac87  mov     rbx, qword ptr [rsp+330h+var_2D0+8]
0x14003ac8c  cmp     r14, rbx
0x14003ac8f  jz      loc_14003AF61
0x14003ac95  mov     rsi, rbx
0x14003ac98  sub     rsi, r14
0x14003ac9b  sar     rsi, 3
0x14003ac9f  xorps   xmm0, xmm0
0x14003aca2  movdqu  xmmword ptr [rsp+330h+var_310], xmm0
0x14003aca8  xor     ecx, ecx
0x14003acaa  mov     [rsp+330h+var_300], rcx
  ... truncated ...
```
