# CImportRowset::Init(CImportStream *,tagIMPORT_INFO *,unsigned __int64,tagIMPORT_COLINFO * const,unsigned __int64,tagIMPORT_KEYINFO * const,unsigned __int64,uchar * const,unsigned __int64,uchar * const,unsigned __int64,uchar * const,unsigned __int64,uchar * const,CBcpImport *,DELIMITER_INFO *,int,unsigned __int64,int,int,int,bool,bool,bool,bool)

- ea: `0x10209ff20`
- end: `0x1020a150b`
- name: `?Init@CImportRowset@@QEAAJPEAVCImportStream@@PEAUtagIMPORT_INFO@@_KQEAUtagIMPORT_COLINFO@@2QEAUtagIMPORT_KEYINFO@@2QEAE252525PEAVCBcpImport@@PEAUDELIMITER_INFO@@H2HHH_N888@Z`
- size: `5611`
- prototype: `__int64 __usercall@<rax>(CImportRowset *__hidden this@<rcx>, struct CImportStream *@<rdx>, struct tagIMPORT_INFO *@<r8>, unsigned __int64@<r9>, struct tagIMPORT_COLINFO *const, unsigned __int64, struct tagIMPORT_KEYINFO *const Source, unsigned __int64 cchWideChar, LPCWCH lpWideCharStr, rsize_t DestinationSize, LPCWCH, rsize_t SourceSize, LPCWCH, unsigned __int64, LPCWCH, struct CBcpImport *, struct DELIMITER_INFO *, int, unsigned __int64, int, int, int, bool, bool, bool, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x102097910`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100415e90`
- `0x102078d60`
- `0x102099d90`
- `0x10209a310`
- `0x10209d5c0`
- `0x10209ff20`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1020a0963`
- `KERNEL32!WideCharToMultiByte` at `0x1020a09ab`
- `KERNEL32!WideCharToMultiByte` at `0x1020a0a84`
- `KERNEL32!WideCharToMultiByte` at `0x1020a0b5f`
- `KERNEL32!WideCharToMultiByte` at `0x1020a0963`
- `KERNEL32!WideCharToMultiByte` at `0x1020a09ab`
- `KERNEL32!WideCharToMultiByte` at `0x1020a0a84`
- `KERNEL32!WideCharToMultiByte` at `0x1020a0b5f`
- `KERNEL32!GetLastError` at `0x1020a0c9a`
- `KERNEL32!GetLastError` at `0x1020a0ca4`
- `KERNEL32!GetLastError` at `0x1020a0cb5`
- `KERNEL32!GetLastError` at `0x1020a0cbf`
- `KERNEL32!GetLastError` at `0x1020a0ce9`
- `KERNEL32!GetLastError` at `0x1020a0cf7`
- `KERNEL32!GetLastError` at `0x1020a0c9a`
- `KERNEL32!GetLastError` at `0x1020a0ca4`
- `KERNEL32!GetLastError` at `0x1020a0cb5`
- `KERNEL32!GetLastError` at `0x1020a0cbf`
- `KERNEL32!GetLastError` at `0x1020a0ce9`
- `KERNEL32!GetLastError` at `0x1020a0cf7`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1020a0539`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1020a057b`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1020a0667`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1020a0753`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1020a0539`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1020a057b`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1020a0667`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1020a0753`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0123`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0636`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0724`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0a49`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0b23`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0f78`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0fdf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a1046`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0123`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0636`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0724`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0a49`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0b23`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0f78`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0fdf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a1046`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a01aa`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a024d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0df8`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0e6d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0ee2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a11c9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a125e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a12eb`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a137c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a1411`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a149e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a01aa`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a024d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0df8`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0e6d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a0ee2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a11c9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a125e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a12eb`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a137c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a1411`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020a149e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020a0486`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020a0486`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1020a03b2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1020a03b2`
- `sqldk!SystemThread_TlsIndex` at `0x1020a00c1`
- `sqldk!SystemThread_TlsIndex` at `0x1020a0157`
- `sqldk!SystemThread_TlsIndex` at `0x1020a01fa`
- `sqldk!SystemThread_TlsIndex` at `0x1020a033f`
- `sqldk!SystemThread_TlsIndex` at `0x1020a05d2`
- `sqldk!SystemThread_TlsIndex` at `0x1020a06c0`
- `sqldk!SystemThread_TlsIndex` at `0x1020a09fd`
- `sqldk!SystemThread_TlsIndex` at `0x1020a0ad6`
- `sqldk!SystemThread_TlsIndex` at `0x1020a0da9`
- `sqldk!SystemThread_TlsIndex` at `0x1020a0e1e`
- `sqldk!SystemThread_TlsIndex` at `0x1020a0e93`
- `sqldk!SystemThread_TlsIndex` at `0x1020a0f2b`
- `sqldk!SystemThread_TlsIndex` at `0x1020a0f92`
- `sqldk!SystemThread_TlsIndex` at `0x1020a0ff9`
- `sqldk!SystemThread_TlsIndex` at `0x1020a1176`
- `sqldk!SystemThread_TlsIndex` at `0x1020a120b`
- `sqldk!SystemThread_TlsIndex` at `0x1020a1298`
- `sqldk!SystemThread_TlsIndex` at `0x1020a1329`
- `sqldk!SystemThread_TlsIndex` at `0x1020a13be`
- `sqldk!SystemThread_TlsIndex` at `0x1020a144b`
- `sqldk!SystemThread_TlsOffset` at `0x1020a00ca`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0160`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0203`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0348`
- `sqldk!SystemThread_TlsOffset` at `0x1020a05db`
- `sqldk!SystemThread_TlsOffset` at `0x1020a06c9`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0a06`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0adf`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0db2`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0e27`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0e9c`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0f34`
- `sqldk!SystemThread_TlsOffset` at `0x1020a0f9b`
- `sqldk!SystemThread_TlsOffset` at `0x1020a1002`
- `sqldk!SystemThread_TlsOffset` at `0x1020a117f`
- `sqldk!SystemThread_TlsOffset` at `0x1020a1214`
- `sqldk!SystemThread_TlsOffset` at `0x1020a12a1`
- `sqldk!SystemThread_TlsOffset` at `0x1020a1332`
- `sqldk!SystemThread_TlsOffset` at `0x1020a13c7`
- `sqldk!SystemThread_TlsOffset` at `0x1020a1454`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a00e3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a017b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a021e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0366`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a05f6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a06e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0a21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0afa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0dcd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0e42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0eb7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0f4f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0fb6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a101d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a119a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a122f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a12bc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a134d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a13e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a146f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a00e3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a017b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a021e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0366`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a05f6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a06e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0a21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0afa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0dcd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0e42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0eb7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0f4f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a0fb6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a101d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a119a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a122f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a12bc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a134d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a13e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020a146f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0646`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0734`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0765`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0772`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a088e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0898`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0a59`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0b33`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0c7e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0c88`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0cd1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0cde`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0646`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0734`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0765`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0772`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a088e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0898`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0a59`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0b33`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0c7e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0c88`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0cd1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020a0cde`
- `sqllang!?ImpPrintError@@YAJKK_KKK0QEB_W0101I_NPEA_W@Z` at `0x1020a0884`
- `sqllang!?ImpPrintError@@YAJKK_KKK0QEB_W0101I_NPEA_W@Z` at `0x1020a0c74`
- `sqllang!?ImpPrintError@@YAJKK_KKK0QEB_W0101I_NPEA_W@Z` at `0x1020a0884`
- `sqllang!?ImpPrintError@@YAJKK_KKK0QEB_W0101I_NPEA_W@Z` at `0x1020a0c74`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x1020a1112`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x1020a1112`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CImportRowset::Init(
        CImportRowset *this,
        struct CImportStream *a2,
        struct tagIMPORT_INFO *a3,
        unsigned __int64 a4,
        struct tagIMPORT_COLINFO *const a5,
        unsigned __int64 a6,
        struct tagIMPORT_KEYINFO *const Source,
        unsigned __int64 cchWideChar,
        CHAR *lpWideCharStr,
        rsize_t DestinationSize,
        CHAR *a11,
        rsize_t SourceSize,
        char *a13,
        unsigned __int64 a14,
        char *a15,
        struct CBcpImport *a16,
        struct DELIMITER_INFO *a17,
        int a18,
        unsigned __int64 a19,
        int a20,
        int a21,
        int a22,
        bool a23,
        bool a24,
        bool a25,
        bool a26)
{
  struct tagIMPORT_COLINFO *v30; // r13
  struct DELIMITER_INFO *v31; // r12
  unsigned __int64 v32; // r8
  BOOL v33; // eax
  __int64 v34; // rbx
  __int64 v35; // rcx
  unsigned __int64 v36; // rax
  void *v37; // rax
  __int64 v38; // rbx
  __int64 v39; // rdx
  struct IMemObj *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rdx
  CHAR *v44; // rax
  CHAR *v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rdi
  __int64 v49; // r10
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rax
  void *v52; // rax
  signed int LastError; // esi
  __int64 v54; // rcx
  CHAR *v55; // rdi
  int v56; // eax
  int v57; // edx
  int v58; // eax
  unsigned __int64 v59; // r8
  __int64 v60; // rcx
  unsigned __int64 v61; // rcx
  void *v62; // rsp
  void *v63; // rsp
  unsigned __int8 *v64; // r15
  unsigned __int64 v65; // rbx
  __int64 v66; // rcx
  unsigned __int64 v67; // rcx
  void *v68; // rsp
  void *v69; // rsp
  CHAR *v70; // rsi
  int v71; // eax
  int v72; // eax
  unsigned int v73; // r13d
  wchar_t *v74; // rbx
  __int64 v75; // rbx
  __int64 v76; // r10
  unsigned __int64 v77; // rax
  int v78; // eax
  unsigned int v79; // r9d
  wchar_t *v80; // rdi
  __int64 v81; // rbx
  __int64 v82; // r10
  unsigned __int64 v83; // rax
  int v84; // eax
  unsigned __int64 v85; // r10
  _WORD *v86; // rax
  unsigned __int64 v87; // rcx
  unsigned __int64 v88; // rsi
  __int64 v89; // rdx
  __int64 v90; // rcx
  rsize_t v91; // rdi
  unsigned __int64 cbMultiByte; // r8
  __int64 v93; // rcx
  unsigned __int64 v94; // rcx
  void *v95; // rsp
  void *v96; // rsp
  unsigned __int8 *v97; // r13
  unsigned __int64 v98; // rbx
  __int64 v99; // rcx
  void *v100; // rsp
  void *v101; // rsp
  unsigned __int8 *v102; // r15
  int v103; // eax
  int v104; // eax
  unsigned __int64 v105; // r12
  CHAR *lpMultiByteStr; // rbx
  unsigned int v107; // edi
  __int64 v108; // rbx
  __int64 v109; // rdx
  int v110; // eax
  unsigned __int64 v111; // r9
  unsigned int v112; // r15d
  __int64 v113; // rbx
  __int64 v114; // rdx
  int v115; // eax
  unsigned __int64 v116; // r10
  _WORD *v117; // rax
  unsigned __int64 v118; // rcx
  __int64 v119; // rbx
  __int64 v120; // rdx
  _OWORD *v121; // rax
  __int64 v122; // rbx
  __int64 v123; // rdx
  _OWORD *v124; // rax
  __int64 v125; // rbx
  __int64 v126; // rdx
  _OWORD *v127; // rax
  __int64 v128; // rbx
  __int64 v129; // rdx
  __int64 v130; // rbx
  __int64 v131; // rdx
  __int64 v132; // rbx
  __int64 v133; // rdx
  __int64 v134; // rax
  __int64 v135; // rbx
  __int64 v136; // rbx
  __int64 v137; // rdx
  CHAR *v138; // rax
  __int64 v139; // rcx
  __int64 v140; // rbx
  __int64 v141; // rdx
  CHAR *v142; // rax
  __int64 v143; // rbx
  __int64 v144; // rdx
  CHAR *v145; // rax
  __int64 v146; // rbx
  __int64 v147; // rdx
  CHAR *v148; // rax
  __int64 v149; // rbx
  __int64 v150; // rdx
  CHAR *v151; // rax
  __int64 v152; // rbx
  __int64 v153; // rdx
  CHAR *v154; // rax
  unsigned __int8 *v156; // [rsp+48h] [rbp-38h]
  CHAR MultiByteStr[8]; // [rsp+80h] [rbp+0h] BYREF
  CHAR *v158; // [rsp+88h] [rbp+8h]
  wchar_t *v159; // [rsp+90h] [rbp+10h]
  struct IMemObj *v160; // [rsp+98h] [rbp+18h]
  CHAR *v161; // [rsp+A0h] [rbp+20h]
  CHAR *v162; // [rsp+A8h] [rbp+28h]
  unsigned __int64 v163; // [rsp+B0h] [rbp+30h]
  struct tagIMPORT_INFO *v164; // [rsp+B8h] [rbp+38h]
  struct CBcpImport *v165; // [rsp+C0h] [rbp+40h]
  __int64 v166; // [rsp+C8h] [rbp+48h]
  unsigned __int64 cchWideChara; // [rsp+148h] [rbp+C8h]
  unsigned __int64 cchWideCharb; // [rsp+148h] [rbp+C8h]
  rsize_t DestinationSizea; // [rsp+158h] [rbp+D8h]
  rsize_t DestinationSizeb; // [rsp+158h] [rbp+D8h]

  v166 = -2;
  v163 = a4;
  v164 = a3;
  v165 = a16;
  (*(void (__fastcall **)(struct CBcpImport *))(*(_QWORD *)a16 + 8LL))(a16);
  if ( a18 || a21 || a22 || a25 )
  {
    *((_QWORD *)this + 27) = a4;
    v30 = a5;
    *((_QWORD *)this + 25) = a5;
    v31 = a17;
    *((_QWORD *)this + 26) = a17;
  }
  else
  {
    v30 = a5;
    v31 = a17;
  }
  v32 = a6;
  *((_QWORD *)this + 13) = a6;
  *((_DWORD *)this + 30) = *((_DWORD *)a3 + 10);
  *((_DWORD *)this + 31) = *((_DWORD *)a3 + 11);
  *((_DWORD *)this + 32) = *((_DWORD *)a3 + 15);
  *((_DWORD *)this + 37) = *((_DWORD *)a3 + 16);
  *((_DWORD *)this + 38) = *((_DWORD *)a3 + 17);
  *((_DWORD *)this + 39) = *((_DWORD *)a3 + 12);
  *((_QWORD *)this + 22) = *((_QWORD *)a3 + 9);
  *((_DWORD *)this + 46) = *((_DWORD *)a3 + 20);
  *((_DWORD *)this + 47) = *((_DWORD *)a3 + 21);
  *((_DWORD *)this + 33) = a18;
  *((_DWORD *)this + 34) = a22;
  *((_BYTE *)this + 140) = a23;
  *((_QWORD *)this + 21) = a2;
  *((_BYTE *)this + 141) = *((_BYTE *)a3 + 108);
  v33 = *((_QWORD *)a3 + 12) || *((_DWORD *)a3 + 26);
  *((_DWORD *)this + 48) = v33;
  *((_BYTE *)this + 196) = a24;
  *((_BYTE *)this + 197) = a26;
  if ( a6 )
  {
    v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v35 = *(_QWORD *)(v34 + 256);
    if ( !v35 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v35 = *(_QWORD *)(v34 + 256);
      v32 = *((_QWORD *)this + 13);
    }
    v36 = 16 * v32;
    if ( !is_mul_ok(v32, 0x10u) )
      v36 = -1;
    v37 = operator new[](
            v36,
            *(struct IMemObj **)(v35 + 1000),
            "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
            310,
            5u);
    *((_QWORD *)this + 14) = v37;
    memcpy_s(v37, 16LL * *((_QWORD *)this + 13), Source, 16LL * *((_QWORD *)this + 13));
  }
  *(_DWORD *)MultiByteStr = 317;
  v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v39 = *(_QWORD *)(v38 + 256);
  if ( !v39 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v39 = *(_QWORD *)(v38 + 256);
  }
  v161 = *(CHAR **)(v39 + 1000);
  v40 = (struct IMemObj *)operator new(
                            0x40u,
                            (struct IMemObj *)v161,
                            "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
                            317,
                            5u);
  v160 = v40;
  if ( v40 )
  {
    v41 = *((_QWORD *)this + 5);
    *(_QWORD *)v40 = 0;
    *((_QWORD *)v40 + 1) = 0;
    *((_QWORD *)v40 + 2) = 0;
    *((_DWORD *)v40 + 6) = 0;
    *((_QWORD *)v40 + 4) = &CBufSwitchSink::`vftable';
    *((_QWORD *)v40 + 5) = 0;
    *((_QWORD *)v40 + 6) = v41;
    *((_QWORD *)v40 + 7) = 0;
  }
  *((_QWORD *)this + 1) = v40;
  *(_DWORD *)MultiByteStr = 319;
  v42 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v43 = *(_QWORD *)(v42 + 256);
  if ( !v43 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v43 = *(_QWORD *)(v42 + 256);
  }
  v160 = *(struct IMemObj **)(v43 + 1000);
  v44 = (CHAR *)operator new(0xB8u, v160, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp", 319, 5u);
  v45 = v44;
  v161 = v44;
  if ( v44 )
  {
    v165 = 0;
    v46 = *((_QWORD *)this + 21);
    v47 = *((_QWORD *)this + 1);
    *(_QWORD *)v44 = &CImpRowset::`vftable';
    *((_QWORD *)v44 + 1) = this;
    *((_QWORD *)v44 + 2) = this;
    *((_QWORD *)v44 + 3) = v47;
    *((_QWORD *)v44 + 4) = v46;
    *((_QWORD *)v44 + 5) = 0;
    *((_QWORD *)v44 + 6) = a19;
    *((_QWORD *)v44 + 7) = 0;
    *((_DWORD *)v44 + 16) = 0;
    *((_QWORD *)v44 + 9) = 0;
    *((_QWORD *)v44 + 10) = 0;
    *((_DWORD *)v44 + 22) = *((_DWORD *)a3 + 2);
    *((_QWORD *)v44 + 12) = *((_QWORD *)a3 + 2);
    *((_QWORD *)v44 + 13) = *((_QWORD *)a3 + 3);
    *((_QWORD *)v44 + 14) = *((_QWORD *)a3 + 4);
    *((_QWORD *)v44 + 15) = 0;
    *((_QWORD *)v44 + 17) = 0;
    *((_DWORD *)v44 + 36) = *((_DWORD *)this + 36);
    *((_DWORD *)v44 + 37) = *((_DWORD *)this + 48);
    *((_DWORD *)v44 + 38) = 0;
    *((_WORD *)v44 + 78) = 0;
    v44[158] = 0;
    *((_QWORD *)v44 + 20) = a16;
    *((_QWORD *)v44 + 21) = *((_QWORD *)a3 + 14);
    *((_QWORD *)v44 + 22) = *((_QWORD *)a3 + 17);
  }
  else
  {
    v45 = 0;
  }
  *((_QWORD *)this + 5) = v45;
  *((_QWORD *)v45 + 16) = a4;
  v48 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v49 = *(_QWORD *)(v48 + 256);
  v50 = a4;
  if ( !v49 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v49 = *(_QWORD *)(v48 + 256);
    v50 = *((_QWORD *)v45 + 16);
  }
  v51 = 8 * (v50 + 1);
  if ( !is_mul_ok(v50 + 1, 8u) )
    v51 = -1;
  v52 = operator new[](
          v51,
          *(struct IMemObj **)(v49 + 1000),
          1,
          "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impirow.cpp",
          143,
          5u);
  *((_QWORD *)v45 + 9) = v52;
  if ( !v52 )
    goto LABEL_31;
  memset_0(v52, 0, 8LL * *((_QWORD *)v45 + 16) + 8);
  v54 = *((_QWORD *)v45 + 1);
  v55 = 0;
  *((_DWORD *)v45 + 35) = *(_DWORD *)(v54 + 148) == 6;
  *((_DWORD *)v45 + 38) = *(_DWORD *)(v54 + 136);
  v45[156] = *(_BYTE *)(v54 + 140);
  v45[157] = *(_BYTE *)(v54 + 141);
  v45[158] = byte_10316E9B1;
  if ( *(_DWORD *)(v54 + 148) == 4 )
    *(_DWORD *)(v54 + 148) = 1;
  *(_QWORD *)MultiByteStr = 2;
  if ( a20 != 1 )
    goto LABEL_120;
  if ( *((_DWORD *)this + 48) )
  {
    v56 = *((_DWORD *)this + 37);
    if ( v56 )
    {
      if ( v56 != 1 )
        goto LABEL_41;
      v57 = 9;
    }
    else
    {
      v57 = 6;
    }
    ex_raise(48, v57, 16, 1);
  }
LABEL_41:
  v58 = *((_DWORD *)this + 37);
  if ( !v58 )
  {
    *((_DWORD *)this + 37) = 1;
    v59 = (unsigned int)(2 * cchWideChar + 2);
    v60 = v59 + 15;
    if ( v59 + 15 <= v59 )
      v60 = 0xFFFFFFFFFFFFFF0LL;
    v61 = v60 & 0xFFFFFFFFFFFFFFF0uLL;
    v62 = alloca(v61);
    v63 = alloca(v61);
    v64 = (unsigned __int8 *)MultiByteStr;
    v158 = MultiByteStr;
    v65 = (unsigned int)(2 * DestinationSize + 2);
    v66 = v65 + 15;
    if ( v65 + 15 <= v65 )
      v66 = 0xFFFFFFFFFFFFFF0LL;
    v67 = v66 & 0xFFFFFFFFFFFFFFF0uLL;
    v68 = alloca(v67);
    v69 = alloca(v67);
    v70 = MultiByteStr;
    v161 = MultiByteStr;
    v71 = FastDBCSToUnicode(
            *((_DWORD *)this + 31),
            lpWideCharStr,
            cchWideChar,
            (wchar_t *)MultiByteStr,
            (unsigned int)v59 >> 1);
    if ( !v71 && cchWideChar )
    {
      LastError = -2147467259;
      goto LABEL_189;
    }
    lpWideCharStr = MultiByteStr;
    cchWideChara = (unsigned int)(2 * v71);
    v72 = FastDBCSToUnicode(
            *((_DWORD *)this + 31),
            a11,
            DestinationSize,
            (wchar_t *)MultiByteStr,
            (unsigned int)v65 >> 1);
    if ( !v72 && DestinationSize )
      goto LABEL_51;
    a11 = MultiByteStr;
    DestinationSizea = (unsigned int)(2 * v72);
    v73 = 0;
    v74 = 0;
    v159 = 0;
    if ( a13 )
    {
      v75 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v76 = *(_QWORD *)(v75 + 256);
      if ( !v76 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v76 = *(_QWORD *)(v75 + 256);
      }
      v77 = 2 * (SourceSize + 1);
      if ( !is_mul_ok(SourceSize + 1, 2u) )
        v77 = -1;
      v74 = (wchar_t *)operator new[](
                         v77,
                         *(struct IMemObj **)(v76 + 1000),
                         "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
                         408,
                         5u);
      if ( v74 )
        operator delete[](0);
      v159 = v74;
      v78 = FastDBCSToUnicode(*((_DWORD *)this + 31), a13, SourceSize, v74, (unsigned int)(2 * SourceSize + 2) >> 1);
      if ( !v78 && SourceSize )
        goto LABEL_72;
      v73 = 2 * v78;
      a13 = (char *)v74;
      SourceSize = (unsigned int)(2 * v78);
    }
    v79 = 0;
    v80 = 0;
    v162 = 0;
    if ( a15 )
    {
      v81 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v82 = *(_QWORD *)(v81 + 256);
      if ( !v82 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v82 = *(_QWORD *)(v81 + 256);
      }
      v83 = 2 * (a14 + 1);
      if ( !is_mul_ok(a14 + 1, 2u) )
        v83 = -1;
      v80 = (wchar_t *)operator new[](
                         v83,
                         *(struct IMemObj **)(v82 + 1000),
                         "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
                         436,
                         5u);
      if ( v80 )
        operator delete[](0);
      v162 = (CHAR *)v80;
      v84 = FastDBCSToUnicode(*((_DWORD *)this + 31), a15, a14, v80, (unsigned int)(2 * a14 + 2) >> 1);
      if ( !v84 && a14 )
      {
        operator delete[](v80);
        v74 = v159;
LABEL_72:
        operator delete[](v74);
        LastError = -2147467259;
        goto LABEL_189;
      }
      v79 = 2 * v84;
      v74 = v159;
      v70 = v161;
      v64 = (unsigned __int8 *)v158;
    }
    v85 = v163;
    if ( v163 && a5 )
    {
      v86 = (_WORD *)((char *)a5 + 70);
      v87 = v163;
      do
      {
        if ( *v86 == 129 )
          *v86 = 130;
        v86 += 192;
        --v87;
      }
      while ( v87 );
    }
    v156 = (unsigned __int8 *)v70;
    v88 = cchWideChara;
    CImportColumns::Init(
      *((CImportColumns **)this + 1),
      v85,
      a5,
      *((struct CImportStream **)this + 21),
      this,
      v164,
      cchWideChara,
      v64,
      DestinationSizea,
      v156,
      v73,
      (unsigned __int8 *const)v74,
      v79,
      (unsigned __int8 *const)v80,
      a17);
    ImpPrintError(0x1Eu, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0x10u, 1, 0);
    operator delete[](v80);
    operator delete[](v74);
    v91 = DestinationSizea;
    goto LABEL_121;
  }
  if ( v58 == 1 )
  {
    *((_DWORD *)this + 37) = 0;
    cbMultiByte = (unsigned int)(cchWideChar + 1);
    v93 = cbMultiByte + 15;
    if ( cbMultiByte + 15 <= cbMultiByte )
      v93 = 0xFFFFFFFFFFFFFF0LL;
    v94 = v93 & 0xFFFFFFFFFFFFFFF0uLL;
    v95 = alloca(v94);
    v96 = alloca(v94);
    v97 = (unsigned __int8 *)MultiByteStr;
    v162 = MultiByteStr;
    v98 = (unsigned int)(DestinationSize + 1);
    v99 = v98 + 15;
    if ( v98 + 15 <= v98 )
      v99 = 0xFFFFFFFFFFFFFF0LL;
    v100 = alloca(v99 & 0xFFFFFFFFFFFFFFF0uLL);
    v101 = alloca(v99 & 0xFFFFFFFFFFFFFFF0uLL);
    v102 = (unsigned __int8 *)MultiByteStr;
    v161 = MultiByteStr;
    if ( !MultiByteStr )
    {
LABEL_31:
      LastError = -2147024882;
      goto LABEL_189;
    }
    v103 = WideCharToMultiByte(
             *((_DWORD *)this + 31),
             0,
             (LPCWCH)lpWideCharStr,
             cchWideChar,
             MultiByteStr,
             cbMultiByte,
             0,
             0);
    if ( !v103
      || (lpWideCharStr = MultiByteStr,
          cchWideCharb = (unsigned int)((unsigned __int64)v103 >> 1),
          (v104 = WideCharToMultiByte(*((_DWORD *)this + 31), 0, (LPCWCH)a11, DestinationSize, MultiByteStr, v98, 0, 0)) == 0) )
    {
      if ( !GetLastError() )
      {
LABEL_51:
        LastError = -2147467259;
        goto LABEL_189;
      }
      LastError = GetLastError();
      goto LABEL_189;
    }
    a11 = MultiByteStr;
    DestinationSizeb = (unsigned int)((unsigned __int64)v104 >> 1);
    LODWORD(v105) = 0;
    lpMultiByteStr = 0;
    v159 = 0;
    if ( a13 )
    {
      v107 = SourceSize + 1;
      v108 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v109 = *(_QWORD *)(v108 + 256);
      if ( !v109 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v109 = *(_QWORD *)(v108 + 256);
      }
      lpMultiByteStr = (CHAR *)operator new[](
                                 v107,
                                 *(struct IMemObj **)(v109 + 1000),
                                 "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
                                 556,
                                 5u);
      if ( lpMultiByteStr )
        operator delete[](0);
      v159 = (wchar_t *)lpMultiByteStr;
      v110 = WideCharToMultiByte(*((_DWORD *)this + 31), 0, (LPCWCH)a13, SourceSize, lpMultiByteStr, v107, 0, 0);
      if ( !v110 )
      {
        if ( GetLastError() )
          LastError = GetLastError();
        else
          LastError = -2147467259;
        goto LABEL_117;
      }
      v105 = (unsigned __int64)v110 >> 1;
      a13 = lpMultiByteStr;
      SourceSize = (unsigned int)v105;
      v55 = 0;
    }
    LODWORD(v111) = 0;
    v158 = 0;
    if ( !a15 )
      goto LABEL_103;
    v112 = a14 + 1;
    v113 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v114 = *(_QWORD *)(v113 + 256);
    if ( !v114 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v114 = *(_QWORD *)(v113 + 256);
    }
    v55 = (CHAR *)operator new[](
                    v112,
                    *(struct IMemObj **)(v114 + 1000),
                    "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
                    587,
                    5u);
    if ( v55 )
      operator delete[](0);
    v158 = v55;
    v115 = WideCharToMultiByte(*((_DWORD *)this + 31), 0, (LPCWCH)a15, a14, v55, v112, 0, 0);
    if ( v115 )
    {
      v111 = (unsigned __int64)v115 >> 1;
      lpMultiByteStr = (CHAR *)v159;
      v102 = (unsigned __int8 *)v161;
      v97 = (unsigned __int8 *)v162;
LABEL_103:
      v116 = v163;
      if ( v163 && a5 )
      {
        v117 = (_WORD *)((char *)a5 + 70);
        v118 = v163;
        do
        {
          if ( *v117 == 130 )
            *v117 = 129;
          v117 += 192;
          --v118;
        }
        while ( v118 );
      }
      v88 = cchWideCharb;
      CImportColumns::Init(
        *((CImportColumns **)this + 1),
        v116,
        a5,
        *((struct CImportStream **)this + 21),
        this,
        v164,
        cchWideCharb,
        v97,
        DestinationSizeb,
        v102,
        (unsigned int)v105,
        (unsigned __int8 *const)lpMultiByteStr,
        (unsigned int)v111,
        (unsigned __int8 *const)v55,
        a17);
      ImpPrintError(0x1Fu, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0x10u, 1, 0);
      operator delete[](v55);
      operator delete[](lpMultiByteStr);
      v91 = DestinationSizeb;
      goto LABEL_121;
    }
    if ( GetLastError() )
      LastError = GetLastError();
    else
      LastError = -2147467259;
    operator delete[](v55);
    lpMultiByteStr = (CHAR *)v159;
LABEL_117:
    operator delete[](lpMultiByteStr);
    goto LABEL_189;
  }
LABEL_120:
  v91 = DestinationSize;
  CImportColumns::Init(
    *((CImportColumns **)this + 1),
    a4,
    v30,
    *((struct CImportStream **)this + 21),
    this,
    a3,
    cchWideChar,
    (unsigned __int8 *const)lpWideCharStr,
    DestinationSize,
    (unsigned __int8 *const)a11,
    SourceSize,
    (unsigned __int8 *const)a13,
    a14,
    (unsigned __int8 *const)a15,
    v31);
  v88 = cchWideChar;
LABEL_121:
  if ( a22 )
  {
    v119 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v120 = *(_QWORD *)(v119 + 256);
    if ( !v120 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v120 = *(_QWORD *)(v119 + 256);
    }
    v121 = operator new(
             0x10u,
             *(struct IMemObj **)(v120 + 1000),
             "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
             688,
             5u);
    if ( v121 )
      *v121 = 0;
    else
      v121 = 0;
    *((_QWORD *)this + 28) = v121;
    v122 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v123 = *(_QWORD *)(v122 + 256);
    if ( !v123 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v123 = *(_QWORD *)(v122 + 256);
    }
    v124 = operator new(
             0x10u,
             *(struct IMemObj **)(v123 + 1000),
             "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
             689,
             5u);
    if ( v124 )
      *v124 = 0;
    else
      v124 = 0;
    *((_QWORD *)this + 29) = v124;
    v125 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v126 = *(_QWORD *)(v125 + 256);
    if ( !v126 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v126 = *(_QWORD *)(v125 + 256);
    }
    v127 = operator new(
             0x10u,
             *(struct IMemObj **)(v126 + 1000),
             "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
             690,
             5u);
    if ( v127 )
      *v127 = 0;
    else
      v127 = 0;
    *((_QWORD *)this + 30) = v127;
    **((_DWORD **)this + 28) = v88;
    **((_DWORD **)this + 29) = v91;
    **((_DWORD **)this + 30) = SourceSize;
    v128 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v129 = *(_QWORD *)(v128 + 256);
    if ( !v129 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v129 = *(_QWORD *)(v128 + 256);
    }
    *(_QWORD *)(*((_QWORD *)this + 28) + 8LL) = operator new[](
                                                  v88,
                                                  *(struct IMemObj **)(v129 + 1000),
                                                  "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
                                                  696,
                                                  5u);
    v130 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v131 = *(_QWORD *)(v130 + 256);
    if ( !v131 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v131 = *(_QWORD *)(v130 + 256);
    }
    *(_QWORD *)(*((_QWORD *)this + 29) + 8LL) = operator new[](
                                                  v91,
                                                  *(struct IMemObj **)(v131 + 1000),
                                                  "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
                                                  697,
                                                  5u);
    v132 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v133 = *(_QWORD *)(v132 + 256);
    if ( !v133 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v133 = *(_QWORD *)(v132 + 256);
    }
    *(_QWORD *)(*((_QWORD *)this + 30) + 8LL) = operator new[](
                                                  SourceSize,
                                                  *(struct IMemObj **)(v133 + 1000),
                                                  "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp",
                                                  698,
                                                  5u);
    memcpy_s(*(void *const *)(*((_QWORD *)this + 28) + 8LL), v88, lpWideCharStr, v88);
    memcpy_s(*(void *const *)(*((_QWORD *)this + 29) + 8LL), v91, a11, v91);
    memcpy_s(*(void *const *)(*((_QWORD *)this + 30) + 8LL), SourceSize, a13, SourceSize);
    v134 = *((_QWORD *)this + 21);
    if ( *(_BYTE *)(v134 + 1312) )
    {
      if ( !*((_DWORD *)this + 37) )
      {
        *(_DWORD *)MultiByteStr = BytesInMBChar(
                                    *((_DWORD *)this + 31),
                                    (const unsigned __int8 *)a11,
                                    (const unsigned __int8 *)&a11[v91]);
        v134 = *((_QWORD *)this + 21);
      }
      v90 = *(_QWORD *)MultiByteStr;
      *(_DWORD *)(v134 + 1244) = *(_DWORD *)MultiByteStr;
    }
  }
  v135 = *((_QWORD *)this + 5);
  if ( *(_BYTE *)(*(_QWORD *)(v135 + 8) + 196LL) )
  {
    *(_DWORD *)(v135 + 64) = 1;
LABEL_158:
    *(_DWORD *)MultiByteStr = 748;
    v136 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v137 = *(_QWORD *)(v136 + 256);
    if ( !v137 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v137 = *(_QWORD *)(v136 + 256);
    }
    v160 = *(struct IMemObj **)(v137 + 1000);
    v138 = (CHAR *)operator new(0x20u, v160, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp", 748, 5u);
    v158 = v138;
    if ( v138 )
    {
      v139 = *((_QWORD *)this + 1);
      *(_QWORD *)v138 = &CImpColumnsInfo::`vftable';
      *((_QWORD *)v138 + 1) = this;
      *((_QWORD *)v138 + 2) = this;
      *((_QWORD *)v138 + 3) = v139;
    }
    else
    {
      v138 = 0;
    }
    *((_QWORD *)this + 4) = v138;
    *(_DWORD *)MultiByteStr = 749;
    v140 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v141 = *(_QWORD *)(v140 + 256);
    if ( !v141 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v141 = *(_QWORD *)(v140 + 256);
    }
    v160 = *(struct IMemObj **)(v141 + 1000);
    v142 = (CHAR *)operator new(0x18u, v160, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp", 749, 5u);
    v158 = v142;
    if ( v142 )
    {
      *(_QWORD *)v142 = &CImpAccessor::`vftable';
      *((_QWORD *)v142 + 1) = this;
      *((_QWORD *)v142 + 2) = this;
    }
    else
    {
      v142 = 0;
    }
    *((_QWORD *)this + 6) = v142;
    *(_DWORD *)MultiByteStr = 750;
    v143 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v144 = *(_QWORD *)(v143 + 256);
    if ( !v144 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v144 = *(_QWORD *)(v143 + 256);
    }
    v160 = *(struct IMemObj **)(v144 + 1000);
    v145 = (CHAR *)operator new(0x20u, v160, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp", 750, 5u);
    v158 = v145;
    if ( v145 )
    {
      *(_QWORD *)v145 = &CImpRowsetInfo::`vftable';
      *((_QWORD *)v145 + 1) = this;
      *((_QWORD *)v145 + 2) = this;
      *((_QWORD *)v145 + 3) = 0;
    }
    else
    {
      v145 = 0;
    }
    *((_QWORD *)this + 7) = v145;
    *(_DWORD *)MultiByteStr = 751;
    v146 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v147 = *(_QWORD *)(v146 + 256);
    if ( !v147 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v147 = *(_QWORD *)(v146 + 256);
    }
    v160 = *(struct IMemObj **)(v147 + 1000);
    v148 = (CHAR *)operator new(0x28u, v160, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp", 751, 5u);
    v158 = v148;
    if ( v148 )
    {
      *(_QWORD *)v148 = &CImpIRowsetHelper::`vftable';
      *((_QWORD *)v148 + 1) = this;
      *((_QWORD *)v148 + 2) = this;
      *((_QWORD *)v148 + 3) = 0;
      *((_QWORD *)v148 + 4) = 0;
    }
    else
    {
      v148 = 0;
    }
    *((_QWORD *)this + 9) = v148;
    *(_DWORD *)MultiByteStr = 752;
    v149 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v150 = *(_QWORD *)(v149 + 256);
    if ( !v150 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v150 = *(_QWORD *)(v149 + 256);
    }
    v160 = *(struct IMemObj **)(v150 + 1000);
    v151 = (CHAR *)operator new(0x18u, v160, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp", 752, 5u);
    v158 = v151;
    if ( v151 )
    {
      *(_QWORD *)v151 = &CImpRowsetSSInfo::`vftable';
      *((_QWORD *)v151 + 1) = this;
      *((_QWORD *)v151 + 2) = this;
    }
    else
    {
      v151 = 0;
    }
    *((_QWORD *)this + 8) = v151;
    *(_DWORD *)MultiByteStr = 753;
    v152 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v153 = *(_QWORD *)(v152 + 256);
    if ( !v153 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v153 = *(_QWORD *)(v152 + 256);
    }
    v160 = *(struct IMemObj **)(v153 + 1000);
    v154 = (CHAR *)operator new(0x18u, v160, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\improwst.cpp", 753, 5u);
    v158 = v154;
    if ( v154 )
    {
      *(_QWORD *)v154 = &CImpIRowsetFileSplit::`vftable';
      *((_QWORD *)v154 + 1) = this;
      *((_QWORD *)v154 + 2) = this;
    }
    else
    {
      v154 = 0;
    }
    *((_QWORD *)this + 10) = v154;
    LastError = 0;
    goto LABEL_189;
  }
  if ( *(_BYTE *)(v135 + 156)
    && *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v90, v89) + 857)
    && (int)CImpRowset::SeekNextRow(v135, 3) < 0 )
  {
    LastError = -2147467259;
    goto LABEL_189;
  }
  LastError = CImpRowset::SkipFirstRows((CImpRowset *)v135);
  if ( LastError < 0 )
  {
    LastError = -2147467259;
    goto LABEL_189;
  }
  if ( LastError == 265926 )
    LastError = 0;
  if ( !LastError )
    goto LABEL_158;
LABEL_189:
  if ( v165 )
    (*(void (__fastcall **)(struct CBcpImport *))(*(_QWORD *)v165 + 16LL))(v165);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x10209ff20  push    rbp
0x10209ff22  push    r12
0x10209ff24  push    r13
0x10209ff26  push    r14
0x10209ff28  push    r15
0x10209ff2a  sub     rsp, 0E0h
0x10209ff31  lea     rbp, [rsp+80h]
0x10209ff39  mov     [rbp+80h+var_38], 0FFFFFFFFFFFFFFFEh
0x10209ff41  mov     [rbp+80h+arg_0], rbx
0x10209ff48  mov     [rbp+80h+arg_8], rsi
0x10209ff4f  mov     [rbp+80h+arg_10], rdi
0x10209ff56  mov     rax, cs:__security_cookie
0x10209ff5d  xor     rax, rbp
0x10209ff60  mov     [rbp+80h+var_30], rax
0x10209ff64  mov     r15, r9
0x10209ff67  mov     [rbp+80h+var_50], r9
0x10209ff6b  mov     rsi, r8
0x10209ff6e  mov     [rbp+80h+var_48], r8
0x10209ff72  mov     rbx, rdx
0x10209ff75  mov     r14, rcx
0x10209ff78  mov     rdi, [rbp+80h+arg_78]
0x10209ff7f  mov     [rbp+80h+var_40], rdi
0x10209ff83  mov     rax, [rdi]
0x10209ff86  mov     rcx, rdi
0x10209ff89  call    qword ptr [rax+8]
0x10209ff8c  mov     ecx, [rbp+80h+arg_88]
0x10209ff92  mov     edx, [rbp+80h+arg_A8]
0x10209ff98  test    ecx, ecx
0x10209ff9a  jnz     short loc_10209FFB0
0x10209ff9c  cmp     [rbp+80h+arg_A0], ecx
0x10209ffa2  jnz     short loc_10209FFB0
0x10209ffa4  test    edx, edx
0x10209ffa6  jnz     short loc_10209FFB0
0x10209ffa8  cmp     [rbp+80h+arg_C0], dl
0x10209ffae  jz      short loc_10209FFD5
0x10209ffb0  mov     [r14+0D8h], r15
0x10209ffb7  mov     r13, [rbp+80h+arg_20]
0x10209ffbe  mov     [r14+0C8h], r13
0x10209ffc5  mov     r12, [rbp+80h+arg_80]
0x10209ffcc  mov     [r14+0D0h], r12
0x10209ffd3  jmp     short loc_10209FFE3
0x10209ffd5  mov     r13, [rbp+80h+arg_20]
0x10209ffdc  mov     r12, [rbp+80h+arg_80]
0x10209ffe3  mov     r8, [rbp+80h+arg_28]
0x10209ffea  mov     [r14+68h], r8
0x10209ffee  mov     eax, [rsi+28h]
0x10209fff1  mov     [r14+78h], eax
0x10209fff5  mov     eax, [rsi+2Ch]
0x10209fff8  mov     [r14+7Ch], eax
0x10209fffc  mov     eax, [rsi+3Ch]
0x10209ffff  mov     [r14+80h], eax
0x1020a0006  mov     eax, [rsi+40h]
0x1020a0009  mov     [r14+94h], eax
0x1020a0010  mov     eax, [rsi+44h]
0x1020a0013  mov     [r14+98h], eax
0x1020a001a  mov     eax, [rsi+30h]
0x1020a001d  mov     [r14+9Ch], eax
0x1020a0024  mov     rax, [rsi+48h]
0x1020a0028  mov     [r14+0B0h], rax
0x1020a002f  mov     eax, [rsi+50h]
0x1020a0032  mov     [r14+0B8h], eax
0x1020a0039  mov     eax, [rsi+54h]
0x1020a003c  mov     [r14+0BCh], eax
0x1020a0043  mov     [r14+84h], ecx
0x1020a004a  mov     [r14+88h], edx
0x1020a0051  movzx   eax, [rbp+80h+arg_B0]
0x1020a0058  mov     [r14+8Ch], al
0x1020a005f  mov     [r14+0A8h], rbx
0x1020a0066  movzx   eax, byte ptr [rsi+6Ch]
0x1020a006a  mov     [r14+8Dh], al
0x1020a0071  cmp     dword ptr [rsi+60h], 0
0x1020a0075  jnz     short loc_1020A0087
0x1020a0077  cmp     dword ptr [rsi+64h], 0
0x1020a007b  jnz     short loc_1020A0087
0x1020a007d  cmp     dword ptr [rsi+68h], 0
0x1020a0081  jnz     short loc_1020A0087
0x1020a0083  xor     eax, eax
0x1020a0085  jmp     short loc_1020A008C
0x1020a0087  mov     eax, 1
0x1020a008c  mov     [r14+0C0h], eax
0x1020a0093  movzx   eax, [rbp+80h+arg_B8]
0x1020a009a  mov     [r14+0C4h], al
0x1020a00a1  movzx   eax, [rbp+80h+arg_C8]
0x1020a00a8  mov     [r14+0C5h], al
0x1020a00af  test    r8, r8
0x1020a00b2  jz      loc_1020A0147
0x1020a00b8  mov     rdx, gs:58h
0x1020a00c1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020a00c8  mov     ecx, [rax]
0x1020a00ca  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020a00d1  mov     ebx, [rax]
0x1020a00d3  add     rbx, [rdx+rcx*8]
0x1020a00d7  mov     rcx, [rbx+100h]
0x1020a00de  test    rcx, rcx
0x1020a00e1  jnz     short loc_1020A00F4
0x1020a00e3  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1020a00e9  mov     rcx, [rbx+100h]
0x1020a00f0  mov     r8, [r14+68h]
0x1020a00f4  mov     eax, 10h
0x1020a00f9  mul     r8
0x1020a00fc  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1020a0103  cmovo   rax, rdx
0x1020a0107  mov     byte ptr [rsp+100h+lpMultiByteStr], 5
0x1020a010c  mov     r9d, 136h
0x1020a0112  lea     r8, aSqlNtdbmsStore_699; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x1020a0119  mov     rdx, [rcx+3E8h]
0x1020a0120  mov     rcx, rax
0x1020a0123  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1020a0129  mov     [r14+70h], rax
0x1020a012d  mov     rdx, [r14+68h]
0x1020a0131  shl     rdx, 4; DestinationSize
0x1020a0135  mov     r9, rdx; SourceSize
0x1020a0138  mov     r8, [rbp+80h+Source]; Source
0x1020a013f  mov     rcx, rax; Destination
0x1020a0142  call    memcpy_s
0x1020a0147  mov     dword ptr [rbp+80h+MultiByteStr], 13Dh
0x1020a014e  mov     rdx, gs:58h
0x1020a0157  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020a015e  mov     ecx, [rax]
0x1020a0160  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020a0167  mov     ebx, [rax]
0x1020a0169  add     rbx, [rdx+rcx*8]
0x1020a016d  mov     rdx, [rbx+100h]
0x1020a0174  test    rdx, rdx
0x1020a0177  jnz     short loc_1020A0188
0x1020a0179  xor     ecx, ecx
0x1020a017b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1020a0181  mov     rdx, [rbx+100h]
0x1020a0188  mov     rdx, [rdx+3E8h]
0x1020a018f  mov     [rbp+80h+var_60], rdx
0x1020a0193  mov     byte ptr [rsp+100h+lpMultiByteStr], 5
0x1020a0198  mov     r9d, 13Dh
0x1020a019e  lea     r8, aSqlNtdbmsStore_699; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x1020a01a5  mov     ecx, 40h ; '@'
0x1020a01aa  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1020a01b0  mov     [rbp+80h+var_68], rax
0x1020a01b4  test    rax, rax
0x1020a01b7  jz      short loc_1020A01E6
0x1020a01b9  mov     rcx, [r14+28h]
0x1020a01bd  xor     r8d, r8d
0x1020a01c0  mov     [rax], r8
0x1020a01c3  mov     [rax+8], r8
0x1020a01c7  mov     [rax+10h], r8
0x1020a01cb  mov     [rax+18h], r8d
0x1020a01cf  lea     rdx, ??_7CBufSwitchSink@@6B@; const CBufSwitchSink::`vftable'
0x1020a01d6  mov     [rax+20h], rdx
0x1020a01da  mov     [rax+28h], r8
0x1020a01de  mov     [rax+30h], rcx
0x1020a01e2  mov     [rax+38h], r8
0x1020a01e6  mov     [r14+8], rax
0x1020a01ea  mov     dword ptr [rbp+80h+MultiByteStr], 13Fh
0x1020a01f1  mov     rdx, gs:58h
0x1020a01fa  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020a0201  mov     ecx, [rax]
0x1020a0203  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020a020a  mov     ebx, [rax]
0x1020a020c  add     rbx, [rdx+rcx*8]
0x1020a0210  mov     rdx, [rbx+100h]
0x1020a0217  test    rdx, rdx
0x1020a021a  jnz     short loc_1020A022B
0x1020a021c  xor     ecx, ecx
0x1020a021e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1020a0224  mov     rdx, [rbx+100h]
0x1020a022b  mov     rdx, [rdx+3E8h]
0x1020a0232  mov     [rbp+80h+var_68], rdx
0x1020a0236  mov     byte ptr [rsp+100h+lpMultiByteStr], 5
0x1020a023b  mov     r9d, 13Fh
0x1020a0241  lea     r8, aSqlNtdbmsStore_699; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x1020a0248  mov     ecx, 0B8h
0x1020a024d  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1020a0253  mov     rbx, rax
0x1020a0256  mov     [rbp+80h+var_60], rax
0x1020a025a  test    rax, rax
0x1020a025d  jz      loc_1020A0329
0x1020a0263  xor     r8d, r8d
0x1020a0266  mov     [rbp+80h+var_40], r8
0x1020a026a  mov     rdx, [r14+0A8h]
0x1020a0271  mov     rcx, [r14+8]
0x1020a0275  lea     rax, ??_7CImpRowset@@6B@; const CImpRowset::`vftable'
0x1020a027c  mov     [rbx], rax
0x1020a027f  mov     [rbx+8], r14
0x1020a0283  mov     [rbx+10h], r14
0x1020a0287  mov     [rbx+18h], rcx
0x1020a028b  mov     [rbx+20h], rdx
0x1020a028f  mov     [rbx+28h], r8
0x1020a0293  mov     rax, [rbp+80h+arg_90]
0x1020a029a  mov     [rbx+30h], rax
0x1020a029e  mov     [rbx+38h], r8
0x1020a02a2  mov     [rbx+40h], r8d
0x1020a02a6  mov     [rbx+48h], r8
0x1020a02aa  mov     [rbx+50h], r8
0x1020a02ae  mov     eax, [rsi+8]
0x1020a02b1  mov     [rbx+58h], eax
0x1020a02b4  mov     rax, [rsi+10h]
0x1020a02b8  mov     [rbx+60h], rax
0x1020a02bc  mov     rax, [rsi+18h]
0x1020a02c0  mov     [rbx+68h], rax
0x1020a02c4  mov     rax, [rsi+20h]
0x1020a02c8  mov     [rbx+70h], rax
0x1020a02cc  mov     [rbx+78h], r8
0x1020a02d0  mov     [rbx+88h], r8
0x1020a02d7  mov     eax, [r14+90h]
0x1020a02de  mov     [rbx+90h], eax
0x1020a02e4  mov     eax, [r14+0C0h]
0x1020a02eb  mov     [rbx+94h], eax
0x1020a02f1  mov     [rbx+98h], r8d
0x1020a02f8  mov     [rbx+9Ch], r8w
0x1020a0300  mov     [rbx+9Eh], r8b
0x1020a0307  mov     [rbx+0A0h], rdi
0x1020a030e  mov     rax, [rsi+70h]
0x1020a0312  mov     [rbx+0A8h], rax
0x1020a0319  mov     rax, [rsi+88h]
0x1020a0320  mov     [rbx+0B0h], rax
0x1020a0327  jmp     short loc_1020A032B
0x1020a0329  xor     ebx, ebx
0x1020a032b  mov     [r14+28h], rbx
0x1020a032f  mov     [rbx+80h], r15
0x1020a0336  mov     rdx, gs:58h
0x1020a033f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020a0346  mov     ecx, [rax]
0x1020a0348  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020a034f  mov     edi, [rax]
0x1020a0351  add     rdi, [rdx+rcx*8]
0x1020a0355  mov     r10, [rdi+100h]
0x1020a035c  mov     rcx, r15
0x1020a035f  test    r10, r10
0x1020a0362  jnz     short loc_1020A037A
0x1020a0364  xor     ecx, ecx
0x1020a0366  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1020a036c  mov     r10, [rdi+100h]
0x1020a0373  mov     rcx, [rbx+80h]
0x1020a037a  inc     rcx
0x1020a037d  mov     eax, 8
0x1020a0382  mul     rcx
0x1020a0385  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1020a038c  cmovo   rax, rcx
0x1020a0390  mov     byte ptr [rsp+100h+cbMultiByte], 5
0x1020a0395  mov     dword ptr [rsp+100h+lpMultiByteStr], 8Fh
0x1020a039d  lea     r9, aSqlNtdbmsStore_254; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x1020a03a4  lea     r8d, [rcx+2]
0x1020a03a8  mov     rdx, [r10+3E8h]
0x1020a03af  mov     rcx, rax
0x1020a03b2  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1020a03b8  mov     [rbx+48h], rax
0x1020a03bc  test    rax, rax
0x1020a03bf  jnz     short loc_1020A03CB
0x1020a03c1  mov     esi, 8007000Eh
0x1020a03c6  jmp     loc_1020A14CB
0x1020a03cb  mov     r8, [rbx+80h]
0x1020a03d2  lea     r8, ds:8[r8*8]; Size
0x1020a03da  xor     edx, edx; Val
0x1020a03dc  mov     rcx, rax; void *
0x1020a03df  call    memset_0
0x1020a03e4  mov     rcx, [rbx+8]
0x1020a03e8  xor     edi, edi
0x1020a03ea  mov     eax, edi
0x1020a03ec  cmp     dword ptr [rcx+94h], 6
0x1020a03f3  setz    al
0x1020a03f6  mov     [rbx+8Ch], eax
0x1020a03fc  mov     eax, [rcx+88h]
0x1020a0402  mov     [rbx+98h], eax
0x1020a0408  movzx   eax, byte ptr [rcx+8Ch]
0x1020a040f  mov     [rbx+9Ch], al
0x1020a0415  movzx   eax, byte ptr [rcx+8Dh]
0x1020a041c  mov     [rbx+9Dh], al
0x1020a0422  movzx   eax, cs:byte_10316E9B1
0x1020a0429  mov     [rbx+9Eh], al
0x1020a042f  cmp     dword ptr [rcx+94h], 4
0x1020a0436  jnz     short loc_1020A0442
0x1020a0438  mov     dword ptr [rcx+94h], 1
0x1020a0442  mov     qword ptr [rbp+80h+MultiByteStr], 2
0x1020a044a  cmp     [rbp+80h+arg_98], 1
0x1020a0451  jnz     loc_1020A0D04
0x1020a0457  cmp     [r14+0C0h], edi
0x1020a045e  jz      short loc_1020A048C
0x1020a0460  mov     eax, [r14+94h]
0x1020a0467  test    eax, eax
0x1020a0469  jnz     short loc_1020A0470
0x1020a046b  lea     edx, [rax+6]
0x1020a046e  jmp     short loc_1020A0478
0x1020a0470  cmp     eax, 1
0x1020a0473  jnz     short loc_1020A048C
0x1020a0475  lea     edx, [rax+8]
0x1020a0478  mov     r9d, 1
0x1020a047e  lea     r8d, [r9+0Fh]
0x1020a0482  lea     ecx, [r9+2Fh]
0x1020a0486  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1020a048c  mov     eax, [r14+94h]
0x1020a0493  test    eax, eax
0x1020a0495  jnz     loc_1020A08AA
0x1020a049b  mov     dword ptr [r14+94h], 1
0x1020a04a6  mov     r12, [rbp+80h+cchWideChar]
0x1020a04ad  lea     r8d, ds:2[r12*2]
0x1020a04b5  mov     eax, r8d
0x1020a04b8  lea     rcx, [r8+0Fh]
0x1020a04bc  mov     rdx, 0FFFFFFFFFFFFFF0h
0x1020a04c6  cmp     rcx, rax
0x1020a04c9  ja      short loc_1020A04CE
0x1020a04cb  mov     rcx, rdx
0x1020a04ce  and     rcx, 0FFFFFFFFFFFFFFF0h
  ... truncated ...
```
