# BTreeMgr::Seek(SEBindings const *,BTreeMgr::BTREE_SEEK_OPTION,BTreeMgr::BTREE_TRAVERSAL_MODE,int,BTreeHPage *,SearchInfo &,PrefetchObject *)

- ea: `0x100412840`
- end: `0x100412b89`
- name: `?Seek@BTreeMgr@@AEAA?AW4SeekRetCode@1@PEBVSEBindings@@W4BTREE_SEEK_OPTION@1@W4BTREE_TRAVERSAL_MODE@1@HPEAVBTreeHPage@@AEAVSearchInfo@@PEAVPrefetchObject@@@Z`
- size: `841`
- prototype: `enum BTreeMgr::SeekRetCode __high(const struct SEBindings *, enum BTreeMgr::BTREE_SEEK_OPTION, enum BTreeMgr::BTREE_TRAVERSAL_MODE, int, struct BTreeHPage *, struct SearchInfo *, struct PrefetchObject *)`
- caller_count: `9`
- callee_count: `84`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100413d00`
- `0x1004365d0`
- `0x1004b0a30`
- `0x1004b17f0`
- `0x101292690`
- `0x1012b9800`
- `0x1012be240`
- `0x1014beb30`
- `0x1014c4ea0`

## callees

- `0x100401010`
- `0x100401490`
- `0x100403030`
- `0x10040d950`
- `0x10040da40`
- `0x10040da80`
- `0x10040eca0`
- `0x10040fc00`
- `0x1004126a0`
- `0x100412840`
- `0x100412b90`
- `0x1004141b0`
- `0x1004145f0`
- `0x100420130`
- `0x100432c80`
- `0x1004375f0`
- `0x10043ba50`
- `0x100441e00`
- `0x100449090`
- `0x10046bf90`
- `0x1004729d0`
- `0x100472a40`
- `0x10047ffb0`
- `0x100480030`
- `0x10049a590`
- `0x10049a5d0`
- `0x1004b0ec0`
- `0x1004b1d60`
- `0x1004b1d70`
- `0x1004bf030`
- `0x100530d50`
- `0x100545bf0`
- `0x100553e20`
- `0x1005bbfc0`
- `0x1005d9f70`
- `0x100626480`
- `0x10069f4f0`
- `0x1006f5330`
- `0x100720360`
- `0x1007e06b0`
- `0x100b10220`
- `0x10121e820`
- `0x101253de0`
- `0x101253e00`
- `0x101253e60`
- `0x101253eb0`
- `0x10125c1f0`
- `0x10125c210`
- `0x101279020`
- `0x1012c5bd0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10129ab70`
- `KERNEL32!VirtualProtect` at `0x10129acb2`
- `KERNEL32!VirtualProtect` at `0x10129baec`
- `KERNEL32!VirtualProtect` at `0x10129bbed`
- `KERNEL32!VirtualProtect` at `0x10129bd59`
- `KERNEL32!VirtualProtect` at `0x10129c440`
- `KERNEL32!VirtualProtect` at `0x10129c61d`
- `KERNEL32!VirtualProtect` at `0x10129c8e1`
- `KERNEL32!VirtualProtect` at `0x10129d10b`
- `KERNEL32!VirtualProtect` at `0x10129d20c`
- `KERNEL32!VirtualProtect` at `0x10129d372`
- `KERNEL32!VirtualProtect` at `0x10129dab6`
- `KERNEL32!VirtualProtect` at `0x10129ec19`
- `KERNEL32!VirtualProtect` at `0x10129edbf`
- `KERNEL32!VirtualProtect` at `0x10129ef18`
- `KERNEL32!VirtualProtect` at `0x10129f016`
- `KERNEL32!VirtualProtect` at `0x10129f16a`
- `KERNEL32!VirtualProtect` at `0x10129f28a`
- `KERNEL32!VirtualProtect` at `0x10129f39d`
- `KERNEL32!VirtualProtect` at `0x10129ab70`
- `KERNEL32!VirtualProtect` at `0x10129acb2`
- `KERNEL32!VirtualProtect` at `0x10129baec`
- `KERNEL32!VirtualProtect` at `0x10129bbed`
- `KERNEL32!VirtualProtect` at `0x10129bd59`
- `KERNEL32!VirtualProtect` at `0x10129c440`
- `KERNEL32!VirtualProtect` at `0x10129c61d`
- `KERNEL32!VirtualProtect` at `0x10129c8e1`
- `KERNEL32!VirtualProtect` at `0x10129d10b`
- `KERNEL32!VirtualProtect` at `0x10129d20c`
- `KERNEL32!VirtualProtect` at `0x10129d372`
- `KERNEL32!VirtualProtect` at `0x10129dab6`
- `KERNEL32!VirtualProtect` at `0x10129ec19`
- `KERNEL32!VirtualProtect` at `0x10129edbf`
- `KERNEL32!VirtualProtect` at `0x10129ef18`
- `KERNEL32!VirtualProtect` at `0x10129f016`
- `KERNEL32!VirtualProtect` at `0x10129f16a`
- `KERNEL32!VirtualProtect` at `0x10129f28a`
- `KERNEL32!VirtualProtect` at `0x10129f39d`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10129b1cf`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10129c0af`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10129d6cf`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10041fd49`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10129b506`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10129cb39`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100412942`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129aa2f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129c6ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129deb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129df63`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e185`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e245`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e2e8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e64c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e675`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e6a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e969`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e992`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129aa2f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129c6ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129deb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129df63`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e185`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e245`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e2e8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e64c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e675`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e6a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e969`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e992`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e423`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e4a6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e530`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e80c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e875`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e423`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e4a6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e530`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e80c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e875`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10129aaa6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10129b55c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10129cb8e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10129aaa6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10129b55c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10129cb8e`
- `sqldk!SystemThread_TlsIndex` at `0x10041fcb8`
- `sqldk!SystemThread_TlsIndex` at `0x10041fd6f`
- `sqldk!SystemThread_TlsIndex` at `0x10041fda6`
- `sqldk!SystemThread_TlsIndex` at `0x10129aeab`
- `sqldk!SystemThread_TlsIndex` at `0x10129b459`
- `sqldk!SystemThread_TlsIndex` at `0x10129b52c`
- `sqldk!SystemThread_TlsIndex` at `0x10129b573`
- `sqldk!SystemThread_TlsIndex` at `0x10129b887`
- `sqldk!SystemThread_TlsIndex` at `0x10129b8c8`
- `sqldk!SystemThread_TlsIndex` at `0x10129ca8c`
- `sqldk!SystemThread_TlsIndex` at `0x10129cb5f`
- `sqldk!SystemThread_TlsIndex` at `0x10129cba5`
- `sqldk!SystemThread_TlsIndex` at `0x10129ceae`
- `sqldk!SystemThread_TlsIndex` at `0x10129ceee`
- `sqldk!SystemThread_TlsOffset` at `0x10041fcc1`
- `sqldk!SystemThread_TlsOffset` at `0x10041fd78`
- `sqldk!SystemThread_TlsOffset` at `0x10041fdaf`
- `sqldk!SystemThread_TlsOffset` at `0x10129aeb4`
- `sqldk!SystemThread_TlsOffset` at `0x10129b462`
- `sqldk!SystemThread_TlsOffset` at `0x10129b535`
- `sqldk!SystemThread_TlsOffset` at `0x10129b57c`
- `sqldk!SystemThread_TlsOffset` at `0x10129b890`
- `sqldk!SystemThread_TlsOffset` at `0x10129b8d1`
- `sqldk!SystemThread_TlsOffset` at `0x10129ca95`
- `sqldk!SystemThread_TlsOffset` at `0x10129cb68`
- `sqldk!SystemThread_TlsOffset` at `0x10129cbae`
- `sqldk!SystemThread_TlsOffset` at `0x10129ceb7`
- `sqldk!SystemThread_TlsOffset` at `0x10129cef7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129aa8e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129b47d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129cab0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129aa8e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129b47d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129cab0`

## string_xrefs

- `0x10129aa1c`: `Sql\Ntdbms\storeng\dfs\access\BTreeMgr.inl`
- `0x10129c6db`: `Sql\Ntdbms\storeng\dfs\access\BTreeMgr.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall BTreeMgr::Seek(
        BTreeMgr *a1,
        const struct SEBindings *a2,
        int a3,
        unsigned int a4,
        int a5,
        PageRef *a6,
        SearchInfo *a7,
        struct PrefetchObject *a8)
{
  BTreeMgr *v10; // r13
  struct PrefetchObject *v11; // rcx
  int v12; // r15d
  int v13; // ebx
  const struct HoBtAccess *v14; // rsi
  PhysicalColumnAttribute *v15; // r12
  _QWORD *ObjectDataImpl; // rax
  int v17; // ecx
  __int64 v18; // rax
  int v19; // eax
  SearchInfo *v20; // rax
  int *v21; // r14
  int v22; // r9d
  SearchInfo *v23; // rbx
  int v24; // esi
  int v25; // r14d
  unsigned int v26; // edi
  int v27; // edx
  int v28; // eax
  char v29; // cl
  char v30; // r15
  PageRef *v31; // rsi
  int v33; // eax
  __int64 v34; // r14
  unsigned __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rbx
  _QWORD *v39; // r8
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rcx
  __int64 v42; // rcx
  char v43; // r13
  char v44; // r12
  __int64 v45; // rdx
  struct CSessionTraceFlags *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // r15
  _QWORD *v49; // rsi
  unsigned int v50; // edi
  Page **v51; // rax
  unsigned int v52; // edx
  Page *v53; // rcx
  __int64 v54; // rax
  unsigned int v55; // r8d
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v57; // r8
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 v61; // r12
  __int64 v62; // rsi
  Page *v63; // rcx
  __int64 v64; // rax
  int v65; // r15d
  __int16 v66; // dx
  __int16 v67; // ax
  Page *v68; // r14
  unsigned int v69; // edi
  SearchInfo *v70; // rbx
  int v71; // edx
  unsigned int v72; // edi
  volatile signed __int32 *v73; // rbx
  int v74; // ebx
  __int64 v75; // rdi
  Page *v76; // r14
  _BYTE *v77; // rax
  unsigned __int8 *v78; // rbx
  __int16 v79; // cx
  unsigned __int16 v80; // dx
  bool v81; // cc
  unsigned int v82; // ecx
  unsigned int v83; // edi
  Page **v84; // rbx
  unsigned int v85; // edi
  volatile signed __int32 *v86; // rbx
  __int64 v87; // rax
  __int64 v88; // rax
  bool v89; // zf
  __int64 v90; // rax
  int v91; // edx
  int v92; // edx
  unsigned __int16 v93; // dx
  unsigned int v94; // ecx
  unsigned int v95; // ecx
  int v96; // eax
  unsigned int v97; // edi
  Page **v98; // rbx
  Page *v99; // rax
  __int64 v100; // rcx
  unsigned int v101; // edi
  Page **v102; // rbx
  Page *v103; // rax
  __int64 v104; // rcx
  Page *v105; // r11
  char v106; // al
  int v107; // eax
  unsigned int v108; // ecx
  int v109; // eax
  unsigned int v110; // ecx
  LSN v111; // xmm0_8
  unsigned __int16 v112; // bx
  Page *v113; // r11
  char v114; // al
  unsigned __int16 v115; // r11
  __int64 v116; // r10
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rax
  int *v120; // rdx
  __int64 v121; // rcx
  int v122; // ecx
  int **v123; // rax
  unsigned int v124; // eax
  int v125; // ecx
  __int64 v126; // rdx
  Page *v127; // r11
  char v128; // al
  int v129; // esi
  BTreeMgr *v130; // rdi
  _QWORD *v131; // rbx
  __int64 v132; // r14
  unsigned __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rbx
  _QWORD *v137; // r8
  unsigned __int64 v138; // rax
  unsigned __int64 v139; // rcx
  __int64 v140; // rcx
  __int64 v141; // rax
  bool v142; // zf
  int v143; // r12d
  __int64 v144; // rax
  struct CSessionTraceFlags *v145; // rcx
  __int64 v146; // rdx
  struct SEInternalTLS *SETLSFromTlsMaybeNull; // r13
  _QWORD *v148; // r15
  Page **v149; // rax
  unsigned int v150; // edx
  Page *v151; // rcx
  __int64 v152; // rax
  unsigned int v153; // r8d
  __int64 v154; // rdx
  Page *v155; // r11
  char v156; // al
  int v157; // eax
  unsigned int v158; // ecx
  Page **v159; // rdx
  Page *v160; // r11
  char v161; // cl
  __int16 v162; // si
  __int64 v163; // xmm1_8
  __int64 v164; // xmm0_8
  unsigned int v165; // edi
  volatile signed __int32 *v166; // rbx
  Page *v167; // rax
  __int64 v168; // rcx
  unsigned int v169; // edi
  volatile signed __int32 *v170; // rbx
  Page *v171; // rax
  __int64 v172; // rcx
  unsigned int v173; // edi
  volatile signed __int32 *v174; // rbx
  Page *v175; // rax
  __int64 v176; // rcx
  int v177; // eax
  unsigned int v178; // ecx
  LSN v179; // xmm0_8
  unsigned __int16 v180; // bx
  Page *v181; // r11
  char v182; // al
  unsigned __int16 v183; // r11
  __int64 v184; // r10
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // rax
  int *v188; // rdx
  __int64 v189; // rcx
  int v190; // ecx
  int **v191; // rax
  __int64 v192; // rcx
  __int64 v193; // rax
  __int64 v194; // rax
  __int64 v195; // rax
  __int64 v196; // r12
  __int64 v197; // rsi
  Page *v198; // rcx
  __int64 v199; // rax
  int v200; // r15d
  __int16 v201; // ax
  __int16 v202; // r14
  __int64 v203; // rdx
  unsigned __int16 v204; // ax
  Page *v205; // r11
  __int64 v206; // rcx
  char v207; // al
  __int16 v208; // r11
  __int64 v209; // rax
  unsigned int v210; // edi
  volatile signed __int32 *v211; // rbx
  Page *v212; // rax
  __int64 v213; // rcx
  __int16 v214; // r14
  __int64 v215; // rdx
  unsigned __int16 v216; // ax
  unsigned int v217; // edi
  Page **v218; // rbx
  Page *v219; // rax
  __int64 v220; // rcx
  PageComprMgr *PageComprMgr; // rsi
  unsigned __int8 *v222; // rbx
  unsigned int v223; // edi
  Page *v224; // rax
  __int64 v225; // rcx
  __int64 v226; // rdx
  Page *v227; // r11
  char v228; // al
  int v229; // esi
  _QWORD *v230; // rax
  __int64 v231; // rdi
  __int64 v232; // rbx
  unsigned __int16 v233; // ax
  unsigned int v234; // eax
  __int64 v235; // rdx
  __int64 v236; // r14
  unsigned __int64 v237; // rcx
  __int64 v238; // rax
  __int64 v239; // rax
  __int64 v240; // rbx
  _QWORD *v241; // r8
  unsigned __int64 v242; // rax
  unsigned __int64 v243; // rcx
  __int64 v244; // rcx
  __int64 v245; // rax
  bool v246; // zf
  int v247; // r12d
  __int64 v248; // rdx
  struct CSessionTraceFlags *v249; // rcx
  __int64 v250; // rax
  struct SEInternalTLS *v251; // r13
  _QWORD *v252; // r15
  Page **v253; // rax
  unsigned int v254; // edx
  Page *v255; // rcx
  __int64 v256; // rax
  unsigned int v257; // r8d
  _QWORD *v258; // rdx
  Page *v259; // r11
  char v260; // al
  int v261; // eax
  unsigned int v262; // ecx
  Page **v263; // rdx
  Page *v264; // r11
  char v265; // cl
  __int16 v266; // si
  __int64 v267; // xmm1_8
  __int64 v268; // xmm0_8
  unsigned int v269; // edi
  volatile signed __int32 *v270; // rbx
  Page *v271; // rax
  __int64 v272; // rcx
  unsigned int v273; // edi
  volatile signed __int32 *v274; // rbx
  Page *v275; // rax
  __int64 v276; // rcx
  unsigned int v277; // edi
  volatile signed __int32 *v278; // rbx
  Page *v279; // rax
  __int64 v280; // rcx
  int v281; // eax
  unsigned int v282; // ecx
  LSN v283; // xmm0_8
  unsigned __int16 v284; // bx
  Page *v285; // r11
  char v286; // al
  unsigned __int16 v287; // r11
  __int64 v288; // r10
  __int64 v289; // rax
  __int64 v290; // rax
  __int64 v291; // rax
  int *v292; // rdx
  __int64 v293; // rcx
  int v294; // ecx
  int **v295; // rax
  unsigned int v296; // eax
  int v297; // ecx
  __int64 v298; // rcx
  __int64 v299; // rax
  __int64 v300; // rax
  __int64 v301; // rax
  __int64 v302; // r12
  __int64 v303; // rsi
  Page *v304; // rcx
  __int64 v305; // rax
  int v306; // r15d
  __int16 v307; // ax
  __int16 v308; // r14
  __int64 v309; // rdx
  unsigned __int16 v310; // ax
  Page *v311; // r11
  __int64 v312; // rcx
  char v313; // al
  __int16 v314; // r11
  __int64 v315; // rax
  unsigned int v316; // edi
  volatile signed __int32 *v317; // rbx
  Page *v318; // rax
  __int64 v319; // rcx
  const void *Payload; // rax
  __int64 v321; // rdx
  __int64 v322; // rax
  char v323; // al
  unsigned __int8 *v324; // r15
  __int64 Offset; // rax
  __int64 v326; // r12
  unsigned __int8 *v327; // rdi
  __int64 v328; // rax
  __int16 v329; // cx
  __int16 v330; // dx
  unsigned int v331; // eax
  const unsigned __int8 *v332; // rdx
  unsigned __int16 v333; // ax
  unsigned __int8 *v334; // rdi
  int IsGhostVersionRec; // eax
  CDRecord *v336; // rcx
  int v337; // r14d
  unsigned __int16 v338; // cx
  __int16 v339; // dx
  unsigned __int8 *v340; // rbx
  unsigned int v341; // eax
  int v342; // ecx
  struct COLOFF *v343; // rbx
  unsigned __int16 v344; // r8
  OffsetArray *v345; // r14
  unsigned __int16 v346; // ax
  __int64 v347; // rbx
  struct COLOFF *v348; // rax
  struct COLOFF *v349; // rdi
  __int64 v350; // rsi
  unsigned int v351; // ebx
  unsigned int v352; // ecx
  unsigned int v353; // eax
  unsigned __int16 v354; // cx
  SV_Header *v355; // rbx
  unsigned __int16 ColumnIdClusterTableSize; // ax
  unsigned __int16 ColumnCount; // ax
  struct RecVersioningInfo *VersioningInfo; // rax
  unsigned int PayloadSize; // eax
  unsigned int v360; // ecx
  __int16 v361; // bx
  int v362; // edi
  struct COLOFF *v363; // rsi
  __int64 v364; // rbx
  unsigned int v365; // edi
  HeapPageRef *v366; // rax
  unsigned int v367; // eax
  unsigned int v368; // edi
  PageComprMgr *v369; // rcx
  unsigned int v370; // edi
  volatile signed __int32 *v371; // rbx
  Page *v372; // rax
  __int64 v373; // rcx
  _QWORD *v374; // rdx
  unsigned int v375; // edi
  volatile signed __int32 *v376; // rbx
  Page *v377; // rax
  __int64 v378; // rcx
  Page *v379; // rax
  __int64 v380; // rcx
  Page *v381; // rax
  __int64 v382; // rcx
  __int64 v383; // rax
  unsigned int v384; // edi
  volatile signed __int32 *v385; // rbx
  Page *v386; // rax
  __int64 v387; // rcx
  unsigned int v388; // edi
  Page **v389; // rbx
  Page *v390; // rax
  __int64 v391; // rcx
  int v392; // edi
  __int64 v393; // rbx
  __int64 v394; // rax
  __int64 v395; // rcx
  signed __int32 v396[8]; // [rsp+0h] [rbp-100h] BYREF
  struct PrefetchObject *v397; // [rsp+20h] [rbp-E0h]
  unsigned int *v398; // [rsp+30h] [rbp-D0h]
  char v399; // [rsp+40h] [rbp-C0h]
  Page **v400; // [rsp+48h] [rbp-B8h] BYREF
  char v401; // [rsp+50h] [rbp-B0h]
  unsigned int v402; // [rsp+54h] [rbp-ACh]
  unsigned int v403; // [rsp+58h] [rbp-A8h]
  char v404; // [rsp+60h] [rbp-A0h]
  int v405; // [rsp+64h] [rbp-9Ch] BYREF
  Page **v406; // [rsp+68h] [rbp-98h] BYREF
  char v407; // [rsp+70h] [rbp-90h]
  unsigned int v408; // [rsp+74h] [rbp-8Ch]
  unsigned int v409; // [rsp+78h] [rbp-88h]
  int v410; // [rsp+80h] [rbp-80h]
  unsigned int v411; // [rsp+84h] [rbp-7Ch] BYREF
  int v412; // [rsp+88h] [rbp-78h]
  unsigned int v413; // [rsp+8Ch] [rbp-74h]
  int v414; // [rsp+90h] [rbp-70h] BYREF
  __int16 v415; // [rsp+94h] [rbp-6Ch]
  int v416; // [rsp+98h] [rbp-68h]
  PhysicalColumnAttribute *v417; // [rsp+A0h] [rbp-60h]
  int v418; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v419; // [rsp+ACh] [rbp-54h]
  int v420; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v421; // [rsp+B4h] [rbp-4Ch]
  int v422; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v423; // [rsp+C0h] [rbp-40h]
  unsigned int v424; // [rsp+C8h] [rbp-38h] BYREF
  SearchInfo *v425; // [rsp+D0h] [rbp-30h]
  __int64 v426; // [rsp+D8h] [rbp-28h]
  __int64 v427; // [rsp+E0h] [rbp-20h]
  __int64 v428; // [rsp+E8h] [rbp-18h]
  BTreeMgr *v429; // [rsp+F0h] [rbp-10h]
  unsigned int v430; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v431; // [rsp+FCh] [rbp-4h] BYREF
  unsigned int v432; // [rsp+100h] [rbp+0h] BYREF
  int v433; // [rsp+104h] [rbp+4h] BYREF
  Page *v434; // [rsp+108h] [rbp+8h]
  BOOL v435; // [rsp+110h] [rbp+10h]
  unsigned int v436; // [rsp+114h] [rbp+14h] BYREF
  LSN v437; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 v438; // [rsp+120h] [rbp+20h]
  LSN v439; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 v440; // [rsp+130h] [rbp+30h]
  LSN v441; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 v442; // [rsp+140h] [rbp+40h]
  PageRef *v443; // [rsp+148h] [rbp+48h]
  __int64 v444; // [rsp+150h] [rbp+50h] BYREF
  __int16 v445; // [rsp+158h] [rbp+58h]
  __int64 v446; // [rsp+160h] [rbp+60h] BYREF
  __int16 v447; // [rsp+168h] [rbp+68h]
  __int64 v448; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v449; // [rsp+178h] [rbp+78h]
  __int64 v450; // [rsp+180h] [rbp+80h] BYREF
  __int16 v451; // [rsp+188h] [rbp+88h]
  __int64 v452; // [rsp+190h] [rbp+90h] BYREF
  __int16 v453; // [rsp+198h] [rbp+98h]
  __int64 v454; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v455; // [rsp+1A8h] [rbp+A8h]
  __int64 v456; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v457; // [rsp+1B8h] [rbp+B8h]
  int v458; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v459; // [rsp+1C4h] [rbp+C4h] BYREF
  int v460; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v461; // [rsp+1CCh] [rbp+CCh] BYREF
  int v462; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int v463; // [rsp+1D4h] [rbp+D4h] BYREF
  int v464; // [rsp+1D8h] [rbp+D8h] BYREF
  int v465; // [rsp+1DCh] [rbp+DCh] BYREF
  int v466; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v467; // [rsp+1E4h] [rbp+E4h] BYREF
  __int64 v468; // [rsp+1E8h] [rbp+E8h] BYREF
  __int16 v469; // [rsp+1F0h] [rbp+F0h]
  __int64 v470; // [rsp+1F8h] [rbp+F8h] BYREF
  __int16 v471; // [rsp+200h] [rbp+100h]
  int v472; // [rsp+208h] [rbp+108h] BYREF
  __int16 v473; // [rsp+20Ch] [rbp+10Ch]
  int v474; // [rsp+210h] [rbp+110h] BYREF
  __int16 v475; // [rsp+214h] [rbp+114h]
  int v476; // [rsp+218h] [rbp+118h] BYREF
  __int16 v477; // [rsp+21Ch] [rbp+11Ch]
  int v478; // [rsp+220h] [rbp+120h] BYREF
  __int16 v479; // [rsp+224h] [rbp+124h]
  int v480; // [rsp+228h] [rbp+128h] BYREF
  __int16 v481; // [rsp+22Ch] [rbp+12Ch]
  int v482; // [rsp+230h] [rbp+130h] BYREF
  __int16 v483; // [rsp+234h] [rbp+134h]
  int v484; // [rsp+238h] [rbp+138h] BYREF
  __int16 v485; // [rsp+23Ch] [rbp+13Ch]
  int v486; // [rsp+240h] [rbp+140h] BYREF
  __int16 v487; // [rsp+244h] [rbp+144h]
  int v488; // [rsp+248h] [rbp+148h] BYREF
  __int16 v489; // [rsp+24Ch] [rbp+14Ch]
  int v490; // [rsp+250h] [rbp+150h] BYREF
  __int16 v491; // [rsp+254h] [rbp+154h]
  int v492; // [rsp+258h] [rbp+158h] BYREF
  __int16 v493; // [rsp+25Ch] [rbp+15Ch]
  int v494; // [rsp+260h] [rbp+160h] BYREF
  __int16 v495; // [rsp+264h] [rbp+164h]
  int v496; // [rsp+268h] [rbp+168h] BYREF
  __int16 v497; // [rsp+26Ch] [rbp+16Ch]
  unsigned int v498; // [rsp+270h] [rbp+170h] BYREF
  struct PrefetchObject *v499; // [rsp+278h] [rbp+178h]
  int v500; // [rsp+280h] [rbp+180h] BYREF
  __int16 v501; // [rsp+284h] [rbp+184h]
  __int16 v502; // [rsp+286h] [rbp+186h]
  int v503; // [rsp+288h] [rbp+188h] BYREF
  __int16 v504; // [rsp+28Ch] [rbp+18Ch]
  __int16 v505; // [rsp+28Eh] [rbp+18Eh]
  int v506; // [rsp+290h] [rbp+190h] BYREF
  __int16 v507; // [rsp+294h] [rbp+194h]
  __int16 v508; // [rsp+296h] [rbp+196h]
  int v509; // [rsp+298h] [rbp+198h] BYREF
  __int16 v510; // [rsp+29Ch] [rbp+19Ch]
  __int16 v511; // [rsp+29Eh] [rbp+19Eh]
  int v512; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int16 v513; // [rsp+2A4h] [rbp+1A4h]
  __int16 v514; // [rsp+2A6h] [rbp+1A6h]
  int v515; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int16 v516; // [rsp+2ACh] [rbp+1ACh]
  __int16 v517; // [rsp+2AEh] [rbp+1AEh]
  __int64 v518; // [rsp+2B0h] [rbp+1B0h]
  LSN v519; // [rsp+2B8h] [rbp+1B8h]
  int v520; // [rsp+2C0h] [rbp+1C0h]
  __int64 v521; // [rsp+2C4h] [rbp+1C4h]
  int v522; // [rsp+2CCh] [rbp+1CCh]
  __int64 v523; // [rsp+2D0h] [rbp+1D0h]
  int v524; // [rsp+2D8h] [rbp+1D8h]
  LSN v525; // [rsp+2DCh] [rbp+1DCh]
  int v526; // [rsp+2E4h] [rbp+1E4h]
  __int64 v527; // [rsp+2E8h] [rbp+1E8h]
  int v528; // [rsp+2F0h] [rbp+1F0h]
  LSN v529; // [rsp+2F4h] [rbp+1F4h]
  int v530; // [rsp+2FCh] [rbp+1FCh]
  int v531; // [rsp+300h] [rbp+200h]
  unsigned int v532; // [rsp+308h] [rbp+208h] BYREF
  __int64 v533; // [rsp+30Ch] [rbp+20Ch]
  unsigned int v534; // [rsp+320h] [rbp+220h] BYREF
  __int64 v535; // [rsp+324h] [rbp+224h]
  unsigned int v536; // [rsp+338h] [rbp+238h] BYREF
  __int64 v537; // [rsp+33Ch] [rbp+23Ch]
  __int64 v538; // [rsp+350h] [rbp+250h] BYREF
  __int16 v539; // [rsp+358h] [rbp+258h]
  LSN v540; // [rsp+360h] [rbp+260h] BYREF
  __int16 v541; // [rsp+368h] [rbp+268h]
  LSN v542; // [rsp+370h] [rbp+270h] BYREF
  __int16 v543; // [rsp+378h] [rbp+278h]
  __int64 v544; // [rsp+380h] [rbp+280h] BYREF
  __int16 v545; // [rsp+388h] [rbp+288h]
  LSN v546; // [rsp+390h] [rbp+290h] BYREF
  __int16 v547; // [rsp+398h] [rbp+298h]
  unsigned __int8 *v548; // [rsp+3A0h] [rbp+2A0h] BYREF
  char v549[8]; // [rsp+3A8h] [rbp+2A8h] BYREF
  unsigned __int8 *v550; // [rsp+3B0h] [rbp+2B0h] BYREF
  int v551; // [rsp+3B8h] [rbp+2B8h] BYREF
  int v552; // [rsp+3BCh] [rbp+2BCh] BYREF
  DWORD v553; // [rsp+3C0h] [rbp+2C0h] BYREF
  DWORD v554; // [rsp+3C4h] [rbp+2C4h] BYREF
  DWORD v555; // [rsp+3C8h] [rbp+2C8h] BYREF
  DWORD v556; // [rsp+3CCh] [rbp+2CCh] BYREF
  DWORD v557; // [rsp+3D0h] [rbp+2D0h] BYREF
  DWORD v558; // [rsp+3D4h] [rbp+2D4h] BYREF
  DWORD v559; // [rsp+3D8h] [rbp+2D8h] BYREF
  DWORD v560; // [rsp+3DCh] [rbp+2DCh] BYREF
  DWORD v561; // [rsp+3E0h] [rbp+2E0h] BYREF
  DWORD v562; // [rsp+3E4h] [rbp+2E4h] BYREF
  DWORD v563; // [rsp+3E8h] [rbp+2E8h] BYREF
  DWORD v564; // [rsp+3ECh] [rbp+2ECh] BYREF
  DWORD v565; // [rsp+3F0h] [rbp+2F0h] BYREF
  DWORD v566; // [rsp+3F4h] [rbp+2F4h] BYREF
  DWORD v567; // [rsp+3F8h] [rbp+2F8h] BYREF
  DWORD flOldProtect; // [rsp+3FCh] [rbp+2FCh] BYREF
  DWORD v569; // [rsp+400h] [rbp+300h] BYREF
  DWORD v570; // [rsp+404h] [rbp+304h] BYREF
  DWORD v571; // [rsp+408h] [rbp+308h] BYREF
  int v572; // [rsp+40Ch] [rbp+30Ch] BYREF
  unsigned __int8 *v573; // [rsp+410h] [rbp+310h] BYREF
  char v574[8]; // [rsp+418h] [rbp+318h] BYREF
  __int64 v575; // [rsp+420h] [rbp+320h]
  char v576[8]; // [rsp+430h] [rbp+330h] BYREF
  int v577; // [rsp+438h] [rbp+338h]
  int v578; // [rsp+440h] [rbp+340h]
  int **v579; // [rsp+448h] [rbp+348h]
  char *v580; // [rsp+450h] [rbp+350h]
  __int64 v581; // [rsp+458h] [rbp+358h]
  int *v582; // [rsp+460h] [rbp+360h] BYREF
  int v583; // [rsp+468h] [rbp+368h]
  int v584; // [rsp+46Ch] [rbp+36Ch]
  GUID *v585; // [rsp+470h] [rbp+370h]
  int v586; // [rsp+478h] [rbp+378h]
  int v587; // [rsp+47Ch] [rbp+37Ch]
  GUID *v588; // [rsp+480h] [rbp+380h]
  int v589; // [rsp+488h] [rbp+388h]
  int v590; // [rsp+48Ch] [rbp+38Ch]
  wchar_t *v591; // [rsp+490h] [rbp+390h]
  int v592; // [rsp+498h] [rbp+398h]
  int v593; // [rsp+49Ch] [rbp+39Ch]
  wchar_t *v594; // [rsp+4A0h] [rbp+3A0h]
  int v595; // [rsp+4A8h] [rbp+3A8h]
  int v596; // [rsp+4ACh] [rbp+3ACh]
  __int64 v597; // [rsp+4B0h] [rbp+3B0h]
  int v598; // [rsp+4B8h] [rbp+3B8h]
  int v599; // [rsp+4BCh] [rbp+3BCh]
  char v600; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int64 v601; // [rsp+680h] [rbp+580h]
  __int64 v602; // [rsp+688h] [rbp+588h]
  int v603; // [rsp+690h] [rbp+590h] BYREF
  __int16 v604; // [rsp+694h] [rbp+594h]
  int v605; // [rsp+696h] [rbp+596h]
  char v606; // [rsp+69Ah] [rbp+59Ah]
  char v607; // [rsp+69Bh] [rbp+59Bh]
  char v608[8]; // [rsp+6D0h] [rbp+5D0h] BYREF
  int v609; // [rsp+6D8h] [rbp+5D8h]
  int v610; // [rsp+6E0h] [rbp+5E0h]
  int **v611; // [rsp+6E8h] [rbp+5E8h]
  char *v612; // [rsp+6F0h] [rbp+5F0h]
  __int64 v613; // [rsp+6F8h] [rbp+5F8h]
  int *v614; // [rsp+700h] [rbp+600h] BYREF
  int v615; // [rsp+708h] [rbp+608h]
  int v616; // [rsp+70Ch] [rbp+60Ch]
  GUID *v617; // [rsp+710h] [rbp+610h]
  int v618; // [rsp+718h] [rbp+618h]
  int v619; // [rsp+71Ch] [rbp+61Ch]
  GUID *v620; // [rsp+720h] [rbp+620h]
  int v621; // [rsp+728h] [rbp+628h]
  int v622; // [rsp+72Ch] [rbp+62Ch]
  wchar_t *v623; // [rsp+730h] [rbp+630h]
  int v624; // [rsp+738h] [rbp+638h]
  int v625; // [rsp+73Ch] [rbp+63Ch]
  wchar_t *v626; // [rsp+740h] [rbp+640h]
  int v627; // [rsp+748h] [rbp+648h]
  int v628; // [rsp+74Ch] [rbp+64Ch]
  __int64 v629; // [rsp+750h] [rbp+650h]
  int v630; // [rsp+758h] [rbp+658h]
  int v631; // [rsp+75Ch] [rbp+65Ch]
  char v632; // [rsp+760h] [rbp+660h] BYREF
  __int64 v633; // [rsp+920h] [rbp+820h]
  __int64 v634; // [rsp+928h] [rbp+828h]
  int v635; // [rsp+930h] [rbp+830h] BYREF
  __int16 v636; // [rsp+934h] [rbp+834h]
  int v637; // [rsp+936h] [rbp+836h]
  char v638; // [rsp+93Ah] [rbp+83Ah]
  char v639; // [rsp+93Bh] [rbp+83Bh]
  char v640[8]; // [rsp+970h] [rbp+870h] BYREF
  int v641; // [rsp+978h] [rbp+878h]
  int v642; // [rsp+980h] [rbp+880h]
  int **v643; // [rsp+988h] [rbp+888h]
  char *v644; // [rsp+990h] [rbp+890h]
  __int64 v645; // [rsp+998h] [rbp+898h]
  int *v646; // [rsp+9A0h] [rbp+8A0h] BYREF
  int v647; // [rsp+9A8h] [rbp+8A8h]
  int v648; // [rsp+9ACh] [rbp+8ACh]
  GUID *v649; // [rsp+9B0h] [rbp+8B0h]
  int v650; // [rsp+9B8h] [rbp+8B8h]
  int v651; // [rsp+9BCh] [rbp+8BCh]
  GUID *v652; // [rsp+9C0h] [rbp+8C0h]
  int v653; // [rsp+9C8h] [rbp+8C8h]
  int v654; // [rsp+9CCh] [rbp+8CCh]
  wchar_t *v655; // [rsp+9D0h] [rbp+8D0h]
  int v656; // [rsp+9D8h] [rbp+8D8h]
  int v657; // [rsp+9DCh] [rbp+8DCh]
  wchar_t *v658; // [rsp+9E0h] [rbp+8E0h]
  int v659; // [rsp+9E8h] [rbp+8E8h]
  int v660; // [rsp+9ECh] [rbp+8ECh]
  __int64 v661; // [rsp+9F0h] [rbp+8F0h]
  int v662; // [rsp+9F8h] [rbp+8F8h]
  int v663; // [rsp+9FCh] [rbp+8FCh]
  char v664; // [rsp+A00h] [rbp+900h] BYREF
  __int64 v665; // [rsp+BC0h] [rbp+AC0h]
  __int64 v666; // [rsp+BC8h] [rbp+AC8h]
  int v667; // [rsp+BD0h] [rbp+AD0h] BYREF
  __int16 v668; // [rsp+BD4h] [rbp+AD4h]
  int v669; // [rsp+BD6h] [rbp+AD6h]
  char v670; // [rsp+BDAh] [rbp+ADAh]
  char v671; // [rsp+BDBh] [rbp+ADBh]
  __int16 v672; // [rsp+C10h] [rbp+B10h]
  unsigned __int16 v673; // [rsp+C12h] [rbp+B12h] BYREF
  unsigned int v674; // [rsp+C14h] [rbp+B14h]
  unsigned __int8 *v675; // [rsp+C18h] [rbp+B18h]
  unsigned int v676; // [rsp+C20h] [rbp+B20h]
  unsigned int v677; // [rsp+C24h] [rbp+B24h]
  unsigned int v678; // [rsp+C28h] [rbp+B28h]
  unsigned __int16 v679; // [rsp+C2Ch] [rbp+B2Ch]
  unsigned __int64 v680; // [rsp+C2Eh] [rbp+B2Eh]
  _TBYTE v681; // [rsp+C36h] [rbp+B36h] BYREF
  int v682; // [rsp+C40h] [rbp+B40h]
  int v683; // [rsp+C44h] [rbp+B44h]
  char v684[120]; // [rsp+C48h] [rbp+B48h] BYREF
  __int64 v685; // [rsp+CC0h] [rbp+BC0h] BYREF
  __int16 v686; // [rsp+CC8h] [rbp+BC8h]
  _QWORD v687[2]; // [rsp+CD0h] [rbp+BD0h] BYREF
  __int16 v688; // [rsp+CE6h] [rbp+BE6h]
  unsigned __int8 v689[8]; // [rsp+CE8h] [rbp+BE8h] BYREF
  wchar_t v690[24]; // [rsp+CF0h] [rbp+BF0h] BYREF
  wchar_t v691[24]; // [rsp+D20h] [rbp+C20h] BYREF
  wchar_t v692[24]; // [rsp+D50h] [rbp+C50h] BYREF
  wchar_t v693[24]; // [rsp+D80h] [rbp+C80h] BYREF
  wchar_t v694[24]; // [rsp+DB0h] [rbp+CB0h] BYREF
  wchar_t v695[24]; // [rsp+DE0h] [rbp+CE0h] BYREF

  v575 = -2;
  v413 = a4;
  v10 = a1;
  v429 = a1;
  v443 = a6;
  v425 = a7;
  v11 = a8;
  v499 = a8;
  v12 = -1;
  v412 = -1;
  v405 = -1;
  v414 = 0;
  v415 = 0;
  v406 = 0;
  v407 = 0;
  v408 = 0;
  v400 = 0;
  v401 = 0;
  v402 = 0;
  v434 = 0;
  v410 = 0x7FFFFFFF;
  v404 = 0;
  v13 = 0;
  v399 = 0;
  v14 = (const struct HoBtAccess *)**((_QWORD **)v10 + 1);
  v15 = (PhysicalColumnAttribute *)(*((_QWORD *)v14 + 1) + 528LL);
  v417 = v15;
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    ObjectDataImpl = PerCPUDataImpl::GetObjectDataImpl((PerCPUDataImpl *)&qword_10316EC90);
    ++ObjectDataImpl[10];
    v11 = v499;
  }
  if ( v11 && *(_DWORD *)v11 && !(unsigned int)BTreeMgr::RevalidatePrefetchObject(v10, v11, &v400) )
  {
    v79 = *((_WORD *)v499 + 20);
    v414 = *((_DWORD *)v499 + 9);
    v415 = v79;
    v410 = *((unsigned __int8 *)*v400 + 3) - 1;
  }
  v17 = -1;
  if ( v413 - 1 <= 1 )
    v17 = a5;
  v422 = v17;
  v435 = 1;
  if ( !*((_DWORD *)a2 + 4) )
  {
    v18 = *((_QWORD *)v14 + 1);
    v19 = *(char *)(v18 + 262) < 0 ? 1 : *(_DWORD *)(**(_QWORD **)(v18 + 352) + 28LL);
    if ( *((_DWORD *)a2 + 2) != v19 )
    {
      v13 = 1;
      if ( a3 == 1 )
        v13 = 3;
    }
  }
  v20 = v425;
  v21 = (int *)((char *)v425 + 16);
  if ( *((_BYTE *)v425 + 20) )
  {
    *v21 = v13;
    v23 = v20;
  }
  else
  {
    v22 = v13;
    v23 = v425;
    SearchInfo::InitSlow(v425, a2, v14, v22);
  }
  *((_BYTE *)v23 + 21) = 0;
  *((_QWORD *)v23 + 3) = (char *)v23 + 56;
  *((_QWORD *)v23 + 4) = (char *)v23 + 56;
  *((_QWORD *)v23 + 5) = v21;
  v24 = v410;
  while ( 1 )
  {
LABEL_13:
    v25 = a5;
    v26 = v413;
    if ( v24 != 0x7FFFFFFF )
    {
      v29 = v399;
      goto LABEL_20;
    }
    if ( (unsigned int)BTreeMgr::HandleRoot(v10, v413, (unsigned int)a5, &v422, &v406, v443) != 2 )
      goto LABEL_25;
    v434 = *v406;
    v24 = *((unsigned __int8 *)v434 + 3);
    v410 = v24;
    if ( v24 < a5 )
    {
      if ( (*((_WORD *)v406 + 49) & 0x400) != 0 && (__int16)v408 >= 3 )
      {
        PageRef::UnfixLatchOnly((PageRef *)&v406);
        goto LABEL_25;
      }
      v388 = (__int16)v408;
      v389 = v406;
      if ( (*((_WORD *)v406 + 49) & 8) == 0 )
        goto LABEL_1125;
      if ( (__int16)v408 == 3 )
      {
        v388 = 4;
      }
      else if ( (__int16)v408 < 2 )
      {
LABEL_1125:
        if ( byte_10317ABE5 < 0
          && (*((_DWORD *)v389 + 25) & 8) != 0
          && (int)v388 >= 3
          && (*((_DWORD *)v389 + 25) & 0xC0000000) != 0x40000000
          && *v389
          && VirtualProtect(*v389, 0x2000u, 2u, &v563) )
        {
          _InterlockedAnd((volatile signed __int32 *)v389 + 25, 0x3FFFFFFFu);
          _InterlockedOr((volatile signed __int32 *)v389 + 25, 0x40000000u);
        }
        LatchBase::ReleaseInternal(v389 + 19, v388);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v389, 0, v388);
        v408 &= 0xFFFF0000;
        v406 = 0;
        goto LABEL_25;
      }
      if ( (*((_DWORD *)v406 + 25) & 8) != 0 )
      {
        v390 = v406[18];
        if ( v390 )
        {
          v391 = *((_QWORD *)v390 + 235);
          if ( v391 )
            DirtyPageMgr::OnReleasingBufLatch(v391, v406, v388);
        }
      }
      goto LABEL_1125;
    }
    LatchBase::ReleaseInternal(*((_QWORD *)v443 + 4), *((unsigned int *)v443 + 11));
    *((_DWORD *)v443 + 10) = 0;
    v27 = *(_DWORD *)(*(_QWORD *)v23 + 16LL);
    if ( !v27 )
    {
      v28 = PageRef::SearchPage((PageRef *)&v406, v23);
      v405 = v28;
      if ( !*((_BYTE *)v23 + 21) || (*((_DWORD *)v23 + 4) & 3) == 1 )
LABEL_18:
        v405 = v28 - 1;
      v404 = *((_BYTE *)v23 + 21);
      v29 = 1;
      v399 = 1;
      goto LABEL_20;
    }
    v92 = v27 - 1;
    if ( !v92 )
    {
      v405 = 0;
      v404 = *((_BYTE *)v23 + 21);
      v29 = 1;
      v399 = 1;
      goto LABEL_20;
    }
    if ( v92 == 1 )
    {
      v28 = *((unsigned __int16 *)*v406 + 11);
      goto LABEL_18;
    }
    utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\dfs\\access\\BTreeMgr.inl", 419, "Invalid switch value");
    v404 = *((_BYTE *)v23 + 21);
    v29 = 1;
    v399 = 1;
LABEL_20:
    while ( 2 )
    {
      *(_QWORD *)((char *)v10 + 364) = 0;
      if ( v29 )
      {
        v399 = 0;
        v30 = v404;
        goto LABEL_22;
      }
      if ( v499
        && !(unsigned int)BTreeMgr::PrefetchPageDuringSeek(
                            v499,
                            (const struct PageId *)&v414,
                            *(struct RecoveryUnit **)(*(_QWORD *)(*((_QWORD *)v10 + 1) + 8LL) + 48LL),
                            *((struct DataSetSessionStats **)v10 + 2),
                            v499,
                            (struct PageRef *)&v400,
                            v12) )
      {
        goto LABEL_25;
      }
      v33 = 2;
      if ( v24 <= v422 )
        v33 = 4;
      v416 = v33;
      if ( v26 == 3 )
      {
        if ( v24 == v25 )
          v33 = 4;
        v416 = v33;
      }
      v426 = *((_QWORD *)v10 + 1);
      v428 = *((_QWORD *)v10 + 2);
      v423 = *(_QWORD *)v426;
      v533 = 0;
      v34 = *(_QWORD *)(v423 + 32);
      v35 = (*(unsigned int *)(v423 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v423 + 24) << 32)) << 16;
      v36 = *(_QWORD *)(v34 + 2000);
      if ( v36 != v35 || ((v36 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v37 = *(_QWORD *)(v34 + 2008);
        if ( v37 != v35 || ((v37 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v39 = *(_QWORD **)(v38 + 256);
          if ( !v39 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v39 = *(_QWORD **)(v38 + 256);
          }
          v40 = __rdtsc();
          v41 = v39[104];
          if ( v40 <= v41 && (v41 == 0x7FFFFFFFFFFFFFFFLL || v41 - v40 <= *(_QWORD *)(v39[76] + 3568LL)) )
          {
            v42 = v39[75];
            if ( (*(_DWORD *)(v42 + 188) & 4) == 0 )
              goto LABEL_41;
            v90 = *(_QWORD *)(v42 + 152);
            if ( (*(_BYTE *)(v90 + 616) & 1) != 0 )
              goto LABEL_41;
            v89 = (*(_DWORD *)(v90 + 800) & 0x180) == 0;
          }
          else
          {
            v89 = (unsigned int)SOS_Task::Sleep(0, yieldWait) == 2;
          }
          if ( v89 )
          {
            LOBYTE(v42) = 124;
            RaiseExecutionAbortedError(v42);
          }
        }
      }
LABEL_41:
      v43 = *(_BYTE *)(v34 + 8272);
      v44 = -1;
      if ( !v43 )
        v44 = 2;
      if ( !CommonGlobalState::m_CollectingStatistics
        || byte_10317ABE6 < 0
        || (v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset,
            *(_QWORD *)v45)
        && (v46 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v45 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v46, 0x337u)
        || (v47 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL)) == 0 )
      {
        v48 = 0;
      }
      else
      {
        v48 = *(_QWORD *)(v47 + 96);
      }
      v49 = *(_QWORD **)(v34 + 1832);
      v430 = 0;
      if ( v406 )
      {
        if ( (*((_WORD *)v406 + 49) & 0x400) != 0 && (__int16)v408 >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)&v406);
          goto LABEL_50;
        }
        v97 = (__int16)v408;
        v98 = v406;
        if ( (*((_WORD *)v406 + 49) & 8) == 0 )
          goto LABEL_159;
        if ( (__int16)v408 == 3 )
        {
          v97 = 4;
        }
        else if ( (__int16)v408 < 2 )
        {
LABEL_159:
          if ( byte_10317ABE5 < 0
            && (*((_DWORD *)v98 + 25) & 8) != 0
            && (int)v97 >= 3
            && (*((_DWORD *)v98 + 25) & 0xC0000000) != 0x40000000
            && *v98
            && VirtualProtect(*v98, 0x2000u, 2u, &flOldProtect) )
          {
            _InterlockedAnd((volatile signed __int32 *)v98 + 25, 0x3FFFFFFFu);
            _InterlockedOr((volatile signed __int32 *)v98 + 25, 0x40000000u);
          }
          LatchBase::ReleaseInternal(v98 + 19, v97);
          if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v98, 0, v97);
          v408 &= 0xFFFF0000;
          v406 = 0;
          goto LABEL_50;
        }
        if ( (*((_DWORD *)v406 + 25) & 8) != 0 )
        {
          v99 = v406[18];
          if ( v99 )
          {
            v100 = *((_QWORD *)v99 + 235);
            if ( v100 )
              DirtyPageMgr::OnReleasingBufLatch(v100, v406, v97);
          }
        }
        goto LABEL_159;
      }
LABEL_50:
      if ( !*(_QWORD *)(v34 + 1832) )
        goto LABEL_51;
      PageRef::CatchupPageRedos((PageRef *)&v406, (const struct PageId *)&v414, (struct RecoveryUnit *)v34);
      if ( !v406 )
        goto LABEL_51;
      if ( (*((_WORD *)v406 + 49) & 0x400) != 0 && (__int16)v408 >= 3 )
      {
        PageRef::UnfixLatchOnly((PageRef *)&v406);
        goto LABEL_51;
      }
      v101 = (__int16)v408;
      v102 = v406;
      if ( (*((_WORD *)v406 + 49) & 8) != 0 )
      {
        if ( (__int16)v408 == 3 )
        {
          v101 = 4;
LABEL_179:
          if ( (*((_DWORD *)v406 + 25) & 8) != 0 )
          {
            v103 = v406[18];
            if ( v103 )
            {
              v104 = *((_QWORD *)v103 + 235);
              if ( v104 )
                DirtyPageMgr::OnReleasingBufLatch(v104, v406, v101);
            }
          }
          goto LABEL_183;
        }
        if ( (__int16)v408 >= 2 )
          goto LABEL_179;
      }
LABEL_183:
      if ( byte_10317ABE5 < 0
        && (*((_DWORD *)v102 + 25) & 8) != 0
        && (int)v101 >= 3
        && (*((_DWORD *)v102 + 25) & 0xC0000000) != 0x40000000
        && *v102
        && VirtualProtect(*v102, 0x2000u, 2u, &v562) )
      {
        _InterlockedAnd((volatile signed __int32 *)v102 + 25, 0x3FFFFFFFu);
        _InterlockedOr((volatile signed __int32 *)v102 + 25, 0x40000000u);
      }
      LatchBase::ReleaseInternal(v102 + 19, v101);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v102, 0, v101);
      v408 &= 0xFFFF0000;
      v406 = 0;
LABEL_51:
      v50 = v416;
      if ( (unsigned int)v416 >= 3 )
        RecoveryUnit::PrePageUpdateHint((RecoveryUnit *)v34, (const struct PageId *)&v414);
      LODWORD(v397) = v50;
      v51 = (Page **)BPool::Get(qword_10317B628, v34, &v414, &v430, v397, &v532);
      v406 = v51;
      v52 = v50 | v408 & 0xFFFF0000;
      v408 = v52;
      if ( v48 )
      {
        v53 = *v51;
        v54 = *(_DWORD *)(v48 + 1280) & 0xF;
        if ( *(Page **)(v48 + 8 * v54 + 1288) != v53 )
        {
          *(_QWORD *)(v48 + 8 * v54 + 1288) = v53;
          ++*(_QWORD *)(v48 + 1280);
          v52 = v408;
        }
      }
      v55 = v52 & 0xFFFFFF | (((v430 >> 3) & 1) << 24);
      v408 = v55;
      v409 = v409 & 0xFFFFFF00 | (v430 >> 4) & 1;
      if ( v49 )
      {
        if ( v48 )
        {
          if ( v48 == *(_QWORD *)(v34 + 7224) )
          {
            ++v49[2917];
            if ( (_DWORD)v533 )
            {
              ++v49[2918];
              v49[2919] += v532;
              if ( v55 >= 0x1000000 )
              {
                ++v49[2920];
                v49[2921] += v532;
              }
            }
          }
        }
      }
      if ( !RecoveryUnit::IsRbIoDb((RecoveryUnit *)v34) || !*(_BYTE *)(v34 + 8272) || !v414 || v414 == 9 && v415 == 1 )
        goto LABEL_58;
      v105 = *v406;
      if ( !*((_WORD *)*v406 + 18) )
      {
LABEL_245:
        v456 = *((_QWORD *)v105 + 5);
        v457 = *((_WORD *)v105 + 24);
        goto LABEL_210;
      }
      v106 = *((_BYTE *)v105 + 1);
      if ( v106 == 11 )
      {
        if ( *((_DWORD *)v105 + 6) == 99 )
          goto LABEL_208;
      }
      else if ( v106 == 8 )
      {
        goto LABEL_244;
      }
      if ( v106 != 9 )
        goto LABEL_245;
LABEL_244:
      if ( *((_DWORD *)v105 + 6) != 99 )
        goto LABEL_245;
LABEL_208:
      v472 = *((_DWORD *)v105 + 8);
      v473 = *((_WORD *)v105 + 18);
      if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v472, ThreadLocalStoragePointer) )
        goto LABEL_245;
      PageHeader::GetIcxLsn(v105, &v456);
LABEL_210:
      v107 = *(_DWORD *)(v34 + 8456);
      do
      {
        v108 = v107 & 0xFFFFFFFE;
        v521 = *(_QWORD *)(v34 + 8444);
        v522 = *(_DWORD *)(v34 + 8452);
        _InterlockedOr(v396, 0);
        v107 = *(_DWORD *)(v34 + 8456);
      }
      while ( v108 != v107 );
      if ( (unsigned int)v521 < (unsigned int)v456
        || (_DWORD)v521 == (_DWORD)v456
        && (HIDWORD(v521) < HIDWORD(v456) || HIDWORD(v521) == HIDWORD(v456) && (unsigned __int16)v522 < v457) )
      {
        if ( *(_BYTE *)(v34 + 27336) )
          goto LABEL_61;
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        if ( *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset + 8LL)
                       + 96LL) == *(_QWORD *)(v34 + 8480)
          || RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v34) )
        {
          goto LABEL_61;
        }
        v109 = *(_DWORD *)(v34 + 8456);
        do
        {
          v110 = v109 & 0xFFFFFFFE;
          v111 = *(LSN *)(v34 + 8444);
          v519 = v111;
          v520 = *(_DWORD *)(v34 + 8452);
          _InterlockedOr(v396, 0);
          v109 = *(_DWORD *)(v34 + 8456);
        }
        while ( v110 != v109 );
        v540 = v111;
        v112 = v520;
        v541 = v520;
        v113 = *v406;
        if ( !*((_WORD *)*v406 + 18) )
          goto LABEL_249;
        v114 = *((_BYTE *)v113 + 1);
        if ( v114 == 11 )
        {
          if ( *((_DWORD *)v113 + 6) == 99 )
          {
LABEL_225:
            v474 = *((_DWORD *)v113 + 8);
            v475 = *((_WORD *)v113 + 18);
            if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v474, ThreadLocalStoragePointer) )
            {
              PageHeader::GetIcxLsn(v113, &v437);
              v115 = v438;
              goto LABEL_227;
            }
LABEL_249:
            v437 = *(LSN *)((char *)v113 + 40);
            v115 = *((_WORD *)v113 + 24);
            v438 = v115;
LABEL_227:
            if ( v519.LowPart < v437.LowPart
              || v519.LowPart == v437.LowPart
              && (v519.HighPart < (unsigned int)v437.HighPart || v519.HighPart == v437.HighPart && v112 < v115) )
            {
              LSN::FormatAsHexString(&v437, v690, &v498);
              LSN::FormatAsHexString(&v540, v691, &v498);
              if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
              {
                v609 = 393216;
                v610 = 0;
                v611 = &v614;
                v612 = &v632;
                v633 = 0;
                v613 = 0;
                v634 = 0;
                v614 = &v635;
                v615 = 52;
                v616 = 5;
                v617 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                v618 = 16;
                v619 = 5;
                v620 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                v621 = 16;
                v622 = 6;
                v623 = 0;
                v624 = 0;
                v625 = 7;
                v626 = 0;
                v627 = 0;
                v628 = 8;
                v629 = 0;
                v630 = 0;
                v631 = 9;
                v635 = *(unsigned __int16 *)(v34 + 1720);
                v636 = v415;
                v637 = v414;
                v638 = v44;
                v639 = *((_BYTE *)*v406 + 1);
                v617 = (GUID *)(v116 + 596);
                v620 = (GUID *)(v116 + 580);
                v117 = -1;
                do
                  ++v117;
                while ( v690[v117] );
                v623 = v690;
                v624 = 2 * v117;
                v118 = -1;
                do
                  ++v118;
                while ( v691[v118] );
                v626 = v691;
                v627 = 2 * v118;
                v458 = 0;
                v119 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v116, &v458);
                v120 = (int *)v119;
                if ( v119 )
                {
                  v121 = -1;
                  do
                    ++v121;
                  while ( *(_WORD *)(v119 + 2 * v121) );
                  v122 = 2 * v121;
                }
                else
                {
                  v122 = 0;
                }
                v123 = v611;
                v611[10] = v120;
                *((_DWORD *)v123 + 22) = v122;
                *((_DWORD *)v123 + 23) = 9;
                XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v608);
              }
            }
            goto LABEL_58;
          }
        }
        else if ( v114 == 8 )
        {
LABEL_248:
          if ( *((_DWORD *)v113 + 6) != 99 )
            goto LABEL_249;
          goto LABEL_225;
        }
        if ( v114 != 9 )
          goto LABEL_249;
        goto LABEL_248;
      }
LABEL_58:
      if ( (__int16)v408 >= 2 && !v43 && *((_BYTE *)*v406 + 1) != v44 )
      {
        if ( v48 )
          *(_QWORD *)(v48 + 1416) = *v406;
        if ( !UtilDbccGetContext()
          || !*((_QWORD *)UtilDbccGetContext() + 6)
          || (v124 = *(_DWORD *)(*((_QWORD *)UtilDbccGetContext() + 6) + 12LL), v124 > 0xD)
          || (v125 = 9792, !_bittest(&v125, v124)) )
        {
          RaiseInconsistencyError(0, 8);
        }
      }
LABEL_61:
      v58 = v428;
      ++*(_DWORD *)(v428 + 4);
      v59 = *(_QWORD *)(v58 + 88);
      if ( v59 )
        ++*(_DWORD *)(v59 + 4);
      if ( (v408 & 0xFF000000) != 0 )
      {
        ++*(_DWORD *)(v58 + 8);
        v87 = *(_QWORD *)(v58 + 88);
        if ( v87 )
          ++*(_DWORD *)(v87 + 8);
        if ( (_BYTE)v409 )
        {
          ++*(_DWORD *)(v58 + 12);
          v88 = *(_QWORD *)(v58 + 88);
          if ( v88 )
            ++*(_DWORD *)(v88 + 12);
        }
      }
      v60 = v423;
      if ( (_DWORD)v533 )
        HoBtAccess::UpdateLatchWaitStats(v423, *((_BYTE *)*v406 + 1), &v532);
      if ( *(_BYTE *)(v34 + 8272) )
      {
        LOBYTE(v398) = 0;
        LOBYTE(v57) = 2;
        if ( !(unsigned __int8)IsPageConsistentOnReadableSecondary(
                                 &v406,
                                 ThreadLocalStoragePointer,
                                 v57,
                                 v50,
                                 v60,
                                 &v400,
                                 (_DWORD)v398) )
        {
          v127 = *v400;
          if ( !*((_WORD *)*v400 + 18) )
            goto LABEL_346;
          v128 = *((_BYTE *)v127 + 1);
          if ( v128 != 11 )
          {
            if ( v128 != 8 )
              goto LABEL_344;
            goto LABEL_345;
          }
          if ( *((_DWORD *)v127 + 6) == 99 )
            goto LABEL_262;
LABEL_344:
          if ( v128 == 9 )
          {
LABEL_345:
            if ( *((_DWORD *)v127 + 6) != 99 )
              goto LABEL_346;
LABEL_262:
            v476 = *((_DWORD *)v127 + 8);
            v477 = *((_WORD *)v127 + 18);
            if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v476, v126) )
              goto LABEL_346;
            PageHeader::GetIcxLsn(v127, &v450);
          }
          else
          {
LABEL_346:
            v450 = *((_QWORD *)v127 + 5);
            v451 = *((_WORD *)v127 + 24);
          }
          v420 = *((_DWORD *)v127 + 8);
          v421 = *((_WORD *)v127 + 18);
          v129 = (__int16)v402;
          v416 = (__int16)v402;
          PageRef::Unlatch((PageRef *)&v400);
          v130 = v429;
          v131 = (_QWORD *)**((_QWORD **)v429 + 1);
          PageRef::UnfixAndWaitForRbIORedoCatchupIfNeeded(
            (PageRef *)&v406,
            (const struct HoBtAttribute *)(v131[1] + 160LL),
            ((unsigned int)*(_QWORD *)((char *)v131 + 20)
           | ((unsigned __int64)(unsigned __int16)WORD2(*(_QWORD *)((char *)v131 + 20)) << 32)) << 16);
          v428 = v131[4];
          v427 = *((_QWORD *)v130 + 1);
          v518 = *((_QWORD *)v130 + 2);
          v426 = *(_QWORD *)v427;
          v535 = 0;
          v132 = *(_QWORD *)(v426 + 32);
          v133 = (*(unsigned int *)(v426 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v426 + 24) << 32)) << 16;
          v134 = *(_QWORD *)(v132 + 2000);
          if ( v134 != v133 || ((v134 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          {
            v135 = *(_QWORD *)(v132 + 2008);
            if ( v135 != v133 || ((v135 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
            {
              v136 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              v137 = *(_QWORD **)(v136 + 256);
              if ( !v137 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v137 = *(_QWORD **)(v136 + 256);
              }
              v138 = __rdtsc();
              v139 = v137[104];
              if ( v138 > v139 || v139 != 0x7FFFFFFFFFFFFFFFLL && v139 - v138 > *(_QWORD *)(v137[76] + 3568LL) )
              {
                v142 = (unsigned int)SOS_Task::Sleep(0, yieldWait) == 2;
                goto LABEL_276;
              }
              v140 = v137[75];
              if ( (*(_DWORD *)(v140 + 188) & 4) != 0 )
              {
                v141 = *(_QWORD *)(v140 + 152);
                if ( (*(_BYTE *)(v141 + 616) & 1) == 0 )
                {
                  v142 = (*(_DWORD *)(v141 + 800) & 0x180) == 0;
LABEL_276:
                  if ( v142 )
                  {
                    LOBYTE(v140) = 124;
                    RaiseExecutionAbortedError(v140);
                  }
                }
              }
            }
          }
          v143 = (unsigned __int16)v129;
          if ( !CommonGlobalState::m_CollectingStatistics
            || byte_10317ABE6 < 0
            || (v144 = *(_QWORD *)(SystemThread_TlsOffset
                                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
            && (v145 = **(struct CSessionTraceFlags ***)(v144 + 56)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v145, 0x337u)
            || (v146 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL)) == 0 )
          {
            SETLSFromTlsMaybeNull = 0;
          }
          else
          {
            SETLSFromTlsMaybeNull = *(struct SEInternalTLS **)(v146 + 96);
          }
          v148 = *(_QWORD **)(v132 + 1832);
LABEL_286:
          v431 = 0;
          if ( v400 )
          {
            if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v400);
              goto LABEL_290;
            }
            v165 = (__int16)v402;
            v166 = (volatile signed __int32 *)v400;
            if ( (*((_WORD *)v400 + 49) & 8) != 0 )
            {
              if ( (__int16)v402 == 3 )
              {
                v165 = 4;
                goto LABEL_352;
              }
              if ( (__int16)v402 >= 2 )
              {
LABEL_352:
                if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
                {
                  v167 = v400[18];
                  if ( v167 )
                  {
                    v168 = *((_QWORD *)v167 + 235);
                    if ( v168 )
                      DirtyPageMgr::OnReleasingBufLatch(v168, v400, v165);
                  }
                }
              }
            }
            if ( byte_10317ABE5 < 0
              && (v166[25] & 8) != 0
              && (int)v165 >= 3
              && (v166[25] & 0xC0000000) != 0x40000000
              && *(_QWORD *)v166
              && VirtualProtect(*(LPVOID *)v166, 0x2000u, 2u, &v570) )
            {
              _InterlockedAnd(v166 + 25, 0x3FFFFFFFu);
              _InterlockedOr(v166 + 25, 0x40000000u);
            }
            LatchBase::ReleaseInternal(v166 + 38, v165);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
              BUF::TraceLatchAcquireRelease(v166, 0, v165);
            v402 &= 0xFFFF0000;
            v400 = 0;
          }
LABEL_290:
          if ( *(_QWORD *)(v132 + 1832) )
          {
            if ( v129 >= 2 )
            {
              PageRef::CatchupPageRedos((PageRef *)&v400, (const struct PageId *)&v420, (struct RecoveryUnit *)v132);
              if ( v400 )
              {
                if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
                {
                  PageRef::UnfixLatchOnly((PageRef *)&v400);
                  goto LABEL_296;
                }
                v169 = (__int16)v402;
                v170 = (volatile signed __int32 *)v400;
                if ( (*((_WORD *)v400 + 49) & 8) != 0 )
                {
                  if ( (__int16)v402 == 3 )
                  {
                    v169 = 4;
                    goto LABEL_372;
                  }
                  if ( (__int16)v402 >= 2 )
                  {
LABEL_372:
                    if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
                    {
                      v171 = v400[18];
                      if ( v171 )
                      {
                        v172 = *((_QWORD *)v171 + 235);
                        if ( v172 )
                          DirtyPageMgr::OnReleasingBufLatch(v172, v400, v169);
                      }
                    }
                  }
                }
                if ( byte_10317ABE5 < 0
                  && (v170[25] & 8) != 0
                  && (int)v169 >= 3
                  && (v170[25] & 0xC0000000) != 0x40000000
                  && *(_QWORD *)v170
                  && VirtualProtect(*(LPVOID *)v170, 0x2000u, 2u, &v569) )
                {
                  _InterlockedAnd(v170 + 25, 0x3FFFFFFFu);
                  _InterlockedOr(v170 + 25, 0x40000000u);
                }
                LatchBase::ReleaseInternal(v170 + 38, v169);
                if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
                  BUF::TraceLatchAcquireRelease(v170, 0, v169);
                v402 &= 0xFFFF0000;
                v400 = 0;
              }
            }
          }
LABEL_296:
          if ( v129 >= 3 )
            RecoveryUnit::PrePageUpdateHint((RecoveryUnit *)v132, (const struct PageId *)&v420);
          LODWORD(v397) = v129;
          v149 = (Page **)BPool::Get(qword_10317B628, v132, &v420, &v431, v397, &v534);
          v400 = v149;
          v150 = v143 | v402 & 0xFFFF0000;
          v402 = v150;
          if ( SETLSFromTlsMaybeNull )
          {
            v151 = *v149;
            v152 = *((_DWORD *)SETLSFromTlsMaybeNull + 320) & 0xF;
            if ( *((Page **)SETLSFromTlsMaybeNull + v152 + 161) != v151 )
            {
              *((_QWORD *)SETLSFromTlsMaybeNull + v152 + 161) = v151;
              ++*((_QWORD *)SETLSFromTlsMaybeNull + 160);
              v150 = v402;
            }
          }
          v153 = v150 & 0xFFFFFF | (((v431 >> 3) & 1) << 24);
          v402 = v153;
          v403 = v403 & 0xFFFFFF00 | (v431 >> 4) & 1;
          if ( v148 )
          {
            if ( SETLSFromTlsMaybeNull )
            {
              if ( SETLSFromTlsMaybeNull == *(struct SEInternalTLS **)(v132 + 7224) )
              {
                ++v148[2917];
                if ( (_DWORD)v535 )
                {
                  ++v148[2918];
                  v148[2919] += v534;
                  if ( v153 >= 0x1000000 )
                  {
                    ++v148[2920];
                    v148[2921] += v534;
                  }
                }
              }
            }
          }
          if ( !RecoveryUnit::IsRbIoDb((RecoveryUnit *)v132)
            || !*(_BYTE *)(v132 + 8272)
            || v129 < 2
            || !v420
            || v420 == 9 && v421 == 1 )
          {
            goto LABEL_441;
          }
          v155 = *v400;
          if ( !*((_WORD *)*v400 + 18) )
            goto LABEL_392;
          v156 = *((_BYTE *)v155 + 1);
          if ( v156 != 11 )
          {
            if ( v156 != 8 )
              goto LABEL_390;
            goto LABEL_391;
          }
          if ( *((_DWORD *)v155 + 6) == 99 )
            goto LABEL_316;
LABEL_390:
          if ( v156 == 9 )
          {
LABEL_391:
            if ( *((_DWORD *)v155 + 6) != 99 )
              goto LABEL_392;
LABEL_316:
            v478 = *((_DWORD *)v155 + 8);
            v479 = *((_WORD *)v155 + 18);
            if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v478, v154) )
              goto LABEL_392;
            PageHeader::GetIcxLsn(v155, &v454);
          }
          else
          {
LABEL_392:
            v454 = *((_QWORD *)v155 + 5);
            v455 = *((_WORD *)v155 + 24);
          }
          v157 = *(_DWORD *)(v132 + 8456);
          do
          {
            v158 = v157 & 0xFFFFFFFE;
            v523 = *(_QWORD *)(v132 + 8444);
            v524 = *(_DWORD *)(v132 + 8452);
            _InterlockedOr(v396, 0);
            v157 = *(_DWORD *)(v132 + 8456);
          }
          while ( v158 != v157 );
          if ( (unsigned int)v523 >= (unsigned int)v454
            && ((_DWORD)v523 != (_DWORD)v454
             || HIDWORD(v523) >= HIDWORD(v454) && (HIDWORD(v523) != HIDWORD(v454) || (unsigned __int16)v524 >= v455)) )
          {
            goto LABEL_441;
          }
          if ( !*(_BYTE *)(v132 + 27336)
            && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL)
                         + 96LL) != *(_QWORD *)(v132 + 8480)
            && !RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v132) )
          {
            v177 = *(_DWORD *)(v132 + 8456);
            do
            {
              v178 = v177 & 0xFFFFFFFE;
              v179 = *(LSN *)(v132 + 8444);
              v525 = v179;
              v526 = *(_DWORD *)(v132 + 8452);
              _InterlockedOr(v396, 0);
              v177 = *(_DWORD *)(v132 + 8456);
            }
            while ( v178 != v177 );
            v542 = v179;
            v180 = v526;
            v543 = v526;
            v181 = *v400;
            if ( !*((_WORD *)*v400 + 18) )
              goto LABEL_474;
            v182 = *((_BYTE *)v181 + 1);
            if ( v182 != 11 )
            {
              if ( v182 != 8 )
                goto LABEL_472;
              goto LABEL_473;
            }
            if ( *((_DWORD *)v181 + 6) == 99 )
              goto LABEL_424;
LABEL_472:
            if ( v182 == 9 )
            {
LABEL_473:
              if ( *((_DWORD *)v181 + 6) != 99 )
                goto LABEL_474;
LABEL_424:
              v482 = *((_DWORD *)v181 + 8);
              v483 = *((_WORD *)v181 + 18);
              if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v482, v154) )
                goto LABEL_474;
              PageHeader::GetIcxLsn(v181, &v441);
              v183 = v442;
            }
            else
            {
LABEL_474:
              v441 = *(LSN *)((char *)v181 + 40);
              v183 = *((_WORD *)v181 + 24);
              v442 = v183;
            }
            if ( v525.LowPart < v441.LowPart
              || v525.LowPart == v441.LowPart
              && (v525.HighPart < (unsigned int)v441.HighPart || v525.HighPart == v441.HighPart && v180 < v183) )
            {
              LSN::FormatAsHexString(&v441, v695, &v459);
              LSN::FormatAsHexString(&v542, v692, &v459);
              if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
              {
                v641 = 393216;
                v642 = 0;
                v643 = &v646;
                v644 = &v664;
                v665 = 0;
                v645 = 0;
                v666 = 0;
                v646 = &v667;
                v647 = 52;
                v648 = 5;
                v649 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                v650 = 16;
                v651 = 5;
                v652 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                v653 = 16;
                v654 = 6;
                v655 = 0;
                v656 = 0;
                v657 = 7;
                v658 = 0;
                v659 = 0;
                v660 = 8;
                v661 = 0;
                v662 = 0;
                v663 = 9;
                v667 = *(unsigned __int16 *)(v132 + 1720);
                v668 = v421;
                v669 = v420;
                v670 = -1;
                v671 = *((_BYTE *)*v400 + 1);
                v649 = (GUID *)(v184 + 596);
                v652 = (GUID *)(v184 + 580);
                v185 = -1;
                do
                  ++v185;
                while ( v695[v185] );
                v655 = v695;
                v656 = 2 * v185;
                v186 = -1;
                do
                  ++v186;
                while ( v692[v186] );
                v658 = v692;
                v659 = 2 * v186;
                v460 = 0;
                v187 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v184, &v460);
                v188 = (int *)v187;
                if ( v187 )
                {
                  v189 = -1;
                  do
                    ++v189;
                  while ( *(_WORD *)(v187 + 2 * v189) );
                  v190 = 2 * v189;
                }
                else
                {
                  v190 = 0;
                }
                v191 = v643;
                v643[10] = v188;
                *((_DWORD *)v191 + 22) = v190;
                *((_DWORD *)v191 + 23) = 9;
                XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v640);
              }
            }
LABEL_441:
            v192 = v518;
            ++*(_DWORD *)(v518 + 4);
            v193 = *(_QWORD *)(v192 + 88);
            if ( v193 )
              ++*(_DWORD *)(v193 + 4);
            if ( (v402 & 0xFF000000) != 0 )
            {
              ++*(_DWORD *)(v192 + 8);
              v194 = *(_QWORD *)(v192 + 88);
              if ( v194 )
                ++*(_DWORD *)(v194 + 8);
              if ( (_BYTE)v403 )
              {
                ++*(_DWORD *)(v192 + 12);
                v195 = *(_QWORD *)(v192 + 88);
                if ( v195 )
                  ++*(_DWORD *)(v195 + 12);
              }
            }
            if ( (_DWORD)v535 )
              HoBtAccess::UpdateLatchWaitStats(v426, *((_BYTE *)*v400 + 1), &v534);
            LODWORD(v426) = 0;
            WORD2(v426) = 0;
            v196 = v427;
            v197 = *(_QWORD *)v427;
            if ( v416 > 1 )
            {
              v198 = *v400;
              v199 = *(_QWORD *)(v197 + 8);
              v200 = *((_DWORD *)*v400 + 6);
              if ( v200 != *(_DWORD *)(v199 + 960)
                || (v154 = *((unsigned __int16 *)v198 + 3), v201 = *(_WORD *)(v199 + 964), (_WORD)v154 != v201)
                && (unsigned __int16)(v154 | v201) > 1u )
              {
                v202 = *((_WORD *)v198 + 3);
                if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
                {
                  PageRef::UnfixLatchOnly((PageRef *)&v400);
                  goto LABEL_458;
                }
                v210 = (__int16)v402;
                v211 = (volatile signed __int32 *)v400;
                if ( (*((_WORD *)v400 + 49) & 8) != 0 )
                {
                  if ( (__int16)v402 == 3 )
                  {
                    v210 = 4;
                    goto LABEL_480;
                  }
                  if ( (__int16)v402 >= 2 )
                  {
LABEL_480:
                    if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
                    {
                      v212 = v400[18];
                      if ( v212 )
                      {
                        v213 = *((_QWORD *)v212 + 235);
                        if ( v213 )
                          DirtyPageMgr::OnReleasingBufLatch(v213, v400, v210);
                      }
                    }
                  }
                }
                if ( byte_10317ABE5 < 0
                  && (v211[25] & 8) != 0
                  && (int)v210 >= 3
                  && (v211[25] & 0xC0000000) != 0x40000000
                  && *(_QWORD *)v211
                  && VirtualProtect(*(LPVOID *)v211, 0x2000u, 2u, &v558) )
                {
                  _InterlockedAnd(v211 + 25, 0x3FFFFFFFu);
                  _InterlockedOr(v211 + 25, 0x40000000u);
                }
                LatchBase::ReleaseInternal(v211 + 38, v210);
                if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
                  BUF::TraceLatchAcquireRelease(v211, 0, v210);
                v402 &= 0xFFFF0000;
                v400 = 0;
LABEL_458:
                v203 = *(_QWORD *)(v197 + 8);
                v500 = *(_DWORD *)(v203 + 960);
                v501 = *(_WORD *)(v203 + 964);
                v502 = 0;
                v503 = v200;
                v504 = v202;
                v505 = 0;
                v204 = (**(__int64 (__fastcall ***)(__int64))v197)(v197);
                RaiseWrongPageError(&v420, &v503, v204, &v500, *(_DWORD *)(v196 + 16));
              }
            }
            v205 = *v400;
            v10 = v429;
            v206 = **((_QWORD **)v429 + 1);
            if ( (*(_DWORD *)(v206 + 20) & 0xE0000000) != 0x80000000 || *(_WORD *)(v206 + 24) > 0xFFu )
            {
              if ( !*((_WORD *)v205 + 18) )
                goto LABEL_500;
              v207 = *((_BYTE *)v205 + 1);
              if ( v207 != 11 )
              {
                if ( v207 != 8 )
                  goto LABEL_498;
                goto LABEL_499;
              }
              if ( *((_DWORD *)v205 + 6) == 99 )
                goto LABEL_464;
LABEL_498:
              if ( v207 == 9 )
              {
LABEL_499:
                if ( *((_DWORD *)v205 + 6) != 99 )
                  goto LABEL_500;
LABEL_464:
                v484 = *((_DWORD *)v205 + 8);
                v485 = *((_WORD *)v205 + 18);
                if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v484, v154) )
                  goto LABEL_500;
                PageHeader::GetIcxLsn(v205, &v452);
                v208 = v453;
              }
              else
              {
LABEL_500:
                v452 = *((_QWORD *)v205 + 5);
                v208 = *((_WORD *)v205 + 24);
                v453 = v208;
              }
              if ( v208 == v451 && v452 == v450 && !*((_DWORD *)v10 + 92) )
              {
                v209 = *(_QWORD *)(v428 + 27664);
                v12 = v412;
                v15 = v417;
                v24 = v410;
                v26 = v413;
                v29 = v399;
                v25 = a5;
                if ( v209 )
                  ++*(_QWORD *)(v209 + 16);
                continue;
              }
            }
            if ( v400 )
            {
              if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
              {
                PageRef::UnfixLatchOnly((PageRef *)&v400);
                goto LABEL_1024;
              }
              v375 = (__int16)v402;
              v376 = (volatile signed __int32 *)v400;
              if ( (*((_WORD *)v400 + 49) & 8) != 0 )
              {
                if ( (__int16)v402 == 3 )
                {
                  v375 = 4;
                  goto LABEL_1032;
                }
                if ( (__int16)v402 >= 2 )
                {
LABEL_1032:
                  if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
                  {
                    v377 = v400[18];
                    if ( v377 )
                    {
                      v378 = *((_QWORD *)v377 + 235);
                      if ( v378 )
                        DirtyPageMgr::OnReleasingBufLatch(v378, v400, v375);
                    }
                  }
                }
              }
              if ( byte_10317ABE5 < 0
                && (v376[25] & 8) != 0
                && (int)v375 >= 3
                && (v376[25] & 0xC0000000) != 0x40000000
                && *(_QWORD *)v376
                && VirtualProtect(*(LPVOID *)v376, 0x2000u, 2u, &v567) )
              {
                _InterlockedAnd(v376 + 25, 0x3FFFFFFFu);
                _InterlockedOr(v376 + 25, 0x40000000u);
              }
              LatchBase::ReleaseInternal(v376 + 38, v375);
              if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v376, 0, v375);
              v402 &= 0xFFFF0000;
              v400 = 0;
            }
LABEL_1024:
            v24 = 0x7FFFFFFF;
            v410 = 0x7FFFFFFF;
            v23 = v425;
            *((_BYTE *)v425 + 21) = 0;
            *((_QWORD *)v23 + 3) = (char *)v23 + 56;
            *((_QWORD *)v23 + 4) = (char *)v23 + 56;
            *((_QWORD *)v23 + 5) = (char *)v23 + 16;
            v374 = *(_QWORD **)(v428 + 27664);
            if ( v374 )
            {
              if ( v407 != 0 )
              {
                ++*v374;
                v12 = v412;
                v15 = v417;
                goto LABEL_13;
              }
              if ( !v407 )
              {
                ++v374[1];
                v12 = v412;
                v15 = v417;
                goto LABEL_13;
              }
              if ( -(v407 != 0) == 1 )
              {
                ++v374[3];
                v12 = v412;
                v15 = v417;
                goto LABEL_13;
              }
            }
            v12 = v412;
            v15 = v417;
            goto LABEL_13;
          }
          v154 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( *(_QWORD *)(v154 + 96) == *(_QWORD *)(v132 + 8480)
            || RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v132) )
          {
            goto LABEL_441;
          }
          if ( !SETLSFromTlsMaybeNull )
            SETLSFromTlsMaybeNull = GetSETLSFromTlsMaybeNull();
          v159 = v400;
          v160 = *v400;
          if ( !*((_WORD *)*v400 + 18) )
            goto LABEL_398;
          v161 = *((_BYTE *)v160 + 1);
          if ( v161 != 11 )
          {
            if ( v161 != 8 )
              goto LABEL_394;
            goto LABEL_395;
          }
          if ( *((_DWORD *)v160 + 6) == 99 )
            goto LABEL_335;
LABEL_394:
          if ( v161 == 9 )
          {
LABEL_395:
            if ( *((_DWORD *)v160 + 6) != 99 )
              goto LABEL_398;
LABEL_335:
            v480 = *((_DWORD *)v160 + 8);
            v481 = *((_WORD *)v160 + 18);
            if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v480, v400) )
            {
              v159 = v400;
              goto LABEL_398;
            }
            PageHeader::GetIcxLsn(v160, &v468);
            v159 = v400;
            v162 = v469;
            v163 = v468;
          }
          else
          {
LABEL_398:
            v163 = *((_QWORD *)v160 + 5);
            v468 = v163;
            v162 = *((_WORD *)v160 + 24);
            v469 = v162;
          }
          v164 = v163;
          v423 = v163;
          if ( v159 )
          {
            if ( (*((_WORD *)v159 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v400);
              goto LABEL_341;
            }
            v173 = (__int16)v402;
            v174 = (volatile signed __int32 *)v400;
            if ( (*((_WORD *)v159 + 49) & 8) != 0 )
            {
              if ( (__int16)v402 == 3 )
              {
                v173 = 4;
                goto LABEL_402;
              }
              if ( (__int16)v402 >= 2 )
              {
LABEL_402:
                if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
                {
                  v175 = v400[18];
                  if ( v175 )
                  {
                    v176 = *((_QWORD *)v175 + 235);
                    if ( v176 )
                      DirtyPageMgr::OnReleasingBufLatch(v176, v400, v173);
                  }
                }
              }
            }
            if ( byte_10317ABE5 < 0
              && (v174[25] & 8) != 0
              && (int)v173 >= 3
              && (v174[25] & 0xC0000000) != 0x40000000
              && *(_QWORD *)v174
              && VirtualProtect(*(LPVOID *)v174, 0x2000u, 2u, &v559) )
            {
              _InterlockedAnd(v174 + 25, 0x3FFFFFFFu);
              _InterlockedOr(v174 + 25, 0x40000000u);
            }
            LatchBase::ReleaseInternal(v174 + 38, v173);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
              BUF::TraceLatchAcquireRelease(v174, 0, v173);
            v402 &= 0xFFFF0000;
            v400 = 0;
LABEL_341:
            v164 = v423;
          }
          v538 = v164;
          v539 = v162;
          v397 = 0;
          RecoveryMgr::WaitForRedoLsnToCatchUp(*(_QWORD *)(v132 + 1832), &v538, 4);
          v129 = v416;
          goto LABEL_286;
        }
      }
      break;
    }
    LODWORD(v427) = 0;
    WORD2(v427) = 0;
    v61 = v426;
    v62 = *(_QWORD *)v426;
    v63 = *v406;
    v64 = *(_QWORD *)(*(_QWORD *)v426 + 8LL);
    v65 = *((_DWORD *)*v406 + 6);
    if ( v65 != *(_DWORD *)(v64 + 960)
      || (v66 = *((_WORD *)v63 + 3), v67 = *(_WORD *)(v64 + 964), v66 != v67) && (unsigned __int16)(v66 | v67) > 1u )
    {
      v214 = *((_WORD *)v63 + 3);
      if ( (*((_WORD *)v406 + 49) & 0x400) != 0 && (__int16)v408 >= 3 )
      {
        PageRef::UnfixLatchOnly((PageRef *)&v406);
LABEL_505:
        v215 = *(_QWORD *)(v62 + 8);
        v506 = *(_DWORD *)(v215 + 960);
        v507 = *(_WORD *)(v215 + 964);
        v508 = 0;
        v509 = v65;
        v510 = v214;
        v511 = 0;
        v216 = (**(__int64 (__fastcall ***)(__int64))v62)(v62);
        RaiseWrongPageError(&v414, &v509, v216, &v506, *(_DWORD *)(v61 + 16));
        goto LABEL_69;
      }
      v217 = (__int16)v408;
      v218 = v406;
      if ( (*((_WORD *)v406 + 49) & 8) != 0 )
      {
        if ( (__int16)v408 == 3 )
        {
          v217 = 4;
          goto LABEL_509;
        }
        if ( (__int16)v408 >= 2 )
        {
LABEL_509:
          if ( (*((_DWORD *)v406 + 25) & 8) != 0 )
          {
            v219 = v406[18];
            if ( v219 )
            {
              v220 = *((_QWORD *)v219 + 235);
              if ( v220 )
                DirtyPageMgr::OnReleasingBufLatch(v220, v406, v217);
            }
          }
        }
      }
      if ( byte_10317ABE5 < 0
        && (*((_DWORD *)v218 + 25) & 8) != 0
        && (int)v217 >= 3
        && (*((_DWORD *)v218 + 25) & 0xC0000000) != 0x40000000
        && *v218
        && VirtualProtect(*v218, 0x2000u, 2u, &v557) )
      {
        _InterlockedAnd((volatile signed __int32 *)v218 + 25, 0x3FFFFFFFu);
        _InterlockedOr((volatile signed __int32 *)v218 + 25, 0x40000000u);
      }
      LatchBase::ReleaseInternal(v218 + 19, v217);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v218, 0, v217);
      v408 &= 0xFFFF0000;
      v406 = 0;
      goto LABEL_505;
    }
LABEL_69:
    v68 = *v406;
    v434 = v68;
    v10 = v429;
    if ( (*((_BYTE *)v68 + 4) & 1) == 0 && !*((_DWORD *)v429 + 91) )
      break;
    PageRef::Unlatch((PageRef *)&v406);
    v227 = *v400;
    if ( !*((_WORD *)*v400 + 18) )
      goto LABEL_657;
    v228 = *((_BYTE *)v227 + 1);
    if ( v228 != 11 )
    {
      if ( v228 != 8 )
      {
LABEL_655:
        if ( v228 != 9 )
          goto LABEL_657;
      }
      if ( *((_DWORD *)v227 + 6) != 99 )
        goto LABEL_657;
      goto LABEL_573;
    }
    if ( *((_DWORD *)v227 + 6) != 99 )
      goto LABEL_655;
LABEL_573:
    v486 = *((_DWORD *)v227 + 8);
    v487 = *((_WORD *)v227 + 18);
    if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v486, v226) )
    {
      PageHeader::GetIcxLsn(v227, &v444);
      goto LABEL_575;
    }
LABEL_657:
    v444 = *((_QWORD *)v227 + 5);
    v445 = *((_WORD *)v227 + 24);
LABEL_575:
    v418 = *((_DWORD *)v227 + 8);
    v419 = *((_WORD *)v227 + 18);
    v229 = (__int16)v402;
    v416 = (__int16)v402;
    v428 = *(_QWORD *)(**((_QWORD **)v10 + 1) + 32LL);
    PageRef::Unlatch((PageRef *)&v400);
    v687[0] = 0;
    v688 = 1;
    v230 = (_QWORD *)*((_QWORD *)v10 + 1);
    v231 = v230[1];
    v232 = *(_QWORD *)(*v230 + 20LL);
    v233 = (**(__int64 (__fastcall ***)(_QWORD))*v230)(*v230);
    v234 = SMOReaderLock::Lock(v687, &v414, v231, v233, v232);
    LOBYTE(v235) = 21;
    lck_StandardHandler(v234, v235);
    v518 = *((_QWORD *)v10 + 1);
    v427 = *((_QWORD *)v10 + 2);
    v426 = *(_QWORD *)v518;
    v537 = 0;
    v236 = *(_QWORD *)(v426 + 32);
    v237 = (*(unsigned int *)(v426 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v426 + 24) << 32)) << 16;
    v238 = *(_QWORD *)(v236 + 2000);
    if ( v238 != v237 || ((v238 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v239 = *(_QWORD *)(v236 + 2008);
      if ( v239 != v237 || ((v239 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v240 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v241 = *(_QWORD **)(v240 + 256);
        if ( !v241 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v241 = *(_QWORD **)(v240 + 256);
        }
        v242 = __rdtsc();
        v243 = v241[104];
        if ( v242 > v243 || v243 != 0x7FFFFFFFFFFFFFFFLL && v243 - v242 > *(_QWORD *)(v241[76] + 3568LL) )
        {
          v246 = (unsigned int)SOS_Task::Sleep(0, yieldWait) == 2;
LABEL_587:
          if ( v246 )
          {
            LOBYTE(v244) = 124;
            RaiseExecutionAbortedError(v244);
          }
          goto LABEL_589;
        }
        v244 = v241[75];
        if ( (*(_DWORD *)(v244 + 188) & 4) != 0 )
        {
          v245 = *(_QWORD *)(v244 + 152);
          if ( (*(_BYTE *)(v245 + 616) & 1) == 0 )
          {
            v246 = (*(_DWORD *)(v245 + 800) & 0x180) == 0;
            goto LABEL_587;
          }
        }
      }
    }
LABEL_589:
    v247 = (unsigned __int16)v229;
    if ( !CommonGlobalState::m_CollectingStatistics
      || byte_10317ABE6 < 0
      || (v248 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v248)
      && (v249 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v248 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v249, 0x337u)
      || (v250 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL)) == 0 )
    {
      v251 = 0;
    }
    else
    {
      v251 = *(struct SEInternalTLS **)(v250 + 96);
    }
    v252 = *(_QWORD **)(v236 + 1832);
    while ( 1 )
    {
      v432 = 0;
      if ( !v400 )
        goto LABEL_601;
      if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
      {
        PageRef::UnfixLatchOnly((PageRef *)&v400);
        goto LABEL_601;
      }
      v269 = (__int16)v402;
      v270 = (volatile signed __int32 *)v400;
      if ( (*((_WORD *)v400 + 49) & 8) != 0 )
      {
        if ( (__int16)v402 == 3 )
        {
          v269 = 4;
LABEL_663:
          if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
          {
            v271 = v400[18];
            if ( v271 )
            {
              v272 = *((_QWORD *)v271 + 235);
              if ( v272 )
                DirtyPageMgr::OnReleasingBufLatch(v272, v400, v269);
            }
          }
          goto LABEL_667;
        }
        if ( (__int16)v402 >= 2 )
          goto LABEL_663;
      }
LABEL_667:
      if ( byte_10317ABE5 < 0
        && (v270[25] & 8) != 0
        && (int)v269 >= 3
        && (v270[25] & 0xC0000000) != 0x40000000
        && *(_QWORD *)v270
        && VirtualProtect(*(LPVOID *)v270, 0x2000u, 2u, &v561) )
      {
        _InterlockedAnd(v270 + 25, 0x3FFFFFFFu);
        _InterlockedOr(v270 + 25, 0x40000000u);
      }
      LatchBase::ReleaseInternal(v270 + 38, v269);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v270, 0, v269);
      v402 &= 0xFFFF0000;
      v400 = 0;
LABEL_601:
      if ( !*(_QWORD *)(v236 + 1832) )
        goto LABEL_607;
      if ( v229 < 2 )
        goto LABEL_607;
      PageRef::CatchupPageRedos((PageRef *)&v400, (const struct PageId *)&v418, (struct RecoveryUnit *)v236);
      if ( !v400 )
        goto LABEL_607;
      if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
      {
        PageRef::UnfixLatchOnly((PageRef *)&v400);
        goto LABEL_607;
      }
      v273 = (__int16)v402;
      v274 = (volatile signed __int32 *)v400;
      if ( (*((_WORD *)v400 + 49) & 8) != 0 )
      {
        if ( (__int16)v402 == 3 )
        {
          v273 = 4;
LABEL_683:
          if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
          {
            v275 = v400[18];
            if ( v275 )
            {
              v276 = *((_QWORD *)v275 + 235);
              if ( v276 )
                DirtyPageMgr::OnReleasingBufLatch(v276, v400, v273);
            }
          }
          goto LABEL_687;
        }
        if ( (__int16)v402 >= 2 )
          goto LABEL_683;
      }
LABEL_687:
      if ( byte_10317ABE5 < 0
        && (v274[25] & 8) != 0
        && (int)v273 >= 3
        && (v274[25] & 0xC0000000) != 0x40000000
        && *(_QWORD *)v274
        && VirtualProtect(*(LPVOID *)v274, 0x2000u, 2u, &v555) )
      {
        _InterlockedAnd(v274 + 25, 0x3FFFFFFFu);
        _InterlockedOr(v274 + 25, 0x40000000u);
      }
      LatchBase::ReleaseInternal(v274 + 38, v273);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v274, 0, v273);
      v402 &= 0xFFFF0000;
      v400 = 0;
LABEL_607:
      if ( v229 >= 3 )
        RecoveryUnit::PrePageUpdateHint((RecoveryUnit *)v236, (const struct PageId *)&v418);
      LODWORD(v397) = v229;
      v253 = (Page **)BPool::Get(qword_10317B628, v236, &v418, &v432, v397, &v536);
      v400 = v253;
      v254 = v247 | v402 & 0xFFFF0000;
      v402 = v254;
      if ( v251 )
      {
        v255 = *v253;
        v256 = *((_DWORD *)v251 + 320) & 0xF;
        if ( *((Page **)v251 + v256 + 161) != v255 )
        {
          *((_QWORD *)v251 + v256 + 161) = v255;
          ++*((_QWORD *)v251 + 160);
          v254 = v402;
        }
      }
      v257 = v254 & 0xFFFFFF | (((v432 >> 3) & 1) << 24);
      v402 = v257;
      v403 = v403 & 0xFFFFFF00 | (v432 >> 4) & 1;
      if ( v252 )
      {
        if ( v251 )
        {
          if ( v251 == *(struct SEInternalTLS **)(v236 + 7224) )
          {
            ++v252[2917];
            if ( (_DWORD)v537 )
            {
              ++v252[2918];
              v252[2919] += v536;
              if ( v257 >= 0x1000000 )
              {
                ++v252[2920];
                v252[2921] += v536;
              }
            }
          }
        }
      }
      if ( !RecoveryUnit::IsRbIoDb((RecoveryUnit *)v236)
        || !*(_BYTE *)(v236 + 8272)
        || v229 < 2
        || !v418
        || v418 == 9 && v419 == 1 )
      {
        goto LABEL_752;
      }
      v259 = *v400;
      if ( !*((_WORD *)*v400 + 18) )
      {
LABEL_703:
        v448 = *((_QWORD *)v259 + 5);
        v449 = *((_WORD *)v259 + 24);
        goto LABEL_629;
      }
      v260 = *((_BYTE *)v259 + 1);
      if ( v260 == 11 )
      {
        if ( *((_DWORD *)v259 + 6) == 99 )
          goto LABEL_627;
      }
      else if ( v260 == 8 )
      {
        goto LABEL_702;
      }
      if ( v260 != 9 )
        goto LABEL_703;
LABEL_702:
      if ( *((_DWORD *)v259 + 6) != 99 )
        goto LABEL_703;
LABEL_627:
      v488 = *((_DWORD *)v259 + 8);
      v489 = *((_WORD *)v259 + 18);
      if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v488, v258) )
        goto LABEL_703;
      PageHeader::GetIcxLsn(v259, &v448);
LABEL_629:
      v261 = *(_DWORD *)(v236 + 8456);
      do
      {
        v262 = v261 & 0xFFFFFFFE;
        v527 = *(_QWORD *)(v236 + 8444);
        v528 = *(_DWORD *)(v236 + 8452);
        _InterlockedOr(v396, 0);
        v261 = *(_DWORD *)(v236 + 8456);
      }
      while ( v262 != v261 );
      if ( (unsigned int)v527 >= (unsigned int)v448
        && ((_DWORD)v527 != (_DWORD)v448
         || HIDWORD(v527) >= HIDWORD(v448) && (HIDWORD(v527) != HIDWORD(v448) || (unsigned __int16)v528 >= v449)) )
      {
        goto LABEL_752;
      }
      if ( !*(_BYTE *)(v236 + 27336)
        && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL)
                     + 96LL) != *(_QWORD *)(v236 + 8480)
        && !RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v236) )
      {
        break;
      }
      v258 = NtCurrentTeb()->ThreadLocalStoragePointer;
      if ( *(_QWORD *)(*(_QWORD *)(v258[SystemThread_TlsIndex] + SystemThread_TlsOffset + 8LL) + 96LL) == *(_QWORD *)(v236 + 8480)
        || RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v236) )
      {
        goto LABEL_752;
      }
      if ( !v251 )
        v251 = GetSETLSFromTlsMaybeNull();
      v263 = v400;
      v264 = *v400;
      if ( !*((_WORD *)*v400 + 18) )
        goto LABEL_709;
      v265 = *((_BYTE *)v264 + 1);
      if ( v265 != 11 )
      {
        if ( v265 != 8 )
        {
LABEL_705:
          if ( v265 != 9 )
            goto LABEL_709;
        }
        if ( *((_DWORD *)v264 + 6) != 99 )
          goto LABEL_709;
        goto LABEL_646;
      }
      if ( *((_DWORD *)v264 + 6) != 99 )
        goto LABEL_705;
LABEL_646:
      v490 = *((_DWORD *)v264 + 8);
      v491 = *((_WORD *)v264 + 18);
      if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v490, v400) )
      {
        PageHeader::GetIcxLsn(v264, &v470);
        v263 = v400;
        v266 = v471;
        v267 = v470;
        goto LABEL_648;
      }
      v263 = v400;
LABEL_709:
      v267 = *((_QWORD *)v264 + 5);
      v470 = v267;
      v266 = *((_WORD *)v264 + 24);
      v471 = v266;
LABEL_648:
      v268 = v267;
      v423 = v267;
      if ( !v263 )
        goto LABEL_653;
      if ( (*((_WORD *)v263 + 49) & 0x400) == 0 || (__int16)v402 < 3 )
      {
        v277 = (__int16)v402;
        v278 = (volatile signed __int32 *)v400;
        if ( (*((_WORD *)v263 + 49) & 8) != 0 )
        {
          if ( (__int16)v402 == 3 )
          {
            v277 = 4;
            goto LABEL_713;
          }
          if ( (__int16)v402 >= 2 )
          {
LABEL_713:
            if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
            {
              v279 = v400[18];
              if ( v279 )
              {
                v280 = *((_QWORD *)v279 + 235);
                if ( v280 )
                  DirtyPageMgr::OnReleasingBufLatch(v280, v400, v277);
              }
            }
          }
        }
        if ( byte_10317ABE5 < 0
          && (v278[25] & 8) != 0
          && (int)v277 >= 3
          && (v278[25] & 0xC0000000) != 0x40000000
          && *(_QWORD *)v278
          && VirtualProtect(*(LPVOID *)v278, 0x2000u, 2u, &v554) )
        {
          _InterlockedAnd(v278 + 25, 0x3FFFFFFFu);
          _InterlockedOr(v278 + 25, 0x40000000u);
        }
        LatchBase::ReleaseInternal(v278 + 38, v277);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v278, 0, v277);
        v402 &= 0xFFFF0000;
        v400 = 0;
        goto LABEL_652;
      }
      PageRef::UnfixLatchOnly((PageRef *)&v400);
LABEL_652:
      v268 = v423;
LABEL_653:
      v544 = v268;
      v545 = v266;
      v397 = 0;
      RecoveryMgr::WaitForRedoLsnToCatchUp(*(_QWORD *)(v236 + 1832), &v544, 4);
      v229 = v416;
    }
    v281 = *(_DWORD *)(v236 + 8456);
    do
    {
      v282 = v281 & 0xFFFFFFFE;
      v283 = *(LSN *)(v236 + 8444);
      v529 = v283;
      v530 = *(_DWORD *)(v236 + 8452);
      _InterlockedOr(v396, 0);
      v281 = *(_DWORD *)(v236 + 8456);
    }
    while ( v282 != v281 );
    v546 = v283;
    v284 = v530;
    v547 = v530;
    v285 = *v400;
    if ( !*((_WORD *)*v400 + 18) )
      goto LABEL_795;
    v286 = *((_BYTE *)v285 + 1);
    if ( v286 != 11 )
    {
      if ( v286 != 8 )
        goto LABEL_793;
      goto LABEL_794;
    }
    if ( *((_DWORD *)v285 + 6) == 99 )
      goto LABEL_735;
LABEL_793:
    if ( v286 == 9 )
    {
LABEL_794:
      if ( *((_DWORD *)v285 + 6) != 99 )
        goto LABEL_795;
LABEL_735:
      v492 = *((_DWORD *)v285 + 8);
      v493 = *((_WORD *)v285 + 18);
      if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v492, v258) )
        goto LABEL_795;
      PageHeader::GetIcxLsn(v285, &v439);
      v287 = v440;
    }
    else
    {
LABEL_795:
      v439 = *(LSN *)((char *)v285 + 40);
      v287 = *((_WORD *)v285 + 24);
      v440 = v287;
    }
    if ( v529.LowPart < v439.LowPart
      || v529.LowPart == v439.LowPart
      && (v529.HighPart < (unsigned int)v439.HighPart || v529.HighPart == v439.HighPart && v284 < v287) )
    {
      LSN::FormatAsHexString(&v439, v693, &v461);
      LSN::FormatAsHexString(&v546, v694, &v461);
      if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
      {
        v577 = 393216;
        v578 = 0;
        v579 = &v582;
        v580 = &v600;
        v601 = 0;
        v581 = 0;
        v602 = 0;
        v582 = &v603;
        v583 = 52;
        v584 = 5;
        v585 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
        v586 = 16;
        v587 = 5;
        v588 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
        v589 = 16;
        v590 = 6;
        v591 = 0;
        v592 = 0;
        v593 = 7;
        v594 = 0;
        v595 = 0;
        v596 = 8;
        v597 = 0;
        v598 = 0;
        v599 = 9;
        v603 = *(unsigned __int16 *)(v236 + 1720);
        v604 = v419;
        v605 = v418;
        v606 = 2;
        v607 = *((_BYTE *)*v400 + 1);
        v585 = (GUID *)(v288 + 596);
        v588 = (GUID *)(v288 + 580);
        v289 = -1;
        do
          ++v289;
        while ( v693[v289] );
        v591 = v693;
        v592 = 2 * v289;
        v290 = -1;
        do
          ++v290;
        while ( v694[v290] );
        v594 = v694;
        v595 = 2 * v290;
        v462 = 0;
        v291 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v288, &v462);
        v292 = (int *)v291;
        if ( v291 )
        {
          v293 = -1;
          do
            ++v293;
          while ( *(_WORD *)(v291 + 2 * v293) );
          v294 = 2 * v293;
        }
        else
        {
          v294 = 0;
        }
        v295 = v579;
        v579[10] = v292;
        *((_DWORD *)v295 + 22) = v294;
        *((_DWORD *)v295 + 23) = 9;
        XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v576);
      }
    }
LABEL_752:
    if ( (__int16)v402 >= 2 && *((_BYTE *)*v400 + 1) != 2 )
    {
      if ( v251 )
        *((_QWORD *)v251 + 177) = *v400;
      if ( !UtilDbccGetContext()
        || !*((_QWORD *)UtilDbccGetContext() + 6)
        || (v296 = *(_DWORD *)(*((_QWORD *)UtilDbccGetContext() + 6) + 12LL), v296 > 0xD)
        || (v297 = 9792, !_bittest(&v297, v296)) )
      {
        RaiseInconsistencyError(0, 8);
      }
    }
    v298 = v427;
    ++*(_DWORD *)(v427 + 4);
    v299 = *(_QWORD *)(v298 + 88);
    if ( v299 )
      ++*(_DWORD *)(v299 + 4);
    if ( (v402 & 0xFF000000) != 0 )
    {
      ++*(_DWORD *)(v298 + 8);
      v300 = *(_QWORD *)(v298 + 88);
      if ( v300 )
        ++*(_DWORD *)(v300 + 8);
      if ( (_BYTE)v403 )
      {
        ++*(_DWORD *)(v298 + 12);
        v301 = *(_QWORD *)(v298 + 88);
        if ( v301 )
          ++*(_DWORD *)(v301 + 12);
      }
    }
    if ( (_DWORD)v537 )
      HoBtAccess::UpdateLatchWaitStats(v426, *((_BYTE *)*v400 + 1), &v536);
    LODWORD(v427) = 0;
    WORD2(v427) = 0;
    v302 = v518;
    v303 = *(_QWORD *)v518;
    if ( v416 > 1 )
    {
      v304 = *v400;
      v305 = *(_QWORD *)(v303 + 8);
      v306 = *((_DWORD *)*v400 + 6);
      if ( v306 != *(_DWORD *)(v305 + 960)
        || (v258 = (_QWORD *)*((unsigned __int16 *)v304 + 3), v307 = *(_WORD *)(v305 + 964), (_WORD)v258 != v307)
        && (unsigned __int16)((unsigned __int16)v258 | v307) > 1u )
      {
        v308 = *((_WORD *)v304 + 3);
        if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)&v400);
          goto LABEL_778;
        }
        v316 = (__int16)v402;
        v317 = (volatile signed __int32 *)v400;
        if ( (*((_WORD *)v400 + 49) & 8) != 0 )
        {
          if ( (__int16)v402 == 3 )
          {
            v316 = 4;
            goto LABEL_801;
          }
          if ( (__int16)v402 >= 2 )
          {
LABEL_801:
            if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
            {
              v318 = v400[18];
              if ( v318 )
              {
                v319 = *((_QWORD *)v318 + 235);
                if ( v319 )
                  DirtyPageMgr::OnReleasingBufLatch(v319, v400, v316);
              }
            }
          }
        }
        if ( byte_10317ABE5 < 0
          && (v317[25] & 8) != 0
          && (int)v316 >= 3
          && (v317[25] & 0xC0000000) != 0x40000000
          && *(_QWORD *)v317
          && VirtualProtect(*(LPVOID *)v317, 0x2000u, 2u, &v553) )
        {
          _InterlockedAnd(v317 + 25, 0x3FFFFFFFu);
          _InterlockedOr(v317 + 25, 0x40000000u);
        }
        LatchBase::ReleaseInternal(v317 + 38, v316);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v317, 0, v316);
        v402 &= 0xFFFF0000;
        v400 = 0;
LABEL_778:
        v309 = *(_QWORD *)(v303 + 8);
        v512 = *(_DWORD *)(v309 + 960);
        v513 = *(_WORD *)(v309 + 964);
        v514 = 0;
        v515 = v306;
        v516 = v308;
        v517 = 0;
        v310 = (**(__int64 (__fastcall ***)(__int64))v303)(v303);
        RaiseWrongPageError(&v418, &v515, v310, &v512, *(_DWORD *)(v302 + 16));
      }
    }
    v311 = *v400;
    v10 = v429;
    v312 = **((_QWORD **)v429 + 1);
    if ( (*(_DWORD *)(v312 + 20) & 0xE0000000) != 0x80000000 || *(_WORD *)(v312 + 24) > 0xFFu )
    {
      if ( !*((_WORD *)v311 + 18) )
        goto LABEL_821;
      v313 = *((_BYTE *)v311 + 1);
      if ( v313 != 11 )
      {
        if ( v313 != 8 )
          goto LABEL_819;
        goto LABEL_820;
      }
      if ( *((_DWORD *)v311 + 6) == 99 )
        goto LABEL_784;
LABEL_819:
      if ( v313 == 9 )
      {
LABEL_820:
        if ( *((_DWORD *)v311 + 6) != 99 )
          goto LABEL_821;
LABEL_784:
        v494 = *((_DWORD *)v311 + 8);
        v495 = *((_WORD *)v311 + 18);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v494, v258) )
          goto LABEL_821;
        PageHeader::GetIcxLsn(v311, &v446);
        v314 = v447;
      }
      else
      {
LABEL_821:
        v446 = *((_QWORD *)v311 + 5);
        v314 = *((_WORD *)v311 + 24);
        v447 = v314;
      }
      if ( v314 == v445 && v446 == v444 && !*((_DWORD *)v10 + 92) )
      {
        v315 = *(_QWORD *)(v428 + 27664);
        if ( v315 )
          ++*(_QWORD *)(v315 + 32);
        AutoLogicalRevertModLock::~AutoLogicalRevertModLock((AutoLogicalRevertModLock *)v687);
        v12 = v412;
        v15 = v417;
        v24 = v410;
        v26 = v413;
        v29 = v399;
        v25 = a5;
        goto LABEL_20;
      }
    }
    if ( !v400 )
      goto LABEL_1092;
    if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v400);
      goto LABEL_1092;
    }
    v384 = (__int16)v402;
    v385 = (volatile signed __int32 *)v400;
    if ( (*((_WORD *)v400 + 49) & 8) != 0 )
    {
      if ( (__int16)v402 == 3 )
      {
        v384 = 4;
        goto LABEL_1098;
      }
      if ( (__int16)v402 >= 2 )
      {
LABEL_1098:
        if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
        {
          v386 = v400[18];
          if ( v386 )
          {
            v387 = *((_QWORD *)v386 + 235);
            if ( v387 )
              DirtyPageMgr::OnReleasingBufLatch(v387, v400, v384);
          }
        }
      }
    }
    if ( byte_10317ABE5 < 0
      && (v385[25] & 8) != 0
      && (int)v384 >= 3
      && (v385[25] & 0xC0000000) != 0x40000000
      && *(_QWORD *)v385
      && VirtualProtect(*(LPVOID *)v385, 0x2000u, 2u, &v564) )
    {
      _InterlockedAnd(v385 + 25, 0x3FFFFFFFu);
      _InterlockedOr(v385 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal(v385 + 38, v384);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v385, 0, v384);
    v402 &= 0xFFFF0000;
    v400 = 0;
LABEL_1092:
    v24 = 0x7FFFFFFF;
    v410 = 0x7FFFFFFF;
    v383 = *(_QWORD *)(v428 + 27664);
    if ( v383 )
      ++*(_QWORD *)(v383 + 24);
    v23 = v425;
    *((_BYTE *)v425 + 21) = 0;
    *((_QWORD *)v23 + 3) = (char *)v23 + 56;
    *((_QWORD *)v23 + 4) = (char *)v23 + 56;
    *((_QWORD *)v23 + 5) = (char *)v23 + 16;
    AutoLogicalRevertModLock::~AutoLogicalRevertModLock((AutoLogicalRevertModLock *)v687);
    v12 = v412;
    v15 = v417;
  }
  v24 = v410;
  v69 = v413;
  if ( v410 != v422 )
    goto LABEL_72;
  if ( v413 == 1 )
  {
    v80 = *((_WORD *)v68 + 11);
    v81 = v80 <= 2u;
LABEL_94:
    if ( !v81 )
    {
      v82 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)v429 + 1) + 8LL) + 180LL) + 2;
      if ( (*((_BYTE *)v429 + 332) & 1) != 0 && v80 > 3u && v82 <= 0x2000 - *((_DWORD *)v429 + 84) )
        v82 = 0x2000 - *((_DWORD *)v429 + 84);
      if ( *((unsigned __int16 *)v68 + 14) <= v82 )
      {
LABEL_97:
        v422 = v410 + 1;
        if ( (*((_WORD *)v406 + 49) & 0x400) != 0 && (__int16)v408 >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)&v406);
          goto LABEL_102;
        }
        v83 = (__int16)v408;
        v84 = v406;
        if ( (*((_WORD *)v406 + 49) & 8) != 0 )
        {
          if ( (__int16)v408 == 3 )
          {
            v83 = 4;
          }
          else if ( (__int16)v408 < 2 )
          {
            goto LABEL_99;
          }
          if ( (*((_DWORD *)v406 + 25) & 8) != 0 )
          {
            v379 = v406[18];
            if ( v379 )
            {
              v380 = *((_QWORD *)v379 + 235);
              if ( v380 )
                DirtyPageMgr::OnReleasingBufLatch(v380, v406, v83);
            }
          }
        }
LABEL_99:
        if ( byte_10317ABE5 < 0
          && (*((_DWORD *)v84 + 25) & 8) != 0
          && (int)v83 >= 3
          && (*((_DWORD *)v84 + 25) & 0xC0000000) != 0x40000000
          && *v84
          && VirtualProtect(*v84, 0x2000u, 2u, &v566) )
        {
          _InterlockedAnd((volatile signed __int32 *)v84 + 25, 0x3FFFFFFFu);
          _InterlockedOr((volatile signed __int32 *)v84 + 25, 0x40000000u);
        }
        LatchBase::ReleaseInternal(v84 + 19, v83);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v84, 0, v83);
        v408 &= 0xFFFF0000;
        v406 = 0;
LABEL_102:
        if ( !v400 )
        {
LABEL_108:
          v24 = 0x7FFFFFFF;
          v410 = 0x7FFFFFFF;
          v23 = v425;
          *((_BYTE *)v425 + 21) = 0;
          *((_QWORD *)v23 + 3) = (char *)v23 + 56;
          *((_QWORD *)v23 + 4) = (char *)v23 + 56;
          *((_QWORD *)v23 + 5) = (char *)v23 + 16;
          v12 = v412;
          v15 = v417;
          goto LABEL_13;
        }
        if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)&v400);
          goto LABEL_108;
        }
        v85 = (__int16)v402;
        v86 = (volatile signed __int32 *)v400;
        if ( (*((_WORD *)v400 + 49) & 8) == 0 )
        {
LABEL_105:
          if ( byte_10317ABE5 < 0
            && (v86[25] & 8) != 0
            && (int)v85 >= 3
            && (v86[25] & 0xC0000000) != 0x40000000
            && *(_QWORD *)v86
            && VirtualProtect(*(LPVOID *)v86, 0x2000u, 2u, &v565) )
          {
            _InterlockedAnd(v86 + 25, 0x3FFFFFFFu);
            _InterlockedOr(v86 + 25, 0x40000000u);
          }
          LatchBase::ReleaseInternal(v86 + 38, v85);
          if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v86, 0, v85);
          v402 &= 0xFFFF0000;
          v400 = 0;
          goto LABEL_108;
        }
        if ( (__int16)v402 == 3 )
        {
          v85 = 4;
        }
        else if ( (__int16)v402 < 2 )
        {
          goto LABEL_105;
        }
        if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
        {
          v381 = v400[18];
          if ( v381 )
          {
            v382 = *((_QWORD *)v381 + 235);
            if ( v382 )
              DirtyPageMgr::OnReleasingBufLatch(v382, v400, v85);
          }
        }
        goto LABEL_105;
      }
    }
  }
  else if ( v413 == 2 )
  {
    v80 = *((_WORD *)v68 + 11);
    v81 = v80 <= 2u;
    if ( v80 >= 2u )
      goto LABEL_94;
    goto LABEL_97;
  }
LABEL_72:
  v70 = v425;
  v71 = *(_DWORD *)(*(_QWORD *)v425 + 16LL);
  if ( v71 )
  {
    v91 = v71 - 1;
    if ( v91 )
    {
      if ( v91 == 1 )
        v405 = *((unsigned __int16 *)v68 + 11) - 1;
      else
        utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\dfs\\access\\BTreeMgr.inl", 419, "Invalid switch value");
    }
    else
    {
      v405 = 0;
    }
  }
  else
  {
    v405 = PageRef::SearchPage((PageRef *)&v406, v425);
    if ( !*((_BYTE *)v70 + 21) || (*((_DWORD *)v70 + 4) & 3) == 1 )
      --v405;
  }
  v30 = *((_BYTE *)v70 + 21);
  v404 = v30;
  if ( v24 < v422 )
  {
    v93 = *((_WORD *)v68 + 11);
    if ( v93 <= 2u )
      goto LABEL_545;
    v94 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)v10 + 1) + 8LL) + 180LL) + 2;
    if ( (*((_BYTE *)v10 + 332) & 1) != 0 && v93 > 3u && v94 <= 0x2000 - *((_DWORD *)v10 + 84) )
      v94 = 0x2000 - *((_DWORD *)v10 + 84);
    if ( *((unsigned __int16 *)v68 + 14) > v94 )
    {
LABEL_545:
      if ( v69 == 1 || v93 >= 2u )
        goto LABEL_76;
    }
    else
    {
      v95 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)v10 + 1) + 8LL) + 180LL) + 2;
      if ( (*((_BYTE *)v10 + 332) & 1) != 0 && v93 > 3u && v95 <= 0x2000 - *((_DWORD *)v10 + 84) )
        v95 = 0x2000 - *((_DWORD *)v10 + 84);
      if ( *((unsigned __int16 *)v68 + 14) <= v95 )
      {
        v96 = 1;
LABEL_135:
        v434 = BTreeMgr::SplitOrShrinkUnsafePage(
                 v10,
                 (struct PageRef *)&v400,
                 (struct PageRef *)&v406,
                 v412,
                 &v405,
                 v96);
        goto LABEL_76;
      }
    }
    v96 = 0;
    goto LABEL_135;
  }
LABEL_76:
  if ( v400 )
  {
    if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v400);
      goto LABEL_82;
    }
    v72 = (__int16)v402;
    v73 = (volatile signed __int32 *)v400;
    if ( (*((_WORD *)v400 + 49) & 8) == 0 )
    {
LABEL_79:
      if ( byte_10317ABE5 < 0
        && (v73[25] & 8) != 0
        && (int)v72 >= 3
        && (v73[25] & 0xC0000000) != 0x40000000
        && *(_QWORD *)v73
        && VirtualProtect(*(LPVOID *)v73, 0x2000u, 2u, &v556) )
      {
        _InterlockedAnd(v73 + 25, 0x3FFFFFFFu);
        _InterlockedOr(v73 + 25, 0x40000000u);
      }
      LatchBase::ReleaseInternal(v73 + 38, v72);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v73, 0, v72);
      v402 &= 0xFFFF0000;
      v400 = 0;
      goto LABEL_82;
    }
    if ( (__int16)v402 == 3 )
    {
      v72 = 4;
    }
    else if ( (__int16)v402 < 2 )
    {
      goto LABEL_79;
    }
    if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
    {
      v224 = v400[18];
      if ( v224 )
      {
        v225 = *((_QWORD *)v224 + 235);
        if ( v225 )
          DirtyPageMgr::OnReleasingBufLatch(v225, v400, v72);
      }
    }
    goto LABEL_79;
  }
LABEL_82:
  v15 = v417;
LABEL_22:
  if ( v24 != a5 )
  {
    v74 = v405;
    v75 = -v405 + 4095LL;
    v423 = v75;
    v76 = v434;
    v77 = (char *)v76 + PageSlot::GetOffset((Page *)((char *)v434 + 2 * v75));
    if ( (*v77 & 1) == 0 )
    {
      v78 = &v77[*(int *)v15];
      goto LABEL_85;
    }
    v672 = -1;
    v675 = 0;
    v674 = 0;
    v680 = 0;
    *(_QWORD *)((char *)&v681 + 2) = 0;
    CDRecord::SetPageComprMgr((CDRecord *)&v673, 0);
    v683 = v74;
    if ( *((char *)v76 + 2) >= 0 )
    {
      PageComprMgr = 0;
      goto LABEL_552;
    }
    Payload = CHadrFsFileRequestMsg::GetPayload(v76);
    CachePrefetch(Payload);
    if ( !v672 || (PageComprMgr = (PageComprMgr *)CDRecord::GetPageComprMgr((CDRecord *)&v673)) == 0 )
    {
      v322 = XMRENoSplitCompressionInfo<64>::SegmentSize(120, v684);
      *(_OWORD *)v322 = 0;
      *(_OWORD *)(v322 + 16) = 0;
      *(_OWORD *)(v322 + 32) = 0;
      *(_OWORD *)(v322 + 48) = 0;
      *(_OWORD *)(v322 + 64) = 0;
      *(_OWORD *)(v322 + 80) = 0;
      *(_OWORD *)(v322 + 96) = 0;
      *(_QWORD *)(v322 + 112) = 0;
      PageComprMgr = PageComprMgr::PageComprMgr((PageComprMgr *)v322);
    }
    if ( !*((_WORD *)v76 + 18) )
      goto LABEL_836;
    v323 = *((_BYTE *)v76 + 1);
    if ( v323 == 11 )
    {
      if ( *((_DWORD *)v76 + 6) == 99 )
      {
LABEL_828:
        v496 = *((_DWORD *)v76 + 8);
        v497 = *((_WORD *)v76 + 18);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v496, v321) )
        {
          PageHeader::GetIcxLsn(v76, &v685);
LABEL_830:
          v324 = (unsigned __int8 *)CHadrFsFileRequestMsg::GetPayload(v76);
          *(_QWORD *)PageComprMgr = v324;
          AlignedLSN::operator=((char *)PageComprMgr + 96, &v685);
          AllocUnitId::AllocUnitId((PageComprMgr *)((char *)PageComprMgr + 108), (Page *)((char *)v76 + 32));
          Offset = PageComprInfo::GetOffset(v574, *v324);
          v531 = *(_DWORD *)Offset;
          v326 = *(__int16 *)(Offset + 4);
          *((_WORD *)PageComprMgr + 8) = -1;
          *((_QWORD *)PageComprMgr + 3) = 0;
          *((_DWORD *)PageComprMgr + 5) = 0;
          *(_QWORD *)((char *)PageComprMgr + 46) = 0;
          *((_QWORD *)PageComprMgr + 7) = 0;
          CDRecord::SetPageComprMgr((PageComprMgr *)((char *)PageComprMgr + 18), 0);
          PageDictionary::Reset((PageComprMgr *)((char *)PageComprMgr + 72));
          if ( (unsigned int)PageComprInfo::HasAnchorRecord(PageComprMgr) )
          {
            v327 = &v324[v326];
            if ( (v324[v326] & 1) != 0 )
            {
              *((_WORD *)PageComprMgr + 8) = 1;
              *((_QWORD *)PageComprMgr + 3) = v327;
              switch ( (unsigned int)CDRecord::GetCDRecType((char *)PageComprMgr + 18) )
              {
                case 0u:
                case 0xCu:
                case 0x10u:
                case 0x14u:
                case 0x18u:
                case 0x1Cu:
                  v328 = *((_QWORD *)PageComprMgr + 3);
                  v329 = *(unsigned __int8 *)(v328 + 1);
                  if ( (v329 & 0x80u) != 0 )
                  {
                    v333 = *(_WORD *)(v328 + 1);
                    *((_WORD *)PageComprMgr + 9) = v333;
                    v330 = 3;
                    v329 = HIBYTE(v333) | ((v333 & 0x7F) << 8);
                  }
                  else
                  {
                    v330 = 2;
                  }
                  *((_WORD *)PageComprMgr + 9) = v329;
                  *((_WORD *)PageComprMgr + 20) = v330;
                  *((_WORD *)PageComprMgr + 22) = v330
                                                + (((unsigned int)*((unsigned __int16 *)PageComprMgr + 9) + 1) >> 1);
                  v331 = *((unsigned __int16 *)PageComprMgr + 9);
                  if ( v331 > 0x1E )
                    *((_WORD *)PageComprMgr + 21) = (__int16)(v331 - 1) / 30;
                  else
                    *((_WORD *)PageComprMgr + 21) = 0;
                  *((_DWORD *)PageComprMgr + 5) = 0;
                  *((_DWORD *)PageComprMgr + 16) = 0;
                  *((_QWORD *)PageComprMgr + 7) = 0;
                  CDRecord::SetPageComprMgr((PageComprMgr *)((char *)PageComprMgr + 18), 0);
                  break;
                case 4u:
                  v334 = (unsigned __int8 *)*((_QWORD *)PageComprMgr + 3);
                  IsGhostVersionRec = CDRecord::IsGhostVersionRec((PageComprMgr *)((char *)PageComprMgr + 18));
                  v336 = (PageComprMgr *)((char *)PageComprMgr + 18);
                  if ( IsGhostVersionRec )
                  {
                    CDRecord::InitRecAddressAndSize(v336, v334, 0xFu);
                    *((_DWORD *)PageComprMgr + 16) = 1;
                  }
                  else
                  {
                    CDRecord::InitRecAddressAndSize(v336, v334, 1u);
                  }
                  goto LABEL_853;
                case 8u:
                  CDRecord::InitRecAddressAndSize(
                    (PageComprMgr *)((char *)PageComprMgr + 18),
                    *((unsigned __int8 **)PageComprMgr + 3),
                    9u);
                  goto LABEL_853;
                default:
                  utassert_fail(
                    1u,
                    "FALSE",
                    "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                    207,
                    "Invalid switch value");
LABEL_853:
                  *((_QWORD *)PageComprMgr + 7) = 0;
                  CDRecord::SetPageComprMgr((PageComprMgr *)((char *)PageComprMgr + 18), 0);
                  break;
              }
            }
            else
            {
              *((_WORD *)PageComprMgr + 8) = 0;
              v337 = 0;
              *((_QWORD *)PageComprMgr + 3) = v327;
              *((_DWORD *)PageComprMgr + 5) = 0;
              *(_DWORD *)((char *)PageComprMgr + 54) = 0;
              switch ( (unsigned __int8)FixedVarRecord::GetRecType(&v324[v326]) )
              {
                case 0u:
                case 2u:
                case 8u:
                case 0xCu:
                  v337 = *((unsigned __int16 *)v327 + 1);
                  if ( (unsigned int)(v337 - 1) > 0x1F9D )
                    RaiseInconsistencyError(*((_QWORD *)PageComprMgr + 3), 6);
                  break;
                case 4u:
                  v337 = 9;
                  break;
                case 6u:
                case 0xAu:
                  break;
                case 0xEu:
                  v337 = 1;
                  break;
                default:
                  utassert_fail(
                    1u,
                    "FALSE",
                    "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                    294,
                    "Invalid switch value");
                  break;
              }
              *((_DWORD *)PageComprMgr + 8) = v337;
              *(_QWORD *)((char *)PageComprMgr + 46) = 0;
              v76 = v434;
            }
            v75 = v423;
          }
          if ( (unsigned int)PageComprInfo::HasDictionary(PageComprMgr) )
          {
            if ( HIWORD(v531) )
              v332 = &v324[*(unsigned __int16 *)&v324[2 * SHIWORD(v531) + 1]];
            else
              v332 = &v324[v326];
            PageDictionary::Init((PageComprMgr *)((char *)PageComprMgr + 72), v332);
          }
          if ( (unsigned int)PageComprInfo::HasCache(PageComprMgr) )
            PageComprInfoCache::Init(*((PageComprInfoCache **)PageComprMgr + 1), PageComprMgr);
LABEL_552:
          v222 = (unsigned __int8 *)v76 + PageSlot::GetOffset((Page *)((char *)v76 + 2 * v75));
          v223 = Page::MinLen(v76);
          v89 = (*v222 & 1) == 0;
          v675 = v222;
          if ( v89 )
          {
            v672 = 0;
            v674 = 0;
            LODWORD(v681) = 0;
            switch ( (unsigned __int8)FixedVarRecord::GetRecType(v222) )
            {
              case 0u:
              case 2u:
              case 8u:
              case 0xCu:
                v223 = *((unsigned __int16 *)v222 + 1);
                if ( v223 - 1 > 0x1F9D )
                  RaiseInconsistencyError(v675, 6);
                break;
              case 4u:
                v223 = 9;
                break;
              case 6u:
              case 0xAu:
                break;
              case 0xEu:
                v223 = 1;
                break;
              default:
                utassert_fail(
                  1u,
                  "FALSE",
                  "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                  294,
                  "Invalid switch value");
                break;
            }
            v676 = v223;
            v680 = (unsigned __int64)v76 + 0x2000;
          }
          else
          {
            v672 = 1;
            switch ( (unsigned int)CDRecord::GetCDRecType(&v673) )
            {
              case 0u:
              case 0xCu:
              case 0x10u:
              case 0x14u:
              case 0x18u:
              case 0x1Cu:
                if ( (v675[1] & 0x80u) != 0 )
                {
                  v338 = HIBYTE(*(_WORD *)(v675 + 1)) | ((*(_WORD *)(v675 + 1) & 0x7F) << 8);
                  v673 = v338;
                  v339 = 3;
                  LOWORD(v678) = 3;
                }
                else
                {
                  v338 = v675[1];
                  v673 = v338;
                  v339 = 2;
                  LOWORD(v678) = 2;
                }
                v679 = v339 + (((unsigned int)v338 + 1) >> 1);
                if ( v338 > 0x1Eu )
                  HIWORD(v678) = (v338 - 1) / 30;
                else
                  HIWORD(v678) = 0;
                v674 = 0;
                v682 = 0;
                break;
              case 4u:
                v340 = v675;
                if ( (unsigned int)CDRecord::IsGhostVersionRec((CDRecord *)&v673) )
                {
                  CDRecord::InitRecAddressAndSize((CDRecord *)&v673, v340, 0xFu);
                  v682 = 1;
                }
                else
                {
                  CDRecord::InitRecAddressAndSize((CDRecord *)&v673, v340, 1u);
                }
                break;
              case 8u:
                CDRecord::InitRecAddressAndSize((CDRecord *)&v673, v675, 9u);
                break;
              default:
                utassert_fail(
                  1u,
                  "FALSE",
                  "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                  207,
                  "Invalid switch value");
                break;
            }
            *(_QWORD *)((char *)&v681 + 2) = (char *)v76 + 0x2000;
            CDRecord::SetPageComprMgr((CDRecord *)&v673, PageComprMgr);
          }
          v15 = v417;
          if ( v672 )
          {
            v424 = 0;
            v78 = (unsigned __int8 *)CDRecord::LocateColumnInternal((CDRecord *)&v673, v417, 0, &v411, &v424);
            if ( v672 && CDRecord::GetPageComprMgr((CDRecord *)&v673) )
            {
              v366 = v672 ? (HeapPageRef *)CDRecord::GetPageComprMgr((CDRecord *)&v673) : 0LL;
              if ( (unsigned int)HeapPageRef::IsValid(v366) )
              {
                if ( !(unsigned int)PhysicalColumnAttribute::IsBitType(v15) )
                {
                  v367 = v424;
                  if ( (v424 & 1) == 0 )
                  {
                    v368 = v411;
                    if ( v672 )
                    {
                      v369 = (PageComprMgr *)CDRecord::GetPageComprMgr((CDRecord *)&v673);
                      v367 = v424;
                    }
                    else
                    {
                      v369 = 0;
                    }
                    v78 = (unsigned __int8 *)PageComprMgr::DecompressColumn(v369, v15, v78, v368, v689, 6u, &v411, v367);
                  }
                }
              }
            }
            v24 = v410;
          }
          else if ( (unsigned int)PhysicalColumnAttribute::IsSparse(v417) )
          {
            if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v673) )
            {
              v78 = (unsigned __int8 *)FixedVarSparseVector::LocateColumn(
                                         (FixedVarSparseVector *)((char *)&v681 + 4),
                                         v15,
                                         &v411,
                                         &v572);
            }
            else
            {
              v78 = 0;
              v411 = 0;
            }
            v24 = v410;
          }
          else
          {
            if ( (unsigned int)PhysicalColumnAttribute::HasSEDefault(v15) )
            {
              FixedVarRecord::InternalCheckNullAndDefault((FixedVarRecord *)&v673, v15, 0, &v464, &v433);
              if ( !v433 && (unsigned int)PhysicalColumnAttribute::HasSEDefault(v15) )
              {
                PhysicalColumnAttribute::GetSEDefault(v15, (const unsigned __int8 **)&v573, &v463);
                v411 = v463;
                v78 = v573;
                v24 = v410;
                goto LABEL_85;
              }
            }
            else
            {
              v464 = 0;
              v433 = 1;
            }
            if ( *(int *)v15 < 0 )
            {
              if ( !v674 )
              {
                v673 = 0;
                v677 = v676;
                if ( (*FixedVarRecord::TagA((FixedVarRecord *)&v673) & 0x10) != 0 )
                {
                  if ( (*FixedVarRecord::TagA((FixedVarRecord *)&v673) & 0x10) != 0 )
                    v342 = *(unsigned __int16 *)&v675[v676];
                  else
                    v342 = 0;
                  v677 += 2 + ((unsigned int)(v342 + 7) >> 3);
                }
                if ( (*FixedVarRecord::TagA((FixedVarRecord *)&v673) & 0x20) != 0 )
                {
                  v343 = FixedVarRecord::ColOffTbl((FixedVarRecord *)&v673);
                  v344 = *(_WORD *)v343;
                  v679 = v344;
                  if ( !v344 )
                  {
                    if ( CFeatureSwitchesMin::FHSMIDataPageAndLogValidationEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin)
                      && TaskInRedo() )
                    {
                      if ( CFeatureSwitchesMin::FDumpOnHSMIDataPageAndLogValidationErrorEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin) )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                    RaiseInconsistencyError(v675, 3);
                    v344 = v679;
                  }
                  v678 = v677 + 2 + 2 * v344;
                  if ( v678 > 0x1F9E )
                  {
                    if ( CFeatureSwitchesMin::FHSMIDataPageAndLogValidationEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin)
                      && TaskInRedo() )
                    {
                      if ( CFeatureSwitchesMin::FDumpOnHSMIDataPageAndLogValidationErrorEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin) )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                    RaiseInconsistencyError(v675, 4);
                    v344 = v679;
                  }
                  v345 = (struct COLOFF *)((char *)v343 + 2);
                  v674 = (unsigned __int16)VarColOffset::operator[]((char *)v343 + 2, v344 - 1LL);
                  if ( v678 > v674 )
                  {
                    if ( CFeatureSwitchesMin::FHSMIDataPageAndLogValidationEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin)
                      && TaskInRedo() )
                    {
                      if ( CFeatureSwitchesMin::FDumpOnHSMIDataPageAndLogValidationErrorEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin) )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                    RaiseInconsistencyError(v675, 4);
                  }
                  v346 = v679;
                  while ( (unsigned int)OffsetArray::IsComplex(v345, (unsigned int)v346 - 1) )
                  {
                    v347 = v679;
                    v348 = FixedVarRecord::ColOffTbl((FixedVarRecord *)&v673);
                    v349 = v348;
                    v350 = (unsigned int)v347;
                    if ( (_DWORD)v347 == 1 )
                      v351 = v678;
                    else
                      v351 = (unsigned __int16)VarColOffset::operator[]((char *)v348 + 2, v347 - 2);
                    v352 = (unsigned __int16)VarColOffset::operator[]((char *)v349 + 2, v350 - 1);
                    v353 = v678;
                    if ( v351 < v678 || v352 < v351 )
                    {
                      RaiseInconsistencyError(v675, 7);
                      v353 = v678;
                    }
                    if ( v351 < v353 || v351 > v674 )
                      goto LABEL_963;
                    v354 = *(_WORD *)&v675[v351];
                    if ( v354 == 5 )
                    {
                      v673 |= 2u;
                      --v679;
                      WORD2(v681) = v351;
                      v355 = (SV_Header *)&v675[(unsigned __int16)v351];
                      if ( (unsigned int)SV_Header::HasColumnIdClusterTable(v355) )
                      {
                        ColumnIdClusterTableSize = SV_Header::GetColumnIdClusterTableSize(v355);
                        WORD3(v681) ^= (WORD3(v681) ^ (ColumnIdClusterTableSize << 11)) & 0x3800;
                      }
                      else
                      {
                        WORD3(v681) &= 0xC7FFu;
                      }
                      ColumnCount = SV_Header::GetColumnCount(v355);
                      WORD3(v681) ^= (ColumnCount ^ WORD3(v681)) & 0x7FF;
                      break;
                    }
                    if ( v354 >= 0x400u )
                    {
                      v673 |= 1u;
                      v89 = v679 == 1;
                      v346 = --v679;
                      if ( !v89 )
                        continue;
                    }
                    break;
                  }
                }
                else
                {
                  v674 = v677;
                  v679 = 0;
                  v678 = v677;
                }
                if ( (unsigned int)FixedVarRecord::HasVersioningInfo((FixedVarRecord *)&v673) )
                {
                  LODWORD(v681) = v674;
                  v674 += 14;
                  VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v673);
                  RecVersioningInfo::GetPtr(VersioningInfo, v549);
                  PayloadSize = VersionRecPtr::GetPayloadSize((VersionRecPtr *)v549);
                  v360 = PayloadSize + v674;
                  v674 += PayloadSize;
                }
                else
                {
                  LODWORD(v681) = 0;
                  v360 = v674;
                }
                if ( v680 && v680 < (unsigned __int64)&v675[v360] )
                {
                  if ( CFeatureSwitchesMin::FHSMIDataPageAndLogValidationEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin)
                    && TaskInRedo() )
                  {
                    if ( CFeatureSwitchesMin::FDumpOnHSMIDataPageAndLogValidationErrorEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin) )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                  RaiseInconsistencyError(v675, 18);
                  v360 = v674;
                }
                if ( v360 - 1 > 0x3F3B )
                {
                  if ( CFeatureSwitchesMin::FHSMIDataPageAndLogValidationEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin)
                    && TaskInRedo() )
                  {
                    if ( CFeatureSwitchesMin::FDumpOnHSMIDataPageAndLogValidationErrorEnabled((CFeatureSwitchesMin *)&g_featureSwitchesMin) )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                  RaiseInconsistencyError(v675, 5);
                }
              }
LABEL_963:
              v361 = -*(_WORD *)v15;
              if ( !(unsigned int)PhysicalColumnAttribute::HasSEDefault(v15)
                || (FixedVarRecord::InternalCheckNullAndDefault((FixedVarRecord *)&v673, v15, 0, &v551, &v466), v466) )
              {
                v362 = v361;
                if ( v361 > (unsigned int)v679 )
                {
                  v78 = v675;
                  v411 = 0;
                  v24 = v410;
                }
                else
                {
                  v363 = FixedVarRecord::ColOffTbl((FixedVarRecord *)&v673);
                  if ( v361 == 1 )
                    v364 = v678;
                  else
                    v364 = (unsigned __int16)VarColOffset::operator[]((char *)v363 + 2, v361 - 2);
                  v365 = (unsigned __int16)VarColOffset::operator[]((char *)v363 + 2, v362 - 1);
                  if ( (unsigned int)v364 < v678 || v365 < (unsigned int)v364 )
                    RaiseInconsistencyError(v675, 7);
                  v411 = v365 - v364;
                  v78 = &v675[v364];
                  v24 = v410;
                }
              }
              else
              {
                PhysicalColumnAttribute::GetSEDefault(v15, (const unsigned __int8 **)&v550, &v467);
                v411 = v467;
                v78 = v550;
                v24 = v410;
              }
            }
            else if ( (unsigned int)PhysicalColumnAttribute::IsBitType(v15) )
            {
              v78 = (unsigned __int8 *)FixedVarRecord::LocateNonNullBitColumn((FixedVarRecord *)&v673, v15, &v411);
              v24 = v410;
            }
            else if ( !(unsigned int)PhysicalColumnAttribute::HasSEDefault(v15)
                   || (FixedVarRecord::InternalCheckNullAndDefault((FixedVarRecord *)&v673, v15, 0, &v552, &v465), v465) )
            {
              v411 = 6;
              v78 = &v675[*(int *)v15];
              v24 = v410;
            }
            else
            {
              PhysicalColumnAttribute::GetSEDefault(v15, (const unsigned __int8 **)&v548, &v436);
              v341 = v436;
              if ( v436 != 6 )
              {
                utassert_fail(
                  1u,
                  "0 == maxSize || cbDefault == maxSize",
                  "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                  769,
                  0);
                v341 = v436;
              }
              v411 = v341;
              v78 = v548;
              v24 = v410;
            }
          }
LABEL_85:
          PageId::SetFromUnalignedBuf((PageId *)&v414, v78);
          if ( !v400 )
          {
LABEL_86:
            v400 = v406;
            v402 = (unsigned __int16)v408 | v402 & 0xFFFF0000;
            v406 = 0;
            v408 &= 0xFFFF0000;
            v12 = v405;
            v412 = v405;
            v405 = -1;
            v410 = --v24;
            v10 = v429;
            v26 = v413;
            v29 = v399;
            v25 = a5;
            goto LABEL_20;
          }
          if ( (*((_WORD *)v400 + 49) & 0x400) != 0 && (__int16)v402 >= 3 )
          {
            PageRef::UnfixLatchOnly((PageRef *)&v400);
            goto LABEL_86;
          }
          v370 = (__int16)v402;
          v371 = (volatile signed __int32 *)v400;
          if ( (*((_WORD *)v400 + 49) & 8) != 0 )
          {
            if ( (__int16)v402 == 3 )
            {
              v370 = 4;
LABEL_1003:
              if ( (*((_DWORD *)v400 + 25) & 8) != 0 )
              {
                v372 = v400[18];
                if ( v372 )
                {
                  v373 = *((_QWORD *)v372 + 235);
                  if ( v373 )
                    DirtyPageMgr::OnReleasingBufLatch(v373, v400, v370);
                }
              }
              goto LABEL_1007;
            }
            if ( (__int16)v402 >= 2 )
              goto LABEL_1003;
          }
LABEL_1007:
          if ( byte_10317ABE5 < 0
            && (v371[25] & 8) != 0
            && (int)v370 >= 3
            && (v371[25] & 0xC0000000) != 0x40000000
            && *(_QWORD *)v371
            && VirtualProtect(*(LPVOID *)v371, 0x2000u, 2u, &v571) )
          {
            _InterlockedAnd(v371 + 25, 0x3FFFFFFFu);
            _InterlockedOr(v371 + 25, 0x40000000u);
          }
          LatchBase::ReleaseInternal(v371 + 38, v370);
          if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v371, 0, v370);
          v402 &= 0xFFFF0000;
          v400 = 0;
          goto LABEL_86;
        }
LABEL_836:
        v685 = *((_QWORD *)v76 + 5);
        v686 = *((_WORD *)v76 + 24);
        goto LABEL_830;
      }
    }
    else if ( v323 == 8 )
    {
LABEL_835:
      if ( *((_DWORD *)v76 + 6) != 99 )
        goto LABEL_836;
      goto LABEL_828;
    }
    if ( v323 != 9 )
      goto LABEL_836;
    goto LABEL_835;
  }
  v31 = v443;
  if ( !*(_QWORD *)v443 )
    goto LABEL_24;
  if ( (*(_WORD *)(*(_QWORD *)v443 + 98LL) & 0x400) != 0 && *((__int16 *)v443 + 6) >= 3 )
  {
    PageRef::UnfixLatchOnly(v443);
    goto LABEL_24;
  }
  v392 = *((__int16 *)v443 + 6);
  v393 = *(_QWORD *)v443;
  if ( (*(_WORD *)(*(_QWORD *)v443 + 98LL) & 8) != 0 )
  {
    if ( v392 == 3 )
    {
      v392 = 4;
      goto LABEL_1144;
    }
    if ( v392 >= 2 )
    {
LABEL_1144:
      if ( (*(_DWORD *)(v393 + 100) & 8) != 0 )
      {
        v394 = *(_QWORD *)(v393 + 144);
        if ( v394 )
        {
          v395 = *(_QWORD *)(v394 + 1880);
          if ( v395 )
            DirtyPageMgr::OnReleasingBufLatch(v395, *(_QWORD *)v443, (unsigned int)v392);
        }
      }
    }
  }
  if ( byte_10317ABE5 < 0
    && (*(_DWORD *)(v393 + 100) & 8) != 0
    && v392 >= 3
    && (*(_DWORD *)(v393 + 100) & 0xC0000000) != 0x40000000
    && *(_QWORD *)v393
    && VirtualProtect(*(LPVOID *)v393, 0x2000u, 2u, &v560) )
  {
    _InterlockedAnd((volatile signed __int32 *)(v393 + 100), 0x3FFFFFFFu);
    _InterlockedOr((volatile signed __int32 *)(v393 + 100), 0x40000000u);
  }
  LatchBase::ReleaseInternal(v393 + 152, (unsigned int)v392);
  if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
    BUF::TraceLatchAcquireRelease(v393, 0, (unsigned int)v392);
LABEL_24:
  *(_QWORD *)v31 = v406;
  *((_WORD *)v31 + 6) = v408;
  v406 = 0;
  v408 &= 0xFFFF0000;
  *((_DWORD *)v31 + 6) = v405;
  v435 = v30 == 0;
LABEL_25:
  PageRef::~PageRef((PageRef *)&v400);
  PageRef::~PageRef((PageRef *)&v406);
  return v435;
}

```

## disassembly

```asm
0x100412840  push    rbp
0x100412842  push    rsi
0x100412843  push    rdi
0x100412844  push    r12
0x100412846  push    r13
0x100412848  push    r14
0x10041284a  push    r15
0x10041284c  lea     rbp, [rsp-0D20h]
0x100412854  sub     rsp, 0E20h
0x10041285b  mov     [rbp+0D50h+var_A30], 0FFFFFFFFFFFFFFFEh
0x100412866  mov     [rsp+0E50h+arg_10], rbx
0x10041286e  mov     rax, cs:__security_cookie
0x100412875  xor     rax, rsp
0x100412878  mov     [rbp+0D50h+var_40], rax
0x10041287f  mov     [rbp+0D50h+var_DC4], r9d
0x100412883  mov     r14d, r8d
0x100412886  mov     rdi, rdx
0x100412889  mov     r13, rcx
0x10041288c  mov     [rbp+0D50h+var_D60], rcx
0x100412890  mov     rax, [rbp+0D50h+arg_28]
0x100412897  mov     [rbp+0D50h+var_D08], rax
0x10041289b  mov     rax, [rbp+0D50h+arg_30]
0x1004128a2  mov     [rbp+0D50h+var_D80], rax
0x1004128a6  mov     rcx, [rbp+0D50h+arg_38]
0x1004128ad  mov     [rbp+0D50h+var_BD8], rcx
0x1004128b4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1004128bb  mov     r15d, eax
0x1004128be  mov     [rbp+0D50h+var_DC8], eax
0x1004128c1  mov     [rsp+0E50h+var_DEC], eax
0x1004128c5  xor     edx, edx
0x1004128c7  mov     [rbp+0D50h+var_DC0], edx
0x1004128ca  mov     [rbp+0D50h+var_DBC], dx
0x1004128ce  mov     [rsp+0E50h+var_DE8], rdx
0x1004128d3  mov     [rsp+0E50h+var_DE0], dl
0x1004128d7  mov     eax, [rsp+0E50h+var_DDC]
0x1004128db  and     eax, 0FFFF0000h
0x1004128e0  mov     [rsp+0E50h+var_DDC], eax
0x1004128e4  and     eax, 0FF00FFFFh
0x1004128e9  mov     [rsp+0E50h+var_DDC], eax
0x1004128ed  mov     [rsp+0E50h+var_DDC], edx
0x1004128f1  mov     [rsp+0E50h+var_E08], rdx
0x1004128f6  mov     [rsp+0E50h+var_E00], dl
0x1004128fa  mov     eax, [rsp+0E50h+var_DFC]
0x1004128fe  and     eax, 0FFFF0000h
0x100412903  mov     [rsp+0E50h+var_DFC], eax
0x100412907  and     eax, 0FF00FFFFh
0x10041290c  mov     [rsp+0E50h+var_DFC], eax
0x100412910  mov     [rsp+0E50h+var_DFC], edx
0x100412914  mov     [rbp+0D50h+var_D48], rdx
0x100412918  mov     eax, 7FFFFFFFh
0x10041291d  mov     [rbp+0D50h+var_DD0], eax
0x100412920  xor     al, al
0x100412922  mov     [rsp+0E50h+var_DF0], al
0x100412926  mov     ebx, edx
0x100412928  mov     [rsp+0E50h+var_E10], al
0x10041292c  mov     rax, [r13+8]
0x100412930  mov     rsi, [rax]
0x100412933  mov     r12, [rsi+8]
0x100412937  add     r12, 210h
0x10041293e  mov     [rbp+0D50h+var_DB0], r12
0x100412942  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x100412949  cmp     [rax], dl
0x10041294b  jz      short loc_100412964
0x10041294d  lea     rcx, qword_10316EC90; this
0x100412954  call    ?GetObjectDataImpl@PerCPUDataImpl@@IEBAPEAXXZ; PerCPUDataImpl::GetObjectDataImpl(void)
0x100412959  inc     qword ptr [rax+50h]
0x10041295d  mov     rcx, [rbp+0D50h+var_BD8]
0x100412964  test    rcx, rcx
0x100412967  jnz     loc_100436575
0x10041296d  mov     eax, [rbp+0D50h+var_DC4]
0x100412970  dec     eax
0x100412972  mov     ecx, 0FFFFFFFFh
0x100412977  cmp     eax, 1
0x10041297a  cmovbe  ecx, [rbp+0D50h+arg_20]
0x100412981  mov     [rbp+0D50h+var_D98], ecx
0x100412984  mov     edx, 3
0x100412989  mov     ecx, 1
0x10041298e  mov     [rbp+0D50h+var_D40], ecx
0x100412991  cmp     [rdi+10h], ebx
0x100412994  jnz     short loc_1004129C1
0x100412996  mov     rax, [rsi+8]
0x10041299a  cmp     [rax+106h], bl
0x1004129a0  jl      loc_10129A9FD
0x1004129a6  mov     rax, [rax+160h]
0x1004129ad  mov     rcx, [rax]
0x1004129b0  mov     eax, [rcx+1Ch]
0x1004129b3  mov     ecx, 1
0x1004129b8  cmp     [rdi+8], eax
0x1004129bb  jnz     loc_100419BD6
0x1004129c1  mov     rax, [rbp+0D50h+var_D80]
0x1004129c5  lea     r14, [rax+10h]
0x1004129c9  cmp     byte ptr [rax+14h], 0
0x1004129cd  jnz     loc_1004B96D8
0x1004129d3  mov     r9d, ebx; int
0x1004129d6  mov     r8, rsi; struct HoBtAccess *
0x1004129d9  mov     rdx, rdi; struct SEBindings *
0x1004129dc  mov     rbx, rax
0x1004129df  mov     rcx, rax; this
0x1004129e2  call    ?InitSlow@SearchInfo@@QEAAXPEBVSEBindings@@PEBVHoBtAccess@@H@Z; SearchInfo::InitSlow(SEBindings const *,HoBtAccess const *,int)
0x1004129e7  mov     byte ptr [rbx+15h], 0
0x1004129eb  lea     rax, [rbx+38h]
0x1004129ef  mov     [rbx+18h], rax
0x1004129f3  mov     [rbx+20h], rax
0x1004129f7  mov     [rbx+28h], r14
0x1004129fb  mov     esi, [rbp+0D50h+var_DD0]
0x1004129fe  xchg    ax, ax
0x100412a00  mov     r14d, [rbp+0D50h+arg_20]
0x100412a07  mov     edi, [rbp+0D50h+var_DC4]
0x100412a0a  cmp     esi, 7FFFFFFFh
0x100412a10  jnz     loc_1004E29E7
0x100412a16  mov     rax, [rbp+0D50h+var_D08]
0x100412a1a  mov     [rsp+0E50h+var_E28], rax
0x100412a1f  lea     rax, [rsp+0E50h+var_DE8]
0x100412a24  mov     [rsp+0E50h+var_E30], rax
0x100412a29  lea     r9, [rbp+0D50h+var_D98]
0x100412a2d  mov     r8d, r14d
0x100412a30  mov     edx, edi
0x100412a32  mov     rcx, r13
0x100412a35  call    ?HandleRoot@BTreeMgr@@AEAA?AW4VR_STATUS@1@W4BTREE_TRAVERSAL_MODE@1@HAEAHAEAVPageRef@@PEAVBTreeHPage@@@Z; BTreeMgr::HandleRoot(BTreeMgr::BTREE_TRAVERSAL_MODE,int,int &,PageRef &,BTreeHPage *)
0x100412a3a  cmp     eax, 2
0x100412a3d  jnz     loc_100412B47
0x100412a43  mov     rcx, [rsp+0E50h+var_DE8]
0x100412a48  mov     rax, [rcx]
0x100412a4b  mov     [rbp+0D50h+var_D48], rax
0x100412a4f  movzx   esi, byte ptr [rax+3]
0x100412a53  mov     [rbp+0D50h+var_DD0], esi
0x100412a56  cmp     esi, r14d
0x100412a59  jl      loc_10129F1D5
0x100412a5f  mov     rax, [rbp+0D50h+var_D08]
0x100412a63  mov     edx, [rax+2Ch]
0x100412a66  mov     rcx, [rax+20h]
0x100412a6a  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x100412a6f  mov     rax, [rbp+0D50h+var_D08]
0x100412a73  xor     r9d, r9d
0x100412a76  mov     [rax+28h], r9d
0x100412a7a  mov     rax, [rsp+0E50h+var_DE8]
0x100412a7f  mov     r8, [rax]
0x100412a82  mov     rcx, [rbx]
0x100412a85  mov     edx, [rcx+10h]
0x100412a88  test    edx, edx
0x100412a8a  jnz     loc_1005A65F9
0x100412a90  mov     rdx, rbx; struct SearchInfo *
0x100412a93  lea     rcx, [rsp+0E50h+var_DE8]; this
0x100412a98  call    ?SearchPage@PageRef@@QEAAHAEAVSearchInfo@@@Z; PageRef::SearchPage(SearchInfo &)
0x100412a9d  mov     [rsp+0E50h+var_DEC], eax
0x100412aa1  cmp     byte ptr [rbx+15h], 0
0x100412aa5  jnz     loc_10047BE1D
0x100412aab  dec     eax
0x100412aad  mov     [rsp+0E50h+var_DEC], eax
0x100412ab1  movzx   eax, byte ptr [rbx+15h]
0x100412ab5  mov     [rsp+0E50h+var_DF0], al
0x100412ab9  mov     cl, 1
0x100412abb  mov     [rsp+0E50h+var_E10], cl
0x100412abf  jmp     short loc_100412AC2
0x100412ac2  xor     ebx, ebx
0x100412ac4  nop     dword ptr [rax+00h]
0x100412ac8  nop     dword ptr [rax+rax+00000000h]
0x100412ad0  mov     qword ptr [r13+16Ch], 0
0x100412adb  test    cl, cl
0x100412add  jz      loc_10041FC27
0x100412ae3  xor     al, al
0x100412ae5  mov     [rsp+0E50h+var_E10], al
0x100412ae9  movzx   r15d, [rsp+0E50h+var_DF0]
0x100412aef  xor     r13d, r13d
0x100412af2  mov     ebx, 400h
0x100412af7  jmp     short loc_100412AFA
0x100412afa  cmp     esi, [rbp+0D50h+arg_20]
0x100412b00  jnz     loc_10042006B
0x100412b06  mov     rsi, [rbp+0D50h+var_D08]
0x100412b0a  mov     rax, [rsi]
0x100412b0d  test    rax, rax
0x100412b10  jnz     loc_10129F2F5
0x100412b16  mov     rax, [rsp+0E50h+var_DE8]
0x100412b1b  mov     [rsi], rax
0x100412b1e  movzx   eax, word ptr [rsp+0E50h+var_DDC]
0x100412b23  mov     [rsi+0Ch], ax
0x100412b27  mov     [rsp+0E50h+var_DE8], r13
0x100412b2c  and     [rsp+0E50h+var_DDC], 0FFFF0000h
0x100412b34  mov     eax, [rsp+0E50h+var_DEC]
0x100412b38  mov     [rsi+18h], eax
0x100412b3b  mov     eax, r13d
0x100412b3e  test    r15b, r15b
0x100412b41  setz    al
0x100412b44  mov     [rbp+0D50h+var_D40], eax
0x100412b47  lea     rcx, [rsp+0E50h+var_E08]; this
0x100412b4c  call    ??1PageRef@@QEAA@XZ; PageRef::~PageRef(void)
0x100412b51  nop
0x100412b52  lea     rcx, [rsp+0E50h+var_DE8]; this
0x100412b57  call    ??1PageRef@@QEAA@XZ; PageRef::~PageRef(void)
0x100412b5c  mov     eax, [rbp+0D50h+var_D40]
0x100412b5f  mov     rcx, [rbp+0D50h+var_40]
0x100412b66  xor     rcx, rsp; StackCookie
0x100412b69  call    __security_check_cookie
0x100412b6e  mov     rbx, [rsp+0E50h+arg_10]
0x100412b76  add     rsp, 0E20h
0x100412b7d  pop     r15
0x100412b7f  pop     r14
0x100412b81  pop     r13
0x100412b83  pop     r12
0x100412b85  pop     rdi
0x100412b86  pop     rsi
0x100412b87  pop     rbp
0x100412b88  retn
0x100419bd6  mov     ebx, ecx
0x100419bd8  cmp     r14d, 1
0x100419bdc  cmovz   ebx, edx
0x100419bdf  jmp     loc_1004129C1
0x10041fc27  mov     rcx, [rbp+0D50h+var_BD8]; this
0x10041fc2e  test    rcx, rcx
0x10041fc31  jnz     loc_1004375AE
0x10041fc37  mov     r15d, 2
0x10041fc3d  mov     eax, r15d
0x10041fc40  cmp     esi, [rbp+0D50h+var_D98]
0x10041fc43  mov     ecx, 4
0x10041fc48  cmovle  eax, ecx
0x10041fc4b  mov     [rbp+0D50h+var_DB8], eax
0x10041fc4e  cmp     edi, 3
0x10041fc51  jz      loc_10129AA53
0x10041fc57  mov     rcx, [r13+8]
0x10041fc5b  mov     [rbp+0D50h+var_D78], rcx
0x10041fc5f  mov     rax, [r13+10h]
0x10041fc63  mov     [rbp+0D50h+var_D68], rax
0x10041fc67  mov     rax, [rcx]
0x10041fc6a  mov     [rbp+0D50h+var_D90], rax
0x10041fc6e  mov     [rbp+0D50h+var_B44], 0
0x10041fc79  mov     r14, [rax+20h]
0x10041fc7d  movzx   ecx, word ptr [rax+18h]
0x10041fc81  shl     rcx, 20h
0x10041fc85  mov     eax, [rax+14h]
0x10041fc88  or      rcx, rax
0x10041fc8b  shl     rcx, 10h
0x10041fc8f  mov     rax, [r14+7D0h]
0x10041fc96  cmp     rax, rcx
0x10041fc99  jz      loc_10129AA62
0x10041fc9f  mov     rax, [r14+7D8h]
0x10041fca6  cmp     rax, rcx
0x10041fca9  jz      loc_10129AA77
0x10041fcaf  mov     rdx, gs:58h
0x10041fcb8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041fcbf  mov     ecx, [rax]
0x10041fcc1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041fcc8  mov     ebx, [rax]
0x10041fcca  add     rbx, [rdx+rcx*8]
0x10041fcce  mov     r8, [rbx+100h]
0x10041fcd5  test    r8, r8
0x10041fcd8  jz      loc_10129AA8C
0x10041fcde  rdtsc
0x10041fce0  shl     rdx, 20h
0x10041fce4  or      rax, rdx
0x10041fce7  mov     rcx, [r8+340h]
0x10041fcee  cmp     rax, rcx
0x10041fcf1  ja      loc_10047C04A
0x10041fcf7  mov     rdx, 7FFFFFFFFFFFFFFFh
0x10041fd01  cmp     rcx, rdx
0x10041fd04  jz      short loc_10041FD1D
0x10041fd06  sub     rcx, rax
0x10041fd09  mov     rax, [r8+260h]
0x10041fd10  cmp     rcx, [rax+0DF0h]
0x10041fd17  ja      loc_10047C04A
0x10041fd1d  mov     rcx, [r8+258h]
0x10041fd24  mov     eax, [rcx+0BCh]
0x10041fd2a  test    al, 4
0x10041fd2c  jnz     loc_10047C05E
0x10041fd32  xor     ebx, ebx
0x10041fd34  movzx   r13d, byte ptr [r14+2050h]
0x10041fd3c  mov     r12d, 0FFh
0x10041fd42  test    r13b, r13b
0x10041fd45  cmovz   r12d, r15d
0x10041fd49  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x10041fd50  cmp     byte ptr [rax], 0
0x10041fd53  jz      loc_10129AAB4
0x10041fd59  test    cs:byte_10317ABE6, 80h
0x10041fd60  jnz     loc_10129AAB4
0x10041fd66  mov     r8, gs:58h
0x10041fd6f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041fd76  mov     ecx, [rax]
0x10041fd78  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041fd7f  mov     edx, [rax]
0x10041fd81  add     rdx, [r8+rcx*8]
0x10041fd85  mov     rax, [rdx]
0x10041fd88  test    rax, rax
0x10041fd8b  jz      short loc_10041FD9D
0x10041fd8d  mov     rax, [rax+38h]
0x10041fd91  mov     rcx, [rax]
0x10041fd94  test    rcx, rcx
0x10041fd97  jnz     loc_10129AAA1
0x10041fd9d  mov     r8, gs:58h
0x10041fda6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041fdad  mov     ecx, [rax]
0x10041fdaf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041fdb6  mov     edx, [rax]
0x10041fdb8  add     rdx, [r8+rcx*8]
0x10041fdbc  mov     rax, [rdx+8]
0x10041fdc0  test    rax, rax
0x10041fdc3  jz      loc_10129AAB4
0x10041fdc9  mov     r15, [rax+60h]
0x10041fdcd  jmp     short loc_10041FDD0
0x10041fdd0  mov     rsi, [r14+728h]
0x10041fdd7  mov     [rbp+0D50h+var_D58], ebx
0x10041fdda  mov     rcx, [rsp+0E50h+var_DE8]
  ... truncated ...
```
