# RGNOBJAPI::bSwap(RGNOBJ *)

- ea: `0x14002a730`
- end: `0x14002abb2`
- name: `?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z`
- size: `1154`
- prototype: `__int64 __fastcall(RGNOBJAPI *__hidden this, struct RGNOBJ *)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x140017970`
- `0x140021d40`
- `0x140022690`
- `0x140028b20`
- `0x1400333e0`

## callees

- `0x1400252f0`
- `0x140026270`
- `0x14002a730`
- `0x140031bf4`
- `0x140043e04`
- `0x1400f0fb8`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a918`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002aaf1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a918`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002aaf1`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14002ab74`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14002ab74`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14002ab65`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14002ab65`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002a79b`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002a79b`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14002a78c`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14002a78c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a9ba`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a9fe`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002aa64`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a9ba`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a9fe`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002aa64`
- `WIN32K!W32GetSessionState` at `0x14002a75e`
- `WIN32K!W32GetSessionState` at `0x14002a8a3`
- `WIN32K!W32GetSessionState` at `0x14002a75e`
- `WIN32K!W32GetSessionState` at `0x14002a8a3`

## pseudocode

```c
__int64 __fastcall RGNOBJAPI::bSwap(__int64 **this, __int64 **a2)
{
  __int64 v2; // rsi
  __int64 *v3; // rbx
  __int64 SessionState; // rax
  __int64 v7; // r13
  unsigned int v8; // edi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r14
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  unsigned int *v13; // r14
  unsigned int v14; // esi
  __int64 *v15; // r10
  __int16 v16; // r8
  __int64 v17; // rdi
  unsigned __int16 v18; // cx
  int v19; // esi
  __int16 v20; // dx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int16 v25; // ax
  __int64 *v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rax
  int v29; // r8d
  __int64 *v30; // rbx
  _QWORD *v31; // rsi
  __int64 v32; // rdi
  _QWORD *v33; // r14
  __int64 **v34; // rax
  _QWORD *v35; // rax
  __int64 v36; // rcx
  _QWORD *v37; // rdx
  __int64 *v38; // rcx
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 *v40; // rdi
  _QWORD *v41; // rbx
  __int64 *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  _QWORD *v45; // rax
  __int64 v46; // rcx
  __int64 *v47; // rdi
  _QWORD *v48; // rbx
  __int64 *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rdx
  _QWORD *v52; // rax
  __int64 v53; // rcx
  ThreadRestrictNewHandlesRegion *v55; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v58; // [rsp+20h] [rbp-28h] BYREF
  int v59; // [rsp+28h] [rbp-20h]
  int v60; // [rsp+2Ch] [rbp-1Ch]
  __int64 v61; // [rsp+30h] [rbp-18h]
  __int64 *v62; // [rsp+90h] [rbp+48h]
  __int64 v63; // [rsp+98h] [rbp+50h] BYREF
  __int64 v64; // [rsp+A0h] [rbp+58h]
  __int64 *v65; // [rsp+A8h] [rbp+60h]

  v2 = 0;
  v3 = *this;
  v65 = *a2;
  v62 = v3;
  LOWORD(v60) = 0;
  SessionState = W32GetSessionState(this);
  v63 = 0;
  v7 = *(_QWORD *)(SessionState + 88);
  v8 = (unsigned __int16)*(_DWORD *)v3 | (*(_DWORD *)v3 >> 8) & 0xFF0000;
  v61 = v7;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v63);
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v2 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v10 = (v2 + 8) & -(__int64)(v2 != 0);
  if ( v10 )
    v64 = *(_QWORD *)(((v2 + 8) & -(__int64)(v2 != 0)) + 0x40);
  else
    v64 = 0;
  v11 = *(_QWORD *)(v7 + 8);
  v59 = 1;
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, v8);
  v58 = (unsigned int *)v12;
  v13 = (unsigned int *)v12;
  if ( v12 )
  {
    _m_prefetchw((const void *)(v12 + 8));
    v14 = *(_DWORD *)(v12 + 8) & 0xFFFFFFFE;
    if ( v14 == (v63 & 0xFFFFFFFC) || !v14 || v64 && v14 == (unsigned int)UMPDGetThreadClientPID(v10) )
    {
      if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v7 + 8) + 96LL))(
                         *(_QWORD *)(v7 + 8),
                         *v13)
                     + 14)
          & 0x20) == 0
        || v10
        && (v55 = *(ThreadRestrictNewHandlesRegion **)(v10 + 328)) != 0
        && *((_BYTE *)v55 + 80)
        && ThreadRestrictNewHandlesRegion::InRegion(v55, v8) )
      {
LABEL_9:
        v15 = v65;
        v16 = *((_WORD *)v65 + 7);
        v17 = *v65;
        v18 = *((_WORD *)v62 + 7) & 0x70;
        v19 = *((_DWORD *)v65 + 2);
        v20 = *((_WORD *)v62 + 7) & 0x80;
        v21 = v65[2];
        v60 = *((_DWORD *)v65 + 3);
        v22 = v16 & 0x80u | v18;
        *((_WORD *)v65 + 7) = v22;
        v23 = *(_QWORD *)v62;
        *((_WORD *)v62 + 7) = v16 & 0x70 | v20;
        *v15 = v23;
        *((_WORD *)v15 + 6) = *((_WORD *)v62 + 6);
        *((_DWORD *)v15 + 2) = v62[2];
        v15[2] = *((_QWORD *)v62 + 2);
        v24 = W32GetSessionState(v22);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(*(_QWORD *)(v24 + 88) + 8LL) + 104LL))(
          *(_QWORD *)(*(_QWORD *)(v24 + 88) + 8LL),
          (unsigned __int16)*v62 | (*v62 >> 8) & 0xFF0000u,
          v65);
        v25 = v60;
        *(_QWORD *)v62 = v17;
        *((_WORD *)v62 + 6) = v25;
        v62[2] = v19;
        *((_QWORD *)v62 + 2) = v21;
        v26 = *(__int64 **)(v7 + 8);
        v27 = *v26;
        v28 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v26 + 96))(v26, *v13);
        (*(void (__fastcall **)(__int64 *, __int64))(v27 + 48))(v26, v28);
        KeLeaveCriticalRegion();
        v29 = *((_DWORD *)*this + 19);
        *((_DWORD *)*this + 19) = *((_DWORD *)*a2 + 19);
        *((_DWORD *)*a2 + 19) = v29;
        v30 = *this + 10;
        v31 = *a2 + 10;
        v32 = *v30;
        v33 = (_QWORD *)*v31;
        if ( *this != (__int64 *)-80LL )
        {
          if ( *(__int64 **)(v32 + 8) != v30 )
            goto LABEL_25;
          v34 = (__int64 **)(*this)[11];
          if ( *v34 != v30 )
            goto LABEL_25;
          *v34 = (__int64 *)v32;
          *(_QWORD *)(v32 + 8) = v34;
          v30[1] = (__int64)v30;
          *v30 = (__int64)v30;
        }
        v35 = *a2 + 10;
        if ( *a2 != (__int64 *)-80LL )
        {
          v36 = *v35;
          if ( *(_QWORD **)(*v35 + 8LL) != v35 )
            goto LABEL_25;
          v37 = (_QWORD *)(*a2)[11];
          if ( (_QWORD *)*v37 != v35 )
            goto LABEL_25;
          *v37 = v36;
          *(_QWORD *)(v36 + 8) = v37;
          v35[1] = v35;
          *v35 = v35;
        }
        v38 = *this;
        *this = *a2;
        *a2 = v38;
        CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
        if ( !CurrentThreadWin32Thread
          || (-(__int64)(*CurrentThreadWin32Thread != 0) & (*CurrentThreadWin32Thread + 8LL)) == 0 )
        {
          return 1;
        }
        if ( (__int64 *)v32 != v30 )
        {
          v40 = *this;
          v41 = *this + 10;
          if ( *this != (__int64 *)-80LL )
          {
            v42 = (__int64 *)PsGetCurrentThreadWin32Thread();
            if ( v42 )
              v43 = *v42;
            else
              v43 = 0;
            v41[2] = v40;
            v41[3] = CleanUpRegion;
            v44 = (v43 + 8) & -(__int64)(v43 != 0);
            if ( v44 )
            {
              v45 = (_QWORD *)(v44 + 88);
              v46 = *(_QWORD *)(((v43 + 8) & -(__int64)(v43 != 0)) + 0x58);
              if ( *(_QWORD *)(v46 + 8) != v44 + 88 )
                goto LABEL_25;
              *v41 = v46;
              v41[1] = v45;
              *(_QWORD *)(v46 + 8) = v41;
              *v45 = v41;
            }
            else
            {
              v41[1] = v41;
              *v41 = v41;
            }
          }
        }
        if ( v33 == v31 )
          return 1;
        v47 = *a2;
        v48 = *a2 + 10;
        if ( *a2 == (__int64 *)-80LL )
          return 1;
        v49 = (__int64 *)PsGetCurrentThreadWin32Thread();
        if ( v49 )
          v50 = *v49;
        else
          v50 = 0;
        v48[2] = v47;
        v48[3] = CleanUpRegion;
        v51 = (v50 + 8) & -(__int64)(v50 != 0);
        if ( !v51 )
        {
          v48[1] = v48;
          *v48 = v48;
          return 1;
        }
        v52 = (_QWORD *)(v51 + 88);
        v53 = *(_QWORD *)(((v50 + 8) & -(__int64)(v50 != 0)) + 0x58);
        if ( *(_QWORD *)(v53 + 8) == v51 + 88 )
        {
          *v48 = v53;
          v48[1] = v52;
          *(_QWORD *)(v53 + 8) = v48;
          *v52 = v48;
          return 1;
        }
LABEL_25:
        __fastfail(3u);
      }
      LOBYTE(v60) = 1;
    }
    HANDLELOCK::vUnlock((HANDLELOCK *)&v58);
    if ( v59 )
    {
      v7 = v61;
      v13 = v58;
      goto LABEL_9;
    }
  }
  else
  {
    v59 = 0;
    KeLeaveCriticalRegion();
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v58);
  return 0;
}

```

## disassembly

```asm
0x14002a730  push    rbp
0x14002a732  push    rbx
0x14002a733  push    rsi
0x14002a734  push    rdi
0x14002a735  push    r12
0x14002a737  push    r13
0x14002a739  push    r14
0x14002a73b  push    r15
0x14002a73d  mov     rbp, rsp
0x14002a740  sub     rsp, 48h
0x14002a744  mov     r8, [rdx]
0x14002a747  xor     esi, esi
0x14002a749  mov     rbx, [rcx]
0x14002a74c  mov     r15, rdx
0x14002a74f  mov     [rbp+arg_18], r8
0x14002a753  mov     r12, rcx
0x14002a756  mov     [rbp+arg_0], rbx
0x14002a75a  mov     word ptr [rbp+var_1C], si
0x14002a75e  call    cs:__imp_W32GetSessionState
0x14002a765  nop     dword ptr [rax+rax+00h]
0x14002a76a  lea     rcx, [rbp+arg_8]
0x14002a76e  mov     [rbp+arg_8], rsi
0x14002a772  mov     r13, [rax+58h]
0x14002a776  mov     eax, [rbx]
0x14002a778  mov     edi, eax
0x14002a77a  shr     edi, 8
0x14002a77d  movzx   eax, ax
0x14002a780  and     edi, 0FF0000h
0x14002a786  or      edi, eax
0x14002a788  mov     [rbp+var_18], r13
0x14002a78c  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14002a793  nop     dword ptr [rax+rax+00h]
0x14002a798  mov     r14, rax
0x14002a79b  call    cs:__imp_KeIsAttachedProcess
0x14002a7a2  nop     dword ptr [rax+rax+00h]
0x14002a7a7  test    al, al
0x14002a7a9  jnz     loc_14002AB5E
0x14002a7af  test    r14, r14
0x14002a7b2  jz      short loc_14002A7B7
0x14002a7b4  mov     rsi, [r14]
0x14002a7b7  lea     rax, [rsi+8]
0x14002a7bb  neg     rsi
0x14002a7be  sbb     rbx, rbx
0x14002a7c1  and     rbx, rax
0x14002a7c4  jz      loc_14002AB8D
0x14002a7ca  mov     rsi, [rbx+40h]
0x14002a7ce  mov     [rbp+arg_10], rsi
0x14002a7d2  mov     rcx, [r13+8]
0x14002a7d6  mov     edx, edi
0x14002a7d8  mov     [rbp+var_20], 1
0x14002a7df  mov     rax, [rcx]
0x14002a7e2  mov     rax, [rax+28h]
0x14002a7e6  call    _guard_dispatch_icall
0x14002a7eb  mov     [rbp+var_28], rax
0x14002a7ef  mov     r14, rax
0x14002a7f2  test    rax, rax
0x14002a7f5  jz      loc_14002AAEA
0x14002a7fb  prefetchw byte ptr [rax+8]
0x14002a7ff  mov     esi, [rax+8]
0x14002a802  mov     eax, dword ptr [rbp+arg_8]
0x14002a805  and     esi, 0FFFFFFFEh
0x14002a808  and     eax, 0FFFFFFFCh
0x14002a80b  cmp     esi, eax
0x14002a80d  jnz     loc_14002AAC9
0x14002a813  mov     rcx, [r13+8]
0x14002a817  mov     edx, [r14]
0x14002a81a  mov     rax, [rcx]
0x14002a81d  mov     rax, [rax+60h]
0x14002a821  call    _guard_dispatch_icall
0x14002a826  test    byte ptr [rax+0Eh], 20h
0x14002a82a  jnz     loc_14002AB0A
0x14002a830  mov     r10, [rbp+arg_18]
0x14002a834  mov     r11d, 80h
0x14002a83a  mov     r9, [rbp+arg_0]
0x14002a83e  mov     eax, [r10+0Ch]
0x14002a842  movzx   edx, word ptr [r9+0Eh]
0x14002a847  movzx   r8d, word ptr [r10+0Eh]
0x14002a84c  movzx   ecx, dx
0x14002a84f  mov     rdi, [r10]
0x14002a852  and     cx, 70h
0x14002a856  mov     esi, [r10+8]
0x14002a85a  and     dx, r11w
0x14002a85e  mov     rbx, [r10+10h]
0x14002a862  mov     [rbp+var_1C], eax
0x14002a865  movzx   eax, r8w
0x14002a869  and     ax, r11w
0x14002a86d  and     r8w, 70h
0x14002a872  or      cx, ax
0x14002a875  or      dx, r8w
0x14002a879  mov     [r10+0Eh], cx
0x14002a87e  mov     rax, [r9]
0x14002a881  mov     [r9+0Eh], dx
0x14002a886  mov     [r10], rax
0x14002a889  movzx   eax, word ptr [r9+0Ch]
0x14002a88e  xchg    ax, [r10+0Ch]
0x14002a893  mov     eax, [r9+8]
0x14002a897  mov     [r10+8], eax
0x14002a89b  mov     rax, [r9+10h]
0x14002a89f  mov     [r10+10h], rax
0x14002a8a3  call    cs:__imp_W32GetSessionState
0x14002a8aa  nop     dword ptr [rax+rax+00h]
0x14002a8af  mov     r8, [rbp+arg_18]
0x14002a8b3  mov     rcx, [rax+58h]
0x14002a8b7  mov     rax, [rbp+arg_0]
0x14002a8bb  mov     rcx, [rcx+8]
0x14002a8bf  mov     eax, [rax]
0x14002a8c1  mov     edx, eax
0x14002a8c3  shr     edx, 8
0x14002a8c6  movzx   eax, ax
0x14002a8c9  and     edx, 0FF0000h
0x14002a8cf  mov     r9, [rcx]
0x14002a8d2  or      edx, eax
0x14002a8d4  mov     rax, [r9+68h]
0x14002a8d8  call    _guard_dispatch_icall
0x14002a8dd  movzx   eax, word ptr [rbp+var_1C]
0x14002a8e1  mov     rcx, [rbp+arg_0]
0x14002a8e5  mov     [rcx], rdi
0x14002a8e8  xchg    ax, [rcx+0Ch]
0x14002a8ec  mov     [rcx+8], esi
0x14002a8ef  mov     [rcx+10h], rbx
0x14002a8f3  mov     rdi, [r13+8]
0x14002a8f7  mov     edx, [r14]
0x14002a8fa  mov     rcx, rdi
0x14002a8fd  mov     rbx, [rdi]
0x14002a900  mov     rax, [rbx+60h]
0x14002a904  call    _guard_dispatch_icall
0x14002a909  mov     rdx, rax
0x14002a90c  mov     rcx, rdi
0x14002a90f  mov     rax, [rbx+30h]
0x14002a913  call    _guard_dispatch_icall
0x14002a918  call    cs:__imp_KeLeaveCriticalRegion
0x14002a91f  nop     dword ptr [rax+rax+00h]
0x14002a924  mov     rax, [r15]
0x14002a927  mov     rdx, [r12]
0x14002a92b  mov     ecx, [rax+4Ch]
0x14002a92e  mov     r8d, [rdx+4Ch]
0x14002a932  mov     [rdx+4Ch], ecx
0x14002a935  mov     rax, [r15]
0x14002a938  mov     [rax+4Ch], r8d
0x14002a93c  mov     rbx, [r12]
0x14002a940  mov     rsi, [r15]
0x14002a943  add     rbx, 50h ; 'P'
0x14002a947  add     rsi, 50h ; 'P'
0x14002a94b  mov     rdi, [rbx]
0x14002a94e  mov     r14, [rsi]
0x14002a951  test    rbx, rbx
0x14002a954  jz      short loc_14002A97B
0x14002a956  cmp     [rdi+8], rbx
0x14002a95a  jnz     loc_14002AA3E
0x14002a960  mov     rax, [rbx+8]
0x14002a964  cmp     [rax], rbx
0x14002a967  jnz     loc_14002AA3E
0x14002a96d  mov     [rax], rdi
0x14002a970  mov     [rdi+8], rax
0x14002a974  mov     [rbx+8], rbx
0x14002a978  mov     [rbx], rbx
0x14002a97b  mov     rax, [r15]
0x14002a97e  add     rax, 50h ; 'P'
0x14002a982  jz      short loc_14002A9AC
0x14002a984  mov     rcx, [rax]
0x14002a987  cmp     [rcx+8], rax
0x14002a98b  jnz     loc_14002AA3E
0x14002a991  mov     rdx, [rax+8]
0x14002a995  cmp     [rdx], rax
0x14002a998  jnz     loc_14002AA3E
0x14002a99e  mov     [rdx], rcx
0x14002a9a1  mov     [rcx+8], rdx
0x14002a9a5  mov     [rax+8], rax
0x14002a9a9  mov     [rax], rax
0x14002a9ac  mov     rax, [r15]
0x14002a9af  mov     rcx, [r12]
0x14002a9b3  mov     [r12], rax
0x14002a9b7  mov     [r15], rcx
0x14002a9ba  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002a9c1  nop     dword ptr [rax+rax+00h]
0x14002a9c6  test    rax, rax
0x14002a9c9  jz      loc_14002AAB2
0x14002a9cf  mov     rax, [rax]
0x14002a9d2  lea     rcx, [rax+8]
0x14002a9d6  neg     rax
0x14002a9d9  sbb     rax, rax
0x14002a9dc  test    rcx, rax
0x14002a9df  jz      loc_14002AAB2
0x14002a9e5  lea     r13, ?CleanUpRegion@@YAXPEAVREGION@@@Z; CleanUpRegion(REGION *)
0x14002a9ec  cmp     rdi, rbx
0x14002a9ef  jz      short loc_14002AA53
0x14002a9f1  mov     rdi, [r12]
0x14002a9f5  lea     rbx, [rdi+50h]
0x14002a9f9  test    rbx, rbx
0x14002a9fc  jz      short loc_14002AA53
0x14002a9fe  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002aa05  nop     dword ptr [rax+rax+00h]
0x14002aa0a  test    rax, rax
0x14002aa0d  jz      loc_14002AB50
0x14002aa13  mov     rcx, [rax]
0x14002aa16  lea     rax, [rcx+8]
0x14002aa1a  mov     [rbx+10h], rdi
0x14002aa1e  neg     rcx
0x14002aa21  mov     [rbx+18h], r13
0x14002aa25  sbb     rdx, rdx
0x14002aa28  and     rdx, rax
0x14002aa2b  jz      loc_14002AB9A
0x14002aa31  lea     rax, [rdx+58h]
0x14002aa35  mov     rcx, [rax]
0x14002aa38  cmp     [rcx+8], rax
0x14002aa3c  jz      short loc_14002AA45
0x14002aa3e  mov     ecx, 3
0x14002aa43  int     29h; Win8: RtlFailFast(ecx)
0x14002aa45  mov     [rbx], rcx
0x14002aa48  mov     [rbx+8], rax
0x14002aa4c  mov     [rcx+8], rbx
0x14002aa50  mov     [rax], rbx
0x14002aa53  cmp     r14, rsi
0x14002aa56  jz      short loc_14002AAB2
0x14002aa58  mov     rdi, [r15]
0x14002aa5b  lea     rbx, [rdi+50h]
0x14002aa5f  test    rbx, rbx
0x14002aa62  jz      short loc_14002AAB2
0x14002aa64  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002aa6b  nop     dword ptr [rax+rax+00h]
0x14002aa70  test    rax, rax
0x14002aa73  jz      loc_14002AB57
0x14002aa79  mov     rcx, [rax]
0x14002aa7c  lea     rax, [rcx+8]
0x14002aa80  mov     [rbx+10h], rdi
0x14002aa84  neg     rcx
0x14002aa87  mov     [rbx+18h], r13
0x14002aa8b  sbb     rdx, rdx
0x14002aa8e  and     rdx, rax
0x14002aa91  jz      loc_14002ABA6
0x14002aa97  lea     rax, [rdx+58h]
0x14002aa9b  mov     rcx, [rax]
0x14002aa9e  cmp     [rcx+8], rax
0x14002aaa2  jnz     short loc_14002AA3E
0x14002aaa4  mov     [rbx], rcx
0x14002aaa7  mov     [rbx+8], rax
0x14002aaab  mov     [rcx+8], rbx
0x14002aaaf  mov     [rax], rbx
0x14002aab2  mov     eax, 1
0x14002aab7  add     rsp, 48h
0x14002aabb  pop     r15
0x14002aabd  pop     r14
0x14002aabf  pop     r13
0x14002aac1  pop     r12
0x14002aac3  pop     rdi
0x14002aac4  pop     rsi
0x14002aac5  pop     rbx
0x14002aac6  pop     rbp
0x14002aac7  retn
0x14002aac9  test    esi, esi
0x14002aacb  jz      loc_14002A813
0x14002aad1  cmp     [rbp+arg_10], 0
0x14002aad6  jz      short loc_14002AB34
0x14002aad8  mov     rcx, rbx
0x14002aadb  call    UMPDGetThreadClientPID
0x14002aae0  cmp     esi, eax
0x14002aae2  jz      loc_14002A813
0x14002aae8  jmp     short loc_14002AB34
0x14002aaea  mov     [rbp+var_20], 0
0x14002aaf1  call    cs:__imp_KeLeaveCriticalRegion
0x14002aaf8  nop     dword ptr [rax+rax+00h]
0x14002aafd  lea     rcx, [rbp+var_28]; this
0x14002ab01  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x14002ab06  xor     eax, eax
0x14002ab08  jmp     short loc_14002AAB7
0x14002ab0a  test    rbx, rbx
0x14002ab0d  jz      short loc_14002AB30
0x14002ab0f  mov     rcx, [rbx+148h]; this
0x14002ab16  test    rcx, rcx
0x14002ab19  jz      short loc_14002AB30
0x14002ab1b  cmp     byte ptr [rcx+50h], 0
0x14002ab1f  jz      short loc_14002AB30
0x14002ab21  mov     edx, edi; unsigned int
0x14002ab23  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14002ab28  test    al, al
0x14002ab2a  jnz     loc_14002A830
0x14002ab30  mov     byte ptr [rbp+var_1C], 1
0x14002ab34  lea     rcx, [rbp+var_28]; this
0x14002ab38  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14002ab3d  cmp     [rbp+var_20], 0
0x14002ab41  jz      short loc_14002AAFD
0x14002ab43  mov     r13, [rbp+var_18]
0x14002ab47  mov     r14, [rbp+var_28]
0x14002ab4b  jmp     loc_14002A830
0x14002ab50  xor     ecx, ecx
0x14002ab52  jmp     loc_14002AA16
0x14002ab57  xor     ecx, ecx
0x14002ab59  jmp     loc_14002AA7C
0x14002ab5e  call    W32GetCurrentWin32kSessionId
0x14002ab63  mov     ebx, eax
0x14002ab65  call    cs:__imp_PsGetCurrentThreadProcess
0x14002ab6c  nop     dword ptr [rax+rax+00h]
0x14002ab71  mov     rcx, rax
0x14002ab74  call    cs:__imp_PsGetProcessSessionIdEx
0x14002ab7b  nop     dword ptr [rax+rax+00h]
0x14002ab80  cmp     ebx, eax
0x14002ab82  jz      loc_14002A7AF
0x14002ab88  jmp     loc_14002A7B7
0x14002ab8d  mov     [rbp+arg_10], 0
0x14002ab95  jmp     loc_14002A7D2
  ... truncated ...
```
