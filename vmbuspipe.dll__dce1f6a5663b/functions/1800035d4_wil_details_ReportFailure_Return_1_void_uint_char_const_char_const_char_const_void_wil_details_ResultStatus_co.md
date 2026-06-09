# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800035d4`
- end: `0x18000387a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800018c0`

## callees

- `0x1800024e0`
- `0x1800030ae`
- `0x1800035d4`
- `0x1800045f4`
- `0x180005cf0`
- `0x180006c48`
- `0x180006d24`
- `0x180007930`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000369a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000369a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000378f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000378f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003819`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003819`

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
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800035d4  push    rbp
0x1800035d6  push    rbx
0x1800035d7  push    rsi
0x1800035d8  push    rdi
0x1800035d9  push    r12
0x1800035db  push    r14
0x1800035dd  push    r15
0x1800035df  lea     rbp, [rsp-13D0h]
0x1800035e7  mov     eax, 14D0h
0x1800035ec  call    _alloca_probe
0x1800035f1  sub     rsp, rax
0x1800035f4  mov     rax, cs:__security_cookie
0x1800035fb  xor     rax, rsp
0x1800035fe  mov     [rbp+1400h+var_40], rax
0x180003605  mov     rsi, r8
0x180003608  mov     edi, edx
0x18000360a  mov     rbx, rcx
0x18000360d  mov     r14, [rbp+1400h+arg_28]
0x180003614  xor     edx, edx; Val
0x180003616  mov     r8d, 98h; Size
0x18000361c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003621  call    memset_0
0x180003626  nop
0x180003627  xor     r12d, r12d
0x18000362a  mov     [rbp+1400h+OutputString], r12w
0x180003632  mov     [rbp+1400h+var_1440], r12b
0x180003636  mov     rdx, [rbp+1400h+arg_30]; int
0x18000363d  mov     ecx, [rdx]; this
0x18000363f  mov     [rsp+1500h+var_14D8], ecx
0x180003643  mov     eax, [rdx+4]
0x180003646  mov     [rsp+1500h+var_14D4], eax
0x18000364a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000364f  mov     r15d, eax
0x180003652  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000365a  mov     ecx, r12d
0x18000365d  lea     eax, [r12+8]
0x180003662  cmp     dword ptr [rdx+8], 1
0x180003666  cmovz   ecx, eax
0x180003669  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000366d  lea     ecx, [rax-7]
0x180003670  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003678  inc     ecx
0x18000367a  mov     [rsp+1500h+var_14D0], ecx
0x18000367e  mov     rcx, [rbp+1400h+arg_38]
0x180003685  test    rcx, rcx
0x180003688  jz      short loc_180003695
0x18000368a  cmp     [rcx], r12w
0x18000368e  mov     [rsp+1500h+var_14C8], rcx
0x180003693  jnz     short loc_18000369A
0x180003695  mov     [rsp+1500h+var_14C8], r12
0x18000369a  call    cs:__imp_GetCurrentThreadId
0x1800036a0  mov     [rsp+1500h+var_14C0], eax
0x1800036a4  mov     [rsp+1500h+var_14A8], rsi
0x1800036a9  mov     [rsp+1500h+var_14A0], edi
0x1800036ad  mov     [rsp+1500h+var_149C], r15d
0x1800036b2  mov     [rsp+1500h+var_14B8], r12
0x1800036b7  mov     [rsp+1500h+var_14B0], r12
0x1800036bc  mov     [rbp+1400h+var_1458], r14
0x1800036c0  mov     [rbp+1400h+var_1450], rbx
0x1800036c4  mov     [rsp+1500h+var_1498], r12
0x1800036c9  xorps   xmm0, xmm0
0x1800036cc  xor     eax, eax
0x1800036ce  movups  [rbp+1400h+var_1478], xmm0
0x1800036d2  mov     [rbp+1400h+var_1468], rax
0x1800036d6  xorps   xmm1, xmm1
0x1800036d9  movups  [rsp+1500h+var_1490], xmm1
0x1800036de  mov     [rbp+1400h+var_1480], rax
0x1800036e2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800036e9  test    rax, rax
0x1800036ec  jz      short loc_1800036F9
0x1800036ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f3  mov     [rbp+1400h+var_1460], rax
0x1800036f7  jmp     short loc_1800036FD
0x1800036f9  mov     [rbp+1400h+var_1460], r12
0x1800036fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003704  test    rax, rax
0x180003707  jz      short loc_180003713
0x180003709  lea     rcx, [rsp+1500h+var_14E0]
0x18000370e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003713  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000371a  test    rax, rax
0x18000371d  jz      short loc_180003733
0x18000371f  mov     r8d, 400h
0x180003725  lea     rdx, [rbp+1400h+var_1440]
0x180003729  lea     rcx, [rsp+1500h+var_14E0]
0x18000372e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003733  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000373a  test    rax, rax
0x18000373d  jz      short loc_180003749
0x18000373f  lea     rcx, [rsp+1500h+var_14E0]
0x180003744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003749  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003750  test    rax, rax
0x180003753  jz      short loc_180003766
0x180003755  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000375a  jnz     short loc_180003766
0x18000375c  lea     rcx, [rsp+1500h+var_14E0]
0x180003761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003766  cmp     [rsp+1500h+var_14D8], r12d
0x18000376b  jge     loc_180003874
0x180003771  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003778  jnz     short loc_180003799
0x18000377a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003781  test    rax, rax
0x180003784  jz      short loc_18000378F
0x180003786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378b  test    al, al
0x18000378d  jmp     short loc_180003797
0x18000378f  call    cs:__imp_IsDebuggerPresent
0x180003795  test    eax, eax
0x180003797  jz      short loc_1800037A0
0x180003799  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000379e  jz      short loc_1800037C6
0x1800037a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037a7  test    rax, rax
0x1800037aa  jz      short loc_18000381F
0x1800037ac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800037b3  jnz     short loc_18000381F
0x1800037b5  xor     r8d, r8d
0x1800037b8  xor     edx, edx
0x1800037ba  lea     rcx, [rsp+1500h+var_14E0]
0x1800037bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c4  jmp     short loc_18000381F
0x1800037c6  mov     ebx, 800h
0x1800037cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037d2  test    rax, rax
0x1800037d5  jz      short loc_1800037F4
0x1800037d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800037de  jnz     short loc_1800037F4
0x1800037e0  mov     r8d, ebx
0x1800037e3  lea     rdx, [rbp+1400h+OutputString]
0x1800037ea  lea     rcx, [rsp+1500h+var_14E0]
0x1800037ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f4  cmp     [rbp+1400h+OutputString], r12w
0x1800037fc  jnz     short loc_180003812
0x1800037fe  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003803  mov     rdx, rbx; unsigned __int16 *
0x180003806  lea     rcx, [rbp+1400h+OutputString]; this
0x18000380d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003812  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003819  call    cs:__imp_OutputDebugStringW
0x18000381f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003824  jnz     short loc_18000382F
0x180003826  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000382d  jz      short loc_180003841
0x18000382f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003836  test    rax, rax
0x180003839  jz      short loc_180003841
0x18000383b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003840  nop
0x180003841  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003846  jnz     short loc_180003869
0x180003848  mov     rcx, [rbp+1400h+var_40]
0x18000384f  xor     rcx, rsp; StackCookie
0x180003852  call    __security_check_cookie
0x180003857  add     rsp, 14D0h
0x18000385e  pop     r15
0x180003860  pop     r14
0x180003862  pop     r12
0x180003864  pop     rdi
0x180003865  pop     rsi
0x180003866  pop     rbx
0x180003867  pop     rbp
0x180003868  retn
0x180003869  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000386e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003874  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
