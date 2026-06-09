# IndexPageRef::MarkGhost(HoBtAccess &,XDES *,LogLockCollection const * const,RecVersioningInfo const *,int,Record *,IndexPageRef::DeleteFlag)

- ea: `0x10048abf0`
- end: `0x10048b5aa`
- name: `?MarkGhost@IndexPageRef@@QEAAXAEAVHoBtAccess@@PEAVXDES@@QEBVLogLockCollection@@PEBVRecVersioningInfo@@HPEAVRecord@@VDeleteFlag@1@@Z`
- size: `2490`
- prototype: `void __high(struct HoBtAccess *, struct XDES *, const struct LogLockCollection *const, const struct RecVersioningInfo *, int, struct Record *, struct IndexPageRef::DeleteFlag)`
- caller_count: `1`
- callee_count: `31`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x10045bcc0`

## callees

- `0x100401490`
- `0x100402000`
- `0x100402740`
- `0x100415e90`
- `0x100427840`
- `0x10042d750`
- `0x1004410c0`
- `0x100441e00`
- `0x100445e80`
- `0x10044b5a0`
- `0x10044bad0`
- `0x100455720`
- `0x10046bf90`
- `0x1004729d0`
- `0x10047bc10`
- `0x100480030`
- `0x1004807a0`
- `0x10048a4a0`
- `0x10048abf0`
- `0x100493040`
- `0x10049aa60`
- `0x10049b060`
- `0x10049e5a0`
- `0x10058cca0`
- `0x1012c9010`
- `0x10130d530`
- `0x10168b160`
- `0x101d0fad0`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021ed230`

## import_xrefs

- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10048b399`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10048b3da`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10131e910`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10131c9f1`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10131cb91`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10131cd21`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10131ce11`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10131cf4f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131c908`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131ca74`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131cacc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131cc04`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131cc5c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131d3b0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131d45d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131d610`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131d656`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131dd9a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131ddc5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131ddf0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131dee4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131df0f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e3a6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e3d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e3fc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e86e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e899`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131f081`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131f12e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131f383`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131f42c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131c908`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131ca74`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131cacc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131cc04`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131cc5c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131d3b0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131d45d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131d610`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131d656`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131dd9a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131ddc5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131ddf0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131dee4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131df0f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e3a6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e3d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e3fc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e86e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131e899`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131f081`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131f12e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131f383`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10131f42c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131d7a3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131d85c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131d914`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131db35`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131dbe0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e130`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e1e4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e29a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e5d4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e67e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131d7a3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131d85c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131d914`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131db35`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131dbe0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e130`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e1e4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e29a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e5d4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10131e67e`
- `sqldk!SystemThread_TlsIndex` at `0x10131d747`
- `sqldk!SystemThread_TlsIndex` at `0x10131d800`
- `sqldk!SystemThread_TlsIndex` at `0x10131d8b8`
- `sqldk!SystemThread_TlsIndex` at `0x10131dad9`
- `sqldk!SystemThread_TlsIndex` at `0x10131db84`
- `sqldk!SystemThread_TlsIndex` at `0x10131e0d4`
- `sqldk!SystemThread_TlsIndex` at `0x10131e188`
- `sqldk!SystemThread_TlsIndex` at `0x10131e23e`
- `sqldk!SystemThread_TlsIndex` at `0x10131e578`
- `sqldk!SystemThread_TlsIndex` at `0x10131e622`
- `sqldk!SystemThread_TlsIndex` at `0x10131e93f`
- `sqldk!SystemThread_TlsIndex` at `0x10131ea76`
- `sqldk!SystemThread_TlsIndex` at `0x10131eafd`
- `sqldk!SystemThread_TlsOffset` at `0x10131d750`
- `sqldk!SystemThread_TlsOffset` at `0x10131d809`
- `sqldk!SystemThread_TlsOffset` at `0x10131d8c1`
- `sqldk!SystemThread_TlsOffset` at `0x10131dae2`
- `sqldk!SystemThread_TlsOffset` at `0x10131db8d`
- `sqldk!SystemThread_TlsOffset` at `0x10131e0dd`
- `sqldk!SystemThread_TlsOffset` at `0x10131e191`
- `sqldk!SystemThread_TlsOffset` at `0x10131e247`
- `sqldk!SystemThread_TlsOffset` at `0x10131e581`
- `sqldk!SystemThread_TlsOffset` at `0x10131e62b`
- `sqldk!SystemThread_TlsOffset` at `0x10131e948`
- `sqldk!SystemThread_TlsOffset` at `0x10131ea7f`
- `sqldk!SystemThread_TlsOffset` at `0x10131eb06`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10131e963`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10131ea9b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10131eb22`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10131e963`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10131ea9b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10131eb22`

## string_xrefs

- `0x10131ca6d`: `!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x10131cbfd`: `!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x10131cac5`: `(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x10131cc55`: `(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x10131c901`: `pXdes->DoesXactSupportCTR() || !pCommittedRec`

## pseudocode

```c
__int64 *__fastcall IndexPageRef::MarkGhost(
        PageRef *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 *a5,
        unsigned int a6,
        __int16 *a7,
        unsigned __int8 *a8)
{
  PageRef *v8; // rsi
  int v9; // ebx
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  __int64 *v14; // rcx
  BUF *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // r15
  __int16 v20; // r13
  BUF *v21; // r11
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // r11
  char v26; // al
  unsigned __int16 v27; // r15
  BUF *v28; // r11
  __int64 v29; // rcx
  __int64 FCB; // rax
  BUF *v31; // r11
  __int64 v32; // r14
  BUF *v33; // rsi
  __int64 v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // eax
  __int64 v37; // rax
  __int64 v38; // r11
  char v39; // al
  unsigned __int16 v40; // si
  PageRef *v41; // r9
  __int64 v42; // rax
  __int64 v43; // rcx
  unsigned int v44; // eax
  char v45; // al
  __int64 v46; // rdx
  unsigned __int8 *v47; // rsi
  int *v48; // r14
  unsigned __int8 v49; // r15
  char v50; // al
  char v51; // r15
  HoBtAccess *v52; // rsi
  char v53; // al
  HoBtAccess *v54; // rsi
  char v55; // al
  char v56; // al
  PageRef *v57; // r9
  BUF *v58; // r11
  __int64 v59; // rax
  __int16 v60; // cx
  __int64 v61; // rsi
  int v62; // r14d
  char v63; // al
  int v64; // eax
  __int64 v65; // r15
  __int16 v66; // r11
  unsigned int v67; // esi
  PageComprInfoCache **v68; // r12
  int v69; // r15d
  char *v70; // r9
  char v71; // al
  __int16 *v72; // rax
  int v73; // r15d
  _BYTE *v74; // rdx
  char v75; // cl
  __int16 *v76; // rax
  __int16 *v77; // rsi
  unsigned __int8 *v78; // r14
  int v79; // r13d
  __int64 v80; // r9
  BOOL v81; // ecx
  __int128 v82; // xmm0
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v84; // r8
  __int64 v85; // r12
  __int64 v86; // rsi
  __int64 v87; // rsi
  __int64 v88; // rax
  __int64 v89; // rsi
  PageRef *v90; // r14
  unsigned int v91; // r10d
  unsigned __int8 v92; // al
  bool v93; // zf
  int v94; // ecx
  int v95; // edx
  int v96; // ecx
  int v97; // edx
  __int64 v98; // rcx
  int v99; // r8d
  int v100; // eax
  __int64 v101; // rcx
  __int64 *result; // rax
  __int64 v103; // rax
  PageRef *v104; // r14
  __int64 v105; // rcx
  struct RecoveryUnit *v106; // rcx
  BUF *v107; // rdx
  __int64 v108; // r11
  RecoveryUnit *v109; // rcx
  __int64 v110; // r11
  __int64 v111; // r11
  __int64 v112; // r11
  __int64 v113; // r11
  __int64 v114; // r11
  __int64 v115; // r8
  unsigned int v116; // ecx
  __int64 v117; // rcx
  __int64 v118; // r11
  __int64 v119; // r11
  XDES *v120; // rax
  int DoesXactGenVersion; // eax
  __int64 v122; // rax
  int v123; // eax
  __int64 v124; // rax
  int v125; // eax
  XDES *v126; // rax
  int v127; // eax
  __int64 v128; // rax
  int v129; // eax
  __int64 v130; // rax
  int v131; // eax
  XDES *v132; // rax
  int v133; // eax
  __int64 v134; // rax
  XDES *v135; // rax
  int v136; // eax
  __int64 v137; // rax
  XDES *v138; // rax
  int v139; // eax
  __int64 v140; // rax
  char *v141; // rdx
  unsigned __int8 *v142; // r13
  char v143; // al
  __int16 v144; // cx
  __int64 v145; // rdx
  __int64 v146; // rcx
  __int64 v147; // r8
  int v148; // eax
  unsigned __int8 *v149; // r8
  unsigned __int8 v150; // dl
  __int16 v151; // dx
  unsigned __int16 v152; // cx
  __int64 v153; // rax
  __int16 v154; // cx
  int v155; // eax
  int v156; // ecx
  int v157; // r15d
  char v158; // dl
  unsigned __int16 v159; // cx
  unsigned __int16 v160; // ax
  void *v161; // rsp
  rsize_t v162; // rdx
  char *v163; // r13
  _WORD *v164; // r15
  __int64 v165; // rax
  __int64 v166; // rax
  unsigned int v167; // r8d
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  char *v172; // rax
  unsigned int v173; // r14d
  unsigned __int16 v174; // dx
  struct RecVersioningInfo *VersioningInfo; // rax
  int v176; // edx
  __int64 v177; // r9
  __int64 v178; // r8
  __int16 v179; // ax
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rax
  __int64 v183; // rax
  char v184; // cl
  unsigned int v185; // ecx
  char *v186; // r8
  char *v187; // rdx
  int v188; // ecx
  unsigned int v189; // esi
  char *v190; // rdx
  __int16 v191; // ax
  __int16 v192; // cx
  char *v193; // rdx
  __int16 v194; // ax
  __int16 v195; // cx
  PageComprInfoCache **v196; // rax
  unsigned int v197; // r8d
  char *v198; // r13
  _WORD *v199; // r15
  __int64 v200; // rax
  __int64 v201; // rax
  unsigned int v202; // edx
  __int64 v203; // rax
  __int64 v204; // rax
  __int64 v205; // rax
  __int64 v206; // rax
  char *v207; // rax
  unsigned int v208; // r14d
  unsigned __int16 v209; // r8
  char *v210; // r8
  __int16 v211; // ax
  __int16 v212; // cx
  struct RecVersioningInfo *v213; // rax
  int v214; // r8d
  __int64 v215; // r9
  __int64 v216; // rdx
  __int16 v217; // ax
  __int64 v218; // rax
  __int64 v219; // rax
  __int64 v220; // rax
  __int64 v221; // rax
  char v222; // cl
  char *v223; // r8
  char *v224; // rdx
  int v225; // ecx
  unsigned int v226; // esi
  char *v227; // rdx
  __int16 v228; // r8
  __int16 v229; // cx
  unsigned int v230; // eax
  __int64 v231; // r14
  __int64 v232; // rsi
  __int64 v233; // rax
  __int64 v234; // rcx
  __int64 v235; // rcx
  PageComprInfoCache **v236; // rax
  __int64 v237; // r14
  __int64 v238; // rax
  __int64 v239; // rcx
  __int64 v240; // rcx
  __int64 v241; // r14
  __int64 v242; // rax
  __int64 v243; // rcx
  __int64 v244; // rcx
  int v245; // ecx
  __int16 v246; // r11
  const char *v247; // r9
  PageComprInfoCache **v248; // r12
  int v249; // r15d
  unsigned __int8 *v250; // r8
  __int64 v251; // rdx
  unsigned __int8 *v252; // r12
  char v253; // al
  __int16 v254; // cx
  __int64 v255; // rdx
  __int64 v256; // rcx
  __int64 v257; // r13
  unsigned __int8 *v258; // r8
  unsigned __int8 v259; // dl
  __int16 v260; // dx
  unsigned __int16 v261; // cx
  unsigned __int8 *v262; // rax
  __int16 v263; // cx
  int v264; // eax
  int v265; // ecx
  int v266; // r15d
  unsigned __int16 v267; // cx
  char v268; // dl
  BOOL v269; // ecx
  int v270; // edx
  PageRef *v271; // r9
  BUF *v272; // r11
  __int64 v273; // rax
  __int16 v274; // cx
  int v275; // ecx
  char v276; // [rsp+0h] [rbp-1FA0h] BYREF
  unsigned __int64 *v277; // [rsp+1F40h] [rbp-60h]
  int v278; // [rsp+1F48h] [rbp-58h]
  int v279; // [rsp+1F50h] [rbp-50h]
  __int64 v280; // [rsp+1F58h] [rbp-48h]
  __int64 v281; // [rsp+1F60h] [rbp-40h]
  int v282; // [rsp+1F68h] [rbp-38h]
  unsigned __int64 *v283; // [rsp+1F70h] [rbp-30h]
  char *v284; // [rsp+1F78h] [rbp-28h]
  unsigned __int64 *v285; // [rsp+1F80h] [rbp-20h]
  __int64 v286; // [rsp+1F88h] [rbp-18h]
  rsize_t v287; // [rsp+1F90h] [rbp-10h]
  rsize_t DestinationSize; // [rsp+1FA0h] [rbp+0h]
  __int64 v289; // [rsp+1FA8h] [rbp+8h]
  PageRef *v290; // [rsp+1FB0h] [rbp+10h]
  rsize_t v291; // [rsp+1FB8h] [rbp+18h]
  int v292; // [rsp+1FC0h] [rbp+20h]
  int v293; // [rsp+1FC4h] [rbp+24h]
  unsigned __int8 *v294; // [rsp+1FC8h] [rbp+28h]
  __int64 v295; // [rsp+1FD0h] [rbp+30h] BYREF
  int v296; // [rsp+1FD8h] [rbp+38h] BYREF
  __int16 v297; // [rsp+1FDCh] [rbp+3Ch]
  rsize_t SourceSize; // [rsp+1FE0h] [rbp+40h] BYREF
  __int16 *v299; // [rsp+1FE8h] [rbp+48h]
  unsigned __int64 v300; // [rsp+1FF0h] [rbp+50h] BYREF
  unsigned __int64 *v301; // [rsp+1FF8h] [rbp+58h]
  __int64 v302; // [rsp+2000h] [rbp+60h] BYREF
  unsigned __int16 v303; // [rsp+2008h] [rbp+68h]
  __int64 v304; // [rsp+2010h] [rbp+70h] BYREF
  unsigned __int16 v305; // [rsp+2018h] [rbp+78h]
  __int64 v306; // [rsp+2020h] [rbp+80h] BYREF
  __int16 v307; // [rsp+2028h] [rbp+88h]
  __int64 v308; // [rsp+2030h] [rbp+90h] BYREF
  __int16 v309; // [rsp+2038h] [rbp+98h]
  int v310; // [rsp+2040h] [rbp+A0h]
  int v311; // [rsp+2044h] [rbp+A4h] BYREF
  __int16 v312; // [rsp+2048h] [rbp+A8h]
  int v313; // [rsp+204Ch] [rbp+ACh] BYREF
  __int16 v314; // [rsp+2050h] [rbp+B0h]
  int v315; // [rsp+2054h] [rbp+B4h] BYREF
  __int16 v316; // [rsp+2058h] [rbp+B8h]
  __int64 v317; // [rsp+2060h] [rbp+C0h]
  int v318; // [rsp+2068h] [rbp+C8h] BYREF
  __int16 v319; // [rsp+206Ch] [rbp+CCh]
  __int16 v320; // [rsp+206Eh] [rbp+CEh]
  __int64 v321; // [rsp+2070h] [rbp+D0h]
  __int64 v322; // [rsp+2078h] [rbp+D8h]
  __int128 v323; // [rsp+2080h] [rbp+E0h] BYREF
  __int16 v324; // [rsp+2090h] [rbp+F0h] BYREF
  unsigned __int16 v325; // [rsp+2092h] [rbp+F2h] BYREF
  int v326; // [rsp+2094h] [rbp+F4h]
  void *Source; // [rsp+2098h] [rbp+F8h]
  PageComprInfoCache **v328; // [rsp+20A0h] [rbp+100h]
  _BYTE v329[24]; // [rsp+20A8h] [rbp+108h]
  int v330; // [rsp+20C0h] [rbp+120h]
  unsigned int v331; // [rsp+20C4h] [rbp+124h]
  PageComprInfoCache *v332[2]; // [rsp+20C8h] [rbp+128h] BYREF
  __int128 v333; // [rsp+20D8h] [rbp+138h]
  __int64 v334; // [rsp+20E8h] [rbp+148h]
  _BYTE v335[14]; // [rsp+20F0h] [rbp+150h] BYREF
  _TBYTE v336; // [rsp+20FEh] [rbp+15Eh]
  _OWORD v337[2]; // [rsp+2108h] [rbp+168h] BYREF
  __int128 v338; // [rsp+2128h] [rbp+188h]
  __int64 v339; // [rsp+2138h] [rbp+198h]
  __int16 v340; // [rsp+2140h] [rbp+1A0h] BYREF
  unsigned __int16 v341; // [rsp+2142h] [rbp+1A2h] BYREF
  unsigned int v342; // [rsp+2144h] [rbp+1A4h]
  char *v343; // [rsp+2148h] [rbp+1A8h]
  PageComprInfoCache **v344; // [rsp+2150h] [rbp+1B0h]
  unsigned int v345; // [rsp+2158h] [rbp+1B8h]
  __int16 v346; // [rsp+215Ch] [rbp+1BCh]
  __int64 v347; // [rsp+215Eh] [rbp+1BEh]
  _TBYTE v348; // [rsp+2166h] [rbp+1C6h]
  void *Destination; // [rsp+2178h] [rbp+1D8h]
  unsigned int v350; // [rsp+2180h] [rbp+1E0h]
  __int16 v351; // [rsp+2188h] [rbp+1E8h]
  unsigned __int16 v352; // [rsp+218Ah] [rbp+1EAh]
  int v353; // [rsp+218Ch] [rbp+1ECh]
  _BYTE *v354; // [rsp+2190h] [rbp+1F0h]
  PageComprInfoCache **v355; // [rsp+2198h] [rbp+1F8h]
  _BYTE v356[24]; // [rsp+21A0h] [rbp+200h]
  int v357; // [rsp+21B8h] [rbp+218h]
  unsigned int v358; // [rsp+21BCh] [rbp+21Ch]
  PageComprInfoCache *v359[2]; // [rsp+21C0h] [rbp+220h] BYREF
  __int128 v360; // [rsp+21D0h] [rbp+230h]
  __int64 v361; // [rsp+21E0h] [rbp+240h]
  _BYTE v362[14]; // [rsp+21E8h] [rbp+248h] BYREF
  _TBYTE v363; // [rsp+21F6h] [rbp+256h]
  _OWORD v364[2]; // [rsp+2200h] [rbp+260h] BYREF
  __int128 v365; // [rsp+2220h] [rbp+280h]
  __int64 v366; // [rsp+2230h] [rbp+290h]
  unsigned __int64 v367; // [rsp+2238h] [rbp+298h] BYREF
  int v368; // [rsp+2240h] [rbp+2A0h]
  __int16 v369; // [rsp+2244h] [rbp+2A4h]

  v8 = a1;
  v9 = 0;
  v299 = a7;
  v290 = a1;
  v11 = *(unsigned __int16 *)(a2 + 24);
  v294 = a8;
  v12 = *(unsigned int *)(a2 + 20) | (unsigned __int64)(v11 << 32);
  v367 = 0;
  v13 = *((_QWORD *)v8 + 5);
  v368 = 0;
  v369 = 0;
  v321 = v12 << 16;
  v14 = *(__int64 **)(v13 + 8);
  v322 = a4;
  v295 = a2;
  v15 = *(BUF **)v8;
  v16 = *v14;
  v293 = 8;
  v317 = 0;
  v301 = 0;
  v17 = *(_QWORD *)(v16 + 8);
  v320 = 0;
  v318 = *(_DWORD *)(v17 + 960);
  v319 = *(_WORD *)(v17 + 964);
  v19 = BPool::PrepareToDirty(qword_10317B628, v15, 1, 0);
  v289 = v19;
  v20 = 2;
  *(_WORD *)(v19 + 4) &= 0xEDFFu;
  *(_DWORD *)(v19 + 64) = 1;
  v21 = *(BUF **)v8;
  if ( *(_WORD *)(*(_QWORD *)v8 + 44LL) != 2 )
  {
    v22 = *((_QWORD *)v21 + 18);
    if ( !v22 )
    {
      BUF::FixupPru(*(BUF **)v8);
      v22 = *(_QWORD *)(v108 + 144);
      v21 = *(BUF **)v8;
    }
    v23 = *(_QWORD *)(v22 + 1712);
    if ( (*(_BYTE *)(v23 + 60) & 1) == 0 || *(_QWORD *)(v23 + 640) )
      goto LABEL_7;
    v109 = (RecoveryUnit *)*((_QWORD *)v21 + 18);
    if ( !v109 )
    {
      BUF::FixupPru(v21);
      v109 = *(RecoveryUnit **)(v110 + 144);
    }
    if ( RecoveryUnit::IsBackupAllowedOnRbIoDb(v109) )
    {
LABEL_7:
      v24 = *(_QWORD *)(*(_QWORD *)v8 + 144LL);
      if ( !v24 )
      {
        BUF::FixupPru(*(BUF **)v8);
        v24 = *(_QWORD *)(v111 + 144);
      }
      if ( (*(_BYTE *)(v24 + 7376) & 0x20) == 0 )
      {
        v25 = **(_QWORD **)v8;
        if ( !*(_WORD *)(v25 + 36) )
          goto LABEL_12;
        v26 = *(_BYTE *)(v25 + 1);
        if ( v26 == 11 )
        {
          if ( *(_DWORD *)(v25 + 24) == 99 )
          {
LABEL_157:
            v311 = *(_DWORD *)(v25 + 32);
            v312 = *(_WORD *)(v25 + 36);
            if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v311, v18) )
            {
              PageHeader::GetIcxLsn(v25, &v302);
              v27 = v303;
              goto LABEL_13;
            }
LABEL_12:
            v27 = *(_WORD *)(v25 + 48);
            v302 = *(_QWORD *)(v25 + 40);
            v303 = v27;
LABEL_13:
            v28 = *(BUF **)v8;
            v29 = *(_QWORD *)(*(_QWORD *)v8 + 144LL);
            if ( !v29 )
            {
              BUF::FixupPru(*(BUF **)v8);
              v29 = *((_QWORD *)v28 + 18);
            }
            FCB = FileMgr::GetFCB(*(_QWORD *)(v29 + 1696), *((unsigned __int16 *)v28 + 58), 0);
            v31 = *(BUF **)v8;
            v32 = FCB;
            v33 = v31;
            v34 = *((_QWORD *)v31 + 18);
            if ( !v34 )
            {
              BUF::FixupPru(v31);
              v34 = *(_QWORD *)(v112 + 144);
              v31 = *(BUF **)v290;
              v33 = *(BUF **)v290;
            }
            if ( !*(_DWORD *)(*(_QWORD *)(v34 + 1960) + 88LL) )
            {
              v35 = *(_DWORD *)(v32 + 304);
              if ( v35 <= (unsigned int)v302 )
              {
                if ( v35 != (_DWORD)v302 )
                  goto LABEL_22;
                v36 = *(_DWORD *)(v32 + 308);
                if ( v36 <= HIDWORD(v302) && (v36 != HIDWORD(v302) || *(_WORD *)(v32 + 312) <= v27) )
                  goto LABEL_22;
              }
            }
            v103 = *((_QWORD *)v31 + 18);
            if ( v103 )
            {
              v104 = v290;
            }
            else
            {
              BUF::FixupPru(v31);
              v104 = v290;
              v103 = *(_QWORD *)(v113 + 144);
              v31 = *(BUF **)v290;
              v33 = *(BUF **)v290;
            }
            v105 = *(_QWORD *)(v103 + 1712);
            if ( (*(_BYTE *)(v105 + 60) & 1) == 0 || *(_QWORD *)(v105 + 640) )
            {
              v106 = (struct RecoveryUnit *)*((_QWORD *)v33 + 18);
              v107 = v33;
              if ( !v106 )
              {
                BUF::FixupPru(v33);
                v107 = *(BUF **)v104;
                v106 = (struct RecoveryUnit *)*((_QWORD *)v33 + 18);
              }
              PageRef::SetDiffMapChangeBit(v106, (const struct PageId *)(*(_QWORD *)v107 + 32LL));
              v8 = v290;
            }
            else
            {
LABEL_22:
              v37 = *((_QWORD *)v31 + 18);
              if ( v37 )
              {
                v8 = v290;
              }
              else
              {
                BUF::FixupPru(v31);
                v8 = v290;
                v37 = *(_QWORD *)(v114 + 144);
                v31 = *(BUF **)v290;
              }
              if ( *(_DWORD *)(*(_QWORD *)(v37 + 1960) + 272LL) )
              {
                v115 = *(_QWORD *)v31;
                v116 = *(_DWORD *)(*(_QWORD *)v31 + 32LL) & 0xFFFFFFF8;
                v18 = v116 / 0x7CD00;
                if ( v116 != 511232 * (_DWORD)v18 )
                {
                  v117 = *((_QWORD *)v31 + 18);
                  if ( !v117 )
                  {
                    BUF::FixupPru(v31);
                    v117 = *(_QWORD *)(v118 + 144);
                    v115 = **(_QWORD **)v8;
                  }
                  BackupManager::MarkExtentInBackupBitmapList(
                    *(BackupManager **)(v117 + 1960),
                    (const struct PageId *)(v115 + 32));
                }
              }
            }
            v19 = v289;
            goto LABEL_26;
          }
        }
        else if ( v26 == 8 )
        {
LABEL_159:
          if ( *(_DWORD *)(v25 + 24) != 99 )
            goto LABEL_12;
          goto LABEL_157;
        }
        if ( v26 != 9 )
          goto LABEL_12;
        goto LABEL_159;
      }
    }
  }
LABEL_26:
  v38 = **(_QWORD **)v8;
  if ( (*(_WORD *)(v38 + 4) & 0x2000) == 0 )
    goto LABEL_38;
  if ( !*(_WORD *)(v38 + 36) )
    goto LABEL_31;
  v39 = *(_BYTE *)(v38 + 1);
  if ( v39 != 11 )
  {
    if ( v39 == 8 )
    {
LABEL_172:
      if ( *(_DWORD *)(v38 + 24) != 99 )
        goto LABEL_31;
      goto LABEL_170;
    }
LABEL_30:
    if ( v39 != 9 )
      goto LABEL_31;
    goto LABEL_172;
  }
  if ( *(_DWORD *)(v38 + 24) != 99 )
    goto LABEL_30;
LABEL_170:
  v313 = *(_DWORD *)(v38 + 32);
  v314 = *(_WORD *)(v38 + 36);
  if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v313, v18) )
  {
    PageHeader::GetIcxLsn(v38, &v304);
    v40 = v305;
    goto LABEL_32;
  }
LABEL_31:
  v40 = *(_WORD *)(v38 + 48);
  v304 = *(_QWORD *)(v38 + 40);
  v305 = v40;
LABEL_32:
  v41 = v290;
  v42 = *(_QWORD *)(*(_QWORD *)v290 + 144LL);
  if ( !v42 )
  {
    BUF::FixupPru(*(BUF **)v290);
    v42 = *(_QWORD *)(v119 + 144);
    v41 = v290;
  }
  v43 = *(_QWORD *)(*(_QWORD *)(v42 + 1712) + 704LL);
  if ( (*(_WORD *)(v43 + 10) != 2 || (_DWORD)v304) && (unsigned int)v304 <= *(_DWORD *)v43 )
  {
    if ( (_DWORD)v304 != *(_DWORD *)v43
      || (v44 = *(_DWORD *)(v43 + 4), HIDWORD(v304) <= v44) && (HIDWORD(v304) != v44 || v40 <= *(_WORD *)(v43 + 8)) )
    {
      PageRef::RemoveOldVersionInfo(v41, v18, (const struct AllocUnitId *)&v318);
    }
  }
LABEL_38:
  v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 136LL))(a3);
  if ( v299 )
  {
    if ( v45 )
      utassert_fail(1u, "pXdes->DoesXactSupportCTR() || !pCommittedRec", "IndexPageRef.cpp", 2013, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 704LL))(a3);
  }
  if ( (*(_DWORD *)(a3 + 536) & 5) == 1 && (*(_BYTE *)(a3 + 728) & 2) != 0
    || (**(unsigned __int8 (__fastcall ***)(__int64))a3)(a3) )
  {
    if ( !a5 )
    {
      v301 = 0;
      goto LABEL_122;
    }
    v246 = -1;
    v358 = a6;
    v247 = "Invalid switch value";
    v301 = a5;
    v351 = -1;
    v354 = 0;
    v353 = 0;
    *(_QWORD *)&v356[6] = 0;
    *(_QWORD *)&v356[16] = 0;
    v355 = 0;
    if ( *(char *)(v19 + 2) >= 0 )
    {
      v248 = 0;
LABEL_623:
      v249 = *(unsigned __int16 *)(v19 + 14);
      v250 = (unsigned __int8 *)(v289 + *(unsigned __int16 *)(v289 + 2 * (4095LL - (int)a6)));
      v93 = (*v250 & 1) == 0;
      v354 = v250;
      if ( v93 )
      {
        v351 = 0;
        v353 = 0;
        *(_DWORD *)&v356[14] = 0;
        v251 = *v250 & 0xE;
        switch ( *v250 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v249 = *((unsigned __int16 *)v250 + 1);
            if ( (unsigned int)(v249 - 1) > 0x1F9D )
              RaiseInconsistencyError(v250, 6);
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
            v249 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v249 = 1;
            break;
        }
        LODWORD(v355) = v249;
        *(_QWORD *)&v356[6] = v289 + 0x2000;
      }
      else
      {
        v351 = 1;
        v251 = *v250;
        switch ( *v250 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( (v250[1] & 0x80u) != 0 )
            {
              v267 = HIBYTE(*(_WORD *)(v250 + 1)) | ((*(_WORD *)(v250 + 1) & 0x7F) << 8);
              *(_WORD *)v356 = 3;
              v20 = 3;
              v352 = v267;
            }
            else
            {
              v267 = v250[1];
              v352 = v267;
              *(_WORD *)v356 = 2;
            }
            *(_WORD *)&v356[4] = v20 + ((unsigned __int16)(v267 + 1) >> 1);
            if ( v267 > 0x1Eu )
            {
              v275 = v267 - 1;
              v353 = 0;
              v357 = 0;
              v251 = (unsigned int)(v275 / 30);
              *(_WORD *)&v356[2] = v275 / 30;
            }
            else
            {
              *(_WORD *)&v356[2] = 0;
              v353 = 0;
              v357 = 0;
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
            if ( (v251 & 0x1C) == 4 && (v251 & 2) != 0 )
            {
              *(_QWORD *)v356 = 0;
              v352 = 0;
              *(_QWORD *)&v356[8] = 0;
              v353 = 15;
              v357 = 1;
            }
            else
            {
              *(_QWORD *)v356 = 0;
              v352 = 0;
              *(_QWORD *)&v356[8] = 0;
              v353 = 1;
              v357 = 0;
            }
            break;
          case 8:
            *(_QWORD *)v356 = 0;
            v352 = 0;
            *(_QWORD *)&v356[8] = 0;
            v353 = 9;
            v357 = 0;
            break;
        }
        v355 = v248;
        *(_QWORD *)&v356[16] = v289 + 0x2000;
      }
      if ( !(**(unsigned __int8 (__fastcall ***)(__int64, __int64, unsigned __int8 *, const char *))a3)(
              a3,
              v251,
              v250,
              v247) )
      {
        if ( v351 )
        {
          v269 = (((*v354 & 0x1C) - 4) & 0xFFFFFFE7) == 0;
        }
        else
        {
          v268 = *v354 & 0xE;
          if ( v268 == 2 )
            v269 = (v354[1] & 1) != 0;
          else
            v269 = ((v268 - 10) & 0xF9) == 0;
        }
        v270 = 8;
        if ( v269 )
          v270 = 0x100000;
        v293 = v270;
      }
      if ( (**(unsigned __int8 (__fastcall ***)(__int64))a3)(a3) )
      {
        v271 = v290;
        v272 = *(BUF **)v290;
        v273 = *(_QWORD *)(*(_QWORD *)v290 + 144LL);
        if ( !v273 )
        {
          BUF::FixupPru(*(BUF **)v290);
          v273 = *((_QWORD *)v272 + 18);
          v271 = v290;
        }
        if ( *(_WORD *)(v273 + 1662) >= 0x387u )
          v274 = (unsigned __int16)~*((_WORD *)v272 + 49) >> 8;
        else
          LOBYTE(v274) = ~(*(_BYTE *)(*(_QWORD *)v272 + 2LL) >> 6);
        if ( (v274 & 1) != 0 )
          PageRef::SetVersionState(v271, 1, (struct XDES *)a3);
      }
      goto LABEL_122;
    }
    v252 = (unsigned __int8 *)(v19 + 96);
    _mm_prefetch((const char *)(v19 + 96), 0);
    v366 = 0;
    memset(v362, 0, sizeof(v362));
    v360 = 0xFFFFu;
    v363 = 0.0;
    memset(v364, 0, sizeof(v364));
    v361 = 0;
    v365 = 0u;
    *(_OWORD *)v359 = 0;
    if ( !*(_WORD *)(v19 + 36) )
      goto LABEL_636;
    v253 = *(_BYTE *)(v19 + 1);
    if ( v253 == 11 )
    {
      if ( *(_DWORD *)(v19 + 24) == 99 )
      {
LABEL_628:
        v315 = *(_DWORD *)(v19 + 32);
        v316 = *(_WORD *)(v19 + 36);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v315, v46) )
        {
          PageHeader::GetIcxLsn(v19, &v308);
          v254 = v309;
LABEL_630:
          v255 = *v252;
          *(_QWORD *)&v365 = v308;
          HIDWORD(v365) = *(_DWORD *)(v19 + 32);
          LODWORD(v366) = *(unsigned __int16 *)(v19 + 36);
          WORD4(v365) = v254;
          v256 = 6 * v255 + 38287744;
          v257 = *(__int16 *)((char *)&word_100400002[1] + v256);
          v296 = *(unsigned int *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4.Data1
                                 + v256);
          v359[0] = (PageComprInfoCache *)(v19 + 96);
          LOWORD(v360) = v246;
          *((_QWORD *)&v360 + 1) = 0;
          DWORD1(v360) = 0;
          *(_QWORD *)&v362[6] = 0;
          *(_QWORD *)((char *)&v363 + 2) = 0;
          v361 = 0;
          memset((char *)v364 + 8, 0, 18);
          if ( (v255 & 2) != 0 )
          {
            v93 = (v252[v257] & 1) == 0;
            v258 = &v252[v257];
            *((_QWORD *)&v360 + 1) = &v252[v257];
            if ( v93 )
            {
              LOWORD(v360) = 0;
              v266 = 0;
              LODWORD(v363) = 0;
              switch ( *v258 & 0xE )
              {
                case 0:
                case 2:
                case 8:
                case 0xC:
                  v266 = *((unsigned __int16 *)v258 + 1);
                  if ( (unsigned int)(v266 - 1) > 0x1F9D )
                    RaiseInconsistencyError(&v252[v257], 6);
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
                  v266 = 9;
                  break;
                case 6:
                case 0xA:
                  break;
                case 0xE:
                  v266 = 1;
                  break;
              }
              LODWORD(v361) = v266;
              v19 = v289;
              *(_QWORD *)&v362[6] = 0;
            }
            else
            {
              LOWORD(v360) = 1;
              v259 = *v258;
              switch ( *v258 & 0x1C )
              {
                case 0:
                case 0xC:
                case 0x10:
                case 0x14:
                case 0x18:
                case 0x1C:
                  if ( (v258[1] & 0x80u) != 0 )
                  {
                    v260 = 3;
                    v261 = HIBYTE(*(_WORD *)(v258 + 1)) | ((*(_WORD *)(v258 + 1) & 0x7F) << 8);
                  }
                  else
                  {
                    v260 = 2;
                    v261 = v258[1];
                  }
                  WORD1(v360) = v261;
                  *(_WORD *)v362 = v260;
                  *(_WORD *)&v362[4] = v260 + (((unsigned int)v261 + 1) >> 1);
                  if ( v261 > 0x1Eu )
                  {
                    LODWORD(v364[0]) = 0;
                    *(_QWORD *)((char *)&v363 + 2) = 0;
                    v361 = 0;
                    *(_WORD *)&v362[2] = (v261 - 1) / 30;
                  }
                  else
                  {
                    *(_WORD *)&v362[2] = 0;
                    LODWORD(v364[0]) = 0;
                    *(_QWORD *)((char *)&v363 + 2) = 0;
                    v361 = 0;
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
                  utassert_fail(
                    1u,
                    "FALSE",
                    "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                    207,
                    "Invalid switch value");
                  *(_QWORD *)((char *)&v363 + 2) = 0;
                  v361 = 0;
                  break;
                case 4:
                  if ( (v259 & 0x1C) == 4 && (v259 & 2) != 0 )
                  {
                    v264 = 1;
                    v265 = 15;
                  }
                  else
                  {
                    v264 = 0;
                    v265 = 1;
                  }
                  *(_DWORD *)v362 = 0;
                  WORD1(v360) = 0;
                  *(_WORD *)&v362[4] = 0;
                  v363 = 0.0;
                  DWORD1(v360) = v265;
                  LODWORD(v364[0]) = v264;
                  v361 = 0;
                  break;
                case 8:
                  *(_DWORD *)v362 = 0;
                  WORD1(v360) = 0;
                  *(_WORD *)&v362[4] = 0;
                  v363 = 0.0;
                  DWORD1(v360) = 9;
                  LODWORD(v364[0]) = 0;
                  v361 = 0;
                  break;
              }
            }
          }
          if ( (*(_BYTE *)v359[0] & 4) != 0 )
          {
            if ( HIWORD(v296) )
              v262 = &v252[*(unsigned __int16 *)&v252[2 * SHIWORD(v296) + 1]];
            else
              v262 = &v252[v257];
            *((_QWORD *)&v364[0] + 1) = v262;
            v263 = *(_WORD *)v262 + 1;
            *(_QWORD *)&v364[1] = v262 + 2;
            WORD4(v364[1]) = 2 * v263;
          }
          if ( v359[1] )
            PageComprInfoCache::Init(v359[1], (const struct PageComprInfo *)v359);
          v20 = 2;
          v247 = "Invalid switch value";
          v248 = v359;
          goto LABEL_623;
        }
LABEL_636:
        v254 = *(_WORD *)(v19 + 48);
        v308 = *(_QWORD *)(v19 + 40);
        v309 = v254;
        goto LABEL_630;
      }
    }
    else if ( v253 == 8 )
    {
LABEL_635:
      if ( *(_DWORD *)(v19 + 24) != 99 )
        goto LABEL_636;
      goto LABEL_628;
    }
    if ( v253 != 9 )
      goto LABEL_636;
    goto LABEL_635;
  }
  v47 = v294;
  v48 = *(int **)(a3 + 208);
  v49 = v294[8];
  if ( (v49 & 1) != 0 || (**(unsigned __int8 (__fastcall ***)(__int64))a3)(a3) )
    goto LABEL_122;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 136LL))(a3) )
    goto LABEL_50;
  if ( v294[9] || !v48 && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3) )
    goto LABEL_122;
  v50 = *(_BYTE *)(a3 + 592);
  if ( (v50 & 4) != 0 )
    goto LABEL_50;
  if ( (v50 & 0x5A) != 0 )
    goto LABEL_49;
  if ( (*(_BYTE *)(a3 + 536) & 1) != 0 )
  {
    if ( *(_QWORD *)(a3 + 208)
      || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 136LL))(a3)
      || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3) )
    {
      if ( !(unsigned int)XDES::IsActive((XDES *)a3) )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 624LL))(a3);
      if ( (*(_BYTE *)(a3 + 536) & 4) != 0 )
      {
        v120 = (XDES *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 488LL))(a3);
        DoesXactGenVersion = XDES::DoesXactGenVersion(v120);
      }
      else
      {
        if ( (*(_BYTE *)(a3 + 592) & 0x52) == 2 && XVB::IsSnapshot(*(XVB **)(a3 + 208)) )
        {
          v122 = *(_QWORD *)(a3 + 208);
          if ( !*(_BYTE *)(v122 + 304) )
          {
            *(_BYTE *)(v122 + 304) = 1;
            if ( CommonGlobalState::m_PerfCountersEnabled )
              PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
          }
        }
        DoesXactGenVersion = (*(_BYTE *)(a3 + 592) & 0x5A) != 0;
      }
      if ( DoesXactGenVersion )
      {
LABEL_49:
        if ( (*(_BYTE *)(a3 + 592) & 0x40) != 0 && v47[10] )
          goto LABEL_122;
      }
    }
    else
    {
      *(_BYTE *)(a3 + 592) |= 4u;
    }
  }
LABEL_50:
  v51 = v49 & 0x1C;
  if ( v51 )
    goto LABEL_59;
  v52 = (HoBtAccess *)*((_QWORD *)v47 + 2);
  if ( v52 )
  {
    if ( (unsigned int)HoBtAccess::IsVersioned(v52) )
    {
      v123 = *(_DWORD *)(*((_QWORD *)v52 + 1) + 256LL);
      if ( v123 )
      {
        if ( (unsigned int)(v123 - 3) > 1 )
          utassert_fail(
            1u,
            "!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()",
            "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
            278,
            0);
      }
    }
    if ( (unsigned int)HoBtAccess::IsOibLobSourceRowset(v52) )
    {
      v124 = *((_QWORD *)v52 + 1);
      if ( (*(_BYTE *)(v124 + 265) & 1) == 0 )
      {
        v125 = *(_DWORD *)(v124 + 256);
        if ( v125 )
        {
          if ( (unsigned int)(v125 - 3) > 1 )
            utassert_fail(
              1u,
              "(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAcc"
              "ess->IsCompressedRowstore ()",
              "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
              281,
              0);
        }
      }
    }
  }
  if ( v48 && (v48[30] > 0 || v48[29] > 0) )
  {
LABEL_61:
    v54 = (HoBtAccess *)*((_QWORD *)v294 + 2);
    if ( v54 )
    {
      if ( (unsigned int)HoBtAccess::IsVersioned(*((HoBtAccess **)v294 + 2)) )
      {
        v129 = *(_DWORD *)(*((_QWORD *)v54 + 1) + 256LL);
        if ( v129 )
        {
          if ( (unsigned int)(v129 - 3) > 1 )
            utassert_fail(
              1u,
              "!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()",
              "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
              278,
              0);
        }
      }
      if ( (unsigned int)HoBtAccess::IsOibLobSourceRowset(v54) )
      {
        v130 = *((_QWORD *)v54 + 1);
        if ( (*(_BYTE *)(v130 + 265) & 1) == 0 )
        {
          v131 = *(_DWORD *)(v130 + 256);
          if ( v131 )
          {
            if ( (unsigned int)(v131 - 3) > 1 )
              utassert_fail(
                1u,
                "(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtA"
                "ccess->IsCompressedRowstore ()",
                "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
                281,
                0);
          }
        }
      }
    }
    if ( v48[30] > 0 || v48[29] > 0 )
      goto LABEL_72;
    v55 = *(_BYTE *)(a3 + 592);
    if ( (v55 & 4) == 0 )
    {
      if ( (v55 & 0x5A) != 0 )
        goto LABEL_68;
      if ( (*(_BYTE *)(a3 + 536) & 1) != 0 )
      {
        if ( *(_QWORD *)(a3 + 208)
          || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 136LL))(a3)
          || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3) )
        {
          if ( !(unsigned int)XDES::IsActive((XDES *)a3) )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 624LL))(a3);
          if ( (*(_BYTE *)(a3 + 536) & 4) != 0 )
          {
            v132 = (XDES *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 488LL))(a3);
            v133 = XDES::DoesXactGenVersion(v132);
          }
          else
          {
            if ( (*(_BYTE *)(a3 + 592) & 0x52) == 2 && XVB::IsSnapshot(*(XVB **)(a3 + 208)) )
            {
              v134 = *(_QWORD *)(a3 + 208);
              if ( !*(_BYTE *)(v134 + 304) )
              {
                *(_BYTE *)(v134 + 304) = 1;
                if ( CommonGlobalState::m_PerfCountersEnabled )
                  PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
              }
            }
            v133 = (*(_BYTE *)(a3 + 592) & 0x5A) != 0;
          }
          if ( v133 )
          {
LABEL_68:
            if ( (*(_BYTE *)(a3 + 592) & 0x10) != 0 )
              goto LABEL_73;
          }
        }
        else
        {
          *(_BYTE *)(a3 + 592) |= 4u;
        }
      }
    }
    v56 = *(_BYTE *)(a3 + 592);
    if ( (v56 & 4) != 0 )
      goto LABEL_72;
    if ( (v56 & 0x5A) == 0 )
    {
      if ( (*(_BYTE *)(a3 + 536) & 1) == 0 )
        goto LABEL_72;
      if ( !*(_QWORD *)(a3 + 208)
        && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 136LL))(a3)
        && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3) )
      {
        *(_BYTE *)(a3 + 592) |= 4u;
        goto LABEL_72;
      }
      if ( !(unsigned int)XDES::IsActive((XDES *)a3) )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 624LL))(a3);
      if ( (*(_BYTE *)(a3 + 536) & 4) != 0 )
      {
        v135 = (XDES *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 488LL))(a3);
        v136 = XDES::DoesXactGenVersion(v135);
      }
      else
      {
        if ( (*(_BYTE *)(a3 + 592) & 0x52) == 2 && XVB::IsSnapshot(*(XVB **)(a3 + 208)) )
        {
          v137 = *(_QWORD *)(a3 + 208);
          if ( !*(_BYTE *)(v137 + 304) )
          {
            *(_BYTE *)(v137 + 304) = 1;
            if ( CommonGlobalState::m_PerfCountersEnabled )
              PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
          }
        }
        v136 = (*(_BYTE *)(a3 + 592) & 0x5A) != 0;
      }
      if ( !v136 )
        goto LABEL_72;
    }
    if ( (*(_BYTE *)(a3 + 592) & 0x40) == 0 )
LABEL_72:
      XVB::Enqueue((XVB *)v48, 0);
LABEL_73:
    if ( !(unsigned int)XDES::IsActive((XDES *)a3) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 624LL))(a3);
    v57 = v290;
    v58 = *(BUF **)v290;
    v59 = *(_QWORD *)(*(_QWORD *)v290 + 144LL);
    if ( !v59 )
    {
      BUF::FixupPru(*(BUF **)v290);
      v59 = *((_QWORD *)v58 + 18);
      v57 = v290;
    }
    if ( *(_WORD *)(v59 + 1662) < 0x387u )
      LOBYTE(v60) = ~(*(_BYTE *)(*(_QWORD *)v58 + 2LL) >> 6);
    else
      v60 = (unsigned __int16)~*((_WORD *)v58 + 49) >> 8;
    if ( (v60 & 1) != 0 )
      PageRef::SetVersionState(v57, 1, (struct XDES *)a3);
    v61 = *(_QWORD *)(a3 + 208);
    v62 = (*((_DWORD *)v294 + 6) >> 1) & 1;
    v93 = (v294[8] & 0x24) == 0;
    v310 = v62;
    if ( v93 )
    {
      v63 = *(_BYTE *)(a3 + 592);
      if ( (v63 & 4) != 0 )
        goto LABEL_280;
      if ( (v63 & 0x5A) == 0 )
      {
        if ( (*(_BYTE *)(a3 + 536) & 1) == 0 )
          goto LABEL_280;
        if ( !v61
          && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 136LL))(a3)
          && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3) )
        {
          *(_BYTE *)(a3 + 592) |= 4u;
          v64 = 0;
          v292 = 0;
          goto LABEL_85;
        }
        if ( !(unsigned int)XDES::IsActive((XDES *)a3) )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 624LL))(a3);
        if ( (*(_BYTE *)(a3 + 536) & 4) != 0 )
        {
          v138 = (XDES *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 488LL))(a3);
          v139 = XDES::DoesXactGenVersion(v138);
        }
        else
        {
          if ( (*(_BYTE *)(a3 + 592) & 0x52) == 2 && XVB::IsSnapshot(*(XVB **)(a3 + 208)) )
          {
            v140 = *(_QWORD *)(a3 + 208);
            if ( !*(_BYTE *)(v140 + 304) )
            {
              *(_BYTE *)(v140 + 304) = 1;
              if ( CommonGlobalState::m_PerfCountersEnabled )
              {
                v141 = 0;
                if ( pCounterLookupBlocks )
                  v141 = (char *)pCounterLookupBlocks + 57344;
                if ( v141 && *(_QWORD *)v141 )
                  _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v141 + 16LL), 1u);
              }
            }
          }
          v139 = (*(_BYTE *)(a3 + 592) & 0x5A) != 0;
        }
        if ( !v139 )
        {
LABEL_280:
          if ( !v61 || *(int *)(v61 + 116) <= 0 )
          {
            v64 = 0;
            v292 = 0;
            goto LABEL_85;
          }
        }
      }
    }
    v64 = 1;
    v292 = 1;
LABEL_85:
    if ( !v62 && !v64 )
      goto LABEL_122;
    v65 = v289;
    v66 = -1;
    v331 = a6;
    v324 = -1;
    Source = 0;
    v326 = 0;
    v67 = 15;
    *(_QWORD *)&v329[6] = 0;
    *(_QWORD *)&v329[16] = 0;
    v328 = 0;
    v340 = -1;
    v343 = 0;
    v342 = 0;
    v347 = 0;
    *(_QWORD *)((char *)&v348 + 2) = 0;
    v344 = 0;
    Destination = 0;
    v350 = 0;
    SourceSize = 9;
    if ( *(char *)(v289 + 2) >= 0 )
    {
      v68 = 0;
      goto LABEL_89;
    }
    v142 = (unsigned __int8 *)(v289 + 96);
    _mm_prefetch((const char *)(v289 + 96), 0);
    v68 = v332;
    v333 = 0xFFFFu;
    memset(v335, 0, sizeof(v335));
    v339 = 0;
    v336 = 0.0;
    memset(v337, 0, sizeof(v337));
    v334 = 0;
    v338 = 0u;
    *(_OWORD *)v332 = 0;
    if ( !*(_WORD *)(v289 + 36) )
      goto LABEL_303;
    v143 = *(_BYTE *)(v289 + 1);
    if ( v143 == 11 )
    {
      if ( *(_DWORD *)(v289 + 24) == 99 )
      {
LABEL_295:
        v296 = *(_DWORD *)(v289 + 32);
        v297 = *(_WORD *)(v289 + 36);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v296, "Invalid switch value") )
        {
          PageHeader::GetIcxLsn(v289, &v306);
          v144 = v307;
LABEL_297:
          v145 = *v142;
          *(_QWORD *)&v338 = v306;
          HIDWORD(v338) = *(_DWORD *)(v289 + 32);
          LODWORD(v339) = *(unsigned __int16 *)(v289 + 36);
          WORD4(v338) = v144;
          v146 = 6 * v145 + 38287744;
          v147 = *(__int16 *)((char *)&word_100400002[1] + v146);
          v148 = *(unsigned int *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4.Data1
                                 + v146);
          LOWORD(DestinationSize) = *(__int16 *)((char *)&word_100400002[1] + v146);
          v332[0] = (PageComprInfoCache *)(v289 + 96);
          LODWORD(v291) = v148;
          LOWORD(v333) = v66;
          *((_QWORD *)&v333 + 1) = 0;
          DWORD1(v333) = 0;
          *(_QWORD *)&v335[6] = 0;
          *(_QWORD *)((char *)&v336 + 2) = 0;
          v334 = 0;
          memset((char *)v337 + 8, 0, 18);
          if ( (v145 & 2) != 0 )
          {
            v149 = &v142[v147];
            v93 = (*v149 & 1) == 0;
            *((_QWORD *)&v333 + 1) = v149;
            if ( v93 )
            {
              LOWORD(v333) = 0;
              v157 = 0;
              LODWORD(v336) = 0;
              switch ( *v149 & 0xE )
              {
                case 0:
                case 2:
                case 8:
                case 0xC:
                  v157 = *((unsigned __int16 *)v149 + 1);
                  if ( (unsigned int)(v157 - 1) > 0x1F9D )
                    RaiseInconsistencyError(v149, 6);
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
                  v157 = 9;
                  break;
                case 6:
                case 0xA:
                  break;
                case 0xE:
                  v157 = 1;
                  break;
              }
              LODWORD(v334) = v157;
              v65 = v289;
              *(_QWORD *)&v335[6] = 0;
            }
            else
            {
              LOWORD(v333) = 1;
              v150 = *v149;
              switch ( *v149 & 0x1C )
              {
                case 0:
                case 0xC:
                case 0x10:
                case 0x14:
                case 0x18:
                case 0x1C:
                  if ( (v149[1] & 0x80u) != 0 )
                  {
                    v151 = 3;
                    v152 = HIBYTE(*(_WORD *)(v149 + 1)) | ((*(_WORD *)(v149 + 1) & 0x7F) << 8);
                  }
                  else
                  {
                    v151 = 2;
                    v152 = v149[1];
                  }
                  WORD1(v333) = v152;
                  *(_WORD *)v335 = v151;
                  *(_WORD *)&v335[4] = v151 + (((unsigned int)v152 + 1) >> 1);
                  if ( v152 > 0x1Eu )
                  {
                    LODWORD(v337[0]) = 0;
                    *(_QWORD *)((char *)&v336 + 2) = 0;
                    v334 = 0;
                    *(_WORD *)&v335[2] = (v152 - 1) / 30;
                  }
                  else
                  {
                    *(_WORD *)&v335[2] = 0;
                    LODWORD(v337[0]) = 0;
                    *(_QWORD *)((char *)&v336 + 2) = 0;
                    v334 = 0;
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
                  utassert_fail(
                    1u,
                    "FALSE",
                    "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                    207,
                    "Invalid switch value");
                  *(_QWORD *)((char *)&v336 + 2) = 0;
                  v334 = 0;
                  break;
                case 4:
                  if ( (v150 & 0x1C) == 4 && (v150 & 2) != 0 )
                  {
                    v155 = 1;
                    v156 = 15;
                  }
                  else
                  {
                    v155 = 0;
                    v156 = 1;
                  }
                  *(_DWORD *)v335 = 0;
                  WORD1(v333) = 0;
                  *(_WORD *)&v335[4] = 0;
                  v336 = 0.0;
                  DWORD1(v333) = v156;
                  LODWORD(v337[0]) = v155;
                  v334 = 0;
                  break;
                case 8:
                  *(_DWORD *)v335 = 0;
                  WORD1(v333) = 0;
                  *(_WORD *)&v335[4] = 0;
                  v336 = 0.0;
                  DWORD1(v333) = 9;
                  LODWORD(v337[0]) = 0;
                  v334 = 0;
                  break;
              }
            }
            LOWORD(v147) = DestinationSize;
          }
          if ( (*(_BYTE *)v332[0] & 4) != 0 )
          {
            if ( WORD1(v291) )
              v153 = *(unsigned __int16 *)&v142[2 * SWORD1(v291) + 1];
            else
              v153 = (__int16)v147;
            *((_QWORD *)&v337[0] + 1) = &v142[v153];
            v154 = *(_WORD *)&v142[v153] + 1;
            *(_QWORD *)&v337[1] = &v142[v153 + 2];
            WORD4(v337[1]) = 2 * v154;
          }
          if ( v332[1] )
            PageComprInfoCache::Init(v332[1], (const struct PageComprInfo *)v332);
          v20 = 2;
LABEL_89:
          v69 = *(unsigned __int16 *)(v65 + 14);
          v70 = (char *)(v289 + *(unsigned __int16 *)(v289 + 2 * (4095LL - (int)a6)));
          v93 = (*v70 & 1) == 0;
          Source = v70;
          if ( v93 )
          {
            v324 = 0;
            v67 = 0;
            v326 = 0;
            *(_DWORD *)&v329[14] = 0;
            switch ( *v70 & 0xE )
            {
              case 0:
              case 2:
              case 8:
              case 0xC:
                JUMPOUT(0x10049EE9DLL);
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
                v67 = v326;
                break;
              case 4:
                v69 = 9;
                break;
              case 6:
              case 0xA:
                break;
              case 0xE:
                v69 = 1;
                break;
            }
            LODWORD(v328) = v69;
            v68 = v328;
            *(_QWORD *)&v329[6] = v289 + 0x2000;
          }
          else
          {
            v324 = 1;
            v158 = *v70;
            switch ( *v70 & 0x1C )
            {
              case 0:
              case 0xC:
              case 0x10:
              case 0x14:
              case 0x18:
              case 0x1C:
                if ( v70[1] < 0 )
                {
                  v160 = *(_WORD *)(v70 + 1);
                  v20 = 3;
                  *(_WORD *)v329 = 3;
                  v159 = HIBYTE(v160) | ((v160 & 0x7F) << 8);
                  v325 = v159;
                }
                else
                {
                  v159 = (unsigned __int8)v70[1];
                  v325 = v159;
                  *(_WORD *)v329 = 2;
                }
                *(_WORD *)&v329[4] = v20 + ((unsigned __int16)(v159 + 1) >> 1);
                if ( v159 > 0x1Eu )
                {
                  v326 = 0;
                  v67 = 0;
                  v330 = 0;
                  *(_WORD *)&v329[2] = (v159 - 1) / 30;
                }
                else
                {
                  *(_WORD *)&v329[2] = 0;
                  v67 = 0;
                  v326 = 0;
                  v330 = 0;
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
                utassert_fail(
                  1u,
                  "FALSE",
                  "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                  207,
                  "Invalid switch value");
                v67 = v326;
                break;
              case 4:
                if ( (v158 & 0x1C) == 4 && (v158 & 2) != 0 )
                {
                  *(_QWORD *)v329 = 0;
                  v325 = 0;
                  *(_QWORD *)&v329[8] = 0;
                  v326 = 15;
                  v330 = 1;
                }
                else
                {
                  *(_QWORD *)v329 = 0;
                  v67 = 1;
                  v325 = 0;
                  *(_QWORD *)&v329[8] = 0;
                  v326 = 1;
                  v330 = 0;
                }
                break;
              case 8:
                v67 = 9;
                *(_QWORD *)v329 = 0;
                v326 = 9;
                v325 = 0;
                *(_QWORD *)&v329[8] = 0;
                v330 = 0;
                break;
            }
            v328 = v68;
            *(_QWORD *)&v329[16] = v289 + 0x2000;
          }
          v71 = *(_BYTE *)(((unsigned __int64)Source & 0xFFFFFFFFFFFFE000uLL) + 2);
          if ( v71 < 0 && !Destination )
          {
            v161 = alloca(8096);
            v350 = 8094;
            Destination = &v276;
            v71 = *(_BYTE *)(((unsigned __int64)Source & 0xFFFFFFFFFFFFE000uLL) + 2);
          }
          if ( v71 >= 0 )
          {
            v72 = &v324;
            goto LABEL_95;
          }
          v162 = v350;
          v163 = (char *)Destination;
          LODWORD(DestinationSize) = v350;
          v340 = v324;
          if ( v324 )
          {
            if ( !v68 || !*v68 )
            {
              CDRecord::CopyNewRec(
                (CDRecord *)&v341,
                (unsigned __int8 *)Destination,
                v350,
                (const struct CDRecord *)&v325);
              v68 = v328;
              v196 = v328;
              if ( !v324 )
                v196 = 0;
              v344 = v196;
              goto LABEL_441;
            }
            Record::DecompressRec((Record *)&v340, (unsigned __int8 *)Destination, v350, (const struct Record *)&v324);
          }
          else
          {
            if ( v67 )
            {
              v167 = *(_DWORD *)v329;
            }
            else
            {
              v67 = (unsigned int)v328;
              v325 = 0;
              HIDWORD(v328) = (_DWORD)v328;
              if ( (*(_BYTE *)Source & 0x10) != 0 )
              {
                v67 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v328) + 7) >> 3)
                    + (_DWORD)v328
                    + 2;
                HIDWORD(v328) = v67;
              }
              if ( (*(_BYTE *)Source & 0x20) != 0 )
              {
                v164 = (char *)Source + v67;
                *(_WORD *)&v329[4] = *v164;
                if ( !*(_WORD *)&v329[4] )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v165 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v165 )
                    {
                      v166 = *(_QWORD *)(v165 + 96);
                      if ( v166 )
                      {
                        if ( *(_BYTE *)(v166 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          else
                            ex_raise(34, 68, 21, 1003);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(Source, 3);
                }
                v167 = HIDWORD(v328) + 2 * (*(unsigned __int16 *)&v329[4] + 1);
                *(_DWORD *)v329 = v167;
                if ( v167 > 0x1F9E )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v168 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v168 )
                    {
                      v169 = *(_QWORD *)(v168 + 96);
                      if ( v169 )
                      {
                        if ( *(_BYTE *)(v169 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(Source, 4);
                  v167 = *(_DWORD *)v329;
                }
                v67 = v164[*(unsigned __int16 *)&v329[4]] & 0x7FFF;
                v326 = v67;
                if ( v167 > v67 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v170 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v170 )
                    {
                      v171 = *(_QWORD *)(v170 + 96);
                      if ( v171 )
                      {
                        if ( *(_BYTE *)(v171 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(Source, 4);
                  v167 = *(_DWORD *)v329;
                  v67 = v326;
                }
                while ( 1 )
                {
                  if ( (__int16)v164[*(unsigned __int16 *)&v329[4]] >= 0 )
                    goto LABEL_397;
                  v172 = (char *)Source + HIDWORD(v328);
                  if ( *(unsigned __int16 *)&v329[4] == 1 )
                  {
                    v173 = v167;
                  }
                  else
                  {
                    v173 = *(_WORD *)&v172[2 * *(unsigned __int16 *)&v329[4] - 2] & 0x7FFF;
                    if ( v173 < v167 )
                    {
LABEL_391:
                      RaiseInconsistencyError(Source, 7);
                      v167 = *(_DWORD *)v329;
                      v67 = v326;
                      goto LABEL_392;
                    }
                  }
                  if ( (*(_WORD *)&v172[2 * *(unsigned __int16 *)&v329[4]] & 0x7FFFu) < v173 )
                    goto LABEL_391;
LABEL_392:
                  if ( v173 < v167 || v173 > v67 )
                    goto LABEL_426;
                  v174 = *(_WORD *)((char *)Source + v173);
                  if ( v174 == 5 )
                  {
                    --*(_WORD *)&v329[4];
                    v325 |= 2u;
                    *(_WORD *)&v329[18] = v173;
                    v193 = (char *)Source + (unsigned __int16)v173;
                    v194 = *((_WORD *)v193 + 1);
                    if ( (v194 & 0x4000) != 0 )
                      v195 = (*(_WORD *)&v329[20] ^ v194) & 0x3800 ^ *(_WORD *)&v329[20];
                    else
                      v195 = *(_WORD *)&v329[20] & 0xC7FF;
                    *(_WORD *)&v329[20] = v195;
                    *(_WORD *)&v329[20] = v195 ^ (*((_WORD *)v193 + 1) ^ v195) & 0x7FF;
                    goto LABEL_397;
                  }
                  if ( v174 >= 0x400u )
                  {
                    v325 |= 1u;
                    if ( --*(_WORD *)&v329[4] )
                      continue;
                  }
                  goto LABEL_397;
                }
              }
              v326 = v67;
              v167 = v67;
              *(_WORD *)&v329[4] = 0;
              *(_DWORD *)v329 = v67;
LABEL_397:
              if ( (*(_BYTE *)Source & 0x40) != 0 )
              {
                *(_DWORD *)&v329[14] = v67;
                v326 = v67 + 14;
                VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v325);
                v176 = 0;
                v177 = HIDWORD(*(_QWORD *)VersioningInfo);
                v178 = HIWORD(*(_QWORD *)VersioningInfo);
                if ( (((__int16)v178 ^ ((unsigned int)(__int16)v178 >> 1)) & 0x2000) != 0 )
                {
                  v179 = v178 & 0xDFFF;
                  if ( (v178 & 0x4000) != 0 )
                    v179 = v178 | 0x2000;
                  LOWORD(v178) = v179;
                }
                if ( (_WORD)v178 == 0xFFFC )
                  v176 = (unsigned __int16)v177 >> 5;
                v167 = *(_DWORD *)v329;
                v67 = v176 + v326;
                v326 += v176;
              }
              else
              {
                *(_DWORD *)&v329[14] = 0;
              }
              if ( *(_QWORD *)&v329[6] && *(_QWORD *)&v329[6] < (unsigned __int64)Source + v67 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v180 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v180 )
                  {
                    v181 = *(_QWORD *)(v180 + 96);
                    if ( v181 )
                    {
                      if ( *(_BYTE *)(v181 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(Source, 18);
                v167 = *(_DWORD *)v329;
                v67 = v326;
              }
              if ( v67 - 1 > 0x3F3B )
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
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(Source, 5);
                v167 = *(_DWORD *)v329;
                v67 = v326;
              }
LABEL_426:
              v162 = (unsigned int)DestinationSize;
            }
            if ( v67 >= 9 || (v184 = *(_BYTE *)Source & 0xE) != 0 && v184 != 12 )
              v185 = v67;
            else
              v185 = 9;
            v344 = v328;
            v341 = v325;
            v346 = *(_WORD *)&v329[4];
            v345 = v167;
            LODWORD(v348) = *(_DWORD *)&v329[14];
            v342 = v67;
            memcpy_s(v163, v162, Source, v185);
            v343 = v163;
            if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v341) )
            {
              v186 = v343;
              v187 = &v343[HIDWORD(v344)];
              v188 = *(unsigned __int16 *)v187 - 1;
              if ( (v341 & 1) == 0 )
                v188 = *(unsigned __int16 *)v187;
              if ( v188 == 1 )
              {
                v189 = v345;
              }
              else
              {
                v189 = *(_WORD *)&v187[2 * v188 - 2] & 0x7FFF;
                if ( v189 < v345 )
                  goto LABEL_437;
              }
              if ( (*(_WORD *)&v187[2 * v188] & 0x7FFFu) >= v189 )
              {
LABEL_438:
                WORD2(v348) = v189;
                v190 = &v186[(unsigned __int16)v189];
                v191 = *((_WORD *)v190 + 1);
                if ( (v191 & 0x4000) != 0 )
                  v192 = (WORD3(v348) ^ v191) & 0x3800 ^ WORD3(v348);
                else
                  v192 = WORD3(v348) & 0xC7FF;
                v68 = v328;
                WORD3(v348) = v192;
                WORD3(v348) = v192 ^ (*((_WORD *)v190 + 1) ^ v192) & 0x7FF;
                goto LABEL_441;
              }
LABEL_437:
              RaiseInconsistencyError(v343, 7);
              v186 = v343;
              goto LABEL_438;
            }
          }
          v68 = v328;
LABEL_441:
          v67 = v326;
          v72 = &v340;
LABEL_95:
          v73 = 0;
          v74 = (_BYTE *)*((_QWORD *)v72 + 1);
          if ( *v72 )
          {
            LOBYTE(v73) = (((*v74 & 0x1C) - 4) & 0xFFFFFFE7) == 0;
          }
          else
          {
            v75 = *v74 & 0xE;
            LODWORD(DestinationSize) = 0;
            if ( v75 != 2 )
            {
              if ( ((v75 - 10) & 0xF9) == 0 )
              {
                LOBYTE(v73) = 1;
                LODWORD(DestinationSize) = 1;
              }
LABEL_99:
              v76 = v299;
              if ( v299 )
              {
                v79 = v292;
                v77 = v299;
                v78 = v294;
                goto LABEL_104;
              }
              if ( *(char *)(((unsigned __int64)Source & 0xFFFFFFFFFFFFE000uLL) + 2) >= 0 )
              {
                v77 = &v324;
LABEL_102:
                v78 = v294;
                v79 = v292;
                LOBYTE(v278) = 0;
                v80 = *((unsigned int *)v294 + 6);
                LOBYTE(v277) = v292;
                if ( (unsigned __int8)PageRef::CanUseInRowGhost(v290, v77, a3, v80, (_DWORD)v277, v278) )
                {
                  v230 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 80LL))(a3);
                  v84 = 1;
                  v300 = v230 | 0xFFFC000100000000uLL;
                  v231 = *(_QWORD *)(*(_QWORD *)(v295 + 8) + 1160LL);
                  if ( v231 && CommonGlobalState::m_CollectingStatistics && (byte_10317ABD0 & 2) == 0 )
                  {
                    if ( !*(_QWORD *)(v231 + 32) )
                      goto LABEL_599;
                    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v232 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v233 = *(_QWORD *)(v232 + 256);
                    if ( !v233 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v233 = *(_QWORD *)(v232 + 256);
                      v84 = 1;
                    }
                    v234 = *(_QWORD *)(v233 + 608);
                    v235 = v234 ? *(unsigned int *)(v234 + 3688) : 0LL;
                    if ( (unsigned int)v235 < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2) )
                    {
                      _mm_lfence();
                      ThreadLocalStoragePointer = *(_QWORD **)(*(_QWORD *)(v231 + 32) + 8 * v235);
                      ++ThreadLocalStoragePointer[41];
                    }
                    else
                    {
LABEL_599:
                      _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)(v231 + 24) + 328LL), 1u);
                    }
                  }
                  goto LABEL_117;
                }
                v68 = v328;
                v76 = v299;
LABEL_104:
                v81 = v324 && v68 && *v68;
                v82 = *(_OWORD *)(v78 + 8);
                LODWORD(v287) = 0;
                v286 = 0;
                v285 = &v300;
                v284 = (char *)&SourceSize + 4;
                LODWORD(v283) = *((_DWORD *)v78 + 7);
                v323 = v82;
                VersionMgr::GenerateVersion(
                  (unsigned __int8 *)&v323,
                  v321,
                  a3,
                  v289,
                  (__int64)v77,
                  1u,
                  v76 == 0,
                  v81,
                  0,
                  v310,
                  (unsigned int)v283,
                  (_DWORD *)&SourceSize + 1,
                  (VersionRecPtr *)&v300,
                  0,
                  v287);
                if ( HIDWORD(SourceSize) == 2 )
                {
                  v85 = v295;
                  v86 = *(_QWORD *)(*(_QWORD *)(v295 + 8) + 1160LL);
                  if ( v86 && CommonGlobalState::m_CollectingStatistics && (byte_10317ABD0 & 2) == 0 )
                  {
                    if ( !*(_QWORD *)(v86 + 32) )
                      goto LABEL_111;
                    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v237 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v238 = *(_QWORD *)(v237 + 256);
                    if ( !v238 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v238 = *(_QWORD *)(v237 + 256);
                    }
                    v239 = *(_QWORD *)(v238 + 608);
                    v240 = v239 ? *(unsigned int *)(v239 + 3688) : 0LL;
                    if ( (unsigned int)v240 < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2) )
                    {
                      _mm_lfence();
                      ThreadLocalStoragePointer = *(_QWORD **)(*(_QWORD *)(v86 + 32) + 8 * v240);
                      ++ThreadLocalStoragePointer[40];
                    }
                    else
                    {
LABEL_111:
                      _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)(v86 + 24) + 320LL), 1u);
                    }
                  }
                  v87 = *(_QWORD *)(*(_QWORD *)(v85 + 8) + 1160LL);
                  if ( v87 && CommonGlobalState::m_CollectingStatistics && (byte_10317ABD0 & 2) == 0 )
                  {
                    if ( !*(_QWORD *)(v87 + 32) )
                      goto LABEL_116;
                    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v241 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v242 = *(_QWORD *)(v241 + 256);
                    if ( !v242 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v242 = *(_QWORD *)(v241 + 256);
                    }
                    v243 = *(_QWORD *)(v242 + 608);
                    v244 = v243 ? *(unsigned int *)(v243 + 3688) : 0LL;
                    if ( (unsigned int)v244 < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2) )
                    {
                      _mm_lfence();
                      ThreadLocalStoragePointer = *(_QWORD **)(*(_QWORD *)(v87 + 32) + 8 * v244);
                      ++ThreadLocalStoragePointer[42];
                    }
                    else
                    {
LABEL_116:
                      _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)(v87 + 24) + 336LL), 1u);
                    }
                  }
                }
LABEL_117:
                if ( v79 )
                {
                  if ( v299 )
                  {
                    v245 = 8;
                    if ( (_BYTE)v73 )
                      v245 = 0x100000;
                    v293 = v245;
                  }
                  v93 = (*(_BYTE *)(a3 + 536) & 4) == 0;
                  v367 = v300;
                  if ( v93 )
                    v88 = a3 + 40;
                  else
                    v88 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a3 + 488LL))(
                            a3,
                            ThreadLocalStoragePointer,
                            v84)
                        + 40;
                  v368 = *(_DWORD *)v88;
                  v369 = *(_WORD *)(v88 + 4);
                  v301 = &v367;
                }
                goto LABEL_122;
              }
              v197 = v350;
              v198 = (char *)Destination;
              LODWORD(v291) = v350;
              v340 = v324;
              if ( v324 )
              {
                if ( v68 && *v68 )
                {
                  Record::DecompressRec(
                    (Record *)&v340,
                    (unsigned __int8 *)Destination,
                    v350,
                    (const struct Record *)&v324);
                }
                else
                {
                  CDRecord::CopyNewRec(
                    (CDRecord *)&v341,
                    (unsigned __int8 *)Destination,
                    v350,
                    (const struct CDRecord *)&v325);
                  v236 = v328;
                  if ( !v324 )
                    v236 = 0;
                  v344 = v236;
                }
                goto LABEL_570;
              }
              if ( v67 )
              {
                v202 = *(_DWORD *)v329;
              }
              else
              {
                v67 = (unsigned int)v328;
                v325 = 0;
                HIDWORD(v328) = (_DWORD)v328;
                if ( (*(_BYTE *)Source & 0x10) != 0 )
                {
                  v67 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v328) + 7) >> 3)
                      + (_DWORD)v328
                      + 2;
                  HIDWORD(v328) = v67;
                }
                if ( (*(_BYTE *)Source & 0x20) != 0 )
                {
                  v199 = (char *)Source + v67;
                  *(_WORD *)&v329[4] = *v199;
                  if ( !*(_WORD *)&v329[4] )
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
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                            else
                              ex_raise(34, 68, 21, 1003);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(Source, 3);
                  }
                  v202 = HIDWORD(v328) + 2 * (*(unsigned __int16 *)&v329[4] + 1);
                  *(_DWORD *)v329 = v202;
                  if ( v202 > 0x1F9E )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v203 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v203 )
                      {
                        v204 = *(_QWORD *)(v203 + 96);
                        if ( v204 )
                        {
                          if ( *(_BYTE *)(v204 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(Source, 4);
                    v202 = *(_DWORD *)v329;
                  }
                  v67 = v199[*(unsigned __int16 *)&v329[4]] & 0x7FFF;
                  v326 = v67;
                  if ( v202 > v67 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v205 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v205 )
                      {
                        v206 = *(_QWORD *)(v205 + 96);
                        if ( v206 )
                        {
                          if ( *(_BYTE *)(v206 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(Source, 4);
                    v202 = *(_DWORD *)v329;
                    v67 = v326;
                  }
                  while ( 1 )
                  {
                    if ( (__int16)v199[*(unsigned __int16 *)&v329[4]] >= 0 )
                      goto LABEL_525;
                    v207 = (char *)Source + HIDWORD(v328);
                    if ( *(unsigned __int16 *)&v329[4] == 1 )
                    {
                      v208 = v202;
                    }
                    else
                    {
                      v208 = *(_WORD *)&v207[2 * *(unsigned __int16 *)&v329[4] - 2] & 0x7FFF;
                      if ( v208 < v202 )
                      {
LABEL_510:
                        RaiseInconsistencyError(Source, 7);
                        v202 = *(_DWORD *)v329;
                        v67 = v326;
                        goto LABEL_511;
                      }
                    }
                    if ( (*(_WORD *)&v207[2 * *(unsigned __int16 *)&v329[4]] & 0x7FFFu) < v208 )
                      goto LABEL_510;
LABEL_511:
                    if ( v208 < v202 || v208 > v67 )
                      goto LABEL_554;
                    v209 = *(_WORD *)((char *)Source + v208);
                    if ( v209 == 5 )
                    {
                      v325 |= 2u;
                      --*(_WORD *)&v329[4];
                      *(_WORD *)&v329[18] = v208;
                      v210 = (char *)Source + (unsigned __int16)v208;
                      v211 = *((_WORD *)v210 + 1);
                      if ( (v211 & 0x4000) != 0 )
                        v212 = (*(_WORD *)&v329[20] ^ v211) & 0x3800 ^ *(_WORD *)&v329[20];
                      else
                        v212 = *(_WORD *)&v329[20] & 0xC7FF;
                      *(_WORD *)&v329[20] = v212;
                      *(_WORD *)&v329[20] = v212 ^ (*((_WORD *)v210 + 1) ^ v212) & 0x7FF;
                      goto LABEL_525;
                    }
                    if ( v209 >= 0x400u )
                    {
                      v325 |= 1u;
                      if ( --*(_WORD *)&v329[4] )
                        continue;
                    }
                    goto LABEL_525;
                  }
                }
                v202 = v67;
                v326 = v67;
                *(_DWORD *)v329 = v67;
                *(_WORD *)&v329[4] = 0;
LABEL_525:
                if ( (*(_BYTE *)Source & 0x40) != 0 )
                {
                  *(_DWORD *)&v329[14] = v67;
                  v326 = v67 + 14;
                  v213 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v325);
                  v214 = 0;
                  v215 = HIDWORD(*(_QWORD *)v213);
                  v216 = HIWORD(*(_QWORD *)v213);
                  if ( (((__int16)v216 ^ ((unsigned int)(__int16)v216 >> 1)) & 0x2000) != 0 )
                  {
                    v217 = v216 & 0xDFFF;
                    if ( (v216 & 0x4000) != 0 )
                      v217 = v216 | 0x2000;
                    LOWORD(v216) = v217;
                  }
                  if ( (_WORD)v216 == 0xFFFC )
                    v214 = (unsigned __int16)v215 >> 5;
                  v202 = *(_DWORD *)v329;
                  v67 = v214 + v326;
                  v326 += v214;
                }
                else
                {
                  *(_DWORD *)&v329[14] = 0;
                }
                if ( *(_QWORD *)&v329[6] && *(_QWORD *)&v329[6] < (unsigned __int64)Source + v67 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v218 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v218 )
                    {
                      v219 = *(_QWORD *)(v218 + 96);
                      if ( v219 )
                      {
                        if ( *(_BYTE *)(v219 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                          else
                            ex_raise(34, 68, 21, 1018);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(Source, 18);
                  v202 = *(_DWORD *)v329;
                  v67 = v326;
                }
                if ( v67 - 1 > 0x3F3B )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v220 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v220 )
                    {
                      v221 = *(_QWORD *)(v220 + 96);
                      if ( v221 )
                      {
                        if ( *(_BYTE *)(v221 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                          else
                            ex_raise(34, 68, 21, 1005);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(Source, 5);
                  v202 = *(_DWORD *)v329;
                  v67 = v326;
                }
LABEL_554:
                v197 = v291;
              }
              if ( v67 >= 9 || (v222 = *(_BYTE *)Source & 0xE) != 0 && v222 != 12 )
                LODWORD(SourceSize) = v67;
              v344 = v328;
              v341 = v325;
              v346 = *(_WORD *)&v329[4];
              v345 = v202;
              LODWORD(v348) = *(_DWORD *)&v329[14];
              v342 = v67;
              memcpy_s(v198, v197, Source, (unsigned int)SourceSize);
              v343 = v198;
              if ( !(unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v341) )
              {
LABEL_569:
                LOBYTE(v73) = DestinationSize;
LABEL_570:
                v77 = &v340;
                goto LABEL_102;
              }
              v223 = v343;
              v224 = &v343[HIDWORD(v344)];
              v225 = *(unsigned __int16 *)v224 - 1;
              if ( (v341 & 1) == 0 )
                v225 = *(unsigned __int16 *)v224;
              if ( v225 == 1 )
              {
                v226 = v345;
              }
              else
              {
                v226 = *(_WORD *)&v224[2 * v225 - 2] & 0x7FFF;
                if ( v226 < v345 )
                  goto LABEL_565;
              }
              if ( (*(_WORD *)&v224[2 * v225] & 0x7FFFu) >= v226 )
              {
LABEL_566:
                WORD2(v348) = v226;
                v227 = &v223[(unsigned __int16)v226];
                v228 = *((_WORD *)v227 + 1);
                if ( (v228 & 0x4000) != 0 )
                  v229 = (v228 ^ WORD3(v348)) & 0x3800 ^ WORD3(v348);
                else
                  v229 = WORD3(v348) & 0xC7FF;
                WORD3(v348) = v229;
                WORD3(v348) = v229 ^ (*((_WORD *)v227 + 1) ^ v229) & 0x7FF;
                goto LABEL_569;
              }
LABEL_565:
              RaiseInconsistencyError(v343, 7);
              v223 = v343;
              goto LABEL_566;
            }
            v73 = (v74[1] & 1) != 0;
          }
          LODWORD(DestinationSize) = v73;
          goto LABEL_99;
        }
LABEL_303:
        v144 = *(_WORD *)(v289 + 48);
        v306 = *(_QWORD *)(v289 + 40);
        v307 = v144;
        goto LABEL_297;
      }
    }
    else if ( v143 == 8 )
    {
LABEL_302:
      if ( *(_DWORD *)(v289 + 24) != 99 )
        goto LABEL_303;
      goto LABEL_295;
    }
    if ( v143 != 9 )
      goto LABEL_303;
    goto LABEL_302;
  }
  v53 = *(_BYTE *)(a3 + 592);
  if ( (v53 & 4) != 0 )
    goto LABEL_122;
  if ( (v53 & 0x5A) != 0 )
    goto LABEL_59;
  if ( (*(_BYTE *)(a3 + 536) & 1) == 0 )
    goto LABEL_122;
  if ( !*(_QWORD *)(a3 + 208)
    && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 136LL))(a3)
    && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3) )
  {
    *(_BYTE *)(a3 + 592) |= 4u;
    goto LABEL_122;
  }
  if ( !(unsigned int)XDES::IsActive((XDES *)a3) )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 624LL))(a3);
  if ( (*(_BYTE *)(a3 + 536) & 4) != 0 )
  {
    v126 = (XDES *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 488LL))(a3);
    v127 = XDES::DoesXactGenVersion(v126);
  }
  else
  {
    if ( (*(_BYTE *)(a3 + 592) & 0x52) == 2 && XVB::IsSnapshot(*(XVB **)(a3 + 208)) )
    {
      v128 = *(_QWORD *)(a3 + 208);
      if ( !*(_BYTE *)(v128 + 304) )
      {
        *(_BYTE *)(v128 + 304) = 1;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
      }
    }
    v127 = (*(_BYTE *)(a3 + 592) & 0x5A) != 0;
  }
  if ( v127 )
  {
LABEL_59:
    if ( !v48 )
      goto LABEL_73;
    if ( v51 )
      goto LABEL_72;
    goto LABEL_61;
  }
LABEL_122:
  v89 = v289;
  v90 = v290;
  v91 = *v294;
  v92 = *v294;
  v93 = *(_BYTE *)(v289 + 1) == 1;
  v285 = 0;
  LODWORD(v284) = 1;
  v94 = v293 | 1;
  v283 = v301;
  if ( (v92 & 4) == 0 )
    v94 = v293;
  v95 = v94 | 0x4000;
  if ( (v91 & 8) == 0 )
    v95 = v94;
  v96 = v95 | 0x100;
  if ( (v91 & 0x10) == 0 )
    v96 = v95;
  v97 = v96 | 0x400000;
  if ( !v299 )
    v97 = v96;
  v98 = *(_QWORD *)(**(_QWORD **)(*((_QWORD *)v290 + 5) + 8LL) + 8LL);
  LODWORD(v295) = *(_DWORD *)(v98 + 960);
  HIDWORD(v295) = *(unsigned __int16 *)(v98 + 964);
  v99 = v97 | 0x1000000;
  if ( (v294[8] & 2) != 0 )
    v99 = v97;
  v282 = v99;
  v100 = v93 | 0x400000;
  v281 = v322;
  v280 = a3;
  v279 = (v91 >> 1) & 1;
  if ( (v91 & 1) != 0 )
    v100 = v93;
  PageRef::DeleteRows(v290, v321, &v295, a6, 1, v100, v279, v280, v281, v282, v283, (_DWORD)v284, v285);
  v101 = **(_QWORD **)v90;
  if ( (*(_DWORD *)(v101 + 24) & 0xE0000000) == 0x80000000 && *(_WORD *)(v101 + 6) <= 0xFFu )
    ++*(_DWORD *)(v101 + 68);
  result = (__int64 *)*(unsigned __int16 *)(v89 + 58);
  if ( (_WORD)result == 1 || (_WORD)result == 2 && !*(_DWORD *)(v89 + 8) && !*(_WORD *)(v89 + 12) )
  {
    result = *(__int64 **)v90;
    if ( (*(_WORD *)(*(_QWORD *)v90 + 98LL) & 4) == 0 )
    {
      LOBYTE(v9) = *(_WORD *)(*(_QWORD *)v90 + 44LL) != 2;
      ChangeGhostPageState(*(_QWORD *)v90, (unsigned int)(v9 + 2), 1);
      result = *(__int64 **)(a3 + 48);
      _InterlockedAnd((volatile signed __int32 *)(result[214] + 5440), 0xFFFFFFF7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x10048abf0  push    rbp
0x10048abf2  push    rbx
0x10048abf3  push    rsi
0x10048abf4  push    rdi
0x10048abf5  push    r12
0x10048abf7  push    r13
0x10048abf9  push    r14
0x10048abfb  push    r15
0x10048abfd  sub     rsp, 338h
0x10048ac04  lea     rbp, [rsp+80h]
0x10048ac0c  mov     rax, cs:__security_cookie
0x10048ac13  xor     rax, rbp
0x10048ac16  mov     [rbp+2F0h+var_48], rax
0x10048ac1d  mov     rax, [rbp+2F0h+arg_30]
0x10048ac24  mov     rsi, rcx
0x10048ac27  mov     r12, [rbp+2F0h+arg_20]
0x10048ac2e  xor     ebx, ebx
0x10048ac30  mov     [rbp+2F0h+var_2A8], rax
0x10048ac34  mov     rdi, r8
0x10048ac37  mov     rax, [rbp+2F0h+arg_38]
0x10048ac3e  mov     r14d, 1
0x10048ac44  mov     [rbp+2F0h+var_2E0], rcx
0x10048ac48  mov     r8d, r14d
0x10048ac4b  movzx   ecx, word ptr [rdx+18h]
0x10048ac4f  mov     [rbp+2F0h+var_2C8], rax
0x10048ac53  mov     eax, ebx
0x10048ac55  mov     eax, [rdx+14h]
0x10048ac58  shl     rcx, 20h
0x10048ac5c  or      rcx, rax
0x10048ac5f  mov     [rbp+2F0h+var_58], rbx
0x10048ac66  mov     rax, [rsi+28h]
0x10048ac6a  mov     [rbp+2F0h+var_50], ebx
0x10048ac70  mov     [rbp+2F0h+var_4C], bx
0x10048ac77  shl     rcx, 10h
0x10048ac7b  mov     [rbp+2F0h+var_220], rcx
0x10048ac82  mov     rcx, [rax+8]
0x10048ac86  mov     [rbp+2F0h+var_218], r9
0x10048ac8d  xor     r9d, r9d
0x10048ac90  mov     [rbp+2F0h+var_2C0], rdx
0x10048ac94  mov     rdx, [rsi]
0x10048ac97  mov     rax, [rcx]
0x10048ac9a  mov     [rbp+2F0h+var_2CC], 8
0x10048aca1  mov     [rbp+2F0h+var_230], rbx
0x10048aca8  mov     [rbp+2F0h+var_298], rbx
0x10048acac  mov     rcx, [rax+8]
0x10048acb0  mov     [rbp+2F0h+var_222], bx
0x10048acb7  mov     eax, [rcx+3C0h]
0x10048acbd  mov     [rbp+2F0h+var_228], eax
0x10048acc3  movzx   eax, word ptr [rcx+3C4h]
0x10048acca  mov     rcx, cs:qword_10317B628
0x10048acd1  mov     [rbp+2F0h+var_224], ax
0x10048acd8  call    ?PrepareToDirty@BPool@@QEAAPEAVPage@@PEAUBUF@@W4ChangeMode@1@_N@Z; BPool::PrepareToDirty(BUF *,BPool::ChangeMode,bool)
0x10048acdd  mov     r15, rax
0x10048ace0  mov     [rbp+2F0h+var_2E8], rax
0x10048ace4  mov     eax, 0EDFFh
0x10048ace9  mov     r13d, 2
0x10048acef  and     [r15+4], ax
0x10048acf4  mov     [r15+40h], r14d
0x10048acf8  mov     r11, [rsi]
0x10048acfb  cmp     r13w, [r11+2Ch]
0x10048ad00  jz      loc_10048AE2F
0x10048ad06  mov     rcx, [r11+90h]
0x10048ad0d  test    rcx, rcx
0x10048ad10  jz      loc_10131C68D
0x10048ad16  mov     rax, [rcx+6B0h]
0x10048ad1d  test    [rax+3Ch], r14b
0x10048ad21  jnz     loc_10131C6A5
0x10048ad27  mov     r11, [rsi]
0x10048ad2a  mov     rax, [r11+90h]
0x10048ad31  test    rax, rax
0x10048ad34  jz      loc_10131C6E0
0x10048ad3a  test    byte ptr [rax+1CD0h], 20h
0x10048ad41  jnz     loc_10048AE2F
0x10048ad47  mov     rax, [rsi]
0x10048ad4a  mov     r11, [rax]
0x10048ad4d  cmp     [r11+24h], bx
0x10048ad52  jz      short loc_10048AD71
0x10048ad54  movzx   eax, byte ptr [r11+1]
0x10048ad59  cmp     al, 0Bh
0x10048ad5b  jz      loc_10131C6F5
0x10048ad61  cmp     al, 8
0x10048ad63  jz      loc_10131C744
0x10048ad69  cmp     al, 9
0x10048ad6b  jz      loc_10131C744
0x10048ad71  movsd   xmm0, qword ptr [r11+28h]
0x10048ad77  movzx   r15d, word ptr [r11+30h]
0x10048ad7c  movsd   [rbp+2F0h+var_290], xmm0
0x10048ad81  mov     [rbp+2F0h+var_288], r15w
0x10048ad86  mov     r11, [rsi]
0x10048ad89  mov     rcx, [r11+90h]
0x10048ad90  test    rcx, rcx
0x10048ad93  jz      loc_10131C751
0x10048ad99  movzx   edx, word ptr [r11+74h]
0x10048ad9e  xor     r8d, r8d
0x10048ada1  mov     rcx, [rcx+6A0h]
0x10048ada8  call    ?GetFCB@FileMgr@@QEBAPEAVFCB@@JW4LookupFailureMode@@@Z; FileMgr::GetFCB(long,LookupFailureMode)
0x10048adad  mov     r11, [rsi]
0x10048adb0  mov     r14, rax
0x10048adb3  mov     rsi, r11
0x10048adb6  mov     rax, [r11+90h]
0x10048adbd  test    rax, rax
0x10048adc0  jz      loc_10131C766
0x10048adc6  mov     rax, [rax+7A8h]
0x10048adcd  cmp     [rax+58h], ebx
0x10048add0  jnz     loc_10049F315
0x10048add6  mov     eax, [r14+130h]
0x10048addd  cmp     eax, dword ptr [rbp+2F0h+var_290]
0x10048ade0  ja      loc_10049F315
0x10048ade6  jnz     short loc_10048ADFE
0x10048ade8  mov     eax, [r14+134h]
0x10048adef  cmp     eax, dword ptr [rbp+2F0h+var_290+4]
0x10048adf2  ja      loc_10049F315
0x10048adf8  jz      loc_10049F307
0x10048adfe  mov     rax, [r11+90h]
0x10048ae05  test    rax, rax
0x10048ae08  jz      loc_10131C7B7
0x10048ae0e  mov     rsi, [rbp+2F0h+var_2E0]
0x10048ae12  mov     rax, [rax+7A8h]
0x10048ae19  cmp     [rax+110h], ebx
0x10048ae1f  jnz     loc_10131C7D3
0x10048ae25  mov     r15, [rbp+2F0h+var_2E8]
0x10048ae29  mov     r14d, 1
0x10048ae2f  mov     rax, [rsi]
0x10048ae32  mov     r11, [rax]
0x10048ae35  mov     eax, 2000h
0x10048ae3a  test    [r11+4], ax
0x10048ae3f  jz      loc_10048AEC6
0x10048ae45  cmp     [r11+24h], bx
0x10048ae4a  jz      short loc_10048AE69
0x10048ae4c  movzx   eax, byte ptr [r11+1]
0x10048ae51  cmp     al, 0Bh
0x10048ae53  jz      loc_10131C844
0x10048ae59  cmp     al, 8
0x10048ae5b  jz      loc_10131C892
0x10048ae61  cmp     al, 9
0x10048ae63  jz      loc_10131C892
0x10048ae69  movsd   xmm0, qword ptr [r11+28h]
0x10048ae6f  movzx   esi, word ptr [r11+30h]
0x10048ae74  movsd   [rbp+2F0h+var_280], xmm0
0x10048ae79  mov     [rbp+2F0h+var_278], si
0x10048ae7d  mov     r9, [rbp+2F0h+var_2E0]
0x10048ae81  mov     r11, [r9]
0x10048ae84  mov     rax, [r11+90h]
0x10048ae8b  test    rax, rax
0x10048ae8e  jz      loc_10131C89F
0x10048ae94  mov     rax, [rax+6B0h]
0x10048ae9b  mov     rcx, [rax+2C0h]
0x10048aea2  mov     eax, dword ptr [rbp+2F0h+var_280]
0x10048aea5  cmp     [rcx+0Ah], r13w
0x10048aeaa  jz      loc_10131C8B8
0x10048aeb0  cmp     eax, [rcx]
0x10048aeb2  ja      short loc_10048AEC6
0x10048aeb4  jnz     loc_10131C8D2
0x10048aeba  mov     eax, [rcx+4]
0x10048aebd  cmp     dword ptr [rbp+2F0h+var_280+4], eax
0x10048aec0  jbe     loc_10131C8C6
0x10048aec6  mov     rax, [rdi]
0x10048aec9  mov     rcx, rdi
0x10048aecc  call    qword ptr [rax+88h]
0x10048aed2  cmp     [rbp+2F0h+var_2A8], rbx
0x10048aed6  jnz     loc_10131C8E8
0x10048aedc  mov     eax, [rdi+218h]
0x10048aee2  and     al, 5
0x10048aee4  cmp     al, 1
0x10048aee6  jnz     short loc_10048AEF5
0x10048aee8  test    [rdi+2D8h], r13b
0x10048aeef  jnz     loc_10048BE9D
0x10048aef5  mov     rax, [rdi]
0x10048aef8  mov     rcx, rdi
0x10048aefb  call    qword ptr [rax]
0x10048aefd  test    al, al
0x10048aeff  jnz     loc_10048BE9D
0x10048af05  mov     rsi, [rbp+2F0h+var_2C8]
0x10048af09  mov     r14, [rdi+0D0h]
0x10048af10  movzx   r15d, byte ptr [rsi+8]
0x10048af15  test    r15b, 1
0x10048af19  jnz     loc_10048B459
0x10048af1f  mov     rax, [rdi]
0x10048af22  mov     rcx, rdi
0x10048af25  call    qword ptr [rax]
0x10048af27  test    al, al
0x10048af29  jnz     loc_10048B459
0x10048af2f  mov     rax, [rdi]
0x10048af32  mov     rcx, rdi
0x10048af35  call    qword ptr [rax+88h]
0x10048af3b  test    al, al
0x10048af3d  jz      short loc_10048AF71
0x10048af3f  cmp     [rsi+9], bl
0x10048af42  jnz     loc_10048B459
0x10048af48  test    r14, r14
0x10048af4b  jz      loc_10131C921
0x10048af51  movzx   eax, byte ptr [rdi+250h]
0x10048af58  test    al, 4
0x10048af5a  jnz     short loc_10048AF71
0x10048af5c  test    al, 5Ah
0x10048af5e  jz      loc_10131C938
0x10048af64  test    byte ptr [rdi+250h], 40h
0x10048af6b  jnz     loc_10131CA29
0x10048af71  and     r15b, 1Ch
0x10048af75  jnz     short loc_10048AFCD
0x10048af77  mov     rsi, [rsi+10h]
0x10048af7b  test    rsi, rsi
0x10048af7e  jz      short loc_10048AFA0
0x10048af80  mov     rcx, rsi; this
0x10048af83  call    ?IsVersioned@HoBtAccess@@QEBAHXZ; HoBtAccess::IsVersioned(void)
0x10048af88  test    eax, eax
0x10048af8a  jnz     loc_10131CA38
0x10048af90  mov     rcx, rsi; this
0x10048af93  call    ?IsOibLobSourceRowset@HoBtAccess@@QEBAHXZ; HoBtAccess::IsOibLobSourceRowset(void)
0x10048af98  test    eax, eax
0x10048af9a  jnz     loc_10131CA81
0x10048afa0  mov     esi, 1
0x10048afa5  test    r14, r14
0x10048afa8  jz      short loc_10048AFB6
0x10048afaa  cmp     [r14+78h], ebx
0x10048afae  jg      short loc_10048AFDB
0x10048afb0  cmp     [r14+74h], ebx
0x10048afb4  jg      short loc_10048AFDB
0x10048afb6  movzx   eax, byte ptr [rdi+250h]
0x10048afbd  test    al, 4
0x10048afbf  jnz     loc_10048B459
0x10048afc5  test    al, 5Ah
0x10048afc7  jz      loc_10131CAD8
0x10048afcd  test    r14, r14
0x10048afd0  jz      loc_10048B05B
0x10048afd6  test    r15b, r15b
0x10048afd9  jnz     short loc_10048B051
0x10048afdb  mov     r8, [rbp+2F0h+var_2C8]
0x10048afdf  mov     rsi, [r8+10h]
0x10048afe3  test    rsi, rsi
0x10048afe6  jz      short loc_10048B008
0x10048afe8  mov     rcx, rsi; this
0x10048afeb  call    ?IsVersioned@HoBtAccess@@QEBAHXZ; HoBtAccess::IsVersioned(void)
0x10048aff0  test    eax, eax
0x10048aff2  jnz     loc_10131CBC8
0x10048aff8  mov     rcx, rsi; this
0x10048affb  call    ?IsOibLobSourceRowset@HoBtAccess@@QEBAHXZ; HoBtAccess::IsOibLobSourceRowset(void)
0x10048b000  test    eax, eax
0x10048b002  jnz     loc_10131CC11
0x10048b008  mov     esi, 1
0x10048b00d  cmp     [r14+78h], ebx
0x10048b011  jg      short loc_10048B051
0x10048b013  cmp     [r14+74h], ebx
0x10048b017  jg      short loc_10048B051
0x10048b019  movzx   eax, byte ptr [rdi+250h]
0x10048b020  test    al, 4
0x10048b022  jnz     short loc_10048B035
0x10048b024  test    al, 5Ah
0x10048b026  jz      loc_10131CC68
0x10048b02c  test    byte ptr [rdi+250h], 10h
0x10048b033  jnz     short loc_10048B05B
0x10048b035  movzx   eax, byte ptr [rdi+250h]
0x10048b03c  test    al, 4
0x10048b03e  jnz     short loc_10048B051
0x10048b040  test    al, 5Ah
0x10048b042  jz      loc_10131CD58
0x10048b048  test    byte ptr [rdi+250h], 40h
0x10048b04f  jnz     short loc_10048B05B
0x10048b051  xor     edx, edx; bool
0x10048b053  mov     rcx, r14; this
0x10048b056  call    ?Enqueue@XVB@@QEAAX_N@Z; XVB::Enqueue(bool)
0x10048b05b  mov     rcx, rdi; this
0x10048b05e  call    ?IsActive@XDES@@QEBAHXZ; XDES::IsActive(void)
0x10048b063  test    eax, eax
0x10048b065  jz      loc_10131CE48
0x10048b06b  mov     r9, [rbp+2F0h+var_2E0]
0x10048b06f  mov     r11, [r9]
0x10048b072  mov     rax, [r11+90h]
0x10048b079  test    rax, rax
0x10048b07c  jz      loc_10131CE5B
0x10048b082  mov     ecx, 387h
0x10048b087  cmp     [rax+67Eh], cx
0x10048b08e  jb      loc_10131CE74
0x10048b094  movzx   ecx, word ptr [r11+62h]
0x10048b099  not     cx
0x10048b09c  shr     cx, 8
0x10048b0a0  test    cl, 1
0x10048b0a3  jz      short loc_10048B0B2
0x10048b0a5  mov     r8, rdi; struct XDES *
0x10048b0a8  mov     dl, 1; bool
0x10048b0aa  mov     rcx, r9; this
0x10048b0ad  call    ?SetVersionState@PageRef@@QEAAX_NPEAVXDES@@@Z; PageRef::SetVersionState(bool,XDES *)
0x10048b0b2  mov     rax, [rbp+2F0h+var_2C8]
0x10048b0b6  mov     rsi, [rdi+0D0h]
0x10048b0bd  mov     r14d, [rax+18h]
0x10048b0c1  shr     r14d, 1
0x10048b0c4  and     r14d, 1
0x10048b0c8  test    byte ptr [rax+8], 24h
0x10048b0cc  mov     [rbp+2F0h+var_250], r14d
0x10048b0d3  jnz     short loc_10048B0EC
0x10048b0d5  movzx   eax, byte ptr [rdi+250h]
0x10048b0dc  test    al, 4
0x10048b0de  jnz     loc_10131CF02
0x10048b0e4  test    al, 5Ah
0x10048b0e6  jz      loc_10131CE86
0x10048b0ec  mov     eax, 1
0x10048b0f1  mov     [rbp+2F0h+var_2D0], eax
0x10048b0f4  test    r14d, r14d
0x10048b0f7  jnz     short loc_10048B101
0x10048b0f9  test    eax, eax
  ... truncated ...
```
