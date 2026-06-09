# PageRef::ChangeFileHeader(Record const &,int,LSN const &,uint,structVLFInfo const *)

- ea: `0x10055b190`
- end: `0x10055b406`
- name: `?ChangeFileHeader@PageRef@@QEAAXAEBVRecord@@HAEBVLSN@@IPEBUstructVLFInfo@@@Z`
- size: `630`
- prototype: `void __fastcall(PageRef *__hidden this, const struct Record *, int, const struct LSN *, unsigned int, const struct structVLFInfo *)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1005591d0`
- `0x10184eb20`
- `0x1025e1444`

## callees

- `0x100401490`
- `0x10042d750`
- `0x100441e00`
- `0x100445e80`
- `0x1004489c0`
- `0x100455720`
- `0x1004729d0`
- `0x10047bc10`
- `0x100480030`
- `0x100480640`
- `0x1004813c0`
- `0x100481c40`
- `0x1004a6ea0`
- `0x100544f10`
- `0x10055b190`
- `0x10055b410`
- `0x10058cca0`
- `0x1012c9010`
- `0x10168b160`
- `0x101d0fad0`
- `0x1021d8a90`
- `0x1021eab40`
- `0x1023aecb0`

## import_xrefs

- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f2721`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f27d2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f2944`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f299c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f400a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4035`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4060`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4137`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4162`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f41bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f41f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f421b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f42f3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f431e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f437d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f43ae`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f43d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f44c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f44ed`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f454a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4575`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f45a0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4671`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f469c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f2721`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f27d2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f2944`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f299c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f400a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4035`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4060`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4137`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4162`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f41bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f41f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f421b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f42f3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f431e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f437d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f43ae`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f43d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f44c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f44ed`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f454a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4575`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f45a0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f4671`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018f469c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2b61`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2c15`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2cc8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2ea7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2f48`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3070`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3125`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f31d6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f33bd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f345e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f35fc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f36b2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3765`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3951`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f39f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3b17`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3bca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3c7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3e61`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3f02`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2b61`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2c15`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2cc8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2ea7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f2f48`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3070`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3125`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f31d6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f33bd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f345e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f35fc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f36b2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3765`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3951`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f39f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3b17`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3bca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3c7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3e61`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018f3f02`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1018f2303`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1018f2303`
- `sqldk!SystemThread_TlsIndex` at `0x10055b26a`
- `sqldk!SystemThread_TlsIndex` at `0x1018f2b03`
- `sqldk!SystemThread_TlsIndex` at `0x1018f2bb7`
- `sqldk!SystemThread_TlsIndex` at `0x1018f2c6a`
- `sqldk!SystemThread_TlsIndex` at `0x1018f2e49`
- `sqldk!SystemThread_TlsIndex` at `0x1018f2eea`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3012`
- `sqldk!SystemThread_TlsIndex` at `0x1018f30c7`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3178`
- `sqldk!SystemThread_TlsIndex` at `0x1018f335f`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3400`
- `sqldk!SystemThread_TlsIndex` at `0x1018f359e`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3654`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3707`
- `sqldk!SystemThread_TlsIndex` at `0x1018f38f3`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3994`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3ab9`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3b6c`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3c1d`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3e03`
- `sqldk!SystemThread_TlsIndex` at `0x1018f3ea4`
- `sqldk!SystemThread_TlsOffset` at `0x10055b273`
- `sqldk!SystemThread_TlsOffset` at `0x1018f2b0c`
- `sqldk!SystemThread_TlsOffset` at `0x1018f2bc0`
- `sqldk!SystemThread_TlsOffset` at `0x1018f2c73`
- `sqldk!SystemThread_TlsOffset` at `0x1018f2e52`
- `sqldk!SystemThread_TlsOffset` at `0x1018f2ef3`
- `sqldk!SystemThread_TlsOffset` at `0x1018f301b`
- `sqldk!SystemThread_TlsOffset` at `0x1018f30d0`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3181`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3368`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3409`
- `sqldk!SystemThread_TlsOffset` at `0x1018f35a7`
- `sqldk!SystemThread_TlsOffset` at `0x1018f365d`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3710`
- `sqldk!SystemThread_TlsOffset` at `0x1018f38fc`
- `sqldk!SystemThread_TlsOffset` at `0x1018f399d`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3ac2`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3b75`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3c26`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3e0c`
- `sqldk!SystemThread_TlsOffset` at `0x1018f3ead`

## string_xrefs

- `0x1018f2348`: `Non-logged log file grow for repair purpose.`

## pseudocode

```c
void __fastcall PageRef::ChangeFileHeader(
        BUF **this,
        const struct Record *a2,
        int a3,
        const struct LSN *a4,
        unsigned int a5,
        const struct structVLFInfo *a6)
{
  BUF *v6; // rdx
  int v7; // esi
  unsigned __int64 v9; // rdx
  __int64 v10; // r13
  __int16 v11; // r15
  BUF *v12; // r11
  __int64 v13; // r11
  __int64 v14; // rax
  struct CSessionTraceFlags *v15; // rcx
  unsigned int v16; // r14d
  _OWORD *v17; // rbx
  int v18; // edi
  unsigned __int8 *v19; // r8
  __int64 v20; // rdx
  BUF *v21; // r11
  struct BUF *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // r11
  __int64 v26; // rax
  RecoveryUnit *v27; // rcx
  __int64 v28; // r11
  __int64 v29; // rax
  __int64 v30; // r11
  __int64 v31; // r11
  char v32; // al
  unsigned __int16 v33; // di
  BUF *v34; // r11
  __int64 v35; // rcx
  __int64 FCB; // rax
  BUF *v37; // r11
  __int64 v38; // rsi
  BUF *v39; // rbx
  __int64 v40; // rax
  __int64 v41; // r11
  unsigned int v42; // eax
  unsigned int v43; // eax
  __int64 v44; // rax
  __int64 v45; // r11
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // r11
  __int64 v49; // r8
  unsigned int v50; // ecx
  __int64 v51; // rcx
  __int64 v52; // r11
  struct RecoveryUnit *v53; // rcx
  BUF *v54; // rdx
  char v55; // al
  unsigned __int16 v56; // bx
  __int64 v57; // rax
  __int64 v58; // r11
  __int64 v59; // rcx
  unsigned int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // r11
  unsigned __int8 *v63; // rsi
  char v64; // al
  __int16 v65; // r11
  int v66; // eax
  int v67; // rax^4
  int v68; // eax
  __int64 v69; // r14
  unsigned __int8 *v70; // r8
  unsigned __int8 v71; // dl
  __int16 v72; // dx
  __int16 v73; // cx
  unsigned int v74; // ecx
  __int64 v75; // rax
  unsigned __int8 *v76; // rax
  __int16 v77; // cx
  PageComprInfoCache *v78; // rcx
  unsigned __int16 v79; // ax
  int v80; // eax
  int v81; // eax
  int v82; // ecx
  int v83; // edi
  unsigned __int16 v84; // cx
  int v85; // ecx
  BUF *v86; // rcx
  __int64 v87; // rax
  __int64 v88; // r11
  __int16 v89; // bx
  unsigned int v90; // edx
  unsigned __int16 *v91; // rdi
  unsigned __int16 v92; // r8
  __int64 v93; // rax
  __int64 v94; // rax
  unsigned int v95; // r10d
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  _BYTE *v100; // rax
  unsigned int v101; // ebx
  unsigned __int16 v102; // r9
  struct RecVersioningInfo *VersioningInfo; // rax
  int v104; // r8d
  __int64 v105; // r9
  __int64 v106; // rdx
  __int16 v107; // ax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  char v112; // cl
  bool v113; // zf
  FixedVarRecord *v114; // rbx
  char *v115; // r8
  __int64 v116; // rdx
  char v117; // al
  unsigned __int16 *v118; // rsi
  unsigned __int16 v119; // cx
  __int64 v120; // rax
  __int64 v121; // rax
  unsigned int v122; // r8d
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // r8
  __int64 v128; // rdx
  __int64 v129; // rax
  unsigned int v130; // edi
  unsigned int v131; // ecx
  unsigned __int16 v132; // cx
  __int16 v133; // ax
  unsigned __int16 v134; // ax
  struct RecVersioningInfo *v135; // rax
  int v136; // r8d
  __int64 v137; // r9
  __int64 v138; // rdx
  __int16 v139; // ax
  unsigned __int64 v140; // r8
  int v141; // ecx
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  unsigned int v146; // ecx
  char v147; // dl
  bool v148; // zf
  unsigned int v149; // edx
  unsigned __int16 *v150; // rsi
  unsigned __int16 v151; // r8
  __int64 v152; // rax
  __int64 v153; // rax
  unsigned int v154; // r10d
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  _BYTE *v159; // rax
  unsigned int v160; // edi
  unsigned __int16 v161; // r9
  struct RecVersioningInfo *v162; // rax
  int v163; // r8d
  __int64 v164; // r9
  __int64 v165; // rdx
  __int16 v166; // ax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rax
  char v171; // cl
  bool v172; // zf
  const struct Record *v173; // r8
  char *v174; // r8
  __int64 v175; // rdx
  char v176; // al
  unsigned __int16 *v177; // rsi
  unsigned __int16 v178; // cx
  __int64 v179; // rax
  __int64 v180; // rax
  unsigned int v181; // r8d
  __int64 v182; // rax
  __int64 v183; // rax
  __int64 v184; // rax
  __int64 v185; // rax
  char *v186; // rdx
  __int64 v187; // rax
  unsigned int v188; // edi
  unsigned int v189; // ecx
  unsigned __int16 v190; // cx
  __int16 v191; // ax
  unsigned __int16 v192; // ax
  struct RecVersioningInfo *v193; // rax
  int v194; // r8d
  __int64 v195; // r9
  __int64 v196; // rdx
  __int16 v197; // ax
  unsigned __int64 v198; // r8
  int v199; // ecx
  __int64 v200; // rax
  __int64 v201; // rax
  __int64 v202; // rax
  __int64 v203; // rax
  char v204; // cl
  int v205; // ebx
  const struct RecoveryUnit *v206; // rcx
  __int64 v207; // r11
  _BYTE *v208; // r8
  __int16 v209; // r9
  __int16 v210; // cx
  __int16 v211; // dx
  __int64 v212; // r8
  _BYTE *v213; // rax
  _BYTE *v214; // r8
  __int16 v215; // r9
  __int16 v216; // cx
  __int16 v217; // dx
  __int64 v218; // r8
  unsigned int v219; // ecx
  _BYTE *v220; // rax
  __int64 v221; // r11
  char v222; // al
  __int64 v223; // xmm1_8
  __int16 v224; // r11
  struct BUF *v225; // rdx
  __int64 v226; // rcx
  __int64 v227; // r11
  char v228; // [rsp+40h] [rbp-C0h]
  int v229; // [rsp+44h] [rbp-BCh]
  const struct LSN *v231; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v232; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v233; // [rsp+60h] [rbp-A0h]
  __int64 v234; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v235; // [rsp+70h] [rbp-90h]
  __int64 v236; // [rsp+78h] [rbp-88h] BYREF
  __int16 v237; // [rsp+80h] [rbp-80h]
  int v238; // [rsp+88h] [rbp-78h] BYREF
  __int16 v239; // [rsp+8Ch] [rbp-74h]
  int v240; // [rsp+90h] [rbp-70h] BYREF
  __int16 v241; // [rsp+94h] [rbp-6Ch]
  int v242; // [rsp+98h] [rbp-68h] BYREF
  __int16 v243; // [rsp+9Ch] [rbp-64h]
  __int64 v244; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v245; // [rsp+A8h] [rbp-58h]
  int v246; // [rsp+B0h] [rbp-50h]
  __int16 v247; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v248; // [rsp+BAh] [rbp-46h] BYREF
  int v249; // [rsp+BCh] [rbp-44h]
  _BYTE *v250; // [rsp+C0h] [rbp-40h]
  _OWORD *v251; // [rsp+C8h] [rbp-38h]
  _BYTE v252[24]; // [rsp+D0h] [rbp-30h]
  int v253; // [rsp+E8h] [rbp-18h]
  int v254; // [rsp+ECh] [rbp-14h]
  _OWORD v255[7]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v256; // [rsp+160h] [rbp+60h]
  __int64 v257; // [rsp+168h] [rbp+68h] BYREF
  __int16 v258; // [rsp+170h] [rbp+70h]
  _BYTE v259[2]; // [rsp+180h] [rbp+80h] BYREF
  __int16 v260; // [rsp+182h] [rbp+82h]
  __int64 v261; // [rsp+184h] [rbp+84h]
  __int16 v262; // [rsp+18Ch] [rbp+8Ch]
  int v263; // [rsp+190h] [rbp+90h]
  __int16 v264; // [rsp+194h] [rbp+94h]
  char v265; // [rsp+196h] [rbp+96h]
  char v266; // [rsp+197h] [rbp+97h]
  unsigned __int64 v267; // [rsp+1B0h] [rbp+B0h]
  int v268; // [rsp+1B8h] [rbp+B8h]
  __int16 v269; // [rsp+1BCh] [rbp+BCh]
  unsigned __int16 v270; // [rsp+1BEh] [rbp+BEh]
  _WORD v271[64]; // [rsp+1C0h] [rbp+C0h]
  unsigned int v272[6]; // [rsp+240h] [rbp+140h] BYREF
  void *v273[5]; // [rsp+258h] [rbp+158h] BYREF

  v6 = *this;
  v7 = a3;
  v231 = a4;
  v229 = a3;
  v247 = -1;
  v250 = 0;
  v249 = 0;
  *(_QWORD *)&v252[6] = 0;
  *(_QWORD *)&v252[16] = 0;
  v251 = 0;
  v10 = BPool::PrepareToDirty(qword_10317B628, v6, 1, 0);
  v11 = 2;
  *(_WORD *)(v10 + 4) &= 0xEDFFu;
  *(_DWORD *)(v10 + 64) = 1;
  v12 = *this;
  if ( *((_WORD *)*this + 22) != 2 )
  {
    v24 = *((_QWORD *)v12 + 18);
    if ( !v24 )
    {
      BUF::FixupPru(*this);
      v24 = *(_QWORD *)(v25 + 144);
      v12 = *this;
    }
    v26 = *(_QWORD *)(v24 + 1712);
    if ( (*(_BYTE *)(v26 + 60) & 1) == 0 || *(_QWORD *)(v26 + 640) )
      goto LABEL_33;
    v27 = (RecoveryUnit *)*((_QWORD *)v12 + 18);
    if ( !v27 )
    {
      BUF::FixupPru(v12);
      v27 = *(RecoveryUnit **)(v28 + 144);
    }
    if ( RecoveryUnit::IsBackupAllowedOnRbIoDb(v27) )
    {
LABEL_33:
      v29 = *((_QWORD *)*this + 18);
      if ( !v29 )
      {
        BUF::FixupPru(*this);
        v29 = *(_QWORD *)(v30 + 144);
      }
      if ( (*(_BYTE *)(v29 + 7376) & 0x20) == 0 )
      {
        v31 = *(_QWORD *)*this;
        if ( !*(_WORD *)(v31 + 36) )
          goto LABEL_64;
        v32 = *(_BYTE *)(v31 + 1);
        if ( v32 == 11 )
        {
          if ( *(_DWORD *)(v31 + 24) == 99 )
          {
LABEL_37:
            v238 = *(_DWORD *)(v31 + 32);
            v239 = *(_WORD *)(v31 + 36);
            if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v238, v9) )
            {
              PageHeader::GetIcxLsn(v31, &v232);
              v33 = v233;
LABEL_39:
              v34 = *this;
              v35 = *((_QWORD *)*this + 18);
              if ( !v35 )
              {
                BUF::FixupPru(*this);
                v35 = *((_QWORD *)v34 + 18);
              }
              FCB = FileMgr::GetFCB(*(_QWORD *)(v35 + 1696), *((unsigned __int16 *)v34 + 58), 0);
              v37 = *this;
              v38 = FCB;
              v39 = *this;
              v40 = *((_QWORD *)*this + 18);
              if ( !v40 )
              {
                BUF::FixupPru(*this);
                v40 = *(_QWORD *)(v41 + 144);
                v37 = *this;
                v39 = *this;
              }
              if ( !*(_DWORD *)(*(_QWORD *)(v40 + 1960) + 88LL) )
              {
                v42 = *(_DWORD *)(v38 + 304);
                if ( v42 <= (unsigned int)v232 )
                {
                  if ( v42 != (_DWORD)v232 )
                    goto LABEL_53;
                  v43 = *(_DWORD *)(v38 + 308);
                  if ( v43 <= HIDWORD(v232) && (v43 != HIDWORD(v232) || *(_WORD *)(v38 + 312) <= v33) )
                    goto LABEL_53;
                }
              }
              v44 = *((_QWORD *)v37 + 18);
              if ( !v44 )
              {
                BUF::FixupPru(v37);
                v44 = *(_QWORD *)(v45 + 144);
                v37 = *this;
                v39 = *this;
              }
              v46 = *(_QWORD *)(v44 + 1712);
              if ( (*(_BYTE *)(v46 + 60) & 1) == 0 || *(_QWORD *)(v46 + 640) )
              {
                v53 = (struct RecoveryUnit *)*((_QWORD *)v39 + 18);
                v54 = v39;
                if ( !v53 )
                {
                  BUF::FixupPru(v39);
                  v54 = *this;
                  v53 = (struct RecoveryUnit *)*((_QWORD *)v39 + 18);
                }
                PageRef::SetDiffMapChangeBit(v53, (const struct PageId *)(*(_QWORD *)v54 + 32LL));
              }
              else
              {
LABEL_53:
                v47 = *((_QWORD *)v37 + 18);
                if ( !v47 )
                {
                  BUF::FixupPru(v37);
                  v47 = *(_QWORD *)(v48 + 144);
                  v37 = *this;
                }
                if ( *(_DWORD *)(*(_QWORD *)(v47 + 1960) + 272LL) )
                {
                  v49 = *(_QWORD *)v37;
                  v50 = *(_DWORD *)(*(_QWORD *)v37 + 32LL) & 0xFFFFFFF8;
                  v9 = v50 / 0x7CD00;
                  if ( v50 != 511232 * (_DWORD)v9 )
                  {
                    v51 = *((_QWORD *)v37 + 18);
                    if ( !v51 )
                    {
                      BUF::FixupPru(v37);
                      v51 = *(_QWORD *)(v52 + 144);
                      v49 = *(_QWORD *)*this;
                    }
                    BackupManager::MarkExtentInBackupBitmapList(
                      *(BackupManager **)(v51 + 1960),
                      (const struct PageId *)(v49 + 32));
                  }
                }
              }
              v7 = v229;
              goto LABEL_2;
            }
LABEL_64:
            v33 = *(_WORD *)(v31 + 48);
            v232 = *(_QWORD *)(v31 + 40);
            v233 = v33;
            goto LABEL_39;
          }
        }
        else if ( v32 == 8 )
        {
LABEL_63:
          if ( *(_DWORD *)(v31 + 24) != 99 )
            goto LABEL_64;
          goto LABEL_37;
        }
        if ( v32 != 9 )
          goto LABEL_64;
        goto LABEL_63;
      }
    }
  }
LABEL_2:
  v13 = *(_QWORD *)*this;
  if ( (*(_WORD *)(v13 + 4) & 0x2000) == 0 )
    goto LABEL_3;
  if ( !*(_WORD *)(v13 + 36) )
    goto LABEL_86;
  v55 = *(_BYTE *)(v13 + 1);
  if ( v55 == 11 )
  {
    if ( *(_DWORD *)(v13 + 24) == 99 )
      goto LABEL_71;
    goto LABEL_84;
  }
  if ( v55 != 8 )
  {
LABEL_84:
    if ( v55 != 9 )
      goto LABEL_86;
  }
  if ( *(_DWORD *)(v13 + 24) != 99 )
    goto LABEL_86;
LABEL_71:
  v240 = *(_DWORD *)(v13 + 32);
  v241 = *(_WORD *)(v13 + 36);
  if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v240, v9) )
  {
LABEL_86:
    v56 = *(_WORD *)(v13 + 48);
    v234 = *(_QWORD *)(v13 + 40);
    v235 = v56;
    goto LABEL_73;
  }
  PageHeader::GetIcxLsn(v13, &v234);
  v56 = v235;
LABEL_73:
  v57 = *((_QWORD *)*this + 18);
  if ( !v57 )
  {
    BUF::FixupPru(*this);
    v57 = *(_QWORD *)(v58 + 144);
  }
  v59 = *(_QWORD *)(*(_QWORD *)(v57 + 1712) + 704LL);
  if ( (*(_WORD *)(v59 + 10) != 2 || (_DWORD)v234) && (unsigned int)v234 <= *(_DWORD *)v59 )
  {
    if ( (_DWORD)v234 != *(_DWORD *)v59
      || (v60 = *(_DWORD *)(v59 + 4), HIDWORD(v234) <= v60) && (HIDWORD(v234) != v60 || v56 <= *(_WORD *)(v59 + 8)) )
    {
      PageRef::RemoveOldVersionInfo((PageRef *)this, v9, (const struct AllocUnitId *)&x_SYSALLOCPGAllocationUnitId);
    }
  }
LABEL_3:
  if ( a6 )
  {
    if ( (qword_10317B028 & 0x1000000000LL) != 0
      || (v9 = SystemThread_TlsIndex,
          (v14 = *(_QWORD *)(SystemThread_TlsOffset
                           + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0)
      && (v15 = **(struct CSessionTraceFlags ***)(v14 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v15, 0x2564u) )
    {
      v61 = *((_QWORD *)*this + 18);
      if ( !v61 )
      {
        BUF::FixupPru(*this);
        v61 = *(_QWORD *)(v62 + 144);
      }
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(v61 + 1736) + 360LL))(*(_QWORD *)(v61 + 1736)) )
      {
        v229 = 0;
        v7 = 0;
        log_unlocalized_systemmetadata(L"%ls", L"Non-logged log file grow for repair purpose.");
      }
    }
  }
  v254 = 0;
  v16 = 9;
  if ( *(char *)(v10 + 2) >= 0 )
  {
    v17 = 0;
    goto LABEL_9;
  }
  v63 = (unsigned __int8 *)(v10 + 96);
  _mm_prefetch((const char *)(v10 + 96), 0);
  if ( !v247 || (v17 = v251) == 0 )
  {
    v17 = v255;
    v256 = 0;
    v255[1] = 0xFFFFu;
    memset(&v255[2], 0, 80);
    v255[0] = 0;
  }
  if ( !*(_WORD *)(v10 + 36) )
    goto LABEL_107;
  v64 = *(_BYTE *)(v10 + 1);
  if ( v64 == 11 )
  {
    if ( *(_DWORD *)(v10 + 24) == 99 )
      goto LABEL_98;
    goto LABEL_105;
  }
  if ( v64 != 8 )
  {
LABEL_105:
    if ( v64 != 9 )
      goto LABEL_107;
  }
  if ( *(_DWORD *)(v10 + 24) != 99 )
    goto LABEL_107;
LABEL_98:
  v242 = *(_DWORD *)(v10 + 32);
  v243 = *(_WORD *)(v10 + 36);
  if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v242, v9) )
  {
LABEL_107:
    v65 = *(_WORD *)(v10 + 48);
    v236 = *(_QWORD *)(v10 + 40);
    v237 = v65;
    goto LABEL_100;
  }
  PageHeader::GetIcxLsn(v10, &v236);
  v65 = v237;
LABEL_100:
  v66 = v236;
  *(_QWORD *)v17 = v63;
  *((_DWORD *)v17 + 24) = v66;
  v67 = HIDWORD(v236);
  *((_WORD *)v17 + 52) = v65;
  *((_DWORD *)v17 + 25) = v67;
  *((_DWORD *)v17 + 27) = *(_DWORD *)(v10 + 32);
  *((_WORD *)v17 + 56) = *(_WORD *)(v10 + 36);
  *((_WORD *)v17 + 57) = 0;
  v68 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v63);
  v69 = word_102883984[3 * *v63];
  *((_WORD *)v17 + 8) = -1;
  *((_QWORD *)v17 + 3) = 0;
  *((_DWORD *)v17 + 5) = 0;
  *(_QWORD *)((char *)v17 + 46) = 0;
  *((_QWORD *)v17 + 7) = 0;
  *((_QWORD *)v17 + 4) = 0;
  *((_QWORD *)v17 + 9) = 0;
  *((_QWORD *)v17 + 10) = 0;
  *((_WORD *)v17 + 44) = 0;
  v246 = v68;
  if ( (**(_BYTE **)v17 & 2) != 0 )
  {
    v70 = &v63[v69];
    if ( (v63[v69] & 1) != 0 )
    {
      *((_WORD *)v17 + 8) = 1;
      *((_QWORD *)v17 + 3) = v70;
      v71 = *v70;
      switch ( *v70 & 0x1C )
      {
        case 0:
        case 0xC:
        case 0x10:
        case 0x14:
        case 0x18:
        case 0x1C:
          if ( (v70[1] & 0x80u) != 0 )
          {
            v79 = *(_WORD *)(v70 + 1);
            v72 = 3;
            *((_WORD *)v17 + 9) = v79;
            v73 = HIBYTE(v79) | ((v79 & 0x7F) << 8);
          }
          else
          {
            v72 = 2;
            v73 = v70[1];
          }
          *((_WORD *)v17 + 9) = v73;
          *((_WORD *)v17 + 20) = v72;
          v74 = *((unsigned __int16 *)v17 + 9);
          *((_WORD *)v17 + 22) = v72 + ((v74 + 1) >> 1);
          if ( v74 > 0x1E )
            *((_WORD *)v17 + 21) = (int)(v74 - 1) / 30;
          else
            *((_WORD *)v17 + 21) = 0;
          *((_DWORD *)v17 + 5) = 0;
          *((_DWORD *)v17 + 16) = 0;
          *((_QWORD *)v17 + 7) = 0;
          *((_QWORD *)v17 + 4) = 0;
          break;
        case 1:
        case 2:
        case 3:
        case 5:
        case 6:
        case 7:
        case 9:
        case 0xA:
        case 0xB:
        case 0xD:
        case 0xE:
        case 0xF:
        case 0x11:
        case 0x12:
        case 0x13:
        case 0x15:
        case 0x16:
        case 0x17:
        case 0x19:
        case 0x1A:
        case 0x1B:
          utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
          *((_QWORD *)v17 + 7) = 0;
          *((_QWORD *)v17 + 4) = 0;
          break;
        case 4:
          if ( (v71 & 0x1C) != 4 || (v80 = 1, (v71 & 2) == 0) )
            v80 = 0;
          if ( v80 )
          {
            *((_DWORD *)v17 + 16) = 0;
            v81 = 1;
            v82 = 15;
          }
          else
          {
            v81 = 0;
            v82 = 1;
          }
          *((_QWORD *)v17 + 5) = 0;
          *((_WORD *)v17 + 9) = 0;
          *((_QWORD *)v17 + 6) = 0;
          *((_QWORD *)v17 + 4) = 0;
          *((_QWORD *)v17 + 7) = 0;
          *((_QWORD *)v17 + 3) = v70;
          *((_DWORD *)v17 + 5) = v82;
          *((_DWORD *)v17 + 16) = v81;
          *((_QWORD *)v17 + 7) = 0;
          *((_QWORD *)v17 + 4) = 0;
          break;
        case 8:
          *((_QWORD *)v17 + 7) = 0;
          *((_QWORD *)v17 + 7) = 0;
          *((_QWORD *)v17 + 5) = 0;
          *((_WORD *)v17 + 9) = 0;
          *((_QWORD *)v17 + 6) = 0;
          *((_QWORD *)v17 + 4) = 0;
          *((_QWORD *)v17 + 3) = v70;
          *((_DWORD *)v17 + 5) = 9;
          *((_DWORD *)v17 + 16) = 0;
          *((_QWORD *)v17 + 4) = 0;
          break;
      }
    }
    else
    {
      *((_WORD *)v17 + 8) = 0;
      v83 = 0;
      *((_QWORD *)v17 + 3) = v70;
      *((_DWORD *)v17 + 5) = 0;
      *(_DWORD *)((char *)v17 + 54) = 0;
      switch ( *v70 & 0xE )
      {
        case 0:
        case 2:
        case 8:
        case 0xC:
          v83 = *((unsigned __int16 *)v70 + 1);
          if ( (unsigned int)(v83 - 1) > 0x1F9D )
            RaiseInconsistencyError(&v63[v69], 6);
          break;
        case 1:
        case 3:
        case 5:
        case 7:
        case 9:
        case 0xB:
        case 0xD:
          utassert_fail(
            1u,
            "FALSE",
            "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
            294,
            "Invalid switch value");
          break;
        case 4:
          v83 = 9;
          break;
        case 6:
        case 0xA:
          break;
        case 0xE:
          v83 = 1;
          break;
      }
      *((_DWORD *)v17 + 8) = v83;
      *(_QWORD *)((char *)v17 + 46) = 0;
    }
  }
  if ( (**(_BYTE **)v17 & 4) != 0 )
  {
    if ( HIWORD(v246) )
      v75 = *(unsigned __int16 *)&v63[2 * SHIWORD(v246) + 1];
    else
      v75 = v69;
    v76 = &v63[v75];
    *((_QWORD *)v17 + 9) = v76;
    v77 = *(_WORD *)v76 + 1;
    *((_QWORD *)v17 + 10) = v76 + 2;
    *((_WORD *)v17 + 44) = 2 * v77;
  }
  v78 = (PageComprInfoCache *)*((_QWORD *)v17 + 1);
  if ( v78 )
    PageComprInfoCache::Init(v78, (const struct PageComprInfo *)v17);
  v7 = v229;
  v16 = 9;
LABEL_9:
  v18 = *(unsigned __int16 *)(v10 + 14);
  v19 = (unsigned __int8 *)(v10 + *(unsigned __int16 *)(v10 + 8190));
  v113 = (*v19 & 1) == 0;
  v250 = v19;
  if ( v113 )
  {
    v247 = 0;
    v249 = 0;
    *(_DWORD *)&v252[14] = 0;
    v20 = *v19 & 0xE;
    switch ( *v19 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v18 = *((unsigned __int16 *)v19 + 1);
        if ( (unsigned int)(v18 - 1) > 0x1F9D )
          RaiseInconsistencyError(v19, 6);
        break;
      case 1:
      case 3:
      case 5:
      case 7:
      case 9:
      case 0xB:
      case 0xD:
        utassert_fail(
          1u,
          "FALSE",
          "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
          294,
          "Invalid switch value");
        break;
      case 4:
        v18 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v18 = 1;
        break;
    }
    LODWORD(v251) = v18;
    *(_QWORD *)&v252[6] = v10 + 0x2000;
  }
  else
  {
    v247 = 1;
    v20 = *v19;
    switch ( *v19 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( (v19[1] & 0x80u) != 0 )
        {
          v84 = HIBYTE(*(_WORD *)(v19 + 1)) | ((*(_WORD *)(v19 + 1) & 0x7F) << 8);
          *(_WORD *)v252 = 3;
          v11 = 3;
          v248 = v84;
        }
        else
        {
          v84 = v19[1];
          v248 = v84;
          *(_WORD *)v252 = 2;
        }
        *(_WORD *)&v252[4] = v11 + ((unsigned __int16)(v84 + 1) >> 1);
        if ( v84 > 0x1Eu )
        {
          v85 = v84 - 1;
          v249 = 0;
          v253 = 0;
          v20 = (unsigned int)(v85 / 30);
          *(_WORD *)&v252[2] = v85 / 30;
        }
        else
        {
          *(_WORD *)&v252[2] = 0;
          v249 = 0;
          v253 = 0;
        }
        break;
      case 1:
      case 2:
      case 3:
      case 5:
      case 6:
      case 7:
      case 9:
      case 0xA:
      case 0xB:
      case 0xD:
      case 0xE:
      case 0xF:
      case 0x11:
      case 0x12:
      case 0x13:
      case 0x15:
      case 0x16:
      case 0x17:
      case 0x19:
      case 0x1A:
      case 0x1B:
        utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
        break;
      case 4:
        if ( (v20 & 0x1C) == 4 && (v20 & 2) != 0 )
        {
          *(_QWORD *)v252 = 0;
          v248 = 0;
          *(_QWORD *)&v252[8] = 0;
          v249 = 15;
          v253 = 1;
        }
        else
        {
          *(_QWORD *)v252 = 0;
          v248 = 0;
          *(_QWORD *)&v252[8] = 0;
          v249 = 1;
          v253 = 0;
        }
        break;
      case 8:
        *(_QWORD *)v252 = 0;
        v248 = 0;
        *(_QWORD *)&v252[8] = 0;
        v249 = 9;
        v253 = 0;
        break;
    }
    v251 = v17;
    *(_QWORD *)&v252[16] = v10 + 0x2000;
  }
  if ( !v7 )
  {
    if ( !*(_WORD *)(v10 + 36) )
      goto LABEL_577;
    v222 = *(_BYTE *)(v10 + 1);
    if ( v222 == 11 )
    {
      if ( *(_DWORD *)(v10 + 24) == 99 )
      {
LABEL_571:
        LODWORD(v231) = *(_DWORD *)(v10 + 32);
        WORD2(v231) = *(_WORD *)(v10 + 36);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v231, v20) )
        {
          PageHeader::GetIcxLsn(v10, &v244);
          v223 = v244;
          v224 = v245;
LABEL_573:
          v257 = v223;
          v258 = v224;
          goto LABEL_18;
        }
LABEL_577:
        v223 = *(_QWORD *)(v10 + 40);
        v224 = *(_WORD *)(v10 + 48);
        v244 = v223;
        v245 = v224;
        goto LABEL_573;
      }
    }
    else if ( v222 == 8 )
    {
LABEL_576:
      if ( *(_DWORD *)(v10 + 24) != 99 )
        goto LABEL_577;
      goto LABEL_571;
    }
    if ( v222 != 9 )
      goto LABEL_577;
    goto LABEL_576;
  }
  v21 = *this;
  if ( *((_WORD *)*this + 22) == 2 )
  {
    GetNextNonLoggedTempDbLsn((struct LSN *)&v257);
    v22 = *this;
    v23 = *((_QWORD *)*this + 18);
    if ( !v23 )
    {
      BUF::FixupPru(*this);
      v22 = *this;
      v23 = *(_QWORD *)(v221 + 144);
    }
    DirtyPageMgr::PreNonLoggedDirty(*(DirtyPageMgr **)(v23 + 1880), v22, 0);
    goto LABEL_18;
  }
  v86 = *this;
  v263 = 0;
  v264 = 0;
  v270 = 0;
  if ( a5 || *(_WORD *)(v10 + 36) != 2 )
    goto LABEL_163;
  v87 = *((_QWORD *)v21 + 18);
  if ( !v87 )
  {
    BUF::FixupPru(v86);
    v87 = *(_QWORD *)(v88 + 144);
    v86 = *this;
  }
  v228 = 1;
  if ( !*(_QWORD *)(*(_QWORD *)(v87 + 1736) + 3208LL) )
LABEL_163:
    v228 = 0;
  v265 = 16;
  v261 = 0;
  v262 = 0;
  v89 = *((_WORD *)v86 + 49);
  v266 = PageLog::MapContext(v10, 0, v19);
  PageLog::FillPageInfo(
    (PageLog *)v259,
    (const struct AllocUnitId *)&x_SYSALLOCPGAllocationUnitId,
    (const struct PageHeader *)v10,
    0,
    0,
    (v89 & 8) != 0);
  v90 = v249;
  v267 = NullRowsetId;
  v269 = 0;
  v268 = 0;
  if ( v247 )
  {
    if ( !v249 )
    {
      CDRecord::Resize((CDRecord *)&v248);
      v90 = v249;
    }
    if ( v90 < 9 )
    {
      if ( (*v250 & 0x1C) != 0 )
      {
        v113 = (*v250 & 0x1C) == 12;
LABEL_241:
        if ( !v113 )
          goto LABEL_243;
      }
LABEL_242:
      LOWORD(v90) = 9;
    }
  }
  else
  {
    if ( !v249 )
    {
      v90 = (unsigned int)v251;
      v248 = 0;
      HIDWORD(v251) = (_DWORD)v251;
      if ( (*v250 & 0x10) != 0 )
      {
        v90 = (((unsigned int)*(unsigned __int16 *)&v250[(unsigned int)v251] + 7) >> 3) + (_DWORD)v251 + 2;
        HIDWORD(v251) = v90;
      }
      if ( (*v250 & 0x20) != 0 )
      {
        v91 = (unsigned __int16 *)&v250[v90];
        v92 = *v91;
        *(_WORD *)&v252[4] = v92;
        if ( !v92 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v93 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v93 )
            {
              v94 = *(_QWORD *)(v93 + 96);
              if ( v94 )
              {
                if ( *(_BYTE *)(v94 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v250, 3);
          v92 = *(_WORD *)&v252[4];
        }
        v95 = HIDWORD(v251) + 2 + 2 * v92;
        *(_DWORD *)v252 = v95;
        if ( v95 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v96 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v96 )
            {
              v97 = *(_QWORD *)(v96 + 96);
              if ( v97 )
              {
                if ( *(_BYTE *)(v97 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v250, 4);
          v92 = *(_WORD *)&v252[4];
          v95 = *(_DWORD *)v252;
        }
        v90 = v91[v92] & 0x7FFF;
        v249 = v90;
        if ( v95 > v90 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v98 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v98 )
            {
              v99 = *(_QWORD *)(v98 + 96);
              if ( v99 )
              {
                if ( *(_BYTE *)(v99 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v250, 4);
          v92 = *(_WORD *)&v252[4];
          v95 = *(_DWORD *)v252;
          v90 = v249;
        }
        while ( 1 )
        {
          if ( (v91[v92] & 0x8000u) == 0 )
            goto LABEL_209;
          v100 = &v250[HIDWORD(v251)];
          if ( v92 == 1 )
          {
            v101 = v95;
          }
          else
          {
            v101 = *(_WORD *)&v100[2 * v92 - 2] & 0x7FFF;
            if ( v101 < v95 )
            {
LABEL_203:
              RaiseInconsistencyError(v250, 7);
              v92 = *(_WORD *)&v252[4];
              v95 = *(_DWORD *)v252;
              v90 = v249;
              goto LABEL_204;
            }
          }
          if ( (*(_WORD *)&v100[2 * v92] & 0x7FFFu) < v101 )
            goto LABEL_203;
LABEL_204:
          if ( v101 < v95 || v101 > v90 )
            goto LABEL_238;
          v102 = *(_WORD *)&v250[v101];
          if ( v102 == 5 )
          {
            v248 |= 2u;
            *(_WORD *)&v252[4] = v92 - 1;
            *(_WORD *)&v252[18] = v101;
            v208 = &v250[(unsigned __int16)v101];
            v209 = *((_WORD *)v208 + 1);
            if ( (v209 & 0x4000) != 0 )
              v210 = (v209 ^ *(_WORD *)&v252[20]) & 0x3800 ^ *(_WORD *)&v252[20];
            else
              v210 = *(_WORD *)&v252[20] & 0xC7FF;
            *(_WORD *)&v252[20] = v210;
            *(_WORD *)&v252[20] = v210 ^ (*((_WORD *)v208 + 1) ^ v210) & 0x7FF;
            goto LABEL_209;
          }
          if ( v102 >= 0x400u )
          {
            v248 |= 1u;
            v113 = v92-- == 1;
            *(_WORD *)&v252[4] = v92;
            if ( !v113 )
              continue;
          }
          goto LABEL_209;
        }
      }
      v249 = v90;
      *(_WORD *)&v252[4] = 0;
      *(_DWORD *)v252 = v90;
LABEL_209:
      if ( (*v250 & 0x40) != 0 )
      {
        *(_DWORD *)&v252[14] = v90;
        v249 = v90 + 14;
        VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v248);
        v104 = 0;
        v105 = HIDWORD(*(_QWORD *)VersioningInfo);
        v106 = HIWORD(*(_QWORD *)VersioningInfo);
        if ( (((__int16)v106 ^ ((unsigned int)(__int16)v106 >> 1)) & 0x2000) != 0 )
        {
          v107 = v106 & 0xDFFF;
          if ( (v106 & 0x4000) != 0 )
            v107 = v106 | 0x2000;
          LOWORD(v106) = v107;
        }
        if ( (_WORD)v106 == 0xFFFC )
          v104 = (unsigned __int16)v105 >> 5;
        v90 = v104 + v249;
        v249 += v104;
      }
      else
      {
        *(_DWORD *)&v252[14] = 0;
      }
      if ( *(_QWORD *)&v252[6] && *(_QWORD *)&v252[6] < (unsigned __int64)&v250[v90] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v108 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v108 )
          {
            v109 = *(_QWORD *)(v108 + 96);
            if ( v109 )
            {
              if ( *(_BYTE *)(v109 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v250, 18);
        v90 = v249;
      }
      if ( v90 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v110 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v110 )
          {
            v111 = *(_QWORD *)(v110 + 96);
            if ( v111 )
            {
              if ( *(_BYTE *)(v111 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v250, 5);
        v90 = v249;
      }
    }
LABEL_238:
    if ( v90 < 9 )
    {
      v112 = *v250 & 0xE;
      if ( v112 )
      {
        v113 = v112 == 12;
        goto LABEL_241;
      }
      goto LABEL_242;
    }
  }
LABEL_243:
  v271[v270++] = v90;
  v114 = (const struct Record *)((char *)a2 + 2);
  if ( !*(_WORD *)a2 )
  {
    if ( *((_DWORD *)a2 + 1) )
      goto LABEL_320;
    v115 = (char *)*((_QWORD *)a2 + 1);
    v116 = *((unsigned int *)a2 + 4);
    *(_WORD *)v114 = 0;
    *((_DWORD *)a2 + 5) = v116;
    v117 = *v115;
    if ( (*v115 & 0x10) != 0 )
    {
      LODWORD(v116) = (((unsigned int)*(unsigned __int16 *)&v115[v116] + 7) >> 3) + v116 + 2;
      *((_DWORD *)a2 + 5) = v116;
      v117 = *v115;
    }
    if ( (v117 & 0x20) == 0 )
    {
      *((_DWORD *)a2 + 1) = v116;
      *((_WORD *)a2 + 14) = 0;
      *((_DWORD *)a2 + 6) = v116;
      goto LABEL_291;
    }
    v118 = (unsigned __int16 *)&v115[(unsigned int)v116];
    v119 = *v118;
    *((_WORD *)a2 + 14) = *v118;
    if ( !v119 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v120 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v120 )
        {
          v121 = *(_QWORD *)(v120 + 96);
          if ( v121 )
          {
            if ( *(_BYTE *)(v121 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
              else
                ex_raise(34, 68, 21, 1003);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)a2 + 1), 3);
      v119 = *((_WORD *)a2 + 14);
      LODWORD(v116) = *((_DWORD *)a2 + 5);
    }
    v122 = v116 + 2 * (v119 + 1);
    *((_DWORD *)a2 + 6) = v122;
    if ( v122 > 0x1F9E )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v123 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v123 )
        {
          v124 = *(_QWORD *)(v123 + 96);
          if ( v124 )
          {
            if ( *(_BYTE *)(v124 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)a2 + 1), 4);
      v119 = *((_WORD *)a2 + 14);
      v122 = *((_DWORD *)a2 + 6);
    }
    LODWORD(v116) = v118[v119] & 0x7FFF;
    *((_DWORD *)a2 + 1) = v116;
    if ( v122 > (unsigned int)v116 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v125 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v125 )
        {
          v126 = *(_QWORD *)(v125 + 96);
          if ( v126 )
          {
            if ( *(_BYTE *)(v126 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*((_QWORD *)a2 + 1), 4);
      v119 = *((_WORD *)a2 + 14);
      LODWORD(v116) = *((_DWORD *)a2 + 1);
    }
    if ( (v118[v119] & 0x8000u) == 0 )
    {
LABEL_290:
      v115 = (char *)*((_QWORD *)a2 + 1);
      goto LABEL_291;
    }
    v127 = *((_QWORD *)a2 + 1);
    while ( 1 )
    {
      v128 = v127 + *((unsigned int *)a2 + 5);
      v129 = v119;
      if ( v119 == 1 )
      {
        v130 = *((_DWORD *)a2 + 6);
        v131 = v130;
      }
      else
      {
        v131 = *((_DWORD *)a2 + 6);
        v130 = *(_WORD *)(v128 + 2 * v129 - 2) & 0x7FFF;
        if ( v130 < v131 )
        {
LABEL_283:
          RaiseInconsistencyError(v127, 7);
          v131 = *((_DWORD *)a2 + 6);
          goto LABEL_284;
        }
      }
      if ( (*(_WORD *)(v128 + 2 * v129) & 0x7FFFu) < v130 )
        goto LABEL_283;
LABEL_284:
      if ( v130 < v131 )
        goto LABEL_320;
      LODWORD(v116) = *((_DWORD *)a2 + 1);
      if ( v130 > (unsigned int)v116 )
        goto LABEL_320;
      v127 = *((_QWORD *)a2 + 1);
      v132 = *(_WORD *)(v130 + v127);
      if ( v132 == 5 )
      {
        *(_WORD *)v114 |= 2u;
        --*((_WORD *)a2 + 14);
        v211 = *((_WORD *)a2 + 22) & 0xC7FF;
        *((_WORD *)a2 + 21) = v130;
        v212 = *((_QWORD *)a2 + 1) + (unsigned __int16)v130;
        if ( _bittest16((const signed __int16 *)(v212 + 2), 0xEu) )
          v211 |= *(_WORD *)(v212 + 2) & 0x3800;
        *((_WORD *)a2 + 22) = v211;
        *((_WORD *)a2 + 22) = v211 ^ (*(_WORD *)(v212 + 2) ^ v211) & 0x7FF;
        v115 = (char *)*((_QWORD *)a2 + 1);
        LODWORD(v116) = *((_DWORD *)a2 + 1);
LABEL_291:
        if ( (*v115 & 0x40) != 0 )
        {
          *(_DWORD *)((char *)a2 + 38) = v116;
          *((_DWORD *)a2 + 1) = v116 + 14;
          v135 = FixedVarRecord::FindVersioningInfo(v114);
          v136 = 0;
          v137 = HIDWORD(*(_QWORD *)v135);
          v138 = HIWORD(*(_QWORD *)v135);
          if ( (((__int16)v138 ^ ((unsigned int)(__int16)v138 >> 1)) & 0x2000) != 0 )
          {
            v139 = v138 & 0xDFFF;
            if ( (v138 & 0x4000) != 0 )
              v139 = v138 | 0x2000;
            LOWORD(v138) = v139;
          }
          if ( (_WORD)v138 == 0xFFFC )
            v136 = (unsigned __int16)v137 >> 5;
          *((_DWORD *)a2 + 1) += v136;
          LODWORD(v116) = *((_DWORD *)a2 + 1);
        }
        else
        {
          *(_DWORD *)((char *)a2 + 38) = 0;
        }
        v140 = *(_QWORD *)((char *)a2 + 30);
        v141 = v116;
        if ( v140 && v140 < *((_QWORD *)a2 + 1) + (unsigned __int64)(unsigned int)v116 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v142 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v142 )
            {
              v143 = *(_QWORD *)(v142 + 96);
              if ( v143 )
              {
                if ( *(_BYTE *)(v143 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)a2 + 1), 18);
          v141 = *((_DWORD *)a2 + 1);
        }
        if ( (unsigned int)(v141 - 1) > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v144 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v144 )
            {
              v145 = *(_QWORD *)(v144 + 96);
              if ( v145 )
              {
                if ( *(_BYTE *)(v145 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)a2 + 1), 5);
        }
LABEL_320:
        v146 = *((_DWORD *)a2 + 1);
        if ( v146 < 9 )
        {
          v147 = **((_BYTE **)a2 + 1) & 0xE;
          if ( v147 )
          {
            v148 = v147 == 12;
            goto LABEL_323;
          }
          goto LABEL_324;
        }
        goto LABEL_325;
      }
      if ( v132 >= 0x400u )
      {
        v133 = *((_WORD *)a2 + 14);
        *(_WORD *)v114 |= 1u;
        v134 = v133 - 1;
        *((_WORD *)a2 + 14) = v134;
        if ( v134 )
        {
          v119 = v134;
          if ( (v118[v134] & 0x8000u) != 0 )
            continue;
        }
      }
      goto LABEL_290;
    }
  }
  v146 = *((_DWORD *)a2 + 1);
  if ( !v146 )
  {
    CDRecord::Resize((const struct Record *)((char *)a2 + 2));
    v146 = *((_DWORD *)a2 + 1);
  }
  if ( v146 < 9 )
  {
    v213 = (_BYTE *)*((_QWORD *)a2 + 1);
    if ( (*v213 & 0x1C) == 0 )
      goto LABEL_324;
    v148 = (*v213 & 0x1C) == 12;
LABEL_323:
    if ( v148 )
LABEL_324:
      LOWORD(v146) = 9;
  }
LABEL_325:
  v271[v270++] = v146;
  v271[v270++] = 10;
  v271[v270] = 32 * a5;
  v149 = v249;
  ++v270;
  v260 = 62;
  v272[0] = 2 * v270 + 64;
  v273[0] = v259;
  if ( v247 )
  {
    if ( !v249 )
    {
      CDRecord::Resize((CDRecord *)&v248);
      v149 = v249;
    }
    if ( v149 < 9 )
    {
      if ( (*v250 & 0x1C) != 0 )
      {
        v172 = (*v250 & 0x1C) == 12;
LABEL_402:
        if ( !v172 )
          goto LABEL_404;
      }
LABEL_403:
      v149 = 9;
    }
  }
  else
  {
    if ( !v249 )
    {
      v149 = (unsigned int)v251;
      v248 = 0;
      HIDWORD(v251) = (_DWORD)v251;
      if ( (*v250 & 0x10) != 0 )
      {
        v149 = (((unsigned int)*(unsigned __int16 *)&v250[(unsigned int)v251] + 7) >> 3) + (_DWORD)v251 + 2;
        HIDWORD(v251) = v149;
      }
      if ( (*v250 & 0x20) != 0 )
      {
        v150 = (unsigned __int16 *)&v250[v149];
        v151 = *v150;
        *(_WORD *)&v252[4] = v151;
        if ( !v151 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v152 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v152 )
            {
              v153 = *(_QWORD *)(v152 + 96);
              if ( v153 )
              {
                if ( *(_BYTE *)(v153 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v250, 3);
          v151 = *(_WORD *)&v252[4];
        }
        v154 = HIDWORD(v251) + 2 + 2 * v151;
        *(_DWORD *)v252 = v154;
        if ( v154 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v155 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v155 )
            {
              v156 = *(_QWORD *)(v155 + 96);
              if ( v156 )
              {
                if ( *(_BYTE *)(v156 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v250, 4);
          v151 = *(_WORD *)&v252[4];
          v154 = *(_DWORD *)v252;
        }
        v149 = v150[v151] & 0x7FFF;
        v249 = v149;
        if ( v154 > v149 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v157 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v157 )
            {
              v158 = *(_QWORD *)(v157 + 96);
              if ( v158 )
              {
                if ( *(_BYTE *)(v158 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v250, 4);
          v151 = *(_WORD *)&v252[4];
          v154 = *(_DWORD *)v252;
          v149 = v249;
        }
        while ( 1 )
        {
          if ( (v150[v151] & 0x8000u) == 0 )
            goto LABEL_370;
          v159 = &v250[HIDWORD(v251)];
          if ( v151 == 1 )
          {
            v160 = v154;
          }
          else
          {
            v160 = *(_WORD *)&v159[2 * v151 - 2] & 0x7FFF;
            if ( v160 < v154 )
            {
LABEL_364:
              RaiseInconsistencyError(v250, 7);
              v151 = *(_WORD *)&v252[4];
              v154 = *(_DWORD *)v252;
              v149 = v249;
              goto LABEL_365;
            }
          }
          if ( (*(_WORD *)&v159[2 * v151] & 0x7FFFu) < v160 )
            goto LABEL_364;
LABEL_365:
          if ( v160 < v154 || v160 > v149 )
            goto LABEL_399;
          v161 = *(_WORD *)&v250[v160];
          if ( v161 == 5 )
          {
            v248 |= 2u;
            *(_WORD *)&v252[4] = v151 - 1;
            *(_WORD *)&v252[18] = v160;
            v214 = &v250[(unsigned __int16)v160];
            v215 = *((_WORD *)v214 + 1);
            if ( (v215 & 0x4000) != 0 )
              v216 = (v215 ^ *(_WORD *)&v252[20]) & 0x3800 ^ *(_WORD *)&v252[20];
            else
              v216 = *(_WORD *)&v252[20] & 0xC7FF;
            *(_WORD *)&v252[20] = v216;
            *(_WORD *)&v252[20] = v216 ^ (*((_WORD *)v214 + 1) ^ v216) & 0x7FF;
            goto LABEL_370;
          }
          if ( v161 >= 0x400u )
          {
            v248 |= 1u;
            v113 = v151-- == 1;
            *(_WORD *)&v252[4] = v151;
            if ( !v113 )
              continue;
          }
          goto LABEL_370;
        }
      }
      v249 = v149;
      *(_WORD *)&v252[4] = 0;
      *(_DWORD *)v252 = v149;
LABEL_370:
      if ( (*v250 & 0x40) != 0 )
      {
        *(_DWORD *)&v252[14] = v149;
        v249 = v149 + 14;
        v162 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v248);
        v163 = 0;
        v164 = HIDWORD(*(_QWORD *)v162);
        v165 = HIWORD(*(_QWORD *)v162);
        if ( (((__int16)v165 ^ ((unsigned int)(__int16)v165 >> 1)) & 0x2000) != 0 )
        {
          v166 = v165 & 0xDFFF;
          if ( (v165 & 0x4000) != 0 )
            v166 = v165 | 0x2000;
          LOWORD(v165) = v166;
        }
        if ( (_WORD)v165 == 0xFFFC )
          v163 = (unsigned __int16)v164 >> 5;
        v149 = v163 + v249;
        v249 += v163;
      }
      else
      {
        *(_DWORD *)&v252[14] = 0;
      }
      if ( *(_QWORD *)&v252[6] && *(_QWORD *)&v252[6] < (unsigned __int64)&v250[v149] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v167 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v167 )
          {
            v168 = *(_QWORD *)(v167 + 96);
            if ( v168 )
            {
              if ( *(_BYTE *)(v168 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v250, 18);
        v149 = v249;
      }
      if ( v149 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v169 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v169 )
          {
            v170 = *(_QWORD *)(v169 + 96);
            if ( v170 )
            {
              if ( *(_BYTE *)(v170 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v250, 5);
        v149 = v249;
      }
    }
LABEL_399:
    if ( v149 < 9 )
    {
      v171 = *v250 & 0xE;
      if ( v171 )
      {
        v172 = v171 == 12;
        goto LABEL_402;
      }
      goto LABEL_403;
    }
  }
LABEL_404:
  v173 = a2;
  v272[1] = v149;
  v273[1] = v250;
  if ( *(_WORD *)a2 )
  {
    v219 = *((_DWORD *)a2 + 1);
    if ( !v219 )
    {
      CDRecord::Resize(v114);
      v219 = *((_DWORD *)a2 + 1);
      v173 = a2;
    }
    if ( v219 >= 9 || (v220 = (_BYTE *)*((_QWORD *)a2 + 1), (*v220 & 0x1C) != 0) && (*v220 & 0x1C) != 0xC )
      v16 = v219;
  }
  else
  {
    if ( !*((_DWORD *)a2 + 1) )
    {
      v174 = (char *)*((_QWORD *)a2 + 1);
      v175 = *((unsigned int *)a2 + 4);
      *(_WORD *)v114 = 0;
      *((_DWORD *)a2 + 5) = v175;
      v176 = *v174;
      if ( (*v174 & 0x10) != 0 )
      {
        LODWORD(v175) = (((unsigned int)*(unsigned __int16 *)&v174[v175] + 7) >> 3) + v175 + 2;
        *((_DWORD *)a2 + 5) = v175;
        v176 = *v174;
      }
      if ( (v176 & 0x20) != 0 )
      {
        v177 = (unsigned __int16 *)&v174[(unsigned int)v175];
        v178 = *v177;
        *((_WORD *)a2 + 14) = *v177;
        if ( !v178 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v179 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v179 )
            {
              v180 = *(_QWORD *)(v179 + 96);
              if ( v180 )
              {
                if ( *(_BYTE *)(v180 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)a2 + 1), 3);
          v178 = *((_WORD *)a2 + 14);
          LODWORD(v175) = *((_DWORD *)a2 + 5);
        }
        v181 = v175 + 2 * (v178 + 1);
        *((_DWORD *)a2 + 6) = v181;
        if ( v181 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v182 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v182 )
            {
              v183 = *(_QWORD *)(v182 + 96);
              if ( v183 )
              {
                if ( *(_BYTE *)(v183 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)a2 + 1), 4);
          v178 = *((_WORD *)a2 + 14);
          v181 = *((_DWORD *)a2 + 6);
        }
        LODWORD(v175) = v177[v178] & 0x7FFF;
        *((_DWORD *)a2 + 1) = v175;
        if ( v181 > (unsigned int)v175 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v184 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v184 )
            {
              v185 = *(_QWORD *)(v184 + 96);
              if ( v185 )
              {
                if ( *(_BYTE *)(v185 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)a2 + 1), 4);
          v178 = *((_WORD *)a2 + 14);
          LODWORD(v175) = *((_DWORD *)a2 + 1);
        }
        if ( (v177[v178] & 0x8000u) != 0 )
        {
          v174 = (char *)*((_QWORD *)a2 + 1);
          while ( 1 )
          {
            v186 = &v174[*((unsigned int *)a2 + 5)];
            v187 = v178;
            if ( v178 == 1 )
            {
              v188 = *((_DWORD *)a2 + 6);
              v189 = v188;
            }
            else
            {
              v189 = *((_DWORD *)a2 + 6);
              v188 = *(_WORD *)&v186[2 * v187 - 2] & 0x7FFF;
              if ( v188 < v189 )
              {
LABEL_444:
                RaiseInconsistencyError(v174, 7);
                v189 = *((_DWORD *)a2 + 6);
                goto LABEL_445;
              }
            }
            if ( (*(_WORD *)&v186[2 * v187] & 0x7FFFu) < v188 )
              goto LABEL_444;
LABEL_445:
            if ( v188 < v189 )
              goto LABEL_480;
            LODWORD(v175) = *((_DWORD *)a2 + 1);
            if ( v188 > (unsigned int)v175 )
              goto LABEL_480;
            v174 = (char *)*((_QWORD *)a2 + 1);
            v190 = *(_WORD *)&v174[v188];
            if ( v190 == 5 )
            {
              *(_WORD *)v114 |= 2u;
              --*((_WORD *)a2 + 14);
              v217 = *((_WORD *)a2 + 22) & 0xC7FF;
              *((_WORD *)a2 + 21) = v188;
              v218 = *((_QWORD *)a2 + 1) + (unsigned __int16)v188;
              if ( _bittest16((const signed __int16 *)(v218 + 2), 0xEu) )
                v217 |= *(_WORD *)(v218 + 2) & 0x3800;
              *((_WORD *)a2 + 22) = v217;
              *((_WORD *)a2 + 22) = v217 ^ (*(_WORD *)(v218 + 2) ^ v217) & 0x7FF;
              LODWORD(v175) = *((_DWORD *)a2 + 1);
              break;
            }
            if ( v190 < 0x400u )
              break;
            v191 = *((_WORD *)a2 + 14);
            *(_WORD *)v114 |= 1u;
            v192 = v191 - 1;
            *((_WORD *)a2 + 14) = v192;
            if ( !v192 )
              break;
            v178 = v192;
            if ( (v177[v192] & 0x8000u) == 0 )
              goto LABEL_451;
          }
        }
        v174 = (char *)*((_QWORD *)a2 + 1);
      }
      else
      {
        *((_DWORD *)a2 + 1) = v175;
        *((_WORD *)a2 + 14) = 0;
        *((_DWORD *)a2 + 6) = v175;
      }
LABEL_451:
      if ( (*v174 & 0x40) != 0 )
      {
        *(_DWORD *)((char *)a2 + 38) = v175;
        *((_DWORD *)a2 + 1) = v175 + 14;
        v193 = FixedVarRecord::FindVersioningInfo(v114);
        v194 = 0;
        v195 = HIDWORD(*(_QWORD *)v193);
        v196 = HIWORD(*(_QWORD *)v193);
        if ( (((__int16)v196 ^ ((unsigned int)(__int16)v196 >> 1)) & 0x2000) != 0 )
        {
          v197 = v196 & 0xDFFF;
          if ( (v196 & 0x4000) != 0 )
            v197 = v196 | 0x2000;
          LOWORD(v196) = v197;
        }
        if ( (_WORD)v196 == 0xFFFC )
          v194 = (unsigned __int16)v195 >> 5;
        *((_DWORD *)a2 + 1) += v194;
        LODWORD(v175) = *((_DWORD *)a2 + 1);
      }
      else
      {
        *(_DWORD *)((char *)a2 + 38) = 0;
      }
      v198 = *(_QWORD *)((char *)a2 + 30);
      v199 = v175;
      if ( v198 && v198 < *((_QWORD *)a2 + 1) + (unsigned __int64)(unsigned int)v175 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v200 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v200 )
          {
            v201 = *(_QWORD *)(v200 + 96);
            if ( v201 )
            {
              if ( *(_BYTE *)(v201 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*((_QWORD *)a2 + 1), 18);
        v199 = *((_DWORD *)a2 + 1);
      }
      if ( (unsigned int)(v199 - 1) > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v202 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v202 )
          {
            v203 = *(_QWORD *)(v202 + 96);
            if ( v203 )
            {
              if ( *(_BYTE *)(v203 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(*((_QWORD *)a2 + 1), 5);
      }
LABEL_480:
      v173 = a2;
    }
    if ( *((_DWORD *)a2 + 1) >= 9u || (v204 = **((_BYTE **)a2 + 1) & 0xE) != 0 && v204 != 12 )
      v16 = *((_DWORD *)a2 + 1);
  }
  v273[2] = *((void **)v173 + 1);
  v273[3] = v231;
  v272[4] = 32 * a5;
  v273[4] = a6;
  v272[2] = v16;
  v272[3] = 10;
  if ( a5 || v228 )
    v205 = 5;
  else
    v205 = 0;
  v206 = (const struct RecoveryUnit *)*((_QWORD *)*this + 18);
  if ( !v206 )
  {
    BUF::FixupPru(*this);
    v206 = *(const struct RecoveryUnit **)(v207 + 144);
  }
  XDES::GenerateNonXactLogRec(v206, 5u, v272, (const void **)v273, (struct LSN *)&v257, 0, v205);
  v7 = v229;
LABEL_18:
  FHdrPage::ReplaceFileHeader((FHdrPage *)v10, a2);
  if ( *(_WORD *)(v10 + 48) != v258 || *(_QWORD *)(v10 + 40) != v257 )
  {
    *(_QWORD *)(v10 + 40) = v257;
    *(_WORD *)(v10 + 48) = v258;
    *(_WORD *)(v10 + 4) &= ~0x20u;
  }
  if ( !v7 )
  {
    v225 = *this;
    v226 = *((_QWORD *)*this + 18);
    if ( !v226 )
    {
      BUF::FixupPru(*this);
      v225 = *this;
      v226 = *(_QWORD *)(v227 + 144);
    }
    DirtyPageMgr::PreNonLoggedDirty(*(DirtyPageMgr **)(v226 + 1880), v225, 0);
  }
  BPool::Dirty(qword_10317B628, *this, 0, (struct LSN *)&v257);
  if ( (byte_10317AD49 & 2) != 0 )
    _InterlockedAnd((volatile signed __int32 *)*this + 25, 0xFFFFFFEF);
}

```

## disassembly

```asm
0x10055b190  mov     [rsp-8+arg_10], rbx
0x10055b195  push    rbp
0x10055b196  push    rsi
0x10055b197  push    rdi
0x10055b198  push    r12
0x10055b19a  push    r13
0x10055b19c  push    r14
0x10055b19e  push    r15
0x10055b1a0  lea     rbp, [rsp-190h]
0x10055b1a8  sub     rsp, 290h
0x10055b1af  mov     rax, cs:__security_cookie
0x10055b1b6  xor     rax, rsp
0x10055b1b9  mov     [rbp+1C0h+var_40], rax
0x10055b1c0  xor     edi, edi
0x10055b1c2  mov     [rsp+2C0h+var_278], rdx
0x10055b1c7  mov     rdx, [rcx]
0x10055b1ca  mov     esi, r8d
0x10055b1cd  mov     [rsp+2C0h+var_270], r9
0x10055b1d2  mov     r12, rcx
0x10055b1d5  mov     rcx, cs:qword_10317B628
0x10055b1dc  mov     eax, 0FFFFFFFFh
0x10055b1e1  mov     [rsp+2C0h+var_27C], r8d
0x10055b1e6  mov     ebx, 1
0x10055b1eb  mov     r8d, ebx
0x10055b1ee  mov     [rbp+1C0h+var_208], ax
0x10055b1f2  xor     r9d, r9d
0x10055b1f5  mov     [rbp+1C0h+var_200], rdi
0x10055b1f9  mov     [rbp+1C0h+var_204], edi
0x10055b1fc  mov     [rbp+1C0h+var_1F0+6], rdi
0x10055b200  mov     [rbp+1C0h+var_1E0], rdi
0x10055b204  mov     [rbp+1C0h+var_1F8], rdi
0x10055b208  call    ?PrepareToDirty@BPool@@QEAAPEAVPage@@PEAUBUF@@W4ChangeMode@1@_N@Z; BPool::PrepareToDirty(BUF *,BPool::ChangeMode,bool)
0x10055b20d  mov     r13, rax
0x10055b210  mov     r15d, 2
0x10055b216  mov     eax, 0EDFFh
0x10055b21b  and     [r13+4], ax
0x10055b220  mov     [r13+40h], ebx
0x10055b224  mov     r11, [r12]
0x10055b228  cmp     r15w, [r11+2Ch]
0x10055b22d  jnz     loc_1018F1F4D
0x10055b233  mov     rax, [r12]
0x10055b237  mov     r11, [rax]
0x10055b23a  mov     eax, 2000h
0x10055b23f  test    [r11+4], ax
0x10055b244  jnz     loc_1018F21F9
0x10055b24a  cmp     [rbp+1C0h+arg_28], 0
0x10055b252  jz      short loc_10055B299
0x10055b254  test    byte ptr cs:qword_10317B028+4, 10h
0x10055b25b  jnz     loc_1018F2311
0x10055b261  mov     r8, gs:58h
0x10055b26a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10055b271  mov     edx, [rax]
0x10055b273  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10055b27a  mov     ecx, [rax]
0x10055b27c  mov     rax, [r8+rdx*8]
0x10055b280  mov     rax, [rcx+rax]
0x10055b284  test    rax, rax
0x10055b287  jz      short loc_10055B299
0x10055b289  mov     rax, [rax+38h]
0x10055b28d  mov     rcx, [rax]
0x10055b290  test    rcx, rcx
0x10055b293  jnz     loc_1018F22FE
0x10055b299  xor     r9d, r9d
0x10055b29c  lea     r10, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x10055b2a3  mov     [rbp+1C0h+var_1D4], r9d
0x10055b2a7  lea     r11, ?szText@?8???$CompileOnDataType@$0A@$00_K@RbpDecode@@CAP6AX_N0HPEA_K1PEBVRbpColumnContextNew@@PEAE@ZW4RbpDataType@@W4RbpEncodingType@@00@Z@4QBDB; "Invalid switch value"
0x10055b2ae  lea     rcx, ?szText@?8???$CompileOnDataType@$0A@$00_K@RbpDecode@@CAP6AX_N0HPEA_K1PEBVRbpColumnContextNew@@PEAE@ZW4RbpDataType@@W4RbpEncodingType@@00@Z@4QBDB; "Invalid switch value"
0x10055b2b5  lea     r14d, [r9+9]
0x10055b2b9  cmp     [r13+2], r9b
0x10055b2bd  jl      loc_1018F2368
0x10055b2c3  mov     ebx, r9d
0x10055b2c6  jmp     short loc_10055B2C9
0x10055b2c9  movzx   r8d, word ptr [r13+1FFEh]
0x10055b2d1  movzx   edi, word ptr [r13+0Eh]
0x10055b2d6  add     r8, r13
0x10055b2d9  test    byte ptr [r8], 1
0x10055b2dd  mov     [rbp+1C0h+var_200], r8
0x10055b2e1  jnz     loc_1018F27E7
0x10055b2e7  mov     [rbp+1C0h+var_208], r9w
0x10055b2ec  mov     [rbp+1C0h+var_204], r9d
0x10055b2f0  mov     [rbp-22h], r9d
0x10055b2f4  movzx   eax, byte ptr [r8]
0x10055b2f8  and     eax, 0Eh
0x10055b2fb  movsxd  rdx, eax
0x10055b2fe  mov     eax, ds:(jpt_10055B309 - 100400000h)[r10+rdx*4]; switch 15 cases
0x10055b306  add     rax, r10
0x10055b309  jmp     rax; switch jump
0x10055b30b  movzx   edi, word ptr [r8+2]; jumptable 000000010055B309 cases 0,2,8,12
0x10055b310  lea     eax, [rdi-1]
0x10055b313  cmp     eax, 1F9Dh
0x10055b318  ja      loc_1018F2953
0x10055b31e  lea     rax, [r13+2000h]; jumptable 000000010055B309 cases 6,10
0x10055b325  mov     dword ptr [rbp+1C0h+var_1F8], edi
0x10055b328  mov     [rbp+1C0h+var_1F0+6], rax
0x10055b32c  test    esi, esi
0x10055b32e  jz      loc_1018F470D
0x10055b334  mov     r11, [r12]
0x10055b338  cmp     word ptr [r11+2Ch], 2
0x10055b33e  jnz     loc_1018F29A6
0x10055b344  lea     rcx, [rbp+1C0h+var_158]; struct LSN *
0x10055b348  call    ?GetNextNonLoggedTempDbLsn@@YAXAEAVLSN@@@Z; GetNextNonLoggedTempDbLsn(LSN &)
0x10055b34d  mov     r11, [r12]
0x10055b351  mov     rdx, r11; struct BUF *
0x10055b354  mov     rcx, [r11+90h]
0x10055b35b  test    rcx, rcx
0x10055b35e  jz      loc_1018F46F4
0x10055b364  mov     rcx, [rcx+758h]; this
0x10055b36b  xor     r8d, r8d; bool
0x10055b36e  call    ?PreNonLoggedDirty@DirtyPageMgr@@QEAAXPEAUBUF@@_N@Z; DirtyPageMgr::PreNonLoggedDirty(BUF *,bool)
0x10055b373  jmp     short loc_10055B376
0x10055b376  mov     rdx, [rsp+2C0h+var_278]; struct Record *
0x10055b37b  mov     rcx, r13; this
0x10055b37e  call    ?ReplaceFileHeader@FHdrPage@@QEAAXAEBVRecord@@@Z; FHdrPage::ReplaceFileHeader(Record const &)
0x10055b383  movzx   eax, [rbp+1C0h+var_150]
0x10055b387  cmp     [r13+30h], ax
0x10055b38c  jz      loc_1018F4798
0x10055b392  movsd   xmm0, [rbp+1C0h+var_158]
0x10055b397  movsd   qword ptr [r13+28h], xmm0
0x10055b39d  movzx   eax, [rbp+1C0h+var_150]
0x10055b3a1  mov     [r13+30h], ax
0x10055b3a6  mov     eax, 0FFDFh
0x10055b3ab  and     [r13+4], ax
0x10055b3b0  test    esi, esi
0x10055b3b2  jz      loc_1018F47B8
0x10055b3b8  mov     rdx, [r12]; struct BUF *
0x10055b3bc  lea     r9, [rbp+1C0h+var_158]; struct LSN *
0x10055b3c0  mov     rcx, cs:qword_10317B628; this
0x10055b3c7  xor     r8d, r8d; bool
0x10055b3ca  call    ?Dirty@BPool@@QEAAXPEAUBUF@@_NAEAVLSN@@@Z; BPool::Dirty(BUF *,bool,LSN &)
0x10055b3cf  test    cs:byte_10317AD49, 2
0x10055b3d6  jnz     loc_1018F47F4
0x10055b3dc  mov     rcx, [rbp+1C0h+var_40]
0x10055b3e3  xor     rcx, rsp; StackCookie
0x10055b3e6  call    __security_check_cookie
0x10055b3eb  mov     rbx, [rsp+2C0h+arg_10]
0x10055b3f3  add     rsp, 290h
0x10055b3fa  pop     r15
0x10055b3fc  pop     r14
0x10055b3fe  pop     r13
0x10055b400  pop     r12
0x10055b402  pop     rdi
0x10055b403  pop     rsi
0x10055b404  pop     rbp
0x10055b405  retn
0x1018f1f4d  mov     rcx, [r11+90h]
0x1018f1f54  test    rcx, rcx
0x1018f1f57  jnz     short loc_1018F1F6C
0x1018f1f59  mov     rcx, r11; this
0x1018f1f5c  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f1f61  mov     rcx, [r11+90h]
0x1018f1f68  mov     r11, [r12]
0x1018f1f6c  mov     rax, [rcx+6B0h]
0x1018f1f73  test    [rax+3Ch], bl
0x1018f1f76  jz      short loc_1018F1FA9
0x1018f1f78  cmp     [rax+280h], rdi
0x1018f1f7f  jnz     short loc_1018F1FA9
0x1018f1f81  mov     rcx, [r11+90h]
0x1018f1f88  test    rcx, rcx
0x1018f1f8b  jnz     short loc_1018F1F9C
0x1018f1f8d  mov     rcx, r11; this
0x1018f1f90  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f1f95  mov     rcx, [r11+90h]; this
0x1018f1f9c  call    ?IsBackupAllowedOnRbIoDb@RecoveryUnit@@QEBA_NXZ; RecoveryUnit::IsBackupAllowedOnRbIoDb(void)
0x1018f1fa1  test    al, al
0x1018f1fa3  jz      loc_10055B233
0x1018f1fa9  mov     r11, [r12]
0x1018f1fad  mov     rax, [r11+90h]
0x1018f1fb4  test    rax, rax
0x1018f1fb7  jnz     short loc_1018F1FC8
0x1018f1fb9  mov     rcx, r11; this
0x1018f1fbc  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f1fc1  mov     rax, [r11+90h]
0x1018f1fc8  test    byte ptr [rax+1CD0h], 20h
0x1018f1fcf  jnz     loc_10055B233
0x1018f1fd5  mov     rax, [r12]
0x1018f1fd9  mov     r11, [rax]
0x1018f1fdc  cmp     [r11+24h], di
0x1018f1fe1  jz      loc_1018F21AB
0x1018f1fe7  movzx   eax, byte ptr [r11+1]
0x1018f1fec  cmp     al, 0Bh
0x1018f1fee  jnz     loc_1018F2198
0x1018f1ff4  cmp     dword ptr [r11+18h], 63h ; 'c'
0x1018f1ff9  jnz     loc_1018F219C
0x1018f1fff  jmp     short loc_1018F2002
0x1018f2002  mov     eax, [r11+20h]
0x1018f2006  lea     rcx, [rbp+1C0h+var_238]
0x1018f200a  mov     [rbp+1C0h+var_238], eax
0x1018f200d  movzx   eax, word ptr [r11+24h]
0x1018f2012  mov     [rbp+1C0h+var_234], ax
0x1018f2016  call    ?IsConcurrentUpdateSupportedPageId@@YA_NVPageId@@@Z; IsConcurrentUpdateSupportedPageId(PageId)
0x1018f201b  test    al, al
0x1018f201d  jz      loc_1018F21AB
0x1018f2023  lea     rdx, [rsp+2C0h+var_268]
0x1018f2028  mov     rcx, r11
0x1018f202b  call    ?GetIcxLsn@PageHeader@@QEBA?AVLSN@@XZ; PageHeader::GetIcxLsn(void)
0x1018f2030  movzx   edi, [rsp+2C0h+var_260]
0x1018f2035  jmp     short loc_1018F2038
0x1018f2038  mov     r11, [r12]
0x1018f203c  mov     rcx, [r11+90h]
0x1018f2043  test    rcx, rcx
0x1018f2046  jnz     short loc_1018F2057
0x1018f2048  mov     rcx, r11; this
0x1018f204b  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f2050  mov     rcx, [r11+90h]
0x1018f2057  movzx   edx, word ptr [r11+74h]
0x1018f205c  xor     r8d, r8d
0x1018f205f  mov     rcx, [rcx+6A0h]
0x1018f2066  call    ?GetFCB@FileMgr@@QEBAPEAVFCB@@JW4LookupFailureMode@@@Z; FileMgr::GetFCB(long,LookupFailureMode)
0x1018f206b  mov     r11, [r12]
0x1018f206f  mov     rsi, rax
0x1018f2072  mov     rbx, r11
0x1018f2075  mov     rax, [r11+90h]
0x1018f207c  test    rax, rax
0x1018f207f  jnz     short loc_1018F2097
0x1018f2081  mov     rcx, r11; this
0x1018f2084  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f2089  mov     rax, [r11+90h]
0x1018f2090  mov     r11, [r12]
0x1018f2094  mov     rbx, r11
0x1018f2097  mov     rax, [rax+7A8h]
0x1018f209e  cmp     dword ptr [rax+58h], 0
0x1018f20a2  jnz     short loc_1018F20C9
0x1018f20a4  mov     eax, [rsi+130h]
0x1018f20aa  cmp     eax, dword ptr [rsp+2C0h+var_268]
0x1018f20ae  ja      short loc_1018F20C9
0x1018f20b0  jnz     short loc_1018F210A
0x1018f20b2  mov     eax, [rsi+134h]
0x1018f20b8  cmp     eax, dword ptr [rsp+2C0h+var_268+4]
0x1018f20bc  ja      short loc_1018F20C9
0x1018f20be  jnz     short loc_1018F210A
0x1018f20c0  cmp     [rsi+138h], di
0x1018f20c7  jbe     short loc_1018F210A
0x1018f20c9  mov     rax, [r11+90h]
0x1018f20d0  test    rax, rax
0x1018f20d3  jnz     short loc_1018F20EB
0x1018f20d5  mov     rcx, r11; this
0x1018f20d8  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f20dd  mov     rax, [r11+90h]
0x1018f20e4  mov     r11, [r12]
0x1018f20e8  mov     rbx, r11
0x1018f20eb  mov     rcx, [rax+6B0h]
0x1018f20f2  test    byte ptr [rcx+3Ch], 1
0x1018f20f6  jz      loc_1018F21C7
0x1018f20fc  cmp     qword ptr [rcx+280h], 0
0x1018f2104  jnz     loc_1018F21C7
0x1018f210a  mov     rax, [r11+90h]
0x1018f2111  test    rax, rax
0x1018f2114  jnz     short loc_1018F2129
0x1018f2116  mov     rcx, r11; this
0x1018f2119  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f211e  mov     rax, [r11+90h]
0x1018f2125  mov     r11, [r12]
0x1018f2129  mov     rax, [rax+7A8h]
0x1018f2130  cmp     dword ptr [rax+110h], 0
0x1018f2137  jz      short loc_1018F218C
0x1018f2139  mov     r8, [r11]
0x1018f213c  mov     eax, 41A26B6Dh
0x1018f2141  mov     ecx, [r8+20h]
0x1018f2145  and     ecx, 0FFFFFFF8h
0x1018f2148  mul     ecx
0x1018f214a  shr     edx, 11h
0x1018f214d  imul    eax, edx, 7CD00h
0x1018f2153  cmp     ecx, eax
0x1018f2155  jz      short loc_1018F218C
0x1018f2157  mov     rcx, [r11+90h]
0x1018f215e  test    rcx, rcx
0x1018f2161  jnz     short loc_1018F2179
0x1018f2163  mov     rcx, r11; this
0x1018f2166  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f216b  mov     rax, [r12]
0x1018f216f  mov     rcx, [r11+90h]
0x1018f2176  mov     r8, [rax]
0x1018f2179  mov     rcx, [rcx+7A8h]; this
0x1018f2180  lea     rdx, [r8+20h]; struct PageId *
0x1018f2184  call    ?MarkExtentInBackupBitmapList@BackupManager@@QEAAXAEBVPageId@@@Z; BackupManager::MarkExtentInBackupBitmapList(PageId const &)
0x1018f2189  jmp     short loc_1018F218C
0x1018f218c  mov     esi, [rsp+2C0h+var_27C]
0x1018f2190  xor     edi, edi
0x1018f2192  jmp     loc_10055B233
0x1018f2198  cmp     al, 8
0x1018f219a  jz      short loc_1018F21A0
0x1018f219c  cmp     al, 9
0x1018f219e  jnz     short loc_1018F21AB
0x1018f21a0  cmp     dword ptr [r11+18h], 63h ; 'c'
0x1018f21a5  jz      loc_1018F2002
0x1018f21ab  movsd   xmm0, qword ptr [r11+28h]
0x1018f21b1  movzx   edi, word ptr [r11+30h]
0x1018f21b6  movsd   [rsp+2C0h+var_268], xmm0
0x1018f21bc  mov     [rsp+2C0h+var_260], di
0x1018f21c1  jmp     loc_1018F2038
0x1018f21c7  mov     rcx, [rbx+90h]
0x1018f21ce  mov     rdx, rbx
0x1018f21d1  test    rcx, rcx
0x1018f21d4  jnz     short loc_1018F21E9
0x1018f21d6  mov     rcx, rbx; this
0x1018f21d9  call    ?FixupPru@BUF@@AEBAXXZ; BUF::FixupPru(void)
0x1018f21de  mov     rdx, [r12]
0x1018f21e2  mov     rcx, [rbx+90h]; struct RecoveryUnit *
0x1018f21e9  mov     rdx, [rdx]
0x1018f21ec  add     rdx, 20h ; ' '; struct PageId *
  ... truncated ...
```
