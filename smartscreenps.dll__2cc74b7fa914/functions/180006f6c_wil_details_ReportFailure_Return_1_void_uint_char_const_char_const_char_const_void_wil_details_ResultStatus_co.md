# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006f6c`
- end: `0x1800071f9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006c2c`

## callees

- `0x180001590`
- `0x180006f6c`
- `0x180007d64`
- `0x180008db0`
- `0x1800099a8`
- `0x180009a84`
- `0x18000bbd0`
- `0x18000c370`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000701a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000701a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000710e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000710e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007198`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007198`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7)
{
  unsigned int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  unsigned __int64 v17[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v18[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v17, 0, 0x98u);
  OutputString[0] = 0;
  v18[0] = 0;
  v17[1] = *a7;
  v10 = wil::details::RecordReturn((wil::details *)LODWORD(v17[1]), (int)a7);
  LODWORD(v17[0]) = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  HIDWORD(v17[0]) = v11;
  LODWORD(v17[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v17[3] = 0;
  LODWORD(v17[4]) = GetCurrentThreadId();
  v17[7] = a3;
  v17[8] = __PAIR64__(v10, a2);
  v17[5] = 0;
  v17[6] = 0;
  v17[17] = a6;
  v17[18] = a1;
  memset(&v17[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v17[16] = wil::details::g_pfnGetModuleName(v14);
  else
    v17[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v17, v18, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v17);
  if ( wil::details::g_pfnOriginateCallback && (v17[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v17);
  if ( SLODWORD(v17[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v17[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v17, v13);
}

```

## disassembly

```asm
0x180006f6c  push    rbp
0x180006f6e  push    rbx
0x180006f6f  push    rsi
0x180006f70  push    rdi
0x180006f71  push    r12
0x180006f73  push    r14
0x180006f75  push    r15
0x180006f77  lea     rbp, [rsp-13D0h]
0x180006f7f  mov     eax, 14D0h
0x180006f84  call    _alloca_probe
0x180006f89  sub     rsp, rax
0x180006f8c  mov     rax, cs:__security_cookie
0x180006f93  xor     rax, rsp
0x180006f96  mov     [rbp+1400h+var_40], rax
0x180006f9d  mov     r14, r8
0x180006fa0  mov     esi, edx
0x180006fa2  mov     r15, rcx
0x180006fa5  mov     rdi, [rbp+1400h+arg_28]
0x180006fac  xor     edx, edx; Val
0x180006fae  mov     r8d, 98h; Size
0x180006fb4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006fb9  call    memset
0x180006fbe  nop
0x180006fbf  xor     r12d, r12d
0x180006fc2  mov     [rbp+1400h+OutputString], r12w
0x180006fca  mov     [rbp+1400h+var_1440], r12b
0x180006fce  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180006fd5  mov     ecx, [rdx]; this
0x180006fd7  mov     [rsp+1500h+var_14D8], ecx
0x180006fdb  mov     eax, [rdx+4]
0x180006fde  mov     [rsp+1500h+var_14D4], eax
0x180006fe2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006fe7  mov     ebx, eax
0x180006fe9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006ff1  mov     ecx, r12d
0x180006ff4  lea     eax, [r12+8]
0x180006ff9  cmp     dword ptr [rdx+8], 1
0x180006ffd  cmovz   ecx, eax
0x180007000  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007004  lea     ecx, [rax-7]
0x180007007  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000700f  inc     ecx
0x180007011  mov     [rsp+1500h+var_14D0], ecx
0x180007015  mov     [rsp+1500h+var_14C8], r12
0x18000701a  call    cs:__imp_GetCurrentThreadId
0x180007020  mov     [rsp+1500h+var_14C0], eax
0x180007024  mov     [rsp+1500h+var_14A8], r14
0x180007029  mov     [rsp+1500h+var_14A0], esi
0x18000702d  mov     [rsp+1500h+var_149C], ebx
0x180007031  mov     [rsp+1500h+var_14B8], r12
0x180007036  mov     [rsp+1500h+var_14B0], r12
0x18000703b  mov     [rbp+1400h+var_1458], rdi
0x18000703f  mov     [rbp+1400h+var_1450], r15
0x180007043  mov     [rsp+1500h+var_1498], r12
0x180007048  xorps   xmm0, xmm0
0x18000704b  xor     eax, eax
0x18000704d  movups  [rbp+1400h+var_1478], xmm0
0x180007051  mov     [rbp+1400h+var_1468], rax
0x180007055  xorps   xmm1, xmm1
0x180007058  movups  [rsp+1500h+var_1490], xmm1
0x18000705d  mov     [rbp+1400h+var_1480], rax
0x180007061  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007068  test    rax, rax
0x18000706b  jz      short loc_180007078
0x18000706d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007072  mov     [rbp+1400h+var_1460], rax
0x180007076  jmp     short loc_18000707C
0x180007078  mov     [rbp+1400h+var_1460], r12
0x18000707c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007083  test    rax, rax
0x180007086  jz      short loc_180007092
0x180007088  lea     rcx, [rsp+1500h+var_14E0]
0x18000708d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007092  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007099  test    rax, rax
0x18000709c  jz      short loc_1800070B2
0x18000709e  mov     r8d, 400h
0x1800070a4  lea     rdx, [rbp+1400h+var_1440]
0x1800070a8  lea     rcx, [rsp+1500h+var_14E0]
0x1800070ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800070b9  test    rax, rax
0x1800070bc  jz      short loc_1800070C8
0x1800070be  lea     rcx, [rsp+1500h+var_14E0]
0x1800070c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800070cf  test    rax, rax
0x1800070d2  jz      short loc_1800070E5
0x1800070d4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800070d9  jnz     short loc_1800070E5
0x1800070db  lea     rcx, [rsp+1500h+var_14E0]
0x1800070e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070e5  cmp     [rsp+1500h+var_14D8], r12d
0x1800070ea  jge     loc_1800071F3
0x1800070f0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800070f7  jnz     short loc_180007118
0x1800070f9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007100  test    rax, rax
0x180007103  jz      short loc_18000710E
0x180007105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000710a  test    al, al
0x18000710c  jmp     short loc_180007116
0x18000710e  call    cs:__imp_IsDebuggerPresent
0x180007114  test    eax, eax
0x180007116  jz      short loc_18000711F
0x180007118  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000711d  jz      short loc_180007145
0x18000711f  mov     rax, cs:g_pfnResultLoggingCallback
0x180007126  test    rax, rax
0x180007129  jz      short loc_18000719E
0x18000712b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007132  jnz     short loc_18000719E
0x180007134  xor     r8d, r8d
0x180007137  xor     edx, edx
0x180007139  lea     rcx, [rsp+1500h+var_14E0]
0x18000713e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007143  jmp     short loc_18000719E
0x180007145  mov     ebx, 800h
0x18000714a  mov     rax, cs:g_pfnResultLoggingCallback
0x180007151  test    rax, rax
0x180007154  jz      short loc_180007173
0x180007156  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000715d  jnz     short loc_180007173
0x18000715f  mov     r8d, ebx
0x180007162  lea     rdx, [rbp+1400h+OutputString]
0x180007169  lea     rcx, [rsp+1500h+var_14E0]
0x18000716e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007173  cmp     [rbp+1400h+OutputString], r12w
0x18000717b  jnz     short loc_180007191
0x18000717d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007182  mov     rdx, rbx; unsigned __int16 *
0x180007185  lea     rcx, [rbp+1400h+OutputString]; this
0x18000718c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007191  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007198  call    cs:__imp_OutputDebugStringW
0x18000719e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800071a3  jnz     short loc_1800071AE
0x1800071a5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800071ac  jz      short loc_1800071C0
0x1800071ae  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800071b5  test    rax, rax
0x1800071b8  jz      short loc_1800071C0
0x1800071ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071bf  nop
0x1800071c0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800071c5  jnz     short loc_1800071E8
0x1800071c7  mov     rcx, [rbp+1400h+var_40]
0x1800071ce  xor     rcx, rsp; StackCookie
0x1800071d1  call    __security_check_cookie
0x1800071d6  add     rsp, 14D0h
0x1800071dd  pop     r15
0x1800071df  pop     r14
0x1800071e1  pop     r12
0x1800071e3  pop     rdi
0x1800071e4  pop     rsi
0x1800071e5  pop     rbx
0x1800071e6  pop     rbp
0x1800071e7  retn
0x1800071e8  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800071ed  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800071f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
