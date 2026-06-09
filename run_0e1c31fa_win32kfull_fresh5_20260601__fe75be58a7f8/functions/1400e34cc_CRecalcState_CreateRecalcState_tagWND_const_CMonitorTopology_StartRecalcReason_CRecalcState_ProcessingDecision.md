# CRecalcState::CreateRecalcState(tagWND const *,CMonitorTopology *,StartRecalcReason,CRecalcState::ProcessingDecision *)

- ea: `0x1400e34cc`
- end: `0x1400e3c7d`
- name: `?CreateRecalcState@CRecalcState@@SAPEAV1@PEBUtagWND@@PEAVCMonitorTopology@@W4StartRecalcReason@@PEAW4ProcessingDecision@1@@Z`
- size: `1969`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400e2818`
- `0x1402de88c`

## callees

- `0x14001aac0`
- `0x14001d918`
- `0x1400b71ac`
- `0x1400e09e4`
- `0x1400e34cc`
- `0x1400e3dec`
- `0x1400e3efc`
- `0x1400e4aec`
- `0x1400e51a8`
- `0x140177ee8`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1400e36a8`
- `ntoskrnl!PsGetThreadId` at `0x1400e37ef`
- `ntoskrnl!PsGetThreadId` at `0x1400e389b`
- `ntoskrnl!PsGetThreadId` at `0x1400e395c`
- `ntoskrnl!PsGetThreadId` at `0x1400e39ff`
- `ntoskrnl!PsGetThreadId` at `0x1400e3a5e`
- `ntoskrnl!PsGetThreadId` at `0x1400e3ace`
- `ntoskrnl!PsGetThreadId` at `0x1400e3b8d`
- `ntoskrnl!PsGetThreadId` at `0x1400e36a8`
- `ntoskrnl!PsGetThreadId` at `0x1400e37ef`
- `ntoskrnl!PsGetThreadId` at `0x1400e389b`
- `ntoskrnl!PsGetThreadId` at `0x1400e395c`
- `ntoskrnl!PsGetThreadId` at `0x1400e39ff`
- `ntoskrnl!PsGetThreadId` at `0x1400e3a5e`
- `ntoskrnl!PsGetThreadId` at `0x1400e3ace`
- `ntoskrnl!PsGetThreadId` at `0x1400e3b8d`
- `win32kbase!Win32AllocPoolZInit` at `0x1400e3506`
- `win32kbase!Win32AllocPoolZInit` at `0x1400e3506`
- `WIN32K!W32GetUserSessionState` at `0x1400e36ba`
- `WIN32K!W32GetUserSessionState` at `0x1400e3801`
- `WIN32K!W32GetUserSessionState` at `0x1400e38ad`
- `WIN32K!W32GetUserSessionState` at `0x1400e396e`
- `WIN32K!W32GetUserSessionState` at `0x1400e3a11`
- `WIN32K!W32GetUserSessionState` at `0x1400e3a70`
- `WIN32K!W32GetUserSessionState` at `0x1400e3ae0`
- `WIN32K!W32GetUserSessionState` at `0x1400e3b9f`
- `WIN32K!W32GetUserSessionState` at `0x1400e3c2f`
- `WIN32K!W32GetUserSessionState` at `0x1400e36ba`
- `WIN32K!W32GetUserSessionState` at `0x1400e3801`
- `WIN32K!W32GetUserSessionState` at `0x1400e38ad`
- `WIN32K!W32GetUserSessionState` at `0x1400e396e`
- `WIN32K!W32GetUserSessionState` at `0x1400e3a11`
- `WIN32K!W32GetUserSessionState` at `0x1400e3a70`
- `WIN32K!W32GetUserSessionState` at `0x1400e3ae0`
- `WIN32K!W32GetUserSessionState` at `0x1400e3b9f`
- `WIN32K!W32GetUserSessionState` at `0x1400e3c2f`

## pseudocode

```c
CRecalcState *__fastcall CRecalcState::CreateRecalcState(
        const struct tagWND *a1,
        __int64 a2,
        unsigned int a3,
        _DWORD *a4)
{
  __int64 v8; // rax
  CRecalcState *v9; // rbp
  char v10; // si
  char v11; // r14
  bool v13; // si
  bool v14; // bl
  __int64 v15; // rdx
  __int16 WindowDpiLastNotify; // ax
  __int64 v17; // rdx
  char v18; // si
  char v19; // bp
  __int64 v20; // rcx
  int v21; // edx
  int v22; // r8d
  __int64 v23; // r9
  char v24; // r15
  char v25; // r14
  char v26; // si
  char v27; // r14
  unsigned __int8 v28; // al
  __int64 v29; // rdi
  char v30; // bl
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // edx
  int v38; // r8d
  __int64 v39; // r9
  __int64 v40; // rcx
  unsigned __int8 v41; // al
  __int64 v42; // rdi
  char v43; // bl
  __int64 v44; // rcx
  __int64 UserSessionState; // rax
  int v46; // r8d
  int v47; // edx
  __int64 v48; // rcx
  char v49; // si
  char v50; // r14
  unsigned __int8 v51; // al
  __int64 v52; // rdi
  char v53; // bl
  __int64 v54; // rcx
  __int64 v55; // rax
  int v56; // r8d
  int v57; // edx
  __int64 v58; // rax
  int v59; // r8d
  int v60; // edx
  __int16 v61; // [rsp+30h] [rbp-68h]
  __int16 v62; // [rsp+30h] [rbp-68h]
  __int64 v63; // [rsp+40h] [rbp-58h]
  __int64 v64; // [rsp+40h] [rbp-58h]
  char ThreadId; // [rsp+48h] [rbp-50h]
  char v66; // [rsp+48h] [rbp-50h]

  *a4 = 0;
  if ( !(unsigned int)((__int64 (*)(void))IsImmersiveBand)() )
    goto LABEL_2;
  v15 = MonitorFromRect(*((_QWORD *)a1 + 5) + 88LL, 0);
  if ( !v15 )
  {
    v18 = 1;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || (v19 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      v19 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || !*((_WORD *)WPP_GLOBAL_Control + 36) )
    {
      v18 = 0;
    }
    if ( !v19 && !v18 )
      return 0;
    ThreadId = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
    v63 = *(_QWORD *)a1;
    v23 = *(_QWORD *)(W32GetUserSessionState(v35) + 69152);
    v61 = 21;
LABEL_34:
    LOBYTE(v22) = v18;
    LOBYTE(v21) = v19;
    WPP_RECORDER_AND_TRACE_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v21,
      v22,
      v23,
      5,
      7,
      v61,
      (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
      v63,
      ThreadId);
    return 0;
  }
  WindowDpiLastNotify = GetWindowDpiLastNotify(a1, v15);
  if ( *(_WORD *)(*(_QWORD *)(v17 + 40) + 60LL) == WindowDpiLastNotify )
  {
    v18 = 1;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || (v19 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      v19 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || !*((_WORD *)WPP_GLOBAL_Control + 36) )
    {
      v18 = 0;
    }
    if ( !v19 && !v18 )
      return 0;
    ThreadId = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
    v63 = *(_QWORD *)a1;
    v23 = *(_QWORD *)(W32GetUserSessionState(v20) + 69152);
    v61 = 22;
    goto LABEL_34;
  }
LABEL_2:
  v8 = Win32AllocPoolZInit(80, 1920168789);
  if ( v8 )
  {
    v9 = (CRecalcState *)CRecalcState::CRecalcState(v8, a1, a2, a3);
    if ( v9 )
    {
      if ( (unsigned int)IsImmersiveBand(a1) )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v24 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v25 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v25 = 0;
        }
        if ( !v24 && !v25 )
          goto LABEL_42;
        v66 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
        v64 = *(_QWORD *)a1;
        v39 = *(_QWORD *)(W32GetUserSessionState(v36) + 69152);
        v62 = 24;
      }
      else if ( a3 == 4 )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v24 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v25 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v25 = 0;
        }
        if ( !v24 && !v25 )
          goto LABEL_42;
        v66 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
        v64 = *(_QWORD *)a1;
        v39 = *(_QWORD *)(W32GetUserSessionState(v40) + 69152);
        v62 = 25;
      }
      else
      {
        if ( (unsigned __int8)CRecalcState::ShouldDeferRecalc(v9, a1, 0) )
        {
          v10 = 1;
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
            || (v11 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
          {
            v11 = 0;
          }
          if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
            || !*((_WORD *)WPP_GLOBAL_Control + 36) )
          {
            v10 = 0;
          }
          if ( v11 || v10 )
          {
            v41 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
            v42 = *(_QWORD *)a1;
            v43 = v41;
            UserSessionState = W32GetUserSessionState(v44);
            LOBYTE(v46) = v10;
            LOBYTE(v47) = v11;
            WPP_RECORDER_AND_TRACE_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v47,
              v46,
              *(_QWORD *)(UserSessionState + 69152),
              5,
              7,
              26,
              (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
              v42,
              v43);
          }
          *a4 = 2;
          return v9;
        }
        if ( !CRecalcState::NeedsMigration(v9, a1) )
        {
          if ( CRecalcState::ShouldStoreAfterProcessing(v9, a1) )
          {
            v49 = 1;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
              || (v50 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v50 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || !*((_WORD *)WPP_GLOBAL_Control + 36) )
            {
              v49 = 0;
            }
            if ( v50 || v49 )
            {
              v51 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
              v52 = *(_QWORD *)a1;
              v53 = v51;
              v55 = W32GetUserSessionState(v54);
              LOBYTE(v56) = v49;
              LOBYTE(v57) = v50;
              WPP_RECORDER_AND_TRACE_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v57,
                v56,
                *(_QWORD *)(v55 + 69152),
                5,
                7,
                28,
                (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
                v52,
                v53);
            }
            *a4 = 3;
          }
          else
          {
            v26 = 1;
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
              || (v27 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v27 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || !*((_WORD *)WPP_GLOBAL_Control + 36) )
            {
              v26 = 0;
            }
            if ( v27 || v26 )
            {
              v28 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
              v29 = *(_QWORD *)a1;
              v30 = v28;
              v32 = W32GetUserSessionState(v31);
              LOBYTE(v33) = v26;
              LOBYTE(v34) = v27;
              WPP_RECORDER_AND_TRACE_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v34,
                v33,
                *(_QWORD *)(v32 + 69152),
                5,
                7,
                29,
                (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
                v29,
                v30);
            }
          }
          return v9;
        }
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
        {
          v24 = 0;
        }
        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
          || (v25 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          v25 = 0;
        }
        if ( !v24 && !v25 )
        {
LABEL_42:
          *a4 = 1;
          return v9;
        }
        v66 = (unsigned __int8)PsGetThreadId(**((PETHREAD **)a1 + 2));
        v64 = *(_QWORD *)a1;
        v39 = *(_QWORD *)(W32GetUserSessionState(v48) + 69152);
        v62 = 27;
      }
      LOBYTE(v38) = v25;
      LOBYTE(v37) = v24;
      WPP_RECORDER_AND_TRACE_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v37,
        v38,
        v39,
        5,
        7,
        v62,
        (__int64)WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids,
        v64,
        v66);
      goto LABEL_42;
    }
  }
  v13 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
  v14 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v13 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v58 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v59) = v14;
    LOBYTE(v60) = v13;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v60,
      v59,
      *(_QWORD *)(v58 + 69152),
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
0x1400e34cc  push    rbx
0x1400e34ce  push    rbp
0x1400e34cf  push    rsi
0x1400e34d0  push    rdi
0x1400e34d1  push    r12
0x1400e34d3  push    r13
0x1400e34d5  push    r14
0x1400e34d7  push    r15
0x1400e34d9  sub     rsp, 58h
0x1400e34dd  xor     r13d, r13d
0x1400e34e0  mov     r12, r9
0x1400e34e3  mov     [r9], r13d
0x1400e34e6  mov     ebx, r8d
0x1400e34e9  mov     rsi, rdx
0x1400e34ec  mov     rdi, rcx
0x1400e34ef  call    IsImmersiveBand
0x1400e34f4  test    eax, eax
0x1400e34f6  jnz     loc_1400E3616
0x1400e34fc  mov     edx, 72737355h
0x1400e3501  mov     ecx, 50h ; 'P'
0x1400e3506  call    cs:__imp_Win32AllocPoolZInit
0x1400e350d  nop     dword ptr [rax+rax+00h]
0x1400e3512  test    rax, rax
0x1400e3515  jz      loc_1400E35D6
0x1400e351b  mov     r9d, ebx
0x1400e351e  mov     r8, rsi
0x1400e3521  mov     rdx, rdi
0x1400e3524  mov     rcx, rax
0x1400e3527  call    ??0CRecalcState@@AEAA@PEBUtagWND@@PEAVCMonitorTopology@@W4StartRecalcReason@@@Z; CRecalcState::CRecalcState(tagWND const *,CMonitorTopology *,StartRecalcReason)
0x1400e352c  mov     rbp, rax
0x1400e352f  test    rax, rax
0x1400e3532  jz      loc_1400E35D6
0x1400e3538  mov     rcx, rdi
0x1400e353b  call    IsImmersiveBand
0x1400e3540  test    eax, eax
0x1400e3542  jnz     loc_1400E38FF
0x1400e3548  cmp     ebx, 4
0x1400e354b  jz      loc_1400E39A2
0x1400e3551  xor     r8d, r8d
0x1400e3554  mov     rdx, rdi
0x1400e3557  mov     rcx, rbp
0x1400e355a  call    ?ShouldDeferRecalc@CRecalcState@@QEBA_NPEBUtagWND@@W4ShouldDeferRecalcOption@1@@Z; CRecalcState::ShouldDeferRecalc(tagWND const *,CRecalcState::ShouldDeferRecalcOption)
0x1400e355f  test    al, al
0x1400e3561  jz      loc_1400E3711
0x1400e3567  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e356e  lea     rax, WPP_GLOBAL_Control
0x1400e3575  mov     esi, 1
0x1400e357a  cmp     rcx, rax
0x1400e357d  jz      short loc_1400E358A
0x1400e357f  mov     eax, [rcx+2Ch]
0x1400e3582  test    al, 40h
0x1400e3584  jnz     loc_1400E3A45
0x1400e358a  mov     r14b, r13b
0x1400e358d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e3594  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e359b  jz      short loc_1400E35A4
0x1400e359d  cmp     [rcx+48h], r13w
0x1400e35a2  jnz     short loc_1400E35A7
0x1400e35a4  mov     sil, r13b
0x1400e35a7  test    r14b, r14b
0x1400e35aa  jnz     loc_1400E3A57
0x1400e35b0  test    sil, sil
0x1400e35b3  jnz     loc_1400E3A57
0x1400e35b9  mov     dword ptr [r12], 2
0x1400e35c1  mov     rax, rbp
0x1400e35c4  add     rsp, 58h
0x1400e35c8  pop     r15
0x1400e35ca  pop     r14
0x1400e35cc  pop     r13
0x1400e35ce  pop     r12
0x1400e35d0  pop     rdi
0x1400e35d1  pop     rsi
0x1400e35d2  pop     rbp
0x1400e35d3  pop     rbx
0x1400e35d4  retn
0x1400e35d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e35dd  lea     rax, WPP_GLOBAL_Control
0x1400e35e4  cmp     rcx, rax
0x1400e35e7  jnz     loc_1400E3C10
0x1400e35ed  mov     sil, r13b
0x1400e35f0  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e35f7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e35fe  setnz   bl
0x1400e3601  test    sil, sil
0x1400e3604  jnz     loc_1400E3C2F
0x1400e360a  test    bl, bl
0x1400e360c  jnz     loc_1400E3C2F
0x1400e3612  xor     eax, eax
0x1400e3614  jmp     short loc_1400E35C4
0x1400e3616  mov     r8, [rdi+28h]
0x1400e361a  xor     edx, edx
0x1400e361c  lea     rcx, [r8+58h]
0x1400e3620  mov     r8d, [r8+120h]
0x1400e3627  call    _MonitorFromRect
0x1400e362c  mov     rdx, rax
0x1400e362f  test    rax, rax
0x1400e3632  jz      loc_1400E3858
0x1400e3638  mov     rcx, rdi
0x1400e363b  call    GetWindowDpiLastNotify
0x1400e3640  mov     rcx, [rdx+28h]
0x1400e3644  cmp     [rcx+3Ch], ax
0x1400e3648  jnz     loc_1400E34FC
0x1400e364e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e3655  lea     rax, WPP_GLOBAL_Control
0x1400e365c  mov     esi, 1
0x1400e3661  cmp     rcx, rax
0x1400e3664  jz      short loc_1400E3676
0x1400e3666  mov     eax, [rcx+2Ch]
0x1400e3669  test    al, 40h
0x1400e366b  jz      short loc_1400E3676
0x1400e366d  cmp     byte ptr [rcx+29h], 5
0x1400e3671  mov     bpl, sil
0x1400e3674  jnb     short loc_1400E3679
0x1400e3676  mov     bpl, r13b
0x1400e3679  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e3680  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e3687  jz      short loc_1400E3690
0x1400e3689  cmp     [rcx+48h], r13w
0x1400e368e  jnz     short loc_1400E3693
0x1400e3690  mov     sil, r13b
0x1400e3693  test    bpl, bpl
0x1400e3696  jnz     short loc_1400E36A1
0x1400e3698  test    sil, sil
0x1400e369b  jz      loc_1400E3612
0x1400e36a1  mov     rcx, [rdi+10h]
0x1400e36a5  mov     rcx, [rcx]; Thread
0x1400e36a8  call    cs:__imp_PsGetThreadId
0x1400e36af  nop     dword ptr [rax+rax+00h]
0x1400e36b4  mov     rdi, [rdi]
0x1400e36b7  mov     rbx, rax
0x1400e36ba  call    cs:__imp_W32GetUserSessionState
0x1400e36c1  nop     dword ptr [rax+rax+00h]
0x1400e36c6  mov     dword ptr [rsp+98h+var_50], ebx
0x1400e36ca  mov     [rsp+98h+var_58], rdi
0x1400e36cf  mov     r9, [rax+10E20h]
0x1400e36d6  lea     rax, WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids
0x1400e36dd  mov     [rsp+98h+var_60], rax
0x1400e36e2  mov     [rsp+98h+var_68], 16h
0x1400e36e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e36f0  mov     r8b, sil
0x1400e36f3  mov     [rsp+98h+var_70], 7
0x1400e36fb  mov     dl, bpl
0x1400e36fe  mov     [rsp+98h+var_78], 5
0x1400e3703  mov     rcx, [rcx+18h]
0x1400e3707  call    WPP_RECORDER_AND_TRACE_SF_qD
0x1400e370c  jmp     loc_1400E3612
0x1400e3711  mov     rdx, rdi; struct tagWND *
0x1400e3714  mov     rcx, rbp; this
0x1400e3717  call    ?NeedsMigration@CRecalcState@@AEBA_NPEBUtagWND@@@Z; CRecalcState::NeedsMigration(tagWND const *)
0x1400e371c  test    al, al
0x1400e371e  jz      short loc_1400E3787
0x1400e3720  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e3727  lea     rax, WPP_GLOBAL_Control
0x1400e372e  mov     esi, 1
0x1400e3733  cmp     rcx, rax
0x1400e3736  jnz     short loc_1400E3769
0x1400e3738  mov     r15b, r13b
0x1400e373b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e3742  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e3749  jnz     short loc_1400E377B
0x1400e374b  mov     r14b, r13b
0x1400e374e  test    r15b, r15b
0x1400e3751  jnz     loc_1400E3AC7
0x1400e3757  test    r14b, r14b
0x1400e375a  jnz     loc_1400E3AC7
0x1400e3760  mov     [r12], esi
0x1400e3764  jmp     loc_1400E35C1
0x1400e3769  mov     eax, [rcx+2Ch]
0x1400e376c  test    al, 40h
0x1400e376e  jz      short loc_1400E3738
0x1400e3770  cmp     byte ptr [rcx+29h], 5
0x1400e3774  mov     r15b, sil
0x1400e3777  jnb     short loc_1400E373B
0x1400e3779  jmp     short loc_1400E3738
0x1400e377b  mov     r14b, sil
0x1400e377e  cmp     [rcx+48h], r13w
0x1400e3783  jnz     short loc_1400E374E
0x1400e3785  jmp     short loc_1400E374B
0x1400e3787  mov     rdx, rdi; struct tagWND *
0x1400e378a  mov     rcx, rbp; this
0x1400e378d  call    ?ShouldStoreAfterProcessing@CRecalcState@@QEBA_NPEBUtagWND@@@Z; CRecalcState::ShouldStoreAfterProcessing(tagWND const *)
0x1400e3792  test    al, al
0x1400e3794  jnz     loc_1400E3B37
0x1400e379a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e37a1  lea     rax, WPP_GLOBAL_Control
0x1400e37a8  mov     esi, 1
0x1400e37ad  cmp     rcx, rax
0x1400e37b0  jz      short loc_1400E37BD
0x1400e37b2  mov     eax, [rcx+2Ch]
0x1400e37b5  test    al, 40h
0x1400e37b7  jnz     loc_1400E3BFE
0x1400e37bd  mov     r14b, r13b
0x1400e37c0  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e37c7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e37ce  jz      short loc_1400E37D7
0x1400e37d0  cmp     [rcx+48h], r13w
0x1400e37d5  jnz     short loc_1400E37DA
0x1400e37d7  mov     sil, r13b
0x1400e37da  test    r14b, r14b
0x1400e37dd  jnz     short loc_1400E37E8
0x1400e37df  test    sil, sil
0x1400e37e2  jz      loc_1400E35C1
0x1400e37e8  mov     rcx, [rdi+10h]
0x1400e37ec  mov     rcx, [rcx]; Thread
0x1400e37ef  call    cs:__imp_PsGetThreadId
0x1400e37f6  nop     dword ptr [rax+rax+00h]
0x1400e37fb  mov     rdi, [rdi]
0x1400e37fe  mov     rbx, rax
0x1400e3801  call    cs:__imp_W32GetUserSessionState
0x1400e3808  nop     dword ptr [rax+rax+00h]
0x1400e380d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e3814  mov     r8b, sil
0x1400e3817  mov     dword ptr [rsp+98h+var_50], ebx
0x1400e381b  mov     dl, r14b
0x1400e381e  mov     [rsp+98h+var_58], rdi
0x1400e3823  mov     r9, [rax+10E20h]
0x1400e382a  lea     rax, WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids
0x1400e3831  mov     rcx, [rcx+18h]
0x1400e3835  mov     [rsp+98h+var_60], rax
0x1400e383a  mov     [rsp+98h+var_68], 1Dh
0x1400e3841  mov     [rsp+98h+var_70], 7
0x1400e3849  mov     [rsp+98h+var_78], 5
0x1400e384e  call    WPP_RECORDER_AND_TRACE_SF_qD
0x1400e3853  jmp     loc_1400E35C1
0x1400e3858  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e385f  lea     rax, WPP_GLOBAL_Control
0x1400e3866  mov     esi, 1
0x1400e386b  cmp     rcx, rax
0x1400e386e  jnz     short loc_1400E38E1
0x1400e3870  mov     bpl, r13b
0x1400e3873  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e387a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e3881  jnz     short loc_1400E38F6
0x1400e3883  mov     sil, r13b
0x1400e3886  test    bpl, bpl
0x1400e3889  jnz     short loc_1400E3894
0x1400e388b  test    sil, sil
0x1400e388e  jz      loc_1400E3612
0x1400e3894  mov     rcx, [rdi+10h]
0x1400e3898  mov     rcx, [rcx]; Thread
0x1400e389b  call    cs:__imp_PsGetThreadId
0x1400e38a2  nop     dword ptr [rax+rax+00h]
0x1400e38a7  mov     rdi, [rdi]
0x1400e38aa  mov     rbx, rax
0x1400e38ad  call    cs:__imp_W32GetUserSessionState
0x1400e38b4  nop     dword ptr [rax+rax+00h]
0x1400e38b9  mov     dword ptr [rsp+98h+var_50], ebx
0x1400e38bd  mov     [rsp+98h+var_58], rdi
0x1400e38c2  mov     r9, [rax+10E20h]
0x1400e38c9  lea     rax, WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids
0x1400e38d0  mov     [rsp+98h+var_60], rax
0x1400e38d5  mov     [rsp+98h+var_68], 15h
0x1400e38dc  jmp     loc_1400E36E9
0x1400e38e1  mov     eax, [rcx+2Ch]
0x1400e38e4  test    al, 40h
0x1400e38e6  jz      short loc_1400E3870
0x1400e38e8  cmp     byte ptr [rcx+29h], 5
0x1400e38ec  mov     bpl, sil
0x1400e38ef  jnb     short loc_1400E3873
0x1400e38f1  jmp     loc_1400E3870
0x1400e38f6  cmp     [rcx+48h], r13w
0x1400e38fb  jnz     short loc_1400E3886
0x1400e38fd  jmp     short loc_1400E3883
0x1400e38ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e3906  lea     rax, WPP_GLOBAL_Control
0x1400e390d  mov     esi, 1
0x1400e3912  cmp     rcx, rax
0x1400e3915  jz      short loc_1400E3927
0x1400e3917  mov     eax, [rcx+2Ch]
0x1400e391a  test    al, 40h
0x1400e391c  jz      short loc_1400E3927
0x1400e391e  cmp     byte ptr [rcx+29h], 5
0x1400e3922  mov     r15b, sil
0x1400e3925  jnb     short loc_1400E392A
0x1400e3927  mov     r15b, r13b
0x1400e392a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e3931  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e3938  jz      short loc_1400E3944
0x1400e393a  mov     r14b, sil
0x1400e393d  cmp     [rcx+48h], r13w
0x1400e3942  jnz     short loc_1400E3947
0x1400e3944  mov     r14b, r13b
0x1400e3947  test    r15b, r15b
0x1400e394a  jnz     short loc_1400E3955
0x1400e394c  test    r14b, r14b
0x1400e394f  jz      loc_1400E3760
0x1400e3955  mov     rcx, [rdi+10h]
0x1400e3959  mov     rcx, [rcx]; Thread
0x1400e395c  call    cs:__imp_PsGetThreadId
0x1400e3963  nop     dword ptr [rax+rax+00h]
0x1400e3968  mov     rdi, [rdi]
0x1400e396b  mov     rbx, rax
0x1400e396e  call    cs:__imp_W32GetUserSessionState
0x1400e3975  nop     dword ptr [rax+rax+00h]
0x1400e397a  mov     dword ptr [rsp+98h+var_50], ebx
0x1400e397e  mov     [rsp+98h+var_58], rdi
0x1400e3983  mov     r9, [rax+10E20h]
0x1400e398a  lea     rax, WPP_9002a0cd975736f7dd1bd7e045542d26_Traceguids
0x1400e3991  mov     [rsp+98h+var_60], rax
0x1400e3996  mov     [rsp+98h+var_68], 18h
  ... truncated ...
```
