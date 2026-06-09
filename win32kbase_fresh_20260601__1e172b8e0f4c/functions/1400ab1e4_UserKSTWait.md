# UserKSTWait

- ea: `0x1400ab1e4`
- end: `0x1400ab6b7`
- name: `UserKSTWait`
- size: `1235`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400aad60`

## callees

- `0x140029fe8`
- `0x14006ea80`
- `0x14006ed20`
- `0x14006ef38`
- `0x140071828`
- `0x1400718f0`
- `0x1400ab1e4`
- `0x1400ab6c0`
- `0x1400ab78c`
- `0x1401aa4fc`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1400ab292`
- `ntoskrnl!PsIsThreadTerminating` at `0x1400ab292`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x1400ab2c2`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x1400ab2c2`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400ab55c`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400ab55c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ab33f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ab33f`
- `WIN32K!W32GetUserSessionState` at `0x1400ab267`
- `WIN32K!W32GetUserSessionState` at `0x1400ab30e`
- `WIN32K!W32GetUserSessionState` at `0x1400ab380`
- `WIN32K!W32GetUserSessionState` at `0x1400ab3b7`
- `WIN32K!W32GetUserSessionState` at `0x1400ab3d4`
- `WIN32K!W32GetUserSessionState` at `0x1400ab57c`
- `WIN32K!W32GetUserSessionState` at `0x1400ab640`
- `WIN32K!W32GetUserSessionState` at `0x1400ab267`
- `WIN32K!W32GetUserSessionState` at `0x1400ab30e`
- `WIN32K!W32GetUserSessionState` at `0x1400ab380`
- `WIN32K!W32GetUserSessionState` at `0x1400ab3b7`
- `WIN32K!W32GetUserSessionState` at `0x1400ab3d4`
- `WIN32K!W32GetUserSessionState` at `0x1400ab57c`
- `WIN32K!W32GetUserSessionState` at `0x1400ab640`

## string_xrefs

- `0x1400ab2e9`: `HandleKSTThreadSignal`

## pseudocode

```c
__int64 UserKSTWait()
{
  char v0; // di
  char v1; // dl
  char v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // esi
  char v7; // r15
  __int64 UserSessionState; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // ebx
  int v13; // r14d
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rbx
  __int64 v24; // rbx
  char v25; // dl
  char v27; // bl
  bool v28; // r14
  char v29; // si
  bool v30; // r14
  ULONG v31; // eax
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  __int64 v35; // rax
  int v36; // [rsp+28h] [rbp-48h]
  __int128 v37; // [rsp+50h] [rbp-20h] BYREF
  __int128 v38; // [rsp+60h] [rbp-10h]
  int v39; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v40; // [rsp+C0h] [rbp+50h] BYREF

  v0 = 1;
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || (v1 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
  {
    v1 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v2 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
  {
    v2 = 0;
  }
  if ( v1 || v2 )
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v1,
      v2,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      5,
      2,
      15,
      (__int64)WPP_ca5d628c69e43baa083638f2a859e370_Traceguids);
  InputTraceLogging::KST::UserKSTWait();
  v6 = 0;
  v37 = 0;
  v7 = 1;
  v38 = 0;
  while ( 1 )
  {
    UserSessionState = W32GetUserSessionState(v4, v3, v5);
    v39 = 0;
    v9 = *(_QWORD *)(UserSessionState + 19296);
    v37 = 0;
    v38 = 0;
    if ( PsIsThreadTerminating(KeGetCurrentThread()) )
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || (v27 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u) )
      {
        v27 = 0;
      }
      v28 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v35 = W32GetUserSessionState(WPP_GLOBAL_Control, v10, v11);
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v27,
          v28,
          *(_QWORD *)(v35 + 69136),
          2,
          2,
          26,
          (__int64)WPP_bfe1492e3be8328fe0df8b7cdd5a481a_Traceguids);
      }
      v12 = -1073741749;
    }
    else
    {
      LOBYTE(v36) = 1;
      v12 = ZwRemoveIoCompletionEx(*(_QWORD *)(v9 + 2904), &v37, 1, &v39, 0, v36);
    }
    v13 = DWORD2(v37);
    InputTraceLogging::KST::WakeKST((unsigned int)v12, DWORD2(v37));
    if ( v12 < 0 )
      break;
    InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(
      (InputTraceLogging::ThreadLockedPerfRegion *)&v40,
      "HandleKSTThreadSignal",
      0);
    if ( v12 == 257 )
      goto LABEL_15;
    if ( (SDWORD2(v37) & 0x80000000) == 0 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 169);
    v16 = W32GetUserSessionState(v4, v3, v5);
    IOCPDispatcher::Dispatch(*(_QWORD *)(v16 + 19296), v13, v37);
    if ( v13 != -2147483647 )
      goto LABEL_15;
    v21 = *(_QWORD *)(W32GetUserSessionState(v4, v3, v5) + 19296);
    if ( (unsigned int)v37 < *(_DWORD *)(v21 + 2896) && (v23 = 32LL * (unsigned int)v37, *(_QWORD *)(v23 + v21 + 2584)) )
      v24 = *(_QWORD *)(v23 + v21 + 2576);
    else
      v24 = 0;
    v4 = *(_QWORD *)(W32GetUserSessionState(v21, v20, v22) + 3056);
    if ( v24 == *(_QWORD *)(v4 + 48) )
    {
      v6 = 0;
      goto LABEL_27;
    }
    v4 = *(_QWORD *)(W32GetUserSessionState(v4, v3, v5) + 3056);
    if ( v24 == *(_QWORD *)(v4 + 56) )
    {
      v6 = 2;
LABEL_27:
      v7 = 0;
    }
LABEL_15:
    v17 = v40;
    if ( v40 )
    {
      CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( CurrentThreadWin32Thread )
        v19 = *CurrentThreadWin32Thread;
      else
        v19 = 0;
      *(_QWORD *)(v19 + 376) = *(_QWORD *)(v17 + 48);
      InputTraceLogging::ThreadLockedPerfRegion::Cleanup((InputTraceLogging::ThreadLockedPerfRegion *)&v40);
    }
    if ( !v7 )
      goto LABEL_30;
  }
  if ( v12 == -1073741749 )
  {
    v6 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || (v29 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u) )
    {
      v29 = 0;
    }
    v30 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = W32GetUserSessionState(WPP_GLOBAL_Control, v14, v15);
      LOBYTE(v33) = v30;
      LOBYTE(v34) = v29;
      WPP_RECORDER_AND_TRACE_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v34,
        v33,
        *(_QWORD *)(v32 + 69136),
        2,
        2,
        16,
        (__int64)WPP_ca5d628c69e43baa083638f2a859e370_Traceguids,
        v12);
    }
    v6 = 1;
  }
  v31 = RtlNtStatusToDosError(v12);
  UserSetLastError(v31);
LABEL_30:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || (v25 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
  {
    v25 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
    v0 = 0;
  if ( v25 || v0 )
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v25,
      v0,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      5,
      2,
      17,
      (__int64)WPP_ca5d628c69e43baa083638f2a859e370_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x1400ab1e4  mov     [rsp-38h+arg_18], rbx
0x1400ab1e9  push    rbp
0x1400ab1ea  push    rsi
0x1400ab1eb  push    rdi
0x1400ab1ec  push    r12
0x1400ab1ee  push    r13
0x1400ab1f0  push    r14
0x1400ab1f2  push    r15
0x1400ab1f4  mov     rbp, rsp
0x1400ab1f7  sub     rsp, 70h
0x1400ab1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab202  lea     r14, WPP_GLOBAL_Control
0x1400ab209  xor     r12d, r12d
0x1400ab20c  lea     edi, [r12+1]
0x1400ab211  lea     r13d, [r12+2]
0x1400ab216  cmp     rcx, r14
0x1400ab219  jnz     loc_1400AB45E
0x1400ab21f  mov     dl, r12b
0x1400ab222  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ab229  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ab230  jnz     loc_1400AB47C
0x1400ab236  mov     r8b, r12b
0x1400ab239  lea     r9, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400ab240  test    dl, dl
0x1400ab242  jnz     loc_1400AB5FA
0x1400ab248  test    r8b, r8b
0x1400ab24b  jnz     loc_1400AB5FA
0x1400ab251  call    ?UserKSTWait@KST@InputTraceLogging@@SAXXZ; InputTraceLogging::KST::UserKSTWait(void)
0x1400ab256  xorps   xmm0, xmm0
0x1400ab259  mov     esi, r12d
0x1400ab25c  movups  [rbp+var_20], xmm0
0x1400ab260  mov     r15b, dil
0x1400ab263  movups  [rbp+var_10], xmm0
0x1400ab267  call    cs:__imp_W32GetUserSessionState
0x1400ab26e  nop     dword ptr [rax+rax+00h]
0x1400ab273  xorps   xmm0, xmm0
0x1400ab276  mov     [rbp+arg_8], r12d
0x1400ab27a  mov     rbx, [rax+4B60h]
0x1400ab281  movups  [rbp+var_20], xmm0
0x1400ab285  movups  [rbp+var_10], xmm0
0x1400ab289  mov     rcx, gs:188h; Thread
0x1400ab292  call    cs:__imp_PsIsThreadTerminating
0x1400ab299  nop     dword ptr [rax+rax+00h]
0x1400ab29e  test    al, al
0x1400ab2a0  jnz     loc_1400AB4B5
0x1400ab2a6  mov     rcx, [rbx+0B58h]
0x1400ab2ad  lea     r9, [rbp+arg_8]
0x1400ab2b1  mov     byte ptr [rsp+70h+var_48], dil
0x1400ab2b6  lea     rdx, [rbp+var_20]
0x1400ab2ba  mov     r8d, edi
0x1400ab2bd  mov     [rsp+70h+var_50], r12
0x1400ab2c2  call    cs:__imp_ZwRemoveIoCompletionEx
0x1400ab2c9  nop     dword ptr [rax+rax+00h]
0x1400ab2ce  mov     ebx, eax
0x1400ab2d0  mov     r14d, dword ptr [rbp+var_20+8]
0x1400ab2d4  mov     ecx, ebx
0x1400ab2d6  mov     edx, r14d
0x1400ab2d9  call    ?WakeKST@KST@InputTraceLogging@@SAXJW4WaitCompletionPacketPurpose@@@Z; InputTraceLogging::KST::WakeKST(long,WaitCompletionPacketPurpose)
0x1400ab2de  test    ebx, ebx
0x1400ab2e0  js      loc_1400AB516
0x1400ab2e6  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x1400ab2e9  lea     rdx, aHandlekstthrea; "HandleKSTThreadSignal"
0x1400ab2f0  lea     rcx, [rbp+arg_10]; this
0x1400ab2f4  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x1400ab2f9  cmp     ebx, 101h
0x1400ab2ff  jz      short loc_1400AB336
0x1400ab301  test    dword ptr [rbp+var_20+8], 80000000h
0x1400ab308  jz      loc_1400AB4F5
0x1400ab30e  call    cs:__imp_W32GetUserSessionState
0x1400ab315  nop     dword ptr [rax+rax+00h]
0x1400ab31a  mov     r8d, dword ptr [rbp+var_20]
0x1400ab31e  mov     edx, r14d
0x1400ab321  mov     rcx, [rax+4B60h]
0x1400ab328  call    ?Dispatch@IOCPDispatcher@@QEAAXW4WaitCompletionPacketPurpose@@K@Z; IOCPDispatcher::Dispatch(WaitCompletionPacketPurpose,ulong)
0x1400ab32d  cmp     r14d, 80000001h
0x1400ab334  jz      short loc_1400AB380
0x1400ab336  mov     rbx, [rbp+arg_10]
0x1400ab33a  test    rbx, rbx
0x1400ab33d  jz      short loc_1400AB36B
0x1400ab33f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ab346  nop     dword ptr [rax+rax+00h]
0x1400ab34b  test    rax, rax
0x1400ab34e  jz      loc_1400AB401
0x1400ab354  mov     rcx, [rax]
0x1400ab357  mov     rax, [rbx+30h]
0x1400ab35b  mov     [rcx+178h], rax
0x1400ab362  lea     rcx, [rbp+arg_10]; this
0x1400ab366  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x1400ab36b  test    r15b, r15b
0x1400ab36e  jz      loc_1400AB409
0x1400ab374  lea     r14, WPP_GLOBAL_Control
0x1400ab37b  jmp     loc_1400AB267
0x1400ab380  call    cs:__imp_W32GetUserSessionState
0x1400ab387  nop     dword ptr [rax+rax+00h]
0x1400ab38c  mov     rcx, [rax+4B60h]
0x1400ab393  mov     rax, qword ptr [rbp+var_20]
0x1400ab397  cmp     eax, [rcx+0B50h]
0x1400ab39d  jnb     short loc_1400AB3FC
0x1400ab39f  mov     ebx, eax
0x1400ab3a1  shl     rbx, 5
0x1400ab3a5  cmp     [rbx+rcx+0A18h], r12
0x1400ab3ad  jz      short loc_1400AB3FC
0x1400ab3af  mov     rbx, [rbx+rcx+0A10h]
0x1400ab3b7  call    cs:__imp_W32GetUserSessionState
0x1400ab3be  nop     dword ptr [rax+rax+00h]
0x1400ab3c3  mov     rcx, [rax+0BF0h]
0x1400ab3ca  cmp     rbx, [rcx+30h]
0x1400ab3ce  jz      loc_1400AB574
0x1400ab3d4  call    cs:__imp_W32GetUserSessionState
0x1400ab3db  nop     dword ptr [rax+rax+00h]
0x1400ab3e0  mov     rcx, [rax+0BF0h]
0x1400ab3e7  cmp     rbx, [rcx+38h]
0x1400ab3eb  jnz     loc_1400AB336
0x1400ab3f1  mov     esi, r13d
0x1400ab3f4  mov     r15b, r12b
0x1400ab3f7  jmp     loc_1400AB336
0x1400ab3fc  mov     rbx, r12
0x1400ab3ff  jmp     short loc_1400AB3B7
0x1400ab401  mov     rcx, r12
0x1400ab404  jmp     loc_1400AB357
0x1400ab409  lea     r15, WPP_GLOBAL_Control
0x1400ab410  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab417  cmp     rcx, r15
0x1400ab41a  jnz     short loc_1400AB48F
0x1400ab41c  mov     dl, r12b
0x1400ab41f  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ab426  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ab42d  jnz     short loc_1400AB4A9
0x1400ab42f  mov     dil, r12b
0x1400ab432  test    dl, dl
0x1400ab434  jnz     loc_1400AB5C8
0x1400ab43a  test    dil, dil
0x1400ab43d  jnz     loc_1400AB5C8
0x1400ab443  mov     rbx, [rsp+70h+arg_18]
0x1400ab44b  mov     eax, esi
0x1400ab44d  add     rsp, 70h
0x1400ab451  pop     r15
0x1400ab453  pop     r14
0x1400ab455  pop     r13
0x1400ab457  pop     r12
0x1400ab459  pop     rdi
0x1400ab45a  pop     rsi
0x1400ab45b  pop     rbp
0x1400ab45c  retn
0x1400ab45e  mov     eax, [rcx+2Ch]
0x1400ab461  test    r13b, al
0x1400ab464  jz      loc_1400AB21F
0x1400ab46a  cmp     byte ptr [rcx+29h], 5
0x1400ab46e  mov     dl, dil
0x1400ab471  jnb     loc_1400AB222
0x1400ab477  jmp     loc_1400AB21F
0x1400ab47c  mov     r8b, dil
0x1400ab47f  cmp     [rcx+48h], r12w
0x1400ab484  jnz     loc_1400AB239
0x1400ab48a  jmp     loc_1400AB236
0x1400ab48f  mov     eax, [rcx+2Ch]
0x1400ab492  test    r13b, al
0x1400ab495  jz      short loc_1400AB41C
0x1400ab497  cmp     byte ptr [rcx+29h], 5
0x1400ab49b  mov     dl, dil
0x1400ab49e  jnb     loc_1400AB41F
0x1400ab4a4  jmp     loc_1400AB41C
0x1400ab4a9  cmp     [rcx+48h], r12w
0x1400ab4ae  jnz     short loc_1400AB432
0x1400ab4b0  jmp     loc_1400AB42F
0x1400ab4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab4bc  cmp     rcx, r14
0x1400ab4bf  jnz     loc_1400AB622
0x1400ab4c5  mov     bl, r12b
0x1400ab4c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ab4cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ab4d6  setnz   r14b
0x1400ab4da  test    bl, bl
0x1400ab4dc  jnz     loc_1400AB640
0x1400ab4e2  test    r14b, r14b
0x1400ab4e5  jnz     loc_1400AB640
0x1400ab4eb  mov     ebx, 0C000004Bh
0x1400ab4f0  jmp     loc_1400AB2D0
0x1400ab4f5  mov     [rbp+arg_0], 20000h
0x1400ab4fc  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400ab503  mov     edx, [rbp+arg_0]
0x1400ab506  mov     r8d, 0A9h
0x1400ab50c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400ab511  jmp     loc_1400AB30E
0x1400ab516  cmp     ebx, 0C000004Bh
0x1400ab51c  jz      loc_1400AB6A8
0x1400ab522  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab529  lea     r15, WPP_GLOBAL_Control
0x1400ab530  cmp     rcx, r15
0x1400ab533  jnz     loc_1400AB68A
0x1400ab539  mov     sil, r12b
0x1400ab53c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ab543  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ab54a  setnz   r14b
0x1400ab54e  test    sil, sil
0x1400ab551  jnz     short loc_1400AB57C
0x1400ab553  test    r14b, r14b
0x1400ab556  jnz     short loc_1400AB57C
0x1400ab558  mov     esi, edi
0x1400ab55a  mov     ecx, ebx; Status
0x1400ab55c  call    cs:__imp_RtlNtStatusToDosError
0x1400ab563  nop     dword ptr [rax+rax+00h]
0x1400ab568  mov     ecx, eax
0x1400ab56a  call    UserSetLastError
0x1400ab56f  jmp     loc_1400AB410
0x1400ab574  mov     esi, r12d
0x1400ab577  jmp     loc_1400AB3F4
0x1400ab57c  call    cs:__imp_W32GetUserSessionState
0x1400ab583  nop     dword ptr [rax+rax+00h]
0x1400ab588  mov     [rsp+70h+var_30], ebx
0x1400ab58c  lea     rcx, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400ab593  mov     [rsp+70h+var_38], rcx
0x1400ab598  mov     r8b, r14b
0x1400ab59b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab5a2  mov     dl, sil
0x1400ab5a5  mov     r9, [rax+10E10h]
0x1400ab5ac  mov     [rsp+70h+var_40], 10h
0x1400ab5b3  mov     [rsp+70h+var_48], r13d
0x1400ab5b8  mov     rcx, [rcx+18h]
0x1400ab5bc  mov     byte ptr [rsp+70h+var_50], r13b
0x1400ab5c1  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400ab5c6  jmp     short loc_1400AB558
0x1400ab5c8  mov     r9, [rcx+40h]
0x1400ab5cc  lea     r8, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400ab5d3  mov     rcx, [rcx+18h]
0x1400ab5d7  mov     [rsp+70h+var_38], r8
0x1400ab5dc  mov     r8b, dil
0x1400ab5df  mov     [rsp+70h+var_40], 11h
0x1400ab5e6  mov     [rsp+70h+var_48], r13d
0x1400ab5eb  mov     byte ptr [rsp+70h+var_50], 5
0x1400ab5f0  call    WPP_RECORDER_AND_TRACE_SF_
0x1400ab5f5  jmp     loc_1400AB443
0x1400ab5fa  mov     [rsp+70h+var_38], r9
0x1400ab5ff  mov     r9, [rcx+40h]
0x1400ab603  mov     rcx, [rcx+18h]
0x1400ab607  mov     [rsp+70h+var_40], 0Fh
0x1400ab60e  mov     [rsp+70h+var_48], r13d
0x1400ab613  mov     byte ptr [rsp+70h+var_50], 5
0x1400ab618  call    WPP_RECORDER_AND_TRACE_SF_
0x1400ab61d  jmp     loc_1400AB251
0x1400ab622  mov     eax, [rcx+2Ch]
0x1400ab625  test    r13b, al
0x1400ab628  jz      loc_1400AB4C5
0x1400ab62e  mov     bl, dil
0x1400ab631  cmp     [rcx+29h], r13b
0x1400ab635  jnb     loc_1400AB4C8
0x1400ab63b  jmp     loc_1400AB4C5
0x1400ab640  call    cs:__imp_W32GetUserSessionState
0x1400ab647  nop     dword ptr [rax+rax+00h]
0x1400ab64c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab653  mov     r8b, r14b
0x1400ab656  mov     dl, bl
0x1400ab658  mov     r9, [rax+10E10h]
0x1400ab65f  lea     rax, WPP_bfe1492e3be8328fe0df8b7cdd5a481a_Traceguids
0x1400ab666  mov     rcx, [rcx+18h]
0x1400ab66a  mov     [rsp+70h+var_38], rax
0x1400ab66f  mov     [rsp+70h+var_40], 1Ah
0x1400ab676  mov     [rsp+70h+var_48], r13d
0x1400ab67b  mov     byte ptr [rsp+70h+var_50], r13b
0x1400ab680  call    WPP_RECORDER_AND_TRACE_SF_
0x1400ab685  jmp     loc_1400AB4EB
0x1400ab68a  mov     eax, [rcx+2Ch]
0x1400ab68d  test    r13b, al
0x1400ab690  jz      loc_1400AB539
0x1400ab696  mov     sil, dil
0x1400ab699  cmp     [rcx+29h], r13b
0x1400ab69d  jnb     loc_1400AB53C
0x1400ab6a3  jmp     loc_1400AB539
0x1400ab6a8  mov     esi, r12d
0x1400ab6ab  lea     r15, WPP_GLOBAL_Control
0x1400ab6b2  jmp     loc_1400AB55A
```
