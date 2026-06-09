# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400046f0`
- end: `0x140004950`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140004494`

## callees

- `0x1400046f0`
- `0x140006834`
- `0x140006fcc`
- `0x140007ba0`
- `0x140009e50`
- `0x14000d1be`
- `0x14000d280`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004791`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004791`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000491e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000491e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004894`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004894`

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
0x1400046f0  mov     [rsp-8+arg_18], rbx
0x1400046f5  push    rbp
0x1400046f6  push    rsi
0x1400046f7  push    rdi
0x1400046f8  push    r12
0x1400046fa  push    r13
0x1400046fc  push    r14
0x1400046fe  push    r15
0x140004700  lea     rbp, [rsp-13C0h]
0x140004708  mov     eax, 14C0h
0x14000470d  call    _alloca_probe
0x140004712  sub     rsp, rax
0x140004715  mov     rsi, [rbp+13F0h+arg_28]
0x14000471c  mov     r15, r8
0x14000471f  mov     r14d, edx
0x140004722  mov     r12, rcx
0x140004725  xor     edx, edx; Val
0x140004727  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000472c  mov     r8d, 98h; Size
0x140004732  call    memset_0
0x140004737  mov     rbx, [rbp+13F0h+arg_30]
0x14000473e  xor     r13d, r13d
0x140004741  mov     [rbp+13F0h+OutputString], r13w
0x140004749  mov     [rbp+13F0h+var_1430], r13b
0x14000474d  mov     ecx, [rbx]; this
0x14000474f  mov     eax, [rbx+4]
0x140004752  mov     [rsp+14F0h+var_14C8], ecx
0x140004756  mov     [rsp+14F0h+var_14C4], eax
0x14000475a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000475f  cmp     dword ptr [rbx+8], 1
0x140004763  mov     edi, eax
0x140004765  lea     eax, [r13+8]
0x140004769  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140004771  mov     ecx, r13d
0x140004774  cmovz   ecx, eax
0x140004777  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000477b  lea     ecx, [rax-7]
0x14000477e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004786  inc     ecx
0x140004788  mov     [rsp+14F0h+var_14B8], r13
0x14000478d  mov     [rsp+14F0h+var_14C0], ecx
0x140004791  call    cs:__imp_GetCurrentThreadId
0x140004797  xorps   xmm0, xmm0
0x14000479a  mov     [rsp+14F0h+var_1498], r15
0x14000479f  mov     [rsp+14F0h+var_14B0], eax
0x1400047a3  xorps   xmm1, xmm1
0x1400047a6  xor     eax, eax
0x1400047a8  mov     [rsp+14F0h+var_1490], r14d
0x1400047ad  mov     [rbp+13F0h+var_1458], rax
0x1400047b1  mov     [rbp+13F0h+var_1470], rax
0x1400047b5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400047bc  mov     [rsp+14F0h+var_148C], edi
0x1400047c0  mov     [rsp+14F0h+var_14A8], r13
0x1400047c5  mov     [rsp+14F0h+var_14A0], r13
0x1400047ca  mov     [rbp+13F0h+var_1448], rsi
0x1400047ce  mov     [rbp+13F0h+var_1440], r12
0x1400047d2  mov     [rsp+14F0h+var_1488], r13
0x1400047d7  movups  [rbp+13F0h+var_1468], xmm0
0x1400047db  movups  [rsp+14F0h+var_1480], xmm1
0x1400047e0  test    rax, rax
0x1400047e3  jz      short loc_1400047F0
0x1400047e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047ea  mov     [rbp+13F0h+var_1450], rax
0x1400047ee  jmp     short loc_1400047F4
0x1400047f0  mov     [rbp+13F0h+var_1450], r13
0x1400047f4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400047fb  test    rax, rax
0x1400047fe  jz      short loc_14000480A
0x140004800  lea     rcx, [rsp+14F0h+var_14D0]
0x140004805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000480a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004811  test    rax, rax
0x140004814  jz      short loc_14000482A
0x140004816  mov     r8d, 400h
0x14000481c  lea     rdx, [rbp+13F0h+var_1430]
0x140004820  lea     rcx, [rsp+14F0h+var_14D0]
0x140004825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000482a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004831  test    rax, rax
0x140004834  jz      short loc_140004840
0x140004836  lea     rcx, [rsp+14F0h+var_14D0]
0x14000483b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004840  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004847  test    rax, rax
0x14000484a  jz      short loc_14000485D
0x14000484c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140004851  jnz     short loc_14000485D
0x140004853  lea     rcx, [rsp+14F0h+var_14D0]
0x140004858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000485d  cmp     [rsp+14F0h+var_14C8], r13d
0x140004862  jl      short loc_140004876
0x140004864  mov     ecx, 8000FFFFh; this
0x140004869  mov     [rsp+14F0h+var_14C8], ecx
0x14000486d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004872  mov     [rsp+14F0h+var_14C4], eax
0x140004876  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000487d  jnz     short loc_14000489E
0x14000487f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004886  test    rax, rax
0x140004889  jz      short loc_140004894
0x14000488b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004890  test    al, al
0x140004892  jmp     short loc_14000489C
0x140004894  call    cs:__imp_IsDebuggerPresent
0x14000489a  test    eax, eax
0x14000489c  jz      short loc_1400048A5
0x14000489e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400048a3  jz      short loc_1400048CB
0x1400048a5  mov     rax, cs:g_pfnResultLoggingCallback
0x1400048ac  test    rax, rax
0x1400048af  jz      short loc_140004924
0x1400048b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400048b8  jnz     short loc_140004924
0x1400048ba  xor     r8d, r8d
0x1400048bd  lea     rcx, [rsp+14F0h+var_14D0]
0x1400048c2  xor     edx, edx
0x1400048c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048c9  jmp     short loc_140004924
0x1400048cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400048d2  mov     ebx, 800h
0x1400048d7  test    rax, rax
0x1400048da  jz      short loc_1400048F9
0x1400048dc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400048e3  jnz     short loc_1400048F9
0x1400048e5  mov     r8d, ebx
0x1400048e8  lea     rdx, [rbp+13F0h+OutputString]
0x1400048ef  lea     rcx, [rsp+14F0h+var_14D0]
0x1400048f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048f9  cmp     [rbp+13F0h+OutputString], r13w
0x140004901  jnz     short loc_140004917
0x140004903  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140004908  mov     rdx, rbx; unsigned __int16 *
0x14000490b  lea     rcx, [rbp+13F0h+OutputString]; this
0x140004912  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004917  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000491e  call    cs:__imp_OutputDebugStringW
0x140004924  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140004929  jnz     short loc_140004934
0x14000492b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140004932  jz      short loc_140004945
0x140004934  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000493b  test    rax, rax
0x14000493e  jz      short loc_140004945
0x140004940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004945  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000494a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
