# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400031e8`
- end: `0x140003475`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002cc8`

## callees

- `0x140002130`
- `0x140002c38`
- `0x1400031e8`
- `0x140004354`
- `0x140005250`
- `0x1400061a0`
- `0x14000627c`
- `0x14000ac20`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003296`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003296`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003414`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003414`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000338a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000338a`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x1400031e8  push    rbp
0x1400031ea  push    rbx
0x1400031eb  push    rsi
0x1400031ec  push    rdi
0x1400031ed  push    r12
0x1400031ef  push    r14
0x1400031f1  push    r15
0x1400031f3  lea     rbp, [rsp-13D0h]
0x1400031fb  mov     eax, 14D0h
0x140003200  call    _alloca_probe
0x140003205  sub     rsp, rax
0x140003208  mov     rax, cs:__security_cookie
0x14000320f  xor     rax, rsp
0x140003212  mov     [rbp+1400h+var_40], rax
0x140003219  mov     r14, r8
0x14000321c  mov     esi, edx
0x14000321e  mov     r15, rcx
0x140003221  mov     rdi, [rbp+1400h+arg_28]
0x140003228  xor     edx, edx; Val
0x14000322a  mov     r8d, 98h; Size
0x140003230  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003235  call    memset_0
0x14000323a  nop
0x14000323b  xor     r12d, r12d
0x14000323e  mov     [rbp+1400h+OutputString], r12w
0x140003246  mov     [rbp+1400h+var_1440], r12b
0x14000324a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140003251  mov     ecx, [rdx]; this
0x140003253  mov     [rsp+1500h+var_14D8], ecx
0x140003257  mov     eax, [rdx+4]
0x14000325a  mov     [rsp+1500h+var_14D4], eax
0x14000325e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003263  mov     ebx, eax
0x140003265  mov     dword ptr [rsp+1500h+var_14E0], 1
0x14000326d  mov     ecx, r12d
0x140003270  lea     eax, [r12+8]
0x140003275  cmp     dword ptr [rdx+8], 1
0x140003279  cmovz   ecx, eax
0x14000327c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003280  lea     ecx, [rax-7]
0x140003283  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000328b  inc     ecx
0x14000328d  mov     [rsp+1500h+var_14D0], ecx
0x140003291  mov     [rsp+1500h+var_14C8], r12
0x140003296  call    cs:__imp_GetCurrentThreadId
0x14000329c  mov     [rsp+1500h+var_14C0], eax
0x1400032a0  mov     [rsp+1500h+var_14A8], r14
0x1400032a5  mov     [rsp+1500h+var_14A0], esi
0x1400032a9  mov     [rsp+1500h+var_149C], ebx
0x1400032ad  mov     [rsp+1500h+var_14B8], r12
0x1400032b2  mov     [rsp+1500h+var_14B0], r12
0x1400032b7  mov     [rbp+1400h+var_1458], rdi
0x1400032bb  mov     [rbp+1400h+var_1450], r15
0x1400032bf  mov     [rsp+1500h+var_1498], r12
0x1400032c4  xorps   xmm0, xmm0
0x1400032c7  xor     eax, eax
0x1400032c9  movups  [rbp+1400h+var_1478], xmm0
0x1400032cd  mov     [rbp+1400h+var_1468], rax
0x1400032d1  xorps   xmm1, xmm1
0x1400032d4  movups  [rsp+1500h+var_1490], xmm1
0x1400032d9  mov     [rbp+1400h+var_1480], rax
0x1400032dd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400032e4  test    rax, rax
0x1400032e7  jz      short loc_1400032F4
0x1400032e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032ee  mov     [rbp+1400h+var_1460], rax
0x1400032f2  jmp     short loc_1400032F8
0x1400032f4  mov     [rbp+1400h+var_1460], r12
0x1400032f8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400032ff  test    rax, rax
0x140003302  jz      short loc_14000330E
0x140003304  lea     rcx, [rsp+1500h+var_14E0]
0x140003309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000330e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003315  test    rax, rax
0x140003318  jz      short loc_14000332E
0x14000331a  mov     r8d, 400h
0x140003320  lea     rdx, [rbp+1400h+var_1440]
0x140003324  lea     rcx, [rsp+1500h+var_14E0]
0x140003329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000332e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003335  test    rax, rax
0x140003338  jz      short loc_140003344
0x14000333a  lea     rcx, [rsp+1500h+var_14E0]
0x14000333f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003344  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000334b  test    rax, rax
0x14000334e  jz      short loc_140003361
0x140003350  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003355  jnz     short loc_140003361
0x140003357  lea     rcx, [rsp+1500h+var_14E0]
0x14000335c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003361  cmp     [rsp+1500h+var_14D8], r12d
0x140003366  jge     loc_14000346F
0x14000336c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003373  jnz     short loc_140003394
0x140003375  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000337c  test    rax, rax
0x14000337f  jz      short loc_14000338A
0x140003381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003386  test    al, al
0x140003388  jmp     short loc_140003392
0x14000338a  call    cs:__imp_IsDebuggerPresent
0x140003390  test    eax, eax
0x140003392  jz      short loc_14000339B
0x140003394  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003399  jz      short loc_1400033C1
0x14000339b  mov     rax, cs:g_pfnResultLoggingCallback
0x1400033a2  test    rax, rax
0x1400033a5  jz      short loc_14000341A
0x1400033a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400033ae  jnz     short loc_14000341A
0x1400033b0  xor     r8d, r8d
0x1400033b3  xor     edx, edx
0x1400033b5  lea     rcx, [rsp+1500h+var_14E0]
0x1400033ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033bf  jmp     short loc_14000341A
0x1400033c1  mov     ebx, 800h
0x1400033c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400033cd  test    rax, rax
0x1400033d0  jz      short loc_1400033EF
0x1400033d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400033d9  jnz     short loc_1400033EF
0x1400033db  mov     r8d, ebx
0x1400033de  lea     rdx, [rbp+1400h+OutputString]
0x1400033e5  lea     rcx, [rsp+1500h+var_14E0]
0x1400033ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033ef  cmp     [rbp+1400h+OutputString], r12w
0x1400033f7  jnz     short loc_14000340D
0x1400033f9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400033fe  mov     rdx, rbx; unsigned __int16 *
0x140003401  lea     rcx, [rbp+1400h+OutputString]; this
0x140003408  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000340d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003414  call    cs:__imp_OutputDebugStringW
0x14000341a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000341f  jnz     short loc_14000342A
0x140003421  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003428  jz      short loc_14000343C
0x14000342a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003431  test    rax, rax
0x140003434  jz      short loc_14000343C
0x140003436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000343b  nop
0x14000343c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003441  jnz     short loc_140003464
0x140003443  mov     rcx, [rbp+1400h+var_40]
0x14000344a  xor     rcx, rsp; StackCookie
0x14000344d  call    __security_check_cookie
0x140003452  add     rsp, 14D0h
0x140003459  pop     r15
0x14000345b  pop     r14
0x14000345d  pop     r12
0x14000345f  pop     rdi
0x140003460  pop     rsi
0x140003461  pop     rbx
0x140003462  pop     rbp
0x140003463  retn
0x140003464  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003469  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000346f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
