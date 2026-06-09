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
  __int64 v48; // rdx
  Gre::Base *v49; // rcx
  __int64 y; // r8
  struct tagPOINT *v51; // r9
  __int64 v52; // r14
  struct Gre::Base::SESSION_GLOBALS *v53; // rax
  __int64 v54; // r8
  int *v55; // r14
  unsigned __int64 v56; // rcx
  LONG x; // ecx
  int v58; // eax
  __int64 v59; // r8
  LONG v60; // edx
  LONG v61; // ecx
  int v62; // eax
  __int64 UserSessionState; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r15
  unsigned int v67; // esi
  void *v68; // r13
  void *v69; // r14
  struct Gre::Base::SESSION_GLOBALS *v70; // rax
  int v71; // eax
  _DWORD *v72; // rcx
  int v73; // r15d
  int v74; // r13d
  void *v75; // rsi
  int v76; // r8d
  int v77; // eax
  int v78; // edx
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
      v52 = *v46;
      if ( *v46 )
      {
        v53 = Gre::Base::Globals(v49);
        LOBYTE(v54) = 18;
        v136 = HmgLock(v53, v52, v54);
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
      v55 = &v110;
      v110 = 33488896;
      v21 = 570425346;
      v114 = &v110;
      if ( v118 || (v91 = 0, v119) )
        v91 = 1;
      vSpDwmUpdateSpriteVisibility((struct DWMSPRITE *)v44, v91);
    }
    else
    {
      v55 = v114;
      if ( (a11 & 0x20000000) == 0 )
      {
        if ( (a11 & 0x40000000) != 0 || !v21 )
        {
          v55 = (int *)(v44 + 76);
          v21 = *(_DWORD *)(v44 + 72);
          a9 = *(_DWORD *)(v44 + 80);
        }
        v114 = v55;
LABEL_44:
        v111 = 2;
        v56 = v21 & 2;
        if ( (v21 & 2) != 0 && (!v55 || (*((_BYTE *)v55 + 3) & 1) != 0 && (*((_DWORD *)v46 + 63) & 1) != 0) )
        {
          v109 = 0;
          goto LABEL_63;
        }
        *(_DWORD *)(v44 + 72) = v21;
        v45 = 1;
        v109 = 1;
        if ( (v21 & 2) != 0 )
        {
          if ( *(_BYTE *)(v44 + 79) != *((_BYTE *)v55 + 3) )
          {
            v71 = bSpDwmCreateLogicalSurface(v116, (struct DWMSPRITE *)v44, (struct SFMLOGICALSURFACE *)v46, 0, &v113);
            FirstLSurf = v113;
            v45 = v71;
            v109 = v71;
          }
          *(_DWORD *)(v44 + 76) = *v55;
          v56 = (unsigned int)*v55;
          *((_DWORD *)FirstLSurf + 61) |= 0x40u;
          *((_DWORD *)FirstLSurf + 60) = v56;
        }
        if ( (v21 & 1) != 0 )
        {
          *(_DWORD *)(v44 + 80) = a9;
          v97 = v46[23];
          if ( v97 )
          {
            if ( (*(_DWORD *)(v97 + 140) & 1) != 0
              && !(unsigned int)bRemoteDriverNeedsDeviceBitmaps((struct PDEVOBJ *)&v131) )
            {
              v98 = v46[23];
              if ( PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v131) )
              {
                v99 = *(_DWORD *)(v98 + 140);
                if ( (v99 & 0x20) == 0 )
                {
                  v100 = *(void **)(v98 + 8);
                  *(_DWORD *)(v98 + 140) = v99 | 0x20;
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
        v56 = (unsigned __int64)v119;
        if ( v119 )
        {
          y = (unsigned int)v119->y;
          x = v119->x;
          v58 = *(_DWORD *)(v44 + 56);
          *(_DWORD *)(v44 + 56) = v119->x;
          *(_DWORD *)(v44 + 64) += x - v58;
          *(_DWORD *)(v44 + 68) += y - *(_DWORD *)(v44 + 60);
          v56 = (unsigned __int64)v119;
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
            if ( v56 && v118 )
            {
              updated = bSpDwmUpdateDragRectShape(v116, (struct DWMSPRITE *)v44, FirstLSurf, v51, v118, &v112, &v113);
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
              v56 = 0;
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
                        *(struct PALETTE **)(v59 + 176),
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
              UserSessionState = W32GetUserSessionState(v56, v48, y, v51);
              v19 = (struct tagMINIWINDOWINFO *)v150;
              v128 = (struct tagMINIWINDOWINFO *)v150;
              v153 = *(_QWORD *)(UserSessionState + 18760);
            }
            if ( v45 && !v108 && (v19 || (*((_DWORD *)FirstLSurf + 63) & 8) != 0) )
            {
              if ( (*((_DWORD *)FirstLSurf + 63) & 8) != 0 )
                SFMLOGICALSURFACE::StartSfmStateTracking(FirstLSurf, v116, *((struct SfmState **)v120 + 543), (int)v51);
              v72 = (_DWORD *)*((_QWORD *)FirstLSurf + 23);
              if ( v72 )
              {
                v73 = v72[8];
                v74 = v72[9];
                if ( (v72[35] & 1) == 0 )
                  v111 = (v72[34] & 0x800) != 0;
              }
              else
              {
                v73 = 0;
                v111 = 0;
                v74 = 0;
              }
              *(_QWORD *)&v127.left = *(_QWORD *)(v44 + 104);
              LODWORD(v113) = *(_DWORD *)(v44 + 116);
              *(_QWORD *)(v44 + 104) = 0;
              v122 = *((_DWORD *)FirstLSurf + 63);
              v121 = *(_DWORD *)(v44 + 136);
              v141 = *(_QWORD *)FirstLSurf;
              v120 = *(struct Gre::Base::SESSION_GLOBALS **)v44;
              v75 = (void *)UserReferenceDwmApiPort(v72);
              IncrementDWMWindowUniqueness();
              if ( v75 )
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
                v79 = v78 | v76 | (2 * (v77 | v122 & 1 | (4 * (v121 & 0xEu))));
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
                *(_DWORD *)&v158[4] = v73;
                *(_DWORD *)&v158[8] = v74;
                SessionState = W32GetSessionState(v79);
                if ( (int)v113 < 1
                  || (v102 = *(_QWORD *)(SessionState + 96),
                      v103 = *(unsigned int *)(v102 + 716),
                      (unsigned int)v103 >= 0x14) )
                {
                  EtwUpdateEvent(v120);
                  LpcRequestPort(v75, &v154);
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
                ObfDereferenceObject(v75);
              }
            }
            if ( (_QWORD)Buffer )
              GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)Buffer);
            SFMLOGICALSURFACEREF_vDestructor(v135);
            PopThreadGuardedObject(v135);
            v65 = *((_QWORD *)FirstLSurf + 23);
            if ( v65 )
              v66 = *(_QWORD *)(v65 + 8);
            else
              v66 = 0;
            v67 = v112;
            v68 = *(void **)v44;
            if ( v65 && (*(_DWORD *)(v65 + 140) & 1) != 0 )
              v67 = v112 & 0xFFFFFFFE;
            if ( (v67 & 1) != 0 && (unsigned __int8)bShouldUseSfmTokenArray(*((unsigned int *)FirstLSurf + 63)) )
            {
              GreAddLogicalSurfaceToDirtyQueue(*(_QWORD *)FirstLSurf, 1, v66);
              v67 &= ~1u;
            }
            if ( v67 )
            {
              v69 = (void *)UserReferenceDwmApiPort(v64);
              IncrementDWMWindowUniqueness();
              if ( v69 )
              {
                memset_0(v135, 0, 0x40u);
                LODWORD(v135[0]) = 4194328;
                WORD2(v135[0]) = 0x8000;
                v137 = 1073741828;
                v139 = v68;
                v138 = v67;
                v140 = v66;
                EtwUpdateEvent(v68);
                LpcRequestPort(v69, v135);
                ObfDereferenceObject(v69);
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
        y = a16;
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
        v56 = *((unsigned int *)FirstLSurf + 63);
        if ( (*((_DWORD *)FirstLSurf + 63) & 0x41) == 1 )
        {
          v56 = (unsigned int)v56 | 0x40;
          *((_DWORD *)FirstLSurf + 63) = v56;
        }
        v48 = *((_QWORD *)FirstLSurf + 23);
        if ( v48 && (*(_DWORD *)(v48 + 140) & 1) == 0 && !*(_QWORD *)(v48 + 272) )
        {
          v56 = (unsigned int)v56 | 8;
          *((_DWORD *)FirstLSurf + 63) = v56;
        }
        goto LABEL_63;
      }
    }
    v21 &= ~0x20000000u;
    goto LABEL_44;
  }
LABEL_89:
  v70 = Gre::Base::Globals(v43);
  DEC_SHARE_REF_CNT(v70, v44);
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
