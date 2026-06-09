# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001f524`
- end: `0x18001f7e9`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001f488`

## callees

- `0x18000856c`
- `0x180015e04`
- `0x18001733c`
- `0x1800193b0`
- `0x180019bc0`
- `0x180019e38`
- `0x18001f524`
- `0x180068320`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f5e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f5e5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f6e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f6e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f77d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f77d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x18001f524  mov     [rsp-8+arg_18], rbx
0x18001f529  push    rbp
0x18001f52a  push    rsi
0x18001f52b  push    rdi
0x18001f52c  push    r12
0x18001f52e  push    r13
0x18001f530  push    r14
0x18001f532  push    r15
0x18001f534  lea     rbp, [rsp-13C0h]
0x18001f53c  mov     eax, 14C0h
0x18001f541  call    _alloca_probe
0x18001f546  sub     rsp, rax
0x18001f549  mov     r14, r8
0x18001f54c  mov     esi, edx
0x18001f54e  mov     rbx, rcx
0x18001f551  mov     r15, [rbp+13F0h+arg_28]
0x18001f558  xor     r13d, r13d
0x18001f55b  cmp     cs:g_pfnThrowPlatformException, r13
0x18001f562  setnz   dil
0x18001f566  xor     edx, edx; Val
0x18001f568  mov     r8d, 98h; Size
0x18001f56e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001f573  call    memset_0
0x18001f578  nop
0x18001f579  mov     [rbp+13F0h+OutputString], r13w
0x18001f581  mov     [rbp+13F0h+var_1430], r13b
0x18001f585  mov     rdx, [rbp+13F0h+arg_30]; int
0x18001f58c  mov     ecx, [rdx]; this
0x18001f58e  mov     [rsp+14F0h+var_14C8], ecx
0x18001f592  mov     eax, [rdx+4]
0x18001f595  mov     [rsp+14F0h+var_14C4], eax
0x18001f599  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001f59e  mov     r12d, eax
0x18001f5a1  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18001f5a6  mov     ecx, r13d
0x18001f5a9  lea     eax, [r13+8]
0x18001f5ad  cmp     dword ptr [rdx+8], 1
0x18001f5b1  cmovz   ecx, eax
0x18001f5b4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001f5b8  lea     ecx, [rax-7]
0x18001f5bb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001f5c3  inc     ecx
0x18001f5c5  mov     [rsp+14F0h+var_14C0], ecx
0x18001f5c9  mov     rcx, [rbp+13F0h+arg_38]
0x18001f5d0  test    rcx, rcx
0x18001f5d3  jz      short loc_18001F5E0
0x18001f5d5  cmp     [rcx], r13w
0x18001f5d9  mov     [rsp+14F0h+var_14B8], rcx
0x18001f5de  jnz     short loc_18001F5E5
0x18001f5e0  mov     [rsp+14F0h+var_14B8], r13
0x18001f5e5  call    cs:__imp_GetCurrentThreadId
0x18001f5eb  mov     [rsp+14F0h+var_14B0], eax
0x18001f5ef  mov     [rsp+14F0h+var_1498], r14
0x18001f5f4  mov     [rsp+14F0h+var_1490], esi
0x18001f5f8  mov     [rsp+14F0h+var_148C], r12d
0x18001f5fd  mov     [rsp+14F0h+var_14A8], r13
0x18001f602  mov     [rsp+14F0h+var_14A0], r13
0x18001f607  mov     [rbp+13F0h+var_1448], r15
0x18001f60b  mov     [rbp+13F0h+var_1440], rbx
0x18001f60f  mov     [rsp+14F0h+var_1488], r13
0x18001f614  xorps   xmm0, xmm0
0x18001f617  xor     eax, eax
0x18001f619  movups  [rbp+13F0h+var_1468], xmm0
0x18001f61d  mov     [rbp+13F0h+var_1458], rax
0x18001f621  xorps   xmm1, xmm1
0x18001f624  movups  [rsp+14F0h+var_1480], xmm1
0x18001f629  mov     [rbp+13F0h+var_1470], rax
0x18001f62d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001f634  test    rax, rax
0x18001f637  jz      short loc_18001F644
0x18001f639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f63e  mov     [rbp+13F0h+var_1450], rax
0x18001f642  jmp     short loc_18001F648
0x18001f644  mov     [rbp+13F0h+var_1450], r13
0x18001f648  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001f64f  test    rax, rax
0x18001f652  jz      short loc_18001F65E
0x18001f654  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f65e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001f665  test    rax, rax
0x18001f668  jz      short loc_18001F67E
0x18001f66a  mov     r8d, 400h
0x18001f670  lea     rdx, [rbp+13F0h+var_1430]
0x18001f674  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f67e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f685  test    rax, rax
0x18001f688  jz      short loc_18001F694
0x18001f68a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f694  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f69b  test    rax, rax
0x18001f69e  jz      short loc_18001F6B6
0x18001f6a0  test    dil, dil
0x18001f6a3  jnz     short loc_18001F6B6
0x18001f6a5  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001f6aa  jnz     short loc_18001F6B6
0x18001f6ac  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6b6  cmp     [rsp+14F0h+var_14C8], r13d
0x18001f6bb  jl      short loc_18001F6C3
0x18001f6bd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001f6c3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001f6ca  jnz     short loc_18001F6EB
0x18001f6cc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001f6d3  test    rax, rax
0x18001f6d6  jz      short loc_18001F6E1
0x18001f6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6dd  test    al, al
0x18001f6df  jmp     short loc_18001F6E9
0x18001f6e1  call    cs:__imp_IsDebuggerPresent
0x18001f6e7  test    eax, eax
0x18001f6e9  jz      short loc_18001F6F4
0x18001f6eb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001f6f0  mov     bl, 1
0x18001f6f2  jz      short loc_18001F6F7
0x18001f6f4  mov     bl, r13b
0x18001f6f7  test    dil, dil
0x18001f6fa  jnz     short loc_18001F726
0x18001f6fc  test    bl, bl
0x18001f6fe  jnz     short loc_18001F726
0x18001f700  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f707  test    rax, rax
0x18001f70a  jz      short loc_18001F783
0x18001f70c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001f713  jnz     short loc_18001F783
0x18001f715  xor     r8d, r8d
0x18001f718  xor     edx, edx
0x18001f71a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f724  jmp     short loc_18001F783
0x18001f726  mov     esi, 800h
0x18001f72b  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f732  test    rax, rax
0x18001f735  jz      short loc_18001F754
0x18001f737  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001f73e  jnz     short loc_18001F754
0x18001f740  mov     r8d, esi
0x18001f743  lea     rdx, [rbp+13F0h+OutputString]
0x18001f74a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f754  cmp     [rbp+13F0h+OutputString], r13w
0x18001f75c  jnz     short loc_18001F772
0x18001f75e  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001f763  mov     rdx, rsi; unsigned __int16 *
0x18001f766  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001f76d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001f772  test    bl, bl
0x18001f774  jz      short loc_18001F783
0x18001f776  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001f77d  call    cs:__imp_OutputDebugStringW
0x18001f783  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001f788  jnz     short loc_18001F793
0x18001f78a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001f791  jz      short loc_18001F7A5
0x18001f793  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001f79a  test    rax, rax
0x18001f79d  jz      short loc_18001F7A5
0x18001f79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7a4  nop
0x18001f7a5  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001f7aa  jz      short loc_18001F7B7
0x18001f7ac  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001f7b1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001f7b7  test    dil, dil
0x18001f7ba  jz      short loc_18001F7D4
0x18001f7bc  lea     rdx, [rbp+13F0h+OutputString]
0x18001f7c3  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f7c8  mov     rax, cs:g_pfnThrowPlatformException
0x18001f7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7d4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001f7d9  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18001f7de  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001f7e3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
