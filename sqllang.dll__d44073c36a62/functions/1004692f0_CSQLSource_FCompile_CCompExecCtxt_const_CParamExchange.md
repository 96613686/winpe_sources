# CSQLSource::FCompile(CCompExecCtxt const &,CParamExchange *)

- ea: `0x1004692f0`
- end: `0x10046932d`
- name: `?FCompile@CSQLSource@@IEAA_NAEBVCCompExecCtxt@@PEAVCParamExchange@@@Z`
- size: `61`
- prototype: `bool __fastcall(CSQLSource *__hidden this, const struct CCompExecCtxt *, struct CParamExchange *)`
- caller_count: `1`
- callee_count: `81`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x10045cd70`

## callees

- `0x100401070`
- `0x100401090`
- `0x10040be50`
- `0x10040c070`
- `0x1004111a0`
- `0x100411230`
- `0x100411270`
- `0x100411b70`
- `0x1004126e0`
- `0x1004131b0`
- `0x1004212f0`
- `0x100426290`
- `0x100426f30`
- `0x100430960`
- `0x100440150`
- `0x10045ab40`
- `0x10045cce0`
- `0x10045d450`
- `0x10045e930`
- `0x10045ecc0`
- `0x10045ee30`
- `0x10045eea0`
- `0x10045f670`
- `0x10045faa0`
- `0x1004601f0`
- `0x100460280`
- `0x1004602b0`
- `0x100460510`
- `0x100460600`
- `0x100460670`
- `0x1004607f0`
- `0x100460850`
- `0x1004690f0`
- `0x1004691f0`
- `0x100469240`
- `0x1004692f0`
- `0x100469340`
- `0x1004699a0`
- `0x10046a210`
- `0x10046a480`
- `0x10046a5c0`
- `0x10046ab90`
- `0x10048c710`
- `0x10049ad80`
- `0x1004c19d0`
- `0x1004d2020`
- `0x100500a60`
- `0x10061b7a0`
- `0x10065d2b0`
- `0x100660620`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10045e378`
- `KERNEL32!QueryPerformanceCounter` at `0x10049be84`
- `KERNEL32!QueryPerformanceCounter` at `0x10045e378`
- `KERNEL32!QueryPerformanceCounter` at `0x10049be84`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x10045dd43`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1006646ba`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10045d803`
- `sqldk!?sm_MallocSpyStatus@SOS_PublicGlobals@@2HA` at `0x10045de83`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10126c953`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10126ca11`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10045e358`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10049be64`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10049bf04`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10126cd4b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10126dbec`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10126cd4b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10126dbec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10126cdd0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10126dc6a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10126e1af`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10126cdd0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10126dc6a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10126e1af`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10045dad8`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10045dec0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126deec`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126dfa8`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126e378`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126e455`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126e81a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10045dad8`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10045dec0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126deec`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126dfa8`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126e378`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126e455`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126e81a`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10126eba7`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10126eba7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10126ec1b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10126ec35`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10126ec1b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10126ec35`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126c168`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126e2f5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126c168`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10126e2f5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10126cccd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10126db75`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10126cccd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10126db75`
- `sqldk!SystemThread_TlsIndex` at `0x10045d847`
- `sqldk!SystemThread_TlsIndex` at `0x10045da8c`
- `sqldk!SystemThread_TlsIndex` at `0x10045dafb`
- `sqldk!SystemThread_TlsIndex` at `0x10045db80`
- `sqldk!SystemThread_TlsIndex` at `0x10045dc9c`
- `sqldk!SystemThread_TlsIndex` at `0x10045e2f3`
- `sqldk!SystemThread_TlsIndex` at `0x10045e7cb`
- `sqldk!SystemThread_TlsIndex` at `0x10045e8b7`
- `sqldk!SystemThread_TlsIndex` at `0x10046a864`
- `sqldk!SystemThread_TlsIndex` at `0x1006647d5`
- `sqldk!SystemThread_TlsIndex` at `0x1006648e1`
- `sqldk!SystemThread_TlsIndex` at `0x10126c0f3`
- `sqldk!SystemThread_TlsIndex` at `0x10126c5f2`
- `sqldk!SystemThread_TlsIndex` at `0x10126c870`
- `sqldk!SystemThread_TlsIndex` at `0x10126cc38`
- `sqldk!SystemThread_TlsIndex` at `0x10126dae0`
- `sqldk!SystemThread_TlsIndex` at `0x10126dd76`
- `sqldk!SystemThread_TlsIndex` at `0x10126e221`
- `sqldk!SystemThread_TlsIndex` at `0x10126ea32`
- `sqldk!SystemThread_TlsOffset` at `0x10045d850`
- `sqldk!SystemThread_TlsOffset` at `0x10045da95`
- `sqldk!SystemThread_TlsOffset` at `0x10045db04`
- `sqldk!SystemThread_TlsOffset` at `0x10045db89`
- `sqldk!SystemThread_TlsOffset` at `0x10045dca5`
- `sqldk!SystemThread_TlsOffset` at `0x10045e2fc`
- `sqldk!SystemThread_TlsOffset` at `0x10045e7d4`
- `sqldk!SystemThread_TlsOffset` at `0x10045e8c0`
- `sqldk!SystemThread_TlsOffset` at `0x10046a86d`
- `sqldk!SystemThread_TlsOffset` at `0x1006647de`
- `sqldk!SystemThread_TlsOffset` at `0x1006648ea`
- `sqldk!SystemThread_TlsOffset` at `0x10126c0fc`
- `sqldk!SystemThread_TlsOffset` at `0x10126c5fb`
- `sqldk!SystemThread_TlsOffset` at `0x10126c879`
- `sqldk!SystemThread_TlsOffset` at `0x10126cc41`
- `sqldk!SystemThread_TlsOffset` at `0x10126dae9`
- `sqldk!SystemThread_TlsOffset` at `0x10126dd7f`
- `sqldk!SystemThread_TlsOffset` at `0x10126e22a`
- `sqldk!SystemThread_TlsOffset` at `0x10126ea3b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10046aac2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126c671`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126ddf5`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126e3d7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126e41f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126e768`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126e9a3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126ea99`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126ebe3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10046aac2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126c671`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126ddf5`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126e3d7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126e41f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126e768`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126e9a3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126ea99`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10126ebe3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126c29a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126c2af`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126c8e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126cc6c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126db14`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126eb94`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126c29a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126c2af`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126c8e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126cc6c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126db14`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10126eb94`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10126bfd8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10126bfd8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126cbb3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126cd3d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126da6a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126dbde`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126e77a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126cbb3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126cd3d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126da6a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126dbde`
- `sqldk!??_V@YAXPEAX@Z` at `0x10126e77a`
- `sqlTsEs!??0CEsComp@@IEAA@XZ` at `0x10126e830`
- `sqlTsEs!??0CEsComp@@IEAA@XZ` at `0x10126e830`
- `sqlTsEs!?FConfigured@CTrustedMachineHost@@SA_NXZ` at `0x10045e1b6`
- `sqlTsEs!?FConfigured@CTrustedMachineHost@@SA_NXZ` at `0x10045e1b6`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x10045d827`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x10045d827`

## string_xrefs

- `0x10126e80c`: `Sql\Ntdbms\include\esx\esx_comp.h`
- `0x10126c42d`: `UNKNOWN TOKEN`
- `0x10126c467`: `UNKNOWN TOKEN`
- `0x10126c00d`: `Compile issued : ProcName: %.*ls\n`
- `0x10126c02a`: `Compile issued : \n`
- `0x10126e19c`: `Sql\Ntdbms\include\common\stdarray.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=82 #try_helpers=1
bool __fastcall CSQLSource::FCompile(CSQLSource *this, CExecLvlRepresentation **a2, struct CParamExchange *a3)
{
  struct CCompExecCtxt *v3; // r14
  CSQLSource *v4; // r12
  __int64 v5; // rsi
  __int64 v6; // rax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rdx
  struct CSessionTraceFlags *v10; // rcx
  CProchdr *v11; // rdi
  CCompPlan *v12; // r13
  char *v13; // rax
  __int64 v14; // rax
  __int16 v15; // ax
  struct CEncryptionParamMetadataMap *v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rax
  __int16 v19; // ax
  __int64 v20; // rax
  __int16 v21; // ax
  struct PARAMD *v22; // rdx
  unsigned int v23; // r8d
  unsigned int v24; // r9d
  __int64 v25; // rax
  __int16 v26; // ax
  int v27; // ecx
  __int64 v28; // rcx
  struct CPmoLock *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rdx
  CGlobalEncryptionTypeDeductionContext *v33; // rdi
  __int64 v34; // rbx
  __int64 v35; // rdx
  CGlobalEncryptionTypeDeductionContext *v36; // rbx
  int v37; // eax
  CProchdr *v38; // rdi
  struct CAlgStmt *v39; // rsi
  CQPCompilationQueue *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rsi
  __int64 v45; // rax
  char v46; // di
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rax
  void (__fastcall ***v50)(_QWORD, _QWORD); // rbx
  struct CCompExecCtxt *v51; // rsi
  struct CAlgStmt *v52; // r14
  CacheStoreWrapper *v53; // rcx
  __int64 v54; // rcx
  struct IMemObj *MemoryObject; // rsi
  _QWORD *v56; // rax
  struct CPmoLock *v57; // rbx
  _QWORD *v58; // rax
  __int64 v59; // rcx
  struct IMemObj *v60; // rdi
  char v61; // dl
  __int64 v62; // rcx
  bool v63; // al
  void ***v64; // r13
  void ***v65; // r12
  __int64 v66; // r14
  CProchdr *v67; // rdi
  __int64 v68; // rsi
  CSQLSource *v69; // rsi
  __int64 v70; // rcx
  CGlobalEncryptionTypeDeductionContext *v71; // rdi
  CMATGen *v72; // rcx
  struct CAlgStmt *v73; // rsi
  CCompPlan *v74; // r14
  __int64 v75; // r13
  __int64 v76; // rbx
  __int64 v77; // rax
  __int64 v78; // rbx
  CSbTransportMgr *QuadPart; // rax
  char v80; // al
  struct CAlgStmt *v81; // rdx
  struct CCompExecCtxt *v82; // rsi
  CSQLSource *v83; // rcx
  struct CPmoLock *v84; // rbx
  struct CStatement *v85; // rcx
  struct CAlgStmt *v86; // r13
  __int64 v87; // rax
  __int64 v88; // rax
  char v89; // al
  bool v90; // al
  struct CStatement *v91; // rbx
  char v92; // al
  char v93; // cl
  char v94; // al
  char v95; // cl
  char v96; // al
  CSQLSource *v97; // rdi
  int v98; // eax
  int v99; // ebx
  bool v100; // al
  int *v101; // rsi
  struct IInstToLanguageMap *v102; // rdx
  struct CCompExecCtxt *v103; // rbx
  struct CAlgStmt *v104; // r8
  const struct CCompExecCtxtStmt *v105; // r9
  __int64 v106; // rdx
  __int64 v107; // rbx
  struct Worker *v108; // rcx
  __int64 v109; // rax
  CExecLvlRepresentation *v110; // rsi
  __int64 v111; // rax
  __int16 v112; // cx
  unsigned __int64 v113; // rax
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // r8
  char v117; // cl
  _DWORD *v118; // rcx
  __int64 v119; // rcx
  __int64 v120; // rax
  __int64 v121; // rdi
  __int64 v122; // rdi
  __int64 v123; // rcx
  struct CStatement *v124; // rbx
  bool result; // al
  CSbTransportMgr *v126; // rcx
  unsigned __int64 v127; // rcx
  unsigned __int64 v128; // rdx
  union _LARGE_INTEGER v129; // r8
  unsigned __int64 v130; // rcx
  unsigned __int64 v131; // rdx
  int v132; // eax
  __int64 v133; // r8
  __int64 v134; // r14
  BOOL v135; // edi
  int StatementInfoBase_1; // eax
  int v137; // esi
  wchar_t *v138; // rbx
  int v139; // edx
  int v140; // r8d
  int v141; // r9d
  int v142; // r11d
  char v143; // r10
  __int64 v144; // rdi
  __int64 v145; // rdi
  __int64 v146; // rcx
  __int64 v147; // rsi
  __int64 v148; // rbx
  char v149; // di
  __int64 v150; // rbx
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rbx
  __int64 v154; // rax
  struct CEncryptionParamMetadataMap *v155; // rcx
  struct CCompPlan *v156; // r9
  char v157; // al
  __int64 v158; // rax
  __int64 v159; // rax
  struct IMemObj *v160; // rdx
  int v161; // eax
  struct CStatement *v162; // rbx
  __int64 v163; // r9
  __int64 v164; // rax
  char *v165; // rbx
  struct CStatement *Safe; // rax
  __int64 v167; // rdx
  unsigned int v168; // ecx
  __int64 v169; // rdx
  __int64 v170; // r8
  __int64 v171; // rcx
  unsigned __int64 v172; // rcx
  __int64 v173; // rax
  __int64 v174; // rax
  int v175; // ecx
  int v176; // eax
  __int64 v177; // rcx
  __int64 v178; // rax
  unsigned int v179; // esi
  unsigned int v180; // ebx
  __int64 v181; // rdi
  struct IMemObj *v182; // r10
  __int64 v183; // r10
  unsigned int v184; // r14d
  unsigned __int64 v185; // rax
  struct CParamExchange *v186; // r9
  __int64 v187; // r9
  __int64 v188; // rax
  struct IMEDModule *v189; // rax
  __int64 v190; // rcx
  __int64 v191; // rcx
  const wchar_t *v192; // rax
  __int64 v193; // r8
  unsigned int v194; // r8d
  __int64 v195; // rcx
  const wchar_t *v196; // rax
  int v197; // r9d
  __int64 v198; // rdx
  __int64 v199; // rbx
  __int64 v200; // rcx
  __int64 v201; // rax
  CGlobalEncryptionTypeDeductionContext *v202; // rbx
  struct CStatement *v203; // rbx
  CExecLvlRepresentation *v204; // rdi
  __int64 v205; // rax
  int v206; // edx
  _BYTE **v207; // r8
  int v208; // ecx
  _BYTE **v209; // rdx
  __int64 v210; // rbx
  __int64 v211; // r10
  struct IMemObj *v212; // r10
  unsigned __int64 v213; // rax
  wchar_t *v214; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  __int64 v216; // rax
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rax
  __int64 v220; // rbx
  __int64 v221; // rax
  int v222; // eax
  __int64 v223; // rax
  __int64 v224; // rax
  __int64 v225; // rax
  __int64 v226; // rax
  __int64 v227; // rax
  int v228; // eax
  __int64 v229; // r8
  __int64 v230; // rsi
  int StatementInfoBase_0; // eax
  int v232; // edi
  wchar_t *v233; // rbx
  int v234; // ecx
  _QWORD **v235; // rdx
  __int64 v236; // rbx
  __int64 v237; // r10
  struct IMemObj *v238; // r10
  unsigned __int64 v239; // rax
  wchar_t *v240; // rax
  struct __crt_locale_pointers *v241; // rax
  __int64 v242; // rdx
  __int64 v243; // rax
  CGlobalEncryptionTypeDeductionContext *v244; // rbx
  struct CStatement *v245; // rbx
  struct IMemObj *LargeCPMemObj; // rbx
  CPmoLock *v247; // rax
  CSQLSource *v248; // rcx
  CPmoLock *v249; // rax
  struct IMemObj *v250; // rbx
  struct CStatement *v251; // rdi
  _QWORD *v252; // rdi
  char *v253; // rdi
  __int64 v254; // rax
  __int64 v255; // r13
  unsigned __int16 v256; // si
  unsigned __int16 i; // ax
  __int64 v258; // rcx
  int v259; // r14d
  unsigned int v260; // ebx
  unsigned int v261; // edx
  __int64 v262; // rdi
  struct IInstToLanguageMap *v263; // rax
  int v264; // ebx
  unsigned __int64 v265; // rax
  struct IMemObj *v266; // r12
  _WORD *v267; // r14
  struct CAlgStmt *v268; // rdi
  __int64 v269; // rbx
  _OWORD *v270; // rax
  _OWORD *v271; // r13
  void *v272; // rsi
  _DWORD *v273; // r12
  _QWORD *v274; // rax
  void (__fastcall ***v275)(_QWORD, __int64); // rbx
  __int64 v276; // rax
  struct CPmoLock *v277; // rdi
  __int64 v278; // r13
  _QWORD *v279; // rcx
  struct IMemObj *v280; // rax
  const struct CEsCompFull *v281; // r13
  CEsComp *v282; // rax
  CEsComp *v283; // r10
  __int64 v284; // r10
  struct CPmoLock *v285; // rcx
  __int64 v286; // rbx
  __int64 v287; // rcx
  __int64 v288; // rax
  struct CPmoLock *v289; // [rsp+20h] [rbp-3D18h]
  int v290; // [rsp+20h] [rbp-3D18h]
  int v291; // [rsp+28h] [rbp-3D10h]
  TraceUtil *v292; // [rsp+28h] [rbp-3D10h]
  TraceUtil *v293; // [rsp+28h] [rbp-3D10h]
  wchar_t *v294; // [rsp+30h] [rbp-3D08h]
  char v295; // [rsp+90h] [rbp-3CA8h]
  bool v296; // [rsp+91h] [rbp-3CA7h]
  bool v297; // [rsp+92h] [rbp-3CA6h]
  char v298; // [rsp+93h] [rbp-3CA5h]
  char v299; // [rsp+94h] [rbp-3CA4h]
  char v300; // [rsp+95h] [rbp-3CA3h]
  struct CStatement *v301; // [rsp+98h] [rbp-3CA0h] BYREF
  char *v302; // [rsp+A0h] [rbp-3C98h]
  char v303; // [rsp+A8h] [rbp-3C90h]
  char v304[3]; // [rsp+A9h] [rbp-3C8Fh] BYREF
  int v305; // [rsp+ACh] [rbp-3C8Ch] BYREF
  int v306; // [rsp+B0h] [rbp-3C88h] BYREF
  struct CAlgStmt *v307; // [rsp+B8h] [rbp-3C80h]
  CProchdr *v308; // [rsp+C0h] [rbp-3C78h]
  struct CPmoLock *v309; // [rsp+C8h] [rbp-3C70h] BYREF
  struct CCompExecCtxt *v310; // [rsp+D0h] [rbp-3C68h]
  char v311; // [rsp+D8h] [rbp-3C60h]
  char v312; // [rsp+D9h] [rbp-3C5Fh]
  bool v313; // [rsp+DAh] [rbp-3C5Eh]
  char v314; // [rsp+DBh] [rbp-3C5Dh]
  bool v315; // [rsp+E0h] [rbp-3C58h]
  char v316; // [rsp+E8h] [rbp-3C50h]
  int v317; // [rsp+ECh] [rbp-3C4Ch]
  CCompPlan *v318; // [rsp+F0h] [rbp-3C48h]
  __int16 v319; // [rsp+F8h] [rbp-3C40h]
  __int64 v320; // [rsp+100h] [rbp-3C38h]
  CSQLSource *v321; // [rsp+108h] [rbp-3C30h]
  void (__fastcall ***v322)(_QWORD, _QWORD); // [rsp+110h] [rbp-3C28h]
  CExecLvlRepresentation *v323; // [rsp+118h] [rbp-3C20h]
  int v324; // [rsp+120h] [rbp-3C18h]
  unsigned int v325; // [rsp+124h] [rbp-3C14h]
  int v326; // [rsp+128h] [rbp-3C10h] BYREF
  int v327; // [rsp+12Ch] [rbp-3C0Ch] BYREF
  struct CStatement *v328; // [rsp+130h] [rbp-3C08h]
  char *v329; // [rsp+138h] [rbp-3C00h]
  CGlobalEncryptionTypeDeductionContext *v330; // [rsp+140h] [rbp-3BF8h]
  __int64 v331; // [rsp+148h] [rbp-3BF0h]
  __int64 v332; // [rsp+150h] [rbp-3BE8h] BYREF
  __int64 v333; // [rsp+158h] [rbp-3BE0h] BYREF
  int v334; // [rsp+160h] [rbp-3BD8h] BYREF
  bool v335; // [rsp+164h] [rbp-3BD4h]
  char v336; // [rsp+165h] [rbp-3BD3h]
  char v337; // [rsp+166h] [rbp-3BD2h]
  char v338; // [rsp+167h] [rbp-3BD1h]
  char v339; // [rsp+168h] [rbp-3BD0h]
  char v340; // [rsp+170h] [rbp-3BC8h]
  void (__fastcall ***v341)(_QWORD, __int64); // [rsp+178h] [rbp-3BC0h]
  bool v342; // [rsp+180h] [rbp-3BB8h]
  __int64 v343; // [rsp+18Ch] [rbp-3BACh] BYREF
  __int64 v344; // [rsp+198h] [rbp-3BA0h]
  __int64 v345; // [rsp+1A0h] [rbp-3B98h]
  wchar_t *v346; // [rsp+1A8h] [rbp-3B90h]
  wchar_t *v347; // [rsp+1B0h] [rbp-3B88h]
  unsigned __int64 v348; // [rsp+1B8h] [rbp-3B80h]
  __int64 v349; // [rsp+1C0h] [rbp-3B78h]
  __int128 v350; // [rsp+1C8h] [rbp-3B70h]
  __int128 v351; // [rsp+1D8h] [rbp-3B60h]
  struct CPmoLock *v352; // [rsp+1E8h] [rbp-3B50h]
  unsigned int v353; // [rsp+1F0h] [rbp-3B48h] BYREF
  struct CParamExchange *v354; // [rsp+1F8h] [rbp-3B40h]
  __int64 v355; // [rsp+200h] [rbp-3B38h] BYREF
  int v356; // [rsp+208h] [rbp-3B30h]
  __int64 v357; // [rsp+210h] [rbp-3B28h] BYREF
  wchar_t *v358; // [rsp+218h] [rbp-3B20h] BYREF
  BOOL v359; // [rsp+220h] [rbp-3B18h]
  int v360; // [rsp+224h] [rbp-3B14h] BYREF
  int v361; // [rsp+228h] [rbp-3B10h]
  unsigned int v362; // [rsp+22Ch] [rbp-3B0Ch] BYREF
  __int64 (__fastcall **v363)(); // [rsp+230h] [rbp-3B08h] BYREF
  char v364; // [rsp+238h] [rbp-3B00h]
  void (__fastcall ***v365)(_QWORD, _QWORD); // [rsp+240h] [rbp-3AF8h]
  __int64 v366; // [rsp+248h] [rbp-3AF0h]
  int v367; // [rsp+250h] [rbp-3AE8h]
  wchar_t *v368; // [rsp+258h] [rbp-3AE0h] BYREF
  __int64 v369; // [rsp+260h] [rbp-3AD8h]
  CCompPlan *v370; // [rsp+268h] [rbp-3AD0h]
  __int16 v371; // [rsp+270h] [rbp-3AC8h]
  __int16 v372; // [rsp+278h] [rbp-3AC0h]
  __int16 v373; // [rsp+280h] [rbp-3AB8h]
  __int16 v374; // [rsp+288h] [rbp-3AB0h]
  int v375; // [rsp+290h] [rbp-3AA8h]
  BOOL v376; // [rsp+294h] [rbp-3AA4h]
  BOOL v377; // [rsp+298h] [rbp-3AA0h]
  int v378; // [rsp+29Ch] [rbp-3A9Ch] BYREF
  int v379; // [rsp+2A0h] [rbp-3A98h] BYREF
  __int64 v380; // [rsp+2A8h] [rbp-3A90h] BYREF
  __int64 v381; // [rsp+2B0h] [rbp-3A88h] BYREF
  __int64 v382; // [rsp+2B8h] [rbp-3A80h] BYREF
  struct CPmoLock *v383; // [rsp+2C0h] [rbp-3A78h]
  unsigned __int64 v384; // [rsp+2C8h] [rbp-3A70h]
  int v385; // [rsp+2D0h] [rbp-3A68h]
  _QWORD *v386; // [rsp+2D8h] [rbp-3A60h]
  unsigned int v387; // [rsp+2E0h] [rbp-3A58h]
  struct IMemObj *v388; // [rsp+2E8h] [rbp-3A50h]
  unsigned __int64 v389; // [rsp+2F0h] [rbp-3A48h] BYREF
  unsigned __int64 v390; // [rsp+2F8h] [rbp-3A40h] BYREF
  CExecLvlRepresentation *v391; // [rsp+300h] [rbp-3A38h]
  __int64 v392; // [rsp+308h] [rbp-3A30h] BYREF
  struct IMemObj *v393; // [rsp+310h] [rbp-3A28h] BYREF
  struct IMemObj *v394; // [rsp+318h] [rbp-3A20h] BYREF
  struct IMemObj *v395; // [rsp+320h] [rbp-3A18h]
  __int64 v396; // [rsp+328h] [rbp-3A10h]
  _WORD *v397; // [rsp+330h] [rbp-3A08h]
  struct CPmoLock *v398; // [rsp+338h] [rbp-3A00h] BYREF
  struct CPmoLock *v399; // [rsp+340h] [rbp-39F8h]
  CSQLSource *v400; // [rsp+348h] [rbp-39F0h]
  CSbTransportMgr *v401; // [rsp+350h] [rbp-39E8h] BYREF
  CSbTransportMgr *v402; // [rsp+358h] [rbp-39E0h] BYREF
  CSbTransportMgr *v403; // [rsp+360h] [rbp-39D8h] BYREF
  unsigned __int64 v404; // [rsp+368h] [rbp-39D0h] BYREF
  unsigned __int64 v405; // [rsp+370h] [rbp-39C8h]
  unsigned __int64 v406; // [rsp+378h] [rbp-39C0h] BYREF
  struct IMemObj *v407; // [rsp+380h] [rbp-39B8h]
  struct CPmoLock *v408; // [rsp+388h] [rbp-39B0h]
  __int64 v409; // [rsp+398h] [rbp-39A0h]
  bool v410; // [rsp+3A0h] [rbp-3998h]
  __int64 (__fastcall **v411)(); // [rsp+3A8h] [rbp-3990h] BYREF
  char v412; // [rsp+3B0h] [rbp-3988h]
  __int64 v413; // [rsp+3B8h] [rbp-3980h]
  int v414; // [rsp+3C0h] [rbp-3978h]
  int v415; // [rsp+3C4h] [rbp-3974h]
  int v416; // [rsp+3C8h] [rbp-3970h]
  int v417; // [rsp+3CCh] [rbp-396Ch] BYREF
  char v418; // [rsp+3D0h] [rbp-3968h]
  int v420; // [rsp+3D8h] [rbp-3960h]
  int v421; // [rsp+3DCh] [rbp-395Ch]
  int v422; // [rsp+3E0h] [rbp-3958h]
  int v423; // [rsp+3E4h] [rbp-3954h]
  int v424; // [rsp+3E8h] [rbp-3950h]
  int v425; // [rsp+3ECh] [rbp-394Ch]
  int v426; // [rsp+3F0h] [rbp-3948h]
  int v427; // [rsp+3F4h] [rbp-3944h]
  int v428; // [rsp+3F8h] [rbp-3940h]
  int v429; // [rsp+3FCh] [rbp-393Ch]
  unsigned int v430; // [rsp+400h] [rbp-3938h]
  int v431; // [rsp+408h] [rbp-3930h]
  int v432; // [rsp+40Ch] [rbp-392Ch]
  int v433; // [rsp+410h] [rbp-3928h]
  int v434; // [rsp+418h] [rbp-3920h]
  int v435; // [rsp+420h] [rbp-3918h]
  int v436; // [rsp+424h] [rbp-3914h]
  int v437; // [rsp+428h] [rbp-3910h]
  int v438; // [rsp+42Ch] [rbp-390Ch]
  int v439; // [rsp+430h] [rbp-3908h]
  int v440; // [rsp+438h] [rbp-3900h]
  int v441; // [rsp+440h] [rbp-38F8h]
  int v442; // [rsp+448h] [rbp-38F0h]
  int v443; // [rsp+44Ch] [rbp-38ECh]
  int v444; // [rsp+450h] [rbp-38E8h]
  int v445; // [rsp+454h] [rbp-38E4h]
  __int64 v446; // [rsp+458h] [rbp-38E0h]
  __int64 v447; // [rsp+460h] [rbp-38D8h]
  __int64 v448; // [rsp+468h] [rbp-38D0h]
  struct CPmoLock *v449; // [rsp+470h] [rbp-38C8h]
  __int64 v450; // [rsp+478h] [rbp-38C0h]
  LARGE_INTEGER PerformanceCount; // [rsp+480h] [rbp-38B8h] BYREF
  CSbTransportMgr *v452; // [rsp+488h] [rbp-38B0h]
  __int64 v453; // [rsp+490h] [rbp-38A8h]
  LARGE_INTEGER v454; // [rsp+498h] [rbp-38A0h] BYREF
  CSbTransportMgr *v455; // [rsp+4A0h] [rbp-3898h]
  CSbTransportMgr *v456; // [rsp+4A8h] [rbp-3890h] BYREF
  __int64 v457; // [rsp+4B0h] [rbp-3888h]
  __int64 v458; // [rsp+4B8h] [rbp-3880h]
  __int64 v459; // [rsp+4C0h] [rbp-3878h]
  int v460; // [rsp+4C8h] [rbp-3870h]
  int v461; // [rsp+4CCh] [rbp-386Ch]
  int v462; // [rsp+4D0h] [rbp-3868h]
  int v463; // [rsp+4D8h] [rbp-3860h]
  __int64 v464; // [rsp+4E0h] [rbp-3858h]
  struct IMemObj *v465; // [rsp+4E8h] [rbp-3850h] BYREF
  _QWORD *v466; // [rsp+4F0h] [rbp-3848h]
  __int64 v467; // [rsp+4F8h] [rbp-3840h]
  char *v468; // [rsp+500h] [rbp-3838h]
  __int64 v469; // [rsp+508h] [rbp-3830h]
  _OWORD *v470; // [rsp+510h] [rbp-3828h]
  void *v471; // [rsp+518h] [rbp-3820h]
  _OWORD *v472; // [rsp+520h] [rbp-3818h]
  __int64 v473; // [rsp+528h] [rbp-3810h]
  struct IMemObj *v474; // [rsp+530h] [rbp-3808h]
  _DWORD *v475; // [rsp+538h] [rbp-3800h]
  CPmoLock *v476; // [rsp+540h] [rbp-37F8h]
  struct IMemObj *v477; // [rsp+548h] [rbp-37F0h]
  int v478; // [rsp+550h] [rbp-37E8h]
  __int64 v479; // [rsp+558h] [rbp-37E0h]
  struct CParamExchange *v480; // [rsp+560h] [rbp-37D8h]
  CExecLvlRepresentation **v481; // [rsp+568h] [rbp-37D0h]
  __int64 v482; // [rsp+570h] [rbp-37C8h]
  int v483; // [rsp+580h] [rbp-37B8h]
  int v484; // [rsp+588h] [rbp-37B0h]
  int v485; // [rsp+58Ch] [rbp-37ACh]
  int v486; // [rsp+590h] [rbp-37A8h]
  int v487; // [rsp+594h] [rbp-37A4h]
  int v488; // [rsp+598h] [rbp-37A0h]
  int v489; // [rsp+5A0h] [rbp-3798h]
  struct CStatement *v490; // [rsp+5A8h] [rbp-3790h]
  char *v491; // [rsp+5B0h] [rbp-3788h]
  int v492; // [rsp+5B8h] [rbp-3780h]
  int v493; // [rsp+5C0h] [rbp-3778h]
  int v494; // [rsp+5C4h] [rbp-3774h]
  int v495; // [rsp+5C8h] [rbp-3770h]
  __int128 v496; // [rsp+5D0h] [rbp-3768h]
  char v497; // [rsp+5E0h] [rbp-3758h]
  __int64 v498; // [rsp+5E8h] [rbp-3750h]
  char v499[8]; // [rsp+5F0h] [rbp-3748h] BYREF
  _WORD v500[4]; // [rsp+5F8h] [rbp-3740h] BYREF
  int v501; // [rsp+600h] [rbp-3738h]
  __int64 **v502; // [rsp+608h] [rbp-3730h]
  char *v503; // [rsp+610h] [rbp-3728h]
  __int64 v504; // [rsp+618h] [rbp-3720h]
  __int64 *v505; // [rsp+620h] [rbp-3718h] BYREF
  int v506; // [rsp+628h] [rbp-3710h]
  __int16 v507; // [rsp+62Ch] [rbp-370Ch]
  __int16 v508; // [rsp+62Eh] [rbp-370Ah]
  wchar_t *v509; // [rsp+630h] [rbp-3708h] BYREF
  int v510; // [rsp+638h] [rbp-3700h]
  __int16 v511; // [rsp+63Ch] [rbp-36FCh]
  __int16 v512; // [rsp+63Eh] [rbp-36FAh]
  wchar_t *v513; // [rsp+640h] [rbp-36F8h] BYREF
  int v514; // [rsp+648h] [rbp-36F0h]
  __int16 v515; // [rsp+64Ch] [rbp-36ECh]
  __int16 v516; // [rsp+64Eh] [rbp-36EAh]
  wchar_t *v517; // [rsp+650h] [rbp-36E8h] BYREF
  int v518; // [rsp+658h] [rbp-36E0h]
  __int16 v519; // [rsp+65Ch] [rbp-36DCh]
  __int16 v520; // [rsp+65Eh] [rbp-36DAh]
  __int64 v521; // [rsp+660h] [rbp-36D8h] BYREF
  int v522; // [rsp+668h] [rbp-36D0h]
  __int16 v523; // [rsp+66Ch] [rbp-36CCh]
  __int16 v524; // [rsp+66Eh] [rbp-36CAh]
  OLECHAR *v525; // [rsp+670h] [rbp-36C8h] BYREF
  int v526; // [rsp+678h] [rbp-36C0h]
  __int16 v527; // [rsp+67Ch] [rbp-36BCh]
  __int16 v528; // [rsp+67Eh] [rbp-36BAh]
  __int64 v529; // [rsp+680h] [rbp-36B8h] BYREF
  int v530; // [rsp+688h] [rbp-36B0h]
  __int16 v531; // [rsp+68Ch] [rbp-36ACh]
  __int16 v532; // [rsp+68Eh] [rbp-36AAh]
  __int64 v533; // [rsp+690h] [rbp-36A8h] BYREF
  int v534; // [rsp+698h] [rbp-36A0h]
  __int16 v535; // [rsp+69Ch] [rbp-369Ch]
  __int16 v536; // [rsp+69Eh] [rbp-369Ah]
  char v537; // [rsp+6A0h] [rbp-3698h] BYREF
  int v538; // [rsp+840h] [rbp-34F8h]
  int v539; // [rsp+844h] [rbp-34F4h]
  __int64 v540; // [rsp+848h] [rbp-34F0h]
  __int64 v541; // [rsp+850h] [rbp-34E8h] BYREF
  int v542; // [rsp+858h] [rbp-34E0h]
  _QWORD *v543; // [rsp+8A0h] [rbp-3498h]
  __int64 *v544; // [rsp+8A8h] [rbp-3490h]
  __int64 v545; // [rsp+8B0h] [rbp-3488h]
  void (__fastcall ***v546)(_QWORD, _QWORD); // [rsp+8B8h] [rbp-3480h]
  __int64 v547; // [rsp+8C0h] [rbp-3478h]
  _QWORD *v548; // [rsp+8C8h] [rbp-3470h]
  __int64 *v549; // [rsp+8D0h] [rbp-3468h]
  __int64 v550; // [rsp+8D8h] [rbp-3460h]
  struct CPmoLock *v551; // [rsp+8E0h] [rbp-3458h]
  __int64 v552; // [rsp+8E8h] [rbp-3450h]
  _QWORD *v553; // [rsp+8F0h] [rbp-3448h]
  __int64 v554; // [rsp+8F8h] [rbp-3440h]
  CSbTransportMgr **v555; // [rsp+900h] [rbp-3438h]
  CSbTransportMgr *v556; // [rsp+908h] [rbp-3430h]
  _WORD *v557; // [rsp+910h] [rbp-3428h]
  bool **v558; // [rsp+918h] [rbp-3420h]
  __int64 *v559; // [rsp+920h] [rbp-3418h]
  __int64 *v560; // [rsp+928h] [rbp-3410h]
  CSbTransportMgr **v561; // [rsp+930h] [rbp-3408h]
  CSbTransportMgr *v562; // [rsp+938h] [rbp-3400h]
  CSbTransportMgr **v563; // [rsp+940h] [rbp-33F8h]
  CSbTransportMgr **v564; // [rsp+948h] [rbp-33F0h]
  __int64 *v565; // [rsp+950h] [rbp-33E8h]
  union _LARGE_INTEGER v566; // [rsp+958h] [rbp-33E0h]
  __int64 v567; // [rsp+960h] [rbp-33D8h]
  __int64 v568; // [rsp+968h] [rbp-33D0h]
  __int64 *v569; // [rsp+970h] [rbp-33C8h]
  unsigned __int64 v570; // [rsp+978h] [rbp-33C0h]
  unsigned __int64 *v571; // [rsp+980h] [rbp-33B8h]
  unsigned __int64 *v572; // [rsp+988h] [rbp-33B0h]
  __int64 *v573; // [rsp+990h] [rbp-33A8h]
  union _LARGE_INTEGER v574; // [rsp+998h] [rbp-33A0h]
  __int64 v575; // [rsp+9A0h] [rbp-3398h]
  __int64 v576; // [rsp+9A8h] [rbp-3390h]
  __int64 *v577; // [rsp+9B0h] [rbp-3388h]
  unsigned __int64 v578; // [rsp+9B8h] [rbp-3380h]
  __int64 v579; // [rsp+9C0h] [rbp-3378h]
  struct CStatement *v580; // [rsp+9C8h] [rbp-3370h]
  _QWORD *v581; // [rsp+9D0h] [rbp-3368h]
  __int64 v582; // [rsp+9D8h] [rbp-3360h]
  struct IMemObj *v583; // [rsp+9E0h] [rbp-3358h]
  wchar_t *v584; // [rsp+9E8h] [rbp-3350h]
  wchar_t *v585; // [rsp+9F0h] [rbp-3348h]
  __int64 v586; // [rsp+9F8h] [rbp-3340h]
  __int64 v587; // [rsp+A00h] [rbp-3338h]
  _BYTE **v588; // [rsp+A08h] [rbp-3330h]
  _BYTE **v589; // [rsp+A10h] [rbp-3328h]
  __int64 v590; // [rsp+A18h] [rbp-3320h]
  _WORD *v591; // [rsp+A20h] [rbp-3318h]
  _DWORD **v592; // [rsp+A28h] [rbp-3310h]
  wchar_t **v593; // [rsp+A30h] [rbp-3308h]
  wchar_t **v594; // [rsp+A38h] [rbp-3300h]
  wchar_t **v595; // [rsp+A40h] [rbp-32F8h]
  __int64 *v596; // [rsp+A48h] [rbp-32F0h]
  OLECHAR **v597; // [rsp+A50h] [rbp-32E8h]
  __int64 *v598; // [rsp+A58h] [rbp-32E0h]
  __int64 *v599; // [rsp+A60h] [rbp-32D8h]
  wchar_t *v600; // [rsp+A68h] [rbp-32D0h]
  wchar_t **v601; // [rsp+A70h] [rbp-32C8h]
  wchar_t *v602; // [rsp+A78h] [rbp-32C0h]
  wchar_t **v603; // [rsp+A80h] [rbp-32B8h]
  wchar_t *v604; // [rsp+A88h] [rbp-32B0h]
  wchar_t **v605; // [rsp+A90h] [rbp-32A8h]
  OLECHAR *v606; // [rsp+A98h] [rbp-32A0h]
  OLECHAR **v607; // [rsp+AA0h] [rbp-3298h]
  __int64 v608; // [rsp+AA8h] [rbp-3290h]
  __int64 *v609; // [rsp+AB0h] [rbp-3288h]
  _WORD *v610; // [rsp+AB8h] [rbp-3280h]
  __int64 **v611; // [rsp+AC0h] [rbp-3278h]
  wchar_t **v612; // [rsp+AC8h] [rbp-3270h]
  wchar_t **v613; // [rsp+AD0h] [rbp-3268h]
  wchar_t **v614; // [rsp+AD8h] [rbp-3260h]
  __int64 *v615; // [rsp+AE0h] [rbp-3258h]
  OLECHAR **v616; // [rsp+AE8h] [rbp-3250h]
  __int64 *v617; // [rsp+AF0h] [rbp-3248h]
  __int64 *v618; // [rsp+AF8h] [rbp-3240h]
  wchar_t *v619; // [rsp+B00h] [rbp-3238h]
  wchar_t **v620; // [rsp+B08h] [rbp-3230h]
  wchar_t *v621; // [rsp+B10h] [rbp-3228h]
  wchar_t **v622; // [rsp+B18h] [rbp-3220h]
  wchar_t *v623; // [rsp+B20h] [rbp-3218h]
  wchar_t **v624; // [rsp+B28h] [rbp-3210h]
  OLECHAR *v625; // [rsp+B30h] [rbp-3208h]
  OLECHAR **v626; // [rsp+B38h] [rbp-3200h]
  __int64 v627; // [rsp+B40h] [rbp-31F8h]
  __int64 *v628; // [rsp+B48h] [rbp-31F0h]
  __int64 v629; // [rsp+B50h] [rbp-31E8h]
  struct CStatement *v630; // [rsp+B58h] [rbp-31E0h]
  _QWORD *v631; // [rsp+B60h] [rbp-31D8h]
  __int64 v632; // [rsp+B68h] [rbp-31D0h]
  struct IMemObj *v633; // [rsp+B70h] [rbp-31C8h]
  wchar_t *v634; // [rsp+B78h] [rbp-31C0h]
  wchar_t *v635; // [rsp+B80h] [rbp-31B8h]
  __int64 v636; // [rsp+B88h] [rbp-31B0h]
  _QWORD **v637; // [rsp+B90h] [rbp-31A8h]
  __int64 v638; // [rsp+B98h] [rbp-31A0h]
  void (__fastcall ***v639)(_QWORD, _QWORD); // [rsp+BA0h] [rbp-3198h]
  __int64 v640; // [rsp+BA8h] [rbp-3190h]
  _QWORD *v641; // [rsp+BB0h] [rbp-3188h]
  __int64 *v642; // [rsp+BB8h] [rbp-3180h]
  __int64 v643; // [rsp+BC0h] [rbp-3178h]
  CGlobalEncryptionTypeDeductionContext *v644; // [rsp+BC8h] [rbp-3170h]
  __int64 v645; // [rsp+BD0h] [rbp-3168h]
  char *v646; // [rsp+BD8h] [rbp-3160h]
  struct CStatement *v647; // [rsp+BE0h] [rbp-3158h]
  struct CStatement *v648; // [rsp+BE8h] [rbp-3150h]
  __int64 v649; // [rsp+BF0h] [rbp-3148h]
  _WORD *v650; // [rsp+BF8h] [rbp-3140h]
  int **v651; // [rsp+C00h] [rbp-3138h]
  struct IMemObj *v652; // [rsp+C08h] [rbp-3130h]
  struct IMemObj *v653; // [rsp+C10h] [rbp-3128h]
  CPmoLock *v654; // [rsp+C18h] [rbp-3120h]
  CPmoLock *v655; // [rsp+C20h] [rbp-3118h]
  CPmoLock *v656; // [rsp+C28h] [rbp-3110h]
  struct CStatement *v657; // [rsp+C30h] [rbp-3108h]
  wchar_t *ParameterPrefixWithoutCaching; // [rsp+C38h] [rbp-3100h]
  _QWORD *v659; // [rsp+C40h] [rbp-30F8h]
  struct IMemObj **v660; // [rsp+C48h] [rbp-30F0h]
  struct IMemObj **v661; // [rsp+C50h] [rbp-30E8h]
  struct IMemObj **v662; // [rsp+C58h] [rbp-30E0h]
  char *v663; // [rsp+C60h] [rbp-30D8h]
  struct IMemObj **v664; // [rsp+C68h] [rbp-30D0h]
  struct IMemObj **v665; // [rsp+C70h] [rbp-30C8h]
  char *v666; // [rsp+C78h] [rbp-30C0h]
  char *v667; // [rsp+C80h] [rbp-30B8h]
  __int64 v668; // [rsp+C88h] [rbp-30B0h]
  __int64 v669; // [rsp+C90h] [rbp-30A8h]
  __int64 v670; // [rsp+C98h] [rbp-30A0h]
  _QWORD *v671; // [rsp+CA0h] [rbp-3098h]
  __int64 *v672; // [rsp+CA8h] [rbp-3090h]
  __int64 v673; // [rsp+CB0h] [rbp-3088h]
  __int64 v674; // [rsp+CB8h] [rbp-3080h]
  void *v675; // [rsp+CC0h] [rbp-3078h]
  __int64 v676; // [rsp+CC8h] [rbp-3070h]
  _OWORD *v677; // [rsp+CD0h] [rbp-3068h]
  __int64 v678; // [rsp+CD8h] [rbp-3060h]
  _OWORD *v679; // [rsp+CE0h] [rbp-3058h]
  _OWORD *v680; // [rsp+CE8h] [rbp-3050h]
  __int64 v681; // [rsp+CF0h] [rbp-3048h]
  _DWORD *v682; // [rsp+CF8h] [rbp-3040h]
  _QWORD *v683; // [rsp+D00h] [rbp-3038h]
  __int64 v684; // [rsp+D08h] [rbp-3030h]
  void *v685; // [rsp+D10h] [rbp-3028h]
  struct CStatement *v686; // [rsp+D18h] [rbp-3020h]
  _OWORD *v687; // [rsp+D20h] [rbp-3018h]
  unsigned __int64 v688; // [rsp+D28h] [rbp-3010h]
  struct CPmoLock *v689; // [rsp+D30h] [rbp-3008h]
  __int64 v690; // [rsp+D38h] [rbp-3000h]
  __int64 v691; // [rsp+D40h] [rbp-2FF8h]
  const struct CEsCompFull *v692; // [rsp+D48h] [rbp-2FF0h]
  CEsComp *v693; // [rsp+D50h] [rbp-2FE8h]
  CEsComp *v694; // [rsp+D58h] [rbp-2FE0h]
  CEsComp *v695; // [rsp+D60h] [rbp-2FD8h]
  _DWORD *v696; // [rsp+D68h] [rbp-2FD0h]
  void *v697; // [rsp+D70h] [rbp-2FC8h]
  _WORD *v698; // [rsp+D78h] [rbp-2FC0h]
  void (__fastcall ***v699)(_QWORD, __int64); // [rsp+D80h] [rbp-2FB8h]
  __int64 v700; // [rsp+D88h] [rbp-2FB0h]
  __int64 v701; // [rsp+D90h] [rbp-2FA8h]
  int *v702; // [rsp+D98h] [rbp-2FA0h]
  struct CStatement *v703; // [rsp+DA0h] [rbp-2F98h]
  __int64 v704; // [rsp+DA8h] [rbp-2F90h]
  struct IMemObj *v705; // [rsp+DB0h] [rbp-2F88h]
  struct IMemObj *v706; // [rsp+DB8h] [rbp-2F80h]
  _QWORD *v707; // [rsp+DC0h] [rbp-2F78h]
  void ***v708; // [rsp+DC8h] [rbp-2F70h]
  __int64 v709; // [rsp+DD0h] [rbp-2F68h]
  __int64 v710; // [rsp+DD8h] [rbp-2F60h]
  void (__fastcall ***v711)(_QWORD, _QWORD); // [rsp+DE0h] [rbp-2F58h]
  __int64 v712; // [rsp+DE8h] [rbp-2F50h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+DF0h] [rbp-2F48h]
  __int64 *v714; // [rsp+DF8h] [rbp-2F40h]
  __int64 v715; // [rsp+E10h] [rbp-2F28h]
  CGlobalEncryptionTypeDeductionContext *v716; // [rsp+E18h] [rbp-2F20h]
  __int64 v717; // [rsp+E20h] [rbp-2F18h]
  void (__fastcall ***v718)(_QWORD, _QWORD); // [rsp+E28h] [rbp-2F10h]
  __int64 v719; // [rsp+E30h] [rbp-2F08h]
  char v720[8]; // [rsp+E40h] [rbp-2EF8h] BYREF
  _WORD v721[4]; // [rsp+E48h] [rbp-2EF0h] BYREF
  int v722; // [rsp+E50h] [rbp-2EE8h]
  _DWORD **v723; // [rsp+E58h] [rbp-2EE0h]
  char *v724; // [rsp+E60h] [rbp-2ED8h]
  __int64 v725; // [rsp+E68h] [rbp-2ED0h]
  _DWORD *v726; // [rsp+E70h] [rbp-2EC8h] BYREF
  int v727; // [rsp+E78h] [rbp-2EC0h]
  __int16 v728; // [rsp+E7Ch] [rbp-2EBCh]
  __int16 v729; // [rsp+E7Eh] [rbp-2EBAh]
  wchar_t *v730; // [rsp+E80h] [rbp-2EB8h] BYREF
  int v731; // [rsp+E88h] [rbp-2EB0h]
  __int16 v732; // [rsp+E8Ch] [rbp-2EACh]
  __int16 v733; // [rsp+E8Eh] [rbp-2EAAh]
  wchar_t *v734; // [rsp+E90h] [rbp-2EA8h] BYREF
  int v735; // [rsp+E98h] [rbp-2EA0h]
  __int16 v736; // [rsp+E9Ch] [rbp-2E9Ch]
  __int16 v737; // [rsp+E9Eh] [rbp-2E9Ah]
  wchar_t *v738; // [rsp+EA0h] [rbp-2E98h] BYREF
  int v739; // [rsp+EA8h] [rbp-2E90h]
  __int16 v740; // [rsp+EACh] [rbp-2E8Ch]
  __int16 v741; // [rsp+EAEh] [rbp-2E8Ah]
  __int64 v742; // [rsp+EB0h] [rbp-2E88h] BYREF
  int v743; // [rsp+EB8h] [rbp-2E80h]
  __int16 v744; // [rsp+EBCh] [rbp-2E7Ch]
  __int16 v745; // [rsp+EBEh] [rbp-2E7Ah]
  OLECHAR *v746; // [rsp+EC0h] [rbp-2E78h] BYREF
  int v747; // [rsp+EC8h] [rbp-2E70h]
  __int16 v748; // [rsp+ECCh] [rbp-2E6Ch]
  __int16 v749; // [rsp+ECEh] [rbp-2E6Ah]
  __int64 v750; // [rsp+ED0h] [rbp-2E68h] BYREF
  int v751; // [rsp+ED8h] [rbp-2E60h]
  __int16 v752; // [rsp+EDCh] [rbp-2E5Ch]
  __int16 v753; // [rsp+EDEh] [rbp-2E5Ah]
  __int64 v754; // [rsp+EE0h] [rbp-2E58h] BYREF
  int v755; // [rsp+EE8h] [rbp-2E50h]
  __int16 v756; // [rsp+EECh] [rbp-2E4Ch]
  __int16 v757; // [rsp+EEEh] [rbp-2E4Ah]
  char v758; // [rsp+EF0h] [rbp-2E48h] BYREF
  int v759; // [rsp+1090h] [rbp-2CA8h]
  int v760; // [rsp+1094h] [rbp-2CA4h]
  __int64 v761; // [rsp+1098h] [rbp-2CA0h]
  _DWORD v762[20]; // [rsp+10A0h] [rbp-2C98h] BYREF
  _OWORD v763[5]; // [rsp+10F0h] [rbp-2C48h] BYREF
  char v764[8]; // [rsp+1140h] [rbp-2BF8h] BYREF
  _WORD v765[4]; // [rsp+1148h] [rbp-2BF0h] BYREF
  int v766; // [rsp+1150h] [rbp-2BE8h]
  bool **v767; // [rsp+1158h] [rbp-2BE0h]
  char *v768; // [rsp+1160h] [rbp-2BD8h]
  __int64 v769; // [rsp+1168h] [rbp-2BD0h]
  bool *v770; // [rsp+1170h] [rbp-2BC8h] BYREF
  int v771; // [rsp+1178h] [rbp-2BC0h]
  __int16 v772; // [rsp+117Ch] [rbp-2BBCh]
  __int16 v773; // [rsp+117Eh] [rbp-2BBAh]
  __int64 v774; // [rsp+1180h] [rbp-2BB8h] BYREF
  int v775; // [rsp+1188h] [rbp-2BB0h]
  __int16 v776; // [rsp+118Ch] [rbp-2BACh]
  __int16 v777; // [rsp+118Eh] [rbp-2BAAh]
  __int64 v778; // [rsp+1190h] [rbp-2BA8h] BYREF
  int v779; // [rsp+1198h] [rbp-2BA0h]
  __int16 v780; // [rsp+119Ch] [rbp-2B9Ch]
  __int16 v781; // [rsp+119Eh] [rbp-2B9Ah]
  char v782; // [rsp+11A0h] [rbp-2B98h] BYREF
  int v783; // [rsp+1390h] [rbp-29A8h]
  int v784; // [rsp+1394h] [rbp-29A4h]
  __int64 v785; // [rsp+1398h] [rbp-29A0h]
  bool v786; // [rsp+13A0h] [rbp-2998h] BYREF
  unsigned __int64 v787; // [rsp+13A1h] [rbp-2997h]
  unsigned __int64 v788; // [rsp+13A9h] [rbp-298Fh]
  char v789; // [rsp+13B1h] [rbp-2987h]
  __int64 v790; // [rsp+13B2h] [rbp-2986h]
  int v791; // [rsp+13BAh] [rbp-297Eh]
  __int128 v792; // [rsp+13D0h] [rbp-2968h]
  char v793[8]; // [rsp+13E0h] [rbp-2958h] BYREF
  _WORD v794[4]; // [rsp+13E8h] [rbp-2950h] BYREF
  int v795; // [rsp+13F0h] [rbp-2948h]
  int **v796; // [rsp+13F8h] [rbp-2940h]
  char *v797; // [rsp+1400h] [rbp-2938h]
  __int64 v798; // [rsp+1408h] [rbp-2930h]
  int *v799; // [rsp+1410h] [rbp-2928h] BYREF
  int v800; // [rsp+1418h] [rbp-2920h]
  __int16 v801; // [rsp+141Ch] [rbp-291Ch]
  __int16 v802; // [rsp+141Eh] [rbp-291Ah]
  char v803; // [rsp+1420h] [rbp-2918h] BYREF
  int v804; // [rsp+1630h] [rbp-2708h]
  int v805; // [rsp+1634h] [rbp-2704h]
  __int64 v806; // [rsp+1638h] [rbp-2700h]
  int v807; // [rsp+1640h] [rbp-26F8h] BYREF
  _OWORD v808[2]; // [rsp+1650h] [rbp-26E8h] BYREF
  struct CAlgStmt *v809; // [rsp+1670h] [rbp-26C8h]
  int v810; // [rsp+1678h] [rbp-26C0h]
  char v811; // [rsp+167Ch] [rbp-26BCh]
  __int64 v812; // [rsp+1680h] [rbp-26B8h]
  GUID v813; // [rsp+1688h] [rbp-26B0h]
  __int64 v814; // [rsp+1698h] [rbp-26A0h]
  __int64 v815; // [rsp+16A0h] [rbp-2698h]
  __int64 v816; // [rsp+16A8h] [rbp-2690h]
  char v817; // [rsp+16B0h] [rbp-2688h]
  __int64 v818; // [rsp+16B8h] [rbp-2680h]
  __int128 v819; // [rsp+16C0h] [rbp-2678h]
  __m128i v820; // [rsp+16D0h] [rbp-2668h]
  __int64 v821; // [rsp+16E0h] [rbp-2658h]
  int v822; // [rsp+16F0h] [rbp-2648h]
  __int64 v823; // [rsp+16F8h] [rbp-2640h]
  __int64 v824; // [rsp+1700h] [rbp-2638h]
  _OWORD v825[2]; // [rsp+1710h] [rbp-2628h] BYREF
  __int64 v826; // [rsp+1730h] [rbp-2608h]
  int v827; // [rsp+1738h] [rbp-2600h]
  char v828; // [rsp+173Ch] [rbp-25FCh]
  __int64 v829; // [rsp+1740h] [rbp-25F8h]
  GUID v830; // [rsp+1748h] [rbp-25F0h]
  __int64 v831; // [rsp+1758h] [rbp-25E0h]
  __int64 v832; // [rsp+1760h] [rbp-25D8h]
  __int64 v833; // [rsp+1768h] [rbp-25D0h]
  char v834; // [rsp+1770h] [rbp-25C8h]
  __int64 v835; // [rsp+1778h] [rbp-25C0h]
  __int128 v836; // [rsp+1780h] [rbp-25B8h]
  __m128i si128; // [rsp+1790h] [rbp-25A8h]
  __int64 v838; // [rsp+17A0h] [rbp-2598h]
  int v839; // [rsp+17B0h] [rbp-2588h]
  __int64 v840; // [rsp+17B8h] [rbp-2580h]
  __int64 v841; // [rsp+17C0h] [rbp-2578h]
  GUID rguid; // [rsp+17D0h] [rbp-2568h] BYREF
  void **v843; // [rsp+17E0h] [rbp-2558h] BYREF
  void ***v844; // [rsp+17E8h] [rbp-2550h]
  int v845; // [rsp+17F0h] [rbp-2548h]
  __int64 v846; // [rsp+17F8h] [rbp-2540h]
  __int64 v847; // [rsp+1800h] [rbp-2538h]
  int v848; // [rsp+1808h] [rbp-2530h]
  int v849; // [rsp+180Ch] [rbp-252Ch]
  __int64 v850; // [rsp+1810h] [rbp-2528h]
  char v851; // [rsp+1818h] [rbp-2520h]
  __int64 v852; // [rsp+1820h] [rbp-2518h]
  __int64 v853; // [rsp+1828h] [rbp-2510h]
  __int64 v854; // [rsp+1834h] [rbp-2504h]
  __int64 v855; // [rsp+183Ch] [rbp-24FCh]
  int v856; // [rsp+3784h] [rbp-5B4h]
  __int16 v857; // [rsp+3788h] [rbp-5B0h]
  __int16 v858; // [rsp+388Ah] [rbp-4AEh]
  __int64 v859; // [rsp+398Ch] [rbp-3ACh]
  __int16 v860; // [rsp+3994h] [rbp-3A4h]
  int v861; // [rsp+3998h] [rbp-3A0h]
  __int64 v862; // [rsp+39A0h] [rbp-398h]
  __int64 v863; // [rsp+39A8h] [rbp-390h]
  wchar_t v864[40]; // [rsp+39B0h] [rbp-388h] BYREF
  wchar_t v865[40]; // [rsp+3A00h] [rbp-338h] BYREF
  wchar_t v866[40]; // [rsp+3A50h] [rbp-2E8h] BYREF
  OLECHAR sz[40]; // [rsp+3AA0h] [rbp-298h] BYREF
  _BYTE v868[256]; // [rsp+3AF0h] [rbp-248h] BYREF
  _BYTE v869[264]; // [rsp+3BF0h] [rbp-148h] BYREF

  v704 = -2;
  v354 = a3;
  v3 = (struct CCompExecCtxt *)a2;
  v310 = (struct CCompExecCtxt *)a2;
  v4 = this;
  v321 = this;
  v400 = this;
  v481 = a2;
  v480 = a3;
  v5 = *((_QWORD *)this + 9);
  v331 = v5;
  if ( !v5 )
  {
    v6 = *((_QWORD *)this + 52);
    if ( v6 )
      v5 = *(_QWORD *)(v6 + 88);
    else
      v5 = 0;
    v331 = v5;
  }
  v482 = v5;
  v479 = v5;
  v458 = v5;
  v457 = v5;
  v448 = v5;
  v447 = v5;
  v446 = v5;
  v297 = v5 != 0;
  v300 = 1;
  v323 = a2[20];
  v353 = 0;
  v299 = 1;
  v317 = 0;
  v7 = *((_DWORD *)this + 8);
  v8 = 0;
  if ( (v7 & 8) != 0 )
  {
    v317 = 1;
    v8 = 1;
  }
  if ( (*((_DWORD *)v4 + 144) & 0x2000000) != 0 && (v7 & 4) != 0 )
    v317 = v8 | 0x12;
  if ( !v5 )
    CSQLSource::CreateCompPlan(v4, v3);
  CSQLSource::SetupTriggerContext(v4, v3);
  if ( CommonGlobalState::m_PerfCountersEnabled )
    PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0xFu, 0x30u, 1, 0);
  if ( (*((_BYTE *)qword_102ECFB10 + 55) & 0x20) != 0
    || (v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v9)
    && (v10 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v9 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v10, 0x1BDu) )
  {
    v175 = *((_DWORD *)v4 + 8);
    if ( (v175 & 8) != 0 )
    {
      CSQLSource::PwsName(v4);
      v176 = CSQLSource::CbName(v4);
      traceprint2(L"Compile issued : ProcName: %.*ls\n", (unsigned __int64)v176 >> 1);
    }
    else if ( (v175 & 4) != 0 )
    {
      traceprint2(L"Compile issued : \n");
      CSQLStrings::Dump(v4);
    }
  }
  v11 = (CProchdr *)*((_QWORD *)v4 + 8);
  v308 = v11;
  v12 = (CCompPlan *)*((_QWORD *)v4 + 9);
  v318 = v12;
  if ( v12 )
  {
    v370 = v12;
    v13 = (char *)v12 + 128;
    goto LABEL_17;
  }
  v164 = *((_QWORD *)v4 + 52);
  if ( v164 )
  {
    v12 = *(CCompPlan **)(v164 + 88);
    v318 = v12;
    v370 = v12;
    if ( v12 )
    {
      v13 = (char *)v12 + 128;
      goto LABEL_17;
    }
  }
  else
  {
    v12 = 0;
    v318 = 0;
    v370 = 0;
  }
  v13 = 0;
LABEL_17:
  v328 = 0;
  v329 = v13;
  if ( !v5 )
  {
    v14 = *((_QWORD *)v11 + 3);
    if ( !*(_DWORD *)(v14 + 8) || (v15 = *(_WORD *)(v14 + 28), v15 == 20801) || v15 == 20816 || v15 == 22597 )
    {
      if ( *((_BYTE *)v11 + 56) )
      {
        memset(v763, 0, 48);
        v174 = *(_QWORD *)(**(_QWORD **)(*(_QWORD *)(*((_QWORD *)v4 + 8) + 176LL) + 8LL) + 104LL);
        WParseName::Parse((WParseName *)v763, *(const wchar_t **)(v174 + 64), *(unsigned __int16 *)(v174 + 72));
        if ( CProchdr::FSetImplicitSchema(*((CProchdr **)v4 + 8), (const struct WParseName *const)v763) )
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 16) + 496LL) + 16LL) = *(_QWORD *)(*((_QWORD *)v4 + 8) + 224LL);
      }
    }
    if ( *((_DWORD *)v4 + 230) == 2 )
      v16 = (struct CEncryptionParamMetadataMap *)*((_QWORD *)v4 + 113);
    else
      v16 = 0;
    CProchdr::BindReturnType(v11, v3, v16);
    v17 = *((_QWORD *)v4 + 8);
    v18 = *(_QWORD *)(v17 + 24);
    if ( !*(_DWORD *)(v18 + 8) || (v19 = *(_WORD *)(v18 + 28), v19 == 20801) || v19 == 20816 || v19 == 22597 )
    {
      if ( *(_BYTE *)(v17 + 56) )
      {
        v172 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v17 + 176) + 72LL) - 178);
        if ( (unsigned int)v172 <= 0x3A )
        {
          v173 = 0x480180020000001LL;
          if ( _bittest64(&v173, v172) )
            CSQLSource::GetNameDependencies(v4, v3, 0);
        }
      }
    }
    v20 = *((_QWORD *)v11 + 3);
    if ( (!*(_DWORD *)(v20 + 8) || (v21 = *(_WORD *)(v20 + 28), v21 == 20801) || v21 == 20816 || v21 == 22597)
      && *((_BYTE *)v11 + 56) )
    {
      v22 = 0;
      v23 = 0;
      v24 = 0;
    }
    else
    {
      v22 = (struct PARAMD *)*((_QWORD *)v11 + 24);
      v23 = *((_DWORD *)v11 + 54);
      v24 = *((_DWORD *)v11 + 55);
    }
    CCompPlan::SetupParamColl(v12, v22, v23, v24);
    CSQLSource::PopulatePlanGuide(v4, v3);
    v25 = *((_QWORD *)v11 + 3);
    if ( *(_DWORD *)(v25 + 8) && (v26 = *(_WORD *)(v25 + 28), v26 != 20801) && v26 != 20816 && v26 != 22597
      || !*((_BYTE *)v11 + 56) )
    {
      if ( CExecLvlRepresentation::FResyncQuery(*((CExecLvlRepresentation **)v3 + 20))
        && v354
        && ((v177 = *((_QWORD *)v4 + 2)) == 0
         || *((_WORD *)v4 + 4) != *(_WORD *)(v177 + 8)
         || (*(_DWORD *)(v177 + 32) & 2) == 0
         && (*((_WORD *)v4 + 4) != *(_WORD *)(v177 + 8)
          || (v178 = *(_QWORD *)(v177 + 16)) == 0
          || (*(_DWORD *)(v178 + 32) & 2) == 0)
         || *((char *)v4 + 445) < 0) )
      {
        v179 = *((_DWORD *)v354 + 7) - *((_DWORD *)v354 + 10);
        v180 = *((_DWORD *)v11 + 54);
        if ( v179 > v180 )
        {
          v181 = *((_QWORD *)v4 + 71);
          v182 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                              + SystemThread_TlsIndex)
                                                            + SystemThread_TlsOffset)
                                                + 160LL)
                                    + 32LL);
          if ( !v182 )
          {
            v183 = *((_QWORD *)v12 + 33);
            if ( *(_DWORD *)(v183 + 120) )
              v182 = 0;
            else
              v182 = *(struct IMemObj **)(v183 + 8);
          }
          v184 = v179 - v180;
          v185 = 8LL * (v179 - v180);
          if ( !is_mul_ok(v179 - v180, 8u) )
            v185 = -1;
          *(_QWORD *)(v181 + 16) = operator new[](v185, v182, "sql\\ntdbms\\cursors\\src\\cursproc.cpp", 3867, 4u);
          v186 = v354;
          do
          {
            *(_QWORD *)(*(_QWORD *)(v181 + 16) + 8LL * (unsigned int)(*(_DWORD *)(v181 + 24))++) = *(_QWORD *)(*((_QWORD *)v186 + 2) + 8LL * (int)(v180 + *((_DWORD *)v186 + 10)));
            ++v180;
          }
          while ( v180 < v179 );
          *((_DWORD *)v186 + 7) -= v184;
          *((_DWORD *)v186 + 9) -= v184;
          v3 = v310;
          v11 = v308;
        }
      }
      if ( *((_DWORD *)v11 + 54) || *((_DWORD *)v11 + 55) || *((_QWORD *)v11 + 24) )
      {
        v147 = *(_QWORD *)(*((_QWORD *)v4 + 8) + 16LL);
        v148 = *((_QWORD *)v4 + 110);
        if ( v148 && (v153 = *(_QWORD *)(v148 + 8)) != 0 )
        {
          v149 = 0;
        }
        else
        {
          v149 = 1;
          v150 = *((_QWORD *)v3 + 16);
          if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(v150 + 336) + 120LL))(v150 + 336) )
          {
            v152 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v150 + 336) + 152LL))(v150 + 336);
          }
          else
          {
            v151 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 18) + 432LL))(*((_QWORD *)v3 + 18));
            v152 = g_metadataFactory(v147, v151, "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp", 8446);
          }
          v153 = v152;
        }
        v409 = v153;
        v410 = v149 != 0;
        v411 = &off_102467C58;
        v412 = 0;
        v413 = v153;
        (*(void (__fastcall **)(__int64, __int64 (__fastcall ***)()))(*(_QWORD *)v153 + 32LL))(v153, &v411);
        memset(v825, 0, sizeof(v825));
        v826 = 0;
        v827 = 0;
        v828 = 0;
        v829 = 0;
        v830 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
        v831 = 0;
        v832 = 0;
        v833 = 0;
        v834 &= 0xFCu;
        v835 = 0;
        v836 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
        v838 = 0;
        v839 = 0;
        v840 = 0;
        v841 = 0;
        v154 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset);
        *(_QWORD *)(v154 + 176) = v825;
        *(_BYTE *)(v154 + 168) = 1;
        **((_QWORD **)v3 + 22) = v153;
        v362 = 0;
        if ( *((_DWORD *)v4 + 230) == 2 )
          v155 = (struct CEncryptionParamMetadataMap *)*((_QWORD *)v4 + 113);
        else
          v155 = 0;
        v156 = (struct CCompPlan *)*((_QWORD *)v4 + 9);
        if ( !v156 )
        {
          v187 = *((_QWORD *)v4 + 52);
          if ( v187 )
            v156 = *(struct CCompPlan **)(v187 + 88);
          else
            v156 = 0;
        }
        v11 = v308;
        CProchdr::ProcessVariables(v308, v3, (*((_DWORD *)v4 + 8) & 4) == 0, v156, v155, &v362);
        if ( *((_DWORD *)v4 + 230) == 2
          && (*((_DWORD *)v4 + 8) & 8) != 0
          && !CExecLvlRepresentation::FInModuleEncryptionDeduction(*((CExecLvlRepresentation **)v3 + 20)) )
        {
          v188 = **(_QWORD **)(*((_QWORD *)v3 + 20) + 24LL);
          if ( *(__int16 *)(*((_QWORD *)v308 + 3) + 56LL) <= 1 )
            v189 = (struct IMEDModule *)(*(__int64 (**)(void))(v188 + 168))();
          else
            v189 = (struct IMEDModule *)(*(__int64 (**)(void))(v188 + 232))();
          CProchdr::CheckParameterEncryptionAgainstMetadata(v308, v189);
        }
        CCompPlan::InitParams(v12, v3, v308, v354, v362, (*((_DWORD *)v4 + 8) & 4) == 0);
        v157 = *((_BYTE *)v4 + 445) ^ (*((_BYTE *)v4 + 445) ^ (8 * v412)) & 8;
        *((_BYTE *)v4 + 445) = v157;
        if ( (v157 & 8) != 0 )
          CSQLSource::SetImplNameres(v4);
        v158 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset);
        *(_QWORD *)(v158 + 176) = 0;
        *(_BYTE *)(v158 + 168) = 0;
        v411 = &off_102467C58;
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v413 + 32LL))(v413, 0);
        if ( v410 )
          (**(void (__fastcall ***)(__int64, __int64))v153)(v153, 1);
        v409 = 0;
      }
      v27 = *((_DWORD *)v4 + 144);
      if ( (v27 & 0x4000) != 0 && (v27 & 0x1000000) != 0 )
      {
        v5 = v331;
        if ( !*(_DWORD *)(*((_QWORD *)v12 + 35) + 16LL) )
        {
          *((_WORD *)v4 + 70) = 20801;
          *(_WORD *)(*((_QWORD *)v12 + 3) + 28LL) = 20801;
        }
      }
      else
      {
        v5 = v331;
      }
    }
LABEL_39:
    v28 = *((_QWORD *)v11 + 40);
    if ( v28 )
      (*(void (__fastcall **)(__int64, CProchdr *))(*(_QWORD *)v28 + 152LL))(v28, v11);
    v29 = (struct CPmoLock *)*((_QWORD *)v12 + 33);
    v399 = v29;
    if ( v5 )
      v29 = 0;
    v352 = v29;
    if ( v29 )
      *((_DWORD *)v29 + 30) = 0;
    v30 = *((_QWORD *)v3 + 16);
    v367 = *(_DWORD *)(v30 + 316);
    v366 = v30;
    v301 = 0;
    v302 = (char *)v12 + 128;
    v296 = 0;
    LODWORD(v322) = 7570;
    v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v32 = *(_QWORD *)(v31 + 256);
    if ( !v32 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v32 = *(_QWORD *)(v31 + 256);
    }
    v407 = *(struct IMemObj **)(v32 + 1000);
    v33 = (CGlobalEncryptionTypeDeductionContext *)operator new(
                                                     0xB0u,
                                                     v407,
                                                     "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp",
                                                     7570,
                                                     3u);
    v369 = (__int64)v33;
    if ( v33 )
    {
      v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v35 = *(_QWORD *)(v34 + 256);
      if ( !v35 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v35 = *(_QWORD *)(v34 + 256);
      }
      v36 = CGlobalEncryptionTypeDeductionContext::CGlobalEncryptionTypeDeductionContext(
              v33,
              *(struct IMemObj **)(v35 + 1000));
    }
    else
    {
      v36 = 0;
    }
    v330 = v36;
    v37 = *((_DWORD *)v4 + 230);
    v38 = v308;
    if ( v37 )
    {
      if ( v37 == 2 )
      {
        *((_QWORD *)v308 + 19) = *((_QWORD *)v4 + 113);
        *((_QWORD *)v38 + 20) = *((_QWORD *)v4 + 114);
      }
    }
    else
    {
      *((_QWORD *)v308 + 21) = v36;
    }
    v39 = (struct CAlgStmt *)*((_QWORD *)v38 + 22);
    while ( 1 )
    {
      v307 = v39;
      if ( !v39 )
      {
        v110 = v323;
LABEL_180:
        v366 = 0;
        if ( (*((_DWORD *)v4 + 144) & 0x10) != 0 )
          ex_raise(2, 0, 25, 7);
        v304[0] = 0;
        CSQLSource::UpdateEncryptionAnalysisState<CCompPlan>(v4, v3, v12, v36, v304);
        if ( (*((_DWORD *)v4 + 144) & 0x10) != 0 )
          ex_raise(2, 0, 25, 7);
        if ( *((_DWORD *)v4 + 230) == 3 )
          CheckTMKeysSentAgainstKeysNeeded(v3, *((struct CColEncryptionKeySet **)v12 + 302), 10);
        if ( !v304[0] )
        {
          v117 = v317;
          if ( (v317 & 5) == 1 )
          {
            if ( (v299 || (v317 & 0x10) != 0) && (*((_BYTE *)v12 + 151) &= ~2u, v299) || (v117 & 2) != 0 )
              *((_BYTE *)v12 + 148) |= 0x80u;
          }
          else
          {
            *((_DWORD *)v4 + 144) |= 0x400u;
            v171 = *((_QWORD *)v4 + 9);
            if ( !v171 )
            {
              v287 = *((_QWORD *)v4 + 52);
              if ( v287 )
                v171 = *(_QWORD *)(v287 + 88);
              else
                v171 = 0;
            }
            LOBYTE(v116) = 1;
            CCache::EventPlanNotCached(v171, 20, v116);
          }
          *((_BYTE *)v12 + 151) |= 1u;
          if ( !v482 )
          {
            v118 = (_DWORD *)*((_QWORD *)v110 + 1);
            if ( (v118[8] & 2) != 0
              && (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)v118 + 352LL))(v118) == 21076
              || (v119 = *((_QWORD *)v110 + 1), (*(_DWORD *)(v119 + 32) & 2) != 0)
              && (v120 = *(_QWORD *)(v119 + 400)) != 0
              && (*(_BYTE *)(v120 + 40) & 2) != 0 )
            {
              if ( !CExecLvlRepresentation::FExtendedTrigger(v110) )
              {
                v288 = *((_QWORD *)v4 + 89);
                if ( v288 )
                  *((_QWORD *)v12 + 38) = *(_QWORD *)(v288 + 56);
              }
            }
            *((_DWORD *)v12 + 36) |= *((_DWORD *)v38 + 26);
            v121 = *((_QWORD *)v110 + 3);
            if ( v121 )
            {
              v159 = *((_QWORD *)v12 + 33);
              v160 = 0;
              if ( !*(_DWORD *)(v159 + 120) )
                v160 = *(struct IMemObj **)(v159 + 8);
              CSECExecAsCompileServices::SetToObject(
                (CCompPlan *)((char *)v12 + 312),
                v160,
                *((struct IMetadataAccess **)v4 + 92),
                *((struct IMEDObject **)v110 + 3));
              v161 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 8LL))(v121);
              LODWORD(v408) = 1;
              HIDWORD(v408) = v161;
              *((_QWORD *)v12 + 36) = v408;
              *((_DWORD *)v12 + 74) = 0;
            }
            if ( (*((_DWORD *)v4 + 144) & 0x400) == 0 )
              *((_BYTE *)v12 + 148) |= 1u;
            CCompPlan::MapControl(v12, *((struct CAlgStmt **)v308 + 22));
            v122 = *((_QWORD *)v3 + 20);
            if ( *(char *)(v122 + 44) < 0
              || CExecLvlRepresentation::FEncryptedLevel(*((CExecLvlRepresentation **)v3 + 20))
              || FCurrentStatementEncrypted()
              || (v123 = *(_QWORD *)(v122 + 8), (*(_DWORD *)(v123 + 32) & 2) != 0) && (*(_BYTE *)(v123 + 579) & 1) == 0 )
            {
              *((_BYTE *)v12 + 148) |= 2u;
              *(_BYTE *)(*((_QWORD *)v3 + 20) + 44LL) |= 0x80u;
            }
            if ( CExecLvlRepresentation::FEncryptedLevel(*((CExecLvlRepresentation **)v3 + 20)) )
              *((_BYTE *)v12 + 148) |= 4u;
            if ( !v300 )
              *((_BYTE *)v12 + 148) &= ~0x20u;
          }
        }
        if ( v36 )
        {
          CGlobalEncryptionTypeDeductionContext::~CGlobalEncryptionTypeDeductionContext(v36);
          operator delete(v36, 0xB0u);
        }
        if ( v301 )
          (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)v301 + 296LL))(v301, v302);
        if ( v352 )
          *((_DWORD *)v352 + 30) = 1;
        v124 = v328;
        if ( v328 )
        {
          (*(void (__fastcall **)(struct CStatement *, _QWORD))(*(_QWORD *)v328 + 528LL))(v328, 0);
          (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)v124 + 296LL))(v124, v329);
        }
        goto LABEL_219;
      }
      v40 = *(CQPCompilationQueue **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                  + SystemThread_TlsIndex)
                                                + SystemThread_TlsOffset
                                                + 8LL)
                                    + 80LL);
      if ( v40 )
        CQPCompilationQueue::ReleaseSemaphoresIfPossibleInternal(v40);
      v41 = *((_QWORD *)v38 + 2);
      v349 = v41;
      v344 = v41;
      if ( v41 )
        v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 104LL))(v41);
      else
        v42 = 0;
      v345 = v42;
      RefreshByValueSEParams(1);
      memset(v808, 0, sizeof(v808));
      v809 = 0;
      v810 = 0;
      v811 = 0;
      v812 = 0;
      v813 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v814 = 0;
      v815 = 0;
      v816 = 0;
      v817 &= 0xFCu;
      v818 = 0;
      v819 = 0;
      v820 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
      v821 = 0;
      v822 = 0;
      v823 = 0;
      v824 = 0;
      v43 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      *(_QWORD *)(v43 + 176) = v808;
      *(_BYTE *)(v43 + 168) = 1;
      v407 = v3;
      v391 = v323;
      v44 = *(_QWORD *)(*((_QWORD *)v4 + 8) + 16LL);
      v45 = *((_QWORD *)v4 + 110);
      if ( v45 && (v50 = *(void (__fastcall ****)(_QWORD, _QWORD))(v45 + 8), (v322 = v50) != 0) )
      {
        v46 = 0;
      }
      else
      {
        v46 = 1;
        v47 = *((_QWORD *)v3 + 16);
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(v47 + 336) + 120LL))(v47 + 336) )
        {
          v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v47 + 336) + 152LL))(v47 + 336);
        }
        else
        {
          v48 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 18) + 432LL))(*((_QWORD *)v3 + 18));
          v49 = g_metadataFactory(v44, v48, "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp", 8446);
        }
        v322 = (void (__fastcall ***)(_QWORD, _QWORD))v49;
        v50 = (void (__fastcall ***)(_QWORD, _QWORD))v49;
      }
      v341 = v50;
      v324 = v46 != 0;
      v342 = v46 != 0;
      v363 = &off_102467C58;
      v364 = 0;
      v365 = v50;
      ((void (__fastcall **)(_QWORD, __int64 (__fastcall ***)()))*v50)[4](v50, &v363);
      v51 = v310;
      **((_QWORD **)v310 + 22) = v50;
      *(_QWORD *)(*((_QWORD *)v51 + 22) + 8LL) = &v363;
      v52 = v307;
      *((_QWORD *)v307 + 11) = *((_QWORD *)v12 + 32);
      v809 = v52;
      *((_DWORD *)v4 + 117) = *((_DWORD *)v52 + 15);
      *((_DWORD *)v4 + 300) = *((_DWORD *)v52 + 14);
      v309 = 0;
      v295 = 0;
      v311 = FIsRecompilableStmt(v52);
      if ( !v311 )
      {
        v145 = *((_QWORD *)v12 + 33);
        v309 = (struct CPmoLock *)v145;
        _InterlockedIncrement((volatile signed __int32 *)v145);
        v320 = v145 + 120;
        if ( *(_DWORD *)(v145 + 120) )
          v60 = 0;
        else
          v60 = *(struct IMemObj **)(v145 + 8);
        v388 = v60;
        v295 = 1;
        v324 = v342;
        v57 = v309;
        v52 = v307;
        goto LABEL_77;
      }
      if ( (*(_BYTE *)(*((_QWORD *)v12 + 3) + 140LL) & 2) != 0 && !v446 )
      {
        v144 = *((_QWORD *)v12 + 33);
        v309 = (struct CPmoLock *)v144;
        _InterlockedIncrement((volatile signed __int32 *)v144);
        v295 = 1;
        v320 = v144 + 120;
        if ( *(_DWORD *)(v144 + 120) )
          v60 = 0;
        else
          v60 = *(struct IMemObj **)(v144 + 8);
        v388 = v60;
        v324 = v342;
        v57 = v309;
        v52 = v307;
        goto LABEL_77;
      }
      v53 = CCache::sm_rgpcsProcCache;
      if ( (*((_BYTE *)v4 + 32) & 0x14) != 0 )
        v53 = *(&CCache::sm_rgpcsProcCache + 1);
      MemoryObject = (struct IMemObj *)CacheStoreWrapper::CreateMemoryObject(v53, *((_QWORD *)v12 + 17), 18, 33554433);
      if ( !MemoryObject )
      {
        LOBYTE(v54) = -117;
        ex_raise_oom(v54);
      }
      v705 = MemoryObject;
      if ( SOS_PublicGlobals::sm_MallocSpyStatus )
        break;
LABEL_71:
      v478 = 7702;
      v706 = MemoryObject;
      v56 = operator new(0x80u, MemoryObject, "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp", 7702, 3u);
      v57 = (struct CPmoLock *)v56;
      v707 = v56;
      if ( v56 )
      {
        *(_DWORD *)v56 = 1;
        v56[1] = MemoryObject;
        v58 = v56 + 3;
        v58[1] = v58;
        *v58 = v58;
        *((_QWORD *)v57 + 5) = 0;
        *((_QWORD *)v57 + 2) = &UnfairRecursiveMutexInternal<SuspendQueueExpSLock,1>::`vftable';
        *((_QWORD *)v57 + 6) = 0;
        *((_QWORD *)v57 + 7) = 0;
        *((_QWORD *)v57 + 9) = 0;
        *((_DWORD *)v57 + 20) = 4194680;
        *((_QWORD *)v57 + 11) = 0;
        *((_QWORD *)v57 + 13) = 0;
        *((_QWORD *)v57 + 12) = 0;
        *((_QWORD *)v57 + 14) = 0;
        *((_DWORD *)v57 + 30) = 0;
        v59 = *((_QWORD *)v57 + 1);
        if ( v59 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      }
      else
      {
        v57 = 0;
      }
      v309 = v57;
      v320 = (__int64)v57 + 120;
      v60 = 0;
      if ( !*((_DWORD *)v57 + 30) )
        v60 = (struct IMemObj *)*((_QWORD *)v57 + 1);
      v388 = v60;
      (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)MemoryObject + 16LL))(MemoryObject);
      v51 = v310;
LABEL_77:
      *((_QWORD *)v323 + 4) = v60;
      if ( !*((_QWORD *)v52 + 31) || *((_QWORD *)v4 + 100) )
      {
        v298 = 0;
      }
      else
      {
        v298 = 1;
        if ( (*((_BYTE *)v52 + 236) & 0x20) == 0 )
        {
          v61 = 1;
          goto LABEL_80;
        }
      }
      v61 = 0;
LABEL_80:
      v303 = v61;
      v62 = *(_QWORD *)(*((_QWORD *)v51 + 14) + 24LL);
      v844 = 0;
      v845 = 0;
      v846 = 0;
      v847 = 0;
      v848 = 0;
      v849 = 1;
      v850 = 0;
      v851 = 1;
      v852 = v62;
      v843 = &CMsgBufferCOut::`vftable';
      v853 = v62;
      v854 = 0;
      v855 = 0;
      v856 = 0;
      v857 = 0;
      v858 = 0;
      v859 = 0;
      v860 = 224;
      v861 = 0;
      v862 = 0;
      v863 = 0;
      v63 = v296 || *((_DWORD *)v52 + 18) == 226;
      v296 = v63;
      v350 = 0;
      v351 = 0;
      if ( !v61 || (v708 = &v843, v66 = *((_QWORD *)v51 + 14), v709 = v66, v65 = *(void ****)(v66 + 24), v65 == &v843) )
      {
        v64 = (void ***)v351;
        v65 = (void ***)*((_QWORD *)&v350 + 1);
        v66 = v350;
      }
      else
      {
        *(_QWORD *)&v350 = v66;
        *((_QWORD *)&v350 + 1) = v65;
        v64 = v844;
        *(_QWORD *)&v351 = v844;
        *((_QWORD *)&v351 + 1) = &v843;
        v844 = v65;
        *(_QWORD *)(v66 + 24) = &v843;
      }
      v67 = v308;
      v68 = *(_QWORD *)(*((_QWORD *)v67 + 2) + 16LL)
          * (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v308 + 2) + 120LL))(*((_QWORD *)v308 + 2));
      v710 = v68;
      v335 = (*(__int64 (__fastcall **)(CSQLSource *))(*(_QWORD *)v321 + 272LL))(v321);
      LOBYTE(v67) = CProchdr::FNormalizeStep(v308, v310, v307, v318, v297, v354, &v353, v335);
      v289 = (struct CPmoLock *)v68;
      v69 = v321;
      CSQLSource::PublishFrontendMemoryUsage(v321, v310, *((_QWORD *)v308 + 2), 1, v289);
      if ( !(_BYTE)v67 )
      {
        v336 = 0;
        if ( v66 )
        {
          *(_QWORD *)(*(_QWORD *)(v66 + 24) + 8LL) = v64;
          *(_QWORD *)(v66 + 24) = v65;
          v350 = 0;
          v351 = 0;
        }
        CMsgBufferCOut::~CMsgBufferCOut((CMsgBufferCOut *)&v843);
        CAutoRefc<CPmoLock>::~CAutoRefc<CPmoLock>(&v309);
        v363 = &off_102467C58;
        (*v365)[4](v365, 0);
        if ( (_BYTE)v324 )
        {
          v711 = v322;
          (**v322)(v322, 1);
        }
        v341 = 0;
        v712 = 0;
        *((_QWORD *)v323 + 4) = 0;
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v714 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v201 = *v714;
        v715 = v201;
        *(_QWORD *)(v201 + 176) = 0;
        *(_BYTE *)(v201 + 168) = 0;
        if ( v349 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v349 + 112LL))(v349, v345);
        v344 = 0;
        v202 = v330;
        v716 = v330;
        if ( v330 )
        {
          CGlobalEncryptionTypeDeductionContext::~CGlobalEncryptionTypeDeductionContext(v330);
          operator delete(v202, 0xB0u);
        }
        if ( v301 )
          (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)v301 + 296LL))(v301, v302);
        if ( v366 )
        {
          *(_DWORD *)(v366 + 316) = v367;
          v366 = 0;
        }
        if ( v352 )
          *((_DWORD *)v352 + 30) = 1;
        v203 = v328;
        if ( v328 )
        {
          (*(void (__fastcall **)(struct CStatement *, _QWORD))(*(_QWORD *)v328 + 528LL))(v328, 0);
          (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)v203 + 296LL))(v203, v329);
        }
        v328 = 0;
        return 0;
      }
      if ( !(unsigned __int8)CTrustedMachineHost::FConfigured(v70)
        || *((_DWORD *)v69 + 230) != 3
        || (v204 = (CExecLvlRepresentation *)*((_QWORD *)v310 + 20), CExecLvlRepresentation::FInternal(v204))
        || CExecLvlRepresentation::FInModule(v204)
        || (*((_DWORD *)v69 + 8) & 8) != 0 && (*((_BYTE *)v69 + 144) & 1) != 0 )
      {
        v71 = v330;
      }
      else
      {
        v71 = v330;
        CGlobalEncryptionTypeDeductionContext::GatherParamEncryptionInfoForStatement(v330, v310, v308, v307);
      }
      if ( *((_DWORD *)v69 + 230) <= 1u )
      {
        CGlobalEncryptionTypeDeductionContext::GatherParamEncryptionInfoForStatement(v71, v310, v308, v307);
        if ( *((_BYTE *)v71 + 152) )
          *((_DWORD *)v69 + 230) = 1;
      }
      v72 = (CMATGen *)*((_QWORD *)v69 + 136);
      if ( v72 )
        CMATGen::AddTSQLStatementToMAT(v72, v308, v307);
      if ( *((_DWORD *)v69 + 230) != 1 )
      {
        v73 = v307;
        v337 = FIsRecompilableStmt(v307);
        if ( v311 == v337 || v448 )
        {
          if ( v295 )
          {
            v449 = 0;
            v383 = 0;
          }
          else
          {
            v449 = v57;
            v383 = v57;
            *(_DWORD *)v320 = 0;
          }
        }
        else
        {
          v388 = CCompPlan::PmoPlanGet(v318);
          *((_QWORD *)v323 + 4) = v388;
          CAutoRefc<CPmoLock>::operator=(&v309, *(_QWORD *)(v146 + 264));
          v551 = v309;
          _InterlockedIncrement((volatile signed __int32 *)v309);
          v449 = 0;
          v383 = 0;
        }
        v74 = v318;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v318 + 2) + 120LL))(*((_QWORD *)v318 + 2));
        if ( v301 )
          (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)v301 + 296LL))(v301, v302);
        v301 = 0;
        v75 = *((_QWORD *)v310 + 16);
        v552 = v75;
        v498 = v75;
        v497 = *(_BYTE *)(v75 + 562);
        *(_BYTE *)(v75 + 562) = v298;
        v553 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v76 = v553[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v554 = v76;
        v77 = *(_QWORD *)(v76 + 256);
        v450 = v77;
        if ( !v77 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v77 = *(_QWORD *)(v76 + 256);
          v450 = v77;
        }
        v78 = *(_QWORD *)(v77 + 600);
        v453 = v78;
        SOS_Task::GetCurrentWorkerTimeInTicks(v78, &v389);
        v555 = &v401;
        v489 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
          v401 = (CSbTransportMgr *)PerformanceCount.QuadPart;
        }
        else
        {
          QuadPart = MEMORY[0x7FFE0008];
          v452 = MEMORY[0x7FFE0008];
          v401 = MEMORY[0x7FFE0008];
          v78 = v453;
        }
        v556 = QuadPart;
        v403 = QuadPart;
        v4 = v321;
        v80 = (*(__int64 (__fastcall **)(CSQLSource *))(*(_QWORD *)v321 + 272LL))(v321);
        v81 = v73;
        v82 = v310;
        v313 = !CCompPlan::FCompileStep(v310, v81, v74, v308, v309, v353, &v301, v80, v297);
        if ( v301 )
        {
          switch ( *((_DWORD *)v301 + 35) )
          {
            case 3:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
            case 9:
            case 0xA:
            case 0xB:
            case 0xC:
            case 0xD:
            case 0xE:
            case 0xF:
            case 0x9E:
            case 0xA1:
            case 0xA7:
            case 0xA8:
            case 0xA9:
            case 0xAA:
            case 0xCC:
            case 0xCD:
            case 0xD2:
            case 0xD3:
            case 0xD4:
            case 0xD5:
            case 0xD6:
              v312 = 1;
              v320 = 0x8000000007LL;
              if ( (char)qword_102EDC9FC >= 0 )
                break;
              v371 = 3;
              v557 = v765;
              v765[0] = 0;
              v765[1] = 3;
              v766 = 0;
              v767 = &v770;
              v768 = &v782;
              v783 = 0;
              v784 = 0;
              v769 = 0;
              v785 = 0;
              v558 = &v770;
              v770 = &v786;
              v771 = 46;
              v772 = 2;
              v773 = 0;
              v559 = &v774;
              v774 = 0;
              v775 = 0;
              v776 = 7;
              v777 = 0;
              v560 = &v778;
              v778 = 0;
              v779 = 0;
              v780 = 8;
              v781 = 0;
              SOS_Task::GetCurrentWorkerTimeInTicks(v78, &v406);
              v561 = &v402;
              v493 = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v454);
                v126 = (CSbTransportMgr *)v454.QuadPart;
              }
              else
              {
                v455 = MEMORY[0x7FFE0008];
                v126 = MEMORY[0x7FFE0008];
              }
              v402 = v126;
              v562 = v126;
              v456 = v126;
              v563 = &v403;
              v564 = &v456;
              if ( v126 < v403 )
                v127 = 0;
              else
                v127 = v126 - v403;
              v348 = v127;
              v404 = v127;
              v565 = (__int64 *)&v404;
              if ( v127 == -1 )
              {
                v128 = -1;
                v129.QuadPart = 0x346DC5D63886594BLL;
                goto LABEL_227;
              }
              v494 = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                v566 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                v567 = 1;
                v420 = 3;
                v421 = 1000;
                v568 = 1000;
                v128 = 1000 * v127 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                v405 = v128;
                v129.QuadPart = 0x346DC5D63886594BLL;
              }
              else
              {
                v569 = (__int64 *)&v404;
                v422 = -4;
                v423 = 10000;
                v129.QuadPart = 0x346DC5D63886594BLL;
                v128 = v127 / 0x2710;
                v570 = v127 / 0x2710;
LABEL_227:
                v405 = v128;
              }
              v788 = v128;
              v571 = &v389;
              v572 = &v406;
              if ( v406 < v389 )
                v130 = 0;
              else
                v130 = v406 - v389;
              v348 = v130;
              v390 = v130;
              v573 = (__int64 *)&v390;
              if ( v130 == -1 )
              {
                v131 = -1;
                goto LABEL_232;
              }
              v424 = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                v129 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                v574 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                v575 = 1;
                v425 = 3;
                v426 = 1000;
                v576 = 1000;
                v131 = 1000 * v130 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                v348 = v131;
              }
              else
              {
                v577 = (__int64 *)&v390;
                v427 = -4;
                v428 = 10000;
                v131 = v130 / 0x2710;
                v578 = v130 / 0x2710;
LABEL_232:
                v348 = v131;
              }
              v787 = v131;
              v786 = v457 != 0;
              LOBYTE(v132) = 19;
              v375 = 19;
              if ( v458 )
              {
                v132 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ISubClassFromXret)(
                         *(unsigned int *)(*(_QWORD *)(*((_QWORD *)v82 + 20) + 8LL) + 616LL),
                         v131,
                         (union _LARGE_INTEGER)v129.QuadPart,
                         *(_QWORD *)&Base_PublicGlobals::sm_invariantTscAvailable);
                v375 = v132;
              }
              v789 = v132;
              v357 = 0;
              v133 = *((_QWORD *)v4 + 52);
              v579 = v133;
              v580 = v301;
              v134 = off_102FE4CB0[2];
              v376 = v134 != 0;
              v135 = off_102FE4CB0[9] != 0;
              v359 = v135;
              v381 = 0;
              v343 = 0;
              v332 = 0;
              v347 = 0;
              v358 = 0;
              v305 = 0;
              v380 = 0;
              v326 = 0;
              LODWORD(v294) = 128;
              if ( v134 )
                StatementInfoBase_1 = TraceUtil::GetStatementInfoBase_1_(
                                        (int)v4,
                                        (int)v301,
                                        v133,
                                        0,
                                        v135,
                                        (TraceUtil *)v868,
                                        v294,
                                        (__int64)&v381,
                                        (int)&v332 + 4,
                                        (__int64)&v343,
                                        (__int64)&v343 + 4,
                                        (__int64)&v332,
                                        (__int64)&v357,
                                        (__int64)&v358,
                                        (__int64)&v305,
                                        (__int64)&v380,
                                        (__int64)&v326);
              else
                StatementInfoBase_1 = TraceUtil::GetStatementInfoBase_0_(
                                        (int)v4,
                                        (int)v301,
                                        v133,
                                        0,
                                        v135,
                                        (TraceUtil *)v868,
                                        v294,
                                        (__int64)&v381,
                                        (int)&v332 + 4,
                                        (__int64)&v343,
                                        (__int64)&v343 + 4,
                                        (__int64)&v332,
                                        (__int64)&v357,
                                        (__int64)&v358,
                                        (__int64)&v305,
                                        (__int64)&v380,
                                        (__int64)&v326);
              v137 = StatementInfoBase_1;
              v356 = StatementInfoBase_1;
              v138 = v358;
              v347 = v358;
              switch ( StatementInfoBase_1 )
              {
                case 1:
                  v138 = L"-- Error: Unknown error. Cannot generate statement text";
                  v347 = L"-- Error: Unknown error. Cannot generate statement text";
                  v305 = 55;
                  break;
                case 2:
                  v138 = L"-- Error: Out of memory. Cannot generate statement text";
                  v347 = L"-- Error: Out of memory. Cannot generate statement text";
                  v305 = 55;
                  break;
                case 3:
                  v138 = (wchar_t *)L"-- Encrypted text";
                  v347 = (wchar_t *)L"-- Encrypted text";
                  v305 = 17;
                  break;
                case 4:
                  if ( v134 )
                  {
                    v305 = v326 + 3;
                    v581 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v210 = v581[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v582 = v210;
                    v211 = *(_QWORD *)(v210 + 256);
                    v459 = v211;
                    if ( !v211 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v211 = *(_QWORD *)(v210 + 256);
                      v459 = v211;
                    }
                    v212 = *(struct IMemObj **)(v211 + 1000);
                    v583 = v212;
                    v213 = 2LL * (v305 + 1);
                    if ( !is_mul_ok(v305 + 1, 2u) )
                      v213 = -1;
                    v214 = (wchar_t *)operator new[](v213, v212, 1, "Sql\\Ntdbms\\msql\\inc\\StatementInfo.h", 322, 3u);
                    v138 = v214;
                    v584 = v214;
                    v358 = v214;
                    v347 = v214;
                    if ( v214 )
                    {
                      v585 = v214;
                      if ( (wchar_t *)v357 != v214 )
                      {
                        v586 = v357;
                        operator delete[]((void *)v357);
                      }
                      v357 = (__int64)v138;
                      DefaultLocale = GetDefaultLocale();
                      LODWORD(v292) = v326;
                      StringCchPrintf_lW(v358, v305 + 1, L"%s%.*s", DefaultLocale, L"-- ", v292, v380);
                      v137 = v356;
                      v135 = v359;
                    }
                    else
                    {
                      v138 = L"-- Error: Out of memory. Cannot generate statement text";
                      v347 = L"-- Error: Out of memory. Cannot generate statement text";
                      v305 = 55;
                      v137 = v356;
                      v135 = v359;
                    }
                  }
                  break;
                case 5:
                case 6:
                  break;
                default:
                  utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\msql\\inc\\StatementInfo.h", 348, "Invalid switch value");
                  break;
              }
              if ( v137 == 3 )
              {
                v790 = 0;
                v791 = 0;
              }
              else
              {
                v790 = v343;
                v791 = v332;
                if ( v135 )
                {
                  v206 = HIDWORD(v332);
                  v495 = HIDWORD(v332);
                  v587 = v381;
                  v207 = v767 + 4;
                  v588 = v767 + 4;
                  v767[4] = (bool *)v381;
                  *((_DWORD *)v207 + 2) = 2 * v206;
                  *((_WORD *)v207 + 6) = 8;
                  *((_WORD *)v207 + 7) = 0;
                }
              }
              if ( v376 )
              {
                v208 = v305;
                v492 = v305;
                v209 = v767 + 2;
                v589 = v767 + 2;
                v767[2] = (bool *)v138;
                *((_DWORD *)v209 + 2) = 2 * v208;
                *((_WORD *)v209 + 6) = 7;
                *((_WORD *)v209 + 7) = 0;
              }
              XeSqlPkg::sql_statement_post_compile::Publish((XeSqlPkg::sql_statement_post_compile *)v764);
              v590 = v357;
              operator delete[]((void *)v357);
              v74 = v318;
              v82 = v310;
              break;
            default:
              v312 = 0;
              break;
          }
        }
        if ( (unsigned int)IsVDWFrontendInstance() )
        {
          if ( CSQLSource::FFireSqlFrontendEvent(v83, v82) )
          {
            if ( v301 )
            {
              v324 = 15;
              v325 = 0x80000000;
              if ( dword_102EDCA1C < 0 || (v460 = 16, v461 = 16, (dword_102EDCA20 & 0x10) != 0) )
              {
                CSQLSource::GetBatchGuids(v4, v864, v865, v866);
                (*(void (__fastcall **)(struct CStatement *, GUID *))(*(_QWORD *)v301 + 88LL))(v301, &rguid);
                UtilGuidToString(&rguid, sz, 0x27u);
                v488 = *((_DWORD *)v301 + 35);
                v792 = *((_OWORD *)&rgSnStmtName + v488);
                v496 = v792;
                v384 = 0x800000000000000FuLL;
                if ( dword_102EDCA1C >= 0 )
                {
                  v220 = v496;
                }
                else
                {
                  v372 = 8;
                  v591 = v721;
                  v721[0] = 0;
                  v721[1] = 8;
                  v722 = 0;
                  v723 = &v726;
                  v724 = &v758;
                  v759 = 0;
                  v760 = 0;
                  v725 = 0;
                  v761 = 0;
                  v592 = &v726;
                  v726 = v762;
                  v727 = 68;
                  v728 = 7;
                  v729 = 0;
                  v593 = &v730;
                  v730 = 0;
                  v731 = 0;
                  v732 = 3;
                  v733 = 0;
                  v594 = &v734;
                  v734 = 0;
                  v735 = 0;
                  v736 = 4;
                  v737 = 0;
                  v595 = &v738;
                  v738 = 0;
                  v739 = 0;
                  v740 = 5;
                  v741 = 0;
                  v596 = &v742;
                  v742 = 0;
                  v743 = 0;
                  v744 = 6;
                  v745 = 0;
                  v597 = &v746;
                  v746 = 0;
                  v747 = 0;
                  v748 = 7;
                  v749 = 0;
                  v598 = &v750;
                  v750 = 0;
                  v751 = 0;
                  v752 = 8;
                  v753 = 0;
                  v599 = &v754;
                  v754 = 0;
                  v755 = 0;
                  v756 = 9;
                  v757 = 0;
                  v600 = v864;
                  v216 = -1;
                  do
                    ++v216;
                  while ( v864[v216] );
                  v487 = 2 * v216;
                  v601 = &v730;
                  v730 = v864;
                  v731 = 2 * v216;
                  v732 = 3;
                  v733 = 0;
                  v602 = v865;
                  v217 = -1;
                  do
                    ++v217;
                  while ( v865[v217] );
                  v486 = 2 * v217;
                  v603 = &v734;
                  v734 = v865;
                  v735 = 2 * v217;
                  v736 = 4;
                  v737 = 0;
                  v604 = v866;
                  v218 = -1;
                  do
                    ++v218;
                  while ( v866[v218] );
                  v485 = 2 * v218;
                  v605 = &v738;
                  v738 = v866;
                  v739 = 2 * v218;
                  v740 = 5;
                  v741 = 0;
                  v606 = sz;
                  v219 = -1;
                  do
                    ++v219;
                  while ( sz[v219] );
                  v444 = 2 * v219;
                  v607 = &v746;
                  v746 = sz;
                  v747 = 2 * v219;
                  v748 = 7;
                  v749 = 0;
                  v220 = v496;
                  v608 = v496;
                  if ( (_QWORD)v496 )
                  {
                    v221 = -1;
                    do
                      ++v221;
                    while ( *(_WORD *)(v496 + 2 * v221) );
                    v222 = 2 * v221;
                  }
                  else
                  {
                    v222 = 0;
                  }
                  v484 = v222;
                  v609 = &v750;
                  v750 = v496;
                  v751 = v222;
                  v752 = 8;
                  v753 = 0;
                  v762[0] = 0;
                  v762[1] = 0;
                  v762[2] = 0;
                  XeSqlPkg::vdw_sql_statement_compiled::Publish((XeSqlPkg::vdw_sql_statement_compiled *)v720);
                }
                v369 = 0x1000000010LL;
                if ( (dword_102EDCA20 & 0x10) != 0 )
                {
                  v373 = 8;
                  v610 = v500;
                  v500[0] = 0;
                  v500[1] = 8;
                  v501 = 0;
                  v502 = &v505;
                  v503 = &v537;
                  v538 = 0;
                  v539 = 0;
                  v504 = 0;
                  v540 = 0;
                  v611 = &v505;
                  v505 = &v541;
                  v506 = 68;
                  v507 = 7;
                  v508 = 0;
                  v612 = &v509;
                  v509 = 0;
                  v510 = 0;
                  v511 = 3;
                  v512 = 0;
                  v613 = &v513;
                  v513 = 0;
                  v514 = 0;
                  v515 = 4;
                  v516 = 0;
                  v614 = &v517;
                  v517 = 0;
                  v518 = 0;
                  v519 = 5;
                  v520 = 0;
                  v615 = &v521;
                  v521 = 0;
                  v522 = 0;
                  v523 = 6;
                  v524 = 0;
                  v616 = &v525;
                  v525 = 0;
                  v526 = 0;
                  v527 = 7;
                  v528 = 0;
                  v617 = &v529;
                  v529 = 0;
                  v530 = 0;
                  v531 = 8;
                  v532 = 0;
                  v618 = &v533;
                  v533 = 0;
                  v534 = 0;
                  v535 = 9;
                  v536 = 0;
                  v619 = v864;
                  v223 = -1;
                  do
                    ++v223;
                  while ( v864[v223] );
                  v463 = 2 * v223;
                  v620 = &v509;
                  v509 = v864;
                  v510 = 2 * v223;
                  v511 = 3;
                  v512 = 0;
                  v621 = v865;
                  v224 = -1;
                  do
                    ++v224;
                  while ( v865[v224] );
                  v445 = 2 * v224;
                  v622 = &v513;
                  v513 = v865;
                  v514 = 2 * v224;
                  v515 = 4;
                  v516 = 0;
                  v623 = v866;
                  v225 = -1;
                  do
                    ++v225;
                  while ( v866[v225] );
                  v439 = 2 * v225;
                  v624 = &v517;
                  v517 = v866;
                  v518 = 2 * v225;
                  v519 = 5;
                  v520 = 0;
                  v625 = sz;
                  v226 = -1;
                  do
                    ++v226;
                  while ( sz[v226] );
                  v437 = 2 * v226;
                  v626 = &v525;
                  v525 = sz;
                  v526 = 2 * v226;
                  v527 = 7;
                  v528 = 0;
                  v627 = v220;
                  if ( v220 )
                  {
                    v227 = -1;
                    do
                      ++v227;
                    while ( *(_WORD *)(v220 + 2 * v227) );
                    v228 = 2 * v227;
                  }
                  else
                  {
                    v228 = 0;
                  }
                  v436 = v228;
                  v628 = &v529;
                  v529 = v220;
                  v530 = v228;
                  v531 = 8;
                  v532 = 0;
                  v541 = 0;
                  v542 = 0;
                  v355 = 0;
                  v229 = *((_QWORD *)v4 + 52);
                  v629 = v229;
                  v630 = v301;
                  v230 = off_103003058[2];
                  v377 = v230 != 0;
                  v435 = 0;
                  v392 = 0;
                  v360 = 0;
                  v333 = 0;
                  v334 = 0;
                  v346 = 0;
                  v368 = 0;
                  v306 = 0;
                  v382 = 0;
                  v327 = 0;
                  LODWORD(v294) = 128;
                  if ( v230 )
                    StatementInfoBase_0 = TraceUtil::GetStatementInfoBase_1_(
                                            (int)v4,
                                            (int)v301,
                                            v229,
                                            0,
                                            0,
                                            (TraceUtil *)v869,
                                            v294,
                                            (__int64)&v392,
                                            (int)&v360,
                                            (__int64)&v333,
                                            (__int64)&v333 + 4,
                                            (__int64)&v334,
                                            (__int64)&v355,
                                            (__int64)&v368,
                                            (__int64)&v306,
                                            (__int64)&v382,
                                            (__int64)&v327);
                  else
                    StatementInfoBase_0 = TraceUtil::GetStatementInfoBase_0_(
                                            (int)v4,
                                            (int)v301,
                                            v229,
                                            0,
                                            0,
                                            (TraceUtil *)v869,
                                            v294,
                                            (__int64)&v392,
                                            (int)&v360,
                                            (__int64)&v333,
                                            (__int64)&v333 + 4,
                                            (__int64)&v334,
                                            (__int64)&v355,
                                            (__int64)&v368,
                                            (__int64)&v306,
                                            (__int64)&v382,
                                            (__int64)&v327);
                  v232 = StatementInfoBase_0;
                  v361 = StatementInfoBase_0;
                  v233 = v368;
                  v346 = v368;
                  switch ( StatementInfoBase_0 )
                  {
                    case 1:
                      v233 = L"-- Error: Unknown error. Cannot generate statement text";
                      v346 = L"-- Error: Unknown error. Cannot generate statement text";
                      v306 = 55;
                      break;
                    case 2:
                      v233 = L"-- Error: Out of memory. Cannot generate statement text";
                      v346 = L"-- Error: Out of memory. Cannot generate statement text";
                      v306 = 55;
                      break;
                    case 3:
                      v233 = (wchar_t *)L"-- Encrypted text";
                      v346 = (wchar_t *)L"-- Encrypted text";
                      v306 = 17;
                      break;
                    case 4:
                      if ( v230 )
                      {
                        v306 = v327 + 3;
                        v631 = NtCurrentTeb()->ThreadLocalStoragePointer;
                        v236 = v631[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                        v632 = v236;
                        v237 = *(_QWORD *)(v236 + 256);
                        v464 = v237;
                        if ( !v237 )
                        {
                          SystemThread::MakeMiniSOSThread(0);
                          v237 = *(_QWORD *)(v236 + 256);
                          v464 = v237;
                        }
                        v238 = *(struct IMemObj **)(v237 + 1000);
                        v633 = v238;
                        v239 = 2LL * (v306 + 1);
                        if ( !is_mul_ok(v306 + 1, 2u) )
                          v239 = -1;
                        v240 = (wchar_t *)operator new[](
                                            v239,
                                            v238,
                                            1,
                                            "Sql\\Ntdbms\\msql\\inc\\StatementInfo.h",
                                            322,
                                            3u);
                        v233 = v240;
                        v634 = v240;
                        v368 = v240;
                        v346 = v240;
                        if ( v240 )
                        {
                          v635 = v240;
                          if ( (wchar_t *)v355 != v240 )
                          {
                            v636 = v355;
                            operator delete[]((void *)v355);
                          }
                          v355 = (__int64)v233;
                          v241 = GetDefaultLocale();
                          LODWORD(v293) = v327;
                          StringCchPrintf_lW(v368, v306 + 1, L"%s%.*s", v241, L"-- ", v293, v382);
                          v232 = v361;
                        }
                        else
                        {
                          v233 = L"-- Error: Out of memory. Cannot generate statement text";
                          v346 = L"-- Error: Out of memory. Cannot generate statement text";
                          v306 = 55;
                          v232 = v361;
                        }
                      }
                      break;
                    case 5:
                    case 6:
                      break;
                    default:
                      utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\msql\\inc\\StatementInfo.h", 348, "Invalid switch value");
                      break;
                  }
                  if ( v232 == 3 )
                  {
                    v541 = 0;
                    v542 = 0;
                  }
                  else
                  {
                    v541 = v333;
                    v542 = v334;
                  }
                  if ( v377 )
                  {
                    v234 = v306;
                    v434 = v306;
                    v235 = v502 + 14;
                    v637 = v502 + 14;
                    v502[14] = (__int64 *)v233;
                    *((_DWORD *)v235 + 2) = 2 * v234;
                    *((_WORD *)v235 + 6) = 9;
                    *((_WORD *)v235 + 7) = 0;
                  }
                  XeSqlPkg::private_vdw_sql_statement_compiled::Publish((XeSqlPkg::private_vdw_sql_statement_compiled *)v499);
                  v638 = v355;
                  operator delete[]((void *)v355);
                }
              }
            }
          }
        }
        if ( *((_DWORD *)v4 + 230) <= 1u && *((_BYTE *)v330 + 152) )
          *((_DWORD *)v4 + 230) = 1;
        v84 = v383;
        if ( !v301 )
          v84 = 0;
        v383 = v84;
        CAutoRefc<CPmoLock>::operator=(&v309, 0);
        *(_BYTE *)(v75 + 562) = v497;
        if ( v84 )
          *((_DWORD *)v84 + 30) = 1;
        if ( v313 )
        {
          v338 = 0;
          v242 = v350;
          if ( (_QWORD)v350 )
          {
            *(_QWORD *)(*(_QWORD *)(v350 + 24) + 8LL) = v351;
            *(_QWORD *)(v242 + 24) = *((_QWORD *)&v350 + 1);
            v350 = 0;
            v351 = 0;
          }
          CMsgBufferCOut::~CMsgBufferCOut((CMsgBufferCOut *)&v843);
          CAutoRefc<CPmoLock>::~CAutoRefc<CPmoLock>(&v309);
          v363 = &off_102467C58;
          (*v365)[4](v365, 0);
          if ( v342 )
          {
            v639 = v322;
            (**v322)(v322, 1);
          }
          v341 = 0;
          v640 = 0;
          *((_QWORD *)v323 + 4) = 0;
          v641 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v642 = (__int64 *)(v641[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v243 = *v642;
          v643 = v243;
          *(_QWORD *)(v243 + 176) = 0;
          *(_BYTE *)(v243 + 168) = 0;
          if ( v349 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v349 + 112LL))(v349, v345);
          v344 = 0;
          v244 = v330;
          v644 = v330;
          if ( v330 )
          {
            CGlobalEncryptionTypeDeductionContext::~CGlobalEncryptionTypeDeductionContext(v330);
            operator delete(v244, 0xB0u);
          }
          if ( v301 )
            (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)v301 + 296LL))(v301, v302);
          if ( v366 )
          {
            *(_DWORD *)(v366 + 316) = v367;
            v366 = 0;
          }
          if ( v352 )
            *((_DWORD *)v352 + 30) = 1;
          v245 = v328;
          if ( v328 )
          {
            (*(void (__fastcall **)(struct CStatement *, _QWORD))(*(_QWORD *)v328 + 528LL))(v328, 0);
            (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)v245 + 296LL))(v245, v329);
          }
          v328 = 0;
          return 0;
        }
        v85 = v301;
        if ( v301 )
        {
          v86 = v307;
          v87 = *((_QWORD *)v307 + 16);
          if ( v87 )
          {
            v645 = *((_QWORD *)v307 + 16);
            if ( (unsigned int)(*(_DWORD *)(v87 + 4) - 2) <= 1 )
            {
              v646 = (char *)v4 + 152;
              if ( !*((_QWORD *)v4 + 20) )
                *((_QWORD *)v4 + 20) = v4;
              *((_DWORD *)v4 + 50) = 0;
              if ( !*((_QWORD *)v4 + 36) )
              {
                v162 = v301;
                v647 = v301;
                v314 = 0;
                if ( (*(unsigned __int8 (__fastcall **)(struct CStatement *, __int64))(*(_QWORD *)v301 + 24LL))(
                       v301,
                       204)
                  && (v648 = v162, (v649 = *((_QWORD *)v162 + 284)) != 0) )
                {
                  v314 = 1;
                  v349 = 0x400000000000000ALL;
                  if ( (qword_102EDCA04 & 0x4000000000000000LL) != 0 )
                  {
                    v374 = 1;
                    v650 = v794;
                    v794[0] = 0;
                    v794[1] = 1;
                    v795 = 0;
                    v796 = &v799;
                    v797 = &v803;
                    v804 = 0;
                    v805 = 0;
                    v798 = 0;
                    v806 = 0;
                    v651 = &v799;
                    v799 = &v807;
                    v800 = 4;
                    v801 = 0;
                    v802 = 0;
                    v807 = 13;
                    XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason::Publish((XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason *)v793);
                  }
                }
                else
                {
                  LOBYTE(v163) = -117;
                  LargeCPMemObj = (struct IMemObj *)CSQLSource::PmoCreateLargeCPMemObj(
                                                      v4,
                                                      *((_QWORD *)v74 + 17),
                                                      18,
                                                      v163,
                                                      33554433);
                  v652 = LargeCPMemObj;
                  v477 = LargeCPMemObj;
                  v433 = 8047;
                  v653 = LargeCPMemObj;
                  v247 = (CPmoLock *)operator new(0x80u, LargeCPMemObj, "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp", 8047, 3u);
                  v654 = v247;
                  if ( v247 )
                    v249 = CPmoLock::CPmoLock(v247, LargeCPMemObj);
                  else
                    v249 = 0;
                  v655 = v249;
                  v398 = v249;
                  v656 = v249;
                  v476 = v249;
                  if ( v249 )
                    *((_DWORD *)v249 + 30) = 0;
                  v250 = 0;
                  if ( !*((_DWORD *)v249 + 30) )
                    v250 = (struct IMemObj *)*((_QWORD *)v249 + 1);
                  v395 = v250;
                  v251 = v301;
                  v657 = v301;
                  if ( !*((_QWORD *)v301 + 254) )
                  {
                    ParameterPrefixWithoutCaching = CSQLSource::GetParameterPrefixWithoutCaching(v248, v86, v250);
                    *((_QWORD *)v251 + 254) = ParameterPrefixWithoutCaching;
                  }
                  v432 = 8058;
                  v252 = operator new(0x30u, v250, "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp", 8058, 1u);
                  v659 = v252;
                  if ( v252 )
                  {
                    v660 = &v393;
                    v661 = &v465;
                    v465 = v250;
                    v662 = &v393;
                    v393 = v250;
                    v663 = (char *)(v252 + 2);
                    v664 = &v394;
                    v665 = &v394;
                    v394 = v250;
                    v666 = (char *)(v252 + 2);
                    v667 = (char *)(v252 + 2);
                    v252[2] = v250;
                    *((_DWORD *)v252 + 7) = 0;
                    *((_DWORD *)v252 + 8) = 4;
                    v252[5] = 0;
                    *v252 = &CRefCount::`vftable';
                    *((_DWORD *)v252 + 2) = 1;
                    *v252 = &DRgDRgPRiGroup::`vftable';
                    v466 = v252;
                  }
                  else
                  {
                    v252 = 0;
                    v466 = 0;
                  }
                  v386 = v252;
                  if ( v252 )
                    v253 = (char *)(v252 + 2);
                  else
                    v253 = 0;
                  v468 = v253;
                  v254 = *((_QWORD *)v86 + 2);
                  if ( v254 )
                  {
                    v668 = *(_QWORD *)(v254 + 16);
                    v255 = *(_QWORD *)(v668 + 680);
                    v469 = v255;
                    if ( v255 )
                    {
                      v256 = 0;
                      v319 = 0;
                      for ( i = 0; (unsigned int)i < *(_DWORD *)(v255 + 28); i = v256 )
                      {
                        v387 = i;
                        v467 = v255 + 16;
                        if ( (unsigned int)i >= *(_DWORD *)(v255 + 28) )
                        {
                          v258 = 0;
                        }
                        else
                        {
                          _mm_lfence();
                          v258 = *(_QWORD *)(*(_QWORD *)(v467 + 24) + 8LL * v387);
                          v253 = v468;
                          v255 = v469;
                          v256 = v319;
                        }
                        v669 = v258;
                        v670 = v258;
                        v259 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v258 + 120) + 72LL))(*(_QWORD *)(v258 + 120));
                        v431 = v259;
                        if ( !*((_QWORD *)v253 + 3) )
                        {
                          v260 = *((_DWORD *)v253 + 4);
                          v430 = v260;
                          *((_QWORD *)v253 + 3) = StdAlloc<CRawMemObjAlloc<0>>::AllocArray<enum EXMLScalarStyle>(
                                                    v253,
                                                    v260);
                          *((_DWORD *)v253 + 4) = v260;
                        }
                        v261 = *((_DWORD *)v253 + 3);
                        if ( v261 >= *((_DWORD *)v253 + 4) )
                        {
                          if ( v261 == -1 )
                          {
                            utassert_fail(
                              1u,
                              "m_cElems < ULONG_MAX",
                              "Sql\\Ntdbms\\include\\common\\stdarray.inl",
                              217,
                              0);
                            v261 = *((_DWORD *)v253 + 3);
                          }
                          CTDynArray<unsigned long,CFnI_FTLCID,CFnD_Noop<unsigned long>,CMemObjAlloc<0>>::DoResize(
                            v253,
                            v261 + 1);
                        }
                        *(_DWORD *)(*((_QWORD *)v253 + 3) + 4LL * (unsigned int)(*((_DWORD *)v253 + 3))++) = v259;
                        v319 = ++v256;
                      }
                    }
                  }
                  v671 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v672 = (__int64 *)(v671[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v673 = *v672;
                  v674 = *(_QWORD *)(v673 + 160);
                  v262 = v674;
                  v263 = CExecLvlRepresentation::Pilm(v323);
                  (*(void (__fastcall **)(struct IInstToLanguageMap *, _QWORD, int *, int *))(*(_QWORD *)v263 + 8LL))(
                    v263,
                    *((unsigned int *)v301 + 17),
                    &v379,
                    &v378);
                  v264 = v378 - v379 + 2;
                  v429 = v264;
                  v462 = v379;
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v262 + 8) + 248LL))(*(_QWORD *)(v262 + 8));
                  v265 = 2 * (((unsigned __int64)v264 >> 1) + 1);
                  if ( !is_mul_ok(((unsigned __int64)v264 >> 1) + 1, 2u) )
                    v265 = -1;
                  v266 = v395;
                  v397 = operator new[](v265, v395, "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp", 8080, 1u);
                  v267 = v397;
                  v471 = v397;
                  v675 = v397;
                  v443 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD))(**(_QWORD **)(v262 + 8) + 240LL))(
                           *(_QWORD *)(v262 + 8),
                           v397,
                           (unsigned int)v264);
                  v267[(unsigned __int64)v443 >> 1] = 0;
                  v268 = v307;
                  v269 = *((_QWORD *)v307 + 16);
                  v676 = v269;
                  v396 = 0;
                  v270 = operator new(0x60u, v266, "sql\\ntdbms\\msql\\proc\\multiplan.cpp", 469, 3u);
                  v271 = v270;
                  v677 = v270;
                  if ( v270 )
                  {
                    *v270 = *(_OWORD *)v269;
                    v270[1] = *(_OWORD *)(v269 + 16);
                    v270[2] = *(_OWORD *)(v269 + 32);
                    v270[3] = *(_OWORD *)(v269 + 48);
                    v270[4] = *(_OWORD *)(v269 + 64);
                    v270[5] = *(_OWORD *)(v269 + 80);
                    v470 = v270;
                    v678 = 0;
                    operator delete(0, 0x60u);
                  }
                  else
                  {
                    v271 = 0;
                    v470 = 0;
                  }
                  *(_QWORD *)(v269 + 8) = 0;
                  *(_QWORD *)(v269 + 16) = 0;
                  *(_QWORD *)(v269 + 24) = 0;
                  *(_QWORD *)(v269 + 32) = 0;
                  v679 = v271;
                  v396 = 0;
                  v680 = v271;
                  v681 = 0;
                  operator delete(0, 0x60u);
                  v272 = v271;
                  v472 = v271;
                  v442 = 8093;
                  v273 = operator new(0x900u, v266, "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp", 8093, 3u);
                  v682 = v273;
                  if ( v273 )
                  {
                    v274 = v386;
                    v683 = v386;
                    v275 = 0;
                    v386 = 0;
                    if ( v683 )
                      v276 = (__int64)(v274 + 2);
                    else
                      v276 = 0;
                    v320 = v276;
                    v684 = v276;
                    v685 = v397;
                    v267 = 0;
                    v471 = 0;
                    v369 = (__int64)v301;
                    v686 = v301;
                    v301 = 0;
                    v687 = v271;
                    v272 = 0;
                    v472 = 0;
                    v384 = *((_QWORD *)v268 + 20);
                    v688 = v384;
                    v315 = CExecLvlRepresentation::FEncrypted(*((CExecLvlRepresentation **)v310 + 20));
                    LODWORD(v322) = *((_DWORD *)v268 + 28);
                    v441 = (int)v322;
                    v324 = *((_DWORD *)v268 + 16);
                    v440 = v324;
                    v277 = v398;
                    v689 = v398;
                    CStatement::CStatement(v273, 273);
                    *(_QWORD *)v273 = &CStmtExecBase::`vftable';
                    v273[548] = 0;
                    v273[549] = 0;
                    *(_QWORD *)v273 = &CStmtMultiPlan::`vftable';
                    *((_QWORD *)v273 + 275) = v397;
                    *((_QWORD *)v273 + 277) = v271;
                    v278 = v369;
                    *((_QWORD *)v273 + 278) = v369;
                    *((_QWORD *)v273 + 279) = v320;
                    *((_QWORD *)v273 + 280) = v384;
                    *((_QWORD *)v273 + 281) = 0;
                    v273[564] = v324;
                    v273[565] = (_DWORD)v322;
                    *((_BYTE *)v273 + 2264) = v315;
                    *((_QWORD *)v273 + 276) = *(_QWORD *)(*((_QWORD *)v273 + 278) + 2032LL);
                    v279 = (_QWORD *)*((_QWORD *)v273 + 278);
                    v320 = v279[14];
                    v473 = v320;
                    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, __int64))(*v279 + 24LL))(v279, 204) )
                    {
                      v690 = v278;
                      v691 = *(_QWORD *)(v278 + 2264);
                      v320 = *(_QWORD *)(v691 + 112);
                      v473 = v320;
                      v280 = 0;
                      if ( !*((_DWORD *)v277 + 30) )
                        v280 = (struct IMemObj *)*((_QWORD *)v277 + 1);
                      v474 = v280;
                      v281 = *(const struct CEsCompFull **)(v278 + 2280);
                      v692 = v281;
                      if ( v281 )
                      {
                        if ( (*((_BYTE *)v281 + 8) & 4) != 0 )
                        {
                          *((_QWORD *)v273 + 281) = CEsCompFull::Clone(v280, v281);
                        }
                        else
                        {
                          v438 = 255;
                          v282 = (CEsComp *)operator new(0x80u, v280, "Sql\\Ntdbms\\include\\esx\\esx_comp.h", 255, 3u);
                          v693 = v282;
                          if ( v282 )
                            v283 = CEsComp::CEsComp(v282);
                          else
                            v283 = 0;
                          v694 = v283;
                          v695 = v283;
                          CEsComp::operator=(v283, v281);
                          *(_BYTE *)(v284 + 8) &= ~4u;
                          *((_QWORD *)v273 + 281) = v284;
                        }
                      }
                    }
                    *((_QWORD *)v273 + 14) = v320;
                    CStatement::SetPmoLock((CStatement *)v273, v277);
                    v475 = v273;
                    v268 = v307;
                  }
                  else
                  {
                    v273 = 0;
                    v475 = 0;
                    v275 = (void (__fastcall ***)(_QWORD, __int64))v386;
                  }
                  if ( v301 )
                    (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)v301 + 296LL))(v301, v302);
                  v301 = (struct CStatement *)v273;
                  v385 = *((_DWORD *)v268 + 14);
                  v696 = v273;
                  v273[17] = v385;
                  v273[18] = 0;
                  *((_QWORD *)v301 + 16) = *((_QWORD *)v268 + 11);
                  (*(void (__fastcall **)(struct CStatement *))(*(_QWORD *)v301 + 536LL))(v301);
                  v697 = v272;
                  operator delete(v272, 0x60u);
                  v698 = v267;
                  operator delete[](v267);
                  v699 = v275;
                  if ( v275 )
                    (**v275)(v275, 1);
                  if ( v476 )
                    *((_DWORD *)v476 + 30) = 1;
                  CAutoRefc<CPmoLock>::~CAutoRefc<CPmoLock>(&v398);
                  if ( v477 )
                    (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)v477 + 16LL))(v477);
                }
              }
              v85 = v301;
            }
          }
          v88 = *((_QWORD *)v85 + 14);
          if ( !v88 )
            goto LABEL_118;
          v700 = v88 + 176;
          v701 = v88 + 200;
          v139 = *(_DWORD *)(v88 + 200);
          v414 = v139;
          v140 = *(_DWORD *)(v88 + 204);
          v415 = v140;
          v141 = *(_DWORD *)(v88 + 208);
          v416 = v141;
          v702 = &v417;
          v142 = *(_DWORD *)(v88 + 212);
          v417 = v142;
          v143 = *(_BYTE *)(v88 + 216);
          v418 = v143;
          if ( !*(_DWORD *)(v88 + 220) )
            goto LABEL_118;
          if ( v139 && v140 != -1 && v141 && (!v143 || v142) )
          {
            v316 = 1;
LABEL_245:
            v89 = 1;
          }
          else
          {
LABEL_118:
            v316 = 0;
            if ( *((_BYTE *)v85 + 136) )
              goto LABEL_245;
            v89 = 0;
          }
          *((_BYTE *)v85 + 136) = v89;
          v90 = v300 && (*(unsigned __int8 (__fastcall **)(struct CStatement *))(*(_QWORD *)v301 + 232LL))(v301);
          v300 = v90;
          if ( v331 )
          {
            v12 = v318;
          }
          else
          {
            v91 = 0;
            if ( (*(unsigned __int8 (__fastcall **)(struct CStatement *, __int64))(*(_QWORD *)v301 + 24LL))(v301, 12) )
              v91 = v301;
            v703 = v91;
            v92 = (*(__int64 (**)(void))(*(_QWORD *)v301 + 136LL))();
            v339 = v92;
            v12 = v318;
            v93 = *((_BYTE *)v318 + 148);
            if ( (v93 & 8) != 0 && v92 )
              v94 = 8;
            else
              v94 = 0;
            *((_BYTE *)v318 + 148) = v94 | v93 & 0xF7;
            v95 = (*(unsigned __int8 (__fastcall **)(struct CStatement *))(*(_QWORD *)v301 + 160LL))(v301)
               || v91 && (*((_BYTE *)v91 + 2236) & 8) != 0;
            v340 = v95;
            v96 = *((_BYTE *)v12 + 148);
            if ( (v96 & 0x40) != 0 || v95 )
              v95 = 64;
            *((_BYTE *)v12 + 148) = v95 | v96 & 0xBF;
            if ( !v296 && (v364 || v91 && (*((_BYTE *)v91 + 2236) & 0x20) != 0) )
            {
              v97 = v321;
              CSQLSource::SetImplNameres(v321);
            }
            else
            {
              v97 = v321;
            }
            if ( ((*(unsigned int (__fastcall **)(struct CStatement *))(*(_QWORD *)v301 + 424LL))(v301)
               || (*(unsigned __int8 (__fastcall **)(struct CStatement *))(*(_QWORD *)v301 + 368LL))(v301))
              && (*((_DWORD *)v97 + 144) & 0x400) == 0 )
            {
              *((_BYTE *)v12 + 148) |= 1u;
            }
          }
          v98 = (*(__int64 (__fastcall **)(struct CStatement *))(*(_QWORD *)v301 + 152LL))(v301);
          v99 = v317 | v98;
          v317 |= v98;
          if ( v299 )
          {
            if ( (v99 & 8) != 0 )
            {
              v99 &= ~8u;
              v317 = v99;
            }
            else
            {
              v299 = 0;
            }
          }
          v100 = IsDWCopyStatementEnabled();
          v101 = (int *)v307;
          if ( v100 && (*((_WORD *)v307 + 112) & 0x4000) != 0 )
            v317 = v99 | 4;
          v102 = (CCompPlan *)((char *)v12 + 128);
          if ( !v12 )
            v102 = 0;
          CMetaStmtSet::StoreStatement((CCompPlan *)((char *)v12 + 152), v102, v307, v301, v399, v297);
          v103 = v310;
          v4 = v321;
          CSQLSource::StorePlanInQDS(v321, v301, v101[16], v101[17], v101[15], v310);
          LOBYTE(v291) = v297;
          LOBYTE(v290) = (*((_DWORD *)v4 + 144) & 0x400) == 0;
          CSQLSource::ExtractQueryParameterizationData(v4, v301, v101, v103, v290, v291, *((_DWORD *)v4 + 154));
          CSQLSource::ExtractIndexAdvisorTrivialPlanData(v4, v301, v104, v105);
          v85 = v301;
        }
        else
        {
          v12 = v318;
          v101 = (int *)v307;
        }
        if ( v298 && v85 && !(*(unsigned __int8 (__fastcall **)(struct CStatement *))(*(_QWORD *)v85 + 368LL))(v85) )
          CSQLSource::SetPlanGuideSuccessForStmt(v4, (struct CAlgStmt *)v101, 1, *((_DWORD *)v12 + 38));
        v106 = v350;
        if ( (_QWORD)v350 )
        {
          *(_QWORD *)(*(_QWORD *)(v350 + 24) + 8LL) = v351;
          *(_QWORD *)(v106 + 24) = *((_QWORD *)&v350 + 1);
          v350 = 0;
          v351 = 0;
        }
        v107 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v108 = *(struct Worker **)(v107 + 256);
        if ( !v108 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v108 = *(struct Worker **)(v107 + 256);
        }
        if ( *((_DWORD *)v108 + 139) )
          ExceptionPostCatchActions(v108);
        LOBYTE(v108) = -119;
        YieldAndCheckForAbort(v108);
        v843 = &CMsgBufferCOut::`vftable';
        CMsgBufferCOut::SendLastError((CMsgBufferCOut *)&v843);
        v843 = &CConnectionOutput::`vftable';
        if ( v309 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v309, 0xFFFFFFFF) == 1 )
          {
            v285 = v309;
            v286 = *((_QWORD *)v309 + 1);
            v408 = v309;
            *(_DWORD *)v309 = -2147426643;
            operator delete(v285, 0x80u);
            if ( v286 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v286 + 240LL))(v286);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v286 + 16LL))(v286);
            }
          }
        }
        v363 = &off_102467C58;
        (*v365)[4](v365, 0);
        if ( v342 && v341 )
          (**v341)(v341, 1);
        v341 = 0;
        *((_QWORD *)v391 + 4) = 0;
        v109 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset);
        *(_QWORD *)(v109 + 176) = 0;
        *(_BYTE *)(v109 + 168) = 0;
        if ( v344 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v344 + 112LL))(v344, v345);
        v344 = 0;
        goto LABEL_159;
      }
      v111 = *((_QWORD *)v308 + 3);
      v717 = v111;
      if ( !*(_DWORD *)(v111 + 8) || (v112 = *(_WORD *)(v111 + 28), v112 == 20801) || v112 == 20816 || v112 == 22597 )
      {
        v101 = (int *)v307;
        if ( *((_BYTE *)v308 + 56) )
        {
          v483 = *((_DWORD *)v307 + 18);
          v113 = (unsigned int)(v483 - 178);
          if ( (unsigned int)v113 <= 0x3A )
          {
            v114 = 0x480180020000001LL;
            if ( _bittest64(&v114, v113) )
            {
              if ( (*((_BYTE *)v308 + 108) & 1) == 0 )
              {
                if ( v66 )
                {
                  *(_QWORD *)(*(_QWORD *)(v66 + 24) + 8LL) = v64;
                  *(_QWORD *)(v66 + 24) = v65;
                  v350 = 0;
                  v351 = 0;
                }
                CMsgBufferCOut::~CMsgBufferCOut((CMsgBufferCOut *)&v843);
                CAutoRefc<CPmoLock>::~CAutoRefc<CPmoLock>(&v309);
                v363 = &off_102467C58;
                (*v365)[4](v365, 0);
                if ( (_BYTE)v324 )
                {
                  v718 = v322;
                  (**v322)(v322, 1);
                }
                v341 = 0;
                v719 = 0;
                v110 = v323;
                *((_QWORD *)v323 + 4) = 0;
                v543 = NtCurrentTeb()->ThreadLocalStoragePointer;
                v544 = (__int64 *)(v543[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                v115 = *v544;
                v545 = v115;
                *(_QWORD *)(v115 + 176) = 0;
                *(_BYTE *)(v115 + 168) = 0;
                if ( v349 )
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v349 + 112LL))(v349, v345);
                v344 = 0;
                v36 = v330;
                v4 = v321;
                v12 = v318;
                v3 = v310;
                v38 = v308;
                goto LABEL_180;
              }
            }
          }
        }
      }
      else
      {
        v101 = (int *)v307;
      }
      if ( v66 )
      {
        *(_QWORD *)(*(_QWORD *)(v66 + 24) + 8LL) = v64;
        *(_QWORD *)(v66 + 24) = v65;
        v350 = 0;
        v351 = 0;
      }
      CMsgBufferCOut::~CMsgBufferCOut((CMsgBufferCOut *)&v843);
      CAutoRefc<CPmoLock>::~CAutoRefc<CPmoLock>(&v309);
      v363 = &off_102467C58;
      (*v365)[4](v365, 0);
      if ( (_BYTE)v324 )
      {
        v546 = v322;
        (**v322)(v322, 1);
      }
      v341 = 0;
      v547 = 0;
      *((_QWORD *)v323 + 4) = 0;
      v548 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v549 = (__int64 *)(v548[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v205 = *v549;
      v550 = v205;
      *(_QWORD *)(v205 + 176) = 0;
      *(_BYTE *)(v205 + 168) = 0;
      if ( v349 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v349 + 112LL))(v349, v345);
      v344 = 0;
      v4 = v321;
      v12 = v318;
LABEL_159:
      v39 = *(struct CAlgStmt **)v101;
      v36 = v330;
      v3 = v310;
      v38 = v308;
    }
    v190 = *((_QWORD *)v52 + 3);
    if ( v190 )
    {
      v199 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v190 + 312LL))(v190);
      v200 = *((_QWORD *)v52 + 3);
      v194 = v199;
      if ( v200 )
      {
        v196 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v200 + 304LL))(
                                  v200,
                                  v198,
                                  v199);
        v194 = v199;
LABEL_387:
        if ( v447 )
          v197 = *(_DWORD *)(*((_QWORD *)v12 + 28) + 16LL * *((int *)v52 + 14) - 8);
        else
          v197 = *((_DWORD *)v52 + 17);
        CStatement::SetDescriptiveNameForPmo(
          MemoryObject,
          v12,
          *((_DWORD *)v52 + 14),
          *((_DWORD *)v52 + 16),
          v197,
          v194,
          v196);
        goto LABEL_71;
      }
    }
    else
    {
      v191 = *((int *)v52 + 18);
      if ( (unsigned int)(v191 - 1) <= 0x2C8 && qword_1024620C0[v191] )
        v192 = (const wchar_t *)qword_1024620C0[v191];
      else
        v192 = L"UNKNOWN TOKEN";
      v193 = -1;
      do
        ++v193;
      while ( v192[v193] );
      v194 = 2 * v193;
    }
    v195 = *((int *)v52 + 18);
    if ( (unsigned int)(v195 - 1) <= 0x2C8 && qword_1024620C0[v195] )
      v196 = (const wchar_t *)qword_1024620C0[v195];
    else
      v196 = L"UNKNOWN TOKEN";
    goto LABEL_387;
  }
  v165 = (char *)v12 + 128;
  if ( !v12 )
    v165 = 0;
  v490 = 0;
  v491 = v165;
  Safe = CMetaStmtSet::PstmtGetSafe(
           (CCompPlan *)((char *)v12 + 152),
           *((_QWORD *)v4 + 57),
           HIDWORD(*((_QWORD *)v4 + 57)));
  v490 = Safe;
  if ( !*((_BYTE *)Safe + 152) || *((_DWORD *)v4 + 154) != 7 )
  {
    v490 = 0;
    v328 = Safe;
    LOBYTE(v167) = 1;
    (*(void (__fastcall **)(struct CStatement *, __int64))(*(_QWORD *)Safe + 528LL))(Safe, v167);
    v168 = *(_DWORD *)(*((_QWORD *)v12 + 35) + 16LL);
    if ( v168 )
    {
      v169 = 0;
      v170 = v168;
      do
      {
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v12 + 35) + 8LL) + v169) + 88LL) = 0;
        v169 += 8;
        --v170;
      }
      while ( v170 );
    }
    _InterlockedIncrement64((volatile signed __int64 *)v12 + 32);
    CSQLSource::PopulatePlanGuide(v4, v3);
    goto LABEL_39;
  }
  (*(void (__fastcall **)(struct CStatement *, char *))(*(_QWORD *)Safe + 296LL))(Safe, v165);
LABEL_219:
  result = 1;
  v328 = 0;
  return result;
}

```

## disassembly

```asm
0x1004692f0  push    rbx
0x1004692f2  push    rsi
0x1004692f3  push    rdi
0x1004692f4  push    r12
0x1004692f6  push    r13
0x1004692f8  push    r14
0x1004692fa  push    r15
0x1004692fc  mov     eax, 3D00h
0x100469301  call    _alloca_probe
0x100469306  sub     rsp, rax
0x100469309  mov     [rsp+3D38h+var_2F90], 0FFFFFFFFFFFFFFFEh
0x100469315  mov     rax, cs:__security_cookie
0x10046931c  xor     rax, rsp
0x10046931f  mov     [rsp+3D38h+var_40], rax
0x100469327  jmp     loc_10045D6E3
0x10045d6e3  mov     rax, r8
0x10045d6e6  mov     [rsp+3D38h+var_3B40], rax
0x10045d6ee  mov     r14, rdx
0x10045d6f1  mov     [rsp+3D38h+var_3C68], rdx
0x10045d6f9  mov     r12, rcx
0x10045d6fc  mov     [rsp+3D38h+var_3C30], rcx
0x10045d704  mov     [rsp+3D38h+var_39F0], rcx
0x10045d70c  mov     [rsp+3D38h+var_37D0], rdx
0x10045d714  mov     [rsp+3D38h+var_37D8], rax
0x10045d71c  mov     rsi, [rcx+48h]
0x10045d720  mov     [rsp+3D38h+var_3BF0], rsi
0x10045d728  xor     r15d, r15d
0x10045d72b  test    rsi, rsi
0x10045d72e  jnz     short loc_10045D74B
0x10045d730  mov     rax, [rcx+1A0h]
0x10045d737  test    rax, rax
0x10045d73a  jnz     loc_1006CBAAC
0x10045d740  mov     rsi, r15
0x10045d743  mov     [rsp+3D38h+var_3BF0], rsi
0x10045d74b  mov     [rsp+3D38h+var_37C8], rsi
0x10045d753  mov     [rsp+3D38h+var_37E0], rsi
0x10045d75b  mov     [rsp+3D38h+var_3880], rsi
0x10045d763  mov     [rsp+3D38h+var_3888], rsi
0x10045d76b  mov     [rsp+3D38h+var_38D0], rsi
0x10045d773  mov     [rsp+3D38h+var_38D8], rsi
0x10045d77b  mov     [rsp+3D38h+var_38E0], rsi
0x10045d783  test    rsi, rsi
0x10045d786  setnz   [rsp+3D38h+var_3CA6]
0x10045d78e  mov     [rsp+3D38h+var_3CA3], 1
0x10045d796  mov     rax, [rdx+0A0h]
0x10045d79d  mov     [rsp+3D38h+var_3C20], rax
0x10045d7a5  mov     [rsp+3D38h+var_3B48], r15d
0x10045d7ad  mov     [rsp+3D38h+var_3CA4], 1
0x10045d7b5  mov     [rsp+3D38h+var_3C4C], r15d
0x10045d7bd  mov     edx, [rcx+20h]
0x10045d7c0  mov     ecx, r15d
0x10045d7c3  mov     eax, edx
0x10045d7c5  shr     eax, 3
0x10045d7c8  mov     ebx, 1
0x10045d7cd  test    bl, al
0x10045d7cf  jnz     loc_100663EF6
0x10045d7d5  mov     eax, [r12+240h]
0x10045d7dd  shr     eax, 19h
0x10045d7e0  test    al, 1
0x10045d7e2  jnz     loc_10126BFB7
0x10045d7e8  test    rsi, rsi
0x10045d7eb  jnz     short loc_10045D7F8
0x10045d7ed  mov     rdx, r14; struct CCompExecCtxt *
0x10045d7f0  mov     rcx, r12; this
0x10045d7f3  call    ?CreateCompPlan@CSQLSource@@AEAAXAEBVCCompExecCtxt@@@Z; CSQLSource::CreateCompPlan(CCompExecCtxt const &)
0x10045d7f8  mov     rdx, r14; struct CCompExecCtxt *
0x10045d7fb  mov     rcx, r12; this
0x10045d7fe  call    ?SetupTriggerContext@CSQLSource@@QEAAXAEBVCCompExecCtxt@@@Z; CSQLSource::SetupTriggerContext(CCompExecCtxt const &)
0x10045d803  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10045d80a  cmp     byte ptr [rax], 0
0x10045d80d  jz      short loc_10045D82D
0x10045d80f  mov     [rsp+3D38h+var_3D18], r15
0x10045d814  mov     r9, rbx
0x10045d817  mov     edx, 0Fh
0x10045d81c  lea     r8d, [rdx+21h]
0x10045d820  mov     rcx, cs:qword_102ECFB00
0x10045d827  call    cs:__imp_?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z; PerfmonManager::IncrementCounterValue(ulong,ulong,__int64,unsigned __int64 *)
0x10045d82d  mov     rax, cs:qword_102ECFB10
0x10045d834  test    byte ptr [rax+37h], 20h
0x10045d838  jnz     loc_10126BFE6
0x10045d83e  mov     r8, gs:58h
0x10045d847  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045d84e  mov     ecx, [rax]
0x10045d850  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045d857  mov     edx, [rax]
0x10045d859  add     rdx, [r8+rcx*8]
0x10045d85d  mov     rax, [rdx]
0x10045d860  test    rax, rax
0x10045d863  jz      short loc_10045D875
0x10045d865  mov     rax, [rax+38h]
0x10045d869  mov     rcx, [rax]
0x10045d86c  test    rcx, rcx
0x10045d86f  jnz     loc_10126BFD3
0x10045d875  mov     rdi, [r12+40h]
0x10045d87a  mov     [rsp+3D38h+var_3C78], rdi
0x10045d882  mov     r13, [r12+48h]
0x10045d887  mov     [rsp+3D38h+var_3C48], r13
0x10045d88f  test    r13, r13
0x10045d892  jz      loc_1006CBAB6
0x10045d898  mov     [rsp+3D38h+var_3AD0], r13
0x10045d8a0  lea     rax, [r13+80h]
0x10045d8a7  jmp     short loc_10045D8AA
0x10045d8aa  mov     [rsp+3D38h+var_3C08], r15
0x10045d8b2  mov     [rsp+3D38h+var_3C00], rax
0x10045d8ba  test    rsi, rsi
0x10045d8bd  jnz     loc_1006CBAF1
0x10045d8c3  mov     rax, [rdi+18h]
0x10045d8c7  mov     ebx, 5845h
0x10045d8cc  cmp     [rax+8], esi
0x10045d8cf  jz      short loc_10045D8E3
0x10045d8d1  movzx   eax, word ptr [rax+1Ch]
0x10045d8d5  mov     ecx, 5141h
0x10045d8da  cmp     ax, cx
0x10045d8dd  jnz     loc_1007635E6
0x10045d8e3  cmp     byte ptr [rdi+38h], 0
0x10045d8e7  jnz     loc_1006FE612
0x10045d8ed  cmp     dword ptr [r12+398h], 2
0x10045d8f6  jz      loc_10126C061
0x10045d8fc  mov     r8, r15; struct CEncryptionParamMetadataMap *
0x10045d8ff  mov     rdx, r14; struct CCompExecCtxt *
0x10045d902  mov     rcx, rdi; this
0x10045d905  call    ?BindReturnType@CProchdr@@QEAAXAEBVCCompExecCtxt@@PEAVCEncryptionParamMetadataMap@@@Z; CProchdr::BindReturnType(CCompExecCtxt const &,CEncryptionParamMetadataMap *)
0x10045d90a  mov     rcx, [r12+40h]
0x10045d90f  mov     rax, [rcx+18h]
0x10045d913  cmp     dword ptr [rax+8], 0
0x10045d917  jz      short loc_10045D92B
0x10045d919  movzx   eax, word ptr [rax+1Ch]
0x10045d91d  mov     edx, 5141h
0x10045d922  cmp     ax, dx
0x10045d925  jnz     loc_100763603
0x10045d92b  cmp     byte ptr [rcx+38h], 0
0x10045d92f  jnz     loc_1006F6D9C
0x10045d935  mov     rax, [rdi+18h]
0x10045d939  cmp     dword ptr [rax+8], 0
0x10045d93d  jz      short loc_10045D951
0x10045d93f  movzx   eax, word ptr [rax+1Ch]
0x10045d943  mov     ecx, 5141h
0x10045d948  cmp     ax, cx
0x10045d94b  jnz     loc_100763620
0x10045d951  cmp     byte ptr [rdi+38h], 0
0x10045d955  jnz     loc_1006F2903
0x10045d95b  mov     rdx, [rdi+0C0h]; struct PARAMD *
0x10045d962  mov     r8d, [rdi+0D8h]; unsigned int
0x10045d969  mov     r9d, [rdi+0DCh]; unsigned int
0x10045d970  mov     rcx, r13; this
0x10045d973  call    ?SetupParamColl@CCompPlan@@QEAAXPEAVPARAMD@@II@Z; CCompPlan::SetupParamColl(PARAMD *,uint,uint)
0x10045d978  mov     rdx, r14; struct CCompExecCtxt *
0x10045d97b  mov     rcx, r12; this
0x10045d97e  call    ?PopulatePlanGuide@CSQLSource@@IEAAXAEBVCCompExecCtxt@@@Z; CSQLSource::PopulatePlanGuide(CCompExecCtxt const &)
0x10045d983  mov     rax, [rdi+18h]
0x10045d987  cmp     dword ptr [rax+8], 0
0x10045d98b  jz      short loc_10045D99F
0x10045d98d  movzx   eax, word ptr [rax+1Ch]
0x10045d991  mov     ecx, 5141h
0x10045d996  cmp     ax, cx
0x10045d999  jnz     loc_10076363D
0x10045d99f  cmp     byte ptr [rdi+38h], 0
0x10045d9a3  jnz     short loc_10045D9FE
0x10045d9a5  mov     rcx, [r14+0A0h]; this
0x10045d9ac  call    ?FResyncQuery@CExecLvlRepresentation@@QEBA_NXZ; CExecLvlRepresentation::FResyncQuery(void)
0x10045d9b1  test    al, al
0x10045d9b3  jnz     loc_10126C06F
0x10045d9b9  cmp     dword ptr [rdi+0D8h], 0
0x10045d9c0  jnz     loc_10066465A
0x10045d9c6  cmp     dword ptr [rdi+0DCh], 0
0x10045d9cd  jnz     loc_10066465A
0x10045d9d3  cmp     qword ptr [rdi+0C0h], 0
0x10045d9db  jnz     loc_10066465A
0x10045d9e1  mov     ecx, [r12+240h]
0x10045d9e9  mov     eax, ecx
0x10045d9eb  shr     eax, 0Eh
0x10045d9ee  test    al, 1
0x10045d9f0  jnz     loc_1006D7C29
0x10045d9f6  mov     rsi, [rsp+3D38h+var_3BF0]
0x10045d9fe  mov     rcx, [rdi+140h]
0x10045da05  test    rcx, rcx
0x10045da08  jz      short loc_10045DA16
0x10045da0a  mov     rax, [rcx]
0x10045da0d  mov     rdx, rdi
0x10045da10  call    qword ptr [rax+98h]
0x10045da16  mov     rax, [r13+108h]
0x10045da1d  mov     [rsp+3D38h+var_39F8], rax
0x10045da25  test    rsi, rsi
0x10045da28  cmovnz  rax, r15
0x10045da2c  mov     [rsp+3D38h+var_3B50], rax
0x10045da34  test    rax, rax
0x10045da37  jz      short loc_10045DA3D
0x10045da39  mov     [rax+78h], r15d
0x10045da3d  mov     rcx, [r14+80h]
0x10045da44  mov     eax, [rcx+13Ch]
0x10045da4a  mov     [rsp+3D38h+var_3AE8], eax
0x10045da51  mov     [rsp+3D38h+var_3AF0], rcx
0x10045da59  lea     rax, [r13+80h]
0x10045da60  mov     [rsp+3D38h+var_3CA0], r15
0x10045da68  mov     [rsp+3D38h+var_3C98], rax
0x10045da70  mov     [rsp+3D38h+var_3CA7], 0
0x10045da78  mov     dword ptr [rsp+3D38h+var_3C28], 1D92h
0x10045da83  mov     rdx, gs:58h
0x10045da8c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045da93  mov     ecx, [rax]
0x10045da95  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045da9c  mov     ebx, [rax]
0x10045da9e  add     rbx, [rdx+rcx*8]
0x10045daa2  mov     rdx, [rbx+100h]
0x10045daa9  test    rdx, rdx
0x10045daac  jz      loc_10126C298
0x10045dab2  mov     rdx, [rdx+3E8h]
0x10045dab9  mov     [rsp+3D38h+var_39B8], rdx
0x10045dac1  mov     byte ptr [rsp+3D38h+var_3D18], 3
0x10045dac6  mov     r9d, 1D92h
0x10045dacc  lea     r8, aSqlNtdbmsMsqlP_112; "sql\\ntdbms\\msql\\proc\\sqlsrc.cpp"
0x10045dad3  mov     ecx, 0B0h
0x10045dad8  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10045dade  mov     rdi, rax
0x10045dae1  mov     [rsp+3D38h+var_3AD8], rax
0x10045dae9  test    rax, rax
0x10045daec  jz      loc_10126C2C2
0x10045daf2  mov     r8, gs:58h
0x10045dafb  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10045db02  mov     edx, [rcx]
0x10045db04  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10045db0b  mov     ebx, [rcx]
0x10045db0d  add     rbx, [r8+rdx*8]
0x10045db11  mov     rdx, [rbx+100h]
0x10045db18  test    rdx, rdx
0x10045db1b  jz      loc_10126C2AD
0x10045db21  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x10045db28  mov     rcx, rdi; this
0x10045db2b  call    ??0CGlobalEncryptionTypeDeductionContext@@QEAA@PEAVIMemObj@@@Z; CGlobalEncryptionTypeDeductionContext::CGlobalEncryptionTypeDeductionContext(IMemObj *)
0x10045db30  mov     rbx, rax
0x10045db33  jmp     short loc_10045DB36
0x10045db36  mov     [rsp+3D38h+var_3BF8], rbx
0x10045db3e  mov     eax, [r12+398h]
0x10045db46  mov     rdi, [rsp+3D38h+var_3C78]
0x10045db4e  test    eax, eax
0x10045db50  jz      loc_10066464D
0x10045db56  cmp     eax, 2
0x10045db59  jz      loc_10126C2CB
0x10045db5f  mov     rsi, [rdi+0B0h]
0x10045db66  mov     [rsp+3D38h+var_3C80], rsi
0x10045db6e  test    rsi, rsi
0x10045db71  jz      loc_10046A71B
0x10045db77  mov     rdx, gs:58h
0x10045db80  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045db87  mov     ecx, [rax]
0x10045db89  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045db90  mov     eax, [rax]
0x10045db92  add     rax, [rdx+rcx*8]
0x10045db96  mov     rax, [rax+8]
0x10045db9a  mov     rcx, [rax+50h]; this
0x10045db9e  test    rcx, rcx
0x10045dba1  jz      short loc_10045DBA8
0x10045dba3  call    ?ReleaseSemaphoresIfPossibleInternal@CQPCompilationQueue@@AEAAXXZ; CQPCompilationQueue::ReleaseSemaphoresIfPossibleInternal(void)
0x10045dba8  mov     rcx, [rdi+10h]
0x10045dbac  mov     [rsp+3D38h+var_3B78], rcx
0x10045dbb4  mov     [rsp+3D38h+var_3BA0], rcx
0x10045dbbc  test    rcx, rcx
0x10045dbbf  jz      loc_10126C2EF
0x10045dbc5  mov     rax, [rcx]
0x10045dbc8  call    qword ptr [rax+68h]
0x10045dbcb  jmp     short loc_10045DBCE
0x10045dbce  mov     [rsp+3D38h+var_3B98], rax
0x10045dbd6  mov     ecx, 1
0x10045dbdb  call    ?RefreshByValueSEParams@@YAXW4ESEParamRefreshOptions@@@Z; RefreshByValueSEParams(ESEParamRefreshOptions)
0x10045dbe0  xorps   xmm0, xmm0
0x10045dbe3  movdqa  [rsp+3D38h+var_26E8], xmm0
0x10045dbec  xorps   xmm1, xmm1
0x10045dbef  movdqa  [rsp+3D38h+var_26D8], xmm1
0x10045dbf8  mov     [rsp+3D38h+var_26C8], r15
0x10045dc00  mov     [rsp+3D38h+var_26C0], r15d
0x10045dc08  mov     [rsp+3D38h+var_26BC], 0
0x10045dc10  mov     [rsp+3D38h+var_26B8], r15
0x10045dc18  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x10045dc1f  movups  [rsp+3D38h+var_26B0], xmm0
0x10045dc27  mov     [rsp+3D38h+var_26A0], r15
0x10045dc2f  mov     [rsp+3D38h+var_2698], r15
0x10045dc37  mov     [rsp+3D38h+var_2690], 0
0x10045dc43  and     [rsp+3D38h+var_2688], 0FCh
0x10045dc4b  mov     [rsp+3D38h+var_2680], r15
0x10045dc53  xorps   xmm0, xmm0
0x10045dc56  movdqa  [rsp+3D38h+var_2678], xmm0
0x10045dc5f  movdqa  xmm1, cs:__xmm@ffffffffffffffff0000000000000000
0x10045dc67  movdqa  [rsp+3D38h+var_2668], xmm1
0x10045dc70  mov     [rsp+3D38h+var_2658], r15
0x10045dc78  mov     [rsp+3D38h+var_2648], 0
0x10045dc83  mov     [rsp+3D38h+var_2640], r15
0x10045dc8b  mov     [rsp+3D38h+var_2638], r15
0x10045dc93  mov     r8, gs:58h
0x10045dc9c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045dca3  mov     ecx, [rax]
0x10045dca5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045dcac  mov     edx, [rax]
0x10045dcae  add     rdx, [r8+rcx*8]
0x10045dcb2  mov     rax, [rdx]
0x10045dcb5  lea     rcx, [rsp+3D38h+var_26E8]
0x10045dcbd  mov     [rax+0B0h], rcx
0x10045dcc4  mov     byte ptr [rax+0A8h], 1
0x10045dccb  mov     [rsp+3D38h+var_39B8], r14
0x10045dcd3  mov     rax, [rsp+3D38h+var_3C20]
0x10045dcdb  mov     [rsp+3D38h+var_3A38], rax
  ... truncated ...
```
