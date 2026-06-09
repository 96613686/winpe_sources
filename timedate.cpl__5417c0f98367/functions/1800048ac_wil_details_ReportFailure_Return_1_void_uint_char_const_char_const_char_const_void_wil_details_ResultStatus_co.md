# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800048ac`
- end: `0x180004b40`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004574`

## callees

- `0x1800048ac`
- `0x180005e14`
- `0x180007980`
- `0x180008ff8`
- `0x1800091b4`
- `0x180028f2e`
- `0x180028f60`
- `0x180028ff0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004956`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004956`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004adb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004adb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004a51`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004a51`

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
0x1800048ac  mov     [rsp-8+arg_10], rbx
0x1800048b1  push    rbp
0x1800048b2  push    rsi
0x1800048b3  push    rdi
0x1800048b4  push    r14
0x1800048b6  push    r15
0x1800048b8  lea     rbp, [rsp-13D0h]
0x1800048c0  mov     eax, 14D0h
0x1800048c5  call    _alloca_probe
0x1800048ca  sub     rsp, rax
0x1800048cd  mov     rax, cs:__security_cookie
0x1800048d4  xor     rax, rsp
0x1800048d7  mov     [rbp+13F0h+var_30], rax
0x1800048de  mov     rdi, [rbp+13F0h+arg_28]
0x1800048e5  mov     esi, edx
0x1800048e7  mov     r14, rcx
0x1800048ea  xor     edx, edx; Val
0x1800048ec  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800048f1  mov     r8d, 98h; Size
0x1800048f7  call    memset_0
0x1800048fc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180004903  xor     r15d, r15d
0x180004906  mov     [rbp+13F0h+OutputString], r15w
0x18000490e  mov     [rbp+13F0h+var_1430], r15b
0x180004912  mov     ecx, [rdx]; this
0x180004914  mov     eax, [rdx+4]
0x180004917  mov     [rsp+14F0h+var_14C8], ecx
0x18000491b  mov     [rsp+14F0h+var_14C4], eax
0x18000491f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004924  cmp     dword ptr [rdx+8], 1
0x180004928  mov     ebx, eax
0x18000492a  lea     eax, [r15+8]
0x18000492e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180004936  mov     ecx, r15d
0x180004939  cmovz   ecx, eax
0x18000493c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004940  lea     ecx, [rax-7]
0x180004943  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000494b  inc     ecx
0x18000494d  mov     [rsp+14F0h+var_14B8], r15
0x180004952  mov     [rsp+14F0h+var_14C0], ecx
0x180004956  call    cs:__imp_GetCurrentThreadId
0x18000495c  xorps   xmm0, xmm0
0x18000495f  mov     [rsp+14F0h+var_1490], esi
0x180004963  mov     [rsp+14F0h+var_14B0], eax
0x180004967  xorps   xmm1, xmm1
0x18000496a  lea     rax, aWil; "wil"
0x180004971  mov     [rsp+14F0h+var_148C], ebx
0x180004975  mov     [rsp+14F0h+var_1498], rax
0x18000497a  xor     eax, eax
0x18000497c  mov     [rbp+13F0h+var_1458], rax
0x180004980  mov     [rbp+13F0h+var_1470], rax
0x180004984  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000498b  mov     [rsp+14F0h+var_14A8], r15
0x180004990  mov     [rsp+14F0h+var_14A0], r15
0x180004995  mov     [rbp+13F0h+var_1448], rdi
0x180004999  mov     [rbp+13F0h+var_1440], r14
0x18000499d  mov     [rsp+14F0h+var_1488], r15
0x1800049a2  movups  [rbp+13F0h+var_1468], xmm0
0x1800049a6  movups  [rsp+14F0h+var_1480], xmm1
0x1800049ab  test    rax, rax
0x1800049ae  jz      short loc_1800049BB
0x1800049b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b5  mov     [rbp+13F0h+var_1450], rax
0x1800049b9  jmp     short loc_1800049BF
0x1800049bb  mov     [rbp+13F0h+var_1450], r15
0x1800049bf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800049c6  test    rax, rax
0x1800049c9  jz      short loc_1800049D5
0x1800049cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800049d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800049dc  test    rax, rax
0x1800049df  jz      short loc_1800049F5
0x1800049e1  mov     r8d, 400h
0x1800049e7  lea     rdx, [rbp+13F0h+var_1430]
0x1800049eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800049f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800049fc  test    rax, rax
0x1800049ff  jz      short loc_180004A0B
0x180004a01  lea     rcx, [rsp+14F0h+var_14D0]
0x180004a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004a12  test    rax, rax
0x180004a15  jz      short loc_180004A28
0x180004a17  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004a1c  jnz     short loc_180004A28
0x180004a1e  lea     rcx, [rsp+14F0h+var_14D0]
0x180004a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a28  cmp     [rsp+14F0h+var_14C8], r15d
0x180004a2d  jge     loc_180004B2F
0x180004a33  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180004a3a  jnz     short loc_180004A5B
0x180004a3c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004a43  test    rax, rax
0x180004a46  jz      short loc_180004A51
0x180004a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a4d  test    al, al
0x180004a4f  jmp     short loc_180004A59
0x180004a51  call    cs:__imp_IsDebuggerPresent
0x180004a57  test    eax, eax
0x180004a59  jz      short loc_180004A62
0x180004a5b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004a60  jz      short loc_180004A88
0x180004a62  mov     rax, cs:g_pfnResultLoggingCallback
0x180004a69  test    rax, rax
0x180004a6c  jz      short loc_180004AE1
0x180004a6e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004a75  jnz     short loc_180004AE1
0x180004a77  xor     r8d, r8d
0x180004a7a  lea     rcx, [rsp+14F0h+var_14D0]
0x180004a7f  xor     edx, edx
0x180004a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a86  jmp     short loc_180004AE1
0x180004a88  mov     rax, cs:g_pfnResultLoggingCallback
0x180004a8f  mov     ebx, 800h
0x180004a94  test    rax, rax
0x180004a97  jz      short loc_180004AB6
0x180004a99  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004aa0  jnz     short loc_180004AB6
0x180004aa2  mov     r8d, ebx
0x180004aa5  lea     rdx, [rbp+13F0h+OutputString]
0x180004aac  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab6  cmp     [rbp+13F0h+OutputString], r15w
0x180004abe  jnz     short loc_180004AD4
0x180004ac0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004ac5  mov     rdx, rbx; unsigned __int16 *
0x180004ac8  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004acf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004ad4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004adb  call    cs:__imp_OutputDebugStringW
0x180004ae1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004ae6  jnz     short loc_180004AF1
0x180004ae8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180004aef  jz      short loc_180004B02
0x180004af1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004af8  test    rax, rax
0x180004afb  jz      short loc_180004B02
0x180004afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b02  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004b07  jnz     short loc_180004B35
0x180004b09  mov     rcx, [rbp+13F0h+var_30]
0x180004b10  xor     rcx, rsp; StackCookie
0x180004b13  call    __security_check_cookie
0x180004b18  mov     rbx, [rsp+14F0h+arg_10]
0x180004b20  add     rsp, 14D0h
0x180004b27  pop     r15
0x180004b29  pop     r14
0x180004b2b  pop     rdi
0x180004b2c  pop     rsi
0x180004b2d  pop     rbp
0x180004b2e  retn
0x180004b2f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004b35  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004b3a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
