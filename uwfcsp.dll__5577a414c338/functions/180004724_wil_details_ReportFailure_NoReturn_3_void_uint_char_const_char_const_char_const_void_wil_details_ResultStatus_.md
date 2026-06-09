# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004724`
- end: `0x18000498b`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800044d0`

## callees

- `0x180004724`
- `0x180005794`
- `0x180005fd4`
- `0x180006700`
- `0x1800070a0`
- `0x18001a1d6`
- `0x18001a2d0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047c5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004959`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004959`

## string_xrefs

- `0x1800047da`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
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
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
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
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
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
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180004724  mov     [rsp-8+arg_10], rbx
0x180004729  mov     [rsp-8+arg_18], rsi
0x18000472e  push    rbp
0x18000472f  push    rdi
0x180004730  push    r12
0x180004732  push    r14
0x180004734  push    r15
0x180004736  lea     rbp, [rsp-13C0h]
0x18000473e  mov     eax, 14C0h
0x180004743  call    _alloca_probe
0x180004748  sub     rsp, rax
0x18000474b  mov     rsi, [rbp+13E0h+arg_28]
0x180004752  mov     r14d, edx
0x180004755  mov     r15, rcx
0x180004758  xor     edx, edx; Val
0x18000475a  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000475f  mov     r8d, 98h; Size
0x180004765  call    memset_0
0x18000476a  mov     rbx, [rbp+13E0h+arg_30]
0x180004771  xor     r12d, r12d
0x180004774  mov     [rbp+13E0h+OutputString], r12w
0x18000477c  mov     [rbp+13E0h+var_1420], r12b
0x180004780  mov     ecx, [rbx]; this
0x180004782  mov     eax, [rbx+4]
0x180004785  mov     [rsp+14E0h+var_14B8], ecx
0x180004789  mov     [rsp+14E0h+var_14B4], eax
0x18000478d  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004792  cmp     dword ptr [rbx+8], 1
0x180004796  mov     edi, eax
0x180004798  lea     eax, [r12+8]
0x18000479d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800047a5  mov     ecx, r12d
0x1800047a8  cmovz   ecx, eax
0x1800047ab  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800047af  lea     ecx, [rax-7]
0x1800047b2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800047ba  inc     ecx
0x1800047bc  mov     [rsp+14E0h+var_14A8], r12
0x1800047c1  mov     [rsp+14E0h+var_14B0], ecx
0x1800047c5  call    cs:__imp_GetCurrentThreadId
0x1800047cb  xorps   xmm0, xmm0
0x1800047ce  mov     [rsp+14E0h+var_1480], r14d
0x1800047d3  mov     [rsp+14E0h+var_14A0], eax
0x1800047d7  xorps   xmm1, xmm1
0x1800047da  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800047e1  mov     [rsp+14E0h+var_147C], edi
0x1800047e5  mov     [rsp+14E0h+var_1488], rax
0x1800047ea  xor     eax, eax
0x1800047ec  mov     [rbp+13E0h+var_1448], rax
0x1800047f0  mov     [rbp+13E0h+var_1460], rax
0x1800047f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800047fb  mov     [rsp+14E0h+var_1498], r12
0x180004800  mov     [rsp+14E0h+var_1490], r12
0x180004805  mov     [rbp+13E0h+var_1438], rsi
0x180004809  mov     [rbp+13E0h+var_1430], r15
0x18000480d  mov     [rsp+14E0h+var_1478], r12
0x180004812  movups  [rbp+13E0h+var_1458], xmm0
0x180004816  movups  [rsp+14E0h+var_1470], xmm1
0x18000481b  test    rax, rax
0x18000481e  jz      short loc_18000482B
0x180004820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004825  mov     [rbp+13E0h+var_1440], rax
0x180004829  jmp     short loc_18000482F
0x18000482b  mov     [rbp+13E0h+var_1440], r12
0x18000482f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004836  test    rax, rax
0x180004839  jz      short loc_180004845
0x18000483b  lea     rcx, [rsp+14E0h+var_14C0]
0x180004840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004845  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000484c  test    rax, rax
0x18000484f  jz      short loc_180004865
0x180004851  mov     r8d, 400h
0x180004857  lea     rdx, [rbp+13E0h+var_1420]
0x18000485b  lea     rcx, [rsp+14E0h+var_14C0]
0x180004860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004865  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000486c  test    rax, rax
0x18000486f  jz      short loc_18000487B
0x180004871  lea     rcx, [rsp+14E0h+var_14C0]
0x180004876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004882  test    rax, rax
0x180004885  jz      short loc_180004898
0x180004887  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000488c  jnz     short loc_180004898
0x18000488e  lea     rcx, [rsp+14E0h+var_14C0]
0x180004893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004898  cmp     [rsp+14E0h+var_14B8], r12d
0x18000489d  jl      short loc_1800048B1
0x18000489f  mov     ecx, 8000FFFFh; this
0x1800048a4  mov     [rsp+14E0h+var_14B8], ecx
0x1800048a8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800048ad  mov     [rsp+14E0h+var_14B4], eax
0x1800048b1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800048b8  jnz     short loc_1800048D9
0x1800048ba  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800048c1  test    rax, rax
0x1800048c4  jz      short loc_1800048CF
0x1800048c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048cb  test    al, al
0x1800048cd  jmp     short loc_1800048D7
0x1800048cf  call    cs:__imp_IsDebuggerPresent
0x1800048d5  test    eax, eax
0x1800048d7  jz      short loc_1800048E0
0x1800048d9  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800048de  jz      short loc_180004906
0x1800048e0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048e7  test    rax, rax
0x1800048ea  jz      short loc_18000495F
0x1800048ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800048f3  jnz     short loc_18000495F
0x1800048f5  xor     r8d, r8d
0x1800048f8  lea     rcx, [rsp+14E0h+var_14C0]
0x1800048fd  xor     edx, edx
0x1800048ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004904  jmp     short loc_18000495F
0x180004906  mov     rax, cs:g_pfnResultLoggingCallback
0x18000490d  mov     ebx, 800h
0x180004912  test    rax, rax
0x180004915  jz      short loc_180004934
0x180004917  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000491e  jnz     short loc_180004934
0x180004920  mov     r8d, ebx
0x180004923  lea     rdx, [rbp+13E0h+OutputString]
0x18000492a  lea     rcx, [rsp+14E0h+var_14C0]
0x18000492f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004934  cmp     [rbp+13E0h+OutputString], r12w
0x18000493c  jnz     short loc_180004952
0x18000493e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180004943  mov     rdx, rbx; unsigned __int16 *
0x180004946  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000494d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004952  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180004959  call    cs:__imp_OutputDebugStringW
0x18000495f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180004964  jnz     short loc_18000496F
0x180004966  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000496d  jz      short loc_180004980
0x18000496f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004976  test    rax, rax
0x180004979  jz      short loc_180004980
0x18000497b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004980  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180004985  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
