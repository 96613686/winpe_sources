# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180001d94`
- end: `0x180002036`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180001d3c`

## callees

- `0x180001400`
- `0x180001ca2`
- `0x180001d94`
- `0x18000203c`
- `0x180002544`
- `0x180002620`
- `0x1800026fc`
- `0x180002f20`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001e4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001e4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180001fd0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180001fd0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180001f46`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180001f46`

## string_xrefs

- `0x180001e55`: `onecore\base\telemetry\utc\service\api\client\current_dll\utcrpcapiwrapperexport.cpp`

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
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
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
  v25 = "onecore\\base\\telemetry\\utc\\service\\api\\client\\current_dll\\utcrpcapiwrapperexport.cpp";
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v37, 1024);
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x180001d94  push    rbp
0x180001d96  push    rsi
0x180001d97  push    rdi
0x180001d98  push    r14
0x180001d9a  push    r15
0x180001d9c  lea     rbp, [rsp-13E0h]
0x180001da4  mov     eax, 14E0h
0x180001da9  call    _alloca_probe
0x180001dae  sub     rsp, rax
0x180001db1  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x180001db9  mov     [rsp+1500h+arg_10], rbx
0x180001dc1  mov     rax, cs:__security_cookie
0x180001dc8  xor     rax, rsp
0x180001dcb  mov     [rbp+1400h+var_30], rax
0x180001dd2  mov     esi, edx
0x180001dd4  mov     r14, rcx
0x180001dd7  mov     rdi, [rbp+1400h+arg_28]
0x180001dde  xor     edx, edx; Val
0x180001de0  mov     r8d, 98h; Size
0x180001de6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180001deb  call    memset_0
0x180001df0  nop
0x180001df1  xor     r15d, r15d
0x180001df4  mov     [rbp+1400h+OutputString], r15w
0x180001dfc  mov     [rbp+1400h+var_1430], r15b
0x180001e00  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180001e07  mov     ecx, [rdx]; this
0x180001e09  mov     [rsp+1500h+var_14D8], ecx
0x180001e0d  mov     eax, [rdx+4]
0x180001e10  mov     [rsp+1500h+var_14D4], eax
0x180001e14  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180001e19  mov     ebx, eax
0x180001e1b  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180001e23  mov     ecx, r15d
0x180001e26  lea     eax, [r15+8]
0x180001e2a  cmp     dword ptr [rdx+8], 1
0x180001e2e  cmovz   ecx, eax
0x180001e31  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180001e35  lea     ecx, [rax-7]
0x180001e38  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180001e40  inc     ecx
0x180001e42  mov     [rsp+1500h+var_14D0], ecx
0x180001e46  mov     [rsp+1500h+var_14C8], r15
0x180001e4b  call    cs:__imp_GetCurrentThreadId
0x180001e51  mov     [rsp+1500h+var_14C0], eax
0x180001e55  lea     rax, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\service"...
0x180001e5c  mov     [rsp+1500h+var_14A8], rax
0x180001e61  mov     [rsp+1500h+var_14A0], esi
0x180001e65  mov     [rsp+1500h+var_149C], ebx
0x180001e69  mov     [rsp+1500h+var_14B8], r15
0x180001e6e  mov     [rsp+1500h+var_14B0], r15
0x180001e73  mov     [rbp+1400h+var_1458], rdi
0x180001e77  mov     [rbp+1400h+var_1450], r14
0x180001e7b  mov     [rsp+1500h+var_1498], r15
0x180001e80  xorps   xmm0, xmm0
0x180001e83  xor     eax, eax
0x180001e85  movups  [rbp+1400h+var_1478], xmm0
0x180001e89  mov     [rbp+1400h+var_1468], rax
0x180001e8d  xorps   xmm1, xmm1
0x180001e90  movups  [rsp+1500h+var_1490], xmm1
0x180001e95  mov     [rbp+1400h+var_1480], rax
0x180001e99  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180001ea0  test    rax, rax
0x180001ea3  jz      short loc_180001EB0
0x180001ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eaa  mov     [rbp+1400h+var_1460], rax
0x180001eae  jmp     short loc_180001EB4
0x180001eb0  mov     [rbp+1400h+var_1460], r15
0x180001eb4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180001ebb  test    rax, rax
0x180001ebe  jz      short loc_180001ECA
0x180001ec0  lea     rcx, [rsp+1500h+var_14E0]
0x180001ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180001ed1  test    rax, rax
0x180001ed4  jz      short loc_180001EEA
0x180001ed6  mov     r8d, 400h
0x180001edc  lea     rdx, [rbp+1400h+var_1430]
0x180001ee0  lea     rcx, [rsp+1500h+var_14E0]
0x180001ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180001ef1  test    rax, rax
0x180001ef4  jz      short loc_180001F00
0x180001ef6  lea     rcx, [rsp+1500h+var_14E0]
0x180001efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f00  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180001f07  test    rax, rax
0x180001f0a  jz      short loc_180001F1D
0x180001f0c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180001f11  jnz     short loc_180001F1D
0x180001f13  lea     rcx, [rsp+1500h+var_14E0]
0x180001f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f1d  cmp     [rsp+1500h+var_14D8], r15d
0x180001f22  jge     loc_180002030
0x180001f28  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180001f2f  jnz     short loc_180001F50
0x180001f31  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180001f38  test    rax, rax
0x180001f3b  jz      short loc_180001F46
0x180001f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f42  test    al, al
0x180001f44  jmp     short loc_180001F4E
0x180001f46  call    cs:__imp_IsDebuggerPresent
0x180001f4c  test    eax, eax
0x180001f4e  jz      short loc_180001F57
0x180001f50  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180001f55  jz      short loc_180001F7D
0x180001f57  mov     rax, cs:g_pfnResultLoggingCallback
0x180001f5e  test    rax, rax
0x180001f61  jz      short loc_180001FD6
0x180001f63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180001f6a  jnz     short loc_180001FD6
0x180001f6c  xor     r8d, r8d
0x180001f6f  xor     edx, edx
0x180001f71  lea     rcx, [rsp+1500h+var_14E0]
0x180001f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f7b  jmp     short loc_180001FD6
0x180001f7d  mov     ebx, 800h
0x180001f82  mov     rax, cs:g_pfnResultLoggingCallback
0x180001f89  test    rax, rax
0x180001f8c  jz      short loc_180001FAB
0x180001f8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180001f95  jnz     short loc_180001FAB
0x180001f97  mov     r8d, ebx
0x180001f9a  lea     rdx, [rbp+1400h+OutputString]
0x180001fa1  lea     rcx, [rsp+1500h+var_14E0]
0x180001fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fab  cmp     [rbp+1400h+OutputString], r15w
0x180001fb3  jnz     short loc_180001FC9
0x180001fb5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180001fba  mov     rdx, rbx; wchar_t *
0x180001fbd  lea     rcx, [rbp+1400h+OutputString]; this
0x180001fc4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180001fc9  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180001fd0  call    cs:__imp_OutputDebugStringW
0x180001fd6  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180001fdb  jnz     short loc_180001FE6
0x180001fdd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180001fe4  jz      short loc_180001FF8
0x180001fe6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180001fed  test    rax, rax
0x180001ff0  jz      short loc_180001FF8
0x180001ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff7  nop
0x180001ff8  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180001ffd  jnz     short loc_180002025
0x180001fff  mov     rcx, [rbp+1400h+var_30]
0x180002006  xor     rcx, rsp; StackCookie
0x180002009  call    __security_check_cookie
0x18000200e  mov     rbx, [rsp+1500h+arg_10]
0x180002016  add     rsp, 14E0h
0x18000201d  pop     r15
0x18000201f  pop     r14
0x180002021  pop     rdi
0x180002022  pop     rsi
0x180002023  pop     rbp
0x180002024  retn
0x180002025  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000202a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002030  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
