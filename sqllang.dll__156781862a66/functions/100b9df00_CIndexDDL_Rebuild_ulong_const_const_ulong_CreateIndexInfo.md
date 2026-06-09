# CIndexDDL::Rebuild(ulong const * const,ulong,CreateIndexInfo &)

- ea: `0x100b9df00`
- end: `0x100b9fb0e`
- name: `?Rebuild@CIndexDDL@@QEAAXQEBKKAEAVCreateIndexInfo@@@Z`
- size: `7182`
- prototype: `void __fastcall(CIndexDDL *__hidden this, const unsigned int *const, unsigned int, struct CreateIndexInfo *)`
- caller_count: `6`
- callee_count: `36`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1008aef10`
- `0x100b67020`
- `0x100b82b60`
- `0x100b997c0`
- `0x100ba3dc0`
- `0x101793df0`

## callees

- `0x100401070`
- `0x1004131b0`
- `0x100444f60`
- `0x10045a980`
- `0x10049b130`
- `0x10049b2f0`
- `0x10066ed40`
- `0x10079b5f0`
- `0x100b78cf0`
- `0x100b8ba20`
- `0x100b8c290`
- `0x100b8d560`
- `0x100b919d0`
- `0x100b922f0`
- `0x100b92f60`
- `0x100b933b0`
- `0x100b93550`
- `0x100b9b5e0`
- `0x100b9b840`
- `0x100b9df00`
- `0x100b9fb20`
- `0x100ba00d0`
- `0x100ba09d0`
- `0x100ba0ff0`
- `0x100ba1160`
- `0x100ba16c0`
- `0x100ba7d40`
- `0x100ba8070`
- `0x100bacee0`
- `0x100baece0`
- `0x100baf090`
- `0x100bcb420`
- `0x100ccf600`
- `0x1011c2c90`
- `0x1012ea990`
- `0x101e88ac0`

## import_xrefs

- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x100b9e8b9`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x100b9f327`
- `sqldk!?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA` at `0x100b9e803`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100b9f4ce`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100b9f74a`
- `sqldk!?GetDeadlockPriority@SOS_Task@@QEBA?AW4TASK_DEADLOCK_PRIORITY@1@XZ` at `0x100b9f0f6`
- `sqldk!?GetDeadlockPriority@SOS_Task@@QEBA?AW4TASK_DEADLOCK_PRIORITY@1@XZ` at `0x100b9f0f6`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x100b9f1ae`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x100b9f1ae`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100b9e0ce`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100b9f686`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100b9e0ce`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100b9f686`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9e2c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9e348`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9e42b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9e7bd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9eaba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9eb6d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9ec04`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9ed5c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9eeb5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9e2c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9e348`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9e42b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9e7bd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9eaba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9eb6d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9ec04`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9ed5c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b9eeb5`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e08a`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e0fb`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e43a`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e47d`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e4d0`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e5cd`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e610`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e663`
- `sqldk!SystemThread_TlsIndex` at `0x100b9e873`
- `sqldk!SystemThread_TlsIndex` at `0x100b9ed86`
- `sqldk!SystemThread_TlsIndex` at `0x100b9f0c0`
- `sqldk!SystemThread_TlsIndex` at `0x100b9f175`
- `sqldk!SystemThread_TlsIndex` at `0x100b9f223`
- `sqldk!SystemThread_TlsIndex` at `0x100b9f268`
- `sqldk!SystemThread_TlsIndex` at `0x100b9f2e1`
- `sqldk!SystemThread_TlsIndex` at `0x100b9f5a5`
- `sqldk!SystemThread_TlsIndex` at `0x100b9f619`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e093`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e10c`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e443`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e486`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e4d9`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e5d6`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e619`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e66c`
- `sqldk!SystemThread_TlsOffset` at `0x100b9e87c`
- `sqldk!SystemThread_TlsOffset` at `0x100b9ed97`
- `sqldk!SystemThread_TlsOffset` at `0x100b9f0c9`
- `sqldk!SystemThread_TlsOffset` at `0x100b9f17e`
- `sqldk!SystemThread_TlsOffset` at `0x100b9f22c`
- `sqldk!SystemThread_TlsOffset` at `0x100b9f271`
- `sqldk!SystemThread_TlsOffset` at `0x100b9f2ea`
- `sqldk!SystemThread_TlsOffset` at `0x100b9f5b6`
- `sqldk!SystemThread_TlsOffset` at `0x100b9f622`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9f585`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9f864`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9f8bb`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9f924`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9fa61`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9fa7f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9fadd`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9f585`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9f864`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9f8bb`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9f924`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9fa61`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9fa7f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b9fadd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e467`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e4ba`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e5fa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e64d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e895`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9f0e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9f197`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9f303`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e467`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e4ba`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e5fa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e64d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9e895`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9f0e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9f197`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b9f303`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b9fa53`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b9fa71`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b9fa53`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b9fa71`
- `sqlmin!GetXdbServerGlobals` at `0x100b9e073`
- `sqlmin!GetXdbServerGlobals` at `0x100b9e073`

## string_xrefs

- `0x100b9f673`: `Sql\Ntdbms\include\common\stdarray.inl`
- `0x100b9e0c5`: `pFidoTempList`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CIndexDDL::Rebuild(
        CIndexDDL *this,
        const unsigned int *a2,
        unsigned int a3,
        struct CreateIndexInfo *a4)
{
  unsigned int v5; // r14d
  unsigned int v8; // eax
  const unsigned int *v9; // rcx
  char *ThreadLocalStoragePointer; // rdx
  bool v11; // bl
  CFidoTempObjectList *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdi
  __int64 v15; // rax
  int v16; // eax
  struct TmpObject *v17; // rax
  void **v18; // rdi
  void **v19; // rbx
  bool v20; // r12
  struct BaseXact *v21; // rax
  __int64 v22; // r15
  __int64 v23; // r14
  unsigned int v24; // eax
  __int64 v25; // rax
  struct IMEDDataSpace *v26; // r14
  int v27; // eax
  __int64 (__fastcall **v28)(__int64); // rdx
  __int64 (__fastcall ***v29)(_QWORD); // rax
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // eax
  __int64 (__fastcall **v33)(__int64); // rdx
  int v34; // ebx
  __int64 (__fastcall ***v35)(_QWORD); // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned int v39; // r8d
  int v40; // eax
  __int64 (__fastcall **v41)(__int64); // rdx
  int v42; // ebx
  __int64 (__fastcall ***v43)(_QWORD); // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r9
  int v48; // eax
  __int64 v49; // rbx
  __int64 v50; // r8
  struct CDataCompInfoRunTime *DataCompInfoRunTime; // rax
  bool v52; // bl
  const unsigned int *v53; // r12
  int v54; // r15d
  __int64 v55; // rax
  __int64 v56; // rbx
  __int64 v57; // r8
  struct CXmlCompInfoRunTime *XmlCompInfoRunTime; // rax
  __int64 v59; // rax
  char v60; // al
  unsigned int v61; // r8d
  const unsigned int *v62; // r14
  bool v63; // dl
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rdi
  __int64 v67; // rdi
  __int64 v68; // rbx
  __int64 v69; // rcx
  char v70; // al
  char v71; // di
  struct IMEDRelation *v72; // rcx
  __int64 v73; // rdi
  const wchar_t **v74; // rbx
  __int64 v75; // rax
  bool v76; // dl
  unsigned int v77; // ebx
  struct IMEDIndex *v78; // rax
  __int64 v79; // rax
  __int64 v80; // rbx
  int v81; // eax
  bool v82; // r15
  bool v83; // r14
  bool v84; // di
  __int64 i; // rdi
  _QWORD *v86; // rbx
  bool v87; // r14
  char v88; // al
  __int64 v89; // rax
  __int64 v90; // r9
  __int64 *v91; // rcx
  __int64 v92; // r8
  struct IMEDIndex *v93; // r14
  char v94; // al
  _QWORD *v95; // rbx
  bool v96; // bl
  __int64 v97; // r8
  bool v98; // zf
  __int64 (__fastcall *v99)(__int64 *, _QWORD); // rax
  char v100; // al
  __int64 v101; // rdi
  _QWORD *v102; // rbx
  __int64 v103; // rcx
  __int64 v104; // rax
  struct IMEDDataSpace *v105; // r8
  char v106; // al
  unsigned int v107; // edi
  const unsigned int *v108; // r14
  int v109; // r15d
  struct IMEDIndex *v110; // rbx
  __int64 v111; // rax
  int v112; // eax
  char v113; // cl
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rbx
  __int64 v117; // rcx
  unsigned int DeadlockPriority; // eax
  __int64 v119; // rbx
  __int64 v120; // rcx
  __int64 v121; // rbx
  struct BaseXact *v122; // rdi
  __int64 v123; // r8
  __int64 v124; // rbx
  __int64 v125; // rcx
  __int64 v126; // rdi
  __int64 v127; // rbx
  __int64 v128; // rcx
  __int64 v129; // rdi
  unsigned int v130; // eax
  __int64 *v131; // r12
  __int64 v132; // rax
  __int64 v133; // rdi
  unsigned int v134; // eax
  __int64 v135; // r8
  __int64 v136; // rax
  __int64 v137; // r15
  unsigned int j; // edi
  __int64 v139; // rdx
  unsigned int k; // r14d
  __int64 v141; // rdx
  __int64 v142; // rdi
  __int64 v143; // rax
  unsigned int m; // edi
  __int64 v145; // rdx
  __int64 v146; // rdi
  unsigned int v147; // eax
  __int64 v148; // rax
  __int64 v149; // r14
  __int64 *v150; // r15
  __int64 v151; // r12
  __int64 v152; // rdi
  unsigned int v153; // eax
  __int64 v154; // rdi
  __int64 v155; // r14
  void *v156; // rcx
  __int64 v157; // r8
  struct CIndexDDL *v158; // r14
  __int64 v159; // rcx
  __int64 v160; // rbx
  unsigned int v161; // edi
  unsigned int v162; // eax
  unsigned int v163; // edx
  unsigned int n; // edi
  unsigned __int16 v165; // ax
  char v166; // r8
  __int64 v167; // rax
  __int64 v168; // r9
  __int64 *v169; // r14
  __int64 v170; // rax
  __int64 *v171; // rcx
  __int64 *v172; // rdi
  _QWORD *v173; // rax
  __int64 *v174; // r8
  __int64 *v175; // rcx
  __int64 *v176; // rdi
  __int64 v177; // rax
  __int64 *v178; // r14
  __int64 v179; // rax
  __int64 *v180; // rcx
  __int64 *v181; // rdi
  _QWORD *v182; // rax
  __int64 v183; // rax
  __int64 v184; // rbx
  __int64 v185; // r15
  __int64 v186; // r14
  unsigned int v187; // edi
  _QWORD *v188; // rbx
  __int64 v189; // rax
  __int64 *v190; // rcx
  __int64 *v191; // rdx
  __int64 *v192; // rbx
  __int64 v193; // rax
  wchar_t *v194; // [rsp+20h] [rbp-E0h]
  int v195; // [rsp+20h] [rbp-E0h]
  int v196; // [rsp+20h] [rbp-E0h]
  unsigned int v197[2]; // [rsp+28h] [rbp-D8h]
  int v198; // [rsp+28h] [rbp-D8h]
  unsigned int v199[2]; // [rsp+30h] [rbp-D0h]
  wchar_t *v200; // [rsp+38h] [rbp-C8h]
  char v201; // [rsp+50h] [rbp-B0h]
  char v202; // [rsp+51h] [rbp-AFh]
  bool v203; // [rsp+52h] [rbp-AEh]
  char v204; // [rsp+53h] [rbp-ADh]
  bool v205; // [rsp+54h] [rbp-ACh]
  int v206; // [rsp+58h] [rbp-A8h]
  bool v207; // [rsp+5Ch] [rbp-A4h]
  bool v210; // [rsp+6Ch] [rbp-94h]
  __int64 v211; // [rsp+70h] [rbp-90h] BYREF
  void **v212; // [rsp+78h] [rbp-88h]
  void **v213; // [rsp+80h] [rbp-80h]
  int v214; // [rsp+88h] [rbp-78h]
  __int64 v215; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v216; // [rsp+98h] [rbp-68h]
  __int64 v217; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v218; // [rsp+A8h] [rbp-58h]
  __int64 v219; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v220; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v221; // [rsp+C0h] [rbp-40h] BYREF
  int v222; // [rsp+C8h] [rbp-38h]
  __int64 v223; // [rsp+CCh] [rbp-34h]
  int v224; // [rsp+D4h] [rbp-2Ch]
  int v225; // [rsp+D8h] [rbp-28h]
  __int64 v226; // [rsp+DCh] [rbp-24h]
  struct IMetadataAccess *v227; // [rsp+E8h] [rbp-18h]
  __int64 v228; // [rsp+F0h] [rbp-10h]
  void (__fastcall ***v229)(_QWORD, __int64); // [rsp+F8h] [rbp-8h]
  struct BaseXact *v230; // [rsp+100h] [rbp+0h]
  __int64 v231; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v232[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v233; // [rsp+120h] [rbp+20h] BYREF
  int v234; // [rsp+128h] [rbp+28h]
  __int64 v235; // [rsp+12Ch] [rbp+2Ch]
  int v236; // [rsp+134h] [rbp+34h]
  int v237; // [rsp+138h] [rbp+38h]
  __int64 v238; // [rsp+13Ch] [rbp+3Ch]
  __int64 v239; // [rsp+148h] [rbp+48h] BYREF
  int v240; // [rsp+150h] [rbp+50h]
  __int64 v241; // [rsp+154h] [rbp+54h]
  int v242; // [rsp+15Ch] [rbp+5Ch]
  int v243; // [rsp+160h] [rbp+60h]
  __int64 v244; // [rsp+164h] [rbp+64h]
  __int64 v245; // [rsp+170h] [rbp+70h]
  char v246[24]; // [rsp+178h] [rbp+78h] BYREF
  _WORD *v247; // [rsp+190h] [rbp+90h]
  int v248; // [rsp+1A4h] [rbp+A4h]
  _BYTE v249[48]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v250[48]; // [rsp+1D8h] [rbp+D8h] BYREF

  v245 = -2;
  v5 = a3;
  v221 = 0;
  v223 = 0;
  v224 = 0;
  v226 = 1;
  v225 = -1;
  v222 = -2;
  v218 = &v217;
  v217 = (__int64)&v217;
  v229 = 0;
  if ( (*((_BYTE *)this + 171) & 1) != 0 && (*(_BYTE *)a4 & 0x20) != 0 && (*((_BYTE *)a4 + 24) & 8) != 0 )
    v229 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
  if ( !*((_DWORD *)this + 204) )
    *((_DWORD *)this + 204) = 3;
  v201 = 0;
  v206 = -1;
  v202 = 0;
  v214 = -1;
  v207 = 0;
  v204 = 0;
  v205 = 0;
  v210 = 0;
  v8 = 0;
  if ( a3 )
  {
    v9 = a2;
    while ( *v9 )
    {
      if ( *v9 == 1 )
      {
        v201 = 1;
        v206 = v8;
        goto LABEL_15;
      }
      ++v8;
      ++v9;
      if ( v8 >= a3 )
        goto LABEL_15;
    }
    v202 = 1;
    v214 = v8;
  }
LABEL_15:
  WParseName::Parse((WParseName *)v246, *((const wchar_t **)this + 18), *((_DWORD *)this + 38));
  if ( 2 * v248 && *v247 == 35 && (2 * v248 == 2 || v247[1] != 35) )
  {
    v11 = 0;
    if ( *(_BYTE *)(GetXdbServerGlobals(v247, ThreadLocalStoragePointer) + 12004) )
    {
      v12 = *(CFidoTempObjectList **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                              + SystemThread_TlsIndex)
                                                            + SystemThread_TlsOffset)
                                                + 72LL)
                                    + 432LL);
      if ( v12 )
        v11 = CFidoTempObjectList::LookupFidoTempByName(v12, *((const wchar_t **)this + 18), *((_DWORD *)this + 38)) != 0;
      else
        utassert_fail(1u, "pFidoTempList", "indcreat.cpp", 18781, 0);
    }
    ThreadLocalStoragePointer = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
    v13 = 8LL * SystemThread_TlsIndex;
    v14 = *(_QWORD *)(*(_QWORD *)&ThreadLocalStoragePointer[v13] + SystemThread_TlsOffset);
    if ( !v11 )
    {
      if ( *(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v13)) )
      {
        if ( *(_BYTE *)(v14 + 153) )
        {
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                             + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                         + v13))
                                                 + 160LL)
                                     + 8LL)
                         + 445LL)
              & 0x20) != 0 )
          {
            v15 = (***((__int64 (__fastcall ****)(_QWORD))this + 2))(*((_QWORD *)this + 2));
            v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
            v17 = CScopedTmpObjectList::PLocalTmpTab((CScopedTmpObjectList *)(*(_QWORD *)(v14 + 128) + 168LL), v16);
            if ( v17 )
              *((_BYTE *)v17 + 33) = 0;
          }
        }
      }
    }
  }
  if ( (*((_BYTE *)this + 160) & 0x40) != 0 )
    CIndexDDL::CheckLockForOnlineBuild(this);
  LOBYTE(ThreadLocalStoragePointer) = 1;
  CIndexDDL::LockBuildIndexRes(this, ThreadLocalStoragePointer, 0, *((_BYTE *)this + 171) & 1);
  v18 = 0;
  v212 = 0;
  v19 = 0;
  v213 = 0;
  v20 = (*(_QWORD *)a4 & 0x200000LL) != 0;
  v21 = (struct BaseXact *)(*(_QWORD *)a4 >> 25);
  LOBYTE(v21) = (*(_QWORD *)a4 & 0x2000000LL) != 0;
  v230 = v21;
  if ( !*((_DWORD *)this + 49) && !v20 && !(_BYTE)v21 )
  {
    v54 = v206;
    goto LABEL_93;
  }
  v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 232LL))(*((_QWORD *)this + 2), *a2);
  v23 = **((_QWORD **)this + 3);
  v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 224LL))(v22);
  v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(v23 + 680))(*((_QWORD *)this + 3), v24, 1);
  v26 = (struct IMEDDataSpace *)v25;
  if ( *((_DWORD *)this + 49) )
  {
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 40LL))(v25) )
    {
      v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      v28 = *(__int64 (__fastcall ***)(__int64))v22;
      if ( v27 )
      {
        LODWORD(v219) = 13028;
        v31 = v28[3](v22);
      }
      else
      {
        LODWORD(v219) = 13029;
        v29 = (__int64 (__fastcall ***)(_QWORD))(*v28)(v22);
        v30 = (**v29)(v29);
        v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30);
      }
      LODWORD(v194) = 13088;
      ex_raise(77, 29, 16, 1, v194, v219, v219, *(_DWORD *)(v31 + 8), *(_QWORD *)v31);
    }
    if ( *((_DWORD *)this + 49) > (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v22 + 240LL))(v22) )
    {
      _mm_lfence();
      v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      v33 = *(__int64 (__fastcall ***)(__int64))v22;
      if ( v32 )
      {
        v34 = 13028;
        v37 = v33[3](v22);
      }
      else
      {
        v34 = 13029;
        v35 = (__int64 (__fastcall ***)(_QWORD))(*v33)(v22);
        v36 = (**v35)(v35);
        v37 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 40LL))(v36);
      }
      LODWORD(v200) = *(_DWORD *)(v37 + 8);
      v199[0] = v34;
      v197[0] = *((_DWORD *)this + 49);
      LODWORD(v194) = v34;
      ex_raise(77, 30, 16, 1, v194, *(_QWORD *)v197, *(_QWORD *)v199, v200, *(_QWORD *)v37);
      v18 = v212;
      v19 = v213;
    }
  }
  if ( !v20 )
  {
    v54 = v206;
    v53 = a2;
    goto LABEL_77;
  }
  if ( *((_QWORD *)a4 + 248) )
    v26 = (struct IMEDDataSpace *)*((_QWORD *)a4 + 248);
  if ( FTableHasSparseOrColSetColumns(*((struct IMEDRelation **)this + 2)) )
  {
    v38 = *((_QWORD *)a4 + 8);
    if ( v38 )
    {
      v39 = *(_DWORD *)(v38 + 4);
      if ( v39 )
      {
        v46 = 0;
        v47 = *(_QWORD *)(v38 + 8);
        while ( 1 )
        {
          v48 = *(_DWORD *)(v47 + 24 * v46);
          if ( v48 )
          {
            if ( (unsigned int)(v48 - 3) > 1 )
              break;
          }
          v46 = (unsigned int)(v46 + 1);
          if ( (unsigned int)v46 >= v39 )
            goto LABEL_61;
        }
      }
      else if ( !*(_DWORD *)v38 )
      {
        goto LABEL_61;
      }
      v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      v41 = *(__int64 (__fastcall ***)(__int64))v22;
      if ( v40 )
      {
        v42 = 13028;
        v45 = v41[3](v22);
      }
      else
      {
        v42 = 13029;
        v43 = (__int64 (__fastcall ***)(_QWORD))(*v41)(v22);
        v44 = (**v43)(v43);
        v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 40LL))(v44);
      }
      v197[0] = *(_DWORD *)(v45 + 8);
      LODWORD(v194) = v42;
      ex_raise(106, 22, 16, 2, v194, *(_QWORD *)v197, *(_QWORD *)v45);
    }
  }
LABEL_61:
  v49 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v50 = *(_QWORD *)(v49 + 256);
  if ( (*((_BYTE *)this + 160) & 2) != 0 )
  {
    if ( !v50 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v50 = *(_QWORD *)(v49 + 256);
    }
    DataCompInfoRunTime = CIndexOptionInfo::GetDataCompInfoRunTime(
                            a4,
                            *(const struct CCompExecCtxtStmt **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + SystemThread_TlsIndex)
                                                               + SystemThread_TlsOffset),
                            *(struct IMemObj **)(v50 + 1000),
                            0,
                            v26,
                            0x3320u,
                            0x32E5u,
                            *((const wchar_t **)this + 18),
                            *((_DWORD *)this + 38));
  }
  else
  {
    if ( !v50 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v50 = *(_QWORD *)(v49 + 256);
    }
    DataCompInfoRunTime = CIndexOptionInfo::GetDataCompInfoRunTime(
                            a4,
                            *(const struct CCompExecCtxtStmt **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + SystemThread_TlsIndex)
                                                               + SystemThread_TlsOffset),
                            *(struct IMemObj **)(v50 + 1000),
                            0,
                            v26,
                            0x3320u,
                            0x32E4u,
                            (const wchar_t *)a4 + 48,
                            *((_DWORD *)a4 + 88));
  }
  v212 = (void **)DataCompInfoRunTime;
  v18 = (void **)DataCompInfoRunTime;
  *((_QWORD *)this + 26) = DataCompInfoRunTime;
  v52 = 0;
  v53 = a2;
  if ( v201 )
  {
    v54 = v206;
    v55 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 232LL))(*((_QWORD *)this + 2), a2[v206]);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 40LL))(v55, &v221);
    if ( (v221 & 0x200000) != 0 )
    {
LABEL_74:
      *((_BYTE *)this + 224) &= ~2u;
      *((_BYTE *)this + 224) |= 2 * v52;
      goto LABEL_75;
    }
  }
  else
  {
    v54 = v206;
  }
  if ( (*(_DWORD *)a4 & 0x200000) != 0 )
  {
    v52 = (*((_BYTE *)a4 + 25) & 8) != 0;
    goto LABEL_74;
  }
LABEL_75:
  v19 = v213;
LABEL_77:
  if ( (_BYTE)v230 )
  {
    if ( *((_QWORD *)a4 + 248) )
      v26 = (struct IMEDDataSpace *)*((_QWORD *)a4 + 248);
    v56 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v57 = *(_QWORD *)(v56 + 256);
    if ( (*((_BYTE *)this + 160) & 2) != 0 )
    {
      if ( !v57 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v57 = *(_QWORD *)(v56 + 256);
      }
      XmlCompInfoRunTime = CIndexOptionInfo::GetXmlCompInfoRunTime(
                             a4,
                             *(const struct CCompExecCtxtStmt **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + SystemThread_TlsIndex)
                                                                + SystemThread_TlsOffset),
                             *(struct IMemObj **)(v57 + 1000),
                             0,
                             v26,
                             0x3320u,
                             0x32E5u,
                             *((const wchar_t **)this + 18),
                             *((_DWORD *)this + 38));
    }
    else
    {
      if ( !v57 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v57 = *(_QWORD *)(v56 + 256);
      }
      XmlCompInfoRunTime = CIndexOptionInfo::GetXmlCompInfoRunTime(
                             a4,
                             *(const struct CCompExecCtxtStmt **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + SystemThread_TlsIndex)
                                                                + SystemThread_TlsOffset),
                             *(struct IMemObj **)(v57 + 1000),
                             0,
                             v26,
                             0x3320u,
                             0x32E4u,
                             (const wchar_t *)a4 + 48,
                             *((_DWORD *)a4 + 88));
    }
    v213 = (void **)XmlCompInfoRunTime;
    v19 = (void **)XmlCompInfoRunTime;
    *((_QWORD *)this + 27) = XmlCompInfoRunTime;
    if ( !v201
      || (v59 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 232LL))(
                  *((_QWORD *)this + 2),
                  v53[v54]),
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 40LL))(v59, &v221),
          (v221 & 0x200000) == 0) )
    {
      if ( (*(_DWORD *)a4 & 0x2000000) != 0 )
      {
        v60 = *((_BYTE *)a4 + 25);
        *((_BYTE *)this + 224) &= ~4u;
        *((_BYTE *)this + 224) |= 4 * ((v60 & 0x10) != 0);
      }
    }
    v18 = v212;
  }
  v5 = a3;
LABEL_93:
  if ( (*((_BYTE *)this + 171) & 1) != 0 )
  {
    if ( CIndexDDL::FConvertToResumeIfPossibleAndExecute(this, 0, 0, a2, (unsigned int)v194) )
      goto LABEL_340;
    v61 = v5;
    v62 = a2;
    CIndexDDL::LockStatisticsRes(this, a2, v61);
  }
  else
  {
    v62 = a2;
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 352LL))(*((_QWORD *)this + 2)) )
  {
    v64 = (***((__int64 (__fastcall ****)(_QWORD))this + 2))(*((_QWORD *)this + 2));
    v65 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
    ex_raise(106, 37, 16, 3, 12, L"object", v65);
  }
  v211 = 0;
  v227 = 0;
  if ( (*((_BYTE *)this + 171) & 1) != 0 && ((*(_BYTE *)a4 & 0x20) == 0 || (*((_BYTE *)a4 + 24) & 8) == 0) )
  {
    v66 = *(_QWORD *)(*((_QWORD *)this + 7) + 656LL);
    v211 = (*(__int64 (__fastcall **)(struct IAutoXactFactory *))(*(_QWORD *)g_pAutoXactFactory + 8LL))(g_pAutoXactFactory);
    LOBYTE(v194) = 0;
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64, __int64, _DWORD))(*(_QWORD *)v211 + 24LL))(
      v211,
      L"RESUMABLE_BUILD_MD_CREATION",
      54,
      v66,
      (_DWORD)v194);
    if ( v211 )
      v67 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v211 + 64LL))(v211);
    else
      v67 = 0;
    v68 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v69 = *(_QWORD *)(v68 + 256);
    if ( !v69 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v69 = *(_QWORD *)(v68 + 256);
    }
    v227 = (struct IMetadataAccess *)g_metadataFactory(
                                       *(_QWORD *)(v69 + 1000),
                                       v67,
                                       "Sql\\Ntdbms\\msql\\ddl\\indcreat.cpp",
                                       18991);
    CIndexDDL::SetActiveIMedAccess(this, v227, 0);
    *((_QWORD *)this + 14) = &v211;
  }
  v70 = *((_BYTE *)this + 160);
  v71 = v201;
  if ( (v70 & 0x40) != 0 && (v201 || v202) && (v70 & 0x10) == 0 )
  {
    v72 = (struct IMEDRelation *)*((_QWORD *)this + 2);
    if ( v201 )
    {
      v73 = (*(__int64 (__fastcall **)(struct IMEDRelation *, _QWORD))(*(_QWORD *)v72 + 232LL))(v72, v62[v54]);
      v74 = (const wchar_t **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 24LL))(v73);
      v75 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 24LL))(v73);
      CTableIndexUtil::FailIfLobAndActiveXact(
        *((_BYTE *)this + 169),
        v76,
        *((struct IMEDRelation **)this + 2),
        *(_DWORD *)(v75 + 8),
        *v74);
      v71 = v201;
    }
    else
    {
      CTableIndexUtil::FailIfLobAndActiveXact(
        *((_BYTE *)this + 169),
        v63,
        v72,
        *((_DWORD *)this + 38),
        *((const wchar_t **)this + 18));
    }
  }
  *((_BYTE *)this + 161) ^= (*((_BYTE *)this + 161) ^ (*((_BYTE *)a4 + 1969) >> 3)) & 1;
  if ( v71 )
    v77 = *((_DWORD *)this + 49);
  else
    v77 = 0;
  v78 = (struct IMEDIndex *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 360LL))(
                              *((_QWORD *)this + 2),
                              0,
                              0);
  v203 = SMD::FHasOriginalLocator(v78, v77);
  if ( v71 )
    StopClusteredCrawl(*((struct IMetadataAccess **)this + 1), *((struct IMEDRelation **)this + 2), 0);
  if ( *(char *)a4 < 0 && *((char *)a4 + 24) < 0 )
  {
    v79 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 392LL))(*((_QWORD *)this + 2), 0);
    v80 = v79;
    if ( v79 )
    {
      v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 8LL))(v79);
      v82 = v81 == 1 && v71;
      v83 = v81 == 1 && !v71;
      (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2), v249);
      v84 = (v249[40] & 0x20) != 0;
      v239 = 0;
      v241 = 0;
      v242 = 0;
      v244 = 1;
      v243 = -1;
      v240 = -2;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v80 + 40LL))(v80, &v239);
      if ( v83 && (*(_DWORD *)a4 & 0x10000000) != 0 && (*((_BYTE *)a4 + 26) & 4) != 0 )
      {
        LODWORD(v194) = 13088;
        ex_raise(353, 97, 16, 1, v194);
      }
      if ( (!*((_BYTE *)qword_102EF3550 + 232) || (*((_BYTE *)qword_102ECFB10 + 1279) & 8) != 0) && v82 && !v84
        || (!*((_BYTE *)qword_102EF3550 + 1071) || (*((_BYTE *)qword_102ECFB10 + 1279) & 0x10) != 0) && v83
        || (!*((_BYTE *)qword_102EF3550 + 1095)
         || (*((_BYTE *)qword_102ECFB10 + 1277) & 4) != 0
         || v202
         || *((char *)a4 + 1968) < 0)
        && (!*((_BYTE *)qword_102EF3550 + 1068) || (*((_BYTE *)qword_102ECFB10 + 1277) & 0x10) != 0)
        && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v80 + 8LL))(v80) != 1 )
      {
        LODWORD(v194) = 13088;
        ex_raise(353, 52, 16, 1, v194);
        v71 = v201;
        goto LABEL_158;
      }
    }
    else
    {
      if ( (*((_BYTE *)a4 + 1968) & 9) != 9 )
        goto LABEL_158;
      for ( i = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 360LL))(
                  *((_QWORD *)this + 2),
                  0,
                  0);
            i;
            i = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 2) + 360LL))(
                  *((_QWORD *)this + 2),
                  i,
                  0) )
      {
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)i + 8LL))(i) > 1
          && !CFeatureSwitchesMin::FNCIOnCCIOnlineIndexRebuildEnabled(qword_102EF3550) )
        {
          v86 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 24LL))(i);
          LODWORD(v194) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 24LL))(i) + 8);
          ex_raise(353, 91, 16, 2, v194, *v86);
        }
      }
    }
    v71 = v201;
  }
LABEL_158:
  v87 = 0;
  if ( (*(_BYTE *)a4 & 0x20) != 0 && (*((_BYTE *)a4 + 24) & 8) != 0 )
  {
    v88 = *((_BYTE *)a4 + 1968);
    if ( (v88 & 1) != 0 && (v88 & 2) == 0 )
    {
      v87 = *a2 > 1;
      v207 = v87;
    }
  }
  if ( *((_DWORD *)this + 39) == 8278 )
  {
    v89 = (***((__int64 (__fastcall ****)(_QWORD))this + 5))(*((_QWORD *)this + 5));
    LOBYTE(v200) = 0;
    LOBYTE(v194) = 0;
    LOBYTE(v90) = 1;
    CBaseTableCollection::Populate(
      &v217,
      *((_QWORD *)this + 4),
      v89,
      v90,
      (_DWORD)v194,
      *((_DWORD *)this + 139),
      *((_DWORD *)this + 140),
      (_DWORD)v200);
  }
  *((_QWORD *)a4 + 247) = *((_QWORD *)this + 2);
  if ( !v71 && !v202 && !v87 )
    goto LABEL_214;
  v91 = (__int64 *)*((_QWORD *)this + 2);
  v92 = *v91;
  if ( v71 )
  {
    v93 = (struct IMEDIndex *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(v92 + 232))(v91, a2[v206]);
    (*(void (__fastcall **)(struct IMEDIndex *, __int64 *))(*(_QWORD *)v93 + 40LL))(v93, &v221);
    *((_BYTE *)this + 168) &= ~4u;
    *((_BYTE *)this + 168) |= (BYTE2(v221) >> 3) & 4;
    v94 = BYTE1(v221);
    if ( (v221 & 0x1000) != 0 && (*((_BYTE *)this + 160) & 0x40) != 0 )
    {
      v95 = (_QWORD *)(*(__int64 (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v93 + 24LL))(v93);
      LODWORD(v194) = *(_DWORD *)((*(__int64 (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v93 + 24LL))(v93) + 8);
      ex_raise(19, 88, 16, 1, v194, *v95);
      v94 = BYTE1(v221);
    }
    v205 = (v94 & 0x10) != 0;
    v96 = (v94 & 1) == 0;
    if ( (v94 & 1) != 0 )
      goto LABEL_181;
    v97 = 8LL * SystemThread_TlsIndex;
    if ( (*(_BYTE *)(*(_QWORD *)(SystemThread_TlsOffset
                               + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v97)
                               + 80LL)
                   + 1000LL)
        & 2) != 0 )
      goto LABEL_180;
    if ( *((_DWORD *)this + 204) == 2 )
    {
      v98 = (*((_BYTE *)a4 + 1969) & 1) == 0;
    }
    else
    {
      if ( (*((_BYTE *)a4 + 1969) & 1) == 0 )
      {
LABEL_179:
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v97))
                                    + 128LL)
                        + 80LL)
            & 0x80000) == 0 )
        {
LABEL_181:
          if ( (v221 & 0x200000) != 0 && *((_DWORD *)this + 204) == 3 )
            *((_BYTE *)a4 + 1968) |= 0x80u;
          goto LABEL_193;
        }
LABEL_180:
        *((_BYTE *)a4 + 1968) |= 0x80u;
        goto LABEL_181;
      }
      v98 = (*((_BYTE *)this + 160) & 0x40) == 0;
    }
    if ( !v98 )
      goto LABEL_180;
    goto LABEL_179;
  }
  v99 = *(__int64 (__fastcall **)(__int64 *, _QWORD))(v92 + 232);
  if ( v202 )
  {
    v93 = (struct IMEDIndex *)v99(v91, 0);
    if ( *((_DWORD *)this + 49) )
    {
      v100 = *((_BYTE *)this + 160);
      if ( (v100 & 0x40) == 0 )
        *((_BYTE *)this + 160) = v100 | 8;
    }
    (*(void (__fastcall **)(struct IMEDIndex *, __int64 *))(*(_QWORD *)v93 + 40LL))(v93, &v221);
    if ( (v221 & 0x1000) != 0 && (*((_BYTE *)this + 160) & 0x40) != 0 )
    {
      v101 = (***((__int64 (__fastcall ****)(_QWORD))this + 2))(*((_QWORD *)this + 2));
      v102 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v101 + 40LL))(v101);
      LODWORD(v194) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v101 + 40LL))(v101) + 8);
      ex_raise(20, 5, 16, 1, v194, *v102);
    }
  }
  else
  {
    v93 = (struct IMEDIndex *)v99(v91, *a2);
  }
  v96 = 0;
LABEL_193:
  (*(void (__fastcall **)(struct IMEDIndex *, __int64 *))(*(_QWORD *)v93 + 40LL))(v93, &v221);
  if ( (v221 & 0x1000) != 0 )
    v210 = (*(unsigned int (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v93 + 240LL))(v93) != 0;
  CIndexDDL::RebuildIndexEntry(this, v93, a4, 0);
  if ( v202 || *((char *)a4 + 1968) < 0 )
  {
    *((_BYTE *)a4 + 1969) |= 1u;
    *((_BYTE *)this + 168) &= ~2u;
  }
  if ( v96 && *((char *)a4 + 1968) >= 0 && !*((_BYTE *)this + 172) )
  {
    if ( *((_DWORD *)this + 153) )
      v103 = **((_QWORD **)this + 78);
    else
      v103 = 0;
    v104 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v103 + 320LL))(v103);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 168LL))(v104);
  }
  if ( (*((_BYTE *)a4 + 1969) & 1) == 0 )
  {
LABEL_214:
    v106 = 0;
    goto LABEL_215;
  }
  if ( (*((_BYTE *)this + 160) & 4) != 0 )
    v105 = (struct IMEDDataSpace *)*((_QWORD *)a4 + 248);
  else
    v105 = 0;
  if ( (*(_BYTE *)a4 & 0x20) != 0 && (*((_BYTE *)a4 + 24) & 8) != 0 && (*((_BYTE *)this + 171) & 1) == 0 )
  {
    CIndexDDL::RebuildNCIndexEntries(this, 0, v105);
    v106 = 1;
    v204 = 1;
  }
  else
  {
    CIndexDDL::RebuildNCIndexEntries(this, a4, v105);
    v106 = 1;
    v204 = 1;
  }
LABEL_215:
  v107 = 0;
  if ( a3 )
  {
    v108 = a2;
    v109 = v214;
    do
    {
      if ( v106 )
        break;
      if ( v107 != v206 && v107 != v109 )
      {
        v110 = (struct IMEDIndex *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 232LL))(
                                     *((_QWORD *)this + 2),
                                     *v108);
        (*(void (__fastcall **)(struct IMEDIndex *, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v221);
        if ( (v221 & 0x1000) != 0 )
        {
          v111 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 360LL))(
                   *((_QWORD *)this + 2),
                   0,
                   0);
          v112 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v111 + 240LL))(v111);
          v113 = v210;
          if ( v112 )
            v113 = 1;
          v210 = v113;
        }
        if ( (*((_BYTE *)a4 + 1969) & 0x10) != 0 )
        {
          *((_DWORD *)this + 41) = *a2;
          *((_BYTE *)this + 161) |= 0x18u;
        }
        v114 = *((_QWORD *)this + 26);
        if ( v114 )
          *(_QWORD *)(v114 + 24) = v110;
        v115 = *((_QWORD *)this + 27);
        if ( v115 )
          *(_QWORD *)(v115 + 24) = v110;
        CIndexDDL::RebuildIndexEntry(this, v110, a4, 0);
        v106 = v204;
      }
      ++v107;
      ++v108;
    }
    while ( v107 < a3 );
  }
  v116 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v117 = *(_QWORD *)(v116 + 256);
  if ( !v117 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v117 = *(_QWORD *)(v116 + 256);
  }
  DeadlockPriority = SOS_Task::GetDeadlockPriority(*(_QWORD *)(v117 + 600));
  if ( (*((_BYTE *)this + 160) & 0x40) != 0 && !DeadlockPriority )
    DeadlockPriority = -10;
  v220 = 0;
  AutoChangeDeadlockPriority::SetDeadlockPriority(&v220, DeadlockPriority);
  if ( (*((_BYTE *)a4 + 1968) & 2) != 0 )
  {
    CIndexDDL::ConstructHypotheticalIndex(this, a4);
  }
  else if ( (*((_BYTE *)this + 160) & 0x40) != 0 )
  {
    if ( (*((_BYTE *)this + 171) & 1) != 0 )
    {
      v227 = 0;
      v229 = 0;
    }
    CIndexDDL::ConstructIndicesOnline(this);
  }
  else
  {
    CIndexDDL::ConstructIndicesOffline(this);
  }
  if ( HIDWORD(v220) )
  {
    v119 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v120 = *(_QWORD *)(v119 + 256);
    if ( !v120 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v120 = *(_QWORD *)(v119 + 256);
    }
    SOS_Task::SetDeadlockPriority(*(_QWORD *)(v120 + 600), (unsigned int)v220);
  }
  if ( v227 )
    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v227)(v227, 1);
  if ( v211 )
    (**(void (__fastcall ***)(__int64, __int64))v211)(v211, 1);
  if ( (*((_BYTE *)this + 171) & 1) != 0 )
    CIndexDDL::UpdateStatsIfNecessaryForResumable(this);
  v121 = 0;
  v228 = 0;
  v122 = *(struct BaseXact **)(*((_QWORD *)this + 7) + 656LL);
  v230 = v122;
  if ( (*((_BYTE *)this + 171) & 1) != 0 )
  {
    AutoOverrideMsqlXact::InitializeAndOverride(
      *((AutoOverrideMsqlXact **)this + 16),
      *(struct CMsqlXactManager **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset
                                              + 32LL)
                                  + 72LL));
    v123 = *(_QWORD *)(*((_QWORD *)this + 7) + 656LL);
    v124 = *((_QWORD *)this + 17);
    *(_DWORD *)(v124 + 8) = 1;
    v125 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset)
                     + 144LL);
    *(_QWORD *)(v124 + 16) = v125;
    LOBYTE(v199[0]) = 0;
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64, __int64, int, int, unsigned int, __int64, _DWORD))(*(_QWORD *)v125 + 8LL))(
      v125,
      L"RESUMABLE_BUILD_SWAP",
      40,
      1,
      2,
      1,
      v199[0],
      v123,
      0);
    *(_DWORD *)v124 = 1;
    v126 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 17) + 16LL) + 432LL))(*(_QWORD *)(*((_QWORD *)this + 17) + 16LL));
    v127 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v128 = *(_QWORD *)(v127 + 256);
    if ( !v128 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v128 = *(_QWORD *)(v127 + 256);
    }
    v121 = g_metadataFactory(*(_QWORD *)(v128 + 1000), v126, "Sql\\Ntdbms\\msql\\ddl\\indcreat.cpp", 19339);
    v228 = v121;
    v129 = *(_QWORD *)v121;
    v130 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
    v131 = (__int64 *)(*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(v129 + 56))(
                        v121,
                        v130,
                        0,
                        0,
                        0,
                        0);
    v132 = (***((__int64 (__fastcall ****)(_QWORD))this + 5))(*((_QWORD *)this + 5));
    v133 = *v131;
    v134 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v132 + 8LL))(v132);
    LOBYTE(v198) = 1;
    LOBYTE(v195) = 0;
    LOBYTE(v135) = 1;
    v136 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, int, int, _DWORD, _DWORD))(v133 + 120))(
             v131,
             v134,
             v135,
             0,
             v195,
             v198,
             0,
             0);
    v137 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v136 + 120LL))(v136);
    for ( j = 0; j < *((_DWORD *)this + 145); ++j )
    {
      if ( *(_QWORD *)(*((_QWORD *)this + 74) + 8LL * j) )
      {
        if ( j >= *((_DWORD *)this + 169) )
          v139 = 0;
        else
          v139 = *(unsigned int *)(*((_QWORD *)this + 86) + 4LL * j);
        v219 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v137 + 232LL))(v137, v139);
        CTDynArray<CBaseTableProjectedColumnInfo *,CFnI_Default<CBaseTableProjectedColumnInfo *>,CFnD_Noop<CBaseTableProjectedColumnInfo *>,CMemObjAlloc<0>>::TReplace(
          (char *)this + 568,
          j,
          &v219);
      }
    }
    for ( k = 0; k < *((_DWORD *)this + 153); ++k )
    {
      if ( k >= *((_DWORD *)this + 177) )
        v141 = 0;
      else
        v141 = *(unsigned int *)(*((_QWORD *)this + 90) + 4LL * k);
      v142 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v137 + 232LL))(v137, v141);
      v143 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v142 + 48LL))(v142);
      if ( v143 )
        v142 = v143;
      v231 = v142;
      CTDynArray<CBaseTableProjectedColumnInfo *,CFnI_Default<CBaseTableProjectedColumnInfo *>,CFnD_Noop<CBaseTableProjectedColumnInfo *>,CMemObjAlloc<0>>::TReplace(
        (char *)this + 600,
        k,
        &v231);
    }
    for ( m = 0; m < *((_DWORD *)this + 161); ++m )
    {
      if ( m >= *((_DWORD *)this + 185) )
        v145 = 0;
      else
        v145 = *(unsigned int *)(*((_QWORD *)this + 94) + 4LL * m);
      v232[0] = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v137 + 232LL))(v137, v145);
      CTDynArray<CBaseTableProjectedColumnInfo *,CFnI_Default<CBaseTableProjectedColumnInfo *>,CFnD_Noop<CBaseTableProjectedColumnInfo *>,CMemObjAlloc<0>>::TReplace(
        (char *)this + 632,
        m,
        v232);
    }
    *((_QWORD *)this + 3) = v131;
    *((_QWORD *)this + 2) = v137;
    *((_QWORD *)this + 1) = v121;
    v146 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
    v147 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3));
    v148 = g_dbtableFactory[4](v147);
    *((_QWORD *)this + 10) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v146 + 272LL))(
                               v146,
                               *(unsigned __int16 *)(v148 + 40),
                               *(_QWORD *)(v148 + 4624));
    *((_QWORD *)this + 11) = 0;
    v149 = (***((__int64 (__fastcall ****)(_QWORD))this + 2))(*((_QWORD *)this + 2));
    v150 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 648LL))(*((_QWORD *)this + 2));
    v151 = *v150;
    v152 = *((_QWORD *)this + 3);
    LODWORD(v149) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v149 + 8LL))(v149);
    v153 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v152 + 16LL))(v152);
    LOBYTE(v196) = 0;
    (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, int))(v151 + 312))(
      v150,
      *((_QWORD *)this + 1),
      v153,
      (unsigned int)v149,
      v196);
    if ( a3 )
    {
      v154 = 0;
      v155 = a3;
      do
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v154 + *((_QWORD *)this + 15)) + 104LL))(*(_QWORD *)(v154 + *((_QWORD *)this + 15)));
        v154 += 8;
        --v155;
      }
      while ( v155 );
    }
    v156 = (void *)*((_QWORD *)this + 15);
    *((_QWORD *)this + 15) = 0;
    operator delete(v156, 8u);
    v122 = v230;
  }
  if ( !*((_BYTE *)this + 172) )
    goto LABEL_293;
  v157 = 8LL * SystemThread_TlsIndex;
  if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + v157)
                                                     + SystemThread_TlsOffset)
                                         + 72LL)
                             + 456LL)
                 + 24LL) )
  {
    v121 = v228;
LABEL_293:
    if ( v207 )
      v163 = *a2;
    else
      v163 = -1;
    CIndexDDL::CleanupIndices(this, v163);
    if ( v201 )
      CIndexDDL::AddLocatorColumn(this, v203, v122);
    if ( (*((_BYTE *)this + 171) & 1) == 0 )
    {
      for ( n = 0; n < *((_DWORD *)this + 153); ++n )
        CIndexDDL::UpdateStatsIfNecessary(this, n);
    }
    if ( v205
      || (*(_BYTE *)a4 & 0x20) != 0
      && (*((_BYTE *)a4 + 24) & 8) != 0
      && (*((_BYTE *)a4 + 1968) & 1) != 0
      && (*((_BYTE *)a4 + 1969) & 1) != 0 )
    {
      v165 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3));
      if ( (*(_DWORD *)(g_dbtableFactory[4](v165) + 1524) & 4) != 0 )
      {
        v166 = *((_BYTE *)this + 160);
        if ( v166 >= 0 && (v166 & 1) == 0 && *((_DWORD *)this + 39) == 8277 )
          MatchingPartitionIndexViewHelper::CheckAndCreateMpIdxViewsAfterSchemaChange(
            *((struct IMetadataAccess **)this + 1),
            *((struct IMEDRelation **)this + 2),
            (v166 & 0x40) != 0,
            0);
      }
    }
    if ( *((_DWORD *)this + 39) == 8278 && (*((_BYTE *)this + 171) & 1) != 0 )
    {
      v216 = &v215;
      v215 = (__int64)&v215;
      v167 = (***((__int64 (__fastcall ****)(_QWORD))this + 2))(*((_QWORD *)this + 2));
      LOBYTE(v200) = 0;
      LOBYTE(v194) = 0;
      LOBYTE(v168) = 1;
      CBaseTableCollection::Populate(
        &v215,
        *((_QWORD *)this + 1),
        v167,
        v168,
        (_DWORD)v194,
        *((_DWORD *)this + 139),
        *((_DWORD *)this + 140),
        (_DWORD)v200);
      v169 = v216;
      if ( v216 != &v215 && v216 )
      {
        do
        {
          v170 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v169[2] + 296LL))(v169[2]);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v170 + 200LL))(v170);
          v171 = (__int64 *)v169[1];
          v172 = v171;
          if ( v171 == &v215 )
            v172 = 0;
          v173 = (_QWORD *)*v169;
          v173[1] = v171;
          *v171 = (__int64)v173;
          v169[1] = 0;
          *v169 = 0;
          operator delete(v169, 0x18u);
          v169 = v172;
        }
        while ( v172 );
      }
      v174 = v216;
      if ( v216 != &v215 && v216 )
      {
        do
        {
          v175 = (__int64 *)v174[1];
          v176 = v175;
          if ( v175 == &v215 )
            v176 = 0;
          v177 = *v174;
          *(_QWORD *)(v177 + 8) = v175;
          *v175 = v177;
          v174[1] = 0;
          *v174 = 0;
          operator delete(v174, 0x18u);
          v174 = v176;
        }
        while ( v176 );
      }
    }
    else
    {
      v178 = v218;
      if ( v218 != &v217 && v218 )
      {
        do
        {
          v179 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v178[2] + 296LL))(v178[2]);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v179 + 200LL))(v179);
          v180 = (__int64 *)v178[1];
          v181 = v180;
          if ( v180 == &v217 )
            v181 = 0;
          v182 = (_QWORD *)*v178;
          v182[1] = v180;
          *v180 = (__int64)v182;
          v178[1] = 0;
          *v178 = 0;
          operator delete(v178, 0x18u);
          v178 = v181;
        }
        while ( v181 );
      }
    }
    goto LABEL_329;
  }
  v158 = CIndexDDL::ExportInfoForDeferredCleanupIndices(
           this,
           *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                                  + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                              + v157))
                                                      + 72LL)
                                          + 456LL)
                              + 8LL));
  v232[1] = 0;
  v159 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset)
                               + 72LL)
                   + 456LL);
  v160 = *(_QWORD *)(v159 + 16);
  v161 = *(_DWORD *)(v160 + 16);
  if ( !*(_QWORD *)(v160 + 24) )
  {
    *(_QWORD *)(v160 + 24) = StdAlloc<CRawMemObjAlloc<0>>::AllocArray<CReqdPlanProperties *>(
                               *(_QWORD *)(v159 + 16),
                               v161);
    *(_DWORD *)(v160 + 16) = v161;
  }
  v162 = *(_DWORD *)(v160 + 12);
  if ( v162 >= v161 )
  {
    if ( v162 == -1 )
    {
      utassert_fail(1u, "m_cElems < ULONG_MAX", "Sql\\Ntdbms\\include\\common\\stdarray.inl", 217, 0);
      v162 = *(_DWORD *)(v160 + 12);
    }
    CTDynArray<DRgCId *,CFnI_Default<DRgCId *>,CFnD_Refc_Opt<DRgCId>,CMemObjAlloc<0>>::DoResize(v160, v162 + 1);
    v162 = *(_DWORD *)(v160 + 12);
  }
  *(_QWORD *)(*(_QWORD *)(v160 + 24) + 8LL * v162) = v158;
  ++*(_DWORD *)(v160 + 12);
  v121 = v228;
LABEL_329:
  if ( v121 )
    (**(void (__fastcall ***)(__int64, __int64))v121)(v121, 1);
  v183 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 240LL))(
           *((_QWORD *)this + 5),
           *a2,
           0,
           0);
  if ( v183 )
  {
    v184 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v183 + 72LL))(v183);
    v185 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 232LL))(*((_QWORD *)this + 5), *a2);
    v233 = 0;
    v235 = 0;
    v236 = 0;
    v238 = 1;
    v237 = -1;
    v234 = -2;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v185 + 40LL))(v185, &v233);
    (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5), v250);
    if ( !v184
      && (*((_BYTE *)this + 824) & 1) != 0
      && (v233 & 0x200000) == 0
      && !*((_DWORD *)this + 49)
      && !v210
      && (v250[40] & 0x20) == 0 )
    {
      v186 = *(_QWORD *)(***((__int64 (__fastcall ****)(_QWORD))this + 6))(*((_QWORD *)this + 6));
      v187 = *(_DWORD *)((***((__int64 (__fastcall ****)(_QWORD))this + 6))(*((_QWORD *)this + 6)) + 8);
      v188 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v185 + 24LL))(v185);
      v189 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v185 + 24LL))(v185);
      scierrlog(0x29B5u, *(unsigned int *)(v189 + 8), *v188, v187, v186);
    }
  }
  CIndexDDL::ResetOperationState(this);
  v18 = v212;
  v19 = v213;
LABEL_340:
  if ( v19 )
  {
    operator delete[](v19[1]);
    operator delete(v19, 0x20u);
  }
  if ( v18 )
  {
    operator delete[](v18[1]);
    operator delete(v18, 0x20u);
  }
  if ( v229 )
    (**v229)(v229, 1);
  v190 = v218;
  if ( v218 != &v217 && v218 )
  {
    do
    {
      v191 = (__int64 *)v190[1];
      v192 = v191;
      if ( v191 == &v217 )
        v192 = 0;
      v193 = *v190;
      *(_QWORD *)(v193 + 8) = v191;
      *v191 = v193;
      v190[1] = 0;
      *v190 = 0;
      operator delete(v190, 0x18u);
      v190 = v192;
    }
    while ( v192 );
  }
}

```

## disassembly

```asm
0x100b9df00  push    rbp
0x100b9df02  push    rbx
0x100b9df03  push    rsi
0x100b9df04  push    rdi
0x100b9df05  push    r12
0x100b9df07  push    r13
0x100b9df09  push    r14
0x100b9df0b  push    r15
0x100b9df0d  lea     rbp, [rsp-118h]
0x100b9df15  sub     rsp, 218h
0x100b9df1c  mov     [rbp+150h+var_E0], 0FFFFFFFFFFFFFFFEh
0x100b9df24  mov     rax, cs:__security_cookie
0x100b9df2b  xor     rax, rsp
0x100b9df2e  mov     [rbp+150h+var_48], rax
0x100b9df35  mov     r13, r9
0x100b9df38  mov     r14d, r8d
0x100b9df3b  mov     [rsp+250h+var_1E8], r8d
0x100b9df40  mov     r15, rdx
0x100b9df43  mov     [rsp+250h+var_1F0], rdx
0x100b9df48  mov     rsi, rcx
0x100b9df4b  xor     r12d, r12d
0x100b9df4e  mov     [rbp+150h+var_190], r12
0x100b9df52  mov     [rbp+150h+var_184], r12
0x100b9df56  mov     [rbp+150h+var_17C], r12d
0x100b9df5a  mov     [rbp+150h+var_174], 1
0x100b9df62  mov     [rbp+150h+var_178], 0FFFFFFFFh
0x100b9df69  mov     [rbp+150h+var_188], 0FFFFFFFEh
0x100b9df70  lea     edi, [r12+1]
0x100b9df75  xorps   xmm0, xmm0
0x100b9df78  movdqu  [rbp+150h+var_1B0], xmm0
0x100b9df7d  lea     rax, [rbp+150h+var_1B0]
0x100b9df81  mov     qword ptr [rbp+150h+var_1B0+8], rax
0x100b9df85  lea     rax, [rbp+150h+var_1B0]
0x100b9df89  mov     qword ptr [rbp+150h+var_1B0], rax
0x100b9df8d  mov     [rbp+150h+var_158], r12
0x100b9df91  test    [rcx+0ABh], dil
0x100b9df98  jz      short loc_100B9DFAF
0x100b9df9a  test    byte ptr [r9], 20h
0x100b9df9e  jz      short loc_100B9DFAF
0x100b9dfa0  test    byte ptr [r9+18h], 8
0x100b9dfa5  jz      short loc_100B9DFAF
0x100b9dfa7  mov     rax, [rcx+8]
0x100b9dfab  mov     [rbp+150h+var_158], rax
0x100b9dfaf  cmp     dword ptr [rcx+330h], 0
0x100b9dfb6  jnz     short loc_100B9DFC2
0x100b9dfb8  mov     dword ptr [rcx+330h], 3
0x100b9dfc2  mov     [rsp+250h+var_200], 0
0x100b9dfc7  mov     [rsp+250h+var_1F8], 0FFFFFFFFh
0x100b9dfcf  mov     [rsp+250h+var_1FF], 0
0x100b9dfd4  mov     [rbp+150h+var_1C8], 0FFFFFFFFh
0x100b9dfdb  xor     al, al
0x100b9dfdd  mov     [rsp+250h+var_1F4], eax
0x100b9dfe1  mov     [rsp+250h+var_1FD], al
0x100b9dfe5  mov     [rsp+250h+var_1FC], al
0x100b9dfe9  mov     byte ptr [rsp+250h+var_1E4], al
0x100b9dfed  mov     eax, r12d
0x100b9dff0  test    r8d, r8d
0x100b9dff3  jz      short loc_100B9E023
0x100b9dff5  mov     rcx, r15
0x100b9dff8  mov     edx, [rcx]
0x100b9dffa  test    edx, edx
0x100b9dffc  jz      short loc_100B9E01B
0x100b9dffe  cmp     edx, 1
0x100b9e001  jz      short loc_100B9E010
0x100b9e003  inc     eax
0x100b9e005  add     rcx, 4
0x100b9e009  cmp     eax, r8d
0x100b9e00c  jb      short loc_100B9DFF8
0x100b9e00e  jmp     short loc_100B9E023
0x100b9e010  mov     [rsp+250h+var_200], 1
0x100b9e015  mov     [rsp+250h+var_1F8], eax
0x100b9e019  jmp     short loc_100B9E023
0x100b9e01b  mov     [rsp+250h+var_1FF], 1
0x100b9e020  mov     [rbp+150h+var_1C8], eax
0x100b9e023  mov     r8d, [rsi+98h]; int
0x100b9e02a  mov     rdx, [rsi+90h]; wchar_t *
0x100b9e031  lea     rcx, [rbp+150h+var_D8]; this
0x100b9e035  call    ?Parse@WParseName@@QEAAXPEB_WH@Z; WParseName::Parse(wchar_t const *,int)
0x100b9e03a  mov     ecx, [rbp+150h+var_AC]
0x100b9e040  lea     eax, [rcx+rcx]
0x100b9e043  test    eax, eax
0x100b9e045  jz      loc_100B9E192
0x100b9e04b  mov     rcx, [rbp+150h+var_C0]
0x100b9e052  cmp     word ptr [rcx], 23h ; '#'
0x100b9e056  jnz     loc_100B9E192
0x100b9e05c  cmp     eax, 2
0x100b9e05f  jz      short loc_100B9E071
0x100b9e061  add     eax, 0FFFFFFFEh
0x100b9e064  jz      short loc_100B9E071
0x100b9e066  cmp     word ptr [rcx+2], 23h ; '#'
0x100b9e06b  jz      loc_100B9E192
0x100b9e071  xor     bl, bl
0x100b9e073  call    cs:__imp_GetXdbServerGlobals
0x100b9e079  cmp     [rax+2EE4h], bl
0x100b9e07f  jz      short loc_100B9E0F2
0x100b9e081  mov     rdx, gs:58h
0x100b9e08a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100b9e091  mov     ecx, [rax]
0x100b9e093  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100b9e09a  mov     eax, [rax]
0x100b9e09c  add     rax, [rdx+rcx*8]
0x100b9e0a0  mov     rax, [rax]
0x100b9e0a3  mov     rcx, [rax+48h]
0x100b9e0a7  mov     rcx, [rcx+1B0h]; this
0x100b9e0ae  test    rcx, rcx
0x100b9e0b1  jnz     short loc_100B9E0D6
0x100b9e0b3  mov     [rsp+250h+var_230], r12
0x100b9e0b8  mov     r9d, 495Dh
0x100b9e0be  lea     r8, aIndcreatCpp; "indcreat.cpp"
0x100b9e0c5  lea     rdx, aPfidotemplist; "pFidoTempList"
0x100b9e0cc  mov     ecx, edi
0x100b9e0ce  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100b9e0d4  jmp     short loc_100B9E0F2
0x100b9e0d6  mov     r8d, [rsi+98h]; int
0x100b9e0dd  mov     rdx, [rsi+90h]; wchar_t *
0x100b9e0e4  call    ?LookupFidoTempByName@CFidoTempObjectList@@QEAAPEAVFidoTempObject@@PEB_WH@Z; CFidoTempObjectList::LookupFidoTempByName(wchar_t const *,int)
0x100b9e0e9  movzx   ebx, bl
0x100b9e0ec  test    rax, rax
0x100b9e0ef  cmovnz  ebx, edi
0x100b9e0f2  mov     rdx, gs:58h
0x100b9e0fb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100b9e102  mov     ecx, [rax]
0x100b9e104  lea     r8, ds:0[rcx*8]
0x100b9e10c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100b9e113  mov     r9d, [rax]
0x100b9e116  mov     rax, [r8+rdx]
0x100b9e11a  mov     rdi, [rax+r9]
0x100b9e11e  test    bl, bl
0x100b9e120  jnz     short loc_100B9E192
0x100b9e122  mov     rax, gs:58h
0x100b9e12b  mov     rcx, [r8+rax]
0x100b9e12f  cmp     qword ptr [r9+rcx], 0
0x100b9e134  jz      short loc_100B9E192
0x100b9e136  cmp     [rdi+99h], bl
0x100b9e13c  jz      short loc_100B9E192
0x100b9e13e  mov     rax, gs:58h
0x100b9e147  mov     rcx, [r8+rax]
0x100b9e14b  mov     rax, [r9+rcx]
0x100b9e14f  mov     rcx, [rax+0A0h]
0x100b9e156  mov     rax, [rcx+8]
0x100b9e15a  test    byte ptr [rax+1BDh], 20h
0x100b9e161  jz      short loc_100B9E192
0x100b9e163  mov     rcx, [rsi+10h]
0x100b9e167  mov     rax, [rcx]
0x100b9e16a  call    qword ptr [rax]
0x100b9e16c  mov     rdx, [rax]
0x100b9e16f  mov     rcx, rax
0x100b9e172  call    qword ptr [rdx+8]
0x100b9e175  mov     rcx, [rdi+80h]
0x100b9e17c  add     rcx, 0A8h; this
0x100b9e183  mov     edx, eax; int
0x100b9e185  call    ?PLocalTmpTab@CScopedTmpObjectList@@QEBAPEAVTmpObject@@J@Z; CScopedTmpObjectList::PLocalTmpTab(long)
0x100b9e18a  test    rax, rax
0x100b9e18d  jz      short loc_100B9E192
0x100b9e18f  mov     [rax+21h], bl
0x100b9e192  test    byte ptr [rsi+0A0h], 40h
0x100b9e199  jz      short loc_100B9E1A3
0x100b9e19b  mov     rcx, rsi; this
0x100b9e19e  call    ?CheckLockForOnlineBuild@CIndexDDL@@IEAAXXZ; CIndexDDL::CheckLockForOnlineBuild(void)
0x100b9e1a3  movzx   r9d, byte ptr [rsi+0ABh]
0x100b9e1ab  and     r9b, 1
0x100b9e1af  xor     r8d, r8d
0x100b9e1b2  mov     dl, 1
0x100b9e1b4  mov     rcx, rsi
0x100b9e1b7  call    ?LockBuildIndexRes@CIndexDDL@@QEBAX_NW4KillLockOption@@0@Z; CIndexDDL::LockBuildIndexRes(bool,KillLockOption,bool)
0x100b9e1bc  mov     rdi, r12
0x100b9e1bf  mov     [rsp+250h+var_1D8], r12
0x100b9e1c4  mov     rbx, r12
0x100b9e1c7  mov     [rbp+150h+var_1D0], rbx
0x100b9e1cb  mov     rax, [r13+0]
0x100b9e1cf  mov     r12, rax
0x100b9e1d2  shr     r12, 15h
0x100b9e1d6  and     r12b, 1
0x100b9e1da  shr     rax, 19h
0x100b9e1de  and     al, 1
0x100b9e1e0  mov     [rbp+150h+var_150], rax
0x100b9e1e4  cmp     dword ptr [rsi+0C4h], 0
0x100b9e1eb  jnz     short loc_100B9E1FA
0x100b9e1ed  test    r12b, r12b
0x100b9e1f0  jnz     short loc_100B9E1FA
0x100b9e1f2  test    al, al
0x100b9e1f4  jz      loc_100B9E761
0x100b9e1fa  mov     rcx, [rsi+10h]
0x100b9e1fe  mov     rax, [rcx]
0x100b9e201  mov     edx, [r15]
0x100b9e204  call    qword ptr [rax+0E8h]
0x100b9e20a  mov     r15, rax
0x100b9e20d  mov     rcx, [rsi+18h]
0x100b9e211  mov     r14, [rcx]
0x100b9e214  mov     rdx, [rax]
0x100b9e217  mov     rcx, rax
0x100b9e21a  call    qword ptr [rdx+0E0h]
0x100b9e220  mov     edx, eax
0x100b9e222  mov     r9b, 1
0x100b9e225  movzx   r8d, r9b
0x100b9e229  mov     rcx, [rsi+18h]
0x100b9e22d  call    qword ptr [r14+2A8h]
0x100b9e234  mov     r14, rax
0x100b9e237  cmp     dword ptr [rsi+0C4h], 0
0x100b9e23e  jz      loc_100B9E357
0x100b9e244  mov     rdx, [rax]
0x100b9e247  mov     rcx, rax
0x100b9e24a  call    qword ptr [rdx+28h]
0x100b9e24d  test    rax, rax
0x100b9e250  jnz     short loc_100B9E2C8
0x100b9e252  mov     rdx, [r15]
0x100b9e255  mov     rcx, r15
0x100b9e258  call    qword ptr [rdx+8]
0x100b9e25b  mov     rdx, [r15]
0x100b9e25e  mov     rcx, r15
0x100b9e261  test    eax, eax
0x100b9e263  jnz     short loc_100B9E282
0x100b9e265  mov     eax, 32E5h
0x100b9e26a  mov     dword ptr [rbp+150h+var_1A0], eax
0x100b9e26d  call    qword ptr [rdx]
0x100b9e26f  mov     rdx, [rax]
0x100b9e272  mov     rcx, rax
0x100b9e275  call    qword ptr [rdx]
0x100b9e277  mov     rdx, [rax]
0x100b9e27a  mov     rcx, rax
0x100b9e27d  call    qword ptr [rdx+28h]
0x100b9e280  jmp     short loc_100B9E28D
0x100b9e282  mov     eax, 32E4h
0x100b9e287  mov     dword ptr [rbp+150h+var_1A0], eax
0x100b9e28a  call    qword ptr [rdx+18h]
0x100b9e28d  mov     rcx, rax
0x100b9e290  mov     rax, [rax]
0x100b9e293  mov     qword ptr [rsp+250h+var_210], rax
0x100b9e298  mov     eax, [rcx+8]
0x100b9e29b  mov     dword ptr [rsp+250h+var_218], eax
0x100b9e29f  mov     eax, dword ptr [rbp+150h+var_1A0]
0x100b9e2a2  mov     [rsp+250h+var_220], eax
0x100b9e2a6  mov     [rsp+250h+var_228], eax
0x100b9e2aa  mov     dword ptr [rsp+250h+var_230], 3320h
0x100b9e2b2  mov     edx, 1Dh
0x100b9e2b7  lea     ecx, [rdx+30h]
0x100b9e2ba  lea     r9d, [rdx-1Ch]
0x100b9e2be  lea     r8d, [rdx-0Dh]
0x100b9e2c2  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100b9e2c8  mov     rax, [r15]
0x100b9e2cb  mov     rcx, r15
0x100b9e2ce  call    qword ptr [rax+0F0h]
0x100b9e2d4  cmp     [rsi+0C4h], eax
0x100b9e2da  jbe     short loc_100B9E357
0x100b9e2dc  lfence
0x100b9e2df  mov     rax, [r15]
0x100b9e2e2  mov     rcx, r15
0x100b9e2e5  call    qword ptr [rax+8]
0x100b9e2e8  mov     rdx, [r15]
0x100b9e2eb  mov     rcx, r15
0x100b9e2ee  test    eax, eax
0x100b9e2f0  jnz     short loc_100B9E30C
0x100b9e2f2  mov     ebx, 32E5h
0x100b9e2f7  call    qword ptr [rdx]
0x100b9e2f9  mov     rdx, [rax]
0x100b9e2fc  mov     rcx, rax
0x100b9e2ff  call    qword ptr [rdx]
0x100b9e301  mov     rdx, [rax]
0x100b9e304  mov     rcx, rax
0x100b9e307  call    qword ptr [rdx+28h]
0x100b9e30a  jmp     short loc_100B9E314
0x100b9e30c  mov     ebx, 32E4h
0x100b9e311  call    qword ptr [rdx+18h]
0x100b9e314  mov     rcx, rax
0x100b9e317  mov     rax, [rax]
0x100b9e31a  mov     qword ptr [rsp+250h+var_210], rax
0x100b9e31f  mov     eax, [rcx+8]
0x100b9e322  mov     dword ptr [rsp+250h+var_218], eax
0x100b9e326  mov     [rsp+250h+var_220], ebx
0x100b9e32a  mov     eax, [rsi+0C4h]
0x100b9e330  mov     [rsp+250h+var_228], eax
0x100b9e334  mov     dword ptr [rsp+250h+var_230], ebx
0x100b9e338  mov     edx, 1Eh
0x100b9e33d  lea     ecx, [rdx+2Fh]
0x100b9e340  lea     r9d, [rdx-1Dh]
0x100b9e344  lea     r8d, [rdx-0Eh]
0x100b9e348  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100b9e34e  mov     rdi, [rsp+250h+var_1D8]
0x100b9e353  mov     rbx, [rbp+150h+var_1D0]
0x100b9e357  test    r12b, r12b
0x100b9e35a  jz      loc_100B9E5A2
0x100b9e360  mov     rax, [r13+7C0h]
0x100b9e367  test    rax, rax
0x100b9e36a  cmovnz  r14, rax
0x100b9e36e  mov     rcx, [rsi+10h]; struct IMEDRelation *
0x100b9e372  call    ?FTableHasSparseOrColSetColumns@@YA_NPEAVIMEDRelation@@@Z; FTableHasSparseOrColSetColumns(IMEDRelation *)
0x100b9e377  test    al, al
0x100b9e379  jz      loc_100B9E431
0x100b9e37f  mov     rax, [r13+40h]
0x100b9e383  test    rax, rax
0x100b9e386  jz      loc_100B9E431
0x100b9e38c  mov     r8d, [rax+4]
0x100b9e390  test    r8d, r8d
0x100b9e393  jnz     short loc_100B9E3CB
0x100b9e395  cmp     [rax], r8d
0x100b9e398  jz      loc_100B9E431
0x100b9e39e  mov     rax, [r15]
0x100b9e3a1  mov     rcx, r15
0x100b9e3a4  call    qword ptr [rax+8]
0x100b9e3a7  mov     rdx, [r15]
  ... truncated ...
```
