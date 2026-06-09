# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18002cd04`
- end: `0x18002cf66`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002caa8`

## callees

- `0x18002cd04`
- `0x18002fe84`
- `0x180030620`
- `0x1800316d0`
- `0x1800340b0`
- `0x180056df2`
- `0x180056ef0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cda6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cda6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002cf33`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002cf33`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002cea9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002cea9`

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
0x18002cd04  mov     [rsp-8+arg_18], rbx
0x18002cd09  push    rbp
0x18002cd0a  push    rsi
0x18002cd0b  push    rdi
0x18002cd0c  push    r12
0x18002cd0e  push    r13
0x18002cd10  push    r14
0x18002cd12  push    r15
0x18002cd14  lea     rbp, [rsp-13C0h]
0x18002cd1c  mov     eax, 14C0h
0x18002cd21  call    _alloca_probe
0x18002cd26  sub     rsp, rax
0x18002cd29  mov     r15, r8
0x18002cd2c  mov     r14d, edx
0x18002cd2f  mov     r12, rcx
0x18002cd32  mov     rsi, [rbp+13F0h+arg_28]
0x18002cd39  xor     edx, edx; Val
0x18002cd3b  mov     r8d, 98h; Size
0x18002cd41  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002cd46  call    memset_0
0x18002cd4b  nop
0x18002cd4c  xor     r13d, r13d
0x18002cd4f  mov     [rbp+13F0h+OutputString], r13w
0x18002cd57  mov     [rbp+13F0h+var_1430], r13b
0x18002cd5b  mov     rbx, [rbp+13F0h+arg_30]
0x18002cd62  mov     ecx, [rbx]; this
0x18002cd64  mov     [rsp+14F0h+var_14C8], ecx
0x18002cd68  mov     eax, [rbx+4]
0x18002cd6b  mov     [rsp+14F0h+var_14C4], eax
0x18002cd6f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002cd74  mov     edi, eax
0x18002cd76  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18002cd7e  mov     ecx, r13d
0x18002cd81  lea     eax, [r13+8]
0x18002cd85  cmp     dword ptr [rbx+8], 1
0x18002cd89  cmovz   ecx, eax
0x18002cd8c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002cd90  lea     ecx, [rax-7]
0x18002cd93  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002cd9b  inc     ecx
0x18002cd9d  mov     [rsp+14F0h+var_14C0], ecx
0x18002cda1  mov     [rsp+14F0h+var_14B8], r13
0x18002cda6  call    cs:__imp_GetCurrentThreadId
0x18002cdac  mov     [rsp+14F0h+var_14B0], eax
0x18002cdb0  mov     [rsp+14F0h+var_1498], r15
0x18002cdb5  mov     [rsp+14F0h+var_1490], r14d
0x18002cdba  mov     [rsp+14F0h+var_148C], edi
0x18002cdbe  mov     [rsp+14F0h+var_14A8], r13
0x18002cdc3  mov     [rsp+14F0h+var_14A0], r13
0x18002cdc8  mov     [rbp+13F0h+var_1448], rsi
0x18002cdcc  mov     [rbp+13F0h+var_1440], r12
0x18002cdd0  mov     [rsp+14F0h+var_1488], r13
0x18002cdd5  xorps   xmm0, xmm0
0x18002cdd8  xor     eax, eax
0x18002cdda  movups  [rbp+13F0h+var_1468], xmm0
0x18002cdde  mov     [rbp+13F0h+var_1458], rax
0x18002cde2  xorps   xmm1, xmm1
0x18002cde5  movups  [rsp+14F0h+var_1480], xmm1
0x18002cdea  mov     [rbp+13F0h+var_1470], rax
0x18002cdee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002cdf5  test    rax, rax
0x18002cdf8  jz      short loc_18002CE05
0x18002cdfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdff  mov     [rbp+13F0h+var_1450], rax
0x18002ce03  jmp     short loc_18002CE09
0x18002ce05  mov     [rbp+13F0h+var_1450], r13
0x18002ce09  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002ce10  test    rax, rax
0x18002ce13  jz      short loc_18002CE1F
0x18002ce15  lea     rcx, [rsp+14F0h+var_14D0]
0x18002ce1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce1f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002ce26  test    rax, rax
0x18002ce29  jz      short loc_18002CE3F
0x18002ce2b  mov     r8d, 400h
0x18002ce31  lea     rdx, [rbp+13F0h+var_1430]
0x18002ce35  lea     rcx, [rsp+14F0h+var_14D0]
0x18002ce3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce3f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002ce46  test    rax, rax
0x18002ce49  jz      short loc_18002CE55
0x18002ce4b  lea     rcx, [rsp+14F0h+var_14D0]
0x18002ce50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce55  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002ce5c  test    rax, rax
0x18002ce5f  jz      short loc_18002CE72
0x18002ce61  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002ce66  jnz     short loc_18002CE72
0x18002ce68  lea     rcx, [rsp+14F0h+var_14D0]
0x18002ce6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce72  cmp     [rsp+14F0h+var_14C8], r13d
0x18002ce77  jl      short loc_18002CE8B
0x18002ce79  mov     ecx, 8000FFFFh; this
0x18002ce7e  mov     [rsp+14F0h+var_14C8], ecx
0x18002ce82  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002ce87  mov     [rsp+14F0h+var_14C4], eax
0x18002ce8b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18002ce92  jnz     short loc_18002CEB3
0x18002ce94  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002ce9b  test    rax, rax
0x18002ce9e  jz      short loc_18002CEA9
0x18002cea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cea5  test    al, al
0x18002cea7  jmp     short loc_18002CEB1
0x18002cea9  call    cs:__imp_IsDebuggerPresent
0x18002ceaf  test    eax, eax
0x18002ceb1  jz      short loc_18002CEBA
0x18002ceb3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002ceb8  jz      short loc_18002CEE0
0x18002ceba  mov     rax, cs:g_pfnResultLoggingCallback
0x18002cec1  test    rax, rax
0x18002cec4  jz      short loc_18002CF39
0x18002cec6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002cecd  jnz     short loc_18002CF39
0x18002cecf  xor     r8d, r8d
0x18002ced2  xor     edx, edx
0x18002ced4  lea     rcx, [rsp+14F0h+var_14D0]
0x18002ced9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cede  jmp     short loc_18002CF39
0x18002cee0  mov     ebx, 800h
0x18002cee5  mov     rax, cs:g_pfnResultLoggingCallback
0x18002ceec  test    rax, rax
0x18002ceef  jz      short loc_18002CF0E
0x18002cef1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002cef8  jnz     short loc_18002CF0E
0x18002cefa  mov     r8d, ebx
0x18002cefd  lea     rdx, [rbp+13F0h+OutputString]
0x18002cf04  lea     rcx, [rsp+14F0h+var_14D0]
0x18002cf09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf0e  cmp     [rbp+13F0h+OutputString], r13w
0x18002cf16  jnz     short loc_18002CF2C
0x18002cf18  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002cf1d  mov     rdx, rbx; unsigned __int16 *
0x18002cf20  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002cf27  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002cf2c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002cf33  call    cs:__imp_OutputDebugStringW
0x18002cf39  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002cf3e  jnz     short loc_18002CF49
0x18002cf40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18002cf47  jz      short loc_18002CF5B
0x18002cf49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002cf50  test    rax, rax
0x18002cf53  jz      short loc_18002CF5B
0x18002cf55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf5a  nop
0x18002cf5b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002cf60  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
