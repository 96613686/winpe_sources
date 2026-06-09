# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800088fc`
- end: `0x180008b53`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008694`

## callees

- `0x1800026e0`
- `0x1800088fc`
- `0x18000b2ac`
- `0x18000ba88`
- `0x18000edc4`
- `0x18001218a`
- `0x180012240`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008a9b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000899a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000899a`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v11; // eax
  int v12; // edx
  int v13; // eax
  int v14; // ecx
  int v15; // edi
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v17; // rdx
  __int64 v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  __int64 v26; // [rsp+38h] [rbp-C8h]
  DWORD v27; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2080]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v11 = a7[1];
  v23 = *a7;
  v24 = v11;
  v13 = wil::details::RecordFailFast((wil::details *)(unsigned int)v23, v12);
  v14 = 0;
  v21 = 3;
  v15 = v13;
  if ( a7[2] == 1 )
    v14 = 8;
  v22 = v14;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v27 = CurrentThreadId;
  v31 = a2;
  v37 = 0;
  v35 = 0;
  v32 = v15;
  v28 = 0;
  v29 = a4;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
  {
    v23 = -2147418113;
    v24 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v17);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v22 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v19);
    OutputDebugStringW(OutputString);
  }
  if ( (v22 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v18);
  }
  wil::details::WilFailFast((wil::details *)&v21, v17);
}

```

## disassembly

```asm
0x1800088fc  push    rbp
0x1800088fe  push    rbx
0x1800088ff  push    rsi
0x180008900  push    rdi
0x180008901  push    r12
0x180008903  push    r13
0x180008905  push    r14
0x180008907  push    r15
0x180008909  lea     rbp, [rsp-13C8h]
0x180008911  mov     eax, 14C8h
0x180008916  call    _alloca_probe
0x18000891b  sub     rsp, rax
0x18000891e  mov     rsi, [rbp+1400h+arg_28]
0x180008925  mov     r15, r8
0x180008928  mov     r14d, edx
0x18000892b  mov     r12, rcx
0x18000892e  xor     edx, edx; Val
0x180008930  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008935  mov     r8d, 98h; Size
0x18000893b  mov     r13, r9
0x18000893e  call    memset_0
0x180008943  mov     rbx, [rbp+1400h+arg_30]
0x18000894a  xor     eax, eax
0x18000894c  mov     [rbp+1400h+OutputString], ax
0x180008953  mov     [rbp+1400h+var_1440], al
0x180008956  mov     ecx, [rbx]; this
0x180008958  mov     eax, [rbx+4]
0x18000895b  mov     [rsp+1500h+var_14D8], ecx
0x18000895f  mov     [rsp+1500h+var_14D4], eax
0x180008963  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008968  xor     ecx, ecx
0x18000896a  mov     dword ptr [rsp+1500h+var_14E0], 3
0x180008972  cmp     dword ptr [rbx+8], 1
0x180008976  mov     edi, eax
0x180008978  lea     eax, [rcx+8]
0x18000897b  cmovz   ecx, eax
0x18000897e  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180008982  lea     ecx, [rax-7]
0x180008985  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000898d  inc     ecx
0x18000898f  xor     ebx, ebx
0x180008991  mov     [rsp+1500h+var_14D0], ecx
0x180008995  mov     [rsp+1500h+var_14C8], rbx
0x18000899a  call    cs:__imp_GetCurrentThreadId
0x1800089a0  xorps   xmm0, xmm0
0x1800089a3  mov     [rsp+1500h+var_14A8], r15
0x1800089a8  mov     [rsp+1500h+var_14C0], eax
0x1800089ac  xorps   xmm1, xmm1
0x1800089af  xor     eax, eax
0x1800089b1  mov     [rsp+1500h+var_14A0], r14d
0x1800089b6  mov     [rbp+1400h+var_1468], rax
0x1800089ba  mov     [rbp+1400h+var_1480], rax
0x1800089be  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800089c5  mov     [rsp+1500h+var_149C], edi
0x1800089c9  mov     [rsp+1500h+var_14B8], rbx
0x1800089ce  mov     [rsp+1500h+var_14B0], r13
0x1800089d3  mov     [rbp+1400h+var_1458], rsi
0x1800089d7  mov     [rbp+1400h+var_1450], r12
0x1800089db  mov     [rsp+1500h+var_1498], rbx
0x1800089e0  movups  [rbp+1400h+var_1478], xmm0
0x1800089e4  movups  [rsp+1500h+var_1490], xmm1
0x1800089e9  test    rax, rax
0x1800089ec  jz      short loc_1800089F9
0x1800089ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089f3  mov     [rbp+1400h+var_1460], rax
0x1800089f7  jmp     short loc_1800089FD
0x1800089f9  mov     [rbp+1400h+var_1460], rbx
0x1800089fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008a04  test    rax, rax
0x180008a07  jz      short loc_180008A13
0x180008a09  lea     rcx, [rsp+1500h+var_14E0]
0x180008a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a13  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008a1a  test    rax, rax
0x180008a1d  jz      short loc_180008A33
0x180008a1f  mov     r8d, 400h
0x180008a25  lea     rdx, [rbp+1400h+var_1440]
0x180008a29  lea     rcx, [rsp+1500h+var_14E0]
0x180008a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a33  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a3a  test    rax, rax
0x180008a3d  jz      short loc_180008A49
0x180008a3f  lea     rcx, [rsp+1500h+var_14E0]
0x180008a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a49  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a50  test    rax, rax
0x180008a53  jz      short loc_180008A66
0x180008a55  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008a5a  jnz     short loc_180008A66
0x180008a5c  lea     rcx, [rsp+1500h+var_14E0]
0x180008a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a66  cmp     [rsp+1500h+var_14D8], ebx
0x180008a6a  jl      short loc_180008A7E
0x180008a6c  mov     ecx, 8000FFFFh; this
0x180008a71  mov     [rsp+1500h+var_14D8], ecx
0x180008a75  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008a7a  mov     [rsp+1500h+var_14D4], eax
0x180008a7e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x180008a84  jnz     short loc_180008AA5
0x180008a86  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008a8d  test    rax, rax
0x180008a90  jz      short loc_180008A9B
0x180008a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a97  test    al, al
0x180008a99  jmp     short loc_180008AA3
0x180008a9b  call    cs:__imp_IsDebuggerPresent
0x180008aa1  test    eax, eax
0x180008aa3  jz      short loc_180008AAC
0x180008aa5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008aaa  jz      short loc_180008AD1
0x180008aac  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ab3  test    rax, rax
0x180008ab6  jz      short loc_180008B28
0x180008ab8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180008abe  jnz     short loc_180008B28
0x180008ac0  xor     r8d, r8d
0x180008ac3  lea     rcx, [rsp+1500h+var_14E0]
0x180008ac8  xor     edx, edx
0x180008aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008acf  jmp     short loc_180008B28
0x180008ad1  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ad8  mov     edi, 800h
0x180008add  test    rax, rax
0x180008ae0  jz      short loc_180008AFE
0x180008ae2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180008ae8  jnz     short loc_180008AFE
0x180008aea  mov     r8d, edi
0x180008aed  lea     rdx, [rbp+1400h+OutputString]
0x180008af4  lea     rcx, [rsp+1500h+var_14E0]
0x180008af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008afe  cmp     [rbp+1400h+OutputString], bx
0x180008b05  jnz     short loc_180008B1B
0x180008b07  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180008b0c  mov     rdx, rdi; unsigned __int16 *
0x180008b0f  lea     rcx, [rbp+1400h+OutputString]; this
0x180008b16  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008b1b  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180008b22  call    cs:__imp_OutputDebugStringW
0x180008b28  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008b2d  jnz     short loc_180008B37
0x180008b2f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x180008b35  jz      short loc_180008B48
0x180008b37  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008b3e  test    rax, rax
0x180008b41  jz      short loc_180008B48
0x180008b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b48  lea     rcx, [rsp+1500h+var_14E0]; this
0x180008b4d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
