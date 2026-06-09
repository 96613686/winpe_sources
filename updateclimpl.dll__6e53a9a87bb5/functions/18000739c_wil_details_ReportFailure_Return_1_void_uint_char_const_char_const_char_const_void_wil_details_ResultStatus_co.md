# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000739c`
- end: `0x18000764b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `687`
- prototype: `void __fastcall(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006f7c`

## callees

- `0x180004298`
- `0x180004724`
- `0x180004b08`
- `0x180005f00`
- `0x18000739c`
- `0x180010310`
- `0x180014870`
- `0x1800148e0`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007462`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007462`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800075ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800075ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007558`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007558`

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
0x18000739c  push    rbp
0x18000739e  push    rbx
0x18000739f  push    rsi
0x1800073a0  push    rdi
0x1800073a1  push    r12
0x1800073a3  push    r14
0x1800073a5  push    r15
0x1800073a7  lea     rbp, [rsp-13D0h]
0x1800073af  mov     eax, 14D0h
0x1800073b4  call    _alloca_probe
0x1800073b9  sub     rsp, rax
0x1800073bc  mov     rax, cs:__security_cookie
0x1800073c3  xor     rax, rsp
0x1800073c6  mov     [rbp+1400h+var_40], rax
0x1800073cd  mov     rsi, r8
0x1800073d0  mov     edi, edx
0x1800073d2  mov     rbx, rcx
0x1800073d5  mov     r14, [rbp+1400h+arg_28]
0x1800073dc  xor     edx, edx; Val
0x1800073de  mov     r8d, 98h; Size
0x1800073e4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800073e9  call    memset
0x1800073ee  nop
0x1800073ef  xor     r12d, r12d
0x1800073f2  mov     [rbp+1400h+OutputString], r12w
0x1800073fa  mov     [rbp+1400h+var_1440], r12b
0x1800073fe  mov     rdx, [rbp+1400h+arg_30]; int
0x180007405  mov     ecx, [rdx]; this
0x180007407  mov     [rsp+1500h+var_14D8], ecx
0x18000740b  mov     eax, [rdx+4]
0x18000740e  mov     [rsp+1500h+var_14D4], eax
0x180007412  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007417  mov     r15d, eax
0x18000741a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007422  mov     ecx, r12d
0x180007425  lea     eax, [r12+8]
0x18000742a  cmp     dword ptr [rdx+8], 1
0x18000742e  cmovz   ecx, eax
0x180007431  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007435  lea     ecx, [rax-7]
0x180007438  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007440  inc     ecx
0x180007442  mov     [rsp+1500h+var_14D0], ecx
0x180007446  mov     rcx, [rbp+1400h+arg_38]
0x18000744d  test    rcx, rcx
0x180007450  jz      short loc_18000745D
0x180007452  cmp     [rcx], r12w
0x180007456  mov     [rsp+1500h+var_14C8], rcx
0x18000745b  jnz     short loc_180007462
0x18000745d  mov     [rsp+1500h+var_14C8], r12
0x180007462  call    cs:__imp_GetCurrentThreadId
0x180007468  mov     [rsp+1500h+var_14C0], eax
0x18000746c  mov     [rsp+1500h+var_14A8], rsi
0x180007471  mov     [rsp+1500h+var_14A0], edi
0x180007475  mov     [rsp+1500h+var_149C], r15d
0x18000747a  mov     [rsp+1500h+var_14B8], r12
0x18000747f  mov     [rsp+1500h+var_14B0], r12
0x180007484  mov     [rbp+1400h+var_1458], r14
0x180007488  mov     [rbp+1400h+var_1450], rbx
0x18000748c  mov     [rsp+1500h+var_1498], r12
0x180007491  xorps   xmm0, xmm0
0x180007494  xor     eax, eax
0x180007496  movups  [rbp+1400h+var_1478], xmm0
0x18000749a  mov     [rbp+1400h+var_1468], rax
0x18000749e  xorps   xmm1, xmm1
0x1800074a1  movups  [rsp+1500h+var_1490], xmm1
0x1800074a6  mov     [rbp+1400h+var_1480], rax
0x1800074aa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800074b1  test    rax, rax
0x1800074b4  jz      short loc_1800074C1
0x1800074b6  call    _guard_dispatch_icall
0x1800074bb  mov     [rbp+1400h+var_1460], rax
0x1800074bf  jmp     short loc_1800074C5
0x1800074c1  mov     [rbp+1400h+var_1460], r12
0x1800074c5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800074cc  test    rax, rax
0x1800074cf  jz      short loc_1800074DB
0x1800074d1  lea     rcx, [rsp+1500h+var_14E0]
0x1800074d6  call    _guard_dispatch_icall
0x1800074db  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800074e2  test    rax, rax
0x1800074e5  jz      short loc_1800074FB
0x1800074e7  mov     r8d, 400h
0x1800074ed  lea     rdx, [rbp+1400h+var_1440]
0x1800074f1  lea     rcx, [rsp+1500h+var_14E0]
0x1800074f6  call    _guard_dispatch_icall
0x1800074fb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007502  test    rax, rax
0x180007505  jz      short loc_180007511
0x180007507  lea     rcx, [rsp+1500h+var_14E0]
0x18000750c  call    _guard_dispatch_icall
0x180007511  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007518  test    rax, rax
0x18000751b  jz      short loc_18000752E
0x18000751d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007522  jnz     short loc_18000752E
0x180007524  lea     rcx, [rsp+1500h+var_14E0]
0x180007529  call    _guard_dispatch_icall
0x18000752e  cmp     [rsp+1500h+var_14D8], r12d
0x180007533  jge     loc_180007645
0x180007539  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007540  jnz     short loc_18000756A
0x180007542  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007549  test    rax, rax
0x18000754c  jz      short loc_180007558
0x18000754e  call    _guard_dispatch_icall
0x180007553  movzx   ecx, al
0x180007556  jmp     short loc_180007566
0x180007558  call    cs:__imp_IsDebuggerPresent
0x18000755e  mov     ecx, r12d
0x180007561  test    eax, eax
0x180007563  setnz   cl
0x180007566  test    ecx, ecx
0x180007568  jz      short loc_180007571
0x18000756a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000756f  jz      short loc_180007597
0x180007571  mov     rax, cs:g_pfnResultLoggingCallback
0x180007578  test    rax, rax
0x18000757b  jz      short loc_1800075F0
0x18000757d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007584  jnz     short loc_1800075F0
0x180007586  xor     r8d, r8d
0x180007589  xor     edx, edx
0x18000758b  lea     rcx, [rsp+1500h+var_14E0]
0x180007590  call    _guard_dispatch_icall
0x180007595  jmp     short loc_1800075F0
0x180007597  mov     ebx, 800h
0x18000759c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800075a3  test    rax, rax
0x1800075a6  jz      short loc_1800075C5
0x1800075a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800075af  jnz     short loc_1800075C5
0x1800075b1  mov     r8d, ebx
0x1800075b4  lea     rdx, [rbp+1400h+OutputString]
0x1800075bb  lea     rcx, [rsp+1500h+var_14E0]
0x1800075c0  call    _guard_dispatch_icall
0x1800075c5  cmp     [rbp+1400h+OutputString], r12w
0x1800075cd  jnz     short loc_1800075E3
0x1800075cf  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800075d4  mov     rdx, rbx; wchar_t *
0x1800075d7  lea     rcx, [rbp+1400h+OutputString]; this
0x1800075de  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800075e3  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800075ea  call    cs:__imp_OutputDebugStringW
0x1800075f0  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800075f5  jnz     short loc_180007600
0x1800075f7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800075fe  jz      short loc_180007612
0x180007600  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007607  test    rax, rax
0x18000760a  jz      short loc_180007612
0x18000760c  call    _guard_dispatch_icall
0x180007611  nop
0x180007612  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180007617  jnz     short loc_18000763A
0x180007619  mov     rcx, [rbp+1400h+var_40]
0x180007620  xor     rcx, rsp; StackCookie
0x180007623  call    __security_check_cookie
0x180007628  add     rsp, 14D0h
0x18000762f  pop     r15
0x180007631  pop     r14
0x180007633  pop     r12
0x180007635  pop     rdi
0x180007636  pop     rsi
0x180007637  pop     rbx
0x180007638  pop     rbp
0x180007639  retn
0x18000763a  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000763f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007645  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
