# xxxMoveEventAbsolute(long,long,unsigned __int64,void *,_MOUSE_INPUT_DATA *,unsigned __int64,unsigned __int64,_CommitMousePosAndMoveOptions,_MousePacketPerf *)

- ea: `0x1401b1114`
- end: `0x1401b1644`
- name: `?xxxMoveEventAbsolute@@YA?AW4_CommitMousePosAndMoveResult@@JJ_KPEAXPEAU_MOUSE_INPUT_DATA@@00W4_CommitMousePosAndMoveOptions@@PEAU_MousePacketPerf@@@Z`
- size: `1328`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401b1090`

## callees

- `0x140014114`
- `0x140033080`
- `0x14003bb20`
- `0x1400945ec`
- `0x1400bcaa0`
- `0x1400bf728`
- `0x1400c0130`
- `0x1400c459c`
- `0x1401243e0`
- `0x140144100`
- `0x140144650`
- `0x1401939d0`
- `0x1401b1114`
- `0x1401b7e50`
- `0x14026928c`
- `0x140341ff0`

## import_xrefs

- `win32kbase!EtwTraceGreMovePointerEnd` at `0x1401b15a8`
- `win32kbase!EtwTraceGreMovePointerEnd` at `0x1401b15a8`
- `win32kbase!EtwTraceGreMovePointerBegin` at `0x1401b150c`
- `win32kbase!EtwTraceGreMovePointerBegin` at `0x1401b150c`
- `win32kbase!SetMouseMoveBoundHitFlagsForMoveSize` at `0x1401b14b2`
- `win32kbase!SetMouseMoveBoundHitFlagsForMoveSize` at `0x1401b14b2`
- `win32kbase!?BoundPoint@CCursorClip@@QEAA?AUClipResult@@UtagPOINT@@W4BoundPointOptions@@W4InputTracing_MouseUpdatePositionReason@@PEAU3@@Z` at `0x1401b1484`
- `win32kbase!?BoundPoint@CCursorClip@@QEAA?AUClipResult@@UtagPOINT@@W4BoundPointOptions@@W4InputTracing_MouseUpdatePositionReason@@PEAU3@@Z` at `0x1401b1484`
- `win32kbase!EnterCrit` at `0x1401b11e6`
- `win32kbase!EnterCrit` at `0x1401b13e2`
- `win32kbase!EnterCrit` at `0x1401b11e6`
- `win32kbase!EnterCrit` at `0x1401b13e2`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401b130e`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401b13b0`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401b140d`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401b130e`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401b13b0`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401b140d`
- `WIN32K!W32GetUserSessionState` at `0x1401b1172`
- `WIN32K!W32GetUserSessionState` at `0x1401b118b`
- `WIN32K!W32GetUserSessionState` at `0x1401b1240`
- `WIN32K!W32GetUserSessionState` at `0x1401b13c4`
- `WIN32K!W32GetUserSessionState` at `0x1401b13ee`
- `WIN32K!W32GetUserSessionState` at `0x1401b1420`
- `WIN32K!W32GetUserSessionState` at `0x1401b1459`
- `WIN32K!W32GetUserSessionState` at `0x1401b152e`
- `WIN32K!W32GetUserSessionState` at `0x1401b154a`
- `WIN32K!W32GetUserSessionState` at `0x1401b15bd`
- `WIN32K!W32GetUserSessionState` at `0x1401b15e4`
- `WIN32K!W32GetUserSessionState` at `0x1401b15f9`
- `WIN32K!W32GetUserSessionState` at `0x1401b160e`
- `WIN32K!W32GetUserSessionState` at `0x1401b1172`
- `WIN32K!W32GetUserSessionState` at `0x1401b118b`
- `WIN32K!W32GetUserSessionState` at `0x1401b1240`
- `WIN32K!W32GetUserSessionState` at `0x1401b13c4`
- `WIN32K!W32GetUserSessionState` at `0x1401b13ee`
- `WIN32K!W32GetUserSessionState` at `0x1401b1420`
- `WIN32K!W32GetUserSessionState` at `0x1401b1459`
- `WIN32K!W32GetUserSessionState` at `0x1401b152e`
- `WIN32K!W32GetUserSessionState` at `0x1401b154a`
- `WIN32K!W32GetUserSessionState` at `0x1401b15bd`
- `WIN32K!W32GetUserSessionState` at `0x1401b15e4`
- `WIN32K!W32GetUserSessionState` at `0x1401b15f9`
- `WIN32K!W32GetUserSessionState` at `0x1401b160e`
- `HAL!KeQueryPerformanceCounter` at `0x1401b1163`
- `HAL!KeQueryPerformanceCounter` at `0x1401b12ea`
- `HAL!KeQueryPerformanceCounter` at `0x1401b151a`
- `HAL!KeQueryPerformanceCounter` at `0x1401b1588`
- `HAL!KeQueryPerformanceCounter` at `0x1401b1163`
- `HAL!KeQueryPerformanceCounter` at `0x1401b12ea`
- `HAL!KeQueryPerformanceCounter` at `0x1401b151a`
- `HAL!KeQueryPerformanceCounter` at `0x1401b1588`

## string_xrefs

- `0x1401b14ec`: `MoveCursor`
- `0x1401b11fd`: `LowLevelMouseMoveHook`

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
0x1401b1114  push    rbp
0x1401b1116  push    rbx
0x1401b1117  push    rsi
0x1401b1118  push    rdi
0x1401b1119  push    r12
0x1401b111b  push    r13
0x1401b111d  push    r14
0x1401b111f  push    r15
0x1401b1121  lea     rbp, [rsp-7]
0x1401b1126  sub     rsp, 0B8h
0x1401b112d  mov     rax, cs:__security_cookie
0x1401b1134  xor     rax, rsp
0x1401b1137  mov     [rbp+3Fh+var_48], rax
0x1401b113b  mov     rax, [rbp+3Fh+arg_40]
0x1401b1142  mov     r14d, 1
0x1401b1148  mov     rdi, [rbp+3Fh+arg_20]
0x1401b114c  mov     r15d, r14d
0x1401b114f  mov     [rbp+3Fh+var_A8], ecx
0x1401b1152  xor     ecx, ecx; PerformanceFrequency
0x1401b1154  mov     [rbp+3Fh+var_A0], rax
0x1401b1158  mov     [rbp+3Fh+var_88], r9
0x1401b115c  mov     [rbp+3Fh+var_B0], r8
0x1401b1160  mov     [rbp+3Fh+var_A4], edx
0x1401b1163  call    cs:__imp_KeQueryPerformanceCounter
0x1401b116a  nop     dword ptr [rax+rax+00h]
0x1401b116f  mov     rbx, rax
0x1401b1172  call    cs:__imp_W32GetUserSessionState
0x1401b1179  nop     dword ptr [rax+rax+00h]
0x1401b117e  mov     rcx, [rax+4940h]
0x1401b1185  mov     esi, [rcx+2C8h]
0x1401b118b  call    cs:__imp_W32GetUserSessionState
0x1401b1192  nop     dword ptr [rax+rax+00h]
0x1401b1197  mov     rcx, [rax+4940h]
0x1401b119e  mov     rax, [rcx+1F0h]
0x1401b11a5  mov     rcx, [rax]
0x1401b11a8  or      esi, [rcx+10h]
0x1401b11ab  and     esi, 8000h
0x1401b11b1  test    rdi, rdi
0x1401b11b4  jz      short loc_1401B11C4
0x1401b11b6  call    RawInputRequestedForMouse
0x1401b11bb  test    eax, eax
0x1401b11bd  jz      short loc_1401B11C4
0x1401b11bf  mov     r12b, r14b
0x1401b11c2  jmp     short loc_1401B11C7
0x1401b11c4  xor     r12b, r12b
0x1401b11c7  mov     r13d, dword ptr [rbp+3Fh+arg_38]
0x1401b11ce  mov     r14d, 2
0x1401b11d4  test    esi, esi
0x1401b11d6  jnz     short loc_1401B11E1
0x1401b11d8  test    r12b, r12b
0x1401b11db  jz      loc_1401B13BC
0x1401b11e1  xor     edx, edx
0x1401b11e3  mov     ecx, r15d
0x1401b11e6  call    cs:__imp_EnterCrit
0x1401b11ed  nop     dword ptr [rax+rax+00h]
0x1401b11f2  test    esi, esi
0x1401b11f4  jz      loc_1401B132A
0x1401b11fa  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x1401b11fd  lea     rdx, aLowlevelmousem; "LowLevelMouseMoveHook"
0x1401b1204  lea     rcx, [rbp+3Fh+var_98]; this
0x1401b1208  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x1401b120d  mov     eax, [rbp+3Fh+var_A8]
0x1401b1210  mov     [rbp+3Fh+var_68], eax
0x1401b1213  mov     eax, [rbp+3Fh+var_A4]
0x1401b1216  mov     [rbp+3Fh+var_64], eax
0x1401b1219  movzx   eax, r13b
0x1401b121d  and     eax, r15d
0x1401b1220  mov     dword ptr [rbp+3Fh+var_58+4], 0
0x1401b1227  mov     dword ptr [rbp+3Fh+var_60+4], eax
0x1401b122a  mov     rax, [rbp+3Fh+arg_28]
0x1401b122e  mov     dword ptr [rbp+3Fh+var_58], eax
0x1401b1231  mov     rax, [rbp+3Fh+var_B0]
0x1401b1235  mov     [rbp+3Fh+var_50], rax
0x1401b1239  mov     dword ptr [rbp+3Fh+var_60], 0
0x1401b1240  call    cs:__imp_W32GetUserSessionState
0x1401b1247  nop     dword ptr [rax+rax+00h]
0x1401b124c  mov     edx, 0Eh
0x1401b1251  mov     rcx, [rax+4940h]
0x1401b1258  call    PhkFirstValid
0x1401b125d  mov     [rbp+3Fh+var_B0], rax
0x1401b1261  test    rax, rax
0x1401b1264  jz      loc_1401B1321
0x1401b126a  mov     rax, [rbp+3Fh+var_A0]
0x1401b126e  mov     [rax+20h], rbx
0x1401b1272  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401b1277  mov     rcx, [rbp+3Fh+var_B0]
0x1401b127b  lea     r9, [rbp+3Fh+var_68]
0x1401b127f  mov     rsi, rax
0x1401b1282  mov     [rsp+0F0h+var_D0], r15d
0x1401b1287  xor     edx, edx
0x1401b1289  mov     r8d, 200h
0x1401b128f  mov     rbx, [rax+620h]
0x1401b1296  lea     rax, [rbp+3Fh+var_68]
0x1401b129a  mov     [rsi+620h], rax
0x1401b12a1  call    ?xxxCallHook2@@YA_JPEAUtagHOOK@@H_K_JW4CallHookHints@@@Z; xxxCallHook2(tagHOOK *,int,unsigned __int64,__int64,CallHookHints)
0x1401b12a6  mov     rcx, [rsi+1E0h]
0x1401b12ad  mov     [rsi+620h], rbx
0x1401b12b4  mov     [rbp+3Fh+var_B0], rax
0x1401b12b8  mov     r8d, [rcx+4]
0x1401b12bc  mov     rcx, [rsi+1E0h]
0x1401b12c3  mov     edx, [rcx+10h]
0x1401b12c6  and     r8d, edx
0x1401b12c9  test    r8d, 0FFFFFDFFh
0x1401b12d0  jz      short loc_1401B12E8
0x1401b12d2  mov     rcx, [rsi+1E0h]
0x1401b12d9  mov     edx, [rcx+4]
0x1401b12dc  mov     rcx, rsi
0x1401b12df  btr     edx, 9
0x1401b12e3  call    SetWakeBit
0x1401b12e8  xor     ecx, ecx; PerformanceFrequency
0x1401b12ea  call    cs:__imp_KeQueryPerformanceCounter
0x1401b12f1  nop     dword ptr [rax+rax+00h]
0x1401b12f6  cmp     [rbp+3Fh+var_B0], 0
0x1401b12fb  mov     rcx, [rbp+3Fh+var_A0]
0x1401b12ff  mov     [rcx+28h], rax
0x1401b1303  jz      short loc_1401B1321
0x1401b1305  lea     rcx, [rbp+3Fh+var_98]; this
0x1401b1309  call    ??1ThreadLockedPerfRegion@InputTraceLogging@@QEAA@XZ; InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion(void)
0x1401b130e  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1401b1315  nop     dword ptr [rax+rax+00h]
0x1401b131a  xor     eax, eax
0x1401b131c  jmp     loc_1401B1623
0x1401b1321  lea     rcx, [rbp+3Fh+var_98]; this
0x1401b1325  call    ??1ThreadLockedPerfRegion@InputTraceLogging@@QEAA@XZ; InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion(void)
0x1401b132a  mov     ebx, dword ptr [rbp+3Fh+arg_28]
0x1401b132d  test    r12b, r12b
0x1401b1330  jz      short loc_1401B13B0
0x1401b1332  call    RawInputRequestedForMouse
0x1401b1337  test    eax, eax
0x1401b1339  jz      short loc_1401B13B0
0x1401b133b  mov     rdx, [rbp+3Fh+var_88]
0x1401b133f  lea     r9, [rbp+3Fh+var_68]
0x1401b1343  xor     eax, eax
0x1401b1345  mov     [rbp+3Fh+var_60], rdx
0x1401b1349  mov     [rbp+3Fh+var_7E], ax
0x1401b134d  mov     r8d, ebx
0x1401b1350  movzx   eax, word ptr [rdi+2]
0x1401b1354  mov     [rbp+3Fh+var_80], ax
0x1401b1358  mov     eax, [rdi+4]
0x1401b135b  mov     [rbp+3Fh+var_7C], eax
0x1401b135e  mov     eax, [rdi+8]
0x1401b1361  mov     [rbp+3Fh+var_78], eax
0x1401b1364  mov     eax, [rdi+0Ch]
0x1401b1367  mov     [rbp+3Fh+var_74], eax
0x1401b136a  mov     eax, [rdi+10h]
0x1401b136d  mov     [rbp+3Fh+var_70], eax
0x1401b1370  mov     eax, [rdi+14h]
0x1401b1373  mov     [rbp+3Fh+var_6C], eax
0x1401b1376  mov     rax, rdx
0x1401b1379  mov     rdx, [rbp+3Fh+arg_30]
0x1401b137d  neg     rax
0x1401b1380  sbb     ecx, ecx
0x1401b1382  xor     eax, eax
0x1401b1384  and     ecx, r14d
0x1401b1387  mov     [rbp+3Fh+var_64], eax
0x1401b138a  mov     [rbp+3Fh+var_58], rax
0x1401b138e  lea     rax, [rbp+3Fh+var_80]
0x1401b1392  mov     [rbp+3Fh+var_68], ecx
0x1401b1395  xor     ecx, ecx
0x1401b1397  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1401b139c  call    EditionPostRawMouseInputMessage
0x1401b13a1  test    eax, eax
0x1401b13a3  jz      short loc_1401B13B0
0x1401b13a5  mov     r15d, 9
0x1401b13ab  mov     word ptr [rdi], 0FFFFh
0x1401b13b0  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1401b13b7  nop     dword ptr [rax+rax+00h]
0x1401b13bc  mov     esi, r13d
0x1401b13bf  and     esi, r14d
0x1401b13c2  jz      short loc_1401B141B
0x1401b13c4  call    cs:__imp_W32GetUserSessionState
0x1401b13cb  nop     dword ptr [rax+rax+00h]
0x1401b13d0  mov     ebx, 1
0x1401b13d5  cmp     [rax+8D4Ch], r14d
0x1401b13dc  jnz     short loc_1401B1420
0x1401b13de  xor     edx, edx
0x1401b13e0  mov     ecx, ebx
0x1401b13e2  call    cs:__imp_EnterCrit
0x1401b13e9  nop     dword ptr [rax+rax+00h]
0x1401b13ee  call    cs:__imp_W32GetUserSessionState
0x1401b13f5  nop     dword ptr [rax+rax+00h]
0x1401b13fa  cmp     [rax+8D4Ch], r14d
0x1401b1401  jnz     short loc_1401B140D
0x1401b1403  mov     edx, ebx
0x1401b1405  lea     ecx, [rbx+7]
0x1401b1408  call    TransitionCursorSuppressionState
0x1401b140d  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1401b1414  nop     dword ptr [rax+rax+00h]
0x1401b1419  jmp     short loc_1401B1420
0x1401b141b  mov     ebx, 1
0x1401b1420  call    cs:__imp_W32GetUserSessionState
0x1401b1427  nop     dword ptr [rax+rax+00h]
0x1401b142c  lea     r12, [rax+4B38h]
0x1401b1433  mov     eax, [rbp+3Fh+var_A8]
0x1401b1436  mov     [r12], eax
0x1401b143a  mov     eax, [rbp+3Fh+var_A4]
0x1401b143d  mov     [r12+4], eax
0x1401b1442  test    r13b, 4
0x1401b1446  jnz     short loc_1401B144D
0x1401b1448  mov     ebx, r14d
0x1401b144b  jmp     short loc_1401B1459
0x1401b144d  test    rdi, rdi
0x1401b1450  jz      short loc_1401B1457
0x1401b1452  test    [rdi+2], bl
0x1401b1455  jz      short loc_1401B1459
0x1401b1457  xor     ebx, ebx
0x1401b1459  call    cs:__imp_W32GetUserSessionState
0x1401b1460  nop     dword ptr [rax+rax+00h]
0x1401b1465  mov     r8, [r12]
0x1401b1469  lea     rdx, [rbp+3Fh+var_90]
0x1401b146d  mov     [rsp+0F0h+var_C8], r12
0x1401b1472  mov     r9d, ebx
0x1401b1475  mov     [rsp+0F0h+var_D0], 0
0x1401b147d  mov     rcx, [rax+8CE8h]
0x1401b1484  call    cs:__imp_?BoundPoint@CCursorClip@@QEAA?AUClipResult@@UtagPOINT@@W4BoundPointOptions@@W4InputTracing_MouseUpdatePositionReason@@PEAU3@@Z; CCursorClip::BoundPoint(tagPOINT,BoundPointOptions,InputTracing_MouseUpdatePositionReason,tagPOINT *)
0x1401b148b  nop     dword ptr [rax+rax+00h]
0x1401b1490  mov     rax, [rbp+3Fh+var_90]
0x1401b1494  cmp     eax, r14d
0x1401b1497  jnz     short loc_1401B149E
0x1401b1499  or      r15d, r14d
0x1401b149c  jmp     short loc_1401B14AF
0x1401b149e  mov     ecx, 1
0x1401b14a3  cmp     eax, ecx
0x1401b14a5  jnz     short loc_1401B14AB
0x1401b14a7  or      r15d, 4
0x1401b14ab  test    eax, eax
0x1401b14ad  jz      short loc_1401B14C3
0x1401b14af  mov     ecx, dword ptr [rbp+3Fh+var_90+4]
0x1401b14b2  call    cs:__imp_SetMouseMoveBoundHitFlagsForMoveSize
0x1401b14b9  nop     dword ptr [rax+rax+00h]
0x1401b14be  mov     ecx, 1
0x1401b14c3  test    r13b, 10h
0x1401b14c7  jnz     short loc_1401B14D3
0x1401b14c9  xor     r14d, r14d
0x1401b14cc  test    cl, r13b
0x1401b14cf  cmovnz  r14d, ecx
0x1401b14d3  test    esi, esi
0x1401b14d5  jz      loc_1401B15DB
0x1401b14db  call    UsingPenCursors
0x1401b14e0  test    eax, eax
0x1401b14e2  jz      short loc_1401B14E9
0x1401b14e4  call    ?RestoreMouseCursors@@YAXXZ; RestoreMouseCursors(void)
0x1401b14e9  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x1401b14ec  lea     rdx, aMovecursor; "MoveCursor"
0x1401b14f3  lea     rcx, [rbp+3Fh+var_B0]; this
0x1401b14f7  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x1401b14fc  mov     r13, [rbp+3Fh+arg_28]
0x1401b1500  mov     r8d, [r12+4]
0x1401b1505  mov     ecx, r13d
0x1401b1508  mov     edx, [r12]
0x1401b150c  call    cs:__imp_EtwTraceGreMovePointerBegin
0x1401b1513  nop     dword ptr [rax+rax+00h]
0x1401b1518  xor     ecx, ecx; PerformanceFrequency
0x1401b151a  call    cs:__imp_KeQueryPerformanceCounter
0x1401b1521  nop     dword ptr [rax+rax+00h]
0x1401b1526  mov     rcx, [rbp+3Fh+var_A0]
0x1401b152a  mov     [rcx+10h], rax
0x1401b152e  call    cs:__imp_W32GetUserSessionState
0x1401b1535  nop     dword ptr [rax+rax+00h]
0x1401b153a  mov     ebx, [r12+4]
0x1401b153f  mov     edi, [r12]
0x1401b1543  mov     rsi, [rax+8D28h]
0x1401b154a  call    cs:__imp_W32GetUserSessionState
0x1401b1551  nop     dword ptr [rax+rax+00h]
0x1401b1556  mov     r9d, ebx; int
0x1401b1559  mov     r8d, edi; int
0x1401b155c  mov     rcx, rsi; this
0x1401b155f  mov     rdx, [rax+0DDA8h]
0x1401b1566  mov     rax, [rbp+3Fh+arg_30]
0x1401b156a  mov     [rsp+0F0h+var_C0], rax; unsigned __int64
0x1401b156f  mov     rax, [rbp+3Fh+var_88]
0x1401b1573  mov     rdx, [rdx+28h]; HDEV
0x1401b1577  mov     [rsp+0F0h+var_C8], rax; void *
0x1401b157c  mov     [rsp+0F0h+var_D0], r14d; unsigned int
0x1401b1581  call    ?MovePointer@CursorApiRouter@@QEAAXPEAUHDEV__@@HHKPEAX_K@Z; CursorApiRouter::MovePointer(HDEV__ *,int,int,ulong,void *,unsigned __int64)
0x1401b1586  xor     ecx, ecx; PerformanceFrequency
0x1401b1588  call    cs:__imp_KeQueryPerformanceCounter
0x1401b158f  nop     dword ptr [rax+rax+00h]
0x1401b1594  mov     rcx, [rbp+3Fh+var_A0]
0x1401b1598  mov     [rcx+18h], rax
0x1401b159c  mov     ecx, r13d
0x1401b159f  mov     r8d, [r12+4]
0x1401b15a4  mov     edx, [r12]
0x1401b15a8  call    cs:__imp_EtwTraceGreMovePointerEnd
0x1401b15af  nop     dword ptr [rax+rax+00h]
0x1401b15b4  lea     rcx, [rbp+3Fh+var_B0]; this
0x1401b15b8  call    ??1ThreadLockedPerfRegion@InputTraceLogging@@QEAA@XZ; InputTraceLogging::ThreadLockedPerfRegion::~ThreadLockedPerfRegion(void)
0x1401b15bd  call    cs:__imp_W32GetUserSessionState
0x1401b15c4  nop     dword ptr [rax+rax+00h]
0x1401b15c9  xor     r8d, r8d; bool
0x1401b15cc  mov     rdx, r12; struct tagPOINT *
0x1401b15cf  mov     rcx, [rax+8D50h]; this
0x1401b15d6  call    ?zzzUpdateGlobalCursorSize@CCursorSizes@@QEAAXPEBUtagPOINT@@_N@Z; CCursorSizes::zzzUpdateGlobalCursorSize(tagPOINT const *,bool)
0x1401b15db  call    IsRemoteConnection
0x1401b15e0  test    eax, eax
0x1401b15e2  jnz     short loc_1401B1620
0x1401b15e4  call    cs:__imp_W32GetUserSessionState
0x1401b15eb  nop     dword ptr [rax+rax+00h]
0x1401b15f0  cmp     dword ptr [rax+3F70h], 0
0x1401b15f7  jz      short loc_1401B1620
  ... truncated ...
```
