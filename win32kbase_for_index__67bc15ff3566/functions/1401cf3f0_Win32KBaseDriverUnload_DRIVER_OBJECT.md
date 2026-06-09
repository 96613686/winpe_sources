# Win32KBaseDriverUnload(_DRIVER_OBJECT *)

- ea: `0x1401cf3f0`
- end: `0x1401cfb8b`
- name: `?Win32KBaseDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `1947`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402d9400`

## callees

- `0x14001365c`
- `0x140014e60`
- `0x140015ed0`
- `0x140049ec0`
- `0x140065e7c`
- `0x140067600`
- `0x14007b930`
- `0x1400cef7c`
- `0x140120f8c`
- `0x14012e834`
- `0x1401341d4`
- `0x140168220`
- `0x140176614`
- `0x14017beac`
- `0x1401840a0`
- `0x140188984`
- `0x14018a7f0`
- `0x1401aace0`
- `0x1401aae00`
- `0x1401ac948`
- `0x1401acba4`
- `0x1401ad2b0`
- `0x1401b8c48`
- `0x1401b9f80`
- `0x1401c9dec`
- `0x1401cf3f0`
- `0x1401d24c8`
- `0x140216184`
- `0x140236430`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401cfac3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cfac3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401cf54a`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401cf54a`
- `ntoskrnl!RtlDestroyHeap` at `0x1401cf846`
- `ntoskrnl!RtlDestroyHeap` at `0x1401cf846`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401cf865`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401cf927`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401cf865`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401cf927`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf7d3`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf884`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf946`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf7d3`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf884`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf946`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf498`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf4bd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf4de`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf503`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf57d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf5a2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf952`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf986`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cfa44`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cfa69`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf498`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf4bd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf4de`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf503`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf57d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf5a2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf952`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf986`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cfa44`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cfa69`
- `WIN32K!W32GetSessionState` at `0x1401cf5cc`
- `WIN32K!W32GetSessionState` at `0x1401cfb3c`
- `WIN32K!W32GetSessionState` at `0x1401cfb56`
- `WIN32K!W32GetSessionState` at `0x1401cf5cc`
- `WIN32K!W32GetSessionState` at `0x1401cfb3c`
- `WIN32K!W32GetSessionState` at `0x1401cfb56`
- `WIN32K!W32UnregisterSessionProcess` at `0x1401cf62c`
- `WIN32K!W32UnregisterSessionProcess` at `0x1401cf62c`
- `WIN32K!W32GetDCompSessionState` at `0x1401cf524`
- `WIN32K!W32GetDCompSessionState` at `0x1401cf563`
- `WIN32K!W32GetDCompSessionState` at `0x1401cf524`
- `WIN32K!W32GetDCompSessionState` at `0x1401cf563`
- `WIN32K!W32GetUserSessionState` at `0x1401cf446`
- `WIN32K!W32GetUserSessionState` at `0x1401cf5ff`
- `WIN32K!W32GetUserSessionState` at `0x1401cf618`
- `WIN32K!W32GetUserSessionState` at `0x1401cf638`
- `WIN32K!W32GetUserSessionState` at `0x1401cf651`
- `WIN32K!W32GetUserSessionState` at `0x1401cf66d`
- `WIN32K!W32GetUserSessionState` at `0x1401cf684`
- `WIN32K!W32GetUserSessionState` at `0x1401cf6ae`
- `WIN32K!W32GetUserSessionState` at `0x1401cf6ca`
- `WIN32K!W32GetUserSessionState` at `0x1401cf6fc`
- `WIN32K!W32GetUserSessionState` at `0x1401cf710`
- `WIN32K!W32GetUserSessionState` at `0x1401cf725`
- `WIN32K!W32GetUserSessionState` at `0x1401cf738`
- `WIN32K!W32GetUserSessionState` at `0x1401cf753`
- `WIN32K!W32GetUserSessionState` at `0x1401cf768`
- `WIN32K!W32GetUserSessionState` at `0x1401cf780`
- `WIN32K!W32GetUserSessionState` at `0x1401cf798`
- `WIN32K!W32GetUserSessionState` at `0x1401cf7ab`
- `WIN32K!W32GetUserSessionState` at `0x1401cf7c0`
- `WIN32K!W32GetUserSessionState` at `0x1401cf7df`
- `WIN32K!W32GetUserSessionState` at `0x1401cf7f2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf80b`
- `WIN32K!W32GetUserSessionState` at `0x1401cf81e`
- `WIN32K!W32GetUserSessionState` at `0x1401cf833`
- `WIN32K!W32GetUserSessionState` at `0x1401cf852`
- `WIN32K!W32GetUserSessionState` at `0x1401cf871`
- `WIN32K!W32GetUserSessionState` at `0x1401cf890`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8a5`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8bd`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8d2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8ea`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8ff`
- `WIN32K!W32GetUserSessionState` at `0x1401cf914`
- `WIN32K!W32GetUserSessionState` at `0x1401cf933`
- `WIN32K!W32GetUserSessionState` at `0x1401cf977`
- `WIN32K!W32GetUserSessionState` at `0x1401cf9ae`
- `WIN32K!W32GetUserSessionState` at `0x1401cf9c2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf9dd`
- `WIN32K!W32GetUserSessionState` at `0x1401cf9ff`
- `WIN32K!W32GetUserSessionState` at `0x1401cfa14`
- `WIN32K!W32GetUserSessionState` at `0x1401cfa31`
- `WIN32K!W32GetUserSessionState` at `0x1401cfa99`
- `WIN32K!W32GetUserSessionState` at `0x1401cfaae`
- `WIN32K!W32GetUserSessionState` at `0x1401cfacf`
- `WIN32K!W32GetUserSessionState` at `0x1401cfae7`
- `WIN32K!W32GetUserSessionState` at `0x1401cf446`
- `WIN32K!W32GetUserSessionState` at `0x1401cf5ff`
- `WIN32K!W32GetUserSessionState` at `0x1401cf618`
- `WIN32K!W32GetUserSessionState` at `0x1401cf638`
- `WIN32K!W32GetUserSessionState` at `0x1401cf651`
- `WIN32K!W32GetUserSessionState` at `0x1401cf66d`
- `WIN32K!W32GetUserSessionState` at `0x1401cf684`
- `WIN32K!W32GetUserSessionState` at `0x1401cf6ae`
- `WIN32K!W32GetUserSessionState` at `0x1401cf6ca`
- `WIN32K!W32GetUserSessionState` at `0x1401cf6fc`
- `WIN32K!W32GetUserSessionState` at `0x1401cf710`
- `WIN32K!W32GetUserSessionState` at `0x1401cf725`
- `WIN32K!W32GetUserSessionState` at `0x1401cf738`
- `WIN32K!W32GetUserSessionState` at `0x1401cf753`
- `WIN32K!W32GetUserSessionState` at `0x1401cf768`
- `WIN32K!W32GetUserSessionState` at `0x1401cf780`
- `WIN32K!W32GetUserSessionState` at `0x1401cf798`
- `WIN32K!W32GetUserSessionState` at `0x1401cf7ab`
- `WIN32K!W32GetUserSessionState` at `0x1401cf7c0`
- `WIN32K!W32GetUserSessionState` at `0x1401cf7df`
- `WIN32K!W32GetUserSessionState` at `0x1401cf7f2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf80b`
- `WIN32K!W32GetUserSessionState` at `0x1401cf81e`
- `WIN32K!W32GetUserSessionState` at `0x1401cf833`
- `WIN32K!W32GetUserSessionState` at `0x1401cf852`
- `WIN32K!W32GetUserSessionState` at `0x1401cf871`
- `WIN32K!W32GetUserSessionState` at `0x1401cf890`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8a5`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8bd`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8d2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8ea`
- `WIN32K!W32GetUserSessionState` at `0x1401cf8ff`
- `WIN32K!W32GetUserSessionState` at `0x1401cf914`
- `WIN32K!W32GetUserSessionState` at `0x1401cf933`
- `WIN32K!W32GetUserSessionState` at `0x1401cf977`
- `WIN32K!W32GetUserSessionState` at `0x1401cf9ae`
- `WIN32K!W32GetUserSessionState` at `0x1401cf9c2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf9dd`
- `WIN32K!W32GetUserSessionState` at `0x1401cf9ff`
- `WIN32K!W32GetUserSessionState` at `0x1401cfa14`
- `WIN32K!W32GetUserSessionState` at `0x1401cfa31`
- `WIN32K!W32GetUserSessionState` at `0x1401cfa99`
- `WIN32K!W32GetUserSessionState` at `0x1401cfaae`
- `WIN32K!W32GetUserSessionState` at `0x1401cfacf`
- `WIN32K!W32GetUserSessionState` at `0x1401cfae7`

## pseudocode

```c
void __fastcall Win32KBaseDriverUnload(struct _DRIVER_OBJECT *a1, __int64 a2, __int64 a3)
{
  char v3; // bl
  bool v4; // di
  __int64 UserSessionState; // rax
  int v6; // r8d
  int v7; // edx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int (*v12)(void); // rax
  void (*v13)(void); // rax
  int (*v14)(void); // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  void (*v17)(void); // rax
  unsigned int v18; // edx
  __int64 DCompSessionState; // rbx
  void *v20; // rcx
  struct _ERESOURCE *v21; // rcx
  __int64 v22; // rdx
  void *v23; // rcx
  Gre::Base *v24; // rcx
  int (*v25)(void); // rax
  __int64 v26; // rdx
  void (*v27)(void); // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rdi
  OPM *v32; // rbx
  void *v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rdx
  _QWORD *v46; // rcx
  __int64 v47; // r8
  __int64 v48; // rcx
  _QWORD *v49; // rdi
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  _QWORD *v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  _QWORD *v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  void *v70; // rbx
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // r8
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  __int64 v89; // rax
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // r8
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // r8
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // r8
  __int64 v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // rax
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // rdx
  __int64 v120; // rcx
  __int64 v121; // r8
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // r8
  int (*v127)(void); // rax
  __int64 v128; // rbx
  __int64 v129; // rdx
  __int64 v130; // rcx
  void (__fastcall *v131)(__int64); // rax
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // r8
  __int64 v135; // rbx
  void *v136; // rdi
  __int64 v137; // rax
  __int64 v138; // rdx
  __int64 v139; // rcx
  __int64 v140; // r8
  __int64 v141; // rdx
  CAsyncKeyEventMonitor *v142; // rcx
  __int64 v143; // r8
  int (*v144)(void); // rax
  __int64 v145; // rdx
  __int64 v146; // rcx
  void (*v147)(void); // rax
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // r8
  __int64 v151; // rdx
  __int64 v152; // rcx
  __int64 v153; // r8
  __int64 v154; // rax
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // r8
  __int64 v158; // rdx
  __int64 v159; // rcx
  __int64 v160; // r8
  __int64 v161; // rax
  __int64 v162; // rdi
  void *v163; // rbx
  __int64 v164; // rcx
  PDRIVER_OBJECT v165; // rbx
  __int64 SessionState; // rax
  __int64 v167; // rcx
  __int64 v168; // rax
  volatile signed __int32 *v169[24]; // [rsp+40h] [rbp-C8h] BYREF

  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0
    || (v3 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v3 = 0;
  }
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, a2, a3);
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v7,
      v6,
      *(_QWORD *)(UserSessionState + 69136),
      4,
      14,
      11,
      (__int64)WPP_0406774dfaff3b2fc9e8e45c21beea27_Traceguids);
  }
  CTempW32ThreadNonPaged::CTempW32ThreadNonPaged((CTempW32ThreadNonPaged *)v169);
  v11 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v9, v8) + 48);
  v12 = *(int (**)(void))(v11 + 3848);
  if ( v12 )
  {
    if ( v12() >= 0 )
    {
      v11 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v11, v10) + 48);
      v13 = *(void (**)(void))(v11 + 3856);
      if ( v13 )
        v13();
    }
  }
  v14 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v11, v10) + 48) + 248LL);
  if ( v14 )
  {
    if ( v14() >= 0 )
    {
      v17 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v16, v15) + 48) + 256LL);
      if ( v17 )
        v17();
    }
  }
  DCompSessionState = W32GetDCompSessionState();
  v20 = *(void **)(DCompSessionState + 16);
  if ( v20 )
    DirectComposition::CConnection::`scalar deleting destructor'(v20, v18);
  v21 = *(struct _ERESOURCE **)(DCompSessionState + 32);
  if ( v21 )
  {
    ExDeleteResourceLite(v21);
    GreDeleteFastMutex(*(PVOID *)(DCompSessionState + 32));
    *(_QWORD *)(DCompSessionState + 32) = 0;
  }
  v23 = *(void **)(W32GetDCompSessionState() + 24);
  if ( v23 )
    DirectComposition::CSynchronizationManager::`scalar deleting destructor'(v23, v22);
  v24 = *(Gre::Base **)(W32GetWin32kBaseApiSetTable(v23, v22) + 48);
  v25 = (int (*)(void))*((_QWORD *)v24 + 35);
  if ( v25 )
  {
    if ( v25() >= 0 )
    {
      v24 = *(Gre::Base **)(W32GetWin32kBaseApiSetTable(v24, v26) + 48);
      v27 = (void (*)(void))*((_QWORD *)v24 + 36);
      if ( v27 )
        v27();
    }
  }
  if ( Gre::Base::IsSessionGlobalsAreaAllocated(v24) )
  {
    v31 = *(_QWORD *)(W32GetSessionState(v29) + 88);
    v32 = *(OPM **)(v31 + 3728);
    if ( v32 )
    {
      COPM::~COPM(*(COPM **)(v31 + 3728));
      OPM::OPMFreeMemory(v32, v33);
    }
    *(_QWORD *)(v31 + 3728) = 0;
  }
  v34 = W32GetUserSessionState(v29, v28, v30);
  *(_DWORD *)(v34 + 68920) |= 0x80u;
  MultiUserNtGreCleanup();
  v38 = W32GetUserSessionState(v36, v35, v37);
  *(_DWORD *)(v38 + 68920) |= 0x100u;
  W32UnregisterSessionProcess();
  if ( *(_QWORD *)(W32GetUserSessionState(v40, v39, v41) + 56744) )
  {
    v46 = (_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v43, v42, v44) + 56744) + 24LL);
    if ( (_QWORD *)*v46 != v46 )
    {
      v48 = *(_QWORD *)(W32GetUserSessionState(v46, v45, v47) + 56744);
      v49 = *(_QWORD **)(v48 + 24);
      v52 = *(_QWORD *)(W32GetUserSessionState(v48, v50, v51) + 56744) + 24LL;
      if ( v49 != (_QWORD *)v52 )
      {
        do
        {
          v55 = (_QWORD *)*v49;
          GreDeleteFastMutex(v49);
          v49 = v55;
          v53 = *(_QWORD *)(W32GetUserSessionState(v57, v56, v58) + 56744) + 24LL;
        }
        while ( v55 != (_QWORD *)v53 );
      }
      v59 = (_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v53, v52, v54) + 56744) + 24LL);
      v59[1] = v59;
      *v59 = v59;
    }
  }
  InputUnInitialize();
  Win32kNtUserCleanup();
  DestroyHandleTableObjects();
  CleanupDomainLocks();
  v63 = W32GetUserSessionState(v61, v60, v62);
  *(_DWORD *)(v63 + 68920) |= 0x200u;
  if ( *(_QWORD *)(W32GetUserSessionState(v65, v64, v66) + 42384) )
  {
    v70 = *(void **)(W32GetUserSessionState(v68, v67, v69) + 42384);
    v74 = W32GetUserSessionState(v72, v71, v73);
    NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(
      (NSInstrumentation::CLeakTrackingAllocator *)(v74 + 72016),
      v70);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v68, v67, v69) + 19632) )
  {
    v78 = W32GetUserSessionState(v76, v75, v77);
    UserTypeIsolationAllocators::Destroy(*(UserTypeIsolationAllocators **)(v78 + 19632));
    v82 = W32GetUserSessionState(v80, v79, v81);
    GreDeleteFastMutex(*(PVOID *)(v82 + 19632));
    *(_QWORD *)(W32GetUserSessionState(v84, v83, v85) + 19632) = 0;
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v76, v75, v77) + 71272) )
  {
    v89 = W32GetUserSessionState(v87, v86, v88);
    ObfDereferenceObject(*(PVOID *)(v89 + 71272));
    *(_QWORD *)(W32GetUserSessionState(v91, v90, v92) + 71272) = 0;
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v87, v86, v88) + 19672) )
  {
    *(_QWORD *)(W32GetUserSessionState(v94, v93, v95) + 19704) = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v97, v96, v98) + 19688) )
    {
      v102 = W32GetUserSessionState(v100, v99, v101);
      RtlDestroyHeap(*(PVOID *)(v102 + 19696));
      v106 = W32GetUserSessionState(v104, v103, v105);
      MmUnmapViewInSessionSpace(*(PVOID *)(v106 + 19688));
    }
    v107 = W32GetUserSessionState(v100, v99, v101);
    ObfDereferenceObject(*(PVOID *)(v107 + 19672));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v94, v93, v95) + 56744) )
  {
    v111 = W32GetUserSessionState(v109, v108, v110);
    GreDeleteFastMutex(*(PVOID *)(v111 + 56744));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v109, v108, v110) + 62688) )
  {
    v115 = W32GetUserSessionState(v113, v112, v114);
    GreDeleteFastMutex(*(PVOID *)(v115 + 62688));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v113, v112, v114) + 19680) )
  {
    if ( *(_QWORD *)(W32GetUserSessionState(v117, v116, v118) + 19664) )
    {
      v122 = W32GetUserSessionState(v120, v119, v121);
      MmUnmapViewInSessionSpace(*(PVOID *)(v122 + 19664));
    }
    v123 = W32GetUserSessionState(v120, v119, v121);
    ObfDereferenceObject(*(PVOID *)(v123 + 19680));
  }
  v125 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v117, v116) + 48);
  v127 = *(int (**)(void))(v125 + 296);
  if ( v127 )
  {
    if ( v127() >= 0 )
    {
      v128 = W32GetUserSessionState(v125, v124, v126);
      v125 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v130, v129) + 48);
      v131 = *(void (__fastcall **)(__int64))(v125 + 304);
      if ( v131 )
        v131(v128 + 65808);
    }
  }
  if ( *(_DWORD *)(W32GetUserSessionState(v125, v124, v126) + 69856) )
  {
    v135 = W32GetUserSessionState(v133, v132, v134);
    v136 = *(void **)(v135 + 19416);
    if ( v136 )
    {
      v137 = W32GetUserSessionState(v133, v132, v134);
      NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(
        (NSInstrumentation::CLeakTrackingAllocator *)(v137 + 72016),
        v136);
      *(_QWORD *)(v135 + 19416) = 0;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v133, v132, v134) + 14440) )
  {
    v142 = *(CAsyncKeyEventMonitor **)(W32GetUserSessionState(v139, v138, v140) + 14440);
    if ( v142 )
      CAsyncKeyEventMonitor::`scalar deleting destructor'(v142, v141);
    *(_QWORD *)(W32GetUserSessionState(v142, v141, v143) + 14440) = 0;
  }
  v144 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v139, v138) + 48) + 312LL);
  if ( v144 )
  {
    if ( v144() >= 0 )
    {
      v147 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v146, v145) + 48) + 320LL);
      if ( v147 )
        v147();
    }
  }
  CoreMessagingKPort::UnInitialize();
  CoreMsgUninitialize();
  RIMUnInitialize();
  if ( *(_QWORD *)(W32GetUserSessionState(v149, v148, v150) + 42360) )
  {
    v154 = W32GetUserSessionState(v152, v151, v153);
    ExFreePoolWithTag(*(PVOID *)(v154 + 42360), 0);
    *(_QWORD *)(W32GetUserSessionState(v156, v155, v157) + 42360) = 0;
  }
  FreeWin32KSyscallFilter();
  v161 = W32GetUserSessionState(v159, v158, v160);
  v162 = v161;
  v163 = *(void **)(v161 + 41144);
  if ( v163 )
  {
    CQoSReport::~CQoSReport(*(CQoSReport **)(v161 + 41144));
    GreDeleteFastMutex(v163);
  }
  *(_QWORD *)(v162 + 41144) = 0;
  UninitializeWin32PoolTracking();
  UninitializeWin32SiloGlobals();
  v165 = gpWin32kDriverObject;
  if ( gpWin32kDriverObject )
  {
    UninitializeBaseWppLog();
    EditionUninitializeWppLogging(v165);
  }
  SessionState = W32GetSessionState(v164);
  FreePerSessionWin32kCall(SessionState + 152);
  v168 = W32GetSessionState(v167);
  FreeWin32kApiSetTable(v168 + 152);
  CTempW32ThreadNonPaged::~CTempW32ThreadNonPaged(v169);
}

```

## disassembly

```asm
0x1401cf3f0  mov     [rsp+arg_0], rbx
0x1401cf3f5  mov     [rsp+arg_8], rsi
0x1401cf3fa  push    rdi
0x1401cf3fb  sub     rsp, 100h
0x1401cf402  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cf409  lea     rax, WPP_GLOBAL_Control
0x1401cf410  xor     esi, esi
0x1401cf412  cmp     rcx, rax
0x1401cf415  jz      short loc_1401CF428
0x1401cf417  test    dword ptr [rcx+2Ch], 2000h
0x1401cf41e  jz      short loc_1401CF428
0x1401cf420  cmp     byte ptr [rcx+29h], 4
0x1401cf424  mov     bl, 1
0x1401cf426  jnb     short loc_1401CF42B
0x1401cf428  mov     bl, sil
0x1401cf42b  lea     rax, WPP_RECORDER_INITIALIZED
0x1401cf432  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401cf439  setnz   dil
0x1401cf43d  test    bl, bl
0x1401cf43f  jnz     short loc_1401CF446
0x1401cf441  test    dil, dil
0x1401cf444  jz      short loc_1401CF48E
0x1401cf446  call    cs:__imp_W32GetUserSessionState
0x1401cf44d  nop     dword ptr [rax+rax+00h]
0x1401cf452  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cf459  mov     r8b, dil
0x1401cf45c  mov     dl, bl
0x1401cf45e  mov     r9, [rax+10E10h]
0x1401cf465  lea     rax, WPP_0406774dfaff3b2fc9e8e45c21beea27_Traceguids
0x1401cf46c  mov     rcx, [rcx+18h]
0x1401cf470  mov     [rsp+108h+var_D0], rax
0x1401cf475  mov     [rsp+108h+var_D8], 0Bh
0x1401cf47c  mov     [rsp+108h+var_E0], 0Eh
0x1401cf484  mov     [rsp+108h+var_E8], 4
0x1401cf489  call    WPP_RECORDER_AND_TRACE_SF_
0x1401cf48e  lea     rcx, [rsp+108h+var_C8]; this
0x1401cf493  call    ??0CTempW32ThreadNonPaged@@QEAA@XZ; CTempW32ThreadNonPaged::CTempW32ThreadNonPaged(void)
0x1401cf498  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf49f  nop     dword ptr [rax+rax+00h]
0x1401cf4a4  mov     rcx, [rax+30h]
0x1401cf4a8  mov     rax, [rcx+0F08h]
0x1401cf4af  test    rax, rax
0x1401cf4b2  jz      short loc_1401CF4DE
0x1401cf4b4  call    _guard_dispatch_icall
0x1401cf4b9  test    eax, eax
0x1401cf4bb  js      short loc_1401CF4DE
0x1401cf4bd  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf4c4  nop     dword ptr [rax+rax+00h]
0x1401cf4c9  mov     rcx, [rax+30h]
0x1401cf4cd  mov     rax, [rcx+0F10h]
0x1401cf4d4  test    rax, rax
0x1401cf4d7  jz      short loc_1401CF4DE
0x1401cf4d9  call    _guard_dispatch_icall
0x1401cf4de  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf4e5  nop     dword ptr [rax+rax+00h]
0x1401cf4ea  mov     rcx, [rax+30h]
0x1401cf4ee  mov     rax, [rcx+0F8h]
0x1401cf4f5  test    rax, rax
0x1401cf4f8  jz      short loc_1401CF524
0x1401cf4fa  call    _guard_dispatch_icall
0x1401cf4ff  test    eax, eax
0x1401cf501  js      short loc_1401CF524
0x1401cf503  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf50a  nop     dword ptr [rax+rax+00h]
0x1401cf50f  mov     rcx, [rax+30h]
0x1401cf513  mov     rax, [rcx+100h]
0x1401cf51a  test    rax, rax
0x1401cf51d  jz      short loc_1401CF524
0x1401cf51f  call    _guard_dispatch_icall
0x1401cf524  call    cs:__imp_W32GetDCompSessionState
0x1401cf52b  nop     dword ptr [rax+rax+00h]
0x1401cf530  mov     rbx, rax
0x1401cf533  mov     rcx, [rax+10h]; Buffer
0x1401cf537  test    rcx, rcx
0x1401cf53a  jz      short loc_1401CF541
0x1401cf53c  call    ??_GCConnection@DirectComposition@@AEAAPEAXI@Z; DirectComposition::CConnection::`scalar deleting destructor'(uint)
0x1401cf541  mov     rcx, [rbx+20h]; Resource
0x1401cf545  test    rcx, rcx
0x1401cf548  jz      short loc_1401CF563
0x1401cf54a  call    cs:__imp_ExDeleteResourceLite
0x1401cf551  nop     dword ptr [rax+rax+00h]
0x1401cf556  mov     rcx, [rbx+20h]; Buffer
0x1401cf55a  call    GreDeleteFastMutex
0x1401cf55f  mov     [rbx+20h], rsi
0x1401cf563  call    cs:__imp_W32GetDCompSessionState
0x1401cf56a  nop     dword ptr [rax+rax+00h]
0x1401cf56f  mov     rcx, [rax+18h]; Buffer
0x1401cf573  test    rcx, rcx
0x1401cf576  jz      short loc_1401CF57D
0x1401cf578  call    ??_GCSynchronizationManager@DirectComposition@@IEAAPEAXI@Z; DirectComposition::CSynchronizationManager::`scalar deleting destructor'(uint)
0x1401cf57d  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf584  nop     dword ptr [rax+rax+00h]
0x1401cf589  mov     rcx, [rax+30h]
0x1401cf58d  mov     rax, [rcx+118h]
0x1401cf594  test    rax, rax
0x1401cf597  jz      short loc_1401CF5C3
0x1401cf599  call    _guard_dispatch_icall
0x1401cf59e  test    eax, eax
0x1401cf5a0  js      short loc_1401CF5C3
0x1401cf5a2  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf5a9  nop     dword ptr [rax+rax+00h]
0x1401cf5ae  mov     rcx, [rax+30h]
0x1401cf5b2  mov     rax, [rcx+120h]
0x1401cf5b9  test    rax, rax
0x1401cf5bc  jz      short loc_1401CF5C3
0x1401cf5be  call    _guard_dispatch_icall
0x1401cf5c3  call    ?IsSessionGlobalsAreaAllocated@Base@Gre@@YA_NXZ; Gre::Base::IsSessionGlobalsAreaAllocated(void)
0x1401cf5c8  test    al, al
0x1401cf5ca  jz      short loc_1401CF5FF
0x1401cf5cc  call    cs:__imp_W32GetSessionState
0x1401cf5d3  nop     dword ptr [rax+rax+00h]
0x1401cf5d8  mov     rdi, [rax+58h]
0x1401cf5dc  mov     rbx, [rdi+0E90h]
0x1401cf5e3  test    rbx, rbx
0x1401cf5e6  jz      short loc_1401CF5F8
0x1401cf5e8  mov     rcx, rbx; this
0x1401cf5eb  call    ??1COPM@@QEAA@XZ; COPM::~COPM(void)
0x1401cf5f0  mov     rcx, rbx; this
0x1401cf5f3  call    ?OPMFreeMemory@OPM@@YAXPEAX@Z; OPM::OPMFreeMemory(void *)
0x1401cf5f8  mov     [rdi+0E90h], rsi
0x1401cf5ff  call    cs:__imp_W32GetUserSessionState
0x1401cf606  nop     dword ptr [rax+rax+00h]
0x1401cf60b  bts     dword ptr [rax+10D38h], 7
0x1401cf613  call    MultiUserNtGreCleanup
0x1401cf618  call    cs:__imp_W32GetUserSessionState
0x1401cf61f  nop     dword ptr [rax+rax+00h]
0x1401cf624  bts     dword ptr [rax+10D38h], 8
0x1401cf62c  call    cs:__imp_W32UnregisterSessionProcess
0x1401cf633  nop     dword ptr [rax+rax+00h]
0x1401cf638  call    cs:__imp_W32GetUserSessionState
0x1401cf63f  nop     dword ptr [rax+rax+00h]
0x1401cf644  cmp     [rax+0DDA8h], rsi
0x1401cf64b  jz      loc_1401CF6E8
0x1401cf651  call    cs:__imp_W32GetUserSessionState
0x1401cf658  nop     dword ptr [rax+rax+00h]
0x1401cf65d  mov     rcx, [rax+0DDA8h]
0x1401cf664  add     rcx, 18h
0x1401cf668  cmp     [rcx], rcx
0x1401cf66b  jz      short loc_1401CF6E8
0x1401cf66d  call    cs:__imp_W32GetUserSessionState
0x1401cf674  nop     dword ptr [rax+rax+00h]
0x1401cf679  mov     rcx, [rax+0DDA8h]
0x1401cf680  mov     rdi, [rcx+18h]
0x1401cf684  call    cs:__imp_W32GetUserSessionState
0x1401cf68b  nop     dword ptr [rax+rax+00h]
0x1401cf690  mov     rdx, [rax+0DDA8h]
0x1401cf697  add     rdx, 18h
0x1401cf69b  cmp     rdi, rdx
0x1401cf69e  jz      short loc_1401CF6CA
0x1401cf6a0  mov     rbx, [rdi]
0x1401cf6a3  mov     rcx, rdi; Buffer
0x1401cf6a6  call    GreDeleteFastMutex
0x1401cf6ab  mov     rdi, rbx
0x1401cf6ae  call    cs:__imp_W32GetUserSessionState
0x1401cf6b5  nop     dword ptr [rax+rax+00h]
0x1401cf6ba  mov     rcx, [rax+0DDA8h]
0x1401cf6c1  add     rcx, 18h
0x1401cf6c5  cmp     rbx, rcx
0x1401cf6c8  jnz     short loc_1401CF6A0
0x1401cf6ca  call    cs:__imp_W32GetUserSessionState
0x1401cf6d1  nop     dword ptr [rax+rax+00h]
0x1401cf6d6  mov     rcx, [rax+0DDA8h]
0x1401cf6dd  add     rcx, 18h
0x1401cf6e1  mov     [rcx+8], rcx
0x1401cf6e5  mov     [rcx], rcx
0x1401cf6e8  call    InputUnInitialize
0x1401cf6ed  call    ?Win32kNtUserCleanup@@YAHXZ; Win32kNtUserCleanup(void)
0x1401cf6f2  call    ?DestroyHandleTableObjects@@YAXXZ; DestroyHandleTableObjects(void)
0x1401cf6f7  call    ?CleanupDomainLocks@@YAXXZ; CleanupDomainLocks(void)
0x1401cf6fc  call    cs:__imp_W32GetUserSessionState
0x1401cf703  nop     dword ptr [rax+rax+00h]
0x1401cf708  bts     dword ptr [rax+10D38h], 9
0x1401cf710  call    cs:__imp_W32GetUserSessionState
0x1401cf717  nop     dword ptr [rax+rax+00h]
0x1401cf71c  cmp     [rax+0A590h], rsi
0x1401cf723  jz      short loc_1401CF753
0x1401cf725  call    cs:__imp_W32GetUserSessionState
0x1401cf72c  nop     dword ptr [rax+rax+00h]
0x1401cf731  mov     rbx, [rax+0A590h]
0x1401cf738  call    cs:__imp_W32GetUserSessionState
0x1401cf73f  nop     dword ptr [rax+rax+00h]
0x1401cf744  mov     rdx, rbx; void *
0x1401cf747  lea     rcx, [rax+11950h]; this
0x1401cf74e  call    ?FreePagedLookasideList@CLeakTrackingAllocator@NSInstrumentation@@QEAAXPEAX@Z; NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(void *)
0x1401cf753  call    cs:__imp_W32GetUserSessionState
0x1401cf75a  nop     dword ptr [rax+rax+00h]
0x1401cf75f  cmp     [rax+4CB0h], rsi
0x1401cf766  jz      short loc_1401CF7AB
0x1401cf768  call    cs:__imp_W32GetUserSessionState
0x1401cf76f  nop     dword ptr [rax+rax+00h]
0x1401cf774  mov     rcx, [rax+4CB0h]; this
0x1401cf77b  call    ?Destroy@UserTypeIsolationAllocators@@QEAAXXZ; UserTypeIsolationAllocators::Destroy(void)
0x1401cf780  call    cs:__imp_W32GetUserSessionState
0x1401cf787  nop     dword ptr [rax+rax+00h]
0x1401cf78c  mov     rcx, [rax+4CB0h]; Buffer
0x1401cf793  call    GreDeleteFastMutex
0x1401cf798  call    cs:__imp_W32GetUserSessionState
0x1401cf79f  nop     dword ptr [rax+rax+00h]
0x1401cf7a4  mov     [rax+4CB0h], rsi
0x1401cf7ab  call    cs:__imp_W32GetUserSessionState
0x1401cf7b2  nop     dword ptr [rax+rax+00h]
0x1401cf7b7  cmp     [rax+11668h], rsi
0x1401cf7be  jz      short loc_1401CF7F2
0x1401cf7c0  call    cs:__imp_W32GetUserSessionState
0x1401cf7c7  nop     dword ptr [rax+rax+00h]
0x1401cf7cc  mov     rcx, [rax+11668h]; Object
0x1401cf7d3  call    cs:__imp_ObfDereferenceObject
0x1401cf7da  nop     dword ptr [rax+rax+00h]
0x1401cf7df  call    cs:__imp_W32GetUserSessionState
0x1401cf7e6  nop     dword ptr [rax+rax+00h]
0x1401cf7eb  mov     [rax+11668h], rsi
0x1401cf7f2  call    cs:__imp_W32GetUserSessionState
0x1401cf7f9  nop     dword ptr [rax+rax+00h]
0x1401cf7fe  cmp     [rax+4CD8h], rsi
0x1401cf805  jz      loc_1401CF890
0x1401cf80b  call    cs:__imp_W32GetUserSessionState
0x1401cf812  nop     dword ptr [rax+rax+00h]
0x1401cf817  mov     [rax+4CF8h], rsi
0x1401cf81e  call    cs:__imp_W32GetUserSessionState
0x1401cf825  nop     dword ptr [rax+rax+00h]
0x1401cf82a  cmp     [rax+4CE8h], rsi
0x1401cf831  jz      short loc_1401CF871
0x1401cf833  call    cs:__imp_W32GetUserSessionState
0x1401cf83a  nop     dword ptr [rax+rax+00h]
0x1401cf83f  mov     rcx, [rax+4CF0h]; HeapHandle
0x1401cf846  call    cs:__imp_RtlDestroyHeap
0x1401cf84d  nop     dword ptr [rax+rax+00h]
0x1401cf852  call    cs:__imp_W32GetUserSessionState
0x1401cf859  nop     dword ptr [rax+rax+00h]
0x1401cf85e  mov     rcx, [rax+4CE8h]; MappedBase
0x1401cf865  call    cs:__imp_MmUnmapViewInSessionSpace
0x1401cf86c  nop     dword ptr [rax+rax+00h]
0x1401cf871  call    cs:__imp_W32GetUserSessionState
0x1401cf878  nop     dword ptr [rax+rax+00h]
0x1401cf87d  mov     rcx, [rax+4CD8h]; Object
0x1401cf884  call    cs:__imp_ObfDereferenceObject
0x1401cf88b  nop     dword ptr [rax+rax+00h]
0x1401cf890  call    cs:__imp_W32GetUserSessionState
0x1401cf897  nop     dword ptr [rax+rax+00h]
0x1401cf89c  cmp     [rax+0DDA8h], rsi
0x1401cf8a3  jz      short loc_1401CF8BD
0x1401cf8a5  call    cs:__imp_W32GetUserSessionState
0x1401cf8ac  nop     dword ptr [rax+rax+00h]
0x1401cf8b1  mov     rcx, [rax+0DDA8h]; Buffer
0x1401cf8b8  call    GreDeleteFastMutex
0x1401cf8bd  call    cs:__imp_W32GetUserSessionState
0x1401cf8c4  nop     dword ptr [rax+rax+00h]
0x1401cf8c9  cmp     [rax+0F4E0h], rsi
0x1401cf8d0  jz      short loc_1401CF8EA
0x1401cf8d2  call    cs:__imp_W32GetUserSessionState
0x1401cf8d9  nop     dword ptr [rax+rax+00h]
0x1401cf8de  mov     rcx, [rax+0F4E0h]; Buffer
0x1401cf8e5  call    GreDeleteFastMutex
0x1401cf8ea  call    cs:__imp_W32GetUserSessionState
0x1401cf8f1  nop     dword ptr [rax+rax+00h]
0x1401cf8f6  cmp     [rax+4CE0h], rsi
0x1401cf8fd  jz      short loc_1401CF952
0x1401cf8ff  call    cs:__imp_W32GetUserSessionState
0x1401cf906  nop     dword ptr [rax+rax+00h]
0x1401cf90b  cmp     [rax+4CD0h], rsi
0x1401cf912  jz      short loc_1401CF933
0x1401cf914  call    cs:__imp_W32GetUserSessionState
0x1401cf91b  nop     dword ptr [rax+rax+00h]
0x1401cf920  mov     rcx, [rax+4CD0h]; MappedBase
0x1401cf927  call    cs:__imp_MmUnmapViewInSessionSpace
0x1401cf92e  nop     dword ptr [rax+rax+00h]
0x1401cf933  call    cs:__imp_W32GetUserSessionState
0x1401cf93a  nop     dword ptr [rax+rax+00h]
0x1401cf93f  mov     rcx, [rax+4CE0h]; Object
0x1401cf946  call    cs:__imp_ObfDereferenceObject
0x1401cf94d  nop     dword ptr [rax+rax+00h]
0x1401cf952  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf959  nop     dword ptr [rax+rax+00h]
0x1401cf95e  mov     rcx, [rax+30h]
0x1401cf962  mov     rax, [rcx+128h]
0x1401cf969  test    rax, rax
0x1401cf96c  jz      short loc_1401CF9AE
0x1401cf96e  call    _guard_dispatch_icall
0x1401cf973  test    eax, eax
0x1401cf975  js      short loc_1401CF9AE
0x1401cf977  call    cs:__imp_W32GetUserSessionState
0x1401cf97e  nop     dword ptr [rax+rax+00h]
0x1401cf983  mov     rbx, rax
0x1401cf986  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf98d  nop     dword ptr [rax+rax+00h]
0x1401cf992  mov     rcx, [rax+30h]
0x1401cf996  mov     rax, [rcx+130h]
0x1401cf99d  test    rax, rax
0x1401cf9a0  jz      short loc_1401CF9AE
0x1401cf9a2  lea     rcx, [rbx+10110h]
0x1401cf9a9  call    _guard_dispatch_icall
0x1401cf9ae  call    cs:__imp_W32GetUserSessionState
0x1401cf9b5  nop     dword ptr [rax+rax+00h]
0x1401cf9ba  cmp     [rax+110E0h], esi
0x1401cf9c0  jz      short loc_1401CF9FF
0x1401cf9c2  call    cs:__imp_W32GetUserSessionState
0x1401cf9c9  nop     dword ptr [rax+rax+00h]
0x1401cf9ce  mov     rbx, rax
0x1401cf9d1  mov     rdi, [rax+4BD8h]
0x1401cf9d8  test    rdi, rdi
  ... truncated ...
```
