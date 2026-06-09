# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180009d14`
- end: `0x180009f96`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008d40`

## callees

- `0x180007888`
- `0x180007d50`
- `0x180007f90`
- `0x180008c90`
- `0x180009d14`
- `0x1800e45c0`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009dcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009dcd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009f63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009f63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009ed1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009ed1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        __int64 a7,
        _WORD *a8)
{
  int v11; // edx
  unsigned int v12; // r12d
  int v13; // ecx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
  unsigned __int64 v18[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *(_QWORD *)a7;
  v12 = wil::details::RecordFailFast((wil::details *)LODWORD(v18[1]), v11);
  LODWORD(v18[0]) = 3;
  v13 = 0;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v13 = 8;
  HIDWORD(v18[0]) = v13;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v18[3] = (unsigned __int64)a8, v14) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v12, a2);
  v18[5] = 0;
  v18[6] = 0;
  v18[17] = a6;
  v18[18] = a1;
  memset(&v18[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v18[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v18[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v18, v19, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v18);
  if ( wil::details::g_pfnOriginateCallback && (v18[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v18);
  if ( SLODWORD(v18[1]) >= 0 )
  {
    LODWORD(v18[1]) = -2147418113;
    HIDWORD(v18[1]) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v18[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0, v17);
  }
  if ( (v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
  wil::details::WilFailFast((wil::details *)v18, v15);
}

```

## disassembly

```asm
0x180009d14  mov     [rsp-8+arg_18], rbx
0x180009d19  push    rbp
0x180009d1a  push    rsi
0x180009d1b  push    rdi
0x180009d1c  push    r12
0x180009d1e  push    r13
0x180009d20  push    r14
0x180009d22  push    r15
0x180009d24  lea     rbp, [rsp-13C0h]
0x180009d2c  mov     eax, 14C0h
0x180009d31  call    _alloca_probe
0x180009d36  sub     rsp, rax
0x180009d39  mov     r14, r8
0x180009d3c  mov     esi, edx
0x180009d3e  mov     rdi, rcx
0x180009d41  mov     r15, [rbp+13F0h+arg_28]
0x180009d48  xor     edx, edx; Val
0x180009d4a  mov     r8d, 98h; Size
0x180009d50  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009d55  call    memset
0x180009d5a  nop
0x180009d5b  xor     r13d, r13d
0x180009d5e  mov     [rbp+13F0h+OutputString], r13w
0x180009d66  mov     [rbp+13F0h+var_1430], r13b
0x180009d6a  mov     rbx, [rbp+13F0h+arg_30]
0x180009d71  mov     ecx, [rbx]; this
0x180009d73  mov     [rsp+14F0h+var_14C8], ecx
0x180009d77  mov     eax, [rbx+4]
0x180009d7a  mov     [rsp+14F0h+var_14C4], eax
0x180009d7e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009d83  mov     r12d, eax
0x180009d86  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180009d8e  mov     ecx, r13d
0x180009d91  lea     eax, [r13+8]
0x180009d95  cmp     dword ptr [rbx+8], 1
0x180009d99  cmovz   ecx, eax
0x180009d9c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009da0  lea     ecx, [rax-7]
0x180009da3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009dab  inc     ecx
0x180009dad  mov     [rsp+14F0h+var_14C0], ecx
0x180009db1  mov     rcx, [rbp+13F0h+arg_38]
0x180009db8  test    rcx, rcx
0x180009dbb  jz      short loc_180009DC8
0x180009dbd  cmp     [rcx], r13w
0x180009dc1  mov     [rsp+14F0h+var_14B8], rcx
0x180009dc6  jnz     short loc_180009DCD
0x180009dc8  mov     [rsp+14F0h+var_14B8], r13
0x180009dcd  call    cs:__imp_GetCurrentThreadId
0x180009dd3  mov     [rsp+14F0h+var_14B0], eax
0x180009dd7  mov     [rsp+14F0h+var_1498], r14
0x180009ddc  mov     [rsp+14F0h+var_1490], esi
0x180009de0  mov     [rsp+14F0h+var_148C], r12d
0x180009de5  mov     [rsp+14F0h+var_14A8], r13
0x180009dea  mov     [rsp+14F0h+var_14A0], r13
0x180009def  mov     [rbp+13F0h+var_1448], r15
0x180009df3  mov     [rbp+13F0h+var_1440], rdi
0x180009df7  mov     [rsp+14F0h+var_1488], r13
0x180009dfc  xorps   xmm0, xmm0
0x180009dff  xor     eax, eax
0x180009e01  movups  [rbp+13F0h+var_1468], xmm0
0x180009e05  mov     [rbp+13F0h+var_1458], rax
0x180009e09  xorps   xmm1, xmm1
0x180009e0c  movups  [rsp+14F0h+var_1480], xmm1
0x180009e11  mov     [rbp+13F0h+var_1470], rax
0x180009e15  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009e1c  test    rax, rax
0x180009e1f  jz      short loc_180009E2C
0x180009e21  call    _guard_dispatch_icall
0x180009e26  mov     [rbp+13F0h+var_1450], rax
0x180009e2a  jmp     short loc_180009E30
0x180009e2c  mov     [rbp+13F0h+var_1450], r13
0x180009e30  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009e37  test    rax, rax
0x180009e3a  jz      short loc_180009E46
0x180009e3c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009e41  call    _guard_dispatch_icall
0x180009e46  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009e4d  test    rax, rax
0x180009e50  jz      short loc_180009E66
0x180009e52  mov     r8d, 400h
0x180009e58  lea     rdx, [rbp+13F0h+var_1430]
0x180009e5c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009e61  call    _guard_dispatch_icall
0x180009e66  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009e6d  test    rax, rax
0x180009e70  jz      short loc_180009E7C
0x180009e72  lea     rcx, [rsp+14F0h+var_14D0]
0x180009e77  call    _guard_dispatch_icall
0x180009e7c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009e83  test    rax, rax
0x180009e86  jz      short loc_180009E99
0x180009e88  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009e8d  jnz     short loc_180009E99
0x180009e8f  lea     rcx, [rsp+14F0h+var_14D0]
0x180009e94  call    _guard_dispatch_icall
0x180009e99  cmp     [rsp+14F0h+var_14C8], r13d
0x180009e9e  jl      short loc_180009EB2
0x180009ea0  mov     ecx, 8000FFFFh; this
0x180009ea5  mov     [rsp+14F0h+var_14C8], ecx
0x180009ea9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009eae  mov     [rsp+14F0h+var_14C4], eax
0x180009eb2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180009eb9  jnz     short loc_180009EE3
0x180009ebb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009ec2  test    rax, rax
0x180009ec5  jz      short loc_180009ED1
0x180009ec7  call    _guard_dispatch_icall
0x180009ecc  movzx   ecx, al
0x180009ecf  jmp     short loc_180009EDF
0x180009ed1  call    cs:__imp_IsDebuggerPresent
0x180009ed7  mov     ecx, r13d
0x180009eda  test    eax, eax
0x180009edc  setnz   cl
0x180009edf  test    ecx, ecx
0x180009ee1  jz      short loc_180009EEA
0x180009ee3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009ee8  jz      short loc_180009F10
0x180009eea  mov     rax, cs:g_pfnResultLoggingCallback
0x180009ef1  test    rax, rax
0x180009ef4  jz      short loc_180009F69
0x180009ef6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009efd  jnz     short loc_180009F69
0x180009eff  xor     r8d, r8d
0x180009f02  xor     edx, edx
0x180009f04  lea     rcx, [rsp+14F0h+var_14D0]
0x180009f09  call    _guard_dispatch_icall
0x180009f0e  jmp     short loc_180009F69
0x180009f10  mov     ebx, 800h
0x180009f15  mov     rax, cs:g_pfnResultLoggingCallback
0x180009f1c  test    rax, rax
0x180009f1f  jz      short loc_180009F3E
0x180009f21  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009f28  jnz     short loc_180009F3E
0x180009f2a  mov     r8d, ebx
0x180009f2d  lea     rdx, [rbp+13F0h+OutputString]
0x180009f34  lea     rcx, [rsp+14F0h+var_14D0]
0x180009f39  call    _guard_dispatch_icall
0x180009f3e  cmp     [rbp+13F0h+OutputString], r13w
0x180009f46  jnz     short loc_180009F5C
0x180009f48  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009f4d  mov     rdx, rbx; wchar_t *
0x180009f50  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009f57  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180009f5c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009f63  call    cs:__imp_OutputDebugStringW
0x180009f69  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180009f6e  jnz     short loc_180009F79
0x180009f70  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180009f77  jz      short loc_180009F8B
0x180009f79  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009f80  test    rax, rax
0x180009f83  jz      short loc_180009F8B
0x180009f85  call    _guard_dispatch_icall
0x180009f8a  nop
0x180009f8b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009f90  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
