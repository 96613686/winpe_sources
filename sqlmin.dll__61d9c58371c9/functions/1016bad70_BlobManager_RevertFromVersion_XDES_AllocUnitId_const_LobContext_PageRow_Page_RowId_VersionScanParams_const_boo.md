# BlobManager::RevertFromVersion(XDES *,AllocUnitId const &,LobContext *,PageRow &,Page *,RowId,VersionScanParams const *,bool,bool,XdesRMReadWrite *,PageRef &)

- ea: `0x1016bad70`
- end: `0x1016bec51`
- name: `?RevertFromVersion@BlobManager@@SA?AW4LogicalRevertBlobReturnCode@@PEAVXDES@@AEBVAllocUnitId@@PEAVLobContext@@AEAVPageRow@@PEAVPage@@URowId@@PEBVVersionScanParams@@_N7PEAVXdesRMReadWrite@@AEAVPageRef@@@Z`
- size: `16097`
- prototype: ``
- caller_count: `3`
- callee_count: `41`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1005a8f50`
- `0x1016b80d0`
- `0x1016bad70`

## callees

- `0x100401490`
- `0x100402000`
- `0x10040e4f0`
- `0x10040fc00`
- `0x100427970`
- `0x100441ae0`
- `0x100441e00`
- `0x100441e40`
- `0x100450ee0`
- `0x10046c170`
- `0x1004729d0`
- `0x10047bad0`
- `0x100480030`
- `0x10048c200`
- `0x100490430`
- `0x10049a0c0`
- `0x10049ff80`
- `0x1004a08c0`
- `0x1004a2090`
- `0x1004bf030`
- `0x100604ea0`
- `0x10072db10`
- `0x101200050`
- `0x1012c9010`
- `0x10130cda0`
- `0x1016bad70`
- `0x1017371e0`
- `0x10191e410`
- `0x1019206f0`
- `0x101d11730`
- `0x101d19a30`
- `0x101d7f320`
- `0x101d94000`
- `0x1021d45f0`
- `0x1021d8a90`
- `0x1021e8a60`
- `0x1021e8ae0`
- `0x1021eab40`
- `0x102394d80`
- `0x1023aea00`
- `0x1023aee60`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1016bc572`
- `KERNEL32!HeapAlloc` at `0x1016bc572`
- `KERNEL32!GetProcessHeap` at `0x1016bc561`
- `KERNEL32!GetProcessHeap` at `0x1016bc561`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1016bc55a`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1016bc55a`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1016bc606`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1016bc606`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1016bc5c1`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1016bc5c1`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1016be472`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1016be5d7`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1016be752`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016beb51`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016beb51`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb0d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb20b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb359`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb7a8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb8c8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bc7c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bc906`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bca68`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bce85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bcfa8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bd623`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bd81a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bd94f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bdc60`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bdd85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb0d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb20b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb359`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb7a8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bb8c8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bc7c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bc906`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bca68`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bce85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bcfa8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bd623`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bd81a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bd94f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bdc60`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016bdd85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb0b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb1e3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb333`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb782`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb8a2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bbd39`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bc7a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bc8e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bca42`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bce5f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bcf82`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb0b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb1e3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb333`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb782`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bb8a2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bbd39`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bc7a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bc8e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bca42`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bce5f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016bcf82`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016bbf1c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016bc40b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016bc53d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016bbf1c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016bc40b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016bc53d`
- `sqldk!SystemThread_TlsIndex` at `0x1016bb028`
- `sqldk!SystemThread_TlsIndex` at `0x1016bb15b`
- `sqldk!SystemThread_TlsIndex` at `0x1016bb2ab`
- `sqldk!SystemThread_TlsIndex` at `0x1016bb6fa`
- `sqldk!SystemThread_TlsIndex` at `0x1016bb81a`
- `sqldk!SystemThread_TlsIndex` at `0x1016bbeb9`
- `sqldk!SystemThread_TlsIndex` at `0x1016bc3ac`
- `sqldk!SystemThread_TlsIndex` at `0x1016bc4de`
- `sqldk!SystemThread_TlsIndex` at `0x1016bc718`
- `sqldk!SystemThread_TlsIndex` at `0x1016bc858`
- `sqldk!SystemThread_TlsIndex` at `0x1016bc9ba`
- `sqldk!SystemThread_TlsIndex` at `0x1016bcdd7`
- `sqldk!SystemThread_TlsIndex` at `0x1016bcefa`
- `sqldk!SystemThread_TlsIndex` at `0x1016be4e6`
- `sqldk!SystemThread_TlsIndex` at `0x1016be64f`
- `sqldk!SystemThread_TlsIndex` at `0x1016be7ca`
- `sqldk!SystemThread_TlsIndex` at `0x1016beb19`
- `sqldk!SystemThread_TlsOffset` at `0x1016bb031`
- `sqldk!SystemThread_TlsOffset` at `0x1016bb164`
- `sqldk!SystemThread_TlsOffset` at `0x1016bb2b4`
- `sqldk!SystemThread_TlsOffset` at `0x1016bb703`
- `sqldk!SystemThread_TlsOffset` at `0x1016bb823`
- `sqldk!SystemThread_TlsOffset` at `0x1016bbec2`
- `sqldk!SystemThread_TlsOffset` at `0x1016bc3b5`
- `sqldk!SystemThread_TlsOffset` at `0x1016bc4e7`
- `sqldk!SystemThread_TlsOffset` at `0x1016bc721`
- `sqldk!SystemThread_TlsOffset` at `0x1016bc861`
- `sqldk!SystemThread_TlsOffset` at `0x1016bc9c3`
- `sqldk!SystemThread_TlsOffset` at `0x1016bcde0`
- `sqldk!SystemThread_TlsOffset` at `0x1016bcf03`
- `sqldk!SystemThread_TlsOffset` at `0x1016be4ef`
- `sqldk!SystemThread_TlsOffset` at `0x1016be658`
- `sqldk!SystemThread_TlsOffset` at `0x1016be7d3`
- `sqldk!SystemThread_TlsOffset` at `0x1016beb22`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016be51a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016be683`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016be7fe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016beb3b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016be51a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016be683`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016be7fe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016beb3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall BlobManager::RevertFromVersion(
        struct BaseXact **a1,
        __int64 a2,
        __int64 a3,
        struct PageRow *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8,
        char a9,
        __int64 a10,
        PageRef *a11)
{
  struct PageRow *v11; // rsi
  struct BaseXact **v12; // rdi
  __int64 v13; // r15
  struct BaseXact *v14; // r14
  char *v15; // rbx
  char *v16; // rcx
  __int16 v17; // dx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  char *v20; // rdi
  int *v21; // r14
  int v22; // edx
  int *v23; // r13
  _QWORD *v24; // r12
  _BYTE *v25; // rcx
  __int16 v26; // ax
  _WORD *v27; // r14
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // edx
  unsigned int *v31; // r15
  __int64 v32; // rax
  __int64 v33; // rcx
  unsigned int v34; // edx
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // r8d
  __int64 v38; // r10
  __int64 v39; // rdx
  unsigned int v40; // ebx
  unsigned int v41; // r9d
  unsigned int v42; // esi
  unsigned int v43; // esi
  unsigned __int16 v44; // dx
  __int64 v45; // rdx
  __int16 v46; // ax
  bool v47; // zf
  int v48; // edx
  char v49; // cl
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // r10
  unsigned __int64 v52; // r11
  unsigned __int64 v53; // r9
  int v54; // eax
  unsigned __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  unsigned int v60; // ecx
  _BYTE *v61; // rax
  int v62; // edx
  __int64 v63; // rdx
  _DWORD *v64; // rsi
  __int64 v65; // rax
  int v66; // ebx
  __int16 v67; // di
  __int64 v68; // rdx
  int v69; // ebx
  __int64 Lsn; // rdi
  __int64 v71; // rsi
  char v72; // r14
  __int64 v73; // rax
  __int64 v74; // rbx
  char *v75; // rcx
  __int64 v76; // rcx
  unsigned int v77; // eax
  __int64 v78; // rdi
  struct PageRow *v79; // rdi
  char *v80; // rcx
  __int64 v81; // rax
  struct CSessionTraceFlags *v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  unsigned int v85; // ebx
  __int64 v86; // rax
  unsigned int v87; // ecx
  unsigned int v88; // ecx
  const struct UpdateSequenceMarker **v89; // rbx
  __int64 v90; // rbx
  __int64 v91; // rcx
  __int64 v92; // rax
  struct CSessionTraceFlags *v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rdi
  __int64 v96; // rcx
  unsigned int v97; // ebx
  __int64 v98; // rax
  __int64 v99; // rax
  struct CSessionTraceFlags *v100; // rcx
  HANDLE ProcessHeap; // rax
  CTracePrintStream *v102; // rax
  CTracePrintStream *v103; // rbx
  unsigned int v104; // r11d
  unsigned __int16 v105; // r9
  __int64 v106; // rax
  __int64 v107; // rcx
  unsigned int v108; // r10d
  __int64 v109; // rax
  __int64 v110; // rcx
  __int64 v111; // rax
  __int64 v112; // rcx
  _BYTE *v113; // rdx
  unsigned int v114; // ebx
  unsigned int v115; // esi
  unsigned int v116; // esi
  unsigned __int16 v117; // dx
  _BYTE *v118; // rdx
  __int16 v119; // ax
  unsigned __int64 v120; // rdx
  unsigned __int64 v121; // r10
  unsigned __int64 v122; // r11
  unsigned __int64 v123; // r9
  int v124; // eax
  __int64 v125; // rax
  __int64 v126; // rcx
  __int64 v127; // rax
  __int64 v128; // rcx
  unsigned int v129; // r13d
  char v130; // cl
  __int16 v131; // r9
  char v132; // cl
  char v133; // al
  __int64 v134; // rbx
  struct BaseXact *v135; // rax
  __int64 v136; // rdx
  __int16 v138; // r11
  _OWORD *v139; // rbx
  int v140; // r12d
  int v141; // ecx
  unsigned __int8 *v142; // r14
  char v143; // al
  char v144; // al
  __int16 v145; // dx
  int v146; // ecx
  __int64 v147; // rcx
  __int64 v148; // r15
  unsigned __int8 *v149; // r8
  unsigned __int8 v150; // al
  int v151; // esi
  _BYTE *v152; // rcx
  unsigned __int8 v153; // dl
  __int16 v154; // ax
  __int16 v155; // ax
  __int16 v156; // cx
  unsigned __int16 v157; // cx
  unsigned int v158; // eax
  unsigned __int8 *v159; // rax
  __int16 v160; // cx
  PageComprInfoCache *v161; // rcx
  int v162; // esi
  unsigned __int8 *v163; // r8
  unsigned __int8 v164; // al
  unsigned __int16 v165; // ax
  __int16 v166; // cx
  int v167; // ecx
  unsigned int v168; // ecx
  unsigned int v169; // ecx
  int v170; // eax
  char v171; // cl
  char v172; // al
  __int64 v173; // rbx
  __int64 v174; // rdx
  __int64 v175; // r15
  struct BaseXact *v176; // r13
  PageRef *v177; // rbx
  int v178; // eax
  __int64 v179; // rdx
  int v180; // ecx
  int v181; // ecx
  HoBtAccess *v182; // rsi
  _QWORD *v183; // rbx
  __int64 v184; // rdi
  __int64 v185; // rax
  __int64 v186; // rcx
  __int64 v187; // rcx
  __int64 v188; // rbx
  _QWORD *v189; // rbx
  __int64 v190; // rdi
  __int64 v191; // rax
  __int64 v192; // rcx
  __int64 v193; // rcx
  unsigned __int64 v194; // rdx
  __int64 v195; // rbx
  _QWORD *v196; // rbx
  __int64 v197; // rdi
  __int64 v198; // rax
  __int64 v199; // rcx
  __int64 v200; // rcx
  _BYTE *v201; // rax
  char v202; // cl
  char v203; // al
  __int64 v204; // rax
  __int64 v205; // rcx
  __int64 v206; // rbx
  struct Worker *v207; // rcx
  struct Record *v208; // [rsp+20h] [rbp-2CF8h]
  int v209; // [rsp+30h] [rbp-2CE8h]
  int v210; // [rsp+38h] [rbp-2CE0h]
  int v211; // [rsp+40h] [rbp-2CD8h]
  int v212; // [rsp+64h] [rbp-2CB4h]
  int v213; // [rsp+68h] [rbp-2CB0h]
  char v214; // [rsp+6Eh] [rbp-2CAAh]
  unsigned int v215; // [rsp+70h] [rbp-2CA8h]
  char *v216; // [rsp+78h] [rbp-2CA0h]
  struct XDES *v217; // [rsp+80h] [rbp-2C98h]
  FixedVarRecord *v218; // [rsp+98h] [rbp-2C80h]
  int v219; // [rsp+A0h] [rbp-2C78h]
  int v220; // [rsp+A4h] [rbp-2C74h] BYREF
  struct PageRow *v221; // [rsp+A8h] [rbp-2C70h]
  PageRef *v222; // [rsp+B0h] [rbp-2C68h]
  __int128 v223; // [rsp+B8h] [rbp-2C60h] BYREF
  __int64 v224; // [rsp+C8h] [rbp-2C50h]
  char v225; // [rsp+D0h] [rbp-2C48h]
  char v226; // [rsp+D1h] [rbp-2C47h]
  char v227; // [rsp+D2h] [rbp-2C46h]
  char v228; // [rsp+D3h] [rbp-2C45h]
  char v229; // [rsp+D4h] [rbp-2C44h]
  char v230; // [rsp+D5h] [rbp-2C43h]
  char v231; // [rsp+D6h] [rbp-2C42h]
  char v232; // [rsp+D7h] [rbp-2C41h]
  char v233; // [rsp+D8h] [rbp-2C40h]
  char v234; // [rsp+D9h] [rbp-2C3Fh]
  char v235; // [rsp+DAh] [rbp-2C3Eh]
  char v236; // [rsp+DBh] [rbp-2C3Dh]
  char v237; // [rsp+DCh] [rbp-2C3Ch]
  bool v238; // [rsp+DDh] [rbp-2C3Bh]
  char v239; // [rsp+DEh] [rbp-2C3Ah]
  bool v240; // [rsp+DFh] [rbp-2C39h]
  char v241; // [rsp+E0h] [rbp-2C38h]
  bool v242; // [rsp+E1h] [rbp-2C37h]
  char v243; // [rsp+E2h] [rbp-2C36h]
  __int128 v244; // [rsp+E8h] [rbp-2C30h] BYREF
  __int64 v245; // [rsp+F8h] [rbp-2C20h]
  char v246; // [rsp+100h] [rbp-2C18h]
  char v247; // [rsp+101h] [rbp-2C17h]
  char v248; // [rsp+102h] [rbp-2C16h]
  int v249; // [rsp+108h] [rbp-2C10h]
  char v250; // [rsp+110h] [rbp-2C08h]
  char v251; // [rsp+111h] [rbp-2C07h]
  char v252; // [rsp+112h] [rbp-2C06h]
  char v253; // [rsp+113h] [rbp-2C05h]
  char v254; // [rsp+114h] [rbp-2C04h]
  unsigned int v255; // [rsp+118h] [rbp-2C00h]
  int v256; // [rsp+120h] [rbp-2BF8h]
  char v257; // [rsp+128h] [rbp-2BF0h]
  char v258; // [rsp+129h] [rbp-2BEFh]
  char v259; // [rsp+12Ah] [rbp-2BEEh]
  char v260; // [rsp+12Bh] [rbp-2BEDh]
  unsigned int v261; // [rsp+12Ch] [rbp-2BECh]
  __int128 v262; // [rsp+130h] [rbp-2BE8h] BYREF
  __int64 v263; // [rsp+140h] [rbp-2BD8h]
  char *v264; // [rsp+148h] [rbp-2BD0h] BYREF
  int v265; // [rsp+150h] [rbp-2BC8h] BYREF
  __int16 v266; // [rsp+154h] [rbp-2BC4h]
  int v267; // [rsp+156h] [rbp-2BC2h] BYREF
  __int16 v268; // [rsp+15Ah] [rbp-2BBEh]
  int v269; // [rsp+15Ch] [rbp-2BBCh] BYREF
  __int16 v270; // [rsp+160h] [rbp-2BB8h]
  __int64 v271; // [rsp+168h] [rbp-2BB0h]
  int v272; // [rsp+170h] [rbp-2BA8h]
  unsigned int v273; // [rsp+174h] [rbp-2BA4h]
  __int64 v274; // [rsp+178h] [rbp-2BA0h] BYREF
  int v275; // [rsp+180h] [rbp-2B98h] BYREF
  __int16 v276; // [rsp+184h] [rbp-2B94h]
  int v277; // [rsp+188h] [rbp-2B90h] BYREF
  __int16 v278; // [rsp+18Ch] [rbp-2B8Ch]
  int v279; // [rsp+190h] [rbp-2B88h]
  __int16 v280; // [rsp+194h] [rbp-2B84h]
  int v281; // [rsp+198h] [rbp-2B80h] BYREF
  __int16 v282; // [rsp+19Ch] [rbp-2B7Ch]
  HoBtAccess *v283; // [rsp+1A0h] [rbp-2B78h]
  __int64 v284; // [rsp+1A8h] [rbp-2B70h]
  __int64 v285; // [rsp+1B0h] [rbp-2B68h]
  __int64 v286; // [rsp+1B8h] [rbp-2B60h]
  struct BaseXact *v287; // [rsp+1C0h] [rbp-2B58h]
  __int64 v288; // [rsp+1C8h] [rbp-2B50h] BYREF
  __int16 v289; // [rsp+1D0h] [rbp-2B48h]
  int v290; // [rsp+1D8h] [rbp-2B40h]
  int v291; // [rsp+1DCh] [rbp-2B3Ch]
  int v292; // [rsp+1E0h] [rbp-2B38h]
  int v293; // [rsp+1E4h] [rbp-2B34h]
  char v294[8]; // [rsp+1E8h] [rbp-2B30h] BYREF
  char v295[8]; // [rsp+1F0h] [rbp-2B28h] BYREF
  _OWORD *v296; // [rsp+1F8h] [rbp-2B20h]
  __int64 v297; // [rsp+200h] [rbp-2B18h]
  __int16 v298; // [rsp+208h] [rbp-2B10h]
  __int16 v299; // [rsp+20Ch] [rbp-2B0Ch]
  signed __int32 v300; // [rsp+210h] [rbp-2B08h]
  __int16 v301; // [rsp+214h] [rbp-2B04h]
  __int16 v302; // [rsp+218h] [rbp-2B00h]
  __int16 v303; // [rsp+21Ch] [rbp-2AFCh]
  int v304; // [rsp+220h] [rbp-2AF8h] BYREF
  __int16 v305; // [rsp+224h] [rbp-2AF4h]
  int v306; // [rsp+228h] [rbp-2AF0h] BYREF
  __int16 v307; // [rsp+22Ch] [rbp-2AECh]
  int v308; // [rsp+230h] [rbp-2AE8h] BYREF
  __int16 v309; // [rsp+234h] [rbp-2AE4h]
  unsigned __int16 v310; // [rsp+238h] [rbp-2AE0h]
  unsigned __int16 v311; // [rsp+23Ch] [rbp-2ADCh]
  __int16 v312; // [rsp+240h] [rbp-2AD8h]
  __int16 v313; // [rsp+248h] [rbp-2AD0h]
  unsigned __int16 v314; // [rsp+24Ch] [rbp-2ACCh]
  unsigned __int16 v315; // [rsp+250h] [rbp-2AC8h]
  unsigned __int16 v316; // [rsp+254h] [rbp-2AC4h]
  int v317; // [rsp+258h] [rbp-2AC0h]
  int v318; // [rsp+25Ch] [rbp-2ABCh]
  int v319; // [rsp+260h] [rbp-2AB8h]
  int v320; // [rsp+264h] [rbp-2AB4h]
  char v321[8]; // [rsp+268h] [rbp-2AB0h] BYREF
  char v322[8]; // [rsp+270h] [rbp-2AA8h] BYREF
  char v323[8]; // [rsp+278h] [rbp-2AA0h] BYREF
  int v324; // [rsp+280h] [rbp-2A98h]
  __int16 v325; // [rsp+284h] [rbp-2A94h]
  __int16 v326; // [rsp+288h] [rbp-2A90h]
  __int16 v327; // [rsp+28Ch] [rbp-2A8Ch]
  __int64 v328; // [rsp+290h] [rbp-2A88h]
  unsigned __int16 *v329; // [rsp+298h] [rbp-2A80h]
  unsigned __int64 v330; // [rsp+2A0h] [rbp-2A78h]
  __int64 v331; // [rsp+2A8h] [rbp-2A70h]
  __int16 *v332; // [rsp+2B0h] [rbp-2A68h]
  int v333; // [rsp+2C0h] [rbp-2A58h] BYREF
  __int16 v334; // [rsp+2C4h] [rbp-2A54h]
  int v335; // [rsp+2C8h] [rbp-2A50h]
  int v336; // [rsp+2CCh] [rbp-2A4Ch] BYREF
  __int16 v337; // [rsp+2D0h] [rbp-2A48h]
  __int16 v338; // [rsp+2D2h] [rbp-2A46h]
  __int64 v339; // [rsp+2D8h] [rbp-2A40h]
  __int64 v340; // [rsp+2E0h] [rbp-2A38h]
  __int64 v341; // [rsp+2E8h] [rbp-2A30h]
  _BYTE *v342; // [rsp+2F0h] [rbp-2A28h]
  _BYTE *v343; // [rsp+2F8h] [rbp-2A20h]
  char *v344; // [rsp+300h] [rbp-2A18h]
  char v345; // [rsp+308h] [rbp-2A10h]
  char v346; // [rsp+309h] [rbp-2A0Fh]
  char v347; // [rsp+30Ah] [rbp-2A0Eh]
  int v348; // [rsp+310h] [rbp-2A08h]
  unsigned int v349; // [rsp+318h] [rbp-2A00h]
  unsigned int v350; // [rsp+31Ch] [rbp-29FCh]
  unsigned int v351; // [rsp+320h] [rbp-29F8h]
  unsigned int v352; // [rsp+324h] [rbp-29F4h]
  unsigned int v353; // [rsp+328h] [rbp-29F0h]
  int v354; // [rsp+330h] [rbp-29E8h]
  int v355; // [rsp+334h] [rbp-29E4h]
  int v356; // [rsp+338h] [rbp-29E0h]
  int v357; // [rsp+33Ch] [rbp-29DCh]
  unsigned int v358; // [rsp+340h] [rbp-29D8h]
  int v359; // [rsp+344h] [rbp-29D4h]
  int v360; // [rsp+348h] [rbp-29D0h]
  int v361; // [rsp+34Ch] [rbp-29CCh]
  int v362; // [rsp+350h] [rbp-29C8h]
  BOOL v363; // [rsp+358h] [rbp-29C0h]
  int v364; // [rsp+35Ch] [rbp-29BCh]
  int v365; // [rsp+360h] [rbp-29B8h]
  int v366; // [rsp+364h] [rbp-29B4h]
  int v367; // [rsp+368h] [rbp-29B0h]
  int v368; // [rsp+36Ch] [rbp-29ACh]
  int v369; // [rsp+370h] [rbp-29A8h]
  unsigned int v370; // [rsp+378h] [rbp-29A0h]
  unsigned int v371; // [rsp+37Ch] [rbp-299Ch]
  unsigned int v372; // [rsp+380h] [rbp-2998h]
  unsigned int v373; // [rsp+388h] [rbp-2990h]
  int v374; // [rsp+390h] [rbp-2988h]
  int v375; // [rsp+394h] [rbp-2984h]
  unsigned int v376; // [rsp+398h] [rbp-2980h]
  int v377; // [rsp+39Ch] [rbp-297Ch]
  int v378; // [rsp+3A0h] [rbp-2978h]
  int v379; // [rsp+3A4h] [rbp-2974h]
  int v380; // [rsp+3A8h] [rbp-2970h]
  int v381; // [rsp+3B0h] [rbp-2968h]
  int v382; // [rsp+3B8h] [rbp-2960h]
  int v383; // [rsp+3BCh] [rbp-295Ch]
  int v384; // [rsp+3C0h] [rbp-2958h]
  int v385; // [rsp+3C4h] [rbp-2954h]
  int v386; // [rsp+3C8h] [rbp-2950h]
  int v387; // [rsp+3CCh] [rbp-294Ch]
  int v388; // [rsp+3D0h] [rbp-2948h]
  int v389; // [rsp+3D4h] [rbp-2944h]
  int v390; // [rsp+3D8h] [rbp-2940h]
  int v391; // [rsp+3DCh] [rbp-293Ch]
  __int64 v392; // [rsp+3E0h] [rbp-2938h]
  __int64 v393; // [rsp+3E8h] [rbp-2930h]
  __int64 v394; // [rsp+3F0h] [rbp-2928h]
  unsigned __int64 v395; // [rsp+3F8h] [rbp-2920h] BYREF
  __int64 v396; // [rsp+400h] [rbp-2918h]
  __int64 v397; // [rsp+408h] [rbp-2910h]
  struct CSessionTraceFlags *v398; // [rsp+410h] [rbp-2908h]
  struct CSessionTraceFlags *v399; // [rsp+418h] [rbp-2900h]
  struct CSessionTraceFlags *v400; // [rsp+420h] [rbp-28F8h]
  CTracePrintStream *v401; // [rsp+428h] [rbp-28F0h]
  __int64 v402; // [rsp+430h] [rbp-28E8h]
  __int64 v403; // [rsp+438h] [rbp-28E0h]
  __int64 v404; // [rsp+440h] [rbp-28D8h]
  unsigned __int64 v405; // [rsp+448h] [rbp-28D0h] BYREF
  __int64 v406; // [rsp+450h] [rbp-28C8h]
  __int64 v407; // [rsp+458h] [rbp-28C0h]
  __int64 v408; // [rsp+460h] [rbp-28B8h]
  _QWORD *v409; // [rsp+468h] [rbp-28B0h]
  __int64 v410; // [rsp+470h] [rbp-28A8h]
  _QWORD *v411; // [rsp+478h] [rbp-28A0h]
  __int64 v412; // [rsp+480h] [rbp-2898h]
  _QWORD *v413; // [rsp+488h] [rbp-2890h]
  _QWORD v414[2]; // [rsp+490h] [rbp-2888h] BYREF
  int v415; // [rsp+4A0h] [rbp-2878h]
  int v416; // [rsp+4A4h] [rbp-2874h]
  int v417; // [rsp+4A8h] [rbp-2870h]
  int v418; // [rsp+4ACh] [rbp-286Ch]
  int v419; // [rsp+4B0h] [rbp-2868h]
  _BYTE v420[4]; // [rsp+4C8h] [rbp-2850h] BYREF
  __int64 v421; // [rsp+4CCh] [rbp-284Ch]
  _QWORD *v422; // [rsp+4E0h] [rbp-2838h]
  __int64 v423; // [rsp+4E8h] [rbp-2830h]
  __int64 v424; // [rsp+4F0h] [rbp-2828h]
  __int64 v425; // [rsp+4F8h] [rbp-2820h]
  __int64 v426; // [rsp+500h] [rbp-2818h]
  _QWORD *v427; // [rsp+508h] [rbp-2810h]
  __int64 v428; // [rsp+510h] [rbp-2808h]
  __int64 v429; // [rsp+518h] [rbp-2800h]
  __int64 v430; // [rsp+520h] [rbp-27F8h]
  __int64 v431; // [rsp+528h] [rbp-27F0h]
  __int16 *v432; // [rsp+530h] [rbp-27E8h]
  __int64 v433; // [rsp+538h] [rbp-27E0h]
  char *v434; // [rsp+540h] [rbp-27D8h]
  __int64 v435; // [rsp+548h] [rbp-27D0h]
  struct RecVersioningInfo *VersioningInfo; // [rsp+550h] [rbp-27C8h]
  __int64 *v437; // [rsp+558h] [rbp-27C0h]
  _QWORD *v438; // [rsp+560h] [rbp-27B8h]
  __int64 v439; // [rsp+568h] [rbp-27B0h]
  __int64 v440; // [rsp+570h] [rbp-27A8h]
  __int64 v441; // [rsp+578h] [rbp-27A0h]
  __int64 v442; // [rsp+580h] [rbp-2798h]
  _QWORD *v443; // [rsp+588h] [rbp-2790h]
  __int64 v444; // [rsp+590h] [rbp-2788h]
  __int64 v445; // [rsp+598h] [rbp-2780h]
  __int64 v446; // [rsp+5A0h] [rbp-2778h]
  __int64 v447; // [rsp+5A8h] [rbp-2770h]
  _BYTE *v448; // [rsp+5B0h] [rbp-2768h]
  char *v449; // [rsp+5B8h] [rbp-2760h]
  __int128 *v450; // [rsp+5C0h] [rbp-2758h]
  __int64 v451; // [rsp+5C8h] [rbp-2750h]
  int *v452; // [rsp+5D0h] [rbp-2748h]
  int *v453; // [rsp+5D8h] [rbp-2740h]
  __int64 v454; // [rsp+5E0h] [rbp-2738h]
  __int64 v455; // [rsp+5E8h] [rbp-2730h]
  __int64 v456; // [rsp+5F0h] [rbp-2728h]
  __int64 v457; // [rsp+5F8h] [rbp-2720h]
  __int64 v458; // [rsp+600h] [rbp-2718h]
  __int64 v459; // [rsp+608h] [rbp-2710h]
  char *v460; // [rsp+610h] [rbp-2708h]
  __int64 v461; // [rsp+618h] [rbp-2700h]
  __int64 v462; // [rsp+620h] [rbp-26F8h]
  char *v463; // [rsp+628h] [rbp-26F0h]
  _QWORD *v464; // [rsp+630h] [rbp-26E8h]
  _QWORD *v465; // [rsp+638h] [rbp-26E0h]
  _QWORD *v466; // [rsp+640h] [rbp-26D8h]
  __int64 v467; // [rsp+648h] [rbp-26D0h]
  __int64 v468; // [rsp+650h] [rbp-26C8h]
  struct CSessionTraceFlags *v469; // [rsp+658h] [rbp-26C0h]
  __int64 v470; // [rsp+660h] [rbp-26B8h]
  int *v471; // [rsp+668h] [rbp-26B0h]
  __int64 v472; // [rsp+670h] [rbp-26A8h]
  int *v473; // [rsp+678h] [rbp-26A0h]
  __int64 v474; // [rsp+680h] [rbp-2698h]
  signed __int64 v475; // [rsp+688h] [rbp-2690h]
  signed __int64 v476; // [rsp+690h] [rbp-2688h]
  char *v477; // [rsp+698h] [rbp-2680h]
  int *v478; // [rsp+6A0h] [rbp-2678h]
  _QWORD *v479; // [rsp+6A8h] [rbp-2670h]
  _QWORD *v480; // [rsp+6B0h] [rbp-2668h]
  _QWORD *v481; // [rsp+6B8h] [rbp-2660h]
  __int64 v482; // [rsp+6C0h] [rbp-2658h]
  __int64 v483; // [rsp+6C8h] [rbp-2650h]
  struct CSessionTraceFlags *v484; // [rsp+6D0h] [rbp-2648h]
  __int64 v485; // [rsp+6D8h] [rbp-2640h]
  _QWORD *v486; // [rsp+6E0h] [rbp-2638h]
  _QWORD *v487; // [rsp+6E8h] [rbp-2630h]
  _QWORD *v488; // [rsp+6F0h] [rbp-2628h]
  __int64 v489; // [rsp+6F8h] [rbp-2620h]
  __int64 v490; // [rsp+700h] [rbp-2618h]
  struct CSessionTraceFlags *v491; // [rsp+708h] [rbp-2610h]
  CTracePrintStream *v492; // [rsp+710h] [rbp-2608h]
  CTracePrintStream *v493; // [rsp+718h] [rbp-2600h]
  CTracePrintStream *v494; // [rsp+720h] [rbp-25F8h]
  _QWORD *v495; // [rsp+728h] [rbp-25F0h]
  __int64 v496; // [rsp+730h] [rbp-25E8h]
  __int64 v497; // [rsp+738h] [rbp-25E0h]
  __int64 v498; // [rsp+740h] [rbp-25D8h]
  __int64 v499; // [rsp+748h] [rbp-25D0h]
  _QWORD *v500; // [rsp+750h] [rbp-25C8h]
  __int64 v501; // [rsp+758h] [rbp-25C0h]
  __int64 v502; // [rsp+760h] [rbp-25B8h]
  __int64 v503; // [rsp+768h] [rbp-25B0h]
  __int64 v504; // [rsp+770h] [rbp-25A8h]
  _QWORD *v505; // [rsp+778h] [rbp-25A0h]
  __int64 v506; // [rsp+780h] [rbp-2598h]
  __int64 v507; // [rsp+788h] [rbp-2590h]
  __int64 v508; // [rsp+790h] [rbp-2588h]
  __int64 v509; // [rsp+798h] [rbp-2580h]
  __int16 *v510; // [rsp+7A0h] [rbp-2578h]
  _BYTE *v511; // [rsp+7A8h] [rbp-2570h]
  char *v512; // [rsp+7B0h] [rbp-2568h]
  _BYTE *v513; // [rsp+7B8h] [rbp-2560h]
  struct RecVersioningInfo *v514; // [rsp+7C0h] [rbp-2558h]
  __int64 *v515; // [rsp+7C8h] [rbp-2550h]
  _QWORD *v516; // [rsp+7D0h] [rbp-2548h]
  __int64 v517; // [rsp+7D8h] [rbp-2540h]
  __int64 v518; // [rsp+7E0h] [rbp-2538h]
  __int64 v519; // [rsp+7E8h] [rbp-2530h]
  __int64 v520; // [rsp+7F0h] [rbp-2528h]
  _QWORD *v521; // [rsp+7F8h] [rbp-2520h]
  __int64 v522; // [rsp+800h] [rbp-2518h]
  __int64 v523; // [rsp+808h] [rbp-2510h]
  __int64 v524; // [rsp+810h] [rbp-2508h]
  __int64 v525; // [rsp+818h] [rbp-2500h]
  _BYTE *v526; // [rsp+820h] [rbp-24F8h]
  int *v527; // [rsp+828h] [rbp-24F0h]
  int *v528; // [rsp+830h] [rbp-24E8h]
  _BYTE *v529; // [rsp+838h] [rbp-24E0h]
  __int64 *v530; // [rsp+840h] [rbp-24D8h]
  int *v531; // [rsp+848h] [rbp-24D0h]
  _DWORD *v532; // [rsp+850h] [rbp-24C8h]
  int *v533; // [rsp+858h] [rbp-24C0h]
  _BYTE *v534; // [rsp+860h] [rbp-24B8h]
  __int64 v535; // [rsp+868h] [rbp-24B0h]
  __int64 *v536; // [rsp+870h] [rbp-24A8h]
  _BYTE *v537; // [rsp+878h] [rbp-24A0h]
  int *v538; // [rsp+880h] [rbp-2498h]
  int *v539; // [rsp+888h] [rbp-2490h]
  int *v540; // [rsp+890h] [rbp-2488h]
  __int64 v541; // [rsp+898h] [rbp-2480h]
  _QWORD *v542; // [rsp+8A0h] [rbp-2478h]
  _QWORD *v543; // [rsp+8A8h] [rbp-2470h]
  __int64 v544; // [rsp+8B0h] [rbp-2468h]
  __int64 v545; // [rsp+8B8h] [rbp-2460h]
  __int64 v546; // [rsp+8C0h] [rbp-2458h]
  volatile signed __int64 *v547; // [rsp+8C8h] [rbp-2450h]
  signed __int64 v548; // [rsp+8D0h] [rbp-2448h]
  __int64 v549; // [rsp+8D8h] [rbp-2440h]
  __int64 v550; // [rsp+8E0h] [rbp-2438h]
  _QWORD *v551; // [rsp+8E8h] [rbp-2430h]
  __int64 v552; // [rsp+8F0h] [rbp-2428h]
  __int64 v553; // [rsp+8F8h] [rbp-2420h]
  __int64 v554; // [rsp+900h] [rbp-2418h]
  volatile signed __int64 *v555; // [rsp+908h] [rbp-2410h]
  signed __int64 v556; // [rsp+910h] [rbp-2408h]
  __int64 v557; // [rsp+918h] [rbp-2400h]
  __int64 v558; // [rsp+920h] [rbp-23F8h]
  _QWORD *v559; // [rsp+928h] [rbp-23F0h]
  __int64 v560; // [rsp+930h] [rbp-23E8h]
  __int64 v561; // [rsp+938h] [rbp-23E0h]
  __int64 v562; // [rsp+940h] [rbp-23D8h]
  _BYTE *v563; // [rsp+948h] [rbp-23D0h]
  __int64 v564; // [rsp+950h] [rbp-23C8h]
  __int64 v565; // [rsp+958h] [rbp-23C0h]
  char *v566; // [rsp+960h] [rbp-23B8h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+968h] [rbp-23B0h]
  __int64 v568; // [rsp+970h] [rbp-23A8h]
  __int64 v569; // [rsp+978h] [rbp-23A0h]
  __int128 v570; // [rsp+980h] [rbp-2398h] BYREF
  __int64 v571; // [rsp+990h] [rbp-2388h]
  __int128 v572; // [rsp+9A0h] [rbp-2378h] BYREF
  __int64 v573; // [rsp+9B0h] [rbp-2368h]
  __int128 v574; // [rsp+9C0h] [rbp-2358h] BYREF
  __int64 v575; // [rsp+9D0h] [rbp-2348h]
  __int128 v576; // [rsp+9E0h] [rbp-2338h] BYREF
  __int64 v577; // [rsp+9F0h] [rbp-2328h]
  __int64 v578; // [rsp+A00h] [rbp-2318h]
  char v579[40]; // [rsp+A08h] [rbp-2310h] BYREF
  _BYTE v580[96]; // [rsp+A30h] [rbp-22E8h] BYREF
  int v581; // [rsp+A90h] [rbp-2288h] BYREF
  int v582; // [rsp+A94h] [rbp-2284h]
  int v583; // [rsp+A98h] [rbp-2280h]
  __int16 v584; // [rsp+A9Ch] [rbp-227Ch]
  char v585; // [rsp+A9Eh] [rbp-227Ah]
  __int16 v586; // [rsp+AA0h] [rbp-2278h] BYREF
  unsigned __int16 v587; // [rsp+AA2h] [rbp-2276h]
  int v588; // [rsp+AA4h] [rbp-2274h]
  unsigned __int8 *v589; // [rsp+AA8h] [rbp-2270h]
  _OWORD *v590; // [rsp+AB0h] [rbp-2268h]
  __int16 v591; // [rsp+AB8h] [rbp-2260h]
  __int16 v592; // [rsp+ABAh] [rbp-225Eh]
  __int16 v593; // [rsp+ABCh] [rbp-225Ch]
  __int64 v594; // [rsp+ABEh] [rbp-225Ah]
  _BYTE v595[10]; // [rsp+AC6h] [rbp-2252h] BYREF
  int v596; // [rsp+AD0h] [rbp-2248h]
  int v597; // [rsp+AD4h] [rbp-2244h]
  _OWORD v598[7]; // [rsp+AD8h] [rbp-2240h] BYREF
  __int64 v599; // [rsp+B48h] [rbp-21D0h]
  _DWORD v600[2]; // [rsp+B50h] [rbp-21C8h] BYREF
  __int16 v601; // [rsp+B58h] [rbp-21C0h]
  __int16 v602; // [rsp+B60h] [rbp-21B8h] BYREF
  __int16 v603; // [rsp+B62h] [rbp-21B6h] BYREF
  unsigned int v604; // [rsp+B64h] [rbp-21B4h]
  _BYTE *v605; // [rsp+B68h] [rbp-21B0h]
  __int64 v606; // [rsp+B70h] [rbp-21A8h]
  unsigned int v607; // [rsp+B78h] [rbp-21A0h]
  unsigned __int16 v608; // [rsp+B7Ch] [rbp-219Ch]
  unsigned __int64 v609; // [rsp+B7Eh] [rbp-219Ah]
  _TBYTE v610; // [rsp+B86h] [rbp-2192h] BYREF
  int v611; // [rsp+B94h] [rbp-2184h]
  unsigned __int8 v612[4]; // [rsp+C10h] [rbp-2108h] BYREF
  int v613; // [rsp+C14h] [rbp-2104h]
  int v614; // [rsp+C18h] [rbp-2100h]
  __int128 v615; // [rsp+C20h] [rbp-20F8h]
  int v616; // [rsp+C30h] [rbp-20E8h]
  __int64 v617; // [rsp+C40h] [rbp-20D8h]
  int v618; // [rsp+C48h] [rbp-20D0h]
  __int64 v619; // [rsp+C50h] [rbp-20C8h]
  _BYTE v620[12]; // [rsp+C60h] [rbp-20B8h] BYREF
  unsigned int v621; // [rsp+C6Ch] [rbp-20ACh]
  char v622; // [rsp+C70h] [rbp-20A8h]
  __int64 v623; // [rsp+C78h] [rbp-20A0h] BYREF
  int v624; // [rsp+C94h] [rbp-2084h]
  char v625; // [rsp+C98h] [rbp-2080h]
  __int64 v626; // [rsp+CA0h] [rbp-2078h] BYREF
  _BYTE v627[4]; // [rsp+CB0h] [rbp-2068h] BYREF
  char v628; // [rsp+CB4h] [rbp-2064h] BYREF
  unsigned __int8 v629[8096]; // [rsp+D30h] [rbp-1FE8h] BYREF

  v564 = -2;
  v11 = a4;
  v221 = a4;
  v286 = a3;
  v271 = a2;
  v12 = a1;
  v283 = (HoBtAccess *)a1;
  v13 = a5;
  v297 = a5;
  v285 = a6;
  v328 = a10;
  v222 = a11;
  v215 = 0;
  v14 = a1[6];
  v287 = v14;
  v414[1] = a11;
  v274 = 0;
  v421 = 0;
  v15 = (char *)a4 + 2;
  v264 = (char *)a4 + 2;
  v16 = (char *)a4 + 2;
  if ( *(_WORD *)a4 )
    CDRecord::GetXdesTs(v16, &v281);
  else
    FixedVarRecord::GetXdesTs(v16, &v281);
  v306 = v281;
  v307 = v282;
  v17 = *(_WORD *)v11;
  v18 = **((unsigned __int8 **)v11 + 1);
  if ( *(_WORD *)v11 )
    v19 = v18 >> 1;
  else
    v19 = v18 >> 6;
  v415 = v19 & 1;
  if ( (v19 & 1) != 0 )
  {
    v300 = 0;
    v301 = 0;
    if ( v282 || v281 )
    {
      if ( v17 )
        CDRecord::GetVersionRecPtr(v15, v321);
      else
        FixedVarRecord::GetVersionRecPtr(v15, v321);
      v566 = v321;
      if ( (unsigned int)XdesMgr::GetRowAbortState((char *)v14 + 6600, &v306, v321) )
      {
        if ( *((_BYTE *)v14 + 8272) )
        {
          scierrlogwithstate(0x298u, 10, 3);
          DBTABLE::RaiseReadonlyDbError(*((DBTABLE **)v14 + 214));
        }
        if ( *(_WORD *)v11 )
        {
          v449 = v15;
          v60 = *(_DWORD *)(v15 + 2);
          if ( !v60 )
          {
            CDRecord::Resize((CDRecord *)v15);
            v60 = *(_DWORD *)(v15 + 2);
          }
          if ( v60 < 9 )
          {
            v61 = *(_BYTE **)(v15 + 6);
            v47 = (*v61 & 0x1C) == 0;
            v62 = *v61 & 0x1C;
            v357 = v62;
            if ( v47 || v62 == 12 )
              v60 = 9;
          }
          v358 = v60;
          v255 = v60;
        }
        else
        {
          v20 = v15;
          v216 = v15;
          v21 = (int *)(v15 + 2);
          v218 = (FixedVarRecord *)(v15 + 2);
          if ( !*(_DWORD *)(v15 + 2) )
          {
            v212 = 0;
            *(_WORD *)v15 = 0;
            v22 = *(_DWORD *)(v15 + 14);
            v23 = (int *)(v15 + 18);
            *(_DWORD *)(v15 + 18) = v22;
            v24 = v15 + 6;
            v25 = *(_BYTE **)(v15 + 6);
            if ( (*v25 & 0x10) != 0 )
            {
              v22 += (((unsigned int)*(unsigned __int16 *)&v25[*(unsigned int *)(v15 + 14)] + 7) >> 3) + 2;
              *v23 = v22;
              v25 = (_BYTE *)*v24;
            }
            if ( (*v25 & 0x20) != 0 )
            {
              v332 = (__int16 *)&v25[v22];
              v26 = *v332;
              v27 = v15 + 26;
              *((_WORD *)v15 + 13) = *v332;
              if ( !v26 )
              {
                v212 = 1;
                if ( byte_10316E8D7 || (v234 = qword_10317B120, (qword_10317B120 & 1) != 0) )
                {
                  v416 = 88;
                  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v568 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v578 = v568;
                  v28 = *(_QWORD *)(v568 + 8);
                  v565 = v28;
                  v569 = v28;
                  if ( v28 )
                  {
                    v29 = *(_QWORD *)(v28 + 96);
                    v392 = v29;
                    if ( v29 && *(_BYTE *)(v29 + 1177) )
                    {
                      if ( byte_10316E7C7 || (v246 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                  else
                  {
                    v392 = 0;
                  }
                  v20 = v15;
                }
                RaiseInconsistencyError(*v24, 3);
              }
              v30 = *v23 + 2 * ((unsigned __int16)*v27 + 1);
              v31 = (unsigned int *)(v20 + 22);
              *(_DWORD *)(v20 + 22) = v30;
              if ( v30 > 0x1F9E )
              {
                ++v212;
                if ( byte_10316E8D7 || (v247 = qword_10317B120, (qword_10317B120 & 1) != 0) )
                {
                  v417 = 88;
                  v422 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v423 = v422[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v424 = v423;
                  v32 = *(_QWORD *)(v423 + 8);
                  v425 = v32;
                  v426 = v32;
                  if ( v32 )
                  {
                    v33 = *(_QWORD *)(v32 + 96);
                    v393 = v33;
                    if ( v33 && *(_BYTE *)(v33 + 1177) )
                    {
                      if ( byte_10316E7C7 || (v248 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                  else
                  {
                    v393 = 0;
                  }
                  v20 = v15;
                }
                RaiseInconsistencyError(*v24, 4);
              }
              v327 = v332[(unsigned __int16)*v27];
              v34 = v327 & 0x7FFF;
              *(_DWORD *)v218 = v34;
              if ( *v31 > v34 )
              {
                ++v212;
                if ( byte_10316E8D7 || (v250 = qword_10317B120, (qword_10317B120 & 1) != 0) )
                {
                  v418 = 88;
                  v427 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v428 = v427[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v429 = v428;
                  v35 = *(_QWORD *)(v428 + 8);
                  v430 = v35;
                  v431 = v35;
                  if ( v35 )
                  {
                    v36 = *(_QWORD *)(v35 + 96);
                    v394 = v36;
                    if ( v36 && *(_BYTE *)(v36 + 1177) )
                    {
                      if ( byte_10316E7C7 || (v251 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                  else
                  {
                    v394 = 0;
                  }
                  v20 = v15;
                }
                RaiseInconsistencyError(*v24, 4);
              }
              while ( 1 )
              {
                v37 = (unsigned __int16)*v27;
                v432 = &v332[v37 - 1 + 1];
                if ( *v432 >= 0 )
                {
LABEL_82:
                  v21 = (int *)v218;
                  goto LABEL_84;
                }
                v419 = v37;
                v38 = *v24;
                v39 = *v24 + (unsigned int)*v23;
                v433 = v39;
                if ( v37 == 1 )
                {
                  v40 = *v31;
                }
                else
                {
                  v326 = *(_WORD *)(v39 + 2LL * (v37 - 2) + 2);
                  v40 = v326 & 0x7FFF;
                }
                v41 = *v31;
                v349 = v40;
                v325 = *(_WORD *)(v39 + 2LL * (v37 - 1) + 2);
                v42 = v325 & 0x7FFF;
                v350 = v42;
                if ( v40 < v41 || v42 < v40 )
                {
                  RaiseInconsistencyError(v38, 7);
                  v41 = *v31;
                }
                v43 = v42 - v40;
                v351 = v43;
                v352 = v40;
                if ( v40 < v41 || v40 > *(_DWORD *)v218 )
                {
                  v318 = v212 + 1;
                  v21 = (int *)v218;
                  v15 = v264;
                  v11 = v221;
                  goto LABEL_77;
                }
                v44 = *(_WORD *)(v40 + *v24);
                v314 = v44;
                if ( v44 == 5 )
                  break;
                if ( v44 >= 0x400u )
                {
                  *(_WORD *)v20 |= 1u;
                  v47 = (*v27)-- == 1;
                  if ( !v47 )
                    continue;
                }
                goto LABEL_82;
              }
              *(_WORD *)v20 |= 2u;
              --*v27;
              v353 = v43;
              v434 = v20 + 40;
              *((_WORD *)v20 + 20) = v40;
              v45 = *(_QWORD *)(v20 + 6) + (unsigned __int16)v40;
              v435 = v45;
              v46 = *(_WORD *)(v45 + 2);
              *((_WORD *)v20 + 21) &= 0xC7FFu;
              if ( (v46 & 0x4000) != 0 )
                *((_WORD *)v20 + 21) |= v46 & 0x3800;
              *((_WORD *)v20 + 21) ^= (*(_WORD *)(v45 + 2) ^ *((_WORD *)v20 + 21)) & 0x7FF;
              v21 = (int *)v218;
            }
            else
            {
              *v21 = v22;
              *((_WORD *)v15 + 13) = 0;
              *(_DWORD *)(v15 + 22) = *v23;
            }
LABEL_84:
            if ( (*(_BYTE *)*v24 & 0x40) != 0 )
            {
              *((_DWORD *)v20 + 9) = *v21;
              *v21 += 14;
              VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v20);
              v50 = *(_QWORD *)VersioningInfo;
              v395 = v50;
              v51 = HIDWORD(v50);
              v52 = HIDWORD(v50);
              v53 = HIDWORD(v50);
              v317 = 0;
              if ( ((SHIWORD(v50) ^ ((unsigned int)SHIWORD(v50) >> 1)) & 0x2000) != 0 )
              {
                if ( (v50 & 0x4000000000000000LL) != 0 )
                {
                  LOWORD(v50) = HIWORD(v50) | 0x2000;
                  LOWORD(v53) = v52;
                }
                else
                {
                  LOWORD(v50) = HIWORD(v50) & 0xDFFF;
                  LOWORD(v53) = v51;
                }
              }
              else
              {
                v50 >>= 48;
              }
              v313 = v50;
              v54 = 0;
              if ( (_WORD)v50 == 0xFFFC )
              {
                v437 = (__int64 *)&v395;
                v54 = (unsigned __int16)v53 >> 5;
                v317 = v54;
              }
              *v21 += v54;
            }
            else
            {
              *((_DWORD *)v20 + 9) = 0;
            }
            v55 = *(_QWORD *)(v20 + 28);
            if ( v55 && v55 < *v24 + (unsigned __int64)(unsigned int)*v21 )
            {
              ++v212;
              if ( byte_10316E8D7 || (v252 = qword_10317B120, (qword_10317B120 & 1) != 0) )
              {
                v354 = 88;
                v438 = NtCurrentTeb()->ThreadLocalStoragePointer;
                v439 = v438[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                v440 = v439;
                v56 = *(_QWORD *)(v439 + 8);
                v441 = v56;
                v442 = v56;
                if ( v56 )
                {
                  v57 = *(_QWORD *)(v56 + 96);
                  v396 = v57;
                  if ( v57 && *(_BYTE *)(v57 + 1177) )
                  {
                    if ( byte_10316E7C7 || (v253 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
                else
                {
                  v396 = 0;
                }
                v20 = v216;
              }
              RaiseInconsistencyError(*v24, 18);
            }
            if ( (unsigned int)(*v21 - 1) > 0x3F3B )
            {
              ++v212;
              if ( byte_10316E8D7 || (v257 = qword_10317B120, (qword_10317B120 & 1) != 0) )
              {
                v355 = 88;
                v443 = NtCurrentTeb()->ThreadLocalStoragePointer;
                v444 = v443[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                v445 = v444;
                v58 = *(_QWORD *)(v444 + 8);
                v446 = v58;
                v447 = v58;
                if ( v58 )
                {
                  v59 = *(_QWORD *)(v58 + 96);
                  v397 = v59;
                  if ( v59 && *(_BYTE *)(v59 + 1177) )
                  {
                    if ( byte_10316E7C7 || (v258 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
                else
                {
                  v397 = 0;
                }
                v20 = v216;
              }
              RaiseInconsistencyError(*v24, 5);
            }
            v318 = v212;
            v15 = v264;
            v11 = v221;
          }
LABEL_77:
          v48 = *v21;
          if ( (unsigned int)*v21 < 9 )
          {
            v448 = *(_BYTE **)(v20 + 6);
            v49 = *v448 & 0xE;
            v259 = v49;
            if ( !v49 || v49 == 12 )
              v48 = 9;
          }
          v356 = v48;
          v255 = v48;
          v13 = v297;
          v12 = (struct BaseXact **)v283;
        }
        v602 = -1;
        v605 = 0;
        v604 = 0;
        v609 = 0;
        *(_QWORD *)((char *)&v610 + 2) = 0;
        v606 = 0;
        v611 = -1;
        v273 = 0;
        if ( *(_WORD *)v11 )
          CDRecord::GetVersionRecPtr(v15, v322);
        else
          FixedVarRecord::GetVersionRecPtr(v15, v322);
        v284 = 0;
        v64 = (_DWORD *)v285;
        v219 = *(__int16 *)(v285 + 6);
        v220 = 0;
        v450 = &v223;
        LOWORD(v223) = v223 & 0xC0;
        BYTE2(v223) = 0;
        *((_QWORD *)&v223 + 1) = 0;
        LOBYTE(v224) = v224 & 0xE0;
        if ( a9 )
        {
          v65 = v328;
          if ( !v328 )
          {
            AutoSimpleXact::BeginSubXactNoVersioning(
              (AutoSimpleXact *)&v274,
              L"BlobManager::RevertFromVersion",
              60,
              v12[82],
              0);
            v65 = (*(__int64 (__fastcall **)(__int64, struct BaseXact *))(*(_QWORD *)v274 + 88LL))(v274, v287);
          }
          v12 = (struct BaseXact **)v65;
          v284 = v65;
          LOBYTE(v63) = 1;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v65 + 840LL))(v65, v63);
        }
        v217 = (struct XDES *)v12;
        v214 = (*((__int64 (__fastcall **)(struct BaseXact **))*v12 + 1))(v12);
        if ( !v214 )
        {
          if ( a9 )
          {
            v451 = v13 + 32;
            v66 = *(_DWORD *)(v13 + 32);
            v279 = v66;
            v67 = *(_WORD *)(v13 + 36);
            v280 = v67;
            v452 = &v277;
            v277 = v66;
            v278 = v67;
            v279 = XdesRMReadWrite::AcquireLogicalRevertModLock(v284, 0, &v277);
            if ( v279 < 0 )
            {
              _mm_lfence();
              PageRef::Unlatch(v222);
              v453 = &v275;
              v275 = v66;
              v276 = v67;
              v279 = XdesRMReadWrite::AcquireLogicalRevertModLock(v284, 0xFFFFFFFFLL, &v275);
              LOBYTE(v68) = 35;
              lck_StandardHandler((unsigned int)v279, v68);
              PageRef::Latch(v222, 4, 0xFFFFFFFFLL, v420, 0, 0, 1);
            }
          }
        }
        if ( VersionRecPtr::IsNull((VersionRecPtr *)v322) || VersionRecPtr::IsNullWithSeq((VersionRecPtr *)v322) )
          goto LABEL_342;
        v600[0] = 0;
        v600[1] = 0;
        v601 = 0;
        v69 = *(_WORD *)(v13 + 4) & 0x2000;
        v359 = v69;
        Lsn = Page::GetLsn(v13, v579, 0, 0);
        v454 = Lsn;
        v71 = *((_QWORD *)v217 + 6);
        v331 = v71;
        v72 = *(_BYTE *)(v71 + 7390);
        if ( *(_BYTE *)(v71 + 8272) && (*(_BYTE *)(a7 + 16) & 1) != 0 )
        {
          v455 = v71;
          v456 = *(_QWORD *)(*(_QWORD *)(v71 + 1832) + 24496LL);
          v73 = (*(unsigned int (__fastcall **)(struct XDES *))(*(_QWORD *)v217 + 240LL))(v217)
              ? (*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v217 + 488LL))(v217)
              : (__int64)v217;
          v457 = *(_QWORD *)(v73 + 584);
          v458 = v457;
          if ( !*(_BYTE *)(v457 + 22) )
            ex_raise(39, 48, 16, 2);
        }
        PageRow::Clone((PageRow *)&v602, v221);
        v220 = 1;
        if ( !v69 )
        {
          v225 = (unsigned __int8)byte_10317AD6E >> 3;
          if ( (byte_10317AD6E & 8) != 0 )
            goto LABEL_223;
          v320 = 0;
          v364 = 88;
          v479 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v480 = (_QWORD *)(v479[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v481 = v480;
          v92 = *v480;
          v482 = v92;
          v483 = v92;
          if ( !v92 || (v93 = **(struct CSessionTraceFlags ***)(v92 + 56), (v484 = v93) == 0) )
          {
            v399 = 0;
            goto LABEL_228;
          }
          v399 = v93;
          v320 = CSessionTraceFlags::CheckSessionTraceInternal(v93, 0xF73u);
          if ( v320 )
          {
LABEL_223:
            v94 = *((_QWORD *)v217 + 26);
            v485 = v94;
            if ( v94 )
              v95 = *(_QWORD *)(v94 + 64);
            else
              v95 = 0;
            v96 = *((_QWORD *)v217 + 82);
            v311 = *(_WORD *)(*((_QWORD *)v217 + 6) + 1720LL);
            v97 = v311;
            v98 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v96 + 312LL))(v96);
            LogSystemMetadata(
              L"Page is current (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
              v97,
              *(_QWORD *)(a7 + 40),
              v98,
              v95);
          }
LABEL_228:
          v226 = (unsigned __int8)byte_10317AD6E >> 3;
          if ( (byte_10317AD6E & 8) != 0 )
          {
LABEL_232:
            CDStream::CDStream((CDStream *)v580);
            ProcessHeap = GetProcessHeap();
            v102 = (CTracePrintStream *)HeapAlloc(ProcessHeap, 0, 0x6C0u);
            v492 = v102;
            if ( v102 )
              v103 = CTracePrintStream::CTracePrintStream(v102, 0);
            else
              v103 = 0;
            v493 = v103;
            v401 = v103;
            if ( v103 && !CDStream::AddDevice((CDStream *)v580, v103) )
            {
              v494 = v103;
              (**(void (__fastcall ***)(CTracePrintStream *, __int64))v103)(v103, 1);
              v401 = 0;
            }
            Record::Dump((Record *)&v602, (struct CDStream *)v580);
            CDStream::~CDStream((CDStream *)v580);
            goto LABEL_240;
          }
          v324 = 0;
          v365 = 88;
          v486 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v487 = (_QWORD *)(v486[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v488 = v487;
          v99 = *v487;
          v489 = v99;
          v490 = v99;
          if ( v99 && (v100 = **(struct CSessionTraceFlags ***)(v99 + 56), (v491 = v100) != 0) )
          {
            v400 = v100;
            v324 = CSessionTraceFlags::CheckSessionTraceInternal(v100, 0xF73u);
            if ( v324 )
              goto LABEL_232;
          }
          else
          {
            v400 = 0;
          }
LABEL_240:
          if ( !(unsigned int)Record::IsGhostRecord((Record *)&v602) && v220 )
          {
            if ( v602 )
            {
              v129 = v604;
              if ( !v604 )
              {
                CDRecord::Resize((CDRecord *)&v603);
                v129 = v604;
              }
              if ( v129 < 9 && ((*v605 & 0x1C) == 0 || (*v605 & 0x1C) == 0xC) )
                v129 = 9;
              v273 = v129;
              v131 = v129;
            }
            else
            {
              if ( !v604 )
              {
                v213 = 0;
                v603 = 0;
                v104 = v606;
                HIDWORD(v606) = v606;
                if ( (*v605 & 0x10) != 0 )
                {
                  v104 = (((unsigned int)*(unsigned __int16 *)&v605[(unsigned int)v606] + 7) >> 3) + v606 + 2;
                  HIDWORD(v606) = v104;
                }
                if ( (*v605 & 0x20) != 0 )
                {
                  v329 = (unsigned __int16 *)&v605[v104];
                  v105 = *v329;
                  v608 = v105;
                  if ( !v105 )
                  {
                    v213 = 1;
                    if ( byte_10316E8D7 || (v227 = qword_10317B120, (qword_10317B120 & 1) != 0) )
                    {
                      v366 = 88;
                      v495 = NtCurrentTeb()->ThreadLocalStoragePointer;
                      v496 = v495[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                      v497 = v496;
                      v106 = *(_QWORD *)(v496 + 8);
                      v498 = v106;
                      v499 = v106;
                      if ( v106 )
                      {
                        v107 = *(_QWORD *)(v106 + 96);
                        v402 = v107;
                        if ( v107 && *(_BYTE *)(v107 + 1177) )
                        {
                          if ( byte_10316E7C7
                            || (v228 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                          {
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          }
                          else
                          {
                            ex_raise(34, 68, 21, 1003);
                          }
                        }
                      }
                      else
                      {
                        v402 = 0;
                      }
                    }
                    RaiseInconsistencyError(v605, 3);
                    v105 = v608;
                    v104 = HIDWORD(v606);
                  }
                  v108 = v104 + 2 * (v105 + 1);
                  v607 = v108;
                  if ( v108 > 0x1F9E )
                  {
                    ++v213;
                    if ( byte_10316E8D7 || (v229 = qword_10317B120, (qword_10317B120 & 1) != 0) )
                    {
                      v367 = 88;
                      v500 = NtCurrentTeb()->ThreadLocalStoragePointer;
                      v501 = v500[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                      v502 = v501;
                      v109 = *(_QWORD *)(v501 + 8);
                      v503 = v109;
                      v504 = v109;
                      if ( v109 )
                      {
                        v110 = *(_QWORD *)(v109 + 96);
                        v403 = v110;
                        if ( v110 && *(_BYTE *)(v110 + 1177) )
                        {
                          if ( byte_10316E7C7
                            || (v230 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                          {
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          }
                          else
                          {
                            ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                      else
                      {
                        v403 = 0;
                      }
                    }
                    RaiseInconsistencyError(v605, 4);
                    v105 = v608;
                    v108 = v607;
                    v104 = HIDWORD(v606);
                  }
                  v310 = v329[v105];
                  v604 = v310 & 0x7FFF;
                  if ( v108 > v604 )
                  {
                    ++v213;
                    if ( byte_10316E8D7 || (v231 = qword_10317B120, (qword_10317B120 & 1) != 0) )
                    {
                      v368 = 88;
                      v505 = NtCurrentTeb()->ThreadLocalStoragePointer;
                      v506 = v505[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                      v507 = v506;
                      v111 = *(_QWORD *)(v506 + 8);
                      v508 = v111;
                      v509 = v111;
                      if ( v111 )
                      {
                        v112 = *(_QWORD *)(v111 + 96);
                        v404 = v112;
                        if ( v112 && *(_BYTE *)(v112 + 1177) )
                        {
                          if ( byte_10316E7C7
                            || (v232 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                          {
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          }
                          else
                          {
                            ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                      else
                      {
                        v404 = 0;
                      }
                    }
                    RaiseInconsistencyError(v605, 4);
                    v105 = v608;
                    v108 = v607;
                    v104 = HIDWORD(v606);
                  }
                  while ( 1 )
                  {
                    v510 = (__int16 *)&v329[v105];
                    if ( *v510 >= 0 )
                      break;
                    v369 = v105;
                    v113 = &v605[v104];
                    v511 = v113;
                    if ( v105 == 1 )
                    {
                      v114 = v108;
                    }
                    else
                    {
                      v303 = *(_WORD *)&v113[2 * v105 - 2];
                      v114 = v303 & 0x7FFF;
                    }
                    v298 = *(_WORD *)&v113[2 * v105];
                    v115 = v298 & 0x7FFF;
                    v370 = v115;
                    if ( v114 < v108 || v115 < v114 )
                    {
                      RaiseInconsistencyError(v605, 7);
                      v105 = v608;
                      v108 = v607;
                      v104 = HIDWORD(v606);
                    }
                    v116 = v115 - v114;
                    v371 = v116;
                    v372 = v114;
                    if ( v114 < v108 || v114 > v604 )
                    {
                      v291 = v213 + 1;
                      goto LABEL_337;
                    }
                    v117 = *(_WORD *)&v605[v114];
                    v316 = v117;
                    if ( v117 == 5 )
                    {
                      v603 |= 2u;
                      --v608;
                      v373 = v116;
                      v512 = (char *)&v610 + 4;
                      DWORD1(v610) = __PAIR32__(WORD3(v610), v114) & 0xC7FFFFFF;
                      v118 = &v605[(unsigned __int16)v114];
                      v513 = v118;
                      v119 = *((_WORD *)v118 + 1);
                      if ( (v119 & 0x4000) != 0 )
                        WORD3(v610) |= v119 & 0x3800;
                      WORD3(v610) ^= (*((_WORD *)v118 + 1) ^ WORD3(v610)) & 0x7FF;
                      break;
                    }
                    if ( v117 >= 0x400u )
                    {
                      v603 |= 1u;
                      v47 = v105-- == 1;
                      v608 = v105;
                      if ( !v47 )
                        continue;
                    }
                    break;
                  }
                }
                else
                {
                  v604 = v104;
                  v608 = 0;
                  v607 = v104;
                }
                if ( (*v605 & 0x40) != 0 )
                {
                  LODWORD(v610) = v604;
                  v604 += 14;
                  v514 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v603);
                  v120 = *(_QWORD *)v514;
                  v405 = v120;
                  v121 = HIDWORD(v120);
                  v122 = HIDWORD(v120);
                  v123 = HIDWORD(v120);
                  v290 = 0;
                  if ( ((SHIWORD(v120) ^ ((unsigned int)SHIWORD(v120) >> 1)) & 0x2000) != 0 )
                  {
                    if ( (v120 & 0x4000000000000000LL) != 0 )
                    {
                      LOWORD(v120) = HIWORD(v120) | 0x2000;
                      LOWORD(v123) = v122;
                    }
                    else
                    {
                      LOWORD(v120) = HIWORD(v120) & 0xDFFF;
                      LOWORD(v123) = v121;
                    }
                  }
                  else
                  {
                    v120 >>= 48;
                  }
                  v299 = v120;
                  v124 = 0;
                  if ( (_WORD)v120 == 0xFFFC )
                  {
                    v515 = (__int64 *)&v405;
                    v124 = (unsigned __int16)v123 >> 5;
                    v290 = v124;
                  }
                  v604 += v124;
                }
                else
                {
                  LODWORD(v610) = 0;
                }
                if ( v609 && v609 < (unsigned __int64)&v605[v604] )
                {
                  ++v213;
                  if ( byte_10316E8D7 || (v233 = qword_10317B120, (qword_10317B120 & 1) != 0) )
                  {
                    v374 = 88;
                    v516 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v517 = v516[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v518 = v517;
                    v125 = *(_QWORD *)(v517 + 8);
                    v519 = v125;
                    v520 = v125;
                    if ( v125 )
                    {
                      v126 = *(_QWORD *)(v125 + 96);
                      v406 = v126;
                      if ( v126 && *(_BYTE *)(v126 + 1177) )
                      {
                        if ( byte_10316E7C7
                          || (v254 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                        {
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        }
                        else
                        {
                          ex_raise(34, 68, 21, 1018);
                        }
                      }
                    }
                    else
                    {
                      v406 = 0;
                    }
                  }
                  RaiseInconsistencyError(v605, 18);
                }
                if ( v604 - 1 > 0x3F3B )
                {
                  ++v213;
                  if ( byte_10316E8D7 || (v235 = qword_10317B120, (qword_10317B120 & 1) != 0) )
                  {
                    v375 = 88;
                    v521 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v522 = v521[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v523 = v522;
                    v127 = *(_QWORD *)(v522 + 8);
                    v524 = v127;
                    v525 = v127;
                    if ( v127 )
                    {
                      v128 = *(_QWORD *)(v127 + 96);
                      v407 = v128;
                      if ( v128 && *(_BYTE *)(v128 + 1177) )
                      {
                        if ( byte_10316E7C7
                          || (v236 = (unsigned __int8)qword_10317B120 >> 1, (qword_10317B120 & 2) != 0) )
                        {
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        }
                        else
                        {
                          ex_raise(34, 68, 21, 1005);
                        }
                      }
                    }
                    else
                    {
                      v407 = 0;
                    }
                  }
                  RaiseInconsistencyError(v605, 5);
                }
                v291 = v213;
              }
LABEL_337:
              v129 = v604;
              if ( v604 < 9 )
              {
                v526 = v605;
                v130 = *v605 & 0xE;
                v237 = v130;
                if ( !v130 || v130 == 12 )
                  v129 = 9;
              }
              v376 = v129;
              v273 = v129;
              v131 = v129;
            }
            v377 = (1 << (*(_WORD *)(v13 + 4) & 2)) - 1;
            v136 = (unsigned __int16)v377;
            LOWORD(v136) = ~(_WORD)v377;
            v378 = v377;
            if ( (unsigned __int16)(~(_WORD)v377 & (v131 + v377)) > (unsigned __int16)(~(_WORD)v377 & (v377 + v255)) )
            {
              if ( !a9 )
              {
                if ( v274 )
                  (**(void (__fastcall ***)(__int64, __int64))v274)(v274, 1);
                return 1;
              }
              v138 = -1;
              v586 = -1;
              v589 = 0;
              v588 = 0;
              v594 = 0;
              *(_QWORD *)&v595[2] = 0;
              v139 = 0;
              v590 = 0;
              v597 = -1;
              v140 = 0;
              v292 = 0;
              v141 = 0;
              while ( 1 )
              {
                while ( 1 )
                {
                  if ( v141 >= *(unsigned __int16 *)(v13 + 22) )
                    goto LABEL_448;
                  if ( v141 != v219 && *(_WORD *)(v13 + 2 * (4095LL - v141)) )
                    break;
                  v292 = ++v140;
                  v141 = v140;
                }
                v597 = v140;
                if ( *(char *)(v13 + 2) < 0 )
                  break;
                v139 = 0;
                v296 = 0;
LABEL_412:
                v162 = *(unsigned __int16 *)(v13 + 14);
                v163 = (unsigned __int8 *)(v13 + *(unsigned __int16 *)(v13 + 2 * (4095LL - v140)));
                v164 = *v163 & 1;
                v586 = v164;
                if ( v164 )
                {
                  v589 = v163;
                  v136 = *v163;
                  switch ( *v163 & 0x1C )
                  {
                    case 0:
                    case 0xC:
                    case 0x10:
                    case 0x14:
                    case 0x18:
                    case 0x1C:
                      v165 = v163[1];
                      if ( (v165 & 0x80u) != 0 )
                      {
                        v587 = *(_WORD *)(v163 + 1);
                        v165 = ((v587 & 0x7F) << 8) | HIBYTE(v587);
                        v166 = 3;
                      }
                      else
                      {
                        v166 = 2;
                      }
                      v587 = v165;
                      v136 = v165;
                      v591 = v166;
                      v593 = v166 + (((unsigned int)v165 + 1) >> 1);
                      if ( v165 > 0x1Eu )
                      {
                        v167 = v165 - 1;
                        v136 = (unsigned int)(v167 / 30);
                        v592 = v167 / 30;
                      }
                      else
                      {
                        v592 = 0;
                      }
                      v588 = 0;
                      v596 = 0;
                      break;
                    case 1:
                    case 2:
                    case 3:
                    case 5:
                    case 6:
                    case 7:
                    case 9:
                    case 0xA:
                    case 0xB:
                    case 0xD:
                    case 0xE:
                    case 0xF:
                    case 0x11:
                    case 0x12:
                    case 0x13:
                    case 0x15:
                    case 0x16:
                    case 0x17:
                    case 0x19:
                    case 0x1A:
                    case 0x1B:
                      utassert_fail(
                        1u,
                        "FALSE",
                        "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                        207,
                        "Invalid switch value");
                      break;
                    case 4:
                      if ( (v136 & 0x1C) == 4 && (v136 & 2) != 0 )
                      {
                        v591 = 0;
                        v587 = 0;
                        v592 = 0;
                        v593 = 0;
                        v594 = 0;
                        memset(v595, 0, sizeof(v595));
                        v590 = 0;
                        v589 = v163;
                        v588 = 15;
                        v596 = 1;
                      }
                      else
                      {
                        v591 = 0;
                        v587 = 0;
                        v592 = 0;
                        v593 = 0;
                        v594 = 0;
                        memset(v595, 0, sizeof(v595));
                        v590 = 0;
                        v589 = v163;
                        v588 = 1;
                        v596 = 0;
                      }
                      break;
                    case 8:
                      v591 = 0;
                      v587 = 0;
                      v592 = 0;
                      v593 = 0;
                      v594 = 0;
                      memset(v595, 0, sizeof(v595));
                      v590 = 0;
                      v589 = v163;
                      v588 = 9;
                      v596 = 0;
                      break;
                  }
                  *(_QWORD *)&v595[2] = v13 + 0x2000;
                  v590 = v139;
                }
                else
                {
                  v256 = v162;
                  v589 = v163;
                  v588 = 0;
                  *(_DWORD *)v595 = 0;
                  v136 = *v163 & 0xE;
                  switch ( *v163 & 0xE )
                  {
                    case 0:
                    case 2:
                    case 8:
                    case 0xC:
                      v162 = *((unsigned __int16 *)v163 + 1);
                      v256 = v162;
                      if ( (unsigned int)(v162 - 1) > 0x1F9D )
                        RaiseInconsistencyError(v163, 6);
                      break;
                    case 1:
                    case 3:
                    case 5:
                    case 7:
                    case 9:
                    case 0xB:
                    case 0xD:
                      utassert_fail(
                        1u,
                        "FALSE",
                        "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                        294,
                        "Invalid switch value");
                      break;
                    case 4:
                      v162 = 9;
                      v256 = 9;
                      break;
                    case 6:
                    case 0xA:
                      break;
                    case 0xE:
                      v162 = 1;
                      v256 = 1;
                      break;
                  }
                  LODWORD(v590) = v162;
                  v594 = v13 + 0x2000;
                  v139 = v590;
                }
                v168 = *v589;
                if ( v586 )
                  v169 = v168 >> 1;
                else
                  v169 = v168 >> 6;
                if ( (v169 & 1) != 0 )
                {
                  LODWORD(v264) = *(_DWORD *)v285;
                  WORD2(v264) = *(_WORD *)(v285 + 4);
                  HIWORD(v264) = v140;
                  LOBYTE(v211) = 0;
                  LOBYTE(v210) = a8;
                  v170 = BlobManager::RevertFromVersion(v217, v271, v286, &v586, v13, &v264, a7, v210, v211, v284, v222);
                  if ( v170 == 3 )
                  {
                    if ( !a8 )
                      utassert_fail(1u, "ctrCleaner", "blobman.cpp", 5301, 0);
                    v215 = 3;
                    goto LABEL_534;
                  }
                  if ( v170 == 2 )
                  {
                    v215 = 2;
                    goto LABEL_534;
                  }
                  v139 = v590;
                  v138 = -1;
                  v292 = ++v140;
                  v141 = v140;
                }
                else
                {
                  v138 = -1;
                  v292 = ++v140;
                  v141 = v140;
                }
              }
              v142 = (unsigned __int8 *)(v13 + 96);
              _mm_prefetch((const char *)(v13 + 96), 0);
              if ( v586 )
              {
                v296 = v139;
                if ( v139 )
                  goto LABEL_368;
              }
              else
              {
                v296 = 0;
              }
              v599 = 0;
              v598[0] = 0;
              v598[1] = 0xFFFFu;
              memset(&v598[2], 0, 80);
              v139 = v598;
              v296 = v598;
LABEL_368:
              if ( !*(_WORD *)(v13 + 36) )
                goto LABEL_380;
              v143 = *(_BYTE *)(v13 + 1);
              if ( v143 == 11 )
              {
                if ( *(_DWORD *)(v13 + 24) == 99 )
                {
LABEL_375:
                  v304 = *(_DWORD *)(v13 + 32);
                  v305 = *(_WORD *)(v13 + 36);
                  if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v304, v136) )
                  {
                    v144 = 1;
                    goto LABEL_378;
                  }
LABEL_377:
                  v144 = 0;
LABEL_378:
                  if ( v144 )
                  {
                    PageHeader::GetIcxLsn(v13, &v288);
LABEL_381:
                    *(_QWORD *)v139 = v142;
                    v145 = v289;
                    v146 = HIDWORD(v288);
                    *((_DWORD *)v139 + 24) = v288;
                    *((_DWORD *)v139 + 25) = v146;
                    *((_WORD *)v139 + 52) = v145;
                    *((_DWORD *)v139 + 27) = *(_DWORD *)(v13 + 32);
                    *((_WORD *)v139 + 56) = *(_WORD *)(v13 + 36);
                    *((_WORD *)v139 + 57) = 0;
                    v147 = 3LL * *v142;
                    v348 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v142);
                    v148 = word_102883984[v147];
                    *((_WORD *)v139 + 8) = v138;
                    *((_QWORD *)v139 + 3) = 0;
                    *((_DWORD *)v139 + 5) = 0;
                    *(_QWORD *)((char *)v139 + 46) = 0;
                    *((_QWORD *)v139 + 7) = 0;
                    *((_QWORD *)v139 + 4) = 0;
                    *((_QWORD *)v139 + 9) = 0;
                    *((_QWORD *)v139 + 10) = 0;
                    *((_WORD *)v139 + 44) = 0;
                    if ( (**(_BYTE **)v139 & 2) != 0 )
                    {
                      v149 = &v142[v148];
                      v150 = v142[v148] & 1;
                      *((_WORD *)v139 + 8) = v150;
                      if ( v150 )
                      {
                        *((_QWORD *)v139 + 3) = v149;
                        v153 = *v149;
                        switch ( *v149 & 0x1C )
                        {
                          case 0:
                          case 0xC:
                          case 0x10:
                          case 0x14:
                          case 0x18:
                          case 0x1C:
                            v154 = v149[1];
                            if ( (v154 & 0x80u) != 0 )
                            {
                              v157 = *(_WORD *)(v149 + 1);
                              *((_WORD *)v139 + 9) = v157;
                              *((_WORD *)v139 + 9) = HIBYTE(v157) | ((v157 & 0x7F) << 8);
                              v155 = 3;
                              v156 = 3;
                            }
                            else
                            {
                              *((_WORD *)v139 + 9) = v154;
                              v155 = 2;
                              v156 = 2;
                            }
                            *((_WORD *)v139 + 20) = v155;
                            *((_WORD *)v139 + 22) = v156 + (((unsigned int)*((unsigned __int16 *)v139 + 9) + 1) >> 1);
                            v158 = *((unsigned __int16 *)v139 + 9);
                            if ( v158 > 0x1E )
                              *((_WORD *)v139 + 21) = (int)(v158 - 1) / 30;
                            else
                              *((_WORD *)v139 + 21) = 0;
                            *((_DWORD *)v139 + 5) = 0;
                            *((_DWORD *)v139 + 16) = 0;
                            break;
                          case 1:
                          case 2:
                          case 3:
                          case 5:
                          case 6:
                          case 7:
                          case 9:
                          case 0xA:
                          case 0xB:
                          case 0xD:
                          case 0xE:
                          case 0xF:
                          case 0x11:
                          case 0x12:
                          case 0x13:
                          case 0x15:
                          case 0x16:
                          case 0x17:
                          case 0x19:
                          case 0x1A:
                          case 0x1B:
                            utassert_fail(
                              1u,
                              "FALSE",
                              "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                              207,
                              "Invalid switch value");
                            break;
                          case 4:
                            if ( (v153 & 0x1C) == 4 && (v153 & 2) != 0 )
                            {
                              *((_QWORD *)v139 + 3) = 0;
                              *((_DWORD *)v139 + 5) = 0;
                              *((_WORD *)v139 + 20) = 0;
                              *((_WORD *)v139 + 9) = 0;
                              *((_WORD *)v139 + 21) = 0;
                              *((_WORD *)v139 + 22) = 0;
                              *((_WORD *)v139 + 23) = 0;
                              *((_WORD *)v139 + 24) = 0;
                              *((_WORD *)v139 + 25) = 0;
                              *((_WORD *)v139 + 26) = 0;
                              *((_WORD *)v139 + 27) = 0;
                              *((_QWORD *)v139 + 4) = 0;
                              *((_DWORD *)v139 + 16) = 0;
                              *((_QWORD *)v139 + 7) = 0;
                              *((_QWORD *)v139 + 3) = v149;
                              *((_DWORD *)v139 + 5) = 15;
                              *((_DWORD *)v139 + 16) = 0;
                              *((_DWORD *)v139 + 16) = 1;
                            }
                            else
                            {
                              *((_QWORD *)v139 + 3) = 0;
                              *((_DWORD *)v139 + 5) = 0;
                              *((_WORD *)v139 + 20) = 0;
                              *((_WORD *)v139 + 9) = 0;
                              *((_WORD *)v139 + 21) = 0;
                              *((_WORD *)v139 + 22) = 0;
                              *((_WORD *)v139 + 23) = 0;
                              *((_WORD *)v139 + 24) = 0;
                              *((_WORD *)v139 + 25) = 0;
                              *((_WORD *)v139 + 26) = 0;
                              *((_WORD *)v139 + 27) = 0;
                              *((_QWORD *)v139 + 4) = 0;
                              *((_DWORD *)v139 + 16) = 0;
                              *((_QWORD *)v139 + 7) = 0;
                              *((_QWORD *)v139 + 3) = v149;
                              *((_DWORD *)v139 + 5) = 1;
                              *((_DWORD *)v139 + 16) = 0;
                            }
                            break;
                          case 8:
                            *((_QWORD *)v139 + 3) = 0;
                            *((_DWORD *)v139 + 5) = 0;
                            *((_WORD *)v139 + 20) = 0;
                            *((_WORD *)v139 + 9) = 0;
                            *((_WORD *)v139 + 21) = 0;
                            *((_WORD *)v139 + 22) = 0;
                            *((_WORD *)v139 + 23) = 0;
                            *((_WORD *)v139 + 24) = 0;
                            *((_WORD *)v139 + 25) = 0;
                            *((_WORD *)v139 + 26) = 0;
                            *((_WORD *)v139 + 27) = 0;
                            *((_QWORD *)v139 + 4) = 0;
                            *((_DWORD *)v139 + 16) = 0;
                            *((_QWORD *)v139 + 7) = 0;
                            *((_QWORD *)v139 + 3) = v149;
                            *((_DWORD *)v139 + 5) = 9;
                            *((_DWORD *)v139 + 16) = 0;
                            break;
                        }
                        *((_QWORD *)v139 + 7) = 0;
                        *((_QWORD *)v139 + 4) = 0;
                      }
                      else
                      {
                        v151 = 0;
                        v249 = 0;
                        *((_QWORD *)v139 + 3) = v149;
                        *((_DWORD *)v139 + 5) = 0;
                        *(_DWORD *)((char *)v139 + 54) = 0;
                        v152 = (_BYTE *)*((_QWORD *)v139 + 3);
                        switch ( *v152 & 0xE )
                        {
                          case 0:
                          case 2:
                          case 8:
                          case 0xC:
                            v151 = *((unsigned __int16 *)v149 + 1);
                            v249 = v151;
                            if ( (unsigned int)(v151 - 1) <= 0x1F9D )
                              goto LABEL_389;
                            RaiseInconsistencyError(v152, 6);
                            *((_DWORD *)v139 + 8) = v151;
                            *(_QWORD *)((char *)v139 + 46) = 0;
                            break;
                          case 1:
                          case 3:
                          case 5:
                          case 7:
                          case 9:
                          case 0xB:
                          case 0xD:
                            utassert_fail(
                              1u,
                              "FALSE",
                              "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                              294,
                              "Invalid switch value");
                            goto LABEL_389;
                          case 4:
                            v249 = 9;
                            *((_DWORD *)v139 + 8) = 9;
                            *(_QWORD *)((char *)v139 + 46) = 0;
                            break;
                          case 6:
                          case 0xA:
LABEL_389:
                            *((_DWORD *)v139 + 8) = v151;
                            *(_QWORD *)((char *)v139 + 46) = 0;
                            break;
                          case 0xE:
                            v249 = 1;
                            *((_DWORD *)v139 + 8) = 1;
                            *(_QWORD *)((char *)v139 + 46) = 0;
                            break;
                        }
                      }
                    }
                    if ( (**(_BYTE **)v139 & 4) != 0 )
                    {
                      if ( HIWORD(v348) )
                        v159 = &v142[*(unsigned __int16 *)&v142[2 * SHIWORD(v348) + 1]];
                      else
                        v159 = &v142[v148];
                      *((_QWORD *)v139 + 9) = v159;
                      v160 = *(_WORD *)v159;
                      *((_QWORD *)v139 + 10) = v159 + 2;
                      *((_WORD *)v139 + 44) = 2 * (v160 + 1);
                    }
                    v161 = (PageComprInfoCache *)*((_QWORD *)v139 + 1);
                    if ( v161 )
                      PageComprInfoCache::Init(v161, (const struct PageComprInfo *)v139);
                    v13 = v297;
                    goto LABEL_412;
                  }
LABEL_380:
                  v288 = *(_QWORD *)(v13 + 40);
                  v289 = *(_WORD *)(v13 + 48);
                  goto LABEL_381;
                }
              }
              else if ( v143 == 8 )
              {
LABEL_374:
                if ( *(_DWORD *)(v13 + 24) != 99 )
                  goto LABEL_377;
                goto LABEL_375;
              }
              if ( v143 != 9 )
                goto LABEL_377;
              goto LABEL_374;
            }
LABEL_448:
            v171 = v224 & 0xFC;
            LOBYTE(v224) = v224 & 0xFC;
            v172 = 0;
            v173 = v286;
            if ( *(_DWORD *)(v286 + 56) == 3 )
              v172 = 4;
            LOBYTE(v224) = v171 & 0xFB | v172;
            HoBtVersioningStatus::Init(
              (HoBtVersioningStatus *)&v223,
              *(struct HoBtAccess **)(v286 + 88),
              (*(unsigned __int8 *)(v286 + 120) >> 5) & 1);
            v174 = *(_QWORD *)(v173 + 88);
            if ( v214 )
            {
              v570 = v223;
              v571 = v224;
              LODWORD(v208) = v219;
              TextPageRef::RevertTextNode(v222, v174, v271, v217, v208, &v570, &v602);
            }
            else
            {
              v572 = v223;
              v573 = v224;
              TextPageRef::ModifyTextNode(v222, v174, v271, v217, 0, v219, 0, v255, v129, v605, &v572);
            }
            ++*((_QWORD *)v287 + 64);
            v215 = 4;
            goto LABEL_534;
          }
          v64 = (_DWORD *)v285;
LABEL_342:
          if ( v214 )
          {
            LOWORD(v262) = v262 & 0xC0;
            BYTE2(v262) = 0;
            *((_QWORD *)&v262 + 1) = 0;
            v132 = v263 & 0xE0;
            LOBYTE(v263) = v263 & 0xE0;
            v133 = 0;
            v134 = v286;
            if ( *(_DWORD *)(v286 + 56) == 3 )
              v133 = 4;
            LOBYTE(v263) = v132 & 0xFB | v133;
            HoBtVersioningStatus::Init(
              (HoBtVersioningStatus *)&v262,
              *(struct HoBtAccess **)(v286 + 88),
              (*(unsigned __int8 *)(v286 + 120) >> 5) & 1);
            v574 = v262;
            v575 = v263;
            LODWORD(v208) = v219;
            TextPageRef::RevertTextNode(v222, *(_QWORD *)(v134 + 88), v271, v217, v208, &v574, 0);
            v135 = v287;
            ++*((_QWORD *)v287 + 64);
            ++*((_QWORD *)v135 + 123);
            v215 = 4;
LABEL_534:
            if ( a9 && !v328 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v274 + 40LL))(v274);
            goto LABEL_537;
          }
          v175 = v286;
          v283 = *(HoBtAccess **)(v286 + 88);
          v527 = &v333;
          v333 = 0;
          v334 = 0;
          v335 = 0;
          v528 = &v336;
          v338 = 0;
          v339 = 0;
          v340 = 120;
          v341 = 0;
          v342 = v627;
          v344 = &v628;
          v345 = 0;
          v346 = 0;
          v347 = 0;
          v343 = v627;
          v337 = 0;
          v336 = 0;
          v529 = v627;
          v627[0] = 0;
          v627[1] = 0;
          v627[2] = 0;
          v627[3] = 4;
          v612[0] = 0;
          v613 = -1;
          v614 = 0;
          v615 = 0;
          v616 = 0;
          v617 = 0;
          v618 = 0;
          v619 = 0;
          v585 = 1;
          v621 = 0;
          v622 = 0;
          v530 = &v623;
          v623 = 0;
          v176 = v287;
          v302 = *((_WORD *)v287 + 860);
          v612[0] = 5;
          *(_QWORD *)&v615 = (char *)v217 + 56;
          v614 = 0x2000000;
          v585 = 9;
          v584 = v302;
          v583 = 0;
          v531 = &v581;
          v532 = v64;
          v533 = &v581;
          v581 = *v64;
          v582 = v64[1];
          v613 = 0;
          v379 = lck_lockInternal(v612, (LockRes *)&v581, (__int64)v620, 0);
          if ( v379 < 0 )
          {
            if ( a8 )
            {
              v215 = 3;
LABEL_529:
              if ( v617 )
              {
                v204 = v617 + 8;
                v300 = _InterlockedDecrement((volatile signed __int32 *)(v617 + 8));
                if ( !v300 )
                {
                  v205 = v204 - 8;
                  if ( !v204 )
                    v205 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v205 + 8LL))(v205);
                }
              }
              goto LABEL_534;
            }
            v613 = -1;
            v177 = v222;
            PageRef::Unlatch(v222);
            if ( v585 == 5 )
            {
              if ( v582 )
              {
LABEL_460:
                v178 = lck_lockInternal(v612, (LockRes *)&v581, (__int64)v620, 0);
                v382 = v178;
                goto LABEL_461;
              }
            }
            else if ( v585 == 11 )
            {
              if ( !md_locks_are_partitioned )
                goto LABEL_460;
            }
            else if ( v585 != 2 || v581 )
            {
              goto LABEL_460;
            }
            if ( !dword_10317F810 )
              goto LABEL_460;
            if ( v585 == 2 )
              v180 = *((unsigned __int8 *)&LCK_DBLock_LPOM + v612[0]);
            else
              v180 = *((_DWORD *)&LCK_modeGroups + 5 * v612[0]);
            v380 = v180;
            if ( !v180 )
            {
              v178 = lck_lockPartitionedAll(v612, &v581, v620);
LABEL_461:
              v261 = v178;
              if ( v178 >= 0 )
              {
                LOBYTE(v209) = 1;
                PageRef::Latch(v177, 4, 0xFFFFFFFFLL, v420, 0, 0, v209);
                v215 = 2;
              }
              else
              {
                if ( v178 != -1 )
                {
                  _mm_lfence();
                  LOBYTE(v179) = 25;
                  lck_StandardHandler(v261, v179);
                }
                v215 = 3;
              }
              goto LABEL_529;
            }
            v534 = v620;
            v535 = v615;
            v624 = 0;
            v625 = 0;
            v536 = &v626;
            v626 = 0;
            v537 = v620;
            v181 = *(_DWORD *)(v615 + 124);
            v381 = v181;
            if ( v585 == 2 )
            {
              v540 = &v581;
            }
            else
            {
              if ( v585 != 5 )
              {
                v538 = &v581;
                HIWORD(v583) = v181;
                goto LABEL_481;
              }
              v539 = &v581;
            }
            v583 = v181;
LABEL_481:
            v618 |= 0x20u;
            v178 = lck_lockInternal(v612, (LockRes *)&v581, (__int64)v620, 0);
            v293 = v178;
            v618 &= ~0x20u;
            if ( v178 == -5 )
            {
              v178 = lck_lockPartitionedAll(v612, &v581, v620);
              v293 = v178;
            }
            goto LABEL_461;
          }
          v182 = v283;
          v183 = *(_QWORD **)(*((_QWORD *)v283 + 1) + 1160LL);
          if ( v183 )
          {
            v238 = CommonGlobalState::m_CollectingStatistics;
            if ( CommonGlobalState::m_CollectingStatistics )
            {
              v239 = (unsigned __int8)byte_10317ABD0 >> 1;
              if ( (byte_10317ABD0 & 2) == 0 )
              {
                v409 = v183;
                v541 = 1;
                v542 = v183;
                if ( v183[1] )
                {
                  v383 = 88;
                  v543 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v184 = v543[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v544 = v184;
                  v185 = *(_QWORD *)(v184 + 256);
                  v408 = v185;
                  if ( !v185 )
                  {
                    SystemThread::MakeMiniSOSThread(0);
                    v185 = *(_QWORD *)(v184 + 256);
                    v408 = v185;
                  }
                  v186 = *(_QWORD *)(v185 + 608);
                  v545 = v186;
                  if ( v186 )
                    v187 = *(unsigned int *)(v186 + 3688);
                  else
                    v187 = 0;
                  v384 = v187;
                  v385 = v187;
                  if ( (unsigned int)v187 < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2) )
                  {
                    _mm_lfence();
                    v546 = *(_QWORD *)(v183[1] + 8 * v187);
                    ++*(_QWORD *)(v546 + 8);
                    goto LABEL_498;
                  }
                  v183 = v409;
                }
                v547 = (volatile signed __int64 *)(*v183 + 8LL);
                v548 = _InterlockedIncrement64(v547);
              }
            }
          }
LABEL_498:
          if ( !v621 )
          {
LABEL_526:
            v201 = v342;
            v343 = v342;
            v563 = v342;
            *v342 = 0;
            v201[1] = 0;
            v201[2] = 0;
            v201[3] = 4;
            v344 = v342 + 4;
            v341 = 0;
            v414[0] = HoBtAccess::GetLockResourceId(v283);
            v343[2] = 0;
            v347 = 1;
            LogLockCollection::AddOperation(&v333, 1, 1, 8, v414);
            LogLockCollection::AddOperation(&v333, 1, 2, 0, 0);
            LogLockCollection::AddOperation(&v333, 2, 3, 0, 0);
            LOWORD(v244) = v244 & 0xC0;
            BYTE2(v244) = 0;
            *((_QWORD *)&v244 + 1) = 0;
            v202 = v245 & 0xE0;
            LOBYTE(v245) = v245 & 0xE0;
            v203 = 0;
            if ( *(_DWORD *)(v175 + 56) == 3 )
              v203 = 4;
            LOBYTE(v245) = v202 & 0xFB | v203;
            HoBtVersioningStatus::Init(
              (HoBtVersioningStatus *)&v244,
              *(struct HoBtAccess **)(v175 + 88),
              (*(unsigned __int8 *)(v175 + 120) >> 5) & 1);
            LOBYTE(v245) = v245 & 0xEF;
            v576 = v244;
            v577 = v245;
            TextPageRef::Delete(v222, *(_QWORD *)(v175 + 88), v271, v217, &v333, v219, &v576);
            ++*((_QWORD *)v176 + 64);
            v215 = 4;
            goto LABEL_529;
          }
          v188 = *(_QWORD *)(*((_QWORD *)v182 + 1) + 1160LL);
          if ( v188 )
          {
            v240 = CommonGlobalState::m_CollectingStatistics;
            if ( CommonGlobalState::m_CollectingStatistics )
            {
              v241 = (unsigned __int8)byte_10317ABD0 >> 1;
              if ( (byte_10317ABD0 & 2) == 0 )
              {
                v549 = v188;
                v550 = 22;
                v189 = (_QWORD *)(v188 + 24);
                v411 = v189;
                if ( v189[1] )
                {
                  v386 = 88;
                  v551 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v190 = v551[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v552 = v190;
                  v191 = *(_QWORD *)(v190 + 256);
                  v410 = v191;
                  if ( !v191 )
                  {
                    SystemThread::MakeMiniSOSThread(0);
                    v191 = *(_QWORD *)(v190 + 256);
                    v410 = v191;
                  }
                  v192 = *(_QWORD *)(v191 + 608);
                  v553 = v192;
                  if ( v192 )
                    v193 = *(unsigned int *)(v192 + 3688);
                  else
                    v193 = 0;
                  v387 = v193;
                  v388 = v193;
                  if ( (unsigned int)v193 < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2) )
                  {
                    _mm_lfence();
                    v554 = *(_QWORD *)(v189[1] + 8 * v193);
                    ++*(_QWORD *)(v554 + 176);
                    goto LABEL_512;
                  }
                  v189 = v411;
                }
                v555 = (volatile signed __int64 *)(*v189 + 176LL);
                v556 = _InterlockedIncrement64(v555);
              }
            }
          }
LABEL_512:
          v194 = v621;
          v330 = v621;
          if ( !v621 )
            goto LABEL_526;
          v195 = *(_QWORD *)(*((_QWORD *)v182 + 1) + 1160LL);
          if ( !v195 )
            goto LABEL_526;
          v242 = CommonGlobalState::m_CollectingStatistics;
          if ( !CommonGlobalState::m_CollectingStatistics )
            goto LABEL_526;
          v243 = (unsigned __int8)byte_10317ABD0 >> 1;
          if ( (byte_10317ABD0 & 2) != 0 )
            goto LABEL_526;
          v557 = v195;
          v558 = 23;
          v196 = (_QWORD *)(v195 + 24);
          v413 = v196;
          if ( v196[1] )
          {
            v389 = 88;
            v559 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v197 = v559[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v560 = v197;
            v198 = *(_QWORD *)(v197 + 256);
            v412 = v198;
            if ( !v198 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v198 = *(_QWORD *)(v197 + 256);
              v412 = v198;
            }
            v199 = *(_QWORD *)(v198 + 608);
            v561 = v199;
            if ( v199 )
              v200 = *(unsigned int *)(v199 + 3688);
            else
              v200 = 0;
            v390 = v200;
            v391 = v200;
            if ( (unsigned int)v200 < *((_DWORD *)g_SchemaMgrPartitionedHeap + 2) )
            {
              _mm_lfence();
              v562 = *(_QWORD *)(v196[1] + 8 * v200);
              *(_QWORD *)(v562 + 184) += v330;
              goto LABEL_526;
            }
            v196 = v413;
            v194 = v330;
          }
          _InterlockedExchangeAdd64((volatile signed __int64 *)(*v196 + 184LL), v194);
          goto LABEL_526;
        }
        v74 = *((_QWORD *)v217 + 6);
        v459 = v74;
        if ( *(_BYTE *)(v74 + 6872) )
          goto LABEL_155;
        v75 = (char *)v221 + 2;
        if ( *(_WORD *)v221 )
          CDRecord::GetVersionRecPtr(v75, v323);
        else
          FixedVarRecord::GetVersionRecPtr(v75, v323);
        v460 = v323;
        if ( !VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v323) )
        {
LABEL_155:
          v76 = *(_QWORD *)(*(_QWORD *)(v74 + 1712) + 704LL);
          v461 = v76;
          if ( *(_WORD *)(v76 + 10) != 2 || *(_DWORD *)Lsn )
          {
            v462 = v76;
            if ( *(_DWORD *)Lsn <= *(_DWORD *)v76 )
            {
              if ( *(_DWORD *)Lsn != *(_DWORD *)v76
                || (v77 = *(_DWORD *)(Lsn + 4), v77 <= *(_DWORD *)(v76 + 4))
                && (v77 != *(_DWORD *)(v76 + 4) || *(_WORD *)(Lsn + 8) <= *(_WORD *)(v76 + 8)) )
              {
                v78 = 0;
                v272 = 0;
                if ( !*(_BYTE *)(v74 + 8272) )
                {
LABEL_168:
                  v260 = (unsigned __int8)byte_10317AD6E >> 3;
                  if ( (byte_10317AD6E & 8) != 0 )
                  {
LABEL_172:
                    v83 = *((_QWORD *)v217 + 26);
                    v470 = v83;
                    if ( v83 )
                      v78 = *(_QWORD *)(v83 + 64);
                    v84 = *((_QWORD *)v217 + 82);
                    v315 = *(_WORD *)(*((_QWORD *)v217 + 6) + 1720LL);
                    v85 = v315;
                    v86 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v84 + 312LL))(v84);
                    LogSystemMetadata(
                      L"Before recovery version (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                      v85,
                      *(_QWORD *)(a7 + 40),
                      v86,
                      v78);
                    goto LABEL_228;
                  }
                  v319 = 0;
                  v360 = 88;
                  v464 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v465 = (_QWORD *)(v464[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v466 = v465;
                  v81 = *v465;
                  v467 = v81;
                  v468 = v81;
                  if ( v81 && (v82 = **(struct CSessionTraceFlags ***)(v81 + 56), (v469 = v82) != 0) )
                  {
                    v398 = v82;
                    v319 = CSessionTraceFlags::CheckSessionTraceInternal(v82, 0xF73u);
                    if ( v319 )
                      goto LABEL_172;
                  }
                  else
                  {
                    v398 = 0;
                  }
                  goto LABEL_228;
                }
                v79 = v221;
                v80 = (char *)v221 + 2;
                if ( *(_WORD *)v221 )
                  CDRecord::GetVersionRecPtr(v80, v294);
                else
                  FixedVarRecord::GetVersionRecPtr(v80, v294);
                v463 = v294;
                if ( !VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v294) )
                {
                  v78 = 0;
                  goto LABEL_168;
                }
LABEL_178:
                v87 = (unsigned __int8)*v605;
                if ( v602 )
                  v88 = v87 >> 1;
                else
                  v88 = v87 >> 6;
                v361 = v88 & 1;
                if ( (v88 & 1) == 0 )
                  goto LABEL_228;
                LODWORD(v221) = 0;
                WORD2(v221) = 0;
                if ( v602 )
                  CDRecord::GetXdesTs(&v603, &v267);
                else
                  FixedVarRecord::GetXdesTs(&v603, &v267);
                v471 = &v267;
                if ( !v268 && !v267 )
                  goto LABEL_228;
                v89 = (const struct UpdateSequenceMarker **)a7;
                if ( a7 && (*(_BYTE *)(a7 + 16) & 0x20) != 0 )
                {
                  if ( (*((_BYTE *)v217 + 536) & 4) != 0 )
                    v90 = (*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v217 + 488LL))(v217) + 40;
                  else
                    v90 = (__int64)v217 + 40;
                  v472 = v90;
                  if ( v602 )
                    CDRecord::GetXdesTs(&v603, &v265);
                  else
                    FixedVarRecord::GetXdesTs(&v603, &v265);
                  v473 = &v265;
                  if ( v266 == *(_WORD *)(v90 + 4) && v265 == *(_DWORD *)v90 )
                  {
                    v91 = *((_QWORD *)v217 + 26);
                    v474 = v91;
                    if ( v72 )
                    {
                      if ( !v91 || !*(_BYTE *)(v91 + 52) )
                      {
                        v89 = (const struct UpdateSequenceMarker **)a7;
                        goto LABEL_206;
                      }
                      v89 = (const struct UpdateSequenceMarker **)a7;
                      if ( !*(_QWORD *)(v91 + 64) )
                        goto LABEL_206;
                      v475 = _InterlockedCompareExchange64((volatile signed __int64 *)(v91 + 296), 0, 0);
                      v476 = v475;
                      v71 = v331;
                      if ( *(_QWORD *)(*(_QWORD *)a7 + 40LL) == v475 )
                        goto LABEL_206;
                    }
                    else
                    {
                      v89 = (const struct UpdateSequenceMarker **)a7;
                    }
                    VersionMgr::GetVersionWithUpdateMarker(
                      *((struct XVB **)v217 + 26),
                      v89[4],
                      *(const struct DBTABLE **)(v71 + 1712),
                      v629,
                      0x1F9Eu,
                      *v89,
                      (struct Record *)&v602,
                      0,
                      1,
                      (struct VersionMgr::GetVersionResult *)&v220,
                      0);
LABEL_206:
                    if ( !v72 )
                      goto LABEL_240;
                    if ( v602 )
                      CDRecord::GetVersionRecPtr(&v603, v295);
                    else
                      FixedVarRecord::GetVersionRecPtr(&v603, v295);
                    v477 = v295;
                    if ( v602 )
                      CDRecord::GetXdesTs(&v603, &v269);
                    else
                      FixedVarRecord::GetXdesTs(&v603, &v269);
                    v478 = &v269;
                    v362 = v269;
                    v312 = v270;
                    v308 = v269;
                    v309 = v270;
                    if ( !(unsigned int)XdesMgr::GetRowAbortState(v71 + 6600, &v308, v295) )
                      goto LABEL_240;
                    goto LABEL_216;
                  }
                  v89 = (const struct UpdateSequenceMarker **)a7;
                }
LABEL_216:
                v47 = *(_WORD *)v79 == 1;
                v363 = v47;
                if ( v47 )
                  VersionMgr::GetVersionFromCompressed(
                    v79,
                    v629,
                    0x1F9Eu,
                    v217,
                    (const struct VersionScanParams *)v89,
                    (struct PageRow *)&v602,
                    (struct VersionMgr::GetVersionResult *)&v220,
                    1,
                    0,
                    0,
                    (const struct LSN *)v600,
                    0);
                else
                  VersionMgr::GetVersionLong(
                    v629,
                    0x1F9Eu,
                    v217,
                    (const struct VersionScanParams *)v89,
                    (struct Record *)&v602,
                    (struct VersionMgr::GetVersionResult *)&v220,
                    1,
                    0,
                    0,
                    (const struct LSN *)v600,
                    1,
                    0);
                goto LABEL_240;
              }
            }
          }
          v272 = 1;
        }
        v79 = v221;
        goto LABEL_178;
      }
    }
  }
LABEL_537:
  v206 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v207 = *(struct Worker **)(v206 + 256);
  if ( !v207 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v207 = *(struct Worker **)(v206 + 256);
  }
  if ( *((_DWORD *)v207 + 139) )
    ExceptionPostCatchActions(v207);
  if ( v274 )
    (**(void (__fastcall ***)(__int64, __int64))v274)(v274, 1);
  return v215;
}

```

## disassembly

```asm
0x1016bad70  push    rbx
0x1016bad72  push    rsi
0x1016bad73  push    rdi
0x1016bad74  push    r12
0x1016bad76  push    r13
0x1016bad78  push    r14
0x1016bad7a  push    r15
0x1016bad7c  mov     eax, 2CE0h
0x1016bad81  call    _alloca_probe
0x1016bad86  sub     rsp, rax
0x1016bad89  mov     [rsp+2D18h+var_23C8], 0FFFFFFFFFFFFFFFEh
0x1016bad95  mov     rax, cs:__security_cookie
0x1016bad9c  xor     rax, rsp
0x1016bad9f  mov     [rsp+2D18h+var_48], rax
0x1016bada7  mov     rsi, r9
0x1016badaa  mov     [rsp+2D18h+var_2C70], r9
0x1016badb2  mov     [rsp+2D18h+var_2B60], r8
0x1016badba  mov     [rsp+2D18h+var_2BB0], rdx
0x1016badc2  mov     rdi, rcx
0x1016badc5  mov     [rsp+2D18h+var_2B78], rcx
0x1016badcd  mov     r15, [rsp+2D18h+arg_20]
0x1016badd5  mov     [rsp+2D18h+var_2B18], r15
0x1016baddd  mov     rax, [rsp+2D18h+arg_28]
0x1016bade5  mov     [rsp+2D18h+var_2B68], rax
0x1016baded  mov     rax, [rsp+2D18h+arg_30]
0x1016badf5  mov     [rsp+2D18h+var_2C88], rax
0x1016badfd  mov     rax, [rsp+2D18h+arg_48]
0x1016bae05  mov     [rsp+2D18h+var_2A88], rax
0x1016bae0d  mov     rax, [rsp+2D18h+arg_50]
0x1016bae15  mov     [rsp+2D18h+var_2C68], rax
0x1016bae1d  xor     r12d, r12d
0x1016bae20  mov     [rsp+2D18h+var_2CA8], r12d
0x1016bae25  mov     r14, [rcx+30h]
0x1016bae29  mov     [rsp+2D18h+var_2B58], r14
0x1016bae31  mov     [rsp+2D18h+var_2880], rax
0x1016bae39  mov     [rsp+2D18h+var_2BA0], r12
0x1016bae41  mov     [rsp+2D18h+var_284C], r12
0x1016bae49  lea     rbx, [r9+2]
0x1016bae4d  mov     [rsp+2D18h+var_2BD0], rbx
0x1016bae55  lea     rdx, [rsp+2D18h+var_2B80]
0x1016bae5d  mov     rcx, rbx
0x1016bae60  cmp     [r9], r12w
0x1016bae64  jnz     short loc_1016BAE6D
0x1016bae66  call    ?GetXdesTs@FixedVarRecord@@AEBA?AVXdesTs@@XZ; FixedVarRecord::GetXdesTs(void)
0x1016bae6b  jmp     short loc_1016BAE72
0x1016bae6d  call    ?GetXdesTs@CDRecord@@AEBA?AVXdesTs@@XZ; CDRecord::GetXdesTs(void)
0x1016bae72  mov     r9d, [rsp+2D18h+var_2B80]
0x1016bae7a  movzx   r8d, [rsp+2D18h+var_2B7C]
0x1016bae83  mov     [rsp+2D18h+var_2AF0], r9d
0x1016bae8b  mov     [rsp+2D18h+var_2AEC], r8w
0x1016bae94  movzx   edx, word ptr [rsi]
0x1016bae97  mov     rax, [rsi+8]
0x1016bae9b  movzx   ecx, byte ptr [rax]
0x1016bae9e  test    dx, dx
0x1016baea1  jnz     short loc_1016BAEA8
0x1016baea3  shr     ecx, 6
0x1016baea6  jmp     short loc_1016BAEAA
0x1016baea8  shr     ecx, 1
0x1016baeaa  and     ecx, 1
0x1016baead  mov     [rsp+2D18h+var_2878], ecx
0x1016baeb4  test    ecx, ecx
0x1016baeb6  jz      loc_1016BEB10
0x1016baebc  mov     [rsp+2D18h+var_2B08], r12d
0x1016baec4  mov     [rsp+2D18h+var_2B04], r12w
0x1016baecd  test    r8w, r8w
0x1016baed1  jnz     short loc_1016BAEDC
0x1016baed3  test    r9d, r9d
0x1016baed6  jz      loc_1016BEB10
0x1016baedc  mov     rcx, rbx
0x1016baedf  test    dx, dx
0x1016baee2  lea     rdx, [rsp+2D18h+var_2AB0]
0x1016baeea  jnz     short loc_1016BAEF3
0x1016baeec  call    ?GetVersionRecPtr@FixedVarRecord@@AEBA?AVVersionRecPtr@@XZ; FixedVarRecord::GetVersionRecPtr(void)
0x1016baef1  jmp     short loc_1016BAEF8
0x1016baef3  call    ?GetVersionRecPtr@CDRecord@@AEBA?AVVersionRecPtr@@XZ; CDRecord::GetVersionRecPtr(void)
0x1016baef8  lea     rax, [rsp+2D18h+var_2AB0]
0x1016baf00  mov     [rsp+2D18h+var_23B8], rax
0x1016baf08  lea     rcx, [r14+19C8h]
0x1016baf0f  lea     r8, [rsp+2D18h+var_2AB0]
0x1016baf17  lea     rdx, [rsp+2D18h+var_2AF0]
0x1016baf1f  call    ?GetRowAbortState@XdesMgr@@QEAA?AW4XdesAbortState@@AEBVXdesId@@AEBVVersionRecPtr@@_N@Z; XdesMgr::GetRowAbortState(XdesId const &,VersionRecPtr const &,bool)
0x1016baf24  test    eax, eax
0x1016baf26  jz      loc_1016BEB10
0x1016baf2c  cmp     byte ptr [r14+2050h], 0
0x1016baf34  jz      short loc_1016BAF55
0x1016baf36  mov     edx, 0Ah; int
0x1016baf3b  mov     ecx, 298h; unsigned int
0x1016baf40  lea     r8d, [rdx-7]; int
0x1016baf44  call    ?scierrlogwithstate@@YAXKHHZZ; scierrlogwithstate(ulong,int,int,...)
0x1016baf49  mov     rcx, [r14+6B0h]; this
0x1016baf50  call    ?RaiseReadonlyDbError@DBTABLE@@QEBAXXZ; DBTABLE::RaiseReadonlyDbError(void)
0x1016baf55  cmp     word ptr [rsi], 0
0x1016baf59  jnz     loc_1016BB90F
0x1016baf5f  mov     rdi, rbx
0x1016baf62  mov     [rsp+2D18h+var_2CA0], rbx
0x1016baf67  lea     r14, [rbx+2]
0x1016baf6b  mov     [rsp+2D18h+var_2C80], r14
0x1016baf73  cmp     dword ptr [r14], 0
0x1016baf77  jnz     loc_1016BB549
0x1016baf7d  xor     r15d, r15d
0x1016baf80  mov     [rsp+2D18h+var_2CB4], r15d
0x1016baf85  mov     [rbx], r15w
0x1016baf89  mov     edx, [rbx+0Eh]
0x1016baf8c  lea     r13, [rbx+12h]
0x1016baf90  mov     [r13+0], edx
0x1016baf94  lea     r12, [rbx+6]
0x1016baf98  mov     rcx, [r12]
0x1016baf9c  test    byte ptr [rcx], 10h
0x1016baf9f  jz      short loc_1016BAFBB
0x1016bafa1  mov     eax, [rbx+0Eh]
0x1016bafa4  movzx   ecx, word ptr [rcx+rax]
0x1016bafa8  add     ecx, 7
0x1016bafab  shr     ecx, 3
0x1016bafae  add     edx, 2
0x1016bafb1  add     edx, ecx
0x1016bafb3  mov     [r13+0], edx
0x1016bafb7  mov     rcx, [r12]
0x1016bafbb  test    byte ptr [rcx], 20h
0x1016bafbe  jz      loc_1016BB5B2
0x1016bafc4  mov     eax, edx
0x1016bafc6  add     rax, rcx
0x1016bafc9  mov     [rsp+2D18h+var_2A68], rax
0x1016bafd1  movzx   eax, word ptr [rax]
0x1016bafd4  lea     r14, [rbx+1Ah]
0x1016bafd8  mov     [r14], ax
0x1016bafdc  test    ax, ax
0x1016bafdf  jnz     loc_1016BB0F9
0x1016bafe5  mov     [rsp+2D18h+var_2CB4], 1
0x1016bafed  cmp     cs:byte_10316E8D7, r15b
0x1016baff4  jnz     short loc_1016BB00C
0x1016baff6  movzx   eax, byte ptr cs:qword_10317B120
0x1016baffd  mov     [rsp+2D18h+var_2C3F], al
0x1016bb004  test    al, 1
0x1016bb006  jz      loc_1016BB0EB
0x1016bb00c  mov     [rsp+2D18h+var_2874], 58h ; 'X'
0x1016bb017  mov     r8, gs:58h
0x1016bb020  mov     [rsp+2D18h+var_23B0], r8
0x1016bb028  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016bb02f  mov     ecx, [rax]
0x1016bb031  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016bb038  mov     edx, [rax]
0x1016bb03a  add     rdx, [r8+rcx*8]
0x1016bb03e  mov     [rsp+2D18h+var_23A8], rdx
0x1016bb046  mov     [rsp+2D18h+var_2318], rdx
0x1016bb04e  mov     rax, [rdx+8]
0x1016bb052  mov     [rsp+2D18h+var_23C0], rax
0x1016bb05a  mov     [rsp+2D18h+var_23A0], rax
0x1016bb062  test    rax, rax
0x1016bb065  jz      short loc_1016BB0DE
0x1016bb067  mov     rcx, [rax+60h]
0x1016bb06b  mov     [rsp+2D18h+var_2938], rcx
0x1016bb073  test    rcx, rcx
0x1016bb076  jz      short loc_1016BB0E6
0x1016bb078  cmp     [rcx+499h], r15b
0x1016bb07f  jz      short loc_1016BB0E6
0x1016bb081  cmp     cs:byte_10316E7C7, r15b
0x1016bb088  jnz     short loc_1016BB0B8
0x1016bb08a  movzx   eax, byte ptr cs:qword_10317B120
0x1016bb091  shr     al, 1
0x1016bb093  mov     [rsp+2D18h+var_2C18], al
0x1016bb09a  test    al, 1
0x1016bb09c  jnz     short loc_1016BB0B8
0x1016bb09e  mov     edx, 44h ; 'D'
0x1016bb0a3  lea     ecx, [rdx-22h]
0x1016bb0a6  mov     r9d, 3EBh
0x1016bb0ac  lea     r8d, [rdx-2Fh]
0x1016bb0b0  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016bb0b6  jmp     short loc_1016BB0E6
0x1016bb0b8  mov     [rsp+2D18h+var_2CF8], r15
0x1016bb0bd  mov     r9d, 7DAh
0x1016bb0c3  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x1016bb0ca  lea     rdx, aFalse; "false"
0x1016bb0d1  mov     ecx, 1
0x1016bb0d6  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1016bb0dc  jmp     short loc_1016BB0E6
0x1016bb0de  mov     [rsp+2D18h+var_2938], r15
0x1016bb0e6  mov     rdi, [rsp+2D18h+var_2CA0]
0x1016bb0eb  mov     edx, 3
0x1016bb0f0  mov     rcx, [r12]
0x1016bb0f4  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x1016bb0f9  movzx   edx, word ptr [r14]
0x1016bb0fd  mov     eax, [r13+0]
0x1016bb101  inc     edx
0x1016bb103  lea     edx, [rax+rdx*2]
0x1016bb106  lea     r15, [rdi+16h]
0x1016bb10a  mov     [r15], edx
0x1016bb10d  cmp     edx, 1F9Eh
0x1016bb113  jbe     loc_1016BB234
0x1016bb119  inc     [rsp+2D18h+var_2CB4]
0x1016bb11d  cmp     cs:byte_10316E8D7, 0
0x1016bb124  jnz     short loc_1016BB13F
0x1016bb126  movzx   eax, byte ptr cs:qword_10317B120
0x1016bb12d  mov     [rsp+2D18h+var_2C17], al
0x1016bb134  test    al, 1
0x1016bb136  jnz     short loc_1016BB13F
0x1016bb138  xor     esi, esi
0x1016bb13a  jmp     loc_1016BB222
0x1016bb13f  mov     [rsp+2D18h+var_2870], 58h ; 'X'
0x1016bb14a  mov     r8, gs:58h
0x1016bb153  mov     [rsp+2D18h+var_2838], r8
0x1016bb15b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016bb162  mov     ecx, [rax]
0x1016bb164  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016bb16b  mov     edx, [rax]
0x1016bb16d  add     rdx, [r8+rcx*8]
0x1016bb171  mov     [rsp+2D18h+var_2830], rdx
0x1016bb179  mov     [rsp+2D18h+var_2828], rdx
0x1016bb181  mov     rax, [rdx+8]
0x1016bb185  mov     [rsp+2D18h+var_2820], rax
0x1016bb18d  mov     [rsp+2D18h+var_2818], rax
0x1016bb195  test    rax, rax
0x1016bb198  jz      short loc_1016BB213
0x1016bb19a  mov     rcx, [rax+60h]
0x1016bb19e  mov     [rsp+2D18h+var_2930], rcx
0x1016bb1a6  test    rcx, rcx
0x1016bb1a9  jz      short loc_1016BB1E9
0x1016bb1ab  cmp     byte ptr [rcx+499h], 0
0x1016bb1b2  jz      short loc_1016BB1E9
0x1016bb1b4  cmp     cs:byte_10316E7C7, 0
0x1016bb1bb  jnz     short loc_1016BB1ED
0x1016bb1bd  movzx   eax, byte ptr cs:qword_10317B120
0x1016bb1c4  shr     al, 1
0x1016bb1c6  mov     [rsp+2D18h+var_2C16], al
0x1016bb1cd  test    al, 1
0x1016bb1cf  jnz     short loc_1016BB1ED
0x1016bb1d1  mov     edx, 44h ; 'D'
0x1016bb1d6  lea     ecx, [rdx-22h]
0x1016bb1d9  mov     r9d, 3ECh
0x1016bb1df  lea     r8d, [rdx-2Fh]
0x1016bb1e3  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016bb1e9  xor     esi, esi
0x1016bb1eb  jmp     short loc_1016BB21D
0x1016bb1ed  xor     esi, esi
0x1016bb1ef  mov     [rsp+2D18h+var_2CF8], rsi
0x1016bb1f4  mov     r9d, 7E1h
0x1016bb1fa  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x1016bb201  lea     rdx, aFalse; "false"
0x1016bb208  lea     ecx, [rsi+1]
0x1016bb20b  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1016bb211  jmp     short loc_1016BB21D
0x1016bb213  xor     esi, esi
0x1016bb215  mov     [rsp+2D18h+var_2930], rsi
0x1016bb21d  mov     rdi, [rsp+2D18h+var_2CA0]
0x1016bb222  mov     ebx, 4
0x1016bb227  mov     edx, ebx
0x1016bb229  mov     rcx, [r12]
0x1016bb22d  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x1016bb232  jmp     short loc_1016BB23B
0x1016bb234  mov     ebx, 4
0x1016bb239  xor     esi, esi
0x1016bb23b  movzx   ecx, word ptr [r14]
0x1016bb23f  mov     rax, [rsp+2D18h+var_2A68]
0x1016bb247  movzx   edx, word ptr [rax+rcx*2]
0x1016bb24b  mov     [rsp+2D18h+var_2A8C], dx
0x1016bb253  and     edx, 7FFFh
0x1016bb259  mov     rax, [rsp+2D18h+var_2C80]
0x1016bb261  mov     [rax], edx
0x1016bb263  cmp     [r15], edx
0x1016bb266  jbe     loc_1016BB379
0x1016bb26c  inc     [rsp+2D18h+var_2CB4]
0x1016bb270  cmp     cs:byte_10316E8D7, 0
0x1016bb277  jnz     short loc_1016BB28F
0x1016bb279  movzx   eax, byte ptr cs:qword_10317B120
0x1016bb280  mov     [rsp+2D18h+var_2C08], al
0x1016bb287  test    al, 1
0x1016bb289  jz      loc_1016BB36E
0x1016bb28f  mov     [rsp+2D18h+var_286C], 58h ; 'X'
0x1016bb29a  mov     r8, gs:58h
0x1016bb2a3  mov     [rsp+2D18h+var_2810], r8
0x1016bb2ab  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016bb2b2  mov     ecx, [rax]
0x1016bb2b4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016bb2bb  mov     edx, [rax]
0x1016bb2bd  add     rdx, [r8+rcx*8]
0x1016bb2c1  mov     [rsp+2D18h+var_2808], rdx
0x1016bb2c9  mov     [rsp+2D18h+var_2800], rdx
0x1016bb2d1  mov     rax, [rdx+8]
0x1016bb2d5  mov     [rsp+2D18h+var_27F8], rax
0x1016bb2dd  mov     [rsp+2D18h+var_27F0], rax
0x1016bb2e5  test    rax, rax
0x1016bb2e8  jz      short loc_1016BB361
0x1016bb2ea  mov     rcx, [rax+60h]
0x1016bb2ee  mov     [rsp+2D18h+var_2928], rcx
0x1016bb2f6  test    rcx, rcx
0x1016bb2f9  jz      short loc_1016BB369
0x1016bb2fb  cmp     byte ptr [rcx+499h], 0
0x1016bb302  jz      short loc_1016BB369
0x1016bb304  cmp     cs:byte_10316E7C7, 0
0x1016bb30b  jnz     short loc_1016BB33B
0x1016bb30d  movzx   eax, byte ptr cs:qword_10317B120
0x1016bb314  shr     al, 1
0x1016bb316  mov     [rsp+2D18h+var_2C07], al
0x1016bb31d  test    al, 1
0x1016bb31f  jnz     short loc_1016BB33B
0x1016bb321  mov     edx, 44h ; 'D'
0x1016bb326  lea     ecx, [rdx-22h]
0x1016bb329  mov     r9d, 3ECh
0x1016bb32f  lea     r8d, [rdx-2Fh]
0x1016bb333  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016bb339  jmp     short loc_1016BB369
  ... truncated ...
```
