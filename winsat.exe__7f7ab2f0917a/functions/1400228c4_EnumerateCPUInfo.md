# EnumerateCPUInfo

- ea: `0x1400228c4`
- end: `0x140026108`
- name: `EnumerateCPUInfo`
- size: `14404`
- prototype: `__int64 __fastcall(mlib::XmlStream *this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002b890`

## callees

- `0x1400039f0`
- `0x140004348`
- `0x14000449c`
- `0x140005d78`
- `0x140008064`
- `0x140008178`
- `0x1400085b4`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140013454`
- `0x14001362c`
- `0x140016d04`
- `0x140017af0`
- `0x14002093c`
- `0x1400219d0`
- `0x140021a34`
- `0x140021e6c`
- `0x1400228c4`
- `0x140113220`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x140024b02`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024c11`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024d19`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024e21`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024b02`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024c11`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024d19`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024e21`
- `msvcrt!_wcsicmp` at `0x140023420`
- `msvcrt!_wcsicmp` at `0x140023446`
- `msvcrt!_wcsicmp` at `0x140023420`
- `msvcrt!_wcsicmp` at `0x140023446`

## string_xrefs

- `0x14002307a`: `CoresAreThreaded`
- `0x1400230fc`: `CoresAreThreaded`
- `0x140023a6f`: `CompactSignature`
- `0x140023aea`: `CompactSignature`
- `0x140023c8e`: `L1Cache`
- `0x140024075`: `L1Cache`
- `0x140024166`: `L2Cache`
- `0x14002454d`: `L2Cache`
- `0x14002463e`: `L3Cache`
- `0x140024a25`: `L3Cache`
- `0x1400252bd`: `RelationCache`
- `0x1400255fc`: `RelationCache`
- `0x140025e3a`: `  Cache| Level:`
- `0x140025dd1`: `  RelationCache            `

## pseudocode

```c
// Hidden C++ exception states: #wind=86
__int64 __fastcall EnumerateCPUInfo(mlib::XmlStream *this)
{
  mlib::XmlStream *v1; // rdi
  __int64 *v2; // rax
  __int64 *v3; // rax
  __int64 *v4; // rax
  __int64 *v5; // rax
  __int64 *v6; // rax
  __int64 v7; // rbx
  const wchar_t *v8; // rdx
  __int64 *v9; // rcx
  __int64 *v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rbx
  const wchar_t *v13; // rdx
  __int64 *v14; // rcx
  __int64 *v15; // rax
  __int64 *v16; // rax
  int v17; // ebx
  const wchar_t *v18; // rdx
  __int64 *v19; // rcx
  __int64 *v20; // rax
  __int64 *v21; // rax
  int v22; // ebx
  const wchar_t *v23; // rdx
  __int64 *v24; // rcx
  __int64 *v25; // rax
  __int64 *v26; // rax
  int v27; // ebx
  const wchar_t *v28; // rdx
  __int64 *v29; // rcx
  __int64 *v30; // rax
  __int64 *v31; // rax
  int v32; // ebx
  const wchar_t *v33; // rdx
  __int64 *v34; // rcx
  __int64 *v35; // rax
  __int64 *v36; // rax
  int v37; // ebx
  const wchar_t *v38; // rdx
  __int64 *v39; // rcx
  __int64 *v40; // rax
  __int64 *v41; // rax
  BOOL v42; // ebx
  const wchar_t *v43; // rdx
  __int64 *v44; // rcx
  __int64 *v45; // rax
  __int64 *v46; // rax
  const wchar_t *v47; // rbx
  const wchar_t *v48; // rdx
  __int64 *v49; // rcx
  __int64 *v50; // rax
  __int64 *v51; // rax
  const wchar_t *v52; // rdx
  __int64 *v53; // rcx
  __int64 *v54; // rax
  __int64 v55; // rax
  unsigned int v56; // esi
  __int64 v57; // rax
  __int64 *v58; // rax
  __int64 *v59; // rax
  __int64 *v60; // rax
  __int64 *v61; // rax
  __int64 v62; // rbx
  const wchar_t *v63; // rdx
  __int64 *v64; // rcx
  __int64 *v65; // rax
  __int64 *v66; // rax
  unsigned int v67; // ebx
  const wchar_t *v68; // rdx
  __int64 *v69; // rcx
  __int64 *v70; // rax
  __int64 *v71; // rax
  unsigned int v72; // ebx
  const wchar_t *v73; // rdx
  __int64 *v74; // rcx
  __int64 *v75; // rax
  __int64 *v76; // rax
  unsigned int v77; // ebx
  const wchar_t *v78; // rdx
  __int64 *v79; // rcx
  __int64 *v80; // rax
  __int64 *v81; // rax
  unsigned int v82; // ebx
  const wchar_t *v83; // rdx
  __int64 *v84; // rcx
  __int64 *v85; // rax
  __int64 *v86; // rax
  int v87; // ebx
  const wchar_t *v88; // rdx
  __int64 *v89; // rcx
  __int64 *v90; // rax
  __int64 *v91; // rax
  int v92; // ebx
  const wchar_t *v93; // rdx
  __int64 *v94; // rcx
  __int64 *v95; // rax
  const wchar_t *v96; // rdx
  __int64 *v97; // rcx
  __int64 *v98; // rax
  __int64 *v99; // rax
  __int64 *v100; // rax
  int v101; // ebx
  const wchar_t *v102; // rdx
  __int64 *v103; // rcx
  __int64 *v104; // rax
  __int64 *v105; // rax
  int v106; // ebx
  const wchar_t *v107; // rdx
  __int64 *v108; // rcx
  __int64 *v109; // rax
  __int64 *v110; // rax
  int v111; // ebx
  const wchar_t *v112; // rdx
  __int64 *v113; // rcx
  __int64 *v114; // rax
  __int64 *v115; // rax
  int v116; // ebx
  const wchar_t *v117; // rdx
  __int64 *v118; // rcx
  __int64 *v119; // rax
  const wchar_t *v120; // rdx
  __int64 *v121; // rcx
  __int64 *v122; // rax
  __int64 *v123; // rax
  __int64 *v124; // rax
  int v125; // ebx
  const wchar_t *v126; // rdx
  __int64 *v127; // rcx
  __int64 *v128; // rax
  __int64 *v129; // rax
  int v130; // ebx
  const wchar_t *v131; // rdx
  __int64 *v132; // rcx
  __int64 *v133; // rax
  __int64 *v134; // rax
  int v135; // ebx
  const wchar_t *v136; // rdx
  __int64 *v137; // rcx
  __int64 *v138; // rax
  __int64 *v139; // rax
  int v140; // ebx
  const wchar_t *v141; // rdx
  __int64 *v142; // rcx
  __int64 *v143; // rax
  const wchar_t *v144; // rdx
  __int64 *v145; // rcx
  __int64 *v146; // rax
  __int64 *v147; // rax
  __int64 *v148; // rax
  int v149; // ebx
  const wchar_t *v150; // rdx
  __int64 *v151; // rcx
  __int64 *v152; // rax
  __int64 *v153; // rax
  int v154; // ebx
  const wchar_t *v155; // rdx
  __int64 *v156; // rcx
  __int64 *v157; // rax
  __int64 *v158; // rax
  int v159; // ebx
  const wchar_t *v160; // rdx
  __int64 *v161; // rcx
  __int64 *v162; // rax
  __int64 *v163; // rax
  int v164; // ebx
  const wchar_t *v165; // rdx
  __int64 *v166; // rcx
  __int64 *v167; // rax
  const wchar_t *v168; // rdx
  __int64 *v169; // rcx
  __int64 *v170; // rax
  BOOL v171; // esi
  __int64 *v172; // rax
  const wchar_t *v173; // rbx
  const wchar_t *v174; // rdx
  const wchar_t *v175; // rdx
  __int64 *v176; // rcx
  __int64 *v177; // rax
  BOOL v178; // esi
  __int64 *v179; // rax
  const wchar_t *v180; // rdx
  const wchar_t *v181; // rdx
  __int64 *v182; // rcx
  __int64 *v183; // rax
  BOOL v184; // esi
  __int64 *v185; // rax
  const wchar_t *v186; // rdx
  const wchar_t *v187; // rdx
  __int64 *v188; // rcx
  __int64 *v189; // rax
  BOOL v190; // esi
  __int64 *v191; // rax
  const wchar_t *v192; // rdx
  __int64 *v193; // rcx
  __int64 *v194; // rax
  __int64 v195; // rsi
  __int64 *v196; // rax
  unsigned int i; // r15d
  __int64 v198; // r14
  int v199; // ecx
  int v200; // ecx
  int v201; // ecx
  __int64 v202; // rbx
  unsigned __int64 **v203; // rcx
  __int64 v204; // rbx
  __int64 *v205; // rdx
  __int64 v206; // rcx
  __int64 *v207; // rax
  __int64 *v208; // rax
  __int64 v209; // rbx
  __int64 *v210; // rdx
  __int64 v211; // rcx
  __int64 *v212; // rax
  unsigned int v213; // ebx
  int v214; // ebx
  unsigned int v215; // ebx
  unsigned int v216; // ebx
  __int64 v217; // rbx
  __int64 *v218; // rax
  __int64 *v219; // rax
  __int64 v220; // rbx
  __int64 *v221; // rdx
  __int64 v222; // rcx
  __int64 *v223; // rax
  int v224; // ebx
  __int64 *v225; // rax
  __int64 *v226; // rax
  __int64 v227; // rbx
  __int64 *v228; // rdx
  __int64 v229; // rcx
  const wchar_t *v230; // rdx
  __int64 *v231; // rcx
  __int64 *v232; // rax
  __int64 *v233; // rax
  unsigned int v234; // ebx
  __int64 *v235; // rdx
  __int64 v236; // rcx
  const wchar_t *v237; // rdx
  __int64 *v238; // rcx
  __int64 *v239; // rax
  unsigned int v240; // r14d
  __int64 v241; // rbx
  int v242; // ecx
  int v243; // ecx
  int v244; // ecx
  __int64 v245; // rax
  __int64 *v246; // rax
  __int64 v247; // rax
  __int64 *v248; // rax
  __int64 *v249; // rax
  __int64 *v250; // rax
  __int64 v251; // rax
  __int64 v252; // rax
  __int64 v253; // rax
  __int64 *v254; // rax
  __int64 v255; // rax
  __int64 *v256; // rax
  __int64 v257; // rax
  __int64 *v258; // rax
  __int64 v259; // rax
  __int64 *v260; // rax
  __int64 *v261; // rax
  __int64 *v262; // rax
  __int64 *v263; // rax
  __int64 *v264; // rax
  __int64 v265; // rax
  __int64 *v266; // rax
  __int64 *v267; // rax
  __int64 *v268; // rax
  __int64 *v269; // rax
  __int64 *v270; // rax
  __int64 v271; // rax
  __int64 *v272; // r8
  __int64 v273; // rax
  __int64 *v274; // rax
  __int64 v275; // rax
  __int64 *v276; // rax
  __int64 *v277; // rax
  __int64 *v278; // rax
  __int64 v279; // rax
  __int64 *v280; // rax
  __int64 v281; // rax
  __int64 *v282; // rax
  __int64 *v283; // rax
  __int64 *v284; // rax
  __int64 v285; // rax
  unsigned __int64 *v287; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 *v288; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 *v289; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 *v290; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 *v291; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 *v292; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 *v293; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 *v294; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 *v295; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 *v296; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 *v297; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 *v298; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 *v299; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 *v300; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 *v301; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 *v302; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 *v303; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 *v304; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 *v305; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v306; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v307; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 *v308; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v309; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 *v310; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 *v311; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v312; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v313; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 *v314; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v315; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 *v316; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 *v317; // [rsp+110h] [rbp+10h] BYREF
  __int64 v318; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 *v319; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 *v320; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int64 *v321; // [rsp+130h] [rbp+30h] BYREF
  __int64 v322; // [rsp+138h] [rbp+38h] BYREF
  __int64 v323; // [rsp+140h] [rbp+40h] BYREF
  mlib::XmlStream *v324; // [rsp+148h] [rbp+48h]
  __int128 v325; // [rsp+150h] [rbp+50h] BYREF
  int v326; // [rsp+160h] [rbp+60h]

  v1 = this;
  v324 = this;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v299,
    L"Processor");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v2 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v2, &v299);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v298,
    L"Instance");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v3 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v3, &v298);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v287,
    L"id");
  *((_DWORD *)v1 + 2) = 3;
  v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L" ");
  v5 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v4, &v287);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, (__int64)L"=");
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, 0);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v287);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v298);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v299);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v298,
    L"ProcessorName");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v6, &v298);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v7 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
     + 8;
  mlib::XmlStream::BeforeText(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, v7);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v299,
    L"ProcessorName");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v9 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v10, &v299);
    v8 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_14;
    v8 = L"/>";
    v9 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, (__int64)v8);
LABEL_14:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v299);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v298);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v290,
    L"TSCFrequency");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v11, &v290);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v12 = *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v12);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v289,
    L"TSCFrequency");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v14 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v15, &v289);
    v13 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_23;
    v13 = L"/>";
    v14 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v14, (__int64)v13);
LABEL_23:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v297,
    L"NumProcs");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v16, &v297);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v17 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 448);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v17);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v296,
    L"NumProcs");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v19 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v20, &v296);
    v18 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_32;
    v18 = L"/>";
    v19 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, (__int64)v18);
LABEL_32:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v295,
    L"NumCores");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v21, &v295);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v22 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 452);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v22);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v294,
    L"NumCores");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v25 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v24 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v25, &v294);
    v23 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_41;
    v23 = L"/>";
    v24 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, (__int64)v23);
LABEL_41:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v293,
    L"NumCPUs");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v26, &v293);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v27 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 456);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v27);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v303,
    L"NumCPUs");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v29 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v30, &v303);
    v28 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_50;
    v28 = L"/>";
    v29 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, (__int64)v28);
LABEL_50:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v302,
    L"NumCPUsPerCore");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v31, &v302);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v32 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 460);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v32);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v301,
    L"NumCPUsPerCore");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v34 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v35, &v301);
    v33 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_59;
    v33 = L"/>";
    v34 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, (__int64)v33);
LABEL_59:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v300,
    L"NumCoresPerProcessor");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v36, &v300);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v37 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 464);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v37);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v287,
    L"NumCoresPerProcessor");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v40 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v39 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v40, &v287);
    v38 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_68;
    v38 = L"/>";
    v39 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, (__int64)v38);
LABEL_68:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v298,
    L"CoresAreThreaded");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v41 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v41, &v298);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v42 = *(_BYTE *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                 + 468) != 0;
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v42);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v299,
    L"CoresAreThreaded");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v44 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v45, &v299);
    v43 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_77;
    v43 = L"/>";
    v44 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, (__int64)v43);
LABEL_77:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v299);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v298);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v287);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v300);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v301);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v302);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v303);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v293);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v294);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v295);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v296);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v297);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
  v325 = 0;
  v326 = 0;
  GetCPUID(&v325, 2147483649LL);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v289,
    L"X64Capable");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v46 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v46, &v289);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v47 = L"1";
  if ( (v326 & 0x20000000) == 0 )
    v47 = L"0";
  mlib::XmlStream::BeforeText(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)v47);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v290,
    L"X64Capable");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v50 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v49 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v50, &v290);
    v48 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_88;
    v48 = L"/>";
    v49 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v49, (__int64)v48);
LABEL_88:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v289,
    L"X64Running");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v51 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v51, &v289);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"1");
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v290,
    L"X64Running");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v54 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v53 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v54, &v290);
    v52 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_97;
    v52 = L"/>";
    v53 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v53, (__int64)v52);
LABEL_97:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
  v55 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo);
  v56 = _wcsicmp((const wchar_t *)(v55 + 208), L"AMD") == 0;
  v57 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo);
  if ( !_wcsicmp((const wchar_t *)(v57 + 208), L"Intel") )
    v56 = 2;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v288,
    L"Signature");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v58 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v58, &v288);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v292,
    L"Manufacturer");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v59 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v59, &v292);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v291,
    L"friendly");
  *((_DWORD *)v1 + 2) = 3;
  v60 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L" ");
  v61 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v60, &v291);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v61, (__int64)L"=");
  v62 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
      + 208;
  mlib::XmlStream::BeforeText(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, v62);
  mlib::XmlStream::AfterText(v1);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v56);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v287,
    L"Manufacturer");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v65 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v64 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v65, &v287);
    v63 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_110;
    v63 = L"/>";
    v64 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v64, (__int64)v63);
LABEL_110:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v298,
    L"Stepping");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v66, &v298);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v67 = *(unsigned __int8 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                           + 480);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v67);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v299,
    L"Stepping");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v70 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v69 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v70, &v299);
    v68 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_119;
    v68 = L"/>";
    v69 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v69, (__int64)v68);
LABEL_119:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v300,
    L"Model");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v71 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v71, &v300);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v72 = *(unsigned __int8 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                           + 481);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v72);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v301,
    L"Model");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v75 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v74 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v75, &v301);
    v73 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_128;
    v73 = L"/>";
    v74 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, (__int64)v73);
LABEL_128:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v302,
    L"Family");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v76 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v76, &v302);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v77 = *(unsigned __int8 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                           + 482);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v77);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v303,
    L"Family");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v80 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v79 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v80, &v303);
    v78 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_137;
    v78 = L"/>";
    v79 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v79, (__int64)v78);
LABEL_137:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v293,
    L"ExtendedModel");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v81 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v81, &v293);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v82 = *(unsigned __int8 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                           + 483);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v82);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v294,
    L"ExtendedModel");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v85 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v84 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v85, &v294);
    v83 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_146;
    v83 = L"/>";
    v84 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v84, (__int64)v83);
LABEL_146:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v295,
    L"ExtendedFamily");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v86 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v86, &v295);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v87 = *(unsigned __int16 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                            + 484);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v87);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v296,
    L"ExtendedFamily");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v90 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v89 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v90, &v296);
    v88 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_155;
    v88 = L"/>";
    v89 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v89, (__int64)v88);
LABEL_155:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v297,
    L"CompactSignature");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v91 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v91, &v297);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v92 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 486);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v92);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v289,
    L"CompactSignature");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v95 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v94 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v95, &v289);
    v93 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_164;
    v93 = L"/>";
    v94 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v94, (__int64)v93);
LABEL_164:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v290,
    L"Signature");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v98 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v97 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v98, &v290);
    v96 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_171;
    v96 = L"/>";
    v97 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v97, (__int64)v96);
LABEL_171:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v297);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v296);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v295);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v294);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v293);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v303);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v302);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v301);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v300);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v299);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v298);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v287);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v291);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v292);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
  if ( !*(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 408) )
    goto LABEL_218;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v293,
    L"L1Cache");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v99 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v99, &v293);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v294,
    L"Size");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v100 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v100, &v294);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v101 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 408);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v101);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v295,
    L"Size");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v104 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v103 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v104, &v295);
    v102 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_183;
    v102 = L"/>";
    v103 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v103, (__int64)v102);
LABEL_183:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v296,
    L"Ways");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v105 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v105, &v296);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v106 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 416);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v106);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v297,
    L"Ways");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v109 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v108 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v109, &v297);
    v107 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_192;
    v107 = L"/>";
    v108 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v108, (__int64)v107);
LABEL_192:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v289,
    L"LineSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v110 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v110, &v289);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v111 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 412);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v111);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v290,
    L"LineSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v114 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v113 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v114, &v290);
    v112 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_201;
    v112 = L"/>";
    v113 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v113, (__int64)v112);
LABEL_201:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v291,
    L"SectorSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v115 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v115, &v291);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v116 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 408);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v116);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v292,
    L"SectorSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v119 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v118 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v119, &v292);
    v117 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_210;
    v117 = L"/>";
    v118 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v118, (__int64)v117);
LABEL_210:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v288,
    L"L1Cache");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v122 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v121 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v122, &v288);
    v120 = L">";
    goto LABEL_216;
  }
  if ( *((_DWORD *)v1 + 2) == 2 )
  {
    v120 = L"/>";
    v121 = *(__int64 **)v1;
LABEL_216:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v121, (__int64)v120);
  }
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v292);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v291);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v297);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v296);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v295);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v294);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v293);
LABEL_218:
  if ( !*(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 420) )
    goto LABEL_265;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v293,
    L"L2Cache");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v123 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v123, &v293);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v294,
    L"Size");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v124 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v124, &v294);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v125 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 420);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v125);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v295,
    L"Size");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v128 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v127 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v128, &v295);
    v126 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_230;
    v126 = L"/>";
    v127 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v127, (__int64)v126);
LABEL_230:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v296,
    L"Ways");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v129 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v129, &v296);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v130 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 428);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v130);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v297,
    L"Ways");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v133 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v132 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v133, &v297);
    v131 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_239;
    v131 = L"/>";
    v132 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v132, (__int64)v131);
LABEL_239:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v289,
    L"LineSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v134 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v134, &v289);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v135 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 424);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v135);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v290,
    L"LineSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v138 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v137 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v138, &v290);
    v136 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_248;
    v136 = L"/>";
    v137 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, (__int64)v136);
LABEL_248:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v291,
    L"SectorSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v139 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v139, &v291);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v140 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 420);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v140);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v292,
    L"SectorSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v143 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v142 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v143, &v292);
    v141 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_257;
    v141 = L"/>";
    v142 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, (__int64)v141);
LABEL_257:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v288,
    L"L2Cache");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v146 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v145 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v146, &v288);
    v144 = L">";
    goto LABEL_263;
  }
  if ( *((_DWORD *)v1 + 2) == 2 )
  {
    v144 = L"/>";
    v145 = *(__int64 **)v1;
LABEL_263:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, (__int64)v144);
  }
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v292);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v291);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v297);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v296);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v295);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v294);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v293);
LABEL_265:
  if ( !*(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                  + 432) )
    goto LABEL_312;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v293,
    L"L3Cache");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v147 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v147, &v293);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v294,
    L"Size");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v148 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v148, &v294);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v149 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 432);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v149);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v295,
    L"Size");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v152 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v151 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v152, &v295);
    v150 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_277;
    v150 = L"/>";
    v151 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v151, (__int64)v150);
LABEL_277:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v296,
    L"Ways");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v153 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v153, &v296);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v154 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 440);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v154);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v297,
    L"Ways");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v157 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v156 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v157, &v297);
    v155 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_286;
    v155 = L"/>";
    v156 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v156, (__int64)v155);
LABEL_286:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v289,
    L"LineSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v158 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v158, &v289);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v159 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 436);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v159);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v290,
    L"LineSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v162 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v161 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v162, &v290);
    v160 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_295;
    v160 = L"/>";
    v161 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v161, (__int64)v160);
LABEL_295:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v291,
    L"SectorSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v163 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v163, &v291);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v164 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                   + 432);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v164);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v292,
    L"SectorSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v167 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v166 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v167, &v292);
    v165 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_304;
    v165 = L"/>";
    v166 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v166, (__int64)v165);
LABEL_304:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v288,
    L"L3Cache");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v170 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v169 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v170, &v288);
    v168 = L">";
    goto LABEL_310;
  }
  if ( *((_DWORD *)v1 + 2) == 2 )
  {
    v168 = L"/>";
    v169 = *(__int64 **)v1;
LABEL_310:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v169, (__int64)v168);
  }
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v292);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v291);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v297);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v296);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v295);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v294);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v293);
LABEL_312:
  v171 = IsProcessorFeaturePresent(3u);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v292,
    L"MMX");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v172 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v172, &v292);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  v173 = L"Yes";
  v174 = L"Yes";
  if ( !v171 )
    v174 = L"No";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)v174);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v288,
    L"MMX");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v177 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v176 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v177, &v288);
    v175 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_323;
    v175 = L"/>";
    v176 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v176, (__int64)v175);
LABEL_323:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v292);
  v178 = IsProcessorFeaturePresent(6u);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v291,
    L"SSE");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v179 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v179, &v291);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  v180 = L"Yes";
  if ( !v178 )
    v180 = L"No";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)v180);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v288,
    L"SSE");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v183 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v182 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v183, &v288);
    v181 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_334;
    v181 = L"/>";
    v182 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v182, (__int64)v181);
LABEL_334:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v291);
  v184 = IsProcessorFeaturePresent(0xAu);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v292,
    L"SSE2");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v185 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v185, &v292);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  v186 = L"Yes";
  if ( !v184 )
    v186 = L"No";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)v186);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v288,
    L"SSE2");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v189 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v188 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v189, &v288);
    v187 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_345;
    v187 = L"/>";
    v188 = *(__int64 **)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v188, (__int64)v187);
LABEL_345:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v292);
  v190 = IsProcessorFeaturePresent(0xDu);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v291,
    L"SSE3");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  v191 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v191, &v291);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  if ( !v190 )
    v173 = L"No";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)v173);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v288,
    L"SSE3");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    v194 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
    v193 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v194, &v288);
    v192 = L">";
    goto LABEL_355;
  }
  if ( *((_DWORD *)v1 + 2) == 2 )
  {
    v192 = L"/>";
    v193 = *(__int64 **)v1;
LABEL_355:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v193, (__int64)v192);
  }
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v291);
  if ( *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                 + 1024) )
  {
    v195 = *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                     + 1024);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v288,
      L"LogicalProcessorInfo");
    if ( *((_DWORD *)v1 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
    *((_DWORD *)v1 + 2) = 2;
    mlib::XmlStream::Indent(v1);
    v196 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v196, &v288);
    ++*((_DWORD *)v1 + 3);
    *((_BYTE *)v1 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
    for ( i = 0;
          (unsigned __int64)i < *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                                          + 1032);
          ++i )
    {
      v198 = 32LL * i;
      v199 = *(_DWORD *)(v198 + v195 + 8);
      if ( v199 )
      {
        v200 = v199 - 1;
        if ( v200 )
        {
          v201 = v200 - 1;
          if ( v201 )
          {
            if ( v201 == 1 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v293,
                L"RelationProcessorPackage");
              mlib::XmlStream::WriteBeginTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v294,
                L"Mask");
              mlib::XmlStream::WriteBeginTag(v1);
              LODWORD(v287) = 16;
              mlib::XmlStream::BeforeText(v1);
              mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v287);
              mlib::XmlStream::AfterText(v1);
              v204 = *(_QWORD *)(v198 + v195);
              mlib::XmlStream::BeforeText(v1);
              std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v204);
              mlib::XmlStream::AfterText(v1);
              mlib::XmlStream::BeforeText(v1);
              v205 = *(__int64 **)v1;
              v206 = *(int *)(**(_QWORD **)v1 + 4LL);
              *(_DWORD *)((char *)v205 + v206 + 24) |= 0x201u;
              *(_WORD *)((char *)v205 + *(int *)(*v205 + 4) + 88) = 32;
              *(__int64 *)((char *)v205 + *(int *)(*v205 + 4) + 40) = 0;
              mlib::XmlStream::AfterText(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v295,
                L"Mask");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v296,
                L"RelationProcessorPackage");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v296);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v295);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v294);
              v203 = &v293;
            }
            else
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v297,
                L"RelationUnknown");
              mlib::XmlStream::WriteBeginTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v289,
                L"Mask");
              mlib::XmlStream::WriteBeginTag(v1);
              LODWORD(v287) = 16;
              mlib::XmlStream::BeforeText(v1);
              mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v287);
              mlib::XmlStream::AfterText(v1);
              v202 = *(_QWORD *)(v198 + v195);
              mlib::XmlStream::BeforeText(v1);
              std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v202);
              mlib::XmlStream::AfterText(v1);
              mlib::XmlStream::WriteText<mlib::_normobj>(v1, 0);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v290,
                L"Mask");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v291,
                L"Relationship");
              mlib::XmlStream::WriteBeginTag(v1);
              LODWORD(v287) = 8;
              mlib::XmlStream::BeforeText(v1);
              mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v287);
              mlib::XmlStream::AfterText(v1);
              LODWORD(v202) = *(_DWORD *)(v198 + v195 + 8);
              mlib::XmlStream::BeforeText(v1);
              std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, (unsigned int)v202);
              mlib::XmlStream::AfterText(v1);
              mlib::XmlStream::WriteText<mlib::_normobj>(v1, 0);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v292,
                L"Relationship");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v288,
                L"RelationUnknown");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v288);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v292);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v291);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v290);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v289);
              v203 = &v297;
            }
          }
          else
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v311,
              L"RelationCache");
            if ( *((_DWORD *)v1 + 2) == 2 )
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
            *((_DWORD *)v1 + 2) = 2;
            mlib::XmlStream::Indent(v1);
            v207 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v207, &v311);
            ++*((_DWORD *)v1 + 3);
            *((_BYTE *)v1 + 17) = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v310,
              L"Mask");
            if ( *((_DWORD *)v1 + 2) == 2 )
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
            *((_DWORD *)v1 + 2) = 2;
            mlib::XmlStream::Indent(v1);
            v208 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v208, &v310);
            ++*((_DWORD *)v1 + 3);
            *((_BYTE *)v1 + 17) = 0;
            LODWORD(v287) = 16;
            mlib::XmlStream::BeforeText(v1);
            mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v287);
            mlib::XmlStream::AfterText(v1);
            v209 = *(_QWORD *)(v198 + v195);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v209);
            mlib::XmlStream::AfterText(v1);
            mlib::XmlStream::BeforeText(v1);
            v210 = *(__int64 **)v1;
            v211 = *(int *)(**(_QWORD **)v1 + 4LL);
            *(_DWORD *)((char *)v210 + v211 + 24) |= 0x201u;
            *(_WORD *)((char *)v210 + *(int *)(*v210 + 4) + 88) = 32;
            *(__int64 *)((char *)v210 + *(int *)(*v210 + 4) + 40) = 0;
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v309,
              L"Mask");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v308,
              L"Level");
            if ( *((_DWORD *)v1 + 2) == 2 )
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
            *((_DWORD *)v1 + 2) = 2;
            mlib::XmlStream::Indent(v1);
            v212 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v212, &v308);
            ++*((_DWORD *)v1 + 3);
            *((_BYTE *)v1 + 17) = 0;
            v213 = *(unsigned __int8 *)(v198 + v195 + 16);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v213);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v307,
              L"Level");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v306,
              L"Size");
            mlib::XmlStream::WriteBeginTag(v1);
            v214 = *(_DWORD *)(v198 + v195 + 20);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v214);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v323,
              L"Size");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v322,
              L"LineSize");
            mlib::XmlStream::WriteBeginTag(v1);
            v215 = *(unsigned __int16 *)(v198 + v195 + 18);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v215);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v298,
              L"LineSize");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v299,
              L"Associativity");
            mlib::XmlStream::WriteBeginTag(v1);
            v216 = *(unsigned __int8 *)(v198 + v195 + 17);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v216);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v300,
              L"Associativity");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v301,
              L"Type");
            mlib::XmlStream::WriteBeginTag(v1);
            v217 = CachTypeStr(*(unsigned int *)(v198 + v195 + 24));
            mlib::XmlStream::BeforeText(v1);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, v217);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v302,
              L"Type");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v303,
              L"RelationCache");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v303);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v302);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v301);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v300);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v299);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v298);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v322);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v323);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v306);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v307);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v308);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v309);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v310);
            v203 = &v311;
          }
        }
        else
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v317,
            L"RelationNumaNode");
          if ( *((_DWORD *)v1 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
          *((_DWORD *)v1 + 2) = 2;
          mlib::XmlStream::Indent(v1);
          v218 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v218, &v317);
          ++*((_DWORD *)v1 + 3);
          *((_BYTE *)v1 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v316,
            L"Mask");
          if ( *((_DWORD *)v1 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
          *((_DWORD *)v1 + 2) = 2;
          mlib::XmlStream::Indent(v1);
          v219 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v219, &v316);
          ++*((_DWORD *)v1 + 3);
          *((_BYTE *)v1 + 17) = 0;
          LODWORD(v287) = 16;
          mlib::XmlStream::BeforeText(v1);
          mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v287);
          mlib::XmlStream::AfterText(v1);
          v220 = *(_QWORD *)(v198 + v195);
          mlib::XmlStream::BeforeText(v1);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v220);
          mlib::XmlStream::AfterText(v1);
          mlib::XmlStream::BeforeText(v1);
          v221 = *(__int64 **)v1;
          v222 = *(int *)(**(_QWORD **)v1 + 4LL);
          *(_DWORD *)((char *)v221 + v222 + 24) |= 0x201u;
          *(_WORD *)((char *)v221 + *(int *)(*v221 + 4) + 88) = 32;
          *(__int64 *)((char *)v221 + *(int *)(*v221 + 4) + 40) = 0;
          mlib::XmlStream::AfterText(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v315,
            L"Mask");
          mlib::XmlStream::WriteEndTag(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v314,
            L"NodeNum");
          if ( *((_DWORD *)v1 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
          *((_DWORD *)v1 + 2) = 2;
          mlib::XmlStream::Indent(v1);
          v223 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v223, &v314);
          ++*((_DWORD *)v1 + 3);
          *((_BYTE *)v1 + 17) = 0;
          v224 = *(_DWORD *)(v198 + v195 + 16);
          mlib::XmlStream::BeforeText(v1);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v224);
          mlib::XmlStream::AfterText(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v313,
            L"NodeNum");
          mlib::XmlStream::WriteEndTag(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v312,
            L"RelationNumaNode");
          mlib::XmlStream::WriteEndTag(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v312);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v313);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v314);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v315);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v316);
          v203 = &v317;
        }
        goto LABEL_401;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v304,
        L"RelationProcessorCore");
      if ( *((_DWORD *)v1 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
      *((_DWORD *)v1 + 2) = 2;
      mlib::XmlStream::Indent(v1);
      v225 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v225, &v304);
      ++*((_DWORD *)v1 + 3);
      *((_BYTE *)v1 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v305,
        L"Mask");
      if ( *((_DWORD *)v1 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
      *((_DWORD *)v1 + 2) = 2;
      mlib::XmlStream::Indent(v1);
      v226 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v226, &v305);
      ++*((_DWORD *)v1 + 3);
      *((_BYTE *)v1 + 17) = 0;
      LODWORD(v287) = 16;
      mlib::XmlStream::BeforeText(v1);
      mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v287);
      mlib::XmlStream::AfterText(v1);
      v227 = *(_QWORD *)(v198 + v195);
      mlib::XmlStream::BeforeText(v1);
      std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v227);
      mlib::XmlStream::AfterText(v1);
      mlib::XmlStream::BeforeText(v1);
      v228 = *(__int64 **)v1;
      v229 = *(int *)(**(_QWORD **)v1 + 4LL);
      *(_DWORD *)((char *)v228 + v229 + 24) |= 0x201u;
      *(_WORD *)((char *)v228 + *(int *)(*v228 + 4) + 88) = 32;
      *(__int64 *)((char *)v228 + *(int *)(*v228 + 4) + 40) = 0;
      mlib::XmlStream::AfterText(v1);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v321,
        L"Mask");
      --*((_DWORD *)v1 + 3);
      if ( *((_DWORD *)v1 + 2) == 1 )
      {
        if ( !*((_BYTE *)v1 + 17) )
          mlib::XmlStream::Indent(v1);
        *((_BYTE *)v1 + 17) = 0;
        v232 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
        v231 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v232,
                 &v321);
        v230 = L">";
      }
      else
      {
        if ( *((_DWORD *)v1 + 2) != 2 )
          goto LABEL_391;
        v230 = L"/>";
        v231 = *(__int64 **)v1;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v231, (__int64)v230);
LABEL_391:
      *((_DWORD *)v1 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v320,
        L"Flags");
      if ( *((_DWORD *)v1 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L">");
      *((_DWORD *)v1 + 2) = 2;
      mlib::XmlStream::Indent(v1);
      v233 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v233, &v320);
      ++*((_DWORD *)v1 + 3);
      *((_BYTE *)v1 + 17) = 0;
      LODWORD(v287) = 2;
      mlib::XmlStream::BeforeText(v1);
      mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v287);
      mlib::XmlStream::AfterText(v1);
      v234 = *(unsigned __int8 *)(v198 + v195 + 16);
      mlib::XmlStream::BeforeText(v1);
      std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v234);
      mlib::XmlStream::AfterText(v1);
      mlib::XmlStream::BeforeText(v1);
      v235 = *(__int64 **)v1;
      v236 = *(int *)(**(_QWORD **)v1 + 4LL);
      *(_DWORD *)((char *)v235 + v236 + 24) |= 0x201u;
      *(_WORD *)((char *)v235 + *(int *)(*v235 + 4) + 88) = 32;
      *(__int64 *)((char *)v235 + *(int *)(*v235 + 4) + 40) = 0;
      mlib::XmlStream::AfterText(v1);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v319,
        L"Flags");
      --*((_DWORD *)v1 + 3);
      if ( *((_DWORD *)v1 + 2) == 1 )
      {
        if ( !*((_BYTE *)v1 + 17) )
          mlib::XmlStream::Indent(v1);
        *((_BYTE *)v1 + 17) = 0;
        v239 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v1, (__int64)L"</");
        v238 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                 v239,
                 &v319);
        v237 = L">";
        goto LABEL_399;
      }
      if ( *((_DWORD *)v1 + 2) == 2 )
      {
        v237 = L"/>";
        v238 = *(__int64 **)v1;
LABEL_399:
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v238, (__int64)v237);
      }
      *((_DWORD *)v1 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v318,
        L"RelationProcessorCore");
      mlib::XmlStream::WriteEndTag(v1);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v318);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v319);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v320);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v321);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v305);
      v203 = &v304;
LABEL_401:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v203);
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v304,
      L"LogicalProcessorInfo");
    mlib::XmlStream::WriteEndTag(v1);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v304);
    if ( App::s_VVerbose )
    {
      v240 = 0;
      if ( *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                     + 1032) )
      {
        while ( 1 )
        {
          v241 = 32LL * v240;
          v242 = *(_DWORD *)(v241 + v195 + 8);
          if ( !v242 )
            break;
          v243 = v242 - 1;
          if ( v243 )
          {
            v244 = v243 - 1;
            if ( v244 )
            {
              if ( v244 != 1 )
              {
                v245 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
                v246 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                         (__int64 *)(v245 + 240),
                         (__int64)L"  Relation UNKNOWN         ");
                LODWORD(v287) = 16;
                v247 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v246, &v287);
                v248 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v247, *(_QWORD *)(v241 + v195));
                *(_DWORD *)((char *)v248 + *(int *)(*v248 + 4) + 24) |= 0x201u;
                *(_WORD *)((char *)v248 + *(int *)(*v248 + 4) + 88) = 32;
                *(__int64 *)((char *)v248 + *(int *)(*v248 + 4) + 40) = 0;
                v249 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v248, (__int64)L"  ");
                v250 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v249, (__int64)L"  Relation=");
                LODWORD(v287) = 8;
                v251 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v250, &v287);
                v252 = std::basic_ostream<unsigned short>::operator<<(v251, *(_DWORD *)(v241 + v195 + 8));
LABEL_413:
                *(_DWORD *)(*(int *)(*(_QWORD *)v252 + 4LL) + v252 + 24) |= 0x201u;
                *(_WORD *)(*(int *)(*(_QWORD *)v252 + 4LL) + v252 + 88) = 32;
                *(_QWORD *)(*(int *)(*(_QWORD *)v252 + 4LL) + v252 + 40) = 0;
                goto LABEL_414;
              }
              v253 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
              v254 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                       (__int64 *)(v253 + 240),
                       (__int64)L"  RelationProcessorPackage ");
              LODWORD(v287) = 16;
              v255 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v254, &v287);
              v256 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v255, *(_QWORD *)(v241 + v195));
              *(_DWORD *)((char *)v256 + *(int *)(*v256 + 4) + 24) |= 0x201u;
              *(_WORD *)((char *)v256 + *(int *)(*v256 + 4) + 88) = 32;
              *(__int64 *)((char *)v256 + *(int *)(*v256 + 4) + 40) = 0;
              v252 = (__int64)std::operator<<<unsigned short,std::char_traits<unsigned short>>(v256, (__int64)L"  ");
            }
            else
            {
              v257 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
              v258 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                       (__int64 *)(v257 + 240),
                       (__int64)L"  RelationCache            ");
              LODWORD(v287) = 16;
              v259 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v258, &v287);
              v260 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v259, *(_QWORD *)(v241 + v195));
              *(_DWORD *)((char *)v260 + *(int *)(*v260 + 4) + 24) |= 0x201u;
              *(_WORD *)((char *)v260 + *(int *)(*v260 + 4) + 88) = 32;
              *(__int64 *)((char *)v260 + *(int *)(*v260 + 4) + 40) = 0;
              v261 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v260, (__int64)L"  ");
              v262 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v261, (__int64)L"  Cache| Level:");
              v263 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(
                                  (__int64)v262,
                                  *(unsigned __int8 *)(v241 + v195 + 16));
              v264 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v263, (__int64)L" Assoc:");
              LODWORD(v287) = 2;
              v265 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v264, &v287);
              v266 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(
                                  v265,
                                  *(unsigned __int8 *)(v241 + v195 + 17));
              *(_DWORD *)((char *)v266 + *(int *)(*v266 + 4) + 24) |= 0x201u;
              *(_WORD *)((char *)v266 + *(int *)(*v266 + 4) + 88) = 32;
              *(__int64 *)((char *)v266 + *(int *)(*v266 + 4) + 40) = 0;
              v267 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v266, (__int64)L" LineSize:");
              v268 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(
                                  (__int64)v267,
                                  *(unsigned __int16 *)(v241 + v195 + 18));
              v269 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v268, (__int64)L" Size:");
              v270 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(
                                  (__int64)v269,
                                  *(_DWORD *)(v241 + v195 + 20));
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v270, (__int64)L" Type:");
              v271 = CachTypeStr(*(unsigned int *)(v241 + v195 + 24));
              v252 = (__int64)std::operator<<<unsigned short,std::char_traits<unsigned short>>(v272, v271);
            }
          }
          else
          {
            v273 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
            v274 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                     (__int64 *)(v273 + 240),
                     (__int64)L"  RelationNumaNode         ");
            LODWORD(v287) = 16;
            v275 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v274, &v287);
            v276 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v275, *(_QWORD *)(v241 + v195));
            *(_DWORD *)((char *)v276 + *(int *)(*v276 + 4) + 24) |= 0x201u;
            *(_WORD *)((char *)v276 + *(int *)(*v276 + 4) + 88) = 32;
            *(__int64 *)((char *)v276 + *(int *)(*v276 + 4) + 40) = 0;
            v277 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v276, (__int64)L"  ");
            v278 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v277, (__int64)L"  NodeNum=");
            v252 = std::basic_ostream<unsigned short>::operator<<((__int64)v278, *(_DWORD *)(v241 + v195 + 16));
          }
LABEL_414:
          std::endl(v252);
          if ( (unsigned __int64)++v240 >= *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                                                     + 1032) )
          {
            v1 = v324;
            goto LABEL_416;
          }
        }
        v279 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
        v280 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(v279 + 240),
                 (__int64)L"  RelationProcessorCore    ");
        LODWORD(v287) = 16;
        v281 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v280, &v287);
        v282 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v281, *(_QWORD *)(v241 + v195));
        *(_DWORD *)((char *)v282 + *(int *)(*v282 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v282 + *(int *)(*v282 + 4) + 88) = 32;
        *(__int64 *)((char *)v282 + *(int *)(*v282 + 4) + 40) = 0;
        v283 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v282, (__int64)L"  ");
        v284 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v283, (__int64)L"  Flags=");
        LODWORD(v287) = 2;
        v285 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v284, &v287);
        v252 = std::basic_ostream<unsigned short>::operator<<(v285, *(unsigned __int8 *)(v241 + v195 + 16));
        goto LABEL_413;
      }
    }
  }
LABEL_416:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v305,
    L"Instance");
  mlib::XmlStream::WriteEndTag(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v304,
    L"Processor");
  mlib::XmlStream::WriteEndTag(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v304);
  return mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v305);
}

```

## disassembly

```asm
0x1400228c4  push    rbp
0x1400228c6  push    rbx
0x1400228c7  push    rsi
0x1400228c8  push    rdi
0x1400228c9  push    r12
0x1400228cb  push    r13
0x1400228cd  push    r14
0x1400228cf  push    r15
0x1400228d1  lea     rbp, [rsp-78h]
0x1400228d6  sub     rsp, 178h
0x1400228dd  mov     rax, cs:__security_cookie
0x1400228e4  xor     rax, rsp
0x1400228e7  mov     [rbp+0B0h+var_48], rax
0x1400228eb  mov     rdi, rcx
0x1400228ee  mov     [rbp+0B0h+var_68], rcx
0x1400228f2  lea     rdx, aProcessor_0; "Processor"
0x1400228f9  lea     rcx, [rbp+0B0h+var_130]
0x1400228fd  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022902  nop
0x140022903  lea     r14, asc_14012B480; ">"
0x14002290a  mov     r13d, 2
0x140022910  cmp     [rdi+8], r13d
0x140022914  jnz     short loc_140022921
0x140022916  mov     rdx, r14
0x140022919  mov     rcx, [rdi]
0x14002291c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022921  mov     [rdi+8], r13d
0x140022925  mov     rcx, rdi; this
0x140022928  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002292d  lea     rsi, asc_14012B484; "<"
0x140022934  mov     rdx, rsi
0x140022937  mov     rcx, [rdi]
0x14002293a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002293f  mov     rcx, rax
0x140022942  lea     rdx, [rbp+0B0h+var_130]
0x140022946  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002294b  mov     r15d, 1
0x140022951  add     [rdi+0Ch], r15d
0x140022955  xor     r12d, r12d
0x140022958  mov     [rdi+11h], r12b
0x14002295c  lea     rdx, aInstance; "Instance"
0x140022963  lea     rcx, [rsp+1B0h+var_138]
0x140022968  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002296d  nop
0x14002296e  cmp     [rdi+8], r13d
0x140022972  jnz     short loc_14002297F
0x140022974  mov     rdx, r14
0x140022977  mov     rcx, [rdi]
0x14002297a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002297f  mov     [rdi+8], r13d
0x140022983  mov     rcx, rdi; this
0x140022986  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002298b  mov     rdx, rsi
0x14002298e  mov     rcx, [rdi]
0x140022991  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022996  mov     rcx, rax
0x140022999  lea     rdx, [rsp+1B0h+var_138]
0x14002299e  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400229a3  add     [rdi+0Ch], r15d
0x1400229a7  mov     [rdi+11h], r12b
0x1400229ab  lea     rdx, aId; "id"
0x1400229b2  lea     rcx, [rsp+1B0h+var_190]
0x1400229b7  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400229bc  nop
0x1400229bd  mov     dword ptr [rdi+8], 3
0x1400229c4  lea     rdx, asc_14012B49C; " "
0x1400229cb  mov     rcx, [rdi]
0x1400229ce  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400229d3  mov     rcx, rax
0x1400229d6  lea     rdx, [rsp+1B0h+var_190]
0x1400229db  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400229e0  mov     rcx, rax
0x1400229e3  lea     rdx, asc_14012B498; "="
0x1400229ea  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400229ef  mov     rcx, rdi; this
0x1400229f2  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x1400229f7  xor     edx, edx
0x1400229f9  mov     rcx, [rdi]
0x1400229fc  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x140022a01  mov     rcx, rdi; this
0x140022a04  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022a09  nop
0x140022a0a  lea     rcx, [rsp+1B0h+var_190]
0x140022a0f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022a14  nop
0x140022a15  lea     rcx, [rsp+1B0h+var_138]
0x140022a1a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022a1f  nop
0x140022a20  lea     rcx, [rbp+0B0h+var_130]
0x140022a24  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022a29  lea     rdx, aProcessorname; "ProcessorName"
0x140022a30  lea     rcx, [rsp+1B0h+var_138]
0x140022a35  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022a3a  nop
0x140022a3b  cmp     [rdi+8], r13d
0x140022a3f  jnz     short loc_140022A4C
0x140022a41  mov     rdx, r14
0x140022a44  mov     rcx, [rdi]
0x140022a47  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022a4c  mov     [rdi+8], r13d
0x140022a50  mov     rcx, rdi; this
0x140022a53  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022a58  mov     rdx, rsi
0x140022a5b  mov     rcx, [rdi]
0x140022a5e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022a63  mov     rcx, rax
0x140022a66  lea     rdx, [rsp+1B0h+var_138]
0x140022a6b  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022a70  add     [rdi+0Ch], r15d
0x140022a74  mov     [rdi+11h], r12b
0x140022a78  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140022a7f  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140022a84  lea     rbx, [rax+8]
0x140022a88  mov     rcx, rdi; this
0x140022a8b  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140022a90  mov     rdx, rbx
0x140022a93  mov     rcx, [rdi]
0x140022a96  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022a9b  mov     rcx, rdi; this
0x140022a9e  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022aa3  lea     rdx, aProcessorname; "ProcessorName"
0x140022aaa  lea     rcx, [rbp+0B0h+var_130]
0x140022aae  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022ab3  nop
0x140022ab4  dec     dword ptr [rdi+0Ch]
0x140022ab7  mov     ecx, [rdi+8]
0x140022aba  sub     ecx, 1
0x140022abd  jz      short loc_140022AD0
0x140022abf  cmp     ecx, 1
0x140022ac2  jnz     short loc_140022B08
0x140022ac4  lea     rdx, asc_14012B488; "/>"
0x140022acb  mov     rcx, [rdi]
0x140022ace  jmp     short loc_140022B03
0x140022ad0  cmp     [rdi+11h], r12b
0x140022ad4  jnz     short loc_140022ADE
0x140022ad6  mov     rcx, rdi; this
0x140022ad9  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022ade  mov     [rdi+11h], r12b
0x140022ae2  lea     rdx, asc_14012B490; "</"
0x140022ae9  mov     rcx, [rdi]
0x140022aec  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022af1  mov     rcx, rax
0x140022af4  lea     rdx, [rbp+0B0h+var_130]
0x140022af8  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022afd  mov     rcx, rax
0x140022b00  mov     rdx, r14
0x140022b03  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022b08  mov     [rdi+8], r15d
0x140022b0c  lea     rcx, [rbp+0B0h+var_130]
0x140022b10  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022b15  nop
0x140022b16  lea     rcx, [rsp+1B0h+var_138]
0x140022b1b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022b20  lea     rdx, aTscfrequency; "TSCFrequency"
0x140022b27  lea     rcx, [rsp+1B0h+var_178]
0x140022b2c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022b31  nop
0x140022b32  cmp     [rdi+8], r13d
0x140022b36  jnz     short loc_140022B43
0x140022b38  mov     rdx, r14
0x140022b3b  mov     rcx, [rdi]
0x140022b3e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022b43  mov     [rdi+8], r13d
0x140022b47  mov     rcx, rdi; this
0x140022b4a  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022b4f  mov     rdx, rsi
0x140022b52  mov     rcx, [rdi]
0x140022b55  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022b5a  mov     rcx, rax
0x140022b5d  lea     rdx, [rsp+1B0h+var_178]
0x140022b62  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022b67  add     [rdi+0Ch], r15d
0x140022b6b  mov     [rdi+11h], r12b
0x140022b6f  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140022b76  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140022b7b  mov     rbx, [rax]
0x140022b7e  mov     rcx, rdi; this
0x140022b81  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140022b86  mov     rdx, rbx
0x140022b89  mov     rcx, [rdi]
0x140022b8c  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x140022b91  mov     rcx, rdi; this
0x140022b94  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022b99  lea     rdx, aTscfrequency; "TSCFrequency"
0x140022ba0  lea     rcx, [rsp+1B0h+var_180]
0x140022ba5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022baa  nop
0x140022bab  dec     dword ptr [rdi+0Ch]
0x140022bae  mov     ecx, [rdi+8]
0x140022bb1  sub     ecx, 1
0x140022bb4  jz      short loc_140022BC7
0x140022bb6  cmp     ecx, 1
0x140022bb9  jnz     short loc_140022C00
0x140022bbb  lea     rdx, asc_14012B488; "/>"
0x140022bc2  mov     rcx, [rdi]
0x140022bc5  jmp     short loc_140022BFB
0x140022bc7  cmp     [rdi+11h], r12b
0x140022bcb  jnz     short loc_140022BD5
0x140022bcd  mov     rcx, rdi; this
0x140022bd0  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022bd5  mov     [rdi+11h], r12b
0x140022bd9  lea     rdx, asc_14012B490; "</"
0x140022be0  mov     rcx, [rdi]
0x140022be3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022be8  mov     rcx, rax
0x140022beb  lea     rdx, [rsp+1B0h+var_180]
0x140022bf0  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022bf5  mov     rcx, rax
0x140022bf8  mov     rdx, r14
0x140022bfb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022c00  mov     [rdi+8], r15d
0x140022c04  lea     rdx, aNumprocs; "NumProcs"
0x140022c0b  lea     rcx, [rsp+1B0h+var_140]
0x140022c10  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022c15  nop
0x140022c16  cmp     [rdi+8], r13d
0x140022c1a  jnz     short loc_140022C27
0x140022c1c  mov     rdx, r14
0x140022c1f  mov     rcx, [rdi]
0x140022c22  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022c27  mov     [rdi+8], r13d
0x140022c2b  mov     rcx, rdi; this
0x140022c2e  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022c33  mov     rdx, rsi
0x140022c36  mov     rcx, [rdi]
0x140022c39  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022c3e  mov     rcx, rax
0x140022c41  lea     rdx, [rsp+1B0h+var_140]
0x140022c46  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022c4b  add     [rdi+0Ch], r15d
0x140022c4f  mov     [rdi+11h], r12b
0x140022c53  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140022c5a  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140022c5f  mov     ebx, [rax+1C0h]
0x140022c65  mov     rcx, rdi; this
0x140022c68  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140022c6d  mov     edx, ebx
0x140022c6f  mov     rcx, [rdi]
0x140022c72  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140022c77  mov     rcx, rdi; this
0x140022c7a  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022c7f  lea     rdx, aNumprocs; "NumProcs"
0x140022c86  lea     rcx, [rsp+1B0h+var_148]
0x140022c8b  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022c90  nop
0x140022c91  dec     dword ptr [rdi+0Ch]
0x140022c94  mov     ecx, [rdi+8]
0x140022c97  sub     ecx, 1
0x140022c9a  jz      short loc_140022CAD
0x140022c9c  cmp     ecx, 1
0x140022c9f  jnz     short loc_140022CE6
0x140022ca1  lea     rdx, asc_14012B488; "/>"
0x140022ca8  mov     rcx, [rdi]
0x140022cab  jmp     short loc_140022CE1
0x140022cad  cmp     [rdi+11h], r12b
0x140022cb1  jnz     short loc_140022CBB
0x140022cb3  mov     rcx, rdi; this
0x140022cb6  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022cbb  mov     [rdi+11h], r12b
0x140022cbf  lea     rdx, asc_14012B490; "</"
0x140022cc6  mov     rcx, [rdi]
0x140022cc9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022cce  mov     rcx, rax
0x140022cd1  lea     rdx, [rsp+1B0h+var_148]
0x140022cd6  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022cdb  mov     rcx, rax
0x140022cde  mov     rdx, r14
0x140022ce1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022ce6  mov     [rdi+8], r15d
0x140022cea  lea     rdx, aNumcores; "NumCores"
0x140022cf1  lea     rcx, [rsp+1B0h+var_150]
0x140022cf6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022cfb  nop
0x140022cfc  cmp     [rdi+8], r13d
0x140022d00  jnz     short loc_140022D0D
0x140022d02  mov     rdx, r14
0x140022d05  mov     rcx, [rdi]
0x140022d08  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022d0d  mov     [rdi+8], r13d
0x140022d11  mov     rcx, rdi; this
0x140022d14  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022d19  mov     rdx, rsi
0x140022d1c  mov     rcx, [rdi]
0x140022d1f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022d24  mov     rcx, rax
0x140022d27  lea     rdx, [rsp+1B0h+var_150]
0x140022d2c  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022d31  add     [rdi+0Ch], r15d
0x140022d35  mov     [rdi+11h], r12b
0x140022d39  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140022d40  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140022d45  mov     ebx, [rax+1C4h]
0x140022d4b  mov     rcx, rdi; this
0x140022d4e  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140022d53  mov     edx, ebx
0x140022d55  mov     rcx, [rdi]
0x140022d58  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140022d5d  mov     rcx, rdi; this
0x140022d60  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022d65  lea     rdx, aNumcores; "NumCores"
  ... truncated ...
```
