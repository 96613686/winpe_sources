# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400025a0`
- end: `0x140002855`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000285c`

## callees

- `0x140001b98`
- `0x140001dc4`
- `0x140001efc`
- `0x1400024f0`
- `0x1400025a0`
- `0x14001aa60`
- `0x140020670`
- `0x1400206e0`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400027f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400027f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002762`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002762`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000266c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000266c`

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
        unsigned __int64 *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  unsigned int v13; // r15d
  __int64 v14; // rdx
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v18; // r9
  unsigned __int64 v19[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v20[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v19, 0, 0x98u);
  OutputString[0] = 0;
  v20[0] = 0;
  v19[1] = *a7;
  v13 = wil::details::RecordReturn((wil::details *)LODWORD(v19[1]), (int)a7);
  LODWORD(v19[0]) = 1;
  HIDWORD(v19[0]) = a10;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    HIDWORD(v19[0]) = a10 | 8;
  LODWORD(v19[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v19[3] = (unsigned __int64)a8, v15) )
    v19[3] = 0;
  LODWORD(v19[4]) = GetCurrentThreadId();
  v19[7] = a3;
  v19[8] = __PAIR64__(v13, a2);
  v19[5] = 0;
  v19[6] = 0;
  v19[17] = a6;
  v19[18] = a1;
  memset(&v19[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v19[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v19[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v19, v20, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v19);
  if ( wil::details::g_pfnOriginateCallback && (v19[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v19);
  if ( SLODWORD(v19[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v19[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v19, OutputString, 2048, v18);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v19, v18);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v19, 0, 0, v18);
  }
  if ( ((v19[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v19[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v19, v16);
}

```

## disassembly

```asm
0x1400025a0  push    rbp
0x1400025a2  push    rbx
0x1400025a3  push    rsi
0x1400025a4  push    rdi
0x1400025a5  push    r12
0x1400025a7  push    r14
0x1400025a9  push    r15
0x1400025ab  lea     rbp, [rsp-13D0h]
0x1400025b3  mov     eax, 14D0h
0x1400025b8  call    _alloca_probe
0x1400025bd  sub     rsp, rax
0x1400025c0  mov     rax, cs:__security_cookie
0x1400025c7  xor     rax, rsp
0x1400025ca  mov     [rbp+1400h+var_40], rax
0x1400025d1  mov     rsi, r8
0x1400025d4  mov     edi, edx
0x1400025d6  mov     rbx, rcx
0x1400025d9  mov     r14, [rbp+1400h+arg_28]
0x1400025e0  xor     edx, edx; Val
0x1400025e2  mov     r8d, 98h; Size
0x1400025e8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400025ed  call    memset
0x1400025f2  nop
0x1400025f3  xor     r12d, r12d
0x1400025f6  mov     [rbp+1400h+OutputString], r12w
0x1400025fe  mov     [rbp+1400h+var_1440], r12b
0x140002602  mov     rdx, [rbp+1400h+arg_30]; int
0x140002609  mov     ecx, [rdx]; this
0x14000260b  mov     [rsp+1500h+var_14D8], ecx
0x14000260f  mov     eax, [rdx+4]
0x140002612  mov     [rsp+1500h+var_14D4], eax
0x140002616  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000261b  mov     r15d, eax
0x14000261e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002626  mov     ecx, [rbp+1400h+arg_48]
0x14000262c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002630  cmp     dword ptr [rdx+8], 1
0x140002634  jnz     short loc_14000263D
0x140002636  or      ecx, 8
0x140002639  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000263d  mov     ecx, 1
0x140002642  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000264a  inc     ecx
0x14000264c  mov     [rsp+1500h+var_14D0], ecx
0x140002650  mov     rax, [rbp+1400h+arg_38]
0x140002657  test    rax, rax
0x14000265a  jz      short loc_140002667
0x14000265c  cmp     [rax], r12w
0x140002660  mov     [rsp+1500h+var_14C8], rax
0x140002665  jnz     short loc_14000266C
0x140002667  mov     [rsp+1500h+var_14C8], r12
0x14000266c  call    cs:__imp_GetCurrentThreadId
0x140002672  mov     [rsp+1500h+var_14C0], eax
0x140002676  mov     [rsp+1500h+var_14A8], rsi
0x14000267b  mov     [rsp+1500h+var_14A0], edi
0x14000267f  mov     [rsp+1500h+var_149C], r15d
0x140002684  mov     [rsp+1500h+var_14B8], r12
0x140002689  mov     [rsp+1500h+var_14B0], r12
0x14000268e  mov     [rbp+1400h+var_1458], r14
0x140002692  mov     [rbp+1400h+var_1450], rbx
0x140002696  mov     [rsp+1500h+var_1498], r12
0x14000269b  xorps   xmm0, xmm0
0x14000269e  xor     eax, eax
0x1400026a0  movups  [rbp+1400h+var_1478], xmm0
0x1400026a4  mov     [rbp+1400h+var_1468], rax
0x1400026a8  xorps   xmm1, xmm1
0x1400026ab  movups  [rsp+1500h+var_1490], xmm1
0x1400026b0  mov     [rbp+1400h+var_1480], rax
0x1400026b4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400026bb  test    rax, rax
0x1400026be  jz      short loc_1400026CB
0x1400026c0  call    _guard_dispatch_icall
0x1400026c5  mov     [rbp+1400h+var_1460], rax
0x1400026c9  jmp     short loc_1400026CF
0x1400026cb  mov     [rbp+1400h+var_1460], r12
0x1400026cf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400026d6  test    rax, rax
0x1400026d9  jz      short loc_1400026E5
0x1400026db  lea     rcx, [rsp+1500h+var_14E0]
0x1400026e0  call    _guard_dispatch_icall
0x1400026e5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400026ec  test    rax, rax
0x1400026ef  jz      short loc_140002705
0x1400026f1  mov     r8d, 400h
0x1400026f7  lea     rdx, [rbp+1400h+var_1440]
0x1400026fb  lea     rcx, [rsp+1500h+var_14E0]
0x140002700  call    _guard_dispatch_icall
0x140002705  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000270c  test    rax, rax
0x14000270f  jz      short loc_14000271B
0x140002711  lea     rcx, [rsp+1500h+var_14E0]
0x140002716  call    _guard_dispatch_icall
0x14000271b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002722  test    rax, rax
0x140002725  jz      short loc_140002738
0x140002727  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000272c  jnz     short loc_140002738
0x14000272e  lea     rcx, [rsp+1500h+var_14E0]
0x140002733  call    _guard_dispatch_icall
0x140002738  cmp     [rsp+1500h+var_14D8], r12d
0x14000273d  jge     loc_14000284F
0x140002743  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000274a  jnz     short loc_140002774
0x14000274c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002753  test    rax, rax
0x140002756  jz      short loc_140002762
0x140002758  call    _guard_dispatch_icall
0x14000275d  movzx   ecx, al
0x140002760  jmp     short loc_140002770
0x140002762  call    cs:__imp_IsDebuggerPresent
0x140002768  mov     ecx, r12d
0x14000276b  test    eax, eax
0x14000276d  setnz   cl
0x140002770  test    ecx, ecx
0x140002772  jz      short loc_14000277B
0x140002774  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002779  jz      short loc_1400027A1
0x14000277b  mov     rax, cs:g_pfnResultLoggingCallback
0x140002782  test    rax, rax
0x140002785  jz      short loc_1400027FA
0x140002787  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000278e  jnz     short loc_1400027FA
0x140002790  xor     r8d, r8d
0x140002793  xor     edx, edx
0x140002795  lea     rcx, [rsp+1500h+var_14E0]
0x14000279a  call    _guard_dispatch_icall
0x14000279f  jmp     short loc_1400027FA
0x1400027a1  mov     ebx, 800h
0x1400027a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400027ad  test    rax, rax
0x1400027b0  jz      short loc_1400027CF
0x1400027b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400027b9  jnz     short loc_1400027CF
0x1400027bb  mov     r8d, ebx
0x1400027be  lea     rdx, [rbp+1400h+OutputString]
0x1400027c5  lea     rcx, [rsp+1500h+var_14E0]
0x1400027ca  call    _guard_dispatch_icall
0x1400027cf  cmp     [rbp+1400h+OutputString], r12w
0x1400027d7  jnz     short loc_1400027ED
0x1400027d9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400027de  mov     rdx, rbx; wchar_t *
0x1400027e1  lea     rcx, [rbp+1400h+OutputString]; this
0x1400027e8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1400027ed  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400027f4  call    cs:__imp_OutputDebugStringW
0x1400027fa  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400027ff  jnz     short loc_14000280A
0x140002801  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002808  jz      short loc_14000281C
0x14000280a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002811  test    rax, rax
0x140002814  jz      short loc_14000281C
0x140002816  call    _guard_dispatch_icall
0x14000281b  nop
0x14000281c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002821  jnz     short loc_140002844
0x140002823  mov     rcx, [rbp+1400h+var_40]
0x14000282a  xor     rcx, rsp; StackCookie
0x14000282d  call    __security_check_cookie
0x140002832  add     rsp, 14D0h
0x140002839  pop     r15
0x14000283b  pop     r14
0x14000283d  pop     r12
0x14000283f  pop     rdi
0x140002840  pop     rsi
0x140002841  pop     rbx
0x140002842  pop     rbp
0x140002843  retn
0x140002844  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002849  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000284f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
