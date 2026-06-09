# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800420e0`
- end: `0x18004236d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800387bc`

## callees

- `0x18003a580`
- `0x18003af10`
- `0x1800420e0`
- `0x18004364c`
- `0x180044504`
- `0x180044f28`
- `0x180045160`
- `0x18004b3d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004218e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004218e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180042282`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180042282`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004230c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004230c`

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
0x1800420e0  push    rbp
0x1800420e2  push    rbx
0x1800420e3  push    rsi
0x1800420e4  push    rdi
0x1800420e5  push    r12
0x1800420e7  push    r14
0x1800420e9  push    r15
0x1800420eb  lea     rbp, [rsp-13D0h]
0x1800420f3  mov     eax, 14D0h
0x1800420f8  call    _alloca_probe
0x1800420fd  sub     rsp, rax
0x180042100  mov     rax, cs:__security_cookie
0x180042107  xor     rax, rsp
0x18004210a  mov     [rbp+1400h+var_40], rax
0x180042111  mov     r14, r8
0x180042114  mov     esi, edx
0x180042116  mov     r15, rcx
0x180042119  mov     rdi, [rbp+1400h+arg_28]
0x180042120  xor     edx, edx; Val
0x180042122  mov     r8d, 98h; Size
0x180042128  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18004212d  call    memset_0
0x180042132  nop
0x180042133  xor     r12d, r12d
0x180042136  mov     [rbp+1400h+OutputString], r12w
0x18004213e  mov     [rbp+1400h+var_1440], r12b
0x180042142  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180042149  mov     ecx, [rdx]; this
0x18004214b  mov     [rsp+1500h+var_14D8], ecx
0x18004214f  mov     eax, [rdx+4]
0x180042152  mov     [rsp+1500h+var_14D4], eax
0x180042156  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004215b  mov     ebx, eax
0x18004215d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180042165  mov     ecx, r12d
0x180042168  lea     eax, [r12+8]
0x18004216d  cmp     dword ptr [rdx+8], 1
0x180042171  cmovz   ecx, eax
0x180042174  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180042178  lea     ecx, [rax-7]
0x18004217b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180042183  inc     ecx
0x180042185  mov     [rsp+1500h+var_14D0], ecx
0x180042189  mov     [rsp+1500h+var_14C8], r12
0x18004218e  call    cs:__imp_GetCurrentThreadId
0x180042194  mov     [rsp+1500h+var_14C0], eax
0x180042198  mov     [rsp+1500h+var_14A8], r14
0x18004219d  mov     [rsp+1500h+var_14A0], esi
0x1800421a1  mov     [rsp+1500h+var_149C], ebx
0x1800421a5  mov     [rsp+1500h+var_14B8], r12
0x1800421aa  mov     [rsp+1500h+var_14B0], r12
0x1800421af  mov     [rbp+1400h+var_1458], rdi
0x1800421b3  mov     [rbp+1400h+var_1450], r15
0x1800421b7  mov     [rsp+1500h+var_1498], r12
0x1800421bc  xorps   xmm0, xmm0
0x1800421bf  xor     eax, eax
0x1800421c1  movups  [rbp+1400h+var_1478], xmm0
0x1800421c5  mov     [rbp+1400h+var_1468], rax
0x1800421c9  xorps   xmm1, xmm1
0x1800421cc  movups  [rsp+1500h+var_1490], xmm1
0x1800421d1  mov     [rbp+1400h+var_1480], rax
0x1800421d5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800421dc  test    rax, rax
0x1800421df  jz      short loc_1800421EC
0x1800421e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421e6  mov     [rbp+1400h+var_1460], rax
0x1800421ea  jmp     short loc_1800421F0
0x1800421ec  mov     [rbp+1400h+var_1460], r12
0x1800421f0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800421f7  test    rax, rax
0x1800421fa  jz      short loc_180042206
0x1800421fc  lea     rcx, [rsp+1500h+var_14E0]
0x180042201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042206  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004220d  test    rax, rax
0x180042210  jz      short loc_180042226
0x180042212  mov     r8d, 400h
0x180042218  lea     rdx, [rbp+1400h+var_1440]
0x18004221c  lea     rcx, [rsp+1500h+var_14E0]
0x180042221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042226  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004222d  test    rax, rax
0x180042230  jz      short loc_18004223C
0x180042232  lea     rcx, [rsp+1500h+var_14E0]
0x180042237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004223c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180042243  test    rax, rax
0x180042246  jz      short loc_180042259
0x180042248  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18004224d  jnz     short loc_180042259
0x18004224f  lea     rcx, [rsp+1500h+var_14E0]
0x180042254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042259  cmp     [rsp+1500h+var_14D8], r12d
0x18004225e  jge     loc_180042367
0x180042264  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18004226b  jnz     short loc_18004228C
0x18004226d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180042274  test    rax, rax
0x180042277  jz      short loc_180042282
0x180042279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004227e  test    al, al
0x180042280  jmp     short loc_18004228A
0x180042282  call    cs:__imp_IsDebuggerPresent
0x180042288  test    eax, eax
0x18004228a  jz      short loc_180042293
0x18004228c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180042291  jz      short loc_1800422B9
0x180042293  mov     rax, cs:g_pfnResultLoggingCallback
0x18004229a  test    rax, rax
0x18004229d  jz      short loc_180042312
0x18004229f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800422a6  jnz     short loc_180042312
0x1800422a8  xor     r8d, r8d
0x1800422ab  xor     edx, edx
0x1800422ad  lea     rcx, [rsp+1500h+var_14E0]
0x1800422b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422b7  jmp     short loc_180042312
0x1800422b9  mov     ebx, 800h
0x1800422be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800422c5  test    rax, rax
0x1800422c8  jz      short loc_1800422E7
0x1800422ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800422d1  jnz     short loc_1800422E7
0x1800422d3  mov     r8d, ebx
0x1800422d6  lea     rdx, [rbp+1400h+OutputString]
0x1800422dd  lea     rcx, [rsp+1500h+var_14E0]
0x1800422e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422e7  cmp     [rbp+1400h+OutputString], r12w
0x1800422ef  jnz     short loc_180042305
0x1800422f1  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800422f6  mov     rdx, rbx; unsigned __int16 *
0x1800422f9  lea     rcx, [rbp+1400h+OutputString]; this
0x180042300  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180042305  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18004230c  call    cs:__imp_OutputDebugStringW
0x180042312  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180042317  jnz     short loc_180042322
0x180042319  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180042320  jz      short loc_180042334
0x180042322  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180042329  test    rax, rax
0x18004232c  jz      short loc_180042334
0x18004232e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042333  nop
0x180042334  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180042339  jnz     short loc_18004235C
0x18004233b  mov     rcx, [rbp+1400h+var_40]
0x180042342  xor     rcx, rsp; StackCookie
0x180042345  call    __security_check_cookie
0x18004234a  add     rsp, 14D0h
0x180042351  pop     r15
0x180042353  pop     r14
0x180042355  pop     r12
0x180042357  pop     rdi
0x180042358  pop     rsi
0x180042359  pop     rbx
0x18004235a  pop     rbp
0x18004235b  retn
0x18004235c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180042361  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180042367  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
