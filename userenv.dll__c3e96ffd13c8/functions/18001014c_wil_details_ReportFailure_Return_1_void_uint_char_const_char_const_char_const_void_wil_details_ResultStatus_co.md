# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001014c`
- end: `0x1800103f2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ff3c`

## callees

- `0x18000d9b0`
- `0x18000e330`
- `0x18000f314`
- `0x18001014c`
- `0x1800111b8`
- `0x180011750`
- `0x18001182c`
- `0x18001ac50`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010212`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010212`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010307`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010307`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010391`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010391`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x18001014c  push    rbp
0x18001014e  push    rbx
0x18001014f  push    rsi
0x180010150  push    rdi
0x180010151  push    r12
0x180010153  push    r14
0x180010155  push    r15
0x180010157  lea     rbp, [rsp-13D0h]
0x18001015f  mov     eax, 14D0h
0x180010164  call    _alloca_probe
0x180010169  sub     rsp, rax
0x18001016c  mov     rax, cs:__security_cookie
0x180010173  xor     rax, rsp
0x180010176  mov     [rbp+1400h+var_40], rax
0x18001017d  mov     rsi, r8
0x180010180  mov     edi, edx
0x180010182  mov     rbx, rcx
0x180010185  mov     r14, [rbp+1400h+arg_28]
0x18001018c  xor     edx, edx; Val
0x18001018e  mov     r8d, 98h; Size
0x180010194  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180010199  call    memset_0
0x18001019e  nop
0x18001019f  xor     r12d, r12d
0x1800101a2  mov     [rbp+1400h+OutputString], r12w
0x1800101aa  mov     [rbp+1400h+var_1440], r12b
0x1800101ae  mov     rdx, [rbp+1400h+arg_30]; int
0x1800101b5  mov     ecx, [rdx]; this
0x1800101b7  mov     [rsp+1500h+var_14D8], ecx
0x1800101bb  mov     eax, [rdx+4]
0x1800101be  mov     [rsp+1500h+var_14D4], eax
0x1800101c2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800101c7  mov     r15d, eax
0x1800101ca  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800101d2  mov     ecx, r12d
0x1800101d5  lea     eax, [r12+8]
0x1800101da  cmp     dword ptr [rdx+8], 1
0x1800101de  cmovz   ecx, eax
0x1800101e1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800101e5  lea     ecx, [rax-7]
0x1800101e8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800101f0  inc     ecx
0x1800101f2  mov     [rsp+1500h+var_14D0], ecx
0x1800101f6  mov     rcx, [rbp+1400h+arg_38]
0x1800101fd  test    rcx, rcx
0x180010200  jz      short loc_18001020D
0x180010202  cmp     [rcx], r12w
0x180010206  mov     [rsp+1500h+var_14C8], rcx
0x18001020b  jnz     short loc_180010212
0x18001020d  mov     [rsp+1500h+var_14C8], r12
0x180010212  call    cs:__imp_GetCurrentThreadId
0x180010218  mov     [rsp+1500h+var_14C0], eax
0x18001021c  mov     [rsp+1500h+var_14A8], rsi
0x180010221  mov     [rsp+1500h+var_14A0], edi
0x180010225  mov     [rsp+1500h+var_149C], r15d
0x18001022a  mov     [rsp+1500h+var_14B8], r12
0x18001022f  mov     [rsp+1500h+var_14B0], r12
0x180010234  mov     [rbp+1400h+var_1458], r14
0x180010238  mov     [rbp+1400h+var_1450], rbx
0x18001023c  mov     [rsp+1500h+var_1498], r12
0x180010241  xorps   xmm0, xmm0
0x180010244  xor     eax, eax
0x180010246  movups  [rbp+1400h+var_1478], xmm0
0x18001024a  mov     [rbp+1400h+var_1468], rax
0x18001024e  xorps   xmm1, xmm1
0x180010251  movups  [rsp+1500h+var_1490], xmm1
0x180010256  mov     [rbp+1400h+var_1480], rax
0x18001025a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010261  test    rax, rax
0x180010264  jz      short loc_180010271
0x180010266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001026b  mov     [rbp+1400h+var_1460], rax
0x18001026f  jmp     short loc_180010275
0x180010271  mov     [rbp+1400h+var_1460], r12
0x180010275  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001027c  test    rax, rax
0x18001027f  jz      short loc_18001028B
0x180010281  lea     rcx, [rsp+1500h+var_14E0]
0x180010286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001028b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010292  test    rax, rax
0x180010295  jz      short loc_1800102AB
0x180010297  mov     r8d, 400h
0x18001029d  lea     rdx, [rbp+1400h+var_1440]
0x1800102a1  lea     rcx, [rsp+1500h+var_14E0]
0x1800102a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800102b2  test    rax, rax
0x1800102b5  jz      short loc_1800102C1
0x1800102b7  lea     rcx, [rsp+1500h+var_14E0]
0x1800102bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102c1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800102c8  test    rax, rax
0x1800102cb  jz      short loc_1800102DE
0x1800102cd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800102d2  jnz     short loc_1800102DE
0x1800102d4  lea     rcx, [rsp+1500h+var_14E0]
0x1800102d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102de  cmp     [rsp+1500h+var_14D8], r12d
0x1800102e3  jge     loc_1800103EC
0x1800102e9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800102f0  jnz     short loc_180010311
0x1800102f2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800102f9  test    rax, rax
0x1800102fc  jz      short loc_180010307
0x1800102fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010303  test    al, al
0x180010305  jmp     short loc_18001030F
0x180010307  call    cs:__imp_IsDebuggerPresent
0x18001030d  test    eax, eax
0x18001030f  jz      short loc_180010318
0x180010311  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180010316  jz      short loc_18001033E
0x180010318  mov     rax, cs:g_pfnResultLoggingCallback
0x18001031f  test    rax, rax
0x180010322  jz      short loc_180010397
0x180010324  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001032b  jnz     short loc_180010397
0x18001032d  xor     r8d, r8d
0x180010330  xor     edx, edx
0x180010332  lea     rcx, [rsp+1500h+var_14E0]
0x180010337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001033c  jmp     short loc_180010397
0x18001033e  mov     ebx, 800h
0x180010343  mov     rax, cs:g_pfnResultLoggingCallback
0x18001034a  test    rax, rax
0x18001034d  jz      short loc_18001036C
0x18001034f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180010356  jnz     short loc_18001036C
0x180010358  mov     r8d, ebx
0x18001035b  lea     rdx, [rbp+1400h+OutputString]
0x180010362  lea     rcx, [rsp+1500h+var_14E0]
0x180010367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001036c  cmp     [rbp+1400h+OutputString], r12w
0x180010374  jnz     short loc_18001038A
0x180010376  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18001037b  mov     rdx, rbx; unsigned __int16 *
0x18001037e  lea     rcx, [rbp+1400h+OutputString]; this
0x180010385  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001038a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180010391  call    cs:__imp_OutputDebugStringW
0x180010397  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18001039c  jnz     short loc_1800103A7
0x18001039e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800103a5  jz      short loc_1800103B9
0x1800103a7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800103ae  test    rax, rax
0x1800103b1  jz      short loc_1800103B9
0x1800103b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103b8  nop
0x1800103b9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800103be  jnz     short loc_1800103E1
0x1800103c0  mov     rcx, [rbp+1400h+var_40]
0x1800103c7  xor     rcx, rsp; StackCookie
0x1800103ca  call    __security_check_cookie
0x1800103cf  add     rsp, 14D0h
0x1800103d6  pop     r15
0x1800103d8  pop     r14
0x1800103da  pop     r12
0x1800103dc  pop     rdi
0x1800103dd  pop     rsi
0x1800103de  pop     rbx
0x1800103df  pop     rbp
0x1800103e0  retn
0x1800103e1  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800103e6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800103ec  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
