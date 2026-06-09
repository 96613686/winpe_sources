# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180025114`
- end: `0x1800253d2`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800253d8`

## callees

- `0x1800091d4`
- `0x180009640`
- `0x18000a328`
- `0x18000a8ec`
- `0x18000ab40`
- `0x180025114`
- `0x18002fda9`
- `0x1800369a0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800251bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800251bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025366`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025366`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800252c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800252c2`

## string_xrefs

- `0x1800251c5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v8; // r14
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v14; // r9
  char v15; // bl
  const struct wil::FailureInfo *v16; // rdx
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  __int64 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  const char *v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  _QWORD v29[4]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  char v35[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2056]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v35[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v9 = wil::details::RecordException((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 0;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v18 = v10;
  LODWORD(v21) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  LODWORD(v23) = GetCurrentThreadId();
  v26 = "C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h";
  v27 = 7328;
  v28 = v9;
  v24 = 0;
  v25 = 0;
  v33 = a6;
  v34 = a1;
  memset(v29, 0, sizeof(v29));
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v35, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && !v8 && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (IsDebuggerPresent = ::IsDebuggerPresent())
      : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
        !(_DWORD)IsDebuggerPresent)
    || (v15 = 1, (v18 & 2) != 0) )
  {
    v15 = 0;
  }
  if ( v8 || v15 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v14);
    if ( v15 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v12);
  if ( v8 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v17, OutputString);
  wil::ThrowResultException((wil *)&v17, v12);
  wil::details::WilFailFast((wil::details *)&v17, v16);
}

```

## disassembly

```asm
0x180025114  mov     rax, rsp
0x180025117  mov     [rax+10h], rbx
0x18002511b  mov     [rax+18h], rsi
0x18002511f  mov     [rax+20h], rdi
0x180025123  push    rbp
0x180025124  push    r14
0x180025126  push    r15
0x180025128  lea     rbp, [rax-13D8h]
0x18002512f  mov     eax, 14C0h
0x180025134  call    _alloca_probe
0x180025139  sub     rsp, rax
0x18002513c  mov     rsi, rcx
0x18002513f  mov     rdi, [rbp+13D0h+arg_28]
0x180025146  xor     r15d, r15d
0x180025149  cmp     cs:g_pfnThrowPlatformException, r15
0x180025150  setnz   r14b
0x180025154  xor     edx, edx; Val
0x180025156  mov     r8d, 98h; Size
0x18002515c  lea     rcx, [rsp+14D0h+var_14B0]; void *
0x180025161  call    memset_0
0x180025166  nop
0x180025167  mov     [rbp+13D0h+OutputString], r15w
0x18002516f  mov     [rbp+13D0h+var_1410], r15b
0x180025173  mov     rdx, qword ptr [rbp+13D0h+arg_30]; int
0x18002517a  mov     ecx, [rdx]; this
0x18002517c  mov     [rsp+14D0h+var_14A8], ecx
0x180025180  mov     eax, [rdx+4]
0x180025183  mov     [rsp+14D0h+var_14A4], eax
0x180025187  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002518c  mov     ebx, eax
0x18002518e  mov     dword ptr [rsp+14D0h+var_14B0], r15d
0x180025193  mov     ecx, r15d
0x180025196  lea     eax, [r15+8]
0x18002519a  cmp     dword ptr [rdx+8], 1
0x18002519e  cmovz   ecx, eax
0x1800251a1  mov     dword ptr [rsp+14D0h+var_14B0+4], ecx
0x1800251a5  lea     ecx, [rax-7]
0x1800251a8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800251b0  inc     ecx
0x1800251b2  mov     dword ptr [rsp+14D0h+var_14A0], ecx
0x1800251b6  mov     [rsp+14D0h+var_1498], r15
0x1800251bb  call    cs:__imp_GetCurrentThreadId
0x1800251c1  mov     dword ptr [rsp+14D0h+var_1490], eax
0x1800251c5  lea     rax, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800251cc  mov     qword ptr [rsp+14D0h+var_1478], rax
0x1800251d1  mov     dword ptr [rsp+14D0h+var_1470], 1CA0h
0x1800251d9  mov     dword ptr [rsp+14D0h+var_1470+4], ebx
0x1800251dd  mov     [rsp+14D0h+var_1488], r15
0x1800251e2  mov     [rsp+14D0h+var_1480], r15
0x1800251e7  mov     [rbp+13D0h+var_1428], rdi
0x1800251eb  mov     [rbp+13D0h+var_1420], rsi
0x1800251ef  mov     qword ptr [rsp+14D0h+var_1468], r15
0x1800251f4  xorps   xmm0, xmm0
0x1800251f7  xor     eax, eax
0x1800251f9  movups  [rbp+13D0h+var_1448], xmm0
0x1800251fd  mov     [rbp+13D0h+var_1438], rax
0x180025201  xorps   xmm1, xmm1
0x180025204  movups  xmmword ptr [rsp+14D0h+var_1468+8], xmm1
0x180025209  mov     [rbp+13D0h+var_1450], rax
0x18002520d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025214  test    rax, rax
0x180025217  jz      short loc_180025224
0x180025219  call    _guard_dispatch_icall
0x18002521e  mov     [rbp+13D0h+var_1430], rax
0x180025222  jmp     short loc_180025228
0x180025224  mov     [rbp+13D0h+var_1430], r15
0x180025228  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002522f  test    rax, rax
0x180025232  jz      short loc_18002523E
0x180025234  lea     rcx, [rsp+14D0h+var_14B0]
0x180025239  call    _guard_dispatch_icall
0x18002523e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025245  test    rax, rax
0x180025248  jz      short loc_18002525E
0x18002524a  mov     r8d, 400h
0x180025250  lea     rdx, [rbp+13D0h+var_1410]
0x180025254  lea     rcx, [rsp+14D0h+var_14B0]
0x180025259  call    _guard_dispatch_icall
0x18002525e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025265  test    rax, rax
0x180025268  jz      short loc_180025274
0x18002526a  lea     rcx, [rsp+14D0h+var_14B0]
0x18002526f  call    _guard_dispatch_icall
0x180025274  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002527b  test    rax, rax
0x18002527e  jz      short loc_180025296
0x180025280  test    r14b, r14b
0x180025283  jnz     short loc_180025296
0x180025285  test    byte ptr [rsp+14D0h+var_14B0+4], 2
0x18002528a  jnz     short loc_180025296
0x18002528c  lea     rcx, [rsp+14D0h+var_14B0]
0x180025291  call    _guard_dispatch_icall
0x180025296  cmp     [rsp+14D0h+var_14A8], r15d
0x18002529b  jl      short loc_1800252A3
0x18002529d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800252a3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800252aa  jnz     short loc_1800252D4
0x1800252ac  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800252b3  test    rax, rax
0x1800252b6  jz      short loc_1800252C2
0x1800252b8  call    _guard_dispatch_icall
0x1800252bd  movzx   ecx, al
0x1800252c0  jmp     short loc_1800252D0
0x1800252c2  call    cs:__imp_IsDebuggerPresent
0x1800252c8  mov     ecx, r15d
0x1800252cb  test    eax, eax
0x1800252cd  setnz   cl
0x1800252d0  test    ecx, ecx
0x1800252d2  jz      short loc_1800252DD
0x1800252d4  test    byte ptr [rsp+14D0h+var_14B0+4], 2
0x1800252d9  mov     bl, 1
0x1800252db  jz      short loc_1800252E0
0x1800252dd  mov     bl, r15b
0x1800252e0  test    r14b, r14b
0x1800252e3  jnz     short loc_18002530F
0x1800252e5  test    bl, bl
0x1800252e7  jnz     short loc_18002530F
0x1800252e9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800252f0  test    rax, rax
0x1800252f3  jz      short loc_18002536C
0x1800252f5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800252fc  jnz     short loc_18002536C
0x1800252fe  xor     r8d, r8d
0x180025301  xor     edx, edx
0x180025303  lea     rcx, [rsp+14D0h+var_14B0]
0x180025308  call    _guard_dispatch_icall
0x18002530d  jmp     short loc_18002536C
0x18002530f  mov     edi, 800h
0x180025314  mov     rax, cs:g_pfnResultLoggingCallback
0x18002531b  test    rax, rax
0x18002531e  jz      short loc_18002533D
0x180025320  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180025327  jnz     short loc_18002533D
0x180025329  mov     r8d, edi
0x18002532c  lea     rdx, [rbp+13D0h+OutputString]
0x180025333  lea     rcx, [rsp+14D0h+var_14B0]
0x180025338  call    _guard_dispatch_icall
0x18002533d  cmp     [rbp+13D0h+OutputString], r15w
0x180025345  jnz     short loc_18002535B
0x180025347  lea     r8, [rsp+14D0h+var_14B0]; unsigned __int64
0x18002534c  mov     rdx, rdi; wchar_t *
0x18002534f  lea     rcx, [rbp+13D0h+OutputString]; this
0x180025356  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18002535b  test    bl, bl
0x18002535d  jz      short loc_18002536C
0x18002535f  lea     rcx, [rbp+13D0h+OutputString]; lpOutputString
0x180025366  call    cs:__imp_OutputDebugStringW
0x18002536c  test    byte ptr [rsp+14D0h+var_14B0+4], 4
0x180025371  jnz     short loc_18002537C
0x180025373  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18002537a  jz      short loc_18002538E
0x18002537c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025383  test    rax, rax
0x180025386  jz      short loc_18002538E
0x180025388  call    _guard_dispatch_icall
0x18002538d  nop
0x18002538e  test    byte ptr [rsp+14D0h+var_14B0+4], 1
0x180025393  jz      short loc_1800253A0
0x180025395  lea     rcx, [rsp+14D0h+var_14B0]; this
0x18002539a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800253a0  test    r14b, r14b
0x1800253a3  jz      short loc_1800253BD
0x1800253a5  lea     rdx, [rbp+13D0h+OutputString]
0x1800253ac  lea     rcx, [rsp+14D0h+var_14B0]
0x1800253b1  mov     rax, cs:g_pfnThrowPlatformException
0x1800253b8  call    _guard_dispatch_icall
0x1800253bd  lea     rcx, [rsp+14D0h+var_14B0]; this
0x1800253c2  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800253c7  lea     rcx, [rsp+14D0h+var_14B0]; this
0x1800253cc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
