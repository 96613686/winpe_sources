# GlobalFileHeader::GetDbInfo(DBINFO &)

- ea: `0x101854e80`
- end: `0x101857daf`
- name: `?GetDbInfo@GlobalFileHeader@@QEAAHAEAVDBINFO@@@Z`
- size: `12079`
- prototype: `__int64 __fastcall(GlobalFileHeader *__hidden this, struct DBINFO *)`
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1016c55f0`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100403030`
- `0x10040da40`
- `0x10040da80`
- `0x10040eca0`
- `0x100415e90`
- `0x100441e00`
- `0x1004729d0`
- `0x10047ffb0`
- `0x100480030`
- `0x1005d9f70`
- `0x10069f4f0`
- `0x1012c9010`
- `0x1016c9e80`
- `0x101854e80`
- `0x1018c9d70`
- `0x101907610`
- `0x101cb13d0`
- `0x101ced0e0`
- `0x1021d8a90`
- `0x1021eab40`
- `0x1023ae3e0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x1018550bd`
- `KERNEL32!VirtualProtect` at `0x101855201`
- `KERNEL32!VirtualProtect` at `0x101855671`
- `KERNEL32!VirtualProtect` at `0x101857d23`
- `KERNEL32!VirtualProtect` at `0x1018550bd`
- `KERNEL32!VirtualProtect` at `0x101855201`
- `KERNEL32!VirtualProtect` at `0x101855671`
- `KERNEL32!VirtualProtect` at `0x101857d23`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10185598b`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x101854f4f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101855d68`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101855dfb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10185603a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018560d4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10185620d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018562ea`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018563c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10185668d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856752`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018568e9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018569c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856aa1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856d81`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856e46`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856fb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857096`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857171`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857449`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10185750e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018576a8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857785`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857860`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857b37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857bf2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101855d68`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101855dfb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10185603a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018560d4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10185620d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018562ea`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018563c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10185668d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856752`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018568e9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018569c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856aa1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856d81`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856e46`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101856fb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857096`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857171`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857449`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10185750e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018576a8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857785`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857860`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857b37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101857bf2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018561e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018562c4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185639f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856667`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185672c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018568c3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018569a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856a7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856d5b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856e20`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856f93`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101857070`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185714b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101857423`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018574e8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101857682`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185775f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185783a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101857b11`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018561e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018562c4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185639f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856667`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185672c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018568c3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018569a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856a7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856d5b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856e20`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101856f93`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101857070`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185714b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101857423`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018574e8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101857682`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185775f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10185783a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101857b11`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101854f9c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101854f9c`
- `sqldk!SystemThread_TlsIndex` at `0x101854f6d`
- `sqldk!SystemThread_TlsIndex` at `0x101854faf`
- `sqldk!SystemThread_TlsIndex` at `0x101855472`
- `sqldk!SystemThread_TlsIndex` at `0x1018554b2`
- `sqldk!SystemThread_TlsIndex` at `0x101856192`
- `sqldk!SystemThread_TlsIndex` at `0x10185626f`
- `sqldk!SystemThread_TlsIndex` at `0x10185634a`
- `sqldk!SystemThread_TlsIndex` at `0x101856612`
- `sqldk!SystemThread_TlsIndex` at `0x1018566d7`
- `sqldk!SystemThread_TlsIndex` at `0x10185686e`
- `sqldk!SystemThread_TlsIndex` at `0x10185694b`
- `sqldk!SystemThread_TlsIndex` at `0x101856a26`
- `sqldk!SystemThread_TlsIndex` at `0x101856d06`
- `sqldk!SystemThread_TlsIndex` at `0x101856dcb`
- `sqldk!SystemThread_TlsIndex` at `0x101856f3e`
- `sqldk!SystemThread_TlsIndex` at `0x10185701b`
- `sqldk!SystemThread_TlsIndex` at `0x1018570f6`
- `sqldk!SystemThread_TlsIndex` at `0x1018573ce`
- `sqldk!SystemThread_TlsIndex` at `0x101857493`
- `sqldk!SystemThread_TlsIndex` at `0x10185762d`
- `sqldk!SystemThread_TlsIndex` at `0x10185770a`
- `sqldk!SystemThread_TlsIndex` at `0x1018577e5`
- `sqldk!SystemThread_TlsIndex` at `0x101857abc`
- `sqldk!SystemThread_TlsIndex` at `0x101857b81`
- `sqldk!SystemThread_TlsOffset` at `0x101854f76`
- `sqldk!SystemThread_TlsOffset` at `0x101854fb8`
- `sqldk!SystemThread_TlsOffset` at `0x10185547b`
- `sqldk!SystemThread_TlsOffset` at `0x1018554bb`
- `sqldk!SystemThread_TlsOffset` at `0x10185619b`
- `sqldk!SystemThread_TlsOffset` at `0x101856278`
- `sqldk!SystemThread_TlsOffset` at `0x101856353`
- `sqldk!SystemThread_TlsOffset` at `0x10185661b`
- `sqldk!SystemThread_TlsOffset` at `0x1018566e0`
- `sqldk!SystemThread_TlsOffset` at `0x101856877`
- `sqldk!SystemThread_TlsOffset` at `0x101856954`
- `sqldk!SystemThread_TlsOffset` at `0x101856a2f`
- `sqldk!SystemThread_TlsOffset` at `0x101856d0f`
- `sqldk!SystemThread_TlsOffset` at `0x101856dd4`
- `sqldk!SystemThread_TlsOffset` at `0x101856f47`
- `sqldk!SystemThread_TlsOffset` at `0x101857024`
- `sqldk!SystemThread_TlsOffset` at `0x1018570ff`
- `sqldk!SystemThread_TlsOffset` at `0x1018573d7`
- `sqldk!SystemThread_TlsOffset` at `0x10185749c`
- `sqldk!SystemThread_TlsOffset` at `0x101857636`
- `sqldk!SystemThread_TlsOffset` at `0x101857713`
- `sqldk!SystemThread_TlsOffset` at `0x1018577ee`
- `sqldk!SystemThread_TlsOffset` at `0x101857ac5`
- `sqldk!SystemThread_TlsOffset` at `0x101857b8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GlobalFileHeader::GetDbInfo(GlobalFileHeader *this, struct DBINFO *a2)
{
  GlobalFileHeader *v2; // r12
  __int64 v3; // rbx
  __int64 v4; // rdx
  struct CSessionTraceFlags *v5; // rcx
  __int64 v6; // rax
  struct SEInternalTLS *SETLSFromTlsMaybeNull; // r15
  _QWORD *v8; // r14
  unsigned int v9; // esi
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rcx
  unsigned int v12; // esi
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rcx
  _QWORD *v15; // rax
  unsigned int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned int v19; // edx
  _QWORD *ThreadLocalStoragePointer; // rdx
  unsigned int v21; // r13d
  __int64 v22; // r11
  char v23; // al
  int v24; // eax
  unsigned int v25; // ecx
  _QWORD *v26; // rcx
  __int64 v27; // r11
  __int64 v28; // rdx
  unsigned int v29; // esi
  volatile signed __int32 *v30; // rdi
  __int64 v31; // rcx
  int v32; // eax
  unsigned int v33; // ecx
  LSN v34; // xmm0_8
  unsigned __int16 v35; // di
  __int64 v36; // r11
  char v37; // al
  unsigned __int16 v38; // r11
  __int64 v39; // r10
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  int *v43; // rdx
  __int64 v44; // rcx
  int v45; // ecx
  int **v46; // rax
  __int64 v47; // rsi
  unsigned int v48; // ebx
  _OWORD *v49; // rdi
  unsigned __int8 *v50; // r15
  int v51; // r14d
  char v52; // al
  __int16 v53; // r11
  unsigned __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // r12
  unsigned __int8 *v57; // r8
  unsigned __int8 v58; // dl
  __int16 v59; // dx
  __int16 v60; // cx
  unsigned __int16 v61; // ax
  unsigned int v62; // ecx
  int v63; // eax
  int v64; // eax
  int v65; // ecx
  unsigned __int8 *v66; // rax
  __int16 v67; // cx
  PageComprInfoCache *v68; // rcx
  int v69; // r14d
  unsigned __int16 *v70; // r8
  char v71; // dl
  unsigned __int16 v72; // cx
  __int16 v73; // ax
  __int16 v74; // r8
  unsigned __int16 *v75; // rsi
  unsigned __int16 v76; // dx
  __int64 v77; // rax
  __int64 v78; // rax
  unsigned int v79; // r9d
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  char *v84; // rax
  unsigned int v85; // edi
  unsigned __int16 v86; // r8
  char *v87; // rdx
  __int16 v88; // ax
  __int16 v89; // cx
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v91; // r9
  __int64 v92; // rdx
  int v93; // r8d
  __int16 v94; // ax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  char v99; // cl
  bool v100; // zf
  unsigned int v101; // eax
  void *v102; // r14
  unsigned __int16 *v103; // rsi
  unsigned __int16 v104; // dx
  __int64 v105; // rax
  __int64 v106; // rax
  unsigned int v107; // r9d
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  char *v112; // rax
  unsigned int v113; // edi
  unsigned __int16 v114; // r8
  char *v115; // rdx
  __int16 v116; // ax
  __int16 v117; // cx
  struct RecVersioningInfo *v118; // rax
  __int64 v119; // r9
  __int64 v120; // rdx
  int v121; // r8d
  __int16 v122; // ax
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rax
  char v127; // cl
  bool v128; // zf
  unsigned __int16 *v129; // rsi
  unsigned __int16 v130; // dx
  __int64 v131; // rax
  __int64 v132; // rax
  unsigned int v133; // r9d
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  char *v138; // rax
  unsigned int v139; // edi
  unsigned __int16 v140; // r8
  char *v141; // rdx
  __int16 v142; // ax
  __int16 v143; // cx
  struct RecVersioningInfo *v144; // rax
  __int64 v145; // r9
  __int64 v146; // rdx
  int v147; // r8d
  __int16 v148; // ax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rax
  char v153; // cl
  unsigned int v154; // eax
  unsigned __int16 *v155; // rsi
  unsigned __int16 v156; // dx
  __int64 v157; // rax
  __int64 v158; // rax
  unsigned int v159; // r9d
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  char *v164; // rax
  unsigned int v165; // edi
  unsigned __int16 v166; // r8
  char *v167; // rdx
  __int16 v168; // r8
  __int16 v169; // cx
  struct RecVersioningInfo *v170; // rax
  __int64 v171; // r9
  __int64 v172; // rdx
  int v173; // r8d
  __int16 v174; // ax
  __int64 v175; // rax
  __int64 v176; // rax
  __int64 v177; // rax
  __int64 v178; // rax
  rsize_t v179; // r9
  unsigned int v180; // edi
  volatile signed __int32 *v181; // rbx
  __int64 v182; // rcx
  signed __int32 v184[8]; // [rsp+0h] [rbp-100h] BYREF
  __int64 v185; // [rsp+20h] [rbp-E0h]
  _QWORD *v186; // [rsp+30h] [rbp-D0h] BYREF
  char v187; // [rsp+38h] [rbp-C8h]
  unsigned int v188; // [rsp+3Ch] [rbp-C4h]
  unsigned int v189; // [rsp+40h] [rbp-C0h]
  int v190; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v191; // [rsp+4Ch] [rbp-B4h]
  unsigned int v192; // [rsp+50h] [rbp-B0h]
  LSN v193; // [rsp+54h] [rbp-ACh]
  int v194; // [rsp+5Ch] [rbp-A4h]
  unsigned int v195; // [rsp+60h] [rbp-A0h] BYREF
  LSN v196; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v197; // [rsp+70h] [rbp-90h]
  __int64 v198; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v199; // [rsp+80h] [rbp-80h]
  unsigned __int64 v200; // [rsp+88h] [rbp-78h] BYREF
  __int16 v201; // [rsp+90h] [rbp-70h]
  unsigned int v202; // [rsp+98h] [rbp-68h] BYREF
  int v203; // [rsp+9Ch] [rbp-64h] BYREF
  int v204; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v205; // [rsp+A4h] [rbp-5Ch]
  int v206; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v207; // [rsp+ACh] [rbp-54h]
  int v208; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v209; // [rsp+B4h] [rbp-4Ch]
  int v210; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v211; // [rsp+BCh] [rbp-44h]
  __int64 v212; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v213; // [rsp+C8h] [rbp-38h]
  GlobalFileHeader *v214; // [rsp+D0h] [rbp-30h]
  void *Destination; // [rsp+D8h] [rbp-28h]
  __int64 v216; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v217; // [rsp+E8h] [rbp-18h]
  LSN v218; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v219; // [rsp+F8h] [rbp-8h]
  DWORD flOldProtect; // [rsp+100h] [rbp+0h] BYREF
  DWORD v221; // [rsp+104h] [rbp+4h] BYREF
  DWORD v222; // [rsp+108h] [rbp+8h] BYREF
  DWORD v223; // [rsp+10Ch] [rbp+Ch] BYREF
  unsigned int v224; // [rsp+110h] [rbp+10h] BYREF
  __int64 v225; // [rsp+114h] [rbp+14h]
  __int64 v226; // [rsp+128h] [rbp+28h]
  char v227[8]; // [rsp+130h] [rbp+30h] BYREF
  int v228; // [rsp+138h] [rbp+38h]
  int v229; // [rsp+140h] [rbp+40h]
  int **v230; // [rsp+148h] [rbp+48h]
  char *v231; // [rsp+150h] [rbp+50h]
  __int64 v232; // [rsp+158h] [rbp+58h]
  int *v233; // [rsp+160h] [rbp+60h] BYREF
  int v234; // [rsp+168h] [rbp+68h]
  int v235; // [rsp+16Ch] [rbp+6Ch]
  GUID *v236; // [rsp+170h] [rbp+70h]
  int v237; // [rsp+178h] [rbp+78h]
  int v238; // [rsp+17Ch] [rbp+7Ch]
  GUID *v239; // [rsp+180h] [rbp+80h]
  int v240; // [rsp+188h] [rbp+88h]
  int v241; // [rsp+18Ch] [rbp+8Ch]
  wchar_t *v242; // [rsp+190h] [rbp+90h]
  int v243; // [rsp+198h] [rbp+98h]
  int v244; // [rsp+19Ch] [rbp+9Ch]
  wchar_t *v245; // [rsp+1A0h] [rbp+A0h]
  int v246; // [rsp+1A8h] [rbp+A8h]
  int v247; // [rsp+1ACh] [rbp+ACh]
  __int64 v248; // [rsp+1B0h] [rbp+B0h]
  int v249; // [rsp+1B8h] [rbp+B8h]
  int v250; // [rsp+1BCh] [rbp+BCh]
  char v251; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v252; // [rsp+380h] [rbp+280h]
  __int64 v253; // [rsp+388h] [rbp+288h]
  int v254; // [rsp+390h] [rbp+290h] BYREF
  __int16 v255; // [rsp+394h] [rbp+294h]
  int v256; // [rsp+396h] [rbp+296h]
  char v257; // [rsp+39Ah] [rbp+29Ah]
  char v258; // [rsp+39Bh] [rbp+29Bh]
  __int16 v259; // [rsp+3D0h] [rbp+2D0h]
  unsigned __int16 v260; // [rsp+3D2h] [rbp+2D2h] BYREF
  int v261; // [rsp+3D4h] [rbp+2D4h]
  void *Source; // [rsp+3D8h] [rbp+2D8h]
  _OWORD *v263; // [rsp+3E0h] [rbp+2E0h]
  _BYTE v264[24]; // [rsp+3E8h] [rbp+2E8h]
  int v265; // [rsp+400h] [rbp+300h]
  int v266; // [rsp+404h] [rbp+304h]
  _OWORD v267[7]; // [rsp+408h] [rbp+308h] BYREF
  __int64 v268; // [rsp+478h] [rbp+378h]
  wchar_t v269[24]; // [rsp+480h] [rbp+380h] BYREF
  wchar_t v270[24]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v226 = -2;
  Destination = a2;
  v2 = this;
  v214 = this;
  v186 = 0;
  v187 = 0;
  v188 = 0;
  v259 = -1;
  Source = 0;
  v261 = 0;
  *(_QWORD *)&v264[6] = 0;
  *(_QWORD *)&v264[16] = 0;
  v263 = 0;
  v266 = -1;
  v192 = 0;
  if ( (*(_BYTE *)(*(_QWORD *)this + 124LL) & 1) == 0 )
    goto LABEL_647;
  v190 = 0;
  v191 = 2;
  v3 = *((_QWORD *)this + 1);
  v225 = 0;
  if ( !CommonGlobalState::m_CollectingStatistics
    || byte_10317ABE6 < 0
    || (v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v4)
    && (v5 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v4 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v5, 0x337u)
    || (v6 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL)) == 0 )
  {
    SETLSFromTlsMaybeNull = 0;
  }
  else
  {
    SETLSFromTlsMaybeNull = *(struct SEInternalTLS **)(v6 + 96);
  }
  v8 = *(_QWORD **)(v3 + 1832);
  while ( 1 )
  {
    v195 = 0;
    if ( !v186 )
      goto LABEL_34;
    if ( (*((_WORD *)v186 + 49) & 0x400) != 0 && (__int16)v188 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v186);
      goto LABEL_34;
    }
    v9 = (__int16)v188;
    v10 = (volatile signed __int32 *)v186;
    if ( (*((_WORD *)v186 + 49) & 8) != 0 )
    {
      if ( (__int16)v188 == 3 )
      {
        v9 = 4;
LABEL_19:
        if ( (*((_DWORD *)v186 + 25) & 8) != 0 )
        {
          v11 = v186[18];
          if ( v11 )
          {
            if ( *(_QWORD *)(v11 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v11 + 1880), v186, v9);
            }
          }
        }
        goto LABEL_23;
      }
      if ( (__int16)v188 >= 2 )
        goto LABEL_19;
    }
LABEL_23:
    if ( byte_10317ABE5 < 0
      && (v10[25] & 8) != 0
      && (int)v9 >= 3
      && (v10[25] & 0xC0000000) != 0x40000000
      && *(_QWORD *)v10
      && VirtualProtect(*(LPVOID *)v10, 0x2000u, 2u, &flOldProtect) )
    {
      _InterlockedAnd(v10 + 25, 0x3FFFFFFFu);
      _InterlockedOr(v10 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal(v10 + 38, v9);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v10, 0, v9);
    v188 &= 0xFFFF0000;
    v186 = 0;
LABEL_34:
    if ( !*(_QWORD *)(v3 + 1832) )
      goto LABEL_58;
    PageRef::CatchupPageRedos((PageRef *)&v186, (const struct PageId *)&v190, (struct RecoveryUnit *)v3);
    if ( !v186 )
      goto LABEL_58;
    if ( (*((_WORD *)v186 + 49) & 0x400) != 0 && (__int16)v188 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v186);
      goto LABEL_58;
    }
    v12 = (__int16)v188;
    v13 = (volatile signed __int32 *)v186;
    if ( (*((_WORD *)v186 + 49) & 8) != 0 )
    {
      if ( (__int16)v188 == 3 )
      {
        v12 = 4;
LABEL_43:
        if ( (*((_DWORD *)v186 + 25) & 8) != 0 )
        {
          v14 = v186[18];
          if ( v14 )
          {
            if ( *(_QWORD *)(v14 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v14 + 1880), v186, v12);
            }
          }
        }
        goto LABEL_47;
      }
      if ( (__int16)v188 >= 2 )
        goto LABEL_43;
    }
LABEL_47:
    if ( byte_10317ABE5 < 0
      && (v13[25] & 8) != 0
      && (int)v12 >= 3
      && (v13[25] & 0xC0000000) != 0x40000000
      && *(_QWORD *)v13
      && VirtualProtect(*(LPVOID *)v13, 0x2000u, 2u, &v221) )
    {
      _InterlockedAnd(v13 + 25, 0x3FFFFFFFu);
      _InterlockedOr(v13 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal(v13 + 38, v12);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v13, 0, v12);
    v188 &= 0xFFFF0000;
    v186 = 0;
LABEL_58:
    LODWORD(v185) = 2;
    v15 = (_QWORD *)BPool::Get(qword_10317B628, v3, &v190, &v195, v185, &v224);
    v186 = v15;
    v16 = v188 & 0xFFFF0000 | 2;
    v188 = v16;
    if ( SETLSFromTlsMaybeNull )
    {
      v17 = *v15;
      v18 = *((_DWORD *)SETLSFromTlsMaybeNull + 320) & 0xF;
      if ( *((_QWORD *)SETLSFromTlsMaybeNull + v18 + 161) != v17 )
      {
        *((_QWORD *)SETLSFromTlsMaybeNull + v18 + 161) = v17;
        ++*((_QWORD *)SETLSFromTlsMaybeNull + 160);
        v16 = v188;
      }
    }
    v19 = v16 & 0xFFFFFF | (((v195 >> 3) & 1) << 24);
    v188 = v19;
    v189 = v189 & 0xFFFFFF00 | (v195 >> 4) & 1;
    if ( v8 )
    {
      if ( SETLSFromTlsMaybeNull )
      {
        if ( SETLSFromTlsMaybeNull == *(struct SEInternalTLS **)(v3 + 7224) )
        {
          ++v8[2917];
          if ( (_DWORD)v225 )
          {
            ++v8[2918];
            v8[2919] += v224;
            if ( v19 >= 0x1000000 )
            {
              ++v8[2920];
              v8[2921] += v224;
            }
          }
        }
      }
    }
    v21 = 9;
    if ( !RecoveryUnit::IsRbIoDb((RecoveryUnit *)v3) || !*(_BYTE *)(v3 + 8272) || !v190 || v190 == 9 && v191 == 1 )
      goto LABEL_159;
    v22 = *v186;
    if ( !*(_WORD *)(*v186 + 36LL) )
    {
LABEL_81:
      v198 = *(_QWORD *)(v22 + 40);
      v199 = *(_WORD *)(v22 + 48);
      goto LABEL_82;
    }
    v23 = *(_BYTE *)(v22 + 1);
    if ( v23 == 11 )
    {
      if ( *(_DWORD *)(v22 + 24) == 99 )
        goto LABEL_79;
    }
    else if ( v23 == 8 )
    {
      goto LABEL_78;
    }
    if ( v23 != 9 )
      goto LABEL_81;
LABEL_78:
    if ( *(_DWORD *)(v22 + 24) != 99 )
      goto LABEL_81;
LABEL_79:
    v204 = *(_DWORD *)(v22 + 32);
    v205 = *(_WORD *)(v22 + 36);
    if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v204, ThreadLocalStoragePointer) )
      goto LABEL_81;
    PageHeader::GetIcxLsn(v22, &v198);
LABEL_82:
    v24 = *(_DWORD *)(v3 + 8456);
    do
    {
      v25 = v24 & 0xFFFFFFFE;
      v193 = *(LSN *)(v3 + 8444);
      v194 = *(_DWORD *)(v3 + 8452);
      _InterlockedOr(v184, 0);
      v24 = *(_DWORD *)(v3 + 8456);
    }
    while ( v25 != v24 );
    if ( v193.LowPart >= (unsigned int)v198
      && (v193.LowPart != (_DWORD)v198
       || v193.HighPart >= HIDWORD(v198) && (v193.HighPart != HIDWORD(v198) || (unsigned __int16)v194 >= v199)) )
    {
      goto LABEL_159;
    }
    if ( !*(_BYTE *)(v3 + 27336)
      && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL)
                   + 96LL) != *(_QWORD *)(v3 + 8480)
      && !RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v3) )
    {
      break;
    }
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    if ( *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset + 8LL) + 96LL) == *(_QWORD *)(v3 + 8480)
      || RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v3) )
    {
      goto LABEL_159;
    }
    if ( !SETLSFromTlsMaybeNull )
      SETLSFromTlsMaybeNull = GetSETLSFromTlsMaybeNull();
    v26 = v186;
    v27 = *v186;
    if ( !*(_WORD *)(*v186 + 36LL) )
      goto LABEL_106;
    v28 = *(unsigned __int8 *)(v27 + 1);
    if ( (_BYTE)v28 != 11 )
    {
      if ( (_BYTE)v28 != 8 )
      {
LABEL_101:
        if ( (_BYTE)v28 != 9 )
          goto LABEL_106;
      }
      if ( *(_DWORD *)(v27 + 24) != 99 )
        goto LABEL_106;
      goto LABEL_103;
    }
    if ( *(_DWORD *)(v27 + 24) != 99 )
      goto LABEL_101;
LABEL_103:
    v206 = *(_DWORD *)(v27 + 32);
    v207 = *(_WORD *)(v27 + 36);
    if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v206, v28) )
    {
      PageHeader::GetIcxLsn(v27, &v212);
      v26 = v186;
      goto LABEL_107;
    }
    v26 = v186;
LABEL_106:
    v212 = *(_QWORD *)(v27 + 40);
    v213 = *(_WORD *)(v27 + 48);
LABEL_107:
    if ( !v26 )
      goto LABEL_111;
    if ( (*((_WORD *)v26 + 49) & 0x400) != 0 && (__int16)v188 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v186);
      goto LABEL_111;
    }
    v29 = (__int16)v188;
    v30 = (volatile signed __int32 *)v186;
    if ( (*((_WORD *)v26 + 49) & 8) != 0 )
    {
      if ( (__int16)v188 == 3 )
      {
        v29 = 4;
LABEL_116:
        if ( (*((_DWORD *)v186 + 25) & 8) != 0 )
        {
          v31 = v186[18];
          if ( v31 )
          {
            if ( *(_QWORD *)(v31 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v31 + 1880), v186, v29);
            }
          }
        }
        goto LABEL_120;
      }
      if ( (__int16)v188 >= 2 )
        goto LABEL_116;
    }
LABEL_120:
    if ( byte_10317ABE5 < 0
      && (v30[25] & 8) != 0
      && (int)v29 >= 3
      && (v30[25] & 0xC0000000) != 0x40000000
      && *(_QWORD *)v30
      && VirtualProtect(*(LPVOID *)v30, 0x2000u, 2u, &v222) )
    {
      _InterlockedAnd(v30 + 25, 0x3FFFFFFFu);
      _InterlockedOr(v30 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal(v30 + 38, v29);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
    {
      if ( (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v30, 0, v29);
    }
    v188 &= 0xFFFF0000;
    v186 = 0;
LABEL_111:
    v216 = v212;
    v217 = v213;
    v185 = 0;
    RecoveryMgr::WaitForRedoLsnToCatchUp(*(_QWORD *)(v3 + 1832), &v216, 4);
  }
  v32 = *(_DWORD *)(v3 + 8456);
  do
  {
    v33 = v32 & 0xFFFFFFFE;
    v34 = *(LSN *)(v3 + 8444);
    v193 = v34;
    v194 = *(_DWORD *)(v3 + 8452);
    _InterlockedOr(v184, 0);
    v32 = *(_DWORD *)(v3 + 8456);
  }
  while ( v33 != v32 );
  v218 = v34;
  v35 = v194;
  v219 = v194;
  v36 = *v186;
  if ( !*(_WORD *)(*v186 + 36LL) )
    goto LABEL_142;
  v37 = *(_BYTE *)(v36 + 1);
  if ( v37 != 11 )
  {
    if ( v37 == 8 )
      goto LABEL_139;
    goto LABEL_138;
  }
  if ( *(_DWORD *)(v36 + 24) != 99 )
  {
LABEL_138:
    if ( v37 != 9 )
      goto LABEL_142;
LABEL_139:
    if ( *(_DWORD *)(v36 + 24) == 99 )
      goto LABEL_140;
    goto LABEL_142;
  }
LABEL_140:
  v208 = *(_DWORD *)(v36 + 32);
  v209 = *(_WORD *)(v36 + 36);
  if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v208, ThreadLocalStoragePointer) )
  {
    PageHeader::GetIcxLsn(v36, &v196);
    v38 = v197;
    goto LABEL_143;
  }
LABEL_142:
  v196 = *(LSN *)(v36 + 40);
  v38 = *(_WORD *)(v36 + 48);
  v197 = v38;
LABEL_143:
  if ( v193.LowPart < v196.LowPart
    || v193.LowPart == v196.LowPart
    && (v193.HighPart < (unsigned int)v196.HighPart || v193.HighPart == v196.HighPart && v35 < v38) )
  {
    LSN::FormatAsHexString(&v196, v269, &v202);
    LSN::FormatAsHexString(&v218, v270, &v202);
    if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
    {
      v228 = 393216;
      v229 = 0;
      v230 = &v233;
      v231 = &v251;
      v252 = 0;
      v232 = 0;
      v253 = 0;
      v233 = &v254;
      v234 = 52;
      v235 = 5;
      v236 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
      v237 = 16;
      v238 = 5;
      v239 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
      v240 = 16;
      v241 = 6;
      v242 = 0;
      v243 = 0;
      v244 = 7;
      v245 = 0;
      v246 = 0;
      v247 = 8;
      v248 = 0;
      v249 = 0;
      v250 = 9;
      v254 = *(unsigned __int16 *)(v3 + 1720);
      v255 = v191;
      v256 = v190;
      v257 = -1;
      v258 = *(_BYTE *)(*v186 + 1LL);
      v236 = (GUID *)(v39 + 596);
      v239 = (GUID *)(v39 + 580);
      v40 = -1;
      do
        ++v40;
      while ( v269[v40] );
      v242 = v269;
      v243 = 2 * v40;
      v41 = -1;
      do
        ++v41;
      while ( v270[v41] );
      v245 = v270;
      v246 = 2 * v41;
      v203 = 0;
      v42 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v39, &v203);
      v43 = (int *)v42;
      if ( v42 )
      {
        v44 = -1;
        do
          ++v44;
        while ( *(_WORD *)(v42 + 2 * v44) );
        v45 = 2 * v44;
      }
      else
      {
        v45 = 0;
      }
      v46 = v230;
      v230[10] = v43;
      *((_DWORD *)v46 + 22) = v45;
      *((_DWORD *)v46 + 23) = 9;
      XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v227);
    }
  }
LABEL_159:
  v47 = *v186;
  if ( *(_WORD *)(*v186 + 22LL) <= 1u || !*(_WORD *)(v47 + 8188) )
    goto LABEL_624;
  v266 = 1;
  v48 = 15;
  if ( *(char *)(v47 + 2) >= 0 )
  {
    v49 = 0;
    goto LABEL_211;
  }
  v50 = (unsigned __int8 *)(v47 + 96);
  _mm_prefetch((const char *)(v47 + 96), 0);
  if ( v259 && (v49 = v263) != 0 )
  {
    v51 = 0;
  }
  else
  {
    v268 = 0;
    v267[0] = 0;
    v267[1] = 0xFFFFu;
    v51 = 0;
    memset(&v267[2], 0, 80);
    v49 = v267;
  }
  if ( !*(_WORD *)(v47 + 36) )
    goto LABEL_176;
  v52 = *(_BYTE *)(v47 + 1);
  if ( v52 != 11 )
  {
    if ( v52 == 8 )
      goto LABEL_173;
LABEL_172:
    if ( v52 == 9 )
    {
LABEL_173:
      if ( *(_DWORD *)(v47 + 24) == 99 )
        goto LABEL_174;
    }
LABEL_176:
    v200 = *(_QWORD *)(v47 + 40);
    v53 = *(_WORD *)(v47 + 48);
    v201 = v53;
    goto LABEL_177;
  }
  if ( *(_DWORD *)(v47 + 24) != 99 )
    goto LABEL_172;
LABEL_174:
  v210 = *(_DWORD *)(v47 + 32);
  v211 = *(_WORD *)(v47 + 36);
  if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v210, ThreadLocalStoragePointer) )
    goto LABEL_176;
  PageHeader::GetIcxLsn(v47, &v200);
  v53 = v201;
LABEL_177:
  *(_QWORD *)v49 = v50;
  v54 = HIDWORD(v200);
  *((_DWORD *)v49 + 24) = v200;
  *((_DWORD *)v49 + 25) = v54;
  *((_WORD *)v49 + 52) = v53;
  *((_DWORD *)v49 + 27) = *(_DWORD *)(v47 + 32);
  *((_WORD *)v49 + 56) = *(_WORD *)(v47 + 36);
  *((_WORD *)v49 + 57) = 0;
  v55 = 3LL * *v50;
  v193.LowPart = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v50);
  v56 = word_102883984[v55];
  *((_WORD *)v49 + 8) = -1;
  *((_QWORD *)v49 + 3) = 0;
  *((_DWORD *)v49 + 5) = 0;
  *(_QWORD *)((char *)v49 + 46) = 0;
  *((_QWORD *)v49 + 7) = 0;
  *((_QWORD *)v49 + 4) = 0;
  *((_QWORD *)v49 + 9) = 0;
  *((_QWORD *)v49 + 10) = 0;
  *((_WORD *)v49 + 44) = 0;
  if ( (**(_BYTE **)v49 & 2) != 0 )
  {
    v57 = &v50[v56];
    if ( (v50[v56] & 1) != 0 )
    {
      *((_WORD *)v49 + 8) = 1;
      *((_QWORD *)v49 + 3) = v57;
      v58 = *v57;
      switch ( *v57 & 0x1C )
      {
        case 0:
        case 0xC:
        case 0x10:
        case 0x14:
        case 0x18:
        case 0x1C:
          if ( (v57[1] & 0x80u) != 0 )
          {
            v61 = *(_WORD *)(v57 + 1);
            *((_WORD *)v49 + 9) = v61;
            v59 = 3;
            v60 = HIBYTE(v61) | ((v61 & 0x7F) << 8);
          }
          else
          {
            v59 = 2;
            v60 = v57[1];
          }
          *((_WORD *)v49 + 9) = v60;
          *((_WORD *)v49 + 20) = v59;
          v62 = *((unsigned __int16 *)v49 + 9);
          *((_WORD *)v49 + 22) = v59 + ((v62 + 1) >> 1);
          if ( v62 > 0x1E )
            *((_WORD *)v49 + 21) = (int)(v62 - 1) / 30;
          else
            *((_WORD *)v49 + 21) = 0;
          *((_DWORD *)v49 + 5) = 0;
          *((_DWORD *)v49 + 16) = 0;
          *((_QWORD *)v49 + 7) = 0;
          *((_QWORD *)v49 + 4) = 0;
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
          *((_QWORD *)v49 + 7) = 0;
          *((_QWORD *)v49 + 4) = 0;
          break;
        case 4:
          if ( (v58 & 0x1C) != 4 || (v63 = 1, (v58 & 2) == 0) )
            v63 = 0;
          if ( v63 )
          {
            *((_DWORD *)v49 + 16) = 0;
            v64 = 1;
            v65 = 15;
          }
          else
          {
            v64 = 0;
            v65 = 1;
          }
          *((_QWORD *)v49 + 5) = 0;
          *((_WORD *)v49 + 9) = 0;
          *((_QWORD *)v49 + 6) = 0;
          *((_QWORD *)v49 + 4) = 0;
          *((_QWORD *)v49 + 7) = 0;
          *((_QWORD *)v49 + 3) = v57;
          *((_DWORD *)v49 + 5) = v65;
          *((_DWORD *)v49 + 16) = v64;
          *((_QWORD *)v49 + 7) = 0;
          *((_QWORD *)v49 + 4) = 0;
          break;
        case 8:
          *((_QWORD *)v49 + 5) = 0;
          *((_WORD *)v49 + 9) = 0;
          *((_QWORD *)v49 + 6) = 0;
          *((_QWORD *)v49 + 4) = 0;
          *((_QWORD *)v49 + 7) = 0;
          *((_QWORD *)v49 + 3) = v57;
          *((_DWORD *)v49 + 5) = 9;
          *((_DWORD *)v49 + 16) = 0;
          *((_QWORD *)v49 + 7) = 0;
          *((_QWORD *)v49 + 4) = 0;
          break;
      }
    }
    else
    {
      *((_WORD *)v49 + 8) = 0;
      *((_QWORD *)v49 + 3) = v57;
      *((_DWORD *)v49 + 5) = 0;
      *(_DWORD *)((char *)v49 + 54) = 0;
      switch ( *v57 & 0xE )
      {
        case 0:
        case 2:
        case 8:
        case 0xC:
          v51 = *((unsigned __int16 *)v57 + 1);
          if ( (unsigned int)(v51 - 1) > 0x1F9D )
            RaiseInconsistencyError(&v50[v56], 6);
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
          v51 = 9;
          break;
        case 6:
        case 0xA:
          break;
        case 0xE:
          v51 = 1;
          break;
      }
      *((_DWORD *)v49 + 8) = v51;
      *(_QWORD *)((char *)v49 + 46) = 0;
    }
  }
  if ( (**(_BYTE **)v49 & 4) != 0 )
  {
    if ( HIWORD(v193.u.LowPart) )
      v66 = &v50[*(unsigned __int16 *)&v50[2 * SHIWORD(v193.u.LowPart) + 1]];
    else
      v66 = &v50[v56];
    *((_QWORD *)v49 + 9) = v66;
    v67 = *(_WORD *)v66;
    *((_QWORD *)v49 + 10) = v66 + 2;
    *((_WORD *)v49 + 44) = 2 * (v67 + 1);
  }
  v68 = (PageComprInfoCache *)*((_QWORD *)v49 + 1);
  if ( v68 )
    PageComprInfoCache::Init(v68, (const struct PageComprInfo *)v49);
  v2 = v214;
LABEL_211:
  v69 = *(unsigned __int16 *)(v47 + 14);
  v70 = (unsigned __int16 *)(v47 + *(unsigned __int16 *)(v47 + 8188));
  v100 = (*(_BYTE *)v70 & 1) == 0;
  Source = v70;
  if ( v100 )
  {
    v259 = 0;
    v48 = 0;
    v261 = 0;
    *(_DWORD *)&v264[14] = 0;
    switch ( *(_BYTE *)v70 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v69 = v70[1];
        if ( (unsigned int)(v69 - 1) > 0x1F9D )
        {
          RaiseInconsistencyError(v70, 6);
          goto LABEL_233;
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
LABEL_233:
        v48 = v261;
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
    LODWORD(v263) = v69;
    *(_QWORD *)&v264[6] = v47 + 0x2000;
    LODWORD(v49) = v69;
  }
  else
  {
    v259 = 1;
    v71 = *(_BYTE *)v70;
    switch ( *(_BYTE *)v70 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( *((char *)v70 + 1) < 0 )
        {
          v72 = HIBYTE(*(unsigned __int16 *)((char *)v70 + 1)) | ((*(unsigned __int16 *)((char *)v70 + 1) & 0x7F) << 8);
          v260 = v72;
          v73 = 3;
          v74 = 3;
        }
        else
        {
          v72 = *((unsigned __int8 *)v70 + 1);
          v260 = v72;
          v73 = 2;
          v74 = 2;
        }
        *(_WORD *)v264 = v73;
        *(_WORD *)&v264[4] = v74 + (((unsigned int)v72 + 1) >> 1);
        if ( v72 > 0x1Eu )
          *(_WORD *)&v264[2] = (v72 - 1) / 30;
        else
          *(_WORD *)&v264[2] = 0;
        v48 = 0;
        v261 = 0;
        v265 = 0;
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
        v48 = v261;
        break;
      case 4:
        if ( (v71 & 0x1C) == 4 && (v71 & 2) != 0 )
        {
          *(_QWORD *)v264 = 0;
          v260 = 0;
          *(_QWORD *)&v264[8] = 0;
          v261 = 15;
          v265 = 1;
        }
        else
        {
          *(_QWORD *)v264 = 0;
          v260 = 0;
          *(_QWORD *)&v264[8] = 0;
          v48 = 1;
          v261 = 1;
          v265 = 0;
        }
        break;
      case 8:
        *(_QWORD *)v264 = 0;
        v260 = 0;
        *(_QWORD *)&v264[8] = 0;
        v48 = 9;
        v261 = 9;
        v265 = 0;
        break;
    }
    *(_QWORD *)&v264[16] = v47 + 0x2000;
    v263 = v49;
  }
  if ( v259 )
  {
    if ( !v48 )
    {
      CDRecord::Resize((CDRecord *)&v260);
      v48 = v261;
    }
    if ( v48 >= 9 )
      goto LABEL_333;
    if ( (*(_BYTE *)Source & 0x1C) != 0 )
    {
      v100 = (*(_BYTE *)Source & 0x1C) == 12;
LABEL_331:
      if ( !v100 )
        goto LABEL_333;
    }
LABEL_332:
    v101 = 9;
  }
  else
  {
    if ( !v48 )
    {
      v260 = 0;
      HIDWORD(v263) = (_DWORD)v49;
      v48 = (unsigned int)v49;
      if ( (*(_BYTE *)Source & 0x10) != 0 )
      {
        v48 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v49) + 7) >> 3) + (_DWORD)v49 + 2;
        HIDWORD(v263) = v48;
      }
      if ( (*(_BYTE *)Source & 0x20) != 0 )
      {
        v75 = (unsigned __int16 *)((char *)Source + v48);
        v76 = *v75;
        *(_WORD *)&v264[4] = v76;
        if ( !v76 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v77 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v77 )
            {
              v78 = *(_QWORD *)(v77 + 96);
              if ( v78 )
              {
                if ( *(_BYTE *)(v78 + 1177) )
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
          v76 = *(_WORD *)&v264[4];
        }
        v79 = HIDWORD(v263) + 2 + 2 * v76;
        *(_DWORD *)v264 = v79;
        if ( v79 > 0x1F9E )
        {
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
          }
          RaiseInconsistencyError(Source, 4);
          v76 = *(_WORD *)&v264[4];
          v79 = *(_DWORD *)v264;
        }
        v48 = v75[v76] & 0x7FFF;
        v261 = v48;
        if ( v79 > v48 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v82 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v82 )
            {
              v83 = *(_QWORD *)(v82 + 96);
              if ( v83 )
              {
                if ( *(_BYTE *)(v83 + 1177) )
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
          v76 = *(_WORD *)&v264[4];
          v79 = *(_DWORD *)v264;
          v48 = v261;
        }
        while ( (v75[v76] & 0x8000u) != 0 )
        {
          v84 = (char *)Source + HIDWORD(v263);
          if ( v76 == 1 )
            v85 = v79;
          else
            v85 = *(_WORD *)&v84[2 * v76 - 2] & 0x7FFF;
          if ( v85 < v79 || (*(_WORD *)&v84[2 * v76] & 0x7FFFu) < v85 )
          {
            RaiseInconsistencyError(Source, 7);
            v76 = *(_WORD *)&v264[4];
            v79 = *(_DWORD *)v264;
            v48 = v261;
          }
          if ( v85 < v79 || v85 > v48 )
            goto LABEL_323;
          v86 = *(_WORD *)((char *)Source + v85);
          if ( v86 == 5 )
          {
            v260 |= 2u;
            *(_WORD *)&v264[4] = v76 - 1;
            *(_WORD *)&v264[18] = v85;
            v87 = (char *)Source + (unsigned __int16)v85;
            v88 = *((_WORD *)v87 + 1);
            if ( (v88 & 0x4000) != 0 )
              v89 = (*(_WORD *)&v264[20] ^ v88) & 0x3800 ^ *(_WORD *)&v264[20];
            else
              v89 = *(_WORD *)&v264[20] & 0xC7FF;
            *(_WORD *)&v264[20] = v89;
            *(_WORD *)&v264[20] = v89 ^ (*((_WORD *)v87 + 1) ^ v89) & 0x7FF;
            break;
          }
          if ( v86 >= 0x400u )
          {
            v260 |= 1u;
            v100 = v76-- == 1;
            *(_WORD *)&v264[4] = v76;
            if ( !v100 )
              continue;
          }
          break;
        }
      }
      else
      {
        v261 = v48;
        *(_WORD *)&v264[4] = 0;
        *(_DWORD *)v264 = v48;
      }
      if ( (*(_BYTE *)Source & 0x40) != 0 )
      {
        *(_DWORD *)&v264[14] = v48;
        v261 = v48 + 14;
        VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v260);
        v91 = HIDWORD(*(_QWORD *)VersioningInfo);
        v92 = HIWORD(*(_QWORD *)VersioningInfo);
        v93 = 0;
        if ( (((__int16)v92 ^ ((unsigned int)(__int16)v92 >> 1)) & 0x2000) != 0 )
        {
          v94 = v92 & 0xDFFF;
          if ( (v92 & 0x4000) != 0 )
            v94 = v92 | 0x2000;
          LOWORD(v92) = v94;
        }
        if ( (_WORD)v92 == 0xFFFC )
          v93 = (unsigned __int16)v91 >> 5;
        v48 = v93 + v261;
        v261 += v93;
      }
      else
      {
        *(_DWORD *)&v264[14] = 0;
      }
      if ( *(_QWORD *)&v264[6] && *(_QWORD *)&v264[6] < (unsigned __int64)Source + v48 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v95 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v95 )
          {
            v96 = *(_QWORD *)(v95 + 96);
            if ( v96 )
            {
              if ( *(_BYTE *)(v96 + 1177) )
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
        v48 = v261;
      }
      if ( v48 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v97 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v97 )
          {
            v98 = *(_QWORD *)(v97 + 96);
            if ( v98 )
            {
              if ( *(_BYTE *)(v98 + 1177) )
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
        v48 = v261;
      }
    }
LABEL_323:
    if ( v48 < 9 )
    {
      v99 = *(_BYTE *)Source & 0xE;
      if ( v99 )
      {
        v100 = v99 == 12;
        goto LABEL_331;
      }
      goto LABEL_332;
    }
LABEL_333:
    v101 = v48;
  }
  if ( v101 <= 0x6FA )
  {
    v102 = Destination;
    memset_0(Destination, 0, 0x6FAu);
    if ( !v259 )
    {
      if ( !v48 )
      {
        v260 = 0;
        v48 = (unsigned int)v263;
        HIDWORD(v263) = (_DWORD)v263;
        if ( (*(_BYTE *)Source & 0x10) != 0 )
        {
          v48 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v263) + 7) >> 3) + (_DWORD)v263 + 2;
          HIDWORD(v263) = v48;
        }
        if ( (*(_BYTE *)Source & 0x20) != 0 )
        {
          v103 = (unsigned __int16 *)((char *)Source + v48);
          v104 = *v103;
          *(_WORD *)&v264[4] = v104;
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
            RaiseInconsistencyError(Source, 3);
            v104 = *(_WORD *)&v264[4];
          }
          v107 = HIDWORD(v263) + 2 + 2 * v104;
          *(_DWORD *)v264 = v107;
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
            RaiseInconsistencyError(Source, 4);
            v104 = *(_WORD *)&v264[4];
            v107 = *(_DWORD *)v264;
          }
          v48 = v103[v104] & 0x7FFF;
          v261 = v48;
          if ( v107 > v48 )
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
            RaiseInconsistencyError(Source, 4);
            v104 = *(_WORD *)&v264[4];
            v107 = *(_DWORD *)v264;
            v48 = v261;
          }
          while ( (v103[v104] & 0x8000u) != 0 )
          {
            v112 = (char *)Source + HIDWORD(v263);
            if ( v104 == 1 )
              v113 = v107;
            else
              v113 = *(_WORD *)&v112[2 * v104 - 2] & 0x7FFF;
            if ( v113 < v107 || (*(_WORD *)&v112[2 * v104] & 0x7FFFu) < v113 )
            {
              RaiseInconsistencyError(Source, 7);
              v104 = *(_WORD *)&v264[4];
              v107 = *(_DWORD *)v264;
              v48 = v261;
            }
            if ( v113 < v107 || v113 > v48 )
              goto LABEL_423;
            v114 = *(_WORD *)((char *)Source + v113);
            if ( v114 == 5 )
            {
              v260 |= 2u;
              *(_WORD *)&v264[4] = v104 - 1;
              *(_WORD *)&v264[18] = v113;
              v115 = (char *)Source + (unsigned __int16)v113;
              v116 = *((_WORD *)v115 + 1);
              if ( (v116 & 0x4000) != 0 )
                v117 = (*(_WORD *)&v264[20] ^ v116) & 0x3800 ^ *(_WORD *)&v264[20];
              else
                v117 = *(_WORD *)&v264[20] & 0xC7FF;
              *(_WORD *)&v264[20] = v117;
              *(_WORD *)&v264[20] = v117 ^ (*((_WORD *)v115 + 1) ^ v117) & 0x7FF;
              break;
            }
            if ( v114 >= 0x400u )
            {
              v260 |= 1u;
              v100 = v104-- == 1;
              *(_WORD *)&v264[4] = v104;
              if ( !v100 )
                continue;
            }
            break;
          }
        }
        else
        {
          v261 = v48;
          *(_WORD *)&v264[4] = 0;
          *(_DWORD *)v264 = v48;
        }
        if ( (*(_BYTE *)Source & 0x40) != 0 )
        {
          *(_DWORD *)&v264[14] = v48;
          v261 = v48 + 14;
          v118 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v260);
          v119 = HIDWORD(*(_QWORD *)v118);
          v120 = HIWORD(*(_QWORD *)v118);
          v121 = 0;
          if ( (((__int16)v120 ^ ((unsigned int)(__int16)v120 >> 1)) & 0x2000) != 0 )
          {
            v122 = v120 & 0xDFFF;
            if ( (v120 & 0x4000) != 0 )
              v122 = v120 | 0x2000;
            LOWORD(v120) = v122;
          }
          if ( (_WORD)v120 == 0xFFFC )
            v121 = (unsigned __int16)v119 >> 5;
          v48 = v121 + v261;
          v261 += v121;
        }
        else
        {
          *(_DWORD *)&v264[14] = 0;
        }
        if ( *(_QWORD *)&v264[6] && *(_QWORD *)&v264[6] < (unsigned __int64)Source + v48 )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(Source, 18);
          v48 = v261;
        }
        if ( v48 - 1 > 0x3F3B )
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
                  if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
                    goto LABEL_420;
LABEL_421:
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                }
              }
            }
          }
          goto LABEL_422;
        }
      }
      goto LABEL_423;
    }
LABEL_614:
    if ( !v48 )
    {
      CDRecord::Resize((CDRecord *)&v260);
      v48 = v261;
    }
    if ( v48 >= 9 )
      goto LABEL_620;
    if ( (*(_BYTE *)Source & 0x1C) != 0 )
    {
      v128 = (*(_BYTE *)Source & 0x1C) == 12;
LABEL_619:
      if ( !v128 )
LABEL_620:
        v21 = v48;
    }
    goto LABEL_621;
  }
  if ( *(_BYTE *)(*((_QWORD *)v2 + 1) + 9244LL) )
  {
    v102 = Destination;
    memset_0(Destination, 0, 0x6FAu);
    if ( v259 )
    {
      if ( !v48 )
      {
        CDRecord::Resize((CDRecord *)&v260);
        v48 = v261;
      }
      if ( v48 >= 9 || (*(_BYTE *)Source & 0x1C) != 0 && (*(_BYTE *)Source & 0x1C) != 0xC )
        v154 = v48;
      else
        v154 = 9;
    }
    else
    {
      if ( !v48 )
      {
        v260 = 0;
        v48 = (unsigned int)v263;
        HIDWORD(v263) = (_DWORD)v263;
        if ( (*(_BYTE *)Source & 0x10) != 0 )
        {
          v48 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v263) + 7) >> 3) + (_DWORD)v263 + 2;
          HIDWORD(v263) = v48;
        }
        if ( (*(_BYTE *)Source & 0x20) != 0 )
        {
          v129 = (unsigned __int16 *)((char *)Source + v48);
          v130 = *v129;
          *(_WORD *)&v264[4] = v130;
          if ( !v130 )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(Source, 3);
            v130 = *(_WORD *)&v264[4];
          }
          v133 = HIDWORD(v263) + 2 + 2 * v130;
          *(_DWORD *)v264 = v133;
          if ( v133 > 0x1F9E )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v134 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v134 )
              {
                v135 = *(_QWORD *)(v134 + 96);
                if ( v135 )
                {
                  if ( *(_BYTE *)(v135 + 1177) )
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
            v130 = *(_WORD *)&v264[4];
            v133 = *(_DWORD *)v264;
          }
          v48 = v129[v130] & 0x7FFF;
          v261 = v48;
          if ( v133 > v48 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v136 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v136 )
              {
                v137 = *(_QWORD *)(v136 + 96);
                if ( v137 )
                {
                  if ( *(_BYTE *)(v137 + 1177) )
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
            v130 = *(_WORD *)&v264[4];
            v133 = *(_DWORD *)v264;
            v48 = v261;
          }
          while ( (v129[v130] & 0x8000u) != 0 )
          {
            v138 = (char *)Source + HIDWORD(v263);
            if ( v130 == 1 )
              v139 = v133;
            else
              v139 = *(_WORD *)&v138[2 * v130 - 2] & 0x7FFF;
            if ( v139 < v133 || (*(_WORD *)&v138[2 * v130] & 0x7FFFu) < v139 )
            {
              RaiseInconsistencyError(Source, 7);
              v130 = *(_WORD *)&v264[4];
              v133 = *(_DWORD *)v264;
              v48 = v261;
            }
            if ( v139 < v133 || v139 > v48 )
              goto LABEL_515;
            v140 = *(_WORD *)((char *)Source + v139);
            if ( v140 == 5 )
            {
              v260 |= 2u;
              *(_WORD *)&v264[4] = v130 - 1;
              *(_WORD *)&v264[18] = v139;
              v141 = (char *)Source + (unsigned __int16)v139;
              v142 = *((_WORD *)v141 + 1);
              if ( (v142 & 0x4000) != 0 )
                v143 = (*(_WORD *)&v264[20] ^ v142) & 0x3800 ^ *(_WORD *)&v264[20];
              else
                v143 = *(_WORD *)&v264[20] & 0xC7FF;
              *(_WORD *)&v264[20] = v143;
              *(_WORD *)&v264[20] = v143 ^ (*((_WORD *)v141 + 1) ^ v143) & 0x7FF;
              break;
            }
            if ( v140 >= 0x400u )
            {
              v260 |= 1u;
              v100 = v130-- == 1;
              *(_WORD *)&v264[4] = v130;
              if ( !v100 )
                continue;
            }
            break;
          }
        }
        else
        {
          v261 = v48;
          *(_WORD *)&v264[4] = 0;
          *(_DWORD *)v264 = v48;
        }
        if ( (*(_BYTE *)Source & 0x40) != 0 )
        {
          *(_DWORD *)&v264[14] = v48;
          v261 = v48 + 14;
          v144 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v260);
          v145 = HIDWORD(*(_QWORD *)v144);
          v146 = HIWORD(*(_QWORD *)v144);
          v147 = 0;
          if ( (((__int16)v146 ^ ((unsigned int)(__int16)v146 >> 1)) & 0x2000) != 0 )
          {
            v148 = v146 & 0xDFFF;
            if ( (v146 & 0x4000) != 0 )
              v148 = v146 | 0x2000;
            LOWORD(v146) = v148;
          }
          if ( (_WORD)v146 == 0xFFFC )
            v147 = (unsigned __int16)v145 >> 5;
          v48 = v147 + v261;
          v261 += v147;
        }
        else
        {
          *(_DWORD *)&v264[14] = 0;
        }
        if ( *(_QWORD *)&v264[6] && *(_QWORD *)&v264[6] < (unsigned __int64)Source + v48 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v149 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v149 )
            {
              v150 = *(_QWORD *)(v149 + 96);
              if ( v150 )
              {
                if ( *(_BYTE *)(v150 + 1177) )
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
          v48 = v261;
        }
        if ( v48 - 1 > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v151 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v151 )
            {
              v152 = *(_QWORD *)(v151 + 96);
              if ( v152 )
              {
                if ( *(_BYTE *)(v152 + 1177) )
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
          v48 = v261;
        }
      }
LABEL_515:
      if ( v48 >= 9 || (v153 = *(_BYTE *)Source & 0xE) != 0 && v153 != 12 )
        v154 = v48;
      else
        v154 = 9;
    }
    if ( v154 >= 0x6FA )
    {
      v179 = 1786;
    }
    else
    {
      if ( v259 )
        goto LABEL_614;
      if ( !v48 )
      {
        v260 = 0;
        v48 = (unsigned int)v263;
        HIDWORD(v263) = (_DWORD)v263;
        if ( (*(_BYTE *)Source & 0x10) != 0 )
        {
          v48 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v263) + 7) >> 3) + (_DWORD)v263 + 2;
          HIDWORD(v263) = v48;
        }
        if ( (*(_BYTE *)Source & 0x20) != 0 )
        {
          v155 = (unsigned __int16 *)((char *)Source + v48);
          v156 = *v155;
          *(_WORD *)&v264[4] = v156;
          if ( !v156 )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(Source, 3);
            v156 = *(_WORD *)&v264[4];
          }
          v159 = HIDWORD(v263) + 2 + 2 * v156;
          *(_DWORD *)v264 = v159;
          if ( v159 > 0x1F9E )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v160 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v160 )
              {
                v161 = *(_QWORD *)(v160 + 96);
                if ( v161 )
                {
                  if ( *(_BYTE *)(v161 + 1177) )
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
            v156 = *(_WORD *)&v264[4];
            v159 = *(_DWORD *)v264;
          }
          v48 = v155[v156] & 0x7FFF;
          v261 = v48;
          if ( v159 > v48 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v162 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v162 )
              {
                v163 = *(_QWORD *)(v162 + 96);
                if ( v163 )
                {
                  if ( *(_BYTE *)(v163 + 1177) )
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
            v156 = *(_WORD *)&v264[4];
            v159 = *(_DWORD *)v264;
            v48 = v261;
          }
          while ( (v155[v156] & 0x8000u) != 0 )
          {
            v164 = (char *)Source + HIDWORD(v263);
            if ( v156 == 1 )
              v165 = v159;
            else
              v165 = *(_WORD *)&v164[2 * v156 - 2] & 0x7FFF;
            if ( v165 < v159 || (*(_WORD *)&v164[2 * v156] & 0x7FFFu) < v165 )
            {
              RaiseInconsistencyError(Source, 7);
              v156 = *(_WORD *)&v264[4];
              v159 = *(_DWORD *)v264;
              v48 = v261;
            }
            if ( v165 < v159 || v165 > v48 )
              goto LABEL_423;
            v166 = *(_WORD *)((char *)Source + v165);
            if ( v166 == 5 )
            {
              v260 |= 2u;
              *(_WORD *)&v264[4] = v156 - 1;
              *(_WORD *)&v264[18] = v165;
              v167 = (char *)Source + (unsigned __int16)v165;
              v168 = *((_WORD *)v167 + 1);
              if ( (v168 & 0x4000) != 0 )
                v169 = (v168 ^ *(_WORD *)&v264[20]) & 0x3800 ^ *(_WORD *)&v264[20];
              else
                v169 = *(_WORD *)&v264[20] & 0xC7FF;
              *(_WORD *)&v264[20] = v169;
              *(_WORD *)&v264[20] = v169 ^ (*((_WORD *)v167 + 1) ^ v169) & 0x7FF;
              break;
            }
            if ( v166 >= 0x400u )
            {
              v260 |= 1u;
              v100 = v156-- == 1;
              *(_WORD *)&v264[4] = v156;
              if ( !v100 )
                continue;
            }
            break;
          }
        }
        else
        {
          v261 = v48;
          *(_WORD *)&v264[4] = 0;
          *(_DWORD *)v264 = v48;
        }
        if ( (*(_BYTE *)Source & 0x40) != 0 )
        {
          *(_DWORD *)&v264[14] = v48;
          v261 = v48 + 14;
          v170 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v260);
          v171 = HIDWORD(*(_QWORD *)v170);
          v172 = HIWORD(*(_QWORD *)v170);
          v173 = 0;
          if ( (((__int16)v172 ^ ((unsigned int)(__int16)v172 >> 1)) & 0x2000) != 0 )
          {
            v174 = v172 & 0xDFFF;
            if ( (v172 & 0x4000) != 0 )
              v174 = v172 | 0x2000;
            LOWORD(v172) = v174;
          }
          if ( (_WORD)v172 == 0xFFFC )
            v173 = (unsigned __int16)v171 >> 5;
          v48 = v173 + v261;
          v261 += v173;
        }
        else
        {
          *(_DWORD *)&v264[14] = 0;
        }
        if ( *(_QWORD *)&v264[6] && *(_QWORD *)&v264[6] < (unsigned __int64)Source + v48 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v175 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v175 )
            {
              v176 = *(_QWORD *)(v175 + 96);
              if ( v176 )
              {
                if ( *(_BYTE *)(v176 + 1177) )
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
          v48 = v261;
        }
        if ( v48 - 1 > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v177 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v177 )
            {
              v178 = *(_QWORD *)(v177 + 96);
              if ( v178 )
              {
                if ( *(_BYTE *)(v178 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    goto LABEL_421;
LABEL_420:
                  ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
LABEL_422:
          RaiseInconsistencyError(Source, 5);
          v48 = v261;
        }
      }
LABEL_423:
      if ( v48 >= 9 )
        goto LABEL_620;
      v127 = *(_BYTE *)Source & 0xE;
      if ( v127 )
      {
        v128 = v127 == 12;
        goto LABEL_619;
      }
LABEL_621:
      v179 = v21;
    }
    memcpy_s(v102, 0x6FAu, Source, v179);
    v192 = 1;
  }
LABEL_624:
  if ( v186 )
  {
    if ( (*((_WORD *)v186 + 49) & 0x400) != 0 && (__int16)v188 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v186);
      goto LABEL_647;
    }
    v180 = (__int16)v188;
    v181 = (volatile signed __int32 *)v186;
    if ( (*((_WORD *)v186 + 49) & 8) != 0 )
    {
      if ( (__int16)v188 == 3 )
      {
        v180 = 4;
        goto LABEL_632;
      }
      if ( (__int16)v188 >= 2 )
      {
LABEL_632:
        if ( (*((_DWORD *)v186 + 25) & 8) != 0 )
        {
          v182 = v186[18];
          if ( v182 )
          {
            if ( *(_QWORD *)(v182 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v182 + 1880), v186, v180);
            }
          }
        }
      }
    }
    if ( byte_10317ABE5 < 0
      && (v181[25] & 8) != 0
      && (int)v180 >= 3
      && (v181[25] & 0xC0000000) != 0x40000000
      && *(_QWORD *)v181
      && VirtualProtect(*(LPVOID *)v181, 0x2000u, 2u, &v223) )
    {
      _InterlockedAnd(v181 + 25, 0x3FFFFFFFu);
      _InterlockedOr(v181 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal(v181 + 38, v180);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v181, 0, v180);
    v188 &= 0xFFFF0000;
    v186 = 0;
  }
LABEL_647:
  PageRef::~PageRef((PageRef *)&v186);
  return v192;
}

```

## disassembly

```asm
0x101854e80  push    rbp
0x101854e82  push    rsi
0x101854e83  push    rdi
0x101854e84  push    r12
0x101854e86  push    r13
0x101854e88  push    r14
0x101854e8a  push    r15
0x101854e8c  lea     rbp, [rsp-3F0h]
0x101854e94  sub     rsp, 4F0h
0x101854e9b  mov     [rbp+420h+var_3F8], 0FFFFFFFFFFFFFFFEh
0x101854ea3  mov     [rsp+520h+arg_10], rbx
0x101854eab  mov     rax, cs:__security_cookie
0x101854eb2  xor     rax, rsp
0x101854eb5  mov     [rbp+420h+var_40], rax
0x101854ebc  mov     [rbp+420h+Destination], rdx
0x101854ec0  mov     r12, rcx
0x101854ec3  mov     [rbp+420h+var_450], rcx
0x101854ec7  xor     r13d, r13d
0x101854eca  mov     [rsp+520h+var_4F0], r13
0x101854ecf  mov     [rsp+520h+var_4E8], r13b
0x101854ed4  mov     eax, [rsp+520h+var_4E4]
0x101854ed8  and     eax, 0FFFF0000h
0x101854edd  mov     [rsp+520h+var_4E4], eax
0x101854ee1  and     eax, 0FF00FFFFh
0x101854ee6  mov     [rsp+520h+var_4E4], eax
0x101854eea  mov     [rsp+520h+var_4E4], r13d
0x101854eef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x101854ef6  mov     [rbp+420h+var_150], ax
0x101854efd  mov     [rbp+420h+Source], r13
0x101854f04  mov     [rbp+420h+var_14C], r13d
0x101854f0b  mov     [rbp+420h+var_138+6], r13
0x101854f12  mov     [rbp+420h+var_128], r13
0x101854f19  mov     [rbp+420h+var_140], r13
0x101854f20  mov     [rbp+420h+var_11C], eax
0x101854f26  mov     [rsp+520h+var_4D0], r13d
0x101854f2b  mov     rax, [rcx]
0x101854f2e  test    byte ptr [rax+7Ch], 1
0x101854f32  jz      loc_101857D77
0x101854f38  mov     [rsp+520h+var_4D8], r13d
0x101854f3d  mov     eax, 2
0x101854f42  mov     [rsp+520h+var_4D4], ax
0x101854f47  mov     rbx, [rcx+8]
0x101854f4b  mov     [rbp+420h+var_40C], r13
0x101854f4f  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x101854f56  cmp     [rax], r13b
0x101854f59  jz      short loc_101854FD4
0x101854f5b  test    cs:byte_10317ABE6, 80h
0x101854f62  jnz     short loc_101854FD4
0x101854f64  mov     r8, gs:58h
0x101854f6d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101854f74  mov     ecx, [rax]
0x101854f76  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101854f7d  mov     edx, [rax]
0x101854f7f  add     rdx, [r8+rcx*8]
0x101854f83  mov     rax, [rdx]
0x101854f86  test    rax, rax
0x101854f89  jz      short loc_101854FA6
0x101854f8b  mov     rax, [rax+38h]
0x101854f8f  mov     rcx, [rax]
0x101854f92  test    rcx, rcx
0x101854f95  jz      short loc_101854FA6
0x101854f97  mov     edx, 337h
0x101854f9c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101854fa2  test    eax, eax
0x101854fa4  jnz     short loc_101854FD4
0x101854fa6  mov     r8, gs:58h
0x101854faf  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101854fb6  mov     ecx, [rax]
0x101854fb8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101854fbf  mov     edx, [rax]
0x101854fc1  add     rdx, [r8+rcx*8]
0x101854fc5  mov     rax, [rdx+8]
0x101854fc9  test    rax, rax
0x101854fcc  jz      short loc_101854FD4
0x101854fce  mov     r15, [rax+60h]
0x101854fd2  jmp     short loc_101854FD7
0x101854fd4  mov     r15, r13
0x101854fd7  mov     r14, [rbx+728h]
0x101854fde  mov     edi, 400h
0x101854fe3  mov     r10d, 2000h
0x101854fe9  mov     [rsp+520h+var_4C0], r13d
0x101854fee  mov     rcx, [rsp+520h+var_4F0]
0x101854ff3  test    rcx, rcx
0x101854ff6  jz      loc_101855116
0x101854ffc  movzx   eax, word ptr [rcx+62h]
0x101855000  movsx   edx, word ptr [rsp+520h+var_4E4]
0x101855005  test    di, ax
0x101855008  jz      short loc_10185501E
0x10185500a  cmp     edx, 3
0x10185500d  jl      short loc_10185501E
0x10185500f  lea     rcx, [rsp+520h+var_4F0]; this
0x101855014  call    ?UnfixLatchOnly@PageRef@@IEAAXXZ; PageRef::UnfixLatchOnly(void)
0x101855019  jmp     loc_101855116
0x10185501e  mov     esi, edx
0x101855020  mov     rdi, [rsp+520h+var_4F0]
0x101855025  movzx   eax, word ptr [rcx+62h]
0x101855029  shr     al, 3
0x10185502c  test    al, 1
0x10185502e  jz      short loc_101855084
0x101855030  cmp     edx, 3
0x101855033  jnz     short loc_10185503A
0x101855035  lea     esi, [rdx+1]
0x101855038  jmp     short loc_10185503F
0x10185503a  cmp     edx, 2
0x10185503d  jl      short loc_101855084
0x10185503f  mov     rax, [rsp+520h+var_4F0]
0x101855044  mov     ecx, [rax+64h]
0x101855047  test    cl, 8
0x10185504a  jz      short loc_101855084
0x10185504c  mov     rax, [rsp+520h+var_4F0]
0x101855051  mov     rcx, [rax+90h]
0x101855058  test    rcx, rcx
0x10185505b  jz      short loc_101855084
0x10185505d  cmp     qword ptr [rcx+758h], 0
0x101855065  jz      short loc_101855084
0x101855067  lfence
0x10185506a  mov     r8d, esi
0x10185506d  mov     rdx, [rsp+520h+var_4F0]
0x101855072  mov     rcx, [rcx+758h]
0x101855079  call    ?OnReleasingBufLatch@DirtyPageMgr@@QEAAXPEAUBUF@@W4LATCH_TYPE@LatchBase@@@Z; DirtyPageMgr::OnReleasingBufLatch(BUF *,LatchBase::LATCH_TYPE)
0x10185507e  mov     r10d, 2000h
0x101855084  test    cs:byte_10317ABE5, 80h
0x10185508b  jz      short loc_1018550D7
0x10185508d  mov     eax, [rdi+64h]
0x101855090  test    al, 8
0x101855092  jz      short loc_1018550D7
0x101855094  cmp     esi, 3
0x101855097  jl      short loc_1018550D7
0x101855099  mov     eax, [rdi+64h]
0x10185509c  and     eax, 0C0000000h
0x1018550a1  cmp     eax, 40000000h
0x1018550a6  jz      short loc_1018550D7
0x1018550a8  mov     rcx, [rdi]; lpAddress
0x1018550ab  test    rcx, rcx
0x1018550ae  jz      short loc_1018550D7
0x1018550b0  lea     r9, [rbp+420h+flOldProtect]; lpflOldProtect
0x1018550b4  mov     r8d, 2; flNewProtect
0x1018550ba  mov     rdx, r10; dwSize
0x1018550bd  call    cs:__imp_VirtualProtect
0x1018550c3  test    eax, eax
0x1018550c5  jz      short loc_1018550D7
0x1018550c7  lock and dword ptr [rdi+64h], 3FFFFFFFh
0x1018550cf  lock or dword ptr [rdi+64h], 40000000h
0x1018550d7  lea     rcx, [rdi+98h]
0x1018550de  mov     edx, esi
0x1018550e0  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x1018550e5  cmp     cs:?sm_acquireReleaseEnforcementExpensive@LatchBase@@0HA, 0; int LatchBase::sm_acquireReleaseEnforcementExpensive
0x1018550ec  jz      short loc_101855104
0x1018550ee  test    cs:byte_10317AD4F, 2
0x1018550f5  jz      short loc_101855104
0x1018550f7  mov     r8d, esi
0x1018550fa  xor     edx, edx
0x1018550fc  mov     rcx, rdi
0x1018550ff  call    ?TraceLatchAcquireRelease@BUF@@QEAAX_NW4LATCH_TYPE@LatchBase@@@Z; BUF::TraceLatchAcquireRelease(bool,LatchBase::LATCH_TYPE)
0x101855104  and     [rsp+520h+var_4E4], 0FFFF0000h
0x10185510c  mov     [rsp+520h+var_4F0], r13
0x101855111  mov     edi, 400h
0x101855116  cmp     qword ptr [rbx+728h], 0
0x10185511e  jz      loc_101855255
0x101855124  mov     r8, rbx; struct RecoveryUnit *
0x101855127  lea     rdx, [rsp+520h+var_4D8]; struct PageId *
0x10185512c  lea     rcx, [rsp+520h+var_4F0]; this
0x101855131  call    ?CatchupPageRedos@PageRef@@QEAAXAEBVPageId@@PEAVRecoveryUnit@@@Z; PageRef::CatchupPageRedos(PageId const &,RecoveryUnit *)
0x101855136  mov     rcx, [rsp+520h+var_4F0]
0x10185513b  test    rcx, rcx
0x10185513e  jz      loc_101855255
0x101855144  movzx   eax, word ptr [rcx+62h]
0x101855148  movsx   edx, word ptr [rsp+520h+var_4E4]
0x10185514d  test    di, ax
0x101855150  jz      short loc_101855166
0x101855152  cmp     edx, 3
0x101855155  jl      short loc_101855166
0x101855157  lea     rcx, [rsp+520h+var_4F0]; this
0x10185515c  call    ?UnfixLatchOnly@PageRef@@IEAAXXZ; PageRef::UnfixLatchOnly(void)
0x101855161  jmp     loc_101855255
0x101855166  mov     esi, edx
0x101855168  mov     rdi, [rsp+520h+var_4F0]
0x10185516d  movzx   eax, word ptr [rcx+62h]
0x101855171  shr     al, 3
0x101855174  test    al, 1
0x101855176  jz      short loc_1018551C6
0x101855178  cmp     edx, 3
0x10185517b  jnz     short loc_101855182
0x10185517d  lea     esi, [rdx+1]
0x101855180  jmp     short loc_101855187
0x101855182  cmp     edx, 2
0x101855185  jl      short loc_1018551C6
0x101855187  mov     rax, [rsp+520h+var_4F0]
0x10185518c  mov     ecx, [rax+64h]
0x10185518f  test    cl, 8
0x101855192  jz      short loc_1018551C6
0x101855194  mov     rax, [rsp+520h+var_4F0]
0x101855199  mov     rcx, [rax+90h]
0x1018551a0  test    rcx, rcx
0x1018551a3  jz      short loc_1018551C6
0x1018551a5  cmp     qword ptr [rcx+758h], 0
0x1018551ad  jz      short loc_1018551C6
0x1018551af  lfence
0x1018551b2  mov     r8d, esi
0x1018551b5  mov     rdx, [rsp+520h+var_4F0]
0x1018551ba  mov     rcx, [rcx+758h]
0x1018551c1  call    ?OnReleasingBufLatch@DirtyPageMgr@@QEAAXPEAUBUF@@W4LATCH_TYPE@LatchBase@@@Z; DirtyPageMgr::OnReleasingBufLatch(BUF *,LatchBase::LATCH_TYPE)
0x1018551c6  test    cs:byte_10317ABE5, 80h
0x1018551cd  jz      short loc_10185521B
0x1018551cf  mov     eax, [rdi+64h]
0x1018551d2  test    al, 8
0x1018551d4  jz      short loc_10185521B
0x1018551d6  cmp     esi, 3
0x1018551d9  jl      short loc_10185521B
0x1018551db  mov     eax, [rdi+64h]
0x1018551de  and     eax, 0C0000000h
0x1018551e3  cmp     eax, 40000000h
0x1018551e8  jz      short loc_10185521B
0x1018551ea  mov     rcx, [rdi]; lpAddress
0x1018551ed  test    rcx, rcx
0x1018551f0  jz      short loc_10185521B
0x1018551f2  lea     r9, [rbp+420h+var_41C]; lpflOldProtect
0x1018551f6  mov     edx, 2000h; dwSize
0x1018551fb  mov     r8d, 2; flNewProtect
0x101855201  call    cs:__imp_VirtualProtect
0x101855207  test    eax, eax
0x101855209  jz      short loc_10185521B
0x10185520b  lock and dword ptr [rdi+64h], 3FFFFFFFh
0x101855213  lock or dword ptr [rdi+64h], 40000000h
0x10185521b  lea     rcx, [rdi+98h]
0x101855222  mov     edx, esi
0x101855224  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x101855229  cmp     cs:?sm_acquireReleaseEnforcementExpensive@LatchBase@@0HA, 0; int LatchBase::sm_acquireReleaseEnforcementExpensive
0x101855230  jz      short loc_101855248
0x101855232  test    cs:byte_10317AD4F, 2
0x101855239  jz      short loc_101855248
0x10185523b  mov     r8d, esi
0x10185523e  xor     edx, edx
0x101855240  mov     rcx, rdi
0x101855243  call    ?TraceLatchAcquireRelease@BUF@@QEAAX_NW4LATCH_TYPE@LatchBase@@@Z; BUF::TraceLatchAcquireRelease(bool,LatchBase::LATCH_TYPE)
0x101855248  and     [rsp+520h+var_4E4], 0FFFF0000h
0x101855250  mov     [rsp+520h+var_4F0], r13
0x101855255  lea     rax, [rbp+420h+var_410]
0x101855259  mov     [rsp+520h+var_4F8], rax
0x10185525e  mov     eax, 2
0x101855263  mov     dword ptr [rsp+520h+var_500], eax
0x101855267  lea     r9, [rsp+520h+var_4C0]
0x10185526c  lea     r8, [rsp+520h+var_4D8]
0x101855271  mov     rdx, rbx
0x101855274  mov     rcx, cs:qword_10317B628
0x10185527b  call    ?Get@BPool@@QEAAPEAUBUF@@AEAVRecoveryUnit@@AEBVPageId@@AEAHW4LATCH_TYPE@LatchBase@@PEAVLatchSuspendInfo@@@Z; BPool::Get(RecoveryUnit &,PageId const &,int &,LatchBase::LATCH_TYPE,LatchSuspendInfo *)
0x101855280  mov     [rsp+520h+var_4F0], rax
0x101855285  mov     r8d, [rsp+520h+var_4E4]
0x10185528a  and     r8d, 0FFFF0002h
0x101855291  or      r8d, 2
0x101855295  mov     [rsp+520h+var_4E4], r8d
0x10185529a  test    r15, r15
0x10185529d  jz      short loc_1018552CA
0x10185529f  mov     rdx, [rax]
0x1018552a2  mov     eax, [r15+500h]
0x1018552a9  and     eax, 0Fh
0x1018552ac  cmp     [r15+rax*8+508h], rdx
0x1018552b4  jz      short loc_1018552CA
0x1018552b6  mov     [r15+rax*8+508h], rdx
0x1018552be  inc     qword ptr [r15+500h]
0x1018552c5  mov     r8d, [rsp+520h+var_4E4]
0x1018552ca  mov     ecx, [rsp+520h+var_4C0]
0x1018552ce  mov     edx, ecx
0x1018552d0  shr     edx, 3
0x1018552d3  and     edx, 1
0x1018552d6  shl     edx, 18h
0x1018552d9  and     r8d, 0FFFFFFh
0x1018552e0  or      edx, r8d
0x1018552e3  mov     [rsp+520h+var_4E4], edx
0x1018552e7  shr     ecx, 4
0x1018552ea  and     ecx, 1
0x1018552ed  mov     eax, [rsp+520h+var_4E0]
0x1018552f1  and     eax, 0FFFFFF00h
0x1018552f6  or      ecx, eax
0x1018552f8  mov     [rsp+520h+var_4E0], ecx
0x1018552fc  test    r14, r14
0x1018552ff  jz      short loc_101855346
0x101855301  test    r15, r15
0x101855304  jz      short loc_101855346
0x101855306  cmp     r15, [rbx+1C38h]
0x10185530d  jnz     short loc_101855346
0x10185530f  inc     qword ptr [r14+5B28h]
0x101855316  cmp     dword ptr [rbp+420h+var_40C], 0
0x10185531a  jz      short loc_101855346
0x10185531c  inc     qword ptr [r14+5B30h]
0x101855323  mov     eax, [rbp+420h+var_410]
0x101855326  add     [r14+5B38h], rax
0x10185532d  cmp     edx, 1000000h
0x101855333  jb      short loc_101855346
0x101855335  inc     qword ptr [r14+5B40h]
0x10185533c  mov     eax, [rbp+420h+var_410]
0x10185533f  add     [r14+5B48h], rax
0x101855346  mov     rcx, rbx; this
0x101855349  call    ?IsRbIoDb@RecoveryUnit@@QEBA_NXZ; RecoveryUnit::IsRbIoDb(void)
0x10185534e  mov     r13d, 9
0x101855354  test    al, al
0x101855356  jz      loc_1018559CB
0x10185535c  cmp     byte ptr [rbx+2050h], 0
0x101855363  jz      loc_1018559CB
0x101855369  mov     eax, [rsp+520h+var_4D8]
  ... truncated ...
```
