# UtilDbccSetNullColumnLength(DbccCombinedId const &,FullPageId const &,int,ulong,short)

- ea: `0x101ea2520`
- end: `0x101ea501d`
- name: `?UtilDbccSetNullColumnLength@@YAXAEBVDbccCombinedId@@AEBVFullPageId@@HKF@Z`
- size: `11005`
- prototype: `void __fastcall(const struct DbccCombinedId *, const struct FullPageId *, int, unsigned int, __int16)`
- caller_count: `1`
- callee_count: `40`
- tags: `installer_update, broker_com_uri`

## callers

- `0x101e828f0`

## callees

- `0x100401490`
- `0x100402000`
- `0x100403030`
- `0x10040da40`
- `0x10040da80`
- `0x10040eca0`
- `0x100415e90`
- `0x1004176a0`
- `0x100432c80`
- `0x10043ba50`
- `0x100441e00`
- `0x100445640`
- `0x10046bf90`
- `0x1004729d0`
- `0x10047bc10`
- `0x10047ffb0`
- `0x100480030`
- `0x100484700`
- `0x100492f80`
- `0x1004c4700`
- `0x10052b970`
- `0x1005d9f70`
- `0x10069f4f0`
- `0x1012c9010`
- `0x1016c9e80`
- `0x1018c9d70`
- `0x101907610`
- `0x101cb13d0`
- `0x101ced0e0`
- `0x101ea2520`
- `0x101ea5110`
- `0x101ed08f0`
- `0x101ed0980`
- `0x101ed0b00`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021e86b0`
- `0x1021eab40`
- `0x1021ed230`
- `0x1023ae3e0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x101ea2892`
- `KERNEL32!VirtualProtect` at `0x101ea29cf`
- `KERNEL32!VirtualProtect` at `0x101ea2e06`
- `KERNEL32!VirtualProtect` at `0x101ea2892`
- `KERNEL32!VirtualProtect` at `0x101ea29cf`
- `KERNEL32!VirtualProtect` at `0x101ea2e06`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101ea316b`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x101ea2724`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea35da`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3670`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea38a5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3968`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3aab`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3b80`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3c54`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3f0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3fd1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4153`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4228`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea42fc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea45b0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4675`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4963`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4a32`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4b00`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4d6d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4e2c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea35da`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3670`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea38a5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3968`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3aab`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3b80`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3c54`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3f0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea3fd1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4153`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4228`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea42fc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea45b0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4675`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4963`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4a32`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4b00`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4d6d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ea4e2c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea266b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea326b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3a85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3b5a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3c2e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3ee6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3fab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea412d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4202`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea42d6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea458a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea464f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4940`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4a0f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4add`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4d47`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4e06`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4faf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea266b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea326b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3a85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3b5a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3c2e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3ee6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea3fab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea412d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4202`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea42d6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea458a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea464f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4940`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4a0f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4add`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4d47`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4e06`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ea4faf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101ea2771`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101ea2771`
- `sqldk!SystemThread_TlsIndex` at `0x101ea2742`
- `sqldk!SystemThread_TlsIndex` at `0x101ea2784`
- `sqldk!SystemThread_TlsIndex` at `0x101ea2c3f`
- `sqldk!SystemThread_TlsIndex` at `0x101ea2c7f`
- `sqldk!SystemThread_TlsIndex` at `0x101ea3a30`
- `sqldk!SystemThread_TlsIndex` at `0x101ea3b05`
- `sqldk!SystemThread_TlsIndex` at `0x101ea3bd9`
- `sqldk!SystemThread_TlsIndex` at `0x101ea3e91`
- `sqldk!SystemThread_TlsIndex` at `0x101ea3f56`
- `sqldk!SystemThread_TlsIndex` at `0x101ea40d8`
- `sqldk!SystemThread_TlsIndex` at `0x101ea41ad`
- `sqldk!SystemThread_TlsIndex` at `0x101ea4281`
- `sqldk!SystemThread_TlsIndex` at `0x101ea4535`
- `sqldk!SystemThread_TlsIndex` at `0x101ea45fa`
- `sqldk!SystemThread_TlsIndex` at `0x101ea48eb`
- `sqldk!SystemThread_TlsIndex` at `0x101ea49ba`
- `sqldk!SystemThread_TlsIndex` at `0x101ea4a88`
- `sqldk!SystemThread_TlsIndex` at `0x101ea4cf2`
- `sqldk!SystemThread_TlsIndex` at `0x101ea4db1`
- `sqldk!SystemThread_TlsOffset` at `0x101ea274b`
- `sqldk!SystemThread_TlsOffset` at `0x101ea278d`
- `sqldk!SystemThread_TlsOffset` at `0x101ea2c48`
- `sqldk!SystemThread_TlsOffset` at `0x101ea2c88`
- `sqldk!SystemThread_TlsOffset` at `0x101ea3a39`
- `sqldk!SystemThread_TlsOffset` at `0x101ea3b0e`
- `sqldk!SystemThread_TlsOffset` at `0x101ea3be2`
- `sqldk!SystemThread_TlsOffset` at `0x101ea3e9a`
- `sqldk!SystemThread_TlsOffset` at `0x101ea3f5f`
- `sqldk!SystemThread_TlsOffset` at `0x101ea40e1`
- `sqldk!SystemThread_TlsOffset` at `0x101ea41b6`
- `sqldk!SystemThread_TlsOffset` at `0x101ea428a`
- `sqldk!SystemThread_TlsOffset` at `0x101ea453e`
- `sqldk!SystemThread_TlsOffset` at `0x101ea4603`
- `sqldk!SystemThread_TlsOffset` at `0x101ea48f4`
- `sqldk!SystemThread_TlsOffset` at `0x101ea49c3`
- `sqldk!SystemThread_TlsOffset` at `0x101ea4a91`
- `sqldk!SystemThread_TlsOffset` at `0x101ea4cfb`
- `sqldk!SystemThread_TlsOffset` at `0x101ea4dba`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UtilDbccSetNullColumnLength(
        const struct DbccCombinedId *a1,
        const struct FullPageId *a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int16 a5)
{
  struct SEInternalTLS *SETLSFromTlsMaybeNull; // r15
  struct XDES *v8; // rdi
  struct RecoveryUnit *PrimaryPRU; // rax
  unsigned int v10; // esi
  __int64 v11; // rdx
  __int64 FCB; // rax
  __int64 v13; // rsi
  unsigned int LockTimeout; // eax
  __int16 v15; // cx
  __int64 v16; // rbx
  __int64 v17; // rdx
  struct CSessionTraceFlags *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // r14
  __int64 v21; // r13
  __int16 v22; // r12
  unsigned int v23; // esi
  BUF *v24; // rdi
  __int64 v25; // rcx
  unsigned int v26; // esi
  BUF *v27; // rdi
  __int64 v28; // rcx
  BUF *v29; // rax
  unsigned int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned int v33; // edx
  bool IsRbIoDb; // al
  __int64 v35; // rdx
  __int64 v36; // r11
  char v37; // al
  int v38; // eax
  unsigned int v39; // ecx
  __int64 v40; // rdx
  BUF *v41; // rcx
  __int64 v42; // r11
  __int64 v43; // rdx
  unsigned int v44; // esi
  BUF *v45; // rdi
  __int64 v46; // rcx
  int v47; // eax
  unsigned int v48; // ecx
  LSN v49; // xmm0_8
  unsigned __int16 v50; // di
  __int64 v51; // r11
  char v52; // al
  unsigned __int16 v53; // r11
  __int64 v54; // r10
  int v55; // r14d
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  int *v59; // rdx
  __int64 v60; // rcx
  int v61; // ecx
  int **v62; // rax
  __int64 v63; // rsi
  unsigned int v64; // ebx
  _WORD *v65; // r13
  __int64 v66; // rdx
  unsigned int v67; // r15d
  __int64 v68; // rax
  unsigned int v69; // ebx
  struct PageComprInfo *v70; // rdi
  unsigned __int8 *v71; // r15
  char v72; // al
  __int16 v73; // r11
  unsigned __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // r12
  unsigned __int8 *v77; // r8
  unsigned __int8 v78; // dl
  __int16 v79; // dx
  __int16 v80; // cx
  unsigned __int16 v81; // ax
  unsigned int v82; // ecx
  int v83; // eax
  int v84; // eax
  int v85; // ecx
  unsigned __int8 *v86; // rax
  __int16 v87; // cx
  PageComprInfoCache *v88; // rcx
  int v89; // r14d
  unsigned __int16 *v90; // r9
  char v91; // dl
  unsigned __int16 v92; // cx
  __int64 v93; // rsi
  _WORD *v94; // rsi
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  char *v101; // rax
  unsigned int v102; // edi
  unsigned __int16 v103; // dx
  char *v104; // rdx
  __int16 v105; // r8
  __int16 v106; // cx
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v108; // r9
  __int64 v109; // rdx
  int v110; // r8d
  __int16 v111; // ax
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  char v116; // cl
  bool v117; // zf
  unsigned int v118; // r14d
  _WORD *v119; // rsi
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  char *v126; // rax
  unsigned int v127; // edi
  unsigned __int16 v128; // dx
  char *v129; // rdx
  __int16 v130; // ax
  __int16 v131; // cx
  struct RecVersioningInfo *v132; // rax
  __int64 v133; // r9
  __int64 v134; // rdx
  int v135; // r8d
  __int16 v136; // ax
  __int64 v137; // rax
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // rax
  char v141; // cl
  unsigned int v142; // ecx
  unsigned __int8 *v143; // r8
  unsigned __int8 *v144; // rdx
  int v145; // ecx
  unsigned int v146; // ebx
  unsigned int v147; // edx
  unsigned __int8 *v148; // rdx
  __int16 v149; // ax
  __int16 v150; // cx
  struct PageComprInfo *v151; // rax
  unsigned int v152; // edx
  unsigned __int8 *v153; // rdi
  unsigned __int16 v154; // r8
  __int64 v155; // rax
  __int64 v156; // rax
  unsigned int v157; // r10d
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 v160; // rax
  __int64 v161; // rax
  unsigned __int8 *v162; // rax
  unsigned int v163; // ebx
  unsigned __int16 v164; // r9
  unsigned __int8 *v165; // r8
  __int16 v166; // r9
  __int16 v167; // cx
  struct RecVersioningInfo *v168; // rax
  __int64 v169; // r9
  __int64 v170; // rdx
  int v171; // r8d
  __int16 v172; // ax
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  char v177; // cl
  unsigned int v178; // ecx
  XDES *v179; // rbx
  void (__fastcall ***v180)(_QWORD, __int64); // rbx
  unsigned int v181; // eax
  int v182; // ecx
  __int64 v183; // rcx
  signed __int32 v184[8]; // [rsp+0h] [rbp-110h] BYREF
  __int16 v185[4]; // [rsp+20h] [rbp-F0h]
  unsigned __int8 v186[8]; // [rsp+90h] [rbp-80h] BYREF
  BUF *v187; // [rsp+98h] [rbp-78h] BYREF
  char v188; // [rsp+A0h] [rbp-70h]
  unsigned int v189; // [rsp+A4h] [rbp-6Ch]
  unsigned int v190; // [rsp+A8h] [rbp-68h]
  __int16 v191; // [rsp+B0h] [rbp-60h] BYREF
  unsigned __int16 v192; // [rsp+B2h] [rbp-5Eh] BYREF
  unsigned int v193; // [rsp+B4h] [rbp-5Ch]
  unsigned __int8 *v194; // [rsp+B8h] [rbp-58h]
  struct PageComprInfo *v195; // [rsp+C0h] [rbp-50h]
  unsigned int v196; // [rsp+C8h] [rbp-48h]
  unsigned __int16 v197; // [rsp+CCh] [rbp-44h]
  unsigned __int64 v198; // [rsp+CEh] [rbp-42h]
  _TBYTE v199; // [rsp+D6h] [rbp-3Ah]
  int v200; // [rsp+E8h] [rbp-28h] BYREF
  __int16 v201; // [rsp+ECh] [rbp-24h]
  unsigned int v202; // [rsp+F0h] [rbp-20h]
  unsigned int v203; // [rsp+F4h] [rbp-1Ch] BYREF
  int v204; // [rsp+F8h] [rbp-18h] BYREF
  __int16 v205; // [rsp+FCh] [rbp-14h]
  LSN v206; // [rsp+100h] [rbp-10h]
  int v207; // [rsp+108h] [rbp-8h]
  unsigned int v208; // [rsp+10Ch] [rbp-4h] BYREF
  int v209; // [rsp+110h] [rbp+0h]
  LSN v210; // [rsp+118h] [rbp+8h] BYREF
  unsigned __int16 v211; // [rsp+120h] [rbp+10h]
  void (__fastcall ***v212)(_QWORD, __int64); // [rsp+128h] [rbp+18h] BYREF
  __int64 v213; // [rsp+130h] [rbp+20h] BYREF
  unsigned __int16 v214; // [rsp+138h] [rbp+28h]
  int v215; // [rsp+140h] [rbp+30h] BYREF
  int v216; // [rsp+144h] [rbp+34h] BYREF
  __int16 v217; // [rsp+148h] [rbp+38h]
  int v218; // [rsp+14Ch] [rbp+3Ch] BYREF
  __int16 v219; // [rsp+150h] [rbp+40h]
  int v220; // [rsp+154h] [rbp+44h] BYREF
  __int16 v221; // [rsp+158h] [rbp+48h]
  __int64 v222; // [rsp+160h] [rbp+50h] BYREF
  __int16 v223; // [rsp+168h] [rbp+58h]
  unsigned __int64 v224; // [rsp+170h] [rbp+60h] BYREF
  __int16 v225; // [rsp+178h] [rbp+68h]
  const struct DbccCombinedId *v226; // [rsp+180h] [rbp+70h]
  __int64 v227; // [rsp+188h] [rbp+78h] BYREF
  __int16 v228; // [rsp+190h] [rbp+80h]
  LSN v229; // [rsp+198h] [rbp+88h] BYREF
  __int16 v230; // [rsp+1A0h] [rbp+90h]
  DWORD flOldProtect; // [rsp+1A8h] [rbp+98h] BYREF
  DWORD v232; // [rsp+1ACh] [rbp+9Ch] BYREF
  DWORD v233; // [rsp+1B0h] [rbp+A0h] BYREF
  __int64 v234; // [rsp+1B8h] [rbp+A8h] BYREF
  XDES *v235; // [rsp+1C0h] [rbp+B0h]
  unsigned int v236; // [rsp+1C8h] [rbp+B8h] BYREF
  __int64 v237; // [rsp+1CCh] [rbp+BCh]
  _QWORD v238[2]; // [rsp+1E0h] [rbp+D0h] BYREF
  __int64 v239; // [rsp+1F0h] [rbp+E0h]
  int v240; // [rsp+1F8h] [rbp+E8h]
  int v241; // [rsp+208h] [rbp+F8h]
  char v242; // [rsp+210h] [rbp+100h]
  unsigned int v243; // [rsp+218h] [rbp+108h]
  _BYTE v244[16]; // [rsp+220h] [rbp+110h] BYREF
  __int64 v245; // [rsp+230h] [rbp+120h]
  char v246[8]; // [rsp+240h] [rbp+130h] BYREF
  int v247; // [rsp+248h] [rbp+138h]
  int v248; // [rsp+250h] [rbp+140h]
  int **v249; // [rsp+258h] [rbp+148h]
  char *v250; // [rsp+260h] [rbp+150h]
  __int64 v251; // [rsp+268h] [rbp+158h]
  int *v252; // [rsp+270h] [rbp+160h] BYREF
  int v253; // [rsp+278h] [rbp+168h]
  int v254; // [rsp+27Ch] [rbp+16Ch]
  GUID *v255; // [rsp+280h] [rbp+170h]
  int v256; // [rsp+288h] [rbp+178h]
  int v257; // [rsp+28Ch] [rbp+17Ch]
  GUID *v258; // [rsp+290h] [rbp+180h]
  int v259; // [rsp+298h] [rbp+188h]
  int v260; // [rsp+29Ch] [rbp+18Ch]
  wchar_t *v261; // [rsp+2A0h] [rbp+190h]
  int v262; // [rsp+2A8h] [rbp+198h]
  int v263; // [rsp+2ACh] [rbp+19Ch]
  wchar_t *v264; // [rsp+2B0h] [rbp+1A0h]
  int v265; // [rsp+2B8h] [rbp+1A8h]
  int v266; // [rsp+2BCh] [rbp+1ACh]
  __int64 v267; // [rsp+2C0h] [rbp+1B0h]
  int v268; // [rsp+2C8h] [rbp+1B8h]
  int v269; // [rsp+2CCh] [rbp+1BCh]
  char v270; // [rsp+2D0h] [rbp+1C0h] BYREF
  __int64 v271; // [rsp+490h] [rbp+380h]
  __int64 v272; // [rsp+498h] [rbp+388h]
  int v273; // [rsp+4A0h] [rbp+390h] BYREF
  __int16 v274; // [rsp+4A4h] [rbp+394h]
  int v275; // [rsp+4A6h] [rbp+396h]
  char v276; // [rsp+4AAh] [rbp+39Ah]
  char v277; // [rsp+4ABh] [rbp+39Bh]
  __int16 v278; // [rsp+4E0h] [rbp+3D0h] BYREF
  unsigned __int16 v279; // [rsp+4E2h] [rbp+3D2h] BYREF
  int v280; // [rsp+4E4h] [rbp+3D4h]
  void *Source; // [rsp+4E8h] [rbp+3D8h]
  struct PageComprInfo *v282; // [rsp+4F0h] [rbp+3E0h]
  _BYTE v283[24]; // [rsp+4F8h] [rbp+3E8h]
  int v284; // [rsp+510h] [rbp+400h]
  unsigned int v285; // [rsp+514h] [rbp+404h]
  _OWORD v286[7]; // [rsp+518h] [rbp+408h] BYREF
  __int64 v287; // [rsp+588h] [rbp+478h]
  wchar_t v288[24]; // [rsp+590h] [rbp+480h] BYREF
  wchar_t v289[24]; // [rsp+5C0h] [rbp+4B0h] BYREF
  unsigned __int8 Destination[8096]; // [rsp+5F0h] [rbp+4E0h] BYREF

  v245 = -2;
  v209 = a3;
  v226 = a1;
  v186[0] = 5;
  SETLSFromTlsMaybeNull = 0;
  v187 = 0;
  v188 = 0;
  v189 = 0;
  v212 = 0;
  v238[0] = &HoBtAccess::`vftable';
  v239 = 0;
  v240 = 0;
  v241 = -1;
  v243 = 0x80000000;
  v242 = 0;
  PhysicalColumnAttribute::Init((PhysicalColumnAttribute *)v244, a5, a4, 0, 0);
  v8 = UtilDbccGetCheckXDES(*((_WORD *)a2 + 1));
  PrimaryPRU = UtilDbccGetPrimaryPRU(HIWORD(*(_DWORD *)a2));
  v10 = *((_DWORD *)a2 + 1);
  v11 = *((unsigned __int16 *)a2 + 4);
  if ( !(_WORD)v11
    || !PrimaryPRU
    || (unsigned __int16)v11 > *(_WORD *)(*((_QWORD *)PrimaryPRU + 212) + 116LL)
    || (_mm_lfence(), (FCB = FileMgr::GetFCB(*((_QWORD *)PrimaryPRU + 212), v11, 1)) == 0)
    || *(_DWORD *)(FCB + 128) <= v10 )
  {
    ex_raise(25, 0, 25, 0);
  }
  AutoSystemXact::Begin((AutoSystemXact *)&v212, L"SetNullColumn", 26, v8);
  v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*v212)[35])(v212, *((_QWORD *)v8 + 6));
  v235 = (XDES *)v13;
  LockTimeout = UtilDbccGetLockTimeout();
  GetHoBtLockInternal(v8, *((_QWORD *)a1 + 1), v238, v186, &v234, 0, 0, 1, LockTimeout, 1, 0, 0);
  LOBYTE(v185[0]) = 0;
  XDES::LogHoBtLock(v8, v234, v186[0], 0, *(_DWORD *)v185);
  v15 = *((_WORD *)a2 + 4);
  v200 = *((_DWORD *)a2 + 1);
  v201 = v15;
  v16 = *(_QWORD *)(v13 + 48);
  v237 = 0;
  if ( CommonGlobalState::m_CollectingStatistics && byte_10317ABE6 >= 0 )
  {
    v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( !*(_QWORD *)v17
      || (v18 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v17 + 56LL)) == 0
      || !CSessionTraceFlags::CheckSessionTraceInternal(v18, 0x337u) )
    {
      v19 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v19 )
        SETLSFromTlsMaybeNull = *(struct SEInternalTLS **)(v19 + 96);
    }
  }
  v20 = *(_QWORD **)(v16 + 1832);
  v21 = 4;
  v22 = 2;
  while ( 1 )
  {
    v208 = 0;
    if ( !v187 )
      goto LABEL_38;
    if ( (*((_WORD *)v187 + 49) & 0x400) != 0 && (__int16)v189 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v187);
      goto LABEL_38;
    }
    v23 = (__int16)v189;
    v24 = v187;
    if ( (*((_WORD *)v187 + 49) & 8) != 0 )
    {
      if ( (__int16)v189 == 3 )
      {
        v23 = 4;
LABEL_23:
        if ( (*((_DWORD *)v187 + 25) & 8) != 0 )
        {
          v25 = *((_QWORD *)v187 + 18);
          if ( v25 )
          {
            if ( *(_QWORD *)(v25 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v25 + 1880), v187, v23);
            }
          }
        }
        goto LABEL_27;
      }
      if ( (__int16)v189 >= 2 )
        goto LABEL_23;
    }
LABEL_27:
    if ( byte_10317ABE5 < 0
      && (*((_DWORD *)v24 + 25) & 8) != 0
      && (int)v23 >= 3
      && (*((_DWORD *)v24 + 25) & 0xC0000000) != 0x40000000
      && *(_QWORD *)v24
      && VirtualProtect(*(LPVOID *)v24, 0x2000u, 2u, &flOldProtect) )
    {
      _InterlockedAnd((volatile signed __int32 *)v24 + 25, 0x3FFFFFFFu);
      _InterlockedOr((volatile signed __int32 *)v24 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal((char *)v24 + 152, v23);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v24, 0, v23);
    v189 &= 0xFFFF0000;
    v187 = 0;
LABEL_38:
    if ( !*(_QWORD *)(v16 + 1832) )
      goto LABEL_62;
    PageRef::CatchupPageRedos((PageRef *)&v187, (const struct PageId *)&v200, (struct RecoveryUnit *)v16);
    if ( !v187 )
      goto LABEL_62;
    if ( (*((_WORD *)v187 + 49) & 0x400) != 0 && (__int16)v189 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v187);
      goto LABEL_62;
    }
    v26 = (__int16)v189;
    v27 = v187;
    if ( (*((_WORD *)v187 + 49) & 8) != 0 )
    {
      if ( (__int16)v189 == 3 )
      {
        v26 = 4;
LABEL_47:
        if ( (*((_DWORD *)v187 + 25) & 8) != 0 )
        {
          v28 = *((_QWORD *)v187 + 18);
          if ( v28 )
          {
            if ( *(_QWORD *)(v28 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v28 + 1880), v187, v26);
            }
          }
        }
        goto LABEL_51;
      }
      if ( (__int16)v189 >= 2 )
        goto LABEL_47;
    }
LABEL_51:
    if ( byte_10317ABE5 < 0
      && (*((_DWORD *)v27 + 25) & 8) != 0
      && (int)v26 >= 3
      && (*((_DWORD *)v27 + 25) & 0xC0000000) != 0x40000000
      && *(_QWORD *)v27
      && VirtualProtect(*(LPVOID *)v27, 0x2000u, 2u, &v232) )
    {
      _InterlockedAnd((volatile signed __int32 *)v27 + 25, 0x3FFFFFFFu);
      _InterlockedOr((volatile signed __int32 *)v27 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal((char *)v27 + 152, v26);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
      BUF::TraceLatchAcquireRelease(v27, 0, v26);
    v189 &= 0xFFFF0000;
    v187 = 0;
LABEL_62:
    RecoveryUnit::PrePageUpdateHint((RecoveryUnit *)v16, (const struct PageId *)&v200);
    *(_DWORD *)v185 = 4;
    v29 = (BUF *)BPool::Get(qword_10317B628, v16, &v200, &v208, *(_QWORD *)v185, &v236);
    v187 = v29;
    v30 = v189 & 0xFFFF0000 | 4;
    v189 = v30;
    if ( SETLSFromTlsMaybeNull )
    {
      v31 = *(_QWORD *)v29;
      v32 = *((_DWORD *)SETLSFromTlsMaybeNull + 320) & 0xF;
      if ( *((_QWORD *)SETLSFromTlsMaybeNull + v32 + 161) != v31 )
      {
        *((_QWORD *)SETLSFromTlsMaybeNull + v32 + 161) = v31;
        ++*((_QWORD *)SETLSFromTlsMaybeNull + 160);
        v30 = v189;
      }
    }
    v33 = v30 & 0xFFFFFF | (((v208 >> 3) & 1) << 24);
    v189 = v33;
    v190 = v190 & 0xFFFFFF00 | (v208 >> 4) & 1;
    if ( v20 )
    {
      if ( SETLSFromTlsMaybeNull )
      {
        if ( SETLSFromTlsMaybeNull == *(struct SEInternalTLS **)(v16 + 7224) )
        {
          ++v20[2917];
          if ( (_DWORD)v237 )
          {
            ++v20[2918];
            v20[2919] += v236;
            if ( v33 >= 0x1000000 )
            {
              ++v20[2920];
              v20[2921] += v236;
            }
          }
        }
      }
    }
    IsRbIoDb = RecoveryUnit::IsRbIoDb((RecoveryUnit *)v16);
    v202 = 9;
    if ( !IsRbIoDb || !*(_BYTE *)(v16 + 8272) || !v200 || v200 == 9 && v201 == 1 )
      goto LABEL_163;
    v36 = *(_QWORD *)v187;
    if ( !*(_WORD *)(*(_QWORD *)v187 + 36LL) )
    {
LABEL_85:
      v213 = *(_QWORD *)(v36 + 40);
      v214 = *(_WORD *)(v36 + 48);
      goto LABEL_86;
    }
    v37 = *(_BYTE *)(v36 + 1);
    if ( v37 == 11 )
    {
      if ( *(_DWORD *)(v36 + 24) == 99 )
        goto LABEL_83;
    }
    else if ( v37 == 8 )
    {
      goto LABEL_82;
    }
    if ( v37 != 9 )
      goto LABEL_85;
LABEL_82:
    if ( *(_DWORD *)(v36 + 24) != 99 )
      goto LABEL_85;
LABEL_83:
    v216 = *(_DWORD *)(v36 + 32);
    v217 = *(_WORD *)(v36 + 36);
    if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v216, v35) )
      goto LABEL_85;
    PageHeader::GetIcxLsn(v36, &v213);
LABEL_86:
    v38 = *(_DWORD *)(v16 + 8456);
    do
    {
      v39 = v38 & 0xFFFFFFFE;
      v206 = *(LSN *)(v16 + 8444);
      v207 = *(_DWORD *)(v16 + 8452);
      _InterlockedOr(v184, 0);
      v38 = *(_DWORD *)(v16 + 8456);
    }
    while ( v39 != v38 );
    if ( v206.LowPart >= (unsigned int)v213
      && (v206.LowPart != (_DWORD)v213
       || v206.HighPart >= HIDWORD(v213) && (v206.HighPart != HIDWORD(v213) || (unsigned __int16)v207 >= v214)) )
    {
      goto LABEL_163;
    }
    if ( !*(_BYTE *)(v16 + 27336)
      && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL)
                   + 96LL) != *(_QWORD *)(v16 + 8480)
      && !RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v16) )
    {
      break;
    }
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL)
                   + 96LL) == *(_QWORD *)(v16 + 8480)
      || RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v16) )
    {
      goto LABEL_163;
    }
    if ( !SETLSFromTlsMaybeNull )
      SETLSFromTlsMaybeNull = GetSETLSFromTlsMaybeNull();
    v41 = v187;
    v42 = *(_QWORD *)v187;
    if ( !*(_WORD *)(*(_QWORD *)v187 + 36LL) )
      goto LABEL_110;
    v43 = *(unsigned __int8 *)(v42 + 1);
    if ( (_BYTE)v43 != 11 )
    {
      if ( (_BYTE)v43 != 8 )
      {
LABEL_105:
        if ( (_BYTE)v43 != 9 )
          goto LABEL_110;
      }
      if ( *(_DWORD *)(v42 + 24) != 99 )
        goto LABEL_110;
      goto LABEL_107;
    }
    if ( *(_DWORD *)(v42 + 24) != 99 )
      goto LABEL_105;
LABEL_107:
    v218 = *(_DWORD *)(v42 + 32);
    v219 = *(_WORD *)(v42 + 36);
    if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v218, v43) )
    {
      PageHeader::GetIcxLsn(v42, &v222);
      v41 = v187;
      goto LABEL_111;
    }
    v41 = v187;
LABEL_110:
    v222 = *(_QWORD *)(v42 + 40);
    v223 = *(_WORD *)(v42 + 48);
LABEL_111:
    if ( !v41 )
      goto LABEL_134;
    if ( (*((_WORD *)v41 + 49) & 0x400) != 0 && (__int16)v189 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v187);
      goto LABEL_134;
    }
    v44 = (__int16)v189;
    v45 = v187;
    if ( (*((_WORD *)v41 + 49) & 8) != 0 )
    {
      if ( (__int16)v189 == 3 )
      {
        v44 = 4;
LABEL_119:
        if ( (*((_DWORD *)v187 + 25) & 8) != 0 )
        {
          v46 = *((_QWORD *)v187 + 18);
          if ( v46 )
          {
            if ( *(_QWORD *)(v46 + 1880) )
            {
              _mm_lfence();
              DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v46 + 1880), v187, v44);
            }
          }
        }
        goto LABEL_123;
      }
      if ( (__int16)v189 >= 2 )
        goto LABEL_119;
    }
LABEL_123:
    if ( byte_10317ABE5 < 0
      && (*((_DWORD *)v45 + 25) & 8) != 0
      && (int)v44 >= 3
      && (*((_DWORD *)v45 + 25) & 0xC0000000) != 0x40000000
      && *(_QWORD *)v45
      && VirtualProtect(*(LPVOID *)v45, 0x2000u, 2u, &v233) )
    {
      _InterlockedAnd((volatile signed __int32 *)v45 + 25, 0x3FFFFFFFu);
      _InterlockedOr((volatile signed __int32 *)v45 + 25, 0x40000000u);
    }
    LatchBase::ReleaseInternal((char *)v45 + 152, v44);
    if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
    {
      if ( (byte_10317AD4F & 2) != 0 )
        BUF::TraceLatchAcquireRelease(v45, 0, v44);
    }
    v189 &= 0xFFFF0000;
    v187 = 0;
LABEL_134:
    v227 = v222;
    v228 = v223;
    *(_QWORD *)v185 = 0;
    RecoveryMgr::WaitForRedoLsnToCatchUp(*(_QWORD *)(v16 + 1832), &v227, 4);
  }
  v47 = *(_DWORD *)(v16 + 8456);
  do
  {
    v48 = v47 & 0xFFFFFFFE;
    v49 = *(LSN *)(v16 + 8444);
    v206 = v49;
    v207 = *(_DWORD *)(v16 + 8452);
    _InterlockedOr(v184, 0);
    v47 = *(_DWORD *)(v16 + 8456);
  }
  while ( v48 != v47 );
  v229 = v49;
  v50 = v207;
  v230 = v207;
  v51 = *(_QWORD *)v187;
  if ( !*(_WORD *)(*(_QWORD *)v187 + 36LL) )
    goto LABEL_146;
  v52 = *(_BYTE *)(v51 + 1);
  if ( v52 != 11 )
  {
    if ( v52 == 8 )
      goto LABEL_143;
    goto LABEL_142;
  }
  if ( *(_DWORD *)(v51 + 24) != 99 )
  {
LABEL_142:
    if ( v52 != 9 )
    {
LABEL_146:
      v210 = *(LSN *)(v51 + 40);
      v53 = *(_WORD *)(v51 + 48);
      v211 = v53;
      goto LABEL_147;
    }
LABEL_143:
    if ( *(_DWORD *)(v51 + 24) == 99 )
      goto LABEL_144;
    goto LABEL_146;
  }
LABEL_144:
  v220 = *(_DWORD *)(v51 + 32);
  v221 = *(_WORD *)(v51 + 36);
  if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v220, v40) )
    goto LABEL_146;
  PageHeader::GetIcxLsn(v51, &v210);
  v53 = v211;
LABEL_147:
  if ( v206.LowPart >= v210.LowPart
    && (v206.LowPart != v210.LowPart
     || v206.HighPart >= (unsigned int)v210.HighPart && (v206.HighPart != v210.HighPart || v50 >= v53)) )
  {
LABEL_163:
    v55 = 0;
    goto LABEL_164;
  }
  LSN::FormatAsHexString(&v210, v288, &v203);
  LSN::FormatAsHexString(&v229, v289, &v203);
  v55 = 0;
  if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
  {
    v247 = 393216;
    v248 = 0;
    v249 = &v252;
    v250 = &v270;
    v271 = 0;
    v251 = 0;
    v272 = 0;
    v252 = &v273;
    v253 = 52;
    v254 = 5;
    v255 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
    v256 = 16;
    v257 = 5;
    v258 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
    v259 = 16;
    v260 = 6;
    v261 = 0;
    v262 = 0;
    v263 = 7;
    v264 = 0;
    v265 = 0;
    v266 = 8;
    v267 = 0;
    v268 = 0;
    v269 = 9;
    v273 = *(unsigned __int16 *)(v16 + 1720);
    v274 = v201;
    v275 = v200;
    v276 = -1;
    v277 = *(_BYTE *)(*(_QWORD *)v187 + 1LL);
    v255 = (GUID *)(v54 + 596);
    v258 = (GUID *)(v54 + 580);
    v56 = -1;
    do
      ++v56;
    while ( v288[v56] );
    v261 = v288;
    v262 = 2 * v56;
    v57 = -1;
    do
      ++v57;
    while ( v289[v57] );
    v264 = v289;
    v265 = 2 * v57;
    v215 = 0;
    v58 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v54, &v215);
    v59 = (int *)v58;
    if ( v58 )
    {
      v60 = -1;
      do
        ++v60;
      while ( *(_WORD *)(v58 + 2 * v60) );
      v61 = 2 * v60;
    }
    else
    {
      v61 = 0;
    }
    v62 = v249;
    v249[10] = v59;
    *((_DWORD *)v62 + 22) = v61;
    *((_DWORD *)v62 + 23) = 9;
    XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v246);
  }
LABEL_164:
  v63 = *(_QWORD *)v187;
  v64 = v209;
  if ( v209 >= (unsigned int)*(unsigned __int16 *)(*(_QWORD *)v187 + 22LL) )
    goto LABEL_566;
  v65 = (_WORD *)(v63 + 2 * (4095LL - v209));
  if ( !*v65 )
    goto LABEL_565;
  v191 = -1;
  v194 = 0;
  v193 = 0;
  v198 = 0;
  *(_QWORD *)((char *)&v199 + 2) = 0;
  v195 = 0;
  v278 = -1;
  Source = 0;
  v280 = 0;
  *(_QWORD *)&v283[6] = 0;
  *(_QWORD *)&v283[16] = 0;
  v282 = 0;
  v67 = UtilDbccSetObjectStatus(v226);
  v203 = v67;
  if ( (v67 & 1) != 0 )
  {
    if ( UtilDbccGetContext() )
      v68 = (__int64)UtilDbccGetContext() + 16;
    else
      v68 = 4;
    *(_DWORD *)v68 |= 2u;
    ex_raise(89, 67, 16, 158);
  }
  v285 = v64;
  v69 = 15;
  if ( *(char *)(v63 + 2) >= 0 )
  {
    v70 = 0;
    goto LABEL_220;
  }
  v71 = (unsigned __int8 *)(v63 + 96);
  _mm_prefetch((const char *)(v63 + 96), 0);
  if ( !v278 || (v70 = v282) == 0 )
  {
    v287 = 0;
    v286[0] = 0;
    v286[1] = 0xFFFFu;
    memset(&v286[2], 0, 80);
    v70 = (struct PageComprInfo *)v286;
  }
  if ( !*(_WORD *)(v63 + 36) )
    goto LABEL_185;
  v72 = *(_BYTE *)(v63 + 1);
  if ( v72 != 11 )
  {
    if ( v72 == 8 )
      goto LABEL_182;
LABEL_181:
    if ( v72 == 9 )
    {
LABEL_182:
      if ( *(_DWORD *)(v63 + 24) == 99 )
        goto LABEL_183;
    }
LABEL_185:
    v224 = *(_QWORD *)(v63 + 40);
    v73 = *(_WORD *)(v63 + 48);
    goto LABEL_186;
  }
  if ( *(_DWORD *)(v63 + 24) != 99 )
    goto LABEL_181;
LABEL_183:
  v204 = *(_DWORD *)(v63 + 32);
  v205 = *(_WORD *)(v63 + 36);
  if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v204, v66) )
    goto LABEL_185;
  PageHeader::GetIcxLsn(v63, &v224);
  v73 = v225;
LABEL_186:
  *(_QWORD *)v70 = v71;
  v74 = HIDWORD(v224);
  *((_DWORD *)v70 + 24) = v224;
  *((_DWORD *)v70 + 25) = v74;
  *((_WORD *)v70 + 52) = v73;
  *((_DWORD *)v70 + 27) = *(_DWORD *)(v63 + 32);
  *((_WORD *)v70 + 56) = *(_WORD *)(v63 + 36);
  *((_WORD *)v70 + 57) = 0;
  v75 = 3LL * *v71;
  v204 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v71);
  v76 = word_102883984[v75];
  *((_WORD *)v70 + 8) = -1;
  *((_QWORD *)v70 + 3) = 0;
  *((_DWORD *)v70 + 5) = 0;
  *(_QWORD *)((char *)v70 + 46) = 0;
  *((_QWORD *)v70 + 7) = 0;
  *((_QWORD *)v70 + 4) = 0;
  *((_QWORD *)v70 + 9) = 0;
  *((_QWORD *)v70 + 10) = 0;
  *((_WORD *)v70 + 44) = 0;
  if ( (**(_BYTE **)v70 & 2) != 0 )
  {
    v77 = &v71[v76];
    if ( (v71[v76] & 1) != 0 )
    {
      *((_WORD *)v70 + 8) = 1;
      *((_QWORD *)v70 + 3) = v77;
      v78 = *v77;
      switch ( *v77 & 0x1C )
      {
        case 0:
        case 0xC:
        case 0x10:
        case 0x14:
        case 0x18:
        case 0x1C:
          if ( (v77[1] & 0x80u) != 0 )
          {
            v81 = *(_WORD *)(v77 + 1);
            *((_WORD *)v70 + 9) = v81;
            v79 = 3;
            v80 = HIBYTE(v81) | ((v81 & 0x7F) << 8);
          }
          else
          {
            v79 = 2;
            v80 = v77[1];
          }
          *((_WORD *)v70 + 9) = v80;
          *((_WORD *)v70 + 20) = v79;
          v82 = *((unsigned __int16 *)v70 + 9);
          *((_WORD *)v70 + 22) = v79 + ((v82 + 1) >> 1);
          if ( v82 > 0x1E )
            *((_WORD *)v70 + 21) = (int)(v82 - 1) / 30;
          else
            *((_WORD *)v70 + 21) = 0;
          *((_DWORD *)v70 + 5) = 0;
          *((_DWORD *)v70 + 16) = 0;
          *((_QWORD *)v70 + 7) = 0;
          *((_QWORD *)v70 + 4) = 0;
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
          *((_QWORD *)v70 + 7) = 0;
          *((_QWORD *)v70 + 4) = 0;
          break;
        case 4:
          if ( (v78 & 0x1C) != 4 || (v83 = 1, (v78 & 2) == 0) )
            v83 = 0;
          if ( v83 )
          {
            *((_DWORD *)v70 + 16) = 0;
            v84 = 1;
            v85 = 15;
          }
          else
          {
            v84 = 0;
            v85 = 1;
          }
          *((_QWORD *)v70 + 5) = 0;
          *((_WORD *)v70 + 9) = 0;
          *((_QWORD *)v70 + 6) = 0;
          *((_QWORD *)v70 + 4) = 0;
          *((_QWORD *)v70 + 7) = 0;
          *((_QWORD *)v70 + 3) = v77;
          *((_DWORD *)v70 + 5) = v85;
          *((_DWORD *)v70 + 16) = v84;
          *((_QWORD *)v70 + 7) = 0;
          *((_QWORD *)v70 + 4) = 0;
          break;
        case 8:
          *((_QWORD *)v70 + 5) = 0;
          *((_WORD *)v70 + 9) = 0;
          *((_QWORD *)v70 + 6) = 0;
          *((_QWORD *)v70 + 4) = 0;
          *((_QWORD *)v70 + 7) = 0;
          *((_QWORD *)v70 + 3) = v77;
          *((_DWORD *)v70 + 5) = 9;
          *((_DWORD *)v70 + 16) = 0;
          *((_QWORD *)v70 + 7) = 0;
          *((_QWORD *)v70 + 4) = 0;
          break;
      }
    }
    else
    {
      *((_WORD *)v70 + 8) = 0;
      *((_QWORD *)v70 + 3) = v77;
      *((_DWORD *)v70 + 5) = 0;
      *(_DWORD *)((char *)v70 + 54) = 0;
      switch ( *v77 & 0xE )
      {
        case 0:
        case 2:
        case 8:
        case 0xC:
          v55 = *((unsigned __int16 *)v77 + 1);
          if ( (unsigned int)(v55 - 1) > 0x1F9D )
            RaiseInconsistencyError(&v71[v76], 6);
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
          v55 = 9;
          break;
        case 6:
        case 0xA:
          break;
        case 0xE:
          v55 = 1;
          break;
      }
      *((_DWORD *)v70 + 8) = v55;
      *(_QWORD *)((char *)v70 + 46) = 0;
    }
  }
  if ( (**(_BYTE **)v70 & 4) != 0 )
  {
    if ( HIWORD(v204) )
      v86 = &v71[*(unsigned __int16 *)&v71[2 * SHIWORD(v204) + 1]];
    else
      v86 = &v71[v76];
    *((_QWORD *)v70 + 9) = v86;
    v87 = *(_WORD *)v86;
    *((_QWORD *)v70 + 10) = v86 + 2;
    *((_WORD *)v70 + 44) = 2 * (v87 + 1);
  }
  v88 = (PageComprInfoCache *)*((_QWORD *)v70 + 1);
  if ( v88 )
    PageComprInfoCache::Init(v88, v70);
  v67 = v203;
  v22 = 2;
LABEL_220:
  v89 = *(unsigned __int16 *)(v63 + 14);
  v90 = (unsigned __int16 *)(v63 + (unsigned __int16)*v65);
  v117 = (*(_BYTE *)v90 & 1) == 0;
  Source = v90;
  if ( v117 )
  {
    v278 = 0;
    v69 = 0;
    v280 = 0;
    *(_DWORD *)&v283[14] = 0;
    switch ( *(_BYTE *)v90 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v89 = v90[1];
        if ( (unsigned int)(v89 - 1) > 0x1F9D )
        {
          RaiseInconsistencyError(v90, 6);
          goto LABEL_245;
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
LABEL_245:
        v69 = v280;
        break;
      case 4:
        v89 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v89 = 1;
        break;
    }
    LODWORD(v282) = v89;
    if ( v63 )
      v93 = v63 + 0x2000;
    else
      v93 = 0;
    *(_QWORD *)&v283[6] = v93;
    LODWORD(v70) = v89;
  }
  else
  {
    v278 = 1;
    v91 = *(_BYTE *)v90;
    switch ( *(_BYTE *)v90 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( *((char *)v90 + 1) < 0 )
        {
          v92 = HIBYTE(*(unsigned __int16 *)((char *)v90 + 1)) | ((*(unsigned __int16 *)((char *)v90 + 1) & 0x7F) << 8);
          v279 = v92;
          *(_WORD *)v283 = 3;
          v22 = 3;
        }
        else
        {
          v92 = *((unsigned __int8 *)v90 + 1);
          v279 = v92;
          *(_WORD *)v283 = 2;
        }
        *(_WORD *)&v283[4] = v22 + (((unsigned int)v92 + 1) >> 1);
        if ( v92 > 0x1Eu )
          *(_WORD *)&v283[2] = (v92 - 1) / 30;
        else
          *(_WORD *)&v283[2] = 0;
        v69 = 0;
        v280 = 0;
        v284 = 0;
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
        v69 = v280;
        break;
      case 4:
        if ( (v91 & 0x1C) == 4 && (v91 & 2) != 0 )
        {
          *(_QWORD *)v283 = 0;
          v279 = 0;
          *(_QWORD *)&v283[8] = 0;
          v280 = 15;
          v284 = 1;
        }
        else
        {
          *(_QWORD *)v283 = 0;
          v279 = 0;
          *(_QWORD *)&v283[8] = 0;
          v69 = 1;
          v280 = 1;
          v284 = 0;
        }
        break;
      case 8:
        *(_QWORD *)v283 = 0;
        v279 = 0;
        *(_QWORD *)&v283[8] = 0;
        v69 = 9;
        v280 = 9;
        v284 = 0;
        break;
    }
    if ( v63 )
      *(_QWORD *)&v283[16] = v63 + 0x2000;
    else
      *(_QWORD *)&v283[16] = 0;
    v282 = v70;
  }
  if ( v278 )
  {
    if ( !v69 )
    {
      CDRecord::Resize((CDRecord *)&v279);
      v69 = v280;
    }
    if ( v69 >= 9 )
      goto LABEL_349;
    if ( (*(_BYTE *)Source & 0x1C) != 0 )
    {
      v117 = (*(_BYTE *)Source & 0x1C) == 12;
LABEL_347:
      if ( !v117 )
        goto LABEL_349;
    }
LABEL_348:
    v118 = 9;
  }
  else
  {
    if ( !v69 )
    {
      v279 = 0;
      HIDWORD(v282) = (_DWORD)v70;
      v69 = (unsigned int)v70;
      if ( (*(_BYTE *)Source & 0x10) != 0 )
      {
        v69 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v70) + 7) >> 3) + (_DWORD)v70 + 2;
        HIDWORD(v282) = v69;
      }
      if ( (*(_BYTE *)Source & 0x20) != 0 )
      {
        v94 = (char *)Source + v69;
        *(_WORD *)&v283[4] = *v94;
        if ( !*(_WORD *)&v283[4] )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(Source, 3);
        }
        *(_DWORD *)v283 = HIDWORD(v282) + 2 * (*(unsigned __int16 *)&v283[4] + 1);
        if ( *(_DWORD *)v283 > 0x1F9Eu )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(Source, 4);
        }
        v69 = v94[*(unsigned __int16 *)&v283[4]] & 0x7FFF;
        v280 = v69;
        if ( *(_DWORD *)v283 > v69 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v99 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v99 )
            {
              v100 = *(_QWORD *)(v99 + 96);
              if ( v100 )
              {
                if ( *(_BYTE *)(v100 + 1177) )
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
          v69 = v280;
        }
        while ( (__int16)v94[*(unsigned __int16 *)&v283[4]] < 0 )
        {
          v101 = (char *)Source + HIDWORD(v282);
          if ( *(unsigned __int16 *)&v283[4] == 1 )
            v102 = *(_DWORD *)v283;
          else
            v102 = *(_WORD *)&v101[2 * *(unsigned __int16 *)&v283[4] - 2] & 0x7FFF;
          if ( v102 < *(_DWORD *)v283 || (*(_WORD *)&v101[2 * *(unsigned __int16 *)&v283[4]] & 0x7FFFu) < v102 )
          {
            RaiseInconsistencyError(Source, 7);
            v69 = v280;
          }
          if ( v102 < *(_DWORD *)v283 || v102 > v69 )
            goto LABEL_339;
          v103 = *(_WORD *)((char *)Source + v102);
          if ( v103 == 5 )
          {
            v279 |= 2u;
            --*(_WORD *)&v283[4];
            *(_WORD *)&v283[18] = v102;
            v104 = (char *)Source + (unsigned __int16)v102;
            v105 = *((_WORD *)v104 + 1);
            if ( (v105 & 0x4000) != 0 )
              v106 = (v105 ^ *(_WORD *)&v283[20]) & 0x3800 ^ *(_WORD *)&v283[20];
            else
              v106 = *(_WORD *)&v283[20] & 0xC7FF;
            *(_WORD *)&v283[20] = v106;
            *(_WORD *)&v283[20] = v106 ^ (*((_WORD *)v104 + 1) ^ v106) & 0x7FF;
            break;
          }
          if ( v103 >= 0x400u )
          {
            v279 |= 1u;
            if ( --*(_WORD *)&v283[4] )
              continue;
          }
          break;
        }
      }
      else
      {
        v280 = v69;
        *(_WORD *)&v283[4] = 0;
        *(_DWORD *)v283 = v69;
      }
      if ( (*(_BYTE *)Source & 0x40) != 0 )
      {
        *(_DWORD *)&v283[14] = v69;
        v280 = v69 + 14;
        VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v279);
        v108 = HIDWORD(*(_QWORD *)VersioningInfo);
        v109 = HIWORD(*(_QWORD *)VersioningInfo);
        v110 = 0;
        if ( (((__int16)v109 ^ ((unsigned int)(__int16)v109 >> 1)) & 0x2000) != 0 )
        {
          v111 = v109 & 0xDFFF;
          if ( (v109 & 0x4000) != 0 )
            v111 = v109 | 0x2000;
          LOWORD(v109) = v111;
        }
        if ( (_WORD)v109 == 0xFFFC )
          v110 = (unsigned __int16)v108 >> 5;
        v69 = v110 + v280;
        v280 += v110;
      }
      else
      {
        *(_DWORD *)&v283[14] = 0;
      }
      if ( *(_QWORD *)&v283[6] && *(_QWORD *)&v283[6] < (unsigned __int64)Source + v69 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v112 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v112 )
          {
            v113 = *(_QWORD *)(v112 + 96);
            if ( v113 )
            {
              if ( *(_BYTE *)(v113 + 1177) )
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
        v69 = v280;
      }
      if ( v69 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v114 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v114 )
          {
            v115 = *(_QWORD *)(v114 + 96);
            if ( v115 )
            {
              if ( *(_BYTE *)(v115 + 1177) )
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
        v69 = v280;
      }
    }
LABEL_339:
    if ( v69 < 9 )
    {
      v116 = *(_BYTE *)Source & 0xE;
      if ( v116 )
      {
        v117 = v116 == 12;
        goto LABEL_347;
      }
      goto LABEL_348;
    }
LABEL_349:
    v118 = v69;
  }
  v191 = v278;
  if ( v278 )
  {
    if ( v282 && *(_QWORD *)v282 )
    {
      Record::DecompressRec((Record *)&v191, Destination, 0x1F9Eu, (const struct Record *)&v278);
    }
    else
    {
      CDRecord::CopyNewRec((CDRecord *)&v192, Destination, 0x1F9Eu, (const struct CDRecord *)&v279);
      v151 = v282;
      if ( !v278 )
        v151 = 0;
      v195 = v151;
    }
  }
  else
  {
    if ( !v69 )
    {
      v279 = 0;
      v69 = (unsigned int)v282;
      HIDWORD(v282) = (_DWORD)v282;
      if ( (*(_BYTE *)Source & 0x10) != 0 )
      {
        v69 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v282) + 7) >> 3) + (_DWORD)v282 + 2;
        HIDWORD(v282) = v69;
      }
      if ( (*(_BYTE *)Source & 0x20) != 0 )
      {
        v119 = (char *)Source + v69;
        *(_WORD *)&v283[4] = *v119;
        if ( !*(_WORD *)&v283[4] )
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
          RaiseInconsistencyError(Source, 3);
        }
        *(_DWORD *)v283 = HIDWORD(v282) + 2 * (*(unsigned __int16 *)&v283[4] + 1);
        if ( *(_DWORD *)v283 > 0x1F9Eu )
        {
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(Source, 4);
        }
        v69 = v119[*(unsigned __int16 *)&v283[4]] & 0x7FFF;
        v280 = v69;
        if ( *(_DWORD *)v283 > v69 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v124 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v124 )
            {
              v125 = *(_QWORD *)(v124 + 96);
              if ( v125 )
              {
                if ( *(_BYTE *)(v125 + 1177) )
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
          v69 = v280;
        }
        while ( (__int16)v119[*(unsigned __int16 *)&v283[4]] < 0 )
        {
          v126 = (char *)Source + HIDWORD(v282);
          if ( *(unsigned __int16 *)&v283[4] == 1 )
            v127 = *(_DWORD *)v283;
          else
            v127 = *(_WORD *)&v126[2 * *(unsigned __int16 *)&v283[4] - 2] & 0x7FFF;
          if ( v127 < *(_DWORD *)v283 || (*(_WORD *)&v126[2 * *(unsigned __int16 *)&v283[4]] & 0x7FFFu) < v127 )
          {
            RaiseInconsistencyError(Source, 7);
            v69 = v280;
          }
          if ( v127 < *(_DWORD *)v283 || v127 > v69 )
            goto LABEL_438;
          v128 = *(_WORD *)((char *)Source + v127);
          if ( v128 == 5 )
          {
            v279 |= 2u;
            --*(_WORD *)&v283[4];
            *(_WORD *)&v283[18] = v127;
            v129 = (char *)Source + (unsigned __int16)v127;
            v130 = *((_WORD *)v129 + 1);
            if ( (v130 & 0x4000) != 0 )
              v131 = (*(_WORD *)&v283[20] ^ v130) & 0x3800 ^ *(_WORD *)&v283[20];
            else
              v131 = *(_WORD *)&v283[20] & 0xC7FF;
            *(_WORD *)&v283[20] = v131;
            *(_WORD *)&v283[20] = v131 ^ (*((_WORD *)v129 + 1) ^ v131) & 0x7FF;
            break;
          }
          if ( v128 >= 0x400u )
          {
            v279 |= 1u;
            if ( --*(_WORD *)&v283[4] )
              continue;
          }
          break;
        }
      }
      else
      {
        v280 = v69;
        *(_WORD *)&v283[4] = 0;
        *(_DWORD *)v283 = v69;
      }
      if ( (*(_BYTE *)Source & 0x40) != 0 )
      {
        *(_DWORD *)&v283[14] = v69;
        v280 = v69 + 14;
        v132 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v279);
        v133 = HIDWORD(*(_QWORD *)v132);
        v134 = HIWORD(*(_QWORD *)v132);
        v135 = 0;
        if ( (((__int16)v134 ^ ((unsigned int)(__int16)v134 >> 1)) & 0x2000) != 0 )
        {
          v136 = v134 & 0xDFFF;
          if ( (v134 & 0x4000) != 0 )
            v136 = v134 | 0x2000;
          LOWORD(v134) = v136;
        }
        if ( (_WORD)v134 == 0xFFFC )
          v135 = (unsigned __int16)v133 >> 5;
        v69 = v135 + v280;
        v280 += v135;
      }
      else
      {
        *(_DWORD *)&v283[14] = 0;
      }
      if ( *(_QWORD *)&v283[6] && *(_QWORD *)&v283[6] < (unsigned __int64)Source + v69 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v137 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v137 )
          {
            v138 = *(_QWORD *)(v137 + 96);
            if ( v138 )
            {
              if ( *(_BYTE *)(v138 + 1177) )
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
        v69 = v280;
      }
      if ( v69 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v139 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v139 )
          {
            v140 = *(_QWORD *)(v139 + 96);
            if ( v140 )
            {
              if ( *(_BYTE *)(v140 + 1177) )
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
        v69 = v280;
      }
    }
LABEL_438:
    if ( v69 >= 9 || (v141 = *(_BYTE *)Source & 0xE) != 0 && v141 != 12 )
      v142 = v69;
    else
      v142 = 9;
    v195 = v282;
    v192 = v279;
    v193 = v69;
    v197 = *(_WORD *)&v283[4];
    v196 = *(_DWORD *)v283;
    LODWORD(v199) = *(_DWORD *)&v283[14];
    memcpy_s(Destination, 0x1F9Eu, Source, v142);
    v194 = Destination;
    if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v192) )
    {
      v143 = v194;
      v144 = &v194[HIDWORD(v195)];
      v145 = *(unsigned __int16 *)v144 - 1;
      if ( (v192 & 1) == 0 )
        v145 = *(unsigned __int16 *)v144;
      if ( v145 == 1 )
        v146 = v196;
      else
        v146 = *(_WORD *)&v144[2 * v145 - 2] & 0x7FFF;
      v147 = *(_WORD *)&v144[2 * v145] & 0x7FFF;
      if ( v146 < v196 || v147 < v146 )
      {
        RaiseInconsistencyError(v194, 7);
        v143 = v194;
      }
      WORD2(v199) = v146;
      v148 = &v143[(unsigned __int16)v146];
      v149 = *((_WORD *)v148 + 1);
      if ( (v149 & 0x4000) != 0 )
        v150 = (WORD3(v199) ^ v149) & 0x3800 ^ WORD3(v199);
      else
        v150 = WORD3(v199) & 0xC7FF;
      WORD3(v199) = v150;
      WORD3(v199) = v150 ^ (*((_WORD *)v148 + 1) ^ v150) & 0x7FF;
    }
  }
  if ( v191 )
    CDRecord::SetNull((CDRecord *)&v192, (const struct PhysicalColumnAttribute *)v244);
  else
    FixedVarRecord::SetNull((FixedVarRecord *)&v192, (const struct PhysicalColumnAttribute *)v244, 0, 1);
  if ( v191 )
  {
    v178 = v193;
    if ( !v193 )
    {
      CDRecord::Resize((CDRecord *)&v192);
      v178 = v193;
    }
    if ( v178 >= 9 || (*v194 & 0x1C) != 0 && (*v194 & 0x1C) != 0xC )
      v202 = v178;
    else
      v202 = 9;
  }
  else
  {
    v152 = v193;
    if ( !v193 )
    {
      v192 = 0;
      v152 = (unsigned int)v195;
      HIDWORD(v195) = (_DWORD)v195;
      if ( (*v194 & 0x10) != 0 )
      {
        v152 = (((unsigned int)*(unsigned __int16 *)&v194[(unsigned int)v195] + 7) >> 3) + (_DWORD)v195 + 2;
        HIDWORD(v195) = v152;
      }
      if ( (*v194 & 0x20) != 0 )
      {
        v153 = &v194[v152];
        v154 = *(_WORD *)v153;
        v197 = v154;
        if ( !v154 )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v194, 3);
          v154 = v197;
        }
        v157 = HIDWORD(v195) + 2 + 2 * v154;
        v196 = v157;
        if ( v157 > 0x1F9E )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v194, 4);
          v154 = v197;
          v157 = v196;
        }
        v152 = *(_WORD *)&v153[2 * v154] & 0x7FFF;
        v193 = v152;
        if ( v157 > v152 )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v194, 4);
          v154 = v197;
          v157 = v196;
          v152 = v193;
        }
        while ( *(__int16 *)&v153[2 * v154] < 0 )
        {
          v162 = &v194[HIDWORD(v195)];
          if ( v154 == 1 )
            v163 = v157;
          else
            v163 = *(_WORD *)&v162[2 * v154 - 2] & 0x7FFF;
          if ( v163 < v157 || (*(_WORD *)&v162[2 * v154] & 0x7FFFu) < v163 )
          {
            RaiseInconsistencyError(v194, 7);
            v154 = v197;
            v157 = v196;
            v152 = v193;
          }
          if ( v163 < v157 || v163 > v152 )
            goto LABEL_553;
          v164 = *(_WORD *)&v194[v163];
          if ( v164 == 5 )
          {
            v192 |= 2u;
            v197 = v154 - 1;
            WORD2(v199) = v163;
            v165 = &v194[(unsigned __int16)v163];
            v166 = *((_WORD *)v165 + 1);
            if ( (v166 & 0x4000) != 0 )
              v167 = (v166 ^ WORD3(v199)) & 0x3800 ^ WORD3(v199);
            else
              v167 = WORD3(v199) & 0xC7FF;
            WORD3(v199) = v167;
            WORD3(v199) = v167 ^ (*((_WORD *)v165 + 1) ^ v167) & 0x7FF;
            break;
          }
          if ( v164 >= 0x400u )
          {
            v192 |= 1u;
            v117 = v154-- == 1;
            v197 = v154;
            if ( !v117 )
              continue;
          }
          break;
        }
      }
      else
      {
        v193 = v152;
        v197 = 0;
        v196 = v152;
      }
      if ( (*v194 & 0x40) != 0 )
      {
        LODWORD(v199) = v152;
        v193 = v152 + 14;
        v168 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v192);
        v169 = HIDWORD(*(_QWORD *)v168);
        v170 = HIWORD(*(_QWORD *)v168);
        v171 = 0;
        if ( (((__int16)v170 ^ ((unsigned int)(__int16)v170 >> 1)) & 0x2000) != 0 )
        {
          v172 = v170 & 0xDFFF;
          if ( (v170 & 0x4000) != 0 )
            v172 = v170 | 0x2000;
          LOWORD(v170) = v172;
        }
        if ( (_WORD)v170 == 0xFFFC )
          v171 = (unsigned __int16)v169 >> 5;
        v152 = v171 + v193;
        v193 += v171;
      }
      else
      {
        LODWORD(v199) = 0;
      }
      if ( v198 && v198 < (unsigned __int64)&v194[v152] )
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
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v194, 18);
        v152 = v193;
      }
      if ( v152 - 1 > 0x3F3B )
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
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v194, 5);
        v152 = v193;
      }
    }
LABEL_553:
    if ( v152 >= 9 || (v177 = *v194 & 0xE) != 0 && v177 != 12 )
      v202 = v152;
  }
  v179 = v235;
  (*(void (__fastcall **)(XDES *))(*(_QWORD *)v235 + 624LL))(v235);
  PageRef::ModifyRow(
    &v187,
    *((_QWORD *)v226 + 1),
    (const struct DbccCombinedId *)((char *)v226 + 16),
    v209,
    0,
    v118,
    v202,
    v194,
    v67,
    0,
    v179,
    0,
    0,
    0,
    0,
    0,
    0,
    0);
LABEL_565:
  v21 = 4;
LABEL_566:
  v180 = v212;
  ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v212)[54])(v212);
  (**v180)(v180, 1);
  v212 = 0;
  if ( !UtilDbccGetContext()
    || !*((_QWORD *)UtilDbccGetContext() + 6)
    || (v181 = *(_DWORD *)(*((_QWORD *)UtilDbccGetContext() + 6) + 12LL), v181 > 0xD)
    || (v182 = 9792, !_bittest(&v182, v181))
    || (v183 = *((_QWORD *)UtilDbccGetContext() + 20)) == 0
    || !*(_QWORD *)(v183 + 8) )
  {
    if ( UtilDbccGetContext() )
      v21 = (__int64)UtilDbccGetContext() + 16;
    *(_DWORD *)v21 |= 2u;
    ex_raise(89, 67, 16, 159);
  }
  v238[0] = &HoBtAccess::`vftable';
  if ( (_DWORD)v239 == 3 )
  {
    LODWORD(v239) = 0;
    LatchBase::ReleaseInternal(v238[1] + 1328LL, 1);
  }
  PageRef::~PageRef((PageRef *)&v187);
}

```

## disassembly

```asm
0x101ea2520  push    rbp
0x101ea2522  push    rsi
0x101ea2523  push    rdi
0x101ea2524  push    r12
0x101ea2526  push    r13
0x101ea2528  push    r14
0x101ea252a  push    r15
0x101ea252c  lea     rbp, [rsp-2490h]
0x101ea2534  mov     eax, 25A0h
0x101ea2539  call    _alloca_probe
0x101ea253e  sub     rsp, rax
0x101ea2541  mov     [rbp+24C0h+var_23A0], 0FFFFFFFFFFFFFFFEh
0x101ea254c  mov     [rsp+25D0h+arg_18], rbx
0x101ea2554  mov     rax, cs:__security_cookie
0x101ea255b  xor     rax, rsp
0x101ea255e  mov     [rbp+24C0h+var_40], rax
0x101ea2565  mov     r10d, r9d
0x101ea2568  mov     [rbp+24C0h+var_24C0], r8d
0x101ea256c  mov     rbx, rdx
0x101ea256f  mov     r14, rcx
0x101ea2572  mov     [rbp+24C0h+var_2450], rcx
0x101ea2576  mov     [rbp+24C0h+var_2540], 5
0x101ea257a  xor     r15d, r15d
0x101ea257d  mov     [rbp+24C0h+var_2538], r15
0x101ea2581  mov     [rbp+24C0h+var_2530], r15b
0x101ea2585  mov     eax, [rbp+24C0h+var_252C]
0x101ea2588  and     eax, 0FFFF0000h
0x101ea258d  mov     [rbp+24C0h+var_252C], eax
0x101ea2590  and     eax, 0FF00FFFFh
0x101ea2595  mov     [rbp+24C0h+var_252C], eax
0x101ea2598  mov     [rbp+24C0h+var_252C], r15d
0x101ea259c  mov     [rbp+24C0h+var_24A8], r15
0x101ea25a0  lea     rax, ??_7IByteStoreBuilder@@6B@; const IByteStoreBuilder::`vftable'
0x101ea25a7  mov     [rbp+24C0h+var_23F0], rax
0x101ea25ae  lea     rax, ??_7HoBtAccess@@6B@; const HoBtAccess::`vftable'
0x101ea25b5  mov     [rbp+24C0h+var_23F0], rax
0x101ea25bc  mov     [rbp+24C0h+var_23E0], r15
0x101ea25c3  mov     [rbp+24C0h+var_23D8], r15d
0x101ea25ca  mov     rax, 0FFFFFFFFFFFFFFFFh
0x101ea25d1  mov     [rbp+24C0h+var_23C8], eax
0x101ea25d7  mov     [rbp+24C0h+var_23B8], 80000000h
0x101ea25e1  mov     [rbp+24C0h+var_23C0], r15b
0x101ea25e8  movsx   edx, [rbp+24C0h+arg_20]; int
0x101ea25ef  mov     dword ptr [rsp+25D0h+var_25B0], r15d; __int16
0x101ea25f4  xor     r9d, r9d; unsigned __int8
0x101ea25f7  movzx   r8d, r10w; unsigned __int16
0x101ea25fb  lea     rcx, [rbp+24C0h+var_23B0]; this
0x101ea2602  call    ?Init@PhysicalColumnAttribute@@QEAAXHGEH@Z; PhysicalColumnAttribute::Init(int,ushort,uchar,int)
0x101ea2607  movzx   ecx, word ptr [rbx+2]; unsigned __int16
0x101ea260b  call    ?UtilDbccGetCheckXDES@@YAPEAVXDES@@G@Z; UtilDbccGetCheckXDES(ushort)
0x101ea2610  mov     rdi, rax
0x101ea2613  mov     ecx, [rbx]
0x101ea2615  shr     ecx, 10h; unsigned __int16
0x101ea2618  call    ?UtilDbccGetPrimaryPRU@@YAPEAVRecoveryUnit@@G@Z; UtilDbccGetPrimaryPRU(ushort)
0x101ea261d  mov     esi, [rbx+4]
0x101ea2620  movzx   edx, word ptr [rbx+8]
0x101ea2624  lea     r12d, [r15+1]
0x101ea2628  test    dx, dx
0x101ea262b  jz      short loc_101EA265E
0x101ea262d  test    rax, rax
0x101ea2630  jz      short loc_101EA265E
0x101ea2632  mov     rcx, [rax+6A0h]
0x101ea2639  cmp     dx, [rcx+74h]
0x101ea263d  ja      short loc_101EA265E
0x101ea263f  lfence
0x101ea2642  mov     r8d, r12d
0x101ea2645  mov     rcx, [rax+6A0h]
0x101ea264c  call    ?GetFCB@FileMgr@@QEBAPEAVFCB@@JW4LookupFailureMode@@@Z; FileMgr::GetFCB(long,LookupFailureMode)
0x101ea2651  test    rax, rax
0x101ea2654  jz      short loc_101EA265E
0x101ea2656  cmp     [rax+80h], esi
0x101ea265c  ja      short loc_101EA2671
0x101ea265e  xor     r9d, r9d
0x101ea2661  xor     edx, edx
0x101ea2663  mov     ecx, 19h
0x101ea2668  mov     r8d, ecx
0x101ea266b  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101ea2671  mov     r9, rdi; struct XDES *
0x101ea2674  mov     r8d, 1Ah; int
0x101ea267a  lea     rdx, aSetnullcolumn; "SetNullColumn"
0x101ea2681  lea     rcx, [rbp+24C0h+var_24A8]; this
0x101ea2685  call    ?Begin@AutoSystemXact@@QEAAXPEB_WHPEAVXDES@@@Z; AutoSystemXact::Begin(wchar_t const *,int,XDES *)
0x101ea268a  mov     rcx, [rbp+24C0h+var_24A8]
0x101ea268e  mov     rax, [rcx]
0x101ea2691  mov     rdx, [rdi+30h]
0x101ea2695  call    qword ptr [rax+118h]
0x101ea269b  mov     rsi, rax
0x101ea269e  mov     [rbp+24C0h+var_2410], rax
0x101ea26a5  call    ?UtilDbccGetLockTimeout@@YA?BKXZ; UtilDbccGetLockTimeout(void)
0x101ea26aa  mov     dword ptr [rsp+25D0h+var_2578], r15d
0x101ea26af  mov     dword ptr [rsp+25D0h+var_2580], r15d
0x101ea26b4  mov     [rsp+25D0h+var_2588], r12d
0x101ea26b9  mov     [rsp+25D0h+var_2590], eax
0x101ea26bd  mov     dword ptr [rsp+25D0h+var_2598], r12d
0x101ea26c2  mov     [rsp+25D0h+var_25A0], r15d
0x101ea26c7  mov     [rsp+25D0h+var_25A8], r15
0x101ea26cc  lea     rax, [rbp+24C0h+var_2418]
0x101ea26d3  mov     qword ptr [rsp+25D0h+var_25B0], rax
0x101ea26d8  lea     r9, [rbp+24C0h+var_2540]
0x101ea26dc  lea     r8, [rbp+24C0h+var_23F0]
0x101ea26e3  mov     rdx, [r14+8]
0x101ea26e7  mov     rcx, rdi
0x101ea26ea  call    ?GetHoBtLockInternal@@YA?AW4LCK_RESULT@@PEAVXDES@@_KAEAVHoBtAccess@@AEAW4LCK_MODE@@AEA_KPEAVCacheLockResourceId@@W4LongLockFlags@@W4LogLockingFlags@@KW4LockWaitOption@@W4InstantLockFlags@@W4ImmediateLockFlags@@@Z; GetHoBtLockInternal(XDES *,unsigned __int64,HoBtAccess &,LCK_MODE &,unsigned __int64 &,CacheLockResourceId *,LongLockFlags,LogLockingFlags,ulong,LockWaitOption,InstantLockFlags,ImmediateLockFlags)
0x101ea26ef  mov     byte ptr [rsp+25D0h+var_25B0], 0
0x101ea26f4  xor     r9d, r9d
0x101ea26f7  movzx   r8d, [rbp+24C0h+var_2540]
0x101ea26fc  mov     rdx, [rbp+24C0h+var_2418]
0x101ea2703  mov     rcx, rdi
0x101ea2706  call    ?LogHoBtLock@XDES@@QEAAX_KW4LCK_MODE@@_N_N@Z; XDES::LogHoBtLock(unsigned __int64,LCK_MODE,bool,bool)
0x101ea270b  mov     eax, [rbx+4]
0x101ea270e  movzx   ecx, word ptr [rbx+8]
0x101ea2712  mov     [rbp+24C0h+var_24E8], eax
0x101ea2715  mov     [rbp+24C0h+var_24E4], cx
0x101ea2719  mov     rbx, [rsi+30h]
0x101ea271d  mov     [rbp+24C0h+var_2404], r15
0x101ea2724  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x101ea272b  cmp     byte ptr [rax], 0
0x101ea272e  jz      short loc_101EA27A7
0x101ea2730  test    cs:byte_10317ABE6, 80h
0x101ea2737  jnz     short loc_101EA27A7
0x101ea2739  mov     r8, gs:58h
0x101ea2742  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101ea2749  mov     ecx, [rax]
0x101ea274b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101ea2752  mov     edx, [rax]
0x101ea2754  add     rdx, [r8+rcx*8]
0x101ea2758  mov     rax, [rdx]
0x101ea275b  test    rax, rax
0x101ea275e  jz      short loc_101EA277B
0x101ea2760  mov     rax, [rax+38h]
0x101ea2764  mov     rcx, [rax]
0x101ea2767  test    rcx, rcx
0x101ea276a  jz      short loc_101EA277B
0x101ea276c  mov     edx, 337h
0x101ea2771  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101ea2777  test    eax, eax
0x101ea2779  jnz     short loc_101EA27A7
0x101ea277b  mov     r8, gs:58h
0x101ea2784  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101ea278b  mov     ecx, [rax]
0x101ea278d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101ea2794  mov     edx, [rax]
0x101ea2796  add     rdx, [r8+rcx*8]
0x101ea279a  mov     rax, [rdx+8]
0x101ea279e  test    rax, rax
0x101ea27a1  jz      short loc_101EA27A7
0x101ea27a3  mov     r15, [rax+60h]
0x101ea27a7  mov     r14, [rbx+728h]
0x101ea27ae  mov     edi, 400h
0x101ea27b3  mov     r13d, 4
0x101ea27b9  lea     r12d, [r13-2]
0x101ea27bd  mov     r10d, 2000h
0x101ea27c3  mov     [rbp+24C0h+var_24C4], 0
0x101ea27ca  mov     rcx, [rbp+24C0h+var_2538]
0x101ea27ce  test    rcx, rcx
0x101ea27d1  jz      loc_101EA28ED
0x101ea27d7  movzx   eax, word ptr [rcx+62h]
0x101ea27db  movsx   edx, word ptr [rbp+24C0h+var_252C]
0x101ea27df  test    di, ax
0x101ea27e2  jz      short loc_101EA27F7
0x101ea27e4  cmp     edx, 3
0x101ea27e7  jl      short loc_101EA27F7
0x101ea27e9  lea     rcx, [rbp+24C0h+var_2538]; this
0x101ea27ed  call    ?UnfixLatchOnly@PageRef@@IEAAXXZ; PageRef::UnfixLatchOnly(void)
0x101ea27f2  jmp     loc_101EA28ED
0x101ea27f7  mov     esi, edx
0x101ea27f9  mov     rdi, [rbp+24C0h+var_2538]
0x101ea27fd  movzx   eax, word ptr [rcx+62h]
0x101ea2801  shr     al, 3
0x101ea2804  test    al, 1
0x101ea2806  jz      short loc_101EA2859
0x101ea2808  cmp     edx, 3
0x101ea280b  jnz     short loc_101EA2812
0x101ea280d  mov     esi, r13d
0x101ea2810  jmp     short loc_101EA2817
0x101ea2812  cmp     edx, r12d
0x101ea2815  jl      short loc_101EA2859
0x101ea2817  mov     rax, [rbp+24C0h+var_2538]
0x101ea281b  mov     ecx, [rax+64h]
0x101ea281e  test    cl, 8
0x101ea2821  jz      short loc_101EA2859
0x101ea2823  mov     rax, [rbp+24C0h+var_2538]
0x101ea2827  mov     rcx, [rax+90h]
0x101ea282e  test    rcx, rcx
0x101ea2831  jz      short loc_101EA2859
0x101ea2833  cmp     qword ptr [rcx+758h], 0
0x101ea283b  jz      short loc_101EA2859
0x101ea283d  lfence
0x101ea2840  mov     r8d, esi
0x101ea2843  mov     rdx, [rbp+24C0h+var_2538]
0x101ea2847  mov     rcx, [rcx+758h]
0x101ea284e  call    ?OnReleasingBufLatch@DirtyPageMgr@@QEAAXPEAUBUF@@W4LATCH_TYPE@LatchBase@@@Z; DirtyPageMgr::OnReleasingBufLatch(BUF *,LatchBase::LATCH_TYPE)
0x101ea2853  mov     r10d, 2000h
0x101ea2859  test    cs:byte_10317ABE5, 80h
0x101ea2860  jz      short loc_101EA28AC
0x101ea2862  mov     eax, [rdi+64h]
0x101ea2865  test    al, 8
0x101ea2867  jz      short loc_101EA28AC
0x101ea2869  cmp     esi, 3
0x101ea286c  jl      short loc_101EA28AC
0x101ea286e  mov     eax, [rdi+64h]
0x101ea2871  and     eax, 0C0000000h
0x101ea2876  cmp     eax, 40000000h
0x101ea287b  jz      short loc_101EA28AC
0x101ea287d  mov     rcx, [rdi]; lpAddress
0x101ea2880  test    rcx, rcx
0x101ea2883  jz      short loc_101EA28AC
0x101ea2885  lea     r9, [rbp+24C0h+flOldProtect]; lpflOldProtect
0x101ea288c  mov     r8d, r12d; flNewProtect
0x101ea288f  mov     rdx, r10; dwSize
0x101ea2892  call    cs:__imp_VirtualProtect
0x101ea2898  test    eax, eax
0x101ea289a  jz      short loc_101EA28AC
0x101ea289c  lock and dword ptr [rdi+64h], 3FFFFFFFh
0x101ea28a4  lock or dword ptr [rdi+64h], 40000000h
0x101ea28ac  lea     rcx, [rdi+98h]
0x101ea28b3  mov     edx, esi
0x101ea28b5  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x101ea28ba  cmp     cs:?sm_acquireReleaseEnforcementExpensive@LatchBase@@0HA, 0; int LatchBase::sm_acquireReleaseEnforcementExpensive
0x101ea28c1  jz      short loc_101EA28D9
0x101ea28c3  test    cs:byte_10317AD4F, r12b
0x101ea28ca  jz      short loc_101EA28D9
0x101ea28cc  mov     r8d, esi
0x101ea28cf  xor     edx, edx
0x101ea28d1  mov     rcx, rdi
0x101ea28d4  call    ?TraceLatchAcquireRelease@BUF@@QEAAX_NW4LATCH_TYPE@LatchBase@@@Z; BUF::TraceLatchAcquireRelease(bool,LatchBase::LATCH_TYPE)
0x101ea28d9  and     [rbp+24C0h+var_252C], 0FFFF0000h
0x101ea28e0  mov     [rbp+24C0h+var_2538], 0
0x101ea28e8  mov     edi, 400h
0x101ea28ed  cmp     qword ptr [rbx+728h], 0
0x101ea28f5  jz      loc_101EA2A25
0x101ea28fb  mov     r8, rbx; struct RecoveryUnit *
0x101ea28fe  lea     rdx, [rbp+24C0h+var_24E8]; struct PageId *
0x101ea2902  lea     rcx, [rbp+24C0h+var_2538]; this
0x101ea2906  call    ?CatchupPageRedos@PageRef@@QEAAXAEBVPageId@@PEAVRecoveryUnit@@@Z; PageRef::CatchupPageRedos(PageId const &,RecoveryUnit *)
0x101ea290b  mov     rcx, [rbp+24C0h+var_2538]
0x101ea290f  test    rcx, rcx
0x101ea2912  jz      loc_101EA2A25
0x101ea2918  movzx   eax, word ptr [rcx+62h]
0x101ea291c  movsx   edx, word ptr [rbp+24C0h+var_252C]
0x101ea2920  test    di, ax
0x101ea2923  jz      short loc_101EA2938
0x101ea2925  cmp     edx, 3
0x101ea2928  jl      short loc_101EA2938
0x101ea292a  lea     rcx, [rbp+24C0h+var_2538]; this
0x101ea292e  call    ?UnfixLatchOnly@PageRef@@IEAAXXZ; PageRef::UnfixLatchOnly(void)
0x101ea2933  jmp     loc_101EA2A25
0x101ea2938  mov     esi, edx
0x101ea293a  mov     rdi, [rbp+24C0h+var_2538]
0x101ea293e  movzx   eax, word ptr [rcx+62h]
0x101ea2942  shr     al, 3
0x101ea2945  test    al, 1
0x101ea2947  jz      short loc_101EA2994
0x101ea2949  cmp     edx, 3
0x101ea294c  jnz     short loc_101EA2953
0x101ea294e  mov     esi, r13d
0x101ea2951  jmp     short loc_101EA2958
0x101ea2953  cmp     edx, r12d
0x101ea2956  jl      short loc_101EA2994
0x101ea2958  mov     rax, [rbp+24C0h+var_2538]
0x101ea295c  mov     ecx, [rax+64h]
0x101ea295f  test    cl, 8
0x101ea2962  jz      short loc_101EA2994
0x101ea2964  mov     rax, [rbp+24C0h+var_2538]
0x101ea2968  mov     rcx, [rax+90h]
0x101ea296f  test    rcx, rcx
0x101ea2972  jz      short loc_101EA2994
0x101ea2974  cmp     qword ptr [rcx+758h], 0
0x101ea297c  jz      short loc_101EA2994
0x101ea297e  lfence
0x101ea2981  mov     r8d, esi
0x101ea2984  mov     rdx, [rbp+24C0h+var_2538]
0x101ea2988  mov     rcx, [rcx+758h]
0x101ea298f  call    ?OnReleasingBufLatch@DirtyPageMgr@@QEAAXPEAUBUF@@W4LATCH_TYPE@LatchBase@@@Z; DirtyPageMgr::OnReleasingBufLatch(BUF *,LatchBase::LATCH_TYPE)
0x101ea2994  test    cs:byte_10317ABE5, 80h
0x101ea299b  jz      short loc_101EA29E9
0x101ea299d  mov     eax, [rdi+64h]
0x101ea29a0  test    al, 8
0x101ea29a2  jz      short loc_101EA29E9
0x101ea29a4  cmp     esi, 3
0x101ea29a7  jl      short loc_101EA29E9
0x101ea29a9  mov     eax, [rdi+64h]
0x101ea29ac  and     eax, 0C0000000h
0x101ea29b1  cmp     eax, 40000000h
0x101ea29b6  jz      short loc_101EA29E9
0x101ea29b8  mov     rcx, [rdi]; lpAddress
0x101ea29bb  test    rcx, rcx
0x101ea29be  jz      short loc_101EA29E9
0x101ea29c0  lea     r9, [rbp+24C0h+var_2424]; lpflOldProtect
0x101ea29c7  mov     r8d, r12d; flNewProtect
0x101ea29ca  mov     edx, 2000h; dwSize
0x101ea29cf  call    cs:__imp_VirtualProtect
0x101ea29d5  test    eax, eax
0x101ea29d7  jz      short loc_101EA29E9
0x101ea29d9  lock and dword ptr [rdi+64h], 3FFFFFFFh
0x101ea29e1  lock or dword ptr [rdi+64h], 40000000h
0x101ea29e9  lea     rcx, [rdi+98h]
0x101ea29f0  mov     edx, esi
0x101ea29f2  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x101ea29f7  cmp     cs:?sm_acquireReleaseEnforcementExpensive@LatchBase@@0HA, 0; int LatchBase::sm_acquireReleaseEnforcementExpensive
  ... truncated ...
```
