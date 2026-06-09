# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800153d4`
- end: `0x18001566a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180014edc`

## callees

- `0x1800153d4`
- `0x1800185f4`
- `0x18001d5b0`
- `0x1800200d0`
- `0x18002028c`
- `0x18007755e`
- `0x180077590`
- `0x180077620`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001547f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001547f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001557a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001557a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015604`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015604`

## pseudocode

```c
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
0x1800153d4  mov     [rsp-8+arg_10], rbx
0x1800153d9  push    rbp
0x1800153da  push    rsi
0x1800153db  push    rdi
0x1800153dc  push    r14
0x1800153de  push    r15
0x1800153e0  lea     rbp, [rsp-13D0h]
0x1800153e8  mov     eax, 14D0h
0x1800153ed  call    _alloca_probe
0x1800153f2  sub     rsp, rax
0x1800153f5  mov     rax, cs:__security_cookie
0x1800153fc  xor     rax, rsp
0x1800153ff  mov     [rbp+13F0h+var_30], rax
0x180015406  mov     esi, edx
0x180015408  mov     r14, rcx
0x18001540b  mov     rdi, [rbp+13F0h+arg_28]
0x180015412  xor     edx, edx; Val
0x180015414  mov     r8d, 98h; Size
0x18001541a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001541f  call    memset_0
0x180015424  nop
0x180015425  xor     r15d, r15d
0x180015428  mov     [rbp+13F0h+OutputString], r15w
0x180015430  mov     [rbp+13F0h+var_1430], r15b
0x180015434  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001543b  mov     ecx, [rdx]; this
0x18001543d  mov     [rsp+14F0h+var_14C8], ecx
0x180015441  mov     eax, [rdx+4]
0x180015444  mov     [rsp+14F0h+var_14C4], eax
0x180015448  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001544d  mov     ebx, eax
0x18001544f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180015457  mov     ecx, r15d
0x18001545a  lea     eax, [r15+8]
0x18001545e  cmp     dword ptr [rdx+8], 1
0x180015462  cmovz   ecx, eax
0x180015465  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180015469  lea     ecx, [rax-7]
0x18001546c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015474  inc     ecx
0x180015476  mov     [rsp+14F0h+var_14C0], ecx
0x18001547a  mov     [rsp+14F0h+var_14B8], r15
0x18001547f  call    cs:__imp_GetCurrentThreadId
0x180015485  mov     [rsp+14F0h+var_14B0], eax
0x180015489  lea     rax, aWil; "wil"
0x180015490  mov     [rsp+14F0h+var_1498], rax
0x180015495  mov     [rsp+14F0h+var_1490], esi
0x180015499  mov     [rsp+14F0h+var_148C], ebx
0x18001549d  mov     [rsp+14F0h+var_14A8], r15
0x1800154a2  mov     [rsp+14F0h+var_14A0], r15
0x1800154a7  mov     [rbp+13F0h+var_1448], rdi
0x1800154ab  mov     [rbp+13F0h+var_1440], r14
0x1800154af  mov     [rsp+14F0h+var_1488], r15
0x1800154b4  xorps   xmm0, xmm0
0x1800154b7  xor     eax, eax
0x1800154b9  movups  [rbp+13F0h+var_1468], xmm0
0x1800154bd  mov     [rbp+13F0h+var_1458], rax
0x1800154c1  xorps   xmm1, xmm1
0x1800154c4  movups  [rsp+14F0h+var_1480], xmm1
0x1800154c9  mov     [rbp+13F0h+var_1470], rax
0x1800154cd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800154d4  test    rax, rax
0x1800154d7  jz      short loc_1800154E4
0x1800154d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154de  mov     [rbp+13F0h+var_1450], rax
0x1800154e2  jmp     short loc_1800154E8
0x1800154e4  mov     [rbp+13F0h+var_1450], r15
0x1800154e8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800154ef  test    rax, rax
0x1800154f2  jz      short loc_1800154FE
0x1800154f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800154f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154fe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015505  test    rax, rax
0x180015508  jz      short loc_18001551E
0x18001550a  mov     r8d, 400h
0x180015510  lea     rdx, [rbp+13F0h+var_1430]
0x180015514  lea     rcx, [rsp+14F0h+var_14D0]
0x180015519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001551e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015525  test    rax, rax
0x180015528  jz      short loc_180015534
0x18001552a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001552f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015534  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001553b  test    rax, rax
0x18001553e  jz      short loc_180015551
0x180015540  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180015545  jnz     short loc_180015551
0x180015547  lea     rcx, [rsp+14F0h+var_14D0]
0x18001554c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015551  cmp     [rsp+14F0h+var_14C8], r15d
0x180015556  jge     loc_180015664
0x18001555c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180015563  jnz     short loc_180015584
0x180015565  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001556c  test    rax, rax
0x18001556f  jz      short loc_18001557A
0x180015571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015576  test    al, al
0x180015578  jmp     short loc_180015582
0x18001557a  call    cs:__imp_IsDebuggerPresent
0x180015580  test    eax, eax
0x180015582  jz      short loc_18001558B
0x180015584  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180015589  jz      short loc_1800155B1
0x18001558b  mov     rax, cs:g_pfnResultLoggingCallback
0x180015592  test    rax, rax
0x180015595  jz      short loc_18001560A
0x180015597  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001559e  jnz     short loc_18001560A
0x1800155a0  xor     r8d, r8d
0x1800155a3  xor     edx, edx
0x1800155a5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800155aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155af  jmp     short loc_18001560A
0x1800155b1  mov     ebx, 800h
0x1800155b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800155bd  test    rax, rax
0x1800155c0  jz      short loc_1800155DF
0x1800155c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800155c9  jnz     short loc_1800155DF
0x1800155cb  mov     r8d, ebx
0x1800155ce  lea     rdx, [rbp+13F0h+OutputString]
0x1800155d5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800155da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155df  cmp     [rbp+13F0h+OutputString], r15w
0x1800155e7  jnz     short loc_1800155FD
0x1800155e9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800155ee  mov     rdx, rbx; unsigned __int16 *
0x1800155f1  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800155f8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800155fd  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180015604  call    cs:__imp_OutputDebugStringW
0x18001560a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001560f  jnz     short loc_18001561A
0x180015611  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180015618  jz      short loc_18001562C
0x18001561a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015621  test    rax, rax
0x180015624  jz      short loc_18001562C
0x180015626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001562b  nop
0x18001562c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180015631  jnz     short loc_180015659
0x180015633  mov     rcx, [rbp+13F0h+var_30]
0x18001563a  xor     rcx, rsp; StackCookie
0x18001563d  call    __security_check_cookie
0x180015642  mov     rbx, [rsp+14F0h+arg_10]
0x18001564a  add     rsp, 14D0h
0x180015651  pop     r15
0x180015653  pop     r14
0x180015655  pop     rdi
0x180015656  pop     rsi
0x180015657  pop     rbp
0x180015658  retn
0x180015659  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001565e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180015664  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
