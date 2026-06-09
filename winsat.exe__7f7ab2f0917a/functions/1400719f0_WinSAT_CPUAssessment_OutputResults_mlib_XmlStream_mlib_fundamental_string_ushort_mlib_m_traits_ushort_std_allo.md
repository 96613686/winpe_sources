# WinSAT::CPUAssessment::OutputResults(mlib::XmlStream &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400719f0`
- end: `0x14007406a`
- name: `?OutputResults@CPUAssessment@WinSAT@@UEBAJAEAVXmlStream@mlib@@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@4@@Z`
- size: `9850`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140001abc`
- `0x140004348`
- `0x14000449c`
- `0x140005b80`
- `0x140005d78`
- `0x140005f4c`
- `0x14000695c`
- `0x140007e3c`
- `0x140007f14`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x1400086f8`
- `0x140008730`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140016264`
- `0x140016d04`
- `0x140017af0`
- `0x14002093c`
- `0x14004fce4`
- `0x14004fe00`
- `0x1400530a8`
- `0x140056f94`
- `0x140058be8`
- `0x14005c1f0`
- `0x14005ca70`
- `0x1400603d4`
- `0x1400719f0`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140071b39`
- `KERNEL32!GetLastError` at `0x140071b39`
- `KERNEL32!GetExitCodeThread` at `0x140071a90`
- `KERNEL32!GetExitCodeThread` at `0x140071a90`

## string_xrefs

- `0x14007253c`: `NumThreads`
- `0x1400725b3`: `NumThreads`
- `0x140071ce7`: `CPU-Compression2`
- `0x140071ce0`: `CPU-Compression`
- `0x140072441`: `MaxThreads`
- `0x1400724cc`: `MaxThreads`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
__int64 __fastcall WinSAT::CPUAssessment::OutputResults(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned int v6; // r15d
  char v7; // bl
  unsigned int i; // r14d
  __int64 v9; // rax
  __int64 v10; // rbx
  const unsigned __int16 *v11; // rax
  __int64 *v12; // rax
  __int64 *v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 *v16; // rax
  unsigned __int16 v17; // r9
  const unsigned __int16 *v18; // rax
  __int64 *v19; // rax
  __int64 *v20; // rax
  __int64 *v21; // rax
  __int64 v22; // rbx
  unsigned __int16 v23; // r9
  const unsigned __int16 *v24; // rax
  __int64 *v25; // rax
  __int64 *v26; // rax
  __int64 *v27; // rax
  mlib::MUILoader *v28; // rax
  double v29; // xmm6_8
  double v30; // xmm7_8
  __int64 v31; // r8
  unsigned __int64 v32; // r12
  unsigned int v33; // ebx
  _QWORD *v34; // r14
  __int64 v35; // rcx
  unsigned __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // rax
  const wchar_t *v39; // rdx
  __int64 v40; // rax
  __int64 *v41; // rax
  __int64 v42; // rax
  __int64 *v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  void **v46; // r9
  __int64 *v47; // rax
  __int64 *v48; // rax
  __int64 *v49; // rax
  __int64 *v50; // rax
  __int64 *v51; // rax
  __int64 *v52; // rax
  __int64 *v53; // rax
  const wchar_t *v54; // rdx
  __int64 *v55; // rcx
  __int64 *v56; // rax
  __int64 *v57; // rax
  __int64 *v58; // rax
  __int64 *v59; // rax
  __int64 *v60; // rax
  __int64 *v61; // rax
  __int64 *v62; // rax
  __int64 *v63; // rax
  const wchar_t *v64; // rdx
  __int64 *v65; // rcx
  __int64 *v66; // rax
  __int64 *v67; // rax
  __int64 *v68; // rax
  __int64 *v69; // rax
  __int64 *v70; // rax
  __int64 *v71; // rax
  __int64 *v72; // rax
  __int64 *v73; // rax
  const wchar_t *v74; // rdx
  __int64 *v75; // rcx
  __int64 *v76; // rax
  __int64 *v77; // rax
  const wchar_t *v78; // rbx
  const wchar_t *v79; // rdx
  __int64 *v80; // rcx
  __int64 *v81; // rax
  __int64 *v82; // rax
  int v83; // ebx
  const wchar_t *v84; // rdx
  __int64 *v85; // rcx
  __int64 *v86; // rax
  __int64 *v87; // rax
  __int64 *v88; // rax
  __int64 *v89; // rax
  int v90; // ebx
  const wchar_t *v91; // rdx
  __int64 *v92; // rcx
  __int64 *v93; // rax
  __int64 *v94; // rax
  __int64 *v95; // rax
  __int64 *v96; // rax
  __int64 *v97; // rdx
  __int64 v98; // rcx
  __int64 *v99; // r8
  __int64 v100; // rcx
  const wchar_t *v101; // rdx
  __int64 *v102; // rcx
  __int64 *v103; // rax
  __int64 *v104; // rax
  __int64 *v105; // rax
  __int64 *v106; // rax
  __int64 *v107; // rdx
  __int64 v108; // rcx
  __int64 *v109; // r8
  __int64 v110; // rcx
  const wchar_t *v111; // rdx
  __int64 *v112; // rcx
  __int64 *v113; // rax
  __int64 *v114; // rax
  int v115; // ebx
  unsigned __int64 *v116; // rax
  DWORD v117; // r8d
  double v118; // xmm11_8
  unsigned __int64 v119; // rcx
  double v120; // xmm10_8
  __int64 v121; // r13
  _QWORD *v122; // r14
  __int64 v123; // rcx
  double v124; // xmm0_8
  __int64 v125; // rax
  double v126; // xmm6_8
  __int64 v127; // rcx
  double v128; // xmm0_8
  __int64 v129; // rax
  double v130; // xmm7_8
  __int64 v131; // rcx
  double v132; // xmm0_8
  __int64 v133; // rax
  double v134; // xmm8_8
  __int64 v135; // rcx
  double v136; // xmm0_8
  __int64 v137; // rax
  __int64 *v138; // rax
  __int64 *v139; // rax
  __int64 *v140; // rax
  __int64 *v141; // rax
  __int64 v142; // rbx
  __int64 *v143; // rax
  __int64 *v144; // rax
  __int64 *v145; // rax
  __int64 *v146; // rdx
  __int64 v147; // rcx
  __int64 *v148; // rdx
  __int64 v149; // rcx
  const wchar_t *v150; // rdx
  __int64 *v151; // rcx
  __int64 *v152; // rax
  __int64 *v153; // rax
  __int64 *v154; // rax
  __int64 *v155; // rax
  __int64 *v156; // rax
  __int64 *v157; // rax
  __int64 *v158; // rdx
  __int64 v159; // rcx
  __int64 *v160; // rdx
  __int64 v161; // rcx
  const wchar_t *v162; // rdx
  __int64 *v163; // rcx
  __int64 *v164; // rax
  __int64 *v165; // rax
  __int64 *v166; // rax
  __int64 *v167; // rax
  __int64 *v168; // rdx
  __int64 v169; // rcx
  __int64 *v170; // rdx
  __int64 v171; // rcx
  const wchar_t *v172; // rdx
  __int64 *v173; // rcx
  __int64 *v174; // rax
  __int64 *v175; // rax
  __int64 *v176; // rax
  __int64 *v177; // rax
  __int64 *v178; // rdx
  __int64 v179; // rcx
  __int64 *v180; // rdx
  __int64 v181; // rcx
  const wchar_t *v182; // rdx
  __int64 *v183; // rcx
  __int64 *v184; // rax
  __int64 *v185; // rax
  __int64 *v186; // rax
  __int64 *v187; // rax
  __int64 *v188; // rax
  __int64 *v189; // rax
  __int64 v190; // rdx
  double v191; // xmm6_8
  unsigned __int64 v192; // rbx
  __int64 *v193; // rdx
  __int64 v194; // rcx
  const wchar_t *v195; // rdx
  __int64 *v196; // rcx
  __int64 *v197; // rax
  __int64 *v198; // rax
  __int64 *v199; // rax
  __int64 *v200; // rax
  __int64 *v201; // rax
  __int64 *v202; // rax
  __int64 v203; // rdx
  double v204; // xmm6_8
  unsigned __int64 v205; // rbx
  __int64 *v206; // rdx
  __int64 v207; // rcx
  const wchar_t *v208; // rdx
  __int64 *v209; // rcx
  __int64 *v210; // rax
  __int64 *v211; // rax
  __int64 *v212; // rax
  __int64 *v213; // rax
  __int64 *v214; // rax
  __int64 *v215; // rax
  __int64 v216; // rdx
  double v217; // xmm6_8
  __int64 v218; // rbx
  __int64 *v219; // rdx
  __int64 v220; // rcx
  const wchar_t *v221; // rdx
  __int64 *v222; // rcx
  __int64 *v223; // rax
  __int64 *v224; // rax
  const wchar_t *v225; // rdx
  __int64 *v226; // rcx
  __int64 *v227; // rax
  const wchar_t *v228; // rdx
  __int64 *v229; // rcx
  __int64 *v230; // rax
  const wchar_t *v231; // rdx
  __int64 *v232; // rcx
  __int64 *v233; // rax
  DWORD ExitCode[2]; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 *v236; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int64 *v237; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v238; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int64 *v239; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 *v240; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int64 *v241; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 *v242; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 *v243; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 *v244; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 *v245; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 *v246; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 *v247; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 *v248; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 *v249; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 *v250; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int64 *v251; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 *v252; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int64 *v253; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 *v254; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int64 *v255; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 *v256; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int64 *v257; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 *v258; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int64 *v259; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 *v260; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int64 *v261; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int64 *v262; // [rsp+110h] [rbp+8h] BYREF
  unsigned __int64 *v263; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int64 *v264; // [rsp+120h] [rbp+18h] BYREF
  unsigned __int64 *v265; // [rsp+128h] [rbp+20h] BYREF
  unsigned int v266; // [rsp+130h] [rbp+28h]
  unsigned __int64 *v267; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int64 *v268; // [rsp+140h] [rbp+38h] BYREF
  void *Block[2]; // [rsp+148h] [rbp+40h] BYREF
  __int64 v270; // [rsp+158h] [rbp+50h]
  __int64 v271[30]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v272[112]; // [rsp+268h] [rbp+160h] BYREF
  WCHAR Buffer[256]; // [rsp+2D8h] [rbp+1D0h] BYREF
  DWORD LastError; // [rsp+4D8h] [rbp+3D0h]
  char v275; // [rsp+4DCh] [rbp+3D4h]
  __int64 v276; // [rsp+4E0h] [rbp+3D8h]

  if ( *(_BYTE *)(a1 + 8296) )
    return (unsigned int)-2147221503;
  v7 = 1;
  for ( i = 0; ; ++i )
  {
    v9 = *(unsigned int *)(a1 + 8300);
    if ( i >= (unsigned int)v9 )
      break;
    ExitCode[0] = 0;
    if ( !GetExitCodeThread(*(HANDLE *)(*(_QWORD *)(a1 + 8LL * i + 104) + 816LL), ExitCode) )
    {
      LastError = GetLastError();
      v275 = 1;
      v276 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v271,
        a3);
      v18 = mlib::MUIStr_((mlib *)"base\\winsat\\cpu\\cpuat.cpp", (const char *)0x278, 524, v17);
      v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v271, (__int64)v18);
      v20 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v19, 10);
      v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, (__int64)Buffer);
      std::endl(v21);
      v22 = *(_QWORD *)(a1 + 24);
      v24 = mlib::MUIStr_((mlib *)"base\\winsat\\cpu\\cpuat.cpp", (const char *)0x27A, 524, v23);
      v25 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v22 + 240), (__int64)v24);
      v26 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v25, 10);
      v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, (__int64)Buffer);
      std::endl(v27);
      v6 = -2147221503;
      mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v271);
      return v6;
    }
    if ( ExitCode[0] )
    {
      LastError = ExitCode[0];
      v275 = 1;
      v276 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v10 = *(_QWORD *)(a1 + 24);
      v11 = mlib::MUISpf_((mlib *)"base\\winsat\\cpu\\cpuat.cpp", (const char *)0x284, 525, i);
      v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v10 + 240), (__int64)v11);
      v13 = (__int64 *)std::endl(v12);
      v14 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v13,
              (unsigned __int64 **)(*(_QWORD *)(a1 + 8LL * i + 104) + 104LL));
      v15 = (__int64 *)std::endl(v14);
      v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, (__int64)Buffer);
      std::endl(v16);
      v7 = 0;
    }
  }
  if ( !v7 )
  {
    v28 = mlib::MUILoader::MUILoader((mlib::MUILoader *)Block, 526);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator=(
      a3,
      (__int64)v28);
    return (unsigned int)-2147221503;
  }
  v6 = 0;
  v266 = 0;
  *(_DWORD *)(a1 + 56) = 6;
  v29 = 0.0;
  v30 = 0.0;
  *(_OWORD *)Block = 0;
  v270 = 0;
  v237 = 0;
  std::vector<SampleManager const *>::resize(Block, v9, &v237);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v238,
    64);
  v32 = -1;
  v33 = 0;
  if ( *(_DWORD *)(a1 + 8300) )
  {
    v34 = Block[0];
    while ( 1 )
    {
      v35 = *(_QWORD *)(a1 + 8LL * v33 + 104);
      v36 = *(_QWORD *)(v35 + 792);
      if ( v32 < v36 )
        v36 = v32;
      v32 = v36;
      v34[v33] = v35 + 648;
      v37 = *(_DWORD *)(a1 + 8428);
      if ( (unsigned int)(v37 - 1) <= 2 )
        break;
      if ( (unsigned int)(v37 - 4) <= 1 )
      {
        v38 = *(_QWORD *)(a1 + 8LL * v33 + 104);
        v29 = v29 + *(double *)(v38 + 824);
        v30 = v30 + *(double *)(v38 + 832);
        v39 = L"CPU-Compression2";
        if ( v37 != 5 )
          v39 = L"CPU-Compression";
LABEL_25:
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
          (__int64)&v238,
          (__int64)v39,
          v31);
      }
      if ( ++v33 >= *(_DWORD *)(a1 + 8300) )
        goto LABEL_27;
    }
    v40 = *(_QWORD *)(a1 + 8LL * v33 + 104);
    v29 = v29 + *(double *)(v40 + 824);
    v30 = v30 + *(double *)(v40 + 832);
    if ( v37 == 2 )
    {
      v39 = L"CPU-Encryption2";
    }
    else
    {
      v39 = L"CPU-CRC32";
      if ( v37 != 3 )
        v39 = L"CPU-Encryption";
    }
    goto LABEL_25;
  }
LABEL_27:
  if ( *(_BYTE *)(a1 + 8297) )
  {
    v41 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*(_QWORD *)(a1 + 16) + 240LL),
            (__int64)L"> Total BytesPerSecond        = ");
    *(_DWORD *)((char *)v41 + *(int *)(*v41 + 4) + 24) |= 0x2080u;
    *(__int64 *)((char *)v41 + *(int *)(*v41 + 4) + 32) = 0;
    *(__int64 *)((char *)v41 + *(int *)(*v41 + 4) + 40) = 10;
    v42 = std::basic_ostream<unsigned short>::operator<<((__int64)v41, v29);
    std::endl(v42);
    if ( *(_BYTE *)(a1 + 8297) )
    {
      v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              (__int64 *)(*(_QWORD *)(a1 + 16) + 240LL),
              (__int64)L"> Total BytesPerSecond (mean) = ");
      *(_DWORD *)((char *)v43 + *(int *)(*v43 + 4) + 24) |= 0x2080u;
      *(__int64 *)((char *)v43 + *(int *)(*v43 + 4) + 32) = 0;
      *(__int64 *)((char *)v43 + *(int *)(*v43 + 4) + 40) = 10;
      v44 = std::basic_ostream<unsigned short>::operator<<((__int64)v43, v30);
      std::endl(v44);
    }
  }
  if ( *(_WORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40)
                + 498) )
  {
    *(_QWORD *)ExitCode = 0;
    v45 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40);
    KeyInfo::GenDumpFileName(v45, &v236, &v238);
    if ( !mlib::MCreateFile((LPCWSTR)v236[3], (const unsigned __int16 *)0x22, ExitCode, v46) )
    {
      mlib::handle_ostreamT<char,std::char_traits<char>>::handle_ostreamT<char,std::char_traits<char>>(
        v271,
        *(_QWORD *)ExitCode);
      SampleManager::DumpSamples(Block, v272);
      mlib::handle_ostreamT<char,std::char_traits<char>>::`vbase destructor'(v271);
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v236);
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v264,
    L"Units");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v47 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v47, &v264);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v263,
    L"name");
  *((_DWORD *)a2 + 2) = 3;
  v48 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v49 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v48, &v263);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v49, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v262,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  v50 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v51 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v50, &v262);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v51, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"B/s");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v261,
    L"descrip");
  *((_DWORD *)a2 + 2) = 3;
  v52 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v53 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v52, &v261);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v53, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes per second");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v260,
    L"Units");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v56 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v55 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v56, &v260);
    v54 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_43;
    v54 = L"/>";
    v55 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, (__int64)v54);
LABEL_43:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v259,
    L"Units");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v57 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v57, &v259);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v258,
    L"name");
  *((_DWORD *)a2 + 2) = 3;
  v58 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v59 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v58, &v258);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v59, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v257,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  v60 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v61 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v60, &v257);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v61, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v256,
    L"descrip");
  *((_DWORD *)a2 + 2) = 3;
  v62 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v63 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v62, &v256);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v63, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v255,
    L"Units");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v65 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v66, &v255);
    v64 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_52;
    v64 = L"/>";
    v65 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, (__int64)v64);
LABEL_52:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v254,
    L"Units");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v67 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v67, &v254);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v253,
    L"name");
  *((_DWORD *)a2 + 2) = 3;
  v68 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v69 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v68, &v253);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v69, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"ticks");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v252,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  v70 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v71 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v70, &v252);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v71, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"ticks");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v251,
    L"descrip");
  *((_DWORD *)a2 + 2) = 3;
  v72 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v73 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v72, &v251);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v73, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"cpu clock ticks");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v250,
    L"Units");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v76 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v75 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v76, &v250);
    v74 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_61;
    v74 = L"/>";
    v75 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v75, (__int64)v74);
LABEL_61:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v249,
    L"MaxThreads");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v77 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v77, &v249);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  v78 = L"1";
  if ( !*(_BYTE *)(a1 + 8336) )
    v78 = L"NumberOfSchedulableUnits";
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)v78);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v248,
    L"MaxThreads");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v81 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v80 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v81, &v248);
    v79 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_72;
    v79 = L"/>";
    v80 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v80, (__int64)v79);
LABEL_72:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v247,
    L"NumThreads");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v82 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v82, &v247);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  v83 = *(_DWORD *)(a1 + 8300);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2, v83);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v246,
    L"NumThreads");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v86 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v85 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v86, &v246);
    v84 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_81;
    v84 = L"/>";
    v85 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, (__int64)v84);
LABEL_81:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v245,
    L"WorkingBufferSize");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v87 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v87, &v245);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v244,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  v88 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v89 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v88, &v244);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v89, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  v90 = *(_DWORD *)(a1 + 8424);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2, v90);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v243,
    L"WorkingBufferSize");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v93 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v92 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v93, &v243);
    v91 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_90;
    v91 = L"/>";
    v92 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v92, (__int64)v91);
LABEL_90:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v242,
    L"TotalBytesPerSecond");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v94 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v94, &v242);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v241,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  v95 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v96 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v95, &v241);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v96, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  v97 = (__int64 *)*a2;
  v98 = *(int *)(*(_QWORD *)*a2 + 4LL);
  *(_DWORD *)((char *)v97 + v98 + 24) |= 0x2080u;
  *(__int64 *)((char *)v97 + *(int *)(*v97 + 4) + 32) = 5;
  *(__int64 *)((char *)v97 + *(int *)(*v97 + 4) + 40) = 0;
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2, v29);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  v99 = (__int64 *)*a2;
  v100 = *(int *)(*(_QWORD *)*a2 + 4LL);
  *(_DWORD *)((char *)v99 + v100 + 24) |= 0x201u;
  *(_WORD *)((char *)v99 + *(int *)(*v99 + 4) + 88) = 32;
  *(__int64 *)((char *)v99 + *(int *)(*v99 + 4) + 40) = 0;
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v240,
    L"TotalBytesPerSecond");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v103 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v102 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v103, &v240);
    v101 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_99;
    v101 = L"/>";
    v102 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v102, (__int64)v101);
LABEL_99:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v239,
    L"TotalBytesPerSecondMean");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v104 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v104, &v239);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    ExitCode,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  v105 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v106 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
           v105,
           (unsigned __int64 **)ExitCode);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v106, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  v107 = (__int64 *)*a2;
  v108 = *(int *)(*(_QWORD *)*a2 + 4LL);
  *(_DWORD *)((char *)v107 + v108 + 24) |= 0x2080u;
  *(__int64 *)((char *)v107 + *(int *)(*v107 + 4) + 32) = 5;
  *(__int64 *)((char *)v107 + *(int *)(*v107 + 4) + 40) = 0;
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2, v30);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  v109 = (__int64 *)*a2;
  v110 = *(int *)(*(_QWORD *)*a2 + 4LL);
  *(_DWORD *)((char *)v109 + v110 + 24) |= 0x201u;
  *(_WORD *)((char *)v109 + *(int *)(*v109 + 4) + 88) = 32;
  *(__int64 *)((char *)v109 + *(int *)(*v109 + 4) + 40) = 0;
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v236,
    L"TotalBytesPerSecondMean");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v113 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v112 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v113, &v236);
    v111 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_108;
    v111 = L"/>";
    v112 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v112, (__int64)v111);
LABEL_108:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v236);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(ExitCode);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v239);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v240);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v241);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v242);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v243);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v244);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v245);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v246);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v247);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v248);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v249);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v250);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v251);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v252);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v253);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v254);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v255);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v256);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v257);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v258);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v259);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v261);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v262);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v263);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v264);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v265,
    L"PerCPUData");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v114 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v114, &v265);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v265);
  v115 = *(_DWORD *)(a1 + 8424);
  v116 = (unsigned __int64 *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40);
  if ( *(_DWORD *)(a1 + 8300) )
  {
    v117 = 0;
    ExitCode[0] = 0;
    v118 = (double)(2 * v115);
    v119 = *v116;
    if ( (*v116 & 0x8000000000000000uLL) != 0LL )
      v120 = (double)(int)(v119 & 1 | (v119 >> 1)) + (double)(int)(v119 & 1 | (v119 >> 1));
    else
      v120 = (double)(int)v119;
    while ( 1 )
    {
      v121 = v117;
      v122 = *(_QWORD **)(a1 + 8LL * v117 + 104);
      v123 = v122[87];
      if ( v123 < 0 )
      {
        v125 = v122[87] & 1LL | ((unsigned __int64)v123 >> 1);
        v124 = (double)(int)v125 + (double)(int)v125;
      }
      else
      {
        v124 = (double)(int)v123;
      }
      v126 = v118 / (v124 / v120);
      v127 = v122[88];
      if ( v127 < 0 )
      {
        v129 = v122[88] & 1LL | ((unsigned __int64)v127 >> 1);
        v128 = (double)(int)v129 + (double)(int)v129;
      }
      else
      {
        v128 = (double)(int)v127;
      }
      v130 = v118 / (v128 / v120);
      v131 = v122[85];
      if ( v131 < 0 )
      {
        v133 = v122[85] & 1LL | ((unsigned __int64)v131 >> 1);
        v132 = (double)(int)v133 + (double)(int)v133;
      }
      else
      {
        v132 = (double)(int)v131;
      }
      v134 = v118 / (v132 / v120);
      v135 = v122[86];
      if ( v135 < 0 )
      {
        v137 = v122[86] & 1LL | ((unsigned __int64)v135 >> 1);
        v136 = (double)(int)v137 + (double)(int)v137;
      }
      else
      {
        v136 = (double)(int)v135;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v236,
        L"CPUData");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v138 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v138, &v236);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v239,
        L"CPUIndex");
      *((_DWORD *)a2 + 2) = 3;
      v139 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v140 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v139, &v239);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v140, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, ExitCode[0]);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v240,
        L"Repetitions");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v141 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v141, &v240);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      v142 = (__int64)(v122[82] - v122[81]) >> 3;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v142);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v241,
        L"Repetitions");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v152 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v153 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v152,
                 &v241);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v153, (__int64)L">");
      }
      else if ( *((_DWORD *)a2 + 2) == 2 )
      {
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"/>");
      }
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v242,
        L"Min");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v143 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v143, &v242);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v243,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v144 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v145 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v144, &v243);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v146 = (__int64 *)*a2;
      v147 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v146 + v147 + 24) |= 0x2080u;
      *(__int64 *)((char *)v146 + *(int *)(*v146 + 4) + 32) = 5;
      *(__int64 *)((char *)v146 + *(int *)(*v146 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v126);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v148 = (__int64 *)*a2;
      v149 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v148 + v149 + 24) |= 0x201u;
      *(_WORD *)((char *)v148 + *(int *)(*v148 + 4) + 88) = 32;
      *(__int64 *)((char *)v148 + *(int *)(*v148 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v244,
        L"Min");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v154 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v151 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v154,
                 &v244);
        v150 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_145;
        v150 = L"/>";
        v151 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v151, (__int64)v150);
LABEL_145:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v245,
        L"Max");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v155 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v155, &v245);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v246,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v156 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v157 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v156, &v246);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v157, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v158 = (__int64 *)*a2;
      v159 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v158 + v159 + 24) |= 0x2080u;
      *(__int64 *)((char *)v158 + *(int *)(*v158 + 4) + 32) = 5;
      *(__int64 *)((char *)v158 + *(int *)(*v158 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v130);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v160 = (__int64 *)*a2;
      v161 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v160 + v161 + 24) |= 0x201u;
      *(_WORD *)((char *)v160 + *(int *)(*v160 + 4) + 88) = 32;
      *(__int64 *)((char *)v160 + *(int *)(*v160 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v247,
        L"Max");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v164 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v163 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v164,
                 &v247);
        v162 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_154;
        v162 = L"/>";
        v163 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v163, (__int64)v162);
LABEL_154:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v248,
        L"Median");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v165 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v165, &v248);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v249,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v166 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v167 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v166, &v249);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v167, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v168 = (__int64 *)*a2;
      v169 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v168 + v169 + 24) |= 0x2080u;
      *(__int64 *)((char *)v168 + *(int *)(*v168 + 4) + 32) = 5;
      *(__int64 *)((char *)v168 + *(int *)(*v168 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v134);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v170 = (__int64 *)*a2;
      v171 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v170 + v171 + 24) |= 0x201u;
      *(_WORD *)((char *)v170 + *(int *)(*v170 + 4) + 88) = 32;
      *(__int64 *)((char *)v170 + *(int *)(*v170 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v250,
        L"Median");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v174 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v173 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v174,
                 &v250);
        v172 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_163;
        v172 = L"/>";
        v173 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v173, (__int64)v172);
LABEL_163:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v251,
        L"Mean");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v175 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v175, &v251);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v252,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v176 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v177 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v176, &v252);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v177, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v178 = (__int64 *)*a2;
      v179 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v178 + v179 + 24) |= 0x2080u;
      *(__int64 *)((char *)v178 + *(int *)(*v178 + 4) + 32) = 5;
      *(__int64 *)((char *)v178 + *(int *)(*v178 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v118 / (v136 / v120));
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v180 = (__int64 *)*a2;
      v181 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v180 + v181 + 24) |= 0x201u;
      *(_WORD *)((char *)v180 + *(int *)(*v180 + 4) + 88) = 32;
      *(__int64 *)((char *)v180 + *(int *)(*v180 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v253,
        L"Mean");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v184 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v183 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v184,
                 &v253);
        v182 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_172;
        v182 = L"/>";
        v183 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v183, (__int64)v182);
LABEL_172:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v254,
        L"StartTick");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v185 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v185, &v254);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v255,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v186 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v187 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v186, &v255);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v187, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"ticks");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v256,
        L"microseconds");
      *((_DWORD *)a2 + 2) = 3;
      v188 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v189 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v188, &v256);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v189, (__int64)L"=");
      v190 = 1000000 * (*(_QWORD *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 792LL) - v32);
      if ( v190 < 0 )
        v191 = (double)(int)(v190 & 1 | ((unsigned __int64)v190 >> 1))
             + (double)(int)(v190 & 1 | ((unsigned __int64)v190 >> 1));
      else
        v191 = (double)(int)v190;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v191 / v120);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v192 = *(_QWORD *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 792LL) - v32;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v192);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v193 = (__int64 *)*a2;
      v194 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v193 + v194 + 24) |= 0x201u;
      *(_WORD *)((char *)v193 + *(int *)(*v193 + 4) + 88) = 32;
      *(__int64 *)((char *)v193 + *(int *)(*v193 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v257,
        L"StartTick");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v197 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v196 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v197,
                 &v257);
        v195 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_184;
        v195 = L"/>";
        v196 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v196, (__int64)v195);
LABEL_184:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v258,
        L"EndTick");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v198 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v198, &v258);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v259,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v199 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v200 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v199, &v259);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v200, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"ticks");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v260,
        L"microseconds");
      *((_DWORD *)a2 + 2) = 3;
      v201 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v202 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v201, &v260);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v202, (__int64)L"=");
      v203 = 1000000 * (*(_QWORD *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 800LL) - v32);
      if ( v203 < 0 )
        v204 = (double)(int)((unsigned __int64)v203 >> 1) + (double)(int)((unsigned __int64)v203 >> 1);
      else
        v204 = (double)(int)v203;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v204 / v120);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v205 = *(_QWORD *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 800LL) - v32;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v205);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v206 = (__int64 *)*a2;
      v207 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v206 + v207 + 24) |= 0x201u;
      *(_WORD *)((char *)v206 + *(int *)(*v206 + 4) + 88) = 32;
      *(__int64 *)((char *)v206 + *(int *)(*v206 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v261,
        L"EndTick");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v210 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v209 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v210,
                 &v261);
        v208 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_196;
        v208 = L"/>";
        v209 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v209, (__int64)v208);
LABEL_196:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v262,
        L"Duration");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v211 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v211, &v262);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v263,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v212 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v213 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v212, &v263);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v213, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"ticks");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v264,
        L"microseconds");
      *((_DWORD *)a2 + 2) = 3;
      v214 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v215 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v214, &v264);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v215, (__int64)L"=");
      v216 = 1000000LL
           * (*(_QWORD *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 800LL)
            - *(_QWORD *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 792LL));
      if ( v216 < 0 )
        v217 = (double)(int)((unsigned __int64)v216 >> 1) + (double)(int)((unsigned __int64)v216 >> 1);
      else
        v217 = (double)(int)v216;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v217 / v120);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v218 = *(_QWORD *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 800LL)
           - *(_QWORD *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 792LL);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v218);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v219 = (__int64 *)*a2;
      v220 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v219 + v220 + 24) |= 0x201u;
      *(_WORD *)((char *)v219 + *(int *)(*v219 + 4) + 88) = 32;
      *(__int64 *)((char *)v219 + *(int *)(*v219 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v265,
        L"Duration");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v223 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v222 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v223,
                 &v265);
        v221 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_208;
        v221 = L"/>";
        v222 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v222, (__int64)v221);
LABEL_208:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v265);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v264);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v263);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v262);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v261);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v260);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v259);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v258);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v257);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v256);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v255);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v254);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v253);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v252);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v251);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v250);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v249);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v248);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v247);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v246);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v245);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v244);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v243);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v242);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v241);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v240);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v239);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v236);
      if ( !*(_BYTE *)(*(_QWORD *)(a1 + 8 * v121 + 104) + 808LL) )
        goto LABEL_219;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v268,
        L"RDTSCDeltaViolation");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v224 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v224, &v268);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v267,
        L"RDTSCDeltaViolation");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v227 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v226 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v227,
                 &v267);
        v225 = L">";
        goto LABEL_217;
      }
      if ( *((_DWORD *)a2 + 2) == 2 )
      {
        v225 = L"/>";
        v226 = (__int64 *)*a2;
LABEL_217:
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v226, (__int64)v225);
      }
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v267);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v268);
LABEL_219:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v237,
        L"CPUData");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v230 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v229 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v230,
                 &v237);
        v228 = L">";
        goto LABEL_225;
      }
      if ( *((_DWORD *)a2 + 2) == 2 )
      {
        v228 = L"/>";
        v229 = (__int64 *)*a2;
LABEL_225:
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v229, (__int64)v228);
      }
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v237);
      v117 = ExitCode[0] + 1;
      ExitCode[0] = v117;
      if ( v117 >= *(_DWORD *)(a1 + 8300) )
      {
        v6 = v266;
        break;
      }
    }
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v237,
    L"PerCPUData");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v233 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v232 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v233, &v237);
    v231 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_235;
    v231 = L"/>";
    v232 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v232, (__int64)v231);
LABEL_235:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v237);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v238);
  if ( Block[0] )
    operator delete(Block[0]);
  return v6;
}

```

## disassembly

```asm
0x1400719f0  mov     rax, rsp
0x1400719f3  mov     [rax+20h], rbx
0x1400719f7  push    rbp
0x1400719f8  push    rsi
0x1400719f9  push    rdi
0x1400719fa  push    r12
0x1400719fc  push    r13
0x1400719fe  push    r14
0x140071a00  push    r15
0x140071a02  lea     rbp, [rax-488h]
0x140071a09  sub     rsp, 550h
0x140071a10  movaps  xmmword ptr [rax-48h], xmm6
0x140071a14  movaps  xmmword ptr [rax-58h], xmm7
0x140071a18  movaps  xmmword ptr [rax-68h], xmm8
0x140071a1d  movaps  xmmword ptr [rax-78h], xmm9
0x140071a22  movaps  xmmword ptr [rax-88h], xmm10
0x140071a2a  movaps  xmmword ptr [rax-98h], xmm11
0x140071a32  mov     rax, cs:__security_cookie
0x140071a39  xor     rax, rsp
0x140071a3c  mov     [rbp+480h+var_A0], rax
0x140071a43  mov     r12, r8
0x140071a46  mov     rdi, rdx
0x140071a49  mov     rsi, rcx
0x140071a4c  xor     r13d, r13d
0x140071a4f  cmp     [rcx+2068h], r13b
0x140071a56  jz      short loc_140071A63
0x140071a58  mov     r15d, 80040001h
0x140071a5e  jmp     loc_14007401F
0x140071a63  mov     bl, 1
0x140071a65  mov     r14d, r13d
0x140071a68  mov     eax, [rsi+206Ch]
0x140071a6e  cmp     r14d, eax
0x140071a71  jnb     loc_140071C12
0x140071a77  mov     [rsp+580h+ExitCode], r13d
0x140071a7c  mov     r15d, r14d
0x140071a7f  mov     rcx, [rsi+r15*8+68h]
0x140071a84  lea     rdx, [rsp+580h+ExitCode]; lpExitCode
0x140071a89  mov     rcx, [rcx+330h]; hThread
0x140071a90  call    cs:__imp_GetExitCodeThread
0x140071a96  test    eax, eax
0x140071a98  jz      loc_140071B39
0x140071a9e  mov     eax, [rsp+580h+ExitCode]
0x140071aa2  test    eax, eax
0x140071aa4  jz      loc_140071B31
0x140071aaa  mov     [rbp+480h+var_B0], eax
0x140071ab0  mov     [rbp+480h+var_AC], 1
0x140071ab7  mov     [rbp+480h+var_A8], r13
0x140071abe  lea     rcx, [rbp+480h+Buffer]; lpBuffer
0x140071ac5  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140071aca  mov     rbx, [rsi+18h]
0x140071ace  mov     r8d, 20Dh; int
0x140071ad4  mov     r9d, r14d; unsigned __int16
0x140071ad7  lea     edx, [r8+77h]; char *
0x140071adb  lea     rcx, aBaseWinsatCpuC; "base\\winsat\\cpu\\cpuat.cpp"
0x140071ae2  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x140071ae7  mov     rdx, rax
0x140071aea  lea     rcx, [rbx+0F0h]
0x140071af1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071af6  mov     rcx, rax
0x140071af9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071afe  mov     rdx, [rsi+r15*8+68h]
0x140071b03  add     rdx, 68h ; 'h'
0x140071b07  mov     rcx, rax
0x140071b0a  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140071b0f  mov     rcx, rax
0x140071b12  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071b17  lea     rdx, [rbp+480h+Buffer]
0x140071b1e  mov     rcx, rax
0x140071b21  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071b26  mov     rcx, rax
0x140071b29  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071b2e  mov     bl, r13b
0x140071b31  inc     r14d
0x140071b34  jmp     loc_140071A68
0x140071b39  call    cs:__imp_GetLastError
0x140071b3f  mov     [rbp+480h+var_B0], eax
0x140071b45  mov     [rbp+480h+var_AC], 1
0x140071b4c  mov     [rbp+480h+var_A8], r13
0x140071b53  lea     rcx, [rbp+480h+Buffer]; lpBuffer
0x140071b5a  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140071b5f  mov     rdx, r12
0x140071b62  lea     rcx, [rbp+480h+var_410]
0x140071b66  call    ??0?$fundamental_ostringstream@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@V?$allocator@G@2@@mlib@@QEAA@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x140071b6b  nop
0x140071b6c  mov     edi, 20Ch
0x140071b71  mov     r8d, edi; int
0x140071b74  lea     edx, [rdi+6Ch]; char *
0x140071b77  lea     rcx, aBaseWinsatCpuC; "base\\winsat\\cpu\\cpuat.cpp"
0x140071b7e  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140071b83  mov     rdx, rax
0x140071b86  lea     rcx, [rbp+480h+var_410]
0x140071b8a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071b8f  mov     r14d, 0Ah
0x140071b95  mov     edx, r14d
0x140071b98  mov     rcx, rax
0x140071b9b  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140071ba0  lea     rdx, [rbp+480h+Buffer]
0x140071ba7  mov     rcx, rax
0x140071baa  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071baf  mov     rcx, rax
0x140071bb2  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071bb7  mov     rbx, [rsi+18h]
0x140071bbb  mov     r8d, edi; int
0x140071bbe  lea     edx, [rdi+6Eh]; char *
0x140071bc1  lea     rcx, aBaseWinsatCpuC; "base\\winsat\\cpu\\cpuat.cpp"
0x140071bc8  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140071bcd  mov     rdx, rax
0x140071bd0  lea     rcx, [rbx+0F0h]
0x140071bd7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071bdc  mov     edx, r14d
0x140071bdf  mov     rcx, rax
0x140071be2  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140071be7  lea     rdx, [rbp+480h+Buffer]
0x140071bee  mov     rcx, rax
0x140071bf1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071bf6  mov     rcx, rax
0x140071bf9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071bfe  mov     r15d, 80040001h
0x140071c04  lea     rcx, [rbp+480h+var_410]
0x140071c08  call    ??_D?$fundamental_ostringstream@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@V?$allocator@G@2@@mlib@@QEAAXXZ; mlib::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x140071c0d  jmp     loc_14007401F
0x140071c12  test    bl, bl
0x140071c14  jnz     short loc_140071C34
0x140071c16  mov     edx, 20Eh; unsigned __int16
0x140071c1b  lea     rcx, [rbp+480h+Block]; this
0x140071c1f  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x140071c24  mov     rdx, rax
0x140071c27  mov     rcx, r12
0x140071c2a  call    ??4?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV01@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator=(mlib::MSInitializer const &)
0x140071c2f  jmp     loc_140071A58
0x140071c34  mov     r15d, r13d
0x140071c37  mov     [rbp+480h+var_458], r13d
0x140071c3b  mov     dword ptr [rsi+38h], 6
0x140071c42  xorps   xmm6, xmm6
0x140071c45  xorps   xmm7, xmm7
0x140071c48  xorps   xmm0, xmm0
0x140071c4b  movdqu  xmmword ptr [rbp+480h+Block], xmm0
0x140071c50  mov     [rbp+480h+var_430], r13
0x140071c54  mov     [rsp+580h+var_540], r13
0x140071c59  mov     rdx, rax
0x140071c5c  lea     r8, [rsp+580h+var_540]
0x140071c61  lea     rcx, [rbp+480h+Block]
0x140071c65  call    ?resize@?$vector@PEBVSampleManager@@V?$allocator@PEBVSampleManager@@@std@@@std@@QEAAX_KAEBQEBVSampleManager@@@Z; std::vector<SampleManager const *>::resize(unsigned __int64,SampleManager const * const &)
0x140071c6a  mov     edx, 40h ; '@'
0x140071c6f  lea     rcx, [rsp+580h+var_538]
0x140071c74  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140071c79  nop
0x140071c7a  or      r12, 0FFFFFFFFFFFFFFFFh
0x140071c7e  mov     ebx, r13d
0x140071c81  cmp     [rsi+206Ch], r13d
0x140071c88  jbe     loc_140071D45
0x140071c8e  mov     r14, [rbp+480h+Block]
0x140071c92  mov     edx, ebx
0x140071c94  mov     rcx, [rsi+rdx*8+68h]
0x140071c99  mov     rax, [rcx+318h]
0x140071ca0  cmp     r12, rax
0x140071ca3  cmovb   rax, r12
0x140071ca7  mov     r12, rax
0x140071caa  lea     rax, [rcx+288h]
0x140071cb1  mov     [r14+rdx*8], rax
0x140071cb5  mov     ecx, [rsi+20ECh]
0x140071cbb  lea     eax, [rcx-1]
0x140071cbe  cmp     eax, 2
0x140071cc1  jbe     short loc_140071CF7
0x140071cc3  lea     eax, [rcx-4]
0x140071cc6  cmp     eax, 1
0x140071cc9  ja      short loc_140071D37
0x140071ccb  mov     rax, [rsi+rdx*8+68h]
0x140071cd0  addsd   xmm6, qword ptr [rax+338h]
0x140071cd8  addsd   xmm7, qword ptr [rax+340h]
0x140071ce0  lea     rax, aCpuCompression; "CPU-Compression"
0x140071ce7  lea     rdx, aCpuCompression_1; "CPU-Compression2"
0x140071cee  cmp     ecx, 5
0x140071cf1  cmovnz  rdx, rax
0x140071cf5  jmp     short loc_140071D2D
0x140071cf7  mov     rax, [rsi+rdx*8+68h]
0x140071cfc  addsd   xmm6, qword ptr [rax+338h]
0x140071d04  addsd   xmm7, qword ptr [rax+340h]
0x140071d0c  cmp     ecx, 2
0x140071d0f  jnz     short loc_140071D1A
0x140071d11  lea     rdx, aCpuEncryption2; "CPU-Encryption2"
0x140071d18  jmp     short loc_140071D2D
0x140071d1a  cmp     ecx, 3
0x140071d1d  lea     rdx, aCpuCrc32; "CPU-CRC32"
0x140071d24  jz      short loc_140071D2D
0x140071d26  lea     rdx, aCpuEncryption; "CPU-Encryption"
0x140071d2d  lea     rcx, [rsp+580h+var_538]
0x140071d32  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x140071d37  inc     ebx
0x140071d39  cmp     ebx, [rsi+206Ch]
0x140071d3f  jb      loc_140071C92
0x140071d45  cmp     [rsi+2069h], r13b
0x140071d4c  jz      loc_140071E06
0x140071d52  mov     rcx, [rsi+10h]
0x140071d56  mov     ebx, 0F0h
0x140071d5b  add     rcx, rbx
0x140071d5e  lea     rdx, aTotalBytespers_0; "> Total BytesPerSecond        = "
0x140071d65  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071d6a  mov     rdx, rax
0x140071d6d  mov     rax, [rax]
0x140071d70  movsxd  rcx, dword ptr [rax+4]
0x140071d74  or      dword ptr [rcx+rdx+18h], 2080h
0x140071d7c  mov     rax, [rdx]
0x140071d7f  movsxd  rcx, dword ptr [rax+4]
0x140071d83  mov     [rcx+rdx+20h], r13
0x140071d88  mov     rax, [rdx]
0x140071d8b  movsxd  rcx, dword ptr [rax+4]
0x140071d8f  mov     r14d, 0Ah
0x140071d95  mov     [rcx+rdx+28h], r14
0x140071d9a  movaps  xmm1, xmm6
0x140071d9d  mov     rcx, rdx
0x140071da0  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@N@Z; std::basic_ostream<ushort>::operator<<(double)
0x140071da5  mov     rcx, rax
0x140071da8  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071dad  cmp     [rsi+2069h], r13b
0x140071db4  jz      short loc_140071E06
0x140071db6  mov     rcx, [rsi+10h]
0x140071dba  add     rcx, rbx
0x140071dbd  lea     rdx, aTotalBytespers; "> Total BytesPerSecond (mean) = "
0x140071dc4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071dc9  mov     rdx, rax
0x140071dcc  mov     rax, [rax]
0x140071dcf  movsxd  rcx, dword ptr [rax+4]
0x140071dd3  or      dword ptr [rcx+rdx+18h], 2080h
0x140071ddb  mov     rax, [rdx]
0x140071dde  movsxd  rcx, dword ptr [rax+4]
0x140071de2  mov     [rcx+rdx+20h], r13
0x140071de7  mov     rax, [rdx]
0x140071dea  movsxd  rcx, dword ptr [rax+4]
0x140071dee  mov     [rcx+rdx+28h], r14
0x140071df3  movaps  xmm1, xmm7
0x140071df6  mov     rcx, rdx
0x140071df9  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@N@Z; std::basic_ostream<ushort>::operator<<(double)
0x140071dfe  mov     rcx, rax
0x140071e01  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071e06  lea     r14, [rsi+28h]
0x140071e0a  mov     rcx, r14
0x140071e0d  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140071e12  cmp     [rax+1F2h], r13w
0x140071e1a  jz      short loc_140071E8C
0x140071e1c  mov     qword ptr [rsp+580h+ExitCode], r13
0x140071e21  mov     rcx, r14
0x140071e24  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140071e29  lea     r8, [rsp+580h+var_538]
0x140071e2e  lea     rdx, [rsp+580h+var_548]
0x140071e33  mov     rcx, rax
0x140071e36  call    ?GenDumpFileName@KeyInfo@@QEBA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEBV23@@Z; KeyInfo::GenDumpFileName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140071e3b  nop
0x140071e3c  lea     r8, [rsp+580h+ExitCode]; unsigned int
0x140071e41  mov     edx, 22h ; '"'; unsigned __int16 *
0x140071e46  mov     rcx, [rsp+580h+var_548]
0x140071e4b  mov     rcx, [rcx+18h]; lpFileName
0x140071e4f  call    ?MCreateFile@mlib@@YAKPEBGKAEAPEAX@Z; mlib::MCreateFile(ushort const *,ulong,void * &)
0x140071e54  test    eax, eax
0x140071e56  jnz     short loc_140071E82
0x140071e58  mov     rdx, qword ptr [rsp+580h+ExitCode]
0x140071e5d  lea     rcx, [rbp+480h+var_410]
0x140071e61  call    ??0?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@QEAA@PEAX_N_K@Z; mlib::handle_ostreamT<char,std::char_traits<char>>::handle_ostreamT<char,std::char_traits<char>>(void *,bool,unsigned __int64)
0x140071e66  nop
0x140071e67  lea     rdx, [rbp+480h+var_320]
0x140071e6e  lea     rcx, [rbp+480h+Block]
0x140071e72  call    ?DumpSamples@SampleManager@@SAXAEAV?$vector@PEBVSampleManager@@V?$allocator@PEBVSampleManager@@@std@@@std@@AEAV?$basic_ostream@DU?$char_traits@D@std@@@3@@Z; SampleManager::DumpSamples(std::vector<SampleManager const *> &,std::ostream &)
0x140071e77  nop
0x140071e78  lea     rcx, [rbp+480h+var_410]
0x140071e7c  call    ??_D?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@QEAAXXZ; mlib::handle_ostreamT<char,std::char_traits<char>>::`vbase destructor'(void)
0x140071e81  nop
0x140071e82  lea     rcx, [rsp+580h+var_548]
0x140071e87  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140071e8c  lea     rdx, aUnits; "Units"
0x140071e93  lea     rcx, [rbp+480h+var_468]
0x140071e97  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140071e9c  nop
0x140071e9d  cmp     dword ptr [rdi+8], 2
0x140071ea1  jnz     short loc_140071EB2
0x140071ea3  lea     rdx, asc_14012B480; ">"
0x140071eaa  mov     rcx, [rdi]
0x140071ead  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071eb2  mov     dword ptr [rdi+8], 2
0x140071eb9  mov     rcx, rdi; this
0x140071ebc  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140071ec1  lea     rdx, asc_14012B484; "<"
0x140071ec8  mov     rcx, [rdi]
0x140071ecb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071ed0  mov     rcx, rax
0x140071ed3  lea     rdx, [rbp+480h+var_468]
0x140071ed7  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140071edc  mov     ebx, 1
0x140071ee1  add     [rdi+0Ch], ebx
0x140071ee4  mov     [rdi+11h], r13b
0x140071ee8  lea     rdx, aName_0; "name"
0x140071eef  lea     rcx, [rbp+480h+var_470]
0x140071ef3  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140071ef8  nop
0x140071ef9  mov     dword ptr [rdi+8], 3
0x140071f00  lea     rdx, asc_14012B49C; " "
0x140071f07  mov     rcx, [rdi]
0x140071f0a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071f0f  mov     rcx, rax
0x140071f12  lea     rdx, [rbp+480h+var_470]
0x140071f16  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
  ... truncated ...
```
