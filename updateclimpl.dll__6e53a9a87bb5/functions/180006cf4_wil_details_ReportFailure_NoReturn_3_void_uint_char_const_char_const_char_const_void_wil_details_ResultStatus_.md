# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180006cf4`
- end: `0x180006f76`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005d5c`

## callees

- `0x180004298`
- `0x180004724`
- `0x180004b40`
- `0x180004d50`
- `0x180006cf4`
- `0x180014870`
- `0x1800148e0`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006f43`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006f43`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006eb1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006eb1`

## pseudocode

```c
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
      g_pfnResultLoggingCallback(v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0);
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
0x180006cf4  mov     [rsp-8+arg_18], rbx
0x180006cf9  push    rbp
0x180006cfa  push    rsi
0x180006cfb  push    rdi
0x180006cfc  push    r12
0x180006cfe  push    r13
0x180006d00  push    r14
0x180006d02  push    r15
0x180006d04  lea     rbp, [rsp-13C0h]
0x180006d0c  mov     eax, 14C0h
0x180006d11  call    _alloca_probe
0x180006d16  sub     rsp, rax
0x180006d19  mov     r14, r8
0x180006d1c  mov     esi, edx
0x180006d1e  mov     rdi, rcx
0x180006d21  mov     r15, [rbp+13F0h+arg_28]
0x180006d28  xor     edx, edx; Val
0x180006d2a  mov     r8d, 98h; Size
0x180006d30  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006d35  call    memset
0x180006d3a  nop
0x180006d3b  xor     r13d, r13d
0x180006d3e  mov     [rbp+13F0h+OutputString], r13w
0x180006d46  mov     [rbp+13F0h+var_1430], r13b
0x180006d4a  mov     rbx, [rbp+13F0h+arg_30]
0x180006d51  mov     ecx, [rbx]; this
0x180006d53  mov     [rsp+14F0h+var_14C8], ecx
0x180006d57  mov     eax, [rbx+4]
0x180006d5a  mov     [rsp+14F0h+var_14C4], eax
0x180006d5e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006d63  mov     r12d, eax
0x180006d66  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180006d6e  mov     ecx, r13d
0x180006d71  lea     eax, [r13+8]
0x180006d75  cmp     dword ptr [rbx+8], 1
0x180006d79  cmovz   ecx, eax
0x180006d7c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006d80  lea     ecx, [rax-7]
0x180006d83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006d8b  inc     ecx
0x180006d8d  mov     [rsp+14F0h+var_14C0], ecx
0x180006d91  mov     rcx, [rbp+13F0h+arg_38]
0x180006d98  test    rcx, rcx
0x180006d9b  jz      short loc_180006DA8
0x180006d9d  cmp     [rcx], r13w
0x180006da1  mov     [rsp+14F0h+var_14B8], rcx
0x180006da6  jnz     short loc_180006DAD
0x180006da8  mov     [rsp+14F0h+var_14B8], r13
0x180006dad  call    cs:__imp_GetCurrentThreadId
0x180006db3  mov     [rsp+14F0h+var_14B0], eax
0x180006db7  mov     [rsp+14F0h+var_1498], r14
0x180006dbc  mov     [rsp+14F0h+var_1490], esi
0x180006dc0  mov     [rsp+14F0h+var_148C], r12d
0x180006dc5  mov     [rsp+14F0h+var_14A8], r13
0x180006dca  mov     [rsp+14F0h+var_14A0], r13
0x180006dcf  mov     [rbp+13F0h+var_1448], r15
0x180006dd3  mov     [rbp+13F0h+var_1440], rdi
0x180006dd7  mov     [rsp+14F0h+var_1488], r13
0x180006ddc  xorps   xmm0, xmm0
0x180006ddf  xor     eax, eax
0x180006de1  movups  [rbp+13F0h+var_1468], xmm0
0x180006de5  mov     [rbp+13F0h+var_1458], rax
0x180006de9  xorps   xmm1, xmm1
0x180006dec  movups  [rsp+14F0h+var_1480], xmm1
0x180006df1  mov     [rbp+13F0h+var_1470], rax
0x180006df5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006dfc  test    rax, rax
0x180006dff  jz      short loc_180006E0C
0x180006e01  call    _guard_dispatch_icall
0x180006e06  mov     [rbp+13F0h+var_1450], rax
0x180006e0a  jmp     short loc_180006E10
0x180006e0c  mov     [rbp+13F0h+var_1450], r13
0x180006e10  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006e17  test    rax, rax
0x180006e1a  jz      short loc_180006E26
0x180006e1c  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e21  call    _guard_dispatch_icall
0x180006e26  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006e2d  test    rax, rax
0x180006e30  jz      short loc_180006E46
0x180006e32  mov     r8d, 400h
0x180006e38  lea     rdx, [rbp+13F0h+var_1430]
0x180006e3c  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e41  call    _guard_dispatch_icall
0x180006e46  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006e4d  test    rax, rax
0x180006e50  jz      short loc_180006E5C
0x180006e52  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e57  call    _guard_dispatch_icall
0x180006e5c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006e63  test    rax, rax
0x180006e66  jz      short loc_180006E79
0x180006e68  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006e6d  jnz     short loc_180006E79
0x180006e6f  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e74  call    _guard_dispatch_icall
0x180006e79  cmp     [rsp+14F0h+var_14C8], r13d
0x180006e7e  jl      short loc_180006E92
0x180006e80  mov     ecx, 8000FFFFh; this
0x180006e85  mov     [rsp+14F0h+var_14C8], ecx
0x180006e89  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006e8e  mov     [rsp+14F0h+var_14C4], eax
0x180006e92  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006e99  jnz     short loc_180006EC3
0x180006e9b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006ea2  test    rax, rax
0x180006ea5  jz      short loc_180006EB1
0x180006ea7  call    _guard_dispatch_icall
0x180006eac  movzx   ecx, al
0x180006eaf  jmp     short loc_180006EBF
0x180006eb1  call    cs:__imp_IsDebuggerPresent
0x180006eb7  mov     ecx, r13d
0x180006eba  test    eax, eax
0x180006ebc  setnz   cl
0x180006ebf  test    ecx, ecx
0x180006ec1  jz      short loc_180006ECA
0x180006ec3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006ec8  jz      short loc_180006EF0
0x180006eca  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ed1  test    rax, rax
0x180006ed4  jz      short loc_180006F49
0x180006ed6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006edd  jnz     short loc_180006F49
0x180006edf  xor     r8d, r8d
0x180006ee2  xor     edx, edx
0x180006ee4  lea     rcx, [rsp+14F0h+var_14D0]
0x180006ee9  call    _guard_dispatch_icall
0x180006eee  jmp     short loc_180006F49
0x180006ef0  mov     ebx, 800h
0x180006ef5  mov     rax, cs:g_pfnResultLoggingCallback
0x180006efc  test    rax, rax
0x180006eff  jz      short loc_180006F1E
0x180006f01  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006f08  jnz     short loc_180006F1E
0x180006f0a  mov     r8d, ebx
0x180006f0d  lea     rdx, [rbp+13F0h+OutputString]
0x180006f14  lea     rcx, [rsp+14F0h+var_14D0]
0x180006f19  call    _guard_dispatch_icall
0x180006f1e  cmp     [rbp+13F0h+OutputString], r13w
0x180006f26  jnz     short loc_180006F3C
0x180006f28  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006f2d  mov     rdx, rbx; wchar_t *
0x180006f30  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006f37  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180006f3c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006f43  call    cs:__imp_OutputDebugStringW
0x180006f49  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006f4e  jnz     short loc_180006F59
0x180006f50  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006f57  jz      short loc_180006F6B
0x180006f59  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006f60  test    rax, rax
0x180006f63  jz      short loc_180006F6B
0x180006f65  call    _guard_dispatch_icall
0x180006f6a  nop
0x180006f6b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006f70  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
