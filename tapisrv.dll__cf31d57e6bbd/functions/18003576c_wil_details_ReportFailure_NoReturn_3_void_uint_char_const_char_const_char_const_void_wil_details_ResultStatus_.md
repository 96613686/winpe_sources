# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18003576c`
- end: `0x1800359cc`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180035538`

## callees

- `0x180001f50`
- `0x18003576c`
- `0x1800380e4`
- `0x180038ebc`
- `0x18003a050`
- `0x18003c250`
- `0x18003fb10`
- `0x180040010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180035910`
- `KERNEL32!IsDebuggerPresent` at `0x180035910`
- `KERNEL32!OutputDebugStringW` at `0x18003599a`
- `KERNEL32!OutputDebugStringW` at `0x18003599a`
- `KERNEL32!GetCurrentThreadId` at `0x18003580d`
- `KERNEL32!GetCurrentThreadId` at `0x18003580d`

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
0x18003576c  mov     [rsp-8+arg_18], rbx
0x180035771  push    rbp
0x180035772  push    rsi
0x180035773  push    rdi
0x180035774  push    r12
0x180035776  push    r13
0x180035778  push    r14
0x18003577a  push    r15
0x18003577c  lea     rbp, [rsp-13C0h]
0x180035784  mov     eax, 14C0h
0x180035789  call    _alloca_probe
0x18003578e  sub     rsp, rax
0x180035791  mov     rsi, [rbp+13F0h+arg_28]
0x180035798  mov     r15, r8
0x18003579b  mov     r14d, edx
0x18003579e  mov     r12, rcx
0x1800357a1  xor     edx, edx; Val
0x1800357a3  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800357a8  mov     r8d, 98h; Size
0x1800357ae  call    memset_0
0x1800357b3  mov     rbx, [rbp+13F0h+arg_30]
0x1800357ba  xor     r13d, r13d
0x1800357bd  mov     [rbp+13F0h+OutputString], r13w
0x1800357c5  mov     [rbp+13F0h+var_1430], r13b
0x1800357c9  mov     ecx, [rbx]; this
0x1800357cb  mov     eax, [rbx+4]
0x1800357ce  mov     [rsp+14F0h+var_14C8], ecx
0x1800357d2  mov     [rsp+14F0h+var_14C4], eax
0x1800357d6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800357db  cmp     dword ptr [rbx+8], 1
0x1800357df  mov     edi, eax
0x1800357e1  lea     eax, [r13+8]
0x1800357e5  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800357ed  mov     ecx, r13d
0x1800357f0  cmovz   ecx, eax
0x1800357f3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800357f7  lea     ecx, [rax-7]
0x1800357fa  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180035802  inc     ecx
0x180035804  mov     [rsp+14F0h+var_14B8], r13
0x180035809  mov     [rsp+14F0h+var_14C0], ecx
0x18003580d  call    cs:__imp_GetCurrentThreadId
0x180035813  xorps   xmm0, xmm0
0x180035816  mov     [rsp+14F0h+var_1498], r15
0x18003581b  mov     [rsp+14F0h+var_14B0], eax
0x18003581f  xorps   xmm1, xmm1
0x180035822  xor     eax, eax
0x180035824  mov     [rsp+14F0h+var_1490], r14d
0x180035829  mov     [rbp+13F0h+var_1458], rax
0x18003582d  mov     [rbp+13F0h+var_1470], rax
0x180035831  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180035838  mov     [rsp+14F0h+var_148C], edi
0x18003583c  mov     [rsp+14F0h+var_14A8], r13
0x180035841  mov     [rsp+14F0h+var_14A0], r13
0x180035846  mov     [rbp+13F0h+var_1448], rsi
0x18003584a  mov     [rbp+13F0h+var_1440], r12
0x18003584e  mov     [rsp+14F0h+var_1488], r13
0x180035853  movups  [rbp+13F0h+var_1468], xmm0
0x180035857  movups  [rsp+14F0h+var_1480], xmm1
0x18003585c  test    rax, rax
0x18003585f  jz      short loc_18003586C
0x180035861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035866  mov     [rbp+13F0h+var_1450], rax
0x18003586a  jmp     short loc_180035870
0x18003586c  mov     [rbp+13F0h+var_1450], r13
0x180035870  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180035877  test    rax, rax
0x18003587a  jz      short loc_180035886
0x18003587c  lea     rcx, [rsp+14F0h+var_14D0]
0x180035881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035886  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003588d  test    rax, rax
0x180035890  jz      short loc_1800358A6
0x180035892  mov     r8d, 400h
0x180035898  lea     rdx, [rbp+13F0h+var_1430]
0x18003589c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800358a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358a6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800358ad  test    rax, rax
0x1800358b0  jz      short loc_1800358BC
0x1800358b2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800358b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358bc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800358c3  test    rax, rax
0x1800358c6  jz      short loc_1800358D9
0x1800358c8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800358cd  jnz     short loc_1800358D9
0x1800358cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800358d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358d9  cmp     [rsp+14F0h+var_14C8], r13d
0x1800358de  jl      short loc_1800358F2
0x1800358e0  mov     ecx, 8000FFFFh; this
0x1800358e5  mov     [rsp+14F0h+var_14C8], ecx
0x1800358e9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800358ee  mov     [rsp+14F0h+var_14C4], eax
0x1800358f2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800358f9  jnz     short loc_18003591A
0x1800358fb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180035902  test    rax, rax
0x180035905  jz      short loc_180035910
0x180035907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003590c  test    al, al
0x18003590e  jmp     short loc_180035918
0x180035910  call    cs:__imp_IsDebuggerPresent
0x180035916  test    eax, eax
0x180035918  jz      short loc_180035921
0x18003591a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003591f  jz      short loc_180035947
0x180035921  mov     rax, cs:g_pfnResultLoggingCallback
0x180035928  test    rax, rax
0x18003592b  jz      short loc_1800359A0
0x18003592d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180035934  jnz     short loc_1800359A0
0x180035936  xor     r8d, r8d
0x180035939  lea     rcx, [rsp+14F0h+var_14D0]
0x18003593e  xor     edx, edx
0x180035940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035945  jmp     short loc_1800359A0
0x180035947  mov     rax, cs:g_pfnResultLoggingCallback
0x18003594e  mov     ebx, 800h
0x180035953  test    rax, rax
0x180035956  jz      short loc_180035975
0x180035958  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18003595f  jnz     short loc_180035975
0x180035961  mov     r8d, ebx
0x180035964  lea     rdx, [rbp+13F0h+OutputString]
0x18003596b  lea     rcx, [rsp+14F0h+var_14D0]
0x180035970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035975  cmp     [rbp+13F0h+OutputString], r13w
0x18003597d  jnz     short loc_180035993
0x18003597f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180035984  mov     rdx, rbx; unsigned __int16 *
0x180035987  lea     rcx, [rbp+13F0h+OutputString]; this
0x18003598e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180035993  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18003599a  call    cs:__imp_OutputDebugStringW
0x1800359a0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800359a5  jnz     short loc_1800359B0
0x1800359a7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800359ae  jz      short loc_1800359C1
0x1800359b0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800359b7  test    rax, rax
0x1800359ba  jz      short loc_1800359C1
0x1800359bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359c1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800359c6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
