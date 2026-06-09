# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001516c`
- end: `0x1800153ce`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180014f38`

## callees

- `0x18001516c`
- `0x1800185f4`
- `0x180019050`
- `0x18001d410`
- `0x1800200d0`
- `0x18007755e`
- `0x180077620`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001520e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001520e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015311`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015311`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001539b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001539b`

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
0x18001516c  mov     [rsp-8+arg_18], rbx
0x180015171  push    rbp
0x180015172  push    rsi
0x180015173  push    rdi
0x180015174  push    r12
0x180015176  push    r13
0x180015178  push    r14
0x18001517a  push    r15
0x18001517c  lea     rbp, [rsp-13C0h]
0x180015184  mov     eax, 14C0h
0x180015189  call    _alloca_probe
0x18001518e  sub     rsp, rax
0x180015191  mov     r15, r8
0x180015194  mov     r14d, edx
0x180015197  mov     r12, rcx
0x18001519a  mov     rsi, [rbp+13F0h+arg_28]
0x1800151a1  xor     edx, edx; Val
0x1800151a3  mov     r8d, 98h; Size
0x1800151a9  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800151ae  call    memset_0
0x1800151b3  nop
0x1800151b4  xor     r13d, r13d
0x1800151b7  mov     [rbp+13F0h+OutputString], r13w
0x1800151bf  mov     [rbp+13F0h+var_1430], r13b
0x1800151c3  mov     rbx, [rbp+13F0h+arg_30]
0x1800151ca  mov     ecx, [rbx]; this
0x1800151cc  mov     [rsp+14F0h+var_14C8], ecx
0x1800151d0  mov     eax, [rbx+4]
0x1800151d3  mov     [rsp+14F0h+var_14C4], eax
0x1800151d7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800151dc  mov     edi, eax
0x1800151de  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800151e6  mov     ecx, r13d
0x1800151e9  lea     eax, [r13+8]
0x1800151ed  cmp     dword ptr [rbx+8], 1
0x1800151f1  cmovz   ecx, eax
0x1800151f4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800151f8  lea     ecx, [rax-7]
0x1800151fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015203  inc     ecx
0x180015205  mov     [rsp+14F0h+var_14C0], ecx
0x180015209  mov     [rsp+14F0h+var_14B8], r13
0x18001520e  call    cs:__imp_GetCurrentThreadId
0x180015214  mov     [rsp+14F0h+var_14B0], eax
0x180015218  mov     [rsp+14F0h+var_1498], r15
0x18001521d  mov     [rsp+14F0h+var_1490], r14d
0x180015222  mov     [rsp+14F0h+var_148C], edi
0x180015226  mov     [rsp+14F0h+var_14A8], r13
0x18001522b  mov     [rsp+14F0h+var_14A0], r13
0x180015230  mov     [rbp+13F0h+var_1448], rsi
0x180015234  mov     [rbp+13F0h+var_1440], r12
0x180015238  mov     [rsp+14F0h+var_1488], r13
0x18001523d  xorps   xmm0, xmm0
0x180015240  xor     eax, eax
0x180015242  movups  [rbp+13F0h+var_1468], xmm0
0x180015246  mov     [rbp+13F0h+var_1458], rax
0x18001524a  xorps   xmm1, xmm1
0x18001524d  movups  [rsp+14F0h+var_1480], xmm1
0x180015252  mov     [rbp+13F0h+var_1470], rax
0x180015256  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001525d  test    rax, rax
0x180015260  jz      short loc_18001526D
0x180015262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015267  mov     [rbp+13F0h+var_1450], rax
0x18001526b  jmp     short loc_180015271
0x18001526d  mov     [rbp+13F0h+var_1450], r13
0x180015271  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015278  test    rax, rax
0x18001527b  jz      short loc_180015287
0x18001527d  lea     rcx, [rsp+14F0h+var_14D0]
0x180015282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015287  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001528e  test    rax, rax
0x180015291  jz      short loc_1800152A7
0x180015293  mov     r8d, 400h
0x180015299  lea     rdx, [rbp+13F0h+var_1430]
0x18001529d  lea     rcx, [rsp+14F0h+var_14D0]
0x1800152a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800152ae  test    rax, rax
0x1800152b1  jz      short loc_1800152BD
0x1800152b3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800152b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152bd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800152c4  test    rax, rax
0x1800152c7  jz      short loc_1800152DA
0x1800152c9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800152ce  jnz     short loc_1800152DA
0x1800152d0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800152d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152da  cmp     [rsp+14F0h+var_14C8], r13d
0x1800152df  jl      short loc_1800152F3
0x1800152e1  mov     ecx, 8000FFFFh; this
0x1800152e6  mov     [rsp+14F0h+var_14C8], ecx
0x1800152ea  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800152ef  mov     [rsp+14F0h+var_14C4], eax
0x1800152f3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800152fa  jnz     short loc_18001531B
0x1800152fc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015303  test    rax, rax
0x180015306  jz      short loc_180015311
0x180015308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001530d  test    al, al
0x18001530f  jmp     short loc_180015319
0x180015311  call    cs:__imp_IsDebuggerPresent
0x180015317  test    eax, eax
0x180015319  jz      short loc_180015322
0x18001531b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180015320  jz      short loc_180015348
0x180015322  mov     rax, cs:g_pfnResultLoggingCallback
0x180015329  test    rax, rax
0x18001532c  jz      short loc_1800153A1
0x18001532e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180015335  jnz     short loc_1800153A1
0x180015337  xor     r8d, r8d
0x18001533a  xor     edx, edx
0x18001533c  lea     rcx, [rsp+14F0h+var_14D0]
0x180015341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015346  jmp     short loc_1800153A1
0x180015348  mov     ebx, 800h
0x18001534d  mov     rax, cs:g_pfnResultLoggingCallback
0x180015354  test    rax, rax
0x180015357  jz      short loc_180015376
0x180015359  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180015360  jnz     short loc_180015376
0x180015362  mov     r8d, ebx
0x180015365  lea     rdx, [rbp+13F0h+OutputString]
0x18001536c  lea     rcx, [rsp+14F0h+var_14D0]
0x180015371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015376  cmp     [rbp+13F0h+OutputString], r13w
0x18001537e  jnz     short loc_180015394
0x180015380  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180015385  mov     rdx, rbx; unsigned __int16 *
0x180015388  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001538f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180015394  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001539b  call    cs:__imp_OutputDebugStringW
0x1800153a1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800153a6  jnz     short loc_1800153B1
0x1800153a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800153af  jz      short loc_1800153C3
0x1800153b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800153b8  test    rax, rax
0x1800153bb  jz      short loc_1800153C3
0x1800153bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153c2  nop
0x1800153c3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800153c8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
