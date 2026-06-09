# DBMgr::DetachDB(ContextHandle,wchar_t const *,int,int,int,AutoSimpleXact *,AutoDbLock *)

- ea: `0x101708510`
- end: `0x10170a0f9`
- name: `?DetachDB@DBMgr@@QEAAXVContextHandle@@PEB_WHHHPEAVAutoSimpleXact@@PEAVAutoDbLock@@@Z`
- size: `7145`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x101eb1840`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100401fcf`
- `0x100403430`
- `0x1004ab3d0`
- `0x1004abbd0`
- `0x1004bf030`
- `0x1004bff60`
- `0x1004d9cf0`
- `0x10053fe80`
- `0x1005a6310`
- `0x1005cc960`
- `0x1005cccc0`
- `0x1005ce7c0`
- `0x1005cef70`
- `0x1005d58b0`
- `0x100650250`
- `0x100ac5d80`
- `0x1011538d0`
- `0x1016fc920`
- `0x1016fce50`
- `0x101708510`
- `0x10171e840`
- `0x10171ee70`
- `0x10171f7a0`
- `0x10171fb90`
- `0x101738cb0`
- `0x101738dd0`
- `0x101983c70`
- `0x101983ed0`
- `0x101ad7740`
- `0x102064b40`
- `0x102066d60`
- `0x1020b3d50`
- `0x1023adf80`

## import_xrefs

- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10170893e`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10170893e`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101709120`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101709540`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101709af0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1017098d1`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101709c8f`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10170a06a`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1017098d1`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101709c8f`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10170a06a`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x1017097f4`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x101709bc5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101708ddf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101709164`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101708ddf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101709164`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708873`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708966`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017089e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708a37`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708b00`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708b2a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708c8f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708f93`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101709008`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10170922d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017092f7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708873`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708966`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017089e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708a37`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708b00`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708b2a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708c8f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101708f93`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101709008`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10170922d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017092f7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017086ad`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101708772`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101708ad6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101709202`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017093cc`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101709a29`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017086ad`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101708772`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101708ad6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101709202`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017093cc`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101709a29`
- `sqldk!SystemThread_TlsIndex` at `0x10170865e`
- `sqldk!SystemThread_TlsIndex` at `0x101708723`
- `sqldk!SystemThread_TlsIndex` at `0x101708a87`
- `sqldk!SystemThread_TlsIndex` at `0x101708b41`
- `sqldk!SystemThread_TlsIndex` at `0x101708bdf`
- `sqldk!SystemThread_TlsIndex` at `0x101708cfb`
- `sqldk!SystemThread_TlsIndex` at `0x101708d4c`
- `sqldk!SystemThread_TlsIndex` at `0x101708eae`
- `sqldk!SystemThread_TlsIndex` at `0x1017091b3`
- `sqldk!SystemThread_TlsIndex` at `0x10170937d`
- `sqldk!SystemThread_TlsIndex` at `0x101709879`
- `sqldk!SystemThread_TlsIndex` at `0x1017099d2`
- `sqldk!SystemThread_TlsIndex` at `0x101709a85`
- `sqldk!SystemThread_TlsIndex` at `0x101709c37`
- `sqldk!SystemThread_TlsIndex` at `0x101709e60`
- `sqldk!SystemThread_TlsIndex` at `0x10170a032`
- `sqldk!SystemThread_TlsIndex` at `0x10170a094`
- `sqldk!SystemThread_TlsOffset` at `0x101708667`
- `sqldk!SystemThread_TlsOffset` at `0x10170872c`
- `sqldk!SystemThread_TlsOffset` at `0x101708a90`
- `sqldk!SystemThread_TlsOffset` at `0x101708b52`
- `sqldk!SystemThread_TlsOffset` at `0x101708bf0`
- `sqldk!SystemThread_TlsOffset` at `0x101708d04`
- `sqldk!SystemThread_TlsOffset` at `0x101708d55`
- `sqldk!SystemThread_TlsOffset` at `0x101708ebf`
- `sqldk!SystemThread_TlsOffset` at `0x1017091bc`
- `sqldk!SystemThread_TlsOffset` at `0x101709386`
- `sqldk!SystemThread_TlsOffset` at `0x101709882`
- `sqldk!SystemThread_TlsOffset` at `0x1017099db`
- `sqldk!SystemThread_TlsOffset` at `0x101709a8e`
- `sqldk!SystemThread_TlsOffset` at `0x101709c40`
- `sqldk!SystemThread_TlsOffset` at `0x101709e71`
- `sqldk!SystemThread_TlsOffset` at `0x10170a03b`
- `sqldk!SystemThread_TlsOffset` at `0x10170a09d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017098ab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101709ab7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101709c69`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10170a054`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017098ab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101709ab7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101709c69`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10170a054`
- `sqllang!?CloseEncryptionKeysOfDatabaseFromSession@@YAXK@Z` at `0x101709915`
- `sqllang!?CloseEncryptionKeysOfDatabaseFromSession@@YAXK@Z` at `0x101709915`
- `sqllang!?DetachDB@QPEvent@@YAXK@Z` at `0x10170991d`
- `sqllang!?DetachDB@QPEvent@@YAXK@Z` at `0x10170991d`
- `sqllang!?InitializeAndOverride@AutoOverrideMsqlXact@@QEAAXXZ` at `0x101708fbc`
- `sqllang!?InitializeAndOverride@AutoOverrideMsqlXact@@QEAAXXZ` at `0x101708fbc`
- `sqllang!??1AutoOverrideMsqlXact@@QEAA@XZ` at `0x101709a5b`
- `sqllang!??1AutoOverrideMsqlXact@@QEAA@XZ` at `0x101709a5b`
- `sqllang!?MarkAppDomainsForUnload@@YAXKKPEAVRecoveryUnit@@@Z` at `0x1017097c0`
- `sqllang!?MarkAppDomainsForUnload@@YAXKKPEAVRecoveryUnit@@@Z` at `0x1017097c0`
- `sqllang!?RemoveByDbid@CCache@@SAXKW4ESpCacheRemoveReason@XeSqlPkg@@E@Z` at `0x1017097d0`
- `sqllang!?RemoveByDbid@CCache@@SAXKW4ESpCacheRemoveReason@XeSqlPkg@@E@Z` at `0x1017097d0`

## string_xrefs

- `0x101708dd5`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall DBMgr::DetachDB(
        DBMgr *a1,
        __int64 a2,
        const wchar_t *a3,
        unsigned int a4,
        int a5,
        int a6,
        _QWORD *a7,
        __int64 a8)
{
  unsigned __int64 v8; // r12
  const wchar_t *v9; // r13
  DBMgr *v10; // r14
  __int64 v11; // rax
  struct CSessionTraceFlags *v12; // rcx
  __int64 v13; // rax
  struct CSessionTraceFlags *v14; // rcx
  struct BaseXact *v15; // rax
  struct IMS_DatabaseReg *v16; // rsi
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // rax
  struct CSessionTraceFlags *v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // r9
  unsigned int v23; // esi
  char v24; // si
  __int64 v25; // rax
  __int64 v26; // r9
  int v27; // eax
  __int64 v28; // rdx
  struct IMS_DatabaseReg *v29; // rdi
  __int64 v30; // r9
  __int64 v31; // rdi
  __int64 v32; // rax
  struct CSessionTraceFlags *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int16 v37; // cx
  __int16 i; // ax
  __int64 v39; // r13
  struct CSessionTraceFlags *v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r8
  int v43; // r12d
  __int64 v44; // rdi
  struct Worker *v45; // rcx
  _BOOL8 v46; // r8
  unsigned int v47; // edi
  unsigned int v48; // edx
  __int64 v49; // rax
  struct CSessionTraceFlags *v50; // rcx
  __int64 v51; // rdi
  __int64 v52; // rcx
  struct IMetadataAccess *v53; // r12
  struct IMS_DatabaseReg *v54; // rdi
  unsigned int v55; // esi
  __int64 v56; // rdi
  bool v57; // zf
  __int64 v58; // rax
  __int64 v59; // rdi
  struct Worker *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rax
  _BOOL8 v63; // r8
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r10
  __int64 v67; // rbx
  struct Worker *v68; // rcx
  __int64 v69; // rcx
  const struct SQLError *CurrentException; // rax
  int (*v71)(int, int, int, int, char *); // [rsp+20h] [rbp-D78h]
  struct Worker *v72; // [rsp+28h] [rbp-D70h]
  __int64 v73; // [rsp+30h] [rbp-D68h]
  int v74; // [rsp+38h] [rbp-D60h]
  unsigned int v75; // [rsp+50h] [rbp-D48h]
  int v76; // [rsp+58h] [rbp-D40h]
  __int64 v77; // [rsp+60h] [rbp-D38h]
  __int16 v78; // [rsp+68h] [rbp-D30h]
  BOOL v79; // [rsp+6Ch] [rbp-D2Ch]
  int v80; // [rsp+70h] [rbp-D28h]
  int v81; // [rsp+80h] [rbp-D18h] BYREF
  int v82; // [rsp+84h] [rbp-D14h] BYREF
  unsigned int v83; // [rsp+88h] [rbp-D10h]
  int v84; // [rsp+8Ch] [rbp-D0Ch]
  int v85; // [rsp+90h] [rbp-D08h]
  __int64 v86; // [rsp+98h] [rbp-D00h]
  __int64 v87; // [rsp+A0h] [rbp-CF8h]
  unsigned int v88; // [rsp+A8h] [rbp-CF0h]
  unsigned int v89; // [rsp+B0h] [rbp-CE8h] BYREF
  unsigned int v90; // [rsp+B4h] [rbp-CE4h] BYREF
  void **v91; // [rsp+B8h] [rbp-CE0h] BYREF
  __int64 v92; // [rsp+C0h] [rbp-CD8h]
  __int64 v93; // [rsp+C8h] [rbp-CD0h] BYREF
  _QWORD *v94; // [rsp+D0h] [rbp-CC8h]
  int v95; // [rsp+D8h] [rbp-CC0h] BYREF
  int v96; // [rsp+DCh] [rbp-CBCh] BYREF
  int v97; // [rsp+E0h] [rbp-CB8h]
  __int128 v98; // [rsp+E8h] [rbp-CB0h]
  int v99; // [rsp+F8h] [rbp-CA0h]
  int v100; // [rsp+FCh] [rbp-C9Ch]
  int v101; // [rsp+100h] [rbp-C98h]
  int v102; // [rsp+104h] [rbp-C94h]
  int v103; // [rsp+108h] [rbp-C90h]
  int v104; // [rsp+10Ch] [rbp-C8Ch]
  __int16 v105; // [rsp+110h] [rbp-C88h]
  DBMgr *v106; // [rsp+118h] [rbp-C80h]
  void (__fastcall ***v107)(_QWORD); // [rsp+120h] [rbp-C78h] BYREF
  const wchar_t *v108; // [rsp+128h] [rbp-C70h]
  struct IMS_DatabaseReg *v109; // [rsp+130h] [rbp-C68h]
  int v110; // [rsp+138h] [rbp-C60h]
  struct CSessionTraceFlags *v111; // [rsp+140h] [rbp-C58h]
  struct CSessionTraceFlags *v112; // [rsp+148h] [rbp-C50h]
  __int64 v113; // [rsp+150h] [rbp-C48h]
  struct CSessionTraceFlags *v114; // [rsp+158h] [rbp-C40h]
  struct CSessionTraceFlags *v115; // [rsp+160h] [rbp-C38h]
  struct CSessionTraceFlags *v116; // [rsp+168h] [rbp-C30h]
  int v117; // [rsp+170h] [rbp-C28h]
  struct Worker *v118; // [rsp+178h] [rbp-C20h]
  __int64 v119; // [rsp+180h] [rbp-C18h]
  struct CSessionTraceFlags *v120; // [rsp+188h] [rbp-C10h]
  struct Worker *v121; // [rsp+190h] [rbp-C08h]
  __int64 v122; // [rsp+198h] [rbp-C00h]
  BOOL v123; // [rsp+1A0h] [rbp-BF8h]
  struct IMetadataAccess *v124; // [rsp+1A8h] [rbp-BF0h]
  __int64 v125; // [rsp+1B0h] [rbp-BE8h]
  char *v126; // [rsp+1B8h] [rbp-BE0h]
  int v127; // [rsp+1C0h] [rbp-BD8h]
  unsigned int v128; // [rsp+1C4h] [rbp-BD4h]
  struct _GUID v129; // [rsp+1D0h] [rbp-BC8h] BYREF
  _BYTE v130[16]; // [rsp+1E0h] [rbp-BB8h] BYREF
  __int128 v131; // [rsp+1F0h] [rbp-BA8h] BYREF
  __int64 v132; // [rsp+200h] [rbp-B98h]
  int v133; // [rsp+20Ch] [rbp-B8Ch]
  _BYTE v134[4]; // [rsp+210h] [rbp-B88h] BYREF
  char v135; // [rsp+214h] [rbp-B84h]
  int v136; // [rsp+218h] [rbp-B80h]
  __int16 v137; // [rsp+21Ch] [rbp-B7Ch]
  int v138; // [rsp+220h] [rbp-B78h]
  int v139; // [rsp+224h] [rbp-B74h]
  int v140; // [rsp+228h] [rbp-B70h]
  __int128 v141; // [rsp+230h] [rbp-B68h]
  __int128 v142; // [rsp+240h] [rbp-B58h]
  int v143; // [rsp+250h] [rbp-B48h]
  int v144; // [rsp+254h] [rbp-B44h]
  __int64 v145; // [rsp+258h] [rbp-B40h]
  __int128 v146; // [rsp+260h] [rbp-B38h]
  char v147; // [rsp+270h] [rbp-B28h]
  char v148[344]; // [rsp+278h] [rbp-B20h] BYREF
  __int64 v149; // [rsp+3D0h] [rbp-9C8h]
  GUID v150; // [rsp+3D8h] [rbp-9C0h]
  char v151; // [rsp+3E8h] [rbp-9B0h]
  __int64 v152; // [rsp+3F0h] [rbp-9A8h]
  struct CSessionTraceFlags *v153; // [rsp+3F8h] [rbp-9A0h]
  __int64 *v154; // [rsp+400h] [rbp-998h]
  __int64 *v155; // [rsp+408h] [rbp-990h]
  wchar_t *v156; // [rsp+410h] [rbp-988h]
  const wchar_t *v157; // [rsp+418h] [rbp-980h]
  _QWORD *v158; // [rsp+420h] [rbp-978h]
  __int64 *v159; // [rsp+428h] [rbp-970h]
  __int64 v160; // [rsp+430h] [rbp-968h]
  struct CSessionTraceFlags *v161; // [rsp+438h] [rbp-960h]
  char *v162; // [rsp+440h] [rbp-958h]
  __int64 *v163; // [rsp+448h] [rbp-950h]
  __int64 v164; // [rsp+450h] [rbp-948h]
  char *v165; // [rsp+458h] [rbp-940h]
  __int64 *v166; // [rsp+460h] [rbp-938h]
  __int64 v167; // [rsp+468h] [rbp-930h]
  char *v168; // [rsp+470h] [rbp-928h]
  __int64 *v169; // [rsp+478h] [rbp-920h]
  __int64 v170; // [rsp+480h] [rbp-918h]
  char *v171; // [rsp+488h] [rbp-910h]
  __int64 v172; // [rsp+490h] [rbp-908h]
  __int64 v173; // [rsp+498h] [rbp-900h]
  __int64 v174; // [rsp+4A0h] [rbp-8F8h]
  _QWORD *v175; // [rsp+4A8h] [rbp-8F0h]
  __int64 *v176; // [rsp+4B0h] [rbp-8E8h]
  __int64 v177; // [rsp+4B8h] [rbp-8E0h]
  _QWORD *v178; // [rsp+4C0h] [rbp-8D8h]
  __int64 *v179; // [rsp+4C8h] [rbp-8D0h]
  __int64 v180; // [rsp+4D0h] [rbp-8C8h]
  char *v181; // [rsp+4D8h] [rbp-8C0h]
  __int64 *v182; // [rsp+4E0h] [rbp-8B8h]
  __int64 v183; // [rsp+4E8h] [rbp-8B0h]
  __int64 v184; // [rsp+4F0h] [rbp-8A8h]
  __int64 v185; // [rsp+4F8h] [rbp-8A0h]
  __int64 v186; // [rsp+500h] [rbp-898h]
  __int64 v187; // [rsp+508h] [rbp-890h]
  _QWORD *v188; // [rsp+510h] [rbp-888h]
  __int64 *v189; // [rsp+518h] [rbp-880h]
  __int64 v190; // [rsp+520h] [rbp-878h]
  struct CSessionTraceFlags *v191; // [rsp+528h] [rbp-870h]
  __int64 v192; // [rsp+530h] [rbp-868h]
  __int64 v193; // [rsp+538h] [rbp-860h]
  __int64 v194; // [rsp+540h] [rbp-858h]
  __int64 v195; // [rsp+548h] [rbp-850h]
  __int64 v196; // [rsp+550h] [rbp-848h]
  _QWORD *v197; // [rsp+558h] [rbp-840h]
  __int64 *v198; // [rsp+560h] [rbp-838h]
  __int64 v199; // [rsp+568h] [rbp-830h]
  struct CSessionTraceFlags *v200; // [rsp+570h] [rbp-828h]
  __int64 v201; // [rsp+578h] [rbp-820h]
  _QWORD *v202; // [rsp+580h] [rbp-818h]
  __int64 v203; // [rsp+588h] [rbp-810h]
  struct Worker *v204; // [rsp+590h] [rbp-808h]
  __int64 v205; // [rsp+598h] [rbp-800h]
  __int64 *v206; // [rsp+5A0h] [rbp-7F8h]
  __int64 *v207; // [rsp+5A8h] [rbp-7F0h]
  _QWORD *v208; // [rsp+5B0h] [rbp-7E8h]
  __int64 *v209; // [rsp+5B8h] [rbp-7E0h]
  __int64 v210; // [rsp+5C0h] [rbp-7D8h]
  struct CSessionTraceFlags *v211; // [rsp+5C8h] [rbp-7D0h]
  __int64 v212; // [rsp+5D0h] [rbp-7C8h]
  _QWORD *v213; // [rsp+5D8h] [rbp-7C0h]
  __int64 v214; // [rsp+5E0h] [rbp-7B8h]
  struct Worker *v215; // [rsp+5E8h] [rbp-7B0h]
  _QWORD *v216; // [rsp+5F0h] [rbp-7A8h]
  __int64 v217; // [rsp+5F8h] [rbp-7A0h]
  __int64 v218; // [rsp+600h] [rbp-798h]
  struct IMetadataAccess *v219; // [rsp+608h] [rbp-790h]
  __int64 v220; // [rsp+610h] [rbp-788h]
  __int64 v221; // [rsp+618h] [rbp-780h]
  struct IMetadataAccess *v222; // [rsp+620h] [rbp-778h]
  struct IMetadataAccess *v223; // [rsp+628h] [rbp-770h]
  __int64 v224; // [rsp+630h] [rbp-768h]
  char *v225; // [rsp+638h] [rbp-760h]
  __int64 *v226; // [rsp+640h] [rbp-758h]
  __int64 v227; // [rsp+648h] [rbp-750h]
  char *v228; // [rsp+650h] [rbp-748h]
  __int64 v229; // [rsp+658h] [rbp-740h]
  __int64 v230; // [rsp+660h] [rbp-738h]
  __int64 v231; // [rsp+668h] [rbp-730h]
  _WORD *v232; // [rsp+670h] [rbp-728h]
  unsigned int **v233; // [rsp+678h] [rbp-720h]
  __int64 v234; // [rsp+680h] [rbp-718h]
  _QWORD *v235; // [rsp+688h] [rbp-710h]
  __int64 *v236; // [rsp+690h] [rbp-708h]
  __int64 *v237; // [rsp+698h] [rbp-700h]
  __int64 v238; // [rsp+6A0h] [rbp-6F8h]
  __int64 v239; // [rsp+6A8h] [rbp-6F0h]
  _QWORD *v240; // [rsp+6B0h] [rbp-6E8h]
  __int64 v241; // [rsp+6B8h] [rbp-6E0h]
  __int64 v242; // [rsp+6C0h] [rbp-6D8h]
  __int64 v243; // [rsp+6C8h] [rbp-6D0h]
  __int64 v244; // [rsp+6D0h] [rbp-6C8h]
  _QWORD *v245; // [rsp+6D8h] [rbp-6C0h]
  __int64 *v246; // [rsp+6E0h] [rbp-6B8h]
  __int64 v247; // [rsp+6E8h] [rbp-6B0h]
  _QWORD *v248; // [rsp+6F0h] [rbp-6A8h]
  __int64 v249; // [rsp+6F8h] [rbp-6A0h]
  __int64 v250; // [rsp+700h] [rbp-698h]
  __int64 v251; // [rsp+708h] [rbp-690h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+710h] [rbp-688h]
  __int64 *v253; // [rsp+718h] [rbp-680h]
  _BYTE v254[16]; // [rsp+720h] [rbp-678h] BYREF
  _BYTE v255[16]; // [rsp+730h] [rbp-668h] BYREF
  struct _GUID v256; // [rsp+740h] [rbp-658h] BYREF
  __int64 v257; // [rsp+750h] [rbp-648h]
  struct CSessionTraceFlags *v258; // [rsp+758h] [rbp-640h]
  _QWORD *v259; // [rsp+760h] [rbp-638h]
  __int64 *v260; // [rsp+768h] [rbp-630h]
  _BYTE v261[24]; // [rsp+770h] [rbp-628h] BYREF
  _BYTE v262[24]; // [rsp+788h] [rbp-610h] BYREF
  _BYTE v263[40]; // [rsp+7A0h] [rbp-5F8h] BYREF
  _BYTE v264[40]; // [rsp+7C8h] [rbp-5D0h] BYREF
  _BYTE v265[32]; // [rsp+7F0h] [rbp-5A8h] BYREF
  char v266[8]; // [rsp+810h] [rbp-588h] BYREF
  _WORD v267[4]; // [rsp+818h] [rbp-580h] BYREF
  int v268; // [rsp+820h] [rbp-578h]
  unsigned int **v269; // [rsp+828h] [rbp-570h]
  char *v270; // [rsp+830h] [rbp-568h]
  __int64 v271; // [rsp+838h] [rbp-560h]
  unsigned int *v272; // [rsp+840h] [rbp-558h] BYREF
  int v273; // [rsp+848h] [rbp-550h]
  __int16 v274; // [rsp+84Ch] [rbp-54Ch]
  __int16 v275; // [rsp+84Eh] [rbp-54Ah]
  char v276; // [rsp+850h] [rbp-548h] BYREF
  int v277; // [rsp+A60h] [rbp-338h]
  int v278; // [rsp+A64h] [rbp-334h]
  __int64 v279; // [rsp+A68h] [rbp-330h]
  unsigned int v280; // [rsp+A70h] [rbp-328h] BYREF
  _BYTE v281[320]; // [rsp+A80h] [rbp-318h] BYREF
  _BYTE v282[312]; // [rsp+BC0h] [rbp-1D8h] BYREF
  int v283; // [rsp+CF8h] [rbp-A0h]
  int v284; // [rsp+CFCh] [rbp-9Ch]
  int v285; // [rsp+D1Ch] [rbp-7Ch]
  int v286; // [rsp+D38h] [rbp-60h]
  char v287; // [rsp+D3Ch] [rbp-5Ch]
  char v288; // [rsp+D3Dh] [rbp-5Bh]

  v184 = -2;
  v8 = (int)a4;
  v83 = a4;
  v9 = a3;
  v86 = (__int64)a3;
  v10 = a1;
  v106 = a1;
  v108 = a3;
  v88 = a4;
  v94 = a7;
  v80 = -1;
  memset_0(v282, 0, 0x188u);
  v286 = -1;
  v129 = GUID_NULL;
  v85 = 0;
  v76 = a6;
  v84 = 0;
  v107 = 0;
  v79 = 0;
  try
  {
    v95 = 0;
    v96 = 0;
    v97 = 1;
    v98 = 0;
    AsynchronousDiskPool::AsynchronousDiskPool((AsynchronousDiskPool *)v281, qword_103172088);
    AsynchronousDiskPool::Init((AsynchronousDiskPool *)v281);
    if ( (byte_10317AC62 & 0x20) == 0 )
    {
      v99 = 0;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      v253 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v11 = *v253;
      v257 = v11;
      if ( v11 && (v12 = **(struct CSessionTraceFlags ***)(v11 + 56), (v258 = v12) != 0) )
      {
        v111 = v12;
        v99 = CSessionTraceFlags::CheckSessionTraceInternal(v12, 0x715u);
        if ( v99 )
          goto LABEL_17;
      }
      else
      {
        v111 = 0;
      }
      v110 = dword_10317A9FC;
      if ( (dword_10317A9FC & 0x20) == 0 && (byte_10317AD43 & 1) == 0 )
        goto LABEL_17;
      v76 = 1;
      if ( (byte_10317AC62 & 0x40) != 0 )
        goto LABEL_17;
      v100 = 0;
      v259 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v260 = (__int64 *)(v259[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v13 = *v260;
      v152 = v13;
      if ( v13 && (v14 = **(struct CSessionTraceFlags ***)(v13 + 56), (v153 = v14) != 0) )
      {
        v112 = v14;
        v100 = CSessionTraceFlags::CheckSessionTraceInternal(v14, 0x716u);
        if ( v100 )
          goto LABEL_17;
      }
      else
      {
        v112 = 0;
      }
      _InterlockedIncrement(&dword_1033C1040);
      v84 = 1;
    }
LABEL_17:
    v92 = 0;
    v154 = &v93;
    v155 = &v93;
    v93 = 0;
    v91 = &AutoReadOnlyIMAPhysicalMaster::`vftable';
    if ( a7 && *a7 )
      v15 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a7 + 64LL))(*a7);
    else
      v15 = 0;
    AutoReadOnlyIMA::Init((AutoReadOnlyIMA *)&v91, v9, v8, v15);
    v16 = (struct IMS_DatabaseReg *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v92 + 72LL))(v92);
    v109 = v16;
    v17 = (*(__int64 (__fastcall **)(struct IMS_DatabaseReg *, const wchar_t *, _QWORD))(*(_QWORD *)v16 + 8LL))(
            v16,
            v9,
            (unsigned int)v8);
    v75 = v17;
    if ( !v17 )
      ex_raise(37, 1, 11, 2, 13087, 13030, v8, v9);
    if ( (byte_10317AD43 & 1) == 0 && FSystemDBName(v9, v8) )
    {
      v156 = &word_103185B6E;
      if ( word_103185B6E )
      {
        if ( FSystemDBId(v17, 0x10u) )
          goto LABEL_33;
        goto LABEL_32;
      }
      if ( !dword_1031852C8
        || !FSystemDBId(v17, 0x10u)
        && !FSystemDBId(v17, 0x40u)
        && (v128 = dword_1031C47DC,
            v157 = L"msdb",
            v117 = CompareStringWEnglishNoCase(1u, 0, v9, v8 >> 1, L"msdb", (unsigned __int64)(int)dword_1031C47DC >> 1),
            v117 != 2) )
      {
LABEL_32:
        ex_raise(79, 40, 16, 1);
      }
    }
LABEL_33:
    if ( v76 && !a6 )
    {
      switch ( v17 )
      {
        case 0x7FFCu:
          v18 = *((_QWORD *)v10 + 13);
          break;
        case 0x7FFDu:
          v18 = *((_QWORD *)v10 + 14);
          break;
        case 0x7FFFu:
          v18 = *((_QWORD *)v10 + 11);
          break;
        default:
          if ( v17 > *((_DWORD *)v10 + 19) || !v17 )
          {
            v113 = 0;
            goto LABEL_47;
          }
          v18 = *(_QWORD *)(*((_QWORD *)v10 + 5) + 8LL * (int)(v17 - 1));
          break;
      }
      v113 = v18;
      if ( v18 )
        ex_raise(37, 10, 16, 1);
    }
LABEL_47:
    DBMgr::VerifyNoSnapshotBeforeDropOrDetach(v10, v16, v17, 0);
    (**(void (__fastcall ***)(struct IMS_DatabaseReg *, _QWORD, _BYTE *, _QWORD))v16)(v16, v17, v282, 0);
    if ( v283 && !v284 )
    {
      LODWORD(v71) = 13102;
      ex_raise(37, 6, 16, 1, v71);
    }
    if ( (v287 & 4) != 0 && !a6 && (byte_10317AC62 & 0x10) == 0 )
    {
      v101 = 0;
      v158 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v159 = (__int64 *)(v158[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v19 = *v159;
      v160 = v19;
      if ( v19 && (v20 = **(struct CSessionTraceFlags ***)(v19 + 56), (v161 = v20) != 0) )
      {
        v114 = v20;
        v101 = CSessionTraceFlags::CheckSessionTraceInternal(v20, 0x714u);
        if ( v101 )
          goto LABEL_59;
      }
      else
      {
        v114 = 0;
      }
      ex_raise(37, 7, 16, 1);
    }
LABEL_59:
    if ( v285 )
    {
      LODWORD(v71) = v8;
      ex_raise(37, 52, 16, 2, v71, v9);
    }
    v162 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
    v21 = 8LL * SystemThread_TlsIndex;
    v163 = (__int64 *)(SystemThread_TlsOffset + *(_QWORD *)&v162[v21]);
    v164 = *v163;
    v87 = v164;
    if ( CSessionLockList::IsHeldSingleUserLock(*(CSessionLockList **)(v164 + 88), v75) )
    {
      v165 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
      v166 = (__int64 *)(SystemThread_TlsOffset + *(_QWORD *)&v165[v21]);
      v167 = *v166;
      v87 = v167;
      CSessionLockList::RemoveSingleUserLock(*(CSessionLockList **)(v167 + 88), v75);
    }
    v168 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
    v22 = 8LL * SystemThread_TlsIndex;
    v169 = (__int64 *)(SystemThread_TlsOffset + *(_QWORD *)&v168[v22]);
    v170 = *v169;
    v87 = v170;
    v171 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
    v172 = SystemThread_TlsOffset + *(_QWORD *)&v171[v22];
    v173 = *(_QWORD *)(v172 + 8);
    v174 = *(_QWORD *)(v173 + 104);
    v23 = v75;
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v174 + 40) + 184LL))(
           *(_QWORD *)(v174 + 40),
           v75,
           0) )
    {
      LODWORD(v72) = v8;
      LODWORD(v71) = 13030;
      ex_raise(37, 3, 16, 3, v71, v72, v9);
    }
    v85 = 1;
    NotifyDropDatabase::Enlist(&off_1031D4CE0, v75, 8);
    v90 = v75;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v10 + 28) + 24LL))(*((_QWORD *)v10 + 28), v75, 0);
    if ( v94 )
    {
      if ( *v94 )
        v25 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v94 + 64LL))(*v94);
      else
        v25 = 0;
    }
    else
    {
      v97 = 1;
      v175 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v176 = (__int64 *)(v175[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v177 = *v176;
      v87 = v177;
      *(_QWORD *)&v98 = *(_QWORD *)(v177 + 144);
      v178 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v179 = (__int64 *)(v178[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v180 = *v179;
      v87 = v180;
      v24 = *(_BYTE *)(v180 + 152);
      v123 = v24 != 0;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v98 + 464LL))(v98) )
      {
        if ( v24 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v98 + 488LL))(v98) )
          utassert_fail(
            1u,
            "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
            "automsqlxact.cpp",
            235,
            0);
        (*(void (__fastcall **)(_QWORD, __int64, __int64, int *))(*(_QWORD *)v98 + 232LL))(v98, 2, 1, &v96);
        v97 = 1;
        v95 = 3;
      }
      else
      {
        LOBYTE(v73) = 0;
        (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, _DWORD, _QWORD, bool))(*(_QWORD *)v98 + 8LL))(
          v98,
          L"DetachDB",
          16,
          1,
          2,
          1,
          v73,
          0,
          v24 != 0);
        v95 = 1;
      }
      v25 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v98 + 432LL))(v98);
      v23 = v75;
    }
    v87 = v25;
    if ( !a8 )
    {
      v181 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
      v26 = 8LL * SystemThread_TlsIndex;
      v182 = (__int64 *)(SystemThread_TlsOffset + *(_QWORD *)&v181[v26]);
      v183 = *v182;
      v126 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
      v185 = SystemThread_TlsOffset + *(_QWORD *)&v126[v26];
      v186 = *(_QWORD *)(v185 + 8);
      v187 = *(_QWORD *)(v186 + 104);
      LOBYTE(v73) = 0;
      LOBYTE(v26) = 5;
      v23 = v75;
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, _DWORD, _DWORD))(**(_QWORD **)(v187 + 40)
                                                                                             + 160LL))(
              *(_QWORD *)(v187 + 40),
              v75,
              37,
              v26,
              20000,
              0,
              v73);
      v80 = v27;
      if ( v27 < 0 )
      {
        if ( v27 == -1 )
        {
          LODWORD(v72) = v8;
          LODWORD(v71) = 13030;
          ex_raise(37, 3, 16, 2, v71, v72, v9);
        }
        else
        {
          _mm_lfence();
          LOBYTE(v28) = 29;
          lck_StandardHandler((unsigned int)v27, v28);
          v23 = v75;
        }
      }
    }
    v131 = 0;
    v132 = 0;
    v133 = 0;
    AutoOverrideMsqlXact::InitializeAndOverride((AutoOverrideMsqlXact *)&v131);
    v29 = v109;
    if ( v23 != (*(unsigned int (__fastcall **)(struct IMS_DatabaseReg *, const wchar_t *, _QWORD))(*(_QWORD *)v109 + 8LL))(
                  v109,
                  v9,
                  (unsigned int)v8) )
    {
      LODWORD(v73) = v8;
      LODWORD(v72) = 13030;
      LODWORD(v71) = 13087;
      ex_raise(37, 1, 11, 3, v71, v72, v73, v9);
    }
    DBMgr::VerifyNoSnapshotBeforeDropOrDetach(v10, v29, v23, 0);
    switch ( v23 )
    {
      case 0x7FFCu:
        v31 = *((_QWORD *)v10 + 13);
        break;
      case 0x7FFDu:
        v31 = *((_QWORD *)v10 + 14);
        break;
      case 0x7FFFu:
        v31 = *((_QWORD *)v10 + 11);
        break;
      default:
        if ( v23 > *((_DWORD *)v10 + 19) || !v23 )
        {
          v31 = 0;
          v77 = 0;
          goto LABEL_94;
        }
        v31 = *(_QWORD *)(*((_QWORD *)v10 + 5) + 8LL * (int)(v23 - 1));
        break;
    }
    v77 = v31;
    if ( v31 )
      goto LABEL_110;
LABEL_94:
    if ( v76 || (v288 & 4) == 0 )
      goto LABEL_110;
    v81 = 0;
    if ( CAutoDb::FUse((CAutoDb *)&v81, v23, 0, 1, 0, 0) )
    {
      switch ( v23 )
      {
        case 0x7FFCu:
          v31 = *((_QWORD *)v10 + 13);
          break;
        case 0x7FFDu:
          v31 = *((_QWORD *)v10 + 14);
          break;
        case 0x7FFFu:
          v31 = *((_QWORD *)v10 + 11);
          break;
        default:
          if ( v23 > *((_DWORD *)v10 + 19) || !v23 )
          {
            v31 = 0;
            v77 = 0;
            goto LABEL_108;
          }
          v31 = *(_QWORD *)(*((_QWORD *)v10 + 5) + 8LL * (int)(v23 - 1));
          break;
      }
      v77 = v31;
    }
LABEL_108:
    if ( v81 )
    {
      v81 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
LABEL_110:
    if ( v31 && !a6 )
    {
      if ( v76 )
        utassert_fail(1u, "!safeMode", "dbmgr.cpp", 9963, 0);
      if ( (*(_DWORD *)(v31 + 632) & 0x140) == 0 || (byte_10317AC62 & 0x10) != 0 )
        goto LABEL_123;
      v102 = 0;
      v188 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v189 = (__int64 *)(v188[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v32 = *v189;
      v190 = v32;
      if ( v32 && (v33 = **(struct CSessionTraceFlags ***)(v32 + 56), (v191 = v33) != 0) )
      {
        v115 = v33;
        v102 = CSessionTraceFlags::CheckSessionTraceInternal(v33, 0x714u);
        if ( v102 )
          goto LABEL_122;
      }
      else
      {
        v115 = 0;
      }
      ex_raise(37, 7, 16, 2);
LABEL_122:
      v23 = v75;
      v31 = v77;
LABEL_123:
      v34 = *(_QWORD *)(v31 + 4624);
      v192 = v34;
      v35 = *(_QWORD *)(v34 + 1712) + 784LL;
      v193 = v35;
      if ( *(_DWORD *)v35
        && (*(_QWORD *)(v35 + 4) != *(_QWORD *)&x_AG_DB_IdBad.Data1
         || *(_QWORD *)(v35 + 12) != *(_QWORD *)x_AG_DB_IdBad.Data4)
        || *(_DWORD *)(v31 + 1648) )
      {
        v194 = v34;
        v36 = *(_QWORD *)(v34 + 1712) + 784LL;
        v195 = v36;
        if ( !*(_DWORD *)v36
          || *(_QWORD *)(v36 + 4) == *(_QWORD *)&x_AG_DB_IdBad.Data1
          && *(_QWORD *)(v36 + 12) == *(_QWORD *)x_AG_DB_IdBad.Data4 )
        {
          LODWORD(v71) = v8;
          ex_raise(37, 43, 16, 2, v71, v9);
        }
        else
        {
          LODWORD(v71) = *(_DWORD *)(v31 + 928);
          ex_raise(37, 52, 16, 2, v71, v31 + 936);
        }
      }
      v37 = 0;
      v78 = 0;
      for ( i = 0; ; i = v37 )
      {
        while ( 1 )
        {
          if ( i )
          {
            v9 = (const wchar_t *)v86;
            goto LABEL_147;
          }
          v39 = *(_QWORD *)(v31 + 4624);
          v196 = v39;
          if ( v39 )
            break;
          v78 = ++v37;
          i = v37;
        }
        v127 = dword_103172554;
        if ( !dword_103172554 && (byte_10317AC61 & 4) == 0 )
          break;
LABEL_145:
        v78 = ++v37;
      }
      v103 = 0;
      v197 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v40 = (struct CSessionTraceFlags *)SystemThread_TlsIndex;
      v198 = (__int64 *)(v197[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v41 = *v198;
      v199 = v41;
      if ( v41 && (v40 = **(struct CSessionTraceFlags ***)(v41 + 56), (v200 = v40) != 0) )
      {
        v116 = v40;
        v103 = CSessionTraceFlags::CheckSessionTraceInternal(v40, 0x70Au);
        if ( v103 )
          goto LABEL_144;
      }
      else
      {
        v116 = 0;
      }
      DBMgr::EnqueueDbFileReAcls(v40, *(struct FileMgr **)(v39 + 1696), (struct AsynchronousDiskPool *)v281);
LABEL_144:
      v37 = v78;
      v23 = v75;
      v31 = v77;
      goto LABEL_145;
    }
LABEL_147:
    if ( !dword_103172528 )
    {
      LOWORD(v74) = 0;
      LOBYTE(v72) = 1;
      LOBYTE(v71) = 0;
      LOBYTE(v30) = 1;
      CleanupVersionsFromDb(v23, 0, 0, v30, (_DWORD)v71, (_DWORD)v72, 0, v74, 0, 0);
    }
    if ( !g_SegmentSizeMb )
      RBPEX::NotifyDrop(v23, 0);
    if ( (**(unsigned __int8 (__fastcall ***)(__int64))qword_1031C4710)(qword_1031C4710) )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1031C4710 + 72LL))(qword_1031C4710, v23, 0);
    v43 = a5;
    if ( !a5 && !v76 )
    {
      if ( !v31 )
      {
        v82 = 0;
        if ( CAutoDb::FUse((CAutoDb *)&v82, v23, 0, 1, 0, 0) )
        {
          switch ( v23 )
          {
            case 0x7FFCu:
              v31 = *((_QWORD *)v10 + 13);
              break;
            case 0x7FFDu:
              v31 = *((_QWORD *)v10 + 14);
              break;
            case 0x7FFFu:
              v31 = *((_QWORD *)v10 + 11);
              break;
            default:
              if ( v23 <= *((_DWORD *)v10 + 19) && v23 )
                v31 = *(_QWORD *)(*((_QWORD *)v10 + 5) + 8LL * (int)(v23 - 1));
              else
                v31 = 0;
              break;
          }
        }
        if ( v82 )
        {
          v82 = 0;
          ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
        }
        if ( !v31 )
          goto LABEL_174;
      }
      v134[0] = 0;
      v134[1] = 16;
      v134[2] = 0;
      v134[3] = 0;
      v135 &= 0xF0u;
      v136 = 0;
      v137 = -1;
      v138 = 0;
      v139 = 0;
      v140 = 2;
      v141 = 0;
      v142 = 0;
      v143 = 0xFFFF;
      v144 = 0;
      v145 = 0;
      v146 = 0;
      v147 &= 0xFCu;
      v149 = 0;
      v150 = GUID_NULL;
      v151 = 0;
      memset_0(v148, 0, sizeof(v148));
      v79 = DBTABLE::ShouldSkipFulltextRecovery((DBTABLE *)v31, (struct DatabaseStartupInfo *)v134) == 0;
      DatabaseStartupInfo::~DatabaseStartupInfo((DatabaseStartupInfo *)v134);
    }
    if ( v31 )
      DBTABLE::GetDatabaseBindingId((DBTABLE *)v31, &v129);
    if ( v76 )
    {
LABEL_175:
      LOBYTE(v42) = 1;
      CCache::RemoveByDbid(v23, 11, v42);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v10 + 28) + 48LL))(*((_QWORD *)v10 + 28), v23);
      v201 = 0;
      try
      {
        ExcHandler::ExcHandler((ExcHandler *)v263, 0, 0, 0, hdl_prntbackout, 0);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v10 + 28) + 56LL))(
          *((_QWORD *)v10 + 28),
          v23,
          v92);
        ExcHandler::~ExcHandler((ExcHandler *)v263);
      }
      catch ( SQLError v265 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v254, (const struct SQLError *)v265);
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v254);
        }
        catch ( ShortStackException )
        {
        }
        v10 = v106;
        v9 = v108;
        v83 = v88;
        v43 = a5;
      }
      v202 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v44 = v202[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v203 = v44;
      v45 = *(struct Worker **)(v44 + 256);
      v118 = v45;
      if ( !v45 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v45 = *(struct Worker **)(v44 + 256);
        v118 = v45;
      }
      v204 = v45;
      if ( *((_DWORD *)v45 + 139) )
        ExceptionPostCatchActions(v45);
      if ( v43 || (v46 = v79, v76) )
        v46 = 0;
      v47 = v75;
      (*(void (__fastcall **)(_QWORD, _QWORD, _BOOL8, _QWORD, void (__fastcall ****)(_QWORD)))(**((_QWORD **)v10 + 28)
                                                                                             + 72LL))(
        *((_QWORD *)v10 + 28),
        v75,
        v46,
        0,
        &v107);
      if ( !v76 )
      {
        CloseEncryptionKeysOfDatabaseFromSession(v75);
        QPEvent::DetachDB((QPEvent *)v75, v48);
      }
      v205 = v92;
      if ( v92 )
        (**(void (__fastcall ***)(__int64, __int64))v92)(v92, 1);
      v92 = 0;
      v206 = &v93;
      if ( v93 )
      {
        v119 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 72LL))(v93);
        if ( v119 )
        {
          v207 = &v93;
          if ( v93 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 32LL))(v93);
        }
      }
      else
      {
        v119 = 0;
      }
      if ( (byte_10317B033 & 2) != 0 )
        goto LABEL_197;
      v104 = 0;
      v208 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v209 = (__int64 *)(v208[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v49 = *v209;
      v210 = v49;
      if ( v49 && (v50 = **(struct CSessionTraceFlags ***)(v49 + 56), (v211 = v50) != 0) )
      {
        v120 = v50;
        v104 = CSessionTraceFlags::CheckSessionTraceInternal(v50, 0x2599u);
        if ( v104 )
        {
LABEL_196:
          v47 = v75;
LABEL_197:
          DBMgr::ShutdownDB(v10, v47, 0, 1);
LABEL_198:
          AutoOverrideMsqlXact::~AutoOverrideMsqlXact((AutoOverrideMsqlXact *)&v131);
          if ( g_SegmentSizeMb )
            RBPEX::NotifyDrop(v47, 0);
          v216 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v51 = v216[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v217 = v51;
          v52 = *(_QWORD *)(v51 + 256);
          v122 = v52;
          if ( !v52 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v52 = *(_QWORD *)(v51 + 256);
            v122 = v52;
          }
          v218 = *(_QWORD *)(v52 + 1000);
          v53 = (struct IMetadataAccess *)((__int64 (__fastcall **)(__int64, __int64, const char *, __int64))g_metadataFactory)[5](
                                            v218,
                                            v87,
                                            "sql\\ntdbms\\storeng\\dfs\\manager\\dbmgr.cpp",
                                            10219);
          v219 = v53;
          v124 = v53;
          v54 = (struct IMS_DatabaseReg *)(*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v53 + 72LL))(v53);
          v109 = v54;
          v55 = v75;
          if ( v75 > 2 )
            DBMgr::RemoveAllRecUnitInfoFromMaster(v10, v53, v75);
          (*(void (__fastcall **)(struct IMS_DatabaseReg *, _QWORD))(*(_QWORD *)v54 + 64LL))(v54, v75);
          v89 = 0;
          v56 = (*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v53 + 80LL))(v53);
          v220 = v56;
          (**(void (__fastcall ***)(__int64, _QWORD, _QWORD, _QWORD))v56)(v56, v75, 0, 0);
          while ( 1 )
          {
            v57 = (*(unsigned __int8 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v56 + 16LL))(v56, &v89) == 0;
            v58 = *(_QWORD *)v56;
            if ( v57 )
              break;
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v58 + 48))(v56, v75, v89);
          }
          (*(void (__fastcall **)(__int64))(v58 + 64))(v56);
          v61 = (*(__int64 (__fastcall **)(struct IMetadataAccess *, __int64, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v53 + 56LL))(
                  v53,
                  1,
                  0,
                  0,
                  0,
                  0);
          v221 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v61 + 752LL))(v61);
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v221 + 24LL))(v221, 76, v75);
          if ( !v76 || a6 )
          {
            v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_103179570 + 32LL))(qword_103179570);
            (*(void (__fastcall **)(__int64, struct IMetadataAccess *, _QWORD))(*(_QWORD *)v62 + 16LL))(v62, v53, v75);
          }
          v222 = v53;
          v124 = 0;
          v223 = v53;
          if ( v53 )
            (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v53)(v53, 1);
          if ( v94 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v94 + 32LL))(*v94);
          else
            CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v95, 0);
          AsynchronousDiskPool::WaitUntilDone((AsynchronousDiskPool *)v281);
          if ( a5 )
            v63 = 1;
          else
            v63 = !v79;
          v64 = *((_QWORD *)v10 + 28);
          v256 = v129;
          (*(void (__fastcall **)(__int64, _QWORD, _BOOL8, __int64, struct _GUID *, void (__fastcall ***)(_QWORD)))(*(_QWORD *)v64 + 88LL))(
            v64,
            v75,
            v63,
            1,
            &v256,
            v107);
          if ( !v79 && !a5 )
            ex_callprint(9951, 10, 1, v83, v9);
          if ( !v76 || a6 )
          {
            BadPageList::DropDatabase(v75);
            v65 = -1;
            do
              ++v65;
            while ( v9[v65] );
            v224 = v65;
            CorruptedPageList::RemoveDatabase(v9, v65, 1);
            DBMirroring::CleanupDBMMonitorData(v75);
          }
          if ( !a8 )
          {
            v80 = -1;
            v225 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
            v66 = 8LL * SystemThread_TlsIndex;
            v226 = (__int64 *)(SystemThread_TlsOffset + *(_QWORD *)&v225[v66]);
            v227 = *v226;
            v86 = v227;
            v228 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
            v229 = SystemThread_TlsOffset + *(_QWORD *)&v228[v66];
            v230 = *(_QWORD *)(v229 + 8);
            v231 = *(_QWORD *)(v230 + 104);
            v55 = v75;
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _DWORD))(**(_QWORD **)(v231 + 40) + 168LL))(
              *(_QWORD *)(v231 + 40),
              v75,
              37,
              5,
              0);
          }
          v86 = 0x20000000000003LL;
          if ( (dword_10317F6CC & 0x200000) != 0 )
          {
            v105 = 1;
            v232 = v267;
            v267[0] = 0;
            v267[1] = 1;
            v268 = 0;
            v269 = &v272;
            v270 = &v276;
            v277 = 0;
            v278 = 0;
            v271 = 0;
            v279 = 0;
            v233 = &v272;
            v272 = &v280;
            v273 = 4;
            v274 = 0;
            v275 = 0;
            v280 = v55;
            XeSqlPkg::database_detached::Publish((XeSqlPkg::database_detached *)v266);
          }
          v234 = 0;
          AutoEnlistDrop::~AutoEnlistDrop((AutoEnlistDrop *)&v90);
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v91);
          AsynchronousDiskPool::~AsynchronousDiskPool((AsynchronousDiskPool *)v281);
          if ( v95 )
            CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v95, 0);
          goto LABEL_262;
        }
      }
      else
      {
        v120 = 0;
      }
      if ( !a6 )
      {
        v212 = 0;
        try
        {
          ExcHandler::ExcHandler((ExcHandler *)v264, 0, 0, 0, hdl_prntbackout, 0);
          DBMgr::CleanShutdownDB(v10, v75);
          ExcHandler::~ExcHandler((ExcHandler *)v264);
        }
        catch ( SQLError v261 )
        {
          try
          {
            ExceptionBackout::ExceptionBackout((ExceptionBackout *)v255, (const struct SQLError *)v261);
            DBMgr::ShutdownDB(v106, v75, 0, 1);
            ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v255);
          }
          catch ( ShortStackException )
          {
          }
          v10 = v106;
          v9 = v108;
          v83 = v88;
        }
        v213 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v59 = v213[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v214 = v59;
        v60 = *(struct Worker **)(v59 + 256);
        v121 = v60;
        if ( !v60 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v60 = *(struct Worker **)(v59 + 256);
          v121 = v60;
        }
        v215 = v60;
        if ( *((_DWORD *)v60 + 139) )
          ExceptionPostCatchActions(v60);
        LOWORD(v47) = v75;
        goto LABEL_198;
      }
      goto LABEL_196;
    }
LABEL_174:
    MarkAppDomainsForUnload(v23, 0, 0);
    goto LABEL_175;
  }
  catch ( SQLError v262 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v130, (const struct SQLError *)v262);
      if ( v80 >= 0 )
      {
        v235 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v236 = (__int64 *)(SystemThread_TlsOffset + v235[SystemThread_TlsIndex]);
        v237 = v236;
        v238 = *v236;
        v239 = v238;
        v86 = v238;
        v240 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v241 = SystemThread_TlsOffset + v240[SystemThread_TlsIndex];
        v242 = v241;
        v243 = *(_QWORD *)(v241 + 8);
        v244 = v243;
        v125 = *(_QWORD *)(v243 + 104);
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _DWORD))(**(_QWORD **)(v125 + 40) + 168LL))(
          *(_QWORD *)(v125 + 40),
          v75,
          37,
          5,
          0);
      }
      if ( v84 )
        _InterlockedDecrement(&dword_1033C1040);
      if ( v85 )
      {
        v245 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v246 = (__int64 *)(SystemThread_TlsOffset + v245[SystemThread_TlsIndex]);
        v247 = *v246;
        v86 = v247;
        v248 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v249 = SystemThread_TlsOffset + v248[SystemThread_TlsIndex];
        v250 = *(_QWORD *)(v249 + 8);
        v251 = *(_QWORD *)(v250 + 104);
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v251 + 40) + 192LL))(*(_QWORD *)(v251 + 40), v75);
      }
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v130);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v130);
    }
    catch ( ShortStackException )
    {
    }
  }
LABEL_262:
  v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v68 = *(struct Worker **)(v67 + 256);
  if ( !v68 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v68 = *(struct Worker **)(v67 + 256);
  }
  if ( *((_DWORD *)v68 + 139) )
    ExceptionPostCatchActions(v68);
  if ( v84 )
    _InterlockedDecrement(&dword_1033C1040);
  if ( v85 )
  {
    v69 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset
                                            + 8LL)
                                + 104LL)
                    + 40LL);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v69 + 192LL))(v69, v75);
  }
  if ( v107 )
    (**v107)(v107);
}

```

## disassembly

```asm
0x101708510  push    rbx
0x101708512  push    rsi
0x101708513  push    rdi
0x101708514  push    r12
0x101708516  push    r13
0x101708518  push    r14
0x10170851a  push    r15
0x10170851c  sub     rsp, 0D60h
0x101708523  mov     [rsp+0D98h+var_8A8], 0FFFFFFFFFFFFFFFEh
0x10170852f  mov     rax, cs:__security_cookie
0x101708536  xor     rax, rsp
0x101708539  mov     [rsp+0D98h+var_48], rax
0x101708541  movsxd  r12, r9d
0x101708544  mov     [rsp+0D98h+var_D10], r12d
0x10170854c  mov     r13, r8
0x10170854f  mov     [rsp+0D98h+var_D00], r8
0x101708557  mov     r14, rcx
0x10170855a  mov     [rsp+0D98h+var_C80], rcx
0x101708562  mov     [rsp+0D98h+var_C70], r8
0x10170856a  mov     [rsp+0D98h+var_CF0], r12d
0x101708572  mov     rdi, [rsp+0D98h+arg_30]
0x10170857a  mov     [rsp+0D98h+var_CC8], rdi
0x101708582  mov     [rsp+0D98h+var_D28], 0FFFFFFFFh
0x10170858a  xor     edx, edx; Val
0x10170858c  mov     r8d, 188h; Size
0x101708592  lea     rcx, [rsp+0D98h+var_1D8]; void *
0x10170859a  call    memset_0
0x10170859f  mov     [rsp+0D98h+var_60], 0FFFFFFFFh
0x1017085aa  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1017085b1  movaps  xmmword ptr [rsp+0D98h+var_BC8.Data1], xmm0
0x1017085b9  xor     ebx, ebx
0x1017085bb  mov     [rsp+0D98h+var_D08], ebx
0x1017085c2  mov     eax, [rsp+0D98h+arg_28]
0x1017085c9  mov     [rsp+0D98h+var_D40], eax
0x1017085cd  mov     [rsp+0D98h+var_D0C], ebx
0x1017085d4  mov     [rsp+0D98h+var_D43], 5
0x1017085d9  mov     [rsp+0D98h+var_C78], rbx
0x1017085e1  mov     [rsp+0D98h+var_D2C], ebx
0x1017085e5  mov     [rsp+0D98h+var_CC0], ebx
0x1017085ec  mov     [rsp+0D98h+var_CBC], ebx
0x1017085f3  mov     r15d, 1
0x1017085f9  mov     [rsp+0D98h+var_CB8], r15d
0x101708601  xorps   xmm0, xmm0
0x101708604  movdqu  [rsp+0D98h+var_CB0], xmm0
0x10170860d  mov     rdx, cs:qword_103172088; struct IMemObj *
0x101708614  lea     rcx, [rsp+0D98h+var_318]; this
0x10170861c  call    ??0AsynchronousDiskPool@@QEAA@PEAVIMemObj@@@Z; AsynchronousDiskPool::AsynchronousDiskPool(IMemObj *)
0x101708621  nop
0x101708622  lea     rcx, [rsp+0D98h+var_318]; this
0x10170862a  call    ?Init@AsynchronousDiskPool@@QEAAXXZ; AsynchronousDiskPool::Init(void)
0x10170862f  movzx   eax, cs:byte_10317AC62
0x101708636  shr     al, 5
0x101708639  mov     [rsp+0D98h+var_D24], al
0x10170863d  test    r15b, al
0x101708640  jnz     loc_10170879C
0x101708646  mov     [rsp+0D98h+var_CA0], ebx
0x10170864d  mov     r8, gs:58h
0x101708656  mov     [rsp+0D98h+var_688], r8
0x10170865e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101708665  mov     ecx, [rax]
0x101708667  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10170866e  mov     edx, [rax]
0x101708670  add     rdx, [r8+rcx*8]
0x101708674  mov     [rsp+0D98h+var_680], rdx
0x10170867c  mov     rax, [rdx]
0x10170867f  mov     [rsp+0D98h+var_648], rax
0x101708687  test    rax, rax
0x10170868a  jz      short loc_1017086C4
0x10170868c  mov     rax, [rax+38h]
0x101708690  mov     rcx, [rax]
0x101708693  mov     [rsp+0D98h+var_640], rcx
0x10170869b  test    rcx, rcx
0x10170869e  jz      short loc_1017086C4
0x1017086a0  mov     [rsp+0D98h+var_C58], rcx
0x1017086a8  mov     edx, 715h
0x1017086ad  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1017086b3  mov     [rsp+0D98h+var_CA0], eax
0x1017086ba  test    eax, eax
0x1017086bc  jnz     loc_10170879C
0x1017086c2  jmp     short loc_1017086CC
0x1017086c4  mov     [rsp+0D98h+var_C58], rbx
0x1017086cc  mov     eax, cs:dword_10317A9FC
0x1017086d2  mov     [rsp+0D98h+var_C60], eax
0x1017086d9  test    al, 20h
0x1017086db  jnz     short loc_1017086F0
0x1017086dd  movzx   eax, cs:byte_10317AD43
0x1017086e4  mov     [rsp+0D98h+var_D23], al
0x1017086e8  test    al, 1
0x1017086ea  jz      loc_10170879C
0x1017086f0  mov     [rsp+0D98h+var_D40], r15d
0x1017086f5  movzx   eax, cs:byte_10317AC62
0x1017086fc  shr     al, 6
0x1017086ff  mov     [rsp+0D98h+var_D22], al
0x101708703  test    al, 1
0x101708705  jnz     loc_10170879C
0x10170870b  mov     [rsp+0D98h+var_C9C], ebx
0x101708712  mov     r8, gs:58h
0x10170871b  mov     [rsp+0D98h+var_638], r8
0x101708723  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10170872a  mov     ecx, [rax]
0x10170872c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101708733  mov     edx, [rax]
0x101708735  add     rdx, [r8+rcx*8]
0x101708739  mov     [rsp+0D98h+var_630], rdx
0x101708741  mov     rax, [rdx]
0x101708744  mov     [rsp+0D98h+var_9A8], rax
0x10170874c  test    rax, rax
0x10170874f  jz      short loc_101708785
0x101708751  mov     rax, [rax+38h]
0x101708755  mov     rcx, [rax]
0x101708758  mov     [rsp+0D98h+var_9A0], rcx
0x101708760  test    rcx, rcx
0x101708763  jz      short loc_101708785
0x101708765  mov     [rsp+0D98h+var_C50], rcx
0x10170876d  mov     edx, 716h
0x101708772  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101708778  mov     [rsp+0D98h+var_C9C], eax
0x10170877f  test    eax, eax
0x101708781  jz      short loc_10170878D
0x101708783  jmp     short loc_10170879C
0x101708785  mov     [rsp+0D98h+var_C50], rbx
0x10170878d  lock inc cs:dword_1033C1040
0x101708794  mov     [rsp+0D98h+var_D0C], r15d
0x10170879c  lea     rax, ??_7AutoReadOnlyIMA@@6B@; const AutoReadOnlyIMA::`vftable'
0x1017087a3  mov     [rsp+0D98h+var_CE0], rax
0x1017087ab  mov     [rsp+0D98h+var_CD8], rbx
0x1017087b3  lea     rax, [rsp+0D98h+var_CD0]
0x1017087bb  mov     [rsp+0D98h+var_998], rax
0x1017087c3  lea     rax, [rsp+0D98h+var_CD0]
0x1017087cb  mov     [rsp+0D98h+var_990], rax
0x1017087d3  mov     [rsp+0D98h+var_CD0], rbx
0x1017087db  lea     rax, ??_7AutoReadOnlyIMAPhysicalMaster@@6B@; const AutoReadOnlyIMAPhysicalMaster::`vftable'
0x1017087e2  mov     [rsp+0D98h+var_CE0], rax
0x1017087ea  test    rdi, rdi
0x1017087ed  jz      short loc_1017087FF
0x1017087ef  mov     rcx, [rdi]
0x1017087f2  test    rcx, rcx
0x1017087f5  jz      short loc_1017087FF
0x1017087f7  mov     rax, [rcx]
0x1017087fa  call    qword ptr [rax+40h]
0x1017087fd  jmp     short loc_101708802
0x1017087ff  mov     rax, rbx
0x101708802  mov     r9, rax; struct BaseXact *
0x101708805  mov     r8d, r12d; unsigned int
0x101708808  mov     rdx, r13; wchar_t *
0x10170880b  lea     rcx, [rsp+0D98h+var_CE0]; this
0x101708813  call    ?Init@AutoReadOnlyIMA@@QEAAXPEB_WKPEAVBaseXact@@@Z; AutoReadOnlyIMA::Init(wchar_t const *,ulong,BaseXact *)
0x101708818  mov     rcx, [rsp+0D98h+var_CD8]
0x101708820  mov     rax, [rcx]
0x101708823  call    qword ptr [rax+48h]
0x101708826  mov     rsi, rax
0x101708829  mov     [rsp+0D98h+var_C68], rax
0x101708831  mov     r9, [rax]
0x101708834  mov     r8d, r12d
0x101708837  mov     rdx, r13
0x10170883a  mov     rcx, rax
0x10170883d  call    qword ptr [r9+8]
0x101708841  mov     edi, eax
0x101708843  mov     [rsp+0D98h+var_D48], eax
0x101708847  test    eax, eax
0x101708849  jnz     short loc_101708879
0x10170884b  mov     [rsp+0D98h+var_D60], r13
0x101708850  mov     dword ptr [rsp+0D98h+var_D68], r12d
0x101708855  mov     dword ptr [rsp+0D98h+var_D70], 32E6h
0x10170885d  mov     dword ptr [rsp+0D98h+var_D78], 331Fh
0x101708865  lea     r9d, [rax+2]
0x101708869  lea     r8d, [rax+0Bh]
0x10170886d  mov     edx, r15d
0x101708870  lea     ecx, [rax+25h]
0x101708873  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101708879  movzx   eax, cs:byte_10317AD43
0x101708880  mov     [rsp+0D98h+var_D21], al
0x101708884  test    al, 1
0x101708886  jnz     loc_10170896C
0x10170888c  mov     edx, r12d; unsigned int
0x10170888f  mov     rcx, r13; wchar_t *
0x101708892  call    ?FSystemDBName@@YA_NPEB_WK@Z; FSystemDBName(wchar_t const *,ulong)
0x101708897  test    al, al
0x101708899  jz      loc_10170896C
0x10170889f  mov     [rsp+0D98h+var_D44], 1
0x1017088a4  lea     rax, word_103185B6E
0x1017088ab  mov     [rsp+0D98h+var_988], rax
0x1017088b3  cmp     cs:word_103185B6E, 0
0x1017088bb  jz      short loc_1017088DB
0x1017088bd  mov     edx, 10h; unsigned int
0x1017088c2  mov     ecx, edi; unsigned int
0x1017088c4  call    ?FSystemDBId@@YA_NKI@Z; FSystemDBId(ulong,uint)
0x1017088c9  test    al, al
0x1017088cb  jz      loc_101708957
0x1017088d1  mov     [rsp+0D98h+var_D44], 0
0x1017088d6  jmp     loc_10170896C
0x1017088db  cmp     cs:dword_1031852C8, 0
0x1017088e2  jz      short loc_101708957
0x1017088e4  mov     edx, 10h; unsigned int
0x1017088e9  mov     ecx, edi; unsigned int
0x1017088eb  call    ?FSystemDBId@@YA_NKI@Z; FSystemDBId(ulong,uint)
0x1017088f0  test    al, al
0x1017088f2  jnz     short loc_101708950
0x1017088f4  mov     edx, 40h ; '@'; unsigned int
0x1017088f9  mov     ecx, edi; unsigned int
0x1017088fb  call    ?FSystemDBId@@YA_NKI@Z; FSystemDBId(ulong,uint)
0x101708900  test    al, al
0x101708902  jnz     short loc_101708950
0x101708904  movsxd  rax, cs:dword_1031C47DC
0x10170890b  mov     [rsp+0D98h+var_BD4], eax
0x101708912  mov     rdx, cs:off_10281DB98; "msdb"
0x101708919  mov     [rsp+0D98h+var_980], rdx
0x101708921  mov     rcx, rax
0x101708924  shr     rcx, 1
0x101708927  mov     r9, r12
0x10170892a  shr     r9, 1
0x10170892d  mov     dword ptr [rsp+0D98h+var_D70], ecx
0x101708931  mov     [rsp+0D98h+var_D78], rdx
0x101708936  mov     r8, r13
0x101708939  xor     edx, edx
0x10170893b  mov     ecx, r15d
0x10170893e  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x101708944  mov     [rsp+0D98h+var_C28], eax
0x10170894b  cmp     eax, 2
0x10170894e  jnz     short loc_101708957
0x101708950  mov     [rsp+0D98h+var_D44], 0
0x101708955  jmp     short loc_10170896C
0x101708957  mov     r9d, r15d
0x10170895a  mov     edx, 28h ; '('
0x10170895f  lea     ecx, [rdx+27h]
0x101708962  lea     r8d, [rdx-18h]
0x101708966  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10170896c  cmp     [rsp+0D98h+var_D40], 0
0x101708971  jz      short loc_1017089E6
0x101708973  cmp     [rsp+0D98h+arg_28], 0
0x10170897b  jnz     short loc_1017089E6
0x10170897d  mov     eax, edi
0x10170897f  sub     eax, 7FFCh
0x101708984  jz      short loc_1017089C0
0x101708986  sub     eax, 1
0x101708989  jz      short loc_1017089BA
0x10170898b  cmp     eax, 2
0x10170898e  jz      short loc_1017089B4
0x101708990  cmp     edi, [r14+4Ch]
0x101708994  ja      short loc_1017089AA
0x101708996  test    edi, edi
0x101708998  jz      short loc_1017089AA
0x10170899a  lea     eax, [rdi-1]
0x10170899d  movsxd  rcx, eax
0x1017089a0  mov     rax, [r14+28h]
0x1017089a4  mov     rdx, [rax+rcx*8]
0x1017089a8  jmp     short loc_1017089C4
0x1017089aa  mov     [rsp+0D98h+var_C48], rbx
0x1017089b2  jmp     short loc_1017089E6
0x1017089b4  mov     rdx, [r14+58h]
0x1017089b8  jmp     short loc_1017089C4
0x1017089ba  mov     rdx, [r14+70h]
0x1017089be  jmp     short loc_1017089C4
0x1017089c0  mov     rdx, [r14+68h]
0x1017089c4  mov     [rsp+0D98h+var_C48], rdx
0x1017089cc  test    rdx, rdx
0x1017089cf  jz      short loc_1017089E6
0x1017089d1  mov     r9d, r15d
0x1017089d4  mov     edx, 0Ah
0x1017089d9  lea     ecx, [rdx+1Bh]
0x1017089dc  lea     r8d, [rdx+6]
0x1017089e0  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1017089e6  xor     r9d, r9d; int
0x1017089e9  mov     r8d, edi; unsigned int
0x1017089ec  mov     rdx, rsi; struct IMS_DatabaseReg *
0x1017089ef  mov     rcx, r14; this
0x1017089f2  call    ?VerifyNoSnapshotBeforeDropOrDetach@DBMgr@@QEAAXPEAVIMS_DatabaseReg@@KH@Z; DBMgr::VerifyNoSnapshotBeforeDropOrDetach(IMS_DatabaseReg *,ulong,int)
0x1017089f7  mov     rax, [rsi]
0x1017089fa  xor     r9d, r9d
0x1017089fd  lea     r8, [rsp+0D98h+var_1D8]
0x101708a05  mov     edx, edi
0x101708a07  mov     rcx, rsi
0x101708a0a  call    qword ptr [rax]
0x101708a0c  cmp     [rsp+0D98h+var_A0], 0
0x101708a14  jz      short loc_101708A3D
0x101708a16  cmp     [rsp+0D98h+var_9C], 0
0x101708a1e  jnz     short loc_101708A3D
0x101708a20  mov     dword ptr [rsp+0D98h+var_D78], 332Eh
0x101708a28  mov     r9d, r15d
0x101708a2b  mov     edx, 6
0x101708a30  lea     ecx, [rdx+1Fh]
0x101708a33  lea     r8d, [rdx+0Ah]
0x101708a37  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101708a3d  test    [rsp+0D98h+var_5C], 4
0x101708a45  jz      loc_101708B06
0x101708a4b  cmp     [rsp+0D98h+arg_28], 0
0x101708a53  jnz     loc_101708B06
0x101708a59  movzx   eax, cs:byte_10317AC62
0x101708a60  shr     al, 4
0x101708a63  mov     [rsp+0D98h+var_D20], al
0x101708a67  test    al, 1
0x101708a69  jnz     loc_101708B06
0x101708a6f  mov     [rsp+0D98h+var_C98], ebx
0x101708a76  mov     r8, gs:58h
0x101708a7f  mov     [rsp+0D98h+var_978], r8
0x101708a87  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101708a8e  mov     ecx, [rax]
0x101708a90  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101708a97  mov     edx, [rax]
0x101708a99  add     rdx, [r8+rcx*8]
  ... truncated ...
```
