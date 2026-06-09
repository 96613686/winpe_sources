# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180009af8`
- end: `0x180009dc6`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009dcc`

## callees

- `0x180001e74`
- `0x1800022e0`
- `0x180002fc8`
- `0x18000358c`
- `0x1800037f0`
- `0x180009af8`
- `0x180015940`
- `0x1800159b0`
- `0x180015a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009bb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009bb9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009cb6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009cb6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009d5a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009d5a`

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
0x180009af8  mov     [rsp-8+arg_18], rbx
0x180009afd  push    rbp
0x180009afe  push    rsi
0x180009aff  push    rdi
0x180009b00  push    r12
0x180009b02  push    r13
0x180009b04  push    r14
0x180009b06  push    r15
0x180009b08  lea     rbp, [rsp-13C0h]
0x180009b10  mov     eax, 14C0h
0x180009b15  call    _alloca_probe
0x180009b1a  sub     rsp, rax
0x180009b1d  mov     r14, r8
0x180009b20  mov     esi, edx
0x180009b22  mov     rbx, rcx
0x180009b25  mov     r15, [rbp+13F0h+arg_28]
0x180009b2c  xor     r13d, r13d
0x180009b2f  cmp     cs:g_pfnThrowPlatformException, r13
0x180009b36  setnz   dil
0x180009b3a  xor     edx, edx; Val
0x180009b3c  mov     r8d, 98h; Size
0x180009b42  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009b47  call    memset
0x180009b4c  nop
0x180009b4d  mov     [rbp+13F0h+OutputString], r13w
0x180009b55  mov     [rbp+13F0h+var_1430], r13b
0x180009b59  mov     rdx, [rbp+13F0h+arg_30]; int
0x180009b60  mov     ecx, [rdx]; this
0x180009b62  mov     [rsp+14F0h+var_14C8], ecx
0x180009b66  mov     eax, [rdx+4]
0x180009b69  mov     [rsp+14F0h+var_14C4], eax
0x180009b6d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009b72  mov     r12d, eax
0x180009b75  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180009b7a  mov     ecx, r13d
0x180009b7d  lea     eax, [r13+8]
0x180009b81  cmp     dword ptr [rdx+8], 1
0x180009b85  cmovz   ecx, eax
0x180009b88  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009b8c  lea     ecx, [rax-7]
0x180009b8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009b97  inc     ecx
0x180009b99  mov     [rsp+14F0h+var_14C0], ecx
0x180009b9d  mov     rcx, [rbp+13F0h+arg_38]
0x180009ba4  test    rcx, rcx
0x180009ba7  jz      short loc_180009BB4
0x180009ba9  cmp     [rcx], r13w
0x180009bad  mov     [rsp+14F0h+var_14B8], rcx
0x180009bb2  jnz     short loc_180009BB9
0x180009bb4  mov     [rsp+14F0h+var_14B8], r13
0x180009bb9  call    cs:__imp_GetCurrentThreadId
0x180009bbf  mov     [rsp+14F0h+var_14B0], eax
0x180009bc3  mov     [rsp+14F0h+var_1498], r14
0x180009bc8  mov     [rsp+14F0h+var_1490], esi
0x180009bcc  mov     [rsp+14F0h+var_148C], r12d
0x180009bd1  mov     [rsp+14F0h+var_14A8], r13
0x180009bd6  mov     [rsp+14F0h+var_14A0], r13
0x180009bdb  mov     [rbp+13F0h+var_1448], r15
0x180009bdf  mov     [rbp+13F0h+var_1440], rbx
0x180009be3  mov     [rsp+14F0h+var_1488], r13
0x180009be8  xorps   xmm0, xmm0
0x180009beb  xor     eax, eax
0x180009bed  movups  [rbp+13F0h+var_1468], xmm0
0x180009bf1  mov     [rbp+13F0h+var_1458], rax
0x180009bf5  xorps   xmm1, xmm1
0x180009bf8  movups  [rsp+14F0h+var_1480], xmm1
0x180009bfd  mov     [rbp+13F0h+var_1470], rax
0x180009c01  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009c08  test    rax, rax
0x180009c0b  jz      short loc_180009C18
0x180009c0d  call    _guard_dispatch_icall
0x180009c12  mov     [rbp+13F0h+var_1450], rax
0x180009c16  jmp     short loc_180009C1C
0x180009c18  mov     [rbp+13F0h+var_1450], r13
0x180009c1c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009c23  test    rax, rax
0x180009c26  jz      short loc_180009C32
0x180009c28  lea     rcx, [rsp+14F0h+var_14D0]
0x180009c2d  call    _guard_dispatch_icall
0x180009c32  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009c39  test    rax, rax
0x180009c3c  jz      short loc_180009C52
0x180009c3e  mov     r8d, 400h
0x180009c44  lea     rdx, [rbp+13F0h+var_1430]
0x180009c48  lea     rcx, [rsp+14F0h+var_14D0]
0x180009c4d  call    _guard_dispatch_icall
0x180009c52  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009c59  test    rax, rax
0x180009c5c  jz      short loc_180009C68
0x180009c5e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009c63  call    _guard_dispatch_icall
0x180009c68  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009c6f  test    rax, rax
0x180009c72  jz      short loc_180009C8A
0x180009c74  test    dil, dil
0x180009c77  jnz     short loc_180009C8A
0x180009c79  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009c7e  jnz     short loc_180009C8A
0x180009c80  lea     rcx, [rsp+14F0h+var_14D0]
0x180009c85  call    _guard_dispatch_icall
0x180009c8a  cmp     [rsp+14F0h+var_14C8], r13d
0x180009c8f  jl      short loc_180009C97
0x180009c91  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009c97  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180009c9e  jnz     short loc_180009CC8
0x180009ca0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009ca7  test    rax, rax
0x180009caa  jz      short loc_180009CB6
0x180009cac  call    _guard_dispatch_icall
0x180009cb1  movzx   ecx, al
0x180009cb4  jmp     short loc_180009CC4
0x180009cb6  call    cs:__imp_IsDebuggerPresent
0x180009cbc  mov     ecx, r13d
0x180009cbf  test    eax, eax
0x180009cc1  setnz   cl
0x180009cc4  test    ecx, ecx
0x180009cc6  jz      short loc_180009CD1
0x180009cc8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009ccd  mov     bl, 1
0x180009ccf  jz      short loc_180009CD4
0x180009cd1  mov     bl, r13b
0x180009cd4  test    dil, dil
0x180009cd7  jnz     short loc_180009D03
0x180009cd9  test    bl, bl
0x180009cdb  jnz     short loc_180009D03
0x180009cdd  mov     rax, cs:g_pfnResultLoggingCallback
0x180009ce4  test    rax, rax
0x180009ce7  jz      short loc_180009D60
0x180009ce9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009cf0  jnz     short loc_180009D60
0x180009cf2  xor     r8d, r8d
0x180009cf5  xor     edx, edx
0x180009cf7  lea     rcx, [rsp+14F0h+var_14D0]
0x180009cfc  call    _guard_dispatch_icall
0x180009d01  jmp     short loc_180009D60
0x180009d03  mov     esi, 800h
0x180009d08  mov     rax, cs:g_pfnResultLoggingCallback
0x180009d0f  test    rax, rax
0x180009d12  jz      short loc_180009D31
0x180009d14  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009d1b  jnz     short loc_180009D31
0x180009d1d  mov     r8d, esi
0x180009d20  lea     rdx, [rbp+13F0h+OutputString]
0x180009d27  lea     rcx, [rsp+14F0h+var_14D0]
0x180009d2c  call    _guard_dispatch_icall
0x180009d31  cmp     [rbp+13F0h+OutputString], r13w
0x180009d39  jnz     short loc_180009D4F
0x180009d3b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009d40  mov     rdx, rsi; wchar_t *
0x180009d43  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009d4a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180009d4f  test    bl, bl
0x180009d51  jz      short loc_180009D60
0x180009d53  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009d5a  call    cs:__imp_OutputDebugStringW
0x180009d60  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180009d65  jnz     short loc_180009D70
0x180009d67  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180009d6e  jz      short loc_180009D82
0x180009d70  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009d77  test    rax, rax
0x180009d7a  jz      short loc_180009D82
0x180009d7c  call    _guard_dispatch_icall
0x180009d81  nop
0x180009d82  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180009d87  jz      short loc_180009D94
0x180009d89  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009d8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009d94  test    dil, dil
0x180009d97  jz      short loc_180009DB1
0x180009d99  lea     rdx, [rbp+13F0h+OutputString]
0x180009da0  lea     rcx, [rsp+14F0h+var_14D0]
0x180009da5  mov     rax, cs:g_pfnThrowPlatformException
0x180009dac  call    _guard_dispatch_icall
0x180009db1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009db6  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180009dbb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009dc0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
