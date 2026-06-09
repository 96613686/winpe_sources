# bGetRealizedBrush(BRUSH *,EBRUSHOBJ *,int (*)(_BRUSHOBJ *,_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_XLATEOBJ *,ulong))

- ea: `0x1401290b4`
- end: `0x140129d32`
- name: `?bGetRealizedBrush@@YAHPEAVBRUSH@@PEAVEBRUSHOBJ@@P6AHPEAU_BRUSHOBJ@@PEAU_SURFOBJ@@33PEAU_XLATEOBJ@@K@Z@Z`
- size: `3198`
- prototype: `int(struct BRUSH *, struct EBRUSHOBJ *, int (*)(struct _BRUSHOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _XLATEOBJ *, unsigned int))`
- caller_count: `3`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140128694`
- `0x140128c60`
- `0x14012a2e0`

## callees

- `0x14005fb0c`
- `0x14006f0dc`
- `0x14007a824`
- `0x14007a930`
- `0x14008c4a4`
- `0x14008d8bc`
- `0x1400950c8`
- `0x140096604`
- `0x140127ba0`
- `0x1401290b4`
- `0x1401399b0`
- `0x14013b358`
- `0x14013b410`
- `0x14013d5bc`
- `0x14013d6c0`
- `0x14013db54`
- `0x140155f3c`
- `0x1401562d8`
- `0x1401b2330`
- `0x140294c60`
- `0x140296924`
- `0x1402fb8c4`
- `0x140302124`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401290eb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140129179`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401291e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140129368`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14012940c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401295f0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401290eb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140129179`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401291e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140129368`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14012940c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401295f0`
- `win32kbase!HmgShareLock` at `0x140129202`
- `win32kbase!HmgShareLock` at `0x140129380`
- `win32kbase!HmgShareLock` at `0x140129202`
- `win32kbase!HmgShareLock` at `0x140129380`
- `win32kbase!PushThreadGuardedObject` at `0x140129128`
- `win32kbase!PushThreadGuardedObject` at `0x140129128`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140129336`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1401293c1`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14012959e`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140129336`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1401293c1`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14012959e`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z` at `0x14012919d`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z` at `0x14012919d`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x140129319`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1401293a4`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x14012957e`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1401296d8`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x140129868`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x140129319`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1401293a4`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x14012957e`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1401296d8`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x140129868`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14012974b`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x140129769`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14012974b`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x140129769`
- `win32kbase!rgbFromColorref` at `0x140129801`
- `win32kbase!rgbFromColorref` at `0x140129801`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14012950d`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1401299e2`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140129b52`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14012950d`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1401299e2`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140129b52`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x140129999`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x140129b1b`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x140129999`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x140129b1b`
- `win32kbase!?hFindIcmDIB@BRUSH@@QEAAPEAUHBITMAP__@@PEAX@Z` at `0x140129c6e`
- `win32kbase!?hFindIcmDIB@BRUSH@@QEAAPEAUHBITMAP__@@PEAX@Z` at `0x140129c6e`
- `win32kbase!AllocThreadBufferWithTag` at `0x1401295d0`
- `win32kbase!AllocThreadBufferWithTag` at `0x1401295d0`
- `win32kbase!Win32FreePool` at `0x140129a26`
- `win32kbase!Win32FreePool` at `0x140129a26`

## pseudocode

```c
__int64 __fastcall bGetRealizedBrush(
        struct BRUSH *a1,
        struct EBRUSHOBJ *a2,
        __int64 (__fastcall *a3)(struct _BRUSHOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _XLATEOBJ *, unsigned int))
{
  struct Gre::Base::SESSION_GLOBALS *v6; // r12
  int v7; // r8d
  __int64 v8; // r15
  struct Gre::Base::SESSION_GLOBALS *v9; // rsi
  char v10; // r14
  Gre::Base *v11; // rcx
  __int64 v12; // rax
  unsigned __int8 v13; // bl
  int v14; // r12d
  int v15; // eax
  struct Gre::Base::SESSION_GLOBALS *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // r9
  __int64 v23; // r10
  __int64 v24; // r8
  int inited; // eax
  struct _XLATEOBJ *v26; // r15
  __int64 v27; // rcx
  __int64 v28; // r8
  unsigned int v29; // ebx
  __int64 v31; // rbx
  struct Gre::Base::SESSION_GLOBALS *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r13
  struct _XLATEOBJ *v35; // r9
  __int64 v36; // r8
  HDEV v37; // rax
  __int64 (__fastcall *v38)(struct _BRUSHOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _XLATEOBJ *, unsigned int); // r13
  __int64 v39; // rcx
  HDEV v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rdx
  ULONG v43; // eax
  int v44; // eax
  Gre::Base *v45; // rcx
  __int64 v46; // rbx
  unsigned int NearestIndexFromColorref; // r13d
  unsigned int *v48; // r8
  int v49; // r12d
  int v50; // eax
  int v51; // eax
  bool v52; // zf
  struct Gre::Base::SESSION_GLOBALS *v53; // r13
  bool v54; // dl
  HPALETTE *v55; // rax
  HPALETTE *v56; // r12
  char v57; // cl
  HDEV v58; // rax
  int v59; // edx
  int v60; // ecx
  int v61; // edx
  int v62; // edx
  int v63; // edx
  int v64; // edx
  int v65; // edx
  char v66; // cl
  __int128 *v67; // rax
  __int128 v68; // xmm0
  __int64 v69; // xmm1_8
  __int64 HalftoneBrush; // rcx
  __int64 v71; // rax
  void *v72; // rbx
  void *v73; // rdx
  int v74; // eax
  HBITMAP IcmDIB; // rax
  int v76; // edx
  char v77[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v78; // [rsp+68h] [rbp-98h] BYREF
  HBITMAP v79; // [rsp+70h] [rbp-90h] BYREF
  HDEV hdev; // [rsp+78h] [rbp-88h] BYREF
  __int64 v81; // [rsp+80h] [rbp-80h] BYREF
  struct Gre::Base::SESSION_GLOBALS *v82; // [rsp+88h] [rbp-78h] BYREF
  __int64 v83; // [rsp+90h] [rbp-70h] BYREF
  char v84; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v85)(struct _BRUSHOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _XLATEOBJ *, unsigned int); // [rsp+A0h] [rbp-60h]
  _QWORD v86[3]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v87; // [rsp+C0h] [rbp-40h]
  __int128 v88; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v89; // [rsp+D8h] [rbp-28h]
  _DWORD v90[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v91; // [rsp+F0h] [rbp-10h]
  struct Gre::Base::SESSION_GLOBALS **v92; // [rsp+F8h] [rbp-8h]
  struct _SURFOBJ *v93; // [rsp+100h] [rbp+0h]
  _OWORD v94[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v95; // [rsp+128h] [rbp+28h]
  __int128 v96; // [rsp+130h] [rbp+30h] BYREF
  __int64 v97; // [rsp+140h] [rbp+40h]

  v85 = a3;
  v6 = Gre::Base::Globals(a1);
  v82 = v6;
  v87 = *((_DWORD *)a1 + 20);
  if ( v87 == 12 )
    return 0;
  memset(v94, 0, sizeof(v94));
  PushThreadGuardedObject(
    v94,
    v94,
    UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
  v95 = 0;
  v81 = 0;
  SURFMEM::SURFMEM(v86, 2);
  v8 = (unsigned int)(v7 + 1);
  hdev = *(HDEV *)(*((_QWORD *)a2 + 10) + 48LL);
  if ( ((unsigned __int8)*((_DWORD *)hdev + 10) & (unsigned __int8)(v7 + 1)) != 0 && a3 == EngRealizeBrush )
  {
    v9 = Gre::Base::Globals((Gre::Base *)EngRealizeBrush);
    GreAcquireSemaphoreShared<1,>(v9);
    v10 = v8;
  }
  else
  {
    v10 = v7;
    v9 = Gre::Base::Globals((Gre::Base *)EngRealizeBrush);
  }
  NEEDGRELOCK::vLock((NEEDGRELOCK *)v77, (struct PDEVOBJ *)&hdev);
  v12 = *((unsigned int *)a1 + 20);
  v13 = 6;
  if ( (unsigned int)v12 < 6 )
  {
    v31 = *((_QWORD *)hdev + v12 + 182);
    v32 = Gre::Base::Globals((Gre::Base *)hdev);
    LOBYTE(v33) = 5;
    v95 = HmgShareLock(v32, v31, v33, 0);
    v34 = v95;
    if ( !v95 )
      goto LABEL_27;
    v46 = AllocThreadBufferWithTag(96, 1953265735, 0);
    if ( !v46 )
    {
      v81 = 0;
      goto LABEL_27;
    }
    v93 = (struct _SURFOBJ *)(v34 + 24);
    *(_DWORD *)v46 = v8 + _InterlockedExchangeAdd((volatile signed __int32 *)Gre::Base::Globals(v45) + 944, v8);
    *(_QWORD *)(v46 + 4) = 2;
    *(_QWORD *)(v46 + 16) = v46 + 84;
    *(_DWORD *)(v46 + 76) = 0;
    *(_DWORD *)(v46 + 12) = 2;
    *(_DWORD *)(v46 + 36) = -1;
    *(_QWORD *)(v46 + 40) = 0;
    *(_QWORD *)(v46 + 48) = 0;
    *(_QWORD *)(v46 + 56) = 0;
    NearestIndexFromColorref = *((_DWORD *)a2 + 13);
    v81 = v46;
    if ( (unsigned int)EBRUSHOBJ::bIsCMYKColor(a2) )
    {
      v49 = *((_DWORD *)a2 + 6);
      *v48 = NearestIndexFromColorref;
      *(_DWORD *)(v46 + 88) = v49;
      XLATE::vCheckForICM((XLATE *)v46, *((void **)a2 + 8), *((_DWORD *)a2 + 18));
    }
    else
    {
      NearestIndexFromColorref = ulGetNearestIndexFromColorref(
                                   *((_QWORD *)a2 + 11),
                                   *((_QWORD *)a2 + 12),
                                   NearestIndexFromColorref,
                                   (unsigned int)v8);
      v50 = ulGetNearestIndexFromColorref(
              *((_QWORD *)a2 + 11),
              *((_QWORD *)a2 + 12),
              *((unsigned int *)a2 + 6),
              (unsigned int)v8);
      v49 = v50;
      if ( *(_DWORD *)(*((_QWORD *)a2 + 10) + 96LL) == (_DWORD)v8
        && *(_DWORD *)(*((_QWORD *)a2 + 11) + 28LL)
        && *((_DWORD *)a2 + 13) != *((_DWORD *)a2 + 6)
        && NearestIndexFromColorref == v50 )
      {
        v49 = v8 - NearestIndexFromColorref;
      }
      *(_DWORD *)(v46 + 84) = NearestIndexFromColorref;
      *(_DWORD *)(v46 + 88) = v49;
      XLATE::vCheckForICM((XLATE *)v46, *((void **)a2 + 8), *((_DWORD *)a2 + 18));
      XLATE::vCheckForTrivial((XLATE *)v46);
    }
    v26 = (struct _XLATEOBJ *)v46;
    *(_QWORD *)(v46 + 40) = *((_QWORD *)v82 + 488);
    *(_QWORD *)(v46 + 48) = *((_QWORD *)a2 + 11);
    *(_QWORD *)(v46 + 56) = *((_QWORD *)a2 + 12);
    *(_DWORD *)(v46 + 76) |= 0x100u;
    *(_DWORD *)(v46 + 28) = NearestIndexFromColorref;
    *(_DWORD *)(v46 + 32) = v49;
    goto LABEL_21;
  }
  v93 = 0;
  if ( (unsigned int)v12 < 0xC )
  {
    if ( (unsigned int)EBRUSHOBJ::bIsCMYKColor(a2) )
      goto LABEL_52;
    v36 = *((unsigned int *)a2 + 6);
    if ( (v36 & 0x1000000) != 0 )
    {
      LODWORD(v36) = rgbFromColorref(*((_QWORD *)a2 + 11), *((_QWORD *)a2 + 12), v36);
      *((_DWORD *)a2 + 6) = v36;
      v35 = 0;
    }
    v37 = hdev;
    v38 = v85;
    if ( ((_DWORD)hdev[452] & 0x200000) != 0 && v85 != EngRealizeBrush )
    {
      v51 = v85(
              (struct _BRUSHOBJ *)a2,
              (struct _SURFOBJ *)((*((_QWORD *)a2 + 10) + 24LL) & -(__int64)(*((_QWORD *)a2 + 10) != 0)),
              0,
              0,
              v35,
              (unsigned int)v36 | 0x80000000);
      v35 = 0;
      if ( v51 )
      {
        NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v77);
LABEL_53:
        if ( v10 )
          GreReleaseSemaphoreShared<1,>(v9);
LABEL_55:
        SURFMEM::~SURFMEM((SURFMEM *)v86);
        EXLATEOBJ::vAltUnlock((EXLATEOBJ *)&v81);
        SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v94);
        return (unsigned int)v8;
      }
      v37 = hdev;
    }
    v39 = *((_QWORD *)a2 + 10);
    v88 = 0;
    v89 = 0;
    if ( *(_DWORD *)(v39 + 96) == (_DWORD)v8 )
      LODWORD(v88) = v8;
    else
      LODWORD(v88) = v37[523];
    if ( !*((_WORD *)v37 + 1048) )
      goto LABEL_52;
    if ( *((_WORD *)v37 + 1049) == (_WORD)v35 )
      goto LABEL_52;
    DWORD1(v88) = *((unsigned __int16 *)v37 + 1048);
    DWORD2(v88) = *((unsigned __int16 *)v37 + 1049);
    *(_QWORD *)&v89 = v35;
    DWORD2(v89) = v8;
    if ( !SURFMEM::bCreateDIB(
            (SURFMEM *)v86,
            (struct _DEVBITMAPINFO *)&v88,
            0,
            0,
            (unsigned int)v35,
            v35,
            (unsigned __int64)v35,
            (_DWORD)v35,
            v8,
            (_DWORD)v35) )
      goto LABEL_52;
    v40 = hdev;
    v41 = *((unsigned int *)a2 + 6);
    v42 = (unsigned int)v8 + (*(_DWORD *)(*((_QWORD *)a2 + 10) + 96LL) == (_DWORD)v8);
    if ( *((_QWORD *)hdev + 348) )
    {
      if ( ((_DWORD)hdev[10] & 0x8000) == 0 )
        v40 = (HDEV)*((_QWORD *)hdev + 223);
      v43 = (*((__int64 (__fastcall **)(HDEV, __int64, __int64, _QWORD))hdev + 348))(
              v40,
              v42,
              v41,
              *(_QWORD *)(v86[0] + 72LL));
    }
    else
    {
      v43 = EngDitherColor(hdev, v42, v41, *(ULONG **)(v86[0] + 72LL));
    }
    v44 = v43 - v8;
    if ( !v44 )
    {
      v26 = (struct _XLATEOBJ *)((char *)v6 + 4664);
      goto LABEL_21;
    }
    if ( v44 != (_DWORD)v8 )
    {
LABEL_52:
      NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v77);
      LODWORD(v8) = 0;
      goto LABEL_53;
    }
    v52 = v38 == EngRealizeBrush;
    v53 = v6;
    if ( !v52 || (unsigned __int8)GrepIsLockOwnedByCurrentThread<1,Gre::Base::SESSION_GLOBALS>(v6) )
      v54 = 0;
    else
      v54 = v8;
    NEEDDYNAMICMODECHANGESHARELOCK::NEEDDYNAMICMODECHANGESHARELOCK((NEEDDYNAMICMODECHANGESHARELOCK *)&v83, v54);
    LODWORD(v79) = v85 == EngRealizeBrush;
    HTSEMOBJ::vAcquire((HTSEMOBJ *)&v79);
    if ( PDEVOBJ::pDevHTInfo((PDEVOBJ *)&hdev) || (unsigned int)PDEVOBJ::bEnableHalftone((PDEVOBJ *)&hdev, 0) )
    {
      v55 = (HPALETTE *)PDEVOBJ::pDevHTInfo((PDEVOBJ *)&hdev);
      LODWORD(v82) = *((_DWORD *)a2 + 6);
      v56 = v55;
      v57 = 0;
      v92 = &v82;
      v58 = hdev;
      LODWORD(v78) = 0;
      v91 = v8;
      v90[0] = 262400;
      v52 = ((_DWORD)hdev[591] & 0x100) == 0;
      v59 = (_DWORD)hdev[591] & 0x100;
      v90[1] = 255;
      if ( v52 )
        v57 = 2;
      LOBYTE(v78) = v57;
      v60 = *((_DWORD *)a2 + 18);
      if ( (v60 & 4) != 0 || (v60 & 0x20) == 0 && (v60 & 3) != 0 )
        LOBYTE(v78) = v59 != 0 ? 16 : 18;
      if ( __PAIR64__(*((unsigned __int16 *)v56 + 5), *((unsigned __int16 *)v56 + 4)) != *(_QWORD *)((char *)&v88 + 4) )
      {
        SURFACE::bDeleteSurface(v86[0], v53, 0);
        DWORD1(v88) = *((unsigned __int16 *)v56 + 4);
        DWORD2(v88) = *((unsigned __int16 *)v56 + 5);
        if ( !SURFMEM::bCreateDIB((SURFMEM *)v86, (struct _DEVBITMAPINFO *)&v88, 0, 0, 0, 0, 0, 0, v8, 0) )
          goto LABEL_130;
        v58 = hdev;
      }
      v61 = *((_DWORD *)v58 + 590);
      if ( v61 )
      {
        v62 = v61 - 2;
        if ( v62 )
        {
          v63 = v62 - v8;
          if ( v63 )
          {
            v64 = v63 - v8;
            if ( v64 )
            {
              v65 = v64 - v8;
              if ( v65 )
              {
                if ( v65 != 2 )
                  goto LABEL_130;
              }
              else
              {
                v13 = -3;
              }
            }
            else
            {
              v13 = -2;
            }
          }
          else
          {
            v13 = -1;
          }
        }
        else
        {
          v13 = 2;
        }
      }
      else
      {
        v13 = v8;
      }
      v66 = *((_BYTE *)v58 + 2352);
      v67 = (__int128 *)*((_QWORD *)a2 + 7);
      BYTE3(v78) = v66;
      BYTE1(v78) = v13;
      v68 = *v67;
      BYTE2(v78) = 4;
      v96 = v68;
      v69 = *((_QWORD *)v67 + 2);
      WORD5(v96) = 10000;
      v97 = v69;
      *(_DWORD *)((char *)&v96 + 6) = 655370000;
      if ( v13 != (_DWORD)v88
        && (v13 != 0xFF || (_DWORD)v88 != 2)
        && (v13 != 0xFE || (_DWORD)v88 != 3)
        && (v13 != 0xFD || (_DWORD)v88 != 4) )
      {
        TraceLoggingWriteUnsupportedGdiUsage(24, (unsigned int)v88, v13);
      }
      HalftoneBrush = (unsigned int)HT_CreateHalftoneBrush((_DWORD)v56, (unsigned int)&v96, (unsigned int)v90, v78, 0);
      v71 = v86[0];
      if ( (int)HalftoneBrush <= *(_DWORD *)(v86[0] + 64LL) )
      {
LABEL_125:
        if ( (int)HT_CreateHalftoneBrush((_DWORD)v56, (unsigned int)&v96, (unsigned int)v90, v78, *(_QWORD *)(v71 + 72)) <= 0 )
        {
          HTSEMOBJ::vRelease((HTSEMOBJ *)&v79);
          if ( v84 )
            GreReleaseSemaphoreShared<1,>(v83);
          goto LABEL_52;
        }
        if ( ((_DWORD)hdev[10] & 0x200) != 0 )
        {
          v26 = (struct _XLATEOBJ *)((char *)v53 + 4664);
        }
        else
        {
          EPALOBJ::EPALOBJ((EPALOBJ *)&v78, *v56);
          if ( !(unsigned int)EXLATEOBJ::bInitXlateObj(
                                &v81,
                                *((_QWORD *)a2 + 8),
                                *((unsigned int *)a2 + 18),
                                v78,
                                *(_QWORD *)(*((_QWORD *)a2 + 10) + 176LL),
                                *((_QWORD *)a2 + 12),
                                *((_QWORD *)a2 + 12),
                                *((_DWORD *)a2 + 12),
                                *((_DWORD *)a2 + 13),
                                0xFFFFFF,
                                0) )
          {
            EPALOBJ::~EPALOBJ((EPALOBJ *)&v78);
            goto LABEL_130;
          }
          v26 = (struct _XLATEOBJ *)v81;
          EPALOBJ::~EPALOBJ((EPALOBJ *)&v78);
        }
        HTSEMOBJ::vRelease((HTSEMOBJ *)&v79);
        if ( v84 )
          GreReleaseSemaphoreShared<1,>(v83);
        goto LABEL_21;
      }
      v72 = (void *)PALLOCMEM(HalftoneBrush, 1835167815);
      if ( v72 )
      {
        SURFACE::bDeleteSurface(v86[0], v53, 0);
        if ( SURFMEM::bCreateDIB((SURFMEM *)v86, (struct _DEVBITMAPINFO *)&v88, v72, 0, 0, 0, 0, 0, v8, 0) )
        {
          *(_BYTE *)(v86[0] + 736LL) = v8;
          v71 = v86[0];
          goto LABEL_125;
        }
        Win32FreePool(v72);
      }
    }
LABEL_130:
    HTSEMOBJ::vRelease((HTSEMOBJ *)&v79);
    if ( v84 )
      GreReleaseSemaphoreShared<1,>(v83);
    NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v77);
    if ( v10 )
      GreReleaseSemaphoreShared<1,>(v9);
    LODWORD(v8) = 0;
    goto LABEL_55;
  }
  v14 = 0;
  v79 = (HBITMAP)*((_QWORD *)a1 + 3);
  v15 = *((_DWORD *)a2 + 18);
  if ( ((unsigned __int8)v15 & (unsigned __int8)v8) != 0 )
  {
    v73 = (void *)*((_QWORD *)a2 + 8);
    if ( v73 )
    {
      v74 = *((_DWORD *)a1 + 10);
      if ( (v74 & 0x80u) == 0 )
      {
        if ( (v74 & 0x20000) == 0 )
          goto LABEL_10;
      }
      else
      {
        if ( *((_DWORD *)a1 + 21) )
          goto LABEL_10;
        IcmDIB = BRUSH::hFindIcmDIB(a1, v73);
        if ( !IcmDIB )
          goto LABEL_10;
        v79 = IcmDIB;
      }
    }
    else if ( (unsigned int)EBRUSHOBJ::bIsCMYKColor(a2) )
    {
      goto LABEL_10;
    }
    v14 = v8;
    goto LABEL_10;
  }
  if ( (v15 & 6) != 0 )
    v14 = v8;
LABEL_10:
  v16 = Gre::Base::Globals(v11);
  LOBYTE(v17) = 5;
  v18 = HmgShareLock(v16, v79, v17, (unsigned int)v8);
  v95 = v18;
  v19 = v18;
  if ( !v18 )
    goto LABEL_27;
  v20 = *(_QWORD *)(v18 + 176);
  v21 = *((_DWORD *)a1 + 10);
  v22 = *((_QWORD *)a2 + 10);
  if ( (v21 & 0x1000) == 0 )
  {
    if ( (v21 & 0x2000) != 0 )
    {
      if ( *(_DWORD *)(v19 + 96) != *(_DWORD *)(v22 + 96) )
        goto LABEL_27;
      v26 = (struct _XLATEOBJ *)((char *)v82 + 4664);
      goto LABEL_21;
    }
    if ( (*(_WORD *)(v19 + 100) || *(_QWORD *)(v19 + 24)) && *(HDEV *)(v19 + 48) != hdev )
      goto LABEL_27;
    if ( v20 )
      goto LABEL_16;
    v76 = *(_DWORD *)(v19 + 96);
    if ( v76 == *((_DWORD *)hdev + 523) )
    {
      if ( ((_DWORD)hdev[539] & 0x100) == 0 )
      {
        v20 = *((_QWORD *)hdev + 224);
LABEL_16:
        if ( v14 )
        {
          v23 = *((_QWORD *)a2 + 8);
          v24 = *((unsigned int *)a2 + 18);
        }
        else
        {
          v23 = 0;
          v24 = 0;
        }
        inited = EXLATEOBJ::bInitXlateObj(
                   &v81,
                   v23,
                   v24,
                   v20,
                   *(_QWORD *)(v22 + 176),
                   *((_QWORD *)a2 + 12),
                   *((_QWORD *)a2 + 12),
                   *((_DWORD *)a2 + 12),
                   *((_DWORD *)a2 + 13),
                   0xFFFFFF,
                   0);
        goto LABEL_19;
      }
    }
    else
    {
      if ( v76 == *((_DWORD *)a2 + 19) )
      {
        v20 = *((_QWORD *)a2 + 13);
        goto LABEL_16;
      }
      if ( v76 == 3 )
      {
        if ( ((_DWORD)hdev[539] & 0x100) == 0 )
        {
          v20 = *((_QWORD *)v82 + 486);
          goto LABEL_16;
        }
      }
      else if ( ((_DWORD)hdev[10] & 0x20000) == 0 )
      {
        goto LABEL_27;
      }
    }
    v20 = 0;
    goto LABEL_16;
  }
  inited = EXLATEOBJ::bMakeXlate(
             &v81,
             *(_QWORD *)(v20 + 112),
             *((_QWORD *)a2 + 12),
             v22,
             *(_DWORD *)(v20 + 60),
             *(_DWORD *)(v20 + 28));
LABEL_19:
  if ( !inited )
    goto LABEL_27;
  v26 = (struct _XLATEOBJ *)v81;
LABEL_21:
  v27 = v95;
  if ( !v95 )
  {
    v27 = v86[0];
    if ( !v86[0] )
    {
      if ( v85 != EngRealizeBrush )
      {
        v28 = 0;
        goto LABEL_23;
      }
LABEL_27:
      NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v77);
      if ( v10 )
        GreReleaseSemaphoreShared<1,>(v9);
      SURFMEM::~SURFMEM((SURFMEM *)v86);
      EXLATEOBJ::vAltUnlock((EXLATEOBJ *)&v81);
      SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v94);
      return 0;
    }
  }
  v28 = (v27 + 24) & -(__int64)(v27 != 0);
LABEL_23:
  v29 = v85(
          (struct _BRUSHOBJ *)a2,
          (struct _SURFOBJ *)((*((_QWORD *)a2 + 10) + 24LL) & -(__int64)(*((_QWORD *)a2 + 10) != 0)),
          (struct _SURFOBJ *)v28,
          v93,
          v26,
          v87);
  NEEDGRELOCK::vUnlock((NEEDGRELOCK *)v77);
  if ( v10 )
    GreReleaseSemaphoreShared<1,>(v9);
  SURFMEM::~SURFMEM((SURFMEM *)v86);
  EXLATEOBJ::vAltUnlock((EXLATEOBJ *)&v81);
  SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v94);
  return v29;
}

```

## disassembly

```asm
0x1401290b4  mov     [rsp-8+arg_18], rbx
0x1401290b9  push    rbp
0x1401290ba  push    rsi
0x1401290bb  push    rdi
0x1401290bc  push    r12
0x1401290be  push    r13
0x1401290c0  push    r14
0x1401290c2  push    r15
0x1401290c4  lea     rbp, [rsp-50h]
0x1401290c9  sub     rsp, 150h
0x1401290d0  mov     rax, cs:__security_cookie
0x1401290d7  xor     rax, rsp
0x1401290da  mov     [rbp+80h+var_38], rax
0x1401290de  mov     rbx, r8
0x1401290e1  mov     rdi, rdx
0x1401290e4  mov     [rbp+80h+var_E0], rbx
0x1401290e8  mov     r13, rcx
0x1401290eb  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x1401290f2  nop     dword ptr [rax+rax+00h]
0x1401290f7  mov     r12, rax
0x1401290fa  mov     [rbp+80h+var_F8], rax
0x1401290fe  mov     eax, [r13+50h]
0x140129102  mov     [rbp+80h+var_C0], eax
0x140129105  cmp     eax, 0Ch
0x140129108  jz      loc_1401293DF
0x14012910e  xorps   xmm0, xmm0
0x140129111  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z
0x140129118  lea     rdx, [rbp+80h+var_78]
0x14012911c  lea     rcx, [rbp+80h+var_78]
0x140129120  movups  [rbp+80h+var_78], xmm0
0x140129124  movups  [rbp+80h+var_68], xmm0
0x140129128  call    cs:__imp_PushThreadGuardedObject
0x14012912f  nop     dword ptr [rax+rax+00h]
0x140129134  xor     r8d, r8d
0x140129137  lea     rcx, [rbp+80h+var_D8]
0x14012913b  mov     [rbp+80h+var_58], r8
0x14012913f  mov     [rbp+80h+var_100], r8
0x140129143  lea     edx, [r8+2]
0x140129147  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z
0x14012914c  mov     rax, [rdi+50h]
0x140129150  lea     r15d, [r8+1]
0x140129154  mov     rcx, [rax+30h]
0x140129158  mov     [rsp+180h+hdev], rcx
0x14012915d  mov     eax, [rcx+28h]
0x140129160  lea     rcx, ?EngRealizeBrush@@YAHPEAU_BRUSHOBJ@@PEAU_SURFOBJ@@11PEAU_XLATEOBJ@@K@Z
0x140129167  test    r15b, al
0x14012916a  jz      loc_140129409
0x140129170  cmp     rbx, rcx
0x140129173  jnz     loc_140129409
0x140129179  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x140129180  nop     dword ptr [rax+rax+00h]
0x140129185  mov     rcx, rax
0x140129188  mov     rsi, rax
0x14012918b  call    ??$GreAcquireSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z
0x140129190  mov     r14b, r15b
0x140129193  lea     rdx, [rsp+180h+hdev]
0x140129198  lea     rcx, [rsp+180h+var_120]
0x14012919d  call    cs:__imp_?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z
0x1401291a4  nop     dword ptr [rax+rax+00h]
0x1401291a9  mov     eax, [r13+50h]
0x1401291ad  mov     ebx, 6
0x1401291b2  cmp     eax, ebx
0x1401291b4  jb      loc_14012935B
0x1401291ba  xor     r9d, r9d
0x1401291bd  mov     [rbp+80h+var_80], r9
0x1401291c1  cmp     eax, 0Ch
0x1401291c4  jb      loc_140129455
0x1401291ca  mov     rax, [r13+18h]
0x1401291ce  mov     r12d, r9d
0x1401291d1  mov     [rsp+180h+var_110], rax
0x1401291d6  mov     eax, [rdi+48h]
0x1401291d9  test    r15b, al
0x1401291dc  jnz     loc_140129C50
0x1401291e2  test    bl, al
0x1401291e4  cmovnz  r12d, r15d
0x1401291e8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x1401291ef  nop     dword ptr [rax+rax+00h]
0x1401291f4  mov     rdx, [rsp+180h+var_110]
0x1401291f9  mov     r9d, r15d
0x1401291fc  mov     rcx, rax
0x1401291ff  mov     r8b, 5
0x140129202  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z
0x140129209  nop     dword ptr [rax+rax+00h]
0x14012920e  xor     r15d, r15d
0x140129211  mov     [rbp+80h+var_58], rax
0x140129215  mov     rcx, rax
0x140129218  test    rax, rax
0x14012921b  jz      loc_14012939F
0x140129221  mov     rdx, [rax+0B0h]
0x140129228  mov     eax, [r13+28h]
0x14012922c  mov     r9, [rdi+50h]
0x140129230  bt      eax, 0Ch
0x140129234  jb      loc_140129697
0x14012923a  bt      eax, 0Dh
0x14012923e  jb      loc_140129CAE
0x140129244  mov     rax, [rsp+180h+hdev]
0x140129249  cmp     [rcx+64h], r15w
0x14012924e  jnz     loc_140129446
0x140129254  cmp     [rcx+18h], r15
0x140129258  jnz     loc_140129446
0x14012925e  test    rdx, rdx
0x140129261  jz      loc_140129CCB
0x140129267  mov     r11d, [rdi+34h]
0x14012926b  mov     ebx, [rdi+30h]
0x14012926e  mov     rax, [rdi+60h]
0x140129272  mov     rcx, [r9+0B0h]
0x140129279  test    r12d, r12d
0x14012927c  jnz     loc_140129681
0x140129282  mov     r10, r15
0x140129285  mov     r8d, r15d
0x140129288  mov     [rsp+180h+var_130], r15d
0x14012928d  mov     r9, rdx
0x140129290  mov     [rsp+180h+var_138], 0FFFFFFh
0x140129298  mov     rdx, r10
0x14012929b  mov     [rsp+180h+var_140], r11d
0x1401292a0  mov     [rsp+180h+var_148], ebx
0x1401292a4  mov     [rsp+180h+var_150], rax
0x1401292a9  mov     [rsp+180h+var_158], rax
0x1401292ae  mov     [rsp+180h+var_160], rcx
0x1401292b3  lea     rcx, [rbp+80h+var_100]
0x1401292b7  call    ?bInitXlateObj@EXLATEOBJ@@QEAAHPEAXJVXEPALOBJ@@111KKKK@Z
0x1401292bc  test    eax, eax
0x1401292be  jz      loc_14012939F
0x1401292c4  mov     r15, [rbp+80h+var_100]
0x1401292c8  xor     r12d, r12d
0x1401292cb  mov     rcx, [rbp+80h+var_58]
0x1401292cf  test    rcx, rcx
0x1401292d2  jz      loc_140129420
0x1401292d8  lea     rax, [rcx+18h]
0x1401292dc  neg     rcx
0x1401292df  sbb     r8, r8
0x1401292e2  and     r8, rax
0x1401292e5  mov     rax, [rdi+50h]
0x1401292e9  mov     rcx, rdi
0x1401292ec  mov     r9, [rbp+80h+var_80]
0x1401292f0  lea     r10, [rax+18h]
0x1401292f4  neg     rax
0x1401292f7  mov     eax, [rbp+80h+var_C0]
0x1401292fa  mov     dword ptr [rsp+180h+var_158], eax
0x1401292fe  sbb     rdx, rdx
0x140129301  mov     rax, [rbp+80h+var_E0]
0x140129305  and     rdx, r10
0x140129308  mov     [rsp+180h+var_160], r15
0x14012930d  call    _guard_dispatch_icall
0x140129312  lea     rcx, [rsp+180h+var_120]
0x140129317  mov     ebx, eax
0x140129319  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ
0x140129320  nop     dword ptr [rax+rax+00h]
0x140129325  test    r14b, r14b
0x140129328  jz      short loc_140129332
0x14012932a  mov     rcx, rsi
0x14012932d  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z
0x140129332  lea     rcx, [rbp+80h+var_D8]
0x140129336  call    cs:__imp_??1SURFMEM@@QEAA@XZ
0x14012933d  nop     dword ptr [rax+rax+00h]
0x140129342  lea     rcx, [rbp+80h+var_100]; this
0x140129346  call    ?vAltUnlock@EXLATEOBJ@@QEAAXXZ
0x14012934b  lea     rcx, [rbp+80h+var_78]; this
0x14012934f  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ
0x140129354  mov     eax, ebx
0x140129356  jmp     loc_1401293E1
0x14012935b  mov     rcx, [rsp+180h+hdev]
0x140129360  mov     rbx, [rcx+rax*8+5B0h]
0x140129368  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x14012936f  nop     dword ptr [rax+rax+00h]
0x140129374  xor     r9d, r9d
0x140129377  mov     r8b, 5
0x14012937a  mov     rcx, rax
0x14012937d  mov     rdx, rbx
0x140129380  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z
0x140129387  nop     dword ptr [rax+rax+00h]
0x14012938c  xor     r12d, r12d
0x14012938f  mov     [rbp+80h+var_58], rax
0x140129393  mov     r13, rax
0x140129396  test    rax, rax
0x140129399  jnz     loc_1401295C4
0x14012939f  lea     rcx, [rsp+180h+var_120]
0x1401293a4  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ
0x1401293ab  nop     dword ptr [rax+rax+00h]
0x1401293b0  test    r14b, r14b
0x1401293b3  jz      short loc_1401293BD
0x1401293b5  mov     rcx, rsi
0x1401293b8  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z
0x1401293bd  lea     rcx, [rbp+80h+var_D8]
0x1401293c1  call    cs:__imp_??1SURFMEM@@QEAA@XZ
0x1401293c8  nop     dword ptr [rax+rax+00h]
0x1401293cd  lea     rcx, [rbp+80h+var_100]; this
0x1401293d1  call    ?vAltUnlock@EXLATEOBJ@@QEAAXXZ
0x1401293d6  lea     rcx, [rbp+80h+var_78]; this
0x1401293da  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ
0x1401293df  xor     eax, eax
0x1401293e1  mov     rcx, [rbp+80h+var_38]
0x1401293e5  xor     rcx, rsp; StackCookie
0x1401293e8  call    __security_check_cookie
0x1401293ed  mov     rbx, [rsp+180h+arg_18]
0x1401293f5  add     rsp, 150h
0x1401293fc  pop     r15
0x1401293fe  pop     r14
0x140129400  pop     r13
0x140129402  pop     r12
0x140129404  pop     rdi
0x140129405  pop     rsi
0x140129406  pop     rbp
0x140129407  retn
0x140129409  mov     r14b, r8b
0x14012940c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x140129413  nop     dword ptr [rax+rax+00h]
0x140129418  mov     rsi, rax
0x14012941b  jmp     loc_140129193
0x140129420  mov     rcx, [rbp+80h+var_D8]
0x140129424  test    rcx, rcx
0x140129427  jnz     loc_1401292D8
0x14012942d  lea     rax, ?EngRealizeBrush@@YAHPEAU_BRUSHOBJ@@PEAU_SURFOBJ@@11PEAU_XLATEOBJ@@K@Z
0x140129434  cmp     [rbp+80h+var_E0], rax
0x140129438  jz      loc_14012939F
0x14012943e  mov     r8, r12
0x140129441  jmp     loc_1401292E5
0x140129446  cmp     [rcx+30h], rax
0x14012944a  jz      loc_14012925E
0x140129450  jmp     loc_14012939F
0x140129455  mov     rcx, rdi; this
0x140129458  call    ?bIsCMYKColor@EBRUSHOBJ@@QEBAHXZ
0x14012945d  test    eax, eax
0x14012945f  jnz     loc_140129579
0x140129465  mov     r8d, [rdi+18h]
0x140129469  bt      r8d, 18h
0x14012946e  jb      loc_1401297F9
0x140129474  mov     rax, [rsp+180h+hdev]
0x140129479  mov     r13, [rbp+80h+var_E0]
0x14012947d  test    dword ptr [rax+710h], 200000h
0x140129487  jnz     loc_14012981B
0x14012948d  mov     rcx, [rdi+50h]
0x140129491  xorps   xmm0, xmm0
0x140129494  movups  [rbp+80h+var_B8], xmm0
0x140129498  movups  [rbp+80h+var_A8], xmm0
0x14012949c  cmp     [rcx+60h], r15d
0x1401294a0  jz      loc_1401296BB
0x1401294a6  mov     ecx, [rax+82Ch]
0x1401294ac  mov     dword ptr [rbp+80h+var_B8], ecx
0x1401294af  movzx   ecx, word ptr [rax+830h]
0x1401294b6  test    ecx, ecx
0x1401294b8  jz      loc_140129579
0x1401294be  cmp     [rax+832h], r9w
0x1401294c6  jz      loc_140129579
0x1401294cc  mov     [rsp+180h+var_138], r9d
0x1401294d1  lea     rdx, [rbp+80h+var_B8]
0x1401294d5  mov     [rsp+180h+var_140], r15d
0x1401294da  xor     r8d, r8d
0x1401294dd  mov     [rsp+180h+var_148], r9d
0x1401294e2  mov     [rsp+180h+var_150], r9
0x1401294e7  mov     dword ptr [rbp+80h+var_B8+4], ecx
0x1401294ea  movzx   ecx, word ptr [rax+832h]
0x1401294f1  mov     [rsp+180h+var_158], r9
0x1401294f6  mov     dword ptr [rsp+180h+var_160], r9d
0x1401294fb  mov     dword ptr [rbp+80h+var_B8+8], ecx
0x1401294fe  lea     rcx, [rbp+80h+var_D8]
0x140129502  mov     qword ptr [rbp+80h+var_A8], r9
0x140129506  xor     r9d, r9d
0x140129509  mov     dword ptr [rbp+80h+var_A8+8], r15d
0x14012950d  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z
0x140129514  nop     dword ptr [rax+rax+00h]
0x140129519  xor     r8d, r8d
0x14012951c  test    eax, eax
0x14012951e  jz      short loc_140129579
0x140129520  mov     rax, [rdi+50h]
0x140129524  mov     edx, r8d
0x140129527  mov     rcx, [rsp+180h+hdev]; hdev
0x14012952c  mov     r8d, [rdi+18h]; rgb
0x140129530  cmp     [rax+60h], r15d
0x140129534  mov     r10, [rcx+0AE0h]
0x14012953b  setz    dl
0x14012953e  add     edx, r15d; iMode
0x140129541  test    r10, r10
0x140129544  jz      loc_14012966F
0x14012954a  test    dword ptr [rcx+28h], 8000h
0x140129551  mov     rax, [rbp+80h+var_D8]
0x140129555  mov     r9, [rax+48h]
0x140129559  jz      loc_140129883
0x14012955f  mov     rax, r10
0x140129562  call    _guard_dispatch_icall
0x140129567  sub     eax, r15d
0x14012956a  jz      loc_140129C43
0x140129570  cmp     eax, r15d
0x140129573  jz      loc_14012988F
0x140129579  lea     rcx, [rsp+180h+var_120]
0x14012957e  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ
0x140129585  nop     dword ptr [rax+rax+00h]
0x14012958a  xor     r15d, r15d
0x14012958d  test    r14b, r14b
0x140129590  jz      short loc_14012959A
0x140129592  mov     rcx, rsi
0x140129595  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z
0x14012959a  lea     rcx, [rbp+80h+var_D8]
0x14012959e  call    cs:__imp_??1SURFMEM@@QEAA@XZ
0x1401295a5  nop     dword ptr [rax+rax+00h]
0x1401295aa  lea     rcx, [rbp+80h+var_100]; this
0x1401295ae  call    ?vAltUnlock@EXLATEOBJ@@QEAAXXZ
0x1401295b3  lea     rcx, [rbp+80h+var_78]; this
0x1401295b7  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ
0x1401295bc  mov     eax, r15d
  ... truncated ...
```
