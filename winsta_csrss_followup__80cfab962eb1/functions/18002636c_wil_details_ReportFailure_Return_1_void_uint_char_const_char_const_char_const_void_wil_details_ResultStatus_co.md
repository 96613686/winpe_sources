# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18002636c`
- end: `0x18002660a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180026108`

## callees

- `0x18002636c`
- `0x180027d34`
- `0x180028994`
- `0x180029250`
- `0x18002932c`
- `0x180032be6`
- `0x180032c20`
- `0x180032ce0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026419`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800265a3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800265a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026513`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026513`

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
0x18002636c  push    rbp
0x18002636e  push    rbx
0x18002636f  push    rsi
0x180026370  push    rdi
0x180026371  push    r12
0x180026373  push    r14
0x180026375  push    r15
0x180026377  lea     rbp, [rsp-13D0h]
0x18002637f  mov     eax, 14D0h
0x180026384  call    _alloca_probe
0x180026389  sub     rsp, rax
0x18002638c  mov     rax, cs:__security_cookie
0x180026393  xor     rax, rsp
0x180026396  mov     [rbp+1400h+var_40], rax
0x18002639d  mov     rdi, [rbp+1400h+arg_28]
0x1800263a4  mov     r14, r8
0x1800263a7  mov     esi, edx
0x1800263a9  mov     r15, rcx
0x1800263ac  xor     edx, edx; Val
0x1800263ae  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800263b3  mov     r8d, 98h; Size
0x1800263b9  call    memset_0
0x1800263be  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800263c5  xor     r12d, r12d
0x1800263c8  mov     [rbp+1400h+OutputString], r12w
0x1800263d0  mov     [rbp+1400h+var_1440], r12b
0x1800263d4  mov     ecx, [rdx]; this
0x1800263d6  mov     eax, [rdx+4]
0x1800263d9  mov     [rsp+1500h+var_14D8], ecx
0x1800263dd  mov     [rsp+1500h+var_14D4], eax
0x1800263e1  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800263e6  cmp     dword ptr [rdx+8], 1
0x1800263ea  mov     ebx, eax
0x1800263ec  lea     eax, [r12+8]
0x1800263f1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800263f9  mov     ecx, r12d
0x1800263fc  cmovz   ecx, eax
0x1800263ff  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180026403  lea     ecx, [rax-7]
0x180026406  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002640e  inc     ecx
0x180026410  mov     [rsp+1500h+var_14C8], r12
0x180026415  mov     [rsp+1500h+var_14D0], ecx
0x180026419  call    cs:__imp_GetCurrentThreadId
0x180026420  nop     dword ptr [rax+rax+00h]
0x180026425  xorps   xmm0, xmm0
0x180026428  mov     [rsp+1500h+var_14A8], r14
0x18002642d  mov     [rsp+1500h+var_14C0], eax
0x180026431  xorps   xmm1, xmm1
0x180026434  xor     eax, eax
0x180026436  mov     [rsp+1500h+var_14A0], esi
0x18002643a  mov     [rbp+1400h+var_1468], rax
0x18002643e  mov     [rbp+1400h+var_1480], rax
0x180026442  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180026449  mov     [rsp+1500h+var_149C], ebx
0x18002644d  mov     [rsp+1500h+var_14B8], r12
0x180026452  mov     [rsp+1500h+var_14B0], r12
0x180026457  mov     [rbp+1400h+var_1458], rdi
0x18002645b  mov     [rbp+1400h+var_1450], r15
0x18002645f  mov     [rsp+1500h+var_1498], r12
0x180026464  movups  [rbp+1400h+var_1478], xmm0
0x180026468  movups  [rsp+1500h+var_1490], xmm1
0x18002646d  test    rax, rax
0x180026470  jz      short loc_18002647D
0x180026472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026477  mov     [rbp+1400h+var_1460], rax
0x18002647b  jmp     short loc_180026481
0x18002647d  mov     [rbp+1400h+var_1460], r12
0x180026481  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180026488  test    rax, rax
0x18002648b  jz      short loc_180026497
0x18002648d  lea     rcx, [rsp+1500h+var_14E0]
0x180026492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026497  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002649e  test    rax, rax
0x1800264a1  jz      short loc_1800264B7
0x1800264a3  mov     r8d, 400h
0x1800264a9  lea     rdx, [rbp+1400h+var_1440]
0x1800264ad  lea     rcx, [rsp+1500h+var_14E0]
0x1800264b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800264be  test    rax, rax
0x1800264c1  jz      short loc_1800264CD
0x1800264c3  lea     rcx, [rsp+1500h+var_14E0]
0x1800264c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264cd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800264d4  test    rax, rax
0x1800264d7  jz      short loc_1800264EA
0x1800264d9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800264de  jnz     short loc_1800264EA
0x1800264e0  lea     rcx, [rsp+1500h+var_14E0]
0x1800264e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ea  cmp     [rsp+1500h+var_14D8], r12d
0x1800264ef  jge     loc_1800265F9
0x1800264f5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800264fc  jnz     short loc_180026523
0x1800264fe  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180026505  test    rax, rax
0x180026508  jz      short loc_180026513
0x18002650a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002650f  test    al, al
0x180026511  jmp     short loc_180026521
0x180026513  call    cs:__imp_IsDebuggerPresent
0x18002651a  nop     dword ptr [rax+rax+00h]
0x18002651f  test    eax, eax
0x180026521  jz      short loc_18002652A
0x180026523  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180026528  jz      short loc_180026550
0x18002652a  mov     rax, cs:g_pfnResultLoggingCallback
0x180026531  test    rax, rax
0x180026534  jz      short loc_1800265AF
0x180026536  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18002653d  jnz     short loc_1800265AF
0x18002653f  xor     r8d, r8d
0x180026542  lea     rcx, [rsp+1500h+var_14E0]
0x180026547  xor     edx, edx
0x180026549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002654e  jmp     short loc_1800265AF
0x180026550  mov     rax, cs:g_pfnResultLoggingCallback
0x180026557  mov     ebx, 800h
0x18002655c  test    rax, rax
0x18002655f  jz      short loc_18002657E
0x180026561  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180026568  jnz     short loc_18002657E
0x18002656a  mov     r8d, ebx
0x18002656d  lea     rdx, [rbp+1400h+OutputString]
0x180026574  lea     rcx, [rsp+1500h+var_14E0]
0x180026579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002657e  cmp     [rbp+1400h+OutputString], r12w
0x180026586  jnz     short loc_18002659C
0x180026588  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18002658d  mov     rdx, rbx; unsigned __int16 *
0x180026590  lea     rcx, [rbp+1400h+OutputString]; this
0x180026597  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002659c  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800265a3  call    cs:__imp_OutputDebugStringW
0x1800265aa  nop     dword ptr [rax+rax+00h]
0x1800265af  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800265b4  jnz     short loc_1800265BF
0x1800265b6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800265bd  jz      short loc_1800265D0
0x1800265bf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800265c6  test    rax, rax
0x1800265c9  jz      short loc_1800265D0
0x1800265cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265d0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800265d5  jnz     short loc_1800265FF
0x1800265d7  mov     rcx, [rbp+1400h+var_40]
0x1800265de  xor     rcx, rsp; StackCookie
0x1800265e1  call    __security_check_cookie
0x1800265e6  add     rsp, 14D0h
0x1800265ed  pop     r15
0x1800265ef  pop     r14
0x1800265f1  pop     r12
0x1800265f3  pop     rdi
0x1800265f4  pop     rsi
0x1800265f5  pop     rbx
0x1800265f6  pop     rbp
0x1800265f7  retn
0x1800265f9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800265ff  lea     rcx, [rsp+1500h+var_14E0]; this
0x180026604  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
