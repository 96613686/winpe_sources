# GreSelectVisRgn

- ea: `0x140021d40`
- end: `0x140022683`
- name: `GreSelectVisRgn`
- size: `2371`
- prototype: ``
- caller_count: `3`
- callee_count: `38`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140066cd0`
- `0x140066fe0`
- `0x140067c4c`

## callees

- `0x140010070`
- `0x140018770`
- `0x1400195ac`
- `0x140019d88`
- `0x14001d160`
- `0x140020444`
- `0x140020ab0`
- `0x1400215d0`
- `0x140021d40`
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

- `ntoskrnl!PsGetCurrentProcessId` at `0x140021e73`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140021e73`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140021daa`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140022000`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140021daa`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140022000`
- `WIN32K!W32GetSessionState` at `0x140021d7f`
- `WIN32K!W32GetSessionState` at `0x140021e7f`
- `WIN32K!W32GetSessionState` at `0x140021f65`
- `WIN32K!W32GetSessionState` at `0x1400220d1`
- `WIN32K!W32GetSessionState` at `0x140022192`
- `WIN32K!W32GetSessionState` at `0x140022243`
- `WIN32K!W32GetSessionState` at `0x14002246b`
- `WIN32K!W32GetSessionState` at `0x140021d7f`
- `WIN32K!W32GetSessionState` at `0x140021e7f`
- `WIN32K!W32GetSessionState` at `0x140021f65`
- `WIN32K!W32GetSessionState` at `0x1400220d1`
- `WIN32K!W32GetSessionState` at `0x140022192`
- `WIN32K!W32GetSessionState` at `0x140022243`
- `WIN32K!W32GetSessionState` at `0x14002246b`

## pseudocode

```c
__int64 __fastcall GreSelectVisRgn(__int64 a1, HRGN a2, int a3)
{
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct Gre::Base::SESSION_GLOBALS *v10; // r15
  HSEMAPHORE v11; // r13
  DC *v12; // rcx
  unsigned int v13; // r12d
  struct _ENTRY *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 SessionState; // rax
  __int64 v26; // rax
  DC *v27; // rbx
  __int64 v28; // rsi
  volatile signed __int16 *v29; // rdi
  __int64 *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r11
  __int64 v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  int v38; // r9d
  LONG v39; // r8d
  int v40; // r10d
  LONG v41; // edx
  bool v42; // zf
  __int64 v43; // rax
  int v44; // ebx
  int v45; // edi
  volatile signed __int16 *v46; // rsi
  int v47; // r8d
  DC *v48; // rbx
  DC *v49; // rcx
  struct _ENTRY *v50; // rax
  DC *v51; // rbx
  __int64 v52; // rcx
  struct _GRETHREAD *v53; // rax
  __int64 v54; // rax
  _QWORD **v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 result; // rax
  __int64 v60; // rax
  __int64 v61; // rcx
  DC *v62; // rbx
  __int64 *v63; // rax
  int v64; // esi
  LONG v65; // ebx
  __int64 v66; // rax
  bool v67; // cc
  LONG v68; // r9d
  __int64 v69; // rax
  unsigned int sizeScan; // eax
  const struct BaseRustExports *v71; // rbx
  const struct REGION_CORE *v72; // rdi
  HSURF v73; // rdx
  volatile signed __int16 *v74; // [rsp+30h] [rbp-A9h] BYREF
  __int128 v75; // [rsp+38h] [rbp-A1h] BYREF
  __int128 v76; // [rsp+48h] [rbp-91h]
  __int64 v77; // [rsp+58h] [rbp-81h]
  DC *v78; // [rsp+60h] [rbp-79h] BYREF
  int v79; // [rsp+68h] [rbp-71h]
  struct Gre::Base::SESSION_GLOBALS *v80; // [rsp+70h] [rbp-69h]
  __int64 v81; // [rsp+78h] [rbp-61h]
  __int128 v82; // [rsp+80h] [rbp-59h] BYREF
  __int128 v83; // [rsp+90h] [rbp-49h]
  unsigned __int64 v84; // [rsp+A0h] [rbp-39h] BYREF
  volatile signed __int16 *v85; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v86; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD **v87; // [rsp+B8h] [rbp-21h]
  int v88; // [rsp+D8h] [rbp-1h]
  struct _RECTL v89; // [rsp+E0h] [rbp+7h] BYREF

  LODWORD(v84) = a3;
  v78 = 0;
  v79 = 0;
  v80 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(a1) + 88);
  v81 = 0;
  v78 = 0;
  v79 = 0;
  v82 = 0;
  v83 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    v7 = *CurrentThreadWin32Thread;
  else
    v7 = 0;
  v8 = (v7 + 8) & -(__int64)(v7 != 0);
  *(_QWORD *)&v83 = &v78;
  *((_QWORD *)&v83 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  if ( v8 )
  {
    v9 = *(_QWORD *)(((v7 + 8) & -(__int64)(v7 != 0)) + 0x58);
    if ( *(_QWORD *)(v9 + 8) != v8 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v82 = *(_QWORD *)(v8 + 88);
    *((_QWORD *)&v82 + 1) = v8 + 88;
    *(_QWORD *)(v9 + 8) = &v82;
    *(_QWORD *)(v8 + 88) = &v82;
  }
  else
  {
    *((_QWORD *)&v82 + 1) = &v82;
    *(_QWORD *)&v82 = &v82;
  }
  LOBYTE(v6) = 1;
  v78 = (DC *)HmgShareLock(v80, a1, v6, 1);
  if ( v78 )
  {
    v10 = v80;
    v11 = (HSEMAPHORE)(*(_QWORD *)v80 + 1248LL);
    GreAcquireSemaphoreInternal(v11);
    GrepAcquireLockValidate<11>();
    v12 = v78;
    v13 = 1;
    *((_DWORD *)v78 + 9) |= 0x10u;
    v14 = DC::PentryFromPobj(v12, v10);
    *((_BYTE *)v14 + 15) |= 4u;
    if ( !a2 )
    {
      DC::vReleaseVis(v78, v10);
      DC::bSetDefaultRegion(v78);
      goto LABEL_54;
    }
    PsGetCurrentProcessId();
    v16 = *(_QWORD **)(W32GetSessionState(v15) + 88);
    v74 = (volatile signed __int16 *)(*v16 + 1512LL);
    GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v17, v74);
    HANDLELOCK::HANDLELOCK(&v75, v16, a2, 1);
    if ( DWORD2(v75) )
    {
      v18 = v75;
      if ( *(_BYTE *)(v75 + 14) == 4
        && *(_WORD *)(v75 + 12) == WORD1(a2)
        && ((v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v76 + 8) + 96LL))(
                     *(_QWORD *)(v76 + 8),
                     *(unsigned int *)v75),
             GreGetCurrentThread(),
             !*(_WORD *)(v19 + 12))
         || *(struct _KTHREAD **)(v19 + 16) == KeGetCurrentThread()) )
      {
        v22 = *(_DWORD *)(v18 + 8) & 0xFFFFFFFE;
        if ( v22 && (unsigned int)HmgIncProcessHandleCount(0, v20, v21) )
        {
          HmgDecProcessHandleCount(v16, v22);
          HANDLELOCK::Pid((HANDLELOCK *)&v75, 0);
          *(_WORD *)(v19 + 14) &= ~0x10u;
        }
      }
      else
      {
        BYTE13(v75) = 1;
      }
      HANDLELOCK::vUnlock((HANDLELOCK *)&v75);
    }
    HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v75);
    SEMOBJ<20>::vUnlock(&v74);
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v85, a2, 0, 0);
    if ( !v85 )
      goto LABEL_65;
    v24 = *(_QWORD *)v78;
    SessionState = W32GetSessionState(v23);
    v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(SessionState + 88) + 8LL) + 16LL))(
            *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 8LL),
            (unsigned __int16)v24 | ((unsigned int)v24 >> 8) & 0xFF0000);
    if ( v26
      && *(_BYTE *)(v26 + 14) == 1
      && *(_WORD *)(v26 + 12) == WORD1(v24)
      && (*(_DWORD *)(v26 + 8) & 0xFFFFFFFE) == 0x80000012
      || (v27 = v78, (*((_DWORD *)v78 + 9) & 0x100000) == 0)
      || (v28 = *((_QWORD *)v78 + 6)) == 0
      || (v29 = v85) == 0 )
    {
LABEL_40:
      v44 = v84;
      v45 = 1;
      if ( (_DWORD)v84 == 1 )
      {
        v46 = v85;
        if ( (unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v85) )
        {
          v85 = 0;
          goto LABEL_43;
        }
        v13 = 0;
LABEL_71:
        if ( !v13 && v44 == 1 )
        {
LABEL_47:
          if ( !v88 )
            RGNOBJ::UpdateUserRgn((RGNOBJ *)&v85);
          if ( v85 )
            _InterlockedDecrement16(v85 + 6);
          v54 = v86;
          if ( *(__int64 **)(v86 + 8) != &v86 )
            goto LABEL_5;
          v55 = v87;
          if ( *v87 != &v86 )
            goto LABEL_5;
          *v87 = (_QWORD *)v86;
          *(_QWORD *)(v54 + 8) = v55;
LABEL_54:
          if ( v11 )
          {
            if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
              McTemplateK0pz_EtwWriteTransfer(
                (_DWORD)v55,
                (unsigned int)LockRelease,
                v47,
                (_DWORD)v11,
                (__int64)L"VisRgnPublish");
            GrepReleaseLockValidate<11>();
            GreReleaseSemaphoreSharedInternal(v11);
          }
          if ( v78 )
          {
            v56 = W32GetSessionState(v55);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v56 + 88), v78);
            v78 = 0;
          }
          v57 = v82;
          if ( *(__int128 **)(v82 + 8) == &v82 )
          {
            v58 = *((_QWORD *)&v82 + 1);
            if ( **((__int128 ***)&v82 + 1) == &v82 )
            {
              **((_QWORD **)&v82 + 1) = v82;
              result = v13;
              *(_QWORD *)(v57 + 8) = v58;
              return result;
            }
          }
LABEL_5:
          __fastfail(3u);
        }
        if ( !v45 )
        {
LABEL_44:
          v51 = v78;
          GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v78 + 1112));
          *((_QWORD *)v78 + 142) = v46;
          *((_DWORD *)v46 + 18) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(v52)
                                                                                              + 88)
                                                                                  + 4248LL));
          v53 = GreGetCurrentThreadCrossSessionCheck();
          if ( v53 )
            *(_QWORD *)v53 &= ~0x4000000000uLL;
          GrePushLock::ReleaseLock((DC *)((char *)v51 + 1112));
          goto LABEL_47;
        }
LABEL_43:
        v48 = v78;
        v49 = v78;
        *((_DWORD *)v78 + 9) |= 0x10u;
        v50 = DC::PentryFromPobj(v49, v10);
        *((_BYTE *)v50 + 15) |= 4u;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v48 + 1112));
        v74 = (volatile signed __int16 *)*((_QWORD *)v48 + 142);
        *(_QWORD *)&v89.left = v48;
        LOBYTE(v89.right) = 1;
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v74);
        *((_QWORD *)v48 + 142) = *((_QWORD *)v10 + 533);
        _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v89);
        goto LABEL_44;
      }
      if ( (_DWORD)v84 != 2 )
      {
        if ( (_DWORD)v84 != 4 )
        {
          v46 = 0;
          goto LABEL_43;
        }
        v62 = v78;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v78 + 1112));
        *(_QWORD *)&v89.left = v62;
        LOBYTE(v89.right) = 1;
        v46 = (volatile signed __int16 *)*((_QWORD *)v78 + 142);
        if ( v46 )
        {
          if ( v46 != *((volatile signed __int16 **)v10 + 533) )
          {
            v74 = (volatile signed __int16 *)*((_QWORD *)v78 + 142);
            RGNOBJAPI::bSwap((__int64 **)&v85, (__int64 **)&v74);
            v46 = v74;
            v45 = 0;
LABEL_80:
            _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v89);
            v44 = v84;
            goto LABEL_71;
          }
        }
        else
        {
          v46 = (volatile signed __int16 *)*((_QWORD *)v10 + 533);
        }
        v13 = 0;
        goto LABEL_80;
      }
      sizeScan = REGION_CORE::get_sizeScan((REGION_CORE *)(v85 + 12));
      v74 = 0;
      RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v74, sizeScan);
      v46 = v74;
      if ( v74 )
      {
        if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
        {
          v71 = *(const struct BaseRustExports **)WPP_MAIN_CB.Dpc.ProcessorHistory;
          v72 = (const struct REGION_CORE *)((unsigned __int64)(v74 + 12) & -(__int64)(v74 != 0));
          (*(void (__fastcall **)(const struct REGION_CORE *, unsigned __int64, __int64))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory
                                                                                        + 48LL))(
            v72,
            (unsigned __int64)(v85 + 12) & -(__int64)(v85 != 0),
            -(__int64)v85);
          RgnCaptureLiveMemoryDumpOnZeroSizedScan(v71, v72);
        }
        else
        {
          v84 = (unsigned __int64)(v74 + 12) & -(__int64)(v74 != 0);
          v74 = (volatile signed __int16 *)((unsigned __int64)(v85 + 12) & -(__int64)(v85 != 0));
          RGNCOREOBJ::vCopy((RGNCOREOBJ *)&v84, (const struct RGNCOREOBJ *)&v74);
        }
        goto LABEL_43;
      }
LABEL_65:
      v46 = (volatile signed __int16 *)*((_QWORD *)v10 + 533);
      goto LABEL_43;
    }
    v75 = 0;
    v76 = 0;
    v30 = (__int64 *)PsGetCurrentThreadWin32Thread();
    if ( v30 )
      v31 = *v30;
    else
      v31 = 0;
    v32 = (v31 + 8) & -(__int64)(v31 != 0);
    *(_QWORD *)&v76 = &v75;
    *((_QWORD *)&v76 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    if ( v32 )
    {
      v33 = *(_QWORD *)(((v31 + 8) & -(__int64)(v31 != 0)) + 0x58);
      if ( *(_QWORD *)(v33 + 8) != v32 + 88 )
        goto LABEL_5;
      *(_QWORD *)&v75 = *(_QWORD *)(v32 + 88);
      *((_QWORD *)&v75 + 1) = v32 + 88;
      *(_QWORD *)(v33 + 8) = &v75;
      *(_QWORD *)(v32 + 88) = &v75;
    }
    else
    {
      *((_QWORD *)&v75 + 1) = &v75;
      *(_QWORD *)&v75 = &v75;
    }
    v42 = (*((_DWORD *)v27 + 9) & 0x40000) == 0;
    v34 = 0;
    v77 = 0;
    if ( v42 )
    {
      v35 = *((_QWORD *)v27 + 62);
    }
    else
    {
      v73 = (HSURF)*((_QWORD *)v27 + 268);
      if ( v73 )
      {
        SURFREF::vLock((SURFREF *)&v75, v73);
        v34 = v77;
        v35 = v77;
        v36 = v77;
LABEL_31:
        if ( !v35 )
        {
          v42 = v36 == 0;
          goto LABEL_37;
        }
        if ( (*(_DWORD *)(v28 + 40) & 0x20000) != 0 && *(int *)(v35 + 160) < 0
          || (v37 = *((_DWORD *)v27 + 9), (v37 & 0x1000) != 0) && (v37 & 0x4000) == 0
          || (v38 = *((_DWORD *)v29 + 13), v39 = *((_DWORD *)v29 + 15), v38 == v39)
          || (v40 = *((_DWORD *)v29 + 14), v41 = *((_DWORD *)v29 + 16), v40 == v41)
          || v38 == 0x7FFFFFFF && v41 == 0x80000000 && v40 == 0x7FFFFFFF && v39 == 0x80000000 )
        {
LABEL_36:
          v42 = v34 == 0;
LABEL_37:
          if ( !v42 )
          {
            v43 = W32GetSessionState(v35);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v43 + 88), v77);
          }
          PopThreadGuardedObject(&v75);
          goto LABEL_40;
        }
        v63 = (__int64 *)(v35 + 716);
        v64 = *((_DWORD *)v29 + 13);
        v65 = *((_DWORD *)v29 + 14);
        if ( (*(_DWORD *)(v35 + 164) & 0x800) == 0 )
          v63 = (__int64 *)(v35 + 56);
        v66 = *v63;
        if ( v38 >= v39 )
        {
          if ( v38 > v39 )
          {
            v64 = *((_DWORD *)v29 + 15);
            v39 = *((_DWORD *)v29 + 13);
          }
          v67 = v40 <= v41;
        }
        else
        {
          v67 = v40 <= v41;
          if ( v40 < v41 )
          {
            if ( v38 >= 0 && (int)v66 >= v39 && v40 >= 0 && SHIDWORD(v66) >= v41 )
              goto LABEL_36;
LABEL_96:
            v68 = 0;
            if ( v64 >= 0 )
              v68 = v64;
            if ( v65 < 0 )
              v65 = 0;
            if ( (int)v66 < v39 )
              v39 = v66;
            if ( SHIDWORD(v66) < v41 )
              v41 = HIDWORD(v66);
            if ( v39 < v68 )
            {
              v68 = v39;
            }
            else if ( v41 < v65 )
            {
              v65 = v41;
            }
            v89.left = v68;
            v89.top = v65;
            v89.right = v39;
            v89.bottom = v41;
            if ( v34 )
            {
              v69 = W32GetSessionState(v35);
              HmgDecrementShareReferenceCount(*(_QWORD *)(v69 + 88), v77);
            }
            PopThreadGuardedObject(&v75);
            RGNOBJ::vSet((RGNOBJ *)&v85, &v89);
            goto LABEL_40;
          }
        }
        if ( !v67 )
        {
          v65 = *((_DWORD *)v29 + 16);
          v41 = *((_DWORD *)v29 + 14);
        }
        goto LABEL_96;
      }
      v35 = *(_QWORD *)(v28 + 2544);
    }
    v36 = 0;
    goto LABEL_31;
  }
  v60 = v82;
  if ( *(__int128 **)(v82 + 8) != &v82 )
    goto LABEL_5;
  v61 = *((_QWORD *)&v82 + 1);
  if ( **((__int128 ***)&v82 + 1) != &v82 )
    goto LABEL_5;
  **((_QWORD **)&v82 + 1) = v82;
  *(_QWORD *)(v60 + 8) = v61;
  return 0;
}

```

## disassembly

```asm
0x140021d40  mov     [rsp-8+arg_10], rbx
0x140021d45  push    rbp
0x140021d46  push    rsi
0x140021d47  push    rdi
0x140021d48  push    r12
0x140021d4a  push    r13
0x140021d4c  push    r14
0x140021d4e  push    r15
0x140021d50  lea     rbp, [rsp-27h]
0x140021d55  sub     rsp, 100h
0x140021d5c  mov     rax, cs:__security_cookie
0x140021d63  xor     rax, rsp
0x140021d66  mov     [rbp+57h+var_40], rax
0x140021d6a  xor     r14d, r14d
0x140021d6d  mov     dword ptr [rbp+57h+var_90], r8d
0x140021d71  mov     [rbp+57h+var_D0], r14
0x140021d75  mov     rsi, rdx
0x140021d78  mov     [rbp+57h+var_C8], r14d
0x140021d7c  mov     rbx, rcx
0x140021d7f  call    cs:__imp_W32GetSessionState
0x140021d86  nop     dword ptr [rax+rax+00h]
0x140021d8b  xorps   xmm0, xmm0
0x140021d8e  mov     rcx, [rax+58h]
0x140021d92  mov     [rbp+57h+var_C0], rcx
0x140021d96  mov     [rbp+57h+var_B8], r14
0x140021d9a  mov     [rbp+57h+var_D0], r14
0x140021d9e  mov     [rbp+57h+var_C8], r14d
0x140021da2  movups  [rbp+57h+var_B0], xmm0
0x140021da6  movups  [rbp+57h+var_A0], xmm0
0x140021daa  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140021db1  nop     dword ptr [rax+rax+00h]
0x140021db6  test    rax, rax
0x140021db9  jz      loc_1400225B7
0x140021dbf  mov     rcx, [rax]
0x140021dc2  lea     rax, [rcx+8]
0x140021dc6  neg     rcx
0x140021dc9  sbb     rdx, rdx
0x140021dcc  and     rdx, rax
0x140021dcf  lea     rax, [rbp+57h+var_D0]
0x140021dd3  mov     qword ptr [rbp+57h+var_A0], rax
0x140021dd7  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x140021dde  mov     qword ptr [rbp+57h+var_A0+8], rax
0x140021de2  jz      loc_1400225E7
0x140021de8  lea     rax, [rdx+58h]
0x140021dec  mov     rcx, [rax]
0x140021def  cmp     [rcx+8], rax
0x140021df3  jz      short loc_140021DFC
0x140021df5  mov     ecx, 3
0x140021dfa  int     29h; Win8: RtlFailFast(ecx)
0x140021dfc  mov     qword ptr [rbp+57h+var_B0], rcx
0x140021e00  lea     rdx, [rbp+57h+var_B0]
0x140021e04  mov     qword ptr [rbp+57h+var_B0+8], rax
0x140021e08  mov     [rcx+8], rdx
0x140021e0c  lea     rcx, [rbp+57h+var_B0]
0x140021e10  mov     [rax], rcx
0x140021e13  mov     rcx, [rbp+57h+var_C0]
0x140021e17  mov     r9d, 1
0x140021e1d  mov     r8b, r9b
0x140021e20  mov     rdx, rbx
0x140021e23  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140021e28  mov     [rbp+57h+var_D0], rax
0x140021e2c  test    rax, rax
0x140021e2f  jz      loc_1400222B5
0x140021e35  mov     r15, [rbp+57h+var_C0]
0x140021e39  mov     r13, [r15]
0x140021e3c  add     r13, 4E0h
0x140021e43  mov     rcx, r13; Resource
0x140021e46  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x140021e4b  call    ??$GrepAcquireLockValidate@$0L@@@YAXXZ; GrepAcquireLockValidate<11>(void)
0x140021e50  mov     rcx, [rbp+57h+var_D0]; this
0x140021e54  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x140021e57  mov     r12d, 1
0x140021e5d  or      dword ptr [rcx+24h], 10h
0x140021e61  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140021e66  or      byte ptr [rax+0Fh], 4
0x140021e6a  test    rsi, rsi
0x140021e6d  jz      loc_1400224C7
0x140021e73  call    cs:__imp_PsGetCurrentProcessId
0x140021e7a  nop     dword ptr [rax+rax+00h]
0x140021e7f  call    cs:__imp_W32GetSessionState
0x140021e86  nop     dword ptr [rax+rax+00h]
0x140021e8b  mov     r14, [rax+58h]
0x140021e8f  mov     rdx, [r14]
0x140021e92  add     rdx, 5E8h
0x140021e99  mov     [rsp+130h+var_100], rdx
0x140021e9e  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140021ea3  mov     r9d, r12d
0x140021ea6  lea     rcx, [rsp+130h+var_F8]
0x140021eab  mov     r8, rsi
0x140021eae  mov     rdx, r14
0x140021eb1  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x140021eb6  cmp     dword ptr [rsp+130h+var_F8+8], 0
0x140021ebb  jz      short loc_140021F2B
0x140021ebd  mov     rbx, qword ptr [rsp+130h+var_F8]
0x140021ec2  cmp     byte ptr [rbx+0Eh], 4
0x140021ec6  jnz     loc_1400222EF
0x140021ecc  movzx   eax, byte ptr [rbx+0Ch]
0x140021ed0  movzx   ecx, byte ptr [rbx+0Dh]
0x140021ed4  shl     cx, 8
0x140021ed8  or      cx, ax
0x140021edb  mov     eax, esi
0x140021edd  shr     eax, 10h
0x140021ee0  cmp     cx, ax
0x140021ee3  jnz     loc_1400222EF
0x140021ee9  mov     rax, qword ptr [rsp+130h+var_E8]
0x140021eee  mov     edx, [rbx]
0x140021ef0  mov     rcx, [rax+8]
0x140021ef4  mov     rax, [rcx]
0x140021ef7  mov     rax, [rax+60h]
0x140021efb  call    _guard_dispatch_icall
0x140021f00  mov     rdi, rax
0x140021f03  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140021f08  movzx   ecx, word ptr [rdi+0Ch]
0x140021f0c  test    cx, cx
0x140021f0f  jnz     loc_14002262F
0x140021f15  mov     ebx, [rbx+8]
0x140021f18  and     ebx, 0FFFFFFFEh
0x140021f1b  jnz     loc_1400222F9
0x140021f21  lea     rcx, [rsp+130h+var_F8]; this
0x140021f26  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140021f2b  lea     rcx, [rsp+130h+var_F8]; this
0x140021f30  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x140021f35  lea     rcx, [rsp+130h+var_100]
0x140021f3a  call    ?vUnlock@?$SEMOBJ@$0BE@@@QEAAXXZ; SEMOBJ<20>::vUnlock(void)
0x140021f3f  xor     r9d, r9d; int
0x140021f42  lea     rcx, [rbp+57h+var_88]; this
0x140021f46  xor     r8d, r8d; int
0x140021f49  mov     rdx, rsi; HRGN
0x140021f4c  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140021f51  xor     r14d, r14d
0x140021f54  cmp     [rbp+57h+var_88], r14
0x140021f58  jz      loc_1400222E3
0x140021f5e  mov     rax, [rbp+57h+var_D0]
0x140021f62  mov     rbx, [rax]
0x140021f65  call    cs:__imp_W32GetSessionState
0x140021f6c  nop     dword ptr [rax+rax+00h]
0x140021f71  mov     edx, ebx
0x140021f73  shr     edx, 8
0x140021f76  and     edx, 0FF0000h
0x140021f7c  mov     rcx, [rax+58h]
0x140021f80  movzx   eax, bx
0x140021f83  or      edx, eax
0x140021f85  mov     rcx, [rcx+8]
0x140021f89  mov     r8, [rcx]
0x140021f8c  mov     rax, [r8+10h]
0x140021f90  call    _guard_dispatch_icall
0x140021f95  test    rax, rax
0x140021f98  jz      short loc_140021FC8
0x140021f9a  cmp     [rax+0Eh], r12b
0x140021f9e  jnz     short loc_140021FC8
0x140021fa0  movzx   edx, byte ptr [rax+0Dh]
0x140021fa4  movzx   ecx, byte ptr [rax+0Ch]
0x140021fa8  shl     dx, 8
0x140021fac  or      dx, cx
0x140021faf  shr     ebx, 10h
0x140021fb2  cmp     dx, bx
0x140021fb5  jnz     short loc_140021FC8
0x140021fb7  mov     eax, [rax+8]
0x140021fba  and     eax, 0FFFFFFFEh
0x140021fbd  cmp     eax, 80000012h
0x140021fc2  jz      loc_1400220F5
0x140021fc8  mov     rbx, [rbp+57h+var_D0]
0x140021fcc  test    dword ptr [rbx+24h], 100000h
0x140021fd3  jz      loc_1400220F5
0x140021fd9  mov     rsi, [rbx+30h]
0x140021fdd  test    rsi, rsi
0x140021fe0  jz      loc_1400220F5
0x140021fe6  mov     rdi, [rbp+57h+var_88]
0x140021fea  test    rdi, rdi
0x140021fed  jz      loc_1400220F5
0x140021ff3  xorps   xmm0, xmm0
0x140021ff6  movups  [rsp+130h+var_F8], xmm0
0x140021ffb  movups  [rsp+130h+var_E8], xmm0
0x140022000  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140022007  nop     dword ptr [rax+rax+00h]
0x14002200c  test    rax, rax
0x14002200f  jz      loc_1400225BF
0x140022015  mov     rcx, [rax]
0x140022018  lea     rax, [rcx+8]
0x14002201c  neg     rcx
0x14002201f  sbb     rdx, rdx
0x140022022  and     rdx, rax
0x140022025  lea     rax, [rsp+130h+var_F8]
0x14002202a  mov     qword ptr [rsp+130h+var_E8], rax
0x14002202f  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x140022036  mov     qword ptr [rsp+130h+var_E8+8], rax
0x14002203b  jz      loc_140022616
0x140022041  lea     rax, [rdx+58h]
0x140022045  mov     rcx, [rax]
0x140022048  cmp     [rcx+8], rax
0x14002204c  jnz     loc_140021DF5
0x140022052  mov     qword ptr [rsp+130h+var_F8], rcx
0x140022057  lea     rdx, [rsp+130h+var_F8]
0x14002205c  mov     qword ptr [rsp+130h+var_F8+8], rax
0x140022061  mov     [rcx+8], rdx
0x140022065  lea     rcx, [rsp+130h+var_F8]
0x14002206a  mov     [rax], rcx
0x14002206d  test    dword ptr [rbx+24h], 40000h
0x140022074  mov     r11, r14
0x140022077  mov     [rsp+130h+var_D8], r14
0x14002207c  jnz     loc_1400225CF
0x140022082  mov     rcx, [rbx+1F0h]
0x140022089  mov     rax, r14
0x14002208c  test    rcx, rcx
0x14002208f  jz      loc_14002232C
0x140022095  test    dword ptr [rsi+28h], 20000h
0x14002209c  jnz     loc_1400224A1
0x1400220a2  mov     eax, [rbx+24h]
0x1400220a5  bt      eax, 0Ch
0x1400220a9  jb      loc_140022647
0x1400220af  mov     r9d, [rdi+34h]
0x1400220b3  mov     r8d, [rdi+3Ch]
0x1400220b7  cmp     r9d, r8d
0x1400220ba  jz      short loc_1400220CC
0x1400220bc  mov     r10d, [rdi+38h]
0x1400220c0  mov     edx, [rdi+40h]
0x1400220c3  cmp     r10d, edx
0x1400220c6  jnz     loc_1400223C8
0x1400220cc  test    r11, r11
0x1400220cf  jz      short loc_1400220EB
0x1400220d1  call    cs:__imp_W32GetSessionState
0x1400220d8  nop     dword ptr [rax+rax+00h]
0x1400220dd  mov     rdx, [rsp+130h+var_D8]
0x1400220e2  mov     rcx, [rax+58h]
0x1400220e6  call    HmgDecrementShareReferenceCount
0x1400220eb  lea     rcx, [rsp+130h+var_F8]
0x1400220f0  call    PopThreadGuardedObject
0x1400220f5  mov     ebx, dword ptr [rbp+57h+var_90]
0x1400220f8  mov     edi, r12d
0x1400220fb  mov     ecx, ebx
0x1400220fd  sub     ecx, r12d
0x140022100  jnz     loc_140022352
0x140022106  mov     rsi, [rbp+57h+var_88]
0x14002210a  lea     rcx, [rbp+57h+var_88]; this
0x14002210e  call    ?bDeleteHandle@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteHandle(void)
0x140022113  test    eax, eax
0x140022115  jz      loc_140022334
0x14002211b  mov     [rbp+57h+var_88], r14
0x14002211f  mov     rbx, [rbp+57h+var_D0]
0x140022123  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x140022126  mov     rcx, rbx; this
0x140022129  or      dword ptr [rbx+24h], 10h
0x14002212d  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140022132  lea     rcx, [rbx+458h]; this
0x140022139  or      byte ptr [rax+0Fh], 4
0x14002213d  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x140022142  mov     rax, [rbx+470h]
0x140022149  lea     rcx, [rsp+130h+var_100]; this
0x14002214e  mov     [rsp+130h+var_100], rax
0x140022153  mov     qword ptr [rbp+57h+var_50.left], rbx
0x140022157  mov     byte ptr [rbp+57h+var_50.right], 1
0x14002215b  call    ?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140022160  mov     rax, [r15+10A8h]
0x140022167  lea     rcx, [rbp+57h+var_50]
0x14002216b  mov     [rbx+470h], rax
0x140022172  call    ?reset@?$lambda_call@V_lambda_1_@?1??AcquireDcVisRgnExclusive@DC@@QEAA@XZ@@details@wil@@QEAAXXZ; wil::details::lambda_call<`DC::AcquireDcVisRgnExclusive(void)'::`2'::_lambda_1_>::reset(void)
0x140022177  mov     rbx, [rbp+57h+var_D0]
0x14002217b  lea     rcx, [rbx+458h]; this
0x140022182  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x140022187  mov     rax, [rbp+57h+var_D0]
0x14002218b  mov     [rax+470h], rsi
0x140022192  call    cs:__imp_W32GetSessionState
0x140022199  nop     dword ptr [rax+rax+00h]
0x14002219e  mov     rcx, [rax+58h]
0x1400221a2  mov     eax, 1
0x1400221a7  lock xadd [rcx+1098h], eax
0x1400221af  inc     eax
0x1400221b1  mov     [rsi+48h], eax
0x1400221b4  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x1400221b9  test    rax, rax
0x1400221bc  jz      short loc_1400221CB
0x1400221be  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x1400221c8  and     [rax], rcx
0x1400221cb  lea     rcx, [rbx+458h]; this
0x1400221d2  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x1400221d7  cmp     [rbp+57h+var_58], r14d
0x1400221db  jnz     short loc_1400221E6
0x1400221dd  lea     rcx, [rbp+57h+var_88]; this
0x1400221e1  call    ?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x1400221e6  mov     rax, [rbp+57h+var_88]
0x1400221ea  test    rax, rax
0x1400221ed  jz      short loc_1400221F4
0x1400221ef  lock dec word ptr [rax+0Ch]
0x1400221f4  mov     rax, [rbp+57h+var_80]
0x1400221f8  lea     rcx, [rbp+57h+var_80]
0x1400221fc  cmp     [rax+8], rcx
0x140022200  jnz     loc_140021DF5
0x140022206  mov     rcx, [rbp+57h+var_78]
0x14002220a  lea     rdx, [rbp+57h+var_80]
0x14002220e  cmp     [rcx], rdx
0x140022211  jnz     loc_140021DF5
0x140022217  mov     [rcx], rax
0x14002221a  mov     [rax+8], rcx
0x14002221e  test    r13, r13
0x140022221  jz      short loc_14002223D
0x140022223  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r14d
0x14002222a  jnz     loc_140022656
0x140022230  call    ??$GrepReleaseLockValidate@$0L@@@YAXXZ; GrepReleaseLockValidate<11>(void)
0x140022235  mov     rcx, r13; HSEMAPHORE
0x140022238  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
  ... truncated ...
```
