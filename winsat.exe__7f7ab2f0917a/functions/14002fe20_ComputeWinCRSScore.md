# ComputeWinCRSScore

- ea: `0x14002fe20`
- end: `0x1400324dc`
- name: `ComputeWinCRSScore`
- size: `9916`
- prototype: `__int64 __fastcall(mlib::XmlStream *this)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140033bf4`

## callees

- `0x140004348`
- `0x14000449c`
- `0x140005d78`
- `0x1400083a4`
- `0x1400085b4`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140016d04`
- `0x140017af0`
- `0x140018968`
- `0x14001e0c0`
- `0x140020820`
- `0x14002093c`
- `0x14002c48c`
- `0x14002d9a4`
- `0x14002e0a4`
- `0x14002e584`
- `0x14002f430`
- `0x14002fe20`
- `0x140032ec8`
- `0x1400337c4`
- `0x140034414`
- `0x140034840`
- `0x14003ec14`
- `0x14004d864`
- `0x140052fac`
- `0x140053508`
- `0x14005354c`
- `0x1400535e4`
- `0x140053678`
- `0x140053bf0`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400300f7`
- `KERNEL32!GetLastError` at `0x140030263`
- `KERNEL32!GetLastError` at `0x1400303b2`
- `KERNEL32!GetLastError` at `0x140030501`
- `KERNEL32!GetLastError` at `0x140030650`
- `KERNEL32!GetLastError` at `0x14003079f`
- `KERNEL32!GetLastError` at `0x1400300f7`
- `KERNEL32!GetLastError` at `0x140030263`
- `KERNEL32!GetLastError` at `0x1400303b2`
- `KERNEL32!GetLastError` at `0x140030501`
- `KERNEL32!GetLastError` at `0x140030650`
- `KERNEL32!GetLastError` at `0x14003079f`

## string_xrefs

- `0x14002fff4`: `INFO: Failed to load current config - not limiting!`
- `0x14003013b`: `ERROR: Can't write CRS score to the registry %u: %s`
- `0x140030165`: `> Wrote CRS score to the registry %u`
- `0x14003018d`: `Skipping Registry Entry for CRS score`
- `0x1400302a7`: `ERROR: Can't write memory score to the registry %u: %s`
- `0x1400302ca`: `> Wrote memory score to the registry %u`
- `0x1400302eb`: `Skipping Registry Entry for memory score`
- `0x1400303f6`: `ERROR: Can't write cpu score to the registry %u: %s`
- `0x140030419`: `> Wrote cpu score to the registry %u`
- `0x14003043a`: `Skipping Registry Entry for cpu score`
- `0x140030545`: `ERROR: Can't write DWM score to the registry %u: %s`
- `0x140030568`: `> Wrote DWM score to the registry %u`
- `0x140030589`: `Skipping Registry Entry for DWM score`
- `0x140030694`: `ERROR: Can't write D3D score to the registry %u: %s`
- `0x1400306b7`: `> Wrote D3D score to the registry %u`
- `0x1400306d8`: `Skipping Registry Entry for D3D score`
- `0x1400307e3`: `ERROR: Can't write disk score to the registry %u: %s`
- `0x140030806`: `> Wrote disk score to the registry %u`
- `0x140030827`: `Skipping Registry Entry for disk score`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall ComputeWinCRSScore(__int64 **this, char a2, char a3, __int64 a4)
{
  bool v8; // dl
  __int64 v9; // rcx
  char v10; // si
  double v11; // xmm0_8
  __int64 v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rax
  double v15; // xmm6_8
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 *v33; // rax
  __int64 *v34; // rax
  double v35; // xmm6_8
  __int64 *v36; // rax
  __int64 *v37; // rax
  __int64 *v38; // rax
  double v39; // xmm6_8
  __int64 *v40; // rax
  __int64 *v41; // rax
  __int64 *v42; // rax
  double v43; // xmm6_8
  __int64 *v44; // rax
  __int64 *v45; // rax
  __int64 *v46; // rax
  double v47; // xmm6_8
  __int64 *v48; // rax
  __int64 *v49; // rax
  __int64 *v50; // rax
  double v51; // xmm6_8
  __int64 *v52; // rax
  __int64 *v53; // rax
  __int64 *v54; // rax
  double v55; // xmm6_8
  __int64 *v56; // rax
  __int64 *v57; // rax
  __int64 *v58; // rax
  double v59; // xmm6_8
  __int64 *v60; // rax
  __int64 *v61; // rax
  __int64 *v62; // rax
  double v63; // xmm6_8
  __int64 *v64; // rax
  __int64 *v65; // rax
  __int64 *v66; // rax
  double v67; // xmm6_8
  __int64 *v68; // rax
  __int64 *v69; // rax
  __int64 *v70; // rax
  double v71; // xmm6_8
  __int64 *v72; // rax
  __int64 *v73; // rax
  __int64 *v74; // rax
  __int64 *v75; // rax
  double v76; // xmm6_8
  __int64 *v77; // rax
  __int64 *v78; // rax
  __int64 *v79; // rax
  double v80; // xmm6_8
  __int64 *v81; // rax
  __int64 *v82; // rax
  __int64 *v83; // rax
  double v84; // xmm6_8
  __int64 *v85; // rax
  __int64 *v86; // rax
  __int64 *v87; // rax
  double v88; // xmm6_8
  __int64 *v89; // rax
  __int64 *v90; // rax
  __int64 *v91; // rax
  double v92; // xmm6_8
  __int64 *v93; // rax
  __int64 *v94; // rax
  __int64 *v95; // rax
  __int64 *v96; // rax
  __int64 *v97; // rax
  __int64 *v98; // rax
  __int64 *v99; // rax
  __int64 *v100; // rax
  __int64 *v101; // rax
  __int64 v102; // rdi
  __int64 *v103; // rax
  __int64 *v104; // rax
  __int64 v105; // rdi
  __int64 v106; // rdi
  __int64 *v107; // rax
  __int64 *v108; // rax
  __int64 *v109; // rax
  __int64 *v110; // rax
  __int64 *v111; // rax
  __int64 *v112; // rax
  __int64 *v113; // rax
  __int64 *v114; // rax
  __int64 v115; // rdi
  __int64 v116; // rdi
  __int64 *v117; // rax
  __int64 *v118; // rax
  __int64 *v119; // rax
  __int64 *v120; // rax
  __int64 *v121; // rax
  __int64 *v122; // rax
  __int64 *v123; // rax
  __int64 *v124; // rax
  __int64 v125; // rdi
  __int64 v126; // rdi
  __int64 *v127; // rax
  __int64 *v128; // rax
  __int64 *v129; // rax
  __int64 *v130; // rax
  __int64 *v131; // rax
  __int64 *v132; // rax
  __int64 *v133; // rax
  __int64 *v134; // rax
  __int64 v135; // rdi
  __int64 v136; // rdi
  __int64 *v137; // rax
  __int64 *v138; // rax
  __int64 *v139; // rax
  __int64 *v140; // rax
  __int64 *v141; // rax
  __int64 *v142; // rax
  __int64 *v143; // rax
  __int64 *v144; // rax
  __int64 result; // rax
  unsigned __int64 *v146; // [rsp+30h] [rbp-258h] BYREF
  unsigned __int64 *v147; // [rsp+38h] [rbp-250h] BYREF
  unsigned __int64 *v148; // [rsp+40h] [rbp-248h] BYREF
  unsigned __int64 *v149; // [rsp+48h] [rbp-240h] BYREF
  unsigned __int64 *v150; // [rsp+50h] [rbp-238h] BYREF
  unsigned __int64 *v151; // [rsp+58h] [rbp-230h] BYREF
  _QWORD v152[2]; // [rsp+60h] [rbp-228h] BYREF
  _QWORD v153[10]; // [rsp+70h] [rbp-218h] BYREF
  mlib::MSError *v154; // [rsp+C0h] [rbp-1C8h] BYREF
  CHAR v155[80]; // [rsp+D0h] [rbp-1B8h] BYREF
  CHAR Buffer[256]; // [rsp+120h] [rbp-168h] BYREF
  DWORD LastError; // [rsp+220h] [rbp-68h]
  char v158; // [rsp+224h] [rbp-64h]
  __int64 v159; // [rsp+228h] [rbp-60h]

  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v152,
      L"NtNlf");
    mlib::BoolReg::BoolReg((__int64)v155);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v152);
    byte_1401C3310 = mlib::BoolReg::get((mlib::BoolReg *)v155, v8);
    LoadScalingFactorsFromTextFile();
    ComputeCPUScore();
    LOBYTE(v9) = a3;
    ComputeMemScore(v9);
    ComputeDWMScore();
    dbl_140168890 = DOUBLE_9_9;
    dbl_140168948 = DOUBLE_9_9;
    dbl_1401688C0 = DOUBLE_9_9;
    qword_1401C3320 = (__int64)L"NoD3DTestRun";
    qword_1401C3330 = (__int64)L"We no longer run the D3D test. Returned scores and metrics are hardcoded sentinel values.";
    ComputeDiskScore();
    if ( !a2
      || dbl_140168900 == 1.797693134862316e308
      || dbl_140168880 == 1.797693134862316e308
      || dbl_1401688F0 == 1.797693134862316e308
      || dbl_1401688C0 == 1.797693134862316e308
      || dbl_140168930 == 1.797693134862316e308 )
    {
      v10 = 0;
      v11 = 0.0;
    }
    else
    {
      v10 = 1;
      v11 = fmin(
              fmin(fmin(fmin(fmin(1.797693134862316e308, dbl_140168900), dbl_140168880), dbl_1401688F0), dbl_1401688C0),
              dbl_140168930);
      dbl_140168970 = v11;
      if ( (int)WinSATCriticalHardwareInfo::PopulateFromDoc(CurrentConfig, a4, 4095) < 0 )
      {
        if ( App::s_IsPrivateBld && App::s_Verbose )
        {
          v12 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
          v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                  (__int64 *)(v12 + 240),
                  (__int64)L"INFO: Failed to load current config - not limiting!");
          std::endl(v13);
        }
        v11 = dbl_140168970;
LABEL_16:
        if ( v11 == 0.0 )
        {
LABEL_78:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v146,
            L"WinSPR");
          if ( *((_DWORD *)this + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
          *((_DWORD *)this + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)this);
          v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v33, &v146);
          ++*((_DWORD *)this + 3);
          *((_BYTE *)this + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
          if ( (unsigned int)dword_1401C330C >= 6 )
          {
            if ( v10 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"SystemScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v34, &v147);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v35 = dbl_140168970;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v35);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"SystemScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v37 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v36,
                        &v146);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v37, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
            }
            if ( dbl_140168880 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"MemoryScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v38 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v38, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v39 = dbl_140168880;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v39);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"MemoryScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v40 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v41 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v40,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v41, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( dbl_140168900 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"CpuScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v42 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v42, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v43 = dbl_140168900;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v43);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"CpuScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v45 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v44,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( dbl_140168898 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"CPUSubAggScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v46 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v46, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v47 = dbl_140168898;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v47);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"CPUSubAggScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v48 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v49 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v48,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v49, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( dbl_1401688D0 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"VideoEncodeScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v50 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v50, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v51 = dbl_1401688D0;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v51);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"VideoEncodeScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v52 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v53 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v52,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v53, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( dbl_1401688F0 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"GraphicsScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v54 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v54, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v55 = dbl_1401688F0;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v55);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"GraphicsScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v56 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v57 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v56,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v57, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( dbl_140168890 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"Dx9SubScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v58 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v58, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v59 = dbl_140168890;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v59);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"Dx9SubScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v60 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v61 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v60,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v61, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( dbl_140168948 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"Dx10SubScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v62 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v62, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v63 = dbl_140168948;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v63);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"Dx10SubScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v64 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v65 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v64,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( dbl_1401688C0 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"GamingScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v66, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v67 = dbl_1401688C0;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v67);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"GamingScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v68 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v69 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v68,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v69, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( dbl_140168930 != 1.797693134862316e308 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v146,
                L"DiskScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v70 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v70, &v146);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              v71 = dbl_140168930;
              mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
              std::basic_ostream<unsigned short>::operator<<((__int64)*this, v71);
              mlib::XmlStream::AfterText((mlib::XmlStream *)this);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"DiskScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v72 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v73 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v72,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v73, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            }
            if ( byte_1401C3328 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"ScoreRaisedDueToHigherPreviousScore");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v74 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v74, &v147);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              if ( *(double *)&qword_140168940 != 1.797693134862316e308 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v146,
                  L"ActualCPUScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v75 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v75,
                  &v146);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                v76 = *(double *)&qword_140168940;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::basic_ostream<unsigned short>::operator<<((__int64)*this, v76);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"ActualCPUScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v77 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v78 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                          v77,
                          &v147);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v78, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
              }
              if ( *(double *)&qword_140168950 != 1.797693134862316e308 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v146,
                  L"ActualMemScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v79 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v79,
                  &v146);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                v80 = *(double *)&qword_140168950;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::basic_ostream<unsigned short>::operator<<((__int64)*this, v80);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"ActualMemScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v81 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v82 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                          v81,
                          &v147);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v82, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
              }
              if ( *(double *)&qword_1401688E8 != 1.797693134862316e308 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v146,
                  L"ActualD3DScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v83 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v83,
                  &v146);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                v84 = *(double *)&qword_1401688E8;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::basic_ostream<unsigned short>::operator<<((__int64)*this, v84);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"ActualD3DScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v85 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v86 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                          v85,
                          &v147);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v86, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
              }
              if ( *(double *)&qword_1401688E0 != 1.797693134862316e308 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v146,
                  L"ActualDWMScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v87 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v87,
                  &v146);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                v88 = *(double *)&qword_1401688E0;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::basic_ostream<unsigned short>::operator<<((__int64)*this, v88);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"ActualDWMScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v89 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v90 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                          v89,
                          &v147);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v90, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
              }
              if ( *(double *)&qword_1401688F8 != 1.797693134862316e308 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v146,
                  L"ActualDiskScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v91 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v91,
                  &v146);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                v92 = *(double *)&qword_1401688F8;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::basic_ostream<unsigned short>::operator<<((__int64)*this, v92);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"ActualDiskScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v93 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v94 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                          v93,
                          &v147);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v94, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
              }
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"ScoreRaisedDueToHigherPreviousScore");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v95 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v96 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                        v95,
                        &v147);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v96, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
            }
            if ( qword_1401C3340 || qword_1401C3360 || qword_1401C3320 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v147,
                L"LimitsApplied");
              if ( *((_DWORD *)this + 2) == 2 )
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
              *((_DWORD *)this + 2) = 2;
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
              v97 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
              mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v97, &v147);
              ++*((_DWORD *)this + 3);
              *((_BYTE *)this + 17) = 0;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              if ( qword_1401C3340 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v148,
                  L"MemoryScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v98 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v98,
                  &v148);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v151,
                  L"LimitApplied");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v99 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v99,
                  &v151);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v150,
                  L"Friendly");
                *((_DWORD *)this + 2) = 3;
                v100 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L" ");
                v101 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                         v100,
                         &v150);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v101, (__int64)L"=");
                v102 = qword_1401C32F0;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, v102);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v149,
                  L"Relation");
                *((_DWORD *)this + 2) = 3;
                v103 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L" ");
                v104 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                         v103,
                         &v149);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v104, (__int64)L"=");
                v105 = qword_1401C3348;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, v105);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                v106 = qword_1401C3340;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::basic_ostream<unsigned short>::operator<<(*this, v106);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v146,
                  L"LimitApplied");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v107 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v108 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                           v107,
                           &v146);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v108, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"MemoryScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v109 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v110 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                           v109,
                           &v147);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v110, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v149);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v150);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v151);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v148);
              }
              if ( qword_1401C3360 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"GraphicsScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v111 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v111,
                  &v147);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v149,
                  L"LimitApplied");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v112 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v112,
                  &v149);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v150,
                  L"Friendly");
                *((_DWORD *)this + 2) = 3;
                v113 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L" ");
                v114 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                         v113,
                         &v150);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v114, (__int64)L"=");
                v115 = qword_1401C3318;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, v115);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                v116 = qword_1401C3360;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, v116);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v151,
                  L"LimitApplied");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v117 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v118 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                           v117,
                           &v151);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v118, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v148,
                  L"GraphicsScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v119 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v120 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                           v119,
                           &v148);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v120, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v148);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v151);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v150);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v149);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              }
              if ( qword_1401C3320 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"GamingScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v121 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v121,
                  &v147);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v149,
                  L"LimitApplied");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v122 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v122,
                  &v149);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v150,
                  L"Friendly");
                *((_DWORD *)this + 2) = 3;
                v123 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L" ");
                v124 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                         v123,
                         &v150);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v124, (__int64)L"=");
                v125 = qword_1401C3330;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, v125);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                v126 = qword_1401C3320;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, v126);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v151,
                  L"LimitApplied");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v127 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v128 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                           v127,
                           &v151);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v128, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v148,
                  L"GamingScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v129 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v130 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                           v129,
                           &v148);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v130, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v148);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v151);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v150);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v149);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              }
              if ( qword_1401C3368 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v147,
                  L"DiskScore");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v131 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v131,
                  &v147);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v149,
                  L"LimitApplied");
                if ( *((_DWORD *)this + 2) == 2 )
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
                *((_DWORD *)this + 2) = 2;
                mlib::XmlStream::Indent((mlib::XmlStream *)this);
                v132 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
                mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v132,
                  &v149);
                ++*((_DWORD *)this + 3);
                *((_BYTE *)this + 17) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v150,
                  L"Friendly");
                *((_DWORD *)this + 2) = 3;
                v133 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L" ");
                v134 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                         v133,
                         &v150);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v134, (__int64)L"=");
                v135 = qword_1401C3358;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, v135);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                v136 = qword_1401C3368;
                mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, v136);
                mlib::XmlStream::AfterText((mlib::XmlStream *)this);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v151,
                  L"LimitApplied");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v137 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v138 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                           v137,
                           &v151);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v138, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v148,
                  L"DiskScore");
                --*((_DWORD *)this + 3);
                if ( *((_DWORD *)this + 2) == 1 )
                {
                  if ( !*((_BYTE *)this + 17) )
                    mlib::XmlStream::Indent((mlib::XmlStream *)this);
                  *((_BYTE *)this + 17) = 0;
                  v139 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                  v140 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                           v139,
                           &v148);
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v140, (__int64)L">");
                }
                else if ( *((_DWORD *)this + 2) == 2 )
                {
                  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
                }
                *((_DWORD *)this + 2) = 1;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v148);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v151);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v150);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v149);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v147);
              }
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v148,
                L"LimitsApplied");
              --*((_DWORD *)this + 3);
              if ( *((_DWORD *)this + 2) == 1 )
              {
                if ( !*((_BYTE *)this + 17) )
                  mlib::XmlStream::Indent((mlib::XmlStream *)this);
                *((_BYTE *)this + 17) = 0;
                v141 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
                v142 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                         v141,
                         &v148);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, (__int64)L">");
              }
              else if ( *((_DWORD *)this + 2) == 2 )
              {
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
              }
              *((_DWORD *)this + 2) = 1;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v148);
            }
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v148,
            L"WinSPR");
          --*((_DWORD *)this + 3);
          if ( *((_DWORD *)this + 2) == 1 )
          {
            if ( !*((_BYTE *)this + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)this);
            *((_BYTE *)this + 17) = 0;
            v143 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
            v144 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v143,
                     &v148);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v144, (__int64)L">");
          }
          else if ( *((_DWORD *)this + 2) == 2 )
          {
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"/>");
          }
          *((_DWORD *)this + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v148);
          if ( App::s_isFormal )
          {
            SQMAllResults();
            SetCommonSQMDataPoints();
          }
          mlib::BoolReg::~BoolReg((mlib::BoolReg *)v155);
          return 0;
        }
        if ( v11 != 1.797693134862316e308 )
        {
          if ( !App::s_isAxeMode )
          {
            v14 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile);
            if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v14) )
            {
              if ( !App::s_WsSwapTest && App::s_RegistryCreated )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v146,
                  L"WinCRSScore");
                mlib::DWORDReg::DWORDReg(v153);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
                v15 = DOUBLE_10_0;
                mlib::DWORDReg::operator=(v153, (unsigned int)(int)(dbl_140168970 * 10.0));
                if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v153) )
                {
                  LastError = GetLastError();
                  v158 = 1;
                  v159 = 0;
                  mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
                  v16 = mlib::DWORDReg::operator unsigned long(v153);
                  Log_Text_F(
                    "base\\winsat\\exe\\processresults.cpp",
                    1736,
                    "ERROR: Can't write CRS score to the registry %u: %s",
                    v16,
                    Buffer);
                }
                else
                {
                  v17 = mlib::DWORDReg::operator unsigned long(v153);
                  Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1739, "> Wrote CRS score to the registry %u", v17);
                }
                mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v153);
                goto LABEL_28;
              }
            }
          }
          Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1742, "Skipping Registry Entry for CRS score");
        }
        v15 = DOUBLE_10_0;
LABEL_28:
        if ( dbl_140168880 != 1.797693134862316e308 )
        {
          if ( App::s_isAxeMode
            || (v18 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
                !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v18))
            || App::s_WsSwapTest
            || !App::s_RegistryCreated )
          {
            Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1763, "Skipping Registry Entry for memory score");
          }
          else
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v146,
              L"MemoryScore");
            mlib::DWORDReg::DWORDReg(v153);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            mlib::DWORDReg::operator=(v153, (unsigned int)(int)(dbl_140168880 * v15));
            if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v153) )
            {
              LastError = GetLastError();
              v158 = 1;
              v159 = 0;
              mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
              v19 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F(
                "base\\winsat\\exe\\processresults.cpp",
                1756,
                "ERROR: Can't write memory score to the registry %u: %s",
                v19,
                Buffer);
            }
            else
            {
              v20 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1760, "> Wrote memory score to the registry %u", v20);
            }
            mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v153);
          }
        }
        if ( dbl_140168900 != 1.797693134862316e308 )
        {
          if ( App::s_isAxeMode
            || (v21 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
                !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v21))
            || App::s_WsSwapTest
            || !App::s_RegistryCreated )
          {
            Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1782, "Skipping Registry Entry for cpu score");
          }
          else
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v146,
              L"CPUScore");
            mlib::DWORDReg::DWORDReg(v153);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            mlib::DWORDReg::operator=(v153, (unsigned int)(int)(dbl_140168900 * v15));
            if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v153) )
            {
              LastError = GetLastError();
              v158 = 1;
              v159 = 0;
              mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
              v22 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F(
                "base\\winsat\\exe\\processresults.cpp",
                1776,
                "ERROR: Can't write cpu score to the registry %u: %s",
                v22,
                Buffer);
            }
            else
            {
              v23 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1779, "> Wrote cpu score to the registry %u", v23);
            }
            mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v153);
          }
        }
        if ( dbl_1401688F0 != 1.797693134862316e308 )
        {
          if ( App::s_isAxeMode
            || (v24 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
                !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v24))
            || App::s_WsSwapTest
            || !App::s_RegistryCreated )
          {
            Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1803, "Skipping Registry Entry for DWM score");
          }
          else
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v146,
              L"DWMScore");
            mlib::DWORDReg::DWORDReg(v153);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            mlib::DWORDReg::operator=(v153, (unsigned int)(int)(dbl_1401688F0 * v15));
            if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v153) )
            {
              LastError = GetLastError();
              v158 = 1;
              v159 = 0;
              mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
              v25 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F(
                "base\\winsat\\exe\\processresults.cpp",
                1796,
                "ERROR: Can't write DWM score to the registry %u: %s",
                v25,
                Buffer);
            }
            else
            {
              v26 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1800, "> Wrote DWM score to the registry %u", v26);
            }
            mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v153);
          }
        }
        if ( dbl_1401688C0 != 1.797693134862316e308 )
        {
          if ( App::s_isAxeMode
            || (v27 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
                !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v27))
            || App::s_WsSwapTest
            || !App::s_RegistryCreated )
          {
            Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1823, "Skipping Registry Entry for D3D score");
          }
          else
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v146,
              L"D3DScore");
            mlib::DWORDReg::DWORDReg(v153);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            mlib::DWORDReg::operator=(v153, (unsigned int)(int)(dbl_1401688C0 * v15));
            if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v153) )
            {
              LastError = GetLastError();
              v158 = 1;
              v159 = 0;
              mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
              v28 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F(
                "base\\winsat\\exe\\processresults.cpp",
                1816,
                "ERROR: Can't write D3D score to the registry %u: %s",
                v28,
                Buffer);
            }
            else
            {
              v29 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1820, "> Wrote D3D score to the registry %u", v29);
            }
            mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v153);
          }
        }
        if ( dbl_140168930 != 1.797693134862316e308 )
        {
          if ( App::s_isAxeMode
            || (v30 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
                !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v30))
            || App::s_WsSwapTest
            || !App::s_RegistryCreated )
          {
            Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1843, "Skipping Registry Entry for disk score");
          }
          else
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v146,
              L"DiskScore");
            mlib::DWORDReg::DWORDReg(v153);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v146);
            mlib::DWORDReg::operator=(v153, (unsigned int)(int)(dbl_140168930 * v15));
            if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v153) )
            {
              LastError = GetLastError();
              v158 = 1;
              v159 = 0;
              mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
              v31 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F(
                "base\\winsat\\exe\\processresults.cpp",
                1836,
                "ERROR: Can't write disk score to the registry %u: %s",
                v31,
                Buffer);
            }
            else
            {
              v32 = mlib::DWORDReg::operator unsigned long(v153);
              Log_Text_F("base\\winsat\\exe\\processresults.cpp", 1840, "> Wrote disk score to the registry %u", v32);
            }
            mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v153);
          }
        }
        goto LABEL_78;
      }
      LimitByMostRecentAssessment();
    }
    dbl_140168970 = v11;
    goto LABEL_16;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( mlib::MSError *v154 )
  {
    return *(unsigned int *)v154;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x14002fe20  mov     rax, rsp
0x14002fe23  mov     [rax+10h], rbx
0x14002fe27  mov     [rax+18h], rsi
0x14002fe2b  push    rdi
0x14002fe2c  push    r12
0x14002fe2e  push    r13
0x14002fe30  push    r14
0x14002fe32  push    r15
0x14002fe34  sub     rsp, 260h
0x14002fe3b  movaps  xmmword ptr [rax-38h], xmm6
0x14002fe3f  movaps  xmmword ptr [rax-48h], xmm7
0x14002fe43  mov     rax, cs:__security_cookie
0x14002fe4a  xor     rax, rsp
0x14002fe4d  mov     [rsp+288h+var_58], rax
0x14002fe55  mov     r14, r9
0x14002fe58  mov     dil, r8b
0x14002fe5b  mov     sil, dl
0x14002fe5e  mov     rbx, rcx
0x14002fe61  lea     rdx, aNtnlf; "NtNlf"
0x14002fe68  lea     rcx, [rsp+288h+var_228]
0x14002fe6d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002fe72  nop
0x14002fe73  lea     r8, [rsp+288h+var_228]
0x14002fe78  mov     rdx, cs:qword_1401C6370
0x14002fe7f  lea     rcx, [rsp+288h+var_1B8]
0x14002fe87  call    ??0BoolReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::BoolReg::BoolReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002fe8c  nop
0x14002fe8d  lea     rcx, [rsp+288h+var_228]
0x14002fe92  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002fe97  lea     rcx, [rsp+288h+var_1B8]; this
0x14002fe9f  call    ?get@BoolReg@mlib@@QEAA_N_N@Z; mlib::BoolReg::get(bool)
0x14002fea4  mov     cs:byte_1401C3310, al
0x14002feaa  call    LoadScalingFactorsFromTextFile
0x14002feaf  call    ComputeCPUScore
0x14002feb4  mov     cl, dil
0x14002feb7  call    ComputeMemScore
0x14002febc  call    ComputeDWMScore
0x14002fec1  movsd   xmm0, cs:__real@4023cccccccccccd
0x14002fec9  movsd   cs:dbl_140168890, xmm0
0x14002fed1  movsd   cs:dbl_140168948, xmm0
0x14002fed9  movsd   cs:dbl_1401688C0, xmm0
0x14002fee1  lea     rax, aNod3dtestrun; "NoD3DTestRun"
0x14002fee8  mov     cs:qword_1401C3320, rax
0x14002feef  lea     rax, aWeNoLongerRunT; "We no longer run the D3D test. Returned"...
0x14002fef6  mov     cs:qword_1401C3330, rax
0x14002fefd  call    ComputeDiskScore
0x14002ff02  xor     r12d, r12d
0x14002ff05  movsd   xmm7, cs:__real@7fefffffffffffff
0x14002ff0d  test    sil, sil
0x14002ff10  jz      loc_140030019
0x14002ff16  movsd   xmm0, cs:dbl_140168900
0x14002ff1e  ucomisd xmm0, xmm7
0x14002ff22  jp      short loc_14002FF2A
0x14002ff24  jz      loc_140030019
0x14002ff2a  movsd   xmm0, cs:dbl_140168880
0x14002ff32  ucomisd xmm0, xmm7
0x14002ff36  jp      short loc_14002FF3E
0x14002ff38  jz      loc_140030019
0x14002ff3e  movsd   xmm0, cs:dbl_1401688F0
0x14002ff46  ucomisd xmm0, xmm7
0x14002ff4a  jp      short loc_14002FF52
0x14002ff4c  jz      loc_140030019
0x14002ff52  movsd   xmm0, cs:dbl_1401688C0
0x14002ff5a  ucomisd xmm0, xmm7
0x14002ff5e  jp      short loc_14002FF66
0x14002ff60  jz      loc_140030019
0x14002ff66  movsd   xmm0, cs:dbl_140168930
0x14002ff6e  ucomisd xmm0, xmm7
0x14002ff72  jp      short loc_14002FF7A
0x14002ff74  jz      loc_140030019
0x14002ff7a  mov     r15d, 1
0x14002ff80  mov     sil, r15b
0x14002ff83  movaps  xmm0, xmm7
0x14002ff86  minsd   xmm0, cs:dbl_140168900
0x14002ff8e  minsd   xmm0, cs:dbl_140168880
0x14002ff96  minsd   xmm0, cs:dbl_1401688F0
0x14002ff9e  minsd   xmm0, cs:dbl_1401688C0
0x14002ffa6  minsd   xmm0, cs:dbl_140168930
0x14002ffae  movsd   cs:dbl_140168970, xmm0
0x14002ffb6  mov     r8d, 0FFFh
0x14002ffbc  mov     rdx, r14
0x14002ffbf  lea     rcx, ?CurrentConfig@@3UWinSATCriticalHardwareInfo@@A; WinSATCriticalHardwareInfo CurrentConfig
0x14002ffc6  call    ?PopulateFromDoc@WinSATCriticalHardwareInfo@@QEAAJPEAUIXMLDOMDocument2@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateFromDoc(IXMLDOMDocument2 *,HardwareID)
0x14002ffcb  test    eax, eax
0x14002ffcd  jns     short loc_140030012
0x14002ffcf  cmp     cs:?s_IsPrivateBld@App@@2_NA, r12b; bool App::s_IsPrivateBld
0x14002ffd6  jz      short loc_140030008
0x14002ffd8  cmp     cs:?s_Verbose@App@@2_NA, r12b; bool App::s_Verbose
0x14002ffdf  jz      short loc_140030008
0x14002ffe1  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14002ffe8  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ffed  lea     rcx, [rax+0F0h]
0x14002fff4  lea     rdx, aInfoFailedToLo_0; "INFO: Failed to load current config - n"...
0x14002fffb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140030000  mov     rcx, rax
0x140030003  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140030008  movsd   xmm0, cs:dbl_140168970
0x140030010  jmp     short loc_14003002D
0x140030012  call    LimitByMostRecentAssessment
0x140030017  jmp     short loc_140030025
0x140030019  mov     sil, r12b
0x14003001c  xorps   xmm0, xmm0
0x14003001f  mov     r15d, 1
0x140030025  movsd   cs:dbl_140168970, xmm0
0x14003002d  xorps   xmm1, xmm1
0x140030030  ucomisd xmm0, xmm1
0x140030034  jp      short loc_14003003C
0x140030036  jz      loc_14003083B
0x14003003c  ucomisd xmm0, xmm7
0x140030040  jp      short loc_140030050
0x140030042  jnz     short loc_140030050
0x140030044  lea     rdi, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14003004b  jmp     loc_1400301A8
0x140030050  cmp     cs:?s_isAxeMode@App@@2_NA, r12b; bool App::s_isAxeMode
0x140030057  jnz     loc_14003018D
0x14003005d  lea     rcx, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x140030064  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140030069  mov     rcx, rax
0x14003006c  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x140030071  test    al, al
0x140030073  jz      loc_14003018D
0x140030079  cmp     cs:?s_WsSwapTest@App@@2_NA, r12b; bool App::s_WsSwapTest
0x140030080  jnz     loc_14003018D
0x140030086  cmp     cs:?s_RegistryCreated@App@@2_NA, r12b; bool App::s_RegistryCreated
0x14003008d  jz      loc_14003018D
0x140030093  lea     rdx, aWincrsscore; "WinCRSScore"
0x14003009a  lea     rcx, [rsp+288h+var_258]
0x14003009f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400300a4  nop
0x1400300a5  lea     r8, [rsp+288h+var_258]
0x1400300aa  mov     rdx, cs:qword_1401C6370
0x1400300b1  lea     rcx, [rsp+288h+var_218]
0x1400300b6  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x1400300bb  nop
0x1400300bc  lea     rcx, [rsp+288h+var_258]
0x1400300c1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400300c6  movsd   xmm0, cs:dbl_140168970
0x1400300ce  movsd   xmm6, cs:__real@4024000000000000
0x1400300d6  mulsd   xmm0, xmm6
0x1400300da  cvttsd2si rdx, xmm0
0x1400300df  lea     rcx, [rsp+288h+var_218]
0x1400300e4  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x1400300e9  lea     rcx, [rsp+288h+var_218]; this
0x1400300ee  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x1400300f3  test    eax, eax
0x1400300f5  jz      short loc_140030158
0x1400300f7  call    cs:__imp_GetLastError
0x1400300fd  mov     [rsp+288h+var_68], eax
0x140030104  mov     [rsp+288h+var_64], r15b
0x14003010c  mov     [rsp+288h+var_60], r12
0x140030114  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x14003011c  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x140030121  lea     rcx, [rsp+288h+var_218]
0x140030126  call    ??BDWORDReg@mlib@@QEAAKXZ; mlib::DWORDReg::operator ulong(void)
0x14003012b  lea     rcx, [rsp+288h+Buffer]
0x140030133  mov     [rsp+288h+var_268], rcx
0x140030138  mov     r9d, eax
0x14003013b  lea     r8, aErrorCanTWrite_5; "ERROR: Can't write CRS score to the reg"...
0x140030142  mov     edx, 6C8h
0x140030147  lea     rdi, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14003014e  mov     rcx, rdi
0x140030151  call    Log_Text_F
0x140030156  jmp     short loc_140030181
0x140030158  lea     rcx, [rsp+288h+var_218]
0x14003015d  call    ??BDWORDReg@mlib@@QEAAKXZ; mlib::DWORDReg::operator ulong(void)
0x140030162  mov     r9d, eax
0x140030165  lea     r8, aWroteCrsScoreT; "> Wrote CRS score to the registry %u"
0x14003016c  mov     edx, 6CBh
0x140030171  lea     rdi, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x140030178  mov     rcx, rdi
0x14003017b  call    Log_Text_F
0x140030180  nop
0x140030181  lea     rcx, [rsp+288h+var_218]; this
0x140030186  call    ??1DWORDReg@mlib@@UEAA@XZ; mlib::DWORDReg::~DWORDReg(void)
0x14003018b  jmp     short loc_1400301B0
0x14003018d  lea     r8, aSkippingRegist; "Skipping Registry Entry for CRS score"
0x140030194  mov     edx, 6CEh
0x140030199  lea     rdi, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x1400301a0  mov     rcx, rdi
0x1400301a3  call    Log_Text_F
0x1400301a8  movsd   xmm6, cs:__real@4024000000000000
0x1400301b0  movsd   xmm0, cs:dbl_140168880
0x1400301b8  ucomisd xmm0, xmm7
0x1400301bc  jp      short loc_1400301C4
0x1400301be  jz      loc_1400302FF
0x1400301c4  cmp     cs:?s_isAxeMode@App@@2_NA, r12b; bool App::s_isAxeMode
0x1400301cb  jnz     loc_1400302EB
0x1400301d1  lea     rcx, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x1400301d8  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x1400301dd  mov     rcx, rax
0x1400301e0  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x1400301e5  test    al, al
0x1400301e7  jz      loc_1400302EB
0x1400301ed  cmp     cs:?s_WsSwapTest@App@@2_NA, r12b; bool App::s_WsSwapTest
0x1400301f4  jnz     loc_1400302EB
0x1400301fa  cmp     cs:?s_RegistryCreated@App@@2_NA, r12b; bool App::s_RegistryCreated
0x140030201  jz      loc_1400302EB
0x140030207  lea     rdx, aMemoryscore; "MemoryScore"
0x14003020e  lea     rcx, [rsp+288h+var_258]
0x140030213  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140030218  nop
0x140030219  lea     r8, [rsp+288h+var_258]
0x14003021e  mov     rdx, cs:qword_1401C6370
0x140030225  lea     rcx, [rsp+288h+var_218]
0x14003022a  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14003022f  nop
0x140030230  lea     rcx, [rsp+288h+var_258]
0x140030235  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003023a  movsd   xmm0, cs:dbl_140168880
0x140030242  mulsd   xmm0, xmm6
0x140030246  cvttsd2si rdx, xmm0
0x14003024b  lea     rcx, [rsp+288h+var_218]
0x140030250  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x140030255  lea     rcx, [rsp+288h+var_218]; this
0x14003025a  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x14003025f  test    eax, eax
0x140030261  jz      short loc_1400302BD
0x140030263  call    cs:__imp_GetLastError
0x140030269  mov     [rsp+288h+var_68], eax
0x140030270  mov     [rsp+288h+var_64], r15b
0x140030278  mov     [rsp+288h+var_60], r12
0x140030280  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x140030288  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x14003028d  lea     rcx, [rsp+288h+var_218]
0x140030292  call    ??BDWORDReg@mlib@@QEAAKXZ; mlib::DWORDReg::operator ulong(void)
0x140030297  lea     rcx, [rsp+288h+Buffer]
0x14003029f  mov     [rsp+288h+var_268], rcx
0x1400302a4  mov     r9d, eax
0x1400302a7  lea     r8, aErrorCanTWrite_16; "ERROR: Can't write memory score to the "...
0x1400302ae  mov     edx, 6DCh
0x1400302b3  mov     rcx, rdi
0x1400302b6  call    Log_Text_F
0x1400302bb  jmp     short loc_1400302DF
0x1400302bd  lea     rcx, [rsp+288h+var_218]
0x1400302c2  call    ??BDWORDReg@mlib@@QEAAKXZ; mlib::DWORDReg::operator ulong(void)
0x1400302c7  mov     r9d, eax
0x1400302ca  lea     r8, aWroteMemorySco; "> Wrote memory score to the registry %u"
0x1400302d1  mov     edx, 6E0h
0x1400302d6  mov     rcx, rdi
0x1400302d9  call    Log_Text_F
0x1400302de  nop
0x1400302df  lea     rcx, [rsp+288h+var_218]; this
0x1400302e4  call    ??1DWORDReg@mlib@@UEAA@XZ; mlib::DWORDReg::~DWORDReg(void)
0x1400302e9  jmp     short loc_1400302FF
0x1400302eb  lea     r8, aSkippingRegist_6; "Skipping Registry Entry for memory scor"...
0x1400302f2  mov     edx, 6E3h
0x1400302f7  mov     rcx, rdi
0x1400302fa  call    Log_Text_F
0x1400302ff  movsd   xmm0, cs:dbl_140168900
0x140030307  ucomisd xmm0, xmm7
0x14003030b  jp      short loc_140030313
0x14003030d  jz      loc_14003044E
0x140030313  cmp     cs:?s_isAxeMode@App@@2_NA, r12b; bool App::s_isAxeMode
0x14003031a  jnz     loc_14003043A
0x140030320  lea     rcx, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x140030327  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14003032c  mov     rcx, rax
0x14003032f  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x140030334  test    al, al
0x140030336  jz      loc_14003043A
0x14003033c  cmp     cs:?s_WsSwapTest@App@@2_NA, r12b; bool App::s_WsSwapTest
0x140030343  jnz     loc_14003043A
0x140030349  cmp     cs:?s_RegistryCreated@App@@2_NA, r12b; bool App::s_RegistryCreated
0x140030350  jz      loc_14003043A
0x140030356  lea     rdx, aCpuscore; "CPUScore"
0x14003035d  lea     rcx, [rsp+288h+var_258]
0x140030362  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140030367  nop
0x140030368  lea     r8, [rsp+288h+var_258]
0x14003036d  mov     rdx, cs:qword_1401C6370
0x140030374  lea     rcx, [rsp+288h+var_218]
0x140030379  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14003037e  nop
0x14003037f  lea     rcx, [rsp+288h+var_258]
0x140030384  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140030389  movsd   xmm0, cs:dbl_140168900
0x140030391  mulsd   xmm0, xmm6
0x140030395  cvttsd2si rdx, xmm0
0x14003039a  lea     rcx, [rsp+288h+var_218]
0x14003039f  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x1400303a4  lea     rcx, [rsp+288h+var_218]; this
0x1400303a9  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x1400303ae  test    eax, eax
0x1400303b0  jz      short loc_14003040C
0x1400303b2  call    cs:__imp_GetLastError
0x1400303b8  mov     [rsp+288h+var_68], eax
0x1400303bf  mov     [rsp+288h+var_64], r15b
0x1400303c7  mov     [rsp+288h+var_60], r12
0x1400303cf  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x1400303d7  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x1400303dc  lea     rcx, [rsp+288h+var_218]
0x1400303e1  call    ??BDWORDReg@mlib@@QEAAKXZ; mlib::DWORDReg::operator ulong(void)
0x1400303e6  lea     rcx, [rsp+288h+Buffer]
0x1400303ee  mov     [rsp+288h+var_268], rcx
0x1400303f3  mov     r9d, eax
0x1400303f6  lea     r8, aErrorCanTWrite_10; "ERROR: Can't write cpu score to the reg"...
0x1400303fd  mov     edx, 6F0h
0x140030402  mov     rcx, rdi
0x140030405  call    Log_Text_F
0x14003040a  jmp     short loc_14003042E
  ... truncated ...
```
