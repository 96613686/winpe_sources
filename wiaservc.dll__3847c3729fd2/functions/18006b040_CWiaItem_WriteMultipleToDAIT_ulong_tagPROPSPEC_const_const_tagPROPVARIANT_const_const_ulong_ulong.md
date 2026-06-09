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
  struct tagWiaTraceData_Type *v8; // rax
  char *v9; // rdx
  unsigned int v10; // r8d
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
  unsigned __int64 v32; // rdx
  int v33; // r8d
  unsigned int v34; // ebx
  struct tagPROPSPEC *v35; // rax
  char *v36; // rbx
  void *v37; // rdx
  void **v38; // rax
  void *v39; // rdx
  __int64 v40; // rcx
  struct tagPROPSPEC *v41; // rax
  char *v42; // rbx
  void *v43; // rdx
  struct tagPROPVARIANT *v44; // rax
  char *v45; // rbx
  void *v46; // rdx
  struct tagPROPVARIANT *v47; // rax
  char *v48; // rbx
  void *v49; // rdx
  struct tagPROPVARIANT *v50; // rax
  char *v51; // rbx
  void *v52; // rdx
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  CWiaItem *v56; // rax
  CWiaItem *v57; // rcx
  char *v58; // rbx
  void *v59; // rdx
  void **v60; // rax
  void *v61; // rdx
  __int64 v62; // rcx
  char *v63; // rbx
  void *v64; // rdx
  void **v65; // rax
  void *v66; // rdx
  __int64 v67; // rcx
  char *v68; // rbx
  void *v69; // rdx
  unsigned int *v70; // r15
  CWiaItem *v71; // rcx
  char *v72; // rbx
  void *v73; // rdx
  void **v74; // rax
  void *v75; // rdx
  __int64 v76; // rcx
  unsigned int v77; // r14d
  char *v78; // rbx
  void *v79; // rdx
  void **v80; // rax
  void *v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rax
  const struct tagPROPSPEC *v84; // rcx
  __int64 v85; // r14
  __int64 v86; // rax
  bool v87; // zf
  struct tagPROPSPEC v88; // xmm0
  __int64 v89; // r9
  PROPID propid; // ebx
  int PropCompatCategory; // eax
  int v92; // ecx
  int v93; // ebx
  unsigned int *v94; // r12
  struct tagPROPSPEC *v95; // rcx
  struct tagPROPVARIANT *v96; // r15
  PROPID v97; // eax
  const struct tagPROPVARIANT *v98; // rcx
  const struct tagPROPVARIANT *v99; // r14
  char *v100; // rbx
  void *v101; // rdx
  void **v102; // rax
  void *v103; // rdx
  __int64 v104; // rcx
  int v105; // r9d
  BSTR *pbstrVal; // rcx
  __int64 v107; // rax
  GUID *v108; // rax
  char *v109; // rbx
  void *v110; // rdx
  char *v111; // rbx
  void *v112; // rdx
  CWiaItem *v113; // rax
  int v114; // ecx
  char *v115; // rbx
  void *v116; // rdx
  void **v117; // rax
  void *v118; // rdx
  __int64 v119; // rcx
  char *v120; // rbx
  void *v121; // rdx
  LONG v122; // edx
  char *v123; // rbx
  void *v124; // rdx
  void **v125; // rax
  void *v126; // rdx
  __int64 v127; // rcx
  int v128; // eax
  char *v129; // rbx
  void *v130; // rdx
  char *v131; // rbx
  void *v132; // rdx
  void **v133; // rax
  void *v134; // rdx
  __int64 v135; // rcx
  CWiaItem *v136; // rax
  int v137; // ecx
  char *v138; // rbx
  void *v139; // rdx
  void **v140; // rax
  void *v141; // rdx
  __int64 v142; // rcx
  char *v143; // rbx
  void *v144; // rdx
  PROPVARIANT *v145; // rcx
  char *v146; // rbx
  void *v147; // rdx
  void **v148; // rax
  void *v149; // rdx
  __int64 v150; // rcx
  CWiaItem *v151; // rax
  int v152; // ecx
  const struct tagPROPVARIANT *v153; // r12
  __int64 v154; // r14
  LONG lVal; // edx
  char *v156; // rbx
  void *v157; // rdx
  void **v158; // rax
  void *v159; // rdx
  __int64 v160; // rcx
  char *v161; // rbx
  void *v162; // rdx
  char *v163; // rbx
  void *v164; // rdx
  char *v165; // rbx
  void *v166; // rdx
  unsigned int v167; // r14d
  char *v168; // rbx
  void *v169; // rdx
  void **v170; // rax
  void *v171; // rdx
  __int64 v172; // rcx
  unsigned int v173; // ebx
  unsigned int v174; // r15d
  char *v175; // rbx
  void *v176; // rdx
  void **v177; // rax
  void *v178; // rdx
  __int64 v179; // rcx
  __int64 v180; // rbx
  char *v181; // rbx
  void *v182; // rdx
  char *v183; // rbx
  void *v184; // rdx
  char *v185; // rbx
  void *v186; // rdx
  __int64 v187; // rbx
  struct tagPROPVARIANT *v188; // r9
  struct tagPROPSPEC *v189; // r12
  unsigned int v190; // r15d
  char *v191; // rbx
  void *v192; // rdx
  void **v193; // rax
  void *v194; // rdx
  __int64 v195; // rcx
  char *v196; // rbx
  void *v197; // rdx
  void **v198; // rax
  void *v199; // rdx
  __int64 v200; // rcx
  char *v201; // rbx
  void *v202; // rdx
  struct tagPROPVARIANT *v203; // rbx
  unsigned __int64 v204; // rdx
  struct tagPROPVARIANT *v205; // rbx
  unsigned __int64 v206; // rdx
  struct tagPROPVARIANT *v207; // rbx
  unsigned __int64 v208; // rdx
  char *v209; // rbx
  void *v210; // rdx
  void **v211; // rax
  void *v212; // rdx
  __int64 v213; // rcx
  int v214; // r15d
  CWiaItem *v215; // rax
  char *v216; // rbx
  void *v217; // rdx
  void **v218; // rax
  void *v219; // rdx
  __int64 v220; // rcx
  int v221; // ebx
  __int64 v222; // rcx
  int v223; // r14d
  GUID *v224; // rax
  struct CWiaItem *v225; // rcx
  char *v226; // rbx
  void *v227; // rdx
  char *v228; // rbx
  void *v229; // rdx
  char *v230; // rbx
  void *v231; // rdx
  char *v232; // rbx
  void *v233; // rdx
  char *v234; // rbx
  void *v235; // rdx
  char *v236; // rbx
  void *v237; // rdx
  void **v238; // rax
  void *v239; // rdx
  __int64 v240; // rcx
  unsigned int lpMem; // [rsp+28h] [rbp-E0h]
  unsigned int lpMema; // [rsp+28h] [rbp-E0h]
  unsigned int v244; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v245; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v246; // [rsp+40h] [rbp-C8h]
  struct tagPROPSPEC *v247; // [rsp+48h] [rbp-C0h]
  struct CWiaItem *v248; // [rsp+50h] [rbp-B8h]
  unsigned int v249[2]; // [rsp+58h] [rbp-B0h] BYREF
  struct tagPROPVARIANT *v250; // [rsp+60h] [rbp-A8h]
  struct tagPROPVARIANT *v251; // [rsp+68h] [rbp-A0h]
  struct tagPROPSPEC *v252; // [rsp+70h] [rbp-98h]
  struct CWiaItem *v253; // [rsp+78h] [rbp-90h] BYREF
  struct tagPROPSPEC v254; // [rsp+80h] [rbp-88h] BYREF
  int v255; // [rsp+90h] [rbp-78h]
  struct tagPROPVARIANT *v256; // [rsp+98h] [rbp-70h]
  struct tagPROPSPEC *v257; // [rsp+A0h] [rbp-68h]
  PROPVARIANT v258[6]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v259[24]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v260; // [rsp+F0h] [rbp-18h]
  PROPVARIANT v261[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v262; // [rsp+108h] [rbp+0h]
  BOOL v263; // [rsp+110h] [rbp+8h]
  __int128 v264; // [rsp+118h] [rbp+10h] BYREF
  OLECHAR *v265; // [rsp+128h] [rbp+20h]
  PROPVARIANT pvar[2]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v267; // [rsp+140h] [rbp+38h]
  struct tagPROPSPEC v268; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v269[120]; // [rsp+158h] [rbp+50h] BYREF
  unsigned int v270; // [rsp+218h] [rbp+110h] BYREF
  unsigned int v271; // [rsp+220h] [rbp+118h]
  const struct tagPROPSPEC *v272; // [rsp+228h] [rbp+120h]
  const struct tagPROPVARIANT *v273; // [rsp+230h] [rbp+128h]

  v273 = a4;
  v272 = a3;
  v271 = a2;
  v7 = a2;
  v8 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::WriteMultipleToDAIT");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v269, v9, v10, "CWiaItem::WriteMultipleToDAIT", lpMem, v8);
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
    LODWORD(v246) = v22;
    v247 = 0;
    v256 = 0;
    v251 = 0;
    v263 = v22 == 1;
    v23 = 0;
    v250 = 0;
    v24 = 16 * v7;
    v249[1] = 0;
    v245 = 0;
    if ( !is_mul_ok(v7, 0x10u) )
      v24 = -1;
    v270 = 0;
    v25 = (struct tagPROPSPEC *)operator new[](v24);
    v257 = v25;
    if ( !v25 )
    {
      v252 = 0;
      RelatedDAITItem = -2147024882;
      v27 = (char *)WiaTrace_TraceLog("out of memory (1) (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v27);
      WiaTrcLib::Free((WiaTrcLib *)v27, v28);
      v29 = (void **)WiaTrace_Trace("out of memory (1) (0x%X)", -2147024882);
      WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v29);
      v34 = 8;
      v248 = 0;
      v244 = 8;
      goto LABEL_43;
    }
    memset_0(v25, 0, 16 * v7);
    v35 = (struct tagPROPSPEC *)operator new[](saturated_mul(v7, 0x10u));
    v252 = v35;
    if ( !v35 )
    {
      RelatedDAITItem = -2147024882;
      v36 = (char *)WiaTrace_TraceLog("out of memory (2) (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v36);
      WiaTrcLib::Free((WiaTrcLib *)v36, v37);
      v38 = (void **)WiaTrace_Trace("out of memory (2) (0x%X)", 2147942414LL);
LABEL_11:
      WiaTrace_ProcessTrace_Ex(v40, v39, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v38);
      v248 = 0;
LABEL_12:
      v34 = 8;
LABEL_41:
      v244 = v34;
      goto LABEL_42;
    }
    memset_0(v35, 0, 16 * v7);
    if ( v22 == 1 )
    {
      v41 = (struct tagPROPSPEC *)operator new[](saturated_mul(v7, 0x10u));
      v247 = v41;
      if ( !v41 )
      {
        RelatedDAITItem = -2147024882;
        v42 = (char *)WiaTrace_TraceLog("out of memory (3) (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v42);
        WiaTrcLib::Free((WiaTrcLib *)v42, v43);
        v38 = (void **)WiaTrace_Trace("out of memory (3) (0x%X)", 2147942414LL);
        goto LABEL_11;
      }
      memset_0(v41, 0, 16 * v7);
    }
    v44 = (struct tagPROPVARIANT *)operator new[](saturated_mul(v7, 0x18u));
    v256 = v44;
    if ( !v44 )
    {
      RelatedDAITItem = -2147024882;
      v45 = (char *)WiaTrace_TraceLog("out of memory (4) (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v45);
      WiaTrcLib::Free((WiaTrcLib *)v45, v46);
      v38 = (void **)WiaTrace_Trace("out of memory (4) (0x%X)", 2147942414LL);
      goto LABEL_11;
    }
    memset_0(v44, 0, 24 * v7);
    v47 = (struct tagPROPVARIANT *)operator new[](saturated_mul(v7, 0x18u));
    v251 = v47;
    if ( !v47 )
    {
      RelatedDAITItem = -2147024882;
      v48 = (char *)WiaTrace_TraceLog("out of memory (5) (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v48);
      WiaTrcLib::Free((WiaTrcLib *)v48, v49);
      v38 = (void **)WiaTrace_Trace("out of memory (5) (0x%X)", 2147942414LL);
      goto LABEL_11;
    }
    memset_0(v47, 0, 24 * v7);
    if ( v22 == 1 )
    {
      v50 = (struct tagPROPVARIANT *)operator new[](saturated_mul(v7, 0x18u));
      v250 = v50;
      v23 = v50;
      if ( !v50 )
      {
        RelatedDAITItem = -2147024882;
        v51 = (char *)WiaTrace_TraceLog("out of memory (6) (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v51);
        WiaTrcLib::Free((WiaTrcLib *)v51, v52);
        v53 = (void **)WiaTrace_Trace("out of memory (6) (0x%X)", -2147024882);
        WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v53);
        v248 = 0;
        goto LABEL_12;
      }
      memset_0(v50, 0, 24 * v7);
      v56 = this[26];
      v248 = 0;
      v253 = 0;
      v57 = (CWiaItem *)*((_QWORD *)v56 + 10);
      if ( !v57 )
      {
        RelatedDAITItem = -2147467261;
        v58 = (char *)WiaTrace_TraceLog("(legacy app) NULL D-AIT XP child item (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v58);
        WiaTrcLib::Free((WiaTrcLib *)v58, v59);
        v60 = (void **)WiaTrace_Trace("(legacy app) NULL D-AIT XP child item (0x%X)", 2147500035LL);
LABEL_26:
        WiaTrace_ProcessTrace_Ex(v62, v61, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v60);
        v34 = 8;
        v250 = v23;
        goto LABEL_41;
      }
      RelatedDAITItem = CWiaItem::FindRelatedDAITItem(v57, &v253, 1);
      if ( RelatedDAITItem < 0 )
      {
        v63 = (char *)WiaTrace_TraceLog("FindRelatedDAITItem failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v63);
        WiaTrcLib::Free((WiaTrcLib *)v63, v64);
        v65 = (void **)WiaTrace_Trace("FindRelatedDAITItem failed (0x%X)", RelatedDAITItem);
        WiaTrace_ProcessTrace_Ex(v67, v66, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v65);
        v34 = 8;
        v248 = v253;
        v250 = v23;
        goto LABEL_41;
      }
      v248 = v253;
      if ( !v253 )
      {
        RelatedDAITItem = -2147467261;
        v68 = (char *)WiaTrace_TraceLog("FindRelatedDAITItem returned NULL item (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v68);
        WiaTrcLib::Free((WiaTrcLib *)v68, v69);
        v60 = (void **)WiaTrace_Trace("FindRelatedDAITItem returned NULL item (0x%X)", 2147500035LL);
        goto LABEL_26;
      }
    }
    else
    {
      RelatedDAITItem = 0;
      v248 = 0;
    }
    v250 = v23;
    v34 = 8;
    v244 = 8;
    if ( v22 == 1 )
    {
      v70 = a6;
      v71 = this[26];
      v249[0] = *a6;
      RelatedDAITItem = CWiaItem::GetDocumentHandling(v71, v249, 0);
      if ( RelatedDAITItem >= 0 )
      {
        v77 = v249[0];
        if ( v249[0] == *v70 )
        {
          v77 = *v70;
        }
        else
        {
          RelatedDAITItem = CWiaItem::InitChildItemXPProps(this[26], 1);
          if ( RelatedDAITItem < 0 )
          {
            v78 = (char *)WiaTrace_TraceLog("failed to reinitialize the legacy child A-AIT item (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v78);
            WiaTrcLib::Free((WiaTrcLib *)v78, v79);
            v80 = (void **)WiaTrace_Trace("failed to reinitialize the legacy child A-AIT item (0x%X)", RelatedDAITItem);
            WiaTrace_ProcessTrace_Ex(v82, v81, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v80);
          }
          *v70 = v77;
        }
        v34 = 6 - ((v77 & 1) != 0);
        goto LABEL_41;
      }
      v72 = (char *)WiaTrace_TraceLog("failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v72);
      WiaTrcLib::Free((WiaTrcLib *)v72, v73);
      v74 = (void **)WiaTrace_Trace(
                       "failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)",
                       RelatedDAITItem);
      WiaTrace_ProcessTrace_Ex(v76, v75, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v74);
      v34 = 8;
    }
LABEL_42:
    LODWORD(v7) = v271;
LABEL_43:
    v255 = 0;
    LODWORD(v253) = 0;
    v265 = *(OLECHAR **)&WiaImgFmt_MEMORYBMP.Data1;
    v254 = 0;
    *(_QWORD *)&v264 = _mm_srli_si128((__m128i)WiaImgFmt_MEMORYBMP, 8).m128i_u64[0];
    if ( RelatedDAITItem >= 0 )
    {
      v83 = 0;
      while ( 1 )
      {
        v249[0] = v83;
        if ( (unsigned int)v83 >= (unsigned int)v7 )
          goto LABEL_146;
        v84 = v272;
        v85 = (unsigned int)v83;
        v86 = v83;
        v87 = v272[v86].ulKind == 0;
        v88 = v272[v86];
        v268 = v88;
        if ( v87 )
        {
          RelatedDAITItem = CWiaPropStg::GetPropIDFromName(this[27], &v268, &v254);
          if ( RelatedDAITItem < 0 )
          {
            v165 = (char *)WiaTrace_TraceLog("GetPropIDFromName failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v165);
            WiaTrcLib::Free((WiaTrcLib *)v165, v166);
            v133 = (void **)WiaTrace_Trace("GetPropIDFromName failed (0x%X)", RelatedDAITItem);
            goto LABEL_145;
          }
          v254.ulKind = 1;
        }
        else
        {
          v254 = v88;
        }
        v89 = v34;
        propid = v254.propid;
        memset(v258, 0, 32);
        PropCompatCategory = CWiaItem::GetPropCompatCategory(v84, v254.propid, v263, v89, v258);
        v33 = HIDWORD(v258[3]);
        v92 = v246;
        if ( propid == 3088 && (_DWORD)v246 == 1 )
        {
          v32 = (unsigned __int64)this[8];
          if ( *(_QWORD *)(v32 + 88) )
            v33 = 0;
          v92 = v246;
        }
        if ( !PropCompatCategory || v33 )
        {
          if ( propid != 3088 )
            goto LABEL_143;
          if ( v92 != 1 )
          {
            if ( *((CWiaItem ***)this[26] + 11) != this )
            {
              RelatedDAITItem = -2147024809;
              v146 = (char *)WiaTrace_TraceLog("WIA_IPS_DOCUMENT_HANDLING_SELECT is not supported on this item (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v146);
              WiaTrcLib::Free((WiaTrcLib *)v146, v147);
              v148 = (void **)WiaTrace_Trace(
                                "WIA_IPS_DOCUMENT_HANDLING_SELECT is not supported on this item (0x%X)",
                                -2147024809);
              WiaTrace_ProcessTrace_Ex(v150, v149, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v148);
              goto LABEL_143;
            }
            v136 = this[27];
            memset(v259, 0, sizeof(v259));
            RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, struct tagPROPSPEC *, _BYTE *))(**((_QWORD **)v136 + 1) + 24LL))(
                                *((_QWORD *)v136 + 1),
                                1,
                                &v254,
                                v259);
            if ( RelatedDAITItem < 0 )
            {
              v143 = (char *)WiaTrace_TraceLog("ValidStg#IPropertyStorage::ReadMultiple(WIA_IPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v143);
              WiaTrcLib::Free((WiaTrcLib *)v143, v144);
              v140 = (void **)WiaTrace_Trace(
                                "ValidStg#IPropertyStorage::ReadMultiple(WIA_IPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)",
                                (unsigned int)RelatedDAITItem);
LABEL_127:
              WiaTrace_ProcessTrace_Ex(v142, v141, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v140);
            }
            else
            {
              if ( (*(_WORD *)v259 & 0x1000) != 0 )
                v137 = *(_DWORD *)(*(_QWORD *)&v259[16] + 4LL);
              else
                v137 = *(_DWORD *)&v259[8];
              if ( ((v273[v85].vt - 3) & 0xFFEF) != 0 || (v137 & v273[v85].lVal) != v273[v85].lVal )
              {
                RelatedDAITItem = -2147024809;
                v138 = (char *)WiaTrace_TraceLog("invalid value(s) requested for WIA_IPS_DOCUMENT_HANDLING_SELECT (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v138);
                WiaTrcLib::Free((WiaTrcLib *)v138, v139);
                v140 = (void **)WiaTrace_Trace(
                                  "invalid value(s) requested for WIA_IPS_DOCUMENT_HANDLING_SELECT (0x%X)",
                                  2147942487LL);
                goto LABEL_127;
              }
            }
            v145 = (PROPVARIANT *)v259;
LABEL_142:
            PropVariantClear(v145);
            goto LABEL_143;
          }
          v262 = 0;
          v151 = this[27];
          *(_OWORD *)v261 = 0;
          RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, struct tagPROPSPEC *, PROPVARIANT *))(**((_QWORD **)v151 + 1) + 24LL))(
                              *((_QWORD *)v151 + 1),
                              1,
                              &v254,
                              v261);
          if ( RelatedDAITItem < 0 )
          {
            v163 = (char *)WiaTrace_TraceLog("ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v163);
            WiaTrcLib::Free((WiaTrcLib *)v163, v164);
            v158 = (void **)WiaTrace_Trace(
                              "ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)",
                              (unsigned int)RelatedDAITItem);
          }
          else
          {
            if ( ((__int64)v261[0] & 0x1000) != 0 )
              v152 = *(_DWORD *)(v262 + 4);
            else
              v152 = (int)v261[1];
            v153 = v273;
            v154 = v85;
            if ( ((v273[v154].vt - 3) & 0xFFEF) == 0 )
            {
              lVal = v273[v154].lVal;
              if ( (v152 & lVal) == lVal )
              {
                if ( (lVal & 0x7D) != 0 && (lVal & 2) != 0 )
                {
                  RelatedDAITItem = -2147024809;
                  v156 = (char *)WiaTrace_TraceLog("WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X - flatbed AND feeder related f"
                                                   "lags cannot be enabled at the same time (0x%X)");
                  WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v156);
                  WiaTrcLib::Free((WiaTrcLib *)v156, v157);
                  v158 = (void **)WiaTrace_Trace(
                                    "WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X - flatbed AND feeder related flags cannot be "
                                    "enabled at the same time (0x%X)",
                                    v153[v154].lVal,
                                    -2147024809);
                  goto LABEL_140;
                }
LABEL_141:
                v145 = v261;
                goto LABEL_142;
              }
            }
            RelatedDAITItem = -2147024809;
            v161 = (char *)WiaTrace_TraceLog("invalid value(s) requested for WIA_DPS_DOCUMENT_HANDLING_SELECT (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v161);
            WiaTrcLib::Free((WiaTrcLib *)v161, v162);
            v158 = (void **)WiaTrace_Trace(
                              "invalid value(s) requested for WIA_DPS_DOCUMENT_HANDLING_SELECT (0x%X)",
                              2147942487LL);
          }
LABEL_140:
          WiaTrace_ProcessTrace_Ex(v160, v159, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v158);
          goto LABEL_141;
        }
        v93 = v246;
        if ( (_DWORD)v246 != 1 )
          break;
        if ( HIDWORD(v258[2]) == 4 || HIDWORD(v258[2]) == 8 && this[26] == (CWiaItem *)this )
          goto LABEL_82;
        if ( HIDWORD(v258[2]) == 6 && !*((_QWORD *)this[8] + 12) )
          goto LABEL_143;
        if ( HIDWORD(v258[2]) == 5 )
        {
          if ( !*((_QWORD *)this[8] + 11) )
            goto LABEL_143;
LABEL_79:
          v95 = &v247[v270];
          v96 = &v23[v270];
          v94 = &v270;
          goto LABEL_83;
        }
        if ( HIDWORD(v258[2]) != 6 && *((struct CWiaItem **)this[8] + 12) != v248 )
          goto LABEL_79;
        v94 = &v245;
        v95 = &v252[v245];
        v96 = &v251[v245];
LABEL_83:
        v97 = (PROPID)v258[2];
LABEL_63:
        v95->propid = v97;
        v95->ulKind = 1;
        v98 = v273;
        *(_OWORD *)&v96->vt = 0;
        v96->bstrblobVal.pData = 0;
        v99 = &v98[v85];
        PropVariantCopy((PROPVARIANT *)v96, (const PROPVARIANT *)v99);
        if ( v254.propid == 4108 )
        {
          if ( v93 != 1 )
            goto LABEL_114;
          if ( ((v99->vt - 3) & 0xFFEF) != 0 )
          {
            RelatedDAITItem = -2147418113;
            v100 = (char *)WiaTrace_TraceLog("invalid VT for WIA_IPA_TYMED (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v100);
            WiaTrcLib::Free((WiaTrcLib *)v100, v101);
            v102 = (void **)WiaTrace_Trace("invalid VT for WIA_IPA_TYMED (0x%X)", 2147549183LL);
            goto LABEL_67;
          }
          v87 = v99->lVal == 128;
          v255 = 1;
          if ( v87 )
            v96->lVal = 2;
        }
        else if ( v254.propid == 4106 )
        {
          if ( v93 != 1 )
            goto LABEL_114;
          if ( v99->vt != 72 )
          {
            RelatedDAITItem = -2147418113;
            v111 = (char *)WiaTrace_TraceLog("invalid VT for WIA_IPA_FORMAT (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v111);
            WiaTrcLib::Free((WiaTrcLib *)v111, v112);
            v102 = (void **)WiaTrace_Trace("invalid VT for WIA_IPA_FORMAT (0x%X)", 2147549183LL);
            goto LABEL_67;
          }
          pbstrVal = v99->pbstrVal;
          LODWORD(v253) = 1;
          v107 = (char *)*pbstrVal - (char *)v265;
          if ( *pbstrVal == v265 )
            v107 = (__int64)pbstrVal[1] - v264;
          if ( !v107 )
          {
            v108 = (GUID *)CoTaskMemAlloc(0x10u);
            v96->hVal.QuadPart = (LONGLONG)v108;
            if ( v108 )
            {
              *v108 = WiaImgFmt_BMP;
              goto LABEL_114;
            }
            RelatedDAITItem = -2147024882;
            v109 = (char *)WiaTrace_TraceLog("cannot allocate memory for format GUID (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v109);
            WiaTrcLib::Free((WiaTrcLib *)v109, v110);
            v102 = (void **)WiaTrace_Trace("cannot allocate memory for format GUID (0x%X)", 2147942414LL);
LABEL_67:
            v105 = 1;
LABEL_113:
            WiaTrace_ProcessTrace_Ex(v104, v103, (void *)"CWiaItem::WriteMultipleToDAIT", v105, v102);
          }
        }
        else if ( v254.propid == 3088 && v93 == 1 )
        {
          v267 = 0;
          v113 = this[27];
          *(_OWORD *)pvar = 0;
          RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, struct tagPROPSPEC *, PROPVARIANT *))(**((_QWORD **)v113 + 1) + 24LL))(
                              *((_QWORD *)v113 + 1),
                              1,
                              &v254,
                              pvar);
          if ( RelatedDAITItem < 0 )
          {
            v120 = (char *)WiaTrace_TraceLog("ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v120);
            WiaTrcLib::Free((WiaTrcLib *)v120, v121);
            v117 = (void **)WiaTrace_Trace(
                              "ValidStg#IPropertyStorage::ReadMultiple(WIA_DPS_DOCUMENT_HANDLING_SELECT) failed (0x%X)",
                              (unsigned int)RelatedDAITItem);
LABEL_106:
            WiaTrace_ProcessTrace_Ex(v119, v118, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v117);
          }
          else
          {
            if ( ((__int64)pvar[0] & 0x1000) != 0 )
              v114 = *(_DWORD *)(v267 + 4);
            else
              v114 = (int)pvar[1];
            if ( ((v99->vt - 3) & 0xFFEF) != 0 || (v114 & v99->lVal) != v99->lVal )
            {
              RelatedDAITItem = -2147024809;
              v115 = (char *)WiaTrace_TraceLog("invalid value(s) requested for WIA_DPS_DOCUMENT_HANDLING_SELECT (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v115);
              WiaTrcLib::Free((WiaTrcLib *)v115, v116);
              v117 = (void **)WiaTrace_Trace(
                                "invalid value(s) requested for WIA_DPS_DOCUMENT_HANDLING_SELECT (0x%X)",
                                2147942487LL);
              goto LABEL_106;
            }
          }
          PropVariantClear(pvar);
          if ( RelatedDAITItem < 0 )
            goto LABEL_114;
          v122 = v99->lVal;
          if ( (v122 & 0x7D) != 0 && (v122 & 2) != 0 )
          {
            RelatedDAITItem = -2147024809;
            v123 = (char *)WiaTrace_TraceLog("WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X - flatbed AND feeder related flags c"
                                             "annot be enabled at the same time (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v123);
            WiaTrcLib::Free((WiaTrcLib *)v123, v124);
            v125 = (void **)WiaTrace_Trace(
                              "WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X - flatbed AND feeder related flags cannot be enable"
                              "d at the same time (0x%X)",
                              v99->lVal,
                              -2147024809);
            WiaTrace_ProcessTrace_Ex(v127, v126, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v125);
            goto LABEL_114;
          }
          v128 = v99->lVal & 0x7C;
          v96->lVal = v128;
          if ( (v122 & 0x7C) == 0 )
          {
            v128 = 32;
            v96->lVal = 32;
          }
          v129 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                           0,
                           0,
                           "WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X, WIA_IPS_DOCUMENT_HANDLING_SELECT: 0x%X",
                           v99->lVal,
                           v128);
          WriteDbgTraceInfoWI("CWiaItem::WriteMultipleToDAIT", v129);
          WiaTrcLib::Free((WiaTrcLib *)v129, v130);
          v102 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                            0,
                            0,
                            "WIA_DPS_DOCUMENT_HANDLING_SELECT: 0x%X, WIA_IPS_DOCUMENT_HANDLING_SELECT: 0x%X",
                            v99->lVal,
                            v96->lVal);
          v105 = 4;
          goto LABEL_113;
        }
LABEL_114:
        ++*v94;
        if ( RelatedDAITItem < 0 )
        {
          v131 = (char *)WiaTrace_TraceLog("property translation on %u failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v131);
          WiaTrcLib::Free((WiaTrcLib *)v131, v132);
          v133 = (void **)WiaTrace_Trace("property translation on %u failed (0x%X)", v254.propid, RelatedDAITItem);
LABEL_145:
          WiaTrace_ProcessTrace_Ex(v135, v134, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v133);
          v167 = 0;
          goto LABEL_174;
        }
LABEL_143:
        v23 = v250;
        v83 = v249[0] + 1;
        v34 = v244;
        LODWORD(v7) = v271;
      }
      if ( LODWORD(v258[1]) != 1 && (LODWORD(v258[1]) != 3 || this[26] != (CWiaItem *)this) )
      {
        v94 = &v245;
        v95 = &v252[v245];
        v96 = &v251[v245];
LABEL_62:
        v97 = HIDWORD(v258[0]);
        goto LABEL_63;
      }
LABEL_82:
      v94 = &v249[1];
      v95 = &v257[v249[1]];
      v96 = &v256[v249[1]];
      if ( (_DWORD)v246 != 1 )
        goto LABEL_62;
      goto LABEL_83;
    }
LABEL_146:
    v167 = 0;
    v244 = 0;
    if ( RelatedDAITItem < 0 )
      goto LABEL_174;
    if ( (_DWORD)v246 != 1 )
    {
      RelatedDAITItem = CWiaItem::GetDocumentHandling(this[8], &v244, 1);
      if ( RelatedDAITItem < 0 )
      {
        RelatedDAITItem = -2147467261;
        v168 = (char *)WiaTrace_TraceLog("failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v168);
        WiaTrcLib::Free((WiaTrcLib *)v168, v169);
        v170 = (void **)WiaTrace_Trace(
                          "failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)",
                          -2147467261);
        WiaTrace_ProcessTrace_Ex(v172, v171, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v170);
        v167 = v244;
LABEL_174:
        v189 = v247;
        v190 = v270;
        goto LABEL_175;
      }
      v167 = v244;
    }
    v173 = v249[1];
    v174 = a5;
    if ( v249[1]
      && (LogRWMultiple(0, v249[1], v257, v256, L"D-AIT (root)"),
          RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *, unsigned int))(*((_QWORD *)this[8] + 1) + 32LL))(
                              (__int64)this[8] + 8,
                              v173,
                              v257,
                              v256,
                              v174),
          RelatedDAITItem < 0) )
    {
      v175 = (char *)WiaTrace_TraceLog("WriteMultiple on root D-AIT item failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v175);
      WiaTrcLib::Free((WiaTrcLib *)v175, v176);
      v177 = (void **)WiaTrace_Trace("WriteMultiple on root D-AIT item failed (0x%X)", (unsigned int)RelatedDAITItem);
    }
    else
    {
      if ( v245 )
      {
        if ( (_DWORD)v246 == 1 )
          v180 = *((_QWORD *)this[8] + 12);
        else
          v180 = *((_QWORD *)this[26] + 10);
        if ( !v180 )
        {
          RelatedDAITItem = -2147467261;
          v181 = (char *)WiaTrace_TraceLog("NULL child #1 D-AIT item (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v181);
          WiaTrcLib::Free((WiaTrcLib *)v181, v182);
          v177 = (void **)WiaTrace_Trace("NULL child #1 D-AIT item (0x%X)", 2147500035LL);
          goto LABEL_173;
        }
        if ( (_DWORD)v246 != 1 && this != (CWiaItem **)this[26] )
        {
          RelatedDAITItem = CWiaItem::SetLegacyItemContext((CWiaItem *)this);
          if ( RelatedDAITItem < 0 )
          {
            v183 = (char *)WiaTrace_TraceLog("SetLegacyItemContext for child #1 failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v183);
            WiaTrcLib::Free((WiaTrcLib *)v183, v184);
            v177 = (void **)WiaTrace_Trace(
                              "SetLegacyItemContext for child #1 failed (0x%X)",
                              (unsigned int)RelatedDAITItem);
            goto LABEL_173;
          }
        }
        LogRWMultiple(0, v245, v252, v251, L"D-AIT (child #1)");
        RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *, unsigned int))(*(_QWORD *)(v180 + 8) + 32LL))(
                            v180 + 8,
                            v245,
                            v252,
                            v251,
                            v174);
        if ( RelatedDAITItem < 0 )
        {
          v185 = (char *)WiaTrace_TraceLog("WriteMultiple on #1 child D-AIT item failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v185);
          WiaTrcLib::Free((WiaTrcLib *)v185, v186);
          v177 = (void **)WiaTrace_Trace(
                            "WriteMultiple on #1 child D-AIT item failed (0x%X)",
                            (unsigned int)RelatedDAITItem);
          goto LABEL_173;
        }
      }
      if ( !v270 )
        goto LABEL_174;
      if ( (_DWORD)v246 == 1 )
      {
        v187 = *((_QWORD *)this[8] + 11);
        if ( v187 )
        {
          LogRWMultiple(0, v270, v247, v23, L"D-AIT (child #2)");
          lpMema = v174;
          v188 = v23;
          v189 = v247;
          v190 = v270;
          RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *, unsigned int))(*(_QWORD *)(v187 + 8) + 32LL))(
                              v187 + 8,
                              v270,
                              v247,
                              v188,
                              lpMema);
          if ( RelatedDAITItem < 0 )
          {
            v191 = (char *)WiaTrace_TraceLog("WriteMultiple on #2 child D-AIT item failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v191);
            WiaTrcLib::Free((WiaTrcLib *)v191, v192);
            v193 = (void **)WiaTrace_Trace("WriteMultiple on #2 child D-AIT item failed (0x%X)", RelatedDAITItem);
            WiaTrace_ProcessTrace_Ex(v195, v194, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v193);
          }
LABEL_175:
          v203 = v256;
          if ( v256 )
          {
            CustomFreePropVariantArray(v249[1], v256, L"Root");
            operator delete(v203, v204);
          }
          v205 = v251;
          if ( v251 )
          {
            CustomFreePropVariantArray(v245, v251, L"ChildOne");
            operator delete(v205, v206);
          }
          v207 = v250;
          if ( v250 )
          {
            CustomFreePropVariantArray(v190, v250, L"ChildTwo");
            operator delete(v207, v208);
          }
          if ( v257 )
            operator delete(v257, v32);
          if ( v252 )
            operator delete(v252, v32);
          if ( v189 )
            operator delete(v189, v32);
          if ( RelatedDAITItem < 0 )
            goto LABEL_220;
          if ( (_DWORD)v246 != 1 )
          {
            RelatedDAITItem = CWiaItem::SetDocumentHandling(this[8], v167, v33);
            if ( RelatedDAITItem >= 0 )
            {
LABEL_221:
              v16 = RelatedDAITItem;
              goto LABEL_222;
            }
            v209 = (char *)WiaTrace_TraceLog("cannot restore WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v209);
            WiaTrcLib::Free((WiaTrcLib *)v209, v210);
            v211 = (void **)WiaTrace_Trace(
                              "cannot restore WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT (0x%X)",
                              (unsigned int)RelatedDAITItem);
            goto LABEL_219;
          }
          v214 = v255;
          if ( !v255 && !(_DWORD)v253 )
            goto LABEL_221;
          *(_DWORD *)v259 = 1;
          v260 = 4106;
          v215 = this[27];
          *(_OWORD *)&v259[8] = 0;
          *(_DWORD *)&v259[16] = 1;
          memset(v258, 0, sizeof(v258));
          *(_DWORD *)&v259[8] = 4108;
          RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, PROPVARIANT *))(**(_QWORD **)v215 + 24LL))(
                              *(_QWORD *)v215,
                              2,
                              v259,
                              v258);
          if ( RelatedDAITItem >= 0 )
          {
            v221 = LODWORD(v258[1]) == 128;
            v222 = (__int64)v265 - *(_QWORD *)v258[4];
            if ( v265 == *(OLECHAR **)v258[4] )
              v222 = v264 - *((_QWORD *)v258[4] + 1);
            v223 = v222 == 0;
            if ( v223 == v221 )
              goto LABEL_214;
            if ( v214 )
            {
              v224 = (GUID *)CoTaskMemAlloc(0x10u);
              v258[4] = v224;
              if ( !v224 )
              {
                RelatedDAITItem = -2147024882;
                v228 = (char *)WiaTrace_TraceLog("cannot allocate memory for format GUID (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v228);
                WiaTrcLib::Free((WiaTrcLib *)v228, v229);
                v218 = (void **)WiaTrace_Trace("cannot allocate memory for format GUID (0x%X)", 2147942414LL);
                goto LABEL_213;
              }
              v225 = v248;
              *v224 = WiaImgFmt_BMP;
              RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, PROPVARIANT *, int))(*((_QWORD *)v225 + 1) + 32LL))(
                                  (__int64)v225 + 8,
                                  1,
                                  &v259[16],
                                  &v258[3],
                                  4098);
              if ( RelatedDAITItem < 0 )
              {
                v226 = (char *)WiaTrace_TraceLog("failed to set WiaImgFmt_BMP on D-AIT child (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v226);
                WiaTrcLib::Free((WiaTrcLib *)v226, v227);
                v218 = (void **)WiaTrace_Trace(
                                  "failed to set WiaImgFmt_BMP on D-AIT child (0x%X)",
                                  (unsigned int)RelatedDAITItem);
                goto LABEL_213;
              }
              if ( v221 )
                *(GUID *)v258[4] = WiaImgFmt_MEMORYBMP;
              else
                *(GUID *)v258[4] = WiaImgFmt_BMP;
            }
            else
            {
              LODWORD(v258[1]) = 2;
              RelatedDAITItem = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, PROPVARIANT *, int))(*((_QWORD *)v248 + 1) + 32LL))(
                                  (__int64)v248 + 8,
                                  1,
                                  v259,
                                  v258,
                                  4098);
              if ( RelatedDAITItem < 0 )
              {
                v230 = (char *)WiaTrace_TraceLog("failed to set TYMED_FILE on D-AIT child (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v230);
                WiaTrcLib::Free((WiaTrcLib *)v230, v231);
                v218 = (void **)WiaTrace_Trace(
                                  "failed to set TYMED_FILE on D-AIT child (0x%X)",
                                  (unsigned int)RelatedDAITItem);
                goto LABEL_213;
              }
              if ( v223 )
                LODWORD(v258[1]) = 128;
              else
                LODWORD(v258[1]) = v221 != 0 ? 128 : 2;
            }
            RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, PROPVARIANT *, int))(**(_QWORD **)this[27] + 32LL))(
                                *(_QWORD *)this[27],
                                2,
                                v259,
                                v258,
                                4098);
            if ( RelatedDAITItem >= 0 )
            {
LABEL_214:
              PropVariantClear(v258);
              PropVariantClear(&v258[3]);
              if ( RelatedDAITItem < 0 )
              {
LABEL_220:
                v236 = (char *)WiaTrace_TraceLog("failed to translate call to linked D-AIT item(s) (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v236);
                WiaTrcLib::Free((WiaTrcLib *)v236, v237);
                v238 = (void **)WiaTrace_Trace(
                                  "failed to translate call to linked D-AIT item(s) (0x%X)",
                                  RelatedDAITItem);
                WiaTrace_ProcessTrace_Ex(v240, v239, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v238);
                goto LABEL_221;
              }
              v262 = 0;
              v264 = 0;
              LODWORD(v264) = 1;
              *(_OWORD *)v261 = 0;
              DWORD2(v264) = 4123;
              if ( (*(int (__fastcall **)(__int64, __int64, __int128 *, PROPVARIANT *))(*((_QWORD *)v248 + 1) + 24LL))(
                     (__int64)v248 + 8,
                     1,
                     &v264,
                     v261) >= 0 )
                RelatedDAITItem = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *, int))(**(_QWORD **)this[27] + 32LL))(
                                    *(_QWORD *)this[27],
                                    1,
                                    &v264,
                                    v261,
                                    4098);
              PropVariantClear(v261);
              if ( RelatedDAITItem >= 0 )
                goto LABEL_221;
              v234 = (char *)WiaTrace_TraceLog("cannot refresh WIA_IPA_FILENAME_EXTENSION (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v234);
              WiaTrcLib::Free((WiaTrcLib *)v234, v235);
              v211 = (void **)WiaTrace_Trace(
                                "cannot refresh WIA_IPA_FILENAME_EXTENSION (0x%X)",
                                (unsigned int)RelatedDAITItem);
LABEL_219:
              WiaTrace_ProcessTrace_Ex(v213, v212, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v211);
              goto LABEL_220;
            }
            v232 = (char *)WiaTrace_TraceLog("cannot sync on A-AIT child TYMED_CALLBACK with WiaImgFmt_MEMORYBMP (2) (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v232);
            WiaTrcLib::Free((WiaTrcLib *)v232, v233);
            v218 = (void **)WiaTrace_Trace(
                              "cannot sync on A-AIT child TYMED_CALLBACK with WiaImgFmt_MEMORYBMP (2) (0x%X)",
                              (unsigned int)RelatedDAITItem);
          }
          else
          {
            v216 = (char *)WiaTrace_TraceLog("cannot sync on A-AIT child TYMED_CALLBACK with WiaImgFmt_MEMORYBMP (1) (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v216);
            WiaTrcLib::Free((WiaTrcLib *)v216, v217);
            v218 = (void **)WiaTrace_Trace(
                              "cannot sync on A-AIT child TYMED_CALLBACK with WiaImgFmt_MEMORYBMP (1) (0x%X)",
                              (unsigned int)RelatedDAITItem);
          }
LABEL_213:
          WiaTrace_ProcessTrace_Ex(v220, v219, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v218);
          goto LABEL_214;
        }
      }
      else
      {
        v196 = (char *)WiaTrace_TraceLog("not a lagacy app, there is no D-AIT child #2 (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v196);
        WiaTrcLib::Free((WiaTrcLib *)v196, v197);
        v198 = (void **)WiaTrace_Trace("not a lagacy app, there is no D-AIT child #2 (0x%X)", -2147418113);
        WiaTrace_ProcessTrace_Ex(v200, v199, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v198);
      }
      RelatedDAITItem = -2147467261;
      v201 = (char *)WiaTrace_TraceLog("NULL child #2 D-AIT item (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v201);
      WiaTrcLib::Free((WiaTrcLib *)v201, v202);
      v177 = (void **)WiaTrace_Trace("NULL child #2 D-AIT item (0x%X)", 2147500035LL);
    }
LABEL_173:
    WiaTrace_ProcessTrace_Ex(v179, v178, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v177);
    goto LABEL_174;
  }
  v11 = (char *)WiaTrace_TraceLog("called on a non-A-AIT item (E_FAIL)");
  WriteDbgTraceErrorWI("CWiaItem::WriteMultipleToDAIT", v11);
  WiaTrcLib::Free((WiaTrcLib *)v11, v12);
  v13 = (void **)WiaTrace_Trace("called on a non-A-AIT item (E_FAIL)");
  WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CWiaItem::WriteMultipleToDAIT", 1, v13);
  v16 = -2147467259;
LABEL_222:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v269);
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
