# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003464`
- end: `0x1400036f8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002f44`

## callees

- `0x140003464`
- `0x140003fdc`
- `0x140004b98`
- `0x140005354`
- `0x140005464`
- `0x14001755a`
- `0x1400175a0`
- `0x1400175d0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000350e`
- `KERNEL32!GetCurrentThreadId` at `0x14000350e`
- `KERNEL32!OutputDebugStringW` at `0x140003693`
- `KERNEL32!OutputDebugStringW` at `0x140003693`
- `KERNEL32!IsDebuggerPresent` at `0x140003609`
- `KERNEL32!IsDebuggerPresent` at `0x140003609`

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
0x140003464  mov     [rsp-8+arg_10], rbx
0x140003469  push    rbp
0x14000346a  push    rsi
0x14000346b  push    rdi
0x14000346c  push    r14
0x14000346e  push    r15
0x140003470  lea     rbp, [rsp-13D0h]
0x140003478  mov     eax, 14D0h
0x14000347d  call    _alloca_probe
0x140003482  sub     rsp, rax
0x140003485  mov     rax, cs:__security_cookie
0x14000348c  xor     rax, rsp
0x14000348f  mov     [rbp+13F0h+var_30], rax
0x140003496  mov     rdi, [rbp+13F0h+arg_28]
0x14000349d  mov     esi, edx
0x14000349f  mov     r14, rcx
0x1400034a2  xor     edx, edx; Val
0x1400034a4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400034a9  mov     r8d, 98h; Size
0x1400034af  call    memset_0
0x1400034b4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400034bb  xor     r15d, r15d
0x1400034be  mov     [rbp+13F0h+OutputString], r15w
0x1400034c6  mov     [rbp+13F0h+var_1430], r15b
0x1400034ca  mov     ecx, [rdx]; this
0x1400034cc  mov     eax, [rdx+4]
0x1400034cf  mov     [rsp+14F0h+var_14C8], ecx
0x1400034d3  mov     [rsp+14F0h+var_14C4], eax
0x1400034d7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400034dc  cmp     dword ptr [rdx+8], 1
0x1400034e0  mov     ebx, eax
0x1400034e2  lea     eax, [r15+8]
0x1400034e6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400034ee  mov     ecx, r15d
0x1400034f1  cmovz   ecx, eax
0x1400034f4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400034f8  lea     ecx, [rax-7]
0x1400034fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003503  inc     ecx
0x140003505  mov     [rsp+14F0h+var_14B8], r15
0x14000350a  mov     [rsp+14F0h+var_14C0], ecx
0x14000350e  call    cs:__imp_GetCurrentThreadId
0x140003514  xorps   xmm0, xmm0
0x140003517  mov     [rsp+14F0h+var_1490], esi
0x14000351b  mov     [rsp+14F0h+var_14B0], eax
0x14000351f  xorps   xmm1, xmm1
0x140003522  lea     rax, aWil; "wil"
0x140003529  mov     [rsp+14F0h+var_148C], ebx
0x14000352d  mov     [rsp+14F0h+var_1498], rax
0x140003532  xor     eax, eax
0x140003534  mov     [rbp+13F0h+var_1458], rax
0x140003538  mov     [rbp+13F0h+var_1470], rax
0x14000353c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003543  mov     [rsp+14F0h+var_14A8], r15
0x140003548  mov     [rsp+14F0h+var_14A0], r15
0x14000354d  mov     [rbp+13F0h+var_1448], rdi
0x140003551  mov     [rbp+13F0h+var_1440], r14
0x140003555  mov     [rsp+14F0h+var_1488], r15
0x14000355a  movups  [rbp+13F0h+var_1468], xmm0
0x14000355e  movups  [rsp+14F0h+var_1480], xmm1
0x140003563  test    rax, rax
0x140003566  jz      short loc_140003573
0x140003568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000356d  mov     [rbp+13F0h+var_1450], rax
0x140003571  jmp     short loc_140003577
0x140003573  mov     [rbp+13F0h+var_1450], r15
0x140003577  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000357e  test    rax, rax
0x140003581  jz      short loc_14000358D
0x140003583  lea     rcx, [rsp+14F0h+var_14D0]
0x140003588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000358d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003594  test    rax, rax
0x140003597  jz      short loc_1400035AD
0x140003599  mov     r8d, 400h
0x14000359f  lea     rdx, [rbp+13F0h+var_1430]
0x1400035a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400035a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035ad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400035b4  test    rax, rax
0x1400035b7  jz      short loc_1400035C3
0x1400035b9  lea     rcx, [rsp+14F0h+var_14D0]
0x1400035be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400035ca  test    rax, rax
0x1400035cd  jz      short loc_1400035E0
0x1400035cf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400035d4  jnz     short loc_1400035E0
0x1400035d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1400035db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035e0  cmp     [rsp+14F0h+var_14C8], r15d
0x1400035e5  jge     loc_1400036E7
0x1400035eb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400035f2  jnz     short loc_140003613
0x1400035f4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400035fb  test    rax, rax
0x1400035fe  jz      short loc_140003609
0x140003600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003605  test    al, al
0x140003607  jmp     short loc_140003611
0x140003609  call    cs:__imp_IsDebuggerPresent
0x14000360f  test    eax, eax
0x140003611  jz      short loc_14000361A
0x140003613  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003618  jz      short loc_140003640
0x14000361a  mov     rax, cs:g_pfnResultLoggingCallback
0x140003621  test    rax, rax
0x140003624  jz      short loc_140003699
0x140003626  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000362d  jnz     short loc_140003699
0x14000362f  xor     r8d, r8d
0x140003632  lea     rcx, [rsp+14F0h+var_14D0]
0x140003637  xor     edx, edx
0x140003639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000363e  jmp     short loc_140003699
0x140003640  mov     rax, cs:g_pfnResultLoggingCallback
0x140003647  mov     ebx, 800h
0x14000364c  test    rax, rax
0x14000364f  jz      short loc_14000366E
0x140003651  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003658  jnz     short loc_14000366E
0x14000365a  mov     r8d, ebx
0x14000365d  lea     rdx, [rbp+13F0h+OutputString]
0x140003664  lea     rcx, [rsp+14F0h+var_14D0]
0x140003669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000366e  cmp     [rbp+13F0h+OutputString], r15w
0x140003676  jnz     short loc_14000368C
0x140003678  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000367d  mov     rdx, rbx; unsigned __int16 *
0x140003680  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003687  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000368c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003693  call    cs:__imp_OutputDebugStringW
0x140003699  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000369e  jnz     short loc_1400036A9
0x1400036a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400036a7  jz      short loc_1400036BA
0x1400036a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400036b0  test    rax, rax
0x1400036b3  jz      short loc_1400036BA
0x1400036b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036ba  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400036bf  jnz     short loc_1400036ED
0x1400036c1  mov     rcx, [rbp+13F0h+var_30]
0x1400036c8  xor     rcx, rsp; StackCookie
0x1400036cb  call    __security_check_cookie
0x1400036d0  mov     rbx, [rsp+14F0h+arg_10]
0x1400036d8  add     rsp, 14D0h
0x1400036df  pop     r15
0x1400036e1  pop     r14
0x1400036e3  pop     rdi
0x1400036e4  pop     rsi
0x1400036e5  pop     rbp
0x1400036e6  retn
0x1400036e7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400036ed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400036f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
