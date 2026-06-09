# MoveOneIAMPageInternal(AllocUnitId const &,PageId const &,PageId const &,XDES *,uint,HoBtAccess *,IAMPageRef &,IAMPageRef &)

- ea: `0x101658480`
- end: `0x10165ba90`
- name: `?MoveOneIAMPageInternal@@YA?AW4MOVE_IAM_PAGE_RESULT@@AEBVAllocUnitId@@AEBVPageId@@1PEAVXDES@@IPEAVHoBtAccess@@AEAVIAMPageRef@@4@Z`
- size: `13840`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1016576a0`
- `0x101657f00`

## callees

- `0x100401490`
- `0x100403030`
- `0x10040da80`
- `0x100441e00`
- `0x100445640`
- `0x1004556e0`
- `0x100456310`
- `0x1004729d0`
- `0x10047bc10`
- `0x10047ffb0`
- `0x100480030`
- `0x100481160`
- `0x1005742f0`
- `0x1005d16f0`
- `0x1012c9010`
- `0x101658480`
- `0x1016c9e80`
- `0x1018c9d70`
- `0x1021d8a90`
- `0x1021eab40`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x101658690`
- `KERNEL32!VirtualProtect` at `0x10165881f`
- `KERNEL32!VirtualProtect` at `0x10165b4bc`
- `KERNEL32!VirtualProtect` at `0x10165b660`
- `KERNEL32!VirtualProtect` at `0x10165b860`
- `KERNEL32!VirtualProtect` at `0x101658690`
- `KERNEL32!VirtualProtect` at `0x10165881f`
- `KERNEL32!VirtualProtect` at `0x10165b4bc`
- `KERNEL32!VirtualProtect` at `0x10165b660`
- `KERNEL32!VirtualProtect` at `0x10165b860`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016588bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101658ccf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101658d65`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101658f89`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659025`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165915b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659234`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165930a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016595ed`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016596ad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659828`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659903`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016599db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659cb4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659d76`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659e67`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a1ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a237`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a440`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a4e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a60e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a6e6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a7cb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165aaad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165ab6f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165ad0d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165ade5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165aebc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165b19f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165b261`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165b32c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016588bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101658ccf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101658d65`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101658f89`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659025`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165915b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659234`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165930a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016595ed`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016596ad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659828`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659903`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016599db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659cb4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659d76`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101659e67`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a1ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a237`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a440`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a4e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a60e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a6e6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165a7cb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165aaad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165ab6f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165ad0d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165ade5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165aebc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165b19f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165b261`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10165b32c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659137`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659210`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016592e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016595c9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659689`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659802`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016598dd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016599b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659c8e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659d50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165a5ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165a6c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165a7a7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165aa89`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165ab4b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165ace9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165adc1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165ae98`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165b17b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165b23d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165b781`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659137`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659210`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016592e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016595c9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659689`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659802`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016598dd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016599b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659c8e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101659d50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165a5ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165a6c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165a7a7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165aa89`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165ab4b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165ace9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165adc1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165ae98`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165b17b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165b23d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10165b781`
- `sqldk!SystemThread_TlsIndex` at `0x1016590e4`
- `sqldk!SystemThread_TlsIndex` at `0x1016591bd`
- `sqldk!SystemThread_TlsIndex` at `0x101659293`
- `sqldk!SystemThread_TlsIndex` at `0x101659576`
- `sqldk!SystemThread_TlsIndex` at `0x101659636`
- `sqldk!SystemThread_TlsIndex` at `0x1016597af`
- `sqldk!SystemThread_TlsIndex` at `0x10165988a`
- `sqldk!SystemThread_TlsIndex` at `0x101659962`
- `sqldk!SystemThread_TlsIndex` at `0x101659c3b`
- `sqldk!SystemThread_TlsIndex` at `0x101659cfd`
- `sqldk!SystemThread_TlsIndex` at `0x10165a597`
- `sqldk!SystemThread_TlsIndex` at `0x10165a66f`
- `sqldk!SystemThread_TlsIndex` at `0x10165a754`
- `sqldk!SystemThread_TlsIndex` at `0x10165aa36`
- `sqldk!SystemThread_TlsIndex` at `0x10165aaf8`
- `sqldk!SystemThread_TlsIndex` at `0x10165ac96`
- `sqldk!SystemThread_TlsIndex` at `0x10165ad6e`
- `sqldk!SystemThread_TlsIndex` at `0x10165ae45`
- `sqldk!SystemThread_TlsIndex` at `0x10165b128`
- `sqldk!SystemThread_TlsIndex` at `0x10165b1ea`
- `sqldk!SystemThread_TlsOffset` at `0x1016590ed`
- `sqldk!SystemThread_TlsOffset` at `0x1016591c6`
- `sqldk!SystemThread_TlsOffset` at `0x10165929c`
- `sqldk!SystemThread_TlsOffset` at `0x10165957f`
- `sqldk!SystemThread_TlsOffset` at `0x10165963f`
- `sqldk!SystemThread_TlsOffset` at `0x1016597b8`
- `sqldk!SystemThread_TlsOffset` at `0x101659893`
- `sqldk!SystemThread_TlsOffset` at `0x10165996b`
- `sqldk!SystemThread_TlsOffset` at `0x101659c44`
- `sqldk!SystemThread_TlsOffset` at `0x101659d06`
- `sqldk!SystemThread_TlsOffset` at `0x10165a5a0`
- `sqldk!SystemThread_TlsOffset` at `0x10165a678`
- `sqldk!SystemThread_TlsOffset` at `0x10165a75d`
- `sqldk!SystemThread_TlsOffset` at `0x10165aa3f`
- `sqldk!SystemThread_TlsOffset` at `0x10165ab01`
- `sqldk!SystemThread_TlsOffset` at `0x10165ac9f`
- `sqldk!SystemThread_TlsOffset` at `0x10165ad77`
- `sqldk!SystemThread_TlsOffset` at `0x10165ae4e`
- `sqldk!SystemThread_TlsOffset` at `0x10165b131`
- `sqldk!SystemThread_TlsOffset` at `0x10165b1f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MoveOneIAMPageInternal(
        struct AllocUnitId *a1,
        __int64 a2,
        __int64 a3,
        XDES *a4,
        unsigned int a5,
        __int64 a6,
        __int16 *a7,
        PageRef *a8)
{
  struct AllocUnitId *v9; // rsi
  __int16 *v10; // r12
  int v11; // ebx
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 FCB; // r14
  __int64 *v15; // r9
  __int64 v16; // r8
  __int64 v17; // rdx
  __int16 v18; // cx
  __int16 v19; // ax
  int v20; // esi
  __int64 *v21; // rdi
  __int64 v22; // rcx
  XDES *v23; // r14
  __int64 result; // rax
  BUF *v25; // rcx
  int v26; // esi
  BUF *v27; // rdi
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 v30; // rsi
  __int64 v31; // rcx
  __int64 *v32; // rsi
  __int64 v33; // rax
  int v34; // edx
  __int16 v35; // cx
  struct AllocUnitId *v36; // rdi
  __int64 v37; // rdx
  __int16 v38; // cx
  __int64 v39; // rsi
  unsigned int v40; // r14d
  __int128 *v41; // rdi
  unsigned __int8 *v42; // r12
  char v43; // al
  __int16 v44; // r11
  unsigned __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // r13
  unsigned __int8 *v48; // r8
  unsigned __int8 v49; // dl
  __int16 v50; // dx
  __int16 v51; // cx
  unsigned __int16 v52; // ax
  unsigned int v53; // ecx
  int v54; // eax
  int v55; // eax
  int v56; // ecx
  int v57; // r15d
  __int64 v58; // rax
  unsigned __int8 *v59; // rax
  __int16 v60; // cx
  PageComprInfoCache *v61; // rcx
  int v62; // r15d
  unsigned __int16 *v63; // r8
  char v64; // dl
  unsigned __int16 v65; // cx
  __int16 v66; // ax
  __int16 v67; // r8
  unsigned int v68; // edx
  char *v69; // rsi
  unsigned __int16 v70; // r8
  __int64 v71; // rax
  __int64 v72; // rax
  unsigned int v73; // r10d
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  char *v78; // rax
  unsigned int v79; // edi
  unsigned __int16 v80; // r9
  char *v81; // r8
  __int16 v82; // r9
  __int16 v83; // cx
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v85; // r9
  __int64 v86; // rdx
  int v87; // r8d
  __int16 v88; // ax
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rax
  char v93; // cl
  bool v94; // zf
  unsigned int v95; // r15d
  char *v96; // rsi
  unsigned __int16 v97; // r8
  __int64 v98; // rax
  __int64 v99; // rax
  unsigned int v100; // r10d
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  char *v105; // rax
  unsigned int v106; // edi
  unsigned __int16 v107; // r9
  char *v108; // r8
  __int16 v109; // ax
  __int16 v110; // cx
  struct RecVersioningInfo *v111; // rax
  __int64 v112; // r9
  __int64 v113; // rdx
  int v114; // r8d
  __int16 v115; // ax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rax
  char v120; // cl
  bool v121; // zf
  __int64 v122; // rdx
  __int64 v123; // r15
  __int128 *v124; // rdi
  unsigned __int8 *v125; // r13
  char v126; // al
  __int16 v127; // r11
  unsigned __int64 v128; // rcx
  __int64 v129; // rcx
  __int64 v130; // r12
  unsigned __int8 *v131; // r8
  unsigned __int8 v132; // dl
  __int16 v133; // dx
  __int16 v134; // cx
  unsigned __int16 v135; // ax
  unsigned int v136; // ecx
  int v137; // eax
  int v138; // eax
  int v139; // ecx
  int v140; // esi
  __int64 v141; // rax
  unsigned __int8 *v142; // rax
  __int16 v143; // cx
  PageComprInfoCache *v144; // rcx
  int v145; // esi
  unsigned __int16 *v146; // r8
  char v147; // dl
  unsigned __int16 v148; // cx
  __int16 v149; // ax
  __int16 v150; // r8
  char *v151; // rsi
  unsigned __int16 v152; // dx
  __int64 v153; // rax
  __int64 v154; // rax
  unsigned int v155; // r8d
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  char *v160; // rax
  unsigned int v161; // edi
  unsigned __int16 v162; // r9
  char *v163; // rdx
  __int16 v164; // ax
  __int16 v165; // cx
  struct RecVersioningInfo *v166; // rax
  __int64 v167; // r9
  __int64 v168; // rdx
  int v169; // r8d
  __int16 v170; // ax
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rax
  __int64 v174; // rax
  char v175; // cl
  int v176; // r15d
  char *v177; // rsi
  unsigned __int16 v178; // dx
  __int64 v179; // rax
  __int64 v180; // rax
  unsigned int v181; // r8d
  __int64 v182; // rax
  __int64 v183; // rax
  __int64 v184; // rax
  __int64 v185; // rax
  char *v186; // rax
  unsigned int v187; // edi
  unsigned __int16 v188; // r9
  char *v189; // rdx
  __int16 v190; // ax
  __int16 v191; // cx
  struct RecVersioningInfo *v192; // rax
  __int64 v193; // r9
  __int64 v194; // rdx
  int v195; // r8d
  __int16 v196; // ax
  __int64 v197; // rax
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // rax
  char v201; // cl
  XDES *v202; // r12
  struct AllocUnitId *v203; // r15
  unsigned int v204; // esi
  __int64 v205; // rdi
  __int64 v206; // rcx
  unsigned int v207; // esi
  __int64 v208; // rdi
  __int64 v209; // rcx
  __int64 v210; // rdi
  int v211; // r14d
  unsigned int v212; // esi
  HoBtAccess *v213; // r13
  __int64 v214; // rax
  char v215; // r15
  int v216; // r13d
  __int64 *v217; // rdi
  __int64 v218; // rcx
  __int16 v219; // [rsp+20h] [rbp-F0h]
  __int64 v220; // [rsp+28h] [rbp-E8h]
  XDES *v221; // [rsp+30h] [rbp-E0h]
  unsigned int v222; // [rsp+30h] [rbp-E0h]
  __int64 v223; // [rsp+30h] [rbp-E0h]
  int v224; // [rsp+40h] [rbp-D0h]
  int v225; // [rsp+90h] [rbp-80h] BYREF
  __int16 v226; // [rsp+94h] [rbp-7Ch]
  unsigned int v227; // [rsp+98h] [rbp-78h]
  int v228; // [rsp+9Ch] [rbp-74h] BYREF
  __int16 v229; // [rsp+A0h] [rbp-70h]
  int v230; // [rsp+A4h] [rbp-6Ch] BYREF
  __int16 v231; // [rsp+A8h] [rbp-68h]
  __int64 v232; // [rsp+B0h] [rbp-60h] BYREF
  char v233; // [rsp+B8h] [rbp-58h]
  int v234; // [rsp+BCh] [rbp-54h]
  __int64 v235; // [rsp+C8h] [rbp-48h] BYREF
  char v236; // [rsp+D0h] [rbp-40h]
  int v237; // [rsp+D4h] [rbp-3Ch]
  __int64 v238; // [rsp+E0h] [rbp-30h] BYREF
  struct AllocUnitId *v239; // [rsp+E8h] [rbp-28h]
  __int64 v240; // [rsp+F0h] [rbp-20h] BYREF
  int v241; // [rsp+F8h] [rbp-18h]
  unsigned __int64 v242; // [rsp+100h] [rbp-10h] BYREF
  __int16 v243; // [rsp+108h] [rbp-8h]
  unsigned __int64 v244; // [rsp+110h] [rbp+0h] BYREF
  __int16 v245; // [rsp+118h] [rbp+8h]
  _DWORD v246[2]; // [rsp+120h] [rbp+10h] BYREF
  __int16 v247; // [rsp+128h] [rbp+18h]
  int v248; // [rsp+12Ch] [rbp+1Ch]
  __int16 v249; // [rsp+130h] [rbp+20h]
  int v250; // [rsp+134h] [rbp+24h]
  __int16 v251; // [rsp+138h] [rbp+28h]
  int v252; // [rsp+13Ch] [rbp+2Ch] BYREF
  __int16 v253; // [rsp+140h] [rbp+30h]
  int v254; // [rsp+144h] [rbp+34h]
  __int16 v255; // [rsp+148h] [rbp+38h]
  int v256; // [rsp+14Ch] [rbp+3Ch]
  __int16 v257; // [rsp+150h] [rbp+40h]
  int v258; // [rsp+158h] [rbp+48h] BYREF
  __int16 v259; // [rsp+15Ch] [rbp+4Ch]
  __int16 v260; // [rsp+15Eh] [rbp+4Eh]
  XDES *v261; // [rsp+160h] [rbp+50h]
  __int64 v262; // [rsp+168h] [rbp+58h]
  __int64 v263; // [rsp+170h] [rbp+60h] BYREF
  __int64 v264; // [rsp+178h] [rbp+68h]
  int v265; // [rsp+180h] [rbp+70h] BYREF
  __int16 v266; // [rsp+184h] [rbp+74h]
  int v267; // [rsp+188h] [rbp+78h] BYREF
  __int16 v268; // [rsp+18Ch] [rbp+7Ch]
  __int16 *v269; // [rsp+190h] [rbp+80h]
  BUF **v270; // [rsp+198h] [rbp+88h]
  __int64 v271; // [rsp+1A0h] [rbp+90h]
  __int64 v272; // [rsp+1A8h] [rbp+98h] BYREF
  DWORD flOldProtect; // [rsp+1B0h] [rbp+A0h] BYREF
  DWORD v274; // [rsp+1B4h] [rbp+A4h] BYREF
  DWORD v275; // [rsp+1B8h] [rbp+A8h] BYREF
  DWORD v276; // [rsp+1BCh] [rbp+ACh] BYREF
  DWORD v277; // [rsp+1C0h] [rbp+B0h] BYREF
  HoBtAccess *v278; // [rsp+1C8h] [rbp+B8h]
  __int64 v279; // [rsp+1D0h] [rbp+C0h]
  __int16 v280; // [rsp+1D8h] [rbp+C8h]
  unsigned __int16 v281; // [rsp+1DAh] [rbp+CAh] BYREF
  int v282; // [rsp+1DCh] [rbp+CCh]
  unsigned __int16 *v283; // [rsp+1E0h] [rbp+D0h]
  __int128 *v284; // [rsp+1E8h] [rbp+D8h]
  _BYTE v285[24]; // [rsp+1F0h] [rbp+E0h]
  int v286; // [rsp+208h] [rbp+F8h]
  int v287; // [rsp+20Ch] [rbp+FCh]
  __int128 v288; // [rsp+210h] [rbp+100h] BYREF
  __int128 v289; // [rsp+220h] [rbp+110h]
  _BYTE v290[22]; // [rsp+230h] [rbp+120h] BYREF
  __int16 v291; // [rsp+246h] [rbp+136h]
  __int64 v292; // [rsp+248h] [rbp+138h]
  __int128 v293; // [rsp+250h] [rbp+140h]
  __int128 v294; // [rsp+260h] [rbp+150h]
  __int128 v295; // [rsp+270h] [rbp+160h]
  __int64 v296; // [rsp+280h] [rbp+170h]

  v279 = -2;
  v261 = a4;
  v271 = a3;
  v9 = a1;
  v239 = a1;
  v278 = (HoBtAccess *)a6;
  v10 = a7;
  v269 = a7;
  v270 = (BUF **)a8;
  v280 = -1;
  v11 = 0;
  v283 = 0;
  v282 = 0;
  *(_QWORD *)&v285[6] = 0;
  *(_QWORD *)&v285[16] = 0;
  v284 = 0;
  v12 = *((_QWORD *)a4 + 6);
  v262 = v12;
  v246[0] = 0;
  v240 = 0;
  if ( a6 )
  {
    v13 = *(_QWORD *)(a6 + 20);
    LODWORD(v240) = v13;
    WORD2(v240) = WORD2(v13);
  }
  FCB = FileMgr::GetFCB(*(_QWORD *)(v12 + 1696), *(unsigned __int16 *)(a3 + 4), 0);
  IAMPageRef::Fix(a7, a3, 2, v12);
  v15 = *(__int64 **)a7;
  v16 = **(_QWORD **)a7;
  v17 = *(unsigned __int16 *)(v16 + 8190);
  v246[1] = *(_DWORD *)(v17 + v16 + 40);
  v247 = *(_WORD *)(v17 + v16 + 44);
  if ( *(_DWORD *)v9 != *(_DWORD *)(v16 + 24) )
    goto LABEL_672;
  v18 = 0;
  if ( *((_WORD *)v9 + 2) != 1 )
    v18 = *((_WORD *)v9 + 2);
  v19 = 0;
  if ( *(_WORD *)(v16 + 6) != 1 )
    v19 = *(_WORD *)(v16 + 6);
  if ( v18 != v19 )
  {
LABEL_672:
    if ( (*((_WORD *)v15 + 49) & 0x400) != 0 && a7[6] >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)a7);
      return 2;
    }
    v216 = a7[6];
    v217 = *(__int64 **)a7;
    if ( (*(_WORD *)(*(_QWORD *)a7 + 98LL) & 8) != 0 )
    {
      if ( v216 == 3 )
      {
        v216 = 4;
LABEL_678:
        if ( (*((_DWORD *)v217 + 25) & 8) != 0 )
        {
          v218 = v217[18];
          if ( v218 )
          {
            if ( *(_QWORD *)(v218 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v218 + 1880), *(_QWORD *)a7, (unsigned int)v216);
            }
          }
        }
        goto LABEL_682;
      }
      if ( v216 >= 2 )
        goto LABEL_678;
    }
LABEL_682:
    if ( byte_10317ABE5 < 0
      && (*((_DWORD *)v217 + 25) & 8) != 0
      && v216 >= 3
      && (*((_DWORD *)v217 + 25) & 0xC0000000) != 0x40000000
      && *v217
      && VirtualProtect((LPVOID)*v217, 0x2000u, 2u, &v277) )
    {
      _InterlockedAnd((volatile signed __int32 *)v217 + 25, 0x3FFFFFFFu);
      _InterlockedOr((volatile signed __int32 *)v217 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal(v217 + 19, (unsigned int)v216);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v217, 0, (unsigned int)v216);
    a7[6] = 0;
    *(_QWORD *)a7 = 0;
    return 2;
  }
  if ( (*((_WORD *)v15 + 49) & 0x400) != 0 && a7[6] >= 3 )
  {
    PageRef::UnfixLatchOnly((PageRef *)a7);
    goto LABEL_31;
  }
  v20 = a7[6];
  v21 = *(__int64 **)a7;
  if ( (*(_WORD *)(*(_QWORD *)a7 + 98LL) & 8) != 0 )
  {
    if ( v20 == 3 )
    {
      v20 = 4;
LABEL_16:
      if ( (*((_DWORD *)v21 + 25) & 8) != 0 )
      {
        v22 = v21[18];
        if ( v22 )
        {
          if ( *(_QWORD *)(v22 + 1880) )
          {
            _mm_lfence();
            DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v22 + 1880), *(_QWORD *)a7, (unsigned int)v20);
          }
        }
      }
      goto LABEL_20;
    }
    if ( v20 >= 2 )
      goto LABEL_16;
  }
LABEL_20:
  if ( byte_10317ABE5 < 0
    && (*((_DWORD *)v21 + 25) & 8) != 0
    && v20 >= 3
    && (*((_DWORD *)v21 + 25) & 0xC0000000) != 0x40000000
    && *v21
    && VirtualProtect((LPVOID)*v21, 0x2000u, 2u, &flOldProtect) )
  {
    _InterlockedAnd((volatile signed __int32 *)v21 + 25, 0x3FFFFFFFu);
    _InterlockedOr((volatile signed __int32 *)v21 + 25, 0x40000000u);
  }
  LatchBase::ReleaseInternal(v21 + 19, (unsigned int)v20);
  if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
    BUF::TraceLatchAcquireRelease(v21, 0, (unsigned int)v20);
  a7[6] = 0;
  *(_QWORD *)a7 = 0;
  v9 = v239;
LABEL_31:
  v258 = *(_DWORD *)v9;
  v259 = *((_WORD *)v9 + 2);
  v260 = 0;
  v219 = *(_WORD *)(FCB + 132);
  v23 = v261;
  result = AllocIAMPage(v261, v261, a5, 0, v219, &v258, &v240);
  if ( !(_DWORD)result )
    return result;
  v25 = *(BUF **)a8;
  v225 = *(_DWORD *)(*(_QWORD *)a8 + 112LL);
  v226 = *((_WORD *)v25 + 58);
  if ( v25 )
  {
    if ( (*((_WORD *)v25 + 49) & 0x400) != 0 && *((__int16 *)a8 + 6) >= 3 )
    {
      PageRef::UnfixLatchOnly(a8);
      goto LABEL_55;
    }
    v26 = *((__int16 *)a8 + 6);
    v27 = *(BUF **)a8;
    if ( (*(_WORD *)(*(_QWORD *)a8 + 98LL) & 8) == 0 )
      goto LABEL_44;
    if ( v26 == 3 )
    {
      v26 = 4;
    }
    else if ( v26 < 2 )
    {
LABEL_44:
      if ( byte_10317ABE5 < 0
        && (*((_DWORD *)v27 + 25) & 8) != 0
        && v26 >= 3
        && (*((_DWORD *)v27 + 25) & 0xC0000000) != 0x40000000
        && *(_QWORD *)v27
        && VirtualProtect(*(LPVOID *)v27, 0x2000u, 2u, &v274) )
      {
        _InterlockedAnd((volatile signed __int32 *)v27 + 25, 0x3FFFFFFFu);
        _InterlockedOr((volatile signed __int32 *)v27 + 25, 0x40000000u);
      }
      LatchBase::ReleaseInternal((char *)v27 + 152, (unsigned int)v26);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v27, 0, (unsigned int)v26);
      *((_WORD *)a8 + 6) = 0;
      *(_QWORD *)a8 = 0;
      goto LABEL_55;
    }
    if ( (*((_DWORD *)v27 + 25) & 8) != 0 )
    {
      v28 = *((_QWORD *)v27 + 18);
      if ( v28 )
      {
        if ( *(_QWORD *)(v28 + 1880) )
        {
          _mm_lfence();
          DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v28 + 1880), *(_QWORD *)a8, (unsigned int)v26);
        }
      }
    }
    goto LABEL_44;
  }
LABEL_55:
  v29 = v262;
  v30 = v271;
  IAMPageRef::Fix(a7, v271, 4, v262);
  v31 = **(_QWORD **)a7;
  if ( *(_DWORD *)v30 != *(_DWORD *)(v31 + 32) || *(_WORD *)(v30 + 4) != *(_WORD *)(v31 + 36) )
    utassert_fail(1u, "sourcePageId == oldIAMPageRef.GetPagePtr()->GetId()", "SpaceMgrMaintenance.cpp", 2020, 0);
  IAMPageRef::Fix(a8, &v225, 4, v29);
  v32 = *(__int64 **)a7;
  v33 = **(_QWORD **)a7;
  v34 = *(_DWORD *)(v33 + 8);
  v35 = *(_WORD *)(v33 + 12);
  v230 = v34;
  v231 = v35;
  if ( v34 || v35 )
  {
    v248 = v34;
    v249 = v35;
    v221 = v23;
    LODWORD(v220) = 0;
    v36 = v239;
    PageRef::ModifyHeader(a8, v239, 8);
    v32 = *(__int64 **)a7;
  }
  else
  {
    v36 = v239;
  }
  v37 = *(unsigned int *)(*v32 + 16);
  v38 = *(_WORD *)(*v32 + 20);
  v228 = v37;
  v229 = v38;
  if ( (_DWORD)v37 || v38 )
  {
    v250 = v37;
    v251 = v38;
    v221 = v23;
    LODWORD(v220) = 0;
    PageRef::ModifyHeader(a8, v36, 16);
    v32 = *(__int64 **)a7;
  }
  v39 = *v32;
  v287 = 0;
  v227 = 9;
  v40 = 15;
  if ( *(char *)(v39 + 2) >= 0 )
  {
    v41 = 0;
    goto LABEL_114;
  }
  v42 = (unsigned __int8 *)(v39 + 96);
  _mm_prefetch((const char *)(v39 + 96), 0);
  if ( !v280 || (v41 = v284) == 0 )
  {
    v291 = 0;
    v293 = 0u;
    v294 = 0;
    v296 = 0;
    v288 = 0;
    v289 = 0xFFFFu;
    v292 = 0;
    memset(v290, 0, sizeof(v290));
    v295 = 0u;
    v41 = &v288;
  }
  if ( !*(_WORD *)(v39 + 36) )
    goto LABEL_79;
  v43 = *(_BYTE *)(v39 + 1);
  if ( v43 != 11 )
  {
    if ( v43 == 8 )
    {
LABEL_76:
      if ( *(_DWORD *)(v39 + 24) == 99 )
        goto LABEL_77;
LABEL_79:
      v242 = *(_QWORD *)(v39 + 40);
      v44 = *(_WORD *)(v39 + 48);
      v243 = v44;
      goto LABEL_80;
    }
LABEL_75:
    if ( v43 != 9 )
      goto LABEL_79;
    goto LABEL_76;
  }
  if ( *(_DWORD *)(v39 + 24) != 99 )
    goto LABEL_75;
LABEL_77:
  v267 = *(_DWORD *)(v39 + 32);
  v268 = *(_WORD *)(v39 + 36);
  if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v267, v37) )
    goto LABEL_79;
  PageHeader::GetIcxLsn(v39, &v242);
  v44 = v243;
LABEL_80:
  *(_QWORD *)v41 = v42;
  v45 = HIDWORD(v242);
  *((_DWORD *)v41 + 24) = v242;
  *((_DWORD *)v41 + 25) = v45;
  *((_WORD *)v41 + 52) = v44;
  *((_DWORD *)v41 + 27) = *(_DWORD *)(v39 + 32);
  *((_WORD *)v41 + 56) = *(_WORD *)(v39 + 36);
  *((_WORD *)v41 + 57) = 0;
  v46 = 3LL * *v42;
  v241 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v42);
  v47 = word_102883984[v46];
  *((_WORD *)v41 + 8) = -1;
  *((_QWORD *)v41 + 3) = 0;
  *((_DWORD *)v41 + 5) = 0;
  *(_QWORD *)((char *)v41 + 46) = 0;
  *((_QWORD *)v41 + 7) = 0;
  *((_QWORD *)v41 + 4) = 0;
  *((_QWORD *)v41 + 9) = 0;
  *((_QWORD *)v41 + 10) = 0;
  *((_WORD *)v41 + 44) = 0;
  if ( (**(_BYTE **)v41 & 2) != 0 )
  {
    v48 = &v42[v47];
    if ( (v42[v47] & 1) != 0 )
    {
      *((_WORD *)v41 + 8) = 1;
      *((_QWORD *)v41 + 3) = v48;
      v49 = *v48;
      switch ( *v48 & 0x1C )
      {
        case 0:
        case 0xC:
        case 0x10:
        case 0x14:
        case 0x18:
        case 0x1C:
          if ( (v48[1] & 0x80u) != 0 )
          {
            v52 = *(_WORD *)(v48 + 1);
            *((_WORD *)v41 + 9) = v52;
            v50 = 3;
            v51 = HIBYTE(v52) | ((v52 & 0x7F) << 8);
          }
          else
          {
            v50 = 2;
            v51 = v48[1];
          }
          *((_WORD *)v41 + 9) = v51;
          *((_WORD *)v41 + 20) = v50;
          v53 = *((unsigned __int16 *)v41 + 9);
          *((_WORD *)v41 + 22) = v50 + ((v53 + 1) >> 1);
          if ( v53 > 0x1E )
            *((_WORD *)v41 + 21) = (int)(v53 - 1) / 30;
          else
            *((_WORD *)v41 + 21) = 0;
          *((_DWORD *)v41 + 5) = 0;
          *((_DWORD *)v41 + 16) = 0;
          *((_QWORD *)v41 + 7) = 0;
          *((_QWORD *)v41 + 4) = 0;
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
          *((_QWORD *)v41 + 7) = 0;
          *((_QWORD *)v41 + 4) = 0;
          break;
        case 4:
          if ( (v49 & 0x1C) != 4 || (v54 = 1, (v49 & 2) == 0) )
            v54 = 0;
          if ( v54 )
          {
            *((_DWORD *)v41 + 16) = 0;
            v55 = 1;
            v56 = 15;
          }
          else
          {
            v55 = 0;
            v56 = 1;
          }
          *((_QWORD *)v41 + 5) = 0;
          *((_WORD *)v41 + 9) = 0;
          *((_QWORD *)v41 + 6) = 0;
          *((_QWORD *)v41 + 4) = 0;
          *((_QWORD *)v41 + 7) = 0;
          *((_QWORD *)v41 + 3) = v48;
          *((_DWORD *)v41 + 5) = v56;
          *((_DWORD *)v41 + 16) = v55;
          *((_QWORD *)v41 + 7) = 0;
          *((_QWORD *)v41 + 4) = 0;
          break;
        case 8:
          *((_QWORD *)v41 + 5) = 0;
          *((_WORD *)v41 + 9) = 0;
          *((_QWORD *)v41 + 6) = 0;
          *((_QWORD *)v41 + 4) = 0;
          *((_QWORD *)v41 + 7) = 0;
          *((_QWORD *)v41 + 3) = v48;
          *((_DWORD *)v41 + 5) = 9;
          *((_DWORD *)v41 + 16) = 0;
          *((_QWORD *)v41 + 7) = 0;
          *((_QWORD *)v41 + 4) = 0;
          break;
      }
    }
    else
    {
      *((_WORD *)v41 + 8) = 0;
      v57 = 0;
      *((_QWORD *)v41 + 3) = v48;
      *((_DWORD *)v41 + 5) = 0;
      *(_DWORD *)((char *)v41 + 54) = 0;
      switch ( *v48 & 0xE )
      {
        case 0:
        case 2:
        case 8:
        case 0xC:
          v57 = *((unsigned __int16 *)v48 + 1);
          if ( (unsigned int)(v57 - 1) > 0x1F9D )
            RaiseInconsistencyError(&v42[v47], 6);
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
          v57 = 9;
          break;
        case 6:
        case 0xA:
          break;
        case 0xE:
          v57 = 1;
          break;
      }
      *((_DWORD *)v41 + 8) = v57;
      *(_QWORD *)((char *)v41 + 46) = 0;
    }
  }
  if ( (**(_BYTE **)v41 & 4) != 0 )
  {
    if ( HIWORD(v241) )
      v58 = *(unsigned __int16 *)&v42[2 * SHIWORD(v241) + 1];
    else
      v58 = v47;
    v59 = &v42[v58];
    *((_QWORD *)v41 + 9) = v59;
    v60 = *(_WORD *)v59;
    *((_QWORD *)v41 + 10) = v59 + 2;
    *((_WORD *)v41 + 44) = 2 * (v60 + 1);
  }
  v61 = (PageComprInfoCache *)*((_QWORD *)v41 + 1);
  if ( v61 )
    PageComprInfoCache::Init(v61, (const struct PageComprInfo *)v41);
  v10 = v269;
LABEL_114:
  v62 = *(unsigned __int16 *)(v39 + 14);
  v63 = (unsigned __int16 *)(v39 + *(unsigned __int16 *)(v39 + 8190));
  v94 = (*(_BYTE *)v63 & 1) == 0;
  v283 = v63;
  if ( v94 )
  {
    v280 = 0;
    v68 = 0;
    v282 = 0;
    *(_DWORD *)&v285[14] = 0;
    switch ( *(_BYTE *)v63 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v62 = v63[1];
        if ( (unsigned int)(v62 - 1) > 0x1F9D )
        {
          RaiseInconsistencyError(v63, 6);
          goto LABEL_136;
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
LABEL_136:
        v68 = v282;
        break;
      case 4:
        v62 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v62 = 1;
        break;
    }
    LODWORD(v284) = v62;
    *(_QWORD *)&v285[6] = v39 + 0x2000;
    LODWORD(v41) = v62;
  }
  else
  {
    v280 = 1;
    v64 = *(_BYTE *)v63;
    switch ( *(_BYTE *)v63 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( *((char *)v63 + 1) < 0 )
        {
          v65 = HIBYTE(*(unsigned __int16 *)((char *)v63 + 1)) | ((*(unsigned __int16 *)((char *)v63 + 1) & 0x7F) << 8);
          v281 = v65;
          v66 = 3;
          v67 = 3;
        }
        else
        {
          v65 = *((unsigned __int8 *)v63 + 1);
          v281 = v65;
          v66 = 2;
          v67 = 2;
        }
        *(_WORD *)v285 = v66;
        *(_WORD *)&v285[4] = v67 + (((unsigned int)v65 + 1) >> 1);
        if ( v65 > 0x1Eu )
          *(_WORD *)&v285[2] = (__int16)(v65 - 1) / 30;
        else
          *(_WORD *)&v285[2] = 0;
        v68 = 0;
        v282 = 0;
        v286 = 0;
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
        v68 = v282;
        break;
      case 4:
        if ( (v64 & 0x1C) == 4 && (v64 & 2) != 0 )
        {
          *(_QWORD *)v285 = 0;
          v281 = 0;
          *(_QWORD *)&v285[8] = 0;
          v68 = 15;
          v282 = 15;
          v286 = 1;
        }
        else
        {
          *(_QWORD *)v285 = 0;
          v281 = 0;
          *(_QWORD *)&v285[8] = 0;
          v68 = 1;
          v282 = 1;
          v286 = 0;
        }
        break;
      case 8:
        *(_QWORD *)v285 = 0;
        v281 = 0;
        *(_QWORD *)&v285[8] = 0;
        v68 = 9;
        v282 = 9;
        v286 = 0;
        break;
    }
    *(_QWORD *)&v285[16] = v39 + 0x2000;
    v284 = v41;
  }
  if ( !v280 )
  {
    if ( !v68 )
    {
      v281 = 0;
      HIDWORD(v284) = (_DWORD)v41;
      v68 = (unsigned int)v41;
      if ( (*(_BYTE *)v283 & 0x10) != 0 )
      {
        v68 = (((unsigned int)*(unsigned __int16 *)((char *)v283 + (unsigned int)v41) + 7) >> 3) + (_DWORD)v41 + 2;
        HIDWORD(v284) = v68;
      }
      if ( (*(_BYTE *)v283 & 0x20) != 0 )
      {
        v69 = (char *)v283 + v68;
        v70 = *(_WORD *)v69;
        *(_WORD *)&v285[4] = v70;
        if ( !v70 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v71 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v71 )
            {
              v72 = *(_QWORD *)(v71 + 96);
              if ( v72 )
              {
                if ( *(_BYTE *)(v72 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0, v220, v221);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 3);
          v70 = *(_WORD *)&v285[4];
        }
        v73 = HIDWORD(v284) + 2 + 2 * v70;
        *(_DWORD *)v285 = v73;
        if ( v73 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v74 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v74 )
            {
              v75 = *(_QWORD *)(v74 + 96);
              if ( v75 )
              {
                if ( *(_BYTE *)(v75 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 4);
          v70 = *(_WORD *)&v285[4];
          v73 = *(_DWORD *)v285;
        }
        v68 = *(_WORD *)&v69[2 * v70] & 0x7FFF;
        v282 = v68;
        if ( v73 > v68 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v76 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v76 )
            {
              v77 = *(_QWORD *)(v76 + 96);
              if ( v77 )
              {
                if ( *(_BYTE *)(v77 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 4);
          v70 = *(_WORD *)&v285[4];
          v73 = *(_DWORD *)v285;
          v68 = v282;
        }
        while ( *(__int16 *)&v69[2 * v70] < 0 )
        {
          v78 = (char *)v283 + HIDWORD(v284);
          if ( v70 == 1 )
            v79 = v73;
          else
            v79 = *(_WORD *)&v78[2 * v70 - 2] & 0x7FFF;
          if ( v79 < v73 || (*(_WORD *)&v78[2 * v70] & 0x7FFFu) < v79 )
          {
            RaiseInconsistencyError(v283, 7);
            v70 = *(_WORD *)&v285[4];
            v73 = *(_DWORD *)v285;
            v68 = v282;
          }
          if ( v79 < v73 || v79 > v68 )
            goto LABEL_226;
          v80 = *(unsigned __int16 *)((char *)v283 + v79);
          if ( v80 == 5 )
          {
            v281 |= 2u;
            *(_WORD *)&v285[4] = v70 - 1;
            *(_WORD *)&v285[18] = v79;
            v81 = (char *)v283 + (unsigned __int16)v79;
            v82 = *((_WORD *)v81 + 1);
            if ( (v82 & 0x4000) != 0 )
              v83 = (v82 ^ *(_WORD *)&v285[20]) & 0x3800 ^ *(_WORD *)&v285[20];
            else
              v83 = *(_WORD *)&v285[20] & 0xC7FF;
            *(_WORD *)&v285[20] = v83;
            *(_WORD *)&v285[20] = v83 ^ (*((_WORD *)v81 + 1) ^ v83) & 0x7FF;
            break;
          }
          if ( v80 >= 0x400u )
          {
            v281 |= 1u;
            v94 = v70-- == 1;
            *(_WORD *)&v285[4] = v70;
            if ( !v94 )
              continue;
          }
          break;
        }
      }
      else
      {
        v282 = v68;
        *(_WORD *)&v285[4] = 0;
        *(_DWORD *)v285 = v68;
      }
      if ( (*(_BYTE *)v283 & 0x40) != 0 )
      {
        *(_DWORD *)&v285[14] = v68;
        v282 = v68 + 14;
        VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v281);
        v85 = HIDWORD(*(_QWORD *)VersioningInfo);
        v86 = HIWORD(*(_QWORD *)VersioningInfo);
        v87 = 0;
        if ( (((__int16)v86 ^ ((unsigned int)(__int16)v86 >> 1)) & 0x2000) != 0 )
        {
          v88 = v86 & 0xDFFF;
          if ( (v86 & 0x4000) != 0 )
            v88 = v86 | 0x2000;
          LOWORD(v86) = v88;
        }
        if ( (_WORD)v86 == 0xFFFC )
          v87 = (unsigned __int16)v85 >> 5;
        v68 = v87 + v282;
        v282 += v87;
      }
      else
      {
        *(_DWORD *)&v285[14] = 0;
      }
      if ( *(_QWORD *)&v285[6] && *(_QWORD *)&v285[6] < (unsigned __int64)v283 + v68 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v89 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v89 )
          {
            v90 = *(_QWORD *)(v89 + 96);
            if ( v90 )
            {
              if ( *(_BYTE *)(v90 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v283, 18);
        v68 = v282;
      }
      if ( v68 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v91 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v91 )
          {
            v92 = *(_QWORD *)(v91 + 96);
            if ( v92 )
            {
              if ( *(_BYTE *)(v92 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v283, 5);
        v68 = v282;
      }
    }
LABEL_226:
    if ( v68 >= 9 )
      goto LABEL_236;
    v93 = *(_BYTE *)v283 & 0xE;
    if ( v93 )
    {
      v94 = v93 == 12;
      goto LABEL_234;
    }
LABEL_235:
    v95 = 9;
    goto LABEL_237;
  }
  if ( !v68 )
  {
    CDRecord::Resize((CDRecord *)&v281);
    v68 = v282;
  }
  if ( v68 >= 9 )
    goto LABEL_236;
  if ( (*(_BYTE *)v283 & 0x1C) == 0 )
    goto LABEL_235;
  v94 = (*(_BYTE *)v283 & 0x1C) == 12;
LABEL_234:
  if ( v94 )
    goto LABEL_235;
LABEL_236:
  v95 = v68;
LABEL_237:
  if ( v280 )
  {
    if ( !v68 )
    {
      CDRecord::Resize((CDRecord *)&v281);
      v68 = v282;
    }
    if ( v68 < 9 )
    {
      if ( (*(_BYTE *)v283 & 0x1C) != 0 )
      {
        v121 = (*(_BYTE *)v283 & 0x1C) == 12;
LABEL_333:
        if ( !v121 )
          goto LABEL_335;
      }
LABEL_334:
      v68 = 9;
    }
  }
  else
  {
    if ( !v68 )
    {
      v281 = 0;
      v68 = (unsigned int)v284;
      HIDWORD(v284) = (_DWORD)v284;
      if ( (*(_BYTE *)v283 & 0x10) != 0 )
      {
        v68 = (((unsigned int)*(unsigned __int16 *)((char *)v283 + (unsigned int)v284) + 7) >> 3) + (_DWORD)v284 + 2;
        HIDWORD(v284) = v68;
      }
      if ( (*(_BYTE *)v283 & 0x20) != 0 )
      {
        v96 = (char *)v283 + v68;
        v97 = *(_WORD *)v96;
        *(_WORD *)&v285[4] = v97;
        if ( !v97 )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 3);
          v97 = *(_WORD *)&v285[4];
        }
        v100 = HIDWORD(v284) + 2 + 2 * v97;
        *(_DWORD *)v285 = v100;
        if ( v100 > 0x1F9E )
        {
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 4);
          v97 = *(_WORD *)&v285[4];
          v100 = *(_DWORD *)v285;
        }
        v68 = *(_WORD *)&v96[2 * v97] & 0x7FFF;
        v282 = v68;
        if ( v100 > v68 )
        {
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 4);
          v97 = *(_WORD *)&v285[4];
          v100 = *(_DWORD *)v285;
          v68 = v282;
        }
        while ( *(__int16 *)&v96[2 * v97] < 0 )
        {
          v105 = (char *)v283 + HIDWORD(v284);
          if ( v97 == 1 )
            v106 = v100;
          else
            v106 = *(_WORD *)&v105[2 * v97 - 2] & 0x7FFF;
          if ( v106 < v100 || (*(_WORD *)&v105[2 * v97] & 0x7FFFu) < v106 )
          {
            RaiseInconsistencyError(v283, 7);
            v97 = *(_WORD *)&v285[4];
            v100 = *(_DWORD *)v285;
            v68 = v282;
          }
          if ( v106 < v100 || v106 > v68 )
            goto LABEL_325;
          v107 = *(unsigned __int16 *)((char *)v283 + v106);
          if ( v107 == 5 )
          {
            v281 |= 2u;
            *(_WORD *)&v285[4] = v97 - 1;
            *(_WORD *)&v285[18] = v106;
            v108 = (char *)v283 + (unsigned __int16)v106;
            v109 = *((_WORD *)v108 + 1);
            if ( (v109 & 0x4000) != 0 )
              v110 = (*(_WORD *)&v285[20] ^ v109) & 0x3800 ^ *(_WORD *)&v285[20];
            else
              v110 = *(_WORD *)&v285[20] & 0xC7FF;
            *(_WORD *)&v285[20] = v110;
            *(_WORD *)&v285[20] = v110 ^ (*((_WORD *)v108 + 1) ^ v110) & 0x7FF;
            break;
          }
          if ( v107 >= 0x400u )
          {
            v281 |= 1u;
            v94 = v97-- == 1;
            *(_WORD *)&v285[4] = v97;
            if ( !v94 )
              continue;
          }
          break;
        }
      }
      else
      {
        v282 = v68;
        *(_WORD *)&v285[4] = 0;
        *(_DWORD *)v285 = v68;
      }
      if ( (*(_BYTE *)v283 & 0x40) != 0 )
      {
        *(_DWORD *)&v285[14] = v68;
        v282 = v68 + 14;
        v111 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v281);
        v112 = HIDWORD(*(_QWORD *)v111);
        v113 = HIWORD(*(_QWORD *)v111);
        v114 = 0;
        if ( (((__int16)v113 ^ ((unsigned int)(__int16)v113 >> 1)) & 0x2000) != 0 )
        {
          v115 = v113 & 0xDFFF;
          if ( (v113 & 0x4000) != 0 )
            v115 = v113 | 0x2000;
          LOWORD(v113) = v115;
        }
        if ( (_WORD)v113 == 0xFFFC )
          v114 = (unsigned __int16)v112 >> 5;
        v68 = v114 + v282;
        v282 += v114;
      }
      else
      {
        *(_DWORD *)&v285[14] = 0;
      }
      if ( *(_QWORD *)&v285[6] && *(_QWORD *)&v285[6] < (unsigned __int64)v283 + v68 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v116 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v116 )
          {
            v117 = *(_QWORD *)(v116 + 96);
            if ( v117 )
            {
              if ( *(_BYTE *)(v117 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v283, 18);
        v68 = v282;
      }
      if ( v68 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v118 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v118 )
          {
            v119 = *(_QWORD *)(v118 + 96);
            if ( v119 )
            {
              if ( *(_BYTE *)(v119 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v283, 5);
        v68 = v282;
      }
    }
LABEL_325:
    if ( v68 < 9 )
    {
      v120 = *(_BYTE *)v283 & 0xE;
      if ( v120 )
      {
        v121 = v120 == 12;
        goto LABEL_333;
      }
      goto LABEL_334;
    }
  }
LABEL_335:
  if ( (unsigned int)PageRef::ModifyRow(v270, 0, v239, 0, 0, v68, v95, v283, 0, 0, v261, 0, 0, 0, 0, 0, 0, 0) )
    utassert_fail(1u, "insufficientSpace == 0", "SpaceMgrMaintenance.cpp", 2075, 0);
  v123 = **(_QWORD **)v10;
  v287 = 1;
  if ( *(char *)(v123 + 2) >= 0 )
  {
    v124 = 0;
    goto LABEL_385;
  }
  v125 = (unsigned __int8 *)(v123 + 96);
  _mm_prefetch((const char *)(v123 + 96), 0);
  if ( !v280 || (v124 = v284) == 0 )
  {
    v291 = 0;
    v293 = 0u;
    v294 = 0;
    v296 = 0;
    v288 = 0;
    v289 = 0xFFFFu;
    v292 = 0;
    memset(v290, 0, sizeof(v290));
    v295 = 0u;
    v124 = &v288;
  }
  if ( !*(_WORD *)(v123 + 36) )
    goto LABEL_351;
  v126 = *(_BYTE *)(v123 + 1);
  if ( v126 != 11 )
  {
    if ( v126 == 8 )
    {
LABEL_348:
      if ( *(_DWORD *)(v123 + 24) == 99 )
        goto LABEL_349;
LABEL_351:
      v244 = *(_QWORD *)(v123 + 40);
      v127 = *(_WORD *)(v123 + 48);
      v245 = v127;
      goto LABEL_352;
    }
LABEL_347:
    if ( v126 != 9 )
      goto LABEL_351;
    goto LABEL_348;
  }
  if ( *(_DWORD *)(v123 + 24) != 99 )
    goto LABEL_347;
LABEL_349:
  v265 = *(_DWORD *)(v123 + 32);
  v266 = *(_WORD *)(v123 + 36);
  if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v265, v122) )
    goto LABEL_351;
  PageHeader::GetIcxLsn(v123, &v244);
  v127 = v245;
LABEL_352:
  *(_QWORD *)v124 = v125;
  v128 = HIDWORD(v244);
  *((_DWORD *)v124 + 24) = v244;
  *((_DWORD *)v124 + 25) = v128;
  *((_WORD *)v124 + 52) = v127;
  *((_DWORD *)v124 + 27) = *(_DWORD *)(v123 + 32);
  *((_WORD *)v124 + 56) = *(_WORD *)(v123 + 36);
  *((_WORD *)v124 + 57) = 0;
  v129 = 3LL * *v125;
  v241 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v125);
  v130 = word_102883984[v129];
  *((_WORD *)v124 + 8) = -1;
  *((_QWORD *)v124 + 3) = 0;
  *((_DWORD *)v124 + 5) = 0;
  *(_QWORD *)((char *)v124 + 46) = 0;
  *((_QWORD *)v124 + 7) = 0;
  *((_QWORD *)v124 + 4) = 0;
  *((_QWORD *)v124 + 9) = 0;
  *((_QWORD *)v124 + 10) = 0;
  *((_WORD *)v124 + 44) = 0;
  if ( (**(_BYTE **)v124 & 2) != 0 )
  {
    v131 = &v125[v130];
    if ( (v125[v130] & 1) != 0 )
    {
      *((_WORD *)v124 + 8) = 1;
      *((_QWORD *)v124 + 3) = v131;
      v132 = *v131;
      switch ( *v131 & 0x1C )
      {
        case 0:
        case 0xC:
        case 0x10:
        case 0x14:
        case 0x18:
        case 0x1C:
          if ( (v131[1] & 0x80u) != 0 )
          {
            v135 = *(_WORD *)(v131 + 1);
            *((_WORD *)v124 + 9) = v135;
            v133 = 3;
            v134 = HIBYTE(v135) | ((v135 & 0x7F) << 8);
          }
          else
          {
            v133 = 2;
            v134 = v131[1];
          }
          *((_WORD *)v124 + 9) = v134;
          *((_WORD *)v124 + 20) = v133;
          v136 = *((unsigned __int16 *)v124 + 9);
          *((_WORD *)v124 + 22) = v133 + ((v136 + 1) >> 1);
          if ( v136 > 0x1E )
            *((_WORD *)v124 + 21) = (int)(v136 - 1) / 30;
          else
            *((_WORD *)v124 + 21) = 0;
          *((_DWORD *)v124 + 5) = 0;
          *((_DWORD *)v124 + 16) = 0;
          *((_QWORD *)v124 + 7) = 0;
          *((_QWORD *)v124 + 4) = 0;
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
          *((_QWORD *)v124 + 7) = 0;
          *((_QWORD *)v124 + 4) = 0;
          break;
        case 4:
          if ( (v132 & 0x1C) != 4 || (v137 = 1, (v132 & 2) == 0) )
            v137 = 0;
          if ( v137 )
          {
            *((_DWORD *)v124 + 16) = 0;
            v138 = 1;
            v139 = 15;
          }
          else
          {
            v138 = 0;
            v139 = 1;
          }
          *((_QWORD *)v124 + 5) = 0;
          *((_WORD *)v124 + 9) = 0;
          *((_QWORD *)v124 + 6) = 0;
          *((_QWORD *)v124 + 4) = 0;
          *((_QWORD *)v124 + 7) = 0;
          *((_QWORD *)v124 + 3) = v131;
          *((_DWORD *)v124 + 5) = v139;
          *((_DWORD *)v124 + 16) = v138;
          *((_QWORD *)v124 + 7) = 0;
          *((_QWORD *)v124 + 4) = 0;
          break;
        case 8:
          *((_QWORD *)v124 + 5) = 0;
          *((_WORD *)v124 + 9) = 0;
          *((_QWORD *)v124 + 6) = 0;
          *((_QWORD *)v124 + 4) = 0;
          *((_QWORD *)v124 + 7) = 0;
          *((_QWORD *)v124 + 3) = v131;
          *((_DWORD *)v124 + 5) = 9;
          *((_DWORD *)v124 + 16) = 0;
          *((_QWORD *)v124 + 7) = 0;
          *((_QWORD *)v124 + 4) = 0;
          break;
      }
    }
    else
    {
      *((_WORD *)v124 + 8) = 0;
      v140 = 0;
      *((_QWORD *)v124 + 3) = v131;
      *((_DWORD *)v124 + 5) = 0;
      *(_DWORD *)((char *)v124 + 54) = 0;
      switch ( *v131 & 0xE )
      {
        case 0:
        case 2:
        case 8:
        case 0xC:
          v140 = *((unsigned __int16 *)v131 + 1);
          if ( (unsigned int)(v140 - 1) > 0x1F9D )
            RaiseInconsistencyError(&v125[v130], 6);
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
          v140 = 9;
          break;
        case 6:
        case 0xA:
          break;
        case 0xE:
          v140 = 1;
          break;
      }
      *((_DWORD *)v124 + 8) = v140;
      *(_QWORD *)((char *)v124 + 46) = 0;
    }
  }
  if ( (**(_BYTE **)v124 & 4) != 0 )
  {
    if ( HIWORD(v241) )
      v141 = *(unsigned __int16 *)&v125[2 * SHIWORD(v241) + 1];
    else
      v141 = v130;
    v142 = &v125[v141];
    *((_QWORD *)v124 + 9) = v142;
    v143 = *(_WORD *)v142;
    *((_QWORD *)v124 + 10) = v142 + 2;
    *((_WORD *)v124 + 44) = 2 * (v143 + 1);
  }
  v144 = (PageComprInfoCache *)*((_QWORD *)v124 + 1);
  if ( v144 )
    PageComprInfoCache::Init(v144, (const struct PageComprInfo *)v124);
LABEL_385:
  v145 = *(unsigned __int16 *)(v123 + 14);
  v146 = (unsigned __int16 *)(v123 + *(unsigned __int16 *)(v123 + 8188));
  v94 = (*(_BYTE *)v146 & 1) == 0;
  v283 = v146;
  if ( v94 )
  {
    v280 = 0;
    v40 = 0;
    v282 = 0;
    *(_DWORD *)&v285[14] = 0;
    switch ( *(_BYTE *)v146 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v145 = v146[1];
        if ( (unsigned int)(v145 - 1) > 0x1F9D )
        {
          RaiseInconsistencyError(v146, 6);
          goto LABEL_407;
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
LABEL_407:
        v40 = v282;
        break;
      case 4:
        v145 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v145 = 1;
        break;
    }
    LODWORD(v284) = v145;
    *(_QWORD *)&v285[6] = v123 + 0x2000;
    LODWORD(v124) = v145;
  }
  else
  {
    v280 = 1;
    v147 = *(_BYTE *)v146;
    switch ( *(_BYTE *)v146 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( *((char *)v146 + 1) < 0 )
        {
          v148 = HIBYTE(*(unsigned __int16 *)((char *)v146 + 1))
               | ((*(unsigned __int16 *)((char *)v146 + 1) & 0x7F) << 8);
          v281 = v148;
          v149 = 3;
          v150 = 3;
        }
        else
        {
          v148 = *((unsigned __int8 *)v146 + 1);
          v281 = v148;
          v149 = 2;
          v150 = 2;
        }
        *(_WORD *)v285 = v149;
        *(_WORD *)&v285[4] = v150 + (((unsigned int)v148 + 1) >> 1);
        if ( v148 > 0x1Eu )
          *(_WORD *)&v285[2] = (v148 - 1) / 30;
        else
          *(_WORD *)&v285[2] = 0;
        v40 = 0;
        v282 = 0;
        v286 = 0;
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
        v40 = v282;
        break;
      case 4:
        if ( (v147 & 0x1C) == 4 && (v147 & 2) != 0 )
        {
          *(_QWORD *)v285 = 0;
          v281 = 0;
          *(_QWORD *)&v285[8] = 0;
          v282 = 15;
          v286 = 1;
        }
        else
        {
          *(_QWORD *)v285 = 0;
          v281 = 0;
          *(_QWORD *)&v285[8] = 0;
          v40 = 1;
          v282 = 1;
          v286 = 0;
        }
        break;
      case 8:
        *(_QWORD *)v285 = 0;
        v281 = 0;
        *(_QWORD *)&v285[8] = 0;
        v40 = 9;
        v282 = 9;
        v286 = 0;
        break;
    }
    *(_QWORD *)&v285[16] = v123 + 0x2000;
    v284 = v124;
  }
  if ( v280 )
  {
    if ( !v40 )
    {
      CDRecord::Resize((CDRecord *)&v281);
      v40 = v282;
    }
    if ( v40 >= 9 || (*(_BYTE *)v283 & 0x1C) != 0 && (*(_BYTE *)v283 & 0x1C) != 0xC )
      v176 = v40;
    else
      v176 = 9;
  }
  else
  {
    if ( !v40 )
    {
      v281 = 0;
      HIDWORD(v284) = (_DWORD)v124;
      v40 = (unsigned int)v124;
      if ( (*(_BYTE *)v283 & 0x10) != 0 )
      {
        v40 = (((unsigned int)*(unsigned __int16 *)((char *)v283 + (unsigned int)v124) + 7) >> 3) + (_DWORD)v124 + 2;
        HIDWORD(v284) = v40;
      }
      if ( (*(_BYTE *)v283 & 0x20) != 0 )
      {
        v151 = (char *)v283 + v40;
        v152 = *(_WORD *)v151;
        *(_WORD *)&v285[4] = v152;
        if ( !v152 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v153 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v153 )
            {
              v154 = *(_QWORD *)(v153 + 96);
              if ( v154 )
              {
                if ( *(_BYTE *)(v154 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 3);
          v152 = *(_WORD *)&v285[4];
        }
        v155 = HIDWORD(v284) + 2 + 2 * v152;
        *(_DWORD *)v285 = v155;
        if ( v155 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v156 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v156 )
            {
              v157 = *(_QWORD *)(v156 + 96);
              if ( v157 )
              {
                if ( *(_BYTE *)(v157 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 4);
          v152 = *(_WORD *)&v285[4];
          v155 = *(_DWORD *)v285;
        }
        v40 = *(_WORD *)&v151[2 * v152] & 0x7FFF;
        v282 = v40;
        if ( v155 > v40 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v158 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v158 )
            {
              v159 = *(_QWORD *)(v158 + 96);
              if ( v159 )
              {
                if ( *(_BYTE *)(v159 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v283, 4);
          v152 = *(_WORD *)&v285[4];
          v155 = *(_DWORD *)v285;
          v40 = v282;
        }
        while ( *(__int16 *)&v151[2 * v152] < 0 )
        {
          v160 = (char *)v283 + HIDWORD(v284);
          if ( v152 == 1 )
            v161 = v155;
          else
            v161 = *(_WORD *)&v160[2 * v152 - 2] & 0x7FFF;
          if ( v161 < v155 || (*(_WORD *)&v160[2 * v152] & 0x7FFFu) < v161 )
          {
            RaiseInconsistencyError(v283, 7);
            v152 = *(_WORD *)&v285[4];
            v155 = *(_DWORD *)v285;
            v40 = v282;
          }
          if ( v161 < v155 || v161 > v40 )
            goto LABEL_497;
          v162 = *(unsigned __int16 *)((char *)v283 + v161);
          if ( v162 == 5 )
          {
            v281 |= 2u;
            *(_WORD *)&v285[4] = v152 - 1;
            *(_WORD *)&v285[18] = v161;
            v163 = (char *)v283 + (unsigned __int16)v161;
            v164 = *((_WORD *)v163 + 1);
            if ( (v164 & 0x4000) != 0 )
              v165 = (*(_WORD *)&v285[20] ^ v164) & 0x3800 ^ *(_WORD *)&v285[20];
            else
              v165 = *(_WORD *)&v285[20] & 0xC7FF;
            *(_WORD *)&v285[20] = v165;
            *(_WORD *)&v285[20] = v165 ^ (*((_WORD *)v163 + 1) ^ v165) & 0x7FF;
            break;
          }
          if ( v162 >= 0x400u )
          {
            v281 |= 1u;
            v94 = v152-- == 1;
            *(_WORD *)&v285[4] = v152;
            if ( !v94 )
              continue;
          }
          break;
        }
      }
      else
      {
        v282 = v40;
        *(_WORD *)&v285[4] = 0;
        *(_DWORD *)v285 = v40;
      }
      if ( (*(_BYTE *)v283 & 0x40) != 0 )
      {
        *(_DWORD *)&v285[14] = v40;
        v282 = v40 + 14;
        v166 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v281);
        v167 = HIDWORD(*(_QWORD *)v166);
        v168 = HIWORD(*(_QWORD *)v166);
        v169 = 0;
        if ( (((__int16)v168 ^ ((unsigned int)(__int16)v168 >> 1)) & 0x2000) != 0 )
        {
          v170 = v168 & 0xDFFF;
          if ( (v168 & 0x4000) != 0 )
            v170 = v168 | 0x2000;
          LOWORD(v168) = v170;
        }
        if ( (_WORD)v168 == 0xFFFC )
          v169 = (unsigned __int16)v167 >> 5;
        v40 = v169 + v282;
        v282 += v169;
      }
      else
      {
        *(_DWORD *)&v285[14] = 0;
      }
      if ( *(_QWORD *)&v285[6] && *(_QWORD *)&v285[6] < (unsigned __int64)v283 + v40 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v171 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v171 )
          {
            v172 = *(_QWORD *)(v171 + 96);
            if ( v172 )
            {
              if ( *(_BYTE *)(v172 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v283, 18);
        v40 = v282;
      }
      if ( v40 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v173 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v173 )
          {
            v174 = *(_QWORD *)(v173 + 96);
            if ( v174 )
            {
              if ( *(_BYTE *)(v174 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v283, 5);
        v40 = v282;
      }
    }
LABEL_497:
    if ( v40 >= 9 || (v175 = *(_BYTE *)v283 & 0xE) != 0 && v175 != 12 )
      v176 = v40;
    else
      v176 = 9;
  }
  if ( v280 )
  {
    if ( !v40 )
    {
      CDRecord::Resize((CDRecord *)&v281);
      v40 = v282;
    }
    if ( v40 >= 9 || (*(_BYTE *)v283 & 0x1C) != 0 && (*(_BYTE *)v283 & 0x1C) != 0xC )
    {
LABEL_600:
      v227 = v40;
      goto LABEL_601;
    }
    v227 = 9;
  }
  else
  {
    if ( !v40 )
    {
      v281 = 0;
      v40 = (unsigned int)v284;
      HIDWORD(v284) = (_DWORD)v284;
      if ( (*(_BYTE *)v283 & 0x10) != 0 )
      {
        v40 = (((unsigned int)*(unsigned __int16 *)((char *)v283 + (unsigned int)v284) + 7) >> 3) + (_DWORD)v284 + 2;
        HIDWORD(v284) = v40;
      }
      if ( (*(_BYTE *)v283 & 0x20) != 0 )
      {
        v177 = (char *)v283 + v40;
        v178 = *(_WORD *)v177;
        *(_WORD *)&v285[4] = v178;
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
          RaiseInconsistencyError(v283, 3);
          v178 = *(_WORD *)&v285[4];
        }
        v181 = HIDWORD(v284) + 2 + 2 * v178;
        *(_DWORD *)v285 = v181;
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
          RaiseInconsistencyError(v283, 4);
          v178 = *(_WORD *)&v285[4];
          v181 = *(_DWORD *)v285;
        }
        v40 = *(_WORD *)&v177[2 * v178] & 0x7FFF;
        v282 = v40;
        if ( v181 > v40 )
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
          RaiseInconsistencyError(v283, 4);
          v178 = *(_WORD *)&v285[4];
          v181 = *(_DWORD *)v285;
          v40 = v282;
        }
        while ( *(__int16 *)&v177[2 * v178] < 0 )
        {
          v186 = (char *)v283 + HIDWORD(v284);
          if ( v178 == 1 )
            v187 = v181;
          else
            v187 = *(_WORD *)&v186[2 * v178 - 2] & 0x7FFF;
          if ( v187 < v181 || (*(_WORD *)&v186[2 * v178] & 0x7FFFu) < v187 )
          {
            RaiseInconsistencyError(v283, 7);
            v178 = *(_WORD *)&v285[4];
            v181 = *(_DWORD *)v285;
            v40 = v282;
          }
          if ( v187 < v181 || v187 > v40 )
            goto LABEL_597;
          v188 = *(unsigned __int16 *)((char *)v283 + v187);
          if ( v188 == 5 )
          {
            v281 |= 2u;
            *(_WORD *)&v285[4] = v178 - 1;
            *(_WORD *)&v285[18] = v187;
            v189 = (char *)v283 + (unsigned __int16)v187;
            v190 = *((_WORD *)v189 + 1);
            if ( (v190 & 0x4000) != 0 )
              v191 = (*(_WORD *)&v285[20] ^ v190) & 0x3800 ^ *(_WORD *)&v285[20];
            else
              v191 = *(_WORD *)&v285[20] & 0xC7FF;
            *(_WORD *)&v285[20] = v191;
            *(_WORD *)&v285[20] = v191 ^ (*((_WORD *)v189 + 1) ^ v191) & 0x7FF;
            break;
          }
          if ( v188 >= 0x400u )
          {
            v281 |= 1u;
            v94 = v178-- == 1;
            *(_WORD *)&v285[4] = v178;
            if ( !v94 )
              continue;
          }
          break;
        }
      }
      else
      {
        v282 = v40;
        *(_WORD *)&v285[4] = 0;
        *(_DWORD *)v285 = v40;
      }
      if ( (*(_BYTE *)v283 & 0x40) != 0 )
      {
        *(_DWORD *)&v285[14] = v40;
        v282 = v40 + 14;
        v192 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v281);
        v193 = HIDWORD(*(_QWORD *)v192);
        v194 = HIWORD(*(_QWORD *)v192);
        v195 = 0;
        if ( (((__int16)v194 ^ ((unsigned int)(__int16)v194 >> 1)) & 0x2000) != 0 )
        {
          v196 = v194 & 0xDFFF;
          if ( (v194 & 0x4000) != 0 )
            v196 = v194 | 0x2000;
          LOWORD(v194) = v196;
        }
        if ( (_WORD)v194 == 0xFFFC )
          v195 = (unsigned __int16)v193 >> 5;
        v40 = v195 + v282;
        v282 += v195;
      }
      else
      {
        *(_DWORD *)&v285[14] = 0;
      }
      if ( *(_QWORD *)&v285[6] && *(_QWORD *)&v285[6] < (unsigned __int64)v283 + v40 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v197 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v197 )
          {
            v198 = *(_QWORD *)(v197 + 96);
            if ( v198 )
            {
              if ( *(_BYTE *)(v198 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v283, 18);
        v40 = v282;
      }
      if ( v40 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v199 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v199 )
          {
            v200 = *(_QWORD *)(v199 + 96);
            if ( v200 )
            {
              if ( *(_BYTE *)(v200 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v283, 5);
        v40 = v282;
      }
    }
LABEL_597:
    if ( v40 >= 9 )
      goto LABEL_600;
    v201 = *(_BYTE *)v283 & 0xE;
    if ( v201 )
    {
      if ( v201 != 12 )
        goto LABEL_600;
    }
  }
LABEL_601:
  v202 = v261;
  v222 = v176;
  v203 = v239;
  if ( (unsigned int)PageRef::ModifyRow(v270, 0, v239, 1u, 0, v227, v222, v283, 0, 0, v261, 0, 0, 0, 0, 0, 0, 0) )
    utassert_fail(1u, "insufficientSpace == 0", "SpaceMgrMaintenance.cpp", 2097, 0);
  if ( v230 || v231 )
  {
    v235 = 0;
    v236 = 0;
    v237 = 0;
    IAMPageRef::Fix(&v235, &v230, 4, v262);
    v256 = v225;
    v257 = v226;
    HIDWORD(v223) = HIDWORD(v202);
    PageRef::ModifyHeader(&v235, v203, 16);
    if ( !v235 )
    {
LABEL_634:
      PageRef::~PageRef((PageRef *)&v235);
      goto LABEL_635;
    }
    if ( (*(_WORD *)(v235 + 98) & 0x400) != 0 && (__int16)v237 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v235);
      goto LABEL_634;
    }
    v204 = (__int16)v237;
    v205 = v235;
    if ( (*(_WORD *)(v235 + 98) & 8) != 0 )
    {
      if ( (__int16)v237 == 3 )
      {
        v204 = 4;
LABEL_619:
        if ( (*(_DWORD *)(v235 + 100) & 8) != 0 )
        {
          v206 = *(_QWORD *)(v235 + 144);
          if ( v206 )
          {
            if ( *(_QWORD *)(v206 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v206 + 1880), v235, v204);
            }
          }
        }
        goto LABEL_623;
      }
      if ( (__int16)v237 >= 2 )
        goto LABEL_619;
    }
LABEL_623:
    if ( byte_10317ABE5 < 0
      && (*(_DWORD *)(v205 + 100) & 8) != 0
      && (int)v204 >= 3
      && (*(_DWORD *)(v205 + 100) & 0xC0000000) != 0x40000000
      && *(_QWORD *)v205
      && VirtualProtect(*(LPVOID *)v205, 0x2000u, 2u, &v275) )
    {
      _InterlockedAnd((volatile signed __int32 *)(v205 + 100), 0x3FFFFFFFu);
      _InterlockedOr((volatile signed __int32 *)(v205 + 100), 0x40000000u);
    }
    LatchBase::ReleaseInternal(v205 + 152, v204);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v205, 0, v204);
    v237 &= 0xFFFF0000;
    v235 = 0;
    goto LABEL_634;
  }
LABEL_635:
  if ( !v228 && !v229 )
    goto LABEL_661;
  v232 = 0;
  v233 = 0;
  v234 = 0;
  IAMPageRef::Fix(&v232, &v228, 4, v262);
  v254 = v225;
  v255 = v226;
  HIDWORD(v223) = HIDWORD(v202);
  PageRef::ModifyHeader(&v232, v203, 8);
  if ( v232 )
  {
    if ( (*(_WORD *)(v232 + 98) & 0x400) != 0 && (__int16)v234 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v232);
      goto LABEL_660;
    }
    v207 = (__int16)v234;
    v208 = v232;
    if ( (*(_WORD *)(v232 + 98) & 8) != 0 )
    {
      if ( (__int16)v234 == 3 )
      {
        v207 = 4;
LABEL_645:
        if ( (*(_DWORD *)(v232 + 100) & 8) != 0 )
        {
          v209 = *(_QWORD *)(v232 + 144);
          if ( v209 )
          {
            if ( *(_QWORD *)(v209 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v209 + 1880), v232, v207);
            }
          }
        }
        goto LABEL_649;
      }
      if ( (__int16)v234 >= 2 )
        goto LABEL_645;
    }
LABEL_649:
    if ( byte_10317ABE5 < 0
      && (*(_DWORD *)(v208 + 100) & 8) != 0
      && (int)v207 >= 3
      && (*(_DWORD *)(v208 + 100) & 0xC0000000) != 0x40000000
      && *(_QWORD *)v208
      && VirtualProtect(*(LPVOID *)v208, 0x2000u, 2u, &v276) )
    {
      _InterlockedAnd((volatile signed __int32 *)(v208 + 100), 0x3FFFFFFFu);
      _InterlockedOr((volatile signed __int32 *)(v208 + 100), 0x40000000u);
    }
    LatchBase::ReleaseInternal(v208 + 152, v207);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v208, 0, v207);
    v234 &= 0xFFFF0000;
    v232 = 0;
  }
LABEL_660:
  PageRef::~PageRef((PageRef *)&v232);
LABEL_661:
  v252 = 0;
  v253 = 0;
  v210 = 0;
  v263 = 0;
  v211 = 0;
  v264 = 0;
  v212 = 0;
  v238 = 0;
  v272 = 0;
  v213 = v278;
  if ( v278 )
  {
    HoBtAccess::AcquireAllocAccess(v278, (struct CAutoLatch *)&v263);
    v214 = *(_QWORD *)((char *)v213 + 20);
    LODWORD(v238) = v214;
    WORD2(v238) = WORD2(v214);
    v212 = HIDWORD(v264);
    v211 = v264;
    v210 = v263;
  }
  LOBYTE(v224) = 0;
  LODWORD(v223) = 0;
  v215 = DeAllocMgr::DeAllocatePageInternal(&v272, v202, &v252, v203, &v238, v271, v223, 0, v224, v246, 0);
  if ( v211 )
  {
    LatchBase::ReleaseInternal(v210, v212);
    LODWORD(v264) = 0;
  }
  if ( !v215 )
    ex_raise(26, 5, 25, 7);
  if ( v225 || v226 )
    v11 = 1;
  return v11 != 0 ? 3 : 0;
}

```

## disassembly

```asm
0x101658480  push    rbp
0x101658482  push    rsi
0x101658483  push    rdi
0x101658484  push    r12
0x101658486  push    r13
0x101658488  push    r14
0x10165848a  push    r15
0x10165848c  lea     rbp, [rsp-180h]
0x101658494  sub     rsp, 290h
0x10165849b  mov     [rbp+1B0h+var_F0], 0FFFFFFFFFFFFFFFEh
0x1016584a6  mov     [rsp+2C0h+arg_8], rbx
0x1016584ae  mov     rax, cs:__security_cookie
0x1016584b5  xor     rax, rsp
0x1016584b8  mov     [rbp+1B0h+var_38], rax
0x1016584bf  mov     [rbp+1B0h+var_160], r9
0x1016584c3  mov     r13, r8
0x1016584c6  mov     [rbp+1B0h+var_120], r8
0x1016584cd  mov     rsi, rcx
0x1016584d0  mov     [rbp+1B0h+var_1D8], rcx
0x1016584d4  mov     rax, [rbp+1B0h+arg_28]
0x1016584db  mov     [rbp+1B0h+var_F8], rax
0x1016584e2  mov     r12, [rbp+1B0h+arg_30]
0x1016584e9  mov     [rbp+1B0h+var_130], r12
0x1016584f0  mov     r15, [rbp+1B0h+arg_38]
0x1016584f7  mov     [rbp+1B0h+var_128], r15
0x1016584fe  mov     ecx, 0FFFFFFFFh
0x101658503  mov     [rbp+1B0h+var_E8], cx
0x10165850a  xor     ebx, ebx
0x10165850c  mov     [rbp+1B0h+var_E0], rbx
0x101658513  mov     [rbp+1B0h+var_E4], ebx
0x101658519  mov     [rbp+1B0h+var_D0+6], rbx
0x101658520  mov     [rbp+1B0h+var_C0], rbx
0x101658527  mov     [rbp+1B0h+var_D8], rbx
0x10165852e  mov     rdi, [r9+30h]
0x101658532  mov     [rbp+1B0h+var_158], rdi
0x101658536  mov     [rbp+1B0h+var_1A0], ebx
0x101658539  mov     [rbp+1B0h+var_1D0], rbx
0x10165853d  test    rax, rax
0x101658540  jz      short loc_101658551
0x101658542  mov     rax, [rax+14h]
0x101658546  mov     dword ptr [rbp+1B0h+var_1D0], eax
0x101658549  shr     rax, 20h
0x10165854d  mov     word ptr [rbp+1B0h+var_1D0+4], ax
0x101658551  movzx   edx, word ptr [r8+4]
0x101658556  xor     r8d, r8d
0x101658559  mov     rcx, [rdi+6A0h]
0x101658560  call    ?GetFCB@FileMgr@@QEBAPEAVFCB@@JW4LookupFailureMode@@@Z; FileMgr::GetFCB(long,LookupFailureMode)
0x101658565  mov     r14, rax
0x101658568  mov     r9, rdi
0x10165856b  mov     r8d, 2
0x101658571  mov     rdx, r13
0x101658574  mov     rcx, r12
0x101658577  call    ?Fix@IAMPageRef@@QEAAPEAVIAMPage@@AEBVPageId@@W4LATCH_TYPE@LatchBase@@PEAVRecoveryUnit@@@Z; IAMPageRef::Fix(PageId const &,LatchBase::LATCH_TYPE,RecoveryUnit *)
0x10165857c  mov     r9, [r12]
0x101658580  mov     r8, [r9]
0x101658583  movzx   edx, word ptr [r8+1FFEh]
0x10165858b  mov     ecx, [rdx+r8+28h]
0x101658590  mov     [rbp+1B0h+var_19C], ecx
0x101658593  movzx   eax, word ptr [rdx+r8+2Ch]
0x101658599  mov     [rbp+1B0h+var_198], ax
0x10165859d  movzx   edx, word ptr [r8+6]
0x1016585a2  mov     eax, [r8+18h]
0x1016585a6  cmp     [rsi], eax
0x1016585a8  jnz     loc_10165B7A5
0x1016585ae  mov     ecx, ebx
0x1016585b0  cmp     word ptr [rsi+4], 1
0x1016585b5  cmovnz  cx, [rsi+4]
0x1016585ba  mov     eax, ebx
0x1016585bc  cmp     dx, 1
0x1016585c0  cmovnz  ax, dx
0x1016585c4  cmp     cx, ax
0x1016585c7  jnz     loc_10165B7A5
0x1016585cd  movzx   eax, word ptr [r9+62h]
0x1016585d2  mov     edi, 400h
0x1016585d7  mov     edx, 2000h
0x1016585dc  mov     r13d, 4
0x1016585e2  test    di, ax
0x1016585e5  jz      short loc_1016585FD
0x1016585e7  cmp     word ptr [r12+0Ch], 3
0x1016585ee  jl      short loc_1016585FD
0x1016585f0  mov     rcx, r12; this
0x1016585f3  call    ?UnfixLatchOnly@PageRef@@IEAAXXZ; PageRef::UnfixLatchOnly(void)
0x1016585f8  jmp     loc_1016586E9
0x1016585fd  movsx   esi, word ptr [r12+0Ch]
0x101658603  mov     rdi, [r12]
0x101658607  movzx   eax, word ptr [rdi+62h]
0x10165860b  shr     al, 3
0x10165860e  test    al, 1
0x101658610  jz      short loc_101658657
0x101658612  cmp     esi, 3
0x101658615  jnz     short loc_10165861C
0x101658617  mov     esi, r13d
0x10165861a  jmp     short loc_101658621
0x10165861c  cmp     esi, 2
0x10165861f  jl      short loc_101658657
0x101658621  mov     eax, [rdi+64h]
0x101658624  test    al, 8
0x101658626  jz      short loc_101658657
0x101658628  mov     rcx, [rdi+90h]
0x10165862f  test    rcx, rcx
0x101658632  jz      short loc_101658657
0x101658634  cmp     [rcx+758h], rbx
0x10165863b  jz      short loc_101658657
0x10165863d  lfence
0x101658640  mov     r8d, esi
0x101658643  mov     rdx, rdi
0x101658646  mov     rcx, [rcx+758h]
0x10165864d  call    ?OnReleasingBufLatch@DirtyPageMgr@@QEAAXPEAUBUF@@W4LATCH_TYPE@LatchBase@@@Z; DirtyPageMgr::OnReleasingBufLatch(BUF *,LatchBase::LATCH_TYPE)
0x101658652  mov     edx, 2000h; dwSize
0x101658657  test    cs:byte_10317ABE5, 80h
0x10165865e  jz      short loc_1016586AA
0x101658660  mov     eax, [rdi+64h]
0x101658663  test    al, 8
0x101658665  jz      short loc_1016586AA
0x101658667  cmp     esi, 3
0x10165866a  jl      short loc_1016586AA
0x10165866c  mov     eax, [rdi+64h]
0x10165866f  and     eax, 0C0000000h
0x101658674  cmp     eax, 40000000h
0x101658679  jz      short loc_1016586AA
0x10165867b  mov     rcx, [rdi]; lpAddress
0x10165867e  test    rcx, rcx
0x101658681  jz      short loc_1016586AA
0x101658683  lea     r9, [rbp+1B0h+flOldProtect]; lpflOldProtect
0x10165868a  mov     r8d, 2; flNewProtect
0x101658690  call    cs:__imp_VirtualProtect
0x101658696  test    eax, eax
0x101658698  jz      short loc_1016586AA
0x10165869a  lock and dword ptr [rdi+64h], 3FFFFFFFh
0x1016586a2  lock or dword ptr [rdi+64h], 40000000h
0x1016586aa  lea     rcx, [rdi+98h]
0x1016586b1  mov     edx, esi
0x1016586b3  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x1016586b8  cmp     cs:?sm_acquireReleaseEnforcementExpensive@LatchBase@@0HA, ebx; int LatchBase::sm_acquireReleaseEnforcementExpensive
0x1016586be  jz      short loc_1016586D6
0x1016586c0  test    cs:byte_10317AD4F, 2
0x1016586c7  jz      short loc_1016586D6
0x1016586c9  mov     r8d, esi
0x1016586cc  xor     edx, edx
0x1016586ce  mov     rcx, rdi
0x1016586d1  call    ?TraceLatchAcquireRelease@BUF@@QEAAX_NW4LATCH_TYPE@LatchBase@@@Z; BUF::TraceLatchAcquireRelease(bool,LatchBase::LATCH_TYPE)
0x1016586d6  mov     [r12+0Ch], bx
0x1016586dc  mov     [r12], rbx
0x1016586e0  mov     edi, 400h
0x1016586e5  mov     rsi, [rbp+1B0h+var_1D8]
0x1016586e9  mov     eax, [rsi]
0x1016586eb  mov     [rbp+1B0h+var_168], eax
0x1016586ee  movzx   eax, word ptr [rsi+4]
0x1016586f2  mov     [rbp+1B0h+var_164], ax
0x1016586f6  mov     [rbp+1B0h+var_162], bx
0x1016586fa  mov     [rsp+2C0h+var_268], r15
0x1016586ff  mov     [rsp+2C0h+var_270], rbx
0x101658704  mov     eax, 1
0x101658709  mov     dword ptr [rsp+2C0h+var_278], eax
0x10165870d  lea     rax, [rbp+1B0h+var_19C]
0x101658711  mov     [rsp+2C0h+var_280], rax
0x101658716  lea     rax, [rbp+1B0h+var_1D0]
0x10165871a  mov     [rsp+2C0h+var_290], rax
0x10165871f  lea     rax, [rbp+1B0h+var_168]
0x101658723  mov     [rsp+2C0h+var_298], rax
0x101658728  movzx   eax, word ptr [r14+84h]
0x101658730  mov     word ptr [rsp+2C0h+var_2A0], ax
0x101658735  xor     r9d, r9d
0x101658738  mov     r8d, [rbp+1B0h+arg_20]
0x10165873f  mov     r14, [rbp+1B0h+var_160]
0x101658743  mov     rdx, r14
0x101658746  mov     rcx, r14
0x101658749  call    ?AllocIAMPage@@YAHPEAVXDES@@0IW4LogMode@@GVAllocUnitId@@AEBVHoBtId@@AEBVPageId@@4HPEAVIAMPageRef@@AEAV6@@Z; AllocIAMPage(XDES *,XDES *,uint,LogMode,ushort,AllocUnitId,HoBtId const &,PageId const &,PageId const &,int,IAMPageRef *,IAMPageRef &)
0x10165874e  test    eax, eax
0x101658750  jz      loc_10165B8B6
0x101658756  mov     rcx, [r15]
0x101658759  mov     eax, [rcx+70h]
0x10165875c  mov     [rbp+1B0h+var_230], eax
0x10165875f  movzx   eax, word ptr [rcx+74h]
0x101658763  mov     [rbp+1B0h+var_22C], ax
0x101658767  test    rcx, rcx
0x10165876a  jz      loc_10165886D
0x101658770  movzx   eax, word ptr [rcx+62h]
0x101658774  test    di, ax
0x101658777  jz      short loc_10165878E
0x101658779  cmp     word ptr [r15+0Ch], 3
0x10165877f  jl      short loc_10165878E
0x101658781  mov     rcx, r15; this
0x101658784  call    ?UnfixLatchOnly@PageRef@@IEAAXXZ; PageRef::UnfixLatchOnly(void)
0x101658789  jmp     loc_10165886D
0x10165878e  movsx   esi, word ptr [r15+0Ch]
0x101658793  mov     rdi, [r15]
0x101658796  movzx   eax, word ptr [rdi+62h]
0x10165879a  shr     al, 3
0x10165879d  test    al, 1
0x10165879f  jz      short loc_1016587E1
0x1016587a1  cmp     esi, 3
0x1016587a4  jnz     short loc_1016587AB
0x1016587a6  mov     esi, r13d
0x1016587a9  jmp     short loc_1016587B0
0x1016587ab  cmp     esi, 2
0x1016587ae  jl      short loc_1016587E1
0x1016587b0  mov     eax, [rdi+64h]
0x1016587b3  test    al, 8
0x1016587b5  jz      short loc_1016587E1
0x1016587b7  mov     rcx, [rdi+90h]
0x1016587be  test    rcx, rcx
0x1016587c1  jz      short loc_1016587E1
0x1016587c3  cmp     [rcx+758h], rbx
0x1016587ca  jz      short loc_1016587E1
0x1016587cc  lfence
0x1016587cf  mov     r8d, esi
0x1016587d2  mov     rdx, rdi
0x1016587d5  mov     rcx, [rcx+758h]
0x1016587dc  call    ?OnReleasingBufLatch@DirtyPageMgr@@QEAAXPEAUBUF@@W4LATCH_TYPE@LatchBase@@@Z; DirtyPageMgr::OnReleasingBufLatch(BUF *,LatchBase::LATCH_TYPE)
0x1016587e1  test    cs:byte_10317ABE5, 80h
0x1016587e8  jz      short loc_101658839
0x1016587ea  mov     eax, [rdi+64h]
0x1016587ed  test    al, 8
0x1016587ef  jz      short loc_101658839
0x1016587f1  cmp     esi, 3
0x1016587f4  jl      short loc_101658839
0x1016587f6  mov     eax, [rdi+64h]
0x1016587f9  and     eax, 0C0000000h
0x1016587fe  cmp     eax, 40000000h
0x101658803  jz      short loc_101658839
0x101658805  mov     rcx, [rdi]; lpAddress
0x101658808  test    rcx, rcx
0x10165880b  jz      short loc_101658839
0x10165880d  lea     r9, [rbp+1B0h+var_10C]; lpflOldProtect
0x101658814  mov     edx, 2000h; dwSize
0x101658819  mov     r8d, 2; flNewProtect
0x10165881f  call    cs:__imp_VirtualProtect
0x101658825  test    eax, eax
0x101658827  jz      short loc_101658839
0x101658829  lock and dword ptr [rdi+64h], 3FFFFFFFh
0x101658831  lock or dword ptr [rdi+64h], 40000000h
0x101658839  lea     rcx, [rdi+98h]
0x101658840  mov     edx, esi
0x101658842  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x101658847  cmp     cs:?sm_acquireReleaseEnforcementExpensive@LatchBase@@0HA, ebx; int LatchBase::sm_acquireReleaseEnforcementExpensive
0x10165884d  jz      short loc_101658865
0x10165884f  test    cs:byte_10317AD4F, 2
0x101658856  jz      short loc_101658865
0x101658858  mov     r8d, esi
0x10165885b  xor     edx, edx
0x10165885d  mov     rcx, rdi
0x101658860  call    ?TraceLatchAcquireRelease@BUF@@QEAAX_NW4LATCH_TYPE@LatchBase@@@Z; BUF::TraceLatchAcquireRelease(bool,LatchBase::LATCH_TYPE)
0x101658865  mov     [r15+0Ch], bx
0x10165886a  mov     [r15], rbx
0x10165886d  mov     rdi, [rbp+1B0h+var_158]
0x101658871  mov     r9, rdi
0x101658874  mov     r8d, r13d
0x101658877  mov     rsi, [rbp+1B0h+var_120]
0x10165887e  mov     rdx, rsi
0x101658881  mov     rcx, r12
0x101658884  call    ?Fix@IAMPageRef@@QEAAPEAVIAMPage@@AEBVPageId@@W4LATCH_TYPE@LatchBase@@PEAVRecoveryUnit@@@Z; IAMPageRef::Fix(PageId const &,LatchBase::LATCH_TYPE,RecoveryUnit *)
0x101658889  mov     rax, [r12]
0x10165888d  mov     rcx, [rax]
0x101658890  mov     eax, [rcx+20h]
0x101658893  cmp     [rsi], eax
0x101658895  jnz     short loc_1016588A1
0x101658897  movzx   eax, word ptr [rcx+24h]
0x10165889b  cmp     [rsi+4], ax
0x10165889f  jz      short loc_1016588C5
0x1016588a1  mov     [rsp+2C0h+var_2A0], rbx
0x1016588a6  mov     r9d, 7E4h
0x1016588ac  lea     r8, aSpacemgrmainte; "SpaceMgrMaintenance.cpp"
0x1016588b3  lea     rdx, aSourcepageidOl; "sourcePageId == oldIAMPageRef.GetPagePt"...
0x1016588ba  mov     ecx, 1
0x1016588bf  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1016588c5  mov     r9, rdi
0x1016588c8  mov     r8d, r13d
0x1016588cb  lea     rdx, [rbp+1B0h+var_230]
0x1016588cf  mov     rcx, r15
0x1016588d2  call    ?Fix@IAMPageRef@@QEAAPEAVIAMPage@@AEBVPageId@@W4LATCH_TYPE@LatchBase@@PEAVRecoveryUnit@@@Z; IAMPageRef::Fix(PageId const &,LatchBase::LATCH_TYPE,RecoveryUnit *)
0x1016588d7  mov     rsi, [r12]
0x1016588db  mov     rax, [rsi]
0x1016588de  mov     edx, [rax+8]
0x1016588e1  movzx   ecx, word ptr [rax+0Ch]
0x1016588e5  mov     [rbp+1B0h+var_21C], edx
0x1016588e8  mov     [rbp+1B0h+var_218], cx
0x1016588ec  test    edx, edx
0x1016588ee  jnz     short loc_1016588FB
0x1016588f0  test    cx, cx
0x1016588f3  jnz     short loc_1016588FB
0x1016588f5  mov     rdi, [rbp+1B0h+var_1D8]
0x1016588f9  jmp     short loc_101658931
0x1016588fb  mov     [rbp+1B0h+var_194], edx
0x1016588fe  mov     [rbp+1B0h+var_190], cx
0x101658902  mov     [rsp+2C0h+var_290], r14
0x101658907  mov     dword ptr [rsp+2C0h+var_298], ebx
0x10165890b  lea     rax, [rbp+1B0h+var_194]
0x10165890f  mov     [rsp+2C0h+var_2A0], rax
0x101658914  mov     r9d, 6
0x10165891a  lea     r8d, [r9+2]
0x10165891e  mov     rdi, [rbp+1B0h+var_1D8]
0x101658922  mov     rdx, rdi
0x101658925  mov     rcx, r15
0x101658928  call    ?ModifyHeader@PageRef@@QEAAXAEBVAllocUnitId@@IIPEBXW4LogMode@@PEAVXDES@@@Z; PageRef::ModifyHeader(AllocUnitId const &,uint,uint,void const *,LogMode,XDES *)
0x10165892d  mov     rsi, [r12]
0x101658931  mov     rax, [rsi]
0x101658934  mov     edx, [rax+10h]
0x101658937  movzx   ecx, word ptr [rax+14h]
0x10165893b  mov     [rbp+1B0h+var_224], edx
  ... truncated ...
```
