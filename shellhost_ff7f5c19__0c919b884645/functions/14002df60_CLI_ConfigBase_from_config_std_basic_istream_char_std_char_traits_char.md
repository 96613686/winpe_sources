# CLI::ConfigBase::from_config(std::basic_istream<char,std::char_traits<char>> &)

- ea: `0x14002df60`
- end: `0x1400304ac`
- name: `?from_config@ConfigBase@CLI@@UEBA?AV?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@AEAV?$basic_istream@DU?$char_traits@D@std@@@4@@Z`
- size: `9548`
- prototype: ``
- caller_count: `0`
- callee_count: `54`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140007fe0`
- `0x1400083f0`
- `0x140008614`
- `0x140008910`
- `0x140008a50`
- `0x140008d50`
- `0x140009870`
- `0x14000aae0`
- `0x14000b0a0`
- `0x14000b0f0`
- `0x14000b57c`
- `0x14000c338`
- `0x14000c868`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010608`
- `0x140010614`
- `0x140010d40`
- `0x140010e40`
- `0x1400112e0`
- `0x140011f20`
- `0x140012cd0`
- `0x140013940`
- `0x1400149b0`
- `0x14001ad90`
- `0x14001ae70`
- `0x14001bf10`
- `0x140029950`
- `0x14002b4f0`
- `0x14002c790`
- `0x14002cf50`
- `0x14002cfa0`
- `0x14002df60`
- `0x1400304c0`
- `0x140030720`
- `0x140035cf0`
- `0x14003ca60`
- `0x14003d400`
- `0x14003e490`
- `0x140040890`
- `0x140041330`
- `0x140043eb0`
- `0x140043ed0`
- `0x1400447fc`
- `0x1400455d0`
- `0x14004a9e0`
- `0x14004aaac`
- `0x14004c1a4`
- `0x14004e1b4`

## import_xrefs

- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x14002e183`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x14002eff3`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x14002ff43`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x14002e183`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x14002eff3`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x14002ff43`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x14002f330`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x14002f330`
- `msvcp_win!?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z` at `0x14002e15c`
- `msvcp_win!?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z` at `0x14002efcc`
- `msvcp_win!?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z` at `0x14002f309`
- `msvcp_win!?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z` at `0x14002ff1c`
- `msvcp_win!?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z` at `0x14002e15c`
- `msvcp_win!?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z` at `0x14002efcc`
- `msvcp_win!?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z` at `0x14002f309`
- `msvcp_win!?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z` at `0x14002ff1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
_QWORD *__fastcall CLI::ConfigBase::from_config(_BYTE *a1, _QWORD *a2, __int64 a3)
{
  __int64 v3; // rdi
  _QWORD *v4; // r12
  _BYTE *v5; // r15
  int v6; // r14d
  char v7; // dl
  char *v8; // rax
  size_t v9; // rdx
  unsigned __int8 v10; // al
  __int64 v11; // rax
  void **v12; // rdi
  unsigned __int64 v13; // r13
  unsigned __int64 v14; // rbx
  size_t v15; // rax
  void *v16; // rax
  void *v17; // rcx
  _QWORD *v18; // rax
  size_t v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // rdx
  void *v23; // rcx
  __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  void *v26; // rcx
  __int64 v27; // r14
  __int64 v28; // rbx
  unsigned __int64 v29; // rdx
  void *v30; // rcx
  void **v31; // rbx
  void **v32; // rdi
  unsigned __int64 v33; // rdx
  char *v34; // rax
  unsigned __int64 v35; // rdx
  _BYTE *v36; // rcx
  unsigned __int64 v37; // rdx
  _BYTE *v38; // rcx
  void **v39; // rax
  void **v40; // rdi
  unsigned __int64 v41; // xmm0_8
  unsigned __int64 v42; // rsi
  bool v43; // cf
  int v44; // eax
  void **v45; // rax
  bool v46; // cf
  int v47; // eax
  void **v48; // rax
  void **v49; // rax
  void **v50; // rcx
  __int64 v51; // rdx
  __int64 parents; // rax
  __int64 v53; // r8
  void **v54; // rdx
  unsigned __int64 v55; // rdx
  void *v56; // rcx
  void **v57; // xmm1_8
  __int64 v58; // rcx
  void **v59; // rax
  unsigned __int64 v60; // xmm0_8
  void **v61; // rax
  __int64 v62; // r8
  void **v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rax
  const void *v66; // rcx
  void **v67; // rdx
  void **v68; // rcx
  void **v69; // rdi
  size_t v70; // rsi
  size_t v71; // rbx
  int v72; // ebx
  void **v73; // rdx
  unsigned __int64 v74; // rdx
  void *v75; // rcx
  char *v76; // rbx
  char *v77; // rdi
  unsigned __int64 v78; // rdx
  _BYTE *v79; // rcx
  void **v80; // rax
  void **v81; // rax
  void **v82; // rcx
  unsigned __int64 first_of; // rbx
  void **v84; // rcx
  void **v85; // rax
  int v86; // ecx
  __int64 v87; // r8
  void **v88; // r8
  void **v89; // rcx
  unsigned __int64 v90; // rdi
  void **v91; // rcx
  unsigned __int64 v92; // rax
  unsigned __int64 v93; // r12
  unsigned __int64 v94; // r8
  void **v95; // rdx
  __int64 v96; // rbx
  unsigned __int64 v97; // rdx
  void *v98; // rcx
  unsigned __int64 v99; // rbx
  __int64 v100; // r8
  void **v101; // rdx
  unsigned __int64 v102; // rdi
  __int64 v103; // r15
  _QWORD *v104; // rcx
  _QWORD *v105; // rsi
  unsigned __int64 v106; // r14
  _QWORD *v107; // rcx
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rdx
  unsigned __int8 v111; // al
  __int64 v112; // rax
  _QWORD *v113; // rax
  __int64 v114; // rax
  __int64 v115; // r8
  __int64 v116; // rdx
  __int64 v117; // rax
  void **v118; // rcx
  char *v119; // rax
  char v120; // r14
  __int64 v121; // r13
  __int64 v122; // r8
  void **v123; // rdx
  unsigned __int64 v124; // rdx
  char v125; // si
  char v126; // di
  char v127; // bl
  unsigned __int8 v128; // al
  __int64 v129; // rax
  __int128 *v130; // rdx
  __int64 v131; // r9
  void **v132; // rax
  __int64 v133; // rcx
  void **v134; // rax
  __int64 v135; // rcx
  void **v136; // rax
  __int64 v137; // rcx
  void **v138; // rax
  unsigned __int64 v139; // rcx
  _QWORD *v140; // rax
  _QWORD *v141; // rax
  unsigned __int64 v142; // rcx
  _QWORD *v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  unsigned __int64 v146; // rcx
  _QWORD *v147; // rax
  __int128 *v148; // rax
  __int64 v149; // r8
  __int128 *v150; // rax
  unsigned __int64 v151; // rdx
  void *v152; // rcx
  void **v153; // rdx
  __int64 v154; // rbx
  __int64 v155; // rax
  __int64 v156; // r8
  __int64 v157; // rdx
  char *v158; // rdi
  char *v159; // rbx
  char *v160; // r14
  char *v161; // rbx
  unsigned __int64 v162; // rdx
  void *v163; // rcx
  char *v164; // rbx
  char *v165; // rdi
  unsigned __int64 v166; // rdx
  _BYTE *v167; // rcx
  __int64 v168; // rsi
  const void *v169; // rdx
  char *i; // rdi
  unsigned __int64 v171; // rdx
  void *v172; // rcx
  char *v173; // rbx
  char *v174; // rdi
  void **v175; // rcx
  __int64 v176; // rdi
  unsigned __int64 v177; // rdx
  void *v178; // rcx
  void **v179; // rdi
  unsigned __int64 v180; // rdx
  void *v181; // rcx
  void **v182; // rdi
  void **v183; // rax
  char v184; // bl
  unsigned __int8 v185; // al
  __int64 v186; // rax
  __int64 v187; // rax
  void **v188; // rax
  unsigned __int64 v189; // rdx
  void *v190; // rcx
  void **v191; // rdi
  unsigned __int64 v192; // rdx
  char *v193; // rax
  unsigned __int64 v194; // rdx
  char *v195; // rcx
  void **v196; // rcx
  __int64 v197; // rdx
  __int64 v198; // rax
  char *v199; // rbx
  char *v200; // rdi
  unsigned __int64 v201; // rdx
  _BYTE *v202; // rcx
  __int64 j; // rbx
  __int64 v204; // rbx
  unsigned __int64 v205; // rdx
  void *v206; // rcx
  unsigned __int64 v207; // rdx
  void *v208; // rcx
  unsigned __int64 v209; // rdx
  void *v210; // rcx
  unsigned __int64 v211; // rdx
  void *v212; // rcx
  unsigned __int64 v213; // rdx
  void *v214; // rcx
  unsigned __int64 v215; // rdx
  void *v216; // rcx
  __int64 v218; // rax
  __int64 v219; // rax
  __int64 v220; // rax
  __int64 v221; // rax
  char v222; // [rsp+30h] [rbp-2D8h]
  unsigned __int8 v223; // [rsp+31h] [rbp-2D7h]
  char v224; // [rsp+32h] [rbp-2D6h]
  char v225; // [rsp+33h] [rbp-2D5h]
  char v226; // [rsp+34h] [rbp-2D4h]
  char v227; // [rsp+35h] [rbp-2D3h]
  int v228; // [rsp+38h] [rbp-2D0h]
  void *v230[2]; // [rsp+58h] [rbp-2B0h] BYREF
  __int64 v231; // [rsp+68h] [rbp-2A0h]
  _BYTE v232[4]; // [rsp+70h] [rbp-298h] BYREF
  int v233; // [rsp+74h] [rbp-294h]
  _QWORD *v234; // [rsp+78h] [rbp-290h]
  void *v235[2]; // [rsp+80h] [rbp-288h] BYREF
  __int64 v236; // [rsp+90h] [rbp-278h]
  _BYTE *v237; // [rsp+A0h] [rbp-268h]
  __int64 v238; // [rsp+A8h] [rbp-260h] BYREF
  _QWORD v239[2]; // [rsp+B0h] [rbp-258h] BYREF
  const std::invalid_argument *v240; // [rsp+C0h] [rbp-248h] BYREF
  const std::invalid_argument *v241[2]; // [rsp+C8h] [rbp-240h] BYREF
  void *v242[2]; // [rsp+D8h] [rbp-230h] BYREF
  __m128i v243; // [rsp+E8h] [rbp-220h]
  void *v244[2]; // [rsp+F8h] [rbp-210h] BYREF
  __m128i v245; // [rsp+108h] [rbp-200h]
  void *v246[2]; // [rsp+118h] [rbp-1F0h] BYREF
  size_t v247[2]; // [rsp+128h] [rbp-1E0h]
  _QWORD v248[2]; // [rsp+138h] [rbp-1D0h] BYREF
  unsigned __int64 v249; // [rsp+148h] [rbp-1C0h]
  unsigned __int64 v250; // [rsp+150h] [rbp-1B8h]
  void *Buf1[2]; // [rsp+158h] [rbp-1B0h] BYREF
  size_t Size[2]; // [rsp+168h] [rbp-1A0h]
  __int128 v253; // [rsp+178h] [rbp-190h] BYREF
  __int64 v254; // [rsp+188h] [rbp-180h]
  unsigned __int64 v255; // [rsp+190h] [rbp-178h]
  _BYTE v256[32]; // [rsp+198h] [rbp-170h] BYREF
  void *Buf2[2]; // [rsp+1B8h] [rbp-150h] BYREF
  __int64 v258; // [rsp+1C8h] [rbp-140h]
  unsigned __int64 v259; // [rsp+1D0h] [rbp-138h]
  void *Src[2]; // [rsp+1D8h] [rbp-130h] BYREF
  unsigned __int64 v261; // [rsp+1E8h] [rbp-120h]
  unsigned __int64 v262; // [rsp+1F0h] [rbp-118h]
  __int128 v263; // [rsp+1F8h] [rbp-110h] BYREF
  __m128i v264; // [rsp+208h] [rbp-100h]
  void *v265[2]; // [rsp+218h] [rbp-F0h] BYREF
  __int64 v266; // [rsp+228h] [rbp-E0h]
  unsigned __int64 v267; // [rsp+230h] [rbp-D8h]
  _BYTE v268[64]; // [rsp+240h] [rbp-C8h] BYREF
  _BYTE v269[64]; // [rsp+280h] [rbp-88h] BYREF

  v3 = a3;
  v4 = a2;
  v234 = a2;
  v5 = a1;
  v237 = a1;
  v241[1] = (const std::invalid_argument *)a2;
  *(_OWORD *)v244 = 0;
  v245.m128i_i64[0] = 0;
  v245.m128i_i64[1] = 15;
  LOBYTE(v244[0]) = 0;
  *(_OWORD *)Src = 0;
  v261 = 0;
  v262 = 15;
  LOBYTE(Src[0]) = 0;
  HIWORD(Buf1[1]) = 0;
  Size[0] = 7;
  Size[1] = 15;
  qmemcpy(Buf1, "defaul", 6);
  *(void **)((char *)Buf1 + 6) = (void *)(unsigned __int8)aDefault[6];
  HIWORD(Buf2[1]) = 0;
  v258 = 7;
  v259 = 15;
  qmemcpy(Buf2, "defaul", 6);
  *(void **)((char *)Buf2 + 6) = (void *)(unsigned __int8)aDefault[6];
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v6 = 1;
  v7 = a1[33];
  v226 = v7;
  if ( v7 == 91 )
  {
    v8 = a1 + 34;
    if ( a1[34] == 93 && a1[35] == 44 )
    {
      v222 = 1;
LABEL_5:
      v225 = 0;
      v224 = 0;
      v227 = *v8;
      goto LABEL_6;
    }
  }
  v8 = a1 + 34;
  if ( v7 )
  {
    v222 = 0;
    if ( v7 != 32 )
      goto LABEL_5;
  }
  v222 = 0;
  if ( v7 != *v8 )
    goto LABEL_5;
  v225 = 1;
  v224 = 0;
  v226 = 91;
  v227 = 93;
  if ( a1[35] == 32 )
  {
    v223 = 44;
    goto LABEL_7;
  }
LABEL_6:
  v223 = a1[35];
LABEL_7:
  v233 = 0;
  v232[0] = a1[40];
  v232[1] = a1[32];
  v232[2] = a1[36];
  *(_OWORD *)v265 = 0;
  v266 = 0;
  v267 = 0;
  std::string::_Construct<1,char const *>(v265, v232, 3);
  while ( 1 )
  {
    LOBYTE(v9) = 10;
    v10 = std::ios::widen(v3 + *(int *)(*(_QWORD *)v3 + 4LL), v9);
    v11 = std::getline<char,std::char_traits<char>,std::allocator<char>>(v3, Src, v10);
    if ( !(unsigned __int8)std::ios_base::operator bool(v11 + *(int *)(*(_QWORD *)v11 + 4LL)) )
      break;
    *(_OWORD *)v230 = 0;
    v231 = 0;
    *(_OWORD *)v246 = 0;
    v247[0] = 0;
    v247[1] = 15;
    LOBYTE(v246[0]) = 0;
    *(_OWORD *)v242 = 0;
    v243 = 0u;
    v12 = Src;
    if ( v262 > 0xF )
      v12 = (void **)Src[0];
    v13 = v261;
    if ( v261 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlen_string();
    if ( v261 > 0xF )
    {
      v14 = v261 | 0xF;
      if ( (v261 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
      {
        v14 = 0x7FFFFFFFFFFFFFFFLL;
        v15 = 0x8000000000000027uLL;
        goto LABEL_22;
      }
      if ( v14 < 0x16 )
        v14 = 22;
      v19 = v14 + 1;
      if ( v14 == -1 )
      {
        v18 = 0;
      }
      else if ( v19 < 0x1000 )
      {
        v18 = operator new(v19);
      }
      else
      {
        v15 = v14 + 40;
        if ( v14 + 40 < v14 + 1 )
          std::_Throw_bad_array_new_length();
LABEL_22:
        v16 = operator new(v15);
        v17 = v16;
        if ( !v16 )
          goto LABEL_119;
        v18 = (_QWORD *)(((unsigned __int64)v16 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v18 - 1) = v17;
      }
      v242[0] = v18;
      v243.m128i_i64[0] = v13;
      v243.m128i_i64[1] = v14;
      memcpy_0(v18, v12, v13 + 1);
      goto LABEL_33;
    }
    v243.m128i_i64[0] = v261;
    v243.m128i_i64[1] = 15;
    *(_OWORD *)v242 = *(_OWORD *)v12;
LABEL_33:
    v20 = CLI::detail::rtrim(v242);
    v21 = CLI::detail::ltrim(v20);
    std::string::string(&v263, v21);
    v228 = v6 | 2;
    if ( v243.m128i_i64[1] > 0xFuLL )
    {
      v22 = v243.m128i_i64[1] + 1;
      v23 = v242[0];
      if ( (unsigned __int64)(v243.m128i_i64[1] + 1) >= 0x1000 )
      {
        if ( (unsigned __int64)v242[0] - *((_QWORD *)v242[0] - 1) - 8 > 0x1F )
          goto LABEL_119;
        v22 = v243.m128i_i64[1] + 40;
        v23 = (void *)*((_QWORD *)v242[0] - 1);
      }
      operator delete(v23, v22);
    }
    v24 = v245.m128i_i64[1];
    if ( v245.m128i_i64[1] > 0xFuLL )
    {
      v25 = v245.m128i_i64[1] + 1;
      v26 = v244[0];
      if ( (unsigned __int64)(v245.m128i_i64[1] + 1) >= 0x1000 )
      {
        if ( (unsigned __int64)v244[0] - *((_QWORD *)v244[0] - 1) - 8 > 0x1F )
          goto LABEL_119;
        v25 = v245.m128i_i64[1] + 40;
        v26 = (void *)*((_QWORD *)v244[0] - 1);
      }
      operator delete(v26, v25);
    }
    *(_OWORD *)v244 = v263;
    v245 = v264;
    v27 = v264.m128i_i64[0];
    v28 = v264.m128i_i64[0];
    if ( v264.m128i_i64[0] >= 3uLL )
    {
      v39 = v244;
      v40 = (void **)v263;
      v41 = _mm_srli_si128(v264, 8).m128i_u64[0];
      v42 = v41;
      if ( v41 > 0xF )
        v39 = (void **)v263;
      v43 = *(_BYTE *)v39 < 0x22u;
      if ( *(_BYTE *)v39 == 34
        && (v43 = *((_BYTE *)v39 + 1) < 0x22u, *((_BYTE *)v39 + 1) == 34)
        && (v43 = *((_BYTE *)v39 + 2) < 0x22u, *((_BYTE *)v39 + 2) == 34) )
      {
        v44 = 0;
      }
      else
      {
        v44 = v43 ? -1 : 1;
      }
      if ( !v44 )
        goto LABEL_397;
      v45 = v244;
      if ( v41 > 0xF )
        v45 = (void **)v263;
      v46 = *(_BYTE *)v45 < 0x27u;
      if ( *(_BYTE *)v45 == 39
        && (v46 = *((_BYTE *)v45 + 1) < 0x27u, *((_BYTE *)v45 + 1) == 39)
        && (v46 = *((_BYTE *)v45 + 2) < 0x27u, *((_BYTE *)v45 + 2) == 39) )
      {
        v47 = 0;
      }
      else
      {
        v47 = v46 ? -1 : 1;
      }
      if ( v47 )
      {
        v48 = v244;
        if ( v41 > 0xF )
          v48 = (void **)v263;
        if ( *(_BYTE *)v48 != 91 )
          goto LABEL_152;
        v49 = v244;
        if ( v41 > 0xF )
          v49 = (void **)v263;
        if ( *((_BYTE *)v49 + v264.m128i_i64[0] - 1) == 93 )
        {
          v50 = Buf1;
          if ( Size[1] > 0xF )
            v50 = (void **)Buf1[0];
          if ( Size[0] != 7 || memcmp_0(v50, "default", 7u) )
          {
            v51 = v4[1];
            if ( v51 == v4[2] )
            {
              std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(v4);
            }
            else
            {
              *(_QWORD *)v51 = 0;
              *(_QWORD *)(v51 + 8) = 0;
              *(_QWORD *)(v51 + 16) = 0;
              *(_OWORD *)(v51 + 24) = 0;
              *(_QWORD *)(v51 + 40) = 0;
              *(_QWORD *)(v51 + 48) = 15;
              *(_BYTE *)(v51 + 24) = 0;
              *(_QWORD *)(v51 + 56) = 0;
              *(_QWORD *)(v51 + 64) = 0;
              *(_QWORD *)(v51 + 72) = 0;
              v4[1] += 80LL;
            }
            parents = CLI::detail::generate_parents(v242, Buf1, v246, (unsigned __int8)v5[40]);
            std::vector<std::string>::operator=(v4[1] - 80LL, parents);
            std::vector<std::string>::_Tidy(v242);
            std::string::_Assign<char>(v4[1] - 56LL, "--", 2);
            v42 = v245.m128i_u64[1];
            v27 = v245.m128i_i64[0];
            v40 = (void **)v244[0];
          }
          *(_OWORD *)v242 = 0;
          v243 = 0u;
          if ( !v27 )
            std::_String_val<std::_Simple_types<char>>::_Xran();
          v53 = v28 - 2;
          if ( v27 - 1 < (unsigned __int64)(v28 - 2) )
            v53 = v27 - 1;
          v54 = v244;
          if ( v42 > 0xF )
            v54 = v40;
          std::string::_Construct<1,char const *>(v242, (char *)v54 + 1, v53);
          v6 = v228 | 4;
          if ( Size[1] > 0xF )
          {
            v55 = Size[1] + 1;
            v56 = Buf1[0];
            if ( Size[1] + 1 >= 0x1000 )
            {
              if ( (unsigned __int64)Buf1[0] - *((_QWORD *)Buf1[0] - 1) - 8 > 0x1F )
LABEL_119:
                __fastfail(5u);
              v55 = Size[1] + 40;
              v56 = (void *)*((_QWORD *)Buf1[0] - 1);
            }
            operator delete(v56, v55);
          }
          v57 = (void **)v242[0];
          *(_OWORD *)Buf1 = *(_OWORD *)v242;
          *(__m128i *)Size = v243;
          v58 = v243.m128i_i64[0];
          if ( v243.m128i_i64[0] > 1uLL )
          {
            v59 = Buf1;
            v60 = _mm_srli_si128(v243, 8).m128i_u64[0];
            if ( v60 > 0xF )
              v59 = (void **)v242[0];
            if ( *(_BYTE *)v59 == 91 )
            {
              v61 = Buf1;
              if ( v60 > 0xF )
                v61 = (void **)v242[0];
              if ( *((_BYTE *)v61 + v243.m128i_i64[0] - 1) == 93 )
              {
                v62 = v243.m128i_i64[0] - 2;
                *(_OWORD *)v242 = 0;
                v243 = 0u;
                if ( v58 - 1 < (unsigned __int64)(v58 - 2) )
                  v62 = v58 - 1;
                v63 = Buf1;
                if ( v60 > 0xF )
                  v63 = v57;
                std::string::_Construct<1,char const *>(v242, (char *)v63 + 1, v62);
                v6 = v228 | 0x44;
                if ( Size[1] > 0xF )
                  std::string::_Deallocate_for_capacity(Buf1, Buf1[0]);
                *(_OWORD *)Buf1 = *(_OWORD *)v242;
                *(__m128i *)Size = v243;
                v243.m128i_i64[0] = 0;
                v243.m128i_i64[1] = 15;
                LOBYTE(v242[0]) = 0;
                std::string::_Tidy_deallocate(v242);
              }
            }
          }
          v64 = std::string::string(v242, Buf1);
          v65 = CLI::detail::to_lower(&v263, v64);
          if ( *(_QWORD *)(v65 + 24) <= 0xFu )
            v66 = (const void *)v65;
          else
            v66 = *(const void **)v65;
          if ( *(_QWORD *)(v65 + 16) != 7 )
          {
            std::string::_Tidy_deallocate(&v263);
LABEL_123:
            CLI::detail::checkParentSegments(v4, Buf1, (unsigned __int8)v5[40]);
            goto LABEL_124;
          }
          v72 = memcmp_0(v66, "default", 7u);
          std::string::_Tidy_deallocate(&v263);
          if ( v72 )
            goto LABEL_123;
          std::string::_Assign<char>(Buf1, "default", 7);
LABEL_124:
          v67 = Buf2;
          if ( v259 > 0xF )
            v67 = (void **)Buf2[0];
          v68 = Buf1;
          v69 = (void **)Buf1[0];
          v70 = Size[1];
          if ( Size[1] > 0xF )
            v68 = (void **)Buf1[0];
          v71 = Size[0];
          if ( Size[0] == v258 && (!Size[0] || !memcmp_0(v68, v67, Size[0])) )
          {
            ++v233;
          }
          else
          {
            v233 = 0;
            v73 = Buf1;
            if ( v70 > 0xF )
              v73 = v69;
            std::string::_Assign<char>(Buf2, v73, v71);
          }
          v9 = v247[1];
          if ( v247[1] > 0xF )
          {
            v74 = v247[1] + 1;
            v75 = v246[0];
            if ( v247[1] + 1 >= 0x1000 )
            {
              if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
                goto LABEL_418;
              v74 = v247[1] + 40;
              v75 = (void *)*((_QWORD *)v246[0] - 1);
            }
            operator delete(v75, v74);
          }
          v247[0] = 0;
          v247[1] = 15;
          LOBYTE(v246[0]) = 0;
          v76 = (char *)v230[0];
          if ( v230[0] )
          {
            v77 = (char *)v230[1];
            if ( v230[0] != v230[1] )
            {
              do
              {
                std::string::_Tidy_deallocate(v76);
                v76 += 32;
              }
              while ( v76 != v77 );
              v76 = (char *)v230[0];
            }
            v78 = (v231 - (_QWORD)v76) & 0xFFFFFFFFFFFFFFE0uLL;
            if ( v78 < 0x1000 )
            {
              v79 = v76;
            }
            else
            {
              v79 = (_BYTE *)*((_QWORD *)v76 - 1);
              if ( (unsigned __int64)(v76 - v79 - 8) > 0x1F )
                goto LABEL_449;
              v78 += 39LL;
            }
            operator delete(v79, v78);
          }
          v224 = 0;
          v3 = a3;
        }
        else
        {
LABEL_152:
          v80 = v244;
          if ( v41 > 0xF )
            v80 = (void **)v263;
          if ( *(_BYTE *)v80 == 59 )
            goto LABEL_388;
          v81 = v244;
          if ( v41 > 0xF )
            v81 = (void **)v263;
          if ( *(_BYTE *)v81 == 35 )
            goto LABEL_388;
          v82 = v244;
          if ( v41 > 0xF )
            v82 = (void **)v263;
          if ( *(_BYTE *)v82 == v5[32] )
          {
LABEL_388:
            v9 = v247[1];
            if ( v247[1] > 0xF )
            {
              v180 = v247[1] + 1;
              v181 = v246[0];
              if ( v247[1] + 1 >= 0x1000 )
              {
                if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
                  goto LABEL_418;
                v180 = v247[1] + 40;
                v181 = (void *)*((_QWORD *)v246[0] - 1);
              }
              operator delete(v181, v180);
            }
            v247[0] = 0;
            v247[1] = 15;
            LOBYTE(v246[0]) = 0;
            v31 = (void **)v230[0];
            v3 = a3;
            v6 = v228;
            if ( v230[0] )
            {
              v182 = (void **)v230[1];
              if ( v230[0] == v230[1] )
                goto LABEL_59;
              do
              {
                std::string::_Tidy_deallocate(v31);
                v31 += 4;
              }
              while ( v31 != v182 );
              goto LABEL_58;
            }
          }
          else
          {
            first_of = 0;
            v84 = v244;
            if ( v41 > 0xF )
              LODWORD(v84) = v263;
            if ( std::_Traits_find_first_of<std::char_traits<char>>(
                   (_DWORD)v84,
                   v264.m128i_i32[0],
                   0,
                   (unsigned int)"\"'`",
                   3) != -1
              && v245.m128i_i64[0] )
            {
              do
              {
                v85 = v244;
                if ( v245.m128i_i64[1] > 0xFuLL )
                  v85 = (void **)v244[0];
                v86 = *((unsigned __int8 *)v85 + first_of);
                if ( (unsigned __int8)(v86 - 34) <= 0x3Eu
                  && (v87 = 0x4000000000000021LL, _bittest64(&v87, (unsigned int)(v86 - 34))) )
                {
                  v88 = v244;
                  if ( v245.m128i_i64[1] > 0xFuLL )
                    v88 = (void **)v244[0];
                  first_of = CLI::detail::close_sequence(v244, first_of, *((unsigned __int8 *)v88 + first_of)) + 1;
                }
                else
                {
                  if ( (_BYTE)v86 == v5[36] || (_BYTE)v86 == v5[32] )
                  {
                    --first_of;
                    break;
                  }
                  if ( (_BYTE)v86 == 32 || (_BYTE)v86 == 9 || (_BYTE)v86 == v5[40] )
                    ++first_of;
                  else
                    first_of = std::string::find_first_of(v244, v265, first_of);
                }
              }
              while ( first_of < v245.m128i_i64[0] );
            }
            v89 = v244;
            if ( v245.m128i_i64[1] > 0xFuLL )
              v89 = (void **)v244[0];
            v90 = std::_Traits_find_ch<std::char_traits<char>>(
                    v89,
                    v245.m128i_i64[0],
                    first_of + 1,
                    (unsigned __int8)v5[36]);
            v91 = v244;
            if ( v245.m128i_i64[1] > 0xFuLL )
              v91 = (void **)v244[0];
            v92 = std::_Traits_find_ch<std::char_traits<char>>(
                    v91,
                    v245.m128i_i64[0],
                    first_of,
                    (unsigned __int8)v5[32]);
            v93 = v92;
            if ( v92 < v90 || v90 == -1 )
            {
              *(_OWORD *)v242 = 0;
              v243 = 0u;
              if ( v245.m128i_i64[0] < v92 )
                v93 = v245.m128i_i64[0];
              v153 = v244;
              if ( v245.m128i_i64[1] > 0xFuLL )
                v153 = (void **)v244[0];
              std::string::_Construct<1,char const *>(v242, v153, v93);
              v228 |= 0x20u;
              v154 = CLI::detail::trim_copy(v256, v242);
              if ( v246 != (void **)v154 )
              {
                if ( v247[1] > 0xF )
                  std::string::_Deallocate_for_capacity(v246, v246[0]);
                v247[0] = 0;
                v247[1] = 15;
                LOBYTE(v246[0]) = 0;
                *(_OWORD *)v246 = *(_OWORD *)v154;
                *(_OWORD *)v247 = *(_OWORD *)(v154 + 16);
                *(_QWORD *)(v154 + 16) = 0;
                *(_QWORD *)(v154 + 24) = 15;
                *(_BYTE *)v154 = 0;
              }
              std::string::_Tidy_deallocate(v256);
              std::string::_Tidy_deallocate(v242);
              *(_OWORD *)v242 = 0;
              v243.m128i_i64[0] = 4;
              v243.m128i_i64[1] = 15;
              strcpy((char *)v242, "true");
              std::vector<std::string>::_Assign_counted_range<std::string const *>(v230, v242, 1);
              `eh vector destructor iterator'(v242, 0x20u, 1u, std::string::_Tidy_deallocate);
              goto LABEL_322;
            }
            *(_OWORD *)v242 = 0;
            v243 = 0u;
            v94 = v90;
            if ( v245.m128i_i64[0] < v90 )
              v94 = v245.m128i_i64[0];
            v95 = v244;
            if ( v245.m128i_i64[1] > 0xFuLL )
              v95 = (void **)v244[0];
            std::string::_Construct<1,char const *>(v242, v95, v94);
            v96 = CLI::detail::trim_copy(&v263, v242);
            if ( v246 != (void **)v96 )
            {
              if ( v247[1] > 0xF )
              {
                v97 = v247[1] + 1;
                v98 = v246[0];
                if ( v247[1] + 1 >= 0x1000 )
                {
                  if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
                    __fastfail(5u);
                  v97 = v247[1] + 40;
                  v98 = (void *)*((_QWORD *)v246[0] - 1);
                }
                operator delete(v98, v97);
              }
              v247[0] = 0;
              v247[1] = 15;
              LOBYTE(v246[0]) = 0;
              *(_OWORD *)v246 = *(_OWORD *)v96;
              *(_OWORD *)v247 = *(_OWORD *)(v96 + 16);
              *(_QWORD *)(v96 + 16) = 0;
              *(_QWORD *)(v96 + 24) = 15;
              *(_BYTE *)v96 = 0;
            }
            std::string::_Tidy_deallocate(&v263);
            std::string::_Tidy_deallocate(v242);
            v99 = v90 + 1;
            *(_OWORD *)v242 = 0;
            v243 = 0u;
            if ( v245.m128i_i64[0] < v90 + 1 )
              std::_String_val<std::_Simple_types<char>>::_Xran();
            v100 = -1;
            if ( v245.m128i_i64[0] - v99 != -1 )
              v100 = v245.m128i_i64[0] - v99;
            v101 = v244;
            if ( v245.m128i_i64[1] > 0xFuLL )
              v101 = (void **)v244[0];
            std::string::_Construct<1,char const *>(v242, (char *)v101 + v99, v100);
            v228 |= 0x18u;
            CLI::detail::trim_copy(v248, v242);
            if ( v243.m128i_i64[1] > 0xFuLL )
              std::string::_Deallocate_for_capacity(v242, v242[0]);
            v102 = v249;
            v103 = 3;
            if ( v249 < 3 )
              v103 = v249;
            v104 = v248;
            v105 = (_QWORD *)v248[0];
            v106 = v250;
            if ( v250 > 0xF )
              v104 = (_QWORD *)v248[0];
            if ( !(unsigned int)std::_Traits_compare<std::char_traits<char>>(v104, v103, "'''", 3) )
              goto LABEL_239;
            v107 = v248;
            if ( v106 > 0xF )
              v107 = v105;
            if ( !(unsigned int)std::_Traits_compare<std::char_traits<char>>(v107, v103, "\"\"\"", 3) )
            {
LABEL_239:
              v119 = (char *)v248;
              if ( v106 > 0xF )
                v119 = (char *)v105;
              *(_OWORD *)v242 = 0;
              v243 = 0u;
              if ( v13 < v99 )
                std::_String_val<std::_Simple_types<char>>::_Xran();
              v120 = *v119;
              v121 = v13 - v99;
              v122 = -1;
              if ( v121 != -1 )
                v122 = v121;
              v123 = Src;
              if ( v262 > 0xF )
                v123 = (void **)Src[0];
              std::string::_Construct<1,char const *>(v242, (char *)v123 + v99, v122);
              v228 |= 0x80u;
              std::string::operator=(v248, v242);
              if ( v243.m128i_i64[1] > 0xFuLL )
                std::string::_Deallocate_for_capacity(v242, v242[0]);
              CLI::detail::ltrim(v248);
              std::string::erase(v248, 0, 3);
              v125 = 1;
              v126 = 0;
              v127 = 1;
              if ( v249 && *(_BYTE *)std::string::back(v248) == 92 )
              {
                std::string::pop_back(v248);
                v126 = 1;
              }
              while ( v125 )
              {
                v253 = 0;
                v254 = 0;
                v255 = 15;
                LOBYTE(v253) = 0;
                LOBYTE(v124) = 10;
                v128 = std::ios::widen(a3 + *(int *)(*(_QWORD *)a3 + 4LL), v124);
                v129 = std::getline<char,std::char_traits<char>,std::allocator<char>>(a3, &v253, v128);
                if ( (unsigned __int8)std::ios_base::operator!(v129 + *(int *)(*(_QWORD *)v129 + 4LL)) )
                {
                  std::string::_Tidy_deallocate(&v253);
                  break;
                }
                v130 = &v253;
                if ( v255 > 0xF )
                  v130 = (__int128 *)v253;
                std::string::_Assign<char>(v244, v130, v254);
                CLI::detail::rtrim(v244);
                if ( v245.m128i_i64[0] < 3uLL )
                  goto LABEL_289;
                v132 = v244;
                if ( v245.m128i_i64[1] > 0xFuLL )
                  v132 = (void **)v244[0];
                if ( *((_BYTE *)v132 + v245.m128i_i64[0] - 1) == v120
                  && *((_BYTE *)v132 + v245.m128i_i64[0] - 2) == v120
                  && *((_BYTE *)v132 + v245.m128i_i64[0] - 3) == v120 )
                {
                  v133 = --v245.m128i_i64[0];
                  v134 = v244;
                  if ( v245.m128i_i64[1] > 0xFuLL )
                    v134 = (void **)v244[0];
                  *((_BYTE *)v134 + v133) = 0;
                  v135 = --v245.m128i_i64[0];
                  v136 = v244;
                  if ( v245.m128i_i64[1] > 0xFuLL )
                    v136 = (void **)v244[0];
                  *((_BYTE *)v136 + v135) = 0;
                  v137 = --v245.m128i_i64[0];
                  v138 = v244;
                  if ( v245.m128i_i64[1] > 0xFuLL )
                    v138 = (void **)v244[0];
                  *((_BYTE *)v138 + v137) = 0;
                  if ( v126 )
                  {
                    CLI::detail::ltrim(v244);
                  }
                  else
                  {
                    v139 = v249;
                    if ( !v127 || v249 )
                    {
                      if ( v249 >= v250 )
                      {
                        LOBYTE(v131) = 10;
                        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(
                          v248,
                          1,
                          0,
                          v131);
                      }
                      else
                      {
                        ++v249;
                        v140 = v248;
                        if ( v250 > 0xF )
                          v140 = (_QWORD *)v248[0];
                        *(_WORD *)((char *)v140 + v139) = 10;
                      }
                    }
                  }
                  std::string::_Append<char>(v248);
                  v125 = 0;
                  if ( v249 )
                  {
                    v141 = v248;
                    if ( v250 > 0xF )
                      v141 = (_QWORD *)v248[0];
                    if ( *((_BYTE *)v141 + v249 - 1) == 10 )
                    {
                      v142 = --v249;
                      v143 = v248;
                      if ( v250 > 0xF )
                        v143 = (_QWORD *)v248[0];
                      *((_BYTE *)v143 + v142) = 0;
                    }
                  }
                  if ( v120 == 34 )
                  {
                    try
                    {
                      v144 = CLI::detail::remove_escaped_characters(v256, v248);
                      std::string::operator=(v248, v144);
                      std::string::_Tidy_deallocate(v256);
                    }
                    catch ( const std::invalid_argument *v241 )
                    {
                      v218 = (*(__int64 (__fastcall **)(const std::invalid_argument *))(*(_QWORD *)v241[0] + 8LL))(v241[0]);
                      v219 = std::string::string(v256, v218);
                      CLI::ParseError::ParseError(v268, v219, 111);
                      throw (CLI::ParseError *)v268;
                    }
                  }
                }
                else
                {
LABEL_289:
                  if ( v126 )
                  {
                    v145 = CLI::detail::rtrim(&v253);
                    CLI::detail::ltrim(v145);
                  }
                  else
                  {
                    v146 = v249;
                    if ( !v127 || v249 )
                    {
                      if ( v249 >= v250 )
                      {
                        LOBYTE(v131) = 10;
                        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(
                          v248,
                          1,
                          0,
                          v131);
                      }
                      else
                      {
                        ++v249;
                        v147 = v248;
                        if ( v250 > 0xF )
                          v147 = (_QWORD *)v248[0];
                        *(_WORD *)((char *)v147 + v146) = 10;
                      }
                    }
                  }
                  v126 = 0;
                  if ( v254 )
                  {
                    v148 = &v253;
                    if ( v255 > 0xF )
                      v148 = (__int128 *)v253;
                    if ( *((_BYTE *)v148 + v254 - 1) == 92 )
                    {
                      v126 = 1;
                      v149 = --v254;
                      v150 = &v253;
                      if ( v255 > 0xF )
                        v150 = (__int128 *)v253;
                      *((_BYTE *)v150 + v149) = 0;
                    }
                  }
                  std::string::_Append<char>(v248);
                }
                v124 = v255;
                if ( v255 > 0xF )
                {
                  v151 = v255 + 1;
                  v152 = (void *)v253;
                  if ( v255 + 1 >= 0x1000 )
                  {
                    if ( (unsigned __int64)(v253 - *(_QWORD *)(v253 - 8) - 8) > 0x1F )
                      __fastfail(5u);
                    v151 = v255 + 40;
                    v152 = *(void **)(v253 - 8);
                  }
                  operator delete(v152, v151);
                }
                v127 = 0;
              }
              std::string::string(&v263, v248);
              std::vector<std::string>::_Assign_counted_range<std::string const *>(v230, &v263, 1);
              v118 = (void **)&v263;
              goto LABEL_255;
            }
            if ( v93 != -1 )
            {
              v108 = std::string::string(&v263, v248);
              CLI::detail::split_up(v242, v108, (unsigned __int8)v237[32]);
              v109 = CLI::detail::trim_copy(v256, v242[0]);
              std::string::operator=(v248, v109);
              std::string::_Tidy_deallocate(v256);
              std::vector<std::string>::_Tidy(v242);
              v102 = v249;
            }
            if ( v102 > 1 && *(_BYTE *)std::string::front(v248) == v226 )
            {
              std::string::string(v242);
              while ( *(_BYTE *)std::string::back(v248) != v227 )
              {
                LOBYTE(v110) = 10;
                v111 = std::ios::widen(a3 + *(int *)(*(_QWORD *)a3 + 4LL), v110);
                v112 = std::getline<char,std::char_traits<char>,std::allocator<char>>(a3, v242, v111);
                if ( !(unsigned __int8)std::ios_base::operator bool(v112 + *(int *)(*(_QWORD *)v112 + 4LL)) )
                  break;
                CLI::detail::trim(v242);
                std::string::operator+=(v248, v242);
              }
              std::string::_Tidy_deallocate(v242);
              v113 = v248;
              if ( v250 > 0xF )
                v113 = (_QWORD *)v248[0];
              if ( *((_BYTE *)v113 + v249 - 1) == v227 )
                v114 = std::string::substr(v248, v256, 1, v249 - 2);
              else
                v114 = std::string::substr(v248, v256, 1, -1);
              v115 = v223;
            }
            else
            {
              if ( !v222 && !v225 )
                goto LABEL_238;
              if ( std::string::find_first_of(v248, v223, 0) == -1 )
              {
                if ( !v222 && !v225 || (LOBYTE(v116) = 32, std::string::find_first_of(v248, v116, 0) == -1) )
                {
LABEL_238:
                  std::string::string(v242, v248);
                  v239[0] = v242;
                  v239[1] = v244;
                  std::vector<std::string>::operator=(v230, v239);
                  v118 = v242;
LABEL_255:
                  `eh vector destructor iterator'(v118, 0x20u, 1u, std::string::_Tidy_deallocate);
                  goto LABEL_256;
                }
                v114 = std::string::string(v256, v248);
                v115 = 0;
              }
              else
              {
                v114 = std::string::string(v256, v248);
                v115 = v223;
              }
            }
            v117 = CLI::detail::split_up(v242, v114, v115);
            std::vector<std::string>::operator=(v230, v117);
            std::vector<std::string>::_Tidy(v242);
LABEL_256:
            std::string::_Tidy_deallocate(v248);
            v5 = v237;
LABEL_322:
            *(_OWORD *)v235 = 0;
            v236 = 0;
            try
            {
              v155 = CLI::detail::generate_parents(v242, Buf1, v246, (unsigned __int8)v5[40]);
              std::vector<std::string>::operator=(v235, v155);
              std::vector<std::string>::_Tidy(v242);
              LOBYTE(v156) = 39;
              LOBYTE(v157) = 34;
              CLI::detail::process_quoted_string(v246, v157, v156);
              v159 = (char *)v230[0];
              v158 = (char *)v230[1];
              while ( v159 != v158 )
              {
                CLI::detail::process_quoted_string(v159, (unsigned __int8)v5[37], (unsigned __int8)v5[38]);
                v159 += 32;
              }
            }
            catch ( const std::invalid_argument *v240 )
            {
              v220 = (*(__int64 (__fastcall **)(const std::invalid_argument *))(*(_QWORD *)v240 + 8LL))(v240);
              v221 = std::string::string(v256, v220);
              CLI::ParseError::ParseError(v269, v221, 111);
              throw (CLI::ParseError *)v269;
            }
            v160 = (char *)v235[1];
            v161 = (char *)v235[0];
            if ( ((char *)v235[1] - (char *)v235[0]) >> 5 <= (unsigned __int64)(unsigned __int8)v5[39] )
            {
              if ( !*((_QWORD *)v5 + 8) || v224 )
                goto LABEL_348;
              if ( v235[0] == v235[1] || (unsigned __int8)std::operator!=<char>(v235[0], v5 + 48) )
              {
                if ( v161 )
                {
                  for ( i = v161; i != v160; i += 32 )
                    std::string::_Tidy_deallocate(i);
                  std::allocator<std::string>::deallocate(v235, v161, (v236 - (__int64)v161) >> 5);
                }
                v9 = v247[1];
                if ( v247[1] > 0xF )
                {
                  v171 = v247[1] + 1;
                  v172 = v246[0];
                  if ( v247[1] + 1 >= 0x1000 )
                  {
                    if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
                      goto LABEL_418;
                    v171 = v247[1] + 40;
                    v172 = (void *)*((_QWORD *)v246[0] - 1);
                  }
                  operator delete(v172, v171);
                }
                v247[0] = 0;
                v247[1] = 15;
                LOBYTE(v246[0]) = 0;
                v173 = (char *)v230[0];
                v4 = v234;
                v3 = a3;
                v6 = v228;
                if ( v230[0] )
                {
                  v174 = (char *)v230[1];
                  if ( v230[0] != v230[1] )
                  {
                    do
                    {
                      std::string::_Tidy_deallocate(v173);
                      v173 += 32;
                    }
                    while ( v173 != v174 );
                  }
                  std::allocator<std::string>::deallocate(
                    v230,
                    v230[0],
                    (signed __int64)(v231 - (unsigned __int64)v230[0]) >> 5);
                  v4 = v234;
                  v3 = a3;
                  v6 = v228;
                }
              }
              else if ( *((__int16 *)v5 + 21) < 0 || v233 == *((__int16 *)v5 + 21) )
              {
                std::vector<std::string>::erase(v235, &v238, v161);
                v224 = 1;
                v160 = (char *)v235[1];
                v161 = (char *)v235[0];
LABEL_348:
                v4 = v234;
                v168 = v234[1];
                if ( *v234 == v168 )
                  goto LABEL_375;
                if ( *(_QWORD *)(v168 - 32) <= 0xFu )
                  v169 = (const void *)(v168 - 56);
                else
                  v169 = *(const void **)(v168 - 56);
                v175 = v246;
                if ( v247[1] > 0xF )
                  v175 = (void **)v246[0];
                if ( v247[0] != *(_QWORD *)(v168 - 40) || v247[0] && memcmp_0(v175, v169, v247[0]) )
                  goto LABEL_375;
                v176 = *(_QWORD *)(v168 - 80);
                if ( (((v160 - v161) ^ (*(_QWORD *)(v168 - 72) - v176)) & 0xFFFFFFFFFFFFFFE0uLL) != 0 )
                  goto LABEL_375;
                if ( v161 != v160 )
                {
                  while ( (unsigned __int8)std::operator==<char>(v161, v176) )
                  {
                    v161 += 32;
                    v176 += 32;
                    if ( v161 == v160 )
                      goto LABEL_374;
                  }
LABEL_375:
                  if ( v168 == v4[2] )
                  {
                    std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(v4);
                  }
                  else
                  {
                    *(_QWORD *)v168 = 0;
                    *(_QWORD *)(v168 + 8) = 0;
                    *(_QWORD *)(v168 + 16) = 0;
                    *(_OWORD *)(v168 + 24) = 0;
                    *(_QWORD *)(v168 + 40) = 0;
                    *(_QWORD *)(v168 + 48) = 15;
                    *(_BYTE *)(v168 + 24) = 0;
                    *(_QWORD *)(v168 + 56) = 0;
                    *(_QWORD *)(v168 + 64) = 0;
                    *(_QWORD *)(v168 + 72) = 0;
                    v4[1] += 80LL;
                  }
                  std::vector<std::string>::operator=(v4[1] - 80LL, v235);
                  std::string::operator=(v4[1] - 56LL, v246);
                  std::vector<std::string>::operator=(v4[1] - 24LL, v230);
                  goto LABEL_379;
                }
LABEL_374:
                std::vector<std::string>::_Insert_counted_range<std::string *>(
                  v168 - 24,
                  *(_QWORD *)(v168 - 24 + 8),
                  v230[0],
                  ((char *)v230[1] - (char *)v230[0]) >> 5);
LABEL_379:
                std::vector<std::string>::_Tidy(v235);
                v9 = v247[1];
                if ( v247[1] > 0xF )
                {
                  v177 = v247[1] + 1;
                  v178 = v246[0];
                  if ( v247[1] + 1 >= 0x1000 )
                  {
                    if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
                      goto LABEL_418;
                    v177 = v247[1] + 40;
                    v178 = (void *)*((_QWORD *)v246[0] - 1);
                  }
                  operator delete(v178, v177);
                }
                v247[0] = 0;
                v247[1] = 15;
                LOBYTE(v246[0]) = 0;
                v31 = (void **)v230[0];
                v3 = a3;
                v6 = v228;
                if ( v230[0] )
                {
                  v179 = (void **)v230[1];
                  if ( v230[0] == v230[1] )
                    goto LABEL_59;
                  do
                  {
                    std::string::_Tidy_deallocate(v31);
                    v31 += 4;
                  }
                  while ( v31 != v179 );
                  goto LABEL_58;
                }
              }
              else
              {
                std::vector<std::string>::_Tidy(v235);
                std::string::_Tidy_deallocate(v246);
                std::vector<std::string>::_Tidy(v230);
                v4 = v234;
                v3 = a3;
                v6 = v228;
              }
            }
            else
            {
              std::vector<std::string>::_Tidy(v235);
              v9 = v247[1];
              if ( v247[1] > 0xF )
              {
                v162 = v247[1] + 1;
                v163 = v246[0];
                if ( v247[1] + 1 >= 0x1000 )
                {
                  if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
                    goto LABEL_418;
                  v162 = v247[1] + 40;
                  v163 = (void *)*((_QWORD *)v246[0] - 1);
                }
                operator delete(v163, v162);
              }
              v247[0] = 0;
              v247[1] = 15;
              LOBYTE(v246[0]) = 0;
              v164 = (char *)v230[0];
              v4 = v234;
              v3 = a3;
              v6 = v228;
              if ( v230[0] )
              {
                v165 = (char *)v230[1];
                if ( v230[0] != v230[1] )
                {
                  do
                  {
                    std::string::_Tidy_deallocate(v164);
                    v164 += 32;
                  }
                  while ( v164 != v165 );
                  v164 = (char *)v230[0];
                }
                v166 = (v231 - (_QWORD)v164) & 0xFFFFFFFFFFFFFFE0uLL;
                if ( v166 < 0x1000 )
                {
                  v167 = v164;
                }
                else
                {
                  v167 = (_BYTE *)*((_QWORD *)v164 - 1);
                  if ( (unsigned __int64)(v164 - v167 - 8) > 0x1F )
                    goto LABEL_449;
                  v166 += 39LL;
                }
                operator delete(v167, v166);
                v4 = v234;
                v3 = a3;
                v6 = v228;
              }
            }
          }
        }
      }
      else
      {
LABEL_397:
        v183 = v244;
        if ( v41 > 0xF )
          v183 = (void **)v263;
        v184 = *(_BYTE *)v183;
        v3 = a3;
        while ( 1 )
        {
          LOBYTE(v24) = 10;
          v185 = std::ios::widen(a3 + *(int *)(*(_QWORD *)a3 + 4LL), v24);
          v186 = std::getline<char,std::char_traits<char>,std::allocator<char>>(a3, v244, v185);
          if ( !(unsigned __int8)std::ios_base::operator bool(v186 + *(int *)(*(_QWORD *)v186 + 4LL)) )
            break;
          v187 = CLI::detail::rtrim(v244);
          CLI::detail::ltrim(v187);
          if ( v245.m128i_i64[0] >= 3uLL )
          {
            v188 = v244;
            if ( v245.m128i_i64[1] > 0xFuLL )
              v188 = (void **)v244[0];
            if ( *((_BYTE *)v188 + v245.m128i_i64[0] - 1) == v184
              && *((_BYTE *)v188 + v245.m128i_i64[0] - 2) == v184
              && *((_BYTE *)v188 + v245.m128i_i64[0] - 3) == v184 )
            {
              break;
            }
          }
        }
        v9 = v247[1];
        if ( v247[1] > 0xF )
        {
          v189 = v247[1] + 1;
          v190 = v246[0];
          if ( v247[1] + 1 >= 0x1000 )
          {
            if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
LABEL_418:
              __fastfail(5u);
            v189 = v247[1] + 40;
            v190 = (void *)*((_QWORD *)v246[0] - 1);
          }
          operator delete(v190, v189);
        }
        v247[0] = 0;
        v247[1] = 15;
        LOBYTE(v246[0]) = 0;
        v31 = (void **)v230[0];
        v6 = v228;
        if ( v230[0] )
        {
          v191 = (void **)v230[1];
          if ( v230[0] == v230[1] )
            goto LABEL_59;
          do
          {
            v192 = (unsigned __int64)v31[3];
            if ( v192 > 0xF )
            {
              v193 = (char *)*v31;
              v194 = v192 + 1;
              if ( v194 < 0x1000 )
              {
                v195 = (char *)*v31;
              }
              else
              {
                v195 = (char *)*((_QWORD *)v193 - 1);
                if ( (unsigned __int64)(v193 - v195 - 8) > 0x1F )
                  goto LABEL_449;
                v194 += 39LL;
              }
              operator delete(v195, v194);
            }
            v31[2] = 0;
            v31[3] = (void *)15;
            *(_BYTE *)v31 = 0;
            v31 += 4;
          }
          while ( v31 != v191 );
          goto LABEL_58;
        }
      }
    }
    else
    {
      v9 = v247[1];
      if ( v247[1] > 0xF )
      {
        v29 = v247[1] + 1;
        v30 = v246[0];
        if ( v247[1] + 1 >= 0x1000 )
        {
          if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
            goto LABEL_418;
          v29 = v247[1] + 40;
          v30 = (void *)*((_QWORD *)v246[0] - 1);
        }
        operator delete(v30, v29);
      }
      v247[0] = 0;
      v247[1] = 15;
      LOBYTE(v246[0]) = 0;
      v31 = (void **)v230[0];
      v3 = a3;
      v6 = v228;
      if ( v230[0] )
      {
        v32 = (void **)v230[1];
        if ( v230[0] != v230[1] )
        {
          do
          {
            v33 = (unsigned __int64)v31[3];
            if ( v33 > 0xF )
            {
              v34 = (char *)*v31;
              v35 = v33 + 1;
              if ( v35 < 0x1000 )
              {
                v36 = *v31;
              }
              else
              {
                v36 = (_BYTE *)*((_QWORD *)v34 - 1);
                if ( (unsigned __int64)(v34 - v36 - 8) > 0x1F )
                  goto LABEL_449;
                v35 += 39LL;
              }
              operator delete(v36, v35);
            }
            v31[2] = 0;
            v31[3] = (void *)15;
            *(_BYTE *)v31 = 0;
            v31 += 4;
          }
          while ( v31 != v32 );
LABEL_58:
          v31 = (void **)v230[0];
        }
LABEL_59:
        v37 = (v231 - (_QWORD)v31) & 0xFFFFFFFFFFFFFFE0uLL;
        if ( v37 < 0x1000 )
        {
          operator delete(v31, v37);
          v3 = a3;
          v6 = v228;
        }
        else
        {
          v38 = *(v31 - 1);
          if ( (unsigned __int64)((char *)v31 - v38 - 8) > 0x1F )
            goto LABEL_449;
          operator delete(v38, v37 + 39);
          v3 = a3;
          v6 = v228;
        }
      }
    }
  }
  v196 = Buf1;
  if ( Size[1] > 0xF )
    v196 = (void **)Buf1[0];
  if ( Size[0] != 7 || memcmp_0(v196, "default", 7u) )
  {
    *(_OWORD *)v242 = 0;
    v243.m128i_i64[0] = 0;
    v243.m128i_i64[1] = 15;
    LOBYTE(v242[0]) = 0;
    v197 = v4[1];
    if ( v197 == v4[2] )
    {
      std::vector<CLI::ConfigItem>::_Emplace_reallocate<>(v4);
    }
    else
    {
      *(_QWORD *)v197 = 0;
      *(_QWORD *)(v197 + 8) = 0;
      *(_QWORD *)(v197 + 16) = 0;
      *(_OWORD *)(v197 + 24) = 0;
      *(_QWORD *)(v197 + 40) = 0;
      *(_QWORD *)(v197 + 48) = 15;
      *(_BYTE *)(v197 + 24) = 0;
      *(_QWORD *)(v197 + 56) = 0;
      *(_QWORD *)(v197 + 64) = 0;
      *(_QWORD *)(v197 + 72) = 0;
      v4[1] += 80LL;
    }
    v198 = CLI::detail::generate_parents(v235, Buf1, v242, (unsigned __int8)v5[40]);
    std::vector<std::string>::operator=(v4[1] - 80LL, v198);
    v199 = (char *)v235[0];
    if ( v235[0] )
    {
      v200 = (char *)v235[1];
      if ( v235[0] != v235[1] )
      {
        do
        {
          std::string::_Tidy_deallocate(v199);
          v199 += 32;
        }
        while ( v199 != v200 );
        v199 = (char *)v235[0];
      }
      v201 = (v236 - (_QWORD)v199) & 0xFFFFFFFFFFFFFFE0uLL;
      if ( v201 < 0x1000 )
      {
        v202 = v199;
      }
      else
      {
        v202 = (_BYTE *)*((_QWORD *)v199 - 1);
        if ( (unsigned __int64)(v199 - v202 - 8) > 0x1F )
          __fastfail(5u);
        v201 += 39LL;
      }
      operator delete(v202, v201);
    }
    std::string::_Assign<char>(v4[1] - 56LL, "--", 2);
    for ( j = v4[1]; (unsigned __int64)((__int64)(*(_QWORD *)(j - 72) - *(_QWORD *)(j - 80)) >> 5) > 1; j = v4[1] )
    {
      if ( j == v4[2] )
      {
        std::vector<CLI::ConfigItem>::_Emplace_reallocate<CLI::ConfigItem const &>(v4, j, j - 80);
      }
      else
      {
        v238 = j;
        std::vector<std::string>::vector<std::string>(j, j - 80);
        std::string::string(j + 24, j - 56);
        std::vector<std::string>::vector<std::string>(j + 56, j - 24);
        v4[1] += 80LL;
      }
      v204 = v4[1];
      std::string::_Tidy_deallocate((void *)(*(_QWORD *)(v204 - 72) - 32LL));
      *(_QWORD *)(v204 - 72) -= 32LL;
    }
    if ( v243.m128i_i64[1] > 0xFuLL )
    {
      v205 = v243.m128i_i64[1] + 1;
      if ( (unsigned __int64)(v243.m128i_i64[1] + 1) < 0x1000 )
      {
        v206 = v242[0];
      }
      else
      {
        v206 = (void *)*((_QWORD *)v242[0] - 1);
        if ( (unsigned __int64)((char *)v242[0] - (char *)v206 - 8) > 0x1F )
LABEL_449:
          __fastfail(5u);
        v205 = v243.m128i_i64[1] + 40;
      }
      operator delete(v206, v205);
    }
  }
  if ( v267 > 0xF )
  {
    v207 = v267 + 1;
    if ( v267 + 1 < 0x1000 )
    {
      v208 = v265[0];
    }
    else
    {
      v208 = (void *)*((_QWORD *)v265[0] - 1);
      if ( (unsigned __int64)((char *)v265[0] - (char *)v208 - 8) > 0x1F )
        __fastfail(5u);
      v207 = v267 + 40;
    }
    operator delete(v208, v207);
  }
  if ( v259 > 0xF )
  {
    v209 = v259 + 1;
    if ( v259 + 1 < 0x1000 )
    {
      v210 = Buf2[0];
    }
    else
    {
      v210 = (void *)*((_QWORD *)Buf2[0] - 1);
      if ( (unsigned __int64)((char *)Buf2[0] - (char *)v210 - 8) > 0x1F )
        __fastfail(5u);
      v209 = v259 + 40;
    }
    operator delete(v210, v209);
  }
  if ( Size[1] > 0xF )
  {
    v211 = Size[1] + 1;
    if ( Size[1] + 1 < 0x1000 )
    {
      v212 = Buf1[0];
    }
    else
    {
      v212 = (void *)*((_QWORD *)Buf1[0] - 1);
      if ( (unsigned __int64)((char *)Buf1[0] - (char *)v212 - 8) > 0x1F )
        __fastfail(5u);
      v211 = Size[1] + 40;
    }
    operator delete(v212, v211);
  }
  Size[0] = 0;
  Size[1] = 15;
  LOBYTE(Buf1[0]) = 0;
  if ( v262 > 0xF )
  {
    v213 = v262 + 1;
    if ( v262 + 1 < 0x1000 )
    {
      v214 = Src[0];
    }
    else
    {
      v214 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v214 - 8) > 0x1F )
        __fastfail(5u);
      v213 = v262 + 40;
    }
    operator delete(v214, v213);
  }
  if ( v245.m128i_i64[1] > 0xFuLL )
  {
    v215 = v245.m128i_i64[1] + 1;
    if ( (unsigned __int64)(v245.m128i_i64[1] + 1) < 0x1000 )
    {
      v216 = v244[0];
    }
    else
    {
      v216 = (void *)*((_QWORD *)v244[0] - 1);
      if ( (unsigned __int64)((char *)v244[0] - (char *)v216 - 8) > 0x1F )
        __fastfail(5u);
      v215 = v245.m128i_i64[1] + 40;
    }
    operator delete(v216, v215);
  }
  return v4;
}

```

## disassembly

```asm
0x14002df60  mov     r11, rsp
0x14002df63  push    rbx
0x14002df64  push    rsi
0x14002df65  push    rdi
0x14002df66  push    r12
0x14002df68  push    r13
0x14002df6a  push    r14
0x14002df6c  push    r15
0x14002df6e  sub     rsp, 2D0h
0x14002df75  mov     rax, cs:__security_cookie
0x14002df7c  xor     rax, rsp
0x14002df7f  mov     [rsp+308h+var_48], rax
0x14002df87  mov     rdi, r8
0x14002df8a  mov     [rsp+308h+var_2C0], r8
0x14002df8f  mov     r12, rdx
0x14002df92  mov     [rsp+308h+var_290], rdx
0x14002df97  mov     r15, rcx
0x14002df9a  mov     [rsp+308h+var_268], rcx
0x14002dfa2  mov     [r11-238h], rdx
0x14002dfa9  xor     r8d, r8d
0x14002dfac  mov     [rsp+308h+var_2C8], r8d
0x14002dfb1  xorps   xmm0, xmm0
0x14002dfb4  movups  xmmword ptr [rsp+308h+var_210], xmm0
0x14002dfbc  mov     [r11-200h], r8
0x14002dfc3  mov     qword ptr [r11-1F8h], 0Fh
0x14002dfce  mov     [r11-210h], r8b
0x14002dfd5  movups  xmmword ptr [rsp+308h+Src], xmm0
0x14002dfdd  mov     [r11-120h], r8
0x14002dfe4  mov     qword ptr [r11-118h], 0Fh
0x14002dfef  mov     byte ptr [rsp+308h+Src], r8b
0x14002dff7  movups  xmmword ptr [rsp+308h+Buf1], xmm0
0x14002dfff  mov     qword ptr [r11-1A0h], 7
0x14002e00a  mov     qword ptr [r11-198h], 0Fh
0x14002e015  mov     rax, qword ptr cs:aDefault; "default"
0x14002e01c  mov     dword ptr [rsp+308h+Buf1], eax
0x14002e023  movzx   edx, word ptr cs:aDefault+4; "ult"
0x14002e02a  mov     word ptr [rsp+308h+Buf1+4], dx
0x14002e032  movzx   ecx, byte ptr cs:aDefault+6; "t"
0x14002e039  mov     byte ptr [rsp+308h+Buf1+6], cl
0x14002e040  mov     byte ptr [rsp+308h+Buf1+7], r8b
0x14002e048  movups  xmmword ptr [rsp+308h+Buf2], xmm0
0x14002e050  mov     qword ptr [r11-140h], 7
0x14002e05b  mov     esi, 0Fh
0x14002e060  mov     [r11-138h], rsi
0x14002e067  mov     dword ptr [rsp+308h+Buf2], eax
0x14002e06e  mov     word ptr [rsp+308h+Buf2+4], dx
0x14002e076  mov     byte ptr [rsp+308h+Buf2+6], cl
0x14002e07d  mov     byte ptr [rsp+308h+Buf2+7], r8b
0x14002e085  mov     [r12], r8
0x14002e089  mov     [r12+8], r8
0x14002e08e  mov     [r12+10h], r8
0x14002e093  mov     r14d, 1
0x14002e099  mov     [rsp+308h+var_2C8], r14d
0x14002e09e  movzx   edx, byte ptr [r15+21h]
0x14002e0a3  mov     [rsp+308h+var_2D4], dl
0x14002e0a7  cmp     dl, 5Bh ; '['
0x14002e0aa  jnz     loc_14002E208
0x14002e0b0  lea     rax, [r15+22h]
0x14002e0b4  cmp     byte ptr [rax], 5Dh ; ']'
0x14002e0b7  jnz     loc_14002E208
0x14002e0bd  cmp     byte ptr [r15+23h], 2Ch ; ','
0x14002e0c2  jnz     loc_14002E208
0x14002e0c8  mov     [rsp+308h+var_2D8], r14b
0x14002e0cd  xor     cl, cl
0x14002e0cf  mov     [rsp+308h+var_2D5], cl
0x14002e0d3  xor     r13b, r13b
0x14002e0d6  mov     [rsp+308h+var_2D6], r13b
0x14002e0db  movzx   eax, byte ptr [rax]
0x14002e0de  mov     [rsp+308h+var_2D3], al
0x14002e0e2  movzx   eax, byte ptr [r15+23h]
0x14002e0e7  mov     [rsp+308h+var_2D7], al
0x14002e0eb  mov     [rsp+308h+var_2B8], r13b
0x14002e0f0  xor     r13d, r13d
0x14002e0f3  mov     [rsp+308h+var_294], r13d
0x14002e0f8  movzx   eax, byte ptr [r15+28h]
0x14002e0fd  mov     [rsp+308h+var_298], al
0x14002e101  movzx   eax, byte ptr [r15+20h]
0x14002e106  mov     [rsp+308h+var_297], al
0x14002e10a  movzx   eax, byte ptr [r15+24h]
0x14002e10f  mov     [rsp+308h+var_296], al
0x14002e113  movups  xmmword ptr [rsp+308h+var_F0], xmm0
0x14002e11b  mov     [rsp+308h+var_E0], r13
0x14002e123  mov     [rsp+308h+var_D8], r13
0x14002e12b  mov     r8d, 3
0x14002e131  lea     rdx, [rsp+308h+var_298]
0x14002e136  lea     rcx, [rsp+308h+var_F0]
0x14002e13e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14002e143  nop
0x14002e144  mov     rsi, 7FFFFFFFFFFFFFFFh
0x14002e14e  xchg    ax, ax
0x14002e150  mov     rax, [rdi]
0x14002e153  movsxd  rcx, dword ptr [rax+4]
0x14002e157  add     rcx, rdi
0x14002e15a  mov     dl, 0Ah
0x14002e15c  call    cs:__imp_?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x14002e162  movzx   r8d, al
0x14002e166  lea     rdx, [rsp+308h+Src]
0x14002e16e  mov     rcx, rdi
0x14002e171  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@$$QEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@D@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &&,std::string &,char)
0x14002e176  mov     rdx, rax
0x14002e179  mov     rax, [rax]
0x14002e17c  movsxd  rcx, dword ptr [rax+4]
0x14002e180  add     rcx, rdx
0x14002e183  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x14002e189  test    al, al
0x14002e18b  jz      loc_140030091
0x14002e191  xorps   xmm0, xmm0
0x14002e194  movdqu  xmmword ptr [rsp+308h+var_2B0], xmm0
0x14002e19a  mov     [rsp+308h+var_2A0], r13
0x14002e19f  movups  xmmword ptr [rsp+308h+var_1F0], xmm0
0x14002e1a7  mov     [rsp+308h+var_1E0], r13
0x14002e1af  mov     [rsp+308h+var_1E0+8], 0Fh
0x14002e1bb  mov     byte ptr [rsp+308h+var_1F0], 0
0x14002e1c3  movups  xmmword ptr [rsp+308h+var_230], xmm0
0x14002e1cb  mov     qword ptr [rsp+308h+var_220], r13
0x14002e1d3  mov     qword ptr [rsp+308h+var_220+8], r13
0x14002e1db  lea     rdi, [rsp+308h+Src]
0x14002e1e3  cmp     [rsp+308h+var_118], 0Fh
0x14002e1ec  cmova   rdi, [rsp+308h+Src]
0x14002e1f5  mov     r13, [rsp+308h+var_120]
0x14002e1fd  cmp     r13, rsi
0x14002e200  ja      loc_14003048E
0x14002e206  jmp     short loc_14002E259
0x14002e208  lea     rax, [r15+22h]
0x14002e20c  test    dl, dl
0x14002e20e  jz      short loc_14002E21F
0x14002e210  xor     cl, cl
0x14002e212  mov     [rsp+308h+var_2D8], cl
0x14002e216  cmp     dl, 20h ; ' '
0x14002e219  jnz     loc_14002E0CD
0x14002e21f  xor     cl, cl
0x14002e221  mov     [rsp+308h+var_2D8], cl
0x14002e225  cmp     dl, [rax]
0x14002e227  jnz     loc_14002E0CD
0x14002e22d  mov     [rsp+308h+var_2D5], r14b
0x14002e232  xor     r13b, r13b
0x14002e235  mov     [rsp+308h+var_2D6], r13b
0x14002e23a  mov     [rsp+308h+var_2D4], 5Bh ; '['
0x14002e23f  mov     [rsp+308h+var_2D3], 5Dh ; ']'
0x14002e244  cmp     byte ptr [r15+23h], 20h ; ' '
0x14002e249  jnz     loc_14002E0E2
0x14002e24f  mov     [rsp+308h+var_2D7], 2Ch ; ','
0x14002e254  jmp     loc_14002E0EB
0x14002e259  cmp     r13, 0Fh
0x14002e25d  ja      short loc_14002E283
0x14002e25f  mov     qword ptr [rsp+308h+var_220], r13
0x14002e267  mov     qword ptr [rsp+308h+var_220+8], 0Fh
0x14002e273  movups  xmm0, xmmword ptr [rdi]
0x14002e276  movups  xmmword ptr [rsp+308h+var_230], xmm0
0x14002e27e  jmp     loc_14002E321
0x14002e283  mov     rbx, r13
0x14002e286  or      rbx, 0Fh
0x14002e28a  cmp     rbx, rsi
0x14002e28d  jbe     short loc_14002E2BE
0x14002e28f  mov     rbx, rsi
0x14002e292  mov     rax, 8000000000000027h
0x14002e29c  mov     rcx, rax; Size
0x14002e29f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002e2a4  mov     rcx, rax
0x14002e2a7  test    rax, rax
0x14002e2aa  jz      loc_14002E8EE
0x14002e2b0  add     rax, 27h ; '''
0x14002e2b4  and     rax, 0FFFFFFFFFFFFFFE0h
0x14002e2b8  mov     [rax-8], rcx
0x14002e2bc  jmp     short loc_14002E2F9
0x14002e2be  cmp     rbx, 16h
0x14002e2c2  mov     eax, 16h
0x14002e2c7  cmovb   rbx, rax
0x14002e2cb  lea     rcx, [rbx+1]; Size
0x14002e2cf  test    rcx, rcx
0x14002e2d2  jnz     short loc_14002E2DC
0x14002e2d4  xor     r8d, r8d
0x14002e2d7  mov     eax, r8d
0x14002e2da  jmp     short loc_14002E2F9
0x14002e2dc  cmp     rcx, 1000h
0x14002e2e3  jb      short loc_14002E2F4
0x14002e2e5  lea     rax, [rcx+27h]
0x14002e2e9  cmp     rax, rcx
0x14002e2ec  jbe     loc_140030494
0x14002e2f2  jmp     short loc_14002E29C
0x14002e2f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002e2f9  mov     [rsp+308h+var_230], rax
0x14002e301  mov     qword ptr [rsp+308h+var_220], r13
0x14002e309  mov     qword ptr [rsp+308h+var_220+8], rbx
0x14002e311  lea     r8, [r13+1]; Size
0x14002e315  mov     rdx, rdi; Src
0x14002e318  mov     rcx, rax; void *
0x14002e31b  call    memcpy_0
0x14002e320  nop
0x14002e321  lea     rcx, [rsp+308h+var_230]
0x14002e329  call    ?rtrim@detail@CLI@@YAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV34@@Z; CLI::detail::rtrim(std::string &)
0x14002e32e  mov     rcx, rax
0x14002e331  call    ?ltrim@detail@CLI@@YAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV34@@Z; CLI::detail::ltrim(std::string &)
0x14002e336  mov     rdx, rax
0x14002e339  lea     rcx, [rsp+308h+var_110]
0x14002e341  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x14002e346  or      r14d, 2
0x14002e34a  mov     [rsp+308h+var_2D0], r14d
0x14002e34f  mov     [rsp+308h+var_2C8], r14d
0x14002e354  mov     rdx, qword ptr [rsp+308h+var_220+8]
0x14002e35c  cmp     rdx, 0Fh
0x14002e360  jbe     short loc_14002E397
0x14002e362  inc     rdx
0x14002e365  mov     rcx, [rsp+308h+var_230]
0x14002e36d  cmp     rdx, 1000h
0x14002e374  jb      short loc_14002E392
0x14002e376  mov     rax, [rcx-8]
0x14002e37a  sub     rcx, rax
0x14002e37d  sub     rcx, 8
0x14002e381  cmp     rcx, 1Fh
0x14002e385  ja      loc_14002E8EE
0x14002e38b  add     rdx, 27h ; '''; unsigned __int64
0x14002e38f  mov     rcx, rax; void *
0x14002e392  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002e397  mov     rdx, [rsp+308h+var_1F8]
0x14002e39f  cmp     rdx, 0Fh
0x14002e3a3  jbe     short loc_14002E3DA
0x14002e3a5  inc     rdx
0x14002e3a8  mov     rcx, [rsp+308h+var_210]
0x14002e3b0  cmp     rdx, 1000h
0x14002e3b7  jb      short loc_14002E3D5
0x14002e3b9  mov     rax, [rcx-8]
0x14002e3bd  sub     rcx, rax
0x14002e3c0  sub     rcx, 8
0x14002e3c4  cmp     rcx, 1Fh
0x14002e3c8  ja      loc_14002E8EE
0x14002e3ce  add     rdx, 27h ; '''; unsigned __int64
0x14002e3d2  mov     rcx, rax; void *
0x14002e3d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002e3da  movups  xmm1, [rsp+308h+var_110]
0x14002e3e2  movups  xmmword ptr [rsp+308h+var_210], xmm1
0x14002e3ea  movups  xmm0, [rsp+308h+var_100]
0x14002e3f2  movups  xmmword ptr [rsp+108h], xmm0
0x14002e3fa  movq    r14, xmm0
0x14002e3ff  mov     rbx, r14
0x14002e402  cmp     r14, 3
0x14002e406  jnb     loc_14002E542
0x14002e40c  mov     rdx, [rsp+308h+var_1E0+8]
0x14002e414  cmp     rdx, 0Fh
0x14002e418  jbe     short loc_14002E44F
0x14002e41a  inc     rdx
0x14002e41d  mov     rcx, [rsp+308h+var_1F0]
0x14002e425  cmp     rdx, 1000h
0x14002e42c  jb      short loc_14002E44A
0x14002e42e  mov     rax, [rcx-8]
0x14002e432  sub     rcx, rax
0x14002e435  sub     rcx, 8
0x14002e439  cmp     rcx, 1Fh
0x14002e43d  ja      loc_140030065
0x14002e443  add     rdx, 27h ; '''; unsigned __int64
0x14002e447  mov     rcx, rax; void *
0x14002e44a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002e44f  xor     r13d, r13d
0x14002e452  mov     [rsp+308h+var_1E0], r13
0x14002e45a  mov     [rsp+308h+var_1E0+8], 0Fh
0x14002e466  mov     byte ptr [rsp+308h+var_1F0], r13b
0x14002e46e  mov     rbx, [rsp+308h+var_2B0]
0x14002e473  test    rbx, rbx
0x14002e476  mov     rdi, [rsp+308h+var_2C0]
0x14002e47b  mov     r14d, [rsp+308h+var_2D0]
0x14002e480  jz      loc_14002E150
0x14002e486  mov     rdi, [rsp+308h+var_2B0+8]
0x14002e48b  cmp     rbx, rdi
0x14002e48e  jz      short loc_14002E4E9
0x14002e490  mov     rdx, [rbx+18h]
0x14002e494  cmp     rdx, 0Fh
0x14002e498  jbe     short loc_14002E4CC
0x14002e49a  mov     rax, [rbx]
0x14002e49d  inc     rdx; unsigned __int64
0x14002e4a0  cmp     rdx, 1000h
0x14002e4a7  jb      short loc_14002E4C4
0x14002e4a9  mov     rcx, [rax-8]
0x14002e4ad  sub     rax, rcx
0x14002e4b0  sub     rax, 8
0x14002e4b4  cmp     rax, 1Fh
0x14002e4b8  ja      loc_1400302CB
0x14002e4be  add     rdx, 27h ; '''
0x14002e4c2  jmp     short loc_14002E4C7
0x14002e4c4  mov     rcx, rax; void *
0x14002e4c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002e4cc  mov     [rbx+10h], r13
0x14002e4d0  mov     qword ptr [rbx+18h], 0Fh
0x14002e4d8  mov     byte ptr [rbx], 0
0x14002e4db  add     rbx, 20h ; ' '
0x14002e4df  cmp     rbx, rdi
0x14002e4e2  jnz     short loc_14002E490
0x14002e4e4  mov     rbx, [rsp+308h+var_2B0]
0x14002e4e9  mov     rdx, [rsp+308h+var_2A0]
0x14002e4ee  sub     rdx, rbx
0x14002e4f1  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x14002e4f5  cmp     rdx, 1000h
0x14002e4fc  jb      short loc_14002E52B
0x14002e4fe  mov     rcx, [rbx-8]; void *
0x14002e502  sub     rbx, rcx
0x14002e505  sub     rbx, 8
0x14002e509  cmp     rbx, 1Fh
0x14002e50d  ja      loc_1400302CB
0x14002e513  add     rdx, 27h ; '''; unsigned __int64
0x14002e517  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002e51c  mov     rdi, [rsp+308h+var_2C0]
  ... truncated ...
```
