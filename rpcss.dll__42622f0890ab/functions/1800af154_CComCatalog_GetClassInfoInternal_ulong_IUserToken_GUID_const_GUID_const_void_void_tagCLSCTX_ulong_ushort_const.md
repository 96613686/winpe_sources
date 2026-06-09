# CComCatalog::GetClassInfoInternal(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *,tagCLSCTX,ulong,ushort const *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)

- ea: `0x1800af154`
- end: `0x1800b23e4`
- name: `?GetClassInfoInternal@CComCatalog@@AEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAXW4tagCLSCTX@@KPEBG5IQEBQEAUHSTRING__@@I6@Z`
- size: `12944`
- prototype: `__int64 __fastcall(CComCatalog *this, unsigned int, struct IUserToken *, struct _GUID *, GUID *, void **, void *, enum tagCLSCTX, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned int, HSTRING *const, unsigned int, HSTRING *const)`
- caller_count: `4`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007a110`
- `0x1800af000`
- `0x1800af090`
- `0x1800c9850`

## callees

- `0x180003064`
- `0x180005c40`
- `0x180009f1c`
- `0x18000b428`
- `0x18000f1b8`
- `0x18000fe24`
- `0x180029a54`
- `0x18002ba28`
- `0x18002da44`
- `0x180034540`
- `0x1800382ac`
- `0x180039088`
- `0x18003ffd0`
- `0x180040580`
- `0x180040990`
- `0x18004778c`
- `0x18005d538`
- `0x18005f740`
- `0x18006548c`
- `0x180069c80`
- `0x18006d90c`
- `0x1800795dc`
- `0x18007a610`
- `0x18007afa8`
- `0x18008150c`
- `0x18008e98c`
- `0x180092858`
- `0x18009d760`
- `0x1800ad900`
- `0x1800ad95c`
- `0x1800adb24`
- `0x1800af154`
- `0x1800b27e0`
- `0x1800c73bc`
- `0x1800c74d8`
- `0x1800c768c`
- `0x1800ca424`
- `0x1800caa58`
- `0x1800cdf80`
- `0x1800cea8c`
- `0x1800cf120`
- `0x18010b010`

## string_xrefs

- `0x1800af281`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1800af321`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1800af47e`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1800af505`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1800af753`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1800af984`: `onecore\com\combase\catalog\catalog.cxx`
- `0x1800af9f6`: `CComCatalog::GetClassInfoInternal`
- `0x1800afaa4`: `CComCatalog::GetClassInfoInternal`
- `0x1800afbb0`: `CComCatalog::GetClassInfoInternal`
- `0x1800afd6a`: `CComCatalog::GetClassInfoInternal`
- `0x1800afe15`: `CComCatalog::GetClassInfoInternal`
- `0x1800afeb8`: `CComCatalog::GetClassInfoInternal`
- `0x1800affed`: `CComCatalog::GetClassInfoInternal`
- `0x1800b0132`: `CComCatalog::GetClassInfoInternal`
- `0x1800b01e5`: `CComCatalog::GetClassInfoInternal`
- `0x1800b0331`: `CComCatalog::GetClassInfoInternal`
- `0x1800b0423`: `CComCatalog::GetClassInfoInternal`
- `0x1800b04b8`: `CComCatalog::GetClassInfoInternal`
- `0x1800b0793`: `CComCatalog::GetClassInfoInternal`
- `0x1800b0837`: `CComCatalog::GetClassInfoInternal`
- `0x1800b091a`: `CComCatalog::GetClassInfoInternal`
- `0x1800b09b6`: `CComCatalog::GetClassInfoInternal`
- `0x1800b0ab7`: `CComCatalog::GetClassInfoInternal`
- `0x1800b0d89`: `CComCatalog::GetClassInfoInternal`
- `0x1800b10d9`: `CComCatalog::GetClassInfoInternal`
- `0x1800b1190`: `CComCatalog::GetClassInfoInternal`
- `0x1800b1272`: `CComCatalog::GetClassInfoInternal`
- `0x1800b1329`: `CComCatalog::GetClassInfoInternal`
- `0x1800b1406`: `CComCatalog::GetClassInfoInternal`
- `0x1800b14b9`: `CComCatalog::GetClassInfoInternal`
- `0x1800b1ab1`: `CComCatalog::GetClassInfoInternal`
- `0x1800b1bd2`: `CComCatalog::GetClassInfoInternal`
- `0x1800b1e9c`: `CComCatalog::GetClassInfoInternal`
- `0x1800b1f43`: `CComCatalog::GetClassInfoInternal`
- `0x1800b2245`: `CComCatalog::GetClassInfoInternal`
- `0x1800afaab`: `Found %ls in COM SxS Catalog`
- `0x1800af9fd`: `Look for %ls in COM SxS Catalog...`
- `0x1800afbb7`: `Look for %ls in COM SxS Catalog...`
- `0x1800afce1`: `Look for %ls in PackagedCom current package Catalog...`
- `0x1800b1ab8`: `Look for %ls in PackagedCom current package Catalog...`
- `0x1800afb36`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x1800b009a`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x1800b0e26`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x1800b1c70`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x1800b1e1a`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x1800b21d8`: `CLSID:%ls Flags:%#x IID:%ls`
- `0x1800afff4`: `Found %ls in PackagedCom current package Catalog`
- `0x1800b01ec`: `Found %ls in PackagedCom current package Catalog`
- `0x1800b1bd9`: `Found %ls in PackagedCom current package Catalog`
- `0x1800b0338`: `Found %ls in cache`
- `0x1800b04bf`: `Found %ls in cache`
- `0x1800b042a`: `Look for %ls in cache...`
- `0x1800b0921`: `Look for %ls in COM Base CLB...`
- `0x1800b0a49`: `Look for %ls in PackagedCom all packages Catalog...`
- `0x1800b1ea3`: `Look for %ls in PackagedCom all packages Catalog...`
- `0x1800b09bd`: `Found %ls in COM Base CLB`
- `0x1800b10e0`: `Look for %ls in registry...`
- `0x1800b0d90`: `Found %ls in PackagedCom all packages Catalog`
- `0x1800b1f4a`: `Found %ls in PackagedCom all packages Catalog`
- `0x1800b1279`: `Look for %ls in x86 WOW registry...`
- `0x1800b1197`: `Found %ls in registry`
- `0x1800b140d`: `Look for %ls in ARM32 WOW registry...`
- `0x1800b1330`: `Found %ls in x86 WOW registry`
- `0x1800b14c0`: `Found %ls in ARM32 WOW registry`
- `0x1800b224c`: `Adding %ls to cache...`

## pseudocode

```c
__int64 __fastcall CComCatalog::GetClassInfoInternal(
        CComCatalog *this,
        unsigned int a2,
        struct IUserToken *a3,
        struct _GUID *a4,
        GUID *a5,
        void **a6,
        void *a7,
        enum tagCLSCTX a8,
        unsigned int a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11,
        unsigned int a12,
        HSTRING *const a13,
        unsigned int a14,
        HSTRING *const a15)
{
  int v17; // r13d
  int v18; // r12d
  unsigned int ProxyStubClassInfoFromPackageScopedCatalog; // edi
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  int v22; // edx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rbx
  int v29; // eax
  __int64 PackagedComCurrentPackageProvider; // rax
  struct IUserToken *v31; // r14
  int IsPackageInCurrentPackageGraph; // eax
  __int64 v33; // rdx
  __int64 v34; // r9
  struct IUserTokenInternal *v35; // rdx
  __int64 (__fastcall **v36)(struct IUserToken *, GUID *, struct IUserTokenInternal **); // rax
  __int64 (__fastcall *v37)(struct IUserToken *, GUID *, struct IUserTokenInternal **); // rdi
  __int64 v38; // rcx
  unsigned int v39; // eax
  char v40; // r14
  unsigned int v41; // edi
  unsigned int v42; // ecx
  char IsEnabled; // al
  unsigned __int16 *v44; // rdi
  char v45; // al
  __int64 v46; // rcx
  unsigned __int16 *v47; // r15
  char v48; // di
  char v49; // si
  int PackageFamilyName; // eax
  __int64 v51; // rdx
  bool v52; // di
  char v53; // r15
  bool v54; // r15
  CComCatalog *v55; // rcx
  CComCatalog *v56; // rbx
  void **v57; // r15
  struct _GUID *v58; // r14
  GUID *v59; // rsi
  CComCatalog *v60; // rcx
  char v61; // al
  __int64 v62; // rdx
  __int64 v63; // r8
  CComCatalog *v64; // rdi
  int v65; // r9d
  __int64 v66; // rsi
  __int64 (__fastcall *v67)(__int64, _QWORD, struct IUserToken *, GUID *); // rdi
  int v68; // r8d
  int v69; // r9d
  int v70; // r8d
  int v71; // r13d
  __int64 v72; // rdx
  int v73; // r9d
  __int64 v74; // rsi
  __int64 (__fastcall *v75)(__int64, _QWORD, struct IUserToken *, GUID *); // rdi
  int v76; // r8d
  char v77; // al
  __int64 v78; // rdx
  __int64 v79; // r8
  const char *v80; // r9
  __int64 v81; // rdx
  __int64 v82; // r8
  int v83; // r15d
  __int64 v84; // r8
  CComCatalog *v85; // r13
  __int64 v86; // rsi
  __int64 (__fastcall *v87)(__int64, _QWORD, struct IUserToken *, GUID *); // rdi
  GUID *v88; // r12
  enum tagCLSCTX v89; // r15d
  int v90; // eax
  __int64 v91; // rdx
  __int64 v92; // r8
  HSTRING **v93; // rcx
  __int64 v94; // rsi
  __int64 (__fastcall *v95)(__int64, _QWORD, _QWORD, struct IUserTokenInternal *); // rdi
  int v96; // eax
  unsigned int v97; // r15d
  __int64 v98; // r9
  __int64 v99; // rsi
  __int64 (__fastcall *v100)(__int64, _QWORD, struct IUserToken *, GUID *); // rdi
  struct IUnknown *v101; // rdx
  __int64 v102; // r8
  int NoClassInfo; // eax
  __int64 v104; // rdx
  __int64 v105; // rdx
  __int64 v106; // r8
  int v107; // edi
  unsigned int v108; // esi
  __int64 *v109; // rsi
  __int64 v110; // rax
  __int64 (__fastcall *v111)(__int64 *, _QWORD, struct IUserToken *, GUID *); // rdi
  __int64 v112; // rdx
  __int64 v113; // r8
  bool v114; // zf
  CComCatalog *v115; // rdi
  __int64 *v116; // rsi
  int v117; // r13d
  __int64 v118; // rax
  __int64 (__fastcall *v119)(__int64 *, _QWORD, struct IUserToken *, GUID *); // rdi
  unsigned int v120; // edi
  int v121; // esi
  __int64 v122; // rsi
  __int64 (__fastcall *v123)(__int64, _QWORD, struct IUserToken *, GUID *); // rdi
  int v124; // r9d
  __int64 v125; // rsi
  __int64 (__fastcall *v126)(__int64, _QWORD, struct IUserToken *, GUID *); // rdi
  char v127; // al
  __int64 v128; // rdx
  __int64 v129; // r8
  int v130; // r9d
  __int64 v131; // r10
  __int64 v132; // rdx
  __int64 v133; // r8
  __int64 v134; // rcx
  int v135; // eax
  __int64 v136; // rdx
  __int64 v137; // r8
  __int64 v138; // rsi
  __int64 (__fastcall *v139)(__int64, _QWORD, _QWORD, struct IUserTokenInternal *); // rdi
  GUID *v140; // r15
  unsigned int v141; // eax
  __int64 v142; // rsi
  __int64 (__fastcall *v143)(__int64, _QWORD, struct IUserToken *, GUID *); // rdi
  __int64 v144; // rdx
  __int64 v145; // r8
  __int64 v146; // rsi
  __int64 (__fastcall *v147)(__int64, _QWORD, __int64, struct IUserTokenInternal *); // rdi
  unsigned int v148; // eax
  __int64 v149; // rsi
  __int64 (__fastcall *v150)(__int64, __int64, struct IUserToken *, GUID *); // rdi
  __int64 v151; // rdx
  __int64 v152; // rdx
  __int64 v153; // r8
  __int64 v154; // rdx
  __int64 v155; // r8
  unsigned int v156; // edi
  CComCatalog *v157; // r15
  int v158; // esi
  void *v159; // rdi
  int v160; // r12d
  void *v161; // rdi
  int v162; // eax
  __int64 v163; // rdx
  __int64 v164; // r8
  bool v165; // r13
  unsigned __int16 NativeArchitecture; // ax
  bool v167; // cl
  unsigned __int16 v168; // ax
  unsigned __int16 v169; // ax
  __int64 v170; // rdi
  char *v171; // rsi
  __int64 (__fastcall *v172)(__int64, __int64, struct IUserToken *, GUID *); // r15
  __int64 v173; // rdx
  int v174; // r8d
  int v175; // ecx
  int v176; // r13d
  __int64 v177; // rdi
  char *v178; // rsi
  __int64 (__fastcall *v179)(__int64, __int64, struct IUserToken *, GUID *); // r15
  __int64 v180; // rdx
  int v181; // r8d
  __int64 v182; // rdi
  char *v183; // rsi
  __int64 (__fastcall *v184)(__int64, __int64, struct IUserToken *, GUID *); // r15
  __int64 v185; // rdx
  struct IUnknown *v186; // r8
  struct IUnknown **v187; // rdx
  unsigned int v188; // edi
  struct IUnknown **v189; // rdx
  __int64 v190; // r8
  __int64 v191; // rcx
  struct IUnknown **v192; // rdx
  unsigned __int16 v193; // ax
  struct IUnknown **v194; // rdx
  struct IUnknown **v195; // rax
  struct IUnknown **v196; // rax
  __int64 v197; // rcx
  __int64 v198; // rdx
  __int64 v199; // rcx
  char v200; // al
  __int64 v201; // rdx
  __int64 v202; // r8
  CComCatalog *v203; // rsi
  __int64 *v204; // r15
  int v205; // r13d
  __int64 v206; // rax
  __int64 (__fastcall *v207)(__int64 *, _QWORD, struct IUserToken *, GUID *); // rdi
  __int64 *v208; // r15
  __int64 v209; // rax
  __int64 (__fastcall *v210)(__int64 *, _QWORD, struct IUserToken *, GUID *); // rdi
  int v211; // eax
  __int64 v212; // rdx
  __int64 v213; // r8
  __int64 v214; // r9
  int v215; // eax
  __int64 v216; // rdx
  __int64 v217; // r8
  CComCatalog *v218; // rdi
  __int64 (__fastcall *v219)(CComCatalog *, _QWORD, _QWORD, struct IUserTokenInternal *); // rbx
  GUID *v220; // r15
  int v221; // eax
  int v222; // r8d
  __int64 (__fastcall ***v223)(_QWORD, GUID *, __int64 *); // rcx
  int v224; // eax
  __int64 v225; // rdx
  __int64 v226; // r8
  __int64 v227; // rdi
  __int64 (__fastcall *v228)(__int64, _QWORD, _QWORD, struct IUserTokenInternal *); // rbx
  int v229; // eax
  struct IUserToken *v230; // rsi
  __int64 v231; // rdi
  __int64 (__fastcall *v232)(__int64, _QWORD, struct IUserToken *, GUID *); // rbx
  char *v233; // rcx
  struct _GUID *v234; // rbx
  __int64 v235; // rdx
  int v236; // ecx
  __int64 v237; // r8
  int v238; // r9d
  bool v239; // di
  __int64 v240; // rdx
  __int64 v241; // r8
  __int64 v242; // rdx
  __int64 v243; // r8
  int v244; // eax
  __int64 v245; // rdx
  char v246; // cl
  __int64 v247; // rdx
  __int64 v248; // r8
  int v249; // eax
  struct IUnknown *v250; // rax
  int v252; // [rsp+20h] [rbp-E0h]
  struct _GUID *v253; // [rsp+28h] [rbp-D8h]
  struct IUnknown **v254; // [rsp+30h] [rbp-D0h]
  struct IUnknown **v255; // [rsp+30h] [rbp-D0h]
  struct IUnknown **v256; // [rsp+30h] [rbp-D0h]
  struct IUnknown **v257; // [rsp+30h] [rbp-D0h]
  struct IUnknown **v258; // [rsp+30h] [rbp-D0h]
  struct IUnknown **v259; // [rsp+30h] [rbp-D0h]
  unsigned int v260; // [rsp+70h] [rbp-90h] BYREF
  struct IUnknown *v261; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v262[2]; // [rsp+80h] [rbp-80h] BYREF
  bool v263; // [rsp+84h] [rbp-7Ch] BYREF
  char v264; // [rsp+85h] [rbp-7Bh]
  bool v265; // [rsp+86h] [rbp-7Ah] BYREF
  int v266; // [rsp+88h] [rbp-78h]
  bool v267; // [rsp+8Ch] [rbp-74h]
  char v268; // [rsp+8Dh] [rbp-73h]
  int v269; // [rsp+90h] [rbp-70h]
  GUID *rguid; // [rsp+98h] [rbp-68h]
  struct _GUID *v271; // [rsp+A0h] [rbp-60h]
  CComCatalog *v272; // [rsp+A8h] [rbp-58h] BYREF
  struct IUserTokenInternal *v273; // [rsp+B0h] [rbp-50h] BYREF
  int ClassInfoW; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v275; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v276; // [rsp+C8h] [rbp-38h]
  _DWORD v277[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v278; // [rsp+D8h] [rbp-28h]
  __int64 v279; // [rsp+E0h] [rbp-20h]
  int v280; // [rsp+E8h] [rbp-18h] BYREF
  int (__fastcall ***v281)(_QWORD, GUID *, struct IUnknown ***); // [rsp+F0h] [rbp-10h] BYREF
  struct IUserToken *v282; // [rsp+F8h] [rbp-8h]
  __int64 v283; // [rsp+100h] [rbp+0h] BYREF
  struct IUnknown **v284; // [rsp+108h] [rbp+8h] BYREF
  HSTRING *v285; // [rsp+110h] [rbp+10h] BYREF
  struct IUnknown *v286; // [rsp+118h] [rbp+18h] BYREF
  bool v287; // [rsp+120h] [rbp+20h] BYREF
  int v288; // [rsp+124h] [rbp+24h]
  unsigned __int16 v289[2]; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 v290; // [rsp+12Ch] [rbp+2Ch] BYREF
  unsigned int v291; // [rsp+130h] [rbp+30h] BYREF
  __int64 v292; // [rsp+138h] [rbp+38h] BYREF
  struct IUnknown *v293; // [rsp+140h] [rbp+40h] BYREF
  bool v294; // [rsp+148h] [rbp+48h]
  int v295; // [rsp+14Ch] [rbp+4Ch]
  struct IUnknown *v296; // [rsp+150h] [rbp+50h] BYREF
  bool v297; // [rsp+158h] [rbp+58h]
  int v298; // [rsp+15Ch] [rbp+5Ch]
  unsigned __int16 *v299; // [rsp+160h] [rbp+60h]
  unsigned __int16 *v300; // [rsp+168h] [rbp+68h]
  unsigned __int16 v301[4]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 *v302; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v303[2]; // [rsp+180h] [rbp+80h] BYREF
  void **v304; // [rsp+190h] [rbp+90h]
  __int128 v305; // [rsp+198h] [rbp+98h]
  struct IUnknown **v306; // [rsp+1A8h] [rbp+A8h]
  unsigned int v307; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int8 *v308; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned __int8 *v309; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int8 *v310[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  _QWORD v311[4]; // [rsp+1E8h] [rbp+E8h] BYREF
  char v312; // [rsp+208h] [rbp+108h]
  OLECHAR sz[40]; // [rsp+210h] [rbp+110h] BYREF
  OLECHAR v314[40]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v304 = a6;
  v17 = 0;
  v18 = 0;
  v300 = a10;
  v285 = a13;
  v303[1] = a15;
  v311[0] = &ClassInfoW;
  v311[1] = &v280;
  v311[3] = &v260;
  rguid = a4;
  v282 = a3;
  v272 = this;
  v260 = a2;
  v271 = a5;
  v299 = a11;
  ClassInfoW = 0;
  v280 = 0;
  v311[2] = a4;
  v312 = 1;
  v269 = 0;
  v262[0] = 0;
  v309 = 0;
  v289[0] = 0;
  v308 = 0;
  v290 = 0;
  v286 = 0;
  v287 = 0;
  v288 = 128;
  v296 = 0;
  v297 = 0;
  v298 = 256;
  v293 = 0;
  v294 = 0;
  v295 = 512;
  v278 = 0;
  v279 = 0;
  v277[0] = a2;
  if ( (a2 & 0xCE8) == 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( a12 && !v285 )
      {
        ProxyStubClassInfoFromPackageScopedCatalog = -2147024809;
        v20 = 3355;
LABEL_10:
        v21 = ProxyStubClassInfoFromPackageScopedCatalog;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
          (const char *)v21,
          v252);
LABEL_612:
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v293);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v296);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v286);
        v312 = 0;
        goto LABEL_613;
      }
      if ( (a8 & 0xFFFFFFE8) != 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v260);
        v20 = 3358;
LABEL_9:
        ProxyStubClassInfoFromPackageScopedCatalog = -2147418113;
        goto LABEL_10;
      }
      if ( (a9 & 0xCFF) != 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v260);
        v20 = 3359;
        goto LABEL_9;
      }
      if ( (v260 & 0x17) != 0 )
      {
        if ( a8 != (v260 & 0x17) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v260);
          v20 = 3377;
          goto LABEL_9;
        }
      }
      else if ( a8 != (CLSCTX_REMOTE_SERVER|CLSCTX_LOCAL_SERVER|CLSCTX_INPROC_HANDLER|CLSCTX_INPROC_SERVER) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v260);
        v20 = 3373;
        goto LABEL_9;
      }
      if ( a9 != (v260 & 0xFFFFF300) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v260);
        v20 = 3381;
        goto LABEL_9;
      }
      if ( v300 && a11 )
      {
        ProxyStubClassInfoFromPackageScopedCatalog = -2147024809;
        v20 = 3384;
        goto LABEL_10;
      }
    }
    v276 = v260 & 0x200000;
    LODWORD(v283) = v260 & 0x8000000;
    GuidString::GuidString(sz, a4);
    GuidString::GuidString(v314, a5);
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
    {
      v253 = (struct _GUID *)sz;
      ComTraceMessageT<unsigned short const *,unsigned long,unsigned short const *>(v23, v22, v24, v25);
    }
    *v304 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && !CComCatalog::ms_fInitialized )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v26);
    }
    v27 = CComCatalog::InitializeCatalogIfNecessary(this);
    ProxyStubClassInfoFromPackageScopedCatalog = v27;
    if ( v27 < 0 )
    {
      v21 = (unsigned int)v27;
      v20 = 3411;
      goto LABEL_11;
    }
    v28 = 0;
    v275 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      v29 = CComCatalog::InitializePackagedComCurrentPackageProviderIfNecessary(this, 0);
      ProxyStubClassInfoFromPackageScopedCatalog = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD58,
          (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
          (const char *)(unsigned int)v29,
          v252);
LABEL_35:
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v275);
        goto LABEL_612;
      }
      PackagedComCurrentPackageProvider = CComCatalog::GetPackagedComCurrentPackageProvider(this, &v302);
      wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(
        &v275,
        PackagedComCurrentPackageProvider);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v302);
      v28 = v275;
    }
    v31 = v282;
    v273 = 0;
    if ( v282 )
    {
      IsPackageInCurrentPackageGraph = (*(__int64 (__fastcall **)(struct IUserToken *, unsigned __int8 **, unsigned __int16 *))(*(_QWORD *)v282 + 40LL))(
                                         v282,
                                         &v309,
                                         v289);
      ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
      if ( IsPackageInCurrentPackageGraph < 0 )
      {
        v33 = 3428;
LABEL_40:
        v34 = (unsigned int)IsPackageInCurrentPackageGraph;
LABEL_41:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
          (const char *)v34,
          v252);
LABEL_42:
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v273);
        goto LABEL_35;
      }
      IsPackageInCurrentPackageGraph = (*(__int64 (__fastcall **)(struct IUserToken *, unsigned __int8 **, unsigned __int16 *))(*(_QWORD *)v31 + 56LL))(
                                         v31,
                                         &v308,
                                         &v290);
      ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
      if ( IsPackageInCurrentPackageGraph < 0 )
      {
        v33 = 3429;
        goto LABEL_40;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
      {
        v35 = v273;
        v36 = *(__int64 (__fastcall ***)(struct IUserToken *, GUID *, struct IUserTokenInternal **))v31;
        v273 = 0;
        v37 = *v36;
        if ( v35 )
          (*(void (__fastcall **)(struct IUserTokenInternal *))(*(_QWORD *)v35 + 16LL))(v35);
        ProxyStubClassInfoFromPackageScopedCatalog = v37(v31, &GUID_000001fc_0000_0000_cfff_123045660046, &v273);
        if ( (ProxyStubClassInfoFromPackageScopedCatalog & 0x80000000) != 0 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v38);
          v34 = ProxyStubClassInfoFromPackageScopedCatalog;
          v33 = 3435;
          goto LABEL_41;
        }
      }
    }
    v39 = CComCatalog::FlagsForCacheKey(v260);
    v310[0] = (unsigned __int8 *)a4;
    v307 = v39 & 0xF7FFFFFF;
    v277[1] = v39 & 0xF7FFFFFF;
    v310[1] = v309;
    v310[2] = v308;
    v310[3] = (unsigned __int8 *)&v307;
    v301[0] = 16;
    v301[1] = v289[0];
    v301[2] = v290;
    v301[3] = 4;
    v40 = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      v41 = a9 >> 9;
      v42 = v260 & 0xFFFFFDFF;
      LOBYTE(v41) = (a9 & 0x200) != 0;
      v291 = v41;
    }
    else
    {
      v42 = v260 & 0xFFFFFDFF;
      LOBYTE(v291) = (v260 & 0x200) != 0;
    }
    v260 = v42;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v44 = v300;
    if ( IsEnabled )
    {
      if ( !v300 && !v299 && !a12 && !a14 )
        v40 = 0;
      LOBYTE(v266) = v40;
    }
    else
    {
      v40 = 0;
      LOBYTE(v266) = 0;
    }
    v45 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v46 = 0;
    if ( !v45 )
    {
      v48 = 0;
      v264 = 0;
      goto LABEL_91;
    }
    v47 = v299;
    if ( !v44 && !v299 )
    {
      v264 = 0;
LABEL_65:
      v48 = v264;
LABEL_91:
      v49 = 0;
      v265 = 0;
      v267 = 0;
LABEL_92:
      v268 = 0;
      goto LABEL_93;
    }
    v264 = 1;
    if ( v44 )
    {
      if ( (a9 & 0x4000) != 0 )
      {
        v263 = 0;
        IsPackageInCurrentPackageGraph = GetIsPackageInCurrentPackageGraph(v44, v273, a12, v285, &v263);
        v46 = 0;
        ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
        if ( IsPackageInCurrentPackageGraph < 0 )
        {
          v33 = 3562;
          goto LABEL_40;
        }
        v267 = !v263;
      }
      else
      {
        v267 = 1;
      }
      v48 = v264;
      v49 = 1;
      v265 = 1;
      goto LABEL_92;
    }
    if ( !v299 )
      goto LABEL_65;
    v302 = 0;
    PackageFamilyName = TryGetPackageFamilyName(v273, &v302);
    ProxyStubClassInfoFromPackageScopedCatalog = PackageFamilyName;
    if ( PackageFamilyName < 0 )
    {
      v51 = 3589;
LABEL_76:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v51,
        (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
        (const char *)(unsigned int)PackageFamilyName,
        v252);
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v302);
      goto LABEL_42;
    }
    if ( v302 && PackageNamesMatch(v47, v302) )
    {
      if ( g_bInSCM )
      {
        v52 = 1;
      }
      else
      {
        LODWORD(v281) = 0;
        PackageFamilyName = AppModelPolicy_GetPolicy(-4, 16, &v281);
        ProxyStubClassInfoFromPackageScopedCatalog = PackageFamilyName;
        if ( PackageFamilyName < 0 )
        {
          v51 = 3619;
          goto LABEL_76;
        }
        v52 = (_DWORD)v281 != 1048577;
      }
      v53 = 0;
      v265 = v52;
      v267 = 0;
      v268 = 1;
    }
    else
    {
      v268 = 0;
      v53 = 1;
      v267 = 1;
      v52 = 1;
      v265 = 1;
    }
    v49 = v53;
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v302);
    v264 = 1;
    if ( v53 )
    {
      v260 &= ~0x1000u;
    }
    else
    {
      v267 = 0;
      v265 = v52;
    }
    v48 = v264;
LABEL_93:
    v54 = 1;
    v263 = 1;
    if ( (v260 & 0x80000) == 0 )
      goto LABEL_102;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( v48 )
      {
        v54 = 0;
        goto LABEL_102;
      }
      IsPackageInCurrentPackageGraph = IsAllowListedCLSID(rguid, &v263);
      ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
      if ( IsPackageInCurrentPackageGraph < 0 )
      {
        v33 = 3700;
        goto LABEL_40;
      }
    }
    else
    {
      IsPackageInCurrentPackageGraph = IsAllowListedCLSID(rguid, &v263);
      ProxyStubClassInfoFromPackageScopedCatalog = IsPackageInCurrentPackageGraph;
      if ( IsPackageInCurrentPackageGraph < 0 )
      {
        v33 = 3705;
        goto LABEL_40;
      }
    }
    v54 = v263;
LABEL_102:
    if ( ((v260 ^ (v260 >> 4)) & 0x40000) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v46);
    if ( (v260 & 0x440000) == 0x440000 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
        && v40 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v55);
        ProxyStubClassInfoFromPackageScopedCatalog = -2147418113;
        v33 = 3728;
        v34 = 2147549183LL;
        goto LABEL_41;
      }
      v56 = v272;
      v57 = v304;
      v58 = v271;
      v59 = rguid;
      ProxyStubClassInfoFromPackageScopedCatalog = CComCatalog::GetProxyStubClassInfoFromPackageScopedCatalog(
                                                     v55,
                                                     v260,
                                                     rguid,
                                                     *((struct IComCatalogInternal **)v272 + 21),
                                                     (struct CCache *)s_pCacheInboxAppProxyStubClassInfo,
                                                     v271,
                                                     v304);
      if ( ProxyStubClassInfoFromPackageScopedCatalog == -2147221164 )
        ProxyStubClassInfoFromPackageScopedCatalog = CComCatalog::GetProxyStubClassInfoFromPackageScopedCatalog(
                                                       v60,
                                                       v260,
                                                       v59,
                                                       *((struct IComCatalogInternal **)v56 + 20),
                                                       (struct CCache *)s_pCachePerUserProxyStubClassInfo,
                                                       v58,
                                                       v57);
      if ( (ProxyStubClassInfoFromPackageScopedCatalog & 0x80000000) != 0 )
      {
        v34 = ProxyStubClassInfoFromPackageScopedCatalog;
        v33 = 3739;
        goto LABEL_41;
      }
LABEL_611:
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v273);
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v275);
      ProxyStubClassInfoFromPackageScopedCatalog = 0;
      goto LABEL_612;
    }
    v261 = 0;
    v61 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v63 = 0;
    if ( v61 )
    {
      if ( !(_DWORD)v283 || v276 )
      {
        v64 = v272;
        if ( !*((_QWORD *)v272 + 18) || v49 )
        {
LABEL_147:
          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v62, v63);
          if ( !v54 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xEF2,
              (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
              (const char *)0x80040154LL,
              v252);
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v261);
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v273);
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v275);
            ProxyStubClassInfoFromPackageScopedCatalog = -2147221164;
            goto LABEL_612;
          }
          LODWORD(v281) = v260 & 0x80000;
          v77 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
          v80 = L"Look for %ls in PackagedCom current package Catalog...";
          if ( v77 )
          {
            if ( v267 )
              goto LABEL_153;
            v79 = (unsigned int)g_bInSCM;
            if ( g_bInSCM )
            {
              if ( (v260 & 0x2000) == 0 )
                goto LABEL_153;
            }
            else if ( !v28 || (v260 & 1) == 0 )
            {
              goto LABEL_153;
            }
            v280 = 2;
            LODWORD(v278) = v17 | 2;
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
            {
              ComTraceMessageT<unsigned short const *>(
                (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                (unsigned int)"CComCatalog::GetClassInfoInternal",
                3880,
                4,
                (__int64)v80);
              v79 = (unsigned int)g_bInSCM;
            }
            v89 = a8;
            if ( !(_DWORD)v79 )
              v89 = a8 & 1;
            v303[0] = 0;
            v90 = wil::com_query_to_nothrow<IComCatalogPackageAware,wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> &>(
                    &v275,
                    v303,
                    v79,
                    v80);
            ProxyStubClassInfoFromPackageScopedCatalog = v90;
            if ( v90 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF37,
                (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                (const char *)(unsigned int)v90,
                v252);
LABEL_173:
              v93 = (HSTRING **)v303;
LABEL_463:
              wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v93);
              goto LABEL_131;
            }
            v94 = v303[0];
            v95 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct IUserTokenInternal *))(*(_QWORD *)v303[0]
                                                                                                 + 24LL);
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v91, v92);
            HIDWORD(v255) = HIDWORD(v299);
            LODWORD(v253) = (_DWORD)v300;
            v252 = (int)rguid;
            v96 = v95(v94, (unsigned int)v89, 0, v273);
            ClassInfoW = v96;
            ProxyStubClassInfoFromPackageScopedCatalog = v96;
            if ( v96 )
            {
              if ( v96 != -2147221164 )
              {
                if ( v96 < 0 )
                {
                  LODWORD(v255) = v260;
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    (void *)0xF4E,
                    (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                    (const char *)(unsigned int)v96,
                    (int)"CLSID:%ls Flags:%#x IID:%ls",
                    (const char *)sz,
                    v255,
                    v314);
                }
                goto LABEL_173;
              }
            }
            else
            {
              v18 |= 2u;
              HIDWORD(v278) = v18;
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                v253 = (struct _GUID *)sz;
                ComTraceMessageT<unsigned short const *>(
                  (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                  (unsigned int)"CComCatalog::GetClassInfoInternal",
                  3905,
                  4,
                  (__int64)L"Found %ls in PackagedCom current package Catalog");
              }
              LOWORD(v71) = 256;
              v269 = 256;
              v262[0] = 256;
              if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
              {
                v279 = 0x200000002LL;
                wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v303);
LABEL_180:
                v88 = rguid;
                goto LABEL_581;
              }
            }
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(v303);
          }
          else
          {
            v79 = (unsigned int)g_bInSCM;
            if ( g_bInSCM )
            {
              v97 = v260;
              if ( (v260 & 0x2000) == 0 )
                goto LABEL_153;
            }
            else
            {
              if ( !*((_QWORD *)v64 + 25) )
                goto LABEL_153;
              v97 = v260;
              if ( (v260 & 1) == 0 )
                goto LABEL_153;
            }
            v280 = 2;
            LODWORD(v278) = v17 | 2;
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
            {
              ComTraceMessageT<unsigned short const *>(
                (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                (unsigned int)"CComCatalog::GetClassInfoInternal",
                3931,
                4,
                v98,
                sz);
              v79 = (unsigned int)g_bInSCM;
              v97 = v260;
            }
            if ( !(_DWORD)v79 )
              v97 &= 0xFFFFF301;
            v99 = *((_QWORD *)v64 + 25);
            v100 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUserToken *, GUID *))(*(_QWORD *)v99 + 24LL);
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v78, v79);
            HIDWORD(v254) = 0;
            v253 = (struct _GUID *)&v261;
            v252 = (int)v271;
            ClassInfoW = v100(v99, v97, v282, rguid);
            ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
            if ( ClassInfoW )
            {
              if ( ClassInfoW != -2147221164 )
              {
                if ( ClassInfoW >= 0 )
                  goto LABEL_131;
                v72 = 3961;
                goto LABEL_130;
              }
            }
            else
            {
              v18 |= 2u;
              HIDWORD(v278) = v18;
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                v253 = (struct _GUID *)sz;
                ComTraceMessageT<unsigned short const *>(
                  (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                  (unsigned int)"CComCatalog::GetClassInfoInternal",
                  3950,
                  4,
                  (__int64)L"Found %ls in PackagedCom current package Catalog");
              }
              LOWORD(v71) = 256;
              v269 = 256;
              v262[0] = 256;
              if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
              {
                v279 = 0x200000002LL;
                goto LABEL_180;
              }
            }
          }
LABEL_153:
          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v78, v79);
          v83 = v278;
          if ( (v260 & 0x1000) != 0 )
          {
            v84 = 4;
            v83 = v278 | 4;
            v280 = 4;
            LODWORD(v278) = v278 | 4;
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              ComTraceMessageT<unsigned short const *>(
                (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                (unsigned int)"CComCatalog::GetClassInfoInternal",
                3978,
                v84,
                (__int64)L"Look for %ls in private hive Catalog...",
                sz);
            v85 = v272;
            v86 = *((_QWORD *)v272 + 22);
            v87 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUserToken *, GUID *))(*(_QWORD *)v86 + 24LL);
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v81, v84);
            HIDWORD(v254) = 0;
            v253 = (struct _GUID *)&v261;
            v252 = (int)v271;
            ClassInfoW = v87(v86, v260, v282, rguid);
            ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
            if ( ClassInfoW )
            {
              if ( ClassInfoW != -2147221164 )
              {
                if ( ClassInfoW >= 0 )
                  goto LABEL_131;
                v72 = 4002;
                goto LABEL_130;
              }
            }
            else
            {
              v18 |= 4u;
              HIDWORD(v278) = v18;
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                v253 = (struct _GUID *)sz;
                ComTraceMessageT<unsigned short const *>(
                  (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                  (unsigned int)"CComCatalog::GetClassInfoInternal",
                  3988,
                  4,
                  (__int64)L"Found %ls in private hive Catalog");
              }
              LOWORD(v71) = 256;
              v269 = 256;
              v262[0] = 256;
              if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
              {
                v279 = 0x400000004LL;
LABEL_163:
                v88 = rguid;
LABEL_581:
                v234 = v271;
                goto LABEL_582;
              }
              v85 = v272;
            }
          }
          else
          {
            v85 = v272;
          }
          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v81, v82);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
          {
            if ( (_BYTE)v266 || !s_pCacheClassInfo )
            {
LABEL_240:
              wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v101, v102);
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
              {
                v107 = (int)v281;
                v108 = v276;
                if ( !v264 && !(_DWORD)v281 && !(_DWORD)v283 && !v276 )
                {
                  v109 = (__int64 *)*((_QWORD *)v85 + 17);
                  if ( v109 )
                  {
                    v280 = 16;
                    v110 = *v109;
                    LODWORD(v278) = v83 | 0x10;
                    v111 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct IUserToken *, GUID *))(v110 + 24);
                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v105, v106);
                    v254 = (struct IUnknown **)((char *)v85 + 16);
                    v253 = (struct _GUID *)&v261;
                    v252 = (int)v271;
                    ClassInfoW = v111(v109, v260, v282, rguid);
                    ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                    if ( ClassInfoW )
                    {
                      if ( ClassInfoW != -2147221164 )
                      {
                        if ( ClassInfoW >= 0 )
                          goto LABEL_131;
                        v72 = 4174;
                        goto LABEL_130;
                      }
                    }
                    else
                    {
                      LOWORD(v71) = 2;
                      v18 |= 0x10u;
                      v269 = 2;
                      HIDWORD(v278) = v18;
                      v262[0] = 2;
                      if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
                      {
                        v279 = 0x1000000010LL;
                        goto LABEL_180;
                      }
                    }
                    v107 = (int)v281;
                  }
                  v108 = v276;
                }
                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v105, v106);
                if ( v264 )
                  goto LABEL_299;
                v114 = v107 == 0;
                v115 = v272;
                if ( v114 && !(_DWORD)v283 && !v108 )
                {
                  v116 = (__int64 *)*((_QWORD *)v272 + 14);
                  v117 = v278;
                  if ( !v116 )
                    goto LABEL_301;
                  v280 = 32;
                  v117 = v278 | 0x20;
                  v118 = *v116;
                  LODWORD(v278) = v278 | 0x20;
                  v119 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct IUserToken *, GUID *))(v118 + 24);
                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v112, v113);
                  v254 = (struct IUnknown **)((char *)v272 + 16);
                  v253 = (struct _GUID *)&v261;
                  v252 = (int)v271;
                  ClassInfoW = v119(v116, v260, v282, rguid);
                  ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                  if ( ClassInfoW )
                  {
                    if ( ClassInfoW != -2147221164 )
                    {
                      if ( ClassInfoW >= 0 )
                        goto LABEL_131;
                      v72 = 4201;
                      goto LABEL_130;
                    }
                    goto LABEL_300;
                  }
                  LOWORD(v71) = 2;
                  v18 |= 0x20u;
                  HIDWORD(v278) = v18;
                  v269 = 2;
                  v262[0] = 2;
                  if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
                  {
                    v279 = 0x2000000020LL;
                    goto LABEL_180;
                  }
LABEL_299:
                  v117 = v278;
LABEL_300:
                  v115 = v272;
LABEL_301:
                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v112, v113);
                  v127 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
                  v129 = 0;
                  if ( v127 && v268 || !g_bInSCM || (v260 & 0x4000) != 0 )
                  {
LABEL_336:
                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v128, v129);
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                    {
                      if ( !v264 && !g_bInSCM )
                      {
                        if ( (_DWORD)v283 || (v156 = v276) == 0 )
                        {
                          v157 = v272;
                          v158 = 2048;
                          v280 = 2048;
                          LODWORD(v278) = v117 | 0x800;
                          v159 = (char *)v272 + 16;
                          if ( !v272 )
                            v159 = 0;
                          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v154, v155);
                          ClassInfoW = DeviceCatalogs::GetClassInfoW(
                                         (CComCatalog *)((char *)v157 + 224),
                                         v260 & 0xFFFFF301,
                                         v282,
                                         rguid,
                                         v271,
                                         (void **)&v261,
                                         v159);
                          ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                          if ( !ClassInfoW )
                          {
LABEL_344:
                            v160 = v18 | 0x800;
                            LODWORD(v279) = 2048;
                            v71 = 1024;
LABEL_345:
                            HIDWORD(v279) = v158;
                            HIDWORD(v278) = v160;
                            v269 = v71;
                            v262[0] = v71;
                            goto LABEL_180;
                          }
                          if ( ClassInfoW != -2147221164 )
                          {
                            if ( ClassInfoW >= 0 )
                              goto LABEL_131;
                            v72 = 4432;
                            goto LABEL_130;
                          }
                          goto LABEL_360;
                        }
LABEL_358:
                        v157 = v272;
LABEL_361:
                        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
                          && v265 )
                        {
                          goto LABEL_501;
                        }
                        v165 = 0;
                        v263 = 0;
                        if ( !g_bInSCM || (v260 & 0x10000000) != 0 )
                        {
                          v167 = 1;
                        }
                        else if ( (v260 & 0x20000000) != 0 )
                        {
                          NativeArchitecture = GetNativeArchitecture();
                          v163 = 332;
                          v167 = NativeArchitecture == 332;
                          v165 = NativeArchitecture != 332;
                        }
                        else if ( (v260 & 0x40000000) != 0 )
                        {
                          v168 = GetNativeArchitecture();
                          v167 = GetArchitecturePointerSizeInBytes(v168) == 8;
                        }
                        else if ( (v260 & 0x80000000) == 0 )
                        {
                          v167 = 1;
                          v263 = 1;
                          v165 = 1;
                        }
                        else
                        {
                          v169 = GetNativeArchitecture();
                          v163 = 452;
                          v167 = v169 == 452;
                          v263 = v169 != 452;
                        }
                        if ( (_DWORD)v283 || !v156 )
                        {
                          if ( *((_QWORD *)v157 + 13) && v167 )
                          {
                            LODWORD(v278) = v278 | 0x80;
                            v280 = 128;
                            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                              ComTraceMessageT<unsigned short const *>(
                                (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                (unsigned int)"CComCatalog::GetClassInfoInternal",
                                4555,
                                v164,
                                (__int64)L"Look for %ls in registry...",
                                sz);
                            v170 = *((_QWORD *)v157 + 13);
                            v171 = (char *)v272 + 16;
                            v172 = *(__int64 (__fastcall **)(__int64, __int64, struct IUserToken *, GUID *))(*(_QWORD *)v170 + 24LL);
                            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v286, v163, v164);
                            v173 = v260;
                            if ( (_DWORD)v281 )
                              v173 = v260 | 0x30000;
                            HIDWORD(v254) = HIDWORD(v171);
                            v253 = (struct _GUID *)&v286;
                            v252 = (int)v271;
                            ClassInfoW = v172(v170, v173, v282, rguid);
                            ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                            if ( ClassInfoW )
                            {
                              if ( ClassInfoW != -2147221164 )
                              {
                                if ( ClassInfoW >= 0 )
                                  goto LABEL_131;
                                v72 = 4584;
                                goto LABEL_130;
                              }
                              v157 = v272;
                            }
                            else
                            {
                              v18 |= 0x80u;
                              HIDWORD(v278) = v18;
                              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                              {
                                v253 = (struct _GUID *)sz;
                                ComTraceMessageT<unsigned short const *>(
                                  (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                  (unsigned int)"CComCatalog::GetClassInfoInternal",
                                  4566,
                                  v174,
                                  (__int64)L"Found %ls in registry");
                              }
                              v269 = 1;
                              v262[0] = 1;
                              if ( !ClassRegistrationMatchesRequestedClsctx(v286, v260, &v287) && !g_bInSCM )
                                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v286, v163, v164);
                              v157 = v272;
                              if ( v287 )
                                LODWORD(v279) = 128;
                            }
                          }
                          v175 = v283;
                          if ( (_DWORD)v283 || !v276 )
                          {
                            if ( *((_QWORD *)v157 + 15) )
                            {
                              v114 = !v165;
                              v176 = v278;
                              if ( !v114 )
                              {
                                v176 = v278 | 0x100;
                                v280 = 256;
                                LODWORD(v278) = v278 | 0x100;
                                if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                  ComTraceMessageT<unsigned short const *>(
                                    (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                    (unsigned int)"CComCatalog::GetClassInfoInternal",
                                    4595,
                                    v164,
                                    (__int64)L"Look for %ls in x86 WOW registry...",
                                    sz);
                                v177 = *((_QWORD *)v157 + 15);
                                v178 = (char *)v272 + 16;
                                v179 = *(__int64 (__fastcall **)(__int64, __int64, struct IUserToken *, GUID *))(*(_QWORD *)v177 + 24LL);
                                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v296, v163, v164);
                                v180 = v260;
                                if ( (_DWORD)v281 )
                                  v180 = v260 | 0x30000;
                                HIDWORD(v254) = HIDWORD(v178);
                                v253 = (struct _GUID *)&v296;
                                v252 = (int)v271;
                                ClassInfoW = v179(v177, v180, v282, rguid);
                                ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                                if ( ClassInfoW )
                                {
                                  if ( ClassInfoW != -2147221164 )
                                  {
                                    if ( ClassInfoW >= 0 )
                                      goto LABEL_131;
                                    v72 = 4617;
                                    goto LABEL_130;
                                  }
                                  v157 = v272;
                                  v175 = v283;
                                }
                                else
                                {
                                  v18 |= 0x100u;
                                  HIDWORD(v278) = v18;
                                  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                  {
                                    v253 = (struct _GUID *)sz;
                                    ComTraceMessageT<unsigned short const *>(
                                      (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                      (unsigned int)"CComCatalog::GetClassInfoInternal",
                                      4607,
                                      v181,
                                      (__int64)L"Found %ls in x86 WOW registry");
                                  }
                                  v265 = 0;
                                  v269 = 8;
                                  v262[0] = 8;
                                  ClassRegistrationMatchesRequestedClsctx(v296, v260, &v265);
                                  v157 = v272;
                                  v175 = v283;
                                  v297 = v265;
                                  if ( v265 )
                                    LODWORD(v279) = v279 | 0x100;
                                }
                              }
                            }
                            else
                            {
                              v176 = v278;
                            }
                            if ( (v175 || !v276) && *((_QWORD *)v157 + 16) && v263 )
                            {
                              v280 = 512;
                              LODWORD(v278) = v176 | 0x200;
                              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                ComTraceMessageT<unsigned short const *>(
                                  (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                  (unsigned int)"CComCatalog::GetClassInfoInternal",
                                  4628,
                                  4,
                                  (__int64)L"Look for %ls in ARM32 WOW registry...",
                                  sz);
                              v182 = *((_QWORD *)v157 + 16);
                              v183 = (char *)v272 + 16;
                              v184 = *(__int64 (__fastcall **)(__int64, __int64, struct IUserToken *, GUID *))(*(_QWORD *)v182 + 24LL);
                              wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v293, v163, v164);
                              v185 = v260;
                              if ( (_DWORD)v281 )
                                v185 = v260 | 0x30000;
                              HIDWORD(v254) = HIDWORD(v183);
                              v253 = (struct _GUID *)&v293;
                              v252 = (int)v271;
                              ClassInfoW = v184(v182, v185, v282, rguid);
                              ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                              if ( !ClassInfoW )
                              {
                                v18 |= 0x200u;
                                HIDWORD(v278) = v18;
                                if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                {
                                  v253 = (struct _GUID *)sz;
                                  ComTraceMessageT<unsigned short const *>(
                                    (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                    (unsigned int)"CComCatalog::GetClassInfoInternal",
                                    4640,
                                    4,
                                    (__int64)L"Found %ls in ARM32 WOW registry");
                                }
                                LOWORD(v71) = 8;
                                v262[0] = 8;
                                v269 = 8;
                                v263 = 0;
                                ClassRegistrationMatchesRequestedClsctx(v293, v260, &v263);
                                v294 = v263;
                                if ( v263 )
                                  LODWORD(v279) = v279 | 0x200;
LABEL_434:
                                v186 = v296;
                                if ( v286 || v296 || v293 != v286 )
                                {
                                  if ( !g_bInSCM || (v260 & 0x10000000) != 0 )
                                    goto LABEL_438;
                                  if ( (v260 & 0x20000000) != 0 )
                                  {
                                    if ( GetNativeArchitecture() != 332 )
                                    {
                                      HIDWORD(v279) = 256;
                                      v187 = &v296;
                                      goto LABEL_439;
                                    }
LABEL_438:
                                    v187 = &v286;
                                    HIDWORD(v279) = 128;
LABEL_439:
                                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(&v261, v187, v186);
                                    goto LABEL_180;
                                  }
                                  if ( (v260 & 0x40000000) != 0 )
                                    goto LABEL_438;
                                  if ( (v260 & 0x80000000) != 0 )
                                  {
                                    if ( GetNativeArchitecture() != 452 )
                                    {
                                      HIDWORD(v279) = 512;
                                      v187 = &v293;
                                      goto LABEL_439;
                                    }
                                    goto LABEL_438;
                                  }
                                  v188 = v260 | 0x1000000;
                                  v281 = 0;
                                  if ( (v260 & 0x7000100) != 0 )
                                    v188 = v260;
                                  if ( v286 )
                                  {
                                    v189 = &v286;
                                  }
                                  else
                                  {
                                    v189 = &v296;
                                    if ( !v296 )
                                      v189 = &v293;
                                  }
                                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(&v281, v189, v296);
                                  v284 = 0;
                                  if ( (**v281)(v281, &GUID_0318b242_d086_4de9_b10c_2824a6ca1019, &v284) >= 0 )
                                  {
                                    v291 = 0;
                                    ((void (__fastcall *)(struct IUnknown **, unsigned int *))(*v284)[3].lpVtbl)(
                                      v284,
                                      &v291);
                                    if ( v291 )
                                    {
                                      switch ( v291 )
                                      {
                                        case 1u:
                                          if ( (v188 & 0x1000100) == 0 )
                                          {
                                            if ( (v188 & 0x2000000) == 0 )
                                            {
                                              if ( (v188 & 0x4000000) == 0 )
                                              {
                                                MicrosoftTelemetryAssertTriggeredNoArgs(v191);
                                                goto LABEL_500;
                                              }
                                              if ( !v293 )
                                              {
LABEL_500:
                                                wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v284);
                                                wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v281);
                                                goto LABEL_501;
                                              }
                                              HIDWORD(v279) = 512;
                                              v194 = &v293;
LABEL_475:
                                              wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(
                                                &v261,
                                                v194,
                                                v190);
                                              wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v284);
                                              wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v281);
                                              goto LABEL_180;
                                            }
                                            goto LABEL_477;
                                          }
                                          break;
                                        case 2u:
                                          if ( GetNativeArchitecture() != 332 )
                                          {
LABEL_477:
                                            if ( !v296 )
                                              goto LABEL_500;
                                            HIDWORD(v279) = 256;
                                            v194 = &v296;
                                            goto LABEL_475;
                                          }
                                          break;
                                        case 3u:
                                          v193 = GetNativeArchitecture();
                                          if ( GetArchitecturePointerSizeInBytes(v193) != 8 )
                                            goto LABEL_500;
                                          break;
                                        case 4u:
                                          if ( GetNativeArchitecture() != 452 )
                                          {
                                            if ( v293 )
                                            {
                                              HIDWORD(v279) = 512;
                                              v192 = &v293;
                                              goto LABEL_466;
                                            }
                                            goto LABEL_500;
                                          }
                                          goto LABEL_464;
                                        case 5u:
                                          if ( GetNativeArchitecture() == 0xAA64 )
                                            goto LABEL_464;
                                          goto LABEL_500;
                                        case 0x80000000:
LABEL_464:
                                          if ( v286 )
                                          {
                                            HIDWORD(v279) = 128;
                                            v192 = &v286;
LABEL_466:
                                            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(
                                              &v261,
                                              v192,
                                              v190);
                                            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v284);
                                            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v281);
                                            goto LABEL_163;
                                          }
                                          goto LABEL_500;
                                        default:
                                          ProxyStubClassInfoFromPackageScopedCatalog = -2147221165;
                                          wil::details::in1diag3::Return_Hr(
                                            retaddr,
                                            (void *)0x1326,
                                            (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                            (const char *)0x80040153LL,
                                            v252);
                                          wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v284);
                                          v93 = (HSTRING **)&v281;
                                          goto LABEL_463;
                                      }
                                      if ( !v286 )
                                        goto LABEL_500;
                                      HIDWORD(v279) = 128;
                                      v194 = &v286;
                                      goto LABEL_475;
                                    }
                                  }
                                  v306 = 0;
                                  v305 = 0;
                                  if ( (v188 & 0x1000100) != 0 )
                                  {
                                    *(_QWORD *)&v305 = &v286;
                                    v195 = &v296;
                                  }
                                  else
                                  {
                                    if ( (v188 & 0x2000000) == 0 )
                                    {
                                      if ( (v188 & 0x4000000) == 0 )
                                        goto LABEL_493;
                                      *(_QWORD *)&v305 = &v293;
                                      *((_QWORD *)&v305 + 1) = &v286;
                                      v196 = &v296;
LABEL_492:
                                      v306 = v196;
LABEL_493:
                                      v197 = 0;
                                      while ( 1 )
                                      {
                                        v198 = *((_QWORD *)&v305 + v197);
                                        if ( *(_QWORD *)v198 )
                                        {
                                          if ( *(_BYTE *)(v198 + 8) )
                                            break;
                                        }
                                        v197 = (unsigned int)(v197 + 1);
                                        if ( (unsigned int)v197 >= 3 )
                                        {
                                          v199 = 0;
                                          while ( 1 )
                                          {
                                            v198 = *((_QWORD *)&v305 + v199);
                                            if ( *(_QWORD *)v198 )
                                              goto LABEL_579;
                                            v199 = (unsigned int)(v199 + 1);
                                            if ( (unsigned int)v199 >= 3 )
                                              goto LABEL_500;
                                          }
                                        }
                                      }
LABEL_579:
                                      HIDWORD(v279) = *(_DWORD *)(v198 + 12);
                                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(&v261, v198, v190);
                                      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v284);
                                      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v281);
                                      goto LABEL_580;
                                    }
                                    *(_QWORD *)&v305 = &v296;
                                    v195 = &v286;
                                  }
                                  *((_QWORD *)&v305 + 1) = v195;
                                  v196 = &v293;
                                  goto LABEL_492;
                                }
LABEL_501:
                                v200 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
                                v203 = v272;
                                if ( v200 )
                                {
                                  if ( !v264 )
                                  {
                                    v204 = (__int64 *)*((_QWORD *)v272 + 27);
                                    if ( v204 )
                                    {
                                      if ( (_DWORD)v283 || !v276 )
                                      {
                                        v158 = 1024;
                                        v280 = 1024;
                                        v205 = v278 | 0x400;
                                        v206 = *v204;
                                        LODWORD(v278) = v278 | 0x400;
                                        v207 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct IUserToken *, GUID *))(v206 + 24);
                                        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v201, v202);
                                        v254 = (struct IUnknown **)((char *)v272 + 16);
                                        v253 = (struct _GUID *)&v261;
                                        v252 = (int)v271;
                                        ClassInfoW = v207(v204, v260, v282, rguid);
                                        ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                                        if ( !ClassInfoW )
                                        {
LABEL_507:
                                          v160 = v18 | 0x400;
                                          v71 = 512;
                                          LODWORD(v279) = v279 | 0x400;
                                          goto LABEL_345;
                                        }
                                        if ( ClassInfoW != -2147221164 )
                                        {
                                          if ( ClassInfoW >= 0 )
                                            goto LABEL_131;
                                          v72 = 4998;
                                          goto LABEL_130;
                                        }
LABEL_519:
                                        v203 = v272;
                                        goto LABEL_520;
                                      }
                                    }
                                  }
                                }
                                else
                                {
                                  v208 = (__int64 *)*((_QWORD *)v272 + 27);
                                  if ( v208 && ((_DWORD)v283 || !v276) )
                                  {
                                    v158 = 1024;
                                    v280 = 1024;
                                    v205 = v278 | 0x400;
                                    v209 = *v208;
                                    LODWORD(v278) = v278 | 0x400;
                                    v210 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct IUserToken *, GUID *))(v209 + 24);
                                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v201, v202);
                                    v254 = (struct IUnknown **)((char *)v272 + 16);
                                    v253 = (struct _GUID *)&v261;
                                    v252 = (int)v271;
                                    v211 = v210(v208, v260, v282, rguid);
                                    ClassInfoW = v211;
                                    ProxyStubClassInfoFromPackageScopedCatalog = v211;
                                    if ( !v211 )
                                      goto LABEL_507;
                                    if ( v211 != -2147221164 )
                                    {
                                      if ( v211 >= 0 )
                                        goto LABEL_131;
                                      v72 = 5021;
                                      goto LABEL_130;
                                    }
                                    goto LABEL_519;
                                  }
                                }
                                v205 = v278;
LABEL_520:
                                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                                {
                                  if ( v267 || g_bInSCM || !v28 || (v260 & 0x17) == 1 )
                                  {
                                    LODWORD(v220) = (_DWORD)rguid;
                                  }
                                  else
                                  {
                                    v205 |= 2u;
                                    v280 = 2;
                                    LODWORD(v278) = v205;
                                    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                      ComTraceMessageT<unsigned short const *>(
                                        (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                        (unsigned int)"CComCatalog::GetClassInfoInternal",
                                        5046,
                                        v213,
                                        (__int64)L"Look for %ls in PackagedCom current package Catalog...");
                                    v272 = 0;
                                    v215 = wil::com_query_to_nothrow<IComCatalogPackageAware,wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> &>(
                                             &v275,
                                             &v272,
                                             v213,
                                             v214);
                                    ProxyStubClassInfoFromPackageScopedCatalog = v215;
                                    if ( v215 < 0 )
                                    {
                                      wil::details::in1diag3::Return_Hr(
                                        retaddr,
                                        (void *)0x13BF,
                                        (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                        (const char *)(unsigned int)v215,
                                        v252);
LABEL_530:
                                      v93 = (HSTRING **)&v272;
                                      goto LABEL_463;
                                    }
                                    v218 = v272;
                                    v219 = *(__int64 (__fastcall **)(CComCatalog *, _QWORD, _QWORD, struct IUserTokenInternal *))(*(_QWORD *)v272 + 24LL);
                                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v216, v217);
                                    v220 = rguid;
                                    HIDWORD(v257) = HIDWORD(v299);
                                    LODWORD(v253) = (_DWORD)v300;
                                    v252 = (int)rguid;
                                    v221 = v219(v218, a8 & 0xFFFFFFFE, 0, v273);
                                    ClassInfoW = v221;
                                    ProxyStubClassInfoFromPackageScopedCatalog = v221;
                                    if ( v221 )
                                    {
                                      if ( v221 != -2147221164 )
                                      {
                                        if ( v221 < 0 )
                                        {
                                          LODWORD(v257) = v260;
                                          wil::details::in1diag3::Return_HrMsg(
                                            retaddr,
                                            (void *)0x13D4,
                                            (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                            (const char *)(unsigned int)v221,
                                            (int)"CLSID:%ls Flags:%#x IID:%ls",
                                            (const char *)sz,
                                            v257,
                                            v314);
                                        }
                                        goto LABEL_530;
                                      }
                                    }
                                    else
                                    {
                                      v18 |= 2u;
                                      HIDWORD(v278) = v18;
                                      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                      {
                                        v253 = (struct _GUID *)sz;
                                        ComTraceMessageT<unsigned short const *>(
                                          (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                          (unsigned int)"CComCatalog::GetClassInfoInternal",
                                          5065,
                                          v222,
                                          (__int64)L"Found %ls in PackagedCom current package Catalog");
                                      }
                                      LOWORD(v71) = 256;
                                      v269 = 256;
                                      v262[0] = 256;
                                      if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
                                      {
                                        LODWORD(v279) = v279 | 2;
                                        HIDWORD(v279) = 2;
                                        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v272);
                                        v88 = v220;
                                        goto LABEL_581;
                                      }
                                      v205 = v278;
                                    }
                                    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v272);
                                  }
                                  if ( !v268 && !g_bInSCM )
                                  {
                                    v223 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v203 + 23);
                                    v280 = 64;
                                    v283 = 0;
                                    v224 = (**v223)(v223, &GUID_bcf8570c_b66f_4849_aa7a_94d710f655bf, &v283);
                                    ProxyStubClassInfoFromPackageScopedCatalog = v224;
                                    if ( v224 < 0 )
                                    {
                                      wil::details::in1diag3::Return_Hr(
                                        retaddr,
                                        (void *)0x13E2,
                                        (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                        (const char *)(unsigned int)v224,
                                        v252);
LABEL_547:
                                      v93 = (HSTRING **)&v283;
                                      goto LABEL_463;
                                    }
                                    v227 = v283;
                                    LODWORD(v278) = v205 | 0x40;
                                    v228 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct IUserTokenInternal *))(*(_QWORD *)v283 + 24LL);
                                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v225, v226);
                                    HIDWORD(v258) = HIDWORD(v299);
                                    LODWORD(v253) = (_DWORD)v300;
                                    v252 = (int)v220;
                                    v229 = v228(v227, (unsigned int)a8, 0, v273);
                                    ClassInfoW = v229;
                                    ProxyStubClassInfoFromPackageScopedCatalog = v229;
                                    if ( v229 )
                                    {
                                      if ( v229 != -2147221164 )
                                      {
                                        if ( v229 < 0 )
                                        {
                                          LODWORD(v258) = v260;
                                          wil::details::in1diag3::Return_HrMsg(
                                            retaddr,
                                            (void *)0x13F8,
                                            (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                            (const char *)(unsigned int)v229,
                                            (int)"CLSID:%ls Flags:%#x IID:%ls",
                                            (const char *)sz,
                                            v258,
                                            v314);
                                        }
                                        goto LABEL_547;
                                      }
                                    }
                                    else
                                    {
                                      LOWORD(v71) = 1;
                                      v269 = 1;
                                      HIDWORD(v278) = v18 | 0x40;
                                      v262[0] = 1;
                                      if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
                                      {
                                        LODWORD(v279) = v279 | 0x40;
                                        HIDWORD(v279) = 64;
                                        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v283);
                                        goto LABEL_580;
                                      }
                                    }
                                    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v283);
                                    v230 = v282;
                                    goto LABEL_570;
                                  }
LABEL_569:
                                  v230 = v282;
                                  goto LABEL_570;
                                }
                                if ( g_bInSCM || !*((_QWORD *)v203 + 23) )
                                  goto LABEL_569;
                                v280 = 64;
                                LODWORD(v278) = v205 | 0x40;
                                if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                  ComTraceMessageT<unsigned short const *>(
                                    (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                    (unsigned int)"CComCatalog::GetClassInfoInternal",
                                    5124,
                                    4,
                                    (__int64)L"Look for %ls in PackagedCom all packages Catalog...",
                                    sz);
                                v231 = *((_QWORD *)v203 + 23);
                                v232 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUserToken *, GUID *))(*(_QWORD *)v231 + 24LL);
                                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v212, v213);
                                v233 = (char *)v203 + 16;
                                v230 = v282;
                                HIDWORD(v254) = HIDWORD(v233);
                                v253 = (struct _GUID *)&v261;
                                v252 = (int)v271;
                                ClassInfoW = v232(v231, v260, v282, rguid);
                                ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                                if ( !ClassInfoW )
                                {
                                  HIDWORD(v278) = v18 | 0x40;
                                  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                  {
                                    v253 = (struct _GUID *)sz;
                                    ComTraceMessageT<unsigned short const *>(
                                      (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                      (unsigned int)"CComCatalog::GetClassInfoInternal",
                                      5131,
                                      4,
                                      (__int64)L"Found %ls in PackagedCom all packages Catalog");
                                  }
                                  LOWORD(v71) = 1;
                                  v269 = 1;
                                  v262[0] = 1;
                                  if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
                                  {
                                    LODWORD(v279) = v279 | 0x40;
                                    HIDWORD(v279) = 64;
                                    goto LABEL_580;
                                  }
                                  goto LABEL_570;
                                }
                                if ( ClassInfoW == -2147221164 )
                                {
LABEL_570:
                                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v212, v213);
                                  v234 = v271;
                                  v88 = rguid;
                                  LODWORD(v281) = -2147221164;
                                  ComTrace::LogClassNotFound<long,_GUID const &,_GUID const &,ComCatalogDiagnosticData &>(
                                    &v281,
                                    rguid,
                                    v271,
                                    v277);
                                  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
                                    ComTraceMessageT<long,unsigned short const *,unsigned long,unsigned short const *>(
                                      v236,
                                      v235,
                                      v237,
                                      v238,
                                      v252,
                                      (_DWORD)v253,
                                      (__int64)sz,
                                      v260,
                                      (__int64)v314);
                                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v235, v237);
                                  NoClassInfo = CComCatalog::CreateNoClassInfo(v230, v88, v234, (void **)&v261);
                                  ProxyStubClassInfoFromPackageScopedCatalog = NoClassInfo;
                                  if ( NoClassInfo >= 0 )
                                  {
                                    LOWORD(v71) = 4;
                                    v262[0] = 4;
                                    v269 = 4;
                                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                                    {
                                      v239 = v266;
                                      if ( !(_BYTE)v266 )
                                        v239 = HasAnyComDependenciesOnPackages();
LABEL_583:
                                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                                      {
                                        if ( !v239
                                          && s_pCacheClassInfo
                                          && ((unsigned __int16)v71 & (unsigned __int16)gdwCacheableFlags) != 0 )
                                        {
                                          v285 = 0;
                                          wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v285, v240, v241);
                                          if ( (unsigned int)CCache::AddElement(
                                                               (CCache *)s_pCacheClassInfo,
                                                               v88->Data1,
                                                               4u,
                                                               v310,
                                                               v301,
                                                               v262,
                                                               v261,
                                                               (struct IUnknown **)&v285) == 1 )
                                          {
                                            if ( !v285 )
                                            {
                                              LODWORD(v281) = -2147221164;
                                              ComTrace::LogClassNotFound<long,_GUID const &,_GUID const &,ComCatalogDiagnosticData &>(
                                                &v281,
                                                v88,
                                                v271,
                                                v277);
                                              ProxyStubClassInfoFromPackageScopedCatalog = -2147221164;
LABEL_592:
                                              v245 = 5202;
LABEL_593:
                                              LODWORD(v259) = v260;
                                              wil::details::in1diag3::Return_HrMsg(
                                                retaddr,
                                                (void *)v245,
                                                (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                                (const char *)ProxyStubClassInfoFromPackageScopedCatalog,
                                                (int)"CLSID:%ls Flags:%#x IID:%ls",
                                                (const char *)sz,
                                                v259,
                                                v314);
                                              goto LABEL_594;
                                            }
                                            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(
                                              &v261,
                                              v242,
                                              v243);
                                            v244 = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(
                                                     &v285,
                                                     v234,
                                                     &v261);
                                            ProxyStubClassInfoFromPackageScopedCatalog = v244;
                                            if ( v244 )
                                            {
                                              if ( v244 >= 0 )
                                              {
LABEL_594:
                                                v93 = &v285;
                                                goto LABEL_463;
                                              }
                                              goto LABEL_592;
                                            }
                                          }
                                          goto LABEL_595;
                                        }
LABEL_607:
                                        v246 = v269;
                                        goto LABEL_608;
                                      }
                                      if ( !s_pCacheClassInfo
                                        || ((unsigned __int16)v71 & (unsigned __int16)gdwCacheableFlags) == 0 )
                                      {
                                        goto LABEL_607;
                                      }
                                      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                                        ComTraceMessageT<unsigned short const *>(
                                          (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                          (unsigned int)"CComCatalog::GetClassInfoInternal",
                                          5211,
                                          4,
                                          (__int64)L"Adding %ls to cache...",
                                          sz);
                                      v285 = 0;
                                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v285, v240, v241);
                                      if ( (unsigned int)CCache::AddElement(
                                                           (CCache *)s_pCacheClassInfo,
                                                           v88->Data1,
                                                           4u,
                                                           v310,
                                                           v301,
                                                           v262,
                                                           v261,
                                                           (struct IUnknown **)&v285) == 1 )
                                      {
                                        if ( !v285 )
                                        {
                                          LODWORD(v281) = -2147221164;
                                          ComTrace::LogClassNotFound<long,_GUID const &,_GUID const &,ComCatalogDiagnosticData &>(
                                            &v281,
                                            v88,
                                            v271,
                                            v277);
                                          ProxyStubClassInfoFromPackageScopedCatalog = -2147221164;
LABEL_606:
                                          v245 = 5238;
                                          goto LABEL_593;
                                        }
                                        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v247, v248);
                                        v249 = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(
                                                 &v285,
                                                 v234,
                                                 &v261);
                                        ProxyStubClassInfoFromPackageScopedCatalog = v249;
                                        if ( v249 )
                                        {
                                          if ( v249 >= 0 )
                                            goto LABEL_594;
                                          goto LABEL_606;
                                        }
                                      }
LABEL_595:
                                      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v285);
                                      v246 = v262[0];
LABEL_608:
                                      v250 = v261;
                                      v261 = 0;
                                      *v304 = v250;
                                      if ( (v246 & 4) != 0 )
                                      {
                                        LODWORD(v281) = 1;
                                        ComTrace::LogClassNotFound<long,_GUID const &,_GUID const &,ComCatalogDiagnosticData &>(
                                          &v281,
                                          v88,
                                          v234,
                                          v277);
                                        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v261);
                                        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v273);
                                        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v275);
                                        ProxyStubClassInfoFromPackageScopedCatalog = 1;
                                        goto LABEL_612;
                                      }
                                      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v261);
                                      goto LABEL_611;
                                    }
LABEL_582:
                                    v239 = v266;
                                    goto LABEL_583;
                                  }
                                  v104 = 5154;
                                  goto LABEL_225;
                                }
                                if ( ClassInfoW >= 0 )
                                  goto LABEL_131;
                                v72 = 5142;
LABEL_130:
                                LODWORD(v254) = v260;
                                wil::details::in1diag3::Return_HrMsg(
                                  retaddr,
                                  (void *)v72,
                                  (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                                  (const char *)ProxyStubClassInfoFromPackageScopedCatalog,
                                  (int)"CLSID:%ls Flags:%#x IID:%ls",
                                  (const char *)sz,
                                  v254,
                                  v314);
                                goto LABEL_131;
                              }
                              if ( ClassInfoW != -2147221164 )
                              {
                                if ( ClassInfoW >= 0 )
                                  goto LABEL_131;
                                v72 = 4650;
                                goto LABEL_130;
                              }
                            }
                          }
                        }
                        LOWORD(v71) = v269;
                        goto LABEL_434;
                      }
                    }
                    else if ( !g_bInSCM )
                    {
                      if ( (_DWORD)v283 || (v156 = v276) == 0 )
                      {
                        v157 = v272;
                        v158 = 2048;
                        v280 = 2048;
                        LODWORD(v278) = v117 | 0x800;
                        v161 = (char *)v272 + 16;
                        if ( !v272 )
                          v161 = 0;
                        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v154, v155);
                        v162 = DeviceCatalogs::GetClassInfoW(
                                 (CComCatalog *)((char *)v157 + 224),
                                 v260 & 0xFFFFF301,
                                 v282,
                                 rguid,
                                 v271,
                                 (void **)&v261,
                                 v161);
                        ClassInfoW = v162;
                        ProxyStubClassInfoFromPackageScopedCatalog = v162;
                        if ( !v162 )
                          goto LABEL_344;
                        if ( v162 != -2147221164 )
                        {
                          if ( v162 >= 0 )
                            goto LABEL_131;
                          v72 = 4455;
                          goto LABEL_130;
                        }
                        goto LABEL_360;
                      }
                      goto LABEL_358;
                    }
                    v157 = v272;
LABEL_360:
                    v156 = v276;
                    goto LABEL_361;
                  }
                  v117 |= 0x40u;
                  v280 = 64;
                  LODWORD(v278) = v117;
                  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                  {
                    ComTraceMessageT<unsigned short const *>(
                      (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                      (unsigned int)"CComCatalog::GetClassInfoInternal",
                      4303,
                      v130,
                      v131);
                    v129 = 0;
                  }
                  v292 = v129;
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                  {
                    v134 = v292;
                    v292 = 0;
                    if ( v134 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 16LL))(v134);
                    v135 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v115 + 23))(
                             *((_QWORD *)v115 + 23),
                             &GUID_bcf8570c_b66f_4849_aa7a_94d710f655bf,
                             &v292);
                    ProxyStubClassInfoFromPackageScopedCatalog = v135;
                    if ( v135 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x10D6,
                        (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                        (const char *)(unsigned int)v135,
                        v252);
LABEL_313:
                      v93 = (HSTRING **)&v292;
                      goto LABEL_463;
                    }
                    v138 = v292;
                    v139 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct IUserTokenInternal *))(*(_QWORD *)v292 + 24LL);
                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v136, v137);
                    v140 = rguid;
                    HIDWORD(v256) = HIDWORD(v299);
                    LODWORD(v253) = (_DWORD)v300;
                    v252 = (int)rguid;
                    v141 = v139(v138, (unsigned int)a8, 0, v273);
                  }
                  else
                  {
                    v142 = *((_QWORD *)v115 + 23);
                    v143 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUserToken *, GUID *))(*(_QWORD *)v142
                                                                                                  + 24LL);
                    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v132, v133);
                    v140 = rguid;
                    HIDWORD(v256) = 0;
                    v253 = (struct _GUID *)&v261;
                    v252 = (int)v271;
                    v141 = v143(v142, v260, v282, rguid);
                  }
                  ClassInfoW = v141;
                  ProxyStubClassInfoFromPackageScopedCatalog = v141;
                  if ( v141 == -2147221164 && (_BYTE)v291 )
                  {
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                    {
                      v146 = v292;
                      v147 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, struct IUserTokenInternal *))(*(_QWORD *)v292 + 24LL);
                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v144, v145);
                      HIDWORD(v256) = HIDWORD(v299);
                      LODWORD(v253) = (_DWORD)v300;
                      v252 = (int)v140;
                      v148 = v147(v146, (unsigned int)a8, 512, v273);
                    }
                    else
                    {
                      v149 = *((_QWORD *)v272 + 23);
                      v150 = *(__int64 (__fastcall **)(__int64, __int64, struct IUserToken *, GUID *))(*(_QWORD *)v149 + 24LL);
                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v144, v145);
                      v151 = v260;
                      LODWORD(v151) = v260 | 0x200;
                      HIDWORD(v256) = 0;
                      v253 = (struct _GUID *)&v261;
                      v252 = (int)v271;
                      v148 = v150(v149, v151, v282, v140);
                    }
                    ClassInfoW = v148;
                    ProxyStubClassInfoFromPackageScopedCatalog = v148;
                    if ( v148 )
                      goto LABEL_331;
                    v284 = &v261;
                    if ( (int)lambda_c56a88c6bd0f565e516d65786a230941_::operator()(&v284) < 0 )
                    {
                      ClassInfoW = -2147221164;
                      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v152, v153);
                    }
                    ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                  }
                  if ( !ProxyStubClassInfoFromPackageScopedCatalog )
                  {
                    v18 |= 0x40u;
                    HIDWORD(v278) = v18;
                    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                    {
                      v253 = (struct _GUID *)sz;
                      ComTraceMessageT<unsigned short const *>(
                        (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                        (unsigned int)"CComCatalog::GetClassInfoInternal",
                        4385,
                        4,
                        (__int64)L"Found %ls in PackagedCom all packages Catalog");
                    }
                    LOWORD(v71) = 1;
                    v269 = 1;
                    v262[0] = 1;
                    if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
                    {
                      v279 = 0x4000000040LL;
                      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v292);
                      goto LABEL_163;
                    }
                    v117 = v278;
LABEL_335:
                    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v292);
                    goto LABEL_336;
                  }
LABEL_331:
                  if ( ProxyStubClassInfoFromPackageScopedCatalog != -2147221164 )
                  {
                    if ( (ProxyStubClassInfoFromPackageScopedCatalog & 0x80000000) != 0 )
                    {
                      LODWORD(v256) = v260;
                      wil::details::in1diag3::Return_HrMsg(
                        retaddr,
                        (void *)0x112D,
                        (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                        (const char *)ProxyStubClassInfoFromPackageScopedCatalog,
                        (int)"CLSID:%ls Flags:%#x IID:%ls",
                        (const char *)sz,
                        v256,
                        v314);
                    }
                    goto LABEL_313;
                  }
                  goto LABEL_335;
                }
              }
              else
              {
                v120 = v276;
                v121 = v283;
                if ( !(_DWORD)v281 && !(_DWORD)v283 && !v276 && *((_QWORD *)v85 + 17) )
                {
                  v280 = 16;
                  LODWORD(v278) = v83 | 0x10;
                  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(v283 + 4)) )
                    ComTraceMessageT<unsigned short const *>(
                      (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                      (unsigned int)"CComCatalog::GetClassInfoInternal",
                      4213,
                      v106,
                      (__int64)L"Look for %ls in REGDB...",
                      sz);
                  v122 = *((_QWORD *)v85 + 17);
                  v123 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUserToken *, GUID *))(*(_QWORD *)v122 + 24LL);
                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v105, v106);
                  v254 = (struct IUnknown **)((char *)v85 + 16);
                  v253 = (struct _GUID *)&v261;
                  v252 = (int)v271;
                  ClassInfoW = v123(v122, v260, v282, rguid);
                  ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                  if ( ClassInfoW )
                  {
                    if ( ClassInfoW != -2147221164 )
                    {
                      if ( ClassInfoW >= 0 )
                        goto LABEL_131;
                      v72 = 4231;
                      goto LABEL_130;
                    }
                  }
                  else
                  {
                    v18 |= 0x10u;
                    HIDWORD(v278) = v18;
                    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                    {
                      v253 = (struct _GUID *)sz;
                      ComTraceMessageT<unsigned short const *>(
                        (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                        (unsigned int)"CComCatalog::GetClassInfoInternal",
                        4220,
                        4,
                        (__int64)L"Found %ls in REGDB");
                    }
                    LOWORD(v71) = 2;
                    v269 = 2;
                    v262[0] = 2;
                    if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
                    {
                      v279 = 0x1000000010LL;
                      goto LABEL_163;
                    }
                  }
                  v121 = v283;
                  v120 = v276;
                }
                wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v105, v106);
                v113 = 0;
                if ( (_DWORD)v281 || v121 )
                  goto LABEL_299;
                v114 = v120 == 0;
                v115 = v272;
                if ( v114 )
                {
                  v117 = v278;
                  if ( !*((_QWORD *)v272 + 14) )
                    goto LABEL_301;
                  v117 = v278 | 0x20;
                  v280 = 32;
                  LODWORD(v278) = v278 | 0x20;
                  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                    ComTraceMessageT<unsigned short const *>(
                      (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                      (unsigned int)"CComCatalog::GetClassInfoInternal",
                      4243,
                      v124,
                      (__int64)L"Look for %ls in COM Base CLB...",
                      sz);
                  v125 = *((_QWORD *)v115 + 14);
                  v126 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUserToken *, GUID *))(*(_QWORD *)v125 + 24LL);
                  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v112, v113);
                  v254 = (struct IUnknown **)((char *)v272 + 16);
                  v253 = (struct _GUID *)&v261;
                  v252 = (int)v271;
                  ClassInfoW = v126(v125, v260, v282, rguid);
                  ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
                  if ( ClassInfoW )
                  {
                    if ( ClassInfoW != -2147221164 )
                    {
                      if ( ClassInfoW >= 0 )
                        goto LABEL_131;
                      v72 = 4260;
                      goto LABEL_130;
                    }
                    goto LABEL_300;
                  }
                  v18 |= 0x20u;
                  HIDWORD(v278) = v18;
                  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
                  {
                    v253 = (struct _GUID *)sz;
                    ComTraceMessageT<unsigned short const *>(
                      (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                      (unsigned int)"CComCatalog::GetClassInfoInternal",
                      4249,
                      4,
                      (__int64)L"Found %ls in COM Base CLB");
                  }
                  LOWORD(v71) = 2;
                  v269 = 2;
                  v262[0] = 2;
                  if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
                  {
                    v279 = 0x2000000020LL;
                    goto LABEL_163;
                  }
                  goto LABEL_299;
                }
              }
              v117 = v278;
              goto LABEL_301;
            }
            v83 |= 8u;
            LODWORD(v278) = v83;
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v101, v102);
            if ( !(unsigned int)CCache::GetElement(
                                  (CCache *)s_pCacheClassInfo,
                                  rguid->Data1,
                                  4u,
                                  v310,
                                  v301,
                                  v262,
                                  &v261) )
            {
              v18 |= 8u;
              HIDWORD(v278) = v18;
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                v253 = (struct _GUID *)sz;
                ComTraceMessageT<unsigned short const *>(
                  (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                  (unsigned int)"CComCatalog::GetClassInfoInternal",
                  4028,
                  4,
                  (__int64)L"Found %ls in cache");
              }
              if ( v261
                && (!IsCComNoClassInfo(v261) || !HasAnyComDependenciesOnPackages())
                && CComCatalog::CheckForRefresh(v282, v261, (struct CCache *)s_pCacheClassInfo) >= 0 )
              {
                NoClassInfo = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(&v261, v271, v304);
                ProxyStubClassInfoFromPackageScopedCatalog = NoClassInfo;
                if ( !NoClassInfo )
                  goto LABEL_220;
                if ( NoClassInfo < 0 )
                {
                  v104 = 4086;
LABEL_225:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v104,
                    (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                    (const char *)(unsigned int)NoClassInfo,
                    v252);
                  goto LABEL_131;
                }
                goto LABEL_131;
              }
            }
          }
          else
          {
            if ( !s_pCacheClassInfo )
              goto LABEL_240;
            v83 |= 8u;
            LODWORD(v278) = v83;
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              ComTraceMessageT<unsigned short const *>(
                (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                (unsigned int)"CComCatalog::GetClassInfoInternal",
                4109,
                4,
                (__int64)L"Look for %ls in cache...",
                sz);
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v101, v102);
            if ( !(unsigned int)CCache::GetElement(
                                  (CCache *)s_pCacheClassInfo,
                                  rguid->Data1,
                                  4u,
                                  v310,
                                  v301,
                                  v262,
                                  &v261) )
            {
              v18 |= 8u;
              HIDWORD(v278) = v18;
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                v253 = (struct _GUID *)sz;
                ComTraceMessageT<unsigned short const *>(
                  (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
                  (unsigned int)"CComCatalog::GetClassInfoInternal",
                  4124,
                  4,
                  (__int64)L"Found %ls in cache");
              }
              v101 = v261;
              if ( v261 )
              {
                if ( CComCatalog::CheckForRefresh(v282, v261, (struct CCache *)s_pCacheClassInfo) >= 0 )
                {
                  NoClassInfo = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(&v261, v271, v304);
                  ProxyStubClassInfoFromPackageScopedCatalog = NoClassInfo;
                  if ( !NoClassInfo )
                  {
LABEL_220:
                    if ( (v262[0] & 4) != 0 )
                      ProxyStubClassInfoFromPackageScopedCatalog = 1;
                    goto LABEL_131;
                  }
                  if ( NoClassInfo < 0 )
                  {
                    v104 = 4137;
                    goto LABEL_225;
                  }
LABEL_131:
                  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v261);
                  goto LABEL_42;
                }
              }
            }
          }
          v269 = v262[0];
          goto LABEL_240;
        }
        v280 = 1;
        v17 = 1;
        LODWORD(v278) = 1;
        if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
          ComTraceMessageT<unsigned short const *>(
            (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
            (unsigned int)"CComCatalog::GetClassInfoInternal",
            3762,
            v65,
            (__int64)L"Look for %ls in COM SxS Catalog...",
            sz);
        v66 = *((_QWORD *)v64 + 18);
        v67 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUserToken *, GUID *))(*(_QWORD *)v66 + 24LL);
        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v62, v63);
        v254 = (struct IUnknown **)((char *)v272 + 16);
        v253 = (struct _GUID *)&v261;
        v252 = (int)v271;
        ClassInfoW = v67(v66, v260, v282, rguid);
        ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
        if ( ClassInfoW )
        {
          if ( ClassInfoW != -2147221164 )
          {
            if ( ClassInfoW >= 0 )
              goto LABEL_131;
            v72 = 3781;
            goto LABEL_130;
          }
          goto LABEL_146;
        }
        v18 = 1;
        HIDWORD(v278) = 1;
        if ( !gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(4) )
          goto LABEL_125;
        v69 = v68;
        v70 = 3768;
LABEL_124:
        v253 = (struct _GUID *)sz;
        ComTraceMessageT<unsigned short const *>(
          (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
          (unsigned int)"CComCatalog::GetClassInfoInternal",
          v70,
          v69,
          (__int64)L"Found %ls in COM SxS Catalog");
LABEL_125:
        LOWORD(v71) = 16;
        v262[0] = 16;
        v269 = 16;
        if ( ClassRegistrationMatchesRequestedClsctx(v261, v260, 0) )
        {
          v279 = 0x100000001LL;
LABEL_580:
          v88 = rguid;
          goto LABEL_581;
        }
        v17 = v278;
      }
    }
    else if ( !(_DWORD)v283 || v276 )
    {
      v64 = v272;
      if ( !*((_QWORD *)v272 + 18) )
        goto LABEL_147;
      v280 = 1;
      v17 = 1;
      LODWORD(v278) = 1;
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
        ComTraceMessageT<unsigned short const *>(
          (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
          (unsigned int)"CComCatalog::GetClassInfoInternal",
          3795,
          v73,
          (__int64)L"Look for %ls in COM SxS Catalog...",
          sz);
      v74 = *((_QWORD *)v64 + 18);
      v75 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IUserToken *, GUID *))(*(_QWORD *)v74 + 24LL);
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v261, v62, v63);
      v254 = (struct IUnknown **)((char *)v272 + 16);
      v253 = (struct _GUID *)&v261;
      v252 = (int)v271;
      ClassInfoW = v75(v74, v260, v282, rguid);
      ProxyStubClassInfoFromPackageScopedCatalog = ClassInfoW;
      if ( ClassInfoW )
      {
        if ( ClassInfoW != -2147221164 )
        {
          if ( ClassInfoW >= 0 )
            goto LABEL_131;
          v72 = 3814;
          goto LABEL_130;
        }
        goto LABEL_146;
      }
      v18 = 1;
      HIDWORD(v278) = 1;
      if ( !gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(4) )
        goto LABEL_125;
      v69 = v76;
      v70 = 3801;
      goto LABEL_124;
    }
LABEL_146:
    v64 = v272;
    goto LABEL_147;
  }
  ProxyStubClassInfoFromPackageScopedCatalog = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD17,
    (unsigned int)"onecore\\com\\combase\\catalog\\catalog.cxx",
    (const char *)0x80070057LL,
    v252);
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v293);
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v296);
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v286);
  v312 = 0;
LABEL_613:
  lambda_009d5060e5934af28c563eb57404125c_::operator()(v311);
  return ProxyStubClassInfoFromPackageScopedCatalog;
}

```

## disassembly

```asm
0x1800af154  push    rbp
0x1800af156  push    rbx
0x1800af157  push    rsi
0x1800af158  push    rdi
0x1800af159  push    r12
0x1800af15b  push    r13
0x1800af15d  push    r14
0x1800af15f  push    r15
0x1800af161  lea     rbp, [rsp-1C8h]
0x1800af169  sub     rsp, 2C8h
0x1800af170  mov     rax, cs:__security_cookie
0x1800af177  xor     rax, rsp
0x1800af17a  mov     [rbp+200h+var_50], rax
0x1800af181  mov     rax, [rbp+200h+arg_28]
0x1800af188  xor     esi, esi
0x1800af18a  mov     rbx, [rbp+200h+arg_20]
0x1800af191  mov     r15, r9
0x1800af194  mov     rdi, [rbp+200h+arg_50]
0x1800af19b  mov     r14, rcx
0x1800af19e  mov     [rbp+200h+var_170], rax
0x1800af1a5  mov     r13d, esi
0x1800af1a8  mov     rax, [rbp+200h+arg_48]
0x1800af1af  mov     r12d, esi
0x1800af1b2  mov     [rbp+200h+var_198], rax
0x1800af1b6  mov     rax, [rbp+200h+arg_60]
0x1800af1bd  mov     [rbp+200h+var_1F0], rax
0x1800af1c1  mov     rax, [rbp+200h+arg_70]
0x1800af1c8  mov     [rbp+200h+var_178], rax
0x1800af1cf  lea     rax, [rbp+200h+var_248]
0x1800af1d3  mov     [rbp+200h+var_118], rax
0x1800af1da  lea     rax, [rbp+200h+var_218]
0x1800af1de  mov     [rbp+200h+var_110], rax
0x1800af1e5  lea     rax, [rsp+300h+var_290]
0x1800af1ea  mov     [rbp+200h+var_100], rax
0x1800af1f1  mov     [rbp+200h+rguid], r9
0x1800af1f5  mov     [rbp+200h+var_208], r8
0x1800af1f9  mov     [rbp+200h+var_258], rcx
0x1800af1fd  mov     [rsp+300h+var_290], edx
0x1800af201  mov     [rbp+200h+var_260], rbx
0x1800af205  mov     [rbp+200h+var_1A0], rdi
0x1800af209  mov     [rbp+200h+var_248], esi
0x1800af20c  mov     [rbp+200h+var_218], esi
0x1800af20f  mov     [rbp+200h+var_108], r9
0x1800af216  mov     [rbp+200h+var_F8], 1
0x1800af21d  mov     [rbp+200h+var_270], esi
0x1800af220  mov     [rbp+200h+var_280], si
0x1800af224  mov     [rbp+200h+var_140], rsi
0x1800af22b  mov     [rbp+200h+var_1D8], si
0x1800af22f  mov     [rbp+200h+var_148], rsi
0x1800af236  mov     [rbp+200h+var_1D4], si
0x1800af23a  mov     [rbp+200h+var_1E8], rsi
0x1800af23e  mov     [rbp+200h+var_1E0], sil
0x1800af242  mov     [rbp+200h+var_1DC], 80h
0x1800af249  mov     [rbp+200h+var_1B0], rsi
0x1800af24d  mov     [rbp+200h+var_1A8], sil
0x1800af251  mov     [rbp+200h+var_1A4], 100h
0x1800af258  mov     [rbp+200h+var_1C0], rsi
0x1800af25c  mov     [rbp+200h+var_1B8], sil
0x1800af260  mov     [rbp+200h+var_1B4], 200h
0x1800af267  mov     [rbp+200h+var_228], rsi
0x1800af26b  mov     [rbp+200h+var_220], rsi
0x1800af26f  mov     [rbp+200h+var_230], edx
0x1800af272  test    edx, 0CE8h
0x1800af278  jz      short loc_1800AF2C1
0x1800af27a  mov     rcx, [rbp+208h]; this
0x1800af281  lea     r8, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\catalog"...
0x1800af288  mov     edi, 80070057h
0x1800af28d  mov     edx, 0D17h; void *
0x1800af292  mov     r9d, edi; char *
0x1800af295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af29a  lea     rcx, [rbp+200h+var_1C0]
0x1800af29e  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800af2a3  lea     rcx, [rbp+200h+var_1B0]
0x1800af2a7  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800af2ac  lea     rcx, [rbp+200h+var_1E8]
0x1800af2b0  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800af2b5  mov     [rbp+200h+var_F8], sil
0x1800af2bc  jmp     loc_1800B23B3
0x1800af2c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800af2c8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800af2cd  mov     esi, [rbp+200h+arg_40]
0x1800af2d3  mov     edx, [rbp+200h+arg_38]
0x1800af2d9  mov     ecx, [rsp+300h+var_290]
0x1800af2dd  test    al, al
0x1800af2df  jz      loc_1800AF39F
0x1800af2e5  cmp     [rbp+200h+arg_58], r12d
0x1800af2ec  jbe     short loc_1800AF300
0x1800af2ee  cmp     [rbp+200h+var_1F0], r12
0x1800af2f2  jnz     short loc_1800AF300
0x1800af2f4  mov     edi, 80070057h
0x1800af2f9  mov     edx, 0D1Bh
0x1800af2fe  jmp     short loc_1800AF317
0x1800af300  test    edx, 0FFFFFFE8h
0x1800af306  jz      short loc_1800AF332
0x1800af308  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800af30d  mov     edx, 0D1Eh; void *
0x1800af312  mov     edi, 8000FFFFh
0x1800af317  mov     r9d, edi; char *
0x1800af31a  mov     rcx, [rbp+208h]; this
0x1800af321  lea     r8, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\catalog"...
0x1800af328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af32d  jmp     loc_1800B2391
0x1800af332  test    esi, 0CFFh
0x1800af338  jz      short loc_1800AF346
0x1800af33a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800af33f  mov     edx, 0D1Fh
0x1800af344  jmp     short loc_1800AF312
0x1800af346  mov     eax, ecx
0x1800af348  and     eax, 17h
0x1800af34b  jnz     short loc_1800AF35E
0x1800af34d  cmp     edx, 17h
0x1800af350  jz      short loc_1800AF36E
0x1800af352  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800af357  mov     edx, 0D2Dh
0x1800af35c  jmp     short loc_1800AF312
0x1800af35e  cmp     edx, eax
0x1800af360  jz      short loc_1800AF36E
0x1800af362  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800af367  mov     edx, 0D31h
0x1800af36c  jmp     short loc_1800AF312
0x1800af36e  mov     eax, ecx
0x1800af370  and     eax, 0FFFFF300h
0x1800af375  cmp     esi, eax
0x1800af377  jz      short loc_1800AF385
0x1800af379  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800af37e  mov     edx, 0D35h
0x1800af383  jmp     short loc_1800AF312
0x1800af385  cmp     [rbp+200h+var_198], r12
0x1800af389  jz      short loc_1800AF39F
0x1800af38b  test    rdi, rdi
0x1800af38e  jz      short loc_1800AF39F
0x1800af390  mov     edi, 80070057h
0x1800af395  mov     edx, 0D38h
0x1800af39a  jmp     loc_1800AF317
0x1800af39f  mov     eax, ecx
0x1800af3a1  mov     rdx, r15; rguid
0x1800af3a4  and     ecx, 200000h
0x1800af3aa  and     eax, 8000000h
0x1800af3af  mov     [rbp+200h+var_238], ecx
0x1800af3b2  lea     rcx, [rbp+200h+sz]; lpsz
0x1800af3b9  mov     dword ptr [rbp+200h+var_200], eax
0x1800af3bc  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x1800af3c1  mov     rdx, rbx; rguid
0x1800af3c4  lea     rcx, [rbp+200h+var_A0]; lpsz
0x1800af3cb  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x1800af3d0  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800af3d7  jz      short loc_1800AF40C
0x1800af3d9  mov     ecx, 4
0x1800af3de  call    IsWppLevelEnabled
0x1800af3e3  test    al, al
0x1800af3e5  jz      short loc_1800AF40C
0x1800af3e7  lea     rax, [rbp+200h+var_A0]
0x1800af3ee  mov     [rsp+300h+var_2C8], rax
0x1800af3f3  mov     eax, [rsp+300h+var_290]
0x1800af3f7  mov     dword ptr [rsp+300h+var_2D0], eax
0x1800af3fb  lea     rax, [rbp+200h+sz]
0x1800af402  mov     [rsp+300h+var_2D8], rax
0x1800af407  call    ??$ComTraceMessageT@PEBGKPEBG@@YAXPEBD0HW4TraceLevel@@PEBG2K2@Z; ComTraceMessageT<ushort const *,ulong,ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,ushort const *)
0x1800af40c  mov     rax, [rbp+200h+var_170]
0x1800af413  mov     [rax], r12
0x1800af416  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800af41d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800af422  test    al, al
0x1800af424  jz      short loc_1800AF436
0x1800af426  mov     al, cs:?ms_fInitialized@CComCatalog@@0U?$atomic@_N@std@@A; std::atomic<bool> CComCatalog::ms_fInitialized
0x1800af42c  nop
0x1800af42d  test    al, al
0x1800af42f  jnz     short loc_1800AF436
0x1800af431  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800af436  mov     rcx, r14; this
0x1800af439  call    ?InitializeCatalogIfNecessary@CComCatalog@@QEAAJXZ; CComCatalog::InitializeCatalogIfNecessary(void)
0x1800af43e  mov     edi, eax
0x1800af440  test    eax, eax
0x1800af442  jns     short loc_1800AF451
0x1800af444  mov     r9d, eax
0x1800af447  mov     edx, 0D53h
0x1800af44c  jmp     loc_1800AF31A
0x1800af451  xor     ebx, ebx
0x1800af453  mov     [rbp+200h+var_240], rbx
0x1800af457  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800af45e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800af463  test    al, al
0x1800af465  jz      short loc_1800AF4C5
0x1800af467  xor     edx, edx; bool
0x1800af469  mov     rcx, r14; this
0x1800af46c  call    ?InitializePackagedComCurrentPackageProviderIfNecessary@CComCatalog@@AEAAJ_N@Z; CComCatalog::InitializePackagedComCurrentPackageProviderIfNecessary(bool)
0x1800af471  mov     edi, eax
0x1800af473  test    eax, eax
0x1800af475  jns     short loc_1800AF4A0
0x1800af477  mov     rcx, [rbp+208h]; this
0x1800af47e  lea     r8, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\catalog"...
0x1800af485  mov     r9d, eax; char *
0x1800af488  mov     edx, 0D58h; void *
0x1800af48d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af492  lea     rcx, [rbp+200h+var_240]
0x1800af496  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800af49b  jmp     loc_1800B2391
0x1800af4a0  lea     rdx, [rbp+200h+var_188]
0x1800af4a4  mov     rcx, r14
0x1800af4a7  call    ?GetPackagedComCurrentPackageProvider@CComCatalog@@AEAA?AV?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@XZ; CComCatalog::GetPackagedComCurrentPackageProvider(void)
0x1800af4ac  mov     rdx, rax
0x1800af4af  lea     rcx, [rbp+200h+var_240]
0x1800af4b3  call    ??4?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> &&)
0x1800af4b8  lea     rcx, [rbp+200h+var_188]
0x1800af4bc  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800af4c1  mov     rbx, [rbp+200h+var_240]
0x1800af4c5  mov     r14, [rbp+200h+var_208]
0x1800af4c9  mov     [rbp+200h+var_250], r12
0x1800af4cd  test    r14, r14
0x1800af4d0  jz      loc_1800AF5A6
0x1800af4d6  mov     rax, [r14]
0x1800af4d9  lea     r8, [rbp+200h+var_1D8]
0x1800af4dd  lea     rdx, [rbp+200h+var_140]
0x1800af4e4  mov     rcx, r14
0x1800af4e7  mov     rax, [rax+28h]
0x1800af4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af4f0  mov     edi, eax
0x1800af4f2  test    eax, eax
0x1800af4f4  jns     short loc_1800AF51F
0x1800af4f6  mov     edx, 0D64h; void *
0x1800af4fb  mov     r9d, eax; char *
0x1800af4fe  mov     rcx, [rbp+208h]; this
0x1800af505  lea     r8, aOnecoreComComb_74; "onecore\\com\\combase\\catalog\\catalog"...
0x1800af50c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af511  lea     rcx, [rbp+200h+var_250]
0x1800af515  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800af51a  jmp     loc_1800AF492
0x1800af51f  mov     rax, [r14]
0x1800af522  lea     r8, [rbp+200h+var_1D4]
0x1800af526  lea     rdx, [rbp+200h+var_148]
0x1800af52d  mov     rcx, r14
0x1800af530  mov     rax, [rax+38h]
0x1800af534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af539  mov     edi, eax
0x1800af53b  test    eax, eax
0x1800af53d  jns     short loc_1800AF546
0x1800af53f  mov     edx, 0D65h
0x1800af544  jmp     short loc_1800AF4FB
0x1800af546  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800af54d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800af552  test    al, al
0x1800af554  jz      short loc_1800AF5A6
0x1800af556  mov     rdx, [rbp+200h+var_250]
0x1800af55a  mov     rax, [r14]
0x1800af55d  mov     [rbp+200h+var_250], r12
0x1800af561  mov     rdi, [rax]
0x1800af564  test    rdx, rdx
0x1800af567  jz      short loc_1800AF578
0x1800af569  mov     rcx, [rdx]
0x1800af56c  mov     rax, [rcx+10h]
0x1800af570  mov     rcx, rdx
0x1800af573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af578  lea     r8, [rbp+200h+var_250]
0x1800af57c  mov     rcx, r14
0x1800af57f  lea     rdx, _GUID_000001fc_0000_0000_cfff_123045660046
0x1800af586  mov     rax, rdi
0x1800af589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af58e  mov     edi, eax
0x1800af590  test    eax, eax
0x1800af592  jns     short loc_1800AF5A6
0x1800af594  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800af599  mov     r9d, edi
0x1800af59c  mov     edx, 0D6Bh
0x1800af5a1  jmp     loc_1800AF4FE
0x1800af5a6  mov     ecx, [rsp+300h+var_290]; unsigned int
0x1800af5aa  call    ?FlagsForCacheKey@CComCatalog@@CAKK@Z; CComCatalog::FlagsForCacheKey(ulong)
0x1800af5af  btr     eax, 1Bh
0x1800af5b3  mov     [rbp+200h+var_138], r15
0x1800af5ba  mov     [rbp+200h+var_150], eax
0x1800af5c0  mov     [rbp+200h+var_22C], eax
0x1800af5c3  mov     rax, [rbp+200h+var_140]
0x1800af5ca  mov     [rbp+200h+var_130], rax
0x1800af5d1  mov     rax, [rbp+200h+var_148]
0x1800af5d8  mov     [rbp+200h+var_128], rax
0x1800af5df  lea     rax, [rbp+200h+var_150]
0x1800af5e6  mov     [rbp+200h+var_120], rax
0x1800af5ed  mov     eax, 10h
0x1800af5f2  mov     [rbp+200h+var_190], ax
0x1800af5f6  movzx   eax, [rbp+200h+var_1D8]
0x1800af5fa  mov     [rbp+200h+var_18E], ax
0x1800af5fe  movzx   eax, [rbp+200h+var_1D4]
0x1800af602  mov     [rbp+200h+var_18C], ax
0x1800af606  mov     eax, 4
0x1800af60b  mov     [rbp+200h+var_18A], ax
0x1800af60f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800af616  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800af61b  xor     r15d, r15d
0x1800af61e  lea     r14d, [r15+1]
0x1800af622  test    al, al
0x1800af624  jz      short loc_1800AF63B
0x1800af626  mov     ecx, [rsp+300h+var_290]
0x1800af62a  mov     edi, esi
0x1800af62c  shr     edi, 9
0x1800af62f  btr     ecx, 9
0x1800af633  and     dil, r14b
0x1800af636  mov     [rbp+200h+var_1D0], edi
0x1800af639  jmp     short loc_1800AF64E
0x1800af63b  mov     eax, [rsp+300h+var_290]
0x1800af63f  mov     ecx, eax
0x1800af641  btr     ecx, 9
  ... truncated ...
```
