# APIDCOBJ::APIDCOBJ(HDC__ *)

- ea: `0x140025268`
- end: `0x14002574d`
- name: `??0APIDCOBJ@@QEAA@PEAUHDC__@@@Z`
- size: `1253`
- prototype: `APIDCOBJ *__fastcall(APIDCOBJ *__hidden this, HDC)`
- caller_count: `17`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010210`
- `0x140016274`
- `0x140016bb0`
- `0x140018340`
- `0x14001bef0`
- `0x1400222f0`
- `0x140022740`
- `0x14002a870`
- `0x140036190`
- `0x14006f890`
- `0x1400d79e0`
- `0x1400e5e70`
- `0x140120cf0`
- `0x140133960`
- `0x1401638f0`
- `0x140183fb0`
- `0x1401e6a08`

## callees

- `0x14001e034`
- `0x1400232f4`
- `0x140025268`
- `0x140025754`
- `0x1400371c0`
- `0x140079330`
- `0x140111520`
- `0x140120e30`
- `0x14012e228`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400254a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025610`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400254a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025610`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400256a8`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400256a8`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400256e9`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400256e9`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140025699`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140025699`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002536e`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002536e`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x1400256d5`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x1400256d5`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14002535f`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14002535f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400252ce`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140025553`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400252ce`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140025553`
- `WIN32K!W32GetSessionState` at `0x140025290`
- `WIN32K!W32GetSessionState` at `0x140025290`

## pseudocode

```c
APIDCOBJ *__fastcall APIDCOBJ::APIDCOBJ(APIDCOBJ *this, HDC a2)
{
  unsigned int v2; // r15d
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r14
  __int64 v15; // r12
  unsigned int v16; // r13d
  __int64 v17; // rdi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r15
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rcx
  int v25; // edi
  __int64 v26; // rax
  unsigned int *v27; // r15
  unsigned int v28; // r12d
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v34; // rax
  __int64 *v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  __int64 *v41; // rbx
  __int64 *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 **v45; // rax
  __int64 v46; // rax
  ThreadRestrictNewHandlesRegion *v48; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v51; // [rsp+20h] [rbp-28h] BYREF
  int v52; // [rsp+28h] [rbp-20h]
  __int16 v53; // [rsp+2Ch] [rbp-1Ch]
  __int64 v54; // [rsp+30h] [rbp-18h]
  __int64 v55; // [rsp+90h] [rbp+48h] BYREF
  HDC v56; // [rsp+98h] [rbp+50h]
  __int64 v57; // [rsp+A0h] [rbp+58h]
  __int64 v58; // [rsp+A8h] [rbp+60h]

  v56 = a2;
  v2 = (unsigned int)a2;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  v4 = (_QWORD *)((char *)this + 32);
  v7 = *(_QWORD *)(W32GetSessionState(this) + 88);
  *((_QWORD *)this + 2) = v7;
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_OWORD *)this + 3) = 0;
  if ( this != (APIDCOBJ *)-32LL )
  {
    CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v6, v5, v7, v8);
    if ( CurrentThreadWin32Thread )
      v10 = *CurrentThreadWin32Thread;
    else
      v10 = 0;
    *((_QWORD *)this + 6) = (unsigned __int64)this & -(__int64)((APIDCOBJ *)((char *)this + 32) != 0);
    v11 = (v10 + 8) & -(__int64)(v10 != 0);
    *((_QWORD *)this + 7) = UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic;
    if ( v11 )
    {
      v12 = (_QWORD *)(v11 + 88);
      v13 = *(_QWORD *)(((v10 + 8) & -(__int64)(v10 != 0)) + 0x58);
      if ( *(_QWORD *)(v13 + 8) != v11 + 88 )
        goto LABEL_6;
      *v4 = v13;
      *((_QWORD *)this + 5) = v12;
      *(_QWORD *)(v13 + 8) = v4;
      *v12 = v4;
    }
    else
    {
      *((_QWORD *)this + 5) = (char *)this + 32;
      *v4 = v4;
    }
  }
  v53 = 0;
  v55 = 0;
  v14 = 0;
  v15 = *((_QWORD *)this + 2);
  v16 = (unsigned __int16)v2 | (v2 >> 8) & 0xFF0000;
  v58 = v15;
  v54 = v15;
  v17 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v55);
  if ( !(unsigned __int8)KeIsAttachedProcess(v20, v19)
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v17 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v21 = v17 + 8;
  v22 = -v17;
  v23 = v21 & -(__int64)(v22 != 0);
  if ( v23 )
  {
    v57 = *(_QWORD *)((v21 & -(__int64)(v22 != 0)) + 0x40);
    v15 = v58;
  }
  else
  {
    v57 = 0;
  }
  v24 = *(_QWORD *)(v15 + 8);
  v25 = 1;
  v52 = 1;
  v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 40LL))(v24, v16);
  v51 = (unsigned int *)v26;
  v27 = (unsigned int *)v26;
  if ( !v26 )
  {
    v25 = 0;
    KeLeaveCriticalRegion();
    goto LABEL_16;
  }
  _m_prefetchw((const void *)(v26 + 8));
  v28 = *(_DWORD *)(v26 + 8) & 0xFFFFFFFE;
  if ( v28 != (v55 & 0xFFFFFFFC) && v28 && (!v57 || v28 != (unsigned int)UMPDGetThreadClientPID(v23)) )
    goto LABEL_58;
  v15 = v58;
  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v58 + 8) + 96LL))(
                     *(_QWORD *)(v58 + 8),
                     *v27)
                 + 14)
      & 0x20) != 0
    && (!v23
     || (v48 = *(ThreadRestrictNewHandlesRegion **)(v23 + 328)) == 0
     || !*((_BYTE *)v48 + 80)
     || !ThreadRestrictNewHandlesRegion::InRegion(v48, v16)) )
  {
    LOBYTE(v53) = 1;
LABEL_58:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v51);
    v27 = v51;
    v25 = v52;
    v15 = v54;
  }
LABEL_16:
  if ( v25 )
  {
    if ( *((_BYTE *)v27 + 14) == 1 && *((_WORD *)v27 + 6) == WORD1(v56) )
    {
      CurrentThread = KeGetCurrentThread();
      v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v15 + 8) + 96LL))(*(_QWORD *)(v15 + 8), *v27);
      v14 = v34;
      if ( !*(_WORD *)(v34 + 12) || *(struct _KTHREAD **)(v34 + 16) == CurrentThread )
      {
        _InterlockedAdd16((volatile signed __int16 *)(v34 + 12), 1u);
        *(_QWORD *)(v34 + 16) = CurrentThread;
      }
      else
      {
        v14 = 0;
      }
    }
    v35 = *(__int64 **)(v15 + 8);
    v36 = *v35;
    v37 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v35 + 96))(v35, *v27);
    (*(void (__fastcall **)(__int64 *, __int64))(v36 + 48))(v35, v37);
    KeLeaveCriticalRegion();
  }
  *(_QWORD *)this = v14;
  if ( v14 )
  {
    if ( *(_DWORD *)(v14 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v14 + 12));
      *(_QWORD *)this = 0;
    }
  }
  else if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction() != 1
         && (unsigned __int8)PsIsWin32KFilterAuditEnabled() )
  {
    PsGetWin32KFilterSet();
  }
  if ( *(_QWORD *)this )
  {
    if ( (*(_DWORD *)(*(_QWORD *)this + 44LL) & 2) == 0 )
    {
      v38 = DCOBJ::SaveAttributesHelper(this);
      v30 = *(_QWORD *)this;
      if ( !v38 )
      {
        _InterlockedDecrement16((volatile signed __int16 *)(v30 + 12));
        *(_QWORD *)this = 0;
        goto LABEL_33;
      }
      *(_DWORD *)(v30 + 44) |= 2u;
      *((_DWORD *)this + 2) = 1;
    }
    v29 = *(_QWORD *)this;
    v30 = *(unsigned int *)(*(_QWORD *)this + 520LL);
    if ( (v30 & 4) != 0 )
    {
      v30 = (unsigned int)v30 & 0xFFFFFFFB;
      *(_DWORD *)(v29 + 520) = v30;
      v29 = *(_QWORD *)(v29 + 976);
      v39 = *(_DWORD *)(v29 + 340);
      if ( (v30 & 1) != 0 )
        v40 = v39 | 0x16090;
      else
        v40 = v39 | 0x6090;
      *(_DWORD *)(v29 + 340) = v40;
    }
  }
LABEL_33:
  v41 = (__int64 *)((char *)this + 64);
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  if ( this != (APIDCOBJ *)-64LL )
  {
    v42 = (__int64 *)PsGetCurrentThreadWin32Thread(v30, v29, v31, v32);
    if ( v42 )
      v43 = *v42;
    else
      v43 = 0;
    v44 = v43 + 8;
    *((_QWORD *)this + 10) = (unsigned __int64)this & -(__int64)((APIDCOBJ *)((char *)this + 64) != 0);
    v30 = -v43;
    v29 = v44 & -(__int64)(v30 != 0);
    *((_QWORD *)this + 11) = UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic;
    if ( v29 )
    {
      v45 = (__int64 **)(v29 + 88);
      v30 = *(_QWORD *)(v29 + 88);
      if ( *(_QWORD *)(v30 + 8) != v29 + 88 )
LABEL_6:
        __fastfail(3u);
      *v41 = v30;
      *((_QWORD *)this + 9) = v45;
      *(_QWORD *)(v30 + 8) = v41;
      *v45 = v41;
    }
    else
    {
      *((_QWORD *)this + 9) = (char *)this + 64;
      *v41 = (__int64)v41;
    }
  }
  v46 = *(_QWORD *)this;
  *((_BYTE *)this + 96) = 1;
  if ( v46 )
  {
    if ( *(_WORD *)(v46 + 12) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v30, v29, v31, v32);
    if ( *(_WORD *)(*(_QWORD *)this + 12LL) != 1 )
      DCOBJ::vUnlock(this);
  }
  return this;
}

```

## disassembly

```asm
0x140025268  mov     [rsp-40h+arg_8], rdx
0x14002526d  push    rbp
0x14002526e  push    rbx
0x14002526f  push    rsi
0x140025270  push    rdi
0x140025271  push    r12
0x140025273  push    r13
0x140025275  push    r14
0x140025277  push    r15
0x140025279  mov     rbp, rsp
0x14002527c  sub     rsp, 48h
0x140025280  xor     r12d, r12d
0x140025283  mov     r15, rdx
0x140025286  mov     [rcx], r12
0x140025289  mov     rsi, rcx
0x14002528c  mov     [rcx+8], r12d
0x140025290  call    cs:__imp_W32GetSessionState
0x140025297  nop     dword ptr [rax+rax+00h]
0x14002529c  lea     rbx, [rsi+20h]
0x1400252a0  xorps   xmm0, xmm0
0x1400252a3  mov     r8, [rax+58h]
0x1400252a7  mov     rax, rbx
0x1400252aa  neg     rax
0x1400252ad  mov     [rsi+10h], r8
0x1400252b1  mov     [rsi+18h], r12
0x1400252b5  sbb     rdi, rdi
0x1400252b8  mov     [rsi], r12
0x1400252bb  mov     [rsi+8], r12d
0x1400252bf  and     rdi, rsi
0x1400252c2  movups  xmmword ptr [rbx], xmm0
0x1400252c5  movups  xmmword ptr [rbx+10h], xmm0
0x1400252c9  test    rbx, rbx
0x1400252cc  jz      short loc_14002532A
0x1400252ce  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400252d5  nop     dword ptr [rax+rax+00h]
0x1400252da  test    rax, rax
0x1400252dd  jz      loc_140025682
0x1400252e3  mov     rcx, [rax]
0x1400252e6  lea     rax, [rcx+8]
0x1400252ea  mov     [rbx+10h], rdi
0x1400252ee  neg     rcx
0x1400252f1  sbb     rdx, rdx
0x1400252f4  and     rdx, rax
0x1400252f7  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VDRVOBJ@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400252fe  mov     [rbx+18h], rax
0x140025302  jz      loc_140025703
0x140025308  lea     rax, [rdx+58h]
0x14002530c  mov     rcx, [rax]
0x14002530f  cmp     [rcx+8], rax
0x140025313  jz      short loc_14002531C
0x140025315  mov     ecx, 3
0x14002531a  int     29h; Win8: RtlFailFast(ecx)
0x14002531c  mov     [rbx], rcx
0x14002531f  mov     [rbx+8], rax
0x140025323  mov     [rcx+8], rbx
0x140025327  mov     [rax], rbx
0x14002532a  movzx   eax, r15w
0x14002532e  lea     rcx, [rbp+arg_0]
0x140025332  xor     ebx, ebx
0x140025334  mov     [rbp+var_1C], r12w
0x140025339  mov     r13d, r15d
0x14002533c  mov     [rbp+arg_0], rbx
0x140025340  shr     r13d, 8
0x140025344  mov     r14, r12
0x140025347  mov     r12, [rsi+10h]
0x14002534b  and     r13d, 0FF0000h
0x140025352  or      r13d, eax
0x140025355  mov     [rbp+arg_18], r12
0x140025359  mov     [rbp+var_18], r12
0x14002535d  mov     edi, ebx
0x14002535f  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140025366  nop     dword ptr [rax+rax+00h]
0x14002536b  mov     r15, rax
0x14002536e  call    cs:__imp_KeIsAttachedProcess
0x140025375  nop     dword ptr [rax+rax+00h]
0x14002537a  test    al, al
0x14002537c  jnz     loc_140025692
0x140025382  test    r15, r15
0x140025385  jz      short loc_14002538A
0x140025387  mov     rdi, [r15]
0x14002538a  lea     rax, [rdi+8]
0x14002538e  neg     rdi
0x140025391  sbb     rbx, rbx
0x140025394  and     rbx, rax
0x140025397  jz      loc_1400256FA
0x14002539d  mov     r12, [rbx+40h]
0x1400253a1  mov     [rbp+arg_10], r12
0x1400253a5  mov     r12, [rbp+arg_18]
0x1400253a9  mov     rcx, [r12+8]
0x1400253ae  mov     edi, 1
0x1400253b3  mov     edx, r13d
0x1400253b6  mov     [rbp+var_20], edi
0x1400253b9  mov     rax, [rcx]
0x1400253bc  mov     rax, [rax+28h]
0x1400253c0  call    _guard_dispatch_icall
0x1400253c5  xor     ecx, ecx
0x1400253c7  mov     [rbp+var_28], rax
0x1400253cb  mov     r15, rax
0x1400253ce  test    rax, rax
0x1400253d1  jz      loc_14002560E
0x1400253d7  prefetchw byte ptr [rax+8]
0x1400253db  mov     r12d, [rax+8]
0x1400253df  mov     eax, dword ptr [rbp+arg_0]
0x1400253e2  and     r12d, 0FFFFFFFEh
0x1400253e6  and     eax, 0FFFFFFFCh
0x1400253e9  cmp     r12d, eax
0x1400253ec  jnz     loc_1400255EC
0x1400253f2  mov     r12, [rbp+arg_18]
0x1400253f6  mov     edx, [r15]
0x1400253f9  mov     rcx, [r12+8]
0x1400253fe  mov     rax, [rcx]
0x140025401  mov     rax, [rax+60h]
0x140025405  call    _guard_dispatch_icall
0x14002540a  test    byte ptr [rax+0Eh], 20h
0x14002540e  jnz     loc_14002563D
0x140025414  xor     r13d, r13d
0x140025417  test    edi, edi
0x140025419  jz      loc_1400254B0
0x14002541f  cmp     byte ptr [r15+0Eh], 1
0x140025424  jnz     short loc_14002547E
0x140025426  movzx   eax, byte ptr [r15+0Ch]
0x14002542b  movzx   ecx, byte ptr [r15+0Dh]
0x140025430  shl     cx, 8
0x140025434  or      cx, ax
0x140025437  mov     rax, [rbp+arg_8]
0x14002543b  shr     eax, 10h
0x14002543e  cmp     cx, ax
0x140025441  jnz     short loc_14002547E
0x140025443  mov     rbx, gs:188h
0x14002544c  mov     rcx, [r12+8]
0x140025451  mov     edx, [r15]
0x140025454  mov     rax, [rcx]
0x140025457  mov     rax, [rax+60h]
0x14002545b  call    _guard_dispatch_icall
0x140025460  mov     r14, rax
0x140025463  movzx   ecx, word ptr [rax+0Ch]
0x140025467  test    cx, cx
0x14002546a  jnz     loc_140025621
0x140025470  mov     ecx, 1
0x140025475  lock add [rax+0Ch], cx
0x14002547a  mov     [rax+10h], rbx
0x14002547e  mov     rdi, [r12+8]
0x140025483  mov     edx, [r15]
0x140025486  mov     rcx, rdi
0x140025489  mov     rbx, [rdi]
0x14002548c  mov     rax, [rbx+60h]
0x140025490  call    _guard_dispatch_icall
0x140025495  mov     rdx, rax
0x140025498  mov     rcx, rdi
0x14002549b  mov     rax, [rbx+30h]
0x14002549f  call    _guard_dispatch_icall
0x1400254a4  call    cs:__imp_KeLeaveCriticalRegion
0x1400254ab  nop     dword ptr [rax+rax+00h]
0x1400254b0  xor     r15d, r15d
0x1400254b3  mov     [rsi], r14
0x1400254b6  test    r14, r14
0x1400254b9  jz      loc_1400256C1
0x1400254bf  cmp     [r14+858h], r15d
0x1400254c6  jnz     loc_14002571B
0x1400254cc  mov     r14d, 1
0x1400254d2  mov     rax, [rsi]
0x1400254d5  test    rax, rax
0x1400254d8  jz      short loc_140025534
0x1400254da  mov     eax, [rax+2Ch]
0x1400254dd  test    al, 2
0x1400254df  jnz     short loc_1400254FC
0x1400254e1  mov     rcx, rsi; this
0x1400254e4  call    ?SaveAttributesHelper@DCOBJ@@AEAAHXZ; DCOBJ::SaveAttributesHelper(void)
0x1400254e9  mov     rcx, [rsi]
0x1400254ec  test    eax, eax
0x1400254ee  jz      loc_140025729
0x1400254f4  or      dword ptr [rcx+2Ch], 2
0x1400254f8  mov     [rsi+8], r14d
0x1400254fc  mov     rdx, [rsi]
0x1400254ff  mov     ecx, [rdx+208h]
0x140025505  test    cl, 4
0x140025508  jz      short loc_140025534
0x14002550a  and     ecx, 0FFFFFFFBh
0x14002550d  mov     [rdx+208h], ecx
0x140025513  mov     rdx, [rdx+3D0h]
0x14002551a  mov     eax, [rdx+154h]
0x140025520  test    r14b, cl
0x140025523  jz      loc_140025633
0x140025529  or      eax, 16090h
0x14002552e  mov     [rdx+154h], eax
0x140025534  lea     rbx, [rsi+40h]
0x140025538  xorps   xmm0, xmm0
0x14002553b  mov     rax, rbx
0x14002553e  neg     rax
0x140025541  movups  xmmword ptr [rbx], xmm0
0x140025544  sbb     rdi, rdi
0x140025547  and     rdi, rsi
0x14002554a  movups  xmmword ptr [rbx+10h], xmm0
0x14002554e  test    rbx, rbx
0x140025551  jz      short loc_1400255AC
0x140025553  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002555a  nop     dword ptr [rax+rax+00h]
0x14002555f  test    rax, rax
0x140025562  jz      loc_14002568A
0x140025568  mov     rcx, [rax]
0x14002556b  lea     rax, [rcx+8]
0x14002556f  mov     [rbx+10h], rdi
0x140025573  neg     rcx
0x140025576  sbb     rdx, rdx
0x140025579  and     rdx, rax
0x14002557c  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140025583  mov     [rbx+18h], rax
0x140025587  jz      loc_14002570F
0x14002558d  lea     rax, [rdx+58h]
0x140025591  mov     rcx, [rax]
0x140025594  cmp     [rcx+8], rax
0x140025598  jnz     loc_140025315
0x14002559e  mov     [rbx], rcx
0x1400255a1  mov     [rbx+8], rax
0x1400255a5  mov     [rcx+8], rbx
0x1400255a9  mov     [rax], rbx
0x1400255ac  mov     rax, [rsi]
0x1400255af  mov     [rsi+60h], r14b
0x1400255b3  test    rax, rax
0x1400255b6  jz      short loc_1400255D7
0x1400255b8  movzx   eax, word ptr [rax+0Ch]
0x1400255bc  cmp     ax, r14w
0x1400255c0  jnz     loc_140025736
0x1400255c6  mov     rax, [rsi]
0x1400255c9  movzx   ecx, word ptr [rax+0Ch]
0x1400255cd  cmp     cx, r14w
0x1400255d1  jnz     loc_140025740
0x1400255d7  mov     rax, rsi
0x1400255da  add     rsp, 48h
0x1400255de  pop     r15
0x1400255e0  pop     r14
0x1400255e2  pop     r13
0x1400255e4  pop     r12
0x1400255e6  pop     rdi
0x1400255e7  pop     rsi
0x1400255e8  pop     rbx
0x1400255e9  pop     rbp
0x1400255ea  retn
0x1400255ec  test    r12d, r12d
0x1400255ef  jz      loc_1400253F2
0x1400255f5  cmp     [rbp+arg_10], rcx
0x1400255f9  jz      short loc_140025669
0x1400255fb  mov     rcx, rbx
0x1400255fe  call    UMPDGetThreadClientPID
0x140025603  cmp     r12d, eax
0x140025606  jz      loc_1400253F2
0x14002560c  jmp     short loc_140025669
0x14002560e  mov     edi, ecx
0x140025610  call    cs:__imp_KeLeaveCriticalRegion
0x140025617  nop     dword ptr [rax+rax+00h]
0x14002561c  jmp     loc_140025414
0x140025621  cmp     [rax+10h], rbx
0x140025625  jz      loc_140025470
0x14002562b  mov     r14, r13
0x14002562e  jmp     loc_14002547E
0x140025633  or      eax, 6090h
0x140025638  jmp     loc_14002552E
0x14002563d  xor     eax, eax
0x14002563f  test    rbx, rbx
0x140025642  jz      short loc_140025665
0x140025644  mov     rcx, [rbx+148h]; this
0x14002564b  test    rcx, rcx
0x14002564e  jz      short loc_140025665
0x140025650  cmp     [rcx+50h], al
0x140025653  jz      short loc_140025665
0x140025655  mov     edx, r13d; unsigned int
0x140025658  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14002565d  test    al, al
0x14002565f  jnz     loc_140025414
0x140025665  mov     byte ptr [rbp+var_1C], dil
0x140025669  lea     rcx, [rbp+var_28]; this
0x14002566d  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140025672  mov     r15, [rbp+var_28]
0x140025676  mov     edi, [rbp+var_20]
0x140025679  mov     r12, [rbp+var_18]
0x14002567d  jmp     loc_140025414
0x140025682  mov     rcx, r12
0x140025685  jmp     loc_1400252E6
0x14002568a  mov     rcx, r15
0x14002568d  jmp     loc_14002556B
0x140025692  call    W32GetCurrentWin32kSessionId
0x140025697  mov     ebx, eax
0x140025699  call    cs:__imp_PsGetCurrentThreadProcess
0x1400256a0  nop     dword ptr [rax+rax+00h]
0x1400256a5  mov     rcx, rax
0x1400256a8  call    cs:__imp_PsGetProcessSessionIdEx
0x1400256af  nop     dword ptr [rax+rax+00h]
0x1400256b4  cmp     ebx, eax
0x1400256b6  jz      loc_140025382
0x1400256bc  jmp     loc_14002538A
0x1400256c1  call    ?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x1400256c6  mov     r14d, 1
0x1400256cc  cmp     eax, r14d
0x1400256cf  jz      loc_1400254D2
0x1400256d5  call    cs:__imp_PsIsWin32KFilterAuditEnabled
0x1400256dc  nop     dword ptr [rax+rax+00h]
0x1400256e1  test    al, al
0x1400256e3  jz      loc_1400254D2
0x1400256e9  call    cs:__imp_PsGetWin32KFilterSet
0x1400256f0  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
