# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180008e88`
- end: `0x1800090fa`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008c14`

## callees

- `0x180008e88`
- `0x18000ae94`
- `0x18000b6a8`
- `0x18000c370`
- `0x18000e3bc`
- `0x180030362`
- `0x180030450`
- `0x180031010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180009032`
- `KERNEL32!IsDebuggerPresent` at `0x180009032`
- `KERNEL32!OutputDebugStringW` at `0x1800090c2`
- `KERNEL32!OutputDebugStringW` at `0x1800090c2`
- `KERNEL32!GetCurrentThreadId` at `0x180008f29`
- `KERNEL32!GetCurrentThreadId` at `0x180008f29`

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
0x180008e88  mov     [rsp-8+arg_18], rbx
0x180008e8d  push    rbp
0x180008e8e  push    rsi
0x180008e8f  push    rdi
0x180008e90  push    r12
0x180008e92  push    r13
0x180008e94  push    r14
0x180008e96  push    r15
0x180008e98  lea     rbp, [rsp-13C0h]
0x180008ea0  mov     eax, 14C0h
0x180008ea5  call    _alloca_probe
0x180008eaa  sub     rsp, rax
0x180008ead  mov     rsi, [rbp+13F0h+arg_28]
0x180008eb4  mov     r15, r8
0x180008eb7  mov     r14d, edx
0x180008eba  mov     r12, rcx
0x180008ebd  xor     edx, edx; Val
0x180008ebf  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008ec4  mov     r8d, 98h; Size
0x180008eca  call    memset_0
0x180008ecf  mov     rbx, [rbp+13F0h+arg_30]
0x180008ed6  xor     r13d, r13d
0x180008ed9  mov     [rbp+13F0h+OutputString], r13w
0x180008ee1  mov     [rbp+13F0h+var_1430], r13b
0x180008ee5  mov     ecx, [rbx]; this
0x180008ee7  mov     eax, [rbx+4]
0x180008eea  mov     [rsp+14F0h+var_14C8], ecx
0x180008eee  mov     [rsp+14F0h+var_14C4], eax
0x180008ef2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008ef7  cmp     dword ptr [rbx+8], 1
0x180008efb  mov     edi, eax
0x180008efd  lea     eax, [r13+8]
0x180008f01  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180008f09  mov     ecx, r13d
0x180008f0c  cmovz   ecx, eax
0x180008f0f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008f13  lea     ecx, [rax-7]
0x180008f16  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180008f1e  inc     ecx
0x180008f20  mov     [rsp+14F0h+var_14B8], r13
0x180008f25  mov     [rsp+14F0h+var_14C0], ecx
0x180008f29  call    cs:__imp_GetCurrentThreadId
0x180008f30  nop     dword ptr [rax+rax+00h]
0x180008f35  xorps   xmm0, xmm0
0x180008f38  mov     [rsp+14F0h+var_1498], r15
0x180008f3d  mov     [rsp+14F0h+var_14B0], eax
0x180008f41  xorps   xmm1, xmm1
0x180008f44  xor     eax, eax
0x180008f46  mov     [rsp+14F0h+var_1490], r14d
0x180008f4b  mov     [rbp+13F0h+var_1458], rax
0x180008f4f  mov     [rbp+13F0h+var_1470], rax
0x180008f53  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008f5a  mov     [rsp+14F0h+var_148C], edi
0x180008f5e  mov     [rsp+14F0h+var_14A8], r13
0x180008f63  mov     [rsp+14F0h+var_14A0], r13
0x180008f68  mov     [rbp+13F0h+var_1448], rsi
0x180008f6c  mov     [rbp+13F0h+var_1440], r12
0x180008f70  mov     [rsp+14F0h+var_1488], r13
0x180008f75  movups  [rbp+13F0h+var_1468], xmm0
0x180008f79  movups  [rsp+14F0h+var_1480], xmm1
0x180008f7e  test    rax, rax
0x180008f81  jz      short loc_180008F8E
0x180008f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f88  mov     [rbp+13F0h+var_1450], rax
0x180008f8c  jmp     short loc_180008F92
0x180008f8e  mov     [rbp+13F0h+var_1450], r13
0x180008f92  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008f99  test    rax, rax
0x180008f9c  jz      short loc_180008FA8
0x180008f9e  lea     rcx, [rsp+14F0h+var_14D0]
0x180008fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fa8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008faf  test    rax, rax
0x180008fb2  jz      short loc_180008FC8
0x180008fb4  mov     r8d, 400h
0x180008fba  lea     rdx, [rbp+13F0h+var_1430]
0x180008fbe  lea     rcx, [rsp+14F0h+var_14D0]
0x180008fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008fcf  test    rax, rax
0x180008fd2  jz      short loc_180008FDE
0x180008fd4  lea     rcx, [rsp+14F0h+var_14D0]
0x180008fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fde  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008fe5  test    rax, rax
0x180008fe8  jz      short loc_180008FFB
0x180008fea  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008fef  jnz     short loc_180008FFB
0x180008ff1  lea     rcx, [rsp+14F0h+var_14D0]
0x180008ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ffb  cmp     [rsp+14F0h+var_14C8], r13d
0x180009000  jl      short loc_180009014
0x180009002  mov     ecx, 8000FFFFh; this
0x180009007  mov     [rsp+14F0h+var_14C8], ecx
0x18000900b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009010  mov     [rsp+14F0h+var_14C4], eax
0x180009014  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000901b  jnz     short loc_180009042
0x18000901d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009024  test    rax, rax
0x180009027  jz      short loc_180009032
0x180009029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000902e  test    al, al
0x180009030  jmp     short loc_180009040
0x180009032  call    cs:__imp_IsDebuggerPresent
0x180009039  nop     dword ptr [rax+rax+00h]
0x18000903e  test    eax, eax
0x180009040  jz      short loc_180009049
0x180009042  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009047  jz      short loc_18000906F
0x180009049  mov     rax, cs:g_pfnResultLoggingCallback
0x180009050  test    rax, rax
0x180009053  jz      short loc_1800090CE
0x180009055  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000905c  jnz     short loc_1800090CE
0x18000905e  xor     r8d, r8d
0x180009061  lea     rcx, [rsp+14F0h+var_14D0]
0x180009066  xor     edx, edx
0x180009068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000906d  jmp     short loc_1800090CE
0x18000906f  mov     rax, cs:g_pfnResultLoggingCallback
0x180009076  mov     ebx, 800h
0x18000907b  test    rax, rax
0x18000907e  jz      short loc_18000909D
0x180009080  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009087  jnz     short loc_18000909D
0x180009089  mov     r8d, ebx
0x18000908c  lea     rdx, [rbp+13F0h+OutputString]
0x180009093  lea     rcx, [rsp+14F0h+var_14D0]
0x180009098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000909d  cmp     [rbp+13F0h+OutputString], r13w
0x1800090a5  jnz     short loc_1800090BB
0x1800090a7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800090ac  mov     rdx, rbx; unsigned __int16 *
0x1800090af  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800090b6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800090bb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800090c2  call    cs:__imp_OutputDebugStringW
0x1800090c9  nop     dword ptr [rax+rax+00h]
0x1800090ce  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800090d3  jnz     short loc_1800090DE
0x1800090d5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800090dc  jz      short loc_1800090EF
0x1800090de  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800090e5  test    rax, rax
0x1800090e8  jz      short loc_1800090EF
0x1800090ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ef  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800090f4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
