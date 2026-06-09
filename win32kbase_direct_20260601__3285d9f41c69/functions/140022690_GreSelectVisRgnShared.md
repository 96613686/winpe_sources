# GreSelectVisRgnShared

- ea: `0x140022690`
- end: `0x140022fe9`
- name: `GreSelectVisRgnShared`
- size: `2393`
- prototype: `__int64 __fastcall(__int64, HRGN, int)`
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140010070`
- `0x140018770`
- `0x1400195ac`
- `0x140019d88`
- `0x14001d160`
- `0x140020444`
- `0x140020ab0`
- `0x1400215d0`
- `0x140022690`
- `0x140022ff0`
- `0x140023050`
- `0x140024930`
- `0x140024cc0`
- `0x140024f80`
- `0x1400252f0`
- `0x140025360`
- `0x140025990`
- `0x140025a30`
- `0x140025b50`
- `0x140026270`
- `0x140026f60`
- `0x140027200`
- `0x1400272d4`
- `0x140027f3c`
- `0x140028360`
- `0x140028590`
- `0x140029748`
- `0x140029778`
- `0x140029a54`
- `0x14002a730`
- `0x140040ccc`
- `0x1400487d0`
- `0x140048d40`
- `0x140153b0c`
- `0x140190760`
- `0x1401b4018`
- `0x140238160`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140022813`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140022813`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400226fe`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400229a2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400226fe`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400229a2`
- `WIN32K!W32GetSessionState` at `0x1400226d3`
- `WIN32K!W32GetSessionState` at `0x14002281f`
- `WIN32K!W32GetSessionState` at `0x140022907`
- `WIN32K!W32GetSessionState` at `0x140022a76`
- `WIN32K!W32GetSessionState` at `0x140022b30`
- `WIN32K!W32GetSessionState` at `0x140022be5`
- `WIN32K!W32GetSessionState` at `0x140022da1`
- `WIN32K!W32GetSessionState` at `0x1400226d3`
- `WIN32K!W32GetSessionState` at `0x14002281f`
- `WIN32K!W32GetSessionState` at `0x140022907`
- `WIN32K!W32GetSessionState` at `0x140022a76`
- `WIN32K!W32GetSessionState` at `0x140022b30`
- `WIN32K!W32GetSessionState` at `0x140022be5`
- `WIN32K!W32GetSessionState` at `0x140022da1`

## pseudocode

```c
__int64 __fastcall GreSelectVisRgnShared(__int64 a1, HRGN a2, int a3)
{
  int v3; // r13d
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 result; // rax
  struct Gre::Base::SESSION_GLOBALS *v14; // r15
  HSEMAPHORE v15; // r12
  DC *v16; // rcx
  unsigned int v17; // ebx
  struct _ENTRY *v18; // rax
  _QWORD *v19; // r14
  __int64 v20; // rbx
  __int64 v21; // r13
  unsigned int v22; // ebx
  __int64 v23; // rbx
  __int64 SessionState; // rax
  __int64 v25; // rax
  DC *v26; // rbx
  __int64 v27; // r14
  _DWORD *v28; // rdi
  _QWORD *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // r9
  __int64 v34; // r11
  __int64 v35; // rax
  int v36; // eax
  int v37; // r8d
  LONG v38; // edx
  int v39; // r10d
  LONG v40; // ecx
  bool v41; // zf
  __int64 v42; // rax
  __int64 v43; // r14
  int v44; // r8d
  DC *v45; // rbx
  DC *v46; // rcx
  struct _ENTRY *v47; // rax
  DC *v48; // rbx
  struct _GRETHREAD *v49; // rax
  __int64 v50; // rax
  _QWORD **v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rdx
  DC *v55; // rbx
  int v56; // ebx
  LONG v57; // edi
  LONG v58; // ebx
  __int64 *v59; // r11
  __int64 v60; // r11
  bool v61; // cc
  __int64 v62; // rax
  unsigned int sizeScan; // eax
  const struct REGION_CORE *v64; // rdi
  __int64 v65; // rbx
  __int64 v66; // rdx
  __int64 v67; // rdx
  HSURF v68; // rdx
  __int64 v69; // [rsp+30h] [rbp-A9h] BYREF
  int v70; // [rsp+38h] [rbp-A1h]
  __int128 v71; // [rsp+40h] [rbp-99h] BYREF
  __int128 v72; // [rsp+50h] [rbp-89h]
  __int64 v73; // [rsp+60h] [rbp-79h]
  __int64 v74; // [rsp+68h] [rbp-71h] BYREF
  DC *v75; // [rsp+70h] [rbp-69h] BYREF
  int v76; // [rsp+78h] [rbp-61h]
  struct Gre::Base::SESSION_GLOBALS *v77; // [rsp+80h] [rbp-59h]
  __int64 v78; // [rsp+88h] [rbp-51h]
  __int128 v79; // [rsp+90h] [rbp-49h] BYREF
  __int128 v80; // [rsp+A0h] [rbp-39h]
  __int64 v81; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-21h] BYREF
  _QWORD **v83; // [rsp+C0h] [rbp-19h]
  int v84; // [rsp+E0h] [rbp+7h]
  struct _RECTL v85; // [rsp+E8h] [rbp+Fh] BYREF

  LODWORD(v69) = a3;
  v75 = 0;
  v3 = a3;
  v76 = 0;
  v77 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState() + 88);
  v78 = 0;
  v75 = 0;
  v76 = 0;
  v79 = 0;
  v80 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( !CurrentThreadWin32Thread || (v7 = *CurrentThreadWin32Thread) == 0 )
  {
    *(_QWORD *)&v80 = &v75;
    *((_QWORD *)&v80 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_120;
  }
  *(_QWORD *)&v80 = &v75;
  *((_QWORD *)&v80 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  v8 = v7 + 8;
  if ( !v8 )
  {
LABEL_120:
    *((_QWORD *)&v79 + 1) = &v79;
    *(_QWORD *)&v79 = &v79;
    goto LABEL_7;
  }
  v9 = *(_QWORD *)(v8 + 88);
  v10 = (_QWORD *)(v8 + 88);
  if ( *(_QWORD **)(v9 + 8) != v10 )
    goto LABEL_5;
  *(_QWORD *)&v79 = v9;
  *((_QWORD *)&v79 + 1) = v10;
  *(_QWORD *)(v9 + 8) = &v79;
  *v10 = &v79;
LABEL_7:
  v75 = (DC *)HmgShareLock(v77, a1, 1);
  if ( !v75 )
  {
    v11 = v79;
    if ( *(__int128 **)(v79 + 8) == &v79 )
    {
      v12 = *((_QWORD *)&v79 + 1);
      if ( **((__int128 ***)&v79 + 1) == &v79 )
      {
        **((_QWORD **)&v79 + 1) = v79;
        *(_QWORD *)(v11 + 8) = v12;
        return 0;
      }
    }
LABEL_5:
    __fastfail(3u);
  }
  v14 = v77;
  v15 = (HSEMAPHORE)(*(_QWORD *)v77 + 1248LL);
  GreAcquireSemaphoreInternal(v15);
  GrepAcquireLockValidate<11>();
  v16 = v75;
  v17 = 1;
  v70 = 1;
  *((_DWORD *)v75 + 9) |= 0x10u;
  v18 = DC::PentryFromPobj(v16, v14);
  *((_BYTE *)v18 + 15) |= 4u;
  if ( !a2 )
  {
    DC::vReleaseVis(v75, v14);
    DC::bSetDefaultRegion(v75);
    goto LABEL_58;
  }
  PsGetCurrentProcessId();
  v19 = *(_QWORD **)(W32GetSessionState() + 88);
  v74 = *v19 + 1512LL;
  GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>();
  HANDLELOCK::HANDLELOCK(&v71, v19, a2, 1);
  if ( DWORD2(v71) )
  {
    v20 = v71;
    if ( *(_BYTE *)(v71 + 14) == 4 && *(_WORD *)(v71 + 12) == WORD1(a2) )
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v72 + 8) + 96LL))(
              *(_QWORD *)(v72 + 8),
              *(unsigned int *)v71);
      GreGetCurrentThread();
      if ( !*(_WORD *)(v21 + 12) || *(struct _KTHREAD **)(v21 + 16) == KeGetCurrentThread() )
      {
        v22 = *(_DWORD *)(v20 + 8) & 0xFFFFFFFE;
        if ( v22 && (unsigned int)HmgIncProcessHandleCount(0) )
        {
          HmgDecProcessHandleCount(v19, v22);
          HANDLELOCK::Pid((HANDLELOCK *)&v71, 0);
          *(_WORD *)(v21 + 14) &= ~0x10u;
        }
        v3 = v69;
        goto LABEL_18;
      }
      v3 = v69;
    }
    BYTE13(v71) = 1;
LABEL_18:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v71);
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v71);
  SEMOBJ<20>::vUnlock(&v74);
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v81, a2, 0, 0);
  if ( !v81 )
    goto LABEL_66;
  v23 = *(_QWORD *)v75;
  SessionState = W32GetSessionState();
  v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(SessionState + 88) + 8LL) + 16LL))(
          *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 8LL),
          (unsigned __int16)v23 | ((unsigned int)v23 >> 8) & 0xFF0000);
  if ( v25
    && *(_BYTE *)(v25 + 14) == 1
    && *(_WORD *)(v25 + 12) == WORD1(v23)
    && (*(_DWORD *)(v25 + 8) & 0xFFFFFFFE) == 0x80000012 )
  {
    goto LABEL_44;
  }
  v26 = v75;
  if ( (*((_DWORD *)v75 + 9) & 0x100000) == 0 )
    goto LABEL_44;
  v27 = *((_QWORD *)v75 + 6);
  if ( !v27 )
    goto LABEL_44;
  v28 = (_DWORD *)v81;
  if ( !v81 )
    goto LABEL_44;
  v71 = 0;
  v72 = 0;
  v29 = (_QWORD *)PsGetCurrentThreadWin32Thread();
  if ( !v29 || !*v29 )
  {
    *(_QWORD *)&v72 = &v71;
    *((_QWORD *)&v72 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_129;
  }
  v30 = *v29 + 8LL;
  *(_QWORD *)&v72 = &v71;
  *((_QWORD *)&v72 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
  if ( !v30 )
  {
LABEL_129:
    *((_QWORD *)&v71 + 1) = &v71;
    *(_QWORD *)&v71 = &v71;
    goto LABEL_32;
  }
  v31 = *(_QWORD *)(v30 + 88);
  v32 = (_QWORD *)(v30 + 88);
  if ( *(_QWORD **)(v31 + 8) != v32 )
    goto LABEL_5;
  *(_QWORD *)&v71 = v31;
  *((_QWORD *)&v71 + 1) = v32;
  *(_QWORD *)(v31 + 8) = &v71;
  *v32 = &v71;
LABEL_32:
  v33 = 0;
  v41 = (*((_DWORD *)v26 + 9) & 0x40000) == 0;
  v73 = 0;
  if ( v41 )
  {
    v34 = *((_QWORD *)v26 + 62);
    v35 = 0;
  }
  else
  {
    v68 = (HSURF)*((_QWORD *)v26 + 268);
    if ( v68 )
    {
      SURFREF::vLock((SURFREF *)&v71, v68);
      v33 = v73;
      v34 = v73;
      v35 = v73;
    }
    else
    {
      v34 = *(_QWORD *)(v27 + 2544);
      v35 = 0;
    }
  }
  if ( !v34 )
  {
    v41 = v35 == 0;
LABEL_41:
    if ( v41 )
    {
LABEL_43:
      PopThreadGuardedObject(&v71);
      goto LABEL_44;
    }
LABEL_42:
    v42 = W32GetSessionState();
    HmgDecrementShareReferenceCount(*(_QWORD *)(v42 + 88), v73);
    goto LABEL_43;
  }
  if ( (*(_DWORD *)(v27 + 40) & 0x20000) != 0 && *(int *)(v34 + 160) < 0
    || (v36 = *((_DWORD *)v26 + 9), (v36 & 0x1000) != 0) && (v36 & 0x4000) == 0
    || (v37 = v28[13], v38 = v28[15], v37 == v38)
    || (v39 = v28[14], v40 = v28[16], v39 == v40)
    || v37 == 0x7FFFFFFF && v40 == 0x80000000 && v39 == 0x7FFFFFFF && v38 == v40 )
  {
    v41 = v33 == 0;
    goto LABEL_41;
  }
  v57 = v28[13];
  v58 = v39;
  if ( (*(_DWORD *)(v34 + 164) & 0x800) != 0 )
    v59 = (__int64 *)(v34 + 716);
  else
    v59 = (__int64 *)(v34 + 56);
  v60 = *v59;
  if ( v37 >= v38 )
  {
    if ( v37 > v38 )
    {
      v57 = v38;
      v38 = v37;
    }
    v61 = v39 <= v40;
    goto LABEL_91;
  }
  v61 = v39 <= v40;
  if ( v39 >= v40 )
  {
LABEL_91:
    if ( !v61 )
    {
      v58 = v40;
      v40 = v39;
    }
    goto LABEL_93;
  }
  if ( v37 < 0 )
  {
LABEL_93:
    if ( v57 < 0 )
      v57 = 0;
LABEL_95:
    if ( v58 < 0 )
      v58 = 0;
    if ( (int)v60 < v38 )
      v38 = v60;
    if ( SHIDWORD(v60) >= v40 )
      goto LABEL_101;
    goto LABEL_100;
  }
  if ( (int)v60 < v38 || v39 < 0 )
    goto LABEL_95;
  if ( SHIDWORD(v60) >= v40 )
  {
    if ( !v33 )
      goto LABEL_43;
    goto LABEL_42;
  }
LABEL_100:
  v40 = HIDWORD(v60);
LABEL_101:
  if ( v38 < v57 )
  {
    v57 = v38;
  }
  else if ( v40 < v58 )
  {
    v58 = v40;
  }
  v85.left = v57;
  v85.top = v58;
  v85.right = v38;
  v85.bottom = v40;
  if ( v33 )
  {
    v62 = W32GetSessionState();
    HmgDecrementShareReferenceCount(*(_QWORD *)(v62 + 88), v73);
  }
  PopThreadGuardedObject(&v71);
  RGNOBJ::vSet((RGNOBJ *)&v81, &v85);
LABEL_44:
  if ( v3 != 1 )
  {
    if ( v3 != 2 )
    {
      if ( v3 != 4 )
      {
        v43 = 0;
        goto LABEL_47;
      }
      v55 = v75;
      GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v75 + 1112));
      *(_QWORD *)&v85.left = v55;
      LOBYTE(v85.right) = 1;
      v43 = *((_QWORD *)v75 + 142);
      if ( v43 )
      {
        if ( v43 != *((_QWORD *)v14 + 533) )
        {
          v69 = *((_QWORD *)v75 + 142);
          RGNOBJAPI::bSwap((RGNOBJAPI *)&v81, (struct RGNOBJ *)&v69);
          v43 = v69;
          v56 = 0;
          goto LABEL_75;
        }
      }
      else
      {
        v43 = *((_QWORD *)v14 + 533);
      }
      v56 = 1;
      v70 = 0;
LABEL_75:
      _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v85);
      if ( !v56 )
        goto LABEL_48;
      goto LABEL_47;
    }
    sizeScan = REGION_CORE::get_sizeScan((REGION_CORE *)(v81 + 24));
    v69 = 0;
    RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v69, sizeScan);
    v43 = v69;
    if ( v69 )
    {
      if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
      {
        v64 = (const struct REGION_CORE *)(v69 + 24);
        v65 = *(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory;
        v66 = v81 + 24;
        if ( !v81 )
          v66 = 0;
        (*(void (__fastcall **)(const struct REGION_CORE *, __int64, __int64))(v65 + 48))(v64, v66, v81);
        RgnCaptureLiveMemoryDumpOnZeroSizedScan((const struct BaseRustExports *)v65, v64);
      }
      else
      {
        v69 += 24;
        v67 = v81 + 24;
        if ( !v81 )
          v67 = 0;
        v74 = v67;
        RGNCOREOBJ::vCopy((RGNCOREOBJ *)&v69, (const struct RGNCOREOBJ *)&v74);
      }
      goto LABEL_47;
    }
LABEL_66:
    v43 = *((_QWORD *)v14 + 533);
    goto LABEL_47;
  }
  v43 = v81;
  if ( (unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v81) )
  {
    v81 = 0;
LABEL_47:
    v45 = v75;
    v46 = v75;
    *((_DWORD *)v75 + 9) |= 0x10u;
    v47 = DC::PentryFromPobj(v46, v14);
    *((_BYTE *)v47 + 15) |= 4u;
    GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v45 + 1112));
    v74 = *((_QWORD *)v45 + 142);
    *(_QWORD *)&v85.left = v45;
    LOBYTE(v85.right) = 1;
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v74);
    *((_QWORD *)v45 + 142) = *((_QWORD *)v14 + 533);
    _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v85);
LABEL_48:
    v48 = v75;
    GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v75 + 1112));
    *((_QWORD *)v75 + 142) = v43;
    *(_DWORD *)(v43 + 72) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState() + 88)
                                                                            + 4248LL));
    v49 = GreGetCurrentThreadCrossSessionCheck();
    if ( v49 )
      *(_QWORD *)v49 &= ~0x4000000000uLL;
    GrePushLock::ReleaseLock((DC *)((char *)v48 + 1112));
    v17 = v70;
    goto LABEL_51;
  }
  v17 = 0;
LABEL_51:
  if ( !v84 )
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v81);
  if ( v81 )
    _InterlockedDecrement16((volatile signed __int16 *)(v81 + 12));
  v50 = v82;
  if ( *(__int64 **)(v82 + 8) != &v82 )
    goto LABEL_5;
  v51 = v83;
  if ( *v83 != &v82 )
    goto LABEL_5;
  *v83 = (_QWORD *)v82;
  *(_QWORD *)(v50 + 8) = v51;
LABEL_58:
  if ( v15 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        (_DWORD)v51,
        (unsigned int)LockRelease,
        v44,
        (_DWORD)v15,
        (__int64)L"VisRgnPublish");
    GrepReleaseLockValidate<11>();
    GreReleaseSemaphoreSharedInternal(v15);
  }
  if ( v75 )
  {
    v52 = W32GetSessionState();
    HmgDecrementShareReferenceCount(*(_QWORD *)(v52 + 88), v75);
    v75 = 0;
  }
  v53 = v79;
  if ( *(__int128 **)(v79 + 8) != &v79 )
    goto LABEL_5;
  v54 = *((_QWORD *)&v79 + 1);
  if ( **((__int128 ***)&v79 + 1) != &v79 )
    goto LABEL_5;
  **((_QWORD **)&v79 + 1) = v79;
  result = v17;
  *(_QWORD *)(v53 + 8) = v54;
  return result;
}

```

## disassembly

```asm
0x140022690  mov     [rsp-8+arg_10], rbx
0x140022695  push    rbp
0x140022696  push    rsi
0x140022697  push    rdi
0x140022698  push    r12
0x14002269a  push    r13
0x14002269c  push    r14
0x14002269e  push    r15
0x1400226a0  lea     rbp, [rsp-27h]
0x1400226a5  sub     rsp, 100h
0x1400226ac  mov     rax, cs:__security_cookie
0x1400226b3  xor     rax, rsp
0x1400226b6  mov     [rbp+57h+var_38], rax
0x1400226ba  xor     r14d, r14d
0x1400226bd  mov     dword ptr [rsp+130h+var_100], r8d
0x1400226c2  mov     [rbp+57h+var_C0], r14
0x1400226c6  mov     r13d, r8d
0x1400226c9  mov     [rbp+57h+var_B8], r14d
0x1400226cd  mov     rdi, rdx
0x1400226d0  mov     rbx, rcx
0x1400226d3  call    cs:__imp_W32GetSessionState
0x1400226da  nop     dword ptr [rax+rax+00h]
0x1400226df  xorps   xmm0, xmm0
0x1400226e2  mov     rcx, [rax+58h]
0x1400226e6  mov     [rbp+57h+var_B0], rcx
0x1400226ea  mov     [rbp+57h+var_A8], r14
0x1400226ee  mov     [rbp+57h+var_C0], r14
0x1400226f2  mov     [rbp+57h+var_B8], r14d
0x1400226f6  movups  [rbp+57h+var_A0], xmm0
0x1400226fa  movups  [rbp+57h+var_90], xmm0
0x1400226fe  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140022705  nop     dword ptr [rax+rax+00h]
0x14002270a  test    rax, rax
0x14002270d  jz      loc_140022E9D
0x140022713  mov     rax, [rax]
0x140022716  test    rax, rax
0x140022719  jz      loc_140022E9D
0x14002271f  lea     rcx, [rbp+57h+var_C0]
0x140022723  mov     qword ptr [rbp+57h+var_90], rcx
0x140022727  lea     rcx, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x14002272e  mov     qword ptr [rbp+57h+var_90+8], rcx
0x140022732  add     rax, 8
0x140022736  jz      loc_140022EB0
0x14002273c  mov     rcx, [rax+58h]
0x140022740  add     rax, 58h ; 'X'
0x140022744  cmp     [rcx+8], rax
0x140022748  jz      short loc_140022751
0x14002274a  mov     ecx, 3
0x14002274f  int     29h; Win8: RtlFailFast(ecx)
0x140022751  mov     qword ptr [rbp+57h+var_A0], rcx
0x140022755  lea     rdx, [rbp+57h+var_A0]
0x140022759  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14002275d  mov     [rcx+8], rdx
0x140022761  lea     rcx, [rbp+57h+var_A0]
0x140022765  mov     [rax], rcx
0x140022768  mov     rcx, [rbp+57h+var_B0]
0x14002276c  mov     esi, 1
0x140022771  mov     r9d, esi
0x140022774  movzx   r8d, sil
0x140022778  mov     rdx, rbx
0x14002277b  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140022780  mov     [rbp+57h+var_C0], rax
0x140022784  test    rax, rax
0x140022787  jnz     short loc_1400227D5
0x140022789  mov     rax, qword ptr [rbp+57h+var_A0]
0x14002278d  lea     rcx, [rbp+57h+var_A0]
0x140022791  cmp     [rax+8], rcx
0x140022795  jnz     short loc_14002274A
0x140022797  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x14002279b  lea     rdx, [rbp+57h+var_A0]
0x14002279f  cmp     [rcx], rdx
0x1400227a2  jnz     short loc_14002274A
0x1400227a4  mov     [rcx], rax
0x1400227a7  mov     [rax+8], rcx
0x1400227ab  xor     eax, eax
0x1400227ad  mov     rcx, [rbp+57h+var_38]
0x1400227b1  xor     rcx, rsp; StackCookie
0x1400227b4  call    __security_check_cookie
0x1400227b9  mov     rbx, [rsp+130h+arg_10]
0x1400227c1  add     rsp, 100h
0x1400227c8  pop     r15
0x1400227ca  pop     r14
0x1400227cc  pop     r13
0x1400227ce  pop     r12
0x1400227d0  pop     rdi
0x1400227d1  pop     rsi
0x1400227d2  pop     rbp
0x1400227d3  retn
0x1400227d5  mov     r15, [rbp+57h+var_B0]
0x1400227d9  mov     r12, [r15]
0x1400227dc  add     r12, 4E0h
0x1400227e3  mov     rcx, r12; Resource
0x1400227e6  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x1400227eb  call    ??$GrepAcquireLockValidate@$0L@@@YAXXZ; GrepAcquireLockValidate<11>(void)
0x1400227f0  mov     rcx, [rbp+57h+var_C0]; this
0x1400227f4  mov     ebx, esi
0x1400227f6  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x1400227f9  mov     [rsp+130h+var_F8], ebx
0x1400227fd  or      dword ptr [rcx+24h], 10h
0x140022801  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140022806  or      byte ptr [rax+0Fh], 4
0x14002280a  test    rdi, rdi
0x14002280d  jz      loc_140022E0C
0x140022813  call    cs:__imp_PsGetCurrentProcessId
0x14002281a  nop     dword ptr [rax+rax+00h]
0x14002281f  call    cs:__imp_W32GetSessionState
0x140022826  nop     dword ptr [rax+rax+00h]
0x14002282b  mov     r14, [rax+58h]
0x14002282f  mov     rdx, [r14]
0x140022832  add     rdx, 5E8h
0x140022839  mov     [rbp+57h+var_C8], rdx
0x14002283d  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140022842  mov     r9d, esi
0x140022845  lea     rcx, [rsp+130h+var_F0]
0x14002284a  mov     r8, rdi
0x14002284d  mov     rdx, r14
0x140022850  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x140022855  cmp     dword ptr [rsp+130h+var_F0+8], 0
0x14002285a  jz      short loc_1400228D0
0x14002285c  mov     rbx, qword ptr [rsp+130h+var_F0]
0x140022861  cmp     byte ptr [rbx+0Eh], 4
0x140022865  jnz     loc_140022FA3
0x14002286b  movzx   eax, byte ptr [rbx+0Ch]
0x14002286f  movzx   ecx, byte ptr [rbx+0Dh]
0x140022873  shl     cx, 8
0x140022877  or      cx, ax
0x14002287a  mov     eax, edi
0x14002287c  shr     eax, 10h
0x14002287f  cmp     cx, ax
0x140022882  jnz     loc_140022FA3
0x140022888  mov     rax, qword ptr [rsp+130h+var_E0]
0x14002288d  mov     edx, [rbx]
0x14002288f  mov     rcx, [rax+8]
0x140022893  mov     rax, [rcx]
0x140022896  mov     rax, [rax+60h]
0x14002289a  call    _guard_dispatch_icall
0x14002289f  mov     r13, rax
0x1400228a2  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x1400228a7  movzx   ecx, word ptr [r13+0Ch]
0x1400228ac  test    cx, cx
0x1400228af  jnz     loc_140022F8B
0x1400228b5  mov     ebx, [rbx+8]
0x1400228b8  and     ebx, 0FFFFFFFEh
0x1400228bb  jnz     loc_140022C3F
0x1400228c1  mov     r13d, dword ptr [rsp+130h+var_100]
0x1400228c6  lea     rcx, [rsp+130h+var_F0]; this
0x1400228cb  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x1400228d0  lea     rcx, [rsp+130h+var_F0]; this
0x1400228d5  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x1400228da  lea     rcx, [rbp+57h+var_C8]
0x1400228de  call    ?vUnlock@?$SEMOBJ@$0BE@@@QEAAXXZ; SEMOBJ<20>::vUnlock(void)
0x1400228e3  xor     r9d, r9d; int
0x1400228e6  lea     rcx, [rbp+57h+var_80]; this
0x1400228ea  xor     r8d, r8d; int
0x1400228ed  mov     rdx, rdi; HRGN
0x1400228f0  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x1400228f5  cmp     [rbp+57h+var_80], 0
0x1400228fa  jz      loc_140022C33
0x140022900  mov     rax, [rbp+57h+var_C0]
0x140022904  mov     rbx, [rax]
0x140022907  call    cs:__imp_W32GetSessionState
0x14002290e  nop     dword ptr [rax+rax+00h]
0x140022913  mov     edx, ebx
0x140022915  shr     edx, 8
0x140022918  and     edx, 0FF0000h
0x14002291e  mov     rcx, [rax+58h]
0x140022922  movzx   eax, bx
0x140022925  or      edx, eax
0x140022927  mov     rcx, [rcx+8]
0x14002292b  mov     r8, [rcx]
0x14002292e  mov     rax, [r8+10h]
0x140022932  call    _guard_dispatch_icall
0x140022937  test    rax, rax
0x14002293a  jz      short loc_14002296A
0x14002293c  cmp     [rax+0Eh], sil
0x140022940  jnz     short loc_14002296A
0x140022942  movzx   edx, byte ptr [rax+0Dh]
0x140022946  movzx   ecx, byte ptr [rax+0Ch]
0x14002294a  shl     dx, 8
0x14002294e  or      dx, cx
0x140022951  shr     ebx, 10h
0x140022954  cmp     dx, bx
0x140022957  jnz     short loc_14002296A
0x140022959  mov     eax, [rax+8]
0x14002295c  and     eax, 0FFFFFFFEh
0x14002295f  cmp     eax, 80000012h
0x140022964  jz      loc_140022A99
0x14002296a  mov     rbx, [rbp+57h+var_C0]
0x14002296e  test    dword ptr [rbx+24h], 100000h
0x140022975  jz      loc_140022A99
0x14002297b  mov     r14, [rbx+30h]
0x14002297f  test    r14, r14
0x140022982  jz      loc_140022A99
0x140022988  mov     rdi, [rbp+57h+var_80]
0x14002298c  test    rdi, rdi
0x14002298f  jz      loc_140022A99
0x140022995  xorps   xmm0, xmm0
0x140022998  movups  [rsp+130h+var_F0], xmm0
0x14002299d  movups  [rsp+130h+var_E0], xmm0
0x1400229a2  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400229a9  nop     dword ptr [rax+rax+00h]
0x1400229ae  test    rax, rax
0x1400229b1  jz      loc_140022F21
0x1400229b7  mov     rcx, [rax]
0x1400229ba  test    rcx, rcx
0x1400229bd  jz      loc_140022F21
0x1400229c3  lea     rax, [rcx+8]
0x1400229c7  lea     rcx, [rsp+130h+var_F0]
0x1400229cc  mov     qword ptr [rsp+130h+var_E0], rcx
0x1400229d1  lea     rcx, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400229d8  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x1400229dd  test    rax, rax
0x1400229e0  jz      loc_140022F37
0x1400229e6  mov     rcx, [rax+58h]
0x1400229ea  add     rax, 58h ; 'X'
0x1400229ee  cmp     [rcx+8], rax
0x1400229f2  jnz     loc_14002274A
0x1400229f8  mov     qword ptr [rsp+130h+var_F0], rcx
0x1400229fd  lea     rdx, [rsp+130h+var_F0]
0x140022a02  mov     qword ptr [rsp+130h+var_F0+8], rax
0x140022a07  mov     [rcx+8], rdx
0x140022a0b  lea     rcx, [rsp+130h+var_F0]
0x140022a10  mov     [rax], rcx
0x140022a13  xor     r9d, r9d
0x140022a16  test    dword ptr [rbx+24h], 40000h
0x140022a1d  mov     [rbp+57h+var_D0], r9
0x140022a21  jnz     loc_140022F58
0x140022a27  mov     r11, [rbx+1F0h]
0x140022a2e  xor     eax, eax
0x140022a30  test    r11, r11
0x140022a33  jz      short loc_140022A71
0x140022a35  test    dword ptr [r14+28h], 20000h
0x140022a3d  jnz     loc_140022DDF
0x140022a43  mov     eax, [rbx+24h]
0x140022a46  bt      eax, 0Ch
0x140022a4a  jb      loc_140022FAD
0x140022a50  mov     r8d, [rdi+34h]
0x140022a54  mov     edx, [rdi+3Ch]
0x140022a57  cmp     r8d, edx
0x140022a5a  jz      short loc_140022A6C
0x140022a5c  mov     r10d, [rdi+38h]
0x140022a60  mov     ecx, [rdi+40h]
0x140022a63  cmp     r10d, ecx
0x140022a66  jnz     loc_140022CFB
0x140022a6c  test    r9, r9
0x140022a6f  jmp     short loc_140022A74
0x140022a71  test    rax, rax
0x140022a74  jz      short loc_140022A8F
0x140022a76  call    cs:__imp_W32GetSessionState
0x140022a7d  nop     dword ptr [rax+rax+00h]
0x140022a82  mov     rdx, [rbp+57h+var_D0]
0x140022a86  mov     rcx, [rax+58h]
0x140022a8a  call    HmgDecrementShareReferenceCount
0x140022a8f  lea     rcx, [rsp+130h+var_F0]
0x140022a94  call    PopThreadGuardedObject
0x140022a99  cmp     r13d, esi
0x140022a9c  jnz     loc_140022C7E
0x140022aa2  mov     r14, [rbp+57h+var_80]
0x140022aa6  lea     rcx, [rbp+57h+var_80]; this
0x140022aaa  call    ?bDeleteHandle@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteHandle(void)
0x140022aaf  test    eax, eax
0x140022ab1  jz      loc_140022C73
0x140022ab7  mov     [rbp+57h+var_80], 0
0x140022abf  mov     rbx, [rbp+57h+var_C0]
0x140022ac3  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x140022ac6  mov     rcx, rbx; this
0x140022ac9  or      dword ptr [rbx+24h], 10h
0x140022acd  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140022ad2  lea     rcx, [rbx+458h]; this
0x140022ad9  or      byte ptr [rax+0Fh], 4
0x140022add  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x140022ae2  mov     rax, [rbx+470h]
0x140022ae9  lea     rcx, [rbp+57h+var_C8]; this
0x140022aed  mov     [rbp+57h+var_C8], rax
0x140022af1  mov     qword ptr [rbp+57h+var_48.left], rbx
0x140022af5  mov     byte ptr [rbp+57h+var_48.right], sil
0x140022af9  call    ?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140022afe  mov     rax, [r15+10A8h]
0x140022b05  lea     rcx, [rbp+57h+var_48]
0x140022b09  mov     [rbx+470h], rax
0x140022b10  call    ?reset@?$lambda_call@V_lambda_1_@?1??AcquireDcVisRgnExclusive@DC@@QEAA@XZ@@details@wil@@QEAAXXZ; wil::details::lambda_call<`DC::AcquireDcVisRgnExclusive(void)'::`2'::_lambda_1_>::reset(void)
0x140022b15  mov     rbx, [rbp+57h+var_C0]
0x140022b19  lea     rcx, [rbx+458h]; this
0x140022b20  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x140022b25  mov     rax, [rbp+57h+var_C0]
0x140022b29  mov     [rax+470h], r14
0x140022b30  call    cs:__imp_W32GetSessionState
0x140022b37  nop     dword ptr [rax+rax+00h]
0x140022b3c  mov     rdx, [rax+58h]
0x140022b40  lock xadd [rdx+1098h], esi
0x140022b48  inc     esi
0x140022b4a  mov     [r14+48h], esi
0x140022b4e  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x140022b53  test    rax, rax
0x140022b56  jz      short loc_140022B65
0x140022b58  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x140022b62  and     [rax], rcx
0x140022b65  lea     rcx, [rbx+458h]; this
0x140022b6c  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x140022b71  mov     ebx, [rsp+130h+var_F8]
  ... truncated ...
```
