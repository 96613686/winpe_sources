# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180009ec4`
- end: `0x18000a146`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a14c`

## callees

- `0x18000897c`
- `0x1800097a0`
- `0x1800098dc`
- `0x180009ec4`
- `0x18000a184`
- `0x180096100`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a113`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a113`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a081`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a081`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009f7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009f7d`

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
0x180009ec4  mov     [rsp-8+arg_18], rbx
0x180009ec9  push    rbp
0x180009eca  push    rsi
0x180009ecb  push    rdi
0x180009ecc  push    r12
0x180009ece  push    r13
0x180009ed0  push    r14
0x180009ed2  push    r15
0x180009ed4  lea     rbp, [rsp-13C0h]
0x180009edc  mov     eax, 14C0h
0x180009ee1  call    _alloca_probe
0x180009ee6  sub     rsp, rax
0x180009ee9  mov     r14, r8
0x180009eec  mov     esi, edx
0x180009eee  mov     rdi, rcx
0x180009ef1  mov     r15, [rbp+13F0h+arg_28]
0x180009ef8  xor     edx, edx; Val
0x180009efa  mov     r8d, 98h; Size
0x180009f00  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009f05  call    memset
0x180009f0a  nop
0x180009f0b  xor     r13d, r13d
0x180009f0e  mov     [rbp+13F0h+OutputString], r13w
0x180009f16  mov     [rbp+13F0h+var_1430], r13b
0x180009f1a  mov     rbx, [rbp+13F0h+arg_30]
0x180009f21  mov     ecx, [rbx]; this
0x180009f23  mov     [rsp+14F0h+var_14C8], ecx
0x180009f27  mov     eax, [rbx+4]
0x180009f2a  mov     [rsp+14F0h+var_14C4], eax
0x180009f2e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009f33  mov     r12d, eax
0x180009f36  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180009f3e  mov     ecx, r13d
0x180009f41  lea     eax, [r13+8]
0x180009f45  cmp     dword ptr [rbx+8], 1
0x180009f49  cmovz   ecx, eax
0x180009f4c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009f50  lea     ecx, [rax-7]
0x180009f53  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009f5b  inc     ecx
0x180009f5d  mov     [rsp+14F0h+var_14C0], ecx
0x180009f61  mov     rcx, [rbp+13F0h+arg_38]
0x180009f68  test    rcx, rcx
0x180009f6b  jz      short loc_180009F78
0x180009f6d  cmp     [rcx], r13w
0x180009f71  mov     [rsp+14F0h+var_14B8], rcx
0x180009f76  jnz     short loc_180009F7D
0x180009f78  mov     [rsp+14F0h+var_14B8], r13
0x180009f7d  call    cs:__imp_GetCurrentThreadId
0x180009f83  mov     [rsp+14F0h+var_14B0], eax
0x180009f87  mov     [rsp+14F0h+var_1498], r14
0x180009f8c  mov     [rsp+14F0h+var_1490], esi
0x180009f90  mov     [rsp+14F0h+var_148C], r12d
0x180009f95  mov     [rsp+14F0h+var_14A8], r13
0x180009f9a  mov     [rsp+14F0h+var_14A0], r13
0x180009f9f  mov     [rbp+13F0h+var_1448], r15
0x180009fa3  mov     [rbp+13F0h+var_1440], rdi
0x180009fa7  mov     [rsp+14F0h+var_1488], r13
0x180009fac  xorps   xmm0, xmm0
0x180009faf  xor     eax, eax
0x180009fb1  movups  [rbp+13F0h+var_1468], xmm0
0x180009fb5  mov     [rbp+13F0h+var_1458], rax
0x180009fb9  xorps   xmm1, xmm1
0x180009fbc  movups  [rsp+14F0h+var_1480], xmm1
0x180009fc1  mov     [rbp+13F0h+var_1470], rax
0x180009fc5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009fcc  test    rax, rax
0x180009fcf  jz      short loc_180009FDC
0x180009fd1  call    _guard_dispatch_icall
0x180009fd6  mov     [rbp+13F0h+var_1450], rax
0x180009fda  jmp     short loc_180009FE0
0x180009fdc  mov     [rbp+13F0h+var_1450], r13
0x180009fe0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009fe7  test    rax, rax
0x180009fea  jz      short loc_180009FF6
0x180009fec  lea     rcx, [rsp+14F0h+var_14D0]
0x180009ff1  call    _guard_dispatch_icall
0x180009ff6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009ffd  test    rax, rax
0x18000a000  jz      short loc_18000A016
0x18000a002  mov     r8d, 400h
0x18000a008  lea     rdx, [rbp+13F0h+var_1430]
0x18000a00c  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a011  call    _guard_dispatch_icall
0x18000a016  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a01d  test    rax, rax
0x18000a020  jz      short loc_18000A02C
0x18000a022  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a027  call    _guard_dispatch_icall
0x18000a02c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a033  test    rax, rax
0x18000a036  jz      short loc_18000A049
0x18000a038  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a03d  jnz     short loc_18000A049
0x18000a03f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a044  call    _guard_dispatch_icall
0x18000a049  cmp     [rsp+14F0h+var_14C8], r13d
0x18000a04e  jl      short loc_18000A062
0x18000a050  mov     ecx, 8000FFFFh; this
0x18000a055  mov     [rsp+14F0h+var_14C8], ecx
0x18000a059  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a05e  mov     [rsp+14F0h+var_14C4], eax
0x18000a062  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000a069  jnz     short loc_18000A093
0x18000a06b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a072  test    rax, rax
0x18000a075  jz      short loc_18000A081
0x18000a077  call    _guard_dispatch_icall
0x18000a07c  movzx   ecx, al
0x18000a07f  jmp     short loc_18000A08F
0x18000a081  call    cs:__imp_IsDebuggerPresent
0x18000a087  mov     ecx, r13d
0x18000a08a  test    eax, eax
0x18000a08c  setnz   cl
0x18000a08f  test    ecx, ecx
0x18000a091  jz      short loc_18000A09A
0x18000a093  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a098  jz      short loc_18000A0C0
0x18000a09a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a0a1  test    rax, rax
0x18000a0a4  jz      short loc_18000A119
0x18000a0a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a0ad  jnz     short loc_18000A119
0x18000a0af  xor     r8d, r8d
0x18000a0b2  xor     edx, edx
0x18000a0b4  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a0b9  call    _guard_dispatch_icall
0x18000a0be  jmp     short loc_18000A119
0x18000a0c0  mov     ebx, 800h
0x18000a0c5  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a0cc  test    rax, rax
0x18000a0cf  jz      short loc_18000A0EE
0x18000a0d1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a0d8  jnz     short loc_18000A0EE
0x18000a0da  mov     r8d, ebx
0x18000a0dd  lea     rdx, [rbp+13F0h+OutputString]
0x18000a0e4  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a0e9  call    _guard_dispatch_icall
0x18000a0ee  cmp     [rbp+13F0h+OutputString], r13w
0x18000a0f6  jnz     short loc_18000A10C
0x18000a0f8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000a0fd  mov     rdx, rbx; wchar_t *
0x18000a100  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000a107  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000a10c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000a113  call    cs:__imp_OutputDebugStringW
0x18000a119  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000a11e  jnz     short loc_18000A129
0x18000a120  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000a127  jz      short loc_18000A13B
0x18000a129  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a130  test    rax, rax
0x18000a133  jz      short loc_18000A13B
0x18000a135  call    _guard_dispatch_icall
0x18000a13a  nop
0x18000a13b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a140  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
