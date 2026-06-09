# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005840`
- end: `0x180005ae9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005334`

## callees

- `0x180002ad0`
- `0x180003528`
- `0x180005840`
- `0x1800075a4`
- `0x180009020`
- `0x18000a73c`
- `0x18000a970`
- `0x18009c3c0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a7c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a7c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059ec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180005840  mov     [rsp-8+arg_10], rbx
0x180005845  push    rbp
0x180005846  push    rsi
0x180005847  push    rdi
0x180005848  push    r14
0x18000584a  push    r15
0x18000584c  lea     rbp, [rsp-13D0h]
0x180005854  mov     eax, 14D0h
0x180005859  call    _alloca_probe
0x18000585e  sub     rsp, rax
0x180005861  mov     rax, cs:__security_cookie
0x180005868  xor     rax, rsp
0x18000586b  mov     [rbp+13F0h+var_30], rax
0x180005872  mov     esi, edx
0x180005874  mov     r14, rcx
0x180005877  mov     rdi, [rbp+13F0h+arg_28]
0x18000587e  xor     edx, edx; Val
0x180005880  mov     r8d, 98h; Size
0x180005886  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000588b  call    memset_0
0x180005890  nop
0x180005891  xor     r15d, r15d
0x180005894  mov     [rbp+13F0h+OutputString], r15w
0x18000589c  mov     [rbp+13F0h+var_1430], r15b
0x1800058a0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800058a7  mov     ecx, [rdx]; this
0x1800058a9  mov     [rsp+14F0h+var_14C8], ecx
0x1800058ad  mov     eax, [rdx+4]
0x1800058b0  mov     [rsp+14F0h+var_14C4], eax
0x1800058b4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800058b9  mov     ebx, eax
0x1800058bb  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800058c3  mov     ecx, r15d
0x1800058c6  lea     eax, [r15+8]
0x1800058ca  cmp     dword ptr [rdx+8], 1
0x1800058ce  cmovz   ecx, eax
0x1800058d1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800058d5  lea     ecx, [rax-7]
0x1800058d8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800058e0  inc     ecx
0x1800058e2  mov     [rsp+14F0h+var_14C0], ecx
0x1800058e6  mov     [rsp+14F0h+var_14B8], r15
0x1800058eb  call    cs:__imp_GetCurrentThreadId
0x1800058f2  nop     dword ptr [rax+rax+00h]
0x1800058f7  mov     [rsp+14F0h+var_14B0], eax
0x1800058fb  lea     rax, aWil; "wil"
0x180005902  mov     [rsp+14F0h+var_1498], rax
0x180005907  mov     [rsp+14F0h+var_1490], esi
0x18000590b  mov     [rsp+14F0h+var_148C], ebx
0x18000590f  mov     [rsp+14F0h+var_14A8], r15
0x180005914  mov     [rsp+14F0h+var_14A0], r15
0x180005919  mov     [rbp+13F0h+var_1448], rdi
0x18000591d  mov     [rbp+13F0h+var_1440], r14
0x180005921  mov     [rsp+14F0h+var_1488], r15
0x180005926  xorps   xmm0, xmm0
0x180005929  xor     eax, eax
0x18000592b  movups  [rbp+13F0h+var_1468], xmm0
0x18000592f  mov     [rbp+13F0h+var_1458], rax
0x180005933  xorps   xmm1, xmm1
0x180005936  movups  [rsp+14F0h+var_1480], xmm1
0x18000593b  mov     [rbp+13F0h+var_1470], rax
0x18000593f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005946  test    rax, rax
0x180005949  jz      short loc_180005956
0x18000594b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005950  mov     [rbp+13F0h+var_1450], rax
0x180005954  jmp     short loc_18000595A
0x180005956  mov     [rbp+13F0h+var_1450], r15
0x18000595a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005961  test    rax, rax
0x180005964  jz      short loc_180005970
0x180005966  lea     rcx, [rsp+14F0h+var_14D0]
0x18000596b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005970  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005977  test    rax, rax
0x18000597a  jz      short loc_180005990
0x18000597c  mov     r8d, 400h
0x180005982  lea     rdx, [rbp+13F0h+var_1430]
0x180005986  lea     rcx, [rsp+14F0h+var_14D0]
0x18000598b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005990  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005997  test    rax, rax
0x18000599a  jz      short loc_1800059A6
0x18000599c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800059a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059a6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800059ad  test    rax, rax
0x1800059b0  jz      short loc_1800059C3
0x1800059b2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800059b7  jnz     short loc_1800059C3
0x1800059b9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800059be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c3  cmp     [rsp+14F0h+var_14C8], r15d
0x1800059c8  jge     loc_180005AE3
0x1800059ce  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800059d5  jnz     short loc_1800059FC
0x1800059d7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800059de  test    rax, rax
0x1800059e1  jz      short loc_1800059EC
0x1800059e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e8  test    al, al
0x1800059ea  jmp     short loc_1800059FA
0x1800059ec  call    cs:__imp_IsDebuggerPresent
0x1800059f3  nop     dword ptr [rax+rax+00h]
0x1800059f8  test    eax, eax
0x1800059fa  jz      short loc_180005A03
0x1800059fc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005a01  jz      short loc_180005A29
0x180005a03  mov     rax, cs:g_pfnResultLoggingCallback
0x180005a0a  test    rax, rax
0x180005a0d  jz      short loc_180005A88
0x180005a0f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005a16  jnz     short loc_180005A88
0x180005a18  xor     r8d, r8d
0x180005a1b  xor     edx, edx
0x180005a1d  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a27  jmp     short loc_180005A88
0x180005a29  mov     ebx, 800h
0x180005a2e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005a35  test    rax, rax
0x180005a38  jz      short loc_180005A57
0x180005a3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005a41  jnz     short loc_180005A57
0x180005a43  mov     r8d, ebx
0x180005a46  lea     rdx, [rbp+13F0h+OutputString]
0x180005a4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a57  cmp     [rbp+13F0h+OutputString], r15w
0x180005a5f  jnz     short loc_180005A75
0x180005a61  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005a66  mov     rdx, rbx; wchar_t *
0x180005a69  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x180005a70  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005a75  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005a7c  call    cs:__imp_OutputDebugStringW
0x180005a83  nop     dword ptr [rax+rax+00h]
0x180005a88  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005a8d  jnz     short loc_180005A98
0x180005a8f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005a96  jz      short loc_180005AAA
0x180005a98  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005a9f  test    rax, rax
0x180005aa2  jz      short loc_180005AAA
0x180005aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa9  nop
0x180005aaa  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005aaf  jnz     short loc_180005AD8
0x180005ab1  mov     rcx, [rbp+13F0h+var_30]
0x180005ab8  xor     rcx, rsp; StackCookie
0x180005abb  call    __security_check_cookie
0x180005ac0  mov     rbx, [rsp+14F0h+arg_10]
0x180005ac8  add     rsp, 14D0h
0x180005acf  pop     r15
0x180005ad1  pop     r14
0x180005ad3  pop     rdi
0x180005ad4  pop     rsi
0x180005ad5  pop     rbp
0x180005ad6  retn
0x180005ad8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005add  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005ae3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
