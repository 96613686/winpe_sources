# CLI::App::_parse_single_config(CLI::ConfigItem const &,unsigned __int64)

- ea: `0x140023ac0`
- end: `0x1400246bf`
- name: `?_parse_single_config@App@CLI@@IEAA_NAEBUConfigItem@2@_K@Z`
- size: `3071`
- prototype: `bool __fastcall(CLI::App *__hidden this, const struct CLI::ConfigItem *, unsigned __int64)`
- caller_count: `2`
- callee_count: `41`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140022ef0`
- `0x140023ac0`

## callees

- `0x1400080f8`
- `0x1400083f0`
- `0x1400088d0`
- `0x140008a50`
- `0x14000ba3c`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010608`
- `0x140010614`
- `0x140010620`
- `0x140010668`
- `0x140011af0`
- `0x140012820`
- `0x140018c50`
- `0x14001c6b0`
- `0x14001d120`
- `0x14001ea70`
- `0x14001f090`
- `0x140020300`
- `0x140020750`
- `0x140020fd0`
- `0x140023ac0`
- `0x140024c30`
- `0x140025b40`
- `0x140027480`
- `0x140028890`
- `0x140028950`
- `0x1400304e0`
- `0x140031810`
- `0x1400325d0`
- `0x140034270`
- `0x1400356e0`
- `0x14003e590`
- `0x14003e830`
- `0x14003f230`
- `0x14004a9e0`
- `0x14004aaac`
- `0x140052264`
- `0x14005246c`
- `0x140067010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002420f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002420f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
bool __fastcall CLI::App::_parse_single_config(CLI::App *this, const struct CLI::ConfigItem *a2, unsigned __int64 a3)
{
  void *v6; // rbx
  CLI::App *subcommand; // rsi
  char *v9; // rbx
  char *v10; // rcx
  unsigned __int64 v11; // r12
  __int64 v12; // rdi
  __int64 v13; // rbx
  const void **v14; // rbx
  char *v15; // r14
  char *v16; // rcx
  __int64 v17; // r15
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r12
  size_t v21; // rcx
  char *v22; // rdi
  void *v23; // rax
  char *v24; // r8
  _BYTE *v25; // rdx
  char *v26; // rcx
  size_t v27; // r8
  const void *v28; // rcx
  __int64 v29; // r15
  char *v30; // rax
  CLI::Option *option_no_throw; // r12
  char *v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  unsigned __int64 v36; // rdx
  void *v37; // rcx
  __int64 v38; // r15
  __int64 i; // rbx
  _DWORD *v40; // rdx
  const void **v41; // rdi
  unsigned __int64 v42; // r12
  CLI::Option *v43; // r14
  void **v44; // rsi
  __int64 v45; // rdi
  size_t v46; // rax
  void *v47; // rax
  void *v48; // rcx
  _QWORD *v49; // rax
  size_t v50; // rcx
  __int64 flag_value; // rbx
  unsigned __int64 v52; // rdx
  void *v53; // rax
  __int64 v54; // rax
  unsigned __int64 v55; // rdx
  void *v56; // rax
  unsigned __int64 v57; // rdx
  void *v58; // rcx
  __int64 v59; // rax
  void *v60; // rcx
  bool v61; // cc
  const void **v62; // r13
  _QWORD *v63; // rbx
  _QWORD *v64; // r14
  unsigned __int64 v65; // rsi
  const void *v66; // rcx
  const void *v67; // rbx
  const void *v68; // rcx
  const void *v69; // rcx
  const void **v70; // rcx
  const void *v71; // r15
  const void *v72; // rdx
  _QWORD *v73; // rcx
  size_t v74; // r8
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rdi
  __int64 v79; // rbx
  unsigned int items_expected_max; // eax
  __int64 v81; // rax
  __int64 v82; // rax
  const void **v83; // [rsp+40h] [rbp-228h]
  void *v84; // [rsp+40h] [rbp-228h]
  unsigned __int8 v85; // [rsp+48h] [rbp-220h]
  CLI::Option *v86; // [rsp+50h] [rbp-218h] BYREF
  _BYTE v87[32]; // [rsp+58h] [rbp-210h] BYREF
  void *v88[2]; // [rsp+78h] [rbp-1F0h] BYREF
  __int64 v89; // [rsp+88h] [rbp-1E0h]
  unsigned __int64 v90; // [rsp+90h] [rbp-1D8h]
  void *Src[2]; // [rsp+98h] [rbp-1D0h] BYREF
  __int128 v92; // [rsp+A8h] [rbp-1C0h]
  void *v93[3]; // [rsp+B8h] [rbp-1B0h] BYREF
  unsigned __int64 v94; // [rsp+D0h] [rbp-198h]
  _BYTE pExceptionObject[64]; // [rsp+E0h] [rbp-188h] BYREF
  _BYTE v96[64]; // [rsp+120h] [rbp-148h] BYREF
  _BYTE v97[64]; // [rsp+160h] [rbp-108h] BYREF
  _BYTE v98[64]; // [rsp+1A0h] [rbp-C8h] BYREF
  _BYTE v99[64]; // [rsp+1E0h] [rbp-88h] BYREF

  if ( a3 < (__int64)(*((_QWORD *)a2 + 1) - *(_QWORD *)a2) >> 5 )
  {
    v6 = (void *)std::string::string(v93, *(_QWORD *)a2 + 32 * a3);
    subcommand = (CLI::App *)CLI::App::_find_subcommand(this, v6, 0);
    if ( !subcommand )
    {
      v76 = std::string::string(v88, v6);
      CLI::OptionNotFound::OptionNotFound(pExceptionObject, v76);
      throw (CLI::OptionNotFound *)pExceptionObject;
    }
    std::string::_Tidy_deallocate(v6);
    return CLI::App::_parse_single_config(subcommand, a2, a3 + 1);
  }
  v9 = (char *)a2 + 24;
  v10 = (char *)a2 + 24;
  v11 = *((_QWORD *)a2 + 6);
  if ( v11 > 0xF )
    v10 = *(char **)v9;
  v12 = *((_QWORD *)a2 + 5);
  if ( v12 == 2 && !memcmp_0(v10, "++", 2u) )
  {
    if ( *((_BYTE *)this + 798) )
    {
      CLI::App::increment_parsed(this);
      CLI::App::_trigger_pre_parse(this, 2u);
      v13 = *((_QWORD *)this + 105);
      if ( v13 )
      {
        v14 = (const void **)(v13 + 680);
        v15 = (char *)v14[1];
        v16 = (char *)v14[2];
        if ( v15 != v16 )
        {
          *(_QWORD *)v15 = this;
          v14[1] = (char *)v14[1] + 8;
          return 1;
        }
        v17 = (v15 - (_BYTE *)*v14) >> 3;
        if ( v17 == 0x1FFFFFFFFFFFFFFFLL )
          std::vector<std::shared_ptr<CLI::App>>::_Xlength();
        v18 = (v16 - (_BYTE *)*v14) >> 3;
        v19 = v18 >> 1;
        if ( v18 > 0x1FFFFFFFFFFFFFFFLL - (v18 >> 1) )
          goto LABEL_159;
        v20 = v17 + 1;
        if ( v18 + v19 >= v17 + 1 )
          v20 = v18 + v19;
        if ( v20 > 0x1FFFFFFFFFFFFFFFLL )
          goto LABEL_159;
        v21 = 8 * v20;
        if ( !(8 * v20) )
        {
          v22 = 0;
LABEL_25:
          *(_QWORD *)&v22[8 * v17] = this;
          v24 = (char *)v14[1];
          v25 = *v14;
          v26 = v22;
          if ( v15 == v24 )
          {
            v27 = v24 - v25;
          }
          else
          {
            memmove_0(v22, v25, v15 - v25);
            v27 = (_BYTE *)v14[1] - v15;
            v26 = &v22[8 * v17 + 8];
            v25 = v15;
          }
          memmove_0(v26, v25, v27);
          std::vector<CLI::App *>::_Change_array(v14, v22, v17 + 1, v20);
          return 1;
        }
        if ( v21 < 0x1000 )
        {
          v22 = (char *)operator new(v21);
          goto LABEL_25;
        }
        if ( v21 + 39 < v21 )
LABEL_159:
          std::_Throw_bad_array_new_length();
        v23 = operator new(v21 + 39);
        if ( v23 )
        {
          v22 = (char *)(((unsigned __int64)v23 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v22 - 1) = v23;
          goto LABEL_25;
        }
LABEL_116:
        __fastfail(5u);
      }
    }
    return 1;
  }
  v28 = v9;
  if ( v11 > 0xF )
    v28 = *(const void **)v9;
  if ( v12 == 2 && !memcmp_0(v28, "--", 2u) )
  {
    if ( *((_BYTE *)this + 798) && *((_QWORD *)this + 25) )
    {
      CLI::App::_process_callbacks(this);
      CLI::App::_process_requirements(this);
      CLI::App::run_callback(this, 0, 0);
      return 1;
    }
    return 1;
  }
  v29 = 0x7FFFFFFFFFFFFFFFLL;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - v12) < 2 )
    goto LABEL_156;
  v30 = v9;
  if ( v11 > 0xF )
    v30 = *(char **)v9;
  std::string::string(v88, v85, v9, "--", 2, v30, v12);
  option_no_throw = (CLI::Option *)CLI::App::get_option_no_throw(this, v88);
  v86 = option_no_throw;
  if ( option_no_throw )
    goto LABEL_63;
  if ( *((_QWORD *)a2 + 5) != 1 )
    goto LABEL_46;
  if ( *((_QWORD *)v9 + 2) == 0x7FFFFFFFFFFFFFFFLL )
LABEL_156:
    std::_Xlen_string();
  if ( *((_QWORD *)v9 + 3) <= 0xFu )
    v32 = v9;
  else
    v32 = *(char **)v9;
  std::string::string(v88, v85, v9, "-", 1, v32, *((_QWORD *)v9 + 2));
  option_no_throw = (CLI::Option *)CLI::App::get_option_no_throw(this, v88);
  v86 = option_no_throw;
  if ( !option_no_throw )
  {
LABEL_46:
    v33 = std::string::string(v87, v9);
    option_no_throw = (CLI::Option *)CLI::App::get_option_no_throw(this, v33);
    v86 = option_no_throw;
    if ( !option_no_throw )
    {
      if ( *((_BYTE *)this + 73) == 3 )
      {
        LODWORD(v86) = 0;
        v34 = CLI::ConfigItem::fullname(a2, v88);
        v35 = *((_QWORD *)this + 80);
        if ( v35 == *((_QWORD *)this + 81) )
        {
          std::vector<std::pair<enum CLI::detail::Classifier,std::string>>::_Emplace_reallocate<enum CLI::detail::Classifier,std::string>(
            (char *)this + 632,
            v35,
            &v86,
            v34);
        }
        else
        {
          *(_DWORD *)v35 = 0;
          *(_OWORD *)(v35 + 8) = 0;
          *(_QWORD *)(v35 + 24) = 0;
          *(_QWORD *)(v35 + 32) = 0;
          *(_OWORD *)(v35 + 8) = *(_OWORD *)v34;
          *(_OWORD *)(v35 + 24) = *(_OWORD *)(v34 + 16);
          *(_QWORD *)(v34 + 16) = 0;
          *(_QWORD *)(v34 + 24) = 15;
          *(_BYTE *)v34 = 0;
          *((_QWORD *)this + 80) += 40LL;
        }
        if ( v90 > 0xF )
        {
          v36 = v90 + 1;
          if ( v90 + 1 < 0x1000 )
          {
            v37 = v88[0];
          }
          else
          {
            v37 = (void *)*((_QWORD *)v88[0] - 1);
            if ( (unsigned __int64)((char *)v88[0] - (char *)v37 - 8) > 0x1F )
              goto LABEL_116;
            v36 = v90 + 40;
          }
          operator delete(v37, v36);
        }
      }
      v38 = *((_QWORD *)a2 + 8);
      for ( i = *((_QWORD *)a2 + 7); i != v38; i += 32 )
      {
        LODWORD(v86) = 0;
        v40 = (_DWORD *)*((_QWORD *)this + 80);
        if ( v40 == *((_DWORD **)this + 81) )
        {
          std::vector<std::pair<enum CLI::detail::Classifier,std::string>>::_Emplace_reallocate<enum CLI::detail::Classifier &,std::string const &>(
            (char *)this + 632,
            v40,
            &v86,
            i);
        }
        else
        {
          *v40 = 0;
          std::string::string(v40 + 2, i);
          *((_QWORD *)this + 80) += 40LL;
        }
      }
      return 0;
    }
  }
LABEL_63:
  if ( !*((_BYTE *)option_no_throw + 35) )
  {
    if ( *((_BYTE *)this + 73) != 2 )
    {
      v77 = CLI::ConfigItem::fullname(a2, v87);
      CLI::ConfigError::NotConfigurable(v96, v77);
      throw (CLI::ConfigError *)v96;
    }
    return 0;
  }
  if ( *((_QWORD *)option_no_throw + 71) != *((_QWORD *)option_no_throw + 72) )
    return 1;
  if ( *((_DWORD *)option_no_throw + 108) )
    goto LABEL_154;
  v83 = (const void **)*((_QWORD *)a2 + 8);
  v41 = (const void **)*((_QWORD *)a2 + 7);
  v42 = ((char *)v83 - (char *)v41) >> 5;
  if ( v42 <= 1 )
  {
    (*(void (__fastcall **)(_QWORD, void **, const struct CLI::ConfigItem *))(**((_QWORD **)this + 114) + 16LL))(
      *((_QWORD *)this + 114),
      Src,
      a2);
    v43 = v86;
    if ( !*((_BYTE *)v86 + 36) )
      goto LABEL_97;
    *(_OWORD *)v88 = 0;
    v89 = 0;
    v90 = 0;
    v44 = Src;
    if ( *((_QWORD *)&v92 + 1) > 0xFu )
      v44 = (void **)Src[0];
    v45 = v92;
    if ( (unsigned __int64)v92 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlen_string();
    if ( (unsigned __int64)v92 <= 0xF )
    {
      v89 = v92;
      v90 = 15;
      *(_OWORD *)v88 = *(_OWORD *)v44;
      goto LABEL_88;
    }
    if ( ((unsigned __int64)v92 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v46 = 0x8000000000000027uLL;
LABEL_77:
      v47 = operator new(v46);
      v48 = v47;
      if ( !v47 )
        goto LABEL_109;
      v49 = (_QWORD *)(((unsigned __int64)v47 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v49 - 1) = v48;
      goto LABEL_87;
    }
    v29 = v92 | 0xF;
    if ( ((unsigned __int64)v92 | 0xF) < 0x16 )
      v29 = 22;
    v50 = v29 + 1;
    if ( v29 == -1 )
    {
      v49 = 0;
    }
    else
    {
      if ( v50 >= 0x1000 )
      {
        v46 = v29 + 40;
        if ( v29 + 40 < (unsigned __int64)(v29 + 1) )
          std::_Throw_bad_array_new_length();
        goto LABEL_77;
      }
      v49 = operator new(v50);
    }
LABEL_87:
    v88[0] = v49;
    v89 = v45;
    v90 = v29;
    memcpy_0(v49, v44, v45 + 1);
LABEL_88:
    if ( CLI::detail::to_flag_value(v88) == 1 )
    {
      *(_OWORD *)v88 = 0;
      v89 = 2;
      v90 = 15;
      strcpy((char *)v88, "{}");
      flag_value = CLI::Option::get_flag_value(v43, v93, v9, v88);
      if ( Src != (void **)flag_value )
      {
        if ( *((_QWORD *)&v92 + 1) > 0xFu )
        {
          v52 = *((_QWORD *)&v92 + 1) + 1LL;
          if ( (unsigned __int64)(*((_QWORD *)&v92 + 1) + 1LL) < 0x1000 )
          {
            v53 = Src[0];
          }
          else
          {
            v53 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v53 - 8) > 0x1F )
              goto LABEL_109;
            v52 = *((_QWORD *)&v92 + 1) + 40LL;
          }
          operator delete(v53, v52);
        }
LABEL_104:
        *(_QWORD *)&v92 = 0;
        *((_QWORD *)&v92 + 1) = 15;
        LOBYTE(Src[0]) = 0;
        *(_OWORD *)Src = *(_OWORD *)flag_value;
        v92 = *(_OWORD *)(flag_value + 16);
        *(_BYTE *)flag_value = 0;
        *(_QWORD *)(flag_value + 24) = 15;
        *(_QWORD *)(flag_value + 16) = 0;
        goto LABEL_105;
      }
      goto LABEL_105;
    }
LABEL_97:
    *(_DWORD *)_o__errno() = 0;
    v54 = std::string::string(v88, Src);
    flag_value = CLI::Option::get_flag_value(v43, v93, v9, v54);
    if ( Src != (void **)flag_value )
    {
      if ( *((_QWORD *)&v92 + 1) > 0xFu )
      {
        v55 = *((_QWORD *)&v92 + 1) + 1LL;
        if ( (unsigned __int64)(*((_QWORD *)&v92 + 1) + 1LL) < 0x1000 )
        {
          v56 = Src[0];
        }
        else
        {
          v56 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v56 - 8) > 0x1F )
            goto LABEL_109;
          v55 = *((_QWORD *)&v92 + 1) + 40LL;
        }
        operator delete(v56, v55);
      }
      goto LABEL_104;
    }
LABEL_105:
    if ( v94 <= 0xF )
      goto LABEL_112;
    v57 = v94 + 1;
    if ( v94 + 1 < 0x1000 )
    {
      v58 = v93[0];
      goto LABEL_111;
    }
    v58 = (void *)*((_QWORD *)v93[0] - 1);
    if ( (unsigned __int64)((char *)v93[0] - (char *)v58 - 8) <= 0x1F )
    {
      v57 = v94 + 40;
LABEL_111:
      operator delete(v58, v57);
LABEL_112:
      v59 = std::string::string(v93, Src);
      CLI::Option::add_result(v43, v59);
      if ( *((_QWORD *)&v92 + 1) > 0xFu )
      {
        if ( (unsigned __int64)(*((_QWORD *)&v92 + 1) + 1LL) < 0x1000 )
        {
          operator delete(Src[0], *((_QWORD *)&v92 + 1) + 1LL);
          return 1;
        }
        v60 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v60 - 8) <= 0x1F )
        {
          operator delete(v60, *((_QWORD *)&v92 + 1) + 40LL);
          return 1;
        }
        goto LABEL_116;
      }
      return 1;
    }
LABEL_109:
    __fastfail(5u);
  }
  v61 = (int)v42 <= (int)CLI::Option::get_items_expected_max(v86);
  option_no_throw = v86;
  if ( v61 || *((_BYTE *)v86 + 39) == 4 )
  {
LABEL_154:
    v75 = std::vector<std::string>::vector<std::string>(v88, (char *)a2 + 56);
    CLI::Option::add_result(option_no_throw, v75);
    CLI::Option::run_callback(option_no_throw);
    return 1;
  }
  if ( (int)CLI::Option::get_items_expected_max(v86) > 1 )
  {
    v78 = CLI::ConfigItem::fullname(a2, v93);
    v79 = std::vector<std::string>::size((char *)a2 + 56);
    items_expected_max = CLI::Option::get_items_expected_max(v86);
    CLI::ArgumentMismatch::AtMost(v97, v78, items_expected_max, v79);
    throw (CLI::ArgumentMismatch *)v97;
  }
  if ( !*((_BYTE *)v86 + 36) )
  {
    v81 = CLI::ConfigItem::fullname(a2, v87);
    CLI::ConversionError::TooManyInputsFlag(v98, v81);
    throw (CLI::ConversionError *)v98;
  }
  v62 = v83;
  if ( v41 == v83 )
    return 1;
  do
  {
    v63 = (_QWORD *)*((_QWORD *)option_no_throw + 11);
    v64 = (_QWORD *)*((_QWORD *)option_no_throw + 12);
    v65 = (unsigned __int64)v41[3];
    if ( v63 == v64 )
    {
      v66 = v41;
      if ( v65 > 0xF )
        v66 = *v41;
      v67 = v41[2];
      if ( v67 != (const void *)4 || memcmp_0(v66, "true", 4u) )
      {
        v68 = v41;
        if ( v65 > 0xF )
          v68 = *v41;
        if ( v67 != (const void *)5 || memcmp_0(v68, "false", 5u) )
        {
          v69 = v41;
          if ( v65 > 0xF )
            v69 = *v41;
          if ( v67 != (const void *)1 || memcmp_0(v69, "1", 1u) )
          {
            v70 = v65 <= 0xF ? v41 : (const void **)*v41;
            if ( v67 != (const void *)1 || memcmp_0(v70, "0", 1u) )
            {
LABEL_165:
              v82 = std::string::string(v87, "invalid flag argument given");
              CLI::InvalidError::InvalidError(v99, v82);
              throw (CLI::InvalidError *)v99;
            }
          }
        }
      }
    }
    else
    {
      v71 = v41[2];
      while ( 1 )
      {
        v72 = v41;
        if ( v65 > 0xF )
          v72 = *v41;
        v73 = v63[7] <= 0xFu ? v63 + 4 : (_QWORD *)v63[4];
        v74 = v63[6];
        if ( (const void *)v74 == v71 && (!v74 || !memcmp_0(v73, v72, v74)) )
          break;
        v63 += 8;
        if ( v63 == v64 )
          goto LABEL_165;
      }
    }
    v84 = (void *)std::string::string(v93, v41);
    CLI::Option::_add_result(option_no_throw, v84, (char *)option_no_throw + 568);
    *((_BYTE *)option_no_throw + 616) = 0;
    std::string::_Tidy_deallocate(v84);
    v41 += 4;
  }
  while ( v41 != v62 );
  return 1;
}

```

## disassembly

```asm
0x140023ac0  push    rbx
0x140023ac2  push    rsi
0x140023ac3  push    rdi
0x140023ac4  push    r12
0x140023ac6  push    r13
0x140023ac8  push    r14
0x140023aca  push    r15
0x140023acc  sub     rsp, 230h
0x140023ad3  mov     rax, cs:__security_cookie
0x140023ada  xor     rax, rsp
0x140023add  mov     [rsp+268h+var_48], rax
0x140023ae5  mov     rdi, r8
0x140023ae8  mov     r14, rdx
0x140023aeb  mov     rsi, rcx
0x140023aee  xor     r13d, r13d
0x140023af1  mov     rcx, [rdx]
0x140023af4  mov     rax, [rdx+8]
0x140023af8  sub     rax, rcx
0x140023afb  sar     rax, 5
0x140023aff  cmp     r8, rax
0x140023b02  jnb     short loc_140023B7E
0x140023b04  mov     rdx, r8
0x140023b07  shl     rdx, 5
0x140023b0b  add     rdx, rcx
0x140023b0e  lea     rcx, [rsp+268h+var_1B0]
0x140023b16  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140023b1b  mov     rbx, rax
0x140023b1e  mov     [rsp+268h+var_228], rax
0x140023b23  xor     r9d, r9d
0x140023b26  xor     r8d, r8d
0x140023b29  mov     rdx, rax
0x140023b2c  mov     rcx, rsi
0x140023b2f  call    ?_find_subcommand@App@CLI@@IEBAPEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N1@Z; CLI::App::_find_subcommand(std::string const &,bool,bool)
0x140023b34  mov     rsi, rax
0x140023b37  test    rax, rax
0x140023b3a  jz      loc_140024589
0x140023b40  mov     rcx, rbx; void *
0x140023b43  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140023b48  lea     r8, [rdi+1]; unsigned __int64
0x140023b4c  mov     rdx, r14; struct CLI::ConfigItem *
0x140023b4f  mov     rcx, rsi; this
0x140023b52  call    ?_parse_single_config@App@CLI@@IEAA_NAEBUConfigItem@2@_K@Z; CLI::App::_parse_single_config(CLI::ConfigItem const &,unsigned __int64)
0x140023b57  jmp     short loc_140023B5B
0x140023b59  xor     al, al
0x140023b5b  mov     rcx, [rsp+268h+var_48]
0x140023b63  xor     rcx, rsp; StackCookie
0x140023b66  call    __security_check_cookie
0x140023b6b  add     rsp, 230h
0x140023b72  pop     r15
0x140023b74  pop     r14
0x140023b76  pop     r13
0x140023b78  pop     r12
0x140023b7a  pop     rdi
0x140023b7b  pop     rsi
0x140023b7c  pop     rbx
0x140023b7d  retn
0x140023b7e  lea     rbx, [rdx+18h]
0x140023b82  mov     rcx, rbx
0x140023b85  mov     r12, [rbx+18h]
0x140023b89  cmp     r12, 0Fh
0x140023b8d  jbe     short loc_140023B92
0x140023b8f  mov     rcx, [rbx]; Buf1
0x140023b92  mov     rdi, [rbx+10h]
0x140023b96  cmp     rdi, 2
0x140023b9a  jnz     loc_140023D00
0x140023ba0  mov     r8, rdi; Size
0x140023ba3  lea     rdx, asc_14006CF78; "++"
0x140023baa  call    memcmp_0
0x140023baf  test    eax, eax
0x140023bb1  jnz     loc_140023D00
0x140023bb7  cmp     [rsi+31Eh], al
0x140023bbd  jz      loc_14002457C
0x140023bc3  mov     rcx, rsi; this
0x140023bc6  call    ?increment_parsed@App@CLI@@IEAAXXZ; CLI::App::increment_parsed(void)
0x140023bcb  mov     rdx, rdi; unsigned __int64
0x140023bce  mov     rcx, rsi; this
0x140023bd1  call    ?_trigger_pre_parse@App@CLI@@IEAAX_K@Z; CLI::App::_trigger_pre_parse(unsigned __int64)
0x140023bd6  mov     rbx, [rsi+348h]
0x140023bdd  test    rbx, rbx
0x140023be0  jz      loc_14002457C
0x140023be6  add     rbx, 2A8h
0x140023bed  mov     r14, [rbx+8]
0x140023bf1  mov     rcx, [rbx+10h]
0x140023bf5  cmp     r14, rcx
0x140023bf8  jz      short loc_140023C09
0x140023bfa  mov     [r14], rsi
0x140023bfd  add     qword ptr [rbx+8], 8
0x140023c02  mov     al, 1
0x140023c04  jmp     loc_140023B5B
0x140023c09  mov     rax, [rbx]
0x140023c0c  mov     r15, r14
0x140023c0f  sub     r15, rax
0x140023c12  sar     r15, 3
0x140023c16  mov     r8, 1FFFFFFFFFFFFFFFh
0x140023c20  cmp     r15, r8
0x140023c23  jz      loc_1400245BB
0x140023c29  sub     rcx, rax
0x140023c2c  sar     rcx, 3
0x140023c30  mov     rdx, rcx
0x140023c33  shr     rdx, 1
0x140023c36  mov     rax, r8
0x140023c39  sub     rax, rdx
0x140023c3c  cmp     rcx, rax
0x140023c3f  ja      loc_1400245C1
0x140023c45  lea     r13, [r15+1]
0x140023c49  lea     rax, [rcx+rdx]
0x140023c4d  mov     r12, r13
0x140023c50  cmp     rax, r13
0x140023c53  cmovnb  r12, rax
0x140023c57  cmp     r12, r8
0x140023c5a  ja      loc_1400245C1
0x140023c60  lea     rcx, ds:0[r12*8]; Size
0x140023c68  test    rcx, rcx
0x140023c6b  jnz     short loc_140023C71
0x140023c6d  xor     edi, edi
0x140023c6f  jmp     short loc_140023CAE
0x140023c71  cmp     rcx, 1000h
0x140023c78  jb      short loc_140023CA6
0x140023c7a  lea     rax, [rcx+27h]
0x140023c7e  cmp     rax, rcx
0x140023c81  jbe     loc_1400245C1
0x140023c87  mov     rcx, rax; Size
0x140023c8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140023c8f  test    rax, rax
0x140023c92  jz      loc_14002438E
0x140023c98  lea     rdi, [rax+27h]
0x140023c9c  and     rdi, 0FFFFFFFFFFFFFFE0h
0x140023ca0  mov     [rdi-8], rax
0x140023ca4  jmp     short loc_140023CAE
0x140023ca6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140023cab  mov     rdi, rax
0x140023cae  mov     [rdi+r15*8], rsi
0x140023cb2  mov     r8, [rbx+8]
0x140023cb6  mov     rdx, [rbx]; Src
0x140023cb9  mov     rcx, rdi; void *
0x140023cbc  cmp     r14, r8
0x140023cbf  jnz     short loc_140023CC6
0x140023cc1  sub     r8, rdx
0x140023cc4  jmp     short loc_140023CE3
0x140023cc6  mov     r8, r14
0x140023cc9  sub     r8, rdx; Size
0x140023ccc  call    memmove_0
0x140023cd1  mov     r8, [rbx+8]
0x140023cd5  sub     r8, r14; Size
0x140023cd8  lea     rcx, [r15+1]
0x140023cdc  lea     rcx, [rdi+rcx*8]; void *
0x140023ce0  mov     rdx, r14; Src
0x140023ce3  call    memmove_0
0x140023ce8  mov     r9, r12
0x140023ceb  mov     r8, r13
0x140023cee  mov     rdx, rdi
0x140023cf1  mov     rcx, rbx
0x140023cf4  call    ?_Change_array@?$vector@PEAVApp@CLI@@V?$allocator@PEAVApp@CLI@@@std@@@std@@AEAAXQEAPEAVApp@CLI@@_K1@Z; std::vector<CLI::App *>::_Change_array(CLI::App * * const,unsigned __int64,unsigned __int64)
0x140023cf9  mov     al, 1
0x140023cfb  jmp     loc_140023B5B
0x140023d00  mov     rcx, rbx
0x140023d03  cmp     r12, 0Fh
0x140023d07  jbe     short loc_140023D0C
0x140023d09  mov     rcx, [rbx]; Buf1
0x140023d0c  cmp     rdi, 2
0x140023d10  jnz     short loc_140023D63
0x140023d12  mov     r8, rdi; Size
0x140023d15  lea     rdx, asc_14006CCD4; "--"
0x140023d1c  call    memcmp_0
0x140023d21  test    eax, eax
0x140023d23  jnz     short loc_140023D63
0x140023d25  cmp     [rsi+31Eh], al
0x140023d2b  jz      loc_14002457C
0x140023d31  cmp     qword ptr [rsi+0C8h], 0
0x140023d39  jz      loc_14002457C
0x140023d3f  mov     rcx, rsi; this
0x140023d42  call    ?_process_callbacks@App@CLI@@IEAAXXZ; CLI::App::_process_callbacks(void)
0x140023d47  mov     rcx, rsi; this
0x140023d4a  call    ?_process_requirements@App@CLI@@IEAAXXZ; CLI::App::_process_requirements(void)
0x140023d4f  xor     r8d, r8d; bool
0x140023d52  xor     edx, edx; bool
0x140023d54  mov     rcx, rsi; this
0x140023d57  call    ?run_callback@App@CLI@@IEAAX_N0@Z; CLI::App::run_callback(bool,bool)
0x140023d5c  mov     al, 1
0x140023d5e  jmp     loc_140023B5B
0x140023d63  mov     r15, 7FFFFFFFFFFFFFFFh
0x140023d6d  mov     rax, r15
0x140023d70  sub     rax, rdi
0x140023d73  cmp     rax, 2
0x140023d77  jb      loc_140024583
0x140023d7d  mov     rax, rbx
0x140023d80  cmp     r12, 0Fh
0x140023d84  jbe     short loc_140023D89
0x140023d86  mov     rax, [rbx]
0x140023d89  mov     [rsp+268h+var_238], rdi
0x140023d8e  mov     [rsp+268h+var_240], rax
0x140023d93  mov     [rsp+268h+var_248], 2
0x140023d9c  lea     r9, asc_14006CCD4; "--"
0x140023da3  mov     r8, rbx
0x140023da6  movzx   edx, [rsp+268h+var_220]
0x140023dab  lea     rcx, [rsp+268h+var_1F0]
0x140023db0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x140023db5  lea     rdx, [rsp+268h+var_1F0]
0x140023dba  mov     rcx, rsi
0x140023dbd  call    ?get_option_no_throw@App@CLI@@QEAAPEAVOption@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::App::get_option_no_throw(std::string)
0x140023dc2  mov     r12, rax
0x140023dc5  mov     [rsp+268h+var_218], rax
0x140023dca  test    rax, rax
0x140023dcd  jnz     loc_140023F90
0x140023dd3  cmp     qword ptr [r14+28h], 1
0x140023dd8  jnz     short loc_140023E47
0x140023dda  mov     rcx, [rbx+10h]
0x140023dde  mov     rax, r15
0x140023de1  sub     rax, rcx
0x140023de4  cmp     rax, 1
0x140023de8  jb      loc_140024583
0x140023dee  cmp     qword ptr [rbx+18h], 0Fh
0x140023df3  jbe     short loc_140023DFA
0x140023df5  mov     rax, [rbx]
0x140023df8  jmp     short loc_140023DFD
0x140023dfa  mov     rax, rbx
0x140023dfd  mov     [rsp+268h+var_238], rcx
0x140023e02  mov     [rsp+268h+var_240], rax
0x140023e07  mov     [rsp+268h+var_248], 1
0x140023e10  lea     r9, asc_14006E5AC; "-"
0x140023e17  mov     r8, rbx
0x140023e1a  movzx   edx, [rsp+268h+var_220]
0x140023e1f  lea     rcx, [rsp+268h+var_1F0]
0x140023e24  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x140023e29  lea     rdx, [rsp+268h+var_1F0]
0x140023e2e  mov     rcx, rsi
0x140023e31  call    ?get_option_no_throw@App@CLI@@QEAAPEAVOption@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::App::get_option_no_throw(std::string)
0x140023e36  mov     r12, rax
0x140023e39  mov     [rsp+268h+var_218], rax
0x140023e3e  test    rax, rax
0x140023e41  jnz     loc_140023F90
0x140023e47  mov     rdx, rbx
0x140023e4a  lea     rcx, [rsp+268h+var_210]
0x140023e4f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140023e54  mov     rdx, rax
0x140023e57  mov     rcx, rsi
0x140023e5a  call    ?get_option_no_throw@App@CLI@@QEAAPEAVOption@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::App::get_option_no_throw(std::string)
0x140023e5f  mov     r12, rax
0x140023e62  mov     [rsp+268h+var_218], rax
0x140023e67  test    rax, rax
0x140023e6a  jnz     loc_140023F90
0x140023e70  cmp     byte ptr [rsi+49h], 3
0x140023e74  jnz     loc_140023F25
0x140023e7a  mov     dword ptr [rsp+268h+var_218], r13d
0x140023e7f  lea     rdx, [rsp+268h+var_1F0]
0x140023e84  mov     rcx, r14
0x140023e87  call    ?fullname@ConfigItem@CLI@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CLI::ConfigItem::fullname(void)
0x140023e8c  nop
0x140023e8d  lea     rcx, [rsi+278h]
0x140023e94  mov     rdx, [rcx+8]
0x140023e98  cmp     rdx, [rcx+10h]
0x140023e9c  jz      short loc_140023ED5
0x140023e9e  mov     [rdx], r13d
0x140023ea1  xorps   xmm0, xmm0
0x140023ea4  movups  xmmword ptr [rdx+8], xmm0
0x140023ea8  mov     [rdx+18h], r13
0x140023eac  mov     [rdx+20h], r13
0x140023eb0  movups  xmm0, xmmword ptr [rax]
0x140023eb3  movups  xmmword ptr [rdx+8], xmm0
0x140023eb7  movups  xmm1, xmmword ptr [rax+10h]
0x140023ebb  movups  xmmword ptr [rdx+18h], xmm1
0x140023ebf  mov     [rax+10h], r13
0x140023ec3  mov     qword ptr [rax+18h], 0Fh
0x140023ecb  mov     [rax], r12b
0x140023ece  add     qword ptr [rcx+8], 28h ; '('
0x140023ed3  jmp     short loc_140023EE3
0x140023ed5  mov     r9, rax
0x140023ed8  lea     r8, [rsp+268h+var_218]
0x140023edd  call    ??$_Emplace_reallocate@W4Classifier@detail@CLI@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@U?$pair@W4Classifier@detail@CLI@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@V?$allocator@U?$pair@W4Classifier@detail@CLI@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@2@@std@@AEAAPEAU?$pair@W4Classifier@detail@CLI@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@QEAU21@$$QEAW4Classifier@detail@CLI@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::vector<std::pair<CLI::detail::Classifier,std::string>>::_Emplace_reallocate<CLI::detail::Classifier,std::string>(std::pair<CLI::detail::Classifier,std::string> * const,CLI::detail::Classifier &&,std::string &&)
0x140023ee2  nop
0x140023ee3  mov     rdx, [rsp+268h+var_1D8]
0x140023eeb  cmp     rdx, 0Fh
0x140023eef  jbe     short loc_140023F25
0x140023ef1  mov     rax, [rsp+268h+var_1F0]
0x140023ef6  inc     rdx; unsigned __int64
0x140023ef9  cmp     rdx, 1000h
0x140023f00  jb      short loc_140023F1D
0x140023f02  mov     rcx, [rax-8]
0x140023f06  sub     rax, rcx
0x140023f09  sub     rax, 8
0x140023f0d  cmp     rax, 1Fh
0x140023f11  ja      loc_14002438E
0x140023f17  add     rdx, 27h ; '''
0x140023f1b  jmp     short loc_140023F20
0x140023f1d  mov     rcx, rax; void *
0x140023f20  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140023f25  mov     r15, [r14+40h]
0x140023f29  mov     rbx, [r14+38h]
0x140023f2d  cmp     rbx, r15
0x140023f30  jz      loc_140023B59
0x140023f36  nop     word ptr [rax+rax+00000000h]
0x140023f40  mov     dword ptr [rsp+268h+var_218], r13d
0x140023f45  mov     rdx, [rsi+280h]
0x140023f4c  cmp     rdx, [rsi+288h]
0x140023f53  jz      short loc_140023F6E
0x140023f55  mov     [rdx], r13d
0x140023f58  lea     rcx, [rdx+8]
0x140023f5c  mov     rdx, rbx
0x140023f5f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140023f64  add     qword ptr [rsi+280h], 28h ; '('
  ... truncated ...
```
