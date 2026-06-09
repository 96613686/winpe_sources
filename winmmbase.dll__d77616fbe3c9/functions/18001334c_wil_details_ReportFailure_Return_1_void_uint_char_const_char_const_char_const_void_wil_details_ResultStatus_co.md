# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001334c`
- end: `0x1800135e2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001300c`

## callees

- `0x1800106c0`
- `0x18001102a`
- `0x18001334c`
- `0x1800144e4`
- `0x1800156b0`
- `0x180016438`
- `0x180016514`
- `0x180020750`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800133f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800133f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800134f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800134f2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001357c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001357c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18001334c  mov     [rsp-8+arg_10], rbx
0x180013351  push    rbp
0x180013352  push    rsi
0x180013353  push    rdi
0x180013354  push    r14
0x180013356  push    r15
0x180013358  lea     rbp, [rsp-13D0h]
0x180013360  mov     eax, 14D0h
0x180013365  call    _alloca_probe
0x18001336a  sub     rsp, rax
0x18001336d  mov     rax, cs:__security_cookie
0x180013374  xor     rax, rsp
0x180013377  mov     [rbp+13F0h+var_30], rax
0x18001337e  mov     esi, edx
0x180013380  mov     r14, rcx
0x180013383  mov     rdi, [rbp+13F0h+arg_28]
0x18001338a  xor     edx, edx; Val
0x18001338c  mov     r8d, 98h; Size
0x180013392  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180013397  call    memset_0
0x18001339c  nop
0x18001339d  xor     r15d, r15d
0x1800133a0  mov     [rbp+13F0h+OutputString], r15w
0x1800133a8  mov     [rbp+13F0h+var_1430], r15b
0x1800133ac  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800133b3  mov     ecx, [rdx]; this
0x1800133b5  mov     [rsp+14F0h+var_14C8], ecx
0x1800133b9  mov     eax, [rdx+4]
0x1800133bc  mov     [rsp+14F0h+var_14C4], eax
0x1800133c0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800133c5  mov     ebx, eax
0x1800133c7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800133cf  mov     ecx, r15d
0x1800133d2  lea     eax, [r15+8]
0x1800133d6  cmp     dword ptr [rdx+8], 1
0x1800133da  cmovz   ecx, eax
0x1800133dd  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800133e1  lea     ecx, [rax-7]
0x1800133e4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800133ec  inc     ecx
0x1800133ee  mov     [rsp+14F0h+var_14C0], ecx
0x1800133f2  mov     [rsp+14F0h+var_14B8], r15
0x1800133f7  call    cs:__imp_GetCurrentThreadId
0x1800133fd  mov     [rsp+14F0h+var_14B0], eax
0x180013401  lea     rax, aWil; "wil"
0x180013408  mov     [rsp+14F0h+var_1498], rax
0x18001340d  mov     [rsp+14F0h+var_1490], esi
0x180013411  mov     [rsp+14F0h+var_148C], ebx
0x180013415  mov     [rsp+14F0h+var_14A8], r15
0x18001341a  mov     [rsp+14F0h+var_14A0], r15
0x18001341f  mov     [rbp+13F0h+var_1448], rdi
0x180013423  mov     [rbp+13F0h+var_1440], r14
0x180013427  mov     [rsp+14F0h+var_1488], r15
0x18001342c  xorps   xmm0, xmm0
0x18001342f  xor     eax, eax
0x180013431  movups  [rbp+13F0h+var_1468], xmm0
0x180013435  mov     [rbp+13F0h+var_1458], rax
0x180013439  xorps   xmm1, xmm1
0x18001343c  movups  [rsp+14F0h+var_1480], xmm1
0x180013441  mov     [rbp+13F0h+var_1470], rax
0x180013445  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001344c  test    rax, rax
0x18001344f  jz      short loc_18001345C
0x180013451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013456  mov     [rbp+13F0h+var_1450], rax
0x18001345a  jmp     short loc_180013460
0x18001345c  mov     [rbp+13F0h+var_1450], r15
0x180013460  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013467  test    rax, rax
0x18001346a  jz      short loc_180013476
0x18001346c  lea     rcx, [rsp+14F0h+var_14D0]
0x180013471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013476  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001347d  test    rax, rax
0x180013480  jz      short loc_180013496
0x180013482  mov     r8d, 400h
0x180013488  lea     rdx, [rbp+13F0h+var_1430]
0x18001348c  lea     rcx, [rsp+14F0h+var_14D0]
0x180013491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013496  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001349d  test    rax, rax
0x1800134a0  jz      short loc_1800134AC
0x1800134a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800134a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ac  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800134b3  test    rax, rax
0x1800134b6  jz      short loc_1800134C9
0x1800134b8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800134bd  jnz     short loc_1800134C9
0x1800134bf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800134c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134c9  cmp     [rsp+14F0h+var_14C8], r15d
0x1800134ce  jge     loc_1800135DC
0x1800134d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800134db  jnz     short loc_1800134FC
0x1800134dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800134e4  test    rax, rax
0x1800134e7  jz      short loc_1800134F2
0x1800134e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ee  test    al, al
0x1800134f0  jmp     short loc_1800134FA
0x1800134f2  call    cs:__imp_IsDebuggerPresent
0x1800134f8  test    eax, eax
0x1800134fa  jz      short loc_180013503
0x1800134fc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180013501  jz      short loc_180013529
0x180013503  mov     rax, cs:g_pfnResultLoggingCallback
0x18001350a  test    rax, rax
0x18001350d  jz      short loc_180013582
0x18001350f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180013516  jnz     short loc_180013582
0x180013518  xor     r8d, r8d
0x18001351b  xor     edx, edx
0x18001351d  lea     rcx, [rsp+14F0h+var_14D0]
0x180013522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013527  jmp     short loc_180013582
0x180013529  mov     ebx, 800h
0x18001352e  mov     rax, cs:g_pfnResultLoggingCallback
0x180013535  test    rax, rax
0x180013538  jz      short loc_180013557
0x18001353a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180013541  jnz     short loc_180013557
0x180013543  mov     r8d, ebx
0x180013546  lea     rdx, [rbp+13F0h+OutputString]
0x18001354d  lea     rcx, [rsp+14F0h+var_14D0]
0x180013552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013557  cmp     [rbp+13F0h+OutputString], r15w
0x18001355f  jnz     short loc_180013575
0x180013561  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180013566  mov     rdx, rbx; unsigned __int16 *
0x180013569  lea     rcx, [rbp+13F0h+OutputString]; this
0x180013570  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013575  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001357c  call    cs:__imp_OutputDebugStringW
0x180013582  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180013587  jnz     short loc_180013592
0x180013589  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180013590  jz      short loc_1800135A4
0x180013592  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013599  test    rax, rax
0x18001359c  jz      short loc_1800135A4
0x18001359e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135a3  nop
0x1800135a4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800135a9  jnz     short loc_1800135D1
0x1800135ab  mov     rcx, [rbp+13F0h+var_30]
0x1800135b2  xor     rcx, rsp; StackCookie
0x1800135b5  call    __security_check_cookie
0x1800135ba  mov     rbx, [rsp+14F0h+arg_10]
0x1800135c2  add     rsp, 14D0h
0x1800135c9  pop     r15
0x1800135cb  pop     r14
0x1800135cd  pop     rdi
0x1800135ce  pop     rsi
0x1800135cf  pop     rbp
0x1800135d0  retn
0x1800135d1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800135d6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800135dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
