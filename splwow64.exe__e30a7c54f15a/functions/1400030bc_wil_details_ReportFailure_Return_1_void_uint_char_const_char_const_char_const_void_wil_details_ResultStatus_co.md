# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400030bc`
- end: `0x140003350`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002b9c`

## callees

- `0x140001ee0`
- `0x1400028b8`
- `0x1400030bc`
- `0x140004374`
- `0x140005560`
- `0x140006280`
- `0x14000635c`
- `0x1400154e0`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003166`
- `KERNEL32!GetCurrentThreadId` at `0x140003166`
- `KERNEL32!OutputDebugStringW` at `0x1400032eb`
- `KERNEL32!OutputDebugStringW` at `0x1400032eb`
- `KERNEL32!IsDebuggerPresent` at `0x140003261`
- `KERNEL32!IsDebuggerPresent` at `0x140003261`

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
0x1400030bc  mov     [rsp-8+arg_10], rbx
0x1400030c1  push    rbp
0x1400030c2  push    rsi
0x1400030c3  push    rdi
0x1400030c4  push    r14
0x1400030c6  push    r15
0x1400030c8  lea     rbp, [rsp-13D0h]
0x1400030d0  mov     eax, 14D0h
0x1400030d5  call    _alloca_probe
0x1400030da  sub     rsp, rax
0x1400030dd  mov     rax, cs:__security_cookie
0x1400030e4  xor     rax, rsp
0x1400030e7  mov     [rbp+13F0h+var_30], rax
0x1400030ee  mov     rdi, [rbp+13F0h+arg_28]
0x1400030f5  mov     esi, edx
0x1400030f7  mov     r14, rcx
0x1400030fa  xor     edx, edx; Val
0x1400030fc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003101  mov     r8d, 98h; Size
0x140003107  call    memset_0
0x14000310c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140003113  xor     r15d, r15d
0x140003116  mov     [rbp+13F0h+OutputString], r15w
0x14000311e  mov     [rbp+13F0h+var_1430], r15b
0x140003122  mov     ecx, [rdx]; this
0x140003124  mov     eax, [rdx+4]
0x140003127  mov     [rsp+14F0h+var_14C8], ecx
0x14000312b  mov     [rsp+14F0h+var_14C4], eax
0x14000312f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003134  cmp     dword ptr [rdx+8], 1
0x140003138  mov     ebx, eax
0x14000313a  lea     eax, [r15+8]
0x14000313e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140003146  mov     ecx, r15d
0x140003149  cmovz   ecx, eax
0x14000314c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003150  lea     ecx, [rax-7]
0x140003153  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000315b  inc     ecx
0x14000315d  mov     [rsp+14F0h+var_14B8], r15
0x140003162  mov     [rsp+14F0h+var_14C0], ecx
0x140003166  call    cs:__imp_GetCurrentThreadId
0x14000316c  xorps   xmm0, xmm0
0x14000316f  mov     [rsp+14F0h+var_1490], esi
0x140003173  mov     [rsp+14F0h+var_14B0], eax
0x140003177  xorps   xmm1, xmm1
0x14000317a  lea     rax, aWil; "wil"
0x140003181  mov     [rsp+14F0h+var_148C], ebx
0x140003185  mov     [rsp+14F0h+var_1498], rax
0x14000318a  xor     eax, eax
0x14000318c  mov     [rbp+13F0h+var_1458], rax
0x140003190  mov     [rbp+13F0h+var_1470], rax
0x140003194  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000319b  mov     [rsp+14F0h+var_14A8], r15
0x1400031a0  mov     [rsp+14F0h+var_14A0], r15
0x1400031a5  mov     [rbp+13F0h+var_1448], rdi
0x1400031a9  mov     [rbp+13F0h+var_1440], r14
0x1400031ad  mov     [rsp+14F0h+var_1488], r15
0x1400031b2  movups  [rbp+13F0h+var_1468], xmm0
0x1400031b6  movups  [rsp+14F0h+var_1480], xmm1
0x1400031bb  test    rax, rax
0x1400031be  jz      short loc_1400031CB
0x1400031c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031c5  mov     [rbp+13F0h+var_1450], rax
0x1400031c9  jmp     short loc_1400031CF
0x1400031cb  mov     [rbp+13F0h+var_1450], r15
0x1400031cf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400031d6  test    rax, rax
0x1400031d9  jz      short loc_1400031E5
0x1400031db  lea     rcx, [rsp+14F0h+var_14D0]
0x1400031e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031e5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400031ec  test    rax, rax
0x1400031ef  jz      short loc_140003205
0x1400031f1  mov     r8d, 400h
0x1400031f7  lea     rdx, [rbp+13F0h+var_1430]
0x1400031fb  lea     rcx, [rsp+14F0h+var_14D0]
0x140003200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003205  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000320c  test    rax, rax
0x14000320f  jz      short loc_14000321B
0x140003211  lea     rcx, [rsp+14F0h+var_14D0]
0x140003216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000321b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003222  test    rax, rax
0x140003225  jz      short loc_140003238
0x140003227  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000322c  jnz     short loc_140003238
0x14000322e  lea     rcx, [rsp+14F0h+var_14D0]
0x140003233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003238  cmp     [rsp+14F0h+var_14C8], r15d
0x14000323d  jge     loc_14000333F
0x140003243  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000324a  jnz     short loc_14000326B
0x14000324c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003253  test    rax, rax
0x140003256  jz      short loc_140003261
0x140003258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000325d  test    al, al
0x14000325f  jmp     short loc_140003269
0x140003261  call    cs:__imp_IsDebuggerPresent
0x140003267  test    eax, eax
0x140003269  jz      short loc_140003272
0x14000326b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003270  jz      short loc_140003298
0x140003272  mov     rax, cs:g_pfnResultLoggingCallback
0x140003279  test    rax, rax
0x14000327c  jz      short loc_1400032F1
0x14000327e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003285  jnz     short loc_1400032F1
0x140003287  xor     r8d, r8d
0x14000328a  lea     rcx, [rsp+14F0h+var_14D0]
0x14000328f  xor     edx, edx
0x140003291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003296  jmp     short loc_1400032F1
0x140003298  mov     rax, cs:g_pfnResultLoggingCallback
0x14000329f  mov     ebx, 800h
0x1400032a4  test    rax, rax
0x1400032a7  jz      short loc_1400032C6
0x1400032a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400032b0  jnz     short loc_1400032C6
0x1400032b2  mov     r8d, ebx
0x1400032b5  lea     rdx, [rbp+13F0h+OutputString]
0x1400032bc  lea     rcx, [rsp+14F0h+var_14D0]
0x1400032c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032c6  cmp     [rbp+13F0h+OutputString], r15w
0x1400032ce  jnz     short loc_1400032E4
0x1400032d0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400032d5  mov     rdx, rbx; unsigned __int16 *
0x1400032d8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400032df  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400032e4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400032eb  call    cs:__imp_OutputDebugStringW
0x1400032f1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400032f6  jnz     short loc_140003301
0x1400032f8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400032ff  jz      short loc_140003312
0x140003301  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003308  test    rax, rax
0x14000330b  jz      short loc_140003312
0x14000330d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003312  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140003317  jnz     short loc_140003345
0x140003319  mov     rcx, [rbp+13F0h+var_30]
0x140003320  xor     rcx, rsp; StackCookie
0x140003323  call    __security_check_cookie
0x140003328  mov     rbx, [rsp+14F0h+arg_10]
0x140003330  add     rsp, 14D0h
0x140003337  pop     r15
0x140003339  pop     r14
0x14000333b  pop     rdi
0x14000333c  pop     rsi
0x14000333d  pop     rbp
0x14000333e  retn
0x14000333f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003345  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000334a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
