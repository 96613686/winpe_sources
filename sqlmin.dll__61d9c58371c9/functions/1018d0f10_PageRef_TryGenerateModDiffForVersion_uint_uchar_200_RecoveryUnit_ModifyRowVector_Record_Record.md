# PageRef::TryGenerateModDiffForVersion(uint &,uchar (&)[200],RecoveryUnit *,ModifyRowVector &,Record &,Record &)

- ea: `0x1018d0f10`
- end: `0x1018d2e80`
- name: `?TryGenerateModDiffForVersion@PageRef@@SA_NAEAIAEAY0MI@EPEAVRecoveryUnit@@AEAVModifyRowVector@@AEAVRecord@@4@Z`
- size: `8048`
- prototype: `bool __fastcall(unsigned int *, unsigned __int8 (*)[200], struct RecoveryUnit *, struct ModifyRowVector *, struct Record *, struct Record *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x10049a9f0`
- `0x10049b060`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100402000`
- `0x10042d300`
- `0x100441e00`
- `0x100441e40`
- `0x100447c30`
- `0x10048c200`
- `0x10049c6c0`
- `0x10049dc80`
- `0x1004b4190`
- `0x1018d0f10`
- `0x10190d090`
- `0x101d1df10`
- `0x1021d8a90`
- `0x1021e8a60`
- `0x1021e8ae0`
- `0x1021e8b50`
- `0x1021e8c30`
- `0x1021eab40`
- `0x1021ecfd0`

## import_xrefs

- `sqldk!?NoThrowHandler@@YAHHHHHPEAD@Z` at `0x1018d0fe0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1018d2e50`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1018d2e50`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d125b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1336`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1414`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d16d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d179b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d195b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1a32`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1b0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1d96`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1e5f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d201d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d20f8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d21d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d245e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d2523`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d26d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d27ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d2889`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d2b1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d2be2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d125b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1336`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1414`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d16d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d179b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d195b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1a32`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1b0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1d96`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d1e5f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d201d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d20f8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d21d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d245e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d2523`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d26d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d27ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d2889`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d2b1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d2be2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1231`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d130c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d13ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d16b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1775`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1935`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1a0c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1ae6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1d70`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1e39`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1ff7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d20d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d21ab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2438`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d24fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d26ab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2786`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2863`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2af7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2bbc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1231`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d130c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d13ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d16b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1775`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1935`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1a0c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1ae6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1d70`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1e39`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d1ff7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d20d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d21ab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2438`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d24fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d26ab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2786`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2863`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2af7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d2bbc`
- `sqldk!SystemThread_TlsIndex` at `0x1018d11dc`
- `sqldk!SystemThread_TlsIndex` at `0x1018d12b7`
- `sqldk!SystemThread_TlsIndex` at `0x1018d1395`
- `sqldk!SystemThread_TlsIndex` at `0x1018d165b`
- `sqldk!SystemThread_TlsIndex` at `0x1018d1720`
- `sqldk!SystemThread_TlsIndex` at `0x1018d18e2`
- `sqldk!SystemThread_TlsIndex` at `0x1018d19b7`
- `sqldk!SystemThread_TlsIndex` at `0x1018d1a91`
- `sqldk!SystemThread_TlsIndex` at `0x1018d1d1b`
- `sqldk!SystemThread_TlsIndex` at `0x1018d1de4`
- `sqldk!SystemThread_TlsIndex` at `0x1018d1fa2`
- `sqldk!SystemThread_TlsIndex` at `0x1018d207d`
- `sqldk!SystemThread_TlsIndex` at `0x1018d2156`
- `sqldk!SystemThread_TlsIndex` at `0x1018d23e3`
- `sqldk!SystemThread_TlsIndex` at `0x1018d24a8`
- `sqldk!SystemThread_TlsIndex` at `0x1018d2656`
- `sqldk!SystemThread_TlsIndex` at `0x1018d2731`
- `sqldk!SystemThread_TlsIndex` at `0x1018d280e`
- `sqldk!SystemThread_TlsIndex` at `0x1018d2aa2`
- `sqldk!SystemThread_TlsIndex` at `0x1018d2b67`
- `sqldk!SystemThread_TlsIndex` at `0x1018d2e18`
- `sqldk!SystemThread_TlsOffset` at `0x1018d11e5`
- `sqldk!SystemThread_TlsOffset` at `0x1018d12c0`
- `sqldk!SystemThread_TlsOffset` at `0x1018d139e`
- `sqldk!SystemThread_TlsOffset` at `0x1018d1664`
- `sqldk!SystemThread_TlsOffset` at `0x1018d1729`
- `sqldk!SystemThread_TlsOffset` at `0x1018d18eb`
- `sqldk!SystemThread_TlsOffset` at `0x1018d19c0`
- `sqldk!SystemThread_TlsOffset` at `0x1018d1a9a`
- `sqldk!SystemThread_TlsOffset` at `0x1018d1d24`
- `sqldk!SystemThread_TlsOffset` at `0x1018d1ded`
- `sqldk!SystemThread_TlsOffset` at `0x1018d1fab`
- `sqldk!SystemThread_TlsOffset` at `0x1018d2086`
- `sqldk!SystemThread_TlsOffset` at `0x1018d215f`
- `sqldk!SystemThread_TlsOffset` at `0x1018d23ec`
- `sqldk!SystemThread_TlsOffset` at `0x1018d24b1`
- `sqldk!SystemThread_TlsOffset` at `0x1018d265f`
- `sqldk!SystemThread_TlsOffset` at `0x1018d273a`
- `sqldk!SystemThread_TlsOffset` at `0x1018d2817`
- `sqldk!SystemThread_TlsOffset` at `0x1018d2aab`
- `sqldk!SystemThread_TlsOffset` at `0x1018d2b70`
- `sqldk!SystemThread_TlsOffset` at `0x1018d2e21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018d2e3a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018d2e3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall PageRef::TryGenerateModDiffForVersion(
        unsigned int *a1,
        unsigned __int8 (*a2)[200],
        struct RecoveryUnit *a3,
        struct ModifyRowVector *a4,
        struct Record *a5,
        struct Record *a6)
{
  struct Record *v7; // r13
  unsigned int v8; // r14d
  unsigned int v9; // r14d
  int v10; // r14d
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  char *v13; // rcx
  unsigned int v14; // esi
  unsigned __int16 v15; // di
  char *v16; // rcx
  char *v17; // rcx
  CDRecord *v18; // rcx
  CDRecord *v19; // rcx
  FixedVarRecord *v20; // rdi
  FixedVarRecord *v21; // rbx
  unsigned int *v22; // r12
  __int64 v23; // rdx
  int *v24; // r14
  char **v25; // r15
  char *v26; // r8
  char v27; // al
  int v28; // ecx
  _WORD *v29; // rsi
  __int16 v30; // ax
  __int64 v31; // rax
  __int64 v32; // rax
  int v33; // r8d
  unsigned int v34; // r9d
  unsigned int *v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rax
  unsigned int v38; // edx
  __int64 v39; // rax
  __int64 v40; // rax
  FixedVarRecord *v41; // r10
  char *v42; // rax
  unsigned int v43; // edi
  unsigned int v44; // ecx
  unsigned int v45; // eax
  unsigned __int16 v46; // dx
  __int16 v47; // cx
  __int16 v48; // ax
  __int16 v49; // cx
  __int16 v50; // ax
  unsigned int v51; // eax
  unsigned __int64 v52; // rdx
  int v53; // r8d
  unsigned __int64 v54; // r8
  int v55; // ecx
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  unsigned int v60; // edx
  char v61; // cl
  unsigned int v62; // ecx
  _BYTE *v63; // rax
  FixedVarRecord *v64; // rdi
  char *v65; // r13
  unsigned int *v66; // r12
  __int64 v67; // rdx
  int *v68; // r14
  char **v69; // r15
  char *v70; // r8
  char v71; // al
  int v72; // ecx
  _WORD *v73; // rsi
  __int16 v74; // ax
  __int64 v75; // rax
  __int64 v76; // rax
  int v77; // r8d
  unsigned int v78; // r9d
  unsigned int *v79; // rbx
  __int64 v80; // rax
  __int64 v81; // rax
  unsigned int v82; // edx
  __int64 v83; // rax
  __int64 v84; // rax
  FixedVarRecord *v85; // r10
  char *v86; // rax
  unsigned int v87; // ebx
  unsigned int v88; // ecx
  unsigned int v89; // eax
  unsigned __int16 v90; // dx
  __int64 v91; // rdx
  __int16 v92; // cx
  __int16 v93; // ax
  __int16 v94; // cx
  __int16 v95; // ax
  unsigned int v96; // eax
  unsigned __int64 v97; // rdx
  int v98; // r8d
  unsigned __int64 v99; // r8
  int v100; // ecx
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  unsigned int v105; // ecx
  char v106; // dl
  unsigned int v107; // eax
  _BYTE *v108; // rax
  struct Record *v109; // r13
  FixedVarRecord *v110; // rdi
  FixedVarRecord *v111; // rbx
  FixedVarRecord *v112; // r13
  unsigned int *v113; // r14
  __int64 v114; // rdx
  int *v115; // r12
  char **v116; // r15
  char *v117; // r8
  char v118; // al
  int v119; // ecx
  _WORD *v120; // rsi
  __int16 v121; // ax
  __int64 v122; // rax
  __int64 v123; // rax
  int v124; // r8d
  unsigned int v125; // r9d
  unsigned int *v126; // rdi
  __int64 v127; // rax
  __int64 v128; // rax
  unsigned int v129; // edx
  __int64 v130; // rax
  __int64 v131; // rax
  FixedVarRecord *v132; // r10
  char *v133; // rax
  unsigned int v134; // edi
  unsigned int v135; // ecx
  unsigned int v136; // eax
  unsigned __int16 v137; // dx
  __int64 v138; // rdx
  __int16 v139; // cx
  __int16 v140; // ax
  __int16 v141; // cx
  __int16 v142; // ax
  unsigned int v143; // eax
  unsigned __int64 v144; // rdx
  int v145; // r8d
  unsigned __int64 v146; // r8
  int v147; // ecx
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  unsigned int v152; // edx
  char v153; // cl
  FixedVarRecord *v154; // rsi
  unsigned int v155; // ecx
  _BYTE *v156; // rax
  FixedVarRecord *v157; // rbx
  FixedVarRecord *v158; // r13
  __int64 v159; // r8
  int *v160; // r12
  char **v161; // r15
  char *v162; // rdx
  char v163; // al
  int v164; // ecx
  _WORD *v165; // rsi
  __int16 v166; // ax
  __int64 v167; // rax
  __int64 v168; // rax
  int v169; // r8d
  unsigned int v170; // r9d
  unsigned int *v171; // rdi
  __int64 v172; // rax
  __int64 v173; // rax
  unsigned int v174; // edx
  unsigned int *v175; // r14
  __int64 v176; // rax
  __int64 v177; // rax
  FixedVarRecord *v178; // r10
  char *v179; // rax
  unsigned int v180; // edi
  unsigned int v181; // ecx
  unsigned int v182; // eax
  unsigned __int16 v183; // dx
  __int64 v184; // rdx
  __int16 v185; // cx
  __int16 v186; // ax
  __int16 v187; // cx
  __int16 v188; // ax
  unsigned __int64 v189; // rdx
  int v190; // r8d
  __int64 v191; // rax
  unsigned __int64 v192; // rdx
  int v193; // ecx
  __int64 v194; // rax
  __int64 v195; // rax
  __int64 v196; // rax
  __int64 v197; // rax
  char v198; // cl
  _BYTE *v199; // rax
  __int64 v200; // r10
  ModifyRowVector *v201; // r14
  __int64 v202; // r8
  unsigned __int64 v203; // rax
  __int64 v204; // rcx
  unsigned __int64 v205; // rcx
  void *v206; // rsp
  void *v207; // rsp
  char *v208; // rcx
  char *v209; // rax
  char *v210; // rax
  struct Record *v211; // rdi
  FixedVarRecord *v212; // rbx
  unsigned int v213; // r8d
  unsigned int *v214; // r15
  __int64 v215; // rbx
  struct Worker *v216; // rcx
  const struct SQLError *CurrentException; // rax
  FixedVarRecord *v219; // [rsp+30h] [rbp+0h] BYREF
  int v220; // [rsp+38h] [rbp+8h]
  int v221; // [rsp+3Ch] [rbp+Ch]
  int v222; // [rsp+40h] [rbp+10h]
  int v223; // [rsp+44h] [rbp+14h]
  unsigned int v224; // [rsp+48h] [rbp+18h]
  char v225; // [rsp+4Ch] [rbp+1Ch]
  _QWORD v226[2]; // [rsp+50h] [rbp+20h] BYREF
  FixedVarRecord *v227; // [rsp+60h] [rbp+30h] BYREF
  FixedVarRecord *v228; // [rsp+70h] [rbp+40h]
  struct Record *v229; // [rsp+78h] [rbp+48h]
  unsigned int v230; // [rsp+80h] [rbp+50h]
  int v231; // [rsp+84h] [rbp+54h]
  struct Record *v232; // [rsp+88h] [rbp+58h]
  char v233[8]; // [rsp+90h] [rbp+60h] BYREF
  int v234; // [rsp+98h] [rbp+68h] BYREF
  __int64 v235; // [rsp+A0h] [rbp+70h]
  unsigned int v236; // [rsp+A8h] [rbp+78h]
  unsigned int v237; // [rsp+ACh] [rbp+7Ch]
  ModifyRowVector *v238; // [rsp+B0h] [rbp+80h]
  unsigned int *v239; // [rsp+B8h] [rbp+88h]
  unsigned __int8 (*v240)[200]; // [rsp+C0h] [rbp+90h]
  struct RecoveryUnit *v241; // [rsp+C8h] [rbp+98h]
  unsigned int *v242; // [rsp+D0h] [rbp+A0h]
  __int64 v243; // [rsp+D8h] [rbp+A8h]
  unsigned __int64 v244; // [rsp+E0h] [rbp+B0h]
  unsigned __int64 v245; // [rsp+E8h] [rbp+B8h]
  unsigned __int64 v246; // [rsp+F0h] [rbp+C0h]
  unsigned __int64 v247; // [rsp+F8h] [rbp+C8h]
  _BYTE v248[24]; // [rsp+100h] [rbp+D0h] BYREF
  _BYTE v249[40]; // [rsp+118h] [rbp+E8h] BYREF
  __int64 v250; // [rsp+140h] [rbp+110h] BYREF
  int v251; // [rsp+148h] [rbp+118h]
  __int16 v252; // [rsp+14Ch] [rbp+11Ch]
  __int64 v253; // [rsp+220h] [rbp+1F0h] BYREF
  int v254; // [rsp+228h] [rbp+1F8h]
  __int16 v255; // [rsp+22Ch] [rbp+1FCh]

  v243 = -2;
  v238 = a4;
  v241 = a3;
  v240 = a2;
  v239 = a1;
  v242 = a1;
  v229 = a5;
  v7 = a6;
  v232 = a6;
  v250 = 0;
  v251 = 0;
  v252 = 0;
  v219 = 0;
  v253 = 0;
  v254 = 0;
  v255 = 0;
  v8 = **((unsigned __int8 **)a6 + 1);
  if ( *(_WORD *)a6 )
    v9 = v8 >> 1;
  else
    v9 = v8 >> 6;
  v10 = v9 & 1;
  v231 = v10;
  v225 = 0;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v249, 0, 0, 0, NoThrowHandler, 0);
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v234, 1);
    v11 = **((unsigned __int8 **)a5 + 1);
    if ( *(_WORD *)a5 )
      v12 = v11 >> 1;
    else
      v12 = v11 >> 6;
    if ( (v12 & 1) != 0 )
    {
      v13 = (char *)a5 + 2;
      if ( *(_WORD *)a5 )
        CDRecord::GetXdesTs(v13, v226);
      else
        FixedVarRecord::GetXdesTs(v13, v226);
      v14 = v226[0];
      LODWORD(v228) = v226[0];
      v15 = WORD2(v226[0]);
      WORD2(v228) = WORD2(v226[0]);
      LODWORD(v226[0]) = 0;
      WORD2(v226[0]) = 0;
      XdesMgr::GetOldestActiveXdesId((struct RecoveryUnit *)((char *)a3 + 6600), (struct XdesId *)v226);
      LODWORD(v219) = 0;
      WORD2(v219) = 0;
      if ( !v15 && !v14 )
        goto LABEL_21;
      LODWORD(v227) = v14;
      WORD2(v227) = v15;
      v16 = (char *)a5 + 2;
      if ( *(_WORD *)a5 )
        CDRecord::GetVersionRecPtr(v16, v233);
      else
        FixedVarRecord::GetVersionRecPtr(v16, v233);
      if ( !(unsigned __int8)VersionMgr::IsTimestampInteresting(*((_QWORD *)a3 + 214), &v227, v233)
        && (WORD2(v226[0]) > v15 || WORD2(v226[0]) == v15 && LODWORD(v226[0]) > v14) )
      {
LABEL_21:
        v225 = 1;
        v17 = (char *)a5 + 2;
        if ( *(_WORD *)a5 )
          CDRecord::GetVersionRecPtr(v17, &v219);
        else
          FixedVarRecord::GetVersionRecPtr(v17, &v219);
        v18 = (struct Record *)((char *)a5 + 2);
        if ( *(_WORD *)a5 )
          CDRecord::StripVerInfo(v18, (struct RecVersionInfoWithPayload *)&v253);
        else
          FixedVarRecord::StripVerInfo(v18, (struct RecVersionInfoWithPayload *)&v253);
      }
    }
    if ( (_BYTE)v10 )
    {
      v19 = (struct Record *)((char *)a6 + 2);
      if ( *(_WORD *)a6 )
        CDRecord::StripVerInfo(v19, (struct RecVersionInfoWithPayload *)&v250);
      else
        FixedVarRecord::StripVerInfo(v19, (struct RecVersionInfoWithPayload *)&v250);
    }
    v20 = (struct Record *)((char *)a5 + 2);
    v228 = (struct Record *)((char *)a5 + 2);
    if ( *(_WORD *)a5 )
    {
      v62 = *((_DWORD *)a5 + 1);
      if ( !v62 )
      {
        CDRecord::Resize((struct Record *)((char *)a5 + 2));
        v62 = *((_DWORD *)a5 + 1);
      }
      if ( v62 >= 9 || (v63 = (_BYTE *)*((_QWORD *)a5 + 1), (*v63 & 0x1C) != 0) && (*v63 & 0x1C) != 0xC )
      {
        v224 = 9;
      }
      else
      {
        v224 = 9;
        v62 = 9;
      }
      v230 = v62;
      goto LABEL_139;
    }
    v21 = (struct Record *)((char *)a5 + 2);
    v219 = (struct Record *)((char *)a5 + 2);
    v22 = (unsigned int *)((char *)a5 + 4);
    if ( *((_DWORD *)a5 + 1) )
      goto LABEL_126;
    v220 = 0;
    *(_WORD *)v20 = 0;
    v23 = *((unsigned int *)a5 + 4);
    v24 = (int *)((char *)a5 + 20);
    *((_DWORD *)a5 + 5) = v23;
    v25 = (char **)((char *)a5 + 8);
    v26 = (char *)*((_QWORD *)a5 + 1);
    v27 = *v26;
    v28 = v23;
    if ( (*v26 & 0x10) != 0 )
    {
      LODWORD(v23) = (((unsigned int)*(unsigned __int16 *)&v26[v23] + 7) >> 3) + v23 + 2;
      *v24 = v23;
      v27 = *v26;
      v28 = v23;
    }
    v29 = (_WORD *)((char *)a5 + 28);
    if ( (v27 & 0x20) == 0 )
    {
      *v22 = v23;
      *v29 = 0;
      *((_DWORD *)a5 + 6) = v28;
      goto LABEL_92;
    }
    v227 = (FixedVarRecord *)&v26[(unsigned int)v23];
    v30 = *(_WORD *)v227;
    *v29 = *(_WORD *)v227;
    if ( !v30 )
    {
      v220 = 1;
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v31 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL);
        if ( v31 )
        {
          v32 = *(_QWORD *)(v31 + 96);
          if ( v32 )
          {
            if ( *(_BYTE *)(v32 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
              else
                ex_raise(34, 68, 21, 1003);
            }
          }
        }
        v21 = v219;
      }
      RaiseInconsistencyError(*v25, 3);
      v28 = *v24;
    }
    v33 = (unsigned __int16)*v29;
    v34 = v28 + 2 * (v33 + 1);
    v35 = (unsigned int *)((char *)v21 + 22);
    *(_DWORD *)((char *)v21 + 22) = v34;
    if ( v34 > 0x1F9E )
    {
      ++v220;
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v36 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL);
        if ( v36 )
        {
          v37 = *(_QWORD *)(v36 + 96);
          if ( v37 )
          {
            if ( *(_BYTE *)(v37 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
        v21 = v219;
      }
      RaiseInconsistencyError(*v25, 4);
      LOWORD(v33) = *v29;
      v34 = *v35;
    }
    v38 = *((_WORD *)v227 + (unsigned __int16)v33) & 0x7FFF;
    *v22 = v38;
    if ( v34 > v38 )
    {
      ++v220;
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v39 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL);
        if ( v39 )
        {
          v40 = *(_QWORD *)(v39 + 96);
          if ( v40 )
          {
            if ( *(_BYTE *)(v40 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
        v21 = v219;
      }
      RaiseInconsistencyError(*v25, 4);
      LOWORD(v33) = *v29;
    }
    v41 = v228;
    while ( 1 )
    {
      if ( *((__int16 *)v227 + (unsigned int)(unsigned __int16)v33) >= 0 )
      {
LABEL_90:
        v26 = *v25;
        LODWORD(v23) = *v22;
        v20 = v228;
        goto LABEL_92;
      }
      v42 = &(*v25)[*v24];
      if ( (unsigned __int16)v33 == 1 )
      {
        v43 = *(_DWORD *)((char *)v41 + 22);
        v44 = v43;
        v45 = *(_WORD *)&v42[2 * (unsigned __int16)v33] & 0x7FFF;
      }
      else
      {
        v43 = *(_WORD *)&v42[2 * (unsigned __int16)v33 - 2] & 0x7FFF;
        v44 = *(_DWORD *)((char *)v41 + 22);
        v45 = *(_WORD *)&v42[2 * (unsigned __int16)v33] & 0x7FFF;
        if ( v43 < v44 )
          goto LABEL_78;
      }
      if ( v45 < v43 )
      {
LABEL_78:
        RaiseInconsistencyError(*v25, 7);
        v44 = *(_DWORD *)((char *)v228 + 22);
        v41 = v228;
      }
      v230 = v43;
      if ( v43 < v44 || v43 > *v22 )
      {
        ++v220;
        goto LABEL_126;
      }
      v46 = *(_WORD *)&(*v25)[v43];
      if ( v46 == 5 )
      {
        *(_WORD *)v21 |= 2u;
        --*v29;
        *((_WORD *)v21 + 20) = v43;
        v23 = *(_QWORD *)((char *)v21 + 6) + (unsigned __int16)v43;
        v47 = *(_WORD *)(v23 + 2);
        v48 = *((_WORD *)v21 + 21) & 0xC7FF;
        if ( (v47 & 0x4000) != 0 )
        {
          v49 = v48 | v47 & 0x3800;
          *((_WORD *)v21 + 21) = v49;
        }
        else
        {
          *((_WORD *)v21 + 21) = v48;
          v49 = v48;
        }
        *((_WORD *)v21 + 21) = v49 ^ (*(_WORD *)(v23 + 2) ^ v49) & 0x7FF;
        v26 = *v25;
        LODWORD(v23) = *v22;
        v20 = v228;
LABEL_92:
        if ( (*v26 & 0x40) != 0 )
        {
          v51 = *v22;
          *(_DWORD *)((char *)a5 + 38) = *v22;
          *v22 = v51 + 14;
          v244 = *(_QWORD *)FixedVarRecord::FindVersioningInfo(v21);
          v52 = HIWORD(v244);
          v53 = 0;
          if ( ((SHIWORD(v244) ^ ((unsigned int)SHIWORD(v244) >> 1)) & 0x2000) != 0 )
          {
            if ( (v244 & 0x4000000000000000LL) != 0 )
              LOWORD(v52) = HIWORD(v244) | 0x2000;
            else
              LOWORD(v52) = HIWORD(v244) & 0xDFFF;
          }
          if ( (_WORD)v52 == 0xFFFC )
            v53 = WORD2(v244) >> 5;
          *v22 += v53;
          LODWORD(v23) = *v22;
        }
        else
        {
          *(_DWORD *)((char *)a5 + 38) = 0;
        }
        v54 = *(_QWORD *)((char *)v21 + 28);
        v55 = v23;
        if ( v54 && v54 < (unsigned __int64)&(*v25)[(unsigned int)v23] )
        {
          ++v220;
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v56 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v56 )
            {
              v57 = *(_QWORD *)(v56 + 96);
              if ( v57 )
              {
                if ( *(_BYTE *)(v57 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
            v21 = v219;
          }
          RaiseInconsistencyError(*v25, 18);
          v55 = *(_DWORD *)((char *)v20 + 2);
        }
        if ( (unsigned int)(v55 - 1) > 0x3F3B )
        {
          ++v220;
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v58 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v58 )
            {
              v59 = *(_QWORD *)(v58 + 96);
              if ( v59 )
              {
                if ( *(_BYTE *)(v59 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
            v21 = v219;
          }
          RaiseInconsistencyError(*v25, 5);
        }
LABEL_126:
        v60 = *v22;
        if ( *v22 >= 9 || (v61 = **(_BYTE **)((char *)v21 + 6) & 0xE) != 0 && v61 != 12 )
        {
          v224 = 9;
          v230 = v60;
          v7 = v232;
        }
        else
        {
          v224 = 9;
          v230 = 9;
          v7 = v232;
        }
LABEL_139:
        v64 = (struct Record *)((char *)v7 + 2);
        v227 = (struct Record *)((char *)v7 + 2);
        if ( *(_WORD *)v7 )
        {
          v105 = *((_DWORD *)v7 + 1);
          if ( !v105 )
          {
            CDRecord::Resize((struct Record *)((char *)v7 + 2));
            v105 = *((_DWORD *)v7 + 1);
          }
          if ( v105 >= 9 || (v108 = (_BYTE *)*((_QWORD *)v7 + 1), (*v108 & 0x1C) != 0) && (*v108 & 0x1C) != 0xC )
            v107 = v105;
          else
            v107 = 9;
        }
        else
        {
          v219 = (struct Record *)((char *)v7 + 2);
          v65 = (char *)v7 + 2;
          v66 = (unsigned int *)((char *)v64 + 2);
          if ( *(_DWORD *)((char *)v64 + 2) )
            goto LABEL_234;
          v221 = 0;
          *(_WORD *)v64 = 0;
          v67 = *(unsigned int *)((char *)v64 + 14);
          v68 = (int *)((char *)v64 + 18);
          *(_DWORD *)((char *)v64 + 18) = v67;
          v69 = (char **)((char *)v64 + 6);
          v70 = *(char **)((char *)v64 + 6);
          v71 = *v70;
          v72 = v67;
          if ( (*v70 & 0x10) != 0 )
          {
            LODWORD(v67) = (((unsigned int)*(unsigned __int16 *)&v70[v67] + 7) >> 3) + 2 + v67;
            *v68 = v67;
            v71 = *v70;
            v72 = v67;
          }
          v73 = (_WORD *)((char *)v64 + 26);
          if ( (v71 & 0x20) != 0 )
          {
            v226[0] = &v70[(unsigned int)v67];
            v74 = *(_WORD *)v226[0];
            *v73 = *(_WORD *)v226[0];
            if ( !v74 )
            {
              v221 = 1;
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v75 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v75 )
                {
                  v76 = *(_QWORD *)(v75 + 96);
                  if ( v76 )
                  {
                    if ( *(_BYTE *)(v76 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
                v64 = v219;
              }
              RaiseInconsistencyError(*v69, 3);
              v72 = *v68;
            }
            v77 = (unsigned __int16)*v73;
            v78 = v72 + 2 * (v77 + 1);
            v79 = (unsigned int *)((char *)v64 + 22);
            *(_DWORD *)((char *)v64 + 22) = v78;
            if ( v78 > 0x1F9E )
            {
              ++v221;
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v80 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v80 )
                {
                  v81 = *(_QWORD *)(v80 + 96);
                  if ( v81 )
                  {
                    if ( *(_BYTE *)(v81 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
                v64 = v219;
              }
              RaiseInconsistencyError(*v69, 4);
              LOWORD(v77) = *v73;
              v78 = *v79;
            }
            v82 = *(_WORD *)(v226[0] + 2LL * (unsigned __int16)v77) & 0x7FFF;
            *v66 = v82;
            if ( v78 > v82 )
            {
              ++v221;
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v83 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v83 )
                {
                  v84 = *(_QWORD *)(v83 + 96);
                  if ( v84 )
                  {
                    if ( *(_BYTE *)(v84 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
                v64 = v219;
              }
              RaiseInconsistencyError(*v69, 4);
              LOWORD(v77) = *v73;
            }
            v85 = v227;
            while ( 1 )
            {
              if ( *(__int16 *)(v226[0] + 2LL * ((unsigned int)(unsigned __int16)v77 - 1) + 2) >= 0 )
                goto LABEL_194;
              v86 = &(*v69)[*v68];
              if ( (unsigned __int16)v77 == 1 )
              {
                v87 = *(_DWORD *)((char *)v85 + 22);
                v88 = v87;
                v89 = *(_WORD *)&v86[2 * (unsigned __int16)v77] & 0x7FFF;
              }
              else
              {
                v87 = *(_WORD *)&v86[2 * (unsigned __int16)v77 - 2] & 0x7FFF;
                v88 = *(_DWORD *)((char *)v85 + 22);
                v89 = *(_WORD *)&v86[2 * (unsigned __int16)v77] & 0x7FFF;
                if ( v87 < v88 )
                  goto LABEL_186;
              }
              if ( v89 < v87 )
              {
LABEL_186:
                RaiseInconsistencyError(*v69, 7);
                v88 = *(_DWORD *)((char *)v227 + 22);
                v85 = v227;
              }
              v236 = v87;
              if ( v87 < v88 || v87 > *v66 )
              {
                ++v221;
                goto LABEL_234;
              }
              v90 = *(_WORD *)&(*v69)[v87];
              if ( v90 == 5 )
              {
                *(_WORD *)v64 |= 2u;
                --*v73;
                *((_WORD *)v64 + 20) = v87;
                v91 = *(_QWORD *)((char *)v64 + 6) + (unsigned __int16)v87;
                v92 = *(_WORD *)(v91 + 2);
                v93 = *((_WORD *)v64 + 21) & 0xC7FF;
                if ( (v92 & 0x4000) != 0 )
                {
                  v94 = v93 | v92 & 0x3800;
                  *((_WORD *)v64 + 21) = v94;
                }
                else
                {
                  *((_WORD *)v64 + 21) = v93;
                  v94 = v93;
                }
                *((_WORD *)v64 + 21) = v94 ^ (*(_WORD *)(v91 + 2) ^ v94) & 0x7FF;
LABEL_194:
                v70 = *v69;
                LODWORD(v67) = *v66;
                goto LABEL_200;
              }
              if ( v90 < 0x400u )
                goto LABEL_194;
              *(_WORD *)v64 |= 1u;
              v95 = *v73 - 1;
              *v73 = v95;
              if ( !v95 )
                goto LABEL_194;
              LOWORD(v77) = v95;
            }
          }
          *v66 = v67;
          *v73 = 0;
          *(_DWORD *)((char *)v64 + 22) = v72;
LABEL_200:
          if ( (*v70 & 0x40) != 0 )
          {
            v96 = *v66;
            *((_DWORD *)v65 + 9) = *v66;
            *v66 = v96 + 14;
            v245 = *(_QWORD *)FixedVarRecord::FindVersioningInfo(v64);
            v97 = HIWORD(v245);
            v98 = 0;
            if ( ((SHIWORD(v245) ^ ((unsigned int)SHIWORD(v245) >> 1)) & 0x2000) != 0 )
            {
              if ( (v245 & 0x4000000000000000LL) != 0 )
                LOWORD(v97) = HIWORD(v245) | 0x2000;
              else
                LOWORD(v97) = HIWORD(v245) & 0xDFFF;
            }
            if ( (_WORD)v97 == 0xFFFC )
              v98 = WORD2(v245) >> 5;
            *v66 += v98;
            LODWORD(v67) = *v66;
          }
          else
          {
            *((_DWORD *)v65 + 9) = 0;
          }
          v99 = *(_QWORD *)((char *)v64 + 28);
          v100 = v67;
          if ( v99 && v99 < (unsigned __int64)&(*v69)[(unsigned int)v67] )
          {
            ++v221;
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v101 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v101 )
              {
                v102 = *(_QWORD *)(v101 + 96);
                if ( v102 )
                {
                  if ( *(_BYTE *)(v102 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
              v64 = v219;
            }
            RaiseInconsistencyError(*v69, 18);
            v100 = *(_DWORD *)((char *)v227 + 2);
          }
          if ( (unsigned int)(v100 - 1) > 0x3F3B )
          {
            ++v221;
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v103 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v103 )
              {
                v104 = *(_QWORD *)(v103 + 96);
                if ( v104 )
                {
                  if ( *(_BYTE *)(v104 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
              v64 = v219;
            }
            RaiseInconsistencyError(*v69, 5);
          }
LABEL_234:
          v105 = *v66;
          if ( *v66 >= 9 || (v106 = **(_BYTE **)((char *)v64 + 6) & 0xE) != 0 && v106 != 12 )
          {
            v107 = *v66;
            v64 = v227;
            v7 = v232;
          }
          else
          {
            v107 = 9;
            v64 = v227;
            v7 = v232;
          }
        }
        if ( v230 > v107 )
        {
          v109 = v229;
          if ( *(_WORD *)v229 )
          {
            v154 = v228;
            v155 = *(_DWORD *)((char *)v228 + 2);
            if ( !v155 )
            {
              CDRecord::Resize(v228);
              v155 = *(_DWORD *)((char *)v154 + 2);
            }
            if ( v155 >= 9 || (v156 = *(_BYTE **)((char *)v154 + 6), (*v156 & 0x1C) != 0) && (*v156 & 0x1C) != 0xC )
              v224 = v155;
            else
              v224 = 9;
          }
          else
          {
            v110 = v228;
            v111 = v228;
            v219 = v228;
            v112 = v228;
            v113 = (unsigned int *)((char *)v228 + 2);
            if ( !*(_DWORD *)((char *)v228 + 2) )
            {
              v222 = 0;
              *(_WORD *)v228 = 0;
              v114 = *(unsigned int *)((char *)v110 + 14);
              v115 = (int *)((char *)v110 + 18);
              *(_DWORD *)((char *)v110 + 18) = v114;
              v116 = (char **)((char *)v110 + 6);
              v117 = *(char **)((char *)v110 + 6);
              v118 = *v117;
              v119 = v114;
              if ( (*v117 & 0x10) != 0 )
              {
                LODWORD(v114) = (((unsigned int)*(unsigned __int16 *)&v117[v114] + 7) >> 3) + v114 + 2;
                *v115 = v114;
                v118 = *v117;
                v119 = v114;
              }
              v120 = (_WORD *)((char *)v110 + 26);
              if ( (v118 & 0x20) != 0 )
              {
                v226[0] = &v117[(unsigned int)v114];
                v121 = *(_WORD *)v226[0];
                *v120 = *(_WORD *)v226[0];
                if ( !v121 )
                {
                  v222 = 1;
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v122 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v122 )
                    {
                      v123 = *(_QWORD *)(v122 + 96);
                      if ( v123 )
                      {
                        if ( *(_BYTE *)(v123 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          else
                            ex_raise(34, 68, 21, 1003);
                        }
                      }
                    }
                    v111 = v219;
                  }
                  RaiseInconsistencyError(*v116, 3);
                  v119 = *v115;
                }
                v124 = (unsigned __int16)*v120;
                v125 = v119 + 2 * (v124 + 1);
                v126 = (unsigned int *)((char *)v111 + 22);
                *(_DWORD *)((char *)v111 + 22) = v125;
                if ( v125 > 0x1F9E )
                {
                  ++v222;
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v127 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v127 )
                    {
                      v128 = *(_QWORD *)(v127 + 96);
                      if ( v128 )
                      {
                        if ( *(_BYTE *)(v128 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                    v111 = v219;
                  }
                  RaiseInconsistencyError(*v116, 4);
                  LOWORD(v124) = *v120;
                  v125 = *v126;
                }
                v129 = *(_WORD *)(v226[0] + 2LL * (unsigned __int16)v124) & 0x7FFF;
                *v113 = v129;
                if ( v125 > v129 )
                {
                  ++v222;
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v130 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v130 )
                    {
                      v131 = *(_QWORD *)(v130 + 96);
                      if ( v131 )
                      {
                        if ( *(_BYTE *)(v131 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                    v111 = v219;
                  }
                  RaiseInconsistencyError(*v116, 4);
                  LOWORD(v124) = *v120;
                }
                v132 = v228;
                while ( 1 )
                {
                  if ( *(__int16 *)(v226[0] + 2LL * ((unsigned int)(unsigned __int16)v124 - 1) + 2) >= 0 )
                    goto LABEL_302;
                  v133 = &(*v116)[*v115];
                  if ( (unsigned __int16)v124 == 1 )
                  {
                    v134 = *(_DWORD *)((char *)v132 + 22);
                    v135 = v134;
                    v136 = *(_WORD *)&v133[2 * (unsigned __int16)v124] & 0x7FFF;
                  }
                  else
                  {
                    v134 = *(_WORD *)&v133[2 * (unsigned __int16)v124 - 2] & 0x7FFF;
                    v135 = *(_DWORD *)((char *)v132 + 22);
                    v136 = *(_WORD *)&v133[2 * (unsigned __int16)v124] & 0x7FFF;
                    if ( v134 < v135 )
                      goto LABEL_294;
                  }
                  if ( v136 < v134 )
                  {
LABEL_294:
                    RaiseInconsistencyError(*v116, 7);
                    v135 = *(_DWORD *)((char *)v228 + 22);
                    v132 = v228;
                  }
                  v237 = v134;
                  if ( v134 < v135 || v134 > *v113 )
                  {
                    ++v222;
                    goto LABEL_342;
                  }
                  v137 = *(_WORD *)&(*v116)[v134];
                  if ( v137 == 5 )
                  {
                    *(_WORD *)v111 |= 2u;
                    --*v120;
                    *((_WORD *)v111 + 20) = v134;
                    v138 = *(_QWORD *)((char *)v111 + 6) + (unsigned __int16)v134;
                    v139 = *(_WORD *)(v138 + 2);
                    v140 = *((_WORD *)v111 + 21) & 0xC7FF;
                    if ( (v139 & 0x4000) != 0 )
                    {
                      v141 = v140 | v139 & 0x3800;
                      *((_WORD *)v111 + 21) = v141;
                    }
                    else
                    {
                      *((_WORD *)v111 + 21) = v140;
                      v141 = v140;
                    }
                    *((_WORD *)v111 + 21) = v141 ^ (*(_WORD *)(v138 + 2) ^ v141) & 0x7FF;
LABEL_302:
                    v117 = *v116;
                    LODWORD(v114) = *v113;
                    v110 = v228;
                    goto LABEL_308;
                  }
                  if ( v137 < 0x400u )
                    goto LABEL_302;
                  *(_WORD *)v111 |= 1u;
                  v142 = *v120 - 1;
                  *v120 = v142;
                  if ( !v142 )
                    goto LABEL_302;
                  LOWORD(v124) = v142;
                }
              }
              *v113 = v114;
              *v120 = 0;
              *(_DWORD *)((char *)v110 + 22) = v119;
LABEL_308:
              if ( (*v117 & 0x40) != 0 )
              {
                v143 = *v113;
                *((_DWORD *)v112 + 9) = *v113;
                *v113 = v143 + 14;
                v246 = *(_QWORD *)FixedVarRecord::FindVersioningInfo(v111);
                v144 = HIWORD(v246);
                v145 = 0;
                if ( ((SHIWORD(v246) ^ ((unsigned int)SHIWORD(v246) >> 1)) & 0x2000) != 0 )
                {
                  if ( (v246 & 0x4000000000000000LL) != 0 )
                    LOWORD(v144) = HIWORD(v246) | 0x2000;
                  else
                    LOWORD(v144) = HIWORD(v246) & 0xDFFF;
                }
                if ( (_WORD)v144 == 0xFFFC )
                  v145 = WORD2(v246) >> 5;
                *v113 += v145;
                LODWORD(v114) = *v113;
              }
              else
              {
                *((_DWORD *)v112 + 9) = 0;
              }
              v146 = *(_QWORD *)((char *)v111 + 28);
              v147 = v114;
              if ( v146 && v146 < (unsigned __int64)&(*v116)[(unsigned int)v114] )
              {
                ++v222;
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v148 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v148 )
                  {
                    v149 = *(_QWORD *)(v148 + 96);
                    if ( v149 )
                    {
                      if ( *(_BYTE *)(v149 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                  v111 = v219;
                }
                RaiseInconsistencyError(*v116, 18);
                v147 = *(_DWORD *)((char *)v110 + 2);
              }
              if ( (unsigned int)(v147 - 1) > 0x3F3B )
              {
                ++v222;
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v150 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v150 )
                  {
                    v151 = *(_QWORD *)(v150 + 96);
                    if ( v151 )
                    {
                      if ( *(_BYTE *)(v151 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                  v111 = v219;
                }
                RaiseInconsistencyError(*v116, 5);
              }
            }
LABEL_342:
            v152 = *v113;
            if ( *v113 >= 9 || (v153 = **(_BYTE **)((char *)v111 + 6) & 0xE) != 0 && v153 != 12 )
LABEL_345:
              v224 = v152;
LABEL_459:
            v154 = v228;
            v109 = v229;
          }
          v200 = (v224 >> 4) + 4;
          v201 = v238;
          *((_DWORD *)v238 + 5) = v200;
          v202 = 16LL * (unsigned int)v200;
          v203 = 6 * v200 + 8 * v200 + 28 + v202 + 56 + 2LL * (unsigned int)(2 * v200 + 4);
          v229 = (struct Record *)v203;
          *((_DWORD *)v201 + 4) = 1;
          *((_DWORD *)v201 + 6) = v203;
          v204 = v203 + 15;
          if ( v203 + 15 < v203 )
            v204 = 0xFFFFFFFFFFFFFF0LL;
          v205 = v204 & 0xFFFFFFFFFFFFFFF0uLL;
          v206 = alloca(v205);
          v207 = alloca(v205);
          *((_QWORD *)v201 + 9) = &v219;
          v208 = (char *)&v219 + v202 + 56;
          *((_QWORD *)v201 + 8) = v208;
          v209 = &v208[8 * v200 + 28];
          *((_QWORD *)v201 + 6) = v209;
          v210 = &v209[4 * v200];
          *((_QWORD *)v201 + 7) = v210;
          *((_QWORD *)v201 + 4) = &v210[2 * v200];
          *((_DWORD *)v201 + 10) = 0;
          *((_DWORD *)v201 + 4) = 2;
          *((_DWORD *)v201 + 3) = 0;
          v211 = v232;
          v212 = v227;
          if ( *(_WORD *)v232 )
            CDRecord::FindDiff(v227, v154, v201);
          else
            FixedVarRecord::FindDiff(v227, v154, v201);
          v213 = *((_DWORD *)v201 + 1) + 4 + 16 * *((_DWORD *)v201 + 10);
          v214 = v239;
          *v239 = v213;
          if ( v213 > 0xC8 )
          {
            ++*((_QWORD *)v241 + 23);
            *v214 = 0;
          }
          else
          {
            ModifyRowVector::GenerateVersionPayload(v201, v240, v213);
          }
          if ( (_BYTE)v231 )
          {
            if ( *(_WORD *)v211 )
              CDRecord::RestoreVerInfo(v212, (const struct RecVersionInfoWithPayload *)&v250);
            else
              FixedVarRecord::RestoreVerInfo(v212, (const struct RecVersionInfoWithPayload *)&v250);
          }
          if ( v225 )
          {
            if ( *(_WORD *)v109 )
              CDRecord::RestoreVerInfo(v154, (const struct RecVersionInfoWithPayload *)&v253);
            else
              FixedVarRecord::RestoreVerInfo(v154, (const struct RecVersionInfoWithPayload *)&v253);
          }
          *(_DWORD *)(v235 + 616) &= ~v234;
          ExcHandler::~ExcHandler((ExcHandler *)v249);
          goto LABEL_485;
        }
        if ( *(_WORD *)v7 )
        {
          if ( !v105 )
          {
            CDRecord::Resize(v64);
            v105 = *(_DWORD *)((char *)v64 + 2);
          }
          if ( v105 >= 9 || (v199 = *(_BYTE **)((char *)v64 + 6), (*v199 & 0x1C) != 0) && (*v199 & 0x1C) != 0xC )
          {
            v224 = v105;
            goto LABEL_459;
          }
        }
        else
        {
          v157 = v64;
          v219 = v64;
          v158 = v64;
          if ( v105 )
            goto LABEL_448;
          v223 = 0;
          *(_WORD *)v64 = 0;
          v159 = *(unsigned int *)((char *)v64 + 14);
          v160 = (int *)((char *)v64 + 18);
          *(_DWORD *)((char *)v64 + 18) = v159;
          v161 = (char **)((char *)v64 + 6);
          v162 = *(char **)((char *)v64 + 6);
          v163 = *v162;
          v164 = v159;
          if ( (*v162 & 0x10) != 0 )
          {
            LODWORD(v159) = (((unsigned int)*(unsigned __int16 *)&v162[v159] + 7) >> 3) + 2 + v159;
            *v160 = v159;
            v163 = *v162;
            v164 = v159;
          }
          v165 = (_WORD *)((char *)v64 + 26);
          if ( (v163 & 0x20) != 0 )
          {
            v226[0] = &v162[(unsigned int)v159];
            v166 = *(_WORD *)v226[0];
            *v165 = *(_WORD *)v226[0];
            if ( !v166 )
            {
              v223 = 1;
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
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
                v157 = v219;
              }
              RaiseInconsistencyError(*v161, 3);
              v164 = *v160;
            }
            v169 = (unsigned __int16)*v165;
            v170 = v164 + 2 * (v169 + 1);
            v171 = (unsigned int *)((char *)v157 + 22);
            *(_DWORD *)((char *)v157 + 22) = v170;
            if ( v170 > 0x1F9E )
            {
              ++v223;
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v172 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v172 )
                {
                  v173 = *(_QWORD *)(v172 + 96);
                  if ( v173 )
                  {
                    if ( *(_BYTE *)(v173 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
                v157 = v219;
              }
              RaiseInconsistencyError(*v161, 4);
              LOWORD(v169) = *v165;
              v170 = *v171;
            }
            v174 = *(_WORD *)(v226[0] + 2LL * (unsigned __int16)v169) & 0x7FFF;
            v175 = (unsigned int *)((char *)v157 + 2);
            *(_DWORD *)((char *)v157 + 2) = v174;
            if ( v170 > v174 )
            {
              ++v223;
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v176 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v176 )
                {
                  v177 = *(_QWORD *)(v176 + 96);
                  if ( v177 )
                  {
                    if ( *(_BYTE *)(v177 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
                v157 = v219;
              }
              RaiseInconsistencyError(*v161, 4);
              LOWORD(v169) = *v165;
            }
            v178 = v227;
            while ( 1 )
            {
              if ( *(__int16 *)(v226[0] + 2LL * ((unsigned int)(unsigned __int16)v169 - 1) + 2) >= 0 )
                goto LABEL_408;
              v179 = &(*v161)[*v160];
              if ( (unsigned __int16)v169 == 1 )
              {
                v180 = *(_DWORD *)((char *)v178 + 22);
                v181 = v180;
                v182 = *(_WORD *)&v179[2 * (unsigned __int16)v169] & 0x7FFF;
              }
              else
              {
                v180 = *(_WORD *)&v179[2 * (unsigned __int16)v169 - 2] & 0x7FFF;
                v181 = *(_DWORD *)((char *)v178 + 22);
                v182 = *(_WORD *)&v179[2 * (unsigned __int16)v169] & 0x7FFF;
                if ( v180 < v181 )
                  goto LABEL_400;
              }
              if ( v182 < v180 )
              {
LABEL_400:
                RaiseInconsistencyError(*v161, 7);
                v181 = *(_DWORD *)((char *)v227 + 22);
                v178 = v227;
              }
              v224 = v180;
              if ( v180 < v181 || v180 > *v175 )
              {
                ++v223;
                goto LABEL_448;
              }
              v183 = *(_WORD *)&(*v161)[v180];
              if ( v183 == 5 )
              {
                *(_WORD *)v157 |= 2u;
                --*v165;
                *((_WORD *)v157 + 20) = v180;
                v184 = *(_QWORD *)((char *)v157 + 6) + (unsigned __int16)v180;
                v185 = *(_WORD *)(v184 + 2);
                v186 = *((_WORD *)v157 + 21) & 0xC7FF;
                if ( (v185 & 0x4000) != 0 )
                {
                  v187 = v186 | v185 & 0x3800;
                  *((_WORD *)v157 + 21) = v187;
                }
                else
                {
                  *((_WORD *)v157 + 21) = v186;
                  v187 = v186;
                }
                *((_WORD *)v157 + 21) = v187 ^ (*(_WORD *)(v184 + 2) ^ v187) & 0x7FF;
LABEL_408:
                v162 = *v161;
                v64 = v227;
                goto LABEL_414;
              }
              if ( v183 < 0x400u )
                goto LABEL_408;
              *(_WORD *)v157 |= 1u;
              v188 = *v165 - 1;
              *v165 = v188;
              if ( !v188 )
                goto LABEL_408;
              LOWORD(v169) = v188;
            }
          }
          v175 = (unsigned int *)((char *)v64 + 2);
          *(_DWORD *)((char *)v64 + 2) = v159;
          *v165 = 0;
          *(_DWORD *)((char *)v64 + 22) = v164;
LABEL_414:
          if ( (*v162 & 0x40) != 0 )
          {
            *((_DWORD *)v158 + 9) = *v175;
            *v175 += 14;
            v247 = *(_QWORD *)FixedVarRecord::FindVersioningInfo(v157);
            v189 = HIWORD(v247);
            v190 = 0;
            if ( ((SHIWORD(v247) ^ ((unsigned int)SHIWORD(v247) >> 1)) & 0x2000) != 0 )
            {
              if ( (v247 & 0x4000000000000000LL) != 0 )
                LOWORD(v189) = HIWORD(v247) | 0x2000;
              else
                LOWORD(v189) = HIWORD(v247) & 0xDFFF;
            }
            if ( (_WORD)v189 == 0xFFFC )
              v190 = WORD2(v247) >> 5;
            *v175 += v190;
            v191 = *v175;
          }
          else
          {
            *((_DWORD *)v158 + 9) = 0;
            v191 = *(unsigned int *)((char *)v64 + 2);
          }
          v192 = *(_QWORD *)((char *)v157 + 28);
          v193 = v191;
          if ( v192 && v192 < (unsigned __int64)&(*v161)[v191] )
          {
            ++v223;
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v194 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v194 )
              {
                v195 = *(_QWORD *)(v194 + 96);
                if ( v195 )
                {
                  if ( *(_BYTE *)(v195 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
              v157 = v219;
            }
            RaiseInconsistencyError(*v161, 18);
            v193 = *(_DWORD *)((char *)v64 + 2);
          }
          if ( (unsigned int)(v193 - 1) > 0x3F3B )
          {
            ++v223;
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v196 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v196 )
              {
                v197 = *(_QWORD *)(v196 + 96);
                if ( v197 )
                {
                  if ( *(_BYTE *)(v197 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
              v157 = v219;
            }
            RaiseInconsistencyError(*v161, 5);
          }
LABEL_448:
          v152 = *(_DWORD *)((char *)v157 + 2);
          if ( v152 >= 9 )
            goto LABEL_345;
          v198 = **(_BYTE **)((char *)v157 + 6) & 0xE;
          if ( v198 )
          {
            if ( v198 != 12 )
              goto LABEL_345;
            v224 = 9;
            goto LABEL_459;
          }
        }
        v224 = 9;
        goto LABEL_459;
      }
      if ( v46 < 0x400u )
        goto LABEL_90;
      *(_WORD *)v21 |= 1u;
      v50 = *v29 - 1;
      *v29 = v50;
      if ( !v50 )
        goto LABEL_90;
      LOWORD(v33) = v50;
    }
  }
  catch ( SQLError v248 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)&v234, (const struct SQLError *)v248);
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)&v234);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)&v234);
    }
    catch ( ShortStackException )
    {
    }
    v214 = v242;
  }
LABEL_485:
  v215 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v216 = *(struct Worker **)(v215 + 256);
  if ( !v216 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v216 = *(struct Worker **)(v215 + 256);
  }
  if ( *((_DWORD *)v216 + 139) )
    ExceptionPostCatchActions(v216);
  return *v214 != 0;
}

```

## disassembly

```asm
0x1018d0f10  push    rbp
0x1018d0f12  push    rbx
0x1018d0f13  push    rsi
0x1018d0f14  push    rdi
0x1018d0f15  push    r12
0x1018d0f17  push    r13
0x1018d0f19  push    r14
0x1018d0f1b  push    r15
0x1018d0f1d  sub     rsp, 318h
0x1018d0f24  lea     rbp, [rsp+30h]
0x1018d0f29  mov     [rbp+320h+var_278], 0FFFFFFFFFFFFFFFEh
0x1018d0f34  mov     rax, cs:__security_cookie
0x1018d0f3b  xor     rax, rbp
0x1018d0f3e  mov     [rbp+320h+var_50], rax
0x1018d0f45  mov     [rbp+320h+var_2A0], r9
0x1018d0f4c  mov     r12, r8
0x1018d0f4f  mov     [rbp+320h+var_288], r8
0x1018d0f56  mov     [rbp+320h+var_290], rdx
0x1018d0f5d  mov     [rbp+320h+var_298], rcx
0x1018d0f64  mov     [rbp+320h+var_280], rcx
0x1018d0f6b  mov     r15, [rbp+320h+arg_20]
0x1018d0f72  mov     [rbp+320h+var_2D8], r15
0x1018d0f76  mov     r13, [rbp+320h+arg_28]
0x1018d0f7d  mov     [rbp+320h+var_2C8], r13
0x1018d0f81  xor     esi, esi
0x1018d0f83  mov     [rbp+320h+var_320], rsi
0x1018d0f87  mov     eax, esi
0x1018d0f89  mov     [rbp+320h+var_210], rax
0x1018d0f90  mov     [rbp+320h+var_208], esi
0x1018d0f96  mov     [rbp+320h+var_204], si
0x1018d0f9d  mov     [rbp+320h+var_320], rsi
0x1018d0fa1  mov     [rbp+320h+var_130], rax
0x1018d0fa8  mov     [rbp+320h+var_128], esi
0x1018d0fae  mov     [rbp+320h+var_124], si
0x1018d0fb5  mov     rax, [r13+8]
0x1018d0fb9  movzx   r14d, byte ptr [rax]
0x1018d0fbd  cmp     [r13+0], si
0x1018d0fc2  jnz     short loc_1018D0FCA
0x1018d0fc4  shr     r14d, 6
0x1018d0fc8  jmp     short loc_1018D0FCD
0x1018d0fca  shr     r14d, 1
0x1018d0fcd  and     r14d, 1
0x1018d0fd1  mov     [rbp+320h+var_2CC], r14d
0x1018d0fd5  mov     [rbp+320h+var_304], sil
0x1018d0fd9  xor     edx, edx; unsigned __int16
0x1018d0fdb  mov     [rsp+350h+var_328], rsi; struct Worker *
0x1018d0fe0  mov     rax, cs:__imp_?NoThrowHandler@@YAHHHHHPEAD@Z; NoThrowHandler(int,int,int,int,char *)
0x1018d0fe7  mov     [rsp+350h+var_330], rax; int (*)(int, int, int, int, char *)
0x1018d0fec  xor     r9d, r9d; unsigned __int8
0x1018d0fef  xor     r8d, r8d; unsigned __int8
0x1018d0ff2  lea     rcx, [rbp+320h+var_238]; this
0x1018d0ff9  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x1018d0ffe  nop
0x1018d0fff  mov     edx, 1
0x1018d1004  lea     rcx, [rbp+320h+var_2B8]
0x1018d1008  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x1018d100d  nop
0x1018d100e  movzx   edx, word ptr [r15]
0x1018d1012  mov     rax, [r15+8]
0x1018d1016  movzx   ecx, byte ptr [rax]
0x1018d1019  test    dx, dx
0x1018d101c  jnz     short loc_1018D1023
0x1018d101e  shr     ecx, 6
0x1018d1021  jmp     short loc_1018D1025
0x1018d1023  shr     ecx, 1
0x1018d1025  and     ecx, 1
0x1018d1028  test    ecx, ecx
0x1018d102a  jz      loc_1018D1109
0x1018d1030  lea     rcx, [r15+2]
0x1018d1034  test    dx, dx
0x1018d1037  lea     rdx, [rbp+320h+var_300]
0x1018d103b  jnz     short loc_1018D1044
0x1018d103d  call    ?GetXdesTs@FixedVarRecord@@AEBA?AVXdesTs@@XZ; FixedVarRecord::GetXdesTs(void)
0x1018d1042  jmp     short loc_1018D1049
0x1018d1044  call    ?GetXdesTs@CDRecord@@AEBA?AVXdesTs@@XZ; CDRecord::GetXdesTs(void)
0x1018d1049  mov     esi, dword ptr [rbp+320h+var_300]
0x1018d104c  mov     dword ptr [rbp+320h+var_2E0], esi
0x1018d104f  movzx   edi, word ptr [rbp+320h+var_300+4]
0x1018d1053  mov     word ptr [rbp+320h+var_2E0+4], di
0x1018d1057  xor     eax, eax
0x1018d1059  mov     dword ptr [rbp+320h+var_300], eax
0x1018d105c  mov     word ptr [rbp+320h+var_300+4], ax
0x1018d1060  lea     rcx, [r12+19C8h]; this
0x1018d1068  lea     rdx, [rbp+320h+var_300]; struct XdesId *
0x1018d106c  call    ?GetOldestActiveXdesId@XdesMgr@@QEAAXAEAVXdesId@@@Z; XdesMgr::GetOldestActiveXdesId(XdesId &)
0x1018d1071  xor     eax, eax
0x1018d1073  mov     dword ptr [rbp+320h+var_320], eax
0x1018d1076  mov     word ptr [rbp+320h+var_320+4], ax
0x1018d107a  cmp     ax, di
0x1018d107d  jnz     short loc_1018D1083
0x1018d107f  test    esi, esi
0x1018d1081  jz      short loc_1018D10CA
0x1018d1083  mov     dword ptr [rbp+320h+var_2F0], esi
0x1018d1086  mov     word ptr [rbp+320h+var_2F0+4], di
0x1018d108a  lea     rdx, [rbp+320h+var_2C0]
0x1018d108e  lea     rcx, [r15+2]
0x1018d1092  cmp     [r15], ax
0x1018d1096  jnz     short loc_1018D109F
0x1018d1098  call    ?GetVersionRecPtr@FixedVarRecord@@AEBA?AVVersionRecPtr@@XZ; FixedVarRecord::GetVersionRecPtr(void)
0x1018d109d  jmp     short loc_1018D10A4
0x1018d109f  call    ?GetVersionRecPtr@CDRecord@@AEBA?AVVersionRecPtr@@XZ; CDRecord::GetVersionRecPtr(void)
0x1018d10a4  lea     r8, [rbp+320h+var_2C0]
0x1018d10a8  lea     rdx, [rbp+320h+var_2F0]
0x1018d10ac  mov     rcx, [r12+6B0h]
0x1018d10b4  call    ?IsTimestampInteresting@VersionMgr@@SA_NPEAVDBTABLE@@VXdesTs@@PEAVVersionRecPtr@@@Z; VersionMgr::IsTimestampInteresting(DBTABLE *,XdesTs,VersionRecPtr *)
0x1018d10b9  test    al, al
0x1018d10bb  jnz     short loc_1018D1107
0x1018d10bd  cmp     word ptr [rbp+320h+var_300+4], di
0x1018d10c1  ja      short loc_1018D10CA
0x1018d10c3  jnz     short loc_1018D1107
0x1018d10c5  cmp     dword ptr [rbp+320h+var_300], esi
0x1018d10c8  jbe     short loc_1018D1107
0x1018d10ca  mov     [rbp+320h+var_304], 1
0x1018d10ce  lea     rdx, [rbp+320h+var_320]
0x1018d10d2  lea     rcx, [r15+2]
0x1018d10d6  cmp     word ptr [r15], 0
0x1018d10db  jnz     short loc_1018D10E4
0x1018d10dd  call    ?GetVersionRecPtr@FixedVarRecord@@AEBA?AVVersionRecPtr@@XZ; FixedVarRecord::GetVersionRecPtr(void)
0x1018d10e2  jmp     short loc_1018D10E9
0x1018d10e4  call    ?GetVersionRecPtr@CDRecord@@AEBA?AVVersionRecPtr@@XZ; CDRecord::GetVersionRecPtr(void)
0x1018d10e9  lea     rdx, [rbp+320h+var_130]; Destination
0x1018d10f0  lea     rcx, [r15+2]; this
0x1018d10f4  cmp     word ptr [r15], 0
0x1018d10f9  jnz     short loc_1018D1102
0x1018d10fb  call    ?StripVerInfo@FixedVarRecord@@AEAAXAEAVRecVersionInfoWithPayload@@@Z; FixedVarRecord::StripVerInfo(RecVersionInfoWithPayload &)
0x1018d1100  jmp     short loc_1018D1107
0x1018d1102  call    ?StripVerInfo@CDRecord@@AEAAXAEAVRecVersionInfoWithPayload@@@Z; CDRecord::StripVerInfo(RecVersionInfoWithPayload &)
0x1018d1107  xor     esi, esi
0x1018d1109  test    r14b, r14b
0x1018d110c  jz      short loc_1018D112D
0x1018d110e  lea     rcx, [r13+2]; this
0x1018d1112  lea     rdx, [rbp+320h+var_210]; Destination
0x1018d1119  cmp     word ptr [r13+0], 0
0x1018d111f  jnz     short loc_1018D1128
0x1018d1121  call    ?StripVerInfo@FixedVarRecord@@AEAAXAEAVRecVersionInfoWithPayload@@@Z; FixedVarRecord::StripVerInfo(RecVersionInfoWithPayload &)
0x1018d1126  jmp     short loc_1018D112D
0x1018d1128  call    ?StripVerInfo@CDRecord@@AEAAXAEAVRecVersionInfoWithPayload@@@Z; CDRecord::StripVerInfo(RecVersionInfoWithPayload &)
0x1018d112d  lea     rdi, [r15+2]
0x1018d1131  mov     [rbp+320h+var_2E0], rdi
0x1018d1135  cmp     word ptr [r15], 0
0x1018d113a  jnz     loc_1018D17F5
0x1018d1140  mov     rbx, rdi
0x1018d1143  mov     [rbp+320h+var_320], rbx
0x1018d1147  mov     r13, rdi
0x1018d114a  lea     r12, [rdi+2]
0x1018d114e  cmp     dword ptr [r12], 0
0x1018d1153  jnz     loc_1018D17B8
0x1018d1159  mov     [rbp+320h+var_318], esi
0x1018d115c  mov     [rdi], si
0x1018d115f  mov     edx, [rdi+0Eh]
0x1018d1162  lea     r14, [rdi+12h]
0x1018d1166  mov     [r14], edx
0x1018d1169  lea     r15, [rdi+6]
0x1018d116d  mov     r8, [r15]
0x1018d1170  movzx   eax, byte ptr [r8]
0x1018d1174  mov     ecx, edx
0x1018d1176  test    al, 10h
0x1018d1178  jz      short loc_1018D1193
0x1018d117a  movzx   ecx, word ptr [rdx+r8]
0x1018d117f  add     ecx, 7
0x1018d1182  shr     ecx, 3
0x1018d1185  add     edx, 2
0x1018d1188  add     edx, ecx
0x1018d118a  mov     [r14], edx
0x1018d118d  movzx   eax, byte ptr [r8]
0x1018d1191  mov     ecx, edx
0x1018d1193  lea     rsi, [rdi+1Ah]
0x1018d1197  test    al, 20h
0x1018d1199  jz      loc_1018D1589
0x1018d119f  mov     eax, edx
0x1018d11a1  add     rax, r8
0x1018d11a4  mov     [rbp+320h+var_2F0], rax
0x1018d11a8  movzx   eax, word ptr [rax]
0x1018d11ab  mov     [rsi], ax
0x1018d11ae  test    ax, ax
0x1018d11b1  jnz     loc_1018D1275
0x1018d11b7  mov     [rbp+320h+var_318], 1
0x1018d11be  cmp     cs:byte_10316E8D7, al
0x1018d11c4  jnz     short loc_1018D11D3
0x1018d11c6  test    byte ptr cs:qword_10317B120, 1
0x1018d11cd  jz      loc_1018D1265
0x1018d11d3  mov     r8, gs:58h
0x1018d11dc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1018d11e3  mov     ecx, [rax]
0x1018d11e5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1018d11ec  mov     edx, [rax]
0x1018d11ee  add     rdx, [r8+rcx*8]
0x1018d11f2  mov     rax, [rdx+8]
0x1018d11f6  test    rax, rax
0x1018d11f9  jz      short loc_1018D1261
0x1018d11fb  mov     rax, [rax+60h]
0x1018d11ff  test    rax, rax
0x1018d1202  jz      short loc_1018D1261
0x1018d1204  cmp     byte ptr [rax+499h], 0
0x1018d120b  jz      short loc_1018D1261
0x1018d120d  cmp     cs:byte_10316E7C7, 0
0x1018d1214  jnz     short loc_1018D1239
0x1018d1216  test    byte ptr cs:qword_10317B120, 2
0x1018d121d  jnz     short loc_1018D1239
0x1018d121f  mov     edx, 44h ; 'D'
0x1018d1224  lea     ecx, [rdx-22h]
0x1018d1227  mov     r9d, 3EBh
0x1018d122d  lea     r8d, [rdx-2Fh]
0x1018d1231  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1018d1237  jmp     short loc_1018D1261
0x1018d1239  mov     [rsp+350h+var_330], 0
0x1018d1242  mov     r9d, 7DAh
0x1018d1248  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x1018d124f  lea     rdx, aFalse; "false"
0x1018d1256  mov     ecx, 1
0x1018d125b  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1018d1261  mov     rbx, [rbp+320h+var_320]
0x1018d1265  mov     edx, 3
0x1018d126a  mov     rcx, [r15]
0x1018d126d  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x1018d1272  mov     ecx, [r14]
0x1018d1275  movzx   r8d, word ptr [rsi]
0x1018d1279  lea     r9d, [r8+1]
0x1018d127d  lea     r9d, [rcx+r9*2]
0x1018d1281  lea     rdi, [rbx+16h]
0x1018d1285  mov     [rdi], r9d
0x1018d1288  cmp     r9d, 1F9Eh
0x1018d128f  jbe     loc_1018D1354
0x1018d1295  inc     [rbp+320h+var_318]
0x1018d1298  cmp     cs:byte_10316E8D7, 0
0x1018d129f  jnz     short loc_1018D12AE
0x1018d12a1  test    byte ptr cs:qword_10317B120, 1
0x1018d12a8  jz      loc_1018D1340
0x1018d12ae  mov     r8, gs:58h
0x1018d12b7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1018d12be  mov     ecx, [rax]
0x1018d12c0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1018d12c7  mov     edx, [rax]
0x1018d12c9  add     rdx, [r8+rcx*8]
0x1018d12cd  mov     rax, [rdx+8]
0x1018d12d1  test    rax, rax
0x1018d12d4  jz      short loc_1018D133C
0x1018d12d6  mov     rax, [rax+60h]
0x1018d12da  test    rax, rax
0x1018d12dd  jz      short loc_1018D133C
0x1018d12df  cmp     byte ptr [rax+499h], 0
0x1018d12e6  jz      short loc_1018D133C
0x1018d12e8  cmp     cs:byte_10316E7C7, 0
0x1018d12ef  jnz     short loc_1018D1314
0x1018d12f1  test    byte ptr cs:qword_10317B120, 2
0x1018d12f8  jnz     short loc_1018D1314
0x1018d12fa  mov     edx, 44h ; 'D'
0x1018d12ff  lea     ecx, [rdx-22h]
0x1018d1302  mov     r9d, 3ECh
0x1018d1308  lea     r8d, [rdx-2Fh]
0x1018d130c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1018d1312  jmp     short loc_1018D133C
0x1018d1314  mov     [rsp+350h+var_330], 0
0x1018d131d  mov     r9d, 7E1h
0x1018d1323  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x1018d132a  lea     rdx, aFalse; "false"
0x1018d1331  mov     ecx, 1
0x1018d1336  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1018d133c  mov     rbx, [rbp+320h+var_320]
0x1018d1340  mov     edx, 4
0x1018d1345  mov     rcx, [r15]
0x1018d1348  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x1018d134d  movzx   r8d, word ptr [rsi]
0x1018d1351  mov     r9d, [rdi]
0x1018d1354  movzx   ecx, r8w
0x1018d1358  mov     rax, [rbp+320h+var_2F0]
0x1018d135c  movzx   edx, word ptr [rax+rcx*2]
0x1018d1360  and     edx, 7FFFh
0x1018d1366  mov     [r12], edx
0x1018d136a  cmp     r9d, edx
0x1018d136d  jbe     loc_1018D142F
0x1018d1373  inc     [rbp+320h+var_318]
0x1018d1376  cmp     cs:byte_10316E8D7, 0
0x1018d137d  jnz     short loc_1018D138C
0x1018d137f  test    byte ptr cs:qword_10317B120, 1
0x1018d1386  jz      loc_1018D141E
0x1018d138c  mov     r8, gs:58h
0x1018d1395  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1018d139c  mov     ecx, [rax]
0x1018d139e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1018d13a5  mov     edx, [rax]
0x1018d13a7  add     rdx, [r8+rcx*8]
0x1018d13ab  mov     rax, [rdx+8]
0x1018d13af  test    rax, rax
0x1018d13b2  jz      short loc_1018D141A
0x1018d13b4  mov     rax, [rax+60h]
0x1018d13b8  test    rax, rax
0x1018d13bb  jz      short loc_1018D141A
0x1018d13bd  cmp     byte ptr [rax+499h], 0
0x1018d13c4  jz      short loc_1018D141A
0x1018d13c6  cmp     cs:byte_10316E7C7, 0
0x1018d13cd  jnz     short loc_1018D13F2
0x1018d13cf  test    byte ptr cs:qword_10317B120, 2
0x1018d13d6  jnz     short loc_1018D13F2
0x1018d13d8  mov     edx, 44h ; 'D'
0x1018d13dd  lea     ecx, [rdx-22h]
0x1018d13e0  mov     r9d, 3ECh
0x1018d13e6  lea     r8d, [rdx-2Fh]
0x1018d13ea  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1018d13f0  jmp     short loc_1018D141A
  ... truncated ...
```
