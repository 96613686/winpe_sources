# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000bf50`
- end: `0x18000c1ff`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `687`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000bbe8`

## callees

- `0x1800091d4`
- `0x18000965c`
- `0x18000a8ec`
- `0x18000ab40`
- `0x18000bf50`
- `0x18002fda9`
- `0x18002ffd0`
- `0x1800369a0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c016`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c19e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c19e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c10c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c10c`

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
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
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
  if ( !a8 || (v14 = *a8 == 0, v23 = a8, v14) )
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
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v19 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v15);
}

```

## disassembly

```asm
0x18000bf50  push    rbp
0x18000bf52  push    rbx
0x18000bf53  push    rsi
0x18000bf54  push    rdi
0x18000bf55  push    r12
0x18000bf57  push    r14
0x18000bf59  push    r15
0x18000bf5b  lea     rbp, [rsp-13D0h]
0x18000bf63  mov     eax, 14D0h
0x18000bf68  call    _alloca_probe
0x18000bf6d  sub     rsp, rax
0x18000bf70  mov     rax, cs:__security_cookie
0x18000bf77  xor     rax, rsp
0x18000bf7a  mov     [rbp+1400h+var_40], rax
0x18000bf81  mov     rsi, r8
0x18000bf84  mov     edi, edx
0x18000bf86  mov     rbx, rcx
0x18000bf89  mov     r14, [rbp+1400h+arg_28]
0x18000bf90  xor     edx, edx; Val
0x18000bf92  mov     r8d, 98h; Size
0x18000bf98  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000bf9d  call    memset_0
0x18000bfa2  nop
0x18000bfa3  xor     r12d, r12d
0x18000bfa6  mov     [rbp+1400h+OutputString], r12w
0x18000bfae  mov     [rbp+1400h+var_1440], r12b
0x18000bfb2  mov     rdx, [rbp+1400h+arg_30]; int
0x18000bfb9  mov     ecx, [rdx]; this
0x18000bfbb  mov     [rsp+1500h+var_14D8], ecx
0x18000bfbf  mov     eax, [rdx+4]
0x18000bfc2  mov     [rsp+1500h+var_14D4], eax
0x18000bfc6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bfcb  mov     r15d, eax
0x18000bfce  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000bfd6  mov     ecx, r12d
0x18000bfd9  lea     eax, [r12+8]
0x18000bfde  cmp     dword ptr [rdx+8], 1
0x18000bfe2  cmovz   ecx, eax
0x18000bfe5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000bfe9  lea     ecx, [rax-7]
0x18000bfec  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bff4  inc     ecx
0x18000bff6  mov     [rsp+1500h+var_14D0], ecx
0x18000bffa  mov     rcx, [rbp+1400h+arg_38]
0x18000c001  test    rcx, rcx
0x18000c004  jz      short loc_18000C011
0x18000c006  cmp     [rcx], r12w
0x18000c00a  mov     [rsp+1500h+var_14C8], rcx
0x18000c00f  jnz     short loc_18000C016
0x18000c011  mov     [rsp+1500h+var_14C8], r12
0x18000c016  call    cs:__imp_GetCurrentThreadId
0x18000c01c  mov     [rsp+1500h+var_14C0], eax
0x18000c020  mov     [rsp+1500h+var_14A8], rsi
0x18000c025  mov     [rsp+1500h+var_14A0], edi
0x18000c029  mov     [rsp+1500h+var_149C], r15d
0x18000c02e  mov     [rsp+1500h+var_14B8], r12
0x18000c033  mov     [rsp+1500h+var_14B0], r12
0x18000c038  mov     [rbp+1400h+var_1458], r14
0x18000c03c  mov     [rbp+1400h+var_1450], rbx
0x18000c040  mov     [rsp+1500h+var_1498], r12
0x18000c045  xorps   xmm0, xmm0
0x18000c048  xor     eax, eax
0x18000c04a  movups  [rbp+1400h+var_1478], xmm0
0x18000c04e  mov     [rbp+1400h+var_1468], rax
0x18000c052  xorps   xmm1, xmm1
0x18000c055  movups  [rsp+1500h+var_1490], xmm1
0x18000c05a  mov     [rbp+1400h+var_1480], rax
0x18000c05e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c065  test    rax, rax
0x18000c068  jz      short loc_18000C075
0x18000c06a  call    _guard_dispatch_icall
0x18000c06f  mov     [rbp+1400h+var_1460], rax
0x18000c073  jmp     short loc_18000C079
0x18000c075  mov     [rbp+1400h+var_1460], r12
0x18000c079  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c080  test    rax, rax
0x18000c083  jz      short loc_18000C08F
0x18000c085  lea     rcx, [rsp+1500h+var_14E0]
0x18000c08a  call    _guard_dispatch_icall
0x18000c08f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c096  test    rax, rax
0x18000c099  jz      short loc_18000C0AF
0x18000c09b  mov     r8d, 400h
0x18000c0a1  lea     rdx, [rbp+1400h+var_1440]
0x18000c0a5  lea     rcx, [rsp+1500h+var_14E0]
0x18000c0aa  call    _guard_dispatch_icall
0x18000c0af  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c0b6  test    rax, rax
0x18000c0b9  jz      short loc_18000C0C5
0x18000c0bb  lea     rcx, [rsp+1500h+var_14E0]
0x18000c0c0  call    _guard_dispatch_icall
0x18000c0c5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c0cc  test    rax, rax
0x18000c0cf  jz      short loc_18000C0E2
0x18000c0d1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000c0d6  jnz     short loc_18000C0E2
0x18000c0d8  lea     rcx, [rsp+1500h+var_14E0]
0x18000c0dd  call    _guard_dispatch_icall
0x18000c0e2  cmp     [rsp+1500h+var_14D8], r12d
0x18000c0e7  jge     loc_18000C1F9
0x18000c0ed  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000c0f4  jnz     short loc_18000C11E
0x18000c0f6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c0fd  test    rax, rax
0x18000c100  jz      short loc_18000C10C
0x18000c102  call    _guard_dispatch_icall
0x18000c107  movzx   ecx, al
0x18000c10a  jmp     short loc_18000C11A
0x18000c10c  call    cs:__imp_IsDebuggerPresent
0x18000c112  mov     ecx, r12d
0x18000c115  test    eax, eax
0x18000c117  setnz   cl
0x18000c11a  test    ecx, ecx
0x18000c11c  jz      short loc_18000C125
0x18000c11e  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000c123  jz      short loc_18000C14B
0x18000c125  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c12c  test    rax, rax
0x18000c12f  jz      short loc_18000C1A4
0x18000c131  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000c138  jnz     short loc_18000C1A4
0x18000c13a  xor     r8d, r8d
0x18000c13d  xor     edx, edx
0x18000c13f  lea     rcx, [rsp+1500h+var_14E0]
0x18000c144  call    _guard_dispatch_icall
0x18000c149  jmp     short loc_18000C1A4
0x18000c14b  mov     ebx, 800h
0x18000c150  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c157  test    rax, rax
0x18000c15a  jz      short loc_18000C179
0x18000c15c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000c163  jnz     short loc_18000C179
0x18000c165  mov     r8d, ebx
0x18000c168  lea     rdx, [rbp+1400h+OutputString]
0x18000c16f  lea     rcx, [rsp+1500h+var_14E0]
0x18000c174  call    _guard_dispatch_icall
0x18000c179  cmp     [rbp+1400h+OutputString], r12w
0x18000c181  jnz     short loc_18000C197
0x18000c183  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000c188  mov     rdx, rbx; wchar_t *
0x18000c18b  lea     rcx, [rbp+1400h+OutputString]; this
0x18000c192  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000c197  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000c19e  call    cs:__imp_OutputDebugStringW
0x18000c1a4  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000c1a9  jnz     short loc_18000C1B4
0x18000c1ab  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000c1b2  jz      short loc_18000C1C6
0x18000c1b4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c1bb  test    rax, rax
0x18000c1be  jz      short loc_18000C1C6
0x18000c1c0  call    _guard_dispatch_icall
0x18000c1c5  nop
0x18000c1c6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000c1cb  jnz     short loc_18000C1EE
0x18000c1cd  mov     rcx, [rbp+1400h+var_40]
0x18000c1d4  xor     rcx, rsp; StackCookie
0x18000c1d7  call    __security_check_cookie
0x18000c1dc  add     rsp, 14D0h
0x18000c1e3  pop     r15
0x18000c1e5  pop     r14
0x18000c1e7  pop     r12
0x18000c1e9  pop     rdi
0x18000c1ea  pop     rsi
0x18000c1eb  pop     rbx
0x18000c1ec  pop     rbp
0x18000c1ed  retn
0x18000c1ee  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000c1f3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c1f9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
