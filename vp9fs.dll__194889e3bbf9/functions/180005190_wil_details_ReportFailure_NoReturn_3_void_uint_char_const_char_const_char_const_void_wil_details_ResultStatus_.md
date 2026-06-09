# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005190`
- end: `0x180005409`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004ec8`

## callees

- `0x180004c80`
- `0x180005190`
- `0x180007af4`
- `0x1800082dc`
- `0x180008fb0`
- `0x18000b590`
- `0x18002ef20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005249`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005249`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800053d6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800053d6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000534c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000534c`

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
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180005190  mov     [rsp-8+arg_18], rbx
0x180005195  push    rbp
0x180005196  push    rsi
0x180005197  push    rdi
0x180005198  push    r12
0x18000519a  push    r13
0x18000519c  push    r14
0x18000519e  push    r15
0x1800051a0  lea     rbp, [rsp-13C0h]
0x1800051a8  mov     eax, 14C0h
0x1800051ad  call    _alloca_probe
0x1800051b2  sub     rsp, rax
0x1800051b5  mov     r14, r8
0x1800051b8  mov     esi, edx
0x1800051ba  mov     rdi, rcx
0x1800051bd  mov     r15, [rbp+13F0h+arg_28]
0x1800051c4  xor     edx, edx; Val
0x1800051c6  mov     r8d, 98h; Size
0x1800051cc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800051d1  call    memset_0
0x1800051d6  nop
0x1800051d7  xor     r13d, r13d
0x1800051da  mov     [rbp+13F0h+OutputString], r13w
0x1800051e2  mov     [rbp+13F0h+var_1430], r13b
0x1800051e6  mov     rbx, [rbp+13F0h+arg_30]
0x1800051ed  mov     ecx, [rbx]; this
0x1800051ef  mov     [rsp+14F0h+var_14C8], ecx
0x1800051f3  mov     eax, [rbx+4]
0x1800051f6  mov     [rsp+14F0h+var_14C4], eax
0x1800051fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800051ff  mov     r12d, eax
0x180005202  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000520a  mov     ecx, r13d
0x18000520d  lea     eax, [r13+8]
0x180005211  cmp     dword ptr [rbx+8], 1
0x180005215  cmovz   ecx, eax
0x180005218  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000521c  lea     ecx, [rax-7]
0x18000521f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005227  inc     ecx
0x180005229  mov     [rsp+14F0h+var_14C0], ecx
0x18000522d  mov     rcx, [rbp+13F0h+arg_38]
0x180005234  test    rcx, rcx
0x180005237  jz      short loc_180005244
0x180005239  cmp     [rcx], r13w
0x18000523d  mov     [rsp+14F0h+var_14B8], rcx
0x180005242  jnz     short loc_180005249
0x180005244  mov     [rsp+14F0h+var_14B8], r13
0x180005249  call    cs:__imp_GetCurrentThreadId
0x18000524f  mov     [rsp+14F0h+var_14B0], eax
0x180005253  mov     [rsp+14F0h+var_1498], r14
0x180005258  mov     [rsp+14F0h+var_1490], esi
0x18000525c  mov     [rsp+14F0h+var_148C], r12d
0x180005261  mov     [rsp+14F0h+var_14A8], r13
0x180005266  mov     [rsp+14F0h+var_14A0], r13
0x18000526b  mov     [rbp+13F0h+var_1448], r15
0x18000526f  mov     [rbp+13F0h+var_1440], rdi
0x180005273  mov     [rsp+14F0h+var_1488], r13
0x180005278  xorps   xmm0, xmm0
0x18000527b  xor     eax, eax
0x18000527d  movups  [rbp+13F0h+var_1468], xmm0
0x180005281  mov     [rbp+13F0h+var_1458], rax
0x180005285  xorps   xmm1, xmm1
0x180005288  movups  [rsp+14F0h+var_1480], xmm1
0x18000528d  mov     [rbp+13F0h+var_1470], rax
0x180005291  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005298  test    rax, rax
0x18000529b  jz      short loc_1800052A8
0x18000529d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a2  mov     [rbp+13F0h+var_1450], rax
0x1800052a6  jmp     short loc_1800052AC
0x1800052a8  mov     [rbp+13F0h+var_1450], r13
0x1800052ac  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800052b3  test    rax, rax
0x1800052b6  jz      short loc_1800052C2
0x1800052b8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800052bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800052c9  test    rax, rax
0x1800052cc  jz      short loc_1800052E2
0x1800052ce  mov     r8d, 400h
0x1800052d4  lea     rdx, [rbp+13F0h+var_1430]
0x1800052d8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800052dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800052e9  test    rax, rax
0x1800052ec  jz      short loc_1800052F8
0x1800052ee  lea     rcx, [rsp+14F0h+var_14D0]
0x1800052f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052f8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800052ff  test    rax, rax
0x180005302  jz      short loc_180005315
0x180005304  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005309  jnz     short loc_180005315
0x18000530b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005315  cmp     [rsp+14F0h+var_14C8], r13d
0x18000531a  jl      short loc_18000532E
0x18000531c  mov     ecx, 8000FFFFh; this
0x180005321  mov     [rsp+14F0h+var_14C8], ecx
0x180005325  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000532a  mov     [rsp+14F0h+var_14C4], eax
0x18000532e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005335  jnz     short loc_180005356
0x180005337  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000533e  test    rax, rax
0x180005341  jz      short loc_18000534C
0x180005343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005348  test    al, al
0x18000534a  jmp     short loc_180005354
0x18000534c  call    cs:__imp_IsDebuggerPresent
0x180005352  test    eax, eax
0x180005354  jz      short loc_18000535D
0x180005356  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000535b  jz      short loc_180005383
0x18000535d  mov     rax, cs:g_pfnResultLoggingCallback
0x180005364  test    rax, rax
0x180005367  jz      short loc_1800053DC
0x180005369  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005370  jnz     short loc_1800053DC
0x180005372  xor     r8d, r8d
0x180005375  xor     edx, edx
0x180005377  lea     rcx, [rsp+14F0h+var_14D0]
0x18000537c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005381  jmp     short loc_1800053DC
0x180005383  mov     ebx, 800h
0x180005388  mov     rax, cs:g_pfnResultLoggingCallback
0x18000538f  test    rax, rax
0x180005392  jz      short loc_1800053B1
0x180005394  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000539b  jnz     short loc_1800053B1
0x18000539d  mov     r8d, ebx
0x1800053a0  lea     rdx, [rbp+13F0h+OutputString]
0x1800053a7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800053ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b1  cmp     [rbp+13F0h+OutputString], r13w
0x1800053b9  jnz     short loc_1800053CF
0x1800053bb  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800053c0  mov     rdx, rbx; unsigned __int16 *
0x1800053c3  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800053ca  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800053cf  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800053d6  call    cs:__imp_OutputDebugStringW
0x1800053dc  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800053e1  jnz     short loc_1800053EC
0x1800053e3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800053ea  jz      short loc_1800053FE
0x1800053ec  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800053f3  test    rax, rax
0x1800053f6  jz      short loc_1800053FE
0x1800053f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fd  nop
0x1800053fe  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005403  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
