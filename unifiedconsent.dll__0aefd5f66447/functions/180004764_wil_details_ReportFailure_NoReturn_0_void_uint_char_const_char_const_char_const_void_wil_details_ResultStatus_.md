# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004764`
- end: `0x180004a4a`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004098`

## callees

- `0x180003384`
- `0x180004764`
- `0x180009274`
- `0x18000ac84`
- `0x18000c744`
- `0x18000d8e8`
- `0x18000e140`
- `0x18000e434`
- `0x180070720`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004838`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004838`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800049d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800049d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004938`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004938`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        char a9)
{
  bool v12; // di
  _WORD *v13; // r8
  int v14; // r13d
  int v15; // ecx
  __int64 v16; // rdx
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  char v21; // bl
  const struct wil::FailureInfo *v22; // rdx
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  int v24; // [rsp+24h] [rbp-DCh]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v27; // [rsp+30h] [rbp-D0h]
  _WORD *v28; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+64h] [rbp-9Ch]
  __int64 v35; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  __int128 v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  char v43[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v12 = (a9 & 2) == 0 && g_pfnThrowPlatformException;
  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v25 = *a7;
  v26 = a7[1];
  v14 = wil::details::RecordException((wil::details *)(unsigned int)v25, (int)a7);
  v23 = (int)v13;
  v15 = (int)v13;
  if ( *(_DWORD *)(v16 + 8) == 1 )
    v15 = (_DWORD)v13 + 8;
  v24 = v15;
  v27 = _InterlockedExchangeAdd(&`wil::details::LogFailure'::`2'::s_failureId, (_DWORD)v13 + 1) + 1;
  if ( !a8 || (v20 = *a8 == (unsigned __int16)v13, v28 = a8, v20) )
    v28 = v13;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v14;
  v30 = 0;
  v31 = 0;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && !v12 && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v21 = 1, (v24 & 2) != 0) )
  {
    v21 = 0;
  }
  if ( v12 || v21 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048, v19);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v23, v19);
    if ( v21 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v23, 0, 0, v19);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v17);
  if ( v12 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v23, OutputString);
  if ( (a9 & 2) != 0 )
    wil::RethrowCaughtException(v18);
  wil::ThrowResultException((wil *)&v23, v17);
  wil::details::WilFailFast((wil::details *)&v23, v22);
}

```

## disassembly

```asm
0x180004764  mov     [rsp-8+arg_18], rbx
0x180004769  push    rbp
0x18000476a  push    rsi
0x18000476b  push    rdi
0x18000476c  push    r12
0x18000476e  push    r13
0x180004770  push    r14
0x180004772  push    r15
0x180004774  lea     rbp, [rsp-13C0h]
0x18000477c  mov     eax, 14C0h
0x180004781  call    _alloca_probe
0x180004786  sub     rsp, rax
0x180004789  mov     r15, r8
0x18000478c  mov     r14d, edx
0x18000478f  mov     rbx, rcx
0x180004792  mov     r12, [rbp+13F0h+arg_28]
0x180004799  mov     esi, [rbp+13F0h+arg_40]
0x18000479f  and     esi, 2
0x1800047a2  jnz     short loc_1800047B3
0x1800047a4  cmp     cs:g_pfnThrowPlatformException, 0
0x1800047ac  jz      short loc_1800047B3
0x1800047ae  mov     dil, 1
0x1800047b1  jmp     short loc_1800047B6
0x1800047b3  xor     dil, dil
0x1800047b6  xor     edx, edx; Val
0x1800047b8  mov     r8d, 98h; Size
0x1800047be  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800047c3  call    memset_0
0x1800047c8  nop
0x1800047c9  xor     r8d, r8d
0x1800047cc  mov     [rbp+13F0h+OutputString], r8w
0x1800047d4  mov     [rbp+13F0h+var_1430], r8b
0x1800047d8  mov     rdx, [rbp+13F0h+arg_30]; int
0x1800047df  mov     ecx, [rdx]; this
0x1800047e1  mov     [rsp+14F0h+var_14C8], ecx
0x1800047e5  mov     eax, [rdx+4]
0x1800047e8  mov     [rsp+14F0h+var_14C4], eax
0x1800047ec  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800047f1  mov     r13d, eax
0x1800047f4  mov     dword ptr [rsp+14F0h+var_14D0], r8d
0x1800047f9  mov     ecx, r8d
0x1800047fc  lea     eax, [r8+8]
0x180004800  cmp     dword ptr [rdx+8], 1
0x180004804  cmovz   ecx, eax
0x180004807  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000480b  lea     ecx, [rax-7]
0x18000480e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004816  inc     ecx
0x180004818  mov     [rsp+14F0h+var_14C0], ecx
0x18000481c  mov     rcx, [rbp+13F0h+arg_38]
0x180004823  test    rcx, rcx
0x180004826  jz      short loc_180004833
0x180004828  cmp     [rcx], r8w
0x18000482c  mov     [rsp+14F0h+var_14B8], rcx
0x180004831  jnz     short loc_180004838
0x180004833  mov     [rsp+14F0h+var_14B8], r8
0x180004838  call    cs:__imp_GetCurrentThreadId
0x18000483e  mov     [rsp+14F0h+var_14B0], eax
0x180004842  mov     [rsp+14F0h+var_1498], r15
0x180004847  mov     [rsp+14F0h+var_1490], r14d
0x18000484c  mov     [rsp+14F0h+var_148C], r13d
0x180004851  xor     r14d, r14d
0x180004854  mov     [rsp+14F0h+var_14A8], r14
0x180004859  mov     [rsp+14F0h+var_14A0], r14
0x18000485e  mov     [rbp+13F0h+var_1448], r12
0x180004862  mov     [rbp+13F0h+var_1440], rbx
0x180004866  mov     [rsp+14F0h+var_1488], r14
0x18000486b  xorps   xmm0, xmm0
0x18000486e  xor     eax, eax
0x180004870  movups  [rbp+13F0h+var_1468], xmm0
0x180004874  mov     [rbp+13F0h+var_1458], rax
0x180004878  xorps   xmm1, xmm1
0x18000487b  movups  [rsp+14F0h+var_1480], xmm1
0x180004880  mov     [rbp+13F0h+var_1470], rax
0x180004884  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000488b  test    rax, rax
0x18000488e  jz      short loc_18000489B
0x180004890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004895  mov     [rbp+13F0h+var_1450], rax
0x180004899  jmp     short loc_18000489F
0x18000489b  mov     [rbp+13F0h+var_1450], r14
0x18000489f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800048a6  test    rax, rax
0x1800048a9  jz      short loc_1800048B5
0x1800048ab  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800048bc  test    rax, rax
0x1800048bf  jz      short loc_1800048D5
0x1800048c1  mov     r8d, 400h
0x1800048c7  lea     rdx, [rbp+13F0h+var_1430]
0x1800048cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048d5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048dc  test    rax, rax
0x1800048df  jz      short loc_1800048EB
0x1800048e1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048f2  test    rax, rax
0x1800048f5  jz      short loc_18000490D
0x1800048f7  test    dil, dil
0x1800048fa  jnz     short loc_18000490D
0x1800048fc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004901  jnz     short loc_18000490D
0x180004903  lea     rcx, [rsp+14F0h+var_14D0]
0x180004908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000490d  cmp     [rsp+14F0h+var_14C8], r14d
0x180004912  jl      short loc_18000491A
0x180004914  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000491a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r14b; bool wil::g_fIsDebuggerPresent
0x180004921  jnz     short loc_180004942
0x180004923  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000492a  test    rax, rax
0x18000492d  jz      short loc_180004938
0x18000492f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004934  test    al, al
0x180004936  jmp     short loc_180004940
0x180004938  call    cs:__imp_IsDebuggerPresent
0x18000493e  test    eax, eax
0x180004940  jz      short loc_18000494B
0x180004942  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004947  mov     bl, 1
0x180004949  jz      short loc_18000494E
0x18000494b  mov     bl, r14b
0x18000494e  test    dil, dil
0x180004951  jnz     short loc_18000497D
0x180004953  test    bl, bl
0x180004955  jnz     short loc_18000497D
0x180004957  mov     rax, cs:g_pfnResultLoggingCallback
0x18000495e  test    rax, rax
0x180004961  jz      short loc_1800049DB
0x180004963  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x18000496a  jnz     short loc_1800049DB
0x18000496c  xor     r8d, r8d
0x18000496f  xor     edx, edx
0x180004971  lea     rcx, [rsp+14F0h+var_14D0]
0x180004976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497b  jmp     short loc_1800049DB
0x18000497d  mov     r15d, 800h
0x180004983  mov     rax, cs:g_pfnResultLoggingCallback
0x18000498a  test    rax, rax
0x18000498d  jz      short loc_1800049AC
0x18000498f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x180004996  jnz     short loc_1800049AC
0x180004998  mov     r8d, r15d
0x18000499b  lea     rdx, [rbp+13F0h+OutputString]
0x1800049a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800049a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ac  cmp     [rbp+13F0h+OutputString], r14w
0x1800049b4  jnz     short loc_1800049CA
0x1800049b6  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800049bb  mov     rdx, r15; unsigned __int16 *
0x1800049be  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800049c5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800049ca  test    bl, bl
0x1800049cc  jz      short loc_1800049DB
0x1800049ce  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800049d5  call    cs:__imp_OutputDebugStringW
0x1800049db  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800049e0  jnz     short loc_1800049EB
0x1800049e2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r14b; bool wil::g_fBreakOnFailure
0x1800049e9  jz      short loc_1800049FD
0x1800049eb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800049f2  test    rax, rax
0x1800049f5  jz      short loc_1800049FD
0x1800049f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049fc  nop
0x1800049fd  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004a02  jz      short loc_180004A0F
0x180004a04  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004a09  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004a0f  test    dil, dil
0x180004a12  jz      short loc_180004A2C
0x180004a14  lea     rdx, [rbp+13F0h+OutputString]
0x180004a1b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004a20  mov     rax, cs:g_pfnThrowPlatformException
0x180004a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2c  test    esi, esi
0x180004a2e  jz      short loc_180004A35
0x180004a30  call    ?RethrowCaughtException@wil@@YAXXZ; wil::RethrowCaughtException(void)
0x180004a35  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004a3a  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180004a3f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004a44  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
