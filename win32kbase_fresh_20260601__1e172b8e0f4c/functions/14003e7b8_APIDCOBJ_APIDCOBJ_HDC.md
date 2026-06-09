# APIDCOBJ::APIDCOBJ(HDC__ *)

- ea: `0x14003e7b8`
- end: `0x14003ec9d`
- name: `??0APIDCOBJ@@QEAA@PEAUHDC__@@@Z`
- size: `1253`
- prototype: `APIDCOBJ *__fastcall(APIDCOBJ *__hidden this, HDC)`
- caller_count: `17`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008020`
- `0x1400096d0`
- `0x1400098f0`
- `0x14000f760`
- `0x140014ea0`
- `0x1400223f0`
- `0x1400297a0`
- `0x14002cef0`
- `0x1400934e0`
- `0x1400ae0b4`
- `0x1400af7a0`
- `0x1400b0ba0`
- `0x14012f160`
- `0x140145850`
- `0x140160a80`
- `0x140181b20`
- `0x1401e68c8`

## callees

- `0x140006cf8`
- `0x140008160`
- `0x14001d250`
- `0x140028974`
- `0x14003bf24`
- `0x14003c694`
- `0x14003e7b8`
- `0x14003f0fc`
- `0x14010f2b0`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e9f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003eb60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e9f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003eb60`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003ebf8`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003ebf8`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14003ec39`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14003ec39`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003ebe9`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003ebe9`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003e8be`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003e8be`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14003ec25`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14003ec25`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003e8af`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003e8af`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003e81e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003eaa3`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003e81e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003eaa3`
- `WIN32K!W32GetSessionState` at `0x14003e7e0`
- `WIN32K!W32GetSessionState` at `0x14003e7e0`

## pseudocode

```c
APIDCOBJ *__fastcall APIDCOBJ::APIDCOBJ(APIDCOBJ *this, HDC a2)
{
  unsigned int v2; // r15d
  _QWORD *v4; // rbx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r14
  __int64 v11; // r12
  unsigned int v12; // r13d
  __int64 v13; // rdi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r15
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rcx
  int v19; // edi
  __int64 v20; // rax
  unsigned int *v21; // r15
  unsigned int v22; // r12d
  __int64 v23; // rdx
  __int64 v24; // rcx
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v26; // rax
  __int64 *v27; // rdi
  __int64 v28; // rbx
  __int64 v29; // rax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  __int64 *v33; // rbx
  __int64 *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 **v37; // rax
  __int64 v38; // rax
  ThreadRestrictNewHandlesRegion *v40; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v43; // [rsp+20h] [rbp-28h] BYREF
  int v44; // [rsp+28h] [rbp-20h]
  __int16 v45; // [rsp+2Ch] [rbp-1Ch]
  __int64 v46; // [rsp+30h] [rbp-18h]
  __int64 v47; // [rsp+90h] [rbp+48h] BYREF
  HDC v48; // [rsp+98h] [rbp+50h]
  __int64 v49; // [rsp+A0h] [rbp+58h]
  __int64 v50; // [rsp+A8h] [rbp+60h]

  v48 = a2;
  v2 = (unsigned int)a2;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  v4 = (_QWORD *)((char *)this + 32);
  *((_QWORD *)this + 2) = *(_QWORD *)(W32GetSessionState(this) + 88);
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_OWORD *)this + 3) = 0;
  if ( this != (APIDCOBJ *)-32LL )
  {
    CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
    if ( CurrentThreadWin32Thread )
      v6 = *CurrentThreadWin32Thread;
    else
      v6 = 0;
    *((_QWORD *)this + 6) = (unsigned __int64)this & -(__int64)((APIDCOBJ *)((char *)this + 32) != 0);
    v7 = (v6 + 8) & -(__int64)(v6 != 0);
    *((_QWORD *)this + 7) = UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic;
    if ( v7 )
    {
      v8 = (_QWORD *)(v7 + 88);
      v9 = *(_QWORD *)(((v6 + 8) & -(__int64)(v6 != 0)) + 0x58);
      if ( *(_QWORD *)(v9 + 8) != v7 + 88 )
        goto LABEL_6;
      *v4 = v9;
      *((_QWORD *)this + 5) = v8;
      *(_QWORD *)(v9 + 8) = v4;
      *v8 = v4;
    }
    else
    {
      *((_QWORD *)this + 5) = (char *)this + 32;
      *v4 = v4;
    }
  }
  v45 = 0;
  v47 = 0;
  v10 = 0;
  v11 = *((_QWORD *)this + 2);
  v12 = (unsigned __int16)v2 | (v2 >> 8) & 0xFF0000;
  v50 = v11;
  v46 = v11;
  v13 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v47);
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v13 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v15 = v13 + 8;
  v16 = -v13;
  v17 = v15 & -(__int64)(v16 != 0);
  if ( v17 )
  {
    v49 = *(_QWORD *)((v15 & -(__int64)(v16 != 0)) + 0x40);
    v11 = v50;
  }
  else
  {
    v49 = 0;
  }
  v18 = *(_QWORD *)(v11 + 8);
  v19 = 1;
  v44 = 1;
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 40LL))(v18, v12);
  v43 = (unsigned int *)v20;
  v21 = (unsigned int *)v20;
  if ( !v20 )
  {
    v19 = 0;
    KeLeaveCriticalRegion();
    goto LABEL_16;
  }
  _m_prefetchw((const void *)(v20 + 8));
  v22 = *(_DWORD *)(v20 + 8) & 0xFFFFFFFE;
  if ( v22 != (v47 & 0xFFFFFFFC) && v22 && (!v49 || v22 != (unsigned int)UMPDGetThreadClientPID(v17)) )
    goto LABEL_58;
  v11 = v50;
  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v50 + 8) + 96LL))(
                     *(_QWORD *)(v50 + 8),
                     *v21)
                 + 14)
      & 0x20) != 0
    && (!v17
     || (v40 = *(ThreadRestrictNewHandlesRegion **)(v17 + 328)) == 0
     || !*((_BYTE *)v40 + 80)
     || !ThreadRestrictNewHandlesRegion::InRegion(v40, v12)) )
  {
    LOBYTE(v45) = 1;
LABEL_58:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v43);
    v21 = v43;
    v19 = v44;
    v11 = v46;
  }
LABEL_16:
  if ( v19 )
  {
    if ( *((_BYTE *)v21 + 14) == 1 && *((_WORD *)v21 + 6) == WORD1(v48) )
    {
      CurrentThread = KeGetCurrentThread();
      v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v11 + 8) + 96LL))(*(_QWORD *)(v11 + 8), *v21);
      v10 = v26;
      if ( !*(_WORD *)(v26 + 12) || *(struct _KTHREAD **)(v26 + 16) == CurrentThread )
      {
        _InterlockedAdd16((volatile signed __int16 *)(v26 + 12), 1u);
        *(_QWORD *)(v26 + 16) = CurrentThread;
      }
      else
      {
        v10 = 0;
      }
    }
    v27 = *(__int64 **)(v11 + 8);
    v28 = *v27;
    v29 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v27 + 96))(v27, *v21);
    (*(void (__fastcall **)(__int64 *, __int64))(v28 + 48))(v27, v29);
    KeLeaveCriticalRegion();
  }
  *(_QWORD *)this = v10;
  if ( v10 )
  {
    if ( *(_DWORD *)(v10 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v10 + 12));
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
      v30 = DCOBJ::SaveAttributesHelper(this);
      v24 = *(_QWORD *)this;
      if ( !v30 )
      {
        _InterlockedDecrement16((volatile signed __int16 *)(v24 + 12));
        *(_QWORD *)this = 0;
        goto LABEL_33;
      }
      *(_DWORD *)(v24 + 44) |= 2u;
      *((_DWORD *)this + 2) = 1;
    }
    v23 = *(_QWORD *)this;
    v24 = *(unsigned int *)(*(_QWORD *)this + 520LL);
    if ( (v24 & 4) != 0 )
    {
      v24 = (unsigned int)v24 & 0xFFFFFFFB;
      *(_DWORD *)(v23 + 520) = v24;
      v23 = *(_QWORD *)(v23 + 976);
      v31 = *(_DWORD *)(v23 + 340);
      if ( (v24 & 1) != 0 )
        v32 = v31 | 0x16090;
      else
        v32 = v31 | 0x6090;
      *(_DWORD *)(v23 + 340) = v32;
    }
  }
LABEL_33:
  v33 = (__int64 *)((char *)this + 64);
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  if ( this != (APIDCOBJ *)-64LL )
  {
    v34 = (__int64 *)PsGetCurrentThreadWin32Thread();
    if ( v34 )
      v35 = *v34;
    else
      v35 = 0;
    v36 = v35 + 8;
    *((_QWORD *)this + 10) = (unsigned __int64)this & -(__int64)((APIDCOBJ *)((char *)this + 64) != 0);
    v24 = -v35;
    v23 = v36 & -(__int64)(v24 != 0);
    *((_QWORD *)this + 11) = UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic;
    if ( v23 )
    {
      v37 = (__int64 **)(v23 + 88);
      v24 = *(_QWORD *)(v23 + 88);
      if ( *(_QWORD *)(v24 + 8) != v23 + 88 )
LABEL_6:
        __fastfail(3u);
      *v33 = v24;
      *((_QWORD *)this + 9) = v37;
      *(_QWORD *)(v24 + 8) = v33;
      *v37 = v33;
    }
    else
    {
      *((_QWORD *)this + 9) = (char *)this + 64;
      *v33 = (__int64)v33;
    }
  }
  v38 = *(_QWORD *)this;
  *((_BYTE *)this + 96) = 1;
  if ( v38 )
  {
    if ( *(_WORD *)(v38 + 12) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v24, v23);
    if ( *(_WORD *)(*(_QWORD *)this + 12LL) != 1 )
      DCOBJ::vUnlock(this);
  }
  return this;
}

```

## disassembly

```asm
0x14003e7b8  mov     [rsp-40h+arg_8], rdx
0x14003e7bd  push    rbp
0x14003e7be  push    rbx
0x14003e7bf  push    rsi
0x14003e7c0  push    rdi
0x14003e7c1  push    r12
0x14003e7c3  push    r13
0x14003e7c5  push    r14
0x14003e7c7  push    r15
0x14003e7c9  mov     rbp, rsp
0x14003e7cc  sub     rsp, 48h
0x14003e7d0  xor     r12d, r12d
0x14003e7d3  mov     r15, rdx
0x14003e7d6  mov     [rcx], r12
0x14003e7d9  mov     rsi, rcx
0x14003e7dc  mov     [rcx+8], r12d
0x14003e7e0  call    cs:__imp_W32GetSessionState
0x14003e7e7  nop     dword ptr [rax+rax+00h]
0x14003e7ec  lea     rbx, [rsi+20h]
0x14003e7f0  xorps   xmm0, xmm0
0x14003e7f3  mov     r8, [rax+58h]
0x14003e7f7  mov     rax, rbx
0x14003e7fa  neg     rax
0x14003e7fd  mov     [rsi+10h], r8
0x14003e801  mov     [rsi+18h], r12
0x14003e805  sbb     rdi, rdi
0x14003e808  mov     [rsi], r12
0x14003e80b  mov     [rsi+8], r12d
0x14003e80f  and     rdi, rsi
0x14003e812  movups  xmmword ptr [rbx], xmm0
0x14003e815  movups  xmmword ptr [rbx+10h], xmm0
0x14003e819  test    rbx, rbx
0x14003e81c  jz      short loc_14003E87A
0x14003e81e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14003e825  nop     dword ptr [rax+rax+00h]
0x14003e82a  test    rax, rax
0x14003e82d  jz      loc_14003EBD2
0x14003e833  mov     rcx, [rax]
0x14003e836  lea     rax, [rcx+8]
0x14003e83a  mov     [rbx+10h], rdi
0x14003e83e  neg     rcx
0x14003e841  sbb     rdx, rdx
0x14003e844  and     rdx, rax
0x14003e847  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VDRVOBJ@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic(void *)
0x14003e84e  mov     [rbx+18h], rax
0x14003e852  jz      loc_14003EC53
0x14003e858  lea     rax, [rdx+58h]
0x14003e85c  mov     rcx, [rax]
0x14003e85f  cmp     [rcx+8], rax
0x14003e863  jz      short loc_14003E86C
0x14003e865  mov     ecx, 3
0x14003e86a  int     29h; Win8: RtlFailFast(ecx)
0x14003e86c  mov     [rbx], rcx
0x14003e86f  mov     [rbx+8], rax
0x14003e873  mov     [rcx+8], rbx
0x14003e877  mov     [rax], rbx
0x14003e87a  movzx   eax, r15w
0x14003e87e  lea     rcx, [rbp+arg_0]
0x14003e882  xor     ebx, ebx
0x14003e884  mov     [rbp+var_1C], r12w
0x14003e889  mov     r13d, r15d
0x14003e88c  mov     [rbp+arg_0], rbx
0x14003e890  shr     r13d, 8
0x14003e894  mov     r14, r12
0x14003e897  mov     r12, [rsi+10h]
0x14003e89b  and     r13d, 0FF0000h
0x14003e8a2  or      r13d, eax
0x14003e8a5  mov     [rbp+arg_18], r12
0x14003e8a9  mov     [rbp+var_18], r12
0x14003e8ad  mov     edi, ebx
0x14003e8af  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14003e8b6  nop     dword ptr [rax+rax+00h]
0x14003e8bb  mov     r15, rax
0x14003e8be  call    cs:__imp_KeIsAttachedProcess
0x14003e8c5  nop     dword ptr [rax+rax+00h]
0x14003e8ca  test    al, al
0x14003e8cc  jnz     loc_14003EBE2
0x14003e8d2  test    r15, r15
0x14003e8d5  jz      short loc_14003E8DA
0x14003e8d7  mov     rdi, [r15]
0x14003e8da  lea     rax, [rdi+8]
0x14003e8de  neg     rdi
0x14003e8e1  sbb     rbx, rbx
0x14003e8e4  and     rbx, rax
0x14003e8e7  jz      loc_14003EC4A
0x14003e8ed  mov     r12, [rbx+40h]
0x14003e8f1  mov     [rbp+arg_10], r12
0x14003e8f5  mov     r12, [rbp+arg_18]
0x14003e8f9  mov     rcx, [r12+8]
0x14003e8fe  mov     edi, 1
0x14003e903  mov     edx, r13d
0x14003e906  mov     [rbp+var_20], edi
0x14003e909  mov     rax, [rcx]
0x14003e90c  mov     rax, [rax+28h]
0x14003e910  call    _guard_dispatch_icall
0x14003e915  xor     ecx, ecx
0x14003e917  mov     [rbp+var_28], rax
0x14003e91b  mov     r15, rax
0x14003e91e  test    rax, rax
0x14003e921  jz      loc_14003EB5E
0x14003e927  prefetchw byte ptr [rax+8]
0x14003e92b  mov     r12d, [rax+8]
0x14003e92f  mov     eax, dword ptr [rbp+arg_0]
0x14003e932  and     r12d, 0FFFFFFFEh
0x14003e936  and     eax, 0FFFFFFFCh
0x14003e939  cmp     r12d, eax
0x14003e93c  jnz     loc_14003EB3C
0x14003e942  mov     r12, [rbp+arg_18]
0x14003e946  mov     edx, [r15]
0x14003e949  mov     rcx, [r12+8]
0x14003e94e  mov     rax, [rcx]
0x14003e951  mov     rax, [rax+60h]
0x14003e955  call    _guard_dispatch_icall
0x14003e95a  test    byte ptr [rax+0Eh], 20h
0x14003e95e  jnz     loc_14003EB8D
0x14003e964  xor     r13d, r13d
0x14003e967  test    edi, edi
0x14003e969  jz      loc_14003EA00
0x14003e96f  cmp     byte ptr [r15+0Eh], 1
0x14003e974  jnz     short loc_14003E9CE
0x14003e976  movzx   eax, byte ptr [r15+0Ch]
0x14003e97b  movzx   ecx, byte ptr [r15+0Dh]
0x14003e980  shl     cx, 8
0x14003e984  or      cx, ax
0x14003e987  mov     rax, [rbp+arg_8]
0x14003e98b  shr     eax, 10h
0x14003e98e  cmp     cx, ax
0x14003e991  jnz     short loc_14003E9CE
0x14003e993  mov     rbx, gs:188h
0x14003e99c  mov     rcx, [r12+8]
0x14003e9a1  mov     edx, [r15]
0x14003e9a4  mov     rax, [rcx]
0x14003e9a7  mov     rax, [rax+60h]
0x14003e9ab  call    _guard_dispatch_icall
0x14003e9b0  mov     r14, rax
0x14003e9b3  movzx   ecx, word ptr [rax+0Ch]
0x14003e9b7  test    cx, cx
0x14003e9ba  jnz     loc_14003EB71
0x14003e9c0  mov     ecx, 1
0x14003e9c5  lock add [rax+0Ch], cx
0x14003e9ca  mov     [rax+10h], rbx
0x14003e9ce  mov     rdi, [r12+8]
0x14003e9d3  mov     edx, [r15]
0x14003e9d6  mov     rcx, rdi
0x14003e9d9  mov     rbx, [rdi]
0x14003e9dc  mov     rax, [rbx+60h]
0x14003e9e0  call    _guard_dispatch_icall
0x14003e9e5  mov     rdx, rax
0x14003e9e8  mov     rcx, rdi
0x14003e9eb  mov     rax, [rbx+30h]
0x14003e9ef  call    _guard_dispatch_icall
0x14003e9f4  call    cs:__imp_KeLeaveCriticalRegion
0x14003e9fb  nop     dword ptr [rax+rax+00h]
0x14003ea00  xor     r15d, r15d
0x14003ea03  mov     [rsi], r14
0x14003ea06  test    r14, r14
0x14003ea09  jz      loc_14003EC11
0x14003ea0f  cmp     [r14+858h], r15d
0x14003ea16  jnz     loc_14003EC6B
0x14003ea1c  mov     r14d, 1
0x14003ea22  mov     rax, [rsi]
0x14003ea25  test    rax, rax
0x14003ea28  jz      short loc_14003EA84
0x14003ea2a  mov     eax, [rax+2Ch]
0x14003ea2d  test    al, 2
0x14003ea2f  jnz     short loc_14003EA4C
0x14003ea31  mov     rcx, rsi; this
0x14003ea34  call    ?SaveAttributesHelper@DCOBJ@@AEAAHXZ; DCOBJ::SaveAttributesHelper(void)
0x14003ea39  mov     rcx, [rsi]
0x14003ea3c  test    eax, eax
0x14003ea3e  jz      loc_14003EC79
0x14003ea44  or      dword ptr [rcx+2Ch], 2
0x14003ea48  mov     [rsi+8], r14d
0x14003ea4c  mov     rdx, [rsi]
0x14003ea4f  mov     ecx, [rdx+208h]
0x14003ea55  test    cl, 4
0x14003ea58  jz      short loc_14003EA84
0x14003ea5a  and     ecx, 0FFFFFFFBh
0x14003ea5d  mov     [rdx+208h], ecx
0x14003ea63  mov     rdx, [rdx+3D0h]
0x14003ea6a  mov     eax, [rdx+154h]
0x14003ea70  test    r14b, cl
0x14003ea73  jz      loc_14003EB83
0x14003ea79  or      eax, 16090h
0x14003ea7e  mov     [rdx+154h], eax
0x14003ea84  lea     rbx, [rsi+40h]
0x14003ea88  xorps   xmm0, xmm0
0x14003ea8b  mov     rax, rbx
0x14003ea8e  neg     rax
0x14003ea91  movups  xmmword ptr [rbx], xmm0
0x14003ea94  sbb     rdi, rdi
0x14003ea97  and     rdi, rsi
0x14003ea9a  movups  xmmword ptr [rbx+10h], xmm0
0x14003ea9e  test    rbx, rbx
0x14003eaa1  jz      short loc_14003EAFC
0x14003eaa3  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14003eaaa  nop     dword ptr [rax+rax+00h]
0x14003eaaf  test    rax, rax
0x14003eab2  jz      loc_14003EBDA
0x14003eab8  mov     rcx, [rax]
0x14003eabb  lea     rax, [rcx+8]
0x14003eabf  mov     [rbx+10h], rdi
0x14003eac3  neg     rcx
0x14003eac6  sbb     rdx, rdx
0x14003eac9  and     rdx, rax
0x14003eacc  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14003ead3  mov     [rbx+18h], rax
0x14003ead7  jz      loc_14003EC5F
0x14003eadd  lea     rax, [rdx+58h]
0x14003eae1  mov     rcx, [rax]
0x14003eae4  cmp     [rcx+8], rax
0x14003eae8  jnz     loc_14003E865
0x14003eaee  mov     [rbx], rcx
0x14003eaf1  mov     [rbx+8], rax
0x14003eaf5  mov     [rcx+8], rbx
0x14003eaf9  mov     [rax], rbx
0x14003eafc  mov     rax, [rsi]
0x14003eaff  mov     [rsi+60h], r14b
0x14003eb03  test    rax, rax
0x14003eb06  jz      short loc_14003EB27
0x14003eb08  movzx   eax, word ptr [rax+0Ch]
0x14003eb0c  cmp     ax, r14w
0x14003eb10  jnz     loc_14003EC86
0x14003eb16  mov     rax, [rsi]
0x14003eb19  movzx   ecx, word ptr [rax+0Ch]
0x14003eb1d  cmp     cx, r14w
0x14003eb21  jnz     loc_14003EC90
0x14003eb27  mov     rax, rsi
0x14003eb2a  add     rsp, 48h
0x14003eb2e  pop     r15
0x14003eb30  pop     r14
0x14003eb32  pop     r13
0x14003eb34  pop     r12
0x14003eb36  pop     rdi
0x14003eb37  pop     rsi
0x14003eb38  pop     rbx
0x14003eb39  pop     rbp
0x14003eb3a  retn
0x14003eb3c  test    r12d, r12d
0x14003eb3f  jz      loc_14003E942
0x14003eb45  cmp     [rbp+arg_10], rcx
0x14003eb49  jz      short loc_14003EBB9
0x14003eb4b  mov     rcx, rbx
0x14003eb4e  call    UMPDGetThreadClientPID
0x14003eb53  cmp     r12d, eax
0x14003eb56  jz      loc_14003E942
0x14003eb5c  jmp     short loc_14003EBB9
0x14003eb5e  mov     edi, ecx
0x14003eb60  call    cs:__imp_KeLeaveCriticalRegion
0x14003eb67  nop     dword ptr [rax+rax+00h]
0x14003eb6c  jmp     loc_14003E964
0x14003eb71  cmp     [rax+10h], rbx
0x14003eb75  jz      loc_14003E9C0
0x14003eb7b  mov     r14, r13
0x14003eb7e  jmp     loc_14003E9CE
0x14003eb83  or      eax, 6090h
0x14003eb88  jmp     loc_14003EA7E
0x14003eb8d  xor     eax, eax
0x14003eb8f  test    rbx, rbx
0x14003eb92  jz      short loc_14003EBB5
0x14003eb94  mov     rcx, [rbx+148h]; this
0x14003eb9b  test    rcx, rcx
0x14003eb9e  jz      short loc_14003EBB5
0x14003eba0  cmp     [rcx+50h], al
0x14003eba3  jz      short loc_14003EBB5
0x14003eba5  mov     edx, r13d; unsigned int
0x14003eba8  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14003ebad  test    al, al
0x14003ebaf  jnz     loc_14003E964
0x14003ebb5  mov     byte ptr [rbp+var_1C], dil
0x14003ebb9  lea     rcx, [rbp+var_28]; this
0x14003ebbd  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14003ebc2  mov     r15, [rbp+var_28]
0x14003ebc6  mov     edi, [rbp+var_20]
0x14003ebc9  mov     r12, [rbp+var_18]
0x14003ebcd  jmp     loc_14003E964
0x14003ebd2  mov     rcx, r12
0x14003ebd5  jmp     loc_14003E836
0x14003ebda  mov     rcx, r15
0x14003ebdd  jmp     loc_14003EABB
0x14003ebe2  call    W32GetCurrentWin32kSessionId
0x14003ebe7  mov     ebx, eax
0x14003ebe9  call    cs:__imp_PsGetCurrentThreadProcess
0x14003ebf0  nop     dword ptr [rax+rax+00h]
0x14003ebf5  mov     rcx, rax
0x14003ebf8  call    cs:__imp_PsGetProcessSessionIdEx
0x14003ebff  nop     dword ptr [rax+rax+00h]
0x14003ec04  cmp     ebx, eax
0x14003ec06  jz      loc_14003E8D2
0x14003ec0c  jmp     loc_14003E8DA
0x14003ec11  call    ?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14003ec16  mov     r14d, 1
0x14003ec1c  cmp     eax, r14d
0x14003ec1f  jz      loc_14003EA22
0x14003ec25  call    cs:__imp_PsIsWin32KFilterAuditEnabled
0x14003ec2c  nop     dword ptr [rax+rax+00h]
0x14003ec31  test    al, al
0x14003ec33  jz      loc_14003EA22
0x14003ec39  call    cs:__imp_PsGetWin32KFilterSet
0x14003ec40  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
