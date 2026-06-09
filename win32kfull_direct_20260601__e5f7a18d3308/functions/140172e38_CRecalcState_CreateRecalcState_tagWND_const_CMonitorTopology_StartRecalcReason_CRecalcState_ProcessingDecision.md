# CRecalcState::CreateRecalcState(tagWND const *,CMonitorTopology *,StartRecalcReason,CRecalcState::ProcessingDecision *)

- ea: `0x140172e38`
- end: `0x1401735e9`
- name: `?CreateRecalcState@CRecalcState@@SAPEAV1@PEBUtagWND@@PEAVCMonitorTopology@@W4StartRecalcReason@@PEAW4ProcessingDecision@1@@Z`
- size: `1969`
- prototype: ``
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
CRecalcState *__fastcall CRecalcState::CreateRecalcState(
        const struct tagWND *a1,
        __int64 a2,
        unsigned int a3,
        _DWORD *a4)
{
  __int64 v8; // rax
  __int64 v9; // rdx
  CRecalcState *v10; // rbp
  char v11; // si
  char v12; // r14
  bool v14; // si
  bool v15; // bl
  __int64 v16; // rdx
  __int16 WindowDpiLastNotify; // ax
  __int64 v18; // rdx
  char v19; // si
  char v20; // bp
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // edx
  int v24; // r8d
  __int64 v25; // r9
  char v26; // r15
  char v27; // r14
  char v28; // si
  char v29; // r14
  unsigned __int8 v30; // al
  __int64 v31; // rdi
  char v32; // bl
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  int v36; // r8d
  int v37; // edx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  int v42; // edx
  int v43; // r8d
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rcx
  unsigned __int8 v47; // al
  __int64 v48; // rdi
  char v49; // bl
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 UserSessionState; // rax
  int v53; // r8d
  int v54; // edx
  __int64 v55; // rdx
  __int64 v56; // rcx
  char v57; // si
  char v58; // r14
  unsigned __int8 v59; // al
  __int64 v60; // rdi
  char v61; // bl
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rax
  int v65; // r8d
  int v66; // edx
  __int64 v67; // rax
  int v68; // r8d
  int v69; // edx
  __int16 v70; // [rsp+30h] [rbp-68h]
  __int16 v71; // [rsp+30h] [rbp-68h]
  __int64 v72; // [rsp+40h] [rbp-58h]
  __int64 v73; // [rsp+40h] [rbp-58h]
  char ThreadId; // [rsp+48h] [rbp-50h]
  char v75; // [rsp+48h] [rbp-50h]

  *a4 = 0;
  if ( !(unsigned int)((__int64 (*)(void))IsImmersiveBand)() )
    goto LABEL_2;
  v16 = MonitorFromRect(*((_QWORD *)a1 + 5) + 88LL, 0);
  if ( !v16 )
  {
    v19 = 1;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      v20 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || !*((_WORD *)WPP_GLOBAL_Control + 36) )
    {
      v19 = 0;
    }
    if ( !v20 && !v19 )
      return 0;
    ThreadId = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
    v72 = *(_QWORD *)a1;
    v25 = *(_QWORD *)(W32GetUserSessionState(v39, v38) + 69152);
    v70 = 21;
LABEL_34:
    LOBYTE(v24) = v19;
    LOBYTE(v23) = v20;
    WPP_RECORDER_AND_TRACE_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v23,
      v24,
      v25,
      5,
      7,
      v70,
      (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
      v72,
      ThreadId);
    return 0;
  }
  WindowDpiLastNotify = GetWindowDpiLastNotify(a1, v16);
  if ( *(_WORD *)(*(_QWORD *)(v18 + 40) + 60LL) == WindowDpiLastNotify )
  {
    v19 = 1;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      v20 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || !*((_WORD *)WPP_GLOBAL_Control + 36) )
    {
      v19 = 0;
    }
    if ( !v20 && !v19 )
      return 0;
    ThreadId = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
    v72 = *(_QWORD *)a1;
    v25 = *(_QWORD *)(W32GetUserSessionState(v22, v21) + 69152);
    v70 = 22;
    goto LABEL_34;
  }
LABEL_2:
  v8 = Win32AllocPoolZInit(80, 1920168789);
  if ( v8 )
  {
    v10 = (CRecalcState *)CRecalcState::CRecalcState(v8, a1, a2, a3);
    if ( v10 )
    {
      if ( (unsigned int)IsImmersiveBand(a1) )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v26 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v27 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v27 = 0;
        }
        if ( !v26 && !v27 )
          goto LABEL_42;
        v75 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
        v73 = *(_QWORD *)a1;
        v44 = *(_QWORD *)(W32GetUserSessionState(v41, v40) + 69152);
        v71 = 24;
      }
      else if ( a3 == 4 )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v26 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v27 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v27 = 0;
        }
        if ( !v26 && !v27 )
          goto LABEL_42;
        v75 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
        v73 = *(_QWORD *)a1;
        v44 = *(_QWORD *)(W32GetUserSessionState(v46, v45) + 69152);
        v71 = 25;
      }
      else
      {
        if ( (unsigned __int8)CRecalcState::ShouldDeferRecalc(v10, a1, 0) )
        {
          v11 = 1;
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
            || (v12 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
          {
            v12 = 0;
          }
          if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
            || !*((_WORD *)WPP_GLOBAL_Control + 36) )
          {
            v11 = 0;
          }
          if ( v12 || v11 )
          {
            v47 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
            v48 = *(_QWORD *)a1;
            v49 = v47;
            UserSessionState = W32GetUserSessionState(v51, v50);
            LOBYTE(v53) = v11;
            LOBYTE(v54) = v12;
            WPP_RECORDER_AND_TRACE_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v54,
              v53,
              *(_QWORD *)(UserSessionState + 69152),
              5,
              7,
              26,
              (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
              v48,
              v49);
          }
          *a4 = 2;
          return v10;
        }
        if ( !CRecalcState::NeedsMigration(v10, a1) )
        {
          if ( CRecalcState::ShouldStoreAfterProcessing(v10, a1) )
          {
            v57 = 1;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
              || (v58 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v58 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || !*((_WORD *)WPP_GLOBAL_Control + 36) )
            {
              v57 = 0;
            }
            if ( v58 || v57 )
            {
              v59 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
              v60 = *(_QWORD *)a1;
              v61 = v59;
              v64 = W32GetUserSessionState(v63, v62);
              LOBYTE(v65) = v57;
              LOBYTE(v66) = v58;
              WPP_RECORDER_AND_TRACE_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v66,
                v65,
                *(_QWORD *)(v64 + 69152),
                5,
                7,
                28,
                (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
                v60,
                v61);
            }
            *a4 = 3;
          }
          else
          {
            v28 = 1;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
              || (v29 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v29 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || !*((_WORD *)WPP_GLOBAL_Control + 36) )
            {
              v28 = 0;
            }
            if ( v29 || v28 )
            {
              v30 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
              v31 = *(_QWORD *)a1;
              v32 = v30;
              v35 = W32GetUserSessionState(v34, v33);
              LOBYTE(v36) = v28;
              LOBYTE(v37) = v29;
              WPP_RECORDER_AND_TRACE_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v37,
                v36,
                *(_QWORD *)(v35 + 69152),
                5,
                7,
                29,
                (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
                v31,
                v32);
            }
          }
          return v10;
        }
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v26 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v27 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v27 = 0;
        }
        if ( !v26 && !v27 )
        {
LABEL_42:
          *a4 = 1;
          return v10;
        }
        v75 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
        v73 = *(_QWORD *)a1;
        v44 = *(_QWORD *)(W32GetUserSessionState(v56, v55) + 69152);
        v71 = 27;
      }
      LOBYTE(v43) = v27;
      LOBYTE(v42) = v26;
      WPP_RECORDER_AND_TRACE_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v42,
        v43,
        v44,
        5,
        7,
        v71,
        (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
        v73,
        v75);
      goto LABEL_42;
    }
  }
  v14 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
  v15 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v14 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v67 = W32GetUserSessionState(WPP_GLOBAL_Control, v9);
    LOBYTE(v68) = v15;
    LOBYTE(v69) = v14;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v69,
      v68,
      *(_QWORD *)(v67 + 69152),
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
