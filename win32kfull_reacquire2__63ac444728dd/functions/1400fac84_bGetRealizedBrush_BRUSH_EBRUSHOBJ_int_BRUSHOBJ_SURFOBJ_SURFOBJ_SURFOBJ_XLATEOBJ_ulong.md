# bGetRealizedBrush(BRUSH *,EBRUSHOBJ *,int (*)(_BRUSHOBJ *,_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_XLATEOBJ *,ulong))

- ea: `0x1400fac84`
- end: `0x1400fb902`
- name: `?bGetRealizedBrush@@YAHPEAVBRUSH@@PEAVEBRUSHOBJ@@P6AHPEAU_BRUSHOBJ@@PEAU_SURFOBJ@@33PEAU_XLATEOBJ@@K@Z@Z`
- size: `3198`
- prototype: `int(struct BRUSH *, struct EBRUSHOBJ *, int (*)(struct _BRUSHOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _XLATEOBJ *, unsigned int))`
- caller_count: `3`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400fa264`
- `0x1400fa830`
- `0x1400fbeb0`

## callees

- `0x140050c78`
- `0x140050d10`
- `0x14009a40c`
- `0x14009b35c`
- `0x14009b508`
- `0x1400ab6d8`
- `0x1400acc04`
- `0x1400fac84`
- `0x14011f018`
- `0x14015f220`
- `0x140160ba4`
- `0x140160c5c`
- `0x140162e0c`
- `0x140162f10`
- `0x1401633a4`
- `0x14018d8f4`
- `0x14018dc5c`
- `0x1401afe14`
- `0x14025815c`
- `0x1402971b0`
- `0x140298e04`
- `0x1402fd744`
- `0x140303fa4`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400facbb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fad49`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fadb8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400faf38`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fafdc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fb1c0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400facbb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fad49`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fadb8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400faf38`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fafdc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fb1c0`
- `win32kbase!HmgShareLock` at `0x1400fadd2`
- `win32kbase!HmgShareLock` at `0x1400faf50`
- `win32kbase!HmgShareLock` at `0x1400fadd2`
- `win32kbase!HmgShareLock` at `0x1400faf50`
- `win32kbase!PushThreadGuardedObject` at `0x1400facf8`
- `win32kbase!PushThreadGuardedObject` at `0x1400facf8`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400faf06`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400faf91`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400fb16e`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400faf06`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400faf91`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400fb16e`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z` at `0x1400fad6d`
- `win32kbase!?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z` at `0x1400fad6d`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400faee9`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400faf74`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400fb14e`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400fb2a8`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400fb438`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400faee9`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400faf74`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400fb14e`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400fb2a8`
- `win32kbase!?vUnlock@NEEDGRELOCK@@QEAAXXZ` at `0x1400fb438`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x1400fb31b`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x1400fb339`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x1400fb31b`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x1400fb339`
- `win32kbase!rgbFromColorref` at `0x1400fb3d1`
- `win32kbase!rgbFromColorref` at `0x1400fb3d1`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fb0dd`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fb5b2`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fb722`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fb0dd`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fb5b2`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fb722`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x1400fb569`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x1400fb6eb`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x1400fb569`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x1400fb6eb`
- `win32kbase!?hFindIcmDIB@BRUSH@@QEAAPEAUHBITMAP__@@PEAX@Z` at `0x1400fb83e`
- `win32kbase!?hFindIcmDIB@BRUSH@@QEAAPEAUHBITMAP__@@PEAX@Z` at `0x1400fb83e`
- `win32kbase!AllocThreadBufferWithTag` at `0x1400fb1a0`
- `win32kbase!AllocThreadBufferWithTag` at `0x1400fb1a0`
- `win32kbase!Win32FreePool` at `0x1400fb5f6`
- `win32kbase!Win32FreePool` at `0x1400fb5f6`

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
        SURFACE::bDeleteSurface(v86[0], v53, 0, 0);
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
                                *(_QWORD *)(*((_QWORD *)a2 + 10) + 160LL),
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
        SURFACE::bDeleteSurface(v86[0], v53, 0, 0);
        if ( SURFMEM::bCreateDIB((SURFMEM *)v86, (struct _DEVBITMAPINFO *)&v88, v72, 0, 0, 0, 0, 0, v8, 0) )
        {
          *(_BYTE *)(v86[0] + 720LL) = v8;
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
  v20 = *(_QWORD *)(v18 + 160);
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
                   *(_QWORD *)(v22 + 160),
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
0x1400fac84  mov     [rsp-8+arg_18], rbx
0x1400fac89  push    rbp
0x1400fac8a  push    rsi
0x1400fac8b  push    rdi
0x1400fac8c  push    r12
0x1400fac8e  push    r13
0x1400fac90  push    r14
0x1400fac92  push    r15
0x1400fac94  lea     rbp, [rsp-50h]
0x1400fac99  sub     rsp, 150h
0x1400faca0  mov     rax, cs:__security_cookie
0x1400faca7  xor     rax, rsp
0x1400facaa  mov     [rbp+80h+var_38], rax
0x1400facae  mov     rbx, r8
0x1400facb1  mov     rdi, rdx
0x1400facb4  mov     [rbp+80h+var_E0], rbx
0x1400facb8  mov     r13, rcx
0x1400facbb  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x1400facc2  nop     dword ptr [rax+rax+00h]
0x1400facc7  mov     r12, rax
0x1400facca  mov     [rbp+80h+var_F8], rax
0x1400facce  mov     eax, [r13+50h]
0x1400facd2  mov     [rbp+80h+var_C0], eax
0x1400facd5  cmp     eax, 0Ch
0x1400facd8  jz      loc_1400FAFAF
0x1400facde  xorps   xmm0, xmm0
0x1400face1  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z
0x1400face8  lea     rdx, [rbp+80h+var_78]
0x1400facec  lea     rcx, [rbp+80h+var_78]
0x1400facf0  movups  [rbp+80h+var_78], xmm0
0x1400facf4  movups  [rbp+80h+var_68], xmm0
0x1400facf8  call    cs:__imp_PushThreadGuardedObject
0x1400facff  nop     dword ptr [rax+rax+00h]
0x1400fad04  xor     r8d, r8d
0x1400fad07  lea     rcx, [rbp+80h+var_D8]
0x1400fad0b  mov     [rbp+80h+var_58], r8
0x1400fad0f  mov     [rbp+80h+var_100], r8
0x1400fad13  lea     edx, [r8+2]
0x1400fad17  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z
0x1400fad1c  mov     rax, [rdi+50h]
0x1400fad20  lea     r15d, [r8+1]
0x1400fad24  mov     rcx, [rax+30h]
0x1400fad28  mov     [rsp+180h+hdev], rcx
0x1400fad2d  mov     eax, [rcx+28h]
0x1400fad30  lea     rcx, ?EngRealizeBrush@@YAHPEAU_BRUSHOBJ@@PEAU_SURFOBJ@@11PEAU_XLATEOBJ@@K@Z
0x1400fad37  test    r15b, al
0x1400fad3a  jz      loc_1400FAFD9
0x1400fad40  cmp     rbx, rcx
0x1400fad43  jnz     loc_1400FAFD9
0x1400fad49  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x1400fad50  nop     dword ptr [rax+rax+00h]
0x1400fad55  mov     rcx, rax
0x1400fad58  mov     rsi, rax
0x1400fad5b  call    ??$GreAcquireSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z
0x1400fad60  mov     r14b, r15b
0x1400fad63  lea     rdx, [rsp+180h+hdev]
0x1400fad68  lea     rcx, [rsp+180h+var_120]
0x1400fad6d  call    cs:__imp_?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z
0x1400fad74  nop     dword ptr [rax+rax+00h]
0x1400fad79  mov     eax, [r13+50h]
0x1400fad7d  mov     ebx, 6
0x1400fad82  cmp     eax, ebx
0x1400fad84  jb      loc_1400FAF2B
0x1400fad8a  xor     r9d, r9d
0x1400fad8d  mov     [rbp+80h+var_80], r9
0x1400fad91  cmp     eax, 0Ch
0x1400fad94  jb      loc_1400FB025
0x1400fad9a  mov     rax, [r13+18h]
0x1400fad9e  mov     r12d, r9d
0x1400fada1  mov     [rsp+180h+var_110], rax
0x1400fada6  mov     eax, [rdi+48h]
0x1400fada9  test    r15b, al
0x1400fadac  jnz     loc_1400FB820
0x1400fadb2  test    bl, al
0x1400fadb4  cmovnz  r12d, r15d
0x1400fadb8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x1400fadbf  nop     dword ptr [rax+rax+00h]
0x1400fadc4  mov     rdx, [rsp+180h+var_110]
0x1400fadc9  mov     r9d, r15d
0x1400fadcc  mov     rcx, rax
0x1400fadcf  mov     r8b, 5
0x1400fadd2  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z
0x1400fadd9  nop     dword ptr [rax+rax+00h]
0x1400fadde  xor     r15d, r15d
0x1400fade1  mov     [rbp+80h+var_58], rax
0x1400fade5  mov     rcx, rax
0x1400fade8  test    rax, rax
0x1400fadeb  jz      loc_1400FAF6F
0x1400fadf1  mov     rdx, [rax+0A0h]
0x1400fadf8  mov     eax, [r13+28h]
0x1400fadfc  mov     r9, [rdi+50h]
0x1400fae00  bt      eax, 0Ch
0x1400fae04  jb      loc_1400FB267
0x1400fae0a  bt      eax, 0Dh
0x1400fae0e  jb      loc_1400FB87E
0x1400fae14  mov     rax, [rsp+180h+hdev]
0x1400fae19  cmp     [rcx+64h], r15w
0x1400fae1e  jnz     loc_1400FB016
0x1400fae24  cmp     [rcx+18h], r15
0x1400fae28  jnz     loc_1400FB016
0x1400fae2e  test    rdx, rdx
0x1400fae31  jz      loc_1400FB89B
0x1400fae37  mov     r11d, [rdi+34h]
0x1400fae3b  mov     ebx, [rdi+30h]
0x1400fae3e  mov     rax, [rdi+60h]
0x1400fae42  mov     rcx, [r9+0A0h]
0x1400fae49  test    r12d, r12d
0x1400fae4c  jnz     loc_1400FB251
0x1400fae52  mov     r10, r15
0x1400fae55  mov     r8d, r15d
0x1400fae58  mov     [rsp+180h+var_130], r15d
0x1400fae5d  mov     r9, rdx
0x1400fae60  mov     [rsp+180h+var_138], 0FFFFFFh
0x1400fae68  mov     rdx, r10
0x1400fae6b  mov     [rsp+180h+var_140], r11d
0x1400fae70  mov     [rsp+180h+var_148], ebx
0x1400fae74  mov     [rsp+180h+var_150], rax
0x1400fae79  mov     [rsp+180h+var_158], rax
0x1400fae7e  mov     [rsp+180h+var_160], rcx
0x1400fae83  lea     rcx, [rbp+80h+var_100]
0x1400fae87  call    ?bInitXlateObj@EXLATEOBJ@@QEAAHPEAXJVXEPALOBJ@@111KKKK@Z
0x1400fae8c  test    eax, eax
0x1400fae8e  jz      loc_1400FAF6F
0x1400fae94  mov     r15, [rbp+80h+var_100]
0x1400fae98  xor     r12d, r12d
0x1400fae9b  mov     rcx, [rbp+80h+var_58]
0x1400fae9f  test    rcx, rcx
0x1400faea2  jz      loc_1400FAFF0
0x1400faea8  lea     rax, [rcx+18h]
0x1400faeac  neg     rcx
0x1400faeaf  sbb     r8, r8
0x1400faeb2  and     r8, rax
0x1400faeb5  mov     rax, [rdi+50h]
0x1400faeb9  mov     rcx, rdi
0x1400faebc  mov     r9, [rbp+80h+var_80]
0x1400faec0  lea     r10, [rax+18h]
0x1400faec4  neg     rax
0x1400faec7  mov     eax, [rbp+80h+var_C0]
0x1400faeca  mov     dword ptr [rsp+180h+var_158], eax
0x1400faece  sbb     rdx, rdx
0x1400faed1  mov     rax, [rbp+80h+var_E0]
0x1400faed5  and     rdx, r10
0x1400faed8  mov     [rsp+180h+var_160], r15
0x1400faedd  call    _guard_dispatch_icall
0x1400faee2  lea     rcx, [rsp+180h+var_120]
0x1400faee7  mov     ebx, eax
0x1400faee9  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ
0x1400faef0  nop     dword ptr [rax+rax+00h]
0x1400faef5  test    r14b, r14b
0x1400faef8  jz      short loc_1400FAF02
0x1400faefa  mov     rcx, rsi
0x1400faefd  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z
0x1400faf02  lea     rcx, [rbp+80h+var_D8]
0x1400faf06  call    cs:__imp_??1SURFMEM@@QEAA@XZ
0x1400faf0d  nop     dword ptr [rax+rax+00h]
0x1400faf12  lea     rcx, [rbp+80h+var_100]; this
0x1400faf16  call    ?vAltUnlock@EXLATEOBJ@@QEAAXXZ
0x1400faf1b  lea     rcx, [rbp+80h+var_78]; this
0x1400faf1f  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ
0x1400faf24  mov     eax, ebx
0x1400faf26  jmp     loc_1400FAFB1
0x1400faf2b  mov     rcx, [rsp+180h+hdev]
0x1400faf30  mov     rbx, [rcx+rax*8+5B0h]
0x1400faf38  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x1400faf3f  nop     dword ptr [rax+rax+00h]
0x1400faf44  xor     r9d, r9d
0x1400faf47  mov     r8b, 5
0x1400faf4a  mov     rcx, rax
0x1400faf4d  mov     rdx, rbx
0x1400faf50  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z
0x1400faf57  nop     dword ptr [rax+rax+00h]
0x1400faf5c  xor     r12d, r12d
0x1400faf5f  mov     [rbp+80h+var_58], rax
0x1400faf63  mov     r13, rax
0x1400faf66  test    rax, rax
0x1400faf69  jnz     loc_1400FB194
0x1400faf6f  lea     rcx, [rsp+180h+var_120]
0x1400faf74  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ
0x1400faf7b  nop     dword ptr [rax+rax+00h]
0x1400faf80  test    r14b, r14b
0x1400faf83  jz      short loc_1400FAF8D
0x1400faf85  mov     rcx, rsi
0x1400faf88  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z
0x1400faf8d  lea     rcx, [rbp+80h+var_D8]
0x1400faf91  call    cs:__imp_??1SURFMEM@@QEAA@XZ
0x1400faf98  nop     dword ptr [rax+rax+00h]
0x1400faf9d  lea     rcx, [rbp+80h+var_100]; this
0x1400fafa1  call    ?vAltUnlock@EXLATEOBJ@@QEAAXXZ
0x1400fafa6  lea     rcx, [rbp+80h+var_78]; this
0x1400fafaa  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ
0x1400fafaf  xor     eax, eax
0x1400fafb1  mov     rcx, [rbp+80h+var_38]
0x1400fafb5  xor     rcx, rsp; StackCookie
0x1400fafb8  call    __security_check_cookie
0x1400fafbd  mov     rbx, [rsp+180h+arg_18]
0x1400fafc5  add     rsp, 150h
0x1400fafcc  pop     r15
0x1400fafce  pop     r14
0x1400fafd0  pop     r13
0x1400fafd2  pop     r12
0x1400fafd4  pop     rdi
0x1400fafd5  pop     rsi
0x1400fafd6  pop     rbp
0x1400fafd7  retn
0x1400fafd9  mov     r14b, r8b
0x1400fafdc  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ
0x1400fafe3  nop     dword ptr [rax+rax+00h]
0x1400fafe8  mov     rsi, rax
0x1400fafeb  jmp     loc_1400FAD63
0x1400faff0  mov     rcx, [rbp+80h+var_D8]
0x1400faff4  test    rcx, rcx
0x1400faff7  jnz     loc_1400FAEA8
0x1400faffd  lea     rax, ?EngRealizeBrush@@YAHPEAU_BRUSHOBJ@@PEAU_SURFOBJ@@11PEAU_XLATEOBJ@@K@Z
0x1400fb004  cmp     [rbp+80h+var_E0], rax
0x1400fb008  jz      loc_1400FAF6F
0x1400fb00e  mov     r8, r12
0x1400fb011  jmp     loc_1400FAEB5
0x1400fb016  cmp     [rcx+30h], rax
0x1400fb01a  jz      loc_1400FAE2E
0x1400fb020  jmp     loc_1400FAF6F
0x1400fb025  mov     rcx, rdi; this
0x1400fb028  call    ?bIsCMYKColor@EBRUSHOBJ@@QEBAHXZ
0x1400fb02d  test    eax, eax
0x1400fb02f  jnz     loc_1400FB149
0x1400fb035  mov     r8d, [rdi+18h]
0x1400fb039  bt      r8d, 18h
0x1400fb03e  jb      loc_1400FB3C9
0x1400fb044  mov     rax, [rsp+180h+hdev]
0x1400fb049  mov     r13, [rbp+80h+var_E0]
0x1400fb04d  test    dword ptr [rax+710h], 200000h
0x1400fb057  jnz     loc_1400FB3EB
0x1400fb05d  mov     rcx, [rdi+50h]
0x1400fb061  xorps   xmm0, xmm0
0x1400fb064  movups  [rbp+80h+var_B8], xmm0
0x1400fb068  movups  [rbp+80h+var_A8], xmm0
0x1400fb06c  cmp     [rcx+60h], r15d
0x1400fb070  jz      loc_1400FB28B
0x1400fb076  mov     ecx, [rax+82Ch]
0x1400fb07c  mov     dword ptr [rbp+80h+var_B8], ecx
0x1400fb07f  movzx   ecx, word ptr [rax+830h]
0x1400fb086  test    ecx, ecx
0x1400fb088  jz      loc_1400FB149
0x1400fb08e  cmp     [rax+832h], r9w
0x1400fb096  jz      loc_1400FB149
0x1400fb09c  mov     [rsp+180h+var_138], r9d
0x1400fb0a1  lea     rdx, [rbp+80h+var_B8]
0x1400fb0a5  mov     [rsp+180h+var_140], r15d
0x1400fb0aa  xor     r8d, r8d
0x1400fb0ad  mov     [rsp+180h+var_148], r9d
0x1400fb0b2  mov     [rsp+180h+var_150], r9
0x1400fb0b7  mov     dword ptr [rbp+80h+var_B8+4], ecx
0x1400fb0ba  movzx   ecx, word ptr [rax+832h]
0x1400fb0c1  mov     [rsp+180h+var_158], r9
0x1400fb0c6  mov     dword ptr [rsp+180h+var_160], r9d
0x1400fb0cb  mov     dword ptr [rbp+80h+var_B8+8], ecx
0x1400fb0ce  lea     rcx, [rbp+80h+var_D8]
0x1400fb0d2  mov     qword ptr [rbp+80h+var_A8], r9
0x1400fb0d6  xor     r9d, r9d
0x1400fb0d9  mov     dword ptr [rbp+80h+var_A8+8], r15d
0x1400fb0dd  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z
0x1400fb0e4  nop     dword ptr [rax+rax+00h]
0x1400fb0e9  xor     r8d, r8d
0x1400fb0ec  test    eax, eax
0x1400fb0ee  jz      short loc_1400FB149
0x1400fb0f0  mov     rax, [rdi+50h]
0x1400fb0f4  mov     edx, r8d
0x1400fb0f7  mov     rcx, [rsp+180h+hdev]; hdev
0x1400fb0fc  mov     r8d, [rdi+18h]; rgb
0x1400fb100  cmp     [rax+60h], r15d
0x1400fb104  mov     r10, [rcx+0AE0h]
0x1400fb10b  setz    dl
0x1400fb10e  add     edx, r15d; iMode
0x1400fb111  test    r10, r10
0x1400fb114  jz      loc_1400FB23F
0x1400fb11a  test    dword ptr [rcx+28h], 8000h
0x1400fb121  mov     rax, [rbp+80h+var_D8]
0x1400fb125  mov     r9, [rax+48h]
0x1400fb129  jz      loc_1400FB453
0x1400fb12f  mov     rax, r10
0x1400fb132  call    _guard_dispatch_icall
0x1400fb137  sub     eax, r15d
0x1400fb13a  jz      loc_1400FB813
0x1400fb140  cmp     eax, r15d
0x1400fb143  jz      loc_1400FB45F
0x1400fb149  lea     rcx, [rsp+180h+var_120]
0x1400fb14e  call    cs:__imp_?vUnlock@NEEDGRELOCK@@QEAAXXZ
0x1400fb155  nop     dword ptr [rax+rax+00h]
0x1400fb15a  xor     r15d, r15d
0x1400fb15d  test    r14b, r14b
0x1400fb160  jz      short loc_1400FB16A
0x1400fb162  mov     rcx, rsi
0x1400fb165  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z
0x1400fb16a  lea     rcx, [rbp+80h+var_D8]
0x1400fb16e  call    cs:__imp_??1SURFMEM@@QEAA@XZ
0x1400fb175  nop     dword ptr [rax+rax+00h]
0x1400fb17a  lea     rcx, [rbp+80h+var_100]; this
0x1400fb17e  call    ?vAltUnlock@EXLATEOBJ@@QEAAXXZ
0x1400fb183  lea     rcx, [rbp+80h+var_78]; this
0x1400fb187  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ
0x1400fb18c  mov     eax, r15d
  ... truncated ...
```
