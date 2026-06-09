# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007478`
- end: `0x180007705`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006f4c`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180004fe4`
- `0x180006250`
- `0x180007478`
- `0x18000b7d4`
- `0x18001140c`
- `0x1800344f0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007526`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007526`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800076a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800076a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000761a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000761a`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
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
0x180007478  push    rbp
0x18000747a  push    rbx
0x18000747b  push    rsi
0x18000747c  push    rdi
0x18000747d  push    r12
0x18000747f  push    r14
0x180007481  push    r15
0x180007483  lea     rbp, [rsp-13D0h]
0x18000748b  mov     eax, 14D0h
0x180007490  call    _alloca_probe
0x180007495  sub     rsp, rax
0x180007498  mov     rax, cs:__security_cookie
0x18000749f  xor     rax, rsp
0x1800074a2  mov     [rbp+1400h+var_40], rax
0x1800074a9  mov     r14, r8
0x1800074ac  mov     esi, edx
0x1800074ae  mov     r15, rcx
0x1800074b1  mov     rdi, [rbp+1400h+arg_28]
0x1800074b8  xor     edx, edx; Val
0x1800074ba  mov     r8d, 98h; Size
0x1800074c0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800074c5  call    memset_0
0x1800074ca  nop
0x1800074cb  xor     r12d, r12d
0x1800074ce  mov     [rbp+1400h+OutputString], r12w
0x1800074d6  mov     [rbp+1400h+var_1440], r12b
0x1800074da  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800074e1  mov     ecx, [rdx]; this
0x1800074e3  mov     [rsp+1500h+var_14D8], ecx
0x1800074e7  mov     eax, [rdx+4]
0x1800074ea  mov     [rsp+1500h+var_14D4], eax
0x1800074ee  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800074f3  mov     ebx, eax
0x1800074f5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800074fd  mov     ecx, r12d
0x180007500  lea     eax, [r12+8]
0x180007505  cmp     dword ptr [rdx+8], 1
0x180007509  cmovz   ecx, eax
0x18000750c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007510  lea     ecx, [rax-7]
0x180007513  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000751b  inc     ecx
0x18000751d  mov     [rsp+1500h+var_14D0], ecx
0x180007521  mov     [rsp+1500h+var_14C8], r12
0x180007526  call    cs:__imp_GetCurrentThreadId
0x18000752c  mov     [rsp+1500h+var_14C0], eax
0x180007530  mov     [rsp+1500h+var_14A8], r14
0x180007535  mov     [rsp+1500h+var_14A0], esi
0x180007539  mov     [rsp+1500h+var_149C], ebx
0x18000753d  mov     [rsp+1500h+var_14B8], r12
0x180007542  mov     [rsp+1500h+var_14B0], r12
0x180007547  mov     [rbp+1400h+var_1458], rdi
0x18000754b  mov     [rbp+1400h+var_1450], r15
0x18000754f  mov     [rsp+1500h+var_1498], r12
0x180007554  xorps   xmm0, xmm0
0x180007557  xor     eax, eax
0x180007559  movups  [rbp+1400h+var_1478], xmm0
0x18000755d  mov     [rbp+1400h+var_1468], rax
0x180007561  xorps   xmm1, xmm1
0x180007564  movups  [rsp+1500h+var_1490], xmm1
0x180007569  mov     [rbp+1400h+var_1480], rax
0x18000756d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007574  test    rax, rax
0x180007577  jz      short loc_180007584
0x180007579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000757e  mov     [rbp+1400h+var_1460], rax
0x180007582  jmp     short loc_180007588
0x180007584  mov     [rbp+1400h+var_1460], r12
0x180007588  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000758f  test    rax, rax
0x180007592  jz      short loc_18000759E
0x180007594  lea     rcx, [rsp+1500h+var_14E0]
0x180007599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000759e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800075a5  test    rax, rax
0x1800075a8  jz      short loc_1800075BE
0x1800075aa  mov     r8d, 400h
0x1800075b0  lea     rdx, [rbp+1400h+var_1440]
0x1800075b4  lea     rcx, [rsp+1500h+var_14E0]
0x1800075b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075be  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800075c5  test    rax, rax
0x1800075c8  jz      short loc_1800075D4
0x1800075ca  lea     rcx, [rsp+1500h+var_14E0]
0x1800075cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075d4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800075db  test    rax, rax
0x1800075de  jz      short loc_1800075F1
0x1800075e0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800075e5  jnz     short loc_1800075F1
0x1800075e7  lea     rcx, [rsp+1500h+var_14E0]
0x1800075ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075f1  cmp     [rsp+1500h+var_14D8], r12d
0x1800075f6  jge     loc_1800076FF
0x1800075fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007603  jnz     short loc_180007624
0x180007605  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000760c  test    rax, rax
0x18000760f  jz      short loc_18000761A
0x180007611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007616  test    al, al
0x180007618  jmp     short loc_180007622
0x18000761a  call    cs:__imp_IsDebuggerPresent
0x180007620  test    eax, eax
0x180007622  jz      short loc_18000762B
0x180007624  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007629  jz      short loc_180007651
0x18000762b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007632  test    rax, rax
0x180007635  jz      short loc_1800076AA
0x180007637  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000763e  jnz     short loc_1800076AA
0x180007640  xor     r8d, r8d
0x180007643  xor     edx, edx
0x180007645  lea     rcx, [rsp+1500h+var_14E0]
0x18000764a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000764f  jmp     short loc_1800076AA
0x180007651  mov     ebx, 800h
0x180007656  mov     rax, cs:g_pfnResultLoggingCallback
0x18000765d  test    rax, rax
0x180007660  jz      short loc_18000767F
0x180007662  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007669  jnz     short loc_18000767F
0x18000766b  mov     r8d, ebx
0x18000766e  lea     rdx, [rbp+1400h+OutputString]
0x180007675  lea     rcx, [rsp+1500h+var_14E0]
0x18000767a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767f  cmp     [rbp+1400h+OutputString], r12w
0x180007687  jnz     short loc_18000769D
0x180007689  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000768e  mov     rdx, rbx; wchar_t *
0x180007691  lea     rcx, [rbp+1400h+OutputString]; this
0x180007698  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000769d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800076a4  call    cs:__imp_OutputDebugStringW
0x1800076aa  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800076af  jnz     short loc_1800076BA
0x1800076b1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800076b8  jz      short loc_1800076CC
0x1800076ba  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800076c1  test    rax, rax
0x1800076c4  jz      short loc_1800076CC
0x1800076c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076cb  nop
0x1800076cc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800076d1  jnz     short loc_1800076F4
0x1800076d3  mov     rcx, [rbp+1400h+var_40]
0x1800076da  xor     rcx, rsp; StackCookie
0x1800076dd  call    __security_check_cookie
0x1800076e2  add     rsp, 14D0h
0x1800076e9  pop     r15
0x1800076eb  pop     r14
0x1800076ed  pop     r12
0x1800076ef  pop     rdi
0x1800076f0  pop     rsi
0x1800076f1  pop     rbx
0x1800076f2  pop     rbp
0x1800076f3  retn
0x1800076f4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800076f9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800076ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
