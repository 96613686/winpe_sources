# CStmtCreateLogin::XretExecute(CCompExecCtxtStmt const &,CExecuteStatement *,CMsqlExecContext *)

- ea: `0x101467110`
- end: `0x10146a710`
- name: `?XretExecute@CStmtCreateLogin@@UEBA?AW4EXRetType@@AEBVCCompExecCtxtStmt@@PEAVCExecuteStatement@@PEAVCMsqlExecContext@@@Z`
- size: `13824`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401400`
- `0x100401433`
- `0x100403080`
- `0x10040be50`
- `0x10041a970`
- `0x100430960`
- `0x100440d70`
- `0x100445500`
- `0x10054bd60`
- `0x1006f7e90`
- `0x1006fa910`
- `0x100754350`
- `0x100754dc0`
- `0x100755650`
- `0x100755b10`
- `0x10097edb0`
- `0x100a51a50`
- `0x100dda070`
- `0x10121d760`
- `0x10121d890`
- `0x10138d660`
- `0x10138eb30`
- `0x101394e70`
- `0x1013b5000`
- `0x101452ac0`
- `0x10145b010`
- `0x10145b520`
- `0x10145bd10`
- `0x101466bb0`
- `0x101467110`
- `0x10149cf70`
- `0x10149e850`
- `0x10149f420`
- `0x1014b9c60`
- `0x1014be930`
- `0x1014c1950`
- `0x1014c5210`
- `0x1014c6a30`
- `0x101519620`
- `0x10154c680`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x101468009`
- `RPCRT4!UuidFromStringW` at `0x101468009`
- `KERNEL32!GetLastError` at `0x101469498`
- `KERNEL32!GetLastError` at `0x101469498`
- `ADVAPI32!GetSidSubAuthority` at `0x10146948f`
- `ADVAPI32!GetSidSubAuthority` at `0x10146948f`
- `ole32!CoCreateGuid` at `0x1014671b4`
- `ole32!CoCreateGuid` at `0x101468bea`
- `ole32!CoCreateGuid` at `0x1014671b4`
- `ole32!CoCreateGuid` at `0x101468bea`
- `secforwarder!CertFreeCertificateContext` at `0x101469a37`
- `secforwarder!CertFreeCertificateContext` at `0x101469a37`
- `secforwarder!CertCloseStore` at `0x101469a56`
- `secforwarder!CertCloseStore` at `0x101469a56`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10146a09e`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101468a62`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101469471`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101469478`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101469478`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101467e10`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1014688a3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101468927`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101468a0d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101467e10`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1014688a3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101468927`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101468a0d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101467992`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101467992`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467461`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467534`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467591`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467788`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467cee`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467da9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467ea6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014680a4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014681f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468210`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146828a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014686e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468804`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468880`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468974`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468a5a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468b2c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468b78`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468bcd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468c03`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468c5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468cb4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468d59`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468fe5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469003`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469038`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146905d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014690ef`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146910b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469403`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469575`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469601`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146967e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014696eb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469797`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014699b3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469a24`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469aca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469b77`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469cab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469d79`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469efb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a2f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a348`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a405`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a444`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a518`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a668`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a686`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a704`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467461`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467534`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467591`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467788`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467cee`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467da9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101467ea6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014680a4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014681f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468210`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146828a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014686e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468804`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468880`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468974`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468a5a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468b2c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468b78`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468bcd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468c03`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468c5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468cb4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468d59`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101468fe5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469003`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469038`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146905d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014690ef`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146910b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469403`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469575`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469601`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146967e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014696eb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469797`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014699b3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469a24`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469aca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469b77`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469cab`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469d79`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101469efb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a2f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a348`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a405`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a444`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a518`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a668`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a686`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10146a704`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014677aa`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101467a59`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101469179`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014677aa`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101467a59`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101469179`
- `sqldk!SystemThread_TlsIndex` at `0x1014674d2`
- `sqldk!SystemThread_TlsIndex` at `0x1014677eb`
- `sqldk!SystemThread_TlsIndex` at `0x101467863`
- `sqldk!SystemThread_TlsIndex` at `0x101467c40`
- `sqldk!SystemThread_TlsIndex` at `0x101467f2b`
- `sqldk!SystemThread_TlsIndex` at `0x101468147`
- `sqldk!SystemThread_TlsIndex` at `0x1014694ca`
- `sqldk!SystemThread_TlsIndex` at `0x1014697a6`
- `sqldk!SystemThread_TlsIndex` at `0x101469b86`
- `sqldk!SystemThread_TlsIndex` at `0x10146a5b4`
- `sqldk!SystemThread_TlsOffset` at `0x1014674db`
- `sqldk!SystemThread_TlsOffset` at `0x1014677f4`
- `sqldk!SystemThread_TlsOffset` at `0x10146786c`
- `sqldk!SystemThread_TlsOffset` at `0x101467c49`
- `sqldk!SystemThread_TlsOffset` at `0x101467f34`
- `sqldk!SystemThread_TlsOffset` at `0x101468151`
- `sqldk!SystemThread_TlsOffset` at `0x1014694d3`
- `sqldk!SystemThread_TlsOffset` at `0x1014697af`
- `sqldk!SystemThread_TlsOffset` at `0x101469b8f`
- `sqldk!SystemThread_TlsOffset` at `0x10146a5bd`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101469010`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1014692f4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101469010`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1014692f4`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014677ba`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467b98`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467ba5`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467bb2`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467bd0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467be9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467bf6`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467c00`
- `sqldk!??_V@YAXPEAX@Z` at `0x101468014`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469302`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146930f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146931c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146933d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469354`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469361`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146983d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014698dc`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146994a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469c19`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469d1b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469e1c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469e8a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014677ba`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467b98`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467ba5`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467bb2`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467bd0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467be9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467bf6`
- `sqldk!??_V@YAXPEAX@Z` at `0x101467c00`
- `sqldk!??_V@YAXPEAX@Z` at `0x101468014`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469302`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146930f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146931c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146933d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469354`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469361`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146983d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014698dc`
- `sqldk!??_V@YAXPEAX@Z` at `0x10146994a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101469c19`

## string_xrefs

- `0x1014695a0`: `FIsNonUniqueSID`
- `0x1014695a7`: `GetSidSubAuthority`
- `0x1014671be`: `CREATE`
- `0x1014671fb`: `CREATE`
- `0x101467b3f`: `CREATE`
- `0x101468359`: `CREATE`
- `0x10146a1dd`: `CREATE`
- `0x101467799`: `sql\ntdbms\msql\security\src\secddl.cpp`
- `0x101467a4d`: `sql\ntdbms\msql\security\src\secddl.cpp`
- `0x10146916b`: `sql\ntdbms\msql\security\src\secddl.cpp`
- `0x10146756a`: `CREATE LOGIN FROM WINDOWS`
- `0x10146743d`: `CREATE LOGIN FROM EXTERNAL PROVIDER`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall CStmtCreateLogin::XretExecute(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r13
  unsigned int v8; // r14d
  __int64 v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  CDefaultCollation *v12; // r12
  const wchar_t *v13; // rbx
  __int64 v14; // rcx
  int v15; // edx
  int v16; // esi
  unsigned __int64 v17; // rdi
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v19; // rcx
  __int64 v20; // rbx
  bool v21; // al
  int v22; // ebx
  __int64 v23; // rdi
  int v24; // ecx
  __int64 v25; // rdx
  __int64 v26; // rax
  unsigned int v27; // ecx
  __int64 v28; // rax
  const void *v29; // r15
  unsigned __int64 v30; // rbx
  struct IMemObj *v31; // r13
  unsigned __int8 *v32; // rsi
  int v33; // edi
  unsigned __int8 *v34; // rbx
  unsigned int v35; // esi
  unsigned int v36; // r15d
  __int64 v37; // rax
  __int64 v38; // r9
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rdi
  size_t v42; // rsi
  void *v43; // rax
  __int64 v45; // r15
  __int64 v46; // r9
  __int64 v47; // rax
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rax
  __int64 *v51; // rdi
  __int64 v52; // rsi
  unsigned int v53; // ebx
  unsigned int v54; // eax
  __int64 *v55; // rbx
  __int64 v56; // rdi
  unsigned int v57; // eax
  unsigned int v58; // esi
  bool v59; // di
  __int64 v60; // r13
  const wchar_t *v61; // r12
  unsigned __int64 v62; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  unsigned int v64; // eax
  __int64 v65; // rcx
  __int64 v66; // r8
  int v67; // ecx
  signed __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  int v71; // ecx
  __int64 v72; // rbx
  __int64 v73; // rax
  __m128i v74; // xmm6
  __int64 v75; // rax
  const wchar_t *v76; // rbx
  unsigned int v77; // r10d
  int v78; // ecx
  __int64 v79; // rax
  bool v80; // di
  const wchar_t **v81; // rdx
  int v82; // eax
  bool v83; // al
  __int64 v84; // rbx
  int v85; // eax
  char v86; // si
  __int64 v87; // rax
  __int64 v88; // rdi
  int v89; // r13d
  unsigned int v90; // ebx
  const wchar_t *v91; // rax
  __int64 v92; // rcx
  unsigned int v93; // ebx
  _WORD *v94; // rdi
  const struct CSECCertParams::_SECCertParams near *const *v95; // rdx
  unsigned int v96; // eax
  unsigned int v97; // edx
  __int64 v98; // r9
  unsigned int *v99; // rbx
  int v100; // esi
  unsigned int v101; // ebx
  __int64 v102; // r8
  __int64 v103; // rax
  _WORD *v104; // rbx
  int v105; // edi
  unsigned __int8 *v106; // rcx
  int v107; // eax
  unsigned int v108; // r12d
  unsigned __int64 v109; // rbx
  struct __crt_locale_pointers *v110; // rax
  __int64 v111; // rax
  unsigned __int64 v112; // rbx
  __int64 v113; // rdi
  struct __crt_locale_pointers *v114; // rax
  __int64 v115; // rax
  const wchar_t *v116; // rbx
  unsigned int v117; // eax
  __int64 v118; // r9
  struct __crt_locale_pointers *v119; // rax
  __int64 v120; // rax
  struct CLangInfo *langinfo; // rax
  unsigned int v122; // eax
  __int64 v123; // r8
  int v124; // ecx
  signed __int64 v125; // rdx
  __int64 v126; // rax
  __int64 v127; // rax
  const void *v128; // rbx
  __int64 v129; // r15
  unsigned __int8 v130; // cl
  __int64 v131; // rax
  unsigned __int16 *v132; // rsi
  __int64 v133; // rax
  unsigned int v134; // r13d
  __int64 v135; // rax
  bool v136; // di
  int v137; // ebx
  bool v138; // r12
  __int16 v139; // r8
  __int64 v140; // rax
  char v141; // r15
  const wchar_t *v142; // rdi
  unsigned __int64 v143; // rcx
  unsigned __int64 v144; // rbx
  __int64 v145; // rax
  char v146; // bl
  const wchar_t *v147; // rsi
  unsigned __int64 v148; // rcx
  unsigned __int64 v149; // rdi
  int v150; // r9d
  int v151; // ecx
  __int64 v152; // rax
  int v153; // esi
  struct IPwdPolicyManager *PwdPolicyManager; // rsi
  unsigned __int8 *v155; // rax
  struct IPwdPolicyManager *v156; // rbx
  struct IPwdPolicyManager *v157; // rcx
  int v158; // r8d
  unsigned int v159; // eax
  unsigned int v160; // ebx
  const wchar_t *v161; // rbx
  _DWORD *v162; // r15
  unsigned int v163; // r10d
  int v164; // ecx
  __int64 v165; // rax
  unsigned int v166; // esi
  bool v167; // di
  PDWORD SidSubAuthority; // rbx
  signed int LastError; // eax
  unsigned int v170; // ecx
  int v171; // eax
  bool v172; // al
  unsigned int v173; // eax
  __int64 v174; // r8
  int v175; // ecx
  signed __int64 v176; // rdx
  __int64 v177; // rax
  __int64 v178; // rdx
  __int64 v179; // rax
  int v180; // ecx
  __int64 v181; // rbx
  unsigned __int16 v182; // ax
  __int64 v183; // rax
  __int64 v184; // rbx
  __int64 v185; // rcx
  unsigned int v186; // ebx
  unsigned int v187; // eax
  __int64 v188; // r8
  int v189; // ecx
  signed __int64 v190; // rdx
  __int64 v191; // rax
  __int64 v192; // rdx
  __int64 v193; // rax
  int v194; // ecx
  __int64 v195; // rbx
  unsigned __int16 v196; // ax
  __int64 v197; // rax
  __int64 v198; // rdi
  __int64 v199; // rcx
  struct CSECGlobalCryptoContext *v200; // rsi
  __int64 v201; // rbx
  __int64 v202; // rax
  __int64 v203; // r8
  __int64 (__fastcall ***v204)(_QWORD); // r15
  const struct _GUID *v205; // rax
  __int64 v206; // rsi
  _QWORD *v207; // rbx
  _QWORD *v208; // rax
  __int64 v209; // rcx
  unsigned int v210; // r12d
  __int64 v211; // rbx
  unsigned int v212; // eax
  __int64 *v213; // rsi
  __int64 v214; // rbx
  __int64 v215; // rdi
  int v216; // eax
  __int64 v217; // rbx
  unsigned __int16 v218; // ax
  __int64 v219; // rax
  unsigned __int16 v220; // ax
  __int64 v221; // rbx
  __int64 v222; // rdx
  __int64 v223; // rcx
  unsigned int v224; // esi
  bool v225; // di
  __int64 v226; // rdx
  __int64 v227; // r12
  __int64 v228; // rbx
  __int64 v229; // r13
  const wchar_t *v230; // r15
  unsigned int v231; // eax
  __int64 v232; // r8
  int v233; // ecx
  signed __int64 v234; // rdx
  __int64 v235; // rax
  const void *v236; // rbx
  __int64 v237; // rax
  int v238; // edi
  __int16 *v239; // rbx
  __int64 v240; // rax
  __int16 v241; // ax
  __int64 v242; // rax
  int v243; // ecx
  const wchar_t *v244; // rbx
  int *v245; // r12
  unsigned int v246; // r10d
  int v247; // ecx
  __int64 v248; // rax
  bool v249; // di
  int *v250; // rdx
  int v251; // eax
  bool v252; // al
  int v253; // [rsp+20h] [rbp-E0h]
  char v254[8]; // [rsp+20h] [rbp-E0h]
  char v255[8]; // [rsp+20h] [rbp-E0h]
  char v256[8]; // [rsp+20h] [rbp-E0h]
  int v257; // [rsp+20h] [rbp-E0h]
  char v258[8]; // [rsp+20h] [rbp-E0h]
  char v259[8]; // [rsp+20h] [rbp-E0h]
  char v260[8]; // [rsp+20h] [rbp-E0h]
  char v261[8]; // [rsp+20h] [rbp-E0h]
  char v262[8]; // [rsp+20h] [rbp-E0h]
  int v263; // [rsp+28h] [rbp-D8h]
  wchar_t *v264; // [rsp+28h] [rbp-D8h]
  wchar_t *v265; // [rsp+28h] [rbp-D8h]
  int v266; // [rsp+28h] [rbp-D8h]
  wchar_t *v267; // [rsp+28h] [rbp-D8h]
  wchar_t *v268; // [rsp+28h] [rbp-D8h]
  wchar_t *v269; // [rsp+28h] [rbp-D8h]
  wchar_t *v270; // [rsp+28h] [rbp-D8h]
  unsigned __int8 **v271; // [rsp+30h] [rbp-D0h]
  int v272; // [rsp+30h] [rbp-D0h]
  int v273; // [rsp+38h] [rbp-C8h]
  int v274; // [rsp+40h] [rbp-C0h]
  int v275; // [rsp+48h] [rbp-B8h]
  char v276; // [rsp+80h] [rbp-80h] BYREF
  char v277[7]; // [rsp+81h] [rbp-7Fh] BYREF
  __int64 v278; // [rsp+88h] [rbp-78h]
  unsigned int v279; // [rsp+90h] [rbp-70h]
  int v280; // [rsp+94h] [rbp-6Ch]
  int v281; // [rsp+98h] [rbp-68h]
  bool v282; // [rsp+9Ch] [rbp-64h] BYREF
  bool v283; // [rsp+9Dh] [rbp-63h] BYREF
  bool v284; // [rsp+9Eh] [rbp-62h] BYREF
  bool v285; // [rsp+9Fh] [rbp-61h] BYREF
  char v286; // [rsp+A0h] [rbp-60h] BYREF
  char v287; // [rsp+A1h] [rbp-5Fh]
  unsigned __int16 v288[2]; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 *v289; // [rsp+A8h] [rbp-58h]
  unsigned int MasterDbId; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v291[2]; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned __int16 v292[2]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int Size[3]; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v294; // [rsp+C8h] [rbp-38h] BYREF
  int v295; // [rsp+CCh] [rbp-34h]
  struct IPwdPolicyManager *v296; // [rsp+D0h] [rbp-30h]
  unsigned int v297; // [rsp+D8h] [rbp-28h] BYREF
  int v298; // [rsp+DCh] [rbp-24h]
  unsigned int v299[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int8 *v300; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v301; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v302; // [rsp+100h] [rbp+0h] BYREF
  int v303; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v304; // [rsp+114h] [rbp+14h] BYREF
  unsigned int *v305; // [rsp+118h] [rbp+18h] BYREF
  RPC_WSTR StringUuid; // [rsp+120h] [rbp+20h] BYREF
  int v307; // [rsp+128h] [rbp+28h] BYREF
  int v308; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v309; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v310; // [rsp+134h] [rbp+34h]
  char v311; // [rsp+138h] [rbp+38h]
  unsigned __int8 v312; // [rsp+139h] [rbp+39h]
  char v313; // [rsp+13Ah] [rbp+3Ah]
  int v314; // [rsp+13Ch] [rbp+3Ch]
  __int64 v315; // [rsp+140h] [rbp+40h]
  __int64 v316; // [rsp+148h] [rbp+48h] BYREF
  __int64 v317; // [rsp+150h] [rbp+50h] BYREF
  __int64 v318; // [rsp+158h] [rbp+58h] BYREF
  __int64 v319; // [rsp+160h] [rbp+60h] BYREF
  __int64 v320; // [rsp+168h] [rbp+68h]
  __int64 v321; // [rsp+170h] [rbp+70h] BYREF
  __int64 v322; // [rsp+178h] [rbp+78h]
  __int64 v323; // [rsp+180h] [rbp+80h] BYREF
  int v324; // [rsp+188h] [rbp+88h]
  __int64 v325; // [rsp+190h] [rbp+90h] BYREF
  int v326; // [rsp+198h] [rbp+98h]
  unsigned __int8 *v327[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v328; // [rsp+1B0h] [rbp+B0h]
  __int128 v329; // [rsp+1C0h] [rbp+C0h]
  __int128 v330; // [rsp+1D0h] [rbp+D0h]
  __int128 v331; // [rsp+1E0h] [rbp+E0h]
  void *v332; // [rsp+1F0h] [rbp+F0h]
  __int64 v333; // [rsp+200h] [rbp+100h]
  __int64 v334; // [rsp+208h] [rbp+108h]
  __int64 v335; // [rsp+210h] [rbp+110h] BYREF
  __int128 v336; // [rsp+220h] [rbp+120h] BYREF
  __int128 v337; // [rsp+230h] [rbp+130h]
  __int128 v338; // [rsp+240h] [rbp+140h]
  __int128 v339; // [rsp+250h] [rbp+150h]
  __int128 v340; // [rsp+260h] [rbp+160h]
  void *v341; // [rsp+270h] [rbp+170h]
  HCERTSTORE hCertStore[2]; // [rsp+280h] [rbp+180h] BYREF
  int v343; // [rsp+290h] [rbp+190h]
  __int64 v344; // [rsp+298h] [rbp+198h]
  PCCERT_CONTEXT pCertContext; // [rsp+2A0h] [rbp+1A0h]
  char v346; // [rsp+2A8h] [rbp+1A8h]
  void **v347; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v348[2]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int16 v349; // [rsp+2BAh] [rbp+1BAh]
  __int128 v350; // [rsp+2C0h] [rbp+1C0h]
  int v351; // [rsp+2D0h] [rbp+1D0h]
  __int128 v352; // [rsp+2D8h] [rbp+1D8h]
  __int128 v353; // [rsp+2E8h] [rbp+1E8h]
  void **v354; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v355[2]; // [rsp+308h] [rbp+208h] BYREF
  __int16 v356; // [rsp+30Ah] [rbp+20Ah]
  __int64 v357; // [rsp+310h] [rbp+210h]
  __int64 v358; // [rsp+318h] [rbp+218h]
  int v359; // [rsp+320h] [rbp+220h]
  __int128 v360; // [rsp+328h] [rbp+228h]
  __int128 v361; // [rsp+338h] [rbp+238h]
  _QWORD v362[3]; // [rsp+350h] [rbp+250h] BYREF
  int v363; // [rsp+368h] [rbp+268h]
  const wchar_t *v364; // [rsp+370h] [rbp+270h] BYREF
  unsigned int v365; // [rsp+378h] [rbp+278h]
  const wchar_t *v366; // [rsp+380h] [rbp+280h] BYREF
  int v367; // [rsp+388h] [rbp+288h]
  const wchar_t *v368; // [rsp+390h] [rbp+290h] BYREF
  int v369; // [rsp+398h] [rbp+298h]
  const wchar_t *v370; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v371; // [rsp+3A8h] [rbp+2A8h]
  const wchar_t *v372; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned int v373; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v374; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v375; // [rsp+3C8h] [rbp+2C8h]
  _WORD *v376; // [rsp+3D0h] [rbp+2D0h] BYREF
  int v377; // [rsp+3D8h] [rbp+2D8h]
  const wchar_t *v378; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned int v379; // [rsp+3E8h] [rbp+2E8h]
  __int64 v380; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned int v381; // [rsp+3F8h] [rbp+2F8h]
  void **v382; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v383[2]; // [rsp+408h] [rbp+308h] BYREF
  __int16 v384; // [rsp+40Ah] [rbp+30Ah]
  __int128 v385; // [rsp+410h] [rbp+310h]
  int v386; // [rsp+420h] [rbp+320h]
  __int128 v387; // [rsp+428h] [rbp+328h]
  __int128 v388; // [rsp+438h] [rbp+338h]
  __int64 v389; // [rsp+450h] [rbp+350h]
  GUID v390; // [rsp+460h] [rbp+360h] BYREF
  __m128i v391; // [rsp+470h] [rbp+370h] BYREF
  UUID v392; // [rsp+480h] [rbp+380h] BYREF
  GUID v393; // [rsp+490h] [rbp+390h] BYREF
  __int128 v394; // [rsp+4A0h] [rbp+3A0h] BYREF
  GUID v395; // [rsp+4B0h] [rbp+3B0h] BYREF
  GUID v396; // [rsp+4C0h] [rbp+3C0h] BYREF
  GUID v397; // [rsp+4D0h] [rbp+3D0h] BYREF
  GUID v398; // [rsp+4E0h] [rbp+3E0h] BYREF
  GUID v399; // [rsp+4F0h] [rbp+3F0h] BYREF
  GUID v400; // [rsp+500h] [rbp+400h] BYREF
  GUID v401; // [rsp+510h] [rbp+410h] BYREF
  GUID v402; // [rsp+520h] [rbp+420h] BYREF
  __int64 v403; // [rsp+530h] [rbp+430h]
  __int64 v404; // [rsp+538h] [rbp+438h]
  struct IPwdPolicyManager *v405; // [rsp+540h] [rbp+440h]
  _DWORD v406[6]; // [rsp+548h] [rbp+448h] BYREF
  void *v407; // [rsp+560h] [rbp+460h]
  _DWORD v408[6]; // [rsp+570h] [rbp+470h] BYREF
  void *v409; // [rsp+588h] [rbp+488h]
  _BYTE v410[24]; // [rsp+598h] [rbp+498h] BYREF
  __int64 v411; // [rsp+5B0h] [rbp+4B0h]
  _DWORD v412[6]; // [rsp+5C0h] [rbp+4C0h] BYREF
  void *v413; // [rsp+5D8h] [rbp+4D8h]
  _DWORD v414[6]; // [rsp+5E8h] [rbp+4E8h] BYREF
  void *v415; // [rsp+600h] [rbp+500h]
  _BYTE v416[24]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v417; // [rsp+628h] [rbp+528h]
  _DWORD v418[6]; // [rsp+638h] [rbp+538h] BYREF
  void *v419; // [rsp+650h] [rbp+550h]
  _BYTE v420[24]; // [rsp+660h] [rbp+560h] BYREF
  __int64 v421; // [rsp+678h] [rbp+578h]
  _DWORD v422[6]; // [rsp+688h] [rbp+588h] BYREF
  void *v423; // [rsp+6A0h] [rbp+5A0h]
  _BYTE v424[24]; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v425; // [rsp+6C8h] [rbp+5C8h]
  _BYTE v426[24]; // [rsp+6D8h] [rbp+5D8h] BYREF
  __int64 v427; // [rsp+6F0h] [rbp+5F0h]
  _BYTE v428[24]; // [rsp+700h] [rbp+600h] BYREF
  __int64 v429; // [rsp+718h] [rbp+618h]
  _DWORD v430[6]; // [rsp+728h] [rbp+628h] BYREF
  void *v431; // [rsp+740h] [rbp+640h]
  _BYTE v432[24]; // [rsp+750h] [rbp+650h] BYREF
  __int64 v433; // [rsp+768h] [rbp+668h]
  char v434[8]; // [rsp+780h] [rbp+680h] BYREF
  int v435; // [rsp+788h] [rbp+688h]
  int v436; // [rsp+790h] [rbp+690h]
  char **v437; // [rsp+798h] [rbp+698h]
  char *v438; // [rsp+7A0h] [rbp+6A0h]
  __int64 v439; // [rsp+7A8h] [rbp+6A8h]
  char *v440; // [rsp+7B0h] [rbp+6B0h] BYREF
  int v441; // [rsp+7B8h] [rbp+6B8h]
  int v442; // [rsp+7BCh] [rbp+6BCh]
  const wchar_t *v443; // [rsp+7C0h] [rbp+6C0h]
  __int64 v444; // [rsp+7C8h] [rbp+6C8h]
  const wchar_t *v445; // [rsp+7D0h] [rbp+6D0h]
  int v446; // [rsp+7D8h] [rbp+6D8h]
  int v447; // [rsp+7DCh] [rbp+6DCh]
  char v448; // [rsp+7E0h] [rbp+6E0h] BYREF
  __int64 v449; // [rsp+9D0h] [rbp+8D0h]
  __int64 v450; // [rsp+9D8h] [rbp+8D8h]
  char v451; // [rsp+9E0h] [rbp+8E0h] BYREF
  char v452[8]; // [rsp+9F0h] [rbp+8F0h] BYREF
  int v453; // [rsp+9F8h] [rbp+8F8h]
  int v454; // [rsp+A00h] [rbp+900h]
  char **v455; // [rsp+A08h] [rbp+908h]
  char *v456; // [rsp+A10h] [rbp+910h]
  __int64 v457; // [rsp+A18h] [rbp+918h]
  char *v458; // [rsp+A20h] [rbp+920h] BYREF
  int v459; // [rsp+A28h] [rbp+928h]
  int v460; // [rsp+A2Ch] [rbp+92Ch]
  const wchar_t *v461; // [rsp+A30h] [rbp+930h]
  __int64 v462; // [rsp+A38h] [rbp+938h]
  const wchar_t *v463; // [rsp+A40h] [rbp+940h]
  int v464; // [rsp+A48h] [rbp+948h]
  int v465; // [rsp+A4Ch] [rbp+94Ch]
  char v466; // [rsp+A50h] [rbp+950h] BYREF
  __int64 v467; // [rsp+C40h] [rbp+B40h]
  __int64 v468; // [rsp+C48h] [rbp+B48h]
  char v469; // [rsp+C50h] [rbp+B50h] BYREF
  char v470[8]; // [rsp+C60h] [rbp+B60h] BYREF
  int v471; // [rsp+C68h] [rbp+B68h]
  int v472; // [rsp+C70h] [rbp+B70h]
  char **v473; // [rsp+C78h] [rbp+B78h]
  char *v474; // [rsp+C80h] [rbp+B80h]
  __int64 v475; // [rsp+C88h] [rbp+B88h]
  char *v476; // [rsp+C90h] [rbp+B90h] BYREF
  int v477; // [rsp+C98h] [rbp+B98h]
  int v478; // [rsp+C9Ch] [rbp+B9Ch]
  const wchar_t *v479; // [rsp+CA0h] [rbp+BA0h]
  __int64 v480; // [rsp+CA8h] [rbp+BA8h]
  const wchar_t *v481; // [rsp+CB0h] [rbp+BB0h]
  int v482; // [rsp+CB8h] [rbp+BB8h]
  int v483; // [rsp+CBCh] [rbp+BBCh]
  char v484; // [rsp+CC0h] [rbp+BC0h] BYREF
  __int64 v485; // [rsp+EB0h] [rbp+DB0h]
  __int64 v486; // [rsp+EB8h] [rbp+DB8h]
  char v487; // [rsp+EC0h] [rbp+DC0h] BYREF
  char v488[8]; // [rsp+ED0h] [rbp+DD0h] BYREF
  int v489; // [rsp+ED8h] [rbp+DD8h]
  int v490; // [rsp+EE0h] [rbp+DE0h]
  char **v491; // [rsp+EE8h] [rbp+DE8h]
  char *v492; // [rsp+EF0h] [rbp+DF0h]
  __int64 v493; // [rsp+EF8h] [rbp+DF8h]
  char *v494; // [rsp+F00h] [rbp+E00h] BYREF
  int v495; // [rsp+F08h] [rbp+E08h]
  int v496; // [rsp+F0Ch] [rbp+E0Ch]
  const wchar_t *v497; // [rsp+F10h] [rbp+E10h]
  __int64 v498; // [rsp+F18h] [rbp+E18h]
  const wchar_t *v499; // [rsp+F20h] [rbp+E20h]
  int v500; // [rsp+F28h] [rbp+E28h]
  int v501; // [rsp+F2Ch] [rbp+E2Ch]
  char v502; // [rsp+F30h] [rbp+E30h] BYREF
  __int64 v503; // [rsp+1120h] [rbp+1020h]
  __int64 v504; // [rsp+1128h] [rbp+1028h]
  char v505; // [rsp+1130h] [rbp+1030h] BYREF
  UUID Uuid; // [rsp+1140h] [rbp+1040h] BYREF
  GUID pguid; // [rsp+1150h] [rbp+1050h] BYREF
  GUID v508; // [rsp+1160h] [rbp+1060h] BYREF
  char v509[16]; // [rsp+1170h] [rbp+1070h] BYREF
  int v510; // [rsp+1180h] [rbp+1080h]
  char v511[16]; // [rsp+1188h] [rbp+1088h] BYREF
  char v512[24]; // [rsp+1198h] [rbp+1098h] BYREF
  _BYTE v513[6992]; // [rsp+11B0h] [rbp+10B0h] BYREF
  GUID v514; // [rsp+2D00h] [rbp+2C00h] BYREF
  unsigned __int8 v515[16]; // [rsp+2D10h] [rbp+2C10h] BYREF
  __int128 v516; // [rsp+2D20h] [rbp+2C20h]
  __int128 v517; // [rsp+2D30h] [rbp+2C30h]
  __int128 v518; // [rsp+2D40h] [rbp+2C40h]
  __int128 v519; // [rsp+2D50h] [rbp+2C50h]
  int v520; // [rsp+2D60h] [rbp+2C60h]
  char v521; // [rsp+2D64h] [rbp+2C64h]
  unsigned __int8 pSid[96]; // [rsp+2D70h] [rbp+2C70h] BYREF
  wchar_t v523[136]; // [rsp+2DD0h] [rbp+2CD0h] BYREF
  unsigned __int8 v524[96]; // [rsp+2EE0h] [rbp+2DE0h] BYREF
  _BYTE v525[96]; // [rsp+2F40h] [rbp+2E40h] BYREF
  wchar_t v526[40]; // [rsp+2FA0h] [rbp+2EA0h] BYREF
  _BYTE v527[96]; // [rsp+2FF0h] [rbp+2EF0h] BYREF
  wchar_t v528[136]; // [rsp+3050h] [rbp+2F50h] BYREF
  _WORD v529[3]; // [rsp+3160h] [rbp+3060h] BYREF
  _BYTE v530[506]; // [rsp+3166h] [rbp+3066h] BYREF
  wchar_t v531[136]; // [rsp+3360h] [rbp+3260h] BYREF
  wchar_t v532[136]; // [rsp+3470h] [rbp+3370h] BYREF
  unsigned __int8 Src[512]; // [rsp+3580h] [rbp+3480h] BYREF

  v389 = -2;
  v334 = a4;
  v322 = a3;
  v320 = a2;
  v278 = a1;
  v7 = *(_QWORD *)(a2 + 120);
  *(_QWORD *)&Size[1] = *(_QWORD *)(a4 + 120);
  MasterDbId = GetMasterDbId();
  v289 = *(__int64 **)(a3 + 56);
  v8 = 0;
  v9 = 0;
  pguid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  Uuid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  CoCreateGuid(&pguid);
  if ( ((*(_BYTE *)(*(_QWORD *)(a2 + 72) + 270LL) & 4) != 0
     || (*(_DWORD *)(GetXdbServerGlobals(v11, v10) + 11976) || (unsigned int)IsVDWFrontendInstance())
     && (*(_BYTE *)(*(_QWORD *)(a2 + 72) + 270LL) & 2) == 0)
    && (qword_102F21DB4 & 4) != 0 )
  {
    v435 = 196608;
    v436 = 0;
    v437 = &v440;
    v438 = &v448;
    v449 = 0;
    v439 = 0;
    v450 = 0;
    v440 = &v451;
    v441 = 16;
    v442 = 2;
    v443 = L"CREATE";
    v444 = 12;
    v445 = L"START";
    v446 = 10;
    v447 = 1;
    XeCloudPkg::azuresqldb_login_ddl::Publish((XeCloudPkg::azuresqldb_login_ddl *)v434);
  }
  v12 = (CDefaultCollation *)CDefaultCollation::PDCServer(v11);
  v13 = 0;
  v14 = *(_QWORD *)(a1 + 2328);
  if ( v14 )
  {
    v13 = *(const wchar_t **)(v14 + 8);
    v15 = *(_DWORD *)(v14 + 16);
  }
  else
  {
    v15 = 0;
  }
  v16 = 0;
  v298 = 0;
  v280 = 0;
  *(_DWORD *)v288 = 0;
  v281 = 0;
  v279 = 0;
  v17 = (unsigned __int64)v15 >> 1;
  if ( CompareStringWEnglishNoCase(1u, 0, v13, v17, CStmtCreateLogin::SqlLogin, 3) == 2 )
  {
    v16 = 1;
    v298 = 1;
  }
  else if ( CompareStringWEnglishNoCase(1u, 0, v13, v17, CStmtCreateLogin::NtLogin, 2) == 2 )
  {
    *(_DWORD *)v288 = 1;
  }
  else if ( CompareStringWEnglishNoCase(1u, 0, v13, v17, CStmtCreateLogin::CertLogin, 11) == 2 )
  {
    v280 = 1;
  }
  else if ( CompareStringWEnglishNoCase(1u, 0, v13, v17, CStmtCreateLogin::AKeyLogin, 14) == 2 )
  {
    v281 = 1;
  }
  else if ( CompareStringWEnglishNoCase(1u, 0, v13, v17, CStmtCreateLogin::ExternalLogin, 8) == 2 )
  {
    if ( *(_DWORD *)(qword_102ECFB00 + 14504) || IsBoxAADEnabled(0) )
    {
      if ( !*(_DWORD *)(GetXdbServerGlobals(v19, ThreadLocalStoragePointer) + 11976)
        && !(unsigned int)IsVDWFrontendInstance()
        && !IsBoxAADEnabled(0)
        && !*(_DWORD *)(qword_102ECFB00 + 14504) )
      {
        goto LABEL_38;
      }
      v279 = 1;
    }
    else
    {
      ex_raise(375, 25, 16, 1, 70, L"CREATE LOGIN FROM EXTERNAL PROVIDER");
    }
  }
  if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
  {
    if ( byte_102EDCA50 )
    {
      if ( byte_102EF429C )
      {
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v19 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 72LL);
        v20 = *(_QWORD *)(v19 + 96);
        if ( v20 )
        {
          LOBYTE(ThreadLocalStoragePointer) = 2;
          v21 = CPhysicalConnection::GetFeatureExtension(*(_QWORD *)(v19 + 96), ThreadLocalStoragePointer)
             && *(_DWORD *)(v20 + 988) != 2;
          if ( v16 && v21 )
            ex_raise(374, 57, 16, 1);
        }
      }
    }
  }
LABEL_38:
  if ( *(_DWORD *)(GetXdbServerGlobals(v19, ThreadLocalStoragePointer) + 11976) || (unsigned int)IsVDWFrontendInstance() )
  {
    v22 = *(_DWORD *)v288;
    if ( (*(_BYTE *)(*(_QWORD *)(v320 + 72) + 270LL) & 2) == 0 && *(_DWORD *)v288 )
      ex_raise(419, 6, 16, 5, 50, L"CREATE LOGIN FROM WINDOWS");
  }
  else
  {
    v22 = *(_DWORD *)v288;
  }
  v23 = v278;
  v305 = (unsigned int *)(v278 + 2216);
  v24 = *(_DWORD *)(v278 + 2216);
  *(_QWORD *)&v302 = *(_QWORD *)(v278 + 2208);
  DWORD2(v302) = v24;
  if ( (*(_BYTE *)(*(_QWORD *)(v320 + 72) + 270LL) & 4) != 0 )
  {
    if ( !v279 )
    {
      v347 = &CAutoClearXVariant::`vftable';
      v352 = CTypeInfo::tiWStringNotNull;
      v353 = xmmword_102F39950;
      v349 = 0;
      v348[0] = 3;
      LOBYTE(v352) = _mm_cvtsi128_si32(CTypeInfo::tiWStringNotNull);
      v348[1] = v352;
      v350 = 0;
      v351 = 0;
      *(_QWORD *)&v350 = *(_QWORD *)(v278 + 2208);
      *((_QWORD *)&v350 + 1) = *(unsigned int *)(v278 + 2216);
      v348[0] = 0;
      v25 = 0;
      v26 = *(_QWORD *)(v278 + 2256);
      if ( v26 )
      {
        v25 = *(_QWORD *)(v26 + 8);
        v27 = *(_DWORD *)(v26 + 16);
      }
      else
      {
        v27 = 0;
      }
      v354 = &CAutoClearXVariant::`vftable';
      v360 = CTypeInfo::tiWStringNotNull;
      v361 = xmmword_102F39950;
      v356 = 0;
      LOBYTE(v360) = _mm_cvtsi128_si32(CTypeInfo::tiWStringNotNull);
      v355[1] = v360;
      v359 = 0;
      v357 = v25;
      v358 = v27;
      v355[0] = 0;
      v382 = &CAutoClearXVariant::`vftable';
      v387 = CTypeInfo::tiI4NotNull;
      v388 = xmmword_102F21D40;
      v384 = 0;
      LOBYTE(v387) = _mm_cvtsi128_si32(CTypeInfo::tiI4NotNull);
      v383[1] = v387;
      v385 = 0;
      v386 = 0;
      LODWORD(v385) = 0;
      v383[0] = 0;
      v300 = 0;
      v297 = 0;
      memset_0(Src, 0, sizeof(Src));
      Size[0] = 512;
      v28 = *(_QWORD *)(v278 + 2304);
      if ( v28 )
      {
        v29 = *(const void **)(v28 + 8);
        v30 = *(unsigned int *)(v28 + 16);
        if ( (unsigned int)v30 > 0x55 )
          ex_raise(154, 19, 16, 1);
        v31 = *(struct IMemObj **)&Size[1];
        v32 = (unsigned __int8 *)operator new[](
                                   v30,
                                   *(struct IMemObj **)&Size[1],
                                   "sql\\ntdbms\\msql\\security\\src\\secddl.cpp",
                                   6273,
                                   3u);
        if ( v32 )
          operator delete[](0);
        v300 = v32;
        memcpy_s(v32, v30, v29, v30);
        v297 = v30;
      }
      else
      {
        v31 = *(struct IMemObj **)&Size[1];
      }
      v299[0] = 0;
      CGatewaySqlLoginsTable::CreateLogin(
        *(const struct CCompExecCtxtBasic **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset),
        0,
        (struct CXVariant *const)v348,
        (struct CXVariant *const)v355,
        0,
        (struct CXVariant *const)v383,
        &v300,
        &v297,
        Src,
        Size,
        v299);
      v33 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                          + SystemThread_TlsIndex)
                                                        + SystemThread_TlsOffset)
                                            + 80LL)
                                + 8LL);
      v34 = v300;
      v35 = v297;
      v36 = v299[0];
      if ( byte_102EDCB8A )
      {
        v253 = v33;
        v37 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64))(*v289 + 328))(v289, &v302, 1);
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 256LL))(v37);
        LOBYTE(v253) = 1;
        LOBYTE(v38) = 1;
        v39 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int8 *, _QWORD, __int64, int, int))(*v289 + 344))(
                v289,
                v34,
                v35,
                v38,
                v253,
                v33);
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 256LL))(v39);
        v40 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*v289 + 336))(v289, v36, 1);
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 256LL))(v40);
      }
      v390 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v41 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int8 *, _QWORD, _DWORD, unsigned int, int, GUID *))(*v289 + 360))(
              v289,
              &v302,
              v34,
              v35,
              0,
              v36,
              v33,
              &v390);
      if ( !v41 )
        utassert_fail(1u, "imLgn != nullptr", "secddl.cpp", 6376, 0);
      v364 = L"master";
      v365 = dword_102F1BB98;
      (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v41 + 288LL))(v41, &v364);
      v366 = L"us_english";
      v367 = 20;
      (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v41 + 296LL))(v41, &v366);
      v336 = 0;
      v337 = 0;
      v338 = 0;
      v339 = 0;
      v340 = 0;
      v341 = 0;
      utgettime((struct SQLDATEBASE *)&v321, 1, 0);
      DWORD1(v336) = Size[0];
      v42 = Size[0];
      v43 = operator new[](Size[0], v31, "sql\\ntdbms\\msql\\security\\src\\secddl.cpp", 6388, 3u);
      *((_QWORD *)&v336 + 1) = v43;
      if ( v42 )
      {
        if ( v43 )
        {
          memmove(v43, Src, v42);
        }
        else
        {
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
      }
      *(_QWORD *)&v337 = v321;
      LOBYTE(v336) = v336 & 0xFC;
      (*(void (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v41 + 312LL))(v41, 1, &v336);
      if ( (qword_102F21DB4 & 4) != 0 )
      {
        v453 = 196608;
        v454 = 0;
        v455 = &v458;
        v456 = &v466;
        v467 = 0;
        v457 = 0;
        v468 = 0;
        v458 = &v469;
        v459 = 16;
        v460 = 2;
        v461 = L"CREATE";
        v462 = 12;
        v463 = L"FINISH";
        v464 = 12;
        v465 = 1;
        XeCloudPkg::azuresqldb_login_ddl::Publish((XeCloudPkg::azuresqldb_login_ddl *)v452);
      }
      *(_BYTE *)(v322 + 176) |= 0x10u;
      operator delete[](*((void **)&v336 + 1));
      operator delete[](*((void **)&v340 + 1));
      operator delete[](v341);
      if ( HIDWORD(v338) )
      {
        do
          operator delete[](*(void **)(*((_QWORD *)&v339 + 1) + 8LL * v8++));
        while ( v8 < HIDWORD(v338) );
      }
      operator delete[]((void *)v339);
      operator delete[](*((void **)&v339 + 1));
      operator delete[](v34);
      CAutoClearXVariant::~CAutoClearXVariant(&v382);
      CAutoClearXVariant::~CAutoClearXVariant(&v354);
      CAutoClearXVariant::~CAutoClearXVariant(&v347);
      return 0;
    }
    v294 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                         + SystemThread_TlsIndex)
                                                       + SystemThread_TlsOffset)
                                           + 80LL)
                               + 8LL);
    v45 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*v289 + 56))(
            v289,
            v294,
            0,
            0,
            0,
            0);
    v368 = L"firewall_rules";
    v369 = 28;
    LOBYTE(v46) = 1;
    v47 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v45 + 216LL))(v45, 4, 0, v46);
    LOBYTE(v48) = 1;
    if ( !(*(__int64 (__fastcall **)(__int64, const wchar_t **, __int64, _QWORD, _DWORD, _DWORD, _BYTE))(*(_QWORD *)v47 + 32LL))(
            v47,
            &v368,
            v48,
            0,
            0,
            0,
            0) )
      ex_raise(50, 1, 16, 15);
    v370 = L"loginmanager";
    v371 = 24;
    LOBYTE(v49) = 1;
    v50 = (*(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD, __int64))(*(_QWORD *)v45 + 224LL))(
            v45,
            &v370,
            0,
            v49);
    v51 = *(__int64 **)(*(_QWORD *)(v320 + 120) + 264LL);
    v52 = *v51;
    v53 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
    v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD, _QWORD))(v52 + 480))(v51, v54, v53)
      && !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v320 + 120) + 264LL) + 152LL))(*(_QWORD *)(*(_QWORD *)(v320 + 120) + 264LL)) )
    {
      v55 = *(__int64 **)(*(_QWORD *)(v320 + 120) + 264LL);
      v56 = *v55;
      v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD))(v56 + 496))(v55, v57) )
        ex_raise(152, 47, 16, 105);
    }
    v58 = 85;
    MasterDbId = 85;
    v59 = 0;
    v276 = 0;
    v277[0] = 0;
    v60 = *(_QWORD *)(v278 + 2304);
    v317 = *(_QWORD *)(v278 + 2256);
    v321 = *(_QWORD *)(v278 + 2416);
    v319 = *(_QWORD *)(v278 + 2312);
    v318 = *(_QWORD *)(v278 + 2320);
    v316 = *(_QWORD *)(v278 + 2424);
    v61 = 0;
    v62 = (unsigned __int64)*(unsigned int *)(v278 + 2216) >> 1;
    DefaultLocale = GetDefaultLocale();
    StringCchPrintf_lW(v528, 0x81u, L"%.*s", DefaultLocale, v62, *(_QWORD *)(v278 + 2208));
    v64 = *v305;
    v65 = v278;
    v66 = *(_QWORD *)(v278 + 2208);
    if ( v66 && v64 )
    {
      v67 = 0;
      v68 = (unsigned __int64)v64 >> 1;
      if ( v68 )
      {
        v69 = 0;
        while ( *(_WORD *)(v66 + 2 * v69) != 92 )
        {
          ++v67;
          if ( ++v69 >= v68 )
            goto LABEL_89;
        }
        if ( v67 >= 0 )
          ex_raise(150, 6, 16, 5, v528);
      }
LABEL_89:
      v65 = v278;
    }
    if ( !v60 && !v321 && !v319 && !v318 && !v317 )
    {
      if ( !v316 )
        goto LABEL_101;
      if ( byte_102EDCA59 )
      {
        v70 = *(_QWORD *)(v65 + 2424);
        if ( v70 )
        {
          v61 = *(const wchar_t **)(v70 + 8);
          v71 = *(_DWORD *)(v70 + 16);
        }
        else
        {
          v71 = 0;
        }
        LODWORD(v301) = v71;
LABEL_101:
        if ( byte_102EDCA55 )
        {
          v72 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                    + SystemThread_TlsIndex)
                                                  + SystemThread_TlsOffset)
                                      + 120LL)
                          + 264LL);
          v73 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v72 + 568LL))(v72, v45, 1, 0);
          if ( v73 )
          {
            v74 = *(__m128i *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v73 + 608LL))(v73, v511);
            Uuid = (UUID)v74;
          }
          else
          {
            v75 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD))(*(_QWORD *)v72 + 576LL))(
                    v72,
                    v289,
                    1,
                    0);
            if ( v75 )
            {
              v74 = *(__m128i *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v75 + 80LL))(v75, v512);
              Uuid = (UUID)v74;
            }
            else
            {
              v74 = (__m128i)Uuid;
            }
          }
          if ( v74.m128i_i64[0] != *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
            || _mm_srli_si128(v74, 8).m128i_u64[0] != *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
          {
LABEL_111:
            v76 = *(const wchar_t **)(v278 + 2208);
            v77 = *(_DWORD *)(v278 + 2216);
            if ( !v76 )
              goto LABEL_117;
            if ( !v77 )
              goto LABEL_117;
            v78 = 0;
            if ( !((unsigned __int64)v77 >> 1) )
              goto LABEL_117;
            v79 = 0;
            while ( v76[v79] != 92 )
            {
              ++v78;
              if ( ++v79 >= (__int64)((unsigned __int64)v77 >> 1) )
                goto LABEL_117;
            }
            if ( v78 >= 0 && v77 - 1 != v78 )
            {
              v80 = v61 != 0;
              if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                     + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + SystemThread_TlsIndex))
                                         + 72LL)
                             + 270LL)
                  & 4) == 0 )
              {
                v291[0] = 85;
                v82 = FGetSidFromNt(v76, v77, v524, v291, 85, 1);
                v59 = v82 != 0;
                if ( v82 )
                  v83 = v277[0];
                else
                  v83 = (unsigned int)FGetSidFromNt(v76, *(unsigned int *)(v278 + 2216), v524, v291, 71, 1) != 0;
                if ( !v59 && !v83 )
                  ex_raise(154, 1, 16, 1, v528);
                v58 = v291[0];
                goto LABEL_135;
              }
            }
            else
            {
LABEL_117:
              v80 = v61 != 0;
              if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
                ex_raise(154, 7, 16, 1, v528);
            }
            v391 = v74;
            v81 = &v301;
            if ( v61 )
              v76 = v61;
            else
              v81 = (const wchar_t **)(v278 + 2216);
            LOBYTE(v263) = v80;
            LookupFederatedPrincipal(v76, v81, v528, 0, &pguid, v263, v524, &MasterDbId, &v276, v277, &v391);
            v58 = MasterDbId;
            v59 = v276;
LABEL_135:
            v392 = Uuid;
            v84 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int8 *, _QWORD, unsigned int, _DWORD, unsigned int, UUID *))(*v289 + 360))(
                    v289,
                    &v302,
                    v524,
                    v58,
                    8 - (unsigned int)v59,
                    0,
                    v294,
                    &v392);
            if ( !v84 )
              ex_raise(150, 25, 16, 8, v528);
            v372 = L"master";
            v373 = dword_102F1BB98;
            (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v84 + 288LL))(v84, &v372);
            v374 = L"us_english";
            v375 = 20;
            (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v84 + 296LL))(v84, &v374);
            if ( (qword_102F21DB4 & 4) != 0 )
            {
              v471 = 196608;
              v472 = 0;
              v473 = &v476;
              v474 = &v484;
              v485 = 0;
              v475 = 0;
              v486 = 0;
              v476 = &v487;
              v477 = 16;
              v478 = 2;
              v479 = L"CREATE";
              v480 = 12;
              v481 = L"FINISH_FEDAUTH_LOGIN";
              v482 = 40;
              v483 = 1;
              XeCloudPkg::azuresqldb_login_ddl::Publish((XeCloudPkg::azuresqldb_login_ddl *)v470);
            }
            *(_BYTE *)(v322 + 176) |= 0x10u;
            return 0;
          }
          StringUuid = 0;
          AzureActiveDirectoryService::GetTenantId(*(_QWORD *)&Size[1], &StringUuid);
          UuidFromStringW(StringUuid, &Uuid);
          operator delete[](StringUuid);
        }
        v74 = (__m128i)Uuid;
        goto LABEL_111;
      }
    }
    ex_raise(331, 99, 16, 1);
    goto LABEL_135;
  }
  v287 = 1;
  if ( v16 )
  {
    v85 = 19539;
  }
  else if ( v280 )
  {
    v85 = 19523;
  }
  else
  {
    v85 = (v22 ^ 1) + 19543;
    if ( v281 )
      v85 = 19521;
  }
  v295 = v85;
  v310 = MasterDbId;
  v311 = 0;
  v315 = 0;
  v86 = ISECManager::CheckPermRule(1380142168, *(_QWORD *)&Size[1], v289, MasterDbId, 0, 0, -1, v85, 1, 1, 0, 0);
  v312 = v86;
  v309 = 1380142168;
  v314 = v295;
  v313 = 1;
  if ( v86 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v7 + 264) + 232LL))(*(_QWORD *)(v7 + 264), 1);
    v89 = *(_DWORD *)v288;
  }
  else
  {
    v393 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    ISECManager::CheckPermRuleAuditOnly(1380142168, 0, v289, MasterDbId, 0, 0, v295, 0, 0, &v393, 0, 0, 0, -1);
    v311 = 1;
    v87 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v7 + 264) + 232LL))(*(_QWORD *)(v7 + 264), 1);
    v88 = v87;
    v89 = *(_DWORD *)v288;
    if ( *(_DWORD *)v288 )
    {
      v90 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 32LL))(v87, 1);
      v91 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v88 + 24LL))(v88, 1);
      v23 = v278;
      if ( CDefaultCollation::FEqW(v12, *(const wchar_t **)(v278 + 2208), *v305, v91, v90) )
      {
        v86 = 1;
        v287 = 0;
      }
    }
    else
    {
      v23 = v278;
    }
  }
  if ( (unsigned int)CSECCertParams::GetCertType(*(_QWORD *)(v23 + 2208), *(unsigned int *)(v23 + 2216), MasterDbId) != 11 )
  {
    v93 = *(_DWORD *)(v23 + 2216);
    v94 = *(_WORD **)(v23 + 2208);
    v95 = &CSECCertParams::m_rgCertParams + 6 * (int)CSECCertParams::GetCertType(v94, v93, MasterDbId);
    if ( *(_DWORD *)v95 == 11 && v93 && *v94 == 35
      || !CSECCertParams::FCanDoActionInMode(
            (int)(*((_DWORD *)v95 + 10) << 31) >> 31,
            (const struct CSECCertParams::_SECCertParams *)v95,
            MasterDbId) )
    {
      v23 = v278;
      v96 = *(_DWORD *)(v278 + 2216);
      v97 = v96;
      v98 = *(_QWORD *)(v278 + 2208);
LABEL_164:
      v100 = v298;
      if ( v298 )
      {
        AuditSecurityEvent(104, 1, 0, *(wchar_t **)(v23 + 2208), v96, 0, 0, 0, 0);
        v101 = v279;
      }
      else if ( v89 )
      {
        AuditSecurityEvent(105, 1, 0, (wchar_t *)v98, v96, 0, 0, 0, 0);
        v101 = v279;
      }
      else
      {
        v101 = v279;
        if ( v279 )
          AuditSecurityEvent(104, 1, 0, (wchar_t *)v98, v97, 0, 0, 0, 0);
      }
      ex_raise(152, 47, 16, 1);
      v97 = *(_DWORD *)(v23 + 2216);
      v98 = *(_QWORD *)(v23 + 2208);
      goto LABEL_172;
    }
    v23 = v278;
  }
  v97 = *(_DWORD *)(v23 + 2216);
  v98 = *(_QWORD *)(v23 + 2208);
  v96 = v97;
  if ( v97 > 4 )
  {
    _mm_lfence();
    v99 = (unsigned int *)(v23 + 2216);
    if ( CSystemComponent::GetComponentByName((const wchar_t *)(v98 + 4), v97 - 4) )
    {
      v96 = *v99;
      v97 = *v99;
      v98 = *(_QWORD *)(v23 + 2208);
      goto LABEL_164;
    }
    v97 = *v99;
    v96 = *v99;
    v98 = *(_QWORD *)(v23 + 2208);
  }
  if ( !v86 )
    goto LABEL_164;
  v100 = v298;
  v101 = v279;
LABEL_172:
  if ( v100 )
    goto LABEL_176;
  if ( v89 )
  {
    AuditSecurityEvent(105, 1, 1, (wchar_t *)v98, v97, 0, 0, 0, 0);
    goto LABEL_177;
  }
  if ( v101 )
LABEL_176:
    AuditSecurityEvent(104, 1, 1, (wchar_t *)v98, v97, 0, 0, 0, 0);
LABEL_177:
  v394 = v302;
  CStmtOwnerMgmt::ErrorOutIfCloudLifterUnchangeablePrincipal(v92, &v394, 13105);
  v103 = *(_QWORD *)(v23 + 2368);
  if ( v103 )
  {
    v104 = *(_WORD **)(v103 + 8);
    v105 = *(_DWORD *)(v103 + 16);
    v376 = v104;
    v377 = v105;
    LOBYTE(v102) = 1;
    v106 = (unsigned __int8 *)(*(__int64 (__fastcall **)(__int64 *, _WORD **, __int64))(*v289 + 168))(v289, &v376, v102);
    v300 = v106;
    if ( !v106 || v105 && *v104 == 35 )
    {
      LODWORD(v271) = v105;
      LODWORD(v264) = 13131;
      *(_DWORD *)v254 = 13118;
      ex_raise(151, 51, 16, 1, *(_QWORD *)v254, v264, v271, v104);
      v106 = v300;
    }
    v107 = (*(__int64 (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v106 + 8LL))(v106);
    LOBYTE(v275) = 0;
    LOBYTE(v274) = 1;
    if ( !(unsigned __int8)ISECManager::CheckPermRule(
                             1480805464,
                             *(_QWORD *)&Size[1],
                             v289,
                             MasterDbId,
                             0,
                             v107,
                             -1,
                             0,
                             v274,
                             v275,
                             0,
                             0) )
    {
      LODWORD(v271) = v105;
      LODWORD(v265) = 13131;
      *(_DWORD *)v255 = 13118;
      ex_raise(151, 51, 16, 1, *(_QWORD *)v255, v265, v271, v104);
    }
    v23 = v278;
  }
  else
  {
    v300 = 0;
  }
  v108 = v279;
  v109 = (unsigned __int64)*(unsigned int *)(v23 + 2216) >> 1;
  v110 = GetDefaultLocale();
  StringCchPrintf_lW(v523, 0x81u, L"%.*s", v110, v109, *(_QWORD *)(v23 + 2208));
  v111 = *(_QWORD *)(v23 + 2312);
  if ( v111 && (v301 = *(const wchar_t **)(v111 + 8), v112 = *(unsigned int *)(v111 + 16), (Size[0] = v112) != 0) )
  {
    v113 = (*(__int64 (__fastcall **)(__int64 *))(*v289 + 72))(v289);
    v404 = v113;
    if ( !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v113 + 8LL))(
            v113,
            v301,
            (unsigned int)v112) )
    {
      v114 = GetDefaultLocale();
      StringCchPrintf_lW(v531, 0x81u, L"%.*s", v114, v112 >> 1, v301);
      ex_raise(150, 10, 16, 1, v531);
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v113 + 120LL))(v113, 1);
    v23 = v278;
  }
  else
  {
    v301 = L"master";
    Size[0] = dword_102F1BB98;
  }
  v115 = *(_QWORD *)(v23 + 2320);
  if ( v115
    && (v116 = *(const wchar_t **)(v115 + 8), *(_QWORD *)v299 = v116, v117 = *(_DWORD *)(v115 + 16), (v279 = v117) != 0) )
  {
    if ( !GetLangInfoByName(v116, v117) && !GetLangInfoByAlias(v116, v279) )
    {
      v119 = GetDefaultLocale();
      StringCchPrintf_lW(v532, 0x81u, L"%.*s", v119, (unsigned __int64)v279 >> 1, *(_QWORD *)v299);
      ex_raise(150, 33, 16, 1, v532);
    }
  }
  else
  {
    v120 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
    langinfo = get_langinfo(*(_WORD *)(v120 + 154));
    if ( langinfo )
    {
      *(_QWORD *)v299 = *((_QWORD *)langinfo + 1);
      v279 = *((unsigned __int8 *)langinfo + 16);
    }
    else
    {
      *(_QWORD *)v299 = L"us_english";
      v279 = 20;
    }
  }
  if ( v100 )
  {
    v122 = *(_DWORD *)(v23 + 2216);
    v123 = *(_QWORD *)(v23 + 2208);
    if ( v123 )
    {
      if ( v122 )
      {
        v124 = 0;
        v125 = (unsigned __int64)v122 >> 1;
        if ( v125 )
        {
          v126 = 0;
          while ( *(_WORD *)(v123 + 2 * v126) != 92 )
          {
            ++v124;
            if ( ++v126 >= v125 )
              goto LABEL_207;
          }
          if ( v124 >= 0 )
            ex_raise(150, 6, 16, 1, v523);
        }
      }
    }
LABEL_207:
    v127 = *(_QWORD *)(v23 + 2304);
    if ( v127 )
    {
      v128 = *(const void **)(v127 + 8);
      v129 = *(int *)(v127 + 16);
      MasterDbId = v129;
      if ( (_DWORD)v129 != 16 )
        ex_raise(154, 19, 16, 1);
      if ( (_DWORD)v129 )
      {
        if ( v128 )
        {
          memmove(&v514, v128, (unsigned int)v129);
        }
        else
        {
          memset_0(&v514, 0, (unsigned int)v129);
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
      }
      v130 = 0;
      if ( (int)v129 <= 0 )
      {
LABEL_221:
        ex_raise(154, 33, 16, 1);
      }
      else
      {
        v131 = 0;
        while ( !v130 )
        {
          v130 = *((_BYTE *)&v514.Data1 + v131++);
          if ( v131 >= v129 )
          {
            if ( v130 )
              break;
            goto LABEL_221;
          }
        }
      }
    }
    else
    {
      v508 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      if ( CoCreateGuid(&v508) )
        ex_raise(151, 67, 16, 1);
      v514 = v508;
      MasterDbId = 16;
    }
    v132 = 0;
    StringUuid = 0;
    v133 = *(_QWORD *)(v23 + 2256);
    if ( v133 )
    {
      v132 = *(unsigned __int16 **)(v133 + 8);
      StringUuid = v132;
      v134 = *(_DWORD *)(v133 + 16);
      if ( v134 > 0x100 )
      {
        *(_DWORD *)v256 = 128;
        ex_raise(151, 56, 16, 1, *(_QWORD *)v256);
      }
    }
    else
    {
      v134 = 0;
    }
    v308 = 512;
    v135 = *(_QWORD *)(v23 + 2264);
    if ( !v135 || !*(_DWORD *)(v135 + 16) )
    {
      SecureHash(v529, &v308, v132, v134, 1, 0);
      v138 = 0;
      v277[0] = 0;
      v281 = v308;
      goto LABEL_251;
    }
    v277[0] = 1;
    if ( v134 > 0x200 )
      ex_raise(150, 21, 16, 1, L"PASSWORD");
    if ( v134 )
    {
      if ( v132 && v134 <= 0x200uLL )
      {
        memmove(v529, v132, v134);
        goto LABEL_242;
      }
      memset_0(v529, 0, 0x200u);
      if ( v132 )
      {
        if ( v134 <= 0x200uLL )
          goto LABEL_242;
        *_errno() = 34;
      }
      else
      {
        *_errno() = 22;
      }
      _invalid_parameter_noinfo();
    }
LABEL_242:
    v281 = v134;
    if ( v134 == 16 )
    {
      v136 = 1;
      v137 = 0;
      v138 = 1;
    }
    else
    {
      v150 = -1;
      v151 = -1;
      v139 = v529[0];
      if ( v529[0] == 1 )
      {
        if ( v134 == 26 || v134 == 46 )
          v151 = 1;
      }
      else if ( v529[0] == 2 && v134 == 70 && v529[0] == 2 )
      {
        v151 = 2;
      }
      v136 = v151 < 2;
      if ( v529[0] == 1 )
      {
        if ( v134 == 26 || (v137 = v151, v138 = v151 < 2, v134 == 46) )
        {
          v137 = v151;
          v138 = v151 < 2;
          goto LABEL_245;
        }
      }
      else if ( v529[0] == 2 )
      {
        if ( v134 == 70 && v529[0] == 2 )
          v150 = 2;
        v137 = v151;
        v138 = v151 < 2;
        if ( v150 >= 1 )
          goto LABEL_245;
      }
      else
      {
        v137 = v151;
        v138 = v151 < 2;
      }
    }
    ex_raise(150, 21, 16, 2, L"PASSWORD");
    v139 = v529[0];
LABEL_245:
    if ( v137 == 1 )
    {
      if ( (v134 == 26 || v134 == 46) && v139 == 1 )
        v281 = 26;
      else
        v138 = v136;
    }
    v23 = v278;
LABEL_251:
    v140 = *(_QWORD *)(v23 + 2296);
    v141 = 1;
    v276 = 1;
    if ( !v140 )
      goto LABEL_258;
    v142 = *(const wchar_t **)(v140 + 8);
    v143 = *(int *)(v140 + 16);
    if ( (_DWORD)v143 )
    {
      v144 = v143 >> 1;
      if ( CompareStringWEnglishNoCase(1u, 0, v142, v143 >> 1, L"on", 2) == 2 )
      {
LABEL_256:
        v276 = v141;
        goto LABEL_257;
      }
      if ( CompareStringWEnglishNoCase(1u, 0, v142, v144, L"off", 3) == 2 )
      {
        v141 = 0;
        goto LABEL_256;
      }
    }
LABEL_257:
    v23 = v278;
LABEL_258:
    v145 = *(_QWORD *)(v23 + 2288);
    v146 = 0;
    if ( v145 )
    {
      v147 = *(const wchar_t **)(v145 + 8);
      v148 = *(int *)(v145 + 16);
      if ( (_DWORD)v148 )
      {
        v149 = v148 >> 1;
        if ( CompareStringWEnglishNoCase(1u, 0, v147, v148 >> 1, L"on", 2) == 2 )
          v146 = 1;
        else
          CompareStringWEnglishNoCase(1u, 0, v147, v149, L"off", 3);
        v23 = v278;
      }
    }
    v152 = *(_QWORD *)(v23 + 2272);
    v153 = 0;
    v280 = 0;
    if ( v152 && *(_DWORD *)(v152 + 16) )
    {
      v280 = 1;
      PwdPolicyManager = GetPwdPolicyManager();
      v405 = PwdPolicyManager;
      if ( !(**(unsigned int (__fastcall ***)(struct IPwdPolicyManager *))PwdPolicyManager)(PwdPolicyManager) )
        ex_raise(151, 95, 16, 1);
      if ( v277[0] )
        ex_raise(330, 10, 16, 1);
      operator delete(PwdPolicyManager, 8u);
      v153 = v280;
    }
    if ( v146 && !v141 )
      ex_raise(151, 22, 16, 1);
    if ( v153 && !v146 )
      ex_raise(150, 99, 16, 1);
    v395 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, GUID *, _QWORD, _DWORD, _DWORD, _DWORD, GUID *))(*v289 + 360))(
           v289,
           &v302,
           &v514,
           MasterDbId,
           0,
           0,
           0,
           &v395);
    if ( !v9 )
    {
      LOBYTE(v257) = 1;
      v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD, _QWORD, int, _DWORD))(*v289 + 344))(
             v289,
             &v514,
             MasterDbId,
             0,
             v257,
             0);
      if ( v9 )
        ex_raise(154, 33, 16, 1);
      else
        ex_raise(150, 25, 16, 1, v523);
    }
    *(_OWORD *)v327 = 0;
    v328 = 0;
    v329 = 0;
    v330 = 0;
    v331 = 0;
    v332 = 0;
    utgettime((struct SQLDATEBASE *)&v335, 1, 0);
    HIDWORD(v327[0]) = v281;
    v155 = (unsigned __int8 *)operator new[](
                                v281,
                                *(struct IMemObj **)&Size[1],
                                "sql\\ntdbms\\msql\\security\\src\\secddl.cpp",
                                7013,
                                3u);
    v327[1] = v155;
    if ( v281 )
    {
      if ( v155 )
      {
        memmove(v155, v529, v281);
      }
      else
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
    }
    *(_QWORD *)&v328 = v335;
    LOBYTE(v327[0]) = v276 & 0xFD | (__int64)v327[0] & 0xFC | (2 * v146);
    if ( v276 && v277[0] && !v138 )
    {
      InitializePwdHashHistory(
        *(struct IMemObj **)&Size[1],
        (struct MDAttrLoginPassword *)v327,
        v327[1],
        SHIDWORD(v327[0]));
      (*(void (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v9 + 312LL))(v9, 39, v327);
    }
    else
    {
      (*(void (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v9 + 312LL))(v9, 7, v327);
      if ( !v277[0] )
      {
        v156 = GetPwdPolicyManager();
        v296 = v156;
        if ( v281 == 70 )
        {
          v157 = (struct IPwdPolicyManager *)v530;
          v158 = 64;
        }
        else if ( (v281 == 26 || v281 == 46) && v529[0] == 1 )
        {
          v157 = (struct IPwdPolicyManager *)v530;
          v158 = 20;
        }
        else
        {
          v158 = v307;
          v157 = v296;
        }
        v362[2] = 0;
        v362[1] = 0;
        v362[0] = v9;
        v363 = 0;
        LOBYTE(v273) = 0;
        LOBYTE(v272) = v280;
        v159 = (*(__int64 (__fastcall **)(struct IPwdPolicyManager *, _QWORD *, RPC_WSTR, _QWORD, struct IPwdPolicyManager *, int, int, int))(*(_QWORD *)v156 + 24LL))(
                 v156,
                 v362,
                 StringUuid,
                 v134,
                 v157,
                 v158,
                 v272,
                 v273);
        HandlePasswordValidationResultCode(v159);
        operator delete(v156, 8u);
      }
    }
    operator delete[](v327[1]);
    operator delete[](*((void **)&v331 + 1));
    operator delete[](v332);
    if ( HIDWORD(v329) )
    {
      v160 = 0;
      do
        operator delete[](*(void **)(*((_QWORD *)&v330 + 1) + 8LL * v160++));
      while ( v160 < HIDWORD(v329) );
    }
    operator delete[]((void *)v330);
    operator delete[](*((void **)&v330 + 1));
    goto LABEL_430;
  }
  if ( v89 )
  {
    v303 = 85;
    v283 = 0;
    v282 = 0;
    v161 = *(const wchar_t **)(v23 + 2208);
    v162 = (_DWORD *)(v23 + 2216);
    v163 = *(_DWORD *)(v23 + 2216);
    if ( !v161 )
      goto LABEL_330;
    if ( !v163 )
      goto LABEL_330;
    v164 = 0;
    if ( !((unsigned __int64)v163 >> 1) )
      goto LABEL_330;
    v165 = 0;
    while ( v161[v165] != 92 )
    {
      ++v164;
      if ( ++v165 >= (__int64)((unsigned __int64)v163 >> 1) )
        goto LABEL_330;
    }
    if ( v164 >= 0 && v163 - 1 != v164 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset)
                                 + 72LL)
                     + 270LL)
          & 4) == 0 )
      {
        v292[0] = 85;
        v171 = FGetSidFromNt(v161, v163, pSid, v292, 85, 1);
        v167 = v171 != 0;
        if ( v171 )
          v172 = v282;
        else
          v172 = (unsigned int)FGetSidFromNt(v161, (unsigned int)*v162, pSid, v292, 71, 1) != 0;
        if ( !v167 && !v172 )
          ex_raise(154, 1, 16, 1, v523);
        v166 = v292[0];
LABEL_334:
        if ( OsInfo::IsLinux(SOS_OS_OsInfo) )
        {
          SidSubAuthority = GetSidSubAuthority(pSid, 0);
          LastError = GetLastError();
          if ( LastError > 0 )
            v170 = (unsigned __int16)LastError | 0x80070000;
          else
            v170 = LastError;
          if ( v170 )
          {
            CSECErrorRingBufferManager::StoreRecord(
              L"GetSidSubAuthority",
              L"FIsNonUniqueSID",
              LastError,
              CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
              0);
            goto LABEL_351;
          }
          if ( *SidSubAuthority != 21 )
          {
LABEL_351:
            if ( !(unsigned int)FIsLinuxNTAuthoritySID(pSid) )
            {
              LODWORD(v271) = *v162;
              LODWORD(v267) = 13115;
              *(_DWORD *)v258 = 13105;
              ex_raise(151, 51, 16, 4, *(_QWORD *)v258, v267, v271, *(_QWORD *)(v278 + 2208));
            }
          }
        }
        v397 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
        v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int8 *, _QWORD, unsigned int, _DWORD, _DWORD, GUID *))(*v289 + 360))(
               v289,
               &v302,
               pSid,
               v166,
               2 - (unsigned int)v167,
               0,
               0,
               &v397);
        if ( v9 )
        {
LABEL_431:
          v378 = v301;
          v379 = Size[0];
          (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v9 + 288LL))(v9, &v378);
          v380 = *(_QWORD *)v299;
          v381 = v279;
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 296LL))(v9, &v380);
          goto LABEL_432;
        }
        ex_raise(150, 25, 16, 2, v523);
LABEL_432:
        v210 = 4;
        goto LABEL_433;
      }
    }
    else
    {
LABEL_330:
      if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
        ex_raise(154, 7, 16, 1, v523);
    }
    v396 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    LOBYTE(v266) = 0;
    LookupFederatedPrincipal(v161, v23 + 2216, v523, 0, &pguid, v266, pSid, &v303, &v283, &v282, &v396);
    v166 = v303;
    v167 = v283;
    goto LABEL_334;
  }
  if ( v280 )
  {
    v173 = *(_DWORD *)(v23 + 2216);
    v174 = *(_QWORD *)(v23 + 2208);
    if ( v174 )
    {
      if ( v173 )
      {
        v175 = 0;
        v176 = (unsigned __int64)v173 >> 1;
        if ( v176 )
        {
          v177 = 0;
          while ( *(_WORD *)(v174 + 2 * v177) != 92 )
          {
            ++v175;
            if ( ++v177 >= v176 )
              goto LABEL_365;
          }
          if ( v175 >= 0 )
            ex_raise(150, 6, 16, 1, v523);
        }
      }
    }
LABEL_365:
    v178 = 0;
    v179 = *(_QWORD *)(v23 + 2344);
    if ( v179 )
    {
      v178 = *(_QWORD *)(v179 + 8);
      v180 = *(_DWORD *)(v179 + 16);
    }
    else
    {
      v180 = 0;
    }
    v323 = v178;
    v324 = v180;
    v181 = *v289;
    v182 = GetMasterDbId();
    v183 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(v181 + 56))(
             v289,
             v182,
             0,
             0,
             0,
             0);
    v184 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v183 + 800LL))(v183, &v323, 0);
    if ( !v184 )
    {
      LODWORD(v271) = v324;
      LODWORD(v268) = 13116;
      *(_DWORD *)v259 = 13118;
      ex_raise(151, 51, 16, 1, *(_QWORD *)v259, v268, v271, v323);
    }
    v185 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset)
                                             + 72LL)
                                 + 104LL)
                     + 264LL)
         + 216LL;
    v316 = 0;
    CSECSessionCryptoContext::GetCryptoContext(v185, v412, 3, &v316);
    if ( v412[0] )
    {
      v296 = (struct IPwdPolicyManager *)v410;
      v411 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v410, (const struct CSECCryptoError *)v412);
      RaiseCryptoError(v410, 0);
    }
    if ( v413 )
      operator delete[](v413);
    v304 = 85;
    *(_OWORD *)hCertStore = 0;
    v343 = 0;
    v344 = v316;
    pCertContext = 0;
    v346 = 0;
    CSECCertificate::InitFromMD(hCertStore, v414, *(_QWORD *)&Size[1], v184);
    if ( v414[0] )
    {
      v296 = (struct IPwdPolicyManager *)v426;
      v427 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v426, (const struct CSECCryptoError *)v414);
      RaiseCryptoError(v426, 0);
    }
    if ( v415 )
      operator delete[](v415);
    CSECCertificate::GetSid(hCertStore, v418, &v304, v525);
    if ( v418[0] )
    {
      v296 = (struct IPwdPolicyManager *)v416;
      v417 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v416, (const struct CSECCryptoError *)v418);
      RaiseCryptoError(v416, 0);
    }
    if ( v419 )
      operator delete[](v419);
    v259[0] = 1;
    v186 = v304;
    if ( (*(__int64 (__fastcall **)(__int64 *, _BYTE *, _QWORD, _QWORD, _DWORD, _DWORD))(*v289 + 344))(
           v289,
           v525,
           v304,
           0,
           *(_DWORD *)v259,
           0) )
    {
      LODWORD(v271) = v324;
      *(_DWORD *)v260 = DWORD2(v302);
      ex_raise(331, 40, 16, 1, *(_QWORD *)v260, (_QWORD)v302, v271, v323);
    }
    else
    {
      v398 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _BYTE *, _QWORD, int, _DWORD, _DWORD, GUID *))(*v289 + 360))(
             v289,
             &v302,
             v525,
             v186,
             4,
             0,
             0,
             &v398);
      if ( !v9 )
        ex_raise(150, 25, 16, 3, v523);
    }
    if ( pCertContext )
    {
      CertFreeCertificateContext(pCertContext);
      pCertContext = 0;
    }
    if ( hCertStore[0] )
    {
      CertCloseStore(hCertStore[0], 0);
      hCertStore[0] = 0;
    }
    goto LABEL_430;
  }
  if ( v281 )
  {
    v187 = *(_DWORD *)(v23 + 2216);
    v188 = *(_QWORD *)(v23 + 2208);
    if ( v188 )
    {
      if ( v187 )
      {
        v189 = 0;
        v190 = (unsigned __int64)v187 >> 1;
        if ( v190 )
        {
          v191 = 0;
          while ( *(_WORD *)(v188 + 2 * v191) != 92 )
          {
            ++v189;
            if ( ++v191 >= v190 )
              goto LABEL_400;
          }
          if ( v189 >= 0 )
            ex_raise(150, 6, 16, 1, v523);
        }
      }
    }
LABEL_400:
    v192 = 0;
    v193 = *(_QWORD *)(v23 + 2376);
    if ( v193 )
    {
      v192 = *(_QWORD *)(v193 + 8);
      v194 = *(_DWORD *)(v193 + 16);
    }
    else
    {
      v194 = 0;
    }
    v325 = v192;
    v326 = v194;
    v195 = *v289;
    v196 = GetMasterDbId();
    v197 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(v195 + 56))(
             v289,
             v196,
             0,
             0,
             0,
             0);
    v198 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v197 + 960LL))(v197, &v325, 0);
    if ( !v198 )
    {
      LODWORD(v271) = v326;
      LODWORD(v269) = 13141;
      *(_DWORD *)v261 = 13118;
      ex_raise(151, 51, 16, 1, *(_QWORD *)v261, v269, v271, v325);
    }
    v199 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset)
                                             + 72LL)
                                 + 104LL)
                     + 264LL)
         + 216LL;
    v318 = 0;
    CSECSessionCryptoContext::GetCryptoContext(v199, v422, 3, &v318);
    if ( v422[0] )
    {
      v296 = (struct IPwdPolicyManager *)v420;
      v421 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v420, (const struct CSECCryptoError *)v422);
      RaiseCryptoError(v420, 0);
    }
    if ( v423 )
      operator delete[](v423);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v198 + 72LL))(v198, v509);
    if ( v510 == 6 )
    {
      v333 = 0;
      v317 = 0;
      v200 = CSECGlobalCryptoContext::m_cctxGlobal;
      v201 = *v289;
      v202 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v198 + 56LL))(v198);
      v204 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v201 + 584))(
                                                 v289,
                                                 v202,
                                                 0);
      if ( !v204 )
      {
        v205 = (const struct _GUID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v198 + 56LL))(v198);
        GuidToString(v205, v526, 0x4Au);
        ex_raise(330, 82, 16, 2, v526);
      }
      LOBYTE(v269) = 0;
      CSECGlobalCryptoContext::GetCryptoProvider(v200, v408, v203, v204, &v317, (_DWORD)v269);
      if ( v408[0] )
      {
        v296 = (struct IPwdPolicyManager *)v424;
        v425 = 0;
        CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v424, (const struct CSECCryptoError *)v408);
        RaiseCryptoError(v424, 0);
      }
      if ( v409 )
        operator delete[](v409);
      v206 = v317;
      v333 = v317;
      if ( *(_DWORD *)(v317 + 220) != 1 )
      {
        v207 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64))v198)(v198);
        v208 = (_QWORD *)(**v204)(v204);
        LODWORD(v270) = 13141;
        *(_DWORD *)v262 = 13115;
        ex_raise(330, 83, 16, 1, *(_QWORD *)v262, v270, *v207, *v208);
      }
      v209 = v206 + *(int *)(*(_QWORD *)(v206 + 8) + 4LL) + 8LL;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v209 + 8LL))(v209);
    }
    LODWORD(v305) = 85;
    CSECAsymmetricKey::CSECAsymmetricKey(v513, v318, 0, 0);
    CSECAsymmetricKey::InitFromMD(v513, v430, *(_QWORD *)&Size[1], v198);
    if ( v430[0] )
    {
      v296 = (struct IPwdPolicyManager *)v428;
      v429 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v428, (const struct CSECCryptoError *)v430);
      RaiseCryptoError(v428, 0);
    }
    if ( v431 )
      operator delete[](v431);
    CSECAsymmetricKey::GetSid(v513, v406, &v305, v527);
    if ( v406[0] )
    {
      v296 = (struct IPwdPolicyManager *)v432;
      v433 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v432, (const struct CSECCryptoError *)v406);
      RaiseCryptoError(v432, 0);
    }
    if ( v407 )
      operator delete[](v407);
    v399 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _BYTE *, _QWORD, int, _DWORD, _DWORD, GUID *))(*v289 + 360))(
           v289,
           &v302,
           v527,
           (unsigned int)v305,
           5,
           0,
           0,
           &v399);
    if ( !v9 )
      ex_raise(150, 25, 16, 2, v523);
    CSECAsymmetricKey::~CSECAsymmetricKey((CSECAsymmetricKey *)v513);
LABEL_430:
    if ( v9 )
      goto LABEL_431;
    goto LABEL_432;
  }
  if ( !v108 )
    goto LABEL_432;
  v224 = 85;
  v294 = 85;
  v225 = 0;
  v285 = 0;
  v284 = 0;
  v226 = v278;
  v227 = *(_QWORD *)(v278 + 2304);
  v228 = *(_QWORD *)(v278 + 2416);
  v229 = *(_QWORD *)(v278 + 2424);
  v230 = 0;
  v231 = *(_DWORD *)(v278 + 2216);
  v232 = *(_QWORD *)(v278 + 2208);
  if ( v232 && v231 )
  {
    v233 = 0;
    v234 = (unsigned __int64)v231 >> 1;
    if ( v234 )
    {
      v235 = 0;
      while ( *(_WORD *)(v232 + 2 * v235) != 92 )
      {
        ++v233;
        if ( ++v235 >= v234 )
          goto LABEL_459;
      }
      if ( v233 >= 0 )
        ex_raise(150, 6, 16, 2, v523);
    }
LABEL_459:
    v226 = v278;
  }
  if ( !v227 )
  {
    if ( !v228 )
    {
      if ( v229 )
      {
        v242 = *(_QWORD *)(v226 + 2424);
        if ( v242 )
        {
          v230 = *(const wchar_t **)(v242 + 8);
          v243 = *(_DWORD *)(v242 + 16);
        }
        else
        {
          v243 = 0;
        }
        v307 = v243;
      }
      v244 = *(const wchar_t **)(v226 + 2208);
      v245 = (int *)(v226 + 2216);
      v246 = *(_DWORD *)(v226 + 2216);
      if ( !v244 )
        goto LABEL_499;
      if ( !v246 )
        goto LABEL_499;
      v247 = 0;
      if ( !((unsigned __int64)v246 >> 1) )
        goto LABEL_499;
      v248 = 0;
      while ( v244[v248] != 92 )
      {
        ++v247;
        if ( ++v248 >= (__int64)((unsigned __int64)v246 >> 1) )
          goto LABEL_499;
      }
      if ( v247 >= 0 && v246 - 1 != v247 )
      {
        v249 = v230 != 0;
        if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset)
                                   + 72LL)
                       + 270LL)
            & 4) == 0 )
        {
          v288[0] = 85;
          v251 = FGetSidFromNt(v244, v246, v515, v288, 85, 1);
          v225 = v251 != 0;
          if ( v251 )
            v252 = v284;
          else
            v252 = (unsigned int)FGetSidFromNt(v244, (unsigned int)*v245, v515, v288, 71, 1) != 0;
          if ( !v225 && !v252 )
            ex_raise(154, 1, 16, 1, v523);
          v224 = v288[0];
          goto LABEL_518;
        }
      }
      else
      {
LABEL_499:
        v249 = v230 != 0;
        if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
          ex_raise(154, 7, 16, 1, v523);
      }
      v250 = &v307;
      if ( !v230 )
        v250 = v245;
      v400 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      if ( v230 )
        v244 = v230;
      LOBYTE(v266) = v249;
      LookupFederatedPrincipal(v244, v250, v523, 0, &pguid, v266, v515, &v294, &v285, &v284, &v400);
      v224 = v294;
      v225 = v285;
      goto LABEL_518;
    }
LABEL_517:
    ex_raise(331, 98, 16, 1);
    goto LABEL_518;
  }
  if ( !v228 )
    goto LABEL_517;
  v236 = 0;
  v237 = *(_QWORD *)(v226 + 2304);
  v238 = 8;
  if ( v237 )
  {
    v236 = *(const void **)(v237 + 8);
    v224 = *(_DWORD *)(v237 + 16);
    if ( v224 == 16 )
      goto LABEL_467;
  }
  else
  {
    v224 = 0;
  }
  ex_raise(154, 19, 16, 8);
LABEL_467:
  if ( !v224 )
    goto LABEL_476;
  if ( v236 && v224 <= 0x55uLL )
  {
    memmove(v515, v236, v224);
    goto LABEL_476;
  }
  *(_OWORD *)v515 = 0;
  v516 = 0;
  v517 = 0;
  v518 = 0;
  v519 = 0;
  v520 = 0;
  v521 = 0;
  if ( v236 )
  {
    if ( v224 <= 0x55uLL )
      goto LABEL_476;
    *_errno() = 34;
  }
  else
  {
    *_errno() = 22;
  }
  _invalid_parameter_noinfo();
LABEL_476:
  v239 = 0;
  v240 = *(_QWORD *)(v278 + 2416);
  if ( !v240 || (v239 = *(__int16 **)(v240 + 8), *(_DWORD *)(v240 + 16) != 2) )
    ex_raise(331, 97, 16, 1);
  if ( !v239 )
    goto LABEL_484;
  v241 = *v239;
  if ( *v239 != 69 )
  {
    if ( v241 == 88 )
      goto LABEL_485;
    if ( v241 != 101 )
    {
      if ( v241 != 120 )
      {
LABEL_484:
        ex_raise(331, 97, 16, 1);
        v238 = 0;
      }
LABEL_485:
      v225 = v238 == 7;
      goto LABEL_518;
    }
  }
  v225 = 1;
LABEL_518:
  v401 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int8 *, _QWORD, unsigned int, _DWORD, _DWORD, GUID *))(*v289 + 360))(
         v289,
         &v302,
         v515,
         v224,
         8 - (unsigned int)v225,
         0,
         0,
         &v401);
  if ( v9 )
    goto LABEL_431;
  v210 = 4;
  ex_raise(150, 25, 16, 4, v523);
LABEL_433:
  if ( v300 && v9 )
  {
    v211 = *(_QWORD *)v9;
    v212 = (*(__int64 (**)(void))(*(_QWORD *)v300 + 8LL))();
    (*(void (__fastcall **)(__int64, _QWORD))(v211 + 304))(v9, v212);
  }
  v213 = v289;
  if ( v287 )
  {
    LOBYTE(v118) = 1;
    v214 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, __int64, _DWORD))(*v289 + 336))(v289, 1, 0, v118, 0);
    v319 = 0x100000000LL;
    v215 = (*(__int64 (__fastcall **)(__int64 *))(*v213 + 368))(v213);
    v403 = v215;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v215 + 176LL))(v215);
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64 *, int))(*(_QWORD *)v215 + 216LL))(
      v215,
      v9,
      v214,
      &v319,
      1);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v215 + 240LL))(v215, 1);
  }
  if ( v9 )
  {
    v216 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( !v311 )
    {
      v402 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      ISECManager::CheckPermRuleAuditOnly(
        1380142168,
        *(_QWORD *)&Size[1],
        v213,
        v310,
        v216,
        v312,
        v295,
        0,
        0,
        &v402,
        0,
        0,
        0,
        -1);
      v311 = 1;
    }
  }
  v217 = (*(__int64 (__fastcall **)(__int64 *))(*v213 + 16))(v213);
  v218 = GetMasterDbId();
  v219 = g_dbtableFactory[4](v218);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v217 + 280LL))(v217, *(_QWORD *)(v219 + 4624));
  v220 = GetMasterDbId();
  InvalidateSecurityCaches(v220, 24, 0);
  v286 = 1;
  v221 = v322;
  PostLoginEvent(48, v322, v334, v9, &v286, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
  if ( v286 )
  {
    if ( (*(_DWORD *)(GetXdbServerGlobals(v223, v222) + 11976) || (unsigned int)IsVDWFrontendInstance())
      && (*(_BYTE *)(*(_QWORD *)(v320 + 72) + 270LL) & 2) == 0
      && (qword_102F21DB4 & 4) != 0 )
    {
      v489 = 196608;
      v490 = 0;
      v491 = &v494;
      v492 = &v502;
      v503 = 0;
      v493 = 0;
      v504 = 0;
      v494 = &v505;
      v495 = 16;
      v496 = 2;
      v497 = L"CREATE";
      v498 = 12;
      v499 = L"FINISH";
      v500 = 12;
      v501 = 1;
      XeCloudPkg::azuresqldb_login_ddl::Publish((XeCloudPkg::azuresqldb_login_ddl *)v488);
    }
    *(_BYTE *)(v221 + 176) |= 0x10u;
    v210 = 0;
  }
  CAutoHandleCreateAudit::~CAutoHandleCreateAudit((CAutoHandleCreateAudit *)&v309);
  return v210;
}

```

## disassembly

```asm
0x101467110  push    rbp
0x101467112  push    rbx
0x101467113  push    rsi
0x101467114  push    rdi
0x101467115  push    r12
0x101467117  push    r13
0x101467119  push    r14
0x10146711b  push    r15
0x10146711d  lea     rbp, [rsp-36A8h]
0x101467125  mov     eax, 37A8h
0x10146712a  call    _alloca_probe
0x10146712f  sub     rsp, rax
0x101467132  mov     [rbp+36E0h+var_3390], 0FFFFFFFFFFFFFFFEh
0x10146713d  movaps  [rsp+37E0h+var_50], xmm6
0x101467145  mov     rax, cs:__security_cookie
0x10146714c  xor     rax, rsp
0x10146714f  mov     [rbp+36E0h+var_60], rax
0x101467156  mov     [rbp+36E0h+var_35D8], r9
0x10146715d  mov     rsi, r8
0x101467160  mov     [rbp+36E0h+var_3668], r8
0x101467164  mov     rbx, rdx
0x101467167  mov     [rbp+36E0h+var_3678], rdx
0x10146716b  mov     rdi, rcx
0x10146716e  mov     [rbp+36E0h+var_3758], rcx
0x101467172  mov     r13, [rdx+78h]
0x101467176  mov     rax, [r9+78h]
0x10146717a  mov     qword ptr [rbp+36E0h+Size+4], rax
0x10146717e  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x101467184  movzx   eax, ax
0x101467187  mov     [rbp+36E0h+var_3730], eax
0x10146718a  mov     rax, [rsi+38h]
0x10146718e  mov     [rbp+36E0h+var_3738], rax
0x101467192  xor     r14d, r14d
0x101467195  mov     r15d, r14d
0x101467198  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x10146719f  movups  xmmword ptr [rbp+36E0h+pguid.Data1], xmm0
0x1014671a6  movaps  xmmword ptr [rbp+36E0h+Uuid.Data1], xmm0
0x1014671ad  lea     rcx, [rbp+36E0h+pguid]; pguid
0x1014671b4  call    cs:__imp_CoCreateGuid
0x1014671ba  mov     rax, [rbx+48h]
0x1014671be  lea     r9, aCreate; "CREATE"
0x1014671c5  test    byte ptr [rax+10Eh], 4
0x1014671cc  jnz     short loc_101467202
0x1014671ce  call    cs:__imp_GetXdbServerGlobals
0x1014671d4  cmp     [rax+2EC8h], r14d
0x1014671db  jnz     short loc_1014671EA
0x1014671dd  call    ?IsVDWFrontendInstance@@YAHXZ; IsVDWFrontendInstance(void)
0x1014671e2  test    eax, eax
0x1014671e4  jz      loc_1014672B3
0x1014671ea  mov     rax, [rbx+48h]
0x1014671ee  test    byte ptr [rax+10Eh], 2
0x1014671f5  jnz     loc_1014672B3
0x1014671fb  lea     r9, aCreate; "CREATE"
0x101467202  test    byte ptr cs:qword_102F21DB4, 4
0x101467209  jz      loc_1014672B3
0x10146720f  mov     [rbp+36E0h+var_3058], 30000h
0x101467219  mov     [rbp+36E0h+var_3050], r14d
0x101467220  lea     rax, [rbp+36E0h+var_3030]
0x101467227  mov     [rbp+36E0h+var_3048], rax
0x10146722e  lea     rax, [rbp+36E0h+var_3000]
0x101467235  mov     [rbp+36E0h+var_3040], rax
0x10146723c  mov     [rbp+36E0h+var_2E10], r14
0x101467243  mov     [rbp+36E0h+var_3038], r14
0x10146724a  mov     [rbp+36E0h+var_2E08], r14
0x101467251  lea     rax, [rbp+36E0h+var_2E00]
0x101467258  mov     [rbp+36E0h+var_3030], rax
0x10146725f  mov     [rbp+36E0h+var_3028], 10h
0x101467269  mov     [rbp+36E0h+var_3024], 2
0x101467273  mov     [rbp+36E0h+var_3020], r9
0x10146727a  mov     [rbp+36E0h+var_3018], 0Ch
0x101467285  lea     rax, aStart_2; "START"
0x10146728c  mov     [rbp+36E0h+var_3010], rax
0x101467293  mov     [rbp+36E0h+var_3008], 0Ah
0x10146729d  mov     [rbp+36E0h+var_3004], 1
0x1014672a7  lea     rcx, [rbp+36E0h+var_3060]; this
0x1014672ae  call    ?Publish@azuresqldb_login_ddl@XeCloudPkg@@QEAAXXZ; XeCloudPkg::azuresqldb_login_ddl::Publish(void)
0x1014672b3  call    cs:__imp_?PDCServer@CDefaultCollation@@SAPEAV1@XZ; CDefaultCollation::PDCServer(void)
0x1014672b9  mov     r12, rax
0x1014672bc  mov     rbx, r14
0x1014672bf  mov     rcx, [rdi+918h]
0x1014672c6  test    rcx, rcx
0x1014672c9  jz      short loc_1014672D4
0x1014672cb  mov     rbx, [rcx+8]
0x1014672cf  mov     edx, [rcx+10h]
0x1014672d2  jmp     short loc_1014672D7
0x1014672d4  mov     edx, r14d
0x1014672d7  mov     esi, r14d
0x1014672da  mov     [rbp+36E0h+var_3704], r14d
0x1014672de  mov     [rbp+36E0h+var_374C], r14d
0x1014672e2  mov     dword ptr [rbp+36E0h+var_373C], r14d
0x1014672e6  mov     [rbp+36E0h+var_3748], r14d
0x1014672ea  mov     [rbp+36E0h+var_3750], r14d
0x1014672ee  mov     rcx, cs:?SqlLogin@CStmtCreateLogin@@2U_LoginType@1@B; CStmtCreateLogin::_LoginType const CStmtCreateLogin::SqlLogin
0x1014672f5  movsxd  rdi, edx
0x1014672f8  shr     rdi, 1
0x1014672fb  movsxd  rax, cs:dword_1026DF3E8
0x101467302  shr     rax, 1
0x101467305  mov     dword ptr [rsp+37E0h+var_37B8], eax
0x101467309  mov     qword ptr [rsp+37E0h+var_37C0], rcx
0x10146730e  mov     r9d, edi
0x101467311  mov     r8, rbx
0x101467314  xor     edx, edx
0x101467316  lea     ecx, [rdx+1]
0x101467319  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10146731f  cmp     eax, 2
0x101467322  jnz     short loc_101467333
0x101467324  mov     edi, 1
0x101467329  mov     esi, edi
0x10146732b  mov     [rbp+36E0h+var_3704], edi
0x10146732e  jmp     loc_1014674A3
0x101467333  mov     rcx, cs:?NtLogin@CStmtCreateLogin@@2U_LoginType@1@B; CStmtCreateLogin::_LoginType const CStmtCreateLogin::NtLogin
0x10146733a  movsxd  rax, cs:dword_1026DF3F8
0x101467341  shr     rax, 1
0x101467344  mov     dword ptr [rsp+37E0h+var_37B8], eax
0x101467348  mov     qword ptr [rsp+37E0h+var_37C0], rcx
0x10146734d  mov     r9d, edi
0x101467350  mov     r8, rbx
0x101467353  xor     edx, edx
0x101467355  lea     ecx, [rdx+1]
0x101467358  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10146735e  cmp     eax, 2
0x101467361  jnz     short loc_101467370
0x101467363  mov     edi, 1
0x101467368  mov     dword ptr [rbp+36E0h+var_373C], edi
0x10146736b  jmp     loc_1014674A3
0x101467370  mov     rcx, cs:?CertLogin@CStmtCreateLogin@@2U_LoginType@1@B; CStmtCreateLogin::_LoginType const CStmtCreateLogin::CertLogin
0x101467377  movsxd  rax, cs:dword_1026DF618
0x10146737e  shr     rax, 1
0x101467381  mov     dword ptr [rsp+37E0h+var_37B8], eax
0x101467385  mov     qword ptr [rsp+37E0h+var_37C0], rcx
0x10146738a  mov     r9d, edi
0x10146738d  mov     r8, rbx
0x101467390  xor     edx, edx
0x101467392  lea     ecx, [rdx+1]
0x101467395  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10146739b  cmp     eax, 2
0x10146739e  jnz     short loc_1014673AD
0x1014673a0  mov     edi, 1
0x1014673a5  mov     [rbp+36E0h+var_374C], edi
0x1014673a8  jmp     loc_1014674A3
0x1014673ad  mov     rcx, cs:?AKeyLogin@CStmtCreateLogin@@2U_LoginType@1@B; CStmtCreateLogin::_LoginType const CStmtCreateLogin::AKeyLogin
0x1014673b4  movsxd  rax, cs:dword_1026DF628
0x1014673bb  shr     rax, 1
0x1014673be  mov     dword ptr [rsp+37E0h+var_37B8], eax
0x1014673c2  mov     qword ptr [rsp+37E0h+var_37C0], rcx
0x1014673c7  mov     r9d, edi
0x1014673ca  mov     r8, rbx
0x1014673cd  xor     edx, edx
0x1014673cf  lea     ecx, [rdx+1]
0x1014673d2  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x1014673d8  cmp     eax, 2
0x1014673db  jnz     short loc_1014673EA
0x1014673dd  mov     edi, 1
0x1014673e2  mov     [rbp+36E0h+var_3748], edi
0x1014673e5  jmp     loc_1014674A3
0x1014673ea  mov     rcx, cs:?ExternalLogin@CStmtCreateLogin@@2U_LoginType@1@B; CStmtCreateLogin::_LoginType const CStmtCreateLogin::ExternalLogin
0x1014673f1  movsxd  rax, cs:dword_1026DF608
0x1014673f8  shr     rax, 1
0x1014673fb  mov     dword ptr [rsp+37E0h+var_37B8], eax
0x1014673ff  mov     qword ptr [rsp+37E0h+var_37C0], rcx
0x101467404  mov     r9d, edi
0x101467407  mov     r8, rbx
0x10146740a  xor     edx, edx
0x10146740c  mov     edi, 1
0x101467411  mov     ecx, edi
0x101467413  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x101467419  cmp     eax, 2
0x10146741c  jnz     loc_1014674A3
0x101467422  mov     rax, cs:qword_102ECFB00
0x101467429  cmp     [rax+38A8h], r14d
0x101467430  jnz     short loc_101467469
0x101467432  xor     ecx, ecx; bool
0x101467434  call    ?IsBoxAADEnabled@@YA_N_N@Z; IsBoxAADEnabled(bool)
0x101467439  test    al, al
0x10146743b  jnz     short loc_101467469
0x10146743d  lea     rax, aCreateLoginFro; "CREATE LOGIN FROM EXTERNAL PROVIDER"
0x101467444  mov     [rsp+37E0h+var_37B8], rax
0x101467449  mov     qword ptr [rsp+37E0h+var_37C0], 46h ; 'F'
0x101467452  mov     r9d, edi
0x101467455  lea     edx, [rdi+18h]
0x101467458  mov     ecx, 177h
0x10146745d  lea     r8d, [rdi+0Fh]
0x101467461  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101467467  jmp     short loc_1014674A3
0x101467469  call    cs:__imp_GetXdbServerGlobals
0x10146746f  cmp     [rax+2EC8h], r14d
0x101467476  jnz     short loc_1014674A0
0x101467478  call    ?IsVDWFrontendInstance@@YAHXZ; IsVDWFrontendInstance(void)
0x10146747d  test    eax, eax
0x10146747f  jnz     short loc_1014674A0
0x101467481  xor     ecx, ecx; bool
0x101467483  call    ?IsBoxAADEnabled@@YA_N_N@Z; IsBoxAADEnabled(bool)
0x101467488  test    al, al
0x10146748a  jnz     short loc_1014674A0
0x10146748c  mov     rax, cs:qword_102ECFB00
0x101467493  cmp     [rax+38A8h], r14d
0x10146749a  jz      loc_10146753A
0x1014674a0  mov     [rbp+36E0h+var_3750], edi
0x1014674a3  mov     rax, cs:qword_102ECFB00
0x1014674aa  cmp     [rax+38A8h], r14d
0x1014674b1  jz      loc_10146753A
0x1014674b7  cmp     cs:byte_102EDCA50, r14b
0x1014674be  jz      short loc_10146753A
0x1014674c0  cmp     cs:byte_102EF429C, r14b
0x1014674c7  jz      short loc_10146753A
0x1014674c9  mov     rdx, gs:58h
0x1014674d2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1014674d9  mov     ecx, [rax]
0x1014674db  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1014674e2  mov     eax, [rax]
0x1014674e4  add     rax, [rdx+rcx*8]
0x1014674e8  mov     rax, [rax]
0x1014674eb  mov     rcx, [rax+48h]
0x1014674ef  mov     rbx, [rcx+60h]
0x1014674f3  test    rbx, rbx
0x1014674f6  jz      short loc_10146753A
0x1014674f8  mov     dl, 2
0x1014674fa  mov     rcx, rbx
0x1014674fd  call    ?GetFeatureExtension@CPhysicalConnection@@QEBAPEAVCFeatureExtension@@W4EFeatureExtensionId@@@Z; CPhysicalConnection::GetFeatureExtension(EFeatureExtensionId)
0x101467502  test    rax, rax
0x101467505  jz      short loc_101467519
0x101467507  cmp     dword ptr [rbx+3DCh], 2
0x10146750e  jz      short loc_101467519
0x101467510  test    rax, rax
0x101467513  jz      short loc_101467519
0x101467515  mov     al, 1
0x101467517  jmp     short loc_10146751B
0x101467519  xor     al, al
0x10146751b  test    esi, esi
0x10146751d  jz      short loc_10146753A
0x10146751f  test    al, al
0x101467521  jz      short loc_10146753A
0x101467523  mov     r9d, edi
0x101467526  mov     edx, 39h ; '9'
0x10146752b  mov     ecx, 176h
0x101467530  lea     r8d, [rdx-29h]
0x101467534  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10146753a  call    cs:__imp_GetXdbServerGlobals
0x101467540  cmp     [rax+2EC8h], r14d
0x101467547  jnz     short loc_101467552
0x101467549  call    ?IsVDWFrontendInstance@@YAHXZ; IsVDWFrontendInstance(void)
0x10146754e  test    eax, eax
0x101467550  jz      short loc_101467599
0x101467552  mov     rax, [rbp+36E0h+var_3678]
0x101467556  mov     rax, [rax+48h]
0x10146755a  mov     ebx, dword ptr [rbp+36E0h+var_373C]
0x10146755d  test    byte ptr [rax+10Eh], 2
0x101467564  jnz     short loc_10146759C
0x101467566  test    ebx, ebx
0x101467568  jz      short loc_10146759C
0x10146756a  lea     rax, aCreateLoginFro_0; "CREATE LOGIN FROM WINDOWS"
0x101467571  mov     [rsp+37E0h+var_37B8], rax
0x101467576  mov     qword ptr [rsp+37E0h+var_37C0], 32h ; '2'
0x10146757f  mov     edx, 6
0x101467584  mov     ecx, 1A3h
0x101467589  lea     r9d, [rdx-1]
0x10146758d  lea     r8d, [rdx+0Ah]
0x101467591  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101467597  jmp     short loc_10146759C
0x101467599  mov     ebx, dword ptr [rbp+36E0h+var_373C]
0x10146759c  mov     rdi, [rbp+36E0h+var_3758]
0x1014675a0  lea     rdx, [rdi+8A8h]
0x1014675a7  mov     [rbp+36E0h+var_36C8], rdx
0x1014675ab  mov     ecx, [rdx]
0x1014675ad  mov     rax, [rdi+8A0h]
0x1014675b4  mov     qword ptr [rbp+36E0h+var_36E0], rax
0x1014675b8  mov     dword ptr [rbp+36E0h+var_36E0+8], ecx
0x1014675bb  mov     rax, [rbp+36E0h+var_3678]
0x1014675bf  mov     rax, [rax+48h]
0x1014675c3  test    byte ptr [rax+10Eh], 4
0x1014675ca  jz      loc_1014683B2
0x1014675d0  cmp     [rbp+36E0h+var_3750], r14d
0x1014675d4  jnz     loc_101467C37
0x1014675da  lea     r8, ??_7CAutoClearXVariant@@6B@; const CAutoClearXVariant::`vftable'
0x1014675e1  mov     [rbp+36E0h+var_3530], r8
0x1014675e8  movups  xmm1, cs:?tiWStringNotNull@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiWStringNotNull
0x1014675ef  movups  [rbp+36E0h+var_3508], xmm1
0x1014675f6  movups  xmm0, cs:xmmword_102F39950
0x1014675fd  movups  [rbp+36E0h+var_34F8], xmm0
0x101467604  mov     [rbp+36E0h+var_3526], r14w
0x10146760c  mov     [rbp+36E0h+var_3528], 3
0x101467613  movd    eax, xmm1
0x101467617  mov     byte ptr [rbp+36E0h+var_3508], al
0x10146761d  mov     [rbp+36E0h+var_3527], al
0x101467623  xorps   xmm0, xmm0
0x101467626  movdqa  [rbp+36E0h+var_3520], xmm0
0x10146762e  mov     [rbp+36E0h+var_3510], r14d
0x101467635  mov     rax, [rdi+8A0h]
0x10146763c  mov     qword ptr [rbp+36E0h+var_3520], rax
0x101467643  mov     eax, [rdx]
0x101467645  mov     qword ptr [rbp+36E0h+var_3520+8], rax
0x10146764c  mov     [rbp+36E0h+var_3528], 0
0x101467653  mov     rdx, r14
0x101467656  mov     rax, [rdi+8D0h]
0x10146765d  test    rax, rax
0x101467660  jz      short loc_10146766B
0x101467662  mov     rdx, [rax+8]
0x101467666  mov     ecx, [rax+10h]
0x101467669  jmp     short loc_10146766E
0x10146766b  mov     ecx, r14d
  ... truncated ...
```
