# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1400052cc`
- end: `0x14000554e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140003d50`

## callees

- `0x140001db0`
- `0x140001efc`
- `0x1400024f0`
- `0x140002868`
- `0x1400052cc`
- `0x140020670`
- `0x1400206e0`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000551b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000551b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005489`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005489`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005385`

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
0x1400052cc  mov     [rsp-8+arg_18], rbx
0x1400052d1  push    rbp
0x1400052d2  push    rsi
0x1400052d3  push    rdi
0x1400052d4  push    r12
0x1400052d6  push    r13
0x1400052d8  push    r14
0x1400052da  push    r15
0x1400052dc  lea     rbp, [rsp-13C0h]
0x1400052e4  mov     eax, 14C0h
0x1400052e9  call    _alloca_probe
0x1400052ee  sub     rsp, rax
0x1400052f1  mov     r14, r8
0x1400052f4  mov     esi, edx
0x1400052f6  mov     rdi, rcx
0x1400052f9  mov     r15, [rbp+13F0h+arg_28]
0x140005300  xor     edx, edx; Val
0x140005302  mov     r8d, 98h; Size
0x140005308  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000530d  call    memset
0x140005312  nop
0x140005313  xor     r13d, r13d
0x140005316  mov     [rbp+13F0h+OutputString], r13w
0x14000531e  mov     [rbp+13F0h+var_1430], r13b
0x140005322  mov     rbx, [rbp+13F0h+arg_30]
0x140005329  mov     ecx, [rbx]; this
0x14000532b  mov     [rsp+14F0h+var_14C8], ecx
0x14000532f  mov     eax, [rbx+4]
0x140005332  mov     [rsp+14F0h+var_14C4], eax
0x140005336  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000533b  mov     r12d, eax
0x14000533e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140005346  mov     ecx, r13d
0x140005349  lea     eax, [r13+8]
0x14000534d  cmp     dword ptr [rbx+8], 1
0x140005351  cmovz   ecx, eax
0x140005354  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140005358  lea     ecx, [rax-7]
0x14000535b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005363  inc     ecx
0x140005365  mov     [rsp+14F0h+var_14C0], ecx
0x140005369  mov     rcx, [rbp+13F0h+arg_38]
0x140005370  test    rcx, rcx
0x140005373  jz      short loc_140005380
0x140005375  cmp     [rcx], r13w
0x140005379  mov     [rsp+14F0h+var_14B8], rcx
0x14000537e  jnz     short loc_140005385
0x140005380  mov     [rsp+14F0h+var_14B8], r13
0x140005385  call    cs:__imp_GetCurrentThreadId
0x14000538b  mov     [rsp+14F0h+var_14B0], eax
0x14000538f  mov     [rsp+14F0h+var_1498], r14
0x140005394  mov     [rsp+14F0h+var_1490], esi
0x140005398  mov     [rsp+14F0h+var_148C], r12d
0x14000539d  mov     [rsp+14F0h+var_14A8], r13
0x1400053a2  mov     [rsp+14F0h+var_14A0], r13
0x1400053a7  mov     [rbp+13F0h+var_1448], r15
0x1400053ab  mov     [rbp+13F0h+var_1440], rdi
0x1400053af  mov     [rsp+14F0h+var_1488], r13
0x1400053b4  xorps   xmm0, xmm0
0x1400053b7  xor     eax, eax
0x1400053b9  movups  [rbp+13F0h+var_1468], xmm0
0x1400053bd  mov     [rbp+13F0h+var_1458], rax
0x1400053c1  xorps   xmm1, xmm1
0x1400053c4  movups  [rsp+14F0h+var_1480], xmm1
0x1400053c9  mov     [rbp+13F0h+var_1470], rax
0x1400053cd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400053d4  test    rax, rax
0x1400053d7  jz      short loc_1400053E4
0x1400053d9  call    _guard_dispatch_icall
0x1400053de  mov     [rbp+13F0h+var_1450], rax
0x1400053e2  jmp     short loc_1400053E8
0x1400053e4  mov     [rbp+13F0h+var_1450], r13
0x1400053e8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400053ef  test    rax, rax
0x1400053f2  jz      short loc_1400053FE
0x1400053f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400053f9  call    _guard_dispatch_icall
0x1400053fe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005405  test    rax, rax
0x140005408  jz      short loc_14000541E
0x14000540a  mov     r8d, 400h
0x140005410  lea     rdx, [rbp+13F0h+var_1430]
0x140005414  lea     rcx, [rsp+14F0h+var_14D0]
0x140005419  call    _guard_dispatch_icall
0x14000541e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005425  test    rax, rax
0x140005428  jz      short loc_140005434
0x14000542a  lea     rcx, [rsp+14F0h+var_14D0]
0x14000542f  call    _guard_dispatch_icall
0x140005434  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000543b  test    rax, rax
0x14000543e  jz      short loc_140005451
0x140005440  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140005445  jnz     short loc_140005451
0x140005447  lea     rcx, [rsp+14F0h+var_14D0]
0x14000544c  call    _guard_dispatch_icall
0x140005451  cmp     [rsp+14F0h+var_14C8], r13d
0x140005456  jl      short loc_14000546A
0x140005458  mov     ecx, 8000FFFFh; this
0x14000545d  mov     [rsp+14F0h+var_14C8], ecx
0x140005461  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005466  mov     [rsp+14F0h+var_14C4], eax
0x14000546a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140005471  jnz     short loc_14000549B
0x140005473  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000547a  test    rax, rax
0x14000547d  jz      short loc_140005489
0x14000547f  call    _guard_dispatch_icall
0x140005484  movzx   ecx, al
0x140005487  jmp     short loc_140005497
0x140005489  call    cs:__imp_IsDebuggerPresent
0x14000548f  mov     ecx, r13d
0x140005492  test    eax, eax
0x140005494  setnz   cl
0x140005497  test    ecx, ecx
0x140005499  jz      short loc_1400054A2
0x14000549b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400054a0  jz      short loc_1400054C8
0x1400054a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400054a9  test    rax, rax
0x1400054ac  jz      short loc_140005521
0x1400054ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400054b5  jnz     short loc_140005521
0x1400054b7  xor     r8d, r8d
0x1400054ba  xor     edx, edx
0x1400054bc  lea     rcx, [rsp+14F0h+var_14D0]
0x1400054c1  call    _guard_dispatch_icall
0x1400054c6  jmp     short loc_140005521
0x1400054c8  mov     ebx, 800h
0x1400054cd  mov     rax, cs:g_pfnResultLoggingCallback
0x1400054d4  test    rax, rax
0x1400054d7  jz      short loc_1400054F6
0x1400054d9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400054e0  jnz     short loc_1400054F6
0x1400054e2  mov     r8d, ebx
0x1400054e5  lea     rdx, [rbp+13F0h+OutputString]
0x1400054ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1400054f1  call    _guard_dispatch_icall
0x1400054f6  cmp     [rbp+13F0h+OutputString], r13w
0x1400054fe  jnz     short loc_140005514
0x140005500  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140005505  mov     rdx, rbx; wchar_t *
0x140005508  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000550f  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140005514  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000551b  call    cs:__imp_OutputDebugStringW
0x140005521  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140005526  jnz     short loc_140005531
0x140005528  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000552f  jz      short loc_140005543
0x140005531  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005538  test    rax, rax
0x14000553b  jz      short loc_140005543
0x14000553d  call    _guard_dispatch_icall
0x140005542  nop
0x140005543  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140005548  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
