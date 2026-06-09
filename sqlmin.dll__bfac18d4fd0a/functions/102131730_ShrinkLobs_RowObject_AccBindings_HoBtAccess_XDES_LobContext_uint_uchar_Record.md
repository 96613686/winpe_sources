# ShrinkLobs(RowObject *,AccBindings *,HoBtAccess *,XDES *,LobContext &,uint,uchar *,Record &)

- ea: `0x102131730`
- end: `0x1021338d3`
- name: `?ShrinkLobs@@YAXPEAVRowObject@@PEAVAccBindings@@PEAVHoBtAccess@@PEAVXDES@@AEAVLobContext@@IPEAEAEAVRecord@@@Z`
- size: `8611`
- prototype: `void __fastcall(struct RowObject *, struct AccBindings *, struct HoBtAccess *, struct XDES *, struct LobContext *, rsize_t DestinationSize, unsigned __int8 *Destination, struct Record *)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1004421f0`
- `0x101462d50`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x1004025c0`
- `0x100415e90`
- `0x100427970`
- `0x10043e110`
- `0x10043e1c0`
- `0x100441e00`
- `0x10046bf90`
- `0x1004807a0`
- `0x1012c6720`
- `0x10132b810`
- `0x102130e80`
- `0x102131730`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021db830`
- `0x1021e7bb0`
- `0x1021eab40`
- `0x1021ed230`

## import_xrefs

- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021318c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102131995`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102131a69`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102131d0a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102131dd8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021320c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132198`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132265`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021324f9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021325c7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132796`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132868`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132935`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132bab`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132c6b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132ea1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132f74`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102133043`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021332bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102133381`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021318c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102131995`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102131a69`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102131d0a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102131dd8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021320c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132198`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132265`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021324f9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021325c7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132796`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132868`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132935`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132bab`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132c6b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132ea1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102132f74`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102133043`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1021332bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102133381`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213189c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213196f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102131a43`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102131ce4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102131da4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021320a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132172`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213223f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021324d3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132593`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132770`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132842`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213290f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132b85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132c45`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132e7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132f4e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213301d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102133299`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213335b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213189c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213196f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102131a43`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102131ce4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102131da4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021320a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132172`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213223f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1021324d3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132593`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132770`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132842`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213290f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132b85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132c45`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132e7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102132f4e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213301d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102133299`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10213335b`
- `sqldk!SystemThread_TlsIndex` at `0x102131846`
- `sqldk!SystemThread_TlsIndex` at `0x102131919`
- `sqldk!SystemThread_TlsIndex` at `0x1021319ed`
- `sqldk!SystemThread_TlsIndex` at `0x102131c8e`
- `sqldk!SystemThread_TlsIndex` at `0x102131d4e`
- `sqldk!SystemThread_TlsIndex` at `0x10213204a`
- `sqldk!SystemThread_TlsIndex` at `0x10213211c`
- `sqldk!SystemThread_TlsIndex` at `0x1021321e9`
- `sqldk!SystemThread_TlsIndex` at `0x10213247d`
- `sqldk!SystemThread_TlsIndex` at `0x10213253d`
- `sqldk!SystemThread_TlsIndex` at `0x10213271a`
- `sqldk!SystemThread_TlsIndex` at `0x1021327ec`
- `sqldk!SystemThread_TlsIndex` at `0x1021328b9`
- `sqldk!SystemThread_TlsIndex` at `0x102132b2f`
- `sqldk!SystemThread_TlsIndex` at `0x102132bef`
- `sqldk!SystemThread_TlsIndex` at `0x102132e25`
- `sqldk!SystemThread_TlsIndex` at `0x102132ef8`
- `sqldk!SystemThread_TlsIndex` at `0x102132fc7`
- `sqldk!SystemThread_TlsIndex` at `0x102133243`
- `sqldk!SystemThread_TlsIndex` at `0x102133305`
- `sqldk!SystemThread_TlsIndex` at `0x1021335a6`
- `sqldk!SystemThread_TlsOffset` at `0x10213184f`
- `sqldk!SystemThread_TlsOffset` at `0x102131922`
- `sqldk!SystemThread_TlsOffset` at `0x1021319f6`
- `sqldk!SystemThread_TlsOffset` at `0x102131c97`
- `sqldk!SystemThread_TlsOffset` at `0x102131d57`
- `sqldk!SystemThread_TlsOffset` at `0x102132053`
- `sqldk!SystemThread_TlsOffset` at `0x102132125`
- `sqldk!SystemThread_TlsOffset` at `0x1021321f2`
- `sqldk!SystemThread_TlsOffset` at `0x102132486`
- `sqldk!SystemThread_TlsOffset` at `0x102132546`
- `sqldk!SystemThread_TlsOffset` at `0x102132723`
- `sqldk!SystemThread_TlsOffset` at `0x1021327f5`
- `sqldk!SystemThread_TlsOffset` at `0x1021328c2`
- `sqldk!SystemThread_TlsOffset` at `0x102132b38`
- `sqldk!SystemThread_TlsOffset` at `0x102132bf8`
- `sqldk!SystemThread_TlsOffset` at `0x102132e2e`
- `sqldk!SystemThread_TlsOffset` at `0x102132f01`
- `sqldk!SystemThread_TlsOffset` at `0x102132fd0`
- `sqldk!SystemThread_TlsOffset` at `0x10213324c`
- `sqldk!SystemThread_TlsOffset` at `0x10213330e`
- `sqldk!SystemThread_TlsOffset` at `0x1021335af`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1021335ca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1021335ca`

## pseudocode

```c
void __fastcall ShrinkLobs(
        struct RowObject *a1,
        struct AccBindings *a2,
        struct HoBtAccess *a3,
        struct XDES *a4,
        struct LobContext *a5,
        rsize_t DestinationSize,
        unsigned __int8 *Destination,
        struct Record *a8)
{
  struct Record *v8; // r14
  __int64 v9; // rax
  char v10; // r13
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rsi
  __int16 v14; // cx
  unsigned int v15; // r15d
  FixedVarRecord *v16; // r15
  _BYTE *v17; // rdx
  __int64 v18; // r8
  _BYTE *v19; // rcx
  char v20; // al
  unsigned __int16 *v21; // r14
  unsigned __int16 v22; // dx
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned int v25; // r9d
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v32; // rcx
  unsigned int v33; // edi
  unsigned int v34; // r8d
  unsigned __int16 v35; // cx
  __int16 v36; // dx
  int v37; // eax
  struct RecVersioningInfo *VersioningInfo; // rax
  int v39; // r8d
  __int64 v40; // r9
  __int64 v41; // rdx
  __int16 v42; // ax
  unsigned __int64 v43; // r9
  int v44; // edx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  unsigned int v49; // edx
  char v50; // cl
  unsigned __int16 *v51; // rdx
  int v52; // ecx
  unsigned int v53; // ebx
  __int16 v54; // dx
  __int64 v55; // r8
  char *v56; // rbx
  CDRecord *v57; // rcx
  _QWORD *v58; // rax
  __int64 v59; // rax
  __int16 v60; // dx
  unsigned int v61; // r8d
  int v62; // eax
  char *v63; // r8
  __int64 v64; // rdx
  char v65; // al
  unsigned __int16 *v66; // rsi
  unsigned __int16 v67; // cx
  __int64 v68; // rax
  __int64 v69; // rax
  unsigned int v70; // r8d
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // r8
  __int64 v76; // rax
  __int64 v77; // rcx
  unsigned int v78; // edi
  unsigned int v79; // edx
  unsigned __int16 v80; // cx
  __int16 v81; // ax
  unsigned __int16 v82; // ax
  __int16 v83; // dx
  __int64 v84; // r8
  struct RecVersioningInfo *v85; // rax
  int v86; // r8d
  __int64 v87; // r9
  __int64 v88; // rdx
  __int16 v89; // ax
  unsigned __int64 v90; // r9
  int v91; // ecx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  unsigned int v96; // ecx
  char v97; // dl
  char v98; // dl
  unsigned int v99; // eax
  char *v100; // r8
  __int64 v101; // rdx
  char v102; // al
  unsigned __int16 *v103; // rsi
  unsigned __int16 v104; // cx
  __int64 v105; // rax
  __int64 v106; // rax
  unsigned int v107; // r8d
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // r8
  __int64 v113; // rax
  __int64 v114; // rcx
  unsigned int v115; // edi
  unsigned int v116; // edx
  unsigned __int16 v117; // cx
  __int16 v118; // ax
  unsigned __int16 v119; // ax
  __int16 v120; // dx
  __int64 v121; // r8
  struct RecVersioningInfo *v122; // rax
  int v123; // r8d
  __int64 v124; // r9
  __int64 v125; // rdx
  __int16 v126; // ax
  unsigned __int64 v127; // r9
  int v128; // ecx
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  char v133; // cl
  unsigned int v134; // ecx
  char v135; // dl
  unsigned int v136; // eax
  _BYTE *v137; // rcx
  __int16 v138; // cx
  char *v139; // rcx
  char v140; // al
  _BYTE *v141; // r8
  __int64 v142; // rdx
  _BYTE *v143; // rcx
  char v144; // al
  unsigned __int16 *v145; // rsi
  unsigned __int16 v146; // r8
  __int64 v147; // rax
  __int64 v148; // rax
  unsigned int v149; // r9d
  __int64 v150; // rax
  __int64 v151; // rax
  unsigned int v152; // ecx
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // r8
  __int64 v157; // rcx
  unsigned int v158; // edi
  unsigned int v159; // edx
  unsigned __int16 v160; // cx
  __int16 v161; // ax
  unsigned __int16 v162; // ax
  __int16 v163; // dx
  __int64 v164; // r8
  struct RecVersioningInfo *v165; // rax
  int v166; // r8d
  __int64 v167; // r9
  __int64 v168; // rdx
  __int16 v169; // ax
  unsigned __int64 v170; // r9
  int v171; // r8d
  __int64 v172; // rax
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  _BYTE *v176; // rdx
  unsigned int v177; // edi
  unsigned int v178; // ecx
  _WORD *v179; // r12
  unsigned int v180; // r8d
  __int64 v181; // r11
  int v182; // r10d
  int v183; // r14d
  size_t v184; // r15
  _WORD *v185; // rsi
  unsigned int i; // r9d
  __int64 v187; // r8
  unsigned __int16 v188; // di
  int j; // eax
  unsigned __int64 v190; // r8
  HoBtAccess *v191; // r12
  unsigned int v192; // r13d
  __int64 v193; // r15
  __int64 v194; // rcx
  __int64 v195; // rax
  _QWORD *v196; // rdi
  __int64 v197; // rbx
  __int64 v198; // rax
  __int64 v199; // rcx
  __int64 v200; // rcx
  unsigned int v201; // esi
  __int64 v202; // rdx
  __int64 v203; // rdi
  HoBtColumnAttributeCache *v204; // rbx
  __int64 v205; // r14
  char v206; // r12
  struct RowObject *v207; // r8
  unsigned int k; // edx
  __int64 v209; // rcx
  struct LobContext *v210; // r11
  __int64 v211; // r9
  unsigned int m; // edx
  __int64 v213; // rcx
  __int64 v214; // rcx
  double v215; // xmm0_8
  struct LobContext *v216; // rbx
  struct RowObject *v217; // rdi
  bool v218; // zf
  XDES *v219; // r14
  unsigned __int64 LockResourceId; // rax
  __int64 v221; // r9
  __int64 v222; // rcx
  __int64 v223; // rdx
  __int64 v224; // r9
  bool v225; // cf
  __int64 v226; // r8
  __int64 v227; // rcx
  __int64 v228; // rax
  __int64 v229; // rdx
  unsigned int v230; // esi
  int v231; // edx
  __int64 v232; // rcx
  unsigned __int64 v233; // rcx
  __int16 v234; // [rsp+30h] [rbp-C1h]
  int v235; // [rsp+34h] [rbp-BDh] BYREF
  struct Record *v236; // [rsp+38h] [rbp-B9h] BYREF
  HoBtAccess *v237; // [rsp+40h] [rbp-B1h]
  struct RowObject *v238; // [rsp+48h] [rbp-A9h]
  struct LobContext *v239; // [rsp+50h] [rbp-A1h]
  XDES *v240; // [rsp+58h] [rbp-99h]
  struct AccBindings *v241; // [rsp+60h] [rbp-91h]
  __int128 v242; // [rsp+68h] [rbp-89h]
  char v243; // [rsp+80h] [rbp-71h] BYREF
  __int16 v244; // [rsp+82h] [rbp-6Fh]
  __int16 v245; // [rsp+8Eh] [rbp-63h]
  int v246; // [rsp+90h] [rbp-61h]
  int v247; // [rsp+94h] [rbp-5Dh]
  __int64 v248; // [rsp+98h] [rbp-59h]
  __int64 v249; // [rsp+A0h] [rbp-51h]
  struct RowObject *v250; // [rsp+A8h] [rbp-49h]
  struct LobContext *v251; // [rsp+B0h] [rbp-41h]
  __int64 v252; // [rsp+B8h] [rbp-39h]
  char v253[16]; // [rsp+C0h] [rbp-31h] BYREF

  v8 = a8;
  v239 = a5;
  v9 = *((_QWORD *)a4 + 6);
  v240 = a4;
  v237 = a3;
  v241 = a2;
  v10 = *(_BYTE *)(v9 + 7390);
  v11 = *((_QWORD *)a3 + 1);
  v238 = a1;
  v236 = a8;
  v234 = *(_WORD *)(v11 + 200);
  v12 = (**(__int64 (__fastcall ***)(struct RowObject *))a1)(a1);
  v235 = 0x7FFF;
  v13 = v12;
  v14 = *(_WORD *)v12;
  *(_WORD *)a8 = *(_WORD *)v12;
  v15 = 9;
  if ( v14 )
  {
    if ( *(_WORD *)v12 && (v58 = *(_QWORD **)(v12 + 16)) != 0 && *v58 )
    {
      Record::DecompressRec(a8, Destination, DestinationSize, (const struct Record *)v13);
    }
    else
    {
      CDRecord::CopyNewRec(
        (struct Record *)((char *)a8 + 2),
        Destination,
        DestinationSize,
        (const struct CDRecord *)(v13 + 2));
      v59 = 0;
      if ( *(_WORD *)v13 )
        v59 = *(_QWORD *)(v13 + 16);
      *((_QWORD *)a8 + 2) = v59;
    }
    goto LABEL_104;
  }
  v16 = (struct Record *)((char *)a8 + 2);
  if ( *(_DWORD *)(v12 + 4) )
    goto LABEL_88;
  v17 = *(_BYTE **)(v12 + 8);
  v18 = *(unsigned int *)(v12 + 16);
  v19 = v17;
  *(_WORD *)(v12 + 2) = 0;
  *(_DWORD *)(v12 + 20) = v18;
  v20 = *v17;
  if ( (*v17 & 0x10) != 0 )
  {
    LODWORD(v18) = (((unsigned int)*(unsigned __int16 *)&v17[v18] + 7) >> 3) + 2 + v18;
    v19 = v17;
    *(_DWORD *)(v13 + 20) = v18;
    v20 = *v17;
  }
  if ( (v20 & 0x20) == 0 )
  {
    *(_DWORD *)(v13 + 4) = v18;
    *(_WORD *)(v13 + 28) = 0;
    *(_DWORD *)(v13 + 24) = v18;
    goto LABEL_56;
  }
  v21 = (unsigned __int16 *)&v17[(unsigned int)v18];
  v22 = *v21;
  *(_WORD *)(v13 + 28) = *v21;
  if ( !v22 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v23 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v23 )
      {
        v24 = *(_QWORD *)(v23 + 96);
        if ( v24 )
        {
          if ( *(_BYTE *)(v24 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
            else
              ex_raise(34, 68, 21, 1003);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v13 + 8), 3);
    v22 = *(_WORD *)(v13 + 28);
    LODWORD(v18) = *(_DWORD *)(v13 + 20);
  }
  v25 = v18 + 2 * (v22 + 1);
  *(_DWORD *)(v13 + 24) = v25;
  if ( v25 > 0x1F9E )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v26 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v26 )
      {
        v27 = *(_QWORD *)(v26 + 96);
        if ( v27 )
        {
          if ( *(_BYTE *)(v27 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v13 + 8), 4);
    v22 = *(_WORD *)(v13 + 28);
    v25 = *(_DWORD *)(v13 + 24);
  }
  v28 = v21[v22] & 0x7FFF;
  *(_DWORD *)(v13 + 4) = v28;
  if ( v25 > v28 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v29 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v29 )
      {
        v30 = *(_QWORD *)(v29 + 96);
        if ( v30 )
        {
          if ( *(_BYTE *)(v30 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v13 + 8), 4);
    v22 = *(_WORD *)(v13 + 28);
  }
  if ( (v21[v22] & 0x8000u) == 0 )
  {
LABEL_51:
    LODWORD(v18) = *(_DWORD *)(v13 + 4);
    v19 = *(_BYTE **)(v13 + 8);
    goto LABEL_56;
  }
  while ( 1 )
  {
    v31 = *(_QWORD *)(v13 + 8);
    v32 = v31 + *(unsigned int *)(v13 + 20);
    if ( v22 == 1 )
    {
      v33 = *(_DWORD *)(v13 + 24);
      v34 = v33;
    }
    else
    {
      v34 = *(_DWORD *)(v13 + 24);
      v33 = *(_WORD *)(v32 + 2LL * v22 - 2) & 0x7FFF;
      if ( v33 < v34 )
        goto LABEL_44;
    }
    if ( (*(_WORD *)(v32 + 2LL * v22) & 0x7FFFu) < v33 )
    {
LABEL_44:
      RaiseInconsistencyError(*(_QWORD *)(v13 + 8), 7);
      v34 = *(_DWORD *)(v13 + 24);
      v31 = *(_QWORD *)(v13 + 8);
      v22 = *(_WORD *)(v13 + 28);
    }
    if ( v33 < v34 || v33 > *(_DWORD *)(v13 + 4) )
      goto LABEL_88;
    v35 = *(_WORD *)(v31 + v33);
    if ( v35 == 5 )
      break;
    if ( v35 >= 0x400u )
    {
      *(_WORD *)(v13 + 2) |= 1u;
      *(_WORD *)(v13 + 28) = --v22;
      if ( v22 )
      {
        if ( (v21[v22] & 0x8000u) != 0 )
          continue;
      }
    }
    goto LABEL_51;
  }
  *(_WORD *)(v13 + 2) |= 2u;
  *(_WORD *)(v13 + 28) = v22 - 1;
  v36 = *(_WORD *)(v13 + 44) & 0xC7FF;
  *(_WORD *)(v13 + 42) = v33;
  v18 = *(_QWORD *)(v13 + 8) + (unsigned __int16)v33;
  if ( _bittest16((const signed __int16 *)(v18 + 2), 0xEu) )
    v36 |= *(_WORD *)(v18 + 2) & 0x3800;
  *(_WORD *)(v13 + 44) = v36;
  *(_WORD *)(v13 + 44) = v36 ^ (*(_WORD *)(v18 + 2) ^ v36) & 0x7FF;
  LODWORD(v18) = *(_DWORD *)(v13 + 4);
  v19 = *(_BYTE **)(v13 + 8);
LABEL_56:
  if ( (*v19 & 0x40) != 0 )
  {
    v37 = *(_DWORD *)(v13 + 4);
    *(_DWORD *)(v13 + 38) = v37;
    *(_DWORD *)(v13 + 4) = v37 + 14;
    VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)(v13 + 2));
    v39 = 0;
    v40 = HIDWORD(*(_QWORD *)VersioningInfo);
    v41 = HIWORD(*(_QWORD *)VersioningInfo);
    if ( (((__int16)v41 ^ ((unsigned int)(__int16)v41 >> 1)) & 0x2000) != 0 )
    {
      v42 = v41 & 0xDFFF;
      if ( (v41 & 0x4000) != 0 )
        v42 = v41 | 0x2000;
      LOWORD(v41) = v42;
    }
    if ( (_WORD)v41 == 0xFFFC )
      v39 = (unsigned __int16)v40 >> 5;
    *(_DWORD *)(v13 + 4) += v39;
    LODWORD(v18) = *(_DWORD *)(v13 + 4);
    v19 = *(_BYTE **)(v13 + 8);
  }
  else
  {
    *(_DWORD *)(v13 + 38) = 0;
  }
  v43 = *(_QWORD *)(v13 + 30);
  v44 = v18;
  if ( v43 && v43 < (unsigned __int64)&v19[(unsigned int)v18] )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v45 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v45 )
      {
        v46 = *(_QWORD *)(v45 + 96);
        if ( v46 )
        {
          if ( *(_BYTE *)(v46 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
            else
              ex_raise(34, 68, 21, 1018);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v13 + 8), 18);
    v44 = *(_DWORD *)(v13 + 4);
  }
  if ( (unsigned int)(v44 - 1) > 0x3F3B )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v47 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v47 )
      {
        v48 = *(_QWORD *)(v47 + 96);
        if ( v48 )
        {
          if ( *(_BYTE *)(v48 + 1177) )
          {
            if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
            {
              ex_raise(34, 68, 21, 1005);
              RaiseInconsistencyError(*(_QWORD *)(v13 + 8), 5);
              goto LABEL_88;
            }
            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v13 + 8), 5);
  }
LABEL_88:
  v49 = *(_DWORD *)(v13 + 4);
  if ( v49 < 9 )
  {
    v50 = **(_BYTE **)(v13 + 8) & 0xE;
    if ( !v50 || v50 == 12 )
      v49 = 9;
  }
  *((_DWORD *)a8 + 4) = *(_DWORD *)(v13 + 16);
  *(_WORD *)v16 = *(_WORD *)(v13 + 2);
  *((_DWORD *)a8 + 1) = *(_DWORD *)(v13 + 4);
  *((_WORD *)a8 + 14) = *(_WORD *)(v13 + 28);
  *((_DWORD *)a8 + 5) = *(_DWORD *)(v13 + 20);
  *((_DWORD *)a8 + 6) = *(_DWORD *)(v13 + 24);
  *(_DWORD *)((char *)a8 + 38) = *(_DWORD *)(v13 + 38);
  memcpy_s(Destination, (unsigned int)DestinationSize, *(const void *const *)(v13 + 8), v49);
  *((_QWORD *)a8 + 1) = Destination;
  if ( (unsigned int)FixedVarRecord::HasSparseVector(v16) )
  {
    v51 = (unsigned __int16 *)(*((_QWORD *)a8 + 1) + *((unsigned int *)a8 + 5));
    v52 = *v51 - 1;
    if ( (*(_BYTE *)v16 & 1) == 0 )
      v52 = *v51;
    if ( v52 == 1 )
    {
      v53 = *((_DWORD *)a8 + 6);
      goto LABEL_98;
    }
    v53 = v51[v52 - 1] & 0x7FFF;
    if ( v53 < *((_DWORD *)a8 + 6) )
    {
LABEL_99:
      RaiseInconsistencyError(*((_QWORD *)a8 + 1), 7);
    }
    else
    {
LABEL_98:
      if ( (v51[v52] & 0x7FFFu) < v53 )
        goto LABEL_99;
    }
    v54 = *((_WORD *)a8 + 22) & 0xC7FF;
    *((_WORD *)a8 + 21) = v53;
    v55 = *((_QWORD *)a8 + 1) + (unsigned __int16)v53;
    if ( _bittest16((const signed __int16 *)(v55 + 2), 0xEu) )
      v54 |= *(_WORD *)(v55 + 2) & 0x3800;
    *((_WORD *)a8 + 22) = v54;
    *((_WORD *)a8 + 22) = v54 ^ (*(_WORD *)(v55 + 2) ^ v54) & 0x7FF;
  }
  v8 = v236;
  v15 = 9;
LABEL_104:
  v56 = (char *)v8 + 2;
  v57 = (struct Record *)((char *)v8 + 2);
  if ( *(_WORD *)v8 )
    CDRecord::MakePrimaryRec(v57);
  else
    FixedVarRecord::MakePrimaryRec(v57);
  v60 = *(_WORD *)v8;
  v61 = **((unsigned __int8 **)v8 + 1);
  v62 = (v61 >> 1) & 1;
  if ( !*(_WORD *)v8 )
    v62 = (v61 >> 6) & 1;
  if ( !v62 )
    goto LABEL_335;
  if ( !v10 )
    goto LABEL_333;
  if ( v60 )
  {
    if ( (((v61 & 0x1C) - 16) & 0xFFFFFFFB) != 0 )
    {
      v96 = *((_DWORD *)v8 + 1);
      if ( !v96 )
      {
        CDRecord::Resize((struct Record *)((char *)v8 + 2));
        v96 = *((_DWORD *)v8 + 1);
        if ( !v96 )
        {
          CDRecord::Resize((struct Record *)((char *)v8 + 2));
          v96 = *((_DWORD *)v8 + 1);
        }
      }
      if ( v96 >= 9 || (v98 = **((_BYTE **)v8 + 1), (v98 & 0x1C) != 0) && (**((_BYTE **)v8 + 1) & 0x1C) != 0xC )
        v98 = **((_BYTE **)v8 + 1);
      else
        v96 = 9;
      if ( (v98 & 2) != 0 )
        v96 = *((_DWORD *)v8 + 12);
      goto LABEL_224;
    }
LABEL_227:
    if ( v60 )
    {
      v134 = *((_DWORD *)v8 + 1);
      if ( !v134 )
      {
        CDRecord::Resize((struct Record *)((char *)v8 + 2));
        v134 = *((_DWORD *)v8 + 1);
        if ( !v134 )
        {
          CDRecord::Resize((struct Record *)((char *)v8 + 2));
          v134 = *((_DWORD *)v8 + 1);
        }
      }
      if ( v134 >= 9 || (v135 = **((_BYTE **)v8 + 1), (v135 & 0x1C) != 0) && (**((_BYTE **)v8 + 1) & 0x1C) != 0xC )
      {
        v15 = v134;
        v135 = **((_BYTE **)v8 + 1);
      }
      if ( (v135 & 2) != 0 )
        v15 = *((_DWORD *)v8 + 12);
    }
    else
    {
      if ( !*((_DWORD *)v8 + 1) )
      {
        v100 = (char *)*((_QWORD *)v8 + 1);
        v101 = *((unsigned int *)v8 + 4);
        *(_WORD *)v56 = 0;
        *((_DWORD *)v8 + 5) = v101;
        v102 = *v100;
        if ( (*v100 & 0x10) != 0 )
        {
          LODWORD(v101) = (((unsigned int)*(unsigned __int16 *)&v100[v101] + 7) >> 3) + v101 + 2;
          *((_DWORD *)v8 + 5) = v101;
          v102 = *v100;
        }
        if ( (v102 & 0x20) != 0 )
        {
          v103 = (unsigned __int16 *)&v100[(unsigned int)v101];
          v104 = *v103;
          *((_WORD *)v8 + 14) = *v103;
          if ( !v104 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v105 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v105 )
              {
                v106 = *(_QWORD *)(v105 + 96);
                if ( v106 )
                {
                  if ( *(_BYTE *)(v106 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v8 + 1), 3);
            v104 = *((_WORD *)v8 + 14);
            LODWORD(v101) = *((_DWORD *)v8 + 5);
          }
          v107 = v101 + 2 * (v104 + 1);
          *((_DWORD *)v8 + 6) = v107;
          if ( v107 > 0x1F9E )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v8 + 1), 4);
            v104 = *((_WORD *)v8 + 14);
            v107 = *((_DWORD *)v8 + 6);
          }
          LODWORD(v101) = v103[v104] & 0x7FFF;
          *((_DWORD *)v8 + 1) = v101;
          if ( v107 > (unsigned int)v101 )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v8 + 1), 4);
            v104 = *((_WORD *)v8 + 14);
            LODWORD(v101) = *((_DWORD *)v8 + 1);
          }
          if ( (v103[v104] & 0x8000u) != 0 )
          {
            while ( 1 )
            {
              v112 = *((_QWORD *)v8 + 1);
              v113 = v104;
              v114 = v112 + *((unsigned int *)v8 + 5);
              if ( (_DWORD)v113 == 1 )
              {
                v115 = *((_DWORD *)v8 + 6);
                v116 = v115;
              }
              else
              {
                v116 = *((_DWORD *)v8 + 6);
                v115 = *(_WORD *)(v114 + 2 * v113 - 2) & 0x7FFF;
                if ( v115 < v116 )
                  goto LABEL_270;
              }
              if ( (*(_WORD *)(v114 + 2 * v113) & 0x7FFFu) < v115 )
              {
LABEL_270:
                RaiseInconsistencyError(*((_QWORD *)v8 + 1), 7);
                v116 = *((_DWORD *)v8 + 6);
                v112 = *((_QWORD *)v8 + 1);
              }
              if ( v115 < v116 )
                goto LABEL_315;
              LODWORD(v101) = *((_DWORD *)v8 + 1);
              if ( v115 > (unsigned int)v101 )
                goto LABEL_315;
              v117 = *(_WORD *)(v115 + v112);
              if ( v117 == 5 )
              {
                *(_WORD *)v56 |= 2u;
                --*((_WORD *)v8 + 14);
                v120 = *((_WORD *)v8 + 22) & 0xC7FF;
                *((_WORD *)v8 + 21) = v115;
                v121 = *((_QWORD *)v8 + 1) + (unsigned __int16)v115;
                if ( _bittest16((const signed __int16 *)(v121 + 2), 0xEu) )
                  v120 |= *(_WORD *)(v121 + 2) & 0x3800;
                *((_WORD *)v8 + 22) = v120;
                *((_WORD *)v8 + 22) = v120 ^ (*(_WORD *)(v121 + 2) ^ v120) & 0x7FF;
                LODWORD(v101) = *((_DWORD *)v8 + 1);
                break;
              }
              if ( v117 < 0x400u )
                break;
              v118 = *((_WORD *)v8 + 14);
              *(_WORD *)v56 |= 1u;
              v119 = v118 - 1;
              *((_WORD *)v8 + 14) = v119;
              if ( !v119 )
                break;
              v104 = v119;
              if ( (v103[v119] & 0x8000u) == 0 )
              {
                v100 = (char *)*((_QWORD *)v8 + 1);
                goto LABEL_283;
              }
            }
          }
          v100 = (char *)*((_QWORD *)v8 + 1);
        }
        else
        {
          *((_DWORD *)v8 + 1) = v101;
          *((_WORD *)v8 + 14) = 0;
          *((_DWORD *)v8 + 6) = v101;
        }
LABEL_283:
        if ( (*v100 & 0x40) != 0 )
        {
          *(_DWORD *)((char *)v8 + 38) = v101;
          *((_DWORD *)v8 + 1) = v101 + 14;
          v122 = FixedVarRecord::FindVersioningInfo((struct Record *)((char *)v8 + 2));
          v123 = 0;
          v124 = HIDWORD(*(_QWORD *)v122);
          v125 = HIWORD(*(_QWORD *)v122);
          if ( (((__int16)v125 ^ ((unsigned int)(__int16)v125 >> 1)) & 0x2000) != 0 )
          {
            v126 = v125 & 0xDFFF;
            if ( (v125 & 0x4000) != 0 )
              v126 = v125 | 0x2000;
            LOWORD(v125) = v126;
          }
          if ( (_WORD)v125 == 0xFFFC )
            v123 = (unsigned __int16)v124 >> 5;
          *((_DWORD *)v8 + 1) += v123;
          LODWORD(v101) = *((_DWORD *)v8 + 1);
          v100 = (char *)*((_QWORD *)v8 + 1);
        }
        else
        {
          *(_DWORD *)((char *)v8 + 38) = 0;
        }
        v127 = *(_QWORD *)((char *)v8 + 30);
        v128 = v101;
        if ( v127 && v127 < (unsigned __int64)&v100[(unsigned int)v101] )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v129 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v129 )
            {
              v130 = *(_QWORD *)(v129 + 96);
              if ( v130 )
              {
                if ( *(_BYTE *)(v130 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)v8 + 1), 18);
          v128 = *((_DWORD *)v8 + 1);
        }
        if ( (unsigned int)(v128 - 1) > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v131 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v131 )
            {
              v132 = *(_QWORD *)(v131 + 96);
              if ( v132 )
              {
                if ( *(_BYTE *)(v132 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)v8 + 1), 5);
        }
      }
LABEL_315:
      if ( *((_DWORD *)v8 + 1) >= 9u || (v133 = **((_BYTE **)v8 + 1), (v133 & 0xE) != 0) && (v133 & 0xE) != 0xC )
      {
        v15 = *((_DWORD *)v8 + 1);
        v133 = **((_BYTE **)v8 + 1);
      }
      if ( (v133 & 0x40) != 0 )
        v15 = *(_DWORD *)((char *)v8 + 38);
    }
    v60 = *(_WORD *)v8;
    v136 = 32;
    if ( *(_WORD *)v8 )
      v136 = 24;
    if ( v15 >= v136 )
      goto LABEL_333;
    goto LABEL_335;
  }
  if ( (v61 & 0xE) == 2 )
    goto LABEL_227;
  if ( *((_DWORD *)v8 + 1) )
    goto LABEL_206;
  v63 = (char *)*((_QWORD *)v8 + 1);
  v64 = *((unsigned int *)v8 + 4);
  *(_WORD *)v56 = 0;
  *((_DWORD *)v8 + 5) = v64;
  v65 = *v63;
  if ( (*v63 & 0x10) != 0 )
  {
    LODWORD(v64) = (((unsigned int)*(unsigned __int16 *)&v63[v64] + 7) >> 3) + v64 + 2;
    *((_DWORD *)v8 + 5) = v64;
    v65 = *v63;
  }
  if ( (v65 & 0x20) == 0 )
  {
    *((_DWORD *)v8 + 1) = v64;
    *((_WORD *)v8 + 14) = 0;
    *((_DWORD *)v8 + 6) = v64;
    goto LABEL_174;
  }
  v66 = (unsigned __int16 *)&v63[(unsigned int)v64];
  v67 = *v66;
  *((_WORD *)v8 + 14) = *v66;
  if ( !v67 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v68 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v68 )
      {
        v69 = *(_QWORD *)(v68 + 96);
        if ( v69 )
        {
          if ( *(_BYTE *)(v69 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
            else
              ex_raise(34, 68, 21, 1003);
          }
        }
      }
    }
    RaiseInconsistencyError(*((_QWORD *)v8 + 1), 3);
    v67 = *((_WORD *)v8 + 14);
    LODWORD(v64) = *((_DWORD *)v8 + 5);
  }
  v70 = v64 + 2 * (v67 + 1);
  *((_DWORD *)v8 + 6) = v70;
  if ( v70 > 0x1F9E )
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
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*((_QWORD *)v8 + 1), 4);
    v67 = *((_WORD *)v8 + 14);
    v70 = *((_DWORD *)v8 + 6);
  }
  LODWORD(v64) = v66[v67] & 0x7FFF;
  *((_DWORD *)v8 + 1) = v64;
  if ( v70 > (unsigned int)v64 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v73 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v73 )
      {
        v74 = *(_QWORD *)(v73 + 96);
        if ( v74 )
        {
          if ( *(_BYTE *)(v74 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*((_QWORD *)v8 + 1), 4);
    v67 = *((_WORD *)v8 + 14);
    LODWORD(v64) = *((_DWORD *)v8 + 1);
  }
  if ( (v66[v67] & 0x8000u) == 0 )
  {
LABEL_169:
    v63 = (char *)*((_QWORD *)v8 + 1);
    goto LABEL_174;
  }
  while ( 2 )
  {
    v75 = *((_QWORD *)v8 + 1);
    v76 = v67;
    v77 = v75 + *((unsigned int *)v8 + 5);
    if ( (_DWORD)v76 == 1 )
    {
      v78 = *((_DWORD *)v8 + 6);
      v79 = v78;
      goto LABEL_161;
    }
    v79 = *((_DWORD *)v8 + 6);
    v78 = *(_WORD *)(v77 + 2 * v76 - 2) & 0x7FFF;
    if ( v78 < v79 )
    {
LABEL_162:
      RaiseInconsistencyError(*((_QWORD *)v8 + 1), 7);
      v79 = *((_DWORD *)v8 + 6);
      v75 = *((_QWORD *)v8 + 1);
    }
    else
    {
LABEL_161:
      if ( (*(_WORD *)(v77 + 2 * v76) & 0x7FFFu) < v78 )
        goto LABEL_162;
    }
    if ( v78 < v79 )
      goto LABEL_206;
    LODWORD(v64) = *((_DWORD *)v8 + 1);
    if ( v78 > (unsigned int)v64 )
      goto LABEL_206;
    v80 = *(_WORD *)(v78 + v75);
    if ( v80 != 5 )
    {
      if ( v80 < 0x400u )
        goto LABEL_169;
      v81 = *((_WORD *)v8 + 14);
      *(_WORD *)v56 |= 1u;
      v82 = v81 - 1;
      *((_WORD *)v8 + 14) = v82;
      if ( !v82 )
        goto LABEL_169;
      v67 = v82;
      if ( (v66[v82] & 0x8000u) == 0 )
        goto LABEL_169;
      continue;
    }
    break;
  }
  *(_WORD *)v56 |= 2u;
  --*((_WORD *)v8 + 14);
  v83 = *((_WORD *)v8 + 22) & 0xC7FF;
  *((_WORD *)v8 + 21) = v78;
  v84 = *((_QWORD *)v8 + 1) + (unsigned __int16)v78;
  if ( _bittest16((const signed __int16 *)(v84 + 2), 0xEu) )
    v83 |= *(_WORD *)(v84 + 2) & 0x3800;
  *((_WORD *)v8 + 22) = v83;
  *((_WORD *)v8 + 22) = v83 ^ (*(_WORD *)(v84 + 2) ^ v83) & 0x7FF;
  LODWORD(v64) = *((_DWORD *)v8 + 1);
  v63 = (char *)*((_QWORD *)v8 + 1);
LABEL_174:
  if ( (*v63 & 0x40) != 0 )
  {
    *(_DWORD *)((char *)v8 + 38) = v64;
    *((_DWORD *)v8 + 1) = v64 + 14;
    v85 = FixedVarRecord::FindVersioningInfo((struct Record *)((char *)v8 + 2));
    v86 = 0;
    v87 = HIDWORD(*(_QWORD *)v85);
    v88 = HIWORD(*(_QWORD *)v85);
    if ( (((__int16)v88 ^ ((unsigned int)(__int16)v88 >> 1)) & 0x2000) != 0 )
    {
      v89 = v88 & 0xDFFF;
      if ( (v88 & 0x4000) != 0 )
        v89 = v88 | 0x2000;
      LOWORD(v88) = v89;
    }
    if ( (_WORD)v88 == 0xFFFC )
      v86 = (unsigned __int16)v87 >> 5;
    *((_DWORD *)v8 + 1) += v86;
    LODWORD(v64) = *((_DWORD *)v8 + 1);
    v63 = (char *)*((_QWORD *)v8 + 1);
  }
  else
  {
    *(_DWORD *)((char *)v8 + 38) = 0;
  }
  v90 = *(_QWORD *)((char *)v8 + 30);
  v91 = v64;
  if ( v90 && v90 < (unsigned __int64)&v63[(unsigned int)v64] )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v92 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v92 )
      {
        v93 = *(_QWORD *)(v92 + 96);
        if ( v93 )
        {
          if ( *(_BYTE *)(v93 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
            else
              ex_raise(34, 68, 21, 1018);
          }
        }
      }
    }
    RaiseInconsistencyError(*((_QWORD *)v8 + 1), 18);
    v91 = *((_DWORD *)v8 + 1);
  }
  if ( (unsigned int)(v91 - 1) > 0x3F3B )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v94 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v94 )
      {
        v95 = *(_QWORD *)(v94 + 96);
        if ( v95 )
        {
          if ( *(_BYTE *)(v95 + 1177) )
          {
            if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
            {
              ex_raise(34, 68, 21, 1005);
              RaiseInconsistencyError(*((_QWORD *)v8 + 1), 5);
              goto LABEL_206;
            }
            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
          }
        }
      }
    }
    RaiseInconsistencyError(*((_QWORD *)v8 + 1), 5);
  }
LABEL_206:
  v96 = *((_DWORD *)v8 + 1);
  if ( v96 >= 9 || (v97 = **((_BYTE **)v8 + 1), (v97 & 0xE) != 0) && (v97 & 0xE) != 0xC )
    v97 = **((_BYTE **)v8 + 1);
  else
    v96 = 9;
  if ( (v97 & 0x40) != 0 )
    v96 = *(_DWORD *)((char *)v8 + 38);
LABEL_224:
  v60 = *(_WORD *)v8;
  v99 = 22;
  if ( *(_WORD *)v8 )
    v99 = 16;
  if ( v96 < v99 )
    goto LABEL_227;
LABEL_333:
  if ( v60 )
  {
    v139 = (char *)*((_QWORD *)v8 + 1);
    v140 = *v139;
    if ( (*v139 & 2) != 0 )
    {
      if ( !*((_DWORD *)v8 + 1) )
      {
        CDRecord::Resize((struct Record *)((char *)v8 + 2));
        v139 = (char *)*((_QWORD *)v8 + 1);
        v140 = *v139;
      }
      *v139 = v140 & 0xFD;
      *((_DWORD *)v8 + 1) = *((_DWORD *)v8 + 12);
      *((_DWORD *)v8 + 12) = 0;
    }
  }
  else
  {
    FixedVarRecord::ClearVersioningInfo((struct Record *)((char *)v8 + 2));
  }
LABEL_335:
  (*(void (__fastcall **)(struct RowObject *))(*(_QWORD *)v238 + 8LL))(v238);
  ShrinkInRowLobs(v239, v8);
  if ( *(_WORD *)v8 )
  {
    v138 = *(_WORD *)v56;
    goto LABEL_343;
  }
  v137 = (_BYTE *)*((_QWORD *)v8 + 1);
  if ( (*v137 & 0x10) != 0 )
  {
    v138 = *(_WORD *)&v137[*((unsigned int *)v8 + 4)];
LABEL_343:
    if ( v138 && !*(_WORD *)v8 )
    {
      if ( !*((_DWORD *)v8 + 1) )
      {
        v141 = (_BYTE *)*((_QWORD *)v8 + 1);
        v142 = *((unsigned int *)v8 + 4);
        v143 = v141;
        *(_WORD *)v56 = 0;
        *((_DWORD *)v8 + 5) = v142;
        v144 = *v141;
        if ( (*v141 & 0x10) != 0 )
        {
          LODWORD(v142) = (((unsigned int)*(unsigned __int16 *)&v141[v142] + 7) >> 3) + 2 + v142;
          v143 = v141;
          *((_DWORD *)v8 + 5) = v142;
          v144 = *v141;
        }
        if ( (v144 & 0x20) != 0 )
        {
          v145 = (unsigned __int16 *)&v141[(unsigned int)v142];
          v146 = *v145;
          *((_WORD *)v8 + 14) = *v145;
          if ( !v146 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v147 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v147 )
              {
                v148 = *(_QWORD *)(v147 + 96);
                if ( v148 )
                {
                  if ( *(_BYTE *)(v148 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v8 + 1), 3);
            v146 = *((_WORD *)v8 + 14);
            LODWORD(v142) = *((_DWORD *)v8 + 5);
          }
          v149 = v142 + 2 * (v146 + 1);
          *((_DWORD *)v8 + 6) = v149;
          if ( v149 > 0x1F9E )
          {
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v8 + 1), 4);
            v146 = *((_WORD *)v8 + 14);
            v149 = *((_DWORD *)v8 + 6);
          }
          v152 = v145[v146] & 0x7FFF;
          *((_DWORD *)v8 + 1) = v152;
          if ( v149 > v152 )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*((_QWORD *)v8 + 1), 4);
            v146 = *((_WORD *)v8 + 14);
          }
          if ( (v145[v146] & 0x8000u) != 0 )
          {
            while ( 1 )
            {
              v155 = v146;
              v156 = *((_QWORD *)v8 + 1);
              v157 = v156 + *((unsigned int *)v8 + 5);
              if ( (_DWORD)v155 == 1 )
              {
                v158 = *((_DWORD *)v8 + 6);
                v159 = v158;
              }
              else
              {
                v159 = *((_DWORD *)v8 + 6);
                v158 = *(_WORD *)(v157 + 2 * v155 - 2) & 0x7FFF;
                if ( v158 < v159 )
                  goto LABEL_387;
              }
              if ( (*(_WORD *)(v157 + 2 * v155) & 0x7FFFu) < v158 )
              {
LABEL_387:
                RaiseInconsistencyError(*((_QWORD *)v8 + 1), 7);
                v159 = *((_DWORD *)v8 + 6);
                v156 = *((_QWORD *)v8 + 1);
              }
              if ( v158 < v159 || v158 > *((_DWORD *)v8 + 1) )
                goto LABEL_432;
              v160 = *(_WORD *)(v158 + v156);
              if ( v160 == 5 )
              {
                *(_WORD *)v56 |= 2u;
                --*((_WORD *)v8 + 14);
                v163 = *((_WORD *)v8 + 22) & 0xC7FF;
                *((_WORD *)v8 + 21) = v158;
                v164 = *((_QWORD *)v8 + 1) + (unsigned __int16)v158;
                if ( _bittest16((const signed __int16 *)(v164 + 2), 0xEu) )
                  v163 |= *(_WORD *)(v164 + 2) & 0x3800;
                *((_WORD *)v8 + 22) = v163;
                *((_WORD *)v8 + 22) = v163 ^ (*(_WORD *)(v164 + 2) ^ v163) & 0x7FF;
                break;
              }
              if ( v160 < 0x400u )
                break;
              v161 = *((_WORD *)v8 + 14);
              *(_WORD *)v56 |= 1u;
              v162 = v161 - 1;
              *((_WORD *)v8 + 14) = v162;
              if ( !v162 )
                break;
              v146 = v162;
              if ( (v145[v162] & 0x8000u) == 0 )
              {
                LODWORD(v142) = *((_DWORD *)v8 + 1);
                v143 = (_BYTE *)*((_QWORD *)v8 + 1);
                goto LABEL_400;
              }
            }
          }
          LODWORD(v142) = *((_DWORD *)v8 + 1);
          v143 = (_BYTE *)*((_QWORD *)v8 + 1);
        }
        else
        {
          *((_DWORD *)v8 + 1) = v142;
          *((_WORD *)v8 + 14) = 0;
          *((_DWORD *)v8 + 6) = v142;
        }
LABEL_400:
        if ( (*v143 & 0x40) != 0 )
        {
          *(_DWORD *)((char *)v8 + 38) = v142;
          *((_DWORD *)v8 + 1) = v142 + 14;
          v165 = FixedVarRecord::FindVersioningInfo((struct Record *)((char *)v8 + 2));
          v166 = 0;
          v167 = HIDWORD(*(_QWORD *)v165);
          v168 = HIWORD(*(_QWORD *)v165);
          if ( (((__int16)v168 ^ ((unsigned int)(__int16)v168 >> 1)) & 0x2000) != 0 )
          {
            v169 = v168 & 0xDFFF;
            if ( (v168 & 0x4000) != 0 )
              v169 = v168 | 0x2000;
            LOWORD(v168) = v169;
          }
          if ( (_WORD)v168 == 0xFFFC )
            v166 = (unsigned __int16)v167 >> 5;
          *((_DWORD *)v8 + 1) += v166;
          LODWORD(v142) = *((_DWORD *)v8 + 1);
          v143 = (_BYTE *)*((_QWORD *)v8 + 1);
        }
        else
        {
          *(_DWORD *)((char *)v8 + 38) = 0;
        }
        v170 = *(_QWORD *)((char *)v8 + 30);
        v171 = v142;
        if ( v170 && v170 < (unsigned __int64)&v143[(unsigned int)v142] )
        {
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)v8 + 1), 18);
          v171 = *((_DWORD *)v8 + 1);
        }
        if ( (unsigned int)(v171 - 1) > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v174 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v174 )
            {
              v175 = *(_QWORD *)(v174 + 96);
              if ( v175 )
              {
                if ( *(_BYTE *)(v175 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(*((_QWORD *)v8 + 1), 5);
        }
      }
LABEL_432:
      v176 = (_BYTE *)*((_QWORD *)v8 + 1);
      if ( (*v176 & 0x10) != 0 )
        v177 = *(unsigned __int16 *)&v176[*((unsigned int *)v8 + 4)];
      else
        v177 = 0;
      if ( v177 < v234 )
      {
        v178 = 0;
        v179 = &v176[*((unsigned int *)v8 + 4)];
        if ( (*v176 & 0x10) != 0 )
          v178 = ((v177 + 7) >> 3) + 2;
        v180 = ((unsigned int)(v234 + 7) >> 3) + 2;
        if ( v180 > v178 )
        {
          v181 = *((unsigned int *)v8 + 5);
          v182 = *((_DWORD *)v8 + 1);
          v183 = v180 - v178;
          v184 = v180 - (unsigned __int64)v178;
          v185 = &v176[v181];
          if ( (*v176 & 0x20) != 0 )
          {
            for ( i = 0;
                  i < (unsigned __int16)*v185;
                  v185[v187 + 1] ^= (unsigned __int16)v235 & (v185[v187 + 1] ^ (v185[v187 + 1] + v183)) )
            {
              v187 = i++;
            }
          }
          memmove(&v176[v181 + v184], v185, (unsigned int)(v182 - v181));
          if ( v183 > 0 )
            memset_0(v185, 0, v184);
          *(_DWORD *)(v56 + 18) += v183;
          *(_DWORD *)(v56 + 22) += v183;
          *(_DWORD *)(v56 + 2) += v183;
          if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)v56) )
            FixedVarRecord::AdjustSparseVector((FixedVarRecord *)v56);
        }
        v188 = v177 + 1;
        *v179 = v234;
        for ( j = v188; v188 <= (unsigned int)v234; j = v188 )
        {
          ++v188;
          v190 = *(int *)(v56 + 14) + ((unsigned __int64)(unsigned int)(j - 1) >> 3);
          *(_BYTE *)(v190 + *(_QWORD *)(v56 + 6) + 2) = *(_BYTE *)(*(_QWORD *)(v56 + 6) + v190 + 2)
                                                      | (1 << ((j - 1) & 7));
        }
      }
    }
  }
  v191 = v237;
  if ( (*((_DWORD *)v237 + 5) & 0xE0000000) != 0x80000000 || *((_WORD *)v237 + 12) > 0xFFu )
  {
    v192 = 0;
    if ( *((_WORD *)v241 + 49) )
    {
      v193 = *((_QWORD *)v241 + 14) + 24LL;
      do
      {
        if ( (*(_DWORD *)(v193 + 40) & 0x200000) == 0 )
        {
          v194 = *((_QWORD *)v191 + 1);
          v195 = *(_QWORD *)(v194 + 144);
          v242 = *(_OWORD *)v193;
          if ( (!v195 || !byte_1031852E4 || !*(_QWORD *)(*(_QWORD *)(v195 + 1712) + 5320LL))
            && *(_DWORD *)(v194 + 244) <= 1u )
          {
            if ( !*(_DWORD *)(v194 + 1152) )
              BaseSharedHoBt::MarkAndReserve((BaseSharedHoBt *)v194);
            v196 = (_QWORD *)v242;
            if ( !*(_QWORD *)(v242 + 8) )
              goto LABEL_467;
            v197 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            v198 = *(_QWORD *)(v197 + 256);
            if ( !v198 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v198 = *(_QWORD *)(v197 + 256);
            }
            v199 = *(_QWORD *)(v198 + 608);
            v200 = v199 ? *(unsigned int *)(v199 + 3688) : 0LL;
            if ( (unsigned int)v200 < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2) )
            {
              _mm_lfence();
              v201 = DWORD2(v242);
              v202 = *(_QWORD *)(v196[1] + 8 * v200);
              ++*(_QWORD *)(v202 + 8LL * *((_QWORD *)&v242 + 1));
            }
            else
            {
LABEL_467:
              v201 = DWORD2(v242);
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*v196 + 8LL * *((_QWORD *)&v242 + 1)), 1u);
            }
            if ( *(_BYTE *)(*((_QWORD *)v240 + 6) + 8296LL) )
            {
              v203 = *((_QWORD *)v191 + 1);
              v204 = *(HoBtColumnAttributeCache **)(v203 + 352);
              HoBtColumnAttributeCache::EnsureUnshareableAttributesAllocated(v204);
              v205 = *((_QWORD *)v204 + 1);
              v206 = 0;
              while ( 1 )
              {
                v207 = *(struct RowObject **)(*((_QWORD *)v204 + 17) + 8LL * v201);
                if ( *((_QWORD *)v204 + 18) )
                {
                  for ( k = 0;
                        k < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2);
                        v207 = (struct RowObject *)((char *)v207
                                                  + *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v204 + 18) + 8 * v209)
                                                              + 8LL * v201)) )
                  {
                    v209 = k++;
                  }
                }
                v210 = *(struct LobContext **)(v205 + 8LL * v201);
                if ( (__int64)v207 <= (__int64)v210 )
                  break;
                v211 = **(_QWORD **)(v203 + 328);
                if ( *(_QWORD *)(v203 + 336) )
                {
                  for ( m = 0;
                        m < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2);
                        v211 += **(_QWORD **)(*(_QWORD *)(v203 + 336) + 8 * v213) )
                  {
                    v213 = m++;
                  }
                }
                v214 = 25;
                v215 = (double)(int)v211 * 0.01;
                if ( (unsigned int)(int)v215 > 0x19uLL )
                  v214 = (unsigned int)(int)v215;
                if ( v210 == (struct LobContext *)_InterlockedCompareExchange64(
                                                    (volatile signed __int64 *)(v205 + 8LL * v201),
                                                    (signed __int64)v207 + v214,
                                                    (signed __int64)v210) )
                {
                  v216 = v210;
                  v238 = v207;
                  v239 = v210;
                  v206 = 1;
                  v217 = v207;
                  goto LABEL_482;
                }
              }
              v216 = v239;
              v217 = v238;
LABEL_482:
              v218 = v206 == 0;
              v191 = v237;
              if ( !v218 )
              {
                v219 = v240;
                LockResourceId = HoBtAccess::GetLockResourceId(v237);
                (*(void (__fastcall **)(XDES *, unsigned __int64))(v221 + 696))(v219, LockResourceId);
                v222 = *((_QWORD *)v191 + 1);
                v246 = 0;
                v247 = 9175040;
                v244 = 64;
                v245 = 0;
                v223 = *(_QWORD *)(v222 + 352);
                if ( v201 >= *(_DWORD *)(*(_QWORD *)v223 + 16LL) )
                {
                  v229 = 0;
                }
                else
                {
                  v224 = *(_QWORD *)(*(_QWORD *)v223 + 8LL);
                  v225 = v201 < *(_DWORD *)v224;
                  _mm_lfence();
                  if ( v225 )
                  {
                    v226 = v201 % *(_DWORD *)(v224 + 36);
                    v227 = v201 / *(_DWORD *)(v224 + 36);
                    v228 = *(_QWORD *)(v224 + 16);
                  }
                  else
                  {
                    v230 = v201 - *(_DWORD *)v224;
                    v226 = v230 % *(_DWORD *)(v224 + 68);
                    v227 = v230 / *(_DWORD *)(v224 + 68);
                    v228 = *(_QWORD *)(v224 + 48);
                  }
                  v229 = *(_QWORD *)(v228 + 8 * v227) + 448 * v226;
                }
                v231 = *(_DWORD *)(v229 + 60);
                v232 = *((unsigned __int16 *)v191 + 12);
                v252 = 0;
                v233 = *((unsigned int *)v191 + 5) | (unsigned __int64)(v232 << 32);
                LODWORD(v252) = v231;
                v248 = v233 << 16;
                v249 = 4;
                v250 = v217;
                v251 = v216;
                v235 = 64;
                v236 = (struct Record *)&v243;
                if ( !(unsigned int)XDES::IsActive(v219) )
                  (*(void (__fastcall **)(XDES *))(*(_QWORD *)v219 + 624LL))(v219);
                (*(void (__fastcall **)(XDES *, __int64, int *, struct Record **, char *))(*(_QWORD *)v219 + 648LL))(
                  v219,
                  1,
                  &v235,
                  &v236,
                  v253);
              }
            }
          }
        }
        ++v192;
        v193 += 80;
      }
      while ( v192 < *((unsigned __int16 *)v241 + 49) );
    }
  }
}

```

## disassembly

```asm
0x102131730  push    rbp
0x102131732  push    rbx
0x102131733  push    rsi
0x102131734  push    rdi
0x102131735  push    r12
0x102131737  push    r13
0x102131739  push    r14
0x10213173b  push    r15
0x10213173d  lea     rbp, [rsp-7]
0x102131742  sub     rsp, 0F8h
0x102131749  mov     rax, cs:__security_cookie
0x102131750  xor     rax, rsp
0x102131753  mov     [rbp+3Fh+var_60], rax
0x102131757  mov     rax, [rbp+3Fh+arg_20]
0x10213175b  mov     r14, [rbp+3Fh+arg_38]
0x102131762  mov     r12, [rbp+3Fh+Destination]
0x102131766  mov     [rsp+130h+var_E0], rax
0x10213176b  mov     rax, [r9+30h]
0x10213176f  mov     [rsp+130h+var_D8], r9
0x102131774  mov     [rsp+130h+var_F0], r8
0x102131779  mov     [rsp+130h+var_D0], rdx
0x10213177e  movzx   r13d, byte ptr [rax+1CDEh]
0x102131786  mov     rax, [r8+8]
0x10213178a  mov     [rsp+130h+var_E8], rcx
0x10213178f  mov     [rsp+130h+var_F8], r14
0x102131794  movzx   eax, word ptr [rax+0C8h]
0x10213179b  mov     [rsp+130h+var_100], ax
0x1021317a0  mov     rax, [rcx]
0x1021317a3  call    qword ptr [rax]
0x1021317a5  xor     edi, edi
0x1021317a7  mov     [rsp+130h+var_FC], 7FFFh
0x1021317af  mov     rsi, rax
0x1021317b2  movzx   ecx, word ptr [rax]
0x1021317b5  mov     [r14], cx
0x1021317b9  lea     r15d, [rdi+9]
0x1021317bd  test    cx, cx
0x1021317c0  jnz     loc_102131F30
0x1021317c6  lea     r15, [r14+2]
0x1021317ca  cmp     [rax+4], edi
0x1021317cd  jnz     loc_102131DF0
0x1021317d3  mov     rdx, [rax+8]
0x1021317d7  mov     r8d, [rax+10h]
0x1021317db  mov     rcx, rdx
0x1021317de  mov     [rax+2], di
0x1021317e2  mov     [rax+14h], r8d
0x1021317e6  movzx   eax, byte ptr [rdx]
0x1021317e9  test    al, 10h
0x1021317eb  jz      short loc_102131808
0x1021317ed  movzx   ecx, word ptr [rdx+r8]
0x1021317f2  add     ecx, 7
0x1021317f5  shr     ecx, 3
0x1021317f8  add     ecx, 2
0x1021317fb  add     r8d, ecx
0x1021317fe  mov     rcx, rdx
0x102131801  mov     [rsi+14h], r8d
0x102131805  movzx   eax, byte ptr [rdx]
0x102131808  test    al, 20h
0x10213180a  jz      loc_102131BBC
0x102131810  mov     r14d, r8d
0x102131813  add     r14, rdx
0x102131816  movzx   edx, word ptr [r14]
0x10213181a  mov     [rsi+1Ch], dx
0x10213181e  test    dx, dx
0x102131821  jnz     loc_1021318DE
0x102131827  cmp     cs:byte_10316E8D7, dil
0x10213182e  jnz     short loc_10213183D
0x102131830  test    byte ptr cs:qword_10317B120, 1
0x102131837  jz      loc_1021318C8
0x10213183d  mov     r8, gs:58h
0x102131846  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10213184d  mov     edx, [rax]
0x10213184f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102131856  mov     ecx, [rax]
0x102131858  mov     rax, [r8+rdx*8]
0x10213185c  mov     rax, [rax+rcx+8]
0x102131861  test    rax, rax
0x102131864  jz      short loc_1021318C8
0x102131866  mov     rax, [rax+60h]
0x10213186a  test    rax, rax
0x10213186d  jz      short loc_1021318C8
0x10213186f  cmp     [rax+499h], dil
0x102131876  jz      short loc_1021318C8
0x102131878  cmp     cs:byte_10316E7C7, dil
0x10213187f  jnz     short loc_1021318A4
0x102131881  test    byte ptr cs:qword_10317B120, 2
0x102131888  jnz     short loc_1021318A4
0x10213188a  mov     edx, 44h ; 'D'
0x10213188f  mov     r9d, 3EBh
0x102131895  lea     ecx, [rdx-22h]
0x102131898  lea     r8d, [rdx-2Fh]
0x10213189c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1021318a2  jmp     short loc_1021318C8
0x1021318a4  mov     r9d, 7DAh
0x1021318aa  mov     [rsp+130h+var_110], rdi
0x1021318af  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x1021318b6  mov     ecx, 1
0x1021318bb  lea     rdx, aFalse; "false"
0x1021318c2  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1021318c8  mov     rcx, [rsi+8]
0x1021318cc  mov     edx, 3
0x1021318d1  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x1021318d6  movzx   edx, word ptr [rsi+1Ch]
0x1021318da  mov     r8d, [rsi+14h]
0x1021318de  movzx   r9d, dx
0x1021318e2  inc     r9d
0x1021318e5  lea     r9d, [r8+r9*2]
0x1021318e9  mov     [rsi+18h], r9d
0x1021318ed  cmp     r9d, 1F9Eh
0x1021318f4  jbe     loc_1021319B1
0x1021318fa  cmp     cs:byte_10316E8D7, dil
0x102131901  jnz     short loc_102131910
0x102131903  test    byte ptr cs:qword_10317B120, 1
0x10213190a  jz      loc_10213199B
0x102131910  mov     r8, gs:58h
0x102131919  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102131920  mov     edx, [rax]
0x102131922  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102131929  mov     ecx, [rax]
0x10213192b  mov     rax, [r8+rdx*8]
0x10213192f  mov     rax, [rax+rcx+8]
0x102131934  test    rax, rax
0x102131937  jz      short loc_10213199B
0x102131939  mov     rax, [rax+60h]
0x10213193d  test    rax, rax
0x102131940  jz      short loc_10213199B
0x102131942  cmp     [rax+499h], dil
0x102131949  jz      short loc_10213199B
0x10213194b  cmp     cs:byte_10316E7C7, dil
0x102131952  jnz     short loc_102131977
0x102131954  test    byte ptr cs:qword_10317B120, 2
0x10213195b  jnz     short loc_102131977
0x10213195d  mov     edx, 44h ; 'D'
0x102131962  mov     r9d, 3ECh
0x102131968  lea     ecx, [rdx-22h]
0x10213196b  lea     r8d, [rdx-2Fh]
0x10213196f  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x102131975  jmp     short loc_10213199B
0x102131977  mov     r9d, 7E1h
0x10213197d  mov     [rsp+130h+var_110], rdi
0x102131982  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x102131989  mov     ecx, 1
0x10213198e  lea     rdx, aFalse; "false"
0x102131995  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10213199b  mov     rcx, [rsi+8]
0x10213199f  mov     edx, 4
0x1021319a4  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x1021319a9  movzx   edx, word ptr [rsi+1Ch]
0x1021319ad  mov     r9d, [rsi+18h]
0x1021319b1  movzx   eax, dx
0x1021319b4  mov     r10d, 7FFFh
0x1021319ba  movzx   ecx, word ptr [r14+rax*2]
0x1021319bf  and     ecx, r10d
0x1021319c2  mov     [rsi+4], ecx
0x1021319c5  cmp     r9d, ecx
0x1021319c8  jbe     loc_102131A87
0x1021319ce  cmp     cs:byte_10316E8D7, dil
0x1021319d5  jnz     short loc_1021319E4
0x1021319d7  test    byte ptr cs:qword_10317B120, 1
0x1021319de  jz      loc_102131A6F
0x1021319e4  mov     r8, gs:58h
0x1021319ed  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1021319f4  mov     edx, [rax]
0x1021319f6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1021319fd  mov     ecx, [rax]
0x1021319ff  mov     rax, [r8+rdx*8]
0x102131a03  mov     rax, [rax+rcx+8]
0x102131a08  test    rax, rax
0x102131a0b  jz      short loc_102131A6F
0x102131a0d  mov     rax, [rax+60h]
0x102131a11  test    rax, rax
0x102131a14  jz      short loc_102131A6F
0x102131a16  cmp     [rax+499h], dil
0x102131a1d  jz      short loc_102131A6F
0x102131a1f  cmp     cs:byte_10316E7C7, dil
0x102131a26  jnz     short loc_102131A4B
0x102131a28  test    byte ptr cs:qword_10317B120, 2
0x102131a2f  jnz     short loc_102131A4B
0x102131a31  mov     edx, 44h ; 'D'
0x102131a36  mov     r9d, 3ECh
0x102131a3c  lea     ecx, [rdx-22h]
0x102131a3f  lea     r8d, [rdx-2Fh]
0x102131a43  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x102131a49  jmp     short loc_102131A6F
0x102131a4b  mov     r9d, 7E8h
0x102131a51  mov     [rsp+130h+var_110], rdi
0x102131a56  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x102131a5d  mov     ecx, 1
0x102131a62  lea     rdx, aFalse; "false"
0x102131a69  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x102131a6f  mov     rcx, [rsi+8]
0x102131a73  mov     edx, 4
0x102131a78  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x102131a7d  movzx   edx, word ptr [rsi+1Ch]
0x102131a81  mov     r10d, 7FFFh
0x102131a87  movzx   eax, dx
0x102131a8a  dec     eax
0x102131a8c  cmp     [r14+rax*2+2], di
0x102131a92  jge     loc_102131B41
0x102131a98  nop     dword ptr [rax+rax]
0x102131a9c  nop     dword ptr [rax+00h]
0x102131aa0  mov     r9, [rsi+8]
0x102131aa4  mov     ecx, [rsi+14h]
0x102131aa7  add     rcx, r9
0x102131aaa  movzx   eax, dx
0x102131aad  cmp     eax, 1
0x102131ab0  jnz     short loc_102131ABA
0x102131ab2  mov     edi, [rsi+18h]
0x102131ab5  mov     r8d, edi
0x102131ab8  jmp     short loc_102131ACB
0x102131aba  movzx   edi, word ptr [rcx+rax*2-2]
0x102131abf  mov     r8d, [rsi+18h]
0x102131ac3  and     edi, r10d
0x102131ac6  cmp     edi, r8d
0x102131ac9  jb      short loc_102131AD6
0x102131acb  movzx   eax, word ptr [rcx+rax*2]
0x102131acf  and     eax, r10d
0x102131ad2  cmp     eax, edi
0x102131ad4  jnb     short loc_102131AF5
0x102131ad6  mov     edx, 7
0x102131adb  mov     rcx, r9
0x102131ade  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x102131ae3  mov     r8d, [rsi+18h]
0x102131ae7  mov     r10d, 7FFFh
0x102131aed  mov     r9, [rsi+8]
0x102131af1  movzx   edx, word ptr [rsi+1Ch]
0x102131af5  cmp     edi, r8d
0x102131af8  jb      loc_102131DEE
0x102131afe  cmp     edi, [rsi+4]
0x102131b01  ja      loc_102131DEE
0x102131b07  mov     eax, edi
0x102131b09  movzx   ecx, word ptr [r9+rax]
0x102131b0e  cmp     cx, 5
0x102131b12  jz      short loc_102131B51
0x102131b14  mov     eax, 400h
0x102131b19  cmp     cx, ax
0x102131b1c  jb      short loc_102131B3F
0x102131b1e  or      word ptr [rsi+2], 1
0x102131b23  sub     dx, 1
0x102131b27  mov     [rsi+1Ch], dx
0x102131b2b  jz      short loc_102131B3F
0x102131b2d  movzx   eax, dx
0x102131b30  dec     eax
0x102131b32  cmp     word ptr [r14+rax*2+2], 0
0x102131b39  jl      loc_102131AA0
0x102131b3f  xor     edi, edi
0x102131b41  mov     r8d, [rsi+4]
0x102131b45  mov     r14d, 0C7FFh
0x102131b4b  mov     rcx, [rsi+8]
0x102131b4f  jmp     short loc_102131BCE
0x102131b51  or      word ptr [rsi+2], 2
0x102131b56  dec     dx
0x102131b59  mov     [rsi+1Ch], dx
0x102131b5d  mov     ecx, 7FFh
0x102131b62  movzx   edx, word ptr [rsi+2Ch]
0x102131b66  mov     r14d, 0C7FFh
0x102131b6c  and     dx, r14w
0x102131b70  movzx   r8d, di
0x102131b74  mov     [rsi+2Ah], r8w
0x102131b79  mov     r9d, 3800h
0x102131b7f  add     r8, [rsi+8]
0x102131b83  movzx   eax, word ptr [r8+2]
0x102131b88  and     ax, r9w
0x102131b8c  or      ax, dx
0x102131b8f  bt      word ptr [r8+2], 0Eh
0x102131b96  cmovb   dx, ax
0x102131b9a  mov     [rsi+2Ch], dx
0x102131b9e  movzx   eax, dx
0x102131ba1  xor     ax, [r8+2]
0x102131ba6  and     ax, cx
0x102131ba9  xor     ax, dx
0x102131bac  mov     [rsi+2Ch], ax
0x102131bb0  xor     edi, edi
0x102131bb2  mov     r8d, [rsi+4]
0x102131bb6  mov     rcx, [rsi+8]
0x102131bba  jmp     short loc_102131BCE
0x102131bbc  mov     [rsi+4], r8d
0x102131bc0  mov     r14d, 0C7FFh
0x102131bc6  mov     [rsi+1Ch], di
0x102131bca  mov     [rsi+18h], r8d
0x102131bce  test    byte ptr [rcx], 40h
0x102131bd1  jz      short loc_102131C4D
0x102131bd3  mov     eax, [rsi+4]
0x102131bd6  lea     rcx, [rsi+2]; this
0x102131bda  mov     [rsi+26h], eax
0x102131bdd  add     eax, 0Eh
0x102131be0  mov     [rsi+4], eax
0x102131be3  call    ?FindVersioningInfo@FixedVarRecord@@AEBAPEAVRecVersioningInfo@@XZ; FixedVarRecord::FindVersioningInfo(void)
0x102131be8  mov     r10d, 2000h
0x102131bee  mov     r8d, edi
0x102131bf1  mov     r9, [rax]
0x102131bf4  mov     rdx, r9
0x102131bf7  shr     r9, 20h
0x102131bfb  shr     rdx, 30h
0x102131bff  movsx   ecx, dx
0x102131c02  mov     eax, ecx
0x102131c04  shr     eax, 1
0x102131c06  xor     eax, ecx
0x102131c08  test    r10d, eax
0x102131c0b  jz      short loc_102131C2D
0x102131c0d  movzx   ecx, dx
  ... truncated ...
```
