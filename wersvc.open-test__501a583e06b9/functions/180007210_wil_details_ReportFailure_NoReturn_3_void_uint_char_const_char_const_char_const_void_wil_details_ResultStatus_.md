# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180007210`
- end: `0x180007472`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006fac`

## callees

- `0x1800035e8`
- `0x180004fe4`
- `0x1800053cc`
- `0x180005730`
- `0x180006250`
- `0x180007210`
- `0x1800344f0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072b2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000743f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000743f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800073b5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800073b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v17, v15);
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
0x180007210  mov     [rsp-8+arg_18], rbx
0x180007215  push    rbp
0x180007216  push    rsi
0x180007217  push    rdi
0x180007218  push    r12
0x18000721a  push    r13
0x18000721c  push    r14
0x18000721e  push    r15
0x180007220  lea     rbp, [rsp-13C0h]
0x180007228  mov     eax, 14C0h
0x18000722d  call    _alloca_probe
0x180007232  sub     rsp, rax
0x180007235  mov     r15, r8
0x180007238  mov     r14d, edx
0x18000723b  mov     r12, rcx
0x18000723e  mov     rsi, [rbp+13F0h+arg_28]
0x180007245  xor     edx, edx; Val
0x180007247  mov     r8d, 98h; Size
0x18000724d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007252  call    memset_0
0x180007257  nop
0x180007258  xor     r13d, r13d
0x18000725b  mov     [rbp+13F0h+OutputString], r13w
0x180007263  mov     [rbp+13F0h+var_1430], r13b
0x180007267  mov     rbx, [rbp+13F0h+arg_30]
0x18000726e  mov     ecx, [rbx]; this
0x180007270  mov     [rsp+14F0h+var_14C8], ecx
0x180007274  mov     eax, [rbx+4]
0x180007277  mov     [rsp+14F0h+var_14C4], eax
0x18000727b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007280  mov     edi, eax
0x180007282  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000728a  mov     ecx, r13d
0x18000728d  lea     eax, [r13+8]
0x180007291  cmp     dword ptr [rbx+8], 1
0x180007295  cmovz   ecx, eax
0x180007298  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000729c  lea     ecx, [rax-7]
0x18000729f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800072a7  inc     ecx
0x1800072a9  mov     [rsp+14F0h+var_14C0], ecx
0x1800072ad  mov     [rsp+14F0h+var_14B8], r13
0x1800072b2  call    cs:__imp_GetCurrentThreadId
0x1800072b8  mov     [rsp+14F0h+var_14B0], eax
0x1800072bc  mov     [rsp+14F0h+var_1498], r15
0x1800072c1  mov     [rsp+14F0h+var_1490], r14d
0x1800072c6  mov     [rsp+14F0h+var_148C], edi
0x1800072ca  mov     [rsp+14F0h+var_14A8], r13
0x1800072cf  mov     [rsp+14F0h+var_14A0], r13
0x1800072d4  mov     [rbp+13F0h+var_1448], rsi
0x1800072d8  mov     [rbp+13F0h+var_1440], r12
0x1800072dc  mov     [rsp+14F0h+var_1488], r13
0x1800072e1  xorps   xmm0, xmm0
0x1800072e4  xor     eax, eax
0x1800072e6  movups  [rbp+13F0h+var_1468], xmm0
0x1800072ea  mov     [rbp+13F0h+var_1458], rax
0x1800072ee  xorps   xmm1, xmm1
0x1800072f1  movups  [rsp+14F0h+var_1480], xmm1
0x1800072f6  mov     [rbp+13F0h+var_1470], rax
0x1800072fa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007301  test    rax, rax
0x180007304  jz      short loc_180007311
0x180007306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000730b  mov     [rbp+13F0h+var_1450], rax
0x18000730f  jmp     short loc_180007315
0x180007311  mov     [rbp+13F0h+var_1450], r13
0x180007315  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000731c  test    rax, rax
0x18000731f  jz      short loc_18000732B
0x180007321  lea     rcx, [rsp+14F0h+var_14D0]
0x180007326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000732b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007332  test    rax, rax
0x180007335  jz      short loc_18000734B
0x180007337  mov     r8d, 400h
0x18000733d  lea     rdx, [rbp+13F0h+var_1430]
0x180007341  lea     rcx, [rsp+14F0h+var_14D0]
0x180007346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000734b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007352  test    rax, rax
0x180007355  jz      short loc_180007361
0x180007357  lea     rcx, [rsp+14F0h+var_14D0]
0x18000735c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007361  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007368  test    rax, rax
0x18000736b  jz      short loc_18000737E
0x18000736d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007372  jnz     short loc_18000737E
0x180007374  lea     rcx, [rsp+14F0h+var_14D0]
0x180007379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000737e  cmp     [rsp+14F0h+var_14C8], r13d
0x180007383  jl      short loc_180007397
0x180007385  mov     ecx, 8000FFFFh; this
0x18000738a  mov     [rsp+14F0h+var_14C8], ecx
0x18000738e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007393  mov     [rsp+14F0h+var_14C4], eax
0x180007397  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000739e  jnz     short loc_1800073BF
0x1800073a0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800073a7  test    rax, rax
0x1800073aa  jz      short loc_1800073B5
0x1800073ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b1  test    al, al
0x1800073b3  jmp     short loc_1800073BD
0x1800073b5  call    cs:__imp_IsDebuggerPresent
0x1800073bb  test    eax, eax
0x1800073bd  jz      short loc_1800073C6
0x1800073bf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800073c4  jz      short loc_1800073EC
0x1800073c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800073cd  test    rax, rax
0x1800073d0  jz      short loc_180007445
0x1800073d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800073d9  jnz     short loc_180007445
0x1800073db  xor     r8d, r8d
0x1800073de  xor     edx, edx
0x1800073e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ea  jmp     short loc_180007445
0x1800073ec  mov     ebx, 800h
0x1800073f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800073f8  test    rax, rax
0x1800073fb  jz      short loc_18000741A
0x1800073fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007404  jnz     short loc_18000741A
0x180007406  mov     r8d, ebx
0x180007409  lea     rdx, [rbp+13F0h+OutputString]
0x180007410  lea     rcx, [rsp+14F0h+var_14D0]
0x180007415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000741a  cmp     [rbp+13F0h+OutputString], r13w
0x180007422  jnz     short loc_180007438
0x180007424  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007429  mov     rdx, rbx; wchar_t *
0x18000742c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007433  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180007438  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000743f  call    cs:__imp_OutputDebugStringW
0x180007445  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000744a  jnz     short loc_180007455
0x18000744c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007453  jz      short loc_180007467
0x180007455  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000745c  test    rax, rax
0x18000745f  jz      short loc_180007467
0x180007461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007466  nop
0x180007467  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000746c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
