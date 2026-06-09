# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800d69ec`
- end: `0x1800d6c82`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800d66c0`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x1800d69ec`
- `0x1800d77f4`
- `0x1800d8780`
- `0x1800d9068`
- `0x1800d91d0`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d6a97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d6a97`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800d6b92`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800d6b92`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800d6c1c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800d6c1c`

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
0x1800d69ec  mov     [rsp-8+arg_10], rbx
0x1800d69f1  push    rbp
0x1800d69f2  push    rsi
0x1800d69f3  push    rdi
0x1800d69f4  push    r14
0x1800d69f6  push    r15
0x1800d69f8  lea     rbp, [rsp-13D0h]
0x1800d6a00  mov     eax, 14D0h
0x1800d6a05  call    _alloca_probe
0x1800d6a0a  sub     rsp, rax
0x1800d6a0d  mov     rax, cs:__security_cookie
0x1800d6a14  xor     rax, rsp
0x1800d6a17  mov     [rbp+13F0h+var_30], rax
0x1800d6a1e  mov     esi, edx
0x1800d6a20  mov     r14, rcx
0x1800d6a23  mov     rdi, [rbp+13F0h+arg_28]
0x1800d6a2a  xor     edx, edx; Val
0x1800d6a2c  mov     r8d, 98h; Size
0x1800d6a32  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800d6a37  call    memset_0
0x1800d6a3c  nop
0x1800d6a3d  xor     r15d, r15d
0x1800d6a40  mov     [rbp+13F0h+OutputString], r15w
0x1800d6a48  mov     [rbp+13F0h+var_1430], r15b
0x1800d6a4c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800d6a53  mov     ecx, [rdx]; this
0x1800d6a55  mov     [rsp+14F0h+var_14C8], ecx
0x1800d6a59  mov     eax, [rdx+4]
0x1800d6a5c  mov     [rsp+14F0h+var_14C4], eax
0x1800d6a60  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800d6a65  mov     ebx, eax
0x1800d6a67  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800d6a6f  mov     ecx, r15d
0x1800d6a72  lea     eax, [r15+8]
0x1800d6a76  cmp     dword ptr [rdx+8], 1
0x1800d6a7a  cmovz   ecx, eax
0x1800d6a7d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800d6a81  lea     ecx, [rax-7]
0x1800d6a84  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800d6a8c  inc     ecx
0x1800d6a8e  mov     [rsp+14F0h+var_14C0], ecx
0x1800d6a92  mov     [rsp+14F0h+var_14B8], r15
0x1800d6a97  call    cs:__imp_GetCurrentThreadId
0x1800d6a9d  mov     [rsp+14F0h+var_14B0], eax
0x1800d6aa1  lea     rax, aWil; "wil"
0x1800d6aa8  mov     [rsp+14F0h+var_1498], rax
0x1800d6aad  mov     [rsp+14F0h+var_1490], esi
0x1800d6ab1  mov     [rsp+14F0h+var_148C], ebx
0x1800d6ab5  mov     [rsp+14F0h+var_14A8], r15
0x1800d6aba  mov     [rsp+14F0h+var_14A0], r15
0x1800d6abf  mov     [rbp+13F0h+var_1448], rdi
0x1800d6ac3  mov     [rbp+13F0h+var_1440], r14
0x1800d6ac7  mov     [rsp+14F0h+var_1488], r15
0x1800d6acc  xorps   xmm0, xmm0
0x1800d6acf  xor     eax, eax
0x1800d6ad1  movups  [rbp+13F0h+var_1468], xmm0
0x1800d6ad5  mov     [rbp+13F0h+var_1458], rax
0x1800d6ad9  xorps   xmm1, xmm1
0x1800d6adc  movups  [rsp+14F0h+var_1480], xmm1
0x1800d6ae1  mov     [rbp+13F0h+var_1470], rax
0x1800d6ae5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800d6aec  test    rax, rax
0x1800d6aef  jz      short loc_1800D6AFC
0x1800d6af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6af6  mov     [rbp+13F0h+var_1450], rax
0x1800d6afa  jmp     short loc_1800D6B00
0x1800d6afc  mov     [rbp+13F0h+var_1450], r15
0x1800d6b00  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800d6b07  test    rax, rax
0x1800d6b0a  jz      short loc_1800D6B16
0x1800d6b0c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800d6b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6b16  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800d6b1d  test    rax, rax
0x1800d6b20  jz      short loc_1800D6B36
0x1800d6b22  mov     r8d, 400h
0x1800d6b28  lea     rdx, [rbp+13F0h+var_1430]
0x1800d6b2c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800d6b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6b36  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800d6b3d  test    rax, rax
0x1800d6b40  jz      short loc_1800D6B4C
0x1800d6b42  lea     rcx, [rsp+14F0h+var_14D0]
0x1800d6b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6b4c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800d6b53  test    rax, rax
0x1800d6b56  jz      short loc_1800D6B69
0x1800d6b58  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800d6b5d  jnz     short loc_1800D6B69
0x1800d6b5f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800d6b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6b69  cmp     [rsp+14F0h+var_14C8], r15d
0x1800d6b6e  jge     loc_1800D6C7C
0x1800d6b74  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800d6b7b  jnz     short loc_1800D6B9C
0x1800d6b7d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800d6b84  test    rax, rax
0x1800d6b87  jz      short loc_1800D6B92
0x1800d6b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6b8e  test    al, al
0x1800d6b90  jmp     short loc_1800D6B9A
0x1800d6b92  call    cs:__imp_IsDebuggerPresent
0x1800d6b98  test    eax, eax
0x1800d6b9a  jz      short loc_1800D6BA3
0x1800d6b9c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800d6ba1  jz      short loc_1800D6BC9
0x1800d6ba3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800d6baa  test    rax, rax
0x1800d6bad  jz      short loc_1800D6C22
0x1800d6baf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800d6bb6  jnz     short loc_1800D6C22
0x1800d6bb8  xor     r8d, r8d
0x1800d6bbb  xor     edx, edx
0x1800d6bbd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800d6bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6bc7  jmp     short loc_1800D6C22
0x1800d6bc9  mov     ebx, 800h
0x1800d6bce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800d6bd5  test    rax, rax
0x1800d6bd8  jz      short loc_1800D6BF7
0x1800d6bda  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800d6be1  jnz     short loc_1800D6BF7
0x1800d6be3  mov     r8d, ebx
0x1800d6be6  lea     rdx, [rbp+13F0h+OutputString]
0x1800d6bed  lea     rcx, [rsp+14F0h+var_14D0]
0x1800d6bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6bf7  cmp     [rbp+13F0h+OutputString], r15w
0x1800d6bff  jnz     short loc_1800D6C15
0x1800d6c01  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800d6c06  mov     rdx, rbx; unsigned __int16 *
0x1800d6c09  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800d6c10  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800d6c15  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800d6c1c  call    cs:__imp_OutputDebugStringW
0x1800d6c22  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800d6c27  jnz     short loc_1800D6C32
0x1800d6c29  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800d6c30  jz      short loc_1800D6C44
0x1800d6c32  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800d6c39  test    rax, rax
0x1800d6c3c  jz      short loc_1800D6C44
0x1800d6c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c43  nop
0x1800d6c44  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800d6c49  jnz     short loc_1800D6C71
0x1800d6c4b  mov     rcx, [rbp+13F0h+var_30]
0x1800d6c52  xor     rcx, rsp; StackCookie
0x1800d6c55  call    __security_check_cookie
0x1800d6c5a  mov     rbx, [rsp+14F0h+arg_10]
0x1800d6c62  add     rsp, 14D0h
0x1800d6c69  pop     r15
0x1800d6c6b  pop     r14
0x1800d6c6d  pop     rdi
0x1800d6c6e  pop     rsi
0x1800d6c6f  pop     rbp
0x1800d6c70  retn
0x1800d6c71  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800d6c76  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800d6c7c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
