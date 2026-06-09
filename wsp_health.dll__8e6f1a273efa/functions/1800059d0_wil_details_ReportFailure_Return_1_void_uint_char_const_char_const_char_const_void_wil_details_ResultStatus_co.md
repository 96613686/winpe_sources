# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800059d0`
- end: `0x180005c79`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800054c4`

## callees

- `0x180002b50`
- `0x1800035b4`
- `0x1800059d0`
- `0x180007494`
- `0x180008f10`
- `0x18000a62c`
- `0x18000a7e8`
- `0x1800865f0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a7b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b7c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b7c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005c0c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005c0c`

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
0x1800059d0  mov     [rsp-8+arg_10], rbx
0x1800059d5  push    rbp
0x1800059d6  push    rsi
0x1800059d7  push    rdi
0x1800059d8  push    r14
0x1800059da  push    r15
0x1800059dc  lea     rbp, [rsp-13D0h]
0x1800059e4  mov     eax, 14D0h
0x1800059e9  call    _alloca_probe
0x1800059ee  sub     rsp, rax
0x1800059f1  mov     rax, cs:__security_cookie
0x1800059f8  xor     rax, rsp
0x1800059fb  mov     [rbp+13F0h+var_30], rax
0x180005a02  mov     esi, edx
0x180005a04  mov     r14, rcx
0x180005a07  mov     rdi, [rbp+13F0h+arg_28]
0x180005a0e  xor     edx, edx; Val
0x180005a10  mov     r8d, 98h; Size
0x180005a16  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005a1b  call    memset_0
0x180005a20  nop
0x180005a21  xor     r15d, r15d
0x180005a24  mov     [rbp+13F0h+OutputString], r15w
0x180005a2c  mov     [rbp+13F0h+var_1430], r15b
0x180005a30  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180005a37  mov     ecx, [rdx]; this
0x180005a39  mov     [rsp+14F0h+var_14C8], ecx
0x180005a3d  mov     eax, [rdx+4]
0x180005a40  mov     [rsp+14F0h+var_14C4], eax
0x180005a44  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005a49  mov     ebx, eax
0x180005a4b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180005a53  mov     ecx, r15d
0x180005a56  lea     eax, [r15+8]
0x180005a5a  cmp     dword ptr [rdx+8], 1
0x180005a5e  cmovz   ecx, eax
0x180005a61  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005a65  lea     ecx, [rax-7]
0x180005a68  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005a70  inc     ecx
0x180005a72  mov     [rsp+14F0h+var_14C0], ecx
0x180005a76  mov     [rsp+14F0h+var_14B8], r15
0x180005a7b  call    cs:__imp_GetCurrentThreadId
0x180005a82  nop     dword ptr [rax+rax+00h]
0x180005a87  mov     [rsp+14F0h+var_14B0], eax
0x180005a8b  lea     rax, aWil; "wil"
0x180005a92  mov     [rsp+14F0h+var_1498], rax
0x180005a97  mov     [rsp+14F0h+var_1490], esi
0x180005a9b  mov     [rsp+14F0h+var_148C], ebx
0x180005a9f  mov     [rsp+14F0h+var_14A8], r15
0x180005aa4  mov     [rsp+14F0h+var_14A0], r15
0x180005aa9  mov     [rbp+13F0h+var_1448], rdi
0x180005aad  mov     [rbp+13F0h+var_1440], r14
0x180005ab1  mov     [rsp+14F0h+var_1488], r15
0x180005ab6  xorps   xmm0, xmm0
0x180005ab9  xor     eax, eax
0x180005abb  movups  [rbp+13F0h+var_1468], xmm0
0x180005abf  mov     [rbp+13F0h+var_1458], rax
0x180005ac3  xorps   xmm1, xmm1
0x180005ac6  movups  [rsp+14F0h+var_1480], xmm1
0x180005acb  mov     [rbp+13F0h+var_1470], rax
0x180005acf  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005ad6  test    rax, rax
0x180005ad9  jz      short loc_180005AE6
0x180005adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae0  mov     [rbp+13F0h+var_1450], rax
0x180005ae4  jmp     short loc_180005AEA
0x180005ae6  mov     [rbp+13F0h+var_1450], r15
0x180005aea  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005af1  test    rax, rax
0x180005af4  jz      short loc_180005B00
0x180005af6  lea     rcx, [rsp+14F0h+var_14D0]
0x180005afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b00  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005b07  test    rax, rax
0x180005b0a  jz      short loc_180005B20
0x180005b0c  mov     r8d, 400h
0x180005b12  lea     rdx, [rbp+13F0h+var_1430]
0x180005b16  lea     rcx, [rsp+14F0h+var_14D0]
0x180005b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b20  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b27  test    rax, rax
0x180005b2a  jz      short loc_180005B36
0x180005b2c  lea     rcx, [rsp+14F0h+var_14D0]
0x180005b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b36  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b3d  test    rax, rax
0x180005b40  jz      short loc_180005B53
0x180005b42  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005b47  jnz     short loc_180005B53
0x180005b49  lea     rcx, [rsp+14F0h+var_14D0]
0x180005b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b53  cmp     [rsp+14F0h+var_14C8], r15d
0x180005b58  jge     loc_180005C73
0x180005b5e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180005b65  jnz     short loc_180005B8C
0x180005b67  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005b6e  test    rax, rax
0x180005b71  jz      short loc_180005B7C
0x180005b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b78  test    al, al
0x180005b7a  jmp     short loc_180005B8A
0x180005b7c  call    cs:__imp_IsDebuggerPresent
0x180005b83  nop     dword ptr [rax+rax+00h]
0x180005b88  test    eax, eax
0x180005b8a  jz      short loc_180005B93
0x180005b8c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005b91  jz      short loc_180005BB9
0x180005b93  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b9a  test    rax, rax
0x180005b9d  jz      short loc_180005C18
0x180005b9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005ba6  jnz     short loc_180005C18
0x180005ba8  xor     r8d, r8d
0x180005bab  xor     edx, edx
0x180005bad  lea     rcx, [rsp+14F0h+var_14D0]
0x180005bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb7  jmp     short loc_180005C18
0x180005bb9  mov     ebx, 800h
0x180005bbe  mov     rax, cs:g_pfnResultLoggingCallback
0x180005bc5  test    rax, rax
0x180005bc8  jz      short loc_180005BE7
0x180005bca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005bd1  jnz     short loc_180005BE7
0x180005bd3  mov     r8d, ebx
0x180005bd6  lea     rdx, [rbp+13F0h+OutputString]
0x180005bdd  lea     rcx, [rsp+14F0h+var_14D0]
0x180005be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be7  cmp     [rbp+13F0h+OutputString], r15w
0x180005bef  jnz     short loc_180005C05
0x180005bf1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005bf6  mov     rdx, rbx; wchar_t *
0x180005bf9  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x180005c00  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005c05  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005c0c  call    cs:__imp_OutputDebugStringW
0x180005c13  nop     dword ptr [rax+rax+00h]
0x180005c18  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005c1d  jnz     short loc_180005C28
0x180005c1f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005c26  jz      short loc_180005C3A
0x180005c28  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005c2f  test    rax, rax
0x180005c32  jz      short loc_180005C3A
0x180005c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c39  nop
0x180005c3a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005c3f  jnz     short loc_180005C68
0x180005c41  mov     rcx, [rbp+13F0h+var_30]
0x180005c48  xor     rcx, rsp; StackCookie
0x180005c4b  call    __security_check_cookie
0x180005c50  mov     rbx, [rsp+14F0h+arg_10]
0x180005c58  add     rsp, 14D0h
0x180005c5f  pop     r15
0x180005c61  pop     r14
0x180005c63  pop     rdi
0x180005c64  pop     rsi
0x180005c65  pop     rbp
0x180005c66  retn
0x180005c68  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005c6d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005c73  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
