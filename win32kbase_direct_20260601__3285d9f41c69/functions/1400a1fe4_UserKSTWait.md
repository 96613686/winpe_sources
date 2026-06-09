# UserKSTWait

- ea: `0x1400a1fe4`
- end: `0x1400a24b7`
- name: `UserKSTWait`
- size: `1235`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400a1b60`

## callees

- `0x140033268`
- `0x14006fc20`
- `0x14006fec0`
- `0x1400700d8`
- `0x1400729c8`
- `0x140072a90`
- `0x1400a1fe4`
- `0x1400a24c0`
- `0x1400a258c`
- `0x1401a9f9c`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1400a2092`
- `ntoskrnl!PsIsThreadTerminating` at `0x1400a2092`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x1400a20c2`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x1400a20c2`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400a235c`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400a235c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400a213f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400a213f`
- `WIN32K!W32GetUserSessionState` at `0x1400a2067`
- `WIN32K!W32GetUserSessionState` at `0x1400a210e`
- `WIN32K!W32GetUserSessionState` at `0x1400a2180`
- `WIN32K!W32GetUserSessionState` at `0x1400a21b7`
- `WIN32K!W32GetUserSessionState` at `0x1400a21d4`
- `WIN32K!W32GetUserSessionState` at `0x1400a237c`
- `WIN32K!W32GetUserSessionState` at `0x1400a2440`
- `WIN32K!W32GetUserSessionState` at `0x1400a2067`
- `WIN32K!W32GetUserSessionState` at `0x1400a210e`
- `WIN32K!W32GetUserSessionState` at `0x1400a2180`
- `WIN32K!W32GetUserSessionState` at `0x1400a21b7`
- `WIN32K!W32GetUserSessionState` at `0x1400a21d4`
- `WIN32K!W32GetUserSessionState` at `0x1400a237c`
- `WIN32K!W32GetUserSessionState` at `0x1400a2440`

## string_xrefs

- `0x1400a20e9`: `HandleKSTThreadSignal`

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
0x1400a1fe4  mov     [rsp-38h+arg_18], rbx
0x1400a1fe9  push    rbp
0x1400a1fea  push    rsi
0x1400a1feb  push    rdi
0x1400a1fec  push    r12
0x1400a1fee  push    r13
0x1400a1ff0  push    r14
0x1400a1ff2  push    r15
0x1400a1ff4  mov     rbp, rsp
0x1400a1ff7  sub     rsp, 70h
0x1400a1ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2002  lea     r14, WPP_GLOBAL_Control
0x1400a2009  xor     r12d, r12d
0x1400a200c  lea     edi, [r12+1]
0x1400a2011  lea     r13d, [r12+2]
0x1400a2016  cmp     rcx, r14
0x1400a2019  jnz     loc_1400A225E
0x1400a201f  mov     dl, r12b
0x1400a2022  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a2029  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a2030  jnz     loc_1400A227C
0x1400a2036  mov     r8b, r12b
0x1400a2039  lea     r9, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400a2040  test    dl, dl
0x1400a2042  jnz     loc_1400A23FA
0x1400a2048  test    r8b, r8b
0x1400a204b  jnz     loc_1400A23FA
0x1400a2051  call    ?UserKSTWait@KST@InputTraceLogging@@SAXXZ; InputTraceLogging::KST::UserKSTWait(void)
0x1400a2056  xorps   xmm0, xmm0
0x1400a2059  mov     esi, r12d
0x1400a205c  movups  [rbp+var_20], xmm0
0x1400a2060  mov     r15b, dil
0x1400a2063  movups  [rbp+var_10], xmm0
0x1400a2067  call    cs:__imp_W32GetUserSessionState
0x1400a206e  nop     dword ptr [rax+rax+00h]
0x1400a2073  xorps   xmm0, xmm0
0x1400a2076  mov     [rbp+arg_8], r12d
0x1400a207a  mov     rbx, [rax+4B60h]
0x1400a2081  movups  [rbp+var_20], xmm0
0x1400a2085  movups  [rbp+var_10], xmm0
0x1400a2089  mov     rcx, gs:188h; Thread
0x1400a2092  call    cs:__imp_PsIsThreadTerminating
0x1400a2099  nop     dword ptr [rax+rax+00h]
0x1400a209e  test    al, al
0x1400a20a0  jnz     loc_1400A22B5
0x1400a20a6  mov     rcx, [rbx+0B58h]
0x1400a20ad  lea     r9, [rbp+arg_8]
0x1400a20b1  mov     byte ptr [rsp+70h+var_48], dil
0x1400a20b6  lea     rdx, [rbp+var_20]
0x1400a20ba  mov     r8d, edi
0x1400a20bd  mov     [rsp+70h+var_50], r12
0x1400a20c2  call    cs:__imp_ZwRemoveIoCompletionEx
0x1400a20c9  nop     dword ptr [rax+rax+00h]
0x1400a20ce  mov     ebx, eax
0x1400a20d0  mov     r14d, dword ptr [rbp+var_20+8]
0x1400a20d4  mov     ecx, ebx
0x1400a20d6  mov     edx, r14d
0x1400a20d9  call    ?WakeKST@KST@InputTraceLogging@@SAXJW4WaitCompletionPacketPurpose@@@Z; InputTraceLogging::KST::WakeKST(long,WaitCompletionPacketPurpose)
0x1400a20de  test    ebx, ebx
0x1400a20e0  js      loc_1400A2316
0x1400a20e6  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x1400a20e9  lea     rdx, aHandlekstthrea; "HandleKSTThreadSignal"
0x1400a20f0  lea     rcx, [rbp+arg_10]; this
0x1400a20f4  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x1400a20f9  cmp     ebx, 101h
0x1400a20ff  jz      short loc_1400A2136
0x1400a2101  test    dword ptr [rbp+var_20+8], 80000000h
0x1400a2108  jz      loc_1400A22F5
0x1400a210e  call    cs:__imp_W32GetUserSessionState
0x1400a2115  nop     dword ptr [rax+rax+00h]
0x1400a211a  mov     r8d, dword ptr [rbp+var_20]
0x1400a211e  mov     edx, r14d
0x1400a2121  mov     rcx, [rax+4B60h]
0x1400a2128  call    ?Dispatch@IOCPDispatcher@@QEAAXW4WaitCompletionPacketPurpose@@K@Z; IOCPDispatcher::Dispatch(WaitCompletionPacketPurpose,ulong)
0x1400a212d  cmp     r14d, 80000001h
0x1400a2134  jz      short loc_1400A2180
0x1400a2136  mov     rbx, [rbp+arg_10]
0x1400a213a  test    rbx, rbx
0x1400a213d  jz      short loc_1400A216B
0x1400a213f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400a2146  nop     dword ptr [rax+rax+00h]
0x1400a214b  test    rax, rax
0x1400a214e  jz      loc_1400A2201
0x1400a2154  mov     rcx, [rax]
0x1400a2157  mov     rax, [rbx+30h]
0x1400a215b  mov     [rcx+178h], rax
0x1400a2162  lea     rcx, [rbp+arg_10]; this
0x1400a2166  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x1400a216b  test    r15b, r15b
0x1400a216e  jz      loc_1400A2209
0x1400a2174  lea     r14, WPP_GLOBAL_Control
0x1400a217b  jmp     loc_1400A2067
0x1400a2180  call    cs:__imp_W32GetUserSessionState
0x1400a2187  nop     dword ptr [rax+rax+00h]
0x1400a218c  mov     rcx, [rax+4B60h]
0x1400a2193  mov     rax, qword ptr [rbp+var_20]
0x1400a2197  cmp     eax, [rcx+0B50h]
0x1400a219d  jnb     short loc_1400A21FC
0x1400a219f  mov     ebx, eax
0x1400a21a1  shl     rbx, 5
0x1400a21a5  cmp     [rbx+rcx+0A18h], r12
0x1400a21ad  jz      short loc_1400A21FC
0x1400a21af  mov     rbx, [rbx+rcx+0A10h]
0x1400a21b7  call    cs:__imp_W32GetUserSessionState
0x1400a21be  nop     dword ptr [rax+rax+00h]
0x1400a21c3  mov     rcx, [rax+0BF0h]
0x1400a21ca  cmp     rbx, [rcx+30h]
0x1400a21ce  jz      loc_1400A2374
0x1400a21d4  call    cs:__imp_W32GetUserSessionState
0x1400a21db  nop     dword ptr [rax+rax+00h]
0x1400a21e0  mov     rcx, [rax+0BF0h]
0x1400a21e7  cmp     rbx, [rcx+38h]
0x1400a21eb  jnz     loc_1400A2136
0x1400a21f1  mov     esi, r13d
0x1400a21f4  mov     r15b, r12b
0x1400a21f7  jmp     loc_1400A2136
0x1400a21fc  mov     rbx, r12
0x1400a21ff  jmp     short loc_1400A21B7
0x1400a2201  mov     rcx, r12
0x1400a2204  jmp     loc_1400A2157
0x1400a2209  lea     r15, WPP_GLOBAL_Control
0x1400a2210  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2217  cmp     rcx, r15
0x1400a221a  jnz     short loc_1400A228F
0x1400a221c  mov     dl, r12b
0x1400a221f  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a2226  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a222d  jnz     short loc_1400A22A9
0x1400a222f  mov     dil, r12b
0x1400a2232  test    dl, dl
0x1400a2234  jnz     loc_1400A23C8
0x1400a223a  test    dil, dil
0x1400a223d  jnz     loc_1400A23C8
0x1400a2243  mov     rbx, [rsp+70h+arg_18]
0x1400a224b  mov     eax, esi
0x1400a224d  add     rsp, 70h
0x1400a2251  pop     r15
0x1400a2253  pop     r14
0x1400a2255  pop     r13
0x1400a2257  pop     r12
0x1400a2259  pop     rdi
0x1400a225a  pop     rsi
0x1400a225b  pop     rbp
0x1400a225c  retn
0x1400a225e  mov     eax, [rcx+2Ch]
0x1400a2261  test    r13b, al
0x1400a2264  jz      loc_1400A201F
0x1400a226a  cmp     byte ptr [rcx+29h], 5
0x1400a226e  mov     dl, dil
0x1400a2271  jnb     loc_1400A2022
0x1400a2277  jmp     loc_1400A201F
0x1400a227c  mov     r8b, dil
0x1400a227f  cmp     [rcx+48h], r12w
0x1400a2284  jnz     loc_1400A2039
0x1400a228a  jmp     loc_1400A2036
0x1400a228f  mov     eax, [rcx+2Ch]
0x1400a2292  test    r13b, al
0x1400a2295  jz      short loc_1400A221C
0x1400a2297  cmp     byte ptr [rcx+29h], 5
0x1400a229b  mov     dl, dil
0x1400a229e  jnb     loc_1400A221F
0x1400a22a4  jmp     loc_1400A221C
0x1400a22a9  cmp     [rcx+48h], r12w
0x1400a22ae  jnz     short loc_1400A2232
0x1400a22b0  jmp     loc_1400A222F
0x1400a22b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a22bc  cmp     rcx, r14
0x1400a22bf  jnz     loc_1400A2422
0x1400a22c5  mov     bl, r12b
0x1400a22c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a22cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a22d6  setnz   r14b
0x1400a22da  test    bl, bl
0x1400a22dc  jnz     loc_1400A2440
0x1400a22e2  test    r14b, r14b
0x1400a22e5  jnz     loc_1400A2440
0x1400a22eb  mov     ebx, 0C000004Bh
0x1400a22f0  jmp     loc_1400A20D0
0x1400a22f5  mov     [rbp+arg_0], 20000h
0x1400a22fc  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400a2303  mov     edx, [rbp+arg_0]
0x1400a2306  mov     r8d, 0A9h
0x1400a230c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400a2311  jmp     loc_1400A210E
0x1400a2316  cmp     ebx, 0C000004Bh
0x1400a231c  jz      loc_1400A24A8
0x1400a2322  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2329  lea     r15, WPP_GLOBAL_Control
0x1400a2330  cmp     rcx, r15
0x1400a2333  jnz     loc_1400A248A
0x1400a2339  mov     sil, r12b
0x1400a233c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a2343  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a234a  setnz   r14b
0x1400a234e  test    sil, sil
0x1400a2351  jnz     short loc_1400A237C
0x1400a2353  test    r14b, r14b
0x1400a2356  jnz     short loc_1400A237C
0x1400a2358  mov     esi, edi
0x1400a235a  mov     ecx, ebx; Status
0x1400a235c  call    cs:__imp_RtlNtStatusToDosError
0x1400a2363  nop     dword ptr [rax+rax+00h]
0x1400a2368  mov     ecx, eax
0x1400a236a  call    UserSetLastError
0x1400a236f  jmp     loc_1400A2210
0x1400a2374  mov     esi, r12d
0x1400a2377  jmp     loc_1400A21F4
0x1400a237c  call    cs:__imp_W32GetUserSessionState
0x1400a2383  nop     dword ptr [rax+rax+00h]
0x1400a2388  mov     [rsp+70h+var_30], ebx
0x1400a238c  lea     rcx, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400a2393  mov     [rsp+70h+var_38], rcx
0x1400a2398  mov     r8b, r14b
0x1400a239b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a23a2  mov     dl, sil
0x1400a23a5  mov     r9, [rax+10E10h]
0x1400a23ac  mov     [rsp+70h+var_40], 10h
0x1400a23b3  mov     [rsp+70h+var_48], r13d
0x1400a23b8  mov     rcx, [rcx+18h]
0x1400a23bc  mov     byte ptr [rsp+70h+var_50], r13b
0x1400a23c1  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400a23c6  jmp     short loc_1400A2358
0x1400a23c8  mov     r9, [rcx+40h]
0x1400a23cc  lea     r8, WPP_ca5d628c69e43baa083638f2a859e370_Traceguids
0x1400a23d3  mov     rcx, [rcx+18h]
0x1400a23d7  mov     [rsp+70h+var_38], r8
0x1400a23dc  mov     r8b, dil
0x1400a23df  mov     [rsp+70h+var_40], 11h
0x1400a23e6  mov     [rsp+70h+var_48], r13d
0x1400a23eb  mov     byte ptr [rsp+70h+var_50], 5
0x1400a23f0  call    WPP_RECORDER_AND_TRACE_SF_
0x1400a23f5  jmp     loc_1400A2243
0x1400a23fa  mov     [rsp+70h+var_38], r9
0x1400a23ff  mov     r9, [rcx+40h]
0x1400a2403  mov     rcx, [rcx+18h]
0x1400a2407  mov     [rsp+70h+var_40], 0Fh
0x1400a240e  mov     [rsp+70h+var_48], r13d
0x1400a2413  mov     byte ptr [rsp+70h+var_50], 5
0x1400a2418  call    WPP_RECORDER_AND_TRACE_SF_
0x1400a241d  jmp     loc_1400A2051
0x1400a2422  mov     eax, [rcx+2Ch]
0x1400a2425  test    r13b, al
0x1400a2428  jz      loc_1400A22C5
0x1400a242e  mov     bl, dil
0x1400a2431  cmp     [rcx+29h], r13b
0x1400a2435  jnb     loc_1400A22C8
0x1400a243b  jmp     loc_1400A22C5
0x1400a2440  call    cs:__imp_W32GetUserSessionState
0x1400a2447  nop     dword ptr [rax+rax+00h]
0x1400a244c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2453  mov     r8b, r14b
0x1400a2456  mov     dl, bl
0x1400a2458  mov     r9, [rax+10E10h]
0x1400a245f  lea     rax, WPP_bfe1492e3be8328fe0df8b7cdd5a481a_Traceguids
0x1400a2466  mov     rcx, [rcx+18h]
0x1400a246a  mov     [rsp+70h+var_38], rax
0x1400a246f  mov     [rsp+70h+var_40], 1Ah
0x1400a2476  mov     [rsp+70h+var_48], r13d
0x1400a247b  mov     byte ptr [rsp+70h+var_50], r13b
0x1400a2480  call    WPP_RECORDER_AND_TRACE_SF_
0x1400a2485  jmp     loc_1400A22EB
0x1400a248a  mov     eax, [rcx+2Ch]
0x1400a248d  test    r13b, al
0x1400a2490  jz      loc_1400A2339
0x1400a2496  mov     sil, dil
0x1400a2499  cmp     [rcx+29h], r13b
0x1400a249d  jnb     loc_1400A233C
0x1400a24a3  jmp     loc_1400A2339
0x1400a24a8  mov     esi, r12d
0x1400a24ab  lea     r15, WPP_GLOBAL_Control
0x1400a24b2  jmp     loc_1400A235A
```
