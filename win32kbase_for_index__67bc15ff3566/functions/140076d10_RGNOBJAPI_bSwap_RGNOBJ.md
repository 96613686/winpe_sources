# RGNOBJAPI::bSwap(RGNOBJ *)

- ea: `0x140076d10`
- end: `0x140077192`
- name: `?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z`
- size: `1154`
- prototype: `__int64 __fastcall(RGNOBJAPI *__hidden this, struct RGNOBJ *)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x14002e5a0`
- `0x14002eef0`
- `0x140070250`
- `0x1400756d0`
- `0x140077900`

## callees

- `0x14001e034`
- `0x140031c20`
- `0x1400371c0`
- `0x140076d10`
- `0x140079330`
- `0x14012e228`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076ef8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400770d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076ef8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400770d1`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140077154`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140077154`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140077145`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140077145`
- `ntoskrnl!KeIsAttachedProcess` at `0x140076d7b`
- `ntoskrnl!KeIsAttachedProcess` at `0x140076d7b`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140076d6c`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140076d6c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140076f9a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140076fde`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140077044`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140076f9a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140076fde`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140077044`
- `WIN32K!W32GetSessionState` at `0x140076d3e`
- `WIN32K!W32GetSessionState` at `0x140076e83`
- `WIN32K!W32GetSessionState` at `0x140076d3e`
- `WIN32K!W32GetSessionState` at `0x140076e83`

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
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int *v15; // r14
  unsigned int v16; // esi
  __int64 *v17; // r10
  __int16 v18; // r8
  __int64 v19; // rdi
  unsigned __int16 v20; // cx
  int v21; // esi
  __int16 v22; // dx
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int16 v27; // ax
  __int64 *v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 *v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rbx
  _QWORD *v35; // rsi
  __int64 v36; // rdi
  _QWORD *v37; // r14
  __int64 **v38; // rax
  _QWORD *v39; // rax
  __int64 v40; // rcx
  __int64 *v41; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 *v48; // rdi
  __int64 *v49; // rbx
  __int64 *v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 **v53; // rax
  __int64 *v54; // rdi
  _QWORD *v55; // rbx
  __int64 *v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rdx
  _QWORD *v59; // rax
  __int64 v60; // rcx
  ThreadRestrictNewHandlesRegion *v62; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v65; // [rsp+20h] [rbp-28h] BYREF
  int v66; // [rsp+28h] [rbp-20h]
  int v67; // [rsp+2Ch] [rbp-1Ch]
  __int64 v68; // [rsp+30h] [rbp-18h]
  __int64 *v69; // [rsp+90h] [rbp+48h]
  __int64 v70; // [rsp+98h] [rbp+50h] BYREF
  __int64 v71; // [rsp+A0h] [rbp+58h]
  __int64 *v72; // [rsp+A8h] [rbp+60h]

  v2 = 0;
  v3 = *this;
  v72 = *a2;
  v69 = v3;
  LOWORD(v67) = 0;
  SessionState = W32GetSessionState(this);
  v70 = 0;
  v7 = *(_QWORD *)(SessionState + 88);
  v8 = (unsigned __int16)*(_DWORD *)v3 | (*(_DWORD *)v3 >> 8) & 0xFF0000;
  v68 = v7;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v70);
  if ( !(unsigned __int8)KeIsAttachedProcess(v11, v10)
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v2 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v12 = (v2 + 8) & -(__int64)(v2 != 0);
  if ( v12 )
    v71 = *(_QWORD *)(((v2 + 8) & -(__int64)(v2 != 0)) + 0x40);
  else
    v71 = 0;
  v13 = *(_QWORD *)(v7 + 8);
  v66 = 1;
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, v8);
  v65 = (unsigned int *)v14;
  v15 = (unsigned int *)v14;
  if ( v14 )
  {
    _m_prefetchw((const void *)(v14 + 8));
    v16 = *(_DWORD *)(v14 + 8) & 0xFFFFFFFE;
    if ( v16 == (v70 & 0xFFFFFFFC) || !v16 || v71 && v16 == (unsigned int)UMPDGetThreadClientPID(v12) )
    {
      if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v7 + 8) + 96LL))(
                         *(_QWORD *)(v7 + 8),
                         *v15)
                     + 14)
          & 0x20) == 0
        || v12
        && (v62 = *(ThreadRestrictNewHandlesRegion **)(v12 + 328)) != 0
        && *((_BYTE *)v62 + 80)
        && ThreadRestrictNewHandlesRegion::InRegion(v62, v8) )
      {
LABEL_9:
        v17 = v72;
        v18 = *((_WORD *)v72 + 7);
        v19 = *v72;
        v20 = *((_WORD *)v69 + 7) & 0x70;
        v21 = *((_DWORD *)v72 + 2);
        v22 = *((_WORD *)v69 + 7) & 0x80;
        v23 = v72[2];
        v67 = *((_DWORD *)v72 + 3);
        v24 = v18 & 0x80u | v20;
        *((_WORD *)v72 + 7) = v24;
        v25 = *(_QWORD *)v69;
        *((_WORD *)v69 + 7) = v18 & 0x70 | v22;
        *v17 = v25;
        *((_WORD *)v17 + 6) = *((_WORD *)v69 + 6);
        *((_DWORD *)v17 + 2) = v69[2];
        v17[2] = *((_QWORD *)v69 + 2);
        v26 = W32GetSessionState(v24);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(*(_QWORD *)(v26 + 88) + 8LL) + 104LL))(
          *(_QWORD *)(*(_QWORD *)(v26 + 88) + 8LL),
          (unsigned __int16)*v69 | (*v69 >> 8) & 0xFF0000u,
          v72);
        v27 = v67;
        *(_QWORD *)v69 = v19;
        *((_WORD *)v69 + 6) = v27;
        v69[2] = v21;
        *((_QWORD *)v69 + 2) = v23;
        v28 = *(__int64 **)(v7 + 8);
        v29 = *v28;
        v30 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v28 + 96))(v28, *v15);
        (*(void (__fastcall **)(__int64 *, __int64))(v29 + 48))(v28, v30);
        KeLeaveCriticalRegion();
        v32 = *this;
        v33 = *((unsigned int *)*this + 19);
        *((_DWORD *)*this + 19) = *((_DWORD *)*a2 + 19);
        *((_DWORD *)*a2 + 19) = v33;
        v34 = *this + 10;
        v35 = *a2 + 10;
        v36 = *v34;
        v37 = (_QWORD *)*v35;
        if ( *this != (__int64 *)-80LL )
        {
          if ( *(__int64 **)(v36 + 8) != v34 )
            goto LABEL_25;
          v38 = (__int64 **)(*this)[11];
          if ( *v38 != v34 )
            goto LABEL_25;
          *v38 = (__int64 *)v36;
          *(_QWORD *)(v36 + 8) = v38;
          v34[1] = (__int64)v34;
          *v34 = (__int64)v34;
        }
        v39 = *a2 + 10;
        if ( *a2 != (__int64 *)-80LL )
        {
          v40 = *v39;
          if ( *(_QWORD **)(*v39 + 8LL) != v39 )
            goto LABEL_25;
          v32 = (__int64 *)(*a2)[11];
          if ( (_QWORD *)*v32 != v39 )
            goto LABEL_25;
          *v32 = v40;
          *(_QWORD *)(v40 + 8) = v32;
          v39[1] = v39;
          *v39 = v39;
        }
        v41 = *this;
        *this = *a2;
        *a2 = v41;
        CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v41, v32, v33, v31);
        if ( !CurrentThreadWin32Thread )
          return 1;
        v46 = *CurrentThreadWin32Thread;
        v47 = v46 + 8;
        if ( (-(__int64)(v46 != 0) & (v46 + 8)) == 0 )
          return 1;
        if ( (__int64 *)v36 != v34 )
        {
          v48 = *this;
          v49 = *this + 10;
          if ( *this != (__int64 *)-80LL )
          {
            v50 = (__int64 *)PsGetCurrentThreadWin32Thread(v47, v43, v44, v45);
            if ( v50 )
              v51 = *v50;
            else
              v51 = 0;
            v52 = v51 + 8;
            v49[2] = (__int64)v48;
            v47 = -v51;
            v49[3] = (__int64)CleanUpRegion;
            v43 = v52 & -(__int64)(v47 != 0);
            if ( v43 )
            {
              v53 = (__int64 **)(v43 + 88);
              v47 = *(_QWORD *)(v43 + 88);
              if ( *(_QWORD *)(v47 + 8) != v43 + 88 )
                goto LABEL_25;
              *v49 = v47;
              v49[1] = (__int64)v53;
              *(_QWORD *)(v47 + 8) = v49;
              *v53 = v49;
            }
            else
            {
              v49[1] = (__int64)v49;
              *v49 = (__int64)v49;
            }
          }
        }
        if ( v37 == v35 )
          return 1;
        v54 = *a2;
        v55 = *a2 + 10;
        if ( *a2 == (__int64 *)-80LL )
          return 1;
        v56 = (__int64 *)PsGetCurrentThreadWin32Thread(v47, v43, v44, v45);
        if ( v56 )
          v57 = *v56;
        else
          v57 = 0;
        v55[2] = v54;
        v55[3] = CleanUpRegion;
        v58 = (v57 + 8) & -(__int64)(v57 != 0);
        if ( !v58 )
        {
          v55[1] = v55;
          *v55 = v55;
          return 1;
        }
        v59 = (_QWORD *)(v58 + 88);
        v60 = *(_QWORD *)(((v57 + 8) & -(__int64)(v57 != 0)) + 0x58);
        if ( *(_QWORD *)(v60 + 8) == v58 + 88 )
        {
          *v55 = v60;
          v55[1] = v59;
          *(_QWORD *)(v60 + 8) = v55;
          *v59 = v55;
          return 1;
        }
LABEL_25:
        __fastfail(3u);
      }
      LOBYTE(v67) = 1;
    }
    HANDLELOCK::vUnlock((HANDLELOCK *)&v65);
    if ( v66 )
    {
      v7 = v68;
      v15 = v65;
      goto LABEL_9;
    }
  }
  else
  {
    v66 = 0;
    KeLeaveCriticalRegion();
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v65);
  return 0;
}

```

## disassembly

```asm
0x140076d10  push    rbp
0x140076d12  push    rbx
0x140076d13  push    rsi
0x140076d14  push    rdi
0x140076d15  push    r12
0x140076d17  push    r13
0x140076d19  push    r14
0x140076d1b  push    r15
0x140076d1d  mov     rbp, rsp
0x140076d20  sub     rsp, 48h
0x140076d24  mov     r8, [rdx]
0x140076d27  xor     esi, esi
0x140076d29  mov     rbx, [rcx]
0x140076d2c  mov     r15, rdx
0x140076d2f  mov     [rbp+arg_18], r8
0x140076d33  mov     r12, rcx
0x140076d36  mov     [rbp+arg_0], rbx
0x140076d3a  mov     word ptr [rbp+var_1C], si
0x140076d3e  call    cs:__imp_W32GetSessionState
0x140076d45  nop     dword ptr [rax+rax+00h]
0x140076d4a  lea     rcx, [rbp+arg_8]
0x140076d4e  mov     [rbp+arg_8], rsi
0x140076d52  mov     r13, [rax+58h]
0x140076d56  mov     eax, [rbx]
0x140076d58  mov     edi, eax
0x140076d5a  shr     edi, 8
0x140076d5d  movzx   eax, ax
0x140076d60  and     edi, 0FF0000h
0x140076d66  or      edi, eax
0x140076d68  mov     [rbp+var_18], r13
0x140076d6c  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140076d73  nop     dword ptr [rax+rax+00h]
0x140076d78  mov     r14, rax
0x140076d7b  call    cs:__imp_KeIsAttachedProcess
0x140076d82  nop     dword ptr [rax+rax+00h]
0x140076d87  test    al, al
0x140076d89  jnz     loc_14007713E
0x140076d8f  test    r14, r14
0x140076d92  jz      short loc_140076D97
0x140076d94  mov     rsi, [r14]
0x140076d97  lea     rax, [rsi+8]
0x140076d9b  neg     rsi
0x140076d9e  sbb     rbx, rbx
0x140076da1  and     rbx, rax
0x140076da4  jz      loc_14007716D
0x140076daa  mov     rsi, [rbx+40h]
0x140076dae  mov     [rbp+arg_10], rsi
0x140076db2  mov     rcx, [r13+8]
0x140076db6  mov     edx, edi
0x140076db8  mov     [rbp+var_20], 1
0x140076dbf  mov     rax, [rcx]
0x140076dc2  mov     rax, [rax+28h]
0x140076dc6  call    _guard_dispatch_icall
0x140076dcb  mov     [rbp+var_28], rax
0x140076dcf  mov     r14, rax
0x140076dd2  test    rax, rax
0x140076dd5  jz      loc_1400770CA
0x140076ddb  prefetchw byte ptr [rax+8]
0x140076ddf  mov     esi, [rax+8]
0x140076de2  mov     eax, dword ptr [rbp+arg_8]
0x140076de5  and     esi, 0FFFFFFFEh
0x140076de8  and     eax, 0FFFFFFFCh
0x140076deb  cmp     esi, eax
0x140076ded  jnz     loc_1400770A9
0x140076df3  mov     rcx, [r13+8]
0x140076df7  mov     edx, [r14]
0x140076dfa  mov     rax, [rcx]
0x140076dfd  mov     rax, [rax+60h]
0x140076e01  call    _guard_dispatch_icall
0x140076e06  test    byte ptr [rax+0Eh], 20h
0x140076e0a  jnz     loc_1400770EA
0x140076e10  mov     r10, [rbp+arg_18]
0x140076e14  mov     r11d, 80h
0x140076e1a  mov     r9, [rbp+arg_0]
0x140076e1e  mov     eax, [r10+0Ch]
0x140076e22  movzx   edx, word ptr [r9+0Eh]
0x140076e27  movzx   r8d, word ptr [r10+0Eh]
0x140076e2c  movzx   ecx, dx
0x140076e2f  mov     rdi, [r10]
0x140076e32  and     cx, 70h
0x140076e36  mov     esi, [r10+8]
0x140076e3a  and     dx, r11w
0x140076e3e  mov     rbx, [r10+10h]
0x140076e42  mov     [rbp+var_1C], eax
0x140076e45  movzx   eax, r8w
0x140076e49  and     ax, r11w
0x140076e4d  and     r8w, 70h
0x140076e52  or      cx, ax
0x140076e55  or      dx, r8w
0x140076e59  mov     [r10+0Eh], cx
0x140076e5e  mov     rax, [r9]
0x140076e61  mov     [r9+0Eh], dx
0x140076e66  mov     [r10], rax
0x140076e69  movzx   eax, word ptr [r9+0Ch]
0x140076e6e  xchg    ax, [r10+0Ch]
0x140076e73  mov     eax, [r9+8]
0x140076e77  mov     [r10+8], eax
0x140076e7b  mov     rax, [r9+10h]
0x140076e7f  mov     [r10+10h], rax
0x140076e83  call    cs:__imp_W32GetSessionState
0x140076e8a  nop     dword ptr [rax+rax+00h]
0x140076e8f  mov     r8, [rbp+arg_18]
0x140076e93  mov     rcx, [rax+58h]
0x140076e97  mov     rax, [rbp+arg_0]
0x140076e9b  mov     rcx, [rcx+8]
0x140076e9f  mov     eax, [rax]
0x140076ea1  mov     edx, eax
0x140076ea3  shr     edx, 8
0x140076ea6  movzx   eax, ax
0x140076ea9  and     edx, 0FF0000h
0x140076eaf  mov     r9, [rcx]
0x140076eb2  or      edx, eax
0x140076eb4  mov     rax, [r9+68h]
0x140076eb8  call    _guard_dispatch_icall
0x140076ebd  movzx   eax, word ptr [rbp+var_1C]
0x140076ec1  mov     rcx, [rbp+arg_0]
0x140076ec5  mov     [rcx], rdi
0x140076ec8  xchg    ax, [rcx+0Ch]
0x140076ecc  mov     [rcx+8], esi
0x140076ecf  mov     [rcx+10h], rbx
0x140076ed3  mov     rdi, [r13+8]
0x140076ed7  mov     edx, [r14]
0x140076eda  mov     rcx, rdi
0x140076edd  mov     rbx, [rdi]
0x140076ee0  mov     rax, [rbx+60h]
0x140076ee4  call    _guard_dispatch_icall
0x140076ee9  mov     rdx, rax
0x140076eec  mov     rcx, rdi
0x140076eef  mov     rax, [rbx+30h]
0x140076ef3  call    _guard_dispatch_icall
0x140076ef8  call    cs:__imp_KeLeaveCriticalRegion
0x140076eff  nop     dword ptr [rax+rax+00h]
0x140076f04  mov     rax, [r15]
0x140076f07  mov     rdx, [r12]
0x140076f0b  mov     ecx, [rax+4Ch]
0x140076f0e  mov     r8d, [rdx+4Ch]
0x140076f12  mov     [rdx+4Ch], ecx
0x140076f15  mov     rax, [r15]
0x140076f18  mov     [rax+4Ch], r8d
0x140076f1c  mov     rbx, [r12]
0x140076f20  mov     rsi, [r15]
0x140076f23  add     rbx, 50h ; 'P'
0x140076f27  add     rsi, 50h ; 'P'
0x140076f2b  mov     rdi, [rbx]
0x140076f2e  mov     r14, [rsi]
0x140076f31  test    rbx, rbx
0x140076f34  jz      short loc_140076F5B
0x140076f36  cmp     [rdi+8], rbx
0x140076f3a  jnz     loc_14007701E
0x140076f40  mov     rax, [rbx+8]
0x140076f44  cmp     [rax], rbx
0x140076f47  jnz     loc_14007701E
0x140076f4d  mov     [rax], rdi
0x140076f50  mov     [rdi+8], rax
0x140076f54  mov     [rbx+8], rbx
0x140076f58  mov     [rbx], rbx
0x140076f5b  mov     rax, [r15]
0x140076f5e  add     rax, 50h ; 'P'
0x140076f62  jz      short loc_140076F8C
0x140076f64  mov     rcx, [rax]
0x140076f67  cmp     [rcx+8], rax
0x140076f6b  jnz     loc_14007701E
0x140076f71  mov     rdx, [rax+8]
0x140076f75  cmp     [rdx], rax
0x140076f78  jnz     loc_14007701E
0x140076f7e  mov     [rdx], rcx
0x140076f81  mov     [rcx+8], rdx
0x140076f85  mov     [rax+8], rax
0x140076f89  mov     [rax], rax
0x140076f8c  mov     rax, [r15]
0x140076f8f  mov     rcx, [r12]
0x140076f93  mov     [r12], rax
0x140076f97  mov     [r15], rcx
0x140076f9a  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140076fa1  nop     dword ptr [rax+rax+00h]
0x140076fa6  test    rax, rax
0x140076fa9  jz      loc_140077092
0x140076faf  mov     rax, [rax]
0x140076fb2  lea     rcx, [rax+8]
0x140076fb6  neg     rax
0x140076fb9  sbb     rax, rax
0x140076fbc  test    rcx, rax
0x140076fbf  jz      loc_140077092
0x140076fc5  lea     r13, ?CleanUpRegion@@YAXPEAVREGION@@@Z; CleanUpRegion(REGION *)
0x140076fcc  cmp     rdi, rbx
0x140076fcf  jz      short loc_140077033
0x140076fd1  mov     rdi, [r12]
0x140076fd5  lea     rbx, [rdi+50h]
0x140076fd9  test    rbx, rbx
0x140076fdc  jz      short loc_140077033
0x140076fde  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140076fe5  nop     dword ptr [rax+rax+00h]
0x140076fea  test    rax, rax
0x140076fed  jz      loc_140077130
0x140076ff3  mov     rcx, [rax]
0x140076ff6  lea     rax, [rcx+8]
0x140076ffa  mov     [rbx+10h], rdi
0x140076ffe  neg     rcx
0x140077001  mov     [rbx+18h], r13
0x140077005  sbb     rdx, rdx
0x140077008  and     rdx, rax
0x14007700b  jz      loc_14007717A
0x140077011  lea     rax, [rdx+58h]
0x140077015  mov     rcx, [rax]
0x140077018  cmp     [rcx+8], rax
0x14007701c  jz      short loc_140077025
0x14007701e  mov     ecx, 3
0x140077023  int     29h; Win8: RtlFailFast(ecx)
0x140077025  mov     [rbx], rcx
0x140077028  mov     [rbx+8], rax
0x14007702c  mov     [rcx+8], rbx
0x140077030  mov     [rax], rbx
0x140077033  cmp     r14, rsi
0x140077036  jz      short loc_140077092
0x140077038  mov     rdi, [r15]
0x14007703b  lea     rbx, [rdi+50h]
0x14007703f  test    rbx, rbx
0x140077042  jz      short loc_140077092
0x140077044  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14007704b  nop     dword ptr [rax+rax+00h]
0x140077050  test    rax, rax
0x140077053  jz      loc_140077137
0x140077059  mov     rcx, [rax]
0x14007705c  lea     rax, [rcx+8]
0x140077060  mov     [rbx+10h], rdi
0x140077064  neg     rcx
0x140077067  mov     [rbx+18h], r13
0x14007706b  sbb     rdx, rdx
0x14007706e  and     rdx, rax
0x140077071  jz      loc_140077186
0x140077077  lea     rax, [rdx+58h]
0x14007707b  mov     rcx, [rax]
0x14007707e  cmp     [rcx+8], rax
0x140077082  jnz     short loc_14007701E
0x140077084  mov     [rbx], rcx
0x140077087  mov     [rbx+8], rax
0x14007708b  mov     [rcx+8], rbx
0x14007708f  mov     [rax], rbx
0x140077092  mov     eax, 1
0x140077097  add     rsp, 48h
0x14007709b  pop     r15
0x14007709d  pop     r14
0x14007709f  pop     r13
0x1400770a1  pop     r12
0x1400770a3  pop     rdi
0x1400770a4  pop     rsi
0x1400770a5  pop     rbx
0x1400770a6  pop     rbp
0x1400770a7  retn
0x1400770a9  test    esi, esi
0x1400770ab  jz      loc_140076DF3
0x1400770b1  cmp     [rbp+arg_10], 0
0x1400770b6  jz      short loc_140077114
0x1400770b8  mov     rcx, rbx
0x1400770bb  call    UMPDGetThreadClientPID
0x1400770c0  cmp     esi, eax
0x1400770c2  jz      loc_140076DF3
0x1400770c8  jmp     short loc_140077114
0x1400770ca  mov     [rbp+var_20], 0
0x1400770d1  call    cs:__imp_KeLeaveCriticalRegion
0x1400770d8  nop     dword ptr [rax+rax+00h]
0x1400770dd  lea     rcx, [rbp+var_28]; this
0x1400770e1  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x1400770e6  xor     eax, eax
0x1400770e8  jmp     short loc_140077097
0x1400770ea  test    rbx, rbx
0x1400770ed  jz      short loc_140077110
0x1400770ef  mov     rcx, [rbx+148h]; this
0x1400770f6  test    rcx, rcx
0x1400770f9  jz      short loc_140077110
0x1400770fb  cmp     byte ptr [rcx+50h], 0
0x1400770ff  jz      short loc_140077110
0x140077101  mov     edx, edi; unsigned int
0x140077103  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x140077108  test    al, al
0x14007710a  jnz     loc_140076E10
0x140077110  mov     byte ptr [rbp+var_1C], 1
0x140077114  lea     rcx, [rbp+var_28]; this
0x140077118  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14007711d  cmp     [rbp+var_20], 0
0x140077121  jz      short loc_1400770DD
0x140077123  mov     r13, [rbp+var_18]
0x140077127  mov     r14, [rbp+var_28]
0x14007712b  jmp     loc_140076E10
0x140077130  xor     ecx, ecx
0x140077132  jmp     loc_140076FF6
0x140077137  xor     ecx, ecx
0x140077139  jmp     loc_14007705C
0x14007713e  call    W32GetCurrentWin32kSessionId
0x140077143  mov     ebx, eax
0x140077145  call    cs:__imp_PsGetCurrentThreadProcess
0x14007714c  nop     dword ptr [rax+rax+00h]
0x140077151  mov     rcx, rax
0x140077154  call    cs:__imp_PsGetProcessSessionIdEx
0x14007715b  nop     dword ptr [rax+rax+00h]
0x140077160  cmp     ebx, eax
0x140077162  jz      loc_140076D8F
0x140077168  jmp     loc_140076D97
0x14007716d  mov     [rbp+arg_10], 0
0x140077175  jmp     loc_140076DB2
  ... truncated ...
```
