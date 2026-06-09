# Win32KBaseDriverUnload(_DRIVER_OBJECT *)

- ea: `0x1401cebd0`
- end: `0x1401cf36b`
- name: `?Win32KBaseDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `1947`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402db400`

## callees

- `0x140030a30`
- `0x14003108c`
- `0x140032860`
- `0x1400411c0`
- `0x1400718f0`
- `0x14009bf7c`
- `0x14009d700`
- `0x1400e377c`
- `0x14011d23c`
- `0x14012c234`
- `0x140131f74`
- `0x1401653d0`
- `0x140173c94`
- `0x14017933c`
- `0x140181c10`
- `0x140185a54`
- `0x140187d50`
- `0x1401aa640`
- `0x1401aa760`
- `0x1401ac2a8`
- `0x1401ac504`
- `0x1401acc10`
- `0x1401b8028`
- `0x1401b93c0`
- `0x1401c957c`
- `0x1401cebd0`
- `0x1401d1f48`
- `0x1402160f4`
- `0x140236530`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401cf2a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cf2a3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ced2a`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ced2a`
- `ntoskrnl!RtlDestroyHeap` at `0x1401cf026`
- `ntoskrnl!RtlDestroyHeap` at `0x1401cf026`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401cf045`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401cf107`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401cf045`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401cf107`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cefb3`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf064`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf126`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cefb3`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf064`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cf126`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cec78`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cec9d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cecbe`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cece3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ced5d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ced82`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf132`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf166`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf224`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf249`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cec78`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cec9d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cecbe`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cece3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ced5d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ced82`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf132`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf166`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf224`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cf249`
- `WIN32K!W32GetSessionState` at `0x1401cedac`
- `WIN32K!W32GetSessionState` at `0x1401cf31c`
- `WIN32K!W32GetSessionState` at `0x1401cf336`
- `WIN32K!W32GetSessionState` at `0x1401cedac`
- `WIN32K!W32GetSessionState` at `0x1401cf31c`
- `WIN32K!W32GetSessionState` at `0x1401cf336`
- `WIN32K!W32UnregisterSessionProcess` at `0x1401cee0c`
- `WIN32K!W32UnregisterSessionProcess` at `0x1401cee0c`
- `WIN32K!W32GetDCompSessionState` at `0x1401ced04`
- `WIN32K!W32GetDCompSessionState` at `0x1401ced43`
- `WIN32K!W32GetDCompSessionState` at `0x1401ced04`
- `WIN32K!W32GetDCompSessionState` at `0x1401ced43`
- `WIN32K!W32GetUserSessionState` at `0x1401cec26`
- `WIN32K!W32GetUserSessionState` at `0x1401ceddf`
- `WIN32K!W32GetUserSessionState` at `0x1401cedf8`
- `WIN32K!W32GetUserSessionState` at `0x1401cee18`
- `WIN32K!W32GetUserSessionState` at `0x1401cee31`
- `WIN32K!W32GetUserSessionState` at `0x1401cee4d`
- `WIN32K!W32GetUserSessionState` at `0x1401cee64`
- `WIN32K!W32GetUserSessionState` at `0x1401cee8e`
- `WIN32K!W32GetUserSessionState` at `0x1401ceeaa`
- `WIN32K!W32GetUserSessionState` at `0x1401ceedc`
- `WIN32K!W32GetUserSessionState` at `0x1401ceef0`
- `WIN32K!W32GetUserSessionState` at `0x1401cef05`
- `WIN32K!W32GetUserSessionState` at `0x1401cef18`
- `WIN32K!W32GetUserSessionState` at `0x1401cef33`
- `WIN32K!W32GetUserSessionState` at `0x1401cef48`
- `WIN32K!W32GetUserSessionState` at `0x1401cef60`
- `WIN32K!W32GetUserSessionState` at `0x1401cef78`
- `WIN32K!W32GetUserSessionState` at `0x1401cef8b`
- `WIN32K!W32GetUserSessionState` at `0x1401cefa0`
- `WIN32K!W32GetUserSessionState` at `0x1401cefbf`
- `WIN32K!W32GetUserSessionState` at `0x1401cefd2`
- `WIN32K!W32GetUserSessionState` at `0x1401cefeb`
- `WIN32K!W32GetUserSessionState` at `0x1401ceffe`
- `WIN32K!W32GetUserSessionState` at `0x1401cf013`
- `WIN32K!W32GetUserSessionState` at `0x1401cf032`
- `WIN32K!W32GetUserSessionState` at `0x1401cf051`
- `WIN32K!W32GetUserSessionState` at `0x1401cf070`
- `WIN32K!W32GetUserSessionState` at `0x1401cf085`
- `WIN32K!W32GetUserSessionState` at `0x1401cf09d`
- `WIN32K!W32GetUserSessionState` at `0x1401cf0b2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf0ca`
- `WIN32K!W32GetUserSessionState` at `0x1401cf0df`
- `WIN32K!W32GetUserSessionState` at `0x1401cf0f4`
- `WIN32K!W32GetUserSessionState` at `0x1401cf113`
- `WIN32K!W32GetUserSessionState` at `0x1401cf157`
- `WIN32K!W32GetUserSessionState` at `0x1401cf18e`
- `WIN32K!W32GetUserSessionState` at `0x1401cf1a2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf1bd`
- `WIN32K!W32GetUserSessionState` at `0x1401cf1df`
- `WIN32K!W32GetUserSessionState` at `0x1401cf1f4`
- `WIN32K!W32GetUserSessionState` at `0x1401cf211`
- `WIN32K!W32GetUserSessionState` at `0x1401cf279`
- `WIN32K!W32GetUserSessionState` at `0x1401cf28e`
- `WIN32K!W32GetUserSessionState` at `0x1401cf2af`
- `WIN32K!W32GetUserSessionState` at `0x1401cf2c7`
- `WIN32K!W32GetUserSessionState` at `0x1401cec26`
- `WIN32K!W32GetUserSessionState` at `0x1401ceddf`
- `WIN32K!W32GetUserSessionState` at `0x1401cedf8`
- `WIN32K!W32GetUserSessionState` at `0x1401cee18`
- `WIN32K!W32GetUserSessionState` at `0x1401cee31`
- `WIN32K!W32GetUserSessionState` at `0x1401cee4d`
- `WIN32K!W32GetUserSessionState` at `0x1401cee64`
- `WIN32K!W32GetUserSessionState` at `0x1401cee8e`
- `WIN32K!W32GetUserSessionState` at `0x1401ceeaa`
- `WIN32K!W32GetUserSessionState` at `0x1401ceedc`
- `WIN32K!W32GetUserSessionState` at `0x1401ceef0`
- `WIN32K!W32GetUserSessionState` at `0x1401cef05`
- `WIN32K!W32GetUserSessionState` at `0x1401cef18`
- `WIN32K!W32GetUserSessionState` at `0x1401cef33`
- `WIN32K!W32GetUserSessionState` at `0x1401cef48`
- `WIN32K!W32GetUserSessionState` at `0x1401cef60`
- `WIN32K!W32GetUserSessionState` at `0x1401cef78`
- `WIN32K!W32GetUserSessionState` at `0x1401cef8b`
- `WIN32K!W32GetUserSessionState` at `0x1401cefa0`
- `WIN32K!W32GetUserSessionState` at `0x1401cefbf`
- `WIN32K!W32GetUserSessionState` at `0x1401cefd2`
- `WIN32K!W32GetUserSessionState` at `0x1401cefeb`
- `WIN32K!W32GetUserSessionState` at `0x1401ceffe`
- `WIN32K!W32GetUserSessionState` at `0x1401cf013`
- `WIN32K!W32GetUserSessionState` at `0x1401cf032`
- `WIN32K!W32GetUserSessionState` at `0x1401cf051`
- `WIN32K!W32GetUserSessionState` at `0x1401cf070`
- `WIN32K!W32GetUserSessionState` at `0x1401cf085`
- `WIN32K!W32GetUserSessionState` at `0x1401cf09d`
- `WIN32K!W32GetUserSessionState` at `0x1401cf0b2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf0ca`
- `WIN32K!W32GetUserSessionState` at `0x1401cf0df`
- `WIN32K!W32GetUserSessionState` at `0x1401cf0f4`
- `WIN32K!W32GetUserSessionState` at `0x1401cf113`
- `WIN32K!W32GetUserSessionState` at `0x1401cf157`
- `WIN32K!W32GetUserSessionState` at `0x1401cf18e`
- `WIN32K!W32GetUserSessionState` at `0x1401cf1a2`
- `WIN32K!W32GetUserSessionState` at `0x1401cf1bd`
- `WIN32K!W32GetUserSessionState` at `0x1401cf1df`
- `WIN32K!W32GetUserSessionState` at `0x1401cf1f4`
- `WIN32K!W32GetUserSessionState` at `0x1401cf211`
- `WIN32K!W32GetUserSessionState` at `0x1401cf279`
- `WIN32K!W32GetUserSessionState` at `0x1401cf28e`
- `WIN32K!W32GetUserSessionState` at `0x1401cf2af`
- `WIN32K!W32GetUserSessionState` at `0x1401cf2c7`

## pseudocode

```c
void __fastcall Win32KBaseDriverUnload(struct _DRIVER_OBJECT *a1, __int64 a2, __int64 a3)
{
  char v3; // bl
  bool v4; // di
  __int64 UserSessionState; // rax
  int v6; // r8d
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int (*v10)(void); // rax
  void (*v11)(void); // rax
  int (*v12)(void); // rax
  __int64 v13; // rcx
  void (*v14)(void); // rax
  unsigned int v15; // edx
  __int64 DCompSessionState; // rbx
  void *v17; // rcx
  struct _ERESOURCE *v18; // rcx
  unsigned int v19; // edx
  void *v20; // rcx
  Gre::Base *v21; // rcx
  int (*v22)(void); // rax
  void (*v23)(void); // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rdi
  OPM *v28; // rbx
  void *v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // rdx
  _QWORD *v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rcx
  _QWORD *v45; // rdi
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  _QWORD *v51; // rbx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  _QWORD *v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // r8
  void *v66; // rbx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // rax
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
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // r8
  __int64 v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // r8
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rcx
  __int64 v106; // r8
  __int64 v107; // rax
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // rax
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // r8
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rdx
  __int64 v121; // rcx
  __int64 v122; // r8
  int (*v123)(void); // rax
  __int64 v124; // rbx
  __int64 v125; // rcx
  void (__fastcall *v126)(__int64); // rax
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // rbx
  void *v131; // rdi
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // r8
  __int64 v136; // rdx
  CAsyncKeyEventMonitor *v137; // rcx
  __int64 v138; // r8
  int (*v139)(void); // rax
  __int64 v140; // rcx
  void (*v141)(void); // rax
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // r8
  __int64 v145; // rdx
  __int64 v146; // rcx
  __int64 v147; // r8
  __int64 v148; // rax
  __int64 v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // r8
  __int64 v152; // rdx
  __int64 v153; // rcx
  __int64 v154; // r8
  __int64 v155; // rax
  __int64 v156; // rdi
  void *v157; // rbx
  __int64 v158; // rcx
  PDRIVER_OBJECT v159; // rbx
  __int64 SessionState; // rax
  __int64 v161; // rcx
  __int64 v162; // rax
  volatile signed __int32 *v163[24]; // [rsp+40h] [rbp-C8h] BYREF

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
      (__int64)WPP_5f70da56b76d32e0a0cd6b880e011bcd_Traceguids);
  }
  CTempW32ThreadNonPaged::CTempW32ThreadNonPaged((CTempW32ThreadNonPaged *)v163);
  v9 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v8) + 48);
  v10 = *(int (**)(void))(v9 + 3848);
  if ( v10 )
  {
    if ( v10() >= 0 )
    {
      v9 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v9) + 48);
      v11 = *(void (**)(void))(v9 + 3856);
      if ( v11 )
        v11();
    }
  }
  v12 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v9) + 48) + 248LL);
  if ( v12 )
  {
    if ( v12() >= 0 )
    {
      v14 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v13) + 48) + 256LL);
      if ( v14 )
        v14();
    }
  }
  DCompSessionState = W32GetDCompSessionState();
  v17 = *(void **)(DCompSessionState + 16);
  if ( v17 )
    DirectComposition::CConnection::`scalar deleting destructor'(v17, v15);
  v18 = *(struct _ERESOURCE **)(DCompSessionState + 32);
  if ( v18 )
  {
    ExDeleteResourceLite(v18);
    GreDeleteFastMutex(*(PVOID *)(DCompSessionState + 32));
    *(_QWORD *)(DCompSessionState + 32) = 0;
  }
  v20 = *(void **)(W32GetDCompSessionState() + 24);
  if ( v20 )
    DirectComposition::CSynchronizationManager::`scalar deleting destructor'(v20, v19);
  v21 = *(Gre::Base **)(W32GetWin32kBaseApiSetTable(v20) + 48);
  v22 = (int (*)(void))*((_QWORD *)v21 + 35);
  if ( v22 )
  {
    if ( v22() >= 0 )
    {
      v21 = *(Gre::Base **)(W32GetWin32kBaseApiSetTable(v21) + 48);
      v23 = (void (*)(void))*((_QWORD *)v21 + 36);
      if ( v23 )
        v23();
    }
  }
  if ( Gre::Base::IsSessionGlobalsAreaAllocated(v21) )
  {
    v27 = *(_QWORD *)(W32GetSessionState(v25) + 88);
    v28 = *(OPM **)(v27 + 3728);
    if ( v28 )
    {
      COPM::~COPM(*(COPM **)(v27 + 3728));
      OPM::OPMFreeMemory(v28, v29);
    }
    *(_QWORD *)(v27 + 3728) = 0;
  }
  v30 = W32GetUserSessionState(v25, v24, v26);
  *(_DWORD *)(v30 + 68920) |= 0x80u;
  MultiUserNtGreCleanup();
  v34 = W32GetUserSessionState(v32, v31, v33);
  *(_DWORD *)(v34 + 68920) |= 0x100u;
  W32UnregisterSessionProcess();
  if ( *(_QWORD *)(W32GetUserSessionState(v36, v35, v37) + 56744) )
  {
    v42 = (_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v39, v38, v40) + 56744) + 24LL);
    if ( (_QWORD *)*v42 != v42 )
    {
      v44 = *(_QWORD *)(W32GetUserSessionState(v42, v41, v43) + 56744);
      v45 = *(_QWORD **)(v44 + 24);
      v48 = *(_QWORD *)(W32GetUserSessionState(v44, v46, v47) + 56744) + 24LL;
      if ( v45 != (_QWORD *)v48 )
      {
        do
        {
          v51 = (_QWORD *)*v45;
          GreDeleteFastMutex(v45);
          v45 = v51;
          v49 = *(_QWORD *)(W32GetUserSessionState(v53, v52, v54) + 56744) + 24LL;
        }
        while ( v51 != (_QWORD *)v49 );
      }
      v55 = (_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v49, v48, v50) + 56744) + 24LL);
      v55[1] = v55;
      *v55 = v55;
    }
  }
  InputUnInitialize();
  Win32kNtUserCleanup();
  DestroyHandleTableObjects();
  CleanupDomainLocks();
  v59 = W32GetUserSessionState(v57, v56, v58);
  *(_DWORD *)(v59 + 68920) |= 0x200u;
  if ( *(_QWORD *)(W32GetUserSessionState(v61, v60, v62) + 42384) )
  {
    v66 = *(void **)(W32GetUserSessionState(v64, v63, v65) + 42384);
    v70 = W32GetUserSessionState(v68, v67, v69);
    NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(
      (NSInstrumentation::CLeakTrackingAllocator *)(v70 + 72016),
      v66);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v64, v63, v65) + 19632) )
  {
    v74 = W32GetUserSessionState(v72, v71, v73);
    UserTypeIsolationAllocators::Destroy(*(UserTypeIsolationAllocators **)(v74 + 19632));
    v78 = W32GetUserSessionState(v76, v75, v77);
    GreDeleteFastMutex(*(PVOID *)(v78 + 19632));
    *(_QWORD *)(W32GetUserSessionState(v80, v79, v81) + 19632) = 0;
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v72, v71, v73) + 71272) )
  {
    v85 = W32GetUserSessionState(v83, v82, v84);
    ObfDereferenceObject(*(PVOID *)(v85 + 71272));
    *(_QWORD *)(W32GetUserSessionState(v87, v86, v88) + 71272) = 0;
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v83, v82, v84) + 19672) )
  {
    *(_QWORD *)(W32GetUserSessionState(v90, v89, v91) + 19704) = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v93, v92, v94) + 19688) )
    {
      v98 = W32GetUserSessionState(v96, v95, v97);
      RtlDestroyHeap(*(PVOID *)(v98 + 19696));
      v102 = W32GetUserSessionState(v100, v99, v101);
      MmUnmapViewInSessionSpace(*(PVOID *)(v102 + 19688));
    }
    v103 = W32GetUserSessionState(v96, v95, v97);
    ObfDereferenceObject(*(PVOID *)(v103 + 19672));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v90, v89, v91) + 56744) )
  {
    v107 = W32GetUserSessionState(v105, v104, v106);
    GreDeleteFastMutex(*(PVOID *)(v107 + 56744));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v105, v104, v106) + 62688) )
  {
    v111 = W32GetUserSessionState(v109, v108, v110);
    GreDeleteFastMutex(*(PVOID *)(v111 + 62688));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v109, v108, v110) + 19680) )
  {
    if ( *(_QWORD *)(W32GetUserSessionState(v113, v112, v114) + 19664) )
    {
      v118 = W32GetUserSessionState(v116, v115, v117);
      MmUnmapViewInSessionSpace(*(PVOID *)(v118 + 19664));
    }
    v119 = W32GetUserSessionState(v116, v115, v117);
    ObfDereferenceObject(*(PVOID *)(v119 + 19680));
  }
  v121 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v113) + 48);
  v123 = *(int (**)(void))(v121 + 296);
  if ( v123 )
  {
    if ( v123() >= 0 )
    {
      v124 = W32GetUserSessionState(v121, v120, v122);
      v121 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v125) + 48);
      v126 = *(void (__fastcall **)(__int64))(v121 + 304);
      if ( v126 )
        v126(v124 + 65808);
    }
  }
  if ( *(_DWORD *)(W32GetUserSessionState(v121, v120, v122) + 69856) )
  {
    v130 = W32GetUserSessionState(v128, v127, v129);
    v131 = *(void **)(v130 + 19416);
    if ( v131 )
    {
      v132 = W32GetUserSessionState(v128, v127, v129);
      NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(
        (NSInstrumentation::CLeakTrackingAllocator *)(v132 + 72016),
        v131);
      *(_QWORD *)(v130 + 19416) = 0;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v128, v127, v129) + 14440) )
  {
    v137 = *(CAsyncKeyEventMonitor **)(W32GetUserSessionState(v134, v133, v135) + 14440);
    if ( v137 )
      CAsyncKeyEventMonitor::`scalar deleting destructor'(v137, v136);
    *(_QWORD *)(W32GetUserSessionState(v137, v136, v138) + 14440) = 0;
  }
  v139 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v134) + 48) + 312LL);
  if ( v139 )
  {
    if ( v139() >= 0 )
    {
      v141 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v140) + 48) + 320LL);
      if ( v141 )
        v141();
    }
  }
  CoreMessagingKPort::UnInitialize();
  CoreMsgUninitialize();
  RIMUnInitialize();
  if ( *(_QWORD *)(W32GetUserSessionState(v143, v142, v144) + 42360) )
  {
    v148 = W32GetUserSessionState(v146, v145, v147);
    ExFreePoolWithTag(*(PVOID *)(v148 + 42360), 0);
    *(_QWORD *)(W32GetUserSessionState(v150, v149, v151) + 42360) = 0;
  }
  FreeWin32KSyscallFilter();
  v155 = W32GetUserSessionState(v153, v152, v154);
  v156 = v155;
  v157 = *(void **)(v155 + 41144);
  if ( v157 )
  {
    CQoSReport::~CQoSReport(*(CQoSReport **)(v155 + 41144));
    GreDeleteFastMutex(v157);
  }
  *(_QWORD *)(v156 + 41144) = 0;
  UninitializeWin32PoolTracking();
  UninitializeWin32SiloGlobals();
  v159 = gpWin32kDriverObject;
  if ( gpWin32kDriverObject )
  {
    UninitializeBaseWppLog();
    EditionUninitializeWppLogging(v159);
  }
  SessionState = W32GetSessionState(v158);
  FreePerSessionWin32kCall(SessionState + 152);
  v162 = W32GetSessionState(v161);
  FreeWin32kApiSetTable(v162 + 152);
  CTempW32ThreadNonPaged::~CTempW32ThreadNonPaged(v163);
}

```

## disassembly

```asm
0x1401cebd0  mov     [rsp+arg_0], rbx
0x1401cebd5  mov     [rsp+arg_8], rsi
0x1401cebda  push    rdi
0x1401cebdb  sub     rsp, 100h
0x1401cebe2  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cebe9  lea     rax, WPP_GLOBAL_Control
0x1401cebf0  xor     esi, esi
0x1401cebf2  cmp     rcx, rax
0x1401cebf5  jz      short loc_1401CEC08
0x1401cebf7  test    dword ptr [rcx+2Ch], 2000h
0x1401cebfe  jz      short loc_1401CEC08
0x1401cec00  cmp     byte ptr [rcx+29h], 4
0x1401cec04  mov     bl, 1
0x1401cec06  jnb     short loc_1401CEC0B
0x1401cec08  mov     bl, sil
0x1401cec0b  lea     rax, WPP_RECORDER_INITIALIZED
0x1401cec12  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401cec19  setnz   dil
0x1401cec1d  test    bl, bl
0x1401cec1f  jnz     short loc_1401CEC26
0x1401cec21  test    dil, dil
0x1401cec24  jz      short loc_1401CEC6E
0x1401cec26  call    cs:__imp_W32GetUserSessionState
0x1401cec2d  nop     dword ptr [rax+rax+00h]
0x1401cec32  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cec39  mov     r8b, dil
0x1401cec3c  mov     dl, bl
0x1401cec3e  mov     r9, [rax+10E10h]
0x1401cec45  lea     rax, WPP_5f70da56b76d32e0a0cd6b880e011bcd_Traceguids
0x1401cec4c  mov     rcx, [rcx+18h]
0x1401cec50  mov     [rsp+108h+var_D0], rax
0x1401cec55  mov     [rsp+108h+var_D8], 0Bh
0x1401cec5c  mov     [rsp+108h+var_E0], 0Eh
0x1401cec64  mov     [rsp+108h+var_E8], 4
0x1401cec69  call    WPP_RECORDER_AND_TRACE_SF_
0x1401cec6e  lea     rcx, [rsp+108h+var_C8]; this
0x1401cec73  call    ??0CTempW32ThreadNonPaged@@QEAA@XZ; CTempW32ThreadNonPaged::CTempW32ThreadNonPaged(void)
0x1401cec78  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cec7f  nop     dword ptr [rax+rax+00h]
0x1401cec84  mov     rcx, [rax+30h]
0x1401cec88  mov     rax, [rcx+0F08h]
0x1401cec8f  test    rax, rax
0x1401cec92  jz      short loc_1401CECBE
0x1401cec94  call    _guard_dispatch_icall
0x1401cec99  test    eax, eax
0x1401cec9b  js      short loc_1401CECBE
0x1401cec9d  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ceca4  nop     dword ptr [rax+rax+00h]
0x1401ceca9  mov     rcx, [rax+30h]
0x1401cecad  mov     rax, [rcx+0F10h]
0x1401cecb4  test    rax, rax
0x1401cecb7  jz      short loc_1401CECBE
0x1401cecb9  call    _guard_dispatch_icall
0x1401cecbe  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cecc5  nop     dword ptr [rax+rax+00h]
0x1401cecca  mov     rcx, [rax+30h]
0x1401cecce  mov     rax, [rcx+0F8h]
0x1401cecd5  test    rax, rax
0x1401cecd8  jz      short loc_1401CED04
0x1401cecda  call    _guard_dispatch_icall
0x1401cecdf  test    eax, eax
0x1401cece1  js      short loc_1401CED04
0x1401cece3  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cecea  nop     dword ptr [rax+rax+00h]
0x1401cecef  mov     rcx, [rax+30h]
0x1401cecf3  mov     rax, [rcx+100h]
0x1401cecfa  test    rax, rax
0x1401cecfd  jz      short loc_1401CED04
0x1401cecff  call    _guard_dispatch_icall
0x1401ced04  call    cs:__imp_W32GetDCompSessionState
0x1401ced0b  nop     dword ptr [rax+rax+00h]
0x1401ced10  mov     rbx, rax
0x1401ced13  mov     rcx, [rax+10h]; Buffer
0x1401ced17  test    rcx, rcx
0x1401ced1a  jz      short loc_1401CED21
0x1401ced1c  call    ??_GCConnection@DirectComposition@@AEAAPEAXI@Z; DirectComposition::CConnection::`scalar deleting destructor'(uint)
0x1401ced21  mov     rcx, [rbx+20h]; Resource
0x1401ced25  test    rcx, rcx
0x1401ced28  jz      short loc_1401CED43
0x1401ced2a  call    cs:__imp_ExDeleteResourceLite
0x1401ced31  nop     dword ptr [rax+rax+00h]
0x1401ced36  mov     rcx, [rbx+20h]; Buffer
0x1401ced3a  call    GreDeleteFastMutex
0x1401ced3f  mov     [rbx+20h], rsi
0x1401ced43  call    cs:__imp_W32GetDCompSessionState
0x1401ced4a  nop     dword ptr [rax+rax+00h]
0x1401ced4f  mov     rcx, [rax+18h]; Buffer
0x1401ced53  test    rcx, rcx
0x1401ced56  jz      short loc_1401CED5D
0x1401ced58  call    ??_GCSynchronizationManager@DirectComposition@@IEAAPEAXI@Z; DirectComposition::CSynchronizationManager::`scalar deleting destructor'(uint)
0x1401ced5d  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ced64  nop     dword ptr [rax+rax+00h]
0x1401ced69  mov     rcx, [rax+30h]
0x1401ced6d  mov     rax, [rcx+118h]
0x1401ced74  test    rax, rax
0x1401ced77  jz      short loc_1401CEDA3
0x1401ced79  call    _guard_dispatch_icall
0x1401ced7e  test    eax, eax
0x1401ced80  js      short loc_1401CEDA3
0x1401ced82  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ced89  nop     dword ptr [rax+rax+00h]
0x1401ced8e  mov     rcx, [rax+30h]
0x1401ced92  mov     rax, [rcx+120h]
0x1401ced99  test    rax, rax
0x1401ced9c  jz      short loc_1401CEDA3
0x1401ced9e  call    _guard_dispatch_icall
0x1401ceda3  call    ?IsSessionGlobalsAreaAllocated@Base@Gre@@YA_NXZ; Gre::Base::IsSessionGlobalsAreaAllocated(void)
0x1401ceda8  test    al, al
0x1401cedaa  jz      short loc_1401CEDDF
0x1401cedac  call    cs:__imp_W32GetSessionState
0x1401cedb3  nop     dword ptr [rax+rax+00h]
0x1401cedb8  mov     rdi, [rax+58h]
0x1401cedbc  mov     rbx, [rdi+0E90h]
0x1401cedc3  test    rbx, rbx
0x1401cedc6  jz      short loc_1401CEDD8
0x1401cedc8  mov     rcx, rbx; this
0x1401cedcb  call    ??1COPM@@QEAA@XZ; COPM::~COPM(void)
0x1401cedd0  mov     rcx, rbx; this
0x1401cedd3  call    ?OPMFreeMemory@OPM@@YAXPEAX@Z; OPM::OPMFreeMemory(void *)
0x1401cedd8  mov     [rdi+0E90h], rsi
0x1401ceddf  call    cs:__imp_W32GetUserSessionState
0x1401cede6  nop     dword ptr [rax+rax+00h]
0x1401cedeb  bts     dword ptr [rax+10D38h], 7
0x1401cedf3  call    MultiUserNtGreCleanup
0x1401cedf8  call    cs:__imp_W32GetUserSessionState
0x1401cedff  nop     dword ptr [rax+rax+00h]
0x1401cee04  bts     dword ptr [rax+10D38h], 8
0x1401cee0c  call    cs:__imp_W32UnregisterSessionProcess
0x1401cee13  nop     dword ptr [rax+rax+00h]
0x1401cee18  call    cs:__imp_W32GetUserSessionState
0x1401cee1f  nop     dword ptr [rax+rax+00h]
0x1401cee24  cmp     [rax+0DDA8h], rsi
0x1401cee2b  jz      loc_1401CEEC8
0x1401cee31  call    cs:__imp_W32GetUserSessionState
0x1401cee38  nop     dword ptr [rax+rax+00h]
0x1401cee3d  mov     rcx, [rax+0DDA8h]
0x1401cee44  add     rcx, 18h
0x1401cee48  cmp     [rcx], rcx
0x1401cee4b  jz      short loc_1401CEEC8
0x1401cee4d  call    cs:__imp_W32GetUserSessionState
0x1401cee54  nop     dword ptr [rax+rax+00h]
0x1401cee59  mov     rcx, [rax+0DDA8h]
0x1401cee60  mov     rdi, [rcx+18h]
0x1401cee64  call    cs:__imp_W32GetUserSessionState
0x1401cee6b  nop     dword ptr [rax+rax+00h]
0x1401cee70  mov     rdx, [rax+0DDA8h]
0x1401cee77  add     rdx, 18h
0x1401cee7b  cmp     rdi, rdx
0x1401cee7e  jz      short loc_1401CEEAA
0x1401cee80  mov     rbx, [rdi]
0x1401cee83  mov     rcx, rdi; Buffer
0x1401cee86  call    GreDeleteFastMutex
0x1401cee8b  mov     rdi, rbx
0x1401cee8e  call    cs:__imp_W32GetUserSessionState
0x1401cee95  nop     dword ptr [rax+rax+00h]
0x1401cee9a  mov     rcx, [rax+0DDA8h]
0x1401ceea1  add     rcx, 18h
0x1401ceea5  cmp     rbx, rcx
0x1401ceea8  jnz     short loc_1401CEE80
0x1401ceeaa  call    cs:__imp_W32GetUserSessionState
0x1401ceeb1  nop     dword ptr [rax+rax+00h]
0x1401ceeb6  mov     rcx, [rax+0DDA8h]
0x1401ceebd  add     rcx, 18h
0x1401ceec1  mov     [rcx+8], rcx
0x1401ceec5  mov     [rcx], rcx
0x1401ceec8  call    InputUnInitialize
0x1401ceecd  call    ?Win32kNtUserCleanup@@YAHXZ; Win32kNtUserCleanup(void)
0x1401ceed2  call    ?DestroyHandleTableObjects@@YAXXZ; DestroyHandleTableObjects(void)
0x1401ceed7  call    ?CleanupDomainLocks@@YAXXZ; CleanupDomainLocks(void)
0x1401ceedc  call    cs:__imp_W32GetUserSessionState
0x1401ceee3  nop     dword ptr [rax+rax+00h]
0x1401ceee8  bts     dword ptr [rax+10D38h], 9
0x1401ceef0  call    cs:__imp_W32GetUserSessionState
0x1401ceef7  nop     dword ptr [rax+rax+00h]
0x1401ceefc  cmp     [rax+0A590h], rsi
0x1401cef03  jz      short loc_1401CEF33
0x1401cef05  call    cs:__imp_W32GetUserSessionState
0x1401cef0c  nop     dword ptr [rax+rax+00h]
0x1401cef11  mov     rbx, [rax+0A590h]
0x1401cef18  call    cs:__imp_W32GetUserSessionState
0x1401cef1f  nop     dword ptr [rax+rax+00h]
0x1401cef24  mov     rdx, rbx; void *
0x1401cef27  lea     rcx, [rax+11950h]; this
0x1401cef2e  call    ?FreePagedLookasideList@CLeakTrackingAllocator@NSInstrumentation@@QEAAXPEAX@Z; NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(void *)
0x1401cef33  call    cs:__imp_W32GetUserSessionState
0x1401cef3a  nop     dword ptr [rax+rax+00h]
0x1401cef3f  cmp     [rax+4CB0h], rsi
0x1401cef46  jz      short loc_1401CEF8B
0x1401cef48  call    cs:__imp_W32GetUserSessionState
0x1401cef4f  nop     dword ptr [rax+rax+00h]
0x1401cef54  mov     rcx, [rax+4CB0h]; this
0x1401cef5b  call    ?Destroy@UserTypeIsolationAllocators@@QEAAXXZ; UserTypeIsolationAllocators::Destroy(void)
0x1401cef60  call    cs:__imp_W32GetUserSessionState
0x1401cef67  nop     dword ptr [rax+rax+00h]
0x1401cef6c  mov     rcx, [rax+4CB0h]; Buffer
0x1401cef73  call    GreDeleteFastMutex
0x1401cef78  call    cs:__imp_W32GetUserSessionState
0x1401cef7f  nop     dword ptr [rax+rax+00h]
0x1401cef84  mov     [rax+4CB0h], rsi
0x1401cef8b  call    cs:__imp_W32GetUserSessionState
0x1401cef92  nop     dword ptr [rax+rax+00h]
0x1401cef97  cmp     [rax+11668h], rsi
0x1401cef9e  jz      short loc_1401CEFD2
0x1401cefa0  call    cs:__imp_W32GetUserSessionState
0x1401cefa7  nop     dword ptr [rax+rax+00h]
0x1401cefac  mov     rcx, [rax+11668h]; Object
0x1401cefb3  call    cs:__imp_ObfDereferenceObject
0x1401cefba  nop     dword ptr [rax+rax+00h]
0x1401cefbf  call    cs:__imp_W32GetUserSessionState
0x1401cefc6  nop     dword ptr [rax+rax+00h]
0x1401cefcb  mov     [rax+11668h], rsi
0x1401cefd2  call    cs:__imp_W32GetUserSessionState
0x1401cefd9  nop     dword ptr [rax+rax+00h]
0x1401cefde  cmp     [rax+4CD8h], rsi
0x1401cefe5  jz      loc_1401CF070
0x1401cefeb  call    cs:__imp_W32GetUserSessionState
0x1401ceff2  nop     dword ptr [rax+rax+00h]
0x1401ceff7  mov     [rax+4CF8h], rsi
0x1401ceffe  call    cs:__imp_W32GetUserSessionState
0x1401cf005  nop     dword ptr [rax+rax+00h]
0x1401cf00a  cmp     [rax+4CE8h], rsi
0x1401cf011  jz      short loc_1401CF051
0x1401cf013  call    cs:__imp_W32GetUserSessionState
0x1401cf01a  nop     dword ptr [rax+rax+00h]
0x1401cf01f  mov     rcx, [rax+4CF0h]; HeapHandle
0x1401cf026  call    cs:__imp_RtlDestroyHeap
0x1401cf02d  nop     dword ptr [rax+rax+00h]
0x1401cf032  call    cs:__imp_W32GetUserSessionState
0x1401cf039  nop     dword ptr [rax+rax+00h]
0x1401cf03e  mov     rcx, [rax+4CE8h]; MappedBase
0x1401cf045  call    cs:__imp_MmUnmapViewInSessionSpace
0x1401cf04c  nop     dword ptr [rax+rax+00h]
0x1401cf051  call    cs:__imp_W32GetUserSessionState
0x1401cf058  nop     dword ptr [rax+rax+00h]
0x1401cf05d  mov     rcx, [rax+4CD8h]; Object
0x1401cf064  call    cs:__imp_ObfDereferenceObject
0x1401cf06b  nop     dword ptr [rax+rax+00h]
0x1401cf070  call    cs:__imp_W32GetUserSessionState
0x1401cf077  nop     dword ptr [rax+rax+00h]
0x1401cf07c  cmp     [rax+0DDA8h], rsi
0x1401cf083  jz      short loc_1401CF09D
0x1401cf085  call    cs:__imp_W32GetUserSessionState
0x1401cf08c  nop     dword ptr [rax+rax+00h]
0x1401cf091  mov     rcx, [rax+0DDA8h]; Buffer
0x1401cf098  call    GreDeleteFastMutex
0x1401cf09d  call    cs:__imp_W32GetUserSessionState
0x1401cf0a4  nop     dword ptr [rax+rax+00h]
0x1401cf0a9  cmp     [rax+0F4E0h], rsi
0x1401cf0b0  jz      short loc_1401CF0CA
0x1401cf0b2  call    cs:__imp_W32GetUserSessionState
0x1401cf0b9  nop     dword ptr [rax+rax+00h]
0x1401cf0be  mov     rcx, [rax+0F4E0h]; Buffer
0x1401cf0c5  call    GreDeleteFastMutex
0x1401cf0ca  call    cs:__imp_W32GetUserSessionState
0x1401cf0d1  nop     dword ptr [rax+rax+00h]
0x1401cf0d6  cmp     [rax+4CE0h], rsi
0x1401cf0dd  jz      short loc_1401CF132
0x1401cf0df  call    cs:__imp_W32GetUserSessionState
0x1401cf0e6  nop     dword ptr [rax+rax+00h]
0x1401cf0eb  cmp     [rax+4CD0h], rsi
0x1401cf0f2  jz      short loc_1401CF113
0x1401cf0f4  call    cs:__imp_W32GetUserSessionState
0x1401cf0fb  nop     dword ptr [rax+rax+00h]
0x1401cf100  mov     rcx, [rax+4CD0h]; MappedBase
0x1401cf107  call    cs:__imp_MmUnmapViewInSessionSpace
0x1401cf10e  nop     dword ptr [rax+rax+00h]
0x1401cf113  call    cs:__imp_W32GetUserSessionState
0x1401cf11a  nop     dword ptr [rax+rax+00h]
0x1401cf11f  mov     rcx, [rax+4CE0h]; Object
0x1401cf126  call    cs:__imp_ObfDereferenceObject
0x1401cf12d  nop     dword ptr [rax+rax+00h]
0x1401cf132  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf139  nop     dword ptr [rax+rax+00h]
0x1401cf13e  mov     rcx, [rax+30h]
0x1401cf142  mov     rax, [rcx+128h]
0x1401cf149  test    rax, rax
0x1401cf14c  jz      short loc_1401CF18E
0x1401cf14e  call    _guard_dispatch_icall
0x1401cf153  test    eax, eax
0x1401cf155  js      short loc_1401CF18E
0x1401cf157  call    cs:__imp_W32GetUserSessionState
0x1401cf15e  nop     dword ptr [rax+rax+00h]
0x1401cf163  mov     rbx, rax
0x1401cf166  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cf16d  nop     dword ptr [rax+rax+00h]
0x1401cf172  mov     rcx, [rax+30h]
0x1401cf176  mov     rax, [rcx+130h]
0x1401cf17d  test    rax, rax
0x1401cf180  jz      short loc_1401CF18E
0x1401cf182  lea     rcx, [rbx+10110h]
0x1401cf189  call    _guard_dispatch_icall
0x1401cf18e  call    cs:__imp_W32GetUserSessionState
0x1401cf195  nop     dword ptr [rax+rax+00h]
0x1401cf19a  cmp     [rax+110E0h], esi
0x1401cf1a0  jz      short loc_1401CF1DF
0x1401cf1a2  call    cs:__imp_W32GetUserSessionState
0x1401cf1a9  nop     dword ptr [rax+rax+00h]
0x1401cf1ae  mov     rbx, rax
0x1401cf1b1  mov     rdi, [rax+4BD8h]
0x1401cf1b8  test    rdi, rdi
  ... truncated ...
```
