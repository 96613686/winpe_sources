# WinSAT::MemAssessment1::OutputResults(mlib::XmlStream &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14005ccd0`
- end: `0x14005ed77`
- name: `?OutputResults@MemAssessment1@WinSAT@@UEBAJAEAVXmlStream@mlib@@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@4@@Z`
- size: `8359`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config`

## callees

- `0x140001abc`
- `0x140004348`
- `0x14000449c`
- `0x1400045d4`
- `0x140005d78`
- `0x14000695c`
- `0x140007e3c`
- `0x140007f14`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x140008730`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140016480`
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
- `0x14005ccd0`
- `0x1400603d4`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005cf52`
- `KERNEL32!GetLastError` at `0x14005cf52`
- `KERNEL32!GetExitCodeThread` at `0x14005ce8a`
- `KERNEL32!GetExitCodeThread` at `0x14005ce8a`

## string_xrefs

- `0x14005d65b`: `NumThreads`
- `0x14005d6d0`: `NumThreads`
- `0x14005d8d8`: `UnCachedMemSpace`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall WinSAT::MemAssessment1::OutputResults(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 *v6; // rax
  mlib::XmlStream *v7; // rbx
  const wchar_t *v8; // rdx
  __int64 *v9; // rcx
  __int64 *v10; // rax
  __int16 v11; // dx
  mlib::MUILoader *v12; // rax
  unsigned int v13; // r14d
  char v14; // bl
  unsigned int i; // r14d
  __int64 v16; // rcx
  __int64 v17; // rbx
  const unsigned __int16 *v18; // rax
  __int64 *v19; // rax
  __int64 *v20; // rax
  __int64 *v21; // rax
  __int64 *v22; // rax
  __int64 *v23; // rax
  __int64 v24; // rbx
  unsigned __int16 v25; // r9
  const unsigned __int16 *v26; // rax
  __int64 *v27; // rax
  __int64 *v28; // rax
  __int64 *v29; // rax
  __int64 v30; // rax
  double v31; // xmm6_8
  double v32; // xmm7_8
  unsigned int v33; // edx
  _QWORD *j; // r13
  __int64 v35; // rax
  __int64 *v36; // rax
  __int64 v37; // rax
  __int64 *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rbx
  void **v41; // r9
  __int64 *v42; // rax
  __int64 *v43; // rax
  __int64 *v44; // rax
  __int64 *v45; // rax
  __int64 *v46; // rax
  __int64 *v47; // rax
  __int64 *v48; // rax
  const wchar_t *v49; // rdx
  __int64 *v50; // rcx
  __int64 *v51; // rax
  __int64 *v52; // rax
  __int64 *v53; // rax
  __int64 *v54; // rax
  __int64 *v55; // rax
  __int64 *v56; // rax
  __int64 *v57; // rax
  __int64 *v58; // rax
  const wchar_t *v59; // rdx
  __int64 *v60; // rcx
  __int64 *v61; // rax
  __int64 *v62; // rax
  int v63; // ebx
  const wchar_t *v64; // rdx
  __int64 *v65; // rcx
  __int64 *v66; // rax
  __int64 *v67; // rax
  int v68; // ebx
  const wchar_t *v69; // rdx
  __int64 *v70; // rcx
  __int64 *v71; // rax
  __int64 *v72; // rax
  __int64 *v73; // rax
  __int64 *v74; // rax
  int v75; // ebx
  const wchar_t *v76; // rdx
  __int64 *v77; // rcx
  __int64 *v78; // rax
  __int64 *v79; // rax
  __int64 *v80; // rax
  __int64 *v81; // rax
  const wchar_t *v82; // rbx
  __int64 *v83; // rax
  __int64 *v84; // rax
  int v85; // ebx
  const wchar_t *v86; // rdx
  __int64 *v87; // rcx
  __int64 *v88; // rax
  __int64 *v89; // rax
  __int64 *v90; // rax
  __int64 *v91; // rax
  int v92; // ebx
  const wchar_t *v93; // rdx
  __int64 *v94; // rcx
  __int64 *v95; // rax
  __int64 *v96; // rax
  __int64 *v97; // rax
  __int64 *v98; // rax
  __int64 *v99; // rdx
  __int64 v100; // rcx
  __int64 *v101; // r8
  __int64 v102; // rcx
  const wchar_t *v103; // rdx
  __int64 *v104; // rcx
  __int64 *v105; // rax
  __int64 *v106; // rax
  __int64 *v107; // rax
  __int64 *v108; // rax
  __int64 *v109; // rdx
  __int64 v110; // rcx
  __int64 *v111; // r8
  __int64 v112; // rcx
  const wchar_t *v113; // rdx
  __int64 *v114; // rcx
  __int64 *v115; // rax
  __int64 *v116; // rax
  unsigned int v117; // r12d
  double v118; // xmm10_8
  __int64 v119; // r15
  __int64 v120; // rcx
  double v121; // xmm1_8
  __int64 v122; // rax
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
  const wchar_t *v186; // rdx
  __int64 *v187; // rcx
  __int64 *v188; // rax
  const wchar_t *v189; // rdx
  __int64 *v190; // rcx
  __int64 *v191; // rax
  const wchar_t *v192; // rdx
  __int64 *v193; // rcx
  __int64 *v194; // rax
  unsigned __int64 *v196; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 *v197; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int64 *v198; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int64 *v199; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int64 *v200; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 *v201; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int64 *v202; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 *v203; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 *v204; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 *v205; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 *v206; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 *v207; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 *v208; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 *v209; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 *v210; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 *v211; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int64 *v212; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 *v213; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int64 *v214; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 *v215; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int64 *v216; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 *v217; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int64 *v218; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 *v219; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int64 *v220; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 *v221; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int64 *v222; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int64 *v223; // [rsp+110h] [rbp+8h] BYREF
  unsigned __int64 *v224; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int64 *v225; // [rsp+120h] [rbp+18h] BYREF
  unsigned __int64 *v226; // [rsp+128h] [rbp+20h] BYREF
  void *Block[2]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v228; // [rsp+140h] [rbp+38h]
  _QWORD Buffer[30]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v230[272]; // [rsp+248h] [rbp+140h] BYREF
  DWORD LastError; // [rsp+358h] [rbp+250h]
  char v232; // [rsp+35Ch] [rbp+254h]
  __int64 v233; // [rsp+360h] [rbp+258h]

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v199,
    L"TestName");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v6, &v199);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  v197 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v197,
    *(_QWORD *)(a1 + 728));
  v7 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
         (mlib::XmlStream *)a2,
         &v197);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v198,
    L"TestName");
  --*((_DWORD *)v7 + 3);
  if ( *((_DWORD *)v7 + 2) == 1 )
  {
    if ( !*((_BYTE *)v7 + 17) )
      mlib::XmlStream::Indent(v7);
    *((_BYTE *)v7 + 17) = 0;
    v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v7, (__int64)L"</");
    v9 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v10, &v198);
    v8 = L">";
    goto LABEL_9;
  }
  if ( *((_DWORD *)v7 + 2) == 2 )
  {
    v8 = L"/>";
    v9 = *(__int64 **)v7;
LABEL_9:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, (__int64)v8);
  }
  *((_DWORD *)v7 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v198);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v199);
  if ( !*(_QWORD *)(a1 + 80) )
  {
    v11 = 620;
LABEL_12:
    v12 = mlib::MUILoader::MUILoader((mlib::MUILoader *)Block, v11);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator=(
      a3,
      (__int64)v12);
    return (unsigned int)-2147221503;
  }
  if ( *(_BYTE *)(a1 + 738) )
  {
    v11 = 619;
    goto LABEL_12;
  }
  v14 = 1;
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(a1 + 68) )
    {
      if ( !v14 )
      {
        v11 = 623;
        goto LABEL_12;
      }
      v13 = 0;
      *(_DWORD *)(a1 + 56) = 6;
      v31 = 0.0;
      v32 = 0.0;
      *(_OWORD *)Block = 0;
      v228 = 0;
      v196 = 0;
      std::vector<SampleManager const *>::resize(Block, *(unsigned int *)(a1 + 68), &v196);
      v33 = 0;
      for ( j = Block[0]; v33 < *(_DWORD *)(a1 + 68); ++v33 )
      {
        v35 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * v33);
        v31 = v31 + *(double *)(v35 + 72);
        v32 = v32 + *(double *)(v35 + 96);
        j[v33] = v35 + 152;
      }
      if ( *(_BYTE *)(a1 + 33) )
      {
        v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*(_QWORD *)(a1 + 16) + 240LL),
                (__int64)L"> Total BytesPerSecond        = ");
        *(_DWORD *)((char *)v36 + *(int *)(*v36 + 4) + 24) |= 0x2090u;
        *(__int64 *)((char *)v36 + *(int *)(*v36 + 4) + 32) = 0;
        *(__int64 *)((char *)v36 + *(int *)(*v36 + 4) + 40) = 11;
        v37 = std::basic_ostream<unsigned short>::operator<<((__int64)v36, v31);
        std::endl(v37);
        if ( *(_BYTE *)(a1 + 32) )
        {
          v38 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                  (__int64 *)(*(_QWORD *)(a1 + 16) + 240LL),
                  (__int64)L"> Total BytesPerSecond (mean) = ");
          *(_DWORD *)((char *)v38 + *(int *)(*v38 + 4) + 24) |= 0x2090u;
          *(__int64 *)((char *)v38 + *(int *)(*v38 + 4) + 32) = 0;
          *(__int64 *)((char *)v38 + *(int *)(*v38 + 4) + 40) = 11;
          v39 = std::basic_ostream<unsigned short>::operator<<((__int64)v38, v32);
          std::endl(v39);
        }
      }
      if ( *(_WORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40)
                    + 498) )
      {
        v198 = 0;
        v40 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v199,
          L"MemBandwidth");
        KeyInfo::GenDumpFileName(v40, &v197, &v199);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v199);
        if ( !mlib::MCreateFile((LPCWSTR)v197[3], (const unsigned __int16 *)0x22, &v198, v41) )
        {
          mlib::handle_ostreamT<char,std::char_traits<char>>::handle_ostreamT<char,std::char_traits<char>>(Buffer, v198);
          SampleManager::DumpSamples(Block, v230);
          mlib::handle_ostreamT<char,std::char_traits<char>>::`vbase destructor'(Buffer);
        }
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v197);
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v207,
        L"Units");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v42 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v42, &v207);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v206,
        L"name");
      *((_DWORD *)a2 + 2) = 3;
      v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v44 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v43, &v206);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v205,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v46 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v45, &v205);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v46, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"B/s");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v204,
        L"descrip");
      *((_DWORD *)a2 + 2) = 3;
      v47 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v48 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v47, &v204);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes per second");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v203,
        L"Units");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v51 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v50 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v51, &v203);
        v49 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_43;
        v49 = L"/>";
        v50 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, (__int64)v49);
LABEL_43:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v202,
        L"Units");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v52 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v52, &v202);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v201,
        L"name");
      *((_DWORD *)a2 + 2) = 3;
      v53 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v54 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v53, &v201);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v200,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v55 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v56 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v55, &v200);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v56, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v217,
        L"descrip");
      *((_DWORD *)a2 + 2) = 3;
      v57 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v58 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v57, &v217);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v58, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v216,
        L"Units");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v61 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v60 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v61, &v216);
        v59 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_52;
        v59 = L"/>";
        v60 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v60, (__int64)v59);
LABEL_52:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v215,
        L"NumProcessors");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v62 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v62, &v215);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      v63 = *(_DWORD *)(a1 + 64);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v63);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v214,
        L"NumProcessors");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v65 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v66, &v214);
        v64 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_61;
        v64 = L"/>";
        v65 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, (__int64)v64);
LABEL_61:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v213,
        L"NumThreads");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v67 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v67, &v213);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      v68 = *(_DWORD *)(a1 + 68);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v68);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v212,
        L"NumThreads");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v71 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v70 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v71, &v212);
        v69 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_70;
        v69 = L"/>";
        v70 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v70, (__int64)v69);
LABEL_70:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v211,
        L"PageSize");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v72 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v72, &v211);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v210,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v73 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v74 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v73, &v210);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v75 = *(_DWORD *)(a1 + 72);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v75);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v209,
        L"PageSize");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v78 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v77 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v78, &v209);
        v76 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_79;
        v76 = L"/>";
        v77 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v77, (__int64)v76);
LABEL_79:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v208,
        L"MemBlockSize");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v79 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v79, &v208);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v226,
        L"UnCachedMemSpace");
      *((_DWORD *)a2 + 2) = 3;
      v80 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v81 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v80, &v226);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v81, (__int64)L"=");
      v82 = L"YES";
      if ( !*(_BYTE *)(a1 + 736) )
        v82 = L"NO";
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)v82);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v225,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v83 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v84 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v83, &v225);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v84, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v85 = *(_DWORD *)(a1 + 708);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v85);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v224,
        L"MemBlockSize");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v88 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v87 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v88, &v224);
        v86 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_90;
        v86 = L"/>";
        v87 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v87, (__int64)v86);
LABEL_90:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v223,
        L"MemDestOffset");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v89 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v89, &v223);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v222,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v90 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v91 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v90, &v222);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v91, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v92 = *(_DWORD *)(a1 + 712);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v92);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v221,
        L"MemDestOffset");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v95 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v94 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v95, &v221);
        v93 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_99;
        v93 = L"/>";
        v94 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v94, (__int64)v93);
LABEL_99:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v220,
        L"TotalBytesPerSecond");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v96 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v96, &v220);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v219,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v97 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v98 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v97, &v219);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v98, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v99 = (__int64 *)*a2;
      v100 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v99 + v100 + 24) |= 0x2090u;
      *(__int64 *)((char *)v99 + *(int *)(*v99 + 4) + 32) = 5;
      *(__int64 *)((char *)v99 + *(int *)(*v99 + 4) + 40) = 6;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v31);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v101 = (__int64 *)*a2;
      v102 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v101 + v102 + 24) |= 0x201u;
      *(_WORD *)((char *)v101 + *(int *)(*v101 + 4) + 88) = 32;
      *(__int64 *)((char *)v101 + *(int *)(*v101 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v218,
        L"TotalBytesPerSecond");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v105 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v104 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v105,
                 &v218);
        v103 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_108;
        v103 = L"/>";
        v104 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v104, (__int64)v103);
LABEL_108:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v197,
        L"TotalBytesPerSecondMean");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v106 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v106, &v197);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v198,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      v107 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
      v108 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v107, &v198);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v108, (__int64)L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v109 = (__int64 *)*a2;
      v110 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v109 + v110 + 24) |= 0x2090u;
      *(__int64 *)((char *)v109 + *(int *)(*v109 + 4) + 32) = 5;
      *(__int64 *)((char *)v109 + *(int *)(*v109 + 4) + 40) = 6;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v32);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v111 = (__int64 *)*a2;
      v112 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)((char *)v111 + v112 + 24) |= 0x201u;
      *(_WORD *)((char *)v111 + *(int *)(*v111 + 4) + 88) = 32;
      *(__int64 *)((char *)v111 + *(int *)(*v111 + 4) + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v199,
        L"TotalBytesPerSecondMean");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v115 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v114 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v115,
                 &v199);
        v113 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_117;
        v113 = L"/>";
        v114 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v114, (__int64)v113);
LABEL_117:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v199);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v198);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v197);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v218);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v219);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v220);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v221);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v222);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v223);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v224);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v225);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v226);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v208);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v209);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v210);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v211);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v212);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v213);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v214);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v215);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v216);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v217);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v200);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v201);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v202);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v203);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v204);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v205);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v206);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v207);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v196,
        L"PerCPUData");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      v116 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v116, &v196);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v196);
      if ( *(_DWORD *)(a1 + 68) )
      {
        v117 = 0;
        v118 = (double)(2 * *(_DWORD *)(a1 + 708));
        while ( 1 )
        {
          v119 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * v117);
          v120 = *(_QWORD *)(v119 + 40);
          if ( v120 < 0 )
          {
            v122 = *(_QWORD *)(v119 + 40) & 1LL | ((unsigned __int64)v120 >> 1);
            v121 = (double)(int)v122 + (double)(int)v122;
          }
          else
          {
            v121 = (double)(int)v120;
          }
          v123 = *(_QWORD *)(v119 + 200);
          if ( v123 < 0 )
          {
            v125 = *(_QWORD *)(v119 + 200) & 1LL | ((unsigned __int64)v123 >> 1);
            v124 = (double)(int)v125 + (double)(int)v125;
          }
          else
          {
            v124 = (double)(int)v123;
          }
          v126 = v118 / (v124 / v121);
          v127 = *(_QWORD *)(v119 + 208);
          if ( v127 < 0 )
          {
            v129 = *(_QWORD *)(v119 + 208) & 1LL | ((unsigned __int64)v127 >> 1);
            v128 = (double)(int)v129 + (double)(int)v129;
          }
          else
          {
            v128 = (double)(int)v127;
          }
          v130 = v118 / (v128 / v121);
          v131 = *(_QWORD *)(v119 + 184);
          if ( v131 < 0 )
          {
            v133 = *(_QWORD *)(v119 + 184) & 1LL | ((unsigned __int64)v131 >> 1);
            v132 = (double)(int)v133 + (double)(int)v133;
          }
          else
          {
            v132 = (double)(int)v131;
          }
          v134 = v118 / (v132 / v121);
          v135 = *(_QWORD *)(v119 + 192);
          if ( v135 < 0 )
          {
            v137 = *(_QWORD *)(v119 + 192) & 1LL | ((unsigned __int64)v135 >> 1);
            v136 = (double)(int)v137 + (double)(int)v137;
          }
          else
          {
            v136 = (double)(int)v135;
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v211,
            L"CPUData");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v138 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v138, &v211);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v212,
            L"CPUIndex");
          *((_DWORD *)a2 + 2) = 3;
          v139 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v140 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v139,
                   &v212);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v140, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v117);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v213,
            L"Repetitions");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v141 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v141, &v213);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v142 = (__int64)(*(_QWORD *)(v119 + 160) - *(_QWORD *)(v119 + 152)) >> 3;
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v142);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v214,
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
                     &v214);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v153, (__int64)L">");
          }
          else if ( *((_DWORD *)a2 + 2) == 2 )
          {
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"/>");
          }
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v215,
            L"Min");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v143 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v143, &v215);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v216,
            L"units");
          *((_DWORD *)a2 + 2) = 3;
          v144 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v145 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v144,
                   &v216);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v146 = (__int64 *)*a2;
          v147 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v146 + v147 + 24) |= 0x2090u;
          *(__int64 *)((char *)v146 + *(int *)(*v146 + 4) + 32) = 5;
          *(__int64 *)((char *)v146 + *(int *)(*v146 + 4) + 40) = 6;
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
            &v217,
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
                     &v217);
            v150 = L">";
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
              goto LABEL_155;
            v150 = L"/>";
            v151 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v151, (__int64)v150);
LABEL_155:
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v200,
            L"Max");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v155 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v155, &v200);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v201,
            L"units");
          *((_DWORD *)a2 + 2) = 3;
          v156 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v157 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v156,
                   &v201);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v157, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v158 = (__int64 *)*a2;
          v159 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v158 + v159 + 24) |= 0x2090u;
          *(__int64 *)((char *)v158 + *(int *)(*v158 + 4) + 32) = 5;
          *(__int64 *)((char *)v158 + *(int *)(*v158 + 4) + 40) = 6;
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
            &v202,
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
                     &v202);
            v162 = L">";
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
              goto LABEL_164;
            v162 = L"/>";
            v163 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v163, (__int64)v162);
LABEL_164:
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v203,
            L"Median");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v165 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v165, &v203);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v204,
            L"units");
          *((_DWORD *)a2 + 2) = 3;
          v166 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v167 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v166,
                   &v204);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v167, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v168 = (__int64 *)*a2;
          v169 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v168 + v169 + 24) |= 0x2090u;
          *(__int64 *)((char *)v168 + *(int *)(*v168 + 4) + 32) = 5;
          *(__int64 *)((char *)v168 + *(int *)(*v168 + 4) + 40) = 6;
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
            &v205,
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
                     &v205);
            v172 = L">";
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
              goto LABEL_173;
            v172 = L"/>";
            v173 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v173, (__int64)v172);
LABEL_173:
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v206,
            L"Mean");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v175 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v175, &v206);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v207,
            L"units");
          *((_DWORD *)a2 + 2) = 3;
          v176 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v177 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v176,
                   &v207);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v177, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v178 = (__int64 *)*a2;
          v179 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v178 + v179 + 24) |= 0x2090u;
          *(__int64 *)((char *)v178 + *(int *)(*v178 + 4) + 32) = 5;
          *(__int64 *)((char *)v178 + *(int *)(*v178 + 4) + 40) = 6;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v118 / (v136 / v121));
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v180 = (__int64 *)*a2;
          v181 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v180 + v181 + 24) |= 0x201u;
          *(_WORD *)((char *)v180 + *(int *)(*v180 + 4) + 88) = 32;
          *(__int64 *)((char *)v180 + *(int *)(*v180 + 4) + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v196,
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
                     &v196);
            v182 = L">";
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
              goto LABEL_182;
            v182 = L"/>";
            v183 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v183, (__int64)v182);
LABEL_182:
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v196);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v207);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v206);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v205);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v204);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v203);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v202);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v201);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v200);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v217);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v216);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v215);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v214);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v213);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v212);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v211);
          if ( !*(_BYTE *)(v119 + 336) )
            goto LABEL_193;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v209,
            L"RDTSCDeltaViolation");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v185 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v185, &v209);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v210,
            L"RDTSCDeltaViolation");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            v188 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
            v187 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v188,
                     &v210);
            v186 = L">";
            goto LABEL_191;
          }
          if ( *((_DWORD *)a2 + 2) == 2 )
          {
            v186 = L"/>";
            v187 = (__int64 *)*a2;
LABEL_191:
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v187, (__int64)v186);
          }
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v210);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v209);
LABEL_193:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v208,
            L"CPUData");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            v191 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
            v190 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v191,
                     &v208);
            v189 = L">";
            goto LABEL_199;
          }
          if ( *((_DWORD *)a2 + 2) == 2 )
          {
            v189 = L"/>";
            v190 = (__int64 *)*a2;
LABEL_199:
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v190, (__int64)v189);
          }
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v208);
          if ( ++v117 >= *(_DWORD *)(a1 + 68) )
          {
            j = Block[0];
            break;
          }
        }
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v196,
        L"PerCPUData");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        v194 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
        v193 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v194,
                 &v196);
        v192 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_209;
        v192 = L"/>";
        v193 = (__int64 *)*a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v193, (__int64)v192);
LABEL_209:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v196);
      if ( j )
        operator delete(j);
      return v13;
    }
    if ( !GetExitCodeThread(
            *(HANDLE *)(a1 + 8LL * i + 96),
            (LPDWORD)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * i) + 112LL)) )
      break;
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * i);
    if ( *(_DWORD *)(v16 + 112) )
    {
      LastError = *(_DWORD *)(v16 + 112);
      v232 = 1;
      v233 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v17 = *(_QWORD *)(a1 + 24);
      v18 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x8F6, 622, i);
      v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v17 + 240), (__int64)v18);
      v20 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v19, 10);
      v21 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v20,
              (unsigned __int64 **)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * i) + 408LL));
      v22 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v21, 10);
      v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22, (__int64)Buffer);
      std::endl(v23);
      v14 = 0;
    }
  }
  LastError = GetLastError();
  v232 = 1;
  v233 = 0;
  mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
  v24 = *(_QWORD *)(a1 + 24);
  v26 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x8EA, 621, v25);
  v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v24 + 240), (__int64)v26);
  v28 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v27, 10);
  v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, (__int64)Buffer);
  v30 = std::basic_ostream<unsigned short>::operator<<(v29, 10);
  std::endl(v30);
  return (unsigned int)-2147221503;
}

```

## disassembly

```asm
0x14005ccd0  mov     rax, rsp
0x14005ccd3  mov     [rax+20h], rbx
0x14005ccd7  push    rbp
0x14005ccd8  push    rsi
0x14005ccd9  push    rdi
0x14005ccda  push    r12
0x14005ccdc  push    r13
0x14005ccde  push    r14
0x14005cce0  push    r15
0x14005cce2  lea     rbp, [rax-2F8h]
0x14005cce9  sub     rsp, 3C0h
0x14005ccf0  movaps  xmmword ptr [rax-48h], xmm6
0x14005ccf4  movaps  xmmword ptr [rax-58h], xmm7
0x14005ccf8  movaps  xmmword ptr [rax-68h], xmm8
0x14005ccfd  movaps  xmmword ptr [rax-78h], xmm9
0x14005cd02  movaps  xmmword ptr [rax-88h], xmm10
0x14005cd0a  mov     rax, cs:__security_cookie
0x14005cd11  xor     rax, rsp
0x14005cd14  mov     [rbp+2F0h+var_90], rax
0x14005cd1b  mov     r12, r8
0x14005cd1e  mov     rdi, rdx
0x14005cd21  mov     rsi, rcx
0x14005cd24  lea     rdx, aTestname; "TestName"
0x14005cd2b  lea     rcx, [rsp+3F0h+var_3A8]
0x14005cd30  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14005cd35  nop
0x14005cd36  cmp     dword ptr [rdi+8], 2
0x14005cd3a  jnz     short loc_14005CD4B
0x14005cd3c  lea     rdx, asc_14012B480; ">"
0x14005cd43  mov     rcx, [rdi]
0x14005cd46  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cd4b  mov     dword ptr [rdi+8], 2
0x14005cd52  mov     rcx, rdi; this
0x14005cd55  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14005cd5a  lea     rdx, asc_14012B484; "<"
0x14005cd61  mov     rcx, [rdi]
0x14005cd64  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cd69  mov     rcx, rax
0x14005cd6c  lea     rdx, [rsp+3F0h+var_3A8]
0x14005cd71  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005cd76  inc     dword ptr [rdi+0Ch]
0x14005cd79  xor     r15d, r15d
0x14005cd7c  mov     [rdi+11h], r15b
0x14005cd80  mov     [rsp+3F0h+var_3B8], r15
0x14005cd85  mov     rdx, [rsi+2D8h]
0x14005cd8c  lea     rcx, [rsp+3F0h+var_3B8]
0x14005cd91  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14005cd96  lea     rdx, [rsp+3F0h+var_3B8]
0x14005cd9b  mov     rcx, rdi
0x14005cd9e  call    ??$?6V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@XmlStream@mlib@@QEAAAEAV01@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::XmlStream::operator<<<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)
0x14005cda3  mov     rbx, rax
0x14005cda6  lea     rdx, aTestname; "TestName"
0x14005cdad  lea     rcx, [rsp+3F0h+var_3B0]
0x14005cdb2  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14005cdb7  nop
0x14005cdb8  dec     dword ptr [rbx+0Ch]
0x14005cdbb  mov     eax, [rbx+8]
0x14005cdbe  sub     eax, 1
0x14005cdc1  jz      short loc_14005CDD4
0x14005cdc3  cmp     eax, 1
0x14005cdc6  jnz     short loc_14005CE11
0x14005cdc8  lea     rdx, asc_14012B488; "/>"
0x14005cdcf  mov     rcx, [rbx]
0x14005cdd2  jmp     short loc_14005CE0C
0x14005cdd4  cmp     [rbx+11h], r15b
0x14005cdd8  jnz     short loc_14005CDE2
0x14005cdda  mov     rcx, rbx; this
0x14005cddd  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14005cde2  mov     [rbx+11h], r15b
0x14005cde6  lea     rdx, asc_14012B490; "</"
0x14005cded  mov     rcx, [rbx]
0x14005cdf0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cdf5  mov     rcx, rax
0x14005cdf8  lea     rdx, [rsp+3F0h+var_3B0]
0x14005cdfd  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005ce02  mov     rcx, rax
0x14005ce05  lea     rdx, asc_14012B480; ">"
0x14005ce0c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005ce11  mov     dword ptr [rbx+8], 1
0x14005ce18  lea     rcx, [rsp+3F0h+var_3B0]
0x14005ce1d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005ce22  nop
0x14005ce23  lea     rcx, [rsp+3F0h+var_3A8]
0x14005ce28  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005ce2d  cmp     [rsi+50h], r15
0x14005ce31  jnz     short loc_14005CE57
0x14005ce33  mov     edx, 26Ch; unsigned __int16
0x14005ce38  lea     rcx, [rbp+2F0h+Block]; this
0x14005ce3c  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x14005ce41  mov     rdx, rax
0x14005ce44  mov     rcx, r12
0x14005ce47  call    ??4?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV01@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator=(mlib::MSInitializer const &)
0x14005ce4c  mov     r14d, 80040001h
0x14005ce52  jmp     loc_14005ED31
0x14005ce57  cmp     [rsi+2E2h], r15b
0x14005ce5e  jz      short loc_14005CE67
0x14005ce60  mov     edx, 26Bh
0x14005ce65  jmp     short loc_14005CE38
0x14005ce67  mov     bl, 1
0x14005ce69  mov     r14d, r15d
0x14005ce6c  cmp     r14d, [rsi+44h]
0x14005ce70  jnb     loc_14005CFD2
0x14005ce76  mov     r15d, r14d
0x14005ce79  mov     rax, [rsi+50h]
0x14005ce7d  mov     rdx, [rax+r15*8]
0x14005ce81  add     rdx, 70h ; 'p'; lpExitCode
0x14005ce85  mov     rcx, [rsi+r15*8+60h]; hThread
0x14005ce8a  call    cs:__imp_GetExitCodeThread
0x14005ce90  xor     r13d, r13d
0x14005ce93  test    eax, eax
0x14005ce95  jz      loc_14005CF52
0x14005ce9b  mov     rax, [rsi+50h]
0x14005ce9f  mov     rcx, [rax+r15*8]
0x14005cea3  mov     eax, [rcx+70h]
0x14005cea6  test    eax, eax
0x14005cea8  jz      loc_14005CF47
0x14005ceae  mov     [rbp+2F0h+var_A0], eax
0x14005ceb4  mov     [rbp+2F0h+var_9C], 1
0x14005cebb  mov     [rbp+2F0h+var_98], r13
0x14005cec2  lea     rcx, [rbp+2F0h+Buffer]; lpBuffer
0x14005cec6  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005cecb  mov     rbx, [rsi+18h]
0x14005cecf  mov     r8d, 26Eh; int
0x14005ced5  mov     r9d, r14d; unsigned __int16
0x14005ced8  mov     edx, 8F6h; char *
0x14005cedd  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005cee4  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x14005cee9  mov     rdx, rax
0x14005ceec  lea     rcx, [rbx+0F0h]
0x14005cef3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cef8  mov     r13d, 0Ah
0x14005cefe  mov     edx, r13d
0x14005cf01  mov     rcx, rax
0x14005cf04  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005cf09  mov     rcx, [rsi+50h]
0x14005cf0d  mov     rdx, [rcx+r15*8]
0x14005cf11  add     rdx, 198h
0x14005cf18  mov     rcx, rax
0x14005cf1b  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005cf20  mov     edx, r13d
0x14005cf23  mov     rcx, rax
0x14005cf26  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005cf2b  lea     rdx, [rbp+2F0h+Buffer]
0x14005cf2f  mov     rcx, rax
0x14005cf32  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cf37  mov     rcx, rax
0x14005cf3a  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005cf3f  xor     r15d, r15d
0x14005cf42  mov     bl, r15b
0x14005cf45  jmp     short loc_14005CF4A
0x14005cf47  xor     r15d, r15d
0x14005cf4a  inc     r14d
0x14005cf4d  jmp     loc_14005CE6C
0x14005cf52  call    cs:__imp_GetLastError
0x14005cf58  mov     [rbp+2F0h+var_A0], eax
0x14005cf5e  mov     [rbp+2F0h+var_9C], 1
0x14005cf65  mov     [rbp+2F0h+var_98], r13
0x14005cf6c  lea     rcx, [rbp+2F0h+Buffer]; lpBuffer
0x14005cf70  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005cf75  mov     rbx, [rsi+18h]
0x14005cf79  mov     edx, 8EAh; char *
0x14005cf7e  mov     r8d, 26Dh; int
0x14005cf84  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005cf8b  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14005cf90  mov     rdx, rax
0x14005cf93  lea     rcx, [rbx+0F0h]
0x14005cf9a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cf9f  mov     edx, 0Ah
0x14005cfa4  mov     rcx, rax
0x14005cfa7  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005cfac  lea     rdx, [rbp+2F0h+Buffer]
0x14005cfb0  mov     rcx, rax
0x14005cfb3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cfb8  mov     edx, 0Ah
0x14005cfbd  mov     rcx, rax
0x14005cfc0  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005cfc5  mov     rcx, rax
0x14005cfc8  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005cfcd  jmp     loc_14005CE4C
0x14005cfd2  test    bl, bl
0x14005cfd4  jnz     short loc_14005CFE0
0x14005cfd6  mov     edx, 26Fh
0x14005cfdb  jmp     loc_14005CE38
0x14005cfe0  mov     r14d, r15d
0x14005cfe3  mov     dword ptr [rsi+38h], 6
0x14005cfea  xorps   xmm6, xmm6
0x14005cfed  xorps   xmm7, xmm7
0x14005cff0  xorps   xmm0, xmm0
0x14005cff3  movdqu  xmmword ptr [rbp+2F0h+Block], xmm0
0x14005cff8  mov     [rbp+2F0h+var_2B8], r15
0x14005cffc  mov     [rsp+3F0h+var_3C0], r15
0x14005d001  mov     edx, [rsi+44h]
0x14005d004  lea     r8, [rsp+3F0h+var_3C0]
0x14005d009  lea     rcx, [rbp+2F0h+Block]
0x14005d00d  call    ?resize@?$vector@PEBVSampleManager@@V?$allocator@PEBVSampleManager@@@std@@@std@@QEAAX_KAEBQEBVSampleManager@@@Z; std::vector<SampleManager const *>::resize(unsigned __int64,SampleManager const * const &)
0x14005d012  mov     edx, r15d
0x14005d015  mov     r13, [rbp+2F0h+Block]
0x14005d019  mov     r12d, 1
0x14005d01f  cmp     [rsi+44h], r15d
0x14005d023  jbe     short loc_14005D04C
0x14005d025  mov     ecx, edx
0x14005d027  mov     rax, [rsi+50h]
0x14005d02b  mov     rax, [rax+rcx*8]
0x14005d02f  addsd   xmm6, qword ptr [rax+48h]
0x14005d034  addsd   xmm7, qword ptr [rax+60h]
0x14005d039  add     rax, 98h
0x14005d03f  mov     [r13+rcx*8+0], rax
0x14005d044  add     edx, r12d
0x14005d047  cmp     edx, [rsi+44h]
0x14005d04a  jb      short loc_14005D025
0x14005d04c  cmp     [rsi+21h], r15b
0x14005d050  jz      loc_14005D103
0x14005d056  mov     rcx, [rsi+10h]
0x14005d05a  mov     ebx, 0F0h
0x14005d05f  add     rcx, rbx
0x14005d062  lea     rdx, aTotalBytespers_0; "> Total BytesPerSecond        = "
0x14005d069  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005d06e  mov     rcx, [rax]
0x14005d071  movsxd  rdx, dword ptr [rcx+4]
0x14005d075  or      dword ptr [rdx+rax+18h], 2090h
0x14005d07d  mov     rcx, [rax]
0x14005d080  movsxd  rdx, dword ptr [rcx+4]
0x14005d084  mov     [rdx+rax+20h], r15
0x14005d089  mov     rcx, [rax]
0x14005d08c  movsxd  rdx, dword ptr [rcx+4]
0x14005d090  mov     qword ptr [rdx+rax+28h], 0Bh
0x14005d099  movaps  xmm1, xmm6
0x14005d09c  mov     rcx, rax
0x14005d09f  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@N@Z; std::basic_ostream<ushort>::operator<<(double)
0x14005d0a4  mov     rcx, rax
0x14005d0a7  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005d0ac  cmp     [rsi+20h], r15b
0x14005d0b0  jz      short loc_14005D103
0x14005d0b2  mov     rcx, [rsi+10h]
0x14005d0b6  add     rcx, rbx
0x14005d0b9  lea     rdx, aTotalBytespers; "> Total BytesPerSecond (mean) = "
0x14005d0c0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005d0c5  mov     rcx, [rax]
0x14005d0c8  movsxd  rdx, dword ptr [rcx+4]
0x14005d0cc  or      dword ptr [rdx+rax+18h], 2090h
0x14005d0d4  mov     rcx, [rax]
0x14005d0d7  movsxd  rdx, dword ptr [rcx+4]
0x14005d0db  mov     [rdx+rax+20h], r15
0x14005d0e0  mov     rcx, [rax]
0x14005d0e3  movsxd  rdx, dword ptr [rcx+4]
0x14005d0e7  mov     qword ptr [rdx+rax+28h], 0Bh
0x14005d0f0  movaps  xmm1, xmm7
0x14005d0f3  mov     rcx, rax
0x14005d0f6  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@N@Z; std::basic_ostream<ushort>::operator<<(double)
0x14005d0fb  mov     rcx, rax
0x14005d0fe  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005d103  lea     rcx, [rsi+28h]
0x14005d107  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005d10c  cmp     [rax+1F2h], r15w
0x14005d114  jz      loc_14005D1AA
0x14005d11a  mov     [rsp+3F0h+var_3B0], r15
0x14005d11f  lea     rcx, [rsi+28h]
0x14005d123  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005d128  mov     rbx, rax
0x14005d12b  lea     rdx, aMembandwidth; "MemBandwidth"
0x14005d132  lea     rcx, [rsp+3F0h+var_3A8]
0x14005d137  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14005d13c  nop
0x14005d13d  lea     r8, [rsp+3F0h+var_3A8]
0x14005d142  lea     rdx, [rsp+3F0h+var_3B8]
0x14005d147  mov     rcx, rbx
0x14005d14a  call    ?GenDumpFileName@KeyInfo@@QEBA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEBV23@@Z; KeyInfo::GenDumpFileName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005d14f  nop
0x14005d150  lea     rcx, [rsp+3F0h+var_3A8]
0x14005d155  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005d15a  lea     r8, [rsp+3F0h+var_3B0]; unsigned int
0x14005d15f  mov     edx, 22h ; '"'; unsigned __int16 *
0x14005d164  mov     rcx, [rsp+3F0h+var_3B8]
0x14005d169  mov     rcx, [rcx+18h]; lpFileName
0x14005d16d  call    ?MCreateFile@mlib@@YAKPEBGKAEAPEAX@Z; mlib::MCreateFile(ushort const *,ulong,void * &)
0x14005d172  test    eax, eax
0x14005d174  jnz     short loc_14005D1A0
0x14005d176  mov     rdx, [rsp+3F0h+var_3B0]
0x14005d17b  lea     rcx, [rbp+2F0h+Buffer]
0x14005d17f  call    ??0?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@QEAA@PEAX_N_K@Z; mlib::handle_ostreamT<char,std::char_traits<char>>::handle_ostreamT<char,std::char_traits<char>>(void *,bool,unsigned __int64)
0x14005d184  nop
0x14005d185  lea     rdx, [rbp+2F0h+var_1B0]
0x14005d18c  lea     rcx, [rbp+2F0h+Block]
0x14005d190  call    ?DumpSamples@SampleManager@@SAXAEAV?$vector@PEBVSampleManager@@V?$allocator@PEBVSampleManager@@@std@@@std@@AEAV?$basic_ostream@DU?$char_traits@D@std@@@3@@Z; SampleManager::DumpSamples(std::vector<SampleManager const *> &,std::ostream &)
0x14005d195  nop
0x14005d196  lea     rcx, [rbp+2F0h+Buffer]
0x14005d19a  call    ??_D?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@QEAAXXZ; mlib::handle_ostreamT<char,std::char_traits<char>>::`vbase destructor'(void)
0x14005d19f  nop
0x14005d1a0  lea     rcx, [rsp+3F0h+var_3B8]
0x14005d1a5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005d1aa  lea     rdx, aUnits; "Units"
0x14005d1b1  lea     rcx, [rbp+2F0h+var_368]
0x14005d1b5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14005d1ba  nop
0x14005d1bb  lea     rbx, asc_14012B480; ">"
0x14005d1c2  cmp     dword ptr [rdi+8], 2
0x14005d1c6  jnz     short loc_14005D1D3
0x14005d1c8  mov     rdx, rbx
0x14005d1cb  mov     rcx, [rdi]
0x14005d1ce  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
  ... truncated ...
```
