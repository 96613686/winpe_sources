# CWiaItem::WriteMultipleToDAIT(ulong,tagPROPSPEC const * const,tagPROPVARIANT const * const,ulong,ulong &)

- ea: `0x18006b040`
- end: `0x18006c966`
- name: `?WriteMultipleToDAIT@CWiaItem@@QEAAJKQEBUtagPROPSPEC@@QEBUtagPROPVARIANT@@KAEAK@Z`
- size: `6438`
- prototype: `__int64 __usercall@<rax>(CWiaItem *__hidden this@<rcx>, unsigned int@<edx>, const struct tagPROPSPEC *const@<r8>, const struct tagPROPVARIANT *const@<r9>, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b2c0`
- `0x18005e2e8`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18001901c`
- `0x18001bbc4`
- `0x18001e364`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180033878`
- `0x180034558`
- `0x180034658`
- `0x18005d1e0`
- `0x180062710`
- `0x180062bfc`
- `0x1800657a8`
- `0x1800659c8`
- `0x18006a200`
- `0x18006b040`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18006bbdc`
- `ole32!PropVariantClear` at `0x18006c00a`
- `ole32!PropVariantClear` at `0x18006c811`
- `ole32!PropVariantClear` at `0x18006c81b`
- `ole32!PropVariantClear` at `0x18006c895`
- `ole32!PropVariantClear` at `0x18006bbdc`
- `ole32!PropVariantClear` at `0x18006c00a`
- `ole32!PropVariantClear` at `0x18006c811`
- `ole32!PropVariantClear` at `0x18006c81b`
- `ole32!PropVariantClear` at `0x18006c895`
- `ole32!CoTaskMemAlloc` at `0x18006ba3c`
- `ole32!CoTaskMemAlloc` at `0x18006c64c`
- `ole32!CoTaskMemAlloc` at `0x18006ba3c`
- `ole32!CoTaskMemAlloc` at `0x18006c64c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006b887`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006b887`

## string_xrefs

- `0x18006c0b0`: `failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)`
- `0x18006c0df`: `failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)`
- `0x18006c8ef`: `failed to translate call to linked D-AIT item(s) (0x%X)`
- `0x18006c917`: `failed to translate call to linked D-AIT item(s) (0x%X)`
- `0x18006b647`: `failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)`
- `0x18006b66f`: `failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)`
- `0x18006b06f`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b1ca`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b1f8`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b269`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b297`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b304`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b373`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b3eb`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b467`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b495`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b4f0`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b51e`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b55d`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b58a`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b5d9`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b656`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b683`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b6c5`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b6f2`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b8d3`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006ba6f`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006baad`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bb6e`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bb9f`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bbcc`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bc19`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bc4b`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bc88`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bcc1`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bcf9`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bde6`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006be1a`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006be47`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006be71`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006be9f`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bf57`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bf99`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bfcd`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006bffa`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c03c`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c069`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c0c5`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c0f3`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c174`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c1e1`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c238`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c2b8`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c370`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c39d`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c3c4`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c3f1`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c418`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c446`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c530`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c5e7`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c69a`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c6f2`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c75a`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c7d4`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c801`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c8b4`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c8e1`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c8fe`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006c92b`: `CWiaItem::WriteMultipleToDAIT`
- `0x18006b0fa`: `called in non-compat mode (E_INVALIDARG)`
- `0x18006b11c`: `called in non-compat mode (E_INVALIDARG)`
- `0x18006bb90`: `ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)`
- `0x18006bbb6`: `ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)`
- `0x18006bfbe`: `ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)`
- `0x18006bfe6`: `ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)`
- `0x18006c165`: `WriteMultiple on root D-AIT item failed (0x%X)`
- `0x18006c18d`: `WriteMultiple on root D-AIT item failed (0x%X)`
- `0x18006be0b`: `ValidStg#IPropertyStorage::ReadMultiple(WIA_IPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)`
- `0x18006be33`: `ValidStg#IPropertyStorage::ReadMultiple(WIA_IPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)`
- `0x18006c2a9`: `WriteMultiple on #1 child D-AIT item failed (0x%X)`
- `0x18006c2d1`: `WriteMultiple on #1 child D-AIT item failed (0x%X)`
- `0x18006c361`: `WriteMultiple on #2 child D-AIT item failed (0x%X)`
- `0x18006c389`: `WriteMultiple on #2 child D-AIT item failed (0x%X)`
- `0x18006c8a5`: `cannot refresh WIA_IPA_FILENAME_EXTENSION (0x%X)`
- `0x18006c8cb`: `cannot refresh WIA_IPA_FILENAME_EXTENSION (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::WriteMultipleToDAIT(
        CWiaItem **this,
        unsigned int a2,
        const struct tagPROPSPEC *const a3,
        const struct tagPROPVARIANT *const a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned __int64 v7; // r14
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  int v22; // r15d
  struct tagPROPVARIANT *v23; // r12
  unsigned __int64 v24; // rax
  struct tagPROPSPEC *v25; // rax
  int RelatedDAITItem; // edi
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  int v32; // r8d
  unsigned int v33; // ebx
  struct tagPROPSPEC *v34; // rax
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  struct tagPROPSPEC *v40; // rax
  char *v41; // rbx
  void *v42; // rdx
  struct tagPROPVARIANT *v43; // rax
  char *v44; // rbx
  void *v45; // rdx
  struct tagPROPVARIANT *v46; // rax
  char *v47; // rbx
  void *v48; // rdx
  struct tagPROPVARIANT *v49; // rax
  char *v50; // rbx
  void *v51; // rdx
  void **v52; // rax
  void *v53; // rdx
  __int64 v54; // rcx
  CWiaItem *v55; // rax
  CWiaItem *v56; // rcx
  char *v57; // rbx
  void *v58; // rdx
  void **v59; // rax
  void *v60; // rdx
  __int64 v61; // rcx
  char *v62; // rbx
  void *v63; // rdx
  void **v64; // rax
  void *v65; // rdx
  __int64 v66; // rcx
  char *v67; // rbx
  void *v68; // rdx
  unsigned int *v69; // r15
  CWiaItem *v70; // rcx
  char *v71; // rbx
  void *v72; // rdx
  void **v73; // rax
  void *v74; // rdx
  __int64 v75; // rcx
  unsigned int v76; // r14d
  char *v77; // rbx
  void *v78; // rdx
  void **v79; // rax
  void *v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // rax
  const struct tagPROPSPEC *v83; // rcx
  __int64 v84; // r14
  __int64 v85; // rax
  bool v86; // zf
  struct tagPROPSPEC v87; // xmm0
  __int64 v88; // r9
  PROPID propid; // ebx
  int PropCompatCategory; // eax
  int v91; // ecx
  int v92; // ebx
  unsigned int *v93; // r12
  struct tagPROPSPEC *v94; // rcx
  struct tagPROPVARIANT *v95; // r15
  PROPID v96; // eax
  const struct tagPROPVARIANT *v97; // rcx
  const struct tagPROPVARIANT *v98; // r14
  char *v99; // rbx
  void *v100; // rdx
  void **v101; // rax
  void *v102; // rdx
  __int64 v103; // rcx
  int v104; // r9d
  BSTR *pbstrVal; // rcx
  __int64 v106; // rax
  GUID *v107; // rax
  char *v108; // rbx
  void *v109; // rdx
  char *v110; // rbx
  void *v111; // rdx
  CWiaItem *v112; // rax
  int v113; // ecx
  char *v114; // rbx
  void *v115; // rdx
  void **v116; // rax
  void *v117; // rdx
  __int64 v118; // rcx
  char *v119; // rbx
  void *v120; // rdx
  LONG v121; // edx
  char *v122; // rbx
  void *v123; // rdx
  void **v124; // rax
  void *v125; // rdx
  __int64 v126; // rcx
  int v127; // eax
  char *v128; // rbx
  void *v129; // rdx
  char *v130; // rbx
  void *v131; // rdx
  void **v132; // rax
  void *v133; // rdx
  __int64 v134; // rcx
  CWiaItem *v135; // rax
  int v136; // ecx
  char *v137; // rbx
  void *v138; // rdx
  void **v139; // rax
  void *v140; // rdx
  __int64 v141; // rcx
  char *v142; // rbx
  void *v143; // rdx
  PROPVARIANT *v144; // rcx
  char *v145; // rbx
  void *v146; // rdx
  void **v147; // rax
  void *v148; // rdx
  __int64 v149; // rcx
  CWiaItem *v150; // rax
  int v151; // ecx
  const struct tagPROPVARIANT *v152; // r12
  __int64 v153; // r14
  LONG lVal; // edx
  char *v155; // rbx
  void *v156; // rdx
  void **v157; // rax
  void *v158; // rdx
  __int64 v159; // rcx
  char *v160; // rbx
  void *v161; // rdx
  char *v162; // rbx
  void *v163; // rdx
  char *v164; // rbx
  void *v165; // rdx
  unsigned int v166; // r14d
  char *v167; // rbx
  void *v168; // rdx
  void **v169; // rax
  void *v170; // rdx
  __int64 v171; // rcx
  unsigned int v172; // ebx
  unsigned int v173; // r15d
  char *v174; // rbx
  void *v175; // rdx
  void **v176; // rax
  void *v177; // rdx
  __int64 v178; // rcx
  __int64 v179; // rbx
  char *v180; // rbx
  void *v181; // rdx
  char *v182; // rbx
  void *v183; // rdx
  char *v184; // rbx
  void *v185; // rdx
  __int64 v186; // rbx
  struct tagPROPVARIANT *v187; // r9
  struct tagPROPSPEC *v188; // r12
  unsigned int v189; // r15d
  char *v190; // rbx
  void *v191; // rdx
  void **v192; // rax
  void *v193; // rdx
  __int64 v194; // rcx
  char *v195; // rbx
  void *v196; // rdx
  void **v197; // rax
  void *v198; // rdx
  __int64 v199; // rcx
  char *v200; // rbx
  void *v201; // rdx
  struct tagPROPVARIANT *v202; // rbx
  struct tagPROPVARIANT *v203; // rbx
  struct tagPROPVARIANT *v204; // rbx
  char *v205; // rbx
  void *v206; // rdx
  void **v207; // rax
  void *v208; // rdx
  __int64 v209; // rcx
  int v210; // r15d
  CWiaItem *v211; // rax
  char *v212; // rbx
  void *v213; // rdx
  void **v214; // rax
  void *v215; // rdx
  __int64 v216; // rcx
  int v217; // ebx
  __int64 v218; // rcx
  int v219; // r14d
  GUID *v220; // rax
  struct CWiaItem *v221; // rcx
  char *v222; // rbx
  void *v223; // rdx
  char *v224; // rbx
  void *v225; // rdx
  char *v226; // rbx
  void *v227; // rdx
  char *v228; // rbx
  void *v229; // rdx
  char *v230; // rbx
  void *v231; // rdx
  char *v232; // rbx
  void *v233; // rdx
  void **v234; // rax
  void *v235; // rdx
  __int64 v236; // rcx
  unsigned int lpMem; // [rsp+28h] [rbp-E0h]
  unsigned int lpMema; // [rsp+28h] [rbp-E0h]
  unsigned int v240; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v241; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v242; // [rsp+40h] [rbp-C8h]
  struct tagPROPSPEC *v243; // [rsp+48h] [rbp-C0h]
  struct CWiaItem *v244; // [rsp+50h] [rbp-B8h]
  unsigned int v245[2]; // [rsp+58h] [rbp-B0h] BYREF
  struct tagPROPVARIANT *v246; // [rsp+60h] [rbp-A8h]
  struct tagPROPVARIANT *v247; // [rsp+68h] [rbp-A0h]
  struct tagPROPSPEC *v248; // [rsp+70h] [rbp-98h]
  struct CWiaItem *v249; // [rsp+78h] [rbp-90h] BYREF
  struct tagPROPSPEC v250; // [rsp+80h] [rbp-88h] BYREF
  int v251; // [rsp+90h] [rbp-78h]
  struct tagPROPVARIANT *v252; // [rsp+98h] [rbp-70h]
  struct tagPROPSPEC *v253; // [rsp+A0h] [rbp-68h]
  PROPVARIANT v254[6]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v255[24]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v256; // [rsp+F0h] [rbp-18h]
  PROPVARIANT v257[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v258; // [rsp+108h] [rbp+0h]
  BOOL v259; // [rsp+110h] [rbp+8h]
  __int128 v260; // [rsp+118h] [rbp+10h] BYREF
  OLECHAR *v261; // [rsp+128h] [rbp+20h]
  PROPVARIANT pvar[2]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v263; // [rsp+140h] [rbp+38h]
  struct tagPROPSPEC v264; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v265[120]; // [rsp+158h] [rbp+50h] BYREF
  unsigned int v266; // [rsp+218h] [rbp+110h] BYREF
  unsigned int v267; // [rsp+220h] [rbp+118h]
  const struct tagPROPSPEC *v268; // [rsp+228h] [rbp+120h]
  const struct tagPROPVARIANT *v269; // [rsp+230h] [rbp+128h]

  v269 = a4;
  v268 = a3;
  v267 = a2;
  v7 = a2;
  v8 = (char ***)WiaTrace_Trace("CWiaItem::WriteMultipleToDAIT");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v265, v9, v10, (char **)"CWiaItem::WriteMultipleToDAIT", lpMem, v8);
  if ( *((_QWORD *)this[26] + 8) )
  {
    if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)this) )
    {
      v17 = (char *)WiaTrace_TraceLog("called in non-compat mode (E_INVALIDARG)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v17);
      WiaTrcLib::Free((WiaTrcLib *)v17, v18);
      v19 = (void **)WiaTrace_Trace("called in non-compat mode (E_INVALIDARG)");
      WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v19);
      v16 = -2147024809;
      goto LABEL_222;
    }
    v22 = *((_DWORD *)this + 56);
    LODWORD(v242) = v22;
    v243 = 0;
    v252 = 0;
    v247 = 0;
    v259 = v22 == 1;
    v23 = 0;
    v246 = 0;
    v24 = 16 * v7;
    v245[1] = 0;
    v241 = 0;
    if ( !is_mul_ok(v7, 0x10u) )
      v24 = -1;
    v266 = 0;
    v25 = (struct tagPROPSPEC *)operator new[](v24);
    v253 = v25;
    if ( !v25 )
    {
      v248 = 0;
      RelatedDAITItem = -2147024882;
      v27 = (char *)WiaTrace_TraceLog("out of memory (1) (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v27);
      WiaTrcLib::Free((WiaTrcLib *)v27, v28);
      v29 = (void **)WiaTrace_Trace("out of memory (1) (0x%X)", -2147024882);
      WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v29);
      v33 = 8;
      v244 = 0;
      v240 = 8;
      goto LABEL_43;
    }
    memset_0(v25, 0, 16 * v7);
    v34 = (struct tagPROPSPEC *)operator new[](saturated_mul(v7, 0x10u));
    v248 = v34;
    if ( !v34 )
    {
      RelatedDAITItem = -2147024882;
      v35 = (char *)WiaTrace_TraceLog("out of memory (2) (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v35);
      WiaTrcLib::Free((WiaTrcLib *)v35, v36);
      v37 = (void **)WiaTrace_Trace("out of memory (2) (0x%X)", 2147942414LL);
LABEL_11:
      WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v37);
      v244 = 0;
LABEL_12:
      v33 = 8;
LABEL_41:
      v240 = v33;
      goto LABEL_42;
    }
    memset_0(v34, 0, 16 * v7);
    if ( v22 == 1 )
    {
      v40 = (struct tagPROPSPEC *)operator new[](saturated_mul(v7, 0x10u));
      v243 = v40;
      if ( !v40 )
      {
        RelatedDAITItem = -2147024882;
        v41 = (char *)WiaTrace_TraceLog("out of memory (3) (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v41);
        WiaTrcLib::Free((WiaTrcLib *)v41, v42);
        v37 = (void **)WiaTrace_Trace("out of memory (3) (0x%X)", 2147942414LL);
        goto LABEL_11;
      }
      memset_0(v40, 0, 16 * v7);
    }
    v43 = (struct tagPROPVARIANT *)operator new[](saturated_mul(v7, 0x18u));
    v252 = v43;
    if ( !v43 )
    {
      RelatedDAITItem = -2147024882;
      v44 = (char *)WiaTrace_TraceLog("out of memory (4) (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v44);
      WiaTrcLib::Free((WiaTrcLib *)v44, v45);
      v37 = (void **)WiaTrace_Trace("out of memory (4) (0x%X)", 2147942414LL);
      goto LABEL_11;
    }
    memset_0(v43, 0, 24 * v7);
    v46 = (struct tagPROPVARIANT *)operator new[](saturated_mul(v7, 0x18u));
    v247 = v46;
    if ( !v46 )
    {
      RelatedDAITItem = -2147024882;
      v47 = (char *)WiaTrace_TraceLog("out of memory (5) (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v47);
      WiaTrcLib::Free((WiaTrcLib *)v47, v48);
      v37 = (void **)WiaTrace_Trace("out of memory (5) (0x%X)", 2147942414LL);
      goto LABEL_11;
    }
    memset_0(v46, 0, 24 * v7);
    if ( v22 == 1 )
    {
      v49 = (struct tagPROPVARIANT *)operator new[](saturated_mul(v7, 0x18u));
      v246 = v49;
      v23 = v49;
      if ( !v49 )
      {
        RelatedDAITItem = -2147024882;
        v50 = (char *)WiaTrace_TraceLog("out of memory (6) (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v50);
        WiaTrcLib::Free((WiaTrcLib *)v50, v51);
        v52 = (void **)WiaTrace_Trace("out of memory (6) (0x%X)", -2147024882);
        WiaTrace_ProcessTrace_Ex(v54, v53, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v52);
        v244 = 0;
        goto LABEL_12;
      }
      memset_0(v49, 0, 24 * v7);
      v55 = this[26];
      v244 = 0;
      v249 = 0;
      v56 = (CWiaItem *)*((_QWORD *)v55 + 10);
      if ( !v56 )
      {
        RelatedDAITItem = -2147467261;
        v57 = (char *)WiaTrace_TraceLog("(legacy app) NULL D-AIT XP child item (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v57);
        WiaTrcLib::Free((WiaTrcLib *)v57, v58);
        v59 = (void **)WiaTrace_Trace("(legacy app) NULL D-AIT XP child item (0x%X)", 2147500035LL);
LABEL_26:
        WiaTrace_ProcessTrace_Ex(v61, v60, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v59);
        v33 = 8;
        v246 = v23;
        goto LABEL_41;
      }
      RelatedDAITItem = CWiaItem::FindRelatedDAITItem(v56, &v249, 1);
      if ( RelatedDAITItem < 0 )
      {
        v62 = (char *)WiaTrace_TraceLog("FindRelatedDAITItem failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v62);
        WiaTrcLib::Free((WiaTrcLib *)v62, v63);
        v64 = (void **)WiaTrace_Trace("FindRelatedDAITItem failed (0x%X)", RelatedDAITItem);
        WiaTrace_ProcessTrace_Ex(v66, v65, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v64);
        v33 = 8;
        v244 = v249;
        v246 = v23;
        goto LABEL_41;
      }
      v244 = v249;
      if ( !v249 )
      {
        RelatedDAITItem = -2147467261;
        v67 = (char *)WiaTrace_TraceLog("FindRelatedDAITItem returned NULL item (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v67);
        WiaTrcLib::Free((WiaTrcLib *)v67, v68);
        v59 = (void **)WiaTrace_Trace("FindRelatedDAITItem returned NULL item (0x%X)", 2147500035LL);
        goto LABEL_26;
      }
    }
    else
    {
      RelatedDAITItem = 0;
      v244 = 0;
    }
    v246 = v23;
    v33 = 8;
    v240 = 8;
    if ( v22 == 1 )
    {
      v69 = a6;
      v70 = this[26];
      v245[0] = *a6;
      RelatedDAITItem = CWiaItem::GetDocumentHandling(v70, v245, 0);
      if ( RelatedDAITItem >= 0 )
      {
        v76 = v245[0];
        if ( v245[0] == *v69 )
        {
          v76 = *v69;
        }
        else
        {
          RelatedDAITItem = CWiaItem::InitChildItemXPProps(this[26], 1);
          if ( RelatedDAITItem < 0 )
          {
            v77 = (char *)WiaTrace_TraceLog("failed to reinitialize the legacy child A-AIT item (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v77);
            WiaTrcLib::Free((WiaTrcLib *)v77, v78);
            v79 = (void **)WiaTrace_Trace("failed to reinitialize the legacy child A-AIT item (0x%X)", RelatedDAITItem);
            WiaTrace_ProcessTrace_Ex(v81, v80, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v79);
          }
          *v69 = v76;
        }
        v33 = 6 - ((v76 & 1) != 0);
        goto LABEL_41;
      }
      v71 = (char *)WiaTrace_TraceLog("failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v71);
      WiaTrcLib::Free((WiaTrcLib *)v71, v72);
      v73 = (void **)WiaTrace_Trace(
                       "failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)",
                       RelatedDAITItem);
      WiaTrace_ProcessTrace_Ex(v75, v74, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v73);
      v33 = 8;
    }
LABEL_42:
    LODWORD(v7) = v267;
LABEL_43:
    v251 = 0;
    LODWORD(v249) = 0;
    v261 = *(OLECHAR **)&WiaImgFmt_MEMORYBMP.Data1;
    v250 = 0;
    *(_QWORD *)&v260 = _mm_srli_si128((__m128i)WiaImgFmt_MEMORYBMP, 8).m128i_u64[0];
    if ( RelatedDAITItem >= 0 )
    {
      v82 = 0;
      while ( 1 )
      {
        v245[0] = v82;
        if ( (unsigned int)v82 >= (unsigned int)v7 )
          goto LABEL_146;
        v83 = v268;
        v84 = (unsigned int)v82;
        v85 = v82;
        v86 = v268[v85].ulKind == 0;
        v87 = v268[v85];
        v264 = v87;
        if ( v86 )
        {
          RelatedDAITItem = CWiaPropStg::GetPropIDFromName(this[27], &v264, &v250);
          if ( RelatedDAITItem < 0 )
          {
            v164 = (char *)WiaTrace_TraceLog("GetPropIDFromName failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v164);
            WiaTrcLib::Free((WiaTrcLib *)v164, v165);
            v132 = (void **)WiaTrace_Trace("GetPropIDFromName failed (0x%X)", RelatedDAITItem);
            goto LABEL_145;
          }
          v250.ulKind = 1;
        }
        else
        {
          v250 = v87;
        }
        v88 = v33;
        propid = v250.propid;
        memset(v254, 0, 32);
        PropCompatCategory = CWiaItem::GetPropCompatCategory(v83, v250.propid, v259, v88, v254);
        v32 = HIDWORD(v254[3]);
        v91 = v242;
        if ( propid == 3088 && (_DWORD)v242 == 1 )
        {
          if ( *((_QWORD *)this[8] + 11) )
            v32 = 0;
          v91 = v242;
        }
        if ( !PropCompatCategory || v32 )
        {
          if ( propid != 3088 )
            goto LABEL_143;
          if ( v91 != 1 )
          {
            if ( *((CWiaItem ***)this[26] + 11) != this )
            {
              RelatedDAITItem = -2147024809;
              v145 = (char *)WiaTrace_TraceLog("WIA_IPS_DOCUMENT_HANDLING_SELECT is not supported on this item (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v145);
              WiaTrcLib::Free((WiaTrcLib *)v145, v146);
              v147 = (void **)WiaTrace_Trace(
                                "WIA_IPS_DOCUMENT_HANDLING_SELECT is not supported on this item (0x%X)",
                                -2147024809);
              WiaTrace_ProcessTrace_Ex(v149, v148, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v147);
              goto LABEL_143;
            }
            v135 = this[27];
            memset(v255, 0, sizeof(v255));
            RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, struct tagPROPSPEC *, _BYTE *))(**((_QWORD **)v135 + 1) + 24LL))(
                                *((_QWORD *)v135 + 1),
                                1,
                                &v250,
                                v255);
            if ( RelatedDAITItem < 0 )
            {
              v142 = (char *)WiaTrace_TraceLog("ValidStg#IPropertyStorage::ReadMultiple(WIA_IPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v142);
              WiaTrcLib::Free((WiaTrcLib *)v142, v143);
              v139 = (void **)WiaTrace_Trace(
                                "ValidStg#IPropertyStorage::ReadMultiple(WIA_IPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)",
                                (unsigned int)RelatedDAITItem);
LABEL_127:
              WiaTrace_ProcessTrace_Ex(v141, v140, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v139);
            }
            else
            {
              if ( (*(_WORD *)v255 & 0x1000) != 0 )
                v136 = *(_DWORD *)(*(_QWORD *)&v255[16] + 4LL);
              else
                v136 = *(_DWORD *)&v255[8];
              if ( ((v269[v84].vt - 3) & 0xFFEF) != 0 || (v136 & v269[v84].lVal) != v269[v84].lVal )
              {
                RelatedDAITItem = -2147024809;
                v137 = (char *)WiaTrace_TraceLog("invalid value(s) requested for WIA_IPS_DOCUMENT_HANDLING_SELECT (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v137);
                WiaTrcLib::Free((WiaTrcLib *)v137, v138);
                v139 = (void **)WiaTrace_Trace(
                                  "invalid value(s) requested for WIA_IPS_DOCUMENT_HANDLING_SELECT (0x%X)",
                                  2147942487LL);
                goto LABEL_127;
              }
            }
            v144 = (PROPVARIANT *)v255;
LABEL_142:
            PropVariantClear(v144);
            goto LABEL_143;
          }
          v258 = 0;
          v150 = this[27];
          *(_OWORD *)v257 = 0;
          RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, struct tagPROPSPEC *, PROPVARIANT *))(**((_QWORD **)v150 + 1) + 24LL))(
                              *((_QWORD *)v150 + 1),
                              1,
                              &v250,
                              v257);
          if ( RelatedDAITItem < 0 )
          {
            v162 = (char *)WiaTrace_TraceLog("ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v162);
            WiaTrcLib::Free((WiaTrcLib *)v162, v163);
            v157 = (void **)WiaTrace_Trace(
                              "ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)",
                              (unsigned int)RelatedDAITItem);
          }
          else
          {
            if ( ((__int64)v257[0] & 0x1000) != 0 )
              v151 = *(_DWORD *)(v258 + 4);
            else
              v151 = (int)v257[1];
            v152 = v269;
            v153 = v84;
            if ( ((v269[v153].vt - 3) & 0xFFEF) == 0 )
            {
              lVal = v269[v153].lVal;
              if ( (v151 & lVal) == lVal )
              {
                if ( (lVal & 0x7D) != 0 && (lVal & 2) != 0 )
                {
                  RelatedDAITItem = -2147024809;
                  v155 = (char *)WiaTrace_TraceLog("WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X - flatbed AND feeder related f"
                                                   "lags cannot be enabled at the same time (0x%X)");
                  WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v155);
                  WiaTrcLib::Free((WiaTrcLib *)v155, v156);
                  v157 = (void **)WiaTrace_Trace(
                                    "WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X - flatbed AND feeder related flags cannot be "
                                    "enabled at the same time (0x%X)",
                                    v152[v153].lVal,
                                    -2147024809);
                  goto LABEL_140;
                }
LABEL_141:
                v144 = v257;
                goto LABEL_142;
              }
            }
            RelatedDAITItem = -2147024809;
            v160 = (char *)WiaTrace_TraceLog("invalid value(s) requested for WIA_DPS_DOCUMENT_HANDLING_SELECT (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v160);
            WiaTrcLib::Free((WiaTrcLib *)v160, v161);
            v157 = (void **)WiaTrace_Trace(
                              "invalid value(s) requested for WIA_DPS_DOCUMENT_HANDLING_SELECT (0x%X)",
                              2147942487LL);
          }
LABEL_140:
          WiaTrace_ProcessTrace_Ex(v159, v158, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v157);
          goto LABEL_141;
        }
        v92 = v242;
        if ( (_DWORD)v242 != 1 )
          break;
        if ( HIDWORD(v254[2]) == 4 || HIDWORD(v254[2]) == 8 && this[26] == (CWiaItem *)this )
          goto LABEL_82;
        if ( HIDWORD(v254[2]) == 6 && !*((_QWORD *)this[8] + 12) )
          goto LABEL_143;
        if ( HIDWORD(v254[2]) == 5 )
        {
          if ( !*((_QWORD *)this[8] + 11) )
            goto LABEL_143;
LABEL_79:
          v94 = &v243[v266];
          v95 = &v23[v266];
          v93 = &v266;
          goto LABEL_83;
        }
        if ( HIDWORD(v254[2]) != 6 && *((struct CWiaItem **)this[8] + 12) != v244 )
          goto LABEL_79;
        v93 = &v241;
        v94 = &v248[v241];
        v95 = &v247[v241];
LABEL_83:
        v96 = (PROPID)v254[2];
LABEL_63:
        v94->propid = v96;
        v94->ulKind = 1;
        v97 = v269;
        *(_OWORD *)&v95->vt = 0;
        v95->bstrblobVal.pData = 0;
        v98 = &v97[v84];
        PropVariantCopy((PROPVARIANT *)v95, (const PROPVARIANT *)v98);
        if ( v250.propid == 4108 )
        {
          if ( v92 != 1 )
            goto LABEL_114;
          if ( ((v98->vt - 3) & 0xFFEF) != 0 )
          {
            RelatedDAITItem = -2147418113;
            v99 = (char *)WiaTrace_TraceLog("invalid VT for WIA_IPA_TYMED (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v99);
            WiaTrcLib::Free((WiaTrcLib *)v99, v100);
            v101 = (void **)WiaTrace_Trace("invalid VT for WIA_IPA_TYMED (0x%X)", 2147549183LL);
            goto LABEL_67;
          }
          v86 = v98->lVal == 128;
          v251 = 1;
          if ( v86 )
            v95->lVal = 2;
        }
        else if ( v250.propid == 4106 )
        {
          if ( v92 != 1 )
            goto LABEL_114;
          if ( v98->vt != 72 )
          {
            RelatedDAITItem = -2147418113;
            v110 = (char *)WiaTrace_TraceLog("invalid VT for WIA_IPA_FORMAT (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v110);
            WiaTrcLib::Free((WiaTrcLib *)v110, v111);
            v101 = (void **)WiaTrace_Trace("invalid VT for WIA_IPA_FORMAT (0x%X)", 2147549183LL);
            goto LABEL_67;
          }
          pbstrVal = v98->pbstrVal;
          LODWORD(v249) = 1;
          v106 = (char *)*pbstrVal - (char *)v261;
          if ( *pbstrVal == v261 )
            v106 = (__int64)pbstrVal[1] - v260;
          if ( !v106 )
          {
            v107 = (GUID *)CoTaskMemAlloc(0x10u);
            v95->hVal.QuadPart = (LONGLONG)v107;
            if ( v107 )
            {
              *v107 = WiaImgFmt_BMP;
              goto LABEL_114;
            }
            RelatedDAITItem = -2147024882;
            v108 = (char *)WiaTrace_TraceLog("cannot allocate memory for format GUID (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v108);
            WiaTrcLib::Free((WiaTrcLib *)v108, v109);
            v101 = (void **)WiaTrace_Trace("cannot allocate memory for format GUID (0x%X)", 2147942414LL);
LABEL_67:
            v104 = 1;
LABEL_113:
            WiaTrace_ProcessTrace_Ex(v103, v102, (void *)"CWiaItem::WriteMultipleToDAIT", v104, v101);
          }
        }
        else if ( v250.propid == 3088 && v92 == 1 )
        {
          v263 = 0;
          v112 = this[27];
          *(_OWORD *)pvar = 0;
          RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, struct tagPROPSPEC *, PROPVARIANT *))(**((_QWORD **)v112 + 1) + 24LL))(
                              *((_QWORD *)v112 + 1),
                              1,
                              &v250,
                              pvar);
          if ( RelatedDAITItem < 0 )
          {
            v119 = (char *)WiaTrace_TraceLog("ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v119);
            WiaTrcLib::Free((WiaTrcLib *)v119, v120);
            v116 = (void **)WiaTrace_Trace(
                              "ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)",
                              (unsigned int)RelatedDAITItem);
LABEL_106:
            WiaTrace_ProcessTrace_Ex(v118, v117, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v116);
          }
          else
          {
            if ( ((__int64)pvar[0] & 0x1000) != 0 )
              v113 = *(_DWORD *)(v263 + 4);
            else
              v113 = (int)pvar[1];
            if ( ((v98->vt - 3) & 0xFFEF) != 0 || (v113 & v98->lVal) != v98->lVal )
            {
              RelatedDAITItem = -2147024809;
              v114 = (char *)WiaTrace_TraceLog("invalid value(s) requested for WIA_DPS_DOCUMENT_HANDLING_SELECT (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v114);
              WiaTrcLib::Free((WiaTrcLib *)v114, v115);
              v116 = (void **)WiaTrace_Trace(
                                "invalid value(s) requested for WIA_DPS_DOCUMENT_HANDLING_SELECT (0x%X)",
                                2147942487LL);
              goto LABEL_106;
            }
          }
          PropVariantClear(pvar);
          if ( RelatedDAITItem < 0 )
            goto LABEL_114;
          v121 = v98->lVal;
          if ( (v121 & 0x7D) != 0 && (v121 & 2) != 0 )
          {
            RelatedDAITItem = -2147024809;
            v122 = (char *)WiaTrace_TraceLog("WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X - flatbed AND feeder related flags c"
                                             "annot be enabled at the same time (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v122);
            WiaTrcLib::Free((WiaTrcLib *)v122, v123);
            v124 = (void **)WiaTrace_Trace(
                              "WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X - flatbed AND feeder related flags cannot be enable"
                              "d at the same time (0x%X)",
                              v98->lVal,
                              -2147024809);
            WiaTrace_ProcessTrace_Ex(v126, v125, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v124);
            goto LABEL_114;
          }
          v127 = v98->lVal & 0x7C;
          v95->lVal = v127;
          if ( (v121 & 0x7C) == 0 )
          {
            v127 = 32;
            v95->lVal = 32;
          }
          v128 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                           0,
                           0,
                           "WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X, WIA_IPS_DOCUMENT_HANDLING_SELECT: 0x%X",
                           v98->lVal,
                           v127);
          WriteDbgTraceInfoWI("CWiaItem::WriteMultipleToDAIT", v128);
          WiaTrcLib::Free((WiaTrcLib *)v128, v129);
          v101 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                            0,
                            0,
                            "WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X, WIA_IPS_DOCUMENT_HANDLING_SELECT: 0x%X",
                            v98->lVal,
                            v95->lVal);
          v104 = 4;
          goto LABEL_113;
        }
LABEL_114:
        ++*v93;
        if ( RelatedDAITItem < 0 )
        {
          v130 = (char *)WiaTrace_TraceLog("property translation on %u failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v130);
          WiaTrcLib::Free((WiaTrcLib *)v130, v131);
          v132 = (void **)WiaTrace_Trace("property translation on %u failed (0x%X)", v250.propid, RelatedDAITItem);
LABEL_145:
          WiaTrace_ProcessTrace_Ex(v134, v133, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v132);
          v166 = 0;
          goto LABEL_174;
        }
LABEL_143:
        v23 = v246;
        v82 = v245[0] + 1;
        v33 = v240;
        LODWORD(v7) = v267;
      }
      if ( LODWORD(v254[1]) != 1 && (LODWORD(v254[1]) != 3 || this[26] != (CWiaItem *)this) )
      {
        v93 = &v241;
        v94 = &v248[v241];
        v95 = &v247[v241];
LABEL_62:
        v96 = HIDWORD(v254[0]);
        goto LABEL_63;
      }
LABEL_82:
      v93 = &v245[1];
      v94 = &v253[v245[1]];
      v95 = &v252[v245[1]];
      if ( (_DWORD)v242 != 1 )
        goto LABEL_62;
      goto LABEL_83;
    }
LABEL_146:
    v166 = 0;
    v240 = 0;
    if ( RelatedDAITItem < 0 )
      goto LABEL_174;
    if ( (_DWORD)v242 != 1 )
    {
      RelatedDAITItem = CWiaItem::GetDocumentHandling(this[8], &v240, 1);
      if ( RelatedDAITItem < 0 )
      {
        RelatedDAITItem = -2147467261;
        v167 = (char *)WiaTrace_TraceLog("failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v167);
        WiaTrcLib::Free((WiaTrcLib *)v167, v168);
        v169 = (void **)WiaTrace_Trace(
                          "failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)",
                          -2147467261);
        WiaTrace_ProcessTrace_Ex(v171, v170, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v169);
        v166 = v240;
LABEL_174:
        v188 = v243;
        v189 = v266;
        goto LABEL_175;
      }
      v166 = v240;
    }
    v172 = v245[1];
    v173 = a5;
    if ( v245[1]
      && (LogRWMultiple(0, v245[1], v253, v252, L"D-AIT (root)"),
          RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *, unsigned int))(*((_QWORD *)this[8] + 1) + 32LL))(
                              (__int64)this[8] + 8,
                              v172,
                              v253,
                              v252,
                              v173),
          RelatedDAITItem < 0) )
    {
      v174 = (char *)WiaTrace_TraceLog("WriteMultiple on root D-AIT item failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v174);
      WiaTrcLib::Free((WiaTrcLib *)v174, v175);
      v176 = (void **)WiaTrace_Trace("WriteMultiple on root D-AIT item failed (0x%X)", (unsigned int)RelatedDAITItem);
    }
    else
    {
      if ( v241 )
      {
        if ( (_DWORD)v242 == 1 )
          v179 = *((_QWORD *)this[8] + 12);
        else
          v179 = *((_QWORD *)this[26] + 10);
        if ( !v179 )
        {
          RelatedDAITItem = -2147467261;
          v180 = (char *)WiaTrace_TraceLog("NULL child #1 D-AIT item (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v180);
          WiaTrcLib::Free((WiaTrcLib *)v180, v181);
          v176 = (void **)WiaTrace_Trace("NULL child #1 D-AIT item (0x%X)", 2147500035LL);
          goto LABEL_173;
        }
        if ( (_DWORD)v242 != 1 && this != (CWiaItem **)this[26] )
        {
          RelatedDAITItem = CWiaItem::SetLegacyItemContext((CWiaItem *)this);
          if ( RelatedDAITItem < 0 )
          {
            v182 = (char *)WiaTrace_TraceLog("SetLegacyItemContext for child #1 failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v182);
            WiaTrcLib::Free((WiaTrcLib *)v182, v183);
            v176 = (void **)WiaTrace_Trace(
                              "SetLegacyItemContext for child #1 failed (0x%X)",
                              (unsigned int)RelatedDAITItem);
            goto LABEL_173;
          }
        }
        LogRWMultiple(0, v241, v248, v247, L"D-AIT (child #1)");
        RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *, unsigned int))(*(_QWORD *)(v179 + 8) + 32LL))(
                            v179 + 8,
                            v241,
                            v248,
                            v247,
                            v173);
        if ( RelatedDAITItem < 0 )
        {
          v184 = (char *)WiaTrace_TraceLog("WriteMultiple on #1 child D-AIT item failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v184);
          WiaTrcLib::Free((WiaTrcLib *)v184, v185);
          v176 = (void **)WiaTrace_Trace(
                            "WriteMultiple on #1 child D-AIT item failed (0x%X)",
                            (unsigned int)RelatedDAITItem);
          goto LABEL_173;
        }
      }
      if ( !v266 )
        goto LABEL_174;
      if ( (_DWORD)v242 == 1 )
      {
        v186 = *((_QWORD *)this[8] + 11);
        if ( v186 )
        {
          LogRWMultiple(0, v266, v243, v23, L"D-AIT (child #2)");
          lpMema = v173;
          v187 = v23;
          v188 = v243;
          v189 = v266;
          RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *, unsigned int))(*(_QWORD *)(v186 + 8) + 32LL))(
                              v186 + 8,
                              v266,
                              v243,
                              v187,
                              lpMema);
          if ( RelatedDAITItem < 0 )
          {
            v190 = (char *)WiaTrace_TraceLog("WriteMultiple on #2 child D-AIT item failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v190);
            WiaTrcLib::Free((WiaTrcLib *)v190, v191);
            v192 = (void **)WiaTrace_Trace("WriteMultiple on #2 child D-AIT item failed (0x%X)", RelatedDAITItem);
            WiaTrace_ProcessTrace_Ex(v194, v193, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v192);
          }
LABEL_175:
          v202 = v252;
          if ( v252 )
          {
            CustomFreePropVariantArray(v245[1], v252, L"Root");
            operator delete(v202);
          }
          v203 = v247;
          if ( v247 )
          {
            CustomFreePropVariantArray(v241, v247, L"ChildOne");
            operator delete(v203);
          }
          v204 = v246;
          if ( v246 )
          {
            CustomFreePropVariantArray(v189, v246, L"ChildTwo");
            operator delete(v204);
          }
          if ( v253 )
            operator delete(v253);
          if ( v248 )
            operator delete(v248);
          if ( v188 )
            operator delete(v188);
          if ( RelatedDAITItem < 0 )
            goto LABEL_220;
          if ( (_DWORD)v242 != 1 )
          {
            RelatedDAITItem = CWiaItem::SetDocumentHandling(this[8], v166, v32);
            if ( RelatedDAITItem >= 0 )
            {
LABEL_221:
              v16 = RelatedDAITItem;
              goto LABEL_222;
            }
            v205 = (char *)WiaTrace_TraceLog("cannot restore WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v205);
            WiaTrcLib::Free((WiaTrcLib *)v205, v206);
            v207 = (void **)WiaTrace_Trace(
                              "cannot restore WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT (0x%X)",
                              (unsigned int)RelatedDAITItem);
            goto LABEL_219;
          }
          v210 = v251;
          if ( !v251 && !(_DWORD)v249 )
            goto LABEL_221;
          *(_DWORD *)v255 = 1;
          v256 = 4106;
          v211 = this[27];
          *(_OWORD *)&v255[8] = 0;
          *(_DWORD *)&v255[16] = 1;
          memset(v254, 0, sizeof(v254));
          *(_DWORD *)&v255[8] = 4108;
          RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, PROPVARIANT *))(**(_QWORD **)v211 + 24LL))(
                              *(_QWORD *)v211,
                              2,
                              v255,
                              v254);
          if ( RelatedDAITItem >= 0 )
          {
            v217 = LODWORD(v254[1]) == 128;
            v218 = (__int64)v261 - *(_QWORD *)v254[4];
            if ( v261 == *(OLECHAR **)v254[4] )
              v218 = v260 - *((_QWORD *)v254[4] + 1);
            v219 = v218 == 0;
            if ( v219 == v217 )
              goto LABEL_214;
            if ( v210 )
            {
              v220 = (GUID *)CoTaskMemAlloc(0x10u);
              v254[4] = v220;
              if ( !v220 )
              {
                RelatedDAITItem = -2147024882;
                v224 = (char *)WiaTrace_TraceLog("cannot allocate memory for format GUID (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v224);
                WiaTrcLib::Free((WiaTrcLib *)v224, v225);
                v214 = (void **)WiaTrace_Trace("cannot allocate memory for format GUID (0x%X)", 2147942414LL);
                goto LABEL_213;
              }
              v221 = v244;
              *v220 = WiaImgFmt_BMP;
              RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, PROPVARIANT *, int))(*((_QWORD *)v221 + 1) + 32LL))(
                                  (__int64)v221 + 8,
                                  1,
                                  &v255[16],
                                  &v254[3],
                                  4098);
              if ( RelatedDAITItem < 0 )
              {
                v222 = (char *)WiaTrace_TraceLog("failed to set WiaImgFmt_BMP on D-AIT child (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v222);
                WiaTrcLib::Free((WiaTrcLib *)v222, v223);
                v214 = (void **)WiaTrace_Trace(
                                  "failed to set WiaImgFmt_BMP on D-AIT child (0x%X)",
                                  (unsigned int)RelatedDAITItem);
                goto LABEL_213;
              }
              if ( v217 )
                *(GUID *)v254[4] = WiaImgFmt_MEMORYBMP;
              else
                *(GUID *)v254[4] = WiaImgFmt_BMP;
            }
            else
            {
              LODWORD(v254[1]) = 2;
              RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, PROPVARIANT *, int))(*((_QWORD *)v244 + 1) + 32LL))(
                                  (__int64)v244 + 8,
                                  1,
                                  v255,
                                  v254,
                                  4098);
              if ( RelatedDAITItem < 0 )
              {
                v226 = (char *)WiaTrace_TraceLog("failed to set TYMED_FILE on D-AIT child (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v226);
                WiaTrcLib::Free((WiaTrcLib *)v226, v227);
                v214 = (void **)WiaTrace_Trace(
                                  "failed to set TYMED_FILE on D-AIT child (0x%X)",
                                  (unsigned int)RelatedDAITItem);
                goto LABEL_213;
              }
              if ( v219 )
                LODWORD(v254[1]) = 128;
              else
                LODWORD(v254[1]) = v217 != 0 ? 128 : 2;
            }
            RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, PROPVARIANT *, int))(**(_QWORD **)this[27] + 32LL))(
                                *(_QWORD *)this[27],
                                2,
                                v255,
                                v254,
                                4098);
            if ( RelatedDAITItem >= 0 )
            {
LABEL_214:
              PropVariantClear(v254);
              PropVariantClear(&v254[3]);
              if ( RelatedDAITItem < 0 )
              {
LABEL_220:
                v232 = (char *)WiaTrace_TraceLog("failed to translate call to linked D-AIT item(s) (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v232);
                WiaTrcLib::Free((WiaTrcLib *)v232, v233);
                v234 = (void **)WiaTrace_Trace(
                                  "failed to translate call to linked D-AIT item(s) (0x%X)",
                                  RelatedDAITItem);
                WiaTrace_ProcessTrace_Ex(v236, v235, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v234);
                goto LABEL_221;
              }
              v258 = 0;
              v260 = 0;
              LODWORD(v260) = 1;
              *(_OWORD *)v257 = 0;
              DWORD2(v260) = 4123;
              if ( (*(int (__fastcall **)(__int64, __int64, __int128 *, PROPVARIANT *))(*((_QWORD *)v244 + 1) + 24LL))(
                     (__int64)v244 + 8,
                     1,
                     &v260,
                     v257) >= 0 )
                RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *, int))(**(_QWORD **)this[27] + 32LL))(
                                    *(_QWORD *)this[27],
                                    1,
                                    &v260,
                                    v257,
                                    4098);
              PropVariantClear(v257);
              if ( RelatedDAITItem >= 0 )
                goto LABEL_221;
              v230 = (char *)WiaTrace_TraceLog("cannot refresh WIA_IPA_FILENAME_EXTENSION (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v230);
              WiaTrcLib::Free((WiaTrcLib *)v230, v231);
              v207 = (void **)WiaTrace_Trace(
                                "cannot refresh WIA_IPA_FILENAME_EXTENSION (0x%X)",
                                (unsigned int)RelatedDAITItem);
LABEL_219:
              WiaTrace_ProcessTrace_Ex(v209, v208, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v207);
              goto LABEL_220;
            }
            v228 = (char *)WiaTrace_TraceLog("cannot sync on A-AIT child TYMED_CALLBACK with WiaImgFmt_MEMORYBMP (2) (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v228);
            WiaTrcLib::Free((WiaTrcLib *)v228, v229);
            v214 = (void **)WiaTrace_Trace(
                              "cannot sync on A-AIT child TYMED_CALLBACK with WiaImgFmt_MEMORYBMP (2) (0x%X)",
                              (unsigned int)RelatedDAITItem);
          }
          else
          {
            v212 = (char *)WiaTrace_TraceLog("cannot sync on A-AIT child TYMED_CALLBACK with WiaImgFmt_MEMORYBMP (1) (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v212);
            WiaTrcLib::Free((WiaTrcLib *)v212, v213);
            v214 = (void **)WiaTrace_Trace(
                              "cannot sync on A-AIT child TYMED_CALLBACK with WiaImgFmt_MEMORYBMP (1) (0x%X)",
                              (unsigned int)RelatedDAITItem);
          }
LABEL_213:
          WiaTrace_ProcessTrace_Ex(v216, v215, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v214);
          goto LABEL_214;
        }
      }
      else
      {
        v195 = (char *)WiaTrace_TraceLog("not a lagacy app, there is no D-AIT child #2 (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v195);
        WiaTrcLib::Free((WiaTrcLib *)v195, v196);
        v197 = (void **)WiaTrace_Trace("not a lagacy app, there is no D-AIT child #2 (0x%X)", -2147418113);
        WiaTrace_ProcessTrace_Ex(v199, v198, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v197);
      }
      RelatedDAITItem = -2147467261;
      v200 = (char *)WiaTrace_TraceLog("NULL child #2 D-AIT item (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v200);
      WiaTrcLib::Free((WiaTrcLib *)v200, v201);
      v176 = (void **)WiaTrace_Trace("NULL child #2 D-AIT item (0x%X)", 2147500035LL);
    }
LABEL_173:
    WiaTrace_ProcessTrace_Ex(v178, v177, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v176);
    goto LABEL_174;
  }
  v11 = (char *)WiaTrace_TraceLog("called on a non-A-AIT item (E_FAIL)");
  WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v11);
  WiaTrcLib::Free((WiaTrcLib *)v11, v12);
  v13 = (void **)WiaTrace_Trace("called on a non-A-AIT item (E_FAIL)");
  WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v13);
  v16 = -2147467259;
LABEL_222:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v265);
  return v16;
}

```

## disassembly

```asm
0x18006b040  mov     rax, rsp
0x18006b043  mov     [rax+20h], r9
0x18006b047  mov     [rax+18h], r8
0x18006b04b  mov     [rax+10h], edx
0x18006b04e  push    rbp
0x18006b04f  push    rbx
0x18006b050  push    rsi
0x18006b051  push    rdi
0x18006b052  push    r12
0x18006b054  push    r13
0x18006b056  push    r14
0x18006b058  push    r15
0x18006b05a  lea     rbp, [rax-108h]
0x18006b061  sub     rsp, 1C8h
0x18006b068  mov     r13, rcx
0x18006b06b  movaps  xmmword ptr [rax-58h], xmm6
0x18006b06f  lea     r15, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b076  movaps  xmmword ptr [rax-68h], xmm7
0x18006b07a  mov     rcx, r15
0x18006b07d  mov     r14d, edx
0x18006b080  call    WiaTrace_Trace
0x18006b085  mov     r9, r15; char *
0x18006b088  mov     [rsp+200h+var_1D8], rax; struct tagWiaTraceData_Type *
0x18006b08d  lea     rcx, [rbp+100h+var_B0]; this
0x18006b091  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18006b096  mov     rax, [r13+0D0h]
0x18006b09d  xor     edi, edi
0x18006b09f  cmp     [rax+40h], rdi
0x18006b0a3  jnz     short loc_18006B0EE
0x18006b0a5  lea     rcx, aCalledOnANonAA_0; "called on a non-A-AIT item (E_FAIL)"
0x18006b0ac  call    WiaTrace_TraceLog
0x18006b0b1  mov     rdx, rax; char *
0x18006b0b4  mov     rcx, r15; char *
0x18006b0b7  mov     rbx, rax
0x18006b0ba  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b0bf  mov     rcx, rbx; this
0x18006b0c2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b0c7  lea     rcx, aCalledOnANonAA_0; "called on a non-A-AIT item (E_FAIL)"
0x18006b0ce  call    WiaTrace_Trace
0x18006b0d3  lea     r9d, [rdi+1]; int
0x18006b0d7  mov     [rsp+200h+lpMem], rax; lpMem
0x18006b0dc  mov     r8, r15; int
0x18006b0df  call    WiaTrace_ProcessTrace_Ex
0x18006b0e4  mov     ebx, 80004005h
0x18006b0e9  jmp     loc_18006C939
0x18006b0ee  mov     rcx, r13; this
0x18006b0f1  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x18006b0f6  test    eax, eax
0x18006b0f8  jnz     short loc_18006B145
0x18006b0fa  lea     rcx, aCalledInNonCom; "called in non-compat mode (E_INVALIDARG"...
0x18006b101  call    WiaTrace_TraceLog
0x18006b106  mov     rdx, rax; char *
0x18006b109  mov     rcx, r15; char *
0x18006b10c  mov     rbx, rax
0x18006b10f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b114  mov     rcx, rbx; this
0x18006b117  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b11c  lea     rcx, aCalledInNonCom; "called in non-compat mode (E_INVALIDARG"...
0x18006b123  call    WiaTrace_Trace
0x18006b128  mov     r9d, 1; int
0x18006b12e  mov     [rsp+200h+lpMem], rax; lpMem
0x18006b133  mov     r8, r15; int
0x18006b136  call    WiaTrace_ProcessTrace_Ex
0x18006b13b  mov     ebx, 80070057h
0x18006b140  jmp     loc_18006C939
0x18006b145  mov     r15d, [r13+0E0h]
0x18006b14c  mov     eax, edi
0x18006b14e  mov     esi, 1
0x18006b153  mov     dword ptr [rsp+200h+var_1C8], r15d
0x18006b158  cmp     r15d, esi
0x18006b15b  mov     [rsp+200h+var_1C0], rdi
0x18006b160  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b167  mov     [rbp+100h+var_170], rdi
0x18006b16b  setz    al
0x18006b16e  mov     [rsp+200h+var_1A0], rdi
0x18006b173  mov     [rbp+100h+var_F8], eax
0x18006b176  mov     r12, rdi
0x18006b179  lea     eax, [rsi+0Fh]
0x18006b17c  mov     [rsp+200h+var_1A8], rdi
0x18006b181  mul     r14
0x18006b184  mov     [rsp+200h+var_1B0+4], edi
0x18006b188  mov     rbx, r14
0x18006b18b  mov     [rsp+200h+var_1CC], edi
0x18006b18f  cmovb   rax, rcx
0x18006b193  mov     [rbp+100h+arg_0], edi
0x18006b199  mov     rcx, rax; unsigned __int64
0x18006b19c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006b1a1  mov     [rbp+100h+var_168], rax
0x18006b1a5  test    rax, rax
0x18006b1a8  jnz     short loc_18006B215
0x18006b1aa  mov     r15d, 8007000Eh
0x18006b1b0  mov     [rsp+200h+var_198], rdi
0x18006b1b5  mov     edx, r15d
0x18006b1b8  lea     rcx, aOutOfMemory10x; "out of memory (1) (0x%X)"
0x18006b1bf  mov     edi, r15d
0x18006b1c2  call    WiaTrace_TraceLog
0x18006b1c7  mov     rdx, rax; char *
0x18006b1ca  lea     rcx, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b1d1  mov     rbx, rax
0x18006b1d4  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b1d9  mov     rcx, rbx; this
0x18006b1dc  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b1e1  mov     edx, r15d
0x18006b1e4  lea     rcx, aOutOfMemory10x; "out of memory (1) (0x%X)"
0x18006b1eb  call    WiaTrace_Trace
0x18006b1f0  mov     r9d, esi; int
0x18006b1f3  mov     [rsp+200h+lpMem], rax; lpMem
0x18006b1f8  lea     r8, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b1ff  call    WiaTrace_ProcessTrace_Ex
0x18006b204  lea     ebx, [rsi+7]
0x18006b207  mov     [rsp+200h+var_1B8], r12
0x18006b20c  mov     [rsp+200h+var_1D0], ebx
0x18006b210  jmp     loc_18006B71C
0x18006b215  mov     rdi, rbx
0x18006b218  xor     edx, edx; Val
0x18006b21a  shl     rdi, 4
0x18006b21e  mov     rcx, rax; void *
0x18006b221  mov     r8, rdi; Size
0x18006b224  call    memset_0
0x18006b229  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b230  mov     eax, 10h
0x18006b235  mul     rbx
0x18006b238  cmovb   rax, rcx
0x18006b23c  mov     rcx, rax; unsigned __int64
0x18006b23f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006b244  mov     [rsp+200h+var_198], rax
0x18006b249  test    rax, rax
0x18006b24c  jnz     short loc_18006B2B2
0x18006b24e  mov     r15d, 8007000Eh
0x18006b254  lea     rcx, aOutOfMemory20x; "out of memory (2) (0x%X)"
0x18006b25b  mov     edx, r15d
0x18006b25e  mov     edi, r15d
0x18006b261  call    WiaTrace_TraceLog
0x18006b266  mov     rdx, rax; char *
0x18006b269  lea     rcx, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b270  mov     rbx, rax
0x18006b273  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b278  mov     rcx, rbx; this
0x18006b27b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b280  lea     rcx, aOutOfMemory20x; "out of memory (2) (0x%X)"
0x18006b287  mov     edx, r15d
0x18006b28a  call    WiaTrace_Trace
0x18006b28f  mov     r9d, esi; int
0x18006b292  mov     [rsp+200h+lpMem], rax; lpMem
0x18006b297  lea     r8, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b29e  call    WiaTrace_ProcessTrace_Ex
0x18006b2a3  mov     [rsp+200h+var_1B8], r12
0x18006b2a8  mov     ebx, 8
0x18006b2ad  jmp     loc_18006B711
0x18006b2b2  mov     r8, rdi; Size
0x18006b2b5  xor     edx, edx; Val
0x18006b2b7  mov     rcx, rax; void *
0x18006b2ba  call    memset_0
0x18006b2bf  cmp     r15d, esi
0x18006b2c2  jnz     short loc_18006B334
0x18006b2c4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b2cb  mov     eax, 10h
0x18006b2d0  mul     rbx
0x18006b2d3  cmovb   rax, rcx
0x18006b2d7  mov     rcx, rax; unsigned __int64
0x18006b2da  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006b2df  mov     [rsp+200h+var_1C0], rax
0x18006b2e4  test    rax, rax
0x18006b2e7  jnz     short loc_18006B327
0x18006b2e9  mov     r15d, 8007000Eh
0x18006b2ef  lea     rcx, aOutOfMemory30x; "out of memory (3) (0x%X)"
0x18006b2f6  mov     edx, r15d
0x18006b2f9  mov     edi, r15d
0x18006b2fc  call    WiaTrace_TraceLog
0x18006b301  mov     rdx, rax; char *
0x18006b304  lea     rcx, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b30b  mov     rbx, rax
0x18006b30e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b313  mov     rcx, rbx; this
0x18006b316  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b31b  lea     rcx, aOutOfMemory30x; "out of memory (3) (0x%X)"
0x18006b322  jmp     loc_18006B287
0x18006b327  mov     r8, rdi; Size
0x18006b32a  xor     edx, edx; Val
0x18006b32c  mov     rcx, rax; void *
0x18006b32f  call    memset_0
0x18006b334  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b33b  mov     eax, 18h
0x18006b340  mul     rbx
0x18006b343  cmovb   rax, rcx
0x18006b347  mov     rcx, rax; unsigned __int64
0x18006b34a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006b34f  mov     [rbp+100h+var_170], rax
0x18006b353  test    rax, rax
0x18006b356  jnz     short loc_18006B396
0x18006b358  mov     r15d, 8007000Eh
0x18006b35e  lea     rcx, aOutOfMemory40x; "out of memory (4) (0x%X)"
0x18006b365  mov     edx, r15d
0x18006b368  mov     edi, r15d
0x18006b36b  call    WiaTrace_TraceLog
0x18006b370  mov     rdx, rax; char *
0x18006b373  lea     rcx, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b37a  mov     rbx, rax
0x18006b37d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b382  mov     rcx, rbx; this
0x18006b385  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b38a  lea     rcx, aOutOfMemory40x; "out of memory (4) (0x%X)"
0x18006b391  jmp     loc_18006B287
0x18006b396  lea     rdi, [r14+r14*2]
0x18006b39a  xor     edx, edx; Val
0x18006b39c  shl     rdi, 3
0x18006b3a0  mov     rcx, rax; void *
0x18006b3a3  mov     r8, rdi; Size
0x18006b3a6  call    memset_0
0x18006b3ab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b3b2  mov     eax, 18h
0x18006b3b7  mul     rbx
0x18006b3ba  cmovb   rax, rcx
0x18006b3be  mov     rcx, rax; unsigned __int64
0x18006b3c1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006b3c6  mov     [rsp+200h+var_1A0], rax
0x18006b3cb  test    rax, rax
0x18006b3ce  jnz     short loc_18006B40E
0x18006b3d0  mov     r15d, 8007000Eh
0x18006b3d6  lea     rcx, aOutOfMemory50x; "out of memory (5) (0x%X)"
0x18006b3dd  mov     edx, r15d
0x18006b3e0  mov     edi, r15d
0x18006b3e3  call    WiaTrace_TraceLog
0x18006b3e8  mov     rdx, rax; char *
0x18006b3eb  lea     rcx, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b3f2  mov     rbx, rax
0x18006b3f5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b3fa  mov     rcx, rbx; this
0x18006b3fd  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b402  lea     rcx, aOutOfMemory50x; "out of memory (5) (0x%X)"
0x18006b409  jmp     loc_18006B287
0x18006b40e  mov     r8, rdi; Size
0x18006b411  xor     edx, edx; Val
0x18006b413  mov     rcx, rax; void *
0x18006b416  call    memset_0
0x18006b41b  cmp     r15d, esi
0x18006b41e  jnz     loc_18006B5FF
0x18006b424  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b42b  mov     eax, 18h
0x18006b430  mul     rbx
0x18006b433  cmovb   rax, rcx
0x18006b437  mov     rcx, rax; unsigned __int64
0x18006b43a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006b43f  mov     [rsp+200h+var_1A8], rax
0x18006b444  mov     r12, rax
0x18006b447  test    rax, rax
0x18006b44a  jnz     short loc_18006B4AB
0x18006b44c  mov     r14d, 8007000Eh
0x18006b452  lea     rcx, aOutOfMemory60x; "out of memory (6) (0x%X)"
0x18006b459  mov     edx, r14d
0x18006b45c  mov     edi, r14d
0x18006b45f  call    WiaTrace_TraceLog
0x18006b464  mov     rdx, rax; char *
0x18006b467  lea     rcx, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b46e  mov     rbx, rax
0x18006b471  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b476  mov     rcx, rbx; this
0x18006b479  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b47e  mov     edx, r14d
0x18006b481  lea     rcx, aOutOfMemory60x; "out of memory (6) (0x%X)"
0x18006b488  call    WiaTrace_Trace
0x18006b48d  mov     r9d, esi; int
0x18006b490  mov     [rsp+200h+lpMem], rax; lpMem
0x18006b495  lea     r8, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b49c  call    WiaTrace_ProcessTrace_Ex
0x18006b4a1  mov     [rsp+200h+var_1B8], r12
0x18006b4a6  jmp     loc_18006B2A8
0x18006b4ab  mov     r8, rdi; Size
0x18006b4ae  xor     edx, edx; Val
0x18006b4b0  mov     rcx, r12; void *
0x18006b4b3  call    memset_0
0x18006b4b8  mov     rax, [r13+0D0h]
0x18006b4bf  xor     r14d, r14d
0x18006b4c2  mov     [rsp+200h+var_1B8], r14
0x18006b4c7  mov     qword ptr [rsp+200h+var_190.ulKind], r14
0x18006b4cc  mov     rcx, [rax+50h]; this
0x18006b4d0  test    rcx, rcx
0x18006b4d3  jnz     short loc_18006B539
0x18006b4d5  mov     r15d, 80004003h
0x18006b4db  lea     rcx, aLegacyAppNullD; "(legacy app) NULL D-AIT XP child item ("...
0x18006b4e2  mov     edx, r15d
0x18006b4e5  mov     edi, r15d
0x18006b4e8  call    WiaTrace_TraceLog
0x18006b4ed  mov     rdx, rax; char *
0x18006b4f0  lea     rcx, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b4f7  mov     rbx, rax
0x18006b4fa  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006b4ff  mov     rcx, rbx; this
0x18006b502  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006b507  mov     edx, r15d
0x18006b50a  lea     rcx, aLegacyAppNullD; "(legacy app) NULL D-AIT XP child item ("...
0x18006b511  call    WiaTrace_Trace
0x18006b516  mov     r9d, esi; int
0x18006b519  mov     [rsp+200h+lpMem], rax; lpMem
0x18006b51e  lea     r8, aCwiaitemWritem_0; "CWiaItem::WriteMultipleToDAIT"
0x18006b525  call    WiaTrace_ProcessTrace_Ex
0x18006b52a  mov     ebx, 8
0x18006b52f  mov     [rsp+200h+var_1A8], r12
0x18006b534  jmp     loc_18006B711
0x18006b539  mov     r8d, esi; int
  ... truncated ...
```
