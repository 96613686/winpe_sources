# GrepUpdateSpriteImpl(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *,tagMINIWINDOWINFO *,int,int,ulong)

- ea: `0x1400865c0`
- end: `0x1400874a3`
- name: `?GrepUpdateSpriteImpl@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@PEAUtagMINIWINDOWINFO@@HHK@Z`
- size: `3811`
- prototype: `__int64 __fastcall(HDEV, HWND, void *, struct OPTAPIDCOBJ *, struct tagPOINT *, struct tagSIZE *, struct OPTAPIDCOBJ *, struct tagPOINT *, unsigned int, struct _BLENDFUNCTION *, unsigned int, struct tagRECT *, struct tagMINIWINDOWINFO *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x140086434`

## callees

- `0x140062d70`
- `0x140063f70`
- `0x1400661bc`
- `0x14007eef8`
- `0x140084a10`
- `0x140084abc`
- `0x140085840`
- `0x1400858a8`
- `0x1400865c0`
- `0x1400875b8`
- `0x140087648`
- `0x140087940`
- `0x140087eb0`
- `0x1400883f8`
- `0x14008916c`
- `0x14008bc3c`
- `0x14008bc7c`
- `0x1400923b8`
- `0x140135050`
- `0x14017e6e8`
- `0x1401b72e4`
- `0x140213748`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTable` at `0x140086905`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x140086905`
- `ntoskrnl!LpcRequestPort` at `0x140086d66`
- `ntoskrnl!LpcRequestPort` at `0x14008709d`
- `ntoskrnl!LpcRequestPort` at `0x140086d66`
- `ntoskrnl!LpcRequestPort` at `0x14008709d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400867eb`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400867eb`
- `ntoskrnl!ObfDereferenceObject` at `0x140086d75`
- `ntoskrnl!ObfDereferenceObject` at `0x1400870ac`
- `ntoskrnl!ObfDereferenceObject` at `0x140086d75`
- `ntoskrnl!ObfDereferenceObject` at `0x1400870ac`
- `win32kbase!UserReferenceDwmApiPort` at `0x140086d05`
- `win32kbase!UserReferenceDwmApiPort` at `0x140086f13`
- `win32kbase!UserReferenceDwmApiPort` at `0x140086d05`
- `win32kbase!UserReferenceDwmApiPort` at `0x140086f13`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140086687`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400866a8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008673a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140086824`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008689c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400868cb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140086937`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400869ed`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140086dd5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140086687`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400866a8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008673a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140086824`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008689c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400868cb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140086937`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400869ed`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140086dd5`
- `win32kbase!HmgShareLock` at `0x14008694f`
- `win32kbase!HmgShareLock` at `0x14008694f`
- `win32kbase!PopThreadGuardedObject` at `0x140086cb8`
- `win32kbase!PopThreadGuardedObject` at `0x140086cb8`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140086de7`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140086de7`
- `win32kbase!PushThreadGuardedObject` at `0x1400869c9`
- `win32kbase!PushThreadGuardedObject` at `0x1400869c9`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140086757`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140086757`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14008688b`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14008688b`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x14008677f`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x14008677f`
- `win32kbase!GreReleasePushLockExclusive` at `0x140086922`
- `win32kbase!GreReleasePushLockExclusive` at `0x140086c9f`
- `win32kbase!GreReleasePushLockExclusive` at `0x140086dab`
- `win32kbase!GreReleasePushLockExclusive` at `0x140086dc0`
- `win32kbase!GreReleasePushLockExclusive` at `0x140086922`
- `win32kbase!GreReleasePushLockExclusive` at `0x140086c9f`
- `win32kbase!GreReleasePushLockExclusive` at `0x140086dab`
- `win32kbase!GreReleasePushLockExclusive` at `0x140086dc0`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1400868ee`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14008698d`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140086a28`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140086d90`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1400868ee`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14008698d`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140086a28`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140086d90`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140086857`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140086df8`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140086857`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140086df8`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14008676f`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14008676f`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreExclusive` at `0x140086844`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreExclusive` at `0x140086844`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140086a05`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140086a05`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x14008723b`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x14008723b`
- `win32kbase!?GrepQueueApc@@YA_NP6AXPEAX00@Z00@Z` at `0x140087276`
- `win32kbase!?GrepQueueApc@@YA_NP6AXPEAX00@Z00@Z` at `0x140087276`
- `win32kbase!?GetFirstLSurf@SURFACE@@QEAAPEAVSFMLOGICALSURFACE@@XZ` at `0x14008747e`
- `win32kbase!?GetFirstLSurf@SURFACE@@QEAAPEAVSFMLOGICALSURFACE@@XZ` at `0x14008747e`
- `win32kbase!pProcessDfbSurfaces` at `0x140087466`
- `win32kbase!pProcessDfbSurfaces` at `0x140087466`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAX_N@Z` at `0x1400867cf`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAX_N@Z` at `0x1400867cf`
- `win32kbase!EtwUpdateEvent` at `0x140086d53`
- `win32kbase!EtwUpdateEvent` at `0x140087087`
- `win32kbase!EtwUpdateEvent` at `0x140086d53`
- `win32kbase!EtwUpdateEvent` at `0x140087087`
- `WIN32K!W32GetSessionState` at `0x140087067`
- `WIN32K!W32GetSessionState` at `0x140087067`
- `WIN32K!W32GetUserSessionState` at `0x140086c4e`
- `WIN32K!W32GetUserSessionState` at `0x140086c4e`

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
  Gre::Base *v48; // rcx
  struct tagPOINT *v49; // r9
  __int64 v50; // r14
  struct Gre::Base::SESSION_GLOBALS *v51; // rax
  __int64 v52; // r8
  int *v53; // r14
  unsigned __int64 v54; // rcx
  LONG y; // r8d
  LONG x; // ecx
  int v57; // eax
  __int64 v58; // r8
  LONG v59; // edx
  LONG v60; // ecx
  int v61; // eax
  __int64 v62; // rdx
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
  int v75; // r8d
  int v76; // eax
  int v77; // edx
  __int64 v78; // rcx
  int v79; // eax
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int64 v88; // rax
  __int64 SessionState; // rax
  bool v90; // dl
  struct tagSIZE *v91; // rsi
  OPTAPIDCOBJ *v92; // r14
  bool v93; // al
  __int64 v94; // rax
  DC *v95; // rcx
  __int64 v96; // rax
  __int64 v97; // r14
  int v98; // eax
  void *v99; // rdx
  int updated; // eax
  __int64 v101; // rdx
  __int64 v102; // rax
  __int64 v103; // rcx
  unsigned int v104; // eax
  struct tagRECT v105; // xmm0
  SURFACE *v106; // rax
  char v107; // [rsp+60h] [rbp-A0h]
  int v108; // [rsp+64h] [rbp-9Ch]
  int v109; // [rsp+68h] [rbp-98h] BYREF
  int v110; // [rsp+6Ch] [rbp-94h]
  unsigned int v111; // [rsp+70h] [rbp-90h] BYREF
  struct SFMLOGICALSURFACE *v112; // [rsp+78h] [rbp-88h] BYREF
  int *v113; // [rsp+80h] [rbp-80h]
  int v114; // [rsp+88h] [rbp-78h]
  HDEV v115; // [rsp+90h] [rbp-70h]
  struct tagRECT *v116; // [rsp+98h] [rbp-68h]
  struct tagSIZE *v117; // [rsp+A0h] [rbp-60h]
  struct tagPOINT *v118; // [rsp+A8h] [rbp-58h]
  struct Gre::Base::SESSION_GLOBALS *v119; // [rsp+B0h] [rbp-50h]
  int v120; // [rsp+B8h] [rbp-48h]
  int v121; // [rsp+BCh] [rbp-44h]
  unsigned int v122; // [rsp+C0h] [rbp-40h]
  struct tagPOINT *v123; // [rsp+C8h] [rbp-38h]
  OPTAPIDCOBJ *v124; // [rsp+D0h] [rbp-30h]
  void *v125; // [rsp+D8h] [rbp-28h]
  struct _RECTL v126; // [rsp+E0h] [rbp-20h] BYREF
  struct tagMINIWINDOWINFO *v127; // [rsp+F0h] [rbp-10h]
  HWND v128; // [rsp+F8h] [rbp-8h]
  __int128 Buffer; // [rsp+100h] [rbp+0h] BYREF
  HDEV v130; // [rsp+110h] [rbp+10h] BYREF
  int v131; // [rsp+118h] [rbp+18h]
  HSEMAPHORE v132; // [rsp+120h] [rbp+20h] BYREF
  bool v133; // [rsp+128h] [rbp+28h]
  _OWORD v134[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v135; // [rsp+150h] [rbp+50h]
  int v136; // [rsp+158h] [rbp+58h]
  unsigned int v137; // [rsp+15Ch] [rbp+5Ch]
  void *v138; // [rsp+160h] [rbp+60h]
  __int64 v139; // [rsp+168h] [rbp+68h]
  __int64 v140; // [rsp+170h] [rbp+70h]
  _BYTE v141[8]; // [rsp+178h] [rbp+78h] BYREF
  struct OPTAPIDCOBJ *v142; // [rsp+180h] [rbp+80h]
  DC *v143; // [rsp+190h] [rbp+90h] BYREF
  int v144; // [rsp+198h] [rbp+98h]
  __int64 v145; // [rsp+1A0h] [rbp+A0h]
  __int64 v146; // [rsp+1A8h] [rbp+A8h]
  _BYTE v147[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v148[48]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v149[2]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v150; // [rsp+220h] [rbp+120h]
  __int64 v151; // [rsp+228h] [rbp+128h]
  __int64 v152; // [rsp+230h] [rbp+130h]
  int v153; // [rsp+290h] [rbp+190h] BYREF
  __int16 v154; // [rsp+294h] [rbp+194h]
  __int128 v155; // [rsp+2B8h] [rbp+1B8h]
  _BYTE v156[160]; // [rsp+2C8h] [rbp+1C8h]
  _BYTE v157[20]; // [rsp+368h] [rbp+268h]
  struct tagRECT v158; // [rsp+380h] [rbp+280h] BYREF

  v16 = a1;
  v17 = a10;
  v18 = a11 & 0x200000;
  v19 = a13;
  v117 = a6;
  v123 = a8;
  v118 = a5;
  v124 = a7;
  v125 = a3;
  v128 = a2;
  v115 = a1;
  v116 = a12;
  v142 = a4;
  v113 = (int *)a10;
  v127 = a13;
  v122 = a11 & 0x200000;
  memset_0(v149, 0, 0x88u);
  v109 = 0;
  v111 = 0;
  v21 = a11 & 0xFFDFFFFF;
  v119 = Gre::Base::Globals(v20);
  if ( !a14 || !*((_QWORD *)Gre::Base::Globals(v22) + 28) )
    goto LABEL_3;
  v24 = 0;
  v114 = 1;
  NEEDGRELOCK::vLock((NEEDGRELOCK *)v141, v18 == 0);
  v130 = v16;
  v131 = 0;
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
      v131 = 1;
    }
  }
  v33 = (HSEMAPHORE)(*(_QWORD *)v119 + 520LL);
  v132 = v33;
  v133 = v18 != 0;
  if ( v18 )
    GreAcquireSemaphoreSharedInternal(v33);
  else
    GreAcquireSemaphoreInternal(v33);
  GrepAcquireLockValidate<7>();
  if ( !*((_QWORD *)Gre::Base::Globals(v34) + 28) )
    goto LABEL_6;
  if ( v128 )
  {
    v36 = 0;
    Buffer = 0;
    *(_QWORD *)&Buffer = v128;
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
    v36 = v125;
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
    v107 = 0;
    v114 = 0;
    if ( v42 != -88 )
      GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v42 + 88));
    v46 = *(__int64 **)(v44 + 144);
    v125 = *(void **)v44;
    v112 = (struct SFMLOGICALSURFACE *)v46;
    FirstLSurf = (struct SFMLOGICALSURFACE *)v46;
    memset(v134, 0, sizeof(v134));
    PushThreadGuardedObject(
      v134,
      v134,
      UnexpectedThreadTerminationHandler<SFMLOGICALSURFACEREF>::OnUnexpectedThreadTerminationStatic);
    v135 = 0;
    v136 = 1;
    if ( v46 )
    {
      v50 = *v46;
      if ( *v46 )
      {
        v51 = Gre::Base::Globals(v48);
        LOBYTE(v52) = 18;
        v135 = HmgLock(v51, v50, v52);
      }
    }
    *(_QWORD *)&Buffer = v46 + 32;
    if ( v46 != (__int64 *)-256LL )
      GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v46 + 32));
    if ( v116 )
    {
      v105 = *v116;
      v116 = &v158;
      v158 = v105;
    }
    if ( v21 == 0x2000000 )
    {
      v53 = &v109;
      v109 = 33488896;
      v21 = 570425346;
      v113 = &v109;
      if ( v117 || (v90 = 0, v118) )
        v90 = 1;
      vSpDwmUpdateSpriteVisibility((struct DWMSPRITE *)v44, v90);
    }
    else
    {
      v53 = v113;
      if ( (a11 & 0x20000000) == 0 )
      {
        if ( (a11 & 0x40000000) != 0 || !v21 )
        {
          v53 = (int *)(v44 + 76);
          v21 = *(_DWORD *)(v44 + 72);
          a9 = *(_DWORD *)(v44 + 80);
        }
        v113 = v53;
LABEL_44:
        v110 = 2;
        v54 = v21 & 2;
        if ( (v21 & 2) != 0 && (!v53 || (*((_BYTE *)v53 + 3) & 1) != 0 && (*((_DWORD *)v46 + 63) & 1) != 0) )
        {
          v108 = 0;
          goto LABEL_63;
        }
        *(_DWORD *)(v44 + 72) = v21;
        v45 = 1;
        v108 = 1;
        if ( (v21 & 2) != 0 )
        {
          if ( *(_BYTE *)(v44 + 79) != *((_BYTE *)v53 + 3) )
          {
            v70 = bSpDwmCreateLogicalSurface(v115, (struct DWMSPRITE *)v44, (struct SFMLOGICALSURFACE *)v46, 0, &v112);
            FirstLSurf = v112;
            v45 = v70;
            v108 = v70;
          }
          *(_DWORD *)(v44 + 76) = *v53;
          v54 = (unsigned int)*v53;
          *((_DWORD *)FirstLSurf + 61) |= 0x40u;
          *((_DWORD *)FirstLSurf + 60) = v54;
        }
        if ( (v21 & 1) != 0 )
        {
          *(_DWORD *)(v44 + 80) = a9;
          v96 = v46[23];
          if ( v96 )
          {
            if ( (*(_DWORD *)(v96 + 140) & 1) != 0
              && !(unsigned int)bRemoteDriverNeedsDeviceBitmaps((struct PDEVOBJ *)&v130) )
            {
              v97 = v46[23];
              if ( PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v130) )
              {
                v98 = *(_DWORD *)(v97 + 140);
                if ( (v98 & 0x20) == 0 )
                {
                  v99 = *(void **)(v97 + 8);
                  *(_DWORD *)(v97 + 140) = v98 | 0x20;
                  GrepQueueApc(pConvertDfbSurfaceToDibNKAPC, v99, 0);
                  v107 = 1;
                }
              }
              else
              {
                v106 = (SURFACE *)pProcessDfbSurfaces(v97 - 24, 1);
                if ( v106 )
                {
                  FirstLSurf = SURFACE::GetFirstLSurf(v106);
                  v112 = FirstLSurf;
                }
              }
            }
          }
        }
        if ( !v45 )
          goto LABEL_63;
        v54 = (unsigned __int64)v118;
        if ( v118 )
        {
          y = v118->y;
          x = v118->x;
          v57 = *(_DWORD *)(v44 + 56);
          *(_DWORD *)(v44 + 56) = v118->x;
          *(_DWORD *)(v44 + 64) += x - v57;
          *(_DWORD *)(v44 + 68) += y - *(_DWORD *)(v44 + 60);
          v54 = (unsigned __int64)v118;
          *(_DWORD *)(v44 + 60) = y;
        }
        if ( (*((_DWORD *)FirstLSurf + 63) & 1) != 0 )
        {
          if ( v116 && *((_QWORD *)FirstLSurf + 23) )
            vSpUpdateDirtyRgn((struct DWMSPRITE *)v44, FirstLSurf, *((HDC *)v124 + 12), v116, &v111, a15);
        }
        else
        {
          if ( (v21 & 0x2000000) != 0 )
          {
            if ( v54 && v117 )
            {
              updated = bSpDwmUpdateDragRectShape(v115, (struct DWMSPRITE *)v44, FirstLSurf, v49, v117, &v111, &v112);
              FirstLSurf = v112;
              v45 = updated;
            }
          }
          else if ( v123 )
          {
            v91 = v117;
            if ( v117 )
            {
              v92 = v124;
              v45 = 0;
              v108 = 0;
              v93 = OPTAPIDCOBJ::bValid(v124);
              v54 = 0;
              if ( !v93 )
                goto LABEL_63;
              v94 = *((_QWORD *)v92 + 2);
              v146 = 0;
              v143 = 0;
              v144 = 0;
              v145 = v94;
              UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v147);
              UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v148);
              v95 = *(DC **)v92;
              v148[32] = 0;
              v143 = v95;
              if ( *((_QWORD *)v95 + 62) && !(unsigned int)DC::bInFullScreen(v95) )
              {
                v59 = v123->y;
                v126.left = v123->x;
                v126.right = v91->cx + v126.left;
                v60 = v59 + v91->cy;
                v126.top = v59;
                v126.bottom = v60;
                v61 = bSpDwmUpdateSpriteShape(
                        v115,
                        (struct DWMSPRITE *)v44,
                        FirstLSurf,
                        (struct _SURFOBJ *)(v58 + 24),
                        &v126,
                        *(struct PALETTE **)(v58 + 176),
                        &v111,
                        (struct _RECTL *)((unsigned __int64)&v158 & -(__int64)(v116 != 0)),
                        &v112);
                FirstLSurf = v112;
                v45 = v61;
              }
              APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v143);
            }
          }
          v108 = v45;
          if ( !v45 )
          {
LABEL_63:
            if ( !*(_QWORD *)(v44 + 40) )
            {
              if ( v44 != -56 )
              {
                v149[0] = *(_OWORD *)(v44 + 56);
                v149[1] = v149[0];
              }
              v150 = 0;
              v151 = 0;
              UserSessionState = W32GetUserSessionState(v54);
              v19 = (struct tagMINIWINDOWINFO *)v149;
              v127 = (struct tagMINIWINDOWINFO *)v149;
              v152 = *(_QWORD *)(UserSessionState + 18760);
            }
            if ( v45 && !v107 && (v19 || (*((_DWORD *)FirstLSurf + 63) & 8) != 0) )
            {
              if ( (*((_DWORD *)FirstLSurf + 63) & 8) != 0 )
                SFMLOGICALSURFACE::StartSfmStateTracking(FirstLSurf, v115, *((struct SfmState **)v119 + 543), (int)v49);
              v71 = (_DWORD *)*((_QWORD *)FirstLSurf + 23);
              if ( v71 )
              {
                v72 = v71[8];
                v73 = v71[9];
                if ( (v71[35] & 1) == 0 )
                  v110 = (v71[34] & 0x800) != 0;
              }
              else
              {
                v72 = 0;
                v110 = 0;
                v73 = 0;
              }
              *(_QWORD *)&v126.left = *(_QWORD *)(v44 + 104);
              LODWORD(v112) = *(_DWORD *)(v44 + 116);
              *(_QWORD *)(v44 + 104) = 0;
              v121 = *((_DWORD *)FirstLSurf + 63);
              v120 = *(_DWORD *)(v44 + 136);
              v140 = *(_QWORD *)FirstLSurf;
              v119 = *(struct Gre::Base::SESSION_GLOBALS **)v44;
              v74 = (void *)UserReferenceDwmApiPort();
              IncrementDWMWindowUniqueness();
              if ( v74 )
              {
                memset_0(&v153, 0, 0xECu);
                v154 = 0x8000;
                *(_QWORD *)((char *)&v155 + 4) = v119;
                *(_QWORD *)&v156[152] = v140;
                v153 = 15466692;
                LODWORD(v155) = 1073741830;
                v75 = v121 & 0xC;
                v76 = v120 & 0x40;
                v77 = v120 & 1;
                v78 = v77 | v75 | (2 * (v76 | v121 & 1 | (4 * (v120 & 0xEu))));
                HIDWORD(v155) = v77 | v75 | (2 * (v76 | v121 & 1 | (4 * (v120 & 0xE))));
                if ( v44 != -72 )
                {
                  v79 = *(_DWORD *)(v44 + 80);
                  *(_QWORD *)&v156[140] = *(_QWORD *)(v44 + 72);
                  *(_DWORD *)&v156[148] = v79;
                }
                if ( v127 )
                {
                  v80 = *(_OWORD *)v127;
                  *(_DWORD *)v156 = 1;
                  v81 = *((_OWORD *)v127 + 1);
                  *(_OWORD *)&v156[4] = v80;
                  v82 = *((_OWORD *)v127 + 2);
                  *(_OWORD *)&v156[20] = v81;
                  v83 = *((_OWORD *)v127 + 3);
                  *(_OWORD *)&v156[36] = v82;
                  v84 = *((_OWORD *)v127 + 4);
                  *(_OWORD *)&v156[52] = v83;
                  v85 = *((_OWORD *)v127 + 5);
                  *(_OWORD *)&v156[68] = v84;
                  v86 = *((_OWORD *)v127 + 6);
                  *(_OWORD *)&v156[84] = v85;
                  v87 = *((_OWORD *)v127 + 7);
                  v88 = *((_QWORD *)v127 + 16);
                  *(_OWORD *)&v156[100] = v86;
                  *(_QWORD *)&v156[132] = v88;
                  *(_OWORD *)&v156[116] = v87;
                }
                *(_DWORD *)v157 = v110;
                *(_QWORD *)&v157[12] = *(_QWORD *)&v126.left;
                *(_DWORD *)&v157[4] = v72;
                *(_DWORD *)&v157[8] = v73;
                SessionState = W32GetSessionState(v78);
                if ( (int)v112 < 1
                  || (v101 = *(_QWORD *)(SessionState + 96),
                      v102 = *(unsigned int *)(v101 + 716),
                      (unsigned int)v102 >= 0x14) )
                {
                  EtwUpdateEvent(v119, 1073741830);
                  LpcRequestPort(v74, &v153);
                }
                else
                {
                  v103 = 196 * v102;
                  *(_OWORD *)(v103 + v101 + 720) = v155;
                  *(_OWORD *)(v103 + v101 + 736) = *(_OWORD *)v156;
                  *(_OWORD *)(v103 + v101 + 752) = *(_OWORD *)&v156[16];
                  *(_OWORD *)(v103 + v101 + 768) = *(_OWORD *)&v156[32];
                  *(_OWORD *)(v103 + v101 + 784) = *(_OWORD *)&v156[48];
                  *(_OWORD *)(v103 + v101 + 800) = *(_OWORD *)&v156[64];
                  *(_OWORD *)(v103 + v101 + 816) = *(_OWORD *)&v156[80];
                  *(_OWORD *)(v103 + v101 + 832) = *(_OWORD *)&v156[96];
                  *(_OWORD *)(v103 + v101 + 848) = *(_OWORD *)&v156[112];
                  *(_OWORD *)(v103 + v101 + 864) = *(_OWORD *)&v156[128];
                  *(_OWORD *)(v103 + v101 + 880) = *(_OWORD *)&v156[144];
                  *(_OWORD *)(v103 + v101 + 896) = *(_OWORD *)v157;
                  *(_DWORD *)(v103 + v101 + 912) = *(_DWORD *)&v157[16];
                  v104 = ++*(_DWORD *)(v101 + 716);
                  if ( v104 > *(_DWORD *)(v101 + 4640) )
                    *(_DWORD *)(v101 + 4640) = v104;
                }
                ObfDereferenceObject(v74);
              }
            }
            if ( (_QWORD)Buffer )
              GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)Buffer);
            SFMLOGICALSURFACEREF_vDestructor(v134);
            PopThreadGuardedObject(v134);
            v64 = *((_QWORD *)FirstLSurf + 23);
            if ( v64 )
              v65 = *(_QWORD *)(v64 + 8);
            else
              v65 = 0;
            v66 = v111;
            v67 = *(void **)v44;
            if ( v64 && (*(_DWORD *)(v64 + 140) & 1) != 0 )
              v66 = v111 & 0xFFFFFFFE;
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
                memset_0(v134, 0, 0x40u);
                LODWORD(v134[0]) = 4194328;
                WORD2(v134[0]) = 0x8000;
                v136 = 1073741828;
                v138 = v67;
                v137 = v66;
                v139 = v65;
                EtwUpdateEvent(v67, 1073741828);
                LpcRequestPort(v68, v134);
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
            v17 = (struct _BLENDFUNCTION *)v113;
            v24 = v108;
            goto LABEL_89;
          }
        }
        if ( a16
          && ((*((_QWORD *)FirstLSurf + 23) - 24LL)
            & ((unsigned __int128)-(__int128)*((unsigned __int64 *)FirstLSurf + 23) >> 64)) != 0
          && *(_DWORD *)(((*((_QWORD *)FirstLSurf + 23) - 24LL)
                        & ((unsigned __int128)-(__int128)*((unsigned __int64 *)FirstLSurf + 23) >> 64))
                       + 0x2C0) != a16 )
        {
          *(_DWORD *)(((*((_QWORD *)FirstLSurf + 23) - 24LL)
                     & ((unsigned __int128)-(__int128)*((unsigned __int64 *)FirstLSurf + 23) >> 64))
                    + 0x2C0) = a16;
        }
        v54 = *((unsigned int *)FirstLSurf + 63);
        if ( (*((_DWORD *)FirstLSurf + 63) & 0x41) == 1 )
        {
          v54 = (unsigned int)v54 | 0x40;
          *((_DWORD *)FirstLSurf + 63) = v54;
        }
        v62 = *((_QWORD *)FirstLSurf + 23);
        if ( v62 && (*(_DWORD *)(v62 + 140) & 1) == 0 && !*(_QWORD *)(v62 + 272) )
        {
          v54 = (unsigned int)v54 | 8;
          *((_DWORD *)FirstLSurf + 63) = v54;
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
  SEMOBJEXORSHARED<7>::~SEMOBJEXORSHARED<7>(&v132);
  if ( v131 )
  {
    v26 = *(_QWORD *)Gre::Base::Globals(v25);
    EtwTraceGreLockReleaseSemaphore(L"Sprite", v26 + 1040);
    GrepReleaseLockValidate<6>();
    GreReleaseSemaphoreExclusiveInternal((HSEMAPHORE)(v26 + 1040));
  }
  NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v141);
  if ( v114 )
  {
    v18 = v122;
    v16 = v115;
LABEL_3:
    v23 = v21 | 0x200000;
    if ( !v18 )
      v23 = v21;
    return (unsigned int)GdiUpdateSprite(v16, v128, v125, v142, v118, v117, v124, v123, a9, v17, v23, v116);
  }
  return v24;
}

```

## disassembly

```asm
0x1400865c0  push    rbp
0x1400865c2  push    rbx
0x1400865c3  push    rsi
0x1400865c4  push    rdi
0x1400865c5  push    r12
0x1400865c7  push    r13
0x1400865c9  push    r14
0x1400865cb  push    r15
0x1400865cd  lea     rbp, [rsp-2A8h]
0x1400865d5  sub     rsp, 3A8h
0x1400865dc  mov     rax, cs:__security_cookie
0x1400865e3  xor     rax, rsp
0x1400865e6  mov     [rbp+2E0h+var_50], rax
0x1400865ed  mov     rax, [rbp+2E0h+arg_28]
0x1400865f4  mov     rbx, rcx
0x1400865f7  mov     r12d, [rbp+2E0h+arg_50]
0x1400865fe  mov     esi, r12d
0x140086601  mov     r15, [rbp+2E0h+arg_48]
0x140086608  and     esi, 200000h
0x14008660e  mov     r13, [rbp+2E0h+arg_60]
0x140086615  mov     [rbp+2E0h+var_340], rax
0x140086619  mov     rax, [rbp+2E0h+arg_38]
0x140086620  mov     [rbp+2E0h+var_318], rax
0x140086624  mov     rax, [rbp+2E0h+arg_20]
0x14008662b  mov     [rbp+2E0h+var_338], rax
0x14008662f  mov     rax, [rbp+2E0h+arg_30]
0x140086636  mov     [rbp+2E0h+var_310], rax
0x14008663a  mov     rax, [rbp+2E0h+arg_58]
0x140086641  mov     [rbp+2E0h+var_308], r8
0x140086645  mov     r8d, 88h; Size
0x14008664b  mov     [rbp+2E0h+var_2E8], rdx
0x14008664f  xor     edx, edx; Val
0x140086651  mov     [rbp+2E0h+var_350], rcx
0x140086655  lea     rcx, [rbp+2E0h+var_1E0]; void *
0x14008665c  mov     [rbp+2E0h+var_348], rax
0x140086660  mov     [rbp+2E0h+var_260], r9
0x140086667  mov     [rbp+2E0h+var_360], r15
0x14008666b  mov     [rbp+2E0h+var_2F0], r13
0x14008666f  mov     [rbp+2E0h+var_320], esi
0x140086672  call    memset_0
0x140086677  mov     [rsp+3E0h+var_378], 0
0x14008667f  mov     [rsp+3E0h+var_370], 0
0x140086687  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008668e  nop     dword ptr [rax+rax+00h]
0x140086693  btr     r12d, 15h
0x140086698  mov     [rbp+2E0h+var_330], rax
0x14008669c  cmp     [rbp+2E0h+arg_68], 0
0x1400866a3  mov     rdi, rax
0x1400866a6  jz      short loc_1400866C2
0x1400866a8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400866af  nop     dword ptr [rax+rax+00h]
0x1400866b4  cmp     qword ptr [rax+0E0h], 0
0x1400866bc  jnz     loc_1400867BC
0x1400866c2  mov     r10, [rbp+2E0h+var_348]
0x1400866c6  mov     eax, r12d
0x1400866c9  mov     r9, [rbp+2E0h+var_260]; struct OPTAPIDCOBJ *
0x1400866d0  bts     eax, 15h
0x1400866d4  mov     r8, [rbp+2E0h+var_308]; void *
0x1400866d8  test    esi, esi
0x1400866da  mov     rdx, [rbp+2E0h+var_2E8]; HWND
0x1400866de  mov     rcx, rbx; HDEV
0x1400866e1  mov     [rsp+3E0h+var_388], r10; struct tagRECT *
0x1400866e6  cmovz   eax, r12d
0x1400866ea  mov     [rsp+3E0h+var_390], eax; unsigned int
0x1400866ee  mov     eax, [rbp+2E0h+arg_40]
0x1400866f4  mov     [rsp+3E0h+var_398], r15; struct _BLENDFUNCTION *
0x1400866f9  mov     dword ptr [rsp+3E0h+var_3A0], eax; unsigned int
0x1400866fd  mov     rax, [rbp+2E0h+var_318]
0x140086701  mov     [rsp+3E0h+var_3A8], rax; struct tagPOINT *
0x140086706  mov     rax, [rbp+2E0h+var_310]
0x14008670a  mov     [rsp+3E0h+var_3B0], rax; struct OPTAPIDCOBJ *
0x14008670f  mov     rax, [rbp+2E0h+var_340]
0x140086713  mov     [rsp+3E0h+var_3B8], rax; struct tagSIZE *
0x140086718  mov     rax, [rbp+2E0h+var_338]
0x14008671c  mov     [rsp+3E0h+var_3C0], rax; struct tagPOINT *
0x140086721  call    ?GdiUpdateSprite@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@@Z; GdiUpdateSprite(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *)
0x140086726  mov     r14d, eax
0x140086729  jmp     short loc_140086795
0x14008672b  lea     rcx, [rbp+2E0h+var_2C0]
0x14008672f  call    ??1?$SEMOBJEXORSHARED@$06@@QEAA@XZ; SEMOBJEXORSHARED<7>::~SEMOBJEXORSHARED<7>(void)
0x140086734  cmp     [rbp+2E0h+var_2C8], 0
0x140086738  jz      short loc_14008677B
0x14008673a  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140086741  nop     dword ptr [rax+rax+00h]
0x140086746  lea     rcx, aSprite; "Sprite"
0x14008674d  mov     rbx, [rax]
0x140086750  lea     rdx, [rbx+410h]
0x140086757  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14008675e  nop     dword ptr [rax+rax+00h]
0x140086763  call    ??$GrepReleaseLockValidate@$05@@YAXXZ; GrepReleaseLockValidate<6>(void)
0x140086768  lea     rcx, [rbx+410h]
0x14008676f  call    cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x140086776  nop     dword ptr [rax+rax+00h]
0x14008677b  lea     rcx, [rbp+2E0h+var_268]
0x14008677f  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ; NEEDGRELOCK::vUnlock(void)
0x140086786  nop     dword ptr [rax+rax+00h]
0x14008678b  cmp     [rbp+2E0h+var_358], 0
0x14008678f  jnz     loc_140087497
0x140086795  mov     eax, r14d
0x140086798  mov     rcx, [rbp+2E0h+var_50]
0x14008679f  xor     rcx, rsp; StackCookie
0x1400867a2  call    __security_check_cookie
0x1400867a7  add     rsp, 3A8h
0x1400867ae  pop     r15
0x1400867b0  pop     r14
0x1400867b2  pop     r13
0x1400867b4  pop     r12
0x1400867b6  pop     rdi
0x1400867b7  pop     rsi
0x1400867b8  pop     rbx
0x1400867b9  pop     rbp
0x1400867ba  retn
0x1400867bc  xor     r14d, r14d
0x1400867bf  mov     [rbp+2E0h+var_358], 1
0x1400867c6  test    esi, esi
0x1400867c8  lea     rcx, [rbp+2E0h+var_268]
0x1400867cc  setz    dl
0x1400867cf  call    cs:__imp_?vLock@NEEDGRELOCK@@QEAAX_N@Z; NEEDGRELOCK::vLock(bool)
0x1400867d6  nop     dword ptr [rax+rax+00h]
0x1400867db  mov     [rbp+2E0h+var_2D0], rbx
0x1400867df  mov     [rbp+2E0h+var_2C8], r14d
0x1400867e3  test    esi, esi
0x1400867e5  jnz     loc_14008686F
0x1400867eb  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400867f2  nop     dword ptr [rax+rax+00h]
0x1400867f7  test    rax, rax
0x1400867fa  jz      loc_140087427
0x140086800  mov     rcx, [rax]
0x140086803  lea     rax, [rcx+8]
0x140086807  neg     rcx
0x14008680a  sbb     rcx, rcx
0x14008680d  and     rcx, rax
0x140086810  jz      short loc_140086824
0x140086812  cmp     [rcx+154h], r14d
0x140086819  jnz     short loc_14008686F
0x14008681b  cmp     [rcx+158h], r14d
0x140086822  jnz     short loc_14008686F
0x140086824  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008682b  nop     dword ptr [rax+rax+00h]
0x140086830  xor     r8d, r8d
0x140086833  lea     rcx, aSprite; "Sprite"
0x14008683a  mov     rbx, [rax]
0x14008683d  lea     rdx, [rbx+410h]
0x140086844  call    cs:__imp_EtwTraceGreLockAcquireSemaphoreExclusive
0x14008684b  nop     dword ptr [rax+rax+00h]
0x140086850  lea     rcx, [rbx+410h]
0x140086857  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14008685e  nop     dword ptr [rax+rax+00h]
0x140086863  call    ??$GrepAcquireLockValidate@$05@@YAXXZ; GrepAcquireLockValidate<6>(void)
0x140086868  mov     [rbp+2E0h+var_2C8], 1
0x14008686f  mov     rcx, [rdi]
0x140086872  add     rcx, 208h
0x140086879  test    esi, esi
0x14008687b  mov     [rbp+2E0h+var_2C0], rcx
0x14008687f  setnz   [rbp+2E0h+var_2B8]
0x140086883  test    esi, esi
0x140086885  jz      loc_140086DF8
0x14008688b  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140086892  nop     dword ptr [rax+rax+00h]
0x140086897  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x14008689c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400868a3  nop     dword ptr [rax+rax+00h]
0x1400868a8  cmp     [rax+0E0h], r14
0x1400868af  jz      loc_14008672B
0x1400868b5  mov     rbx, [rbp+2E0h+var_2E8]
0x1400868b9  test    rbx, rbx
0x1400868bc  jz      loc_1400872ED
0x1400868c2  xorps   xmm0, xmm0
0x1400868c5  xor     edi, edi
0x1400868c7  movups  [rbp+2E0h+Buffer], xmm0
0x1400868cb  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400868d2  nop     dword ptr [rax+rax+00h]
0x1400868d7  mov     qword ptr [rbp+2E0h+Buffer], rbx
0x1400868db  mov     rsi, rax
0x1400868de  mov     rbx, [rax+0E0h]
0x1400868e5  add     rbx, 48h ; 'H'
0x1400868e9  jz      short loc_1400868FA
0x1400868eb  mov     rcx, rbx
0x1400868ee  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x1400868f5  nop     dword ptr [rax+rax+00h]
0x1400868fa  mov     rcx, [rsi+0E0h]; Table
0x140086901  lea     rdx, [rbp+2E0h+Buffer]; Buffer
0x140086905  call    cs:__imp_RtlLookupElementGenericTable
0x14008690c  nop     dword ptr [rax+rax+00h]
0x140086911  test    rax, rax
0x140086914  jz      short loc_14008691A
0x140086916  mov     rdi, [rax+8]
0x14008691a  test    rbx, rbx
0x14008691d  jz      short loc_14008692E
0x14008691f  mov     rcx, rbx
0x140086922  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x140086929  nop     dword ptr [rax+rax+00h]
0x14008692e  test    rdi, rdi
0x140086931  jz      loc_14008672B
0x140086937  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008693e  nop     dword ptr [rax+rax+00h]
0x140086943  xor     r9d, r9d
0x140086946  mov     r8b, 0Fh
0x140086949  mov     rcx, rax
0x14008694c  mov     rdx, rdi
0x14008694f  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140086956  nop     dword ptr [rax+rax+00h]
0x14008695b  mov     rbx, rax
0x14008695e  test    rax, rax
0x140086961  jz      loc_14008672B
0x140086967  mov     eax, [rax+88h]
0x14008696d  test    al, 10h
0x14008696f  jnz     loc_140086DD5
0x140086975  xor     r15d, r15d
0x140086978  lea     rax, [rbx+58h]
0x14008697c  mov     [rsp+3E0h+var_380], r15b
0x140086981  mov     [rbp+2E0h+var_358], r15d
0x140086985  test    rax, rax
0x140086988  jz      short loc_140086999
0x14008698a  mov     rcx, rax
0x14008698d  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140086994  nop     dword ptr [rax+rax+00h]
0x140086999  mov     rsi, [rbx+90h]
0x1400869a0  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VSFMLOGICALSURFACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<SFMLOGICALSURFACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400869a7  mov     rax, [rbx]
0x1400869aa  lea     rdx, [rbp+2E0h+var_2B0]
0x1400869ae  xorps   xmm0, xmm0
0x1400869b1  mov     [rbp+2E0h+var_308], rax
0x1400869b5  lea     rcx, [rbp+2E0h+var_2B0]
0x1400869b9  mov     [rsp+3E0h+var_368], rsi
0x1400869be  mov     rdi, rsi
0x1400869c1  movups  [rbp+2E0h+var_2B0], xmm0
0x1400869c5  movups  [rbp+2E0h+var_2A0], xmm0
0x1400869c9  call    cs:__imp_PushThreadGuardedObject
0x1400869d0  nop     dword ptr [rax+rax+00h]
0x1400869d5  mov     [rbp+2E0h+var_290], r15
0x1400869d9  mov     [rbp+2E0h+var_288], 1
0x1400869e0  test    rsi, rsi
0x1400869e3  jz      short loc_140086A15
0x1400869e5  mov     r14, [rsi]
0x1400869e8  test    r14, r14
0x1400869eb  jz      short loc_140086A15
0x1400869ed  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400869f4  nop     dword ptr [rax+rax+00h]
0x1400869f9  xor     r9d, r9d
0x1400869fc  mov     r8b, 12h
0x1400869ff  mov     rcx, rax
0x140086a02  mov     rdx, r14
0x140086a05  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140086a0c  nop     dword ptr [rax+rax+00h]
0x140086a11  mov     [rbp+2E0h+var_290], rax
0x140086a15  lea     rax, [rsi+100h]
0x140086a1c  mov     qword ptr [rbp+2E0h+Buffer], rax
0x140086a20  test    rax, rax
0x140086a23  jz      short loc_140086A34
0x140086a25  mov     rcx, rax
0x140086a28  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140086a2f  nop     dword ptr [rax+rax+00h]
0x140086a34  mov     rax, [rbp+2E0h+var_348]
0x140086a38  test    rax, rax
0x140086a3b  jnz     loc_14008742E
0x140086a41  cmp     r12d, 2000000h
0x140086a48  jz      loc_1400870BD
0x140086a4e  mov     r14, [rbp+2E0h+var_360]
0x140086a52  mov     [rbp+2E0h+var_360], r14
0x140086a56  bt      r12d, 1Dh
0x140086a5b  jb      loc_1400870E8
0x140086a61  bt      r12d, 1Eh
0x140086a66  jnb     loc_1400871EA
0x140086a6c  mov     eax, [rbx+50h]
0x140086a6f  lea     r14, [rbx+4Ch]
0x140086a73  mov     r12d, [rbx+48h]
0x140086a77  mov     [rbp+2E0h+arg_40], eax
0x140086a7d  mov     [rbp+2E0h+var_360], r14
0x140086a81  mov     eax, 2
0x140086a86  mov     ecx, r12d
0x140086a89  mov     [rsp+3E0h+var_374], eax
0x140086a8d  and     ecx, eax
0x140086a8f  jnz     loc_140086E09
0x140086a95  mov     [rbx+48h], r12d
0x140086a99  mov     r15d, 1
0x140086a9f  mov     [rsp+3E0h+var_37C], r15d
0x140086aa4  test    ecx, ecx
0x140086aa6  jnz     loc_140086E31
0x140086aac  test    r12b, 1
0x140086ab0  jnz     loc_1400871F8
0x140086ab6  test    r15d, r15d
0x140086ab9  jz      loc_140086C16
0x140086abf  mov     rcx, [rbp+2E0h+var_338]
0x140086ac3  test    rcx, rcx
0x140086ac6  jz      short loc_140086AEA
0x140086ac8  mov     r8d, [rcx+4]
0x140086acc  mov     ecx, [rcx]
0x140086ace  mov     eax, [rbx+38h]
0x140086ad1  mov     [rbx+38h], ecx
0x140086ad4  sub     ecx, eax
0x140086ad6  add     [rbx+40h], ecx
0x140086ad9  mov     eax, r8d
0x140086adc  sub     eax, [rbx+3Ch]
0x140086adf  add     [rbx+44h], eax
0x140086ae2  mov     rcx, [rbp+2E0h+var_338]
0x140086ae6  mov     [rbx+3Ch], r8d
0x140086aea  mov     eax, [rdi+0FCh]
0x140086af0  test    al, 1
0x140086af2  jz      loc_1400870F2
  ... truncated ...
```
