# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a59c`
- end: `0x18000a84b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `687`
- prototype: `void __fastcall(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009f9c`

## callees

- `0x180007888`
- `0x180007d10`
- `0x180008c90`
- `0x180008ef0`
- `0x18000a59c`
- `0x1800dd930`
- `0x1800e45c0`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a662`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a7ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a7ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a758`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a758`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8)
{
  unsigned int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
  unsigned __int64 v18[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *a7;
  v11 = wil::details::RecordReturn((wil::details *)LODWORD(v18[1]), (int)a7);
  LODWORD(v18[0]) = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  HIDWORD(v18[0]) = v12;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v18[3] = (unsigned __int64)a8, v14) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v11, a2);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
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
  if ( ((v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v18[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v18, v15);
}

```

## disassembly

```asm
0x18000a59c  push    rbp
0x18000a59e  push    rbx
0x18000a59f  push    rsi
0x18000a5a0  push    rdi
0x18000a5a1  push    r12
0x18000a5a3  push    r14
0x18000a5a5  push    r15
0x18000a5a7  lea     rbp, [rsp-13D0h]
0x18000a5af  mov     eax, 14D0h
0x18000a5b4  call    _alloca_probe
0x18000a5b9  sub     rsp, rax
0x18000a5bc  mov     rax, cs:__security_cookie
0x18000a5c3  xor     rax, rsp
0x18000a5c6  mov     [rbp+1400h+var_40], rax
0x18000a5cd  mov     rsi, r8
0x18000a5d0  mov     edi, edx
0x18000a5d2  mov     rbx, rcx
0x18000a5d5  mov     r14, [rbp+1400h+arg_28]
0x18000a5dc  xor     edx, edx; Val
0x18000a5de  mov     r8d, 98h; Size
0x18000a5e4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000a5e9  call    memset
0x18000a5ee  nop
0x18000a5ef  xor     r12d, r12d
0x18000a5f2  mov     [rbp+1400h+OutputString], r12w
0x18000a5fa  mov     [rbp+1400h+var_1440], r12b
0x18000a5fe  mov     rdx, [rbp+1400h+arg_30]; int
0x18000a605  mov     ecx, [rdx]; this
0x18000a607  mov     [rsp+1500h+var_14D8], ecx
0x18000a60b  mov     eax, [rdx+4]
0x18000a60e  mov     [rsp+1500h+var_14D4], eax
0x18000a612  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a617  mov     r15d, eax
0x18000a61a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000a622  mov     ecx, r12d
0x18000a625  lea     eax, [r12+8]
0x18000a62a  cmp     dword ptr [rdx+8], 1
0x18000a62e  cmovz   ecx, eax
0x18000a631  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000a635  lea     ecx, [rax-7]
0x18000a638  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a640  inc     ecx
0x18000a642  mov     [rsp+1500h+var_14D0], ecx
0x18000a646  mov     rcx, [rbp+1400h+arg_38]
0x18000a64d  test    rcx, rcx
0x18000a650  jz      short loc_18000A65D
0x18000a652  cmp     [rcx], r12w
0x18000a656  mov     [rsp+1500h+var_14C8], rcx
0x18000a65b  jnz     short loc_18000A662
0x18000a65d  mov     [rsp+1500h+var_14C8], r12
0x18000a662  call    cs:__imp_GetCurrentThreadId
0x18000a668  mov     [rsp+1500h+var_14C0], eax
0x18000a66c  mov     [rsp+1500h+var_14A8], rsi
0x18000a671  mov     [rsp+1500h+var_14A0], edi
0x18000a675  mov     [rsp+1500h+var_149C], r15d
0x18000a67a  mov     [rsp+1500h+var_14B8], r12
0x18000a67f  mov     [rsp+1500h+var_14B0], r12
0x18000a684  mov     [rbp+1400h+var_1458], r14
0x18000a688  mov     [rbp+1400h+var_1450], rbx
0x18000a68c  mov     [rsp+1500h+var_1498], r12
0x18000a691  xorps   xmm0, xmm0
0x18000a694  xor     eax, eax
0x18000a696  movups  [rbp+1400h+var_1478], xmm0
0x18000a69a  mov     [rbp+1400h+var_1468], rax
0x18000a69e  xorps   xmm1, xmm1
0x18000a6a1  movups  [rsp+1500h+var_1490], xmm1
0x18000a6a6  mov     [rbp+1400h+var_1480], rax
0x18000a6aa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a6b1  test    rax, rax
0x18000a6b4  jz      short loc_18000A6C1
0x18000a6b6  call    _guard_dispatch_icall
0x18000a6bb  mov     [rbp+1400h+var_1460], rax
0x18000a6bf  jmp     short loc_18000A6C5
0x18000a6c1  mov     [rbp+1400h+var_1460], r12
0x18000a6c5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a6cc  test    rax, rax
0x18000a6cf  jz      short loc_18000A6DB
0x18000a6d1  lea     rcx, [rsp+1500h+var_14E0]
0x18000a6d6  call    _guard_dispatch_icall
0x18000a6db  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a6e2  test    rax, rax
0x18000a6e5  jz      short loc_18000A6FB
0x18000a6e7  mov     r8d, 400h
0x18000a6ed  lea     rdx, [rbp+1400h+var_1440]
0x18000a6f1  lea     rcx, [rsp+1500h+var_14E0]
0x18000a6f6  call    _guard_dispatch_icall
0x18000a6fb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a702  test    rax, rax
0x18000a705  jz      short loc_18000A711
0x18000a707  lea     rcx, [rsp+1500h+var_14E0]
0x18000a70c  call    _guard_dispatch_icall
0x18000a711  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a718  test    rax, rax
0x18000a71b  jz      short loc_18000A72E
0x18000a71d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a722  jnz     short loc_18000A72E
0x18000a724  lea     rcx, [rsp+1500h+var_14E0]
0x18000a729  call    _guard_dispatch_icall
0x18000a72e  cmp     [rsp+1500h+var_14D8], r12d
0x18000a733  jge     loc_18000A845
0x18000a739  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000a740  jnz     short loc_18000A76A
0x18000a742  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a749  test    rax, rax
0x18000a74c  jz      short loc_18000A758
0x18000a74e  call    _guard_dispatch_icall
0x18000a753  movzx   ecx, al
0x18000a756  jmp     short loc_18000A766
0x18000a758  call    cs:__imp_IsDebuggerPresent
0x18000a75e  mov     ecx, r12d
0x18000a761  test    eax, eax
0x18000a763  setnz   cl
0x18000a766  test    ecx, ecx
0x18000a768  jz      short loc_18000A771
0x18000a76a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a76f  jz      short loc_18000A797
0x18000a771  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a778  test    rax, rax
0x18000a77b  jz      short loc_18000A7F0
0x18000a77d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000a784  jnz     short loc_18000A7F0
0x18000a786  xor     r8d, r8d
0x18000a789  xor     edx, edx
0x18000a78b  lea     rcx, [rsp+1500h+var_14E0]
0x18000a790  call    _guard_dispatch_icall
0x18000a795  jmp     short loc_18000A7F0
0x18000a797  mov     ebx, 800h
0x18000a79c  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a7a3  test    rax, rax
0x18000a7a6  jz      short loc_18000A7C5
0x18000a7a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000a7af  jnz     short loc_18000A7C5
0x18000a7b1  mov     r8d, ebx
0x18000a7b4  lea     rdx, [rbp+1400h+OutputString]
0x18000a7bb  lea     rcx, [rsp+1500h+var_14E0]
0x18000a7c0  call    _guard_dispatch_icall
0x18000a7c5  cmp     [rbp+1400h+OutputString], r12w
0x18000a7cd  jnz     short loc_18000A7E3
0x18000a7cf  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000a7d4  mov     rdx, rbx; wchar_t *
0x18000a7d7  lea     rcx, [rbp+1400h+OutputString]; this
0x18000a7de  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000a7e3  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000a7ea  call    cs:__imp_OutputDebugStringW
0x18000a7f0  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000a7f5  jnz     short loc_18000A800
0x18000a7f7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000a7fe  jz      short loc_18000A812
0x18000a800  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a807  test    rax, rax
0x18000a80a  jz      short loc_18000A812
0x18000a80c  call    _guard_dispatch_icall
0x18000a811  nop
0x18000a812  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000a817  jnz     short loc_18000A83A
0x18000a819  mov     rcx, [rbp+1400h+var_40]
0x18000a820  xor     rcx, rsp; StackCookie
0x18000a823  call    __security_check_cookie
0x18000a828  add     rsp, 14D0h
0x18000a82f  pop     r15
0x18000a831  pop     r14
0x18000a833  pop     r12
0x18000a835  pop     rdi
0x18000a836  pop     rsi
0x18000a837  pop     rbx
0x18000a838  pop     rbp
0x18000a839  retn
0x18000a83a  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000a83f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000a845  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
