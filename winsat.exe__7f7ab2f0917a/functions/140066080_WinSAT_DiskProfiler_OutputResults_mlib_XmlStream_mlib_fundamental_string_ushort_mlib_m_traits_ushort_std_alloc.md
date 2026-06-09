# WinSAT::DiskProfiler::OutputResults(mlib::XmlStream &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140066080`
- end: `0x1400698fa`
- name: `?OutputResults@DiskProfiler@WinSAT@@UEBAJAEAVXmlStream@mlib@@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@4@@Z`
- size: `14458`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140004170`
- `0x140004348`
- `0x14000449c`
- `0x1400045d4`
- `0x140004ae4`
- `0x140005d78`
- `0x140005f4c`
- `0x140008178`
- `0x1400083a4`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140013454`
- `0x14001362c`
- `0x140016480`
- `0x140016d04`
- `0x140019a1c`
- `0x14001bec8`
- `0x14002093c`
- `0x1400219d0`
- `0x140021a34`
- `0x1400530a8`
- `0x140062c30`
- `0x140065f30`
- `0x140066080`
- `0x140069e64`
- `0x14006d2e0`
- `0x140113220`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14006989b`
- `KERNEL32!SetLastError` at `0x14006989b`

## string_xrefs

- `0x140066100`: `AvailableTempFileSize`
- `0x1400661df`: `AvailableTempFileSize`
- `0x14006626e`: `UsedTempFileSize`
- `0x14006634d`: `UsedTempFileSize`
- `0x140067d71`: `ServiceTime`
- `0x14006811a`: `ServiceTime`
- `0x140068f3f`: `ServiceTime`
- `0x14006902a`: `ServiceTime`
- `0x140069284`: `ServiceTime`
- `0x140069334`: `ServiceTime`
- `0x14006945d`: `ServiceTime`
- `0x14006950b`: `ServiceTime`
- `0x14006862a`: `InterferenceCountWithReads`
- `0x1400686a8`: `InterferenceCountWithReads`
- `0x140069097`: `Writes`
- `0x140069382`: `Writes`
- `0x140068c33`: `Reads`
- `0x140069074`: `Reads`

## pseudocode

```c
// Hidden C++ exception states: #wind=124
__int64 __fastcall WinSAT::DiskProfiler::OutputResults(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r12
  _DWORD *v5; // r15
  __int64 *v6; // rax
  __int64 *v7; // rax
  __int64 *v8; // rax
  __int64 v9; // rbx
  const wchar_t *v10; // rdx
  __int64 *v11; // rcx
  __int64 *v12; // rax
  __int64 *v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rbx
  const wchar_t *v17; // rdx
  __int64 *v18; // rcx
  __int64 *v19; // rax
  __int64 *v20; // rax
  __int64 *v21; // rax
  __int64 *v22; // rax
  __int64 *v23; // rax
  __int64 *v24; // rax
  __int64 *v25; // rax
  __int64 *v26; // rax
  const wchar_t *v27; // rdx
  __int64 *v28; // rcx
  __int64 *v29; // rax
  __int64 *v30; // rax
  __int64 *v31; // rax
  __int64 *v32; // rax
  __int64 *v33; // rax
  __int64 *v34; // rax
  __int64 *v35; // rax
  __int64 *v36; // rax
  const wchar_t *v37; // rdx
  __int64 *v38; // rcx
  __int64 *v39; // rax
  __int64 *v40; // rax
  __int64 *v41; // rax
  __int64 *v42; // rax
  __int64 *v43; // rax
  __int64 *v44; // rax
  __int64 *v45; // rax
  __int64 *v46; // rax
  const wchar_t *v47; // rdx
  __int64 *v48; // rcx
  __int64 *v49; // rax
  __int64 *v50; // rax
  __int64 *v51; // rax
  mlib::XmlStream *v52; // rdi
  const wchar_t *v53; // rdx
  __int64 *v54; // rcx
  __int64 *v55; // rax
  __int64 *v56; // rax
  int v57; // ebx
  const wchar_t *v58; // rdx
  __int64 *v59; // rcx
  __int64 *v60; // rax
  __int64 i; // rbx
  __int64 *v62; // rax
  char v63; // di
  __int64 *v64; // rax
  __int64 *v65; // rax
  __int64 *v66; // rax
  int v67; // edi
  __int64 *v68; // rdx
  __int64 v69; // rcx
  const wchar_t *v70; // rdx
  __int64 *v71; // rcx
  __int64 *v72; // rax
  __int64 *v73; // rax
  __int64 *v74; // rax
  __int64 *v75; // rax
  int v76; // edi
  const wchar_t *v77; // rdx
  __int64 *v78; // rcx
  __int64 *v79; // rax
  __int64 *v80; // rax
  __int64 *v81; // rax
  __int64 *v82; // rax
  mlib::XmlStream *v83; // rdi
  const wchar_t *v84; // rdx
  __int64 *v85; // rcx
  __int64 *v86; // rax
  __int64 *v87; // rax
  __int64 *v88; // rax
  __int64 *v89; // rax
  mlib::XmlStream *v90; // rdi
  const wchar_t *v91; // rdx
  __int64 *v92; // rcx
  __int64 *v93; // rax
  __int64 *v94; // rax
  __int64 *v95; // rax
  __int64 *v96; // rax
  __int64 *v97; // rdx
  __int64 v98; // rcx
  double v99; // xmm6_8
  __int64 *v100; // rdx
  __int64 v101; // rcx
  const wchar_t *v102; // rdx
  __int64 *v103; // rcx
  __int64 *v104; // rax
  __int64 *v105; // rax
  __int64 *v106; // rax
  __int64 *v107; // rax
  __int64 *v108; // rdx
  __int64 v109; // rcx
  double v110; // xmm6_8
  __int64 *v111; // rdx
  __int64 v112; // rcx
  const wchar_t *v113; // rdx
  __int64 *v114; // rcx
  __int64 *v115; // rax
  __int64 *v116; // rax
  __int64 *v117; // rax
  __int64 *v118; // rax
  __int64 *v119; // rax
  mlib::XmlStream *v120; // rdi
  const wchar_t *v121; // rdx
  __int64 *v122; // rcx
  __int64 *v123; // rax
  __int64 *v124; // rax
  __int64 *v125; // rax
  __int64 *v126; // rax
  mlib::XmlStream *v127; // rdi
  const wchar_t *v128; // rdx
  __int64 *v129; // rcx
  __int64 *v130; // rax
  __int64 *v131; // rax
  __int64 *v132; // rax
  __int64 *v133; // rax
  __int64 *v134; // rax
  mlib::XmlStream *v135; // rsi
  const wchar_t *v136; // rdx
  __int64 *v137; // rcx
  __int64 *v138; // rax
  __int64 *v139; // rax
  int v140; // edi
  __int64 *v141; // rax
  __int64 *v142; // rax
  __int64 *v143; // rax
  __int64 *v144; // rax
  mlib::XmlStream *v145; // rsi
  const wchar_t *v146; // rdx
  __int64 *v147; // rcx
  __int64 *v148; // rax
  __int64 *v149; // rax
  __int64 *v150; // rax
  __int64 *v151; // rax
  __int64 *v152; // rdx
  __int64 v153; // rcx
  double v154; // xmm6_8
  __int64 *v155; // rdx
  __int64 v156; // rcx
  const wchar_t *v157; // rdx
  __int64 *v158; // rcx
  __int64 *v159; // rax
  const wchar_t *v160; // rdx
  __int64 *v161; // rcx
  __int64 *v162; // rax
  __int64 *v163; // rax
  unsigned int v164; // edi
  const wchar_t *v165; // rdx
  __int64 *v166; // rcx
  __int64 *v167; // rax
  __int64 *v168; // rax
  int v169; // edi
  const wchar_t *v170; // rdx
  __int64 *v171; // rcx
  __int64 *v172; // rax
  __int64 *v173; // rax
  int v174; // edi
  const wchar_t *v175; // rdx
  __int64 *v176; // rcx
  __int64 *v177; // rax
  __int64 *v178; // rax
  unsigned int v179; // edi
  const wchar_t *v180; // rdx
  __int64 *v181; // rcx
  __int64 *v182; // rax
  __int64 *v183; // rax
  int v184; // edi
  const wchar_t *v185; // rdx
  __int64 *v186; // rcx
  __int64 *v187; // rax
  __int64 *v188; // rax
  __int64 *v189; // rax
  __int64 *v190; // rax
  __int64 *v191; // rax
  mlib::XmlStream *v192; // rdi
  const wchar_t *v193; // rdx
  __int64 *v194; // rcx
  __int64 *v195; // rax
  __int64 *v196; // rax
  __int64 *v197; // rdx
  __int64 v198; // rcx
  double v199; // xmm6_8
  __int64 *v200; // rdx
  __int64 v201; // rcx
  __int64 *v202; // rax
  __int64 *v203; // rax
  __int64 *v204; // rax
  __int64 *v205; // rdx
  __int64 v206; // rcx
  __int64 *v207; // rax
  __int64 *v208; // rax
  __int64 *v209; // rax
  __int64 *v210; // rax
  __int64 *v211; // rax
  mlib::XmlStream *v212; // rsi
  __int64 *v213; // rax
  int v214; // edi
  __int64 *v215; // rax
  __int64 *v216; // rax
  __int64 *v217; // rax
  mlib::XmlStream *v218; // rdi
  __int64 *v219; // rax
  __int64 *v220; // rax
  mlib::XmlStream *v221; // rsi
  int v222; // edi
  __int64 *v223; // rax
  __int64 *v224; // rax
  mlib::XmlStream *v225; // rdi
  int v226; // edi
  __int64 *v227; // rax
  __int64 *v228; // rax
  mlib::XmlStream *v229; // rdi
  WinSAT::DiskProfiler *v230; // rcx
  char v231; // di
  __int64 v232; // rdx
  DWORD v233; // ebx
  const wchar_t *v234; // rdi
  unsigned int v235; // ebx
  __int64 v237; // [rsp+28h] [rbp-E0h] BYREF
  unsigned __int64 *v238; // [rsp+30h] [rbp-D8h] BYREF
  unsigned __int64 *v239; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 *v240; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int64 *v241; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v242; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int64 *v243; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 *v244; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int64 *v245; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 *v246; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 *v247; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 *v248; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 *v249; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 *v250; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 *v251; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 *v252; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 *v253; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 *v254; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int64 *v255; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 *v256; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int64 *v257; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 *v258; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v259; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v260; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int64 *v261; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 *v262; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int64 *v263; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 *v264; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int64 *v265; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int64 *v266; // [rsp+110h] [rbp+8h] BYREF
  unsigned __int64 *v267; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int64 *v268; // [rsp+120h] [rbp+18h] BYREF
  unsigned __int64 *v269; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int64 *v270; // [rsp+130h] [rbp+28h] BYREF
  unsigned __int64 *v271; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int64 *v272; // [rsp+140h] [rbp+38h] BYREF
  unsigned __int64 *v273; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int64 *v274; // [rsp+150h] [rbp+48h] BYREF
  unsigned __int64 *v275; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int64 *v276; // [rsp+160h] [rbp+58h] BYREF
  unsigned __int64 *v277; // [rsp+168h] [rbp+60h] BYREF
  unsigned __int64 *v278; // [rsp+170h] [rbp+68h] BYREF
  unsigned __int64 *v279; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int64 *v280; // [rsp+180h] [rbp+78h] BYREF
  unsigned __int64 *v281; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int64 *v282; // [rsp+190h] [rbp+88h] BYREF
  unsigned __int64 *v283; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int64 *v284; // [rsp+1A0h] [rbp+98h] BYREF
  unsigned __int64 *v285; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int64 *v286; // [rsp+1B0h] [rbp+A8h] BYREF
  unsigned __int64 *v287; // [rsp+1B8h] [rbp+B0h] BYREF
  unsigned __int64 *v288; // [rsp+1C0h] [rbp+B8h] BYREF
  unsigned __int64 *v289; // [rsp+1C8h] [rbp+C0h] BYREF
  unsigned __int64 *v290; // [rsp+1D0h] [rbp+C8h] BYREF
  unsigned __int64 *v291; // [rsp+1D8h] [rbp+D0h] BYREF
  unsigned __int64 *v292; // [rsp+1E0h] [rbp+D8h] BYREF
  unsigned __int64 *v293; // [rsp+1E8h] [rbp+E0h] BYREF
  unsigned __int64 *v294; // [rsp+1F0h] [rbp+E8h] BYREF
  unsigned __int64 *v295; // [rsp+1F8h] [rbp+F0h] BYREF
  unsigned __int64 *v296; // [rsp+200h] [rbp+F8h] BYREF
  unsigned __int64 *v297; // [rsp+208h] [rbp+100h] BYREF
  unsigned __int64 *v298; // [rsp+210h] [rbp+108h] BYREF
  unsigned __int64 *v299; // [rsp+218h] [rbp+110h] BYREF
  unsigned __int64 *v300; // [rsp+220h] [rbp+118h] BYREF
  unsigned __int64 *v301; // [rsp+228h] [rbp+120h] BYREF
  unsigned __int64 *v302; // [rsp+230h] [rbp+128h] BYREF
  unsigned __int64 *v303[2]; // [rsp+238h] [rbp+130h] BYREF
  unsigned __int64 *v304; // [rsp+248h] [rbp+140h] BYREF
  unsigned __int64 *v305; // [rsp+250h] [rbp+148h] BYREF
  __int64 v306; // [rsp+258h] [rbp+150h] BYREF
  __int64 v307; // [rsp+260h] [rbp+158h] BYREF
  unsigned __int64 *v308; // [rsp+268h] [rbp+160h] BYREF
  unsigned __int64 *v309; // [rsp+270h] [rbp+168h] BYREF
  __int64 v310; // [rsp+278h] [rbp+170h] BYREF
  __int64 v311; // [rsp+280h] [rbp+178h] BYREF
  unsigned __int64 *v312; // [rsp+288h] [rbp+180h] BYREF
  unsigned __int64 *v313; // [rsp+290h] [rbp+188h] BYREF
  unsigned __int64 *v314; // [rsp+298h] [rbp+190h] BYREF
  __int64 v315; // [rsp+2A0h] [rbp+198h] BYREF
  unsigned __int64 *v316; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int64 v317; // [rsp+2B0h] [rbp+1A8h] BYREF
  unsigned __int64 *v318; // [rsp+2B8h] [rbp+1B0h] BYREF
  unsigned __int64 *v319; // [rsp+2C0h] [rbp+1B8h] BYREF
  __int64 v320; // [rsp+2C8h] [rbp+1C0h] BYREF
  unsigned __int64 *v321; // [rsp+2D0h] [rbp+1C8h] BYREF
  unsigned __int64 *v322; // [rsp+2D8h] [rbp+1D0h] BYREF
  __int64 v323; // [rsp+2E0h] [rbp+1D8h] BYREF
  __int64 v324; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int64 v325; // [rsp+2F0h] [rbp+1E8h] BYREF
  __int64 v326; // [rsp+2F8h] [rbp+1F0h] BYREF
  __int64 v327; // [rsp+300h] [rbp+1F8h] BYREF
  unsigned __int64 *v328; // [rsp+308h] [rbp+200h] BYREF
  __int64 v329; // [rsp+310h] [rbp+208h] BYREF
  __int64 v330; // [rsp+318h] [rbp+210h] BYREF
  unsigned __int64 *v331; // [rsp+320h] [rbp+218h] BYREF
  __int64 v332; // [rsp+328h] [rbp+220h] BYREF
  __int64 v333; // [rsp+330h] [rbp+228h] BYREF
  __int64 v334; // [rsp+338h] [rbp+230h] BYREF
  __int64 v335; // [rsp+340h] [rbp+238h] BYREF
  unsigned __int64 *v336; // [rsp+348h] [rbp+240h] BYREF
  __int64 v337; // [rsp+350h] [rbp+248h] BYREF
  __int64 v338; // [rsp+358h] [rbp+250h] BYREF
  __int64 v339; // [rsp+360h] [rbp+258h] BYREF
  _QWORD v340[2]; // [rsp+368h] [rbp+260h] BYREF
  __int64 v341; // [rsp+378h] [rbp+270h] BYREF
  __int64 v342; // [rsp+380h] [rbp+278h] BYREF
  __int64 v343; // [rsp+388h] [rbp+280h] BYREF
  __int64 v344; // [rsp+390h] [rbp+288h] BYREF
  __int64 v345; // [rsp+398h] [rbp+290h] BYREF
  unsigned __int64 *v346; // [rsp+3A0h] [rbp+298h] BYREF
  unsigned __int64 *v347[2]; // [rsp+3A8h] [rbp+2A0h] BYREF
  WCHAR Buffer[256]; // [rsp+3B8h] [rbp+2B0h] BYREF
  DWORD dwErrCode; // [rsp+5B8h] [rbp+4B0h]
  char v350; // [rsp+5BCh] [rbp+4B4h]
  __int64 v351; // [rsp+5C0h] [rbp+4B8h]

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v260,
    64);
  v4 = a1 - 8;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    &v260,
    L"\\\\.\\PhysicalDrive%d",
    *(unsigned int *)(a1 - 8 + 212));
  v5 = a2 + 1;
  if ( *(_QWORD *)(a1 + 416) )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v238,
      L"AvailableTempFileSize");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
    *v5 = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v6, &v238);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v239,
      L"units");
    *v5 = 3;
    v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v8 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v7, &v239);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"MB");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    v9 = *(_QWORD *)(a1 + 416) >> 20;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::basic_ostream<unsigned short>::operator<<(*a2, v9);
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v240,
      L"AvailableTempFileSize");
    --*((_DWORD *)a2 + 3);
    if ( *v5 == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      *((_BYTE *)a2 + 17) = 0;
      v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
      v11 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v12, &v240);
      v10 = L">";
    }
    else
    {
      if ( *v5 != 2 )
      {
LABEL_11:
        *v5 = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v240);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v239);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v238);
        goto LABEL_12;
      }
      v10 = L"/>";
      v11 = (__int64 *)*a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, (__int64)v10);
    goto LABEL_11;
  }
LABEL_12:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v238,
    L"UsedTempFileSize");
  if ( *v5 == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
  *v5 = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v13, &v238);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v239,
    L"units");
  *v5 = 3;
  v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
  v15 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v14, &v239);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, (__int64)L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"MB");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  v16 = *(_QWORD *)(a1 + 272) >> 20;
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2, v16);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v240,
    L"UsedTempFileSize");
  --*((_DWORD *)a2 + 3);
  if ( *v5 == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
    v18 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v19, &v240);
    v17 = L">";
  }
  else
  {
    if ( *v5 != 2 )
      goto LABEL_21;
    v17 = L"/>";
    v18 = (__int64 *)*a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, (__int64)v17);
LABEL_21:
  *v5 = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v240);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v239);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v238);
  if ( !*(_DWORD *)(a1 + 192) )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v258,
      L"Units");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
    *v5 = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v20, &v258);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v257,
      L"name");
    *v5 = 3;
    v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v22 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v21, &v257);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v256,
      L"units");
    *v5 = 3;
    v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v24 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v23, &v256);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v255,
      L"descrip");
    *v5 = 3;
    v25 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v26 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v25, &v255);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v254,
      L"Units");
    --*((_DWORD *)a2 + 3);
    if ( *v5 == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      *((_BYTE *)a2 + 17) = 0;
      v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
      v28 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v29, &v254);
      v27 = L">";
    }
    else
    {
      if ( *v5 != 2 )
        goto LABEL_31;
      v27 = L"/>";
      v28 = (__int64 *)*a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, (__int64)v27);
LABEL_31:
    *v5 = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v253,
      L"Units");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
    *v5 = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v30, &v253);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v241,
      L"name");
    *v5 = 3;
    v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v32 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v31, &v241);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"mbs");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v243,
      L"units");
    *v5 = 3;
    v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v34 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v33, &v243);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"MB/s");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v244,
      L"descrip");
    *v5 = 3;
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v36 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v35, &v244);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"megabytes per second");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v245,
      L"Units");
    --*((_DWORD *)a2 + 3);
    if ( *v5 == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      *((_BYTE *)a2 + 17) = 0;
      v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
      v38 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v39, &v245);
      v37 = L">";
    }
    else
    {
      if ( *v5 != 2 )
        goto LABEL_40;
      v37 = L"/>";
      v38 = (__int64 *)*a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v38, (__int64)v37);
LABEL_40:
    *v5 = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v246,
      L"Units");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
    *v5 = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    v40 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v40, &v246);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v247,
      L"name");
    *v5 = 3;
    v41 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v42 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v41, &v247);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"us");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v248,
      L"units");
    *v5 = 3;
    v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v44 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v43, &v248);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"us");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v249,
      L"descrip");
    *v5 = 3;
    v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
    v46 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v45, &v249);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v46, (__int64)L"=");
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"microseconds");
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v250,
      L"Units");
    --*((_DWORD *)a2 + 3);
    if ( *v5 == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      *((_BYTE *)a2 + 17) = 0;
      v49 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
      v48 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v49, &v250);
      v47 = L">";
    }
    else
    {
      if ( *v5 != 2 )
        goto LABEL_49;
      v47 = L"/>";
      v48 = (__int64 *)*a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, (__int64)v47);
LABEL_49:
    *v5 = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v251,
      L"PerDiskData");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
    *v5 = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    v50 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v50, &v251);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v252,
      L"Disk");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
    *v5 = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    v51 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v51, &v252);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    v237 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v237,
      v260);
    v52 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
            (mlib::XmlStream *)a2,
            &v237);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v238,
      L"Disk");
    --*((_DWORD *)v52 + 3);
    if ( *((_DWORD *)v52 + 2) == 1 )
    {
      if ( !*((_BYTE *)v52 + 17) )
        mlib::XmlStream::Indent(v52);
      *((_BYTE *)v52 + 17) = 0;
      v55 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v52, (__int64)L"</");
      v54 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v55, &v238);
      v53 = L">";
    }
    else
    {
      if ( *((_DWORD *)v52 + 2) != 2 )
        goto LABEL_60;
      v53 = L"/>";
      v54 = *(__int64 **)v52;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, (__int64)v53);
LABEL_60:
    *((_DWORD *)v52 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v239,
      L"RandomSeed");
    if ( *((_DWORD *)v52 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v52, (__int64)L">");
    *((_DWORD *)v52 + 2) = 2;
    mlib::XmlStream::Indent(v52);
    v56 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v52, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v56, &v239);
    ++*((_DWORD *)v52 + 3);
    *((_BYTE *)v52 + 17) = 0;
    v57 = *(_DWORD *)(a1 + 268);
    mlib::XmlStream::BeforeText(v52);
    std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v52, v57);
    mlib::XmlStream::AfterText(v52);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v240,
      L"RandomSeed");
    --*((_DWORD *)v52 + 3);
    if ( *((_DWORD *)v52 + 2) == 1 )
    {
      if ( !*((_BYTE *)v52 + 17) )
        mlib::XmlStream::Indent(v52);
      *((_BYTE *)v52 + 17) = 0;
      v60 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v52, (__int64)L"</");
      v59 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v60, &v240);
      v58 = L">";
    }
    else
    {
      if ( *((_DWORD *)v52 + 2) != 2 )
      {
LABEL_69:
        *((_DWORD *)v52 + 2) = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v240);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v239);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v238);
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
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v241);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v253);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v254);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v255);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v256);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v257);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v258);
        for ( i = *(_QWORD *)(a1 + 64); ; i += 488 )
        {
          if ( i == *(_QWORD *)(a1 + 72) )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v242,
              L"PerDiskData");
            mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v242);
            v4 = a1 - 8;
            goto LABEL_277;
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v237,
            32);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            (__int64 *)&v240,
            32);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v258,
            L"Zone");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v62 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v62, &v258);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v258);
          v63 = WinSAT::DiskProfiler::OpModeToString(*(unsigned int *)(i + 208), &v240);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v257,
            L"ModeFlags");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v64 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v64, &v257);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v257);
          if ( v63 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v256,
              L"friendlyName");
            *v5 = 3;
            v65 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
            v66 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v65,
                    &v256);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v66, (__int64)L"=");
            v243 = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v243,
              (__int64)v240);
            mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
              (mlib::XmlStream *)a2,
              &v243);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v256);
          }
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"0x");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          LODWORD(v241) = 8;
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, &v241);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v67 = *(_DWORD *)(i + 208);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v67);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v68 = (__int64 *)*a2;
          v69 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v68 + v69 + 24) |= 0x201u;
          *(_WORD *)((char *)v68 + *(int *)(*v68 + 4) + 88) = 32;
          *(__int64 *)((char *)v68 + *(int *)(*v68 + 4) + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v255,
            L"ModeFlags");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            v72 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
            v71 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v72,
                    &v255);
            v70 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_84;
            v70 = L"/>";
            v71 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v71, (__int64)v70);
LABEL_84:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v255);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v346,
            L"IoSize");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v73 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v73, &v346);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v253,
            L"units");
          *v5 = 3;
          v74 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v75 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v74,
                  &v253);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v75, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v76 = *(_DWORD *)(i + 212);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v76);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v254,
            L"IoSize");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            v79 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
            v78 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v79,
                    &v254);
            v77 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_93;
            v77 = L"/>";
            v78 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v78, (__int64)v77);
LABEL_93:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v254);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v253);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v346);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"0x%010I64x",
            *(_QWORD *)(i + 176));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v262,
            L"ZoneStart");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v80 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v80, &v262);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v261,
            L"units");
          *v5 = 3;
          v81 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v82 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v81,
                  &v261);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v82, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v244 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v244,
            v237);
          v83 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                  (mlib::XmlStream *)a2,
                  &v244);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v347,
            L"ZoneStart");
          --*((_DWORD *)v83 + 3);
          if ( *((_DWORD *)v83 + 2) == 1 )
          {
            if ( !*((_BYTE *)v83 + 17) )
              mlib::XmlStream::Indent(v83);
            *((_BYTE *)v83 + 17) = 0;
            v86 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v83, (__int64)L"</");
            v85 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v86,
                    v347);
            v84 = L">";
          }
          else
          {
            if ( *((_DWORD *)v83 + 2) != 2 )
              goto LABEL_102;
            v84 = L"/>";
            v85 = *(__int64 **)v83;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, (__int64)v84);
LABEL_102:
          *((_DWORD *)v83 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v347);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v261);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v262);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"0x%010I64x",
            *(_QWORD *)(i + 184));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v265,
            L"ZoneEnd");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v87 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v87, &v265);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v264,
            L"units");
          *v5 = 3;
          v88 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v89 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v88,
                  &v264);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v89, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v245 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v245,
            v237);
          v90 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                  (mlib::XmlStream *)a2,
                  &v245);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v263,
            L"ZoneEnd");
          --*((_DWORD *)v90 + 3);
          if ( *((_DWORD *)v90 + 2) == 1 )
          {
            if ( !*((_BYTE *)v90 + 17) )
              mlib::XmlStream::Indent(v90);
            *((_BYTE *)v90 + 17) = 0;
            v93 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v90, (__int64)L"</");
            v92 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v93,
                    &v263);
            v91 = L">";
          }
          else
          {
            if ( *((_DWORD *)v90 + 2) != 2 )
              goto LABEL_111;
            v91 = L"/>";
            v92 = *(__int64 **)v90;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v92, (__int64)v91);
LABEL_111:
          *((_DWORD *)v90 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v263);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v264);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v265);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v271,
            L"Throughput");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v94 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v94, &v271);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v270,
            L"units");
          *v5 = 3;
          v95 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v96 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v95,
                  &v270);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v96, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"mbs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v97 = (__int64 *)*a2;
          v98 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v97 + v98 + 24) |= 0x2080u;
          *(__int64 *)((char *)v97 + *(int *)(*v97 + 4) + 32) = 2;
          *(__int64 *)((char *)v97 + *(int *)(*v97 + 4) + 40) = 4;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v99 = *(double *)(i + 192);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v99);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v100 = (__int64 *)*a2;
          v101 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v100 + v101 + 24) |= 0x201u;
          *(_WORD *)((char *)v100 + *(int *)(*v100 + 4) + 88) = 32;
          *(__int64 *)((char *)v100 + *(int *)(*v100 + 4) + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v269,
            L"Throughput");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            v104 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
            v103 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v104,
                     &v269);
            v102 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_120;
            v102 = L"/>";
            v103 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v103, (__int64)v102);
LABEL_120:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v268,
            L"IssueTime");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v105 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v105, &v268);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v267,
            L"units");
          *v5 = 3;
          v106 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v107 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v106,
                   &v267);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v107, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"us");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v108 = (__int64 *)*a2;
          v109 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v108 + v109 + 24) |= 0x2080u;
          *(__int64 *)((char *)v108 + *(int *)(*v108 + 4) + 32) = 4;
          *(__int64 *)((char *)v108 + *(int *)(*v108 + 4) + 40) = 4;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v110 = *(double *)(i + 200);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v110);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v111 = (__int64 *)*a2;
          v112 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)((char *)v111 + v112 + 24) |= 0x201u;
          *(_WORD *)((char *)v111 + *(int *)(*v111 + 4) + 88) = 32;
          *(__int64 *)((char *)v111 + *(int *)(*v111 + 4) + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v266,
            L"IssueTime");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            v115 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
            v114 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v115,
                     &v266);
            v113 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_129;
            v113 = L"/>";
            v114 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v114, (__int64)v113);
LABEL_129:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v266);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v267);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v268);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v269);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v270);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v271);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v272,
            L"ETWData");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v116 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v116, &v272);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v272);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"0x%010I64x",
            *(_QWORD *)i);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v275,
            L"MinOffset");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v117 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v117, &v275);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v274,
            L"units");
          *v5 = 3;
          v118 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v119 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v118,
                   &v274);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v119, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, "bytes");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v246 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v246,
            v237);
          v120 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                   (mlib::XmlStream *)a2,
                   &v246);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v273,
            L"MinOffset");
          --*((_DWORD *)v120 + 3);
          if ( *((_DWORD *)v120 + 2) == 1 )
          {
            if ( !*((_BYTE *)v120 + 17) )
              mlib::XmlStream::Indent(v120);
            *((_BYTE *)v120 + 17) = 0;
            v123 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v120, (__int64)L"</");
            v122 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v123,
                     &v273);
            v121 = L">";
          }
          else
          {
            if ( *((_DWORD *)v120 + 2) != 2 )
              goto LABEL_140;
            v121 = L"/>";
            v122 = *(__int64 **)v120;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v122, (__int64)v121);
LABEL_140:
          *((_DWORD *)v120 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v273);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v274);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v275);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"0x%010I64x",
            *(_QWORD *)(i + 8));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v281,
            L"MaxOffset");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v124 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v124, &v281);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v280,
            L"units");
          *v5 = 3;
          v125 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v126 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v125,
                   &v280);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v126, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, "bytes");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v247 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v247,
            v237);
          v127 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                   (mlib::XmlStream *)a2,
                   &v247);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v279,
            L"MaxOffset");
          --*((_DWORD *)v127 + 3);
          if ( *((_DWORD *)v127 + 2) == 1 )
          {
            if ( !*((_BYTE *)v127 + 17) )
              mlib::XmlStream::Indent(v127);
            *((_BYTE *)v127 + 17) = 0;
            v130 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v127, (__int64)L"</");
            v129 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v130,
                     &v279);
            v128 = L">";
          }
          else
          {
            if ( *((_DWORD *)v127 + 2) != 2 )
              goto LABEL_149;
            v128 = L"/>";
            v129 = *(__int64 **)v127;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v129, (__int64)v128);
LABEL_149:
          *((_DWORD *)v127 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v278,
            L"AssessmentIOs");
          if ( *((_DWORD *)v127 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v127, (__int64)L">");
          *((_DWORD *)v127 + 2) = 2;
          mlib::XmlStream::Indent(v127);
          v131 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v127, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v131, &v278);
          ++*((_DWORD *)v127 + 3);
          *((_BYTE *)v127 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v277,
            L"TotalData");
          if ( *((_DWORD *)v127 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v127, (__int64)L">");
          *((_DWORD *)v127 + 2) = 2;
          mlib::XmlStream::Indent(v127);
          v132 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v127, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v132, &v277);
          ++*((_DWORD *)v127 + 3);
          *((_BYTE *)v127 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v276,
            L"units");
          *((_DWORD *)v127 + 2) = 3;
          v133 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v127, (__int64)L" ");
          v134 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v133,
                   &v276);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v134, (__int64)L"=");
          mlib::XmlStream::BeforeText(v127);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v127, "bytes");
          mlib::XmlStream::AfterText(v127);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v276);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v277);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v278);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v279);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v280);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v281);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"%I64u",
            *(_QWORD *)(i + 16));
          v241 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v241,
            v237);
          v135 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                   (mlib::XmlStream *)a2,
                   &v241);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v284,
            L"TotalData");
          --*((_DWORD *)v135 + 3);
          if ( *((_DWORD *)v135 + 2) == 1 )
          {
            if ( !*((_BYTE *)v135 + 17) )
              mlib::XmlStream::Indent(v135);
            *((_BYTE *)v135 + 17) = 0;
            v138 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v135, (__int64)L"</");
            v137 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v138,
                     &v284);
            v136 = L">";
          }
          else
          {
            if ( *((_DWORD *)v135 + 2) != 2 )
              goto LABEL_160;
            v136 = L"/>";
            v137 = *(__int64 **)v135;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, (__int64)v136);
LABEL_160:
          *((_DWORD *)v135 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v283,
            L"Count");
          if ( *((_DWORD *)v135 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v135, (__int64)L">");
          *((_DWORD *)v135 + 2) = 2;
          mlib::XmlStream::Indent(v135);
          v139 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v135, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v139, &v283);
          ++*((_DWORD *)v135 + 3);
          *((_BYTE *)v135 + 17) = 0;
          v140 = *(_DWORD *)(i + 112);
          mlib::XmlStream::BeforeText(v135);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v135, v140);
          mlib::XmlStream::AfterText(v135);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v282,
            L"Count");
          --*((_DWORD *)v135 + 3);
          if ( *((_DWORD *)v135 + 2) == 1 )
          {
            if ( !*((_BYTE *)v135 + 17) )
              mlib::XmlStream::Indent(v135);
            *((_BYTE *)v135 + 17) = 0;
            v148 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v135, (__int64)L"</");
            v149 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v148,
                     &v282);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v149, (__int64)L">");
          }
          else if ( *((_DWORD *)v135 + 2) == 2 )
          {
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v135, (__int64)L"/>");
          }
          *((_DWORD *)v135 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v282);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v283);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v284);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v286,
            L"ServiceTime");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v141 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v141, &v286);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v285,
            L"units");
          *v5 = 3;
          v142 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v143 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v142,
                   &v285);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v143, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"us");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v285);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v286);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"%I64u",
            *(_QWORD *)(i + 40));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v297,
            L"Total");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v144 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v144, &v297);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v248 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v248,
            v237);
          v145 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                   (mlib::XmlStream *)a2,
                   &v248);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v296,
            L"Total");
          --*((_DWORD *)v145 + 3);
          if ( *((_DWORD *)v145 + 2) == 1 )
          {
            if ( !*((_BYTE *)v145 + 17) )
              mlib::XmlStream::Indent(v145);
            *((_BYTE *)v145 + 17) = 0;
            v150 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"</");
            v147 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v150,
                     &v296);
            v146 = L">";
          }
          else
          {
            if ( *((_DWORD *)v145 + 2) != 2 )
              goto LABEL_179;
            v146 = L"/>";
            v147 = *(__int64 **)v145;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v147, (__int64)v146);
LABEL_179:
          *((_DWORD *)v145 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v295,
            L"Average");
          if ( *((_DWORD *)v145 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L">");
          *((_DWORD *)v145 + 2) = 2;
          mlib::XmlStream::Indent(v145);
          v151 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v151, &v295);
          ++*((_DWORD *)v145 + 3);
          *((_BYTE *)v145 + 17) = 0;
          mlib::XmlStream::BeforeText(v145);
          v152 = *(__int64 **)v145;
          v153 = *(int *)(**(_QWORD **)v145 + 4LL);
          *(_DWORD *)((char *)v152 + v153 + 24) |= 0x2080u;
          *(__int64 *)((char *)v152 + *(int *)(*v152 + 4) + 32) = 2;
          *(__int64 *)((char *)v152 + *(int *)(*v152 + 4) + 40) = 4;
          mlib::XmlStream::AfterText(v145);
          v154 = *(double *)(i + 104);
          mlib::XmlStream::BeforeText(v145);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v145, v154);
          mlib::XmlStream::AfterText(v145);
          mlib::XmlStream::BeforeText(v145);
          v155 = *(__int64 **)v145;
          v156 = *(int *)(**(_QWORD **)v145 + 4LL);
          *(_DWORD *)((char *)v155 + v156 + 24) |= 0x201u;
          *(_WORD *)((char *)v155 + *(int *)(*v155 + 4) + 88) = 32;
          *(__int64 *)((char *)v155 + *(int *)(*v155 + 4) + 40) = 0;
          mlib::XmlStream::AfterText(v145);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v294,
            L"Average");
          --*((_DWORD *)v145 + 3);
          if ( *((_DWORD *)v145 + 2) == 1 )
          {
            if ( !*((_BYTE *)v145 + 17) )
              mlib::XmlStream::Indent(v145);
            *((_BYTE *)v145 + 17) = 0;
            v159 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"</");
            v158 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v159,
                     &v294);
            v157 = L">";
          }
          else
          {
            if ( *((_DWORD *)v145 + 2) != 2 )
              goto LABEL_188;
            v157 = L"/>";
            v158 = *(__int64 **)v145;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v158, (__int64)v157);
LABEL_188:
          *((_DWORD *)v145 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v293,
            L"ServiceTime");
          --*((_DWORD *)v145 + 3);
          if ( *((_DWORD *)v145 + 2) == 1 )
          {
            if ( !*((_BYTE *)v145 + 17) )
              mlib::XmlStream::Indent(v145);
            *((_BYTE *)v145 + 17) = 0;
            v162 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"</");
            v161 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v162,
                     &v293);
            v160 = L">";
          }
          else
          {
            if ( *((_DWORD *)v145 + 2) != 2 )
              goto LABEL_195;
            v160 = L"/>";
            v161 = *(__int64 **)v145;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v161, (__int64)v160);
LABEL_195:
          *((_DWORD *)v145 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v292,
            L"AllowedInterference");
          if ( *((_DWORD *)v145 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L">");
          *((_DWORD *)v145 + 2) = 2;
          mlib::XmlStream::Indent(v145);
          v163 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v163, &v292);
          ++*((_DWORD *)v145 + 3);
          *((_BYTE *)v145 + 17) = 0;
          v164 = *(_DWORD *)(a1 + 424) * *(_DWORD *)(i + 112) / 0x64u;
          mlib::XmlStream::BeforeText(v145);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v145, v164);
          mlib::XmlStream::AfterText(v145);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v291,
            L"AllowedInterference");
          --*((_DWORD *)v145 + 3);
          if ( *((_DWORD *)v145 + 2) == 1 )
          {
            if ( !*((_BYTE *)v145 + 17) )
              mlib::XmlStream::Indent(v145);
            *((_BYTE *)v145 + 17) = 0;
            v167 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"</");
            v166 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v167,
                     &v291);
            v165 = L">";
          }
          else
          {
            if ( *((_DWORD *)v145 + 2) != 2 )
              goto LABEL_204;
            v165 = L"/>";
            v166 = *(__int64 **)v145;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v166, (__int64)v165);
LABEL_204:
          *((_DWORD *)v145 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v290,
            L"InterferenceCount");
          if ( *((_DWORD *)v145 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L">");
          *((_DWORD *)v145 + 2) = 2;
          mlib::XmlStream::Indent(v145);
          v168 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v168, &v290);
          ++*((_DWORD *)v145 + 3);
          *((_BYTE *)v145 + 17) = 0;
          v169 = *(_DWORD *)(i + 140);
          mlib::XmlStream::BeforeText(v145);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v145, v169);
          mlib::XmlStream::AfterText(v145);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v289,
            L"InterferenceCount");
          --*((_DWORD *)v145 + 3);
          if ( *((_DWORD *)v145 + 2) == 1 )
          {
            if ( !*((_BYTE *)v145 + 17) )
              mlib::XmlStream::Indent(v145);
            *((_BYTE *)v145 + 17) = 0;
            v172 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"</");
            v171 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v172,
                     &v289);
            v170 = L">";
          }
          else
          {
            if ( *((_DWORD *)v145 + 2) != 2 )
              goto LABEL_213;
            v170 = L"/>";
            v171 = *(__int64 **)v145;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v171, (__int64)v170);
LABEL_213:
          *((_DWORD *)v145 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v288,
            L"PermittedInterferencePercentage");
          if ( *((_DWORD *)v145 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L">");
          *((_DWORD *)v145 + 2) = 2;
          mlib::XmlStream::Indent(v145);
          v173 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v173, &v288);
          ++*((_DWORD *)v145 + 3);
          *((_BYTE *)v145 + 17) = 0;
          v174 = *(_DWORD *)(a1 + 424);
          mlib::XmlStream::BeforeText(v145);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v145, v174);
          mlib::XmlStream::AfterText(v145);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v287,
            L"PermittedInterferencePercentage");
          --*((_DWORD *)v145 + 3);
          if ( *((_DWORD *)v145 + 2) == 1 )
          {
            if ( !*((_BYTE *)v145 + 17) )
              mlib::XmlStream::Indent(v145);
            *((_BYTE *)v145 + 17) = 0;
            v177 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v145, (__int64)L"</");
            v176 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v177,
                     &v287);
            v175 = L">";
          }
          else
          {
            if ( *((_DWORD *)v145 + 2) != 2 )
              goto LABEL_222;
            v175 = L"/>";
            v176 = *(__int64 **)v145;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v176, (__int64)v175);
LABEL_222:
          *((_DWORD *)v145 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v287);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v291);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v292);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v293);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v294);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v295);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v296);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v297);
          if ( !*(_DWORD *)(i + 112) )
            goto LABEL_233;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v299,
            L"ActualInterferencePercentage");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v178 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v178, &v299);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v179 = (unsigned int)(100 * *(_DWORD *)(i + 140)) / *(_DWORD *)(i + 112);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v179);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v298,
            L"ActualInterferencePercentage");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            v182 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
            v181 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v182,
                     &v298);
            v180 = L">";
            goto LABEL_231;
          }
          if ( *v5 == 2 )
          {
            v180 = L"/>";
            v181 = (__int64 *)*a2;
LABEL_231:
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v181, (__int64)v180);
          }
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v298);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v299);
LABEL_233:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v301,
            L"InterferenceCountWithReads");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v183 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v183, &v301);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v184 = *(_DWORD *)(i + 144);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v184);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v300,
            L"InterferenceCountWithReads");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            v187 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"</");
            v186 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v187,
                     &v300);
            v185 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_242;
            v185 = L"/>";
            v186 = (__int64 *)*a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v186, (__int64)v185);
LABEL_242:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v300);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v301);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v303,
            L"IOTime");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v188 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v188, v303);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v302,
            L"units");
          *v5 = 3;
          v189 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v190 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v189,
                   &v302);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v190, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"us");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v302);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v303);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"%I64u",
            *(_QWORD *)(i + 48));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v314,
            L"Total");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v191 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v191, &v314);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v249 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v249,
            v237);
          v192 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                   (mlib::XmlStream *)a2,
                   &v249);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v313,
            L"Total");
          --*((_DWORD *)v192 + 3);
          if ( *((_DWORD *)v192 + 2) == 1 )
          {
            if ( !*((_BYTE *)v192 + 17) )
              mlib::XmlStream::Indent(v192);
            *((_BYTE *)v192 + 17) = 0;
            v195 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L"</");
            v194 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v195,
                     &v313);
            v193 = L">";
          }
          else
          {
            if ( *((_DWORD *)v192 + 2) != 2 )
              goto LABEL_253;
            v193 = L"/>";
            v194 = *(__int64 **)v192;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v194, (__int64)v193);
LABEL_253:
          *((_DWORD *)v192 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v312,
            L"Average");
          if ( *((_DWORD *)v192 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L">");
          *((_DWORD *)v192 + 2) = 2;
          mlib::XmlStream::Indent(v192);
          v196 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v196, &v312);
          ++*((_DWORD *)v192 + 3);
          *((_BYTE *)v192 + 17) = 0;
          mlib::XmlStream::BeforeText(v192);
          v197 = *(__int64 **)v192;
          v198 = *(int *)(**(_QWORD **)v192 + 4LL);
          *(_DWORD *)((char *)v197 + v198 + 24) |= 0x2080u;
          *(__int64 *)((char *)v197 + *(int *)(*v197 + 4) + 32) = 2;
          *(__int64 *)((char *)v197 + *(int *)(*v197 + 4) + 40) = 4;
          mlib::XmlStream::AfterText(v192);
          v199 = *(double *)(i + 96);
          mlib::XmlStream::BeforeText(v192);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v192, v199);
          mlib::XmlStream::AfterText(v192);
          mlib::XmlStream::BeforeText(v192);
          v200 = *(__int64 **)v192;
          v201 = *(int *)(**(_QWORD **)v192 + 4LL);
          *(_DWORD *)((char *)v200 + v201 + 24) |= 0x201u;
          *(_WORD *)((char *)v200 + *(int *)(*v200 + 4) + 88) = 32;
          *(__int64 *)((char *)v200 + *(int *)(*v200 + 4) + 40) = 0;
          mlib::XmlStream::AfterText(v192);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v311,
            L"Average");
          mlib::XmlStream::WriteEndTag(v192);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v310,
            L"IOTime");
          mlib::XmlStream::WriteEndTag(v192);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v309,
            L"AvgIOTimeToSrvTimeDelta");
          if ( *((_DWORD *)v192 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L">");
          *((_DWORD *)v192 + 2) = 2;
          mlib::XmlStream::Indent(v192);
          v202 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v202, &v309);
          ++*((_DWORD *)v192 + 3);
          *((_BYTE *)v192 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v308,
            L"units");
          *((_DWORD *)v192 + 2) = 3;
          v203 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L" ");
          v204 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v203,
                   &v308);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v204, (__int64)L"=");
          mlib::XmlStream::BeforeText(v192);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L"us");
          mlib::XmlStream::AfterText(v192);
          v303[1] = (unsigned __int64 *)0x200000004LL;
          mlib::XmlStream::WriteText<mlib::_ffixedobj>(v192, 0x200000004LL);
          mlib::XmlStream::WriteText<double>(v192);
          mlib::XmlStream::BeforeText(v192);
          v205 = *(__int64 **)v192;
          v206 = *(int *)(**(_QWORD **)v192 + 4LL);
          *(_DWORD *)((char *)v205 + v206 + 24) |= 0x201u;
          *(_WORD *)((char *)v205 + *(int *)(*v205 + 4) + 88) = 32;
          *(__int64 *)((char *)v205 + *(int *)(*v205 + 4) + 40) = 0;
          mlib::XmlStream::AfterText(v192);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v307,
            L"AvgIOTimeToSrvTimeDelta");
          mlib::XmlStream::WriteEndTag(v192);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v306,
            L"AssessmentIOs");
          mlib::XmlStream::WriteEndTag(v192);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v305,
            L"NonAssessmentIOs");
          if ( *((_DWORD *)v192 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L">");
          *((_DWORD *)v192 + 2) = 2;
          mlib::XmlStream::Indent(v192);
          v207 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v207, &v305);
          ++*((_DWORD *)v192 + 3);
          *((_BYTE *)v192 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v304,
            L"Reads");
          if ( *((_DWORD *)v192 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L">");
          *((_DWORD *)v192 + 2) = 2;
          mlib::XmlStream::Indent(v192);
          v208 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v192, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v208, &v304);
          ++*((_DWORD *)v192 + 3);
          *((_BYTE *)v192 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v304);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v305);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v306);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v307);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v308);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v309);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v310);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v311);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v312);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v313);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v314);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"%I64u",
            *(_QWORD *)(i + 24));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v319,
            L"TotalData");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
          *v5 = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          v209 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v209, &v319);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v318,
            L"units");
          *v5 = 3;
          v210 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v211 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v210,
                   &v318);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v211, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v250 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v250,
            v237);
          v212 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                   (mlib::XmlStream *)a2,
                   &v250);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v317,
            L"TotalData");
          mlib::XmlStream::WriteEndTag(v212);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v316,
            L"Count");
          if ( *((_DWORD *)v212 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v212, (__int64)L">");
          *((_DWORD *)v212 + 2) = 2;
          mlib::XmlStream::Indent(v212);
          v213 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v212, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v213, &v316);
          ++*((_DWORD *)v212 + 3);
          *((_BYTE *)v212 + 17) = 0;
          v214 = *(_DWORD *)(i + 116);
          mlib::XmlStream::BeforeText(v212);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v212, v214);
          mlib::XmlStream::AfterText(v212);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v315,
            L"Count");
          mlib::XmlStream::WriteEndTag(v212);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v315);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v316);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v317);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v318);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v319);
          if ( (*(_DWORD *)(i + 208) & 0x10000000) != 0 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
              &v237,
              L"%I64u",
              *(_QWORD *)(i + 56));
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v322,
              L"ServiceTime");
            if ( *v5 == 2 )
              std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L">");
            *v5 = 2;
            mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            v215 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"<");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v215, &v322);
            ++*((_DWORD *)a2 + 3);
            *((_BYTE *)a2 + 17) = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v321,
              L"units");
            *v5 = 3;
            v216 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
            v217 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v216,
                     &v321);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v217, (__int64)L"=");
            mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"us");
            mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
            v251 = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v251,
              v237);
            v218 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                     (mlib::XmlStream *)a2,
                     &v251);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v320,
              L"ServiceTime");
            mlib::XmlStream::WriteEndTag(v218);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v320);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v321);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v322);
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v324,
            L"Reads");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v323,
            L"Writes");
          mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v323);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v324);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v237,
            L"%I64u",
            *(_QWORD *)(i + 32));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v329,
            L"TotalData");
          mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v328,
            L"units");
          *v5 = 3;
          v219 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
          v220 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v219,
                   &v328);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v220, (__int64)L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"bytes");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          v252 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v252,
            v237);
          v221 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                   (mlib::XmlStream *)a2,
                   &v252);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v327,
            L"TotalData");
          mlib::XmlStream::WriteEndTag(v221);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v326,
            L"Count");
          mlib::XmlStream::WriteBeginTag(v221);
          v222 = *(_DWORD *)(i + 120);
          mlib::XmlStream::BeforeText(v221);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v221, v222);
          mlib::XmlStream::AfterText(v221);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v325,
            L"Count");
          mlib::XmlStream::WriteEndTag(v221);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v325);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v326);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v327);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v328);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v329);
          if ( (*(_DWORD *)(i + 208) & 0x10000000) != 0 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
              &v237,
              L"%I64u",
              *(_QWORD *)(i + 64));
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v332,
              L"ServiceTime");
            mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v331,
              L"units");
            *v5 = 3;
            v223 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
            v224 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v223,
                     &v331);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v224, (__int64)L"=");
            mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"us");
            mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
            v238 = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v238,
              v237);
            v225 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                     (mlib::XmlStream *)a2,
                     &v238);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v330,
              L"ServiceTime");
            mlib::XmlStream::WriteEndTag(v225);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v330);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v331);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v332);
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v333,
            L"Writes");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v333);
          if ( (*(_DWORD *)(i + 208) & 0x10000000) != 0 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
              &v237,
              L"%I64u",
              *(_QWORD *)(i + 72));
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v340,
              L"Flushes");
            mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v339,
              L"Count");
            mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
            v226 = *(_DWORD *)(i + 124);
            mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
            std::basic_ostream<unsigned short>::operator<<(*a2, v226);
            mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v338,
              L"Count");
            mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v337,
              L"ServiceTime");
            mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v336,
              L"units");
            *v5 = 3;
            v227 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L" ");
            v228 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v227,
                     &v336);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v228, (__int64)L"=");
            mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)L"us");
            mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
            v239 = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v239,
              v237);
            v229 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
                     (mlib::XmlStream *)a2,
                     &v239);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v335,
              L"ServiceTime");
            mlib::XmlStream::WriteEndTag(v229);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v334,
              L"Flushes");
            mlib::XmlStream::WriteEndTag(v229);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v334);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v335);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v336);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v337);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v338);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v339);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v340);
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v343,
            L"NonAssessmentIOs");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v342,
            L"Throughput");
          mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
          v340[1] = 0x200000004LL;
          mlib::XmlStream::WriteText<mlib::_ffixedobj>((mlib::XmlStream *)a2, 0x200000004LL);
          mlib::XmlStream::WriteText<double>((mlib::XmlStream *)a2);
          mlib::XmlStream::WriteText<mlib::_normobj>((mlib::XmlStream *)a2, 0);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v341,
            L"Throughput");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v341);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v342);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v343);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v344,
            L"ETWData");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v344);
          if ( (*(_DWORD *)(i + 208) & 0xC000000) != 0 )
            WinSAT::DiskProfiler::OutputResultsForFlushProfile(
              v230,
              (struct mlib::XmlStream *)a2,
              (const struct WinSAT::DiskProfiler::DiskProfResult *)i);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v259,
            L"Interference");
          mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
          v231 = *(_BYTE *)(i + 149);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          LOBYTE(v232) = v231;
          std::basic_ostream<unsigned short>::operator<<(*a2, v232);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v345,
            L"Interference");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v345);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v259);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v242,
            L"Zone");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v242);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v240);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v237);
        }
      }
      v58 = L"/>";
      v59 = *(__int64 **)v52;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v59, (__int64)v58);
    goto LABEL_69;
  }
LABEL_277:
  v233 = *(_DWORD *)(a1 + 192);
  if ( v233 == 33619978 || v233 == 33619970 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v259,
      L"SuccessReason");
    mlib::XmlStream::WriteBeginTag((mlib::XmlStream *)a2);
    if ( v233 == 33619978 )
      v234 = L"NotEnoughSpace";
    else
      v234 = L"TooFragmented";
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)*a2, (__int64)v234);
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v242,
      L"SuccessReason");
    mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v242);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v259);
    v233 = 0;
  }
  dwErrCode = v233;
  v350 = 1;
  v351 = 0;
  mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
  if ( *(_DWORD *)(a1 + 192) )
    WinSAT::DiskProfiler::PropogateWin32Error(v4, Buffer);
  SetLastError(dwErrCode);
  if ( v233 == 33619979 )
    v235 = -2147221502;
  else
    v235 = dwErrCode != 0 ? 0x80040001 : 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v260);
  return v235;
}

```

## disassembly

```asm
0x140066080  mov     rax, rsp
0x140066083  mov     [rax+18h], rbx
0x140066087  push    rbp
0x140066088  push    rsi
0x140066089  push    rdi
0x14006608a  push    r12
0x14006608c  push    r13
0x14006608e  push    r14
0x140066090  push    r15
0x140066092  lea     rbp, [rax-518h]
0x140066099  sub     rsp, 5E0h
0x1400660a0  movaps  xmmword ptr [rax-48h], xmm6
0x1400660a4  mov     rax, cs:__security_cookie
0x1400660ab  xor     rax, rsp
0x1400660ae  mov     [rbp+510h+var_50], rax
0x1400660b5  mov     r14, rdx
0x1400660b8  mov     r13, rcx
0x1400660bb  mov     edx, 40h ; '@'
0x1400660c0  lea     rcx, [rbp+510h+var_538]
0x1400660c4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x1400660c9  nop
0x1400660ca  lea     r12, [r13-8]
0x1400660ce  mov     r8d, [r12+0D4h]
0x1400660d6  lea     rdx, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x1400660dd  lea     rcx, [rbp+510h+var_538]
0x1400660e1  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x1400660e6  lea     r15, [r14+8]
0x1400660ea  lea     rdi, asc_14012B480; ">"
0x1400660f1  xor     esi, esi
0x1400660f3  cmp     [r13+1A0h], rsi
0x1400660fa  jz      loc_14006626E
0x140066100  lea     rdx, aAvailabletempf; "AvailableTempFileSize"
0x140066107  lea     rcx, [rsp+610h+var_5E8]
0x14006610c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140066111  nop
0x140066112  cmp     dword ptr [r15], 2
0x140066116  jnz     short loc_140066123
0x140066118  mov     rdx, rdi
0x14006611b  mov     rcx, [r14]
0x14006611e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066123  mov     dword ptr [r15], 2
0x14006612a  mov     rcx, r14; this
0x14006612d  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140066132  lea     rdx, asc_14012B484; "<"
0x140066139  mov     rcx, [r14]
0x14006613c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066141  mov     rcx, rax
0x140066144  lea     rdx, [rsp+610h+var_5E8]
0x140066149  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14006614e  inc     dword ptr [r14+0Ch]
0x140066152  mov     [r14+11h], sil
0x140066156  lea     rdx, aUnits_0; "units"
0x14006615d  lea     rcx, [rsp+610h+var_5E0]
0x140066162  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140066167  nop
0x140066168  mov     dword ptr [r15], 3
0x14006616f  lea     rdx, asc_14012B49C; " "
0x140066176  mov     rcx, [r14]
0x140066179  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006617e  mov     rcx, rax
0x140066181  lea     rdx, [rsp+610h+var_5E0]
0x140066186  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14006618b  mov     rcx, rax
0x14006618e  lea     rdx, asc_14012B498; "="
0x140066195  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006619a  mov     rcx, r14; this
0x14006619d  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x1400661a2  lea     rdx, aMb_0; "MB"
0x1400661a9  mov     rcx, [r14]
0x1400661ac  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400661b1  mov     rcx, r14; this
0x1400661b4  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x1400661b9  mov     rbx, [r13+1A0h]
0x1400661c0  shr     rbx, 14h
0x1400661c4  mov     rcx, r14; this
0x1400661c7  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x1400661cc  mov     rdx, rbx
0x1400661cf  mov     rcx, [r14]
0x1400661d2  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x1400661d7  mov     rcx, r14; this
0x1400661da  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x1400661df  lea     rdx, aAvailabletempf; "AvailableTempFileSize"
0x1400661e6  lea     rcx, [rsp+610h+var_5D8]
0x1400661eb  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400661f0  nop
0x1400661f1  dec     dword ptr [r14+0Ch]
0x1400661f5  mov     ecx, [r15]
0x1400661f8  sub     ecx, 1
0x1400661fb  jz      short loc_14006620E
0x1400661fd  cmp     ecx, 1
0x140066200  jnz     short loc_140066247
0x140066202  lea     rdx, asc_14012B488; "/>"
0x140066209  mov     rcx, [r14]
0x14006620c  jmp     short loc_140066242
0x14006620e  cmp     [r14+11h], sil
0x140066212  jnz     short loc_14006621C
0x140066214  mov     rcx, r14; this
0x140066217  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14006621c  mov     [r14+11h], sil
0x140066220  lea     rdx, asc_14012B490; "</"
0x140066227  mov     rcx, [r14]
0x14006622a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006622f  mov     rcx, rax
0x140066232  lea     rdx, [rsp+610h+var_5D8]
0x140066237  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14006623c  mov     rcx, rax
0x14006623f  mov     rdx, rdi
0x140066242  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066247  mov     dword ptr [r15], 1
0x14006624e  lea     rcx, [rsp+610h+var_5D8]
0x140066253  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140066258  nop
0x140066259  lea     rcx, [rsp+610h+var_5E0]
0x14006625e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140066263  nop
0x140066264  lea     rcx, [rsp+610h+var_5E8]
0x140066269  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14006626e  lea     rdx, aUsedtempfilesi; "UsedTempFileSize"
0x140066275  lea     rcx, [rsp+610h+var_5E8]
0x14006627a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14006627f  nop
0x140066280  cmp     dword ptr [r15], 2
0x140066284  jnz     short loc_140066291
0x140066286  mov     rdx, rdi
0x140066289  mov     rcx, [r14]
0x14006628c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066291  mov     dword ptr [r15], 2
0x140066298  mov     rcx, r14; this
0x14006629b  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x1400662a0  lea     rdx, asc_14012B484; "<"
0x1400662a7  mov     rcx, [r14]
0x1400662aa  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400662af  mov     rcx, rax
0x1400662b2  lea     rdx, [rsp+610h+var_5E8]
0x1400662b7  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400662bc  inc     dword ptr [r14+0Ch]
0x1400662c0  mov     [r14+11h], sil
0x1400662c4  lea     rdx, aUnits_0; "units"
0x1400662cb  lea     rcx, [rsp+610h+var_5E0]
0x1400662d0  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400662d5  nop
0x1400662d6  mov     dword ptr [r15], 3
0x1400662dd  lea     rdx, asc_14012B49C; " "
0x1400662e4  mov     rcx, [r14]
0x1400662e7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400662ec  mov     rcx, rax
0x1400662ef  lea     rdx, [rsp+610h+var_5E0]
0x1400662f4  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400662f9  mov     rcx, rax
0x1400662fc  lea     rdx, asc_14012B498; "="
0x140066303  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066308  mov     rcx, r14; this
0x14006630b  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140066310  lea     rdx, aMb_0; "MB"
0x140066317  mov     rcx, [r14]
0x14006631a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006631f  mov     rcx, r14; this
0x140066322  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140066327  mov     rbx, [r13+110h]
0x14006632e  shr     rbx, 14h
0x140066332  mov     rcx, r14; this
0x140066335  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14006633a  mov     rdx, rbx
0x14006633d  mov     rcx, [r14]
0x140066340  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x140066345  mov     rcx, r14; this
0x140066348  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14006634d  lea     rdx, aUsedtempfilesi; "UsedTempFileSize"
0x140066354  lea     rcx, [rsp+610h+var_5D8]
0x140066359  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14006635e  nop
0x14006635f  dec     dword ptr [r14+0Ch]
0x140066363  mov     ecx, [r15]
0x140066366  sub     ecx, 1
0x140066369  jz      short loc_14006637C
0x14006636b  cmp     ecx, 1
0x14006636e  jnz     short loc_1400663B5
0x140066370  lea     rdx, asc_14012B488; "/>"
0x140066377  mov     rcx, [r14]
0x14006637a  jmp     short loc_1400663B0
0x14006637c  cmp     [r14+11h], sil
0x140066380  jnz     short loc_14006638A
0x140066382  mov     rcx, r14; this
0x140066385  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14006638a  mov     [r14+11h], sil
0x14006638e  lea     rdx, asc_14012B490; "</"
0x140066395  mov     rcx, [r14]
0x140066398  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006639d  mov     rcx, rax
0x1400663a0  lea     rdx, [rsp+610h+var_5D8]
0x1400663a5  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400663aa  mov     rcx, rax
0x1400663ad  mov     rdx, rdi
0x1400663b0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400663b5  mov     dword ptr [r15], 1
0x1400663bc  lea     rcx, [rsp+610h+var_5D8]
0x1400663c1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400663c6  nop
0x1400663c7  lea     rcx, [rsp+610h+var_5E0]
0x1400663cc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400663d1  nop
0x1400663d2  lea     rcx, [rsp+610h+var_5E8]
0x1400663d7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400663dc  cmp     [r13+0C0h], esi
0x1400663e3  jnz     loc_1400697B0
0x1400663e9  lea     rdx, aUnits; "Units"
0x1400663f0  lea     rcx, [rbp+510h+var_548]
0x1400663f4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400663f9  nop
0x1400663fa  mov     ebx, 2
0x1400663ff  cmp     [r15], ebx
0x140066402  jnz     short loc_14006640F
0x140066404  mov     rdx, rdi
0x140066407  mov     rcx, [r14]
0x14006640a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006640f  mov     [r15], ebx
0x140066412  mov     rcx, r14; this
0x140066415  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14006641a  lea     rdx, asc_14012B484; "<"
0x140066421  mov     rcx, [r14]
0x140066424  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066429  mov     rcx, rax
0x14006642c  lea     rdx, [rbp+510h+var_548]
0x140066430  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140066435  inc     dword ptr [r14+0Ch]
0x140066439  mov     [r14+11h], sil
0x14006643d  lea     rdx, aName_0; "name"
0x140066444  lea     rcx, [rbp+510h+var_550]
0x140066448  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14006644d  nop
0x14006644e  mov     dword ptr [r15], 3
0x140066455  lea     rdx, asc_14012B49C; " "
0x14006645c  mov     rcx, [r14]
0x14006645f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066464  mov     rcx, rax
0x140066467  lea     rdx, [rbp+510h+var_550]
0x14006646b  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140066470  mov     rcx, rax
0x140066473  lea     rdx, asc_14012B498; "="
0x14006647a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006647f  mov     rcx, r14; this
0x140066482  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140066487  lea     rdx, aBytes_4; "bytes"
0x14006648e  mov     rcx, [r14]
0x140066491  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066496  mov     rcx, r14; this
0x140066499  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14006649e  lea     rdx, aUnits_0; "units"
0x1400664a5  lea     rcx, [rbp+510h+var_558]
0x1400664a9  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400664ae  nop
0x1400664af  mov     dword ptr [r15], 3
0x1400664b6  lea     rdx, asc_14012B49C; " "
0x1400664bd  mov     rcx, [r14]
0x1400664c0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400664c5  mov     rcx, rax
0x1400664c8  lea     rdx, [rbp+510h+var_558]
0x1400664cc  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400664d1  mov     rcx, rax
0x1400664d4  lea     rdx, asc_14012B498; "="
0x1400664db  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400664e0  mov     rcx, r14; this
0x1400664e3  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x1400664e8  lea     rdx, aBytes_4; "bytes"
0x1400664ef  mov     rcx, [r14]
0x1400664f2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400664f7  mov     rcx, r14; this
0x1400664fa  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x1400664ff  lea     rdx, aDescrip; "descrip"
0x140066506  lea     rcx, [rbp+510h+var_560]
0x14006650a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14006650f  nop
0x140066510  mov     dword ptr [r15], 3
0x140066517  lea     rdx, asc_14012B49C; " "
0x14006651e  mov     rcx, [r14]
0x140066521  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066526  mov     rcx, rax
0x140066529  lea     rdx, [rbp+510h+var_560]
0x14006652d  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140066532  mov     rcx, rax
0x140066535  lea     rdx, asc_14012B498; "="
0x14006653c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066541  mov     rcx, r14; this
0x140066544  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140066549  lea     rdx, aBytes_4; "bytes"
0x140066550  mov     rcx, [r14]
0x140066553  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066558  mov     rcx, r14; this
0x14006655b  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140066560  lea     rdx, aUnits; "Units"
0x140066567  lea     rcx, [rbp+510h+var_568]
0x14006656b  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140066570  nop
0x140066571  dec     dword ptr [r14+0Ch]
0x140066575  mov     ecx, [r15]
0x140066578  sub     ecx, 1
0x14006657b  jz      short loc_14006658E
0x14006657d  cmp     ecx, 1
0x140066580  jnz     short loc_1400665C6
0x140066582  lea     rdx, asc_14012B488; "/>"
  ... truncated ...
```
