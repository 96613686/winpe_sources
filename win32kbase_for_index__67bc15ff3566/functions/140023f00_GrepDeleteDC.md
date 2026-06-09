# GrepDeleteDC

- ea: `0x140023f00`
- end: `0x140024572`
- name: `GrepDeleteDC`
- size: `1650`
- prototype: `__int64 __fastcall(HDC, unsigned int)`
- caller_count: `8`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140012210`
- `0x140015860`
- `0x140018870`
- `0x1400222d0`
- `0x140037420`
- `0x14003db48`
- `0x140113350`
- `0x140187424`

## callees

- `0x14001e034`
- `0x14002307c`
- `0x140023344`
- `0x140023b54`
- `0x140023f00`
- `0x140025d20`
- `0x14002bed0`
- `0x14002f850`
- `0x140036f70`
- `0x1400371c0`
- `0x1400782b0`
- `0x1400782e4`
- `0x140079330`
- `0x14007a8c0`
- `0x140120e30`
- `0x14012e228`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024232`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024421`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024232`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024421`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140023fcb`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140023fcb`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140024273`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140024273`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400244e1`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400244e1`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140024541`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140024541`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400244d2`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400244d2`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400240ff`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400240ff`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14002450a`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14002450a`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400240f0`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400240f0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140023f53`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140023f53`
- `WIN32K!W32GetSessionState` at `0x140023f25`
- `WIN32K!W32GetSessionState` at `0x140023f25`

## pseudocode

```c
_BOOL8 __fastcall GrepDeleteDC(HDC a1, unsigned int a2)
{
  HDC v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *CurrentProcessWin32Process; // rax
  DC *v14; // rsi
  char v15; // bl
  DC *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  struct Gre::Base::SESSION_GLOBALS *v20; // r13
  unsigned int v21; // r12d
  __int64 v22; // rdi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r14
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdi
  __int64 v28; // rbx
  int v29; // edi
  __int64 v30; // rax
  unsigned int *v31; // r14
  unsigned int v32; // r13d
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v34; // rax
  __int64 *v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rax
  unsigned int CurrentProcessId; // eax
  DC *v39; // rdx
  unsigned int v40; // ebx
  char *v41; // rax
  struct _ENTRY *v42; // rax
  struct _DC_ATTR *v43; // rax
  __int64 v44; // rdx
  int v45; // ecx
  int v46; // ecx
  DC *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rcx
  ThreadRestrictNewHandlesRegion *v50; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  struct Gre::Base::SESSION_GLOBALS *v53; // [rsp+20h] [rbp-60h]
  unsigned int *v54; // [rsp+28h] [rbp-58h] BYREF
  int v55; // [rsp+30h] [rbp-50h]
  __int16 v56; // [rsp+34h] [rbp-4Ch]
  struct Gre::Base::SESSION_GLOBALS *v57; // [rsp+38h] [rbp-48h]
  DC *v58; // [rsp+40h] [rbp-40h] BYREF
  int v59; // [rsp+48h] [rbp-38h]
  struct Gre::Base::SESSION_GLOBALS *v60; // [rsp+50h] [rbp-30h]
  __int64 v61; // [rsp+58h] [rbp-28h]
  __int128 v62; // [rsp+60h] [rbp-20h] BYREF
  __int128 v63; // [rsp+70h] [rbp-10h]
  __int64 v65; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v66; // [rsp+D8h] [rbp+58h]

  v3 = a1;
  v4 = *(_QWORD *)(W32GetSessionState(a1) + 88);
  v60 = (struct Gre::Base::SESSION_GLOBALS *)v4;
  v61 = 0;
  v58 = 0;
  v59 = 0;
  v62 = 0;
  v63 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v6, v5, v7, v8);
  if ( CurrentThreadWin32Thread )
    v10 = *CurrentThreadWin32Thread;
  else
    v10 = 0;
  v11 = (v10 + 8) & -(__int64)(v10 != 0);
  *(_QWORD *)&v63 = &v58;
  *((_QWORD *)&v63 + 1) = UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic;
  if ( v11 )
  {
    v12 = *(_QWORD *)(((v10 + 8) & -(__int64)(v10 != 0)) + 0x58);
    if ( *(_QWORD *)(v12 + 8) != v11 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v62 = *(_QWORD *)(v11 + 88);
    *((_QWORD *)&v62 + 1) = v11 + 88;
    *(_QWORD *)(v12 + 8) = &v62;
    *(_QWORD *)(v11 + 88) = &v62;
  }
  else
  {
    *((_QWORD *)&v62 + 1) = &v62;
    *(_QWORD *)&v62 = &v62;
  }
  if ( *(_DWORD *)(v4 + 3112)
    || (CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process()) == 0
    || !*CurrentProcessWin32Process )
  {
    DCOBJ::vLockIgnoreAttributes((DCOBJ *)&v58, v3);
LABEL_11:
    v14 = v58;
    goto LABEL_12;
  }
  v20 = v60;
  v14 = 0;
  v56 = 0;
  v21 = (unsigned __int16)v3 | ((unsigned int)v3 >> 8) & 0xFF0000;
  v53 = v60;
  v57 = v60;
  v22 = 0;
  v65 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v65);
  if ( !(unsigned __int8)KeIsAttachedProcess(v25, v24)
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v22 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v26 = v22 + 8;
  v27 = -v22;
  v28 = v26 & -(__int64)(v27 != 0);
  if ( v28 )
  {
    v66 = *(_QWORD *)((v26 & -(__int64)(v27 != 0)) + 0x40);
    v20 = v53;
  }
  else
  {
    v66 = 0;
  }
  v29 = 1;
  v55 = 1;
  v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v20 + 1) + 40LL))(*((_QWORD *)v20 + 1), v21);
  v54 = (unsigned int *)v30;
  v31 = (unsigned int *)v30;
  if ( !v30 )
  {
    v29 = 0;
    KeLeaveCriticalRegion();
    goto LABEL_34;
  }
  _m_prefetchw((const void *)(v30 + 8));
  v32 = *(_DWORD *)(v30 + 8) & 0xFFFFFFFE;
  if ( v32 != (v65 & 0xFFFFFFFC) && v32 && (!v66 || v32 != (unsigned int)UMPDGetThreadClientPID(v28)) )
    goto LABEL_82;
  v20 = v53;
  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v53 + 1) + 96LL))(
                     *((_QWORD *)v53 + 1),
                     *v31)
                 + 14)
      & 0x20) != 0
    && (!v28
     || (v50 = *(ThreadRestrictNewHandlesRegion **)(v28 + 328)) == 0
     || !*((_BYTE *)v50 + 80)
     || !ThreadRestrictNewHandlesRegion::InRegion(v50, v21)) )
  {
    LOBYTE(v56) = 1;
LABEL_82:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v54);
    v31 = v54;
    v29 = v55;
    v20 = v57;
  }
LABEL_34:
  if ( v29 )
  {
    if ( *((_BYTE *)v31 + 14) == 1 && *((_WORD *)v31 + 6) == WORD1(a1) )
    {
      CurrentThread = KeGetCurrentThread();
      v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v20 + 1) + 96LL))(*((_QWORD *)v20 + 1), *v31);
      v14 = (DC *)v34;
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
    v35 = (__int64 *)*((_QWORD *)v20 + 1);
    v36 = *v35;
    v37 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v35 + 96))(v35, *v31);
    (*(void (__fastcall **)(__int64 *, __int64))(v36 + 48))(v35, v37);
    KeLeaveCriticalRegion();
  }
  v58 = v14;
  if ( v14 )
  {
    if ( *((_DWORD *)v14 + 534) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)v14 + 6);
      v14 = 0;
      v58 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction() != 1
      && (unsigned __int8)PsIsWin32KFilterAuditEnabled() )
    {
      PsGetWin32KFilterSet();
    }
    v14 = v58;
  }
  if ( !v14 )
    goto LABEL_56;
  if ( (*((_DWORD *)v14 + 11) & 2) == 0 )
  {
    CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
    v39 = v58;
    v40 = CurrentProcessId & 0xFFFFFFFC;
    if ( *(_QWORD *)v58 )
    {
      v41 = (char *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v60 + 1) + 8LL))(*((_QWORD *)v60 + 1));
    }
    else
    {
      v41 = (char *)v58 + 2152;
      *(_OWORD *)((char *)v58 + 2152) = 0;
      *((_QWORD *)v39 + 271) = 0;
      *((_DWORD *)v39 + 540) = -2147483630;
      *((_QWORD *)v39 + 271) = 0;
    }
    if ( v40 == (*((_DWORD *)v41 + 2) & 0xFFFFFFFE) )
    {
      v42 = DC::PentryFromPobj(v58, v60);
      if ( v42 )
      {
        v43 = (struct _DC_ATTR *)GreDecodeUserModePointer(*((void **)v42 + 2));
        if ( v43 )
        {
          if ( !(unsigned int)DC::SaveAttributes(v58, v43) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)v58 + 6);
            v58 = 0;
            goto LABEL_56;
          }
        }
      }
    }
    *((_DWORD *)v58 + 11) |= 2u;
    v14 = v58;
    v59 = 1;
  }
  v3 = a1;
  if ( (*((_DWORD *)v14 + 130) & 4) != 0 )
  {
    *((_DWORD *)v14 + 130) &= ~4u;
    v44 = *((_QWORD *)v14 + 122);
    v45 = *(_DWORD *)(v44 + 340);
    if ( (*((_DWORD *)v14 + 130) & 1) != 0 )
      v46 = v45 | 0x16090;
    else
      v46 = v45 | 0x6090;
    *(_DWORD *)(v44 + 340) = v46;
    goto LABEL_11;
  }
LABEL_12:
  if ( !v14 )
  {
LABEL_56:
    EngSetLastError(0xAAu);
    v47 = v58;
    if ( v58 )
    {
      if ( v59 && (*((_DWORD *)v58 + 11) & 2) != 0 )
      {
        DCOBJ::RestoreAttributesHelper((DCOBJ *)&v58);
        *((_DWORD *)v58 + 11) &= ~2u;
        v47 = v58;
        v59 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)v47 + 6);
      v58 = 0;
    }
    v48 = v62;
    if ( *(__int128 **)(v62 + 8) != &v62 || (v49 = *((_QWORD *)&v62 + 1), **((__int128 ***)&v62 + 1) != &v62) )
LABEL_5:
      __fastfail(3u);
    **((_QWORD **)&v62 + 1) = v62;
    *(_QWORD *)(v48 + 8) = v49;
    return 0;
  }
  if ( (a2 & 0x400000) != 0 )
  {
    *((_BYTE *)v14 + 2090) = 0;
    v14 = v58;
  }
  if ( !*((_BYTE *)v14 + 2090) )
  {
    v15 = 0;
    if ( XDCOBJ::bDelete((XDCOBJ *)&v58, a2) )
      goto LABEL_17;
    EngSetLastError(0xAAu);
    DCOBJ::~DCOBJ((DCOBJ *)&v58);
    return 0;
  }
  v15 = 1;
  XDCOBJ::bCleanDC((XDCOBJ *)&v58, a2 & 0x1000000);
LABEL_17:
  v16 = v58;
  if ( v58 )
  {
    if ( v59 && (*((_DWORD *)v58 + 11) & 2) != 0 )
    {
      DCOBJ::RestoreAttributesHelper((DCOBJ *)&v58);
      *((_DWORD *)v58 + 11) &= ~2u;
      v16 = v58;
      v59 = 0;
    }
    _InterlockedDecrement16((volatile signed __int16 *)v16 + 6);
    v58 = 0;
  }
  v17 = v62;
  if ( *(__int128 **)(v62 + 8) != &v62 )
    goto LABEL_5;
  v18 = *((_QWORD *)&v62 + 1);
  if ( **((__int128 ***)&v62 + 1) != &v62 )
    goto LABEL_5;
  **((_QWORD **)&v62 + 1) = v62;
  *(_QWORD *)(v17 + 8) = v18;
  return !v15 || (unsigned int)UserReleaseDC(v3) != 0;
}

```

## disassembly

```asm
0x140023f00  mov     [rsp-38h+arg_8], rbx
0x140023f05  mov     [rsp-38h+arg_0], rcx
0x140023f0a  push    rbp
0x140023f0b  push    rsi
0x140023f0c  push    rdi
0x140023f0d  push    r12
0x140023f0f  push    r13
0x140023f11  push    r14
0x140023f13  push    r15
0x140023f15  mov     rbp, rsp
0x140023f18  sub     rsp, 80h
0x140023f1f  mov     r15d, edx
0x140023f22  mov     rdi, rcx
0x140023f25  call    cs:__imp_W32GetSessionState
0x140023f2c  nop     dword ptr [rax+rax+00h]
0x140023f31  xor     r14d, r14d
0x140023f34  xorps   xmm0, xmm0
0x140023f37  mov     rbx, [rax+58h]
0x140023f3b  mov     [rbp+var_30], rbx
0x140023f3f  mov     [rbp+var_28], r14
0x140023f43  mov     [rbp+var_40], r14
0x140023f47  mov     [rbp+var_38], r14d
0x140023f4b  movups  [rbp+var_20], xmm0
0x140023f4f  movups  [rbp+var_10], xmm0
0x140023f53  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140023f5a  nop     dword ptr [rax+rax+00h]
0x140023f5f  test    rax, rax
0x140023f62  jz      loc_1400244C3
0x140023f68  mov     rcx, [rax]
0x140023f6b  lea     rax, [rcx+8]
0x140023f6f  neg     rcx
0x140023f72  sbb     rdx, rdx
0x140023f75  and     rdx, rax
0x140023f78  lea     rax, [rbp+var_40]
0x140023f7c  mov     qword ptr [rbp+var_10], rax
0x140023f80  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VDRVOBJ@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic(void *)
0x140023f87  mov     qword ptr [rbp+var_10+8], rax
0x140023f8b  jz      loc_14002452C
0x140023f91  lea     rax, [rdx+58h]
0x140023f95  mov     rcx, [rax]
0x140023f98  cmp     [rcx+8], rax
0x140023f9c  jz      short loc_140023FA5
0x140023f9e  mov     ecx, 3
0x140023fa3  int     29h; Win8: RtlFailFast(ecx)
0x140023fa5  mov     qword ptr [rbp+var_20], rcx
0x140023fa9  lea     rdx, [rbp+var_20]
0x140023fad  mov     qword ptr [rbp+var_20+8], rax
0x140023fb1  mov     [rcx+8], rdx
0x140023fb5  lea     rcx, [rbp+var_20]
0x140023fb9  mov     [rax], rcx
0x140023fbc  mov     r12d, 1
0x140023fc2  cmp     [rbx+0C28h], r14d
0x140023fc9  jnz     short loc_140023FE5
0x140023fcb  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140023fd2  nop     dword ptr [rax+rax+00h]
0x140023fd7  test    rax, rax
0x140023fda  jz      short loc_140023FE5
0x140023fdc  cmp     [rax], r14
0x140023fdf  jnz     loc_1400240BD
0x140023fe5  mov     rdx, rdi; HDC
0x140023fe8  lea     rcx, [rbp+var_40]; this
0x140023fec  call    ?vLockIgnoreAttributes@DCOBJ@@QEAAXPEAUHDC__@@@Z; DCOBJ::vLockIgnoreAttributes(HDC__ *)
0x140023ff1  mov     rsi, [rbp+var_40]
0x140023ff5  test    rsi, rsi
0x140023ff8  jz      loc_14002434A
0x140023ffe  bt      r15d, 16h
0x140024003  jnb     short loc_140024010
0x140024005  mov     [rsi+82Ah], r14b
0x14002400c  mov     rsi, [rbp+var_40]
0x140024010  lea     rcx, [rbp+var_40]; this
0x140024014  cmp     [rsi+82Ah], r14b
0x14002401b  jnz     loc_1400243AB
0x140024021  mov     edx, r15d; unsigned int
0x140024024  mov     bl, r14b
0x140024027  call    ?bDelete@XDCOBJ@@QEAA_NK@Z; XDCOBJ::bDelete(ulong)
0x14002402c  test    al, al
0x14002402e  jz      loc_140024432
0x140024034  mov     rcx, [rbp+var_40]
0x140024038  test    rcx, rcx
0x14002403b  jz      short loc_14002406C
0x14002403d  cmp     [rbp+var_38], r14d
0x140024041  jz      short loc_140024063
0x140024043  mov     eax, [rcx+2Ch]
0x140024046  test    al, 2
0x140024048  jz      short loc_140024063
0x14002404a  lea     rcx, [rbp+var_40]; this
0x14002404e  call    ?RestoreAttributesHelper@DCOBJ@@AEAAXXZ; DCOBJ::RestoreAttributesHelper(void)
0x140024053  mov     rax, [rbp+var_40]
0x140024057  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14002405b  mov     rcx, [rbp+var_40]
0x14002405f  mov     [rbp+var_38], r14d
0x140024063  lock dec word ptr [rcx+0Ch]
0x140024068  mov     [rbp+var_40], r14
0x14002406c  mov     rax, qword ptr [rbp+var_20]
0x140024070  lea     rcx, [rbp+var_20]
0x140024074  cmp     [rax+8], rcx
0x140024078  jnz     loc_140023F9E
0x14002407e  mov     rcx, qword ptr [rbp+var_20+8]
0x140024082  lea     rdx, [rbp+var_20]
0x140024086  cmp     [rcx], rdx
0x140024089  jnz     loc_140023F9E
0x14002408f  mov     [rcx], rax
0x140024092  mov     [rax+8], rcx
0x140024096  test    bl, bl
0x140024098  jnz     loc_140024467
0x14002409e  mov     eax, r12d
0x1400240a1  mov     rbx, [rsp+80h+arg_8]
0x1400240a9  add     rsp, 80h
0x1400240b0  pop     r15
0x1400240b2  pop     r14
0x1400240b4  pop     r13
0x1400240b6  pop     r12
0x1400240b8  pop     rdi
0x1400240b9  pop     rsi
0x1400240ba  pop     rbp
0x1400240bb  retn
0x1400240bd  mov     r13, [rbp+var_30]
0x1400240c1  lea     rcx, [rbp+arg_10]
0x1400240c5  movzx   eax, di
0x1400240c8  mov     r12d, edi
0x1400240cb  shr     r12d, 8
0x1400240cf  mov     rsi, r14
0x1400240d2  and     r12d, 0FF0000h
0x1400240d9  mov     [rbp+var_4C], r14w
0x1400240de  or      r12d, eax
0x1400240e1  mov     [rbp+var_60], r13
0x1400240e5  mov     [rbp+var_48], r13
0x1400240e9  mov     rdi, r14
0x1400240ec  mov     [rbp+arg_10], r14
0x1400240f0  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x1400240f7  nop     dword ptr [rax+rax+00h]
0x1400240fc  mov     r14, rax
0x1400240ff  call    cs:__imp_KeIsAttachedProcess
0x140024106  nop     dword ptr [rax+rax+00h]
0x14002410b  test    al, al
0x14002410d  jnz     loc_1400244CB
0x140024113  test    r14, r14
0x140024116  jz      short loc_14002411B
0x140024118  mov     rdi, [r14]
0x14002411b  lea     rax, [rdi+8]
0x14002411f  neg     rdi
0x140024122  sbb     rbx, rbx
0x140024125  and     rbx, rax
0x140024128  jz      loc_140024523
0x14002412e  mov     r13, [rbx+40h]
0x140024132  mov     [rbp+arg_18], r13
0x140024136  mov     r13, [rbp+var_60]
0x14002413a  mov     ecx, 1
0x14002413f  mov     edx, r12d
0x140024142  mov     edi, ecx
0x140024144  mov     [rbp+var_50], ecx
0x140024147  mov     rcx, [r13+8]
0x14002414b  mov     rax, [rcx]
0x14002414e  mov     rax, [rax+28h]
0x140024152  call    _guard_dispatch_icall
0x140024157  xor     ecx, ecx
0x140024159  mov     [rbp+var_58], rax
0x14002415d  mov     r14, rax
0x140024160  test    rax, rax
0x140024163  jz      loc_14002441F
0x140024169  prefetchw byte ptr [rax+8]
0x14002416d  mov     r13d, [rax+8]
0x140024171  mov     eax, dword ptr [rbp+arg_10]
0x140024174  and     r13d, 0FFFFFFFEh
0x140024178  and     eax, 0FFFFFFFCh
0x14002417b  cmp     r13d, eax
0x14002417e  jnz     loc_1400243C2
0x140024184  mov     r13, [rbp+var_60]
0x140024188  mov     edx, [r14]
0x14002418b  mov     rcx, [r13+8]
0x14002418f  mov     rax, [rcx]
0x140024192  mov     rax, [rax+60h]
0x140024196  call    _guard_dispatch_icall
0x14002419b  test    byte ptr [rax+0Eh], 20h
0x14002419f  jnz     loc_14002447E
0x1400241a5  xor     r12d, r12d
0x1400241a8  test    edi, edi
0x1400241aa  jz      loc_14002423E
0x1400241b0  cmp     byte ptr [r14+0Eh], 1
0x1400241b5  jnz     short loc_14002420D
0x1400241b7  movzx   eax, byte ptr [r14+0Ch]
0x1400241bc  movzx   ecx, byte ptr [r14+0Dh]
0x1400241c1  shl     cx, 8
0x1400241c5  or      cx, ax
0x1400241c8  mov     eax, dword ptr [rbp+arg_0]
0x1400241cb  shr     eax, 10h
0x1400241ce  cmp     cx, ax
0x1400241d1  jnz     short loc_14002420D
0x1400241d3  mov     rbx, gs:188h
0x1400241dc  mov     rcx, [r13+8]
0x1400241e0  mov     edx, [r14]
0x1400241e3  mov     rax, [rcx]
0x1400241e6  mov     rax, [rax+60h]
0x1400241ea  call    _guard_dispatch_icall
0x1400241ef  mov     rsi, rax
0x1400241f2  movzx   ecx, word ptr [rax+0Ch]
0x1400241f6  test    cx, cx
0x1400241f9  jnz     loc_14002444A
0x1400241ff  mov     ecx, 1
0x140024204  lock add [rax+0Ch], cx
0x140024209  mov     [rax+10h], rbx
0x14002420d  mov     rdi, [r13+8]
0x140024211  mov     edx, [r14]
0x140024214  mov     rcx, rdi
0x140024217  mov     rbx, [rdi]
0x14002421a  mov     rax, [rbx+60h]
0x14002421e  call    _guard_dispatch_icall
0x140024223  mov     rdx, rax
0x140024226  mov     rcx, rdi
0x140024229  mov     rax, [rbx+30h]
0x14002422d  call    _guard_dispatch_icall
0x140024232  call    cs:__imp_KeLeaveCriticalRegion
0x140024239  nop     dword ptr [rax+rax+00h]
0x14002423e  xor     r14d, r14d
0x140024241  mov     [rbp+var_40], rsi
0x140024245  test    rsi, rsi
0x140024248  jz      loc_1400244FA
0x14002424e  lea     r12d, [r14+1]
0x140024252  cmp     [rsi+858h], r14d
0x140024259  jnz     loc_14002454F
0x14002425f  test    rsi, rsi
0x140024262  jz      loc_14002434A
0x140024268  mov     eax, [rsi+2Ch]
0x14002426b  test    al, 2
0x14002426d  jnz     loc_140024304
0x140024273  call    cs:__imp_PsGetCurrentProcessId
0x14002427a  nop     dword ptr [rax+rax+00h]
0x14002427f  mov     rdx, [rbp+var_40]
0x140024283  mov     rbx, rax
0x140024286  and     ebx, 0FFFFFFFCh
0x140024289  cmp     [rdx], r14
0x14002428c  jnz     loc_140024392
0x140024292  lea     rax, [rdx+868h]
0x140024299  xorps   xmm0, xmm0
0x14002429c  movups  xmmword ptr [rax], xmm0
0x14002429f  xor     ecx, ecx
0x1400242a1  mov     [rax+10h], rcx
0x1400242a5  mov     dword ptr [rdx+870h], 80000012h
0x1400242af  mov     [rdx+878h], r14
0x1400242b6  mov     eax, [rax+8]
0x1400242b9  and     eax, 0FFFFFFFEh
0x1400242bc  cmp     ebx, eax
0x1400242be  jnz     short loc_1400242F4
0x1400242c0  mov     rdx, [rbp+var_30]; struct Gre::Base::SESSION_GLOBALS *
0x1400242c4  mov     rcx, [rbp+var_40]; this
0x1400242c8  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x1400242cd  test    rax, rax
0x1400242d0  jz      short loc_1400242F4
0x1400242d2  mov     rcx, [rax+10h]; void *
0x1400242d6  call    ?GreDecodeUserModePointer@@YAPEAXPEAX@Z; GreDecodeUserModePointer(void *)
0x1400242db  test    rax, rax
0x1400242de  jz      short loc_1400242F4
0x1400242e0  mov     rcx, [rbp+var_40]; this
0x1400242e4  mov     rdx, rax; struct _DC_ATTR *
0x1400242e7  call    ?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x1400242ec  test    eax, eax
0x1400242ee  jz      loc_140024560
0x1400242f4  mov     rax, [rbp+var_40]
0x1400242f8  or      dword ptr [rax+2Ch], 2
0x1400242fc  mov     rsi, [rbp+var_40]
0x140024300  mov     [rbp+var_38], r12d
0x140024304  mov     eax, [rsi+208h]
0x14002430a  mov     rdi, [rbp+arg_0]
0x14002430e  test    al, 4
0x140024310  jz      loc_140023FF5
0x140024316  and     dword ptr [rsi+208h], 0FFFFFFFBh
0x14002431d  mov     rdx, [rsi+3D0h]
0x140024324  mov     eax, [rsi+208h]
0x14002432a  mov     ecx, [rdx+154h]
0x140024330  test    r12b, al
0x140024333  jz      loc_14002445C
0x140024339  or      ecx, 16090h
0x14002433f  mov     [rdx+154h], ecx
0x140024345  jmp     loc_140023FF1
0x14002434a  mov     ecx, 0AAh; iError
0x14002434f  call    EngSetLastError
0x140024354  mov     rcx, [rbp+var_40]
0x140024358  test    rcx, rcx
0x14002435b  jnz     loc_1400243EB
0x140024361  mov     rax, qword ptr [rbp+var_20]
0x140024365  lea     rcx, [rbp+var_20]
0x140024369  cmp     [rax+8], rcx
0x14002436d  jnz     loc_140023F9E
0x140024373  mov     rcx, qword ptr [rbp+var_20+8]
0x140024377  lea     rdx, [rbp+var_20]
0x14002437b  cmp     [rcx], rdx
0x14002437e  jnz     loc_140023F9E
0x140024384  mov     [rcx], rax
0x140024387  mov     [rax+8], rcx
0x14002438b  xor     eax, eax
0x14002438d  jmp     loc_1400240A1
0x140024392  mov     rax, [rbp+var_30]
0x140024396  mov     rcx, [rax+8]
0x14002439a  mov     rax, [rcx]
0x14002439d  mov     rax, [rax+8]
0x1400243a1  call    _guard_dispatch_icall
0x1400243a6  jmp     loc_1400242B6
0x1400243ab  shr     r15d, 18h
0x1400243af  mov     bl, r12b
0x1400243b2  and     r15b, r12b
  ... truncated ...
```
