# CLI::Formatter::make_subcommands(CLI::App const *,CLI::AppFormatMode)

- ea: `0x140039c40`
- end: `0x14003a7ca`
- name: `?make_subcommands@Formatter@CLI@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBVApp@2@W4AppFormatMode@2@@Z`
- size: `2954`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400083f0`
- `0x14000c50c`
- `0x14000f43c`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010614`
- `0x140010620`
- `0x14001062c`
- `0x140012110`
- `0x140014710`
- `0x140020300`
- `0x1400349d0`
- `0x140035200`
- `0x140039c40`
- `0x140044d4c`
- `0x14004a9e0`
- `0x14004aa1c`
- `0x14004aaac`
- `0x14004b384`
- `0x140067010`

## import_xrefs

- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a743`
- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a743`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a739`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a739`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a74d`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x14003a74d`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x140039cc9`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x140039cc9`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140039caf`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140039caf`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140039cfa`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x140039cfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void *__fastcall CLI::Formatter::make_subcommands(__int64 a1, void *a2, __int64 a3, int a4)
{
  __int64 v4; // rdi
  _BYTE *v6; // rdx
  __int64 v7; // r12
  __int64 v8; // r15
  _QWORD *v9; // r8
  _QWORD *v10; // rax
  _QWORD *v11; // rdx
  unsigned __int64 v12; // rdx
  _QWORD *v13; // rcx
  _OWORD *v14; // rsi
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rbx
  size_t v17; // rax
  size_t v18; // rcx
  _QWORD *v19; // rax
  void *v20; // rax
  void *v21; // rcx
  void *v22; // rbx
  _QWORD *v23; // rbx
  void **v24; // r14
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rdi
  size_t v27; // rax
  size_t v28; // rcx
  _QWORD *v29; // rax
  void *v30; // rax
  void *v31; // rcx
  unsigned __int64 v32; // rdx
  _QWORD *v33; // rsi
  _QWORD *v34; // r14
  unsigned int v35; // r15d
  __int64 v36; // rax
  _QWORD *v37; // rdx
  __int64 v38; // rax
  _QWORD *v39; // rcx
  unsigned __int64 v40; // rbx
  size_t v41; // rbx
  __int64 *v42; // r13
  void *v43; // rax
  __int64 *v44; // r12
  __int64 *v45; // rax
  __int64 *v46; // rdx
  __int64 *v47; // r8
  __int64 *v48; // rbx
  __int64 *i; // rdi
  _QWORD *v50; // rdx
  __int64 *v51; // r15
  __int64 v52; // r14
  _QWORD *v53; // rsi
  unsigned __int64 v54; // rdi
  _QWORD *v55; // rax
  _QWORD *v56; // rdx
  unsigned __int64 v57; // rdx
  void *v58; // rcx
  unsigned __int64 v59; // rbx
  size_t v60; // rax
  size_t v61; // rcx
  _QWORD *v62; // rax
  void *v63; // rax
  void *v64; // rcx
  _QWORD *v65; // rax
  _QWORD *v66; // rdx
  unsigned __int64 v67; // rdx
  void *v68; // rcx
  unsigned __int64 v69; // rdx
  void *v70; // rsi
  char *v71; // rbx
  char *v72; // rdi
  unsigned __int64 v73; // rdx
  void *v74; // rcx
  unsigned __int64 v75; // rdx
  int v77; // [rsp+20h] [rbp-E0h]
  int v78; // [rsp+20h] [rbp-E0h]
  void *v79[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE *v80; // [rsp+38h] [rbp-C8h]
  __int64 v81; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v82; // [rsp+48h] [rbp-B8h] BYREF
  int v83; // [rsp+50h] [rbp-B0h]
  __int64 v84; // [rsp+58h] [rbp-A8h]
  char *v85; // [rsp+60h] [rbp-A0h]
  _QWORD *v86; // [rsp+68h] [rbp-98h]
  __int128 v87; // [rsp+70h] [rbp-90h] BYREF
  __int64 v88; // [rsp+80h] [rbp-80h]
  __int64 v89; // [rsp+88h] [rbp-78h]
  void *v90; // [rsp+90h] [rbp-70h]
  int v91; // [rsp+9Ch] [rbp-64h]
  _QWORD v92[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v93; // [rsp+B0h] [rbp-50h] BYREF
  void **v94; // [rsp+B8h] [rbp-48h] BYREF
  char v95[96]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v96; // [rsp+120h] [rbp+20h]
  int v97; // [rsp+128h] [rbp+28h]
  _BYTE v98[104]; // [rsp+138h] [rbp+38h] BYREF
  void *Src[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v100; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v101; // [rsp+1B8h] [rbp+B8h]
  __int128 v102; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 v103; // [rsp+1D0h] [rbp+D0h]
  unsigned __int64 v104; // [rsp+1D8h] [rbp+D8h]
  _QWORD v105[7]; // [rsp+1E0h] [rbp+E0h] BYREF
  _QWORD *v106; // [rsp+218h] [rbp+118h]
  void *v107; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int64 v108; // [rsp+238h] [rbp+138h]
  _BYTE v109[56]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE *v110; // [rsp+278h] [rbp+178h]

  v83 = a4;
  v4 = a3;
  v84 = a3;
  v90 = a2;
  v89 = a1;
  v82 = a2;
  v92[0] = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'};
  v93 = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'};
  std::ios::ios(v98);
  v77 = 16;
  std::iostream::basic_iostream<char>(v92, &v94, 0);
  *(_QWORD *)((char *)v92 + *(int *)(v92[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
  *(int *)((char *)&v91 + *(int *)(v92[0] + 4LL)) = *(_DWORD *)(v92[0] + 4LL) - 152;
  std::streambuf::streambuf(&v94);
  v94 = &std::stringbuf::`vftable';
  v96 = 0;
  v97 = 0;
  v110 = 0;
  CLI::App::get_subcommands(v4, &v87, v109);
  if ( v110 )
  {
    v6 = v109;
    LOBYTE(v6) = v110 != v109;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v110 + 32LL))(v110, v6);
  }
  *(_OWORD *)v79 = 0;
  v80 = 0;
  v7 = *((_QWORD *)&v87 + 1);
  v8 = v87;
  if ( (_QWORD)v87 != *((_QWORD *)&v87 + 1) )
  {
    while ( 1 )
    {
      v9 = *(_QWORD **)v8;
      if ( !*(_QWORD *)(*(_QWORD *)v8 + 24LL) )
      {
        if ( v9[108] )
        {
          v10 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 48LL))(a1, &v102);
          v11 = v10[3] <= 0xFu ? v10 : (_QWORD *)*v10;
          std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v93, v11, v10[2]);
          v12 = v104;
          if ( v104 > 0xF )
          {
            v13 = (_QWORD *)v102;
LABEL_52:
            v32 = v12 + 1;
            if ( v32 >= 0x1000 )
            {
              if ( (unsigned __int64)v13 - *(v13 - 1) - 8 > 0x1F )
LABEL_143:
                __fastfail(5u);
              v32 += 39LL;
              v13 = (_QWORD *)*(v13 - 1);
            }
            operator delete(v13, v32);
            goto LABEL_56;
          }
        }
        goto LABEL_56;
      }
      *(_OWORD *)Src = 0;
      v100 = 0;
      v101 = 0;
      if ( v9[109] <= 0xFu )
        v14 = v9 + 106;
      else
        v14 = (_OWORD *)v9[106];
      v15 = v9[108];
      if ( v15 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Xlen_string();
      if ( v15 > 0xF )
        break;
      v100 = v9[108];
      v101 = 15;
      *(_OWORD *)Src = *v14;
LABEL_29:
      if ( v15 )
      {
        v22 = v79[1];
        if ( *(void **)std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_char_std::char_traits_char__std::allocator_char___________lambda_d3e9bf8ec7f235596a56e5dd45d10b59___(
                         &v82,
                         v79[0],
                         v79[1],
                         Src,
                         v77) == v22 )
        {
          v23 = v79[1];
          if ( v79[1] != v80 )
          {
            *(_OWORD *)v79[1] = 0;
            v23[2] = 0;
            v23[3] = 0;
            v24 = Src;
            if ( v101 > 0xF )
              v24 = (void **)Src[0];
            v25 = v100;
            if ( v100 > 0x7FFFFFFFFFFFFFFFLL )
              std::_Xlen_string();
            if ( v100 <= 0xF )
            {
              v23[2] = v100;
              v23[3] = 15;
              *(_OWORD *)v23 = *(_OWORD *)v24;
              v79[1] = (char *)v79[1] + 32;
              goto LABEL_50;
            }
            v26 = v100 | 0xF;
            if ( (v100 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
            {
              v26 = 0x7FFFFFFFFFFFFFFFLL;
              v27 = 0x8000000000000027uLL;
              goto LABEL_45;
            }
            if ( v26 < 0x16 )
              v26 = 22;
            v28 = v26 + 1;
            if ( v26 == -1 )
            {
              v29 = 0;
            }
            else if ( v28 < 0x1000 )
            {
              v29 = operator new(v28);
            }
            else
            {
              v27 = v26 + 40;
              if ( v26 + 40 < v26 + 1 )
                std::_Throw_bad_array_new_length();
LABEL_45:
              v30 = operator new(v27);
              v31 = v30;
              if ( !v30 )
                __fastfail(5u);
              v29 = (_QWORD *)(((unsigned __int64)v30 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *(v29 - 1) = v31;
            }
            *v23 = v29;
            v23[2] = v25;
            v23[3] = v26;
            memcpy_0(v29, v24, v25 + 1);
            v79[1] = (char *)v79[1] + 32;
            goto LABEL_50;
          }
          std::vector<std::string>::_Emplace_reallocate<std::string const &>(v79, v79[1], Src);
        }
      }
LABEL_50:
      v12 = v101;
      if ( v101 > 0xF )
      {
        v13 = Src[0];
        goto LABEL_52;
      }
LABEL_56:
      v8 += 8;
      if ( v8 == v7 )
      {
        v4 = v84;
        goto LABEL_58;
      }
    }
    v16 = v15 | 0xF;
    if ( (v15 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v16 = 0x7FFFFFFFFFFFFFFFLL;
      v17 = 0x8000000000000027uLL;
LABEL_25:
      v20 = operator new(v17);
      v21 = v20;
      if ( !v20 )
        goto LABEL_143;
      v19 = (_QWORD *)(((unsigned __int64)v20 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v19 - 1) = v21;
      goto LABEL_28;
    }
    if ( v16 < 0x16 )
      v16 = 22;
    v18 = v16 + 1;
    if ( v16 == -1 )
    {
      v19 = 0;
    }
    else
    {
      if ( v18 >= 0x1000 )
      {
        v17 = v16 + 40;
        if ( v16 + 40 < v16 + 1 )
          std::_Throw_bad_array_new_length();
        goto LABEL_25;
      }
      v19 = operator new(v18);
    }
LABEL_28:
    Src[0] = v19;
    v100 = v15;
    v101 = v16;
    memcpy_0(v19, v14, v15 + 1);
    v15 = v100;
    goto LABEL_29;
  }
LABEL_58:
  v33 = v79[0];
  v86 = v79[0];
  v34 = v79[1];
  v82 = v79[1];
  if ( v79[0] != v79[1] )
  {
    v35 = 16;
    while ( 1 )
    {
      v36 = std::operator<<<std::char_traits<char>>(&v93, "\n");
      if ( v33[3] <= 0xFu )
        v37 = v33;
      else
        v37 = (_QWORD *)*v33;
      v38 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v36, v37, v33[2]);
      std::operator<<<std::char_traits<char>>(v38, ":\n");
      v105[0] = &std::_Func_impl_no_alloc<_lambda_8cdc0452b3e198991d11a2d5b533c925_,bool,CLI::App const *>::`vftable';
      v105[1] = v33;
      v39 = v105;
      v106 = v105;
      v40 = (__int64)(*(_QWORD *)(v4 + 776) - *(_QWORD *)(v4 + 768)) >> 4;
      *(_OWORD *)Src = 0;
      v85 = 0;
      v100 = 0;
      if ( v40 )
      {
        if ( v40 > 0x1FFFFFFFFFFFFFFFLL )
          std::vector<std::shared_ptr<CLI::App>>::_Xlength();
        v41 = 8 * v40;
        if ( v41 )
        {
          if ( v41 < 0x1000 )
          {
            v42 = (__int64 *)operator new(v41);
          }
          else
          {
            if ( v41 + 39 < v41 )
              std::_Throw_bad_array_new_length();
            v43 = operator new(v41 + 39);
            if ( !v43 )
              __fastfail(5u);
            v42 = (__int64 *)(((unsigned __int64)v43 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v42 - 1) = (__int64)v43;
          }
        }
        else
        {
          v42 = 0;
        }
        Src[0] = v42;
        v85 = (char *)&v42[v41 / 8];
        v100 = (unsigned __int64)&v42[v41 / 8];
        memset_0(v42, 0, v41);
        v44 = &v42[v41 / 8];
        Src[1] = &v42[v41 / 8];
        v39 = v106;
        v4 = v84;
      }
      else
      {
        v44 = (__int64 *)Src[1];
        v42 = (__int64 *)Src[0];
      }
      v78 = v35 | 2;
      v45 = *(__int64 **)(v4 + 776);
      v46 = *(__int64 **)(v4 + 768);
      v47 = v42;
      if ( v46 != v45 )
      {
        do
        {
          *v47 = *v46;
          v46 += 2;
          ++v47;
        }
        while ( v46 != v45 );
        v39 = v106;
      }
      if ( v39 )
      {
        v48 = v42;
        if ( v42 != v44 )
        {
          while ( 1 )
          {
            v81 = *v48;
            if ( !v39 )
            {
              std::_Xbad_function_call();
              __debugbreak();
            }
            if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, __int64 *, __int64 *))(*v39 + 16LL))(v39, &v81, v47) )
              break;
            if ( ++v48 == v44 )
              break;
            v39 = v106;
          }
          v39 = v106;
        }
        if ( v48 != v44 )
        {
          for ( i = v48 + 1; i != v44; v39 = v106 )
          {
            v81 = *i;
            if ( !v39 )
            {
              std::_Xbad_function_call();
LABEL_169:
              std::_Throw_bad_array_new_length();
            }
            if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, __int64 *, __int64 *))(*v39 + 16LL))(v39, &v81, v47) )
              *v48++ = *i;
            ++i;
          }
          if ( v48 != v44 )
          {
            memmove_0(v48, v44, 0);
            v44 = v48;
            Src[1] = v48;
            v39 = v106;
          }
        }
      }
      if ( v39 )
      {
        v50 = v105;
        LOBYTE(v50) = v39 != v105;
        (*(void (__fastcall **)(_QWORD *, _QWORD *, __int64 *))(*v39 + 32LL))(v39, v50, v47);
        v106 = 0;
      }
      v51 = v42;
      if ( v42 != v44 )
        break;
LABEL_134:
      v35 = v78 & 0xFFFFFFFD;
      if ( v42 )
      {
        v69 = 8 * ((v85 - (char *)v42) >> 3);
        if ( v69 >= 0x1000 )
        {
          if ( (unsigned __int64)v42 - *(v42 - 1) - 8 > 0x1F )
            goto LABEL_143;
          v69 += 39LL;
          v42 = (__int64 *)*(v42 - 1);
        }
        operator delete(v42, v69);
      }
      v33 += 4;
      v86 = v33;
      if ( v33 == v34 )
        goto LABEL_144;
      v4 = v84;
    }
    while ( 1 )
    {
      v52 = *v51;
      v53 = (_QWORD *)(*v51 + 8);
      v54 = *(_QWORD *)(*v51 + 24);
      if ( v54 )
      {
        if ( v83 == 1 )
        {
          v102 = 0;
          v103 = 0;
          v104 = 0;
          if ( v53[3] > 0xFu )
            v53 = (_QWORD *)*v53;
          if ( v54 > 0x7FFFFFFFFFFFFFFFLL )
            std::_Xlen_string();
          if ( v54 <= 0xF )
          {
            v103 = v54;
            v104 = 15;
            v102 = *(_OWORD *)v53;
LABEL_123:
            v65 = (_QWORD *)CLI::App::help(v52, &v107, &v102, 2);
            if ( v65[3] <= 0xFu )
              v66 = v65;
            else
              v66 = (_QWORD *)*v65;
            std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v93, v66, v65[2]);
            if ( v108 > 0xF )
            {
              v67 = v108 + 1;
              v68 = v107;
              if ( v108 + 1 >= 0x1000 )
              {
                if ( (unsigned __int64)v107 - *((_QWORD *)v107 - 1) - 8 > 0x1F )
LABEL_142:
                  __fastfail(5u);
                v67 = v108 + 40;
                v68 = (void *)*((_QWORD *)v107 - 1);
              }
              operator delete(v68, v67);
            }
            std::operator<<<std::char_traits<char>>(&v93, "\n");
            goto LABEL_132;
          }
          v59 = v54 | 0xF;
          if ( (v54 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
          {
            v59 = 0x7FFFFFFFFFFFFFFFLL;
            v60 = 0x8000000000000027uLL;
            goto LABEL_119;
          }
          if ( v59 < 0x16 )
            v59 = 22;
          v61 = v59 + 1;
          if ( v59 == -1 )
          {
            v62 = 0;
          }
          else if ( v61 < 0x1000 )
          {
            v62 = operator new(v61);
          }
          else
          {
            v60 = v59 + 40;
            if ( v59 + 40 < v59 + 1 )
              goto LABEL_169;
LABEL_119:
            v63 = operator new(v60);
            v64 = v63;
            if ( !v63 )
              goto LABEL_142;
            v62 = (_QWORD *)(((unsigned __int64)v63 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v62 - 1) = v64;
          }
          *(_QWORD *)&v102 = v62;
          v103 = v54;
          v104 = v59;
          memcpy_0(v62, v53, v54 + 1);
          goto LABEL_123;
        }
        v55 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v89 + 40LL))(
                          v89,
                          &v102,
                          *v51);
        if ( v55[3] <= 0xFu )
          v56 = v55;
        else
          v56 = (_QWORD *)*v55;
        std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v93, v56, v55[2]);
        if ( v104 > 0xF )
        {
          v57 = v104 + 1;
          v58 = (void *)v102;
          if ( v104 + 1 >= 0x1000 )
          {
            if ( (unsigned __int64)(v102 - *(_QWORD *)(v102 - 8) - 8) > 0x1F )
              goto LABEL_142;
            v57 = v104 + 40;
            v58 = *(void **)(v102 - 8);
          }
          operator delete(v58, v57);
        }
      }
LABEL_132:
      if ( ++v51 == v44 )
      {
        v33 = v86;
        v34 = v82;
        goto LABEL_134;
      }
    }
  }
LABEL_144:
  v70 = v90;
  std::stringbuf::str(&v94, v90);
  v71 = (char *)v79[0];
  if ( v79[0] )
  {
    v72 = (char *)v79[1];
    if ( v79[0] != v79[1] )
    {
      do
      {
        std::string::_Tidy_deallocate(v71);
        v71 += 32;
      }
      while ( v71 != v72 );
      v71 = (char *)v79[0];
    }
    v73 = (v80 - v71) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v73 >= 0x1000 )
    {
      if ( (unsigned __int64)&v71[-*((_QWORD *)v71 - 1) - 8] > 0x1F )
        __fastfail(5u);
      v73 += 39LL;
      v71 = (char *)*((_QWORD *)v71 - 1);
    }
    operator delete(v71, v73);
    *(_OWORD *)v79 = 0;
    v80 = 0;
  }
  v74 = (void *)v87;
  if ( (_QWORD)v87 )
  {
    v75 = 8 * ((v88 - (__int64)v87) >> 3);
    if ( v75 >= 0x1000 )
    {
      if ( (unsigned __int64)(v87 - *(_QWORD *)(v87 - 8) - 8) > 0x1F )
        __fastfail(5u);
      v75 += 39LL;
      v74 = *(void **)(v87 - 8);
    }
    operator delete(v74, v75);
    v87 = 0;
    v88 = 0;
  }
  *(_QWORD *)((char *)v92 + *(int *)(v92[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
  *(int *)((char *)&v91 + *(int *)(v92[0] + 4LL)) = *(_DWORD *)(v92[0] + 4LL) - 152;
  v94 = &std::stringbuf::`vftable';
  std::stringbuf::_Tidy(&v94);
  std::streambuf::~streambuf<char,std::char_traits<char>>(&v94);
  std::iostream::~basic_iostream<char,std::char_traits<char>>(v95);
  std::ios::~ios<char,std::char_traits<char>>(v98);
  return v70;
}

```

## disassembly

```asm
0x140039c40  mov     [rsp-8+arg_18], rbx
0x140039c45  push    rbp
0x140039c46  push    rsi
0x140039c47  push    rdi
0x140039c48  push    r12
0x140039c4a  push    r13
0x140039c4c  push    r14
0x140039c4e  push    r15
0x140039c50  lea     rbp, [rsp-190h]
0x140039c58  sub     rsp, 290h
0x140039c5f  mov     rax, cs:__security_cookie
0x140039c66  xor     rax, rsp
0x140039c69  mov     [rbp+1C0h+var_40], rax
0x140039c70  mov     [rsp+2C0h+var_270], r9d
0x140039c75  mov     rdi, r8
0x140039c78  mov     [rsp+2C0h+var_268], r8
0x140039c7d  mov     [rbp+1C0h+var_230], rdx
0x140039c81  mov     r13, rcx
0x140039c84  mov     [rbp+1C0h+var_238], rcx
0x140039c88  mov     [rsp+2C0h+var_278], rdx
0x140039c8d  xor     r14d, r14d
0x140039c90  mov     [rsp+2C0h+var_2A0], r14d
0x140039c95  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_istream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'}
0x140039c9c  mov     [rbp+1C0h+var_220], rax
0x140039ca0  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_ostream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::ostream'}
0x140039ca7  mov     [rbp+1C0h+var_210], rax
0x140039cab  lea     rcx, [rbp+1C0h+var_188]
0x140039caf  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x140039cb5  nop
0x140039cb6  mov     [rsp+2C0h+var_2A0], 10h
0x140039cbe  xor     r8d, r8d
0x140039cc1  lea     rdx, [rbp+1C0h+var_208]
0x140039cc5  lea     rcx, [rbp+1C0h+var_220]
0x140039cc9  call    cs:__imp_??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z; std::iostream::basic_iostream<char>(std::streambuf *)
0x140039ccf  nop
0x140039cd0  mov     rax, [rbp+1C0h+var_220]
0x140039cd4  movsxd  rcx, dword ptr [rax+4]
0x140039cd8  lea     rax, ??_7?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable'
0x140039cdf  mov     [rbp+rcx+1C0h+var_220], rax
0x140039ce4  mov     rax, [rbp+1C0h+var_220]
0x140039ce8  movsxd  rcx, dword ptr [rax+4]
0x140039cec  lea     edx, [rcx-98h]
0x140039cf2  mov     [rbp+rcx+1C0h+var_224], edx
0x140039cf6  lea     rcx, [rbp+1C0h+var_208]
0x140039cfa  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x140039d00  lea     rax, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x140039d07  mov     [rbp+1C0h+var_208], rax
0x140039d0b  mov     [rbp+1C0h+var_1A0], r14
0x140039d0f  mov     [rbp+1C0h+var_198], r14d
0x140039d13  mov     [rbp+1C0h+var_48], r14
0x140039d1a  lea     r8, [rbp+1C0h+var_80]
0x140039d21  lea     rdx, [rsp+2C0h+var_250]
0x140039d26  mov     rcx, rdi
0x140039d29  call    ?get_subcommands@App@CLI@@QEBA?AV?$vector@PEBVApp@CLI@@V?$allocator@PEBVApp@CLI@@@std@@@std@@AEBV?$function@$$A6A_NPEBVApp@CLI@@@Z@4@@Z; CLI::App::get_subcommands(std::function<bool (CLI::App const *)> const &)
0x140039d2e  nop
0x140039d2f  mov     rcx, [rbp+1C0h+var_48]
0x140039d36  test    rcx, rcx
0x140039d39  jz      short loc_140039D54
0x140039d3b  mov     rax, [rcx]
0x140039d3e  lea     rdx, [rbp+1C0h+var_80]
0x140039d45  cmp     rcx, rdx
0x140039d48  setnz   dl
0x140039d4b  mov     rax, [rax+20h]
0x140039d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039d54  xorps   xmm0, xmm0
0x140039d57  movdqu  xmmword ptr [rsp+2C0h+var_298], xmm0
0x140039d5d  mov     [rsp+2C0h+var_288], r14
0x140039d62  mov     r15, qword ptr [rsp+2C0h+var_250]
0x140039d67  mov     r12, qword ptr [rsp+2C0h+var_250+8]
0x140039d6c  mov     rax, 7FFFFFFFFFFFFFFFh
0x140039d76  mov     rcx, 8000000000000027h
0x140039d80  mov     edx, 16h
0x140039d85  cmp     r15, r12
0x140039d88  jz      loc_14003A0B3
0x140039d8e  xchg    ax, ax
0x140039d90  mov     r8, [r15]
0x140039d93  cmp     qword ptr [r8+18h], 0
0x140039d98  jnz     short loc_140039DFA
0x140039d9a  cmp     qword ptr [r8+360h], 0
0x140039da2  jz      loc_14003A0A1
0x140039da8  mov     rax, [r13+0]
0x140039dac  lea     rdx, [rbp+1C0h+var_100]
0x140039db3  mov     rcx, r13
0x140039db6  mov     rax, [rax+30h]
0x140039dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039dbf  nop
0x140039dc0  cmp     qword ptr [rax+18h], 0Fh
0x140039dc5  jbe     short loc_140039DCC
0x140039dc7  mov     rdx, [rax]
0x140039dca  jmp     short loc_140039DCF
0x140039dcc  mov     rdx, rax
0x140039dcf  mov     r8, [rax+10h]
0x140039dd3  lea     rcx, [rbp+1C0h+var_210]
0x140039dd7  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x140039ddc  nop
0x140039ddd  mov     rdx, [rbp+1C0h+var_E8]
0x140039de4  cmp     rdx, 0Fh
0x140039de8  jbe     loc_14003A088
0x140039dee  mov     rcx, qword ptr [rbp+1C0h+var_100]
0x140039df5  jmp     loc_14003A05B
0x140039dfa  xorps   xmm0, xmm0
0x140039dfd  movups  xmmword ptr [rbp+1C0h+Src], xmm0
0x140039e04  mov     [rbp+1C0h+var_110], r14
0x140039e0b  mov     [rbp+1C0h+var_108], r14
0x140039e12  cmp     qword ptr [r8+368h], 0Fh
0x140039e1a  jbe     short loc_140039E25
0x140039e1c  mov     rsi, [r8+350h]
0x140039e23  jmp     short loc_140039E2C
0x140039e25  lea     rsi, [r8+350h]
0x140039e2c  mov     rdi, [r8+360h]
0x140039e33  cmp     rdi, rax
0x140039e36  ja      loc_14003A7A6
0x140039e3c  cmp     rdi, 0Fh
0x140039e40  ja      short loc_140039E63
0x140039e42  mov     [rbp+1C0h+var_110], rdi
0x140039e49  mov     [rbp+1C0h+var_108], 0Fh
0x140039e54  movups  xmm0, xmmword ptr [rsi]
0x140039e57  movups  xmmword ptr [rbp+1C0h+Src], xmm0
0x140039e5e  jmp     loc_140039EF5
0x140039e63  mov     rbx, rdi
0x140039e66  or      rbx, 0Fh
0x140039e6a  cmp     rbx, rax
0x140039e6d  jbe     short loc_140039E77
0x140039e6f  mov     rbx, rax
0x140039e72  mov     rax, rcx
0x140039e75  jmp     short loc_140039EA3
0x140039e77  cmp     rbx, 16h
0x140039e7b  cmovb   rbx, rdx
0x140039e7f  lea     rcx, [rbx+1]; Size
0x140039e83  test    rcx, rcx
0x140039e86  jnz     short loc_140039E8D
0x140039e88  mov     rax, r14
0x140039e8b  jmp     short loc_140039ECA
0x140039e8d  cmp     rcx, 1000h
0x140039e94  jb      short loc_140039EC5
0x140039e96  lea     rax, [rcx+27h]
0x140039e9a  cmp     rax, rcx
0x140039e9d  jbe     loc_14003A794
0x140039ea3  mov     rcx, rax; Size
0x140039ea6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140039eab  mov     rcx, rax
0x140039eae  test    rax, rax
0x140039eb1  jz      loc_14003A611
0x140039eb7  add     rax, 27h ; '''
0x140039ebb  and     rax, 0FFFFFFFFFFFFFFE0h
0x140039ebf  mov     [rax-8], rcx
0x140039ec3  jmp     short loc_140039ECA
0x140039ec5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140039eca  mov     [rbp+1C0h+Src], rax
0x140039ed1  mov     [rbp+1C0h+var_110], rdi
0x140039ed8  mov     [rbp+1C0h+var_108], rbx
0x140039edf  lea     r8, [rdi+1]; Size
0x140039ee3  mov     rdx, rsi; Src
0x140039ee6  mov     rcx, rax; void *
0x140039ee9  call    memcpy_0
0x140039eee  mov     rdi, [rbp+1C0h+var_110]
0x140039ef5  test    rdi, rdi
0x140039ef8  jz      loc_14003A047
0x140039efe  mov     rbx, [rsp+2C0h+var_298+8]
0x140039f03  lea     r9, [rbp+1C0h+Src]
0x140039f0a  mov     r8, rbx
0x140039f0d  mov     rdx, [rsp+2C0h+var_298]
0x140039f12  lea     rcx, [rsp+2C0h+var_278]
0x140039f17  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_std__basic_string_char_std__char_traits_char__std__allocator_char___________lambda_d3e9bf8ec7f235596a56e5dd45d10b59___
0x140039f1c  cmp     [rax], rbx
0x140039f1f  jnz     loc_14003A047
0x140039f25  mov     rbx, [rsp+2C0h+var_298+8]
0x140039f2a  cmp     rbx, [rsp+2C0h+var_288]
0x140039f2f  jz      loc_14003A032
0x140039f35  xorps   xmm0, xmm0
0x140039f38  movups  xmmword ptr [rbx], xmm0
0x140039f3b  mov     [rbx+10h], r14
0x140039f3f  mov     [rbx+18h], r14
0x140039f43  lea     r14, [rbp+1C0h+Src]
0x140039f4a  cmp     [rbp+1C0h+var_108], 0Fh
0x140039f52  cmova   r14, [rbp+1C0h+Src]
0x140039f5a  mov     rsi, [rbp+1C0h+var_110]
0x140039f61  mov     rax, 7FFFFFFFFFFFFFFFh
0x140039f6b  cmp     rsi, rax
0x140039f6e  ja      loc_14003A7A0
0x140039f74  cmp     rsi, 0Fh
0x140039f78  ja      short loc_140039F9B
0x140039f7a  mov     [rbx+10h], rsi
0x140039f7e  mov     qword ptr [rbx+18h], 0Fh
0x140039f86  movups  xmm0, xmmword ptr [r14]
0x140039f8a  movups  xmmword ptr [rbx], xmm0
0x140039f8d  add     [rsp+2C0h+var_298+8], 20h ; ' '
0x140039f93  xor     r14d, r14d
0x140039f96  jmp     loc_14003A047
0x140039f9b  mov     rdi, rsi
0x140039f9e  or      rdi, 0Fh
0x140039fa2  cmp     rdi, rax
0x140039fa5  jbe     short loc_140039FB6
0x140039fa7  mov     rdi, rax
0x140039faa  mov     rax, 8000000000000027h
0x140039fb4  jmp     short loc_140039FE6
0x140039fb6  cmp     rdi, 16h
0x140039fba  mov     eax, 16h
0x140039fbf  cmovb   rdi, rax
0x140039fc3  lea     rcx, [rdi+1]; Size
0x140039fc7  test    rcx, rcx
0x140039fca  jnz     short loc_140039FD0
0x140039fcc  xor     eax, eax
0x140039fce  jmp     short loc_14003A00D
0x140039fd0  cmp     rcx, 1000h
0x140039fd7  jb      short loc_14003A008
0x140039fd9  lea     rax, [rcx+27h]
0x140039fdd  cmp     rax, rcx
0x140039fe0  jbe     loc_14003A79A
0x140039fe6  mov     rcx, rax; Size
0x140039fe9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140039fee  mov     rcx, rax
0x140039ff1  test    rax, rax
0x140039ff4  jz      loc_14003A103
0x140039ffa  add     rax, 27h ; '''
0x140039ffe  and     rax, 0FFFFFFFFFFFFFFE0h
0x14003a002  mov     [rax-8], rcx
0x14003a006  jmp     short loc_14003A00D
0x14003a008  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003a00d  mov     [rbx], rax
0x14003a010  mov     [rbx+10h], rsi
0x14003a014  mov     [rbx+18h], rdi
0x14003a018  lea     r8, [rsi+1]; Size
0x14003a01c  mov     rdx, r14; Src
0x14003a01f  mov     rcx, rax; void *
0x14003a022  call    memcpy_0
0x14003a027  add     [rsp+2C0h+var_298+8], 20h ; ' '
0x14003a02d  xor     r14d, r14d
0x14003a030  jmp     short loc_14003A047
0x14003a032  lea     r8, [rbp+1C0h+Src]
0x14003a039  mov     rdx, rbx
0x14003a03c  lea     rcx, [rsp+2C0h+var_298]
0x14003a041  call    ??$_Emplace_reallocate@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@AEBV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string const &>(std::string * const,std::string const &)
0x14003a046  nop
0x14003a047  mov     rdx, [rbp+1C0h+var_108]
0x14003a04e  cmp     rdx, 0Fh
0x14003a052  jbe     short loc_14003A088
0x14003a054  mov     rcx, [rbp+1C0h+Src]
0x14003a05b  inc     rdx
0x14003a05e  cmp     rdx, 1000h
0x14003a065  jb      short loc_14003A083
0x14003a067  mov     rax, [rcx-8]
0x14003a06b  sub     rcx, rax
0x14003a06e  sub     rcx, 8
0x14003a072  cmp     rcx, 1Fh
0x14003a076  ja      loc_14003A611
0x14003a07c  add     rdx, 27h ; '''; unsigned __int64
0x14003a080  mov     rcx, rax; void *
0x14003a083  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003a088  mov     edx, 16h
0x14003a08d  mov     rcx, 8000000000000027h
0x14003a097  mov     rax, 7FFFFFFFFFFFFFFFh
0x14003a0a1  add     r15, 8
0x14003a0a5  cmp     r15, r12
0x14003a0a8  jnz     loc_140039D90
0x14003a0ae  mov     rdi, [rsp+2C0h+var_268]
0x14003a0b3  mov     rsi, [rsp+2C0h+var_298]
0x14003a0b8  mov     [rsp+2C0h+var_258], rsi
0x14003a0bd  mov     r14, [rsp+2C0h+var_298+8]
0x14003a0c2  mov     [rsp+2C0h+var_278], r14
0x14003a0c7  cmp     rsi, r14
0x14003a0ca  jz      loc_14003A618
0x14003a0d0  mov     r15d, 10h
0x14003a0d6  mov     r12, 1FFFFFFFFFFFFFFFh
0x14003a0e0  lea     rbx, ??_7?$_Func_impl_no_alloc@V_lambda_8cdc0452b3e198991d11a2d5b533c925_@@_NPEBVApp@CLI@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_8cdc0452b3e198991d11a2d5b533c925_,bool,CLI::App const *>::`vftable'
0x14003a0e7  lea     rdx, asc_14006C698; "\n"
0x14003a0ee  lea     rcx, [rbp+1C0h+var_210]
0x14003a0f2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14003a0f7  cmp     qword ptr [rsi+18h], 0Fh
0x14003a0fc  jbe     short loc_14003A10A
0x14003a0fe  mov     rdx, [rsi]
0x14003a101  jmp     short loc_14003A10D
0x14003a103  mov     ecx, 5
0x14003a108  int     29h; Win8: RtlFailFast(ecx)
0x14003a10a  mov     rdx, rsi
0x14003a10d  mov     r8, [rsi+10h]
0x14003a111  mov     rcx, rax
0x14003a114  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x14003a119  lea     rdx, asc_14006D1A4; ":\n"
0x14003a120  mov     rcx, rax
0x14003a123  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14003a128  mov     [rbp+1C0h+var_E0], rbx
0x14003a12f  mov     [rbp+1C0h+var_D8], rsi
0x14003a136  lea     rcx, [rbp+1C0h+var_E0]
0x14003a13d  mov     [rbp+1C0h+var_A8], rcx
0x14003a144  mov     rbx, [rdi+308h]
0x14003a14b  sub     rbx, [rdi+300h]
0x14003a152  sar     rbx, 4
0x14003a156  xorps   xmm0, xmm0
0x14003a159  movdqu  xmmword ptr [rbp+1C0h+Src], xmm0
0x14003a161  xor     eax, eax
0x14003a163  mov     [rsp+2C0h+var_260], rax
0x14003a168  mov     [rbp+1C0h+var_110], rax
0x14003a16f  test    rbx, rbx
0x14003a172  jz      loc_14003A20C
0x14003a178  cmp     rbx, r12
0x14003a17b  ja      loc_14003A7B2
0x14003a181  lea     rbx, ds:0[rbx*8]
0x14003a189  test    rbx, rbx
0x14003a18c  jnz     short loc_14003A193
  ... truncated ...
```
