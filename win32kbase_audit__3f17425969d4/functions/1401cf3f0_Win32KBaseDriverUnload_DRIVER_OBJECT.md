# Win32KBaseDriverUnload(_DRIVER_OBJECT *)

- ea: `0x1401cf3f0`
- end: `0x1401cfb8b`
- name: `?Win32KBaseDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `1947`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *, __int64)`
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
void __fastcall Win32KBaseDriverUnload(struct _DRIVER_OBJECT *a1, __int64 a2)
{
  char v2; // bl
  char v3; // di
  __int64 UserSessionState; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  int (*v7)(void); // rax
  void (*v8)(void); // rax
  __int64 v9; // rcx
  int (*v10)(void); // rax
  void (*v11)(void); // rax
  __int64 DCompSessionState; // rbx
  DirectComposition::CConnection *v13; // rcx
  struct _ERESOURCE *v14; // rcx
  __int64 v15; // rdx
  DirectComposition::CSynchronizationManager *v16; // rcx
  __int64 v17; // rdx
  Gre::Base *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  int (*v21)(void); // rax
  void (*v22)(void); // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdi
  OPM *v26; // rbx
  void *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  Gre::Base *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rdx
  _QWORD *v41; // rcx
  __int64 v42; // rcx
  _DWORD *v43; // rdi
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rcx
  _DWORD *v47; // rbx
  __int64 v48; // rdx
  __int64 v49; // rcx
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  char *v64; // rbx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rdx
  __int64 v108; // rcx
  int (*v109)(void); // rax
  __int64 v110; // rbx
  __int64 v111; // rcx
  void (__fastcall *v112)(__int64); // rax
  __int64 v113; // rdx
  __int64 v114; // rcx
  __int64 v115; // rbx
  char *v116; // rdi
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // rdx
  CAsyncKeyEventMonitor *v121; // rcx
  __int64 v122; // rdx
  __int64 v123; // rcx
  int (*v124)(void); // rax
  void (*v125)(void); // rax
  __int64 v126; // rdx
  __int64 v127; // rcx
  __int64 v128; // rdx
  __int64 v129; // rcx
  __int64 v130; // rdx
  __int64 v131; // rcx
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rdx
  __int64 v136; // rcx
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // rax
  __int64 v140; // rdx
  __int64 v141; // rcx
  __int64 v142; // rdi
  _DWORD *v143; // rbx
  __int64 v144; // rdx
  __int64 v145; // rdx
  __int64 v146; // rcx
  PDRIVER_OBJECT v147; // rbx
  __int64 SessionState; // rax
  __int64 v149; // rcx
  __int64 v150; // rax
  volatile signed __int32 *v151[24]; // [rsp+40h] [rbp-C8h] BYREF

  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0
    || (v2 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v2 = 0;
  }
  v3 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, a2);
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v2,
      v3,
      *(_QWORD *)(UserSessionState + 69136),
      4u,
      0xEu,
      0xBu,
      (__int64)WPP_0406774dfaff3b2fc9e8e45c21beea27_Traceguids);
  }
  CTempW32ThreadNonPaged::CTempW32ThreadNonPaged((CTempW32ThreadNonPaged *)v151);
  v6 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v5) + 48);
  v7 = *(int (**)(void))(v6 + 3848);
  if ( v7 )
  {
    if ( v7() >= 0 )
    {
      v6 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v6) + 48);
      v8 = *(void (**)(void))(v6 + 3856);
      if ( v8 )
        v8();
    }
  }
  v9 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v6) + 48);
  v10 = *(int (**)(void))(v9 + 248);
  if ( v10 )
  {
    if ( v10() >= 0 )
    {
      v9 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v9) + 48);
      v11 = *(void (**)(void))(v9 + 256);
      if ( v11 )
        v11();
    }
  }
  DCompSessionState = W32GetDCompSessionState(v9);
  v13 = *(DirectComposition::CConnection **)(DCompSessionState + 16);
  if ( v13 )
    DirectComposition::CConnection::`scalar deleting destructor'(v13);
  v14 = *(struct _ERESOURCE **)(DCompSessionState + 32);
  if ( v14 )
  {
    ExDeleteResourceLite(v14);
    GreDeleteFastMutex(*(_DWORD **)(DCompSessionState + 32), v15);
    *(_QWORD *)(DCompSessionState + 32) = 0;
  }
  v16 = *(DirectComposition::CSynchronizationManager **)(W32GetDCompSessionState(v14) + 24);
  if ( v16 )
    DirectComposition::CSynchronizationManager::`scalar deleting destructor'(v16);
  v18 = *(Gre::Base **)(W32GetWin32kBaseApiSetTable(v16) + 48);
  v21 = (int (*)(void))*((_QWORD *)v18 + 35);
  if ( v21 )
  {
    if ( v21() >= 0 )
    {
      v18 = *(Gre::Base **)(W32GetWin32kBaseApiSetTable(v18) + 48);
      v22 = (void (*)(void))*((_QWORD *)v18 + 36);
      if ( v22 )
        v22();
    }
  }
  if ( Gre::Base::IsSessionGlobalsAreaAllocated(v18, v17, v19, v20) )
  {
    v25 = *(_QWORD *)(W32GetSessionState(v24) + 88);
    v26 = *(OPM **)(v25 + 3728);
    if ( v26 )
    {
      COPM::~COPM(*(COPM **)(v25 + 3728));
      OPM::OPMFreeMemory(v26, v27);
    }
    *(_QWORD *)(v25 + 3728) = 0;
  }
  v28 = W32GetUserSessionState(v24, v23);
  *(_DWORD *)(v28 + 68920) |= 0x80u;
  MultiUserNtGreCleanup(v30, v29, v31, v32);
  v35 = W32GetUserSessionState(v34, v33);
  *(_DWORD *)(v35 + 68920) |= 0x100u;
  W32UnregisterSessionProcess();
  if ( *(_QWORD *)(W32GetUserSessionState(v37, v36) + 56744) )
  {
    v41 = (_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v39, v38) + 56744) + 24LL);
    if ( (_QWORD *)*v41 != v41 )
    {
      v42 = *(_QWORD *)(W32GetUserSessionState(v41, v40) + 56744);
      v43 = *(_DWORD **)(v42 + 24);
      v45 = *(_QWORD *)(W32GetUserSessionState(v42, v44) + 56744) + 24LL;
      if ( v43 != (_DWORD *)v45 )
      {
        do
        {
          v47 = *(_DWORD **)v43;
          GreDeleteFastMutex(v43, v45);
          v43 = v47;
          v46 = *(_QWORD *)(W32GetUserSessionState(v49, v48) + 56744) + 24LL;
        }
        while ( v47 != (_DWORD *)v46 );
      }
      v50 = (_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v46, v45) + 56744) + 24LL);
      v50[1] = v50;
      *v50 = v50;
    }
  }
  InputUnInitialize();
  Win32kNtUserCleanup(v52, v51);
  DestroyHandleTableObjects(v54, v53);
  CleanupDomainLocks(v56, v55);
  v59 = W32GetUserSessionState(v58, v57);
  *(_DWORD *)(v59 + 68920) |= 0x200u;
  if ( *(_QWORD *)(W32GetUserSessionState(v61, v60) + 42384) )
  {
    v64 = *(char **)(W32GetUserSessionState(v63, v62) + 42384);
    v67 = W32GetUserSessionState(v66, v65);
    NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(
      (NSInstrumentation::CLeakTrackingAllocator *)(v67 + 72016),
      v64);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v63, v62) + 19632) )
  {
    v70 = W32GetUserSessionState(v69, v68);
    UserTypeIsolationAllocators::Destroy(*(UserTypeIsolationAllocators **)(v70 + 19632));
    v73 = W32GetUserSessionState(v72, v71);
    GreDeleteFastMutex(*(_DWORD **)(v73 + 19632), v74);
    *(_QWORD *)(W32GetUserSessionState(v76, v75) + 19632) = 0;
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v69, v68) + 71272) )
  {
    v79 = W32GetUserSessionState(v78, v77);
    ObfDereferenceObject(*(PVOID *)(v79 + 71272));
    *(_QWORD *)(W32GetUserSessionState(v81, v80) + 71272) = 0;
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v78, v77) + 19672) )
  {
    *(_QWORD *)(W32GetUserSessionState(v83, v82) + 19704) = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v85, v84) + 19688) )
    {
      v88 = W32GetUserSessionState(v87, v86);
      RtlDestroyHeap(*(PVOID *)(v88 + 19696));
      v91 = W32GetUserSessionState(v90, v89);
      MmUnmapViewInSessionSpace(*(PVOID *)(v91 + 19688));
    }
    v92 = W32GetUserSessionState(v87, v86);
    ObfDereferenceObject(*(PVOID *)(v92 + 19672));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v83, v82) + 56744) )
  {
    v95 = W32GetUserSessionState(v94, v93);
    GreDeleteFastMutex(*(_DWORD **)(v95 + 56744), v96);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v94, v93) + 62688) )
  {
    v99 = W32GetUserSessionState(v98, v97);
    GreDeleteFastMutex(*(_DWORD **)(v99 + 62688), v100);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v98, v97) + 19680) )
  {
    if ( *(_QWORD *)(W32GetUserSessionState(v102, v101) + 19664) )
    {
      v105 = W32GetUserSessionState(v104, v103);
      MmUnmapViewInSessionSpace(*(PVOID *)(v105 + 19664));
    }
    v106 = W32GetUserSessionState(v104, v103);
    ObfDereferenceObject(*(PVOID *)(v106 + 19680));
  }
  v108 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v102) + 48);
  v109 = *(int (**)(void))(v108 + 296);
  if ( v109 )
  {
    if ( v109() >= 0 )
    {
      v110 = W32GetUserSessionState(v108, v107);
      v108 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v111) + 48);
      v112 = *(void (__fastcall **)(__int64))(v108 + 304);
      if ( v112 )
        v112(v110 + 65808);
    }
  }
  if ( *(_DWORD *)(W32GetUserSessionState(v108, v107) + 69856) )
  {
    v115 = W32GetUserSessionState(v114, v113);
    v116 = *(char **)(v115 + 19416);
    if ( v116 )
    {
      v117 = W32GetUserSessionState(v114, v113);
      NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(
        (NSInstrumentation::CLeakTrackingAllocator *)(v117 + 72016),
        v116);
      *(_QWORD *)(v115 + 19416) = 0;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v114, v113) + 14440) )
  {
    v121 = *(CAsyncKeyEventMonitor **)(W32GetUserSessionState(v119, v118) + 14440);
    if ( v121 )
      CAsyncKeyEventMonitor::`scalar deleting destructor'(v121, v120);
    *(_QWORD *)(W32GetUserSessionState(v121, v120) + 14440) = 0;
  }
  v123 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v119) + 48);
  v124 = *(int (**)(void))(v123 + 312);
  if ( v124 )
  {
    if ( v124() >= 0 )
    {
      v123 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v123) + 48);
      v125 = *(void (**)(void))(v123 + 320);
      if ( v125 )
        v125();
    }
  }
  CoreMessagingKPort::UnInitialize(v123, v122);
  CoreMsgUninitialize(v127, v126);
  RIMUnInitialize(v129, v128);
  if ( *(_QWORD *)(W32GetUserSessionState(v131, v130) + 42360) )
  {
    v134 = W32GetUserSessionState(v133, v132);
    ExFreePoolWithTag(*(PVOID *)(v134 + 42360), 0);
    *(_QWORD *)(W32GetUserSessionState(v136, v135) + 42360) = 0;
  }
  FreeWin32KSyscallFilter(v133, v132);
  v139 = W32GetUserSessionState(v138, v137);
  v142 = v139;
  v143 = *(_DWORD **)(v139 + 41144);
  if ( v143 )
  {
    CQoSReport::~CQoSReport(*(CQoSReport ***)(v139 + 41144));
    GreDeleteFastMutex(v143, v144);
  }
  *(_QWORD *)(v142 + 41144) = 0;
  UninitializeWin32PoolTracking(v141, v140);
  UninitializeWin32SiloGlobals();
  v147 = gpWin32kDriverObject;
  if ( gpWin32kDriverObject )
  {
    UninitializeBaseWppLog(v146, v145);
    EditionUninitializeWppLogging(v147);
  }
  SessionState = W32GetSessionState(v146);
  FreePerSessionWin32kCall((__int64 *)(SessionState + 152));
  v150 = W32GetSessionState(v149);
  FreeWin32kApiSetTable((_QWORD **)(v150 + 152));
  CTempW32ThreadNonPaged::~CTempW32ThreadNonPaged(v151);
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
