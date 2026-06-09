# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003444`
- end: `0x1400036d8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002f24`

## callees

- `0x1400015a0`
- `0x140002254`
- `0x140003444`
- `0x140004944`
- `0x140005aa0`
- `0x1400069a0`
- `0x140006ce8`
- `0x14000b180`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400035e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400035e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003673`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003673`

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
0x140003444  mov     [rsp-8+arg_10], rbx
0x140003449  push    rbp
0x14000344a  push    rsi
0x14000344b  push    rdi
0x14000344c  push    r14
0x14000344e  push    r15
0x140003450  lea     rbp, [rsp-13D0h]
0x140003458  mov     eax, 14D0h
0x14000345d  call    _alloca_probe
0x140003462  sub     rsp, rax
0x140003465  mov     rax, cs:__security_cookie
0x14000346c  xor     rax, rsp
0x14000346f  mov     [rbp+13F0h+var_30], rax
0x140003476  mov     rdi, [rbp+13F0h+arg_28]
0x14000347d  mov     esi, edx
0x14000347f  mov     r14, rcx
0x140003482  xor     edx, edx; Val
0x140003484  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003489  mov     r8d, 98h; Size
0x14000348f  call    memset_0
0x140003494  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000349b  xor     r15d, r15d
0x14000349e  mov     [rbp+13F0h+OutputString], r15w
0x1400034a6  mov     [rbp+13F0h+var_1430], r15b
0x1400034aa  mov     ecx, [rdx]; this
0x1400034ac  mov     eax, [rdx+4]
0x1400034af  mov     [rsp+14F0h+var_14C8], ecx
0x1400034b3  mov     [rsp+14F0h+var_14C4], eax
0x1400034b7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400034bc  cmp     dword ptr [rdx+8], 1
0x1400034c0  mov     ebx, eax
0x1400034c2  lea     eax, [r15+8]
0x1400034c6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400034ce  mov     ecx, r15d
0x1400034d1  cmovz   ecx, eax
0x1400034d4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400034d8  lea     ecx, [rax-7]
0x1400034db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400034e3  inc     ecx
0x1400034e5  mov     [rsp+14F0h+var_14B8], r15
0x1400034ea  mov     [rsp+14F0h+var_14C0], ecx
0x1400034ee  call    cs:__imp_GetCurrentThreadId
0x1400034f4  xorps   xmm0, xmm0
0x1400034f7  mov     [rsp+14F0h+var_1490], esi
0x1400034fb  mov     [rsp+14F0h+var_14B0], eax
0x1400034ff  xorps   xmm1, xmm1
0x140003502  lea     rax, aWil; "wil"
0x140003509  mov     [rsp+14F0h+var_148C], ebx
0x14000350d  mov     [rsp+14F0h+var_1498], rax
0x140003512  xor     eax, eax
0x140003514  mov     [rbp+13F0h+var_1458], rax
0x140003518  mov     [rbp+13F0h+var_1470], rax
0x14000351c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003523  mov     [rsp+14F0h+var_14A8], r15
0x140003528  mov     [rsp+14F0h+var_14A0], r15
0x14000352d  mov     [rbp+13F0h+var_1448], rdi
0x140003531  mov     [rbp+13F0h+var_1440], r14
0x140003535  mov     [rsp+14F0h+var_1488], r15
0x14000353a  movups  [rbp+13F0h+var_1468], xmm0
0x14000353e  movups  [rsp+14F0h+var_1480], xmm1
0x140003543  test    rax, rax
0x140003546  jz      short loc_140003553
0x140003548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000354d  mov     [rbp+13F0h+var_1450], rax
0x140003551  jmp     short loc_140003557
0x140003553  mov     [rbp+13F0h+var_1450], r15
0x140003557  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000355e  test    rax, rax
0x140003561  jz      short loc_14000356D
0x140003563  lea     rcx, [rsp+14F0h+var_14D0]
0x140003568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000356d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003574  test    rax, rax
0x140003577  jz      short loc_14000358D
0x140003579  mov     r8d, 400h
0x14000357f  lea     rdx, [rbp+13F0h+var_1430]
0x140003583  lea     rcx, [rsp+14F0h+var_14D0]
0x140003588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000358d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003594  test    rax, rax
0x140003597  jz      short loc_1400035A3
0x140003599  lea     rcx, [rsp+14F0h+var_14D0]
0x14000359e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400035aa  test    rax, rax
0x1400035ad  jz      short loc_1400035C0
0x1400035af  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400035b4  jnz     short loc_1400035C0
0x1400035b6  lea     rcx, [rsp+14F0h+var_14D0]
0x1400035bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035c0  cmp     [rsp+14F0h+var_14C8], r15d
0x1400035c5  jge     loc_1400036C7
0x1400035cb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400035d2  jnz     short loc_1400035F3
0x1400035d4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400035db  test    rax, rax
0x1400035de  jz      short loc_1400035E9
0x1400035e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035e5  test    al, al
0x1400035e7  jmp     short loc_1400035F1
0x1400035e9  call    cs:__imp_IsDebuggerPresent
0x1400035ef  test    eax, eax
0x1400035f1  jz      short loc_1400035FA
0x1400035f3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400035f8  jz      short loc_140003620
0x1400035fa  mov     rax, cs:g_pfnResultLoggingCallback
0x140003601  test    rax, rax
0x140003604  jz      short loc_140003679
0x140003606  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000360d  jnz     short loc_140003679
0x14000360f  xor     r8d, r8d
0x140003612  lea     rcx, [rsp+14F0h+var_14D0]
0x140003617  xor     edx, edx
0x140003619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000361e  jmp     short loc_140003679
0x140003620  mov     rax, cs:g_pfnResultLoggingCallback
0x140003627  mov     ebx, 800h
0x14000362c  test    rax, rax
0x14000362f  jz      short loc_14000364E
0x140003631  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003638  jnz     short loc_14000364E
0x14000363a  mov     r8d, ebx
0x14000363d  lea     rdx, [rbp+13F0h+OutputString]
0x140003644  lea     rcx, [rsp+14F0h+var_14D0]
0x140003649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000364e  cmp     [rbp+13F0h+OutputString], r15w
0x140003656  jnz     short loc_14000366C
0x140003658  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000365d  mov     rdx, rbx; unsigned __int16 *
0x140003660  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003667  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000366c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003673  call    cs:__imp_OutputDebugStringW
0x140003679  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000367e  jnz     short loc_140003689
0x140003680  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140003687  jz      short loc_14000369A
0x140003689  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003690  test    rax, rax
0x140003693  jz      short loc_14000369A
0x140003695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000369a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000369f  jnz     short loc_1400036CD
0x1400036a1  mov     rcx, [rbp+13F0h+var_30]
0x1400036a8  xor     rcx, rsp; StackCookie
0x1400036ab  call    __security_check_cookie
0x1400036b0  mov     rbx, [rsp+14F0h+arg_10]
0x1400036b8  add     rsp, 14D0h
0x1400036bf  pop     r15
0x1400036c1  pop     r14
0x1400036c3  pop     rdi
0x1400036c4  pop     rsi
0x1400036c5  pop     rbp
0x1400036c6  retn
0x1400036c7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400036cd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400036d2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
