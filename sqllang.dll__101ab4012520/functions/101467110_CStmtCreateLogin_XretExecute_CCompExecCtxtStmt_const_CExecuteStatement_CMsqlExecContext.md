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
  __int64 v10; // rcx
  CDefaultCollation *v11; // r12
  const wchar_t *v12; // rbx
  __int64 v13; // rcx
  int v14; // edx
  int v15; // esi
  unsigned __int64 v16; // rdi
  __int64 v17; // rcx
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v19; // rbx
  bool v20; // al
  int v21; // ebx
  __int64 v22; // rdi
  int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rax
  unsigned int v26; // ecx
  __int64 v27; // rax
  const void *v28; // r15
  unsigned __int64 v29; // rbx
  struct IMemObj *v30; // r13
  unsigned __int8 *v31; // rsi
  int v32; // edi
  unsigned __int8 *v33; // rbx
  unsigned int v34; // esi
  unsigned int v35; // r15d
  __int64 v36; // rax
  __int64 v37; // r9
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdi
  size_t v41; // rsi
  void *v42; // rax
  __int64 v44; // r15
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 *v50; // rdi
  __int64 v51; // rsi
  unsigned int v52; // ebx
  unsigned int v53; // eax
  __int64 *v54; // rbx
  __int64 v55; // rdi
  unsigned int v56; // eax
  unsigned int v57; // esi
  bool v58; // di
  __int64 v59; // r13
  const wchar_t *v60; // r12
  unsigned __int64 v61; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  unsigned int v63; // eax
  __int64 v64; // rcx
  __int64 v65; // r8
  int v66; // ecx
  signed __int64 v67; // rdx
  __int64 v68; // rax
  __int64 v69; // rax
  int v70; // ecx
  __int64 v71; // rbx
  __int64 v72; // rax
  __m128i v73; // xmm6
  __int64 v74; // rax
  const wchar_t *v75; // rbx
  unsigned int v76; // r10d
  int v77; // ecx
  __int64 v78; // rax
  bool v79; // di
  const wchar_t **v80; // rdx
  int v81; // eax
  bool v82; // al
  __int64 v83; // rbx
  int v84; // eax
  char v85; // si
  __int64 v86; // rax
  __int64 v87; // rdi
  int v88; // r13d
  unsigned int v89; // ebx
  const wchar_t *v90; // rax
  __int64 v91; // rcx
  unsigned int v92; // ebx
  _WORD *v93; // rdi
  char *v94; // rdx
  unsigned int v95; // eax
  unsigned int v96; // edx
  __int64 v97; // r9
  unsigned int *v98; // rbx
  int v99; // esi
  unsigned int v100; // ebx
  __int64 v101; // r8
  __int64 v102; // rax
  _WORD *v103; // rbx
  int v104; // edi
  unsigned __int8 *v105; // rcx
  int v106; // eax
  unsigned int v107; // r12d
  unsigned __int64 v108; // rbx
  struct __crt_locale_pointers *v109; // rax
  __int64 v110; // rax
  unsigned __int64 v111; // rbx
  __int64 v112; // rdi
  struct __crt_locale_pointers *v113; // rax
  __int64 v114; // rax
  const wchar_t *v115; // rbx
  unsigned int v116; // eax
  __int64 v117; // r9
  struct __crt_locale_pointers *v118; // rax
  __int64 v119; // rax
  struct CLangInfo *langinfo; // rax
  unsigned int v121; // eax
  __int64 v122; // r8
  int v123; // ecx
  signed __int64 v124; // rdx
  __int64 v125; // rax
  __int64 v126; // rax
  const void *v127; // rbx
  __int64 v128; // r15
  unsigned __int8 v129; // cl
  __int64 v130; // rax
  unsigned __int16 *v131; // rsi
  __int64 v132; // rax
  unsigned int v133; // r13d
  __int64 v134; // rax
  bool v135; // di
  int v136; // ebx
  bool v137; // r12
  __int16 v138; // r8
  __int64 v139; // rax
  char v140; // r15
  const wchar_t *v141; // rdi
  unsigned __int64 v142; // rcx
  unsigned __int64 v143; // rbx
  __int64 v144; // rax
  char v145; // bl
  const wchar_t *v146; // rsi
  unsigned __int64 v147; // rcx
  unsigned __int64 v148; // rdi
  int v149; // r9d
  int v150; // ecx
  __int64 v151; // rax
  int v152; // esi
  struct IPwdPolicyManager *PwdPolicyManager; // rsi
  unsigned __int8 *v154; // rax
  struct IPwdPolicyManager *v155; // rbx
  struct IPwdPolicyManager *v156; // rcx
  int v157; // r8d
  unsigned int v158; // eax
  unsigned int v159; // ebx
  const wchar_t *v160; // rbx
  _DWORD *v161; // r15
  unsigned int v162; // r10d
  int v163; // ecx
  __int64 v164; // rax
  unsigned int v165; // esi
  bool v166; // di
  PDWORD SidSubAuthority; // rbx
  signed int LastError; // eax
  unsigned int v169; // ecx
  int v170; // eax
  bool v171; // al
  unsigned int v172; // eax
  __int64 v173; // r8
  int v174; // ecx
  signed __int64 v175; // rdx
  __int64 v176; // rax
  __int64 v177; // rdx
  __int64 v178; // rax
  int v179; // ecx
  __int64 v180; // rbx
  unsigned __int16 v181; // ax
  __int64 v182; // rax
  __int64 v183; // rbx
  __int64 v184; // rcx
  unsigned int v185; // ebx
  unsigned int v186; // eax
  __int64 v187; // r8
  int v188; // ecx
  signed __int64 v189; // rdx
  __int64 v190; // rax
  __int64 v191; // rdx
  __int64 v192; // rax
  int v193; // ecx
  __int64 v194; // rbx
  unsigned __int16 v195; // ax
  __int64 v196; // rax
  __int64 v197; // rdi
  __int64 v198; // rcx
  struct CSECGlobalCryptoContext *v199; // rsi
  __int64 v200; // rbx
  __int64 v201; // rax
  __int64 v202; // r8
  __int64 (__fastcall ***v203)(_QWORD); // r15
  const struct _GUID *v204; // rax
  __int64 v205; // rsi
  _QWORD *v206; // rbx
  _QWORD *v207; // rax
  __int64 v208; // rcx
  unsigned int v209; // r12d
  __int64 v210; // rbx
  unsigned int v211; // eax
  __int64 *v212; // rsi
  __int64 v213; // rbx
  __int64 v214; // rdi
  int v215; // eax
  __int64 v216; // rbx
  unsigned __int16 v217; // ax
  __int64 v218; // rax
  unsigned __int16 v219; // ax
  __int64 v220; // rbx
  __int64 v221; // rcx
  unsigned int v222; // esi
  bool v223; // di
  __int64 v224; // rdx
  __int64 v225; // r12
  __int64 v226; // rbx
  __int64 v227; // r13
  const wchar_t *v228; // r15
  unsigned int v229; // eax
  __int64 v230; // r8
  int v231; // ecx
  signed __int64 v232; // rdx
  __int64 v233; // rax
  const void *v234; // rbx
  __int64 v235; // rax
  int v236; // edi
  __int16 *v237; // rbx
  __int64 v238; // rax
  __int16 v239; // ax
  __int64 v240; // rax
  int v241; // ecx
  const wchar_t *v242; // rbx
  int *v243; // r12
  unsigned int v244; // r10d
  int v245; // ecx
  __int64 v246; // rax
  bool v247; // di
  int *v248; // rdx
  int v249; // eax
  bool v250; // al
  int v251; // [rsp+20h] [rbp-E0h]
  char v252[8]; // [rsp+20h] [rbp-E0h]
  char v253[8]; // [rsp+20h] [rbp-E0h]
  char v254[8]; // [rsp+20h] [rbp-E0h]
  int v255; // [rsp+20h] [rbp-E0h]
  char v256[8]; // [rsp+20h] [rbp-E0h]
  char v257[8]; // [rsp+20h] [rbp-E0h]
  char v258[8]; // [rsp+20h] [rbp-E0h]
  char v259[8]; // [rsp+20h] [rbp-E0h]
  char v260[8]; // [rsp+20h] [rbp-E0h]
  int v261; // [rsp+28h] [rbp-D8h]
  wchar_t *v262; // [rsp+28h] [rbp-D8h]
  wchar_t *v263; // [rsp+28h] [rbp-D8h]
  int v264; // [rsp+28h] [rbp-D8h]
  wchar_t *v265; // [rsp+28h] [rbp-D8h]
  wchar_t *v266; // [rsp+28h] [rbp-D8h]
  wchar_t *v267; // [rsp+28h] [rbp-D8h]
  wchar_t *v268; // [rsp+28h] [rbp-D8h]
  unsigned __int8 **v269; // [rsp+30h] [rbp-D0h]
  int v270; // [rsp+30h] [rbp-D0h]
  int v271; // [rsp+38h] [rbp-C8h]
  int v272; // [rsp+40h] [rbp-C0h]
  int v273; // [rsp+48h] [rbp-B8h]
  char v274; // [rsp+80h] [rbp-80h] BYREF
  char v275[7]; // [rsp+81h] [rbp-7Fh] BYREF
  __int64 v276; // [rsp+88h] [rbp-78h]
  unsigned int v277; // [rsp+90h] [rbp-70h]
  int v278; // [rsp+94h] [rbp-6Ch]
  int v279; // [rsp+98h] [rbp-68h]
  bool v280; // [rsp+9Ch] [rbp-64h] BYREF
  bool v281; // [rsp+9Dh] [rbp-63h] BYREF
  bool v282; // [rsp+9Eh] [rbp-62h] BYREF
  bool v283; // [rsp+9Fh] [rbp-61h] BYREF
  char v284; // [rsp+A0h] [rbp-60h] BYREF
  char v285; // [rsp+A1h] [rbp-5Fh]
  unsigned __int16 v286[2]; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 *v287; // [rsp+A8h] [rbp-58h]
  unsigned int MasterDbId; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v289[2]; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned __int16 v290[2]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int Size[3]; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v292; // [rsp+C8h] [rbp-38h] BYREF
  int v293; // [rsp+CCh] [rbp-34h]
  struct IPwdPolicyManager *v294; // [rsp+D0h] [rbp-30h]
  unsigned int v295; // [rsp+D8h] [rbp-28h] BYREF
  int v296; // [rsp+DCh] [rbp-24h]
  unsigned int v297[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int8 *v298; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v299; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v300; // [rsp+100h] [rbp+0h] BYREF
  int v301; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v302; // [rsp+114h] [rbp+14h] BYREF
  unsigned int *v303; // [rsp+118h] [rbp+18h] BYREF
  RPC_WSTR StringUuid; // [rsp+120h] [rbp+20h] BYREF
  int v305; // [rsp+128h] [rbp+28h] BYREF
  int v306; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v307; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v308; // [rsp+134h] [rbp+34h]
  char v309; // [rsp+138h] [rbp+38h]
  unsigned __int8 v310; // [rsp+139h] [rbp+39h]
  char v311; // [rsp+13Ah] [rbp+3Ah]
  int v312; // [rsp+13Ch] [rbp+3Ch]
  __int64 v313; // [rsp+140h] [rbp+40h]
  __int64 v314; // [rsp+148h] [rbp+48h] BYREF
  __int64 v315; // [rsp+150h] [rbp+50h] BYREF
  __int64 v316; // [rsp+158h] [rbp+58h] BYREF
  __int64 v317; // [rsp+160h] [rbp+60h] BYREF
  __int64 v318; // [rsp+168h] [rbp+68h]
  __int64 v319; // [rsp+170h] [rbp+70h] BYREF
  __int64 v320; // [rsp+178h] [rbp+78h]
  __int64 v321; // [rsp+180h] [rbp+80h] BYREF
  int v322; // [rsp+188h] [rbp+88h]
  __int64 v323; // [rsp+190h] [rbp+90h] BYREF
  int v324; // [rsp+198h] [rbp+98h]
  unsigned __int8 *v325[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v326; // [rsp+1B0h] [rbp+B0h]
  __int128 v327; // [rsp+1C0h] [rbp+C0h]
  __int128 v328; // [rsp+1D0h] [rbp+D0h]
  __int128 v329; // [rsp+1E0h] [rbp+E0h]
  void *v330; // [rsp+1F0h] [rbp+F0h]
  __int64 v331; // [rsp+200h] [rbp+100h]
  __int64 v332; // [rsp+208h] [rbp+108h]
  __int64 v333; // [rsp+210h] [rbp+110h] BYREF
  __int128 v334; // [rsp+220h] [rbp+120h] BYREF
  __int128 v335; // [rsp+230h] [rbp+130h]
  __int128 v336; // [rsp+240h] [rbp+140h]
  __int128 v337; // [rsp+250h] [rbp+150h]
  __int128 v338; // [rsp+260h] [rbp+160h]
  void *v339; // [rsp+270h] [rbp+170h]
  HCERTSTORE hCertStore[2]; // [rsp+280h] [rbp+180h] BYREF
  int v341; // [rsp+290h] [rbp+190h]
  __int64 v342; // [rsp+298h] [rbp+198h]
  PCCERT_CONTEXT pCertContext; // [rsp+2A0h] [rbp+1A0h]
  char v344; // [rsp+2A8h] [rbp+1A8h]
  void **v345; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v346[2]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int16 v347; // [rsp+2BAh] [rbp+1BAh]
  __int128 v348; // [rsp+2C0h] [rbp+1C0h]
  int v349; // [rsp+2D0h] [rbp+1D0h]
  __int128 v350; // [rsp+2D8h] [rbp+1D8h]
  __int128 v351; // [rsp+2E8h] [rbp+1E8h]
  void **v352; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v353[2]; // [rsp+308h] [rbp+208h] BYREF
  __int16 v354; // [rsp+30Ah] [rbp+20Ah]
  __int64 v355; // [rsp+310h] [rbp+210h]
  __int64 v356; // [rsp+318h] [rbp+218h]
  int v357; // [rsp+320h] [rbp+220h]
  __int128 v358; // [rsp+328h] [rbp+228h]
  __int128 v359; // [rsp+338h] [rbp+238h]
  _QWORD v360[3]; // [rsp+350h] [rbp+250h] BYREF
  int v361; // [rsp+368h] [rbp+268h]
  const wchar_t *v362; // [rsp+370h] [rbp+270h] BYREF
  unsigned int v363; // [rsp+378h] [rbp+278h]
  const wchar_t *v364; // [rsp+380h] [rbp+280h] BYREF
  int v365; // [rsp+388h] [rbp+288h]
  const wchar_t *v366; // [rsp+390h] [rbp+290h] BYREF
  int v367; // [rsp+398h] [rbp+298h]
  const wchar_t *v368; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v369; // [rsp+3A8h] [rbp+2A8h]
  const wchar_t *v370; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned int v371; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v372; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v373; // [rsp+3C8h] [rbp+2C8h]
  _WORD *v374; // [rsp+3D0h] [rbp+2D0h] BYREF
  int v375; // [rsp+3D8h] [rbp+2D8h]
  const wchar_t *v376; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned int v377; // [rsp+3E8h] [rbp+2E8h]
  __int64 v378; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned int v379; // [rsp+3F8h] [rbp+2F8h]
  void **v380; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v381[2]; // [rsp+408h] [rbp+308h] BYREF
  __int16 v382; // [rsp+40Ah] [rbp+30Ah]
  __int128 v383; // [rsp+410h] [rbp+310h]
  int v384; // [rsp+420h] [rbp+320h]
  __int128 v385; // [rsp+428h] [rbp+328h]
  __int128 v386; // [rsp+438h] [rbp+338h]
  __int64 v387; // [rsp+450h] [rbp+350h]
  GUID v388; // [rsp+460h] [rbp+360h] BYREF
  __m128i v389; // [rsp+470h] [rbp+370h] BYREF
  UUID v390; // [rsp+480h] [rbp+380h] BYREF
  GUID v391; // [rsp+490h] [rbp+390h] BYREF
  __int128 v392; // [rsp+4A0h] [rbp+3A0h] BYREF
  GUID v393; // [rsp+4B0h] [rbp+3B0h] BYREF
  GUID v394; // [rsp+4C0h] [rbp+3C0h] BYREF
  GUID v395; // [rsp+4D0h] [rbp+3D0h] BYREF
  GUID v396; // [rsp+4E0h] [rbp+3E0h] BYREF
  GUID v397; // [rsp+4F0h] [rbp+3F0h] BYREF
  GUID v398; // [rsp+500h] [rbp+400h] BYREF
  GUID v399; // [rsp+510h] [rbp+410h] BYREF
  GUID v400; // [rsp+520h] [rbp+420h] BYREF
  __int64 v401; // [rsp+530h] [rbp+430h]
  __int64 v402; // [rsp+538h] [rbp+438h]
  struct IPwdPolicyManager *v403; // [rsp+540h] [rbp+440h]
  _DWORD v404[6]; // [rsp+548h] [rbp+448h] BYREF
  void *v405; // [rsp+560h] [rbp+460h]
  _DWORD v406[6]; // [rsp+570h] [rbp+470h] BYREF
  void *v407; // [rsp+588h] [rbp+488h]
  _BYTE v408[24]; // [rsp+598h] [rbp+498h] BYREF
  __int64 v409; // [rsp+5B0h] [rbp+4B0h]
  _DWORD v410[6]; // [rsp+5C0h] [rbp+4C0h] BYREF
  void *v411; // [rsp+5D8h] [rbp+4D8h]
  _DWORD v412[6]; // [rsp+5E8h] [rbp+4E8h] BYREF
  void *v413; // [rsp+600h] [rbp+500h]
  _BYTE v414[24]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v415; // [rsp+628h] [rbp+528h]
  _DWORD v416[6]; // [rsp+638h] [rbp+538h] BYREF
  void *v417; // [rsp+650h] [rbp+550h]
  _BYTE v418[24]; // [rsp+660h] [rbp+560h] BYREF
  __int64 v419; // [rsp+678h] [rbp+578h]
  _DWORD v420[6]; // [rsp+688h] [rbp+588h] BYREF
  void *v421; // [rsp+6A0h] [rbp+5A0h]
  _BYTE v422[24]; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v423; // [rsp+6C8h] [rbp+5C8h]
  _BYTE v424[24]; // [rsp+6D8h] [rbp+5D8h] BYREF
  __int64 v425; // [rsp+6F0h] [rbp+5F0h]
  _BYTE v426[24]; // [rsp+700h] [rbp+600h] BYREF
  __int64 v427; // [rsp+718h] [rbp+618h]
  _DWORD v428[6]; // [rsp+728h] [rbp+628h] BYREF
  void *v429; // [rsp+740h] [rbp+640h]
  _BYTE v430[24]; // [rsp+750h] [rbp+650h] BYREF
  __int64 v431; // [rsp+768h] [rbp+668h]
  char v432[8]; // [rsp+780h] [rbp+680h] BYREF
  int v433; // [rsp+788h] [rbp+688h]
  int v434; // [rsp+790h] [rbp+690h]
  char **v435; // [rsp+798h] [rbp+698h]
  char *v436; // [rsp+7A0h] [rbp+6A0h]
  __int64 v437; // [rsp+7A8h] [rbp+6A8h]
  char *v438; // [rsp+7B0h] [rbp+6B0h] BYREF
  int v439; // [rsp+7B8h] [rbp+6B8h]
  int v440; // [rsp+7BCh] [rbp+6BCh]
  const wchar_t *v441; // [rsp+7C0h] [rbp+6C0h]
  __int64 v442; // [rsp+7C8h] [rbp+6C8h]
  const wchar_t *v443; // [rsp+7D0h] [rbp+6D0h]
  int v444; // [rsp+7D8h] [rbp+6D8h]
  int v445; // [rsp+7DCh] [rbp+6DCh]
  char v446; // [rsp+7E0h] [rbp+6E0h] BYREF
  __int64 v447; // [rsp+9D0h] [rbp+8D0h]
  __int64 v448; // [rsp+9D8h] [rbp+8D8h]
  char v449; // [rsp+9E0h] [rbp+8E0h] BYREF
  char v450[8]; // [rsp+9F0h] [rbp+8F0h] BYREF
  int v451; // [rsp+9F8h] [rbp+8F8h]
  int v452; // [rsp+A00h] [rbp+900h]
  char **v453; // [rsp+A08h] [rbp+908h]
  char *v454; // [rsp+A10h] [rbp+910h]
  __int64 v455; // [rsp+A18h] [rbp+918h]
  char *v456; // [rsp+A20h] [rbp+920h] BYREF
  int v457; // [rsp+A28h] [rbp+928h]
  int v458; // [rsp+A2Ch] [rbp+92Ch]
  const wchar_t *v459; // [rsp+A30h] [rbp+930h]
  __int64 v460; // [rsp+A38h] [rbp+938h]
  const wchar_t *v461; // [rsp+A40h] [rbp+940h]
  int v462; // [rsp+A48h] [rbp+948h]
  int v463; // [rsp+A4Ch] [rbp+94Ch]
  char v464; // [rsp+A50h] [rbp+950h] BYREF
  __int64 v465; // [rsp+C40h] [rbp+B40h]
  __int64 v466; // [rsp+C48h] [rbp+B48h]
  char v467; // [rsp+C50h] [rbp+B50h] BYREF
  char v468[8]; // [rsp+C60h] [rbp+B60h] BYREF
  int v469; // [rsp+C68h] [rbp+B68h]
  int v470; // [rsp+C70h] [rbp+B70h]
  char **v471; // [rsp+C78h] [rbp+B78h]
  char *v472; // [rsp+C80h] [rbp+B80h]
  __int64 v473; // [rsp+C88h] [rbp+B88h]
  char *v474; // [rsp+C90h] [rbp+B90h] BYREF
  int v475; // [rsp+C98h] [rbp+B98h]
  int v476; // [rsp+C9Ch] [rbp+B9Ch]
  const wchar_t *v477; // [rsp+CA0h] [rbp+BA0h]
  __int64 v478; // [rsp+CA8h] [rbp+BA8h]
  const wchar_t *v479; // [rsp+CB0h] [rbp+BB0h]
  int v480; // [rsp+CB8h] [rbp+BB8h]
  int v481; // [rsp+CBCh] [rbp+BBCh]
  char v482; // [rsp+CC0h] [rbp+BC0h] BYREF
  __int64 v483; // [rsp+EB0h] [rbp+DB0h]
  __int64 v484; // [rsp+EB8h] [rbp+DB8h]
  char v485; // [rsp+EC0h] [rbp+DC0h] BYREF
  char v486[8]; // [rsp+ED0h] [rbp+DD0h] BYREF
  int v487; // [rsp+ED8h] [rbp+DD8h]
  int v488; // [rsp+EE0h] [rbp+DE0h]
  char **v489; // [rsp+EE8h] [rbp+DE8h]
  char *v490; // [rsp+EF0h] [rbp+DF0h]
  __int64 v491; // [rsp+EF8h] [rbp+DF8h]
  char *v492; // [rsp+F00h] [rbp+E00h] BYREF
  int v493; // [rsp+F08h] [rbp+E08h]
  int v494; // [rsp+F0Ch] [rbp+E0Ch]
  const wchar_t *v495; // [rsp+F10h] [rbp+E10h]
  __int64 v496; // [rsp+F18h] [rbp+E18h]
  const wchar_t *v497; // [rsp+F20h] [rbp+E20h]
  int v498; // [rsp+F28h] [rbp+E28h]
  int v499; // [rsp+F2Ch] [rbp+E2Ch]
  char v500; // [rsp+F30h] [rbp+E30h] BYREF
  __int64 v501; // [rsp+1120h] [rbp+1020h]
  __int64 v502; // [rsp+1128h] [rbp+1028h]
  char v503; // [rsp+1130h] [rbp+1030h] BYREF
  UUID Uuid; // [rsp+1140h] [rbp+1040h] BYREF
  GUID pguid; // [rsp+1150h] [rbp+1050h] BYREF
  GUID v506; // [rsp+1160h] [rbp+1060h] BYREF
  char v507[16]; // [rsp+1170h] [rbp+1070h] BYREF
  int v508; // [rsp+1180h] [rbp+1080h]
  char v509[16]; // [rsp+1188h] [rbp+1088h] BYREF
  char v510[24]; // [rsp+1198h] [rbp+1098h] BYREF
  _BYTE v511[6992]; // [rsp+11B0h] [rbp+10B0h] BYREF
  GUID v512; // [rsp+2D00h] [rbp+2C00h] BYREF
  unsigned __int8 v513[16]; // [rsp+2D10h] [rbp+2C10h] BYREF
  __int128 v514; // [rsp+2D20h] [rbp+2C20h]
  __int128 v515; // [rsp+2D30h] [rbp+2C30h]
  __int128 v516; // [rsp+2D40h] [rbp+2C40h]
  __int128 v517; // [rsp+2D50h] [rbp+2C50h]
  int v518; // [rsp+2D60h] [rbp+2C60h]
  char v519; // [rsp+2D64h] [rbp+2C64h]
  unsigned __int8 pSid[96]; // [rsp+2D70h] [rbp+2C70h] BYREF
  wchar_t v521[136]; // [rsp+2DD0h] [rbp+2CD0h] BYREF
  unsigned __int8 v522[96]; // [rsp+2EE0h] [rbp+2DE0h] BYREF
  _BYTE v523[96]; // [rsp+2F40h] [rbp+2E40h] BYREF
  wchar_t v524[40]; // [rsp+2FA0h] [rbp+2EA0h] BYREF
  _BYTE v525[96]; // [rsp+2FF0h] [rbp+2EF0h] BYREF
  wchar_t v526[136]; // [rsp+3050h] [rbp+2F50h] BYREF
  _WORD v527[3]; // [rsp+3160h] [rbp+3060h] BYREF
  _BYTE v528[506]; // [rsp+3166h] [rbp+3066h] BYREF
  wchar_t v529[136]; // [rsp+3360h] [rbp+3260h] BYREF
  wchar_t v530[136]; // [rsp+3470h] [rbp+3370h] BYREF
  unsigned __int8 Src[512]; // [rsp+3580h] [rbp+3480h] BYREF

  v387 = -2;
  v332 = a4;
  v320 = a3;
  v318 = a2;
  v276 = a1;
  v7 = *(_QWORD *)(a2 + 120);
  *(_QWORD *)&Size[1] = *(_QWORD *)(a4 + 120);
  MasterDbId = GetMasterDbId();
  v287 = *(__int64 **)(a3 + 56);
  v8 = 0;
  v9 = 0;
  pguid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  Uuid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  CoCreateGuid(&pguid);
  if ( ((*(_BYTE *)(*(_QWORD *)(a2 + 72) + 270LL) & 4) != 0
     || (*(_DWORD *)(GetXdbServerGlobals(v10) + 11976) || (unsigned int)IsVDWFrontendInstance())
     && (*(_BYTE *)(*(_QWORD *)(a2 + 72) + 270LL) & 2) == 0)
    && (qword_102F21DB4 & 4) != 0 )
  {
    v433 = 196608;
    v434 = 0;
    v435 = &v438;
    v436 = &v446;
    v447 = 0;
    v437 = 0;
    v448 = 0;
    v438 = &v449;
    v439 = 16;
    v440 = 2;
    v441 = L"CREATE";
    v442 = 12;
    v443 = L"START";
    v444 = 10;
    v445 = 1;
    XeCloudPkg::azuresqldb_login_ddl::Publish((XeCloudPkg::azuresqldb_login_ddl *)v432);
  }
  v11 = (CDefaultCollation *)CDefaultCollation::PDCServer();
  v12 = 0;
  v13 = *(_QWORD *)(a1 + 2328);
  if ( v13 )
  {
    v12 = *(const wchar_t **)(v13 + 8);
    v14 = *(_DWORD *)(v13 + 16);
  }
  else
  {
    v14 = 0;
  }
  v15 = 0;
  v296 = 0;
  v278 = 0;
  *(_DWORD *)v286 = 0;
  v279 = 0;
  v277 = 0;
  v16 = (unsigned __int64)v14 >> 1;
  if ( CompareStringWEnglishNoCase(1u, 0, v12, v16, CStmtCreateLogin::SqlLogin, 3) == 2 )
  {
    v15 = 1;
    v296 = 1;
  }
  else if ( CompareStringWEnglishNoCase(1u, 0, v12, v16, CStmtCreateLogin::NtLogin, 2) == 2 )
  {
    *(_DWORD *)v286 = 1;
  }
  else if ( CompareStringWEnglishNoCase(1u, 0, v12, v16, CStmtCreateLogin::CertLogin, 11) == 2 )
  {
    v278 = 1;
  }
  else if ( CompareStringWEnglishNoCase(1u, 0, v12, v16, CStmtCreateLogin::AKeyLogin, 14) == 2 )
  {
    v279 = 1;
  }
  else if ( CompareStringWEnglishNoCase(1u, 0, v12, v16, CStmtCreateLogin::ExternalLogin, 8) == 2 )
  {
    if ( *(_DWORD *)(qword_102ECFB00 + 14504) || IsBoxAADEnabled(0) )
    {
      if ( !*(_DWORD *)(GetXdbServerGlobals(v17) + 11976)
        && !(unsigned int)IsVDWFrontendInstance()
        && !IsBoxAADEnabled(0)
        && !*(_DWORD *)(qword_102ECFB00 + 14504) )
      {
        goto LABEL_38;
      }
      v277 = 1;
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
        v17 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 72LL);
        v19 = *(_QWORD *)(v17 + 96);
        if ( v19 )
        {
          LOBYTE(ThreadLocalStoragePointer) = 2;
          v20 = CPhysicalConnection::GetFeatureExtension(*(_QWORD *)(v17 + 96), ThreadLocalStoragePointer)
             && *(_DWORD *)(v19 + 988) != 2;
          if ( v15 && v20 )
            ex_raise(374, 57, 16, 1);
        }
      }
    }
  }
LABEL_38:
  if ( *(_DWORD *)(GetXdbServerGlobals(v17) + 11976) || (unsigned int)IsVDWFrontendInstance() )
  {
    v21 = *(_DWORD *)v286;
    if ( (*(_BYTE *)(*(_QWORD *)(v318 + 72) + 270LL) & 2) == 0 && *(_DWORD *)v286 )
      ex_raise(419, 6, 16, 5, 50, L"CREATE LOGIN FROM WINDOWS");
  }
  else
  {
    v21 = *(_DWORD *)v286;
  }
  v22 = v276;
  v303 = (unsigned int *)(v276 + 2216);
  v23 = *(_DWORD *)(v276 + 2216);
  *(_QWORD *)&v300 = *(_QWORD *)(v276 + 2208);
  DWORD2(v300) = v23;
  if ( (*(_BYTE *)(*(_QWORD *)(v318 + 72) + 270LL) & 4) != 0 )
  {
    if ( !v277 )
    {
      v345 = &CAutoClearXVariant::`vftable';
      v350 = CTypeInfo::tiWStringNotNull;
      v351 = xmmword_102F39950;
      v347 = 0;
      v346[0] = 3;
      LOBYTE(v350) = _mm_cvtsi128_si32(CTypeInfo::tiWStringNotNull);
      v346[1] = v350;
      v348 = 0;
      v349 = 0;
      *(_QWORD *)&v348 = *(_QWORD *)(v276 + 2208);
      *((_QWORD *)&v348 + 1) = *(unsigned int *)(v276 + 2216);
      v346[0] = 0;
      v24 = 0;
      v25 = *(_QWORD *)(v276 + 2256);
      if ( v25 )
      {
        v24 = *(_QWORD *)(v25 + 8);
        v26 = *(_DWORD *)(v25 + 16);
      }
      else
      {
        v26 = 0;
      }
      v352 = &CAutoClearXVariant::`vftable';
      v358 = CTypeInfo::tiWStringNotNull;
      v359 = xmmword_102F39950;
      v354 = 0;
      LOBYTE(v358) = _mm_cvtsi128_si32(CTypeInfo::tiWStringNotNull);
      v353[1] = v358;
      v357 = 0;
      v355 = v24;
      v356 = v26;
      v353[0] = 0;
      v380 = &CAutoClearXVariant::`vftable';
      v385 = CTypeInfo::tiI4NotNull;
      v386 = xmmword_102F21D40;
      v382 = 0;
      LOBYTE(v385) = _mm_cvtsi128_si32(CTypeInfo::tiI4NotNull);
      v381[1] = v385;
      v383 = 0;
      v384 = 0;
      LODWORD(v383) = 0;
      v381[0] = 0;
      v298 = 0;
      v295 = 0;
      memset_0(Src, 0, sizeof(Src));
      Size[0] = 512;
      v27 = *(_QWORD *)(v276 + 2304);
      if ( v27 )
      {
        v28 = *(const void **)(v27 + 8);
        v29 = *(unsigned int *)(v27 + 16);
        if ( (unsigned int)v29 > 0x55 )
          ex_raise(154, 19, 16, 1);
        v30 = *(struct IMemObj **)&Size[1];
        v31 = (unsigned __int8 *)operator new[](
                                   v29,
                                   *(struct IMemObj **)&Size[1],
                                   "sql\\ntdbms\\msql\\security\\src\\secddl.cpp",
                                   6273,
                                   3u);
        if ( v31 )
          operator delete[](0);
        v298 = v31;
        memcpy_s(v31, v29, v28, v29);
        v295 = v29;
      }
      else
      {
        v30 = *(struct IMemObj **)&Size[1];
      }
      v297[0] = 0;
      CGatewaySqlLoginsTable::CreateLogin(
        *(const struct CCompExecCtxtBasic **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset),
        0,
        (struct CXVariant *const)v346,
        (struct CXVariant *const)v353,
        0,
        (struct CXVariant *const)v381,
        &v298,
        &v295,
        Src,
        Size,
        v297);
      v32 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                          + SystemThread_TlsIndex)
                                                        + SystemThread_TlsOffset)
                                            + 80LL)
                                + 8LL);
      v33 = v298;
      v34 = v295;
      v35 = v297[0];
      if ( byte_102EDCB8A )
      {
        v251 = v32;
        v36 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64))(*v287 + 328))(v287, &v300, 1);
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 256LL))(v36);
        LOBYTE(v251) = 1;
        LOBYTE(v37) = 1;
        v38 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int8 *, _QWORD, __int64, int, int))(*v287 + 344))(
                v287,
                v33,
                v34,
                v37,
                v251,
                v32);
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 256LL))(v38);
        v39 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*v287 + 336))(v287, v35, 1);
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 256LL))(v39);
      }
      v388 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v40 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int8 *, _QWORD, _DWORD, unsigned int, int, GUID *))(*v287 + 360))(
              v287,
              &v300,
              v33,
              v34,
              0,
              v35,
              v32,
              &v388);
      if ( !v40 )
        utassert_fail(1u, "imLgn != nullptr", "secddl.cpp", 6376, 0);
      v362 = L"master";
      v363 = dword_102F1BB98;
      (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v40 + 288LL))(v40, &v362);
      v364 = L"us_english";
      v365 = 20;
      (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v40 + 296LL))(v40, &v364);
      v334 = 0;
      v335 = 0;
      v336 = 0;
      v337 = 0;
      v338 = 0;
      v339 = 0;
      utgettime((struct SQLDATEBASE *)&v319, 1, 0);
      DWORD1(v334) = Size[0];
      v41 = Size[0];
      v42 = operator new[](Size[0], v30, "sql\\ntdbms\\msql\\security\\src\\secddl.cpp", 6388, 3u);
      *((_QWORD *)&v334 + 1) = v42;
      if ( v41 )
      {
        if ( v42 )
        {
          memmove(v42, Src, v41);
        }
        else
        {
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
      }
      *(_QWORD *)&v335 = v319;
      LOBYTE(v334) = v334 & 0xFC;
      (*(void (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v40 + 312LL))(v40, 1, &v334);
      if ( (qword_102F21DB4 & 4) != 0 )
      {
        v451 = 196608;
        v452 = 0;
        v453 = &v456;
        v454 = &v464;
        v465 = 0;
        v455 = 0;
        v466 = 0;
        v456 = &v467;
        v457 = 16;
        v458 = 2;
        v459 = L"CREATE";
        v460 = 12;
        v461 = L"FINISH";
        v462 = 12;
        v463 = 1;
        XeCloudPkg::azuresqldb_login_ddl::Publish((XeCloudPkg::azuresqldb_login_ddl *)v450);
      }
      *(_BYTE *)(v320 + 176) |= 0x10u;
      operator delete[](*((void **)&v334 + 1));
      operator delete[](*((void **)&v338 + 1));
      operator delete[](v339);
      if ( HIDWORD(v336) )
      {
        do
          operator delete[](*(void **)(*((_QWORD *)&v337 + 1) + 8LL * v8++));
        while ( v8 < HIDWORD(v336) );
      }
      operator delete[]((void *)v337);
      operator delete[](*((void **)&v337 + 1));
      operator delete[](v33);
      CAutoClearXVariant::~CAutoClearXVariant(&v380);
      CAutoClearXVariant::~CAutoClearXVariant(&v352);
      CAutoClearXVariant::~CAutoClearXVariant(&v345);
      return 0;
    }
    v292 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                         + SystemThread_TlsIndex)
                                                       + SystemThread_TlsOffset)
                                           + 80LL)
                               + 8LL);
    v44 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*v287 + 56))(
            v287,
            v292,
            0,
            0,
            0,
            0);
    v366 = L"firewall_rules";
    v367 = 28;
    LOBYTE(v45) = 1;
    v46 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v44 + 216LL))(v44, 4, 0, v45);
    LOBYTE(v47) = 1;
    if ( !(*(__int64 (__fastcall **)(__int64, const wchar_t **, __int64, _QWORD, _DWORD, _DWORD, _BYTE))(*(_QWORD *)v46 + 32LL))(
            v46,
            &v366,
            v47,
            0,
            0,
            0,
            0) )
      ex_raise(50, 1, 16, 15);
    v368 = L"loginmanager";
    v369 = 24;
    LOBYTE(v48) = 1;
    v49 = (*(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD, __int64))(*(_QWORD *)v44 + 224LL))(
            v44,
            &v368,
            0,
            v48);
    v50 = *(__int64 **)(*(_QWORD *)(v318 + 120) + 264LL);
    v51 = *v50;
    v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
    v53 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD, _QWORD))(v51 + 480))(v50, v53, v52)
      && !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v318 + 120) + 264LL) + 152LL))(*(_QWORD *)(*(_QWORD *)(v318 + 120) + 264LL)) )
    {
      v54 = *(__int64 **)(*(_QWORD *)(v318 + 120) + 264LL);
      v55 = *v54;
      v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD))(v55 + 496))(v54, v56) )
        ex_raise(152, 47, 16, 105);
    }
    v57 = 85;
    MasterDbId = 85;
    v58 = 0;
    v274 = 0;
    v275[0] = 0;
    v59 = *(_QWORD *)(v276 + 2304);
    v315 = *(_QWORD *)(v276 + 2256);
    v319 = *(_QWORD *)(v276 + 2416);
    v317 = *(_QWORD *)(v276 + 2312);
    v316 = *(_QWORD *)(v276 + 2320);
    v314 = *(_QWORD *)(v276 + 2424);
    v60 = 0;
    v61 = (unsigned __int64)*(unsigned int *)(v276 + 2216) >> 1;
    DefaultLocale = GetDefaultLocale();
    StringCchPrintf_lW(v526, 0x81u, L"%.*s", DefaultLocale, v61, *(_QWORD *)(v276 + 2208));
    v63 = *v303;
    v64 = v276;
    v65 = *(_QWORD *)(v276 + 2208);
    if ( v65 && v63 )
    {
      v66 = 0;
      v67 = (unsigned __int64)v63 >> 1;
      if ( v67 )
      {
        v68 = 0;
        while ( *(_WORD *)(v65 + 2 * v68) != 92 )
        {
          ++v66;
          if ( ++v68 >= v67 )
            goto LABEL_89;
        }
        if ( v66 >= 0 )
          ex_raise(150, 6, 16, 5, v526);
      }
LABEL_89:
      v64 = v276;
    }
    if ( !v59 && !v319 && !v317 && !v316 && !v315 )
    {
      if ( !v314 )
        goto LABEL_101;
      if ( byte_102EDCA59 )
      {
        v69 = *(_QWORD *)(v64 + 2424);
        if ( v69 )
        {
          v60 = *(const wchar_t **)(v69 + 8);
          v70 = *(_DWORD *)(v69 + 16);
        }
        else
        {
          v70 = 0;
        }
        LODWORD(v299) = v70;
LABEL_101:
        if ( byte_102EDCA55 )
        {
          v71 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                    + SystemThread_TlsIndex)
                                                  + SystemThread_TlsOffset)
                                      + 120LL)
                          + 264LL);
          v72 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v71 + 568LL))(v71, v44, 1, 0);
          if ( v72 )
          {
            v73 = *(__m128i *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v72 + 608LL))(v72, v509);
            Uuid = (UUID)v73;
          }
          else
          {
            v74 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD))(*(_QWORD *)v71 + 576LL))(
                    v71,
                    v287,
                    1,
                    0);
            if ( v74 )
            {
              v73 = *(__m128i *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v74 + 80LL))(v74, v510);
              Uuid = (UUID)v73;
            }
            else
            {
              v73 = (__m128i)Uuid;
            }
          }
          if ( v73.m128i_i64[0] != *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
            || _mm_srli_si128(v73, 8).m128i_u64[0] != *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
          {
LABEL_111:
            v75 = *(const wchar_t **)(v276 + 2208);
            v76 = *(_DWORD *)(v276 + 2216);
            if ( !v75 )
              goto LABEL_117;
            if ( !v76 )
              goto LABEL_117;
            v77 = 0;
            if ( !((unsigned __int64)v76 >> 1) )
              goto LABEL_117;
            v78 = 0;
            while ( v75[v78] != 92 )
            {
              ++v77;
              if ( ++v78 >= (__int64)((unsigned __int64)v76 >> 1) )
                goto LABEL_117;
            }
            if ( v77 >= 0 && v76 - 1 != v77 )
            {
              v79 = v60 != 0;
              if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                     + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + SystemThread_TlsIndex))
                                         + 72LL)
                             + 270LL)
                  & 4) == 0 )
              {
                v289[0] = 85;
                v81 = FGetSidFromNt(v75, v76, v522, v289, 85, 1);
                v58 = v81 != 0;
                if ( v81 )
                  v82 = v275[0];
                else
                  v82 = (unsigned int)FGetSidFromNt(v75, *(unsigned int *)(v276 + 2216), v522, v289, 71, 1) != 0;
                if ( !v58 && !v82 )
                  ex_raise(154, 1, 16, 1, v526);
                v57 = v289[0];
                goto LABEL_135;
              }
            }
            else
            {
LABEL_117:
              v79 = v60 != 0;
              if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
                ex_raise(154, 7, 16, 1, v526);
            }
            v389 = v73;
            v80 = &v299;
            if ( v60 )
              v75 = v60;
            else
              v80 = (const wchar_t **)(v276 + 2216);
            LOBYTE(v261) = v79;
            LookupFederatedPrincipal(v75, v80, v526, 0, &pguid, v261, v522, &MasterDbId, &v274, v275, &v389);
            v57 = MasterDbId;
            v58 = v274;
LABEL_135:
            v390 = Uuid;
            v83 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int8 *, _QWORD, unsigned int, _DWORD, unsigned int, UUID *))(*v287 + 360))(
                    v287,
                    &v300,
                    v522,
                    v57,
                    8 - (unsigned int)v58,
                    0,
                    v292,
                    &v390);
            if ( !v83 )
              ex_raise(150, 25, 16, 8, v526);
            v370 = L"master";
            v371 = dword_102F1BB98;
            (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v83 + 288LL))(v83, &v370);
            v372 = L"us_english";
            v373 = 20;
            (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v83 + 296LL))(v83, &v372);
            if ( (qword_102F21DB4 & 4) != 0 )
            {
              v469 = 196608;
              v470 = 0;
              v471 = &v474;
              v472 = &v482;
              v483 = 0;
              v473 = 0;
              v484 = 0;
              v474 = &v485;
              v475 = 16;
              v476 = 2;
              v477 = L"CREATE";
              v478 = 12;
              v479 = L"FINISH_FEDAUTH_LOGIN";
              v480 = 40;
              v481 = 1;
              XeCloudPkg::azuresqldb_login_ddl::Publish((XeCloudPkg::azuresqldb_login_ddl *)v468);
            }
            *(_BYTE *)(v320 + 176) |= 0x10u;
            return 0;
          }
          StringUuid = 0;
          AzureActiveDirectoryService::GetTenantId(*(_QWORD *)&Size[1], &StringUuid);
          UuidFromStringW(StringUuid, &Uuid);
          operator delete[](StringUuid);
        }
        v73 = (__m128i)Uuid;
        goto LABEL_111;
      }
    }
    ex_raise(331, 99, 16, 1);
    goto LABEL_135;
  }
  v285 = 1;
  if ( v15 )
  {
    v84 = 19539;
  }
  else if ( v278 )
  {
    v84 = 19523;
  }
  else
  {
    v84 = (v21 ^ 1) + 19543;
    if ( v279 )
      v84 = 19521;
  }
  v293 = v84;
  v308 = MasterDbId;
  v309 = 0;
  v313 = 0;
  v85 = ISECManager::CheckPermRule(1380142168, *(_QWORD *)&Size[1], v287, MasterDbId, 0, 0, -1, v84, 1, 1, 0, 0);
  v310 = v85;
  v307 = 1380142168;
  v312 = v293;
  v311 = 1;
  if ( v85 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v7 + 264) + 232LL))(*(_QWORD *)(v7 + 264), 1);
    v88 = *(_DWORD *)v286;
  }
  else
  {
    v391 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    ISECManager::CheckPermRuleAuditOnly(1380142168, 0, v287, MasterDbId, 0, 0, v293, 0, 0, &v391, 0, 0, 0, -1);
    v309 = 1;
    v86 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v7 + 264) + 232LL))(*(_QWORD *)(v7 + 264), 1);
    v87 = v86;
    v88 = *(_DWORD *)v286;
    if ( *(_DWORD *)v286 )
    {
      v89 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 32LL))(v86, 1);
      v90 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 24LL))(v87, 1);
      v22 = v276;
      if ( CDefaultCollation::FEqW(v11, *(const wchar_t **)(v276 + 2208), *v303, v90, v89) )
      {
        v85 = 1;
        v285 = 0;
      }
    }
    else
    {
      v22 = v276;
    }
  }
  if ( (unsigned int)CSECCertParams::GetCertType(*(_QWORD *)(v22 + 2208), *(unsigned int *)(v22 + 2216), MasterDbId) != 11 )
  {
    v92 = *(_DWORD *)(v22 + 2216);
    v93 = *(_WORD **)(v22 + 2208);
    v94 = (char *)&CSECCertParams::m_rgCertParams + 48 * (int)CSECCertParams::GetCertType(v93, v92, MasterDbId);
    if ( *(_DWORD *)v94 == 11 && v92 && *v93 == 35
      || !CSECCertParams::FCanDoActionInMode(
            (int)(*((_DWORD *)v94 + 10) << 31) >> 31,
            (const struct CSECCertParams::_SECCertParams *)v94,
            MasterDbId) )
    {
      v22 = v276;
      v95 = *(_DWORD *)(v276 + 2216);
      v96 = v95;
      v97 = *(_QWORD *)(v276 + 2208);
LABEL_164:
      v99 = v296;
      if ( v296 )
      {
        AuditSecurityEvent(104, 1, 0, *(wchar_t **)(v22 + 2208), v95, 0, 0, 0, 0);
        v100 = v277;
      }
      else if ( v88 )
      {
        AuditSecurityEvent(105, 1, 0, (wchar_t *)v97, v95, 0, 0, 0, 0);
        v100 = v277;
      }
      else
      {
        v100 = v277;
        if ( v277 )
          AuditSecurityEvent(104, 1, 0, (wchar_t *)v97, v96, 0, 0, 0, 0);
      }
      ex_raise(152, 47, 16, 1);
      v96 = *(_DWORD *)(v22 + 2216);
      v97 = *(_QWORD *)(v22 + 2208);
      goto LABEL_172;
    }
    v22 = v276;
  }
  v96 = *(_DWORD *)(v22 + 2216);
  v97 = *(_QWORD *)(v22 + 2208);
  v95 = v96;
  if ( v96 > 4 )
  {
    _mm_lfence();
    v98 = (unsigned int *)(v22 + 2216);
    if ( CSystemComponent::GetComponentByName((const wchar_t *)(v97 + 4), v96 - 4) )
    {
      v95 = *v98;
      v96 = *v98;
      v97 = *(_QWORD *)(v22 + 2208);
      goto LABEL_164;
    }
    v96 = *v98;
    v95 = *v98;
    v97 = *(_QWORD *)(v22 + 2208);
  }
  if ( !v85 )
    goto LABEL_164;
  v99 = v296;
  v100 = v277;
LABEL_172:
  if ( v99 )
    goto LABEL_176;
  if ( v88 )
  {
    AuditSecurityEvent(105, 1, 1, (wchar_t *)v97, v96, 0, 0, 0, 0);
    goto LABEL_177;
  }
  if ( v100 )
LABEL_176:
    AuditSecurityEvent(104, 1, 1, (wchar_t *)v97, v96, 0, 0, 0, 0);
LABEL_177:
  v392 = v300;
  CStmtOwnerMgmt::ErrorOutIfCloudLifterUnchangeablePrincipal(v91, &v392, 13105);
  v102 = *(_QWORD *)(v22 + 2368);
  if ( v102 )
  {
    v103 = *(_WORD **)(v102 + 8);
    v104 = *(_DWORD *)(v102 + 16);
    v374 = v103;
    v375 = v104;
    LOBYTE(v101) = 1;
    v105 = (unsigned __int8 *)(*(__int64 (__fastcall **)(__int64 *, _WORD **, __int64))(*v287 + 168))(v287, &v374, v101);
    v298 = v105;
    if ( !v105 || v104 && *v103 == 35 )
    {
      LODWORD(v269) = v104;
      LODWORD(v262) = 13131;
      *(_DWORD *)v252 = 13118;
      ex_raise(151, 51, 16, 1, *(_QWORD *)v252, v262, v269, v103);
      v105 = v298;
    }
    v106 = (*(__int64 (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v105 + 8LL))(v105);
    LOBYTE(v273) = 0;
    LOBYTE(v272) = 1;
    if ( !(unsigned __int8)ISECManager::CheckPermRule(
                             1480805464,
                             *(_QWORD *)&Size[1],
                             v287,
                             MasterDbId,
                             0,
                             v106,
                             -1,
                             0,
                             v272,
                             v273,
                             0,
                             0) )
    {
      LODWORD(v269) = v104;
      LODWORD(v263) = 13131;
      *(_DWORD *)v253 = 13118;
      ex_raise(151, 51, 16, 1, *(_QWORD *)v253, v263, v269, v103);
    }
    v22 = v276;
  }
  else
  {
    v298 = 0;
  }
  v107 = v277;
  v108 = (unsigned __int64)*(unsigned int *)(v22 + 2216) >> 1;
  v109 = GetDefaultLocale();
  StringCchPrintf_lW(v521, 0x81u, L"%.*s", v109, v108, *(_QWORD *)(v22 + 2208));
  v110 = *(_QWORD *)(v22 + 2312);
  if ( v110 && (v299 = *(const wchar_t **)(v110 + 8), v111 = *(unsigned int *)(v110 + 16), (Size[0] = v111) != 0) )
  {
    v112 = (*(__int64 (__fastcall **)(__int64 *))(*v287 + 72))(v287);
    v402 = v112;
    if ( !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v112 + 8LL))(
            v112,
            v299,
            (unsigned int)v111) )
    {
      v113 = GetDefaultLocale();
      StringCchPrintf_lW(v529, 0x81u, L"%.*s", v113, v111 >> 1, v299);
      ex_raise(150, 10, 16, 1, v529);
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v112 + 120LL))(v112, 1);
    v22 = v276;
  }
  else
  {
    v299 = L"master";
    Size[0] = dword_102F1BB98;
  }
  v114 = *(_QWORD *)(v22 + 2320);
  if ( v114
    && (v115 = *(const wchar_t **)(v114 + 8), *(_QWORD *)v297 = v115, v116 = *(_DWORD *)(v114 + 16), (v277 = v116) != 0) )
  {
    if ( !GetLangInfoByName(v115, v116) && !GetLangInfoByAlias(v115, v277) )
    {
      v118 = GetDefaultLocale();
      StringCchPrintf_lW(v530, 0x81u, L"%.*s", v118, (unsigned __int64)v277 >> 1, *(_QWORD *)v297);
      ex_raise(150, 33, 16, 1, v530);
    }
  }
  else
  {
    v119 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
    langinfo = get_langinfo(*(_WORD *)(v119 + 154));
    if ( langinfo )
    {
      *(_QWORD *)v297 = *((_QWORD *)langinfo + 1);
      v277 = *((unsigned __int8 *)langinfo + 16);
    }
    else
    {
      *(_QWORD *)v297 = L"us_english";
      v277 = 20;
    }
  }
  if ( v99 )
  {
    v121 = *(_DWORD *)(v22 + 2216);
    v122 = *(_QWORD *)(v22 + 2208);
    if ( v122 )
    {
      if ( v121 )
      {
        v123 = 0;
        v124 = (unsigned __int64)v121 >> 1;
        if ( v124 )
        {
          v125 = 0;
          while ( *(_WORD *)(v122 + 2 * v125) != 92 )
          {
            ++v123;
            if ( ++v125 >= v124 )
              goto LABEL_207;
          }
          if ( v123 >= 0 )
            ex_raise(150, 6, 16, 1, v521);
        }
      }
    }
LABEL_207:
    v126 = *(_QWORD *)(v22 + 2304);
    if ( v126 )
    {
      v127 = *(const void **)(v126 + 8);
      v128 = *(int *)(v126 + 16);
      MasterDbId = v128;
      if ( (_DWORD)v128 != 16 )
        ex_raise(154, 19, 16, 1);
      if ( (_DWORD)v128 )
      {
        if ( v127 )
        {
          memmove(&v512, v127, (unsigned int)v128);
        }
        else
        {
          memset_0(&v512, 0, (unsigned int)v128);
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
      }
      v129 = 0;
      if ( (int)v128 <= 0 )
      {
LABEL_221:
        ex_raise(154, 33, 16, 1);
      }
      else
      {
        v130 = 0;
        while ( !v129 )
        {
          v129 = *((_BYTE *)&v512.Data1 + v130++);
          if ( v130 >= v128 )
          {
            if ( v129 )
              break;
            goto LABEL_221;
          }
        }
      }
    }
    else
    {
      v506 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      if ( CoCreateGuid(&v506) )
        ex_raise(151, 67, 16, 1);
      v512 = v506;
      MasterDbId = 16;
    }
    v131 = 0;
    StringUuid = 0;
    v132 = *(_QWORD *)(v22 + 2256);
    if ( v132 )
    {
      v131 = *(unsigned __int16 **)(v132 + 8);
      StringUuid = v131;
      v133 = *(_DWORD *)(v132 + 16);
      if ( v133 > 0x100 )
      {
        *(_DWORD *)v254 = 128;
        ex_raise(151, 56, 16, 1, *(_QWORD *)v254);
      }
    }
    else
    {
      v133 = 0;
    }
    v306 = 512;
    v134 = *(_QWORD *)(v22 + 2264);
    if ( !v134 || !*(_DWORD *)(v134 + 16) )
    {
      SecureHash(v527, &v306, v131, v133, 1, 0);
      v137 = 0;
      v275[0] = 0;
      v279 = v306;
      goto LABEL_251;
    }
    v275[0] = 1;
    if ( v133 > 0x200 )
      ex_raise(150, 21, 16, 1, L"PASSWORD");
    if ( v133 )
    {
      if ( v131 && v133 <= 0x200uLL )
      {
        memmove(v527, v131, v133);
        goto LABEL_242;
      }
      memset_0(v527, 0, 0x200u);
      if ( v131 )
      {
        if ( v133 <= 0x200uLL )
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
    v279 = v133;
    if ( v133 == 16 )
    {
      v135 = 1;
      v136 = 0;
      v137 = 1;
    }
    else
    {
      v149 = -1;
      v150 = -1;
      v138 = v527[0];
      if ( v527[0] == 1 )
      {
        if ( v133 == 26 || v133 == 46 )
          v150 = 1;
      }
      else if ( v527[0] == 2 && v133 == 70 && v527[0] == 2 )
      {
        v150 = 2;
      }
      v135 = v150 < 2;
      if ( v527[0] == 1 )
      {
        if ( v133 == 26 || (v136 = v150, v137 = v150 < 2, v133 == 46) )
        {
          v136 = v150;
          v137 = v150 < 2;
          goto LABEL_245;
        }
      }
      else if ( v527[0] == 2 )
      {
        if ( v133 == 70 && v527[0] == 2 )
          v149 = 2;
        v136 = v150;
        v137 = v150 < 2;
        if ( v149 >= 1 )
          goto LABEL_245;
      }
      else
      {
        v136 = v150;
        v137 = v150 < 2;
      }
    }
    ex_raise(150, 21, 16, 2, L"PASSWORD");
    v138 = v527[0];
LABEL_245:
    if ( v136 == 1 )
    {
      if ( (v133 == 26 || v133 == 46) && v138 == 1 )
        v279 = 26;
      else
        v137 = v135;
    }
    v22 = v276;
LABEL_251:
    v139 = *(_QWORD *)(v22 + 2296);
    v140 = 1;
    v274 = 1;
    if ( !v139 )
      goto LABEL_258;
    v141 = *(const wchar_t **)(v139 + 8);
    v142 = *(int *)(v139 + 16);
    if ( (_DWORD)v142 )
    {
      v143 = v142 >> 1;
      if ( CompareStringWEnglishNoCase(1u, 0, v141, v142 >> 1, L"on", 2) == 2 )
      {
LABEL_256:
        v274 = v140;
        goto LABEL_257;
      }
      if ( CompareStringWEnglishNoCase(1u, 0, v141, v143, L"off", 3) == 2 )
      {
        v140 = 0;
        goto LABEL_256;
      }
    }
LABEL_257:
    v22 = v276;
LABEL_258:
    v144 = *(_QWORD *)(v22 + 2288);
    v145 = 0;
    if ( v144 )
    {
      v146 = *(const wchar_t **)(v144 + 8);
      v147 = *(int *)(v144 + 16);
      if ( (_DWORD)v147 )
      {
        v148 = v147 >> 1;
        if ( CompareStringWEnglishNoCase(1u, 0, v146, v147 >> 1, L"on", 2) == 2 )
          v145 = 1;
        else
          CompareStringWEnglishNoCase(1u, 0, v146, v148, L"off", 3);
        v22 = v276;
      }
    }
    v151 = *(_QWORD *)(v22 + 2272);
    v152 = 0;
    v278 = 0;
    if ( v151 && *(_DWORD *)(v151 + 16) )
    {
      v278 = 1;
      PwdPolicyManager = GetPwdPolicyManager();
      v403 = PwdPolicyManager;
      if ( !(**(unsigned int (__fastcall ***)(struct IPwdPolicyManager *))PwdPolicyManager)(PwdPolicyManager) )
        ex_raise(151, 95, 16, 1);
      if ( v275[0] )
        ex_raise(330, 10, 16, 1);
      operator delete(PwdPolicyManager, 8u);
      v152 = v278;
    }
    if ( v145 && !v140 )
      ex_raise(151, 22, 16, 1);
    if ( v152 && !v145 )
      ex_raise(150, 99, 16, 1);
    v393 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, GUID *, _QWORD, _DWORD, _DWORD, _DWORD, GUID *))(*v287 + 360))(
           v287,
           &v300,
           &v512,
           MasterDbId,
           0,
           0,
           0,
           &v393);
    if ( !v9 )
    {
      LOBYTE(v255) = 1;
      v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD, _QWORD, int, _DWORD))(*v287 + 344))(
             v287,
             &v512,
             MasterDbId,
             0,
             v255,
             0);
      if ( v9 )
        ex_raise(154, 33, 16, 1);
      else
        ex_raise(150, 25, 16, 1, v521);
    }
    *(_OWORD *)v325 = 0;
    v326 = 0;
    v327 = 0;
    v328 = 0;
    v329 = 0;
    v330 = 0;
    utgettime((struct SQLDATEBASE *)&v333, 1, 0);
    HIDWORD(v325[0]) = v279;
    v154 = (unsigned __int8 *)operator new[](
                                v279,
                                *(struct IMemObj **)&Size[1],
                                "sql\\ntdbms\\msql\\security\\src\\secddl.cpp",
                                7013,
                                3u);
    v325[1] = v154;
    if ( v279 )
    {
      if ( v154 )
      {
        memmove(v154, v527, v279);
      }
      else
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
    }
    *(_QWORD *)&v326 = v333;
    LOBYTE(v325[0]) = v274 & 0xFD | (__int64)v325[0] & 0xFC | (2 * v145);
    if ( v274 && v275[0] && !v137 )
    {
      InitializePwdHashHistory(
        *(struct IMemObj **)&Size[1],
        (struct MDAttrLoginPassword *)v325,
        v325[1],
        SHIDWORD(v325[0]));
      (*(void (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v9 + 312LL))(v9, 39, v325);
    }
    else
    {
      (*(void (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v9 + 312LL))(v9, 7, v325);
      if ( !v275[0] )
      {
        v155 = GetPwdPolicyManager();
        v294 = v155;
        if ( v279 == 70 )
        {
          v156 = (struct IPwdPolicyManager *)v528;
          v157 = 64;
        }
        else if ( (v279 == 26 || v279 == 46) && v527[0] == 1 )
        {
          v156 = (struct IPwdPolicyManager *)v528;
          v157 = 20;
        }
        else
        {
          v157 = v305;
          v156 = v294;
        }
        v360[2] = 0;
        v360[1] = 0;
        v360[0] = v9;
        v361 = 0;
        LOBYTE(v271) = 0;
        LOBYTE(v270) = v278;
        v158 = (*(__int64 (__fastcall **)(struct IPwdPolicyManager *, _QWORD *, RPC_WSTR, _QWORD, struct IPwdPolicyManager *, int, int, int))(*(_QWORD *)v155 + 24LL))(
                 v155,
                 v360,
                 StringUuid,
                 v133,
                 v156,
                 v157,
                 v270,
                 v271);
        HandlePasswordValidationResultCode(v158);
        operator delete(v155, 8u);
      }
    }
    operator delete[](v325[1]);
    operator delete[](*((void **)&v329 + 1));
    operator delete[](v330);
    if ( HIDWORD(v327) )
    {
      v159 = 0;
      do
        operator delete[](*(void **)(*((_QWORD *)&v328 + 1) + 8LL * v159++));
      while ( v159 < HIDWORD(v327) );
    }
    operator delete[]((void *)v328);
    operator delete[](*((void **)&v328 + 1));
    goto LABEL_430;
  }
  if ( v88 )
  {
    v301 = 85;
    v281 = 0;
    v280 = 0;
    v160 = *(const wchar_t **)(v22 + 2208);
    v161 = (_DWORD *)(v22 + 2216);
    v162 = *(_DWORD *)(v22 + 2216);
    if ( !v160 )
      goto LABEL_330;
    if ( !v162 )
      goto LABEL_330;
    v163 = 0;
    if ( !((unsigned __int64)v162 >> 1) )
      goto LABEL_330;
    v164 = 0;
    while ( v160[v164] != 92 )
    {
      ++v163;
      if ( ++v164 >= (__int64)((unsigned __int64)v162 >> 1) )
        goto LABEL_330;
    }
    if ( v163 >= 0 && v162 - 1 != v163 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset)
                                 + 72LL)
                     + 270LL)
          & 4) == 0 )
      {
        v290[0] = 85;
        v170 = FGetSidFromNt(v160, v162, pSid, v290, 85, 1);
        v166 = v170 != 0;
        if ( v170 )
          v171 = v280;
        else
          v171 = (unsigned int)FGetSidFromNt(v160, (unsigned int)*v161, pSid, v290, 71, 1) != 0;
        if ( !v166 && !v171 )
          ex_raise(154, 1, 16, 1, v521);
        v165 = v290[0];
LABEL_334:
        if ( OsInfo::IsLinux(SOS_OS_OsInfo) )
        {
          SidSubAuthority = GetSidSubAuthority(pSid, 0);
          LastError = GetLastError();
          if ( LastError > 0 )
            v169 = (unsigned __int16)LastError | 0x80070000;
          else
            v169 = LastError;
          if ( v169 )
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
              LODWORD(v269) = *v161;
              LODWORD(v265) = 13115;
              *(_DWORD *)v256 = 13105;
              ex_raise(151, 51, 16, 4, *(_QWORD *)v256, v265, v269, *(_QWORD *)(v276 + 2208));
            }
          }
        }
        v395 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
        v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int8 *, _QWORD, unsigned int, _DWORD, _DWORD, GUID *))(*v287 + 360))(
               v287,
               &v300,
               pSid,
               v165,
               2 - (unsigned int)v166,
               0,
               0,
               &v395);
        if ( v9 )
        {
LABEL_431:
          v376 = v299;
          v377 = Size[0];
          (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v9 + 288LL))(v9, &v376);
          v378 = *(_QWORD *)v297;
          v379 = v277;
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 296LL))(v9, &v378);
          goto LABEL_432;
        }
        ex_raise(150, 25, 16, 2, v521);
LABEL_432:
        v209 = 4;
        goto LABEL_433;
      }
    }
    else
    {
LABEL_330:
      if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
        ex_raise(154, 7, 16, 1, v521);
    }
    v394 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    LOBYTE(v264) = 0;
    LookupFederatedPrincipal(v160, v22 + 2216, v521, 0, &pguid, v264, pSid, &v301, &v281, &v280, &v394);
    v165 = v301;
    v166 = v281;
    goto LABEL_334;
  }
  if ( v278 )
  {
    v172 = *(_DWORD *)(v22 + 2216);
    v173 = *(_QWORD *)(v22 + 2208);
    if ( v173 )
    {
      if ( v172 )
      {
        v174 = 0;
        v175 = (unsigned __int64)v172 >> 1;
        if ( v175 )
        {
          v176 = 0;
          while ( *(_WORD *)(v173 + 2 * v176) != 92 )
          {
            ++v174;
            if ( ++v176 >= v175 )
              goto LABEL_365;
          }
          if ( v174 >= 0 )
            ex_raise(150, 6, 16, 1, v521);
        }
      }
    }
LABEL_365:
    v177 = 0;
    v178 = *(_QWORD *)(v22 + 2344);
    if ( v178 )
    {
      v177 = *(_QWORD *)(v178 + 8);
      v179 = *(_DWORD *)(v178 + 16);
    }
    else
    {
      v179 = 0;
    }
    v321 = v177;
    v322 = v179;
    v180 = *v287;
    v181 = GetMasterDbId();
    v182 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(v180 + 56))(
             v287,
             v181,
             0,
             0,
             0,
             0);
    v183 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v182 + 800LL))(v182, &v321, 0);
    if ( !v183 )
    {
      LODWORD(v269) = v322;
      LODWORD(v266) = 13116;
      *(_DWORD *)v257 = 13118;
      ex_raise(151, 51, 16, 1, *(_QWORD *)v257, v266, v269, v321);
    }
    v184 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset)
                                             + 72LL)
                                 + 104LL)
                     + 264LL)
         + 216LL;
    v314 = 0;
    CSECSessionCryptoContext::GetCryptoContext(v184, v410, 3, &v314);
    if ( v410[0] )
    {
      v294 = (struct IPwdPolicyManager *)v408;
      v409 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v408, (const struct CSECCryptoError *)v410);
      RaiseCryptoError(v408, 0);
    }
    if ( v411 )
      operator delete[](v411);
    v302 = 85;
    *(_OWORD *)hCertStore = 0;
    v341 = 0;
    v342 = v314;
    pCertContext = 0;
    v344 = 0;
    CSECCertificate::InitFromMD(hCertStore, v412, *(_QWORD *)&Size[1], v183);
    if ( v412[0] )
    {
      v294 = (struct IPwdPolicyManager *)v424;
      v425 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v424, (const struct CSECCryptoError *)v412);
      RaiseCryptoError(v424, 0);
    }
    if ( v413 )
      operator delete[](v413);
    CSECCertificate::GetSid(hCertStore, v416, &v302, v523);
    if ( v416[0] )
    {
      v294 = (struct IPwdPolicyManager *)v414;
      v415 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v414, (const struct CSECCryptoError *)v416);
      RaiseCryptoError(v414, 0);
    }
    if ( v417 )
      operator delete[](v417);
    v257[0] = 1;
    v185 = v302;
    if ( (*(__int64 (__fastcall **)(__int64 *, _BYTE *, _QWORD, _QWORD, _DWORD, _DWORD))(*v287 + 344))(
           v287,
           v523,
           v302,
           0,
           *(_DWORD *)v257,
           0) )
    {
      LODWORD(v269) = v322;
      *(_DWORD *)v258 = DWORD2(v300);
      ex_raise(331, 40, 16, 1, *(_QWORD *)v258, (_QWORD)v300, v269, v321);
    }
    else
    {
      v396 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _BYTE *, _QWORD, int, _DWORD, _DWORD, GUID *))(*v287 + 360))(
             v287,
             &v300,
             v523,
             v185,
             4,
             0,
             0,
             &v396);
      if ( !v9 )
        ex_raise(150, 25, 16, 3, v521);
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
  if ( v279 )
  {
    v186 = *(_DWORD *)(v22 + 2216);
    v187 = *(_QWORD *)(v22 + 2208);
    if ( v187 )
    {
      if ( v186 )
      {
        v188 = 0;
        v189 = (unsigned __int64)v186 >> 1;
        if ( v189 )
        {
          v190 = 0;
          while ( *(_WORD *)(v187 + 2 * v190) != 92 )
          {
            ++v188;
            if ( ++v190 >= v189 )
              goto LABEL_400;
          }
          if ( v188 >= 0 )
            ex_raise(150, 6, 16, 1, v521);
        }
      }
    }
LABEL_400:
    v191 = 0;
    v192 = *(_QWORD *)(v22 + 2376);
    if ( v192 )
    {
      v191 = *(_QWORD *)(v192 + 8);
      v193 = *(_DWORD *)(v192 + 16);
    }
    else
    {
      v193 = 0;
    }
    v323 = v191;
    v324 = v193;
    v194 = *v287;
    v195 = GetMasterDbId();
    v196 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(v194 + 56))(
             v287,
             v195,
             0,
             0,
             0,
             0);
    v197 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v196 + 960LL))(v196, &v323, 0);
    if ( !v197 )
    {
      LODWORD(v269) = v324;
      LODWORD(v267) = 13141;
      *(_DWORD *)v259 = 13118;
      ex_raise(151, 51, 16, 1, *(_QWORD *)v259, v267, v269, v323);
    }
    v198 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset)
                                             + 72LL)
                                 + 104LL)
                     + 264LL)
         + 216LL;
    v316 = 0;
    CSECSessionCryptoContext::GetCryptoContext(v198, v420, 3, &v316);
    if ( v420[0] )
    {
      v294 = (struct IPwdPolicyManager *)v418;
      v419 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v418, (const struct CSECCryptoError *)v420);
      RaiseCryptoError(v418, 0);
    }
    if ( v421 )
      operator delete[](v421);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v197 + 72LL))(v197, v507);
    if ( v508 == 6 )
    {
      v331 = 0;
      v315 = 0;
      v199 = CSECGlobalCryptoContext::m_cctxGlobal;
      v200 = *v287;
      v201 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v197 + 56LL))(v197);
      v203 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v200 + 584))(
                                                 v287,
                                                 v201,
                                                 0);
      if ( !v203 )
      {
        v204 = (const struct _GUID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v197 + 56LL))(v197);
        GuidToString(v204, v524, 0x4Au);
        ex_raise(330, 82, 16, 2, v524);
      }
      LOBYTE(v267) = 0;
      CSECGlobalCryptoContext::GetCryptoProvider(v199, v406, v202, v203, &v315, (_DWORD)v267);
      if ( v406[0] )
      {
        v294 = (struct IPwdPolicyManager *)v422;
        v423 = 0;
        CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v422, (const struct CSECCryptoError *)v406);
        RaiseCryptoError(v422, 0);
      }
      if ( v407 )
        operator delete[](v407);
      v205 = v315;
      v331 = v315;
      if ( *(_DWORD *)(v315 + 220) != 1 )
      {
        v206 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64))v197)(v197);
        v207 = (_QWORD *)(**v203)(v203);
        LODWORD(v268) = 13141;
        *(_DWORD *)v260 = 13115;
        ex_raise(330, 83, 16, 1, *(_QWORD *)v260, v268, *v206, *v207);
      }
      v208 = v205 + *(int *)(*(_QWORD *)(v205 + 8) + 4LL) + 8LL;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v208 + 8LL))(v208);
    }
    LODWORD(v303) = 85;
    CSECAsymmetricKey::CSECAsymmetricKey(v511, v316, 0, 0);
    CSECAsymmetricKey::InitFromMD(v511, v428, *(_QWORD *)&Size[1], v197);
    if ( v428[0] )
    {
      v294 = (struct IPwdPolicyManager *)v426;
      v427 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v426, (const struct CSECCryptoError *)v428);
      RaiseCryptoError(v426, 0);
    }
    if ( v429 )
      operator delete[](v429);
    CSECAsymmetricKey::GetSid(v511, v404, &v303, v525);
    if ( v404[0] )
    {
      v294 = (struct IPwdPolicyManager *)v430;
      v431 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v430, (const struct CSECCryptoError *)v404);
      RaiseCryptoError(v430, 0);
    }
    if ( v405 )
      operator delete[](v405);
    v397 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _BYTE *, _QWORD, int, _DWORD, _DWORD, GUID *))(*v287 + 360))(
           v287,
           &v300,
           v525,
           (unsigned int)v303,
           5,
           0,
           0,
           &v397);
    if ( !v9 )
      ex_raise(150, 25, 16, 2, v521);
    CSECAsymmetricKey::~CSECAsymmetricKey((CSECAsymmetricKey *)v511);
LABEL_430:
    if ( v9 )
      goto LABEL_431;
    goto LABEL_432;
  }
  if ( !v107 )
    goto LABEL_432;
  v222 = 85;
  v292 = 85;
  v223 = 0;
  v283 = 0;
  v282 = 0;
  v224 = v276;
  v225 = *(_QWORD *)(v276 + 2304);
  v226 = *(_QWORD *)(v276 + 2416);
  v227 = *(_QWORD *)(v276 + 2424);
  v228 = 0;
  v229 = *(_DWORD *)(v276 + 2216);
  v230 = *(_QWORD *)(v276 + 2208);
  if ( v230 && v229 )
  {
    v231 = 0;
    v232 = (unsigned __int64)v229 >> 1;
    if ( v232 )
    {
      v233 = 0;
      while ( *(_WORD *)(v230 + 2 * v233) != 92 )
      {
        ++v231;
        if ( ++v233 >= v232 )
          goto LABEL_459;
      }
      if ( v231 >= 0 )
        ex_raise(150, 6, 16, 2, v521);
    }
LABEL_459:
    v224 = v276;
  }
  if ( !v225 )
  {
    if ( !v226 )
    {
      if ( v227 )
      {
        v240 = *(_QWORD *)(v224 + 2424);
        if ( v240 )
        {
          v228 = *(const wchar_t **)(v240 + 8);
          v241 = *(_DWORD *)(v240 + 16);
        }
        else
        {
          v241 = 0;
        }
        v305 = v241;
      }
      v242 = *(const wchar_t **)(v224 + 2208);
      v243 = (int *)(v224 + 2216);
      v244 = *(_DWORD *)(v224 + 2216);
      if ( !v242 )
        goto LABEL_499;
      if ( !v244 )
        goto LABEL_499;
      v245 = 0;
      if ( !((unsigned __int64)v244 >> 1) )
        goto LABEL_499;
      v246 = 0;
      while ( v242[v246] != 92 )
      {
        ++v245;
        if ( ++v246 >= (__int64)((unsigned __int64)v244 >> 1) )
          goto LABEL_499;
      }
      if ( v245 >= 0 && v244 - 1 != v245 )
      {
        v247 = v228 != 0;
        if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset)
                                   + 72LL)
                       + 270LL)
            & 4) == 0 )
        {
          v286[0] = 85;
          v249 = FGetSidFromNt(v242, v244, v513, v286, 85, 1);
          v223 = v249 != 0;
          if ( v249 )
            v250 = v282;
          else
            v250 = (unsigned int)FGetSidFromNt(v242, (unsigned int)*v243, v513, v286, 71, 1) != 0;
          if ( !v223 && !v250 )
            ex_raise(154, 1, 16, 1, v521);
          v222 = v286[0];
          goto LABEL_518;
        }
      }
      else
      {
LABEL_499:
        v247 = v228 != 0;
        if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
          ex_raise(154, 7, 16, 1, v521);
      }
      v248 = &v305;
      if ( !v228 )
        v248 = v243;
      v398 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      if ( v228 )
        v242 = v228;
      LOBYTE(v264) = v247;
      LookupFederatedPrincipal(v242, v248, v521, 0, &pguid, v264, v513, &v292, &v283, &v282, &v398);
      v222 = v292;
      v223 = v283;
      goto LABEL_518;
    }
LABEL_517:
    ex_raise(331, 98, 16, 1);
    goto LABEL_518;
  }
  if ( !v226 )
    goto LABEL_517;
  v234 = 0;
  v235 = *(_QWORD *)(v224 + 2304);
  v236 = 8;
  if ( v235 )
  {
    v234 = *(const void **)(v235 + 8);
    v222 = *(_DWORD *)(v235 + 16);
    if ( v222 == 16 )
      goto LABEL_467;
  }
  else
  {
    v222 = 0;
  }
  ex_raise(154, 19, 16, 8);
LABEL_467:
  if ( !v222 )
    goto LABEL_476;
  if ( v234 && v222 <= 0x55uLL )
  {
    memmove(v513, v234, v222);
    goto LABEL_476;
  }
  *(_OWORD *)v513 = 0;
  v514 = 0;
  v515 = 0;
  v516 = 0;
  v517 = 0;
  v518 = 0;
  v519 = 0;
  if ( v234 )
  {
    if ( v222 <= 0x55uLL )
      goto LABEL_476;
    *_errno() = 34;
  }
  else
  {
    *_errno() = 22;
  }
  _invalid_parameter_noinfo();
LABEL_476:
  v237 = 0;
  v238 = *(_QWORD *)(v276 + 2416);
  if ( !v238 || (v237 = *(__int16 **)(v238 + 8), *(_DWORD *)(v238 + 16) != 2) )
    ex_raise(331, 97, 16, 1);
  if ( !v237 )
    goto LABEL_484;
  v239 = *v237;
  if ( *v237 != 69 )
  {
    if ( v239 == 88 )
      goto LABEL_485;
    if ( v239 != 101 )
    {
      if ( v239 != 120 )
      {
LABEL_484:
        ex_raise(331, 97, 16, 1);
        v236 = 0;
      }
LABEL_485:
      v223 = v236 == 7;
      goto LABEL_518;
    }
  }
  v223 = 1;
LABEL_518:
  v399 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int8 *, _QWORD, unsigned int, _DWORD, _DWORD, GUID *))(*v287 + 360))(
         v287,
         &v300,
         v513,
         v222,
         8 - (unsigned int)v223,
         0,
         0,
         &v399);
  if ( v9 )
    goto LABEL_431;
  v209 = 4;
  ex_raise(150, 25, 16, 4, v521);
LABEL_433:
  if ( v298 && v9 )
  {
    v210 = *(_QWORD *)v9;
    v211 = (*(__int64 (**)(void))(*(_QWORD *)v298 + 8LL))();
    (*(void (__fastcall **)(__int64, _QWORD))(v210 + 304))(v9, v211);
  }
  v212 = v287;
  if ( v285 )
  {
    LOBYTE(v117) = 1;
    v213 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, __int64, _DWORD))(*v287 + 336))(v287, 1, 0, v117, 0);
    v317 = 0x100000000LL;
    v214 = (*(__int64 (__fastcall **)(__int64 *))(*v212 + 368))(v212);
    v401 = v214;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 176LL))(v214);
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64 *, int))(*(_QWORD *)v214 + 216LL))(
      v214,
      v9,
      v213,
      &v317,
      1);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v214 + 240LL))(v214, 1);
  }
  if ( v9 )
  {
    v215 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( !v309 )
    {
      v400 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      ISECManager::CheckPermRuleAuditOnly(
        1380142168,
        *(_QWORD *)&Size[1],
        v212,
        v308,
        v215,
        v310,
        v293,
        0,
        0,
        &v400,
        0,
        0,
        0,
        -1);
      v309 = 1;
    }
  }
  v216 = (*(__int64 (__fastcall **)(__int64 *))(*v212 + 16))(v212);
  v217 = GetMasterDbId();
  v218 = g_dbtableFactory[4](v217);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v216 + 280LL))(v216, *(_QWORD *)(v218 + 4624));
  v219 = GetMasterDbId();
  InvalidateSecurityCaches(v219, 24, 0);
  v284 = 1;
  v220 = v320;
  PostLoginEvent(48, v320, v332, v9, &v284, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
  if ( v284 )
  {
    if ( (*(_DWORD *)(GetXdbServerGlobals(v221) + 11976) || (unsigned int)IsVDWFrontendInstance())
      && (*(_BYTE *)(*(_QWORD *)(v318 + 72) + 270LL) & 2) == 0
      && (qword_102F21DB4 & 4) != 0 )
    {
      v487 = 196608;
      v488 = 0;
      v489 = &v492;
      v490 = &v500;
      v501 = 0;
      v491 = 0;
      v502 = 0;
      v492 = &v503;
      v493 = 16;
      v494 = 2;
      v495 = L"CREATE";
      v496 = 12;
      v497 = L"FINISH";
      v498 = 12;
      v499 = 1;
      XeCloudPkg::azuresqldb_login_ddl::Publish((XeCloudPkg::azuresqldb_login_ddl *)v486);
    }
    *(_BYTE *)(v220 + 176) |= 0x10u;
    v209 = 0;
  }
  CAutoHandleCreateAudit::~CAutoHandleCreateAudit((CAutoHandleCreateAudit *)&v307);
  return v209;
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
