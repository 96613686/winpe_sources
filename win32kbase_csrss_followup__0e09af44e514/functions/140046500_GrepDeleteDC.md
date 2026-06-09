# GrepDeleteDC

- ea: `0x140046500`
- end: `0x140046b72`
- name: `GrepDeleteDC`
- size: `1650`
- prototype: `__int64 __fastcall(HDC, unsigned int)`
- caller_count: `8`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400173d0`
- `0x14003db70`
- `0x14003ef3c`
- `0x140044e60`
- `0x1400657c0`
- `0x1400dc590`
- `0x140107540`
- `0x1401855f4`

## callees

- `0x140010e60`
- `0x1400187f0`
- `0x14001f670`
- `0x140022ff0`
- `0x140026270`
- `0x140028a70`
- `0x140031bf4`
- `0x140043e04`
- `0x140045030`
- `0x1400450b0`
- `0x1400455f4`
- `0x140045e04`
- `0x140046500`
- `0x1400482a0`
- `0x140049060`
- `0x1400f0fb8`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046832`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046a21`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046832`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046a21`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400465cb`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400465cb`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140046873`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140046873`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140046ae1`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140046ae1`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140046b41`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140046b41`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140046ad2`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140046ad2`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400466ff`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400466ff`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x140046b0a`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x140046b0a`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400466f0`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400466f0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140046553`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140046553`
- `WIN32K!W32GetSessionState` at `0x140046525`
- `WIN32K!W32GetSessionState` at `0x140046525`

## pseudocode

```c
_BOOL8 __fastcall GrepDeleteDC(HDC a1, unsigned int a2)
{
  HDC v3; // rdi
  __int64 v4; // rbx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *CurrentProcessWin32Process; // rax
  DC *v10; // rsi
  char v11; // bl
  DC *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  struct Gre::Base::SESSION_GLOBALS *v16; // r13
  unsigned int v17; // r12d
  __int64 v18; // rdi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r14
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rbx
  int v23; // edi
  __int64 v24; // rax
  unsigned int *v25; // r14
  unsigned int v26; // r13d
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v28; // rax
  __int64 *v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  unsigned int CurrentProcessId; // eax
  DC *v33; // rdx
  unsigned int v34; // ebx
  char *v35; // rax
  struct _ENTRY *v36; // rax
  struct _DC_ATTR *v37; // rax
  __int64 v38; // rdx
  int v39; // ecx
  int v40; // ecx
  DC *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  ThreadRestrictNewHandlesRegion *v44; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  struct Gre::Base::SESSION_GLOBALS *v47; // [rsp+20h] [rbp-60h]
  unsigned int *v48; // [rsp+28h] [rbp-58h] BYREF
  int v49; // [rsp+30h] [rbp-50h]
  __int16 v50; // [rsp+34h] [rbp-4Ch]
  struct Gre::Base::SESSION_GLOBALS *v51; // [rsp+38h] [rbp-48h]
  DC *v52; // [rsp+40h] [rbp-40h] BYREF
  int v53; // [rsp+48h] [rbp-38h]
  struct Gre::Base::SESSION_GLOBALS *v54; // [rsp+50h] [rbp-30h]
  __int64 v55; // [rsp+58h] [rbp-28h]
  __int128 v56; // [rsp+60h] [rbp-20h] BYREF
  __int128 v57; // [rsp+70h] [rbp-10h]
  __int64 v59; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v60; // [rsp+D8h] [rbp+58h]

  v3 = a1;
  v4 = *(_QWORD *)(W32GetSessionState(a1) + 88);
  v54 = (struct Gre::Base::SESSION_GLOBALS *)v4;
  v55 = 0;
  v52 = 0;
  v53 = 0;
  v56 = 0;
  v57 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    v6 = *CurrentThreadWin32Thread;
  else
    v6 = 0;
  v7 = (v6 + 8) & -(__int64)(v6 != 0);
  *(_QWORD *)&v57 = &v52;
  *((_QWORD *)&v57 + 1) = UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic;
  if ( v7 )
  {
    v8 = *(_QWORD *)(((v6 + 8) & -(__int64)(v6 != 0)) + 0x58);
    if ( *(_QWORD *)(v8 + 8) != v7 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v56 = *(_QWORD *)(v7 + 88);
    *((_QWORD *)&v56 + 1) = v7 + 88;
    *(_QWORD *)(v8 + 8) = &v56;
    *(_QWORD *)(v7 + 88) = &v56;
  }
  else
  {
    *((_QWORD *)&v56 + 1) = &v56;
    *(_QWORD *)&v56 = &v56;
  }
  if ( *(_DWORD *)(v4 + 3112)
    || (CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process()) == 0
    || !*CurrentProcessWin32Process )
  {
    DCOBJ::vLockIgnoreAttributes((DCOBJ *)&v52, v3);
LABEL_11:
    v10 = v52;
    goto LABEL_12;
  }
  v16 = v54;
  v10 = 0;
  v50 = 0;
  v17 = (unsigned __int16)v3 | ((unsigned int)v3 >> 8) & 0xFF0000;
  v47 = v54;
  v51 = v54;
  v18 = 0;
  v59 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v59);
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v18 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v20 = v18 + 8;
  v21 = -v18;
  v22 = v20 & -(__int64)(v21 != 0);
  if ( v22 )
  {
    v60 = *(_QWORD *)((v20 & -(__int64)(v21 != 0)) + 0x40);
    v16 = v47;
  }
  else
  {
    v60 = 0;
  }
  v23 = 1;
  v49 = 1;
  v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v16 + 1) + 40LL))(*((_QWORD *)v16 + 1), v17);
  v48 = (unsigned int *)v24;
  v25 = (unsigned int *)v24;
  if ( !v24 )
  {
    v23 = 0;
    KeLeaveCriticalRegion();
    goto LABEL_34;
  }
  _m_prefetchw((const void *)(v24 + 8));
  v26 = *(_DWORD *)(v24 + 8) & 0xFFFFFFFE;
  if ( v26 != (v59 & 0xFFFFFFFC) && v26 && (!v60 || v26 != (unsigned int)UMPDGetThreadClientPID(v22)) )
    goto LABEL_82;
  v16 = v47;
  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v47 + 1) + 96LL))(
                     *((_QWORD *)v47 + 1),
                     *v25)
                 + 14)
      & 0x20) != 0
    && (!v22
     || (v44 = *(ThreadRestrictNewHandlesRegion **)(v22 + 328)) == 0
     || !*((_BYTE *)v44 + 80)
     || !ThreadRestrictNewHandlesRegion::InRegion(v44, v17)) )
  {
    LOBYTE(v50) = 1;
LABEL_82:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v48);
    v25 = v48;
    v23 = v49;
    v16 = v51;
  }
LABEL_34:
  if ( v23 )
  {
    if ( *((_BYTE *)v25 + 14) == 1 && *((_WORD *)v25 + 6) == WORD1(a1) )
    {
      CurrentThread = KeGetCurrentThread();
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v16 + 1) + 96LL))(*((_QWORD *)v16 + 1), *v25);
      v10 = (DC *)v28;
      if ( !*(_WORD *)(v28 + 12) || *(struct _KTHREAD **)(v28 + 16) == CurrentThread )
      {
        _InterlockedAdd16((volatile signed __int16 *)(v28 + 12), 1u);
        *(_QWORD *)(v28 + 16) = CurrentThread;
      }
      else
      {
        v10 = 0;
      }
    }
    v29 = (__int64 *)*((_QWORD *)v16 + 1);
    v30 = *v29;
    v31 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v29 + 96))(v29, *v25);
    (*(void (__fastcall **)(__int64 *, __int64))(v30 + 48))(v29, v31);
    KeLeaveCriticalRegion();
  }
  v52 = v10;
  if ( v10 )
  {
    if ( *((_DWORD *)v10 + 534) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)v10 + 6);
      v10 = 0;
      v52 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction() != 1
      && (unsigned __int8)PsIsWin32KFilterAuditEnabled() )
    {
      PsGetWin32KFilterSet();
    }
    v10 = v52;
  }
  if ( !v10 )
    goto LABEL_56;
  if ( (*((_DWORD *)v10 + 11) & 2) == 0 )
  {
    CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
    v33 = v52;
    v34 = CurrentProcessId & 0xFFFFFFFC;
    if ( *(_QWORD *)v52 )
    {
      v35 = (char *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v54 + 1) + 8LL))(*((_QWORD *)v54 + 1));
    }
    else
    {
      v35 = (char *)v52 + 2152;
      *(_OWORD *)((char *)v52 + 2152) = 0;
      *((_QWORD *)v33 + 271) = 0;
      *((_DWORD *)v33 + 540) = -2147483630;
      *((_QWORD *)v33 + 271) = 0;
    }
    if ( v34 == (*((_DWORD *)v35 + 2) & 0xFFFFFFFE) )
    {
      v36 = DC::PentryFromPobj(v52, v54);
      if ( v36 )
      {
        v37 = (struct _DC_ATTR *)GreDecodeUserModePointer(*((void **)v36 + 2));
        if ( v37 )
        {
          if ( !(unsigned int)DC::SaveAttributes(v52, v37) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)v52 + 6);
            v52 = 0;
            goto LABEL_56;
          }
        }
      }
    }
    *((_DWORD *)v52 + 11) |= 2u;
    v10 = v52;
    v53 = 1;
  }
  v3 = a1;
  if ( (*((_DWORD *)v10 + 130) & 4) != 0 )
  {
    *((_DWORD *)v10 + 130) &= ~4u;
    v38 = *((_QWORD *)v10 + 122);
    v39 = *(_DWORD *)(v38 + 340);
    if ( (*((_DWORD *)v10 + 130) & 1) != 0 )
      v40 = v39 | 0x16090;
    else
      v40 = v39 | 0x6090;
    *(_DWORD *)(v38 + 340) = v40;
    goto LABEL_11;
  }
LABEL_12:
  if ( !v10 )
  {
LABEL_56:
    EngSetLastError(0xAAu);
    v41 = v52;
    if ( v52 )
    {
      if ( v53 && (*((_DWORD *)v52 + 11) & 2) != 0 )
      {
        DCOBJ::RestoreAttributesHelper((DCOBJ *)&v52);
        *((_DWORD *)v52 + 11) &= ~2u;
        v41 = v52;
        v53 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)v41 + 6);
      v52 = 0;
    }
    v42 = v56;
    if ( *(__int128 **)(v56 + 8) != &v56 || (v43 = *((_QWORD *)&v56 + 1), **((__int128 ***)&v56 + 1) != &v56) )
LABEL_5:
      __fastfail(3u);
    **((_QWORD **)&v56 + 1) = v56;
    *(_QWORD *)(v42 + 8) = v43;
    return 0;
  }
  if ( (a2 & 0x400000) != 0 )
  {
    *((_BYTE *)v10 + 2090) = 0;
    v10 = v52;
  }
  if ( !*((_BYTE *)v10 + 2090) )
  {
    v11 = 0;
    if ( XDCOBJ::bDelete((XDCOBJ *)&v52, a2) )
      goto LABEL_17;
    EngSetLastError(0xAAu);
    DCOBJ::~DCOBJ((DCOBJ *)&v52);
    return 0;
  }
  v11 = 1;
  XDCOBJ::bCleanDC((XDCOBJ *)&v52, a2 & 0x1000000);
LABEL_17:
  v12 = v52;
  if ( v52 )
  {
    if ( v53 && (*((_DWORD *)v52 + 11) & 2) != 0 )
    {
      DCOBJ::RestoreAttributesHelper((DCOBJ *)&v52);
      *((_DWORD *)v52 + 11) &= ~2u;
      v12 = v52;
      v53 = 0;
    }
    _InterlockedDecrement16((volatile signed __int16 *)v12 + 6);
    v52 = 0;
  }
  v13 = v56;
  if ( *(__int128 **)(v56 + 8) != &v56 )
    goto LABEL_5;
  v14 = *((_QWORD *)&v56 + 1);
  if ( **((__int128 ***)&v56 + 1) != &v56 )
    goto LABEL_5;
  **((_QWORD **)&v56 + 1) = v56;
  *(_QWORD *)(v13 + 8) = v14;
  return !v11 || (unsigned int)UserReleaseDC(v3) != 0;
}

```

## disassembly

```asm
0x140046500  mov     [rsp-38h+arg_8], rbx
0x140046505  mov     [rsp-38h+arg_0], rcx
0x14004650a  push    rbp
0x14004650b  push    rsi
0x14004650c  push    rdi
0x14004650d  push    r12
0x14004650f  push    r13
0x140046511  push    r14
0x140046513  push    r15
0x140046515  mov     rbp, rsp
0x140046518  sub     rsp, 80h
0x14004651f  mov     r15d, edx
0x140046522  mov     rdi, rcx
0x140046525  call    cs:__imp_W32GetSessionState
0x14004652c  nop     dword ptr [rax+rax+00h]
0x140046531  xor     r14d, r14d
0x140046534  xorps   xmm0, xmm0
0x140046537  mov     rbx, [rax+58h]
0x14004653b  mov     [rbp+var_30], rbx
0x14004653f  mov     [rbp+var_28], r14
0x140046543  mov     [rbp+var_40], r14
0x140046547  mov     [rbp+var_38], r14d
0x14004654b  movups  [rbp+var_20], xmm0
0x14004654f  movups  [rbp+var_10], xmm0
0x140046553  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14004655a  nop     dword ptr [rax+rax+00h]
0x14004655f  test    rax, rax
0x140046562  jz      loc_140046AC3
0x140046568  mov     rcx, [rax]
0x14004656b  lea     rax, [rcx+8]
0x14004656f  neg     rcx
0x140046572  sbb     rdx, rdx
0x140046575  and     rdx, rax
0x140046578  lea     rax, [rbp+var_40]
0x14004657c  mov     qword ptr [rbp+var_10], rax
0x140046580  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VDRVOBJ@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic(void *)
0x140046587  mov     qword ptr [rbp+var_10+8], rax
0x14004658b  jz      loc_140046B2C
0x140046591  lea     rax, [rdx+58h]
0x140046595  mov     rcx, [rax]
0x140046598  cmp     [rcx+8], rax
0x14004659c  jz      short loc_1400465A5
0x14004659e  mov     ecx, 3
0x1400465a3  int     29h; Win8: RtlFailFast(ecx)
0x1400465a5  mov     qword ptr [rbp+var_20], rcx
0x1400465a9  lea     rdx, [rbp+var_20]
0x1400465ad  mov     qword ptr [rbp+var_20+8], rax
0x1400465b1  mov     [rcx+8], rdx
0x1400465b5  lea     rcx, [rbp+var_20]
0x1400465b9  mov     [rax], rcx
0x1400465bc  mov     r12d, 1
0x1400465c2  cmp     [rbx+0C28h], r14d
0x1400465c9  jnz     short loc_1400465E5
0x1400465cb  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400465d2  nop     dword ptr [rax+rax+00h]
0x1400465d7  test    rax, rax
0x1400465da  jz      short loc_1400465E5
0x1400465dc  cmp     [rax], r14
0x1400465df  jnz     loc_1400466BD
0x1400465e5  mov     rdx, rdi; HDC
0x1400465e8  lea     rcx, [rbp+var_40]; this
0x1400465ec  call    ?vLockIgnoreAttributes@DCOBJ@@QEAAXPEAUHDC__@@@Z; DCOBJ::vLockIgnoreAttributes(HDC__ *)
0x1400465f1  mov     rsi, [rbp+var_40]
0x1400465f5  test    rsi, rsi
0x1400465f8  jz      loc_14004694A
0x1400465fe  bt      r15d, 16h
0x140046603  jnb     short loc_140046610
0x140046605  mov     [rsi+82Ah], r14b
0x14004660c  mov     rsi, [rbp+var_40]
0x140046610  lea     rcx, [rbp+var_40]; this
0x140046614  cmp     [rsi+82Ah], r14b
0x14004661b  jnz     loc_1400469AB
0x140046621  mov     edx, r15d; unsigned int
0x140046624  mov     bl, r14b
0x140046627  call    ?bDelete@XDCOBJ@@QEAA_NK@Z; XDCOBJ::bDelete(ulong)
0x14004662c  test    al, al
0x14004662e  jz      loc_140046A32
0x140046634  mov     rcx, [rbp+var_40]
0x140046638  test    rcx, rcx
0x14004663b  jz      short loc_14004666C
0x14004663d  cmp     [rbp+var_38], r14d
0x140046641  jz      short loc_140046663
0x140046643  mov     eax, [rcx+2Ch]
0x140046646  test    al, 2
0x140046648  jz      short loc_140046663
0x14004664a  lea     rcx, [rbp+var_40]; this
0x14004664e  call    ?RestoreAttributesHelper@DCOBJ@@AEAAXXZ; DCOBJ::RestoreAttributesHelper(void)
0x140046653  mov     rax, [rbp+var_40]
0x140046657  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14004665b  mov     rcx, [rbp+var_40]
0x14004665f  mov     [rbp+var_38], r14d
0x140046663  lock dec word ptr [rcx+0Ch]
0x140046668  mov     [rbp+var_40], r14
0x14004666c  mov     rax, qword ptr [rbp+var_20]
0x140046670  lea     rcx, [rbp+var_20]
0x140046674  cmp     [rax+8], rcx
0x140046678  jnz     loc_14004659E
0x14004667e  mov     rcx, qword ptr [rbp+var_20+8]
0x140046682  lea     rdx, [rbp+var_20]
0x140046686  cmp     [rcx], rdx
0x140046689  jnz     loc_14004659E
0x14004668f  mov     [rcx], rax
0x140046692  mov     [rax+8], rcx
0x140046696  test    bl, bl
0x140046698  jnz     loc_140046A67
0x14004669e  mov     eax, r12d
0x1400466a1  mov     rbx, [rsp+80h+arg_8]
0x1400466a9  add     rsp, 80h
0x1400466b0  pop     r15
0x1400466b2  pop     r14
0x1400466b4  pop     r13
0x1400466b6  pop     r12
0x1400466b8  pop     rdi
0x1400466b9  pop     rsi
0x1400466ba  pop     rbp
0x1400466bb  retn
0x1400466bd  mov     r13, [rbp+var_30]
0x1400466c1  lea     rcx, [rbp+arg_10]
0x1400466c5  movzx   eax, di
0x1400466c8  mov     r12d, edi
0x1400466cb  shr     r12d, 8
0x1400466cf  mov     rsi, r14
0x1400466d2  and     r12d, 0FF0000h
0x1400466d9  mov     [rbp+var_4C], r14w
0x1400466de  or      r12d, eax
0x1400466e1  mov     [rbp+var_60], r13
0x1400466e5  mov     [rbp+var_48], r13
0x1400466e9  mov     rdi, r14
0x1400466ec  mov     [rbp+arg_10], r14
0x1400466f0  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x1400466f7  nop     dword ptr [rax+rax+00h]
0x1400466fc  mov     r14, rax
0x1400466ff  call    cs:__imp_KeIsAttachedProcess
0x140046706  nop     dword ptr [rax+rax+00h]
0x14004670b  test    al, al
0x14004670d  jnz     loc_140046ACB
0x140046713  test    r14, r14
0x140046716  jz      short loc_14004671B
0x140046718  mov     rdi, [r14]
0x14004671b  lea     rax, [rdi+8]
0x14004671f  neg     rdi
0x140046722  sbb     rbx, rbx
0x140046725  and     rbx, rax
0x140046728  jz      loc_140046B23
0x14004672e  mov     r13, [rbx+40h]
0x140046732  mov     [rbp+arg_18], r13
0x140046736  mov     r13, [rbp+var_60]
0x14004673a  mov     ecx, 1
0x14004673f  mov     edx, r12d
0x140046742  mov     edi, ecx
0x140046744  mov     [rbp+var_50], ecx
0x140046747  mov     rcx, [r13+8]
0x14004674b  mov     rax, [rcx]
0x14004674e  mov     rax, [rax+28h]
0x140046752  call    _guard_dispatch_icall
0x140046757  xor     ecx, ecx
0x140046759  mov     [rbp+var_58], rax
0x14004675d  mov     r14, rax
0x140046760  test    rax, rax
0x140046763  jz      loc_140046A1F
0x140046769  prefetchw byte ptr [rax+8]
0x14004676d  mov     r13d, [rax+8]
0x140046771  mov     eax, dword ptr [rbp+arg_10]
0x140046774  and     r13d, 0FFFFFFFEh
0x140046778  and     eax, 0FFFFFFFCh
0x14004677b  cmp     r13d, eax
0x14004677e  jnz     loc_1400469C2
0x140046784  mov     r13, [rbp+var_60]
0x140046788  mov     edx, [r14]
0x14004678b  mov     rcx, [r13+8]
0x14004678f  mov     rax, [rcx]
0x140046792  mov     rax, [rax+60h]
0x140046796  call    _guard_dispatch_icall
0x14004679b  test    byte ptr [rax+0Eh], 20h
0x14004679f  jnz     loc_140046A7E
0x1400467a5  xor     r12d, r12d
0x1400467a8  test    edi, edi
0x1400467aa  jz      loc_14004683E
0x1400467b0  cmp     byte ptr [r14+0Eh], 1
0x1400467b5  jnz     short loc_14004680D
0x1400467b7  movzx   eax, byte ptr [r14+0Ch]
0x1400467bc  movzx   ecx, byte ptr [r14+0Dh]
0x1400467c1  shl     cx, 8
0x1400467c5  or      cx, ax
0x1400467c8  mov     eax, dword ptr [rbp+arg_0]
0x1400467cb  shr     eax, 10h
0x1400467ce  cmp     cx, ax
0x1400467d1  jnz     short loc_14004680D
0x1400467d3  mov     rbx, gs:188h
0x1400467dc  mov     rcx, [r13+8]
0x1400467e0  mov     edx, [r14]
0x1400467e3  mov     rax, [rcx]
0x1400467e6  mov     rax, [rax+60h]
0x1400467ea  call    _guard_dispatch_icall
0x1400467ef  mov     rsi, rax
0x1400467f2  movzx   ecx, word ptr [rax+0Ch]
0x1400467f6  test    cx, cx
0x1400467f9  jnz     loc_140046A4A
0x1400467ff  mov     ecx, 1
0x140046804  lock add [rax+0Ch], cx
0x140046809  mov     [rax+10h], rbx
0x14004680d  mov     rdi, [r13+8]
0x140046811  mov     edx, [r14]
0x140046814  mov     rcx, rdi
0x140046817  mov     rbx, [rdi]
0x14004681a  mov     rax, [rbx+60h]
0x14004681e  call    _guard_dispatch_icall
0x140046823  mov     rdx, rax
0x140046826  mov     rcx, rdi
0x140046829  mov     rax, [rbx+30h]
0x14004682d  call    _guard_dispatch_icall
0x140046832  call    cs:__imp_KeLeaveCriticalRegion
0x140046839  nop     dword ptr [rax+rax+00h]
0x14004683e  xor     r14d, r14d
0x140046841  mov     [rbp+var_40], rsi
0x140046845  test    rsi, rsi
0x140046848  jz      loc_140046AFA
0x14004684e  lea     r12d, [r14+1]
0x140046852  cmp     [rsi+858h], r14d
0x140046859  jnz     loc_140046B4F
0x14004685f  test    rsi, rsi
0x140046862  jz      loc_14004694A
0x140046868  mov     eax, [rsi+2Ch]
0x14004686b  test    al, 2
0x14004686d  jnz     loc_140046904
0x140046873  call    cs:__imp_PsGetCurrentProcessId
0x14004687a  nop     dword ptr [rax+rax+00h]
0x14004687f  mov     rdx, [rbp+var_40]
0x140046883  mov     rbx, rax
0x140046886  and     ebx, 0FFFFFFFCh
0x140046889  cmp     [rdx], r14
0x14004688c  jnz     loc_140046992
0x140046892  lea     rax, [rdx+868h]
0x140046899  xorps   xmm0, xmm0
0x14004689c  movups  xmmword ptr [rax], xmm0
0x14004689f  xor     ecx, ecx
0x1400468a1  mov     [rax+10h], rcx
0x1400468a5  mov     dword ptr [rdx+870h], 80000012h
0x1400468af  mov     [rdx+878h], r14
0x1400468b6  mov     eax, [rax+8]
0x1400468b9  and     eax, 0FFFFFFFEh
0x1400468bc  cmp     ebx, eax
0x1400468be  jnz     short loc_1400468F4
0x1400468c0  mov     rdx, [rbp+var_30]; struct Gre::Base::SESSION_GLOBALS *
0x1400468c4  mov     rcx, [rbp+var_40]; this
0x1400468c8  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x1400468cd  test    rax, rax
0x1400468d0  jz      short loc_1400468F4
0x1400468d2  mov     rcx, [rax+10h]; void *
0x1400468d6  call    ?GreDecodeUserModePointer@@YAPEAXPEAX@Z; GreDecodeUserModePointer(void *)
0x1400468db  test    rax, rax
0x1400468de  jz      short loc_1400468F4
0x1400468e0  mov     rcx, [rbp+var_40]; this
0x1400468e4  mov     rdx, rax; struct _DC_ATTR *
0x1400468e7  call    ?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x1400468ec  test    eax, eax
0x1400468ee  jz      loc_140046B60
0x1400468f4  mov     rax, [rbp+var_40]
0x1400468f8  or      dword ptr [rax+2Ch], 2
0x1400468fc  mov     rsi, [rbp+var_40]
0x140046900  mov     [rbp+var_38], r12d
0x140046904  mov     eax, [rsi+208h]
0x14004690a  mov     rdi, [rbp+arg_0]
0x14004690e  test    al, 4
0x140046910  jz      loc_1400465F5
0x140046916  and     dword ptr [rsi+208h], 0FFFFFFFBh
0x14004691d  mov     rdx, [rsi+3D0h]
0x140046924  mov     eax, [rsi+208h]
0x14004692a  mov     ecx, [rdx+154h]
0x140046930  test    r12b, al
0x140046933  jz      loc_140046A5C
0x140046939  or      ecx, 16090h
0x14004693f  mov     [rdx+154h], ecx
0x140046945  jmp     loc_1400465F1
0x14004694a  mov     ecx, 0AAh; iError
0x14004694f  call    EngSetLastError
0x140046954  mov     rcx, [rbp+var_40]
0x140046958  test    rcx, rcx
0x14004695b  jnz     loc_1400469EB
0x140046961  mov     rax, qword ptr [rbp+var_20]
0x140046965  lea     rcx, [rbp+var_20]
0x140046969  cmp     [rax+8], rcx
0x14004696d  jnz     loc_14004659E
0x140046973  mov     rcx, qword ptr [rbp+var_20+8]
0x140046977  lea     rdx, [rbp+var_20]
0x14004697b  cmp     [rcx], rdx
0x14004697e  jnz     loc_14004659E
0x140046984  mov     [rcx], rax
0x140046987  mov     [rax+8], rcx
0x14004698b  xor     eax, eax
0x14004698d  jmp     loc_1400466A1
0x140046992  mov     rax, [rbp+var_30]
0x140046996  mov     rcx, [rax+8]
0x14004699a  mov     rax, [rcx]
0x14004699d  mov     rax, [rax+8]
0x1400469a1  call    _guard_dispatch_icall
0x1400469a6  jmp     loc_1400468B6
0x1400469ab  shr     r15d, 18h
0x1400469af  mov     bl, r12b
0x1400469b2  and     r15b, r12b
  ... truncated ...
```
