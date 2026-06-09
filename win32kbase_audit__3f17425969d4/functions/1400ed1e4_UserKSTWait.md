# UserKSTWait

- ea: `0x1400ed1e4`
- end: `0x1400ed6b7`
- name: `UserKSTWait`
- size: `1235`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400ecd60`

## callees

- `0x140047050`
- `0x1400472f0`
- `0x140047508`
- `0x140049df8`
- `0x140049ec0`
- `0x1400700d8`
- `0x1400ed1e4`
- `0x1400ed6c0`
- `0x1400ed78c`
- `0x1401aab9c`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1400ed292`
- `ntoskrnl!PsIsThreadTerminating` at `0x1400ed292`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x1400ed2c2`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x1400ed2c2`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400ed55c`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400ed55c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ed33f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ed33f`
- `WIN32K!W32GetUserSessionState` at `0x1400ed267`
- `WIN32K!W32GetUserSessionState` at `0x1400ed30e`
- `WIN32K!W32GetUserSessionState` at `0x1400ed380`
- `WIN32K!W32GetUserSessionState` at `0x1400ed3b7`
- `WIN32K!W32GetUserSessionState` at `0x1400ed3d4`
- `WIN32K!W32GetUserSessionState` at `0x1400ed57c`
- `WIN32K!W32GetUserSessionState` at `0x1400ed640`
- `WIN32K!W32GetUserSessionState` at `0x1400ed267`
- `WIN32K!W32GetUserSessionState` at `0x1400ed30e`
- `WIN32K!W32GetUserSessionState` at `0x1400ed380`
- `WIN32K!W32GetUserSessionState` at `0x1400ed3b7`
- `WIN32K!W32GetUserSessionState` at `0x1400ed3d4`
- `WIN32K!W32GetUserSessionState` at `0x1400ed57c`
- `WIN32K!W32GetUserSessionState` at `0x1400ed640`

## string_xrefs

- `0x1400ed2e9`: `HandleKSTThreadSignal`

## pseudocode

```c
__int64 UserKSTWait()
{
  char v0; // di
  char v1; // dl
  char v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int v5; // esi
  char v6; // r15
  __int64 UserSessionState; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  int v10; // ebx
  int v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 *v14; // rbx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rbx
  char v22; // dl
  char v24; // bl
  char v25; // r14
  char v26; // si
  bool v27; // r14
  ULONG v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  __int64 v33; // rax
  int v34; // [rsp+28h] [rbp-48h]
  __int128 v35; // [rsp+50h] [rbp-20h] BYREF
  __int128 v36; // [rsp+60h] [rbp-10h]
  int v37; // [rsp+B8h] [rbp+48h] BYREF
  __int64 *v38; // [rsp+C0h] [rbp+50h] BYREF

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
      5u,
      2u,
      0xFu,
      (__int64)WPP_ca5d628c69e43baa083638f2a859e370_Traceguids);
  InputTraceLogging::KST::UserKSTWait();
  v5 = 0;
  v35 = 0;
  v6 = 1;
  v36 = 0;
  while ( 1 )
  {
    UserSessionState = W32GetUserSessionState(v4, v3);
    v37 = 0;
    v8 = *(_QWORD *)(UserSessionState + 19296);
    v35 = 0;
    v36 = 0;
    if ( PsIsThreadTerminating(KeGetCurrentThread()) )
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u) )
      {
        v24 = 0;
      }
      v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v33 = W32GetUserSessionState(WPP_GLOBAL_Control, v9);
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v24,
          v25,
          *(_QWORD *)(v33 + 69136),
          2u,
          2u,
          0x1Au,
          (__int64)WPP_9c3dc707b6093594e69bcfa84649926b_Traceguids);
      }
      v10 = -1073741749;
    }
    else
    {
      LOBYTE(v34) = 1;
      v10 = ZwRemoveIoCompletionEx(*(_QWORD *)(v8 + 2904), &v35, 1, &v37, 0, v34);
    }
    v11 = DWORD2(v35);
    InputTraceLogging::KST::WakeKST((unsigned int)v10, DWORD2(v35));
    if ( v10 < 0 )
      break;
    InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(&v38, "HandleKSTThreadSignal", 0);
    if ( v10 == 257 )
      goto LABEL_15;
    if ( (SDWORD2(v35) & 0x80000000) == 0 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 169);
    v13 = W32GetUserSessionState(v4, v3);
    IOCPDispatcher::Dispatch(*(_QWORD *)(v13 + 19296), v11, v35);
    if ( v11 != -2147483647 )
      goto LABEL_15;
    v19 = *(_QWORD *)(W32GetUserSessionState(v4, v3) + 19296);
    if ( (unsigned int)v35 < *(_DWORD *)(v19 + 2896) && (v20 = 32LL * (unsigned int)v35, *(_QWORD *)(v20 + v19 + 2584)) )
      v21 = *(_QWORD *)(v20 + v19 + 2576);
    else
      v21 = 0;
    v4 = *(_QWORD *)(W32GetUserSessionState(v19, v18) + 3056);
    if ( v21 == *(_QWORD *)(v4 + 48) )
    {
      v5 = 0;
      goto LABEL_27;
    }
    v4 = *(_QWORD *)(W32GetUserSessionState(v4, v3) + 3056);
    if ( v21 == *(_QWORD *)(v4 + 56) )
    {
      v5 = 2;
LABEL_27:
      v6 = 0;
    }
LABEL_15:
    v14 = v38;
    if ( v38 )
    {
      CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v4);
      if ( CurrentThreadWin32Thread )
        v17 = *CurrentThreadWin32Thread;
      else
        v17 = 0;
      *(_QWORD *)(v17 + 376) = v14[6];
      InputTraceLogging::ThreadLockedPerfRegion::Cleanup((char **)&v38, v16);
    }
    if ( !v6 )
      goto LABEL_30;
  }
  if ( v10 == -1073741749 )
  {
    v5 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u) )
    {
      v26 = 0;
    }
    v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v30 = W32GetUserSessionState(WPP_GLOBAL_Control, v12);
      LOBYTE(v31) = v27;
      LOBYTE(v32) = v26;
      WPP_RECORDER_AND_TRACE_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v32,
        v31,
        *(_QWORD *)(v30 + 69136),
        2,
        2,
        16,
        (__int64)WPP_ca5d628c69e43baa083638f2a859e370_Traceguids,
        v10);
    }
    v5 = 1;
  }
  v28 = RtlNtStatusToDosError(v10);
  UserSetLastError(v28, v29);
LABEL_30:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || (v22 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
  {
    v22 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
    v0 = 0;
  if ( v22 || v0 )
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v22,
      v0,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      5u,
      2u,
      0x11u,
      (__int64)WPP_ca5d628c69e43baa083638f2a859e370_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x1400ed1e4  mov     [rsp-38h+arg_18], rbx
0x1400ed1e9  push    rbp
0x1400ed1ea  push    rsi
0x1400ed1eb  push    rdi
0x1400ed1ec  push    r12
0x1400ed1ee  push    r13
0x1400ed1f0  push    r14
0x1400ed1f2  push    r15
0x1400ed1f4  mov     rbp, rsp
0x1400ed1f7  sub     rsp, 70h
0x1400ed1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed202  lea     r14, WPP_GLOBAL_Control
0x1400ed209  xor     r12d, r12d
0x1400ed20c  lea     edi, [r12+1]
0x1400ed211  lea     r13d, [r12+2]
0x1400ed216  cmp     rcx, r14
0x1400ed219  jnz     loc_1400ED45E
0x1400ed21f  mov     dl, r12b
0x1400ed222  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ed229  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ed230  jnz     loc_1400ED47C
0x1400ed236  mov     r8b, r12b
0x1400ed239  lea     r9, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400ed240  test    dl, dl
0x1400ed242  jnz     loc_1400ED5FA
0x1400ed248  test    r8b, r8b
0x1400ed24b  jnz     loc_1400ED5FA
0x1400ed251  call    ?UserKSTWait@KST@InputTraceLogging@@SAXXZ; InputTraceLogging::KST::UserKSTWait(void)
0x1400ed256  xorps   xmm0, xmm0
0x1400ed259  mov     esi, r12d
0x1400ed25c  movups  [rbp+var_20], xmm0
0x1400ed260  mov     r15b, dil
0x1400ed263  movups  [rbp+var_10], xmm0
0x1400ed267  call    cs:__imp_W32GetUserSessionState
0x1400ed26e  nop     dword ptr [rax+rax+00h]
0x1400ed273  xorps   xmm0, xmm0
0x1400ed276  mov     [rbp+arg_8], r12d
0x1400ed27a  mov     rbx, [rax+4B60h]
0x1400ed281  movups  [rbp+var_20], xmm0
0x1400ed285  movups  [rbp+var_10], xmm0
0x1400ed289  mov     rcx, gs:188h; Thread
0x1400ed292  call    cs:__imp_PsIsThreadTerminating
0x1400ed299  nop     dword ptr [rax+rax+00h]
0x1400ed29e  test    al, al
0x1400ed2a0  jnz     loc_1400ED4B5
0x1400ed2a6  mov     rcx, [rbx+0B58h]
0x1400ed2ad  lea     r9, [rbp+arg_8]
0x1400ed2b1  mov     byte ptr [rsp+70h+var_48], dil
0x1400ed2b6  lea     rdx, [rbp+var_20]
0x1400ed2ba  mov     r8d, edi
0x1400ed2bd  mov     [rsp+70h+var_50], r12
0x1400ed2c2  call    cs:__imp_ZwRemoveIoCompletionEx
0x1400ed2c9  nop     dword ptr [rax+rax+00h]
0x1400ed2ce  mov     ebx, eax
0x1400ed2d0  mov     r14d, dword ptr [rbp+var_20+8]
0x1400ed2d4  mov     ecx, ebx
0x1400ed2d6  mov     edx, r14d
0x1400ed2d9  call    ?WakeKST@KST@InputTraceLogging@@SAXJW4WaitCompletionPacketPurpose@@@Z; InputTraceLogging::KST::WakeKST(long,WaitCompletionPacketPurpose)
0x1400ed2de  test    ebx, ebx
0x1400ed2e0  js      loc_1400ED516
0x1400ed2e6  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x1400ed2e9  lea     rdx, aHandlekstthrea; "HandleKSTThreadSignal"
0x1400ed2f0  lea     rcx, [rbp+arg_10]; this
0x1400ed2f4  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x1400ed2f9  cmp     ebx, 101h
0x1400ed2ff  jz      short loc_1400ED336
0x1400ed301  test    dword ptr [rbp+var_20+8], 80000000h
0x1400ed308  jz      loc_1400ED4F5
0x1400ed30e  call    cs:__imp_W32GetUserSessionState
0x1400ed315  nop     dword ptr [rax+rax+00h]
0x1400ed31a  mov     r8d, dword ptr [rbp+var_20]
0x1400ed31e  mov     edx, r14d
0x1400ed321  mov     rcx, [rax+4B60h]
0x1400ed328  call    ?Dispatch@IOCPDispatcher@@QEAAXW4WaitCompletionPacketPurpose@@K@Z; IOCPDispatcher::Dispatch(WaitCompletionPacketPurpose,ulong)
0x1400ed32d  cmp     r14d, 80000001h
0x1400ed334  jz      short loc_1400ED380
0x1400ed336  mov     rbx, [rbp+arg_10]
0x1400ed33a  test    rbx, rbx
0x1400ed33d  jz      short loc_1400ED36B
0x1400ed33f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ed346  nop     dword ptr [rax+rax+00h]
0x1400ed34b  test    rax, rax
0x1400ed34e  jz      loc_1400ED401
0x1400ed354  mov     rcx, [rax]
0x1400ed357  mov     rax, [rbx+30h]
0x1400ed35b  mov     [rcx+178h], rax
0x1400ed362  lea     rcx, [rbp+arg_10]; this
0x1400ed366  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x1400ed36b  test    r15b, r15b
0x1400ed36e  jz      loc_1400ED409
0x1400ed374  lea     r14, WPP_GLOBAL_Control
0x1400ed37b  jmp     loc_1400ED267
0x1400ed380  call    cs:__imp_W32GetUserSessionState
0x1400ed387  nop     dword ptr [rax+rax+00h]
0x1400ed38c  mov     rcx, [rax+4B60h]
0x1400ed393  mov     rax, qword ptr [rbp+var_20]
0x1400ed397  cmp     eax, [rcx+0B50h]
0x1400ed39d  jnb     short loc_1400ED3FC
0x1400ed39f  mov     ebx, eax
0x1400ed3a1  shl     rbx, 5
0x1400ed3a5  cmp     [rbx+rcx+0A18h], r12
0x1400ed3ad  jz      short loc_1400ED3FC
0x1400ed3af  mov     rbx, [rbx+rcx+0A10h]
0x1400ed3b7  call    cs:__imp_W32GetUserSessionState
0x1400ed3be  nop     dword ptr [rax+rax+00h]
0x1400ed3c3  mov     rcx, [rax+0BF0h]
0x1400ed3ca  cmp     rbx, [rcx+30h]
0x1400ed3ce  jz      loc_1400ED574
0x1400ed3d4  call    cs:__imp_W32GetUserSessionState
0x1400ed3db  nop     dword ptr [rax+rax+00h]
0x1400ed3e0  mov     rcx, [rax+0BF0h]
0x1400ed3e7  cmp     rbx, [rcx+38h]
0x1400ed3eb  jnz     loc_1400ED336
0x1400ed3f1  mov     esi, r13d
0x1400ed3f4  mov     r15b, r12b
0x1400ed3f7  jmp     loc_1400ED336
0x1400ed3fc  mov     rbx, r12
0x1400ed3ff  jmp     short loc_1400ED3B7
0x1400ed401  mov     rcx, r12
0x1400ed404  jmp     loc_1400ED357
0x1400ed409  lea     r15, WPP_GLOBAL_Control
0x1400ed410  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed417  cmp     rcx, r15
0x1400ed41a  jnz     short loc_1400ED48F
0x1400ed41c  mov     dl, r12b
0x1400ed41f  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ed426  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ed42d  jnz     short loc_1400ED4A9
0x1400ed42f  mov     dil, r12b
0x1400ed432  test    dl, dl
0x1400ed434  jnz     loc_1400ED5C8
0x1400ed43a  test    dil, dil
0x1400ed43d  jnz     loc_1400ED5C8
0x1400ed443  mov     rbx, [rsp+70h+arg_18]
0x1400ed44b  mov     eax, esi
0x1400ed44d  add     rsp, 70h
0x1400ed451  pop     r15
0x1400ed453  pop     r14
0x1400ed455  pop     r13
0x1400ed457  pop     r12
0x1400ed459  pop     rdi
0x1400ed45a  pop     rsi
0x1400ed45b  pop     rbp
0x1400ed45c  retn
0x1400ed45e  mov     eax, [rcx+2Ch]
0x1400ed461  test    r13b, al
0x1400ed464  jz      loc_1400ED21F
0x1400ed46a  cmp     byte ptr [rcx+29h], 5
0x1400ed46e  mov     dl, dil
0x1400ed471  jnb     loc_1400ED222
0x1400ed477  jmp     loc_1400ED21F
0x1400ed47c  mov     r8b, dil
0x1400ed47f  cmp     [rcx+48h], r12w
0x1400ed484  jnz     loc_1400ED239
0x1400ed48a  jmp     loc_1400ED236
0x1400ed48f  mov     eax, [rcx+2Ch]
0x1400ed492  test    r13b, al
0x1400ed495  jz      short loc_1400ED41C
0x1400ed497  cmp     byte ptr [rcx+29h], 5
0x1400ed49b  mov     dl, dil
0x1400ed49e  jnb     loc_1400ED41F
0x1400ed4a4  jmp     loc_1400ED41C
0x1400ed4a9  cmp     [rcx+48h], r12w
0x1400ed4ae  jnz     short loc_1400ED432
0x1400ed4b0  jmp     loc_1400ED42F
0x1400ed4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed4bc  cmp     rcx, r14
0x1400ed4bf  jnz     loc_1400ED622
0x1400ed4c5  mov     bl, r12b
0x1400ed4c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ed4cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ed4d6  setnz   r14b
0x1400ed4da  test    bl, bl
0x1400ed4dc  jnz     loc_1400ED640
0x1400ed4e2  test    r14b, r14b
0x1400ed4e5  jnz     loc_1400ED640
0x1400ed4eb  mov     ebx, 0C000004Bh
0x1400ed4f0  jmp     loc_1400ED2D0
0x1400ed4f5  mov     [rbp+arg_0], 20000h
0x1400ed4fc  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400ed503  mov     edx, [rbp+arg_0]
0x1400ed506  mov     r8d, 0A9h
0x1400ed50c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400ed511  jmp     loc_1400ED30E
0x1400ed516  cmp     ebx, 0C000004Bh
0x1400ed51c  jz      loc_1400ED6A8
0x1400ed522  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed529  lea     r15, WPP_GLOBAL_Control
0x1400ed530  cmp     rcx, r15
0x1400ed533  jnz     loc_1400ED68A
0x1400ed539  mov     sil, r12b
0x1400ed53c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ed543  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ed54a  setnz   r14b
0x1400ed54e  test    sil, sil
0x1400ed551  jnz     short loc_1400ED57C
0x1400ed553  test    r14b, r14b
0x1400ed556  jnz     short loc_1400ED57C
0x1400ed558  mov     esi, edi
0x1400ed55a  mov     ecx, ebx; Status
0x1400ed55c  call    cs:__imp_RtlNtStatusToDosError
0x1400ed563  nop     dword ptr [rax+rax+00h]
0x1400ed568  mov     ecx, eax
0x1400ed56a  call    UserSetLastError
0x1400ed56f  jmp     loc_1400ED410
0x1400ed574  mov     esi, r12d
0x1400ed577  jmp     loc_1400ED3F4
0x1400ed57c  call    cs:__imp_W32GetUserSessionState
0x1400ed583  nop     dword ptr [rax+rax+00h]
0x1400ed588  mov     [rsp+70h+var_30], ebx
0x1400ed58c  lea     rcx, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400ed593  mov     [rsp+70h+var_38], rcx
0x1400ed598  mov     r8b, r14b
0x1400ed59b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed5a2  mov     dl, sil
0x1400ed5a5  mov     r9, [rax+10E10h]
0x1400ed5ac  mov     [rsp+70h+var_40], 10h
0x1400ed5b3  mov     [rsp+70h+var_48], r13d
0x1400ed5b8  mov     rcx, [rcx+18h]
0x1400ed5bc  mov     byte ptr [rsp+70h+var_50], r13b
0x1400ed5c1  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400ed5c6  jmp     short loc_1400ED558
0x1400ed5c8  mov     r9, [rcx+40h]
0x1400ed5cc  lea     r8, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400ed5d3  mov     rcx, [rcx+18h]
0x1400ed5d7  mov     [rsp+70h+var_38], r8
0x1400ed5dc  mov     r8b, dil
0x1400ed5df  mov     [rsp+70h+var_40], 11h
0x1400ed5e6  mov     [rsp+70h+var_48], r13d
0x1400ed5eb  mov     byte ptr [rsp+70h+var_50], 5
0x1400ed5f0  call    WPP_RECORDER_AND_TRACE_SF_
0x1400ed5f5  jmp     loc_1400ED443
0x1400ed5fa  mov     [rsp+70h+var_38], r9
0x1400ed5ff  mov     r9, [rcx+40h]
0x1400ed603  mov     rcx, [rcx+18h]
0x1400ed607  mov     [rsp+70h+var_40], 0Fh
0x1400ed60e  mov     [rsp+70h+var_48], r13d
0x1400ed613  mov     byte ptr [rsp+70h+var_50], 5
0x1400ed618  call    WPP_RECORDER_AND_TRACE_SF_
0x1400ed61d  jmp     loc_1400ED251
0x1400ed622  mov     eax, [rcx+2Ch]
0x1400ed625  test    r13b, al
0x1400ed628  jz      loc_1400ED4C5
0x1400ed62e  mov     bl, dil
0x1400ed631  cmp     [rcx+29h], r13b
0x1400ed635  jnb     loc_1400ED4C8
0x1400ed63b  jmp     loc_1400ED4C5
0x1400ed640  call    cs:__imp_W32GetUserSessionState
0x1400ed647  nop     dword ptr [rax+rax+00h]
0x1400ed64c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed653  mov     r8b, r14b
0x1400ed656  mov     dl, bl
0x1400ed658  mov     r9, [rax+10E10h]
0x1400ed65f  lea     rax, WPP_9c3dc707b6093594e69bcfa84649926b_Traceguids
0x1400ed666  mov     rcx, [rcx+18h]
0x1400ed66a  mov     [rsp+70h+var_38], rax
0x1400ed66f  mov     [rsp+70h+var_40], 1Ah
0x1400ed676  mov     [rsp+70h+var_48], r13d
0x1400ed67b  mov     byte ptr [rsp+70h+var_50], r13b
0x1400ed680  call    WPP_RECORDER_AND_TRACE_SF_
0x1400ed685  jmp     loc_1400ED4EB
0x1400ed68a  mov     eax, [rcx+2Ch]
0x1400ed68d  test    r13b, al
0x1400ed690  jz      loc_1400ED539
0x1400ed696  mov     sil, dil
0x1400ed699  cmp     [rcx+29h], r13b
0x1400ed69d  jnb     loc_1400ED53C
0x1400ed6a3  jmp     loc_1400ED539
0x1400ed6a8  mov     esi, r12d
0x1400ed6ab  lea     r15, WPP_GLOBAL_Control
0x1400ed6b2  jmp     loc_1400ED55A
```
