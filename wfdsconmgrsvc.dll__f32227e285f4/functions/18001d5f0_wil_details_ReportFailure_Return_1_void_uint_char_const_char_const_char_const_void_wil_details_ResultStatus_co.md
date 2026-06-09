# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001d5f0`
- end: `0x18001d886`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001d2b8`

## callees

- `0x180002600`
- `0x180002ffc`
- `0x18001d5f0`
- `0x18001ee14`
- `0x1800208fc`
- `0x180022108`
- `0x180022314`
- `0x180062120`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d69b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d69b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d820`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d820`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d796`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d796`

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
0x18001d5f0  mov     [rsp-8+arg_10], rbx
0x18001d5f5  push    rbp
0x18001d5f6  push    rsi
0x18001d5f7  push    rdi
0x18001d5f8  push    r14
0x18001d5fa  push    r15
0x18001d5fc  lea     rbp, [rsp-13D0h]
0x18001d604  mov     eax, 14D0h
0x18001d609  call    _alloca_probe
0x18001d60e  sub     rsp, rax
0x18001d611  mov     rax, cs:__security_cookie
0x18001d618  xor     rax, rsp
0x18001d61b  mov     [rbp+13F0h+var_30], rax
0x18001d622  mov     esi, edx
0x18001d624  mov     r14, rcx
0x18001d627  mov     rdi, [rbp+13F0h+arg_28]
0x18001d62e  xor     edx, edx; Val
0x18001d630  mov     r8d, 98h; Size
0x18001d636  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001d63b  call    memset_0
0x18001d640  nop
0x18001d641  xor     r15d, r15d
0x18001d644  mov     [rbp+13F0h+OutputString], r15w
0x18001d64c  mov     [rbp+13F0h+var_1430], r15b
0x18001d650  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001d657  mov     ecx, [rdx]; this
0x18001d659  mov     [rsp+14F0h+var_14C8], ecx
0x18001d65d  mov     eax, [rdx+4]
0x18001d660  mov     [rsp+14F0h+var_14C4], eax
0x18001d664  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001d669  mov     ebx, eax
0x18001d66b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18001d673  mov     ecx, r15d
0x18001d676  lea     eax, [r15+8]
0x18001d67a  cmp     dword ptr [rdx+8], 1
0x18001d67e  cmovz   ecx, eax
0x18001d681  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001d685  lea     ecx, [rax-7]
0x18001d688  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001d690  inc     ecx
0x18001d692  mov     [rsp+14F0h+var_14C0], ecx
0x18001d696  mov     [rsp+14F0h+var_14B8], r15
0x18001d69b  call    cs:__imp_GetCurrentThreadId
0x18001d6a1  mov     [rsp+14F0h+var_14B0], eax
0x18001d6a5  lea     rax, aWil; "wil"
0x18001d6ac  mov     [rsp+14F0h+var_1498], rax
0x18001d6b1  mov     [rsp+14F0h+var_1490], esi
0x18001d6b5  mov     [rsp+14F0h+var_148C], ebx
0x18001d6b9  mov     [rsp+14F0h+var_14A8], r15
0x18001d6be  mov     [rsp+14F0h+var_14A0], r15
0x18001d6c3  mov     [rbp+13F0h+var_1448], rdi
0x18001d6c7  mov     [rbp+13F0h+var_1440], r14
0x18001d6cb  mov     [rsp+14F0h+var_1488], r15
0x18001d6d0  xorps   xmm0, xmm0
0x18001d6d3  xor     eax, eax
0x18001d6d5  movups  [rbp+13F0h+var_1468], xmm0
0x18001d6d9  mov     [rbp+13F0h+var_1458], rax
0x18001d6dd  xorps   xmm1, xmm1
0x18001d6e0  movups  [rsp+14F0h+var_1480], xmm1
0x18001d6e5  mov     [rbp+13F0h+var_1470], rax
0x18001d6e9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001d6f0  test    rax, rax
0x18001d6f3  jz      short loc_18001D700
0x18001d6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6fa  mov     [rbp+13F0h+var_1450], rax
0x18001d6fe  jmp     short loc_18001D704
0x18001d700  mov     [rbp+13F0h+var_1450], r15
0x18001d704  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001d70b  test    rax, rax
0x18001d70e  jz      short loc_18001D71A
0x18001d710  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d71a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001d721  test    rax, rax
0x18001d724  jz      short loc_18001D73A
0x18001d726  mov     r8d, 400h
0x18001d72c  lea     rdx, [rbp+13F0h+var_1430]
0x18001d730  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d73a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d741  test    rax, rax
0x18001d744  jz      short loc_18001D750
0x18001d746  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d750  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d757  test    rax, rax
0x18001d75a  jz      short loc_18001D76D
0x18001d75c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001d761  jnz     short loc_18001D76D
0x18001d763  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d76d  cmp     [rsp+14F0h+var_14C8], r15d
0x18001d772  jge     loc_18001D880
0x18001d778  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001d77f  jnz     short loc_18001D7A0
0x18001d781  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001d788  test    rax, rax
0x18001d78b  jz      short loc_18001D796
0x18001d78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d792  test    al, al
0x18001d794  jmp     short loc_18001D79E
0x18001d796  call    cs:__imp_IsDebuggerPresent
0x18001d79c  test    eax, eax
0x18001d79e  jz      short loc_18001D7A7
0x18001d7a0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001d7a5  jz      short loc_18001D7CD
0x18001d7a7  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d7ae  test    rax, rax
0x18001d7b1  jz      short loc_18001D826
0x18001d7b3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001d7ba  jnz     short loc_18001D826
0x18001d7bc  xor     r8d, r8d
0x18001d7bf  xor     edx, edx
0x18001d7c1  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7cb  jmp     short loc_18001D826
0x18001d7cd  mov     ebx, 800h
0x18001d7d2  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d7d9  test    rax, rax
0x18001d7dc  jz      short loc_18001D7FB
0x18001d7de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001d7e5  jnz     short loc_18001D7FB
0x18001d7e7  mov     r8d, ebx
0x18001d7ea  lea     rdx, [rbp+13F0h+OutputString]
0x18001d7f1  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7fb  cmp     [rbp+13F0h+OutputString], r15w
0x18001d803  jnz     short loc_18001D819
0x18001d805  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001d80a  mov     rdx, rbx; unsigned __int16 *
0x18001d80d  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001d814  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001d819  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001d820  call    cs:__imp_OutputDebugStringW
0x18001d826  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001d82b  jnz     short loc_18001D836
0x18001d82d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001d834  jz      short loc_18001D848
0x18001d836  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001d83d  test    rax, rax
0x18001d840  jz      short loc_18001D848
0x18001d842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d847  nop
0x18001d848  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001d84d  jnz     short loc_18001D875
0x18001d84f  mov     rcx, [rbp+13F0h+var_30]
0x18001d856  xor     rcx, rsp; StackCookie
0x18001d859  call    __security_check_cookie
0x18001d85e  mov     rbx, [rsp+14F0h+arg_10]
0x18001d866  add     rsp, 14D0h
0x18001d86d  pop     r15
0x18001d86f  pop     r14
0x18001d871  pop     rdi
0x18001d872  pop     rsi
0x18001d873  pop     rbp
0x18001d874  retn
0x18001d875  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001d87a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001d880  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
