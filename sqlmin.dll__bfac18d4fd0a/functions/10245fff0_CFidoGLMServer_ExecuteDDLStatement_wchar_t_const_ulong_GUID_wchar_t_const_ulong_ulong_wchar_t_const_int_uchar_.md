# CFidoGLMServer::ExecuteDDLStatement(wchar_t * const,ulong,_GUID,wchar_t * const,ulong,ulong,wchar_t const *,int,uchar const *,int,ushort,wchar_t const *,int,wchar_t const *,int,wchar_t * const,ulong,uint,unsigned __int64 *,_GUID const *,unsigned __int64,FidoTransportGlmExecuteDDLRes * *,uchar * *,ulong *,bool *,wchar_t const *,ulong)

- ea: `0x10245fff0`
- end: `0x1024614b3`
- name: `?ExecuteDDLStatement@CFidoGLMServer@@QEAA_NQEA_WKU_GUID@@0KKPEB_WHPEBEHG2H2H0KIPEA_KPEBU2@_KPEAPEAUFidoTransportGlmExecuteDDLRes@@PEAPEAEPEAKPEA_N2K@Z`
- size: `5315`
- prototype: `bool __fastcall(CFidoGLMServer *__hidden this, wchar_t *const, unsigned int, struct _GUID *, wchar_t *const, unsigned int, unsigned int, const wchar_t *, int, const unsigned __int8 *, int, unsigned __int16, const wchar_t *, int, const wchar_t *, int, wchar_t *const, unsigned int, unsigned int, unsigned __int64 *, const struct _GUID *, unsigned __int64, struct FidoTransportGlmExecuteDDLRes **, unsigned __int8 **, unsigned int *, bool *, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x102440720`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100401fcf`
- `0x100415e90`
- `0x1004abbd0`
- `0x1004bff60`
- `0x1006e0e20`
- `0x101ddcae0`
- `0x1023adf80`
- `0x1023e1350`
- `0x1023e1380`
- `0x1023ecca0`
- `0x102444980`
- `0x102444c00`
- `0x10245fff0`

## import_xrefs

- `ole32!StringFromGUID2` at `0x10246103f`
- `ole32!StringFromGUID2` at `0x10246113d`
- `ole32!StringFromGUID2` at `0x10246103f`
- `ole32!StringFromGUID2` at `0x10246113d`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x102460cde`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x102460cde`
- `sqlTsEs!?FEqW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x102460cf6`
- `sqlTsEs!?FEqW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x102460cf6`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x102460a51`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x10246146d`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x102460a51`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x10246146d`
- `sqldk!??0ErrMsgsBase@@QEAA@PEAVIMemObj@@@Z` at `0x102460202`
- `sqldk!??0ErrMsgsBase@@QEAA@PEAVIMemObj@@@Z` at `0x102460202`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x102460f39`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x102460f5e`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x1024610ac`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x1024611f1`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x102460f39`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x102460f5e`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x1024610ac`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x1024611f1`
- `sqldk!?GetMsg@ErrMsg@@QEBAPEB_WPEAH@Z` at `0x1024610c6`
- `sqldk!?GetMsg@ErrMsg@@QEBAPEB_WPEAH@Z` at `0x1024610c6`
- `sqldk!?SetSessionTrace@CSessionTraceFlags@@SA_NKW4FlagUsage@CGlobalTraceFlags@@@Z` at `0x102460b93`
- `sqldk!?SetSessionTrace@CSessionTraceFlags@@SA_NKW4FlagUsage@CGlobalTraceFlags@@@Z` at `0x102460b93`
- `sqldk!?ClearSessionTrace@CSessionTraceFlags@@SA_NKW4FlagUsage@CGlobalTraceFlags@@@Z` at `0x102460d75`
- `sqldk!?ClearSessionTrace@CSessionTraceFlags@@SA_NKW4FlagUsage@CGlobalTraceFlags@@@Z` at `0x102460d75`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1024609cb`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x102460dbf`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10246139f`
- `sqldk!?g_pfnAutoSetupContextForInternalTasksFactory@@3P6APEAVIAutoSetupExecContextsForInternalTasksImpl@@W4thread_type@@FPEB_W@ZEA` at `0x10246018e`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x102460e7a`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1024613fa`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x102460e7a`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1024613fa`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x102460af0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102460685`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102460eb6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102460685`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102460eb6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1024601e4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1024601e4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102460466`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102460547`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1024607c4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102461229`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10246127a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102460466`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102460547`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1024607c4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102461229`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10246127a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102460b82`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102460b82`
- `sqldk!SystemThread_TlsIndex` at `0x10246016f`
- `sqldk!SystemThread_TlsIndex` at `0x102460222`
- `sqldk!SystemThread_TlsIndex` at `0x10246025e`
- `sqldk!SystemThread_TlsIndex` at `0x1024602f1`
- `sqldk!SystemThread_TlsIndex` at `0x102460323`
- `sqldk!SystemThread_TlsIndex` at `0x10246035a`
- `sqldk!SystemThread_TlsIndex` at `0x10246049f`
- `sqldk!SystemThread_TlsIndex` at `0x1024604d8`
- `sqldk!SystemThread_TlsIndex` at `0x1024605c9`
- `sqldk!SystemThread_TlsIndex` at `0x102460b20`
- `sqldk!SystemThread_TlsIndex` at `0x102460e3a`
- `sqldk!SystemThread_TlsIndex` at `0x1024613c2`
- `sqldk!SystemThread_TlsOffset` at `0x102460178`
- `sqldk!SystemThread_TlsOffset` at `0x10246022b`
- `sqldk!SystemThread_TlsOffset` at `0x102460267`
- `sqldk!SystemThread_TlsOffset` at `0x1024602fa`
- `sqldk!SystemThread_TlsOffset` at `0x10246032c`
- `sqldk!SystemThread_TlsOffset` at `0x10246036b`
- `sqldk!SystemThread_TlsOffset` at `0x1024604a8`
- `sqldk!SystemThread_TlsOffset` at `0x1024604e1`
- `sqldk!SystemThread_TlsOffset` at `0x1024605d2`
- `sqldk!SystemThread_TlsOffset` at `0x102460b29`
- `sqldk!SystemThread_TlsOffset` at `0x102460e43`
- `sqldk!SystemThread_TlsOffset` at `0x1024613cb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1024603ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102460e5c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1024613e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1024603ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102460e5c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1024613e4`
- `sqldk!??_V@YAXPEAX@Z` at `0x102460995`
- `sqldk!??_V@YAXPEAX@Z` at `0x102460a86`
- `sqldk!??_V@YAXPEAX@Z` at `0x102461365`
- `sqldk!??_V@YAXPEAX@Z` at `0x102460995`
- `sqldk!??_V@YAXPEAX@Z` at `0x102460a86`
- `sqldk!??_V@YAXPEAX@Z` at `0x102461365`
- `sqllang!?SetStorageToken@CSession@@QEAA_NPEB_WK@Z` at `0x10246034b`
- `sqllang!?SetStorageToken@CSession@@QEAA_NPEB_WK@Z` at `0x10246034b`
- `sqllang!?DisableAutoDropTempTable@CFidoTempObjectList@@QEAAXXZ` at `0x1024603e8`
- `sqllang!?DisableAutoDropTempTable@CFidoTempObjectList@@QEAAXXZ` at `0x1024603e8`
- `sqllang!?Deserialize@CFidoTempObjectList@@QEAAXPEB_WK@Z` at `0x1024603f7`
- `sqllang!?Deserialize@CFidoTempObjectList@@QEAAXPEB_WK@Z` at `0x1024603f7`
- `sqllang!?Restore@CAutoImpersonateForVdw@@QEAAXXZ` at `0x102460d63`
- `sqllang!?Restore@CAutoImpersonateForVdw@@QEAAXXZ` at `0x102460d8d`
- `sqllang!?Restore@CAutoImpersonateForVdw@@QEAAXXZ` at `0x102460d63`
- `sqllang!?Restore@CAutoImpersonateForVdw@@QEAAXXZ` at `0x102460d8d`
- `sqllang!?SetData@CAutoImpersonateForVdw@@QEAAXKW4SDSPrincipalType@@PEB_WKPEBEK1K1KG@Z` at `0x102460cc2`
- `sqllang!?SetData@CAutoImpersonateForVdw@@QEAAXKW4SDSPrincipalType@@PEB_WKPEBEK1K1KG@Z` at `0x102460cc2`
- `sqllang!?Impersonate@CAutoImpersonateForVdw@@QEAAXPEAVIMemObj@@@Z` at `0x102460d22`
- `sqllang!?Impersonate@CAutoImpersonateForVdw@@QEAAXPEAVIMemObj@@@Z` at `0x102460d22`
- `sqllang!?Clear@CFidoTempObjectList@@QEAAXXZ` at `0x10246135c`
- `sqllang!?Clear@CFidoTempObjectList@@QEAAXXZ` at `0x10246135c`
- `sqllang!?Restore@CAutoExecuteAsContext@@QEAAXXZ` at `0x102460dd2`
- `sqllang!?Restore@CAutoExecuteAsContext@@QEAAXXZ` at `0x102460dd2`
- `sqllang!?InitializeAndOverride@AutoOverrideMsqlXact@@QEAAXXZ` at `0x102460420`
- `sqllang!?InitializeAndOverride@AutoOverrideMsqlXact@@QEAAXXZ` at `0x102460420`
- `sqllang!??1AutoOverrideMsqlXact@@QEAA@XZ` at `0x1024609de`
- `sqllang!??1AutoOverrideMsqlXact@@QEAA@XZ` at `0x1024613b2`
- `sqllang!??1AutoOverrideMsqlXact@@QEAA@XZ` at `0x1024609de`
- `sqllang!??1AutoOverrideMsqlXact@@QEAA@XZ` at `0x1024613b2`
- `sqllang!??1CConnectionOutput@@UEAA@XZ` at `0x102460a3d`
- `sqllang!??1CConnectionOutput@@UEAA@XZ` at `0x102461459`
- `sqllang!??1CConnectionOutput@@UEAA@XZ` at `0x102460a3d`
- `sqllang!??1CConnectionOutput@@UEAA@XZ` at `0x102461459`
- `sqllang!??0CDeferMsgsConnOut@@QEAA@PEAVErrMsgs@@PEAVCConnectionOutput@@@Z` at `0x10246024e`
- `sqllang!??0CDeferMsgsConnOut@@QEAA@PEAVErrMsgs@@PEAVCConnectionOutput@@@Z` at `0x10246024e`

## string_xrefs

- `0x10246053d`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=28 #try_helpers=1
__int64 __fastcall CFidoGLMServer::ExecuteDDLStatement(
        struct IMemObj **this,
        wchar_t *const a2,
        int a3,
        struct _GUID *a4,
        wchar_t *const a5,
        unsigned int a6,
        unsigned int a7,
        const wchar_t *a8,
        int a9,
        const unsigned __int8 *a10,
        int a11,
        unsigned __int16 a12,
        const wchar_t *a13,
        int a14,
        const wchar_t *a15,
        int a16,
        wchar_t *const a17,
        unsigned int a18,
        unsigned int a19,
        unsigned __int64 *a20,
        struct _GUID *a21,
        unsigned __int64 a22,
        struct FidoTransportGlmExecuteDDLRes **a23,
        unsigned __int8 **a24,
        unsigned int *a25,
        bool *a26,
        const wchar_t *a27,
        unsigned int a28)
{
  struct BaseXact *v30; // rax
  struct BaseXact *v31; // rbx
  __int64 v32; // rcx
  void ***v33; // rdx
  __int64 v34; // r9
  CFidoTempObjectList *v35; // r12
  __int64 v36; // rbx
  __int64 v37; // rax
  struct IMemObj *v38; // r15
  bool v39; // zf
  __int64 v40; // rax
  struct BaseXact *v41; // r13
  __int64 v42; // rdi
  unsigned __int64 v43; // rax
  char *v44; // rax
  void *v45; // r15
  char *v46; // rbx
  __int64 v47; // rcx
  void **v48; // r15
  struct IMemObj **v49; // rdi
  bool CmplReq; // al
  unsigned __int8 *v51; // rax
  __int64 v52; // rax
  unsigned __int64 **v53; // rcx
  unsigned __int64 **v54; // rax
  unsigned __int64 **v55; // rax
  unsigned __int8 v56; // bl
  __int64 v57; // rdx
  __int64 v59; // rax
  struct CSessionTraceFlags **v60; // rax
  struct CSessionTraceFlags *v61; // rcx
  int v62; // eax
  char v63; // r15
  __int16 v64; // r10
  const wchar_t *v65; // r13
  unsigned int v66; // edi
  struct IMemObj **v67; // rbx
  CDefaultCollation *v68; // rax
  bool v69; // al
  char v70; // r8
  struct IMemObj *v71; // r12
  __int64 v72; // rbx
  struct Worker *v73; // rcx
  __int64 v74; // rdi
  unsigned __int64 v75; // rax
  _WORD *v76; // rax
  _WORD *v77; // r13
  _WORD *v78; // rbx
  __int64 v79; // rcx
  ErrMsgsBase *v80; // rbx
  const struct ErrMsg *NextErrMsg; // rax
  unsigned int v82; // r15d
  unsigned int v83; // edi
  unsigned int v84; // r12d
  int v85; // ecx
  int v86; // ecx
  unsigned int v87; // ecx
  unsigned int v88; // edi
  const struct ErrMsg *v89; // r14
  const wchar_t *Msg; // rdx
  int v91; // edi
  _WORD *v92; // rdi
  struct IMemObj **v93; // rdi
  __int64 v94; // rax
  unsigned __int64 *v95; // r14
  void **v96; // rdx
  unsigned int *v97; // rcx
  __int64 v98; // rbx
  struct Worker *v99; // rcx
  __int64 v100; // rdx
  int v101; // eax
  __int32 v102; // ecx
  int (*v103)(int, int, int, int, char *); // [rsp+20h] [rbp-798h]
  struct Worker *v104; // [rsp+28h] [rbp-790h]
  void **v105; // [rsp+30h] [rbp-788h]
  unsigned int v106[2]; // [rsp+38h] [rbp-780h]
  char v107; // [rsp+60h] [rbp-758h]
  unsigned __int8 v108; // [rsp+61h] [rbp-757h]
  int v109; // [rsp+64h] [rbp-754h] BYREF
  unsigned int v110; // [rsp+68h] [rbp-750h]
  char v111; // [rsp+6Ch] [rbp-74Ch]
  char v112; // [rsp+6Dh] [rbp-74Bh]
  unsigned int v113; // [rsp+70h] [rbp-748h] BYREF
  unsigned int v114; // [rsp+74h] [rbp-744h]
  unsigned int v115; // [rsp+78h] [rbp-740h] BYREF
  int v116; // [rsp+7Ch] [rbp-73Ch]
  struct IMemObj **v117; // [rsp+80h] [rbp-738h]
  int v118; // [rsp+88h] [rbp-730h]
  struct BaseXact *v119; // [rsp+90h] [rbp-728h]
  int v120; // [rsp+98h] [rbp-720h] BYREF
  int v121; // [rsp+9Ch] [rbp-71Ch] BYREF
  int v122; // [rsp+A0h] [rbp-718h]
  __int128 v123; // [rsp+A8h] [rbp-710h]
  void *v124; // [rsp+B8h] [rbp-700h] BYREF
  GUID *rguid; // [rsp+C0h] [rbp-6F8h]
  struct _GUID *v126; // [rsp+C8h] [rbp-6F0h]
  ErrMsgsBase *v127; // [rsp+D0h] [rbp-6E8h]
  int v128; // [rsp+D8h] [rbp-6E0h]
  unsigned int v129; // [rsp+DCh] [rbp-6DCh]
  CFidoTempObjectList *v130; // [rsp+E0h] [rbp-6D8h]
  __int64 v131; // [rsp+E8h] [rbp-6D0h]
  void **v132; // [rsp+F0h] [rbp-6C8h]
  unsigned int *v133; // [rsp+F8h] [rbp-6C0h]
  unsigned __int8 **v134; // [rsp+100h] [rbp-6B8h]
  __m128i si128; // [rsp+108h] [rbp-6B0h] BYREF
  int v136; // [rsp+118h] [rbp-6A0h]
  __int128 v137; // [rsp+120h] [rbp-698h]
  __int128 v138; // [rsp+130h] [rbp-688h]
  struct CSessionTraceFlags *v139; // [rsp+140h] [rbp-678h]
  unsigned __int64 *v140; // [rsp+148h] [rbp-670h]
  void *v141; // [rsp+150h] [rbp-668h]
  __m128i v142; // [rsp+158h] [rbp-660h] BYREF
  int v143; // [rsp+168h] [rbp-650h]
  __int64 v144; // [rsp+170h] [rbp-648h]
  int v145; // [rsp+178h] [rbp-640h]
  __int16 v146; // [rsp+17Ch] [rbp-63Ch]
  const wchar_t *v147; // [rsp+180h] [rbp-638h]
  void *i; // [rsp+188h] [rbp-630h]
  wchar_t *v149; // [rsp+190h] [rbp-628h]
  struct DWFidoTxCtx *v150; // [rsp+198h] [rbp-620h]
  const wchar_t *v151; // [rsp+1A0h] [rbp-618h]
  const wchar_t *v152; // [rsp+1A8h] [rbp-610h]
  const unsigned __int8 *v153; // [rsp+1B0h] [rbp-608h]
  const wchar_t *v154; // [rsp+1B8h] [rbp-600h]
  wchar_t *v155; // [rsp+1C0h] [rbp-5F8h]
  struct IMemObj *v156; // [rsp+1C8h] [rbp-5F0h]
  struct IMemObj *v157; // [rsp+1D0h] [rbp-5E8h]
  struct IMemObj **v158; // [rsp+1D8h] [rbp-5E0h]
  __int64 v159; // [rsp+1E0h] [rbp-5D8h]
  _WORD *j; // [rsp+1E8h] [rbp-5D0h]
  int v161; // [rsp+1F0h] [rbp-5C8h]
  int v162; // [rsp+1F8h] [rbp-5C0h]
  int v163; // [rsp+1FCh] [rbp-5BCh]
  int v164; // [rsp+200h] [rbp-5B8h]
  int v165; // [rsp+204h] [rbp-5B4h]
  __int64 v166; // [rsp+208h] [rbp-5B0h]
  __int128 v167; // [rsp+220h] [rbp-598h] BYREF
  __int64 v168; // [rsp+230h] [rbp-588h]
  int v169; // [rsp+23Ch] [rbp-57Ch]
  __m128i v170; // [rsp+240h] [rbp-578h] BYREF
  int v171; // [rsp+250h] [rbp-568h]
  __int64 *v172; // [rsp+260h] [rbp-558h]
  __int64 v173; // [rsp+268h] [rbp-550h]
  int *v174; // [rsp+270h] [rbp-548h]
  int *v175; // [rsp+278h] [rbp-540h]
  void ***v176; // [rsp+280h] [rbp-538h]
  int *v177; // [rsp+288h] [rbp-530h]
  struct Worker *v178; // [rsp+290h] [rbp-528h]
  _BYTE v179[24]; // [rsp+298h] [rbp-520h] BYREF
  struct _GUID v180; // [rsp+2B0h] [rbp-508h] BYREF
  __int64 v181; // [rsp+2C0h] [rbp-4F8h]
  void *v182; // [rsp+2C8h] [rbp-4F0h]
  _WORD *v183; // [rsp+2D0h] [rbp-4E8h]
  void *v184; // [rsp+2D8h] [rbp-4E0h]
  __int64 v185; // [rsp+2E0h] [rbp-4D8h]
  void **v186; // [rsp+2F0h] [rbp-4C8h] BYREF
  void ***v187; // [rsp+2F8h] [rbp-4C0h]
  __m128i v188; // [rsp+350h] [rbp-468h]
  int v189; // [rsp+360h] [rbp-458h]
  char v190[8]; // [rsp+370h] [rbp-448h] BYREF
  __int16 v191; // [rsp+378h] [rbp-440h]
  __int16 v192; // [rsp+37Ah] [rbp-43Eh]
  int v193; // [rsp+380h] [rbp-438h]
  unsigned __int64 **v194; // [rsp+388h] [rbp-430h]
  char *v195; // [rsp+390h] [rbp-428h]
  __int64 v196; // [rsp+398h] [rbp-420h]
  unsigned __int64 *v197; // [rsp+3A0h] [rbp-418h] BYREF
  int v198; // [rsp+3A8h] [rbp-410h]
  __int16 v199; // [rsp+3ACh] [rbp-40Ch]
  __int16 v200; // [rsp+3AEh] [rbp-40Ah]
  GUID *v201; // [rsp+3B0h] [rbp-408h]
  int v202; // [rsp+3B8h] [rbp-400h]
  __int16 v203; // [rsp+3BCh] [rbp-3FCh]
  __int16 v204; // [rsp+3BEh] [rbp-3FAh]
  GUID *v205; // [rsp+3C0h] [rbp-3F8h]
  int v206; // [rsp+3C8h] [rbp-3F0h]
  __int16 v207; // [rsp+3CCh] [rbp-3ECh]
  __int16 v208; // [rsp+3CEh] [rbp-3EAh]
  GUID *v209; // [rsp+3D0h] [rbp-3E8h]
  int v210; // [rsp+3D8h] [rbp-3E0h]
  __int16 v211; // [rsp+3DCh] [rbp-3DCh]
  __int16 v212; // [rsp+3DEh] [rbp-3DAh]
  char v213; // [rsp+3E0h] [rbp-3D8h] BYREF
  int v214; // [rsp+5C0h] [rbp-1F8h]
  int v215; // [rsp+5C4h] [rbp-1F4h]
  __int64 v216; // [rsp+5C8h] [rbp-1F0h]
  unsigned __int64 v217; // [rsp+5D0h] [rbp-1E8h] BYREF
  unsigned int v218; // [rsp+5D8h] [rbp-1E0h]
  _BYTE v219[40]; // [rsp+618h] [rbp-1A0h] BYREF
  GUID *v220; // [rsp+640h] [rbp-178h]
  int v221; // [rsp+650h] [rbp-168h] BYREF
  __int64 v222; // [rsp+658h] [rbp-160h]
  int v223; // [rsp+660h] [rbp-158h] BYREF
  void **v224; // [rsp+668h] [rbp-150h] BYREF
  __int128 v225; // [rsp+670h] [rbp-148h]
  __int64 v226; // [rsp+680h] [rbp-138h]
  char v227; // [rsp+6A8h] [rbp-110h]
  GUID v228; // [rsp+6B0h] [rbp-108h]
  OLECHAR sz; // [rsp+6C0h] [rbp-F8h] BYREF
  char v230[72]; // [rsp+6C2h] [rbp-F6h] BYREF
  __int16 v231; // [rsp+70Ah] [rbp-AEh]
  __int16 v232; // [rsp+70Ch] [rbp-ACh]
  GUID v233; // [rsp+710h] [rbp-A8h]
  OLECHAR v234; // [rsp+720h] [rbp-98h] BYREF
  char v235[72]; // [rsp+722h] [rbp-96h] BYREF
  __int16 v236; // [rsp+76Ah] [rbp-4Eh]
  __int16 v237; // [rsp+76Ch] [rbp-4Ch]

  v181 = -2;
  rguid = a4;
  v128 = a3;
  v149 = a2;
  v117 = this;
  v110 = a19;
  v129 = a19;
  v158 = this;
  v220 = a4;
  v154 = a8;
  v153 = a10;
  v152 = a13;
  v151 = a15;
  v155 = a17;
  v140 = a20;
  v126 = a21;
  v132 = (void **)a23;
  v134 = a24;
  v133 = a25;
  v131 = (__int64)a26;
  *a20 = 0;
  v108 = 1;
  if ( !a18 )
    return v108;
  v144 = 0;
  v145 = 0;
  v146 = 0;
  v147 = L"DwFidoGlmServerExecuteDDLStatement";
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset) )
  {
    v144 = g_pfnAutoSetupContextForInternalTasksFactory(0, 0);
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v144 + 8LL))(v144, 1, 0);
  }
  v118 = 3806;
  v30 = (struct BaseXact *)operator new(
                             0x20u,
                             this[3],
                             "Sql\\Ntdbms\\storeng\\fido\\metadata\\FidoGLMServer.cpp",
                             3806,
                             5u);
  v31 = v30;
  v119 = v30;
  if ( v30 )
  {
    ErrMsgsBase::ErrMsgsBase(v30, this[3]);
    *((_DWORD *)v31 + 6) = 0;
  }
  else
  {
    v31 = 0;
  }
  v127 = v31;
  CDeferMsgsConnOut::CDeferMsgsConnOut(
    (CDeferMsgsConnOut *)&v186,
    v31,
    *(struct CConnectionOutput **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset)
                                             + 112LL)
                                 + 24LL));
  v32 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)
                  + 112LL);
  v137 = 0;
  v138 = 0;
  v33 = *(void ****)(v32 + 24);
  if ( v33 != &v186 )
  {
    *(_QWORD *)&v137 = v32;
    *((_QWORD *)&v137 + 1) = v33;
    *(_QWORD *)&v138 = v187;
    *((_QWORD *)&v138 + 1) = &v186;
    v187 = v33;
    *(_QWORD *)(v32 + 24) = &v186;
  }
  *(struct _GUID *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 72LL)
                  + 5060LL) = *a4;
  CSession::SetStorageToken(
    *(CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)
                 + 72LL),
    a27,
    a28);
  v34 = 8LL * SystemThread_TlsIndex;
  v35 = *(CFidoTempObjectList **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + v34)
                                                        + SystemThread_TlsOffset)
                                            + 72LL)
                                + 432LL);
  v130 = v35;
  v36 = SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v34);
  v37 = *(_QWORD *)(v36 + 256);
  if ( !v37 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v37 = *(_QWORD *)(v36 + 256);
  }
  v38 = *(struct IMemObj **)(v37 + 1000);
  v156 = v38;
  v157 = v38;
  if ( v35 && a6 )
  {
    _mm_lfence();
    CFidoTempObjectList::DisableAutoDropTempTable(v35);
    CFidoTempObjectList::Deserialize(v35, a5, a6);
  }
  v167 = 0;
  v168 = 0;
  v169 = 0;
  AutoOverrideMsqlXact::InitializeAndOverride((AutoOverrideMsqlXact *)&v167);
  v109 = 0;
  if ( !CAutoDb::FUse((CAutoDb *)&v109, 1u, 0, 1, 1, 0) )
    utassert_fail(1u, "fUseSuccess", "\"Sql\\\\Ntdbms\\\\storeng\\\\fido\\\\metadata\\\\FidoGLMServer.cpp\"", 3839, 0);
  v120 = 0;
  v121 = 0;
  v123 = 0;
  v122 = 1;
  v119 = *(struct BaseXact **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset);
  *(_QWORD *)&v123 = *((_QWORD *)v119 + 18);
  v119 = *(struct BaseXact **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset);
  v161 = 1;
  v39 = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v123 + 464LL))(v123) == 0;
  v40 = *(_QWORD *)v123;
  if ( v39 )
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, _BYTE, _QWORD, int))(v40 + 8))(
      v123,
      L"ExecuteDDL",
      20,
      1,
      2,
      1,
      0,
      0,
      1);
    v120 = 1;
  }
  else
  {
    if ( (*(unsigned __int8 (**)(void))(v40 + 488))() )
      utassert_fail(
        1u,
        "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
        "automsqlxact.cpp",
        235,
        0);
    (*(void (__fastcall **)(_QWORD, __int64, __int64, int *))(*(_QWORD *)v123 + 232LL))(v123, 2, 1, &v121);
    v122 = 1;
    v120 = 3;
  }
  v119 = *(struct BaseXact **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset);
  v41 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v119 + 18) + 616LL))(*((_QWORD *)v119 + 18));
  v119 = v41;
  (*(void (__fastcall **)(struct BaseXact *))(*(_QWORD *)v41 + 288LL))(v41);
  v111 = byte_1031852E4;
  if ( !byte_1031852E4 || byte_1031D5EE8 || (v112 = (unsigned __int8)byte_10317B170 >> 4, (byte_10317B170 & 0x10) != 0) )
  {
    v49 = v117;
    goto LABEL_49;
  }
  v42 = a19;
  v162 = 3867;
  v43 = 4110LL * a19;
  if ( !is_mul_ok(a19, 0x100Eu) )
    v43 = -1;
  v44 = (char *)operator new[](v43, v38, "Sql\\Ntdbms\\storeng\\fido\\metadata\\FidoGLMServer.cpp", 3867, 5u);
  v45 = v44;
  v182 = v44;
  if ( v44 )
  {
    v166 = a19;
    v46 = v44;
    for ( i = v44; ; i = v46 )
    {
      v47 = v42--;
      v166 = v42;
      if ( !v47 )
        break;
      *(_WORD *)v46 = 0;
      *(_DWORD *)(v46 + 2) = 0;
      *(_DWORD *)(v46 + 6) = 0;
      *(_DWORD *)(v46 + 10) = 0;
      memset_0(v46 + 14, 0, 0x1000u);
      v46 += 4110;
    }
  }
  else
  {
    v45 = 0;
  }
  v124 = v45;
  v113 = 0;
  v48 = v132;
  v49 = v117;
  CmplReq = CFidoGlmCmplReqTbl::GetCmplReq(v117[615], v41, v126, a22, *v132, 9u, &v124, 4110 * a19, &v113);
  *(_BYTE *)v131 = CmplReq;
  if ( !CmplReq )
  {
    v184 = v124;
    operator delete[](v124);
LABEL_49:
    v150 = (struct DWFidoTxCtx *)(*(__int64 (__fastcall **)(struct BaseXact *))(*(_QWORD *)v41 + 296LL))(v41);
    SetBase64TxnCookieFromRM(v149, 2 * v128, v150);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v136 = 0;
    v107 = 0;
    v185 = 0;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v219, 0, 0, 0, hdl_prntbackout, 0);
      v118 = 0;
      v172 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset);
      v59 = *v172;
      v173 = v59;
      if ( v59 )
      {
        v60 = *(struct CSessionTraceFlags ***)(v59 + 56);
        v61 = *v60;
        if ( *v60 )
        {
          v139 = *v60;
          v62 = CSessionTraceFlags::CheckSessionTraceInternal(v61, 0x2F63u);
          goto LABEL_56;
        }
        v139 = 0;
      }
      else
      {
        v139 = 0;
      }
      v62 = v118;
LABEL_56:
      if ( v62 )
      {
        v63 = 0;
      }
      else
      {
        CSessionTraceFlags::SetSessionTrace(12131, 0);
        v63 = 1;
        v107 = 1;
      }
      v64 = (*((__int64 (__fastcall **)(struct IMemObj **, struct DWFidoTxCtx *))*v49 + 6))(v49, v150);
      v174 = &v221;
      v221 = 0;
      v222 = 0;
      v175 = &v223;
      v223 = 0;
      v176 = &v224;
      v224 = &VdwImpMessage::`vftable';
      v225 = 0;
      v226 = 0;
      v227 = 0;
      v65 = v151;
      CAutoImpersonateForVdw::SetData(&v221, a7, a12, v154, 2 * a9, v153, a11, v152, 2 * a14, v151, 2 * a16, v64);
      if ( *((_BYTE *)v49 + 48) )
      {
        v66 = 2 * *((_DWORD *)v49 + 87);
        v67 = v117;
        v68 = (CDefaultCollation *)CDefaultCollation::PDCServer();
        v69 = CDefaultCollation::FEqW(v68, (const wchar_t *)v67 + 45, v66, v65, 2 * a16);
        v70 = v227;
        if ( v69 )
          v70 = 1;
        v227 = v70;
        v49 = v67;
      }
      CAutoImpersonateForVdw::Impersonate((CAutoImpersonateForVdw *)&v221, v49[3]);
      v106[1] = 0;
      HIDWORD(v105) = 0;
      HIDWORD(v104) = 0;
      FidoTSqlAgent::ExecuteSqlOnExistingXact(v155, a18, 29);
      CAutoImpersonateForVdw::Restore((CAutoImpersonateForVdw *)&v221);
      if ( v63 )
      {
        CSessionTraceFlags::ClearSessionTrace(12131, 0);
        v107 = 0;
      }
      v108 = 1;
      CAutoImpersonateForVdw::Restore((CAutoImpersonateForVdw *)&v221);
      v177 = &v223;
      if ( v223 )
      {
        v223 = 0;
        ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
      }
      CAutoExecuteAsContext::Restore((CAutoExecuteAsContext *)&v221);
      ExcHandler::~ExcHandler((ExcHandler *)v219);
    }
    catch ( SQLError v142 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v179, (const struct SQLError *)&v142);
        if ( v107 )
          CSessionTraceFlags::ClearSessionTrace(12131, 0);
        v101 = v143;
        if ( v143 == 1 )
          v102 = v142.m128i_i32[0];
        else
          v102 = v142.m128i_u16[0];
        if ( v102 == 3617 )
        {
          v170 = v142;
          v171 = v143;
          ex_raisecontrol(&v170);
          v101 = v143;
        }
        v108 = 0;
        si128 = v142;
        v136 = v101;
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v179);
      }
      catch ( ShortStackException )
      {
      }
      v71 = v157;
      v110 = v129;
      v117 = v158;
      rguid = v220;
      goto LABEL_69;
    }
    v71 = v156;
LABEL_69:
    v72 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v73 = *(struct Worker **)(v72 + 256);
    if ( !v73 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v73 = *(struct Worker **)(v72 + 256);
    }
    v178 = v73;
    if ( *((_DWORD *)v73 + 139) )
      ExceptionPostCatchActions(v73);
    v74 = a19;
    v163 = 3988;
    v75 = 4110LL * a19;
    if ( !is_mul_ok(a19, 0x100Eu) )
      v75 = -1;
    v76 = operator new[](v75, v71, "Sql\\Ntdbms\\storeng\\fido\\metadata\\FidoGLMServer.cpp", 3988, 5u);
    v77 = v76;
    v183 = v76;
    if ( v76 )
    {
      v159 = a19;
      v78 = v76;
      for ( j = v76; ; j = v78 )
      {
        v79 = v74--;
        v159 = v74;
        if ( !v79 )
          break;
        *v78 = 0;
        *(_DWORD *)(v78 + 1) = 0;
        *(_DWORD *)(v78 + 3) = 0;
        *(_DWORD *)(v78 + 5) = 0;
        memset_0(v78 + 7, 0, 0x1000u);
        v78 += 2055;
      }
    }
    else
    {
      v77 = 0;
    }
    v141 = v77;
    v80 = v127;
    NextErrMsg = ErrMsgsBase::GetNextErrMsg(v127, 0);
    v82 = 0;
    v114 = 0;
    v83 = 0;
    while ( NextErrMsg )
    {
      v83 = ++v82;
      v114 = v82;
      NextErrMsg = ErrMsgsBase::GetNextErrMsg(v80, NextErrMsg);
    }
    v84 = 0;
    v116 = 0;
    if ( !v108
      && (v188 = _mm_loadu_si128(&si128),
          v189 = v136,
          v85 = _mm_cvtsi128_si32(v188),
          si128.m128i_i32[0] = v85,
          v85 / 100 == 36)
      && ((v86 = v85 - 3600, v86 == 2) || v86 == 9) )
    {
      v87 = v110;
      if ( v110 )
      {
        *v77 = si128.m128i_i16[0];
        *(_DWORD *)(v77 + 1) = si128.m128i_i32[1];
        *(_DWORD *)(v77 + 3) = si128.m128i_i32[3];
        *(_DWORD *)(v77 + 5) = 0;
        v84 = 1;
        v116 = 1;
        v114 = ++v82;
        v83 = v82;
      }
    }
    else
    {
      v87 = v110;
    }
    if ( v83 <= v87 )
    {
      v88 = a19;
    }
    else
    {
      _mm_lfence();
      v228 = *rguid;
      StringFromGUID2(rguid, &sz, 39);
      v231 = 0;
      v232 = 0;
      v88 = a19;
      FidoLogTraceSystemMetadata(
        6,
        L"GLM_SERVER",
        L"Truncating Error message list at [%d] for statement [%ls] as its too big. Check Pii logs for missing errors.",
        a19,
        v230);
      v80 = v127;
      v77 = v141;
      v82 = v114;
      v84 = v116;
    }
    v89 = ErrMsgsBase::GetNextErrMsg(v80, 0);
    while ( v89 )
    {
      Msg = ErrMsg::GetMsg(v89, (int *)&v115);
      v220 = (GUID *)Msg;
      if ( v82 <= v88 || *((int *)v89 + 1) > 10 && v84 < v88 )
      {
        v92 = &v77[2055 * v84];
        *v92 = *(_WORD *)v89;
        *(_DWORD *)(v92 + 1) = *((_DWORD *)v89 + 1);
        *(_DWORD *)(v92 + 3) = *((_DWORD *)v89 + 3);
        memcpy_s(v92 + 7, 0x1000u, Msg, 2LL * (int)v115);
        *(_DWORD *)(v92 + 5) = v115;
        v116 = ++v84;
      }
      else
      {
        v91 = *(_DWORD *)v89;
        v164 = *(_DWORD *)v89 / 100;
        v165 = v91 % 100;
        v233 = *rguid;
        StringFromGUID2(rguid, &v234, 39);
        v236 = 0;
        v237 = 0;
        v106[0] = v115;
        LODWORD(v105) = *((_DWORD *)v89 + 3);
        LODWORD(v104) = *((_DWORD *)v89 + 1);
        LODWORD(v103) = (unsigned __int16)v91;
        FidoLogTrace(
          6,
          L"GLM_SERVER",
          L"Statement [%ls] encountered Error: %d, Severity: %d, State: %d, Message: %.*ls.",
          v235,
          v103,
          v104,
          v105,
          *(_QWORD *)v106,
          v220);
      }
      v89 = ErrMsgsBase::GetNextErrMsg(v80, v89);
      v88 = a19;
    }
    if ( v84 > v88 )
      utassert_fail(
        1u,
        "errCount <= maxErrors",
        "\"Sql\\\\Ntdbms\\\\storeng\\\\fido\\\\metadata\\\\FidoGLMServer.cpp\"",
        4057,
        0);
    v93 = v117;
    v94 = (*((__int64 (__fastcall **)(struct IMemObj **))*v117 + 18))(v117);
    v95 = v140;
    *v140 = v94;
    if ( !v108 && !v84 )
      utassert_fail(
        1u,
        "fSuccess || errCount > 0",
        "\"Sql\\\\Ntdbms\\\\storeng\\\\fido\\\\metadata\\\\FidoGLMServer.cpp\"",
        4063,
        0);
    v96 = v132;
    *(_QWORD *)((char *)*v132 + 1) = *v95;
    *(_BYTE *)*v96 = v108;
    v97 = v133;
    *v133 = 4110 * v84;
    v141 = 0;
    *v134 = (unsigned __int8 *)v77;
    if ( v108 )
    {
      if ( byte_1031852E4 && !byte_1031D5EE8 && (byte_10317B170 & 0x10) == 0 )
      {
        v180 = *v126;
        CFidoGlmCmplReqTbl::SetCmplReq(v93[615], v119, &v180, a22, *v96, 9u, v77, *v97);
      }
      CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v120, 0);
    }
    else
    {
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v120, 0);
    }
    if ( v130 )
      CFidoTempObjectList::Clear(v130);
    operator delete[](0);
    if ( v120 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v120, 0);
    if ( v109 )
    {
      v109 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    AutoOverrideMsqlXact::~AutoOverrideMsqlXact((AutoOverrideMsqlXact *)&v167);
    v98 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v99 = *(struct Worker **)(v98 + 256);
    if ( !v99 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v99 = *(struct Worker **)(v98 + 256);
    }
    if ( *((_DWORD *)v99 + 139) )
      ExceptionPostCatchActions(v99);
    v100 = v137;
    if ( (_QWORD)v137 )
    {
      *(_QWORD *)(*(_QWORD *)(v137 + 24) + 8LL) = v138;
      *(_QWORD *)(v100 + 24) = *((_QWORD *)&v137 + 1);
      v137 = 0;
      v138 = 0;
    }
    v186 = &CPassThroughConn::`vftable';
    CConnectionOutput::~CConnectionOutput((CConnectionOutput *)&v186);
    if ( v127 )
      ErrMsgsBase::Release(v127);
    if ( v144 )
      (**(void (__fastcall ***)(__int64, __int64))v144)(v144, 1);
    return v108;
  }
  v51 = (unsigned __int8 *)v124;
  v124 = 0;
  *v134 = v51;
  *v133 = v113;
  if ( !*(_BYTE *)*v48 )
    utassert_fail(
      1u,
      "(*ppRes)->fSuccess",
      "\"Sql\\\\Ntdbms\\\\storeng\\\\fido\\\\metadata\\\\FidoGLMServer.cpp\"",
      3884,
      0);
  CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v120, 0);
  v131 = 0x8000000000000LL;
  if ( (g_XeSqlFido_enabledBitmap & 0x80000) != 0 )
  {
    v191 = 0;
    v192 = 4;
    v193 = 0;
    v194 = &v197;
    v195 = &v213;
    v214 = 0;
    v215 = 0;
    v196 = 0;
    v216 = 0;
    v197 = &v217;
    v198 = 36;
    v199 = 3;
    v200 = 0;
    v201 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
    v202 = 16;
    v203 = 2;
    v204 = 0;
    v205 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
    v206 = 16;
    v207 = 3;
    v208 = 0;
    v209 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
    v210 = 16;
    v211 = 4;
    v212 = 0;
    v52 = (*((__int64 (__fastcall **)(struct IMemObj **))*v49 + 1))(v49);
    v53 = v194;
    v194[2] = (unsigned __int64 *)v52;
    *((_DWORD *)v53 + 6) = 16;
    *((_WORD *)v53 + 14) = 2;
    *((_WORD *)v53 + 15) = 0;
    v54 = v194;
    v194[6] = (unsigned __int64 *)&v126->Data1;
    *((_DWORD *)v54 + 14) = 16;
    *((_WORD *)v54 + 30) = 4;
    *((_WORD *)v54 + 31) = 0;
    v55 = v194;
    v194[4] = (unsigned __int64 *)&rguid->Data1;
    *((_DWORD *)v55 + 10) = 16;
    *((_WORD *)v55 + 22) = 3;
    *((_WORD *)v55 + 23) = 0;
    v217 = a22;
    v218 = v113;
    XeSqlFido::fido_glm_execute_ddl_cached::Publish((XeSqlFido::fido_glm_execute_ddl_cached *)v190);
  }
  v56 = *(_BYTE *)*v48;
  operator delete[](0);
  if ( v120 )
    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v120, 0);
  if ( v109 )
  {
    v109 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  AutoOverrideMsqlXact::~AutoOverrideMsqlXact((AutoOverrideMsqlXact *)&v167);
  v57 = v137;
  if ( (_QWORD)v137 )
  {
    *(_QWORD *)(*(_QWORD *)(v137 + 24) + 8LL) = v138;
    *(_QWORD *)(v57 + 24) = *((_QWORD *)&v137 + 1);
    v137 = 0;
    v138 = 0;
  }
  v186 = &CPassThroughConn::`vftable';
  CConnectionOutput::~CConnectionOutput((CConnectionOutput *)&v186);
  if ( v127 )
    ErrMsgsBase::Release(v127);
  if ( v144 )
    (**(void (__fastcall ***)(__int64, __int64))v144)(v144, 1);
  return v56;
}

```

## disassembly

```asm
0x10245fff0  push    rbx
0x10245fff2  push    rsi
0x10245fff3  push    rdi
0x10245fff4  push    r12
0x10245fff6  push    r13
0x10245fff8  push    r14
0x10245fffa  push    r15
0x10245fffc  sub     rsp, 780h
0x102460003  mov     [rsp+7B8h+var_4F8], 0FFFFFFFFFFFFFFFEh
0x10246000f  mov     rax, cs:__security_cookie
0x102460016  xor     rax, rsp
0x102460019  mov     [rsp+7B8h+var_48], rax
0x102460021  mov     r13, r9
0x102460024  mov     [rsp+7B8h+rguid], r9
0x10246002c  mov     [rsp+7B8h+var_6E0], r8d
0x102460034  mov     [rsp+7B8h+var_628], rdx
0x10246003c  mov     r12, rcx
0x10246003f  mov     [rsp+7B8h+var_738], rcx
0x102460047  mov     eax, [rsp+7B8h+arg_90]
0x10246004e  mov     [rsp+7B8h+var_750], eax
0x102460052  mov     [rsp+7B8h+var_6DC], eax
0x102460059  mov     [rsp+7B8h+var_5E0], rcx
0x102460061  mov     [rsp+7B8h+var_178], r9
0x102460069  mov     rdi, [rsp+7B8h+arg_20]
0x102460071  mov     rax, [rsp+7B8h+arg_38]
0x102460079  mov     [rsp+7B8h+var_600], rax
0x102460081  mov     rax, [rsp+7B8h+arg_48]
0x102460089  mov     [rsp+7B8h+var_608], rax
0x102460091  mov     rax, [rsp+7B8h+arg_60]
0x102460099  mov     [rsp+7B8h+var_610], rax
0x1024600a1  mov     rax, [rsp+7B8h+arg_70]
0x1024600a9  mov     [rsp+7B8h+var_618], rax
0x1024600b1  mov     rax, [rsp+7B8h+arg_80]
0x1024600b9  mov     [rsp+7B8h+var_5F8], rax
0x1024600c1  mov     rcx, [rsp+7B8h+arg_98]
0x1024600c9  mov     [rsp+7B8h+var_670], rcx
0x1024600d1  mov     rax, [rsp+7B8h+arg_A0]
0x1024600d9  mov     [rsp+7B8h+var_6F0], rax
0x1024600e1  mov     rax, [rsp+7B8h+arg_B0]
0x1024600e9  mov     [rsp+7B8h+var_6C8], rax
0x1024600f1  mov     rax, [rsp+7B8h+arg_B8]
0x1024600f9  mov     [rsp+7B8h+var_6B8], rax
0x102460101  mov     rax, [rsp+7B8h+arg_C0]
0x102460109  mov     [rsp+7B8h+var_6C0], rax
0x102460111  mov     rax, [rsp+7B8h+arg_C8]
0x102460119  mov     [rsp+7B8h+var_6D0], rax
0x102460121  mov     r15, [rsp+7B8h+arg_D0]
0x102460129  xor     esi, esi
0x10246012b  mov     [rcx], rsi
0x10246012e  mov     [rsp+7B8h+var_757], 1
0x102460133  cmp     [rsp+7B8h+arg_88], esi
0x10246013a  jbe     loc_10246148B
0x102460140  mov     [rsp+7B8h+var_648], rsi
0x102460148  mov     [rsp+7B8h+var_640], esi
0x10246014f  mov     [rsp+7B8h+var_63C], si
0x102460157  lea     r8, aDwfidoglmserve; "DwFidoGlmServerExecuteDDLStatement"
0x10246015e  mov     [rsp+7B8h+var_638], r8
0x102460166  mov     r9, gs:58h
0x10246016f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102460176  mov     ecx, [rax]
0x102460178  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10246017f  mov     edx, [rax]
0x102460181  add     rdx, [r9+rcx*8]
0x102460185  cmp     [rdx], rsi
0x102460188  jnz     short loc_1024601B7
0x10246018a  xor     edx, edx
0x10246018c  xor     ecx, ecx
0x10246018e  mov     rax, cs:__imp_?g_pfnAutoSetupContextForInternalTasksFactory@@3P6APEAVIAutoSetupExecContextsForInternalTasksImpl@@W4thread_type@@FPEB_W@ZEA; IAutoSetupExecContextsForInternalTasksImpl * (*g_pfnAutoSetupContextForInternalTasksFactory)(thread_type,short,wchar_t const *)
0x102460195  call    qword ptr [rax]
0x102460197  mov     [rsp+7B8h+var_648], rax
0x10246019f  mov     r9, [rax]
0x1024601a2  xor     r8d, r8d
0x1024601a5  mov     r14d, 1
0x1024601ab  mov     edx, r14d
0x1024601ae  mov     rcx, rax
0x1024601b1  call    qword ptr [r9+8]
0x1024601b5  jmp     short loc_1024601BD
0x1024601b7  mov     r14d, 1
0x1024601bd  mov     [rsp+7B8h+var_730], 0EDEh
0x1024601c8  mov     byte ptr [rsp+7B8h+var_798], 5
0x1024601cd  mov     r9d, 0EDEh
0x1024601d3  lea     r8, aSqlNtdbmsStore_707; "Sql\\Ntdbms\\storeng\\fido\\metadata\\F"...
0x1024601da  mov     rdx, [r12+18h]
0x1024601df  mov     ecx, 20h ; ' '
0x1024601e4  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1024601ea  mov     rbx, rax
0x1024601ed  mov     [rsp+7B8h+var_728], rax
0x1024601f5  test    rax, rax
0x1024601f8  jz      short loc_10246020E
0x1024601fa  mov     rdx, [r12+18h]
0x1024601ff  mov     rcx, rax
0x102460202  call    cs:__imp_??0ErrMsgsBase@@QEAA@PEAVIMemObj@@@Z; ErrMsgsBase::ErrMsgsBase(IMemObj *)
0x102460208  nop
0x102460209  mov     [rbx+18h], esi
0x10246020c  jmp     short loc_102460211
0x10246020e  mov     rbx, rsi
0x102460211  mov     [rsp+7B8h+var_6E8], rbx
0x102460219  mov     rdx, gs:58h
0x102460222  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102460229  mov     ecx, [rax]
0x10246022b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102460232  mov     eax, [rax]
0x102460234  add     rax, [rdx+rcx*8]
0x102460238  mov     rax, [rax]
0x10246023b  mov     r8, [rax+70h]
0x10246023f  mov     r8, [r8+18h]
0x102460243  mov     rdx, rbx
0x102460246  lea     rcx, [rsp+7B8h+var_4C8]
0x10246024e  call    cs:__imp_??0CDeferMsgsConnOut@@QEAA@PEAVErrMsgs@@PEAVCConnectionOutput@@@Z; CDeferMsgsConnOut::CDeferMsgsConnOut(ErrMsgs *,CConnectionOutput *)
0x102460254  nop
0x102460255  mov     rdx, gs:58h
0x10246025e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102460265  mov     ecx, [rax]
0x102460267  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10246026e  mov     eax, [rax]
0x102460270  add     rax, [rdx+rcx*8]
0x102460274  mov     rax, [rax]
0x102460277  mov     rcx, [rax+70h]
0x10246027b  xorps   xmm0, xmm0
0x10246027e  movdqu  [rsp+7B8h+var_698], xmm0
0x102460287  xorps   xmm1, xmm1
0x10246028a  movdqu  [rsp+7B8h+var_688], xmm1
0x102460293  mov     rdx, [rcx+18h]
0x102460297  lea     rax, [rsp+7B8h+var_4C8]
0x10246029f  cmp     rdx, rax
0x1024602a2  jz      short loc_1024602E8
0x1024602a4  mov     qword ptr [rsp+7B8h+var_698], rcx
0x1024602ac  mov     qword ptr [rsp+7B8h+var_698+8], rdx
0x1024602b4  mov     rax, [rsp+7B8h+var_4C0]
0x1024602bc  mov     qword ptr [rsp+7B8h+var_688], rax
0x1024602c4  lea     rax, [rsp+7B8h+var_4C8]
0x1024602cc  mov     qword ptr [rsp+7B8h+var_688+8], rax
0x1024602d4  mov     [rsp+7B8h+var_4C0], rdx
0x1024602dc  lea     rax, [rsp+7B8h+var_4C8]
0x1024602e4  mov     [rcx+18h], rax
0x1024602e8  mov     rdx, gs:58h
0x1024602f1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1024602f8  mov     ecx, [rax]
0x1024602fa  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102460301  mov     eax, [rax]
0x102460303  add     rax, [rdx+rcx*8]
0x102460307  mov     rax, [rax]
0x10246030a  mov     rcx, [rax+48h]
0x10246030e  movups  xmm0, xmmword ptr [r13+0]
0x102460313  movups  xmmword ptr [rcx+13C4h], xmm0
0x10246031a  mov     r8, gs:58h
0x102460323  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10246032a  mov     ecx, [rax]
0x10246032c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102460333  mov     edx, [rax]
0x102460335  add     rdx, [r8+rcx*8]
0x102460339  mov     rcx, [rdx]
0x10246033c  mov     r8d, [rsp+7B8h+arg_D8]
0x102460344  mov     rdx, r15
0x102460347  mov     rcx, [rcx+48h]
0x10246034b  call    cs:__imp_?SetStorageToken@CSession@@QEAA_NPEB_WK@Z; CSession::SetStorageToken(wchar_t const *,ulong)
0x102460351  mov     rdx, gs:58h
0x10246035a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102460361  mov     ecx, [rax]
0x102460363  lea     r9, ds:0[rcx*8]
0x10246036b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102460372  mov     r8d, [rax]
0x102460375  mov     rax, [r9+rdx]
0x102460379  mov     rcx, [rax+r8]
0x10246037d  mov     rax, [rcx+48h]
0x102460381  mov     r12, [rax+1B0h]
0x102460388  mov     [rsp+7B8h+var_6D8], r12
0x102460390  mov     rax, gs:58h
0x102460399  mov     rbx, [r9+rax]
0x10246039d  add     rbx, r8
0x1024603a0  mov     rax, [rbx+100h]
0x1024603a7  test    rax, rax
0x1024603aa  jnz     short loc_1024603BB
0x1024603ac  xor     ecx, ecx
0x1024603ae  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1024603b4  mov     rax, [rbx+100h]
0x1024603bb  mov     r15, [rax+3E8h]
0x1024603c2  mov     [rsp+7B8h+var_5F0], r15
0x1024603ca  mov     [rsp+7B8h+var_5E8], r15
0x1024603d2  test    r12, r12
0x1024603d5  jz      short loc_1024603FD
0x1024603d7  mov     ebx, [rsp+7B8h+arg_28]
0x1024603de  test    ebx, ebx
0x1024603e0  jz      short loc_1024603FD
0x1024603e2  lfence
0x1024603e5  mov     rcx, r12
0x1024603e8  call    cs:__imp_?DisableAutoDropTempTable@CFidoTempObjectList@@QEAAXXZ; CFidoTempObjectList::DisableAutoDropTempTable(void)
0x1024603ee  mov     r8d, ebx
0x1024603f1  mov     rdx, rdi
0x1024603f4  mov     rcx, r12
0x1024603f7  call    cs:__imp_?Deserialize@CFidoTempObjectList@@QEAAXPEB_WK@Z; CFidoTempObjectList::Deserialize(wchar_t const *,ulong)
0x1024603fd  xorps   xmm0, xmm0
0x102460400  movdqu  [rsp+7B8h+var_598], xmm0
0x102460409  mov     [rsp+7B8h+var_588], rsi
0x102460411  mov     [rsp+7B8h+var_57C], esi
0x102460418  lea     rcx, [rsp+7B8h+var_598]
0x102460420  call    cs:__imp_?InitializeAndOverride@AutoOverrideMsqlXact@@QEAAXXZ; AutoOverrideMsqlXact::InitializeAndOverride(void)
0x102460426  mov     [rsp+7B8h+var_754], esi
0x10246042a  mov     dword ptr [rsp+7B8h+var_790], esi; unsigned int
0x10246042e  mov     byte ptr [rsp+7B8h+var_798], 1; bool
0x102460433  mov     r9b, 1; bool
0x102460436  xor     r8d, r8d; struct BaseXact *
0x102460439  mov     edx, r14d; unsigned int
0x10246043c  lea     rcx, [rsp+7B8h+var_754]; this
0x102460441  call    ?FUse@CAutoDb@@QEAA_NKPEAVBaseXact@@_N1K@Z; CAutoDb::FUse(ulong,BaseXact *,bool,bool,ulong)
0x102460446  test    al, al
0x102460448  jnz     short loc_10246046C
0x10246044a  mov     [rsp+7B8h+var_798], rsi
0x10246044f  mov     r9d, 0EFFh
0x102460455  lea     r8, aSqlNtdbmsStore_1000; "\"Sql\\\\Ntdbms\\\\storeng\\\\fido\\\\m"...
0x10246045c  lea     rdx, aFusesuccess; "fUseSuccess"
0x102460463  mov     ecx, r14d
0x102460466  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10246046c  mov     [rsp+7B8h+var_720], esi
0x102460473  mov     [rsp+7B8h+var_71C], esi
0x10246047a  mov     [rsp+7B8h+var_718], r14d
0x102460482  xorps   xmm0, xmm0
0x102460485  movdqu  [rsp+7B8h+var_710], xmm0
0x10246048e  mov     [rsp+7B8h+var_718], r14d
0x102460496  mov     rdx, gs:58h
0x10246049f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1024604a6  mov     ecx, [rax]
0x1024604a8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1024604af  mov     eax, [rax]
0x1024604b1  add     rax, [rdx+rcx*8]
0x1024604b5  mov     rax, [rax]
0x1024604b8  mov     [rsp+7B8h+var_728], rax
0x1024604c0  mov     rax, [rax+90h]
0x1024604c7  mov     qword ptr [rsp+7B8h+var_710], rax
0x1024604cf  mov     rdx, gs:58h
0x1024604d8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1024604df  mov     ecx, [rax]
0x1024604e1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1024604e8  mov     eax, [rax]
0x1024604ea  add     rax, [rdx+rcx*8]
0x1024604ee  mov     rax, [rax]
0x1024604f1  mov     [rsp+7B8h+var_728], rax
0x1024604f9  mov     [rsp+7B8h+var_5C8], r14d
0x102460501  mov     rcx, qword ptr [rsp+7B8h+var_710]
0x102460509  mov     rax, [rcx]
0x10246050c  call    qword ptr [rax+1D0h]
0x102460512  mov     rcx, qword ptr [rsp+7B8h+var_710]
0x10246051a  test    al, al
0x10246051c  mov     rax, [rcx]
0x10246051f  jz      short loc_102460587
0x102460521  call    qword ptr [rax+1E8h]
0x102460527  test    al, al
0x102460529  jz      short loc_10246054D
0x10246052b  mov     [rsp+7B8h+var_798], rsi
0x102460530  mov     r9d, 0EBh
0x102460536  lea     r8, aAutomsqlxactCp; "automsqlxact.cpp"
0x10246053d  lea     rdx, ?szExpression@?9??BeginNestedXact@CAutoMsqlXact@@QEAAXPEB_WHW4ReadWriteMode@CMsqlXact@@W4DistributionMode@4@W4NestedXactOption@4@W4CTRSupportOption@4@@Z@4QBDB; "rwMode == CMsqlXact::ReadOnly || ctrOpt"...
0x102460544  mov     ecx, r14d
0x102460547  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10246054d  mov     rcx, qword ptr [rsp+7B8h+var_710]
0x102460555  mov     rax, [rcx]
0x102460558  lea     r9, [rsp+7B8h+var_71C]
0x102460560  mov     r8d, r14d
0x102460563  mov     r12d, 2
0x102460569  mov     edx, r12d
0x10246056c  call    qword ptr [rax+0E8h]
0x102460572  mov     [rsp+7B8h+var_718], r14d
0x10246057a  mov     [rsp+7B8h+var_720], 3
0x102460585  jmp     short loc_1024605C0
0x102460587  mov     dword ptr [rsp+7B8h+var_778], r14d
0x10246058c  mov     qword ptr [rsp+7B8h+var_780], rsi
0x102460591  mov     byte ptr [rsp+7B8h+var_788], 0
0x102460596  mov     dword ptr [rsp+7B8h+var_790], r14d
0x10246059b  mov     r12d, 2
0x1024605a1  mov     dword ptr [rsp+7B8h+var_798], r12d
0x1024605a6  mov     r9d, r14d
0x1024605a9  lea     r8d, [r12+12h]
0x1024605ae  lea     rdx, aExecuteddl; "ExecuteDDL"
0x1024605b5  call    qword ptr [rax+8]
0x1024605b8  mov     [rsp+7B8h+var_720], r14d
0x1024605c0  mov     rdx, gs:58h
0x1024605c9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1024605d0  mov     ecx, [rax]
0x1024605d2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1024605d9  mov     eax, [rax]
0x1024605db  add     rax, [rdx+rcx*8]
0x1024605df  mov     rax, [rax]
0x1024605e2  mov     [rsp+7B8h+var_728], rax
0x1024605ea  mov     rcx, [rax+90h]
0x1024605f1  mov     rax, [rcx]
0x1024605f4  call    qword ptr [rax+268h]
0x1024605fa  mov     r13, rax
0x1024605fd  mov     [rsp+7B8h+var_728], rax
0x102460605  mov     rdx, [rax]
0x102460608  mov     rcx, rax
0x10246060b  call    qword ptr [rdx+120h]
0x102460611  movzx   ecx, cs:byte_1031852E4
0x102460618  mov     [rsp+7B8h+var_74C], cl
0x10246061c  test    cl, cl
0x10246061e  jz      loc_102460A8E
0x102460624  cmp     cs:byte_1031D5EE8, 0
0x10246062b  jnz     loc_102460A8E
0x102460631  movzx   ecx, cs:byte_10317B170
0x102460638  shr     cl, 4
0x10246063b  mov     [rsp+7B8h+var_74B], cl
  ... truncated ...
```
