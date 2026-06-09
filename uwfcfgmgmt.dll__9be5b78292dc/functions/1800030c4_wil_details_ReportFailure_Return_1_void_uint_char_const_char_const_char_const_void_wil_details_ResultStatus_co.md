# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800030c4`
- end: `0x180003358`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002bac`

## callees

- `0x1800030c4`
- `0x180003fd4`
- `0x180004ed0`
- `0x180005830`
- `0x180005924`
- `0x18001afe2`
- `0x18001b020`
- `0x18001b0e0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000316e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000316e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003269`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003269`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800032f3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800032f3`

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
0x1800030c4  mov     [rsp-8+arg_10], rbx
0x1800030c9  push    rbp
0x1800030ca  push    rsi
0x1800030cb  push    rdi
0x1800030cc  push    r14
0x1800030ce  push    r15
0x1800030d0  lea     rbp, [rsp-13D0h]
0x1800030d8  mov     eax, 14D0h
0x1800030dd  call    _alloca_probe
0x1800030e2  sub     rsp, rax
0x1800030e5  mov     rax, cs:__security_cookie
0x1800030ec  xor     rax, rsp
0x1800030ef  mov     [rbp+13F0h+var_30], rax
0x1800030f6  mov     rdi, [rbp+13F0h+arg_28]
0x1800030fd  mov     esi, edx
0x1800030ff  mov     r14, rcx
0x180003102  xor     edx, edx; Val
0x180003104  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003109  mov     r8d, 98h; Size
0x18000310f  call    memset_0
0x180003114  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000311b  xor     r15d, r15d
0x18000311e  mov     [rbp+13F0h+OutputString], r15w
0x180003126  mov     [rbp+13F0h+var_1430], r15b
0x18000312a  mov     ecx, [rdx]; this
0x18000312c  mov     eax, [rdx+4]
0x18000312f  mov     [rsp+14F0h+var_14C8], ecx
0x180003133  mov     [rsp+14F0h+var_14C4], eax
0x180003137  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000313c  cmp     dword ptr [rdx+8], 1
0x180003140  mov     ebx, eax
0x180003142  lea     eax, [r15+8]
0x180003146  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000314e  mov     ecx, r15d
0x180003151  cmovz   ecx, eax
0x180003154  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003158  lea     ecx, [rax-7]
0x18000315b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003163  inc     ecx
0x180003165  mov     [rsp+14F0h+var_14B8], r15
0x18000316a  mov     [rsp+14F0h+var_14C0], ecx
0x18000316e  call    cs:__imp_GetCurrentThreadId
0x180003174  xorps   xmm0, xmm0
0x180003177  mov     [rsp+14F0h+var_1490], esi
0x18000317b  mov     [rsp+14F0h+var_14B0], eax
0x18000317f  xorps   xmm1, xmm1
0x180003182  lea     rax, aWil; "wil"
0x180003189  mov     [rsp+14F0h+var_148C], ebx
0x18000318d  mov     [rsp+14F0h+var_1498], rax
0x180003192  xor     eax, eax
0x180003194  mov     [rbp+13F0h+var_1458], rax
0x180003198  mov     [rbp+13F0h+var_1470], rax
0x18000319c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800031a3  mov     [rsp+14F0h+var_14A8], r15
0x1800031a8  mov     [rsp+14F0h+var_14A0], r15
0x1800031ad  mov     [rbp+13F0h+var_1448], rdi
0x1800031b1  mov     [rbp+13F0h+var_1440], r14
0x1800031b5  mov     [rsp+14F0h+var_1488], r15
0x1800031ba  movups  [rbp+13F0h+var_1468], xmm0
0x1800031be  movups  [rsp+14F0h+var_1480], xmm1
0x1800031c3  test    rax, rax
0x1800031c6  jz      short loc_1800031D3
0x1800031c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031cd  mov     [rbp+13F0h+var_1450], rax
0x1800031d1  jmp     short loc_1800031D7
0x1800031d3  mov     [rbp+13F0h+var_1450], r15
0x1800031d7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800031de  test    rax, rax
0x1800031e1  jz      short loc_1800031ED
0x1800031e3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800031f4  test    rax, rax
0x1800031f7  jz      short loc_18000320D
0x1800031f9  mov     r8d, 400h
0x1800031ff  lea     rdx, [rbp+13F0h+var_1430]
0x180003203  lea     rcx, [rsp+14F0h+var_14D0]
0x180003208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000320d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003214  test    rax, rax
0x180003217  jz      short loc_180003223
0x180003219  lea     rcx, [rsp+14F0h+var_14D0]
0x18000321e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003223  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000322a  test    rax, rax
0x18000322d  jz      short loc_180003240
0x18000322f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003234  jnz     short loc_180003240
0x180003236  lea     rcx, [rsp+14F0h+var_14D0]
0x18000323b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003240  cmp     [rsp+14F0h+var_14C8], r15d
0x180003245  jge     loc_180003347
0x18000324b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003252  jnz     short loc_180003273
0x180003254  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000325b  test    rax, rax
0x18000325e  jz      short loc_180003269
0x180003260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003265  test    al, al
0x180003267  jmp     short loc_180003271
0x180003269  call    cs:__imp_IsDebuggerPresent
0x18000326f  test    eax, eax
0x180003271  jz      short loc_18000327A
0x180003273  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003278  jz      short loc_1800032A0
0x18000327a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003281  test    rax, rax
0x180003284  jz      short loc_1800032F9
0x180003286  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000328d  jnz     short loc_1800032F9
0x18000328f  xor     r8d, r8d
0x180003292  lea     rcx, [rsp+14F0h+var_14D0]
0x180003297  xor     edx, edx
0x180003299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000329e  jmp     short loc_1800032F9
0x1800032a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800032a7  mov     ebx, 800h
0x1800032ac  test    rax, rax
0x1800032af  jz      short loc_1800032CE
0x1800032b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800032b8  jnz     short loc_1800032CE
0x1800032ba  mov     r8d, ebx
0x1800032bd  lea     rdx, [rbp+13F0h+OutputString]
0x1800032c4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ce  cmp     [rbp+13F0h+OutputString], r15w
0x1800032d6  jnz     short loc_1800032EC
0x1800032d8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800032dd  mov     rdx, rbx; unsigned __int16 *
0x1800032e0  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800032e7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800032ec  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800032f3  call    cs:__imp_OutputDebugStringW
0x1800032f9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800032fe  jnz     short loc_180003309
0x180003300  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003307  jz      short loc_18000331A
0x180003309  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003310  test    rax, rax
0x180003313  jz      short loc_18000331A
0x180003315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000331f  jnz     short loc_18000334D
0x180003321  mov     rcx, [rbp+13F0h+var_30]
0x180003328  xor     rcx, rsp; StackCookie
0x18000332b  call    __security_check_cookie
0x180003330  mov     rbx, [rsp+14F0h+arg_10]
0x180003338  add     rsp, 14D0h
0x18000333f  pop     r15
0x180003341  pop     r14
0x180003343  pop     rdi
0x180003344  pop     rsi
0x180003345  pop     rbp
0x180003346  retn
0x180003347  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000334d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003352  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
