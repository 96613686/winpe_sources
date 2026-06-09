# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003318`
- end: `0x1800035ac`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002df8`

## callees

- `0x180003318`
- `0x1800041f4`
- `0x1800050e0`
- `0x1800059f0`
- `0x180005acc`
- `0x18001d33a`
- `0x18001d370`
- `0x18001d400`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003547`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003547`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800034bd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800034bd`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180003318  mov     [rsp-8+arg_10], rbx
0x18000331d  push    rbp
0x18000331e  push    rsi
0x18000331f  push    rdi
0x180003320  push    r14
0x180003322  push    r15
0x180003324  lea     rbp, [rsp-13D0h]
0x18000332c  mov     eax, 14D0h
0x180003331  call    _alloca_probe
0x180003336  sub     rsp, rax
0x180003339  mov     rax, cs:__security_cookie
0x180003340  xor     rax, rsp
0x180003343  mov     [rbp+13F0h+var_30], rax
0x18000334a  mov     rdi, [rbp+13F0h+arg_28]
0x180003351  mov     esi, edx
0x180003353  mov     r14, rcx
0x180003356  xor     edx, edx; Val
0x180003358  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000335d  mov     r8d, 98h; Size
0x180003363  call    memset_0
0x180003368  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000336f  xor     r15d, r15d
0x180003372  mov     [rbp+13F0h+OutputString], r15w
0x18000337a  mov     [rbp+13F0h+var_1430], r15b
0x18000337e  mov     ecx, [rdx]; this
0x180003380  mov     eax, [rdx+4]
0x180003383  mov     [rsp+14F0h+var_14C8], ecx
0x180003387  mov     [rsp+14F0h+var_14C4], eax
0x18000338b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003390  cmp     dword ptr [rdx+8], 1
0x180003394  mov     ebx, eax
0x180003396  lea     eax, [r15+8]
0x18000339a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800033a2  mov     ecx, r15d
0x1800033a5  cmovz   ecx, eax
0x1800033a8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800033ac  lea     ecx, [rax-7]
0x1800033af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800033b7  inc     ecx
0x1800033b9  mov     [rsp+14F0h+var_14B8], r15
0x1800033be  mov     [rsp+14F0h+var_14C0], ecx
0x1800033c2  call    cs:__imp_GetCurrentThreadId
0x1800033c8  xorps   xmm0, xmm0
0x1800033cb  mov     [rsp+14F0h+var_1490], esi
0x1800033cf  mov     [rsp+14F0h+var_14B0], eax
0x1800033d3  xorps   xmm1, xmm1
0x1800033d6  lea     rax, aWil; "wil"
0x1800033dd  mov     [rsp+14F0h+var_148C], ebx
0x1800033e1  mov     [rsp+14F0h+var_1498], rax
0x1800033e6  xor     eax, eax
0x1800033e8  mov     [rbp+13F0h+var_1458], rax
0x1800033ec  mov     [rbp+13F0h+var_1470], rax
0x1800033f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033f7  mov     [rsp+14F0h+var_14A8], r15
0x1800033fc  mov     [rsp+14F0h+var_14A0], r15
0x180003401  mov     [rbp+13F0h+var_1448], rdi
0x180003405  mov     [rbp+13F0h+var_1440], r14
0x180003409  mov     [rsp+14F0h+var_1488], r15
0x18000340e  movups  [rbp+13F0h+var_1468], xmm0
0x180003412  movups  [rsp+14F0h+var_1480], xmm1
0x180003417  test    rax, rax
0x18000341a  jz      short loc_180003427
0x18000341c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003421  mov     [rbp+13F0h+var_1450], rax
0x180003425  jmp     short loc_18000342B
0x180003427  mov     [rbp+13F0h+var_1450], r15
0x18000342b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003432  test    rax, rax
0x180003435  jz      short loc_180003441
0x180003437  lea     rcx, [rsp+14F0h+var_14D0]
0x18000343c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003441  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003448  test    rax, rax
0x18000344b  jz      short loc_180003461
0x18000344d  mov     r8d, 400h
0x180003453  lea     rdx, [rbp+13F0h+var_1430]
0x180003457  lea     rcx, [rsp+14F0h+var_14D0]
0x18000345c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003461  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003468  test    rax, rax
0x18000346b  jz      short loc_180003477
0x18000346d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003477  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000347e  test    rax, rax
0x180003481  jz      short loc_180003494
0x180003483  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003488  jnz     short loc_180003494
0x18000348a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000348f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003494  cmp     [rsp+14F0h+var_14C8], r15d
0x180003499  jge     loc_18000359B
0x18000349f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800034a6  jnz     short loc_1800034C7
0x1800034a8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800034af  test    rax, rax
0x1800034b2  jz      short loc_1800034BD
0x1800034b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b9  test    al, al
0x1800034bb  jmp     short loc_1800034C5
0x1800034bd  call    cs:__imp_IsDebuggerPresent
0x1800034c3  test    eax, eax
0x1800034c5  jz      short loc_1800034CE
0x1800034c7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800034cc  jz      short loc_1800034F4
0x1800034ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034d5  test    rax, rax
0x1800034d8  jz      short loc_18000354D
0x1800034da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800034e1  jnz     short loc_18000354D
0x1800034e3  xor     r8d, r8d
0x1800034e6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034eb  xor     edx, edx
0x1800034ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f2  jmp     short loc_18000354D
0x1800034f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034fb  mov     ebx, 800h
0x180003500  test    rax, rax
0x180003503  jz      short loc_180003522
0x180003505  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000350c  jnz     short loc_180003522
0x18000350e  mov     r8d, ebx
0x180003511  lea     rdx, [rbp+13F0h+OutputString]
0x180003518  lea     rcx, [rsp+14F0h+var_14D0]
0x18000351d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003522  cmp     [rbp+13F0h+OutputString], r15w
0x18000352a  jnz     short loc_180003540
0x18000352c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003531  mov     rdx, rbx; unsigned __int16 *
0x180003534  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000353b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003540  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003547  call    cs:__imp_OutputDebugStringW
0x18000354d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003552  jnz     short loc_18000355D
0x180003554  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000355b  jz      short loc_18000356E
0x18000355d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003564  test    rax, rax
0x180003567  jz      short loc_18000356E
0x180003569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000356e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003573  jnz     short loc_1800035A1
0x180003575  mov     rcx, [rbp+13F0h+var_30]
0x18000357c  xor     rcx, rsp; StackCookie
0x18000357f  call    __security_check_cookie
0x180003584  mov     rbx, [rsp+14F0h+arg_10]
0x18000358c  add     rsp, 14D0h
0x180003593  pop     r15
0x180003595  pop     r14
0x180003597  pop     rdi
0x180003598  pop     rsi
0x180003599  pop     rbp
0x18000359a  retn
0x18000359b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800035a1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800035a6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
