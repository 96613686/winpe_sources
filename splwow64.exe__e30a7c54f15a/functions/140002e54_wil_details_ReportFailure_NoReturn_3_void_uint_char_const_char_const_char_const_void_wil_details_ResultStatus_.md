# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002e54`
- end: `0x1400030b4`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002bf8`

## callees

- `0x1400028b8`
- `0x140002e54`
- `0x140004374`
- `0x140004b0c`
- `0x140005530`
- `0x140006280`
- `0x1400154e0`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002ef5`
- `KERNEL32!GetCurrentThreadId` at `0x140002ef5`
- `KERNEL32!OutputDebugStringW` at `0x140003082`
- `KERNEL32!OutputDebugStringW` at `0x140003082`
- `KERNEL32!IsDebuggerPresent` at `0x140002ff8`
- `KERNEL32!IsDebuggerPresent` at `0x140002ff8`

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
0x140002e54  mov     [rsp-8+arg_18], rbx
0x140002e59  push    rbp
0x140002e5a  push    rsi
0x140002e5b  push    rdi
0x140002e5c  push    r12
0x140002e5e  push    r13
0x140002e60  push    r14
0x140002e62  push    r15
0x140002e64  lea     rbp, [rsp-13C0h]
0x140002e6c  mov     eax, 14C0h
0x140002e71  call    _alloca_probe
0x140002e76  sub     rsp, rax
0x140002e79  mov     rsi, [rbp+13F0h+arg_28]
0x140002e80  mov     r15, r8
0x140002e83  mov     r14d, edx
0x140002e86  mov     r12, rcx
0x140002e89  xor     edx, edx; Val
0x140002e8b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002e90  mov     r8d, 98h; Size
0x140002e96  call    memset_0
0x140002e9b  mov     rbx, [rbp+13F0h+arg_30]
0x140002ea2  xor     r13d, r13d
0x140002ea5  mov     [rbp+13F0h+OutputString], r13w
0x140002ead  mov     [rbp+13F0h+var_1430], r13b
0x140002eb1  mov     ecx, [rbx]; this
0x140002eb3  mov     eax, [rbx+4]
0x140002eb6  mov     [rsp+14F0h+var_14C8], ecx
0x140002eba  mov     [rsp+14F0h+var_14C4], eax
0x140002ebe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002ec3  cmp     dword ptr [rbx+8], 1
0x140002ec7  mov     edi, eax
0x140002ec9  lea     eax, [r13+8]
0x140002ecd  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140002ed5  mov     ecx, r13d
0x140002ed8  cmovz   ecx, eax
0x140002edb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002edf  lea     ecx, [rax-7]
0x140002ee2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002eea  inc     ecx
0x140002eec  mov     [rsp+14F0h+var_14B8], r13
0x140002ef1  mov     [rsp+14F0h+var_14C0], ecx
0x140002ef5  call    cs:__imp_GetCurrentThreadId
0x140002efb  xorps   xmm0, xmm0
0x140002efe  mov     [rsp+14F0h+var_1498], r15
0x140002f03  mov     [rsp+14F0h+var_14B0], eax
0x140002f07  xorps   xmm1, xmm1
0x140002f0a  xor     eax, eax
0x140002f0c  mov     [rsp+14F0h+var_1490], r14d
0x140002f11  mov     [rbp+13F0h+var_1458], rax
0x140002f15  mov     [rbp+13F0h+var_1470], rax
0x140002f19  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002f20  mov     [rsp+14F0h+var_148C], edi
0x140002f24  mov     [rsp+14F0h+var_14A8], r13
0x140002f29  mov     [rsp+14F0h+var_14A0], r13
0x140002f2e  mov     [rbp+13F0h+var_1448], rsi
0x140002f32  mov     [rbp+13F0h+var_1440], r12
0x140002f36  mov     [rsp+14F0h+var_1488], r13
0x140002f3b  movups  [rbp+13F0h+var_1468], xmm0
0x140002f3f  movups  [rsp+14F0h+var_1480], xmm1
0x140002f44  test    rax, rax
0x140002f47  jz      short loc_140002F54
0x140002f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f4e  mov     [rbp+13F0h+var_1450], rax
0x140002f52  jmp     short loc_140002F58
0x140002f54  mov     [rbp+13F0h+var_1450], r13
0x140002f58  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002f5f  test    rax, rax
0x140002f62  jz      short loc_140002F6E
0x140002f64  lea     rcx, [rsp+14F0h+var_14D0]
0x140002f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f6e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002f75  test    rax, rax
0x140002f78  jz      short loc_140002F8E
0x140002f7a  mov     r8d, 400h
0x140002f80  lea     rdx, [rbp+13F0h+var_1430]
0x140002f84  lea     rcx, [rsp+14F0h+var_14D0]
0x140002f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f8e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002f95  test    rax, rax
0x140002f98  jz      short loc_140002FA4
0x140002f9a  lea     rcx, [rsp+14F0h+var_14D0]
0x140002f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fa4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002fab  test    rax, rax
0x140002fae  jz      short loc_140002FC1
0x140002fb0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002fb5  jnz     short loc_140002FC1
0x140002fb7  lea     rcx, [rsp+14F0h+var_14D0]
0x140002fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fc1  cmp     [rsp+14F0h+var_14C8], r13d
0x140002fc6  jl      short loc_140002FDA
0x140002fc8  mov     ecx, 8000FFFFh; this
0x140002fcd  mov     [rsp+14F0h+var_14C8], ecx
0x140002fd1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002fd6  mov     [rsp+14F0h+var_14C4], eax
0x140002fda  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140002fe1  jnz     short loc_140003002
0x140002fe3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002fea  test    rax, rax
0x140002fed  jz      short loc_140002FF8
0x140002fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ff4  test    al, al
0x140002ff6  jmp     short loc_140003000
0x140002ff8  call    cs:__imp_IsDebuggerPresent
0x140002ffe  test    eax, eax
0x140003000  jz      short loc_140003009
0x140003002  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003007  jz      short loc_14000302F
0x140003009  mov     rax, cs:g_pfnResultLoggingCallback
0x140003010  test    rax, rax
0x140003013  jz      short loc_140003088
0x140003015  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000301c  jnz     short loc_140003088
0x14000301e  xor     r8d, r8d
0x140003021  lea     rcx, [rsp+14F0h+var_14D0]
0x140003026  xor     edx, edx
0x140003028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000302d  jmp     short loc_140003088
0x14000302f  mov     rax, cs:g_pfnResultLoggingCallback
0x140003036  mov     ebx, 800h
0x14000303b  test    rax, rax
0x14000303e  jz      short loc_14000305D
0x140003040  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003047  jnz     short loc_14000305D
0x140003049  mov     r8d, ebx
0x14000304c  lea     rdx, [rbp+13F0h+OutputString]
0x140003053  lea     rcx, [rsp+14F0h+var_14D0]
0x140003058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000305d  cmp     [rbp+13F0h+OutputString], r13w
0x140003065  jnz     short loc_14000307B
0x140003067  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000306c  mov     rdx, rbx; unsigned __int16 *
0x14000306f  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003076  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000307b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003082  call    cs:__imp_OutputDebugStringW
0x140003088  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000308d  jnz     short loc_140003098
0x14000308f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140003096  jz      short loc_1400030A9
0x140003098  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000309f  test    rax, rax
0x1400030a2  jz      short loc_1400030A9
0x1400030a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030a9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400030ae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
