# GrepUpdateSpriteImpl(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *,tagMINIWINDOWINFO *,int,int,ulong)

- ea: `0x140017000`
- end: `0x140017ece`
- name: `?GrepUpdateSpriteImpl@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@PEAUtagMINIWINDOWINFO@@HHK@Z`
- size: `3790`
- prototype: `__int64 __usercall@<rax>(HDEV@<rcx>, HWND@<rdx>, void *@<r8>, struct OPTAPIDCOBJ *@<r9>, struct tagPOINT *, struct tagSIZE *, struct OPTAPIDCOBJ *, struct tagPOINT *, unsigned int, struct _BLENDFUNCTION *, unsigned int, struct tagRECT *, struct tagMINIWINDOWINFO *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x140016e74`

## callees

- `0x140015178`
- `0x1400151f0`
- `0x140015410`
- `0x140015830`
- `0x140015d84`
- `0x140016248`
- `0x1400164f8`
- `0x140016bb4`
- `0x140016de4`
- `0x140017000`
- `0x140019070`
- `0x1400190d8`
- `0x14005b820`
- `0x14005e498`
- `0x14005e544`
- `0x140062138`
- `0x140068674`
- `0x140069870`
- `0x14009b5c8`
- `0x14011b49c`
- `0x14011c5ac`
- `0x140120e28`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTable` at `0x140017345`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x140017345`
- `ntoskrnl!LpcRequestPort` at `0x1400177a0`
- `ntoskrnl!LpcRequestPort` at `0x140017ad1`
- `ntoskrnl!LpcRequestPort` at `0x1400177a0`
- `ntoskrnl!LpcRequestPort` at `0x140017ad1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001722b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001722b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400177af`
- `ntoskrnl!ObfDereferenceObject` at `0x140017ae0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400177af`
- `ntoskrnl!ObfDereferenceObject` at `0x140017ae0`
- `win32kbase!UserReferenceDwmApiPort` at `0x14001773f`
- `win32kbase!UserReferenceDwmApiPort` at `0x140017947`
- `win32kbase!UserReferenceDwmApiPort` at `0x14001773f`
- `win32kbase!UserReferenceDwmApiPort` at `0x140017947`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400170c7`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400170e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14001717a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140017264`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400172dc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14001730b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140017377`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14001742d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14001780f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400170c7`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400170e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14001717a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140017264`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400172dc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14001730b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140017377`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14001742d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14001780f`
- `win32kbase!HmgShareLock` at `0x14001738f`
- `win32kbase!HmgShareLock` at `0x14001738f`
- `win32kbase!PopThreadGuardedObject` at `0x1400176f5`
- `win32kbase!PopThreadGuardedObject` at `0x1400176f5`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140017821`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140017821`
- `win32kbase!PushThreadGuardedObject` at `0x140017409`
- `win32kbase!PushThreadGuardedObject` at `0x140017409`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140017197`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140017197`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x1400172cb`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x1400172cb`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400171bf`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400171bf`
- `win32kbase!GreReleasePushLockExclusive` at `0x140017362`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400176dc`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400177e5`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400177fa`
- `win32kbase!GreReleasePushLockExclusive` at `0x140017362`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400176dc`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400177e5`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400177fa`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14001732e`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1400173cd`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140017468`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1400177ca`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14001732e`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1400173cd`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140017468`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1400177ca`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140017297`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140017832`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140017297`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140017832`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1400171af`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1400171af`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreExclusive` at `0x140017284`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreExclusive` at `0x140017284`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140017445`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140017445`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x140017c6c`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x140017c6c`
- `win32kbase!?GrepQueueApc@@YA_NP6AXPEAX00@Z00@Z` at `0x140017ca1`
- `win32kbase!?GrepQueueApc@@YA_NP6AXPEAX00@Z00@Z` at `0x140017ca1`
- `win32kbase!?GetFirstLSurf@SURFACE@@QEAAPEAVSFMLOGICALSURFACE@@XZ` at `0x140017ea9`
- `win32kbase!?GetFirstLSurf@SURFACE@@QEAAPEAVSFMLOGICALSURFACE@@XZ` at `0x140017ea9`
- `win32kbase!pProcessDfbSurfaces` at `0x140017e91`
- `win32kbase!pProcessDfbSurfaces` at `0x140017e91`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAX_N@Z` at `0x14001720f`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAX_N@Z` at `0x14001720f`
- `win32kbase!EtwUpdateEvent` at `0x14001778d`
- `win32kbase!EtwUpdateEvent` at `0x140017abb`
- `win32kbase!EtwUpdateEvent` at `0x14001778d`
- `win32kbase!EtwUpdateEvent` at `0x140017abb`
- `WIN32K!W32GetSessionState` at `0x140017a9b`
- `WIN32K!W32GetSessionState` at `0x140017a9b`
- `WIN32K!W32GetUserSessionState` at `0x14001768b`
- `WIN32K!W32GetUserSessionState` at `0x14001768b`

## pseudocode

```c
__int64 __fastcall GrepUpdateSpriteImpl(
        HDEV a1,
        HWND a2,
        void *a3,
        struct OPTAPIDCOBJ *a4,
        struct tagPOINT *a5,
        struct tagSIZE *a6,
        struct OPTAPIDCOBJ *a7,
        struct tagPOINT *a8,
        unsigned int a9,
        struct _BLENDFUNCTION *a10,
        unsigned int a11,
        struct tagRECT *a12,
        struct tagMINIWINDOWINFO *a13,
        int a14,
        int a15,
        unsigned int a16)
{
  HDEV v16; // rbx
  struct _BLENDFUNCTION *v17; // r15
  unsigned int v18; // esi
  struct tagMINIWINDOWINFO *v19; // r13
  Gre::Base *v20; // rcx
  unsigned int v21; // r12d
  Gre::Base *v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // r14d
  Gre::Base *v25; // rcx
  __int64 v26; // rbx
  __int64 v28; // rcx
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v30; // rcx
  Gre::Base *v31; // rcx
  __int64 v32; // rbx
  HSEMAPHORE v33; // rcx
  Gre::Base *v34; // rcx
  Gre::Base *v35; // rcx
  void *v36; // rdi
  struct Gre::Base::SESSION_GLOBALS *v37; // rsi
  struct W32_PUSH_LOCK *v38; // rbx
  _QWORD *v39; // rax
  struct Gre::Base::SESSION_GLOBALS *v40; // rax
  __int64 v41; // r8
  __int64 v42; // rax
  struct W32_PUSH_LOCK *v43; // rcx
  __int64 v44; // rbx
  int v45; // r15d
  __int64 *v46; // rsi
  struct SFMLOGICALSURFACE *FirstLSurf; // rdi
  __int64 v48; // rdx
  Gre::Base *v49; // rcx
  struct tagPOINT *v50; // r9
  __int64 v51; // r14
  struct Gre::Base::SESSION_GLOBALS *v52; // rax
  __int64 v53; // r8
  int *v54; // r14
  unsigned __int64 v55; // rcx
  LONG y; // r8d
  LONG x; // ecx
  int v58; // eax
  __int64 v59; // r8
  LONG v60; // edx
  LONG v61; // ecx
  int v62; // eax
  __int64 UserSessionState; // rax
  __int64 v64; // rax
  __int64 v65; // r15
  unsigned int v66; // esi
  void *v67; // r13
  void *v68; // r14
  struct Gre::Base::SESSION_GLOBALS *v69; // rax
  int v70; // eax
  _DWORD *v71; // rcx
  int v72; // r15d
  int v73; // r13d
  void *v74; // rsi
  __int64 v75; // r9
  __int64 v76; // r8
  int v77; // eax
  __int64 v78; // rdx
  __int64 v79; // rcx
  int v80; // eax
  __int128 v81; // xmm0
  __int128 v82; // xmm1
  __int128 v83; // xmm0
  __int128 v84; // xmm1
  __int128 v85; // xmm0
  __int128 v86; // xmm1
  __int128 v87; // xmm0
  __int128 v88; // xmm1
  __int64 v89; // rax
  __int64 SessionState; // rax
  bool v91; // dl
  struct tagSIZE *v92; // rsi
  OPTAPIDCOBJ *v93; // r14
  bool v94; // al
  __int64 v95; // rax
  DC *v96; // rcx
  __int64 v97; // rax
  __int64 v98; // r14
  int v99; // eax
  void *v100; // rdx
  int updated; // eax
  __int64 v102; // rdx
  __int64 v103; // rax
  __int64 v104; // rcx
  unsigned int v105; // eax
  struct tagRECT v106; // xmm0
  SURFACE *v107; // rax
  char v108; // [rsp+60h] [rbp-A0h]
  int v109; // [rsp+64h] [rbp-9Ch]
  int v110; // [rsp+68h] [rbp-98h] BYREF
  int v111; // [rsp+6Ch] [rbp-94h]
  unsigned int v112; // [rsp+70h] [rbp-90h] BYREF
  struct SFMLOGICALSURFACE *v113; // [rsp+78h] [rbp-88h] BYREF
  int *v114; // [rsp+80h] [rbp-80h]
  int v115; // [rsp+88h] [rbp-78h]
  HDEV v116; // [rsp+90h] [rbp-70h]
  struct tagRECT *v117; // [rsp+98h] [rbp-68h]
  struct tagSIZE *v118; // [rsp+A0h] [rbp-60h]
  struct tagPOINT *v119; // [rsp+A8h] [rbp-58h]
  struct Gre::Base::SESSION_GLOBALS *v120; // [rsp+B0h] [rbp-50h]
  int v121; // [rsp+B8h] [rbp-48h]
  int v122; // [rsp+BCh] [rbp-44h]
  unsigned int v123; // [rsp+C0h] [rbp-40h]
  struct tagPOINT *v124; // [rsp+C8h] [rbp-38h]
  OPTAPIDCOBJ *v125; // [rsp+D0h] [rbp-30h]
  void *v126; // [rsp+D8h] [rbp-28h]
  struct _RECTL v127; // [rsp+E0h] [rbp-20h] BYREF
  struct tagMINIWINDOWINFO *v128; // [rsp+F0h] [rbp-10h]
  HWND v129; // [rsp+F8h] [rbp-8h]
  __int128 Buffer; // [rsp+100h] [rbp+0h] BYREF
  HDEV v131; // [rsp+110h] [rbp+10h] BYREF
  int v132; // [rsp+118h] [rbp+18h]
  HSEMAPHORE v133; // [rsp+120h] [rbp+20h] BYREF
  bool v134; // [rsp+128h] [rbp+28h]
  _OWORD v135[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v136; // [rsp+150h] [rbp+50h]
  int v137; // [rsp+158h] [rbp+58h]
  unsigned int v138; // [rsp+15Ch] [rbp+5Ch]
  void *v139; // [rsp+160h] [rbp+60h]
  __int64 v140; // [rsp+168h] [rbp+68h]
  __int64 v141; // [rsp+170h] [rbp+70h]
  _BYTE v142[8]; // [rsp+178h] [rbp+78h] BYREF
  struct OPTAPIDCOBJ *v143; // [rsp+180h] [rbp+80h]
  DC *v144; // [rsp+190h] [rbp+90h] BYREF
  int v145; // [rsp+198h] [rbp+98h]
  __int64 v146; // [rsp+1A0h] [rbp+A0h]
  __int64 v147; // [rsp+1A8h] [rbp+A8h]
  _BYTE v148[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v149[48]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v150[2]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v151; // [rsp+220h] [rbp+120h]
  __int64 v152; // [rsp+228h] [rbp+128h]
  __int64 v153; // [rsp+230h] [rbp+130h]
  int v154; // [rsp+290h] [rbp+190h] BYREF
  __int16 v155; // [rsp+294h] [rbp+194h]
  __int128 v156; // [rsp+2B8h] [rbp+1B8h]
  _BYTE v157[160]; // [rsp+2C8h] [rbp+1C8h]
  _BYTE v158[20]; // [rsp+368h] [rbp+268h]
  struct tagRECT v159; // [rsp+380h] [rbp+280h] BYREF

  v16 = a1;
  v17 = a10;
  v18 = a11 & 0x200000;
  v19 = a13;
  v118 = a6;
  v124 = a8;
  v119 = a5;
  v125 = a7;
  v126 = a3;
  v129 = a2;
  v116 = a1;
  v117 = a12;
  v143 = a4;
  v114 = (int *)a10;
  v128 = a13;
  v123 = a11 & 0x200000;
  memset_0(v150, 0, 0x88u);
  v110 = 0;
  v112 = 0;
  v21 = a11 & 0xFFDFFFFF;
  v120 = Gre::Base::Globals(v20);
  if ( !a14 || !*((_QWORD *)Gre::Base::Globals(v22) + 28) )
    goto LABEL_3;
  v24 = 0;
  v115 = 1;
  NEEDGRELOCK::vLock((NEEDGRELOCK *)v142, v18 == 0);
  v131 = v16;
  v132 = 0;
  if ( !v18 )
  {
    CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread(v28);
    v30 = CurrentThreadWin32Thread ? *CurrentThreadWin32Thread : 0LL;
    v31 = (Gre::Base *)((v30 + 8) & -(__int64)(v30 != 0));
    if ( !v31 || !*((_DWORD *)v31 + 85) && !*((_DWORD *)v31 + 86) )
    {
      v32 = *(_QWORD *)Gre::Base::Globals(v31);
      EtwTraceGreLockAcquireSemaphoreExclusive(L"Sprite", v32 + 1040, 0);
      GreAcquireSemaphoreInternal((HSEMAPHORE)(v32 + 1040));
      GrepAcquireLockValidate<6>();
      v132 = 1;
    }
  }
  v33 = (HSEMAPHORE)(*(_QWORD *)v120 + 520LL);
  v133 = v33;
  v134 = v18 != 0;
  if ( v18 )
    GreAcquireSemaphoreSharedInternal(v33);
  else
    GreAcquireSemaphoreInternal(v33);
  GrepAcquireLockValidate<7>();
  if ( !*((_QWORD *)Gre::Base::Globals(v34) + 28) )
    goto LABEL_6;
  if ( v129 )
  {
    v36 = 0;
    Buffer = 0;
    *(_QWORD *)&Buffer = v129;
    v37 = Gre::Base::Globals(v35);
    v38 = (struct W32_PUSH_LOCK *)(*((_QWORD *)v37 + 28) + 72LL);
    if ( *((_QWORD *)v37 + 28) != -72 )
      GreAcquirePushLockExclusive(v38);
    v39 = RtlLookupElementGenericTable(*((PRTL_GENERIC_TABLE *)v37 + 28), &Buffer);
    if ( v39 )
      v36 = (void *)v39[1];
    if ( v38 )
      GreReleasePushLockExclusive(v38);
  }
  else
  {
    v36 = v126;
  }
  if ( !v36 )
    goto LABEL_6;
  v40 = Gre::Base::Globals(v35);
  LOBYTE(v41) = 15;
  v42 = HmgShareLock(v40, v36, v41, 0);
  v44 = v42;
  if ( !v42 )
    goto LABEL_6;
  if ( (*(_DWORD *)(v42 + 136) & 0x10) == 0 )
  {
    v45 = 0;
    v108 = 0;
    v115 = 0;
    if ( v42 != -88 )
      GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v42 + 88));
    v46 = *(__int64 **)(v44 + 144);
    v126 = *(void **)v44;
    v113 = (struct SFMLOGICALSURFACE *)v46;
    FirstLSurf = (struct SFMLOGICALSURFACE *)v46;
    memset(v135, 0, sizeof(v135));
    PushThreadGuardedObject(
      v135,
      v135,
      UnexpectedThreadTerminationHandler<SFMLOGICALSURFACEREF>::OnUnexpectedThreadTerminationStatic);
    v136 = 0;
    v137 = 1;
    if ( v46 )
    {
      v51 = *v46;
      if ( *v46 )
      {
        v52 = Gre::Base::Globals(v49);
        LOBYTE(v53) = 18;
        v136 = HmgLock(v52, v51, v53);
      }
    }
    *(_QWORD *)&Buffer = v46 + 32;
    if ( v46 != (__int64 *)-256LL )
      GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v46 + 32));
    if ( v117 )
    {
      v106 = *v117;
      v117 = &v159;
      v159 = v106;
    }
    if ( v21 == 0x2000000 )
    {
      v54 = &v110;
      v110 = 33488896;
      v21 = 570425346;
      v114 = &v110;
      if ( v118 || (v91 = 0, v119) )
        v91 = 1;
      vSpDwmUpdateSpriteVisibility((struct DWMSPRITE *)v44, v91);
    }
    else
    {
      v54 = v114;
      if ( (a11 & 0x20000000) == 0 )
      {
        if ( (a11 & 0x40000000) != 0 || !v21 )
        {
          v54 = (int *)(v44 + 76);
          v21 = *(_DWORD *)(v44 + 72);
          a9 = *(_DWORD *)(v44 + 80);
        }
        v114 = v54;
LABEL_44:
        v111 = 2;
        v55 = v21 & 2;
        if ( (v21 & 2) != 0 && (!v54 || (*((_BYTE *)v54 + 3) & 1) != 0 && (*((_DWORD *)v46 + 63) & 1) != 0) )
        {
          v109 = 0;
          goto LABEL_63;
        }
        *(_DWORD *)(v44 + 72) = v21;
        v45 = 1;
        v109 = 1;
        if ( (v21 & 2) != 0 )
        {
          if ( *(_BYTE *)(v44 + 79) != *((_BYTE *)v54 + 3) )
          {
            v70 = bSpDwmCreateLogicalSurface(v116, (struct DWMSPRITE *)v44, (struct SFMLOGICALSURFACE *)v46, 0, &v113);
            FirstLSurf = v113;
            v45 = v70;
            v109 = v70;
          }
          *(_DWORD *)(v44 + 76) = *v54;
          v55 = (unsigned int)*v54;
          *((_DWORD *)FirstLSurf + 61) |= 0x40u;
          *((_DWORD *)FirstLSurf + 60) = v55;
        }
        if ( (v21 & 1) != 0 )
        {
          *(_DWORD *)(v44 + 80) = a9;
          v97 = v46[23];
          if ( v97 )
          {
            if ( (*(_DWORD *)(v97 + 124) & 1) != 0
              && !(unsigned int)bRemoteDriverNeedsDeviceBitmaps((struct PDEVOBJ *)&v131) )
            {
              v98 = v46[23];
              if ( PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v131) )
              {
                v99 = *(_DWORD *)(v98 + 124);
                if ( (v99 & 0x20) == 0 )
                {
                  v100 = *(void **)(v98 + 8);
                  *(_DWORD *)(v98 + 124) = v99 | 0x20;
                  GrepQueueApc(pConvertDfbSurfaceToDibNKAPC, v100, 0);
                  v108 = 1;
                }
              }
              else
              {
                v107 = (SURFACE *)pProcessDfbSurfaces(v98 - 24, 1);
                if ( v107 )
                {
                  FirstLSurf = SURFACE::GetFirstLSurf(v107);
                  v113 = FirstLSurf;
                }
              }
            }
          }
        }
        if ( !v45 )
          goto LABEL_63;
        v55 = (unsigned __int64)v119;
        if ( v119 )
        {
          y = v119->y;
          x = v119->x;
          v58 = *(_DWORD *)(v44 + 56);
          *(_DWORD *)(v44 + 56) = v119->x;
          *(_DWORD *)(v44 + 64) += x - v58;
          *(_DWORD *)(v44 + 68) += y - *(_DWORD *)(v44 + 60);
          v55 = (unsigned __int64)v119;
          *(_DWORD *)(v44 + 60) = y;
        }
        if ( (*((_DWORD *)FirstLSurf + 63) & 1) != 0 )
        {
          if ( v117 && *((_QWORD *)FirstLSurf + 23) )
            vSpUpdateDirtyRgn((struct DWMSPRITE *)v44, FirstLSurf, *((HDC *)v125 + 12), v117, &v112, a15);
        }
        else
        {
          if ( (v21 & 0x2000000) != 0 )
          {
            if ( v55 && v118 )
            {
              updated = bSpDwmUpdateDragRectShape(v116, (struct DWMSPRITE *)v44, FirstLSurf, v50, v118, &v112, &v113);
              FirstLSurf = v113;
              v45 = updated;
            }
          }
          else if ( v124 )
          {
            v92 = v118;
            if ( v118 )
            {
              v93 = v125;
              v45 = 0;
              v109 = 0;
              v94 = OPTAPIDCOBJ::bValid(v125);
              v55 = 0;
              if ( !v94 )
                goto LABEL_63;
              v95 = *((_QWORD *)v93 + 2);
              v147 = 0;
              v144 = 0;
              v145 = 0;
              v146 = v95;
              UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v148);
              UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v149);
              v96 = *(DC **)v93;
              v149[32] = 0;
              v144 = v96;
              if ( *((_QWORD *)v96 + 62) && !(unsigned int)DC::bInFullScreen(v96) )
              {
                v60 = v124->y;
                v127.left = v124->x;
                v127.right = v92->cx + v127.left;
                v61 = v60 + v92->cy;
                v127.top = v60;
                v127.bottom = v61;
                v62 = bSpDwmUpdateSpriteShape(
                        v116,
                        (struct DWMSPRITE *)v44,
                        FirstLSurf,
                        (struct _SURFOBJ *)(v59 + 24),
                        &v127,
                        *(struct PALETTE **)(v59 + 160),
                        &v112,
                        (struct _RECTL *)((unsigned __int64)&v159 & -(__int64)(v117 != 0)),
                        &v113);
                FirstLSurf = v113;
                v45 = v62;
              }
              APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v144);
            }
          }
          v109 = v45;
          if ( !v45 )
          {
LABEL_63:
            if ( !*(_QWORD *)(v44 + 40) )
            {
              if ( v44 != -56 )
              {
                v150[0] = *(_OWORD *)(v44 + 56);
                v150[1] = v150[0];
              }
              v151 = 0;
              v152 = 0;
              UserSessionState = W32GetUserSessionState(v55, v48);
              v19 = (struct tagMINIWINDOWINFO *)v150;
              v128 = (struct tagMINIWINDOWINFO *)v150;
              v153 = *(_QWORD *)(UserSessionState + 18760);
            }
            if ( v45 && !v108 && (v19 || (*((_DWORD *)FirstLSurf + 63) & 8) != 0) )
            {
              if ( (*((_DWORD *)FirstLSurf + 63) & 8) != 0 )
                SFMLOGICALSURFACE::StartSfmStateTracking(FirstLSurf, v116, *((struct SfmState **)v120 + 543), (int)v50);
              v71 = (_DWORD *)*((_QWORD *)FirstLSurf + 23);
              if ( v71 )
              {
                v72 = v71[8];
                v73 = v71[9];
                if ( (v71[31] & 1) == 0 )
                  v111 = (v71[30] & 0x800) != 0;
              }
              else
              {
                v72 = 0;
                v111 = 0;
                v73 = 0;
              }
              *(_QWORD *)&v127.left = *(_QWORD *)(v44 + 104);
              LODWORD(v113) = *(_DWORD *)(v44 + 116);
              *(_QWORD *)(v44 + 104) = 0;
              v122 = *((_DWORD *)FirstLSurf + 63);
              v121 = *(_DWORD *)(v44 + 136);
              v141 = *(_QWORD *)FirstLSurf;
              v120 = *(struct Gre::Base::SESSION_GLOBALS **)v44;
              v74 = (void *)UserReferenceDwmApiPort();
              IncrementDWMWindowUniqueness();
              if ( v74 )
              {
                memset_0(&v154, 0, 0xECu);
                v155 = 0x8000;
                *(_QWORD *)((char *)&v156 + 4) = v120;
                *(_QWORD *)&v157[152] = v141;
                v154 = 15466692;
                LODWORD(v156) = 1073741830;
                v76 = v122 & 0xC;
                v77 = v121 & 0x40;
                v78 = v121 & 1;
                v79 = (unsigned int)v78 | (unsigned int)v76 | (2 * (v77 | v122 & 1 | (4 * (v121 & 0xE))));
                HIDWORD(v156) = v78 | v76 | (2 * (v77 | v122 & 1 | (4 * (v121 & 0xE))));
                if ( v44 != -72 )
                {
                  v80 = *(_DWORD *)(v44 + 80);
                  *(_QWORD *)&v157[140] = *(_QWORD *)(v44 + 72);
                  *(_DWORD *)&v157[148] = v80;
                }
                if ( v128 )
                {
                  v81 = *(_OWORD *)v128;
                  *(_DWORD *)v157 = 1;
                  v82 = *((_OWORD *)v128 + 1);
                  *(_OWORD *)&v157[4] = v81;
                  v83 = *((_OWORD *)v128 + 2);
                  *(_OWORD *)&v157[20] = v82;
                  v84 = *((_OWORD *)v128 + 3);
                  *(_OWORD *)&v157[36] = v83;
                  v85 = *((_OWORD *)v128 + 4);
                  *(_OWORD *)&v157[52] = v84;
                  v86 = *((_OWORD *)v128 + 5);
                  *(_OWORD *)&v157[68] = v85;
                  v87 = *((_OWORD *)v128 + 6);
                  *(_OWORD *)&v157[84] = v86;
                  v88 = *((_OWORD *)v128 + 7);
                  v89 = *((_QWORD *)v128 + 16);
                  *(_OWORD *)&v157[100] = v87;
                  *(_QWORD *)&v157[132] = v89;
                  *(_OWORD *)&v157[116] = v88;
                }
                *(_DWORD *)v158 = v111;
                *(_QWORD *)&v158[12] = *(_QWORD *)&v127.left;
                *(_DWORD *)&v158[4] = v72;
                *(_DWORD *)&v158[8] = v73;
                SessionState = W32GetSessionState(v79, v78, v76, v75);
                if ( (int)v113 < 1
                  || (v102 = *(_QWORD *)(SessionState + 96),
                      v103 = *(unsigned int *)(v102 + 716),
                      (unsigned int)v103 >= 0x14) )
                {
                  EtwUpdateEvent(v120, 1073741830);
                  LpcRequestPort(v74, &v154);
                }
                else
                {
                  v104 = 196 * v103;
                  *(_OWORD *)(v104 + v102 + 720) = v156;
                  *(_OWORD *)(v104 + v102 + 736) = *(_OWORD *)v157;
                  *(_OWORD *)(v104 + v102 + 752) = *(_OWORD *)&v157[16];
                  *(_OWORD *)(v104 + v102 + 768) = *(_OWORD *)&v157[32];
                  *(_OWORD *)(v104 + v102 + 784) = *(_OWORD *)&v157[48];
                  *(_OWORD *)(v104 + v102 + 800) = *(_OWORD *)&v157[64];
                  *(_OWORD *)(v104 + v102 + 816) = *(_OWORD *)&v157[80];
                  *(_OWORD *)(v104 + v102 + 832) = *(_OWORD *)&v157[96];
                  *(_OWORD *)(v104 + v102 + 848) = *(_OWORD *)&v157[112];
                  *(_OWORD *)(v104 + v102 + 864) = *(_OWORD *)&v157[128];
                  *(_OWORD *)(v104 + v102 + 880) = *(_OWORD *)&v157[144];
                  *(_OWORD *)(v104 + v102 + 896) = *(_OWORD *)v158;
                  *(_DWORD *)(v104 + v102 + 912) = *(_DWORD *)&v158[16];
                  v105 = ++*(_DWORD *)(v102 + 716);
                  if ( v105 > *(_DWORD *)(v102 + 4640) )
                    *(_DWORD *)(v102 + 4640) = v105;
                }
                ObfDereferenceObject(v74);
              }
            }
            if ( (_QWORD)Buffer )
              GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)Buffer);
            SFMLOGICALSURFACEREF_vDestructor(v135);
            PopThreadGuardedObject(v135);
            v64 = *((_QWORD *)FirstLSurf + 23);
            if ( v64 )
              v65 = *(_QWORD *)(v64 + 8);
            else
              v65 = 0;
            v66 = v112;
            v67 = *(void **)v44;
            if ( v64 && (*(_DWORD *)(v64 + 124) & 1) != 0 )
              v66 = v112 & 0xFFFFFFFE;
            if ( (v66 & 1) != 0 && (unsigned __int8)bShouldUseSfmTokenArray(*((unsigned int *)FirstLSurf + 63)) )
            {
              GreAddLogicalSurfaceToDirtyQueue(*(_QWORD *)FirstLSurf, 1, v65);
              v66 &= ~1u;
            }
            if ( v66 )
            {
              v68 = (void *)UserReferenceDwmApiPort();
              IncrementDWMWindowUniqueness();
              if ( v68 )
              {
                memset_0(v135, 0, 0x40u);
                LODWORD(v135[0]) = 4194328;
                WORD2(v135[0]) = 0x8000;
                v137 = 1073741828;
                v139 = v67;
                v138 = v66;
                v140 = v65;
                EtwUpdateEvent(v67, 1073741828);
                LpcRequestPort(v68, v135);
                ObfDereferenceObject(v68);
              }
            }
            if ( FirstLSurf != (struct SFMLOGICALSURFACE *)-256LL )
              GreAcquirePushLockExclusive((struct SFMLOGICALSURFACE *)((char *)FirstLSurf + 256));
            *((_DWORD *)FirstLSurf + 63) &= ~8u;
            if ( FirstLSurf != (struct SFMLOGICALSURFACE *)-256LL )
              GreReleasePushLockExclusive((struct SFMLOGICALSURFACE *)((char *)FirstLSurf + 256));
            v43 = (struct W32_PUSH_LOCK *)(v44 + 88);
            if ( v44 != -88 )
              GreReleasePushLockExclusive(v43);
            v17 = (struct _BLENDFUNCTION *)v114;
            v24 = v109;
            goto LABEL_89;
          }
        }
        if ( a16
          && ((*((_QWORD *)FirstLSurf + 23) - 24LL)
            & ((unsigned __int128)-(__int128)*((unsigned __int64 *)FirstLSurf + 23) >> 64)) != 0
          && *(_DWORD *)(((*((_QWORD *)FirstLSurf + 23) - 24LL)
                        & ((unsigned __int128)-(__int128)*((unsigned __int64 *)FirstLSurf + 23) >> 64))
                       + 0x2B0) != a16 )
        {
          *(_DWORD *)(((*((_QWORD *)FirstLSurf + 23) - 24LL)
                     & ((unsigned __int128)-(__int128)*((unsigned __int64 *)FirstLSurf + 23) >> 64))
                    + 0x2B0) = a16;
        }
        v55 = *((unsigned int *)FirstLSurf + 63);
        if ( (*((_DWORD *)FirstLSurf + 63) & 0x41) == 1 )
        {
          v55 = (unsigned int)v55 | 0x40;
          *((_DWORD *)FirstLSurf + 63) = v55;
        }
        v48 = *((_QWORD *)FirstLSurf + 23);
        if ( v48 && (*(_DWORD *)(v48 + 124) & 1) == 0 && !*(_QWORD *)(v48 + 256) )
        {
          v55 = (unsigned int)v55 | 8;
          *((_DWORD *)FirstLSurf + 63) = v55;
        }
        goto LABEL_63;
      }
    }
    v21 &= ~0x20000000u;
    goto LABEL_44;
  }
LABEL_89:
  v69 = Gre::Base::Globals(v43);
  DEC_SHARE_REF_CNT(v69, v44);
LABEL_6:
  SEMOBJEXORSHARED<7>::~SEMOBJEXORSHARED<7>(&v133);
  if ( v132 )
  {
    v26 = *(_QWORD *)Gre::Base::Globals(v25);
    EtwTraceGreLockReleaseSemaphore(L"Sprite", v26 + 1040);
    GrepReleaseLockValidate<6>();
    GreReleaseSemaphoreExclusiveInternal((HSEMAPHORE)(v26 + 1040));
  }
  NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v142);
  if ( v115 )
  {
    v18 = v123;
    v16 = v116;
LABEL_3:
    v23 = v21 | 0x200000;
    if ( !v18 )
      v23 = v21;
    return (unsigned int)GdiUpdateSprite(v16, v129, v126, v143, v119, v118, v125, v124, a9, v17, v23, v117);
  }
  return v24;
}

```

## disassembly

```asm
0x140017000  push    rbp
0x140017002  push    rbx
0x140017003  push    rsi
0x140017004  push    rdi
0x140017005  push    r12
0x140017007  push    r13
0x140017009  push    r14
0x14001700b  push    r15
0x14001700d  lea     rbp, [rsp-2A8h]
0x140017015  sub     rsp, 3A8h
0x14001701c  mov     rax, cs:__security_cookie
0x140017023  xor     rax, rsp
0x140017026  mov     [rbp+2E0h+var_50], rax
0x14001702d  mov     rax, [rbp+2E0h+arg_28]
0x140017034  mov     rbx, rcx
0x140017037  mov     r12d, [rbp+2E0h+arg_50]
0x14001703e  mov     esi, r12d
0x140017041  mov     r15, [rbp+2E0h+arg_48]
0x140017048  and     esi, 200000h
0x14001704e  mov     r13, [rbp+2E0h+arg_60]
0x140017055  mov     [rbp+2E0h+var_340], rax
0x140017059  mov     rax, [rbp+2E0h+arg_38]
0x140017060  mov     [rbp+2E0h+var_318], rax
0x140017064  mov     rax, [rbp+2E0h+arg_20]
0x14001706b  mov     [rbp+2E0h+var_338], rax
0x14001706f  mov     rax, [rbp+2E0h+arg_30]
0x140017076  mov     [rbp+2E0h+var_310], rax
0x14001707a  mov     rax, [rbp+2E0h+arg_58]
0x140017081  mov     [rbp+2E0h+var_308], r8
0x140017085  mov     r8d, 88h; Size
0x14001708b  mov     [rbp+2E0h+var_2E8], rdx
0x14001708f  xor     edx, edx; Val
0x140017091  mov     [rbp+2E0h+var_350], rcx
0x140017095  lea     rcx, [rbp+2E0h+var_1E0]; void *
0x14001709c  mov     [rbp+2E0h+var_348], rax
0x1400170a0  mov     [rbp+2E0h+var_260], r9
0x1400170a7  mov     [rbp+2E0h+var_360], r15
0x1400170ab  mov     [rbp+2E0h+var_2F0], r13
0x1400170af  mov     [rbp+2E0h+var_320], esi
0x1400170b2  call    memset_0
0x1400170b7  mov     [rsp+3E0h+var_378], 0
0x1400170bf  mov     [rsp+3E0h+var_370], 0
0x1400170c7  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400170ce  nop     dword ptr [rax+rax+00h]
0x1400170d3  btr     r12d, 15h
0x1400170d8  mov     [rbp+2E0h+var_330], rax
0x1400170dc  cmp     [rbp+2E0h+arg_68], 0
0x1400170e3  mov     rdi, rax
0x1400170e6  jz      short loc_140017102
0x1400170e8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400170ef  nop     dword ptr [rax+rax+00h]
0x1400170f4  cmp     qword ptr [rax+0E0h], 0
0x1400170fc  jnz     loc_1400171FC
0x140017102  mov     r10, [rbp+2E0h+var_348]
0x140017106  mov     eax, r12d
0x140017109  mov     r9, [rbp+2E0h+var_260]; struct OPTAPIDCOBJ *
0x140017110  bts     eax, 15h
0x140017114  mov     r8, [rbp+2E0h+var_308]; void *
0x140017118  test    esi, esi
0x14001711a  mov     rdx, [rbp+2E0h+var_2E8]; HWND
0x14001711e  mov     rcx, rbx; HDEV
0x140017121  mov     [rsp+3E0h+var_388], r10; struct tagRECT *
0x140017126  cmovz   eax, r12d
0x14001712a  mov     [rsp+3E0h+var_390], eax; unsigned int
0x14001712e  mov     eax, [rbp+2E0h+arg_40]
0x140017134  mov     [rsp+3E0h+var_398], r15; struct _BLENDFUNCTION *
0x140017139  mov     dword ptr [rsp+3E0h+var_3A0], eax; unsigned int
0x14001713d  mov     rax, [rbp+2E0h+var_318]
0x140017141  mov     [rsp+3E0h+var_3A8], rax; struct tagPOINT *
0x140017146  mov     rax, [rbp+2E0h+var_310]
0x14001714a  mov     [rsp+3E0h+var_3B0], rax; struct OPTAPIDCOBJ *
0x14001714f  mov     rax, [rbp+2E0h+var_340]
0x140017153  mov     [rsp+3E0h+var_3B8], rax; struct tagSIZE *
0x140017158  mov     rax, [rbp+2E0h+var_338]
0x14001715c  mov     [rsp+3E0h+var_3C0], rax; struct tagPOINT *
0x140017161  call    ?GdiUpdateSprite@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@@Z; GdiUpdateSprite(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *)
0x140017166  mov     r14d, eax
0x140017169  jmp     short loc_1400171D5
0x14001716b  lea     rcx, [rbp+2E0h+var_2C0]
0x14001716f  call    ??1?$SEMOBJEXORSHARED@$06@@QEAA@XZ; SEMOBJEXORSHARED<7>::~SEMOBJEXORSHARED<7>(void)
0x140017174  cmp     [rbp+2E0h+var_2C8], 0
0x140017178  jz      short loc_1400171BB
0x14001717a  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140017181  nop     dword ptr [rax+rax+00h]
0x140017186  lea     rcx, aSprite; "Sprite"
0x14001718d  mov     rbx, [rax]
0x140017190  lea     rdx, [rbx+410h]
0x140017197  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14001719e  nop     dword ptr [rax+rax+00h]
0x1400171a3  call    ??$GrepReleaseLockValidate@$05@@YAXXZ; GrepReleaseLockValidate<6>(void)
0x1400171a8  lea     rcx, [rbx+410h]
0x1400171af  call    cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x1400171b6  nop     dword ptr [rax+rax+00h]
0x1400171bb  lea     rcx, [rbp+2E0h+var_268]
0x1400171bf  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ; NEEDGRELOCK::vUnlock(void)
0x1400171c6  nop     dword ptr [rax+rax+00h]
0x1400171cb  cmp     [rbp+2E0h+var_358], 0
0x1400171cf  jnz     loc_140017EC2
0x1400171d5  mov     eax, r14d
0x1400171d8  mov     rcx, [rbp+2E0h+var_50]
0x1400171df  xor     rcx, rsp; StackCookie
0x1400171e2  call    __security_check_cookie
0x1400171e7  add     rsp, 3A8h
0x1400171ee  pop     r15
0x1400171f0  pop     r14
0x1400171f2  pop     r13
0x1400171f4  pop     r12
0x1400171f6  pop     rdi
0x1400171f7  pop     rsi
0x1400171f8  pop     rbx
0x1400171f9  pop     rbp
0x1400171fa  retn
0x1400171fc  xor     r14d, r14d
0x1400171ff  mov     [rbp+2E0h+var_358], 1
0x140017206  test    esi, esi
0x140017208  lea     rcx, [rbp+2E0h+var_268]
0x14001720c  setz    dl
0x14001720f  call    cs:__imp_?vLock@NEEDGRELOCK@@QEAAX_N@Z; NEEDGRELOCK::vLock(bool)
0x140017216  nop     dword ptr [rax+rax+00h]
0x14001721b  mov     [rbp+2E0h+var_2D0], rbx
0x14001721f  mov     [rbp+2E0h+var_2C8], r14d
0x140017223  test    esi, esi
0x140017225  jnz     loc_1400172AF
0x14001722b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140017232  nop     dword ptr [rax+rax+00h]
0x140017237  test    rax, rax
0x14001723a  jz      loc_140017E52
0x140017240  mov     rcx, [rax]
0x140017243  lea     rax, [rcx+8]
0x140017247  neg     rcx
0x14001724a  sbb     rcx, rcx
0x14001724d  and     rcx, rax
0x140017250  jz      short loc_140017264
0x140017252  cmp     [rcx+154h], r14d
0x140017259  jnz     short loc_1400172AF
0x14001725b  cmp     [rcx+158h], r14d
0x140017262  jnz     short loc_1400172AF
0x140017264  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14001726b  nop     dword ptr [rax+rax+00h]
0x140017270  xor     r8d, r8d
0x140017273  lea     rcx, aSprite; "Sprite"
0x14001727a  mov     rbx, [rax]
0x14001727d  lea     rdx, [rbx+410h]
0x140017284  call    cs:__imp_EtwTraceGreLockAcquireSemaphoreExclusive
0x14001728b  nop     dword ptr [rax+rax+00h]
0x140017290  lea     rcx, [rbx+410h]
0x140017297  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14001729e  nop     dword ptr [rax+rax+00h]
0x1400172a3  call    ??$GrepAcquireLockValidate@$05@@YAXXZ; GrepAcquireLockValidate<6>(void)
0x1400172a8  mov     [rbp+2E0h+var_2C8], 1
0x1400172af  mov     rcx, [rdi]
0x1400172b2  add     rcx, 208h
0x1400172b9  test    esi, esi
0x1400172bb  mov     [rbp+2E0h+var_2C0], rcx
0x1400172bf  setnz   [rbp+2E0h+var_2B8]
0x1400172c3  test    esi, esi
0x1400172c5  jz      loc_140017832
0x1400172cb  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400172d2  nop     dword ptr [rax+rax+00h]
0x1400172d7  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x1400172dc  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400172e3  nop     dword ptr [rax+rax+00h]
0x1400172e8  cmp     [rax+0E0h], r14
0x1400172ef  jz      loc_14001716B
0x1400172f5  mov     rbx, [rbp+2E0h+var_2E8]
0x1400172f9  test    rbx, rbx
0x1400172fc  jz      loc_140017D18
0x140017302  xorps   xmm0, xmm0
0x140017305  xor     edi, edi
0x140017307  movups  [rbp+2E0h+Buffer], xmm0
0x14001730b  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140017312  nop     dword ptr [rax+rax+00h]
0x140017317  mov     qword ptr [rbp+2E0h+Buffer], rbx
0x14001731b  mov     rsi, rax
0x14001731e  mov     rbx, [rax+0E0h]
0x140017325  add     rbx, 48h ; 'H'
0x140017329  jz      short loc_14001733A
0x14001732b  mov     rcx, rbx
0x14001732e  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140017335  nop     dword ptr [rax+rax+00h]
0x14001733a  mov     rcx, [rsi+0E0h]; Table
0x140017341  lea     rdx, [rbp+2E0h+Buffer]; Buffer
0x140017345  call    cs:__imp_RtlLookupElementGenericTable
0x14001734c  nop     dword ptr [rax+rax+00h]
0x140017351  test    rax, rax
0x140017354  jz      short loc_14001735A
0x140017356  mov     rdi, [rax+8]
0x14001735a  test    rbx, rbx
0x14001735d  jz      short loc_14001736E
0x14001735f  mov     rcx, rbx
0x140017362  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x140017369  nop     dword ptr [rax+rax+00h]
0x14001736e  test    rdi, rdi
0x140017371  jz      loc_14001716B
0x140017377  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14001737e  nop     dword ptr [rax+rax+00h]
0x140017383  xor     r9d, r9d
0x140017386  mov     r8b, 0Fh
0x140017389  mov     rcx, rax
0x14001738c  mov     rdx, rdi
0x14001738f  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140017396  nop     dword ptr [rax+rax+00h]
0x14001739b  mov     rbx, rax
0x14001739e  test    rax, rax
0x1400173a1  jz      loc_14001716B
0x1400173a7  mov     eax, [rax+88h]
0x1400173ad  test    al, 10h
0x1400173af  jnz     loc_14001780F
0x1400173b5  xor     r15d, r15d
0x1400173b8  lea     rax, [rbx+58h]
0x1400173bc  mov     [rsp+3E0h+var_380], r15b
0x1400173c1  mov     [rbp+2E0h+var_358], r15d
0x1400173c5  test    rax, rax
0x1400173c8  jz      short loc_1400173D9
0x1400173ca  mov     rcx, rax
0x1400173cd  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x1400173d4  nop     dword ptr [rax+rax+00h]
0x1400173d9  mov     rsi, [rbx+90h]
0x1400173e0  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VSFMLOGICALSURFACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<SFMLOGICALSURFACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400173e7  mov     rax, [rbx]
0x1400173ea  lea     rdx, [rbp+2E0h+var_2B0]
0x1400173ee  xorps   xmm0, xmm0
0x1400173f1  mov     [rbp+2E0h+var_308], rax
0x1400173f5  lea     rcx, [rbp+2E0h+var_2B0]
0x1400173f9  mov     [rsp+3E0h+var_368], rsi
0x1400173fe  mov     rdi, rsi
0x140017401  movups  [rbp+2E0h+var_2B0], xmm0
0x140017405  movups  [rbp+2E0h+var_2A0], xmm0
0x140017409  call    cs:__imp_PushThreadGuardedObject
0x140017410  nop     dword ptr [rax+rax+00h]
0x140017415  mov     [rbp+2E0h+var_290], r15
0x140017419  mov     [rbp+2E0h+var_288], 1
0x140017420  test    rsi, rsi
0x140017423  jz      short loc_140017455
0x140017425  mov     r14, [rsi]
0x140017428  test    r14, r14
0x14001742b  jz      short loc_140017455
0x14001742d  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140017434  nop     dword ptr [rax+rax+00h]
0x140017439  xor     r9d, r9d
0x14001743c  mov     r8b, 12h
0x14001743f  mov     rcx, rax
0x140017442  mov     rdx, r14
0x140017445  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14001744c  nop     dword ptr [rax+rax+00h]
0x140017451  mov     [rbp+2E0h+var_290], rax
0x140017455  lea     rax, [rsi+100h]
0x14001745c  mov     qword ptr [rbp+2E0h+Buffer], rax
0x140017460  test    rax, rax
0x140017463  jz      short loc_140017474
0x140017465  mov     rcx, rax
0x140017468  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x14001746f  nop     dword ptr [rax+rax+00h]
0x140017474  mov     rax, [rbp+2E0h+var_348]
0x140017478  test    rax, rax
0x14001747b  jnz     loc_140017E59
0x140017481  cmp     r12d, 2000000h
0x140017488  jz      loc_140017AF1
0x14001748e  mov     r14, [rbp+2E0h+var_360]
0x140017492  mov     [rbp+2E0h+var_360], r14
0x140017496  bt      r12d, 1Dh
0x14001749b  jb      loc_140017B1C
0x1400174a1  bt      r12d, 1Eh
0x1400174a6  jnb     loc_140017C1E
0x1400174ac  mov     eax, [rbx+50h]
0x1400174af  lea     r14, [rbx+4Ch]
0x1400174b3  mov     r12d, [rbx+48h]
0x1400174b7  mov     [rbp+2E0h+arg_40], eax
0x1400174bd  mov     [rbp+2E0h+var_360], r14
0x1400174c1  mov     eax, 2
0x1400174c6  mov     ecx, r12d
0x1400174c9  mov     [rsp+3E0h+var_374], eax
0x1400174cd  and     ecx, eax
0x1400174cf  jnz     loc_140017843
0x1400174d5  mov     [rbx+48h], r12d
0x1400174d9  mov     r15d, 1
0x1400174df  mov     [rsp+3E0h+var_37C], r15d
0x1400174e4  test    ecx, ecx
0x1400174e6  jnz     loc_14001786B
0x1400174ec  test    r12b, 1
0x1400174f0  jnz     loc_140017C2C
0x1400174f6  test    r15d, r15d
0x1400174f9  jz      loc_140017653
0x1400174ff  mov     rcx, [rbp+2E0h+var_338]
0x140017503  test    rcx, rcx
0x140017506  jz      short loc_14001752A
0x140017508  mov     r8d, [rcx+4]
0x14001750c  mov     ecx, [rcx]
0x14001750e  mov     eax, [rbx+38h]
0x140017511  mov     [rbx+38h], ecx
0x140017514  sub     ecx, eax
0x140017516  add     [rbx+40h], ecx
0x140017519  mov     eax, r8d
0x14001751c  sub     eax, [rbx+3Ch]
0x14001751f  add     [rbx+44h], eax
0x140017522  mov     rcx, [rbp+2E0h+var_338]
0x140017526  mov     [rbx+3Ch], r8d
0x14001752a  mov     eax, [rdi+0FCh]
0x140017530  test    al, 1
0x140017532  jz      loc_140017B26
  ... truncated ...
```
