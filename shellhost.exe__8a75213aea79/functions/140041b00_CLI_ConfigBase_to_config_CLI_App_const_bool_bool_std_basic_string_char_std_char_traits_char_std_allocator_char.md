# CLI::ConfigBase::to_config(CLI::App const *,bool,bool,std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x140041b00`
- end: `0x140043c31`
- name: `?to_config@ConfigBase@CLI@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBVApp@2@_N1V34@@Z`
- size: `8497`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400083f0`
- `0x140008614`
- `0x140008a50`
- `0x14000b0a0`
- `0x14000ba3c`
- `0x14000c50c`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010608`
- `0x140010614`
- `0x140010668`
- `0x140010ad0`
- `0x140013030`
- `0x14002b070`
- `0x14002b890`
- `0x14002c270`
- `0x14002d2b0`
- `0x140031810`
- `0x1400324d0`
- `0x140034640`
- `0x1400349d0`
- `0x140035730`
- `0x14003ce10`
- `0x140041b00`
- `0x140044d4c`
- `0x14004556c`
- `0x1400455d0`
- `0x140045aac`
- `0x14004a850`
- `0x14004a9e0`
- `0x14004aa1c`
- `0x14004aaac`
- `0x14004b384`
- `0x14004da28`
- `0x14004e1b4`
- `0x14005246c`
- `0x14005385c`
- `0x140067010`

## import_xrefs

- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140043b49`
- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140043b49`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140043b3b`
- `msvcp_win!??1?$basic_streambuf@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140043b3b`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140043b57`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140043b57`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall CLI::ConfigBase::to_config(_BYTE *a1, __int64 a2, __int64 a3, unsigned __int8 a4, char a5, void *a6)
{
  unsigned __int8 v8; // r9
  __int64 v9; // r9
  unsigned __int64 v10; // rcx
  void **v11; // rax
  __int64 v12; // r9
  unsigned __int64 v13; // rcx
  void **v14; // rax
  __int64 v15; // r9
  unsigned __int64 v16; // rcx
  void **v17; // rax
  __int64 v18; // r9
  unsigned __int64 v19; // rcx
  void **v20; // rax
  __int64 v21; // r9
  unsigned __int64 v22; // rcx
  void **v23; // rax
  __int64 v24; // r9
  unsigned __int64 v25; // rcx
  void **v26; // rax
  void *v27; // rbx
  _OWORD *v28; // r8
  char *v29; // rdx
  unsigned __int64 v30; // rdx
  _QWORD *fixed; // rbx
  void **v32; // rdx
  __int64 v33; // rax
  _QWORD *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rdx
  const void **v37; // r14
  const void *v38; // rcx
  unsigned __int64 v39; // rdi
  const void *v40; // rbx
  unsigned __int64 *v41; // rsi
  __int128 *v42; // r15
  const void *v43; // rcx
  __int64 v44; // rax
  void **v45; // rdx
  __int64 v46; // rax
  unsigned __int64 *v47; // rbx
  const void **v48; // rdx
  __int64 v49; // rax
  const void ***v50; // rax
  const void ***v51; // r15
  unsigned __int128 v52; // kr30_16
  const void **v53; // rdi
  unsigned __int64 v54; // r14
  const void *v55; // rcx
  __int64 v56; // rsi
  const void *v57; // rbx
  const void *v58; // rcx
  unsigned __int64 *v59; // rax
  __int128 *v60; // rsi
  unsigned __int64 v61; // rbx
  unsigned __int64 v62; // rax
  unsigned __int64 v63; // rdx
  void *v64; // rcx
  _BYTE *v65; // rdx
  int v66; // r14d
  bool v67; // bl
  __int64 v68; // rax
  __int64 v69; // r8
  const char *v70; // rdx
  __int64 v71; // rax
  __int64 flag_value; // rax
  _QWORD *v73; // rsi
  __int64 v74; // rax
  _QWORD *v75; // rbx
  void **v76; // rdx
  __int64 v77; // rax
  _QWORD *v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rcx
  _QWORD *v82; // r9
  __int128 *v83; // rax
  __int128 *p_Buf2; // rdx
  __int64 v85; // rax
  __int64 v86; // rax
  void **v87; // rdx
  __int64 v88; // rax
  __int64 v89; // rdx
  unsigned __int64 v90; // rdx
  void *v91; // rax
  __int64 v92; // rdx
  _BYTE *v93; // rdx
  __int64 v94; // r12
  __int64 v95; // r15
  char v96; // bl
  _QWORD *v97; // rsi
  _QWORD *v98; // rbx
  __int64 v99; // rax
  void **v100; // rdx
  __int64 v101; // rax
  __int64 v102; // rax
  _QWORD *v103; // rax
  _OWORD *v104; // r14
  size_t v105; // rdi
  unsigned __int64 v106; // rbx
  size_t v107; // rax
  size_t v108; // rcx
  void *v109; // rax
  void *v110; // rcx
  __int64 (__fastcall **v111)(char *, void **, __int128 *, _QWORD, _DWORD, void **); // rax
  _QWORD *v112; // rax
  _QWORD *v113; // rdx
  unsigned __int64 v114; // rdx
  void *v115; // rcx
  size_t v116; // rax
  char *v117; // rsi
  unsigned __int8 v118; // bl
  unsigned __int8 v119; // di
  char *v120; // rcx
  __int128 *v121; // rsi
  _QWORD *v122; // r15
  unsigned __int64 v123; // r14
  bool v124; // zf
  unsigned __int64 v125; // rsi
  size_t v126; // rcx
  _QWORD *v127; // rax
  void *v128; // rax
  void *v129; // rcx
  _QWORD *v130; // r15
  __int64 v131; // rax
  __int64 v132; // rdx
  _QWORD *v133; // r14
  unsigned __int128 *v134; // r14
  unsigned __int64 v135; // rsi
  unsigned __int64 v136; // rax
  unsigned __int128 *v137; // r9
  __int64 v138; // rax
  __int128 v139; // xmm6
  __int128 v140; // xmm7
  unsigned __int64 v141; // rdx
  void *v142; // rcx
  size_t v143; // rdx
  unsigned __int64 v144; // rdx
  void *v145; // rcx
  const void **v146; // rsi
  _OWORD *v147; // r15
  size_t v148; // r14
  unsigned __int64 v149; // rsi
  size_t v150; // rax
  size_t v151; // rcx
  void *v152; // rax
  void *v153; // rax
  void *v154; // rcx
  size_t v155; // r15
  void **v156; // r13
  size_t v157; // r12
  unsigned __int64 v158; // rsi
  size_t v159; // rax
  size_t v160; // rcx
  __int128 *v161; // r14
  void *v162; // rax
  __int64 v163; // rax
  __int128 v164; // xmm6
  __int128 v165; // xmm7
  unsigned __int64 v166; // rdx
  void *v167; // rcx
  unsigned __int64 v168; // rdx
  void *v169; // rcx
  unsigned __int64 v170; // rdx
  void *v171; // rcx
  __int64 v172; // rax
  __int128 *v173; // rdx
  __int64 v174; // rax
  unsigned __int64 v175; // rdx
  void *v176; // rcx
  __int64 (__fastcall **v177)(char *, void **, __int128 *, _QWORD, _DWORD, void **); // rax
  _QWORD *v178; // rax
  _QWORD *v179; // rdx
  __int64 v180; // rax
  _QWORD *v181; // rdx
  __int64 v182; // rax
  __int128 *v183; // rdx
  __int64 v184; // rax
  unsigned __int64 v185; // rdx
  void *v186; // rcx
  __int64 v187; // rcx
  _OWORD *v188; // r9
  __int128 *v189; // rax
  __int64 v190; // r9
  size_t v191; // rcx
  void **v192; // rax
  __int64 (__fastcall **v193)(char *, void **, __int128 *, _QWORD, _DWORD, void **); // rax
  _QWORD *v194; // rax
  _QWORD *v195; // rdx
  unsigned __int64 v196; // rdx
  void *v197; // rcx
  unsigned __int64 v198; // rdx
  void *v199; // rcx
  unsigned __int64 v200; // rdx
  void *v201; // rax
  char *v202; // rbx
  char *v203; // rdi
  unsigned __int64 v204; // rdx
  _BYTE *v205; // rcx
  unsigned __int64 v206; // rdx
  void *v207; // rcx
  unsigned __int64 v208; // rdx
  void *v209; // rcx
  unsigned __int64 v210; // rdx
  void *v211; // rcx
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // rax
  __int64 v216; // rax
  __int128 *v217; // rdx
  const void **v218; // rdi
  __int128 *v219; // rsi
  __int128 *v220; // rbx
  __int64 v221; // rax
  _BYTE v222[32]; // [rsp+0h] [rbp-4D8h] BYREF
  char v223[8]; // [rsp+20h] [rbp-4B8h]
  unsigned __int8 v224; // [rsp+40h] [rbp-498h]
  char v225; // [rsp+48h] [rbp-490h]
  unsigned __int8 v226[8]; // [rsp+50h] [rbp-488h] BYREF
  int v227; // [rsp+58h] [rbp-480h]
  char v228; // [rsp+5Ch] [rbp-47Ch]
  int v229; // [rsp+60h] [rbp-478h]
  const void ***v230; // [rsp+68h] [rbp-470h] BYREF
  const void **v231; // [rsp+70h] [rbp-468h]
  __int128 *v232; // [rsp+78h] [rbp-460h]
  const void **v233; // [rsp+80h] [rbp-458h]
  const void ***v234; // [rsp+88h] [rbp-450h]
  void *v235; // [rsp+90h] [rbp-448h]
  unsigned __int64 *v236; // [rsp+98h] [rbp-440h]
  unsigned __int64 v237; // [rsp+A0h] [rbp-438h] BYREF
  char *v238; // [rsp+A8h] [rbp-430h]
  char *v239; // [rsp+B0h] [rbp-428h]
  unsigned __int8 *v240; // [rsp+B8h] [rbp-420h]
  void *v241[2]; // [rsp+C0h] [rbp-418h] BYREF
  _BYTE *v242; // [rsp+D0h] [rbp-408h]
  _QWORD *v243; // [rsp+D8h] [rbp-400h]
  const void **v244; // [rsp+E0h] [rbp-3F8h]
  unsigned __int8 *v245; // [rsp+E8h] [rbp-3F0h]
  char *v246; // [rsp+F0h] [rbp-3E8h]
  char *v247; // [rsp+F8h] [rbp-3E0h]
  __int64 v248; // [rsp+100h] [rbp-3D8h]
  unsigned __int64 *v249; // [rsp+108h] [rbp-3D0h]
  __int128 v250; // [rsp+110h] [rbp-3C8h] BYREF
  __int64 v251; // [rsp+120h] [rbp-3B8h]
  __int128 *v252; // [rsp+128h] [rbp-3B0h]
  const void **v253; // [rsp+130h] [rbp-3A8h]
  _QWORD *v254; // [rsp+138h] [rbp-3A0h]
  char *v255; // [rsp+140h] [rbp-398h]
  _BYTE *v256; // [rsp+148h] [rbp-390h]
  _BYTE *v257; // [rsp+150h] [rbp-388h]
  int v258; // [rsp+15Ch] [rbp-37Ch]
  _QWORD v259[2]; // [rsp+160h] [rbp-378h] BYREF
  char v260[8]; // [rsp+170h] [rbp-368h] BYREF
  void **v261; // [rsp+178h] [rbp-360h] BYREF
  char v262[120]; // [rsp+180h] [rbp-358h] BYREF
  char v263[104]; // [rsp+1F8h] [rbp-2E0h] BYREF
  char v264[56]; // [rsp+260h] [rbp-278h] BYREF
  __int64 v265; // [rsp+298h] [rbp-240h]
  _QWORD *v266; // [rsp+2A0h] [rbp-238h]
  __int128 v267; // [rsp+2A8h] [rbp-230h] BYREF
  __int128 v268; // [rsp+2B8h] [rbp-220h]
  void *Src[2]; // [rsp+2C8h] [rbp-210h] BYREF
  size_t Size[2]; // [rsp+2D8h] [rbp-200h]
  void *v271[2]; // [rsp+2E8h] [rbp-1F0h] BYREF
  unsigned __int64 v272; // [rsp+2F8h] [rbp-1E0h]
  unsigned __int64 v273; // [rsp+300h] [rbp-1D8h]
  __int128 Buf2; // [rsp+308h] [rbp-1D0h] BYREF
  __int128 v275; // [rsp+318h] [rbp-1C0h]
  void *v276[2]; // [rsp+328h] [rbp-1B0h] BYREF
  __int64 v277; // [rsp+338h] [rbp-1A0h]
  unsigned __int64 v278; // [rsp+340h] [rbp-198h]
  unsigned __int128 v279; // [rsp+348h] [rbp-190h] BYREF
  unsigned __int64 v280; // [rsp+358h] [rbp-180h]
  unsigned __int64 v281; // [rsp+360h] [rbp-178h]
  __int128 v282; // [rsp+368h] [rbp-170h] BYREF
  unsigned __int64 v283; // [rsp+378h] [rbp-160h]
  unsigned __int64 v284; // [rsp+380h] [rbp-158h]
  void *v285[2]; // [rsp+388h] [rbp-150h] BYREF
  __int64 v286; // [rsp+398h] [rbp-140h]
  unsigned __int64 v287; // [rsp+3A0h] [rbp-138h]
  void **v288; // [rsp+3A8h] [rbp-130h] BYREF
  char v289; // [rsp+3B0h] [rbp-128h] BYREF
  int v290; // [rsp+3B1h] [rbp-127h]
  __int16 v291; // [rsp+3B5h] [rbp-123h]
  char v292; // [rsp+3B7h] [rbp-121h]
  __int64 v293; // [rsp+3B8h] [rbp-120h]
  __int64 v294; // [rsp+3C0h] [rbp-118h]
  __int64 v295; // [rsp+3C8h] [rbp-110h]
  _BYTE v296[32]; // [rsp+3D0h] [rbp-108h] BYREF
  _BYTE v297[56]; // [rsp+3F0h] [rbp-E8h] BYREF
  _BYTE *v298; // [rsp+428h] [rbp-B0h]
  _BYTE pExceptionObject[64]; // [rsp+430h] [rbp-A8h] BYREF

  v224 = a4;
  v243 = (_QWORD *)a3;
  v238 = a1;
  v239 = a1;
  v248 = a2;
  v254 = (_QWORD *)a3;
  v226 = a4;
  v225 = a5;
  v235 = a6;
  v266 = a6;
  v227 = 0;
  v229 = 0;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(
    v259,
    1);
  *(_OWORD *)v276 = 0;
  v278 = 15;
  LOBYTE(v276[0]) = a1[32];
  v277 = 2;
  *(_WORD *)((char *)v276 + 1) = 32;
  *(_OWORD *)v285 = 0;
  v287 = 15;
  LOWORD(v285[0]) = *(_WORD *)"#;";
  v286 = 3;
  WORD1(v285[0]) = LOBYTE(v276[0]);
  v245 = a1 + 40;
  v8 = a1[40];
  v286 = 4;
  *(_WORD *)((char *)v285 + 3) = v8;
  std::string::string(v271, v285);
  v246 = a1 + 38;
  v9 = (unsigned __int8)a1[38];
  v10 = v272;
  if ( v272 >= v273 )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v271, 1, 0, v9);
  }
  else
  {
    ++v272;
    v11 = v271;
    if ( v273 > 0xF )
      v11 = (void **)v271[0];
    *((_BYTE *)v11 + v10) = v9;
    *((_BYTE *)v11 + v10 + 1) = 0;
  }
  v247 = a1 + 37;
  v12 = (unsigned __int8)a1[37];
  v13 = v272;
  if ( v272 >= v273 )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v271, 1, 0, v12);
  }
  else
  {
    ++v272;
    v14 = v271;
    if ( v273 > 0xF )
      v14 = (void **)v271[0];
    *((_BYTE *)v14 + v13) = v12;
    *((_BYTE *)v14 + v13 + 1) = 0;
  }
  v256 = a1 + 33;
  v15 = (unsigned __int8)a1[33];
  v16 = v272;
  if ( v272 >= v273 )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v271, 1, 0, v15);
  }
  else
  {
    ++v272;
    v17 = v271;
    if ( v273 > 0xF )
      v17 = (void **)v271[0];
    *((_BYTE *)v17 + v16) = v15;
    *((_BYTE *)v17 + v16 + 1) = 0;
  }
  v255 = a1 + 34;
  v18 = (unsigned __int8)a1[34];
  v19 = v272;
  if ( v272 >= v273 )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v271, 1, 0, v18);
  }
  else
  {
    ++v272;
    v20 = v271;
    if ( v273 > 0xF )
      v20 = (void **)v271[0];
    *((_BYTE *)v20 + v19) = v18;
    *((_BYTE *)v20 + v19 + 1) = 0;
  }
  v240 = a1 + 36;
  v21 = (unsigned __int8)a1[36];
  v22 = v272;
  if ( v272 >= v273 )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v271, 1, 0, v21);
  }
  else
  {
    ++v272;
    v23 = v271;
    if ( v273 > 0xF )
      v23 = (void **)v271[0];
    *((_BYTE *)v23 + v22) = v21;
    *((_BYTE *)v23 + v22 + 1) = 0;
  }
  v257 = a1 + 35;
  v24 = (unsigned __int8)a1[35];
  v25 = v272;
  if ( v272 >= v273 )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v271, 1, 0, v24);
  }
  else
  {
    ++v272;
    v26 = v271;
    if ( v273 > 0xF )
      v26 = (void **)v271[0];
    *((_BYTE *)v26 + v25) = v24;
    *((_BYTE *)v26 + v25 + 1) = 0;
  }
  CLI::App::get_groups(a3, v241);
  v228 = 0;
  v27 = v241[0];
  HIWORD(v267) = 0;
  *(_QWORD *)&v268 = 7;
  *((_QWORD *)&v268 + 1) = 15;
  qmemcpy(&v267, "Option", 6);
  *(_QWORD *)((char *)&v267 + 6) = (unsigned __int8)aOptions[6];
  v28 = v241[1];
  if ( v241[1] == v242 )
  {
    std::vector<std::string>::_Emplace_reallocate<std::string>(v241, v241[0], &v267);
  }
  else if ( v241[0] == v241[1] )
  {
    *(_OWORD *)v241[1] = v267;
    v28[1] = v268;
    *(_QWORD *)&v268 = 0;
    *((_QWORD *)&v268 + 1) = 15;
    LOBYTE(v267) = 0;
    v241[1] = (char *)v241[1] + 32;
  }
  else
  {
    v288 = v241;
    v289 = v267;
    v290 = *(_DWORD *)((char *)&v267 + 1);
    v291 = *(_WORD *)((char *)&v267 + 5);
    v292 = 0;
    v293 = *((_QWORD *)&v267 + 1);
    v294 = 7;
    v295 = 15;
    *(_QWORD *)&v268 = 0;
    *((_QWORD *)&v268 + 1) = 15;
    LOBYTE(v267) = 0;
    v29 = (char *)v241[1] - 32;
    *(_OWORD *)v241[1] = *((_OWORD *)v241[1] - 2);
    v28[1] = *(v28 - 1);
    *((_QWORD *)v29 + 2) = 0;
    *((_QWORD *)v29 + 3) = 15;
    *v29 = 0;
    v241[1] = (char *)v241[1] + 32;
    std::_Move_backward_unchecked<std::string *,std::string *>(v27);
    std::string::operator=(v27, &v289);
    std::string::_Tidy_deallocate(&v289);
  }
  std::string::_Tidy_deallocate(&v267);
  if ( a5 && (*(_BYTE *)(a3 + 798) || !*(_QWORD *)(a3 + 840) || !*(_QWORD *)(a3 + 24)) )
  {
    std::string::string(&Buf2, a3 + 40);
    v227 = 2048;
    v229 = 2048;
    fixed = (_QWORD *)CLI::detail::fix_newlines(Src, v276, &Buf2);
    v32 = v276;
    if ( v278 > 0xF )
      v32 = (void **)v276[0];
    v33 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v260, v32, v277);
    if ( fixed[3] <= 0xFu )
      v34 = fixed;
    else
      v34 = (_QWORD *)*fixed;
    v35 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v33, v34, fixed[2]);
    LOBYTE(v36) = 10;
    std::operator<<<std::char_traits<char>>(v35, v36);
    std::string::_Tidy_deallocate(Src);
  }
  v37 = (const void **)v241[0];
  v253 = (const void **)v241[1];
  while ( 1 )
  {
    v231 = v37;
    if ( v37 == v253 )
      break;
    v38 = v37;
    v236 = (unsigned __int64 *)(v37 + 3);
    v39 = (unsigned __int64)v37[3];
    if ( v39 > 0xF )
      v38 = *v37;
    v232 = (__int128 *)(v37 + 2);
    v40 = v37[2];
    if ( v40 == (const void *)7 && !memcmp_0(v38, "Options", 7u) || !v40 )
    {
      if ( v228 )
        goto LABEL_150;
      v228 = 1;
    }
    v41 = (unsigned __int64 *)v37;
    v233 = v37;
    v249 = (unsigned __int64 *)(v37 + 3);
    v42 = v232;
    v252 = v232;
    if ( !v225 )
      goto LABEL_67;
    v43 = v37;
    if ( v39 > 0xF )
      v43 = *v37;
    if ( v40 == (const void *)7 && !memcmp_0(v43, "Options", 7u) || !v40 )
    {
LABEL_67:
      v47 = v236;
    }
    else
    {
      LOBYTE(v30) = 10;
      v44 = std::operator<<<std::char_traits<char>>(&v260, v30);
      v45 = v276;
      if ( v278 > 0xF )
        v45 = (void **)v276[0];
      v46 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v44, v45, v277);
      v47 = v236;
      if ( *v236 <= 0xF )
        v48 = v37;
      else
        v48 = (const void **)*v37;
      v49 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v46, v48, *(_QWORD *)v42);
      std::operator<<<std::char_traits<char>>(v49, " Options\n");
    }
    v265 = 0;
    CLI::App::get_options(v243, &v279, &v264);
    v50 = (const void ***)*((_QWORD *)&v279 + 1);
    v52 = v279;
    v234 = (const void ***)(v52 >> 64);
    v51 = (const void ***)v52;
    while ( 1 )
    {
      v230 = v51;
      if ( v51 == v50 )
        break;
      v53 = *v51;
      v244 = v53;
      if ( !*((_BYTE *)v53 + 35) )
        goto LABEL_106;
      v30 = (unsigned __int64)v41;
      v54 = *v47;
      if ( *v47 > 0xF )
        v30 = *v41;
      if ( (unsigned __int64)v53[3] <= 0xF )
        v55 = v53;
      else
        v55 = *v53;
      v56 = *(_QWORD *)v232;
      v57 = v53[2];
      if ( v57 == *(const void **)v232 && (!v57 || !memcmp_0(v55, (const void *)v30, (size_t)v53[2])) )
      {
LABEL_84:
        v59 = (unsigned __int64 *)v53[8];
        if ( v59 == v53[9] )
        {
          v59 = (unsigned __int64 *)v53[5];
          if ( v59 == v53[6] )
          {
            v59 = (unsigned __int64 *)(v53 + 17);
            if ( !v53[19] )
              v59 = (unsigned __int64 *)(v53 + 21);
          }
        }
        v282 = 0;
        v283 = 0;
        v284 = 0;
        if ( v59[3] <= 0xF )
          v60 = (__int128 *)v59;
        else
          v60 = (__int128 *)*v59;
        v61 = v59[2];
        if ( v61 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlen_string();
        if ( v61 > 0xF )
        {
          v62 = v61 | 0xF;
          if ( (v61 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
          {
            if ( v62 < 0x16 )
              v62 = 22;
          }
          else
          {
            v62 = 0x7FFFFFFFFFFFFFFFLL;
          }
          v237 = v62;
          *(_QWORD *)&v282 = std::string::_Allocate_for_capacity<0>(&v282, &v237);
          v283 = v61;
          v284 = v237;
          memcpy_0((void *)v282, v60, v61 + 1);
          v30 = v284;
          v61 = v283;
        }
        else
        {
          v283 = v59[2];
          v30 = 15;
          v284 = 15;
          v282 = *v60;
        }
        if ( !v61 )
          goto LABEL_100;
        CLI::Option::reduced_results((CLI::Option *)v53);
        CLI::detail::ini_join(Src, *v255, *v247, *v246);
        std::vector<std::string>::_Tidy(&v267);
        if ( !Size[0] )
        {
          if ( v224 )
          {
            std::string::string(&Buf2, v53 + 29);
            v66 = v227 | 0x400;
            v67 = (_QWORD)v275 != 0;
            std::string::_Tidy_deallocate(&Buf2);
            if ( v67 )
            {
              std::string::string(&Buf2, v53 + 29);
              v66 |= 0x1000u;
              v227 = v66;
              v229 = v66;
              v68 = CLI::detail::convert_arg_for_ini(v296, &Buf2, 0);
              std::string::operator=(Src, v68);
              std::string::_Tidy_deallocate(v296);
              std::string::_Tidy_deallocate(&Buf2);
              goto LABEL_116;
            }
            v227 = v66;
            v229 = v66;
            if ( !*((_DWORD *)v53 + 108) )
            {
              v69 = 5;
              v70 = "false";
              goto LABEL_115;
            }
            if ( *((_BYTE *)v53 + 619) )
            {
              v69 = 2;
              v70 = "\"\"";
LABEL_115:
              std::string::_Assign<char>(Src, v70, v69);
            }
LABEL_116:
            if ( Size[0] )
            {
LABEL_119:
              if ( v53[14] != v53[15] )
              {
                try
                {
                  v71 = std::string::string(v296, Src);
                  flag_value = CLI::Option::get_flag_value(v53, &v288, &v282, v71);
                  std::string::operator=(Src, flag_value);
                  std::string::_Tidy_deallocate(&v288);
                }
                catch ( CLI::ArgumentMismatch )
                {
                  v65 = v222;
                  v224 = 0;
                  v218 = v244;
                  v220 = (__int128 *)v244[14];
                  v219 = (__int128 *)v244[15];
                  v232 = v219;
                  while ( 1 )
                  {
                    v237 = (unsigned __int64)v220;
                    if ( v220 == v219 )
                      break;
                    try
                    {
                      v215 = std::string::string(&v288, Src);
                      v216 = CLI::Option::get_flag_value(v218, v296, v220, v215);
                      std::string::operator=(Src, v216);
                      std::string::_Tidy_deallocate(v296);
                      if ( &v282 != v220 )
                      {
                        v217 = v220;
                        if ( *((_QWORD *)v220 + 3) > 0xFu )
                          v217 = *(__int128 **)v220;
                        std::string::_Assign<char>(&v282, v217, *((_QWORD *)v220 + 2));
                      }
                      v224 = 1;
                    }
                    catch ( CLI::ArgumentMismatch )
                    {
                      v65 = v222;
                      v218 = v244;
                      v220 = (__int128 *)v237;
                      v219 = v232;
                    }
                    v220 += 2;
                  }
                  if ( !v224 )
                  {
                    v221 = CLI::detail::ini_join(&v288, v239[34], v239[37], v239[38]);
                    std::string::operator=(Src, v221);
                    std::string::_Tidy_deallocate(&v288);
                  }
                  v51 = v230;
                  v53 = v244;
                  v232 = v252;
                  v66 = v229;
                  v236 = v249;
                  v238 = v239;
                  v243 = v254;
                  v224 = v226;
                  v73 = v266;
                  v235 = v266;
                  goto LABEL_121;
                }
              }
              v73 = v235;
LABEL_121:
              if ( v225 && v53[27] )
              {
                LOBYTE(v65) = 10;
                std::operator<<<std::char_traits<char>>(&v260, v65);
                v74 = std::string::string(&v288, v53 + 25);
                v75 = (_QWORD *)CLI::detail::fix_newlines(v296, v276, v74);
                v76 = v276;
                if ( v278 > 0xF )
                  v76 = (void **)v276[0];
                v77 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v260, v76, v277);
                if ( v75[3] <= 0xFu )
                  v78 = v75;
                else
                  v78 = (_QWORD *)*v75;
                v79 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v77, v78, v75[2]);
                LOBYTE(v80) = 10;
                std::operator<<<std::char_traits<char>>(v79, v80);
                std::string::_Tidy_deallocate(v296);
              }
              CLI::clean_name_string(&v282);
              v81 = v73[2];
              if ( 0x7FFFFFFFFFFFFFFFLL - v81 < v283 )
                std::_Xlen_string();
              if ( v73[3] <= 0xFu )
                v82 = v73;
              else
                v82 = (_QWORD *)*v73;
              v83 = &v282;
              if ( v284 > 0xF )
                v83 = (__int128 *)v282;
              std::string::string(&Buf2, v226, v73, v82, v81, v83, v283);
              v227 = v66 | 0x200;
              v229 = v66 | 0x200;
              p_Buf2 = &Buf2;
              if ( *((_QWORD *)&v275 + 1) > 0xFu )
                p_Buf2 = (__int128 *)Buf2;
              v85 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v260, p_Buf2, v275);
              v86 = std::operator<<<std::char_traits<char>>(v85, *v240);
              v87 = Src;
              if ( Size[1] > 0xF )
                v87 = (void **)Src[0];
              v88 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v86, v87, Size[0]);
              LOBYTE(v89) = 10;
              std::operator<<<std::char_traits<char>>(v88, v89);
              std::string::_Tidy_deallocate(&Buf2);
            }
          }
          std::string::_Tidy_deallocate(Src);
          v30 = v284;
LABEL_100:
          if ( v30 > 0xF )
          {
            v63 = v30 + 1;
            v64 = (void *)v282;
            if ( v63 >= 0x1000 )
            {
              if ( (unsigned __int64)(v282 - *(_QWORD *)(v282 - 8) - 8) > 0x1F )
                __fastfail(5u);
              v64 = *(void **)(v282 - 8);
              v63 += 39LL;
            }
            operator delete(v64, v63);
          }
          goto LABEL_105;
        }
        v66 = v227;
        goto LABEL_119;
      }
      v58 = v233;
      if ( v54 > 0xF )
        v58 = *v233;
      if ( v56 == 7 )
      {
        if ( !memcmp_0(v58, "Options", 7u) && !v57 )
          goto LABEL_84;
LABEL_105:
        v41 = (unsigned __int64 *)v233;
        v50 = v234;
LABEL_106:
        ++v51;
        v47 = v236;
      }
      else
      {
        v41 = (unsigned __int64 *)v233;
        v50 = v234;
        ++v51;
        v47 = v236;
      }
    }
    if ( (_QWORD)v279 )
    {
      v90 = 8 * ((__int64)(v280 - v279) >> 3);
      if ( v90 >= 0x1000 )
      {
        v91 = *(void **)(v279 - 8);
        if ( (unsigned __int64)(v279 - (_QWORD)v91 - 8) <= 0x1F )
        {
          v90 += 39LL;
          goto LABEL_148;
        }
LABEL_358:
        __fastfail(5u);
      }
      v91 = (void *)v279;
LABEL_148:
      operator delete(v91, v90);
    }
    v37 = v231;
LABEL_150:
    v37 += 4;
  }
  v298 = 0;
  CLI::App::get_subcommands(v243, &v250, v297);
  if ( v298 )
  {
    v93 = v297;
    LOBYTE(v93) = v298 != v297;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v298 + 32LL))(v298, v93);
    v298 = 0;
  }
  v94 = *((_QWORD *)&v250 + 1);
  v95 = v250;
  if ( (_QWORD)v250 != *((_QWORD *)&v250 + 1) )
  {
    v96 = v225;
    while ( 1 )
    {
      v97 = *(_QWORD **)v95;
      if ( !*(_QWORD *)(*(_QWORD *)v95 + 24LL) && (v224 || CLI::App::count_all((CLI::App *)v97)) )
        break;
LABEL_191:
      v95 += 8;
      if ( v95 == v94 )
        goto LABEL_192;
    }
    if ( v96 )
    {
      v98 = v97 + 106;
      if ( v97[108] )
      {
        LOBYTE(v92) = 10;
        v99 = std::operator<<<std::char_traits<char>>(&v260, v92);
        v100 = v276;
        if ( v278 > 0xF )
          v100 = (void **)v276[0];
        v101 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v99, v100, v277);
        if ( v97[109] > 0xFu )
          v98 = (_QWORD *)*v98;
        v102 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v101, v98, v97[108]);
        std::operator<<<std::char_traits<char>>(v102, " Options\n");
      }
      v96 = v225;
    }
    *(_OWORD *)Src = 0;
    v103 = 0;
    Size[0] = 0;
    Size[1] = 0;
    if ( *((_QWORD *)v235 + 3) <= 0xFu )
      v104 = v235;
    else
      v104 = *(_OWORD **)v235;
    v105 = *((_QWORD *)v235 + 2);
    if ( v105 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlen_string();
    if ( v105 <= 0xF )
    {
      Size[0] = *((_QWORD *)v235 + 2);
      Size[1] = 15;
      *(_OWORD *)Src = *v104;
      goto LABEL_183;
    }
    v106 = v105 | 0xF;
    if ( (v105 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v106 = 0x7FFFFFFFFFFFFFFFLL;
      v107 = 0x8000000000000027uLL;
LABEL_179:
      v109 = operator new(v107);
      v110 = v109;
      if ( !v109 )
        goto LABEL_357;
      v103 = (_QWORD *)(((unsigned __int64)v109 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v103 - 1) = v110;
      goto LABEL_182;
    }
    if ( v106 < 0x16 )
      v106 = 22;
    v108 = v106 + 1;
    if ( v106 != -1 )
    {
      if ( v108 >= 0x1000 )
      {
        v107 = v106 + 40;
        if ( v106 + 40 < v106 + 1 )
          std::_Throw_bad_array_new_length();
        goto LABEL_179;
      }
      v103 = operator new(v108);
    }
LABEL_182:
    Src[0] = v103;
    Size[0] = v105;
    Size[1] = v106;
    memcpy_0(v103, v104, v105 + 1);
    v96 = v225;
LABEL_183:
    v111 = *(__int64 (__fastcall ***)(char *, void **, __int128 *, _QWORD, _DWORD, void **))v238;
    v223[0] = v96;
    v112 = (_QWORD *)(*v111)(v238, (void **)&Buf2, (__int128 *)v97, v224, *(_DWORD *)v223, Src);
    if ( v112[3] <= 0xFu )
      v113 = v112;
    else
      v113 = (_QWORD *)*v112;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v260, v113, v112[2]);
    v92 = *((_QWORD *)&v275 + 1);
    if ( *((_QWORD *)&v275 + 1) > 0xFu )
    {
      v114 = *((_QWORD *)&v275 + 1) + 1LL;
      v115 = (void *)Buf2;
      if ( (unsigned __int64)(*((_QWORD *)&v275 + 1) + 1LL) >= 0x1000 )
      {
        if ( (unsigned __int64)(Buf2 - *(_QWORD *)(Buf2 - 8) - 8) > 0x1F )
LABEL_357:
          __fastfail(5u);
        v114 = *((_QWORD *)&v275 + 1) + 40LL;
        v115 = *(void **)(Buf2 - 8);
      }
      operator delete(v115, v114);
    }
    goto LABEL_191;
  }
LABEL_192:
  v116 = 0x8000000000000027uLL;
  __SET_PAIR__((unsigned __int64)v231, (unsigned __int64)v117, v250);
  v239 = (char *)v250;
  if ( (_QWORD)v250 != *((_QWORD *)&v250 + 1) )
  {
    v118 = v226;
    v119 = v226;
    v120 = (char *)v231;
    while ( 1 )
    {
      v121 = *(__int128 **)v117;
      v232 = v121;
      v122 = (_QWORD *)v121 + 1;
      v123 = *((_QWORD *)v121 + 3);
      if ( v123 )
        break;
LABEL_346:
      v117 = v239 + 8;
      v239 = v117;
      if ( v117 == v120 )
        goto LABEL_347;
    }
    if ( !v224 )
    {
      v124 = CLI::App::count_all((CLI::App *)v121) == 0;
      v116 = 0x8000000000000027uLL;
      if ( v124 )
      {
LABEL_345:
        v120 = (char *)v231;
        goto LABEL_346;
      }
    }
    v267 = 0;
    v268 = 0u;
    if ( *((_QWORD *)v121 + 4) > 0xFu )
      v122 = (_QWORD *)*v122;
    if ( v123 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlen_string();
    if ( v123 <= 0xF )
    {
      *(_QWORD *)&v268 = v123;
      *((_QWORD *)&v268 + 1) = 15;
      v267 = *(_OWORD *)v122;
      goto LABEL_214;
    }
    v125 = v123 | 0xF;
    if ( (v123 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v125 = 0x7FFFFFFFFFFFFFFFLL;
LABEL_210:
      v128 = operator new(v116);
      v129 = v128;
      if ( !v128 )
        goto LABEL_357;
      v127 = (_QWORD *)(((unsigned __int64)v128 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v127 - 1) = v129;
      goto LABEL_213;
    }
    if ( v125 < 0x16 )
      v125 = 22;
    v126 = v125 + 1;
    if ( v125 == -1 )
    {
      v127 = 0;
    }
    else
    {
      if ( v126 >= 0x1000 )
      {
        v116 = v125 + 40;
        if ( v125 + 40 < v125 + 1 )
          std::_Throw_bad_array_new_length();
        goto LABEL_210;
      }
      v127 = operator new(v126);
    }
LABEL_213:
    *(_QWORD *)&v267 = v127;
    *(_QWORD *)&v268 = v123;
    *((_QWORD *)&v268 + 1) = v125;
    memcpy_0(v127, v122, v123 + 1);
    v121 = v232;
LABEL_214:
    CLI::clean_name_string(&v267);
    if ( !*((_BYTE *)v121 + 798) )
      goto LABEL_319;
    v130 = v243;
    v131 = v243[96];
    v132 = v243[97];
    while ( 1 )
    {
      if ( v131 == v132 )
      {
        v213 = std::_Func_impl_no_alloc<_lambda_c3fccf41025ebb26e61afda4a1aacb49_,bool,std::vector<std::string> const &>::_Get(v121);
        v214 = std::string::string(&v288, v213);
        CLI::OptionNotFound::OptionNotFound(pExceptionObject, v214);
        throw (CLI::OptionNotFound *)pExceptionObject;
      }
      if ( *(__int128 **)v131 == v121 )
        break;
      v131 += 16;
    }
    if ( *(_DWORD *)(*(_QWORD *)v131 + 804LL) )
    {
      v133 = v235;
      if ( *((_QWORD *)v235 + 2) || !v243[105] )
      {
        LOBYTE(v132) = 91;
        v180 = std::operator<<<std::char_traits<char>>(&v260, v132);
        if ( v133[3] <= 0xFu )
          v181 = v133;
        else
          v181 = (_QWORD *)*v133;
        v182 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v180, v181, v133[2]);
        v183 = &v267;
        if ( *((_QWORD *)&v268 + 1) > 0xFu )
          v183 = (__int128 *)v267;
        v184 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v182, v183, v268);
        std::operator<<<std::char_traits<char>>(v184, "]\n");
      }
      else
      {
        v279 = 0;
        v280 = 0;
        v281 = 0;
        if ( v243[4] <= 0xFu )
          v134 = (unsigned __int128 *)(v243 + 1);
        else
          v134 = (unsigned __int128 *)v243[1];
        v135 = v243[3];
        if ( v135 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlen_string();
        if ( v135 > 0xF )
        {
          v136 = v135 | 0xF;
          if ( (v135 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
          {
            if ( v136 < 0x16 )
              v136 = 22;
          }
          else
          {
            v136 = 0x7FFFFFFFFFFFFFFFLL;
          }
          v230 = (const void ***)v136;
          *(_QWORD *)&v279 = std::string::_Allocate_for_capacity<0>(&v279, &v230);
          v280 = v135;
          v281 = (unsigned __int64)v230;
          memcpy_0((void *)v279, v134, v135 + 1);
        }
        else
        {
          v280 = v243[3];
          v281 = 15;
          v279 = *v134;
        }
        CLI::clean_name_string(&v279);
        v226 = *v245;
        if ( v280 == 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlen_string();
        v137 = &v279;
        if ( v281 > 0xF )
          v137 = (unsigned __int128 *)v279;
        std::string::string(&Buf2, v119, &v279, v137, v280, &v226, 1);
        v138 = std::string::_Append<char>(&Buf2);
        v139 = *(_OWORD *)v138;
        v140 = *(_OWORD *)(v138 + 16);
        *(_QWORD *)(v138 + 16) = 0;
        *(_QWORD *)(v138 + 24) = 15;
        *(_BYTE *)v138 = 0;
        if ( *((_QWORD *)&v268 + 1) > 0xFu )
        {
          v141 = *((_QWORD *)&v268 + 1) + 1LL;
          v142 = (void *)v267;
          if ( (unsigned __int64)(*((_QWORD *)&v268 + 1) + 1LL) >= 0x1000 )
          {
            if ( (unsigned __int64)(v267 - *(_QWORD *)(v267 - 8) - 8) > 0x1F )
              __fastfail(5u);
            v141 = *((_QWORD *)&v268 + 1) + 40LL;
            v142 = *(void **)(v267 - 8);
          }
          operator delete(v142, v141);
        }
        v267 = v139;
        v268 = v140;
        v143 = *((_QWORD *)&v275 + 1);
        if ( *((_QWORD *)&v275 + 1) > 0xFu )
        {
          v144 = *((_QWORD *)&v275 + 1) + 1LL;
          v145 = (void *)Buf2;
          if ( (unsigned __int64)(*((_QWORD *)&v275 + 1) + 1LL) >= 0x1000 )
          {
            if ( (unsigned __int64)(Buf2 - *(_QWORD *)(Buf2 - 8) - 8) > 0x1F )
LABEL_354:
              __fastfail(5u);
            v144 = *((_QWORD *)&v275 + 1) + 40LL;
            v145 = *(void **)(Buf2 - 8);
          }
          operator delete(v145, v144);
        }
        v227 |= 0x180u;
        v146 = (const void **)v130[105];
        v230 = (const void ***)v146;
        if ( v146[105] )
        {
          while ( 1 )
          {
            *(_OWORD *)Src = 0;
            Size[0] = 0;
            Size[1] = 0;
            if ( (unsigned __int64)v146[4] <= 0xF )
              v147 = v146 + 1;
            else
              v147 = v146[1];
            v148 = (size_t)v146[3];
            if ( v148 > 0x7FFFFFFFFFFFFFFFLL )
              std::_Xlen_string();
            if ( v148 <= 0xF )
            {
              Size[0] = (size_t)v146[3];
              Size[1] = 15;
              *(_OWORD *)Src = *v147;
              goto LABEL_265;
            }
            v149 = v148 | 0xF;
            if ( (v148 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
              break;
            if ( v149 < 0x16 )
              v149 = 22;
            v151 = v149 + 1;
            if ( v149 == -1 )
            {
              v152 = 0;
            }
            else
            {
              if ( v151 >= 0x1000 )
              {
                v150 = v149 + 40;
                if ( v149 + 40 < v149 + 1 )
                  std::_Throw_bad_array_new_length();
                goto LABEL_261;
              }
              v152 = operator new(v151);
            }
LABEL_264:
            Src[0] = v152;
            Size[0] = v148;
            Size[1] = v149;
            memcpy_0(v152, v147, v148 + 1);
LABEL_265:
            CLI::clean_name_string(Src);
            v226 = *v245;
            v155 = Size[0];
            if ( Size[0] == 0x7FFFFFFFFFFFFFFFLL )
              std::_Xlen_string();
            v156 = Src;
            if ( Size[1] > 0xF )
              v156 = (void **)Src[0];
            Buf2 = 0;
            v275 = 0u;
            v157 = Size[0] + 1;
            if ( Size[0] + 1 <= 0xF )
            {
              v158 = 15;
              v161 = &Buf2;
            }
            else
            {
              v158 = v157 | 0xF;
              if ( (v157 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
              {
                v158 = 0x7FFFFFFFFFFFFFFFLL;
                v159 = 0x8000000000000027uLL;
LABEL_277:
                v162 = operator new(v159);
                if ( !v162 )
                  goto LABEL_353;
                v161 = (__int128 *)(((unsigned __int64)v162 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                *((_QWORD *)v161 - 1) = v162;
                *(_QWORD *)&Buf2 = v161;
                goto LABEL_281;
              }
              if ( v158 < 0x16 )
                v158 = 22;
              v160 = v158 + 1;
              if ( v158 == -1 )
              {
                v161 = 0;
                *(_QWORD *)&Buf2 = 0;
              }
              else
              {
                if ( v160 >= 0x1000 )
                {
                  v159 = v158 + 40;
                  if ( v158 + 40 < v158 + 1 )
                    std::_Throw_bad_array_new_length();
                  goto LABEL_277;
                }
                v161 = (__int128 *)operator new(v160);
                *(_QWORD *)&Buf2 = v161;
              }
            }
LABEL_281:
            *(_QWORD *)&v275 = v155 + 1;
            *((_QWORD *)&v275 + 1) = v158;
            memcpy_0(v161, v156, v155);
            *((_BYTE *)v161 + v155) = v226;
            *((_BYTE *)v161 + v157) = 0;
            v163 = std::string::_Append<char>(&Buf2);
            v164 = *(_OWORD *)v163;
            v165 = *(_OWORD *)(v163 + 16);
            *(_QWORD *)(v163 + 16) = 0;
            *(_QWORD *)(v163 + 24) = 15;
            *(_BYTE *)v163 = 0;
            if ( *((_QWORD *)&v268 + 1) > 0xFu )
            {
              v166 = *((_QWORD *)&v268 + 1) + 1LL;
              v167 = (void *)v267;
              if ( (unsigned __int64)(*((_QWORD *)&v268 + 1) + 1LL) >= 0x1000 )
              {
                if ( (unsigned __int64)(v267 - *(_QWORD *)(v267 - 8) - 8) > 0x1F )
                  __fastfail(5u);
                v166 = *((_QWORD *)&v268 + 1) + 40LL;
                v167 = *(void **)(v267 - 8);
              }
              operator delete(v167, v166);
            }
            v267 = v164;
            v268 = v165;
            if ( *((_QWORD *)&v275 + 1) > 0xFu )
            {
              v168 = *((_QWORD *)&v275 + 1) + 1LL;
              v169 = (void *)Buf2;
              if ( (unsigned __int64)(*((_QWORD *)&v275 + 1) + 1LL) >= 0x1000 )
              {
                if ( (unsigned __int64)(Buf2 - *(_QWORD *)(Buf2 - 8) - 8) > 0x1F )
LABEL_353:
                  __fastfail(5u);
                v168 = *((_QWORD *)&v275 + 1) + 40LL;
                v169 = *(void **)(Buf2 - 8);
              }
              operator delete(v169, v168);
            }
            v146 = v230[105];
            v230 = (const void ***)v146;
            v143 = Size[1];
            if ( Size[1] > 0xF )
            {
              v170 = Size[1] + 1;
              v171 = Src[0];
              if ( Size[1] + 1 >= 0x1000 )
              {
                if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
                  goto LABEL_354;
                v170 = Size[1] + 40;
                v171 = (void *)*((_QWORD *)Src[0] - 1);
              }
              operator delete(v171, v170);
            }
            v227 |= 0x30u;
            if ( !v146[105] )
              goto LABEL_297;
          }
          v149 = 0x7FFFFFFFFFFFFFFFLL;
          v150 = 0x8000000000000027uLL;
LABEL_261:
          v153 = operator new(v150);
          v154 = v153;
          if ( !v153 )
            goto LABEL_354;
          v152 = (void *)(((unsigned __int64)v153 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v152 - 1) = v154;
          goto LABEL_264;
        }
LABEL_297:
        LOBYTE(v143) = 91;
        v172 = std::operator<<<std::char_traits<char>>(&v260, v143);
        v173 = &v267;
        if ( *((_QWORD *)&v268 + 1) > 0xFu )
          v173 = (__int128 *)v267;
        v174 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v172, v173, v268);
        std::operator<<<std::char_traits<char>>(v174, "]\n");
        if ( v281 > 0xF )
        {
          v175 = v281 + 1;
          v176 = (void *)v279;
          if ( v281 + 1 >= 0x1000 )
          {
            if ( (unsigned __int64)(v279 - *(_QWORD *)(v279 - 8) - 8) > 0x1F )
              goto LABEL_355;
            v175 = v281 + 40;
            v176 = *(void **)(v279 - 8);
          }
          operator delete(v176, v175);
        }
        v121 = v232;
      }
      Buf2 = 0;
      *(_QWORD *)&v275 = 0;
      *((_QWORD *)&v275 + 1) = 15;
      LOBYTE(Buf2) = 0;
      v177 = *(__int64 (__fastcall ***)(char *, void **, __int128 *, _QWORD, _DWORD, void **))v238;
      v223[0] = v225;
      v178 = (_QWORD *)(*v177)(v238, Src, v121, v224, *(_DWORD *)v223, (void **)&Buf2);
      if ( v178[3] <= 0xFu )
        v179 = v178;
      else
        v179 = (_QWORD *)*v178;
      std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v260, v179, v178[2]);
      if ( Size[1] > 0xF )
      {
        v185 = Size[1] + 1;
        v186 = Src[0];
        if ( Size[1] + 1 >= 0x1000 )
        {
          if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
LABEL_355:
            __fastfail(5u);
          v185 = Size[1] + 40;
          v186 = (void *)*((_QWORD *)Src[0] - 1);
        }
        operator delete(v186, v185);
      }
    }
    else
    {
LABEL_319:
      v187 = *((_QWORD *)v235 + 2);
      if ( 0x7FFFFFFFFFFFFFFFLL - v187 < (unsigned __int64)v268 )
        std::_Xlen_string();
      if ( *((_QWORD *)v235 + 3) <= 0xFu )
        v188 = v235;
      else
        v188 = *(_OWORD **)v235;
      v189 = &v267;
      if ( *((_QWORD *)&v268 + 1) > 0xFu )
        v189 = (__int128 *)v267;
      std::string::string(Src, v118, v235, v188, v187, v189, v268);
      v190 = *v245;
      v191 = Size[0];
      if ( Size[0] >= Size[1] )
      {
        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src, 1, 0, v190);
      }
      else
      {
        ++Size[0];
        v192 = Src;
        if ( Size[1] > 0xF )
          v192 = (void **)Src[0];
        *((_BYTE *)v192 + v191) = v190;
        *((_BYTE *)v192 + v191 + 1) = 0;
      }
      Buf2 = *(_OWORD *)Src;
      v275 = *(_OWORD *)Size;
      Size[0] = 0;
      Size[1] = 15;
      LOBYTE(Src[0]) = 0;
      v193 = *(__int64 (__fastcall ***)(char *, void **, __int128 *, _QWORD, _DWORD, void **))v238;
      v223[0] = v225;
      v194 = (_QWORD *)(*v193)(v238, (void **)&v279, v121, v224, *(_DWORD *)v223, (void **)&Buf2);
      if ( v194[3] <= 0xFu )
        v195 = v194;
      else
        v195 = (_QWORD *)*v194;
      std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v260, v195, v194[2]);
      if ( v281 > 0xF )
      {
        v196 = v281 + 1;
        v197 = (void *)v279;
        if ( v281 + 1 >= 0x1000 )
        {
          if ( (unsigned __int64)(v279 - *(_QWORD *)(v279 - 8) - 8) > 0x1F )
            __fastfail(5u);
          v196 = v281 + 40;
          v197 = *(void **)(v279 - 8);
        }
        operator delete(v197, v196);
      }
      v227 |= 0xCu;
    }
    if ( *((_QWORD *)&v268 + 1) > 0xFu )
    {
      v198 = *((_QWORD *)&v268 + 1) + 1LL;
      v199 = (void *)v267;
      if ( (unsigned __int64)(*((_QWORD *)&v268 + 1) + 1LL) >= 0x1000 )
      {
        if ( (unsigned __int64)(v267 - *(_QWORD *)(v267 - 8) - 8) > 0x1F )
          goto LABEL_357;
        v198 = *((_QWORD *)&v268 + 1) + 40LL;
        v199 = *(void **)(v267 - 8);
      }
      operator delete(v199, v198);
    }
    v116 = 0x8000000000000027uLL;
    goto LABEL_345;
  }
LABEL_347:
  std::stringbuf::str(&v261, v248);
  if ( (_QWORD)v250 )
  {
    v200 = 8 * ((v251 - (__int64)v250) >> 3);
    if ( v200 < 0x1000 )
    {
      v201 = (void *)v250;
    }
    else
    {
      v201 = *(void **)(v250 - 8);
      if ( (unsigned __int64)(v250 - (_QWORD)v201 - 8) > 0x1F )
        goto LABEL_358;
      v200 += 39LL;
    }
    operator delete(v201, v200);
    v250 = 0;
    v251 = 0;
  }
  v202 = (char *)v241[0];
  if ( v241[0] )
  {
    v203 = (char *)v241[1];
    if ( v241[0] != v241[1] )
    {
      do
      {
        std::string::_Tidy_deallocate(v202);
        v202 += 32;
      }
      while ( v202 != v203 );
      v202 = (char *)v241[0];
    }
    v204 = (v242 - v202) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v204 < 0x1000 )
    {
      v205 = v202;
    }
    else
    {
      v205 = (_BYTE *)*((_QWORD *)v202 - 1);
      if ( (unsigned __int64)(v202 - v205 - 8) > 0x1F )
        __fastfail(5u);
      v204 += 39LL;
    }
    operator delete(v205, v204);
    *(_OWORD *)v241 = 0;
    v242 = 0;
  }
  if ( v273 > 0xF )
  {
    v206 = v273 + 1;
    if ( v273 + 1 < 0x1000 )
    {
      v207 = v271[0];
    }
    else
    {
      v207 = (void *)*((_QWORD *)v271[0] - 1);
      if ( (unsigned __int64)((char *)v271[0] - (char *)v207 - 8) > 0x1F )
        __fastfail(5u);
      v206 = v273 + 40;
    }
    operator delete(v207, v206);
  }
  if ( v287 > 0xF )
  {
    v208 = v287 + 1;
    if ( v287 + 1 < 0x1000 )
    {
      v209 = v285[0];
    }
    else
    {
      v209 = (void *)*((_QWORD *)v285[0] - 1);
      if ( (unsigned __int64)((char *)v285[0] - (char *)v209 - 8) > 0x1F )
        __fastfail(5u);
      v208 = v287 + 40;
    }
    operator delete(v209, v208);
  }
  if ( v278 > 0xF )
  {
    v210 = v278 + 1;
    if ( v278 + 1 < 0x1000 )
    {
      v211 = v276[0];
    }
    else
    {
      v211 = (void *)*((_QWORD *)v276[0] - 1);
      if ( (unsigned __int64)((char *)v276[0] - (char *)v211 - 8) > 0x1F )
        __fastfail(5u);
      v210 = v278 + 40;
    }
    operator delete(v211, v210);
  }
  v277 = 0;
  v278 = 15;
  LOBYTE(v276[0]) = 0;
  *(_QWORD *)((char *)v259 + *(int *)(v259[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
  *(int *)((char *)&v258 + *(int *)(v259[0] + 4LL)) = *(_DWORD *)(v259[0] + 4LL) - 152;
  v261 = &std::stringbuf::`vftable';
  std::stringbuf::_Tidy(&v261);
  std::streambuf::~streambuf<char,std::char_traits<char>>(&v261);
  std::iostream::~basic_iostream<char,std::char_traits<char>>(&v262);
  std::ios::~ios<char,std::char_traits<char>>(&v263);
  std::string::_Tidy_deallocate(v235);
  return v248;
}

```

## disassembly

```asm
0x140041b00  mov     r11, rsp
0x140041b03  push    rbx
0x140041b04  push    rsi
0x140041b05  push    rdi
0x140041b06  push    r12
0x140041b08  push    r13
0x140041b0a  push    r14
0x140041b0c  push    r15
0x140041b0e  sub     rsp, 4A0h
0x140041b15  movaps  xmmword ptr [r11-48h], xmm6
0x140041b1a  movaps  xmmword ptr [r11-58h], xmm7
0x140041b1f  mov     rax, cs:__security_cookie
0x140041b26  xor     rax, rsp
0x140041b29  mov     [rsp+4D8h+var_68], rax
0x140041b31  movzx   eax, r9b
0x140041b35  mov     [rsp+4D8h+var_498], al
0x140041b39  mov     r15, r8
0x140041b3c  mov     [rsp+4D8h+var_400], r8
0x140041b44  mov     rbx, rcx
0x140041b47  mov     [rsp+4D8h+var_430], rcx
0x140041b4f  mov     [rsp+4D8h+var_428], rcx
0x140041b57  mov     [rsp+4D8h+var_3D8], rdx
0x140041b5f  mov     [rsp+4D8h+var_3A0], r8
0x140041b67  mov     [rsp+4D8h+var_488], al
0x140041b6b  movzx   esi, [rsp+4D8h+arg_20]
0x140041b73  mov     [rsp+4D8h+var_490], sil
0x140041b78  mov     rcx, [rsp+4D8h+arg_28]
0x140041b80  mov     [r11-448h], rcx
0x140041b87  mov     [r11-238h], rcx
0x140041b8e  xor     r12d, r12d
0x140041b91  mov     eax, r12d
0x140041b94  mov     [rsp+4D8h+var_480], eax
0x140041b98  mov     [rsp+4D8h+var_478], eax
0x140041b9c  mov     edx, 1
0x140041ba1  lea     rcx, [r11-378h]
0x140041ba8  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x140041bad  nop
0x140041bae  xorps   xmm0, xmm0
0x140041bb1  movups  xmmword ptr [rsp+4D8h+var_1B0], xmm0
0x140041bb9  mov     edi, 0Fh
0x140041bbe  mov     [rsp+4D8h+var_198], rdi
0x140041bc6  movzx   r9d, byte ptr [rbx+20h]
0x140041bcb  mov     byte ptr [rsp+4D8h+var_1B0], r9b
0x140041bd3  mov     ecx, 2
0x140041bd8  mov     [rsp+4D8h+var_1A0], rcx
0x140041be0  mov     word ptr [rsp+4D8h+var_1B0+1], 20h ; ' '
0x140041bea  movups  xmmword ptr [rsp+4D8h+var_150], xmm0
0x140041bf2  mov     [rsp+4D8h+var_138], rdi
0x140041bfa  movzx   eax, word ptr cs:asc_14006D18C; "#;"
0x140041c01  mov     word ptr [rsp+4D8h+var_150], ax
0x140041c09  mov     byte ptr [rsp+4D8h+var_150+2], r12b
0x140041c11  lea     rax, [rcx+1]
0x140041c15  mov     [rsp+4D8h+var_140], rax
0x140041c1d  lea     rax, [rsp+4D8h+var_150]
0x140041c25  mov     [rcx+rax], r9b
0x140041c29  mov     [rcx+rax+1], r12b
0x140041c2e  lea     rax, [rbx+28h]
0x140041c32  mov     [rsp+4D8h+var_3F0], rax
0x140041c3a  movzx   r9d, byte ptr [rax]
0x140041c3e  mov     rcx, [rsp+4D8h+var_140]
0x140041c46  mov     rdx, [rsp+4D8h+var_138]
0x140041c4e  cmp     rcx, rdx
0x140041c51  jnb     short loc_140041C7E
0x140041c53  lea     rax, [rcx+1]
0x140041c57  mov     [rsp+4D8h+var_140], rax
0x140041c5f  lea     rax, [rsp+4D8h+var_150]
0x140041c67  cmp     rdx, rdi
0x140041c6a  cmova   rax, [rsp+4D8h+var_150]
0x140041c73  mov     [rax+rcx], r9b
0x140041c77  mov     [rax+rcx+1], r12b
0x140041c7c  jmp     short loc_140041C93
0x140041c7e  xor     r8d, r8d
0x140041c81  mov     edx, 1
0x140041c86  lea     rcx, [rsp+4D8h+var_150]
0x140041c8e  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x140041c93  lea     rdx, [rsp+4D8h+var_150]
0x140041c9b  lea     rcx, [rsp+4D8h+var_1F0]
0x140041ca3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140041ca8  nop
0x140041ca9  lea     rax, [rbx+26h]
0x140041cad  mov     [rsp+4D8h+var_3E8], rax
0x140041cb5  movzx   r9d, byte ptr [rax]
0x140041cb9  mov     rcx, [rsp+4D8h+var_1E0]
0x140041cc1  mov     rdx, [rsp+4D8h+var_1D8]
0x140041cc9  cmp     rcx, rdx
0x140041ccc  jnb     short loc_140041CFA
0x140041cce  lea     rax, [rcx+1]
0x140041cd2  mov     [rsp+4D8h+var_1E0], rax
0x140041cda  lea     rax, [rsp+4D8h+var_1F0]
0x140041ce2  cmp     rdx, 0Fh
0x140041ce6  cmova   rax, [rsp+4D8h+var_1F0]
0x140041cef  mov     [rax+rcx], r9b
0x140041cf3  mov     byte ptr [rax+rcx+1], 0
0x140041cf8  jmp     short loc_140041D0F
0x140041cfa  xor     r8d, r8d
0x140041cfd  mov     edx, 1
0x140041d02  lea     rcx, [rsp+4D8h+var_1F0]
0x140041d0a  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x140041d0f  lea     rax, [rbx+25h]
0x140041d13  mov     [rsp+4D8h+var_3E0], rax
0x140041d1b  movzx   r9d, byte ptr [rax]
0x140041d1f  mov     rcx, [rsp+4D8h+var_1E0]
0x140041d27  mov     rdx, [rsp+4D8h+var_1D8]
0x140041d2f  cmp     rcx, rdx
0x140041d32  jnb     short loc_140041D60
0x140041d34  lea     rax, [rcx+1]
0x140041d38  mov     [rsp+4D8h+var_1E0], rax
0x140041d40  lea     rax, [rsp+4D8h+var_1F0]
0x140041d48  cmp     rdx, 0Fh
0x140041d4c  cmova   rax, [rsp+4D8h+var_1F0]
0x140041d55  mov     [rax+rcx], r9b
0x140041d59  mov     byte ptr [rax+rcx+1], 0
0x140041d5e  jmp     short loc_140041D75
0x140041d60  xor     r8d, r8d
0x140041d63  mov     edx, 1
0x140041d68  lea     rcx, [rsp+4D8h+var_1F0]
0x140041d70  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x140041d75  lea     rax, [rbx+21h]
0x140041d79  mov     [rsp+4D8h+var_390], rax
0x140041d81  movzx   r9d, byte ptr [rax]
0x140041d85  mov     rcx, [rsp+4D8h+var_1E0]
0x140041d8d  mov     rdx, [rsp+4D8h+var_1D8]
0x140041d95  cmp     rcx, rdx
0x140041d98  jnb     short loc_140041DC6
0x140041d9a  lea     rax, [rcx+1]
0x140041d9e  mov     [rsp+4D8h+var_1E0], rax
0x140041da6  lea     rax, [rsp+4D8h+var_1F0]
0x140041dae  cmp     rdx, 0Fh
0x140041db2  cmova   rax, [rsp+4D8h+var_1F0]
0x140041dbb  mov     [rax+rcx], r9b
0x140041dbf  mov     byte ptr [rax+rcx+1], 0
0x140041dc4  jmp     short loc_140041DDB
0x140041dc6  xor     r8d, r8d
0x140041dc9  mov     edx, 1
0x140041dce  lea     rcx, [rsp+4D8h+var_1F0]
0x140041dd6  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x140041ddb  lea     rax, [rbx+22h]
0x140041ddf  mov     [rsp+4D8h+var_398], rax
0x140041de7  movzx   r9d, byte ptr [rax]
0x140041deb  mov     rcx, [rsp+4D8h+var_1E0]
0x140041df3  mov     rdx, [rsp+4D8h+var_1D8]
0x140041dfb  cmp     rcx, rdx
0x140041dfe  jnb     short loc_140041E2C
0x140041e00  lea     rax, [rcx+1]
0x140041e04  mov     [rsp+4D8h+var_1E0], rax
0x140041e0c  lea     rax, [rsp+4D8h+var_1F0]
0x140041e14  cmp     rdx, 0Fh
0x140041e18  cmova   rax, [rsp+4D8h+var_1F0]
0x140041e21  mov     [rax+rcx], r9b
0x140041e25  mov     byte ptr [rax+rcx+1], 0
0x140041e2a  jmp     short loc_140041E41
0x140041e2c  xor     r8d, r8d
0x140041e2f  mov     edx, 1
0x140041e34  lea     rcx, [rsp+4D8h+var_1F0]
0x140041e3c  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x140041e41  lea     rax, [rbx+24h]
0x140041e45  mov     [rsp+4D8h+var_420], rax
0x140041e4d  movzx   r9d, byte ptr [rax]
0x140041e51  mov     rcx, [rsp+4D8h+var_1E0]
0x140041e59  mov     rdx, [rsp+4D8h+var_1D8]
0x140041e61  cmp     rcx, rdx
0x140041e64  jnb     short loc_140041E92
0x140041e66  lea     rax, [rcx+1]
0x140041e6a  mov     [rsp+4D8h+var_1E0], rax
0x140041e72  lea     rax, [rsp+4D8h+var_1F0]
0x140041e7a  cmp     rdx, 0Fh
0x140041e7e  cmova   rax, [rsp+4D8h+var_1F0]
0x140041e87  mov     [rax+rcx], r9b
0x140041e8b  mov     byte ptr [rax+rcx+1], 0
0x140041e90  jmp     short loc_140041EA7
0x140041e92  xor     r8d, r8d
0x140041e95  mov     edx, 1
0x140041e9a  lea     rcx, [rsp+4D8h+var_1F0]
0x140041ea2  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x140041ea7  lea     rax, [rbx+23h]
0x140041eab  mov     [rsp+4D8h+var_388], rax
0x140041eb3  movzx   r9d, byte ptr [rax]
0x140041eb7  mov     rcx, [rsp+4D8h+var_1E0]
0x140041ebf  mov     rdx, [rsp+4D8h+var_1D8]
0x140041ec7  cmp     rcx, rdx
0x140041eca  jnb     short loc_140041EF8
0x140041ecc  lea     rax, [rcx+1]
0x140041ed0  mov     [rsp+4D8h+var_1E0], rax
0x140041ed8  lea     rax, [rsp+4D8h+var_1F0]
0x140041ee0  cmp     rdx, 0Fh
0x140041ee4  cmova   rax, [rsp+4D8h+var_1F0]
0x140041eed  mov     [rax+rcx], r9b
0x140041ef1  mov     byte ptr [rax+rcx+1], 0
0x140041ef6  jmp     short loc_140041F0D
0x140041ef8  xor     r8d, r8d
0x140041efb  mov     edx, 1
0x140041f00  lea     rcx, [rsp+4D8h+var_1F0]
0x140041f08  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x140041f0d  lea     rdx, [rsp+4D8h+var_418]
0x140041f15  mov     rcx, r15
0x140041f18  call    ?get_groups@App@CLI@@QEBA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ; CLI::App::get_groups(void)
0x140041f1d  nop
0x140041f1e  mov     [rsp+4D8h+var_47C], 0
0x140041f23  mov     rbx, [rsp+4D8h+var_418]
0x140041f2b  xorps   xmm0, xmm0
0x140041f2e  movups  [rsp+4D8h+var_230], xmm0
0x140041f36  mov     qword ptr [rsp+4D8h+var_220], 7
0x140041f42  mov     qword ptr [rsp+4D8h+var_220+8], rdi
0x140041f4a  mov     rax, qword ptr cs:aOptions; "Options"
0x140041f51  mov     dword ptr [rsp+4D8h+var_230], eax
0x140041f58  movzx   eax, word ptr cs:aOptions+4; "ons"
0x140041f5f  mov     word ptr [rsp+4D8h+var_230+4], ax
0x140041f67  movzx   eax, byte ptr cs:aOptions+6; "s"
0x140041f6e  mov     byte ptr [rsp+4D8h+var_230+6], al
0x140041f75  mov     byte ptr [rsp+4D8h+var_230+7], 0
0x140041f7d  mov     r8, [rsp+4D8h+var_418+8]
0x140041f85  cmp     r8, [rsp+4D8h+var_408]
0x140041f8d  jz      loc_1400420AF
0x140041f93  cmp     rbx, r8
0x140041f96  jnz     short loc_140041FD7
0x140041f98  movups  xmm0, [rsp+4D8h+var_230]
0x140041fa0  movups  xmmword ptr [r8], xmm0
0x140041fa4  movups  xmm1, [rsp+4D8h+var_220]
0x140041fac  movups  xmmword ptr [r8+10h], xmm1
0x140041fb1  mov     qword ptr [rsp+4D8h+var_220], r12
0x140041fb9  mov     qword ptr [rsp+4D8h+var_220+8], rdi
0x140041fc1  mov     byte ptr [rsp+4D8h+var_230], 0
0x140041fc9  add     [rsp+4D8h+var_418+8], 20h ; ' '
0x140041fd2  jmp     loc_1400420C8
0x140041fd7  lea     rax, [rsp+4D8h+var_418]
0x140041fdf  mov     [rsp+4D8h+var_130], rax
0x140041fe7  movups  [rsp+4D8h+var_128], xmm0
0x140041fef  movzx   eax, byte ptr [rsp+4D8h+var_230]
0x140041ff7  mov     byte ptr [rsp+4D8h+var_128], al
0x140041ffe  mov     eax, dword ptr [rsp+4D8h+var_230+1]
0x140042005  mov     dword ptr [rsp+4D8h+var_128+1], eax
0x14004200c  movzx   eax, word ptr [rsp+4D8h+var_230+5]
0x140042014  mov     word ptr [rsp+4D8h+var_128+5], ax
0x14004201c  mov     byte ptr [rsp+4D8h+var_128+7], 0
0x140042024  mov     rax, qword ptr [rsp+4D8h+var_230+8]
0x14004202c  mov     qword ptr [rsp+4D8h+var_128+8], rax
0x140042034  mov     [rsp+4D8h+var_118], 7
0x140042040  mov     [rsp+4D8h+var_110], rdi
0x140042048  mov     qword ptr [rsp+4D8h+var_220], r12
0x140042050  mov     qword ptr [rsp+4D8h+var_220+8], rdi
0x140042058  mov     byte ptr [rsp+4D8h+var_230], 0
0x140042060  lea     rdx, [r8-20h]
0x140042064  movups  xmm0, xmmword ptr [rdx]
0x140042067  movups  xmmword ptr [r8], xmm0
0x14004206b  movups  xmm1, xmmword ptr [rdx+10h]
0x14004206f  movups  xmmword ptr [r8+10h], xmm1
0x140042074  mov     [rdx+10h], r12
0x140042078  mov     [rdx+18h], rdi
0x14004207c  mov     byte ptr [rdx], 0
0x14004207f  add     [rsp+4D8h+var_418+8], 20h ; ' '
0x140042088  mov     rcx, rbx
0x14004208b  call    ??$_Move_backward_unchecked@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV12@@std@@YAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@PEAV10@00@Z; std::_Move_backward_unchecked<std::string *,std::string *>(std::string *,std::string *,std::string *)
0x140042090  lea     rdx, [rsp+4D8h+var_128]
0x140042098  mov     rcx, rbx
0x14004209b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1400420a0  lea     rcx, [rsp+4D8h+var_128]; void *
0x1400420a8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400420ad  jmp     short loc_1400420C8
0x1400420af  lea     r8, [rsp+4D8h+var_230]
0x1400420b7  mov     rdx, rbx
0x1400420ba  lea     rcx, [rsp+4D8h+var_418]
0x1400420c2  call    ??$_Emplace_reallocate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string>(std::string * const,std::string &&)
0x1400420c7  nop
0x1400420c8  lea     rcx, [rsp+4D8h+var_230]; void *
0x1400420d0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400420d5  test    sil, sil
0x1400420d8  jz      loc_14004219D
0x1400420de  cmp     byte ptr [r15+31Eh], 0
0x1400420e6  jnz     short loc_1400420FD
0x1400420e8  cmp     qword ptr [r15+348h], 0
0x1400420f0  jz      short loc_1400420FD
0x1400420f2  cmp     qword ptr [r15+18h], 0
0x1400420f7  jnz     loc_14004219D
0x1400420fd  lea     rdx, [r15+28h]
0x140042101  lea     rcx, [rsp+4D8h+Buf2]
0x140042109  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x14004210e  mov     eax, 800h
0x140042113  mov     [rsp+4D8h+var_480], eax
0x140042117  mov     [rsp+4D8h+var_478], eax
0x14004211b  lea     r8, [rsp+4D8h+Buf2]
0x140042123  lea     rdx, [rsp+4D8h+var_1B0]
0x14004212b  lea     rcx, [rsp+4D8h+Src]
0x140042133  call    ?fix_newlines@detail@CLI@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@V34@@Z; CLI::detail::fix_newlines(std::string const &,std::string)
0x140042138  mov     rbx, rax
0x14004213b  lea     rdx, [rsp+4D8h+var_1B0]
0x140042143  cmp     [rsp+4D8h+var_198], 0Fh
0x14004214c  cmova   rdx, [rsp+4D8h+var_1B0]
0x140042155  mov     r8, [rsp+4D8h+var_1A0]
0x14004215d  lea     rcx, [rsp+4D8h+var_368]
0x140042165  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x14004216a  cmp     qword ptr [rbx+18h], 0Fh
0x14004216f  jbe     short loc_140042176
0x140042171  mov     rdx, [rbx]
0x140042174  jmp     short loc_140042179
0x140042176  mov     rdx, rbx
0x140042179  mov     r8, [rbx+10h]
0x14004217d  mov     rcx, rax
0x140042180  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x140042185  mov     dl, 0Ah
0x140042187  mov     rcx, rax
  ... truncated ...
```
