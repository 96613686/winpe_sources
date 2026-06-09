# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002fac`
- end: `0x180003242`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002c48`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x180002fac`
- `0x180003e24`
- `0x180004ed0`
- `0x180005a78`
- `0x180005be0`
- `0x180034a90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003057`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800031dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800031dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003152`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003152`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180002fac  mov     [rsp-8+arg_10], rbx
0x180002fb1  push    rbp
0x180002fb2  push    rsi
0x180002fb3  push    rdi
0x180002fb4  push    r14
0x180002fb6  push    r15
0x180002fb8  lea     rbp, [rsp-13D0h]
0x180002fc0  mov     eax, 14D0h
0x180002fc5  call    _alloca_probe
0x180002fca  sub     rsp, rax
0x180002fcd  mov     rax, cs:__security_cookie
0x180002fd4  xor     rax, rsp
0x180002fd7  mov     [rbp+13F0h+var_30], rax
0x180002fde  mov     esi, edx
0x180002fe0  mov     r14, rcx
0x180002fe3  mov     rdi, [rbp+13F0h+arg_28]
0x180002fea  xor     edx, edx; Val
0x180002fec  mov     r8d, 98h; Size
0x180002ff2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002ff7  call    memset_0
0x180002ffc  nop
0x180002ffd  xor     r15d, r15d
0x180003000  mov     [rbp+13F0h+OutputString], r15w
0x180003008  mov     [rbp+13F0h+var_1430], r15b
0x18000300c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003013  mov     ecx, [rdx]; this
0x180003015  mov     [rsp+14F0h+var_14C8], ecx
0x180003019  mov     eax, [rdx+4]
0x18000301c  mov     [rsp+14F0h+var_14C4], eax
0x180003020  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003025  mov     ebx, eax
0x180003027  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000302f  mov     ecx, r15d
0x180003032  lea     eax, [r15+8]
0x180003036  cmp     dword ptr [rdx+8], 1
0x18000303a  cmovz   ecx, eax
0x18000303d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003041  lea     ecx, [rax-7]
0x180003044  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000304c  inc     ecx
0x18000304e  mov     [rsp+14F0h+var_14C0], ecx
0x180003052  mov     [rsp+14F0h+var_14B8], r15
0x180003057  call    cs:__imp_GetCurrentThreadId
0x18000305d  mov     [rsp+14F0h+var_14B0], eax
0x180003061  lea     rax, aWil; "wil"
0x180003068  mov     [rsp+14F0h+var_1498], rax
0x18000306d  mov     [rsp+14F0h+var_1490], esi
0x180003071  mov     [rsp+14F0h+var_148C], ebx
0x180003075  mov     [rsp+14F0h+var_14A8], r15
0x18000307a  mov     [rsp+14F0h+var_14A0], r15
0x18000307f  mov     [rbp+13F0h+var_1448], rdi
0x180003083  mov     [rbp+13F0h+var_1440], r14
0x180003087  mov     [rsp+14F0h+var_1488], r15
0x18000308c  xorps   xmm0, xmm0
0x18000308f  xor     eax, eax
0x180003091  movups  [rbp+13F0h+var_1468], xmm0
0x180003095  mov     [rbp+13F0h+var_1458], rax
0x180003099  xorps   xmm1, xmm1
0x18000309c  movups  [rsp+14F0h+var_1480], xmm1
0x1800030a1  mov     [rbp+13F0h+var_1470], rax
0x1800030a5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800030ac  test    rax, rax
0x1800030af  jz      short loc_1800030BC
0x1800030b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b6  mov     [rbp+13F0h+var_1450], rax
0x1800030ba  jmp     short loc_1800030C0
0x1800030bc  mov     [rbp+13F0h+var_1450], r15
0x1800030c0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800030c7  test    rax, rax
0x1800030ca  jz      short loc_1800030D6
0x1800030cc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800030dd  test    rax, rax
0x1800030e0  jz      short loc_1800030F6
0x1800030e2  mov     r8d, 400h
0x1800030e8  lea     rdx, [rbp+13F0h+var_1430]
0x1800030ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030fd  test    rax, rax
0x180003100  jz      short loc_18000310C
0x180003102  lea     rcx, [rsp+14F0h+var_14D0]
0x180003107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000310c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003113  test    rax, rax
0x180003116  jz      short loc_180003129
0x180003118  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000311d  jnz     short loc_180003129
0x18000311f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003129  cmp     [rsp+14F0h+var_14C8], r15d
0x18000312e  jge     loc_18000323C
0x180003134  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000313b  jnz     short loc_18000315C
0x18000313d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003144  test    rax, rax
0x180003147  jz      short loc_180003152
0x180003149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314e  test    al, al
0x180003150  jmp     short loc_18000315A
0x180003152  call    cs:__imp_IsDebuggerPresent
0x180003158  test    eax, eax
0x18000315a  jz      short loc_180003163
0x18000315c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003161  jz      short loc_180003189
0x180003163  mov     rax, cs:g_pfnResultLoggingCallback
0x18000316a  test    rax, rax
0x18000316d  jz      short loc_1800031E2
0x18000316f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003176  jnz     short loc_1800031E2
0x180003178  xor     r8d, r8d
0x18000317b  xor     edx, edx
0x18000317d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003187  jmp     short loc_1800031E2
0x180003189  mov     ebx, 800h
0x18000318e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003195  test    rax, rax
0x180003198  jz      short loc_1800031B7
0x18000319a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800031a1  jnz     short loc_1800031B7
0x1800031a3  mov     r8d, ebx
0x1800031a6  lea     rdx, [rbp+13F0h+OutputString]
0x1800031ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b7  cmp     [rbp+13F0h+OutputString], r15w
0x1800031bf  jnz     short loc_1800031D5
0x1800031c1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800031c6  mov     rdx, rbx; unsigned __int16 *
0x1800031c9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800031d0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800031d5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800031dc  call    cs:__imp_OutputDebugStringW
0x1800031e2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800031e7  jnz     short loc_1800031F2
0x1800031e9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800031f0  jz      short loc_180003204
0x1800031f2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800031f9  test    rax, rax
0x1800031fc  jz      short loc_180003204
0x1800031fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003203  nop
0x180003204  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003209  jnz     short loc_180003231
0x18000320b  mov     rcx, [rbp+13F0h+var_30]
0x180003212  xor     rcx, rsp; StackCookie
0x180003215  call    __security_check_cookie
0x18000321a  mov     rbx, [rsp+14F0h+arg_10]
0x180003222  add     rsp, 14D0h
0x180003229  pop     r15
0x18000322b  pop     r14
0x18000322d  pop     rdi
0x18000322e  pop     rsi
0x18000322f  pop     rbp
0x180003230  retn
0x180003231  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003236  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000323c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
