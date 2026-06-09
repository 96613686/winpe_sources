# CStmtCreateDB::CreateLocalDatabaseFragment(IMetadataAccess *,ulong,ulong,bool,ulong,ulong,RecoveryUnitDecl *,_GUID const &,AsynchronousDiskPool &)

- ea: `0x101281330`
- end: `0x1012823e5`
- name: `?CreateLocalDatabaseFragment@CStmtCreateDB@@CAXPEAVIMetadataAccess@@KK_NKKPEAVRecoveryUnitDecl@@AEBU_GUID@@AEAVAsynchronousDiskPool@@@Z`
- size: `4277`
- prototype: `static void(struct IMetadataAccess *, unsigned int, unsigned int, bool, unsigned int, unsigned int, struct RecoveryUnitDecl *, const struct _GUID *, struct AsynchronousDiskPool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x101282400`

## callees

- `0x100401070`
- `0x100401433`
- `0x10071db70`
- `0x1007d40d0`
- `0x100a84670`
- `0x100d53750`
- `0x100d63820`
- `0x101281330`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1012817f5`
- `ole32!StringFromGUID2` at `0x1012817f5`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101282228`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012818c0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10128196d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101282036`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012820d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101282205`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012818c0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10128196d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101282036`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1012820d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101282205`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10128199e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10128199e`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1012822a4`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1012822a4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10128186a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101281b06`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012821ac`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10128186a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101281b06`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012821ac`
- `sqldk!SystemThread_TlsIndex` at `0x101281712`
- `sqldk!SystemThread_TlsIndex` at `0x101281aa7`
- `sqldk!SystemThread_TlsIndex` at `0x10128226c`
- `sqldk!SystemThread_TlsOffset` at `0x10128171b`
- `sqldk!SystemThread_TlsOffset` at `0x101281ab0`
- `sqldk!SystemThread_TlsOffset` at `0x101282275`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101282330`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101282374`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1012823b4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101282330`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101282374`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1012823b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101281acb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10128228e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101281acb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10128228e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1012822fc`
- `sqldk!??_V@YAXPEAX@Z` at `0x101282306`
- `sqldk!??_V@YAXPEAX@Z` at `0x101282310`
- `sqldk!??_V@YAXPEAX@Z` at `0x1012822fc`
- `sqldk!??_V@YAXPEAX@Z` at `0x101282306`
- `sqldk!??_V@YAXPEAX@Z` at `0x101282310`
- `sqlmin!?CreateFg@FGMgr@@QEAAXPEAVIMetadataAccess@@PEB_WHW4FG_CONTENT_TYPE@@GAEBU_GUID@@K_NH@Z` at `0x101281ff4`
- `sqlmin!?CreateFg@FGMgr@@QEAAXPEAVIMetadataAccess@@PEB_WHW4FG_CONTENT_TYPE@@GAEBU_GUID@@K_NH@Z` at `0x101281ff4`
- `sqlmin!?OpenDB@DBMgr@@QEAAPEAVDBTABLE@@PEAVBaseXact@@KW4EDBRefType@@HK@Z` at `0x101281eeb`
- `sqlmin!?OpenDB@DBMgr@@QEAAPEAVDBTABLE@@PEAVBaseXact@@KW4EDBRefType@@HK@Z` at `0x101281eeb`
- `sqlmin!?UpdateDwTargetDataPath@@YAJQEB_W@Z` at `0x101281898`
- `sqlmin!?UpdateDwTargetDataPath@@YAJQEB_W@Z` at `0x101281898`
- `sqlmin!?NotifyCreate@RBPEX@@SAXGG@Z` at `0x1012818cc`
- `sqlmin!?NotifyCreate@RBPEX@@SAXGG@Z` at `0x1012818cc`
- `sqlmin!GetDefaultDataPath` at `0x10128193b`
- `sqlmin!GetDefaultDataPath` at `0x10128193b`
- `sqlmin!?InitDefaultFile@CFileDecl@@QEAAXPEB_WH0HPEAVIMemObj@@G@Z` at `0x101281a6c`
- `sqlmin!?InitDefaultFile@CFileDecl@@QEAAXPEB_WH0HPEAVIMemObj@@G@Z` at `0x101281a6c`
- `sqlmin!?CreateRecoveryUnitRow@DBMgr@@QEAAXPEAVIMetadataAccess@@KKAEAUMDAttrRecoveryUnit@@@Z` at `0x101281b5b`
- `sqlmin!?CreateRecoveryUnitRow@DBMgr@@QEAAXPEAVIMetadataAccess@@KKAEAUMDAttrRecoveryUnit@@@Z` at `0x101281b5b`
- `sqlmin!?CreateFilesFromDecls@FileMgr@@SAHPEAVCFileDecl@@0GGPEAV?$SEList@VFileDescription@@$0A@@@QEAVIMemObj@@AEBU_GUID@@PEAPEA_WPEAHPEA_WHGG_N@Z` at `0x101281bd6`
- `sqlmin!?CreateFilesFromDecls@FileMgr@@SAHPEAVCFileDecl@@0GGPEAV?$SEList@VFileDescription@@$0A@@@QEAVIMemObj@@AEBU_GUID@@PEAPEA_WPEAHPEA_WHGG_N@Z` at `0x101281bd6`
- `sqlmin!?CreateStreamFilesFromDecls@StreamFileMgr@@SAXPEAVCFileDecl@@GGPEAV?$SEList@VFileDescription@@$0A@@@1PEAVIMemObj@@AEBU_GUID@@G@Z` at `0x101281c17`
- `sqlmin!?CreateStreamFilesFromDecls@StreamFileMgr@@SAXPEAVCFileDecl@@GGPEAV?$SEList@VFileDescription@@$0A@@@1PEAVIMemObj@@AEBU_GUID@@G@Z` at `0x101281c17`
- `sqlmin!?CreateAndFormatFiles@DBMgr@@QEAAX_KPEBV?$SEList@VFileDescription@@$0A@@@KKPEB_WHPEAVAsynchronousDiskPool@@AEBU_GUID@@KHPEAVBaseXact@@PEAK@Z` at `0x101281d28`
- `sqlmin!?CreateAndFormatFiles@DBMgr@@QEAAX_KPEBV?$SEList@VFileDescription@@$0A@@@KKPEB_WHPEAVAsynchronousDiskPool@@AEBU_GUID@@KHPEAVBaseXact@@PEAK@Z` at `0x101281d28`
- `sqlmin!?CreateStreamFiles@DBMgr@@QEAAXPEBV?$SEList@VFileDescription@@$0A@@@PEAVAsynchronousDiskPool@@PEAVIMemObj@@PEA_WKAEAU_GUID@@VDatabaseStartupInfo@@_N@Z` at `0x101281e14`
- `sqlmin!?CreateStreamFiles@DBMgr@@QEAAXPEBV?$SEList@VFileDescription@@$0A@@@PEAVAsynchronousDiskPool@@PEAVIMemObj@@PEA_WKAEAU_GUID@@VDatabaseStartupInfo@@_N@Z` at `0x101281e14`
- `sqlmin!?CreatePrimaryFileInMaster@DBMgr@@QEAAXPEAVIMetadataAccess@@KKPEB_WK1K@Z` at `0x101281e5e`
- `sqlmin!?CreatePrimaryFileInMaster@DBMgr@@QEAAXPEAVIMetadataAccess@@KKPEB_WK1K@Z` at `0x101281e5e`
- `sqlmin!?StartupDB@DBMgr@@QEAAXVContextHandle@@KAEAVDatabaseStartupInfo@@PEAVBaseXact@@@Z` at `0x101281ebd`
- `sqlmin!?StartupDB@DBMgr@@QEAAXVContextHandle@@KAEAVDatabaseStartupInfo@@PEAVBaseXact@@@Z` at `0x101281ebd`
- `sqlmin!?SyncBootPageWithDbReg@DBMgr@@SA_NPEAVDBTABLE@@PEAVBaseXact@@_N@Z` at `0x101281f14`
- `sqlmin!?SyncBootPageWithDbReg@DBMgr@@SA_NPEAVDBTABLE@@PEAVBaseXact@@_N@Z` at `0x101281f14`
- `sqlmin!?RemapBrickFiles@FileMgr@@QEAAXVContextHandle@@PEAVBaseXact@@@Z` at `0x101281f2f`
- `sqlmin!?RemapBrickFiles@FileMgr@@QEAAXVContextHandle@@PEAVBaseXact@@@Z` at `0x101281f2f`
- `sqlmin!?CopyPruFilesFromBrickFiles@RecoveryUnit@@QEAAXPEAVBaseXact@@@Z` at `0x101281f3b`
- `sqlmin!?CopyPruFilesFromBrickFiles@RecoveryUnit@@QEAAXPEAVBaseXact@@@Z` at `0x101281f3b`
- `sqlmin!?CheckpointDB@@YAXKIW4Type@CheckpointContext@@@Z` at `0x101281f86`
- `sqlmin!?CheckpointDB@@YAXKIW4Type@CheckpointContext@@@Z` at `0x101281f86`
- `sqlmin!?AttachAllFiles@@YAXPEAV?$SEList@VFileDescription@@$0A@@@PEAVRecoveryUnit@@PEAVBaseXact@@@Z` at `0x101282085`
- `sqlmin!?AttachAllFiles@@YAXPEAV?$SEList@VFileDescription@@$0A@@@PEAVRecoveryUnit@@PEAVBaseXact@@@Z` at `0x101282085`
- `sqlmin!?AttachAllStreamFiles@@YAXPEAV?$SEList@VFileDescription@@$0A@@@PEAVRecoveryUnit@@PEAVBaseXact@@@Z` at `0x10128209d`
- `sqlmin!?AttachAllStreamFiles@@YAXPEAV?$SEList@VFileDescription@@$0A@@@PEAVRecoveryUnit@@PEAVBaseXact@@@Z` at `0x10128209d`
- `sqlmin!?HasForeignFiles@FileMgr@@QEBA_NXZ` at `0x1012820f5`
- `sqlmin!?HasForeignFiles@FileMgr@@QEBA_NXZ` at `0x1012820f5`
- `sqlmin!InitializePageServer` at `0x101282132`
- `sqlmin!InitializePageServer` at `0x101282132`
- `sqlmin!?GetPageServerStats@RecoveryUnit@@QEAAPEAUPageServerStats@@XZ` at `0x101282140`
- `sqlmin!?GetPageServerStats@RecoveryUnit@@QEAAPEAUPageServerStats@@XZ` at `0x101282140`
- `sqlmin!PageServerStatsCreate` at `0x101282169`
- `sqlmin!PageServerStatsCreate` at `0x101282169`
- `sqlmin!?RegisterPageServerDb@RecoveryUnit@@QEAAJXZ` at `0x101282181`
- `sqlmin!?RegisterPageServerDb@RecoveryUnit@@QEAAJXZ` at `0x101282181`
- `sqlmin!?StartForeignLogApply@RecoveryUnit@@QEAAXXZ` at `0x1012821d5`
- `sqlmin!?StartForeignLogApply@RecoveryUnit@@QEAAXXZ` at `0x1012821d5`
- `sqlmin!?MarkFullyCreated@DBTABLE@@QEAAXPEAVBaseXact@@@Z` at `0x101282218`
- `sqlmin!?MarkFullyCreated@DBTABLE@@QEAAXPEAVBaseXact@@@Z` at `0x101282218`
- `sqlmin!?GetDwTargetDataPath@@YAPEB_WXZ` at `0x101281933`
- `sqlmin!?GetDwTargetDataPath@@YAPEB_WXZ` at `0x101281933`
- `sqlmin!GetXdbServerGlobals` at `0x1012817ad`
- `sqlmin!GetXdbServerGlobals` at `0x1012818ff`
- `sqlmin!GetXdbServerGlobals` at `0x1012817ad`
- `sqlmin!GetXdbServerGlobals` at `0x1012818ff`

## string_xrefs

- `0x101281963`: `cpwszDefaultDataPath != nullptr`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CStmtCreateDB::CreateLocalDatabaseFragment(
        struct IMetadataAccess *a1,
        unsigned int a2,
        int a3,
        char a4,
        unsigned int a5,
        unsigned int a6,
        struct RecoveryUnitDecl *a7,
        const struct _GUID *a8,
        struct AsynchronousDiskPool *a9)
{
  struct IMemObj *v11; // r13
  __int64 v12; // rax
  void (__fastcall ***v13)(_QWORD, _QWORD, _BYTE *, _QWORD); // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  int v17; // eax
  __int64 v18; // rdx
  int v19; // edi
  __int64 *v20; // rax
  __int64 *i; // rcx
  const wchar_t *DwTargetDataPath; // rax
  const wchar_t *v23; // rsi
  _QWORD *v24; // rax
  _QWORD *v25; // rdi
  unsigned int v26; // eax
  __int64 v27; // rax
  int v28; // r15d
  __int64 v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rsi
  struct RecoveryUnitDecl *v32; // rax
  struct RecoveryUnitDecl *v33; // rdi
  char v34; // dl
  char v35; // dl
  __int64 v36; // r8
  int v37; // eax
  struct AsynchronousDiskPool *v38; // r15
  _OWORD *v39; // rcx
  char *v40; // rax
  void (__fastcall ***v41)(_QWORD, struct IMetadataAccess *, _QWORD, _BYTE *); // rax
  struct BaseXact *v42; // rdi
  __int64 v43; // rsi
  __int64 v44; // r15
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r13
  struct RecoveryUnitDecl *v49; // r14
  __int64 *v50; // rdi
  __int64 *v51; // rax
  int v52; // ecx
  int v53; // ecx
  struct BaseXact *v54; // rdi
  __int64 v55; // rdi
  __int64 j; // rax
  __int64 v57; // rdx
  CFileDecl *v58; // rcx
  __int64 v59; // rdi
  struct Worker *v60; // rcx
  __int64 v61; // rdi
  __int64 *v62; // rcx
  _QWORD *v63; // rdx
  __int64 v64; // rax
  __int64 *v65; // rcx
  _QWORD *v66; // rdx
  __int64 v67; // rax
  struct RecoveryUnitDecl *v68; // rbx
  CFileDecl *v69; // rcx
  const struct SQLError *CurrentException; // rax
  __int64 v71; // [rsp+20h] [rbp-868h]
  int v72; // [rsp+28h] [rbp-860h]
  int v73; // [rsp+38h] [rbp-850h]
  int v74; // [rsp+40h] [rbp-848h]
  int v75; // [rsp+40h] [rbp-848h]
  int v76; // [rsp+48h] [rbp-840h]
  int v77; // [rsp+58h] [rbp-830h]
  int v78; // [rsp+60h] [rbp-828h]
  int v79; // [rsp+68h] [rbp-820h]
  char v80; // [rsp+70h] [rbp-818h]
  unsigned int v82; // [rsp+74h] [rbp-814h]
  int v83; // [rsp+74h] [rbp-814h]
  __int64 v85; // [rsp+80h] [rbp-808h] BYREF
  __int64 *v86; // [rsp+88h] [rbp-800h]
  __int64 v87; // [rsp+90h] [rbp-7F8h] BYREF
  __int64 *v88; // [rsp+98h] [rbp-7F0h]
  int v89; // [rsp+A0h] [rbp-7E8h]
  unsigned int v90; // [rsp+A4h] [rbp-7E4h] BYREF
  __int64 v91; // [rsp+A8h] [rbp-7E0h]
  __int64 v92; // [rsp+B0h] [rbp-7D8h]
  __int64 v93; // [rsp+B8h] [rbp-7D0h]
  char v94; // [rsp+C0h] [rbp-7C8h]
  __int16 v95; // [rsp+C2h] [rbp-7C6h]
  int v96; // [rsp+C8h] [rbp-7C0h]
  int v97; // [rsp+CCh] [rbp-7BCh] BYREF
  const struct _GUID *v98; // [rsp+D0h] [rbp-7B8h]
  struct RecoveryUnitDecl *v99; // [rsp+D8h] [rbp-7B0h]
  const wchar_t *v100; // [rsp+E0h] [rbp-7A8h] BYREF
  __int64 v101; // [rsp+E8h] [rbp-7A0h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-798h] BYREF
  __int64 v103; // [rsp+F8h] [rbp-790h]
  struct RecoveryUnitDecl *v104; // [rsp+100h] [rbp-788h]
  __int64 v105; // [rsp+108h] [rbp-780h]
  __int64 v106; // [rsp+110h] [rbp-778h]
  int v107; // [rsp+118h] [rbp-770h]
  int v108; // [rsp+11Ch] [rbp-76Ch]
  struct AsynchronousDiskPool *v109; // [rsp+120h] [rbp-768h]
  _QWORD v110[7]; // [rsp+128h] [rbp-760h] BYREF
  _BYTE v111[32]; // [rsp+160h] [rbp-728h] BYREF
  _BYTE v112[480]; // [rsp+180h] [rbp-708h] BYREF
  _BYTE v113[16]; // [rsp+360h] [rbp-528h] BYREF
  wchar_t *v114; // [rsp+370h] [rbp-518h]
  unsigned int v115; // [rsp+388h] [rbp-500h]
  int v116; // [rsp+498h] [rbp-3F0h]
  int v117; // [rsp+49Ch] [rbp-3ECh]
  int v118; // [rsp+4A0h] [rbp-3E8h]
  _BYTE v119[48]; // [rsp+4A8h] [rbp-3E0h] BYREF
  int v120; // [rsp+4D8h] [rbp-3B0h]
  char v121; // [rsp+4F0h] [rbp-398h] BYREF
  char v122; // [rsp+4F1h] [rbp-397h]
  char v123; // [rsp+4F2h] [rbp-396h]
  char v124; // [rsp+4F3h] [rbp-395h]
  char v125; // [rsp+4F4h] [rbp-394h]
  int v126; // [rsp+4F8h] [rbp-390h]
  __int16 v127; // [rsp+4FCh] [rbp-38Ch]
  __int64 v128; // [rsp+500h] [rbp-388h]
  int v129; // [rsp+508h] [rbp-380h]
  __int128 v130; // [rsp+510h] [rbp-378h]
  __int128 v131; // [rsp+520h] [rbp-368h]
  __int64 v132; // [rsp+530h] [rbp-358h]
  __int64 v133; // [rsp+538h] [rbp-350h]
  __int128 v134; // [rsp+540h] [rbp-348h]
  char v135; // [rsp+550h] [rbp-338h]
  _QWORD v136[44]; // [rsp+558h] [rbp-330h] BYREF
  GUID v137; // [rsp+6B8h] [rbp-1D0h]
  char v138; // [rsp+6C8h] [rbp-1C0h]
  GUID v139; // [rsp+6D0h] [rbp-1B8h]
  OLECHAR sz; // [rsp+6E0h] [rbp-1A8h] BYREF
  wchar_t v141[36]; // [rsp+6E2h] [rbp-1A6h] BYREF
  int v142; // [rsp+72Ah] [rbp-15Eh]
  wchar_t v143[136]; // [rsp+730h] [rbp-158h] BYREF

  v110[2] = -2;
  v99 = a7;
  v104 = a7;
  v98 = a8;
  v109 = a9;
  v86 = &v85;
  v85 = (__int64)&v85;
  v88 = &v87;
  v87 = (__int64)&v87;
  v100 = 0;
  v90 = 0;
  v121 = 0;
  v122 = 16;
  v123 = 0;
  v124 = 0;
  v125 &= 0xF0u;
  v126 = 0;
  v127 = -1;
  v128 = 0;
  v129 = 2;
  v130 = 0;
  v131 = 0;
  v132 = 0xFFFF;
  v133 = 0;
  v134 = 0;
  v135 &= 0xFCu;
  v136[43] = 0;
  v137 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  v138 = 0;
  memset_0(v136, 0, 0x158u);
  v92 = 0;
  v11 = (struct IMemObj *)(*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)a1 + 8LL))(a1);
  v110[3] = v11;
  v91 = (*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)a1 + 16LL))(a1);
  memset_0(v113, 0, 0x188u);
  v120 = -1;
  v102 = 0;
  v80 = 0;
  v94 = 0;
  v95 = -1;
  v12 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 80LL);
  v93 = v12;
  if ( v12 && !*(_DWORD *)(v12 + 172) && !*(_WORD *)(v12 + 176) )
  {
    v95 = 0;
    *(_WORD *)(v12 + 176) = 203;
    v94 = 1;
  }
  v114 = v143;
  v115 = 258;
  v13 = (void (__fastcall ***)(_QWORD, _QWORD, _BYTE *, _QWORD))(*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)a1 + 72LL))(a1);
  (**v13)(v13, a2, v113, 0);
  v82 = v115;
  if ( *(_BYTE *)(GetXdbServerGlobals(v15, v14) + 12005) && *((_BYTE *)qword_102EF3550 + 120) )
  {
    v139 = CStmtCreateDB::m_gDwPhysicalDbId;
    StringFromGUID2(&CStmtCreateDB::m_gDwPhysicalDbId, &sz, 39);
    v142 = 0;
    v16 = -1;
    do
      ++v16;
    while ( v141[v16] );
    v17 = StringCchPrintfW(v143, 0x81u, L"%ls", v141);
    if ( v17 < 0 )
    {
      _mm_lfence();
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\msql\\proc\\stdb.cpp", 1793, v17);
    }
    if ( 2 * (unsigned __int64)(unsigned int)v16 >= 0x102 )
      _report_rangecheckfailure();
    v143[(unsigned int)v16] = 0;
    v82 = 2 * v16;
    if ( UpdateDwTargetDataPath(v141) )
      utassert_fail(1u, "hr == S_OK", "stdb.cpp", 1803, 0);
  }
  RBPEX::NotifyCreate(a2, 0);
  try
  {
    v20 = (__int64 *)*((_QWORD *)a7 + 2);
    v19 = 0;
    v96 = 0;
    for ( i = v20; i; i = v20 )
    {
      if ( (*((_BYTE *)v20 + 100) & 0x10) == 0 )
        v96 = ++v19;
      v20 = (__int64 *)*v20;
    }
    if ( *(_BYTE *)(GetXdbServerGlobals(0, v18) + 12005)
      && *((_BYTE *)qword_102EF3550 + 120)
      && !FDwSystemDatabase(a2, v11, 0) )
    {
      DwTargetDataPath = GetDwTargetDataPath();
    }
    else
    {
      DwTargetDataPath = (const wchar_t *)GetDefaultDataPath();
    }
    v23 = DwTargetDataPath;
    v110[4] = DwTargetDataPath;
    if ( !DwTargetDataPath )
      utassert_fail(1u, "cpwszDefaultDataPath != nullptr", "stdb.cpp", 1845, 0);
    if ( !v19 )
    {
      v107 = 1854;
      v24 = operator new(0x78u, v11, "sql\\ntdbms\\msql\\proc\\stdb.cpp", 1854, 3u);
      v25 = v24;
      v110[5] = v24;
      if ( v24 )
      {
        *v24 = 0;
        v24[1] = 0;
        v24[2] = 0;
        v24[3] = 0;
        v24[4] = 0;
        *((_DWORD *)v24 + 10) = 0;
        v24[6] = 0;
        *((_DWORD *)v24 + 14) = 0;
        v24[8] = 0;
        *((_DWORD *)v24 + 18) = 0;
        v24[10] = 0;
        *((_DWORD *)v24 + 22) = 0;
        *((_DWORD *)v24 + 23) = 0;
        *((_WORD *)v24 + 48) = 0;
        *((_WORD *)v24 + 49) = 0;
        *((_DWORD *)v24 + 25) &= ~1u;
        v26 = *((_DWORD *)v24 + 25) & 0xFFFFFFFD;
        *((_DWORD *)v25 + 25) = v26;
        v26 |= 4u;
        *((_DWORD *)v25 + 25) = v26;
        v26 &= ~8u;
        *((_DWORD *)v25 + 25) = v26;
        *((_DWORD *)v25 + 25) = v26 & 0xFFFFFFEF;
        v25[13] = 0;
        *((_DWORD *)v25 + 28) = 0;
      }
      else
      {
        v25 = 0;
      }
      v110[6] = v25;
      v80 = 1;
      v27 = -1;
      do
        ++v27;
      while ( v23[v27] );
      v105 = 2 * v27;
      CFileDecl::InitDefaultFile((CFileDecl *)v25, v23, 2 * v27, v143, v82, v11, a3);
      *v25 = *((_QWORD *)a7 + 2);
      *((_QWORD *)a7 + 2) = v25;
    }
    v28 = 0;
    if ( v117 == 1 )
      v28 = v116;
    v89 = v28;
    if ( v28 )
    {
      v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v30 = *(_QWORD *)(v29 + 256);
      if ( !v30 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v30 = *(_QWORD *)(v29 + 256);
      }
      v31 = 3;
      if ( (*(_BYTE *)(*(_QWORD *)(v30 + 992) + 1568LL) & 4) != 0 )
        ex_raise(90, 25, 16, 3, L"tenant creation on DAC");
      v28 = v89;
    }
    else
    {
      v31 = 3;
    }
    v32 = v99;
    v33 = v99;
    while ( v32 )
    {
      LODWORD(v102) = *((_DWORD *)v33 + 1);
      DBMgr::CreateRecoveryUnitRow(
        *(DBMgr **)(qword_102ECFB00 + 32),
        a1,
        a2,
        *(unsigned __int16 *)v33,
        (struct MDAttrRecoveryUnit *)&v102);
      LOBYTE(v79) = *((_BYTE *)v33 + 64);
      LOWORD(v78) = a3;
      LOWORD(v77) = v28;
      FileMgr::CreateFilesFromDecls(
        *((_QWORD *)v33 + 2),
        *((_QWORD *)v33 + 3),
        (unsigned __int16)a2,
        *(unsigned __int16 *)v33,
        &v85,
        v11,
        v98,
        &v100,
        &v90,
        v143,
        v82,
        v77,
        v78,
        v79);
      LOWORD(v73) = *((_WORD *)v33 + 24);
      StreamFileMgr::CreateStreamFilesFromDecls(
        *((_QWORD *)v33 + 2),
        (unsigned __int16)a2,
        0,
        &v85,
        &v87,
        v11,
        v98,
        v73);
      v33 = (struct RecoveryUnitDecl *)*((_QWORD *)v33 + 7);
      v32 = v33;
    }
    v122 |= 0x20u;
    v108 = *(_DWORD *)(qword_102ECFB00 + 14544);
    if ( v108 || (unsigned int)(a3 - 32764) <= 1 )
      v34 = 0x80;
    else
      v34 = 0;
    v123 = v34 | v123 & 0x7F;
    v35 = 2;
    if ( (unsigned int)(a3 - 32764) > 1 )
      v35 = 0;
    v124 = v35 | v124 & 0xFD | 8;
    v36 = 0;
    if ( a4 )
      v36 = v91;
    v37 = 0;
    if ( v117 == 1 )
      v37 = v118;
    v76 = v28;
    v38 = v109;
    DBMgr::CreateAndFormatFiles(
      *(_QWORD *)(qword_102ECFB00 + 32),
      a6,
      &v85,
      a2,
      a3,
      v143,
      v82,
      v109,
      v119,
      v76,
      v37,
      v36,
      &v97);
    v39 = v112;
    v40 = &v121;
    do
    {
      *v39 = *(_OWORD *)v40;
      v39[1] = *((_OWORD *)v40 + 1);
      v39[2] = *((_OWORD *)v40 + 2);
      v39[3] = *((_OWORD *)v40 + 3);
      v39[4] = *((_OWORD *)v40 + 4);
      v39[5] = *((_OWORD *)v40 + 5);
      v39[6] = *((_OWORD *)v40 + 6);
      v39 += 8;
      *(v39 - 1) = *((_OWORD *)v40 + 7);
      v40 += 128;
      --v31;
    }
    while ( v31 );
    *v39 = *(_OWORD *)v40;
    v39[1] = *((_OWORD *)v40 + 1);
    v39[2] = *((_OWORD *)v40 + 2);
    v39[3] = *((_OWORD *)v40 + 3);
    v39[4] = *((_OWORD *)v40 + 4);
    v39[5] = *((_OWORD *)v40 + 5);
    LOBYTE(v74) = *((_BYTE *)v99 + 64);
    DBMgr::CreateStreamFiles(*(_QWORD *)(qword_102ECFB00 + 32), &v87, v38, v11, v143, v82, v98, v112, v74);
    DBMgr::CreatePrimaryFileInMaster(*(DBMgr **)(qword_102ECFB00 + 32), a1, a2, 0, v114, v115, v100, v90);
    v41 = (void (__fastcall ***)(_QWORD, struct IMetadataAccess *, _QWORD, _BYTE *))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(qword_102ECFB00 + 43248) + 32LL))(*(_QWORD *)(qword_102ECFB00 + 43248));
    (**v41)(v41, a1, a2, v113);
    v105 = 0;
    v42 = (struct BaseXact *)v91;
    DBMgr::StartupDB(*(_QWORD *)(qword_102ECFB00 + 32), 0, a2, &v121, v91);
    v106 = qword_102ECFB00;
    v43 = DBMgr::OpenDB(*(_QWORD *)(qword_102ECFB00 + 32), 0, a2, 21, 1, 0);
    v92 = v43;
    v103 = *(_QWORD *)(v43 + 4624);
    v44 = v103;
    DBMgr::SyncBootPageWithDbReg((struct DBTABLE *)v43, v42, 0);
    v106 = 0;
    FileMgr::RemapBrickFiles(*(_QWORD *)(v44 + 1696), 0, v42);
    RecoveryUnit::CopyPruFilesFromBrickFiles((RecoveryUnit *)v44, v42);
    if ( a5 != v97 )
    {
      LOBYTE(v45) = 1;
      v46 = (*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, __int64, _QWORD, _DWORD, _DWORD))(*(_QWORD *)a1 + 56LL))(
              a1,
              a2,
              v45,
              0,
              0,
              0);
      LOBYTE(v47) = 1;
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v46 + 1072LL))(v46, a5, v47);
    }
    CheckpointDB(a2, 0, 0);
    v48 = *(_QWORD *)(*(_QWORD *)(v43 + 4624) + 1688LL);
    v49 = v99;
    v50 = (__int64 *)*((_QWORD *)v99 + 5);
    v51 = v50;
    while ( v51 )
    {
      LOBYTE(v75) = *((_BYTE *)v50 + 45);
      LOWORD(v72) = *((_WORD *)v50 + 23);
      LODWORD(v71) = *((_DWORD *)v50 + 10);
      FGMgr::CreateFg(v48, a1, v50[2], *((unsigned int *)v50 + 6), v71, v72, v51 + 6, (unsigned __int16)v72, v75, 18);
      if ( *((_BYTE *)v50 + 45) )
      {
        v52 = *((_DWORD *)v50 + 10);
        if ( v52 )
        {
          v53 = v52 - 1;
          if ( v53 )
          {
            if ( v53 == 2 )
              *(_DWORD *)(v43 + 3484) = *((unsigned __int16 *)v50 + 23);
            else
              utassert_fail(1u, "FALSE", "stdb.cpp", 2066, "Invalid switch value");
          }
          else
          {
            *(_DWORD *)(v43 + 3480) = *((unsigned __int16 *)v50 + 23);
          }
        }
        else
        {
          *(_DWORD *)(v43 + 3476) = *((unsigned __int16 *)v50 + 23);
        }
      }
      v51 = (__int64 *)*v50;
      v50 = (__int64 *)*v50;
    }
    v54 = (struct BaseXact *)v91;
    AttachAllFiles(&v85, *(_QWORD *)(v43 + 4624), v91);
    AttachAllStreamFiles(&v87, *(_QWORD *)(v43 + 4624), v54);
    if ( a6 > 1 )
    {
      v55 = *((_QWORD *)v49 + 7);
      for ( j = v55; j; j = v55 )
      {
        utassert_fail(1u, "0", "stdb.cpp", 5583, 0);
        v55 = *(_QWORD *)(v55 + 56);
      }
      v54 = (struct BaseXact *)v91;
    }
    if ( FileMgr::HasForeignFiles(*(FileMgr **)(v44 + 1696)) )
    {
      if ( !*((_BYTE *)qword_102EF3550 + 1130)
        || (v57 = *((unsigned __int8 *)qword_102ECFB10 + 1687), (v57 & 0x40) != 0) )
      {
        if ( !RecoveryUnit::GetPageServerStats((RecoveryUnit *)v44) )
        {
          v101 = 0;
          PageServerStatsCreate(*(_QWORD *)(*(_QWORD *)(v44 + 1712) + 688LL), &v101);
          *(_QWORD *)(v44 + 8680) = v101;
        }
        v83 = RecoveryUnit::RegisterPageServerDb((RecoveryUnit *)v44);
        if ( v83 < 0 )
        {
          _mm_lfence();
          LODWORD(v71) = v83;
          ex_raise(494, 11, 16, 1, v71);
          v43 = v92;
          v44 = v103;
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v44 + 1736) + 672LL))(*(_QWORD *)(v44 + 1736));
        RecoveryUnit::StartForeignLogApply((RecoveryUnit *)v44);
      }
      else
      {
        LOBYTE(v57) = 1;
        InitializePageServer(v44, v57);
      }
    }
    else if ( *(_BYTE *)(v44 + 8273) )
    {
      utassert_fail(1u, "!pru->HasForeignFiles()", "stdb.cpp", 2133, 0);
    }
    if ( a4 )
      DBTABLE::MarkFullyCreated((DBTABLE *)v43, v54);
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 21);
    v92 = 0;
    if ( v80 )
    {
      v58 = (CFileDecl *)*((_QWORD *)v49 + 2);
      if ( v58 )
        CFileDecl::`scalar deleting destructor'(v58, 1u);
      *((_QWORD *)v49 + 2) = 0;
    }
  }
  catch ( SQLError v111 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v110, (const struct SQLError *)v111);
      if ( v92 )
        ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 21);
      if ( v80 )
      {
        v68 = v104;
        v69 = (CFileDecl *)*((_QWORD *)v104 + 2);
        if ( v69 )
          CFileDecl::`scalar deleting destructor'(v69, 1u);
        *((_QWORD *)v68 + 2) = 0;
      }
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v110);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v110);
    }
    catch ( ShortStackException )
    {
    }
  }
  v59 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v60 = *(struct Worker **)(v59 + 256);
  if ( !v60 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v60 = *(struct Worker **)(v59 + 256);
  }
  if ( *((_DWORD *)v60 + 139) )
    ExceptionPostCatchActions(v60);
  if ( v93 && v94 )
  {
    *(_WORD *)(v93 + 176) = v95;
    v95 = -1;
    v94 = 0;
  }
  if ( (v122 & 0x10) != 0 )
  {
    v61 = v134;
    if ( (_QWORD)v134 )
    {
      operator delete[](*(void **)(v134 + 16));
      operator delete[](*(void **)(v61 + 48));
      operator delete[](*(void **)(v61 + 80));
      if ( *(_QWORD *)v61 )
        RemapFileEntry::`scalar deleting destructor'(*(RemapFileEntry **)v61, 1u);
      operator delete((void *)v61, 0x58u);
    }
  }
  while ( 1 )
  {
    v62 = v88;
    if ( v88 == &v87 || !v88 )
      break;
    v63 = (_QWORD *)v88[1];
    v64 = *v88;
    *(_QWORD *)(v64 + 8) = v63;
    *v63 = v64;
    v62[1] = 0;
    *v62 = 0;
    operator delete(v62, 0x6E0u);
  }
  while ( 1 )
  {
    v65 = v86;
    if ( v86 == &v85 || !v86 )
      break;
    v66 = (_QWORD *)v86[1];
    v67 = *v86;
    *(_QWORD *)(v67 + 8) = v66;
    *v66 = v67;
    v65[1] = 0;
    *v65 = 0;
    operator delete(v65, 0x6E0u);
  }
}

```

## disassembly

```asm
0x101281330  mov     r11, rsp
0x101281333  push    rbx
0x101281334  push    rsi
0x101281335  push    rdi
0x101281336  push    r12
0x101281338  push    r13
0x10128133a  push    r14
0x10128133c  push    r15
0x10128133e  sub     rsp, 850h
0x101281345  mov     qword ptr [r11-750h], 0FFFFFFFFFFFFFFFEh
0x101281350  mov     rax, cs:__security_cookie
0x101281357  xor     rax, rsp
0x10128135a  mov     [rsp+888h+var_48], rax
0x101281362  mov     [rsp+888h+var_817], r9b
0x101281367  mov     [rsp+888h+var_810], r8d
0x10128136c  mov     r14d, edx
0x10128136f  mov     r12, rcx
0x101281372  mov     r15, [rsp+888h+arg_30]
0x10128137a  mov     [rsp+888h+var_7B0], r15
0x101281382  mov     [rsp+888h+var_788], r15
0x10128138a  mov     rax, [rsp+888h+arg_38]
0x101281392  mov     [rsp+888h+var_7B8], rax
0x10128139a  mov     rax, [rsp+888h+arg_40]
0x1012813a2  mov     [rsp+888h+var_768], rax
0x1012813aa  xor     ebx, ebx
0x1012813ac  mov     [r11-808h], rbx
0x1012813b3  mov     [r11-800h], rbx
0x1012813ba  lea     rax, [r11-808h]
0x1012813c1  mov     [r11-800h], rax
0x1012813c8  lea     rax, [r11-808h]
0x1012813cf  mov     [r11-808h], rax
0x1012813d6  lea     rax, [r11-808h]
0x1012813dd  mov     [r11-800h], rax
0x1012813e4  lea     rax, [r11-808h]
0x1012813eb  mov     [r11-808h], rax
0x1012813f2  mov     [r11-7F8h], rbx
0x1012813f9  mov     [r11-7F0h], rbx
0x101281400  lea     rax, [r11-7F8h]
0x101281407  mov     [r11-7F0h], rax
0x10128140e  lea     rax, [r11-7F8h]
0x101281415  mov     [r11-7F8h], rax
0x10128141c  lea     rax, [r11-7F8h]
0x101281423  mov     [r11-7F0h], rax
0x10128142a  lea     rax, [r11-7F8h]
0x101281431  mov     [r11-7F8h], rax
0x101281438  mov     [r11-7A8h], rbx
0x10128143f  mov     [rsp+888h+var_7E4], ebx
0x101281446  movzx   ecx, [rsp+888h+var_398]
0x10128144e  and     cl, 0FEh
0x101281451  mov     [rsp+888h+var_398], cl
0x101281458  movzx   eax, cl
0x10128145b  and     al, 0FDh
0x10128145d  mov     [rsp+888h+var_398], al
0x101281464  movzx   eax, cl
0x101281467  and     al, 0F9h
0x101281469  mov     [rsp+888h+var_398], al
0x101281470  movzx   eax, cl
0x101281473  and     al, 0F1h
0x101281475  mov     [rsp+888h+var_398], al
0x10128147c  movzx   eax, cl
0x10128147f  and     al, 0E1h
0x101281481  mov     [rsp+888h+var_398], al
0x101281488  movzx   eax, cl
0x10128148b  and     al, 0C1h
0x10128148d  mov     [rsp+888h+var_398], al
0x101281494  and     cl, 81h
0x101281497  mov     [rsp+888h+var_398], cl
0x10128149e  mov     [rsp+888h+var_398], bl
0x1012814a5  movzx   ecx, [rsp+888h+var_397]
0x1012814ad  and     cl, 0FEh
0x1012814b0  mov     [rsp+888h+var_397], cl
0x1012814b7  movzx   eax, cl
0x1012814ba  and     al, 0FDh
0x1012814bc  mov     [rsp+888h+var_397], al
0x1012814c3  movzx   eax, cl
0x1012814c6  and     al, 0F9h
0x1012814c8  mov     [rsp+888h+var_397], al
0x1012814cf  and     cl, 0F1h
0x1012814d2  mov     [rsp+888h+var_397], cl
0x1012814d9  or      cl, 10h
0x1012814dc  mov     [rsp+888h+var_397], cl
0x1012814e3  movzx   eax, cl
0x1012814e6  and     al, 0DFh
0x1012814e8  mov     [rsp+888h+var_397], al
0x1012814ef  movzx   eax, cl
0x1012814f2  and     al, 9Fh
0x1012814f4  mov     [rsp+888h+var_397], al
0x1012814fb  and     cl, 1Fh
0x1012814fe  mov     [rsp+888h+var_397], cl
0x101281505  movzx   ecx, [rsp+888h+var_396]
0x10128150d  and     cl, 0FEh
0x101281510  mov     [rsp+888h+var_396], cl
0x101281517  movzx   eax, cl
0x10128151a  and     al, 0FDh
0x10128151c  mov     [rsp+888h+var_396], al
0x101281523  movzx   eax, cl
0x101281526  and     al, 0F9h
0x101281528  mov     [rsp+888h+var_396], al
0x10128152f  movzx   eax, cl
0x101281532  and     al, 0F1h
0x101281534  mov     [rsp+888h+var_396], al
0x10128153b  movzx   eax, cl
0x10128153e  and     al, 0E1h
0x101281540  mov     [rsp+888h+var_396], al
0x101281547  movzx   eax, cl
0x10128154a  and     al, 0C1h
0x10128154c  mov     [rsp+888h+var_396], al
0x101281553  and     cl, 81h
0x101281556  mov     [rsp+888h+var_396], cl
0x10128155d  mov     [rsp+888h+var_396], bl
0x101281564  movzx   ecx, [rsp+888h+var_395]
0x10128156c  and     cl, 0FEh
0x10128156f  mov     [rsp+888h+var_395], cl
0x101281576  movzx   eax, cl
0x101281579  and     al, 0FDh
0x10128157b  mov     [rsp+888h+var_395], al
0x101281582  movzx   eax, cl
0x101281585  and     al, 0F9h
0x101281587  mov     [rsp+888h+var_395], al
0x10128158e  movzx   eax, cl
0x101281591  and     al, 0F1h
0x101281593  mov     [rsp+888h+var_395], al
0x10128159a  movzx   eax, cl
0x10128159d  and     al, 0E1h
0x10128159f  mov     [rsp+888h+var_395], al
0x1012815a6  movzx   eax, cl
0x1012815a9  and     al, 0C1h
0x1012815ab  mov     [rsp+888h+var_395], al
0x1012815b2  and     cl, 81h
0x1012815b5  mov     [rsp+888h+var_395], cl
0x1012815bc  mov     [rsp+888h+var_395], bl
0x1012815c3  movzx   ecx, [rsp+888h+var_394]
0x1012815cb  and     cl, 0FEh
0x1012815ce  mov     [rsp+888h+var_394], cl
0x1012815d5  movzx   eax, cl
0x1012815d8  and     al, 0FDh
0x1012815da  mov     [rsp+888h+var_394], al
0x1012815e1  movzx   eax, cl
0x1012815e4  and     al, 0F9h
0x1012815e6  mov     [rsp+888h+var_394], al
0x1012815ed  and     cl, 0F1h
0x1012815f0  mov     [rsp+888h+var_394], cl
0x1012815f7  mov     [rsp+888h+var_390], ebx
0x1012815fe  mov     eax, 0FFFFh
0x101281603  mov     [rsp+888h+var_38C], ax
0x10128160b  mov     [r11-388h], rbx
0x101281612  mov     [rsp+888h+var_380], 2
0x10128161d  xorps   xmm0, xmm0
0x101281620  movdqa  [rsp+888h+var_378], xmm0
0x101281629  xorps   xmm1, xmm1
0x10128162c  movdqa  [rsp+888h+var_368], xmm1
0x101281635  mov     [r11-358h], rax
0x10128163c  mov     [r11-350h], rbx
0x101281643  movdqa  [rsp+888h+var_348], xmm0
0x10128164c  movzx   eax, [rsp+888h+var_338]
0x101281654  and     al, 0FEh
0x101281656  mov     [rsp+888h+var_338], al
0x10128165d  and     al, 0FDh
0x10128165f  mov     [rsp+888h+var_338], al
0x101281666  mov     [r11-1D8h], rbx
0x10128166d  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x101281674  movups  [rsp+888h+var_1D0], xmm0
0x10128167c  mov     [rsp+888h+var_1C0], bl
0x101281683  xor     edx, edx; Val
0x101281685  mov     r8d, 158h; Size
0x10128168b  lea     rcx, [r11-330h]; void *
0x101281692  call    memset_0
0x101281697  nop
0x101281698  mov     [rsp+888h+var_7D8], rbx
0x1012816a0  mov     rax, [r12]
0x1012816a4  mov     rcx, r12
0x1012816a7  call    qword ptr [rax+8]
0x1012816aa  mov     r13, rax
0x1012816ad  mov     [rsp+888h+var_748], rax
0x1012816b5  mov     rdx, [r12]
0x1012816b9  mov     rcx, r12
0x1012816bc  call    qword ptr [rdx+10h]
0x1012816bf  mov     [rsp+888h+var_7E0], rax
0x1012816c7  xor     edx, edx; Val
0x1012816c9  mov     r8d, 188h; Size
0x1012816cf  lea     rcx, [rsp+888h+var_528]; void *
0x1012816d7  call    memset_0
0x1012816dc  mov     [rsp+888h+var_3B0], 0FFFFFFFFh
0x1012816e7  mov     [rsp+888h+var_798], rbx
0x1012816ef  mov     [rsp+888h+var_818], bl
0x1012816f3  mov     [rsp+888h+var_7C8], bl
0x1012816fa  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x101281701  mov     [rsp+888h+var_7C6], si
0x101281709  mov     r8, gs:58h
0x101281712  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x101281719  mov     edx, [rcx]
0x10128171b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101281722  mov     ecx, [rax]
0x101281724  add     rcx, [r8+rdx*8]
0x101281728  mov     rax, [rcx+50h]
0x10128172c  mov     [rsp+888h+var_7D0], rax
0x101281734  test    rax, rax
0x101281737  jz      short loc_101281766
0x101281739  cmp     [rax+0ACh], ebx
0x10128173f  jnz     short loc_101281766
0x101281741  cmp     bx, [rax+0B0h]
0x101281748  jnz     short loc_101281766
0x10128174a  mov     [rsp+888h+var_7C6], bx
0x101281752  mov     ecx, 0CBh
0x101281757  mov     [rax+0B0h], cx
0x10128175e  mov     [rsp+888h+var_7C8], 1
0x101281766  lea     rax, [rsp+888h+var_158]
0x10128176e  mov     [rsp+888h+var_518], rax
0x101281776  mov     [rsp+888h+var_500], 102h
0x101281781  mov     rax, [r12]
0x101281785  mov     rcx, r12
0x101281788  call    qword ptr [rax+48h]
0x10128178b  mov     r10, [rax]
0x10128178e  xor     r9d, r9d
0x101281791  lea     r8, [rsp+888h+var_528]
0x101281799  mov     edx, r14d
0x10128179c  mov     rcx, rax
0x10128179f  call    qword ptr [r10]
0x1012817a2  mov     edi, [rsp+888h+var_500]
0x1012817a9  mov     [rsp+888h+var_814], edi
0x1012817ad  call    cs:__imp_GetXdbServerGlobals
0x1012817b3  cmp     byte ptr [rax+2EE5h], 0
0x1012817ba  jz      loc_1012818C6
0x1012817c0  mov     rax, cs:qword_102EF3550
0x1012817c7  cmp     byte ptr [rax+78h], 0
0x1012817cb  jz      loc_1012818C6
0x1012817d1  movups  xmm0, xmmword ptr cs:?m_gDwPhysicalDbId@CStmtCreateDB@@0U_GUID@@A.Data1; _GUID CStmtCreateDB::m_gDwPhysicalDbId ...
0x1012817d8  movaps  [rsp+888h+var_1B8], xmm0
0x1012817e0  mov     r8d, 27h ; '''; cchMax
0x1012817e6  lea     rdx, [rsp+888h+sz]; lpsz
0x1012817ee  lea     rcx, ?m_gDwPhysicalDbId@CStmtCreateDB@@0U_GUID@@A; rguid
0x1012817f5  call    cs:__imp_StringFromGUID2
0x1012817fb  mov     [rsp+888h+var_15E], ebx
0x101281802  lea     rax, [rsp+888h+var_1A6]
0x10128180a  mov     rdi, rsi
0x10128180d  nop     dword ptr [rax]
0x101281810  inc     rdi
0x101281813  cmp     word ptr [rax+rdi*2], 0
0x101281818  jnz     short loc_101281810
0x10128181a  lea     r9, [rsp+888h+var_1A6]
0x101281822  lea     r8, aLs_7; "%ls"
0x101281829  mov     edx, 81h; unsigned __int64
0x10128182e  lea     rcx, [rsp+888h+var_158]; wchar_t *
0x101281836  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10128183b  test    eax, eax
0x10128183d  jns     short loc_101281870
0x10128183f  lfence
0x101281842  mov     dword ptr [rsp+888h+var_858], eax
0x101281846  mov     dword ptr [rsp+888h+var_860], 701h
0x10128184e  lea     rsi, aSqlNtdbmsMsqlP_120; "sql\\ntdbms\\msql\\proc\\stdb.cpp"
0x101281855  mov     [rsp+888h+var_868], rsi
0x10128185a  mov     edx, 7
0x10128185f  lea     ecx, [rdx-3]
0x101281862  lea     r9d, [rdx-6]
0x101281866  lea     r8d, [rdx+9]
0x10128186a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101281870  mov     eax, edi
0x101281872  add     rax, rax
0x101281875  cmp     rax, 102h
0x10128187b  jnb     loc_1012823DF
0x101281881  mov     [rsp+rax+888h+var_158], bx
0x101281889  lea     eax, [rdi+rdi]
0x10128188c  mov     [rsp+888h+var_814], eax
0x101281890  lea     rcx, [rsp+888h+var_1A6]
0x101281898  call    cs:__imp_?UpdateDwTargetDataPath@@YAJQEB_W@Z; UpdateDwTargetDataPath(wchar_t const * const)
0x10128189e  test    eax, eax
0x1012818a0  jz      short loc_1012818C6
0x1012818a2  mov     [rsp+888h+var_868], rbx
0x1012818a7  mov     r9d, 70Bh
0x1012818ad  lea     r8, aStdbCpp; "stdb.cpp"
0x1012818b4  lea     rdx, aHrSOk; "hr == S_OK"
0x1012818bb  mov     ecx, 1
0x1012818c0  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1012818c6  xor     edx, edx
0x1012818c8  movzx   ecx, r14w
0x1012818cc  call    cs:__imp_?NotifyCreate@RBPEX@@SAXGG@Z; RBPEX::NotifyCreate(ushort,ushort)
0x1012818d2  nop
0x1012818d3  mov     rax, [r15+10h]
0x1012818d7  mov     edi, ebx
0x1012818d9  mov     [rsp+888h+var_7C0], ebx
0x1012818e0  mov     rcx, rax
0x1012818e3  test    rcx, rcx
0x1012818e6  jz      short loc_1012818FF
0x1012818e8  test    byte ptr [rax+64h], 10h
0x1012818ec  jnz     short loc_1012818F7
0x1012818ee  inc     edi
0x1012818f0  mov     [rsp+888h+var_7C0], edi
0x1012818f7  mov     rax, [rax]
0x1012818fa  mov     rcx, rax
0x1012818fd  jmp     short loc_1012818E3
0x1012818ff  call    cs:__imp_GetXdbServerGlobals
0x101281905  movzx   ecx, byte ptr [rax+2EE5h]
0x10128190c  mov     [rsp+888h+var_80C], cl
0x101281910  test    cl, cl
0x101281912  jz      short loc_10128193B
0x101281914  mov     rax, cs:qword_102EF3550
0x10128191b  cmp     byte ptr [rax+78h], 0
0x10128191f  jz      short loc_10128193B
0x101281921  xor     r8d, r8d; struct BaseXact *
0x101281924  mov     rdx, r13; struct IMemObj *
  ... truncated ...
```
