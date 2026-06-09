# CRecalcState::CreateRecalcState(tagWND const *,CMonitorTopology *,StartRecalcReason,CRecalcState::ProcessingDecision *)

- ea: `0x140172e38`
- end: `0x1401735e9`
- name: `?CreateRecalcState@CRecalcState@@SAPEAV1@PEBUtagWND@@PEAVCMonitorTopology@@W4StartRecalcReason@@PEAW4ProcessingDecision@1@@Z`
- size: `1969`
- prototype: `CRecalcState *__fastcall(__int64, __int64, unsigned int, _DWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140173cd0`
- `0x1402e074c`

## callees

- `0x140092c40`
- `0x140095650`
- `0x1400dd43c`
- `0x140172318`
- `0x140172e38`
- `0x14017374c`
- `0x14017385c`
- `0x140174a18`
- `0x140175e00`
- `0x140184ce8`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140173014`
- `ntoskrnl!PsGetThreadId` at `0x14017315b`
- `ntoskrnl!PsGetThreadId` at `0x140173207`
- `ntoskrnl!PsGetThreadId` at `0x1401732c8`
- `ntoskrnl!PsGetThreadId` at `0x14017336b`
- `ntoskrnl!PsGetThreadId` at `0x1401733ca`
- `ntoskrnl!PsGetThreadId` at `0x14017343a`
- `ntoskrnl!PsGetThreadId` at `0x1401734f9`
- `ntoskrnl!PsGetThreadId` at `0x140173014`
- `ntoskrnl!PsGetThreadId` at `0x14017315b`
- `ntoskrnl!PsGetThreadId` at `0x140173207`
- `ntoskrnl!PsGetThreadId` at `0x1401732c8`
- `ntoskrnl!PsGetThreadId` at `0x14017336b`
- `ntoskrnl!PsGetThreadId` at `0x1401733ca`
- `ntoskrnl!PsGetThreadId` at `0x14017343a`
- `ntoskrnl!PsGetThreadId` at `0x1401734f9`
- `win32kbase!Win32AllocPoolZInit` at `0x140172e72`
- `win32kbase!Win32AllocPoolZInit` at `0x140172e72`
- `WIN32K!W32GetUserSessionState` at `0x140173026`
- `WIN32K!W32GetUserSessionState` at `0x14017316d`
- `WIN32K!W32GetUserSessionState` at `0x140173219`
- `WIN32K!W32GetUserSessionState` at `0x1401732da`
- `WIN32K!W32GetUserSessionState` at `0x14017337d`
- `WIN32K!W32GetUserSessionState` at `0x1401733dc`
- `WIN32K!W32GetUserSessionState` at `0x14017344c`
- `WIN32K!W32GetUserSessionState` at `0x14017350b`
- `WIN32K!W32GetUserSessionState` at `0x14017359b`
- `WIN32K!W32GetUserSessionState` at `0x140173026`
- `WIN32K!W32GetUserSessionState` at `0x14017316d`
- `WIN32K!W32GetUserSessionState` at `0x140173219`
- `WIN32K!W32GetUserSessionState` at `0x1401732da`
- `WIN32K!W32GetUserSessionState` at `0x14017337d`
- `WIN32K!W32GetUserSessionState` at `0x1401733dc`
- `WIN32K!W32GetUserSessionState` at `0x14017344c`
- `WIN32K!W32GetUserSessionState` at `0x14017350b`
- `WIN32K!W32GetUserSessionState` at `0x14017359b`

## pseudocode

```c
CRecalcState *__fastcall CRecalcState::CreateRecalcState(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  CRecalcState *v12; // rbp
  char v13; // si
  char v14; // r14
  bool v16; // si
  bool v17; // bl
  __int16 WindowDpiLastNotify; // ax
  __int64 v19; // rdx
  char v20; // si
  char v21; // bp
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // edx
  int v27; // r8d
  __int64 v28; // r9
  char v29; // r15
  char v30; // r14
  char v31; // si
  char v32; // r14
  unsigned __int8 v33; // al
  __int64 v34; // rdi
  char v35; // bl
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rax
  int v41; // r8d
  int v42; // edx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  int v51; // edx
  int v52; // r8d
  __int64 v53; // r9
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
  unsigned __int8 v58; // al
  __int64 v59; // rdi
  char v60; // bl
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 UserSessionState; // rax
  int v66; // r8d
  int v67; // edx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r9
  char v72; // si
  char v73; // r14
  unsigned __int8 v74; // al
  __int64 v75; // rdi
  char v76; // bl
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rax
  int v82; // r8d
  int v83; // edx
  __int64 v84; // rax
  int v85; // r8d
  int v86; // edx
  __int16 v87; // [rsp+30h] [rbp-68h]
  __int16 v88; // [rsp+30h] [rbp-68h]
  __int64 v89; // [rsp+40h] [rbp-58h]
  __int64 v90; // [rsp+40h] [rbp-58h]
  char ThreadId; // [rsp+48h] [rbp-50h]
  char v92; // [rsp+48h] [rbp-50h]

  *a4 = 0;
  if ( !(unsigned int)IsImmersiveBand(a1) )
    goto LABEL_2;
  if ( !MonitorFromRect((INT *)(*(_QWORD *)(a1 + 40) + 88LL), 0, *(_DWORD *)(*(_QWORD *)(a1 + 40) + 288LL)) )
  {
    v20 = 1;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || (v21 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      v21 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || !*((_WORD *)WPP_GLOBAL_Control + 36) )
    {
      v20 = 0;
    }
    if ( !v21 && !v20 )
      return 0;
    ThreadId = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(a1 + 16));
    v89 = *(_QWORD *)a1;
    v28 = *(_QWORD *)(W32GetUserSessionState(v44, v43, v45, v46) + 69152);
    v87 = 21;
LABEL_34:
    LOBYTE(v27) = v20;
    LOBYTE(v26) = v21;
    WPP_RECORDER_AND_TRACE_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v26,
      v27,
      v28,
      5,
      7,
      v87,
      (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
      v89,
      ThreadId);
    return 0;
  }
  WindowDpiLastNotify = GetWindowDpiLastNotify(a1);
  if ( *(_WORD *)(*(_QWORD *)(v19 + 40) + 60LL) == WindowDpiLastNotify )
  {
    v20 = 1;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || (v21 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      v21 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || !*((_WORD *)WPP_GLOBAL_Control + 36) )
    {
      v20 = 0;
    }
    if ( !v21 && !v20 )
      return 0;
    ThreadId = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(a1 + 16));
    v89 = *(_QWORD *)a1;
    v28 = *(_QWORD *)(W32GetUserSessionState(v23, v22, v24, v25) + 69152);
    v87 = 22;
    goto LABEL_34;
  }
LABEL_2:
  v8 = Win32AllocPoolZInit(80, 1920168789);
  if ( v8 )
  {
    v12 = (CRecalcState *)CRecalcState::CRecalcState(v8, a1, a2, a3);
    if ( v12 )
    {
      if ( (unsigned int)IsImmersiveBand(a1) )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v29 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v29 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v30 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v30 = 0;
        }
        if ( !v29 && !v30 )
          goto LABEL_42;
        v92 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(a1 + 16));
        v90 = *(_QWORD *)a1;
        v53 = *(_QWORD *)(W32GetUserSessionState(v48, v47, v49, v50) + 69152);
        v88 = 24;
      }
      else if ( a3 == 4 )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v29 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v29 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v30 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v30 = 0;
        }
        if ( !v29 && !v30 )
          goto LABEL_42;
        v92 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(a1 + 16));
        v90 = *(_QWORD *)a1;
        v53 = *(_QWORD *)(W32GetUserSessionState(v55, v54, v56, v57) + 69152);
        v88 = 25;
      }
      else
      {
        if ( (unsigned __int8)CRecalcState::ShouldDeferRecalc(v12, a1, 0) )
        {
          v13 = 1;
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
            || (v14 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
          {
            v14 = 0;
          }
          if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
            || !*((_WORD *)WPP_GLOBAL_Control + 36) )
          {
            v13 = 0;
          }
          if ( v14 || v13 )
          {
            v58 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(a1 + 16));
            v59 = *(_QWORD *)a1;
            v60 = v58;
            UserSessionState = W32GetUserSessionState(v62, v61, v63, v64);
            LOBYTE(v66) = v13;
            LOBYTE(v67) = v14;
            WPP_RECORDER_AND_TRACE_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v67,
              v66,
              *(_QWORD *)(UserSessionState + 69152),
              5,
              7,
              26,
              (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
              v59,
              v60);
          }
          *a4 = 2;
          return v12;
        }
        if ( !CRecalcState::NeedsMigration(v12, (const struct tagWND *)a1) )
        {
          if ( CRecalcState::ShouldStoreAfterProcessing(v12, (const struct tagWND *)a1) )
          {
            v72 = 1;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
              || (v73 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v73 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || !*((_WORD *)WPP_GLOBAL_Control + 36) )
            {
              v72 = 0;
            }
            if ( v73 || v72 )
            {
              v74 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(a1 + 16));
              v75 = *(_QWORD *)a1;
              v76 = v74;
              v81 = W32GetUserSessionState(v78, v77, v79, v80);
              LOBYTE(v82) = v72;
              LOBYTE(v83) = v73;
              WPP_RECORDER_AND_TRACE_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v83,
                v82,
                *(_QWORD *)(v81 + 69152),
                5,
                7,
                28,
                (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
                v75,
                v76);
            }
            *a4 = 3;
          }
          else
          {
            v31 = 1;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
              || (v32 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v32 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || !*((_WORD *)WPP_GLOBAL_Control + 36) )
            {
              v31 = 0;
            }
            if ( v32 || v31 )
            {
              v33 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(a1 + 16));
              v34 = *(_QWORD *)a1;
              v35 = v33;
              v40 = W32GetUserSessionState(v37, v36, v38, v39);
              LOBYTE(v41) = v31;
              LOBYTE(v42) = v32;
              WPP_RECORDER_AND_TRACE_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v42,
                v41,
                *(_QWORD *)(v40 + 69152),
                5,
                7,
                29,
                (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
                v34,
                v35);
            }
          }
          return v12;
        }
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v29 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v29 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v30 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v30 = 0;
        }
        if ( !v29 && !v30 )
        {
LABEL_42:
          *a4 = 1;
          return v12;
        }
        v92 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(a1 + 16));
        v90 = *(_QWORD *)a1;
        v53 = *(_QWORD *)(W32GetUserSessionState(v69, v68, v70, v71) + 69152);
        v88 = 27;
      }
      LOBYTE(v52) = v30;
      LOBYTE(v51) = v29;
      WPP_RECORDER_AND_TRACE_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v51,
        v52,
        v53,
        5,
        7,
        v88,
        (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
        v90,
        v92);
      goto LABEL_42;
    }
  }
  v16 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
  v17 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v16 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v84 = W32GetUserSessionState(WPP_GLOBAL_Control, v9, v10, v11);
    LOBYTE(v85) = v17;
    LOBYTE(v86) = v16;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v86,
      v85,
      *(_QWORD *)(v84 + 69152),
      2,
      7,
      23,
      (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140172e38  push    rbx
0x140172e3a  push    rbp
0x140172e3b  push    rsi
0x140172e3c  push    rdi
0x140172e3d  push    r12
0x140172e3f  push    r13
0x140172e41  push    r14
0x140172e43  push    r15
0x140172e45  sub     rsp, 58h
0x140172e49  xor     r13d, r13d
0x140172e4c  mov     r12, r9
0x140172e4f  mov     [r9], r13d
0x140172e52  mov     ebx, r8d
0x140172e55  mov     rsi, rdx
0x140172e58  mov     rdi, rcx
0x140172e5b  call    IsImmersiveBand
0x140172e60  test    eax, eax
0x140172e62  jnz     loc_140172F82
0x140172e68  mov     edx, 72737355h
0x140172e6d  mov     ecx, 50h ; 'P'
0x140172e72  call    cs:__imp_Win32AllocPoolZInit
0x140172e79  nop     dword ptr [rax+rax+00h]
0x140172e7e  test    rax, rax
0x140172e81  jz      loc_140172F42
0x140172e87  mov     r9d, ebx
0x140172e8a  mov     r8, rsi
0x140172e8d  mov     rdx, rdi
0x140172e90  mov     rcx, rax
0x140172e93  call    ??0CRecalcState@@AEAA@PEBUtagWND@@PEAVCMonitorTopology@@W4StartRecalcReason@@@Z; CRecalcState::CRecalcState(tagWND const *,CMonitorTopology *,StartRecalcReason)
0x140172e98  mov     rbp, rax
0x140172e9b  test    rax, rax
0x140172e9e  jz      loc_140172F42
0x140172ea4  mov     rcx, rdi
0x140172ea7  call    IsImmersiveBand
0x140172eac  test    eax, eax
0x140172eae  jnz     loc_14017326B
0x140172eb4  cmp     ebx, 4
0x140172eb7  jz      loc_14017330E
0x140172ebd  xor     r8d, r8d
0x140172ec0  mov     rdx, rdi
0x140172ec3  mov     rcx, rbp
0x140172ec6  call    ?ShouldDeferRecalc@CRecalcState@@QEBA_NPEBUtagWND@@W4ShouldDeferRecalcOption@1@@Z; CRecalcState::ShouldDeferRecalc(tagWND const *,CRecalcState::ShouldDeferRecalcOption)
0x140172ecb  test    al, al
0x140172ecd  jz      loc_14017307D
0x140172ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x140172eda  lea     rax, WPP_GLOBAL_Control
0x140172ee1  mov     esi, 1
0x140172ee6  cmp     rcx, rax
0x140172ee9  jz      short loc_140172EF6
0x140172eeb  mov     eax, [rcx+2Ch]
0x140172eee  test    al, 40h
0x140172ef0  jnz     loc_1401733B1
0x140172ef6  mov     r14b, r13b
0x140172ef9  lea     rax, WPP_RECORDER_INITIALIZED
0x140172f00  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140172f07  jz      short loc_140172F10
0x140172f09  cmp     [rcx+48h], r13w
0x140172f0e  jnz     short loc_140172F13
0x140172f10  mov     sil, r13b
0x140172f13  test    r14b, r14b
0x140172f16  jnz     loc_1401733C3
0x140172f1c  test    sil, sil
0x140172f1f  jnz     loc_1401733C3
0x140172f25  mov     dword ptr [r12], 2
0x140172f2d  mov     rax, rbp
0x140172f30  add     rsp, 58h
0x140172f34  pop     r15
0x140172f36  pop     r14
0x140172f38  pop     r13
0x140172f3a  pop     r12
0x140172f3c  pop     rdi
0x140172f3d  pop     rsi
0x140172f3e  pop     rbp
0x140172f3f  pop     rbx
0x140172f40  retn
0x140172f42  mov     rcx, cs:WPP_GLOBAL_Control
0x140172f49  lea     rax, WPP_GLOBAL_Control
0x140172f50  cmp     rcx, rax
0x140172f53  jnz     loc_14017357C
0x140172f59  mov     sil, r13b
0x140172f5c  lea     rax, WPP_RECORDER_INITIALIZED
0x140172f63  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140172f6a  setnz   bl
0x140172f6d  test    sil, sil
0x140172f70  jnz     loc_14017359B
0x140172f76  test    bl, bl
0x140172f78  jnz     loc_14017359B
0x140172f7e  xor     eax, eax
0x140172f80  jmp     short loc_140172F30
0x140172f82  mov     r8, [rdi+28h]
0x140172f86  xor     edx, edx
0x140172f88  lea     rcx, [r8+58h]
0x140172f8c  mov     r8d, [r8+120h]
0x140172f93  call    _MonitorFromRect
0x140172f98  mov     rdx, rax
0x140172f9b  test    rax, rax
0x140172f9e  jz      loc_1401731C4
0x140172fa4  mov     rcx, rdi
0x140172fa7  call    GetWindowDpiLastNotify
0x140172fac  mov     rcx, [rdx+28h]
0x140172fb0  cmp     [rcx+3Ch], ax
0x140172fb4  jnz     loc_140172E68
0x140172fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140172fc1  lea     rax, WPP_GLOBAL_Control
0x140172fc8  mov     esi, 1
0x140172fcd  cmp     rcx, rax
0x140172fd0  jz      short loc_140172FE2
0x140172fd2  mov     eax, [rcx+2Ch]
0x140172fd5  test    al, 40h
0x140172fd7  jz      short loc_140172FE2
0x140172fd9  cmp     byte ptr [rcx+29h], 5
0x140172fdd  mov     bpl, sil
0x140172fe0  jnb     short loc_140172FE5
0x140172fe2  mov     bpl, r13b
0x140172fe5  lea     rax, WPP_RECORDER_INITIALIZED
0x140172fec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140172ff3  jz      short loc_140172FFC
0x140172ff5  cmp     [rcx+48h], r13w
0x140172ffa  jnz     short loc_140172FFF
0x140172ffc  mov     sil, r13b
0x140172fff  test    bpl, bpl
0x140173002  jnz     short loc_14017300D
0x140173004  test    sil, sil
0x140173007  jz      loc_140172F7E
0x14017300d  mov     rcx, [rdi+10h]
0x140173011  mov     rcx, [rcx]; Thread
0x140173014  call    cs:__imp_PsGetThreadId
0x14017301b  nop     dword ptr [rax+rax+00h]
0x140173020  mov     rdi, [rdi]
0x140173023  mov     rbx, rax
0x140173026  call    cs:__imp_W32GetUserSessionState
0x14017302d  nop     dword ptr [rax+rax+00h]
0x140173032  mov     dword ptr [rsp+98h+var_50], ebx
0x140173036  mov     [rsp+98h+var_58], rdi
0x14017303b  mov     r9, [rax+10E20h]
0x140173042  lea     rax, WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids
0x140173049  mov     [rsp+98h+var_60], rax
0x14017304e  mov     [rsp+98h+var_68], 16h
0x140173055  mov     rcx, cs:WPP_GLOBAL_Control
0x14017305c  mov     r8b, sil
0x14017305f  mov     [rsp+98h+var_70], 7
0x140173067  mov     dl, bpl
0x14017306a  mov     [rsp+98h+var_78], 5
0x14017306f  mov     rcx, [rcx+18h]
0x140173073  call    WPP_RECORDER_AND_TRACE_SF_qD
0x140173078  jmp     loc_140172F7E
0x14017307d  mov     rdx, rdi; struct tagWND *
0x140173080  mov     rcx, rbp; this
0x140173083  call    ?NeedsMigration@CRecalcState@@AEBA_NPEBUtagWND@@@Z; CRecalcState::NeedsMigration(tagWND const *)
0x140173088  test    al, al
0x14017308a  jz      short loc_1401730F3
0x14017308c  mov     rcx, cs:WPP_GLOBAL_Control
0x140173093  lea     rax, WPP_GLOBAL_Control
0x14017309a  mov     esi, 1
0x14017309f  cmp     rcx, rax
0x1401730a2  jnz     short loc_1401730D5
0x1401730a4  mov     r15b, r13b
0x1401730a7  lea     rax, WPP_RECORDER_INITIALIZED
0x1401730ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401730b5  jnz     short loc_1401730E7
0x1401730b7  mov     r14b, r13b
0x1401730ba  test    r15b, r15b
0x1401730bd  jnz     loc_140173433
0x1401730c3  test    r14b, r14b
0x1401730c6  jnz     loc_140173433
0x1401730cc  mov     [r12], esi
0x1401730d0  jmp     loc_140172F2D
0x1401730d5  mov     eax, [rcx+2Ch]
0x1401730d8  test    al, 40h
0x1401730da  jz      short loc_1401730A4
0x1401730dc  cmp     byte ptr [rcx+29h], 5
0x1401730e0  mov     r15b, sil
0x1401730e3  jnb     short loc_1401730A7
0x1401730e5  jmp     short loc_1401730A4
0x1401730e7  mov     r14b, sil
0x1401730ea  cmp     [rcx+48h], r13w
0x1401730ef  jnz     short loc_1401730BA
0x1401730f1  jmp     short loc_1401730B7
0x1401730f3  mov     rdx, rdi; struct tagWND *
0x1401730f6  mov     rcx, rbp; this
0x1401730f9  call    ?ShouldStoreAfterProcessing@CRecalcState@@QEBA_NPEBUtagWND@@@Z; CRecalcState::ShouldStoreAfterProcessing(tagWND const *)
0x1401730fe  test    al, al
0x140173100  jnz     loc_1401734A3
0x140173106  mov     rcx, cs:WPP_GLOBAL_Control
0x14017310d  lea     rax, WPP_GLOBAL_Control
0x140173114  mov     esi, 1
0x140173119  cmp     rcx, rax
0x14017311c  jz      short loc_140173129
0x14017311e  mov     eax, [rcx+2Ch]
0x140173121  test    al, 40h
0x140173123  jnz     loc_14017356A
0x140173129  mov     r14b, r13b
0x14017312c  lea     rax, WPP_RECORDER_INITIALIZED
0x140173133  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017313a  jz      short loc_140173143
0x14017313c  cmp     [rcx+48h], r13w
0x140173141  jnz     short loc_140173146
0x140173143  mov     sil, r13b
0x140173146  test    r14b, r14b
0x140173149  jnz     short loc_140173154
0x14017314b  test    sil, sil
0x14017314e  jz      loc_140172F2D
0x140173154  mov     rcx, [rdi+10h]
0x140173158  mov     rcx, [rcx]; Thread
0x14017315b  call    cs:__imp_PsGetThreadId
0x140173162  nop     dword ptr [rax+rax+00h]
0x140173167  mov     rdi, [rdi]
0x14017316a  mov     rbx, rax
0x14017316d  call    cs:__imp_W32GetUserSessionState
0x140173174  nop     dword ptr [rax+rax+00h]
0x140173179  mov     rcx, cs:WPP_GLOBAL_Control
0x140173180  mov     r8b, sil
0x140173183  mov     dword ptr [rsp+98h+var_50], ebx
0x140173187  mov     dl, r14b
0x14017318a  mov     [rsp+98h+var_58], rdi
0x14017318f  mov     r9, [rax+10E20h]
0x140173196  lea     rax, WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids
0x14017319d  mov     rcx, [rcx+18h]
0x1401731a1  mov     [rsp+98h+var_60], rax
0x1401731a6  mov     [rsp+98h+var_68], 1Dh
0x1401731ad  mov     [rsp+98h+var_70], 7
0x1401731b5  mov     [rsp+98h+var_78], 5
0x1401731ba  call    WPP_RECORDER_AND_TRACE_SF_qD
0x1401731bf  jmp     loc_140172F2D
0x1401731c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1401731cb  lea     rax, WPP_GLOBAL_Control
0x1401731d2  mov     esi, 1
0x1401731d7  cmp     rcx, rax
0x1401731da  jnz     short loc_14017324D
0x1401731dc  mov     bpl, r13b
0x1401731df  lea     rax, WPP_RECORDER_INITIALIZED
0x1401731e6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401731ed  jnz     short loc_140173262
0x1401731ef  mov     sil, r13b
0x1401731f2  test    bpl, bpl
0x1401731f5  jnz     short loc_140173200
0x1401731f7  test    sil, sil
0x1401731fa  jz      loc_140172F7E
0x140173200  mov     rcx, [rdi+10h]
0x140173204  mov     rcx, [rcx]; Thread
0x140173207  call    cs:__imp_PsGetThreadId
0x14017320e  nop     dword ptr [rax+rax+00h]
0x140173213  mov     rdi, [rdi]
0x140173216  mov     rbx, rax
0x140173219  call    cs:__imp_W32GetUserSessionState
0x140173220  nop     dword ptr [rax+rax+00h]
0x140173225  mov     dword ptr [rsp+98h+var_50], ebx
0x140173229  mov     [rsp+98h+var_58], rdi
0x14017322e  mov     r9, [rax+10E20h]
0x140173235  lea     rax, WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids
0x14017323c  mov     [rsp+98h+var_60], rax
0x140173241  mov     [rsp+98h+var_68], 15h
0x140173248  jmp     loc_140173055
0x14017324d  mov     eax, [rcx+2Ch]
0x140173250  test    al, 40h
0x140173252  jz      short loc_1401731DC
0x140173254  cmp     byte ptr [rcx+29h], 5
0x140173258  mov     bpl, sil
0x14017325b  jnb     short loc_1401731DF
0x14017325d  jmp     loc_1401731DC
0x140173262  cmp     [rcx+48h], r13w
0x140173267  jnz     short loc_1401731F2
0x140173269  jmp     short loc_1401731EF
0x14017326b  mov     rcx, cs:WPP_GLOBAL_Control
0x140173272  lea     rax, WPP_GLOBAL_Control
0x140173279  mov     esi, 1
0x14017327e  cmp     rcx, rax
0x140173281  jz      short loc_140173293
0x140173283  mov     eax, [rcx+2Ch]
0x140173286  test    al, 40h
0x140173288  jz      short loc_140173293
0x14017328a  cmp     byte ptr [rcx+29h], 5
0x14017328e  mov     r15b, sil
0x140173291  jnb     short loc_140173296
0x140173293  mov     r15b, r13b
0x140173296  lea     rax, WPP_RECORDER_INITIALIZED
0x14017329d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401732a4  jz      short loc_1401732B0
0x1401732a6  mov     r14b, sil
0x1401732a9  cmp     [rcx+48h], r13w
0x1401732ae  jnz     short loc_1401732B3
0x1401732b0  mov     r14b, r13b
0x1401732b3  test    r15b, r15b
0x1401732b6  jnz     short loc_1401732C1
0x1401732b8  test    r14b, r14b
0x1401732bb  jz      loc_1401730CC
0x1401732c1  mov     rcx, [rdi+10h]
0x1401732c5  mov     rcx, [rcx]; Thread
0x1401732c8  call    cs:__imp_PsGetThreadId
0x1401732cf  nop     dword ptr [rax+rax+00h]
0x1401732d4  mov     rdi, [rdi]
0x1401732d7  mov     rbx, rax
0x1401732da  call    cs:__imp_W32GetUserSessionState
0x1401732e1  nop     dword ptr [rax+rax+00h]
0x1401732e6  mov     dword ptr [rsp+98h+var_50], ebx
0x1401732ea  mov     [rsp+98h+var_58], rdi
0x1401732ef  mov     r9, [rax+10E20h]
0x1401732f6  lea     rax, WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids
0x1401732fd  mov     [rsp+98h+var_60], rax
0x140173302  mov     [rsp+98h+var_68], 18h
  ... truncated ...
```
