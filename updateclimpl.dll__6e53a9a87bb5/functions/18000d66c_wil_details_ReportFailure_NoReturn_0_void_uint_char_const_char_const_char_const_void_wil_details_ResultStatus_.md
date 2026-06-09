# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000d66c`
- end: `0x18000d93a`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d940`

## callees

- `0x180004298`
- `0x180004724`
- `0x180004aec`
- `0x180005798`
- `0x180005f00`
- `0x18000d66c`
- `0x180014870`
- `0x1800148e0`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d72d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d72d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d8ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d8ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d82a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d82a`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8)
{
  bool v11; // di
  unsigned int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v18; // r9
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  unsigned __int64 v21[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v22[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset(v21, 0, 0x98u);
  OutputString[0] = 0;
  v22[0] = 0;
  v21[1] = *a7;
  v12 = wil::details::RecordException((wil::details *)LODWORD(v21[1]), (int)a7);
  LODWORD(v21[0]) = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  HIDWORD(v21[0]) = v13;
  LODWORD(v21[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v21[3] = (unsigned __int64)a8, v15) )
    v21[3] = 0;
  LODWORD(v21[4]) = GetCurrentThreadId();
  v21[7] = a3;
  v21[8] = __PAIR64__(v12, a2);
  v21[5] = 0;
  v21[6] = 0;
  v21[17] = a6;
  v21[18] = a1;
  memset(&v21[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v21[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v21[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v21, v22, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v21[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v21);
  if ( SLODWORD(v21[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (IsDebuggerPresent = ::IsDebuggerPresent())
      : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
        !(_DWORD)IsDebuggerPresent)
    || (v19 = 1, (v21[0] & 0x200000000LL) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v21, v18);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v21, 0, 0);
  }
  if ( ((v21[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v21[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v21, v16);
  if ( v11 )
    ((void (__fastcall *)(unsigned __int64 *, WCHAR *))g_pfnThrowPlatformException)(v21, OutputString);
  wil::ThrowResultException((wil *)v21, v16);
  wil::details::WilFailFast((wil::details *)v21, v20);
}

```

## disassembly

```asm
0x18000d66c  mov     [rsp-8+arg_18], rbx
0x18000d671  push    rbp
0x18000d672  push    rsi
0x18000d673  push    rdi
0x18000d674  push    r12
0x18000d676  push    r13
0x18000d678  push    r14
0x18000d67a  push    r15
0x18000d67c  lea     rbp, [rsp-13C0h]
0x18000d684  mov     eax, 14C0h
0x18000d689  call    _alloca_probe
0x18000d68e  sub     rsp, rax
0x18000d691  mov     r14, r8
0x18000d694  mov     esi, edx
0x18000d696  mov     rbx, rcx
0x18000d699  mov     r15, [rbp+13F0h+arg_28]
0x18000d6a0  xor     r13d, r13d
0x18000d6a3  cmp     cs:g_pfnThrowPlatformException, r13
0x18000d6aa  setnz   dil
0x18000d6ae  xor     edx, edx; Val
0x18000d6b0  mov     r8d, 98h; Size
0x18000d6b6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000d6bb  call    memset
0x18000d6c0  nop
0x18000d6c1  mov     [rbp+13F0h+OutputString], r13w
0x18000d6c9  mov     [rbp+13F0h+var_1430], r13b
0x18000d6cd  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000d6d4  mov     ecx, [rdx]; this
0x18000d6d6  mov     [rsp+14F0h+var_14C8], ecx
0x18000d6da  mov     eax, [rdx+4]
0x18000d6dd  mov     [rsp+14F0h+var_14C4], eax
0x18000d6e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000d6e6  mov     r12d, eax
0x18000d6e9  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000d6ee  mov     ecx, r13d
0x18000d6f1  lea     eax, [r13+8]
0x18000d6f5  cmp     dword ptr [rdx+8], 1
0x18000d6f9  cmovz   ecx, eax
0x18000d6fc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000d700  lea     ecx, [rax-7]
0x18000d703  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d70b  inc     ecx
0x18000d70d  mov     [rsp+14F0h+var_14C0], ecx
0x18000d711  mov     rcx, [rbp+13F0h+arg_38]
0x18000d718  test    rcx, rcx
0x18000d71b  jz      short loc_18000D728
0x18000d71d  cmp     [rcx], r13w
0x18000d721  mov     [rsp+14F0h+var_14B8], rcx
0x18000d726  jnz     short loc_18000D72D
0x18000d728  mov     [rsp+14F0h+var_14B8], r13
0x18000d72d  call    cs:__imp_GetCurrentThreadId
0x18000d733  mov     [rsp+14F0h+var_14B0], eax
0x18000d737  mov     [rsp+14F0h+var_1498], r14
0x18000d73c  mov     [rsp+14F0h+var_1490], esi
0x18000d740  mov     [rsp+14F0h+var_148C], r12d
0x18000d745  mov     [rsp+14F0h+var_14A8], r13
0x18000d74a  mov     [rsp+14F0h+var_14A0], r13
0x18000d74f  mov     [rbp+13F0h+var_1448], r15
0x18000d753  mov     [rbp+13F0h+var_1440], rbx
0x18000d757  mov     [rsp+14F0h+var_1488], r13
0x18000d75c  xorps   xmm0, xmm0
0x18000d75f  xor     eax, eax
0x18000d761  movups  [rbp+13F0h+var_1468], xmm0
0x18000d765  mov     [rbp+13F0h+var_1458], rax
0x18000d769  xorps   xmm1, xmm1
0x18000d76c  movups  [rsp+14F0h+var_1480], xmm1
0x18000d771  mov     [rbp+13F0h+var_1470], rax
0x18000d775  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d77c  test    rax, rax
0x18000d77f  jz      short loc_18000D78C
0x18000d781  call    _guard_dispatch_icall
0x18000d786  mov     [rbp+13F0h+var_1450], rax
0x18000d78a  jmp     short loc_18000D790
0x18000d78c  mov     [rbp+13F0h+var_1450], r13
0x18000d790  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d797  test    rax, rax
0x18000d79a  jz      short loc_18000D7A6
0x18000d79c  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d7a1  call    _guard_dispatch_icall
0x18000d7a6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d7ad  test    rax, rax
0x18000d7b0  jz      short loc_18000D7C6
0x18000d7b2  mov     r8d, 400h
0x18000d7b8  lea     rdx, [rbp+13F0h+var_1430]
0x18000d7bc  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d7c1  call    _guard_dispatch_icall
0x18000d7c6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d7cd  test    rax, rax
0x18000d7d0  jz      short loc_18000D7DC
0x18000d7d2  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d7d7  call    _guard_dispatch_icall
0x18000d7dc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d7e3  test    rax, rax
0x18000d7e6  jz      short loc_18000D7FE
0x18000d7e8  test    dil, dil
0x18000d7eb  jnz     short loc_18000D7FE
0x18000d7ed  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000d7f2  jnz     short loc_18000D7FE
0x18000d7f4  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d7f9  call    _guard_dispatch_icall
0x18000d7fe  cmp     [rsp+14F0h+var_14C8], r13d
0x18000d803  jl      short loc_18000D80B
0x18000d805  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d80b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000d812  jnz     short loc_18000D83C
0x18000d814  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d81b  test    rax, rax
0x18000d81e  jz      short loc_18000D82A
0x18000d820  call    _guard_dispatch_icall
0x18000d825  movzx   ecx, al
0x18000d828  jmp     short loc_18000D838
0x18000d82a  call    cs:__imp_IsDebuggerPresent
0x18000d830  mov     ecx, r13d
0x18000d833  test    eax, eax
0x18000d835  setnz   cl
0x18000d838  test    ecx, ecx
0x18000d83a  jz      short loc_18000D845
0x18000d83c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000d841  mov     bl, 1
0x18000d843  jz      short loc_18000D848
0x18000d845  mov     bl, r13b
0x18000d848  test    dil, dil
0x18000d84b  jnz     short loc_18000D877
0x18000d84d  test    bl, bl
0x18000d84f  jnz     short loc_18000D877
0x18000d851  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d858  test    rax, rax
0x18000d85b  jz      short loc_18000D8D4
0x18000d85d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000d864  jnz     short loc_18000D8D4
0x18000d866  xor     r8d, r8d
0x18000d869  xor     edx, edx
0x18000d86b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d870  call    _guard_dispatch_icall
0x18000d875  jmp     short loc_18000D8D4
0x18000d877  mov     esi, 800h
0x18000d87c  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d883  test    rax, rax
0x18000d886  jz      short loc_18000D8A5
0x18000d888  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000d88f  jnz     short loc_18000D8A5
0x18000d891  mov     r8d, esi
0x18000d894  lea     rdx, [rbp+13F0h+OutputString]
0x18000d89b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d8a0  call    _guard_dispatch_icall
0x18000d8a5  cmp     [rbp+13F0h+OutputString], r13w
0x18000d8ad  jnz     short loc_18000D8C3
0x18000d8af  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000d8b4  mov     rdx, rsi; wchar_t *
0x18000d8b7  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000d8be  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000d8c3  test    bl, bl
0x18000d8c5  jz      short loc_18000D8D4
0x18000d8c7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000d8ce  call    cs:__imp_OutputDebugStringW
0x18000d8d4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000d8d9  jnz     short loc_18000D8E4
0x18000d8db  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000d8e2  jz      short loc_18000D8F6
0x18000d8e4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d8eb  test    rax, rax
0x18000d8ee  jz      short loc_18000D8F6
0x18000d8f0  call    _guard_dispatch_icall
0x18000d8f5  nop
0x18000d8f6  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000d8fb  jz      short loc_18000D908
0x18000d8fd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d902  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d908  test    dil, dil
0x18000d90b  jz      short loc_18000D925
0x18000d90d  lea     rdx, [rbp+13F0h+OutputString]
0x18000d914  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d919  mov     rax, cs:g_pfnThrowPlatformException
0x18000d920  call    _guard_dispatch_icall
0x18000d925  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d92a  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000d92f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d934  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
