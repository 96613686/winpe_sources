# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007284`
- end: `0x180007518`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006d8c`

## callees

- `0x180007284`
- `0x180008a04`
- `0x18000a5c0`
- `0x18000bae0`
- `0x18000bc9c`
- `0x18000cfbe`
- `0x18000cff0`
- `0x18000d080`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000732e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000732e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007429`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007429`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800074b3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800074b3`

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
0x180007284  mov     [rsp-8+arg_10], rbx
0x180007289  push    rbp
0x18000728a  push    rsi
0x18000728b  push    rdi
0x18000728c  push    r14
0x18000728e  push    r15
0x180007290  lea     rbp, [rsp-13D0h]
0x180007298  mov     eax, 14D0h
0x18000729d  call    _alloca_probe
0x1800072a2  sub     rsp, rax
0x1800072a5  mov     rax, cs:__security_cookie
0x1800072ac  xor     rax, rsp
0x1800072af  mov     [rbp+13F0h+var_30], rax
0x1800072b6  mov     rdi, [rbp+13F0h+arg_28]
0x1800072bd  mov     esi, edx
0x1800072bf  mov     r14, rcx
0x1800072c2  xor     edx, edx; Val
0x1800072c4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800072c9  mov     r8d, 98h; Size
0x1800072cf  call    memset_0
0x1800072d4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800072db  xor     r15d, r15d
0x1800072de  mov     [rbp+13F0h+OutputString], r15w
0x1800072e6  mov     [rbp+13F0h+var_1430], r15b
0x1800072ea  mov     ecx, [rdx]; this
0x1800072ec  mov     eax, [rdx+4]
0x1800072ef  mov     [rsp+14F0h+var_14C8], ecx
0x1800072f3  mov     [rsp+14F0h+var_14C4], eax
0x1800072f7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800072fc  cmp     dword ptr [rdx+8], 1
0x180007300  mov     ebx, eax
0x180007302  lea     eax, [r15+8]
0x180007306  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000730e  mov     ecx, r15d
0x180007311  cmovz   ecx, eax
0x180007314  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007318  lea     ecx, [rax-7]
0x18000731b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007323  inc     ecx
0x180007325  mov     [rsp+14F0h+var_14B8], r15
0x18000732a  mov     [rsp+14F0h+var_14C0], ecx
0x18000732e  call    cs:__imp_GetCurrentThreadId
0x180007334  xorps   xmm0, xmm0
0x180007337  mov     [rsp+14F0h+var_1490], esi
0x18000733b  mov     [rsp+14F0h+var_14B0], eax
0x18000733f  xorps   xmm1, xmm1
0x180007342  lea     rax, aWil; "wil"
0x180007349  mov     [rsp+14F0h+var_148C], ebx
0x18000734d  mov     [rsp+14F0h+var_1498], rax
0x180007352  xor     eax, eax
0x180007354  mov     [rbp+13F0h+var_1458], rax
0x180007358  mov     [rbp+13F0h+var_1470], rax
0x18000735c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007363  mov     [rsp+14F0h+var_14A8], r15
0x180007368  mov     [rsp+14F0h+var_14A0], r15
0x18000736d  mov     [rbp+13F0h+var_1448], rdi
0x180007371  mov     [rbp+13F0h+var_1440], r14
0x180007375  mov     [rsp+14F0h+var_1488], r15
0x18000737a  movups  [rbp+13F0h+var_1468], xmm0
0x18000737e  movups  [rsp+14F0h+var_1480], xmm1
0x180007383  test    rax, rax
0x180007386  jz      short loc_180007393
0x180007388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000738d  mov     [rbp+13F0h+var_1450], rax
0x180007391  jmp     short loc_180007397
0x180007393  mov     [rbp+13F0h+var_1450], r15
0x180007397  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000739e  test    rax, rax
0x1800073a1  jz      short loc_1800073AD
0x1800073a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800073b4  test    rax, rax
0x1800073b7  jz      short loc_1800073CD
0x1800073b9  mov     r8d, 400h
0x1800073bf  lea     rdx, [rbp+13F0h+var_1430]
0x1800073c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073cd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800073d4  test    rax, rax
0x1800073d7  jz      short loc_1800073E3
0x1800073d9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800073ea  test    rax, rax
0x1800073ed  jz      short loc_180007400
0x1800073ef  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800073f4  jnz     short loc_180007400
0x1800073f6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007400  cmp     [rsp+14F0h+var_14C8], r15d
0x180007405  jge     loc_180007507
0x18000740b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180007412  jnz     short loc_180007433
0x180007414  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000741b  test    rax, rax
0x18000741e  jz      short loc_180007429
0x180007420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007425  test    al, al
0x180007427  jmp     short loc_180007431
0x180007429  call    cs:__imp_IsDebuggerPresent
0x18000742f  test    eax, eax
0x180007431  jz      short loc_18000743A
0x180007433  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007438  jz      short loc_180007460
0x18000743a  mov     rax, cs:g_pfnResultLoggingCallback
0x180007441  test    rax, rax
0x180007444  jz      short loc_1800074B9
0x180007446  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000744d  jnz     short loc_1800074B9
0x18000744f  xor     r8d, r8d
0x180007452  lea     rcx, [rsp+14F0h+var_14D0]
0x180007457  xor     edx, edx
0x180007459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000745e  jmp     short loc_1800074B9
0x180007460  mov     rax, cs:g_pfnResultLoggingCallback
0x180007467  mov     ebx, 800h
0x18000746c  test    rax, rax
0x18000746f  jz      short loc_18000748E
0x180007471  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007478  jnz     short loc_18000748E
0x18000747a  mov     r8d, ebx
0x18000747d  lea     rdx, [rbp+13F0h+OutputString]
0x180007484  lea     rcx, [rsp+14F0h+var_14D0]
0x180007489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748e  cmp     [rbp+13F0h+OutputString], r15w
0x180007496  jnz     short loc_1800074AC
0x180007498  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000749d  mov     rdx, rbx; unsigned __int16 *
0x1800074a0  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800074a7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800074ac  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800074b3  call    cs:__imp_OutputDebugStringW
0x1800074b9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800074be  jnz     short loc_1800074C9
0x1800074c0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800074c7  jz      short loc_1800074DA
0x1800074c9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800074d0  test    rax, rax
0x1800074d3  jz      short loc_1800074DA
0x1800074d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074da  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800074df  jnz     short loc_18000750D
0x1800074e1  mov     rcx, [rbp+13F0h+var_30]
0x1800074e8  xor     rcx, rsp; StackCookie
0x1800074eb  call    __security_check_cookie
0x1800074f0  mov     rbx, [rsp+14F0h+arg_10]
0x1800074f8  add     rsp, 14D0h
0x1800074ff  pop     r15
0x180007501  pop     r14
0x180007503  pop     rdi
0x180007504  pop     rsi
0x180007505  pop     rbp
0x180007506  retn
0x180007507  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000750d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007512  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
