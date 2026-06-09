# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008f14`
- end: `0x1800091c3`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `687`
- prototype: `void __fastcall(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800091cc`

## callees

- `0x180008940`
- `0x18000897c`
- `0x180008f14`
- `0x180009584`
- `0x1800098dc`
- `0x18008fe00`
- `0x180096100`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009162`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009162`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800090d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800090d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fda`

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
0x180008f14  push    rbp
0x180008f16  push    rbx
0x180008f17  push    rsi
0x180008f18  push    rdi
0x180008f19  push    r12
0x180008f1b  push    r14
0x180008f1d  push    r15
0x180008f1f  lea     rbp, [rsp-13D0h]
0x180008f27  mov     eax, 14D0h
0x180008f2c  call    _alloca_probe
0x180008f31  sub     rsp, rax
0x180008f34  mov     rax, cs:__security_cookie
0x180008f3b  xor     rax, rsp
0x180008f3e  mov     [rbp+1400h+var_40], rax
0x180008f45  mov     rsi, r8
0x180008f48  mov     edi, edx
0x180008f4a  mov     rbx, rcx
0x180008f4d  mov     r14, [rbp+1400h+arg_28]
0x180008f54  xor     edx, edx; Val
0x180008f56  mov     r8d, 98h; Size
0x180008f5c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008f61  call    memset
0x180008f66  nop
0x180008f67  xor     r12d, r12d
0x180008f6a  mov     [rbp+1400h+OutputString], r12w
0x180008f72  mov     [rbp+1400h+var_1440], r12b
0x180008f76  mov     rdx, [rbp+1400h+arg_30]; int
0x180008f7d  mov     ecx, [rdx]; this
0x180008f7f  mov     [rsp+1500h+var_14D8], ecx
0x180008f83  mov     eax, [rdx+4]
0x180008f86  mov     [rsp+1500h+var_14D4], eax
0x180008f8a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008f8f  mov     r15d, eax
0x180008f92  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180008f9a  mov     ecx, r12d
0x180008f9d  lea     eax, [r12+8]
0x180008fa2  cmp     dword ptr [rdx+8], 1
0x180008fa6  cmovz   ecx, eax
0x180008fa9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180008fad  lea     ecx, [rax-7]
0x180008fb0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008fb8  inc     ecx
0x180008fba  mov     [rsp+1500h+var_14D0], ecx
0x180008fbe  mov     rcx, [rbp+1400h+arg_38]
0x180008fc5  test    rcx, rcx
0x180008fc8  jz      short loc_180008FD5
0x180008fca  cmp     [rcx], r12w
0x180008fce  mov     [rsp+1500h+var_14C8], rcx
0x180008fd3  jnz     short loc_180008FDA
0x180008fd5  mov     [rsp+1500h+var_14C8], r12
0x180008fda  call    cs:__imp_GetCurrentThreadId
0x180008fe0  mov     [rsp+1500h+var_14C0], eax
0x180008fe4  mov     [rsp+1500h+var_14A8], rsi
0x180008fe9  mov     [rsp+1500h+var_14A0], edi
0x180008fed  mov     [rsp+1500h+var_149C], r15d
0x180008ff2  mov     [rsp+1500h+var_14B8], r12
0x180008ff7  mov     [rsp+1500h+var_14B0], r12
0x180008ffc  mov     [rbp+1400h+var_1458], r14
0x180009000  mov     [rbp+1400h+var_1450], rbx
0x180009004  mov     [rsp+1500h+var_1498], r12
0x180009009  xorps   xmm0, xmm0
0x18000900c  xor     eax, eax
0x18000900e  movups  [rbp+1400h+var_1478], xmm0
0x180009012  mov     [rbp+1400h+var_1468], rax
0x180009016  xorps   xmm1, xmm1
0x180009019  movups  [rsp+1500h+var_1490], xmm1
0x18000901e  mov     [rbp+1400h+var_1480], rax
0x180009022  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009029  test    rax, rax
0x18000902c  jz      short loc_180009039
0x18000902e  call    _guard_dispatch_icall
0x180009033  mov     [rbp+1400h+var_1460], rax
0x180009037  jmp     short loc_18000903D
0x180009039  mov     [rbp+1400h+var_1460], r12
0x18000903d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009044  test    rax, rax
0x180009047  jz      short loc_180009053
0x180009049  lea     rcx, [rsp+1500h+var_14E0]
0x18000904e  call    _guard_dispatch_icall
0x180009053  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000905a  test    rax, rax
0x18000905d  jz      short loc_180009073
0x18000905f  mov     r8d, 400h
0x180009065  lea     rdx, [rbp+1400h+var_1440]
0x180009069  lea     rcx, [rsp+1500h+var_14E0]
0x18000906e  call    _guard_dispatch_icall
0x180009073  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000907a  test    rax, rax
0x18000907d  jz      short loc_180009089
0x18000907f  lea     rcx, [rsp+1500h+var_14E0]
0x180009084  call    _guard_dispatch_icall
0x180009089  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009090  test    rax, rax
0x180009093  jz      short loc_1800090A6
0x180009095  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000909a  jnz     short loc_1800090A6
0x18000909c  lea     rcx, [rsp+1500h+var_14E0]
0x1800090a1  call    _guard_dispatch_icall
0x1800090a6  cmp     [rsp+1500h+var_14D8], r12d
0x1800090ab  jge     loc_1800091BD
0x1800090b1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800090b8  jnz     short loc_1800090E2
0x1800090ba  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800090c1  test    rax, rax
0x1800090c4  jz      short loc_1800090D0
0x1800090c6  call    _guard_dispatch_icall
0x1800090cb  movzx   ecx, al
0x1800090ce  jmp     short loc_1800090DE
0x1800090d0  call    cs:__imp_IsDebuggerPresent
0x1800090d6  mov     ecx, r12d
0x1800090d9  test    eax, eax
0x1800090db  setnz   cl
0x1800090de  test    ecx, ecx
0x1800090e0  jz      short loc_1800090E9
0x1800090e2  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800090e7  jz      short loc_18000910F
0x1800090e9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800090f0  test    rax, rax
0x1800090f3  jz      short loc_180009168
0x1800090f5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800090fc  jnz     short loc_180009168
0x1800090fe  xor     r8d, r8d
0x180009101  xor     edx, edx
0x180009103  lea     rcx, [rsp+1500h+var_14E0]
0x180009108  call    _guard_dispatch_icall
0x18000910d  jmp     short loc_180009168
0x18000910f  mov     ebx, 800h
0x180009114  mov     rax, cs:g_pfnResultLoggingCallback
0x18000911b  test    rax, rax
0x18000911e  jz      short loc_18000913D
0x180009120  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180009127  jnz     short loc_18000913D
0x180009129  mov     r8d, ebx
0x18000912c  lea     rdx, [rbp+1400h+OutputString]
0x180009133  lea     rcx, [rsp+1500h+var_14E0]
0x180009138  call    _guard_dispatch_icall
0x18000913d  cmp     [rbp+1400h+OutputString], r12w
0x180009145  jnz     short loc_18000915B
0x180009147  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000914c  mov     rdx, rbx; wchar_t *
0x18000914f  lea     rcx, [rbp+1400h+OutputString]; this
0x180009156  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000915b  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180009162  call    cs:__imp_OutputDebugStringW
0x180009168  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000916d  jnz     short loc_180009178
0x18000916f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180009176  jz      short loc_18000918A
0x180009178  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000917f  test    rax, rax
0x180009182  jz      short loc_18000918A
0x180009184  call    _guard_dispatch_icall
0x180009189  nop
0x18000918a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000918f  jnz     short loc_1800091B2
0x180009191  mov     rcx, [rbp+1400h+var_40]
0x180009198  xor     rcx, rsp; StackCookie
0x18000919b  call    __security_check_cookie
0x1800091a0  add     rsp, 14D0h
0x1800091a7  pop     r15
0x1800091a9  pop     r14
0x1800091ab  pop     r12
0x1800091ad  pop     rdi
0x1800091ae  pop     rsi
0x1800091af  pop     rbx
0x1800091b0  pop     rbp
0x1800091b1  retn
0x1800091b2  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800091b7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800091bd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
