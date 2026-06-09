# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x14000fa90`
- end: `0x14000fce9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000f8d8`

## callees

- `0x140002fbc`
- `0x140007298`
- `0x140007a8c`
- `0x140009320`
- `0x14000d6ec`
- `0x14000fa90`
- `0x14001c930`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fb2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fb2f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000fc30`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000fc30`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000fcb7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000fcb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v11; // edx
  int v12; // edi
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2080]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = a4;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x14000fa90  push    rbp
0x14000fa92  push    rbx
0x14000fa93  push    rsi
0x14000fa94  push    rdi
0x14000fa95  push    r12
0x14000fa97  push    r13
0x14000fa99  push    r14
0x14000fa9b  push    r15
0x14000fa9d  lea     rbp, [rsp-13C8h]
0x14000faa5  mov     eax, 14C8h
0x14000faaa  call    _alloca_probe
0x14000faaf  sub     rsp, rax
0x14000fab2  mov     r13, r9
0x14000fab5  mov     r15, r8
0x14000fab8  mov     r14d, edx
0x14000fabb  mov     r12, rcx
0x14000fabe  mov     rsi, [rbp+1400h+arg_28]
0x14000fac5  xor     edx, edx; Val
0x14000fac7  mov     r8d, 98h; Size
0x14000facd  lea     rcx, [rsp+1500h+var_14E0]; void *
0x14000fad2  call    memset_0
0x14000fad7  nop
0x14000fad8  xor     eax, eax
0x14000fada  mov     [rbp+1400h+OutputString], ax
0x14000fae1  mov     [rbp+1400h+var_1440], al
0x14000fae4  mov     rbx, [rbp+1400h+arg_30]
0x14000faeb  mov     ecx, [rbx]; this
0x14000faed  mov     [rsp+1500h+var_14D8], ecx
0x14000faf1  mov     eax, [rbx+4]
0x14000faf4  mov     [rsp+1500h+var_14D4], eax
0x14000faf8  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000fafd  mov     edi, eax
0x14000faff  mov     dword ptr [rsp+1500h+var_14E0], 3
0x14000fb07  xor     ecx, ecx
0x14000fb09  lea     eax, [rcx+8]
0x14000fb0c  cmp     dword ptr [rbx+8], 1
0x14000fb10  cmovz   ecx, eax
0x14000fb13  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000fb17  lea     ecx, [rax-7]
0x14000fb1a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000fb22  inc     ecx
0x14000fb24  mov     [rsp+1500h+var_14D0], ecx
0x14000fb28  xor     ebx, ebx
0x14000fb2a  mov     [rsp+1500h+var_14C8], rbx
0x14000fb2f  call    cs:__imp_GetCurrentThreadId
0x14000fb35  mov     [rsp+1500h+var_14C0], eax
0x14000fb39  mov     [rsp+1500h+var_14A8], r15
0x14000fb3e  mov     [rsp+1500h+var_14A0], r14d
0x14000fb43  mov     [rsp+1500h+var_149C], edi
0x14000fb47  mov     [rsp+1500h+var_14B8], rbx
0x14000fb4c  mov     [rsp+1500h+var_14B0], r13
0x14000fb51  mov     [rbp+1400h+var_1458], rsi
0x14000fb55  mov     [rbp+1400h+var_1450], r12
0x14000fb59  mov     [rsp+1500h+var_1498], rbx
0x14000fb5e  xorps   xmm0, xmm0
0x14000fb61  xor     eax, eax
0x14000fb63  movups  [rbp+1400h+var_1478], xmm0
0x14000fb67  mov     [rbp+1400h+var_1468], rax
0x14000fb6b  xorps   xmm1, xmm1
0x14000fb6e  movups  [rsp+1500h+var_1490], xmm1
0x14000fb73  mov     [rbp+1400h+var_1480], rax
0x14000fb77  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000fb7e  test    rax, rax
0x14000fb81  jz      short loc_14000FB8E
0x14000fb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb88  mov     [rbp+1400h+var_1460], rax
0x14000fb8c  jmp     short loc_14000FB92
0x14000fb8e  mov     [rbp+1400h+var_1460], rbx
0x14000fb92  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000fb99  test    rax, rax
0x14000fb9c  jz      short loc_14000FBA8
0x14000fb9e  lea     rcx, [rsp+1500h+var_14E0]
0x14000fba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fba8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000fbaf  test    rax, rax
0x14000fbb2  jz      short loc_14000FBC8
0x14000fbb4  mov     r8d, 400h
0x14000fbba  lea     rdx, [rbp+1400h+var_1440]
0x14000fbbe  lea     rcx, [rsp+1500h+var_14E0]
0x14000fbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fbc8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000fbcf  test    rax, rax
0x14000fbd2  jz      short loc_14000FBDE
0x14000fbd4  lea     rcx, [rsp+1500h+var_14E0]
0x14000fbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fbde  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000fbe5  test    rax, rax
0x14000fbe8  jz      short loc_14000FBFB
0x14000fbea  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000fbef  jnz     short loc_14000FBFB
0x14000fbf1  lea     rcx, [rsp+1500h+var_14E0]
0x14000fbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fbfb  cmp     [rsp+1500h+var_14D8], ebx
0x14000fbff  jl      short loc_14000FC13
0x14000fc01  mov     ecx, 8000FFFFh; this
0x14000fc06  mov     [rsp+1500h+var_14D8], ecx
0x14000fc0a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000fc0f  mov     [rsp+1500h+var_14D4], eax
0x14000fc13  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x14000fc19  jnz     short loc_14000FC3A
0x14000fc1b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000fc22  test    rax, rax
0x14000fc25  jz      short loc_14000FC30
0x14000fc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc2c  test    al, al
0x14000fc2e  jmp     short loc_14000FC38
0x14000fc30  call    cs:__imp_IsDebuggerPresent
0x14000fc36  test    eax, eax
0x14000fc38  jz      short loc_14000FC41
0x14000fc3a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000fc3f  jz      short loc_14000FC66
0x14000fc41  mov     rax, cs:g_pfnResultLoggingCallback
0x14000fc48  test    rax, rax
0x14000fc4b  jz      short loc_14000FCBD
0x14000fc4d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x14000fc53  jnz     short loc_14000FCBD
0x14000fc55  xor     r8d, r8d
0x14000fc58  xor     edx, edx
0x14000fc5a  lea     rcx, [rsp+1500h+var_14E0]
0x14000fc5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc64  jmp     short loc_14000FCBD
0x14000fc66  mov     edi, 800h
0x14000fc6b  mov     rax, cs:g_pfnResultLoggingCallback
0x14000fc72  test    rax, rax
0x14000fc75  jz      short loc_14000FC93
0x14000fc77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x14000fc7d  jnz     short loc_14000FC93
0x14000fc7f  mov     r8d, edi
0x14000fc82  lea     rdx, [rbp+1400h+OutputString]
0x14000fc89  lea     rcx, [rsp+1500h+var_14E0]
0x14000fc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc93  cmp     [rbp+1400h+OutputString], bx
0x14000fc9a  jnz     short loc_14000FCB0
0x14000fc9c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000fca1  mov     rdx, rdi; wchar_t *
0x14000fca4  lea     rcx, [rbp+1400h+OutputString]; this
0x14000fcab  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000fcb0  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000fcb7  call    cs:__imp_OutputDebugStringW
0x14000fcbd  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000fcc2  jnz     short loc_14000FCCC
0x14000fcc4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x14000fcca  jz      short loc_14000FCDE
0x14000fccc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000fcd3  test    rax, rax
0x14000fcd6  jz      short loc_14000FCDE
0x14000fcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fcdd  nop
0x14000fcde  lea     rcx, [rsp+1500h+var_14E0]; this
0x14000fce3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
