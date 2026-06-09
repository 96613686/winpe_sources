# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180032dbc`
- end: `0x180033047`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002c284`

## callees

- `0x180031f04`
- `0x180032dbc`
- `0x180034780`
- `0x180035270`
- `0x1800354a8`
- `0x18004de6a`
- `0x18004deb0`
- `0x18004df40`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032e69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032e69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180032fe7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180032fe7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180032f5d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180032f5d`

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
0x180032dbc  push    rbp
0x180032dbe  push    rbx
0x180032dbf  push    rsi
0x180032dc0  push    rdi
0x180032dc1  push    r12
0x180032dc3  push    r14
0x180032dc5  push    r15
0x180032dc7  lea     rbp, [rsp-13D0h]
0x180032dcf  mov     eax, 14D0h
0x180032dd4  call    _alloca_probe
0x180032dd9  sub     rsp, rax
0x180032ddc  mov     rax, cs:__security_cookie
0x180032de3  xor     rax, rsp
0x180032de6  mov     [rbp+1400h+var_40], rax
0x180032ded  mov     rdi, [rbp+1400h+arg_28]
0x180032df4  mov     r14, r8
0x180032df7  mov     esi, edx
0x180032df9  mov     r15, rcx
0x180032dfc  xor     edx, edx; Val
0x180032dfe  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180032e03  mov     r8d, 98h; Size
0x180032e09  call    memset_0
0x180032e0e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180032e15  xor     r12d, r12d
0x180032e18  mov     [rbp+1400h+OutputString], r12w
0x180032e20  mov     [rbp+1400h+var_1440], r12b
0x180032e24  mov     ecx, [rdx]; this
0x180032e26  mov     eax, [rdx+4]
0x180032e29  mov     [rsp+1500h+var_14D8], ecx
0x180032e2d  mov     [rsp+1500h+var_14D4], eax
0x180032e31  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180032e36  cmp     dword ptr [rdx+8], 1
0x180032e3a  mov     ebx, eax
0x180032e3c  lea     eax, [r12+8]
0x180032e41  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180032e49  mov     ecx, r12d
0x180032e4c  cmovz   ecx, eax
0x180032e4f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180032e53  lea     ecx, [rax-7]
0x180032e56  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180032e5e  inc     ecx
0x180032e60  mov     [rsp+1500h+var_14C8], r12
0x180032e65  mov     [rsp+1500h+var_14D0], ecx
0x180032e69  call    cs:__imp_GetCurrentThreadId
0x180032e6f  xorps   xmm0, xmm0
0x180032e72  mov     [rsp+1500h+var_14A8], r14
0x180032e77  mov     [rsp+1500h+var_14C0], eax
0x180032e7b  xorps   xmm1, xmm1
0x180032e7e  xor     eax, eax
0x180032e80  mov     [rsp+1500h+var_14A0], esi
0x180032e84  mov     [rbp+1400h+var_1468], rax
0x180032e88  mov     [rbp+1400h+var_1480], rax
0x180032e8c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180032e93  mov     [rsp+1500h+var_149C], ebx
0x180032e97  mov     [rsp+1500h+var_14B8], r12
0x180032e9c  mov     [rsp+1500h+var_14B0], r12
0x180032ea1  mov     [rbp+1400h+var_1458], rdi
0x180032ea5  mov     [rbp+1400h+var_1450], r15
0x180032ea9  mov     [rsp+1500h+var_1498], r12
0x180032eae  movups  [rbp+1400h+var_1478], xmm0
0x180032eb2  movups  [rsp+1500h+var_1490], xmm1
0x180032eb7  test    rax, rax
0x180032eba  jz      short loc_180032EC7
0x180032ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ec1  mov     [rbp+1400h+var_1460], rax
0x180032ec5  jmp     short loc_180032ECB
0x180032ec7  mov     [rbp+1400h+var_1460], r12
0x180032ecb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180032ed2  test    rax, rax
0x180032ed5  jz      short loc_180032EE1
0x180032ed7  lea     rcx, [rsp+1500h+var_14E0]
0x180032edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ee1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180032ee8  test    rax, rax
0x180032eeb  jz      short loc_180032F01
0x180032eed  mov     r8d, 400h
0x180032ef3  lea     rdx, [rbp+1400h+var_1440]
0x180032ef7  lea     rcx, [rsp+1500h+var_14E0]
0x180032efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f01  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180032f08  test    rax, rax
0x180032f0b  jz      short loc_180032F17
0x180032f0d  lea     rcx, [rsp+1500h+var_14E0]
0x180032f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f17  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180032f1e  test    rax, rax
0x180032f21  jz      short loc_180032F34
0x180032f23  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180032f28  jnz     short loc_180032F34
0x180032f2a  lea     rcx, [rsp+1500h+var_14E0]
0x180032f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f34  cmp     [rsp+1500h+var_14D8], r12d
0x180032f39  jge     loc_180033036
0x180032f3f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180032f46  jnz     short loc_180032F67
0x180032f48  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180032f4f  test    rax, rax
0x180032f52  jz      short loc_180032F5D
0x180032f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f59  test    al, al
0x180032f5b  jmp     short loc_180032F65
0x180032f5d  call    cs:__imp_IsDebuggerPresent
0x180032f63  test    eax, eax
0x180032f65  jz      short loc_180032F6E
0x180032f67  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180032f6c  jz      short loc_180032F94
0x180032f6e  mov     rax, cs:g_pfnResultLoggingCallback
0x180032f75  test    rax, rax
0x180032f78  jz      short loc_180032FED
0x180032f7a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180032f81  jnz     short loc_180032FED
0x180032f83  xor     r8d, r8d
0x180032f86  lea     rcx, [rsp+1500h+var_14E0]
0x180032f8b  xor     edx, edx
0x180032f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f92  jmp     short loc_180032FED
0x180032f94  mov     rax, cs:g_pfnResultLoggingCallback
0x180032f9b  mov     ebx, 800h
0x180032fa0  test    rax, rax
0x180032fa3  jz      short loc_180032FC2
0x180032fa5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180032fac  jnz     short loc_180032FC2
0x180032fae  mov     r8d, ebx
0x180032fb1  lea     rdx, [rbp+1400h+OutputString]
0x180032fb8  lea     rcx, [rsp+1500h+var_14E0]
0x180032fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fc2  cmp     [rbp+1400h+OutputString], r12w
0x180032fca  jnz     short loc_180032FE0
0x180032fcc  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180032fd1  mov     rdx, rbx; unsigned __int16 *
0x180032fd4  lea     rcx, [rbp+1400h+OutputString]; this
0x180032fdb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180032fe0  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180032fe7  call    cs:__imp_OutputDebugStringW
0x180032fed  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180032ff2  jnz     short loc_180032FFD
0x180032ff4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180032ffb  jz      short loc_18003300E
0x180032ffd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180033004  test    rax, rax
0x180033007  jz      short loc_18003300E
0x180033009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003300e  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180033013  jnz     short loc_18003303C
0x180033015  mov     rcx, [rbp+1400h+var_40]
0x18003301c  xor     rcx, rsp; StackCookie
0x18003301f  call    __security_check_cookie
0x180033024  add     rsp, 14D0h
0x18003302b  pop     r15
0x18003302d  pop     r14
0x18003302f  pop     r12
0x180033031  pop     rdi
0x180033032  pop     rsi
0x180033033  pop     rbx
0x180033034  pop     rbp
0x180033035  retn
0x180033036  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003303c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180033041  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
