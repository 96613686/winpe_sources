# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180003360`
- end: `0x1800035d9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003048`

## callees

- `0x180002b38`
- `0x180003360`
- `0x180007e34`
- `0x18000884c`
- `0x18000a150`
- `0x18000d030`
- `0x180014400`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003419`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800035a6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800035a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000351c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000351c`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180003360  mov     [rsp-8+arg_18], rbx
0x180003365  push    rbp
0x180003366  push    rsi
0x180003367  push    rdi
0x180003368  push    r12
0x18000336a  push    r13
0x18000336c  push    r14
0x18000336e  push    r15
0x180003370  lea     rbp, [rsp-13C0h]
0x180003378  mov     eax, 14C0h
0x18000337d  call    _alloca_probe
0x180003382  sub     rsp, rax
0x180003385  mov     r14, r8
0x180003388  mov     esi, edx
0x18000338a  mov     rdi, rcx
0x18000338d  mov     r15, [rbp+13F0h+arg_28]
0x180003394  xor     edx, edx; Val
0x180003396  mov     r8d, 98h; Size
0x18000339c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800033a1  call    memset_0
0x1800033a6  nop
0x1800033a7  xor     r13d, r13d
0x1800033aa  mov     [rbp+13F0h+OutputString], r13w
0x1800033b2  mov     [rbp+13F0h+var_1430], r13b
0x1800033b6  mov     rbx, [rbp+13F0h+arg_30]
0x1800033bd  mov     ecx, [rbx]; this
0x1800033bf  mov     [rsp+14F0h+var_14C8], ecx
0x1800033c3  mov     eax, [rbx+4]
0x1800033c6  mov     [rsp+14F0h+var_14C4], eax
0x1800033ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800033cf  mov     r12d, eax
0x1800033d2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800033da  mov     ecx, r13d
0x1800033dd  lea     eax, [r13+8]
0x1800033e1  cmp     dword ptr [rbx+8], 1
0x1800033e5  cmovz   ecx, eax
0x1800033e8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800033ec  lea     ecx, [rax-7]
0x1800033ef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800033f7  inc     ecx
0x1800033f9  mov     [rsp+14F0h+var_14C0], ecx
0x1800033fd  mov     rcx, [rbp+13F0h+arg_38]
0x180003404  test    rcx, rcx
0x180003407  jz      short loc_180003414
0x180003409  cmp     [rcx], r13w
0x18000340d  mov     [rsp+14F0h+var_14B8], rcx
0x180003412  jnz     short loc_180003419
0x180003414  mov     [rsp+14F0h+var_14B8], r13
0x180003419  call    cs:__imp_GetCurrentThreadId
0x18000341f  mov     [rsp+14F0h+var_14B0], eax
0x180003423  mov     [rsp+14F0h+var_1498], r14
0x180003428  mov     [rsp+14F0h+var_1490], esi
0x18000342c  mov     [rsp+14F0h+var_148C], r12d
0x180003431  mov     [rsp+14F0h+var_14A8], r13
0x180003436  mov     [rsp+14F0h+var_14A0], r13
0x18000343b  mov     [rbp+13F0h+var_1448], r15
0x18000343f  mov     [rbp+13F0h+var_1440], rdi
0x180003443  mov     [rsp+14F0h+var_1488], r13
0x180003448  xorps   xmm0, xmm0
0x18000344b  xor     eax, eax
0x18000344d  movups  [rbp+13F0h+var_1468], xmm0
0x180003451  mov     [rbp+13F0h+var_1458], rax
0x180003455  xorps   xmm1, xmm1
0x180003458  movups  [rsp+14F0h+var_1480], xmm1
0x18000345d  mov     [rbp+13F0h+var_1470], rax
0x180003461  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003468  test    rax, rax
0x18000346b  jz      short loc_180003478
0x18000346d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003472  mov     [rbp+13F0h+var_1450], rax
0x180003476  jmp     short loc_18000347C
0x180003478  mov     [rbp+13F0h+var_1450], r13
0x18000347c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003483  test    rax, rax
0x180003486  jz      short loc_180003492
0x180003488  lea     rcx, [rsp+14F0h+var_14D0]
0x18000348d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003492  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003499  test    rax, rax
0x18000349c  jz      short loc_1800034B2
0x18000349e  mov     r8d, 400h
0x1800034a4  lea     rdx, [rbp+13F0h+var_1430]
0x1800034a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800034b9  test    rax, rax
0x1800034bc  jz      short loc_1800034C8
0x1800034be  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800034cf  test    rax, rax
0x1800034d2  jz      short loc_1800034E5
0x1800034d4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800034d9  jnz     short loc_1800034E5
0x1800034db  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e5  cmp     [rsp+14F0h+var_14C8], r13d
0x1800034ea  jl      short loc_1800034FE
0x1800034ec  mov     ecx, 8000FFFFh; this
0x1800034f1  mov     [rsp+14F0h+var_14C8], ecx
0x1800034f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800034fa  mov     [rsp+14F0h+var_14C4], eax
0x1800034fe  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003505  jnz     short loc_180003526
0x180003507  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000350e  test    rax, rax
0x180003511  jz      short loc_18000351C
0x180003513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003518  test    al, al
0x18000351a  jmp     short loc_180003524
0x18000351c  call    cs:__imp_IsDebuggerPresent
0x180003522  test    eax, eax
0x180003524  jz      short loc_18000352D
0x180003526  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000352b  jz      short loc_180003553
0x18000352d  mov     rax, cs:g_pfnResultLoggingCallback
0x180003534  test    rax, rax
0x180003537  jz      short loc_1800035AC
0x180003539  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003540  jnz     short loc_1800035AC
0x180003542  xor     r8d, r8d
0x180003545  xor     edx, edx
0x180003547  lea     rcx, [rsp+14F0h+var_14D0]
0x18000354c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003551  jmp     short loc_1800035AC
0x180003553  mov     ebx, 800h
0x180003558  mov     rax, cs:g_pfnResultLoggingCallback
0x18000355f  test    rax, rax
0x180003562  jz      short loc_180003581
0x180003564  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000356b  jnz     short loc_180003581
0x18000356d  mov     r8d, ebx
0x180003570  lea     rdx, [rbp+13F0h+OutputString]
0x180003577  lea     rcx, [rsp+14F0h+var_14D0]
0x18000357c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003581  cmp     [rbp+13F0h+OutputString], r13w
0x180003589  jnz     short loc_18000359F
0x18000358b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003590  mov     rdx, rbx; wchar_t *
0x180003593  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000359a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000359f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800035a6  call    cs:__imp_OutputDebugStringW
0x1800035ac  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800035b1  jnz     short loc_1800035BC
0x1800035b3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800035ba  jz      short loc_1800035CE
0x1800035bc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800035c3  test    rax, rax
0x1800035c6  jz      short loc_1800035CE
0x1800035c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035cd  nop
0x1800035ce  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800035d3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
