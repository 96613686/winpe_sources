# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18003bfdc`
- end: `0x18003c23c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003bda8`

## callees

- `0x18001e80c`
- `0x18003bfdc`
- `0x18003d884`
- `0x18003e0f0`
- `0x18003f130`
- `0x1800407d0`
- `0x180043580`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c07d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c07d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c20a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c20a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c180`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c180`

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
0x18003bfdc  mov     [rsp-8+arg_18], rbx
0x18003bfe1  push    rbp
0x18003bfe2  push    rsi
0x18003bfe3  push    rdi
0x18003bfe4  push    r12
0x18003bfe6  push    r13
0x18003bfe8  push    r14
0x18003bfea  push    r15
0x18003bfec  lea     rbp, [rsp-13C0h]
0x18003bff4  mov     eax, 14C0h
0x18003bff9  call    _alloca_probe
0x18003bffe  sub     rsp, rax
0x18003c001  mov     rsi, [rbp+13F0h+arg_28]
0x18003c008  mov     r15, r8
0x18003c00b  mov     r14d, edx
0x18003c00e  mov     r12, rcx
0x18003c011  xor     edx, edx; Val
0x18003c013  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18003c018  mov     r8d, 98h; Size
0x18003c01e  call    memset_0
0x18003c023  mov     rbx, [rbp+13F0h+arg_30]
0x18003c02a  xor     r13d, r13d
0x18003c02d  mov     [rbp+13F0h+OutputString], r13w
0x18003c035  mov     [rbp+13F0h+var_1430], r13b
0x18003c039  mov     ecx, [rbx]; this
0x18003c03b  mov     eax, [rbx+4]
0x18003c03e  mov     [rsp+14F0h+var_14C8], ecx
0x18003c042  mov     [rsp+14F0h+var_14C4], eax
0x18003c046  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003c04b  cmp     dword ptr [rbx+8], 1
0x18003c04f  mov     edi, eax
0x18003c051  lea     eax, [r13+8]
0x18003c055  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18003c05d  mov     ecx, r13d
0x18003c060  cmovz   ecx, eax
0x18003c063  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18003c067  lea     ecx, [rax-7]
0x18003c06a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003c072  inc     ecx
0x18003c074  mov     [rsp+14F0h+var_14B8], r13
0x18003c079  mov     [rsp+14F0h+var_14C0], ecx
0x18003c07d  call    cs:__imp_GetCurrentThreadId
0x18003c083  xorps   xmm0, xmm0
0x18003c086  mov     [rsp+14F0h+var_1498], r15
0x18003c08b  mov     [rsp+14F0h+var_14B0], eax
0x18003c08f  xorps   xmm1, xmm1
0x18003c092  xor     eax, eax
0x18003c094  mov     [rsp+14F0h+var_1490], r14d
0x18003c099  mov     [rbp+13F0h+var_1458], rax
0x18003c09d  mov     [rbp+13F0h+var_1470], rax
0x18003c0a1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003c0a8  mov     [rsp+14F0h+var_148C], edi
0x18003c0ac  mov     [rsp+14F0h+var_14A8], r13
0x18003c0b1  mov     [rsp+14F0h+var_14A0], r13
0x18003c0b6  mov     [rbp+13F0h+var_1448], rsi
0x18003c0ba  mov     [rbp+13F0h+var_1440], r12
0x18003c0be  mov     [rsp+14F0h+var_1488], r13
0x18003c0c3  movups  [rbp+13F0h+var_1468], xmm0
0x18003c0c7  movups  [rsp+14F0h+var_1480], xmm1
0x18003c0cc  test    rax, rax
0x18003c0cf  jz      short loc_18003C0DC
0x18003c0d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0d6  mov     [rbp+13F0h+var_1450], rax
0x18003c0da  jmp     short loc_18003C0E0
0x18003c0dc  mov     [rbp+13F0h+var_1450], r13
0x18003c0e0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003c0e7  test    rax, rax
0x18003c0ea  jz      short loc_18003C0F6
0x18003c0ec  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0f6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003c0fd  test    rax, rax
0x18003c100  jz      short loc_18003C116
0x18003c102  mov     r8d, 400h
0x18003c108  lea     rdx, [rbp+13F0h+var_1430]
0x18003c10c  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c116  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c11d  test    rax, rax
0x18003c120  jz      short loc_18003C12C
0x18003c122  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c12c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c133  test    rax, rax
0x18003c136  jz      short loc_18003C149
0x18003c138  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003c13d  jnz     short loc_18003C149
0x18003c13f  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c149  cmp     [rsp+14F0h+var_14C8], r13d
0x18003c14e  jl      short loc_18003C162
0x18003c150  mov     ecx, 8000FFFFh; this
0x18003c155  mov     [rsp+14F0h+var_14C8], ecx
0x18003c159  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c15e  mov     [rsp+14F0h+var_14C4], eax
0x18003c162  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18003c169  jnz     short loc_18003C18A
0x18003c16b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003c172  test    rax, rax
0x18003c175  jz      short loc_18003C180
0x18003c177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c17c  test    al, al
0x18003c17e  jmp     short loc_18003C188
0x18003c180  call    cs:__imp_IsDebuggerPresent
0x18003c186  test    eax, eax
0x18003c188  jz      short loc_18003C191
0x18003c18a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003c18f  jz      short loc_18003C1B7
0x18003c191  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c198  test    rax, rax
0x18003c19b  jz      short loc_18003C210
0x18003c19d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18003c1a4  jnz     short loc_18003C210
0x18003c1a6  xor     r8d, r8d
0x18003c1a9  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c1ae  xor     edx, edx
0x18003c1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1b5  jmp     short loc_18003C210
0x18003c1b7  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c1be  mov     ebx, 800h
0x18003c1c3  test    rax, rax
0x18003c1c6  jz      short loc_18003C1E5
0x18003c1c8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18003c1cf  jnz     short loc_18003C1E5
0x18003c1d1  mov     r8d, ebx
0x18003c1d4  lea     rdx, [rbp+13F0h+OutputString]
0x18003c1db  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1e5  cmp     [rbp+13F0h+OutputString], r13w
0x18003c1ed  jnz     short loc_18003C203
0x18003c1ef  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18003c1f4  mov     rdx, rbx; unsigned __int16 *
0x18003c1f7  lea     rcx, [rbp+13F0h+OutputString]; this
0x18003c1fe  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003c203  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18003c20a  call    cs:__imp_OutputDebugStringW
0x18003c210  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18003c215  jnz     short loc_18003C220
0x18003c217  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18003c21e  jz      short loc_18003C231
0x18003c220  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003c227  test    rax, rax
0x18003c22a  jz      short loc_18003C231
0x18003c22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c231  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18003c236  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
