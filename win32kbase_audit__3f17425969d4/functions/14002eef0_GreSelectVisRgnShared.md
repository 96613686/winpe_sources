# GreSelectVisRgnShared

- ea: `0x14002eef0`
- end: `0x14002f849`
- name: `GreSelectVisRgnShared`
- size: `2393`
- prototype: `__int64 __fastcall(__int64, HRGN, __int64, __int64)`
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400260d0`
- `0x140026cc8`
- `0x14002a1d0`
- `0x14002cca4`
- `0x14002d310`
- `0x14002de30`
- `0x14002eef0`
- `0x14002f850`
- `0x14002f8b0`
- `0x140031190`
- `0x140031520`
- `0x1400317e0`
- `0x140031c20`
- `0x140031c90`
- `0x140031fa0`
- `0x140032300`
- `0x1400323a0`
- `0x1400324c0`
- `0x14003405c`
- `0x140035008`
- `0x14003d28c`
- `0x1400764f0`
- `0x140076d10`
- `0x1400771b8`
- `0x140077494`
- `0x140078fb0`
- `0x140079250`
- `0x140079330`
- `0x1400798ac`
- `0x140079cd0`
- `0x140079f00`
- `0x14007a030`
- `0x14007a5a0`
- `0x140156e9c`
- `0x140192b70`
- `0x1401b5198`
- `0x1402388e0`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14002f073`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002f073`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002ef5e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002f202`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002ef5e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002f202`
- `WIN32K!W32GetSessionState` at `0x14002ef33`
- `WIN32K!W32GetSessionState` at `0x14002f07f`
- `WIN32K!W32GetSessionState` at `0x14002f167`
- `WIN32K!W32GetSessionState` at `0x14002f2d6`
- `WIN32K!W32GetSessionState` at `0x14002f390`
- `WIN32K!W32GetSessionState` at `0x14002f445`
- `WIN32K!W32GetSessionState` at `0x14002f601`
- `WIN32K!W32GetSessionState` at `0x14002ef33`
- `WIN32K!W32GetSessionState` at `0x14002f07f`
- `WIN32K!W32GetSessionState` at `0x14002f167`
- `WIN32K!W32GetSessionState` at `0x14002f2d6`
- `WIN32K!W32GetSessionState` at `0x14002f390`
- `WIN32K!W32GetSessionState` at `0x14002f445`
- `WIN32K!W32GetSessionState` at `0x14002f601`

## pseudocode

```c
__int64 __fastcall GreSelectVisRgnShared(__int64 a1, HRGN a2, __int64 a3, __int64 a4)
{
  int v4; // r13d
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 result; // rax
  struct Gre::Base::SESSION_GLOBALS *v15; // r15
  HSEMAPHORE v16; // r12
  DC *v17; // rcx
  unsigned int v18; // ebx
  struct _ENTRY *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  _QWORD *v24; // r14
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rbx
  __int64 v28; // r13
  unsigned int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rbx
  __int64 SessionState; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  DC *v38; // rbx
  __int64 v39; // r14
  unsigned int *v40; // rdi
  _QWORD *v41; // rax
  unsigned __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rax
  unsigned __int64 v45; // rcx
  __int64 v46; // rcx
  _QWORD *v47; // rax
  __int64 v48; // r9
  __int64 v49; // r11
  __int64 v50; // rax
  int v51; // eax
  int v52; // r10d
  bool v53; // zf
  __int64 v54; // rax
  __int64 v55; // r14
  __int64 v56; // r8
  __int64 v57; // r9
  DC *v58; // rbx
  DC *v59; // rcx
  struct _ENTRY *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  DC *v64; // rbx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r9
  struct _GRETHREAD *v69; // rax
  __int64 v70; // rax
  _QWORD **v71; // rcx
  __int64 *v72; // rdx
  __int64 v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rdx
  DC *v76; // rbx
  int v77; // ebx
  LONG v78; // edi
  LONG v79; // ebx
  __int64 *v80; // r11
  __int64 v81; // r11
  bool v82; // cc
  __int64 v83; // rax
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // r9
  unsigned int sizeScan; // eax
  __int64 v88; // r8
  __int64 v89; // r9
  const struct REGION_CORE *v90; // rdi
  __int64 v91; // rbx
  __int64 v92; // rdx
  __int64 v93; // rdx
  __int64 v94; // [rsp+30h] [rbp-A9h] BYREF
  int v95; // [rsp+38h] [rbp-A1h]
  __int128 v96; // [rsp+40h] [rbp-99h] BYREF
  __int128 v97; // [rsp+50h] [rbp-89h]
  __int64 v98; // [rsp+60h] [rbp-79h]
  __int64 v99; // [rsp+68h] [rbp-71h] BYREF
  DC *v100; // [rsp+70h] [rbp-69h] BYREF
  int v101; // [rsp+78h] [rbp-61h]
  struct Gre::Base::SESSION_GLOBALS *v102; // [rsp+80h] [rbp-59h]
  __int64 v103; // [rsp+88h] [rbp-51h]
  __int128 v104; // [rsp+90h] [rbp-49h] BYREF
  __int128 v105; // [rsp+A0h] [rbp-39h]
  __int64 v106; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v107; // [rsp+B8h] [rbp-21h] BYREF
  _QWORD **v108; // [rsp+C0h] [rbp-19h]
  int v109; // [rsp+E0h] [rbp+7h]
  struct _RECTL v110; // [rsp+E8h] [rbp+Fh] BYREF

  LODWORD(v94) = a3;
  v100 = 0;
  v4 = a3;
  v101 = 0;
  v102 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(a1, a2, a3, a4) + 88);
  v103 = 0;
  v100 = 0;
  v101 = 0;
  v104 = 0;
  v105 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v102);
  if ( !CurrentThreadWin32Thread || (v8 = *CurrentThreadWin32Thread) == 0 )
  {
    *(_QWORD *)&v105 = &v100;
    *((_QWORD *)&v105 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_120;
  }
  *(_QWORD *)&v105 = &v100;
  *((_QWORD *)&v105 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  v9 = v8 + 8;
  if ( !v9 )
  {
LABEL_120:
    *((_QWORD *)&v104 + 1) = &v104;
    *(_QWORD *)&v104 = &v104;
    goto LABEL_7;
  }
  v10 = *(_QWORD *)(v9 + 88);
  v11 = (_QWORD *)(v9 + 88);
  if ( *(_QWORD **)(v10 + 8) != v11 )
    goto LABEL_5;
  *(_QWORD *)&v104 = v10;
  *((_QWORD *)&v104 + 1) = v11;
  *(_QWORD *)(v10 + 8) = &v104;
  *v11 = &v104;
LABEL_7:
  v100 = (DC *)HmgShareLock(v102, a1, 1, 1);
  if ( !v100 )
  {
    v12 = v104;
    if ( *(__int128 **)(v104 + 8) == &v104 )
    {
      v13 = *((_QWORD *)&v104 + 1);
      if ( **((__int128 ***)&v104 + 1) == &v104 )
      {
        **((_QWORD **)&v104 + 1) = v104;
        *(_QWORD *)(v12 + 8) = v13;
        return 0;
      }
    }
LABEL_5:
    __fastfail(3u);
  }
  v15 = v102;
  v16 = (HSEMAPHORE)(*(_QWORD *)v102 + 1248LL);
  GreAcquireSemaphoreInternal(v16);
  GrepAcquireLockValidate<11>();
  v17 = v100;
  v18 = 1;
  v95 = 1;
  *((_DWORD *)v100 + 9) |= 0x10u;
  v19 = DC::PentryFromPobj(v17, v15);
  *((_BYTE *)v19 + 15) |= 4u;
  if ( !a2 )
  {
    DC::vReleaseVis(v100, v15);
    DC::bSetDefaultRegion(v100, v84, v85, v86);
    goto LABEL_58;
  }
  PsGetCurrentProcessId();
  v24 = *(_QWORD **)(W32GetSessionState(v21, v20, v22, v23) + 88);
  v99 = *v24 + 1512LL;
  GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v25, v99, v26);
  HANDLELOCK::HANDLELOCK(&v96, v24, a2, 1);
  if ( DWORD2(v96) )
  {
    v27 = v96;
    if ( *(_BYTE *)(v96 + 14) == 4 && *(_WORD *)(v96 + 12) == WORD1(a2) )
    {
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v97 + 8) + 96LL))(
              *(_QWORD *)(v97 + 8),
              *(unsigned int *)v96);
      GreGetCurrentThread();
      if ( !*(_WORD *)(v28 + 12) || *(struct _KTHREAD **)(v28 + 16) == KeGetCurrentThread() )
      {
        v29 = *(_DWORD *)(v27 + 8) & 0xFFFFFFFE;
        if ( v29 && (unsigned int)HmgIncProcessHandleCount(0) )
        {
          HmgDecProcessHandleCount(v24, v29);
          HANDLELOCK::Pid((HANDLELOCK *)&v96, 0);
          *(_WORD *)(v28 + 14) &= ~0x10u;
        }
        v4 = v94;
        goto LABEL_18;
      }
      v4 = v94;
    }
    BYTE13(v96) = 1;
LABEL_18:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v96);
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v96);
  SEMOBJ<20>::vUnlock(&v99);
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v106, a2, 0, 0);
  if ( !v106 )
    goto LABEL_66;
  v34 = *(_QWORD *)v100;
  SessionState = W32GetSessionState(v31, v30, v32, v33);
  v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(SessionState + 88) + 8LL) + 16LL))(
          *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 8LL),
          (unsigned __int16)v34 | ((unsigned int)v34 >> 8) & 0xFF0000);
  if ( v36 )
  {
    if ( *(_BYTE *)(v36 + 14) == 1 )
    {
      v37 = *(unsigned __int8 *)(v36 + 12);
      if ( *(_WORD *)(v36 + 12) == WORD1(v34) && (*(_DWORD *)(v36 + 8) & 0xFFFFFFFE) == 0x80000012 )
        goto LABEL_44;
    }
  }
  v38 = v100;
  if ( (*((_DWORD *)v100 + 9) & 0x100000) == 0 )
    goto LABEL_44;
  v39 = *((_QWORD *)v100 + 6);
  if ( !v39 )
    goto LABEL_44;
  v40 = (unsigned int *)v106;
  if ( !v106 )
    goto LABEL_44;
  v96 = 0;
  v97 = 0;
  v41 = (_QWORD *)PsGetCurrentThreadWin32Thread(v37);
  if ( !v41 || !*v41 )
  {
    v45 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    *(_QWORD *)&v97 = &v96;
    *((_QWORD *)&v97 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_129;
  }
  v44 = *v41 + 8LL;
  *(_QWORD *)&v97 = &v96;
  v45 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
  *((_QWORD *)&v97 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
  if ( !v44 )
  {
LABEL_129:
    *((_QWORD *)&v96 + 1) = &v96;
    *(_QWORD *)&v96 = &v96;
    goto LABEL_32;
  }
  v46 = *(_QWORD *)(v44 + 88);
  v47 = (_QWORD *)(v44 + 88);
  if ( *(_QWORD **)(v46 + 8) != v47 )
    goto LABEL_5;
  *(_QWORD *)&v96 = v46;
  v42 = (unsigned __int64)&v96;
  *((_QWORD *)&v96 + 1) = v47;
  *(_QWORD *)(v46 + 8) = &v96;
  v45 = (unsigned __int64)&v96;
  *v47 = &v96;
LABEL_32:
  v48 = 0;
  v53 = (*((_DWORD *)v38 + 9) & 0x40000) == 0;
  v98 = 0;
  if ( v53 )
  {
    v49 = *((_QWORD *)v38 + 62);
    v50 = 0;
  }
  else
  {
    v42 = *((_QWORD *)v38 + 268);
    if ( v42 )
    {
      SURFREF::vLock((SURFREF *)&v96, (HSURF)v42);
      v48 = v98;
      v49 = v98;
      v50 = v98;
    }
    else
    {
      v49 = *(_QWORD *)(v39 + 2544);
      v50 = 0;
    }
  }
  if ( !v49 )
  {
    v53 = v50 == 0;
LABEL_41:
    if ( v53 )
    {
LABEL_43:
      PopThreadGuardedObject(&v96);
      goto LABEL_44;
    }
LABEL_42:
    v54 = W32GetSessionState(v45, v42, v43, v48);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v54 + 88), v98);
    goto LABEL_43;
  }
  if ( (*(_DWORD *)(v39 + 40) & 0x20000) != 0 && *(int *)(v49 + 144) < 0
    || (v51 = *((_DWORD *)v38 + 9), (v51 & 0x1000) != 0) && (v51 & 0x4000) == 0
    || (v43 = v40[13], v42 = v40[15], (_DWORD)v43 == (_DWORD)v42)
    || (v52 = v40[14], v45 = v40[16], v52 == (_DWORD)v45)
    || (_DWORD)v43 == 0x7FFFFFFF && (_DWORD)v45 == 0x80000000 && v52 == 0x7FFFFFFF && (_DWORD)v42 == (_DWORD)v45 )
  {
    v53 = v48 == 0;
    goto LABEL_41;
  }
  v78 = v40[13];
  v79 = v52;
  if ( (*(_DWORD *)(v49 + 148) & 0x800) != 0 )
    v80 = (__int64 *)(v49 + 700);
  else
    v80 = (__int64 *)(v49 + 56);
  v81 = *v80;
  if ( (int)v43 >= (int)v42 )
  {
    if ( (int)v43 > (int)v42 )
    {
      v78 = v42;
      v42 = (unsigned int)v43;
    }
    v82 = v52 <= (int)v45;
    goto LABEL_91;
  }
  v82 = v52 <= (int)v45;
  if ( v52 >= (int)v45 )
  {
LABEL_91:
    if ( !v82 )
    {
      v79 = v45;
      v45 = (unsigned int)v52;
    }
    goto LABEL_93;
  }
  if ( (int)v43 < 0 )
  {
LABEL_93:
    if ( v78 < 0 )
      v78 = 0;
LABEL_95:
    if ( v79 < 0 )
      v79 = 0;
    if ( (int)v81 < (int)v42 )
      v42 = (unsigned int)v81;
    if ( SHIDWORD(v81) >= (int)v45 )
      goto LABEL_101;
    goto LABEL_100;
  }
  if ( (int)v81 < (int)v42 || v52 < 0 )
    goto LABEL_95;
  if ( SHIDWORD(v81) >= (int)v45 )
  {
    if ( !v48 )
      goto LABEL_43;
    goto LABEL_42;
  }
LABEL_100:
  v45 = HIDWORD(v81);
LABEL_101:
  if ( (int)v42 < v78 )
  {
    v78 = v42;
  }
  else if ( (int)v45 < v79 )
  {
    v79 = v45;
  }
  v110.left = v78;
  v110.top = v79;
  v110.right = v42;
  v110.bottom = v45;
  if ( v48 )
  {
    v83 = W32GetSessionState(v45, v42, v43, v48);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v83 + 88), v98);
  }
  PopThreadGuardedObject(&v96);
  RGNOBJ::vSet((RGNOBJ *)&v106, &v110);
LABEL_44:
  if ( v4 != 1 )
  {
    if ( v4 != 2 )
    {
      if ( v4 != 4 )
      {
        v55 = 0;
        goto LABEL_47;
      }
      v76 = v100;
      GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v100 + 1112));
      *(_QWORD *)&v110.left = v76;
      LOBYTE(v110.right) = 1;
      v55 = *((_QWORD *)v100 + 142);
      if ( v55 )
      {
        if ( v55 != *((_QWORD *)v15 + 533) )
        {
          v94 = *((_QWORD *)v100 + 142);
          RGNOBJAPI::bSwap((RGNOBJAPI *)&v106, (struct RGNOBJ *)&v94);
          v55 = v94;
          v77 = 0;
          goto LABEL_75;
        }
      }
      else
      {
        v55 = *((_QWORD *)v15 + 533);
      }
      v77 = 1;
      v95 = 0;
LABEL_75:
      _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v110);
      if ( !v77 )
        goto LABEL_48;
      goto LABEL_47;
    }
    sizeScan = REGION_CORE::get_sizeScan((REGION_CORE *)(v106 + 24));
    v94 = 0;
    RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v94, sizeScan, v88, v89);
    v55 = v94;
    if ( v94 )
    {
      if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
      {
        v90 = (const struct REGION_CORE *)(v94 + 24);
        v91 = *(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory;
        v92 = v106 + 24;
        if ( !v106 )
          v92 = 0;
        (*(void (__fastcall **)(const struct REGION_CORE *, __int64, __int64))(v91 + 48))(v90, v92, v106);
        RgnCaptureLiveMemoryDumpOnZeroSizedScan((unsigned int (__fastcall **)(const struct REGION_CORE *))v91, v90);
      }
      else
      {
        v94 += 24;
        v93 = v106 + 24;
        if ( !v106 )
          v93 = 0;
        v99 = v93;
        RGNCOREOBJ::vCopy((RGNCOREOBJ *)&v94, (const struct RGNCOREOBJ *)&v99);
      }
      goto LABEL_47;
    }
LABEL_66:
    v55 = *((_QWORD *)v15 + 533);
    goto LABEL_47;
  }
  v55 = v106;
  if ( (unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v106) )
  {
    v106 = 0;
LABEL_47:
    v58 = v100;
    v59 = v100;
    *((_DWORD *)v100 + 9) |= 0x10u;
    v60 = DC::PentryFromPobj(v59, v15);
    *((_BYTE *)v60 + 15) |= 4u;
    GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v58 + 1112));
    v99 = *((_QWORD *)v58 + 142);
    *(_QWORD *)&v110.left = v58;
    LOBYTE(v110.right) = 1;
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v99, v61, v62, v63);
    *((_QWORD *)v58 + 142) = *((_QWORD *)v15 + 533);
    _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v110);
LABEL_48:
    v64 = v100;
    GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v100 + 1112));
    *((_QWORD *)v100 + 142) = v55;
    *(_DWORD *)(v55 + 72) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(
                                                                                            v66,
                                                                                            v65,
                                                                                            v67,
                                                                                            v68)
                                                                                        + 88)
                                                                            + 4248LL));
    v69 = GreGetCurrentThreadCrossSessionCheck();
    if ( v69 )
      *(_QWORD *)v69 &= ~0x4000000000uLL;
    GrePushLock::ReleaseLock((DC *)((char *)v64 + 1112));
    v18 = v95;
    goto LABEL_51;
  }
  v18 = 0;
LABEL_51:
  if ( !v109 )
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v106);
  if ( v106 )
    _InterlockedDecrement16((volatile signed __int16 *)(v106 + 12));
  v70 = v107;
  if ( *(__int64 **)(v107 + 8) != &v107 )
    goto LABEL_5;
  v71 = v108;
  v72 = &v107;
  if ( *v108 != &v107 )
    goto LABEL_5;
  *v108 = (_QWORD *)v107;
  *(_QWORD *)(v70 + 8) = v71;
LABEL_58:
  if ( v16 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        (_DWORD)v71,
        (unsigned int)LockRelease,
        v56,
        (_DWORD)v16,
        (__int64)L"VisRgnPublish");
    GrepReleaseLockValidate<11>();
    GreReleaseSemaphoreSharedInternal(v16);
  }
  if ( v100 )
  {
    v73 = W32GetSessionState(v71, v72, v56, v57);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v73 + 88), v100);
    v100 = 0;
  }
  v74 = v104;
  if ( *(__int128 **)(v104 + 8) != &v104 )
    goto LABEL_5;
  v75 = *((_QWORD *)&v104 + 1);
  if ( **((__int128 ***)&v104 + 1) != &v104 )
    goto LABEL_5;
  **((_QWORD **)&v104 + 1) = v104;
  result = v18;
  *(_QWORD *)(v74 + 8) = v75;
  return result;
}

```

## disassembly

```asm
0x14002eef0  mov     [rsp-8+arg_10], rbx
0x14002eef5  push    rbp
0x14002eef6  push    rsi
0x14002eef7  push    rdi
0x14002eef8  push    r12
0x14002eefa  push    r13
0x14002eefc  push    r14
0x14002eefe  push    r15
0x14002ef00  lea     rbp, [rsp-27h]
0x14002ef05  sub     rsp, 100h
0x14002ef0c  mov     rax, cs:__security_cookie
0x14002ef13  xor     rax, rsp
0x14002ef16  mov     [rbp+57h+var_38], rax
0x14002ef1a  xor     r14d, r14d
0x14002ef1d  mov     dword ptr [rsp+130h+var_100], r8d
0x14002ef22  mov     [rbp+57h+var_C0], r14
0x14002ef26  mov     r13d, r8d
0x14002ef29  mov     [rbp+57h+var_B8], r14d
0x14002ef2d  mov     rdi, rdx
0x14002ef30  mov     rbx, rcx
0x14002ef33  call    cs:__imp_W32GetSessionState
0x14002ef3a  nop     dword ptr [rax+rax+00h]
0x14002ef3f  xorps   xmm0, xmm0
0x14002ef42  mov     rcx, [rax+58h]
0x14002ef46  mov     [rbp+57h+var_B0], rcx
0x14002ef4a  mov     [rbp+57h+var_A8], r14
0x14002ef4e  mov     [rbp+57h+var_C0], r14
0x14002ef52  mov     [rbp+57h+var_B8], r14d
0x14002ef56  movups  [rbp+57h+var_A0], xmm0
0x14002ef5a  movups  [rbp+57h+var_90], xmm0
0x14002ef5e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002ef65  nop     dword ptr [rax+rax+00h]
0x14002ef6a  test    rax, rax
0x14002ef6d  jz      loc_14002F6FD
0x14002ef73  mov     rax, [rax]
0x14002ef76  test    rax, rax
0x14002ef79  jz      loc_14002F6FD
0x14002ef7f  lea     rcx, [rbp+57h+var_C0]
0x14002ef83  mov     qword ptr [rbp+57h+var_90], rcx
0x14002ef87  lea     rcx, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x14002ef8e  mov     qword ptr [rbp+57h+var_90+8], rcx
0x14002ef92  add     rax, 8
0x14002ef96  jz      loc_14002F710
0x14002ef9c  mov     rcx, [rax+58h]
0x14002efa0  add     rax, 58h ; 'X'
0x14002efa4  cmp     [rcx+8], rax
0x14002efa8  jz      short loc_14002EFB1
0x14002efaa  mov     ecx, 3
0x14002efaf  int     29h; Win8: RtlFailFast(ecx)
0x14002efb1  mov     qword ptr [rbp+57h+var_A0], rcx
0x14002efb5  lea     rdx, [rbp+57h+var_A0]
0x14002efb9  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14002efbd  mov     [rcx+8], rdx
0x14002efc1  lea     rcx, [rbp+57h+var_A0]
0x14002efc5  mov     [rax], rcx
0x14002efc8  mov     rcx, [rbp+57h+var_B0]
0x14002efcc  mov     esi, 1
0x14002efd1  mov     r9d, esi
0x14002efd4  movzx   r8d, sil
0x14002efd8  mov     rdx, rbx
0x14002efdb  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14002efe0  mov     [rbp+57h+var_C0], rax
0x14002efe4  test    rax, rax
0x14002efe7  jnz     short loc_14002F035
0x14002efe9  mov     rax, qword ptr [rbp+57h+var_A0]
0x14002efed  lea     rcx, [rbp+57h+var_A0]
0x14002eff1  cmp     [rax+8], rcx
0x14002eff5  jnz     short loc_14002EFAA
0x14002eff7  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x14002effb  lea     rdx, [rbp+57h+var_A0]
0x14002efff  cmp     [rcx], rdx
0x14002f002  jnz     short loc_14002EFAA
0x14002f004  mov     [rcx], rax
0x14002f007  mov     [rax+8], rcx
0x14002f00b  xor     eax, eax
0x14002f00d  mov     rcx, [rbp+57h+var_38]
0x14002f011  xor     rcx, rsp; StackCookie
0x14002f014  call    __security_check_cookie
0x14002f019  mov     rbx, [rsp+130h+arg_10]
0x14002f021  add     rsp, 100h
0x14002f028  pop     r15
0x14002f02a  pop     r14
0x14002f02c  pop     r13
0x14002f02e  pop     r12
0x14002f030  pop     rdi
0x14002f031  pop     rsi
0x14002f032  pop     rbp
0x14002f033  retn
0x14002f035  mov     r15, [rbp+57h+var_B0]
0x14002f039  mov     r12, [r15]
0x14002f03c  add     r12, 4E0h
0x14002f043  mov     rcx, r12; Resource
0x14002f046  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14002f04b  call    ??$GrepAcquireLockValidate@$0L@@@YAXXZ; GrepAcquireLockValidate<11>(void)
0x14002f050  mov     rcx, [rbp+57h+var_C0]; this
0x14002f054  mov     ebx, esi
0x14002f056  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x14002f059  mov     [rsp+130h+var_F8], ebx
0x14002f05d  or      dword ptr [rcx+24h], 10h
0x14002f061  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x14002f066  or      byte ptr [rax+0Fh], 4
0x14002f06a  test    rdi, rdi
0x14002f06d  jz      loc_14002F66C
0x14002f073  call    cs:__imp_PsGetCurrentProcessId
0x14002f07a  nop     dword ptr [rax+rax+00h]
0x14002f07f  call    cs:__imp_W32GetSessionState
0x14002f086  nop     dword ptr [rax+rax+00h]
0x14002f08b  mov     r14, [rax+58h]
0x14002f08f  mov     rdx, [r14]
0x14002f092  add     rdx, 5E8h
0x14002f099  mov     [rbp+57h+var_C8], rdx
0x14002f09d  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14002f0a2  mov     r9d, esi
0x14002f0a5  lea     rcx, [rsp+130h+var_F0]
0x14002f0aa  mov     r8, rdi
0x14002f0ad  mov     rdx, r14
0x14002f0b0  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x14002f0b5  cmp     dword ptr [rsp+130h+var_F0+8], 0
0x14002f0ba  jz      short loc_14002F130
0x14002f0bc  mov     rbx, qword ptr [rsp+130h+var_F0]
0x14002f0c1  cmp     byte ptr [rbx+0Eh], 4
0x14002f0c5  jnz     loc_14002F803
0x14002f0cb  movzx   eax, byte ptr [rbx+0Ch]
0x14002f0cf  movzx   ecx, byte ptr [rbx+0Dh]
0x14002f0d3  shl     cx, 8
0x14002f0d7  or      cx, ax
0x14002f0da  mov     eax, edi
0x14002f0dc  shr     eax, 10h
0x14002f0df  cmp     cx, ax
0x14002f0e2  jnz     loc_14002F803
0x14002f0e8  mov     rax, qword ptr [rsp+130h+var_E0]
0x14002f0ed  mov     edx, [rbx]
0x14002f0ef  mov     rcx, [rax+8]
0x14002f0f3  mov     rax, [rcx]
0x14002f0f6  mov     rax, [rax+60h]
0x14002f0fa  call    _guard_dispatch_icall
0x14002f0ff  mov     r13, rax
0x14002f102  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x14002f107  movzx   ecx, word ptr [r13+0Ch]
0x14002f10c  test    cx, cx
0x14002f10f  jnz     loc_14002F7EB
0x14002f115  mov     ebx, [rbx+8]
0x14002f118  and     ebx, 0FFFFFFFEh
0x14002f11b  jnz     loc_14002F49F
0x14002f121  mov     r13d, dword ptr [rsp+130h+var_100]
0x14002f126  lea     rcx, [rsp+130h+var_F0]; this
0x14002f12b  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14002f130  lea     rcx, [rsp+130h+var_F0]; this
0x14002f135  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x14002f13a  lea     rcx, [rbp+57h+var_C8]
0x14002f13e  call    ?vUnlock@?$SEMOBJ@$0BE@@@QEAAXXZ; SEMOBJ<20>::vUnlock(void)
0x14002f143  xor     r9d, r9d; int
0x14002f146  lea     rcx, [rbp+57h+var_80]; this
0x14002f14a  xor     r8d, r8d; int
0x14002f14d  mov     rdx, rdi; HRGN
0x14002f150  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14002f155  cmp     [rbp+57h+var_80], 0
0x14002f15a  jz      loc_14002F493
0x14002f160  mov     rax, [rbp+57h+var_C0]
0x14002f164  mov     rbx, [rax]
0x14002f167  call    cs:__imp_W32GetSessionState
0x14002f16e  nop     dword ptr [rax+rax+00h]
0x14002f173  mov     edx, ebx
0x14002f175  shr     edx, 8
0x14002f178  and     edx, 0FF0000h
0x14002f17e  mov     rcx, [rax+58h]
0x14002f182  movzx   eax, bx
0x14002f185  or      edx, eax
0x14002f187  mov     rcx, [rcx+8]
0x14002f18b  mov     r8, [rcx]
0x14002f18e  mov     rax, [r8+10h]
0x14002f192  call    _guard_dispatch_icall
0x14002f197  test    rax, rax
0x14002f19a  jz      short loc_14002F1CA
0x14002f19c  cmp     [rax+0Eh], sil
0x14002f1a0  jnz     short loc_14002F1CA
0x14002f1a2  movzx   edx, byte ptr [rax+0Dh]
0x14002f1a6  movzx   ecx, byte ptr [rax+0Ch]
0x14002f1aa  shl     dx, 8
0x14002f1ae  or      dx, cx
0x14002f1b1  shr     ebx, 10h
0x14002f1b4  cmp     dx, bx
0x14002f1b7  jnz     short loc_14002F1CA
0x14002f1b9  mov     eax, [rax+8]
0x14002f1bc  and     eax, 0FFFFFFFEh
0x14002f1bf  cmp     eax, 80000012h
0x14002f1c4  jz      loc_14002F2F9
0x14002f1ca  mov     rbx, [rbp+57h+var_C0]
0x14002f1ce  test    dword ptr [rbx+24h], 100000h
0x14002f1d5  jz      loc_14002F2F9
0x14002f1db  mov     r14, [rbx+30h]
0x14002f1df  test    r14, r14
0x14002f1e2  jz      loc_14002F2F9
0x14002f1e8  mov     rdi, [rbp+57h+var_80]
0x14002f1ec  test    rdi, rdi
0x14002f1ef  jz      loc_14002F2F9
0x14002f1f5  xorps   xmm0, xmm0
0x14002f1f8  movups  [rsp+130h+var_F0], xmm0
0x14002f1fd  movups  [rsp+130h+var_E0], xmm0
0x14002f202  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002f209  nop     dword ptr [rax+rax+00h]
0x14002f20e  test    rax, rax
0x14002f211  jz      loc_14002F781
0x14002f217  mov     rcx, [rax]
0x14002f21a  test    rcx, rcx
0x14002f21d  jz      loc_14002F781
0x14002f223  lea     rax, [rcx+8]
0x14002f227  lea     rcx, [rsp+130h+var_F0]
0x14002f22c  mov     qword ptr [rsp+130h+var_E0], rcx
0x14002f231  lea     rcx, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14002f238  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x14002f23d  test    rax, rax
0x14002f240  jz      loc_14002F797
0x14002f246  mov     rcx, [rax+58h]
0x14002f24a  add     rax, 58h ; 'X'
0x14002f24e  cmp     [rcx+8], rax
0x14002f252  jnz     loc_14002EFAA
0x14002f258  mov     qword ptr [rsp+130h+var_F0], rcx
0x14002f25d  lea     rdx, [rsp+130h+var_F0]
0x14002f262  mov     qword ptr [rsp+130h+var_F0+8], rax
0x14002f267  mov     [rcx+8], rdx
0x14002f26b  lea     rcx, [rsp+130h+var_F0]
0x14002f270  mov     [rax], rcx
0x14002f273  xor     r9d, r9d
0x14002f276  test    dword ptr [rbx+24h], 40000h
0x14002f27d  mov     [rbp+57h+var_D0], r9
0x14002f281  jnz     loc_14002F7B8
0x14002f287  mov     r11, [rbx+1F0h]
0x14002f28e  xor     eax, eax
0x14002f290  test    r11, r11
0x14002f293  jz      short loc_14002F2D1
0x14002f295  test    dword ptr [r14+28h], 20000h
0x14002f29d  jnz     loc_14002F63F
0x14002f2a3  mov     eax, [rbx+24h]
0x14002f2a6  bt      eax, 0Ch
0x14002f2aa  jb      loc_14002F80D
0x14002f2b0  mov     r8d, [rdi+34h]
0x14002f2b4  mov     edx, [rdi+3Ch]
0x14002f2b7  cmp     r8d, edx
0x14002f2ba  jz      short loc_14002F2CC
0x14002f2bc  mov     r10d, [rdi+38h]
0x14002f2c0  mov     ecx, [rdi+40h]
0x14002f2c3  cmp     r10d, ecx
0x14002f2c6  jnz     loc_14002F55B
0x14002f2cc  test    r9, r9
0x14002f2cf  jmp     short loc_14002F2D4
0x14002f2d1  test    rax, rax
0x14002f2d4  jz      short loc_14002F2EF
0x14002f2d6  call    cs:__imp_W32GetSessionState
0x14002f2dd  nop     dword ptr [rax+rax+00h]
0x14002f2e2  mov     rdx, [rbp+57h+var_D0]
0x14002f2e6  mov     rcx, [rax+58h]
0x14002f2ea  call    HmgDecrementShareReferenceCount
0x14002f2ef  lea     rcx, [rsp+130h+var_F0]
0x14002f2f4  call    PopThreadGuardedObject
0x14002f2f9  cmp     r13d, esi
0x14002f2fc  jnz     loc_14002F4DE
0x14002f302  mov     r14, [rbp+57h+var_80]
0x14002f306  lea     rcx, [rbp+57h+var_80]; this
0x14002f30a  call    ?bDeleteHandle@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteHandle(void)
0x14002f30f  test    eax, eax
0x14002f311  jz      loc_14002F4D3
0x14002f317  mov     [rbp+57h+var_80], 0
0x14002f31f  mov     rbx, [rbp+57h+var_C0]
0x14002f323  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x14002f326  mov     rcx, rbx; this
0x14002f329  or      dword ptr [rbx+24h], 10h
0x14002f32d  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x14002f332  lea     rcx, [rbx+458h]; this
0x14002f339  or      byte ptr [rax+0Fh], 4
0x14002f33d  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x14002f342  mov     rax, [rbx+470h]
0x14002f349  lea     rcx, [rbp+57h+var_C8]; this
0x14002f34d  mov     [rbp+57h+var_C8], rax
0x14002f351  mov     qword ptr [rbp+57h+var_48.left], rbx
0x14002f355  mov     byte ptr [rbp+57h+var_48.right], sil
0x14002f359  call    ?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14002f35e  mov     rax, [r15+10A8h]
0x14002f365  lea     rcx, [rbp+57h+var_48]
0x14002f369  mov     [rbx+470h], rax
0x14002f370  call    ?reset@?$lambda_call@V_lambda_1_@?1??AcquireDcVisRgnExclusive@DC@@QEAA@XZ@@details@wil@@QEAAXXZ; wil::details::lambda_call<`DC::AcquireDcVisRgnExclusive(void)'::`2'::_lambda_1_>::reset(void)
0x14002f375  mov     rbx, [rbp+57h+var_C0]
0x14002f379  lea     rcx, [rbx+458h]; this
0x14002f380  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x14002f385  mov     rax, [rbp+57h+var_C0]
0x14002f389  mov     [rax+470h], r14
0x14002f390  call    cs:__imp_W32GetSessionState
0x14002f397  nop     dword ptr [rax+rax+00h]
0x14002f39c  mov     rdx, [rax+58h]
0x14002f3a0  lock xadd [rdx+1098h], esi
0x14002f3a8  inc     esi
0x14002f3aa  mov     [r14+48h], esi
0x14002f3ae  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14002f3b3  test    rax, rax
0x14002f3b6  jz      short loc_14002F3C5
0x14002f3b8  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x14002f3c2  and     [rax], rcx
0x14002f3c5  lea     rcx, [rbx+458h]; this
0x14002f3cc  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x14002f3d1  mov     ebx, [rsp+130h+var_F8]
  ... truncated ...
```
