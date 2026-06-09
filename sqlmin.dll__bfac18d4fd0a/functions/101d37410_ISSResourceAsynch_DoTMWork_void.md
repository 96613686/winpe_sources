# ISSResourceAsynch::DoTMWork(void)

- ea: `0x101d37410`
- end: `0x101d38aff`
- name: `?DoTMWork@ISSResourceAsynch@@QEAAXXZ`
- size: `5871`
- prototype: `void __fastcall(ISSResourceAsynch *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x101d364b0`

## callees

- `0x100401010`
- `0x100475060`
- `0x10063e990`
- `0x101d30770`
- `0x101d308c0`
- `0x101d310e0`
- `0x101d31ff0`
- `0x101d32110`
- `0x101d32380`
- `0x101d33ef0`
- `0x101d35430`
- `0x101d35670`
- `0x101d35f00`
- `0x101d371e0`
- `0x101d37310`
- `0x101d37410`
- `0x101d38b10`
- `0x101d3b040`
- `0x101d545f0`
- `0x101d54950`
- `0x101d54b70`
- `0x101d634e0`
- `0x1023aecb0`

## import_xrefs

- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101d38a76`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x101d378e1`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x101d37e70`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x101d381e5`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x101d38454`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x101d3868e`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x101d388b8`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x101d37b01`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x101d37b01`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d38a62`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d38a62`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d375cb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d375f5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37671`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d376d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37700`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d378a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37c1e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37c85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37e6a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37fbd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d38032`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d381c1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d38332`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d38399`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d38412`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d3861c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d375cb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d375f5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37671`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d376d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37700`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d378a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37c1e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37c85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37e6a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d37fbd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d38032`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d381c1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d38332`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d38399`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d38412`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d3861c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d37506`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d3778a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d37a52`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d37d4e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d380d6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d385bb`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d3888b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d37506`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d3778a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d37a52`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d37d4e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d380d6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d385bb`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d3888b`
- `sqldk!SystemThread_TlsIndex` at `0x101d3743f`
- `sqldk!SystemThread_TlsIndex` at `0x101d37474`
- `sqldk!SystemThread_TlsIndex` at `0x101d374d7`
- `sqldk!SystemThread_TlsIndex` at `0x101d37742`
- `sqldk!SystemThread_TlsIndex` at `0x101d3784c`
- `sqldk!SystemThread_TlsIndex` at `0x101d3791e`
- `sqldk!SystemThread_TlsIndex` at `0x101d37a03`
- `sqldk!SystemThread_TlsIndex` at `0x101d37d07`
- `sqldk!SystemThread_TlsIndex` at `0x101d37ea7`
- `sqldk!SystemThread_TlsIndex` at `0x101d3808f`
- `sqldk!SystemThread_TlsIndex` at `0x101d3821c`
- `sqldk!SystemThread_TlsIndex` at `0x101d3848e`
- `sqldk!SystemThread_TlsIndex` at `0x101d38574`
- `sqldk!SystemThread_TlsIndex` at `0x101d38637`
- `sqldk!SystemThread_TlsIndex` at `0x101d386cd`
- `sqldk!SystemThread_TlsIndex` at `0x101d3879a`
- `sqldk!SystemThread_TlsIndex` at `0x101d38844`
- `sqldk!SystemThread_TlsIndex` at `0x101d388ef`
- `sqldk!SystemThread_TlsIndex` at `0x101d38a2a`
- `sqldk!SystemThread_TlsIndex` at `0x101d38ac7`
- `sqldk!SystemThread_TlsOffset` at `0x101d37448`
- `sqldk!SystemThread_TlsOffset` at `0x101d3747d`
- `sqldk!SystemThread_TlsOffset` at `0x101d374e0`
- `sqldk!SystemThread_TlsOffset` at `0x101d3774b`
- `sqldk!SystemThread_TlsOffset` at `0x101d37855`
- `sqldk!SystemThread_TlsOffset` at `0x101d37927`
- `sqldk!SystemThread_TlsOffset` at `0x101d37a0c`
- `sqldk!SystemThread_TlsOffset` at `0x101d37d10`
- `sqldk!SystemThread_TlsOffset` at `0x101d37eb0`
- `sqldk!SystemThread_TlsOffset` at `0x101d38098`
- `sqldk!SystemThread_TlsOffset` at `0x101d38225`
- `sqldk!SystemThread_TlsOffset` at `0x101d38497`
- `sqldk!SystemThread_TlsOffset` at `0x101d3857d`
- `sqldk!SystemThread_TlsOffset` at `0x101d38640`
- `sqldk!SystemThread_TlsOffset` at `0x101d386d6`
- `sqldk!SystemThread_TlsOffset` at `0x101d387a3`
- `sqldk!SystemThread_TlsOffset` at `0x101d3884d`
- `sqldk!SystemThread_TlsOffset` at `0x101d388f8`
- `sqldk!SystemThread_TlsOffset` at `0x101d38a33`
- `sqldk!SystemThread_TlsOffset` at `0x101d38ad0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101d37807`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101d37815`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101d37ce3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101d37807`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101d37815`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101d37ce3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d37498`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d38a4c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d37498`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d38a4c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101d38a82`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101d38a82`

## string_xrefs

- `0x101d37d73`: `commit`
- `0x101d376ca`: `(m_state == ACTIVE) || (m_state == COMMITTED) || (m_state == ABORTED) || (m_state == RECOVERED) || ((m_state == PREPARED) && m_transaction->HasEnded ())`
- `0x101d375e9`: `m_fSystemThreadActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
void __fastcall ISSResourceAsynch::DoTMWork(ISSResourceAsynch *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rax
  struct CSessionTraceFlags *v5; // rcx
  int **v6; // rcx
  const char *v7; // rbx
  const void *v8; // rax
  struct CDTCState *DTCStateByRmId; // rax
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // ecx
  __int64 v16; // rax
  struct CSessionTraceFlags *v17; // rcx
  const void *v18; // rax
  CDTCState *v19; // rax
  CDTCState *v20; // rbx
  _QWORD *v21; // r9
  const struct _GUID *v22; // r13
  _QWORD *v23; // rdx
  __int64 v24; // rax
  _DWORD *v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rsi
  int v28; // eax
  __int64 v29; // rbx
  __int64 v30; // rsi
  int v31; // eax
  __int64 v32; // rax
  struct CSessionTraceFlags *v33; // rcx
  const void *v34; // rax
  struct CDTCState *v35; // rbx
  unsigned int v36; // r14d
  __int64 v37; // r15
  unsigned int v38; // esi
  struct FullXact *v39; // r8
  struct XactWorkspace *v40; // r14
  __int64 v41; // rax
  struct CSessionTraceFlags *v42; // rcx
  const void *v43; // r8
  const char *v44; // rdx
  int v45; // eax
  __int64 v46; // rax
  _DWORD *v47; // rax
  _QWORD *v48; // rax
  const struct _GUID *v49; // r14
  __int64 v50; // rbx
  __int64 v51; // rsi
  int v52; // eax
  _QWORD *v53; // rax
  const struct _GUID *v54; // r14
  __int64 v55; // rbx
  __int64 v56; // rsi
  int v57; // eax
  struct FullXact *v58; // r8
  struct XactWorkspace *v59; // rbx
  __int64 v60; // rbx
  int v61; // eax
  DtcXactRMOnly *v62; // rcx
  __int64 v63; // rax
  struct CSessionTraceFlags *v64; // rcx
  const void *v65; // rax
  __int64 v66; // rax
  _DWORD *v67; // rax
  _QWORD *v68; // rax
  const struct _GUID *v69; // r14
  __int64 v70; // rbx
  __int64 v71; // rsi
  int v72; // eax
  _QWORD *v73; // rax
  const struct _GUID *v74; // r14
  __int64 v75; // rbx
  __int64 v76; // rsi
  int v77; // eax
  struct FullXact *v78; // r8
  struct XactWorkspace *v79; // rbx
  _QWORD *v80; // r9
  const struct _GUID *v81; // r13
  const struct _GUID *v82; // r14
  _QWORD *v83; // rdx
  __int64 v84; // rax
  _DWORD *v85; // rax
  __int64 v86; // rbx
  __int64 v87; // rsi
  int v88; // eax
  __int64 v89; // rsi
  __int64 v90; // rbx
  int v91; // eax
  __int64 v92; // rax
  struct CSessionTraceFlags *v93; // rcx
  const void *v94; // rbx
  const void *v95; // rax
  __int64 v96; // rdx
  _QWORD *v97; // r8
  unsigned __int8 v98; // al
  int v99; // r14d
  __int64 v100; // rax
  _DWORD *v101; // rax
  __int64 v102; // rbx
  __int64 v103; // rsi
  int v104; // eax
  __int64 v105; // rsi
  unsigned __int8 v106; // bl
  int v107; // eax
  __int64 v108; // rax
  _DWORD *v109; // rax
  __int64 v110; // rbx
  __int64 v111; // rsi
  int v112; // eax
  __int64 v113; // rax
  __int64 v114; // rax
  struct CSessionTraceFlags *v115; // rcx
  const void *v116; // rax
  __int64 v117; // rax
  _DWORD *v118; // rax
  __int64 v119; // rbx
  __int64 v120; // rsi
  int v121; // eax
  int v122; // ecx
  __int64 v123; // rbx
  struct Worker *v124; // rcx
  int v125; // r8d
  int v126; // [rsp+20h] [rbp-4C8h]
  int v127; // [rsp+38h] [rbp-4B0h]
  int v128; // [rsp+44h] [rbp-4A4h]
  int v129; // [rsp+50h] [rbp-498h]
  __int64 v130; // [rsp+58h] [rbp-490h]
  int v131; // [rsp+B8h] [rbp-430h] BYREF
  __int64 v132; // [rsp+C0h] [rbp-428h]
  __int64 v133; // [rsp+C8h] [rbp-420h]
  __int64 v134; // [rsp+D0h] [rbp-418h]
  __int64 v135; // [rsp+D8h] [rbp-410h]
  int v136; // [rsp+E0h] [rbp-408h] BYREF
  __int64 v137; // [rsp+E8h] [rbp-400h]
  __int64 v138; // [rsp+F0h] [rbp-3F8h]
  __int64 v139; // [rsp+F8h] [rbp-3F0h]
  __int64 v140; // [rsp+100h] [rbp-3E8h]
  int v141; // [rsp+108h] [rbp-3E0h] BYREF
  __int64 v142; // [rsp+110h] [rbp-3D8h]
  __int64 v143; // [rsp+118h] [rbp-3D0h]
  __int64 v144; // [rsp+120h] [rbp-3C8h]
  __int64 v145; // [rsp+128h] [rbp-3C0h]
  int v146; // [rsp+130h] [rbp-3B8h] BYREF
  __int64 v147; // [rsp+138h] [rbp-3B0h]
  __int64 v148; // [rsp+140h] [rbp-3A8h]
  __int64 v149; // [rsp+148h] [rbp-3A0h]
  __int64 v150; // [rsp+150h] [rbp-398h]
  void *v151; // [rsp+158h] [rbp-390h]
  __int64 v152; // [rsp+160h] [rbp-388h]
  _QWORD *v153; // [rsp+168h] [rbp-380h]
  __int64 *v154; // [rsp+170h] [rbp-378h]
  __int64 v155; // [rsp+178h] [rbp-370h]
  __int64 v156; // [rsp+180h] [rbp-368h]
  _QWORD *v157; // [rsp+188h] [rbp-360h]
  __int64 v158; // [rsp+190h] [rbp-358h]
  __int64 v159; // [rsp+198h] [rbp-350h]
  _DWORD *v160; // [rsp+1A0h] [rbp-348h]
  _QWORD *v161; // [rsp+1A8h] [rbp-340h]
  __int64 *v162; // [rsp+1B0h] [rbp-338h]
  __int64 v163; // [rsp+1B8h] [rbp-330h]
  struct CSessionTraceFlags *v164; // [rsp+1C0h] [rbp-328h]
  struct CDTCState *v165; // [rsp+1C8h] [rbp-320h]
  __int64 v166; // [rsp+1D0h] [rbp-318h]
  __int64 v167; // [rsp+1D8h] [rbp-310h]
  _QWORD *v168; // [rsp+1E0h] [rbp-308h]
  __int64 *v169; // [rsp+1E8h] [rbp-300h]
  __int64 v170; // [rsp+1F0h] [rbp-2F8h]
  struct CSessionTraceFlags *v171; // [rsp+1F8h] [rbp-2F0h]
  __int64 v172; // [rsp+200h] [rbp-2E8h]
  __int64 v173; // [rsp+208h] [rbp-2E0h]
  _QWORD *v174; // [rsp+210h] [rbp-2D8h]
  __int64 v175; // [rsp+218h] [rbp-2D0h]
  __int64 v176; // [rsp+220h] [rbp-2C8h]
  _DWORD *v177; // [rsp+228h] [rbp-2C0h]
  __int64 v178; // [rsp+230h] [rbp-2B8h]
  __int64 v179; // [rsp+238h] [rbp-2B0h]
  __int64 v180; // [rsp+240h] [rbp-2A8h]
  _QWORD *v181; // [rsp+248h] [rbp-2A0h]
  __int64 *v182; // [rsp+250h] [rbp-298h]
  __int64 v183; // [rsp+258h] [rbp-290h]
  struct CSessionTraceFlags *v184; // [rsp+260h] [rbp-288h]
  __int64 v185; // [rsp+268h] [rbp-280h]
  __int64 v186; // [rsp+270h] [rbp-278h]
  _QWORD *v187; // [rsp+278h] [rbp-270h]
  __int64 v188; // [rsp+280h] [rbp-268h]
  __int64 v189; // [rsp+288h] [rbp-260h]
  _DWORD *v190; // [rsp+290h] [rbp-258h]
  __int64 v191; // [rsp+298h] [rbp-250h]
  __int64 v192; // [rsp+2A0h] [rbp-248h]
  __int64 v193; // [rsp+2A8h] [rbp-240h]
  __int64 v194; // [rsp+2B0h] [rbp-238h]
  _QWORD *v195; // [rsp+2B8h] [rbp-230h]
  __int64 v196; // [rsp+2C0h] [rbp-228h]
  __int64 v197; // [rsp+2C8h] [rbp-220h]
  _DWORD *v198; // [rsp+2D0h] [rbp-218h]
  _QWORD *v199; // [rsp+2D8h] [rbp-210h]
  __int64 *v200; // [rsp+2E0h] [rbp-208h]
  __int64 v201; // [rsp+2E8h] [rbp-200h]
  struct CSessionTraceFlags *v202; // [rsp+2F0h] [rbp-1F8h]
  _QWORD *v203; // [rsp+2F8h] [rbp-1F0h]
  __int64 *v204; // [rsp+300h] [rbp-1E8h]
  __int64 v205; // [rsp+308h] [rbp-1E0h]
  __int64 v206; // [rsp+310h] [rbp-1D8h]
  _QWORD *v207; // [rsp+318h] [rbp-1D0h]
  __int64 v208; // [rsp+320h] [rbp-1C8h]
  __int64 v209; // [rsp+328h] [rbp-1C0h]
  _DWORD *v210; // [rsp+330h] [rbp-1B8h]
  _QWORD *v211; // [rsp+338h] [rbp-1B0h]
  __int64 v212; // [rsp+340h] [rbp-1A8h]
  __int64 v213; // [rsp+348h] [rbp-1A0h]
  _DWORD *v214; // [rsp+350h] [rbp-198h]
  _QWORD *v215; // [rsp+358h] [rbp-190h]
  __int64 *v216; // [rsp+360h] [rbp-188h]
  __int64 v217; // [rsp+368h] [rbp-180h]
  struct CSessionTraceFlags *v218; // [rsp+370h] [rbp-178h]
  _QWORD *v219; // [rsp+378h] [rbp-170h]
  __int64 v220; // [rsp+380h] [rbp-168h]
  __int64 v221; // [rsp+388h] [rbp-160h]
  _DWORD *v222; // [rsp+390h] [rbp-158h]
  __int64 v223; // [rsp+398h] [rbp-150h]
  __int64 v224; // [rsp+3A0h] [rbp-148h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+3A8h] [rbp-140h]
  __int64 *v226; // [rsp+3B0h] [rbp-138h]
  __int64 v227; // [rsp+3B8h] [rbp-130h]
  struct CSessionTraceFlags *v228; // [rsp+3C0h] [rbp-128h]
  _BYTE v229[24]; // [rsp+3C8h] [rbp-120h] BYREF
  __int64 v230; // [rsp+3E0h] [rbp-108h]
  _BYTE v231[24]; // [rsp+3E8h] [rbp-100h] BYREF
  __int64 v232; // [rsp+400h] [rbp-E8h]
  _BYTE v233[24]; // [rsp+408h] [rbp-E0h] BYREF
  __int64 v234; // [rsp+420h] [rbp-C8h]
  _BYTE v235[168]; // [rsp+440h] [rbp-A8h] BYREF
  char v236; // [rsp+4F8h] [rbp+10h]

  v206 = -2;
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset)
                       + 72LL)
           + 5081LL) = 1;
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  v130 = v3;
  v129 = *(_DWORD *)(v3 + 616) & 0x27 ^ 0x27;
  *(_DWORD *)(v3 + 616) |= 0x27u;
  if ( (byte_10317AFA6 & 0x20) != 0
    || (v4 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset)) != 0
    && (v5 = **(struct CSessionTraceFlags ***)(v4 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v5, 0x2135u) )
  {
    v6 = (int **)*((_QWORD *)this + 2);
    v7 = (const char *)(&BaseXact::sm_xactStateName)[*v6[9]];
    v8 = (const void *)(*((__int64 (__fastcall **)(int **))*v6 + 89))(v6);
    traceCall("DOTMWORK called in %s state, ITransaction* @%p", v7, v8);
  }
  v236 = 0;
  DTCStateByRmId = GetDTCStateByRmId((const struct _GUID *)((char *)this + 84), 1);
  if ( DTCStateByRmId )
  {
    v236 = *((_BYTE *)DTCStateByRmId + 348);
    CDTCState::Release(DTCStateByRmId);
  }
  ISSResourceAsynch::Lock(this);
  while ( *((_DWORD *)this + 11) )
  {
    if ( *((_DWORD *)this + 20) != 1 )
      utassert_fail(1u, "TRUE == m_locked", "Sql\\Ntdbms\\storeng\\include\\xactimp.h", 1096, 0);
    if ( !*((_DWORD *)this + 17) )
      utassert_fail(1u, "m_fSystemThreadActive", "viperrm.cpp", 4036, 0);
    v10 = *((int *)this + 10);
    v11 = *((_DWORD *)this + v10 + 12);
    *((_DWORD *)this + 10) = ((int)v10 + 1) % 5;
    --*((_DWORD *)this + 11);
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 == 1 )
            {
              v223 = *((_QWORD *)this + 2);
              *(_DWORD *)(v223 + 416) |= 0x1000u;
              v15 = *((_DWORD *)this + 7);
              if ( v15 != 1
                && (unsigned int)(v15 - 3) > 2
                && (v15 != 2
                 || !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 336LL))(*((_QWORD *)this + 2))) )
              {
                utassert_fail(
                  1u,
                  "(m_state == ACTIVE) || (m_state == COMMITTED) || (m_state == ABORTED) || (m_state == RECOVERED) || ((m"
                  "_state == PREPARED) && m_transaction->HasEnded ())",
                  "viperrm.cpp",
                  4408,
                  0);
              }
              if ( *((_DWORD *)this + 2) )
                utassert_fail(1u, "m_refCount == 0", "viperrm.cpp", 4409, 0);
              *((_DWORD *)this + 17) = 0;
              v224 = *((_QWORD *)this + 2);
              *(_DWORD *)(v224 + 416) |= 0x100000u;
              ISSResourceAsynch::UnLock(this);
              if ( (byte_10317AFA6 & 0x20) != 0
                || (ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer,
                    v226 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset),
                    v16 = *v226,
                    (v227 = v16) != 0)
                && (v17 = **(struct CSessionTraceFlags ***)(v16 + 56), (v228 = v17) != 0)
                && CSessionTraceFlags::CheckSessionTraceInternal(v17, 0x2135u) )
              {
                v18 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 712LL))(*((_QWORD *)this + 2));
                traceCall("DTC xact released. ITransaction* @%p", v18);
              }
              v19 = GetDTCStateByRmId((const struct _GUID *)((char *)this + 84), 1);
              v20 = v19;
              if ( v19 )
              {
                CDTCState::DecrementActiveXactCount(v19);
                CDTCState::Release(v20);
              }
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 544LL))(*((_QWORD *)this + 2));
              *(_QWORD *)this = &ISSResourceAsynch::`vftable';
              v151 = (void *)*((_QWORD *)this + 9);
              operator delete(v151, 0x28u);
              operator delete(this, 0x68u);
              v152 = v130 + 616;
              *(_DWORD *)(v130 + 616) &= ~v129;
              v153 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v154 = (__int64 *)(v153[SystemThread_TlsIndex] + SystemThread_TlsOffset);
              v155 = *v154;
              *(_BYTE *)(*(_QWORD *)(v155 + 72) + 5081LL) = 0;
              return;
            }
            utassert_fail(1u, "FALSE", "viperrm.cpp", 4431, "Invalid switch value");
          }
          else
          {
            if ( *((_DWORD *)this + 7) != 2 )
              utassert_fail(1u, "m_state == PREPARED", "viperrm.cpp", 4294, 0);
            v156 = *((_QWORD *)this + 2);
            *(_DWORD *)(v156 + 416) |= 0x800u;
            ISSResourceAsynch::UnLock(this);
            v21 = (_QWORD *)*((_QWORD *)this + 2);
            v22 = (const struct _GUID *)(v21[9] + 464LL);
            v23 = v21;
            if ( CommonGlobalState::m_ProfilerTraceEnabled && (dword_10316ECBC & 0x80000) != 0 )
            {
              v157 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v158 = v157[SystemThread_TlsIndex] + SystemThread_TlsOffset;
              v24 = *(_QWORD *)(v158 + 8);
              v159 = v24;
              if ( v24 && (v25 = *(_DWORD **)(v24 + 48), (v160 = v25) != 0) && !*v25 )
              {
                v26 = *((_QWORD *)this + 2);
                v27 = (*(__int64 (__fastcall **)(__int64))(*v21 + 312LL))(v26);
                v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 896LL))(v26);
                dtc_stateTrace(22, v22, v28, v27);
                v23 = (_QWORD *)*((_QWORD *)this + 2);
              }
              else
              {
                v23 = v21;
              }
            }
            v29 = *((_QWORD *)this + 2);
            v30 = (*(__int64 (__fastcall **)(_QWORD *))(*v23 + 312LL))(v23);
            v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 896LL))(v29);
            dtc_stateXEvent(0x16u, v22, (const struct _GUID *)((char *)this + 84), v31, v30, v236);
            if ( (byte_10317AFA6 & 0x20) != 0
              || (v161 = NtCurrentTeb()->ThreadLocalStoragePointer,
                  v162 = (__int64 *)(v161[SystemThread_TlsIndex] + SystemThread_TlsOffset),
                  v32 = *v162,
                  (v163 = v32) != 0)
              && (v33 = **(struct CSessionTraceFlags ***)(v32 + 56), (v164 = v33) != 0)
              && CSessionTraceFlags::CheckSessionTraceInternal(v33, 0x2135u) )
            {
              v34 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 712LL))(*((_QWORD *)this + 2));
              traceCall("DTC TMDown called. Recovery Initiated. ITransaction* @%p", v34);
            }
            v35 = GetDTCStateByRmId((const struct _GUID *)((char *)this + 84), 1);
            v165 = v35;
            if ( v35 )
            {
              while ( *((_DWORD *)v35 + 87) != 2 )
              {
                v131 = 4194507;
                v132 = 0;
                v134 = 0;
                v133 = 0;
                v135 = 0;
                LOBYTE(v126) = 1;
                if ( !(unsigned int)WaitableBase::Wait((char *)v35 + 216, 0, &v131, 0, v126) )
                  break;
                v136 = 4194656;
                v137 = 0;
                v139 = 0;
                v138 = 0;
                v140 = 0;
                SOS_Task::Sleep(100, &v136);
              }
              v166 = *((_QWORD *)this + 2);
              v36 = *(_DWORD *)(v166 + 344);
              v37 = *(_QWORD *)(v166 + 352);
              v167 = v37;
              while ( 1 )
              {
                v38 = CDTCState::ResolvePreparedXact(v35, v37, v36, v22);
                v127 = v38;
                if ( v38 != 3 )
                  break;
                v141 = 4194656;
                v142 = 0;
                v144 = 0;
                v143 = 0;
                v145 = 0;
                SOS_Task::Sleep(1000, &v141);
              }
            }
            else
            {
              v38 = 2;
              v127 = 2;
            }
            v39 = (struct FullXact *)*((_QWORD *)this + 2);
            v40 = (struct XactWorkspace *)*((_QWORD *)v39 + 10);
            if ( !v40 )
            {
              utassert_fail(1u, "dtcXactWorkspace", "viperrm.cpp", 4360, 0);
              v39 = (struct FullXact *)*((_QWORD *)this + 2);
            }
            AutoSetupEnvForDTCOperation::AutoSetupEnvForDTCOperation((AutoSetupEnvForDTCOperation *)v229, v40, v39);
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 2) + 320LL))(
              *((_QWORD *)this + 2),
              0,
              v230,
              0xFFFFFFFFLL);
            if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 504LL))(*((_QWORD *)this + 2)) )
              utassert_fail(1u, "0 == m_transaction->GetActiveWorkCount ()", "viperrm.cpp", 4373, 0);
            DtcXactRMOnly::HeuristicResolveDTCXact(*((_QWORD *)this + 2), v38);
            if ( v35 )
              CDTCState::decrementRecoveryCount(v35);
            AutoSetupEnvForDTCOperation::~AutoSetupEnvForDTCOperation((AutoSetupEnvForDTCOperation *)v229);
            if ( v35 )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)v35) )
              {
                CDTCState::~CDTCState(v35);
                operator delete(v35, 0x170u);
              }
              v38 = v127;
            }
            if ( (byte_10317AFA6 & 0x20) == 0 )
            {
              v168 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v169 = (__int64 *)(v168[SystemThread_TlsIndex] + SystemThread_TlsOffset);
              v41 = *v169;
              v170 = v41;
              if ( !v41 )
                goto LABEL_77;
              v42 = **(struct CSessionTraceFlags ***)(v41 + 56);
              v171 = v42;
              if ( !v42 || !CSessionTraceFlags::CheckSessionTraceInternal(v42, 0x2135u) )
                goto LABEL_77;
              v38 = v127;
            }
            v43 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 712LL))(*((_QWORD *)this + 2));
            v44 = "commit";
            if ( v38 == 2 )
              v44 = "abort";
            traceCall("In-doubt DTC xact was resloved to %s. ITransaction* @%p", v44, v43);
LABEL_77:
            ISSResourceAsynch::Lock(this);
            *((_DWORD *)this + 7) = 5;
            *(_DWORD *)(*((_QWORD *)this + 2) + 420LL) = 5;
            v172 = *((_QWORD *)this + 2);
            *(_DWORD *)(v172 + 416) |= 0x80000u;
          }
        }
        else
        {
          v173 = *((_QWORD *)this + 2);
          *(_DWORD *)(v173 + 416) |= 0x400u;
          ISSResourceAsynch::UnLock(this);
          v45 = *((_DWORD *)this + 7);
          if ( v45 == 4 )
          {
            log_unlocalized_systemmetadata(L"%ls", L"Unexpected Abort request received from DTC.\n");
            SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(v235, 536871466, 1);
            (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 328LL) + 40LL))(
              *(_QWORD *)(*((_QWORD *)this + 2) + 328LL),
              0);
            SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive((SOS_Task::AutoSwitchPreemptive *)v235);
            ISSResourceAsynch::Lock(this);
          }
          else
          {
            if ( (unsigned int)(v45 - 1) > 1 )
              utassert_fail(1u, "(m_state == ACTIVE) || (m_state == PREPARED)", "viperrm.cpp", 4176, 0);
            if ( CommonGlobalState::m_ProfilerTraceEnabled && (dword_10316ECBC & 0x80000) != 0 )
            {
              v174 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v175 = v174[SystemThread_TlsIndex] + SystemThread_TlsOffset;
              v46 = *(_QWORD *)(v175 + 8);
              v176 = v46;
              if ( v46 )
              {
                v47 = *(_DWORD **)(v46 + 48);
                v177 = v47;
                if ( v47 )
                {
                  if ( !*v47 )
                  {
                    v48 = (_QWORD *)*((_QWORD *)this + 2);
                    v178 = v48[9] + 464LL;
                    v49 = (const struct _GUID *)v178;
                    v50 = *((_QWORD *)this + 2);
                    v51 = (*(__int64 (__fastcall **)(__int64))(*v48 + 312LL))(v50);
                    v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 896LL))(v50);
                    dtc_stateTrace(16, v49, v52, v51);
                  }
                }
              }
            }
            v53 = (_QWORD *)*((_QWORD *)this + 2);
            v179 = v53[9] + 464LL;
            v54 = (const struct _GUID *)v179;
            v55 = *((_QWORD *)this + 2);
            v56 = (*(__int64 (__fastcall **)(__int64))(*v53 + 312LL))(v55);
            v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 896LL))(v55);
            dtc_stateXEvent(0x10u, v54, (const struct _GUID *)((char *)this + 84), v57, v56, v236);
            v58 = (struct FullXact *)*((_QWORD *)this + 2);
            v59 = (struct XactWorkspace *)*((_QWORD *)v58 + 10);
            if ( !v59 )
            {
              utassert_fail(1u, "dtcXactWorkspace", "viperrm.cpp", 4192, 0);
              v58 = (struct FullXact *)*((_QWORD *)this + 2);
            }
            AutoSetupEnvForDTCOperation::AutoSetupEnvForDTCOperation((AutoSetupEnvForDTCOperation *)v231, v59, v58);
            v60 = v232;
            while ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 2) + 320LL))(
                       *((_QWORD *)this + 2),
                       0,
                       v60,
                       0) )
            {
              (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 808LL))(*((_QWORD *)this + 2), 1);
              v146 = 4194655;
              v147 = 0;
              v149 = 0;
              v148 = 0;
              v150 = 0;
              SOS_Task::Sleep(3000, &v146);
            }
            if ( *((_DWORD *)this + 7) != 1
              && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 504LL))(*((_QWORD *)this + 2)) )
            {
              utassert_fail(
                1u,
                "(ACTIVE == m_state) || (0 == m_transaction->GetActiveWorkCount ())",
                "viperrm.cpp",
                4213,
                0);
            }
            v61 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 504LL))(*((_QWORD *)this + 2));
            v62 = (DtcXactRMOnly *)*((_QWORD *)this + 2);
            if ( v61 )
            {
              v180 = *((_QWORD *)this + 2);
              XactRM::DoomXact(*((_QWORD *)v62 + 9), *((_QWORD *)v62 + 41), 2);
              if ( (byte_10317AFA6 & 0x20) != 0
                || (v181 = NtCurrentTeb()->ThreadLocalStoragePointer,
                    v182 = (__int64 *)(v181[SystemThread_TlsIndex] + SystemThread_TlsOffset),
                    v63 = *v182,
                    (v183 = v63) != 0)
                && (v64 = **(struct CSessionTraceFlags ***)(v63 + 56), (v184 = v64) != 0)
                && CSessionTraceFlags::CheckSessionTraceInternal(v64, 0x2135u) )
              {
                v65 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 712LL))(*((_QWORD *)this + 2));
                traceCall("DTC xact doomed with enlist callback. ITransaction* @%p", v65);
              }
            }
            else
            {
              DtcXactRMOnly::RollbackDTCXact(v62);
            }
            AutoSetupEnvForDTCOperation::~AutoSetupEnvForDTCOperation((AutoSetupEnvForDTCOperation *)v231);
            ISSResourceAsynch::Lock(this);
            *((_DWORD *)this + 7) = 4;
            *(_DWORD *)(*((_QWORD *)this + 2) + 420LL) = 4;
            v185 = *((_QWORD *)this + 2);
            *(_DWORD *)(v185 + 416) |= 0x40000u;
          }
        }
      }
      else
      {
        if ( *((_DWORD *)this + 7) != 2 )
          utassert_fail(1u, "m_state == PREPARED", "viperrm.cpp", 4254, 0);
        v186 = *((_QWORD *)this + 2);
        *(_DWORD *)(v186 + 416) |= 0x200u;
        ISSResourceAsynch::UnLock(this);
        if ( CommonGlobalState::m_ProfilerTraceEnabled && (dword_10316ECBC & 0x80000) != 0 )
        {
          v187 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v188 = v187[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v66 = *(_QWORD *)(v188 + 8);
          v189 = v66;
          if ( v66 )
          {
            v67 = *(_DWORD **)(v66 + 48);
            v190 = v67;
            if ( v67 )
            {
              if ( !*v67 )
              {
                v68 = (_QWORD *)*((_QWORD *)this + 2);
                v191 = v68[9] + 464LL;
                v69 = (const struct _GUID *)v191;
                v70 = *((_QWORD *)this + 2);
                v71 = (*(__int64 (__fastcall **)(__int64))(*v68 + 312LL))(v70);
                v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v70 + 896LL))(v70);
                dtc_stateTrace(17, v69, v72, v71);
              }
            }
          }
        }
        v73 = (_QWORD *)*((_QWORD *)this + 2);
        v192 = v73[9] + 464LL;
        v74 = (const struct _GUID *)v192;
        v75 = *((_QWORD *)this + 2);
        v76 = (*(__int64 (__fastcall **)(__int64))(*v73 + 312LL))(v75);
        v77 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 896LL))(v75);
        dtc_stateXEvent(0x11u, v74, (const struct _GUID *)((char *)this + 84), v77, v76, v236);
        v78 = (struct FullXact *)*((_QWORD *)this + 2);
        v79 = (struct XactWorkspace *)*((_QWORD *)v78 + 10);
        if ( !v79 )
        {
          utassert_fail(1u, "dtcXactWorkspace", "viperrm.cpp", 4269, 0);
          v78 = (struct FullXact *)*((_QWORD *)this + 2);
        }
        AutoSetupEnvForDTCOperation::AutoSetupEnvForDTCOperation((AutoSetupEnvForDTCOperation *)v233, v79, v78);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 2) + 320LL))(
          *((_QWORD *)this + 2),
          0,
          v234,
          0xFFFFFFFFLL);
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 504LL))(*((_QWORD *)this + 2)) )
          utassert_fail(1u, "m_transaction->GetActiveWorkCount () == 0", "viperrm.cpp", 4282, 0);
        DtcXactRMOnly::CommitDTCXact(*((DtcXactRMOnly **)this + 2));
        AutoSetupEnvForDTCOperation::~AutoSetupEnvForDTCOperation((AutoSetupEnvForDTCOperation *)v233);
        ISSResourceAsynch::Lock(this);
        *((_DWORD *)this + 7) = 3;
        *(_DWORD *)(*((_QWORD *)this + 2) + 420LL) = 3;
        v193 = *((_QWORD *)this + 2);
        *(_DWORD *)(v193 + 416) |= 0x20000u;
      }
    }
    else
    {
      if ( *((_DWORD *)this + 7) != 1 )
        utassert_fail(1u, "m_state == ACTIVE", "viperrm.cpp", 4044, 0);
      v128 = *((_DWORD *)this + 6);
      v194 = *((_QWORD *)this + 2);
      *(_DWORD *)(v194 + 416) |= 0x100u;
      ISSResourceAsynch::UnLock(this);
      v80 = (_QWORD *)*((_QWORD *)this + 2);
      v81 = (const struct _GUID *)(v80[9] + 464LL);
      v82 = v81;
      v83 = v80;
      if ( CommonGlobalState::m_ProfilerTraceEnabled && (dword_10316ECBC & 0x80000) != 0 )
      {
        v195 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v196 = v195[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v84 = *(_QWORD *)(v196 + 8);
        v197 = v84;
        if ( v84 && (v85 = *(_DWORD **)(v84 + 48), (v198 = v85) != 0) && !*v85 )
        {
          v86 = *((_QWORD *)this + 2);
          v87 = (*(__int64 (__fastcall **)(__int64))(*v80 + 312LL))(v86);
          v88 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 896LL))(v86);
          v82 = v81;
          dtc_stateTrace(14, v81, v88, v87);
          v83 = (_QWORD *)*((_QWORD *)this + 2);
        }
        else
        {
          v83 = v80;
          v82 = v81;
        }
      }
      v89 = *((_QWORD *)this + 2);
      v90 = (*(__int64 (__fastcall **)(_QWORD *))(*v83 + 312LL))(v83);
      v91 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v89 + 896LL))(v89);
      dtc_stateXEvent(0xEu, v82, (const struct _GUID *)((char *)this + 84), v91, v90, v236);
      if ( (byte_10317AFA6 & 0x20) != 0
        || (v199 = NtCurrentTeb()->ThreadLocalStoragePointer,
            v200 = (__int64 *)(v199[SystemThread_TlsIndex] + SystemThread_TlsOffset),
            v92 = *v200,
            (v201 = v92) != 0)
        && (v93 = **(struct CSessionTraceFlags ***)(v92 + 56), (v202 = v93) != 0)
        && CSessionTraceFlags::CheckSessionTraceInternal(v93, 0x2135u) )
      {
        v94 = (const void *)*((_QWORD *)this + 2);
        v95 = (const void *)(*(__int64 (__fastcall **)(const void *))(*(_QWORD *)v94 + 712LL))(v94);
        traceCall("Preparing DTC xact. ITransaction* @%p, m_transaction* @%p", v95, v94);
      }
      v96 = *((_QWORD *)this + 2);
      if ( !*(_QWORD *)(v96 + 80) )
      {
        utassert_fail(1u, "dtcXactWorkspace", "viperrm.cpp", 4072, 0);
        v96 = *((_QWORD *)this + 2);
      }
      v97 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v203 = v97;
      v204 = (__int64 *)(v97[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v205 = *v204;
      LOBYTE(v97) = v128 != 0;
      v98 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(**(_QWORD **)(v205 + 144) + 176LL))(
              *(_QWORD *)(v205 + 144),
              v96,
              v97);
      v99 = v98;
      if ( !v98 )
      {
        if ( (byte_10317AFA6 & 0x20) != 0
          || (v215 = NtCurrentTeb()->ThreadLocalStoragePointer,
              v216 = (__int64 *)(v215[SystemThread_TlsIndex] + SystemThread_TlsOffset),
              v114 = *v216,
              (v217 = v114) != 0)
          && (v115 = **(struct CSessionTraceFlags ***)(v114 + 56), (v218 = v115) != 0)
          && CSessionTraceFlags::CheckSessionTraceInternal(v115, 0x2135u) )
        {
          v116 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 712LL))(*((_QWORD *)this + 2));
          traceCall("DTC xact aborted after failing PREPARE. ITransaction* @%p", v116);
        }
        if ( CommonGlobalState::m_ProfilerTraceEnabled && (dword_10316ECBC & 0x80000) != 0 )
        {
          v219 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v220 = v219[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v117 = *(_QWORD *)(v220 + 8);
          v221 = v117;
          if ( v117 )
          {
            v118 = *(_DWORD **)(v117 + 48);
            v222 = v118;
            if ( v118 )
            {
              if ( !*v118 )
              {
                v119 = *((_QWORD *)this + 2);
                v120 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v119 + 312LL))(v119);
                v121 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v119 + 896LL))(v119);
                dtc_stateTrace(16, v81, v121, v120);
              }
            }
          }
        }
        v113 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 312LL))(*((_QWORD *)this + 2));
        v106 = 16;
        goto LABEL_161;
      }
      if ( !v128 )
      {
        if ( CommonGlobalState::m_ProfilerTraceEnabled && (dword_10316ECBC & 0x80000) != 0 )
        {
          v211 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v212 = v211[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v108 = *(_QWORD *)(v212 + 8);
          v213 = v108;
          if ( v108 )
          {
            v109 = *(_DWORD **)(v108 + 48);
            v214 = v109;
            if ( v109 )
            {
              if ( !*v109 )
              {
                v110 = *((_QWORD *)this + 2);
                v111 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v110 + 312LL))(v110);
                v112 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v110 + 896LL))(v110);
                dtc_stateTrace(15, v81, v112, v111);
              }
            }
          }
        }
        v113 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 312LL))(*((_QWORD *)this + 2));
        v106 = 15;
LABEL_161:
        v105 = v113;
        v107 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 896LL))(*((_QWORD *)this + 2));
        goto LABEL_162;
      }
      if ( CommonGlobalState::m_ProfilerTraceEnabled && (dword_10316ECBC & 0x80000) != 0 )
      {
        v207 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v208 = v207[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v100 = *(_QWORD *)(v208 + 8);
        v209 = v100;
        if ( v100 )
        {
          v101 = *(_DWORD **)(v100 + 48);
          v210 = v101;
          if ( v101 )
          {
            if ( !*v101 )
            {
              v102 = *((_QWORD *)this + 2);
              v103 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v102 + 312LL))(v102);
              v104 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v102 + 896LL))(v102);
              dtc_stateTrace(17, v81, v104, v103);
            }
          }
        }
      }
      v105 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 312LL))(*((_QWORD *)this + 2));
      v106 = 17;
      v107 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 896LL))(*((_QWORD *)this + 2));
LABEL_162:
      dtc_stateXEvent(v106, v81, (const struct _GUID *)((char *)this + 84), v107, v105, v236);
      ISSResourceAsynch::Lock(this);
      if ( v99 )
      {
        if ( v128 )
        {
          *((_DWORD *)this + 7) = 3;
          v122 = 3;
        }
        else
        {
          *((_DWORD *)this + 7) = 2;
          v122 = 2;
        }
      }
      else
      {
        *((_DWORD *)this + 7) = 4;
        v122 = 4;
      }
      *(_DWORD *)(*((_QWORD *)this + 2) + 420LL) = v122;
      *(_DWORD *)(*((_QWORD *)this + 2) + 416LL) |= 0x10000u;
    }
  }
  v123 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v124 = *(struct Worker **)(v123 + 256);
  if ( !v124 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v124 = *(struct Worker **)(v123 + 256);
  }
  if ( *((_DWORD *)v124 + 139) )
    ExceptionPostCatchActions(v124);
  *((_DWORD *)this + 17) = 0;
  if ( *((_DWORD *)this + 20) )
  {
    *((_DWORD *)this + 20) = 0;
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v125 = rand();
      if ( v125 == 5 * (v125 / 5) )
        Spinlock<189,4,258>::UpdateStatSnapshot();
    }
    *((_QWORD *)this + 4) = 0;
  }
  *(_DWORD *)(v130 + 616) &= ~v129;
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))
                       + 72LL)
           + 5081LL) = 0;
}

```

## disassembly

```asm
0x101d37410  mov     [rsp+arg_0], rcx
0x101d37415  push    rbx
0x101d37416  push    rsi
0x101d37417  push    rdi
0x101d37418  push    r12
0x101d3741a  push    r13
0x101d3741c  push    r14
0x101d3741e  push    r15
0x101d37420  sub     rsp, 4B0h
0x101d37427  mov     [rsp+4E8h+var_1D8], 0FFFFFFFFFFFFFFFEh
0x101d37433  mov     rdi, rcx
0x101d37436  mov     rdx, gs:58h
0x101d3743f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d37446  mov     ecx, [rax]
0x101d37448  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d3744f  mov     eax, [rax]
0x101d37451  add     rax, [rdx+rcx*8]
0x101d37455  mov     rax, [rax]
0x101d37458  mov     rcx, [rax+48h]
0x101d3745c  mov     byte ptr [rcx+13D9h], 1
0x101d37463  xor     r12d, r12d
0x101d37466  mov     [rsp+4E8h+var_498], r12d
0x101d3746b  mov     rdx, gs:58h
0x101d37474  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d3747b  mov     ecx, [rax]
0x101d3747d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d37484  mov     ebx, [rax]
0x101d37486  add     rbx, [rdx+rcx*8]
0x101d3748a  mov     rdx, [rbx+100h]
0x101d37491  test    rdx, rdx
0x101d37494  jnz     short loc_101D374A5
0x101d37496  xor     ecx, ecx
0x101d37498  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101d3749e  mov     rdx, [rbx+100h]
0x101d374a5  mov     [rsp+4E8h+var_490], rdx
0x101d374aa  mov     ecx, [rdx+268h]
0x101d374b0  mov     eax, ecx
0x101d374b2  and     eax, 27h
0x101d374b5  xor     eax, 27h
0x101d374b8  mov     [rsp+4E8h+var_498], eax
0x101d374bc  or      ecx, 27h
0x101d374bf  mov     [rdx+268h], ecx
0x101d374c5  test    cs:byte_10317AFA6, 20h
0x101d374cc  jnz     short loc_101D37510
0x101d374ce  mov     r8, gs:58h
0x101d374d7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d374de  mov     ecx, [rax]
0x101d374e0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d374e7  mov     edx, [rax]
0x101d374e9  add     rdx, [r8+rcx*8]
0x101d374ed  mov     rax, [rdx]
0x101d374f0  test    rax, rax
0x101d374f3  jz      short loc_101D37542
0x101d374f5  mov     rax, [rax+38h]
0x101d374f9  mov     rcx, [rax]
0x101d374fc  test    rcx, rcx
0x101d374ff  jz      short loc_101D37542
0x101d37501  mov     edx, 2135h
0x101d37506  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101d3750c  test    eax, eax
0x101d3750e  jz      short loc_101D37542
0x101d37510  mov     rcx, [rdi+10h]
0x101d37514  mov     rax, [rcx+48h]
0x101d37518  movsxd  rdx, dword ptr [rax]
0x101d3751b  lea     rbx, ?sm_xactStateName@BaseXact@@2PAPEBDA; char const * near * BaseXact::sm_xactStateName
0x101d37522  mov     rbx, [rbx+rdx*8]
0x101d37526  mov     rax, [rcx]
0x101d37529  call    qword ptr [rax+2C8h]
0x101d3752f  mov     r8, rax
0x101d37532  mov     rdx, rbx
0x101d37535  lea     rcx, aDotmworkCalled; "DOTMWORK called in %s state, ITransacti"...
0x101d3753c  call    ?traceCall@@YAXPEBDZZ; traceCall(char const *,...)
0x101d37541  nop
0x101d37542  mov     [rsp+4E8h+arg_8], 0
0x101d3754a  lea     rcx, [rdi+54h]; struct _GUID *
0x101d3754e  mov     dl, 1; bool
0x101d37550  call    ?GetDTCStateByRmId@@YAPEAVCDTCState@@AEBU_GUID@@_N@Z; GetDTCStateByRmId(_GUID const &,bool)
0x101d37555  mov     [rsp+4E8h+var_458], rax
0x101d3755d  test    rax, rax
0x101d37560  jz      short loc_101D37578
0x101d37562  movzx   ecx, byte ptr [rax+15Ch]
0x101d37569  mov     [rsp+4E8h+arg_8], cl
0x101d37570  mov     rcx, rax; this
0x101d37573  call    ?Release@CDTCState@@QEAAKXZ; CDTCState::Release(void)
0x101d37578  movzx   eax, [rsp+4E8h+arg_8]
0x101d37580  mov     [rsp+4E8h+arg_10], al
0x101d37587  mov     rcx, rdi; this
0x101d3758a  call    ?Lock@ISSResourceAsynch@@AEAAXXZ; ISSResourceAsynch::Lock(void)
0x101d3758f  lea     rbx, ?szText@?8???$CompileOnDataType@$0A@$00_K@RbpDecode@@CAP6AX_N0HPEA_K1PEBVRbpColumnContextNew@@PEAE@ZW4RbpDataType@@W4RbpEncodingType@@00@Z@4QBDB; "Invalid switch value"
0x101d37596  lea     r15, aAbort; "abort"
0x101d3759d  cmp     dword ptr [rdi+2Ch], 0
0x101d375a1  jz      loc_101D38A14
0x101d375a7  cmp     dword ptr [rdi+50h], 1
0x101d375ab  jz      short loc_101D375D1
0x101d375ad  mov     [rsp+4E8h+var_4C8], r12
0x101d375b2  mov     r9d, 448h
0x101d375b8  lea     r8, ?szFileName@?6??GetXactUTCBeginTime@ParNestedXact@@UEAAXAEAVCDatetime2@@@Z@4QBDB; "Sql\\Ntdbms\\storeng\\include\\xactimp."...
0x101d375bf  lea     rdx, ?szExpression@?6??AssertLockHeld@ISSResourceAsynch@@AEAAXXZ@4QBDB; "TRUE == m_locked"
0x101d375c6  mov     ecx, 1
0x101d375cb  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101d375d1  cmp     dword ptr [rdi+44h], 0
0x101d375d5  jnz     short loc_101D375FB
0x101d375d7  mov     [rsp+4E8h+var_4C8], r12
0x101d375dc  mov     r9d, 0FC4h
0x101d375e2  lea     r8, aViperrmCpp; "viperrm.cpp"
0x101d375e9  lea     rdx, aMFsystemthread; "m_fSystemThreadActive"
0x101d375f0  mov     ecx, 1
0x101d375f5  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101d375fb  movsxd  rcx, dword ptr [rdi+28h]
0x101d375ff  mov     r8d, [rdi+rcx*4+30h]
0x101d37604  mov     [rsp+4E8h+var_488], r8d
0x101d37609  inc     ecx
0x101d3760b  mov     eax, 66666667h
0x101d37610  imul    ecx
0x101d37612  sar     edx, 1
0x101d37614  mov     eax, edx
0x101d37616  shr     eax, 1Fh
0x101d37619  add     edx, eax
0x101d3761b  lea     eax, [rdx+rdx*4]
0x101d3761e  sub     ecx, eax
0x101d37620  mov     [rdi+28h], ecx
0x101d37623  dec     dword ptr [rdi+2Ch]
0x101d37626  test    r8d, r8d
0x101d37629  jz      loc_101D383EE
0x101d3762f  sub     r8d, 1
0x101d37633  jz      loc_101D3819D
0x101d37639  sub     r8d, 1
0x101d3763d  jz      loc_101D37DC5
0x101d37643  sub     r8d, 1
0x101d37647  jz      loc_101D37885
0x101d3764d  cmp     r8d, 1
0x101d37651  jz      short loc_101D3767C
0x101d37653  mov     [rsp+4E8h+var_4C8], rbx
0x101d37658  mov     r9d, 114Fh
0x101d3765e  lea     r8, aViperrmCpp; "viperrm.cpp"
0x101d37665  lea     rdx, ?szExpression@?CC@???$GetJobPartition@$$CBV_lambda_ae11ec6e04ca7d20c663000a5faff827_@@@CBulkSyncedJobSchedulerBySpinLock@@QEAA?AW4EJobSchedResult@CBulkSyncedJobScheduler@@AEAK0KAEBV_lambda_ae11ec6e04ca7d20c663000a5faff827_@@@Z@4QBDB; "FALSE"
0x101d3766c  mov     ecx, 1
0x101d37671  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101d37677  jmp     loc_101D38A0F
0x101d3767c  mov     rax, [rdi+10h]
0x101d37680  mov     [rsp+4E8h+var_150], rax
0x101d37688  or      dword ptr [rax+1A0h], 1000h
0x101d37692  mov     ecx, [rdi+1Ch]
0x101d37695  cmp     ecx, 1
0x101d37698  jz      short loc_101D376DC
0x101d3769a  lea     eax, [rcx-3]
0x101d3769d  cmp     eax, 2
0x101d376a0  jbe     short loc_101D376DC
0x101d376a2  cmp     ecx, 2
0x101d376a5  jnz     short loc_101D376B8
0x101d376a7  mov     rcx, [rdi+10h]
0x101d376ab  mov     rax, [rcx]
0x101d376ae  call    qword ptr [rax+150h]
0x101d376b4  test    eax, eax
0x101d376b6  jnz     short loc_101D376DC
0x101d376b8  mov     [rsp+4E8h+var_4C8], r12
0x101d376bd  mov     r9d, 1138h
0x101d376c3  lea     r8, aViperrmCpp; "viperrm.cpp"
0x101d376ca  lea     rdx, aMStateActiveMS; "(m_state == ACTIVE) || (m_state == COMM"...
0x101d376d1  mov     ecx, 1
0x101d376d6  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101d376dc  cmp     dword ptr [rdi+8], 0
0x101d376e0  jz      short loc_101D37706
0x101d376e2  mov     [rsp+4E8h+var_4C8], r12
0x101d376e7  mov     r9d, 1139h
0x101d376ed  lea     r8, aViperrmCpp; "viperrm.cpp"
0x101d376f4  lea     rdx, ?szExpression@?6???1SparseBitmap@@QEAA@XZ@4QBDB; "m_refCount == 0"
0x101d376fb  mov     ecx, 1
0x101d37700  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101d37706  mov     [rdi+44h], r12d
0x101d3770a  mov     rax, [rdi+10h]
0x101d3770e  mov     [rsp+4E8h+var_148], rax
0x101d37716  or      dword ptr [rax+1A0h], 100000h
0x101d37720  mov     rcx, rdi; this
0x101d37723  call    ?UnLock@ISSResourceAsynch@@AEAAXXZ; ISSResourceAsynch::UnLock(void)
0x101d37728  test    cs:byte_10317AFA6, 20h
0x101d3772f  jnz     short loc_101D37798
0x101d37731  mov     r9, gs:58h
0x101d3773a  mov     [rsp+4E8h+var_140], r9
0x101d37742  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d37749  mov     ecx, [rax]
0x101d3774b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d37752  mov     r8d, [rax]
0x101d37755  add     r8, [r9+rcx*8]
0x101d37759  mov     [rsp+4E8h+var_138], r8
0x101d37761  mov     rax, [r8]
0x101d37764  mov     [rsp+4E8h+var_130], rax
0x101d3776c  test    rax, rax
0x101d3776f  jz      short loc_101D377B4
0x101d37771  mov     rax, [rax+38h]
0x101d37775  mov     rcx, [rax]
0x101d37778  mov     [rsp+4E8h+var_128], rcx
0x101d37780  test    rcx, rcx
0x101d37783  jz      short loc_101D377B4
0x101d37785  mov     edx, 2135h
0x101d3778a  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101d37790  mov     [rsp+4E8h+var_484], eax
0x101d37794  test    eax, eax
0x101d37796  jz      short loc_101D377B4
0x101d37798  mov     rcx, [rdi+10h]
0x101d3779c  mov     rax, [rcx]
0x101d3779f  call    qword ptr [rax+2C8h]
0x101d377a5  mov     rdx, rax
0x101d377a8  lea     rcx, aDtcXactRelease; "DTC xact released. ITransaction* @%p"
0x101d377af  call    ?traceCall@@YAXPEBDZZ; traceCall(char const *,...)
0x101d377b4  lea     rcx, [rdi+54h]; struct _GUID *
0x101d377b8  mov     dl, 1; bool
0x101d377ba  call    ?GetDTCStateByRmId@@YAPEAVCDTCState@@AEBU_GUID@@_N@Z; GetDTCStateByRmId(_GUID const &,bool)
0x101d377bf  mov     rbx, rax
0x101d377c2  mov     [rsp+4E8h+var_458], rax
0x101d377ca  test    rax, rax
0x101d377cd  jz      short loc_101D377DF
0x101d377cf  mov     rcx, rax; this
0x101d377d2  call    ?DecrementActiveXactCount@CDTCState@@QEAAXXZ; CDTCState::DecrementActiveXactCount(void)
0x101d377d7  mov     rcx, rbx; this
0x101d377da  call    ?Release@CDTCState@@QEAAKXZ; CDTCState::Release(void)
0x101d377df  mov     rcx, [rdi+10h]
0x101d377e3  mov     rax, [rcx]
0x101d377e6  call    qword ptr [rax+220h]
0x101d377ec  lea     rax, ??_7ISSResourceAsynch@@6B@; const ISSResourceAsynch::`vftable'
0x101d377f3  mov     [rdi], rax
0x101d377f6  mov     rcx, [rdi+48h]
0x101d377fa  mov     [rsp+4E8h+var_390], rcx
0x101d37802  mov     edx, 28h ; '('
0x101d37807  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x101d3780d  mov     edx, 68h ; 'h'
0x101d37812  mov     rcx, rdi
0x101d37815  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x101d3781b  nop
0x101d3781c  mov     ecx, [rsp+4E8h+var_498]
0x101d37820  not     ecx
0x101d37822  mov     [rsp+4E8h+var_480], ecx
0x101d37826  mov     rax, [rsp+4E8h+var_490]
0x101d3782b  add     rax, 268h
0x101d37831  mov     [rsp+4E8h+var_388], rax
0x101d37839  and     [rax], ecx
0x101d3783b  mov     rdx, gs:58h
0x101d37844  mov     [rsp+4E8h+var_380], rdx
0x101d3784c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d37853  mov     ecx, [rax]
0x101d37855  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d3785c  mov     eax, [rax]
0x101d3785e  add     rax, [rdx+rcx*8]
0x101d37862  mov     [rsp+4E8h+var_378], rax
0x101d3786a  mov     rax, [rax]
0x101d3786d  mov     [rsp+4E8h+var_370], rax
0x101d37875  mov     rax, [rax+48h]
0x101d37879  mov     byte ptr [rax+13D9h], 0
0x101d37880  jmp     loc_101D38AEC
0x101d37885  cmp     dword ptr [rdi+1Ch], 2
0x101d37889  jz      short loc_101D378AF
0x101d3788b  mov     [rsp+4E8h+var_4C8], r12
0x101d37890  mov     r9d, 10C6h
0x101d37896  lea     r8, aViperrmCpp; "viperrm.cpp"
0x101d3789d  lea     rdx, aMStatePrepared; "m_state == PREPARED"
0x101d378a4  mov     ecx, 1
0x101d378a9  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101d378af  mov     rax, [rdi+10h]
0x101d378b3  mov     [rsp+4E8h+var_368], rax
0x101d378bb  or      dword ptr [rax+1A0h], 800h
0x101d378c5  mov     rcx, rdi; this
0x101d378c8  call    ?UnLock@ISSResourceAsynch@@AEAAXXZ; ISSResourceAsynch::UnLock(void)
0x101d378cd  mov     r9, [rdi+10h]
0x101d378d1  mov     r13, [r9+48h]
0x101d378d5  add     r13, 1D0h
0x101d378dc  mov     [rsp+4E8h+var_4B8], r13
0x101d378e1  mov     rax, cs:__imp_?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_ProfilerTraceEnabled
0x101d378e8  movzx   ecx, byte ptr [rax]
0x101d378eb  mov     [rsp+4E8h+arg_18], cl
0x101d378f2  mov     rdx, r9
0x101d378f5  test    cl, cl
0x101d378f7  jz      loc_101D379A8
0x101d378fd  test    cs:dword_10316ECBC, 80000h
0x101d37907  jz      loc_101D379A8
0x101d3790d  mov     r8, gs:58h
0x101d37916  mov     [rsp+4E8h+var_360], r8
0x101d3791e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d37925  mov     ecx, [rax]
0x101d37927  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d3792e  mov     edx, [rax]
0x101d37930  add     rdx, [r8+rcx*8]
0x101d37934  mov     [rsp+4E8h+var_358], rdx
0x101d3793c  mov     rax, [rdx+8]
0x101d37940  mov     [rsp+4E8h+var_350], rax
0x101d37948  test    rax, rax
0x101d3794b  jz      short loc_101D379A0
0x101d3794d  mov     rax, [rax+30h]
0x101d37951  mov     [rsp+4E8h+var_348], rax
0x101d37959  test    rax, rax
0x101d3795c  jz      short loc_101D379A0
0x101d3795e  cmp     dword ptr [rax], 0
0x101d37961  jnz     short loc_101D379A0
0x101d37963  mov     rax, [r9]
0x101d37966  mov     rbx, [rdi+10h]
0x101d3796a  mov     rcx, rbx
0x101d3796d  call    qword ptr [rax+138h]
0x101d37973  mov     rsi, rax
0x101d37976  mov     rdx, [rbx]
0x101d37979  mov     rcx, rbx
0x101d3797c  call    qword ptr [rdx+380h]
  ... truncated ...
```
