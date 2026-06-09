# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000a6c8`
- end: `0x18000a996`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a99c`

## callees

- `0x180001e74`
- `0x1800022e0`
- `0x180002fc8`
- `0x18000358c`
- `0x1800037f0`
- `0x18000a6c8`
- `0x180015990`
- `0x180015a00`
- `0x180015a80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a789`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a886`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a886`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a92a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a92a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(v21, OutputString, 2048, v18);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v21, v18);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v21, 0, 0, v18);
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
0x18000a6c8  mov     [rsp-8+arg_18], rbx
0x18000a6cd  push    rbp
0x18000a6ce  push    rsi
0x18000a6cf  push    rdi
0x18000a6d0  push    r12
0x18000a6d2  push    r13
0x18000a6d4  push    r14
0x18000a6d6  push    r15
0x18000a6d8  lea     rbp, [rsp-13C0h]
0x18000a6e0  mov     eax, 14C0h
0x18000a6e5  call    _alloca_probe
0x18000a6ea  sub     rsp, rax
0x18000a6ed  mov     r14, r8
0x18000a6f0  mov     esi, edx
0x18000a6f2  mov     rbx, rcx
0x18000a6f5  mov     r15, [rbp+13F0h+arg_28]
0x18000a6fc  xor     r13d, r13d
0x18000a6ff  cmp     cs:g_pfnThrowPlatformException, r13
0x18000a706  setnz   dil
0x18000a70a  xor     edx, edx; Val
0x18000a70c  mov     r8d, 98h; Size
0x18000a712  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000a717  call    memset
0x18000a71c  nop
0x18000a71d  mov     [rbp+13F0h+OutputString], r13w
0x18000a725  mov     [rbp+13F0h+var_1430], r13b
0x18000a729  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000a730  mov     ecx, [rdx]; this
0x18000a732  mov     [rsp+14F0h+var_14C8], ecx
0x18000a736  mov     eax, [rdx+4]
0x18000a739  mov     [rsp+14F0h+var_14C4], eax
0x18000a73d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a742  mov     r12d, eax
0x18000a745  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000a74a  mov     ecx, r13d
0x18000a74d  lea     eax, [r13+8]
0x18000a751  cmp     dword ptr [rdx+8], 1
0x18000a755  cmovz   ecx, eax
0x18000a758  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000a75c  lea     ecx, [rax-7]
0x18000a75f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a767  inc     ecx
0x18000a769  mov     [rsp+14F0h+var_14C0], ecx
0x18000a76d  mov     rcx, [rbp+13F0h+arg_38]
0x18000a774  test    rcx, rcx
0x18000a777  jz      short loc_18000A784
0x18000a779  cmp     [rcx], r13w
0x18000a77d  mov     [rsp+14F0h+var_14B8], rcx
0x18000a782  jnz     short loc_18000A789
0x18000a784  mov     [rsp+14F0h+var_14B8], r13
0x18000a789  call    cs:__imp_GetCurrentThreadId
0x18000a78f  mov     [rsp+14F0h+var_14B0], eax
0x18000a793  mov     [rsp+14F0h+var_1498], r14
0x18000a798  mov     [rsp+14F0h+var_1490], esi
0x18000a79c  mov     [rsp+14F0h+var_148C], r12d
0x18000a7a1  mov     [rsp+14F0h+var_14A8], r13
0x18000a7a6  mov     [rsp+14F0h+var_14A0], r13
0x18000a7ab  mov     [rbp+13F0h+var_1448], r15
0x18000a7af  mov     [rbp+13F0h+var_1440], rbx
0x18000a7b3  mov     [rsp+14F0h+var_1488], r13
0x18000a7b8  xorps   xmm0, xmm0
0x18000a7bb  xor     eax, eax
0x18000a7bd  movups  [rbp+13F0h+var_1468], xmm0
0x18000a7c1  mov     [rbp+13F0h+var_1458], rax
0x18000a7c5  xorps   xmm1, xmm1
0x18000a7c8  movups  [rsp+14F0h+var_1480], xmm1
0x18000a7cd  mov     [rbp+13F0h+var_1470], rax
0x18000a7d1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a7d8  test    rax, rax
0x18000a7db  jz      short loc_18000A7E8
0x18000a7dd  call    _guard_dispatch_icall
0x18000a7e2  mov     [rbp+13F0h+var_1450], rax
0x18000a7e6  jmp     short loc_18000A7EC
0x18000a7e8  mov     [rbp+13F0h+var_1450], r13
0x18000a7ec  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a7f3  test    rax, rax
0x18000a7f6  jz      short loc_18000A802
0x18000a7f8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a7fd  call    _guard_dispatch_icall
0x18000a802  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a809  test    rax, rax
0x18000a80c  jz      short loc_18000A822
0x18000a80e  mov     r8d, 400h
0x18000a814  lea     rdx, [rbp+13F0h+var_1430]
0x18000a818  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a81d  call    _guard_dispatch_icall
0x18000a822  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a829  test    rax, rax
0x18000a82c  jz      short loc_18000A838
0x18000a82e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a833  call    _guard_dispatch_icall
0x18000a838  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a83f  test    rax, rax
0x18000a842  jz      short loc_18000A85A
0x18000a844  test    dil, dil
0x18000a847  jnz     short loc_18000A85A
0x18000a849  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a84e  jnz     short loc_18000A85A
0x18000a850  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a855  call    _guard_dispatch_icall
0x18000a85a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000a85f  jl      short loc_18000A867
0x18000a861  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a867  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000a86e  jnz     short loc_18000A898
0x18000a870  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a877  test    rax, rax
0x18000a87a  jz      short loc_18000A886
0x18000a87c  call    _guard_dispatch_icall
0x18000a881  movzx   ecx, al
0x18000a884  jmp     short loc_18000A894
0x18000a886  call    cs:__imp_IsDebuggerPresent
0x18000a88c  mov     ecx, r13d
0x18000a88f  test    eax, eax
0x18000a891  setnz   cl
0x18000a894  test    ecx, ecx
0x18000a896  jz      short loc_18000A8A1
0x18000a898  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a89d  mov     bl, 1
0x18000a89f  jz      short loc_18000A8A4
0x18000a8a1  mov     bl, r13b
0x18000a8a4  test    dil, dil
0x18000a8a7  jnz     short loc_18000A8D3
0x18000a8a9  test    bl, bl
0x18000a8ab  jnz     short loc_18000A8D3
0x18000a8ad  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a8b4  test    rax, rax
0x18000a8b7  jz      short loc_18000A930
0x18000a8b9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a8c0  jnz     short loc_18000A930
0x18000a8c2  xor     r8d, r8d
0x18000a8c5  xor     edx, edx
0x18000a8c7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a8cc  call    _guard_dispatch_icall
0x18000a8d1  jmp     short loc_18000A930
0x18000a8d3  mov     esi, 800h
0x18000a8d8  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a8df  test    rax, rax
0x18000a8e2  jz      short loc_18000A901
0x18000a8e4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a8eb  jnz     short loc_18000A901
0x18000a8ed  mov     r8d, esi
0x18000a8f0  lea     rdx, [rbp+13F0h+OutputString]
0x18000a8f7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a8fc  call    _guard_dispatch_icall
0x18000a901  cmp     [rbp+13F0h+OutputString], r13w
0x18000a909  jnz     short loc_18000A91F
0x18000a90b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000a910  mov     rdx, rsi; wchar_t *
0x18000a913  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000a91a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000a91f  test    bl, bl
0x18000a921  jz      short loc_18000A930
0x18000a923  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000a92a  call    cs:__imp_OutputDebugStringW
0x18000a930  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000a935  jnz     short loc_18000A940
0x18000a937  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000a93e  jz      short loc_18000A952
0x18000a940  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a947  test    rax, rax
0x18000a94a  jz      short loc_18000A952
0x18000a94c  call    _guard_dispatch_icall
0x18000a951  nop
0x18000a952  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000a957  jz      short loc_18000A964
0x18000a959  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a95e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000a964  test    dil, dil
0x18000a967  jz      short loc_18000A981
0x18000a969  lea     rdx, [rbp+13F0h+OutputString]
0x18000a970  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a975  mov     rax, cs:g_pfnThrowPlatformException
0x18000a97c  call    _guard_dispatch_icall
0x18000a981  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a986  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000a98b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a990  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
