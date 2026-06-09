# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003894`
- end: `0x180003b3a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002fec`

## callees

- `0x1800020e0`
- `0x180002b38`
- `0x180003894`
- `0x180007e34`
- `0x18000a298`
- `0x18000d030`
- `0x18000d1fc`
- `0x180014400`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000395a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000395a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003ad9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003ad9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a4f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a4f`

## pseudocode

```c
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x180003894  push    rbp
0x180003896  push    rbx
0x180003897  push    rsi
0x180003898  push    rdi
0x180003899  push    r12
0x18000389b  push    r14
0x18000389d  push    r15
0x18000389f  lea     rbp, [rsp-13D0h]
0x1800038a7  mov     eax, 14D0h
0x1800038ac  call    _alloca_probe
0x1800038b1  sub     rsp, rax
0x1800038b4  mov     rax, cs:__security_cookie
0x1800038bb  xor     rax, rsp
0x1800038be  mov     [rbp+1400h+var_40], rax
0x1800038c5  mov     rsi, r8
0x1800038c8  mov     edi, edx
0x1800038ca  mov     rbx, rcx
0x1800038cd  mov     r14, [rbp+1400h+arg_28]
0x1800038d4  xor     edx, edx; Val
0x1800038d6  mov     r8d, 98h; Size
0x1800038dc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800038e1  call    memset_0
0x1800038e6  nop
0x1800038e7  xor     r12d, r12d
0x1800038ea  mov     [rbp+1400h+OutputString], r12w
0x1800038f2  mov     [rbp+1400h+var_1440], r12b
0x1800038f6  mov     rdx, [rbp+1400h+arg_30]; int
0x1800038fd  mov     ecx, [rdx]; this
0x1800038ff  mov     [rsp+1500h+var_14D8], ecx
0x180003903  mov     eax, [rdx+4]
0x180003906  mov     [rsp+1500h+var_14D4], eax
0x18000390a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000390f  mov     r15d, eax
0x180003912  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000391a  mov     ecx, r12d
0x18000391d  lea     eax, [r12+8]
0x180003922  cmp     dword ptr [rdx+8], 1
0x180003926  cmovz   ecx, eax
0x180003929  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000392d  lea     ecx, [rax-7]
0x180003930  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003938  inc     ecx
0x18000393a  mov     [rsp+1500h+var_14D0], ecx
0x18000393e  mov     rcx, [rbp+1400h+arg_38]
0x180003945  test    rcx, rcx
0x180003948  jz      short loc_180003955
0x18000394a  cmp     [rcx], r12w
0x18000394e  mov     [rsp+1500h+var_14C8], rcx
0x180003953  jnz     short loc_18000395A
0x180003955  mov     [rsp+1500h+var_14C8], r12
0x18000395a  call    cs:__imp_GetCurrentThreadId
0x180003960  mov     [rsp+1500h+var_14C0], eax
0x180003964  mov     [rsp+1500h+var_14A8], rsi
0x180003969  mov     [rsp+1500h+var_14A0], edi
0x18000396d  mov     [rsp+1500h+var_149C], r15d
0x180003972  mov     [rsp+1500h+var_14B8], r12
0x180003977  mov     [rsp+1500h+var_14B0], r12
0x18000397c  mov     [rbp+1400h+var_1458], r14
0x180003980  mov     [rbp+1400h+var_1450], rbx
0x180003984  mov     [rsp+1500h+var_1498], r12
0x180003989  xorps   xmm0, xmm0
0x18000398c  xor     eax, eax
0x18000398e  movups  [rbp+1400h+var_1478], xmm0
0x180003992  mov     [rbp+1400h+var_1468], rax
0x180003996  xorps   xmm1, xmm1
0x180003999  movups  [rsp+1500h+var_1490], xmm1
0x18000399e  mov     [rbp+1400h+var_1480], rax
0x1800039a2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800039a9  test    rax, rax
0x1800039ac  jz      short loc_1800039B9
0x1800039ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b3  mov     [rbp+1400h+var_1460], rax
0x1800039b7  jmp     short loc_1800039BD
0x1800039b9  mov     [rbp+1400h+var_1460], r12
0x1800039bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800039c4  test    rax, rax
0x1800039c7  jz      short loc_1800039D3
0x1800039c9  lea     rcx, [rsp+1500h+var_14E0]
0x1800039ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800039da  test    rax, rax
0x1800039dd  jz      short loc_1800039F3
0x1800039df  mov     r8d, 400h
0x1800039e5  lea     rdx, [rbp+1400h+var_1440]
0x1800039e9  lea     rcx, [rsp+1500h+var_14E0]
0x1800039ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039fa  test    rax, rax
0x1800039fd  jz      short loc_180003A09
0x1800039ff  lea     rcx, [rsp+1500h+var_14E0]
0x180003a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a09  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003a10  test    rax, rax
0x180003a13  jz      short loc_180003A26
0x180003a15  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a1a  jnz     short loc_180003A26
0x180003a1c  lea     rcx, [rsp+1500h+var_14E0]
0x180003a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a26  cmp     [rsp+1500h+var_14D8], r12d
0x180003a2b  jge     loc_180003B34
0x180003a31  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003a38  jnz     short loc_180003A59
0x180003a3a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003a41  test    rax, rax
0x180003a44  jz      short loc_180003A4F
0x180003a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4b  test    al, al
0x180003a4d  jmp     short loc_180003A57
0x180003a4f  call    cs:__imp_IsDebuggerPresent
0x180003a55  test    eax, eax
0x180003a57  jz      short loc_180003A60
0x180003a59  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a5e  jz      short loc_180003A86
0x180003a60  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a67  test    rax, rax
0x180003a6a  jz      short loc_180003ADF
0x180003a6c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a73  jnz     short loc_180003ADF
0x180003a75  xor     r8d, r8d
0x180003a78  xor     edx, edx
0x180003a7a  lea     rcx, [rsp+1500h+var_14E0]
0x180003a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a84  jmp     short loc_180003ADF
0x180003a86  mov     ebx, 800h
0x180003a8b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a92  test    rax, rax
0x180003a95  jz      short loc_180003AB4
0x180003a97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a9e  jnz     short loc_180003AB4
0x180003aa0  mov     r8d, ebx
0x180003aa3  lea     rdx, [rbp+1400h+OutputString]
0x180003aaa  lea     rcx, [rsp+1500h+var_14E0]
0x180003aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab4  cmp     [rbp+1400h+OutputString], r12w
0x180003abc  jnz     short loc_180003AD2
0x180003abe  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003ac3  mov     rdx, rbx; wchar_t *
0x180003ac6  lea     rcx, [rbp+1400h+OutputString]; this
0x180003acd  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003ad2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003ad9  call    cs:__imp_OutputDebugStringW
0x180003adf  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003ae4  jnz     short loc_180003AEF
0x180003ae6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003aed  jz      short loc_180003B01
0x180003aef  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003af6  test    rax, rax
0x180003af9  jz      short loc_180003B01
0x180003afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b00  nop
0x180003b01  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003b06  jnz     short loc_180003B29
0x180003b08  mov     rcx, [rbp+1400h+var_40]
0x180003b0f  xor     rcx, rsp; StackCookie
0x180003b12  call    __security_check_cookie
0x180003b17  add     rsp, 14D0h
0x180003b1e  pop     r15
0x180003b20  pop     r14
0x180003b22  pop     r12
0x180003b24  pop     rdi
0x180003b25  pop     rsi
0x180003b26  pop     rbx
0x180003b27  pop     rbp
0x180003b28  retn
0x180003b29  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003b2e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003b34  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
