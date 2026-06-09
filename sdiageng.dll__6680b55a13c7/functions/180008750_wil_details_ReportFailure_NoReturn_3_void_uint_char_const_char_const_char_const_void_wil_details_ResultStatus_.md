# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180008750`
- end: `0x1800089b2`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800084f4`

## callees

- `0x180008750`
- `0x18000b984`
- `0x18000cb7c`
- `0x18000eb00`
- `0x1800122f0`
- `0x180029882`
- `0x180029980`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800087f2`
- `KERNEL32!GetCurrentThreadId` at `0x1800087f2`
- `KERNEL32!IsDebuggerPresent` at `0x1800088f5`
- `KERNEL32!IsDebuggerPresent` at `0x1800088f5`
- `KERNEL32!OutputDebugStringW` at `0x18000897f`
- `KERNEL32!OutputDebugStringW` at `0x18000897f`

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
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180008750  mov     [rsp-8+arg_18], rbx
0x180008755  push    rbp
0x180008756  push    rsi
0x180008757  push    rdi
0x180008758  push    r12
0x18000875a  push    r13
0x18000875c  push    r14
0x18000875e  push    r15
0x180008760  lea     rbp, [rsp-13C0h]
0x180008768  mov     eax, 14C0h
0x18000876d  call    _alloca_probe
0x180008772  sub     rsp, rax
0x180008775  mov     r15, r8
0x180008778  mov     r14d, edx
0x18000877b  mov     r12, rcx
0x18000877e  mov     rsi, [rbp+13F0h+arg_28]
0x180008785  xor     edx, edx; Val
0x180008787  mov     r8d, 98h; Size
0x18000878d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008792  call    memset_0
0x180008797  nop
0x180008798  xor     r13d, r13d
0x18000879b  mov     [rbp+13F0h+OutputString], r13w
0x1800087a3  mov     [rbp+13F0h+var_1430], r13b
0x1800087a7  mov     rbx, [rbp+13F0h+arg_30]
0x1800087ae  mov     ecx, [rbx]; this
0x1800087b0  mov     [rsp+14F0h+var_14C8], ecx
0x1800087b4  mov     eax, [rbx+4]
0x1800087b7  mov     [rsp+14F0h+var_14C4], eax
0x1800087bb  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800087c0  mov     edi, eax
0x1800087c2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800087ca  mov     ecx, r13d
0x1800087cd  lea     eax, [r13+8]
0x1800087d1  cmp     dword ptr [rbx+8], 1
0x1800087d5  cmovz   ecx, eax
0x1800087d8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800087dc  lea     ecx, [rax-7]
0x1800087df  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800087e7  inc     ecx
0x1800087e9  mov     [rsp+14F0h+var_14C0], ecx
0x1800087ed  mov     [rsp+14F0h+var_14B8], r13
0x1800087f2  call    cs:__imp_GetCurrentThreadId
0x1800087f8  mov     [rsp+14F0h+var_14B0], eax
0x1800087fc  mov     [rsp+14F0h+var_1498], r15
0x180008801  mov     [rsp+14F0h+var_1490], r14d
0x180008806  mov     [rsp+14F0h+var_148C], edi
0x18000880a  mov     [rsp+14F0h+var_14A8], r13
0x18000880f  mov     [rsp+14F0h+var_14A0], r13
0x180008814  mov     [rbp+13F0h+var_1448], rsi
0x180008818  mov     [rbp+13F0h+var_1440], r12
0x18000881c  mov     [rsp+14F0h+var_1488], r13
0x180008821  xorps   xmm0, xmm0
0x180008824  xor     eax, eax
0x180008826  movups  [rbp+13F0h+var_1468], xmm0
0x18000882a  mov     [rbp+13F0h+var_1458], rax
0x18000882e  xorps   xmm1, xmm1
0x180008831  movups  [rsp+14F0h+var_1480], xmm1
0x180008836  mov     [rbp+13F0h+var_1470], rax
0x18000883a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008841  test    rax, rax
0x180008844  jz      short loc_180008851
0x180008846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000884b  mov     [rbp+13F0h+var_1450], rax
0x18000884f  jmp     short loc_180008855
0x180008851  mov     [rbp+13F0h+var_1450], r13
0x180008855  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000885c  test    rax, rax
0x18000885f  jz      short loc_18000886B
0x180008861  lea     rcx, [rsp+14F0h+var_14D0]
0x180008866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000886b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008872  test    rax, rax
0x180008875  jz      short loc_18000888B
0x180008877  mov     r8d, 400h
0x18000887d  lea     rdx, [rbp+13F0h+var_1430]
0x180008881  lea     rcx, [rsp+14F0h+var_14D0]
0x180008886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000888b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008892  test    rax, rax
0x180008895  jz      short loc_1800088A1
0x180008897  lea     rcx, [rsp+14F0h+var_14D0]
0x18000889c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088a1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800088a8  test    rax, rax
0x1800088ab  jz      short loc_1800088BE
0x1800088ad  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800088b2  jnz     short loc_1800088BE
0x1800088b4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800088b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088be  cmp     [rsp+14F0h+var_14C8], r13d
0x1800088c3  jl      short loc_1800088D7
0x1800088c5  mov     ecx, 8000FFFFh; this
0x1800088ca  mov     [rsp+14F0h+var_14C8], ecx
0x1800088ce  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800088d3  mov     [rsp+14F0h+var_14C4], eax
0x1800088d7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800088de  jnz     short loc_1800088FF
0x1800088e0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800088e7  test    rax, rax
0x1800088ea  jz      short loc_1800088F5
0x1800088ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f1  test    al, al
0x1800088f3  jmp     short loc_1800088FD
0x1800088f5  call    cs:__imp_IsDebuggerPresent
0x1800088fb  test    eax, eax
0x1800088fd  jz      short loc_180008906
0x1800088ff  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008904  jz      short loc_18000892C
0x180008906  mov     rax, cs:g_pfnResultLoggingCallback
0x18000890d  test    rax, rax
0x180008910  jz      short loc_180008985
0x180008912  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008919  jnz     short loc_180008985
0x18000891b  xor     r8d, r8d
0x18000891e  xor     edx, edx
0x180008920  lea     rcx, [rsp+14F0h+var_14D0]
0x180008925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000892a  jmp     short loc_180008985
0x18000892c  mov     ebx, 800h
0x180008931  mov     rax, cs:g_pfnResultLoggingCallback
0x180008938  test    rax, rax
0x18000893b  jz      short loc_18000895A
0x18000893d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008944  jnz     short loc_18000895A
0x180008946  mov     r8d, ebx
0x180008949  lea     rdx, [rbp+13F0h+OutputString]
0x180008950  lea     rcx, [rsp+14F0h+var_14D0]
0x180008955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000895a  cmp     [rbp+13F0h+OutputString], r13w
0x180008962  jnz     short loc_180008978
0x180008964  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008969  mov     rdx, rbx; unsigned __int16 *
0x18000896c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008973  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008978  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000897f  call    cs:__imp_OutputDebugStringW
0x180008985  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000898a  jnz     short loc_180008995
0x18000898c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180008993  jz      short loc_1800089A7
0x180008995  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000899c  test    rax, rax
0x18000899f  jz      short loc_1800089A7
0x1800089a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089a6  nop
0x1800089a7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800089ac  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
