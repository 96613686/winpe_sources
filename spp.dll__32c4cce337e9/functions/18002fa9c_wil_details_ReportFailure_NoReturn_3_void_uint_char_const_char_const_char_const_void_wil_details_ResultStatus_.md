# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18002fa9c`
- end: `0x18002fcfc`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002f868`

## callees

- `0x18002fa9c`
- `0x1800311f4`
- `0x180031a60`
- `0x1800328d0`
- `0x180033e40`
- `0x180035b9a`
- `0x180035c60`
- `0x180037010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18002fc40`
- `KERNEL32!IsDebuggerPresent` at `0x18002fc40`
- `KERNEL32!OutputDebugStringW` at `0x18002fcca`
- `KERNEL32!OutputDebugStringW` at `0x18002fcca`
- `KERNEL32!GetCurrentThreadId` at `0x18002fb3d`
- `KERNEL32!GetCurrentThreadId` at `0x18002fb3d`

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
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18002fa9c  mov     [rsp-8+arg_18], rbx
0x18002faa1  push    rbp
0x18002faa2  push    rsi
0x18002faa3  push    rdi
0x18002faa4  push    r12
0x18002faa6  push    r13
0x18002faa8  push    r14
0x18002faaa  push    r15
0x18002faac  lea     rbp, [rsp-13C0h]
0x18002fab4  mov     eax, 14C0h
0x18002fab9  call    _alloca_probe
0x18002fabe  sub     rsp, rax
0x18002fac1  mov     rsi, [rbp+13F0h+arg_28]
0x18002fac8  mov     r15, r8
0x18002facb  mov     r14d, edx
0x18002face  mov     r12, rcx
0x18002fad1  xor     edx, edx; Val
0x18002fad3  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002fad8  mov     r8d, 98h; Size
0x18002fade  call    memset_0
0x18002fae3  mov     rbx, [rbp+13F0h+arg_30]
0x18002faea  xor     r13d, r13d
0x18002faed  mov     [rbp+13F0h+OutputString], r13w
0x18002faf5  mov     [rbp+13F0h+var_1430], r13b
0x18002faf9  mov     ecx, [rbx]; this
0x18002fafb  mov     eax, [rbx+4]
0x18002fafe  mov     [rsp+14F0h+var_14C8], ecx
0x18002fb02  mov     [rsp+14F0h+var_14C4], eax
0x18002fb06  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002fb0b  cmp     dword ptr [rbx+8], 1
0x18002fb0f  mov     edi, eax
0x18002fb11  lea     eax, [r13+8]
0x18002fb15  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18002fb1d  mov     ecx, r13d
0x18002fb20  cmovz   ecx, eax
0x18002fb23  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002fb27  lea     ecx, [rax-7]
0x18002fb2a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002fb32  inc     ecx
0x18002fb34  mov     [rsp+14F0h+var_14B8], r13
0x18002fb39  mov     [rsp+14F0h+var_14C0], ecx
0x18002fb3d  call    cs:__imp_GetCurrentThreadId
0x18002fb43  xorps   xmm0, xmm0
0x18002fb46  mov     [rsp+14F0h+var_1498], r15
0x18002fb4b  mov     [rsp+14F0h+var_14B0], eax
0x18002fb4f  xorps   xmm1, xmm1
0x18002fb52  xor     eax, eax
0x18002fb54  mov     [rsp+14F0h+var_1490], r14d
0x18002fb59  mov     [rbp+13F0h+var_1458], rax
0x18002fb5d  mov     [rbp+13F0h+var_1470], rax
0x18002fb61  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002fb68  mov     [rsp+14F0h+var_148C], edi
0x18002fb6c  mov     [rsp+14F0h+var_14A8], r13
0x18002fb71  mov     [rsp+14F0h+var_14A0], r13
0x18002fb76  mov     [rbp+13F0h+var_1448], rsi
0x18002fb7a  mov     [rbp+13F0h+var_1440], r12
0x18002fb7e  mov     [rsp+14F0h+var_1488], r13
0x18002fb83  movups  [rbp+13F0h+var_1468], xmm0
0x18002fb87  movups  [rsp+14F0h+var_1480], xmm1
0x18002fb8c  test    rax, rax
0x18002fb8f  jz      short loc_18002FB9C
0x18002fb91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb96  mov     [rbp+13F0h+var_1450], rax
0x18002fb9a  jmp     short loc_18002FBA0
0x18002fb9c  mov     [rbp+13F0h+var_1450], r13
0x18002fba0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002fba7  test    rax, rax
0x18002fbaa  jz      short loc_18002FBB6
0x18002fbac  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbb6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002fbbd  test    rax, rax
0x18002fbc0  jz      short loc_18002FBD6
0x18002fbc2  mov     r8d, 400h
0x18002fbc8  lea     rdx, [rbp+13F0h+var_1430]
0x18002fbcc  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbd6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002fbdd  test    rax, rax
0x18002fbe0  jz      short loc_18002FBEC
0x18002fbe2  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002fbf3  test    rax, rax
0x18002fbf6  jz      short loc_18002FC09
0x18002fbf8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002fbfd  jnz     short loc_18002FC09
0x18002fbff  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc09  cmp     [rsp+14F0h+var_14C8], r13d
0x18002fc0e  jl      short loc_18002FC22
0x18002fc10  mov     ecx, 8000FFFFh; this
0x18002fc15  mov     [rsp+14F0h+var_14C8], ecx
0x18002fc19  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002fc1e  mov     [rsp+14F0h+var_14C4], eax
0x18002fc22  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18002fc29  jnz     short loc_18002FC4A
0x18002fc2b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002fc32  test    rax, rax
0x18002fc35  jz      short loc_18002FC40
0x18002fc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc3c  test    al, al
0x18002fc3e  jmp     short loc_18002FC48
0x18002fc40  call    cs:__imp_IsDebuggerPresent
0x18002fc46  test    eax, eax
0x18002fc48  jz      short loc_18002FC51
0x18002fc4a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002fc4f  jz      short loc_18002FC77
0x18002fc51  mov     rax, cs:g_pfnResultLoggingCallback
0x18002fc58  test    rax, rax
0x18002fc5b  jz      short loc_18002FCD0
0x18002fc5d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002fc64  jnz     short loc_18002FCD0
0x18002fc66  xor     r8d, r8d
0x18002fc69  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fc6e  xor     edx, edx
0x18002fc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc75  jmp     short loc_18002FCD0
0x18002fc77  mov     rax, cs:g_pfnResultLoggingCallback
0x18002fc7e  mov     ebx, 800h
0x18002fc83  test    rax, rax
0x18002fc86  jz      short loc_18002FCA5
0x18002fc88  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002fc8f  jnz     short loc_18002FCA5
0x18002fc91  mov     r8d, ebx
0x18002fc94  lea     rdx, [rbp+13F0h+OutputString]
0x18002fc9b  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fca5  cmp     [rbp+13F0h+OutputString], r13w
0x18002fcad  jnz     short loc_18002FCC3
0x18002fcaf  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002fcb4  mov     rdx, rbx; unsigned __int16 *
0x18002fcb7  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002fcbe  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002fcc3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002fcca  call    cs:__imp_OutputDebugStringW
0x18002fcd0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002fcd5  jnz     short loc_18002FCE0
0x18002fcd7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18002fcde  jz      short loc_18002FCF1
0x18002fce0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002fce7  test    rax, rax
0x18002fcea  jz      short loc_18002FCF1
0x18002fcec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcf1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002fcf6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
