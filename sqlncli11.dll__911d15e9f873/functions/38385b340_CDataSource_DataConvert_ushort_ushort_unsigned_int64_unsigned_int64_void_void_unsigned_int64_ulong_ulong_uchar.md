# CDataSource::DataConvert(ushort,ushort,unsigned __int64,unsigned __int64 *,void *,void *,unsigned __int64,ulong,ulong *,uchar,uchar,ECONVERSIONERROR *,uint,uint,ulong)

- ea: `0x38385b340`
- end: `0x3838651c6`
- name: `?DataConvert@CDataSource@@QEAAJGG_KPEA_KPEAX20KPEAKEEPEAW4ECONVERSIONERROR@@IIK@Z`
- size: `40582`
- prototype: `__int64 __fastcall(CDataSource *__hidden this, unsigned __int16, unsigned __int16, unsigned __int64, unsigned __int64 *, void *, void *, unsigned __int64, unsigned int, unsigned int *, char, char, enum ECONVERSIONERROR *, UINT, UINT CodePage, unsigned int)`
- caller_count: `18`
- callee_count: `68`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x383852260`
- `0x3838555b0`
- `0x38385b340`
- `0x3838a5980`
- `0x3839b32c0`
- `0x3839b5030`
- `0x3839b79c0`
- `0x3839b87a0`
- `0x383a05e40`
- `0x383a091b0`
- `0x383a0c470`
- `0x383a0cbd0`
- `0x383a1e4c0`
- `0x383a34610`
- `0x383a393f0`
- `0x383a63970`
- `0x383a65000`
- `0x383a7c230`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x383844d50`
- `0x383854070`
- `0x38385ac40`
- `0x38385b340`
- `0x383866d00`
- `0x3838676f0`
- `0x38387aa50`
- `0x383884bb0`
- `0x383893160`
- `0x38391aed0`
- `0x38391afe0`
- `0x383986a70`
- `0x3839976c0`
- `0x383997880`
- `0x3839afa40`
- `0x3839afae0`
- `0x3839afba0`
- `0x3839afc70`
- `0x3839afd00`
- `0x3839b0000`
- `0x3839b0570`
- `0x3839b0600`
- `0x3839b0880`
- `0x3839b0bb0`
- `0x3839b0ca0`
- `0x3839b1b00`
- `0x3839b1ea0`
- `0x3839b2260`
- `0x3839b2740`
- `0x3839b2ba0`
- `0x3839b2e90`
- `0x3839b2ed0`
- `0x3839b3010`
- `0x3839b81f0`
- `0x3839b87a0`
- `0x3839b9650`
- `0x3839bb270`
- `0x3839bb380`
- `0x3839bb5f0`
- `0x3839bb860`
- `0x3839bbbf0`
- `0x3839c05e0`
- `0x3839c0610`
- `0x3839c0770`
- `0x3839c0820`
- `0x3839c09c0`
- `0x3839c0c20`
- `0x3839c0d10`

## import_xrefs

- `MSVCR100!swscanf_s` at `0x38385fbe1`
- `MSVCR100!swscanf_s` at `0x38385fbe1`
- `MSVCR100!strncpy_s` at `0x38385c361`
- `MSVCR100!strncpy_s` at `0x38385c361`
- `MSVCR100!memcpy_s` at `0x38385c3b7`
- `MSVCR100!memcpy_s` at `0x38385c3b7`
- `MSVCR100!iswspace` at `0x38385fbf0`
- `MSVCR100!iswspace` at `0x38385fbf0`
- `MSVCR100!iswdigit` at `0x38385fc33`
- `MSVCR100!iswdigit` at `0x38385fc33`
- `MSVCR100!wcsncpy_s` at `0x38385c378`
- `MSVCR100!wcsncpy_s` at `0x38385c378`
- `KERNEL32!WideCharToMultiByte` at `0x383861b5a`
- `KERNEL32!WideCharToMultiByte` at `0x383861c3b`
- `KERNEL32!WideCharToMultiByte` at `0x383861b5a`
- `KERNEL32!WideCharToMultiByte` at `0x383861c3b`
- `KERNEL32!SystemTimeToFileTime` at `0x38385fce2`
- `KERNEL32!SystemTimeToFileTime` at `0x38385fde8`
- `KERNEL32!SystemTimeToFileTime` at `0x383860ac4`
- `KERNEL32!SystemTimeToFileTime` at `0x3838611b8`
- `KERNEL32!SystemTimeToFileTime` at `0x38386341f`
- `KERNEL32!SystemTimeToFileTime` at `0x38385fce2`
- `KERNEL32!SystemTimeToFileTime` at `0x38385fde8`
- `KERNEL32!SystemTimeToFileTime` at `0x383860ac4`
- `KERNEL32!SystemTimeToFileTime` at `0x3838611b8`
- `KERNEL32!SystemTimeToFileTime` at `0x38386341f`
- `KERNEL32!GetLocalTime` at `0x383860e08`
- `KERNEL32!GetLocalTime` at `0x3838620a8`
- `KERNEL32!GetLocalTime` at `0x383862166`
- `KERNEL32!GetLocalTime` at `0x383862497`
- `KERNEL32!GetLocalTime` at `0x383862872`
- `KERNEL32!GetLocalTime` at `0x38386291b`
- `KERNEL32!GetLocalTime` at `0x383860e08`
- `KERNEL32!GetLocalTime` at `0x3838620a8`
- `KERNEL32!GetLocalTime` at `0x383862166`
- `KERNEL32!GetLocalTime` at `0x383862497`
- `KERNEL32!GetLocalTime` at `0x383862872`
- `KERNEL32!GetLocalTime` at `0x38386291b`
- `KERNEL32!FileTimeToSystemTime` at `0x38385dd81`
- `KERNEL32!FileTimeToSystemTime` at `0x38385df80`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e02c`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e15f`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e1dd`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e23d`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e2a7`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e3fd`
- `KERNEL32!FileTimeToSystemTime` at `0x383862a72`
- `KERNEL32!FileTimeToSystemTime` at `0x38385dd81`
- `KERNEL32!FileTimeToSystemTime` at `0x38385df80`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e02c`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e15f`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e1dd`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e23d`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e2a7`
- `KERNEL32!FileTimeToSystemTime` at `0x38385e3fd`
- `KERNEL32!FileTimeToSystemTime` at `0x383862a72`
- `ole32!CLSIDFromString` at `0x3838605c0`
- `ole32!CLSIDFromString` at `0x383862e43`
- `ole32!CLSIDFromString` at `0x3838605c0`
- `ole32!CLSIDFromString` at `0x383862e43`
- `ole32!StringFromGUID2` at `0x38385e5bd`
- `ole32!StringFromGUID2` at `0x38385e630`
- `ole32!StringFromGUID2` at `0x38385e5bd`
- `ole32!StringFromGUID2` at `0x38385e630`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x38385b744`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x38385c3e2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x38385d1f5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x38385e64f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x3838618fc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x383861939`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x38385b744`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x38385c3e2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x38385d1f5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x38385e64f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x3838618fc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x383861939`
- `OLEAUT32!__imp_SysStringLen` at `0x38385ed91`
- `OLEAUT32!__imp_SysStringLen` at `0x38385ef74`
- `OLEAUT32!__imp_SysStringLen` at `0x38385f1ae`
- `OLEAUT32!__imp_SysStringLen` at `0x38385f389`
- `OLEAUT32!__imp_SysStringLen` at `0x38385f5f9`
- `OLEAUT32!__imp_SysStringLen` at `0x38385f89f`
- `OLEAUT32!__imp_SysStringLen` at `0x383860535`
- `OLEAUT32!__imp_SysStringLen` at `0x383862df2`
- `OLEAUT32!__imp_SysStringLen` at `0x38385ed91`
- `OLEAUT32!__imp_SysStringLen` at `0x38385ef74`
- `OLEAUT32!__imp_SysStringLen` at `0x38385f1ae`
- `OLEAUT32!__imp_SysStringLen` at `0x38385f389`
- `OLEAUT32!__imp_SysStringLen` at `0x38385f5f9`
- `OLEAUT32!__imp_SysStringLen` at `0x38385f89f`
- `OLEAUT32!__imp_SysStringLen` at `0x383860535`
- `OLEAUT32!__imp_SysStringLen` at `0x383862df2`
- `OLEAUT32!__imp_VariantInit` at `0x38385d5bf`
- `OLEAUT32!__imp_VariantInit` at `0x38385d948`
- `OLEAUT32!__imp_VariantInit` at `0x38385dda5`
- `OLEAUT32!__imp_VariantInit` at `0x38385de97`
- `OLEAUT32!__imp_VariantInit` at `0x38386188f`
- `OLEAUT32!__imp_VariantInit` at `0x38385d5bf`
- `OLEAUT32!__imp_VariantInit` at `0x38385d948`
- `OLEAUT32!__imp_VariantInit` at `0x38385dda5`
- `OLEAUT32!__imp_VariantInit` at `0x38385de97`
- `OLEAUT32!__imp_VariantInit` at `0x38386188f`
- `OLEAUT32!__imp_VariantClear` at `0x383862bae`
- `OLEAUT32!__imp_VariantClear` at `0x383864a82`
- `OLEAUT32!__imp_VariantClear` at `0x383864db0`
- `OLEAUT32!__imp_VariantClear` at `0x383864dc3`
- `OLEAUT32!__imp_VariantClear` at `0x383862bae`
- `OLEAUT32!__imp_VariantClear` at `0x383864a82`
- `OLEAUT32!__imp_VariantClear` at `0x383864db0`
- `OLEAUT32!__imp_VariantClear` at `0x383864dc3`
- `OLEAUT32!__imp_VariantCopy` at `0x38385d5cf`
- `OLEAUT32!__imp_VariantCopy` at `0x3838626e2`
- `OLEAUT32!__imp_VariantCopy` at `0x38385d5cf`
- `OLEAUT32!__imp_VariantCopy` at `0x3838626e2`
- `OLEAUT32!__imp_VariantChangeType` at `0x38385c5da`
- `OLEAUT32!__imp_VariantChangeType` at `0x38385c5da`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x3838627c2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x3838627c2`
- `OLEAUT32!__imp_SafeArrayLock` at `0x3838627d8`
- `OLEAUT32!__imp_SafeArrayLock` at `0x383862e62`
- `OLEAUT32!__imp_SafeArrayLock` at `0x3838627d8`
- `OLEAUT32!__imp_SafeArrayLock` at `0x383862e62`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x383862807`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x383862ea3`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x383862807`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x383862ea3`
- `OLEAUT32!__imp_VarI2FromR4` at `0x38385c7ca`
- `OLEAUT32!__imp_VarI2FromR4` at `0x38385c7ca`
- `OLEAUT32!__imp_VarI2FromR8` at `0x38385ce1e`
- `OLEAUT32!__imp_VarI2FromR8` at `0x383861101`
- `OLEAUT32!__imp_VarI2FromR8` at `0x38385ce1e`
- `OLEAUT32!__imp_VarI2FromR8` at `0x383861101`
- `OLEAUT32!__imp_VarI2FromCy` at `0x38385cb8b`
- `OLEAUT32!__imp_VarI2FromCy` at `0x38385cb8b`
- `OLEAUT32!__imp_VarI2FromStr` at `0x38385e8d5`
- `OLEAUT32!__imp_VarI2FromStr` at `0x38385e8d5`
- `OLEAUT32!__imp_VarI4FromR4` at `0x38385c864`
- `OLEAUT32!__imp_VarI4FromR4` at `0x38385c864`
- `OLEAUT32!__imp_VarI4FromR8` at `0x38385cea2`
- `OLEAUT32!__imp_VarI4FromR8` at `0x38385cea2`
- `OLEAUT32!__imp_VarI4FromCy` at `0x38385cc43`
- `OLEAUT32!__imp_VarI4FromCy` at `0x38385cc43`
- `OLEAUT32!__imp_VarI4FromStr` at `0x38385e9ce`
- `OLEAUT32!__imp_VarI4FromStr` at `0x38385e9ce`
- `OLEAUT32!__imp_VarR4FromR8` at `0x38385cefc`
- `OLEAUT32!__imp_VarR4FromR8` at `0x38385cefc`
- `OLEAUT32!__imp_VarR4FromCy` at `0x38385cc9b`
- `OLEAUT32!__imp_VarR4FromCy` at `0x38385cc9b`
- `OLEAUT32!__imp_VarR4FromStr` at `0x38385eac6`
- `OLEAUT32!__imp_VarR4FromStr` at `0x38385eaee`
- `OLEAUT32!__imp_VarR4FromStr` at `0x38386083f`
- `OLEAUT32!__imp_VarR4FromStr` at `0x38385eac6`
- `OLEAUT32!__imp_VarR4FromStr` at `0x38385eaee`
- `OLEAUT32!__imp_VarR4FromStr` at `0x38386083f`
- `OLEAUT32!__imp_VarR8FromCy` at `0x38385ccbb`
- `OLEAUT32!__imp_VarR8FromCy` at `0x38385ccbb`
- `OLEAUT32!__imp_VarR8FromStr` at `0x38385eb40`
- `OLEAUT32!__imp_VarR8FromStr` at `0x38385eb68`
- `OLEAUT32!__imp_VarR8FromStr` at `0x383860888`
- `OLEAUT32!__imp_VarR8FromStr` at `0x38385eb40`
- `OLEAUT32!__imp_VarR8FromStr` at `0x38385eb68`
- `OLEAUT32!__imp_VarR8FromStr` at `0x383860888`
- `OLEAUT32!__imp_VarDateFromCy` at `0x38385ccfb`
- `OLEAUT32!__imp_VarDateFromCy` at `0x38385ccfb`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385eeb1`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f03b`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f232`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f439`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f739`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f9cb`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385fd5d`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385eeb1`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f03b`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f232`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f439`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f739`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385f9cb`
- `OLEAUT32!__imp_VarDateFromStr` at `0x38385fd5d`
- `OLEAUT32!__imp_VarCyFromI2` at `0x38385d3f1`
- `OLEAUT32!__imp_VarCyFromI2` at `0x38385d3f1`
- `OLEAUT32!__imp_VarCyFromR4` at `0x38385c978`
- `OLEAUT32!__imp_VarCyFromR4` at `0x38385c978`
- `OLEAUT32!__imp_VarCyFromR8` at `0x38385cf3a`
- `OLEAUT32!__imp_VarCyFromR8` at `0x38385cf3a`
- `OLEAUT32!__imp_VarCyFromStr` at `0x38385ebba`
- `OLEAUT32!__imp_VarCyFromStr` at `0x38385ebe2`
- `OLEAUT32!__imp_VarCyFromStr` at `0x38385ebba`
- `OLEAUT32!__imp_VarCyFromStr` at `0x38385ebe2`
- `OLEAUT32!__imp_VarBstrFromCy` at `0x38385cd25`
- `OLEAUT32!__imp_VarBstrFromCy` at `0x38385cd25`
- `OLEAUT32!__imp_VarBstrFromDate` at `0x38385d0fe`
- `OLEAUT32!__imp_VarBstrFromDate` at `0x38385d0fe`
- `OLEAUT32!__imp_VarBoolFromCy` at `0x38385cc23`
- `OLEAUT32!__imp_VarBoolFromCy` at `0x38385cc23`
- `OLEAUT32!__imp_VarBoolFromStr` at `0x38385e97c`
- `OLEAUT32!__imp_VarBoolFromStr` at `0x38385e97c`
- `OLEAUT32!__imp_VarUI1FromR4` at `0x38385c7a0`
- `OLEAUT32!__imp_VarUI1FromR4` at `0x38385c7a0`
- `OLEAUT32!__imp_VarUI1FromR8` at `0x38385cdfd`
- `OLEAUT32!__imp_VarUI1FromR8` at `0x38385cdfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataSource::DataConvert(
        CDataSource *this,
        unsigned __int16 a2,
        int a3,
        __int64 a4,
        unsigned __int64 *a5,
        VARIANTARG *a6,
        char *a7,
        size_t a8,
        unsigned int a9,
        unsigned __int8 *a10,
        char a11,
        char a12,
        enum ECONVERSIONERROR *a13,
        UINT a14,
        UINT CodePage,
        unsigned int a16)
{
  size_t v16; // r11
  enum ECONVERSIONERROR *v17; // rcx
  unsigned __int64 *v18; // rax
  unsigned int *v19; // rsi
  unsigned int v20; // ecx
  VARIANTARG *pvarVal; // rbx
  unsigned __int16 v22; // di
  const void *v23; // rdx
  unsigned int v24; // r10d
  int v25; // eax
  unsigned int v26; // r11d
  _BYTE *v27; // rdi
  int v28; // eax
  unsigned int v29; // edx
  int vt; // r10d
  __int64 v31; // r8
  unsigned __int64 v32; // rsi
  unsigned __int64 v33; // r9
  unsigned __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // eax
  unsigned __int16 *v37; // rax
  CY *v38; // rbx
  int WStrFromStr; // r10d
  HRESULT ConversionSize; // esi
  unsigned int *v41; // rdx
  unsigned __int64 *v42; // rbx
  int *v43; // rcx
  __int64 v44; // r8
  char v45; // dl
  void *v46; // r9
  unsigned int v47; // eax
  int v49; // ecx
  __int16 v50; // di
  const OLECHAR *v51; // rax
  void *(__stdcall **p_Alloc)(IMalloc *, SIZE_T); // rbx
  unsigned __int64 v53; // rax
  size_t v54; // rdx
  char *v55; // rdi
  const OLECHAR *v56; // rbx
  unsigned __int64 v57; // r8
  unsigned __int16 v58; // cx
  int v59; // eax
  unsigned __int16 v60; // cx
  int v61; // eax
  unsigned __int16 v62; // cx
  int v63; // eax
  unsigned __int16 v64; // cx
  int v65; // eax
  unsigned __int16 v66; // cx
  int v67; // eax
  unsigned __int16 v68; // cx
  int v69; // eax
  unsigned __int16 v70; // cx
  int v71; // eax
  unsigned __int16 v72; // cx
  int v73; // eax
  rsize_t v74; // rbx
  wchar_t *v75; // rax
  rsize_t v76; // r9
  void *v77; // rax
  UINT v78; // edx
  HRESULT v79; // eax
  HRESULT v80; // eax
  __int16 v81; // ax
  double v82; // xmm0_8
  double v83; // xmm1_8
  int v84; // edx
  HRESULT v85; // eax
  unsigned __int16 v86; // dx
  DECIMAL *p_pdecOut; // rcx
  unsigned __int64 v88; // r8
  unsigned int *v89; // rsi
  int v90; // eax
  __int64 v91; // rdx
  __int64 v92; // rax
  UINT v93; // eax
  BSTR v94; // rax
  __int64 v95; // rax
  double v96; // xmm0_8
  char *v97; // rcx
  const WCHAR *v98; // rcx
  VARTYPE v99; // ax
  char v100; // al
  VARTYPE v101; // ax
  int v102; // eax
  LONGLONG int64; // rax
  WORD v104; // bx
  WORD wDay; // bx
  WORD wMonth; // di
  WORD v107; // si
  int v108; // eax
  WORD wYear; // bx
  int v110; // eax
  unsigned __int64 v111; // r8
  int v112; // eax
  __int64 v113; // rdx
  LONG Hi; // eax
  int v115; // eax
  BSTR v116; // rax
  char *v117; // rax
  const unsigned __int16 *v118; // rbx
  HRESULT v119; // eax
  HRESULT WStrFromSrc; // r10d
  HRESULT v121; // r10d
  HRESULT v122; // r10d
  HRESULT v123; // r10d
  __int16 v124; // r11
  int v125; // eax
  unsigned __int16 v126; // r8
  int v127; // eax
  unsigned __int16 v128; // ax
  int v129; // r11d
  char v130; // cl
  unsigned int v131; // eax
  VARIANTARG *v132; // rax
  unsigned int v133; // ebx
  unsigned int v134; // ecx
  int v135; // eax
  unsigned int v136; // ebx
  int v137; // eax
  unsigned int v138; // ebx
  int v139; // eax
  LPCOLESTR v140; // rdi
  wint_t v141; // ax
  WORD wMilliseconds; // bx
  __int64 v143; // rsi
  BOOL v144; // eax
  BOOL v145; // eax
  unsigned __int64 v146; // rdi
  unsigned __int16 *v147; // rbx
  unsigned __int16 *p_WideCharStr; // rsi
  int v149; // eax
  __int64 v150; // rdx
  __int64 v151; // rax
  unsigned int v152; // edi
  unsigned __int64 v153; // rcx
  char *v154; // rax
  int v155; // eax
  int *v156; // rcx
  size_t v157; // rcx
  __int64 v158; // r8
  size_t v159; // r9
  int v160; // eax
  size_t v161; // rbx
  char *v162; // rax
  size_t v163; // r8
  unsigned __int64 v164; // rdi
  int v165; // esi
  __int64 v166; // rcx
  int v167; // eax
  char *v168; // rax
  size_t v169; // r9
  int v170; // eax
  size_t v171; // rbx
  int v172; // eax
  unsigned __int64 v173; // rbx
  int v174; // edi
  char *v175; // rax
  char *v176; // rsi
  size_t v177; // r9
  int v178; // eax
  unsigned __int64 v179; // rax
  size_t v180; // rax
  unsigned __int64 v181; // rsi
  char *v182; // rax
  unsigned __int64 v183; // rdi
  int v184; // eax
  OLECHAR *v185; // rbx
  const OLECHAR *v186; // rbx
  OLECHAR *v187; // rax
  size_t *v188; // rcx
  int v189; // eax
  int v190; // r10d
  char *v191; // rax
  char *v192; // r11
  size_t v193; // r9
  LPCOLESTR v194; // rdx
  _BYTE *v195; // r8
  wint_t v196; // cx
  wint_t v197; // ax
  wint_t v198; // cx
  __int64 v199; // rdx
  unsigned int v200; // ebx
  bool v201; // zf
  unsigned __int16 year; // bx
  WORD wReserved1; // r11
  WORD wReserved2; // r10
  WORD wReserved3; // r9
  WORD uiVal; // r8
  WORD second; // cx
  __int64 v208; // kr00_8
  unsigned int Mid32; // ebx
  int v210; // eax
  int v211; // ebx
  int v212; // eax
  unsigned int v213; // ebx
  int v214; // ecx
  int v215; // ebx
  int v216; // eax
  VARTYPE v217; // bx
  WORD v218; // bx
  WORD v219; // di
  unsigned int v220; // ebx
  char *v221; // r10
  VARTYPE v222; // bx
  LONG lVal; // eax
  unsigned int v224; // edx
  const OLECHAR *p_vt; // rcx
  BSTR v226; // rax
  size_t v227; // r11
  int v228; // eax
  char *v229; // rax
  size_t v230; // r9
  LPCOLESTR v231; // rdx
  LPCOLESTR v232; // rdi
  size_t v233; // rbx
  size_t v234; // r9
  OLECHAR v235; // cx
  OLECHAR v236; // cx
  size_t v237; // r11
  const WCHAR *v238; // rdi
  int v239; // eax
  __int64 v240; // rcx
  int v241; // eax
  char *v242; // rax
  char *v243; // rbx
  int v244; // r9d
  int v245; // eax
  WINBOOL *v246; // rdx
  size_t v247; // rcx
  size_t v248; // r9
  size_t v249; // rbx
  char *v250; // rax
  void *v251; // rcx
  size_t v252; // r8
  size_t v253; // r8
  size_t v254; // r8
  size_t v255; // rbx
  char *v256; // rax
  size_t v257; // r8
  char *v258; // rax
  unsigned int v259; // eax
  unsigned int v260; // eax
  WORD v261; // ax
  unsigned int v262; // esi
  unsigned int v263; // eax
  WORD v264; // si
  WORD v265; // di
  int v266; // eax
  int v267; // ebx
  int v268; // eax
  unsigned __int64 v269; // r8
  unsigned int Lo; // eax
  WORD v271; // si
  WORD v272; // di
  int v273; // ecx
  int v274; // ebx
  int v275; // eax
  __int64 v276; // rdx
  VARTYPE v277; // r9
  __int16 v278; // r11
  HRESULT v279; // r10d
  int v280; // ecx
  unsigned int *v281; // rsi
  SAFEARRAY *v282; // rax
  INT v283; // eax
  int v284; // eax
  unsigned __int16 v285; // ax
  BYTE v286; // al
  ULONG v287; // eax
  int valid; // eax
  BYTE v289; // al
  unsigned int v290; // ecx
  VARTYPE v291; // ax
  unsigned int v292; // ecx
  HRESULT v293; // r10d
  unsigned __int64 v294; // r8
  unsigned __int64 v295; // rbx
  unsigned __int64 v296; // rbx
  size_t v297; // r8
  size_t v298; // rcx
  unsigned int v299; // r8d
  __int64 v300; // rsi
  signed int v301; // ebx
  BYTE *v302; // rdi
  unsigned __int8 v303; // r9
  unsigned __int64 v304; // rcx
  double v305; // xmm0_8
  char v306; // cl
  BYTE v307; // al
  BYTE scale; // al
  __int16 tm_sec; // bx
  __int16 tm_min; // di
  __int16 tm_hour; // si
  char *v312; // r10
  __int16 v313; // di
  __int16 v314; // si
  unsigned int v315; // ebx
  int v316; // eax
  int v317; // esi
  unsigned int v318; // edi
  int v319; // eax
  int v320; // ecx
  int v321; // eax
  int v322; // ebx
  int v323; // eax
  unsigned __int64 v324; // r8
  char *v325; // rax
  unsigned int v326; // esi
  char v327; // bl
  int v328; // eax
  unsigned int v329; // ebx
  __int16 v330; // di
  __int16 v331; // si
  unsigned int v332; // ebx
  int v333; // ecx
  int v334; // esi
  unsigned int v335; // edi
  int v336; // ecx
  int v337; // eax
  int v338; // ebx
  int v339; // eax
  __int64 v340; // rdx
  unsigned __int16 v341; // ax
  unsigned __int16 v342; // ax
  unsigned int v343; // ebx
  unsigned __int16 v344; // di
  char *v345; // r10
  SQLUINTEGER fraction; // eax
  unsigned __int16 v347; // ax
  unsigned int v348; // ebx
  VARTYPE v349; // di
  char *v350; // r10
  char *v351; // rcx
  __int64 v352; // rdx
  unsigned __int16 v353; // dx
  int v354; // eax
  unsigned __int64 v355; // rax
  char *lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  size_t cbMultiByte; // [rsp+28h] [rbp-D8h]
  VARIANTARG *cbMultiBytea; // [rsp+28h] [rbp-D8h]
  VARIANTARG *lpDefaultChar; // [rsp+30h] [rbp-D0h]
  const char *lpDefaultChara; // [rsp+30h] [rbp-D0h]
  LPCCH lpDefaultCharb; // [rsp+30h] [rbp-D0h]
  int *lpUsedDefaultChar; // [rsp+38h] [rbp-C8h]
  int *lpUsedDefaultChara; // [rsp+38h] [rbp-C8h]
  LPBOOL lpUsedDefaultCharb; // [rsp+38h] [rbp-C8h]
  unsigned int *p_wMilliseconds; // [rsp+40h] [rbp-C0h]
  char v366; // [rsp+40h] [rbp-C0h]
  unsigned int *v367; // [rsp+40h] [rbp-C0h]
  unsigned int v368; // [rsp+40h] [rbp-C0h]
  unsigned __int8 *v369; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v370; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v371; // [rsp+50h] [rbp-B0h]
  char v372; // [rsp+50h] [rbp-B0h]
  unsigned __int8 *v373; // [rsp+58h] [rbp-A8h]
  char v374; // [rsp+58h] [rbp-A8h]
  UINT v375; // [rsp+68h] [rbp-98h]
  UINT v376; // [rsp+70h] [rbp-90h]
  unsigned int v377; // [rsp+78h] [rbp-88h]
  HRESULT v378; // [rsp+80h] [rbp-80h]
  HRESULT v379; // [rsp+80h] [rbp-80h]
  unsigned int *v380; // [rsp+88h] [rbp-78h]
  unsigned __int8 v381; // [rsp+90h] [rbp-70h]
  VARIANTARG *pvargSrc; // [rsp+98h] [rbp-68h]
  unsigned __int64 *v383; // [rsp+A0h] [rbp-60h]
  unsigned __int8 v384[4]; // [rsp+A8h] [rbp-58h] BYREF
  int v385; // [rsp+ACh] [rbp-54h]
  unsigned __int8 v386[4]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v387; // [rsp+B4h] [rbp-4Ch]
  size_t Size; // [rsp+B8h] [rbp-48h]
  UINT ui[2]; // [rsp+C0h] [rbp-40h] BYREF
  char *Source; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v391[4]; // [rsp+D0h] [rbp-30h]
  LPCOLESTR lpsz; // [rsp+D8h] [rbp-28h] BYREF
  wint_t v393; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int v395; // [rsp+100h] [rbp+0h]
  void *v396; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v397; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *cchWideChar; // [rsp+118h] [rbp+18h] BYREF
  struct tm v399; // [rsp+120h] [rbp+20h] BYREF
  tagTIMESTAMP_STRUCT v400; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v401[2]; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v402; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v403; // [rsp+164h] [rbp+64h] BYREF
  enum ECONVERSIONERROR *v404; // [rsp+168h] [rbp+68h]
  unsigned int v405; // [rsp+170h] [rbp+70h] BYREF
  CDataSource *v406; // [rsp+178h] [rbp+78h]
  __int16 v407[2]; // [rsp+180h] [rbp+80h] BYREF
  int v408; // [rsp+184h] [rbp+84h]
  __int16 v409; // [rsp+188h] [rbp+88h]
  __int16 v410; // [rsp+18Ch] [rbp+8Ch] BYREF
  unsigned __int8 v411[4]; // [rsp+190h] [rbp+90h] BYREF
  __int16 v412; // [rsp+194h] [rbp+94h] BYREF
  __int16 v413[2]; // [rsp+198h] [rbp+98h] BYREF
  __int16 v414; // [rsp+19Ch] [rbp+9Ch] BYREF
  __int16 v415[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int8 v416; // [rsp+1A4h] [rbp+A4h] BYREF
  unsigned __int16 v417; // [rsp+1A6h] [rbp+A6h]
  __int16 v418[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int16 v419; // [rsp+1ACh] [rbp+ACh] BYREF
  unsigned __int16 *v420; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int64 v421; // [rsp+1B8h] [rbp+B8h] BYREF
  int v422; // [rsp+1C0h] [rbp+C0h]
  unsigned int v423; // [rsp+1C4h] [rbp+C4h] BYREF
  int v424; // [rsp+1C8h] [rbp+C8h]
  int v425; // [rsp+1CCh] [rbp+CCh]
  unsigned int v426; // [rsp+1D0h] [rbp+D0h] BYREF
  int v427; // [rsp+1D4h] [rbp+D4h] BYREF
  int v428; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int v429; // [rsp+1DCh] [rbp+DCh] BYREF
  int v430; // [rsp+1E0h] [rbp+E0h]
  VARIANTARG v431; // [rsp+1E8h] [rbp+E8h] BYREF
  void *v432; // [rsp+200h] [rbp+100h]
  int v433; // [rsp+210h] [rbp+110h] BYREF
  int v434; // [rsp+214h] [rbp+114h]
  int v435; // [rsp+218h] [rbp+118h]
  int v436; // [rsp+21Ch] [rbp+11Ch]
  int v437; // [rsp+220h] [rbp+120h]
  VARIANTARG *v438; // [rsp+228h] [rbp+128h]
  char v439; // [rsp+230h] [rbp+130h]
  size_t v440; // [rsp+238h] [rbp+138h]
  __int64 v441; // [rsp+240h] [rbp+140h]
  __int64 v442; // [rsp+248h] [rbp+148h]
  int v443; // [rsp+250h] [rbp+150h]
  __int16 v444; // [rsp+254h] [rbp+154h]
  __int16 v445; // [rsp+256h] [rbp+156h]
  int v446; // [rsp+260h] [rbp+160h] BYREF
  int v447; // [rsp+264h] [rbp+164h]
  int v448; // [rsp+268h] [rbp+168h]
  unsigned int v449; // [rsp+26Ch] [rbp+16Ch]
  int v450; // [rsp+270h] [rbp+170h]
  VARIANTARG *v451; // [rsp+278h] [rbp+178h]
  char v452; // [rsp+280h] [rbp+180h]
  size_t v453; // [rsp+288h] [rbp+188h]
  __int64 v454; // [rsp+290h] [rbp+190h]
  __int64 v455; // [rsp+298h] [rbp+198h]
  int v456; // [rsp+2A0h] [rbp+1A0h]
  __int16 v457; // [rsp+2A4h] [rbp+1A4h]
  __int16 v458; // [rsp+2A6h] [rbp+1A6h]
  int v459; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v460; // [rsp+2B4h] [rbp+1B4h]
  int v461; // [rsp+2B8h] [rbp+1B8h]
  unsigned int v462; // [rsp+2BCh] [rbp+1BCh]
  int v463; // [rsp+2C0h] [rbp+1C0h]
  VARIANTARG *v464; // [rsp+2C8h] [rbp+1C8h]
  char v465; // [rsp+2D0h] [rbp+1D0h]
  size_t v466; // [rsp+2D8h] [rbp+1D8h]
  __int64 v467; // [rsp+2E0h] [rbp+1E0h]
  __int64 v468; // [rsp+2E8h] [rbp+1E8h]
  int v469; // [rsp+2F0h] [rbp+1F0h]
  __int16 v470; // [rsp+2F4h] [rbp+1F4h]
  __int16 v471; // [rsp+2F6h] [rbp+1F6h]
  int v472; // [rsp+300h] [rbp+200h] BYREF
  int v473; // [rsp+304h] [rbp+204h]
  int v474; // [rsp+308h] [rbp+208h]
  int v475; // [rsp+30Ch] [rbp+20Ch]
  int v476; // [rsp+310h] [rbp+210h]
  VARIANTARG *v477; // [rsp+318h] [rbp+218h]
  char v478; // [rsp+320h] [rbp+220h]
  size_t v479; // [rsp+328h] [rbp+228h]
  __int64 v480; // [rsp+330h] [rbp+230h]
  __int64 v481; // [rsp+338h] [rbp+238h]
  int v482; // [rsp+340h] [rbp+240h]
  __int16 v483; // [rsp+344h] [rbp+244h]
  __int16 v484; // [rsp+346h] [rbp+246h]
  int v485; // [rsp+350h] [rbp+250h] BYREF
  int v486; // [rsp+354h] [rbp+254h]
  int v487; // [rsp+358h] [rbp+258h]
  int v488; // [rsp+35Ch] [rbp+25Ch]
  int v489; // [rsp+360h] [rbp+260h]
  VARIANTARG *v490; // [rsp+368h] [rbp+268h]
  char v491; // [rsp+370h] [rbp+270h]
  size_t v492; // [rsp+378h] [rbp+278h]
  __int64 v493; // [rsp+380h] [rbp+280h]
  __int64 v494; // [rsp+388h] [rbp+288h]
  int v495; // [rsp+390h] [rbp+290h]
  __int16 v496; // [rsp+394h] [rbp+294h]
  __int16 v497; // [rsp+396h] [rbp+296h]
  __int64 v498; // [rsp+3A0h] [rbp+2A0h]
  void *Src; // [rsp+3A8h] [rbp+2A8h]
  SAFEARRAYBOUND rgsabound; // [rsp+3B0h] [rbp+2B0h] BYREF
  int v501; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v502; // [rsp+3C4h] [rbp+2C4h]
  int v503; // [rsp+3C8h] [rbp+2C8h]
  int v504; // [rsp+3CCh] [rbp+2CCh]
  int v505; // [rsp+3D0h] [rbp+2D0h]
  VARIANTARG *v506; // [rsp+3D8h] [rbp+2D8h]
  char v507; // [rsp+3E0h] [rbp+2E0h]
  size_t v508; // [rsp+3E8h] [rbp+2E8h]
  __int64 v509; // [rsp+3F0h] [rbp+2F0h]
  __int64 v510; // [rsp+3F8h] [rbp+2F8h]
  int v511; // [rsp+400h] [rbp+300h]
  __int16 v512; // [rsp+404h] [rbp+304h]
  __int16 v513; // [rsp+406h] [rbp+306h]
  __int64 v514; // [rsp+410h] [rbp+310h]
  BSTR v515; // [rsp+418h] [rbp+318h] BYREF
  BSTR pbstrOut; // [rsp+420h] [rbp+320h] BYREF
  BSTR v517; // [rsp+428h] [rbp+328h] BYREF
  DATE v518; // [rsp+430h] [rbp+330h] BYREF
  size_t v519; // [rsp+438h] [rbp+338h]
  DOUBLE v520; // [rsp+440h] [rbp+340h] BYREF
  char v521; // [rsp+448h] [rbp+348h] BYREF
  DATE pdateOut; // [rsp+450h] [rbp+350h] BYREF
  DATE v523; // [rsp+458h] [rbp+358h] BYREF
  DATE v524; // [rsp+460h] [rbp+360h] BYREF
  DATE v525; // [rsp+468h] [rbp+368h] BYREF
  DATE v526; // [rsp+470h] [rbp+370h] BYREF
  char *v527; // [rsp+478h] [rbp+378h]
  char v528; // [rsp+480h] [rbp+380h] BYREF
  DOUBLE dblIn; // [rsp+488h] [rbp+388h] BYREF
  VARIANTARG pvargDest; // [rsp+490h] [rbp+390h] BYREF
  _QWORD v531[2]; // [rsp+4A8h] [rbp+3A8h] BYREF
  int v532; // [rsp+4B8h] [rbp+3B8h]
  int v533; // [rsp+4BCh] [rbp+3BCh]
  VARIANTARG pvarSrc; // [rsp+4C0h] [rbp+3C0h] BYREF
  _QWORD v535[2]; // [rsp+4D8h] [rbp+3D8h] BYREF
  int v536; // [rsp+4E8h] [rbp+3E8h]
  int v537; // [rsp+4ECh] [rbp+3ECh]
  __int64 v538; // [rsp+4F0h] [rbp+3F0h]
  _SYSTEMTIME SystemTime; // [rsp+4F8h] [rbp+3F8h] BYREF
  struct tagDB_NUMERIC v540; // [rsp+508h] [rbp+408h] BYREF
  struct _SYSTEMTIME v541; // [rsp+520h] [rbp+420h] BYREF
  DECIMAL pdecOut; // [rsp+530h] [rbp+430h] BYREF
  struct _SYSTEMTIME v543; // [rsp+540h] [rbp+440h] BYREF
  struct _SYSTEMTIME v544; // [rsp+550h] [rbp+450h] BYREF
  struct _SYSTEMTIME v545; // [rsp+560h] [rbp+460h] BYREF
  struct _SYSTEMTIME v546; // [rsp+570h] [rbp+470h] BYREF
  struct _SYSTEMTIME v547; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int8 v548[112]; // [rsp+590h] [rbp+490h] BYREF
  unsigned __int8 v549[8]; // [rsp+600h] [rbp+500h] BYREF
  __int64 v550; // [rsp+608h] [rbp+508h]
  OLECHAR sz[264]; // [rsp+610h] [rbp+510h] BYREF
  OLECHAR strIn[112]; // [rsp+820h] [rbp+720h] BYREF
  _BYTE v553[112]; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v554[224]; // [rsp+970h] [rbp+870h] BYREF
  WCHAR WideCharStr; // [rsp+A50h] [rbp+950h] BYREF

  v538 = -2;
  v387 = a3;
  *(_DWORD *)v391 = a2;
  v406 = this;
  *(_QWORD *)ui = a4;
  pvargSrc = a6;
  v396 = a6;
  Source = a7;
  v16 = a8;
  Size = a8;
  v381 = a12;
  v384[0] = a12;
  v17 = a13;
  v404 = a13;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_383B49608[0] )
    {
      v373 = a10;
      LODWORD(v371) = a9;
      HIDWORD(v369) = HIDWORD(a8);
      HIDWORD(p_wMilliseconds) = HIDWORD(a7);
      lpUsedDefaultChar = (int *)v396;
      lpDefaultChar = (VARIANTARG *)a5;
      cbMultiByte = *(_QWORD *)ui;
      LODWORD(lpMultiByteStr) = (unsigned __int16)a3;
      bidTraceW(off_383B43280[0], 901120, off_383B49608[0], a2);
      v16 = Size;
      a3 = v387;
      v17 = v404;
    }
    pvargSrc = (VARIANTARG *)v396;
    v381 = v384[0];
  }
  v432 = 0;
  lpsz = 0;
  v385 = 0;
  v424 = 0;
  v408 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v431, 0, sizeof(v431));
  v425 = 0;
  v430 = 0;
  Src = 0;
  if ( v17 )
    *(_DWORD *)v17 = 0;
  v18 = (unsigned __int64 *)&v528;
  if ( a5 )
    v18 = a5;
  v383 = v18;
  v19 = (unsigned int *)&v521;
  if ( a10 )
    v19 = (unsigned int *)a10;
  v380 = v19;
  v20 = a9;
  switch ( a9 )
  {
    case 3u:
      if ( (_WORD)a3 == 12 && Source )
      {
        if ( v16 < 0x18 )
        {
          ConversionSize = -2147024809;
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
            bidTraceW(off_383B43280[0], 976937, off_383B49128[0], 2147942487LL);
          goto LABEL_76;
        }
        *(_WORD *)Source = 1;
        v20 = 3;
      }
      goto LABEL_1761;
    case 8u:
      *v19 = 8;
      *v18 = 0;
      ConversionSize = -2147217887;
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        bidTraceW(off_383B43280[0], 993321, off_383B49128[0], 2147749409LL);
      goto LABEL_76;
    case 0xDu:
LABEL_1761:
      *v19 = v20;
      *v18 = 0;
      ConversionSize = 0;
      goto LABEL_76;
  }
  pvarVal = pvargSrc;
  v22 = v391[0];
  if ( !(unsigned int)CheckBufferAlignment(v391[0], pvargSrc, a3) )
  {
    pvarVal = (VARIANTARG *)v548;
    pvargSrc = (VARIANTARG *)v548;
    v396 = v548;
    *(_QWORD *)ui = `GetFixedLengthOLEDBTypeSize'::`2'::fixedLenSizes[v391[0]];
    memcpy(v548, v23, *(size_t *)ui);
    v24 = 0;
  }
  v25 = v391[0] & 0xFFF;
  if ( v25 == 9 || v25 == 12 )
    v425 = 1;
  *v19 = v24;
  v378 = v24;
  v417 = v22;
  LOWORD(v26) = v387;
  v409 = v387;
  if ( (v22 & 0xBFFF) == 0x90 )
  {
    if ( !pvarVal )
    {
      *v19 = 2;
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        bidTraceW(off_383B43280[0], 1077289, off_383B49128[0], 2147749405LL);
      return 2147749405LL;
    }
    if ( (v387 & 0xBFFF) != 0x90 )
    {
      *(_DWORD *)v391 = FixUpSourceData(&v396, (unsigned __int64 *)ui, &a16, v384);
      pvarVal = (VARIANTARG *)v396;
      pvargSrc = (VARIANTARG *)v396;
      v381 = v384[0];
      LOWORD(v26) = v387;
    }
  }
  if ( (unsigned __int16)v26 <= 0xEu )
    goto LABEL_17;
  ConversionSize = IsLegalDBtype(v26);
  v378 = ConversionSize;
  if ( ConversionSize < 0 )
    goto LABEL_56;
  v26 = v387;
  if ( (v387 & 0xF000) == 0 )
  {
LABEL_109:
    v19 = v380;
LABEL_17:
    v27 = Source;
    goto LABEL_18;
  }
  if ( (v387 & 0x4000) == 0 )
  {
    if ( (v387 & 0x9000) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      {
        LODWORD(lpMultiByteStr) = 1106;
        bidTraceW(off_383B43280[0], 1132585, off_383B49128[0], 2147749405LL);
      }
      goto LABEL_108;
    }
    goto LABEL_109;
  }
  LOWORD(v26) = v387 & 0xBFFF;
  v387 = v26;
  if ( (unsigned __int16)v26 < 0x80u
    || (unsigned __int16)v26 > 0x82u
    && (unsigned __int16)v26 != 132
    && (unsigned __int16)v26 != 141
    && (unsigned __int16)v26 != 144 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    {
      LODWORD(lpMultiByteStr) = 1098;
      bidTraceW(off_383B43280[0], 1124393, off_383B49128[0], 2147749405LL);
    }
    ConversionSize = -2147217891;
LABEL_103:
    *v380 = 2;
    goto LABEL_56;
  }
  v27 = Source;
  v19 = v380;
  if ( Source )
  {
    v28 = 1;
    v385 = 1;
    goto LABEL_19;
  }
LABEL_18:
  v28 = v385;
LABEL_19:
  v29 = a16;
  if ( (a16 & 1) != 0 )
  {
    v432 = v27;
    if ( !v27 )
      goto LABEL_127;
    if ( !v28 )
    {
      if ( (unsigned __int16)v26 < 0x80u )
        goto LABEL_126;
      if ( (unsigned __int16)v26 > 0x82u && (unsigned __int16)v26 != 132 && (unsigned __int16)v26 != 141 )
      {
        if ( (unsigned __int16)v26 == 144 )
          goto LABEL_20;
LABEL_126:
        v27 = v553;
        Source = v553;
        Size = 110;
        goto LABEL_22;
      }
      if ( Size <= 0xDE )
      {
        v27 = v554;
        Source = v554;
        goto LABEL_22;
      }
      v27 = (_BYTE *)((__int64 (__fastcall *)(struct IMalloc *, size_t, __int64))g_pMO->lpVtbl->Alloc)(g_pMO, Size, 141);
      Source = v27;
      if ( v27 )
      {
        v424 = 1;
        v29 = a16;
        goto LABEL_20;
      }
      *v19 = 2;
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        bidTraceW(off_383B43280[0], 1175593, off_383B49128[0], 2147942414LL);
      ConversionSize = -2147024882;
LABEL_76:
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_383B49600[0] )
          bidTraceW(off_383B43280[0], 8943616, off_383B49600[0], (unsigned int)ConversionSize);
      }
      return (unsigned int)ConversionSize;
    }
  }
LABEL_20:
  if ( v27 )
  {
    LOWORD(v26) = v387;
LABEL_22:
    vt = *(_DWORD *)v391;
    v31 = 49151;
    goto LABEL_23;
  }
LABEL_127:
  vt = *(_DWORD *)v391;
  v31 = 49151;
  v49 = v391[0] & 0xBFFF;
  if ( v49 == 8 || (v391[0] & 0xBFFFu) > 0x7F && ((v391[0] & 0xBFFFu) <= 0x82 || v49 == 132 || v49 == 141) )
  {
    v50 = v387;
    ConversionSize = CDataConvert::GetConversionSize(
                       v391[0],
                       v387,
                       (unsigned __int64 *)ui,
                       v383,
                       pvarVal,
                       0,
                       v29,
                       a14,
                       CodePage);
    if ( v50 == 129 )
    {
      if ( *v383 )
        --*v383;
    }
    else if ( v50 == 130 && *v383 >= 2 )
    {
      *v383 -= 2LL;
    }
    goto LABEL_56;
  }
  v27 = v553;
  Source = v553;
  Size = 110;
  LOWORD(v26) = v387;
LABEL_23:
  if ( !pvarVal )
  {
LABEL_1690:
    if ( !a9 )
      *v380 = 8;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_1696;
    v351 = off_383B43280[0];
    if ( !off_383B49128[0] )
      goto LABEL_1696;
    LODWORD(lpMultiByteStr) = 1227;
    v352 = 1256489;
    goto LABEL_1695;
  }
  v514 = *(_QWORD *)&v540.val[8];
  v498 = *(_QWORD *)v540.val;
LABEL_25:
  v32 = *(_QWORD *)ui;
  v33 = 0x2000;
  *(_QWORD *)v401 = *(_QWORD *)ui;
  while ( (vt & 0x2000) != 0 || (v26 & 0x2000) != 0 )
  {
    if ( (vt & 0x4000) == 0 )
    {
      if ( (_WORD)vt == 12 )
      {
        vt = pvarVal->vt;
        *(_DWORD *)v391 = vt;
        pvarVal = (VARIANTARG *)((char *)pvarVal + 8);
        pvargSrc = pvarVal;
        v396 = pvarVal;
        goto LABEL_1541;
      }
      if ( (_WORD)vt != 9 )
      {
        valid = DataConvertForSafeArrays(vt, v26, pvarVal, v27, a9, v380, v383);
LABEL_1689:
        ConversionSize = valid;
        goto LABEL_56;
      }
      v531[0] = 0;
      v531[1] = 0;
      v532 = 0;
      v533 = 0;
      if ( v431.vt )
      {
        if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
          goto LABEL_108;
        LODWORD(lpMultiByteStr) = 1270;
        bidTraceW(off_383B43280[0], 1300521, off_383B49128[0], 2147749405LL);
        ConversionSize = -2147217891;
        goto LABEL_56;
      }
      HIDWORD(p_wMilliseconds) = 0;
      lpUsedDefaultChar = 0;
      lpDefaultChar = &v431;
      LOWORD(lpMultiByteStr) = 2;
      ConversionSize = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64, _DWORD, _QWORD *))(**(_QWORD **)&pvarVal->vt + 48LL))(
                         *(_QWORD *)&pvarVal->vt,
                         0,
                         &GUID_NULL,
                         1033,
                         (_DWORD)lpMultiByteStr,
                         v531);
      v378 = ConversionSize;
      if ( ConversionSize < 0 )
        goto LABEL_56;
LABEL_1306:
      vt = 12;
      *(_DWORD *)v391 = 12;
      pvarVal = &v431;
      pvargSrc = &v431;
      v396 = &v431;
      LOWORD(v26) = v387;
      v31 = 49151;
      goto LABEL_25;
    }
    if ( (vt & 0x2000) != 0 )
    {
      if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
        goto LABEL_108;
      LODWORD(lpMultiByteStr) = 1248;
      bidTraceW(off_383B43280[0], 1277993, off_383B49128[0], 2147749405LL);
      ConversionSize = -2147217891;
      goto LABEL_56;
    }
    LOWORD(vt) = vt & 0xBFFF;
    *(_DWORD *)v391 = vt;
    pvarVal = *(VARIANTARG **)&pvarVal->vt;
    pvargSrc = pvarVal;
    v396 = pvarVal;
LABEL_1541:
    if ( !pvarVal )
      goto LABEL_1690;
    v27 = Source;
  }
  if ( (_WORD)vt == 8 )
  {
    if ( *(_QWORD *)&pvarVal->vt )
      goto LABEL_35;
    vt = 130;
    *(_DWORD *)v391 = 130;
    v32 = 0;
    *(_QWORD *)v401 = 0;
    *(_QWORD *)ui = 0;
    pvargSrc = (VARIANTARG *)&::WideCharStr;
    v396 = (void *)&::WideCharStr;
  }
  else
  {
    if ( (_WORD)vt == 144 )
    {
      if ( (_WORD)v26 == 144 )
        goto LABEL_35;
      vt = FixUpSourceData(&v396, (unsigned __int64 *)ui, &a16, v384);
      *(_DWORD *)v391 = vt;
      v32 = *(_QWORD *)ui;
      *(_QWORD *)v401 = *(_QWORD *)ui;
      pvargSrc = (VARIANTARG *)v396;
      v381 = v384[0];
      LOWORD(v26) = v387;
    }
    if ( (_WORD)vt == 129 )
    {
      if ( (unsigned __int16)v26 <= 1u
        || (unsigned __int16)v26 > 0x80u && ((unsigned __int16)v26 <= 0x82u || (unsigned __int16)v26 == 141) )
      {
        goto LABEL_35;
      }
      if ( v32 + 1 <= 0x6F )
        goto LABEL_34;
      v51 = (const OLECHAR *)((__int64 (__fastcall *)(struct IMalloc *, unsigned __int64, __int64, unsigned __int64, _DWORD, size_t))g_pMO->lpVtbl->Alloc)(
                               g_pMO,
                               2 * v32 + 2,
                               v31,
                               v33,
                               (_DWORD)lpMultiByteStr,
                               cbMultiByte);
LABEL_147:
      lpsz = v51;
      v34 = 1;
      v408 = 1;
      v32 = *(_QWORD *)ui;
      *(_QWORD *)v401 = *(_QWORD *)ui;
      vt = *(_DWORD *)v391;
      goto LABEL_36;
    }
    if ( (_WORD)vt != 130 && (_WORD)vt != 141 )
      goto LABEL_35;
  }
  if ( (unsigned __int16)v26 <= 1u || (unsigned __int16)v26 == 12 )
    goto LABEL_35;
  if ( (v32 >> 1) + 1 > 0x6F )
  {
    p_Alloc = &g_pMO->lpVtbl->Alloc;
    v53 = SizeTAddRtlAsserted(v32, 2u);
    v51 = (const OLECHAR *)((__int64 (__fastcall *)(struct IMalloc *, unsigned __int64))*p_Alloc)(g_pMO, v53);
    goto LABEL_147;
  }
LABEL_34:
  lpsz = strIn;
LABEL_35:
  v34 = 1;
LABEL_36:
  v35 = (unsigned __int16)vt;
  v422 = (unsigned __int16)vt;
  if ( (unsigned __int16)vt < 2u || (unsigned __int16)vt > 3u && (unsigned int)(unsigned __int16)vt - 16 > 5 )
  {
    LOWORD(v26) = v387;
    goto LABEL_40;
  }
  LOWORD(v26) = v387;
  v33 = (unsigned __int16)v387;
  v395 = (unsigned __int16)v387;
  if ( (unsigned __int16)v387 != 12
    && (unsigned __int16)v387 != 14
    && (unsigned __int16)v387 != 64
    && (unsigned __int16)v387 != 131
    && (unsigned __int16)v387 != 144 )
  {
    v54 = 0;
    v55 = 0;
    if ( !v385 && (_WORD)v387 != 8 )
    {
      v56 = (const OLECHAR *)Source;
LABEL_187:
      v57 = 0x383800000uLL;
      switch ( (__int16)vt )
      {
        case 2:
          if ( (unsigned __int16)v387 > 0x92u )
            v62 = 0;
          else
            v62 = NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v387];
          v63 = ConversionMappingPolicy<2,short,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                  (_DWORD)pvargSrc,
                  v32,
                  v62,
                  (_DWORD)v56,
                  Size,
                  (__int64)v383);
          v378 = v63;
          if ( v63 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              bidTraceHR(off_383B43280[0], 1623049, (unsigned int)v63);
              ConversionSize = v378;
              goto LABEL_56;
            }
            goto LABEL_1549;
          }
          LOWORD(v26) = v387;
          LODWORD(v33) = v395;
          break;
        case 3:
          if ( (unsigned __int16)v387 > 0x92u )
            v66 = 0;
          else
            v66 = NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v387];
          v67 = ConversionMappingPolicy<2,int,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                  (_DWORD)pvargSrc,
                  v32,
                  v66,
                  (_DWORD)v56,
                  Size,
                  (__int64)v383);
          v378 = v67;
          if ( v67 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              bidTraceHR(off_383B43280[0], 1639433, (unsigned int)v67);
              ConversionSize = v378;
              goto LABEL_56;
            }
            goto LABEL_1549;
          }
          LOWORD(v26) = v387;
          LODWORD(v33) = v395;
          break;
        case 14:
        case 131:
          if ( v378 >= 0 )
            break;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_1549;
          bidTraceHR(off_383B43280[0], 1673225, (unsigned int)v378);
          ConversionSize = v378;
          goto LABEL_56;
        case 16:
          if ( (unsigned __int16)v387 > 0x92u )
            v58 = 0;
          else
            v58 = NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v387];
          v59 = ConversionMappingPolicy<2,char,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                  (_DWORD)pvargSrc,
                  v32,
                  v58,
                  (_DWORD)v56,
                  Size,
                  (__int64)v383);
          v378 = v59;
          if ( v59 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
              bidTraceHR(off_383B43280[0], 1606665, (unsigned int)v59);
            goto LABEL_1549;
          }
          LOWORD(v26) = v387;
          LODWORD(v33) = v395;
          break;
        case 17:
          if ( (unsigned __int16)v387 > 0x92u )
            v60 = 0;
          else
            v60 = NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v387];
          v61 = ConversionMappingPolicy<2,unsigned char,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                  (_DWORD)pvargSrc,
                  v32,
                  v60,
                  (_DWORD)v56,
                  Size,
                  (__int64)v383);
          v378 = v61;
          if ( v61 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              bidTraceHR(off_383B43280[0], 1614857, (unsigned int)v61);
              ConversionSize = v378;
              goto LABEL_56;
            }
            goto LABEL_1549;
          }
          LOWORD(v26) = v387;
          LODWORD(v33) = v395;
          break;
        case 18:
          if ( (unsigned __int16)v387 > 0x92u )
            v64 = 0;
          else
            v64 = NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v387];
          v65 = ConversionMappingPolicy<2,unsigned short,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                  (_DWORD)pvargSrc,
                  v32,
                  v64,
                  (_DWORD)v56,
                  Size,
                  (__int64)v383);
          v378 = v65;
          if ( v65 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              bidTraceHR(off_383B43280[0], 1631241, (unsigned int)v65);
              ConversionSize = v378;
              goto LABEL_56;
            }
            goto LABEL_1549;
          }
          LOWORD(v26) = v387;
          LODWORD(v33) = v395;
          break;
        case 19:
          if ( (unsigned __int16)v387 > 0x92u )
            v68 = 0;
          else
            v68 = NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v387];
          v69 = ConversionMappingPolicy<2,unsigned int,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                  (_DWORD)pvargSrc,
                  v32,
                  v68,
                  (_DWORD)v56,
                  Size,
                  (__int64)v383);
          v378 = v69;
          if ( v69 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              bidTraceHR(off_383B43280[0], 1647625, (unsigned int)v69);
              ConversionSize = v378;
              goto LABEL_56;
            }
            goto LABEL_1549;
          }
          LOWORD(v26) = v387;
          LODWORD(v33) = v395;
          break;
        case 20:
          if ( (unsigned __int16)v387 > 0x92u )
            v70 = 0;
          else
            v70 = NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v387];
          v71 = ConversionMappingPolicy<2,__int64,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                  (_DWORD)pvargSrc,
                  v32,
                  v70,
                  (_DWORD)v56,
                  Size,
                  (__int64)v383);
          v378 = v71;
          if ( v71 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              bidTraceHR(off_383B43280[0], 1655817, (unsigned int)v71);
              ConversionSize = v378;
              goto LABEL_56;
            }
            goto LABEL_1549;
          }
          LOWORD(v26) = v387;
          LODWORD(v33) = v395;
          break;
        case 21:
          if ( (unsigned __int16)v387 > 0x92u )
            v72 = 0;
          else
            v72 = NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v387];
          v73 = ConversionMappingPolicy<2,unsigned __int64,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                  (_DWORD)pvargSrc,
                  v32,
                  v72,
                  (_DWORD)v56,
                  Size,
                  (__int64)v383);
          v378 = v73;
          if ( v73 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              bidTraceHR(off_383B43280[0], 1664009, (unsigned int)v73);
              ConversionSize = v378;
              goto LABEL_56;
            }
LABEL_1549:
            ConversionSize = v378;
            goto LABEL_56;
          }
          LOWORD(v26) = v387;
          LODWORD(v33) = v395;
          break;
        default:
          break;
      }
      if ( !v385 && (_WORD)v26 != 8 )
      {
        ConversionSize = v378;
LABEL_1178:
        v38 = (CY *)pvargSrc;
        goto LABEL_1179;
      }
      if ( (_DWORD)v33 == 8 )
      {
        v78 = -2;
        if ( *v383 >> 1 < 0xFFFFFFFF )
          v78 = *v383 >> 1;
        *(_QWORD *)v55 = SysAllocStringLen(v56, v78);
        *v383 = 8;
LABEL_245:
        ConversionSize = v378;
        v27 = Source;
        goto LABEL_1526;
      }
      if ( (unsigned int)(v33 - 129) > 1 )
      {
        v77 = (void *)((__int64 (__fastcall *)(LPMALLOC, unsigned __int64, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                        g_pIMalloc,
                        *v383,
                        v57);
        *(_QWORD *)v55 = v77;
        if ( !v77 )
        {
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          {
            LODWORD(lpMultiByteStr) = 1725;
            bidTraceW(off_383B43280[0], 1766441, off_383B49128[0], 2147942414LL);
            ConversionSize = -2147024882;
            goto LABEL_56;
          }
          goto LABEL_1569;
        }
        v27 = Source;
        memcpy_s(v77, *v383, Source, *v383);
        ConversionSize = v378;
        goto LABEL_1526;
      }
      v74 = *v383 + 1;
      if ( (_WORD)v26 == 130 )
        v74 = *v383 + 2;
      v75 = (wchar_t *)((__int64 (__fastcall *)(LPMALLOC, rsize_t, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                         g_pIMalloc,
                         v74,
                         v57);
      *(_QWORD *)v55 = v75;
      if ( !v75 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        {
          LODWORD(lpMultiByteStr) = 1668;
          bidTraceW(off_383B43280[0], 1708073, off_383B49128[0], 2147942414LL);
        }
        goto LABEL_1569;
      }
      v76 = *v383;
      v27 = Source;
      if ( (_WORD)v387 != 129 )
      {
        wcsncpy_s(v75, v74 >> 1, (const wchar_t *)Source, v76 >> 1);
        ConversionSize = v378;
        goto LABEL_1526;
      }
      strncpy_s((char *)v75, v74, Source, v76);
      goto LABEL_238;
    }
    if ( (unsigned __int16)v387 == 8 )
      goto LABEL_171;
    if ( (unsigned __int16)v387 == 128 )
    {
      switch ( (__int16)vt )
      {
        case 2:
        case 18:
          Size = 2;
          break;
        case 3:
        case 19:
          Size = 4;
          break;
        case 16:
        case 17:
          Size = 1;
          break;
        case 20:
        case 21:
          Size = 8;
          break;
        default:
          goto LABEL_182;
      }
      goto LABEL_182;
    }
    if ( (unsigned __int16)v387 > 0x80u && (unsigned __int16)v387 <= 0x82u )
    {
LABEL_171:
      switch ( (__int16)vt )
      {
        case 2:
          v54 = 7;
          break;
        case 3:
          v54 = 12;
          break;
        case 16:
          v54 = 5;
          break;
        case 17:
          v54 = 4;
          break;
        case 18:
          v54 = 6;
          break;
        case 19:
          v54 = 11;
          break;
        case 20:
        case 21:
          v54 = 21;
          break;
        default:
          break;
      }
      if ( (_WORD)v387 == 129 )
        Size = v54;
      else
        Size = 2 * v54;
    }
LABEL_182:
    v55 = Source;
    if ( (_WORD)v387 == 129 || (_WORD)v387 == 128 )
    {
      v56 = (const OLECHAR *)v554;
      Source = v554;
    }
    else
    {
      v56 = strIn;
      Source = (char *)strIn;
    }
    goto LABEL_187;
  }
LABEL_40:
  v395 = (unsigned __int16)v26;
  v36 = (unsigned __int16)v26 + 147 * (unsigned __int16)vt;
  if ( v36 <= 291 )
  {
    if ( v36 != 291 )
    {
      switch ( v36 )
      {
        case 0:
        case 1:
        case 148:
          goto LABEL_248;
        case 2:
        case 11:
        case 18:
          *v383 = 2;
          *(_WORD *)v27 = 0;
          ConversionSize = v378;
          goto LABEL_1526;
        case 3:
        case 4:
        case 19:
          *v383 = 4;
          *(_DWORD *)v27 = 0;
          ConversionSize = v378;
          goto LABEL_1526;
        case 5:
        case 7:
        case 20:
        case 21:
          *v383 = 8;
          *(_QWORD *)v27 = 0;
          ConversionSize = v378;
          goto LABEL_1526;
        case 6:
          *v383 = 8;
          *(_DWORD *)v27 = 0;
          *((_DWORD *)v27 + 1) = 0;
          ConversionSize = v378;
          goto LABEL_1526;
        case 8:
        case 130:
        case 141:
          ConversionSize = FixupFromWstr(&::WideCharStr, 0, v26, 0xFFFFFFFF, v27, v383, Size, v380, v385);
          goto LABEL_1526;
        case 12:
        case 159:
          goto LABEL_468;
        case 14:
          *v383 = 16;
          *((_QWORD *)v27 + 1) = 0;
          *((_DWORD *)v27 + 1) = 0;
          *((_WORD *)v27 + 1) = 0;
          ConversionSize = v378;
          goto LABEL_1526;
        case 16:
        case 17:
          *v383 = 1;
          *v27 = 0;
          ConversionSize = v378;
          goto LABEL_1526;
        case 72:
          *v383 = 16;
          *(_QWORD *)v27 = 0;
          *((_QWORD *)v27 + 1) = 0;
          ConversionSize = v378;
          goto LABEL_1526;
        case 129:
          ConversionSize = CopyToStr((void *)&byte_38387C772, v27, 0, v383, Size, v380, v385);
          goto LABEL_1526;
        case 131:
          *v383 = 19;
          *(_QWORD *)v27 = 0;
          *((_QWORD *)v27 + 1) = 0;
          *((_WORD *)v27 + 8) = 0;
          v27[18] = 0;
          *v27 = 1;
          ConversionSize = v378;
          goto LABEL_1526;
        case 135:
          memset(&pvarSrc, 0, sizeof(pvarSrc));
          memset(&pvargDest, 0, sizeof(pvargDest));
          ConversionSize = VariantChangeType(&pvargDest, &pvarSrc, 0, 7u);
          if ( ConversionSize < 0 )
            goto LABEL_1178;
          ConversionSize = CDataSource::DataConvert(
                             v406,
                             0xCu,
                             v387,
                             0x18u,
                             v383,
                             &pvargDest,
                             v27,
                             Size,
                             a9,
                             v380,
                             a11,
                             v381,
                             0,
                             a14,
                             CodePage,
                             a16);
          break;
        default:
          goto LABEL_1516;
      }
      goto LABEL_1526;
    }
    goto LABEL_1448;
  }
  if ( v36 > 2483 )
  {
    if ( v36 <= 19091 )
    {
      if ( v36 != 19091 )
      {
        if ( v36 > 9409 )
        {
          if ( v36 > 10585 )
          {
            if ( v36 > 18817 )
            {
              v33 = 0x383800000uLL;
              switch ( v36 )
              {
                case 18819:
                case 18835:
                  *v383 = 4;
                  v41 = v380;
                  ConversionSize = v378;
                  v38 = (CY *)pvargSrc;
                  if ( *(_QWORD *)ui >= 4u )
                    *(_DWORD *)v27 = *(_DWORD *)&pvargSrc->vt;
                  else
                    *v380 = 2;
                  goto LABEL_55;
                case 18824:
                case 18945:
                case 18946:
                  goto LABEL_972;
                case 18828:
                  goto LABEL_1291;
                case 18836:
                case 18837:
                  *v383 = 8;
                  v41 = v380;
                  ConversionSize = v378;
                  v38 = (CY *)pvargSrc;
                  if ( *(_QWORD *)ui >= 8u )
                    *(_QWORD *)v27 = *(_QWORD *)&pvargSrc->vt;
                  else
                    *v380 = 2;
                  goto LABEL_55;
                case 18888:
                  *v383 = 16;
                  v41 = v380;
                  ConversionSize = v378;
                  v38 = (CY *)pvargSrc;
                  if ( *(_QWORD *)ui >= 0x10u )
                  {
                    *(_QWORD *)v27 = *(_QWORD *)&pvargSrc->vt;
                    *((_QWORD *)v27 + 1) = pvargSrc->llVal;
                  }
                  else
                  {
                    *v380 = 2;
                  }
                  goto LABEL_55;
                case 18944:
                case 18948:
                case 18957:
                  goto LABEL_1192;
                case 18960:
                  goto LABEL_1448;
                case 18963:
                case 18964:
                  goto LABEL_248;
                case 18965:
                  goto LABEL_615;
                case 18966:
                  goto LABEL_621;
                case 18967:
                  goto LABEL_627;
                case 18968:
                  goto LABEL_631;
                case 18969:
                  goto LABEL_635;
                case 18970:
                  goto LABEL_648;
                case 18971:
                  goto LABEL_48;
                case 18974:
                  goto LABEL_619;
                case 18975:
                  goto LABEL_1110;
                case 18977:
                  goto LABEL_639;
                case 18979:
                  goto LABEL_607;
                case 18980:
                  goto LABEL_609;
                case 18981:
                  goto LABEL_617;
                case 18982:
                  goto LABEL_623;
                case 18983:
                case 18984:
                  goto LABEL_625;
                case 19027:
                  goto LABEL_783;
                case 19035:
                  goto LABEL_902;
                default:
                  goto LABEL_1516;
              }
            }
            if ( v36 < 18816 )
            {
              v33 = 0x383800000uLL;
              switch ( v36 )
              {
                case 10592:
                case 10713:
                case 10714:
                  v38 = (CY *)pvargSrc;
                  cchWideChar = (unsigned __int16 *)StringFromGUID2((const GUID *const)pvargSrc, sz, 260);
                  v80 = FixupFromWstr(
                          sz,
                          (unsigned __int16 *)((char *)cchWideChar - 1),
                          v387,
                          CodePage,
                          v27,
                          v383,
                          Size,
                          v380,
                          v385);
                  goto LABEL_277;
                case 10596:
                  *v383 = 24;
                  v38 = (CY *)pvargSrc;
                  v115 = StringFromGUID2((const GUID *const)pvargSrc, sz, 260);
                  cchWideChar = (unsigned __int16 *)v115;
                  *(_WORD *)v27 = 8;
                  v116 = SysAllocStringLen(sz, v115 - 1);
                  *((_QWORD *)v27 + 1) = v116;
                  if ( !v116 )
                  {
                    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                    {
                      LODWORD(lpMultiByteStr) = 5216;
                      bidTraceW(off_383B43280[0], 5341225, off_383B49128[0], 2147942414LL);
                      ConversionSize = -2147024882;
                      goto LABEL_56;
                    }
                    goto LABEL_1569;
                  }
                  ConversionSize = v378;
                  goto LABEL_54;
                case 10656:
                  *v383 = 16;
                  goto LABEL_583;
                case 10712:
                  *v383 = 16;
                  if ( v385 )
                  {
                    Size = 16;
                    v117 = (char *)((__int64 (__fastcall *)(LPMALLOC, __int64, _QWORD, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                                     g_pIMalloc,
                                     16,
                                     (unsigned __int16)vt,
                                     0x383800000uLL);
                    *(_QWORD *)v27 = v117;
                    if ( !v117 )
                    {
                      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                      {
                        LODWORD(lpMultiByteStr) = 5234;
                        bidTraceW(off_383B43280[0], 5359657, off_383B49128[0], 2147942414LL);
                        ConversionSize = -2147024882;
                        goto LABEL_56;
                      }
                      goto LABEL_1569;
                    }
                    v27 = v117;
                    Source = v117;
                  }
                  else if ( Size < 0x10 )
                  {
                    v41 = v380;
                    *v380 = 6;
                    ConversionSize = v378;
                    v38 = (CY *)pvargSrc;
                    goto LABEL_55;
                  }
LABEL_583:
                  v38 = (CY *)pvargSrc;
LABEL_584:
                  *(_DWORD *)v27 = v38->Lo;
                  *((_DWORD *)v27 + 1) = v38->Hi;
                  *((_DWORD *)v27 + 2) = v38[1].Lo;
                  Hi = v38[1].Hi;
LABEL_585:
                  *((_DWORD *)v27 + 3) = Hi;
LABEL_586:
                  ConversionSize = v378;
                  break;
                case 10728:
                  goto LABEL_1448;
                default:
                  goto LABEL_1516;
              }
              goto LABEL_54;
            }
            goto LABEL_248;
          }
          if ( v36 < 10584 )
          {
            switch ( v36 )
            {
              case 9415:
              case 9420:
                goto LABEL_1293;
              case 9416:
              case 9538:
                *(_QWORD *)&SystemTime.wYear = 0;
                *(_QWORD *)&SystemTime.wHour = 0;
                v38 = (CY *)pvargSrc;
                if ( !FileTimeToSystemTime((const FILETIME *)pvargSrc, &SystemTime) )
                  goto LABEL_1632;
                if ( SystemTime.wMilliseconds )
                {
                  LODWORD(v369) = SystemTime.wMilliseconds;
                  LODWORD(p_wMilliseconds) = SystemTime.wSecond;
                  LODWORD(lpUsedDefaultChar) = SystemTime.wMinute;
                  LODWORD(lpDefaultChar) = SystemTime.wHour;
                  LODWORD(cbMultiByte) = SystemTime.wDay;
                  LODWORD(lpMultiByteStr) = SystemTime.wMonth;
                  v112 = StringCchPrintfW(
                           sz,
                           0x104u,
                           L"%05hi-%02hu-%02hu %02hu:%02hu:%02hu.%03u",
                           SystemTime.wYear,
                           lpMultiByteStr,
                           cbMultiByte,
                           lpDefaultChar,
                           lpUsedDefaultChar,
                           p_wMilliseconds,
                           v369);
                }
                else
                {
                  LODWORD(p_wMilliseconds) = SystemTime.wSecond;
                  LODWORD(lpUsedDefaultChar) = SystemTime.wMinute;
                  LODWORD(lpDefaultChar) = SystemTime.wHour;
                  LODWORD(cbMultiByte) = SystemTime.wDay;
                  LODWORD(lpMultiByteStr) = SystemTime.wMonth;
                  v112 = StringCchPrintfW(
                           sz,
                           0x104u,
                           L"%05hi-%02hu-%02hu %02hu:%02hu:%02hu",
                           SystemTime.wYear,
                           lpMultiByteStr,
                           cbMultiByte,
                           lpDefaultChar,
                           lpUsedDefaultChar,
                           p_wMilliseconds);
                }
                v378 = v112;
                if ( v112 < 0 )
                  goto LABEL_1633;
                v113 = -1;
                do
                  ++v113;
                while ( sz[v113] );
                cchWideChar = (unsigned __int16 *)v113;
                v80 = FixupFromWstr(sz, (unsigned __int16 *)v113, v387, CodePage, v27, v383, Size, v380, v385);
                goto LABEL_277;
              case 9428:
              case 9429:
                *v383 = 8;
                v38 = (CY *)pvargSrc;
                v95 = *(_QWORD *)&pvargSrc->vt;
                if ( (_WORD)v26 != 21 || v95 >= 0 )
                  goto LABEL_398;
                v41 = v380;
                *v380 = 5;
                ConversionSize = v378;
                goto LABEL_55;
              case 9472:
                goto LABEL_546;
              case 9537:
                *(_QWORD *)&SystemTime.wYear = 0;
                *(_QWORD *)&SystemTime.wHour = 0;
                v38 = (CY *)pvargSrc;
                if ( !FileTimeToSystemTime((const FILETIME *)pvargSrc, &SystemTime) )
                  goto LABEL_1632;
                if ( SystemTime.wMilliseconds )
                  v110 = StringCchPrintfA(
                           (char *)sz,
                           0x104u,
                           "%05hi-%02hu-%02hu %02hu:%02hu:%02hu.%03u",
                           SystemTime.wYear,
                           SystemTime.wMonth,
                           SystemTime.wDay,
                           SystemTime.wHour,
                           SystemTime.wMinute,
                           SystemTime.wSecond,
                           SystemTime.wMilliseconds);
                else
                  v110 = StringCchPrintfA(
                           (char *)sz,
                           0x104u,
                           "%05hi-%02hu-%02hu %02hu:%02hu:%02hu",
                           SystemTime.wYear,
                           SystemTime.wMonth,
                           SystemTime.wDay,
                           SystemTime.wHour,
                           SystemTime.wMinute,
                           SystemTime.wSecond);
                v378 = v110;
                if ( v110 < 0 )
                  goto LABEL_1633;
                v111 = -1;
                do
                  ++v111;
                while ( *((_BYTE *)sz + v111) );
                goto LABEL_1048;
              case 9541:
                *v383 = 6;
                *(_QWORD *)&SystemTime.wYear = 0;
                *(_QWORD *)&SystemTime.wHour = 0;
                if ( !FileTimeToSystemTime((const FILETIME *)pvargSrc, &SystemTime) )
                  goto LABEL_1632;
                wYear = SystemTime.wYear;
                if ( !(unsigned int)IsValidDateValue(SystemTime.wYear, SystemTime.wMonth, SystemTime.wDay) )
                  goto LABEL_1632;
                *(_WORD *)v27 = wYear;
                *((_WORD *)v27 + 1) = SystemTime.wMonth;
                *((_WORD *)v27 + 2) = SystemTime.wDay;
                ConversionSize = v378;
                goto LABEL_1526;
              case 9542:
                *v383 = 6;
                *(_QWORD *)&SystemTime.wYear = 0;
                *(_QWORD *)&SystemTime.wHour = 0;
                v38 = (CY *)pvargSrc;
                ConversionSize = v378;
                if ( !FileTimeToSystemTime((const FILETIME *)pvargSrc, &SystemTime) )
                  goto LABEL_1586;
                *(_WORD *)v27 = SystemTime.wHour;
                *((_WORD *)v27 + 1) = SystemTime.wMinute;
                *((_WORD *)v27 + 2) = SystemTime.wSecond;
                goto LABEL_54;
              case 9543:
                *v383 = 16;
                *(_QWORD *)&SystemTime.wYear = 0;
                *(_QWORD *)&SystemTime.wHour = 0;
                if ( !FileTimeToSystemTime((const FILETIME *)pvargSrc, &SystemTime) )
                  goto LABEL_1632;
                v104 = SystemTime.wYear;
                if ( !(unsigned int)IsValidDateValue(SystemTime.wYear, SystemTime.wMonth, SystemTime.wDay) )
                  goto LABEL_1632;
                *(_WORD *)v27 = v104;
                *((_WORD *)v27 + 1) = SystemTime.wMonth;
                *((_WORD *)v27 + 2) = SystemTime.wDay;
                *((_WORD *)v27 + 3) = SystemTime.wHour;
                *((_WORD *)v27 + 4) = SystemTime.wMinute;
                *((_WORD *)v27 + 5) = SystemTime.wSecond;
                *((_DWORD *)v27 + 3) = 1000000 * SystemTime.wMilliseconds;
                ConversionSize = v378;
                goto LABEL_1526;
              case 9553:
                *v383 = 12;
                *(_QWORD *)&SystemTime.wYear = 0;
                *(_QWORD *)&SystemTime.wHour = 0;
                v38 = (CY *)pvargSrc;
                ConversionSize = v378;
                if ( !FileTimeToSystemTime((const FILETIME *)pvargSrc, &SystemTime) )
                  goto LABEL_1586;
                *(_WORD *)v27 = SystemTime.wHour;
                *((_WORD *)v27 + 1) = SystemTime.wMinute;
                *((_WORD *)v27 + 2) = SystemTime.wSecond;
                *((_DWORD *)v27 + 2) = 1000000 * SystemTime.wMilliseconds;
                *((_WORD *)v27 + 3) = 0;
                goto LABEL_54;
              case 9554:
                *v383 = 20;
                *(_QWORD *)&SystemTime.wYear = 0;
                *(_QWORD *)&SystemTime.wHour = 0;
                if ( !FileTimeToSystemTime((const FILETIME *)pvargSrc, &SystemTime) )
                  goto LABEL_1632;
                wDay = SystemTime.wDay;
                wMonth = SystemTime.wMonth;
                v107 = SystemTime.wYear;
                if ( !(unsigned int)IsValidSqlDateValue(SystemTime.wYear, SystemTime.wMonth, SystemTime.wDay) )
                  goto LABEL_1632;
                v108 = TimeZoneOffsetFromTimeStamp(
                         v107,
                         wMonth,
                         wDay,
                         SystemTime.wHour,
                         SystemTime.wMinute,
                         SystemTime.wSecond,
                         1000000 * (unsigned int)SystemTime.wMilliseconds,
                         v407,
                         &v419);
                ConversionSize = v378;
                if ( !v108 )
                  goto LABEL_103;
                v27 = Source;
                *(_WORD *)Source = SystemTime.wYear;
                *((_WORD *)v27 + 1) = SystemTime.wMonth;
                *((_WORD *)v27 + 2) = SystemTime.wDay;
                *((_WORD *)v27 + 3) = SystemTime.wHour;
                *((_WORD *)v27 + 4) = SystemTime.wMinute;
                *((_WORD *)v27 + 5) = SystemTime.wSecond;
                *((_DWORD *)v27 + 3) = 1000000 * SystemTime.wMilliseconds;
                *((_WORD *)v27 + 8) = v407[0];
                *((_WORD *)v27 + 9) = v419;
                goto LABEL_1526;
              default:
                goto LABEL_1516;
            }
          }
LABEL_399:
          *v383 = 0;
          ConversionSize = v378;
          goto LABEL_1526;
        }
        if ( v36 >= 9408 )
          goto LABEL_399;
        if ( v36 <= 2630 )
        {
          if ( v36 != 2630 )
          {
            if ( v36 != 2496 )
            {
              if ( v36 > 2498 )
              {
                if ( v36 <= 2500 )
                  goto LABEL_399;
                if ( v36 != 2511 )
                {
                  if ( v36 == 2513 )
                  {
                    *v383 = 16;
                    v38 = (CY *)pvargSrc;
                    v79 = VarDecFromUI1(pvargSrc->vt, (DECIMAL *)v27);
                    goto LABEL_275;
                  }
                  goto LABEL_1516;
                }
                goto LABEL_1291;
              }
              goto LABEL_1516;
            }
            goto LABEL_1448;
          }
          goto LABEL_498;
        }
        if ( v36 > 2777 )
        {
          if ( v36 > 3071 )
          {
            v33 = 0x383800000uLL;
            switch ( v36 )
            {
              case 3084:
                goto LABEL_1448;
              case 3087:
              case 3088:
                goto LABEL_248;
              case 3099:
                *v383 = 24;
                VariantInit((VARIANTARG *)v27);
                *(_WORD *)v27 = 14;
                v27[3] = 0;
                v27[2] = 0;
                *((_DWORD *)v27 + 1) = 0;
                v38 = (CY *)pvargSrc;
                *((_QWORD *)v27 + 1) = *(_QWORD *)&pvargSrc->vt;
                ConversionSize = v378;
                goto LABEL_54;
              case 3101:
                *v383 = 16;
                v27[2] = 0;
                v27[3] = 0;
                *((_DWORD *)v27 + 1) = 0;
                v38 = (CY *)pvargSrc;
                goto LABEL_528;
              case 3151:
LABEL_531:
                *v383 = 8;
                v38 = (CY *)pvargSrc;
                *(_QWORD *)v27 = *(_QWORD *)&pvargSrc->vt;
                ConversionSize = v378;
                if ( FileTimeToSystemTime((const FILETIME *)v27, &SystemTime) )
                  goto LABEL_54;
                goto LABEL_1586;
              case 3218:
                goto LABEL_537;
              default:
                goto LABEL_1516;
            }
          }
          if ( v36 != 3071 )
          {
            v33 = 0x383800000uLL;
            switch ( v36 )
            {
              case 2790:
              case 2937:
                goto LABEL_1448;
              case 2793:
              case 2794:
              case 2940:
              case 2941:
                goto LABEL_248;
              case 2805:
                goto LABEL_1291;
              case 2807:
                *v383 = 16;
                v38 = (CY *)pvargSrc;
                v79 = VarDecFromUI4(*(_DWORD *)&pvargSrc->vt, (DECIMAL *)v27);
                goto LABEL_275;
              case 2924:
                goto LABEL_519;
              case 2952:
                *v383 = 24;
                VariantInit((VARIANTARG *)v27);
                *(_WORD *)v27 = 14;
                v27[2] = 0;
                *((_DWORD *)v27 + 1) = 0;
                v38 = (CY *)pvargSrc;
                ConversionSize = v378;
                v41 = v380;
                if ( *(__int64 *)&pvargSrc->vt >= 0 )
                {
                  v27[3] = 0;
                  *((_QWORD *)v27 + 1) = *(_QWORD *)&pvargSrc->vt;
                }
                else
                {
                  v27[3] = 0x80;
                  *((_QWORD *)v27 + 1) = -*(_QWORD *)&pvargSrc->vt;
                }
                goto LABEL_55;
              case 2954:
                *v383 = 16;
                v27[2] = 0;
                *((_DWORD *)v27 + 1) = 0;
                v38 = (CY *)pvargSrc;
                if ( *(__int64 *)&pvargSrc->vt < 0 )
                {
                  v27[3] = 0x80;
                  int64 = -*(_QWORD *)&pvargSrc->vt;
                  goto LABEL_529;
                }
                v27[3] = 0;
                break;
              case 3004:
                goto LABEL_531;
              default:
                goto LABEL_1516;
            }
LABEL_528:
            int64 = v38->int64;
LABEL_529:
            *((_QWORD *)v27 + 1) = int64;
            if ( (a16 & 8) != 0 )
              goto LABEL_276;
LABEL_1173:
            ConversionSize = v378;
            goto LABEL_1179;
          }
LABEL_537:
          *v383 = 19;
          *(_QWORD *)v27 = 0;
          *((_QWORD *)v27 + 1) = 0;
          *((_WORD *)v27 + 8) = 0;
          v27[18] = 0;
          v38 = (CY *)pvargSrc;
          if ( (_WORD)vt == 21 || *(__int64 *)&pvargSrc->vt >= 0 )
          {
            v27[2] = 1;
            v92 = *(_QWORD *)&pvargSrc->vt;
          }
          else
          {
            v92 = -*(_QWORD *)&pvargSrc->vt;
          }
          v34 = 8;
LABEL_384:
          *(_QWORD *)(v27 + 3) = v92;
LABEL_385:
          ConversionSize = FindPrecision((struct tagDB_NUMERIC *)v27, v34);
          if ( ConversionSize < 0 )
            goto LABEL_56;
LABEL_386:
          v80 = ScaleNumeric((struct tagDB_NUMERIC *)v27, a11, v381, 0);
          goto LABEL_277;
        }
        if ( v36 != 2777 )
        {
          if ( v36 != 2643 )
          {
            if ( v36 > 2645 )
            {
              if ( v36 <= 2647 )
                goto LABEL_399;
              if ( v36 != 2658 )
              {
                if ( v36 == 2660 )
                {
                  *v383 = 16;
                  v38 = (CY *)pvargSrc;
                  v79 = VarDecFromUI2(pvargSrc->vt, (DECIMAL *)v27);
LABEL_275:
                  ConversionSize = v79;
                  if ( (a16 & 8) != 0 )
                  {
LABEL_276:
                    v80 = ScaleDecimal((struct tagDEC *)v27, v381, 0);
LABEL_277:
                    ConversionSize = v80;
                    goto LABEL_54;
                  }
LABEL_1179:
                  v27 = Source;
                  goto LABEL_54;
                }
                goto LABEL_1516;
              }
LABEL_1291:
              pvarVal = pvargSrc;
              goto LABEL_1292;
            }
LABEL_1516:
            if ( (unsigned __int16)vt <= 0xEu )
              goto LABEL_1521;
            ConversionSize = IsLegalDBtype(vt);
            v378 = ConversionSize;
            if ( ConversionSize < 0 )
              goto LABEL_56;
            HIWORD(vt) = v391[1];
            if ( (v391[0] & 0x4000) == 0 )
            {
LABEL_1521:
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( off_383B49128[0] )
                {
                  LODWORD(lpMultiByteStr) = 8506;
                  bidTraceW(off_383B43280[0], 8710185, off_383B49128[0], 2147749405LL);
                }
                ConversionSize = -2147217891;
                v38 = (CY *)v396;
                v381 = v384[0];
                goto LABEL_54;
              }
              ConversionSize = -2147217891;
              goto LABEL_1526;
            }
            v31 = 49151;
            LOWORD(vt) = v391[0] & 0xBFFF;
            *(_DWORD *)v391 = vt;
            if ( !pvargSrc )
              goto LABEL_1690;
            pvarVal = *(VARIANTARG **)&pvargSrc->vt;
            pvargSrc = pvarVal;
            v396 = pvarVal;
            v32 = *(_QWORD *)ui;
            *(_QWORD *)v401 = *(_QWORD *)ui;
            LOWORD(v26) = v387;
LABEL_1540:
            v33 = 0x2000;
            goto LABEL_1541;
          }
LABEL_1448:
          *v383 = 56;
          if ( v385 )
          {
            v325 = (char *)((__int64 (__fastcall *)(LPMALLOC, __int64, _QWORD, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                             g_pIMalloc,
                             56,
                             (unsigned __int16)vt,
                             v33);
            *(_QWORD *)v27 = v325;
            if ( !v325 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( off_383B49128[0] )
                {
                  LODWORD(lpMultiByteStr) = 5143;
                  bidTraceW(off_383B43280[0], 5266473, off_383B49128[0], 2147942414LL);
                  ConversionSize = -2147024882;
                  v38 = (CY *)v396;
                  v381 = v384[0];
                  goto LABEL_54;
                }
                goto LABEL_1203;
              }
              goto LABEL_1204;
            }
            v27 = v325;
            Source = v325;
          }
          v326 = a16;
          v327 = v381;
          if ( (a16 & 0x40) == 0 )
            v327 = 7;
          v328 = CDataSource::FKatmaiOrNewer(v406);
          v366 = v327;
          v38 = (CY *)pvargSrc;
          v80 = CDataSource::BasicTypeToDBTYPE_SQLVARIANT(
                  v406,
                  pvargSrc,
                  (struct SSVARIANT *)v27,
                  a14,
                  CodePage,
                  v391[0],
                  *(size_t *)ui,
                  v326,
                  v366,
                  v380,
                  v328 == 0);
          goto LABEL_277;
        }
LABEL_511:
        *v383 = 19;
        *(_QWORD *)v27 = 0;
        *((_QWORD *)v27 + 1) = 0;
        *((_WORD *)v27 + 8) = 0;
        v27[18] = 0;
        v38 = (CY *)pvargSrc;
        if ( (_WORD)vt == 18 || (pvargSrc->vt & 0x8000u) == 0 )
        {
          v27[2] = 1;
          v101 = pvargSrc->vt;
        }
        else
        {
          v101 = -pvargSrc->vt;
        }
        *(_WORD *)(v27 + 3) = v101;
        v34 = 2;
        goto LABEL_385;
      }
      goto LABEL_917;
    }
    if ( v36 <= 19387 )
    {
      if ( v36 >= 19386 )
      {
LABEL_966:
        v38 = (CY *)pvargSrc;
        ConversionSize = _VarStrFromNum(
                           (const struct tagDB_NUMERIC *)pvargSrc,
                           sz,
                           (unsigned __int64 *)&cchWideChar,
                           v33);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v80 = FixupFromWstr(sz, cchWideChar, v387, CodePage, v27, v383, Size, v380, v385);
        goto LABEL_277;
      }
      v33 = 0x383800000uLL;
      switch ( v36 )
      {
        case 19092:
          if ( (a16 & 0x180) == 0 || a14 == CodePage || !v32 )
          {
            *v383 = v32;
            v160 = v385;
            if ( v385 )
            {
              v161 = *(_QWORD *)ui + 1LL;
              Size = *(_QWORD *)ui + 1LL;
              v162 = (char *)((__int64 (__fastcall *)(LPMALLOC, __int64, _QWORD, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                               g_pIMalloc,
                               *(_QWORD *)ui + 1LL,
                               (unsigned __int16)vt,
                               0x383800000uLL);
              *(_QWORD *)v27 = v162;
              if ( !v162 )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                {
                  LODWORD(lpMultiByteStr) = 4132;
                  bidTraceW(off_383B43280[0], 4231209, off_383B49128[0], 2147942414LL);
                  ConversionSize = -2147024882;
                  goto LABEL_56;
                }
                goto LABEL_1569;
              }
              v27 = v162;
              Source = v162;
              v160 = v385;
            }
            else
            {
              v161 = Size;
            }
            if ( v161 )
            {
              if ( *(_QWORD *)ui >= v161 )
              {
                *v380 = 4;
                v163 = v161 - 1;
                v38 = (CY *)pvargSrc;
                memcpy(v27, pvargSrc, v163);
                v27[Size - 1] = 0;
              }
              else
              {
                v38 = (CY *)pvargSrc;
                memcpy(v27, pvargSrc, *(size_t *)ui);
                v27[*(_QWORD *)ui] = 0;
              }
              ConversionSize = v378;
              goto LABEL_54;
            }
            if ( v160 )
              ((void (__fastcall *)(LPMALLOC, _BYTE *))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, v27);
            v41 = v380;
            *v380 = 6;
LABEL_853:
            ConversionSize = v378;
            goto LABEL_614;
          }
          v146 = 2 * v32;
          v147 = 0;
          v420 = 0;
          v427 = 0;
          if ( 2 * v32 > 0x1000 )
          {
            v150 = 4 * v32;
            if ( !is_mul_ok(v146, 2u) )
              v150 = -1;
            v151 = ((__int64 (__fastcall *)(struct IMalloc *, __int64, _QWORD, unsigned __int64))g_pMO->lpVtbl[1].Free)(
                     g_pMO,
                     v150,
                     (unsigned __int16)vt,
                     0x383800000uLL);
            if ( !v151 || (CAutoRg<unsigned short>::operator=(&v420, v151), (v147 = v420) == 0) )
            {
              if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              {
                LODWORD(lpMultiByteStr) = 4027;
                bidTraceW(off_383B43280[0], 4123689, off_383B49128[0], 2147942414LL);
              }
              ConversionSize = -2147024882;
              goto LABEL_56;
            }
            p_WideCharStr = v420;
            v149 = ui[0];
          }
          else
          {
            p_WideCharStr = &WideCharStr;
            v149 = v401[0];
          }
          v152 = FastMultiByteToWideChar(a14, 0, (const char *)pvargSrc, v149, p_WideCharStr, v146 >> 1);
          if ( !v152 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_383B49128[0] )
              {
                LODWORD(lpMultiByteStr) = 4043;
                bidTraceW(off_383B43280[0], 4140073, off_383B49128[0], 2147749383LL);
              }
              v147 = v420;
              pvargSrc = (VARIANTARG *)v396;
              v381 = v384[0];
            }
            ConversionSize = -2147217913;
            v41 = v380;
            *v380 = 2;
            if ( v147 )
            {
              ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v147);
              v27 = Source;
              goto LABEL_1526;
            }
LABEL_890:
            v27 = Source;
LABEL_614:
            v38 = (CY *)pvargSrc;
            goto LABEL_55;
          }
          LODWORD(lpMultiByteStr) = 0;
          v153 = (int)FastWideCharToMultiByte(
                        CodePage,
                        p_WideCharStr,
                        (const unsigned __int16 *)v152,
                        0,
                        lpMultiByteStr,
                        0,
                        (const char *)lpDefaultChar,
                        lpUsedDefaultChar);
          *v383 = v153;
          if ( !v385 )
            goto LABEL_832;
          Size = v153 + 1;
          v154 = (char *)((__int64 (__fastcall *)(LPMALLOC))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc);
          *(_QWORD *)Source = v154;
          if ( v154 )
          {
            Source = v154;
LABEL_832:
            if ( Size )
            {
              if ( CodePage >= 0xC42C )
                v155 = IsW2CSpecialCodePage(CodePage);
              else
                v155 = 0;
              v156 = &v427;
              if ( v155 )
                v156 = 0;
              LODWORD(lpMultiByteStr) = Size;
              v157 = (int)FastWideCharToMultiByte(
                            CodePage,
                            p_WideCharStr,
                            (const unsigned __int16 *)v152,
                            Source,
                            lpMultiByteStr,
                            (__int64)v156,
                            lpDefaultChara,
                            lpUsedDefaultChara);
              v397 = v157;
              v159 = Size;
              if ( v157 == *v383 && Size > v157 )
              {
                v27 = Source;
                Source[v157] = 0;
                v41 = v380;
                if ( v427 )
                  *v380 = 4;
              }
              else
              {
                v41 = v380;
                *v380 = 4;
                v27 = Source;
                Source[v159 - 1] = 0;
              }
              if ( v147 )
              {
                ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *, __int64, size_t))g_pMO->lpVtbl[1].DidAlloc)(
                  g_pMO,
                  v147,
                  v158,
                  v159);
                ConversionSize = v378;
                goto LABEL_1526;
              }
              goto LABEL_853;
            }
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_383B49128[0] )
              {
                LODWORD(lpMultiByteStr) = 4081;
                bidTraceW(off_383B43280[0], 4178985, off_383B49128[0], 2147749383LL);
              }
              v147 = v420;
            }
            ConversionSize = -2147217913;
            *v380 = 6;
          }
          else
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_383B49128[0] )
              {
                LODWORD(lpMultiByteStr) = 4070;
                bidTraceW(off_383B43280[0], 4167721, off_383B49128[0], 2147942414LL);
              }
              v147 = v420;
            }
            ConversionSize = -2147024882;
          }
          if ( v147 )
            ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v147);
          goto LABEL_56;
        case 19093:
          if ( a14 >= 0xC42C && (unsigned int)IsW2CSpecialCodePage(a14) )
          {
            v38 = (CY *)pvargSrc;
            v164 = (int)FastMultiByteToWideChar(a14, 0, (const char *)pvargSrc, v32, 0, 0);
            v165 = ui[0];
            v421 = *(_QWORD *)ui;
          }
          else
          {
            v38 = (CY *)pvargSrc;
            v164 = mbsnlenCP((LPCSTR)pvargSrc, v32, &v421, a14);
            v165 = v421;
          }
          v166 = 2 * v164;
          *v383 = 2 * v164;
          v167 = v385;
          if ( !v385 )
            goto LABEL_865;
          Size = v166 + 2;
          v168 = (char *)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, v166 + 2);
          *(_QWORD *)Source = v168;
          if ( !v168 )
          {
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
            {
              LODWORD(lpMultiByteStr) = 4205;
              bidTraceW(off_383B43280[0], 4305961, off_383B49128[0], 2147942414LL);
              ConversionSize = -2147024882;
              goto LABEL_56;
            }
            goto LABEL_1569;
          }
          Source = v168;
          v167 = v385;
LABEL_865:
          v169 = Size;
          if ( Size < 2 )
          {
            v27 = Source;
            if ( v167 )
            {
              ((void (__fastcall *)(LPMALLOC, char *))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, Source);
              v41 = v380;
              *v380 = 6;
              ConversionSize = v378;
            }
            else
            {
LABEL_699:
              v41 = v380;
              *v380 = 6;
              ConversionSize = v378;
            }
            goto LABEL_55;
          }
          if ( a14 >= 0xC42C )
          {
            v170 = IsW2CSpecialCodePage(a14);
            v169 = Size;
          }
          else
          {
            v170 = 0;
          }
          v171 = v169 >> 1;
          v172 = FastMultiByteToWideChar(
                   a14,
                   v170 == 0,
                   (const char *)pvargSrc,
                   v165,
                   (unsigned __int16 *)Source,
                   v169 >> 1);
          v397 = v172;
          if ( v172 == v164 && 2LL * v172 + 2 <= Size )
          {
            v27 = Source;
            *(_WORD *)&Source[2 * v172] = 0;
            ConversionSize = v378;
            goto LABEL_1526;
          }
          v41 = v380;
          *v380 = 4;
          v27 = Source;
          *(_WORD *)&Source[2 * v171 - 2] = 0;
          ConversionSize = v378;
          goto LABEL_614;
        case 19094:
        case 19241:
          goto LABEL_645;
        case 19095:
        case 19238:
        case 19242:
          goto LABEL_917;
        case 19096:
        case 19243:
          goto LABEL_663;
        case 19097:
        case 19244:
          goto LABEL_682;
        case 19098:
        case 19245:
          goto LABEL_725;
        case 19104:
          if ( a14 >= 0xC42C && (unsigned int)IsW2CSpecialCodePage(a14) )
          {
            v173 = (int)FastMultiByteToWideChar(a14, 0, (const char *)pvargSrc, v32, 0, 0);
            v174 = ui[0];
            v421 = *(_QWORD *)ui;
          }
          else
          {
            v173 = mbsnlenCP((LPCSTR)pvargSrc, v32, &v421, a14);
            v174 = v421;
          }
          *v383 = 2 * v173 + 2;
          if ( v385 )
          {
            Size = 2 * v173 + 2;
            v175 = (char *)((__int64 (__fastcall *)(LPMALLOC, size_t))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, Size);
            *(_QWORD *)Source = v175;
            if ( !v175 )
            {
              if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              {
                LODWORD(lpMultiByteStr) = 4281;
                bidTraceW(off_383B43280[0], 4383785, off_383B49128[0], 2147942414LL);
                ConversionSize = -2147024882;
                goto LABEL_56;
              }
              goto LABEL_1569;
            }
            v176 = v175;
            Source = v175;
          }
          else
          {
            v176 = Source;
          }
          v177 = Size;
          if ( Size >= 2 )
          {
            *(_WORD *)v176 = -257;
            if ( a14 >= 0xC42C )
            {
              v178 = IsW2CSpecialCodePage(a14);
              v177 = Size;
            }
            else
            {
              v178 = 0;
            }
            v179 = (int)FastMultiByteToWideChar(
                          a14,
                          v178 == 0,
                          (const char *)pvargSrc,
                          v174,
                          (unsigned __int16 *)v176 + 1,
                          (unsigned int)(v177 >> 1) - 1);
            v397 = v179;
            if ( (int)v179 == v173 && 2LL * (int)v179 + 2 <= Size )
              goto LABEL_245;
          }
          v41 = v380;
          *v380 = 4;
          ConversionSize = v378;
          goto LABEL_890;
        case 19107:
        case 19254:
          goto LABEL_1448;
        case 19108:
        case 19255:
          goto LABEL_700;
        case 19109:
        case 19256:
          goto LABEL_752;
        case 19110:
        case 19111:
        case 19257:
        case 19258:
          goto LABEL_248;
        case 19112:
          goto LABEL_615;
        case 19113:
          goto LABEL_621;
        case 19114:
          goto LABEL_627;
        case 19115:
          goto LABEL_631;
        case 19116:
          goto LABEL_635;
        case 19117:
          goto LABEL_648;
        case 19118:
          goto LABEL_48;
        case 19121:
          goto LABEL_619;
        case 19122:
          goto LABEL_1110;
        case 19124:
          goto LABEL_639;
        case 19126:
          goto LABEL_607;
        case 19127:
          goto LABEL_609;
        case 19128:
          goto LABEL_617;
        case 19129:
          goto LABEL_623;
        case 19130:
        case 19131:
          goto LABEL_625;
        case 19174:
          goto LABEL_783;
        case 19182:
          goto LABEL_902;
        case 19239:
          goto LABEL_1148;
        case 19240:
          goto LABEL_1121;
        case 19251:
          v38 = (CY *)pvargSrc;
          goto LABEL_892;
        case 19259:
        case 19260:
        case 19263:
        case 19268:
        case 19269:
        case 19271:
        case 19273:
        case 19274:
        case 19275:
        case 19276:
          goto LABEL_1291;
        case 19261:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          ConversionSize = _VarStrFromNum(
                             (const struct tagDB_NUMERIC *)pvargSrc,
                             sz,
                             (unsigned __int64 *)&cchWideChar,
                             0x383800000uLL);
          if ( ConversionSize < 0 )
            goto LABEL_54;
          v80 = VarR4FromStr(sz, 0x409u, 0, (FLOAT *)v27);
          goto LABEL_277;
        case 19262:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          ConversionSize = _VarStrFromNum(
                             (const struct tagDB_NUMERIC *)pvargSrc,
                             sz,
                             (unsigned __int64 *)&cchWideChar,
                             0x383800000uLL);
          if ( ConversionSize < 0 )
            goto LABEL_54;
          v80 = VarR8FromStr(sz, 0x409u, 0, (DOUBLE *)v27);
          goto LABEL_277;
        case 19265:
          goto LABEL_966;
        case 19277:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          v80 = _VarI8FromNum((struct tagDB_NUMERIC *)pvargSrc, v26, (__int64 *)v27, v380);
          goto LABEL_277;
        case 19278:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          if ( !pvargSrc->decVal.scale )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          v80 = _VarI8FromNum((struct tagDB_NUMERIC *)pvargSrc, v26, (__int64 *)v27, v380);
          goto LABEL_277;
        default:
          goto LABEL_1516;
      }
    }
    if ( v36 <= 19680 )
    {
      if ( v36 != 19680 )
      {
        v33 = 0x383800000uLL;
        switch ( v36 )
        {
          case 19388:
            *v383 = 19;
            v38 = (CY *)pvargSrc;
            *(_QWORD *)v27 = *(_QWORD *)&pvargSrc->vt;
            *((_QWORD *)v27 + 1) = pvargSrc->llVal;
            *((_WORD *)v27 + 8) = *((_WORD *)&pvargSrc->decVal + 8);
            v27[18] = *((_BYTE *)&pvargSrc->decVal + 18);
            if ( v381 == HIBYTE(pvargSrc->vt) && a11 == LOBYTE(pvargSrc->vt) )
              goto LABEL_290;
            v34 = 16;
            goto LABEL_385;
          case 19401:
            goto LABEL_1448;
          case 19404:
          case 19405:
          case 19551:
          case 19552:
            goto LABEL_248;
          case 19412:
          case 19533:
          case 19534:
LABEL_972:
            v38 = (CY *)pvargSrc;
            v80 = DoBYTEStoSTRConversion(v26, v32, v383, pvargSrc, CodePage, v27, Size, v380, v385);
            goto LABEL_277;
          case 19416:
          case 19558:
            goto LABEL_1291;
          case 19532:
          case 19536:
            goto LABEL_1192;
          case 19559:
            goto LABEL_987;
          case 19563:
            goto LABEL_1675;
          case 19615:
            *v383 = 8;
            *(_QWORD *)&SystemTime.wYear = 0;
            *(_QWORD *)&SystemTime.wHour = 0;
            v38 = (CY *)pvargSrc;
            SystemTime.wYear = pvargSrc->vt;
            SystemTime.wMonth = pvargSrc->wReserved1;
            SystemTime.wDay = pvargSrc->wReserved2;
            if ( !(unsigned int)IsValidFileTimeDateValue(
                                  SystemTime.wYear,
                                  SystemTime.wMonth,
                                  SystemTime.wDay,
                                  0,
                                  0,
                                  0,
                                  0)
              || !SystemTimeToFileTime(&SystemTime, (LPFILETIME)v27) )
            {
              goto LABEL_1632;
            }
            ConversionSize = v378;
            goto LABEL_54;
          default:
            goto LABEL_1516;
        }
      }
      v38 = (CY *)pvargSrc;
      ConversionSize = StringCchPrintfA(
                         (char *)sz,
                         0x104u,
                         "%04hi-%02hu-%02hu",
                         (__int16)pvargSrc->vt,
                         pvargSrc->wReserved1,
                         pvargSrc->wReserved2);
      if ( ConversionSize < 0 )
        goto LABEL_103;
      v111 = -1;
      do
        ++v111;
      while ( *((_BYTE *)sz + v111) );
LABEL_1048:
      cchWideChar = (unsigned __int16 *)v111;
      v80 = CopyToStr(sz, v27, v111, v383, Size, v380, v385);
      goto LABEL_277;
    }
    if ( v36 <= 19974 )
    {
      if ( v36 != 19974 )
      {
        v33 = 0x383800000uLL;
        switch ( v36 )
        {
          case 19681:
LABEL_987:
            v38 = (CY *)pvargSrc;
            LODWORD(cbMultiByte) = pvargSrc->wReserved2;
            LODWORD(lpMultiByteStr) = pvargSrc->wReserved1;
            ConversionSize = StringCchPrintfW(
                               sz,
                               0x104u,
                               L"%04hi-%02hu-%02hu",
                               (unsigned int)(__int16)pvargSrc->vt,
                               lpMultiByteStr,
                               cbMultiByte);
            if ( ConversionSize < 0 )
              goto LABEL_103;
            v199 = -1;
            do
              ++v199;
            while ( sz[v199] );
            goto LABEL_1079;
          case 19684:
          case 19832:
            *v383 = 6;
            v38 = (CY *)pvargSrc;
            *(_DWORD *)v27 = *(_DWORD *)&pvargSrc->vt;
            *((_WORD *)v27 + 2) = pvargSrc->wReserved2;
            ConversionSize = v378;
            goto LABEL_54;
          case 19686:
            *v383 = 16;
            v38 = (CY *)pvargSrc;
            ConversionSize = v378;
            if ( !(unsigned int)IsValidDateValue(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2) )
            {
LABEL_1586:
              *v380 = 6;
              goto LABEL_56;
            }
            *(_DWORD *)v27 = 0;
            *((_DWORD *)v27 + 1) = 0;
            *((_DWORD *)v27 + 2) = 0;
            *((_DWORD *)v27 + 3) = 0;
            *(_WORD *)v27 = pvargSrc->vt;
            *((_WORD *)v27 + 1) = pvargSrc->wReserved1;
            *((_WORD *)v27 + 2) = pvargSrc->wReserved2;
            break;
          case 19695:
          case 19842:
            goto LABEL_1448;
          case 19697:
            *v383 = 20;
            v38 = (CY *)pvargSrc;
            if ( !(unsigned int)IsValidSqlDateValue(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2) )
              goto LABEL_1632;
            *(_DWORD *)v27 = 0;
            *((_DWORD *)v27 + 1) = 0;
            *((_DWORD *)v27 + 2) = 0;
            *((_DWORD *)v27 + 3) = 0;
            *((_DWORD *)v27 + 4) = 0;
            *(_WORD *)v27 = pvargSrc->vt;
            *((_WORD *)v27 + 1) = pvargSrc->wReserved1;
            *((_WORD *)v27 + 2) = pvargSrc->wReserved2;
            if ( (a16 & 0x120) != 0x20 )
              goto LABEL_389;
            ConversionSize = v378;
            if ( !(unsigned int)TimeZoneOffsetFromTimeStamp(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  0,
                                  0,
                                  0,
                                  0,
                                  &v414,
                                  &v410) )
              goto LABEL_103;
            *((_WORD *)v27 + 8) = v414;
            *((_WORD *)v27 + 9) = v410;
            goto LABEL_54;
          case 19698:
          case 19699:
          case 19845:
          case 19846:
            goto LABEL_248;
          case 19706:
          case 19828:
            v38 = (CY *)pvargSrc;
            LODWORD(cbMultiByte) = pvargSrc->wReserved2;
            LODWORD(lpMultiByteStr) = pvargSrc->wReserved1;
            ConversionSize = StringCchPrintfW(
                               sz,
                               0x104u,
                               L"%02hu:%02hu:%02hu",
                               pvargSrc->vt,
                               lpMultiByteStr,
                               cbMultiByte);
            if ( ConversionSize < 0 )
              goto LABEL_103;
            v199 = -1;
            do
              ++v199;
            while ( sz[v199] );
            goto LABEL_1079;
          case 19827:
            v38 = (CY *)pvargSrc;
            ConversionSize = StringCchPrintfA(
                               (char *)sz,
                               0x104u,
                               "%02hu:%02hu:%02hu",
                               pvargSrc->vt,
                               pvargSrc->wReserved1,
                               pvargSrc->wReserved2);
            if ( ConversionSize < 0 )
              goto LABEL_103;
            v111 = -1;
            do
              ++v111;
            while ( *((_BYTE *)sz + v111) );
            goto LABEL_1048;
          case 19831:
          case 19833:
          case 19857:
            goto LABEL_1291;
          case 19843:
            *v383 = 12;
            v38 = (CY *)pvargSrc;
            if ( pvargSrc->vt > 0x17u || pvargSrc->wReserved1 > 0x3Bu || pvargSrc->wReserved2 > 0x3Bu )
              goto LABEL_1632;
            *(_WORD *)v27 = pvargSrc->vt;
            *((_WORD *)v27 + 1) = pvargSrc->wReserved1;
            *((_WORD *)v27 + 2) = pvargSrc->wReserved2;
            *((_DWORD *)v27 + 2) = 0;
            *((_WORD *)v27 + 3) = 0;
            ConversionSize = v378;
            goto LABEL_54;
          case 19844:
            *v383 = 20;
            if ( pvargSrc->vt > 0x17u || pvargSrc->wReserved1 > 0x3Bu || pvargSrc->wReserved2 > 0x3Bu )
              goto LABEL_1632;
            GetLocalTime(&v541);
            v200 = a16 & 0x20;
            if ( (a16 & 0x20) != 0
              && !(unsigned int)TimeZoneOffsetFromTimeStamp(
                                  v541.wYear,
                                  v541.wMonth,
                                  v541.wDay,
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  0,
                                  v418,
                                  v415) )
            {
              goto LABEL_1633;
            }
            *(_DWORD *)v27 = 0;
            *((_DWORD *)v27 + 1) = 0;
            *((_DWORD *)v27 + 2) = 0;
            *((_DWORD *)v27 + 3) = 0;
            *((_DWORD *)v27 + 4) = 0;
            *(_WORD *)v27 = v541.wYear;
            *((_WORD *)v27 + 1) = v541.wMonth;
            *((_WORD *)v27 + 2) = v541.wDay;
            *((_WORD *)v27 + 3) = pvargSrc->vt;
            *((_WORD *)v27 + 4) = pvargSrc->wReserved1;
            *((_WORD *)v27 + 5) = pvargSrc->wReserved2;
            *((_DWORD *)v27 + 3) = 0;
            ConversionSize = v378;
            v41 = v380;
            v201 = v200 == 0;
            v38 = (CY *)pvargSrc;
            if ( !v201 )
            {
              *((_WORD *)v27 + 8) = v418[0];
              *((_WORD *)v27 + 9) = v415[0];
            }
            goto LABEL_55;
          case 19847:
            v38 = (CY *)pvargSrc;
            if ( pvargSrc->vt < 0x64u
              || !(unsigned int)OleDateFromTm(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  pvargSrc->wReserved3,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  pvargSrc->cyVal.Hi / 0xF4240u,
                                  &v520) )
            {
              goto LABEL_1632;
            }
            *v383 = 2;
            v80 = VarI2FromR8(v520, (SHORT *)v27);
            goto LABEL_277;
          case 19852:
            goto LABEL_1293;
          case 19853:
            goto LABEL_1057;
          case 19861:
            v38 = (CY *)pvargSrc;
            if ( pvargSrc->vt < 0x64u
              || !(unsigned int)OleDateFromTm(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  pvargSrc->wReserved3,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  pvargSrc->cyVal.Hi / 0xF4240u,
                                  &dblIn) )
            {
              goto LABEL_1632;
            }
            *v383 = 1;
            v80 = VarI1FromR8(dblIn, v27);
            goto LABEL_277;
          case 19909:
            *v383 = 8;
            *(_QWORD *)&SystemTime.wYear = 0;
            *(_QWORD *)&SystemTime.wHour = 0;
            year = pvargSrc->vt;
            SystemTime.wYear = pvargSrc->vt;
            wReserved1 = pvargSrc->wReserved1;
            SystemTime.wMonth = wReserved1;
            wReserved2 = pvargSrc->wReserved2;
            SystemTime.wDay = wReserved2;
            wReserved3 = pvargSrc->wReserved3;
            SystemTime.wHour = wReserved3;
            uiVal = pvargSrc->uiVal;
            SystemTime.wMinute = uiVal;
            second = WORD1(pvargSrc->decVal.Lo64);
            SystemTime.wSecond = second;
            v208 = 1125899907LL * pvargSrc->decVal.Mid32;
            goto LABEL_1023;
          default:
            goto LABEL_1516;
        }
        goto LABEL_54;
      }
      Mid32 = pvargSrc->decVal.Mid32;
      v403 = Mid32;
      if ( (a16 & 0x20) != 0 )
      {
        if ( pvargSrc->wReserved3 > 0x17u
          || pvargSrc->iVal > 0x3Bu
          || WORD1(pvargSrc->decVal.Lo64) > 0x3Bu
          || Mid32 > 0x3B9AC9FF
          || !(unsigned int)IsValidSqlDateValue(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2) )
        {
LABEL_1632:
          *v380 = 6;
          ConversionSize = v378;
          goto LABEL_56;
        }
        if ( Size < 0x15 )
          v210 = 0;
        else
          v210 = Size - 21;
        v381 = Mid32 != 0 ? 9 : 0;
        v384[0] = v381;
        v211 = v381;
        if ( v210 < v381 )
          v211 = v210;
      }
      else if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v406 + 43) + 40LL) + 880LL) == 80 )
      {
        v211 = Mid32 != 0 ? 9 : 0;
      }
      else
      {
        v211 = v381;
      }
      if ( !AdjustFractionalSeconds(&v403, v211) )
        goto LABEL_1633;
      if ( v211 )
      {
        v212 = StringCchPrintfA(
                 (char *)sz,
                 0x104u,
                 "%04hi-%02hu-%02hu %02hu:%02hu:%02hu.%0*u",
                 (__int16)pvargSrc->vt,
                 pvargSrc->wReserved1,
                 pvargSrc->wReserved2,
                 pvargSrc->wReserved3,
                 pvargSrc->uiVal,
                 WORD1(pvargSrc->decVal.Lo64),
                 v211,
                 v403);
        v38 = (CY *)pvargSrc;
      }
      else
      {
        v38 = (CY *)pvargSrc;
        v212 = StringCchPrintfA(
                 (char *)sz,
                 0x104u,
                 "%04hi-%02hu-%02hu %02hu:%02hu:%02hu",
                 (__int16)pvargSrc->vt,
                 pvargSrc->wReserved1,
                 pvargSrc->wReserved2,
                 pvargSrc->wReserved3,
                 pvargSrc->uiVal,
                 WORD1(pvargSrc->decVal.Lo64));
      }
      v378 = v212;
      if ( v212 < 0 )
        goto LABEL_1633;
      v111 = -1;
      do
        ++v111;
      while ( *((_BYTE *)sz + v111) );
      goto LABEL_1048;
    }
    if ( v36 > 21312 )
    {
      if ( v36 > 21591 )
      {
        switch ( v36 )
        {
          case 21592:
LABEL_1461:
            v330 = *((_WORD *)&pvargSrc->decVal + 9);
            v331 = *((_WORD *)&pvargSrc->decVal + 8);
            v332 = pvargSrc->decVal.Mid32;
            if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  pvargSrc->wReserved3,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  v332,
                                  v331,
                                  v330) )
              goto LABEL_1632;
            if ( v331 < 0 || (v386[0] = 1, v330 < 0) )
              v386[0] = 0;
            v401[0] = v332;
            if ( (a16 & 0x20) != 0 )
            {
              if ( Size >> 1 < 0x1C )
                v333 = 0;
              else
                v333 = (Size >> 1) - 28;
              v381 = 9;
              v384[0] = 9;
              v334 = 9;
              if ( v333 < 9 )
                v334 = v333;
            }
            else
            {
              v334 = v381;
            }
            if ( !AdjustFractionalSeconds(v401, v334) )
              goto LABEL_1633;
            v335 = abs16(v330);
            if ( v334 )
            {
              v405 = v335;
              v336 = 45;
              if ( v386[0] )
                v336 = 43;
              LODWORD(v373) = v336;
              LODWORD(v371) = v401[0];
              LODWORD(v369) = v334;
              LODWORD(v367) = WORD1(pvargSrc->decVal.Lo64);
              LODWORD(lpUsedDefaultCharb) = pvargSrc->uiVal;
              LODWORD(lpDefaultCharb) = pvargSrc->wReserved3;
              LODWORD(cbMultiByte) = pvargSrc->wReserved2;
              LODWORD(lpMultiByteStr) = pvargSrc->wReserved1;
              v337 = StringCchPrintfW(
                       sz,
                       0x104u,
                       L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu.%0*u %01c%02hu:%02hu",
                       (unsigned int)(__int16)pvargSrc->vt,
                       lpMultiByteStr,
                       cbMultiByte,
                       lpDefaultCharb,
                       lpUsedDefaultCharb,
                       v367,
                       v369);
            }
            else
            {
              v338 = abs16(*((_WORD *)&pvargSrc->decVal + 8));
              v339 = 45;
              if ( v386[0] )
                v339 = 43;
              LODWORD(v373) = v335;
              LODWORD(v371) = v338;
              LODWORD(v369) = v339;
              LODWORD(v367) = WORD1(pvargSrc->decVal.Lo64);
              LODWORD(lpUsedDefaultCharb) = pvargSrc->uiVal;
              LODWORD(lpDefaultCharb) = pvargSrc->wReserved3;
              LODWORD(cbMultiByte) = pvargSrc->wReserved2;
              LODWORD(lpMultiByteStr) = pvargSrc->wReserved1;
              v337 = StringCchPrintfW(
                       sz,
                       0x104u,
                       L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu %01c%02hu:%02hu",
                       (unsigned int)(__int16)pvargSrc->vt,
                       lpMultiByteStr,
                       cbMultiByte,
                       lpDefaultCharb,
                       lpUsedDefaultCharb,
                       v367,
                       v369);
            }
            v378 = v337;
            if ( v337 < 0 )
              goto LABEL_1633;
            v340 = -1;
            do
              ++v340;
            while ( sz[v340] );
            cchWideChar = (unsigned __int16 *)v340;
            v27 = Source;
            ConversionSize = FixupFromWstr(
                               sz,
                               (unsigned __int16 *)v340,
                               v387,
                               0xFFFFFFFF,
                               Source,
                               v383,
                               Size,
                               v380,
                               v385);
            goto LABEL_1526;
          case 21595:
            *v383 = 6;
            v217 = pvargSrc->vt;
            if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  pvargSrc->wReserved3,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  pvargSrc->decVal.Mid32,
                                  *((_WORD *)&pvargSrc->decVal + 8),
                                  *((_WORD *)&pvargSrc->decVal + 9)) )
              goto LABEL_1632;
            if ( (a16 & 0x100) != 0 )
            {
LABEL_1085:
              *(_WORD *)v27 = v217;
              v38 = (CY *)pvargSrc;
              *((_WORD *)v27 + 1) = pvargSrc->wReserved1;
              *((_WORD *)v27 + 2) = pvargSrc->wReserved2;
              goto LABEL_1086;
            }
            v38 = (CY *)pvargSrc;
            if ( (a16 & 0x20) != 0 )
              v341 = ConvertOffsetToUTC((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400);
            else
              v341 = ConvertOffsetToLocal((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400);
            ConversionSize = v378;
            if ( v341 )
              goto LABEL_103;
            *(_WORD *)v27 = v400.year;
            *((_WORD *)v27 + 1) = v400.month;
            *((_WORD *)v27 + 2) = v400.day;
            goto LABEL_54;
          case 21596:
            *v383 = 6;
            v38 = (CY *)pvargSrc;
            if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  pvargSrc->wReserved3,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  pvargSrc->decVal.Mid32,
                                  *((_WORD *)&pvargSrc->decVal + 8),
                                  *((_WORD *)&pvargSrc->decVal + 9)) )
              goto LABEL_1632;
            if ( (a16 & 0x20) != 0 )
              v342 = ConvertOffsetToUTC((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400);
            else
              v342 = ConvertOffsetToLocal((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400);
            ConversionSize = v378;
            if ( v342 )
              goto LABEL_103;
            *(_WORD *)v27 = v400.hour;
            *((_WORD *)v27 + 1) = v400.minute;
            *((_WORD *)v27 + 2) = v400.second;
            goto LABEL_54;
          case 21597:
            *v383 = 16;
            v348 = pvargSrc->decVal.Mid32;
            v349 = pvargSrc->vt;
            if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  pvargSrc->wReserved3,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  v348,
                                  *((_WORD *)&pvargSrc->decVal + 8),
                                  *((_WORD *)&pvargSrc->decVal + 9)) )
              goto LABEL_1632;
            if ( (a16 & 0x920) == 0x20 && v348 % dword_3839128A0[v381] )
              goto LABEL_1658;
            v38 = (CY *)pvargSrc;
            if ( (a16 & 0x100) != 0 )
            {
              v350 = Source;
              *(_WORD *)Source = v349;
              v27 = v350;
              *((_WORD *)v350 + 1) = pvargSrc->wReserved1;
              *((_WORD *)v350 + 2) = pvargSrc->wReserved2;
              *((_WORD *)v350 + 3) = pvargSrc->wReserved3;
              *((_WORD *)v350 + 4) = pvargSrc->iVal;
              *((_WORD *)v350 + 5) = WORD1(pvargSrc->decVal.Lo64);
              *((_DWORD *)v350 + 3) = pvargSrc->cyVal.Hi;
              goto LABEL_1086;
            }
            v27 = Source;
            ConversionSize = v378;
            if ( !(unsigned int)ConvertOffsetToDestination(
                                  (const struct tagDBTIMESTAMPOFFSET *)pvargSrc,
                                  (struct tagDBTIMESTAMP *)Source,
                                  a16) )
              goto LABEL_103;
            goto LABEL_54;
          case 21606:
            goto LABEL_1448;
          case 21607:
            *v383 = 12;
            v343 = pvargSrc->decVal.Mid32;
            v344 = pvargSrc->wReserved3;
            if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  v344,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  v343,
                                  *((_WORD *)&pvargSrc->decVal + 8),
                                  *((_WORD *)&pvargSrc->decVal + 9)) )
              goto LABEL_1632;
            if ( (a16 & 0x20) != 0 && v343 % dword_3839128A0[v381] )
              goto LABEL_1658;
            v38 = (CY *)pvargSrc;
            if ( (a16 & 0x100) != 0 )
            {
              v345 = Source;
              *(_WORD *)Source = v344;
              v27 = v345;
              *((_WORD *)v345 + 1) = pvargSrc->iVal;
              *((_WORD *)v345 + 2) = WORD1(pvargSrc->decVal.Lo64);
              fraction = pvargSrc->decVal.Mid32;
            }
            else
            {
              if ( (a16 & 0x20) != 0 )
                v347 = ConvertOffsetToUTC((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400);
              else
                v347 = ConvertOffsetToLocal((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400);
              if ( v347 )
                goto LABEL_1633;
              v27 = Source;
              *(_WORD *)Source = v400.hour;
              *((_WORD *)v27 + 1) = v400.minute;
              *((_WORD *)v27 + 2) = v400.second;
              fraction = v400.fraction;
            }
            *((_DWORD *)v27 + 2) = fraction;
            *((_WORD *)v27 + 3) = 0;
LABEL_1086:
            ConversionSize = v378;
            break;
          case 21608:
            *v383 = 20;
            v329 = pvargSrc->decVal.Mid32;
            if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  pvargSrc->wReserved3,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  v329,
                                  *((_WORD *)&pvargSrc->decVal + 8),
                                  *((_WORD *)&pvargSrc->decVal + 9)) )
              goto LABEL_1632;
            if ( (a16 & 0x20) != 0 && v329 % dword_3839128A0[v381] )
              goto LABEL_1658;
            v38 = (CY *)pvargSrc;
            *(_DWORD *)v27 = *(_DWORD *)&pvargSrc->vt;
            *((_DWORD *)v27 + 1) = pvargSrc->decVal.Hi32;
            *((_DWORD *)v27 + 2) = pvargSrc->lVal;
            *((_DWORD *)v27 + 3) = pvargSrc->cyVal.Hi;
            *((_DWORD *)v27 + 4) = *((_DWORD *)&pvargSrc->decVal + 4);
            goto LABEL_586;
          default:
            goto LABEL_1516;
        }
        goto LABEL_54;
      }
      if ( v36 != 21591 )
      {
        v33 = 0x383800000uLL;
        switch ( v36 )
        {
          case 21315:
          case 21316:
          case 21462:
          case 21463:
            goto LABEL_248;
          case 21322:
          case 21448:
            goto LABEL_1291;
          case 21323:
          case 21445:
            Lo = pvargSrc->cyVal.Lo;
            v423 = Lo;
            if ( pvargSrc->vt > 0x17u )
              goto LABEL_1632;
            v271 = pvargSrc->wReserved1;
            if ( v271 > 0x3Bu )
              goto LABEL_1632;
            v272 = pvargSrc->wReserved2;
            if ( v272 > 0x3Bu || Lo > 0x3B9AC9FF )
              goto LABEL_1632;
            if ( (a16 & 0x20) != 0 )
            {
              if ( Size >> 1 < 0xA )
                v273 = 0;
              else
                v273 = (Size >> 1) - 10;
              v381 = 9;
              v384[0] = 9;
              v274 = 9;
              if ( v273 < 9 )
                v274 = v273;
            }
            else
            {
              v274 = v381;
            }
            if ( !AdjustFractionalSeconds(&v423, v274) )
              goto LABEL_1633;
            if ( v274 )
            {
              LODWORD(lpUsedDefaultChar) = v423;
              LODWORD(lpDefaultChar) = v274;
              LODWORD(cbMultiByte) = v272;
              LODWORD(lpMultiByteStr) = v271;
              v275 = StringCchPrintfW(
                       sz,
                       0x104u,
                       L"%02hu:%02hu:%02hu.%0*u",
                       pvargSrc->vt,
                       lpMultiByteStr,
                       cbMultiByte,
                       lpDefaultChar,
                       lpUsedDefaultChar);
              v38 = (CY *)pvargSrc;
            }
            else
            {
              v38 = (CY *)pvargSrc;
              LODWORD(cbMultiByte) = v272;
              LODWORD(lpMultiByteStr) = v271;
              v275 = StringCchPrintfW(sz, 0x104u, L"%02hu:%02hu:%02hu", pvargSrc->vt, lpMultiByteStr, cbMultiByte);
            }
            v378 = v275;
            if ( v275 < 0 )
              goto LABEL_1633;
            v276 = -1;
            do
              ++v276;
            while ( sz[v276] );
            cchWideChar = (unsigned __int16 *)v276;
            v27 = Source;
            v80 = FixupFromWstr(sz, (unsigned __int16 *)v276, v387, 0xFFFFFFFF, Source, v383, Size, v380, v385);
            goto LABEL_277;
          case 21327:
          case 21474:
LABEL_1675:
            v377 = a16;
            v376 = CodePage;
            v375 = a14;
            v374 = v381;
            v372 = a11;
            v370 = (unsigned __int8 *)v380;
            v368 = a9;
            cbMultiBytea = pvargSrc;
            v353 = vt;
            goto LABEL_1661;
          case 21379:
            *v383 = 8;
            *(_QWORD *)&SystemTime.wYear = 0;
            *(_QWORD *)&SystemTime.wHour = 0;
            GetLocalTime(&v543);
            year = v543.wYear;
            SystemTime.wYear = v543.wYear;
            wReserved1 = v543.wMonth;
            SystemTime.wMonth = v543.wMonth;
            wReserved2 = v543.wDay;
            SystemTime.wDay = v543.wDay;
            wReserved3 = pvargSrc->vt;
            SystemTime.wHour = pvargSrc->vt;
            uiVal = pvargSrc->wReserved1;
            SystemTime.wMinute = uiVal;
            second = pvargSrc->wReserved2;
            SystemTime.wSecond = second;
            v208 = 1125899907LL * pvargSrc->cyVal.Lo;
            goto LABEL_1023;
          case 21444:
            v263 = pvargSrc->cyVal.Lo;
            v426 = v263;
            if ( pvargSrc->vt > 0x17u )
              goto LABEL_1632;
            v264 = pvargSrc->wReserved1;
            if ( v264 > 0x3Bu )
              goto LABEL_1632;
            v265 = pvargSrc->wReserved2;
            if ( v265 > 0x3Bu || v263 > 0x3B9AC9FF )
              goto LABEL_1632;
            if ( (a16 & 0x20) != 0 )
            {
              if ( Size < 0xA )
                v266 = 0;
              else
                v266 = Size - 10;
              v381 = 9;
              v384[0] = 9;
              v267 = 9;
              if ( v266 < 9 )
                v267 = v266;
            }
            else
            {
              v267 = v381;
            }
            if ( !AdjustFractionalSeconds(&v426, v267) )
              goto LABEL_1633;
            if ( v267 )
            {
              v268 = StringCchPrintfA(
                       (char *)sz,
                       0x104u,
                       "%02hu:%02hu:%02hu.%0*u",
                       pvargSrc->vt,
                       v264,
                       v265,
                       v267,
                       v426);
              v38 = (CY *)pvargSrc;
            }
            else
            {
              v38 = (CY *)pvargSrc;
              v268 = StringCchPrintfA((char *)sz, 0x104u, "%02hu:%02hu:%02hu", pvargSrc->vt, v264, v265);
            }
            v378 = v268;
            if ( v268 < 0 )
              goto LABEL_1633;
            v269 = -1;
            do
              ++v269;
            while ( *((_BYTE *)sz + v269) );
            cchWideChar = (unsigned __int16 *)v269;
            v27 = Source;
            v80 = CopyToStr(sz, Source, v269, v383, Size, v380, v385);
            goto LABEL_277;
          case 21449:
            *v383 = 6;
            v38 = (CY *)pvargSrc;
            if ( pvargSrc->vt > 0x17u
              || pvargSrc->wReserved1 > 0x3Bu
              || pvargSrc->wReserved2 > 0x3Bu
              || pvargSrc->lVal > 0x3B9AC9FFu )
            {
              goto LABEL_1632;
            }
            *(_WORD *)v27 = pvargSrc->vt;
            *((_WORD *)v27 + 1) = pvargSrc->wReserved1;
            *((_WORD *)v27 + 2) = pvargSrc->wReserved2;
            goto LABEL_586;
          case 21450:
            *v383 = 16;
            v38 = (CY *)pvargSrc;
            if ( pvargSrc->vt > 0x17u )
              goto LABEL_1632;
            if ( pvargSrc->wReserved1 > 0x3Bu )
              goto LABEL_1632;
            if ( pvargSrc->wReserved2 > 0x3Bu )
              goto LABEL_1632;
            v260 = pvargSrc->cyVal.Lo;
            if ( v260 > 0x3B9AC9FF )
              goto LABEL_1632;
            if ( (a16 & 0x920) == 0x20 && v260 % dword_3839128A0[v381] )
              goto LABEL_1658;
            if ( (a16 & 0x100) != 0 )
            {
              *(_WORD *)v27 = 1900;
              v261 = 1;
              *((_WORD *)v27 + 1) = 1;
            }
            else
            {
              GetLocalTime(&v546);
              *(_WORD *)v27 = v546.wYear;
              *((_WORD *)v27 + 1) = v546.wMonth;
              v261 = v546.wDay;
            }
            *((_WORD *)v27 + 2) = v261;
            *((_WORD *)v27 + 3) = pvargSrc->vt;
            *((_WORD *)v27 + 4) = pvargSrc->wReserved1;
            *((_WORD *)v27 + 5) = pvargSrc->wReserved2;
            *((_DWORD *)v27 + 3) = pvargSrc->lVal;
            ConversionSize = v378;
            goto LABEL_54;
          case 21459:
            goto LABEL_1448;
          case 21460:
            v38 = (CY *)pvargSrc;
            if ( pvargSrc->vt > 0x17u
              || pvargSrc->wReserved1 > 0x3Bu
              || pvargSrc->wReserved2 > 0x3Bu
              || (v259 = pvargSrc->cyVal.Lo, v259 > 0x3B9AC9FF) )
            {
              if ( (a16 & 0x20) != 0 )
                goto LABEL_1632;
              v41 = v380;
              *v380 = 4;
            }
            else
            {
              if ( (a16 & 0x20) != 0 && v259 % dword_3839128A0[v381] )
              {
LABEL_1658:
                *v380 = 6;
                ConversionSize = v378;
                if ( v404 )
                  *(_DWORD *)v404 = 3;
                goto LABEL_56;
              }
              v41 = v380;
            }
            *v383 = 12;
            *(_DWORD *)v27 = *(_DWORD *)&pvargSrc->vt;
            *((_DWORD *)v27 + 1) = pvargSrc->decVal.Hi32;
            *((_DWORD *)v27 + 2) = pvargSrc->lVal;
            ConversionSize = v378;
            break;
          case 21461:
            *v383 = 20;
            v38 = (CY *)pvargSrc;
            if ( pvargSrc->vt > 0x17u
              || pvargSrc->wReserved1 > 0x3Bu
              || pvargSrc->wReserved2 > 0x3Bu
              || pvargSrc->lVal > 0x3B9AC9FFu )
            {
              goto LABEL_1632;
            }
            *(_DWORD *)v27 = 0;
            *((_DWORD *)v27 + 1) = 0;
            *((_DWORD *)v27 + 2) = 0;
            *((_DWORD *)v27 + 3) = 0;
            *((_DWORD *)v27 + 4) = 0;
            v262 = a16;
            if ( (a16 & 0x100) != 0 )
            {
              *(_WORD *)v27 = 1900;
              *((_WORD *)v27 + 1) = 1;
              *((_WORD *)v27 + 2) = 1;
            }
            else
            {
              GetLocalTime(&v547);
              *(_WORD *)v27 = v547.wYear;
              *((_WORD *)v27 + 1) = v547.wMonth;
              *((_WORD *)v27 + 2) = v547.wDay;
            }
            *((_WORD *)v27 + 3) = pvargSrc->vt;
            *((_WORD *)v27 + 4) = pvargSrc->wReserved1;
            *((_WORD *)v27 + 5) = pvargSrc->wReserved2;
            lVal = pvargSrc->lVal;
            v224 = v262;
LABEL_1107:
            *((_DWORD *)v27 + 3) = lVal;
            ConversionSize = v378;
            if ( FixUpTimeZone((struct tagDBTIMESTAMPOFFSET *)v27, v224, v381, v380) )
              goto LABEL_54;
            goto LABEL_56;
          case 21469:
            goto LABEL_1293;
          case 21470:
            goto LABEL_1461;
          case 21526:
            *v383 = 8;
            if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                  pvargSrc->vt,
                                  pvargSrc->wReserved1,
                                  pvargSrc->wReserved2,
                                  pvargSrc->wReserved3,
                                  pvargSrc->uiVal,
                                  WORD1(pvargSrc->decVal.Lo64),
                                  pvargSrc->decVal.Mid32,
                                  *((_WORD *)&pvargSrc->decVal + 8),
                                  *((_WORD *)&pvargSrc->decVal + 9)) )
              goto LABEL_1632;
            if ( ConvertOffsetToLocal((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400) )
              goto LABEL_1633;
            SystemTime.wDayOfWeek = 0;
            SystemTime.wMilliseconds = 0;
            year = v400.year;
            SystemTime.wYear = v400.year;
            wReserved1 = v400.month;
            SystemTime.wMonth = v400.month;
            wReserved2 = v400.day;
            SystemTime.wDay = v400.day;
            wReserved3 = v400.hour;
            SystemTime.wHour = v400.hour;
            uiVal = v400.minute;
            SystemTime.wMinute = v400.minute;
            second = v400.second;
            SystemTime.wSecond = v400.second;
            v208 = 1125899907LL * v400.fraction;
LABEL_1023:
            SystemTime.wMilliseconds = HIDWORD(v208) >> 18;
            if ( !(unsigned int)IsValidFileTimeDateValue(
                                  year,
                                  wReserved1,
                                  wReserved2,
                                  wReserved3,
                                  uiVal,
                                  second,
                                  SystemTime.wMilliseconds)
              || !SystemTimeToFileTime(&SystemTime, (LPFILETIME)v27) )
            {
              goto LABEL_1632;
            }
            ConversionSize = v378;
            goto LABEL_1526;
          default:
            goto LABEL_1516;
        }
LABEL_55:
        if ( v395 != 7 )
          goto LABEL_56;
        switch ( v422 )
        {
          case 2:
          case 3:
          case 16:
          case 17:
          case 18:
          case 19:
            valid = IsValidDate(*(double *)v27, v41);
            v379 = valid;
            if ( valid >= 0 || (bidGblFlags & 2) == 0 )
              goto LABEL_1689;
            bidTraceHR(off_383B43280[0], 8731657, (unsigned int)valid);
            ConversionSize = v379;
            goto LABEL_56;
          case 20:
          case 21:
            if ( v391[0] <= 0xEu )
              goto LABEL_1676;
            ConversionSize = IsLegalDBtype(v391[0]);
            v378 = ConversionSize;
            if ( ConversionSize < 0 )
              goto LABEL_56;
            HIWORD(vt) = v391[1];
            if ( (v391[0] & 0x4000) == 0 )
            {
LABEL_1676:
              if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
                goto LABEL_108;
              LODWORD(lpMultiByteStr) = 8555;
              bidTraceW(off_383B43280[0], 8760361, off_383B49128[0], 2147749405LL);
              ConversionSize = -2147217891;
              goto LABEL_56;
            }
            v31 = 49151;
            LOWORD(vt) = v391[0] & 0xBFFF;
            *(_DWORD *)v391 = vt;
            if ( !v38 )
              goto LABEL_1690;
            pvarVal = (VARIANTARG *)v38->int64;
            pvargSrc = pvarVal;
            v396 = pvarVal;
            v32 = *(_QWORD *)ui;
            *(_QWORD *)v401 = *(_QWORD *)ui;
            LOWORD(v26) = v387;
            break;
          default:
            goto LABEL_56;
        }
        goto LABEL_1540;
      }
      v313 = *((_WORD *)&pvargSrc->decVal + 9);
      v314 = *((_WORD *)&pvargSrc->decVal + 8);
      v315 = pvargSrc->decVal.Mid32;
      if ( !(unsigned int)IsValidTimeStampOffsetValue(
                            pvargSrc->vt,
                            pvargSrc->wReserved1,
                            pvargSrc->wReserved2,
                            pvargSrc->wReserved3,
                            pvargSrc->uiVal,
                            WORD1(pvargSrc->decVal.Lo64),
                            v315,
                            v314,
                            v313) )
        goto LABEL_1632;
      if ( v314 < 0 || (v386[0] = 1, v313 < 0) )
        v386[0] = 0;
      v405 = v315;
      if ( (a16 & 0x20) != 0 )
      {
        if ( Size < 0x1C )
          v316 = 0;
        else
          v316 = Size - 28;
        v381 = 9;
        v384[0] = 9;
        v317 = 9;
        if ( v316 < 9 )
          v317 = v316;
      }
      else
      {
        v317 = v381;
      }
      if ( !AdjustFractionalSeconds(&v405, v317) )
        goto LABEL_1633;
      v318 = abs16(v313);
      if ( v317 )
      {
        v401[0] = v318;
        v319 = abs16(*((_WORD *)&pvargSrc->decVal + 8));
        v320 = 45;
        if ( v386[0] )
          v320 = 43;
        LODWORD(v373) = v320;
        v321 = StringCchPrintfA(
                 (char *)sz,
                 0x104u,
                 "%04hi-%02hu-%02hu %02hu:%02hu:%02hu.%0*u %01c%02hu:%02hu",
                 (__int16)pvargSrc->vt,
                 pvargSrc->wReserved1,
                 pvargSrc->wReserved2,
                 pvargSrc->wReserved3,
                 pvargSrc->uiVal,
                 WORD1(pvargSrc->decVal.Lo64),
                 v317,
                 v405,
                 v373,
                 v319,
                 v401[0]);
      }
      else
      {
        v322 = abs16(*((_WORD *)&pvargSrc->decVal + 8));
        v323 = 45;
        if ( v386[0] )
          v323 = 43;
        LODWORD(v369) = v323;
        v321 = StringCchPrintfA(
                 (char *)sz,
                 0x104u,
                 "%04hi-%02hu-%02hu %02hu:%02hu:%02hu %01c%02hu:%02hu",
                 (__int16)pvargSrc->vt,
                 pvargSrc->wReserved1,
                 pvargSrc->wReserved2,
                 pvargSrc->wReserved3,
                 pvargSrc->uiVal,
                 WORD1(pvargSrc->decVal.Lo64),
                 v369,
                 v322,
                 v318);
      }
      v378 = v321;
      if ( v321 < 0 )
      {
LABEL_1633:
        *v380 = 2;
        ConversionSize = v378;
        goto LABEL_56;
      }
      v324 = -1;
      do
        ++v324;
      while ( *((_BYTE *)sz + v324) );
      cchWideChar = (unsigned __int16 *)v324;
      v27 = Source;
      ConversionSize = CopyToStr(sz, Source, v324, v383, Size, v380, v385);
      goto LABEL_1526;
    }
    if ( v36 == 21312 )
    {
      *v383 = 56;
      if ( v385 )
      {
        v258 = (char *)((__int64 (__fastcall *)(LPMALLOC, __int64, _QWORD, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                         g_pIMalloc,
                         56,
                         (unsigned __int16)vt,
                         v33);
        *(_QWORD *)v27 = v258;
        if ( !v258 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_383B49128[0] )
            {
              LODWORD(lpMultiByteStr) = 5072;
              bidTraceW(off_383B43280[0], 5193769, off_383B49128[0], 2147942414LL);
            }
LABEL_1203:
            ConversionSize = -2147024882;
            v38 = (CY *)v396;
            v381 = v384[0];
            goto LABEL_54;
          }
LABEL_1204:
          ConversionSize = -2147024882;
          goto LABEL_1526;
        }
        v27 = v258;
        Source = v258;
      }
      *(_QWORD *)v27 = 0;
      *((_QWORD *)v27 + 1) = 0;
      *((_QWORD *)v27 + 2) = 0;
      *((_QWORD *)v27 + 3) = 0;
      *((_QWORD *)v27 + 4) = 0;
      *((_QWORD *)v27 + 5) = 0;
      *((_QWORD *)v27 + 6) = 0;
      *(_WORD *)v27 = 0;
      v38 = (CY *)pvargSrc;
      if ( !pvargSrc->vt )
        *v380 = 2;
      ConversionSize = SSVariantCopy((struct SSVARIANT *)v27, (struct SSVARIANT *)pvargSrc, v380);
      v41 = v380;
      if ( pvargSrc->vt == 1 )
        *v380 = 3;
      goto LABEL_55;
    }
    if ( v36 <= 20728 )
    {
      if ( v36 >= 20727 )
      {
LABEL_248:
        *v383 = 0;
        ConversionSize = v378;
        goto LABEL_1526;
      }
      v33 = 0x383800000uLL;
      switch ( v36 )
      {
        case 19975:
LABEL_1057:
          v213 = pvargSrc->decVal.Mid32;
          v429 = v213;
          if ( (a16 & 0x20) != 0 )
          {
            if ( pvargSrc->wReserved3 > 0x17u
              || pvargSrc->iVal > 0x3Bu
              || WORD1(pvargSrc->decVal.Lo64) > 0x3Bu
              || v213 > 0x3B9AC9FF
              || !(unsigned int)IsValidSqlDateValue(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2) )
            {
              goto LABEL_1632;
            }
            if ( Size >> 1 < 0x15 )
              v214 = 0;
            else
              v214 = (Size >> 1) - 21;
            v381 = v213 != 0 ? 9 : 0;
            v384[0] = v381;
            v215 = v381;
            if ( v214 < v381 )
              v215 = v214;
          }
          else if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v406 + 43) + 40LL) + 880LL) == 80 )
          {
            v215 = v213 != 0 ? 9 : 0;
          }
          else
          {
            v215 = v381;
          }
          if ( !AdjustFractionalSeconds(&v429, v215) )
            goto LABEL_1633;
          if ( v215 )
          {
            LODWORD(v371) = v429;
            LODWORD(v369) = v215;
            LODWORD(p_wMilliseconds) = WORD1(pvargSrc->decVal.Lo64);
            LODWORD(lpUsedDefaultChar) = pvargSrc->uiVal;
            LODWORD(lpDefaultChar) = pvargSrc->wReserved3;
            LODWORD(cbMultiByte) = pvargSrc->wReserved2;
            LODWORD(lpMultiByteStr) = pvargSrc->wReserved1;
            v216 = StringCchPrintfW(
                     sz,
                     0x104u,
                     L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu.%0*u",
                     (unsigned int)(__int16)pvargSrc->vt,
                     lpMultiByteStr,
                     cbMultiByte,
                     lpDefaultChar,
                     lpUsedDefaultChar,
                     p_wMilliseconds,
                     v369);
            v38 = (CY *)pvargSrc;
          }
          else
          {
            v38 = (CY *)pvargSrc;
            LODWORD(p_wMilliseconds) = WORD1(pvargSrc->decVal.Lo64);
            LODWORD(lpUsedDefaultChar) = pvargSrc->uiVal;
            LODWORD(lpDefaultChar) = pvargSrc->wReserved3;
            LODWORD(cbMultiByte) = pvargSrc->wReserved2;
            LODWORD(lpMultiByteStr) = pvargSrc->wReserved1;
            v216 = StringCchPrintfW(
                     sz,
                     0x104u,
                     L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu",
                     (unsigned int)(__int16)pvargSrc->vt,
                     lpMultiByteStr,
                     cbMultiByte,
                     lpDefaultChar,
                     lpUsedDefaultChar,
                     p_wMilliseconds);
          }
          v378 = v216;
          if ( v216 < 0 )
            goto LABEL_1633;
          v199 = -1;
          do
            ++v199;
          while ( sz[v199] );
LABEL_1079:
          cchWideChar = (unsigned __int16 *)v199;
          v80 = FixupFromWstr(sz, (unsigned __int16 *)v199, v387, 0xFFFFFFFF, v27, v383, Size, v380, v385);
          break;
        case 19978:
          *v383 = 6;
          if ( pvargSrc->wReserved3 <= 0x17u
            && pvargSrc->iVal <= 0x3Bu
            && WORD1(pvargSrc->decVal.Lo64) <= 0x3Bu
            && pvargSrc->cyVal.Hi <= 0x3B9AC9FFu )
          {
            v217 = pvargSrc->vt;
            if ( (unsigned int)IsValidDateValue(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2) )
              goto LABEL_1085;
          }
          goto LABEL_1632;
        case 19979:
          *v383 = 6;
          v218 = pvargSrc->wReserved3;
          if ( v218 > 0x17u
            || pvargSrc->iVal > 0x3Bu
            || WORD1(pvargSrc->decVal.Lo64) > 0x3Bu
            || pvargSrc->cyVal.Hi > 0x3B9AC9FFu
            || !(unsigned int)IsValidDateValue(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2) )
          {
            goto LABEL_1632;
          }
          *(_WORD *)v27 = v218;
          v38 = (CY *)pvargSrc;
          *((_WORD *)v27 + 1) = pvargSrc->iVal;
          *((_WORD *)v27 + 2) = WORD1(pvargSrc->decVal.Lo64);
          ConversionSize = v378;
          goto LABEL_54;
        case 19980:
          *v383 = 16;
          v38 = (CY *)pvargSrc;
          if ( (a16 & 0x920) != 0x20 || !(pvargSrc->cyVal.Hi % (unsigned int)dword_3839128A0[v381]) )
            goto LABEL_584;
          goto LABEL_1658;
        case 19989:
          goto LABEL_1448;
        case 19990:
          *v383 = 12;
          v219 = pvargSrc->wReserved3;
          if ( v219 > 0x17u )
            goto LABEL_1632;
          if ( pvargSrc->iVal > 0x3Bu )
            goto LABEL_1632;
          if ( WORD1(pvargSrc->decVal.Lo64) > 0x3Bu )
            goto LABEL_1632;
          v220 = pvargSrc->decVal.Mid32;
          if ( v220 > 0x3B9AC9FF
            || !(unsigned int)IsValidSqlDateValue(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2) )
          {
            goto LABEL_1632;
          }
          if ( (a16 & 0x20) != 0 && v220 % dword_3839128A0[v381] )
            goto LABEL_1658;
          v221 = Source;
          *(_WORD *)Source = v219;
          v38 = (CY *)pvargSrc;
          v27 = v221;
          *((_WORD *)v221 + 1) = pvargSrc->iVal;
          *((_WORD *)v221 + 2) = WORD1(pvargSrc->decVal.Lo64);
          *((_DWORD *)v221 + 2) = pvargSrc->cyVal.Hi;
          *((_WORD *)v221 + 3) = 0;
          goto LABEL_586;
        case 19991:
          *v383 = 20;
          if ( pvargSrc->wReserved3 > 0x17u )
            goto LABEL_1632;
          if ( pvargSrc->iVal > 0x3Bu )
            goto LABEL_1632;
          if ( WORD1(pvargSrc->decVal.Lo64) > 0x3Bu )
            goto LABEL_1632;
          if ( pvargSrc->cyVal.Hi > 0x3B9AC9FFu )
            goto LABEL_1632;
          v222 = pvargSrc->vt;
          if ( !(unsigned int)IsValidSqlDateValue(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2) )
            goto LABEL_1632;
          *(_WORD *)v27 = v222;
          v38 = (CY *)pvargSrc;
          *((_WORD *)v27 + 1) = pvargSrc->wReserved1;
          *((_WORD *)v27 + 2) = pvargSrc->wReserved2;
          *((_WORD *)v27 + 3) = pvargSrc->wReserved3;
          *((_WORD *)v27 + 4) = pvargSrc->iVal;
          *((_WORD *)v27 + 5) = WORD1(pvargSrc->decVal.Lo64);
          lVal = pvargSrc->cyVal.Hi;
          v224 = a16;
          goto LABEL_1107;
        default:
          goto LABEL_1516;
      }
      goto LABEL_277;
    }
    switch ( v36 )
    {
      case 20735:
LABEL_48:
        *v383 = 8;
        if ( (_WORD)vt == 129 )
        {
          v37 = SysAllocStringLen(0, ui[0]);
          *(_QWORD *)v27 = v37;
          if ( !v37 )
            goto LABEL_1637;
          v38 = (CY *)pvargSrc;
          WStrFromStr = GetWStrFromStr(a14, (const char *)pvargSrc, *(unsigned __int64 *)ui, v37, &v397);
          v378 = WStrFromStr;
          if ( *(_QWORD *)ui != v397 && v397 )
            *(_DWORD *)(*(_QWORD *)v27 - 4LL) = 2 * v397;
          if ( WStrFromStr < 0 )
          {
            ConversionSize = WStrFromStr;
            goto LABEL_1179;
          }
        }
        else
        {
          v38 = (CY *)pvargSrc;
          *(_QWORD *)v27 = SysAllocStringLen(&pvargSrc->vt, *(_QWORD *)ui >> 1);
        }
        if ( !*(_QWORD *)v27 )
        {
LABEL_1637:
          if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
            goto LABEL_1569;
          LODWORD(lpMultiByteStr) = 4343;
          bidTraceW(off_383B43280[0], 4447273, off_383B49128[0], 2147942414LL);
          ConversionSize = -2147024882;
          goto LABEL_56;
        }
        ConversionSize = v378;
        goto LABEL_54;
      case 20739:
LABEL_1110:
        *v383 = 24;
        VariantInit((VARIANTARG *)v27);
        v38 = (CY *)pvargSrc;
        if ( v391[0] == 129 )
        {
          ConversionSize = GetWStrFromStr(
                             a14,
                             (const char *)pvargSrc,
                             *(unsigned __int64 *)ui,
                             (unsigned __int16 *)lpsz,
                             &v397);
          if ( ConversionSize < 0 )
            goto LABEL_1179;
          *(_QWORD *)ui = 2 * v397;
        }
        else
        {
          ConversionSize = v378;
        }
        *(_WORD *)v27 = 8;
        p_vt = &pvargSrc->vt;
        if ( lpsz )
          p_vt = lpsz;
        v226 = SysAllocStringLen(p_vt, *(_QWORD *)ui >> 1);
        *((_QWORD *)v27 + 1) = v226;
        if ( !v226 )
        {
          if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
            goto LABEL_1569;
          LODWORD(lpMultiByteStr) = 1773;
          bidTraceW(off_383B43280[0], 1815593, off_383B49128[0], 2147942414LL);
          ConversionSize = -2147024882;
          goto LABEL_56;
        }
        goto LABEL_1526;
      case 20855:
      case 20868:
        if ( (a16 & 0x240) != 0x40 )
        {
LABEL_1192:
          *v383 = v32;
          if ( v385 )
          {
            v255 = *(_QWORD *)ui;
            Size = *(_QWORD *)ui;
            v256 = (char *)((__int64 (__fastcall *)(LPMALLOC, _QWORD, _QWORD, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                             g_pIMalloc,
                             *(_QWORD *)ui,
                             (unsigned __int16)vt,
                             v33);
            *(_QWORD *)v27 = v256;
            if ( !v256 )
            {
              if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
                goto LABEL_1569;
              LODWORD(lpMultiByteStr) = 5394;
              bidTraceW(off_383B43280[0], 5523497, off_383B49128[0], 2147942414LL);
              ConversionSize = -2147024882;
              goto LABEL_56;
            }
            v27 = v256;
            Source = v256;
          }
          else
          {
            v255 = Size;
          }
          v252 = *(_QWORD *)ui;
          v251 = v27;
          if ( v255 >= *(_QWORD *)ui )
            goto LABEL_1187;
          *v380 = 4;
          v257 = v255;
          v38 = (CY *)pvargSrc;
          memcpy(v27, pvargSrc, v257);
          ConversionSize = v378;
          goto LABEL_54;
        }
        *v383 = v32 + 2;
        if ( v385 )
        {
          v249 = v32 + 2;
          Size = v32 + 2;
          v250 = (char *)((__int64 (__fastcall *)(LPMALLOC, unsigned __int64, _QWORD, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                           g_pIMalloc,
                           v32 + 2,
                           (unsigned __int16)vt,
                           v33);
          *(_QWORD *)v27 = v250;
          if ( !v250 )
          {
            if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
              goto LABEL_1569;
            LODWORD(lpMultiByteStr) = 5344;
            bidTraceW(off_383B43280[0], 5472297, off_383B49128[0], 2147942414LL);
            ConversionSize = -2147024882;
            goto LABEL_56;
          }
          v27 = v250;
          Source = v250;
        }
        else
        {
          v249 = Size;
        }
        if ( *(_QWORD *)ui + 2LL <= v249 )
        {
          *v27 = -1;
          v27[1] = -2;
          v251 = v27 + 2;
          v252 = *(_QWORD *)ui;
LABEL_1187:
          v38 = (CY *)pvargSrc;
          memcpy(v251, pvargSrc, v252);
          ConversionSize = v378;
          goto LABEL_54;
        }
        *v380 = 4;
        v253 = 2;
        if ( v249 < 2 )
          v253 = v249;
        memcpy(v27, qword_383866850, v253);
        if ( v249 > 2 )
        {
          v254 = v249 - 2;
          v38 = (CY *)pvargSrc;
          memcpy(v27 + 2, pvargSrc, v254);
          ConversionSize = v378;
          goto LABEL_54;
        }
        break;
      case 20856:
        goto LABEL_1148;
      case 20857:
        goto LABEL_1121;
      default:
        goto LABEL_1516;
    }
LABEL_238:
    ConversionSize = v378;
LABEL_1526:
    v38 = (CY *)pvargSrc;
    goto LABEL_54;
  }
  if ( v36 == 2483 )
  {
LABEL_498:
    *v383 = 19;
    *(_QWORD *)v27 = 0;
    *((_QWORD *)v27 + 1) = 0;
    *((_WORD *)v27 + 8) = 0;
    v27[18] = 0;
    v38 = (CY *)pvargSrc;
    if ( (_WORD)vt == 17 || SLOBYTE(pvargSrc->vt) >= 0 )
    {
      v27[2] = 1;
      v100 = pvargSrc->vt;
    }
    else
    {
      v100 = -LOBYTE(pvargSrc->vt);
    }
    v27[3] = v100;
    goto LABEL_385;
  }
  if ( v36 <= 1012 )
  {
    if ( v36 >= 1011 )
    {
LABEL_340:
      pbstrOut = 0;
      v38 = (CY *)pvargSrc;
      ConversionSize = VarBstrFromCy(*(CY *)&pvargSrc->vt, 0x409u, 0, &pbstrOut);
      if ( ConversionSize >= 0 )
      {
        v80 = FixupFromBstr(pbstrOut, v387, CodePage, v27, v383, Size, v380, v385);
        goto LABEL_277;
      }
      goto LABEL_1179;
    }
    if ( v36 > 718 )
    {
      v33 = 0x383800000uLL;
      switch ( v36 )
      {
        case 719:
        case 721:
        case 722:
        case 723:
        case 866:
        case 868:
        case 869:
        case 870:
          goto LABEL_1291;
        case 732:
        case 879:
          goto LABEL_1448;
        case 735:
        case 736:
        case 882:
        case 883:
          goto LABEL_248;
        case 737:
          goto LABEL_349;
        case 738:
          goto LABEL_355;
        case 739:
          goto LABEL_359;
        case 740:
          goto LABEL_360;
        case 741:
          goto LABEL_362;
        case 742:
          v38 = (CY *)pvargSrc;
          ConversionSize = IsValidDate(*(double *)&pvargSrc->vt, v380);
          goto LABEL_361;
        case 743:
        case 864:
        case 865:
          v38 = (CY *)pvargSrc;
          v80 = DoubleToChar(*(double *)&pvargSrc->vt, 17, v26, v27, v383, Size, v380, v385);
          goto LABEL_277;
        case 746:
          goto LABEL_353;
        case 747:
        case 894:
          goto LABEL_468;
        case 749:
          goto LABEL_363;
        case 751:
          goto LABEL_345;
        case 752:
          goto LABEL_346;
        case 753:
          goto LABEL_350;
        case 754:
          goto LABEL_356;
        case 755:
          v38 = (CY *)pvargSrc;
          goto LABEL_313;
        case 756:
          v38 = (CY *)pvargSrc;
          if ( *(double *)&pvargSrc->vt < 0.0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
LABEL_313:
          *v383 = 8;
          v85 = VarDecFromR8(*(DOUBLE *)&v38->int64, &pdecOut);
          goto LABEL_314;
        case 884:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          v80 = VarI2FromCy(*(CY *)&pvargSrc->vt, (SHORT *)v27);
          goto LABEL_277;
        case 885:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          v80 = VarI4FromCy(*(CY *)&pvargSrc->vt, (LONG *)v27);
          goto LABEL_277;
        case 886:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          v80 = VarR4FromCy(*(CY *)&pvargSrc->vt, (FLOAT *)v27);
          goto LABEL_277;
        case 887:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          v80 = VarR8FromCy(*(CY *)&pvargSrc->vt, (DOUBLE *)v27);
          goto LABEL_277;
        case 888:
LABEL_546:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          *(_QWORD *)v27 = *(_QWORD *)&pvargSrc->vt;
          ConversionSize = v378;
          goto LABEL_54;
        case 889:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          v80 = VarDateFromCy(*(CY *)&pvargSrc->vt, (DATE *)v27);
          goto LABEL_277;
        case 890:
          goto LABEL_340;
        case 893:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          v80 = VarBoolFromCy(*(CY *)&pvargSrc->vt, (VARIANT_BOOL *)v27);
          goto LABEL_277;
        case 896:
          *v383 = 16;
          v38 = (CY *)pvargSrc;
          v79 = VarDecFromCy(*(CY *)&pvargSrc->vt, (DECIMAL *)v27);
          goto LABEL_275;
        case 898:
          *v383 = 1;
          v38 = (CY *)pvargSrc;
          v80 = VarI1FromCy(*(CY *)&pvargSrc->vt, v27);
          goto LABEL_277;
        case 899:
          *v383 = 1;
          v38 = (CY *)pvargSrc;
          if ( *(__int64 *)&pvargSrc->vt < 0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          v80 = VarUI1FromCy(*(CY *)&pvargSrc->vt, v27);
          goto LABEL_277;
        case 900:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          if ( *(__int64 *)&pvargSrc->vt < 0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          v80 = VarUI2FromCy(*(CY *)&pvargSrc->vt, (USHORT *)v27);
          goto LABEL_277;
        case 901:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          if ( *(__int64 *)&pvargSrc->vt < 0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          v80 = VarUI4FromCy(*(CY *)&pvargSrc->vt, (ULONG *)v27);
          goto LABEL_277;
        case 902:
          v38 = (CY *)pvargSrc;
          goto LABEL_330;
        case 903:
          v38 = (CY *)pvargSrc;
          if ( *(__int64 *)&pvargSrc->vt < 0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
LABEL_330:
          *v383 = 8;
          v85 = VarDecFromCy(*v38, &pdecOut);
LABEL_314:
          ConversionSize = v85;
          if ( v85 >= 0 )
          {
            v86 = v387;
            p_pdecOut = &pdecOut;
            goto LABEL_316;
          }
          break;
        default:
          goto LABEL_1516;
      }
      goto LABEL_1179;
    }
    if ( v36 >= 717 )
    {
LABEL_305:
      v38 = (CY *)pvargSrc;
      v83 = *(float *)&pvargSrc->vt;
      if ( COERCE_DOUBLE(*(_QWORD *)&v83 & _xmm) >= 3.402823466385289e38
        || (v84 = 8, COERCE_DOUBLE(*(_QWORD *)&v83 & _xmm) <= 1.175494350822288e-38) )
      {
        v84 = 10;
      }
      v80 = DoubleToChar(v83, v84, v26, v27, v383, Size, v380, v385);
      goto LABEL_277;
    }
    if ( v36 > 425 )
    {
      v33 = 0x383800000uLL;
      switch ( v36 )
      {
        case 438:
        case 585:
          goto LABEL_1448;
        case 441:
        case 442:
        case 588:
        case 589:
          goto LABEL_248;
        case 453:
        case 600:
          goto LABEL_468;
        case 455:
          *v383 = 16;
          v38 = (CY *)pvargSrc;
          v79 = VarDecFromI4(*(_DWORD *)&pvargSrc->vt, (DECIMAL *)v27);
          goto LABEL_275;
        case 572:
LABEL_519:
          *v383 = 19;
          *(_QWORD *)v27 = 0;
          *((_QWORD *)v27 + 1) = 0;
          *((_WORD *)v27 + 8) = 0;
          v27[18] = 0;
          v38 = (CY *)pvargSrc;
          if ( (_WORD)vt == 19 || *(int *)&pvargSrc->vt >= 0 )
          {
            v27[2] = 1;
            v102 = *(_DWORD *)&pvargSrc->vt;
          }
          else
          {
            v102 = -*(_DWORD *)&pvargSrc->vt;
          }
          *(_DWORD *)(v27 + 3) = v102;
          v34 = 4;
          goto LABEL_385;
        case 590:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          ConversionSize = VarI2FromR4(*(FLOAT *)&pvargSrc->vt, (SHORT *)v27);
          goto LABEL_54;
        case 591:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          ConversionSize = VarI4FromR4(*(FLOAT *)&pvargSrc->vt, (LONG *)v27);
          goto LABEL_54;
        case 592:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          *(_DWORD *)v27 = *(_DWORD *)&pvargSrc->vt;
          ConversionSize = v378;
          goto LABEL_54;
        case 593:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          *(double *)v27 = *(float *)&pvargSrc->vt;
          ConversionSize = v378;
          goto LABEL_54;
        case 594:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          ConversionSize = VarCyFromR4(*(FLOAT *)&pvargSrc->vt, (CY *)v27);
          goto LABEL_54;
        case 595:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          v82 = *(float *)&pvargSrc->vt;
          *(double *)v27 = v82;
          v80 = IsValidDate(v82, v380);
          goto LABEL_277;
        case 596:
          goto LABEL_305;
        case 599:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          if ( *(float *)&pvargSrc->vt != 0.0 )
            goto LABEL_288;
          v81 = 0;
          goto LABEL_289;
        case 602:
          *v383 = 16;
          v38 = (CY *)pvargSrc;
          v79 = VarDecFromR4(*(FLOAT *)&pvargSrc->vt, (DECIMAL *)v27);
          goto LABEL_275;
        case 604:
          *v383 = 1;
          v38 = (CY *)pvargSrc;
          ConversionSize = VarI1FromR4(*(FLOAT *)&pvargSrc->vt, v27);
          goto LABEL_54;
        case 605:
          *v383 = 1;
          v38 = (CY *)pvargSrc;
          if ( *(float *)&pvargSrc->vt < 0.0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          ConversionSize = VarUI1FromR4(*(FLOAT *)&pvargSrc->vt, v27);
          goto LABEL_54;
        case 606:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          if ( *(float *)&pvargSrc->vt < 0.0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          ConversionSize = VarUI2FromR4(*(FLOAT *)&pvargSrc->vt, (USHORT *)v27);
          goto LABEL_54;
        case 607:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          if ( *(float *)&pvargSrc->vt < 0.0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          ConversionSize = VarUI4FromR4(*(FLOAT *)&pvargSrc->vt, (ULONG *)v27);
          goto LABEL_54;
        case 608:
          v38 = (CY *)pvargSrc;
          goto LABEL_298;
        case 609:
          v38 = (CY *)pvargSrc;
          if ( *(float *)&pvargSrc->vt < 0.0 )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
LABEL_298:
          *v383 = 8;
          ConversionSize = VarDecFromR4(*(FLOAT *)&v38->Lo, &pdecOut);
          if ( ConversionSize < 0 )
            goto LABEL_1179;
          ConversionSize = _VarI8FromDec(&pdecOut, v387, (__int64 *)v27, v380);
          break;
        default:
          goto LABEL_1516;
      }
      goto LABEL_54;
    }
    if ( v36 == 425 )
      goto LABEL_511;
    if ( v36 < 294 )
      goto LABEL_1516;
    if ( v36 <= 295 )
      goto LABEL_399;
    if ( v36 != 306 )
    {
      if ( v36 == 308 )
      {
LABEL_411:
        *v383 = 16;
        v38 = (CY *)pvargSrc;
        v79 = VarDecFromI2(pvargSrc->vt, (DECIMAL *)v27);
        goto LABEL_275;
      }
      goto LABEL_1516;
    }
LABEL_468:
    v430 = 1;
    *v383 = 24;
    v519 = 24;
    Src = v27;
    VariantInit((VARIANTARG *)v27);
    vt = *(_DWORD *)v391;
    LOWORD(v26) = v391[0];
    v387 = v391[0];
    *(_WORD *)v27 = v391[0];
    Source = v27 + 8;
    v383 = (unsigned __int64 *)&v528;
    v32 = *(_QWORD *)ui;
    *(_QWORD *)v401 = *(_QWORD *)ui;
    pvarVal = pvargSrc;
LABEL_1539:
    v31 = 49151;
    goto LABEL_1540;
  }
  if ( v36 <= 1304 )
  {
    if ( v36 == 1304 )
    {
LABEL_917:
      if ( (_WORD)vt == 129 )
        goto LABEL_922;
      if ( (_WORD)vt != 8 )
      {
LABEL_921:
        v32 >>= 1;
LABEL_922:
        v397 = v32;
        v188 = v383;
        *v383 = v32 >> 1;
        if ( (v32 & 1) != 0 )
        {
          v397 = --v32;
          *v380 = 4;
        }
        v38 = (CY *)pvargSrc;
        if ( (_WORD)vt == 129 )
        {
          v189 = GetWStrFromStr(a14, (const char *)pvargSrc, *(unsigned __int64 *)ui, (unsigned __int16 *)lpsz, 0);
        }
        else
        {
          if ( (_WORD)vt != 130 )
          {
LABEL_930:
            v190 = v385;
            if ( !v385 )
            {
              v192 = v527;
LABEL_934:
              v193 = Size;
              if ( Size < *v383 )
              {
                *v380 = 4;
                v32 = 2 * v193;
                v397 = 2 * v193;
              }
              v194 = &pvargSrc->vt;
              if ( lpsz )
                v194 = lpsz;
              v195 = v27;
              if ( v32 )
              {
                while ( 1 )
                {
                  v196 = *v194;
                  if ( !*v194 )
                    break;
                  v393 = *v194;
                  v197 = v196 - 48;
                  if ( (unsigned __int16)(v196 - 48) > 9u )
                  {
                    if ( (unsigned __int16)(v196 - 65) > 5u )
                    {
                      if ( (unsigned __int16)(v196 - 97) > 5u )
                        break;
                      v196 -= 87;
                      v393 = v196;
                    }
                    else
                    {
                      v196 -= 55;
                      v393 = v196;
                    }
                  }
                  else
                  {
                    LOBYTE(v196) = v196 - 48;
                    v393 = v197;
                  }
                  *v195 = 16 * v196;
                  v393 = v194[1];
                  v194 += 2;
                  if ( (unsigned __int16)(v393 - 48) > 9u )
                  {
                    if ( (unsigned __int16)(v393 - 65) > 5u )
                    {
                      if ( (unsigned __int16)(v393 - 97) > 5u )
                        break;
                      v198 = v393 - 87;
                    }
                    else
                    {
                      v198 = v393 - 55;
                    }
                    v393 = v198;
                  }
                  else
                  {
                    LOBYTE(v198) = v393 - 48;
                    v393 -= 48;
                  }
                  *v195 |= v198;
                  v32 -= 2LL;
                  v397 = v32;
                  ++v195;
                  if ( !v32 )
                  {
                    ConversionSize = v378;
                    goto LABEL_1526;
                  }
                }
                if ( v190 )
                  ((void (__fastcall *)(LPMALLOC, char *, _BYTE *))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, v192, v195);
                v41 = v380;
                *v380 = 2;
                ConversionSize = v378;
                goto LABEL_614;
              }
              goto LABEL_238;
            }
            Size = *v188;
            v191 = (char *)((__int64 (__fastcall *)(LPMALLOC, size_t, __int64, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                             g_pIMalloc,
                             Size,
                             v35,
                             v33);
            v192 = v191;
            v527 = v191;
            *(_QWORD *)v27 = v191;
            if ( v191 )
            {
              v27 = v191;
              Source = v191;
              v190 = v385;
              goto LABEL_934;
            }
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
            {
              LODWORD(lpMultiByteStr) = 4760;
              bidTraceW(off_383B43280[0], 4874281, off_383B49128[0], 2147942414LL);
              ConversionSize = -2147024882;
              goto LABEL_56;
            }
LABEL_1569:
            ConversionSize = -2147024882;
            goto LABEL_56;
          }
          v189 = CopyWstr(&pvargSrc->vt, *(size_t *)ui, (unsigned __int16 *)lpsz);
        }
        v378 = v189;
        if ( v189 < 0 )
        {
          ConversionSize = v189;
          goto LABEL_1179;
        }
        v188 = v383;
        goto LABEL_930;
      }
      v187 = *(OLECHAR **)&pvargSrc->vt;
      pvargSrc = (VARIANTARG *)v187;
      if ( v187 )
      {
        v32 = SysStringByteLen(v187);
        *(_QWORD *)ui = v32;
        LOWORD(vt) = v391[0];
        goto LABEL_921;
      }
      if ( (bidGblFlags & 2) == 0 || (v351 = off_383B43280[0], !off_383B49128[0]) )
      {
LABEL_1696:
        ConversionSize = -2147467259;
        goto LABEL_56;
      }
      LODWORD(lpMultiByteStr) = 4710;
      v352 = 4823081;
LABEL_1695:
      bidTraceW(v351, v352, off_383B49128[0], 2147500037LL);
      goto LABEL_1696;
    }
    v33 = 0x383800000uLL;
    switch ( v36 )
    {
      case 1013:
        *v383 = 19;
        *(_QWORD *)v27 = 0;
        *((_QWORD *)v27 + 1) = 0;
        *((_WORD *)v27 + 8) = 0;
        v27[18] = 0;
        v27[1] = 4;
        v38 = (CY *)pvargSrc;
        if ( *(__int64 *)&pvargSrc->vt < 0 )
        {
          v92 = -*(_QWORD *)&pvargSrc->vt;
        }
        else
        {
          v27[2] = 1;
          v92 = *(_QWORD *)&pvargSrc->vt;
        }
        v34 = 12;
        goto LABEL_384;
      case 1026:
      case 1173:
        goto LABEL_1448;
      case 1029:
      case 1030:
      case 1176:
      case 1177:
        goto LABEL_248;
      case 1031:
LABEL_349:
        *v383 = 2;
        v38 = (CY *)pvargSrc;
        v80 = VarI2FromR8(*(DOUBLE *)&pvargSrc->vt, (SHORT *)v27);
        goto LABEL_277;
      case 1032:
LABEL_355:
        *v383 = 4;
        v38 = (CY *)pvargSrc;
        v80 = VarI4FromR8(*(DOUBLE *)&pvargSrc->vt, (LONG *)v27);
        goto LABEL_277;
      case 1033:
LABEL_359:
        *v383 = 4;
        v38 = (CY *)pvargSrc;
        v80 = VarR4FromR8(*(DOUBLE *)&pvargSrc->vt, (FLOAT *)v27);
        goto LABEL_277;
      case 1034:
      case 1036:
LABEL_360:
        v38 = (CY *)pvargSrc;
        ConversionSize = v378;
LABEL_361:
        *v383 = 8;
        *(CY *)v27 = *v38;
        goto LABEL_54;
      case 1035:
LABEL_362:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        v80 = VarCyFromR8(*(DOUBLE *)&pvargSrc->vt, (CY *)v27);
        goto LABEL_277;
      case 1037:
      case 1158:
      case 1159:
        v38 = (CY *)pvargSrc;
        if ( (a16 & 0x20) == 0 )
        {
          v515 = 0;
          ConversionSize = VarBstrFromDate(*(DATE *)&pvargSrc->vt, 0x409u, 0, &v515);
          if ( ConversionSize < 0 )
            goto LABEL_1179;
          v80 = FixupFromBstr(v515, v387, CodePage, v27, v383, Size, v380, v385);
          goto LABEL_277;
        }
        if ( *(double *)&pvargSrc->vt >= 2958466.0 || !(unsigned int)TmFromOleDate(*(double *)&pvargSrc->vt, &v399) )
        {
          v41 = v380;
          *v380 = 2;
          ConversionSize = v378;
          goto LABEL_55;
        }
        LODWORD(lpDefaultChar) = v399.tm_hour;
        LODWORD(cbMultiByte) = v399.tm_mday;
        LODWORD(lpMultiByteStr) = v399.tm_mon;
        if ( (_WORD)v387 == 129 )
        {
          StringCchPrintfA(
            (char *)sz,
            0x208u,
            "%04hi-%02hu-%02hu %02hu:%02hu:%02hu",
            v399.tm_year,
            v399.tm_mon,
            v399.tm_mday,
            v399.tm_hour,
            v399.tm_min,
            v399.tm_sec);
          v88 = -1;
          do
            ++v88;
          while ( *((_BYTE *)sz + v88) );
          cchWideChar = (unsigned __int16 *)v88;
          v89 = v380;
          v90 = CopyToStr(sz, v27, v88, v383, Size, v380, v385);
        }
        else
        {
          StringCchPrintfW(
            sz,
            0x104u,
            L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu",
            (unsigned int)v399.tm_year,
            lpMultiByteStr,
            cbMultiByte,
            lpDefaultChar);
          v91 = -1;
          do
            ++v91;
          while ( sz[v91] );
          cchWideChar = (unsigned __int16 *)v91;
          v89 = v380;
          v90 = FixupFromWstr(sz, (unsigned __int16 *)v91, v387, CodePage, v27, v383, Size, v380, v385);
        }
        v378 = v90;
        if ( v90 < 0 )
        {
          ConversionSize = v90;
          goto LABEL_1179;
        }
        if ( *v89 != 4 )
          goto LABEL_1173;
        *v89 = 2;
        ConversionSize = v90;
        goto LABEL_54;
      case 1040:
LABEL_353:
        *v383 = 2;
        v38 = (CY *)pvargSrc;
        if ( *(double *)&pvargSrc->vt == 0.0 )
          v81 = 0;
        else
LABEL_288:
          v81 = -1;
LABEL_289:
        *(_WORD *)v27 = v81;
LABEL_290:
        ConversionSize = v378;
        goto LABEL_54;
      case 1041:
      case 1188:
        goto LABEL_468;
      case 1043:
LABEL_363:
        *v383 = 16;
        v38 = (CY *)pvargSrc;
        v79 = VarDecFromR8(*(DOUBLE *)&pvargSrc->vt, (DECIMAL *)v27);
        goto LABEL_275;
      case 1045:
LABEL_345:
        *v383 = 1;
        v38 = (CY *)pvargSrc;
        v80 = VarI1FromR8(*(DOUBLE *)&pvargSrc->vt, v27);
        goto LABEL_277;
      case 1046:
LABEL_346:
        *v383 = 1;
        v38 = (CY *)pvargSrc;
        if ( *(double *)&pvargSrc->vt < 0.0 )
        {
          v41 = v380;
          *v380 = 5;
          ConversionSize = v378;
          goto LABEL_55;
        }
        v80 = VarUI1FromR8(*(DOUBLE *)&pvargSrc->vt, v27);
        goto LABEL_277;
      case 1047:
LABEL_350:
        *v383 = 2;
        v38 = (CY *)pvargSrc;
        if ( *(double *)&pvargSrc->vt < 0.0 )
        {
          v41 = v380;
          *v380 = 5;
          ConversionSize = v378;
          goto LABEL_55;
        }
        v80 = VarUI2FromR8(*(DOUBLE *)&pvargSrc->vt, (USHORT *)v27);
        goto LABEL_277;
      case 1048:
LABEL_356:
        *v383 = 4;
        v38 = (CY *)pvargSrc;
        if ( *(double *)&pvargSrc->vt < 0.0 )
        {
          v41 = v380;
          *v380 = 5;
          ConversionSize = v378;
          goto LABEL_55;
        }
        v80 = VarUI4FromR8(*(DOUBLE *)&pvargSrc->vt, (ULONG *)v27);
        goto LABEL_277;
      case 1049:
      case 1050:
      case 1162:
      case 1164:
      case 1174:
      case 1175:
        goto LABEL_1291;
      case 1178:
LABEL_615:
        *v383 = 2;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v80 = VarI2FromStr(lpsz, 0x409u, 0, (SHORT *)v27);
        goto LABEL_277;
      case 1179:
LABEL_621:
        *v383 = 4;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v80 = VarI4FromStr(lpsz, 0x409u, 0, (LONG *)v27);
        goto LABEL_277;
      case 1180:
LABEL_627:
        *v383 = 4;
        v38 = (CY *)pvargSrc;
        WStrFromSrc = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        v378 = WStrFromSrc;
        if ( WStrFromSrc >= 0 )
        {
          WStrFromSrc = VarR4FromStr(lpsz, 0x409u, 0, (FLOAT *)v27);
          v378 = WStrFromSrc;
        }
        if ( WStrFromSrc != -2147352571 )
          goto LABEL_389;
        v80 = VarR4FromStr(lpsz, 0x400u, 0, (FLOAT *)v27);
        goto LABEL_277;
      case 1181:
LABEL_631:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        v121 = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        v378 = v121;
        if ( v121 >= 0 )
        {
          v121 = VarR8FromStr(lpsz, 0x409u, 0, (DOUBLE *)v27);
          v378 = v121;
        }
        if ( v121 != -2147352571 )
          goto LABEL_389;
        v80 = VarR8FromStr(lpsz, 0x400u, 0, (DOUBLE *)v27);
        goto LABEL_277;
      case 1182:
LABEL_635:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        v122 = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        v378 = v122;
        if ( v122 >= 0 )
        {
          v122 = VarCyFromStr(lpsz, 0x409u, 0, (CY *)v27);
          v378 = v122;
        }
        if ( v122 != -2147352571 )
          goto LABEL_389;
        v80 = VarCyFromStr(lpsz, 0x400u, 0, (CY *)v27);
        goto LABEL_277;
      case 1183:
LABEL_648:
        *v383 = 8;
        v464 = 0;
        v465 = 1;
        v466 = 0;
        v467 = 0;
        v468 = 0;
        v469 = 0;
        v470 = 0;
        v471 = 0;
        v459 = 0;
        v460 = 0;
        v461 = 0;
        v462 = 0;
        v463 = 0;
        v38 = (CY *)pvargSrc;
        switch ( (unsigned __int16)vt )
        {
          case 8u:
            v466 = SysStringLen(*(BSTR *)&pvargSrc->vt);
            v464 = *(VARIANTARG **)&pvargSrc->vt;
            break;
          case 0x81u:
            v466 = *(_QWORD *)ui;
            v464 = pvargSrc;
            v465 = 0;
            goto LABEL_655;
          case 0x82u:
            v466 = *(_QWORD *)ui >> 1;
            v464 = pvargSrc;
            break;
          default:
            goto LABEL_655;
        }
        v465 = 1;
LABEL_655:
        CDateTimeParser::Parse((CDateTimeParser *)&v459);
        v124 = v470 & 0xFFBF;
        if ( (v470 & 0xFFBF) == 0x23F || v124 == 959 || v124 == 519 || v124 == 568 )
        {
          CDateTimeParser::CheckDefaultDate((CDateTimeParser *)&v459, a16 & 0x100);
          if ( (unsigned __int16)v459 >= 0x64u )
          {
            if ( (unsigned int)OleDateFromTm(
                                 v459,
                                 HIWORD(v459),
                                 v460,
                                 HIWORD(v460),
                                 v461,
                                 HIWORD(v461),
                                 v462 / 0xF4240,
                                 (double *)v27) )
              goto LABEL_802;
          }
        }
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, v391[0], *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v80 = VarDateFromStr(lpsz, 0x400u, 0, (DATE *)v27);
        goto LABEL_277;
      case 1184:
        *v383 = 8;
        v38 = *(CY **)&pvargSrc->vt;
        if ( *(_QWORD *)&pvargSrc->vt )
        {
          v93 = SysStringByteLen(*(BSTR *)&pvargSrc->vt);
          *(_QWORD *)ui = v93;
          v397 = (unsigned __int64)v93 >> 1;
          v94 = SysAllocStringLen((const OLECHAR *)v38, v93 >> 1);
          *(_QWORD *)v27 = v94;
          if ( !v94 )
          {
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
            {
              LODWORD(lpMultiByteStr) = 4372;
              bidTraceW(off_383B43280[0], 4476969, off_383B49128[0], 2147942414LL);
              ConversionSize = -2147024882;
              goto LABEL_56;
            }
            goto LABEL_1569;
          }
LABEL_389:
          ConversionSize = v378;
          goto LABEL_54;
        }
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_1696;
        v351 = off_383B43280[0];
        if ( !off_383B49128[0] )
          goto LABEL_1696;
        LODWORD(lpMultiByteStr) = 4356;
        v352 = 4460585;
        goto LABEL_1695;
      case 1187:
LABEL_619:
        *v383 = 2;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v80 = VarBoolFromStr(lpsz, 0x409u, 0, (VARIANT_BOOL *)v27);
        goto LABEL_277;
      case 1190:
LABEL_639:
        *v383 = 16;
        v38 = (CY *)pvargSrc;
        v123 = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        v378 = v123;
        if ( v123 >= 0 )
        {
          v123 = VarDecFromStr(lpsz, 0x409u, 0, (DECIMAL *)v27);
          v378 = v123;
        }
        if ( v123 == -2147352571 )
          v378 = VarDecFromStr(lpsz, 0x400u, 0, (DECIMAL *)v27);
        if ( (a16 & 8) != 0 )
          goto LABEL_276;
        goto LABEL_389;
      case 1192:
LABEL_607:
        *v383 = 1;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v80 = VarI1FromStr(lpsz, 0x409u, 0, v27);
        goto LABEL_277;
      case 1193:
LABEL_609:
        *v383 = 1;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v118 = lpsz;
        v119 = VarUI1FromStr(lpsz, 0x409u, 0, v27);
        goto LABEL_611;
      case 1194:
LABEL_617:
        *v383 = 2;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v118 = lpsz;
        v119 = VarUI2FromStr(lpsz, 0x409u, 0, (USHORT *)v27);
        goto LABEL_611;
      case 1195:
LABEL_623:
        *v383 = 4;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v118 = lpsz;
        v119 = VarUI4FromStr(lpsz, 0x409u, 0, (ULONG *)v27);
LABEL_611:
        ConversionSize = v119;
        if ( v119 != -2147352566 || !(unsigned int)IsNegativeStr(v118) )
          goto LABEL_1526;
        v41 = v380;
        *v380 = 5;
        ConversionSize = 0;
        goto LABEL_614;
      case 1196:
      case 1197:
LABEL_625:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        if ( ConversionSize < 0 )
          goto LABEL_54;
        v80 = _VarI8FromStr(lpsz, v387, (__int64 *)v27, v380);
        goto LABEL_277;
      case 1240:
LABEL_783:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
        v378 = ConversionSize;
        if ( ConversionSize < 0 )
          goto LABEL_54;
        *(_QWORD *)&SystemTime.wYear = 0;
        *(_QWORD *)&SystemTime.wHour = 0;
        v371 = (unsigned __int8 *)2;
        v369 = (unsigned __int8 *)&v393;
        p_wMilliseconds = (unsigned int *)&SystemTime.wMilliseconds;
        lpUsedDefaultChar = (int *)&SystemTime.wSecond;
        lpDefaultChar = (VARIANTARG *)&SystemTime.wMinute;
        v139 = swscanf_s(
                 lpsz,
                 L"%5hd-%2hu-%2hu %2hu:%2hu:%2hu.%7hu%c",
                 &SystemTime,
                 &SystemTime.wMonth,
                 &SystemTime.wDay,
                 &SystemTime.wHour);
        if ( v139 == 8 )
        {
          if ( !iswspace(v393) )
            goto LABEL_805;
LABEL_788:
          v140 = lpsz;
          do
            v141 = *v140++;
          while ( v141 != 46 );
          wMilliseconds = 0;
          v143 = 3;
          v397 = 3;
          do
          {
            if ( iswdigit(*v140) )
              wMilliseconds = *v140++ + 10 * wMilliseconds - 48;
            else
              wMilliseconds *= 10;
            --v143;
          }
          while ( v143 );
          SystemTime.wMilliseconds = wMilliseconds;
          ConversionSize = v378;
          goto LABEL_799;
        }
        if ( v139 == 7 )
          goto LABEL_788;
        if ( v139 < 6 || v139 > 7 )
          goto LABEL_805;
        wMilliseconds = SystemTime.wMilliseconds;
LABEL_799:
        if ( !(unsigned int)IsValidFileTimeDateValue(
                              SystemTime.wYear,
                              SystemTime.wMonth,
                              SystemTime.wDay,
                              SystemTime.wHour,
                              SystemTime.wMinute,
                              SystemTime.wSecond,
                              wMilliseconds) )
        {
          v38 = (CY *)pvargSrc;
LABEL_805:
          ConversionSize = GetWStrFromSrc(a14, v38, v391[0], *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
          if ( ConversionSize >= 0
            && (ConversionSize = VarDateFromStr(lpsz, 0x400u, 0, &v525), ConversionSize >= 0)
            && v525 < 2958466.0
            && (unsigned int)TmFromOleDate(v525, &v399) )
          {
            SystemTime.wYear = v399.tm_year;
            SystemTime.wMonth = v399.tm_mon;
            SystemTime.wDay = v399.tm_mday;
            SystemTime.wHour = v399.tm_hour;
            SystemTime.wMinute = v399.tm_min;
            SystemTime.wSecond = v399.tm_sec;
            SystemTime.wMilliseconds = 0;
            v27 = Source;
            v145 = SystemTimeToFileTime(&SystemTime, (LPFILETIME)Source);
            v41 = v380;
            if ( !v145 )
              *v380 = 2;
          }
          else
          {
            v41 = v380;
            *v380 = 2;
            v27 = Source;
          }
          goto LABEL_55;
        }
        v27 = Source;
        v144 = SystemTimeToFileTime(&SystemTime, (LPFILETIME)Source);
        v41 = v380;
        if ( v144 )
          goto LABEL_803;
        *v380 = 2;
        v38 = (CY *)pvargSrc;
        goto LABEL_55;
      case 1248:
LABEL_902:
        *v383 = 16;
        if ( (_WORD)vt == 129 )
        {
          v183 = *(_QWORD *)ui;
          if ( *(_QWORD *)ui > 0x64u )
            v183 = 100;
          v397 = v183;
          v38 = (CY *)pvargSrc;
          v184 = GetWStrFromStr(a14, (const char *)pvargSrc, *(unsigned __int64 *)ui, (unsigned __int16 *)lpsz, 0);
        }
        else
        {
          if ( (_WORD)vt == 8 )
          {
            v185 = *(OLECHAR **)&pvargSrc->vt;
            pvargSrc = (VARIANTARG *)v185;
            if ( !v185 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_1696;
              v351 = off_383B43280[0];
              if ( !off_383B49128[0] )
                goto LABEL_1696;
              LODWORD(lpMultiByteStr) = 4656;
              v352 = 4767785;
              goto LABEL_1695;
            }
            v183 = SysStringLen(v185);
            *(_QWORD *)ui = v183;
            if ( v183 > 0x64 )
              v183 = 100;
            v397 = v183;
            lpsz = strIn;
            memcpy(strIn, v185, 2 * v183);
LABEL_916:
            v186 = lpsz;
            lpsz[v183] = 0;
            v27 = Source;
            ConversionSize = CLSIDFromString(v186, (LPCLSID)Source);
            goto LABEL_1526;
          }
          if ( *(_QWORD *)ui <= 0x64u )
          {
            v183 = *(_QWORD *)ui >> 1;
            v397 = *(_QWORD *)ui >> 1;
          }
          else
          {
            v183 = 100;
            v397 = 100;
          }
          v38 = (CY *)pvargSrc;
          v184 = CopyWstr(&pvargSrc->vt, *(size_t *)ui, (unsigned __int16 *)lpsz);
        }
        ConversionSize = v184;
        if ( v184 < 0 )
          goto LABEL_1179;
        goto LABEL_916;
      default:
        goto LABEL_1516;
    }
  }
  if ( v36 <= 1618 )
  {
    if ( v36 >= 1617 )
      goto LABEL_399;
    v33 = 0x383800000uLL;
    switch ( v36 )
    {
      case 1305:
LABEL_1148:
        v428 = 0;
        v38 = (CY *)pvargSrc;
        if ( (_WORD)vt == 8 )
        {
          v38 = *(CY **)&pvargSrc->vt;
          pvargSrc = (VARIANTARG *)v38;
          if ( !v38 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_1696;
            v351 = off_383B43280[0];
            if ( !off_383B49128[0] )
              goto LABEL_1696;
            LODWORD(lpMultiByteStr) = 4547;
            v352 = 4656169;
            goto LABEL_1695;
          }
          v237 = SysStringByteLen((BSTR)v38);
          *(_QWORD *)ui = v237;
          ConversionSize = v378;
        }
        else
        {
          ConversionSize = CopyWstr(&pvargSrc->vt, v32, (unsigned __int16 *)lpsz);
          if ( ConversionSize < 0 )
            goto LABEL_1179;
          v237 = *(_QWORD *)ui;
        }
        v238 = (const WCHAR *)v38;
        if ( lpsz )
          v238 = lpsz;
        v239 = WideCharToMultiByte(CodePage, 0, v238, v237 >> 1, 0, 0, 0, 0);
        v240 = v239;
        v397 = v239;
        *v383 = v239;
        v241 = v385;
        if ( v385 )
        {
          Size = v240 + 1;
          v242 = (char *)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, v240 + 1);
          *(_QWORD *)Source = v242;
          if ( !v242 )
          {
            if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
              goto LABEL_1569;
            LODWORD(lpMultiByteStr) = 4585;
            bidTraceW(off_383B43280[0], 4695081, off_383B49128[0], 2147942414LL);
            ConversionSize = -2147024882;
            goto LABEL_56;
          }
          v243 = v242;
          Source = v242;
          v241 = v385;
        }
        else
        {
          v243 = Source;
        }
        v244 = Size;
        if ( Size )
        {
          if ( CodePage >= 0xC42C )
          {
            v245 = IsW2CSpecialCodePage(CodePage);
            v244 = Size;
          }
          else
          {
            v245 = 0;
          }
          v246 = &v428;
          if ( v245 )
            v246 = 0;
          v247 = WideCharToMultiByte(CodePage, 0, v238, *(_QWORD *)ui >> 1, v243, v244 & 0x7FFFFFFF, 0, v246);
          v397 = v247;
          v248 = Size;
          if ( v247 == *v383 && Size > v247 )
          {
            v27 = Source;
            Source[v247] = 0;
            v41 = v380;
            v38 = (CY *)pvargSrc;
            if ( v428 )
              *v380 = 4;
            goto LABEL_55;
          }
          v41 = v380;
          *v380 = 4;
          v27 = Source;
          Source[v248 - 1] = 0;
        }
        else
        {
          v27 = Source;
          if ( v241 )
            ((void (__fastcall *)(LPMALLOC, char *))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, Source);
          v41 = v380;
          *v380 = 6;
        }
        goto LABEL_614;
      case 1306:
LABEL_1121:
        v38 = (CY *)pvargSrc;
        if ( (_WORD)vt == 8 )
        {
          v38 = *(CY **)&pvargSrc->vt;
          pvargSrc = (VARIANTARG *)v38;
          if ( !v38 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_1696;
            v351 = off_383B43280[0];
            if ( !off_383B49128[0] )
              goto LABEL_1696;
            LODWORD(lpMultiByteStr) = 4452;
            v352 = 4558889;
            goto LABEL_1695;
          }
          v227 = SysStringByteLen((BSTR)v38);
          *(_QWORD *)ui = v227;
          ConversionSize = v378;
        }
        else
        {
          *(_QWORD *)ui = v32 & 0xFFFFFFFFFFFFFFFEuLL;
          ConversionSize = CopyWstr(&pvargSrc->vt, v32 & 0xFFFFFFFFFFFFFFFEuLL, (unsigned __int16 *)lpsz);
          if ( ConversionSize < 0 )
            goto LABEL_1179;
          v227 = *(_QWORD *)ui;
        }
        *v383 = v227;
        v228 = v385;
        if ( v385 )
        {
          Size = *(_QWORD *)ui + 2LL;
          v229 = (char *)((__int64 (__fastcall *)(LPMALLOC))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc);
          *(_QWORD *)v27 = v229;
          if ( !v229 )
          {
            if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
              goto LABEL_1569;
            LODWORD(lpMultiByteStr) = 4484;
            bidTraceW(off_383B43280[0], 4591657, off_383B49128[0], 2147942414LL);
            ConversionSize = -2147024882;
            goto LABEL_56;
          }
          v27 = v229;
          Source = v229;
          v228 = v385;
        }
        v230 = Size;
        if ( Size < 2 )
        {
          if ( v228 )
            ((void (__fastcall *)(LPMALLOC, _BYTE *))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, v27);
          v41 = v380;
          *v380 = 6;
          goto LABEL_55;
        }
        if ( *(_QWORD *)ui + 2LL > Size )
        {
          *v380 = 4;
          v232 = (LPCOLESTR)v38;
          if ( lpsz )
            v232 = lpsz;
          v233 = v230 - 2;
          memcpy(Source, v232, v230 - 2);
          v234 = Size;
          if ( (a16 & 0x1000) != 0 && Size >= 4 )
          {
            v235 = v232[(Size >> 1) - 2];
            if ( v235 >= 0xD800u && v235 <= 0xDBFFu )
            {
              v236 = v232[(Size >> 1) - 1];
              if ( v236 >= 0xDC00u )
              {
                if ( v236 <= 0xDFFFu )
                  v234 = v233;
                Size = v234;
              }
            }
          }
          v27 = Source;
          *(_WORD *)&Source[2 * (v234 >> 1) - 2] = 0;
        }
        else
        {
          v231 = (LPCOLESTR)v38;
          if ( lpsz )
            v231 = lpsz;
          memcpy(v27, v231, *(size_t *)ui);
          *(_WORD *)&v27[2 * (*(_QWORD *)ui >> 1)] = 0;
        }
        goto LABEL_1526;
      case 1307:
LABEL_645:
        v38 = (CY *)pvargSrc;
        ConversionSize = GetWStrFromSrc(a14, pvargSrc, vt, v32, (unsigned __int16 **)&lpsz);
        if ( ConversionSize >= 0 )
        {
          *(_QWORD *)v27 = 0;
          *((_QWORD *)v27 + 1) = 0;
          *((_WORD *)v27 + 8) = 0;
          v27[18] = 0;
          ConversionSize = FastNumericFromStr(lpsz, (struct tagDB_NUMERIC *)v27, v383);
          *v383 = 19;
          if ( !ConversionSize )
            goto LABEL_386;
        }
        goto LABEL_54;
      case 1308:
        goto LABEL_917;
      case 1309:
LABEL_663:
        *v383 = 6;
        v490 = 0;
        v491 = 1;
        v492 = 0;
        v493 = 0;
        v494 = 0;
        v495 = 0;
        v496 = 0;
        v497 = 0;
        v485 = 0;
        v486 = 0;
        v487 = 0;
        v488 = 0;
        v489 = 0;
        v38 = (CY *)pvargSrc;
        switch ( (unsigned __int16)vt )
        {
          case 8u:
            v492 = SysStringLen(*(BSTR *)&pvargSrc->vt);
            v490 = *(VARIANTARG **)&pvargSrc->vt;
            break;
          case 0x81u:
            v492 = *(_QWORD *)ui;
            v490 = pvargSrc;
            v491 = 0;
            goto LABEL_670;
          case 0x82u:
            v492 = *(_QWORD *)ui >> 1;
            v490 = pvargSrc;
            break;
          default:
            goto LABEL_670;
        }
        v491 = 1;
LABEL_670:
        CDateTimeParser::Parse((CDateTimeParser *)&v485);
        if ( (v496 & 0x607) != 0x207 && v496 != 519 )
        {
          if ( (a16 & 0x100) == 0 || (v125 = v496 & 0xFFBF, v125 != 575) && v125 != 959 )
          {
            ConversionSize = GetWStrFromSrc(a14, pvargSrc, v391[0], *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
            if ( ConversionSize < 0 )
              goto LABEL_103;
            ConversionSize = VarDateFromStr(lpsz, 0x400u, 0, &pdateOut);
            if ( ConversionSize < 0 || pdateOut >= 2958466.0 || !(unsigned int)TmFromOleDate(pdateOut, &v399) )
              goto LABEL_103;
            *(_WORD *)v27 = v399.tm_year;
            *((_WORD *)v27 + 1) = v399.tm_mon;
            *((_WORD *)v27 + 2) = v399.tm_mday;
            goto LABEL_54;
          }
        }
        CDateTimeParser::CheckDefaultDate((CDateTimeParser *)&v485, a16 & 0x100);
        *(_DWORD *)v27 = v485;
        v126 = v486;
        *((_WORD *)v27 + 2) = v486;
        v127 = IsValidDateValue(*(_WORD *)v27, *((_WORD *)v27 + 1), v126);
        v41 = v380;
        if ( v127 )
          goto LABEL_803;
        *v380 = 6;
        ConversionSize = v378;
        goto LABEL_55;
      case 1310:
LABEL_682:
        *v383 = 6;
        v506 = 0;
        v507 = 1;
        v508 = 0;
        v509 = 0;
        v510 = 0;
        v511 = 0;
        v512 = 0;
        v513 = 0;
        v501 = 0;
        v502 = 0;
        v503 = 0;
        v504 = 0;
        v505 = 0;
        v38 = (CY *)pvargSrc;
        switch ( (unsigned __int16)vt )
        {
          case 8u:
            v508 = SysStringLen(*(BSTR *)&pvargSrc->vt);
            v506 = *(VARIANTARG **)&pvargSrc->vt;
            break;
          case 0x81u:
            v508 = *(_QWORD *)ui;
            v506 = pvargSrc;
            v507 = 0;
            goto LABEL_689;
          case 0x82u:
            v508 = *(_QWORD *)ui >> 1;
            v506 = pvargSrc;
            break;
          default:
            goto LABEL_689;
        }
        v507 = 1;
LABEL_689:
        CDateTimeParser::Parse((CDateTimeParser *)&v501);
        if ( (v512 & 0xFFBF) != 0x238 )
        {
          ConversionSize = GetWStrFromSrc(a14, pvargSrc, v391[0], *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
          if ( ConversionSize >= 0 )
          {
            ConversionSize = VarDateFromStr(lpsz, 0x400u, 0, &v526);
            if ( ConversionSize >= 0 && v526 < 2958466.0 && (unsigned int)TmFromOleDate(v526, &v399) )
            {
              *(_WORD *)v27 = v399.tm_hour;
              *((_WORD *)v27 + 1) = v399.tm_min;
              *((_WORD *)v27 + 2) = v399.tm_sec;
              goto LABEL_54;
            }
          }
          v41 = v380;
          *v380 = 2;
          goto LABEL_55;
        }
        *(_WORD *)v27 = HIWORD(v502);
        *((_WORD *)v27 + 1) = v503;
        v128 = HIWORD(v503);
        *((_WORD *)v27 + 2) = HIWORD(v503);
        if ( *(_WORD *)v27 <= 0x17u && *((_WORD *)v27 + 1) <= 0x3Bu && v128 <= 0x3Bu )
          goto LABEL_802;
        goto LABEL_699;
      case 1311:
LABEL_725:
        *v383 = 16;
        v451 = 0;
        v452 = 1;
        v453 = 0;
        v454 = 0;
        v455 = 0;
        v456 = 0;
        v457 = 0;
        v458 = 0;
        v446 = 0;
        v447 = 0;
        v448 = 0;
        v449 = 0;
        v450 = 0;
        switch ( (unsigned __int16)vt )
        {
          case 8u:
            v453 = SysStringLen(*(BSTR *)&pvargSrc->vt);
            v132 = *(VARIANTARG **)&pvargSrc->vt;
            break;
          case 0x81u:
            v453 = *(_QWORD *)ui;
            v132 = pvargSrc;
            v452 = 0;
            goto LABEL_732;
          case 0x82u:
            v453 = *(_QWORD *)ui >> 1;
            v132 = pvargSrc;
            break;
          default:
            goto LABEL_733;
        }
        v452 = 1;
LABEL_732:
        v451 = v132;
LABEL_733:
        CDateTimeParser::Parse((CDateTimeParser *)&v446);
        v133 = a16 & 0x100;
        CDateTimeParser::CheckDefaultDate((CDateTimeParser *)&v446, v133);
        *(_DWORD *)v27 = v446;
        *((_DWORD *)v27 + 1) = v447;
        *((_DWORD *)v27 + 2) = v448;
        v134 = v449;
        *((_DWORD *)v27 + 3) = v449;
        v135 = v457 & 0xFFBF;
        if ( (v135 == 575 || v135 == 519 || v135 == 568 || v133 && v135 == 959)
          && *((_WORD *)v27 + 3) <= 0x17u
          && *((_WORD *)v27 + 4) <= 0x3Bu
          && *((_WORD *)v27 + 5) <= 0x3Bu
          && v134 <= 0x3B9AC9FF
          && (unsigned int)IsValidDateValue(*(_WORD *)v27, *((_WORD *)v27 + 1), *((_WORD *)v27 + 2)) )
        {
          ConversionSize = v378;
          v38 = (CY *)pvargSrc;
        }
        else
        {
          v38 = (CY *)pvargSrc;
          ConversionSize = GetWStrFromSrc(a14, pvargSrc, v391[0], *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
          if ( ConversionSize < 0 )
            goto LABEL_103;
          ConversionSize = VarDateFromStr(lpsz, 0x400u, 0, &v518);
          v378 = ConversionSize;
          if ( ConversionSize < 0 || v518 >= 2958466.0 || !(unsigned int)TmFromOleDate(v518, &v399) )
            goto LABEL_103;
          *(_WORD *)v27 = v399.tm_year;
          *((_WORD *)v27 + 1) = v399.tm_mon;
          *((_WORD *)v27 + 2) = v399.tm_mday;
          *((_WORD *)v27 + 3) = v399.tm_hour;
          *((_WORD *)v27 + 4) = v399.tm_min;
          *((_WORD *)v27 + 5) = v399.tm_sec;
          *((_DWORD *)v27 + 3) = 0;
        }
        if ( (a16 & 0x920) != 0x20 )
          goto LABEL_802;
        if ( !(*((_DWORD *)v27 + 3) % (unsigned int)dword_3839128A0[v381]) )
          goto LABEL_54;
        *v380 = 6;
        if ( v404 )
          *(_DWORD *)v404 = 3;
        goto LABEL_56;
      case 1317:
        v38 = *(CY **)&pvargSrc->vt;
        if ( *(_QWORD *)&pvargSrc->vt )
        {
          v32 = SysStringByteLen(*(BSTR *)&pvargSrc->vt);
          *(_QWORD *)ui = v32;
LABEL_892:
          v180 = v32 + 2;
          *v383 = v32 + 2;
          if ( v385 )
          {
            v181 = v32 + 2;
            Size = v180;
            v182 = (char *)((__int64 (__fastcall *)(LPMALLOC, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                             g_pIMalloc,
                             v181);
            *(_QWORD *)v27 = v182;
            if ( !v182 )
            {
              if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              {
                LODWORD(lpMultiByteStr) = 4408;
                bidTraceW(off_383B43280[0], 4513833, off_383B49128[0], 2147942414LL);
                ConversionSize = -2147024882;
                goto LABEL_56;
              }
              goto LABEL_1569;
            }
            v27 = v182;
            Source = v182;
          }
          else
          {
            v181 = Size;
          }
          if ( *(_QWORD *)ui + 2LL > v181 )
          {
            *v380 = 4;
            if ( v181 < 2 )
            {
              memcpy(v27, qword_383866850, v181);
            }
            else
            {
              *(_WORD *)v27 = -257;
              memcpy(v27 + 2, v38, v181 - 2);
            }
            ConversionSize = v378;
          }
          else
          {
            *(_WORD *)v27 = -257;
            memcpy(v27 + 2, v38, *(size_t *)ui);
            ConversionSize = v378;
          }
          goto LABEL_54;
        }
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_1696;
        v351 = off_383B43280[0];
        if ( !off_383B49128[0] )
          goto LABEL_1696;
        LODWORD(lpMultiByteStr) = 4384;
        v352 = 4489257;
        goto LABEL_1695;
      case 1320:
        goto LABEL_1448;
      case 1321:
LABEL_700:
        *v383 = 12;
        v477 = 0;
        v478 = 1;
        v479 = 0;
        v480 = 0;
        v481 = 0;
        v482 = 0;
        v483 = 0;
        v484 = 0;
        v472 = 0;
        v473 = 0;
        v474 = 0;
        v475 = 0;
        v476 = 0;
        v38 = (CY *)pvargSrc;
        switch ( (unsigned __int16)vt )
        {
          case 8u:
            v479 = SysStringLen(*(BSTR *)&pvargSrc->vt);
            v477 = *(VARIANTARG **)&pvargSrc->vt;
            break;
          case 0x81u:
            v479 = *(_QWORD *)ui;
            v477 = pvargSrc;
            v478 = 0;
            goto LABEL_707;
          case 0x82u:
            v479 = *(_QWORD *)ui >> 1;
            v477 = pvargSrc;
            break;
          default:
            goto LABEL_707;
        }
        v478 = 1;
LABEL_707:
        CDateTimeParser::Parse((CDateTimeParser *)&v472);
        v129 = v483 & 0xFFBF;
        v130 = a16;
        if ( v129 != 568 && ((a16 & 0x100) == 0 || v129 != 575 && v129 != 959) )
        {
          ConversionSize = GetWStrFromSrc(a14, pvargSrc, v391[0], *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
          if ( ConversionSize < 0 )
            goto LABEL_103;
          ConversionSize = VarDateFromStr(lpsz, 0x400u, 0, &v524);
          if ( ConversionSize < 0 || v524 >= 2958466.0 || !(unsigned int)TmFromOleDate(v524, &v399) )
            goto LABEL_103;
          *(_WORD *)v27 = v399.tm_hour;
          *((_WORD *)v27 + 1) = v399.tm_min;
          *((_WORD *)v27 + 2) = v399.tm_sec;
          *((_DWORD *)v27 + 2) = 0;
          *((_WORD *)v27 + 3) = 0;
          goto LABEL_54;
        }
        *(_WORD *)v27 = HIWORD(v473);
        *(_DWORD *)(v27 + 2) = v474;
        *((_DWORD *)v27 + 2) = v475;
        *((_WORD *)v27 + 3) = 0;
        if ( *(_WORD *)v27 > 0x17u
          || *((_WORD *)v27 + 1) > 0x3Bu
          || *((_WORD *)v27 + 2) > 0x3Bu
          || (v131 = *((_DWORD *)v27 + 2), v131 > 0x3B9AC9FF) )
        {
          v41 = v380;
          *v380 = (v130 & 0x20 | 0x40u) >> 4;
          ConversionSize = v378;
          goto LABEL_55;
        }
        if ( (v130 & 0x20) == 0 )
          goto LABEL_802;
        v41 = v380;
        if ( v131 % dword_3839128A0[v381] )
        {
          *v380 = 6;
          if ( v404 )
          {
            *(_DWORD *)v404 = 3;
            ConversionSize = v378;
            goto LABEL_55;
          }
        }
        goto LABEL_803;
      case 1322:
LABEL_752:
        *v383 = 20;
        v438 = 0;
        v439 = 1;
        v440 = 0;
        v441 = 0;
        v442 = 0;
        v443 = 0;
        v444 = 0;
        v445 = 0;
        v433 = 0;
        v434 = 0;
        v435 = 0;
        v436 = 0;
        v437 = 0;
        switch ( (unsigned __int16)vt )
        {
          case 8u:
            v440 = SysStringLen(*(BSTR *)&pvargSrc->vt);
            v438 = *(VARIANTARG **)&pvargSrc->vt;
            break;
          case 0x81u:
            v440 = *(_QWORD *)ui;
            v438 = pvargSrc;
            v439 = 0;
            goto LABEL_759;
          case 0x82u:
            v440 = *(_QWORD *)ui >> 1;
            v438 = pvargSrc;
            break;
          default:
            goto LABEL_759;
        }
        v439 = 1;
LABEL_759:
        CDateTimeParser::Parse((CDateTimeParser *)&v433);
        v136 = a16 & 0x100;
        CDateTimeParser::CheckDefaultDate((CDateTimeParser *)&v433, v136);
        *(_DWORD *)v27 = v433;
        *((_DWORD *)v27 + 1) = v434;
        *((_DWORD *)v27 + 2) = v435;
        *((_DWORD *)v27 + 3) = v436;
        *((_DWORD *)v27 + 4) = v437;
        v137 = v444 & 0xFFBF;
        if ( v137 == 959 || v136 && (v137 == 568 || v137 == 519 || v137 == 575) )
        {
          ConversionSize = v378;
        }
        else
        {
          ConversionSize = GetWStrFromSrc(a14, pvargSrc, v391[0], *(unsigned __int64 *)ui, (unsigned __int16 **)&lpsz);
          if ( ConversionSize < 0 )
            goto LABEL_103;
          ConversionSize = VarDateFromStr(lpsz, 0x400u, 0, &v523);
          v378 = ConversionSize;
          if ( ConversionSize < 0 || v523 >= 2958466.0 || !(unsigned int)TmFromOleDate(v523, &v399) )
            goto LABEL_103;
          *(_WORD *)v27 = v399.tm_year;
          *((_WORD *)v27 + 1) = v399.tm_mon;
          *((_WORD *)v27 + 2) = v399.tm_mday;
          *((_WORD *)v27 + 3) = v399.tm_hour;
          *((_WORD *)v27 + 4) = v399.tm_min;
          *((_WORD *)v27 + 5) = v399.tm_sec;
          *((_DWORD *)v27 + 3) = 0;
          if ( !FixUpTimeZone((struct tagDBTIMESTAMPOFFSET *)v27, a16, v381, v380) )
            goto LABEL_56;
        }
        if ( *((_WORD *)v27 + 3) > 0x17u
          || *((_WORD *)v27 + 4) > 0x3Bu
          || *((_WORD *)v27 + 5) > 0x3Bu
          || abs16(*((_WORD *)v27 + 8)) > 0xEu
          || abs16(*((_WORD *)v27 + 9)) > 0x3Bu
          || (v138 = *((_DWORD *)v27 + 3), v138 > 0x3B9AC9FF)
          || !(unsigned int)IsValidDateValue(*(_WORD *)v27, *((_WORD *)v27 + 1), *((_WORD *)v27 + 2)) )
        {
          v41 = v380;
          *v380 = (a16 & 0x20 | 0x40) >> 4;
          goto LABEL_614;
        }
        if ( (a16 & 0x20) != 0 )
        {
          v41 = v380;
          if ( v138 % dword_3839128A0[v381] )
          {
            *v380 = 6;
            if ( v404 )
            {
              *(_DWORD *)v404 = 3;
              v38 = (CY *)pvargSrc;
              goto LABEL_55;
            }
          }
        }
        else
        {
LABEL_802:
          v41 = v380;
        }
LABEL_803:
        ConversionSize = v378;
        v38 = (CY *)pvargSrc;
        goto LABEL_55;
      case 1323:
      case 1324:
        goto LABEL_248;
      case 1325:
      case 1326:
      case 1327:
      case 1328:
      case 1329:
      case 1330:
      case 1331:
      case 1334:
      case 1337:
      case 1339:
      case 1340:
      case 1341:
      case 1342:
      case 1343:
      case 1344:
      case 1395:
      case 1451:
      case 1452:
      case 1453:
      case 1454:
      case 1456:
      case 1458:
        goto LABEL_1291;
      case 1332:
        goto LABEL_455;
      case 1335:
      case 1482:
        goto LABEL_468;
      case 1336:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        if ( !*(_QWORD *)&pvargSrc->vt )
          goto LABEL_397;
        v80 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _BYTE *, unsigned __int64))&pvargSrc->vt)(
                *(_QWORD *)&pvargSrc->vt,
                &IID_IUnknown,
                v27,
                0x383800000uLL);
        goto LABEL_277;
      default:
        goto LABEL_1516;
    }
  }
  if ( v36 > 1892 )
  {
    if ( v36 > 2188 )
    {
      v33 = 0x383800000uLL;
      switch ( v36 )
      {
        case 2189:
        case 2191:
        case 2192:
        case 2193:
        case 2364:
          goto LABEL_1291;
        case 2202:
          goto LABEL_1448;
        case 2352:
        case 2353:
          goto LABEL_248;
        case 2366:
          *v383 = 16;
          v38 = (CY *)pvargSrc;
          v79 = VarDecFromI1(pvargSrc->vt, (DECIMAL *)v27);
          goto LABEL_275;
        default:
          goto LABEL_1516;
      }
    }
    if ( v36 < 2187 )
    {
      switch ( v36 )
      {
        case 1893:
        case 1894:
        case 1895:
        case 1897:
        case 1898:
        case 1899:
        case 1909:
        case 1910:
LABEL_462:
          pvarVal = pvargSrc;
          goto LABEL_463;
        case 1896:
          goto LABEL_470;
        case 1905:
          pvarVal = pvargSrc;
          if ( pvargSrc->vt == 8209 )
          {
            LOWORD(v26) = 128;
            v387 = 128;
            goto LABEL_1539;
          }
LABEL_463:
          vt = pvarVal->vt;
          *(_DWORD *)v391 = vt;
          if ( (_WORD)vt == 1 )
            goto LABEL_1585;
          if ( (vt & 0xFFF) == 0xC || (vt & 0xB000) != 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
            {
              LODWORD(lpMultiByteStr) = 4978;
              bidTraceW(off_383B43280[0], 5097513, off_383B49128[0], 2147749405LL);
              ConversionSize = -2147217891;
              goto LABEL_56;
            }
LABEL_108:
            ConversionSize = -2147217891;
            goto LABEL_56;
          }
          if ( (_WORD)vt != 14 )
            goto LABEL_1538;
          goto LABEL_1539;
        case 1908:
          *v383 = 56;
          v38 = (CY *)pvargSrc;
          v80 = DBTYPE_VARIANTToDBTYPE_SQLVARIANT(
                  (DECIMAL *)pvargSrc,
                  v27,
                  (const struct tagTDSCOLLATION *)(*((_QWORD *)v406 + 135) + 1816LL),
                  v380);
          goto LABEL_277;
        case 1911:
        case 1912:
        case 2058:
        case 2059:
          goto LABEL_248;
        case 1920:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          if ( *(_QWORD *)&pvargSrc->vt )
          {
            v80 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _BYTE *, unsigned __int64))&pvargSrc->vt)(
                    *(_QWORD *)&pvargSrc->vt,
                    &IID_IDispatch,
                    v27,
                    0x383800000uLL);
            goto LABEL_277;
          }
LABEL_397:
          v95 = 0;
LABEL_398:
          *(_QWORD *)v27 = v95;
          ConversionSize = v378;
          goto LABEL_54;
        case 1923:
          goto LABEL_468;
        case 1924:
LABEL_455:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          if ( *(_QWORD *)&pvargSrc->vt )
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD, unsigned __int64))(**(_QWORD **)&pvargSrc->vt + 8LL))(
              *(_QWORD *)&pvargSrc->vt,
              1,
              (unsigned __int16)vt,
              0x383800000uLL);
          *(_QWORD *)v27 = *(_QWORD *)&pvargSrc->vt;
          ConversionSize = v378;
          goto LABEL_54;
        case 2060:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          v80 = VarI2FromDec((const DECIMAL *)pvargSrc, (SHORT *)v27);
          goto LABEL_277;
        case 2061:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          v80 = VarI4FromDec((const DECIMAL *)pvargSrc, (LONG *)v27);
          goto LABEL_277;
        case 2062:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          v80 = VarR4FromDec((const DECIMAL *)pvargSrc, (FLOAT *)v27);
          goto LABEL_277;
        case 2063:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          v80 = VarR8FromDec((const DECIMAL *)pvargSrc, (DOUBLE *)v27);
          goto LABEL_277;
        case 2064:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          v80 = VarCyFromDec((const DECIMAL *)pvargSrc, (CY *)v27);
          goto LABEL_277;
        case 2065:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          v80 = VarDateFromDec((const DECIMAL *)pvargSrc, (DATE *)v27);
          goto LABEL_277;
        case 2066:
          break;
        case 2069:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          v80 = VarBoolFromDec((const DECIMAL *)pvargSrc, (VARIANT_BOOL *)v27);
          goto LABEL_277;
        case 2070:
          goto LABEL_1291;
        case 2072:
          *v383 = 16;
          v38 = (CY *)pvargSrc;
          *(_QWORD *)v27 = *(_QWORD *)&pvargSrc->vt;
          *((_QWORD *)v27 + 1) = pvargSrc->llVal;
          if ( (a16 & 8) != 0 )
            goto LABEL_276;
          goto LABEL_1173;
        case 2074:
          *v383 = 1;
          v38 = (CY *)pvargSrc;
          v80 = VarI1FromDec((const DECIMAL *)pvargSrc, v27);
          goto LABEL_277;
        case 2075:
          *v383 = 1;
          v38 = (CY *)pvargSrc;
          if ( pvargSrc->decVal.sign )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          v80 = VarUI1FromDec((const DECIMAL *)pvargSrc, v27);
          goto LABEL_277;
        case 2076:
          *v383 = 2;
          v38 = (CY *)pvargSrc;
          if ( pvargSrc->decVal.sign )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          v80 = VarUI2FromDec((const DECIMAL *)pvargSrc, (USHORT *)v27);
          goto LABEL_277;
        case 2077:
          *v383 = 4;
          v38 = (CY *)pvargSrc;
          if ( pvargSrc->decVal.sign )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          v80 = VarUI4FromDec((const DECIMAL *)pvargSrc, (ULONG *)v27);
          goto LABEL_277;
        case 2078:
          *v383 = 8;
          v86 = v26;
          v38 = (CY *)pvargSrc;
          p_pdecOut = (DECIMAL *)pvargSrc;
          goto LABEL_316;
        case 2079:
          *v383 = 8;
          v38 = (CY *)pvargSrc;
          if ( pvargSrc->decVal.sign )
          {
            v41 = v380;
            *v380 = 5;
            ConversionSize = v378;
            goto LABEL_55;
          }
          v86 = v26;
          p_pdecOut = (DECIMAL *)pvargSrc;
LABEL_316:
          v80 = _VarI8FromDec(p_pdecOut, v86, (__int64 *)v27, v380);
          goto LABEL_277;
        default:
          goto LABEL_1516;
      }
    }
    v517 = 0;
    v38 = (CY *)pvargSrc;
    ConversionSize = VarBstrFromDec((const DECIMAL *)pvargSrc, 0x409u, 0, &v517);
    if ( ConversionSize >= 0 )
    {
      v80 = FixupFromBstr(v517, v387, CodePage, v27, v383, Size, v380, v385);
      goto LABEL_277;
    }
    goto LABEL_1179;
  }
  if ( v36 != 1892 )
  {
    v33 = 0x383800000uLL;
    switch ( v36 )
    {
      case 1619:
      case 1628:
      case 1635:
        *v383 = 2;
        v38 = (CY *)pvargSrc;
        *(_WORD *)v27 = pvargSrc->vt;
        ConversionSize = v378;
        goto LABEL_54;
      case 1620:
      case 1636:
        *v383 = 4;
        v38 = (CY *)pvargSrc;
        *(_DWORD *)v27 = (__int16)pvargSrc->vt;
        ConversionSize = v378;
        goto LABEL_54;
      case 1621:
        *v383 = 4;
        v38 = (CY *)pvargSrc;
        *(float *)v27 = (float)(__int16)pvargSrc->vt;
        ConversionSize = v378;
        goto LABEL_54;
      case 1622:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        *(double *)v27 = (double)(__int16)pvargSrc->vt;
        ConversionSize = v378;
        goto LABEL_54;
      case 1623:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        v80 = VarCyFromI2(pvargSrc->vt, (CY *)v27);
        goto LABEL_277;
      case 1624:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        v96 = (double)(__int16)pvargSrc->vt;
        *(double *)v27 = v96;
        v80 = IsValidDate(v96, v380);
        goto LABEL_277;
      case 1625:
      case 1747:
        v38 = (CY *)pvargSrc;
        if ( (a16 & 0x120) == 0x120 )
        {
          v98 = L"1";
          if ( !pvargSrc->vt )
            v98 = L"0";
          v80 = FixupFromWstr(v98, (unsigned __int16 *)1, v26, 0xFFFFFFFF, v27, v383, Size, v380, v385);
        }
        else if ( pvargSrc->vt )
        {
          v80 = FixupFromWstr(L"True", (unsigned __int16 *)4, v26, 0xFFFFFFFF, v27, v383, Size, v380, v385);
        }
        else
        {
          v80 = FixupFromWstr(L"False", (unsigned __int16 *)5, v26, 0xFFFFFFFF, v27, v383, Size, v380, v385);
        }
        goto LABEL_277;
      case 1629:
        goto LABEL_468;
      case 1631:
        goto LABEL_411;
      case 1633:
        *v383 = 1;
        v38 = (CY *)pvargSrc;
        v80 = VarI1FromBool(pvargSrc->vt, v27);
        goto LABEL_277;
      case 1634:
        *v383 = 1;
        v38 = (CY *)pvargSrc;
        v80 = VarUI1FromBool(pvargSrc->vt, v27);
        goto LABEL_277;
      case 1637:
      case 1638:
        *v383 = 8;
        v38 = (CY *)pvargSrc;
        *(_QWORD *)v27 = (__int16)pvargSrc->vt;
        ConversionSize = v378;
        goto LABEL_54;
      case 1746:
        v38 = (CY *)pvargSrc;
        if ( (a16 & 0x120) == 0x120 )
        {
          v97 = "1";
          if ( !pvargSrc->vt )
            v97 = "0";
          v80 = CopyToStr(v97, v27, 1u, v383, Size, v380, v385);
        }
        else if ( pvargSrc->vt )
        {
          v80 = CopyToStr("True", v27, 4u, v383, Size, v380, v385);
        }
        else
        {
          v80 = CopyToStr("False", v27, 5u, v383, Size, v380, v385);
        }
        goto LABEL_277;
      case 1748:
        goto LABEL_511;
      case 1761:
        goto LABEL_1448;
      case 1764:
      case 1765:
      case 1766:
      case 1767:
      case 1768:
      case 1769:
      case 1770:
      case 1771:
      case 1772:
      case 1773:
      case 1774:
      case 1775:
      case 1777:
      case 1778:
      case 1780:
      case 1781:
      case 1782:
      case 1783:
      case 1784:
      case 1785:
      case 1828:
        goto LABEL_462;
      case 1776:
        *v383 = 24;
        VariantInit((VARIANTARG *)v27);
        v38 = (CY *)pvargSrc;
        ConversionSize = VariantCopy((VARIANTARG *)v27, pvargSrc);
        if ( pvargSrc->vt != 1 )
          goto LABEL_1179;
        v41 = v380;
        *v380 = 3;
        break;
      case 1836:
        goto LABEL_470;
      default:
        goto LABEL_1516;
    }
    goto LABEL_55;
  }
LABEL_470:
  pvarVal = pvargSrc;
  v99 = pvargSrc->vt;
  if ( pvargSrc->vt == 1 )
  {
LABEL_1585:
    *v380 = 3;
    ConversionSize = v378;
    goto LABEL_56;
  }
  if ( v99 == 8 || (_WORD)v26 == 128 && (v99 == 3 || v99 == 19) || v99 == 9 )
  {
    vt = v99;
    *(_DWORD *)v391 = v99;
LABEL_1538:
    pvarVal = (VARIANTARG *)((char *)pvarVal + 8);
    pvargSrc = pvarVal;
    v396 = pvarVal;
    goto LABEL_1539;
  }
  if ( (_WORD)v26 == 72 )
  {
    if ( v99 != 16392 )
      goto LABEL_1292;
LABEL_483:
    v31 = 49151;
    vt = v99 & 0xBFFF;
    *(_DWORD *)v391 = vt;
    pvarVal = pvargSrc->pvarVal;
    pvargSrc = pvarVal;
    v396 = pvarVal;
    goto LABEL_1540;
  }
  if ( (_WORD)v26 == 128 && (v99 == 16387 || v99 == 16403 || v99 == 16392) )
    goto LABEL_483;
LABEL_1292:
  if ( (a16 & 0x400) != 0 )
  {
    v353 = 135;
    v377 = a16;
    v376 = CodePage;
    v375 = a14;
    v374 = v381;
    v372 = a11;
    v370 = (unsigned __int8 *)v380;
    v368 = a9;
    cbMultiBytea = pvarVal;
LABEL_1661:
    pvarg.vt = 8;
    ConversionSize = CDataSource::DataConvert(
                       v406,
                       v353,
                       8u,
                       v32,
                       0,
                       cbMultiBytea,
                       &pvarg.decVal.8,
                       8u,
                       v368,
                       (unsigned int *)v370,
                       v372,
                       v374,
                       0,
                       v375,
                       v376,
                       v377);
    if ( ConversionSize < 0 )
      goto LABEL_56;
    v42 = v383;
    *v383 = 24;
    *(VARIANTARG *)v27 = pvarg;
    pvarg.vt = 0;
    goto LABEL_59;
  }
LABEL_1293:
  v277 = ClosestVARTYPE((unsigned __int16)vt);
  pvarg.vt = v277;
  v279 = 0;
  v378 = 0;
  switch ( v280 )
  {
    case 2:
    case 11:
    case 18:
      v38 = (CY *)pvargSrc;
      pvarg.iVal = pvargSrc->vt;
      v281 = v380;
      goto LABEL_1344;
    case 3:
    case 19:
      v38 = (CY *)pvargSrc;
      pvarg.lVal = *(_DWORD *)&pvargSrc->vt;
      v281 = v380;
      goto LABEL_1344;
    case 4:
      v38 = (CY *)pvargSrc;
      pvarg.lVal = *(_DWORD *)&pvargSrc->vt;
      v281 = v380;
      goto LABEL_1344;
    case 5:
    case 7:
      v38 = (CY *)pvargSrc;
      pvarg.llVal = *(_QWORD *)&pvargSrc->vt;
      v281 = v380;
      goto LABEL_1344;
    case 6:
      v38 = (CY *)pvargSrc;
      goto LABEL_1300;
    case 9:
      v38 = (CY *)pvargSrc;
      if ( !*(_QWORD *)&pvargSrc->vt )
      {
LABEL_1300:
        pvarg.cyVal = *v38;
        v281 = v380;
        goto LABEL_1344;
      }
      v535[0] = 0;
      v535[1] = 0;
      v536 = 0;
      v537 = 0;
      if ( v431.vt )
      {
        if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
          goto LABEL_108;
        LODWORD(lpMultiByteStr) = 7715;
        bidTraceW(off_383B43280[0], 7900201, off_383B49128[0], 2147749405LL);
        ConversionSize = -2147217891;
        goto LABEL_56;
      }
      HIDWORD(p_wMilliseconds) = 0;
      lpUsedDefaultChar = 0;
      lpDefaultChar = &v431;
      LOWORD(lpMultiByteStr) = 2;
      ConversionSize = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64, _DWORD, _QWORD *))(**(_QWORD **)&pvargSrc->vt + 48LL))(
                         *(_QWORD *)&pvargSrc->vt,
                         0,
                         &GUID_NULL,
                         1033,
                         (_DWORD)lpMultiByteStr,
                         v535);
      v378 = ConversionSize;
      if ( ConversionSize < 0 )
        goto LABEL_56;
      goto LABEL_1306;
    case 12:
      v38 = (CY *)pvargSrc;
      v279 = VariantCopy(&pvarg, pvargSrc);
      v378 = v279;
      v281 = v380;
      goto LABEL_1344;
    case 14:
      v38 = (CY *)pvargSrc;
      *(_OWORD *)&pvarg.vt = *(_OWORD *)&pvargSrc->vt;
      pvarg.vt = v277;
      v281 = v380;
      goto LABEL_1344;
    case 16:
    case 17:
      v38 = (CY *)pvargSrc;
      pvarg.bVal = pvargSrc->vt;
      v281 = v380;
      goto LABEL_1344;
    case 64:
      *(_QWORD *)&SystemTime.wYear = 0;
      *(_QWORD *)&SystemTime.wHour = 0;
      v38 = (CY *)pvargSrc;
      if ( !FileTimeToSystemTime((const FILETIME *)pvargSrc, &SystemTime) )
        goto LABEL_1632;
      v283 = SystemTimeToVariantTime(&SystemTime, &pvarg.dblVal);
      goto LABEL_1312;
    case 128:
    case 132:
      rgsabound.lLbound = 0;
      rgsabound.cElements = v32;
      v282 = SafeArrayCreate(0x11u, 1u, &rgsabound);
      pvarg.llVal = (LONGLONG)v282;
      if ( v282 )
      {
        ConversionSize = SafeArrayLock(v282);
        v378 = ConversionSize;
        if ( ConversionSize < 0 )
        {
          VariantClear(&pvarg);
          goto LABEL_56;
        }
        v38 = (CY *)pvargSrc;
        memcpy(*(void **)(pvarg.llVal + 16), pvargSrc, *(size_t *)ui);
        SafeArrayUnlock(pvarg.parray);
        v279 = ConversionSize;
        v281 = v380;
LABEL_1344:
        v290 = v395;
        if ( (int)v395 >= 17 && ((int)v395 <= 19 || v395 == 21) )
        {
          if ( (unsigned int)IsVariantNegative(&pvarg) )
          {
            *v281 = 5;
            VariantClear(&pvarg);
            ConversionSize = v378;
            goto LABEL_54;
          }
          v290 = v395;
        }
        if ( v279 >= 0 )
        {
          v291 = ClosestVARTYPE(v290);
          if ( v291 != 12 )
          {
            v293 = VariantChangeTypeEx(&pvarg, &pvarg, 0x409u, 0, v291);
            v378 = v293;
            v292 = v395;
          }
          if ( v293 >= 0 )
          {
            switch ( v292 )
            {
              case 2u:
              case 0xBu:
              case 0x12u:
                *v383 = 2;
                *(_WORD *)v27 = pvarg.iVal;
                goto LABEL_586;
              case 3u:
              case 0x13u:
                *v383 = 4;
                *(_DWORD *)v27 = pvarg.lVal;
                goto LABEL_586;
              case 4u:
                *v383 = 4;
                *(_DWORD *)v27 = pvarg.lVal;
                goto LABEL_586;
              case 5u:
              case 7u:
                *v383 = 8;
                *(_QWORD *)v27 = pvarg.llVal;
                goto LABEL_586;
              case 6u:
                *v383 = 8;
                *(_QWORD *)v27 = pvarg.llVal;
                goto LABEL_586;
              case 8u:
                v42 = v383;
                *v383 = 8;
                *(_QWORD *)v27 = pvarg.llVal;
                pvarg.vt = 0;
                ConversionSize = v378;
                goto LABEL_59;
              case 0xCu:
                v42 = v383;
                *v383 = 24;
                *(VARIANTARG *)v27 = pvarg;
                pvarg.vt = 0;
                ConversionSize = v378;
                goto LABEL_59;
              case 0xEu:
                *v383 = 16;
                *(_OWORD *)v27 = *(_OWORD *)&pvarg.vt;
                if ( (a16 & 8) != 0 )
                  goto LABEL_276;
                goto LABEL_290;
              case 0x10u:
              case 0x11u:
                *v383 = 1;
                *v27 = pvarg.bVal;
                goto LABEL_586;
              case 0x14u:
                *v383 = 8;
                *(_QWORD *)v27 = pvarg.llVal / 10000;
                if ( pvarg.llVal >= 0 )
                {
                  if ( pvarg.llVal % 10000 <= 4999 )
                    goto LABEL_290;
                  ++*(_QWORD *)v27;
                }
                else
                {
                  if ( pvarg.llVal % 10000 >= -4999 )
                    goto LABEL_290;
                  --*(_QWORD *)v27;
                }
                goto LABEL_586;
              case 0x15u:
                *v383 = 8;
                v294 = pvarg.llVal / 0x2710uLL;
                *(_QWORD *)v27 = pvarg.llVal / 0x2710uLL;
                if ( pvarg.llVal % 10000 <= 4999 )
                  goto LABEL_290;
                *(_QWORD *)v27 = v294 + 1;
                goto LABEL_586;
              case 0x40u:
                *v383 = 8;
                *(_QWORD *)&SystemTime.wYear = 0;
                *(_QWORD *)&SystemTime.wHour = 0;
                if ( VariantTimeToSystemTime(pvarg.dblVal, &SystemTime)
                  && (unsigned int)IsValidFileTimeDateValue(
                                     SystemTime.wYear,
                                     SystemTime.wMonth,
                                     SystemTime.wDay,
                                     SystemTime.wHour,
                                     SystemTime.wMinute,
                                     SystemTime.wSecond,
                                     SystemTime.wMilliseconds)
                  && SystemTimeToFileTime(&SystemTime, (LPFILETIME)v27) )
                {
                  goto LABEL_389;
                }
                *v281 = 6;
                ConversionSize = v378;
                goto LABEL_54;
              case 0x48u:
                *v383 = 16;
                if ( pvarg.llVal && !*pvarg.bstrVal )
                {
                  *(_QWORD *)v27 = 0;
                  *((_QWORD *)v27 + 1) = 0;
                  goto LABEL_586;
                }
                v295 = SysStringLen(pvarg.bstrVal);
                *(_QWORD *)ui = v295;
                if ( v295 > 0x64 )
                  v295 = 100;
                v397 = v295;
                lpsz = strIn;
                v296 = v295;
                memcpy(strIn, pvarg.bstrVal, v296 * 2);
                strIn[v296] = 0;
                ConversionSize = CLSIDFromString(strIn, (LPCLSID)v27);
                goto LABEL_1526;
              case 0x80u:
              case 0x84u:
                *v383 = *(unsigned int *)(pvarg.llVal + 24);
                ConversionSize = SafeArrayLock(pvarg.parray);
                if ( ConversionSize < 0 )
                {
                  *v383 = 0;
                  goto LABEL_56;
                }
                v297 = *v383;
                v298 = Size;
                if ( Size < *v383 )
                {
                  *v380 = 4;
                  v297 = v298;
                }
                memcpy(v27, *(const void **)(pvarg.llVal + 16), v297);
                SafeArrayUnlock(pvarg.parray);
                goto LABEL_54;
              case 0x81u:
              case 0x82u:
                v42 = v383;
                *v383 = 2;
                ConversionSize = FixupFromBstr(pvarg.bstrVal, v387, CodePage, v27, v383, Size, v281, v385);
                pvarg.vt = 0;
                goto LABEL_59;
              case 0x83u:
                v299 = 0;
                v403 = 0;
                v300 = -1;
                v540.scale = pvarg.decVal.scale;
                v540.sign = pvarg.decVal.sign == 0;
                *(_QWORD *)v540.val = pvarg.llVal;
                *(_DWORD *)&v540.val[8] = pvarg.decVal.Hi32;
                *(_DWORD *)&v540.val[12] = 0;
                v301 = 96;
                v302 = &v540.val[11];
                v303 = 0;
                v386[0] = 0;
                while ( 2 )
                {
                  while ( v301 )
                  {
                    v304 = *v302;
                    v301 -= *((unsigned __int8 *)qword_383866CD8 + (v304 >> 4));
                    if ( (v304 & 0xF0) != 0 )
                      break;
                    v301 -= *((unsigned __int8 *)qword_383866CD8 + v304);
                    if ( (_BYTE)v304 )
                      break;
                    --v302;
                  }
                  if ( v300 == -1 )
                    v300 = v302 - (BYTE *)&v540 - 2;
                  if ( v301 && !((v301 - 1) % 0xAu % 3) )
                  {
                    if ( !v299 )
                    {
                      v498 = *(_QWORD *)v540.val;
                      v514 = *(_QWORD *)&v540.val[8];
                      v403 = 1;
                    }
                    v386[0] = v303 + 1;
                    v540.precision = (_BYTE)v302 - (unsigned __int8)&v540 - 2;
                    valid = NumericDivideWithRemainder(v540.val, &v540.precision, 0x10u, 1u, 0, 0);
                    if ( valid >= 0 )
                    {
                      v301 = (v301 + 7) & 0xFFFFFFF8;
                      v299 = v403;
                      v303 = v386[0];
                      continue;
                    }
                    goto LABEL_1689;
                  }
                  break;
                }
                v305 = ceil((double)v301 * 0.30103);
                v306 = (int)v305 + v386[0];
                if ( v403 )
                {
                  *(_QWORD *)v540.val = v498;
                  *(_QWORD *)&v540.val[8] = v514;
                }
                v307 = (int)v305 + v386[0];
                if ( !v306 )
                  v307 = 1;
                v540.precision = v307;
                scale = v540.scale;
                if ( !v306 )
                  scale = 1;
                v540.scale = scale;
                ConversionSize = ScaleNumeric(&v540, a11, v381, 0);
                *v383 = 19;
                v27 = Source;
                *(struct tagDB_NUMERIC *)Source = v540;
                break;
              case 0x85u:
                *v383 = 6;
                if ( pvarg.dblVal >= 2958466.0 || !(unsigned int)TmFromOleDate(pvarg.dblVal, &v399) )
                  goto LABEL_1416;
                *(_WORD *)v27 = v399.tm_year;
                *((_WORD *)v27 + 1) = v399.tm_mon;
                *((_WORD *)v27 + 2) = v399.tm_mday;
                goto LABEL_586;
              case 0x86u:
                *v383 = 6;
                if ( pvarg.dblVal >= 2958466.0 || !(unsigned int)TmFromOleDate(pvarg.dblVal, &v399) )
                  goto LABEL_1416;
                *(_WORD *)v27 = v399.tm_hour;
                *((_WORD *)v27 + 1) = v399.tm_min;
                *((_WORD *)v27 + 2) = v399.tm_sec;
                goto LABEL_586;
              case 0x87u:
                *v383 = 16;
                if ( pvarg.dblVal >= 2958466.0 || !(unsigned int)TmFromOleDate(pvarg.dblVal, &v399) )
                  goto LABEL_1416;
                *(_WORD *)v27 = v399.tm_year;
                *((_WORD *)v27 + 1) = v399.tm_mon;
                *((_WORD *)v27 + 2) = v399.tm_mday;
                *((_WORD *)v27 + 3) = v399.tm_hour;
                *((_WORD *)v27 + 4) = v399.tm_min;
                *((_WORD *)v27 + 5) = v399.tm_sec;
                Hi = 0;
                goto LABEL_585;
              case 0x91u:
                *v383 = 12;
                if ( pvarg.dblVal >= 2958466.0 || !(unsigned int)TmFromOleDate(pvarg.dblVal, &v399) )
                  goto LABEL_1416;
                *(_WORD *)v27 = v399.tm_hour;
                *((_WORD *)v27 + 1) = v399.tm_min;
                *((_WORD *)v27 + 2) = v399.tm_sec;
                *((_DWORD *)v27 + 2) = 0;
                goto LABEL_586;
              case 0x92u:
                *v383 = 20;
                if ( pvarg.dblVal >= 2958466.0 || !(unsigned int)TmFromOleDate(pvarg.dblVal, &v399) )
                {
LABEL_1416:
                  *v281 = 6;
                  goto LABEL_586;
                }
                tm_sec = v399.tm_sec;
                tm_min = v399.tm_min;
                tm_hour = v399.tm_hour;
                if ( !(unsigned int)TimeZoneOffsetFromTimeStamp(
                                      v399.tm_year,
                                      v399.tm_mon,
                                      v399.tm_mday,
                                      v399.tm_hour,
                                      v399.tm_min,
                                      v399.tm_sec,
                                      0,
                                      v413,
                                      &v412) )
                  goto LABEL_1633;
                v312 = Source;
                *(_WORD *)Source = v399.tm_year;
                *((_WORD *)v312 + 1) = v399.tm_mon;
                *((_WORD *)v312 + 2) = v399.tm_mday;
                *((_WORD *)v312 + 3) = tm_hour;
                *((_WORD *)v312 + 4) = tm_min;
                v27 = v312;
                *((_WORD *)v312 + 5) = tm_sec;
                *((_DWORD *)v312 + 3) = 0;
                *((_WORD *)v312 + 8) = v413[0];
                *((_WORD *)v312 + 9) = v412;
                goto LABEL_238;
              default:
                goto LABEL_290;
            }
            goto LABEL_1526;
          }
        }
        *v383 = 0;
        ConversionSize = v378;
LABEL_54:
        v41 = v380;
        goto LABEL_55;
      }
      if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
        goto LABEL_1569;
      LODWORD(lpMultiByteStr) = 7758;
      bidTraceW(off_383B43280[0], 7944233, off_383B49128[0], 2147942414LL);
      ConversionSize = -2147024882;
LABEL_56:
      if ( pvarg.vt )
        VariantClear(&pvarg);
      v42 = v383;
      v27 = Source;
LABEL_59:
      if ( v431.vt )
        VariantClear(&v431);
      if ( ConversionSize >= 0 && ConversionSize != 80 )
      {
LABEL_63:
        v43 = (int *)v380;
        goto LABEL_64;
      }
      switch ( ConversionSize )
      {
        case -2147467259:
          v43 = (int *)v380;
          if ( *v380 != 8 )
            goto LABEL_1712;
          goto LABEL_64;
        case -2147352566:
          goto LABEL_1708;
        case -2147217891:
          if ( v425 || v417 == 144 || v409 == 144 )
          {
            v43 = (int *)v380;
            v44 = 2;
            *v380 = 2;
            goto LABEL_65;
          }
          v43 = (int *)v380;
          *v380 = 1;
          goto LABEL_64;
        case -2147024774:
LABEL_1708:
          v43 = (int *)v380;
          *v380 = 6;
          ConversionSize = -2147217833;
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_383B49128[0] )
            {
              LODWORD(lpMultiByteStr) = 8601;
              bidTraceW(off_383B43280[0], 8807465, off_383B49128[0], 2147749463LL);
            }
            goto LABEL_63;
          }
LABEL_64:
          v44 = 2;
          goto LABEL_65;
      }
      v43 = (int *)v380;
      if ( ConversionSize == 80 )
      {
        *v380 = 4;
        ConversionSize = 0;
        goto LABEL_64;
      }
LABEL_1712:
      v44 = 2;
      *v43 = 2;
LABEL_65:
      v45 = a16;
      if ( (a16 & 0x30) == 0x30 && *v43 == 4 && (v391[0] == 133 || v391[0] == 145 || v391[0] == 135 || v391[0] == 146) )
      {
        v46 = (void *)v387;
        if ( (_WORD)v387 == 129 || (_WORD)v387 == 130 )
          *v43 = 2;
      }
      else
      {
        v46 = (void *)v387;
      }
      if ( (v45 & 1) != 0 && ConversionSize != -2147217891 )
      {
        v354 = *v43;
        if ( *v43 == 4 )
          v354 = 2;
        *v43 = v354;
        if ( v432 )
        {
          if ( v354 )
          {
            if ( v385 && v27 && ConversionSize >= 0 && v354 != 4 && v354 != 3 )
            {
              ((void (__fastcall *)(LPMALLOC, _QWORD, __int64, void *, _DWORD, size_t))g_pIMalloc->lpVtbl->Free)(
                g_pIMalloc,
                *(_QWORD *)v432,
                2,
                v46,
                (_DWORD)lpMultiByteStr,
                cbMultiByte);
              v46 = v432;
              *(_QWORD *)v432 = 0;
            }
          }
          else
          {
            if ( v430 )
            {
              v355 = v519;
              v27 = Src;
            }
            else
            {
              switch ( (__int16)v46 )
              {
                case 8:
                  v355 = 8;
                  break;
                case 128:
                case 132:
                case 141:
                  v355 = *v42;
                  if ( *v42 >= Size )
                    goto LABEL_1737;
                  break;
                case 129:
                  v355 = *v42 + 1;
                  if ( v355 >= Size )
                    goto LABEL_1737;
                  break;
                case 130:
                  v355 = *v42 + 2;
                  if ( v355 >= Size )
LABEL_1737:
                    v355 = Size;
                  break;
                default:
                  v355 = *v42;
                  break;
              }
            }
            if ( !v385 )
              memcpy(v432, v27, v355);
          }
        }
      }
      if ( lpsz && v408 )
        ((void (__fastcall *)(struct IMalloc *, LPCOLESTR, __int64, void *))g_pMO->lpVtbl->Free)(g_pMO, lpsz, v44, v46);
      if ( v27 && v424 )
        ((void (__fastcall *)(struct IMalloc *, _BYTE *, __int64, void *))g_pMO->lpVtbl->Free)(g_pMO, v27, v44, v46);
      if ( ConversionSize < 0 )
        goto LABEL_76;
      v47 = *v380;
      if ( !*v380 || v47 == 4 || v47 == 3 )
        goto LABEL_76;
      ConversionSize = -2147217887;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_383B49128[0] )
          bidTraceW(off_383B43280[0], 8936489, off_383B49128[0], 2147749409LL);
        goto LABEL_76;
      }
      return (unsigned int)ConversionSize;
    case 131:
      v38 = (CY *)pvargSrc;
      if ( *(_DWORD *)((char *)&pvargSrc->decVal.Lo64 + 7) || HIBYTE(pvargSrc->vt) > 0x1Cu )
      {
        v386[0] = 16;
        *(_QWORD *)v549 = *(_QWORD *)&pvargSrc->decVal.sign;
        v550 = *(ULONGLONG *)((char *)&pvargSrc->decVal.Lo64 + 3);
        v281 = v380;
        valid = TruncateNumeric(
                  v549,
                  v386,
                  0x10u,
                  pvargSrc->vt,
                  HIBYTE(pvargSrc->vt),
                  pvargSrc->decVal.scale,
                  (unsigned __int8)v380,
                  (unsigned __int8)&v416,
                  &v402,
                  v411,
                  v371,
                  v373);
        v279 = valid;
        v378 = valid;
        if ( valid < 0 || *v380 )
          goto LABEL_1689;
        v289 = 0x80;
        if ( pvargSrc->decVal.scale == 1 )
          v289 = 0;
        pvarg.decVal.sign = v289;
        pvarg.decVal.scale = v402;
        pvarg.llVal = *(_QWORD *)v549;
        v287 = v550;
      }
      else
      {
        v286 = 0x80;
        if ( pvargSrc->decVal.scale == 1 )
          v286 = 0;
        pvarg.decVal.sign = v286;
        pvarg.decVal.scale = HIBYTE(pvargSrc->vt);
        pvarg.llVal = *(_QWORD *)&pvargSrc->decVal.sign;
        v287 = *(_DWORD *)((char *)&pvargSrc->decVal.Lo64 + 3);
        v281 = v380;
      }
      pvarg.decVal.Hi32 = v287;
      goto LABEL_1344;
    case 133:
      v38 = (CY *)pvargSrc;
      if ( pvargSrc->vt < 0x64u )
        goto LABEL_1632;
      v283 = OleDateFromTm(pvargSrc->vt, pvargSrc->wReserved1, pvargSrc->wReserved2, 0, 0, 0, 0, &pvarg.dblVal);
      goto LABEL_1312;
    case 134:
      GetLocalTime(&v544);
      v38 = (CY *)pvargSrc;
      if ( v544.wYear < 0x64u )
        goto LABEL_1632;
      v283 = OleDateFromTm(
               v544.wYear,
               v544.wMonth,
               v544.wDay,
               pvargSrc->vt,
               pvargSrc->wReserved1,
               pvargSrc->wReserved2,
               0,
               &pvarg.dblVal);
      goto LABEL_1312;
    case 135:
      v38 = (CY *)pvargSrc;
      if ( pvargSrc->vt < 0x64u )
        goto LABEL_1632;
      v283 = OleDateFromTm(
               pvargSrc->vt,
               pvargSrc->wReserved1,
               pvargSrc->wReserved2,
               pvargSrc->wReserved3,
               pvargSrc->uiVal,
               WORD1(pvargSrc->decVal.Lo64),
               pvargSrc->cyVal.Hi / 0xF4240u,
               &pvarg.dblVal);
      goto LABEL_1312;
    case 145:
      if ( (v278 & 0x100) != 0 )
      {
        v38 = (CY *)pvargSrc;
        v284 = OleDateFromTm(
                 0x76Cu,
                 1u,
                 1u,
                 pvargSrc->vt,
                 pvargSrc->wReserved1,
                 pvargSrc->wReserved2,
                 pvargSrc->lVal / 0xF4240u,
                 &pvarg.dblVal);
      }
      else
      {
        GetLocalTime(&v545);
        v38 = (CY *)pvargSrc;
        if ( v545.wYear < 0x64u )
          goto LABEL_1632;
        v284 = OleDateFromTm(
                 v545.wYear,
                 v545.wMonth,
                 v545.wDay,
                 pvargSrc->vt,
                 pvargSrc->wReserved1,
                 pvargSrc->wReserved2,
                 pvargSrc->lVal / 0xF4240u,
                 &pvarg.dblVal);
      }
      if ( !v284 )
        goto LABEL_1632;
      if ( (_WORD)v387 == 133 )
        goto LABEL_1633;
LABEL_1313:
      v279 = 0;
      v281 = v380;
      goto LABEL_1344;
    case 146:
      v38 = (CY *)pvargSrc;
      if ( (v278 & 0x20) != 0 )
        v285 = ConvertOffsetToUTC((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400);
      else
        v285 = ConvertOffsetToLocal((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)pvargSrc, &v400);
      if ( v285 )
        goto LABEL_1633;
      if ( v400.year < 0x64u )
        goto LABEL_1632;
      v283 = OleDateFromTm(
               v400.year,
               v400.month,
               v400.day,
               v400.hour,
               v400.minute,
               v400.second,
               v400.fraction / 0xF4240,
               &pvarg.dblVal);
LABEL_1312:
      if ( v283 )
        goto LABEL_1313;
      goto LABEL_1632;
    default:
      ConversionSize = 0;
      goto LABEL_56;
  }
}

```

## disassembly

```asm
0x38385b340  push    rbp
0x38385b342  push    rbx
0x38385b343  push    rsi
0x38385b344  push    rdi
0x38385b345  lea     rbp, [rsp-19C8h]
0x38385b34d  mov     eax, 1AC8h
0x38385b352  call    _alloca_probe
0x38385b357  sub     rsp, rax
0x38385b35a  mov     [rbp+19E0h+var_15F0], 0FFFFFFFFFFFFFFFEh
0x38385b365  movaps  [rsp+1AE0h+var_30], xmm6
0x38385b36d  movaps  [rsp+1AE0h+var_40], xmm7
0x38385b375  movaps  [rsp+1AE0h+var_50], xmm8
0x38385b37e  movaps  [rsp+1AE0h+var_60], xmm9
0x38385b387  movaps  [rsp+1AE0h+var_70], xmm10
0x38385b390  movaps  [rsp+1AE0h+var_80], xmm11
0x38385b399  mov     rax, cs:__security_cookie
0x38385b3a0  xor     rax, rsp
0x38385b3a3  mov     [rbp+19E0h+var_90], rax
0x38385b3aa  mov     [rbp+19E0h+var_1A2C], r8d
0x38385b3ae  movzx   esi, dx
0x38385b3b1  mov     dword ptr [rbp+19E0h+var_1A10], esi
0x38385b3b4  mov     [rbp+19E0h+var_1968], rcx
0x38385b3b8  mov     qword ptr [rbp+19E0h+ui], r9
0x38385b3bc  mov     rbx, [rbp+19E0h+arg_20]
0x38385b3c3  mov     rax, [rbp+19E0h+arg_28]
0x38385b3ca  mov     [rbp+19E0h+pvargSrc], rax
0x38385b3ce  mov     [rbp+19E0h+var_19D8], rax
0x38385b3d2  mov     r10, [rbp+19E0h+arg_30]
0x38385b3d9  mov     [rbp+19E0h+Source], r10
0x38385b3dd  mov     r11, [rbp+19E0h+arg_38]
0x38385b3e4  mov     [rbp+19E0h+Size], r11
0x38385b3e8  mov     rdi, [rbp+19E0h+arg_48]
0x38385b3ef  movzx   eax, [rbp+19E0h+arg_58]
0x38385b3f6  mov     [rbp+19E0h+var_1A50], al
0x38385b3f9  mov     [rbp+19E0h+var_1A38], al
0x38385b3fc  mov     rcx, [rbp+19E0h+arg_60]
0x38385b403  mov     [rbp+19E0h+var_1978], rcx
0x38385b407  test    byte ptr cs:_bidGblFlags, 2
0x38385b40e  jnz     loc_38385B8A9
0x38385b414  xor     r10d, r10d
0x38385b417  mov     [rbp+19E0h+var_18E0], r10
0x38385b41e  mov     [rbp+19E0h+lpsz], r10
0x38385b422  mov     [rbp+19E0h+var_1A34], r10d
0x38385b426  mov     [rbp+19E0h+var_1918], r10d
0x38385b42d  mov     [rbp+19E0h+var_195C], r10d
0x38385b434  mov     word ptr [rbp+19E0h+pvarg], r10w
0x38385b439  mov     word ptr [rbp+19E0h+pvarg+2], r10w
0x38385b43e  mov     word ptr [rbp+19E0h+pvarg+4], r10w
0x38385b443  mov     word ptr [rbp+19E0h+pvarg+6], r10w
0x38385b448  mov     qword ptr [rbp+19E0h+pvarg+8], r10
0x38385b44c  xor     eax, eax
0x38385b44e  mov     qword ptr [rbp+19E0h+pvarg+10h], rax
0x38385b452  mov     word ptr [rbp+19E0h+var_18F8], r10w
0x38385b45a  mov     word ptr [rbp+19E0h+var_18F8+2], r10w
0x38385b462  mov     word ptr [rbp+19E0h+var_18F8+4], r10w
0x38385b46a  mov     word ptr [rbp+19E0h+var_18F8+6], r10w
0x38385b472  mov     qword ptr [rbp+19E0h+var_18F8+8], r10
0x38385b479  mov     qword ptr [rbp+19E0h+var_18F8+10h], rax
0x38385b480  mov     [rbp+19E0h+var_1914], r10d
0x38385b487  mov     [rbp+19E0h+var_1900], r10d
0x38385b48e  mov     [rbp+19E0h+Src], r10
0x38385b495  test    rcx, rcx
0x38385b498  jnz     loc_38385B947
0x38385b49e  lea     rax, [rbp+19E0h+var_1660]
0x38385b4a5  test    rbx, rbx
0x38385b4a8  cmovnz  rax, rbx
0x38385b4ac  mov     [rbp+19E0h+var_1A40], rax
0x38385b4b0  lea     rsi, [rbp+19E0h+var_1698]
0x38385b4b7  test    rdi, rdi
0x38385b4ba  cmovnz  rsi, rdi
0x38385b4be  mov     [rbp+19E0h+var_1A58], rsi
0x38385b4c2  mov     ecx, [rbp+19E0h+arg_40]
0x38385b4c8  cmp     ecx, 3
0x38385b4cb  jz      loc_38386510A
0x38385b4d1  cmp     ecx, 8
0x38385b4d4  jz      loc_3838650BA
0x38385b4da  cmp     ecx, 0Dh
0x38385b4dd  jz      loc_38386516D
0x38385b4e3  mov     rbx, [rbp+19E0h+pvargSrc]
0x38385b4e7  mov     rdx, rbx; void *
0x38385b4ea  mov     edi, dword ptr [rbp+19E0h+var_1A10]
0x38385b4ed  movzx   ecx, di; unsigned __int16
0x38385b4f0  call    ?CheckBufferAlignment@@YAHGPEAXH@Z; CheckBufferAlignment(ushort,void *,int)
0x38385b4f5  lea     rcx, cs:383800000h
0x38385b4fc  test    eax, eax
0x38385b4fe  jz      loc_38385B94F
0x38385b504  movzx   ecx, di
0x38385b507  mov     eax, ecx
0x38385b509  and     eax, 0FFFF0FFFh
0x38385b50e  cmp     eax, 9
0x38385b511  jz      loc_38385B982
0x38385b517  cmp     eax, 0Ch
0x38385b51a  jz      loc_38385B982
0x38385b520  mov     [rsi], r10d
0x38385b523  mov     [rbp+19E0h+var_1A60], r10d
0x38385b527  mov     [rbp+19E0h+var_193A], di
0x38385b52e  mov     r11d, [rbp+19E0h+var_1A2C]
0x38385b532  mov     [rbp+19E0h+var_1958], r11w
0x38385b53a  btr     ecx, 0Eh
0x38385b53e  mov     edx, 90h
0x38385b543  cmp     ecx, edx
0x38385b545  jz      loc_38385B991
0x38385b54b  mov     edi, 0BFFFh
0x38385b550  mov     ecx, 80h
0x38385b555  lea     r10d, [rcx+2]
0x38385b559  lea     r8d, [rcx+0Dh]
0x38385b55d  cmp     r11w, 0Eh
0x38385b562  ja      loc_38385BA27
0x38385b568  mov     rdi, [rbp+19E0h+Source]
0x38385b56c  mov     eax, [rbp+19E0h+var_1A34]
0x38385b56f  mov     edx, [rbp+19E0h+arg_78]
0x38385b575  test    dl, 1
0x38385b578  jnz     loc_38385BB70
0x38385b57e  test    rdi, rdi
0x38385b581  jz      loc_38385BC66
0x38385b587  mov     r11d, [rbp+19E0h+var_1A2C]
0x38385b58b  mov     r10d, dword ptr [rbp+19E0h+var_1A10]
0x38385b58f  mov     r8d, 0BFFFh
0x38385b595  test    rbx, rbx
0x38385b598  jz      loc_383864D54
0x38385b59e  movsd   xmm10, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x38385b5a7  xorps   xmm8, xmm8
0x38385b5ab  movsd   xmm11, cs:__real@47efffffe0000000
0x38385b5b4  movsd   xmm9, cs:__real@3810000000000000
0x38385b5bd  xorps   xmm7, xmm7
0x38385b5c0  movsd   xmm6, cs:__real@4146924100000000
0x38385b5c8  mov     rax, qword ptr [rbp+19E0h+var_15D8.val+8]
0x38385b5cf  mov     [rbp+19E0h+var_16D0], rax
0x38385b5d6  mov     rdx, qword ptr [rbp+19E0h+var_15D8.val]
0x38385b5dd  mov     [rbp+19E0h+var_1740], rdx
0x38385b5e4  mov     rsi, qword ptr [rbp+19E0h+ui]
0x38385b5e8  mov     r9d, 2000h; unsigned __int64
0x38385b5ee  mov     qword ptr [rbp+19E0h+var_1988], rsi
0x38385b5f2  nop     word ptr [rax+rax]
0x38385b5f7  movzx   eax, r10w
0x38385b5fb  and     ax, r9w
0x38385b5ff  jnz     loc_383863F2A
0x38385b605  test    r9w, r11w
0x38385b609  jnz     loc_383863F2A
0x38385b60f  cmp     r10w, 8
0x38385b614  jz      loc_38385BD40
0x38385b61a  mov     eax, 90h
0x38385b61f  cmp     r10w, ax
0x38385b623  jz      loc_38385BD75
0x38385b629  mov     eax, 81h
0x38385b62e  cmp     r10w, ax
0x38385b632  jnz     loc_38385BE13
0x38385b638  movzx   eax, r11w
0x38385b63c  test    eax, eax
0x38385b63e  js      short loc_38385B652
0x38385b640  cmp     eax, 1
0x38385b643  jle     short loc_38385B66B
0x38385b645  mov     ecx, 80h
0x38385b64a  cmp     eax, ecx
0x38385b64c  jg      loc_38385BDBF
0x38385b652  lea     rax, [rsi+1]
0x38385b656  cmp     rax, 6Fh ; 'o'
0x38385b65a  ja      loc_38385BDDE
0x38385b660  lea     rax, [rbp+19E0h+strIn]
0x38385b667  mov     [rbp+19E0h+lpsz], rax
0x38385b66b  mov     edx, 1; cchWideChar
0x38385b670  movzx   r8d, r10w
0x38385b674  mov     [rbp+19E0h+var_1920], r8d
0x38385b67b  cmp     r8d, 2
0x38385b67f  jl      short loc_38385B698
0x38385b681  cmp     r8d, 3
0x38385b685  jle     loc_38385BE86
0x38385b68b  lea     eax, [r8-10h]
0x38385b68f  cmp     eax, 5
0x38385b692  jbe     loc_38385BE86
0x38385b698  mov     r11d, [rbp+19E0h+var_1A2C]
0x38385b69c  movzx   ecx, r11w
0x38385b6a0  mov     [rbp+19E0h+var_19E0], ecx
0x38385b6a3  mov     eax, r8d
0x38385b6a6  imul    eax, 93h
0x38385b6ac  add     eax, ecx
0x38385b6ae  cmp     eax, 123h
0x38385b6b3  jle     loc_38385C3FE
0x38385b6b9  cmp     eax, 9B3h
0x38385b6be  jle     loc_38385C672
0x38385b6c4  cmp     eax, 4A93h
0x38385b6c9  jg      loc_38385E774
0x38385b6cf  jz      loc_3838605CD; jumptable 000000038385D252 case 1308
0x38385b6d5  cmp     eax, 24C1h
0x38385b6da  jle     loc_38385DB20
0x38385b6e0  cmp     eax, 2959h
0x38385b6e5  jle     loc_38385DEC5
0x38385b6eb  cmp     eax, 4981h
0x38385b6f0  jle     loc_38385E542
0x38385b6f6  sub     eax, 4983h; switch 217 cases
0x38385b6fb  cmp     eax, 0D8h
0x38385b700  ja      def_38385B723; jumptable 000000038385B723 default case, cases 18820-18823,18825-18827,18829-18834,18838-18887,18889-18943,18947,18949-18956,18958,18959,18961,18962,18972,18973,18976,18978,18985-19026,19028-19034
0x38385b706  cdqe
0x38385b708  lea     r9, cs:383800000h
0x38385b70f  movzx   eax, ds:(byte_383865F18 - 383800000h)[r9+rax]
0x38385b718  mov     ecx, ds:(jpt_38385B723 - 383800000h)[r9+rax*4]
0x38385b720  add     rcx, r9
0x38385b723  jmp     rcx; switch jump
0x38385b725  mov     rax, [rbp+19E0h+var_1A40]; jumptable 000000038385B723 case 18971
0x38385b729  mov     qword ptr [rax], 8
0x38385b730  mov     eax, 81h
0x38385b735  cmp     r10w, ax
0x38385b739  jnz     loc_38386192B
0x38385b73f  mov     edx, [rbp+19E0h+ui]; ui
0x38385b742  xor     ecx, ecx; strIn
0x38385b744  call    cs:__imp_SysAllocStringLen
0x38385b74a  mov     [rdi], rax
0x38385b74d  test    rax, rax
0x38385b750  jz      loc_38386476E
0x38385b756  lea     rcx, [rbp+19E0h+var_19D0]
0x38385b75a  mov     [rsp+1AE0h+lpMultiByteStr], rcx; unsigned __int64 *
0x38385b75f  mov     r9, rax; unsigned __int16 *
0x38385b762  mov     r8, qword ptr [rbp+19E0h+ui]; unsigned __int64
0x38385b766  mov     rbx, [rbp+19E0h+pvargSrc]
0x38385b76a  mov     rdx, rbx; char *
0x38385b76d  mov     ecx, [rbp+19E0h+arg_68]; CodePage
0x38385b773  call    ?GetWStrFromStr@@YAJIPEBD_KPEAGPEA_K@Z; GetWStrFromStr(uint,char const *,unsigned __int64,ushort *,unsigned __int64 *)
0x38385b778  mov     r10d, eax
0x38385b77b  mov     [rbp+19E0h+var_1A60], eax
0x38385b77e  mov     rax, [rbp+19E0h+var_19D0]
0x38385b782  cmp     qword ptr [rbp+19E0h+ui], rax
0x38385b786  jnz     loc_383861914
0x38385b78c  test    r10d, r10d
0x38385b78f  js      loc_383861CB1
0x38385b795  jmp     short $+2
0x38385b797  cmp     qword ptr [rdi], 0
0x38385b79b  jz      loc_38386476E
0x38385b7a1  mov     esi, [rbp+19E0h+var_1A60]
0x38385b7a4  jmp     short $+2
0x38385b7a6  lea     r9, cs:383800000h
0x38385b7ad  jmp     short $+2
0x38385b7af  mov     rdx, [rbp+19E0h+var_1A58]; unsigned int *
0x38385b7b3  cmp     [rbp+19E0h+var_19E0], 7
0x38385b7b7  jz      loc_383863E98
0x38385b7bd  cmp     word ptr [rbp+19E0h+pvarg], 0; jumptable 0000000383863EC0 default case, cases 4-15
0x38385b7c2  jnz     loc_383864DAC
0x38385b7c8  mov     rbx, [rbp+19E0h+var_1A40]
0x38385b7cc  mov     rdi, [rbp+19E0h+Source]
0x38385b7d0  cmp     word ptr [rbp+19E0h+var_18F8], 0
0x38385b7d8  jnz     loc_383864DBC
0x38385b7de  test    esi, esi
0x38385b7e0  js      loc_383864DCF
0x38385b7e6  cmp     esi, 50h ; 'P'
0x38385b7e9  jz      loc_383864DCF
0x38385b7ef  mov     rcx, [rbp+19E0h+var_1A58]
0x38385b7f3  mov     r8d, 2
0x38385b7f9  mov     edx, [rbp+19E0h+arg_78]
0x38385b7ff  mov     eax, edx
0x38385b801  and     eax, 30h
0x38385b804  mov     r11d, 85h
0x38385b80a  cmp     al, 30h ; '0'
0x38385b80c  jz      loc_383864EBF
0x38385b812  mov     r9d, [rbp+19E0h+var_1A2C]
0x38385b816  test    dl, 1
0x38385b819  jnz     loc_383864F1F
0x38385b81f  mov     rbx, [rbp+19E0h+lpsz]
0x38385b823  test    rbx, rbx
0x38385b826  jz      short loc_38385B835
0x38385b828  cmp     [rbp+19E0h+var_195C], 0
0x38385b82f  jnz     loc_383865032
0x38385b835  test    rdi, rdi
0x38385b838  jz      short loc_38385B847
0x38385b83a  cmp     [rbp+19E0h+var_1918], 0
0x38385b841  jnz     loc_383865048
0x38385b847  test    esi, esi
0x38385b849  js      loc_383865179
0x38385b84f  mov     rcx, [rbp+19E0h+var_1A58]
0x38385b853  mov     eax, [rcx]
0x38385b855  test    eax, eax
0x38385b857  jnz     loc_38386505E
0x38385b85d  test    byte ptr cs:_bidGblFlags, 2
0x38385b864  jnz     loc_383865182
0x38385b86a  mov     eax, esi
0x38385b86c  mov     rcx, [rbp+19E0h+var_90]
0x38385b873  xor     rcx, rsp; StackCookie
0x38385b876  call    __security_check_cookie
0x38385b87b  lea     r11, [rsp+1AE0h+var_18]
0x38385b883  movaps  xmm6, xmmword ptr [r11-18h]
0x38385b888  movaps  xmm7, xmmword ptr [r11-28h]
0x38385b88d  movaps  xmm8, xmmword ptr [r11-38h]
0x38385b892  movaps  xmm9, xmmword ptr [r11-48h]
0x38385b897  movaps  xmm10, xmmword ptr [r11-58h]
0x38385b89c  movaps  xmm11, xmmword ptr [r11-68h]
0x38385b8a1  mov     rsp, r11
0x38385b8a4  pop     rdi
0x38385b8a5  pop     rsi
0x38385b8a6  pop     rbx
0x38385b8a7  pop     rbp
0x38385b8a8  retn
0x38385b8a9  mov     rax, cs:off_383B49608; "<IDataConvert::DataConvert|OLEDB|API> w"...
0x38385b8b0  test    rax, rax
0x38385b8b3  jz      short loc_38385B933
0x38385b8b5  movzx   ecx, [rbp+19E0h+var_1A38]
0x38385b8b9  movzx   edx, [rbp+19E0h+arg_50]
0x38385b8c0  movzx   r8d, r8w
0x38385b8c4  movzx   r9d, si
0x38385b8c8  mov     eax, [rbp+19E0h+arg_78]
0x38385b8ce  mov     [rsp+1AE0h+var_1A70], eax
0x38385b8d2  mov     [rsp+1AE0h+var_1A78], ecx
0x38385b8d6  mov     dword ptr [rsp+1AE0h+var_1A80], edx
  ... truncated ...
```
