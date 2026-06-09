# Win32KBaseDriverUnload(_DRIVER_OBJECT *)

- ea: `0x1401ce670`
- end: `0x1401cee0b`
- name: `?Win32KBaseDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `1947`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402d9400`

## callees

- `0x14004a0d0`
- `0x140072a90`
- `0x140092d7c`
- `0x140094500`
- `0x1400d9b0c`
- `0x1400d9d20`
- `0x1400da37c`
- `0x1400dbb50`
- `0x14011d5ac`
- `0x14012c814`
- `0x140132554`
- `0x140165c70`
- `0x1401749f4`
- `0x140179e9c`
- `0x140182530`
- `0x140186bb4`
- `0x140188eb0`
- `0x1401aa0e0`
- `0x1401aa200`
- `0x1401abd48`
- `0x1401abfa4`
- `0x1401ac6b0`
- `0x1401b7ac8`
- `0x1401b8e60`
- `0x1401c901c`
- `0x1401ce670`
- `0x1401d19e8`
- `0x1402158d4`
- `0x140235b80`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401ced43`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ced43`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ce7ca`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ce7ca`
- `ntoskrnl!RtlDestroyHeap` at `0x1401ceac6`
- `ntoskrnl!RtlDestroyHeap` at `0x1401ceac6`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401ceae5`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401ceba7`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401ceae5`
- `ntoskrnl!MmUnmapViewInSessionSpace` at `0x1401ceba7`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cea53`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ceb04`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cebc6`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cea53`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ceb04`
- `ntoskrnl!ObfDereferenceObject` at `0x1401cebc6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce718`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce73d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce75e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce783`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce7fd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce822`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cebd2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cec06`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cecc4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cece9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce718`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce73d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce75e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce783`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce7fd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce822`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cebd2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cec06`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cecc4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cece9`
- `WIN32K!W32GetSessionState` at `0x1401ce84c`
- `WIN32K!W32GetSessionState` at `0x1401cedbc`
- `WIN32K!W32GetSessionState` at `0x1401cedd6`
- `WIN32K!W32GetSessionState` at `0x1401ce84c`
- `WIN32K!W32GetSessionState` at `0x1401cedbc`
- `WIN32K!W32GetSessionState` at `0x1401cedd6`
- `WIN32K!W32UnregisterSessionProcess` at `0x1401ce8ac`
- `WIN32K!W32UnregisterSessionProcess` at `0x1401ce8ac`
- `WIN32K!W32GetDCompSessionState` at `0x1401ce7a4`
- `WIN32K!W32GetDCompSessionState` at `0x1401ce7e3`
- `WIN32K!W32GetDCompSessionState` at `0x1401ce7a4`
- `WIN32K!W32GetDCompSessionState` at `0x1401ce7e3`
- `WIN32K!W32GetUserSessionState` at `0x1401ce6c6`
- `WIN32K!W32GetUserSessionState` at `0x1401ce87f`
- `WIN32K!W32GetUserSessionState` at `0x1401ce898`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8b8`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8d1`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8ed`
- `WIN32K!W32GetUserSessionState` at `0x1401ce904`
- `WIN32K!W32GetUserSessionState` at `0x1401ce92e`
- `WIN32K!W32GetUserSessionState` at `0x1401ce94a`
- `WIN32K!W32GetUserSessionState` at `0x1401ce97c`
- `WIN32K!W32GetUserSessionState` at `0x1401ce990`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9a5`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9b8`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9d3`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9e8`
- `WIN32K!W32GetUserSessionState` at `0x1401cea00`
- `WIN32K!W32GetUserSessionState` at `0x1401cea18`
- `WIN32K!W32GetUserSessionState` at `0x1401cea2b`
- `WIN32K!W32GetUserSessionState` at `0x1401cea40`
- `WIN32K!W32GetUserSessionState` at `0x1401cea5f`
- `WIN32K!W32GetUserSessionState` at `0x1401cea72`
- `WIN32K!W32GetUserSessionState` at `0x1401cea8b`
- `WIN32K!W32GetUserSessionState` at `0x1401cea9e`
- `WIN32K!W32GetUserSessionState` at `0x1401ceab3`
- `WIN32K!W32GetUserSessionState` at `0x1401cead2`
- `WIN32K!W32GetUserSessionState` at `0x1401ceaf1`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb10`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb25`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb3d`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb52`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb6a`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb7f`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb94`
- `WIN32K!W32GetUserSessionState` at `0x1401cebb3`
- `WIN32K!W32GetUserSessionState` at `0x1401cebf7`
- `WIN32K!W32GetUserSessionState` at `0x1401cec2e`
- `WIN32K!W32GetUserSessionState` at `0x1401cec42`
- `WIN32K!W32GetUserSessionState` at `0x1401cec5d`
- `WIN32K!W32GetUserSessionState` at `0x1401cec7f`
- `WIN32K!W32GetUserSessionState` at `0x1401cec94`
- `WIN32K!W32GetUserSessionState` at `0x1401cecb1`
- `WIN32K!W32GetUserSessionState` at `0x1401ced19`
- `WIN32K!W32GetUserSessionState` at `0x1401ced2e`
- `WIN32K!W32GetUserSessionState` at `0x1401ced4f`
- `WIN32K!W32GetUserSessionState` at `0x1401ced67`
- `WIN32K!W32GetUserSessionState` at `0x1401ce6c6`
- `WIN32K!W32GetUserSessionState` at `0x1401ce87f`
- `WIN32K!W32GetUserSessionState` at `0x1401ce898`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8b8`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8d1`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8ed`
- `WIN32K!W32GetUserSessionState` at `0x1401ce904`
- `WIN32K!W32GetUserSessionState` at `0x1401ce92e`
- `WIN32K!W32GetUserSessionState` at `0x1401ce94a`
- `WIN32K!W32GetUserSessionState` at `0x1401ce97c`
- `WIN32K!W32GetUserSessionState` at `0x1401ce990`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9a5`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9b8`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9d3`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9e8`
- `WIN32K!W32GetUserSessionState` at `0x1401cea00`
- `WIN32K!W32GetUserSessionState` at `0x1401cea18`
- `WIN32K!W32GetUserSessionState` at `0x1401cea2b`
- `WIN32K!W32GetUserSessionState` at `0x1401cea40`
- `WIN32K!W32GetUserSessionState` at `0x1401cea5f`
- `WIN32K!W32GetUserSessionState` at `0x1401cea72`
- `WIN32K!W32GetUserSessionState` at `0x1401cea8b`
- `WIN32K!W32GetUserSessionState` at `0x1401cea9e`
- `WIN32K!W32GetUserSessionState` at `0x1401ceab3`
- `WIN32K!W32GetUserSessionState` at `0x1401cead2`
- `WIN32K!W32GetUserSessionState` at `0x1401ceaf1`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb10`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb25`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb3d`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb52`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb6a`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb7f`
- `WIN32K!W32GetUserSessionState` at `0x1401ceb94`
- `WIN32K!W32GetUserSessionState` at `0x1401cebb3`
- `WIN32K!W32GetUserSessionState` at `0x1401cebf7`
- `WIN32K!W32GetUserSessionState` at `0x1401cec2e`
- `WIN32K!W32GetUserSessionState` at `0x1401cec42`
- `WIN32K!W32GetUserSessionState` at `0x1401cec5d`
- `WIN32K!W32GetUserSessionState` at `0x1401cec7f`
- `WIN32K!W32GetUserSessionState` at `0x1401cec94`
- `WIN32K!W32GetUserSessionState` at `0x1401cecb1`
- `WIN32K!W32GetUserSessionState` at `0x1401ced19`
- `WIN32K!W32GetUserSessionState` at `0x1401ced2e`
- `WIN32K!W32GetUserSessionState` at `0x1401ced4f`
- `WIN32K!W32GetUserSessionState` at `0x1401ced67`

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
      (__int64)WPP_5f70da56b76d32e0a0cd6b880e011bcd_Traceguids);
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
0x1401ce670  mov     [rsp+arg_0], rbx
0x1401ce675  mov     [rsp+arg_8], rsi
0x1401ce67a  push    rdi
0x1401ce67b  sub     rsp, 100h
0x1401ce682  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ce689  lea     rax, WPP_GLOBAL_Control
0x1401ce690  xor     esi, esi
0x1401ce692  cmp     rcx, rax
0x1401ce695  jz      short loc_1401CE6A8
0x1401ce697  test    dword ptr [rcx+2Ch], 2000h
0x1401ce69e  jz      short loc_1401CE6A8
0x1401ce6a0  cmp     byte ptr [rcx+29h], 4
0x1401ce6a4  mov     bl, 1
0x1401ce6a6  jnb     short loc_1401CE6AB
0x1401ce6a8  mov     bl, sil
0x1401ce6ab  lea     rax, WPP_RECORDER_INITIALIZED
0x1401ce6b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401ce6b9  setnz   dil
0x1401ce6bd  test    bl, bl
0x1401ce6bf  jnz     short loc_1401CE6C6
0x1401ce6c1  test    dil, dil
0x1401ce6c4  jz      short loc_1401CE70E
0x1401ce6c6  call    cs:__imp_W32GetUserSessionState
0x1401ce6cd  nop     dword ptr [rax+rax+00h]
0x1401ce6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ce6d9  mov     r8b, dil
0x1401ce6dc  mov     dl, bl
0x1401ce6de  mov     r9, [rax+10E10h]
0x1401ce6e5  lea     rax, WPP_5f70da56b76d32e0a0cd6b880e011bcd_Traceguids
0x1401ce6ec  mov     rcx, [rcx+18h]
0x1401ce6f0  mov     [rsp+108h+var_D0], rax
0x1401ce6f5  mov     [rsp+108h+var_D8], 0Bh
0x1401ce6fc  mov     [rsp+108h+var_E0], 0Eh
0x1401ce704  mov     [rsp+108h+var_E8], 4
0x1401ce709  call    WPP_RECORDER_AND_TRACE_SF_
0x1401ce70e  lea     rcx, [rsp+108h+var_C8]; this
0x1401ce713  call    ??0CTempW32ThreadNonPaged@@QEAA@XZ; CTempW32ThreadNonPaged::CTempW32ThreadNonPaged(void)
0x1401ce718  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce71f  nop     dword ptr [rax+rax+00h]
0x1401ce724  mov     rcx, [rax+30h]
0x1401ce728  mov     rax, [rcx+0F08h]
0x1401ce72f  test    rax, rax
0x1401ce732  jz      short loc_1401CE75E
0x1401ce734  call    _guard_dispatch_icall
0x1401ce739  test    eax, eax
0x1401ce73b  js      short loc_1401CE75E
0x1401ce73d  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce744  nop     dword ptr [rax+rax+00h]
0x1401ce749  mov     rcx, [rax+30h]
0x1401ce74d  mov     rax, [rcx+0F10h]
0x1401ce754  test    rax, rax
0x1401ce757  jz      short loc_1401CE75E
0x1401ce759  call    _guard_dispatch_icall
0x1401ce75e  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce765  nop     dword ptr [rax+rax+00h]
0x1401ce76a  mov     rcx, [rax+30h]
0x1401ce76e  mov     rax, [rcx+0F8h]
0x1401ce775  test    rax, rax
0x1401ce778  jz      short loc_1401CE7A4
0x1401ce77a  call    _guard_dispatch_icall
0x1401ce77f  test    eax, eax
0x1401ce781  js      short loc_1401CE7A4
0x1401ce783  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce78a  nop     dword ptr [rax+rax+00h]
0x1401ce78f  mov     rcx, [rax+30h]
0x1401ce793  mov     rax, [rcx+100h]
0x1401ce79a  test    rax, rax
0x1401ce79d  jz      short loc_1401CE7A4
0x1401ce79f  call    _guard_dispatch_icall
0x1401ce7a4  call    cs:__imp_W32GetDCompSessionState
0x1401ce7ab  nop     dword ptr [rax+rax+00h]
0x1401ce7b0  mov     rbx, rax
0x1401ce7b3  mov     rcx, [rax+10h]; Buffer
0x1401ce7b7  test    rcx, rcx
0x1401ce7ba  jz      short loc_1401CE7C1
0x1401ce7bc  call    ??_GCConnection@DirectComposition@@AEAAPEAXI@Z; DirectComposition::CConnection::`scalar deleting destructor'(uint)
0x1401ce7c1  mov     rcx, [rbx+20h]; Resource
0x1401ce7c5  test    rcx, rcx
0x1401ce7c8  jz      short loc_1401CE7E3
0x1401ce7ca  call    cs:__imp_ExDeleteResourceLite
0x1401ce7d1  nop     dword ptr [rax+rax+00h]
0x1401ce7d6  mov     rcx, [rbx+20h]; Buffer
0x1401ce7da  call    GreDeleteFastMutex
0x1401ce7df  mov     [rbx+20h], rsi
0x1401ce7e3  call    cs:__imp_W32GetDCompSessionState
0x1401ce7ea  nop     dword ptr [rax+rax+00h]
0x1401ce7ef  mov     rcx, [rax+18h]; Buffer
0x1401ce7f3  test    rcx, rcx
0x1401ce7f6  jz      short loc_1401CE7FD
0x1401ce7f8  call    ??_GCSynchronizationManager@DirectComposition@@IEAAPEAXI@Z; DirectComposition::CSynchronizationManager::`scalar deleting destructor'(uint)
0x1401ce7fd  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce804  nop     dword ptr [rax+rax+00h]
0x1401ce809  mov     rcx, [rax+30h]
0x1401ce80d  mov     rax, [rcx+118h]
0x1401ce814  test    rax, rax
0x1401ce817  jz      short loc_1401CE843
0x1401ce819  call    _guard_dispatch_icall
0x1401ce81e  test    eax, eax
0x1401ce820  js      short loc_1401CE843
0x1401ce822  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce829  nop     dword ptr [rax+rax+00h]
0x1401ce82e  mov     rcx, [rax+30h]
0x1401ce832  mov     rax, [rcx+120h]
0x1401ce839  test    rax, rax
0x1401ce83c  jz      short loc_1401CE843
0x1401ce83e  call    _guard_dispatch_icall
0x1401ce843  call    ?IsSessionGlobalsAreaAllocated@Base@Gre@@YA_NXZ; Gre::Base::IsSessionGlobalsAreaAllocated(void)
0x1401ce848  test    al, al
0x1401ce84a  jz      short loc_1401CE87F
0x1401ce84c  call    cs:__imp_W32GetSessionState
0x1401ce853  nop     dword ptr [rax+rax+00h]
0x1401ce858  mov     rdi, [rax+58h]
0x1401ce85c  mov     rbx, [rdi+0E90h]
0x1401ce863  test    rbx, rbx
0x1401ce866  jz      short loc_1401CE878
0x1401ce868  mov     rcx, rbx; this
0x1401ce86b  call    ??1COPM@@QEAA@XZ; COPM::~COPM(void)
0x1401ce870  mov     rcx, rbx; this
0x1401ce873  call    ?OPMFreeMemory@OPM@@YAXPEAX@Z; OPM::OPMFreeMemory(void *)
0x1401ce878  mov     [rdi+0E90h], rsi
0x1401ce87f  call    cs:__imp_W32GetUserSessionState
0x1401ce886  nop     dword ptr [rax+rax+00h]
0x1401ce88b  bts     dword ptr [rax+10D38h], 7
0x1401ce893  call    MultiUserNtGreCleanup
0x1401ce898  call    cs:__imp_W32GetUserSessionState
0x1401ce89f  nop     dword ptr [rax+rax+00h]
0x1401ce8a4  bts     dword ptr [rax+10D38h], 8
0x1401ce8ac  call    cs:__imp_W32UnregisterSessionProcess
0x1401ce8b3  nop     dword ptr [rax+rax+00h]
0x1401ce8b8  call    cs:__imp_W32GetUserSessionState
0x1401ce8bf  nop     dword ptr [rax+rax+00h]
0x1401ce8c4  cmp     [rax+0DDA8h], rsi
0x1401ce8cb  jz      loc_1401CE968
0x1401ce8d1  call    cs:__imp_W32GetUserSessionState
0x1401ce8d8  nop     dword ptr [rax+rax+00h]
0x1401ce8dd  mov     rcx, [rax+0DDA8h]
0x1401ce8e4  add     rcx, 18h
0x1401ce8e8  cmp     [rcx], rcx
0x1401ce8eb  jz      short loc_1401CE968
0x1401ce8ed  call    cs:__imp_W32GetUserSessionState
0x1401ce8f4  nop     dword ptr [rax+rax+00h]
0x1401ce8f9  mov     rcx, [rax+0DDA8h]
0x1401ce900  mov     rdi, [rcx+18h]
0x1401ce904  call    cs:__imp_W32GetUserSessionState
0x1401ce90b  nop     dword ptr [rax+rax+00h]
0x1401ce910  mov     rdx, [rax+0DDA8h]
0x1401ce917  add     rdx, 18h
0x1401ce91b  cmp     rdi, rdx
0x1401ce91e  jz      short loc_1401CE94A
0x1401ce920  mov     rbx, [rdi]
0x1401ce923  mov     rcx, rdi; Buffer
0x1401ce926  call    GreDeleteFastMutex
0x1401ce92b  mov     rdi, rbx
0x1401ce92e  call    cs:__imp_W32GetUserSessionState
0x1401ce935  nop     dword ptr [rax+rax+00h]
0x1401ce93a  mov     rcx, [rax+0DDA8h]
0x1401ce941  add     rcx, 18h
0x1401ce945  cmp     rbx, rcx
0x1401ce948  jnz     short loc_1401CE920
0x1401ce94a  call    cs:__imp_W32GetUserSessionState
0x1401ce951  nop     dword ptr [rax+rax+00h]
0x1401ce956  mov     rcx, [rax+0DDA8h]
0x1401ce95d  add     rcx, 18h
0x1401ce961  mov     [rcx+8], rcx
0x1401ce965  mov     [rcx], rcx
0x1401ce968  call    InputUnInitialize
0x1401ce96d  call    ?Win32kNtUserCleanup@@YAHXZ; Win32kNtUserCleanup(void)
0x1401ce972  call    ?DestroyHandleTableObjects@@YAXXZ; DestroyHandleTableObjects(void)
0x1401ce977  call    ?CleanupDomainLocks@@YAXXZ; CleanupDomainLocks(void)
0x1401ce97c  call    cs:__imp_W32GetUserSessionState
0x1401ce983  nop     dword ptr [rax+rax+00h]
0x1401ce988  bts     dword ptr [rax+10D38h], 9
0x1401ce990  call    cs:__imp_W32GetUserSessionState
0x1401ce997  nop     dword ptr [rax+rax+00h]
0x1401ce99c  cmp     [rax+0A590h], rsi
0x1401ce9a3  jz      short loc_1401CE9D3
0x1401ce9a5  call    cs:__imp_W32GetUserSessionState
0x1401ce9ac  nop     dword ptr [rax+rax+00h]
0x1401ce9b1  mov     rbx, [rax+0A590h]
0x1401ce9b8  call    cs:__imp_W32GetUserSessionState
0x1401ce9bf  nop     dword ptr [rax+rax+00h]
0x1401ce9c4  mov     rdx, rbx; void *
0x1401ce9c7  lea     rcx, [rax+11950h]; this
0x1401ce9ce  call    ?FreePagedLookasideList@CLeakTrackingAllocator@NSInstrumentation@@QEAAXPEAX@Z; NSInstrumentation::CLeakTrackingAllocator::FreePagedLookasideList(void *)
0x1401ce9d3  call    cs:__imp_W32GetUserSessionState
0x1401ce9da  nop     dword ptr [rax+rax+00h]
0x1401ce9df  cmp     [rax+4CB0h], rsi
0x1401ce9e6  jz      short loc_1401CEA2B
0x1401ce9e8  call    cs:__imp_W32GetUserSessionState
0x1401ce9ef  nop     dword ptr [rax+rax+00h]
0x1401ce9f4  mov     rcx, [rax+4CB0h]; this
0x1401ce9fb  call    ?Destroy@UserTypeIsolationAllocators@@QEAAXXZ; UserTypeIsolationAllocators::Destroy(void)
0x1401cea00  call    cs:__imp_W32GetUserSessionState
0x1401cea07  nop     dword ptr [rax+rax+00h]
0x1401cea0c  mov     rcx, [rax+4CB0h]; Buffer
0x1401cea13  call    GreDeleteFastMutex
0x1401cea18  call    cs:__imp_W32GetUserSessionState
0x1401cea1f  nop     dword ptr [rax+rax+00h]
0x1401cea24  mov     [rax+4CB0h], rsi
0x1401cea2b  call    cs:__imp_W32GetUserSessionState
0x1401cea32  nop     dword ptr [rax+rax+00h]
0x1401cea37  cmp     [rax+11668h], rsi
0x1401cea3e  jz      short loc_1401CEA72
0x1401cea40  call    cs:__imp_W32GetUserSessionState
0x1401cea47  nop     dword ptr [rax+rax+00h]
0x1401cea4c  mov     rcx, [rax+11668h]; Object
0x1401cea53  call    cs:__imp_ObfDereferenceObject
0x1401cea5a  nop     dword ptr [rax+rax+00h]
0x1401cea5f  call    cs:__imp_W32GetUserSessionState
0x1401cea66  nop     dword ptr [rax+rax+00h]
0x1401cea6b  mov     [rax+11668h], rsi
0x1401cea72  call    cs:__imp_W32GetUserSessionState
0x1401cea79  nop     dword ptr [rax+rax+00h]
0x1401cea7e  cmp     [rax+4CD8h], rsi
0x1401cea85  jz      loc_1401CEB10
0x1401cea8b  call    cs:__imp_W32GetUserSessionState
0x1401cea92  nop     dword ptr [rax+rax+00h]
0x1401cea97  mov     [rax+4CF8h], rsi
0x1401cea9e  call    cs:__imp_W32GetUserSessionState
0x1401ceaa5  nop     dword ptr [rax+rax+00h]
0x1401ceaaa  cmp     [rax+4CE8h], rsi
0x1401ceab1  jz      short loc_1401CEAF1
0x1401ceab3  call    cs:__imp_W32GetUserSessionState
0x1401ceaba  nop     dword ptr [rax+rax+00h]
0x1401ceabf  mov     rcx, [rax+4CF0h]; HeapHandle
0x1401ceac6  call    cs:__imp_RtlDestroyHeap
0x1401ceacd  nop     dword ptr [rax+rax+00h]
0x1401cead2  call    cs:__imp_W32GetUserSessionState
0x1401cead9  nop     dword ptr [rax+rax+00h]
0x1401ceade  mov     rcx, [rax+4CE8h]; MappedBase
0x1401ceae5  call    cs:__imp_MmUnmapViewInSessionSpace
0x1401ceaec  nop     dword ptr [rax+rax+00h]
0x1401ceaf1  call    cs:__imp_W32GetUserSessionState
0x1401ceaf8  nop     dword ptr [rax+rax+00h]
0x1401ceafd  mov     rcx, [rax+4CD8h]; Object
0x1401ceb04  call    cs:__imp_ObfDereferenceObject
0x1401ceb0b  nop     dword ptr [rax+rax+00h]
0x1401ceb10  call    cs:__imp_W32GetUserSessionState
0x1401ceb17  nop     dword ptr [rax+rax+00h]
0x1401ceb1c  cmp     [rax+0DDA8h], rsi
0x1401ceb23  jz      short loc_1401CEB3D
0x1401ceb25  call    cs:__imp_W32GetUserSessionState
0x1401ceb2c  nop     dword ptr [rax+rax+00h]
0x1401ceb31  mov     rcx, [rax+0DDA8h]; Buffer
0x1401ceb38  call    GreDeleteFastMutex
0x1401ceb3d  call    cs:__imp_W32GetUserSessionState
0x1401ceb44  nop     dword ptr [rax+rax+00h]
0x1401ceb49  cmp     [rax+0F4E0h], rsi
0x1401ceb50  jz      short loc_1401CEB6A
0x1401ceb52  call    cs:__imp_W32GetUserSessionState
0x1401ceb59  nop     dword ptr [rax+rax+00h]
0x1401ceb5e  mov     rcx, [rax+0F4E0h]; Buffer
0x1401ceb65  call    GreDeleteFastMutex
0x1401ceb6a  call    cs:__imp_W32GetUserSessionState
0x1401ceb71  nop     dword ptr [rax+rax+00h]
0x1401ceb76  cmp     [rax+4CE0h], rsi
0x1401ceb7d  jz      short loc_1401CEBD2
0x1401ceb7f  call    cs:__imp_W32GetUserSessionState
0x1401ceb86  nop     dword ptr [rax+rax+00h]
0x1401ceb8b  cmp     [rax+4CD0h], rsi
0x1401ceb92  jz      short loc_1401CEBB3
0x1401ceb94  call    cs:__imp_W32GetUserSessionState
0x1401ceb9b  nop     dword ptr [rax+rax+00h]
0x1401ceba0  mov     rcx, [rax+4CD0h]; MappedBase
0x1401ceba7  call    cs:__imp_MmUnmapViewInSessionSpace
0x1401cebae  nop     dword ptr [rax+rax+00h]
0x1401cebb3  call    cs:__imp_W32GetUserSessionState
0x1401cebba  nop     dword ptr [rax+rax+00h]
0x1401cebbf  mov     rcx, [rax+4CE0h]; Object
0x1401cebc6  call    cs:__imp_ObfDereferenceObject
0x1401cebcd  nop     dword ptr [rax+rax+00h]
0x1401cebd2  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cebd9  nop     dword ptr [rax+rax+00h]
0x1401cebde  mov     rcx, [rax+30h]
0x1401cebe2  mov     rax, [rcx+128h]
0x1401cebe9  test    rax, rax
0x1401cebec  jz      short loc_1401CEC2E
0x1401cebee  call    _guard_dispatch_icall
0x1401cebf3  test    eax, eax
0x1401cebf5  js      short loc_1401CEC2E
0x1401cebf7  call    cs:__imp_W32GetUserSessionState
0x1401cebfe  nop     dword ptr [rax+rax+00h]
0x1401cec03  mov     rbx, rax
0x1401cec06  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cec0d  nop     dword ptr [rax+rax+00h]
0x1401cec12  mov     rcx, [rax+30h]
0x1401cec16  mov     rax, [rcx+130h]
0x1401cec1d  test    rax, rax
0x1401cec20  jz      short loc_1401CEC2E
0x1401cec22  lea     rcx, [rbx+10110h]
0x1401cec29  call    _guard_dispatch_icall
0x1401cec2e  call    cs:__imp_W32GetUserSessionState
0x1401cec35  nop     dword ptr [rax+rax+00h]
0x1401cec3a  cmp     [rax+110E0h], esi
0x1401cec40  jz      short loc_1401CEC7F
0x1401cec42  call    cs:__imp_W32GetUserSessionState
0x1401cec49  nop     dword ptr [rax+rax+00h]
0x1401cec4e  mov     rbx, rax
0x1401cec51  mov     rdi, [rax+4BD8h]
0x1401cec58  test    rdi, rdi
  ... truncated ...
```
