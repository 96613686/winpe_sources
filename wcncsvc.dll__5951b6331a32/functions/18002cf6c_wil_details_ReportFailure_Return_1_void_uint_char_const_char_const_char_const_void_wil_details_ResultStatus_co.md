# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18002cf6c`
- end: `0x18002d202`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002ca4c`

## callees

- `0x18002cf6c`
- `0x18002fe84`
- `0x180031818`
- `0x1800340b0`
- `0x18003426c`
- `0x180056df2`
- `0x180056e30`
- `0x180056ef0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d017`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002d19c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002d19c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d112`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d112`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x18002cf6c  mov     [rsp-8+arg_10], rbx
0x18002cf71  push    rbp
0x18002cf72  push    rsi
0x18002cf73  push    rdi
0x18002cf74  push    r14
0x18002cf76  push    r15
0x18002cf78  lea     rbp, [rsp-13D0h]
0x18002cf80  mov     eax, 14D0h
0x18002cf85  call    _alloca_probe
0x18002cf8a  sub     rsp, rax
0x18002cf8d  mov     rax, cs:__security_cookie
0x18002cf94  xor     rax, rsp
0x18002cf97  mov     [rbp+13F0h+var_30], rax
0x18002cf9e  mov     esi, edx
0x18002cfa0  mov     r14, rcx
0x18002cfa3  mov     rdi, [rbp+13F0h+arg_28]
0x18002cfaa  xor     edx, edx; Val
0x18002cfac  mov     r8d, 98h; Size
0x18002cfb2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002cfb7  call    memset_0
0x18002cfbc  nop
0x18002cfbd  xor     r15d, r15d
0x18002cfc0  mov     [rbp+13F0h+OutputString], r15w
0x18002cfc8  mov     [rbp+13F0h+var_1430], r15b
0x18002cfcc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18002cfd3  mov     ecx, [rdx]; this
0x18002cfd5  mov     [rsp+14F0h+var_14C8], ecx
0x18002cfd9  mov     eax, [rdx+4]
0x18002cfdc  mov     [rsp+14F0h+var_14C4], eax
0x18002cfe0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002cfe5  mov     ebx, eax
0x18002cfe7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18002cfef  mov     ecx, r15d
0x18002cff2  lea     eax, [r15+8]
0x18002cff6  cmp     dword ptr [rdx+8], 1
0x18002cffa  cmovz   ecx, eax
0x18002cffd  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002d001  lea     ecx, [rax-7]
0x18002d004  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002d00c  inc     ecx
0x18002d00e  mov     [rsp+14F0h+var_14C0], ecx
0x18002d012  mov     [rsp+14F0h+var_14B8], r15
0x18002d017  call    cs:__imp_GetCurrentThreadId
0x18002d01d  mov     [rsp+14F0h+var_14B0], eax
0x18002d021  lea     rax, aWil; "wil"
0x18002d028  mov     [rsp+14F0h+var_1498], rax
0x18002d02d  mov     [rsp+14F0h+var_1490], esi
0x18002d031  mov     [rsp+14F0h+var_148C], ebx
0x18002d035  mov     [rsp+14F0h+var_14A8], r15
0x18002d03a  mov     [rsp+14F0h+var_14A0], r15
0x18002d03f  mov     [rbp+13F0h+var_1448], rdi
0x18002d043  mov     [rbp+13F0h+var_1440], r14
0x18002d047  mov     [rsp+14F0h+var_1488], r15
0x18002d04c  xorps   xmm0, xmm0
0x18002d04f  xor     eax, eax
0x18002d051  movups  [rbp+13F0h+var_1468], xmm0
0x18002d055  mov     [rbp+13F0h+var_1458], rax
0x18002d059  xorps   xmm1, xmm1
0x18002d05c  movups  [rsp+14F0h+var_1480], xmm1
0x18002d061  mov     [rbp+13F0h+var_1470], rax
0x18002d065  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002d06c  test    rax, rax
0x18002d06f  jz      short loc_18002D07C
0x18002d071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d076  mov     [rbp+13F0h+var_1450], rax
0x18002d07a  jmp     short loc_18002D080
0x18002d07c  mov     [rbp+13F0h+var_1450], r15
0x18002d080  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002d087  test    rax, rax
0x18002d08a  jz      short loc_18002D096
0x18002d08c  lea     rcx, [rsp+14F0h+var_14D0]
0x18002d091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d096  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002d09d  test    rax, rax
0x18002d0a0  jz      short loc_18002D0B6
0x18002d0a2  mov     r8d, 400h
0x18002d0a8  lea     rdx, [rbp+13F0h+var_1430]
0x18002d0ac  lea     rcx, [rsp+14F0h+var_14D0]
0x18002d0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002d0bd  test    rax, rax
0x18002d0c0  jz      short loc_18002D0CC
0x18002d0c2  lea     rcx, [rsp+14F0h+var_14D0]
0x18002d0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0cc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002d0d3  test    rax, rax
0x18002d0d6  jz      short loc_18002D0E9
0x18002d0d8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002d0dd  jnz     short loc_18002D0E9
0x18002d0df  lea     rcx, [rsp+14F0h+var_14D0]
0x18002d0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0e9  cmp     [rsp+14F0h+var_14C8], r15d
0x18002d0ee  jge     loc_18002D1FC
0x18002d0f4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18002d0fb  jnz     short loc_18002D11C
0x18002d0fd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002d104  test    rax, rax
0x18002d107  jz      short loc_18002D112
0x18002d109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d10e  test    al, al
0x18002d110  jmp     short loc_18002D11A
0x18002d112  call    cs:__imp_IsDebuggerPresent
0x18002d118  test    eax, eax
0x18002d11a  jz      short loc_18002D123
0x18002d11c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002d121  jz      short loc_18002D149
0x18002d123  mov     rax, cs:g_pfnResultLoggingCallback
0x18002d12a  test    rax, rax
0x18002d12d  jz      short loc_18002D1A2
0x18002d12f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002d136  jnz     short loc_18002D1A2
0x18002d138  xor     r8d, r8d
0x18002d13b  xor     edx, edx
0x18002d13d  lea     rcx, [rsp+14F0h+var_14D0]
0x18002d142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d147  jmp     short loc_18002D1A2
0x18002d149  mov     ebx, 800h
0x18002d14e  mov     rax, cs:g_pfnResultLoggingCallback
0x18002d155  test    rax, rax
0x18002d158  jz      short loc_18002D177
0x18002d15a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002d161  jnz     short loc_18002D177
0x18002d163  mov     r8d, ebx
0x18002d166  lea     rdx, [rbp+13F0h+OutputString]
0x18002d16d  lea     rcx, [rsp+14F0h+var_14D0]
0x18002d172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d177  cmp     [rbp+13F0h+OutputString], r15w
0x18002d17f  jnz     short loc_18002D195
0x18002d181  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002d186  mov     rdx, rbx; unsigned __int16 *
0x18002d189  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002d190  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002d195  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002d19c  call    cs:__imp_OutputDebugStringW
0x18002d1a2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002d1a7  jnz     short loc_18002D1B2
0x18002d1a9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18002d1b0  jz      short loc_18002D1C4
0x18002d1b2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002d1b9  test    rax, rax
0x18002d1bc  jz      short loc_18002D1C4
0x18002d1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1c3  nop
0x18002d1c4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002d1c9  jnz     short loc_18002D1F1
0x18002d1cb  mov     rcx, [rbp+13F0h+var_30]
0x18002d1d2  xor     rcx, rsp; StackCookie
0x18002d1d5  call    __security_check_cookie
0x18002d1da  mov     rbx, [rsp+14F0h+arg_10]
0x18002d1e2  add     rsp, 14D0h
0x18002d1e9  pop     r15
0x18002d1eb  pop     r14
0x18002d1ed  pop     rdi
0x18002d1ee  pop     rsi
0x18002d1ef  pop     rbp
0x18002d1f0  retn
0x18002d1f1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002d1f6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002d1fc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
