# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007f20`
- end: `0x1800081c6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007864`

## callees

- `0x180003110`
- `0x180003c88`
- `0x180007f20`
- `0x18000ba8c`
- `0x18000d5a0`
- `0x18000fc54`
- `0x18000ff18`
- `0x180054660`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fe6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008165`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008165`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800080db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800080db`

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
    wil::details::in1diag3::FailFastImmediate_Unexpected(v15);
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
0x180007f20  push    rbp
0x180007f22  push    rbx
0x180007f23  push    rsi
0x180007f24  push    rdi
0x180007f25  push    r12
0x180007f27  push    r14
0x180007f29  push    r15
0x180007f2b  lea     rbp, [rsp-13D0h]
0x180007f33  mov     eax, 14D0h
0x180007f38  call    _alloca_probe
0x180007f3d  sub     rsp, rax
0x180007f40  mov     rax, cs:__security_cookie
0x180007f47  xor     rax, rsp
0x180007f4a  mov     [rbp+1400h+var_40], rax
0x180007f51  mov     rsi, r8
0x180007f54  mov     edi, edx
0x180007f56  mov     rbx, rcx
0x180007f59  mov     r14, [rbp+1400h+arg_28]
0x180007f60  xor     edx, edx; Val
0x180007f62  mov     r8d, 98h; Size
0x180007f68  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007f6d  call    memset_0
0x180007f72  nop
0x180007f73  xor     r12d, r12d
0x180007f76  mov     [rbp+1400h+OutputString], r12w
0x180007f7e  mov     [rbp+1400h+var_1440], r12b
0x180007f82  mov     rdx, [rbp+1400h+arg_30]; int
0x180007f89  mov     ecx, [rdx]; this
0x180007f8b  mov     [rsp+1500h+var_14D8], ecx
0x180007f8f  mov     eax, [rdx+4]
0x180007f92  mov     [rsp+1500h+var_14D4], eax
0x180007f96  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007f9b  mov     r15d, eax
0x180007f9e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007fa6  mov     ecx, r12d
0x180007fa9  lea     eax, [r12+8]
0x180007fae  cmp     dword ptr [rdx+8], 1
0x180007fb2  cmovz   ecx, eax
0x180007fb5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007fb9  lea     ecx, [rax-7]
0x180007fbc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007fc4  inc     ecx
0x180007fc6  mov     [rsp+1500h+var_14D0], ecx
0x180007fca  mov     rcx, [rbp+1400h+arg_38]
0x180007fd1  test    rcx, rcx
0x180007fd4  jz      short loc_180007FE1
0x180007fd6  cmp     [rcx], r12w
0x180007fda  mov     [rsp+1500h+var_14C8], rcx
0x180007fdf  jnz     short loc_180007FE6
0x180007fe1  mov     [rsp+1500h+var_14C8], r12
0x180007fe6  call    cs:__imp_GetCurrentThreadId
0x180007fec  mov     [rsp+1500h+var_14C0], eax
0x180007ff0  mov     [rsp+1500h+var_14A8], rsi
0x180007ff5  mov     [rsp+1500h+var_14A0], edi
0x180007ff9  mov     [rsp+1500h+var_149C], r15d
0x180007ffe  mov     [rsp+1500h+var_14B8], r12
0x180008003  mov     [rsp+1500h+var_14B0], r12
0x180008008  mov     [rbp+1400h+var_1458], r14
0x18000800c  mov     [rbp+1400h+var_1450], rbx
0x180008010  mov     [rsp+1500h+var_1498], r12
0x180008015  xorps   xmm0, xmm0
0x180008018  xor     eax, eax
0x18000801a  movups  [rbp+1400h+var_1478], xmm0
0x18000801e  mov     [rbp+1400h+var_1468], rax
0x180008022  xorps   xmm1, xmm1
0x180008025  movups  [rsp+1500h+var_1490], xmm1
0x18000802a  mov     [rbp+1400h+var_1480], rax
0x18000802e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008035  test    rax, rax
0x180008038  jz      short loc_180008045
0x18000803a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000803f  mov     [rbp+1400h+var_1460], rax
0x180008043  jmp     short loc_180008049
0x180008045  mov     [rbp+1400h+var_1460], r12
0x180008049  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008050  test    rax, rax
0x180008053  jz      short loc_18000805F
0x180008055  lea     rcx, [rsp+1500h+var_14E0]
0x18000805a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000805f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008066  test    rax, rax
0x180008069  jz      short loc_18000807F
0x18000806b  mov     r8d, 400h
0x180008071  lea     rdx, [rbp+1400h+var_1440]
0x180008075  lea     rcx, [rsp+1500h+var_14E0]
0x18000807a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000807f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008086  test    rax, rax
0x180008089  jz      short loc_180008095
0x18000808b  lea     rcx, [rsp+1500h+var_14E0]
0x180008090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008095  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000809c  test    rax, rax
0x18000809f  jz      short loc_1800080B2
0x1800080a1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800080a6  jnz     short loc_1800080B2
0x1800080a8  lea     rcx, [rsp+1500h+var_14E0]
0x1800080ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b2  cmp     [rsp+1500h+var_14D8], r12d
0x1800080b7  jge     loc_1800081C0
0x1800080bd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800080c4  jnz     short loc_1800080E5
0x1800080c6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800080cd  test    rax, rax
0x1800080d0  jz      short loc_1800080DB
0x1800080d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d7  test    al, al
0x1800080d9  jmp     short loc_1800080E3
0x1800080db  call    cs:__imp_IsDebuggerPresent
0x1800080e1  test    eax, eax
0x1800080e3  jz      short loc_1800080EC
0x1800080e5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800080ea  jz      short loc_180008112
0x1800080ec  mov     rax, cs:g_pfnResultLoggingCallback
0x1800080f3  test    rax, rax
0x1800080f6  jz      short loc_18000816B
0x1800080f8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800080ff  jnz     short loc_18000816B
0x180008101  xor     r8d, r8d
0x180008104  xor     edx, edx
0x180008106  lea     rcx, [rsp+1500h+var_14E0]
0x18000810b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008110  jmp     short loc_18000816B
0x180008112  mov     ebx, 800h
0x180008117  mov     rax, cs:g_pfnResultLoggingCallback
0x18000811e  test    rax, rax
0x180008121  jz      short loc_180008140
0x180008123  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000812a  jnz     short loc_180008140
0x18000812c  mov     r8d, ebx
0x18000812f  lea     rdx, [rbp+1400h+OutputString]
0x180008136  lea     rcx, [rsp+1500h+var_14E0]
0x18000813b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008140  cmp     [rbp+1400h+OutputString], r12w
0x180008148  jnz     short loc_18000815E
0x18000814a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000814f  mov     rdx, rbx; unsigned __int16 *
0x180008152  lea     rcx, [rbp+1400h+OutputString]; this
0x180008159  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000815e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180008165  call    cs:__imp_OutputDebugStringW
0x18000816b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008170  jnz     short loc_18000817B
0x180008172  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008179  jz      short loc_18000818D
0x18000817b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008182  test    rax, rax
0x180008185  jz      short loc_18000818D
0x180008187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000818c  nop
0x18000818d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008192  jnz     short loc_1800081B5
0x180008194  mov     rcx, [rbp+1400h+var_40]
0x18000819b  xor     rcx, rsp; StackCookie
0x18000819e  call    __security_check_cookie
0x1800081a3  add     rsp, 14D0h
0x1800081aa  pop     r15
0x1800081ac  pop     r14
0x1800081ae  pop     r12
0x1800081b0  pop     rdi
0x1800081b1  pop     rsi
0x1800081b2  pop     rbx
0x1800081b3  pop     rbp
0x1800081b4  retn
0x1800081b5  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800081ba  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800081c0  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
