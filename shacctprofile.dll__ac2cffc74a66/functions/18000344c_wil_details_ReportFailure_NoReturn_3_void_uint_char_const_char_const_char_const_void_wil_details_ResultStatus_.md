# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000344c`
- end: `0x1800036b3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003200`

## callees

- `0x180002b8e`
- `0x18000344c`
- `0x1800044d4`
- `0x180004c6c`
- `0x180005390`
- `0x180005cd0`
- `0x1800096d0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034ed`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003681`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003681`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800035f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800035f7`

## string_xrefs

- `0x180003502`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000344c  mov     [rsp-8+arg_10], rbx
0x180003451  mov     [rsp-8+arg_18], rsi
0x180003456  push    rbp
0x180003457  push    rdi
0x180003458  push    r12
0x18000345a  push    r14
0x18000345c  push    r15
0x18000345e  lea     rbp, [rsp-13C0h]
0x180003466  mov     eax, 14C0h
0x18000346b  call    _alloca_probe
0x180003470  sub     rsp, rax
0x180003473  mov     rsi, [rbp+13E0h+arg_28]
0x18000347a  mov     r14d, edx
0x18000347d  mov     r15, rcx
0x180003480  xor     edx, edx; Val
0x180003482  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180003487  mov     r8d, 98h; Size
0x18000348d  call    memset_0
0x180003492  mov     rbx, [rbp+13E0h+arg_30]
0x180003499  xor     r12d, r12d
0x18000349c  mov     [rbp+13E0h+OutputString], r12w
0x1800034a4  mov     [rbp+13E0h+var_1420], r12b
0x1800034a8  mov     ecx, [rbx]; this
0x1800034aa  mov     eax, [rbx+4]
0x1800034ad  mov     [rsp+14E0h+var_14B8], ecx
0x1800034b1  mov     [rsp+14E0h+var_14B4], eax
0x1800034b5  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800034ba  cmp     dword ptr [rbx+8], 1
0x1800034be  mov     edi, eax
0x1800034c0  lea     eax, [r12+8]
0x1800034c5  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800034cd  mov     ecx, r12d
0x1800034d0  cmovz   ecx, eax
0x1800034d3  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800034d7  lea     ecx, [rax-7]
0x1800034da  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800034e2  inc     ecx
0x1800034e4  mov     [rsp+14E0h+var_14A8], r12
0x1800034e9  mov     [rsp+14E0h+var_14B0], ecx
0x1800034ed  call    cs:__imp_GetCurrentThreadId
0x1800034f3  xorps   xmm0, xmm0
0x1800034f6  mov     [rsp+14E0h+var_1480], r14d
0x1800034fb  mov     [rsp+14E0h+var_14A0], eax
0x1800034ff  xorps   xmm1, xmm1
0x180003502  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003509  mov     [rsp+14E0h+var_147C], edi
0x18000350d  mov     [rsp+14E0h+var_1488], rax
0x180003512  xor     eax, eax
0x180003514  mov     [rbp+13E0h+var_1448], rax
0x180003518  mov     [rbp+13E0h+var_1460], rax
0x18000351c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003523  mov     [rsp+14E0h+var_1498], r12
0x180003528  mov     [rsp+14E0h+var_1490], r12
0x18000352d  mov     [rbp+13E0h+var_1438], rsi
0x180003531  mov     [rbp+13E0h+var_1430], r15
0x180003535  mov     [rsp+14E0h+var_1478], r12
0x18000353a  movups  [rbp+13E0h+var_1458], xmm0
0x18000353e  movups  [rsp+14E0h+var_1470], xmm1
0x180003543  test    rax, rax
0x180003546  jz      short loc_180003553
0x180003548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354d  mov     [rbp+13E0h+var_1440], rax
0x180003551  jmp     short loc_180003557
0x180003553  mov     [rbp+13E0h+var_1440], r12
0x180003557  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000355e  test    rax, rax
0x180003561  jz      short loc_18000356D
0x180003563  lea     rcx, [rsp+14E0h+var_14C0]
0x180003568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000356d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003574  test    rax, rax
0x180003577  jz      short loc_18000358D
0x180003579  mov     r8d, 400h
0x18000357f  lea     rdx, [rbp+13E0h+var_1420]
0x180003583  lea     rcx, [rsp+14E0h+var_14C0]
0x180003588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000358d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003594  test    rax, rax
0x180003597  jz      short loc_1800035A3
0x180003599  lea     rcx, [rsp+14E0h+var_14C0]
0x18000359e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800035aa  test    rax, rax
0x1800035ad  jz      short loc_1800035C0
0x1800035af  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800035b4  jnz     short loc_1800035C0
0x1800035b6  lea     rcx, [rsp+14E0h+var_14C0]
0x1800035bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c0  cmp     [rsp+14E0h+var_14B8], r12d
0x1800035c5  jl      short loc_1800035D9
0x1800035c7  mov     ecx, 8000FFFFh; this
0x1800035cc  mov     [rsp+14E0h+var_14B8], ecx
0x1800035d0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800035d5  mov     [rsp+14E0h+var_14B4], eax
0x1800035d9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800035e0  jnz     short loc_180003601
0x1800035e2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800035e9  test    rax, rax
0x1800035ec  jz      short loc_1800035F7
0x1800035ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f3  test    al, al
0x1800035f5  jmp     short loc_1800035FF
0x1800035f7  call    cs:__imp_IsDebuggerPresent
0x1800035fd  test    eax, eax
0x1800035ff  jz      short loc_180003608
0x180003601  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003606  jz      short loc_18000362E
0x180003608  mov     rax, cs:g_pfnResultLoggingCallback
0x18000360f  test    rax, rax
0x180003612  jz      short loc_180003687
0x180003614  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000361b  jnz     short loc_180003687
0x18000361d  xor     r8d, r8d
0x180003620  lea     rcx, [rsp+14E0h+var_14C0]
0x180003625  xor     edx, edx
0x180003627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000362c  jmp     short loc_180003687
0x18000362e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003635  mov     ebx, 800h
0x18000363a  test    rax, rax
0x18000363d  jz      short loc_18000365C
0x18000363f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003646  jnz     short loc_18000365C
0x180003648  mov     r8d, ebx
0x18000364b  lea     rdx, [rbp+13E0h+OutputString]
0x180003652  lea     rcx, [rsp+14E0h+var_14C0]
0x180003657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000365c  cmp     [rbp+13E0h+OutputString], r12w
0x180003664  jnz     short loc_18000367A
0x180003666  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x18000366b  mov     rdx, rbx; unsigned __int16 *
0x18000366e  lea     rcx, [rbp+13E0h+OutputString]; this
0x180003675  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000367a  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180003681  call    cs:__imp_OutputDebugStringW
0x180003687  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000368c  jnz     short loc_180003697
0x18000368e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003695  jz      short loc_1800036A8
0x180003697  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000369e  test    rax, rax
0x1800036a1  jz      short loc_1800036A8
0x1800036a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036a8  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800036ad  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
