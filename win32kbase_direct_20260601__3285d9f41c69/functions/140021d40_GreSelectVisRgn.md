# GreSelectVisRgn

- ea: `0x140021d40`
- end: `0x140022683`
- name: `GreSelectVisRgn`
- size: `2371`
- prototype: `__int64 __fastcall(__int64, HRGN, int)`
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
  _QWORD *v15; // r14
  __int64 v16; // rbx
  __int64 v17; // rdi
  unsigned int v18; // ebx
  __int64 v19; // rbx
  __int64 SessionState; // rax
  __int64 v21; // rax
  DC *v22; // rbx
  __int64 v23; // rsi
  _DWORD *v24; // rdi
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r11
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  int v33; // r9d
  LONG v34; // r8d
  int v35; // r10d
  LONG v36; // edx
  bool v37; // zf
  __int64 v38; // rax
  int v39; // ebx
  int v40; // edi
  __int64 v41; // rsi
  int v42; // r8d
  DC *v43; // rbx
  DC *v44; // rcx
  struct _ENTRY *v45; // rax
  DC *v46; // rbx
  struct _GRETHREAD *v47; // rax
  __int64 v48; // rax
  _QWORD **v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 result; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  DC *v56; // rbx
  __int64 *v57; // rax
  int v58; // esi
  LONG v59; // ebx
  __int64 v60; // rax
  bool v61; // cc
  LONG v62; // r9d
  __int64 v63; // rax
  unsigned int sizeScan; // eax
  const struct BaseRustExports *v65; // rbx
  const struct REGION_CORE *v66; // rdi
  HSURF v67; // rdx
  __int64 v68; // [rsp+30h] [rbp-A9h] BYREF
  __int128 v69; // [rsp+38h] [rbp-A1h] BYREF
  __int128 v70; // [rsp+48h] [rbp-91h]
  __int64 v71; // [rsp+58h] [rbp-81h]
  DC *v72; // [rsp+60h] [rbp-79h] BYREF
  int v73; // [rsp+68h] [rbp-71h]
  struct Gre::Base::SESSION_GLOBALS *v74; // [rsp+70h] [rbp-69h]
  __int64 v75; // [rsp+78h] [rbp-61h]
  __int128 v76; // [rsp+80h] [rbp-59h] BYREF
  __int128 v77; // [rsp+90h] [rbp-49h]
  __int64 v78; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD **v81; // [rsp+B8h] [rbp-21h]
  int v82; // [rsp+D8h] [rbp-1h]
  struct _RECTL v83; // [rsp+E0h] [rbp+7h] BYREF

  LODWORD(v78) = a3;
  v72 = 0;
  v73 = 0;
  v74 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState() + 88);
  v75 = 0;
  v72 = 0;
  v73 = 0;
  v76 = 0;
  v77 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    v7 = *CurrentThreadWin32Thread;
  else
    v7 = 0;
  v8 = (v7 + 8) & -(__int64)(v7 != 0);
  *(_QWORD *)&v77 = &v72;
  *((_QWORD *)&v77 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  if ( v8 )
  {
    v9 = *(_QWORD *)(((v7 + 8) & -(__int64)(v7 != 0)) + 0x58);
    if ( *(_QWORD *)(v9 + 8) != v8 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v76 = *(_QWORD *)(v8 + 88);
    *((_QWORD *)&v76 + 1) = v8 + 88;
    *(_QWORD *)(v9 + 8) = &v76;
    *(_QWORD *)(v8 + 88) = &v76;
  }
  else
  {
    *((_QWORD *)&v76 + 1) = &v76;
    *(_QWORD *)&v76 = &v76;
  }
  LOBYTE(v6) = 1;
  v72 = (DC *)HmgShareLock(v74, a1, v6);
  if ( v72 )
  {
    v10 = v74;
    v11 = (HSEMAPHORE)(*(_QWORD *)v74 + 1248LL);
    GreAcquireSemaphoreInternal(v11);
    GrepAcquireLockValidate<11>();
    v12 = v72;
    v13 = 1;
    *((_DWORD *)v72 + 9) |= 0x10u;
    v14 = DC::PentryFromPobj(v12, v10);
    *((_BYTE *)v14 + 15) |= 4u;
    if ( !a2 )
    {
      DC::vReleaseVis(v72, v10);
      DC::bSetDefaultRegion(v72);
      goto LABEL_54;
    }
    PsGetCurrentProcessId();
    v15 = *(_QWORD **)(W32GetSessionState() + 88);
    v68 = *v15 + 1512LL;
    GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>();
    HANDLELOCK::HANDLELOCK(&v69, v15, a2, 1);
    if ( DWORD2(v69) )
    {
      v16 = v69;
      if ( *(_BYTE *)(v69 + 14) == 4
        && *(_WORD *)(v69 + 12) == WORD1(a2)
        && ((v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v70 + 8) + 96LL))(
                     *(_QWORD *)(v70 + 8),
                     *(unsigned int *)v69),
             GreGetCurrentThread(),
             !*(_WORD *)(v17 + 12))
         || *(struct _KTHREAD **)(v17 + 16) == KeGetCurrentThread()) )
      {
        v18 = *(_DWORD *)(v16 + 8) & 0xFFFFFFFE;
        if ( v18 && (unsigned int)HmgIncProcessHandleCount(0) )
        {
          HmgDecProcessHandleCount(v15, v18);
          HANDLELOCK::Pid((HANDLELOCK *)&v69, 0);
          *(_WORD *)(v17 + 14) &= ~0x10u;
        }
      }
      else
      {
        BYTE13(v69) = 1;
      }
      HANDLELOCK::vUnlock((HANDLELOCK *)&v69);
    }
    HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v69);
    SEMOBJ<20>::vUnlock(&v68);
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v79, a2, 0, 0);
    if ( !v79 )
      goto LABEL_65;
    v19 = *(_QWORD *)v72;
    SessionState = W32GetSessionState();
    v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(SessionState + 88) + 8LL) + 16LL))(
            *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 8LL),
            (unsigned __int16)v19 | ((unsigned int)v19 >> 8) & 0xFF0000);
    if ( v21
      && *(_BYTE *)(v21 + 14) == 1
      && *(_WORD *)(v21 + 12) == WORD1(v19)
      && (*(_DWORD *)(v21 + 8) & 0xFFFFFFFE) == 0x80000012
      || (v22 = v72, (*((_DWORD *)v72 + 9) & 0x100000) == 0)
      || (v23 = *((_QWORD *)v72 + 6)) == 0
      || (v24 = (_DWORD *)v79) == 0 )
    {
LABEL_40:
      v39 = v78;
      v40 = 1;
      if ( (_DWORD)v78 == 1 )
      {
        v41 = v79;
        if ( (unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v79) )
        {
          v79 = 0;
          goto LABEL_43;
        }
        v13 = 0;
LABEL_71:
        if ( !v13 && v39 == 1 )
        {
LABEL_47:
          if ( !v82 )
            RGNOBJ::UpdateUserRgn((RGNOBJ *)&v79);
          if ( v79 )
            _InterlockedDecrement16((volatile signed __int16 *)(v79 + 12));
          v48 = v80;
          if ( *(__int64 **)(v80 + 8) != &v80 )
            goto LABEL_5;
          v49 = v81;
          if ( *v81 != &v80 )
            goto LABEL_5;
          *v81 = (_QWORD *)v80;
          *(_QWORD *)(v48 + 8) = v49;
LABEL_54:
          if ( v11 )
          {
            if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
              McTemplateK0pz_EtwWriteTransfer(
                (_DWORD)v49,
                (unsigned int)LockRelease,
                v42,
                (_DWORD)v11,
                (__int64)L"VisRgnPublish");
            GrepReleaseLockValidate<11>();
            GreReleaseSemaphoreSharedInternal(v11);
          }
          if ( v72 )
          {
            v50 = W32GetSessionState();
            HmgDecrementShareReferenceCount(*(_QWORD *)(v50 + 88), v72);
            v72 = 0;
          }
          v51 = v76;
          if ( *(__int128 **)(v76 + 8) == &v76 )
          {
            v52 = *((_QWORD *)&v76 + 1);
            if ( **((__int128 ***)&v76 + 1) == &v76 )
            {
              **((_QWORD **)&v76 + 1) = v76;
              result = v13;
              *(_QWORD *)(v51 + 8) = v52;
              return result;
            }
          }
LABEL_5:
          __fastfail(3u);
        }
        if ( !v40 )
        {
LABEL_44:
          v46 = v72;
          GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v72 + 1112));
          *((_QWORD *)v72 + 142) = v41;
          *(_DWORD *)(v41 + 72) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState() + 88)
                                                                                  + 4248LL));
          v47 = GreGetCurrentThreadCrossSessionCheck();
          if ( v47 )
            *(_QWORD *)v47 &= ~0x4000000000uLL;
          GrePushLock::ReleaseLock((DC *)((char *)v46 + 1112));
          goto LABEL_47;
        }
LABEL_43:
        v43 = v72;
        v44 = v72;
        *((_DWORD *)v72 + 9) |= 0x10u;
        v45 = DC::PentryFromPobj(v44, v10);
        *((_BYTE *)v45 + 15) |= 4u;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v43 + 1112));
        v68 = *((_QWORD *)v43 + 142);
        *(_QWORD *)&v83.left = v43;
        LOBYTE(v83.right) = 1;
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v68);
        *((_QWORD *)v43 + 142) = *((_QWORD *)v10 + 533);
        _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v83);
        goto LABEL_44;
      }
      if ( (_DWORD)v78 != 2 )
      {
        if ( (_DWORD)v78 != 4 )
        {
          v41 = 0;
          goto LABEL_43;
        }
        v56 = v72;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v72 + 1112));
        *(_QWORD *)&v83.left = v56;
        LOBYTE(v83.right) = 1;
        v41 = *((_QWORD *)v72 + 142);
        if ( v41 )
        {
          if ( v41 != *((_QWORD *)v10 + 533) )
          {
            v68 = *((_QWORD *)v72 + 142);
            RGNOBJAPI::bSwap((RGNOBJAPI *)&v79, (struct RGNOBJ *)&v68);
            v41 = v68;
            v40 = 0;
LABEL_80:
            _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v83);
            v39 = v78;
            goto LABEL_71;
          }
        }
        else
        {
          v41 = *((_QWORD *)v10 + 533);
        }
        v13 = 0;
        goto LABEL_80;
      }
      sizeScan = REGION_CORE::get_sizeScan((REGION_CORE *)(v79 + 24));
      v68 = 0;
      RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v68, sizeScan);
      v41 = v68;
      if ( v68 )
      {
        if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
        {
          v65 = *(const struct BaseRustExports **)WPP_MAIN_CB.Dpc.ProcessorHistory;
          v66 = (const struct REGION_CORE *)((v68 + 24) & -(__int64)(v68 != 0));
          (*(void (__fastcall **)(const struct REGION_CORE *, __int64, __int64))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory
                                                                               + 48LL))(
            v66,
            (v79 + 24) & -(__int64)(v79 != 0),
            -v79);
          RgnCaptureLiveMemoryDumpOnZeroSizedScan(v65, v66);
        }
        else
        {
          v78 = (v68 + 24) & -(__int64)(v68 != 0);
          v68 = (v79 + 24) & -(__int64)(v79 != 0);
          RGNCOREOBJ::vCopy((RGNCOREOBJ *)&v78, (const struct RGNCOREOBJ *)&v68);
        }
        goto LABEL_43;
      }
LABEL_65:
      v41 = *((_QWORD *)v10 + 533);
      goto LABEL_43;
    }
    v69 = 0;
    v70 = 0;
    v25 = (__int64 *)PsGetCurrentThreadWin32Thread();
    if ( v25 )
      v26 = *v25;
    else
      v26 = 0;
    v27 = (v26 + 8) & -(__int64)(v26 != 0);
    *(_QWORD *)&v70 = &v69;
    *((_QWORD *)&v70 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    if ( v27 )
    {
      v28 = *(_QWORD *)(((v26 + 8) & -(__int64)(v26 != 0)) + 0x58);
      if ( *(_QWORD *)(v28 + 8) != v27 + 88 )
        goto LABEL_5;
      *(_QWORD *)&v69 = *(_QWORD *)(v27 + 88);
      *((_QWORD *)&v69 + 1) = v27 + 88;
      *(_QWORD *)(v28 + 8) = &v69;
      *(_QWORD *)(v27 + 88) = &v69;
    }
    else
    {
      *((_QWORD *)&v69 + 1) = &v69;
      *(_QWORD *)&v69 = &v69;
    }
    v37 = (*((_DWORD *)v22 + 9) & 0x40000) == 0;
    v29 = 0;
    v71 = 0;
    if ( v37 )
    {
      v30 = *((_QWORD *)v22 + 62);
    }
    else
    {
      v67 = (HSURF)*((_QWORD *)v22 + 268);
      if ( v67 )
      {
        SURFREF::vLock((SURFREF *)&v69, v67);
        v29 = v71;
        v30 = v71;
        v31 = v71;
LABEL_31:
        if ( !v30 )
        {
          v37 = v31 == 0;
          goto LABEL_37;
        }
        if ( (*(_DWORD *)(v23 + 40) & 0x20000) != 0 && *(int *)(v30 + 160) < 0
          || (v32 = *((_DWORD *)v22 + 9), (v32 & 0x1000) != 0) && (v32 & 0x4000) == 0
          || (v33 = v24[13], v34 = v24[15], v33 == v34)
          || (v35 = v24[14], v36 = v24[16], v35 == v36)
          || v33 == 0x7FFFFFFF && v36 == 0x80000000 && v35 == 0x7FFFFFFF && v34 == 0x80000000 )
        {
LABEL_36:
          v37 = v29 == 0;
LABEL_37:
          if ( !v37 )
          {
            v38 = W32GetSessionState();
            HmgDecrementShareReferenceCount(*(_QWORD *)(v38 + 88), v71);
          }
          PopThreadGuardedObject(&v69);
          goto LABEL_40;
        }
        v57 = (__int64 *)(v30 + 716);
        v58 = v24[13];
        v59 = v24[14];
        if ( (*(_DWORD *)(v30 + 164) & 0x800) == 0 )
          v57 = (__int64 *)(v30 + 56);
        v60 = *v57;
        if ( v33 >= v34 )
        {
          if ( v33 > v34 )
          {
            v58 = v24[15];
            v34 = v24[13];
          }
          v61 = v35 <= v36;
        }
        else
        {
          v61 = v35 <= v36;
          if ( v35 < v36 )
          {
            if ( v33 >= 0 && (int)v60 >= v34 && v35 >= 0 && SHIDWORD(v60) >= v36 )
              goto LABEL_36;
LABEL_96:
            v62 = 0;
            if ( v58 >= 0 )
              v62 = v58;
            if ( v59 < 0 )
              v59 = 0;
            if ( (int)v60 < v34 )
              v34 = v60;
            if ( SHIDWORD(v60) < v36 )
              v36 = HIDWORD(v60);
            if ( v34 < v62 )
            {
              v62 = v34;
            }
            else if ( v36 < v59 )
            {
              v59 = v36;
            }
            v83.left = v62;
            v83.top = v59;
            v83.right = v34;
            v83.bottom = v36;
            if ( v29 )
            {
              v63 = W32GetSessionState();
              HmgDecrementShareReferenceCount(*(_QWORD *)(v63 + 88), v71);
            }
            PopThreadGuardedObject(&v69);
            RGNOBJ::vSet((RGNOBJ *)&v79, &v83);
            goto LABEL_40;
          }
        }
        if ( !v61 )
        {
          v59 = v24[16];
          v36 = v24[14];
        }
        goto LABEL_96;
      }
      v30 = *(_QWORD *)(v23 + 2544);
    }
    v31 = 0;
    goto LABEL_31;
  }
  v54 = v76;
  if ( *(__int128 **)(v76 + 8) != &v76 )
    goto LABEL_5;
  v55 = *((_QWORD *)&v76 + 1);
  if ( **((__int128 ***)&v76 + 1) != &v76 )
    goto LABEL_5;
  **((_QWORD **)&v76 + 1) = v76;
  *(_QWORD *)(v54 + 8) = v55;
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
