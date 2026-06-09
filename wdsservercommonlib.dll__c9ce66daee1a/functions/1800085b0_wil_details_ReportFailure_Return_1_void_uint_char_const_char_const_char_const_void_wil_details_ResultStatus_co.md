# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800085b0`
- end: `0x180008857`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008074`

## callees

- `0x1800085b0`
- `0x18000a354`
- `0x18000b9ac`
- `0x18000d87c`
- `0x18000da68`
- `0x18002f3ba`
- `0x18002f3e0`
- `0x18002f4a0`
- `0x180030010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000875b`
- `KERNEL32!IsDebuggerPresent` at `0x18000875b`
- `KERNEL32!OutputDebugStringW` at `0x1800087eb`
- `KERNEL32!OutputDebugStringW` at `0x1800087eb`
- `KERNEL32!GetCurrentThreadId` at `0x18000865a`
- `KERNEL32!GetCurrentThreadId` at `0x18000865a`

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
0x1800085b0  mov     [rsp-8+arg_10], rbx
0x1800085b5  push    rbp
0x1800085b6  push    rsi
0x1800085b7  push    rdi
0x1800085b8  push    r14
0x1800085ba  push    r15
0x1800085bc  lea     rbp, [rsp-13D0h]
0x1800085c4  mov     eax, 14D0h
0x1800085c9  call    _alloca_probe
0x1800085ce  sub     rsp, rax
0x1800085d1  mov     rax, cs:__security_cookie
0x1800085d8  xor     rax, rsp
0x1800085db  mov     [rbp+13F0h+var_30], rax
0x1800085e2  mov     rdi, [rbp+13F0h+arg_28]
0x1800085e9  mov     esi, edx
0x1800085eb  mov     r14, rcx
0x1800085ee  xor     edx, edx; Val
0x1800085f0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800085f5  mov     r8d, 98h; Size
0x1800085fb  call    memset_0
0x180008600  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180008607  xor     r15d, r15d
0x18000860a  mov     [rbp+13F0h+OutputString], r15w
0x180008612  mov     [rbp+13F0h+var_1430], r15b
0x180008616  mov     ecx, [rdx]; this
0x180008618  mov     eax, [rdx+4]
0x18000861b  mov     [rsp+14F0h+var_14C8], ecx
0x18000861f  mov     [rsp+14F0h+var_14C4], eax
0x180008623  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008628  cmp     dword ptr [rdx+8], 1
0x18000862c  mov     ebx, eax
0x18000862e  lea     eax, [r15+8]
0x180008632  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000863a  mov     ecx, r15d
0x18000863d  cmovz   ecx, eax
0x180008640  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008644  lea     ecx, [rax-7]
0x180008647  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000864f  inc     ecx
0x180008651  mov     [rsp+14F0h+var_14B8], r15
0x180008656  mov     [rsp+14F0h+var_14C0], ecx
0x18000865a  call    cs:__imp_GetCurrentThreadId
0x180008661  nop     dword ptr [rax+rax+00h]
0x180008666  xorps   xmm0, xmm0
0x180008669  mov     [rsp+14F0h+var_1490], esi
0x18000866d  mov     [rsp+14F0h+var_14B0], eax
0x180008671  xorps   xmm1, xmm1
0x180008674  lea     rax, aWil; "wil"
0x18000867b  mov     [rsp+14F0h+var_148C], ebx
0x18000867f  mov     [rsp+14F0h+var_1498], rax
0x180008684  xor     eax, eax
0x180008686  mov     [rbp+13F0h+var_1458], rax
0x18000868a  mov     [rbp+13F0h+var_1470], rax
0x18000868e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008695  mov     [rsp+14F0h+var_14A8], r15
0x18000869a  mov     [rsp+14F0h+var_14A0], r15
0x18000869f  mov     [rbp+13F0h+var_1448], rdi
0x1800086a3  mov     [rbp+13F0h+var_1440], r14
0x1800086a7  mov     [rsp+14F0h+var_1488], r15
0x1800086ac  movups  [rbp+13F0h+var_1468], xmm0
0x1800086b0  movups  [rsp+14F0h+var_1480], xmm1
0x1800086b5  test    rax, rax
0x1800086b8  jz      short loc_1800086C5
0x1800086ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086bf  mov     [rbp+13F0h+var_1450], rax
0x1800086c3  jmp     short loc_1800086C9
0x1800086c5  mov     [rbp+13F0h+var_1450], r15
0x1800086c9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800086d0  test    rax, rax
0x1800086d3  jz      short loc_1800086DF
0x1800086d5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800086da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086df  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800086e6  test    rax, rax
0x1800086e9  jz      short loc_1800086FF
0x1800086eb  mov     r8d, 400h
0x1800086f1  lea     rdx, [rbp+13F0h+var_1430]
0x1800086f5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800086fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008706  test    rax, rax
0x180008709  jz      short loc_180008715
0x18000870b  lea     rcx, [rsp+14F0h+var_14D0]
0x180008710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008715  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000871c  test    rax, rax
0x18000871f  jz      short loc_180008732
0x180008721  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008726  jnz     short loc_180008732
0x180008728  lea     rcx, [rsp+14F0h+var_14D0]
0x18000872d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008732  cmp     [rsp+14F0h+var_14C8], r15d
0x180008737  jge     loc_180008846
0x18000873d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180008744  jnz     short loc_18000876B
0x180008746  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000874d  test    rax, rax
0x180008750  jz      short loc_18000875B
0x180008752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008757  test    al, al
0x180008759  jmp     short loc_180008769
0x18000875b  call    cs:__imp_IsDebuggerPresent
0x180008762  nop     dword ptr [rax+rax+00h]
0x180008767  test    eax, eax
0x180008769  jz      short loc_180008772
0x18000876b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008770  jz      short loc_180008798
0x180008772  mov     rax, cs:g_pfnResultLoggingCallback
0x180008779  test    rax, rax
0x18000877c  jz      short loc_1800087F7
0x18000877e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008785  jnz     short loc_1800087F7
0x180008787  xor     r8d, r8d
0x18000878a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000878f  xor     edx, edx
0x180008791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008796  jmp     short loc_1800087F7
0x180008798  mov     rax, cs:g_pfnResultLoggingCallback
0x18000879f  mov     ebx, 800h
0x1800087a4  test    rax, rax
0x1800087a7  jz      short loc_1800087C6
0x1800087a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800087b0  jnz     short loc_1800087C6
0x1800087b2  mov     r8d, ebx
0x1800087b5  lea     rdx, [rbp+13F0h+OutputString]
0x1800087bc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800087c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c6  cmp     [rbp+13F0h+OutputString], r15w
0x1800087ce  jnz     short loc_1800087E4
0x1800087d0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800087d5  mov     rdx, rbx; unsigned __int16 *
0x1800087d8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800087df  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800087e4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800087eb  call    cs:__imp_OutputDebugStringW
0x1800087f2  nop     dword ptr [rax+rax+00h]
0x1800087f7  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800087fc  jnz     short loc_180008807
0x1800087fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180008805  jz      short loc_180008818
0x180008807  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000880e  test    rax, rax
0x180008811  jz      short loc_180008818
0x180008813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008818  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000881d  jnz     short loc_18000884C
0x18000881f  mov     rcx, [rbp+13F0h+var_30]
0x180008826  xor     rcx, rsp; StackCookie
0x180008829  call    __security_check_cookie
0x18000882e  mov     rbx, [rsp+14F0h+arg_10]
0x180008836  add     rsp, 14D0h
0x18000883d  pop     r15
0x18000883f  pop     r14
0x180008841  pop     rdi
0x180008842  pop     rsi
0x180008843  pop     rbp
0x180008844  retn
0x180008846  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000884c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008851  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
