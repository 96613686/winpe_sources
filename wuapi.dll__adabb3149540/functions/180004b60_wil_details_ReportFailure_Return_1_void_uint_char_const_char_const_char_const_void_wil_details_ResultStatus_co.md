# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004b60`
- end: `0x180004df6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004808`

## callees

- `0x180001e74`
- `0x1800022fc`
- `0x18000358c`
- `0x1800037f0`
- `0x180004b60`
- `0x18000fce0`
- `0x180015990`
- `0x180015a00`
- `0x180015a80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d03`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004d95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004d95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7)
{
  unsigned int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v15; // r9
  unsigned __int64 v16[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v16, 0, 0x98u);
  OutputString[0] = 0;
  v17[0] = 0;
  v16[1] = *a7;
  v10 = wil::details::RecordReturn((wil::details *)LODWORD(v16[1]), (int)a7);
  LODWORD(v16[0]) = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  HIDWORD(v16[0]) = v11;
  LODWORD(v16[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v16[3] = 0;
  LODWORD(v16[4]) = GetCurrentThreadId();
  v16[7] = a3;
  v16[8] = __PAIR64__(v10, a2);
  v16[5] = 0;
  v16[6] = 0;
  v16[17] = a6;
  v16[18] = a1;
  memset(&v16[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v16[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v16[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v17, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v16[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048, v15);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v16, v15);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v16, 0, 0, v15);
  }
  if ( ((v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v16[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v13);
}

```

## disassembly

```asm
0x180004b60  push    rbp
0x180004b62  push    rbx
0x180004b63  push    rsi
0x180004b64  push    rdi
0x180004b65  push    r12
0x180004b67  push    r14
0x180004b69  push    r15
0x180004b6b  lea     rbp, [rsp-13D0h]
0x180004b73  mov     eax, 14D0h
0x180004b78  call    _alloca_probe
0x180004b7d  sub     rsp, rax
0x180004b80  mov     rax, cs:__security_cookie
0x180004b87  xor     rax, rsp
0x180004b8a  mov     [rbp+1400h+var_40], rax
0x180004b91  mov     r14, r8
0x180004b94  mov     esi, edx
0x180004b96  mov     r15, rcx
0x180004b99  mov     rdi, [rbp+1400h+arg_28]
0x180004ba0  xor     edx, edx; Val
0x180004ba2  mov     r8d, 98h; Size
0x180004ba8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004bad  call    memset
0x180004bb2  nop
0x180004bb3  xor     r12d, r12d
0x180004bb6  mov     [rbp+1400h+OutputString], r12w
0x180004bbe  mov     [rbp+1400h+var_1440], r12b
0x180004bc2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180004bc9  mov     ecx, [rdx]; this
0x180004bcb  mov     [rsp+1500h+var_14D8], ecx
0x180004bcf  mov     eax, [rdx+4]
0x180004bd2  mov     [rsp+1500h+var_14D4], eax
0x180004bd6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004bdb  mov     ebx, eax
0x180004bdd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004be5  mov     ecx, r12d
0x180004be8  lea     eax, [r12+8]
0x180004bed  cmp     dword ptr [rdx+8], 1
0x180004bf1  cmovz   ecx, eax
0x180004bf4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004bf8  lea     ecx, [rax-7]
0x180004bfb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004c03  inc     ecx
0x180004c05  mov     [rsp+1500h+var_14D0], ecx
0x180004c09  mov     [rsp+1500h+var_14C8], r12
0x180004c0e  call    cs:__imp_GetCurrentThreadId
0x180004c14  mov     [rsp+1500h+var_14C0], eax
0x180004c18  mov     [rsp+1500h+var_14A8], r14
0x180004c1d  mov     [rsp+1500h+var_14A0], esi
0x180004c21  mov     [rsp+1500h+var_149C], ebx
0x180004c25  mov     [rsp+1500h+var_14B8], r12
0x180004c2a  mov     [rsp+1500h+var_14B0], r12
0x180004c2f  mov     [rbp+1400h+var_1458], rdi
0x180004c33  mov     [rbp+1400h+var_1450], r15
0x180004c37  mov     [rsp+1500h+var_1498], r12
0x180004c3c  xorps   xmm0, xmm0
0x180004c3f  xor     eax, eax
0x180004c41  movups  [rbp+1400h+var_1478], xmm0
0x180004c45  mov     [rbp+1400h+var_1468], rax
0x180004c49  xorps   xmm1, xmm1
0x180004c4c  movups  [rsp+1500h+var_1490], xmm1
0x180004c51  mov     [rbp+1400h+var_1480], rax
0x180004c55  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004c5c  test    rax, rax
0x180004c5f  jz      short loc_180004C6C
0x180004c61  call    _guard_dispatch_icall
0x180004c66  mov     [rbp+1400h+var_1460], rax
0x180004c6a  jmp     short loc_180004C70
0x180004c6c  mov     [rbp+1400h+var_1460], r12
0x180004c70  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004c77  test    rax, rax
0x180004c7a  jz      short loc_180004C86
0x180004c7c  lea     rcx, [rsp+1500h+var_14E0]
0x180004c81  call    _guard_dispatch_icall
0x180004c86  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004c8d  test    rax, rax
0x180004c90  jz      short loc_180004CA6
0x180004c92  mov     r8d, 400h
0x180004c98  lea     rdx, [rbp+1400h+var_1440]
0x180004c9c  lea     rcx, [rsp+1500h+var_14E0]
0x180004ca1  call    _guard_dispatch_icall
0x180004ca6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004cad  test    rax, rax
0x180004cb0  jz      short loc_180004CBC
0x180004cb2  lea     rcx, [rsp+1500h+var_14E0]
0x180004cb7  call    _guard_dispatch_icall
0x180004cbc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004cc3  test    rax, rax
0x180004cc6  jz      short loc_180004CD9
0x180004cc8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004ccd  jnz     short loc_180004CD9
0x180004ccf  lea     rcx, [rsp+1500h+var_14E0]
0x180004cd4  call    _guard_dispatch_icall
0x180004cd9  cmp     [rsp+1500h+var_14D8], r12d
0x180004cde  jge     loc_180004DF0
0x180004ce4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004ceb  jnz     short loc_180004D15
0x180004ced  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004cf4  test    rax, rax
0x180004cf7  jz      short loc_180004D03
0x180004cf9  call    _guard_dispatch_icall
0x180004cfe  movzx   ecx, al
0x180004d01  jmp     short loc_180004D11
0x180004d03  call    cs:__imp_IsDebuggerPresent
0x180004d09  mov     ecx, r12d
0x180004d0c  test    eax, eax
0x180004d0e  setnz   cl
0x180004d11  test    ecx, ecx
0x180004d13  jz      short loc_180004D1C
0x180004d15  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004d1a  jz      short loc_180004D42
0x180004d1c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d23  test    rax, rax
0x180004d26  jz      short loc_180004D9B
0x180004d28  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004d2f  jnz     short loc_180004D9B
0x180004d31  xor     r8d, r8d
0x180004d34  xor     edx, edx
0x180004d36  lea     rcx, [rsp+1500h+var_14E0]
0x180004d3b  call    _guard_dispatch_icall
0x180004d40  jmp     short loc_180004D9B
0x180004d42  mov     ebx, 800h
0x180004d47  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d4e  test    rax, rax
0x180004d51  jz      short loc_180004D70
0x180004d53  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004d5a  jnz     short loc_180004D70
0x180004d5c  mov     r8d, ebx
0x180004d5f  lea     rdx, [rbp+1400h+OutputString]
0x180004d66  lea     rcx, [rsp+1500h+var_14E0]
0x180004d6b  call    _guard_dispatch_icall
0x180004d70  cmp     [rbp+1400h+OutputString], r12w
0x180004d78  jnz     short loc_180004D8E
0x180004d7a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004d7f  mov     rdx, rbx; wchar_t *
0x180004d82  lea     rcx, [rbp+1400h+OutputString]; this
0x180004d89  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180004d8e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004d95  call    cs:__imp_OutputDebugStringW
0x180004d9b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004da0  jnz     short loc_180004DAB
0x180004da2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004da9  jz      short loc_180004DBD
0x180004dab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004db2  test    rax, rax
0x180004db5  jz      short loc_180004DBD
0x180004db7  call    _guard_dispatch_icall
0x180004dbc  nop
0x180004dbd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004dc2  jnz     short loc_180004DE5
0x180004dc4  mov     rcx, [rbp+1400h+var_40]
0x180004dcb  xor     rcx, rsp; StackCookie
0x180004dce  call    __security_check_cookie
0x180004dd3  add     rsp, 14D0h
0x180004dda  pop     r15
0x180004ddc  pop     r14
0x180004dde  pop     r12
0x180004de0  pop     rdi
0x180004de1  pop     rsi
0x180004de2  pop     rbx
0x180004de3  pop     rbp
0x180004de4  retn
0x180004de5  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004dea  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004df0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
