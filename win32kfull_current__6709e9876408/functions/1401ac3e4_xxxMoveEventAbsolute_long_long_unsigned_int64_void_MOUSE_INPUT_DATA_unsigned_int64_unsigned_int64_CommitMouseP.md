# xxxMoveEventAbsolute(long,long,unsigned __int64,void *,_MOUSE_INPUT_DATA *,unsigned __int64,unsigned __int64,_CommitMousePosAndMoveOptions,_MousePacketPerf *)

- ea: `0x1401ac3e4`
- end: `0x1401ac914`
- name: `?xxxMoveEventAbsolute@@YA?AW4_CommitMousePosAndMoveResult@@JJ_KPEAXPEAU_MOUSE_INPUT_DATA@@00W4_CommitMousePosAndMoveOptions@@PEAU_MousePacketPerf@@@Z`
- size: `1328`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401ac360`

## callees

- `0x14002ea00`
- `0x14004ab00`
- `0x14004cd80`
- `0x1400aabf0`
- `0x1400c0b64`
- `0x1400e2cb0`
- `0x1400e5938`
- `0x1400e6340`
- `0x1400ea7ac`
- `0x14012a970`
- `0x14013a0c0`
- `0x14013a610`
- `0x1401ac3e4`
- `0x1401b4110`
- `0x14026c5ec`
- `0x140342fa0`

## import_xrefs

- `win32kbase!EtwTraceGreMovePointerEnd` at `0x1401ac878`
- `win32kbase!EtwTraceGreMovePointerEnd` at `0x1401ac878`
- `win32kbase!EtwTraceGreMovePointerBegin` at `0x1401ac7dc`
- `win32kbase!EtwTraceGreMovePointerBegin` at `0x1401ac7dc`
- `win32kbase!SetMouseMoveBoundHitFlagsForMoveSize` at `0x1401ac782`
- `win32kbase!SetMouseMoveBoundHitFlagsForMoveSize` at `0x1401ac782`
- `win32kbase!?BoundPoint@CCursorClip@@QEAA?AUClipResult@@UtagPOINT@@W4BoundPointOptions@@W4InputTracing_MouseUpdatePositionReason@@PEAU3@@Z` at `0x1401ac754`
- `win32kbase!?BoundPoint@CCursorClip@@QEAA?AUClipResult@@UtagPOINT@@W4BoundPointOptions@@W4InputTracing_MouseUpdatePositionReason@@PEAU3@@Z` at `0x1401ac754`
- `win32kbase!EnterCrit` at `0x1401ac4b6`
- `win32kbase!EnterCrit` at `0x1401ac6b2`
- `win32kbase!EnterCrit` at `0x1401ac4b6`
- `win32kbase!EnterCrit` at `0x1401ac6b2`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401ac5de`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401ac680`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401ac6dd`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401ac5de`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401ac680`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401ac6dd`
- `WIN32K!W32GetUserSessionState` at `0x1401ac442`
- `WIN32K!W32GetUserSessionState` at `0x1401ac45b`
- `WIN32K!W32GetUserSessionState` at `0x1401ac510`
- `WIN32K!W32GetUserSessionState` at `0x1401ac694`
- `WIN32K!W32GetUserSessionState` at `0x1401ac6be`
- `WIN32K!W32GetUserSessionState` at `0x1401ac6f0`
- `WIN32K!W32GetUserSessionState` at `0x1401ac729`
- `WIN32K!W32GetUserSessionState` at `0x1401ac7fe`
- `WIN32K!W32GetUserSessionState` at `0x1401ac81a`
- `WIN32K!W32GetUserSessionState` at `0x1401ac88d`
- `WIN32K!W32GetUserSessionState` at `0x1401ac8b4`
- `WIN32K!W32GetUserSessionState` at `0x1401ac8c9`
- `WIN32K!W32GetUserSessionState` at `0x1401ac8de`
- `WIN32K!W32GetUserSessionState` at `0x1401ac442`
- `WIN32K!W32GetUserSessionState` at `0x1401ac45b`
- `WIN32K!W32GetUserSessionState` at `0x1401ac510`
- `WIN32K!W32GetUserSessionState` at `0x1401ac694`
- `WIN32K!W32GetUserSessionState` at `0x1401ac6be`
- `WIN32K!W32GetUserSessionState` at `0x1401ac6f0`
- `WIN32K!W32GetUserSessionState` at `0x1401ac729`
- `WIN32K!W32GetUserSessionState` at `0x1401ac7fe`
- `WIN32K!W32GetUserSessionState` at `0x1401ac81a`
- `WIN32K!W32GetUserSessionState` at `0x1401ac88d`
- `WIN32K!W32GetUserSessionState` at `0x1401ac8b4`
- `WIN32K!W32GetUserSessionState` at `0x1401ac8c9`
- `WIN32K!W32GetUserSessionState` at `0x1401ac8de`
- `HAL!KeQueryPerformanceCounter` at `0x1401ac433`
- `HAL!KeQueryPerformanceCounter` at `0x1401ac5ba`
- `HAL!KeQueryPerformanceCounter` at `0x1401ac7ea`
- `HAL!KeQueryPerformanceCounter` at `0x1401ac858`
- `HAL!KeQueryPerformanceCounter` at `0x1401ac433`
- `HAL!KeQueryPerformanceCounter` at `0x1401ac5ba`
- `HAL!KeQueryPerformanceCounter` at `0x1401ac7ea`
- `HAL!KeQueryPerformanceCounter` at `0x1401ac858`

## string_xrefs

- `0x1401ac7bc`: `MoveCursor`
- `0x1401ac4cd`: `LowLevelMouseMoveHook`

## pseudocode

```c
__int64 __fastcall xxxMoveEventAbsolute(
        int a1,
        int a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        unsigned int a6,
        unsigned __int64 a7,
        char a8,
        LARGE_INTEGER *a9)
{
  unsigned int v9; // r15d
  LARGE_INTEGER PerformanceCounter; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // esi
  __int64 *v14; // rax
  __int64 v15; // rcx
  int v16; // esi
  bool v17; // r12
  unsigned int v18; // r14d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 UserSessionState; // rax
  struct tagTHREADINFO *v23; // rax
  __int64 v24; // rcx
  struct tagTHREADINFO *v25; // rsi
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  LARGE_INTEGER v30; // rax
  bool v31; // zf
  __int64 v32; // rdx
  __int64 v33; // rcx
  unsigned int v35; // ebx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  const struct tagPOINT *v41; // r12
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  LARGE_INTEGER v45; // rax
  LARGE_INTEGER *v46; // rcx
  __int64 v47; // rax
  int y; // ebx
  int x; // edi
  CursorApiRouter *v50; // rsi
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int32 v57; // ebx
  __int64 v58; // rcx
  __int64 Valid; // [rsp+40h] [rbp-71h] BYREF
  int v60; // [rsp+48h] [rbp-69h]
  int v61; // [rsp+4Ch] [rbp-65h]
  LARGE_INTEGER *v62; // [rsp+50h] [rbp-61h]
  char v63[8]; // [rsp+58h] [rbp-59h] BYREF
  _DWORD v64[2]; // [rsp+60h] [rbp-51h] BYREF
  void *v65; // [rsp+68h] [rbp-49h]
  _WORD v66[2]; // [rsp+70h] [rbp-41h] BYREF
  int v67; // [rsp+74h] [rbp-3Dh]
  int v68; // [rsp+78h] [rbp-39h]
  int v69; // [rsp+7Ch] [rbp-35h]
  int v70; // [rsp+80h] [rbp-31h]
  int v71; // [rsp+84h] [rbp-2Dh]
  int v72; // [rsp+88h] [rbp-29h] BYREF
  int v73; // [rsp+8Ch] [rbp-25h]
  void *v74; // [rsp+90h] [rbp-21h]
  __int64 v75; // [rsp+98h] [rbp-19h]
  __int64 v76; // [rsp+A0h] [rbp-11h]

  v9 = 1;
  v60 = a1;
  v62 = a9;
  v65 = a4;
  Valid = a3;
  v61 = a2;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v12 = *(_QWORD *)(W32GetUserSessionState(v11) + 18752);
  v13 = *(_DWORD *)(v12 + 712);
  v14 = *(__int64 **)(*(_QWORD *)(W32GetUserSessionState(v12) + 18752) + 496LL);
  v15 = *v14;
  v16 = (*(_DWORD *)(*v14 + 16) | v13) & 0x8000;
  v17 = a5 && (unsigned int)RawInputRequestedForMouse();
  v18 = 2;
  if ( v16 || v17 )
  {
    EnterCrit(1, 0);
    if ( v16 )
    {
      InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(
        (InputTraceLogging::ThreadLockedPerfRegion *)v63,
        "LowLevelMouseMoveHook",
        0);
      v72 = v60;
      v73 = v61;
      v74 = 0;
      v75 = a6;
      v76 = Valid;
      UserSessionState = W32GetUserSessionState(v21);
      Valid = PhkFirstValid(*(_QWORD *)(UserSessionState + 18752), 14);
      if ( Valid )
      {
        v62[4] = PerformanceCounter;
        v23 = PtiCurrent();
        v24 = Valid;
        v25 = v23;
        v26 = *((_QWORD *)v23 + 196);
        *((_QWORD *)v23 + 196) = &v72;
        v27 = xxxCallHook2(v24, 0, 512, (__int64)&v72, 1u);
        v28 = *((_QWORD *)v25 + 60);
        *((_QWORD *)v25 + 196) = v26;
        Valid = v27;
        if ( (*(_DWORD *)(*((_QWORD *)v25 + 60) + 16LL) & *(_DWORD *)(v28 + 4) & 0xFFFFFDFF) != 0 )
        {
          v29 = *(unsigned int *)(*((_QWORD *)v25 + 60) + 4LL);
          LODWORD(v29) = v29 & 0xFFFFFDFF;
          SetWakeBit(v25, v29);
        }
        v30 = KeQueryPerformanceCounter(0);
        v31 = Valid == 0;
        v62[5] = v30;
        if ( !v31 )
        {
          InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion((InputTraceLogging::ThreadLockedPerfRegion *)v63);
          UserSessionSwitchLeaveCrit(v33, v32);
          return 0;
        }
      }
      InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion((InputTraceLogging::ThreadLockedPerfRegion *)v63);
    }
    if ( v17 )
    {
      if ( (unsigned int)RawInputRequestedForMouse() )
      {
        v74 = v65;
        v66[1] = 0;
        v66[0] = *(_WORD *)(a5 + 2);
        v67 = *(_DWORD *)(a5 + 4);
        v68 = *(_DWORD *)(a5 + 8);
        v69 = *(_DWORD *)(a5 + 12);
        v70 = *(_DWORD *)(a5 + 16);
        v71 = *(_DWORD *)(a5 + 20);
        v73 = 0;
        v75 = 0;
        v72 = v65 != 0 ? 2 : 0;
        if ( (unsigned int)EditionPostRawMouseInputMessage(0, a7, a6, &v72, v66) )
        {
          v9 = 9;
          *(_WORD *)a5 = -1;
        }
      }
    }
    UserSessionSwitchLeaveCrit(v20, v19);
  }
  if ( (a8 & 2) != 0 )
  {
    v35 = 1;
    if ( *(_DWORD *)(W32GetUserSessionState(v15) + 36172) == 2 )
    {
      EnterCrit(1, 0);
      if ( *(_DWORD *)(W32GetUserSessionState(v36) + 36172) == 2 )
        TransitionCursorSuppressionState(8);
      UserSessionSwitchLeaveCrit(v38, v37);
    }
  }
  else
  {
    v35 = 1;
  }
  v39 = W32GetUserSessionState(v15);
  v41 = (const struct tagPOINT *)(v39 + 19256);
  *(_DWORD *)(v39 + 19256) = v60;
  *(_DWORD *)(v39 + 19260) = v61;
  if ( (a8 & 4) != 0 )
  {
    if ( !a5 || (*(_BYTE *)(a5 + 2) & 1) != 0 )
      v35 = 0;
  }
  else
  {
    v35 = 2;
  }
  v42 = W32GetUserSessionState(v40);
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))CCursorClip::BoundPoint)(
    *(_QWORD *)(v42 + 36072),
    v64,
    *v41,
    v35,
    0,
    v41);
  if ( v64[0] == 2 )
  {
    v9 |= 2u;
  }
  else
  {
    v44 = 1;
    if ( v64[0] == 1 )
      v9 |= 4u;
    if ( !v64[0] )
      goto LABEL_36;
  }
  SetMouseMoveBoundHitFlagsForMoveSize(v64[1]);
  v44 = 1;
LABEL_36:
  if ( (a8 & 0x10) == 0 )
    v18 = (a8 & 1) != 0;
  if ( (a8 & 2) != 0 )
  {
    if ( (unsigned int)UsingPenCursors() )
      RestoreMouseCursors();
    InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(
      (InputTraceLogging::ThreadLockedPerfRegion *)&Valid,
      "MoveCursor",
      0);
    EtwTraceGreMovePointerBegin(a6, (unsigned int)v41->x, (unsigned int)v41->y);
    v45 = KeQueryPerformanceCounter(0);
    v46 = v62;
    v62[2] = v45;
    v47 = W32GetUserSessionState(v46);
    y = v41->y;
    x = v41->x;
    v50 = *(CursorApiRouter **)(v47 + 36136);
    v52 = W32GetUserSessionState(v51);
    CursorApiRouter::MovePointer(v50, *(HDEV *)(*(_QWORD *)(v52 + 56744) + 40LL), x, y, v18, v65, a7);
    v62[3] = KeQueryPerformanceCounter(0);
    EtwTraceGreMovePointerEnd(a6, (unsigned int)v41->x, (unsigned int)v41->y);
    InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion((InputTraceLogging::ThreadLockedPerfRegion *)&Valid);
    v54 = W32GetUserSessionState(v53);
    CCursorSizes::zzzUpdateGlobalCursorSize(*(CCursorSizes **)(v54 + 36176), v41, 0);
  }
  if ( !(unsigned int)IsRemoteConnection(v44, v43) )
  {
    if ( *(_DWORD *)(W32GetUserSessionState(v55) + 16240) )
    {
      v57 = *(_DWORD *)(W32GetUserSessionState(v56) + 16240) + 2;
      _InterlockedExchange((volatile __int32 *)(W32GetUserSessionState(v58) + 16244), v57);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1401ac3e4  push    rbp
0x1401ac3e6  push    rbx
0x1401ac3e7  push    rsi
0x1401ac3e8  push    rdi
0x1401ac3e9  push    r12
0x1401ac3eb  push    r13
0x1401ac3ed  push    r14
0x1401ac3ef  push    r15
0x1401ac3f1  lea     rbp, [rsp-7]
0x1401ac3f6  sub     rsp, 0B8h
0x1401ac3fd  mov     rax, cs:__security_cookie
0x1401ac404  xor     rax, rsp
0x1401ac407  mov     [rbp+3Fh+var_48], rax
0x1401ac40b  mov     rax, [rbp+3Fh+arg_40]
0x1401ac412  mov     r14d, 1
0x1401ac418  mov     rdi, [rbp+3Fh+arg_20]
0x1401ac41c  mov     r15d, r14d
0x1401ac41f  mov     [rbp+3Fh+var_A8], ecx
0x1401ac422  xor     ecx, ecx; PerformanceFrequency
0x1401ac424  mov     [rbp+3Fh+var_A0], rax
0x1401ac428  mov     [rbp+3Fh+var_88], r9
0x1401ac42c  mov     [rbp+3Fh+var_B0], r8
0x1401ac430  mov     [rbp+3Fh+var_A4], edx
0x1401ac433  call    cs:__imp_KeQueryPerformanceCounter
0x1401ac43a  nop     dword ptr [rax+rax+00h]
0x1401ac43f  mov     rbx, rax
0x1401ac442  call    cs:__imp_W32GetUserSessionState
0x1401ac449  nop     dword ptr [rax+rax+00h]
0x1401ac44e  mov     rcx, [rax+4940h]
0x1401ac455  mov     esi, [rcx+2C8h]
0x1401ac45b  call    cs:__imp_W32GetUserSessionState
0x1401ac462  nop     dword ptr [rax+rax+00h]
0x1401ac467  mov     rcx, [rax+4940h]
0x1401ac46e  mov     rax, [rcx+1F0h]
0x1401ac475  mov     rcx, [rax]
0x1401ac478  or      esi, [rcx+10h]
0x1401ac47b  and     esi, 8000h
0x1401ac481  test    rdi, rdi
0x1401ac484  jz      short loc_1401AC494
0x1401ac486  call    RawInputRequestedForMouse
0x1401ac48b  test    eax, eax
0x1401ac48d  jz      short loc_1401AC494
0x1401ac48f  mov     r12b, r14b
0x1401ac492  jmp     short loc_1401AC497
0x1401ac494  xor     r12b, r12b
0x1401ac497  mov     r13d, dword ptr [rbp+3Fh+arg_38]
0x1401ac49e  mov     r14d, 2
0x1401ac4a4  test    esi, esi
0x1401ac4a6  jnz     short loc_1401AC4B1
0x1401ac4a8  test    r12b, r12b
0x1401ac4ab  jz      loc_1401AC68C
0x1401ac4b1  xor     edx, edx
0x1401ac4b3  mov     ecx, r15d
0x1401ac4b6  call    cs:__imp_EnterCrit
0x1401ac4bd  nop     dword ptr [rax+rax+00h]
0x1401ac4c2  test    esi, esi
0x1401ac4c4  jz      loc_1401AC5FA
0x1401ac4ca  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x1401ac4cd  lea     rdx, aLowlevelmousem; "LowLevelMouseMoveHook"
0x1401ac4d4  lea     rcx, [rbp+3Fh+var_98]; this
0x1401ac4d8  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x1401ac4dd  mov     eax, [rbp+3Fh+var_A8]
0x1401ac4e0  mov     [rbp+3Fh+var_68], eax
0x1401ac4e3  mov     eax, [rbp+3Fh+var_A4]
0x1401ac4e6  mov     [rbp+3Fh+var_64], eax
0x1401ac4e9  movzx   eax, r13b
0x1401ac4ed  and     eax, r15d
0x1401ac4f0  mov     dword ptr [rbp+3Fh+var_58+4], 0
0x1401ac4f7  mov     dword ptr [rbp+3Fh+var_60+4], eax
0x1401ac4fa  mov     rax, [rbp+3Fh+arg_28]
0x1401ac4fe  mov     dword ptr [rbp+3Fh+var_58], eax
0x1401ac501  mov     rax, [rbp+3Fh+var_B0]
0x1401ac505  mov     [rbp+3Fh+var_50], rax
0x1401ac509  mov     dword ptr [rbp+3Fh+var_60], 0
0x1401ac510  call    cs:__imp_W32GetUserSessionState
0x1401ac517  nop     dword ptr [rax+rax+00h]
0x1401ac51c  mov     edx, 0Eh
0x1401ac521  mov     rcx, [rax+4940h]
0x1401ac528  call    PhkFirstValid
0x1401ac52d  mov     [rbp+3Fh+var_B0], rax
0x1401ac531  test    rax, rax
0x1401ac534  jz      loc_1401AC5F1
0x1401ac53a  mov     rax, [rbp+3Fh+var_A0]
0x1401ac53e  mov     [rax+20h], rbx
0x1401ac542  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401ac547  mov     rcx, [rbp+3Fh+var_B0]
0x1401ac54b  lea     r9, [rbp+3Fh+var_68]
0x1401ac54f  mov     rsi, rax
0x1401ac552  mov     [rsp+0F0h+var_D0], r15d
0x1401ac557  xor     edx, edx
0x1401ac559  mov     r8d, 200h
0x1401ac55f  mov     rbx, [rax+620h]
0x1401ac566  lea     rax, [rbp+3Fh+var_68]
0x1401ac56a  mov     [rsi+620h], rax
0x1401ac571  call    ?xxxCallHook2@@YA_JPEAUtagHOOK@@H_K_JW4CallHookHints@@@Z; xxxCallHook2(tagHOOK *,int,unsigned __int64,__int64,CallHookHints)
0x1401ac576  mov     rcx, [rsi+1E0h]
0x1401ac57d  mov     [rsi+620h], rbx
0x1401ac584  mov     [rbp+3Fh+var_B0], rax
0x1401ac588  mov     r8d, [rcx+4]
0x1401ac58c  mov     rcx, [rsi+1E0h]
0x1401ac593  mov     edx, [rcx+10h]
0x1401ac596  and     r8d, edx
0x1401ac599  test    r8d, 0FFFFFDFFh
0x1401ac5a0  jz      short loc_1401AC5B8
0x1401ac5a2  mov     rcx, [rsi+1E0h]
0x1401ac5a9  mov     edx, [rcx+4]
0x1401ac5ac  mov     rcx, rsi
0x1401ac5af  btr     edx, 9
0x1401ac5b3  call    SetWakeBit
0x1401ac5b8  xor     ecx, ecx; PerformanceFrequency
0x1401ac5ba  call    cs:__imp_KeQueryPerformanceCounter
0x1401ac5c1  nop     dword ptr [rax+rax+00h]
0x1401ac5c6  cmp     [rbp+3Fh+var_B0], 0
0x1401ac5cb  mov     rcx, [rbp+3Fh+var_A0]
0x1401ac5cf  mov     [rcx+28h], rax
0x1401ac5d3  jz      short loc_1401AC5F1
0x1401ac5d5  lea     rcx, [rbp+3Fh+var_98]; this
0x1401ac5d9  call    ??1ThreadLockedPerfRegion@InputTraceLogging@@QEAA@XZ; InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion(void)
0x1401ac5de  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1401ac5e5  nop     dword ptr [rax+rax+00h]
0x1401ac5ea  xor     eax, eax
0x1401ac5ec  jmp     loc_1401AC8F3
0x1401ac5f1  lea     rcx, [rbp+3Fh+var_98]; this
0x1401ac5f5  call    ??1ThreadLockedPerfRegion@InputTraceLogging@@QEAA@XZ; InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion(void)
0x1401ac5fa  mov     ebx, dword ptr [rbp+3Fh+arg_28]
0x1401ac5fd  test    r12b, r12b
0x1401ac600  jz      short loc_1401AC680
0x1401ac602  call    RawInputRequestedForMouse
0x1401ac607  test    eax, eax
0x1401ac609  jz      short loc_1401AC680
0x1401ac60b  mov     rdx, [rbp+3Fh+var_88]
0x1401ac60f  lea     r9, [rbp+3Fh+var_68]
0x1401ac613  xor     eax, eax
0x1401ac615  mov     [rbp+3Fh+var_60], rdx
0x1401ac619  mov     [rbp+3Fh+var_7E], ax
0x1401ac61d  mov     r8d, ebx
0x1401ac620  movzx   eax, word ptr [rdi+2]
0x1401ac624  mov     [rbp+3Fh+var_80], ax
0x1401ac628  mov     eax, [rdi+4]
0x1401ac62b  mov     [rbp+3Fh+var_7C], eax
0x1401ac62e  mov     eax, [rdi+8]
0x1401ac631  mov     [rbp+3Fh+var_78], eax
0x1401ac634  mov     eax, [rdi+0Ch]
0x1401ac637  mov     [rbp+3Fh+var_74], eax
0x1401ac63a  mov     eax, [rdi+10h]
0x1401ac63d  mov     [rbp+3Fh+var_70], eax
0x1401ac640  mov     eax, [rdi+14h]
0x1401ac643  mov     [rbp+3Fh+var_6C], eax
0x1401ac646  mov     rax, rdx
0x1401ac649  mov     rdx, [rbp+3Fh+arg_30]
0x1401ac64d  neg     rax
0x1401ac650  sbb     ecx, ecx
0x1401ac652  xor     eax, eax
0x1401ac654  and     ecx, r14d
0x1401ac657  mov     [rbp+3Fh+var_64], eax
0x1401ac65a  mov     [rbp+3Fh+var_58], rax
0x1401ac65e  lea     rax, [rbp+3Fh+var_80]
0x1401ac662  mov     [rbp+3Fh+var_68], ecx
0x1401ac665  xor     ecx, ecx
0x1401ac667  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1401ac66c  call    EditionPostRawMouseInputMessage
0x1401ac671  test    eax, eax
0x1401ac673  jz      short loc_1401AC680
0x1401ac675  mov     r15d, 9
0x1401ac67b  mov     word ptr [rdi], 0FFFFh
0x1401ac680  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1401ac687  nop     dword ptr [rax+rax+00h]
0x1401ac68c  mov     esi, r13d
0x1401ac68f  and     esi, r14d
0x1401ac692  jz      short loc_1401AC6EB
0x1401ac694  call    cs:__imp_W32GetUserSessionState
0x1401ac69b  nop     dword ptr [rax+rax+00h]
0x1401ac6a0  mov     ebx, 1
0x1401ac6a5  cmp     [rax+8D4Ch], r14d
0x1401ac6ac  jnz     short loc_1401AC6F0
0x1401ac6ae  xor     edx, edx
0x1401ac6b0  mov     ecx, ebx
0x1401ac6b2  call    cs:__imp_EnterCrit
0x1401ac6b9  nop     dword ptr [rax+rax+00h]
0x1401ac6be  call    cs:__imp_W32GetUserSessionState
0x1401ac6c5  nop     dword ptr [rax+rax+00h]
0x1401ac6ca  cmp     [rax+8D4Ch], r14d
0x1401ac6d1  jnz     short loc_1401AC6DD
0x1401ac6d3  mov     edx, ebx
0x1401ac6d5  lea     ecx, [rbx+7]
0x1401ac6d8  call    TransitionCursorSuppressionState
0x1401ac6dd  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1401ac6e4  nop     dword ptr [rax+rax+00h]
0x1401ac6e9  jmp     short loc_1401AC6F0
0x1401ac6eb  mov     ebx, 1
0x1401ac6f0  call    cs:__imp_W32GetUserSessionState
0x1401ac6f7  nop     dword ptr [rax+rax+00h]
0x1401ac6fc  lea     r12, [rax+4B38h]
0x1401ac703  mov     eax, [rbp+3Fh+var_A8]
0x1401ac706  mov     [r12], eax
0x1401ac70a  mov     eax, [rbp+3Fh+var_A4]
0x1401ac70d  mov     [r12+4], eax
0x1401ac712  test    r13b, 4
0x1401ac716  jnz     short loc_1401AC71D
0x1401ac718  mov     ebx, r14d
0x1401ac71b  jmp     short loc_1401AC729
0x1401ac71d  test    rdi, rdi
0x1401ac720  jz      short loc_1401AC727
0x1401ac722  test    [rdi+2], bl
0x1401ac725  jz      short loc_1401AC729
0x1401ac727  xor     ebx, ebx
0x1401ac729  call    cs:__imp_W32GetUserSessionState
0x1401ac730  nop     dword ptr [rax+rax+00h]
0x1401ac735  mov     r8, [r12]
0x1401ac739  lea     rdx, [rbp+3Fh+var_90]
0x1401ac73d  mov     [rsp+0F0h+var_C8], r12
0x1401ac742  mov     r9d, ebx
0x1401ac745  mov     [rsp+0F0h+var_D0], 0
0x1401ac74d  mov     rcx, [rax+8CE8h]
0x1401ac754  call    cs:__imp_?BoundPoint@CCursorClip@@QEAA?AUClipResult@@UtagPOINT@@W4BoundPointOptions@@W4InputTracing_MouseUpdatePositionReason@@PEAU3@@Z; CCursorClip::BoundPoint(tagPOINT,BoundPointOptions,InputTracing_MouseUpdatePositionReason,tagPOINT *)
0x1401ac75b  nop     dword ptr [rax+rax+00h]
0x1401ac760  mov     rax, [rbp+3Fh+var_90]
0x1401ac764  cmp     eax, r14d
0x1401ac767  jnz     short loc_1401AC76E
0x1401ac769  or      r15d, r14d
0x1401ac76c  jmp     short loc_1401AC77F
0x1401ac76e  mov     ecx, 1
0x1401ac773  cmp     eax, ecx
0x1401ac775  jnz     short loc_1401AC77B
0x1401ac777  or      r15d, 4
0x1401ac77b  test    eax, eax
0x1401ac77d  jz      short loc_1401AC793
0x1401ac77f  mov     ecx, dword ptr [rbp+3Fh+var_90+4]
0x1401ac782  call    cs:__imp_SetMouseMoveBoundHitFlagsForMoveSize
0x1401ac789  nop     dword ptr [rax+rax+00h]
0x1401ac78e  mov     ecx, 1
0x1401ac793  test    r13b, 10h
0x1401ac797  jnz     short loc_1401AC7A3
0x1401ac799  xor     r14d, r14d
0x1401ac79c  test    cl, r13b
0x1401ac79f  cmovnz  r14d, ecx
0x1401ac7a3  test    esi, esi
0x1401ac7a5  jz      loc_1401AC8AB
0x1401ac7ab  call    UsingPenCursors
0x1401ac7b0  test    eax, eax
0x1401ac7b2  jz      short loc_1401AC7B9
0x1401ac7b4  call    ?RestoreMouseCursors@@YAXXZ; RestoreMouseCursors(void)
0x1401ac7b9  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x1401ac7bc  lea     rdx, aMovecursor; "MoveCursor"
0x1401ac7c3  lea     rcx, [rbp+3Fh+var_B0]; this
0x1401ac7c7  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x1401ac7cc  mov     r13, [rbp+3Fh+arg_28]
0x1401ac7d0  mov     r8d, [r12+4]
0x1401ac7d5  mov     ecx, r13d
0x1401ac7d8  mov     edx, [r12]
0x1401ac7dc  call    cs:__imp_EtwTraceGreMovePointerBegin
0x1401ac7e3  nop     dword ptr [rax+rax+00h]
0x1401ac7e8  xor     ecx, ecx; PerformanceFrequency
0x1401ac7ea  call    cs:__imp_KeQueryPerformanceCounter
0x1401ac7f1  nop     dword ptr [rax+rax+00h]
0x1401ac7f6  mov     rcx, [rbp+3Fh+var_A0]
0x1401ac7fa  mov     [rcx+10h], rax
0x1401ac7fe  call    cs:__imp_W32GetUserSessionState
0x1401ac805  nop     dword ptr [rax+rax+00h]
0x1401ac80a  mov     ebx, [r12+4]
0x1401ac80f  mov     edi, [r12]
0x1401ac813  mov     rsi, [rax+8D28h]
0x1401ac81a  call    cs:__imp_W32GetUserSessionState
0x1401ac821  nop     dword ptr [rax+rax+00h]
0x1401ac826  mov     r9d, ebx; int
0x1401ac829  mov     r8d, edi; int
0x1401ac82c  mov     rcx, rsi; this
0x1401ac82f  mov     rdx, [rax+0DDA8h]
0x1401ac836  mov     rax, [rbp+3Fh+arg_30]
0x1401ac83a  mov     [rsp+0F0h+var_C0], rax; unsigned __int64
0x1401ac83f  mov     rax, [rbp+3Fh+var_88]
0x1401ac843  mov     rdx, [rdx+28h]; HDEV
0x1401ac847  mov     [rsp+0F0h+var_C8], rax; void *
0x1401ac84c  mov     [rsp+0F0h+var_D0], r14d; unsigned int
0x1401ac851  call    ?MovePointer@CursorApiRouter@@QEAAXPEAUHDEV__@@HHKPEAX_K@Z; CursorApiRouter::MovePointer(HDEV__ *,int,int,ulong,void *,unsigned __int64)
0x1401ac856  xor     ecx, ecx; PerformanceFrequency
0x1401ac858  call    cs:__imp_KeQueryPerformanceCounter
0x1401ac85f  nop     dword ptr [rax+rax+00h]
0x1401ac864  mov     rcx, [rbp+3Fh+var_A0]
0x1401ac868  mov     [rcx+18h], rax
0x1401ac86c  mov     ecx, r13d
0x1401ac86f  mov     r8d, [r12+4]
0x1401ac874  mov     edx, [r12]
0x1401ac878  call    cs:__imp_EtwTraceGreMovePointerEnd
0x1401ac87f  nop     dword ptr [rax+rax+00h]
0x1401ac884  lea     rcx, [rbp+3Fh+var_B0]; this
0x1401ac888  call    ??1ThreadLockedPerfRegion@InputTraceLogging@@QEAA@XZ; InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion(void)
0x1401ac88d  call    cs:__imp_W32GetUserSessionState
0x1401ac894  nop     dword ptr [rax+rax+00h]
0x1401ac899  xor     r8d, r8d; bool
0x1401ac89c  mov     rdx, r12; struct tagPOINT *
0x1401ac89f  mov     rcx, [rax+8D50h]; this
0x1401ac8a6  call    ?zzzUpdateGlobalCursorSize@CCursorSizes@@QEAAXPEBUtagPOINT@@_N@Z; CCursorSizes::zzzUpdateGlobalCursorSize(tagPOINT const *,bool)
0x1401ac8ab  call    IsRemoteConnection
0x1401ac8b0  test    eax, eax
0x1401ac8b2  jnz     short loc_1401AC8F0
0x1401ac8b4  call    cs:__imp_W32GetUserSessionState
0x1401ac8bb  nop     dword ptr [rax+rax+00h]
0x1401ac8c0  cmp     dword ptr [rax+3F70h], 0
0x1401ac8c7  jz      short loc_1401AC8F0
  ... truncated ...
```
