# GreSelectVisRgn

- ea: `0x14002e5a0`
- end: `0x14002eee3`
- name: `GreSelectVisRgn`
- size: `2371`
- prototype: `__int64 __fastcall(__int64, HRGN, __int64, __int64)`
- caller_count: `3`
- callee_count: `38`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140038210`
- `0x140038e7c`
- `0x140039b30`

## callees

- `0x1400260d0`
- `0x140026cc8`
- `0x14002a1d0`
- `0x14002cca4`
- `0x14002d310`
- `0x14002de30`
- `0x14002e5a0`
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

- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e6d3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e6d3`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002e60a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002e860`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002e60a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002e860`
- `WIN32K!W32GetSessionState` at `0x14002e5df`
- `WIN32K!W32GetSessionState` at `0x14002e6df`
- `WIN32K!W32GetSessionState` at `0x14002e7c5`
- `WIN32K!W32GetSessionState` at `0x14002e931`
- `WIN32K!W32GetSessionState` at `0x14002e9f2`
- `WIN32K!W32GetSessionState` at `0x14002eaa3`
- `WIN32K!W32GetSessionState` at `0x14002eccb`
- `WIN32K!W32GetSessionState` at `0x14002e5df`
- `WIN32K!W32GetSessionState` at `0x14002e6df`
- `WIN32K!W32GetSessionState` at `0x14002e7c5`
- `WIN32K!W32GetSessionState` at `0x14002e931`
- `WIN32K!W32GetSessionState` at `0x14002e9f2`
- `WIN32K!W32GetSessionState` at `0x14002eaa3`
- `WIN32K!W32GetSessionState` at `0x14002eccb`

## pseudocode

```c
__int64 __fastcall GreSelectVisRgn(__int64 a1, HRGN a2, __int64 a3, __int64 a4)
{
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  struct Gre::Base::SESSION_GLOBALS *v11; // r15
  HSEMAPHORE v12; // r13
  DC *v13; // rcx
  unsigned int v14; // r12d
  struct _ENTRY *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  _QWORD *v20; // r14
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rbx
  __int64 v24; // rdi
  unsigned int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rbx
  __int64 SessionState; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  DC *v34; // rbx
  __int64 v35; // rsi
  unsigned int *v36; // rdi
  __int64 *v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 v41; // rdx
  _QWORD *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // r11
  __int64 v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  int v48; // r10d
  bool v49; // zf
  __int64 v50; // rax
  int v51; // ebx
  int v52; // edi
  __int64 v53; // rsi
  __int64 v54; // r8
  __int64 v55; // r9
  DC *v56; // rbx
  DC *v57; // rcx
  struct _ENTRY *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  DC *v62; // rbx
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // r9
  struct _GRETHREAD *v67; // rax
  __int64 v68; // rax
  _QWORD **v69; // rcx
  __int64 *v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 result; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  DC *v77; // rbx
  __int64 *v78; // rax
  int v79; // esi
  LONG v80; // ebx
  __int64 v81; // rax
  bool v82; // cc
  __int64 v83; // r9
  __int64 v84; // rax
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // r9
  unsigned int sizeScan; // eax
  __int64 v89; // r8
  __int64 v90; // r9
  unsigned int (__fastcall **v91)(const struct REGION_CORE *); // rbx
  const struct REGION_CORE *v92; // rdi
  __int64 v93; // [rsp+30h] [rbp-A9h] BYREF
  __int128 v94; // [rsp+38h] [rbp-A1h] BYREF
  __int128 v95; // [rsp+48h] [rbp-91h]
  __int64 v96; // [rsp+58h] [rbp-81h]
  DC *v97; // [rsp+60h] [rbp-79h] BYREF
  int v98; // [rsp+68h] [rbp-71h]
  struct Gre::Base::SESSION_GLOBALS *v99; // [rsp+70h] [rbp-69h]
  __int64 v100; // [rsp+78h] [rbp-61h]
  __int128 v101; // [rsp+80h] [rbp-59h] BYREF
  __int128 v102; // [rsp+90h] [rbp-49h]
  __int64 v103; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v104; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v105; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD **v106; // [rsp+B8h] [rbp-21h]
  int v107; // [rsp+D8h] [rbp-1h]
  struct _RECTL v108; // [rsp+E0h] [rbp+7h] BYREF

  LODWORD(v103) = a3;
  v97 = 0;
  v98 = 0;
  v99 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(a1, a2, a3, a4) + 88);
  v100 = 0;
  v97 = 0;
  v98 = 0;
  v101 = 0;
  v102 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v99);
  if ( CurrentThreadWin32Thread )
    v8 = *CurrentThreadWin32Thread;
  else
    v8 = 0;
  v9 = (v8 + 8) & -(__int64)(v8 != 0);
  *(_QWORD *)&v102 = &v97;
  *((_QWORD *)&v102 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  if ( v9 )
  {
    v10 = *(_QWORD *)(((v8 + 8) & -(__int64)(v8 != 0)) + 0x58);
    if ( *(_QWORD *)(v10 + 8) != v9 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v101 = *(_QWORD *)(v9 + 88);
    *((_QWORD *)&v101 + 1) = v9 + 88;
    *(_QWORD *)(v10 + 8) = &v101;
    *(_QWORD *)(v9 + 88) = &v101;
  }
  else
  {
    *((_QWORD *)&v101 + 1) = &v101;
    *(_QWORD *)&v101 = &v101;
  }
  LOBYTE(v7) = 1;
  v97 = (DC *)HmgShareLock(v99, a1, v7, 1);
  if ( v97 )
  {
    v11 = v99;
    v12 = (HSEMAPHORE)(*(_QWORD *)v99 + 1248LL);
    GreAcquireSemaphoreInternal(v12);
    GrepAcquireLockValidate<11>();
    v13 = v97;
    v14 = 1;
    *((_DWORD *)v97 + 9) |= 0x10u;
    v15 = DC::PentryFromPobj(v13, v11);
    *((_BYTE *)v15 + 15) |= 4u;
    if ( !a2 )
    {
      DC::vReleaseVis(v97, v11);
      DC::bSetDefaultRegion(v97, v85, v86, v87);
      goto LABEL_54;
    }
    PsGetCurrentProcessId();
    v20 = *(_QWORD **)(W32GetSessionState(v17, v16, v18, v19) + 88);
    v93 = *v20 + 1512LL;
    GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v21, v93, v22);
    HANDLELOCK::HANDLELOCK(&v94, v20, a2, 1);
    if ( DWORD2(v94) )
    {
      v23 = v94;
      if ( *(_BYTE *)(v94 + 14) == 4
        && *(_WORD *)(v94 + 12) == WORD1(a2)
        && ((v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v95 + 8) + 96LL))(
                     *(_QWORD *)(v95 + 8),
                     *(unsigned int *)v94),
             GreGetCurrentThread(),
             !*(_WORD *)(v24 + 12))
         || *(struct _KTHREAD **)(v24 + 16) == KeGetCurrentThread()) )
      {
        v25 = *(_DWORD *)(v23 + 8) & 0xFFFFFFFE;
        if ( v25 && (unsigned int)HmgIncProcessHandleCount(0) )
        {
          HmgDecProcessHandleCount(v20, v25);
          HANDLELOCK::Pid((HANDLELOCK *)&v94, 0);
          *(_WORD *)(v24 + 14) &= ~0x10u;
        }
      }
      else
      {
        BYTE13(v94) = 1;
      }
      HANDLELOCK::vUnlock((HANDLELOCK *)&v94);
    }
    HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v94);
    SEMOBJ<20>::vUnlock(&v93);
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v104, a2, 0, 0);
    if ( !v104 )
      goto LABEL_65;
    v30 = *(_QWORD *)v97;
    SessionState = W32GetSessionState(v27, v26, v28, v29);
    v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(SessionState + 88) + 8LL) + 16LL))(
            *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 8LL),
            (unsigned __int16)v30 | ((unsigned int)v30 >> 8) & 0xFF0000);
    if ( v32
      && *(_BYTE *)(v32 + 14) == 1
      && (v33 = *(unsigned __int8 *)(v32 + 12), *(_WORD *)(v32 + 12) == WORD1(v30))
      && (*(_DWORD *)(v32 + 8) & 0xFFFFFFFE) == 0x80000012
      || (v34 = v97, (*((_DWORD *)v97 + 9) & 0x100000) == 0)
      || (v35 = *((_QWORD *)v97 + 6)) == 0
      || (v36 = (unsigned int *)v104) == 0 )
    {
LABEL_40:
      v51 = v103;
      v52 = 1;
      if ( (_DWORD)v103 == 1 )
      {
        v53 = v104;
        if ( (unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v104) )
        {
          v104 = 0;
          goto LABEL_43;
        }
        v14 = 0;
LABEL_71:
        if ( !v14 && v51 == 1 )
        {
LABEL_47:
          if ( !v107 )
            RGNOBJ::UpdateUserRgn((RGNOBJ *)&v104);
          if ( v104 )
            _InterlockedDecrement16((volatile signed __int16 *)(v104 + 12));
          v68 = v105;
          if ( *(__int64 **)(v105 + 8) != &v105 )
            goto LABEL_5;
          v69 = v106;
          v70 = &v105;
          if ( *v106 != &v105 )
            goto LABEL_5;
          *v106 = (_QWORD *)v105;
          *(_QWORD *)(v68 + 8) = v69;
LABEL_54:
          if ( v12 )
          {
            if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
              McTemplateK0pz_EtwWriteTransfer(
                (_DWORD)v69,
                (unsigned int)LockRelease,
                v54,
                (_DWORD)v12,
                (__int64)L"VisRgnPublish");
            GrepReleaseLockValidate<11>();
            GreReleaseSemaphoreSharedInternal(v12);
          }
          if ( v97 )
          {
            v71 = W32GetSessionState(v69, v70, v54, v55);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v71 + 88), v97);
            v97 = 0;
          }
          v72 = v101;
          if ( *(__int128 **)(v101 + 8) == &v101 )
          {
            v73 = *((_QWORD *)&v101 + 1);
            if ( **((__int128 ***)&v101 + 1) == &v101 )
            {
              **((_QWORD **)&v101 + 1) = v101;
              result = v14;
              *(_QWORD *)(v72 + 8) = v73;
              return result;
            }
          }
LABEL_5:
          __fastfail(3u);
        }
        if ( !v52 )
        {
LABEL_44:
          v62 = v97;
          GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v97 + 1112));
          *((_QWORD *)v97 + 142) = v53;
          *(_DWORD *)(v53 + 72) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(
                                                                                                  v64,
                                                                                                  v63,
                                                                                                  v65,
                                                                                                  v66)
                                                                                              + 88)
                                                                                  + 4248LL));
          v67 = GreGetCurrentThreadCrossSessionCheck();
          if ( v67 )
            *(_QWORD *)v67 &= ~0x4000000000uLL;
          GrePushLock::ReleaseLock((DC *)((char *)v62 + 1112));
          goto LABEL_47;
        }
LABEL_43:
        v56 = v97;
        v57 = v97;
        *((_DWORD *)v97 + 9) |= 0x10u;
        v58 = DC::PentryFromPobj(v57, v11);
        *((_BYTE *)v58 + 15) |= 4u;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v56 + 1112));
        v93 = *((_QWORD *)v56 + 142);
        *(_QWORD *)&v108.left = v56;
        LOBYTE(v108.right) = 1;
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v93, v59, v60, v61);
        *((_QWORD *)v56 + 142) = *((_QWORD *)v11 + 533);
        _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v108);
        goto LABEL_44;
      }
      if ( (_DWORD)v103 != 2 )
      {
        if ( (_DWORD)v103 != 4 )
        {
          v53 = 0;
          goto LABEL_43;
        }
        v77 = v97;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v97 + 1112));
        *(_QWORD *)&v108.left = v77;
        LOBYTE(v108.right) = 1;
        v53 = *((_QWORD *)v97 + 142);
        if ( v53 )
        {
          if ( v53 != *((_QWORD *)v11 + 533) )
          {
            v93 = *((_QWORD *)v97 + 142);
            RGNOBJAPI::bSwap((RGNOBJAPI *)&v104, (struct RGNOBJ *)&v93);
            v53 = v93;
            v52 = 0;
LABEL_80:
            _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v108);
            v51 = v103;
            goto LABEL_71;
          }
        }
        else
        {
          v53 = *((_QWORD *)v11 + 533);
        }
        v14 = 0;
        goto LABEL_80;
      }
      sizeScan = REGION_CORE::get_sizeScan((REGION_CORE *)(v104 + 24));
      v93 = 0;
      RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v93, sizeScan, v89, v90);
      v53 = v93;
      if ( v93 )
      {
        if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
        {
          v91 = *(unsigned int (__fastcall ***)(const struct REGION_CORE *))WPP_MAIN_CB.Dpc.ProcessorHistory;
          v92 = (const struct REGION_CORE *)((v93 + 24) & -(__int64)(v93 != 0));
          (*(void (__fastcall **)(const struct REGION_CORE *, __int64, __int64))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory
                                                                               + 48LL))(
            v92,
            (v104 + 24) & -(__int64)(v104 != 0),
            -v104);
          RgnCaptureLiveMemoryDumpOnZeroSizedScan(v91, v92);
        }
        else
        {
          v103 = (v93 + 24) & -(__int64)(v93 != 0);
          v93 = (v104 + 24) & -(__int64)(v104 != 0);
          RGNCOREOBJ::vCopy((RGNCOREOBJ *)&v103, (const struct RGNCOREOBJ *)&v93);
        }
        goto LABEL_43;
      }
LABEL_65:
      v53 = *((_QWORD *)v11 + 533);
      goto LABEL_43;
    }
    v94 = 0;
    v95 = 0;
    v37 = (__int64 *)PsGetCurrentThreadWin32Thread(v33);
    if ( v37 )
      v40 = *v37;
    else
      v40 = 0;
    v41 = (v40 + 8) & -(__int64)(v40 != 0);
    *(_QWORD *)&v95 = &v94;
    *((_QWORD *)&v95 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    if ( v41 )
    {
      v42 = (_QWORD *)(v41 + 88);
      v43 = *(_QWORD *)(((v40 + 8) & -(__int64)(v40 != 0)) + 0x58);
      if ( *(_QWORD *)(v43 + 8) != v41 + 88 )
        goto LABEL_5;
      *(_QWORD *)&v94 = *(_QWORD *)(v41 + 88);
      v41 = (__int64)&v94;
      *((_QWORD *)&v94 + 1) = v42;
      *(_QWORD *)(v43 + 8) = &v94;
      *v42 = &v94;
    }
    else
    {
      *((_QWORD *)&v94 + 1) = &v94;
      *(_QWORD *)&v94 = &v94;
    }
    v49 = (*((_DWORD *)v34 + 9) & 0x40000) == 0;
    v44 = 0;
    v96 = 0;
    if ( v49 )
    {
      v45 = *((_QWORD *)v34 + 62);
    }
    else
    {
      v41 = *((_QWORD *)v34 + 268);
      if ( v41 )
      {
        SURFREF::vLock((SURFREF *)&v94, (HSURF)v41);
        v44 = v96;
        v45 = v96;
        v46 = v96;
LABEL_31:
        if ( !v45 )
        {
          v49 = v46 == 0;
          goto LABEL_37;
        }
        if ( (*(_DWORD *)(v35 + 40) & 0x20000) != 0 && *(int *)(v45 + 144) < 0
          || (v47 = *((_DWORD *)v34 + 9), (v47 & 0x1000) != 0) && (v47 & 0x4000) == 0
          || (v39 = v36[13], v38 = v36[15], (_DWORD)v39 == (_DWORD)v38)
          || (v48 = v36[14], v41 = v36[16], v48 == (_DWORD)v41)
          || (_DWORD)v39 == 0x7FFFFFFF && (_DWORD)v41 == 0x80000000 && v48 == 0x7FFFFFFF && (_DWORD)v38 == 0x80000000 )
        {
LABEL_36:
          v49 = v44 == 0;
LABEL_37:
          if ( !v49 )
          {
            v50 = W32GetSessionState(v45, v41, v38, v39);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v50 + 88), v96);
          }
          PopThreadGuardedObject(&v94);
          goto LABEL_40;
        }
        v78 = (__int64 *)(v45 + 700);
        v79 = v36[13];
        v80 = v36[14];
        if ( (*(_DWORD *)(v45 + 148) & 0x800) == 0 )
          v78 = (__int64 *)(v45 + 56);
        v81 = *v78;
        if ( (int)v39 >= (int)v38 )
        {
          if ( (int)v39 > (int)v38 )
          {
            v79 = v36[15];
            v38 = (unsigned int)v39;
          }
          v82 = v48 <= (int)v41;
        }
        else
        {
          v82 = v48 <= (int)v41;
          if ( v48 < (int)v41 )
          {
            if ( (int)v39 >= 0 && (int)v81 >= (int)v38 && v48 >= 0 && SHIDWORD(v81) >= (int)v41 )
              goto LABEL_36;
LABEL_96:
            v83 = 0;
            if ( v79 >= 0 )
              v83 = (unsigned int)v79;
            if ( v80 < 0 )
              v80 = 0;
            if ( (int)v81 < (int)v38 )
              v38 = (unsigned int)v81;
            if ( SHIDWORD(v81) < (int)v41 )
              v41 = HIDWORD(v81);
            if ( (int)v38 < (int)v83 )
            {
              v83 = (unsigned int)v38;
            }
            else if ( (int)v41 < v80 )
            {
              v80 = v41;
            }
            v108.left = v83;
            v108.top = v80;
            v108.right = v38;
            v108.bottom = v41;
            if ( v44 )
            {
              v84 = W32GetSessionState(v45, v41, v38, v83);
              HmgDecrementShareReferenceCount(*(_QWORD *)(v84 + 88), v96);
            }
            PopThreadGuardedObject(&v94);
            RGNOBJ::vSet((RGNOBJ *)&v104, &v108);
            goto LABEL_40;
          }
        }
        if ( !v82 )
        {
          v80 = v36[16];
          v41 = (unsigned int)v48;
        }
        goto LABEL_96;
      }
      v45 = *(_QWORD *)(v35 + 2544);
    }
    v46 = 0;
    goto LABEL_31;
  }
  v75 = v101;
  if ( *(__int128 **)(v101 + 8) != &v101 )
    goto LABEL_5;
  v76 = *((_QWORD *)&v101 + 1);
  if ( **((__int128 ***)&v101 + 1) != &v101 )
    goto LABEL_5;
  **((_QWORD **)&v101 + 1) = v101;
  *(_QWORD *)(v75 + 8) = v76;
  return 0;
}

```

## disassembly

```asm
0x14002e5a0  mov     [rsp-8+arg_10], rbx
0x14002e5a5  push    rbp
0x14002e5a6  push    rsi
0x14002e5a7  push    rdi
0x14002e5a8  push    r12
0x14002e5aa  push    r13
0x14002e5ac  push    r14
0x14002e5ae  push    r15
0x14002e5b0  lea     rbp, [rsp-27h]
0x14002e5b5  sub     rsp, 100h
0x14002e5bc  mov     rax, cs:__security_cookie
0x14002e5c3  xor     rax, rsp
0x14002e5c6  mov     [rbp+57h+var_40], rax
0x14002e5ca  xor     r14d, r14d
0x14002e5cd  mov     dword ptr [rbp+57h+var_90], r8d
0x14002e5d1  mov     [rbp+57h+var_D0], r14
0x14002e5d5  mov     rsi, rdx
0x14002e5d8  mov     [rbp+57h+var_C8], r14d
0x14002e5dc  mov     rbx, rcx
0x14002e5df  call    cs:__imp_W32GetSessionState
0x14002e5e6  nop     dword ptr [rax+rax+00h]
0x14002e5eb  xorps   xmm0, xmm0
0x14002e5ee  mov     rcx, [rax+58h]
0x14002e5f2  mov     [rbp+57h+var_C0], rcx
0x14002e5f6  mov     [rbp+57h+var_B8], r14
0x14002e5fa  mov     [rbp+57h+var_D0], r14
0x14002e5fe  mov     [rbp+57h+var_C8], r14d
0x14002e602  movups  [rbp+57h+var_B0], xmm0
0x14002e606  movups  [rbp+57h+var_A0], xmm0
0x14002e60a  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002e611  nop     dword ptr [rax+rax+00h]
0x14002e616  test    rax, rax
0x14002e619  jz      loc_14002EE17
0x14002e61f  mov     rcx, [rax]
0x14002e622  lea     rax, [rcx+8]
0x14002e626  neg     rcx
0x14002e629  sbb     rdx, rdx
0x14002e62c  and     rdx, rax
0x14002e62f  lea     rax, [rbp+57h+var_D0]
0x14002e633  mov     qword ptr [rbp+57h+var_A0], rax
0x14002e637  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x14002e63e  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14002e642  jz      loc_14002EE47
0x14002e648  lea     rax, [rdx+58h]
0x14002e64c  mov     rcx, [rax]
0x14002e64f  cmp     [rcx+8], rax
0x14002e653  jz      short loc_14002E65C
0x14002e655  mov     ecx, 3
0x14002e65a  int     29h; Win8: RtlFailFast(ecx)
0x14002e65c  mov     qword ptr [rbp+57h+var_B0], rcx
0x14002e660  lea     rdx, [rbp+57h+var_B0]
0x14002e664  mov     qword ptr [rbp+57h+var_B0+8], rax
0x14002e668  mov     [rcx+8], rdx
0x14002e66c  lea     rcx, [rbp+57h+var_B0]
0x14002e670  mov     [rax], rcx
0x14002e673  mov     rcx, [rbp+57h+var_C0]
0x14002e677  mov     r9d, 1
0x14002e67d  mov     r8b, r9b
0x14002e680  mov     rdx, rbx
0x14002e683  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14002e688  mov     [rbp+57h+var_D0], rax
0x14002e68c  test    rax, rax
0x14002e68f  jz      loc_14002EB15
0x14002e695  mov     r15, [rbp+57h+var_C0]
0x14002e699  mov     r13, [r15]
0x14002e69c  add     r13, 4E0h
0x14002e6a3  mov     rcx, r13; Resource
0x14002e6a6  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14002e6ab  call    ??$GrepAcquireLockValidate@$0L@@@YAXXZ; GrepAcquireLockValidate<11>(void)
0x14002e6b0  mov     rcx, [rbp+57h+var_D0]; this
0x14002e6b4  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x14002e6b7  mov     r12d, 1
0x14002e6bd  or      dword ptr [rcx+24h], 10h
0x14002e6c1  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x14002e6c6  or      byte ptr [rax+0Fh], 4
0x14002e6ca  test    rsi, rsi
0x14002e6cd  jz      loc_14002ED27
0x14002e6d3  call    cs:__imp_PsGetCurrentProcessId
0x14002e6da  nop     dword ptr [rax+rax+00h]
0x14002e6df  call    cs:__imp_W32GetSessionState
0x14002e6e6  nop     dword ptr [rax+rax+00h]
0x14002e6eb  mov     r14, [rax+58h]
0x14002e6ef  mov     rdx, [r14]
0x14002e6f2  add     rdx, 5E8h
0x14002e6f9  mov     [rsp+130h+var_100], rdx
0x14002e6fe  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14002e703  mov     r9d, r12d
0x14002e706  lea     rcx, [rsp+130h+var_F8]
0x14002e70b  mov     r8, rsi
0x14002e70e  mov     rdx, r14
0x14002e711  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x14002e716  cmp     dword ptr [rsp+130h+var_F8+8], 0
0x14002e71b  jz      short loc_14002E78B
0x14002e71d  mov     rbx, qword ptr [rsp+130h+var_F8]
0x14002e722  cmp     byte ptr [rbx+0Eh], 4
0x14002e726  jnz     loc_14002EB4F
0x14002e72c  movzx   eax, byte ptr [rbx+0Ch]
0x14002e730  movzx   ecx, byte ptr [rbx+0Dh]
0x14002e734  shl     cx, 8
0x14002e738  or      cx, ax
0x14002e73b  mov     eax, esi
0x14002e73d  shr     eax, 10h
0x14002e740  cmp     cx, ax
0x14002e743  jnz     loc_14002EB4F
0x14002e749  mov     rax, qword ptr [rsp+130h+var_E8]
0x14002e74e  mov     edx, [rbx]
0x14002e750  mov     rcx, [rax+8]
0x14002e754  mov     rax, [rcx]
0x14002e757  mov     rax, [rax+60h]
0x14002e75b  call    _guard_dispatch_icall
0x14002e760  mov     rdi, rax
0x14002e763  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x14002e768  movzx   ecx, word ptr [rdi+0Ch]
0x14002e76c  test    cx, cx
0x14002e76f  jnz     loc_14002EE8F
0x14002e775  mov     ebx, [rbx+8]
0x14002e778  and     ebx, 0FFFFFFFEh
0x14002e77b  jnz     loc_14002EB59
0x14002e781  lea     rcx, [rsp+130h+var_F8]; this
0x14002e786  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14002e78b  lea     rcx, [rsp+130h+var_F8]; this
0x14002e790  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x14002e795  lea     rcx, [rsp+130h+var_100]
0x14002e79a  call    ?vUnlock@?$SEMOBJ@$0BE@@@QEAAXXZ; SEMOBJ<20>::vUnlock(void)
0x14002e79f  xor     r9d, r9d; int
0x14002e7a2  lea     rcx, [rbp+57h+var_88]; this
0x14002e7a6  xor     r8d, r8d; int
0x14002e7a9  mov     rdx, rsi; HRGN
0x14002e7ac  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14002e7b1  xor     r14d, r14d
0x14002e7b4  cmp     [rbp+57h+var_88], r14
0x14002e7b8  jz      loc_14002EB43
0x14002e7be  mov     rax, [rbp+57h+var_D0]
0x14002e7c2  mov     rbx, [rax]
0x14002e7c5  call    cs:__imp_W32GetSessionState
0x14002e7cc  nop     dword ptr [rax+rax+00h]
0x14002e7d1  mov     edx, ebx
0x14002e7d3  shr     edx, 8
0x14002e7d6  and     edx, 0FF0000h
0x14002e7dc  mov     rcx, [rax+58h]
0x14002e7e0  movzx   eax, bx
0x14002e7e3  or      edx, eax
0x14002e7e5  mov     rcx, [rcx+8]
0x14002e7e9  mov     r8, [rcx]
0x14002e7ec  mov     rax, [r8+10h]
0x14002e7f0  call    _guard_dispatch_icall
0x14002e7f5  test    rax, rax
0x14002e7f8  jz      short loc_14002E828
0x14002e7fa  cmp     [rax+0Eh], r12b
0x14002e7fe  jnz     short loc_14002E828
0x14002e800  movzx   edx, byte ptr [rax+0Dh]
0x14002e804  movzx   ecx, byte ptr [rax+0Ch]
0x14002e808  shl     dx, 8
0x14002e80c  or      dx, cx
0x14002e80f  shr     ebx, 10h
0x14002e812  cmp     dx, bx
0x14002e815  jnz     short loc_14002E828
0x14002e817  mov     eax, [rax+8]
0x14002e81a  and     eax, 0FFFFFFFEh
0x14002e81d  cmp     eax, 80000012h
0x14002e822  jz      loc_14002E955
0x14002e828  mov     rbx, [rbp+57h+var_D0]
0x14002e82c  test    dword ptr [rbx+24h], 100000h
0x14002e833  jz      loc_14002E955
0x14002e839  mov     rsi, [rbx+30h]
0x14002e83d  test    rsi, rsi
0x14002e840  jz      loc_14002E955
0x14002e846  mov     rdi, [rbp+57h+var_88]
0x14002e84a  test    rdi, rdi
0x14002e84d  jz      loc_14002E955
0x14002e853  xorps   xmm0, xmm0
0x14002e856  movups  [rsp+130h+var_F8], xmm0
0x14002e85b  movups  [rsp+130h+var_E8], xmm0
0x14002e860  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002e867  nop     dword ptr [rax+rax+00h]
0x14002e86c  test    rax, rax
0x14002e86f  jz      loc_14002EE1F
0x14002e875  mov     rcx, [rax]
0x14002e878  lea     rax, [rcx+8]
0x14002e87c  neg     rcx
0x14002e87f  sbb     rdx, rdx
0x14002e882  and     rdx, rax
0x14002e885  lea     rax, [rsp+130h+var_F8]
0x14002e88a  mov     qword ptr [rsp+130h+var_E8], rax
0x14002e88f  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14002e896  mov     qword ptr [rsp+130h+var_E8+8], rax
0x14002e89b  jz      loc_14002EE76
0x14002e8a1  lea     rax, [rdx+58h]
0x14002e8a5  mov     rcx, [rax]
0x14002e8a8  cmp     [rcx+8], rax
0x14002e8ac  jnz     loc_14002E655
0x14002e8b2  mov     qword ptr [rsp+130h+var_F8], rcx
0x14002e8b7  lea     rdx, [rsp+130h+var_F8]
0x14002e8bc  mov     qword ptr [rsp+130h+var_F8+8], rax
0x14002e8c1  mov     [rcx+8], rdx
0x14002e8c5  lea     rcx, [rsp+130h+var_F8]
0x14002e8ca  mov     [rax], rcx
0x14002e8cd  test    dword ptr [rbx+24h], 40000h
0x14002e8d4  mov     r11, r14
0x14002e8d7  mov     [rsp+130h+var_D8], r14
0x14002e8dc  jnz     loc_14002EE2F
0x14002e8e2  mov     rcx, [rbx+1F0h]
0x14002e8e9  mov     rax, r14
0x14002e8ec  test    rcx, rcx
0x14002e8ef  jz      loc_14002EB8C
0x14002e8f5  test    dword ptr [rsi+28h], 20000h
0x14002e8fc  jnz     loc_14002ED01
0x14002e902  mov     eax, [rbx+24h]
0x14002e905  bt      eax, 0Ch
0x14002e909  jb      loc_14002EEA7
0x14002e90f  mov     r9d, [rdi+34h]
0x14002e913  mov     r8d, [rdi+3Ch]
0x14002e917  cmp     r9d, r8d
0x14002e91a  jz      short loc_14002E92C
0x14002e91c  mov     r10d, [rdi+38h]
0x14002e920  mov     edx, [rdi+40h]
0x14002e923  cmp     r10d, edx
0x14002e926  jnz     loc_14002EC28
0x14002e92c  test    r11, r11
0x14002e92f  jz      short loc_14002E94B
0x14002e931  call    cs:__imp_W32GetSessionState
0x14002e938  nop     dword ptr [rax+rax+00h]
0x14002e93d  mov     rdx, [rsp+130h+var_D8]
0x14002e942  mov     rcx, [rax+58h]
0x14002e946  call    HmgDecrementShareReferenceCount
0x14002e94b  lea     rcx, [rsp+130h+var_F8]
0x14002e950  call    PopThreadGuardedObject
0x14002e955  mov     ebx, dword ptr [rbp+57h+var_90]
0x14002e958  mov     edi, r12d
0x14002e95b  mov     ecx, ebx
0x14002e95d  sub     ecx, r12d
0x14002e960  jnz     loc_14002EBB2
0x14002e966  mov     rsi, [rbp+57h+var_88]
0x14002e96a  lea     rcx, [rbp+57h+var_88]; this
0x14002e96e  call    ?bDeleteHandle@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteHandle(void)
0x14002e973  test    eax, eax
0x14002e975  jz      loc_14002EB94
0x14002e97b  mov     [rbp+57h+var_88], r14
0x14002e97f  mov     rbx, [rbp+57h+var_D0]
0x14002e983  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x14002e986  mov     rcx, rbx; this
0x14002e989  or      dword ptr [rbx+24h], 10h
0x14002e98d  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x14002e992  lea     rcx, [rbx+458h]; this
0x14002e999  or      byte ptr [rax+0Fh], 4
0x14002e99d  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x14002e9a2  mov     rax, [rbx+470h]
0x14002e9a9  lea     rcx, [rsp+130h+var_100]; this
0x14002e9ae  mov     [rsp+130h+var_100], rax
0x14002e9b3  mov     qword ptr [rbp+57h+var_50.left], rbx
0x14002e9b7  mov     byte ptr [rbp+57h+var_50.right], 1
0x14002e9bb  call    ?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14002e9c0  mov     rax, [r15+10A8h]
0x14002e9c7  lea     rcx, [rbp+57h+var_50]
0x14002e9cb  mov     [rbx+470h], rax
0x14002e9d2  call    ?reset@?$lambda_call@V_lambda_1_@?1??AcquireDcVisRgnExclusive@DC@@QEAA@XZ@@details@wil@@QEAAXXZ; wil::details::lambda_call<`DC::AcquireDcVisRgnExclusive(void)'::`2'::_lambda_1_>::reset(void)
0x14002e9d7  mov     rbx, [rbp+57h+var_D0]
0x14002e9db  lea     rcx, [rbx+458h]; this
0x14002e9e2  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x14002e9e7  mov     rax, [rbp+57h+var_D0]
0x14002e9eb  mov     [rax+470h], rsi
0x14002e9f2  call    cs:__imp_W32GetSessionState
0x14002e9f9  nop     dword ptr [rax+rax+00h]
0x14002e9fe  mov     rcx, [rax+58h]
0x14002ea02  mov     eax, 1
0x14002ea07  lock xadd [rcx+1098h], eax
0x14002ea0f  inc     eax
0x14002ea11  mov     [rsi+48h], eax
0x14002ea14  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14002ea19  test    rax, rax
0x14002ea1c  jz      short loc_14002EA2B
0x14002ea1e  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x14002ea28  and     [rax], rcx
0x14002ea2b  lea     rcx, [rbx+458h]; this
0x14002ea32  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x14002ea37  cmp     [rbp+57h+var_58], r14d
0x14002ea3b  jnz     short loc_14002EA46
0x14002ea3d  lea     rcx, [rbp+57h+var_88]; this
0x14002ea41  call    ?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14002ea46  mov     rax, [rbp+57h+var_88]
0x14002ea4a  test    rax, rax
0x14002ea4d  jz      short loc_14002EA54
0x14002ea4f  lock dec word ptr [rax+0Ch]
0x14002ea54  mov     rax, [rbp+57h+var_80]
0x14002ea58  lea     rcx, [rbp+57h+var_80]
0x14002ea5c  cmp     [rax+8], rcx
0x14002ea60  jnz     loc_14002E655
0x14002ea66  mov     rcx, [rbp+57h+var_78]
0x14002ea6a  lea     rdx, [rbp+57h+var_80]
0x14002ea6e  cmp     [rcx], rdx
0x14002ea71  jnz     loc_14002E655
0x14002ea77  mov     [rcx], rax
0x14002ea7a  mov     [rax+8], rcx
0x14002ea7e  test    r13, r13
0x14002ea81  jz      short loc_14002EA9D
0x14002ea83  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r14d
0x14002ea8a  jnz     loc_14002EEB6
0x14002ea90  call    ??$GrepReleaseLockValidate@$0L@@@YAXXZ; GrepReleaseLockValidate<11>(void)
0x14002ea95  mov     rcx, r13; HSEMAPHORE
0x14002ea98  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
  ... truncated ...
```
