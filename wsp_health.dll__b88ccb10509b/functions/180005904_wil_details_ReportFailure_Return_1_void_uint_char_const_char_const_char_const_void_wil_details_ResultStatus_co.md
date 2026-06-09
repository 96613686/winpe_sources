# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005904`
- end: `0x180005b9a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000540c`

## callees

- `0x180002ae0`
- `0x180003514`
- `0x180005904`
- `0x180007224`
- `0x180008bb0`
- `0x18000a2f0`
- `0x18000a4a8`
- `0x1800841e0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059af`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005aaa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005aaa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005b34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005b34`

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
0x180005904  mov     [rsp-8+arg_10], rbx
0x180005909  push    rbp
0x18000590a  push    rsi
0x18000590b  push    rdi
0x18000590c  push    r14
0x18000590e  push    r15
0x180005910  lea     rbp, [rsp-13D0h]
0x180005918  mov     eax, 14D0h
0x18000591d  call    _alloca_probe
0x180005922  sub     rsp, rax
0x180005925  mov     rax, cs:__security_cookie
0x18000592c  xor     rax, rsp
0x18000592f  mov     [rbp+13F0h+var_30], rax
0x180005936  mov     esi, edx
0x180005938  mov     r14, rcx
0x18000593b  mov     rdi, [rbp+13F0h+arg_28]
0x180005942  xor     edx, edx; Val
0x180005944  mov     r8d, 98h; Size
0x18000594a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000594f  call    memset_0
0x180005954  nop
0x180005955  xor     r15d, r15d
0x180005958  mov     [rbp+13F0h+OutputString], r15w
0x180005960  mov     [rbp+13F0h+var_1430], r15b
0x180005964  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000596b  mov     ecx, [rdx]; this
0x18000596d  mov     [rsp+14F0h+var_14C8], ecx
0x180005971  mov     eax, [rdx+4]
0x180005974  mov     [rsp+14F0h+var_14C4], eax
0x180005978  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000597d  mov     ebx, eax
0x18000597f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180005987  mov     ecx, r15d
0x18000598a  lea     eax, [r15+8]
0x18000598e  cmp     dword ptr [rdx+8], 1
0x180005992  cmovz   ecx, eax
0x180005995  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005999  lea     ecx, [rax-7]
0x18000599c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800059a4  inc     ecx
0x1800059a6  mov     [rsp+14F0h+var_14C0], ecx
0x1800059aa  mov     [rsp+14F0h+var_14B8], r15
0x1800059af  call    cs:__imp_GetCurrentThreadId
0x1800059b5  mov     [rsp+14F0h+var_14B0], eax
0x1800059b9  lea     rax, aWil; "wil"
0x1800059c0  mov     [rsp+14F0h+var_1498], rax
0x1800059c5  mov     [rsp+14F0h+var_1490], esi
0x1800059c9  mov     [rsp+14F0h+var_148C], ebx
0x1800059cd  mov     [rsp+14F0h+var_14A8], r15
0x1800059d2  mov     [rsp+14F0h+var_14A0], r15
0x1800059d7  mov     [rbp+13F0h+var_1448], rdi
0x1800059db  mov     [rbp+13F0h+var_1440], r14
0x1800059df  mov     [rsp+14F0h+var_1488], r15
0x1800059e4  xorps   xmm0, xmm0
0x1800059e7  xor     eax, eax
0x1800059e9  movups  [rbp+13F0h+var_1468], xmm0
0x1800059ed  mov     [rbp+13F0h+var_1458], rax
0x1800059f1  xorps   xmm1, xmm1
0x1800059f4  movups  [rsp+14F0h+var_1480], xmm1
0x1800059f9  mov     [rbp+13F0h+var_1470], rax
0x1800059fd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005a04  test    rax, rax
0x180005a07  jz      short loc_180005A14
0x180005a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a0e  mov     [rbp+13F0h+var_1450], rax
0x180005a12  jmp     short loc_180005A18
0x180005a14  mov     [rbp+13F0h+var_1450], r15
0x180005a18  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005a1f  test    rax, rax
0x180005a22  jz      short loc_180005A2E
0x180005a24  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a2e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005a35  test    rax, rax
0x180005a38  jz      short loc_180005A4E
0x180005a3a  mov     r8d, 400h
0x180005a40  lea     rdx, [rbp+13F0h+var_1430]
0x180005a44  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a4e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005a55  test    rax, rax
0x180005a58  jz      short loc_180005A64
0x180005a5a  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a64  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005a6b  test    rax, rax
0x180005a6e  jz      short loc_180005A81
0x180005a70  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005a75  jnz     short loc_180005A81
0x180005a77  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a81  cmp     [rsp+14F0h+var_14C8], r15d
0x180005a86  jge     loc_180005B94
0x180005a8c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180005a93  jnz     short loc_180005AB4
0x180005a95  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005a9c  test    rax, rax
0x180005a9f  jz      short loc_180005AAA
0x180005aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa6  test    al, al
0x180005aa8  jmp     short loc_180005AB2
0x180005aaa  call    cs:__imp_IsDebuggerPresent
0x180005ab0  test    eax, eax
0x180005ab2  jz      short loc_180005ABB
0x180005ab4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005ab9  jz      short loc_180005AE1
0x180005abb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ac2  test    rax, rax
0x180005ac5  jz      short loc_180005B3A
0x180005ac7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005ace  jnz     short loc_180005B3A
0x180005ad0  xor     r8d, r8d
0x180005ad3  xor     edx, edx
0x180005ad5  lea     rcx, [rsp+14F0h+var_14D0]
0x180005ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005adf  jmp     short loc_180005B3A
0x180005ae1  mov     ebx, 800h
0x180005ae6  mov     rax, cs:g_pfnResultLoggingCallback
0x180005aed  test    rax, rax
0x180005af0  jz      short loc_180005B0F
0x180005af2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005af9  jnz     short loc_180005B0F
0x180005afb  mov     r8d, ebx
0x180005afe  lea     rdx, [rbp+13F0h+OutputString]
0x180005b05  lea     rcx, [rsp+14F0h+var_14D0]
0x180005b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b0f  cmp     [rbp+13F0h+OutputString], r15w
0x180005b17  jnz     short loc_180005B2D
0x180005b19  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005b1e  mov     rdx, rbx; wchar_t *
0x180005b21  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x180005b28  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005b2d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005b34  call    cs:__imp_OutputDebugStringW
0x180005b3a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005b3f  jnz     short loc_180005B4A
0x180005b41  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005b48  jz      short loc_180005B5C
0x180005b4a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005b51  test    rax, rax
0x180005b54  jz      short loc_180005B5C
0x180005b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b5b  nop
0x180005b5c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005b61  jnz     short loc_180005B89
0x180005b63  mov     rcx, [rbp+13F0h+var_30]
0x180005b6a  xor     rcx, rsp; StackCookie
0x180005b6d  call    __security_check_cookie
0x180005b72  mov     rbx, [rsp+14F0h+arg_10]
0x180005b7a  add     rsp, 14D0h
0x180005b81  pop     r15
0x180005b83  pop     r14
0x180005b85  pop     rdi
0x180005b86  pop     rsi
0x180005b87  pop     rbp
0x180005b88  retn
0x180005b89  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005b8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005b94  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
