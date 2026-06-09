# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800763d4`
- end: `0x18007665f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800760f4`

## callees

- `0x180014acc`
- `0x180015190`
- `0x180015ea8`
- `0x1800763d4`
- `0x180077a80`
- `0x180079788`
- `0x1800798f0`
- `0x1800859f0`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076481`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076481`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180076575`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180076575`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800765ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800765ff`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x1800763d4  push    rbp
0x1800763d6  push    rbx
0x1800763d7  push    rsi
0x1800763d8  push    rdi
0x1800763d9  push    r12
0x1800763db  push    r14
0x1800763dd  push    r15
0x1800763df  lea     rbp, [rsp-13D0h]
0x1800763e7  mov     eax, 14D0h
0x1800763ec  call    _alloca_probe
0x1800763f1  sub     rsp, rax
0x1800763f4  mov     rax, cs:__security_cookie
0x1800763fb  xor     rax, rsp
0x1800763fe  mov     [rbp+1400h+var_40], rax
0x180076405  mov     rdi, [rbp+1400h+arg_28]
0x18007640c  mov     r14, r8
0x18007640f  mov     esi, edx
0x180076411  mov     r15, rcx
0x180076414  xor     edx, edx; Val
0x180076416  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18007641b  mov     r8d, 98h; Size
0x180076421  call    memset_0
0x180076426  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18007642d  xor     r12d, r12d
0x180076430  mov     [rbp+1400h+OutputString], r12w
0x180076438  mov     [rbp+1400h+var_1440], r12b
0x18007643c  mov     ecx, [rdx]; this
0x18007643e  mov     eax, [rdx+4]
0x180076441  mov     [rsp+1500h+var_14D8], ecx
0x180076445  mov     [rsp+1500h+var_14D4], eax
0x180076449  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18007644e  cmp     dword ptr [rdx+8], 1
0x180076452  mov     ebx, eax
0x180076454  lea     eax, [r12+8]
0x180076459  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180076461  mov     ecx, r12d
0x180076464  cmovz   ecx, eax
0x180076467  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18007646b  lea     ecx, [rax-7]
0x18007646e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180076476  inc     ecx
0x180076478  mov     [rsp+1500h+var_14C8], r12
0x18007647d  mov     [rsp+1500h+var_14D0], ecx
0x180076481  call    cs:__imp_GetCurrentThreadId
0x180076487  xorps   xmm0, xmm0
0x18007648a  mov     [rsp+1500h+var_14A8], r14
0x18007648f  mov     [rsp+1500h+var_14C0], eax
0x180076493  xorps   xmm1, xmm1
0x180076496  xor     eax, eax
0x180076498  mov     [rsp+1500h+var_14A0], esi
0x18007649c  mov     [rbp+1400h+var_1468], rax
0x1800764a0  mov     [rbp+1400h+var_1480], rax
0x1800764a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800764ab  mov     [rsp+1500h+var_149C], ebx
0x1800764af  mov     [rsp+1500h+var_14B8], r12
0x1800764b4  mov     [rsp+1500h+var_14B0], r12
0x1800764b9  mov     [rbp+1400h+var_1458], rdi
0x1800764bd  mov     [rbp+1400h+var_1450], r15
0x1800764c1  mov     [rsp+1500h+var_1498], r12
0x1800764c6  movups  [rbp+1400h+var_1478], xmm0
0x1800764ca  movups  [rsp+1500h+var_1490], xmm1
0x1800764cf  test    rax, rax
0x1800764d2  jz      short loc_1800764DF
0x1800764d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800764d9  mov     [rbp+1400h+var_1460], rax
0x1800764dd  jmp     short loc_1800764E3
0x1800764df  mov     [rbp+1400h+var_1460], r12
0x1800764e3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800764ea  test    rax, rax
0x1800764ed  jz      short loc_1800764F9
0x1800764ef  lea     rcx, [rsp+1500h+var_14E0]
0x1800764f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800764f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180076500  test    rax, rax
0x180076503  jz      short loc_180076519
0x180076505  mov     r8d, 400h
0x18007650b  lea     rdx, [rbp+1400h+var_1440]
0x18007650f  lea     rcx, [rsp+1500h+var_14E0]
0x180076514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076519  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180076520  test    rax, rax
0x180076523  jz      short loc_18007652F
0x180076525  lea     rcx, [rsp+1500h+var_14E0]
0x18007652a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007652f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180076536  test    rax, rax
0x180076539  jz      short loc_18007654C
0x18007653b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180076540  jnz     short loc_18007654C
0x180076542  lea     rcx, [rsp+1500h+var_14E0]
0x180076547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007654c  cmp     [rsp+1500h+var_14D8], r12d
0x180076551  jge     loc_18007664E
0x180076557  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18007655e  jnz     short loc_18007657F
0x180076560  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180076567  test    rax, rax
0x18007656a  jz      short loc_180076575
0x18007656c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076571  test    al, al
0x180076573  jmp     short loc_18007657D
0x180076575  call    cs:__imp_IsDebuggerPresent
0x18007657b  test    eax, eax
0x18007657d  jz      short loc_180076586
0x18007657f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180076584  jz      short loc_1800765AC
0x180076586  mov     rax, cs:g_pfnResultLoggingCallback
0x18007658d  test    rax, rax
0x180076590  jz      short loc_180076605
0x180076592  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180076599  jnz     short loc_180076605
0x18007659b  xor     r8d, r8d
0x18007659e  lea     rcx, [rsp+1500h+var_14E0]
0x1800765a3  xor     edx, edx
0x1800765a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800765aa  jmp     short loc_180076605
0x1800765ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800765b3  mov     ebx, 800h
0x1800765b8  test    rax, rax
0x1800765bb  jz      short loc_1800765DA
0x1800765bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800765c4  jnz     short loc_1800765DA
0x1800765c6  mov     r8d, ebx
0x1800765c9  lea     rdx, [rbp+1400h+OutputString]
0x1800765d0  lea     rcx, [rsp+1500h+var_14E0]
0x1800765d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800765da  cmp     [rbp+1400h+OutputString], r12w
0x1800765e2  jnz     short loc_1800765F8
0x1800765e4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800765e9  mov     rdx, rbx; unsigned __int16 *
0x1800765ec  lea     rcx, [rbp+1400h+OutputString]; this
0x1800765f3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800765f8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800765ff  call    cs:__imp_OutputDebugStringW
0x180076605  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18007660a  jnz     short loc_180076615
0x18007660c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180076613  jz      short loc_180076626
0x180076615  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18007661c  test    rax, rax
0x18007661f  jz      short loc_180076626
0x180076621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076626  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18007662b  jnz     short loc_180076654
0x18007662d  mov     rcx, [rbp+1400h+var_40]
0x180076634  xor     rcx, rsp; StackCookie
0x180076637  call    __security_check_cookie
0x18007663c  add     rsp, 14D0h
0x180076643  pop     r15
0x180076645  pop     r14
0x180076647  pop     r12
0x180076649  pop     rdi
0x18007664a  pop     rsi
0x18007664b  pop     rbx
0x18007664c  pop     rbp
0x18007664d  retn
0x18007664e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180076654  lea     rcx, [rsp+1500h+var_14E0]; this
0x180076659  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
