# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009100`
- end: `0x1800093a7`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008bc4`

## callees

- `0x180009100`
- `0x18000ae94`
- `0x18000c4ec`
- `0x18000e3bc`
- `0x18000e5a8`
- `0x180030362`
- `0x180030390`
- `0x180030450`
- `0x180031010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800092ab`
- `KERNEL32!IsDebuggerPresent` at `0x1800092ab`
- `KERNEL32!OutputDebugStringW` at `0x18000933b`
- `KERNEL32!OutputDebugStringW` at `0x18000933b`
- `KERNEL32!GetCurrentThreadId` at `0x1800091aa`
- `KERNEL32!GetCurrentThreadId` at `0x1800091aa`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180009100  mov     [rsp-8+arg_10], rbx
0x180009105  push    rbp
0x180009106  push    rsi
0x180009107  push    rdi
0x180009108  push    r14
0x18000910a  push    r15
0x18000910c  lea     rbp, [rsp-13D0h]
0x180009114  mov     eax, 14D0h
0x180009119  call    _alloca_probe
0x18000911e  sub     rsp, rax
0x180009121  mov     rax, cs:__security_cookie
0x180009128  xor     rax, rsp
0x18000912b  mov     [rbp+13F0h+var_30], rax
0x180009132  mov     rdi, [rbp+13F0h+arg_28]
0x180009139  mov     esi, edx
0x18000913b  mov     r14, rcx
0x18000913e  xor     edx, edx; Val
0x180009140  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009145  mov     r8d, 98h; Size
0x18000914b  call    memset_0
0x180009150  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180009157  xor     r15d, r15d
0x18000915a  mov     [rbp+13F0h+OutputString], r15w
0x180009162  mov     [rbp+13F0h+var_1430], r15b
0x180009166  mov     ecx, [rdx]; this
0x180009168  mov     eax, [rdx+4]
0x18000916b  mov     [rsp+14F0h+var_14C8], ecx
0x18000916f  mov     [rsp+14F0h+var_14C4], eax
0x180009173  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009178  cmp     dword ptr [rdx+8], 1
0x18000917c  mov     ebx, eax
0x18000917e  lea     eax, [r15+8]
0x180009182  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000918a  mov     ecx, r15d
0x18000918d  cmovz   ecx, eax
0x180009190  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009194  lea     ecx, [rax-7]
0x180009197  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000919f  inc     ecx
0x1800091a1  mov     [rsp+14F0h+var_14B8], r15
0x1800091a6  mov     [rsp+14F0h+var_14C0], ecx
0x1800091aa  call    cs:__imp_GetCurrentThreadId
0x1800091b1  nop     dword ptr [rax+rax+00h]
0x1800091b6  xorps   xmm0, xmm0
0x1800091b9  mov     [rsp+14F0h+var_1490], esi
0x1800091bd  mov     [rsp+14F0h+var_14B0], eax
0x1800091c1  xorps   xmm1, xmm1
0x1800091c4  lea     rax, aWil; "wil"
0x1800091cb  mov     [rsp+14F0h+var_148C], ebx
0x1800091cf  mov     [rsp+14F0h+var_1498], rax
0x1800091d4  xor     eax, eax
0x1800091d6  mov     [rbp+13F0h+var_1458], rax
0x1800091da  mov     [rbp+13F0h+var_1470], rax
0x1800091de  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800091e5  mov     [rsp+14F0h+var_14A8], r15
0x1800091ea  mov     [rsp+14F0h+var_14A0], r15
0x1800091ef  mov     [rbp+13F0h+var_1448], rdi
0x1800091f3  mov     [rbp+13F0h+var_1440], r14
0x1800091f7  mov     [rsp+14F0h+var_1488], r15
0x1800091fc  movups  [rbp+13F0h+var_1468], xmm0
0x180009200  movups  [rsp+14F0h+var_1480], xmm1
0x180009205  test    rax, rax
0x180009208  jz      short loc_180009215
0x18000920a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920f  mov     [rbp+13F0h+var_1450], rax
0x180009213  jmp     short loc_180009219
0x180009215  mov     [rbp+13F0h+var_1450], r15
0x180009219  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009220  test    rax, rax
0x180009223  jz      short loc_18000922F
0x180009225  lea     rcx, [rsp+14F0h+var_14D0]
0x18000922a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000922f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009236  test    rax, rax
0x180009239  jz      short loc_18000924F
0x18000923b  mov     r8d, 400h
0x180009241  lea     rdx, [rbp+13F0h+var_1430]
0x180009245  lea     rcx, [rsp+14F0h+var_14D0]
0x18000924a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000924f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009256  test    rax, rax
0x180009259  jz      short loc_180009265
0x18000925b  lea     rcx, [rsp+14F0h+var_14D0]
0x180009260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009265  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000926c  test    rax, rax
0x18000926f  jz      short loc_180009282
0x180009271  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009276  jnz     short loc_180009282
0x180009278  lea     rcx, [rsp+14F0h+var_14D0]
0x18000927d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009282  cmp     [rsp+14F0h+var_14C8], r15d
0x180009287  jge     loc_180009396
0x18000928d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180009294  jnz     short loc_1800092BB
0x180009296  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000929d  test    rax, rax
0x1800092a0  jz      short loc_1800092AB
0x1800092a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092a7  test    al, al
0x1800092a9  jmp     short loc_1800092B9
0x1800092ab  call    cs:__imp_IsDebuggerPresent
0x1800092b2  nop     dword ptr [rax+rax+00h]
0x1800092b7  test    eax, eax
0x1800092b9  jz      short loc_1800092C2
0x1800092bb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800092c0  jz      short loc_1800092E8
0x1800092c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800092c9  test    rax, rax
0x1800092cc  jz      short loc_180009347
0x1800092ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800092d5  jnz     short loc_180009347
0x1800092d7  xor     r8d, r8d
0x1800092da  lea     rcx, [rsp+14F0h+var_14D0]
0x1800092df  xor     edx, edx
0x1800092e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092e6  jmp     short loc_180009347
0x1800092e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800092ef  mov     ebx, 800h
0x1800092f4  test    rax, rax
0x1800092f7  jz      short loc_180009316
0x1800092f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009300  jnz     short loc_180009316
0x180009302  mov     r8d, ebx
0x180009305  lea     rdx, [rbp+13F0h+OutputString]
0x18000930c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009316  cmp     [rbp+13F0h+OutputString], r15w
0x18000931e  jnz     short loc_180009334
0x180009320  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009325  mov     rdx, rbx; unsigned __int16 *
0x180009328  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000932f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009334  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000933b  call    cs:__imp_OutputDebugStringW
0x180009342  nop     dword ptr [rax+rax+00h]
0x180009347  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000934c  jnz     short loc_180009357
0x18000934e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180009355  jz      short loc_180009368
0x180009357  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000935e  test    rax, rax
0x180009361  jz      short loc_180009368
0x180009363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009368  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000936d  jnz     short loc_18000939C
0x18000936f  mov     rcx, [rbp+13F0h+var_30]
0x180009376  xor     rcx, rsp; StackCookie
0x180009379  call    __security_check_cookie
0x18000937e  mov     rbx, [rsp+14F0h+arg_10]
0x180009386  add     rsp, 14D0h
0x18000938d  pop     r15
0x18000938f  pop     r14
0x180009391  pop     rdi
0x180009392  pop     rsi
0x180009393  pop     rbp
0x180009394  retn
0x180009396  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000939c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800093a1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
