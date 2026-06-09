# BTreeMgr::MoveRowFromLeftSibling(PageRef &,PageRef &,int,int &,PageRef &)

- ea: `0x1012ab8a0`
- end: `0x1012b3e27`
- name: `?MoveRowFromLeftSibling@BTreeMgr@@AEAAXAEAVPageRef@@0HAEAH0@Z`
- size: `34183`
- prototype: `void __fastcall(BTreeMgr *__hidden this, struct PageRef *, struct PageRef *, int, int *, struct PageRef *)`
- caller_count: `2`
- callee_count: `34`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1005bbfc0`
- `0x1012a6450`

## callees

- `0x100401010`
- `0x100401490`
- `0x100402000`
- `0x100403030`
- `0x10040da40`
- `0x10040da80`
- `0x10040eca0`
- `0x100432c80`
- `0x10043ba50`
- `0x10043e660`
- `0x1004410c0`
- `0x10044ee10`
- `0x1004729d0`
- `0x100472a40`
- `0x10047ffb0`
- `0x100480030`
- `0x100553e20`
- `0x1005bcea0`
- `0x1005bd340`
- `0x1005be9d0`
- `0x1005becb0`
- `0x1005d9f70`
- `0x10069f4f0`
- `0x1012ab8a0`
- `0x1012b5110`
- `0x1012c9010`
- `0x1013a6b10`
- `0x1016c9e80`
- `0x1018c9d70`
- `0x101907610`
- `0x101cb13d0`
- `0x101ced0e0`
- `0x1021d8a90`
- `0x1023ae3e0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x1012abc83`
- `KERNEL32!VirtualProtect` at `0x1012ac241`
- `KERNEL32!VirtualProtect` at `0x1012ac460`
- `KERNEL32!VirtualProtect` at `0x1012ad1fe`
- `KERNEL32!VirtualProtect` at `0x1012ad57f`
- `KERNEL32!VirtualProtect` at `0x1012ad931`
- `KERNEL32!VirtualProtect` at `0x1012adf73`
- `KERNEL32!VirtualProtect` at `0x1012ae195`
- `KERNEL32!VirtualProtect` at `0x1012aef2d`
- `KERNEL32!VirtualProtect` at `0x1012af2a9`
- `KERNEL32!VirtualProtect` at `0x1012af660`
- `KERNEL32!VirtualProtect` at `0x1012afd58`
- `KERNEL32!VirtualProtect` at `0x1012aff71`
- `KERNEL32!VirtualProtect` at `0x1012b0d00`
- `KERNEL32!VirtualProtect` at `0x1012b1070`
- `KERNEL32!VirtualProtect` at `0x1012b1413`
- `KERNEL32!VirtualProtect` at `0x1012b240f`
- `KERNEL32!VirtualProtect` at `0x1012b261d`
- `KERNEL32!VirtualProtect` at `0x1012b3750`
- `KERNEL32!VirtualProtect` at `0x1012b3917`
- `KERNEL32!VirtualProtect` at `0x1012b3b07`
- `KERNEL32!VirtualProtect` at `0x1012b3d09`
- `KERNEL32!VirtualProtect` at `0x1012abc83`
- `KERNEL32!VirtualProtect` at `0x1012ac241`
- `KERNEL32!VirtualProtect` at `0x1012ac460`
- `KERNEL32!VirtualProtect` at `0x1012ad1fe`
- `KERNEL32!VirtualProtect` at `0x1012ad57f`
- `KERNEL32!VirtualProtect` at `0x1012ad931`
- `KERNEL32!VirtualProtect` at `0x1012adf73`
- `KERNEL32!VirtualProtect` at `0x1012ae195`
- `KERNEL32!VirtualProtect` at `0x1012aef2d`
- `KERNEL32!VirtualProtect` at `0x1012af2a9`
- `KERNEL32!VirtualProtect` at `0x1012af660`
- `KERNEL32!VirtualProtect` at `0x1012afd58`
- `KERNEL32!VirtualProtect` at `0x1012aff71`
- `KERNEL32!VirtualProtect` at `0x1012b0d00`
- `KERNEL32!VirtualProtect` at `0x1012b1070`
- `KERNEL32!VirtualProtect` at `0x1012b1413`
- `KERNEL32!VirtualProtect` at `0x1012b240f`
- `KERNEL32!VirtualProtect` at `0x1012b261d`
- `KERNEL32!VirtualProtect` at `0x1012b3750`
- `KERNEL32!VirtualProtect` at `0x1012b3917`
- `KERNEL32!VirtualProtect` at `0x1012b3b07`
- `KERNEL32!VirtualProtect` at `0x1012b3d09`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1012ace64`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1012aeb8f`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1012b096f`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1012abf6e`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1012adc9e`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1012afa8e`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1012b3de5`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1012b3de5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012abacd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b1a0a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b1c2c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b1dc2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b20de`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b2bee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b2e10`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b2fb3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b32cf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012abacd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b1a0a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b1c2c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b1dc2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b20de`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b2bee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b2e10`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b2fb3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012b32cf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1012ac00f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1012add3f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1012afb2f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1012ac00f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1012add3f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1012afb2f`
- `sqldk!SystemThread_TlsIndex` at `0x1012abe00`
- `sqldk!SystemThread_TlsIndex` at `0x1012abfb8`
- `sqldk!SystemThread_TlsIndex` at `0x1012ac0af`
- `sqldk!SystemThread_TlsIndex` at `0x1012ac857`
- `sqldk!SystemThread_TlsIndex` at `0x1012aceed`
- `sqldk!SystemThread_TlsIndex` at `0x1012adb38`
- `sqldk!SystemThread_TlsIndex` at `0x1012adce8`
- `sqldk!SystemThread_TlsIndex` at `0x1012adde0`
- `sqldk!SystemThread_TlsIndex` at `0x1012ae597`
- `sqldk!SystemThread_TlsIndex` at `0x1012aec1a`
- `sqldk!SystemThread_TlsIndex` at `0x1012af91c`
- `sqldk!SystemThread_TlsIndex` at `0x1012afad8`
- `sqldk!SystemThread_TlsIndex` at `0x1012afbda`
- `sqldk!SystemThread_TlsIndex` at `0x1012b0377`
- `sqldk!SystemThread_TlsIndex` at `0x1012b09fd`
- `sqldk!SystemThread_TlsIndex` at `0x1012b3dad`
- `sqldk!SystemThread_TlsOffset` at `0x1012abe09`
- `sqldk!SystemThread_TlsOffset` at `0x1012abfc1`
- `sqldk!SystemThread_TlsOffset` at `0x1012ac0b8`
- `sqldk!SystemThread_TlsOffset` at `0x1012ac860`
- `sqldk!SystemThread_TlsOffset` at `0x1012acef6`
- `sqldk!SystemThread_TlsOffset` at `0x1012adb41`
- `sqldk!SystemThread_TlsOffset` at `0x1012adcf1`
- `sqldk!SystemThread_TlsOffset` at `0x1012adde9`
- `sqldk!SystemThread_TlsOffset` at `0x1012ae5a0`
- `sqldk!SystemThread_TlsOffset` at `0x1012aec23`
- `sqldk!SystemThread_TlsOffset` at `0x1012af925`
- `sqldk!SystemThread_TlsOffset` at `0x1012afae1`
- `sqldk!SystemThread_TlsOffset` at `0x1012afbe3`
- `sqldk!SystemThread_TlsOffset` at `0x1012b0380`
- `sqldk!SystemThread_TlsOffset` at `0x1012b0a06`
- `sqldk!SystemThread_TlsOffset` at `0x1012b3db6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012abe34`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012adb6a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012af94e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012b3dcf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012abe34`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012adb6a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012af94e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012b3dcf`

## string_xrefs

- `0x1012abad4`: `BTreeMgr::MoveRowFromLeftSibling`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall BTreeMgr::MoveRowFromLeftSibling(
        BTreeMgr *this,
        __int64 **a2,
        struct PageRef *a3,
        unsigned int a4,
        int *a5,
        __int64 **a6)
{
  BTreeMgr *v7; // rdi
  __int64 *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // ebx
  __int64 *v13; // rax
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rbx
  void *v16; // rcx
  RecoveryUnit *v17; // rbx
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  _QWORD *v22; // r8
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  struct CSessionTraceFlags *v27; // rcx
  struct SEInternalTLS *v28; // rax
  _QWORD *v29; // rsi
  __int64 *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  volatile signed __int32 *v33; // rbx
  void *v34; // rcx
  __int64 *v35; // rbx
  unsigned int v36; // edi
  __int64 *v37; // rax
  __int64 v38; // rcx
  volatile signed __int32 *v39; // rbx
  void *v40; // rcx
  __int64 *v41; // rbx
  unsigned int v42; // edi
  __int64 *v43; // rax
  unsigned int v44; // ecx
  __int64 v45; // rdx
  _DWORD *v46; // r8
  _QWORD *v47; // r9
  unsigned int v48; // edx
  DWORD v49; // edx
  _QWORD *v50; // rcx
  unsigned int *v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r11
  char v54; // al
  char v55; // al
  LSN *v56; // rdi
  _DWORD *v57; // rbx
  int v58; // eax
  int v59; // ecx
  LSN *v60; // rdx
  unsigned __int16 v61; // bx
  __int64 v62; // r11
  char v63; // al
  char v64; // al
  unsigned __int16 v65; // r11
  RecoveryUnit *v66; // rbx
  __int64 v67; // r10
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  int *v71; // rdx
  __int64 v72; // rcx
  DWORD v73; // ecx
  _DWORD **v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r11
  char v77; // al
  char v78; // al
  __int16 v79; // r11
  __int64 v80; // xmm1_8
  __int64 *v81; // rax
  __int64 v82; // rcx
  volatile signed __int32 *v83; // rbx
  void *v84; // rcx
  __int64 *v85; // rbx
  unsigned int v86; // edi
  __int64 v87; // rcx
  unsigned int v88; // eax
  int v89; // ecx
  unsigned __int8 v90; // cf
  int v91; // eax
  __int64 *v92; // rcx
  __int64 v93; // rcx
  volatile signed __int32 *v94; // rbx
  void *v95; // rcx
  __int64 *v96; // rbx
  unsigned int v97; // edi
  _DWORD *v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // r15
  __int64 *v103; // r9
  __int64 v104; // rcx
  __int64 v105; // rdx
  __int16 v106; // r8
  __int16 v107; // ax
  int v108; // esi
  __int16 v109; // r14
  __int64 v110; // rcx
  volatile signed __int32 *v111; // rbx
  void *v112; // rcx
  __int64 *v113; // rbx
  unsigned int v114; // edi
  __int64 v115; // rcx
  unsigned __int16 v116; // ax
  RecoveryUnit *v117; // rbx
  unsigned __int64 v118; // rcx
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rbx
  _QWORD *v122; // rcx
  unsigned __int64 v123; // rax
  unsigned __int64 v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // rax
  struct CSessionTraceFlags *v127; // rcx
  struct SEInternalTLS *v128; // rax
  _QWORD *v129; // rsi
  __int64 *v130; // rax
  __int64 v131; // rax
  __int64 v132; // rcx
  volatile signed __int32 *v133; // rbx
  void *v134; // rcx
  __int64 *v135; // rbx
  unsigned int v136; // edi
  __int64 *v137; // rax
  __int64 v138; // rcx
  volatile signed __int32 *v139; // rbx
  void *v140; // rcx
  __int64 *v141; // rbx
  unsigned int v142; // edi
  unsigned int v143; // ecx
  __int64 v144; // rdx
  _DWORD *v145; // r8
  _QWORD *v146; // r9
  unsigned int v147; // edx
  DWORD v148; // edx
  _QWORD *v149; // rcx
  unsigned int *v150; // r8
  __int64 v151; // rdx
  __int64 v152; // r11
  char v153; // al
  char v154; // al
  LSN *v155; // rdi
  _DWORD *v156; // rbx
  int v157; // eax
  int v158; // ecx
  LSN *v159; // rdx
  unsigned __int16 v160; // bx
  __int64 v161; // r11
  char v162; // al
  char v163; // al
  unsigned __int16 v164; // r11
  __int64 v165; // rbx
  __int64 v166; // r10
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rax
  int *v170; // rdx
  __int64 v171; // rcx
  DWORD v172; // ecx
  _DWORD **v173; // rax
  __int64 v174; // rdx
  __int64 v175; // r11
  char v176; // al
  char v177; // al
  __int16 v178; // r11
  __int64 v179; // xmm1_8
  __int64 *v180; // rax
  __int64 v181; // rcx
  volatile signed __int32 *v182; // rbx
  void *v183; // rcx
  __int64 *v184; // rbx
  unsigned int v185; // edi
  __int64 v186; // rcx
  unsigned int v187; // eax
  int v188; // ecx
  BOOL v189; // eax
  int v190; // edi
  __int64 *v191; // rcx
  __int64 v192; // rcx
  volatile signed __int32 *v193; // rbx
  void *v194; // rcx
  __int64 *v195; // rbx
  unsigned int v196; // edi
  _DWORD *v197; // rcx
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // rax
  __int64 v201; // r15
  __int64 *v202; // r9
  __int64 v203; // rcx
  __int64 v204; // rdx
  __int16 v205; // r8
  __int16 v206; // ax
  int v207; // esi
  __int16 v208; // r14
  __int64 v209; // rcx
  volatile signed __int32 *v210; // rbx
  void *v211; // rcx
  __int64 *v212; // rbx
  unsigned int v213; // edi
  __int64 v214; // rcx
  unsigned __int16 v215; // ax
  __int64 v216; // rdx
  __int64 *v217; // rsi
  __int64 v218; // rsi
  int v219; // eax
  __int64 v220; // rdx
  RecoveryUnit *v221; // rbx
  unsigned __int64 v222; // rcx
  __int64 v223; // rax
  __int64 v224; // rax
  __int64 v225; // rbx
  _QWORD *v226; // rcx
  unsigned __int64 v227; // rax
  unsigned __int64 v228; // rdx
  __int64 v229; // rcx
  __int64 v230; // rax
  struct CSessionTraceFlags *v231; // rcx
  struct SEInternalTLS *v232; // rax
  _QWORD *v233; // rsi
  __int64 v234; // rax
  __int64 v235; // rcx
  volatile signed __int32 *v236; // rbx
  void *v237; // rcx
  _QWORD *v238; // rbx
  unsigned int v239; // edi
  __int64 v240; // rcx
  volatile signed __int32 *v241; // rbx
  void *v242; // rcx
  _QWORD *v243; // rbx
  unsigned int v244; // edi
  _QWORD *v245; // rax
  unsigned int v246; // r8d
  __int64 v247; // rdx
  _DWORD *v248; // rcx
  _QWORD *v249; // r9
  __int64 v250; // rax
  unsigned int v251; // edx
  _QWORD *v252; // rcx
  unsigned int *v253; // r8
  __int64 v254; // rdx
  __int64 v255; // r11
  char v256; // al
  char v257; // al
  LSN *v258; // rdi
  _DWORD *v259; // rbx
  int v260; // eax
  int v261; // ecx
  LSN *v262; // rdx
  unsigned __int16 v263; // bx
  __int64 v264; // r11
  char v265; // al
  char v266; // al
  unsigned __int16 v267; // r11
  RecoveryUnit *v268; // rbx
  __int64 v269; // r10
  __int64 v270; // rax
  __int64 v271; // rax
  __int64 v272; // rax
  int *v273; // rdx
  __int64 v274; // rcx
  DWORD v275; // ecx
  _DWORD **v276; // rax
  __int64 v277; // rdx
  __int64 v278; // r11
  char v279; // al
  char v280; // al
  __int16 v281; // r11
  __int64 v282; // xmm1_8
  __int64 v283; // rcx
  volatile signed __int32 *v284; // rbx
  void *v285; // rcx
  _QWORD *v286; // rbx
  unsigned int v287; // edi
  __int64 v288; // rdx
  int v289; // r9d
  unsigned int v290; // eax
  int v291; // r9d
  int v292; // ecx
  int v293; // eax
  __int64 v294; // rcx
  volatile signed __int32 *v295; // rbx
  void *v296; // rcx
  _QWORD *v297; // rbx
  unsigned int v298; // edi
  _DWORD *v299; // rcx
  __int64 v300; // rax
  __int64 v301; // rax
  __int64 v302; // rax
  __int64 v303; // rsi
  __int64 v304; // rcx
  __int64 v305; // rdx
  __int16 v306; // r8
  __int16 v307; // ax
  int v308; // r14d
  __int16 v309; // r15
  __int64 v310; // rcx
  volatile signed __int32 *v311; // rbx
  void *v312; // rcx
  _QWORD *v313; // rbx
  unsigned int v314; // edi
  __int64 v315; // rcx
  unsigned __int16 v316; // ax
  struct PageComprInfo *v317; // r13
  __int16 v318; // di
  char v319; // al
  char v320; // al
  __int16 v321; // r11
  unsigned __int8 *v322; // r9
  __int16 v323; // dx
  int v324; // ecx
  __int64 v325; // rax
  __int64 v326; // rcx
  unsigned __int8 *v327; // r8
  char *v328; // rdx
  unsigned __int8 *v329; // rdx
  unsigned __int8 v330; // al
  __int64 v331; // r8
  int v332; // edi
  __int64 v333; // rax
  unsigned __int8 *v334; // rax
  __int16 v335; // cx
  PageComprInfoCache *v336; // rcx
  DWORD v337; // ebx
  char *v338; // r8
  bool v339; // zf
  char v340; // dl
  char *v341; // r8
  unsigned __int16 v342; // cx
  BTreeMgr *v343; // r15
  __int64 v344; // rbx
  unsigned __int16 *v345; // r14
  __int16 *v346; // rsi
  struct Page **v347; // rax
  struct Page *v348; // rcx
  volatile signed __int32 *v349; // rbx
  struct Page *v350; // rcx
  struct Page **v351; // rbx
  unsigned int v352; // edi
  struct Page *v353; // rcx
  volatile signed __int32 *v354; // rbx
  struct Page *v355; // rcx
  struct Page **v356; // rbx
  unsigned int v357; // edi
  __int64 v358; // rsi
  struct PageComprInfo *v359; // r13
  __int16 v360; // di
  char v361; // al
  char v362; // al
  __int16 v363; // r11
  unsigned __int8 *v364; // r9
  __int16 v365; // dx
  int v366; // ecx
  __int64 v367; // rax
  __int64 v368; // rcx
  unsigned __int8 *v369; // r8
  char *v370; // rdx
  unsigned __int8 *v371; // rdx
  unsigned __int8 v372; // al
  _WORD *v373; // rbx
  _BYTE *v374; // r8
  unsigned __int8 v375; // r8
  unsigned __int8 *v376; // rdx
  __int16 v377; // ax
  __int16 v378; // cx
  unsigned __int16 v379; // cx
  unsigned int v380; // eax
  __int64 v381; // rax
  unsigned __int8 *v382; // rax
  __int16 v383; // cx
  PageComprInfoCache *v384; // rcx
  DWORD v385; // ebx
  char *v386; // r8
  char v387; // dl
  char *v388; // r8
  unsigned __int16 v389; // cx
  __int64 v390; // rbx
  struct Page **v391; // rax
  struct Page *v392; // rcx
  volatile signed __int32 *v393; // rbx
  struct Page *v394; // rcx
  struct Page **v395; // rbx
  unsigned int v396; // edi
  struct Page *v397; // rcx
  volatile signed __int32 *v398; // rbx
  struct Page *v399; // rcx
  struct Page **v400; // rbx
  unsigned int v401; // edi
  __int64 v402; // rcx
  volatile signed __int32 *v403; // rbx
  void *v404; // rcx
  _QWORD *v405; // rbx
  unsigned int v406; // edi
  struct Page **v407; // rax
  struct Page *v408; // rcx
  volatile signed __int32 *v409; // rbx
  struct Page *v410; // rcx
  struct Page **v411; // rbx
  unsigned int v412; // edi
  __int64 v413; // rbx
  struct Worker *v414; // rcx
  signed __int32 v415[8]; // [rsp+0h] [rbp-33C8h] BYREF
  struct SMOLockOrder *v416; // [rsp+20h] [rbp-33A8h]
  _QWORD *v417; // [rsp+70h] [rbp-3358h] BYREF
  char v418; // [rsp+78h] [rbp-3350h]
  int v419; // [rsp+7Ch] [rbp-334Ch]
  unsigned int v420; // [rsp+80h] [rbp-3348h]
  char v421; // [rsp+88h] [rbp-3340h]
  char v422; // [rsp+89h] [rbp-333Fh]
  char v423; // [rsp+8Ah] [rbp-333Eh]
  char v424; // [rsp+8Bh] [rbp-333Dh]
  __int16 v425; // [rsp+8Ch] [rbp-333Ch]
  struct Page **v426; // [rsp+90h] [rbp-3338h] BYREF
  char v427; // [rsp+98h] [rbp-3330h]
  unsigned int v428; // [rsp+9Ch] [rbp-332Ch]
  RecoveryUnit *v429; // [rsp+A8h] [rbp-3320h]
  RecoveryUnit *v430; // [rsp+B0h] [rbp-3318h]
  RecoveryUnit *v431; // [rsp+B8h] [rbp-3310h]
  char v432; // [rsp+C0h] [rbp-3308h]
  char v433; // [rsp+C1h] [rbp-3307h]
  char v434; // [rsp+C2h] [rbp-3306h]
  char v435; // [rsp+C3h] [rbp-3305h]
  char v436; // [rsp+C4h] [rbp-3304h]
  char v437; // [rsp+C5h] [rbp-3303h]
  char v438; // [rsp+C6h] [rbp-3302h]
  char v439; // [rsp+C7h] [rbp-3301h]
  char v440; // [rsp+C8h] [rbp-3300h]
  char v441; // [rsp+C9h] [rbp-32FFh]
  char v442; // [rsp+CAh] [rbp-32FEh]
  char v443; // [rsp+CBh] [rbp-32FDh]
  char v444; // [rsp+CCh] [rbp-32FCh]
  char v445; // [rsp+CDh] [rbp-32FBh]
  char v446; // [rsp+CEh] [rbp-32FAh]
  char v447; // [rsp+CFh] [rbp-32F9h]
  char v448; // [rsp+D0h] [rbp-32F8h]
  char v449; // [rsp+D1h] [rbp-32F7h]
  char v450; // [rsp+D2h] [rbp-32F6h]
  int v451; // [rsp+D4h] [rbp-32F4h] BYREF
  __int16 v452; // [rsp+D8h] [rbp-32F0h]
  char v453; // [rsp+DCh] [rbp-32ECh]
  char v454; // [rsp+DDh] [rbp-32EBh]
  char v455; // [rsp+DEh] [rbp-32EAh]
  char v456; // [rsp+DFh] [rbp-32E9h]
  int v457; // [rsp+E0h] [rbp-32E8h]
  int v458; // [rsp+E8h] [rbp-32E0h]
  int v459; // [rsp+F0h] [rbp-32D8h]
  int v460; // [rsp+F8h] [rbp-32D0h]
  int v461; // [rsp+100h] [rbp-32C8h]
  int v462; // [rsp+108h] [rbp-32C0h]
  int v463; // [rsp+110h] [rbp-32B8h]
  int v464; // [rsp+118h] [rbp-32B0h]
  int v465; // [rsp+120h] [rbp-32A8h]
  int v466; // [rsp+128h] [rbp-32A0h]
  int v467; // [rsp+130h] [rbp-3298h]
  int v468; // [rsp+138h] [rbp-3290h]
  int v469; // [rsp+140h] [rbp-3288h]
  int v470; // [rsp+148h] [rbp-3280h]
  int v471; // [rsp+150h] [rbp-3278h]
  int v472; // [rsp+158h] [rbp-3270h]
  int v473; // [rsp+160h] [rbp-3268h]
  int v474; // [rsp+168h] [rbp-3260h]
  int v475; // [rsp+170h] [rbp-3258h]
  int v476; // [rsp+188h] [rbp-3240h]
  int v477; // [rsp+1A0h] [rbp-3228h]
  int v478; // [rsp+1A8h] [rbp-3220h]
  int v479; // [rsp+1B0h] [rbp-3218h] BYREF
  __int16 v480; // [rsp+1B4h] [rbp-3214h]
  int v481; // [rsp+1B8h] [rbp-3210h] BYREF
  __int16 v482; // [rsp+1BCh] [rbp-320Ch]
  int v483; // [rsp+1C0h] [rbp-3208h] BYREF
  __int16 v484; // [rsp+1C4h] [rbp-3204h]
  __int16 v485; // [rsp+1C6h] [rbp-3202h]
  char v486; // [rsp+1C8h] [rbp-3200h]
  char v487; // [rsp+1C9h] [rbp-31FFh]
  char v488; // [rsp+1CAh] [rbp-31FEh]
  char v489; // [rsp+1CBh] [rbp-31FDh]
  char v490; // [rsp+1CCh] [rbp-31FCh]
  char v491; // [rsp+1CDh] [rbp-31FBh]
  char v492; // [rsp+1CEh] [rbp-31FAh]
  char v493; // [rsp+1CFh] [rbp-31F9h]
  char v494; // [rsp+1D0h] [rbp-31F8h]
  char v495; // [rsp+1D1h] [rbp-31F7h]
  char v496; // [rsp+1D2h] [rbp-31F6h]
  char v497; // [rsp+1D3h] [rbp-31F5h]
  char v498; // [rsp+1D4h] [rbp-31F4h]
  char v499; // [rsp+1D5h] [rbp-31F3h]
  char v500; // [rsp+1D6h] [rbp-31F2h]
  char v501; // [rsp+1D7h] [rbp-31F1h]
  char v502; // [rsp+1D8h] [rbp-31F0h]
  char v503; // [rsp+1D9h] [rbp-31EFh]
  char v504; // [rsp+1DAh] [rbp-31EEh]
  char v505; // [rsp+1DBh] [rbp-31EDh]
  char v506; // [rsp+1DCh] [rbp-31ECh]
  char v507; // [rsp+1DDh] [rbp-31EBh]
  __int16 v508; // [rsp+1E8h] [rbp-31E0h]
  __int16 v509; // [rsp+1F0h] [rbp-31D8h]
  __int16 v510; // [rsp+1F8h] [rbp-31D0h]
  __int16 v511; // [rsp+200h] [rbp-31C8h]
  __int16 v512; // [rsp+208h] [rbp-31C0h]
  __int16 v513; // [rsp+210h] [rbp-31B8h]
  __int16 v514; // [rsp+218h] [rbp-31B0h]
  __int16 v515; // [rsp+220h] [rbp-31A8h]
  __int16 v516; // [rsp+228h] [rbp-31A0h]
  __int16 v517; // [rsp+230h] [rbp-3198h]
  __int16 v518; // [rsp+238h] [rbp-3190h]
  __int16 v519; // [rsp+240h] [rbp-3188h]
  __int16 v520; // [rsp+248h] [rbp-3180h]
  __int16 v521; // [rsp+250h] [rbp-3178h]
  __int16 v522; // [rsp+258h] [rbp-3170h]
  __int16 v523; // [rsp+260h] [rbp-3168h]
  __int16 v524; // [rsp+268h] [rbp-3160h]
  __int16 v525; // [rsp+270h] [rbp-3158h]
  __int16 v526; // [rsp+278h] [rbp-3150h]
  __int16 v527; // [rsp+280h] [rbp-3148h]
  __int16 v528; // [rsp+288h] [rbp-3140h]
  __int16 v529; // [rsp+290h] [rbp-3138h]
  __int16 v530; // [rsp+298h] [rbp-3130h]
  __int16 v531; // [rsp+2A0h] [rbp-3128h]
  __int16 v532; // [rsp+2A8h] [rbp-3120h]
  __int16 v533; // [rsp+2B0h] [rbp-3118h]
  __int16 v534; // [rsp+2B8h] [rbp-3110h]
  __int16 v535; // [rsp+2C0h] [rbp-3108h]
  __int16 v536; // [rsp+2C8h] [rbp-3100h]
  __int16 v537; // [rsp+2D0h] [rbp-30F8h]
  __int16 v538; // [rsp+2D8h] [rbp-30F0h]
  __int16 v539; // [rsp+2E0h] [rbp-30E8h]
  __int16 v540; // [rsp+2E8h] [rbp-30E0h]
  __int16 v541; // [rsp+2F0h] [rbp-30D8h]
  __int16 v542; // [rsp+2F8h] [rbp-30D0h]
  __int16 v543; // [rsp+300h] [rbp-30C8h]
  __int16 v544; // [rsp+308h] [rbp-30C0h]
  __int16 v545; // [rsp+310h] [rbp-30B8h]
  __int16 v546; // [rsp+318h] [rbp-30B0h]
  __int16 v547; // [rsp+320h] [rbp-30A8h]
  __int16 v548; // [rsp+328h] [rbp-30A0h]
  __int16 v549; // [rsp+330h] [rbp-3098h]
  __int16 v550; // [rsp+338h] [rbp-3090h]
  char v551; // [rsp+340h] [rbp-3088h]
  char v552; // [rsp+341h] [rbp-3087h]
  bool v553; // [rsp+342h] [rbp-3086h]
  unsigned int v554; // [rsp+344h] [rbp-3084h] BYREF
  unsigned int v555; // [rsp+348h] [rbp-3080h] BYREF
  int v556; // [rsp+350h] [rbp-3078h]
  int v557; // [rsp+358h] [rbp-3070h]
  int v558; // [rsp+360h] [rbp-3068h]
  int v559; // [rsp+368h] [rbp-3060h]
  int v560; // [rsp+370h] [rbp-3058h]
  char v561; // [rsp+378h] [rbp-3050h]
  char v562; // [rsp+379h] [rbp-304Fh]
  __int16 v563; // [rsp+380h] [rbp-3048h]
  char v564; // [rsp+388h] [rbp-3040h]
  char v565; // [rsp+389h] [rbp-303Fh]
  char v566; // [rsp+38Ah] [rbp-303Eh]
  char v567; // [rsp+38Bh] [rbp-303Dh]
  char v568; // [rsp+38Ch] [rbp-303Ch]
  char v569; // [rsp+38Dh] [rbp-303Bh]
  char v570; // [rsp+38Eh] [rbp-303Ah]
  char v571; // [rsp+38Fh] [rbp-3039h]
  char v572; // [rsp+390h] [rbp-3038h]
  char v573; // [rsp+391h] [rbp-3037h]
  char v574; // [rsp+392h] [rbp-3036h]
  bool v575; // [rsp+393h] [rbp-3035h]
  char v576; // [rsp+394h] [rbp-3034h]
  char v577; // [rsp+395h] [rbp-3033h]
  char v578; // [rsp+396h] [rbp-3032h]
  char v579; // [rsp+397h] [rbp-3031h]
  char v580; // [rsp+398h] [rbp-3030h]
  char v581; // [rsp+399h] [rbp-302Fh]
  char v582; // [rsp+39Ah] [rbp-302Eh]
  char v583; // [rsp+39Bh] [rbp-302Dh]
  char v584; // [rsp+39Ch] [rbp-302Ch]
  char v585; // [rsp+39Dh] [rbp-302Bh]
  char v586; // [rsp+39Eh] [rbp-302Ah]
  char v587; // [rsp+39Fh] [rbp-3029h]
  char v588; // [rsp+3A0h] [rbp-3028h]
  bool v589; // [rsp+3A1h] [rbp-3027h]
  char v590; // [rsp+3A2h] [rbp-3026h]
  char v591; // [rsp+3A3h] [rbp-3025h]
  __int64 v592; // [rsp+3A8h] [rbp-3020h] BYREF
  __int16 v593; // [rsp+3B0h] [rbp-3018h]
  __int64 v594; // [rsp+3B8h] [rbp-3010h] BYREF
  __int16 v595; // [rsp+3C0h] [rbp-3008h]
  char v596; // [rsp+3C8h] [rbp-3000h]
  __int64 *v597; // [rsp+3D0h] [rbp-2FF8h]
  __int64 *v598; // [rsp+3D8h] [rbp-2FF0h]
  __int64 *v599; // [rsp+3E0h] [rbp-2FE8h]
  __int64 *v600; // [rsp+3E8h] [rbp-2FE0h]
  __int64 *v601; // [rsp+3F0h] [rbp-2FD8h]
  __int64 *v602; // [rsp+3F8h] [rbp-2FD0h]
  __int64 *v603; // [rsp+400h] [rbp-2FC8h]
  __int64 *v604; // [rsp+408h] [rbp-2FC0h]
  __int64 *v605; // [rsp+410h] [rbp-2FB8h]
  __int64 *v606; // [rsp+418h] [rbp-2FB0h]
  __int64 *v607; // [rsp+420h] [rbp-2FA8h]
  struct Page **v608; // [rsp+428h] [rbp-2FA0h]
  struct Page **v609; // [rsp+430h] [rbp-2F98h]
  struct Page **v610; // [rsp+438h] [rbp-2F90h]
  LSN v611; // [rsp+450h] [rbp-2F78h]
  DWORD v612; // [rsp+458h] [rbp-2F70h]
  LSN v613; // [rsp+45Ch] [rbp-2F6Ch]
  DWORD LowPart; // [rsp+464h] [rbp-2F64h]
  LSN v615; // [rsp+468h] [rbp-2F60h]
  DWORD v616; // [rsp+470h] [rbp-2F58h]
  int v617; // [rsp+474h] [rbp-2F54h]
  int v618; // [rsp+478h] [rbp-2F50h]
  BTreeMgr *v619; // [rsp+480h] [rbp-2F48h]
  int v620; // [rsp+488h] [rbp-2F40h]
  unsigned int v621; // [rsp+48Ch] [rbp-2F3Ch]
  __int64 v622; // [rsp+490h] [rbp-2F38h]
  int v623; // [rsp+498h] [rbp-2F30h]
  __int64 v624; // [rsp+49Ch] [rbp-2F2Ch]
  int v625; // [rsp+4A4h] [rbp-2F24h]
  __int64 v626; // [rsp+4A8h] [rbp-2F20h]
  int v627; // [rsp+4B0h] [rbp-2F18h]
  int v628; // [rsp+4B4h] [rbp-2F14h]
  int v629; // [rsp+4B8h] [rbp-2F10h]
  int v630; // [rsp+4BCh] [rbp-2F0Ch]
  int v631; // [rsp+4C0h] [rbp-2F08h]
  unsigned int v632; // [rsp+4C4h] [rbp-2F04h] BYREF
  int v633; // [rsp+4C8h] [rbp-2F00h]
  int v634; // [rsp+4CCh] [rbp-2EFCh]
  struct SEInternalTLS *SETLSFromTlsMaybeNull; // [rsp+4D0h] [rbp-2EF8h]
  int v636; // [rsp+4D8h] [rbp-2EF0h]
  __int16 v637; // [rsp+4DCh] [rbp-2EECh]
  __int16 v638; // [rsp+4DEh] [rbp-2EEAh]
  struct SEInternalTLS *v639; // [rsp+4E0h] [rbp-2EE8h]
  int v640; // [rsp+4E8h] [rbp-2EE0h]
  __int16 v641; // [rsp+4ECh] [rbp-2EDCh]
  __int16 v642; // [rsp+4EEh] [rbp-2EDAh]
  struct SEInternalTLS *v643; // [rsp+4F0h] [rbp-2ED8h]
  int v644; // [rsp+4F8h] [rbp-2ED0h]
  __int16 v645; // [rsp+4FCh] [rbp-2ECCh]
  __int16 v646; // [rsp+4FEh] [rbp-2ECAh]
  __int64 v647; // [rsp+500h] [rbp-2EC8h] BYREF
  __int16 v648; // [rsp+508h] [rbp-2EC0h]
  __int64 v649; // [rsp+510h] [rbp-2EB8h] BYREF
  __int16 v650; // [rsp+518h] [rbp-2EB0h]
  LSN v651; // [rsp+520h] [rbp-2EA8h] BYREF
  unsigned __int16 v652; // [rsp+528h] [rbp-2EA0h]
  __int64 v653; // [rsp+530h] [rbp-2E98h] BYREF
  unsigned __int16 v654; // [rsp+538h] [rbp-2E90h]
  __int64 v655; // [rsp+540h] [rbp-2E88h] BYREF
  unsigned __int16 v656; // [rsp+548h] [rbp-2E80h]
  LSN v657; // [rsp+550h] [rbp-2E78h] BYREF
  unsigned __int16 v658; // [rsp+558h] [rbp-2E70h]
  __int64 v659; // [rsp+560h] [rbp-2E68h] BYREF
  __int16 v660; // [rsp+568h] [rbp-2E60h]
  __int64 v661; // [rsp+570h] [rbp-2E58h] BYREF
  unsigned __int16 v662; // [rsp+578h] [rbp-2E50h]
  LSN v663; // [rsp+580h] [rbp-2E48h] BYREF
  unsigned __int16 v664; // [rsp+588h] [rbp-2E40h]
  int v665; // [rsp+590h] [rbp-2E38h] BYREF
  __int16 v666; // [rsp+594h] [rbp-2E34h]
  int v667; // [rsp+598h] [rbp-2E30h] BYREF
  __int16 v668; // [rsp+59Ch] [rbp-2E2Ch]
  int v669; // [rsp+5A0h] [rbp-2E28h] BYREF
  __int16 v670; // [rsp+5A4h] [rbp-2E24h]
  int v671; // [rsp+5A8h] [rbp-2E20h] BYREF
  __int16 v672; // [rsp+5ACh] [rbp-2E1Ch]
  int v673; // [rsp+5B0h] [rbp-2E18h] BYREF
  __int16 v674; // [rsp+5B4h] [rbp-2E14h]
  int v675; // [rsp+5B8h] [rbp-2E10h] BYREF
  __int16 v676; // [rsp+5BCh] [rbp-2E0Ch]
  int v677; // [rsp+5C0h] [rbp-2E08h] BYREF
  __int16 v678; // [rsp+5C4h] [rbp-2E04h]
  int v679; // [rsp+5C8h] [rbp-2E00h] BYREF
  __int16 v680; // [rsp+5CCh] [rbp-2DFCh]
  int v681; // [rsp+5D0h] [rbp-2DF8h] BYREF
  __int16 v682; // [rsp+5D4h] [rbp-2DF4h]
  int v683; // [rsp+5D8h] [rbp-2DF0h] BYREF
  __int16 v684; // [rsp+5DCh] [rbp-2DECh]
  int v685; // [rsp+5E0h] [rbp-2DE8h] BYREF
  __int16 v686; // [rsp+5E4h] [rbp-2DE4h]
  int v687; // [rsp+5E8h] [rbp-2DE0h]
  __int16 v688; // [rsp+5ECh] [rbp-2DDCh]
  __int16 v689; // [rsp+5EEh] [rbp-2DDAh]
  int v690; // [rsp+5F0h] [rbp-2DD8h] BYREF
  __int16 v691; // [rsp+5F4h] [rbp-2DD4h]
  __int16 v692; // [rsp+5F6h] [rbp-2DD2h]
  int v693; // [rsp+5F8h] [rbp-2DD0h] BYREF
  __int16 v694; // [rsp+5FCh] [rbp-2DCCh]
  __int16 v695; // [rsp+5FEh] [rbp-2DCAh]
  int v696; // [rsp+600h] [rbp-2DC8h]
  __int16 v697; // [rsp+604h] [rbp-2DC4h]
  __int16 v698; // [rsp+606h] [rbp-2DC2h]
  int v699; // [rsp+608h] [rbp-2DC0h] BYREF
  __int16 v700; // [rsp+60Ch] [rbp-2DBCh]
  __int16 v701; // [rsp+60Eh] [rbp-2DBAh]
  int v702; // [rsp+610h] [rbp-2DB8h]
  __int16 v703; // [rsp+614h] [rbp-2DB4h]
  __int16 v704; // [rsp+616h] [rbp-2DB2h]
  int v705; // [rsp+618h] [rbp-2DB0h] BYREF
  __int16 v706; // [rsp+61Ch] [rbp-2DACh]
  __int16 v707; // [rsp+61Eh] [rbp-2DAAh]
  int v708; // [rsp+620h] [rbp-2DA8h] BYREF
  __int16 v709; // [rsp+624h] [rbp-2DA4h]
  __int16 v710; // [rsp+626h] [rbp-2DA2h]
  int v711; // [rsp+628h] [rbp-2DA0h] BYREF
  __int16 v712; // [rsp+62Ch] [rbp-2D9Ch]
  __int16 v713; // [rsp+62Eh] [rbp-2D9Ah]
  int v714; // [rsp+630h] [rbp-2D98h]
  int v715; // [rsp+634h] [rbp-2D94h]
  __int16 v716; // [rsp+638h] [rbp-2D90h]
  int v717; // [rsp+640h] [rbp-2D88h]
  int v718; // [rsp+644h] [rbp-2D84h]
  __int16 v719; // [rsp+648h] [rbp-2D80h]
  int v720; // [rsp+650h] [rbp-2D78h]
  int v721; // [rsp+654h] [rbp-2D74h]
  __int16 v722; // [rsp+658h] [rbp-2D70h]
  __int64 v723; // [rsp+660h] [rbp-2D68h]
  __int16 v724; // [rsp+668h] [rbp-2D60h]
  __int16 v725; // [rsp+66Ah] [rbp-2D5Eh]
  __int64 v726; // [rsp+66Ch] [rbp-2D5Ch]
  __int16 v727; // [rsp+674h] [rbp-2D54h]
  __int16 v728; // [rsp+676h] [rbp-2D52h]
  __int64 v729; // [rsp+678h] [rbp-2D50h]
  __int16 v730; // [rsp+680h] [rbp-2D48h]
  __int16 v731; // [rsp+682h] [rbp-2D46h]
  unsigned int v732; // [rsp+684h] [rbp-2D44h]
  unsigned int v733; // [rsp+688h] [rbp-2D40h]
  unsigned int v734; // [rsp+68Ch] [rbp-2D3Ch] BYREF
  int v735; // [rsp+690h] [rbp-2D38h] BYREF
  int v736; // [rsp+698h] [rbp-2D30h]
  int v737; // [rsp+6A0h] [rbp-2D28h]
  volatile signed __int32 v738; // [rsp+6A8h] [rbp-2D20h]
  int v739; // [rsp+6B0h] [rbp-2D18h]
  int v740; // [rsp+6B8h] [rbp-2D10h]
  int v741; // [rsp+6C0h] [rbp-2D08h]
  volatile signed __int32 v742; // [rsp+6C8h] [rbp-2D00h]
  int v743; // [rsp+6D0h] [rbp-2CF8h]
  int v744; // [rsp+6D8h] [rbp-2CF0h]
  int v745; // [rsp+6E0h] [rbp-2CE8h]
  volatile signed __int32 v746; // [rsp+6E8h] [rbp-2CE0h]
  int v747; // [rsp+6F0h] [rbp-2CD8h]
  int v748; // [rsp+6F8h] [rbp-2CD0h]
  volatile signed __int32 v749; // [rsp+700h] [rbp-2CC8h]
  int v750; // [rsp+708h] [rbp-2CC0h]
  int v751; // [rsp+710h] [rbp-2CB8h]
  volatile signed __int32 v752; // [rsp+718h] [rbp-2CB0h]
  int v753; // [rsp+720h] [rbp-2CA8h]
  int v754; // [rsp+728h] [rbp-2CA0h]
  volatile signed __int32 v755; // [rsp+730h] [rbp-2C98h]
  int v756; // [rsp+738h] [rbp-2C90h]
  int v757; // [rsp+740h] [rbp-2C88h]
  volatile signed __int32 v758; // [rsp+748h] [rbp-2C80h]
  int v759; // [rsp+750h] [rbp-2C78h]
  int v760; // [rsp+758h] [rbp-2C70h]
  volatile signed __int32 v761; // [rsp+760h] [rbp-2C68h]
  int v762; // [rsp+768h] [rbp-2C60h]
  int v763; // [rsp+770h] [rbp-2C58h]
  volatile signed __int32 v764; // [rsp+778h] [rbp-2C50h]
  __int16 v765; // [rsp+780h] [rbp-2C48h]
  __int16 v766; // [rsp+788h] [rbp-2C40h]
  __int16 v767; // [rsp+790h] [rbp-2C38h]
  __int16 v768; // [rsp+798h] [rbp-2C30h]
  __int16 v769; // [rsp+7A0h] [rbp-2C28h]
  __int16 v770; // [rsp+7A8h] [rbp-2C20h]
  __int16 v771; // [rsp+7ACh] [rbp-2C1Ch]
  __int16 v772; // [rsp+7B0h] [rbp-2C18h]
  __int16 v773; // [rsp+7B8h] [rbp-2C10h]
  __int16 v774; // [rsp+7C0h] [rbp-2C08h]
  __int16 v775; // [rsp+7C8h] [rbp-2C00h]
  __int16 v776; // [rsp+7CCh] [rbp-2BFCh]
  __int16 v777; // [rsp+7D0h] [rbp-2BF8h]
  int v778; // [rsp+7E0h] [rbp-2BE8h]
  __int16 v779; // [rsp+7E4h] [rbp-2BE4h]
  int v780; // [rsp+7E8h] [rbp-2BE0h]
  __int16 v781; // [rsp+7ECh] [rbp-2BDCh]
  int v782; // [rsp+7F0h] [rbp-2BD8h] BYREF
  __int16 v783; // [rsp+7F4h] [rbp-2BD4h]
  int v784; // [rsp+830h] [rbp-2B98h]
  int v785; // [rsp+838h] [rbp-2B90h]
  volatile signed __int32 v786; // [rsp+840h] [rbp-2B88h]
  int v787; // [rsp+848h] [rbp-2B80h]
  int v788; // [rsp+850h] [rbp-2B78h]
  int v789; // [rsp+858h] [rbp-2B70h]
  volatile signed __int32 v790; // [rsp+860h] [rbp-2B68h]
  int v791; // [rsp+868h] [rbp-2B60h]
  int v792; // [rsp+870h] [rbp-2B58h]
  volatile signed __int32 v793; // [rsp+878h] [rbp-2B50h]
  unsigned int v794; // [rsp+880h] [rbp-2B48h]
  unsigned int v795; // [rsp+884h] [rbp-2B44h]
  unsigned int v796; // [rsp+888h] [rbp-2B40h] BYREF
  int v797; // [rsp+88Ch] [rbp-2B3Ch] BYREF
  int v798; // [rsp+890h] [rbp-2B38h]
  int v799; // [rsp+898h] [rbp-2B30h]
  volatile signed __int32 v800; // [rsp+8A0h] [rbp-2B28h]
  int v801; // [rsp+8A8h] [rbp-2B20h]
  int v802; // [rsp+8B0h] [rbp-2B18h]
  int v803; // [rsp+8B8h] [rbp-2B10h]
  volatile signed __int32 v804; // [rsp+8C0h] [rbp-2B08h]
  int v805; // [rsp+8C8h] [rbp-2B00h]
  int v806; // [rsp+8D0h] [rbp-2AF8h]
  int v807; // [rsp+8D8h] [rbp-2AF0h]
  volatile signed __int32 v808; // [rsp+8E0h] [rbp-2AE8h]
  int v809; // [rsp+8E8h] [rbp-2AE0h]
  int v810; // [rsp+8F0h] [rbp-2AD8h]
  int v811; // [rsp+8F8h] [rbp-2AD0h]
  volatile signed __int32 v812; // [rsp+900h] [rbp-2AC8h]
  _DWORD *v813; // [rsp+908h] [rbp-2AC0h]
  _DWORD *v814; // [rsp+910h] [rbp-2AB8h]
  _QWORD *v815; // [rsp+918h] [rbp-2AB0h]
  _QWORD *v816; // [rsp+920h] [rbp-2AA8h]
  _QWORD *v817; // [rsp+928h] [rbp-2AA0h]
  _QWORD *v818; // [rsp+930h] [rbp-2A98h]
  _DWORD *v819; // [rsp+938h] [rbp-2A90h]
  _QWORD *v820; // [rsp+940h] [rbp-2A88h]
  struct PageComprInfo *v821; // [rsp+948h] [rbp-2A80h]
  struct PageComprInfo *v822; // [rsp+950h] [rbp-2A78h]
  struct PageRef *v823; // [rsp+958h] [rbp-2A70h]
  _QWORD *v824; // [rsp+960h] [rbp-2A68h]
  int v825; // [rsp+970h] [rbp-2A58h]
  int v826; // [rsp+978h] [rbp-2A50h]
  volatile signed __int32 v827; // [rsp+980h] [rbp-2A48h]
  unsigned int v828; // [rsp+988h] [rbp-2A40h]
  unsigned int v829; // [rsp+98Ch] [rbp-2A3Ch]
  unsigned int v830; // [rsp+990h] [rbp-2A38h] BYREF
  int v831; // [rsp+994h] [rbp-2A34h] BYREF
  int v832; // [rsp+998h] [rbp-2A30h]
  int v833; // [rsp+9A0h] [rbp-2A28h]
  volatile signed __int32 v834; // [rsp+9A8h] [rbp-2A20h]
  BOOL v835; // [rsp+9B0h] [rbp-2A18h]
  int v836; // [rsp+9B8h] [rbp-2A10h]
  int v837; // [rsp+9C0h] [rbp-2A08h]
  volatile signed __int32 v838; // [rsp+9C8h] [rbp-2A00h]
  int v839; // [rsp+9D0h] [rbp-29F8h]
  int v840; // [rsp+9D8h] [rbp-29F0h]
  int v841; // [rsp+9E0h] [rbp-29E8h]
  volatile signed __int32 v842; // [rsp+9E8h] [rbp-29E0h]
  int v843; // [rsp+9F0h] [rbp-29D8h]
  int v844; // [rsp+9F8h] [rbp-29D0h]
  int v845; // [rsp+A00h] [rbp-29C8h]
  volatile signed __int32 v846; // [rsp+A08h] [rbp-29C0h]
  int v847; // [rsp+A10h] [rbp-29B8h]
  int v848; // [rsp+A18h] [rbp-29B0h]
  volatile signed __int32 v849; // [rsp+A20h] [rbp-29A8h]
  __int64 v850; // [rsp+A28h] [rbp-29A0h] BYREF
  __int16 v851; // [rsp+A30h] [rbp-2998h]
  __int64 v852; // [rsp+A38h] [rbp-2990h] BYREF
  __int16 v853; // [rsp+A40h] [rbp-2988h]
  __int64 v854; // [rsp+A48h] [rbp-2980h] BYREF
  __int16 v855; // [rsp+A50h] [rbp-2978h]
  __int64 *v856; // [rsp+A58h] [rbp-2970h]
  unsigned int *v857; // [rsp+A60h] [rbp-2968h]
  LSN *v858; // [rsp+A68h] [rbp-2960h]
  unsigned int *v859; // [rsp+A70h] [rbp-2958h]
  LSN *v860; // [rsp+A78h] [rbp-2950h]
  __int64 *v861; // [rsp+A80h] [rbp-2948h]
  unsigned int *v862; // [rsp+A88h] [rbp-2940h]
  LSN *v863; // [rsp+A90h] [rbp-2938h]
  __int64 v864; // [rsp+A98h] [rbp-2930h]
  struct PageRef *v865; // [rsp+AA0h] [rbp-2928h]
  struct PageRef *v866; // [rsp+AA8h] [rbp-2920h]
  __int64 *v867; // [rsp+AB0h] [rbp-2918h]
  int v868; // [rsp+AB8h] [rbp-2910h]
  __int16 v869; // [rsp+ABCh] [rbp-290Ch]
  int v870; // [rsp+ABEh] [rbp-290Ah]
  __int16 v871; // [rsp+AC2h] [rbp-2906h]
  int v872; // [rsp+AC4h] [rbp-2904h]
  __int16 v873; // [rsp+AC8h] [rbp-2900h]
  int v874; // [rsp+ACAh] [rbp-28FEh]
  __int16 v875; // [rsp+ACEh] [rbp-28FAh]
  int v876; // [rsp+AD0h] [rbp-28F8h]
  __int16 v877; // [rsp+AD4h] [rbp-28F4h]
  int v878; // [rsp+AD6h] [rbp-28F2h]
  __int16 v879; // [rsp+ADAh] [rbp-28EEh]
  int v880; // [rsp+ADCh] [rbp-28ECh]
  __int16 v881; // [rsp+AE0h] [rbp-28E8h]
  __int64 v882; // [rsp+AE8h] [rbp-28E0h] BYREF
  __int16 v883; // [rsp+AF0h] [rbp-28D8h]
  int v884; // [rsp+AF8h] [rbp-28D0h]
  int v885; // [rsp+AFCh] [rbp-28CCh]
  __int16 v886; // [rsp+B00h] [rbp-28C8h]
  LSN v887; // [rsp+B08h] [rbp-28C0h] BYREF
  __int16 v888; // [rsp+B10h] [rbp-28B8h]
  __int64 v889; // [rsp+B18h] [rbp-28B0h] BYREF
  __int16 v890; // [rsp+B20h] [rbp-28A8h]
  int v891; // [rsp+B28h] [rbp-28A0h]
  int v892; // [rsp+B2Ch] [rbp-289Ch]
  __int16 v893; // [rsp+B30h] [rbp-2898h]
  int v894; // [rsp+B38h] [rbp-2890h]
  int v895; // [rsp+B3Ch] [rbp-288Ch]
  __int16 v896; // [rsp+B40h] [rbp-2888h]
  LSN v897; // [rsp+B48h] [rbp-2880h] BYREF
  __int16 v898; // [rsp+B50h] [rbp-2878h]
  __int64 v899; // [rsp+B58h] [rbp-2870h] BYREF
  __int16 v900; // [rsp+B60h] [rbp-2868h]
  int v901; // [rsp+B68h] [rbp-2860h]
  int v902; // [rsp+B6Ch] [rbp-285Ch]
  __int16 v903; // [rsp+B70h] [rbp-2858h]
  int v904; // [rsp+B78h] [rbp-2850h]
  int v905; // [rsp+B7Ch] [rbp-284Ch]
  __int16 v906; // [rsp+B80h] [rbp-2848h]
  LSN v907; // [rsp+B88h] [rbp-2840h] BYREF
  __int16 v908; // [rsp+B90h] [rbp-2838h]
  int v909; // [rsp+B98h] [rbp-2830h]
  int v910; // [rsp+B9Ch] [rbp-282Ch]
  __int16 v911; // [rsp+BA0h] [rbp-2828h]
  unsigned int v912; // [rsp+BA8h] [rbp-2820h]
  int v913; // [rsp+BACh] [rbp-281Ch]
  DWORD v914[2]; // [rsp+BB0h] [rbp-2818h] BYREF
  DWORD v915[2]; // [rsp+BB8h] [rbp-2810h] BYREF
  DWORD v916[2]; // [rsp+BC0h] [rbp-2808h] BYREF
  DWORD v917[8]; // [rsp+BC8h] [rbp-2800h] BYREF
  DWORD v918[3]; // [rsp+BE8h] [rbp-27E0h] BYREF
  DWORD v919[2]; // [rsp+BF4h] [rbp-27D4h] BYREF
  DWORD v920[2]; // [rsp+BFCh] [rbp-27CCh] BYREF
  DWORD v921[2]; // [rsp+C04h] [rbp-27C4h] BYREF
  DWORD v922[7]; // [rsp+C0Ch] [rbp-27BCh] BYREF
  DWORD v923[3]; // [rsp+C28h] [rbp-27A0h] BYREF
  DWORD v924[2]; // [rsp+C34h] [rbp-2794h] BYREF
  DWORD v925[7]; // [rsp+C3Ch] [rbp-278Ch] BYREF
  unsigned int v926; // [rsp+C58h] [rbp-2770h]
  int v927; // [rsp+C60h] [rbp-2768h]
  int v928; // [rsp+C68h] [rbp-2760h]
  DWORD v929[2]; // [rsp+C70h] [rbp-2758h] BYREF
  DWORD v930[8]; // [rsp+C78h] [rbp-2750h] BYREF
  unsigned int v931; // [rsp+C98h] [rbp-2730h]
  int v932; // [rsp+CA0h] [rbp-2728h]
  unsigned int v933; // [rsp+CA8h] [rbp-2720h]
  int v934; // [rsp+CB0h] [rbp-2718h]
  DWORD v935[7]; // [rsp+CB4h] [rbp-2714h] BYREF
  _QWORD *v936; // [rsp+CD0h] [rbp-26F8h]
  __int64 v937; // [rsp+CD8h] [rbp-26F0h]
  struct CSessionTraceFlags *v938; // [rsp+CE0h] [rbp-26E8h]
  __int64 v939; // [rsp+CE8h] [rbp-26E0h]
  char *v940; // [rsp+CF0h] [rbp-26D8h]
  int *v941; // [rsp+CF8h] [rbp-26D0h]
  LONG *p_HighPart; // [rsp+D00h] [rbp-26C8h]
  int v943; // [rsp+D08h] [rbp-26C0h]
  int v944; // [rsp+D0Ch] [rbp-26BCh]
  __int64 v945; // [rsp+D10h] [rbp-26B8h]
  __int64 (__fastcall ***v946)(_QWORD); // [rsp+D18h] [rbp-26B0h]
  _QWORD *v947; // [rsp+D20h] [rbp-26A8h]
  __int64 v948; // [rsp+D28h] [rbp-26A0h]
  struct CSessionTraceFlags *v949; // [rsp+D30h] [rbp-2698h]
  __int64 v950; // [rsp+D38h] [rbp-2690h]
  char *v951; // [rsp+D40h] [rbp-2688h]
  int *v952; // [rsp+D48h] [rbp-2680h]
  LONG *v953; // [rsp+D50h] [rbp-2678h]
  int v954; // [rsp+D58h] [rbp-2670h]
  int v955; // [rsp+D5Ch] [rbp-266Ch]
  __int64 v956; // [rsp+D60h] [rbp-2668h]
  __int64 (__fastcall ***v957)(_QWORD); // [rsp+D68h] [rbp-2660h]
  _QWORD *v958; // [rsp+D70h] [rbp-2658h]
  __int64 v959; // [rsp+D78h] [rbp-2650h]
  struct CSessionTraceFlags *v960; // [rsp+D80h] [rbp-2648h]
  __int64 v961; // [rsp+D88h] [rbp-2640h]
  char *v962; // [rsp+D90h] [rbp-2638h]
  int *v963; // [rsp+D98h] [rbp-2630h]
  LONG *v964; // [rsp+DA0h] [rbp-2628h]
  int v965; // [rsp+DA8h] [rbp-2620h]
  int v966; // [rsp+DACh] [rbp-261Ch]
  __int64 v967; // [rsp+DB0h] [rbp-2618h]
  __int64 (__fastcall ***v968)(_QWORD); // [rsp+DB8h] [rbp-2610h]
  int *v969; // [rsp+DC0h] [rbp-2608h]
  BTreeMgr *v970; // [rsp+DC8h] [rbp-2600h]
  struct PageRef *v971; // [rsp+DD0h] [rbp-25F8h]
  struct PageRef *v972; // [rsp+DD8h] [rbp-25F0h]
  int v973; // [rsp+DE0h] [rbp-25E8h]
  DWORD v974[2]; // [rsp+DE4h] [rbp-25E4h] BYREF
  DWORD v975[2]; // [rsp+DECh] [rbp-25DCh] BYREF
  DWORD v976[19]; // [rsp+DF4h] [rbp-25D4h] BYREF
  DWORD flOldProtect[2]; // [rsp+E40h] [rbp-2588h] BYREF
  DWORD v978[2]; // [rsp+E48h] [rbp-2580h] BYREF
  DWORD v979[10]; // [rsp+E50h] [rbp-2578h] BYREF
  DWORD v980[22]; // [rsp+E78h] [rbp-2550h] BYREF
  _BYTE v981[4]; // [rsp+ED0h] [rbp-24F8h] BYREF
  int v982; // [rsp+ED4h] [rbp-24F4h]
  int v983; // [rsp+ED8h] [rbp-24F0h]
  _BYTE v984[4]; // [rsp+EE8h] [rbp-24E0h] BYREF
  int v985; // [rsp+EECh] [rbp-24DCh]
  int v986; // [rsp+EF0h] [rbp-24D8h]
  _BYTE v987[4]; // [rsp+F00h] [rbp-24C8h] BYREF
  int v988; // [rsp+F04h] [rbp-24C4h]
  int v989; // [rsp+F08h] [rbp-24C0h]
  _QWORD v990[7]; // [rsp+F30h] [rbp-2498h] BYREF
  int v991; // [rsp+F68h] [rbp-2460h]
  int v992; // [rsp+F6Ch] [rbp-245Ch]
  _WORD v993[2]; // [rsp+F70h] [rbp-2458h] BYREF
  int v994; // [rsp+F74h] [rbp-2454h]
  __int64 v995; // [rsp+F78h] [rbp-2450h]
  __int64 v996; // [rsp+F80h] [rbp-2448h]
  __int64 v997; // [rsp+F8Eh] [rbp-243Ah]
  __int64 v998; // [rsp+F98h] [rbp-2430h]
  int v999; // [rsp+FA8h] [rbp-2420h] BYREF
  __int64 v1000; // [rsp+FB0h] [rbp-2418h]
  __int64 v1001; // [rsp+FB8h] [rbp-2410h]
  __int64 v1002; // [rsp+FC0h] [rbp-2408h]
  __int64 v1003; // [rsp+FC8h] [rbp-2400h]
  int v1004; // [rsp+FD0h] [rbp-23F8h] BYREF
  __int64 v1005; // [rsp+FD8h] [rbp-23F0h]
  __int64 v1006; // [rsp+FE0h] [rbp-23E8h]
  __int64 v1007; // [rsp+FE8h] [rbp-23E0h]
  __int64 v1008; // [rsp+FF0h] [rbp-23D8h]
  int v1009; // [rsp+FF8h] [rbp-23D0h] BYREF
  __int64 v1010; // [rsp+1000h] [rbp-23C8h]
  __int64 v1011; // [rsp+1008h] [rbp-23C0h]
  __int64 v1012; // [rsp+1010h] [rbp-23B8h]
  __int64 v1013; // [rsp+1018h] [rbp-23B0h]
  int *v1014; // [rsp+1020h] [rbp-23A8h]
  __int64 v1015; // [rsp+1028h] [rbp-23A0h]
  __int64 v1016; // [rsp+1030h] [rbp-2398h]
  _WORD *v1017; // [rsp+1038h] [rbp-2390h]
  int **v1018; // [rsp+1040h] [rbp-2388h]
  GUID **v1019; // [rsp+1048h] [rbp-2380h]
  GUID **v1020; // [rsp+1050h] [rbp-2378h]
  wchar_t **v1021; // [rsp+1058h] [rbp-2370h]
  wchar_t **v1022; // [rsp+1060h] [rbp-2368h]
  __int64 *v1023; // [rsp+1068h] [rbp-2360h]
  __int64 v1024; // [rsp+1070h] [rbp-2358h]
  GUID **v1025; // [rsp+1078h] [rbp-2350h]
  GUID **v1026; // [rsp+1080h] [rbp-2348h]
  wchar_t *v1027; // [rsp+1088h] [rbp-2340h]
  wchar_t **v1028; // [rsp+1090h] [rbp-2338h]
  wchar_t *v1029; // [rsp+1098h] [rbp-2330h]
  wchar_t **v1030; // [rsp+10A0h] [rbp-2328h]
  __int64 v1031; // [rsp+10A8h] [rbp-2320h]
  _DWORD **v1032; // [rsp+10B0h] [rbp-2318h]
  _QWORD *v1033; // [rsp+10B8h] [rbp-2310h]
  __int64 v1034; // [rsp+10C0h] [rbp-2308h]
  __int64 v1035; // [rsp+10C8h] [rbp-2300h]
  __int64 v1036; // [rsp+10D0h] [rbp-22F8h]
  __int64 *v1037; // [rsp+10D8h] [rbp-22F0h]
  __int64 v1038; // [rsp+10E0h] [rbp-22E8h]
  int *v1039; // [rsp+10E8h] [rbp-22E0h]
  __int64 v1040; // [rsp+10F0h] [rbp-22D8h]
  __int64 *v1041; // [rsp+10F8h] [rbp-22D0h]
  __int64 v1042; // [rsp+1100h] [rbp-22C8h]
  __int64 v1043; // [rsp+1108h] [rbp-22C0h]
  __int64 v1044; // [rsp+1110h] [rbp-22B8h]
  __int64 v1045; // [rsp+1118h] [rbp-22B0h]
  __int64 v1046; // [rsp+1120h] [rbp-22A8h]
  __int64 v1047; // [rsp+1128h] [rbp-22A0h]
  __int64 *v1048; // [rsp+1130h] [rbp-2298h]
  __int64 *v1049; // [rsp+1138h] [rbp-2290h]
  __int64 v1050; // [rsp+1140h] [rbp-2288h]
  __int64 v1051; // [rsp+1148h] [rbp-2280h]
  __int64 v1052; // [rsp+1150h] [rbp-2278h]
  __int64 v1053; // [rsp+1158h] [rbp-2270h]
  __int64 v1054; // [rsp+1160h] [rbp-2268h]
  __int64 v1055; // [rsp+1168h] [rbp-2260h]
  __int64 v1056; // [rsp+1170h] [rbp-2258h]
  __int64 v1057; // [rsp+1178h] [rbp-2250h]
  __int64 v1058; // [rsp+1180h] [rbp-2248h]
  __int64 v1059; // [rsp+1188h] [rbp-2240h]
  __int64 v1060; // [rsp+1190h] [rbp-2238h]
  __int64 v1061; // [rsp+1198h] [rbp-2230h]
  __int64 v1062; // [rsp+11A0h] [rbp-2228h]
  __int64 v1063; // [rsp+11A8h] [rbp-2220h]
  __int64 v1064; // [rsp+11B0h] [rbp-2218h]
  __int64 v1065; // [rsp+11B8h] [rbp-2210h]
  __int64 v1066; // [rsp+11C0h] [rbp-2208h]
  __int64 v1067; // [rsp+11C8h] [rbp-2200h]
  __int64 v1068; // [rsp+11D0h] [rbp-21F8h]
  int *v1069; // [rsp+11D8h] [rbp-21F0h]
  int *v1070; // [rsp+11E0h] [rbp-21E8h]
  __int64 v1071; // [rsp+11E8h] [rbp-21E0h]
  __int64 v1072; // [rsp+11F0h] [rbp-21D8h]
  unsigned __int64 v1073; // [rsp+11F8h] [rbp-21D0h]
  _QWORD *v1074; // [rsp+1200h] [rbp-21C8h]
  __int64 v1075; // [rsp+1208h] [rbp-21C0h]
  _QWORD *v1076; // [rsp+1210h] [rbp-21B8h]
  unsigned __int64 v1077; // [rsp+1218h] [rbp-21B0h]
  __int64 v1078; // [rsp+1220h] [rbp-21A8h]
  __int64 v1079; // [rsp+1228h] [rbp-21A0h]
  _QWORD *v1080; // [rsp+1230h] [rbp-2198h]
  __int64 *v1081; // [rsp+1238h] [rbp-2190h]
  __int64 v1082; // [rsp+1240h] [rbp-2188h]
  struct CSessionTraceFlags *v1083; // [rsp+1248h] [rbp-2180h]
  _QWORD *v1084; // [rsp+1250h] [rbp-2178h]
  __int64 v1085; // [rsp+1258h] [rbp-2170h]
  __int64 v1086; // [rsp+1260h] [rbp-2168h]
  __int64 v1087; // [rsp+1268h] [rbp-2160h]
  __int64 v1088; // [rsp+1270h] [rbp-2158h]
  __int64 v1089; // [rsp+1278h] [rbp-2150h]
  __int64 v1090; // [rsp+1280h] [rbp-2148h]
  __int64 v1091; // [rsp+1288h] [rbp-2140h]
  __int64 v1092; // [rsp+1290h] [rbp-2138h]
  __int64 v1093; // [rsp+1298h] [rbp-2130h]
  __int64 v1094; // [rsp+12A0h] [rbp-2128h]
  __int64 v1095; // [rsp+12A8h] [rbp-2120h]
  __int64 v1096; // [rsp+12B0h] [rbp-2118h]
  __int64 v1097; // [rsp+12B8h] [rbp-2110h]
  __int64 v1098; // [rsp+12C0h] [rbp-2108h]
  __int64 v1099; // [rsp+12C8h] [rbp-2100h]
  _DWORD *v1100; // [rsp+12D0h] [rbp-20F8h]
  _QWORD *v1101; // [rsp+12D8h] [rbp-20F0h]
  __int64 v1102; // [rsp+12E0h] [rbp-20E8h]
  __int64 v1103; // [rsp+12E8h] [rbp-20E0h]
  int *v1104; // [rsp+12F0h] [rbp-20D8h]
  __int64 v1105; // [rsp+12F8h] [rbp-20D0h]
  __int64 *v1106; // [rsp+1300h] [rbp-20C8h]
  _DWORD *v1107; // [rsp+1308h] [rbp-20C0h]
  _QWORD *v1108; // [rsp+1310h] [rbp-20B8h]
  __int64 v1109; // [rsp+1318h] [rbp-20B0h]
  __int64 v1110; // [rsp+1320h] [rbp-20A8h]
  __int64 v1111; // [rsp+1328h] [rbp-20A0h]
  _DWORD *v1112; // [rsp+1330h] [rbp-2098h]
  __int64 v1113; // [rsp+1338h] [rbp-2090h]
  int *v1114; // [rsp+1340h] [rbp-2088h]
  __int64 v1115; // [rsp+1348h] [rbp-2080h]
  __int64 v1116; // [rsp+1350h] [rbp-2078h]
  _WORD *v1117; // [rsp+1358h] [rbp-2070h]
  int **v1118; // [rsp+1360h] [rbp-2068h]
  GUID **v1119; // [rsp+1368h] [rbp-2060h]
  GUID **v1120; // [rsp+1370h] [rbp-2058h]
  wchar_t **v1121; // [rsp+1378h] [rbp-2050h]
  wchar_t **v1122; // [rsp+1380h] [rbp-2048h]
  __int64 *v1123; // [rsp+1388h] [rbp-2040h]
  __int64 v1124; // [rsp+1390h] [rbp-2038h]
  GUID **v1125; // [rsp+1398h] [rbp-2030h]
  GUID **v1126; // [rsp+13A0h] [rbp-2028h]
  wchar_t *v1127; // [rsp+13A8h] [rbp-2020h]
  wchar_t **v1128; // [rsp+13B0h] [rbp-2018h]
  wchar_t *v1129; // [rsp+13B8h] [rbp-2010h]
  wchar_t **v1130; // [rsp+13C0h] [rbp-2008h]
  __int64 v1131; // [rsp+13C8h] [rbp-2000h]
  _DWORD **v1132; // [rsp+13D0h] [rbp-1FF8h]
  _QWORD *v1133; // [rsp+13D8h] [rbp-1FF0h]
  __int64 v1134; // [rsp+13E0h] [rbp-1FE8h]
  __int64 v1135; // [rsp+13E8h] [rbp-1FE0h]
  __int64 v1136; // [rsp+13F0h] [rbp-1FD8h]
  __int64 *v1137; // [rsp+13F8h] [rbp-1FD0h]
  __int64 v1138; // [rsp+1400h] [rbp-1FC8h]
  int *v1139; // [rsp+1408h] [rbp-1FC0h]
  __int64 v1140; // [rsp+1410h] [rbp-1FB8h]
  __int64 *v1141; // [rsp+1418h] [rbp-1FB0h]
  __int64 v1142; // [rsp+1420h] [rbp-1FA8h]
  __int64 v1143; // [rsp+1428h] [rbp-1FA0h]
  __int64 v1144; // [rsp+1430h] [rbp-1F98h]
  __int64 v1145; // [rsp+1438h] [rbp-1F90h]
  __int64 v1146; // [rsp+1440h] [rbp-1F88h]
  __int64 v1147; // [rsp+1448h] [rbp-1F80h]
  __int64 *v1148; // [rsp+1450h] [rbp-1F78h]
  __int64 *v1149; // [rsp+1458h] [rbp-1F70h]
  __int64 v1150; // [rsp+1460h] [rbp-1F68h]
  __int64 v1151; // [rsp+1468h] [rbp-1F60h]
  __int64 v1152; // [rsp+1470h] [rbp-1F58h]
  __int64 v1153; // [rsp+1478h] [rbp-1F50h]
  __int64 v1154; // [rsp+1480h] [rbp-1F48h]
  __int64 v1155; // [rsp+1488h] [rbp-1F40h]
  __int64 v1156; // [rsp+1490h] [rbp-1F38h]
  __int64 v1157; // [rsp+1498h] [rbp-1F30h]
  __int64 v1158; // [rsp+14A0h] [rbp-1F28h]
  __int64 v1159; // [rsp+14A8h] [rbp-1F20h]
  __int64 v1160; // [rsp+14B0h] [rbp-1F18h]
  __int64 v1161; // [rsp+14B8h] [rbp-1F10h]
  __int64 v1162; // [rsp+14C0h] [rbp-1F08h]
  __int64 v1163; // [rsp+14C8h] [rbp-1F00h]
  __int64 v1164; // [rsp+14D0h] [rbp-1EF8h]
  __int64 v1165; // [rsp+14D8h] [rbp-1EF0h]
  __int64 v1166; // [rsp+14E0h] [rbp-1EE8h]
  __int64 v1167; // [rsp+14E8h] [rbp-1EE0h]
  __int64 v1168; // [rsp+14F0h] [rbp-1ED8h]
  int *v1169; // [rsp+14F8h] [rbp-1ED0h]
  int *v1170; // [rsp+1500h] [rbp-1EC8h]
  __int64 v1171; // [rsp+1508h] [rbp-1EC0h]
  __int64 v1172; // [rsp+1510h] [rbp-1EB8h]
  __int64 v1173; // [rsp+1518h] [rbp-1EB0h]
  __int64 v1174; // [rsp+1520h] [rbp-1EA8h]
  __int64 v1175; // [rsp+1528h] [rbp-1EA0h]
  __int64 v1176; // [rsp+1530h] [rbp-1E98h]
  __int64 v1177; // [rsp+1538h] [rbp-1E90h]
  unsigned __int64 v1178; // [rsp+1540h] [rbp-1E88h]
  _QWORD *v1179; // [rsp+1548h] [rbp-1E80h]
  __int64 v1180; // [rsp+1550h] [rbp-1E78h]
  _QWORD *v1181; // [rsp+1558h] [rbp-1E70h]
  unsigned __int64 v1182; // [rsp+1560h] [rbp-1E68h]
  __int64 v1183; // [rsp+1568h] [rbp-1E60h]
  __int64 v1184; // [rsp+1570h] [rbp-1E58h]
  _QWORD *v1185; // [rsp+1578h] [rbp-1E50h]
  __int64 *v1186; // [rsp+1580h] [rbp-1E48h]
  __int64 v1187; // [rsp+1588h] [rbp-1E40h]
  struct CSessionTraceFlags *v1188; // [rsp+1590h] [rbp-1E38h]
  _QWORD *v1189; // [rsp+1598h] [rbp-1E30h]
  __int64 v1190; // [rsp+15A0h] [rbp-1E28h]
  __int64 v1191; // [rsp+15A8h] [rbp-1E20h]
  __int64 v1192; // [rsp+15B0h] [rbp-1E18h]
  __int64 v1193; // [rsp+15B8h] [rbp-1E10h]
  __int64 v1194; // [rsp+15C0h] [rbp-1E08h]
  __int64 v1195; // [rsp+15C8h] [rbp-1E00h]
  __int64 v1196; // [rsp+15D0h] [rbp-1DF8h]
  __int64 v1197; // [rsp+15D8h] [rbp-1DF0h]
  __int64 v1198; // [rsp+15E0h] [rbp-1DE8h]
  __int64 v1199; // [rsp+15E8h] [rbp-1DE0h]
  __int64 v1200; // [rsp+15F0h] [rbp-1DD8h]
  __int64 v1201; // [rsp+15F8h] [rbp-1DD0h]
  __int64 v1202; // [rsp+1600h] [rbp-1DC8h]
  __int64 v1203; // [rsp+1608h] [rbp-1DC0h]
  __int64 v1204; // [rsp+1610h] [rbp-1DB8h]
  _DWORD *v1205; // [rsp+1618h] [rbp-1DB0h]
  _QWORD *v1206; // [rsp+1620h] [rbp-1DA8h]
  __int64 v1207; // [rsp+1628h] [rbp-1DA0h]
  __int64 v1208; // [rsp+1630h] [rbp-1D98h]
  int *v1209; // [rsp+1638h] [rbp-1D90h]
  __int64 v1210; // [rsp+1640h] [rbp-1D88h]
  __int64 *v1211; // [rsp+1648h] [rbp-1D80h]
  _DWORD *v1212; // [rsp+1650h] [rbp-1D78h]
  _QWORD *v1213; // [rsp+1658h] [rbp-1D70h]
  __int64 v1214; // [rsp+1660h] [rbp-1D68h]
  __int64 v1215; // [rsp+1668h] [rbp-1D60h]
  __int64 v1216; // [rsp+1670h] [rbp-1D58h]
  _DWORD *v1217; // [rsp+1678h] [rbp-1D50h]
  __int64 v1218; // [rsp+1680h] [rbp-1D48h]
  int *v1219; // [rsp+1688h] [rbp-1D40h]
  __int64 v1220; // [rsp+1690h] [rbp-1D38h]
  __int64 v1221; // [rsp+1698h] [rbp-1D30h]
  _WORD *v1222; // [rsp+16A0h] [rbp-1D28h]
  int **v1223; // [rsp+16A8h] [rbp-1D20h]
  GUID **v1224; // [rsp+16B0h] [rbp-1D18h]
  GUID **v1225; // [rsp+16B8h] [rbp-1D10h]
  wchar_t **v1226; // [rsp+16C0h] [rbp-1D08h]
  wchar_t **v1227; // [rsp+16C8h] [rbp-1D00h]
  __int64 *v1228; // [rsp+16D0h] [rbp-1CF8h]
  __int64 v1229; // [rsp+16D8h] [rbp-1CF0h]
  GUID **v1230; // [rsp+16E0h] [rbp-1CE8h]
  GUID **v1231; // [rsp+16E8h] [rbp-1CE0h]
  wchar_t *v1232; // [rsp+16F0h] [rbp-1CD8h]
  wchar_t **v1233; // [rsp+16F8h] [rbp-1CD0h]
  wchar_t *v1234; // [rsp+1700h] [rbp-1CC8h]
  wchar_t **v1235; // [rsp+1708h] [rbp-1CC0h]
  __int64 v1236; // [rsp+1710h] [rbp-1CB8h]
  _DWORD **v1237; // [rsp+1718h] [rbp-1CB0h]
  _QWORD *v1238; // [rsp+1720h] [rbp-1CA8h]
  __int64 v1239; // [rsp+1728h] [rbp-1CA0h]
  __int64 v1240; // [rsp+1730h] [rbp-1C98h]
  __int64 v1241; // [rsp+1738h] [rbp-1C90h]
  __int64 *v1242; // [rsp+1740h] [rbp-1C88h]
  __int64 v1243; // [rsp+1748h] [rbp-1C80h]
  int *v1244; // [rsp+1750h] [rbp-1C78h]
  __int64 v1245; // [rsp+1758h] [rbp-1C70h]
  __int64 *v1246; // [rsp+1760h] [rbp-1C68h]
  __int64 v1247; // [rsp+1768h] [rbp-1C60h]
  __int64 v1248; // [rsp+1770h] [rbp-1C58h]
  __int64 v1249; // [rsp+1778h] [rbp-1C50h]
  __int64 v1250; // [rsp+1780h] [rbp-1C48h]
  __int64 v1251; // [rsp+1788h] [rbp-1C40h]
  __int64 v1252; // [rsp+1790h] [rbp-1C38h]
  __int64 *v1253; // [rsp+1798h] [rbp-1C30h]
  __int64 *v1254; // [rsp+17A0h] [rbp-1C28h]
  __int64 v1255; // [rsp+17A8h] [rbp-1C20h]
  __int64 v1256; // [rsp+17B0h] [rbp-1C18h]
  __int64 v1257; // [rsp+17B8h] [rbp-1C10h]
  __int64 v1258; // [rsp+17C0h] [rbp-1C08h]
  __int64 v1259; // [rsp+17C8h] [rbp-1C00h]
  __int64 v1260; // [rsp+17D0h] [rbp-1BF8h]
  __int64 v1261; // [rsp+17D8h] [rbp-1BF0h]
  __int64 v1262; // [rsp+17E0h] [rbp-1BE8h]
  __int64 v1263; // [rsp+17E8h] [rbp-1BE0h]
  __int64 v1264; // [rsp+17F0h] [rbp-1BD8h]
  __int64 v1265; // [rsp+17F8h] [rbp-1BD0h]
  __int64 v1266; // [rsp+1800h] [rbp-1BC8h]
  __int64 v1267; // [rsp+1808h] [rbp-1BC0h]
  __int64 v1268; // [rsp+1810h] [rbp-1BB8h]
  __int64 v1269; // [rsp+1818h] [rbp-1BB0h]
  __int64 v1270; // [rsp+1820h] [rbp-1BA8h]
  __int64 v1271; // [rsp+1828h] [rbp-1BA0h]
  __int64 v1272; // [rsp+1830h] [rbp-1B98h]
  __int64 v1273; // [rsp+1838h] [rbp-1B90h]
  int *v1274; // [rsp+1840h] [rbp-1B88h]
  int *v1275; // [rsp+1848h] [rbp-1B80h]
  __int64 v1276; // [rsp+1850h] [rbp-1B78h]
  __int64 v1277; // [rsp+1858h] [rbp-1B70h]
  __int128 *v1278; // [rsp+1860h] [rbp-1B68h]
  __int128 *v1279; // [rsp+1868h] [rbp-1B60h]
  __int128 *v1280; // [rsp+1870h] [rbp-1B58h]
  char *v1281; // [rsp+1878h] [rbp-1B50h]
  __int128 *v1282; // [rsp+1880h] [rbp-1B48h]
  char *v1283; // [rsp+1888h] [rbp-1B40h]
  int *v1284; // [rsp+1890h] [rbp-1B38h]
  __int64 v1285; // [rsp+1898h] [rbp-1B30h]
  __int64 *v1286; // [rsp+18A0h] [rbp-1B28h]
  __int64 v1287; // [rsp+18A8h] [rbp-1B20h]
  __int64 v1288; // [rsp+18B0h] [rbp-1B18h]
  struct PageComprInfo *v1289; // [rsp+18B8h] [rbp-1B10h]
  char *v1290; // [rsp+18C0h] [rbp-1B08h]
  char *v1291; // [rsp+18C8h] [rbp-1B00h]
  char *v1292; // [rsp+18D0h] [rbp-1AF8h]
  char *v1293; // [rsp+18D8h] [rbp-1AF0h]
  __int64 v1294; // [rsp+18E0h] [rbp-1AE8h]
  char *v1295; // [rsp+18E8h] [rbp-1AE0h]
  char *v1296; // [rsp+18F0h] [rbp-1AD8h]
  unsigned __int8 *v1297; // [rsp+18F8h] [rbp-1AD0h]
  char *v1298; // [rsp+1900h] [rbp-1AC8h]
  char *v1299; // [rsp+1908h] [rbp-1AC0h]
  __int64 v1300; // [rsp+1910h] [rbp-1AB8h]
  char *v1301; // [rsp+1918h] [rbp-1AB0h]
  unsigned __int8 *v1302; // [rsp+1940h] [rbp-1A88h]
  char *v1303; // [rsp+1948h] [rbp-1A80h]
  char *v1304; // [rsp+1950h] [rbp-1A78h]
  __int16 *v1305; // [rsp+1958h] [rbp-1A70h]
  char *v1306; // [rsp+1960h] [rbp-1A68h]
  __int16 *v1307; // [rsp+1968h] [rbp-1A60h]
  char *v1308; // [rsp+1970h] [rbp-1A58h]
  char *v1309; // [rsp+1978h] [rbp-1A50h]
  char *v1310; // [rsp+1980h] [rbp-1A48h]
  char *v1311; // [rsp+1988h] [rbp-1A40h]
  struct RecoveryUnit **v1312; // [rsp+1990h] [rbp-1A38h]
  __int64 v1313; // [rsp+1998h] [rbp-1A30h]
  __int64 v1314; // [rsp+19A0h] [rbp-1A28h]
  __int64 v1315; // [rsp+19A8h] [rbp-1A20h]
  __int64 v1316; // [rsp+19B0h] [rbp-1A18h]
  __int64 v1317; // [rsp+19B8h] [rbp-1A10h]
  struct Page *v1318; // [rsp+19C0h] [rbp-1A08h]
  __int64 v1319; // [rsp+19C8h] [rbp-1A00h]
  __int64 v1320; // [rsp+19D0h] [rbp-19F8h]
  char *v1321; // [rsp+19D8h] [rbp-19F0h]
  struct Page **v1322; // [rsp+19E0h] [rbp-19E8h]
  char *v1323; // [rsp+19E8h] [rbp-19E0h]
  char *v1324; // [rsp+19F0h] [rbp-19D8h]
  struct Page *v1325; // [rsp+19F8h] [rbp-19D0h]
  char *v1326; // [rsp+1A00h] [rbp-19C8h]
  char *v1327; // [rsp+1A08h] [rbp-19C0h]
  __int64 v1328; // [rsp+1A10h] [rbp-19B8h]
  __int64 v1329; // [rsp+1A18h] [rbp-19B0h]
  __int128 *v1330; // [rsp+1A20h] [rbp-19A8h]
  __int128 *v1331; // [rsp+1A28h] [rbp-19A0h]
  __int128 *v1332; // [rsp+1A30h] [rbp-1998h]
  char *v1333; // [rsp+1A38h] [rbp-1990h]
  __int128 *v1334; // [rsp+1A40h] [rbp-1988h]
  char *v1335; // [rsp+1A48h] [rbp-1980h]
  int *v1336; // [rsp+1A50h] [rbp-1978h]
  __int64 v1337; // [rsp+1A58h] [rbp-1970h]
  __int64 *v1338; // [rsp+1A60h] [rbp-1968h]
  __int64 v1339; // [rsp+1A68h] [rbp-1960h]
  __int64 v1340; // [rsp+1A70h] [rbp-1958h]
  struct PageComprInfo *v1341; // [rsp+1A78h] [rbp-1950h]
  char *v1342; // [rsp+1A80h] [rbp-1948h]
  char *v1343; // [rsp+1A88h] [rbp-1940h]
  char *v1344; // [rsp+1A90h] [rbp-1938h]
  char *v1345; // [rsp+1A98h] [rbp-1930h]
  __int64 v1346; // [rsp+1AA0h] [rbp-1928h]
  char *v1347; // [rsp+1AA8h] [rbp-1920h]
  char *v1348; // [rsp+1AB0h] [rbp-1918h]
  unsigned __int8 *v1349; // [rsp+1AB8h] [rbp-1910h]
  char *v1350; // [rsp+1AC0h] [rbp-1908h]
  char *v1351; // [rsp+1AC8h] [rbp-1900h]
  _BYTE *v1352; // [rsp+1AD0h] [rbp-18F8h]
  char *v1353; // [rsp+1AD8h] [rbp-18F0h]
  unsigned __int8 *v1354; // [rsp+1AE0h] [rbp-18E8h]
  unsigned __int8 *v1355; // [rsp+1AE8h] [rbp-18E0h]
  unsigned __int8 *v1356; // [rsp+1AF0h] [rbp-18D8h]
  unsigned __int8 *v1357; // [rsp+1AF8h] [rbp-18D0h]
  unsigned __int8 *v1358; // [rsp+1B00h] [rbp-18C8h]
  char *v1359; // [rsp+1B08h] [rbp-18C0h]
  char *v1360; // [rsp+1B10h] [rbp-18B8h]
  __int16 *v1361; // [rsp+1B18h] [rbp-18B0h]
  char *v1362; // [rsp+1B20h] [rbp-18A8h]
  __int16 *v1363; // [rsp+1B28h] [rbp-18A0h]
  char *v1364; // [rsp+1B30h] [rbp-1898h]
  char *v1365; // [rsp+1B38h] [rbp-1890h]
  char *v1366; // [rsp+1B40h] [rbp-1888h]
  char *v1367; // [rsp+1B48h] [rbp-1880h]
  struct RecoveryUnit **v1368; // [rsp+1B50h] [rbp-1878h]
  __int64 v1369; // [rsp+1B58h] [rbp-1870h]
  struct Page *v1370; // [rsp+1B60h] [rbp-1868h]
  __int64 v1371; // [rsp+1B68h] [rbp-1860h]
  struct RecoveryUnit **v1372; // [rsp+1B70h] [rbp-1858h]
  char *v1373; // [rsp+1B78h] [rbp-1850h]
  struct Page **v1374; // [rsp+1B80h] [rbp-1848h]
  char *v1375; // [rsp+1B88h] [rbp-1840h]
  char *v1376; // [rsp+1B90h] [rbp-1838h]
  struct Page *v1377; // [rsp+1B98h] [rbp-1830h]
  char *v1378; // [rsp+1BA0h] [rbp-1828h]
  char *v1379; // [rsp+1BA8h] [rbp-1820h]
  __int64 v1380; // [rsp+1BB0h] [rbp-1818h]
  __int64 v1381; // [rsp+1BB8h] [rbp-1810h]
  __int64 v1382; // [rsp+1BC0h] [rbp-1808h]
  struct Page *v1383; // [rsp+1BC8h] [rbp-1800h]
  __int64 v1384; // [rsp+1BD0h] [rbp-17F8h]
  __int64 v1385; // [rsp+1BD8h] [rbp-17F0h]
  __int64 v1386; // [rsp+1BE0h] [rbp-17E8h]
  __int64 v1387; // [rsp+1BE8h] [rbp-17E0h]
  __int64 v1388; // [rsp+1BF0h] [rbp-17D8h]
  __int64 v1389; // [rsp+1BF8h] [rbp-17D0h]
  __int64 v1390; // [rsp+1C00h] [rbp-17C8h]
  __int64 v1391; // [rsp+1C08h] [rbp-17C0h]
  __int64 v1392; // [rsp+1C10h] [rbp-17B8h]
  __int64 v1393; // [rsp+1C18h] [rbp-17B0h]
  __int64 v1394; // [rsp+1C20h] [rbp-17A8h]
  struct Page *v1395; // [rsp+1C28h] [rbp-17A0h]
  __int64 v1396; // [rsp+1C30h] [rbp-1798h]
  __int64 v1397; // [rsp+1C38h] [rbp-1790h]
  __int64 v1398; // [rsp+1D08h] [rbp-16C0h]
  __int64 v1399; // [rsp+1D10h] [rbp-16B8h]
  __int64 v1400; // [rsp+1D18h] [rbp-16B0h]
  __int64 v1401; // [rsp+1D20h] [rbp-16A8h]
  __int64 v1402; // [rsp+1D28h] [rbp-16A0h]
  __int64 v1403; // [rsp+1D30h] [rbp-1698h]
  __int64 v1404; // [rsp+1D38h] [rbp-1690h]
  __int64 v1405; // [rsp+1D40h] [rbp-1688h]
  unsigned __int64 v1406; // [rsp+1D48h] [rbp-1680h]
  _QWORD *v1407; // [rsp+1D50h] [rbp-1678h]
  __int64 v1408; // [rsp+1D58h] [rbp-1670h]
  _QWORD *v1409; // [rsp+1D60h] [rbp-1668h]
  unsigned __int64 v1410; // [rsp+1D68h] [rbp-1660h]
  __int64 v1411; // [rsp+1D70h] [rbp-1658h]
  __int64 v1412; // [rsp+1D78h] [rbp-1650h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+1D80h] [rbp-1648h]
  __int64 *v1414; // [rsp+1D88h] [rbp-1640h]
  __int64 v1415; // [rsp+1D90h] [rbp-1638h]
  struct CSessionTraceFlags *v1416; // [rsp+1D98h] [rbp-1630h]
  _QWORD *v1417; // [rsp+1DA0h] [rbp-1628h]
  __int64 v1418; // [rsp+1DA8h] [rbp-1620h]
  __int64 v1419; // [rsp+1DB0h] [rbp-1618h]
  __int64 v1420; // [rsp+1DB8h] [rbp-1610h]
  __int64 v1421; // [rsp+1DC0h] [rbp-1608h]
  __int64 v1422; // [rsp+1DC8h] [rbp-1600h]
  __int64 v1423; // [rsp+1DD0h] [rbp-15F8h]
  __int64 v1424; // [rsp+1DD8h] [rbp-15F0h]
  __int64 v1425; // [rsp+1DE0h] [rbp-15E8h]
  __int64 v1426; // [rsp+1DE8h] [rbp-15E0h]
  __int64 v1427; // [rsp+1DF0h] [rbp-15D8h]
  __int64 v1428; // [rsp+1DF8h] [rbp-15D0h]
  __int64 v1429; // [rsp+1E00h] [rbp-15C8h]
  __int64 v1430; // [rsp+1E08h] [rbp-15C0h]
  __int64 v1431; // [rsp+1E10h] [rbp-15B8h]
  __int64 v1432; // [rsp+1E18h] [rbp-15B0h]
  _DWORD *v1433; // [rsp+1E20h] [rbp-15A8h]
  _QWORD *v1434; // [rsp+1E28h] [rbp-15A0h]
  __int64 v1435; // [rsp+1E30h] [rbp-1598h]
  __int64 v1436; // [rsp+1E38h] [rbp-1590h]
  int *v1437; // [rsp+1E40h] [rbp-1588h]
  __int64 v1438; // [rsp+1E48h] [rbp-1580h]
  __int64 *v1439; // [rsp+1E50h] [rbp-1578h]
  _DWORD *v1440; // [rsp+1E58h] [rbp-1570h]
  _QWORD *v1441; // [rsp+1E60h] [rbp-1568h]
  __int64 v1442; // [rsp+1E68h] [rbp-1560h]
  __int64 v1443; // [rsp+1E70h] [rbp-1558h]
  __int64 v1444; // [rsp+1E78h] [rbp-1550h]
  _DWORD *v1445; // [rsp+1E80h] [rbp-1548h]
  __int64 v1446; // [rsp+1E88h] [rbp-1540h]
  char v1447[8]; // [rsp+1E90h] [rbp-1538h] BYREF
  _WORD v1448[4]; // [rsp+1E98h] [rbp-1530h] BYREF
  int v1449; // [rsp+1EA0h] [rbp-1528h]
  int **v1450; // [rsp+1EA8h] [rbp-1520h]
  char *v1451; // [rsp+1EB0h] [rbp-1518h]
  __int64 v1452; // [rsp+1EB8h] [rbp-1510h]
  int *v1453; // [rsp+1EC0h] [rbp-1508h] BYREF
  int v1454; // [rsp+1EC8h] [rbp-1500h]
  __int16 v1455; // [rsp+1ECCh] [rbp-14FCh]
  __int16 v1456; // [rsp+1ECEh] [rbp-14FAh]
  GUID *v1457; // [rsp+1ED0h] [rbp-14F8h] BYREF
  int v1458; // [rsp+1ED8h] [rbp-14F0h]
  __int16 v1459; // [rsp+1EDCh] [rbp-14ECh]
  __int16 v1460; // [rsp+1EDEh] [rbp-14EAh]
  GUID *v1461; // [rsp+1EE0h] [rbp-14E8h] BYREF
  int v1462; // [rsp+1EE8h] [rbp-14E0h]
  __int16 v1463; // [rsp+1EECh] [rbp-14DCh]
  __int16 v1464; // [rsp+1EEEh] [rbp-14DAh]
  wchar_t *v1465; // [rsp+1EF0h] [rbp-14D8h] BYREF
  int v1466; // [rsp+1EF8h] [rbp-14D0h]
  __int16 v1467; // [rsp+1EFCh] [rbp-14CCh]
  __int16 v1468; // [rsp+1EFEh] [rbp-14CAh]
  wchar_t *v1469; // [rsp+1F00h] [rbp-14C8h] BYREF
  int v1470; // [rsp+1F08h] [rbp-14C0h]
  __int16 v1471; // [rsp+1F0Ch] [rbp-14BCh]
  __int16 v1472; // [rsp+1F0Eh] [rbp-14BAh]
  __int64 v1473; // [rsp+1F10h] [rbp-14B8h] BYREF
  int v1474; // [rsp+1F18h] [rbp-14B0h]
  __int16 v1475; // [rsp+1F1Ch] [rbp-14ACh]
  __int16 v1476; // [rsp+1F1Eh] [rbp-14AAh]
  char v1477; // [rsp+1F20h] [rbp-14A8h] BYREF
  int v1478; // [rsp+20E0h] [rbp-12E8h]
  int v1479; // [rsp+20E4h] [rbp-12E4h]
  __int64 v1480; // [rsp+20E8h] [rbp-12E0h]
  int v1481; // [rsp+20F0h] [rbp-12D8h] BYREF
  __int16 v1482; // [rsp+20F4h] [rbp-12D4h]
  int v1483; // [rsp+20F6h] [rbp-12D2h]
  char v1484; // [rsp+20FAh] [rbp-12CEh]
  char v1485; // [rsp+20FBh] [rbp-12CDh]
  char v1486[8]; // [rsp+2130h] [rbp-1298h] BYREF
  _WORD v1487[4]; // [rsp+2138h] [rbp-1290h] BYREF
  int v1488; // [rsp+2140h] [rbp-1288h]
  int **v1489; // [rsp+2148h] [rbp-1280h]
  char *v1490; // [rsp+2150h] [rbp-1278h]
  __int64 v1491; // [rsp+2158h] [rbp-1270h]
  int *v1492; // [rsp+2160h] [rbp-1268h] BYREF
  int v1493; // [rsp+2168h] [rbp-1260h]
  __int16 v1494; // [rsp+216Ch] [rbp-125Ch]
  __int16 v1495; // [rsp+216Eh] [rbp-125Ah]
  GUID *v1496; // [rsp+2170h] [rbp-1258h] BYREF
  int v1497; // [rsp+2178h] [rbp-1250h]
  __int16 v1498; // [rsp+217Ch] [rbp-124Ch]
  __int16 v1499; // [rsp+217Eh] [rbp-124Ah]
  GUID *v1500; // [rsp+2180h] [rbp-1248h] BYREF
  int v1501; // [rsp+2188h] [rbp-1240h]
  __int16 v1502; // [rsp+218Ch] [rbp-123Ch]
  __int16 v1503; // [rsp+218Eh] [rbp-123Ah]
  wchar_t *v1504; // [rsp+2190h] [rbp-1238h] BYREF
  int v1505; // [rsp+2198h] [rbp-1230h]
  __int16 v1506; // [rsp+219Ch] [rbp-122Ch]
  __int16 v1507; // [rsp+219Eh] [rbp-122Ah]
  wchar_t *v1508; // [rsp+21A0h] [rbp-1228h] BYREF
  int v1509; // [rsp+21A8h] [rbp-1220h]
  __int16 v1510; // [rsp+21ACh] [rbp-121Ch]
  __int16 v1511; // [rsp+21AEh] [rbp-121Ah]
  __int64 v1512; // [rsp+21B0h] [rbp-1218h] BYREF
  int v1513; // [rsp+21B8h] [rbp-1210h]
  __int16 v1514; // [rsp+21BCh] [rbp-120Ch]
  __int16 v1515; // [rsp+21BEh] [rbp-120Ah]
  char v1516; // [rsp+21C0h] [rbp-1208h] BYREF
  int v1517; // [rsp+2380h] [rbp-1048h]
  int v1518; // [rsp+2384h] [rbp-1044h]
  __int64 v1519; // [rsp+2388h] [rbp-1040h]
  int v1520; // [rsp+2390h] [rbp-1038h] BYREF
  __int16 v1521; // [rsp+2394h] [rbp-1034h]
  int v1522; // [rsp+2396h] [rbp-1032h]
  char v1523; // [rsp+239Ah] [rbp-102Eh]
  char v1524; // [rsp+239Bh] [rbp-102Dh]
  char v1525[8]; // [rsp+23D0h] [rbp-FF8h] BYREF
  _WORD v1526[4]; // [rsp+23D8h] [rbp-FF0h] BYREF
  int v1527; // [rsp+23E0h] [rbp-FE8h]
  int **v1528; // [rsp+23E8h] [rbp-FE0h]
  char *v1529; // [rsp+23F0h] [rbp-FD8h]
  __int64 v1530; // [rsp+23F8h] [rbp-FD0h]
  int *v1531; // [rsp+2400h] [rbp-FC8h] BYREF
  int v1532; // [rsp+2408h] [rbp-FC0h]
  __int16 v1533; // [rsp+240Ch] [rbp-FBCh]
  __int16 v1534; // [rsp+240Eh] [rbp-FBAh]
  GUID *v1535; // [rsp+2410h] [rbp-FB8h] BYREF
  int v1536; // [rsp+2418h] [rbp-FB0h]
  __int16 v1537; // [rsp+241Ch] [rbp-FACh]
  __int16 v1538; // [rsp+241Eh] [rbp-FAAh]
  GUID *v1539; // [rsp+2420h] [rbp-FA8h] BYREF
  int v1540; // [rsp+2428h] [rbp-FA0h]
  __int16 v1541; // [rsp+242Ch] [rbp-F9Ch]
  __int16 v1542; // [rsp+242Eh] [rbp-F9Ah]
  wchar_t *v1543; // [rsp+2430h] [rbp-F98h] BYREF
  int v1544; // [rsp+2438h] [rbp-F90h]
  __int16 v1545; // [rsp+243Ch] [rbp-F8Ch]
  __int16 v1546; // [rsp+243Eh] [rbp-F8Ah]
  wchar_t *v1547; // [rsp+2440h] [rbp-F88h] BYREF
  int v1548; // [rsp+2448h] [rbp-F80h]
  __int16 v1549; // [rsp+244Ch] [rbp-F7Ch]
  __int16 v1550; // [rsp+244Eh] [rbp-F7Ah]
  __int64 v1551; // [rsp+2450h] [rbp-F78h] BYREF
  int v1552; // [rsp+2458h] [rbp-F70h]
  __int16 v1553; // [rsp+245Ch] [rbp-F6Ch]
  __int16 v1554; // [rsp+245Eh] [rbp-F6Ah]
  char v1555; // [rsp+2460h] [rbp-F68h] BYREF
  int v1556; // [rsp+2620h] [rbp-DA8h]
  int v1557; // [rsp+2624h] [rbp-DA4h]
  __int64 v1558; // [rsp+2628h] [rbp-DA0h]
  int v1559; // [rsp+2630h] [rbp-D98h] BYREF
  __int16 v1560; // [rsp+2634h] [rbp-D94h]
  int v1561; // [rsp+2636h] [rbp-D92h]
  char v1562; // [rsp+263Ah] [rbp-D8Eh]
  char v1563; // [rsp+263Bh] [rbp-D8Dh]
  int v1564; // [rsp+2674h] [rbp-D54h]
  int v1565; // [rsp+2678h] [rbp-D50h]
  int v1566; // [rsp+268Ch] [rbp-D3Ch]
  int v1567; // [rsp+2690h] [rbp-D38h]
  int v1568; // [rsp+26A4h] [rbp-D24h]
  int v1569; // [rsp+26A8h] [rbp-D20h]
  __int128 v1570; // [rsp+26B8h] [rbp-D10h] BYREF
  __int128 v1571; // [rsp+26E0h] [rbp-CE8h] BYREF
  __int128 v1572[4]; // [rsp+2708h] [rbp-CC0h] BYREF
  __int16 v1573; // [rsp+2748h] [rbp-C80h] BYREF
  unsigned __int16 v1574; // [rsp+274Ah] [rbp-C7Eh] BYREF
  int v1575; // [rsp+274Ch] [rbp-C7Ch]
  char *v1576; // [rsp+2750h] [rbp-C78h]
  struct PageComprInfo *v1577; // [rsp+2758h] [rbp-C70h]
  __int16 v1578; // [rsp+2760h] [rbp-C68h]
  __int16 v1579; // [rsp+2762h] [rbp-C66h]
  __int16 v1580; // [rsp+2764h] [rbp-C64h]
  __int64 v1581; // [rsp+2766h] [rbp-C62h]
  _BYTE v1582[10]; // [rsp+276Eh] [rbp-C5Ah] BYREF
  int v1583; // [rsp+2778h] [rbp-C50h]
  int v1584; // [rsp+277Ch] [rbp-C4Ch]
  __int128 v1585; // [rsp+2780h] [rbp-C48h] BYREF
  __int128 v1586; // [rsp+2790h] [rbp-C38h] BYREF
  _BYTE v1587[22]; // [rsp+27A0h] [rbp-C28h] BYREF
  __int16 v1588; // [rsp+27B6h] [rbp-C12h]
  __int64 v1589; // [rsp+27B8h] [rbp-C10h]
  __int128 v1590; // [rsp+27C0h] [rbp-C08h] BYREF
  __int128 v1591; // [rsp+27D0h] [rbp-BF8h]
  __int128 v1592; // [rsp+27E0h] [rbp-BE8h] BYREF
  __int64 v1593; // [rsp+27F0h] [rbp-BD8h]
  wchar_t v1594[24]; // [rsp+27F8h] [rbp-BD0h] BYREF
  wchar_t v1595[24]; // [rsp+2828h] [rbp-BA0h] BYREF
  wchar_t v1596[24]; // [rsp+2858h] [rbp-B70h] BYREF
  wchar_t v1597[24]; // [rsp+2888h] [rbp-B40h] BYREF
  wchar_t v1598[24]; // [rsp+28B8h] [rbp-B10h] BYREF
  wchar_t v1599[28]; // [rsp+28E8h] [rbp-AE0h] BYREF
  unsigned __int8 v1600[2656]; // [rsp+2920h] [rbp-AA8h] BYREF

  v1398 = -2;
  v621 = a4;
  v823 = a3;
  v865 = (struct PageRef *)a2;
  v7 = this;
  v619 = this;
  v866 = (struct PageRef *)a6;
  v970 = this;
  v972 = (struct PageRef *)a2;
  v969 = a5;
  v971 = (struct PageRef *)a6;
  v417 = 0;
  v418 = 0;
  v419 = 0;
  v1573 = -1;
  v1576 = 0;
  v1575 = 0;
  v1581 = 0;
  *(_QWORD *)&v1582[2] = 0;
  v1577 = 0;
  v1584 = -1;
  v1570 = 0;
  v426 = 0;
  v427 = 0;
  v428 = 0;
  v8 = *a2;
  v9 = *v8;
  v451 = *(_DWORD *)(*v8 + 8);
  v452 = *(_WORD *)(v9 + 12);
  v481 = *((_DWORD *)v8 + 28);
  v482 = *((_WORD *)v8 + 58);
  v10 = **((_QWORD **)v7 + 1);
  v864 = (*(unsigned int *)(v10 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v10 + 24) << 32)) << 16;
  v11 = *(_QWORD *)(v10 + 8);
  v483 = *(_DWORD *)(v11 + 960);
  v484 = *(_WORD *)(v11 + 964);
  v485 = 0;
  v12 = 2;
  if ( *((_DWORD *)v7 + 63) == 3 )
    v12 = 0;
  v991 = 0;
  v990[0] = 0;
  v990[1] = v10;
  if ( (**(unsigned __int16 (__fastcall ***)(__int64))v10)(v10) == 2 )
    v12 = 2;
  v992 = v12;
  v424 = 1;
  if ( !v451 && !v452 )
    utassert_fail(1u, "leftPageId != PageId_NULL", "BtreeMgr.cpp", 5067, 0);
  BTreeMgr::BeginXactForSplitShrink(v7, L"BTreeMgr::MoveRowFromLeftSibling");
  v990[0] = *((_QWORD *)v7 + 34);
  v13 = *a2;
  if ( *a2 )
  {
    v1399 = (__int64)v13 + 98;
    v508 = *((_WORD *)v13 + 49);
    if ( (v508 & 0x400) != 0 && *((__int16 *)a2 + 6) >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)a2);
      goto LABEL_31;
    }
    v477 = *((__int16 *)a2 + 6);
    v597 = *a2;
    v1400 = (__int64)v597 + 98;
    v509 = *((_WORD *)v597 + 49);
    if ( (v509 & 8) == 0 )
      goto LABEL_20;
    if ( v477 == 3 )
    {
      v477 = 4;
    }
    else if ( v477 < 2 )
    {
LABEL_20:
      v551 = (unsigned __int8)byte_10317ABE5 >> 7;
      if ( byte_10317ABE5 < 0 )
      {
        v15 = (volatile signed __int32 *)v597 + 25;
        v1403 = (__int64)v597 + 100;
        v785 = *((_DWORD *)v597 + 25);
        if ( (v785 & 8) != 0 && v477 >= 3 )
        {
          v1404 = (__int64)v597 + 100;
          v786 = *v15;
          if ( (v786 & 0xC0000000) != 0x40000000 )
          {
            v16 = (void *)*v597;
            if ( *v597 )
            {
              v976[18] = 2;
              if ( VirtualProtect(v16, 0x2000u, 2u, flOldProtect) )
              {
                _InterlockedAnd(v15, 0x3FFFFFFFu);
                _InterlockedOr(v15, 0x40000000u);
              }
            }
          }
        }
      }
      LatchBase::ReleaseInternal(v597 + 19, (unsigned int)v477);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
      {
        v552 = (unsigned __int8)byte_10317AD4F >> 1;
        if ( (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v597, 0, (unsigned int)v477);
      }
      *((_DWORD *)a2 + 3) &= 0xFFFF0000;
      *a2 = 0;
      v7 = v619;
      goto LABEL_31;
    }
    v1401 = (__int64)v597 + 100;
    v784 = *((_DWORD *)v597 + 25);
    if ( (v784 & 8) != 0 )
    {
      v14 = v597[18];
      if ( v14 )
      {
        v1402 = v597[18];
        if ( *(_QWORD *)(v14 + 1880) )
        {
          _mm_lfence();
          DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v14 + 1880), v597, (unsigned int)v477);
        }
      }
    }
    goto LABEL_20;
  }
LABEL_31:
  if ( !*a6 )
  {
    v861 = (__int64 *)*((_QWORD *)v7 + 1);
    v813 = (_DWORD *)*((_QWORD *)v7 + 2);
    v714 = 0;
    v715 = 0;
    v716 = 0;
    v945 = *v861;
    v982 = 0;
    v983 = 0;
    v17 = *(RecoveryUnit **)(v945 + 32);
    v431 = v17;
    v1405 = v945 + 20;
    v18 = (*(unsigned int *)(v945 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v945 + 24) << 32)) << 16;
    v1406 = v18;
    v19 = *((_QWORD *)v17 + 250);
    if ( v19 == v18 && (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v432 = 1;
LABEL_52:
      v884 = 0;
      v885 = 0;
      v886 = 0;
      v436 = 0;
      v421 = -1;
LABEL_53:
      v859 = (unsigned int *)v981;
      v1564 = 0;
      v1565 = 0;
      v553 = CommonGlobalState::m_CollectingStatistics;
      if ( !CommonGlobalState::m_CollectingStatistics )
        goto LABEL_59;
      v561 = (unsigned __int8)byte_10317ABE6 >> 7;
      if ( byte_10317ABE6 < 0 )
        goto LABEL_59;
      v787 = 0;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      v1414 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v26 = *v1414;
      v1415 = v26;
      if ( v26 && (v27 = **(struct CSessionTraceFlags ***)(v26 + 56), (v1416 = v27) != 0) )
      {
        v938 = v27;
        v787 = CSessionTraceFlags::CheckSessionTraceInternal(v27, 0x337u);
        if ( v787 )
        {
          v17 = v431;
          goto LABEL_59;
        }
      }
      else
      {
        v938 = 0;
      }
      v1417 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v1418 = v1417[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v31 = *(_QWORD *)(v1418 + 8);
      v1419 = v31;
      v17 = v431;
      if ( v31 )
      {
        v28 = *(struct SEInternalTLS **)(v31 + 96);
        goto LABEL_60;
      }
LABEL_59:
      v28 = 0;
LABEL_60:
      SETLSFromTlsMaybeNull = v28;
      v29 = (_QWORD *)((char *)v17 + 1832);
      v939 = *((_QWORD *)v17 + 229);
      while ( 1 )
      {
        v554 = 0;
        v30 = *a6;
        if ( *a6 )
          break;
LABEL_88:
        if ( *v29 )
        {
          PageRef::CatchupPageRedos((PageRef *)a6, (const struct PageId *)&v451, v17);
          v37 = *a6;
          if ( *a6 )
          {
            v1426 = (__int64)v37 + 98;
            v512 = *((_WORD *)v37 + 49);
            if ( (v512 & 0x400) != 0 && *((__int16 *)a6 + 6) >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)a6);
LABEL_112:
              v17 = v431;
              goto LABEL_113;
            }
            v471 = *((__int16 *)a6 + 6);
            v599 = *a6;
            v1427 = (__int64)v599 + 98;
            v543 = *((_WORD *)v599 + 49);
            if ( (v543 & 8) != 0 )
            {
              if ( v471 == 3 )
              {
                v471 = 4;
                goto LABEL_97;
              }
              if ( v471 >= 2 )
              {
LABEL_97:
                v1428 = (__int64)v599 + 100;
                v791 = *((_DWORD *)v599 + 25);
                if ( (v791 & 8) != 0 )
                {
                  v38 = v599[18];
                  if ( v38 )
                  {
                    v1429 = v599[18];
                    if ( *(_QWORD *)(v38 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v38 + 1880), v599, (unsigned int)v471);
                    }
                  }
                }
              }
            }
            v565 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v39 = (volatile signed __int32 *)v599 + 25;
              v1430 = (__int64)v599 + 100;
              v792 = *((_DWORD *)v599 + 25);
              if ( (v792 & 8) != 0 && v471 >= 3 )
              {
                v1431 = (__int64)v599 + 100;
                v793 = *v39;
                if ( (v793 & 0xC0000000) != 0x40000000 )
                {
                  v40 = (void *)*v599;
                  if ( *v599 )
                  {
                    v978[1] = 2;
                    if ( VirtualProtect(v40, 0x2000u, 2u, v979) )
                    {
                      _InterlockedAnd(v39, 0x3FFFFFFFu);
                      _InterlockedOr(v39, 0x40000000u);
                    }
                  }
                }
              }
            }
            v41 = v599;
            v42 = v471;
            LatchBase::ReleaseInternal(v599 + 19, (unsigned int)v471);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v566 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v41, 0, v42);
            }
            *((_DWORD *)a6 + 3) &= 0xFFFF0000;
            *a6 = 0;
            goto LABEL_112;
          }
        }
LABEL_113:
        RecoveryUnit::PrePageUpdateHint(v17, (const struct PageId *)&v451);
        LODWORD(v416) = 4;
        v43 = (__int64 *)BPool::Get(qword_10317B628, v17, &v451, &v554, v416, v859);
        *a6 = v43;
        v44 = *((_DWORD *)a6 + 3) & 0xFFFF0000 | 4;
        *((_DWORD *)a6 + 3) = v44;
        if ( SETLSFromTlsMaybeNull )
        {
          v45 = *v43;
          v1432 = v45;
          v46 = (_DWORD *)((char *)SETLSFromTlsMaybeNull + 1280);
          v1433 = v46;
          v47 = &v46[2 * (*v46 & 0xF) + 2];
          v1434 = v47;
          if ( *v47 != v45 )
          {
            *v47 = v45;
            ++*(_QWORD *)v46;
            v44 = *((_DWORD *)a6 + 3);
          }
        }
        v48 = v44 & 0xFFFFFF | (((v554 >> 3) & 1) << 24);
        *((_DWORD *)a6 + 3) = v48;
        *((_DWORD *)a6 + 4) = (_DWORD)a6[2] & 0xFFFFFF00 | (v554 >> 4) & 1;
        if ( v939 )
        {
          if ( SETLSFromTlsMaybeNull )
          {
            if ( SETLSFromTlsMaybeNull == *((struct SEInternalTLS **)v17 + 903) )
            {
              v49 = HIBYTE(v48);
              v979[2] = v49;
              v50 = (_QWORD *)(v939 + 22968);
              v1435 = v939 + 22968;
              ++*(_QWORD *)(v939 + 23336);
              v51 = v859;
              if ( v859[1] )
              {
                ++v50[47];
                v50[48] += *v51;
                if ( v49 )
                {
                  ++v50[49];
                  v50[50] += *v51;
                }
              }
            }
          }
        }
        if ( !RecoveryUnit::IsRbIoDb(v17) || !*((_BYTE *)v17 + 8272) )
          goto LABEL_221;
        if ( !v451 || (v868 = 9, v869 = 1, v451 == 9) && v452 == 1 )
        {
          v438 = 1;
          goto LABEL_221;
        }
        v438 = 0;
        v53 = **a6;
        v1436 = v53;
        v434 = 0;
        if ( *(_WORD *)(v53 + 36)
          && ((v54 = *(_BYTE *)(v53 + 1), v54 != 11) && v54 != 8 && v54 != 9
           || *(_DWORD *)(v53 + 24) != 99
           || (v1437 = &v681,
               v1438 = v53 + 32,
               v681 = *(_DWORD *)(v53 + 32),
               v682 = *(_WORD *)(v53 + 36),
               !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v681, v52))
            ? (v55 = 0)
            : (v55 = 1),
              (v434 = v55) != 0) )
        {
          PageHeader::GetIcxLsn(v53, &v655);
        }
        else
        {
          v655 = *(_QWORD *)(v53 + 40);
          v656 = *(_WORD *)(v53 + 48);
        }
        v1439 = &v655;
        v56 = (LSN *)((char *)v17 + 8444);
        v940 = (char *)v17 + 8444;
        v622 = 0;
        v623 = 0;
        v57 = (_DWORD *)((char *)v17 + 8456);
        v1440 = v57;
        v58 = *v57;
        v629 = *v57;
        v941 = v57;
        do
        {
          v794 = v58 & 0xFFFFFFFE;
          v622 = *(_QWORD *)v940;
          v623 = *((_DWORD *)v940 + 2);
          _InterlockedOr(v415, 0);
          v629 = *v941;
          v58 = v629;
        }
        while ( v794 != v629 );
        if ( (unsigned int)v622 >= (unsigned int)v655
          && ((_DWORD)v622 != (_DWORD)v655
           || HIDWORD(v622) >= HIDWORD(v655) && (HIDWORD(v622) != HIDWORD(v655) || (unsigned __int16)v623 >= v656)) )
        {
          goto LABEL_221;
        }
        if ( !*((_BYTE *)v431 + 27336) )
        {
          v1441 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v1442 = v1441[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v1443 = *(_QWORD *)(v1442 + 8);
          v1444 = *(_QWORD *)(v1443 + 96);
          if ( v1444 != *((_QWORD *)v431 + 1060) && !RecoveryUnit::IsParallelRedoThread(v431) )
          {
            v860 = v56;
            v613.QuadPart = 0;
            LowPart = 0;
            v1445 = v57;
            v59 = *v57;
            v628 = *v57;
            v60 = v56;
            p_HighPart = &v56[1].HighPart;
            while ( 1 )
            {
              v795 = v59 & 0xFFFFFFFE;
              v613 = *v60;
              LowPart = v60[1].LowPart;
              _InterlockedOr(v415, 0);
              v59 = *p_HighPart;
              v628 = v59;
              if ( v795 == v59 )
                break;
              v60 = v860;
            }
            v887 = v613;
            v61 = LowPart;
            v888 = LowPart;
            v62 = **a6;
            v1446 = v62;
            v435 = 0;
            if ( *(_WORD *)(v62 + 36)
              && ((v63 = *(_BYTE *)(v62 + 1), v63 != 11) && v63 != 8 && v63 != 9
               || *(_DWORD *)(v62 + 24) != 99
               || (v1014 = &v665,
                   v1015 = v62 + 32,
                   v665 = *(_DWORD *)(v62 + 32),
                   v666 = *(_WORD *)(v62 + 36),
                   !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v665, v60))
                ? (v64 = 0)
                : (v64 = 1),
                  (v435 = v64) != 0) )
            {
              PageHeader::GetIcxLsn(v62, &v657);
              v65 = v658;
            }
            else
            {
              v657 = *(LSN *)(v62 + 40);
              v65 = *(_WORD *)(v62 + 48);
              v658 = v65;
            }
            if ( v613.LowPart < v657.LowPart
              || v613.LowPart == v657.LowPart
              && (v613.HighPart < (unsigned int)v657.HighPart || v613.HighPart == v657.HighPart && v61 < v65) )
            {
              v66 = v431;
              v1016 = *((_QWORD *)v431 + 214);
              LSN::FormatAsHexString(&v657, v1594, &v796);
              LSN::FormatAsHexString(&v887, v1595, &v796);
              v943 = 29;
              v944 = 0x10000;
              if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
              {
                v765 = 6;
                v1017 = v1448;
                v1448[0] = 0;
                v1448[1] = 6;
                v1449 = 0;
                v1450 = &v1453;
                v1451 = &v1477;
                v1478 = 0;
                v1479 = 0;
                v1452 = 0;
                v1480 = 0;
                v1018 = &v1453;
                v1453 = &v1481;
                v1454 = 52;
                v1455 = 5;
                v1456 = 0;
                v1019 = &v1457;
                v1457 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                v1458 = 16;
                v1459 = 5;
                v1460 = 0;
                v1020 = &v1461;
                v1461 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                v1462 = 16;
                v1463 = 6;
                v1464 = 0;
                v1021 = &v1465;
                v1465 = 0;
                v1466 = 0;
                v1467 = 7;
                v1468 = 0;
                v1022 = &v1469;
                v1469 = 0;
                v1470 = 0;
                v1471 = 8;
                v1472 = 0;
                v1023 = &v1473;
                v1473 = 0;
                v1474 = 0;
                v1475 = 9;
                v1476 = 0;
                v1481 = *((unsigned __int16 *)v66 + 860);
                v1482 = v452;
                v1483 = v451;
                v1484 = v421;
                v1024 = **a6;
                v1485 = *(_BYTE *)(v1024 + 1);
                v1025 = &v1457;
                v1457 = (GUID *)(v67 + 596);
                v1458 = 16;
                v1459 = 5;
                v1460 = 0;
                v1026 = &v1461;
                v1461 = (GUID *)(v67 + 580);
                v1462 = 16;
                v1463 = 6;
                v1464 = 0;
                v1027 = v1594;
                v68 = -1;
                do
                  ++v68;
                while ( v1594[v68] );
                v979[4] = 2 * v68;
                v1028 = &v1465;
                v1465 = v1594;
                v1466 = 2 * v68;
                v1467 = 7;
                v1468 = 0;
                v1029 = v1595;
                v69 = -1;
                do
                  ++v69;
                while ( v1595[v69] );
                v979[5] = 2 * v69;
                v1030 = &v1469;
                v1469 = v1595;
                v1470 = 2 * v69;
                v1471 = 8;
                v1472 = 0;
                v797 = 0;
                v70 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v67, &v797);
                v71 = (int *)v70;
                v1031 = v70;
                if ( v70 )
                {
                  v72 = -1;
                  do
                    ++v72;
                  while ( *(_WORD *)(v70 + 2 * v72) );
                  v73 = 2 * v72;
                }
                else
                {
                  v73 = 0;
                }
                v979[6] = v73;
                v74 = v1450 + 10;
                v1032 = v1450 + 10;
                v1450[10] = v71;
                *((_DWORD *)v74 + 2) = v73;
                *((_WORD *)v74 + 6) = 9;
                *((_WORD *)v74 + 7) = 0;
                XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v1447);
              }
            }
LABEL_221:
            if ( *((__int16 *)a6 + 6) >= 2 && v421 != -1 )
            {
              v87 = **a6;
              v1050 = v87;
              if ( *(_BYTE *)(v87 + 1) != v421 )
              {
                if ( SETLSFromTlsMaybeNull )
                {
                  v1051 = v87;
                  *((_QWORD *)SETLSFromTlsMaybeNull + 177) = v87;
                }
                if ( !UtilDbccGetContext() || !*((_QWORD *)UtilDbccGetContext() + 6) )
                {
                  v801 = 0;
                  goto LABEL_234;
                }
                v88 = *(_DWORD *)(*((_QWORD *)UtilDbccGetContext() + 6) + 12LL);
                v912 = v88;
                if ( v88 > 0xD || (v89 = 9792, v90 = _bittest(&v89, v88), v91 = 1, !v90) )
                  v91 = 0;
                v801 = v91;
                if ( !v91 )
LABEL_234:
                  RaiseInconsistencyError(0, 8);
              }
            }
LABEL_235:
            v891 = 0;
            v892 = 0;
            v893 = 0;
            if ( v716 || v714 || v715 )
            {
              v92 = *a6;
              v1052 = **a6;
              if ( (*(_BYTE *)(v1052 + 4) & 1) != 0 )
              {
                v1053 = (__int64)v92 + 98;
                v515 = *((_WORD *)v92 + 49);
                if ( (v515 & 0x400) != 0 && *((__int16 *)a6 + 6) >= 3 )
                {
                  PageRef::UnfixLatchOnly((PageRef *)a6);
LABEL_261:
                  v999 = 4194400;
                  v1000 = 0;
                  v1002 = 0;
                  v1001 = 0;
                  v1003 = 0;
                  SOS_Task::Sleep(10, &v999);
                  v17 = v431;
                  goto LABEL_53;
                }
                v458 = *((__int16 *)a6 + 6);
                v601 = *a6;
                v1054 = (__int64)v601 + 98;
                v516 = *((_WORD *)v601 + 49);
                if ( (v516 & 8) != 0 )
                {
                  if ( v458 == 3 )
                  {
                    v458 = 4;
                    goto LABEL_246;
                  }
                  if ( v458 >= 2 )
                  {
LABEL_246:
                    v1055 = (__int64)v601 + 100;
                    v802 = *((_DWORD *)v601 + 25);
                    if ( (v802 & 8) != 0 )
                    {
                      v93 = v601[18];
                      if ( v93 )
                      {
                        v1056 = v601[18];
                        if ( *(_QWORD *)(v93 + 1880) )
                        {
                          _mm_lfence();
                          DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v93 + 1880), v601, (unsigned int)v458);
                        }
                      }
                    }
                  }
                }
                v569 = (unsigned __int8)byte_10317ABE5 >> 7;
                if ( byte_10317ABE5 < 0 )
                {
                  v94 = (volatile signed __int32 *)v601 + 25;
                  v1057 = (__int64)v601 + 100;
                  v803 = *((_DWORD *)v601 + 25);
                  if ( (v803 & 8) != 0 && v458 >= 3 )
                  {
                    v1058 = (__int64)v601 + 100;
                    v804 = *v94;
                    if ( (v804 & 0xC0000000) != 0x40000000 )
                    {
                      v95 = (void *)*v601;
                      if ( *v601 )
                      {
                        v913 = 2;
                        if ( VirtualProtect(v95, 0x2000u, 2u, v914) )
                        {
                          _InterlockedAnd(v94, 0x3FFFFFFFu);
                          _InterlockedOr(v94, 0x40000000u);
                        }
                      }
                    }
                  }
                }
                v96 = v601;
                v97 = v458;
                LatchBase::ReleaseInternal(v601 + 19, (unsigned int)v458);
                if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
                {
                  v570 = (unsigned __int8)byte_10317AD4F >> 1;
                  if ( (byte_10317AD4F & 2) != 0 )
                    BUF::TraceLatchAcquireRelease(v96, 0, v97);
                }
                *((_DWORD *)a6 + 3) &= 0xFFFF0000;
                *a6 = 0;
                goto LABEL_261;
              }
            }
            v98 = v813;
            ++v813[1];
            v99 = *((_QWORD *)v98 + 11);
            if ( v99 )
              ++*(_DWORD *)(v99 + 4);
            if ( (*((_DWORD *)a6 + 3) & 0xFF000000) != 0 )
            {
              ++v813[2];
              v100 = *((_QWORD *)v98 + 11);
              if ( v100 )
                ++*(_DWORD *)(v100 + 8);
              if ( *((_BYTE *)a6 + 16) )
              {
                ++v813[3];
                v101 = *((_QWORD *)v98 + 11);
                if ( v101 )
                  ++*(_DWORD *)(v101 + 12);
              }
            }
            if ( v982 )
            {
              v1059 = **a6;
              HoBtAccess::UpdateLatchWaitStats(v945, *(unsigned __int8 *)(v1059 + 1), v981, 0xFFFFFFFFLL);
            }
            v571 = 0;
            v572 = 1;
            v636 = 0;
            v637 = 0;
            v638 = 0;
            v102 = *v861;
            v946 = (__int64 (__fastcall ***)(_QWORD))v102;
            v103 = *a6;
            v104 = **a6;
            v1060 = v104;
            v105 = *(_QWORD *)(v102 + 8) + 960LL;
            v1061 = v105;
            v805 = 0;
            if ( *(_DWORD *)(v104 + 24) == *(_DWORD *)v105 )
            {
              v106 = *(_WORD *)(v104 + 6);
              v107 = *(_WORD *)(v105 + 4);
              if ( v106 == v107 || (unsigned __int16)(v106 | v107) <= 1u )
              {
                v805 = 1;
                goto LABEL_299;
              }
            }
            v1062 = v104;
            v696 = 0;
            v697 = 0;
            v698 = 0;
            v108 = *(_DWORD *)(v104 + 24);
            v696 = v108;
            v109 = *(_WORD *)(v104 + 6);
            v697 = v109;
            v636 = v108;
            v637 = v109;
            v638 = 0;
            v1063 = (__int64)v103 + 98;
            v517 = *((_WORD *)v103 + 49);
            if ( (v517 & 0x400) != 0 && *((__int16 *)a6 + 6) >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)a6);
LABEL_298:
              v1069 = &v690;
              v1070 = &v711;
              v115 = *(_QWORD *)(v102 + 8);
              v1071 = v115 + 960;
              v690 = *(_DWORD *)(v115 + 960);
              v691 = *(_WORD *)(v115 + 964);
              v692 = 0;
              v711 = v108;
              v712 = v109;
              v713 = 0;
              v116 = (**v946)(v946);
              RaiseWrongPageError(&v451, &v711, v116, &v690, *((_DWORD *)v861 + 4));
              goto LABEL_299;
            }
            v459 = *((__int16 *)a6 + 6);
            v602 = *a6;
            v1064 = (__int64)v602 + 98;
            v518 = *((_WORD *)v602 + 49);
            if ( (v518 & 8) != 0 )
            {
              if ( v459 == 3 )
              {
                v459 = 4;
                goto LABEL_283;
              }
              if ( v459 >= 2 )
              {
LABEL_283:
                v1065 = (__int64)v602 + 100;
                v806 = *((_DWORD *)v602 + 25);
                if ( (v806 & 8) != 0 )
                {
                  v110 = v602[18];
                  if ( v110 )
                  {
                    v1066 = v602[18];
                    if ( *(_QWORD *)(v110 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v110 + 1880), v602, (unsigned int)v459);
                    }
                  }
                }
              }
            }
            v573 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v111 = (volatile signed __int32 *)v602 + 25;
              v1067 = (__int64)v602 + 100;
              v807 = *((_DWORD *)v602 + 25);
              if ( (v807 & 8) != 0 && v459 >= 3 )
              {
                v1068 = (__int64)v602 + 100;
                v808 = *v111;
                if ( (v808 & 0xC0000000) != 0x40000000 )
                {
                  v112 = (void *)*v602;
                  if ( *v602 )
                  {
                    v914[1] = 2;
                    if ( VirtualProtect(v112, 0x2000u, 2u, v915) )
                    {
                      _InterlockedAnd(v111, 0x3FFFFFFFu);
                      _InterlockedOr(v111, 0x40000000u);
                    }
                  }
                }
              }
            }
            v113 = v602;
            v114 = v459;
            LatchBase::ReleaseInternal(v602 + 19, (unsigned int)v459);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v574 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v113, 0, v114);
            }
            *((_DWORD *)a6 + 3) &= 0xFFFF0000;
            *a6 = 0;
            goto LABEL_298;
          }
        }
        if ( v436 )
          goto LABEL_235;
        v1033 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v1034 = v1033[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v1035 = *(_QWORD *)(v1034 + 8);
        v1036 = *(_QWORD *)(v1035 + 96);
        v17 = v431;
        if ( v1036 == *((_QWORD *)v431 + 1060) || RecoveryUnit::IsParallelRedoThread(v431) )
          goto LABEL_221;
        if ( !SETLSFromTlsMaybeNull )
          SETLSFromTlsMaybeNull = GetSETLSFromTlsMaybeNull();
        v1037 = &v659;
        v76 = **a6;
        v1038 = v76;
        v437 = 0;
        if ( *(_WORD *)(v76 + 36)
          && (((v77 = *(_BYTE *)(v76 + 1), v77 != 11) || *(_DWORD *)(v76 + 24) != 99)
           && (v77 != 8 && v77 != 9 || *(_DWORD *)(v76 + 24) != 99)
           || (v1039 = &v667,
               v1040 = v76 + 32,
               v667 = *(_DWORD *)(v76 + 32),
               v668 = *(_WORD *)(v76 + 36),
               !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v667, v75))
            ? (v78 = 0)
            : (v78 = 1),
              (v437 = v78) != 0) )
        {
          PageHeader::GetIcxLsn(v76, &v659);
          v79 = v660;
          v80 = v659;
        }
        else
        {
          v80 = *(_QWORD *)(v76 + 40);
          v659 = v80;
          v79 = *(_WORD *)(v76 + 48);
          v660 = v79;
        }
        v1041 = &v659;
        v723 = v80;
        v724 = v79;
        v725 = 0;
        v81 = *a6;
        if ( *a6 )
        {
          v1042 = (__int64)v81 + 98;
          v513 = *((_WORD *)v81 + 49);
          if ( (v513 & 0x400) != 0 && *((__int16 *)a6 + 6) >= 3 )
          {
            PageRef::UnfixLatchOnly((PageRef *)a6);
LABEL_218:
            v80 = v723;
            v79 = v724;
            v17 = v431;
            goto LABEL_219;
          }
          v457 = *((__int16 *)a6 + 6);
          v600 = *a6;
          v1043 = (__int64)v600 + 98;
          v514 = *((_WORD *)v600 + 49);
          if ( (v514 & 8) != 0 )
          {
            if ( v457 == 3 )
            {
              v457 = 4;
              goto LABEL_203;
            }
            if ( v457 >= 2 )
            {
LABEL_203:
              v1044 = (__int64)v600 + 100;
              v798 = *((_DWORD *)v600 + 25);
              if ( (v798 & 8) != 0 )
              {
                v82 = v600[18];
                if ( v82 )
                {
                  v1045 = v600[18];
                  if ( *(_QWORD *)(v82 + 1880) )
                  {
                    _mm_lfence();
                    DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v82 + 1880), v600, (unsigned int)v457);
                  }
                }
              }
            }
          }
          v567 = (unsigned __int8)byte_10317ABE5 >> 7;
          if ( byte_10317ABE5 < 0 )
          {
            v83 = (volatile signed __int32 *)v600 + 25;
            v1046 = (__int64)v600 + 100;
            v799 = *((_DWORD *)v600 + 25);
            if ( (v799 & 8) != 0 && v457 >= 3 )
            {
              v1047 = (__int64)v600 + 100;
              v800 = *v83;
              if ( (v800 & 0xC0000000) != 0x40000000 )
              {
                v84 = (void *)*v600;
                if ( *v600 )
                {
                  v979[7] = 2;
                  if ( VirtualProtect(v84, 0x2000u, 2u, v980) )
                  {
                    _InterlockedAnd(v83, 0x3FFFFFFFu);
                    _InterlockedOr(v83, 0x40000000u);
                  }
                }
              }
            }
          }
          v85 = v600;
          v86 = v457;
          LatchBase::ReleaseInternal(v600 + 19, (unsigned int)v457);
          if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
          {
            v568 = (unsigned __int8)byte_10317AD4F >> 1;
            if ( (byte_10317AD4F & 2) != 0 )
              BUF::TraceLatchAcquireRelease(v85, 0, v86);
          }
          *((_DWORD *)a6 + 3) &= 0xFFFF0000;
          *a6 = 0;
          goto LABEL_218;
        }
LABEL_219:
        v1048 = &v889;
        v889 = v80;
        v890 = v79;
        v1049 = &v852;
        v852 = v80;
        v853 = v79;
        v416 = 0;
        RecoveryMgr::WaitForRedoLsnToCatchUp(*v29, &v852, 4);
      }
      v1420 = (__int64)v30 + 98;
      v510 = *((_WORD *)v30 + 49);
      if ( (v510 & 0x400) != 0 && *((__int16 *)a6 + 6) >= 3 )
      {
        PageRef::UnfixLatchOnly((PageRef *)a6);
LABEL_87:
        v17 = v431;
        goto LABEL_88;
      }
      v478 = *((__int16 *)a6 + 6);
      v598 = *a6;
      v1421 = (__int64)v598 + 98;
      v511 = *((_WORD *)v598 + 49);
      if ( (v511 & 8) != 0 )
      {
        if ( v478 == 3 )
        {
          v478 = 4;
LABEL_72:
          v1422 = (__int64)v598 + 100;
          v788 = *((_DWORD *)v598 + 25);
          if ( (v788 & 8) != 0 )
          {
            v32 = v598[18];
            if ( v32 )
            {
              v1423 = v598[18];
              if ( *(_QWORD *)(v32 + 1880) )
              {
                _mm_lfence();
                DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v32 + 1880), v598, (unsigned int)v478);
              }
            }
          }
          goto LABEL_76;
        }
        if ( v478 >= 2 )
          goto LABEL_72;
      }
LABEL_76:
      v562 = (unsigned __int8)byte_10317ABE5 >> 7;
      if ( byte_10317ABE5 < 0 )
      {
        v33 = (volatile signed __int32 *)v598 + 25;
        v1424 = (__int64)v598 + 100;
        v789 = *((_DWORD *)v598 + 25);
        if ( (v789 & 8) != 0 && v478 >= 3 )
        {
          v1425 = (__int64)v598 + 100;
          v790 = *v33;
          if ( (v790 & 0xC0000000) != 0x40000000 )
          {
            v34 = (void *)*v598;
            if ( *v598 )
            {
              flOldProtect[1] = 2;
              if ( VirtualProtect(v34, 0x2000u, 2u, v978) )
              {
                _InterlockedAnd(v33, 0x3FFFFFFFu);
                _InterlockedOr(v33, 0x40000000u);
              }
            }
          }
        }
      }
      v35 = v598;
      v36 = v478;
      LatchBase::ReleaseInternal(v598 + 19, (unsigned int)v478);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
      {
        v564 = (unsigned __int8)byte_10317AD4F >> 1;
        if ( (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v35, 0, v36);
      }
      *((_DWORD *)a6 + 3) &= 0xFFFF0000;
      *a6 = 0;
      goto LABEL_87;
    }
    v432 = 0;
    v20 = *((_QWORD *)v17 + 251);
    if ( v20 == v18 && (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v433 = 1;
      goto LABEL_52;
    }
    v433 = 0;
    v1407 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v21 = v1407[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v1408 = v21;
    v22 = *(_QWORD **)(v21 + 256);
    v936 = v22;
    if ( !v22 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v22 = *(_QWORD **)(v21 + 256);
      v936 = v22;
    }
    v1409 = v22;
    v23 = __rdtsc();
    v1410 = v23;
    v24 = v22[104];
    if ( v23 <= v24 && (v24 == 0x7FFFFFFFFFFFFFFFLL || v24 - v23 <= *(_QWORD *)(v22[76] + 3568LL)) )
    {
      v937 = v22[75];
      v1411 = v937 + 188;
      if ( (*(_DWORD *)(v937 + 188) & 4) != 0 )
      {
        v25 = *(_QWORD *)(v937 + 152);
        v1412 = v25;
        if ( (*(_BYTE *)(v25 + 616) & 1) == 0 && (*(_DWORD *)(v25 + 800) & 0x180) == 0 )
        {
          v620 = 2;
LABEL_50:
          LOBYTE(v25) = 124;
          RaiseExecutionAbortedError(v25);
          goto LABEL_51;
        }
      }
      v620 = 0;
    }
    else
    {
      v620 = SOS_Task::Sleep(0, yieldWait);
      if ( v620 == 2 )
        goto LABEL_50;
    }
LABEL_51:
    v17 = v431;
    goto LABEL_52;
  }
  v424 = 0;
LABEL_299:
  v856 = (__int64 *)*((_QWORD *)v619 + 1);
  v814 = (_DWORD *)*((_QWORD *)v619 + 2);
  v717 = 0;
  v718 = 0;
  v719 = 0;
  v956 = *v856;
  v985 = 0;
  v986 = 0;
  v117 = *(RecoveryUnit **)(v956 + 32);
  v429 = v117;
  v1072 = v956 + 20;
  v118 = (*(unsigned int *)(v956 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v956 + 24) << 32)) << 16;
  v1073 = v118;
  v119 = *((_QWORD *)v117 + 250);
  if ( v119 != v118 || (unsigned __int64)(v119 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v439 = 0;
    v120 = *((_QWORD *)v117 + 251);
    if ( v120 == v118 && (unsigned __int64)(v120 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v440 = 1;
      goto LABEL_318;
    }
    v440 = 0;
    v1074 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v121 = v1074[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v1075 = v121;
    v122 = *(_QWORD **)(v121 + 256);
    v947 = v122;
    if ( !v122 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v122 = *(_QWORD **)(v121 + 256);
      v947 = v122;
    }
    v1076 = v122;
    v123 = __rdtsc();
    v1077 = v123;
    v124 = v122[104];
    if ( v123 <= v124 && (v124 == 0x7FFFFFFFFFFFFFFFLL || v124 - v123 <= *(_QWORD *)(v122[76] + 3568LL)) )
    {
      v948 = v122[75];
      v1078 = v948 + 188;
      if ( (*(_DWORD *)(v948 + 188) & 4) != 0 )
      {
        v125 = *(_QWORD *)(v948 + 152);
        v1079 = v125;
        if ( (*(_BYTE *)(v125 + 616) & 1) == 0 && (*(_DWORD *)(v125 + 800) & 0x180) == 0 )
        {
          v617 = 2;
LABEL_316:
          LOBYTE(v125) = 124;
          RaiseExecutionAbortedError(v125);
          goto LABEL_317;
        }
      }
      v617 = 0;
    }
    else
    {
      v617 = SOS_Task::Sleep(0, yieldWait);
      if ( v617 == 2 )
        goto LABEL_316;
    }
LABEL_317:
    v117 = v429;
    goto LABEL_318;
  }
  v439 = 1;
LABEL_318:
  v894 = 0;
  v895 = 0;
  v896 = 0;
  v450 = 0;
  v422 = -1;
  while ( 2 )
  {
    v862 = (unsigned int *)v984;
    v1566 = 0;
    v1567 = 0;
    v575 = CommonGlobalState::m_CollectingStatistics;
    if ( !CommonGlobalState::m_CollectingStatistics )
      goto LABEL_325;
    v576 = (unsigned __int8)byte_10317ABE6 >> 7;
    if ( byte_10317ABE6 < 0 )
      goto LABEL_325;
    v809 = 0;
    v1080 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v1081 = (__int64 *)(v1080[SystemThread_TlsIndex] + SystemThread_TlsOffset);
    v126 = *v1081;
    v1082 = v126;
    if ( v126 && (v127 = **(struct CSessionTraceFlags ***)(v126 + 56), (v1083 = v127) != 0) )
    {
      v949 = v127;
      v809 = CSessionTraceFlags::CheckSessionTraceInternal(v127, 0x337u);
      if ( v809 )
      {
        v117 = v429;
        goto LABEL_325;
      }
    }
    else
    {
      v949 = 0;
    }
    v1084 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v1085 = v1084[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v131 = *(_QWORD *)(v1085 + 8);
    v1086 = v131;
    v117 = v429;
    if ( v131 )
    {
      v128 = *(struct SEInternalTLS **)(v131 + 96);
      goto LABEL_326;
    }
LABEL_325:
    v128 = 0;
LABEL_326:
    v639 = v128;
    v129 = (_QWORD *)((char *)v117 + 1832);
    v950 = *((_QWORD *)v117 + 229);
    while ( 1 )
    {
      v555 = 0;
      v130 = *a2;
      if ( *a2 )
      {
        v1087 = (__int64)v130 + 98;
        v519 = *((_WORD *)v130 + 49);
        if ( (v519 & 0x400) != 0 && *((__int16 *)a2 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)a2);
LABEL_353:
          v117 = v429;
          goto LABEL_354;
        }
        v460 = *((__int16 *)a2 + 6);
        v603 = *a2;
        v1088 = (__int64)v603 + 98;
        v520 = *((_WORD *)v603 + 49);
        if ( (v520 & 8) != 0 )
        {
          if ( v460 == 3 )
          {
            v460 = 4;
LABEL_338:
            v1089 = (__int64)v603 + 100;
            v810 = *((_DWORD *)v603 + 25);
            if ( (v810 & 8) != 0 )
            {
              v132 = v603[18];
              if ( v132 )
              {
                v1090 = v603[18];
                if ( *(_QWORD *)(v132 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v132 + 1880), v603, (unsigned int)v460);
                }
              }
            }
            goto LABEL_342;
          }
          if ( v460 >= 2 )
            goto LABEL_338;
        }
LABEL_342:
        v577 = (unsigned __int8)byte_10317ABE5 >> 7;
        if ( byte_10317ABE5 < 0 )
        {
          v133 = (volatile signed __int32 *)v603 + 25;
          v1091 = (__int64)v603 + 100;
          v811 = *((_DWORD *)v603 + 25);
          if ( (v811 & 8) != 0 && v460 >= 3 )
          {
            v1092 = (__int64)v603 + 100;
            v812 = *v133;
            if ( (v812 & 0xC0000000) != 0x40000000 )
            {
              v134 = (void *)*v603;
              if ( *v603 )
              {
                v915[1] = 2;
                if ( VirtualProtect(v134, 0x2000u, 2u, v916) )
                {
                  _InterlockedAnd(v133, 0x3FFFFFFFu);
                  _InterlockedOr(v133, 0x40000000u);
                }
              }
            }
          }
        }
        v135 = v603;
        v136 = v460;
        LatchBase::ReleaseInternal(v603 + 19, (unsigned int)v460);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
        {
          v578 = (unsigned __int8)byte_10317AD4F >> 1;
          if ( (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v135, 0, v136);
        }
        *((_DWORD *)a2 + 3) &= 0xFFFF0000;
        *a2 = 0;
        goto LABEL_353;
      }
LABEL_354:
      if ( *v129 )
      {
        PageRef::CatchupPageRedos((PageRef *)a2, (const struct PageId *)&v481, v117);
        v137 = *a2;
        if ( *a2 )
        {
          v1093 = (__int64)v137 + 98;
          v521 = *((_WORD *)v137 + 49);
          if ( (v521 & 0x400) != 0 && *((__int16 *)a2 + 6) >= 3 )
          {
            PageRef::UnfixLatchOnly((PageRef *)a2);
LABEL_378:
            v117 = v429;
            goto LABEL_379;
          }
          v461 = *((__int16 *)a2 + 6);
          v604 = *a2;
          v1094 = (__int64)v604 + 98;
          v522 = *((_WORD *)v604 + 49);
          if ( (v522 & 8) != 0 )
          {
            if ( v461 == 3 )
            {
              v461 = 4;
LABEL_363:
              v1095 = (__int64)v604 + 100;
              v825 = *((_DWORD *)v604 + 25);
              if ( (v825 & 8) != 0 )
              {
                v138 = v604[18];
                if ( v138 )
                {
                  v1096 = v604[18];
                  if ( *(_QWORD *)(v138 + 1880) )
                  {
                    _mm_lfence();
                    DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v138 + 1880), v604, (unsigned int)v461);
                  }
                }
              }
              goto LABEL_367;
            }
            if ( v461 >= 2 )
              goto LABEL_363;
          }
LABEL_367:
          v579 = (unsigned __int8)byte_10317ABE5 >> 7;
          if ( byte_10317ABE5 < 0 )
          {
            v139 = (volatile signed __int32 *)v604 + 25;
            v1097 = (__int64)v604 + 100;
            v826 = *((_DWORD *)v604 + 25);
            if ( (v826 & 8) != 0 && v461 >= 3 )
            {
              v1098 = (__int64)v604 + 100;
              v827 = *v139;
              if ( (v827 & 0xC0000000) != 0x40000000 )
              {
                v140 = (void *)*v604;
                if ( *v604 )
                {
                  v916[1] = 2;
                  if ( VirtualProtect(v140, 0x2000u, 2u, v917) )
                  {
                    _InterlockedAnd(v139, 0x3FFFFFFFu);
                    _InterlockedOr(v139, 0x40000000u);
                  }
                }
              }
            }
          }
          v141 = v604;
          v142 = v461;
          LatchBase::ReleaseInternal(v604 + 19, (unsigned int)v461);
          if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
          {
            v580 = (unsigned __int8)byte_10317AD4F >> 1;
            if ( (byte_10317AD4F & 2) != 0 )
              BUF::TraceLatchAcquireRelease(v141, 0, v142);
          }
          *((_DWORD *)a2 + 3) &= 0xFFFF0000;
          *a2 = 0;
          goto LABEL_378;
        }
      }
LABEL_379:
      RecoveryUnit::PrePageUpdateHint(v117, (const struct PageId *)&v481);
      LODWORD(v416) = 4;
      *a2 = (__int64 *)BPool::Get(qword_10317B628, v117, &v481, &v555, v416, v862);
      v143 = *((_DWORD *)a2 + 3) & 0xFFFF0000 | 4;
      *((_DWORD *)a2 + 3) = v143;
      if ( v639 )
      {
        v144 = **a2;
        v1099 = v144;
        v145 = (_DWORD *)((char *)v639 + 1280);
        v1100 = v145;
        v146 = &v145[2 * (*v145 & 0xF) + 2];
        v1101 = v146;
        if ( *v146 != v144 )
        {
          *v146 = v144;
          ++*(_QWORD *)v145;
          v143 = *((_DWORD *)a2 + 3);
        }
      }
      v147 = v143 & 0xFFFFFF | (((v555 >> 3) & 1) << 24);
      *((_DWORD *)a2 + 3) = v147;
      *((_DWORD *)a2 + 4) = (_DWORD)a2[2] & 0xFFFFFF00 | (v555 >> 4) & 1;
      if ( v950 )
      {
        if ( v639 )
        {
          if ( v639 == *((struct SEInternalTLS **)v117 + 903) )
          {
            v148 = HIBYTE(v147);
            v917[2] = v148;
            v149 = (_QWORD *)(v950 + 22968);
            v1102 = v950 + 22968;
            ++*(_QWORD *)(v950 + 23336);
            v150 = v862;
            if ( v862[1] )
            {
              ++v149[47];
              v149[48] += *v150;
              if ( v148 )
              {
                ++v149[49];
                v149[50] += *v150;
              }
            }
          }
        }
      }
      if ( !RecoveryUnit::IsRbIoDb(v117) || !*((_BYTE *)v117 + 8272) )
        goto LABEL_487;
      if ( !v481 || (v870 = 9, v871 = 1, v481 == 9) && v482 == 1 )
      {
        v456 = 1;
        goto LABEL_487;
      }
      v456 = 0;
      v152 = **a2;
      v1103 = v152;
      v441 = 0;
      if ( *(_WORD *)(v152 + 36)
        && ((v153 = *(_BYTE *)(v152 + 1), v153 != 11) && v153 != 8 && v153 != 9
         || *(_DWORD *)(v152 + 24) != 99
         || (v1104 = &v669,
             v1105 = v152 + 32,
             v669 = *(_DWORD *)(v152 + 32),
             v670 = *(_WORD *)(v152 + 36),
             !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v669, v151))
          ? (v154 = 0)
          : (v154 = 1),
            (v441 = v154) != 0) )
      {
        PageHeader::GetIcxLsn(v152, &v661);
      }
      else
      {
        v661 = *(_QWORD *)(v152 + 40);
        v662 = *(_WORD *)(v152 + 48);
      }
      v1106 = &v661;
      v155 = (LSN *)((char *)v117 + 8444);
      v951 = (char *)v117 + 8444;
      v624 = 0;
      v625 = 0;
      v156 = (_DWORD *)((char *)v117 + 8456);
      v1107 = v156;
      v157 = *v156;
      v618 = *v156;
      v952 = v156;
      do
      {
        v828 = v157 & 0xFFFFFFFE;
        v624 = *(_QWORD *)v951;
        v625 = *((_DWORD *)v951 + 2);
        _InterlockedOr(v415, 0);
        v618 = *v952;
        v157 = v618;
      }
      while ( v828 != v618 );
      if ( (unsigned int)v624 >= (unsigned int)v661
        && ((_DWORD)v624 != (_DWORD)v661
         || HIDWORD(v624) >= HIDWORD(v661) && (HIDWORD(v624) != HIDWORD(v661) || (unsigned __int16)v625 >= v662)) )
      {
        goto LABEL_487;
      }
      if ( !*((_BYTE *)v429 + 27336) )
      {
        v1108 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v1109 = v1108[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v1110 = *(_QWORD *)(v1109 + 8);
        v1111 = *(_QWORD *)(v1110 + 96);
        if ( v1111 != *((_QWORD *)v429 + 1060) && !RecoveryUnit::IsParallelRedoThread(v429) )
          break;
      }
      if ( v450 )
        goto LABEL_502;
      v1133 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v1134 = v1133[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v1135 = *(_QWORD *)(v1134 + 8);
      v1136 = *(_QWORD *)(v1135 + 96);
      v117 = v429;
      if ( v1136 == *((_QWORD *)v429 + 1060) || RecoveryUnit::IsParallelRedoThread(v429) )
        goto LABEL_487;
      if ( !v639 )
        v639 = GetSETLSFromTlsMaybeNull();
      v1137 = &v647;
      v175 = **a2;
      v1138 = v175;
      v449 = 0;
      if ( *(_WORD *)(v175 + 36)
        && (((v176 = *(_BYTE *)(v175 + 1), v176 != 11) || *(_DWORD *)(v175 + 24) != 99)
         && (v176 != 8 && v176 != 9 || *(_DWORD *)(v175 + 24) != 99)
         || (v1139 = &v673,
             v1140 = v175 + 32,
             v673 = *(_DWORD *)(v175 + 32),
             v674 = *(_WORD *)(v175 + 36),
             !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v673, v174))
          ? (v177 = 0)
          : (v177 = 1),
            (v449 = v177) != 0) )
      {
        PageHeader::GetIcxLsn(v175, &v647);
        v178 = v648;
        v179 = v647;
      }
      else
      {
        v179 = *(_QWORD *)(v175 + 40);
        v647 = v179;
        v178 = *(_WORD *)(v175 + 48);
        v648 = v178;
      }
      v1141 = &v647;
      v726 = v179;
      v727 = v178;
      v728 = 0;
      v180 = *a2;
      if ( *a2 )
      {
        v1142 = (__int64)v180 + 98;
        v523 = *((_WORD *)v180 + 49);
        if ( (v523 & 0x400) != 0 && *((__int16 *)a2 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)a2);
LABEL_484:
          v179 = v726;
          v178 = v727;
          v117 = v429;
          goto LABEL_485;
        }
        v462 = *((__int16 *)a2 + 6);
        v605 = *a2;
        v1143 = (__int64)v605 + 98;
        v524 = *((_WORD *)v605 + 49);
        if ( (v524 & 8) != 0 )
        {
          if ( v462 == 3 )
          {
            v462 = 4;
LABEL_469:
            v1144 = (__int64)v605 + 100;
            v832 = *((_DWORD *)v605 + 25);
            if ( (v832 & 8) != 0 )
            {
              v181 = v605[18];
              if ( v181 )
              {
                v1145 = v605[18];
                if ( *(_QWORD *)(v181 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v181 + 1880), v605, (unsigned int)v462);
                }
              }
            }
            goto LABEL_473;
          }
          if ( v462 >= 2 )
            goto LABEL_469;
        }
LABEL_473:
        v581 = (unsigned __int8)byte_10317ABE5 >> 7;
        if ( byte_10317ABE5 < 0 )
        {
          v182 = (volatile signed __int32 *)v605 + 25;
          v1146 = (__int64)v605 + 100;
          v833 = *((_DWORD *)v605 + 25);
          if ( (v833 & 8) != 0 && v462 >= 3 )
          {
            v1147 = (__int64)v605 + 100;
            v834 = *v182;
            if ( (v834 & 0xC0000000) != 0x40000000 )
            {
              v183 = (void *)*v605;
              if ( *v605 )
              {
                v917[7] = 2;
                if ( VirtualProtect(v183, 0x2000u, 2u, v918) )
                {
                  _InterlockedAnd(v182, 0x3FFFFFFFu);
                  _InterlockedOr(v182, 0x40000000u);
                }
              }
            }
          }
        }
        v184 = v605;
        v185 = v462;
        LatchBase::ReleaseInternal(v605 + 19, (unsigned int)v462);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
        {
          v582 = (unsigned __int8)byte_10317AD4F >> 1;
          if ( (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v184, 0, v185);
        }
        *((_DWORD *)a2 + 3) &= 0xFFFF0000;
        *a2 = 0;
        goto LABEL_484;
      }
LABEL_485:
      v1148 = &v899;
      v899 = v179;
      v900 = v178;
      v1149 = &v850;
      v850 = v179;
      v851 = v178;
      v416 = 0;
      RecoveryMgr::WaitForRedoLsnToCatchUp(*v129, &v850, 4);
    }
    v863 = v155;
    v615.QuadPart = 0;
    v616 = 0;
    v1112 = v156;
    v158 = *v156;
    v630 = *v156;
    v159 = v155;
    v953 = &v155[1].HighPart;
    while ( 1 )
    {
      v829 = v158 & 0xFFFFFFFE;
      v615 = *v159;
      v616 = v159[1].LowPart;
      _InterlockedOr(v415, 0);
      v158 = *v953;
      v630 = v158;
      if ( v829 == v158 )
        break;
      v159 = v863;
    }
    v897 = v615;
    v160 = v616;
    v898 = v616;
    v161 = **a2;
    v1113 = v161;
    v453 = 0;
    if ( *(_WORD *)(v161 + 36)
      && ((v162 = *(_BYTE *)(v161 + 1), v162 != 11) && v162 != 8 && v162 != 9
       || *(_DWORD *)(v161 + 24) != 99
       || (v1114 = &v671,
           v1115 = v161 + 32,
           v671 = *(_DWORD *)(v161 + 32),
           v672 = *(_WORD *)(v161 + 36),
           !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v671, v159))
        ? (v163 = 0)
        : (v163 = 1),
          (v453 = v163) != 0) )
    {
      PageHeader::GetIcxLsn(v161, &v663);
      v164 = v664;
    }
    else
    {
      v663 = *(LSN *)(v161 + 40);
      v164 = *(_WORD *)(v161 + 48);
      v664 = v164;
    }
    if ( v615.LowPart < v663.LowPart
      || v615.LowPart == v663.LowPart
      && (v615.HighPart < (unsigned int)v663.HighPart || v615.HighPart == v663.HighPart && v160 < v164) )
    {
      v165 = *((_QWORD *)v429 + 214);
      v1116 = v165;
      LSN::FormatAsHexString(&v663, v1596, &v830);
      LSN::FormatAsHexString(&v897, v1597, &v830);
      v954 = 29;
      v955 = 0x10000;
      if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
      {
        v766 = 6;
        v1117 = v1487;
        v1487[0] = 0;
        v1487[1] = 6;
        v1488 = 0;
        v1489 = &v1492;
        v1490 = &v1516;
        v1517 = 0;
        v1518 = 0;
        v1491 = 0;
        v1519 = 0;
        v1118 = &v1492;
        v1492 = &v1520;
        v1493 = 52;
        v1494 = 5;
        v1495 = 0;
        v1119 = &v1496;
        v1496 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
        v1497 = 16;
        v1498 = 5;
        v1499 = 0;
        v1120 = &v1500;
        v1500 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
        v1501 = 16;
        v1502 = 6;
        v1503 = 0;
        v1121 = &v1504;
        v1504 = 0;
        v1505 = 0;
        v1506 = 7;
        v1507 = 0;
        v1122 = &v1508;
        v1508 = 0;
        v1509 = 0;
        v1510 = 8;
        v1511 = 0;
        v1123 = &v1512;
        v1512 = 0;
        v1513 = 0;
        v1514 = 9;
        v1515 = 0;
        v1520 = *(unsigned __int16 *)(v166 + 1720);
        v1521 = v482;
        v1522 = v481;
        v1523 = v422;
        v1124 = **a2;
        v1524 = *(_BYTE *)(v1124 + 1);
        v1125 = &v1496;
        v1496 = (GUID *)(v165 + 596);
        v1497 = 16;
        v1498 = 5;
        v1499 = 0;
        v1126 = &v1500;
        v1500 = (GUID *)(v165 + 580);
        v1501 = 16;
        v1502 = 6;
        v1503 = 0;
        v1127 = v1596;
        v167 = -1;
        do
          ++v167;
        while ( v1596[v167] );
        v917[4] = 2 * v167;
        v1128 = &v1504;
        v1504 = v1596;
        v1505 = 2 * v167;
        v1506 = 7;
        v1507 = 0;
        v1129 = v1597;
        v168 = -1;
        do
          ++v168;
        while ( v1597[v168] );
        v917[5] = 2 * v168;
        v1130 = &v1508;
        v1508 = v1597;
        v1509 = 2 * v168;
        v1510 = 8;
        v1511 = 0;
        v831 = 0;
        v169 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v165, &v831);
        v170 = (int *)v169;
        v1131 = v169;
        if ( v169 )
        {
          v171 = -1;
          do
            ++v171;
          while ( *(_WORD *)(v169 + 2 * v171) );
          v172 = 2 * v171;
        }
        else
        {
          v172 = 0;
        }
        v917[6] = v172;
        v173 = v1489 + 10;
        v1132 = v1489 + 10;
        v1489[10] = v170;
        *((_DWORD *)v173 + 2) = v172;
        *((_WORD *)v173 + 6) = 9;
        *((_WORD *)v173 + 7) = 0;
        XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v1486);
      }
    }
LABEL_487:
    if ( *((__int16 *)a2 + 6) >= 2 && v422 != -1 )
    {
      v186 = **a2;
      v1150 = v186;
      if ( *(_BYTE *)(v186 + 1) != v422 )
      {
        if ( v639 )
        {
          v1151 = v186;
          *((_QWORD *)v639 + 177) = v186;
        }
        if ( !UtilDbccGetContext() || !*((_QWORD *)UtilDbccGetContext() + 6) )
        {
          v835 = 0;
          goto LABEL_501;
        }
        v187 = *(_DWORD *)(*((_QWORD *)UtilDbccGetContext() + 6) + 12LL);
        v918[1] = v187;
        v189 = 0;
        if ( v187 <= 0xD )
        {
          v188 = 9792;
          if ( _bittest(&v188, v187) )
            v189 = 1;
        }
        v835 = v189;
        if ( !v189 )
LABEL_501:
          RaiseInconsistencyError(0, 8);
      }
    }
LABEL_502:
    v190 = 0;
    v901 = 0;
    v902 = 0;
    v903 = 0;
    if ( v719 || v717 || v718 )
    {
      v191 = *a2;
      v1152 = **a2;
      if ( (*(_BYTE *)(v1152 + 4) & 1) != 0 )
      {
        v1153 = (__int64)v191 + 98;
        v525 = *((_WORD *)v191 + 49);
        if ( (v525 & 0x400) != 0 && *((__int16 *)a2 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)a2);
LABEL_528:
          v1004 = 4194400;
          v1005 = 0;
          v1007 = 0;
          v1006 = 0;
          v1008 = 0;
          SOS_Task::Sleep(10, &v1004);
          v117 = v429;
          continue;
        }
        v463 = *((__int16 *)a2 + 6);
        v606 = *a2;
        v1154 = (__int64)v606 + 98;
        v526 = *((_WORD *)v606 + 49);
        if ( (v526 & 8) != 0 )
        {
          if ( v463 == 3 )
          {
            v463 = 4;
            goto LABEL_513;
          }
          if ( v463 >= 2 )
          {
LABEL_513:
            v1155 = (__int64)v606 + 100;
            v836 = *((_DWORD *)v606 + 25);
            if ( (v836 & 8) != 0 )
            {
              v192 = v606[18];
              if ( v192 )
              {
                v1156 = v606[18];
                if ( *(_QWORD *)(v192 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v192 + 1880), v606, (unsigned int)v463);
                }
              }
            }
          }
        }
        v583 = (unsigned __int8)byte_10317ABE5 >> 7;
        if ( byte_10317ABE5 < 0 )
        {
          v193 = (volatile signed __int32 *)v606 + 25;
          v1157 = (__int64)v606 + 100;
          v837 = *((_DWORD *)v606 + 25);
          if ( (v837 & 8) != 0 && v463 >= 3 )
          {
            v1158 = (__int64)v606 + 100;
            v838 = *v193;
            if ( (v838 & 0xC0000000) != 0x40000000 )
            {
              v194 = (void *)*v606;
              if ( *v606 )
              {
                v918[2] = 2;
                if ( VirtualProtect(v194, 0x2000u, 2u, v919) )
                {
                  _InterlockedAnd(v193, 0x3FFFFFFFu);
                  _InterlockedOr(v193, 0x40000000u);
                }
              }
            }
          }
        }
        v195 = v606;
        v196 = v463;
        LatchBase::ReleaseInternal(v606 + 19, (unsigned int)v463);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
        {
          v584 = (unsigned __int8)byte_10317AD4F >> 1;
          if ( (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v195, 0, v196);
        }
        *((_DWORD *)a2 + 3) &= 0xFFFF0000;
        *a2 = 0;
        goto LABEL_528;
      }
    }
    break;
  }
  v197 = v814;
  ++v814[1];
  v198 = *((_QWORD *)v197 + 11);
  if ( v198 )
    ++*(_DWORD *)(v198 + 4);
  if ( (*((_DWORD *)a2 + 3) & 0xFF000000) != 0 )
  {
    ++v814[2];
    v199 = *((_QWORD *)v197 + 11);
    if ( v199 )
      ++*(_DWORD *)(v199 + 8);
    if ( *((_BYTE *)a2 + 16) )
    {
      ++v814[3];
      v200 = *((_QWORD *)v197 + 11);
      if ( v200 )
        ++*(_DWORD *)(v200 + 12);
    }
  }
  if ( v985 )
  {
    v1159 = **a2;
    HoBtAccess::UpdateLatchWaitStats(v956, *(unsigned __int8 *)(v1159 + 1), v984, 0xFFFFFFFFLL);
  }
  v585 = 0;
  v586 = 1;
  v640 = 0;
  v641 = 0;
  v642 = 0;
  v201 = *v856;
  v957 = (__int64 (__fastcall ***)(_QWORD))v201;
  v202 = *a2;
  v203 = **a2;
  v1160 = v203;
  v204 = *(_QWORD *)(v201 + 8) + 960LL;
  v1161 = v204;
  v839 = 0;
  if ( *(_DWORD *)(v203 + 24) == *(_DWORD *)v204 )
  {
    v205 = *(_WORD *)(v203 + 6);
    v206 = *(_WORD *)(v204 + 4);
    if ( v205 == v206 || (unsigned __int16)(v205 | v206) <= 1u )
    {
      v839 = 1;
      goto LABEL_566;
    }
  }
  v1162 = v203;
  v702 = 0;
  v703 = 0;
  v704 = 0;
  v207 = *(_DWORD *)(v203 + 24);
  v702 = v207;
  v208 = *(_WORD *)(v203 + 6);
  v703 = v208;
  v640 = v207;
  v641 = v208;
  v642 = 0;
  v1163 = (__int64)v202 + 98;
  v527 = *((_WORD *)v202 + 49);
  if ( (v527 & 0x400) == 0 || *((__int16 *)a2 + 6) < 3 )
  {
    v464 = *((__int16 *)a2 + 6);
    v607 = *a2;
    v1164 = (__int64)v607 + 98;
    v528 = *((_WORD *)v607 + 49);
    if ( (v528 & 8) != 0 )
    {
      if ( v464 == 3 )
      {
        v464 = 4;
LABEL_550:
        v1165 = (__int64)v607 + 100;
        v840 = *((_DWORD *)v607 + 25);
        if ( (v840 & 8) != 0 )
        {
          v209 = v607[18];
          if ( v209 )
          {
            v1166 = v607[18];
            if ( *(_QWORD *)(v209 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v209 + 1880), v607, (unsigned int)v464);
            }
          }
        }
        goto LABEL_554;
      }
      if ( v464 >= 2 )
        goto LABEL_550;
    }
LABEL_554:
    v587 = (unsigned __int8)byte_10317ABE5 >> 7;
    if ( byte_10317ABE5 < 0 )
    {
      v210 = (volatile signed __int32 *)v607 + 25;
      v1167 = (__int64)v607 + 100;
      v841 = *((_DWORD *)v607 + 25);
      if ( (v841 & 8) != 0 && v464 >= 3 )
      {
        v1168 = (__int64)v607 + 100;
        v842 = *v210;
        if ( (v842 & 0xC0000000) != 0x40000000 )
        {
          v211 = (void *)*v607;
          if ( *v607 )
          {
            v919[1] = 2;
            if ( VirtualProtect(v211, 0x2000u, 2u, v920) )
            {
              _InterlockedAnd(v210, 0x3FFFFFFFu);
              _InterlockedOr(v210, 0x40000000u);
            }
          }
        }
      }
    }
    v212 = v607;
    v213 = v464;
    LatchBase::ReleaseInternal(v607 + 19, (unsigned int)v464);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
    {
      v588 = (unsigned __int8)byte_10317AD4F >> 1;
      if ( (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v212, 0, v213);
    }
    *((_DWORD *)a2 + 3) &= 0xFFFF0000;
    v190 = 0;
    *a2 = 0;
    goto LABEL_565;
  }
  PageRef::UnfixLatchOnly((PageRef *)a2);
LABEL_565:
  v1169 = &v705;
  v1170 = &v708;
  v214 = *(_QWORD *)(v201 + 8);
  v1171 = v214 + 960;
  v705 = *(_DWORD *)(v214 + 960);
  v706 = *(_WORD *)(v214 + 964);
  v707 = 0;
  v708 = v207;
  v709 = v208;
  v710 = 0;
  v215 = (**v957)(v957);
  RaiseWrongPageError(&v481, &v708, v215, &v705, *((_DWORD *)v856 + 4));
LABEL_566:
  SMOLockOrder::Add((SMOLockOrder *)v990, v823);
  SMOLockOrder::Add((SMOLockOrder *)v990, (struct PageRef *)a6);
  SMOLockOrder::Add((SMOLockOrder *)v990, (struct PageRef *)a2);
  v217 = *a6;
  v1172 = **a6;
  if ( *(_WORD *)(v1172 + 22) != 1 )
  {
    v993[0] = -1;
    v995 = 0;
    v994 = 0;
    v997 = 0;
    v998 = 0;
    v996 = 0;
    v1572[0] = 0;
    v1571 = 0;
    v358 = *v217;
    v1328 = v358;
    v560 = *(unsigned __int16 *)(v358 + 22) - 1;
    v930[1] = v560;
    v1329 = v358;
    v1584 = v560;
    if ( *(char *)(v358 + 2) >= 0 )
    {
      v359 = 0;
      v822 = 0;
      v360 = 3;
      goto LABEL_992;
    }
    _mm_prefetch((const char *)(v358 + 96), 0);
    if ( v1573 )
    {
      v359 = v1577;
      v822 = v1577;
      if ( v1577 )
      {
LABEL_944:
        v448 = 0;
        if ( *(_WORD *)(v358 + 36)
          && ((v361 = *(_BYTE *)(v358 + 1), v361 != 11) && v361 != 8 && v361 != 9
           || *(_DWORD *)(v358 + 24) != 99
           || (v1336 = &v683,
               v1337 = v358 + 32,
               v683 = *(_DWORD *)(v358 + 32),
               v684 = *(_WORD *)(v358 + 36),
               !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v683, v216))
            ? (v362 = 0)
            : (v362 = 1),
              (v448 = v362) != 0) )
        {
          PageHeader::GetIcxLsn(v358, &v594);
          v363 = v595;
        }
        else
        {
          v594 = *(_QWORD *)(v358 + 40);
          v363 = *(_WORD *)(v358 + 48);
          v595 = v363;
        }
        v1338 = &v594;
        v1339 = v358 + 32;
        v364 = (unsigned __int8 *)(v358 + 96);
        v1340 = v358 + 96;
        v1341 = v359;
        if ( v358 + 96 == *(_QWORD *)v359 )
        {
          v1342 = (char *)v359 + 96;
          if ( v363 == *((_WORD *)v359 + 52) && v594 == *((_QWORD *)v359 + 12) )
            v1343 = (char *)v359 + 108;
        }
        *(_QWORD *)v359 = v364;
        v1344 = (char *)v359 + 96;
        v365 = v595;
        v773 = v595;
        v366 = HIDWORD(v594);
        v930[2] = HIDWORD(v594);
        v930[4] = v594;
        *((_DWORD *)v359 + 24) = v594;
        *((_DWORD *)v359 + 25) = v366;
        *((_WORD *)v359 + 52) = v365;
        v1345 = (char *)v359 + 108;
        *((_DWORD *)v359 + 27) = *(_DWORD *)(v358 + 32);
        *((_WORD *)v359 + 56) = *(_WORD *)(v358 + 36);
        *((_WORD *)v359 + 57) = 0;
        v367 = *v364;
        v774 = *v364;
        v876 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * v367);
        v877 = word_102883984[3 * v367];
        v780 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * v367);
        v368 = word_102883984[3 * v367];
        v425 = v368;
        v781 = v368;
        v369 = (unsigned __int8 *)(v358 + 99);
        v1346 = v358 + 99;
        v1347 = (char *)v359 + 16;
        *((_WORD *)v359 + 8) = -1;
        *((_QWORD *)v359 + 3) = 0;
        *((_DWORD *)v359 + 5) = 0;
        *(_QWORD *)((char *)v359 + 46) = 0;
        *((_QWORD *)v359 + 7) = 0;
        *((_QWORD *)v359 + 4) = 0;
        v370 = (char *)v359 + 72;
        v1348 = (char *)v359 + 72;
        *((_QWORD *)v359 + 9) = 0;
        *((_QWORD *)v359 + 10) = 0;
        *((_WORD *)v359 + 44) = 0;
        if ( (**(_BYTE **)v359 & 2) != 0 )
        {
          v371 = &v364[v368];
          v1349 = &v364[v368];
          v1350 = (char *)v359 + 16;
          v372 = v364[v368] & 1;
          v775 = v372;
          *((_WORD *)v359 + 8) = v372;
          v373 = (_WORD *)((char *)v359 + 18);
          if ( v372 )
          {
            v1353 = (char *)v359 + 18;
            *((_QWORD *)v359 + 3) = v371;
            v375 = *v371;
            switch ( *v371 & 0x1C )
            {
              case 0:
              case 0xC:
              case 0x10:
              case 0x14:
              case 0x18:
              case 0x1C:
                v376 = v371 + 1;
                v1354 = v376;
                v377 = *v376;
                v360 = 3;
                if ( (v377 & 0x80u) != 0 )
                {
                  v379 = *(_WORD *)v376;
                  *v373 = *(_WORD *)v376;
                  *v373 = HIBYTE(v379) | ((v379 & 0x7F) << 8);
                  *((_WORD *)v359 + 20) = 3;
                  v378 = 3;
                }
                else
                {
                  *v373 = v377;
                  *((_WORD *)v359 + 20) = 2;
                  v378 = 2;
                }
                *((_WORD *)v359 + 22) = v378 + (((unsigned int)*((unsigned __int16 *)v359 + 9) + 1) >> 1);
                v380 = (unsigned __int16)*v373;
                if ( v380 > 0x1E )
                  *((_WORD *)v359 + 21) = (int)(v380 - 1) / 30;
                else
                  *((_WORD *)v359 + 21) = 0;
                *((_DWORD *)v359 + 5) = 0;
                *((_DWORD *)v359 + 16) = 0;
                goto LABEL_983;
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
                utassert_fail(
                  1u,
                  "FALSE",
                  "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                  207,
                  "Invalid switch value");
                v364 = (unsigned __int8 *)(v358 + 96);
                goto LABEL_982;
              case 4:
                v1356 = &v364[v368];
                v1357 = &v364[v368];
                if ( (v375 & 0x1C) == 4 && (v375 & 2) != 0 )
                {
                  *((_QWORD *)v359 + 3) = 0;
                  *((_DWORD *)v359 + 5) = 0;
                  *((_WORD *)v359 + 20) = 0;
                  *v373 = 0;
                  *((_WORD *)v359 + 21) = 0;
                  *((_WORD *)v359 + 22) = 0;
                  *((_WORD *)v359 + 23) = 0;
                  *((_WORD *)v359 + 24) = 0;
                  *((_WORD *)v359 + 25) = 0;
                  *((_WORD *)v359 + 26) = 0;
                  *((_WORD *)v359 + 27) = 0;
                  *((_QWORD *)v359 + 4) = 0;
                  *((_DWORD *)v359 + 16) = 0;
                  *((_QWORD *)v359 + 7) = 0;
                  *((_QWORD *)v359 + 3) = v371;
                  *((_DWORD *)v359 + 5) = 15;
                  *((_DWORD *)v359 + 16) = 0;
                  *((_DWORD *)v359 + 16) = 1;
                }
                else
                {
                  *((_QWORD *)v359 + 3) = 0;
                  *((_DWORD *)v359 + 5) = 0;
                  *((_WORD *)v359 + 20) = 0;
                  *v373 = 0;
                  *((_WORD *)v359 + 21) = 0;
                  *((_WORD *)v359 + 22) = 0;
                  *((_WORD *)v359 + 23) = 0;
                  *((_WORD *)v359 + 24) = 0;
                  *((_WORD *)v359 + 25) = 0;
                  *((_WORD *)v359 + 26) = 0;
                  *((_WORD *)v359 + 27) = 0;
                  *((_QWORD *)v359 + 4) = 0;
                  *((_DWORD *)v359 + 16) = 0;
                  *((_QWORD *)v359 + 7) = 0;
                  *((_QWORD *)v359 + 3) = v371;
                  *((_DWORD *)v359 + 5) = 1;
                  *((_DWORD *)v359 + 16) = 0;
                }
                goto LABEL_982;
              case 8:
                v1355 = &v364[v368];
                *((_QWORD *)v359 + 3) = 0;
                *((_DWORD *)v359 + 5) = 0;
                *((_WORD *)v359 + 20) = 0;
                *v373 = 0;
                *((_WORD *)v359 + 21) = 0;
                *((_WORD *)v359 + 22) = 0;
                *((_WORD *)v359 + 23) = 0;
                *((_WORD *)v359 + 24) = 0;
                *((_WORD *)v359 + 25) = 0;
                *((_WORD *)v359 + 26) = 0;
                *((_WORD *)v359 + 27) = 0;
                *((_QWORD *)v359 + 4) = 0;
                *((_DWORD *)v359 + 16) = 0;
                *((_QWORD *)v359 + 7) = 0;
                *((_QWORD *)v359 + 3) = v371;
                *((_DWORD *)v359 + 5) = 9;
                *((_DWORD *)v359 + 16) = 0;
LABEL_982:
                v360 = 3;
LABEL_983:
                *((_QWORD *)v359 + 7) = 0;
                *((_QWORD *)v359 + 4) = 0;
                v370 = (char *)v359 + 72;
                LOWORD(v368) = v425;
                v369 = v364 + 3;
                break;
            }
            goto LABEL_985;
          }
          v558 = 0;
          v1351 = (char *)v359 + 18;
          *((_QWORD *)v359 + 3) = v371;
          *((_DWORD *)v359 + 5) = 0;
          *(_DWORD *)((char *)v359 + 54) = 0;
          v374 = (_BYTE *)*((_QWORD *)v359 + 3);
          v1352 = v374;
          switch ( *v374 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v190 = *((unsigned __int16 *)v371 + 1);
              v558 = v190;
              if ( (unsigned int)(v190 - 1) > 0x1F9D )
              {
                RaiseInconsistencyError(v374, 6);
                v364 = (unsigned __int8 *)(v358 + 96);
              }
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
              v364 = (unsigned __int8 *)(v358 + 96);
              break;
            case 4:
              v190 = 9;
              goto LABEL_965;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v190 = 1;
LABEL_965:
              v558 = v190;
              break;
          }
          *((_DWORD *)v359 + 8) = v190;
          *(_QWORD *)((char *)v359 + 46) = 0;
          v370 = (char *)v359 + 72;
          LOWORD(v368) = v425;
          v369 = v364 + 3;
        }
        v360 = 3;
LABEL_985:
        if ( (**(_BYTE **)v359 & 4) != 0 )
        {
          if ( HIWORD(v780) )
            v381 = *(unsigned __int16 *)&v369[2 * SHIWORD(v780) - 2];
          else
            v381 = (__int16)v368;
          v382 = &v364[v381];
          v1358 = v382;
          v1359 = v370;
          *(_QWORD *)v370 = v382;
          v776 = *(_WORD *)v382;
          v383 = v776;
          *((_QWORD *)v370 + 1) = v382 + 2;
          *((_WORD *)v370 + 8) = 2 * (v383 + 1);
        }
        v384 = (PageComprInfoCache *)*((_QWORD *)v359 + 1);
        if ( v384 )
          PageComprInfoCache::Init(v384, v359);
LABEL_992:
        v385 = *(unsigned __int16 *)(v358 + 14);
        v930[6] = v385;
        v386 = (char *)(v358 + *(unsigned __int16 *)(v358 + 2 * (4095LL - v560)));
        v1360 = v386;
        v339 = (*v386 & 1) == 0;
        v777 = *v386 & 1;
        v1573 = v777;
        if ( v339 )
        {
          v559 = v385;
          v1361 = (__int16 *)&v1574;
          v1576 = v386;
          v1575 = 0;
          *(_DWORD *)v1582 = 0;
          v1362 = v386;
          switch ( *v386 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v385 = *((unsigned __int16 *)v386 + 1);
              v559 = v385;
              if ( v385 - 1 > 0x1F9D )
                RaiseInconsistencyError(v386, 6);
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
              v385 = 9;
              v559 = 9;
              break;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v385 = 1;
              v559 = 1;
              break;
          }
          LODWORD(v1577) = v385;
          v1581 = v358 + 0x2000;
        }
        else
        {
          v1363 = (__int16 *)&v1574;
          v1576 = v386;
          v387 = *v386;
          switch ( byte_1012B3FB8[*v386 & 0x1C] )
          {
            case 0:
              v388 = v386 + 1;
              v1364 = v388;
              if ( *v388 < 0 )
              {
                v389 = HIBYTE(*(_WORD *)v388) | ((*(_WORD *)v388 & 0x7F) << 8);
                v1574 = v389;
                v1578 = 3;
              }
              else
              {
                v389 = (unsigned __int8)*v388;
                v1574 = v389;
                v1578 = 2;
                v360 = 2;
              }
              v1580 = v360 + (((unsigned int)v389 + 1) >> 1);
              if ( v389 > 0x1Eu )
                v1579 = (v389 - 1) / 30;
              else
                v1579 = 0;
              v1575 = 0;
              v1583 = 0;
              break;
            case 1:
              v1366 = v386;
              v1367 = v386;
              if ( (v387 & 0x1C) == 4 && (v387 & 2) != 0 )
              {
                v1578 = 0;
                v1574 = 0;
                v1579 = 0;
                v1580 = 0;
                v1581 = 0;
                memset(v1582, 0, sizeof(v1582));
                v1577 = 0;
                v1576 = v386;
                v1575 = 15;
                v1583 = 1;
              }
              else
              {
                v1578 = 0;
                v1574 = 0;
                v1579 = 0;
                v1580 = 0;
                v1581 = 0;
                memset(v1582, 0, sizeof(v1582));
                v1577 = 0;
                v1576 = v386;
                v1575 = 1;
                v1583 = 0;
              }
              break;
            case 2:
              v1365 = v386;
              v1578 = 0;
              v1574 = 0;
              v1579 = 0;
              v1580 = 0;
              v1581 = 0;
              memset(v1582, 0, sizeof(v1582));
              v1577 = 0;
              v1576 = v386;
              v1575 = 9;
              v1583 = 0;
              break;
            case 3:
              utassert_fail(
                1u,
                "FALSE",
                "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                207,
                "Invalid switch value");
              break;
          }
          *(_QWORD *)&v1582[2] = v358 + 0x2000;
          v1577 = v359;
        }
        *(_QWORD *)&v1571 = &v1573;
        v343 = v619;
        v1368 = (struct RecoveryUnit **)*((_QWORD *)v619 + 34);
        v931 = *((_DWORD *)v619 + 64);
        v390 = v864;
        v346 = (__int16 *)v865;
        PageRef::InsertRows(
          (BUF **)v865,
          v864,
          (const struct AllocUnitId *)&v483,
          0,
          1,
          (struct RecordHolder *)&v1571,
          v931,
          0,
          v1368,
          0,
          0,
          0);
        v1369 = *((_QWORD *)v343 + 34);
        v932 = *((_DWORD *)v343 + 64);
        v345 = (unsigned __int16 *)v866;
        PageRef::DeleteRows(v866, v390, &v483, (unsigned int)v560, 1, v932, 0, v1369, 0, 0, 0, 0, 0);
        v782 = 0;
        v783 = 0;
        v1370 = **(struct Page ***)v346;
        BTreeMgr::CreateParentRecord(v343, v1370, (const struct PageId *)&v782, (struct Record *)v993, v1600, 0xA58u);
        *(_QWORD *)&v1572[0] = v993;
        v1371 = *((_QWORD *)v343 + 34);
        v560 = *((_DWORD *)v343 + 64);
        PageRef::DeleteRows(v823, v390, &v483, v621, 1, v560, 0, v1371, 0, 0, 0, 0, 0);
        v1372 = (struct RecoveryUnit **)*((_QWORD *)v343 + 34);
        v933 = *((_DWORD *)v343 + 64);
        PageRef::InsertRows(
          (BUF **)v823,
          v390,
          (const struct AllocUnitId *)&v483,
          v621,
          1,
          (struct RecordHolder *)v1572,
          v933,
          0,
          v1372,
          0,
          0,
          0);
        SMOLockOrder::Clear((SMOLockOrder *)v990);
        if ( !v426 )
          goto LABEL_1018;
        v1373 = (char *)v426 + 98;
        v563 = *((_WORD *)v426 + 49);
        if ( (v563 & 0x400) != 0 && (__int16)v428 >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)&v426);
LABEL_1018:
          v426 = *(struct Page ***)v346;
          v428 = (unsigned __int16)v346[6] | v428 & 0xFFFF0000;
          *(_QWORD *)v346 = 0;
          *((_DWORD *)v346 + 3) &= 0xFFFF0000;
          goto LABEL_1019;
        }
        v472 = (__int16)v428;
        v1374 = v426;
        v1375 = (char *)v426 + 98;
        v544 = *((_WORD *)v426 + 49);
        if ( (v544 & 8) != 0 )
        {
          if ( v472 == 3 )
          {
            v472 = 4;
LABEL_1028:
            v1376 = (char *)v426 + 100;
            v753 = *((_DWORD *)v426 + 25);
            if ( (v753 & 8) != 0 )
            {
              v392 = v426[18];
              if ( v392 )
              {
                v1377 = v426[18];
                if ( *((_QWORD *)v392 + 235) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*((_QWORD *)v392 + 235), v426, (unsigned int)v472);
                }
              }
            }
            goto LABEL_1032;
          }
          if ( v472 >= 2 )
            goto LABEL_1028;
        }
LABEL_1032:
        v500 = (unsigned __int8)byte_10317ABE5 >> 7;
        if ( byte_10317ABE5 < 0 )
        {
          v393 = (volatile signed __int32 *)v426 + 25;
          v1378 = (char *)v426 + 100;
          v754 = *((_DWORD *)v426 + 25);
          if ( (v754 & 8) != 0 && v472 >= 3 )
          {
            v1379 = (char *)v426 + 100;
            v755 = *v393;
            if ( (v755 & 0xC0000000) != 0x40000000 )
            {
              v394 = *v426;
              if ( *v426 )
              {
                v934 = 2;
                if ( VirtualProtect(v394, 0x2000u, 2u, v935) )
                {
                  _InterlockedAnd(v393, 0x3FFFFFFFu);
                  _InterlockedOr(v393, 0x40000000u);
                }
              }
            }
          }
        }
        v395 = v426;
        v396 = v472;
        LatchBase::ReleaseInternal(v426 + 19, (unsigned int)v472);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
        {
          v501 = (unsigned __int8)byte_10317AD4F >> 1;
          if ( (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v395, 0, v396);
        }
        v428 &= 0xFFFF0000;
        v426 = 0;
        goto LABEL_1018;
      }
    }
    else
    {
      v822 = 0;
    }
    v1330 = &v1585;
    v1588 = 0;
    v1590 = 0u;
    v1591 = 0;
    v1593 = 0;
    v1331 = &v1585;
    v1585 = 0;
    v1332 = &v1586;
    v1586 = 0xFFFFu;
    v1589 = 0;
    memset(v1587, 0, sizeof(v1587));
    v1333 = (char *)&v1590 + 8;
    v1334 = &v1592;
    v1592 = 0u;
    v1335 = (char *)&v1592 + 12;
    v359 = (struct PageComprInfo *)&v1585;
    v822 = (struct PageComprInfo *)&v1585;
    goto LABEL_944;
  }
  v872 = 0;
  v873 = 0;
  v218 = **a2;
  v1173 = v218;
  v1174 = v218 + 16;
  v219 = *(_DWORD *)(v218 + 16);
  v874 = v219;
  v220 = *(unsigned __int16 *)(v218 + 20);
  v875 = *(_WORD *)(v218 + 20);
  if ( !v219 && !(_WORD)v220 )
    goto LABEL_835;
  v1175 = v218;
  v1176 = v218 + 16;
  v479 = v219;
  v480 = *(_WORD *)(v218 + 20);
  v867 = (__int64 *)*((_QWORD *)v619 + 1);
  v819 = (_DWORD *)*((_QWORD *)v619 + 2);
  v720 = 0;
  v721 = 0;
  v722 = 0;
  v967 = *v867;
  v988 = 0;
  v989 = 0;
  v221 = *(RecoveryUnit **)(v967 + 32);
  v430 = v221;
  v1177 = v967 + 20;
  v222 = (*(unsigned int *)(v967 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v967 + 24) << 32)) << 16;
  v1178 = v222;
  v223 = *((_QWORD *)v221 + 250);
  if ( v223 != v222 || (unsigned __int64)(v223 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v454 = 0;
    v224 = *((_QWORD *)v221 + 251);
    if ( v224 == v222 && (unsigned __int64)(v224 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v455 = 1;
      goto LABEL_588;
    }
    v455 = 0;
    v1179 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v225 = v1179[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v1180 = v225;
    v226 = *(_QWORD **)(v225 + 256);
    v958 = v226;
    if ( !v226 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v226 = *(_QWORD **)(v225 + 256);
      v958 = v226;
    }
    v1181 = v226;
    v227 = __rdtsc();
    v1182 = v227;
    v228 = v226[104];
    if ( v227 <= v228 && (v228 == 0x7FFFFFFFFFFFFFFFLL || v228 - v227 <= *(_QWORD *)(v226[76] + 3568LL)) )
    {
      v959 = v226[75];
      v1183 = v959 + 188;
      if ( (*(_DWORD *)(v959 + 188) & 4) != 0 )
      {
        v229 = *(_QWORD *)(v959 + 152);
        v1184 = v229;
        if ( (*(_BYTE *)(v229 + 616) & 1) == 0 && (*(_DWORD *)(v229 + 800) & 0x180) == 0 )
        {
          v631 = 2;
LABEL_586:
          LOBYTE(v229) = 124;
          RaiseExecutionAbortedError(v229);
          goto LABEL_587;
        }
      }
      v631 = 0;
    }
    else
    {
      v631 = SOS_Task::Sleep(0, yieldWait);
      if ( v631 == 2 )
        goto LABEL_586;
    }
LABEL_587:
    v221 = v430;
    goto LABEL_588;
  }
  v454 = 1;
LABEL_588:
  v904 = 0;
  v905 = 0;
  v906 = 0;
  v444 = 0;
  v423 = -1;
  while ( 2 )
  {
    v857 = (unsigned int *)v987;
    v1568 = 0;
    v1569 = 0;
    v589 = CommonGlobalState::m_CollectingStatistics;
    if ( !CommonGlobalState::m_CollectingStatistics )
      goto LABEL_595;
    v590 = (unsigned __int8)byte_10317ABE6 >> 7;
    if ( byte_10317ABE6 < 0 )
      goto LABEL_595;
    v843 = 0;
    v1185 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v1186 = (__int64 *)(v1185[SystemThread_TlsIndex] + SystemThread_TlsOffset);
    v230 = *v1186;
    v1187 = v230;
    if ( v230 && (v231 = **(struct CSessionTraceFlags ***)(v230 + 56), (v1188 = v231) != 0) )
    {
      v960 = v231;
      v843 = CSessionTraceFlags::CheckSessionTraceInternal(v231, 0x337u);
      if ( v843 )
      {
        v221 = v430;
        goto LABEL_595;
      }
    }
    else
    {
      v960 = 0;
    }
    v1189 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v1190 = v1189[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v234 = *(_QWORD *)(v1190 + 8);
    v1191 = v234;
    v221 = v430;
    if ( v234 )
      v232 = *(struct SEInternalTLS **)(v234 + 96);
    else
LABEL_595:
      v232 = 0;
    v643 = v232;
    v233 = (_QWORD *)((char *)v221 + 1832);
    v961 = *((_QWORD *)v221 + 229);
    while ( 2 )
    {
      v632 = 0;
      if ( v417 )
      {
        v1192 = (__int64)v417 + 98;
        v529 = *((_WORD *)v417 + 49);
        if ( (v529 & 0x400) != 0 && (__int16)v419 >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)&v417);
          goto LABEL_623;
        }
        v465 = (__int16)v419;
        v815 = v417;
        v1193 = (__int64)v417 + 98;
        v530 = *((_WORD *)v417 + 49);
        if ( (v530 & 8) != 0 )
        {
          if ( v465 == 3 )
          {
            v465 = 4;
            goto LABEL_608;
          }
          if ( v465 >= 2 )
          {
LABEL_608:
            v1194 = (__int64)v417 + 100;
            v844 = *((_DWORD *)v417 + 25);
            if ( (v844 & 8) != 0 )
            {
              v235 = v417[18];
              if ( v235 )
              {
                v1195 = v417[18];
                if ( *(_QWORD *)(v235 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v235 + 1880), v417, (unsigned int)v465);
                }
              }
            }
          }
        }
        v591 = (unsigned __int8)byte_10317ABE5 >> 7;
        if ( byte_10317ABE5 < 0 )
        {
          v236 = (volatile signed __int32 *)v815 + 25;
          v1196 = (__int64)v815 + 100;
          v845 = *((_DWORD *)v815 + 25);
          if ( (v845 & 8) != 0 && v465 >= 3 )
          {
            v1197 = (__int64)v815 + 100;
            v846 = *v236;
            if ( (v846 & 0xC0000000) != 0x40000000 )
            {
              v237 = (void *)*v815;
              if ( *v815 )
              {
                v920[1] = 2;
                if ( VirtualProtect(v237, 0x2000u, 2u, v921) )
                {
                  _InterlockedAnd(v236, 0x3FFFFFFFu);
                  _InterlockedOr(v236, 0x40000000u);
                }
              }
            }
          }
        }
        v238 = v815;
        v239 = v465;
        LatchBase::ReleaseInternal(v815 + 19, (unsigned int)v465);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
        {
          v596 = (unsigned __int8)byte_10317AD4F >> 1;
          if ( (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v238, 0, v239);
        }
        v419 &= 0xFFFF0000;
        v417 = 0;
LABEL_623:
        v221 = v430;
      }
      if ( *v233 )
      {
        PageRef::CatchupPageRedos((PageRef *)&v417, (const struct PageId *)&v479, v221);
        if ( v417 )
        {
          v1198 = (__int64)v417 + 98;
          v531 = *((_WORD *)v417 + 49);
          if ( (v531 & 0x400) != 0 && (__int16)v419 >= 3 )
          {
            PageRef::UnfixLatchOnly((PageRef *)&v417);
            goto LABEL_648;
          }
          v466 = (__int16)v419;
          v816 = v417;
          v1199 = (__int64)v417 + 98;
          v532 = *((_WORD *)v417 + 49);
          if ( (v532 & 8) != 0 )
          {
            if ( v466 == 3 )
            {
              v466 = 4;
              goto LABEL_633;
            }
            if ( v466 >= 2 )
            {
LABEL_633:
              v1200 = (__int64)v417 + 100;
              v847 = *((_DWORD *)v417 + 25);
              if ( (v847 & 8) != 0 )
              {
                v240 = v417[18];
                if ( v240 )
                {
                  v1201 = v417[18];
                  if ( *(_QWORD *)(v240 + 1880) )
                  {
                    _mm_lfence();
                    DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v240 + 1880), v417, (unsigned int)v466);
                  }
                }
              }
            }
          }
          v486 = (unsigned __int8)byte_10317ABE5 >> 7;
          if ( byte_10317ABE5 < 0 )
          {
            v241 = (volatile signed __int32 *)v816 + 25;
            v1202 = (__int64)v816 + 100;
            v848 = *((_DWORD *)v816 + 25);
            if ( (v848 & 8) != 0 && v466 >= 3 )
            {
              v1203 = (__int64)v816 + 100;
              v849 = *v241;
              if ( (v849 & 0xC0000000) != 0x40000000 )
              {
                v242 = (void *)*v816;
                if ( *v816 )
                {
                  v921[1] = 2;
                  if ( VirtualProtect(v242, 0x2000u, 2u, v922) )
                  {
                    _InterlockedAnd(v241, 0x3FFFFFFFu);
                    _InterlockedOr(v241, 0x40000000u);
                  }
                }
              }
            }
          }
          v243 = v816;
          v244 = v466;
          LatchBase::ReleaseInternal(v816 + 19, (unsigned int)v466);
          if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
          {
            v487 = (unsigned __int8)byte_10317AD4F >> 1;
            if ( (byte_10317AD4F & 2) != 0 )
              BUF::TraceLatchAcquireRelease(v243, 0, v244);
          }
          v419 &= 0xFFFF0000;
          v417 = 0;
LABEL_648:
          v221 = v430;
        }
      }
      RecoveryUnit::PrePageUpdateHint(v221, (const struct PageId *)&v479);
      LODWORD(v416) = 4;
      v245 = (_QWORD *)BPool::Get(qword_10317B628, v221, &v479, &v632, v416, v857);
      v417 = v245;
      v246 = v419 & 0xFFFF0000 | 4;
      v419 = v246;
      if ( v643 )
      {
        v247 = *v245;
        v1204 = v247;
        v248 = (_DWORD *)((char *)v643 + 1280);
        v1205 = v248;
        v249 = &v248[2 * (*v248 & 0xF) + 2];
        v1206 = v249;
        if ( *v249 != v247 )
        {
          *v249 = v247;
          ++*(_QWORD *)v248;
          v246 = v419;
        }
      }
      v419 = v246 & 0xFFFFFF | (((v632 >> 3) & 1) << 24);
      v420 = v420 & 0xFFFFFF00 | (v632 >> 4) & 1;
      v250 = v961;
      if ( v961 )
      {
        if ( v643 )
        {
          if ( v643 == *((struct SEInternalTLS **)v221 + 903) )
          {
            v251 = (v246 & 0xFFFFFF | (((v632 >> 3) & 1) << 24)) >> 24;
            v922[1] = v251;
            v252 = (_QWORD *)(v961 + 22968);
            v1207 = v961 + 22968;
            ++*(_QWORD *)(v961 + 23336);
            v253 = v857;
            if ( v857[1] )
            {
              ++*(_QWORD *)(v250 + 23344);
              v252[48] += *v253;
              if ( v251 )
              {
                ++v252[49];
                v252[50] += *v253;
              }
            }
          }
        }
      }
      if ( !RecoveryUnit::IsRbIoDb(v221) || !*((_BYTE *)v221 + 8272) )
        goto LABEL_756;
      if ( !v479 || (v880 = 9, v881 = 1, v479 == 9) && v480 == 1 )
      {
        v446 = 1;
        goto LABEL_756;
      }
      v446 = 0;
      v255 = *v417;
      v1208 = v255;
      v442 = 0;
      if ( *(_WORD *)(v255 + 36)
        && ((v256 = *(_BYTE *)(v255 + 1), v256 != 11) && v256 != 8 && v256 != 9
         || *(_DWORD *)(v255 + 24) != 99
         || (v1209 = &v679,
             v1210 = v255 + 32,
             v679 = *(_DWORD *)(v255 + 32),
             v680 = *(_WORD *)(v255 + 36),
             !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v679, v254))
          ? (v257 = 0)
          : (v257 = 1),
            (v442 = v257) != 0) )
      {
        PageHeader::GetIcxLsn(v255, &v653);
      }
      else
      {
        v653 = *(_QWORD *)(v255 + 40);
        v654 = *(_WORD *)(v255 + 48);
      }
      v1211 = &v653;
      v258 = (LSN *)((char *)v221 + 8444);
      v962 = (char *)v221 + 8444;
      v626 = 0;
      v627 = 0;
      v259 = (_DWORD *)((char *)v221 + 8456);
      v1212 = v259;
      v260 = *v259;
      v633 = *v259;
      v963 = v259;
      do
      {
        v732 = v260 & 0xFFFFFFFE;
        v626 = *(_QWORD *)v962;
        v627 = *((_DWORD *)v962 + 2);
        _InterlockedOr(v415, 0);
        v633 = *v963;
        v260 = v633;
      }
      while ( v732 != v633 );
      if ( (unsigned int)v626 >= (unsigned int)v653
        && ((_DWORD)v626 != (_DWORD)v653
         || HIDWORD(v626) >= HIDWORD(v653) && (HIDWORD(v626) != HIDWORD(v653) || (unsigned __int16)v627 >= v654)) )
      {
        goto LABEL_756;
      }
      if ( *((_BYTE *)v430 + 27336)
        || (v1213 = NtCurrentTeb()->ThreadLocalStoragePointer,
            v1214 = v1213[SystemThread_TlsIndex] + SystemThread_TlsOffset,
            v1215 = *(_QWORD *)(v1214 + 8),
            v1216 = *(_QWORD *)(v1215 + 96),
            v1216 == *((_QWORD *)v430 + 1060))
        || RecoveryUnit::IsParallelRedoThread(v430) )
      {
        if ( v444 )
          goto LABEL_770;
        v1238 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v1239 = v1238[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v1240 = *(_QWORD *)(v1239 + 8);
        v1241 = *(_QWORD *)(v1240 + 96);
        v221 = v430;
        if ( v1241 == *((_QWORD *)v430 + 1060) || RecoveryUnit::IsParallelRedoThread(v430) )
          goto LABEL_756;
        if ( !v643 )
          v643 = GetSETLSFromTlsMaybeNull();
        v1242 = &v649;
        v278 = *v417;
        v1243 = v278;
        v445 = 0;
        if ( *(_WORD *)(v278 + 36)
          && ((v279 = *(_BYTE *)(v278 + 1), v279 != 11) && v279 != 8 && v279 != 9
           || *(_DWORD *)(v278 + 24) != 99
           || (v1244 = &v685,
               v1245 = v278 + 32,
               v685 = *(_DWORD *)(v278 + 32),
               v686 = *(_WORD *)(v278 + 36),
               !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v685, v277))
            ? (v280 = 0)
            : (v280 = 1),
              (v445 = v280) != 0) )
        {
          PageHeader::GetIcxLsn(v278, &v649);
          v281 = v650;
          v282 = v649;
        }
        else
        {
          v282 = *(_QWORD *)(v278 + 40);
          v649 = v282;
          v281 = *(_WORD *)(v278 + 48);
          v650 = v281;
        }
        v1246 = &v649;
        v729 = v282;
        v730 = v281;
        v731 = 0;
        if ( !v417 )
          goto LABEL_754;
        v1247 = (__int64)v417 + 98;
        v533 = *((_WORD *)v417 + 49);
        if ( (v533 & 0x400) != 0 && (__int16)v419 >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)&v417);
LABEL_753:
          v282 = v729;
          v281 = v730;
          v221 = v430;
LABEL_754:
          v1253 = &v882;
          v882 = v282;
          v883 = v281;
          v1254 = &v854;
          v854 = v282;
          v855 = v281;
          v416 = 0;
          RecoveryMgr::WaitForRedoLsnToCatchUp(*v233, &v854, 4);
          continue;
        }
        v467 = (__int16)v419;
        v817 = v417;
        v1248 = (__int64)v417 + 98;
        v534 = *((_WORD *)v417 + 49);
        if ( (v534 & 8) != 0 )
        {
          if ( v467 == 3 )
          {
            v467 = 4;
LABEL_738:
            v1249 = (__int64)v417 + 100;
            v736 = *((_DWORD *)v417 + 25);
            if ( (v736 & 8) != 0 )
            {
              v283 = v417[18];
              if ( v283 )
              {
                v1250 = v417[18];
                if ( *(_QWORD *)(v283 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v283 + 1880), v417, (unsigned int)v467);
                }
              }
            }
            goto LABEL_742;
          }
          if ( v467 >= 2 )
            goto LABEL_738;
        }
LABEL_742:
        v488 = (unsigned __int8)byte_10317ABE5 >> 7;
        if ( byte_10317ABE5 < 0 )
        {
          v284 = (volatile signed __int32 *)v817 + 25;
          v1251 = (__int64)v817 + 100;
          v737 = *((_DWORD *)v817 + 25);
          if ( (v737 & 8) != 0 && v467 >= 3 )
          {
            v1252 = (__int64)v817 + 100;
            v738 = *v284;
            if ( (v738 & 0xC0000000) != 0x40000000 )
            {
              v285 = (void *)*v817;
              if ( *v817 )
              {
                v922[6] = 2;
                if ( VirtualProtect(v285, 0x2000u, 2u, v923) )
                {
                  _InterlockedAnd(v284, 0x3FFFFFFFu);
                  _InterlockedOr(v284, 0x40000000u);
                }
              }
            }
          }
        }
        v286 = v817;
        v287 = v467;
        LatchBase::ReleaseInternal(v817 + 19, (unsigned int)v467);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
        {
          v489 = (unsigned __int8)byte_10317AD4F >> 1;
          if ( (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v286, 0, v287);
        }
        v419 &= 0xFFFF0000;
        v417 = 0;
        goto LABEL_753;
      }
      break;
    }
    v858 = v258;
    v611.QuadPart = 0;
    v612 = 0;
    v1217 = v259;
    v261 = *v259;
    v634 = *v259;
    v262 = v258;
    v964 = &v258[1].HighPart;
    while ( 1 )
    {
      v733 = v261 & 0xFFFFFFFE;
      v611 = *v262;
      v612 = v262[1].LowPart;
      _InterlockedOr(v415, 0);
      v261 = *v964;
      v634 = v261;
      if ( v733 == v261 )
        break;
      v262 = v858;
    }
    v907 = v611;
    v263 = v612;
    v908 = v612;
    v264 = *v417;
    v1218 = v264;
    v443 = 0;
    if ( *(_WORD *)(v264 + 36)
      && ((v265 = *(_BYTE *)(v264 + 1), v265 != 11) && v265 != 8 && v265 != 9
       || *(_DWORD *)(v264 + 24) != 99
       || (v1219 = &v675,
           v1220 = v264 + 32,
           v675 = *(_DWORD *)(v264 + 32),
           v676 = *(_WORD *)(v264 + 36),
           !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v675, v262))
        ? (v266 = 0)
        : (v266 = 1),
          (v443 = v266) != 0) )
    {
      PageHeader::GetIcxLsn(v264, &v651);
      v267 = v652;
    }
    else
    {
      v651 = *(LSN *)(v264 + 40);
      v267 = *(_WORD *)(v264 + 48);
      v652 = v267;
    }
    if ( v611.LowPart < v651.LowPart
      || v611.LowPart == v651.LowPart
      && (v611.HighPart < (unsigned int)v651.HighPart || v611.HighPart == v651.HighPart && v263 < v267) )
    {
      v268 = v430;
      v1221 = *((_QWORD *)v430 + 214);
      LSN::FormatAsHexString(&v651, v1598, &v734);
      LSN::FormatAsHexString(&v907, v1599, &v734);
      v965 = 29;
      v966 = 0x10000;
      if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
      {
        v767 = 6;
        v1222 = v1526;
        v1526[0] = 0;
        v1526[1] = 6;
        v1527 = 0;
        v1528 = &v1531;
        v1529 = &v1555;
        v1556 = 0;
        v1557 = 0;
        v1530 = 0;
        v1558 = 0;
        v1223 = &v1531;
        v1531 = &v1559;
        v1532 = 52;
        v1533 = 5;
        v1534 = 0;
        v1224 = &v1535;
        v1535 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
        v1536 = 16;
        v1537 = 5;
        v1538 = 0;
        v1225 = &v1539;
        v1539 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
        v1540 = 16;
        v1541 = 6;
        v1542 = 0;
        v1226 = &v1543;
        v1543 = 0;
        v1544 = 0;
        v1545 = 7;
        v1546 = 0;
        v1227 = &v1547;
        v1547 = 0;
        v1548 = 0;
        v1549 = 8;
        v1550 = 0;
        v1228 = &v1551;
        v1551 = 0;
        v1552 = 0;
        v1553 = 9;
        v1554 = 0;
        v1559 = *((unsigned __int16 *)v268 + 860);
        v1560 = v480;
        v1561 = v479;
        v1562 = v423;
        v1229 = *v417;
        v1563 = *(_BYTE *)(v1229 + 1);
        v1230 = &v1535;
        v1535 = (GUID *)(v269 + 596);
        v1536 = 16;
        v1537 = 5;
        v1538 = 0;
        v1231 = &v1539;
        v1539 = (GUID *)(v269 + 580);
        v1540 = 16;
        v1541 = 6;
        v1542 = 0;
        v1232 = v1598;
        v270 = -1;
        do
          ++v270;
        while ( v1598[v270] );
        v922[3] = 2 * v270;
        v1233 = &v1543;
        v1543 = v1598;
        v1544 = 2 * v270;
        v1545 = 7;
        v1546 = 0;
        v1234 = v1599;
        v271 = -1;
        do
          ++v271;
        while ( v1599[v271] );
        v922[4] = 2 * v271;
        v1235 = &v1547;
        v1547 = v1599;
        v1548 = 2 * v271;
        v1549 = 8;
        v1550 = 0;
        v735 = 0;
        v272 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v269, &v735);
        v273 = (int *)v272;
        v1236 = v272;
        if ( v272 )
        {
          v274 = -1;
          do
            ++v274;
          while ( *(_WORD *)(v272 + 2 * v274) );
          v275 = 2 * v274;
        }
        else
        {
          v275 = 0;
        }
        v922[5] = v275;
        v276 = v1528 + 10;
        v1237 = v1528 + 10;
        v1528[10] = v273;
        *((_DWORD *)v276 + 2) = v275;
        *((_WORD *)v276 + 6) = 9;
        *((_WORD *)v276 + 7) = 0;
        XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v1525);
      }
    }
LABEL_756:
    if ( (__int16)v419 >= 2 && v423 != -1 )
    {
      v288 = *v417;
      v1255 = v288;
      if ( *(_BYTE *)(v288 + 1) != v423 )
      {
        if ( v643 )
        {
          v1256 = v288;
          *((_QWORD *)v643 + 177) = v288;
        }
        if ( !UtilDbccGetContext() || !*((_QWORD *)UtilDbccGetContext() + 6) )
        {
          v739 = v289;
          goto LABEL_769;
        }
        v290 = *(_DWORD *)(*((_QWORD *)UtilDbccGetContext() + 6) + 12LL);
        v923[1] = v290;
        if ( v290 > 0xD || (v292 = 9792, v90 = _bittest(&v292, v290), v293 = 1, !v90) )
          v293 = v291;
        v739 = v293;
        if ( !v293 )
LABEL_769:
          RaiseInconsistencyError(0, 8);
      }
    }
LABEL_770:
    v909 = 0;
    v910 = 0;
    v911 = 0;
    if ( v722 || v720 || v721 )
    {
      v1257 = *v417;
      if ( (*(_BYTE *)(v1257 + 4) & 1) != 0 )
      {
        v1258 = (__int64)v417 + 98;
        v535 = *((_WORD *)v417 + 49);
        if ( (v535 & 0x400) != 0 && (__int16)v419 >= 3 )
        {
          PageRef::UnfixLatchOnly((PageRef *)&v417);
LABEL_796:
          v1009 = 4194400;
          v1010 = 0;
          v1012 = 0;
          v1011 = 0;
          v1013 = 0;
          SOS_Task::Sleep(10, &v1009);
          v221 = v430;
          continue;
        }
        v468 = (__int16)v419;
        v818 = v417;
        v1259 = (__int64)v417 + 98;
        v536 = *((_WORD *)v417 + 49);
        if ( (v536 & 8) != 0 )
        {
          if ( v468 == 3 )
          {
            v468 = 4;
            goto LABEL_781;
          }
          if ( v468 >= 2 )
          {
LABEL_781:
            v1260 = (__int64)v417 + 100;
            v740 = *((_DWORD *)v417 + 25);
            if ( (v740 & 8) != 0 )
            {
              v294 = v417[18];
              if ( v294 )
              {
                v1261 = v417[18];
                if ( *(_QWORD *)(v294 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v294 + 1880), v417, (unsigned int)v468);
                }
              }
            }
          }
        }
        v490 = (unsigned __int8)byte_10317ABE5 >> 7;
        if ( byte_10317ABE5 < 0 )
        {
          v295 = (volatile signed __int32 *)v818 + 25;
          v1262 = (__int64)v818 + 100;
          v741 = *((_DWORD *)v818 + 25);
          if ( (v741 & 8) != 0 && v468 >= 3 )
          {
            v1263 = (__int64)v818 + 100;
            v742 = *v295;
            if ( (v742 & 0xC0000000) != 0x40000000 )
            {
              v296 = (void *)*v818;
              if ( *v818 )
              {
                v923[2] = 2;
                if ( VirtualProtect(v296, 0x2000u, 2u, v924) )
                {
                  _InterlockedAnd(v295, 0x3FFFFFFFu);
                  _InterlockedOr(v295, 0x40000000u);
                }
              }
            }
          }
        }
        v297 = v818;
        v298 = v468;
        LatchBase::ReleaseInternal(v818 + 19, (unsigned int)v468);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
        {
          v491 = (unsigned __int8)byte_10317AD4F >> 1;
          if ( (byte_10317AD4F & 2) != 0 )
            BUF::TraceLatchAcquireRelease(v297, 0, v298);
        }
        v419 &= 0xFFFF0000;
        v417 = 0;
        goto LABEL_796;
      }
    }
    break;
  }
  v299 = v819;
  ++v819[1];
  v300 = *((_QWORD *)v299 + 11);
  if ( v300 )
    ++*(_DWORD *)(v300 + 4);
  if ( (v419 & 0xFF000000) != 0 )
  {
    ++v819[2];
    v301 = *((_QWORD *)v299 + 11);
    if ( v301 )
      ++*(_DWORD *)(v301 + 8);
    if ( (_BYTE)v420 )
    {
      ++v819[3];
      v302 = *((_QWORD *)v299 + 11);
      if ( v302 )
        ++*(_DWORD *)(v302 + 12);
    }
  }
  if ( v988 )
  {
    v1264 = *v417;
    HoBtAccess::UpdateLatchWaitStats(v967, *(unsigned __int8 *)(v1264 + 1), v987, 0xFFFFFFFFLL);
  }
  v492 = 0;
  v493 = 1;
  v644 = 0;
  v645 = 0;
  v646 = 0;
  v303 = *v867;
  v968 = (__int64 (__fastcall ***)(_QWORD))v303;
  v304 = *v417;
  v1265 = v304;
  v305 = *(_QWORD *)(v303 + 8) + 960LL;
  v1266 = v305;
  v743 = 0;
  if ( *(_DWORD *)(v304 + 24) == *(_DWORD *)v305 )
  {
    v306 = *(_WORD *)(v304 + 6);
    v307 = *(_WORD *)(v305 + 4);
    if ( v306 == v307 || (unsigned __int16)(v306 | v307) <= 1u )
    {
      v743 = 1;
      goto LABEL_834;
    }
  }
  v1267 = v304;
  v687 = 0;
  v688 = 0;
  v689 = 0;
  v308 = *(_DWORD *)(v304 + 24);
  v687 = v308;
  v309 = *(_WORD *)(v304 + 6);
  v688 = v309;
  v644 = v308;
  v645 = v309;
  v646 = 0;
  v1268 = (__int64)v417 + 98;
  v537 = *((_WORD *)v417 + 49);
  if ( (v537 & 0x400) == 0 || (__int16)v419 < 3 )
  {
    v469 = (__int16)v419;
    v820 = v417;
    v1269 = (__int64)v417 + 98;
    v538 = *((_WORD *)v417 + 49);
    if ( (v538 & 8) != 0 )
    {
      if ( v469 == 3 )
      {
        v469 = 4;
LABEL_818:
        v1270 = (__int64)v417 + 100;
        v744 = *((_DWORD *)v417 + 25);
        if ( (v744 & 8) != 0 )
        {
          v310 = v417[18];
          if ( v310 )
          {
            v1271 = v417[18];
            if ( *(_QWORD *)(v310 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v310 + 1880), v417, (unsigned int)v469);
            }
          }
        }
        goto LABEL_822;
      }
      if ( v469 >= 2 )
        goto LABEL_818;
    }
LABEL_822:
    v494 = (unsigned __int8)byte_10317ABE5 >> 7;
    if ( byte_10317ABE5 < 0 )
    {
      v311 = (volatile signed __int32 *)v820 + 25;
      v1272 = (__int64)v820 + 100;
      v745 = *((_DWORD *)v820 + 25);
      if ( (v745 & 8) != 0 && v469 >= 3 )
      {
        v1273 = (__int64)v820 + 100;
        v746 = *v311;
        if ( (v746 & 0xC0000000) != 0x40000000 )
        {
          v312 = (void *)*v820;
          if ( *v820 )
          {
            v924[1] = 2;
            if ( VirtualProtect(v312, 0x2000u, 2u, v925) )
            {
              _InterlockedAnd(v311, 0x3FFFFFFFu);
              _InterlockedOr(v311, 0x40000000u);
            }
          }
        }
      }
    }
    v313 = v820;
    v314 = v469;
    LatchBase::ReleaseInternal(v820 + 19, (unsigned int)v469);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
    {
      v495 = (unsigned __int8)byte_10317AD4F >> 1;
      if ( (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v313, 0, v314);
    }
    v419 &= 0xFFFF0000;
    v417 = 0;
    goto LABEL_833;
  }
  PageRef::UnfixLatchOnly((PageRef *)&v417);
LABEL_833:
  v1274 = &v693;
  v1275 = &v699;
  v315 = *(_QWORD *)(v303 + 8);
  v1276 = v315 + 960;
  v693 = *(_DWORD *)(v315 + 960);
  v694 = *(_WORD *)(v315 + 964);
  v695 = 0;
  v699 = v308;
  v700 = v309;
  v701 = 0;
  v316 = (**v968)(v968);
  RaiseWrongPageError(&v479, &v699, v316, &v693, *((_DWORD *)v867 + 4));
LABEL_834:
  SMOLockOrder::Add((SMOLockOrder *)v990, (struct PageRef *)&v417);
  v218 = **a2;
LABEL_835:
  v1277 = v218;
  v1584 = 0;
  if ( *(char *)(v218 + 2) >= 0 )
  {
    v317 = 0;
    v821 = 0;
    v318 = 3;
    goto LABEL_869;
  }
  _mm_prefetch((const char *)(v218 + 96), 0);
  if ( !v1573 )
  {
    v821 = 0;
    goto LABEL_840;
  }
  v317 = v1577;
  v821 = v1577;
  if ( !v1577 )
  {
LABEL_840:
    v1278 = &v1585;
    v1588 = 0;
    v1590 = 0u;
    v1591 = 0;
    v1593 = 0;
    v1279 = &v1585;
    v1585 = 0;
    v1280 = &v1586;
    v1586 = 0xFFFFu;
    v1589 = 0;
    memset(v1587, 0, sizeof(v1587));
    v1281 = (char *)&v1590 + 8;
    v1282 = &v1592;
    v1592 = 0u;
    v1283 = (char *)&v1592 + 12;
    v317 = (struct PageComprInfo *)&v1585;
    v821 = (struct PageComprInfo *)&v1585;
  }
  v447 = 0;
  if ( *(_WORD *)(v218 + 36)
    && ((v319 = *(_BYTE *)(v218 + 1), v319 != 11) && v319 != 8 && v319 != 9
     || *(_DWORD *)(v218 + 24) != 99
     || (v1284 = &v677,
         v1285 = v218 + 32,
         v677 = *(_DWORD *)(v218 + 32),
         v678 = *(_WORD *)(v218 + 36),
         !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v677, v220))
      ? (v320 = 0)
      : (v320 = 1),
        (v447 = v320) != 0) )
  {
    PageHeader::GetIcxLsn(v218, &v592);
    v321 = v593;
  }
  else
  {
    v592 = *(_QWORD *)(v218 + 40);
    v321 = *(_WORD *)(v218 + 48);
    v593 = v321;
  }
  v1286 = &v592;
  v1287 = v218 + 32;
  v322 = (unsigned __int8 *)(v218 + 96);
  v1288 = v218 + 96;
  v1289 = v317;
  if ( v218 + 96 == *(_QWORD *)v317 )
  {
    v1290 = (char *)v317 + 96;
    if ( v321 == *((_WORD *)v317 + 52) && v592 == *((_QWORD *)v317 + 12) )
      v1291 = (char *)v317 + 108;
  }
  *(_QWORD *)v317 = v322;
  v1292 = (char *)v317 + 96;
  v323 = v593;
  v768 = v593;
  v324 = HIDWORD(v592);
  v925[1] = HIDWORD(v592);
  v925[3] = v592;
  *((_DWORD *)v317 + 24) = v592;
  *((_DWORD *)v317 + 25) = v324;
  *((_WORD *)v317 + 52) = v323;
  v1293 = (char *)v317 + 108;
  *((_DWORD *)v317 + 27) = *(_DWORD *)(v218 + 32);
  *((_WORD *)v317 + 56) = *(_WORD *)(v218 + 36);
  *((_WORD *)v317 + 57) = 0;
  v325 = *v322;
  v769 = *v322;
  v878 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * v325);
  v879 = word_102883984[3 * v325];
  v778 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * v325);
  v326 = word_102883984[3 * v325];
  v425 = v326;
  v779 = v326;
  v327 = (unsigned __int8 *)(v218 + 99);
  v1294 = v218 + 99;
  v1295 = (char *)v317 + 16;
  *((_WORD *)v317 + 8) = -1;
  *((_QWORD *)v317 + 3) = 0;
  *((_DWORD *)v317 + 5) = 0;
  *(_QWORD *)((char *)v317 + 46) = 0;
  *((_QWORD *)v317 + 7) = 0;
  *((_QWORD *)v317 + 4) = 0;
  v328 = (char *)v317 + 72;
  v1296 = (char *)v317 + 72;
  *((_QWORD *)v317 + 9) = 0;
  *((_QWORD *)v317 + 10) = 0;
  *((_WORD *)v317 + 44) = 0;
  if ( (**(_BYTE **)v317 & 2) != 0 )
  {
    v329 = &v322[v326];
    v1297 = &v322[v326];
    v1298 = (char *)v317 + 16;
    v330 = v322[v326] & 1;
    v770 = v330;
    *((_WORD *)v317 + 8) = v330;
    if ( v330 )
    {
      v1301 = (char *)v317 + 18;
      *((_QWORD *)v317 + 3) = v329;
      __asm { jmp     rcx }
    }
    v556 = 0;
    v1299 = (char *)v317 + 18;
    *((_QWORD *)v317 + 3) = v329;
    *((_DWORD *)v317 + 5) = 0;
    *(_DWORD *)((char *)v317 + 54) = 0;
    v331 = *((_QWORD *)v317 + 3);
    v1300 = v331;
    v332 = *((unsigned __int16 *)v329 + 1);
    v556 = v332;
    if ( (unsigned int)(v332 - 1) > 0x1F9D )
    {
      RaiseInconsistencyError(v331, 6);
      v322 = (unsigned __int8 *)(v218 + 96);
    }
    *((_DWORD *)v317 + 8) = v332;
    *(_QWORD *)((char *)v317 + 46) = 0;
    v328 = (char *)v317 + 72;
    LOWORD(v326) = v425;
    v327 = v322 + 3;
  }
  v318 = 3;
  if ( (**(_BYTE **)v317 & 4) != 0 )
  {
    if ( HIWORD(v778) )
      v333 = *(unsigned __int16 *)&v327[2 * SHIWORD(v778) - 2];
    else
      v333 = (__int16)v326;
    v334 = &v322[v333];
    v1302 = v334;
    v1303 = v328;
    *(_QWORD *)v328 = v334;
    v771 = *(_WORD *)v334;
    v335 = v771;
    *((_QWORD *)v328 + 1) = v334 + 2;
    *((_WORD *)v328 + 8) = 2 * (v335 + 1);
  }
  v336 = (PageComprInfoCache *)*((_QWORD *)v317 + 1);
  if ( v336 )
    PageComprInfoCache::Init(v336, v317);
LABEL_869:
  v337 = *(unsigned __int16 *)(v218 + 14);
  v925[5] = v337;
  v338 = (char *)(v218 + *(unsigned __int16 *)(v218 + 8190));
  v1304 = v338;
  v339 = (*v338 & 1) == 0;
  v772 = *v338 & 1;
  v1573 = v772;
  if ( v339 )
  {
    v557 = v337;
    v1305 = (__int16 *)&v1574;
    v1576 = v338;
    v1575 = 0;
    *(_DWORD *)v1582 = 0;
    v1306 = v338;
    switch ( *v338 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v337 = *((unsigned __int16 *)v338 + 1);
        v557 = v337;
        if ( v337 - 1 > 0x1F9D )
          RaiseInconsistencyError(v338, 6);
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
        v337 = 9;
        v557 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v337 = 1;
        v557 = 1;
        break;
    }
    LODWORD(v1577) = v337;
    v1581 = v218 + 0x2000;
  }
  else
  {
    v1307 = (__int16 *)&v1574;
    v1576 = v338;
    v340 = *v338;
    switch ( *v338 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        v341 = v338 + 1;
        v1308 = v341;
        if ( *v341 < 0 )
        {
          v342 = HIBYTE(*(_WORD *)v341) | ((*(_WORD *)v341 & 0x7F) << 8);
          v1574 = v342;
          v1578 = 3;
        }
        else
        {
          v342 = (unsigned __int8)*v341;
          v1574 = v342;
          v1578 = 2;
          v318 = 2;
        }
        v1580 = v318 + (((unsigned int)v342 + 1) >> 1);
        if ( v342 > 0x1Eu )
          v1579 = (v342 - 1) / 30;
        else
          v1579 = 0;
        v1575 = 0;
        v1583 = 0;
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
        v1310 = v338;
        v1311 = v338;
        if ( (v340 & 0x1C) == 4 && (v340 & 2) != 0 )
        {
          v1578 = 0;
          v1574 = 0;
          v1579 = 0;
          v1580 = 0;
          v1581 = 0;
          memset(v1582, 0, sizeof(v1582));
          v1577 = 0;
          v1576 = v338;
          v1575 = 15;
          v1583 = 1;
        }
        else
        {
          v1578 = 0;
          v1574 = 0;
          v1579 = 0;
          v1580 = 0;
          v1581 = 0;
          memset(v1582, 0, sizeof(v1582));
          v1577 = 0;
          v1576 = v338;
          v1575 = 1;
          v1583 = 0;
        }
        break;
      case 8:
        v1309 = v338;
        v1578 = 0;
        v1574 = 0;
        v1579 = 0;
        v1580 = 0;
        v1581 = 0;
        memset(v1582, 0, sizeof(v1582));
        v1577 = 0;
        v1576 = v338;
        v1575 = 9;
        v1583 = 0;
        break;
    }
    *(_QWORD *)&v1582[2] = v218 + 0x2000;
    v1577 = v317;
  }
  *(_QWORD *)&v1570 = &v1573;
  v343 = v619;
  v1312 = (struct RecoveryUnit **)*((_QWORD *)v619 + 34);
  v926 = *((_DWORD *)v619 + 64);
  v344 = v864;
  v345 = (unsigned __int16 *)v866;
  PageRef::InsertRows(
    (BUF **)v866,
    v864,
    (const struct AllocUnitId *)&v483,
    1,
    1,
    (struct RecordHolder *)&v1570,
    v926,
    0,
    v1312,
    0,
    0,
    0);
  v1313 = *((_QWORD *)v343 + 34);
  v927 = *((_DWORD *)v343 + 64);
  v346 = (__int16 *)v865;
  PageRef::DeleteRows(v865, v344, &v483, 0, 1, v927, 0, v1313, 0, 0, 0, 0, 0);
  v1314 = *((_QWORD *)v343 + 34);
  v928 = *((_DWORD *)v343 + 64);
  PageRef::DeleteRows(v823, v344, &v483, v621, 1, v928, 0, v1314, 0, 0, 0, 0, 0);
  BTreeMgr::DeAllocatePage(
    v343,
    (struct PageRef *)v346,
    (struct PageRef *)v345,
    (struct PageRef *)&v417,
    (struct SMOLockOrder *)v990);
  SMOLockOrder::Clear((SMOLockOrder *)v990);
  v347 = *(struct Page ***)v346;
  if ( *(_QWORD *)v346 )
  {
    v1315 = (__int64)v347 + 98;
    v539 = *((_WORD *)v347 + 49);
    if ( (v539 & 0x400) != 0 && v346[6] >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)v346);
      goto LABEL_914;
    }
    v470 = v346[6];
    v608 = *(struct Page ***)v346;
    v1316 = (__int64)v608 + 98;
    v540 = *((_WORD *)v608 + 49);
    if ( (v540 & 8) != 0 )
    {
      if ( v470 == 3 )
      {
        v470 = 4;
        goto LABEL_899;
      }
      if ( v470 >= 2 )
      {
LABEL_899:
        v1317 = (__int64)v608 + 100;
        v747 = *((_DWORD *)v608 + 25);
        if ( (v747 & 8) != 0 )
        {
          v348 = v608[18];
          if ( v348 )
          {
            v1318 = v608[18];
            if ( *((_QWORD *)v348 + 235) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*((_QWORD *)v348 + 235), v608, (unsigned int)v470);
            }
          }
        }
      }
    }
    v496 = (unsigned __int8)byte_10317ABE5 >> 7;
    if ( byte_10317ABE5 < 0 )
    {
      v349 = (volatile signed __int32 *)v608 + 25;
      v1319 = (__int64)v608 + 100;
      v748 = *((_DWORD *)v608 + 25);
      if ( (v748 & 8) != 0 && v470 >= 3 )
      {
        v1320 = (__int64)v608 + 100;
        v749 = *v349;
        if ( (v749 & 0xC0000000) != 0x40000000 )
        {
          v350 = *v608;
          if ( *v608 )
          {
            v935[1] = 2;
            if ( VirtualProtect(v350, 0x2000u, 2u, v929) )
            {
              _InterlockedAnd(v349, 0x3FFFFFFFu);
              _InterlockedOr(v349, 0x40000000u);
            }
          }
        }
      }
    }
    v351 = v608;
    v352 = v470;
    LatchBase::ReleaseInternal(v608 + 19, (unsigned int)v470);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
    {
      v497 = (unsigned __int8)byte_10317AD4F >> 1;
      if ( (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v351, 0, v352);
    }
    *((_DWORD *)v346 + 3) &= 0xFFFF0000;
    *(_QWORD *)v346 = 0;
  }
LABEL_914:
  if ( v426 )
  {
    v1321 = (char *)v426 + 98;
    v541 = *((_WORD *)v426 + 49);
    if ( (v541 & 0x400) != 0 && (__int16)v428 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v426);
      goto LABEL_937;
    }
    v476 = (__int16)v428;
    v1322 = v426;
    v1323 = (char *)v426 + 98;
    v542 = *((_WORD *)v426 + 49);
    if ( (v542 & 8) != 0 )
    {
      if ( v476 == 3 )
      {
        v476 = 4;
        goto LABEL_922;
      }
      if ( v476 >= 2 )
      {
LABEL_922:
        v1324 = (char *)v426 + 100;
        v750 = *((_DWORD *)v426 + 25);
        if ( (v750 & 8) != 0 )
        {
          v353 = v426[18];
          if ( v353 )
          {
            v1325 = v426[18];
            if ( *((_QWORD *)v353 + 235) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*((_QWORD *)v353 + 235), v426, (unsigned int)v476);
            }
          }
        }
      }
    }
    v498 = (unsigned __int8)byte_10317ABE5 >> 7;
    if ( byte_10317ABE5 < 0 )
    {
      v354 = (volatile signed __int32 *)v426 + 25;
      v1326 = (char *)v426 + 100;
      v751 = *((_DWORD *)v426 + 25);
      if ( (v751 & 8) != 0 && v476 >= 3 )
      {
        v1327 = (char *)v426 + 100;
        v752 = *v354;
        if ( (v752 & 0xC0000000) != 0x40000000 )
        {
          v355 = *v426;
          if ( *v426 )
          {
            v929[1] = 2;
            if ( VirtualProtect(v355, 0x2000u, 2u, v930) )
            {
              _InterlockedAnd(v354, 0x3FFFFFFFu);
              _InterlockedOr(v354, 0x40000000u);
            }
          }
        }
      }
    }
    v356 = v426;
    v357 = v476;
    LatchBase::ReleaseInternal(v426 + 19, (unsigned int)v476);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
    {
      v499 = (unsigned __int8)byte_10317AD4F >> 1;
      if ( (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v356, 0, v357);
    }
    v428 &= 0xFFFF0000;
    v426 = 0;
  }
LABEL_937:
  v426 = *(struct Page ***)v345;
  v428 = v345[6] | v428 & 0xFFFF0000;
  *(_QWORD *)v345 = 0;
  *((_DWORD *)v345 + 3) &= 0xFFFF0000;
LABEL_1019:
  BTreeMgr::CommitXactForSplitShrink(v343);
  if ( v424 )
  {
    v391 = *(struct Page ***)v345;
    if ( *(_QWORD *)v345 )
    {
      v1380 = (__int64)v391 + 98;
      v545 = *((_WORD *)v391 + 49);
      if ( (v545 & 0x400) != 0 && (__int16)v345[6] >= 3 )
      {
        PageRef::UnfixLatchOnly((PageRef *)v345);
        goto LABEL_1062;
      }
      v473 = (__int16)v345[6];
      v609 = *(struct Page ***)v345;
      v1381 = (__int64)v609 + 98;
      v546 = *((_WORD *)v609 + 49);
      if ( (v546 & 8) != 0 )
      {
        if ( v473 == 3 )
        {
          v473 = 4;
          goto LABEL_1047;
        }
        if ( v473 >= 2 )
        {
LABEL_1047:
          v1382 = (__int64)v609 + 100;
          v756 = *((_DWORD *)v609 + 25);
          if ( (v756 & 8) != 0 )
          {
            v397 = v609[18];
            if ( v397 )
            {
              v1383 = v609[18];
              if ( *((_QWORD *)v397 + 235) )
              {
                _mm_lfence();
                DirtyPageMgr::OnReleasingBufLatch(*((_QWORD *)v397 + 235), v609, (unsigned int)v473);
              }
            }
          }
        }
      }
      v502 = (unsigned __int8)byte_10317ABE5 >> 7;
      if ( byte_10317ABE5 < 0 )
      {
        v398 = (volatile signed __int32 *)v609 + 25;
        v1384 = (__int64)v609 + 100;
        v757 = *((_DWORD *)v609 + 25);
        if ( (v757 & 8) != 0 && v473 >= 3 )
        {
          v1385 = (__int64)v609 + 100;
          v758 = *v398;
          if ( (v758 & 0xC0000000) != 0x40000000 )
          {
            v399 = *v609;
            if ( *v609 )
            {
              v973 = 2;
              if ( VirtualProtect(v399, 0x2000u, 2u, v974) )
              {
                _InterlockedAnd(v398, 0x3FFFFFFFu);
                _InterlockedOr(v398, 0x40000000u);
              }
            }
          }
        }
      }
      v400 = v609;
      v401 = v473;
      LatchBase::ReleaseInternal(v609 + 19, (unsigned int)v473);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
      {
        v503 = (unsigned __int8)byte_10317AD4F >> 1;
        if ( (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v400, 0, v401);
      }
      *((_DWORD *)v345 + 3) &= 0xFFFF0000;
      *(_QWORD *)v345 = 0;
    }
  }
LABEL_1062:
  if ( v417 )
  {
    v1386 = (__int64)v417 + 98;
    v547 = *((_WORD *)v417 + 49);
    if ( (v547 & 0x400) != 0 && (__int16)v419 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v417);
      goto LABEL_1085;
    }
    v474 = (__int16)v419;
    v824 = v417;
    v1387 = (__int64)v417 + 98;
    v548 = *((_WORD *)v417 + 49);
    if ( (v548 & 8) != 0 )
    {
      if ( v474 == 3 )
      {
        v474 = 4;
        goto LABEL_1070;
      }
      if ( v474 >= 2 )
      {
LABEL_1070:
        v1388 = (__int64)v417 + 100;
        v759 = *((_DWORD *)v417 + 25);
        if ( (v759 & 8) != 0 )
        {
          v402 = v417[18];
          if ( v402 )
          {
            v1389 = v417[18];
            if ( *(_QWORD *)(v402 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v402 + 1880), v417, (unsigned int)v474);
            }
          }
        }
      }
    }
    v504 = (unsigned __int8)byte_10317ABE5 >> 7;
    if ( byte_10317ABE5 < 0 )
    {
      v403 = (volatile signed __int32 *)v824 + 25;
      v1390 = (__int64)v824 + 100;
      v760 = *((_DWORD *)v824 + 25);
      if ( (v760 & 8) != 0 && v474 >= 3 )
      {
        v1391 = (__int64)v824 + 100;
        v761 = *v403;
        if ( (v761 & 0xC0000000) != 0x40000000 )
        {
          v404 = (void *)*v824;
          if ( *v824 )
          {
            v974[1] = 2;
            if ( VirtualProtect(v404, 0x2000u, 2u, v975) )
            {
              _InterlockedAnd(v403, 0x3FFFFFFFu);
              _InterlockedOr(v403, 0x40000000u);
            }
          }
        }
      }
    }
    v405 = v824;
    v406 = v474;
    LatchBase::ReleaseInternal(v824 + 19, (unsigned int)v474);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
    {
      v505 = (unsigned __int8)byte_10317AD4F >> 1;
      if ( (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v405, 0, v406);
    }
    v419 &= 0xFFFF0000;
    v417 = 0;
  }
LABEL_1085:
  *v969 = 1;
  v407 = *(struct Page ***)v346;
  if ( *(_QWORD *)v346 )
  {
    v1392 = (__int64)v407 + 98;
    v549 = *((_WORD *)v407 + 49);
    if ( (v549 & 0x400) != 0 && v346[6] >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)v346);
      goto LABEL_1108;
    }
    v475 = v346[6];
    v610 = *(struct Page ***)v346;
    v1393 = (__int64)v610 + 98;
    v550 = *((_WORD *)v610 + 49);
    if ( (v550 & 8) != 0 )
    {
      if ( v475 == 3 )
      {
        v475 = 4;
        goto LABEL_1093;
      }
      if ( v475 >= 2 )
      {
LABEL_1093:
        v1394 = (__int64)v610 + 100;
        v762 = *((_DWORD *)v610 + 25);
        if ( (v762 & 8) != 0 )
        {
          v408 = v610[18];
          if ( v408 )
          {
            v1395 = v610[18];
            if ( *((_QWORD *)v408 + 235) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*((_QWORD *)v408 + 235), v610, (unsigned int)v475);
            }
          }
        }
      }
    }
    v506 = (unsigned __int8)byte_10317ABE5 >> 7;
    if ( byte_10317ABE5 < 0 )
    {
      v409 = (volatile signed __int32 *)v610 + 25;
      v1396 = (__int64)v610 + 100;
      v763 = *((_DWORD *)v610 + 25);
      if ( (v763 & 8) != 0 && v475 >= 3 )
      {
        v1397 = (__int64)v610 + 100;
        v764 = *v409;
        if ( (v764 & 0xC0000000) != 0x40000000 )
        {
          v410 = *v610;
          if ( *v610 )
          {
            v975[1] = 2;
            if ( VirtualProtect(v410, 0x2000u, 2u, v976) )
            {
              _InterlockedAnd(v409, 0x3FFFFFFFu);
              _InterlockedOr(v409, 0x40000000u);
            }
          }
        }
      }
    }
    v411 = v610;
    v412 = v475;
    LatchBase::ReleaseInternal(v610 + 19, (unsigned int)v475);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
    {
      v507 = (unsigned __int8)byte_10317AD4F >> 1;
      if ( (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v411, 0, v412);
    }
    *((_DWORD *)v346 + 3) &= 0xFFFF0000;
    *(_QWORD *)v346 = 0;
  }
LABEL_1108:
  *(_QWORD *)v346 = v426;
  *((_DWORD *)v346 + 3) &= 0xFFFF0000;
  *((_DWORD *)v346 + 3) |= (unsigned __int16)v428;
  v426 = 0;
  v428 &= 0xFFFF0000;
  v413 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v414 = *(struct Worker **)(v413 + 256);
  if ( !v414 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v414 = *(struct Worker **)(v413 + 256);
  }
  if ( *((_DWORD *)v414 + 139) )
    ExceptionPostCatchActions(v414);
  PageRef::~PageRef((PageRef *)&v426);
  PageRef::~PageRef((PageRef *)&v417);
}

```

## disassembly

```asm
0x1012ab8a0  push    rbx
0x1012ab8a2  push    rsi
0x1012ab8a3  push    rdi
0x1012ab8a4  push    r12
0x1012ab8a6  push    r13
0x1012ab8a8  push    r14
0x1012ab8aa  push    r15
0x1012ab8ac  mov     eax, 3390h
0x1012ab8b1  call    _alloca_probe
0x1012ab8b6  sub     rsp, rax
0x1012ab8b9  mov     [rsp+33C8h+var_16C0], 0FFFFFFFFFFFFFFFEh
0x1012ab8c5  mov     rax, cs:__security_cookie
0x1012ab8cc  xor     rax, rsp
0x1012ab8cf  mov     [rsp+33C8h+var_48], rax
0x1012ab8d7  mov     [rsp+33C8h+var_2F3C], r9d
0x1012ab8df  mov     [rsp+33C8h+var_2A70], r8
0x1012ab8e7  mov     r12, rdx
0x1012ab8ea  mov     [rsp+33C8h+var_2928], rdx
0x1012ab8f2  mov     rdi, rcx
0x1012ab8f5  mov     [rsp+33C8h+var_2F48], rcx
0x1012ab8fd  mov     r13, [rsp+33C8h+arg_28]
0x1012ab905  mov     [rsp+33C8h+var_2920], r13
0x1012ab90d  mov     [rsp+33C8h+var_2600], rcx
0x1012ab915  mov     [rsp+33C8h+var_25F0], rdx
0x1012ab91d  mov     rax, [rsp+33C8h+arg_20]
0x1012ab925  mov     [rsp+33C8h+var_2608], rax
0x1012ab92d  mov     [rsp+33C8h+var_25F8], r13
0x1012ab935  xor     esi, esi
0x1012ab937  mov     [rsp+33C8h+var_3358], rsi
0x1012ab93c  mov     [rsp+33C8h+var_3350], sil
0x1012ab941  mov     eax, [rsp+33C8h+var_334C]
0x1012ab945  and     eax, 0FFFF0000h
0x1012ab94a  mov     [rsp+33C8h+var_334C], eax
0x1012ab94e  and     eax, 0FF00FFFFh
0x1012ab953  mov     [rsp+33C8h+var_334C], eax
0x1012ab957  mov     [rsp+33C8h+var_334C], esi
0x1012ab95b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1012ab962  mov     [rsp+33C8h+var_C80], ax
0x1012ab96a  mov     [rsp+33C8h+var_C78], rsi
0x1012ab972  mov     [rsp+33C8h+var_C7C], esi
0x1012ab979  mov     [rsp+33C8h+var_C62], rsi
0x1012ab981  mov     qword ptr [rsp+33C8h+var_C5A+2], rsi
0x1012ab989  mov     [rsp+33C8h+var_C70], rsi
0x1012ab991  mov     [rsp+33C8h+var_C4C], eax
0x1012ab998  xorps   xmm0, xmm0
0x1012ab99b  movdqu  [rsp+33C8h+var_D10], xmm0
0x1012ab9a4  mov     [rsp+33C8h+var_3338], rsi
0x1012ab9ac  mov     [rsp+33C8h+var_3330], sil
0x1012ab9b4  mov     eax, [rsp+33C8h+var_332C]
0x1012ab9bb  and     eax, 0FFFF0000h
0x1012ab9c0  mov     [rsp+33C8h+var_332C], eax
0x1012ab9c7  and     eax, 0FF00FFFFh
0x1012ab9cc  mov     [rsp+33C8h+var_332C], eax
0x1012ab9d3  mov     [rsp+33C8h+var_332C], esi
0x1012ab9da  mov     rdx, [rdx]
0x1012ab9dd  mov     rcx, [rdx]
0x1012ab9e0  mov     eax, [rcx+8]
0x1012ab9e3  mov     [rsp+33C8h+var_32F4], eax
0x1012ab9ea  movzx   eax, word ptr [rcx+0Ch]
0x1012ab9ee  mov     [rsp+33C8h+var_32F0], ax
0x1012ab9f6  mov     eax, [rdx+70h]
0x1012ab9f9  mov     [rsp+33C8h+var_3210], eax
0x1012aba00  movzx   eax, word ptr [rdx+74h]
0x1012aba04  mov     [rsp+33C8h+var_320C], ax
0x1012aba0c  mov     rax, [rdi+8]
0x1012aba10  mov     rdx, [rax]
0x1012aba13  movzx   ecx, word ptr [rdx+18h]
0x1012aba17  shl     rcx, 20h
0x1012aba1b  mov     eax, [rdx+14h]
0x1012aba1e  or      rcx, rax
0x1012aba21  shl     rcx, 10h
0x1012aba25  mov     [rsp+33C8h+var_2930], rcx
0x1012aba2d  mov     rcx, [rdx+8]
0x1012aba31  mov     eax, [rcx+3C0h]
0x1012aba37  mov     [rsp+33C8h+var_3208], eax
0x1012aba3e  movzx   eax, word ptr [rcx+3C4h]
0x1012aba45  mov     [rsp+33C8h+var_3204], ax
0x1012aba4d  mov     [rsp+33C8h+var_3202], si
0x1012aba55  mov     r14d, 2
0x1012aba5b  mov     ebx, r14d
0x1012aba5e  cmp     dword ptr [rdi+0FCh], 3
0x1012aba65  cmovz   ebx, esi
0x1012aba68  mov     [rsp+33C8h+var_2460], esi
0x1012aba6f  mov     [rsp+33C8h+var_2498], rsi
0x1012aba77  mov     [rsp+33C8h+var_2490], rdx
0x1012aba7f  mov     rax, [rdx]
0x1012aba82  mov     rcx, rdx
0x1012aba85  call    qword ptr [rax]
0x1012aba87  cmp     ax, r14w
0x1012aba8b  cmovz   ebx, r14d
0x1012aba8f  mov     [rsp+33C8h+var_245C], ebx
0x1012aba96  mov     [rsp+33C8h+var_333D], 1
0x1012aba9e  cmp     [rsp+33C8h+var_32F4], esi
0x1012abaa5  jnz     short loc_1012ABAD4
0x1012abaa7  cmp     [rsp+33C8h+var_32F0], si
0x1012abaaf  jnz     short loc_1012ABAD4
0x1012abab1  mov     [rsp+33C8h+var_33A8], rsi
0x1012abab6  mov     r9d, 13CBh
0x1012ababc  lea     r8, aBtreemgrCpp; "BtreeMgr.cpp"
0x1012abac3  lea     rdx, aLeftpageidPage; "leftPageId != PageId_NULL"
0x1012abaca  lea     ecx, [rsi+1]
0x1012abacd  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1012abad3  nop
0x1012abad4  lea     rdx, aBtreemgrMovero; "BTreeMgr::MoveRowFromLeftSibling"
0x1012abadb  mov     rcx, rdi; this
0x1012abade  call    ?BeginXactForSplitShrink@BTreeMgr@@AEAAXPEB_W@Z; BTreeMgr::BeginXactForSplitShrink(wchar_t const *)
0x1012abae3  mov     rax, [rdi+110h]
0x1012abaea  mov     [rsp+33C8h+var_2498], rax
0x1012abaf2  mov     rax, [r12]
0x1012abaf6  mov     r15d, 400h
0x1012abafc  test    rax, rax
0x1012abaff  jz      loc_1012ABCF7
0x1012abb05  add     rax, 62h ; 'b'
0x1012abb09  mov     [rsp+33C8h+var_16B8], rax
0x1012abb11  movzx   eax, word ptr [rax]
0x1012abb14  mov     [rsp+33C8h+var_31E0], ax
0x1012abb1c  test    r15w, ax
0x1012abb20  jz      short loc_1012ABB38
0x1012abb22  cmp     word ptr [r12+0Ch], 3
0x1012abb29  jl      short loc_1012ABB38
0x1012abb2b  mov     rcx, r12; this
0x1012abb2e  call    ?UnfixLatchOnly@PageRef@@IEAAXXZ; PageRef::UnfixLatchOnly(void)
0x1012abb33  jmp     loc_1012ABCF7
0x1012abb38  movsx   eax, word ptr [r12+0Ch]
0x1012abb3e  mov     [rsp+33C8h+var_3228], eax
0x1012abb45  mov     rax, [r12]
0x1012abb49  mov     [rsp+33C8h+var_2FF8], rax
0x1012abb51  add     rax, 62h ; 'b'
0x1012abb55  mov     [rsp+33C8h+var_16B0], rax
0x1012abb5d  movzx   eax, word ptr [rax]
0x1012abb60  mov     [rsp+33C8h+var_31D8], ax
0x1012abb68  shr     al, 3
0x1012abb6b  test    al, 1
0x1012abb6d  jz      loc_1012ABBFA
0x1012abb73  cmp     [rsp+33C8h+var_3228], 3
0x1012abb7b  jnz     short loc_1012ABB8A
0x1012abb7d  mov     [rsp+33C8h+var_3228], 4
0x1012abb88  jmp     short loc_1012ABB94
0x1012abb8a  cmp     [rsp+33C8h+var_3228], 2
0x1012abb92  jl      short loc_1012ABBFA
0x1012abb94  mov     rax, [rsp+33C8h+var_2FF8]
0x1012abb9c  add     rax, 64h ; 'd'
0x1012abba0  mov     [rsp+33C8h+var_16A8], rax
0x1012abba8  mov     eax, [rax]
0x1012abbaa  mov     [rsp+33C8h+var_2B98], eax
0x1012abbb1  test    al, 8
0x1012abbb3  jz      short loc_1012ABBFA
0x1012abbb5  mov     rax, [rsp+33C8h+var_2FF8]
0x1012abbbd  mov     rcx, [rax+90h]
0x1012abbc4  test    rcx, rcx
0x1012abbc7  jz      short loc_1012ABBFA
0x1012abbc9  mov     [rsp+33C8h+var_16A0], rcx
0x1012abbd1  cmp     qword ptr [rcx+758h], 0
0x1012abbd9  jz      short loc_1012ABBFA
0x1012abbdb  lfence
0x1012abbde  mov     r8d, [rsp+33C8h+var_3228]
0x1012abbe6  mov     rdx, [rsp+33C8h+var_2FF8]
0x1012abbee  mov     rcx, [rcx+758h]
0x1012abbf5  call    ?OnReleasingBufLatch@DirtyPageMgr@@QEAAXPEAUBUF@@W4LATCH_TYPE@LatchBase@@@Z; DirtyPageMgr::OnReleasingBufLatch(BUF *,LatchBase::LATCH_TYPE)
0x1012abbfa  movzx   eax, cs:byte_10317ABE5
0x1012abc01  shr     al, 7
0x1012abc04  mov     [rsp+33C8h+var_3088], al
0x1012abc0b  test    al, al
0x1012abc0d  jz      loc_1012ABC9B
0x1012abc13  mov     rbx, [rsp+33C8h+var_2FF8]
0x1012abc1b  add     rbx, 64h ; 'd'
0x1012abc1f  mov     [rsp+33C8h+var_1698], rbx
0x1012abc27  mov     eax, [rbx]
0x1012abc29  mov     [rsp+33C8h+var_2B90], eax
0x1012abc30  test    al, 8
0x1012abc32  jz      short loc_1012ABC9B
0x1012abc34  cmp     [rsp+33C8h+var_3228], 3
0x1012abc3c  jl      short loc_1012ABC9B
0x1012abc3e  mov     [rsp+33C8h+var_1690], rbx
0x1012abc46  mov     eax, [rbx]
0x1012abc48  mov     [rsp+33C8h+var_2B88], eax
0x1012abc4f  and     eax, 0C0000000h
0x1012abc54  cmp     eax, 40000000h
0x1012abc59  jz      short loc_1012ABC9B
0x1012abc5b  mov     rax, [rsp+33C8h+var_2FF8]
0x1012abc63  mov     rcx, [rax]; lpAddress
0x1012abc66  test    rcx, rcx
0x1012abc69  jz      short loc_1012ABC9B
0x1012abc6b  mov     [rsp+33C8h+var_258C], r14d
0x1012abc73  lea     r9, [rsp+33C8h+flOldProtect]; lpflOldProtect
0x1012abc7b  mov     r8d, r14d; flNewProtect
0x1012abc7e  mov     edx, 2000h; dwSize
0x1012abc83  call    cs:__imp_VirtualProtect
0x1012abc89  test    eax, eax
0x1012abc8b  jz      short loc_1012ABC9B
0x1012abc8d  lock and dword ptr [rbx], 3FFFFFFFh
0x1012abc94  lock or dword ptr [rbx], 40000000h
0x1012abc9b  mov     rbx, [rsp+33C8h+var_2FF8]
0x1012abca3  lea     rcx, [rbx+98h]
0x1012abcaa  mov     edi, [rsp+33C8h+var_3228]
0x1012abcb1  mov     edx, edi
0x1012abcb3  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x1012abcb8  cmp     cs:?sm_acquireReleaseEnforcementExpensive@LatchBase@@0HA, 0; int LatchBase::sm_acquireReleaseEnforcementExpensive
0x1012abcbf  jz      short loc_1012ABCE2
0x1012abcc1  movzx   eax, cs:byte_10317AD4F
0x1012abcc8  shr     al, 1
0x1012abcca  mov     [rsp+33C8h+var_3087], al
0x1012abcd1  test    al, 1
0x1012abcd3  jz      short loc_1012ABCE2
0x1012abcd5  mov     r8d, edi
0x1012abcd8  xor     edx, edx
0x1012abcda  mov     rcx, rbx
0x1012abcdd  call    ?TraceLatchAcquireRelease@BUF@@QEAAX_NW4LATCH_TYPE@LatchBase@@@Z; BUF::TraceLatchAcquireRelease(bool,LatchBase::LATCH_TYPE)
0x1012abce2  and     dword ptr [r12+0Ch], 0FFFF0000h
0x1012abceb  mov     [r12], rsi
0x1012abcef  mov     rdi, [rsp+33C8h+var_2F48]
0x1012abcf7  cmp     qword ptr [r13+0], 0
0x1012abcfc  jz      short loc_1012ABD0D
0x1012abcfe  mov     [rsp+33C8h+var_333D], 0
0x1012abd06  xor     edi, edi
0x1012abd08  jmp     loc_1012ADA43
0x1012abd0d  mov     rcx, [rdi+8]
0x1012abd11  mov     [rsp+33C8h+var_2948], rcx
0x1012abd19  mov     rax, [rdi+10h]
0x1012abd1d  mov     [rsp+33C8h+var_2AC0], rax
0x1012abd25  xor     edi, edi
0x1012abd27  mov     [rsp+33C8h+var_2D98], edi
0x1012abd2e  mov     [rsp+33C8h+var_2D94], edi
0x1012abd35  mov     [rsp+33C8h+var_2D90], di
0x1012abd3d  mov     rax, [rcx]
0x1012abd40  mov     [rsp+33C8h+var_26B8], rax
0x1012abd48  mov     [rsp+33C8h+var_24F4], edi
0x1012abd4f  mov     [rsp+33C8h+var_24F0], edi
0x1012abd56  mov     rbx, [rax+20h]
0x1012abd5a  mov     [rsp+33C8h+var_3310], rbx
0x1012abd62  add     rax, 14h
0x1012abd66  mov     [rsp+33C8h+var_1688], rax
0x1012abd6e  movzx   ecx, word ptr [rax+4]
0x1012abd72  shl     rcx, 20h
0x1012abd76  mov     eax, [rax]
0x1012abd78  or      rcx, rax
0x1012abd7b  shl     rcx, 10h
0x1012abd7f  mov     [rsp+33C8h+var_1680], rcx
0x1012abd87  mov     rax, [rbx+7D0h]
0x1012abd8e  cmp     rax, rcx
0x1012abd91  jnz     short loc_1012ABDB3
0x1012abd93  dec     rax
0x1012abd96  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1012abd9a  ja      short loc_1012ABDB3
0x1012abd9c  mov     [rsp+33C8h+var_3308], 1
0x1012abda4  mov     r14, 7FFFFFFFFFFFFFFFh
0x1012abdae  jmp     loc_1012ABF1E
0x1012abdb3  mov     [rsp+33C8h+var_3308], dil
0x1012abdbb  mov     rax, [rbx+7D8h]
0x1012abdc2  cmp     rax, rcx
0x1012abdc5  jnz     short loc_1012ABDE7
0x1012abdc7  dec     rax
0x1012abdca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1012abdce  ja      short loc_1012ABDE7
0x1012abdd0  mov     [rsp+33C8h+var_3307], 1
0x1012abdd8  mov     r14, 7FFFFFFFFFFFFFFFh
0x1012abde2  jmp     loc_1012ABF1E
0x1012abde7  mov     [rsp+33C8h+var_3307], dil
0x1012abdef  mov     rdx, gs:58h
0x1012abdf8  mov     [rsp+33C8h+var_1678], rdx
0x1012abe00  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1012abe07  mov     ecx, [rax]
0x1012abe09  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1012abe10  mov     ebx, [rax]
0x1012abe12  add     rbx, [rdx+rcx*8]
0x1012abe16  mov     [rsp+33C8h+var_1670], rbx
0x1012abe1e  mov     r8, [rbx+100h]
0x1012abe25  mov     [rsp+33C8h+var_26F8], r8
0x1012abe2d  test    r8, r8
0x1012abe30  jnz     short loc_1012ABE49
0x1012abe32  xor     ecx, ecx
0x1012abe34  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1012abe3a  mov     r8, [rbx+100h]
0x1012abe41  mov     [rsp+33C8h+var_26F8], r8
0x1012abe49  mov     [rsp+33C8h+var_1668], r8
0x1012abe51  rdtsc
0x1012abe53  shl     rdx, 20h
0x1012abe57  or      rax, rdx
0x1012abe5a  mov     [rsp+33C8h+var_1660], rax
0x1012abe62  mov     rdx, [r8+340h]
0x1012abe69  mov     r14, 7FFFFFFFFFFFFFFFh
0x1012abe73  cmp     rax, rdx
0x1012abe76  ja      short loc_1012ABEF5
0x1012abe78  cmp     rdx, r14
0x1012abe7b  jz      short loc_1012ABE90
0x1012abe7d  mov     rcx, [r8+260h]
0x1012abe84  sub     rdx, rax
0x1012abe87  cmp     rdx, [rcx+0DF0h]
0x1012abe8e  ja      short loc_1012ABEF5
0x1012abe90  mov     rax, [r8+258h]
0x1012abe97  mov     [rsp+33C8h+var_26F0], rax
0x1012abe9f  add     rax, 0BCh
0x1012abea5  mov     [rsp+33C8h+var_1658], rax
0x1012abead  mov     eax, [rax]
0x1012abeaf  test    al, 4
0x1012abeb1  jz      short loc_1012ABEEC
0x1012abeb3  mov     rax, [rsp+33C8h+var_26F0]
0x1012abebb  mov     rcx, [rax+98h]
0x1012abec2  mov     [rsp+33C8h+var_1650], rcx
0x1012abeca  test    byte ptr [rcx+268h], 1
  ... truncated ...
```
