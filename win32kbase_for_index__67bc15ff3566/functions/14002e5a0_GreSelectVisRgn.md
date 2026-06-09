# GreSelectVisRgn

- ea: `0x14002e5a0`
- end: `0x14002eee3`
- name: `GreSelectVisRgn`
- size: `2371`
- prototype: ``
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
__int64 __fastcall GreSelectVisRgn(__int64 a1, HRGN a2, int a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  struct Gre::Base::SESSION_GLOBALS *v13; // r15
  HSEMAPHORE v14; // r13
  DC *v15; // rcx
  unsigned int v16; // r12d
  struct _ENTRY *v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // r14
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned int v25; // ebx
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 SessionState; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  DC *v34; // rbx
  __int64 v35; // rsi
  volatile signed __int16 *v36; // rdi
  __int64 *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r11
  __int64 v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  int v45; // r9d
  LONG v46; // r8d
  int v47; // r10d
  LONG v48; // edx
  bool v49; // zf
  __int64 v50; // rax
  int v51; // ebx
  int v52; // edi
  volatile signed __int16 *v53; // rsi
  int v54; // r8d
  DC *v55; // rbx
  DC *v56; // rcx
  struct _ENTRY *v57; // rax
  DC *v58; // rbx
  __int64 v59; // rcx
  struct _GRETHREAD *v60; // rax
  __int64 v61; // rax
  _QWORD **v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rdx
  __int64 result; // rax
  __int64 v67; // rax
  __int64 v68; // rcx
  DC *v69; // rbx
  __int64 *v70; // rax
  int v71; // esi
  LONG v72; // ebx
  __int64 v73; // rax
  bool v74; // cc
  LONG v75; // r9d
  __int64 v76; // rax
  unsigned int sizeScan; // eax
  const struct BaseRustExports *v78; // rbx
  const struct REGION_CORE *v79; // rdi
  HSURF v80; // rdx
  volatile signed __int16 *v81; // [rsp+30h] [rbp-A9h] BYREF
  __int128 v82; // [rsp+38h] [rbp-A1h] BYREF
  __int128 v83; // [rsp+48h] [rbp-91h]
  __int64 v84; // [rsp+58h] [rbp-81h]
  DC *v85; // [rsp+60h] [rbp-79h] BYREF
  int v86; // [rsp+68h] [rbp-71h]
  struct Gre::Base::SESSION_GLOBALS *v87; // [rsp+70h] [rbp-69h]
  __int64 v88; // [rsp+78h] [rbp-61h]
  __int128 v89; // [rsp+80h] [rbp-59h] BYREF
  __int128 v90; // [rsp+90h] [rbp-49h]
  unsigned __int64 v91; // [rsp+A0h] [rbp-39h] BYREF
  volatile signed __int16 *v92; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v93; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD **v94; // [rsp+B8h] [rbp-21h]
  int v95; // [rsp+D8h] [rbp-1h]
  struct _RECTL v96; // [rsp+E0h] [rbp+7h] BYREF

  LODWORD(v91) = a3;
  v85 = 0;
  v86 = 0;
  v87 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(a1) + 88);
  v88 = 0;
  v85 = 0;
  v86 = 0;
  v89 = 0;
  v90 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v87, v5, v6, v7);
  if ( CurrentThreadWin32Thread )
    v10 = *CurrentThreadWin32Thread;
  else
    v10 = 0;
  v11 = (v10 + 8) & -(__int64)(v10 != 0);
  *(_QWORD *)&v90 = &v85;
  *((_QWORD *)&v90 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  if ( v11 )
  {
    v12 = *(_QWORD *)(((v10 + 8) & -(__int64)(v10 != 0)) + 0x58);
    if ( *(_QWORD *)(v12 + 8) != v11 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v89 = *(_QWORD *)(v11 + 88);
    *((_QWORD *)&v89 + 1) = v11 + 88;
    *(_QWORD *)(v12 + 8) = &v89;
    *(_QWORD *)(v11 + 88) = &v89;
  }
  else
  {
    *((_QWORD *)&v89 + 1) = &v89;
    *(_QWORD *)&v89 = &v89;
  }
  LOBYTE(v9) = 1;
  v85 = (DC *)HmgShareLock(v87, a1, v9, 1);
  if ( v85 )
  {
    v13 = v87;
    v14 = (HSEMAPHORE)(*(_QWORD *)v87 + 1248LL);
    GreAcquireSemaphoreInternal(v14);
    GrepAcquireLockValidate<11>();
    v15 = v85;
    v16 = 1;
    *((_DWORD *)v85 + 9) |= 0x10u;
    v17 = DC::PentryFromPobj(v15, v13);
    *((_BYTE *)v17 + 15) |= 4u;
    if ( !a2 )
    {
      DC::vReleaseVis(v85, v13);
      DC::bSetDefaultRegion(v85);
      goto LABEL_54;
    }
    PsGetCurrentProcessId();
    v19 = *(_QWORD **)(W32GetSessionState(v18) + 88);
    v81 = (volatile signed __int16 *)(*v19 + 1512LL);
    GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v20, v81);
    HANDLELOCK::HANDLELOCK(&v82, v19, a2, 1);
    if ( DWORD2(v82) )
    {
      v21 = v82;
      if ( *(_BYTE *)(v82 + 14) == 4
        && *(_WORD *)(v82 + 12) == WORD1(a2)
        && ((v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v83 + 8) + 96LL))(
                     *(_QWORD *)(v83 + 8),
                     *(unsigned int *)v82),
             GreGetCurrentThread(),
             !*(_WORD *)(v22 + 12))
         || *(struct _KTHREAD **)(v22 + 16) == KeGetCurrentThread()) )
      {
        v25 = *(_DWORD *)(v21 + 8) & 0xFFFFFFFE;
        if ( v25 && (unsigned int)HmgIncProcessHandleCount(0, v23, v24) )
        {
          HmgDecProcessHandleCount(v19, v25);
          HANDLELOCK::Pid((HANDLELOCK *)&v82, 0);
          *(_WORD *)(v22 + 14) &= ~0x10u;
        }
      }
      else
      {
        BYTE13(v82) = 1;
      }
      HANDLELOCK::vUnlock((HANDLELOCK *)&v82);
    }
    HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v82);
    SEMOBJ<20>::vUnlock(&v81);
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v92, a2, 0, 0);
    if ( !v92 )
      goto LABEL_65;
    v27 = *(_QWORD *)v85;
    SessionState = W32GetSessionState(v26);
    v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(SessionState + 88) + 8LL) + 16LL))(
            *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 8LL),
            (unsigned __int16)v27 | ((unsigned int)v27 >> 8) & 0xFF0000);
    if ( v29
      && *(_BYTE *)(v29 + 14) == 1
      && (v30 = *(unsigned __int8 *)(v29 + 13),
          v31 = *(unsigned __int8 *)(v29 + 12),
          LOWORD(v30) = v31 | ((_WORD)v30 << 8),
          (_WORD)v30 == WORD1(v27))
      && (*(_DWORD *)(v29 + 8) & 0xFFFFFFFE) == 0x80000012
      || (v34 = v85, (*((_DWORD *)v85 + 9) & 0x100000) == 0)
      || (v35 = *((_QWORD *)v85 + 6)) == 0
      || (v36 = v92) == 0 )
    {
LABEL_40:
      v51 = v91;
      v52 = 1;
      if ( (_DWORD)v91 == 1 )
      {
        v53 = v92;
        if ( (unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v92) )
        {
          v92 = 0;
          goto LABEL_43;
        }
        v16 = 0;
LABEL_71:
        if ( !v16 && v51 == 1 )
        {
LABEL_47:
          if ( !v95 )
            RGNOBJ::UpdateUserRgn((RGNOBJ *)&v92);
          if ( v92 )
            _InterlockedDecrement16(v92 + 6);
          v61 = v93;
          if ( *(__int64 **)(v93 + 8) != &v93 )
            goto LABEL_5;
          v62 = v94;
          if ( *v94 != &v93 )
            goto LABEL_5;
          *v94 = (_QWORD *)v93;
          *(_QWORD *)(v61 + 8) = v62;
LABEL_54:
          if ( v14 )
          {
            if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
              McTemplateK0pz_EtwWriteTransfer(
                (_DWORD)v62,
                (unsigned int)LockRelease,
                v54,
                (_DWORD)v14,
                (__int64)L"VisRgnPublish");
            GrepReleaseLockValidate<11>();
            GreReleaseSemaphoreSharedInternal(v14);
          }
          if ( v85 )
          {
            v63 = W32GetSessionState(v62);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v63 + 88), v85);
            v85 = 0;
          }
          v64 = v89;
          if ( *(__int128 **)(v89 + 8) == &v89 )
          {
            v65 = *((_QWORD *)&v89 + 1);
            if ( **((__int128 ***)&v89 + 1) == &v89 )
            {
              **((_QWORD **)&v89 + 1) = v89;
              result = v16;
              *(_QWORD *)(v64 + 8) = v65;
              return result;
            }
          }
LABEL_5:
          __fastfail(3u);
        }
        if ( !v52 )
        {
LABEL_44:
          v58 = v85;
          GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v85 + 1112));
          *((_QWORD *)v85 + 142) = v53;
          *((_DWORD *)v53 + 18) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(v59)
                                                                                              + 88)
                                                                                  + 4248LL));
          v60 = GreGetCurrentThreadCrossSessionCheck();
          if ( v60 )
            *(_QWORD *)v60 &= ~0x4000000000uLL;
          GrePushLock::ReleaseLock((DC *)((char *)v58 + 1112));
          goto LABEL_47;
        }
LABEL_43:
        v55 = v85;
        v56 = v85;
        *((_DWORD *)v85 + 9) |= 0x10u;
        v57 = DC::PentryFromPobj(v56, v13);
        *((_BYTE *)v57 + 15) |= 4u;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v55 + 1112));
        v81 = (volatile signed __int16 *)*((_QWORD *)v55 + 142);
        *(_QWORD *)&v96.left = v55;
        LOBYTE(v96.right) = 1;
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v81);
        *((_QWORD *)v55 + 142) = *((_QWORD *)v13 + 533);
        _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v96);
        goto LABEL_44;
      }
      if ( (_DWORD)v91 != 2 )
      {
        if ( (_DWORD)v91 != 4 )
        {
          v53 = 0;
          goto LABEL_43;
        }
        v69 = v85;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v85 + 1112));
        *(_QWORD *)&v96.left = v69;
        LOBYTE(v96.right) = 1;
        v53 = (volatile signed __int16 *)*((_QWORD *)v85 + 142);
        if ( v53 )
        {
          if ( v53 != *((volatile signed __int16 **)v13 + 533) )
          {
            v81 = (volatile signed __int16 *)*((_QWORD *)v85 + 142);
            RGNOBJAPI::bSwap((__int64 **)&v92, (__int64 **)&v81);
            v53 = v81;
            v52 = 0;
LABEL_80:
            _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v96);
            v51 = v91;
            goto LABEL_71;
          }
        }
        else
        {
          v53 = (volatile signed __int16 *)*((_QWORD *)v13 + 533);
        }
        v16 = 0;
        goto LABEL_80;
      }
      sizeScan = REGION_CORE::get_sizeScan((REGION_CORE *)(v92 + 12));
      v81 = 0;
      RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v81, sizeScan);
      v53 = v81;
      if ( v81 )
      {
        if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
        {
          v78 = *(const struct BaseRustExports **)WPP_MAIN_CB.Dpc.ProcessorHistory;
          v79 = (const struct REGION_CORE *)((unsigned __int64)(v81 + 12) & -(__int64)(v81 != 0));
          (*(void (__fastcall **)(const struct REGION_CORE *, unsigned __int64, __int64))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory
                                                                                        + 48LL))(
            v79,
            (unsigned __int64)(v92 + 12) & -(__int64)(v92 != 0),
            -(__int64)v92);
          RgnCaptureLiveMemoryDumpOnZeroSizedScan(v78, v79);
        }
        else
        {
          v91 = (unsigned __int64)(v81 + 12) & -(__int64)(v81 != 0);
          v81 = (volatile signed __int16 *)((unsigned __int64)(v92 + 12) & -(__int64)(v92 != 0));
          RGNCOREOBJ::vCopy((RGNCOREOBJ *)&v91, (const struct RGNCOREOBJ *)&v81);
        }
        goto LABEL_43;
      }
LABEL_65:
      v53 = (volatile signed __int16 *)*((_QWORD *)v13 + 533);
      goto LABEL_43;
    }
    v82 = 0;
    v83 = 0;
    v37 = (__int64 *)PsGetCurrentThreadWin32Thread(v31, v30, v32, v33);
    if ( v37 )
      v38 = *v37;
    else
      v38 = 0;
    v39 = (v38 + 8) & -(__int64)(v38 != 0);
    *(_QWORD *)&v83 = &v82;
    *((_QWORD *)&v83 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    if ( v39 )
    {
      v40 = *(_QWORD *)(((v38 + 8) & -(__int64)(v38 != 0)) + 0x58);
      if ( *(_QWORD *)(v40 + 8) != v39 + 88 )
        goto LABEL_5;
      *(_QWORD *)&v82 = *(_QWORD *)(v39 + 88);
      *((_QWORD *)&v82 + 1) = v39 + 88;
      *(_QWORD *)(v40 + 8) = &v82;
      *(_QWORD *)(v39 + 88) = &v82;
    }
    else
    {
      *((_QWORD *)&v82 + 1) = &v82;
      *(_QWORD *)&v82 = &v82;
    }
    v49 = (*((_DWORD *)v34 + 9) & 0x40000) == 0;
    v41 = 0;
    v84 = 0;
    if ( v49 )
    {
      v42 = *((_QWORD *)v34 + 62);
    }
    else
    {
      v80 = (HSURF)*((_QWORD *)v34 + 268);
      if ( v80 )
      {
        SURFREF::vLock((SURFREF *)&v82, v80);
        v41 = v84;
        v42 = v84;
        v43 = v84;
LABEL_31:
        if ( !v42 )
        {
          v49 = v43 == 0;
          goto LABEL_37;
        }
        if ( (*(_DWORD *)(v35 + 40) & 0x20000) != 0 && *(int *)(v42 + 144) < 0
          || (v44 = *((_DWORD *)v34 + 9), (v44 & 0x1000) != 0) && (v44 & 0x4000) == 0
          || (v45 = *((_DWORD *)v36 + 13), v46 = *((_DWORD *)v36 + 15), v45 == v46)
          || (v47 = *((_DWORD *)v36 + 14), v48 = *((_DWORD *)v36 + 16), v47 == v48)
          || v45 == 0x7FFFFFFF && v48 == 0x80000000 && v47 == 0x7FFFFFFF && v46 == 0x80000000 )
        {
LABEL_36:
          v49 = v41 == 0;
LABEL_37:
          if ( !v49 )
          {
            v50 = W32GetSessionState(v42);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v50 + 88), v84);
          }
          PopThreadGuardedObject(&v82);
          goto LABEL_40;
        }
        v70 = (__int64 *)(v42 + 700);
        v71 = *((_DWORD *)v36 + 13);
        v72 = *((_DWORD *)v36 + 14);
        if ( (*(_DWORD *)(v42 + 148) & 0x800) == 0 )
          v70 = (__int64 *)(v42 + 56);
        v73 = *v70;
        if ( v45 >= v46 )
        {
          if ( v45 > v46 )
          {
            v71 = *((_DWORD *)v36 + 15);
            v46 = *((_DWORD *)v36 + 13);
          }
          v74 = v47 <= v48;
        }
        else
        {
          v74 = v47 <= v48;
          if ( v47 < v48 )
          {
            if ( v45 >= 0 && (int)v73 >= v46 && v47 >= 0 && SHIDWORD(v73) >= v48 )
              goto LABEL_36;
LABEL_96:
            v75 = 0;
            if ( v71 >= 0 )
              v75 = v71;
            if ( v72 < 0 )
              v72 = 0;
            if ( (int)v73 < v46 )
              v46 = v73;
            if ( SHIDWORD(v73) < v48 )
              v48 = HIDWORD(v73);
            if ( v46 < v75 )
            {
              v75 = v46;
            }
            else if ( v48 < v72 )
            {
              v72 = v48;
            }
            v96.left = v75;
            v96.top = v72;
            v96.right = v46;
            v96.bottom = v48;
            if ( v41 )
            {
              v76 = W32GetSessionState(v42);
              HmgDecrementShareReferenceCount(*(_QWORD *)(v76 + 88), v84);
            }
            PopThreadGuardedObject(&v82);
            RGNOBJ::vSet((RGNOBJ *)&v92, &v96);
            goto LABEL_40;
          }
        }
        if ( !v74 )
        {
          v72 = *((_DWORD *)v36 + 16);
          v48 = *((_DWORD *)v36 + 14);
        }
        goto LABEL_96;
      }
      v42 = *(_QWORD *)(v35 + 2544);
    }
    v43 = 0;
    goto LABEL_31;
  }
  v67 = v89;
  if ( *(__int128 **)(v89 + 8) != &v89 )
    goto LABEL_5;
  v68 = *((_QWORD *)&v89 + 1);
  if ( **((__int128 ***)&v89 + 1) != &v89 )
    goto LABEL_5;
  **((_QWORD **)&v89 + 1) = v89;
  *(_QWORD *)(v67 + 8) = v68;
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
