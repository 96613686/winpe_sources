# BCP_readfmt(unsigned __int64,tagIMPORT_COLINFO *,unsigned __int64 &,CAutoRg<tagIMPORT_COLINFO> &,CAutoRg<DELIMITER_INFO> &,int *,tagIMPORT_INFO const &,wchar_t const *,unsigned __int64,wchar_t *,unsigned __int64,CImpImportProvider *)

- ea: `0x102083b40`
- end: `0x102086685`
- name: `?BCP_readfmt@@YAJ_KPEAUtagIMPORT_COLINFO@@AEA_KAEAV?$CAutoRg@UtagIMPORT_COLINFO@@@@AEAV?$CAutoRg@UDELIMITER_INFO@@@@PEAHAEBUtagIMPORT_INFO@@PEB_W0PEA_W0PEAVCImpImportProvider@@@Z`
- size: `11077`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, wchar_t *, __int64, wchar_t *, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x102097910`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100415e90`
- `0x10042d300`
- `0x10045e0a0`
- `0x10046221a`
- `0x100472440`
- `0x100475060`
- `0x10063e990`
- `0x100a52c40`
- `0x1011538d0`
- `0x101a45530`
- `0x101a45e70`
- `0x102082660`
- `0x102083280`
- `0x1020834c0`
- `0x102083b40`
- `0x102087aa0`
- `0x102087b10`
- `0x10208d890`
- `0x10208de60`
- `0x10208e020`
- `0x10208e0f0`
- `0x1023a8290`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1020851c8`
- `KERNEL32!SetLastError` at `0x102086403`
- `KERNEL32!SetLastError` at `0x1020865b5`
- `KERNEL32!SetLastError` at `0x1020851c8`
- `KERNEL32!SetLastError` at `0x102086403`
- `KERNEL32!SetLastError` at `0x1020865b5`
- `KERNEL32!FreeLibrary` at `0x102084942`
- `KERNEL32!FreeLibrary` at `0x102084d76`
- `KERNEL32!FreeLibrary` at `0x10208516e`
- `KERNEL32!FreeLibrary` at `0x1020855b8`
- `KERNEL32!FreeLibrary` at `0x1020859b1`
- `KERNEL32!FreeLibrary` at `0x1020863ad`
- `KERNEL32!FreeLibrary` at `0x1020864a9`
- `KERNEL32!FreeLibrary` at `0x102086542`
- `KERNEL32!FreeLibrary` at `0x102084942`
- `KERNEL32!FreeLibrary` at `0x102084d76`
- `KERNEL32!FreeLibrary` at `0x10208516e`
- `KERNEL32!FreeLibrary` at `0x1020855b8`
- `KERNEL32!FreeLibrary` at `0x1020859b1`
- `KERNEL32!FreeLibrary` at `0x1020863ad`
- `KERNEL32!FreeLibrary` at `0x1020864a9`
- `KERNEL32!FreeLibrary` at `0x102086542`
- `KERNEL32!GetLastError` at `0x102083ec0`
- `KERNEL32!GetLastError` at `0x10208424f`
- `KERNEL32!GetLastError` at `0x102083ec0`
- `KERNEL32!GetLastError` at `0x10208424f`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102084bc6`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102084cae`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102084dd7`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102084de8`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x10208530b`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102085775`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102085a8b`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102085e48`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102085fbc`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102084bc6`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102084cae`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102084dd7`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102084de8`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x10208530b`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102085775`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102085a8b`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102085e48`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x102085fbc`
- `sqlTsEs!?CIDFromTDSCollation@@YAKPEFBUTDSCOLLATION@@@Z` at `0x102085b7a`
- `sqlTsEs!?CIDFromTDSCollation@@YAKPEFBUTDSCOLLATION@@@Z` at `0x102086039`
- `sqlTsEs!?CIDFromTDSCollation@@YAKPEFBUTDSCOLLATION@@@Z` at `0x102085b7a`
- `sqlTsEs!?CIDFromTDSCollation@@YAKPEFBUTDSCOLLATION@@@Z` at `0x102086039`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x102085b82`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x102086041`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x102085b82`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x102086041`
- `sqlTsEs!?FValidCollation@@YA_NK_N@Z` at `0x102084ff6`
- `sqlTsEs!?FValidCollation@@YA_NK_N@Z` at `0x102084ff6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084b17`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084b42`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084b76`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084ba2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084c10`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084c31`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084c64`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084c8f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1020857f7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084b17`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084b42`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084b76`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084ba2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084c10`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084c31`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084c64`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x102084c8f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1020857f7`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1020865d0`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1020865d0`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x102083d02`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x102084042`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x102083d02`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x102084042`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102084577`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102084605`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102085c34`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102084577`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102084605`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102085c34`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10208441f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10208441f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10208431d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10208434a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102084385`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020865f3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102086613`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102086637`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102086656`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10208431d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10208434a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102084385`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020865f3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102086613`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102086637`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102086656`
- `sqldk!SystemThread_TlsIndex` at `0x102083cbd`
- `sqldk!SystemThread_TlsIndex` at `0x102083d1b`
- `sqldk!SystemThread_TlsIndex` at `0x102083d9a`
- `sqldk!SystemThread_TlsIndex` at `0x102083e26`
- `sqldk!SystemThread_TlsIndex` at `0x102083ed5`
- `sqldk!SystemThread_TlsIndex` at `0x102083f70`
- `sqldk!SystemThread_TlsIndex` at `0x102083ffd`
- `sqldk!SystemThread_TlsIndex` at `0x10208405b`
- `sqldk!SystemThread_TlsIndex` at `0x1020840da`
- `sqldk!SystemThread_TlsIndex` at `0x102084264`
- `sqldk!SystemThread_TlsIndex` at `0x1020843c8`
- `sqldk!SystemThread_TlsIndex` at `0x102084519`
- `sqldk!SystemThread_TlsIndex` at `0x1020845a2`
- `sqldk!SystemThread_TlsIndex` at `0x102085be4`
- `sqldk!SystemThread_TlsOffset` at `0x102083cc6`
- `sqldk!SystemThread_TlsOffset` at `0x102083d24`
- `sqldk!SystemThread_TlsOffset` at `0x102083da3`
- `sqldk!SystemThread_TlsOffset` at `0x102083e2f`
- `sqldk!SystemThread_TlsOffset` at `0x102083ede`
- `sqldk!SystemThread_TlsOffset` at `0x102083f79`
- `sqldk!SystemThread_TlsOffset` at `0x102084006`
- `sqldk!SystemThread_TlsOffset` at `0x102084064`
- `sqldk!SystemThread_TlsOffset` at `0x1020840e3`
- `sqldk!SystemThread_TlsOffset` at `0x10208426d`
- `sqldk!SystemThread_TlsOffset` at `0x1020843d1`
- `sqldk!SystemThread_TlsOffset` at `0x102084522`
- `sqldk!SystemThread_TlsOffset` at `0x1020845ab`
- `sqldk!SystemThread_TlsOffset` at `0x102085bed`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10208495c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10208518a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1020863c7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10208655c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10208495c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10208518a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1020863c7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10208655c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102083ce1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102083d3f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102084021`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10208407f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020843ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10208453b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020845c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102085c08`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102083ce1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102083d3f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102084021`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10208407f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020843ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10208453b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020845c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102085c08`
- `sqldk!??_V@YAXPEAX@Z` at `0x102084590`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208491f`
- `sqldk!??_V@YAXPEAX@Z` at `0x102084d53`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208514b`
- `sqldk!??_V@YAXPEAX@Z` at `0x102085595`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208598e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208638a`
- `sqldk!??_V@YAXPEAX@Z` at `0x102086486`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208651f`
- `sqldk!??_V@YAXPEAX@Z` at `0x102084590`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208491f`
- `sqldk!??_V@YAXPEAX@Z` at `0x102084d53`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208514b`
- `sqldk!??_V@YAXPEAX@Z` at `0x102085595`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208598e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208638a`
- `sqldk!??_V@YAXPEAX@Z` at `0x102086486`
- `sqldk!??_V@YAXPEAX@Z` at `0x10208651f`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x102084b38`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x102084b5b`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x102084c27`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x102084c48`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x102084b38`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x102084b5b`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x102084c27`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x102084c48`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x102084b86`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x102084bb6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x102084c73`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x102084ca2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x102084b86`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x102084bb6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x102084c73`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x102084ca2`
- `api-ms-win-crt-convert-l1-1-0!_wcstombs_l` at `0x10208580e`
- `api-ms-win-crt-convert-l1-1-0!_wcstombs_l` at `0x10208580e`
- `sqllang!?intnl_impersonate_client@@YAHPEAVCSession@@@Z` at `0x102083dd8`
- `sqllang!?intnl_impersonate_client@@YAHPEAVCSession@@@Z` at `0x102084118`
- `sqllang!?intnl_impersonate_client@@YAHPEAVCSession@@@Z` at `0x102083dd8`
- `sqllang!?intnl_impersonate_client@@YAHPEAVCSession@@@Z` at `0x102084118`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102083e46`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102083ef5`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102084284`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102083e46`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102083ef5`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102084284`
- `sqllang!?ImpPrintError@@YAJKK_KKK0QEB_W0101I_NPEA_W@Z` at `0x1020848f7`
- `sqllang!?ImpPrintError@@YAJKK_KKK0QEB_W0101I_NPEA_W@Z` at `0x102084d2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=71
__int64 __fastcall BCP_readfmt(
        unsigned __int64 a1,
        __int64 a2,
        _QWORD *a3,
        void **a4,
        __int64 a5,
        int *a6,
        __int64 a7,
        wchar_t *a8,
        unsigned __int64 a9,
        wchar_t *a10,
        __int64 a11,
        __int64 a12)
{
  int v13; // edi
  DWORD LastError; // ebx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rdx
  _BYTE *v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rdx
  _BYTE *v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rdx
  CBulkFormat *v31; // rax
  CBulkFormat *v32; // rdi
  __int64 v33; // rax
  void *v34; // rbx
  unsigned int v35; // esi
  _QWORD *v36; // rax
  unsigned __int64 v37; // rbx
  __int64 v38; // rdi
  __int64 v39; // rcx
  unsigned __int64 v40; // rax
  void *v41; // rdi
  void **v42; // r14
  __int64 v43; // rdi
  __int64 v44; // rcx
  __int64 v45; // rax
  bool v46; // cf
  unsigned __int64 v47; // rax
  unsigned __int64 *v48; // rax
  _QWORD *v49; // rdx
  void **v50; // rdi
  int *v51; // rax
  int *v52; // r8
  int *v53; // rdx
  int v54; // r12d
  CBulkRecord *v55; // rbx
  __int64 v56; // rdi
  int *v57; // r14
  int *v58; // rcx
  int *v59; // rdx
  char *v60; // rsi
  __int64 v61; // r13
  int v62; // r11d
  CBulkRecord *v63; // rcx
  char *v64; // r9
  char *v65; // r10
  CBulkRecord *v66; // rcx
  const wchar_t *v67; // rcx
  const wchar_t *v68; // r8
  signed __int64 v69; // r8
  int v70; // eax
  int v71; // edx
  unsigned __int64 v72; // r14
  const wchar_t *v73; // rdx
  int v74; // eax
  unsigned __int64 v75; // r10
  __int64 v76; // rcx
  HMODULE v77; // rcx
  __int64 v78; // rcx
  const wchar_t *v79; // rax
  wchar_t *v80; // rdi
  const wchar_t *v81; // r8
  const wchar_t *v82; // rax
  const wchar_t *v83; // rdx
  __int64 v84; // rcx
  wchar_t v85; // ax
  const wchar_t *v86; // rcx
  __int64 v87; // rcx
  const wchar_t *v88; // rax
  int v89; // r12d
  __crt_locale_pointers *v90; // rax
  wchar_t *v91; // r15
  __crt_locale_pointers *v92; // rax
  unsigned int v93; // esi
  __int64 v94; // r14
  const wchar_t **v95; // rdi
  __crt_locale_pointers *v96; // rax
  __crt_locale_pointers *v97; // rax
  unsigned __int16 v98; // r15
  const wchar_t *v99; // rax
  __int64 v100; // r14
  int v101; // r12d
  int v102; // r13d
  __crt_locale_pointers *DefaultLocale; // rax
  __crt_locale_pointers *v104; // rax
  const wchar_t *v105; // r15
  unsigned int v106; // esi
  const wchar_t **v107; // rdi
  __crt_locale_pointers *v108; // rax
  __crt_locale_pointers *v109; // rax
  unsigned __int16 v110; // di
  int v111; // esi
  int v112; // r14d
  int v113; // r15d
  __int64 v114; // rcx
  int v115; // r14d
  __int64 v116; // rax
  unsigned int v117; // edx
  __int64 v118; // r8
  unsigned __int64 v119; // r10
  _OWORD *v120; // rcx
  __int64 *v121; // rax
  __int64 v122; // rdx
  __int64 v123; // rax
  char v124; // al
  __int64 v125; // rcx
  unsigned int v126; // eax
  char *v127; // r15
  unsigned __int64 v128; // r14
  __int64 v129; // rcx
  HMODULE v130; // rcx
  void *v131; // rbx
  struct IFileSystemHandler *v132; // rax
  __int64 v134; // rax
  unsigned __int64 v135; // r12
  unsigned __int16 v136; // ax
  __int64 *v137; // r13
  __int64 v138; // rdx
  __int64 v139; // r8
  unsigned int v140; // eax
  __int64 v141; // r13
  __int64 v142; // rcx
  __int64 v143; // rax
  unsigned int v144; // ecx
  __int64 v145; // rax
  const wchar_t *v146; // r8
  unsigned __int64 v147; // rax
  char *v148; // rcx
  __int64 v149; // rdx
  unsigned __int64 v150; // r9
  signed __int64 v151; // r8
  __int16 v152; // ax
  char *v153; // rax
  __int64 v154; // rcx
  int v155; // r12d
  const wchar_t *v156; // rsi
  unsigned __int16 v157; // r14
  unsigned int v158; // ecx
  int v159; // eax
  const wchar_t *v160; // rdi
  unsigned __int64 v161; // rsi
  unsigned int v162; // r14d
  __int64 v163; // rdi
  __int64 v164; // r13
  const wchar_t *v165; // rdi
  __int64 v166; // rax
  __int64 v167; // rax
  size_t v168; // rsi
  __crt_locale_pointers *v169; // rax
  size_t v170; // rax
  unsigned __int64 v171; // rcx
  __int64 v172; // rax
  int v173; // eax
  const wchar_t *v174; // rcx
  int v175; // esi
  __int64 v176; // rcx
  char v177; // di
  unsigned __int8 v178; // al
  int v179; // r12d
  __int64 v180; // rax
  __int64 v181; // rdx
  __int64 v182; // r12
  unsigned int v183; // eax
  unsigned int v184; // eax
  __int64 v185; // r14
  char *v186; // rdi
  __int64 v187; // rbx
  __int64 v188; // rdx
  void *v189; // rax
  _QWORD *v190; // rdx
  __int64 v191; // rdi
  __int64 v192; // rax
  int v193; // ecx
  char v194; // al
  unsigned __int64 v195; // rax
  __int64 v196; // rcx
  __int64 *v197; // r13
  int v198; // eax
  int v199; // ecx
  int v200; // esi
  unsigned int v201; // eax
  __int64 v202; // r15
  __int16 v203; // di
  unsigned __int64 v204; // rax
  __int16 v205; // dx
  __int16 v206; // cx
  unsigned int v207; // eax
  unsigned int v208; // eax
  __int64 v209; // rcx
  int v210; // edx
  __int64 v211; // rcx
  unsigned int v212; // esi
  unsigned int v213; // eax
  __int64 v214; // rcx
  HMODULE v215; // rcx
  void *v216; // rbx
  struct IFileSystemHandler *v217; // rax
  __int64 v218; // rcx
  __int64 v219; // rcx
  HMODULE v220; // rcx
  void *v221; // rbx
  struct IFileSystemHandler *v222; // rax
  wchar_t *OSErrString; // rbx
  wchar_t *v224; // rax
  char v225; // [rsp+70h] [rbp-2678h]
  int v226; // [rsp+74h] [rbp-2674h]
  void *v227; // [rsp+78h] [rbp-2670h] BYREF
  CBulkFormat *v228; // [rsp+80h] [rbp-2668h]
  unsigned __int64 v229; // [rsp+88h] [rbp-2660h]
  int *v230; // [rsp+90h] [rbp-2658h]
  const wchar_t *v231; // [rsp+98h] [rbp-2650h]
  __int64 v232; // [rsp+A0h] [rbp-2648h]
  int v233; // [rsp+A8h] [rbp-2640h] BYREF
  char v234; // [rsp+ACh] [rbp-263Ch]
  CBulkFormat *v235; // [rsp+B0h] [rbp-2638h]
  int v236; // [rsp+B8h] [rbp-2630h]
  int v237; // [rsp+BCh] [rbp-262Ch]
  const wchar_t *v238; // [rsp+C0h] [rbp-2628h]
  CBulkRecord *v239; // [rsp+C8h] [rbp-2620h] BYREF
  char *v240; // [rsp+D0h] [rbp-2618h]
  unsigned __int16 v241; // [rsp+D8h] [rbp-2610h]
  int v242; // [rsp+DCh] [rbp-260Ch]
  __int64 *v243; // [rsp+E0h] [rbp-2608h]
  unsigned __int64 v244; // [rsp+E8h] [rbp-2600h]
  wchar_t *String2; // [rsp+F0h] [rbp-25F8h]
  __int64 v246; // [rsp+F8h] [rbp-25F0h]
  unsigned int v247; // [rsp+100h] [rbp-25E8h]
  __int64 v248; // [rsp+108h] [rbp-25E0h]
  struct IMemObj *v249; // [rsp+110h] [rbp-25D8h]
  int v250; // [rsp+118h] [rbp-25D0h]
  int v251; // [rsp+11Ch] [rbp-25CCh]
  __int64 v252; // [rsp+120h] [rbp-25C8h]
  __int64 v253; // [rsp+128h] [rbp-25C0h]
  __int64 v254; // [rsp+130h] [rbp-25B8h]
  int *v255; // [rsp+138h] [rbp-25B0h]
  int *v256; // [rsp+140h] [rbp-25A8h]
  unsigned int v257; // [rsp+148h] [rbp-25A0h]
  void **v258; // [rsp+150h] [rbp-2598h]
  int *v259; // [rsp+158h] [rbp-2590h]
  int v260; // [rsp+160h] [rbp-2588h] BYREF
  __int64 v261; // [rsp+168h] [rbp-2580h]
  int v262; // [rsp+170h] [rbp-2578h] BYREF
  int v263; // [rsp+174h] [rbp-2574h]
  __int64 v264; // [rsp+178h] [rbp-2570h]
  int v265; // [rsp+180h] [rbp-2568h] BYREF
  __int64 v266; // [rsp+188h] [rbp-2560h]
  __int64 v267; // [rsp+190h] [rbp-2558h]
  __int64 v268; // [rsp+198h] [rbp-2550h]
  __int64 v269; // [rsp+1A0h] [rbp-2548h]
  bool v270; // [rsp+1B0h] [rbp-2538h]
  int v271; // [rsp+1C0h] [rbp-2528h] BYREF
  __int64 v272; // [rsp+1C8h] [rbp-2520h]
  int v273; // [rsp+1D0h] [rbp-2518h] BYREF
  int v274; // [rsp+1D4h] [rbp-2514h]
  __int64 v275; // [rsp+1D8h] [rbp-2510h]
  int v276; // [rsp+1E0h] [rbp-2508h] BYREF
  __int64 v277; // [rsp+1E8h] [rbp-2500h]
  __int64 v278; // [rsp+1F0h] [rbp-24F8h]
  __int64 v279; // [rsp+1F8h] [rbp-24F0h]
  __int64 v280; // [rsp+200h] [rbp-24E8h]
  bool v281; // [rsp+210h] [rbp-24D8h]
  __int64 v282; // [rsp+220h] [rbp-24C8h]
  CBcpFmtFileException *v283; // [rsp+228h] [rbp-24C0h] BYREF
  CBcpFmtException *v284; // [rsp+230h] [rbp-24B8h] BYREF
  CXmlSyntaxException *v285; // [rsp+238h] [rbp-24B0h] BYREF
  CFmtSyntaxException *v286; // [rsp+240h] [rbp-24A8h] BYREF
  CXMLRWLoadException *v287; // [rsp+248h] [rbp-24A0h] BYREF
  _BYTE v288[96]; // [rsp+250h] [rbp-2498h] BYREF
  __int64 v289; // [rsp+2B0h] [rbp-2438h] BYREF
  char v290[24]; // [rsp+2B8h] [rbp-2430h] BYREF
  int v291; // [rsp+2D0h] [rbp-2418h]
  __int64 v292; // [rsp+2E0h] [rbp-2408h]
  unsigned __int16 v293; // [rsp+2F4h] [rbp-23F4h]
  int v294; // [rsp+2FCh] [rbp-23ECh]
  char v295; // [rsp+300h] [rbp-23E8h]
  char v296; // [rsp+301h] [rbp-23E7h]
  char v297; // [rsp+304h] [rbp-23E4h]
  char v298; // [rsp+306h] [rbp-23E2h]
  char v299; // [rsp+307h] [rbp-23E1h]
  char v300; // [rsp+30Ch] [rbp-23DCh]
  int v301; // [rsp+318h] [rbp-23D0h] BYREF
  char v302; // [rsp+31Ch] [rbp-23CCh]
  unsigned int v303; // [rsp+320h] [rbp-23C8h]
  unsigned int v304; // [rsp+324h] [rbp-23C4h]
  __int16 v305[2]; // [rsp+430h] [rbp-22B8h] BYREF
  int v306; // [rsp+434h] [rbp-22B4h]
  __int64 v307; // [rsp+438h] [rbp-22B0h]
  __int128 v308; // [rsp+440h] [rbp-22A8h]
  __int64 v309; // [rsp+458h] [rbp-2290h]
  __int128 v310; // [rsp+460h] [rbp-2288h]
  __int64 v311; // [rsp+470h] [rbp-2278h]
  char v312; // [rsp+478h] [rbp-2270h]
  int v313; // [rsp+47Ch] [rbp-226Ch]
  __int128 v314; // [rsp+480h] [rbp-2268h]
  char v315; // [rsp+490h] [rbp-2258h]
  __int64 v316; // [rsp+498h] [rbp-2250h]
  char v317; // [rsp+4A0h] [rbp-2248h]
  int v318; // [rsp+4A8h] [rbp-2240h]
  __int64 v319; // [rsp+4ACh] [rbp-223Ch]
  __int64 v320; // [rsp+4B8h] [rbp-2230h]
  __m128i si128; // [rsp+4C0h] [rbp-2228h]
  __int16 v322; // [rsp+4D0h] [rbp-2218h]
  int v323; // [rsp+4D4h] [rbp-2214h]
  char v324; // [rsp+4D8h] [rbp-2210h]
  __int128 v325; // [rsp+4E0h] [rbp-2208h]
  int v326; // [rsp+4F0h] [rbp-21F8h]
  int v327; // [rsp+4F4h] [rbp-21F4h]
  __int16 v328; // [rsp+4F8h] [rbp-21F0h]
  char v329; // [rsp+4FAh] [rbp-21EEh]
  __int64 v330; // [rsp+500h] [rbp-21E8h] BYREF
  char v331[4096]; // [rsp+1500h] [rbp-11E8h] BYREF
  char Dest[144]; // [rsp+2500h] [rbp-1E8h] BYREF
  _BYTE v333[272]; // [rsp+2590h] [rbp-158h] BYREF

  v282 = -2;
  v258 = a4;
  v246 = a2;
  v244 = a1;
  v253 = a5;
  v259 = a6;
  v238 = a8;
  v231 = a8;
  v252 = a12;
  v227 = (void *)-1LL;
  v13 = 0;
  v251 = 0;
  LastError = 0;
  v233 = *(_DWORD *)(a12 + 64);
  v234 = *(_BYTE *)(a12 + 68);
  v239 = 0;
  v250 = *(_DWORD *)(a7 + 68);
  if ( !a8 || !*a8 || !a9 )
  {
    ex_raise(48, 60, 16, 2, &word_10280BED8);
    ex_raise(48, 60, 25, 2, &word_10280BED8);
    return 2147500037LL;
  }
  if ( a11 )
  {
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v260, 1);
    v230 = &v262;
    v265 = 536871477;
    v266 = 0;
    v268 = 0;
    v267 = 0;
    v269 = 0;
    v270 = 0;
    v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v16 = *(_QWORD *)(v15 + 256);
    if ( !v16 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v16 = *(_QWORD *)(v15 + 256);
    }
    v17 = *(_QWORD *)(v16 + 600);
    if ( v17 )
      v270 = (unsigned int)SOS_Task::PushWait(v17, &v265) == 0;
    v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v19 = *(_QWORD *)(v18 + 256);
    if ( !v19 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v19 = *(_QWORD *)(v18 + 256);
    }
    v264 = v19;
    v263 = (*(_DWORD *)(v19 + 800) >> 11) & 1;
    if ( v263 || (*(_BYTE *)(v19 + 800) & 4) == 0 )
    {
      v262 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v19 + 608) + 8LL))(*(_QWORD *)(v19 + 608));
    }
    else
    {
      v262 = 0;
    }
    v20 = *(_BYTE **)(SystemThread_TlsOffset
                    + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
    if ( !dword_103172554 && !*v20 )
      LOBYTE(v13) = intnl_impersonate_client(*(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                               + SystemThread_TlsIndex)
                                                                             + SystemThread_TlsOffset)
                                                                 + 72LL)) == 1;
    v237 = v13;
    if ( !(unsigned int)CreateAzureFileRead(a8, a10, 0, *(_WORD *)(v252 + 76), &v227) )
    {
      if ( v13 )
        intnl_revert_to_self(
          *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 72LL),
          1);
      v230 = &v262;
      if ( v262 )
      {
        if ( v263 )
          *(_DWORD *)(v264 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v264 + 608) + 16LL))(
            *(_QWORD *)(v264 + 608),
            v264,
            1);
      }
      SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v265);
      *(_DWORD *)(v261 + 616) &= ~v260;
      goto LABEL_564;
    }
    LastError = GetLastError();
    if ( v13 )
      intnl_revert_to_self(
        *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset)
                            + 72LL),
        1);
    v230 = &v262;
    if ( v262 )
    {
      if ( v263 )
        *(_DWORD *)(v264 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v264 + 608) + 16LL))(
          *(_QWORD *)(v264 + 608),
          v264,
          1);
    }
    SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v265);
    v21 = v260;
    v22 = v261;
  }
  else
  {
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset)
                               + 72LL)
                   + 270LL)
        & 4) != 0 )
    {
LABEL_568:
      OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v331, 0, 0);
      ex_raise(48, 61, 16, 3, a8, OSErrString);
      ex_raise(48, 61, 25, 3, a8, OSErrString);
      return 2147500037LL;
    }
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v271, 1);
    v230 = &v273;
    v276 = 536871477;
    v277 = 0;
    v279 = 0;
    v278 = 0;
    v280 = 0;
    v281 = 0;
    v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v24 = *(_QWORD *)(v23 + 256);
    if ( !v24 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v24 = *(_QWORD *)(v23 + 256);
    }
    v25 = *(_QWORD *)(v24 + 600);
    if ( v25 )
      v281 = (unsigned int)SOS_Task::PushWait(v25, &v276) == 0;
    v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v27 = *(_QWORD *)(v26 + 256);
    if ( !v27 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v27 = *(_QWORD *)(v26 + 256);
    }
    v275 = v27;
    v274 = (*(_DWORD *)(v27 + 800) >> 11) & 1;
    if ( v274 || (*(_BYTE *)(v27 + 800) & 4) == 0 )
    {
      v273 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v27 + 608) + 8LL))(*(_QWORD *)(v27 + 608));
    }
    else
    {
      v273 = 0;
    }
    v28 = *(_BYTE **)(SystemThread_TlsOffset
                    + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
    if ( !dword_103172554 && !*v28 )
      LOBYTE(v13) = intnl_impersonate_client(*(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                               + SystemThread_TlsIndex)
                                                                             + SystemThread_TlsOffset)
                                                                 + 72LL)) == 1;
    v236 = v13;
    v305[0] = -1;
    v306 = 0x7FFFFFFF;
    v307 = 0;
    v308 = 0;
    v309 = 0;
    v310 = 0;
    v311 = 0;
    v312 = 0;
    v313 = 0;
    v315 = 0;
    v316 = 0;
    v317 = 0;
    v319 = 0;
    v320 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v322 = 0;
    v323 = 0;
    v324 = 0;
    v325 = 0;
    v326 = 0;
    v327 = -1;
    v328 = 0;
    v329 = 0;
    v314 = xmmword_10283FD30;
    v318 = 1;
    v227 = DBCreateFileW(a8, 0x80000000, 1u, 0, 3u, 0x100000u, 0, (const struct FCBFileDirectives *)v305);
    LastError = GetLastError();
    if ( v13 )
      intnl_revert_to_self(
        *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset)
                            + 72LL),
        1);
    v230 = &v273;
    if ( v273 )
    {
      if ( v274 )
        *(_DWORD *)(v275 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v275 + 608) + 16LL))(
          *(_QWORD *)(v275 + 608),
          v275,
          1);
    }
    SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v276);
    v21 = v271;
    v22 = v272;
  }
  *(_DWORD *)(v22 + 616) &= ~v21;
  if ( v227 == (void *)-1LL )
  {
    switch ( LastError )
    {
      case 2u:
        ex_raise(48, 60, 16, 3, a8);
        ex_raise(48, 60, 25, 3, a8);
        return 2147500037LL;
      case 0x57u:
        ex_raise(127, 3, 16, 3, a10);
        ex_raise(127, 3, 25, 3, a10);
        return 2147500037LL;
      case 0x35u:
        ex_raise(127, 4, 16, 3, a10);
        ex_raise(127, 4, 25, 3, a10);
        return 2147500037LL;
    }
    goto LABEL_568;
  }
  try
  {
    SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(v288, 536871477, 1);
    LODWORD(v240) = 1464;
    v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v30 = *(_QWORD *)(v29 + 256);
    if ( !v30 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v30 = *(_QWORD *)(v29 + 256);
    }
    v249 = *(struct IMemObj **)(v30 + 1000);
    v31 = (CBulkFormat *)operator new(0xA0u, v249, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impdisk.cpp", 1464, 5u);
    v235 = v31;
    if ( v31 )
      v32 = CBulkFormat::CBulkFormat(v31);
    else
      v32 = 0;
    v228 = v32;
    v33 = v248;
    if ( v32 )
      v33 = 0;
    v248 = v33;
    v239 = v32;
    v34 = v227;
    CBulkFormat::ParseFormatFile(v32, v227);
    v227 = (void *)-1LL;
    DBCloseHandle(v34);
    SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive((SOS_Task::AutoSwitchPreemptive *)v288);
  }
  catch ( CBcpFmtFileException *v283 )
  {
    v224 = GetOSErrString(*(_DWORD *)v283, (struct ErrorStringHolder *)&v330, 0, 0);
    ex_raise(48, 62, 16, 1, v231, v224);
    goto LABEL_563;
  }
  catch ( CBcpFmtException *v284 )
  {
    TranslateBCPFormatException(v284, v231, a9);
    goto LABEL_563;
  }
  catch ( CXmlSyntaxException *v285 )
  {
    TranslateXmlSyntaxException(v285);
    goto LABEL_563;
  }
  catch ( CFmtSyntaxException *v286 )
  {
    TranslateCFmtSyntaxException(v286, v231);
    goto LABEL_563;
  }
  catch ( CXMLRWLoadException *v287 )
  {
    if ( *(_DWORD *)v287 != 3 )
    {
      ImpPrintError(0x3Eu, 0, 0, 0, 0, a9, v231, 0, 0, 0, 0, 0x10u, 1, 0);
      goto LABEL_563;
    }
    ex_raise(63, 4, 16, 5);
    goto LABEL_563;
  }
  catch ( ... )
  {
    ImpPrintError(0x3Eu, 0, 0, 0, 0, a9, v231, 0, 0, 0, 0, 0x10u, 1, 0);
LABEL_563:
    CAutoP<CBulkFormat>::~CAutoP<CBulkFormat>(&v239);
    goto LABEL_564;
  }
  v256 = (int *)((char *)v32 + 72);
  v35 = 0;
  v36 = (_QWORD *)*((_QWORD *)v32 + 10);
  if ( v36 == (_QWORD *)((char *)v32 + 72) || !v36 )
    goto LABEL_557;
  do
  {
    v247 = ++v35;
    v36 = (_QWORD *)v36[1];
  }
  while ( v36 != (_QWORD *)((char *)v32 + 72) && v36 );
  if ( v35 - 1 > 0x3FF )
  {
LABEL_557:
    ImpPrintError(0x16u, 0, 0, 0, 0, a9, a8, 0, 0, 0, 0, 0x10u, 1, 0);
    v230 = (int *)v32;
    if ( v32 )
    {
      CBulkFormat::Destroy(v32);
      operator delete[](*((void **)v32 + 18));
      v219 = *((_QWORD *)v32 + 16);
      if ( v219 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v219 + 16LL))(v219);
      v220 = (HMODULE)*((_QWORD *)v32 + 15);
      if ( v220 )
      {
        FreeLibrary(v220);
        *((_QWORD *)v32 + 15) = 0;
      }
      CBulkRecord::~CBulkRecord(v32);
      operator delete(v32, 0xA0u);
    }
    return 2147500037LL;
  }
  _mm_lfence();
  v37 = v35;
  if ( v244 > v35 )
    v37 = v244;
  *a3 = v35;
  v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v39 = *(_QWORD *)(v38 + 256);
  if ( !v39 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v39 = *(_QWORD *)(v38 + 256);
  }
  v40 = 384 * v37;
  if ( !is_mul_ok(v37, 0x180u) )
    v40 = -1;
  v41 = operator new[](
          v40,
          *(struct IMemObj **)(v39 + 1000),
          "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impdisk.cpp",
          1527,
          5u);
  v42 = v258;
  if ( *v258 != v41 )
    operator delete[](*v258);
  *v42 = v41;
  v43 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v44 = *(_QWORD *)(v43 + 256);
  if ( !v44 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v44 = *(_QWORD *)(v43 + 256);
  }
  v45 = 16 * v37;
  if ( !is_mul_ok(v37, 0x10u) )
    v45 = -1;
  v46 = __CFADD__(v45, 8);
  v47 = v45 + 8;
  if ( v46 )
    v47 = -1;
  v48 = (unsigned __int64 *)operator new[](
                              v47,
                              *(struct IMemObj **)(v44 + 1000),
                              "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impdisk.cpp",
                              1528,
                              5u);
  if ( v48 )
  {
    *v48 = v37;
    v49 = v48 + 1;
  }
  else
  {
    v49 = 0;
  }
  v50 = (void **)v253;
  CAutoRg<DELIMITER_INFO>::operator=(v253, v49);
  memset_0(*v42, 0, 384 * v37);
  memset_0(*v50, 0, 16 * v37);
  v257 = 0;
  v51 = v256;
  v52 = (int *)*((_QWORD *)v256 + 1);
  v230 = v52;
  v53 = 0;
  if ( v52 == v256 )
  {
    v230 = 0;
    v255 = 0;
  }
  else
  {
    if ( v52 )
      v53 = v52 - 12;
    v255 = v53;
    v247 = v35;
    v51 = v256;
  }
  *v259 = 1;
  v54 = 0;
  v226 = 0;
  v55 = v239;
  if ( !v35 )
  {
    v160 = v238;
    v161 = a9;
    goto LABEL_552;
  }
  v56 = 0;
  v254 = 0;
  while ( 1 )
  {
    v57 = v53;
    v231 = (const wchar_t *)v53;
    if ( v53 )
    {
      v58 = (int *)*((_QWORD *)v53 + 7);
      if ( v58 == v51 )
        v58 = 0;
      v59 = 0;
      if ( v58 )
        v59 = v58 - 12;
      v255 = v59;
    }
    if ( !v57 )
      break;
    v60 = 0;
    v240 = 0;
    v289 = 384;
    memset_0(v290, 0, 0x178u);
    v243 = 0;
    v61 = (__int64)*v258 + 384 * v56;
    v232 = v61;
    if ( v250 != 1 || (v225 = 1, v57[6] != 2) )
      v225 = 0;
    v62 = 0;
    v63 = (CBulkRecord *)*((_QWORD *)v55 + 14);
    if ( v63 == (CBulkRecord *)((char *)v55 + 104) )
      v63 = 0;
    v64 = 0;
    if ( v63 )
      v64 = (char *)v63 - 56;
    while ( 1 )
    {
      v65 = v64;
      if ( !v64 )
        break;
      v66 = (CBulkRecord *)*((_QWORD *)v64 + 8);
      if ( v66 == (CBulkRecord *)((char *)v55 + 104) )
        v66 = 0;
      v64 = 0;
      if ( v66 )
        v64 = (char *)v66 - 56;
      v67 = &word_10280BED8;
      v68 = &word_10280BED8;
      if ( *((_QWORD *)v57 + 1) )
        v68 = (const wchar_t *)*((_QWORD *)v57 + 1);
      if ( *((_QWORD *)v65 + 1) )
        v67 = (const wchar_t *)*((_QWORD *)v65 + 1);
      ++v62;
      v69 = (char *)v68 - (char *)v67;
      do
      {
        v70 = *(const wchar_t *)((char *)v67 + v69);
        v71 = *v67 - v70;
        if ( v71 )
          break;
        ++v67;
      }
      while ( v70 );
      if ( !v71 )
      {
        v60 = v65;
        v240 = v65;
        goto LABEL_127;
      }
    }
    v62 = 0;
LABEL_127:
    v72 = v62;
    v229 = v62;
    v73 = v231;
    if ( !*v259 || *((_DWORD *)v231 + 6) != 2 || (v74 = 1, ((*((_DWORD *)v231 + 7) - 1) & 0xFFFFFFFD) != 0) )
      v74 = 0;
    *v259 = v74;
    v75 = v244;
    if ( v244 )
    {
      if ( v62 > v244 )
        v72 = 0;
      v229 = v72;
    }
    *(_QWORD *)(v61 + 8) = v72;
    switch ( *((_DWORD *)v73 + 6) )
    {
      case 1:
        v80 = L"SQLCHAR";
        break;
      case 2:
        v80 = L"SQLNCHAR";
        break;
      case 3:
        if ( !v72 )
          goto LABEL_150;
        v78 = *((_QWORD *)v60 + 4);
        v79 = &word_10280BED8;
        if ( v78 )
          v79 = (const wchar_t *)*((_QWORD *)v60 + 4);
        if ( *v79 )
        {
          v80 = (wchar_t *)&word_10280BED8;
          if ( v78 )
            v80 = (wchar_t *)*((_QWORD *)v60 + 4);
        }
        else
        {
LABEL_150:
          v80 = L"SQLBINARY";
        }
        break;
      default:
        ImpPrintError(0x18u, 0, (unsigned int)(v54 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
        v230 = (int *)v55;
        if ( v55 )
        {
          CBulkFormat::Destroy(v55);
          operator delete[](*((void **)v55 + 18));
          v76 = *((_QWORD *)v55 + 16);
          if ( v76 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
          v77 = (HMODULE)*((_QWORD *)v55 + 15);
          if ( v77 )
            goto LABEL_142;
          goto LABEL_143;
        }
        goto LABEL_564;
    }
    String2 = v80;
    v81 = (const wchar_t *)*((_QWORD *)v73 + 2);
    v82 = &word_10280BED8;
    if ( v81 )
      v82 = (const wchar_t *)*((_QWORD *)v73 + 2);
    if ( *v82 )
    {
      v83 = &word_10280BED8;
      if ( v81 )
        v83 = v81;
      v84 = 0;
      while ( 1 )
      {
        v85 = v83[v84++];
        if ( v85 != aRaw[v84 - 1] )
          break;
        if ( v84 == 4 )
        {
          v233 = 0;
          v234 = 0;
          goto LABEL_167;
        }
      }
      v86 = &word_10280BED8;
      if ( v81 )
        v86 = v81;
      if ( !SafeGetCollation(v86, (struct TDSCOLLATION *)&v233) )
      {
        v160 = v238;
        v161 = a9;
        ImpPrintError(0x27u, 0, (unsigned int)(v54 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
        v162 = -2147467259;
        goto LABEL_539;
      }
      v75 = v244;
LABEL_167:
      v242 = 2;
    }
    else
    {
      v233 = *(_DWORD *)(v252 + 64);
      v234 = *(_BYTE *)(v252 + 68);
      v242 = 0;
    }
    if ( !v72 )
      goto LABEL_178;
    v251 = 1;
    if ( v75 >= v72 && v246 )
      *(_BYTE *)(v61 + 94) = *(_BYTE *)(384 * v72 + v246 - 290);
    v87 = *((_QWORD *)v60 + 4);
    v88 = &word_10280BED8;
    if ( v87 )
      v88 = (const wchar_t *)*((_QWORD *)v60 + 4);
    if ( !*v88 && v75 >= v72 && v246 )
    {
      v243 = (__int64 *)(v246 + 384 * v72 - 384);
      goto LABEL_178;
    }
    v99 = &word_10280BED8;
    if ( v87 )
      v99 = (const wchar_t *)*((_QWORD *)v60 + 4);
    if ( *v99 )
    {
      v80 = (wchar_t *)&word_10280BED8;
      if ( v87 )
        v80 = (wchar_t *)*((_QWORD *)v60 + 4);
    }
    v100 = 0;
    v101 = 0;
    v102 = 0;
    v236 = 0;
    v237 = 0;
    DefaultLocale = GetDefaultLocale();
    if ( _wcsnicmp_l(L"SQL", v80, 3u, DefaultLocale) )
    {
      v104 = GetDefaultLocale();
      if ( _wcsnicmp_l(L"SYB", v80, 3u, v104) )
        goto LABEL_197;
    }
    v105 = v80 + 3;
    v106 = 0;
    v107 = (const wchar_t **)&off_10336A680;
    while ( 1 )
    {
      v108 = GetDefaultLocale();
      if ( !_wcsicmp_l(v105, *v107, v108) )
        break;
      ++v106;
      ++v100;
      v107 += 3;
      if ( v106 >= 0x1E )
      {
        v109 = GetDefaultLocale();
        if ( !_wcsicmp_l(v105, L"VARIANT", v109) )
        {
          v110 = DbtFromXvt(0x62u);
          v111 = 0;
          v112 = v237;
          LOBYTE(v113) = v236;
          goto LABEL_210;
        }
LABEL_197:
        ImpPrintError(0x18u, 0, (unsigned int)(v226 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
        v230 = (int *)v55;
        if ( v55 )
        {
          CBulkFormat::Destroy(v55);
          operator delete[](*((void **)v55 + 18));
          v114 = *((_QWORD *)v55 + 16);
          if ( v114 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 16LL))(v114);
          v77 = (HMODULE)*((_QWORD *)v55 + 15);
          if ( v77 )
          {
LABEL_142:
            FreeLibrary(v77);
            *((_QWORD *)v55 + 15) = 0;
          }
LABEL_143:
          CBulkRecord::~CBulkRecord(v55);
          operator delete(v55, 0xA0u);
        }
LABEL_564:
        v221 = v227;
        if ( v227 != (void *)-1LL )
        {
          v222 = DBGetHandlerForHandle(v227);
          if ( v222 )
            (*(void (__fastcall **)(struct IFileSystemHandler *, void *))(*(_QWORD *)v222 + 208LL))(v222, v221);
          else
            SetLastError(0x32u);
        }
        return 2147500037LL;
      }
    }
    v110 = *((_WORD *)&off_10336A680 + 12 * v100 + 4);
    v101 = *((_DWORD *)&off_10336A680 + 6 * v100 + 3);
    v115 = (int)(&off_10336A680)[3 * v100 + 1];
    v102 = v115 << 31 >> 31;
    v111 = v115 << 30 >> 31;
    v113 = v115 << 29 >> 31;
    v112 = v115 << 28 >> 31;
    if ( v113 && !v112 )
    {
      if ( v102 )
      {
        v110 = DbtFromXvt(0x3Au);
        v116 = 4;
      }
      else
      {
        v110 = DbtFromXvt(0x3Du);
        v116 = 8;
      }
      if ( v110 == 135 )
        v116 = 16;
      v292 = v116;
    }
LABEL_210:
    if ( (unsigned __int16)(v110 - 128) <= 2u )
    {
      v117 = *((_DWORD *)v240 + 10);
      if ( v117 > 0x1F40 || *((_DWORD *)v231 + 8) > 0x1F40u )
      {
        switch ( v110 )
        {
          case 0x80u:
            v101 = 3;
            break;
          case 0x81u:
            v101 = 1;
            break;
          case 0x82u:
            v101 = 2;
            break;
        }
        v111 = 1;
        if ( *((_DWORD *)v231 + 8) == -1 || v117 == -1 )
          v300 = 1;
      }
    }
    v118 = v246;
    v119 = v244;
    if ( v101 )
    {
      if ( v246 )
      {
        if ( v244 >= v229 )
        {
          v120 = (_OWORD *)(384 * v229 + v246 - 384);
          v121 = &v289;
          v122 = 3;
          do
          {
            *(_OWORD *)v121 = *v120;
            *((_OWORD *)v121 + 1) = v120[1];
            *((_OWORD *)v121 + 2) = v120[2];
            *((_OWORD *)v121 + 3) = v120[3];
            *((_OWORD *)v121 + 4) = v120[4];
            *((_OWORD *)v121 + 5) = v120[5];
            *((_OWORD *)v121 + 6) = v120[6];
            v121 += 16;
            *((_OWORD *)v121 - 1) = v120[7];
            v120 += 8;
            --v122;
          }
          while ( v122 );
          if ( (unsigned __int64)(v292 - 1) <= 0x5E )
          {
            v123 = v292 + 96;
            if ( (unsigned __int64)(v292 + 96) > 0x1F40 )
              v123 = 8000;
            v292 = v123;
          }
        }
      }
      v124 = v300;
      if ( !v102 )
        v124 = 1;
      v300 = v124;
    }
    if ( v118 && v119 >= v229 )
    {
      v125 = v118 + 384 * v229;
      v301 = *(_DWORD *)(v125 - 280);
      v302 = *(_BYTE *)(v125 - 276);
      v303 = *(_DWORD *)(v125 - 272);
      v126 = *(_DWORD *)(v125 - 268);
LABEL_244:
      v304 = v126;
      goto LABEL_245;
    }
    if ( !v242 || v303 == 99999 )
    {
      v301 = *(_DWORD *)(v252 + 64);
      v302 = *(_BYTE *)(v252 + 68);
      v126 = *(_DWORD *)(v252 + 56);
      goto LABEL_244;
    }
    v304 = v303;
    if ( FValidCollation(*(_DWORD *)(v232 + 116), 1) )
    {
      GetTDSCollation(v304, (struct TDSCOLLATION *)&v301);
    }
    else
    {
      v301 = 0;
      v302 = 0;
    }
    v118 = v246;
LABEL_245:
    v293 = v110;
    v297 = v113;
    v299 = v102;
    v294 = v101;
    switch ( v110 )
    {
      case 0x80u:
      case 0x81u:
      case 0x82u:
        v127 = v240;
        if ( v292 )
          goto LABEL_273;
        v134 = *((unsigned int *)v240 + 10);
        v128 = v229;
        if ( (int)v134 <= 0 )
        {
          v292 = 8000;
        }
        else
        {
          if ( (unsigned int)v134 > 0x1F40 )
            v134 = 8000;
          v292 = v134;
        }
        goto LABEL_274;
      case 0x83u:
        v127 = v240;
        if ( v240[40] )
        {
          v295 = v240[40];
          v296 = v240[44];
LABEL_273:
          v128 = v229;
        }
        else
        {
          if ( !v118 )
          {
            ex_callprint(4838, 16, 1);
            v230 = (int *)v55;
            if ( v55 )
            {
              CBulkFormat::Destroy(v55);
              operator delete[](*((void **)v55 + 18));
              v129 = *((_QWORD *)v55 + 16);
              if ( v129 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
              v130 = (HMODULE)*((_QWORD *)v55 + 15);
              if ( v130 )
              {
                FreeLibrary(v130);
                *((_QWORD *)v55 + 15) = 0;
              }
              CBulkRecord::~CBulkRecord(v55);
              operator delete(v55, 0xA0u);
            }
            v131 = v227;
            if ( v227 != (void *)-1LL )
            {
              v132 = DBGetHandlerForHandle(v227);
              if ( v132 )
              {
                (*(void (__fastcall **)(struct IFileSystemHandler *, void *))(*(_QWORD *)v132 + 208LL))(v132, v131);
                return 2147942487LL;
              }
              SetLastError(0x32u);
            }
            return 2147942487LL;
          }
          v128 = v229;
          v295 = *(_BYTE *)(384 * v229 + v118 - 304);
          v296 = *(_BYTE *)(384 * v229 + v118 - 303);
        }
LABEL_274:
        v135 = v244;
        if ( v118 && v244 >= v128 )
        {
          v291 |= *(_DWORD *)(384 * v128 + v118 - 352) & 0x20;
        }
        else
        {
LABEL_278:
          v128 = v229;
          if ( *((_DWORD *)v127 + 12) )
            v291 |= 0x20u;
        }
        if ( (v291 & 0x20) != 0 )
          goto LABEL_285;
        if ( v111 && (unsigned __int16)(v110 - 128) > 2u )
        {
          v298 = 0;
          v291 |= 0x10u;
        }
        else
        {
          v136 = DbtFromXvt(0x62u);
          v298 = 0;
          if ( v110 != v136 )
LABEL_285:
            v298 = 1;
        }
        v137 = &v289;
        v243 = &v289;
        if ( !v246 )
          goto LABEL_296;
        v138 = 384 * v128;
        v137 = &v289;
        v243 = &v289;
        if ( *(_DWORD *)(384 * v128 + v246 - 308) == 1 || *(_DWORD *)(384 * v128 + v246 - 308) == 2 )
        {
          if ( v110 == 129 )
            goto LABEL_292;
          v137 = &v289;
          v243 = &v289;
          if ( v110 == 130 )
          {
            v137 = (__int64 *)(v138 + v246 - 384);
            v243 = v137;
          }
        }
        else if ( *(_DWORD *)(384 * v128 + v246 - 308) == 3 )
        {
          if ( (unsigned __int16)(v110 - 129) <= 1u || (v137 = &v289, v243 = &v289, v110 == 128) )
          {
LABEL_292:
            v137 = (__int64 *)(v138 + v246 - 384);
            v243 = v137;
          }
        }
LABEL_296:
        if ( v135 >= v128 && v246 )
        {
          _mm_lfence();
          v139 = v246 + 384 * v128;
          v140 = *(_DWORD *)(v139 - 264);
          if ( v140 > 0x102 )
            v140 = 258;
          v141 = v232;
          *(_DWORD *)(v232 + 120) = v140;
          memcpy_s((void *const)(v141 + 124), 0x102u, (const void *const)(v139 - 260), v140);
          v55 = v239;
        }
        else
        {
          v142 = *((_QWORD *)v127 + 2);
          if ( v142 )
          {
            v143 = -1;
            do
              ++v143;
            while ( *(_WORD *)(v142 + 2 * v143) );
          }
          else
          {
            LODWORD(v143) = 0;
          }
          if ( 2 * (unsigned __int64)(unsigned int)v143 <= 0x100 )
          {
            if ( v142 )
            {
              v145 = -1;
              do
                ++v145;
              while ( *(_WORD *)(v142 + 2 * v145) );
            }
            else
            {
              LODWORD(v145) = 0;
            }
            v144 = 2 * v145;
          }
          else
          {
            v144 = 256;
          }
          *((_DWORD *)v137 + 30) = v144;
          v146 = &word_10280BED8;
          if ( *((_QWORD *)v127 + 2) )
            v146 = (const wchar_t *)*((_QWORD *)v127 + 2);
          v147 = (unsigned __int64)v144 >> 1;
          v148 = (char *)v137 + 124;
          if ( v147 <= 0x7FFFFFFE )
          {
            v149 = 129;
            v150 = v147 - 129;
            v151 = (char *)v146 - v148;
            do
            {
              if ( !(v150 + v149) )
                break;
              v152 = *(_WORD *)&v148[v151];
              if ( !v152 )
                break;
              *(_WORD *)v148 = v152;
              v148 += 2;
              --v149;
            }
            while ( v149 );
            v153 = v148 - 2;
            if ( v149 )
              v153 = v148;
            *(_WORD *)v153 = 0;
          }
          else
          {
            *(_WORD *)v148 = 0;
          }
        }
        break;
      case 0x87u:
      case 0x91u:
      case 0x92u:
        v127 = v240;
        if ( !v112 )
          goto LABEL_273;
        v296 = 7;
        v291 |= 0x40000000u;
        if ( v240[44] >= 0 )
        {
          v296 = v240[44];
          goto LABEL_273;
        }
        if ( v118 )
        {
          v128 = v229;
          v296 = *(_BYTE *)(384 * v229 + v118 - 303);
          goto LABEL_274;
        }
        v135 = v244;
        goto LABEL_278;
      default:
        v127 = v240;
        goto LABEL_273;
    }
LABEL_178:
    LODWORD(v235) = 0;
    LODWORD(v248) = 0;
    LODWORD(v249) = 0;
    v89 = 0;
    v236 = 0;
    v90 = GetDefaultLocale();
    v91 = String2;
    if ( _wcsnicmp_l(L"SQL", String2, 3u, v90) )
    {
      v92 = GetDefaultLocale();
      if ( _wcsnicmp_l(L"SYB", v91, 3u, v92) )
        goto LABEL_325;
    }
    v93 = 0;
    v94 = 0;
    v95 = (const wchar_t **)&off_10336A680;
    do
    {
      v96 = GetDefaultLocale();
      if ( !_wcsicmp_l(v91 + 3, *v95, v96) )
      {
        v98 = *((_WORD *)&off_10336A680 + 12 * v94 + 4);
        LODWORD(v235) = *((_DWORD *)&off_10336A680 + 6 * v94 + 3);
        v155 = (int)(&off_10336A680)[3 * v94 + 1];
        LODWORD(v248) = v155 << 31 >> 31;
        v237 = v155 << 30 >> 31;
        LODWORD(v249) = v155 << 29 >> 31;
        v89 = v155 << 28 >> 31;
        v236 = v89;
        goto LABEL_331;
      }
      ++v93;
      ++v94;
      v95 += 3;
    }
    while ( v93 < 0x1E );
    v97 = GetDefaultLocale();
    if ( _wcsicmp_l(v91 + 3, L"VARIANT", v97) )
    {
LABEL_325:
      ImpPrintError(0x18u, 0, (unsigned int)(v226 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
      v230 = (int *)v55;
      if ( v55 )
      {
        CBulkFormat::Destroy(v55);
        operator delete[](*((void **)v55 + 18));
        v154 = *((_QWORD *)v55 + 16);
        if ( v154 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 16LL))(v154);
        v77 = (HMODULE)*((_QWORD *)v55 + 15);
        if ( v77 )
          goto LABEL_142;
        goto LABEL_143;
      }
      goto LABEL_564;
    }
    v98 = DbtFromXvt(0x62u);
    v237 = 0;
LABEL_331:
    v156 = v231;
    if ( !v229 && *((_DWORD *)v231 + 8) > 0x1F40u )
    {
      switch ( v98 )
      {
        case 0x80u:
          LODWORD(v235) = 3;
          break;
        case 0x81u:
          LODWORD(v235) = 1;
          break;
        case 0x82u:
          LODWORD(v235) = 2;
          break;
      }
    }
    v241 = v98;
    v157 = v98;
    if ( *((_DWORD *)v231 + 7) == 2 )
    {
      v158 = *((_DWORD *)v231 + 9);
      LODWORD(v228) = v158;
      if ( v158 > 8 || (v159 = 278, !_bittest(&v159, v158)) )
      {
        v160 = v238;
        v161 = a9;
        ImpPrintError(0x19u, 0, (unsigned int)(v226 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
        v162 = -2147467259;
        goto LABEL_539;
      }
    }
    else
    {
      LODWORD(v228) = 0;
    }
    *(_QWORD *)(v232 + 40) = *((int *)v231 + 8);
    v163 = *((int *)v156 + 8);
    LODWORD(String2) = v163;
    if ( (int)v163 < 0 )
    {
      v160 = v238;
      v161 = a9;
      ImpPrintError(0x1Au, 0, (unsigned int)(v226 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
      v162 = -2147467259;
      goto LABEL_539;
    }
    v164 = v163;
    if ( (_DWORD)v163 && v98 != 12 && v98 != 13 && v98 != 128 && (unsigned int)v98 - 129 >= 2 )
    {
      if ( v98 != DbtFromXvt(0x62u) )
        LODWORD(v163) = -1;
      LODWORD(String2) = v163;
    }
    if ( *((_DWORD *)v156 + 7) != 3 )
    {
      v175 = 0;
      goto LABEL_378;
    }
    v165 = (const wchar_t *)*((_QWORD *)v156 + 5);
    if ( v225 )
    {
      v174 = &word_10280BED8;
      if ( v165 )
        v174 = (const wchar_t *)*((_QWORD *)v156 + 5);
      v173 = bcpConvertWideLiteralToBinary(v174, v333, 258);
      goto LABEL_374;
    }
    if ( !v165 )
    {
      LODWORD(v167) = 0;
      goto LABEL_364;
    }
    v166 = -1;
    do
      ++v166;
    while ( v165[v166] );
    if ( (unsigned int)v166 < 0x80 )
    {
      v167 = -1;
      do
        ++v167;
      while ( v165[v167] );
LABEL_364:
      v168 = (unsigned int)v167;
      if ( !v165 )
        v165 = &word_10280BED8;
      goto LABEL_366;
    }
    v168 = 128;
LABEL_366:
    v169 = GetDefaultLocale();
    v170 = _wcstombs_l(Dest, v165, v168, v169);
    v171 = 0;
    if ( v170 )
      v171 = v170;
    v172 = 128;
    if ( v171 < 0x80 )
      v172 = v171;
    Dest[v172] = 0;
    v173 = bcpConvertLiteralToBinary((unsigned __int8 *)Dest);
LABEL_374:
    v175 = v173;
    if ( v173 == -1 )
    {
      v160 = v238;
      v161 = a9;
      ImpPrintError(0x1Bu, 0, (unsigned int)(v226 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
      v162 = -2147467259;
      goto LABEL_539;
    }
    LODWORD(v163) = (_DWORD)String2;
LABEL_378:
    if ( !(_DWORD)v228 && !(_DWORD)v163 && !v175 && v229 )
    {
      ImpPrintError(0x52u, 0, (unsigned int)(v226 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
      v230 = (int *)v55;
      if ( v55 )
      {
        CBulkFormat::Destroy(v55);
        operator delete[](*((void **)v55 + 18));
        v176 = *((_QWORD *)v55 + 16);
        if ( v176 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v176 + 16LL))(v176);
        v77 = (HMODULE)*((_QWORD *)v55 + 15);
        if ( v77 )
          goto LABEL_142;
        goto LABEL_143;
      }
      goto LABEL_564;
    }
    if ( !v243 )
    {
      v177 = (char)v249;
LABEL_407:
      v181 = v232;
      goto LABEL_408;
    }
    if ( (unsigned __int16)(v98 - 129) <= 1u && *((_DWORD *)v243 + 19) == 1 )
    {
      LODWORD(v235) = 1;
LABEL_398:
      v98 = *((_WORD *)v243 + 34);
      *(_QWORD *)(v232 + 48) = v243[6];
      goto LABEL_399;
    }
    if ( (unsigned __int16)(v98 - 129) <= 1u && *((_DWORD *)v243 + 19) == 2 )
    {
      LODWORD(v235) = 2;
      goto LABEL_398;
    }
    if ( (unsigned __int16)(v98 - 128) <= 2u && *((_DWORD *)v243 + 19) == 3 )
    {
      LODWORD(v235) = 3;
      goto LABEL_398;
    }
    if ( (unsigned int)((_DWORD)v235 - 1) <= 2 )
      goto LABEL_398;
LABEL_399:
    v177 = (char)v249;
    if ( !(_DWORD)v249 || v89 )
      goto LABEL_407;
    v178 = 61;
    v179 = v248;
    if ( (_DWORD)v248 )
      v178 = 58;
    v98 = DbtFromXvt(v178);
    v180 = 8;
    if ( v179 )
      v180 = 4;
    v181 = v232;
    *(_QWORD *)(v232 + 48) = v180;
LABEL_408:
    LODWORD(v240) = v226 + 1;
    *(_QWORD *)(v181 + 16) = (unsigned int)(v226 + 1);
    *(_WORD *)(v181 + 68) = v98;
    *(_BYTE *)(v181 + 85) = (_BYTE)v228;
    *(_BYTE *)(v181 + 90) = 0;
    *(_BYTE *)(v181 + 87) = v248;
    *(_BYTE *)(v181 + 84) = v177;
    *(_DWORD *)(v181 + 76) = (_DWORD)v235;
    v182 = v181 + 104;
    *(_DWORD *)(v181 + 104) = v233;
    *(_BYTE *)(v181 + 108) = v234;
    *(_WORD *)(v181 + 70) = v241;
    *(_QWORD *)(v181 + 56) = -1;
    *(_DWORD *)(v181 + 64) = -1;
    if ( v157 == 129 && ((unsigned __int16)(v98 - 129) <= 1u || v98 == 141) )
    {
      if ( v242 == 2 )
      {
        if ( *(_DWORD *)v182 || *(_BYTE *)(v181 + 108) )
        {
          v184 = CIDFromTDSCollation((const struct TDSCOLLATION *)(v181 + 104));
          v183 = UICodePageFromCID(v184);
          v181 = v232;
        }
        else
        {
          v183 = 99999;
        }
      }
      else
      {
        v183 = *(_DWORD *)(v252 + 60);
      }
      *(_DWORD *)(v181 + 112) = v183;
    }
    v185 = 2 * v254;
    *(_DWORD *)(*(_QWORD *)v253 + 16 * v254) = v175;
    if ( v175 )
    {
      v186 = v333;
      if ( !v225 )
        v186 = Dest;
      v187 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v188 = *(_QWORD *)(v187 + 256);
      if ( !v188 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v188 = *(_QWORD *)(v187 + 256);
      }
      v189 = operator new[](
               v175,
               *(struct IMemObj **)(v188 + 1000),
               "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impdisk.cpp",
               2205,
               5u);
      v190 = (_QWORD *)v253;
      *(_QWORD *)(*(_QWORD *)v253 + 8 * v185 + 8) = v189;
      memcpy_s(*(void *const *)(*v190 + 8 * v185 + 8), v175, v186, v175);
      v55 = v239;
      v181 = v232;
    }
    if ( v98 == 135 && v236 )
      *(_DWORD *)(v181 + 32) |= 0x40000000u;
    v191 = (int)String2;
    if ( (_DWORD)String2 == -1 )
    {
      switch ( v98 )
      {
        case 2u:
          *(_QWORD *)(v181 + 48) = 2;
          goto LABEL_436;
        case 3u:
        case 4u:
          *(_QWORD *)(v181 + 48) = 4;
          goto LABEL_436;
        case 5u:
        case 6u:
        case 0x14u:
        case 0x87u:
          if ( (_DWORD)v249 )
            goto LABEL_433;
          v192 = 8;
          break;
        case 0xBu:
        case 0x11u:
          *(_QWORD *)(v181 + 48) = 1;
          goto LABEL_436;
        case 0x83u:
          v193 = (int)v228;
          if ( (_DWORD)v228 )
            goto LABEL_460;
          if ( !v175 )
            *(_QWORD *)(v181 + 48) = v164;
          goto LABEL_438;
        default:
          if ( !(_DWORD)v249 )
            goto LABEL_436;
LABEL_433:
          if ( v98 == 135 )
          {
            v192 = 16;
          }
          else
          {
            v192 = 8;
            if ( (_DWORD)v248 )
              v192 = 4;
          }
          break;
      }
      *(_QWORD *)(v181 + 48) = v192;
LABEL_436:
      v193 = (int)v228;
      goto LABEL_437;
    }
    if ( (_DWORD)String2 )
    {
      v196 = *(_QWORD *)(v181 + 40);
      if ( v196 != (int)String2 )
      {
        *(_QWORD *)(v181 + 40) = (int)String2;
        v196 = v191;
      }
      if ( (_DWORD)v235 )
        goto LABEL_436;
      v195 = v196 - 1;
      v193 = (int)v228;
      goto LABEL_454;
    }
    v193 = (int)v228;
    if ( !v229 && !v175 && !(_DWORD)v228 )
      goto LABEL_438;
    if ( !(_DWORD)v235 )
    {
      v195 = *(_QWORD *)(v181 + 40) - 1LL;
LABEL_454:
      if ( v195 > 0x1F3F )
        *(_QWORD *)(v181 + 40) = 8000;
    }
LABEL_437:
    if ( v193 )
      goto LABEL_460;
LABEL_438:
    if ( (unsigned __int16)(v241 - 129) > 1u )
    {
LABEL_460:
      v194 = 1;
      goto LABEL_461;
    }
    v194 = 0;
LABEL_461:
    *(_BYTE *)(v181 + 88) = v194;
    if ( (unsigned __int16)(v98 - 128) > 2u || v193 <= 0 && v175 <= 0 )
    {
      v197 = v243;
    }
    else
    {
      v197 = v243;
      if ( !v243 )
        goto LABEL_480;
      if ( (unsigned __int16)(*((_WORD *)v243 + 34) - 128) <= 2u || *((_WORD *)v197 + 34) == DbtFromXvt(0x62u) )
      {
        v199 = 1;
        v198 = 0;
      }
      else
      {
        v198 = 0;
        v199 = 0;
      }
      if ( !v199 )
        v198 = v237;
      if ( v198 )
      {
        if ( (int)v191 > 0 && !(_DWORD)v228 && !v175 )
        {
          v181 = v232;
          *(_DWORD *)(v232 + 32) |= 0x10u;
          goto LABEL_480;
        }
        if ( (unsigned __int16)(v98 - 128) > 2u )
        {
          v181 = v232;
          *(_DWORD *)(v232 + 32) |= 0x10u;
          goto LABEL_480;
        }
      }
      v181 = v232;
    }
LABEL_480:
    v200 = (int)v235;
    if ( (_DWORD)v235 )
    {
      *(_DWORD *)(v181 + 32) |= 0x80u;
      if ( !v197 )
        goto LABEL_521;
      *(_BYTE *)(v181 + 92) = *((_BYTE *)v197 + 92);
    }
    else if ( !v197 )
    {
LABEL_521:
      *(_DWORD *)(v181 + 32) |= 0x20u;
      goto LABEL_522;
    }
    if ( (v197[4] & 0x20) != 0 )
      *(_DWORD *)(v181 + 32) |= 0x20u;
    if ( !*((_BYTE *)v197 + 86) && (v197[4] & 0x10) != 0 )
      *(_DWORD *)(v181 + 32) |= 0x10u;
    if ( *((_WORD *)v197 + 34) == 135 && (v197[4] & 0x40000000) != 0 )
      *(_DWORD *)(v181 + 32) |= 0x40000000u;
    *(_QWORD *)(v181 + 96) = v197[12];
    *(_BYTE *)(v181 + 80) = *((_BYTE *)v197 + 80);
    *(_BYTE *)(v181 + 81) = *((_BYTE *)v197 + 81);
    *(_BYTE *)(v181 + 86) = *((_BYTE *)v197 + 86);
    *(_WORD *)(v181 + 68) = *((_WORD *)v197 + 34);
    *(_BYTE *)(v181 + 84) = *((_BYTE *)v197 + 84);
    *(_BYTE *)(v181 + 87) = *((_BYTE *)v197 + 87);
    v201 = *((_DWORD *)v197 + 30);
    if ( v201 > 0x102 )
      v201 = 258;
    *(_DWORD *)(v181 + 120) = v201;
    memcpy_s((void *const)(v181 + 124), 0x102u, (char *)v197 + 124, v201);
    v202 = v232;
    if ( !*(_QWORD *)(v232 + 48) )
    {
      if ( (unsigned __int16)(*(_WORD *)(v232 + 68) - 128) <= 1u
        || (v203 = *(_WORD *)(v232 + 68), v203 == DbtFromXvt(0x62u)) )
      {
        v204 = *(_QWORD *)(v202 + 40);
      }
      else
      {
        if ( v203 != 130 )
          goto LABEL_504;
        v204 = *(_QWORD *)(v202 + 40);
        if ( *(_WORD *)(v202 + 70) == 129 )
        {
          if ( v204 > 0xFA0 )
            v204 = 4000;
        }
        else
        {
          v204 >>= 1;
        }
      }
      *(_QWORD *)(v202 + 48) = v204;
    }
LABEL_504:
    v205 = *(_WORD *)(v202 + 68);
    if ( v205 == 129 || (v206 = *(_WORD *)(v202 + 68), v200 == 1) )
    {
      v206 = *(_WORD *)(v202 + 68);
      if ( *(_DWORD *)(v202 + 112) != 99999 )
      {
        if ( *((_DWORD *)v197 + 26) || *((_BYTE *)v197 + 108) )
        {
          v207 = CIDFromTDSCollation((const struct TDSCOLLATION *)(v197 + 13));
          v208 = UICodePageFromCID(v207);
          v206 = *(_WORD *)(v202 + 68);
          *(_DWORD *)(v202 + 116) = v208;
          v205 = v206;
          if ( v208 != 99999 )
            goto LABEL_512;
        }
        else
        {
          *(_DWORD *)(v202 + 116) = 99999;
        }
        *(_DWORD *)(v202 + 116) = *(_DWORD *)(v202 + 112);
        v206 = v205;
      }
    }
LABEL_512:
    if ( v206 != 130 && v200 != 2 || !v242 || !*(_DWORD *)v182 && !*(_BYTE *)(v202 + 108) )
    {
      if ( *((_DWORD *)v197 + 26) || *((_BYTE *)v197 + 108) )
      {
        *(_DWORD *)v182 = *((_DWORD *)v197 + 26);
        *(_BYTE *)(v182 + 4) = *((_BYTE *)v197 + 108);
      }
      else
      {
        v209 = v252;
        *(_DWORD *)v182 = *(_DWORD *)(v252 + 64);
        *(_BYTE *)(v182 + 4) = *(_BYTE *)(v209 + 68);
      }
    }
LABEL_522:
    if ( v250 == 1 )
    {
      v210 = *((_DWORD *)v231 + 6);
      if ( (unsigned int)(v210 - 1) > 1 || *((_DWORD *)v231 + 7) != 3 )
        goto LABEL_532;
      v211 = 24;
      if ( v230 )
        v211 = (__int64)(v230 - 6);
      if ( *(_DWORD *)v211 != v210 )
      {
LABEL_532:
        v160 = v238;
        v161 = a9;
        ImpPrintError(0x62u, 0, (unsigned int)(v226 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
        v162 = -2147467259;
        goto LABEL_539;
      }
      v212 = v247;
      if ( v226 != v247 - 1 )
      {
        v213 = *(_DWORD *)(*(_QWORD *)v253 + 8 * v185);
        if ( **(_DWORD **)v253 != v213
          || memcmp_0(*(const void **)(*(_QWORD *)v253 + 8LL), *(const void **)(*(_QWORD *)v253 + 8 * v185 + 8), v213) )
        {
          v160 = v238;
          v161 = a9;
          ImpPrintError(0x63u, 0, (unsigned int)(v226 + 1), 0, 0, a9, v238, 0, 0, 0, 0, 0x10u, 1, 0);
          v162 = -2147467259;
          goto LABEL_539;
        }
      }
    }
    else
    {
      v212 = v247;
    }
    v54 = (int)v240;
    v226 = (int)v240;
    v56 = ++v254;
    if ( (unsigned int)v240 >= v212 )
      break;
    v53 = v255;
    v51 = v256;
  }
  v160 = v238;
  v161 = a9;
  v162 = v257;
LABEL_539:
  if ( !v251 )
  {
LABEL_552:
    ImpPrintError(0x16u, 0, 0, 0, 0, v161, v160, 0, 0, 0, 0, 0x10u, 1, 0);
    v230 = (int *)v55;
    if ( v55 )
    {
      CBulkFormat::Destroy(v55);
      operator delete[](*((void **)v55 + 18));
      v218 = *((_QWORD *)v55 + 16);
      if ( v218 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v218 + 16LL))(v218);
      v77 = (HMODULE)*((_QWORD *)v55 + 15);
      if ( v77 )
        goto LABEL_142;
      goto LABEL_143;
    }
    goto LABEL_564;
  }
  v230 = (int *)v55;
  if ( v55 )
  {
    CBulkFormat::Destroy(v55);
    operator delete[](*((void **)v55 + 18));
    v214 = *((_QWORD *)v55 + 16);
    if ( v214 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
    v215 = (HMODULE)*((_QWORD *)v55 + 15);
    if ( v215 )
    {
      FreeLibrary(v215);
      *((_QWORD *)v55 + 15) = 0;
    }
    CBulkRecord::~CBulkRecord(v55);
    operator delete(v55, 0xA0u);
  }
  v216 = v227;
  if ( v227 != (void *)-1LL )
  {
    v217 = DBGetHandlerForHandle(v227);
    if ( v217 )
    {
      (*(void (__fastcall **)(struct IFileSystemHandler *, void *))(*(_QWORD *)v217 + 208LL))(v217, v216);
      return v162;
    }
    SetLastError(0x32u);
  }
  return v162;
}

```

## disassembly

```asm
0x102083b40  push    rbx
0x102083b42  push    rsi
0x102083b43  push    rdi
0x102083b44  push    r12
0x102083b46  push    r13
0x102083b48  push    r14
0x102083b4a  push    r15
0x102083b4c  mov     eax, 26B0h
0x102083b51  call    _alloca_probe
0x102083b56  sub     rsp, rax
0x102083b59  mov     [rsp+26E8h+var_24C8], 0FFFFFFFFFFFFFFFEh
0x102083b65  mov     rax, cs:__security_cookie
0x102083b6c  xor     rax, rsp
0x102083b6f  mov     [rsp+26E8h+var_48], rax
0x102083b77  mov     [rsp+26E8h+var_2598], r9
0x102083b7f  mov     r14, r8
0x102083b82  mov     [rsp+26E8h+var_25F0], rdx
0x102083b8a  mov     [rsp+26E8h+var_2600], rcx
0x102083b92  mov     rax, [rsp+26E8h+arg_20]
0x102083b9a  mov     [rsp+26E8h+var_25C0], rax
0x102083ba2  mov     rax, [rsp+26E8h+arg_28]
0x102083baa  mov     [rsp+26E8h+var_2590], rax
0x102083bb2  mov     r15, [rsp+26E8h+arg_38]
0x102083bba  mov     [rsp+26E8h+var_2628], r15
0x102083bc2  mov     [rsp+26E8h+var_2650], r15
0x102083bca  mov     rsi, [rsp+26E8h+arg_48]
0x102083bd2  mov     rcx, [rsp+26E8h+arg_58]
0x102083bda  mov     [rsp+26E8h+var_25C8], rcx
0x102083be2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x102083be9  mov     [rsp+26E8h+var_2670], rax
0x102083bee  xor     edi, edi
0x102083bf0  mov     [rsp+26E8h+var_25CC], edi
0x102083bf7  mov     ebx, edi
0x102083bf9  mov     eax, [rcx+40h]
0x102083bfc  mov     [rsp+26E8h+var_2640], eax
0x102083c03  movzx   eax, byte ptr [rcx+44h]
0x102083c07  mov     [rsp+26E8h+var_263C], al
0x102083c0e  mov     [rsp+26E8h+var_2620], rdi
0x102083c16  mov     rax, [rsp+26E8h+arg_30]
0x102083c1e  mov     eax, [rax+44h]
0x102083c21  mov     [rsp+26E8h+var_25D0], eax
0x102083c28  test    r15, r15
0x102083c2b  jz      loc_10208661B
0x102083c31  cmp     di, [r15]
0x102083c35  jz      loc_10208661B
0x102083c3b  mov     r12, [rsp+26E8h+arg_40]
0x102083c43  test    r12, r12
0x102083c46  jz      loc_10208661B
0x102083c4c  cmp     [rsp+26E8h+arg_50], rdi
0x102083c54  jz      loc_102083F67
0x102083c5a  mov     r13d, 1
0x102083c60  mov     edx, r13d
0x102083c63  lea     rcx, [rsp+26E8h+var_2588]
0x102083c6b  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x102083c70  nop
0x102083c71  lea     rax, [rsp+26E8h+var_2578]
0x102083c79  mov     [rsp+26E8h+var_2658], rax
0x102083c81  mov     [rsp+26E8h+var_2568], 20000235h
0x102083c8c  mov     [rsp+26E8h+var_2560], rdi
0x102083c94  mov     [rsp+26E8h+var_2550], rdi
0x102083c9c  mov     [rsp+26E8h+var_2558], rdi
0x102083ca4  mov     [rsp+26E8h+var_2548], rdi
0x102083cac  mov     [rsp+26E8h+var_2538], dil
0x102083cb4  mov     rdx, gs:58h
0x102083cbd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102083cc4  mov     ecx, [rax]
0x102083cc6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102083ccd  mov     ebx, [rax]
0x102083ccf  add     rbx, [rdx+rcx*8]
0x102083cd3  mov     rax, [rbx+100h]
0x102083cda  test    rax, rax
0x102083cdd  jnz     short loc_102083CEE
0x102083cdf  xor     ecx, ecx
0x102083ce1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x102083ce7  mov     rax, [rbx+100h]
0x102083cee  mov     rcx, [rax+258h]
0x102083cf5  test    rcx, rcx
0x102083cf8  jz      short loc_102083D12
0x102083cfa  lea     rdx, [rsp+26E8h+var_2568]
0x102083d02  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x102083d08  test    eax, eax
0x102083d0a  setz    [rsp+26E8h+var_2538]
0x102083d12  mov     rdx, gs:58h
0x102083d1b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102083d22  mov     ecx, [rax]
0x102083d24  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102083d2b  mov     ebx, [rax]
0x102083d2d  add     rbx, [rdx+rcx*8]
0x102083d31  mov     rdx, [rbx+100h]
0x102083d38  test    rdx, rdx
0x102083d3b  jnz     short loc_102083D4C
0x102083d3d  xor     ecx, ecx
0x102083d3f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x102083d45  mov     rdx, [rbx+100h]
0x102083d4c  mov     [rsp+26E8h+var_2570], rdx
0x102083d54  mov     eax, [rdx+320h]
0x102083d5a  shr     eax, 0Bh
0x102083d5d  and     eax, 1
0x102083d60  mov     [rsp+26E8h+var_2574], eax
0x102083d67  jnz     short loc_102083D7B
0x102083d69  test    byte ptr [rdx+320h], 4
0x102083d70  jz      short loc_102083D7B
0x102083d72  mov     [rsp+26E8h+var_2578], edi
0x102083d79  jmp     short loc_102083D91
0x102083d7b  mov     [rsp+26E8h+var_2578], r13d
0x102083d83  mov     rcx, [rdx+260h]
0x102083d8a  mov     rax, [rcx]
0x102083d8d  call    qword ptr [rax+8]
0x102083d90  nop
0x102083d91  mov     rdx, gs:58h
0x102083d9a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102083da1  mov     ecx, [rax]
0x102083da3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102083daa  mov     r8d, [rax]
0x102083dad  mov     rax, [rdx+rcx*8]
0x102083db1  mov     rax, [r8+rax]
0x102083db5  cmp     cs:dword_103172554, 0
0x102083dbc  jnz     short loc_102083DE5
0x102083dbe  cmp     byte ptr [rax], 0
0x102083dc1  jnz     short loc_102083DE5
0x102083dc3  mov     rax, gs:58h
0x102083dcc  mov     rcx, [rax+rcx*8]
0x102083dd0  mov     rax, [rcx+r8]
0x102083dd4  mov     rcx, [rax+48h]
0x102083dd8  call    cs:__imp_?intnl_impersonate_client@@YAHPEAVCSession@@@Z; intnl_impersonate_client(CSession *)
0x102083dde  cmp     eax, 1
0x102083de1  setz    dil
0x102083de5  mov     [rsp+26E8h+var_262C], edi
0x102083dec  lea     rax, [rsp+26E8h+var_2670]
0x102083df1  mov     [rsp+26E8h+var_26C8], rax; void **
0x102083df6  mov     rax, [rsp+26E8h+var_25C8]
0x102083dfe  movzx   r9d, word ptr [rax+4Ch]; unsigned __int16
0x102083e03  xor     r8d, r8d; wchar_t *
0x102083e06  mov     rdx, rsi; wchar_t *
0x102083e09  mov     rcx, r15; wchar_t *
0x102083e0c  call    ?CreateAzureFileRead@@YAHPEB_W00GAEAPEAX@Z; CreateAzureFileRead(wchar_t const *,wchar_t const *,wchar_t const *,ushort,void * &)
0x102083e11  test    eax, eax
0x102083e13  jnz     loc_102083EC0
0x102083e19  test    edi, edi
0x102083e1b  jz      short loc_102083E4D
0x102083e1d  mov     r8, gs:58h
0x102083e26  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102083e2d  mov     ecx, [rax]
0x102083e2f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102083e36  mov     edx, [rax]
0x102083e38  add     rdx, [r8+rcx*8]
0x102083e3c  mov     rcx, [rdx]
0x102083e3f  mov     edx, r13d
0x102083e42  mov     rcx, [rcx+48h]
0x102083e46  call    cs:__imp_?intnl_revert_to_self@@YAHPEAVCSession@@H@Z; intnl_revert_to_self(CSession *,int)
0x102083e4c  nop
0x102083e4d  lea     rax, [rsp+26E8h+var_2578]
0x102083e55  mov     [rsp+26E8h+var_2658], rax
0x102083e5d  cmp     [rsp+26E8h+var_2578], 0
0x102083e65  jz      short loc_102083E96
0x102083e67  mov     rdx, [rsp+26E8h+var_2570]
0x102083e6f  mov     rcx, [rdx+260h]
0x102083e76  cmp     [rsp+26E8h+var_2574], 0
0x102083e7e  jz      short loc_102083E8C
0x102083e80  or      dword ptr [rdx+320h], 800h
0x102083e8a  jmp     short loc_102083E96
0x102083e8c  mov     rax, [rcx]
0x102083e8f  mov     r8d, r13d
0x102083e92  call    qword ptr [rax+10h]
0x102083e95  nop
0x102083e96  lea     rcx, [rsp+26E8h+var_2568]; this
0x102083e9e  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x102083ea3  nop
0x102083ea4  mov     ecx, [rsp+26E8h+var_2588]
0x102083eab  not     ecx
0x102083ead  mov     rax, [rsp+26E8h+var_2580]
0x102083eb5  and     [rax+268h], ecx
0x102083ebb  jmp     loc_102086575
0x102083ec0  call    cs:__imp_GetLastError
0x102083ec6  mov     ebx, eax
0x102083ec8  test    edi, edi
0x102083eca  jz      short loc_102083EFC
0x102083ecc  mov     r8, gs:58h
0x102083ed5  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x102083edc  mov     edx, [rcx]
0x102083ede  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x102083ee5  mov     ecx, [rcx]
0x102083ee7  add     rcx, [r8+rdx*8]
0x102083eeb  mov     rcx, [rcx]
0x102083eee  mov     edx, r13d
0x102083ef1  mov     rcx, [rcx+48h]
0x102083ef5  call    cs:__imp_?intnl_revert_to_self@@YAHPEAVCSession@@H@Z; intnl_revert_to_self(CSession *,int)
0x102083efb  nop
0x102083efc  lea     rax, [rsp+26E8h+var_2578]
0x102083f04  mov     [rsp+26E8h+var_2658], rax
0x102083f0c  cmp     [rsp+26E8h+var_2578], 0
0x102083f14  jz      short loc_102083F45
0x102083f16  mov     rdx, [rsp+26E8h+var_2570]
0x102083f1e  mov     rcx, [rdx+260h]
0x102083f25  cmp     [rsp+26E8h+var_2574], 0
0x102083f2d  jz      short loc_102083F3B
0x102083f2f  or      dword ptr [rdx+320h], 800h
0x102083f39  jmp     short loc_102083F45
0x102083f3b  mov     rax, [rcx]
0x102083f3e  mov     r8d, r13d
0x102083f41  call    qword ptr [rax+10h]
0x102083f44  nop
0x102083f45  lea     rcx, [rsp+26E8h+var_2568]; this
0x102083f4d  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x102083f52  nop
0x102083f53  mov     ecx, [rsp+26E8h+var_2588]
0x102083f5a  mov     rax, [rsp+26E8h+var_2580]
0x102083f62  jmp     loc_1020842F1
0x102083f67  mov     rdx, gs:58h
0x102083f70  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102083f77  mov     ecx, [rax]
0x102083f79  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102083f80  mov     eax, [rax]
0x102083f82  add     rax, [rdx+rcx*8]
0x102083f86  mov     rax, [rax]
0x102083f89  mov     rcx, [rax+48h]
0x102083f8d  test    byte ptr [rcx+10Eh], 4
0x102083f94  jnz     loc_1020865C0
0x102083f9a  mov     r13d, 1
0x102083fa0  mov     edx, r13d
0x102083fa3  lea     rcx, [rsp+26E8h+var_2528]
0x102083fab  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x102083fb0  nop
0x102083fb1  lea     rax, [rsp+26E8h+var_2518]
0x102083fb9  mov     [rsp+26E8h+var_2658], rax
0x102083fc1  mov     [rsp+26E8h+var_2508], 20000235h
0x102083fcc  mov     [rsp+26E8h+var_2500], rdi
0x102083fd4  mov     [rsp+26E8h+var_24F0], rdi
0x102083fdc  mov     [rsp+26E8h+var_24F8], rdi
0x102083fe4  mov     [rsp+26E8h+var_24E8], rdi
0x102083fec  mov     [rsp+26E8h+var_24D8], 0
0x102083ff4  mov     rdx, gs:58h
0x102083ffd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102084004  mov     ecx, [rax]
0x102084006  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10208400d  mov     ebx, [rax]
0x10208400f  add     rbx, [rdx+rcx*8]
0x102084013  mov     rax, [rbx+100h]
0x10208401a  test    rax, rax
0x10208401d  jnz     short loc_10208402E
0x10208401f  xor     ecx, ecx
0x102084021  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x102084027  mov     rax, [rbx+100h]
0x10208402e  mov     rcx, [rax+258h]
0x102084035  test    rcx, rcx
0x102084038  jz      short loc_102084052
0x10208403a  lea     rdx, [rsp+26E8h+var_2508]
0x102084042  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x102084048  test    eax, eax
0x10208404a  setz    [rsp+26E8h+var_24D8]
0x102084052  mov     rdx, gs:58h
0x10208405b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102084062  mov     ecx, [rax]
0x102084064  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10208406b  mov     ebx, [rax]
0x10208406d  add     rbx, [rdx+rcx*8]
0x102084071  mov     rdx, [rbx+100h]
0x102084078  test    rdx, rdx
0x10208407b  jnz     short loc_10208408C
0x10208407d  xor     ecx, ecx
0x10208407f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x102084085  mov     rdx, [rbx+100h]
0x10208408c  mov     [rsp+26E8h+var_2510], rdx
0x102084094  mov     eax, [rdx+320h]
0x10208409a  shr     eax, 0Bh
0x10208409d  and     eax, 1
0x1020840a0  mov     [rsp+26E8h+var_2514], eax
0x1020840a7  jnz     short loc_1020840BB
0x1020840a9  test    byte ptr [rdx+320h], 4
0x1020840b0  jz      short loc_1020840BB
0x1020840b2  mov     [rsp+26E8h+var_2518], edi
0x1020840b9  jmp     short loc_1020840D1
0x1020840bb  mov     [rsp+26E8h+var_2518], r13d
0x1020840c3  mov     rcx, [rdx+260h]
0x1020840ca  mov     rax, [rcx]
0x1020840cd  call    qword ptr [rax+8]
0x1020840d0  nop
0x1020840d1  mov     rdx, gs:58h
0x1020840da  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020840e1  mov     ecx, [rax]
0x1020840e3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020840ea  mov     r8d, [rax]
0x1020840ed  mov     rax, [rdx+rcx*8]
0x1020840f1  mov     rax, [r8+rax]
0x1020840f5  cmp     cs:dword_103172554, 0
0x1020840fc  jnz     short loc_102084125
0x1020840fe  cmp     byte ptr [rax], 0
0x102084101  jnz     short loc_102084125
0x102084103  mov     rax, gs:58h
0x10208410c  mov     rcx, [rax+rcx*8]
0x102084110  mov     rax, [rcx+r8]
0x102084114  mov     rcx, [rax+48h]
0x102084118  call    cs:__imp_?intnl_impersonate_client@@YAHPEAVCSession@@@Z; intnl_impersonate_client(CSession *)
0x10208411e  cmp     eax, 1
0x102084121  setz    dil
0x102084125  mov     [rsp+26E8h+var_2630], edi
0x10208412c  mov     eax, 0FFFFh
0x102084131  mov     [rsp+26E8h+var_22B8], ax
0x102084139  mov     [rsp+26E8h+var_22B4], 7FFFFFFFh
0x102084144  xor     ecx, ecx
  ... truncated ...
```
