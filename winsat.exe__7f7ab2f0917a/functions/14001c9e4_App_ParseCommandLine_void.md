# App::ParseCommandLine(void)

- ea: `0x14001c9e4`
- end: `0x14001d98f`
- name: `?ParseCommandLine@App@@SAKXZ`
- size: `4011`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a54c`

## callees

- `0x140004170`
- `0x140005d78`
- `0x140005f10`
- `0x140005f4c`
- `0x1400085b4`
- `0x14000a8d8`
- `0x14000d35c`
- `0x14000e17c`
- `0x140016480`
- `0x140016954`
- `0x140016d04`
- `0x140017af0`
- `0x140018318`
- `0x14001854c`
- `0x140018920`
- `0x14001942c`
- `0x140019bd8`
- `0x140019e1c`
- `0x14001c02c`
- `0x14001c0b4`
- `0x14001c698`
- `0x14001c9e4`
- `0x14001d9d4`
- `0x14001da6c`
- `0x14001dc0c`
- `0x14001dd60`
- `0x14001ddf4`
- `0x14001def8`
- `0x14003f8e0`
- `0x14003fa8c`
- `0x14004eb34`
- `0x14004ebe8`
- `0x14004fce4`
- `0x14004fe00`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x14001d269`
- `KERNEL32!OpenEventW` at `0x14001d377`
- `KERNEL32!OpenEventW` at `0x14001d269`
- `KERNEL32!OpenEventW` at `0x14001d377`
- `KERNEL32!GetLastError` at `0x14001d27b`
- `KERNEL32!GetLastError` at `0x14001d2a5`
- `KERNEL32!GetLastError` at `0x14001d27b`
- `KERNEL32!GetLastError` at `0x14001d2a5`
- `KERNEL32!SetLastError` at `0x14001d29f`
- `KERNEL32!SetLastError` at `0x14001d29f`

## string_xrefs

- `0x14001cd90`: `no file name after the -txml switch`

## pseudocode

```c
__int64 App::ParseCommandLine(void)
{
  __int64 v0; // rax
  __int64 v1; // rcx
  _QWORD *v2; // rax
  __int64 v3; // rcx
  unsigned __int16 v4; // r9
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned __int16 v7; // r9
  __int64 v8; // rax
  unsigned __int16 v9; // r9
  _QWORD **v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rax
  bool v14; // al
  _QWORD *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // r9
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // r9
  _QWORD *next_cl_token; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r9
  __int64 v34; // rax
  __int64 v35; // r9
  __int64 v36; // rax
  __int64 v37; // r9
  _QWORD *v38; // rax
  unsigned __int16 v39; // r9
  _QWORD *v40; // rbx
  unsigned int v41; // ebx
  int v42; // r8d
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // r9
  _QWORD *v48; // rax
  _QWORD *v49; // rax
  _QWORD *v50; // rbx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // r9
  __int64 v54; // rax
  __int64 v55; // r9
  _QWORD *v56; // rax
  _QWORD *v57; // rbx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // r9
  __int64 v61; // rax
  __int64 v62; // r9
  _QWORD *v63; // rax
  _QWORD *v64; // rbx
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // r9
  __int64 v68; // rax
  __int64 v69; // r9
  _QWORD *v70; // rax
  _QWORD *v71; // rbx
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // r9
  __int64 v75; // rax
  __int64 v76; // r9
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // r9
  __int64 v81; // rax
  __int64 v82; // r9
  _QWORD *v83; // rax
  unsigned __int16 v84; // r9
  double *v85; // rcx
  DWORD LastError; // edi
  unsigned __int16 v87; // r9
  __int64 v88; // rax
  __int64 v89; // r9
  __int64 v90; // rax
  __int64 v91; // r9
  _QWORD *v92; // rax
  unsigned __int16 v93; // r9
  unsigned int v94; // ebx
  int v95; // r8d
  __int64 v96; // rax
  __int64 v97; // r9
  __int64 v98; // rax
  __int64 v99; // r9
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // r9
  __int64 v103; // rax
  __int64 v104; // r9
  __int64 v105; // rax
  __int64 v106; // r9
  __int64 v107; // rax
  __int64 v108; // r9
  __int64 v109; // rax
  __int64 v110; // r9
  unsigned __int16 v111; // r9
  __int64 v112; // rax
  __int64 v113; // r9
  unsigned __int64 **v114; // rax
  unsigned __int64 v115; // rbx
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // r9
  unsigned __int16 v119; // r9
  __int64 v120; // rax
  __int64 v121; // r9
  unsigned __int64 **v122; // rax
  unsigned __int64 v123; // rbx
  __int64 v124; // rax
  __int64 v125; // r9
  unsigned __int16 v126; // r9
  __int64 v127; // rax
  __int64 v128; // r9
  unsigned __int64 **v129; // rax
  unsigned __int64 v130; // rbx
  __int64 v131; // rax
  __int64 v132; // r9
  unsigned __int16 v133; // r9
  __int64 v134; // rax
  __int64 v135; // r9
  __int64 v136; // rax
  __int64 v137; // r9
  __int64 v138; // rcx
  __int64 v139; // rcx
  __int64 v140; // rax
  __int64 v141; // r9
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // r9
  char v145; // [rsp+20h] [rbp-30h]
  _QWORD *v146; // [rsp+80h] [rbp+30h] BYREF
  double v147; // [rsp+88h] [rbp+38h] BYREF
  _QWORD *v148; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int64 v149; // [rsp+98h] [rbp+48h] BYREF

  v0 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::GetCommandLineW(v0);
  LODWORD(v147) = 0;
  LOBYTE(v146) = 0;
  if ( !(unsigned int)RegHelper::ReadDWORDValue(v1, L"SaveETLFiles", &v147, &v146) && !(_BYTE)v146 )
  {
    if ( LODWORD(v147) )
    {
      App::s_SaveETLFiles = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v146,
        L"%windir%\\performance\\winsat\\");
      v2 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::ExpandEnvStrings(
                       &v146,
                       &v147);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v146,
        *v2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
      App::AddSwitchWordIfNotPresent(qword_1401C6310, L"admp", v146[3]);
      RegHelper::WriteDWORDValue(v3, L"SaveETLFiles");
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
    }
    else
    {
      App::s_SaveETLFiles = 0;
    }
  }
  if ( !**(_QWORD **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine)
    || (v5 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine),
        (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_all_white_space(v5)) )
  {
    mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0xD2, 10171, v4);
    Record_InternalError_w("base\\winsat\\exe\\app.cpp");
    return 87;
  }
  v6 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
  if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::are_quotes_ballanced(
                          v6,
                          34) )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v146,
      260);
    v8 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::remove_first_cl_token(
                             v8,
                             &v146) )
    {
      mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0xE1, 10001, v9);
      Record_InternalError_w("base\\winsat\\exe\\app.cpp");
      v10 = &v146;
LABEL_12:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v10);
      return 87;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
    v11 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v12) = 1;
    App::s_Help = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                    v11,
                    L"help",
                    &v146,
                    v12);
    v13 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch(
                            v13,
                            63,
                            &v146)
      || (v14 = 0, App::s_Help) )
    {
      v14 = 1;
    }
    App::s_Help = v14;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v147,
      qword_1401C6310 != 0);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v146);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::remove_first_cl_token(
      &v147,
      &v146);
    v145 = mlib::m_traits<unsigned short>::CStrlen(L"help", 0x10000);
    v15 = v146;
    if ( !(unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
                          &v146,
                          v16,
                          *v146,
                          L"help")
      || (v145 = mlib::m_traits<unsigned short>::CStrlen(L"?", 0x10000),
          !(unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
                           &v146,
                           v17,
                           *v15,
                           L"?")) )
    {
      App::s_Help = 1;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
    v18 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v19) = 1;
    App::s_Verbose = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                       v18,
                       L"v",
                       &v146,
                       v19);
    v20 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v21) = 1;
    App::s_VVerbose = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                        v20,
                        L"vv",
                        &v146,
                        v21);
    if ( App::s_VVerbose )
      App::s_Verbose = 1;
    if ( App::s_Help )
      return 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v148);
    v149 = 0;
    v23 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v24) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v23,
                            L"txml",
                            &v149,
                            v24) )
    {
      v25 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_xmlTestFile);
      v26 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v27) = 1;
      next_cl_token = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
                                  v26,
                                  &v146,
                                  v149,
                                  v27);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        v25,
        *next_cl_token);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      v29 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_xmlTestFile);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(v29);
      if ( !**(_QWORD **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_xmlTestFile) )
        goto LABEL_25;
    }
    v30 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v30,
                            L"log",
                            &v149,
                            0) )
    {
      v31 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_tokenq(
        v31,
        &v146,
        v149);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v148,
        v146);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_cl_switch(&v148) )
      {
        v32 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
        LOBYTE(v33) = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
          v32,
          &v146,
          v149,
          v33);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      }
    }
    v34 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v35) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v34,
                            L"xml",
                            &v149,
                            v35) )
    {
      v36 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v37) = 1;
      v38 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
                        v36,
                        &v146,
                        v149,
                        v37);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v148,
        *v38);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v148);
      v40 = v148;
      if ( !*v148 )
      {
        v41 = 342;
        v42 = 10009;
LABEL_33:
        mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)v41, v42, v39);
LABEL_25:
        Record_InternalError_w("base\\winsat\\exe\\app.cpp");
LABEL_26:
        v10 = &v148;
        goto LABEL_12;
      }
      v43 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_XMLOutputFileName);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        v43,
        v40);
    }
    v44 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v45) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v44,
                            L"admp",
                            &v149,
                            v45) )
    {
      v46 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v47) = 1;
      v48 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
                        v46,
                        &v146,
                        v149,
                        v47);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v148,
        *v48);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v148);
      v49 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::ExpandEnvStrings(
                        &v148,
                        &v146);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v148,
        *v49);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      v50 = v148;
      if ( !*v148 )
      {
        v41 = 366;
        v42 = 10040;
        goto LABEL_33;
      }
      v51 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_AssessmentDumpFileName);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        v51,
        v50);
    }
    v52 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v53) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v52,
                            L"datastore",
                            &v149,
                            v53) )
    {
      v54 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v55) = 1;
      v56 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
                        v54,
                        &v146,
                        v149,
                        v55);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v148,
        *v56);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v148);
      v57 = v148;
      if ( !*v148 )
      {
        v41 = 386;
        v42 = 10168;
        goto LABEL_33;
      }
      v58 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(App::s_AssessmentDatastoreDirName);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        v58,
        v57);
    }
    v59 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v60) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v59,
                            L"note",
                            &v149,
                            v60) )
    {
      v61 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v62) = 1;
      v63 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
                        v61,
                        &v146,
                        v149,
                        v62);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v148,
        *v63);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v148);
      v64 = v148;
      if ( *v148 )
      {
        v65 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(App::s_Note);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
          v65,
          v64);
      }
    }
    if ( App::s_IsPrivateBld )
    {
      v66 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v67) = 1;
      if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                              v66,
                              L"cpuff",
                              &v149,
                              v67) )
      {
        v68 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
        LOBYTE(v69) = 1;
        v70 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
                          v68,
                          &v146,
                          v149,
                          v69);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
          &v148,
          *v70);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v148);
        v71 = v148;
        if ( !*v148 )
          goto LABEL_25;
        v72 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CpuScoreFactorsFile);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
          v72,
          v71);
      }
      if ( App::s_IsPrivateBld )
      {
        v73 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
        v146 = 0;
        LOBYTE(v74) = 1;
        App::s_SkipSchemaChk = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                                 v73,
                                 L"ssc",
                                 &v146,
                                 v74);
        if ( App::s_SkipSchemaChk
          || (v75 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_ExEnv),
              v146 = 0,
              LOBYTE(v76) = 1,
              App::s_SkipSchemaChk = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                                       v75,
                                       L"ssc",
                                       &v146,
                                       v76)) )
        {
          v77 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
          v78 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                  v77 + 240,
                  "-- Skipping Schema check! (private only)");
          std::endl(v78);
        }
      }
    }
    v79 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v80) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v79,
                            L"cancelevent",
                            &v149,
                            v80) )
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v146);
      v81 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v82) = 1;
      v83 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
                        v81,
                        &v147,
                        v149,
                        v82);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v146,
        *v83);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v146);
      if ( !*v146 )
      {
        mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0x1C8, 10174, v84);
        Record_InternalError_w("base\\winsat\\exe\\app.cpp");
LABEL_57:
        v85 = (double *)&v146;
LABEL_58:
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v85);
        goto LABEL_26;
      }
      App::s_CanceLEventHandle = OpenEventW(0x1F0003u, 0, (LPCWSTR)v146[3]);
      if ( !App::s_CanceLEventHandle )
      {
        LastError = GetLastError();
        mlib::MUISpf_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0x1D2, 10057, v87);
        SetLastError(LastError);
        GetLastError();
        Record_Win32Error_w("base\\winsat\\exe\\app.cpp", v145);
        goto LABEL_57;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
    }
    v88 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v89) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v88,
                            L"moobegoevent",
                            &v149,
                            v89) )
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v146);
      v90 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v91) = 1;
      v92 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
                        v90,
                        &v147,
                        v149,
                        v91);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v146,
        *v92);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v146);
      if ( !*v146 )
      {
        v94 = 486;
        v95 = 10175;
LABEL_65:
        mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)v94, v95, v93);
        Record_InternalError_w("base\\winsat\\exe\\app.cpp");
        goto LABEL_57;
      }
      App::s_MoobeGoeventhandle = OpenEventW(0x1F0003u, 0, (LPCWSTR)v146[3]);
      if ( !App::s_MoobeGoeventhandle )
      {
        v94 = 493;
        v95 = 10127;
        goto LABEL_65;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
    }
    v96 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v97) = 1;
    App::s_keepDWMRnning = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                             v96,
                             L"kdr",
                             &v146,
                             v97);
    v98 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v99) = 1;
    App::s_includeGUID = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                           v98,
                           L"iguid",
                           &v146,
                           v99);
    if ( App::s_includeGUID )
    {
      v100 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(App::s_GUID);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::UuidCreate(v100);
    }
    v101 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v102) = 1;
    App::s_DumpComputerName = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                                v101,
                                L"icn",
                                &v146,
                                v102);
    v103 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v104) = 1;
    App::s_AllowFormalOnBatt = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                                 v103,
                                 L"fonbat",
                                 &v146,
                                 v104);
    v105 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v106) = 1;
    App::s_RequireBatt = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                           v105,
                           L"requirebatt",
                           &v146,
                           v106);
    v107 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v108) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v107,
                            L"iter",
                            &v149,
                            v108) )
    {
      v109 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v110) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
        v109,
        &v147,
        v149,
        v110);
      LODWORD(v146) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::to_UINT(
        &v147,
        &v146,
        0);
      App::s_Iteration = (unsigned int)v146;
      if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::IsPositiveInteger(&v147)
        || !App::s_Iteration )
      {
        mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0x21A, 10039, v111);
        Record_InternalError_w("base\\winsat\\exe\\app.cpp");
        v85 = &v147;
        goto LABEL_58;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
    }
    v112 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v113) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v112,
                            L"watchdog",
                            &v149,
                            v113) )
    {
      App::s_WatchDogEnabled = 1;
      v114 = (unsigned __int64 **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      v115 = v149;
      if ( v149 < **v114 )
      {
        v116 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
          v116,
          &v146,
          v115,
          0);
        if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_cl_switch(&v146) )
        {
          v117 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
          LOBYTE(v118) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
            v117,
            &v147,
            v115,
            v118);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
          v147 = 0.0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::to_double(
            &v146,
            &v147);
          App::s_ClWatchDogTimeout = v147;
          if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::IsPositiveNumber(&v146)
            || App::s_ClWatchDogTimeout < 0.1 )
          {
            App::s_ClWatchDogTimeout = 0.0;
            App::s_WatchDogEnabled = 0;
            mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0x23B, 10184, v119);
            Record_InternalError_w("base\\winsat\\exe\\app.cpp");
            goto LABEL_57;
          }
        }
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
      }
    }
    v120 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v121) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v120,
                            L"xwait",
                            &v149,
                            v121) )
    {
      v122 = (unsigned __int64 **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      v123 = v149;
      if ( v149 >= **v122 )
      {
        App::s_CancelWaitTimeS = 0.0;
        v41 = 604;
        v42 = 10205;
        goto LABEL_33;
      }
      v124 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v125) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
        v124,
        &v146,
        v123,
        v125);
      v147 = 0.0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::to_double(
        &v146,
        &v147);
      App::s_CancelWaitTimeS = v147;
      if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_cl_switch(&v146)
        && (!(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::IsPositiveNumber(&v146)
         || App::s_CancelWaitTimeS < 1.0) )
      {
        App::s_CancelWaitTimeS = 0.0;
        mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0x256, 10205, v126);
        Record_InternalError_w("base\\winsat\\exe\\app.cpp");
        goto LABEL_57;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
    }
    v127 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v128) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            v127,
                            L"xwdfinal",
                            &v149,
                            v128) )
    {
      v129 = (unsigned __int64 **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      v130 = v149;
      if ( v149 >= **v129 )
      {
        App::s_FinalWatchDogTimeS = 0.0;
        v41 = 635;
        v42 = 10206;
        goto LABEL_33;
      }
      v131 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
      LOBYTE(v132) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::get_next_cl_token(
        v131,
        &v146,
        v130,
        v132);
      v147 = 0.0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::to_double(
        &v146,
        &v147);
      App::s_FinalWatchDogTimeS = v147;
      if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_cl_switch(&v146)
        && (!(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::IsPositiveNumber(&v146)
         || App::s_FinalWatchDogTimeS < 1.0) )
      {
        App::s_FinalWatchDogTimeS = 0.0;
        mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0x275, 10206, v133);
        Record_InternalError_w("base\\winsat\\exe\\app.cpp");
        goto LABEL_57;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
    }
    v134 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v135) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
      v134,
      L"glpi",
      &v149,
      v135);
    v136 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v137) = 1;
    App::s_SuppressWatchDog = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                                v136,
                                L"suppresswd",
                                &v149,
                                v137);
    if ( !App::s_SuppressWatchDog )
    {
      LODWORD(v147) = 0;
      LOBYTE(v146) = 1;
      if ( !(unsigned int)RegHelper::ReadDWORDValue(v138, L"SuppressWatchDogTimer", &v147, &v146) && !(_BYTE)v146 )
      {
        if ( LODWORD(v147) )
        {
          App::s_SuppressWatchDog = 1;
          RegHelper::WriteDWORDValue(v139, L"SuppressWatchDogTimer");
        }
        else
        {
          App::s_SuppressWatchDog = 0;
        }
      }
    }
    v140 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    LOBYTE(v141) = 1;
    App::s_AllowUnsupported = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                                v140,
                                L"unsupported",
                                &v149,
                                v141);
    v142 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    App::s_WsSwapTest = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                          v142,
                          L"wsswap",
                          &v146,
                          0);
    v143 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_CommandLine);
    v146 = 0;
    LOBYTE(v144) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
      v143,
      L"log",
      &v146,
      v144);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v148);
    return 0;
  }
  mlib::MUIStr_((mlib *)"base\\winsat\\exe\\app.cpp", (const char *)0xD7, 10170, v7);
  Record_InternalError_w("base\\winsat\\exe\\app.cpp");
  return 87;
}

```

## disassembly

```asm
0x14001c9e4  push    rbp
0x14001c9e6  push    rbx
0x14001c9e7  push    rsi
0x14001c9e8  push    rdi
0x14001c9e9  push    r14
0x14001c9eb  mov     rbp, rsp
0x14001c9ee  sub     rsp, 50h
0x14001c9f2  movaps  [rsp+50h+var_10], xmm6
0x14001c9f7  movaps  [rsp+50h+var_20], xmm7
0x14001c9fc  xor     esi, esi
0x14001c9fe  lea     r14, ?s_CommandLine@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_CommandLine
0x14001ca05  mov     rcx, r14
0x14001ca08  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001ca0d  mov     rcx, rax
0x14001ca10  call    ?GetCommandLineW@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::GetCommandLineW(void)
0x14001ca15  mov     dword ptr [rbp+arg_8], esi
0x14001ca18  mov     byte ptr [rbp+arg_0], sil
0x14001ca1c  lea     r9, [rbp+arg_0]
0x14001ca20  lea     r8, [rbp+arg_8]
0x14001ca24  lea     rdx, aSaveetlfiles; "SaveETLFiles"
0x14001ca2b  call    ?ReadDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAKPEA_N@Z; RegHelper::ReadDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &,bool *)
0x14001ca30  test    eax, eax
0x14001ca32  jnz     short loc_14001CAB3
0x14001ca34  cmp     byte ptr [rbp+arg_0], sil
0x14001ca38  jnz     short loc_14001CAB3
0x14001ca3a  cmp     dword ptr [rbp+arg_8], esi
0x14001ca3d  jz      short loc_14001CAAC
0x14001ca3f  mov     cs:?s_SaveETLFiles@App@@2_NA, 1; bool App::s_SaveETLFiles
0x14001ca46  lea     rdx, aWindirPerforma; "%windir%\\performance\\winsat\\"
0x14001ca4d  lea     rcx, [rbp+arg_0]
0x14001ca51  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14001ca56  nop
0x14001ca57  lea     rdx, [rbp+arg_8]
0x14001ca5b  lea     rcx, [rbp+arg_0]
0x14001ca5f  call    ?ExpandEnvStrings@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::ExpandEnvStrings(void)
0x14001ca64  mov     rdx, [rax]
0x14001ca67  lea     rcx, [rbp+arg_0]
0x14001ca6b  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14001ca70  lea     rcx, [rbp+arg_8]
0x14001ca74  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001ca79  mov     r8, [rbp+arg_0]
0x14001ca7d  mov     r8, [r8+18h]
0x14001ca81  lea     rdx, aAdmp; "admp"
0x14001ca88  mov     rcx, cs:qword_1401C6310
0x14001ca8f  call    ?AddSwitchWordIfNotPresent@App@@SA_NAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@PEBG1@Z; App::AddSwitchWordIfNotPresent(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,ushort const *,ushort const *)
0x14001ca94  lea     rdx, aSaveetlfiles; "SaveETLFiles"
0x14001ca9b  call    ?WriteDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGK@Z; RegHelper::WriteDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong)
0x14001caa0  nop
0x14001caa1  lea     rcx, [rbp+arg_0]
0x14001caa5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001caaa  jmp     short loc_14001CAB3
0x14001caac  mov     cs:?s_SaveETLFiles@App@@2_NA, sil; bool App::s_SaveETLFiles
0x14001cab3  mov     rcx, r14
0x14001cab6  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cabb  mov     rcx, [rax]
0x14001cabe  cmp     [rcx], rsi
0x14001cac1  jz      loc_14001D94B
0x14001cac7  mov     rcx, r14
0x14001caca  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cacf  mov     rcx, rax
0x14001cad2  call    ?is_all_white_space@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_all_white_space(void)
0x14001cad7  test    al, al
0x14001cad9  jnz     loc_14001D94B
0x14001cadf  mov     rcx, r14
0x14001cae2  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cae7  mov     edx, 22h ; '"'
0x14001caec  mov     rcx, rax
0x14001caef  call    ?are_quotes_ballanced@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::are_quotes_ballanced(ushort)
0x14001caf4  test    al, al
0x14001caf6  jnz     short loc_14001CB2A
0x14001caf8  mov     ebx, 0D7h
0x14001cafd  mov     r8d, 27BAh; int
0x14001cb03  mov     edx, ebx; char *
0x14001cb05  lea     rcx, aBaseWinsatExeA; "base\\winsat\\exe\\app.cpp"
0x14001cb0c  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14001cb11  mov     r8, rax
0x14001cb14  xor     r9d, r9d
0x14001cb17  mov     edx, ebx
0x14001cb19  lea     rcx, aBaseWinsatExeA; "base\\winsat\\exe\\app.cpp"
0x14001cb20  call    Record_InternalError_w
0x14001cb25  jmp     loc_14001D975
0x14001cb2a  mov     edx, 104h
0x14001cb2f  lea     rcx, [rbp+arg_0]
0x14001cb33  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x14001cb38  nop
0x14001cb39  mov     rcx, r14
0x14001cb3c  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cb41  lea     rdx, [rbp+arg_0]
0x14001cb45  mov     rcx, rax
0x14001cb48  call    ?remove_first_cl_token@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NAEAV12@_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::remove_first_cl_token(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,bool)
0x14001cb4d  test    al, al
0x14001cb4f  jnz     short loc_14001CB8A
0x14001cb51  mov     ebx, 0E1h
0x14001cb56  mov     r8d, 2711h; int
0x14001cb5c  mov     edx, ebx; char *
0x14001cb5e  lea     rcx, aBaseWinsatExeA; "base\\winsat\\exe\\app.cpp"
0x14001cb65  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14001cb6a  mov     r8, rax
0x14001cb6d  mov     edx, ebx
0x14001cb6f  lea     rcx, aBaseWinsatExeA; "base\\winsat\\exe\\app.cpp"
0x14001cb76  call    Record_InternalError_w
0x14001cb7b  nop
0x14001cb7c  lea     rcx, [rbp+arg_0]
0x14001cb80  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001cb85  jmp     loc_14001D975
0x14001cb8a  lea     rcx, [rbp+arg_0]
0x14001cb8e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001cb93  mov     rcx, r14
0x14001cb96  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cb9b  mov     [rbp+arg_0], rsi
0x14001cb9f  mov     r9b, 1
0x14001cba2  lea     r8, [rbp+arg_0]
0x14001cba6  lea     rbx, aHelp; "help"
0x14001cbad  mov     rdx, rbx
0x14001cbb0  mov     rcx, rax
0x14001cbb3  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x14001cbb8  mov     cs:?s_Help@App@@2_NA, al; bool App::s_Help
0x14001cbbe  mov     rcx, r14
0x14001cbc1  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cbc6  mov     [rbp+arg_0], rsi
0x14001cbca  mov     edx, 3Fh ; '?'
0x14001cbcf  lea     r8, [rbp+arg_0]
0x14001cbd3  mov     rcx, rax
0x14001cbd6  call    ?has_switch@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch(ushort,unsigned __int64 &,bool)
0x14001cbdb  test    al, al
0x14001cbdd  jnz     short loc_14001CBEB
0x14001cbdf  cmp     cs:?s_Help@App@@2_NA, sil; bool App::s_Help
0x14001cbe6  mov     al, sil
0x14001cbe9  jz      short loc_14001CBED
0x14001cbeb  mov     al, 1
0x14001cbed  mov     cs:?s_Help@App@@2_NA, al; bool App::s_Help
0x14001cbf3  mov     rdx, rsi
0x14001cbf6  cmp     cs:qword_1401C6310, rsi
0x14001cbfd  setnz   dl
0x14001cc00  lea     rcx, [rbp+arg_8]
0x14001cc04  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x14001cc09  nop
0x14001cc0a  lea     rcx, [rbp+arg_0]
0x14001cc0e  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x14001cc13  nop
0x14001cc14  lea     rdx, [rbp+arg_0]
0x14001cc18  lea     rcx, [rbp+arg_8]
0x14001cc1c  call    ?remove_first_cl_token@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NAEAV12@_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::remove_first_cl_token(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,bool)
0x14001cc21  mov     edi, 10000h
0x14001cc26  mov     edx, edi
0x14001cc28  mov     rcx, rbx
0x14001cc2b  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x14001cc30  mov     qword ptr [rsp+50h+var_30], rax
0x14001cc35  mov     r9, rbx
0x14001cc38  mov     rbx, [rbp+arg_0]
0x14001cc3c  mov     r8, [rbx]
0x14001cc3f  lea     rcx, [rbp+arg_0]
0x14001cc43  call    ?comparei_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBAH_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::comparei_str(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x14001cc48  test    eax, eax
0x14001cc4a  jz      short loc_14001CC76
0x14001cc4c  mov     edx, edi
0x14001cc4e  lea     rcx, asc_14012F46C; "?"
0x14001cc55  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x14001cc5a  mov     qword ptr [rsp+50h+var_30], rax; char
0x14001cc5f  lea     r9, asc_14012F46C; "?"
0x14001cc66  mov     r8, [rbx]
0x14001cc69  lea     rcx, [rbp+arg_0]
0x14001cc6d  call    ?comparei_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBAH_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::comparei_str(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x14001cc72  test    eax, eax
0x14001cc74  jnz     short loc_14001CC7D
0x14001cc76  mov     cs:?s_Help@App@@2_NA, 1; bool App::s_Help
0x14001cc7d  lea     rcx, [rbp+arg_0]
0x14001cc81  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001cc86  nop
0x14001cc87  lea     rcx, [rbp+arg_8]
0x14001cc8b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001cc90  mov     rcx, r14
0x14001cc93  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cc98  mov     [rbp+arg_0], rsi
0x14001cc9c  mov     r9b, 1
0x14001cc9f  lea     r8, [rbp+arg_0]
0x14001cca3  lea     rdx, aV; "v"
0x14001ccaa  mov     rcx, rax
0x14001ccad  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x14001ccb2  mov     cs:?s_Verbose@App@@2_NA, al; bool App::s_Verbose
0x14001ccb8  mov     rcx, r14
0x14001ccbb  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001ccc0  mov     [rbp+arg_0], rsi
0x14001ccc4  mov     r9b, 1
0x14001ccc7  lea     r8, [rbp+arg_0]
0x14001cccb  lea     rdx, aVv; "vv"
0x14001ccd2  mov     rcx, rax
0x14001ccd5  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x14001ccda  mov     cs:?s_VVerbose@App@@2_NA, al; bool App::s_VVerbose
0x14001cce0  test    al, al
0x14001cce2  jz      short loc_14001CCEB
0x14001cce4  mov     cs:?s_Verbose@App@@2_NA, 1; bool App::s_Verbose
0x14001cceb  cmp     cs:?s_Help@App@@2_NA, sil; bool App::s_Help
0x14001ccf2  jz      short loc_14001CCFB
0x14001ccf4  xor     eax, eax
0x14001ccf6  jmp     loc_14001D97A
0x14001ccfb  lea     rcx, [rbp+arg_10]
0x14001ccff  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x14001cd04  nop
0x14001cd05  mov     [rbp+arg_18], rsi
0x14001cd09  mov     rcx, r14
0x14001cd0c  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cd11  mov     r9b, 1
0x14001cd14  lea     r8, [rbp+arg_18]
0x14001cd18  lea     rdx, aTxml; "txml"
0x14001cd1f  mov     rcx, rax
0x14001cd22  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x14001cd27  test    al, al
0x14001cd29  jz      loc_14001CDB2
0x14001cd2f  lea     rdi, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x14001cd36  mov     rcx, rdi
0x14001cd39  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cd3e  mov     rbx, rax
0x14001cd41  mov     rcx, r14
0x14001cd44  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cd49  mov     r9b, 1
0x14001cd4c  mov     r8, [rbp+arg_18]
0x14001cd50  lea     rdx, [rbp+arg_0]
0x14001cd54  mov     rcx, rax
0x14001cd57  call    ?get_next_cl_token@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA?AV12@_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::get_next_cl_token(unsigned __int64,bool)
0x14001cd5c  mov     rdx, [rax]
0x14001cd5f  mov     rcx, rbx
0x14001cd62  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14001cd67  lea     rcx, [rbp+arg_0]
0x14001cd6b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001cd70  mov     rcx, rdi
0x14001cd73  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cd78  mov     rcx, rax
0x14001cd7b  call    ?strip_lt_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::strip_lt_ws(void)
0x14001cd80  mov     rcx, rdi
0x14001cd83  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cd88  mov     rcx, [rax]
0x14001cd8b  cmp     [rcx], rsi
0x14001cd8e  jnz     short loc_14001CDB2
0x14001cd90  lea     r8, aNoFileNameAfte_0; "no file name after the -txml switch"
0x14001cd97  mov     edx, 128h
0x14001cd9c  lea     rcx, aBaseWinsatExeA; "base\\winsat\\exe\\app.cpp"
0x14001cda3  call    Record_InternalError_w
0x14001cda8  nop
0x14001cda9  lea     rcx, [rbp+arg_10]
0x14001cdad  jmp     loc_14001CB80
0x14001cdb2  mov     rcx, r14
0x14001cdb5  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cdba  xor     r9d, r9d
0x14001cdbd  lea     r8, [rbp+arg_18]
0x14001cdc1  lea     rdx, aLog_0; "log"
0x14001cdc8  mov     rcx, rax
0x14001cdcb  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x14001cdd0  test    al, al
0x14001cdd2  jz      short loc_14001CE33
0x14001cdd4  mov     rcx, r14
0x14001cdd7  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001cddc  mov     r8, [rbp+arg_18]
0x14001cde0  lea     rdx, [rbp+arg_0]
0x14001cde4  mov     rcx, rax
0x14001cde7  call    ?get_next_cl_tokenq@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::get_next_cl_tokenq(unsigned __int64,bool)
0x14001cdec  mov     rdx, [rbp+arg_0]
0x14001cdf0  lea     rcx, [rbp+arg_10]
0x14001cdf4  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14001cdf9  lea     rcx, [rbp+arg_0]
0x14001cdfd  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001ce02  lea     rcx, [rbp+arg_10]
0x14001ce06  call    ?is_cl_switch@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_cl_switch(void)
0x14001ce0b  test    al, al
0x14001ce0d  jnz     short loc_14001CE33
0x14001ce0f  mov     rcx, r14
0x14001ce12  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001ce17  mov     r9b, 1
0x14001ce1a  mov     r8, [rbp+arg_18]
0x14001ce1e  lea     rdx, [rbp+arg_0]
0x14001ce22  mov     rcx, rax
0x14001ce25  call    ?get_next_cl_token@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA?AV12@_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::get_next_cl_token(unsigned __int64,bool)
0x14001ce2a  lea     rcx, [rbp+arg_0]
0x14001ce2e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001ce33  mov     rcx, r14
0x14001ce36  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001ce3b  mov     r9b, 1
0x14001ce3e  lea     r8, [rbp+arg_18]
0x14001ce42  lea     rdx, aXml; "xml"
0x14001ce49  mov     rcx, rax
0x14001ce4c  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x14001ce51  test    al, al
0x14001ce53  jz      short loc_14001CED1
0x14001ce55  mov     rcx, r14
0x14001ce58  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001ce5d  mov     r9b, 1
0x14001ce60  mov     r8, [rbp+arg_18]
0x14001ce64  lea     rdx, [rbp+arg_0]
0x14001ce68  mov     rcx, rax
0x14001ce6b  call    ?get_next_cl_token@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA?AV12@_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::get_next_cl_token(unsigned __int64,bool)
0x14001ce70  mov     rdx, [rax]
0x14001ce73  lea     rcx, [rbp+arg_10]
0x14001ce77  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14001ce7c  lea     rcx, [rbp+arg_0]
0x14001ce80  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001ce85  lea     rcx, [rbp+arg_10]
0x14001ce89  call    ?strip_lt_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::strip_lt_ws(void)
0x14001ce8e  mov     rbx, [rbp+arg_10]
0x14001ce92  cmp     [rbx], rsi
0x14001ce95  jnz     short loc_14001CEBA
  ... truncated ...
```
