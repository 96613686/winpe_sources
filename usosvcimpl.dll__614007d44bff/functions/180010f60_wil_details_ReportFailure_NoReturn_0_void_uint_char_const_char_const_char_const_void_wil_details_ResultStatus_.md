# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180010f60`
- end: `0x18001122e`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180011234`

## callees

- `0x180007888`
- `0x180007cf4`
- `0x1800089d8`
- `0x180008c90`
- `0x180008ef0`
- `0x180010f60`
- `0x1800e45c0`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011021`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011021`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800111c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800111c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001111e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001111e`

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
0x180010f60  mov     [rsp-8+arg_18], rbx
0x180010f65  push    rbp
0x180010f66  push    rsi
0x180010f67  push    rdi
0x180010f68  push    r12
0x180010f6a  push    r13
0x180010f6c  push    r14
0x180010f6e  push    r15
0x180010f70  lea     rbp, [rsp-13C0h]
0x180010f78  mov     eax, 14C0h
0x180010f7d  call    _alloca_probe
0x180010f82  sub     rsp, rax
0x180010f85  mov     r14, r8
0x180010f88  mov     esi, edx
0x180010f8a  mov     rbx, rcx
0x180010f8d  mov     r15, [rbp+13F0h+arg_28]
0x180010f94  xor     r13d, r13d
0x180010f97  cmp     cs:g_pfnThrowPlatformException, r13
0x180010f9e  setnz   dil
0x180010fa2  xor     edx, edx; Val
0x180010fa4  mov     r8d, 98h; Size
0x180010faa  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180010faf  call    memset
0x180010fb4  nop
0x180010fb5  mov     [rbp+13F0h+OutputString], r13w
0x180010fbd  mov     [rbp+13F0h+var_1430], r13b
0x180010fc1  mov     rdx, [rbp+13F0h+arg_30]; int
0x180010fc8  mov     ecx, [rdx]; this
0x180010fca  mov     [rsp+14F0h+var_14C8], ecx
0x180010fce  mov     eax, [rdx+4]
0x180010fd1  mov     [rsp+14F0h+var_14C4], eax
0x180010fd5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180010fda  mov     r12d, eax
0x180010fdd  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180010fe2  mov     ecx, r13d
0x180010fe5  lea     eax, [r13+8]
0x180010fe9  cmp     dword ptr [rdx+8], 1
0x180010fed  cmovz   ecx, eax
0x180010ff0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180010ff4  lea     ecx, [rax-7]
0x180010ff7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010fff  inc     ecx
0x180011001  mov     [rsp+14F0h+var_14C0], ecx
0x180011005  mov     rcx, [rbp+13F0h+arg_38]
0x18001100c  test    rcx, rcx
0x18001100f  jz      short loc_18001101C
0x180011011  cmp     [rcx], r13w
0x180011015  mov     [rsp+14F0h+var_14B8], rcx
0x18001101a  jnz     short loc_180011021
0x18001101c  mov     [rsp+14F0h+var_14B8], r13
0x180011021  call    cs:__imp_GetCurrentThreadId
0x180011027  mov     [rsp+14F0h+var_14B0], eax
0x18001102b  mov     [rsp+14F0h+var_1498], r14
0x180011030  mov     [rsp+14F0h+var_1490], esi
0x180011034  mov     [rsp+14F0h+var_148C], r12d
0x180011039  mov     [rsp+14F0h+var_14A8], r13
0x18001103e  mov     [rsp+14F0h+var_14A0], r13
0x180011043  mov     [rbp+13F0h+var_1448], r15
0x180011047  mov     [rbp+13F0h+var_1440], rbx
0x18001104b  mov     [rsp+14F0h+var_1488], r13
0x180011050  xorps   xmm0, xmm0
0x180011053  xor     eax, eax
0x180011055  movups  [rbp+13F0h+var_1468], xmm0
0x180011059  mov     [rbp+13F0h+var_1458], rax
0x18001105d  xorps   xmm1, xmm1
0x180011060  movups  [rsp+14F0h+var_1480], xmm1
0x180011065  mov     [rbp+13F0h+var_1470], rax
0x180011069  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011070  test    rax, rax
0x180011073  jz      short loc_180011080
0x180011075  call    _guard_dispatch_icall
0x18001107a  mov     [rbp+13F0h+var_1450], rax
0x18001107e  jmp     short loc_180011084
0x180011080  mov     [rbp+13F0h+var_1450], r13
0x180011084  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001108b  test    rax, rax
0x18001108e  jz      short loc_18001109A
0x180011090  lea     rcx, [rsp+14F0h+var_14D0]
0x180011095  call    _guard_dispatch_icall
0x18001109a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800110a1  test    rax, rax
0x1800110a4  jz      short loc_1800110BA
0x1800110a6  mov     r8d, 400h
0x1800110ac  lea     rdx, [rbp+13F0h+var_1430]
0x1800110b0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800110b5  call    _guard_dispatch_icall
0x1800110ba  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800110c1  test    rax, rax
0x1800110c4  jz      short loc_1800110D0
0x1800110c6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800110cb  call    _guard_dispatch_icall
0x1800110d0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800110d7  test    rax, rax
0x1800110da  jz      short loc_1800110F2
0x1800110dc  test    dil, dil
0x1800110df  jnz     short loc_1800110F2
0x1800110e1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800110e6  jnz     short loc_1800110F2
0x1800110e8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800110ed  call    _guard_dispatch_icall
0x1800110f2  cmp     [rsp+14F0h+var_14C8], r13d
0x1800110f7  jl      short loc_1800110FF
0x1800110f9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800110ff  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180011106  jnz     short loc_180011130
0x180011108  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001110f  test    rax, rax
0x180011112  jz      short loc_18001111E
0x180011114  call    _guard_dispatch_icall
0x180011119  movzx   ecx, al
0x18001111c  jmp     short loc_18001112C
0x18001111e  call    cs:__imp_IsDebuggerPresent
0x180011124  mov     ecx, r13d
0x180011127  test    eax, eax
0x180011129  setnz   cl
0x18001112c  test    ecx, ecx
0x18001112e  jz      short loc_180011139
0x180011130  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180011135  mov     bl, 1
0x180011137  jz      short loc_18001113C
0x180011139  mov     bl, r13b
0x18001113c  test    dil, dil
0x18001113f  jnz     short loc_18001116B
0x180011141  test    bl, bl
0x180011143  jnz     short loc_18001116B
0x180011145  mov     rax, cs:g_pfnResultLoggingCallback
0x18001114c  test    rax, rax
0x18001114f  jz      short loc_1800111C8
0x180011151  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180011158  jnz     short loc_1800111C8
0x18001115a  xor     r8d, r8d
0x18001115d  xor     edx, edx
0x18001115f  lea     rcx, [rsp+14F0h+var_14D0]
0x180011164  call    _guard_dispatch_icall
0x180011169  jmp     short loc_1800111C8
0x18001116b  mov     esi, 800h
0x180011170  mov     rax, cs:g_pfnResultLoggingCallback
0x180011177  test    rax, rax
0x18001117a  jz      short loc_180011199
0x18001117c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180011183  jnz     short loc_180011199
0x180011185  mov     r8d, esi
0x180011188  lea     rdx, [rbp+13F0h+OutputString]
0x18001118f  lea     rcx, [rsp+14F0h+var_14D0]
0x180011194  call    _guard_dispatch_icall
0x180011199  cmp     [rbp+13F0h+OutputString], r13w
0x1800111a1  jnz     short loc_1800111B7
0x1800111a3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800111a8  mov     rdx, rsi; wchar_t *
0x1800111ab  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800111b2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800111b7  test    bl, bl
0x1800111b9  jz      short loc_1800111C8
0x1800111bb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800111c2  call    cs:__imp_OutputDebugStringW
0x1800111c8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800111cd  jnz     short loc_1800111D8
0x1800111cf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800111d6  jz      short loc_1800111EA
0x1800111d8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800111df  test    rax, rax
0x1800111e2  jz      short loc_1800111EA
0x1800111e4  call    _guard_dispatch_icall
0x1800111e9  nop
0x1800111ea  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800111ef  jz      short loc_1800111FC
0x1800111f1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800111f6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800111fc  test    dil, dil
0x1800111ff  jz      short loc_180011219
0x180011201  lea     rdx, [rbp+13F0h+OutputString]
0x180011208  lea     rcx, [rsp+14F0h+var_14D0]
0x18001120d  mov     rax, cs:g_pfnThrowPlatformException
0x180011214  call    _guard_dispatch_icall
0x180011219  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001121e  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180011223  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180011228  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
