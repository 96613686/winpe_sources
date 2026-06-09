# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002e54`
- end: `0x1800030bb`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002c08`

## callees

- `0x180002e54`
- `0x180003fd4`
- `0x18000476c`
- `0x180004ea0`
- `0x180005830`
- `0x18001afe2`
- `0x18001b0e0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ef5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002fff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002fff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003089`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003089`

## string_xrefs

- `0x180002f0a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180002e54  mov     [rsp-8+arg_10], rbx
0x180002e59  mov     [rsp-8+arg_18], rsi
0x180002e5e  push    rbp
0x180002e5f  push    rdi
0x180002e60  push    r12
0x180002e62  push    r14
0x180002e64  push    r15
0x180002e66  lea     rbp, [rsp-13C0h]
0x180002e6e  mov     eax, 14C0h
0x180002e73  call    _alloca_probe
0x180002e78  sub     rsp, rax
0x180002e7b  mov     rsi, [rbp+13E0h+arg_28]
0x180002e82  mov     r14d, edx
0x180002e85  mov     r15, rcx
0x180002e88  xor     edx, edx; Val
0x180002e8a  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002e8f  mov     r8d, 98h; Size
0x180002e95  call    memset_0
0x180002e9a  mov     rbx, [rbp+13E0h+arg_30]
0x180002ea1  xor     r12d, r12d
0x180002ea4  mov     [rbp+13E0h+OutputString], r12w
0x180002eac  mov     [rbp+13E0h+var_1420], r12b
0x180002eb0  mov     ecx, [rbx]; this
0x180002eb2  mov     eax, [rbx+4]
0x180002eb5  mov     [rsp+14E0h+var_14B8], ecx
0x180002eb9  mov     [rsp+14E0h+var_14B4], eax
0x180002ebd  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002ec2  cmp     dword ptr [rbx+8], 1
0x180002ec6  mov     edi, eax
0x180002ec8  lea     eax, [r12+8]
0x180002ecd  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002ed5  mov     ecx, r12d
0x180002ed8  cmovz   ecx, eax
0x180002edb  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002edf  lea     ecx, [rax-7]
0x180002ee2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002eea  inc     ecx
0x180002eec  mov     [rsp+14E0h+var_14A8], r12
0x180002ef1  mov     [rsp+14E0h+var_14B0], ecx
0x180002ef5  call    cs:__imp_GetCurrentThreadId
0x180002efb  xorps   xmm0, xmm0
0x180002efe  mov     [rsp+14E0h+var_1480], r14d
0x180002f03  mov     [rsp+14E0h+var_14A0], eax
0x180002f07  xorps   xmm1, xmm1
0x180002f0a  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002f11  mov     [rsp+14E0h+var_147C], edi
0x180002f15  mov     [rsp+14E0h+var_1488], rax
0x180002f1a  xor     eax, eax
0x180002f1c  mov     [rbp+13E0h+var_1448], rax
0x180002f20  mov     [rbp+13E0h+var_1460], rax
0x180002f24  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002f2b  mov     [rsp+14E0h+var_1498], r12
0x180002f30  mov     [rsp+14E0h+var_1490], r12
0x180002f35  mov     [rbp+13E0h+var_1438], rsi
0x180002f39  mov     [rbp+13E0h+var_1430], r15
0x180002f3d  mov     [rsp+14E0h+var_1478], r12
0x180002f42  movups  [rbp+13E0h+var_1458], xmm0
0x180002f46  movups  [rsp+14E0h+var_1470], xmm1
0x180002f4b  test    rax, rax
0x180002f4e  jz      short loc_180002F5B
0x180002f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f55  mov     [rbp+13E0h+var_1440], rax
0x180002f59  jmp     short loc_180002F5F
0x180002f5b  mov     [rbp+13E0h+var_1440], r12
0x180002f5f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002f66  test    rax, rax
0x180002f69  jz      short loc_180002F75
0x180002f6b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f75  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002f7c  test    rax, rax
0x180002f7f  jz      short loc_180002F95
0x180002f81  mov     r8d, 400h
0x180002f87  lea     rdx, [rbp+13E0h+var_1420]
0x180002f8b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f95  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002f9c  test    rax, rax
0x180002f9f  jz      short loc_180002FAB
0x180002fa1  lea     rcx, [rsp+14E0h+var_14C0]
0x180002fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002fb2  test    rax, rax
0x180002fb5  jz      short loc_180002FC8
0x180002fb7  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002fbc  jnz     short loc_180002FC8
0x180002fbe  lea     rcx, [rsp+14E0h+var_14C0]
0x180002fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc8  cmp     [rsp+14E0h+var_14B8], r12d
0x180002fcd  jl      short loc_180002FE1
0x180002fcf  mov     ecx, 8000FFFFh; this
0x180002fd4  mov     [rsp+14E0h+var_14B8], ecx
0x180002fd8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002fdd  mov     [rsp+14E0h+var_14B4], eax
0x180002fe1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002fe8  jnz     short loc_180003009
0x180002fea  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ff1  test    rax, rax
0x180002ff4  jz      short loc_180002FFF
0x180002ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ffb  test    al, al
0x180002ffd  jmp     short loc_180003007
0x180002fff  call    cs:__imp_IsDebuggerPresent
0x180003005  test    eax, eax
0x180003007  jz      short loc_180003010
0x180003009  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000300e  jz      short loc_180003036
0x180003010  mov     rax, cs:g_pfnResultLoggingCallback
0x180003017  test    rax, rax
0x18000301a  jz      short loc_18000308F
0x18000301c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003023  jnz     short loc_18000308F
0x180003025  xor     r8d, r8d
0x180003028  lea     rcx, [rsp+14E0h+var_14C0]
0x18000302d  xor     edx, edx
0x18000302f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003034  jmp     short loc_18000308F
0x180003036  mov     rax, cs:g_pfnResultLoggingCallback
0x18000303d  mov     ebx, 800h
0x180003042  test    rax, rax
0x180003045  jz      short loc_180003064
0x180003047  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000304e  jnz     short loc_180003064
0x180003050  mov     r8d, ebx
0x180003053  lea     rdx, [rbp+13E0h+OutputString]
0x18000305a  lea     rcx, [rsp+14E0h+var_14C0]
0x18000305f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003064  cmp     [rbp+13E0h+OutputString], r12w
0x18000306c  jnz     short loc_180003082
0x18000306e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180003073  mov     rdx, rbx; unsigned __int16 *
0x180003076  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000307d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003082  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180003089  call    cs:__imp_OutputDebugStringW
0x18000308f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180003094  jnz     short loc_18000309F
0x180003096  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000309d  jz      short loc_1800030B0
0x18000309f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800030a6  test    rax, rax
0x1800030a9  jz      short loc_1800030B0
0x1800030ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b0  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800030b5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
