# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180033638`
- end: `0x1800338c5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003311c`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180033638`
- `0x180035884`
- `0x1800370a8`
- `0x180039520`
- `0x1800396ec`
- `0x180096b40`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800336e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800336e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800337da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800337da`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180033864`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180033864`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180033638  push    rbp
0x18003363a  push    rbx
0x18003363b  push    rsi
0x18003363c  push    rdi
0x18003363d  push    r12
0x18003363f  push    r14
0x180033641  push    r15
0x180033643  lea     rbp, [rsp-13D0h]
0x18003364b  mov     eax, 14D0h
0x180033650  call    _alloca_probe
0x180033655  sub     rsp, rax
0x180033658  mov     rax, cs:__security_cookie
0x18003365f  xor     rax, rsp
0x180033662  mov     [rbp+1400h+var_40], rax
0x180033669  mov     r14, r8
0x18003366c  mov     esi, edx
0x18003366e  mov     r15, rcx
0x180033671  mov     rdi, [rbp+1400h+arg_28]
0x180033678  xor     edx, edx; Val
0x18003367a  mov     r8d, 98h; Size
0x180033680  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180033685  call    memset_0
0x18003368a  nop
0x18003368b  xor     r12d, r12d
0x18003368e  mov     [rbp+1400h+OutputString], r12w
0x180033696  mov     [rbp+1400h+var_1440], r12b
0x18003369a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800336a1  mov     ecx, [rdx]; this
0x1800336a3  mov     [rsp+1500h+var_14D8], ecx
0x1800336a7  mov     eax, [rdx+4]
0x1800336aa  mov     [rsp+1500h+var_14D4], eax
0x1800336ae  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800336b3  mov     ebx, eax
0x1800336b5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800336bd  mov     ecx, r12d
0x1800336c0  lea     eax, [r12+8]
0x1800336c5  cmp     dword ptr [rdx+8], 1
0x1800336c9  cmovz   ecx, eax
0x1800336cc  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800336d0  lea     ecx, [rax-7]
0x1800336d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800336db  inc     ecx
0x1800336dd  mov     [rsp+1500h+var_14D0], ecx
0x1800336e1  mov     [rsp+1500h+var_14C8], r12
0x1800336e6  call    cs:__imp_GetCurrentThreadId
0x1800336ec  mov     [rsp+1500h+var_14C0], eax
0x1800336f0  mov     [rsp+1500h+var_14A8], r14
0x1800336f5  mov     [rsp+1500h+var_14A0], esi
0x1800336f9  mov     [rsp+1500h+var_149C], ebx
0x1800336fd  mov     [rsp+1500h+var_14B8], r12
0x180033702  mov     [rsp+1500h+var_14B0], r12
0x180033707  mov     [rbp+1400h+var_1458], rdi
0x18003370b  mov     [rbp+1400h+var_1450], r15
0x18003370f  mov     [rsp+1500h+var_1498], r12
0x180033714  xorps   xmm0, xmm0
0x180033717  xor     eax, eax
0x180033719  movups  [rbp+1400h+var_1478], xmm0
0x18003371d  mov     [rbp+1400h+var_1468], rax
0x180033721  xorps   xmm1, xmm1
0x180033724  movups  [rsp+1500h+var_1490], xmm1
0x180033729  mov     [rbp+1400h+var_1480], rax
0x18003372d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180033734  test    rax, rax
0x180033737  jz      short loc_180033744
0x180033739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003373e  mov     [rbp+1400h+var_1460], rax
0x180033742  jmp     short loc_180033748
0x180033744  mov     [rbp+1400h+var_1460], r12
0x180033748  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003374f  test    rax, rax
0x180033752  jz      short loc_18003375E
0x180033754  lea     rcx, [rsp+1500h+var_14E0]
0x180033759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003375e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180033765  test    rax, rax
0x180033768  jz      short loc_18003377E
0x18003376a  mov     r8d, 400h
0x180033770  lea     rdx, [rbp+1400h+var_1440]
0x180033774  lea     rcx, [rsp+1500h+var_14E0]
0x180033779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003377e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180033785  test    rax, rax
0x180033788  jz      short loc_180033794
0x18003378a  lea     rcx, [rsp+1500h+var_14E0]
0x18003378f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033794  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003379b  test    rax, rax
0x18003379e  jz      short loc_1800337B1
0x1800337a0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800337a5  jnz     short loc_1800337B1
0x1800337a7  lea     rcx, [rsp+1500h+var_14E0]
0x1800337ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337b1  cmp     [rsp+1500h+var_14D8], r12d
0x1800337b6  jge     loc_1800338BF
0x1800337bc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800337c3  jnz     short loc_1800337E4
0x1800337c5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800337cc  test    rax, rax
0x1800337cf  jz      short loc_1800337DA
0x1800337d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337d6  test    al, al
0x1800337d8  jmp     short loc_1800337E2
0x1800337da  call    cs:__imp_IsDebuggerPresent
0x1800337e0  test    eax, eax
0x1800337e2  jz      short loc_1800337EB
0x1800337e4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800337e9  jz      short loc_180033811
0x1800337eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800337f2  test    rax, rax
0x1800337f5  jz      short loc_18003386A
0x1800337f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800337fe  jnz     short loc_18003386A
0x180033800  xor     r8d, r8d
0x180033803  xor     edx, edx
0x180033805  lea     rcx, [rsp+1500h+var_14E0]
0x18003380a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003380f  jmp     short loc_18003386A
0x180033811  mov     ebx, 800h
0x180033816  mov     rax, cs:g_pfnResultLoggingCallback
0x18003381d  test    rax, rax
0x180033820  jz      short loc_18003383F
0x180033822  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180033829  jnz     short loc_18003383F
0x18003382b  mov     r8d, ebx
0x18003382e  lea     rdx, [rbp+1400h+OutputString]
0x180033835  lea     rcx, [rsp+1500h+var_14E0]
0x18003383a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003383f  cmp     [rbp+1400h+OutputString], r12w
0x180033847  jnz     short loc_18003385D
0x180033849  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18003384e  mov     rdx, rbx; unsigned __int16 *
0x180033851  lea     rcx, [rbp+1400h+OutputString]; this
0x180033858  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003385d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180033864  call    cs:__imp_OutputDebugStringW
0x18003386a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18003386f  jnz     short loc_18003387A
0x180033871  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180033878  jz      short loc_18003388C
0x18003387a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180033881  test    rax, rax
0x180033884  jz      short loc_18003388C
0x180033886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003388b  nop
0x18003388c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180033891  jnz     short loc_1800338B4
0x180033893  mov     rcx, [rbp+1400h+var_40]
0x18003389a  xor     rcx, rsp; StackCookie
0x18003389d  call    __security_check_cookie
0x1800338a2  add     rsp, 14D0h
0x1800338a9  pop     r15
0x1800338ab  pop     r14
0x1800338ad  pop     r12
0x1800338af  pop     rdi
0x1800338b0  pop     rsi
0x1800338b1  pop     rbx
0x1800338b2  pop     rbp
0x1800338b3  retn
0x1800338b4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800338b9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800338bf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
