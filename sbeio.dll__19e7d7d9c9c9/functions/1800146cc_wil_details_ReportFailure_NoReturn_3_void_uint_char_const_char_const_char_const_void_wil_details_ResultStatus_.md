# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800146cc`
- end: `0x180014933`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800144a8`

## callees

- `0x180001f1c`
- `0x1800146cc`
- `0x18001c244`
- `0x18001ccd8`
- `0x18001fa90`
- `0x180026ea0`
- `0x18002a010`
- `0x18002b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180014901`
- `KERNEL32!OutputDebugStringW` at `0x180014901`
- `KERNEL32!IsDebuggerPresent` at `0x180014877`
- `KERNEL32!IsDebuggerPresent` at `0x180014877`
- `KERNEL32!GetCurrentThreadId` at `0x18001476d`
- `KERNEL32!GetCurrentThreadId` at `0x18001476d`

## string_xrefs

- `0x180014782`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800146cc  mov     [rsp-8+arg_10], rbx
0x1800146d1  mov     [rsp-8+arg_18], rsi
0x1800146d6  push    rbp
0x1800146d7  push    rdi
0x1800146d8  push    r12
0x1800146da  push    r14
0x1800146dc  push    r15
0x1800146de  lea     rbp, [rsp-13C0h]
0x1800146e6  mov     eax, 14C0h
0x1800146eb  call    _alloca_probe
0x1800146f0  sub     rsp, rax
0x1800146f3  mov     rsi, [rbp+13E0h+arg_28]
0x1800146fa  mov     r14d, edx
0x1800146fd  mov     r15, rcx
0x180014700  xor     edx, edx; Val
0x180014702  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180014707  mov     r8d, 98h; Size
0x18001470d  call    memset_0
0x180014712  mov     rbx, [rbp+13E0h+arg_30]
0x180014719  xor     r12d, r12d
0x18001471c  mov     [rbp+13E0h+OutputString], r12w
0x180014724  mov     [rbp+13E0h+var_1420], r12b
0x180014728  mov     ecx, [rbx]; this
0x18001472a  mov     eax, [rbx+4]
0x18001472d  mov     [rsp+14E0h+var_14B8], ecx
0x180014731  mov     [rsp+14E0h+var_14B4], eax
0x180014735  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001473a  cmp     dword ptr [rbx+8], 1
0x18001473e  mov     edi, eax
0x180014740  lea     eax, [r12+8]
0x180014745  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x18001474d  mov     ecx, r12d
0x180014750  cmovz   ecx, eax
0x180014753  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180014757  lea     ecx, [rax-7]
0x18001475a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180014762  inc     ecx
0x180014764  mov     [rsp+14E0h+var_14A8], r12
0x180014769  mov     [rsp+14E0h+var_14B0], ecx
0x18001476d  call    cs:__imp_GetCurrentThreadId
0x180014773  xorps   xmm0, xmm0
0x180014776  mov     [rsp+14E0h+var_1480], r14d
0x18001477b  mov     [rsp+14E0h+var_14A0], eax
0x18001477f  xorps   xmm1, xmm1
0x180014782  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014789  mov     [rsp+14E0h+var_147C], edi
0x18001478d  mov     [rsp+14E0h+var_1488], rax
0x180014792  xor     eax, eax
0x180014794  mov     [rbp+13E0h+var_1448], rax
0x180014798  mov     [rbp+13E0h+var_1460], rax
0x18001479c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800147a3  mov     [rsp+14E0h+var_1498], r12
0x1800147a8  mov     [rsp+14E0h+var_1490], r12
0x1800147ad  mov     [rbp+13E0h+var_1438], rsi
0x1800147b1  mov     [rbp+13E0h+var_1430], r15
0x1800147b5  mov     [rsp+14E0h+var_1478], r12
0x1800147ba  movups  [rbp+13E0h+var_1458], xmm0
0x1800147be  movups  [rsp+14E0h+var_1470], xmm1
0x1800147c3  test    rax, rax
0x1800147c6  jz      short loc_1800147D3
0x1800147c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147cd  mov     [rbp+13E0h+var_1440], rax
0x1800147d1  jmp     short loc_1800147D7
0x1800147d3  mov     [rbp+13E0h+var_1440], r12
0x1800147d7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800147de  test    rax, rax
0x1800147e1  jz      short loc_1800147ED
0x1800147e3  lea     rcx, [rsp+14E0h+var_14C0]
0x1800147e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800147f4  test    rax, rax
0x1800147f7  jz      short loc_18001480D
0x1800147f9  mov     r8d, 400h
0x1800147ff  lea     rdx, [rbp+13E0h+var_1420]
0x180014803  lea     rcx, [rsp+14E0h+var_14C0]
0x180014808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001480d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014814  test    rax, rax
0x180014817  jz      short loc_180014823
0x180014819  lea     rcx, [rsp+14E0h+var_14C0]
0x18001481e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014823  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001482a  test    rax, rax
0x18001482d  jz      short loc_180014840
0x18001482f  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180014834  jnz     short loc_180014840
0x180014836  lea     rcx, [rsp+14E0h+var_14C0]
0x18001483b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014840  cmp     [rsp+14E0h+var_14B8], r12d
0x180014845  jl      short loc_180014859
0x180014847  mov     ecx, 8000FFFFh; this
0x18001484c  mov     [rsp+14E0h+var_14B8], ecx
0x180014850  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180014855  mov     [rsp+14E0h+var_14B4], eax
0x180014859  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180014860  jnz     short loc_180014881
0x180014862  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180014869  test    rax, rax
0x18001486c  jz      short loc_180014877
0x18001486e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014873  test    al, al
0x180014875  jmp     short loc_18001487F
0x180014877  call    cs:__imp_IsDebuggerPresent
0x18001487d  test    eax, eax
0x18001487f  jz      short loc_180014888
0x180014881  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180014886  jz      short loc_1800148AE
0x180014888  mov     rax, cs:g_pfnResultLoggingCallback
0x18001488f  test    rax, rax
0x180014892  jz      short loc_180014907
0x180014894  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001489b  jnz     short loc_180014907
0x18001489d  xor     r8d, r8d
0x1800148a0  lea     rcx, [rsp+14E0h+var_14C0]
0x1800148a5  xor     edx, edx
0x1800148a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148ac  jmp     short loc_180014907
0x1800148ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800148b5  mov     ebx, 800h
0x1800148ba  test    rax, rax
0x1800148bd  jz      short loc_1800148DC
0x1800148bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800148c6  jnz     short loc_1800148DC
0x1800148c8  mov     r8d, ebx
0x1800148cb  lea     rdx, [rbp+13E0h+OutputString]
0x1800148d2  lea     rcx, [rsp+14E0h+var_14C0]
0x1800148d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148dc  cmp     [rbp+13E0h+OutputString], r12w
0x1800148e4  jnz     short loc_1800148FA
0x1800148e6  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800148eb  mov     rdx, rbx; unsigned __int16 *
0x1800148ee  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800148f5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800148fa  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180014901  call    cs:__imp_OutputDebugStringW
0x180014907  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18001490c  jnz     short loc_180014917
0x18001490e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180014915  jz      short loc_180014928
0x180014917  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001491e  test    rax, rax
0x180014921  jz      short loc_180014928
0x180014923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014928  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18001492d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
