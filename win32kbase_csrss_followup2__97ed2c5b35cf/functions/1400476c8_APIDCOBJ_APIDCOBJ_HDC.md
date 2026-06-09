# APIDCOBJ::APIDCOBJ(HDC__ *)

- ea: `0x1400476c8`
- end: `0x140047bad`
- name: `??0APIDCOBJ@@QEAA@PEAUHDC__@@@Z`
- size: `1253`
- prototype: `APIDCOBJ *__fastcall(APIDCOBJ *__hidden this, HDC)`
- caller_count: `17`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f060`
- `0x140010d20`
- `0x140012840`
- `0x140012a60`
- `0x1400188d0`
- `0x14001e010`
- `0x14002b410`
- `0x140032a20`
- `0x140036170`
- `0x140062bac`
- `0x140064290`
- `0x140065f50`
- `0x1400d3ed0`
- `0x14012f740`
- `0x140161320`
- `0x140182440`
- `0x1401e61a8`

## callees

- `0x140010e60`
- `0x140026270`
- `0x140031bf4`
- `0x140043e04`
- `0x1400455a4`
- `0x1400476c8`
- `0x14004800c`
- `0x1400f0fb8`
- `0x140110520`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047904`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047a70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047904`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047a70`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140047b08`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140047b08`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140047b49`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140047b49`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140047af9`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140047af9`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400477ce`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400477ce`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x140047b35`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x140047b35`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400477bf`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400477bf`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14004772e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400479b3`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14004772e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400479b3`
- `WIN32K!W32GetSessionState` at `0x1400476f0`
- `WIN32K!W32GetSessionState` at `0x1400476f0`

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
0x1400476c8  mov     [rsp-40h+arg_8], rdx
0x1400476cd  push    rbp
0x1400476ce  push    rbx
0x1400476cf  push    rsi
0x1400476d0  push    rdi
0x1400476d1  push    r12
0x1400476d3  push    r13
0x1400476d5  push    r14
0x1400476d7  push    r15
0x1400476d9  mov     rbp, rsp
0x1400476dc  sub     rsp, 48h
0x1400476e0  xor     r12d, r12d
0x1400476e3  mov     r15, rdx
0x1400476e6  mov     [rcx], r12
0x1400476e9  mov     rsi, rcx
0x1400476ec  mov     [rcx+8], r12d
0x1400476f0  call    cs:__imp_W32GetSessionState
0x1400476f7  nop     dword ptr [rax+rax+00h]
0x1400476fc  lea     rbx, [rsi+20h]
0x140047700  xorps   xmm0, xmm0
0x140047703  mov     r8, [rax+58h]
0x140047707  mov     rax, rbx
0x14004770a  neg     rax
0x14004770d  mov     [rsi+10h], r8
0x140047711  mov     [rsi+18h], r12
0x140047715  sbb     rdi, rdi
0x140047718  mov     [rsi], r12
0x14004771b  mov     [rsi+8], r12d
0x14004771f  and     rdi, rsi
0x140047722  movups  xmmword ptr [rbx], xmm0
0x140047725  movups  xmmword ptr [rbx+10h], xmm0
0x140047729  test    rbx, rbx
0x14004772c  jz      short loc_14004778A
0x14004772e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140047735  nop     dword ptr [rax+rax+00h]
0x14004773a  test    rax, rax
0x14004773d  jz      loc_140047AE2
0x140047743  mov     rcx, [rax]
0x140047746  lea     rax, [rcx+8]
0x14004774a  mov     [rbx+10h], rdi
0x14004774e  neg     rcx
0x140047751  sbb     rdx, rdx
0x140047754  and     rdx, rax
0x140047757  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VDRVOBJ@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic(void *)
0x14004775e  mov     [rbx+18h], rax
0x140047762  jz      loc_140047B63
0x140047768  lea     rax, [rdx+58h]
0x14004776c  mov     rcx, [rax]
0x14004776f  cmp     [rcx+8], rax
0x140047773  jz      short loc_14004777C
0x140047775  mov     ecx, 3
0x14004777a  int     29h; Win8: RtlFailFast(ecx)
0x14004777c  mov     [rbx], rcx
0x14004777f  mov     [rbx+8], rax
0x140047783  mov     [rcx+8], rbx
0x140047787  mov     [rax], rbx
0x14004778a  movzx   eax, r15w
0x14004778e  lea     rcx, [rbp+arg_0]
0x140047792  xor     ebx, ebx
0x140047794  mov     [rbp+var_1C], r12w
0x140047799  mov     r13d, r15d
0x14004779c  mov     [rbp+arg_0], rbx
0x1400477a0  shr     r13d, 8
0x1400477a4  mov     r14, r12
0x1400477a7  mov     r12, [rsi+10h]
0x1400477ab  and     r13d, 0FF0000h
0x1400477b2  or      r13d, eax
0x1400477b5  mov     [rbp+arg_18], r12
0x1400477b9  mov     [rbp+var_18], r12
0x1400477bd  mov     edi, ebx
0x1400477bf  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x1400477c6  nop     dword ptr [rax+rax+00h]
0x1400477cb  mov     r15, rax
0x1400477ce  call    cs:__imp_KeIsAttachedProcess
0x1400477d5  nop     dword ptr [rax+rax+00h]
0x1400477da  test    al, al
0x1400477dc  jnz     loc_140047AF2
0x1400477e2  test    r15, r15
0x1400477e5  jz      short loc_1400477EA
0x1400477e7  mov     rdi, [r15]
0x1400477ea  lea     rax, [rdi+8]
0x1400477ee  neg     rdi
0x1400477f1  sbb     rbx, rbx
0x1400477f4  and     rbx, rax
0x1400477f7  jz      loc_140047B5A
0x1400477fd  mov     r12, [rbx+40h]
0x140047801  mov     [rbp+arg_10], r12
0x140047805  mov     r12, [rbp+arg_18]
0x140047809  mov     rcx, [r12+8]
0x14004780e  mov     edi, 1
0x140047813  mov     edx, r13d
0x140047816  mov     [rbp+var_20], edi
0x140047819  mov     rax, [rcx]
0x14004781c  mov     rax, [rax+28h]
0x140047820  call    _guard_dispatch_icall
0x140047825  xor     ecx, ecx
0x140047827  mov     [rbp+var_28], rax
0x14004782b  mov     r15, rax
0x14004782e  test    rax, rax
0x140047831  jz      loc_140047A6E
0x140047837  prefetchw byte ptr [rax+8]
0x14004783b  mov     r12d, [rax+8]
0x14004783f  mov     eax, dword ptr [rbp+arg_0]
0x140047842  and     r12d, 0FFFFFFFEh
0x140047846  and     eax, 0FFFFFFFCh
0x140047849  cmp     r12d, eax
0x14004784c  jnz     loc_140047A4C
0x140047852  mov     r12, [rbp+arg_18]
0x140047856  mov     edx, [r15]
0x140047859  mov     rcx, [r12+8]
0x14004785e  mov     rax, [rcx]
0x140047861  mov     rax, [rax+60h]
0x140047865  call    _guard_dispatch_icall
0x14004786a  test    byte ptr [rax+0Eh], 20h
0x14004786e  jnz     loc_140047A9D
0x140047874  xor     r13d, r13d
0x140047877  test    edi, edi
0x140047879  jz      loc_140047910
0x14004787f  cmp     byte ptr [r15+0Eh], 1
0x140047884  jnz     short loc_1400478DE
0x140047886  movzx   eax, byte ptr [r15+0Ch]
0x14004788b  movzx   ecx, byte ptr [r15+0Dh]
0x140047890  shl     cx, 8
0x140047894  or      cx, ax
0x140047897  mov     rax, [rbp+arg_8]
0x14004789b  shr     eax, 10h
0x14004789e  cmp     cx, ax
0x1400478a1  jnz     short loc_1400478DE
0x1400478a3  mov     rbx, gs:188h
0x1400478ac  mov     rcx, [r12+8]
0x1400478b1  mov     edx, [r15]
0x1400478b4  mov     rax, [rcx]
0x1400478b7  mov     rax, [rax+60h]
0x1400478bb  call    _guard_dispatch_icall
0x1400478c0  mov     r14, rax
0x1400478c3  movzx   ecx, word ptr [rax+0Ch]
0x1400478c7  test    cx, cx
0x1400478ca  jnz     loc_140047A81
0x1400478d0  mov     ecx, 1
0x1400478d5  lock add [rax+0Ch], cx
0x1400478da  mov     [rax+10h], rbx
0x1400478de  mov     rdi, [r12+8]
0x1400478e3  mov     edx, [r15]
0x1400478e6  mov     rcx, rdi
0x1400478e9  mov     rbx, [rdi]
0x1400478ec  mov     rax, [rbx+60h]
0x1400478f0  call    _guard_dispatch_icall
0x1400478f5  mov     rdx, rax
0x1400478f8  mov     rcx, rdi
0x1400478fb  mov     rax, [rbx+30h]
0x1400478ff  call    _guard_dispatch_icall
0x140047904  call    cs:__imp_KeLeaveCriticalRegion
0x14004790b  nop     dword ptr [rax+rax+00h]
0x140047910  xor     r15d, r15d
0x140047913  mov     [rsi], r14
0x140047916  test    r14, r14
0x140047919  jz      loc_140047B21
0x14004791f  cmp     [r14+858h], r15d
0x140047926  jnz     loc_140047B7B
0x14004792c  mov     r14d, 1
0x140047932  mov     rax, [rsi]
0x140047935  test    rax, rax
0x140047938  jz      short loc_140047994
0x14004793a  mov     eax, [rax+2Ch]
0x14004793d  test    al, 2
0x14004793f  jnz     short loc_14004795C
0x140047941  mov     rcx, rsi; this
0x140047944  call    ?SaveAttributesHelper@DCOBJ@@AEAAHXZ; DCOBJ::SaveAttributesHelper(void)
0x140047949  mov     rcx, [rsi]
0x14004794c  test    eax, eax
0x14004794e  jz      loc_140047B89
0x140047954  or      dword ptr [rcx+2Ch], 2
0x140047958  mov     [rsi+8], r14d
0x14004795c  mov     rdx, [rsi]
0x14004795f  mov     ecx, [rdx+208h]
0x140047965  test    cl, 4
0x140047968  jz      short loc_140047994
0x14004796a  and     ecx, 0FFFFFFFBh
0x14004796d  mov     [rdx+208h], ecx
0x140047973  mov     rdx, [rdx+3D0h]
0x14004797a  mov     eax, [rdx+154h]
0x140047980  test    r14b, cl
0x140047983  jz      loc_140047A93
0x140047989  or      eax, 16090h
0x14004798e  mov     [rdx+154h], eax
0x140047994  lea     rbx, [rsi+40h]
0x140047998  xorps   xmm0, xmm0
0x14004799b  mov     rax, rbx
0x14004799e  neg     rax
0x1400479a1  movups  xmmword ptr [rbx], xmm0
0x1400479a4  sbb     rdi, rdi
0x1400479a7  and     rdi, rsi
0x1400479aa  movups  xmmword ptr [rbx+10h], xmm0
0x1400479ae  test    rbx, rbx
0x1400479b1  jz      short loc_140047A0C
0x1400479b3  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400479ba  nop     dword ptr [rax+rax+00h]
0x1400479bf  test    rax, rax
0x1400479c2  jz      loc_140047AEA
0x1400479c8  mov     rcx, [rax]
0x1400479cb  lea     rax, [rcx+8]
0x1400479cf  mov     [rbx+10h], rdi
0x1400479d3  neg     rcx
0x1400479d6  sbb     rdx, rdx
0x1400479d9  and     rdx, rax
0x1400479dc  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400479e3  mov     [rbx+18h], rax
0x1400479e7  jz      loc_140047B6F
0x1400479ed  lea     rax, [rdx+58h]
0x1400479f1  mov     rcx, [rax]
0x1400479f4  cmp     [rcx+8], rax
0x1400479f8  jnz     loc_140047775
0x1400479fe  mov     [rbx], rcx
0x140047a01  mov     [rbx+8], rax
0x140047a05  mov     [rcx+8], rbx
0x140047a09  mov     [rax], rbx
0x140047a0c  mov     rax, [rsi]
0x140047a0f  mov     [rsi+60h], r14b
0x140047a13  test    rax, rax
0x140047a16  jz      short loc_140047A37
0x140047a18  movzx   eax, word ptr [rax+0Ch]
0x140047a1c  cmp     ax, r14w
0x140047a20  jnz     loc_140047B96
0x140047a26  mov     rax, [rsi]
0x140047a29  movzx   ecx, word ptr [rax+0Ch]
0x140047a2d  cmp     cx, r14w
0x140047a31  jnz     loc_140047BA0
0x140047a37  mov     rax, rsi
0x140047a3a  add     rsp, 48h
0x140047a3e  pop     r15
0x140047a40  pop     r14
0x140047a42  pop     r13
0x140047a44  pop     r12
0x140047a46  pop     rdi
0x140047a47  pop     rsi
0x140047a48  pop     rbx
0x140047a49  pop     rbp
0x140047a4a  retn
0x140047a4c  test    r12d, r12d
0x140047a4f  jz      loc_140047852
0x140047a55  cmp     [rbp+arg_10], rcx
0x140047a59  jz      short loc_140047AC9
0x140047a5b  mov     rcx, rbx
0x140047a5e  call    UMPDGetThreadClientPID
0x140047a63  cmp     r12d, eax
0x140047a66  jz      loc_140047852
0x140047a6c  jmp     short loc_140047AC9
0x140047a6e  mov     edi, ecx
0x140047a70  call    cs:__imp_KeLeaveCriticalRegion
0x140047a77  nop     dword ptr [rax+rax+00h]
0x140047a7c  jmp     loc_140047874
0x140047a81  cmp     [rax+10h], rbx
0x140047a85  jz      loc_1400478D0
0x140047a8b  mov     r14, r13
0x140047a8e  jmp     loc_1400478DE
0x140047a93  or      eax, 6090h
0x140047a98  jmp     loc_14004798E
0x140047a9d  xor     eax, eax
0x140047a9f  test    rbx, rbx
0x140047aa2  jz      short loc_140047AC5
0x140047aa4  mov     rcx, [rbx+148h]; this
0x140047aab  test    rcx, rcx
0x140047aae  jz      short loc_140047AC5
0x140047ab0  cmp     [rcx+50h], al
0x140047ab3  jz      short loc_140047AC5
0x140047ab5  mov     edx, r13d; unsigned int
0x140047ab8  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x140047abd  test    al, al
0x140047abf  jnz     loc_140047874
0x140047ac5  mov     byte ptr [rbp+var_1C], dil
0x140047ac9  lea     rcx, [rbp+var_28]; this
0x140047acd  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140047ad2  mov     r15, [rbp+var_28]
0x140047ad6  mov     edi, [rbp+var_20]
0x140047ad9  mov     r12, [rbp+var_18]
0x140047add  jmp     loc_140047874
0x140047ae2  mov     rcx, r12
0x140047ae5  jmp     loc_140047746
0x140047aea  mov     rcx, r15
0x140047aed  jmp     loc_1400479CB
0x140047af2  call    W32GetCurrentWin32kSessionId
0x140047af7  mov     ebx, eax
0x140047af9  call    cs:__imp_PsGetCurrentThreadProcess
0x140047b00  nop     dword ptr [rax+rax+00h]
0x140047b05  mov     rcx, rax
0x140047b08  call    cs:__imp_PsGetProcessSessionIdEx
0x140047b0f  nop     dword ptr [rax+rax+00h]
0x140047b14  cmp     ebx, eax
0x140047b16  jz      loc_1400477E2
0x140047b1c  jmp     loc_1400477EA
0x140047b21  call    ?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140047b26  mov     r14d, 1
0x140047b2c  cmp     eax, r14d
0x140047b2f  jz      loc_140047932
0x140047b35  call    cs:__imp_PsIsWin32KFilterAuditEnabled
0x140047b3c  nop     dword ptr [rax+rax+00h]
0x140047b41  test    al, al
0x140047b43  jz      loc_140047932
0x140047b49  call    cs:__imp_PsGetWin32KFilterSet
0x140047b50  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
