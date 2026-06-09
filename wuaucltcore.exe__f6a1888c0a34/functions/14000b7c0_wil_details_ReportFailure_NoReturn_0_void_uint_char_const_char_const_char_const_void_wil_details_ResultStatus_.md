# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x14000b7c0`
- end: `0x14000ba8e`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000ba94`

## callees

- `0x140001b7c`
- `0x140001dc4`
- `0x140001efc`
- `0x1400024f0`
- `0x140003a98`
- `0x14000b7c0`
- `0x140020670`
- `0x1400206e0`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ba22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ba22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000b97e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000b97e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b881`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b881`

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
0x14000b7c0  mov     [rsp-8+arg_18], rbx
0x14000b7c5  push    rbp
0x14000b7c6  push    rsi
0x14000b7c7  push    rdi
0x14000b7c8  push    r12
0x14000b7ca  push    r13
0x14000b7cc  push    r14
0x14000b7ce  push    r15
0x14000b7d0  lea     rbp, [rsp-13C0h]
0x14000b7d8  mov     eax, 14C0h
0x14000b7dd  call    _alloca_probe
0x14000b7e2  sub     rsp, rax
0x14000b7e5  mov     r14, r8
0x14000b7e8  mov     esi, edx
0x14000b7ea  mov     rbx, rcx
0x14000b7ed  mov     r15, [rbp+13F0h+arg_28]
0x14000b7f4  xor     r13d, r13d
0x14000b7f7  cmp     cs:g_pfnThrowPlatformException, r13
0x14000b7fe  setnz   dil
0x14000b802  xor     edx, edx; Val
0x14000b804  mov     r8d, 98h; Size
0x14000b80a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000b80f  call    memset
0x14000b814  nop
0x14000b815  mov     [rbp+13F0h+OutputString], r13w
0x14000b81d  mov     [rbp+13F0h+var_1430], r13b
0x14000b821  mov     rdx, [rbp+13F0h+arg_30]; int
0x14000b828  mov     ecx, [rdx]; this
0x14000b82a  mov     [rsp+14F0h+var_14C8], ecx
0x14000b82e  mov     eax, [rdx+4]
0x14000b831  mov     [rsp+14F0h+var_14C4], eax
0x14000b835  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000b83a  mov     r12d, eax
0x14000b83d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x14000b842  mov     ecx, r13d
0x14000b845  lea     eax, [r13+8]
0x14000b849  cmp     dword ptr [rdx+8], 1
0x14000b84d  cmovz   ecx, eax
0x14000b850  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000b854  lea     ecx, [rax-7]
0x14000b857  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000b85f  inc     ecx
0x14000b861  mov     [rsp+14F0h+var_14C0], ecx
0x14000b865  mov     rcx, [rbp+13F0h+arg_38]
0x14000b86c  test    rcx, rcx
0x14000b86f  jz      short loc_14000B87C
0x14000b871  cmp     [rcx], r13w
0x14000b875  mov     [rsp+14F0h+var_14B8], rcx
0x14000b87a  jnz     short loc_14000B881
0x14000b87c  mov     [rsp+14F0h+var_14B8], r13
0x14000b881  call    cs:__imp_GetCurrentThreadId
0x14000b887  mov     [rsp+14F0h+var_14B0], eax
0x14000b88b  mov     [rsp+14F0h+var_1498], r14
0x14000b890  mov     [rsp+14F0h+var_1490], esi
0x14000b894  mov     [rsp+14F0h+var_148C], r12d
0x14000b899  mov     [rsp+14F0h+var_14A8], r13
0x14000b89e  mov     [rsp+14F0h+var_14A0], r13
0x14000b8a3  mov     [rbp+13F0h+var_1448], r15
0x14000b8a7  mov     [rbp+13F0h+var_1440], rbx
0x14000b8ab  mov     [rsp+14F0h+var_1488], r13
0x14000b8b0  xorps   xmm0, xmm0
0x14000b8b3  xor     eax, eax
0x14000b8b5  movups  [rbp+13F0h+var_1468], xmm0
0x14000b8b9  mov     [rbp+13F0h+var_1458], rax
0x14000b8bd  xorps   xmm1, xmm1
0x14000b8c0  movups  [rsp+14F0h+var_1480], xmm1
0x14000b8c5  mov     [rbp+13F0h+var_1470], rax
0x14000b8c9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000b8d0  test    rax, rax
0x14000b8d3  jz      short loc_14000B8E0
0x14000b8d5  call    _guard_dispatch_icall
0x14000b8da  mov     [rbp+13F0h+var_1450], rax
0x14000b8de  jmp     short loc_14000B8E4
0x14000b8e0  mov     [rbp+13F0h+var_1450], r13
0x14000b8e4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000b8eb  test    rax, rax
0x14000b8ee  jz      short loc_14000B8FA
0x14000b8f0  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b8f5  call    _guard_dispatch_icall
0x14000b8fa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000b901  test    rax, rax
0x14000b904  jz      short loc_14000B91A
0x14000b906  mov     r8d, 400h
0x14000b90c  lea     rdx, [rbp+13F0h+var_1430]
0x14000b910  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b915  call    _guard_dispatch_icall
0x14000b91a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000b921  test    rax, rax
0x14000b924  jz      short loc_14000B930
0x14000b926  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b92b  call    _guard_dispatch_icall
0x14000b930  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000b937  test    rax, rax
0x14000b93a  jz      short loc_14000B952
0x14000b93c  test    dil, dil
0x14000b93f  jnz     short loc_14000B952
0x14000b941  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000b946  jnz     short loc_14000B952
0x14000b948  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b94d  call    _guard_dispatch_icall
0x14000b952  cmp     [rsp+14F0h+var_14C8], r13d
0x14000b957  jl      short loc_14000B95F
0x14000b959  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000b95f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000b966  jnz     short loc_14000B990
0x14000b968  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000b96f  test    rax, rax
0x14000b972  jz      short loc_14000B97E
0x14000b974  call    _guard_dispatch_icall
0x14000b979  movzx   ecx, al
0x14000b97c  jmp     short loc_14000B98C
0x14000b97e  call    cs:__imp_IsDebuggerPresent
0x14000b984  mov     ecx, r13d
0x14000b987  test    eax, eax
0x14000b989  setnz   cl
0x14000b98c  test    ecx, ecx
0x14000b98e  jz      short loc_14000B999
0x14000b990  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000b995  mov     bl, 1
0x14000b997  jz      short loc_14000B99C
0x14000b999  mov     bl, r13b
0x14000b99c  test    dil, dil
0x14000b99f  jnz     short loc_14000B9CB
0x14000b9a1  test    bl, bl
0x14000b9a3  jnz     short loc_14000B9CB
0x14000b9a5  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b9ac  test    rax, rax
0x14000b9af  jz      short loc_14000BA28
0x14000b9b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000b9b8  jnz     short loc_14000BA28
0x14000b9ba  xor     r8d, r8d
0x14000b9bd  xor     edx, edx
0x14000b9bf  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b9c4  call    _guard_dispatch_icall
0x14000b9c9  jmp     short loc_14000BA28
0x14000b9cb  mov     esi, 800h
0x14000b9d0  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b9d7  test    rax, rax
0x14000b9da  jz      short loc_14000B9F9
0x14000b9dc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000b9e3  jnz     short loc_14000B9F9
0x14000b9e5  mov     r8d, esi
0x14000b9e8  lea     rdx, [rbp+13F0h+OutputString]
0x14000b9ef  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b9f4  call    _guard_dispatch_icall
0x14000b9f9  cmp     [rbp+13F0h+OutputString], r13w
0x14000ba01  jnz     short loc_14000BA17
0x14000ba03  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000ba08  mov     rdx, rsi; wchar_t *
0x14000ba0b  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000ba12  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000ba17  test    bl, bl
0x14000ba19  jz      short loc_14000BA28
0x14000ba1b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000ba22  call    cs:__imp_OutputDebugStringW
0x14000ba28  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000ba2d  jnz     short loc_14000BA38
0x14000ba2f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000ba36  jz      short loc_14000BA4A
0x14000ba38  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000ba3f  test    rax, rax
0x14000ba42  jz      short loc_14000BA4A
0x14000ba44  call    _guard_dispatch_icall
0x14000ba49  nop
0x14000ba4a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000ba4f  jz      short loc_14000BA5C
0x14000ba51  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000ba56  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000ba5c  test    dil, dil
0x14000ba5f  jz      short loc_14000BA79
0x14000ba61  lea     rdx, [rbp+13F0h+OutputString]
0x14000ba68  lea     rcx, [rsp+14F0h+var_14D0]
0x14000ba6d  mov     rax, cs:g_pfnThrowPlatformException
0x14000ba74  call    _guard_dispatch_icall
0x14000ba79  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000ba7e  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x14000ba83  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000ba88  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
