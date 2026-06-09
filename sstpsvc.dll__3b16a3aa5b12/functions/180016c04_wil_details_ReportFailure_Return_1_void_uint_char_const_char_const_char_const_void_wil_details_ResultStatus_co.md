# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180016c04`
- end: `0x180016e98`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001670c`

## callees

- `0x180016c04`
- `0x180018224`
- `0x180019b80`
- `0x18001b030`
- `0x18001b1ec`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001bd80`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016cae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016cae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016e33`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016e33`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016da9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016da9`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180016c04  mov     [rsp-8+arg_10], rbx
0x180016c09  push    rbp
0x180016c0a  push    rsi
0x180016c0b  push    rdi
0x180016c0c  push    r14
0x180016c0e  push    r15
0x180016c10  lea     rbp, [rsp-13D0h]
0x180016c18  mov     eax, 14D0h
0x180016c1d  call    _alloca_probe
0x180016c22  sub     rsp, rax
0x180016c25  mov     rax, cs:__security_cookie
0x180016c2c  xor     rax, rsp
0x180016c2f  mov     [rbp+13F0h+var_30], rax
0x180016c36  mov     rdi, [rbp+13F0h+arg_28]
0x180016c3d  mov     esi, edx
0x180016c3f  mov     r14, rcx
0x180016c42  xor     edx, edx; Val
0x180016c44  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180016c49  mov     r8d, 98h; Size
0x180016c4f  call    memset_0
0x180016c54  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180016c5b  xor     r15d, r15d
0x180016c5e  mov     [rbp+13F0h+OutputString], r15w
0x180016c66  mov     [rbp+13F0h+var_1430], r15b
0x180016c6a  mov     ecx, [rdx]; this
0x180016c6c  mov     eax, [rdx+4]
0x180016c6f  mov     [rsp+14F0h+var_14C8], ecx
0x180016c73  mov     [rsp+14F0h+var_14C4], eax
0x180016c77  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180016c7c  cmp     dword ptr [rdx+8], 1
0x180016c80  mov     ebx, eax
0x180016c82  lea     eax, [r15+8]
0x180016c86  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180016c8e  mov     ecx, r15d
0x180016c91  cmovz   ecx, eax
0x180016c94  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180016c98  lea     ecx, [rax-7]
0x180016c9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016ca3  inc     ecx
0x180016ca5  mov     [rsp+14F0h+var_14B8], r15
0x180016caa  mov     [rsp+14F0h+var_14C0], ecx
0x180016cae  call    cs:__imp_GetCurrentThreadId
0x180016cb4  xorps   xmm0, xmm0
0x180016cb7  mov     [rsp+14F0h+var_1490], esi
0x180016cbb  mov     [rsp+14F0h+var_14B0], eax
0x180016cbf  xorps   xmm1, xmm1
0x180016cc2  lea     rax, aWil; "wil"
0x180016cc9  mov     [rsp+14F0h+var_148C], ebx
0x180016ccd  mov     [rsp+14F0h+var_1498], rax
0x180016cd2  xor     eax, eax
0x180016cd4  mov     [rbp+13F0h+var_1458], rax
0x180016cd8  mov     [rbp+13F0h+var_1470], rax
0x180016cdc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180016ce3  mov     [rsp+14F0h+var_14A8], r15
0x180016ce8  mov     [rsp+14F0h+var_14A0], r15
0x180016ced  mov     [rbp+13F0h+var_1448], rdi
0x180016cf1  mov     [rbp+13F0h+var_1440], r14
0x180016cf5  mov     [rsp+14F0h+var_1488], r15
0x180016cfa  movups  [rbp+13F0h+var_1468], xmm0
0x180016cfe  movups  [rsp+14F0h+var_1480], xmm1
0x180016d03  test    rax, rax
0x180016d06  jz      short loc_180016D13
0x180016d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d0d  mov     [rbp+13F0h+var_1450], rax
0x180016d11  jmp     short loc_180016D17
0x180016d13  mov     [rbp+13F0h+var_1450], r15
0x180016d17  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180016d1e  test    rax, rax
0x180016d21  jz      short loc_180016D2D
0x180016d23  lea     rcx, [rsp+14F0h+var_14D0]
0x180016d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d2d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180016d34  test    rax, rax
0x180016d37  jz      short loc_180016D4D
0x180016d39  mov     r8d, 400h
0x180016d3f  lea     rdx, [rbp+13F0h+var_1430]
0x180016d43  lea     rcx, [rsp+14F0h+var_14D0]
0x180016d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d4d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016d54  test    rax, rax
0x180016d57  jz      short loc_180016D63
0x180016d59  lea     rcx, [rsp+14F0h+var_14D0]
0x180016d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d63  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016d6a  test    rax, rax
0x180016d6d  jz      short loc_180016D80
0x180016d6f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180016d74  jnz     short loc_180016D80
0x180016d76  lea     rcx, [rsp+14F0h+var_14D0]
0x180016d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d80  cmp     [rsp+14F0h+var_14C8], r15d
0x180016d85  jge     loc_180016E87
0x180016d8b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180016d92  jnz     short loc_180016DB3
0x180016d94  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180016d9b  test    rax, rax
0x180016d9e  jz      short loc_180016DA9
0x180016da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016da5  test    al, al
0x180016da7  jmp     short loc_180016DB1
0x180016da9  call    cs:__imp_IsDebuggerPresent
0x180016daf  test    eax, eax
0x180016db1  jz      short loc_180016DBA
0x180016db3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180016db8  jz      short loc_180016DE0
0x180016dba  mov     rax, cs:g_pfnResultLoggingCallback
0x180016dc1  test    rax, rax
0x180016dc4  jz      short loc_180016E39
0x180016dc6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180016dcd  jnz     short loc_180016E39
0x180016dcf  xor     r8d, r8d
0x180016dd2  lea     rcx, [rsp+14F0h+var_14D0]
0x180016dd7  xor     edx, edx
0x180016dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dde  jmp     short loc_180016E39
0x180016de0  mov     rax, cs:g_pfnResultLoggingCallback
0x180016de7  mov     ebx, 800h
0x180016dec  test    rax, rax
0x180016def  jz      short loc_180016E0E
0x180016df1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180016df8  jnz     short loc_180016E0E
0x180016dfa  mov     r8d, ebx
0x180016dfd  lea     rdx, [rbp+13F0h+OutputString]
0x180016e04  lea     rcx, [rsp+14F0h+var_14D0]
0x180016e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e0e  cmp     [rbp+13F0h+OutputString], r15w
0x180016e16  jnz     short loc_180016E2C
0x180016e18  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180016e1d  mov     rdx, rbx; unsigned __int16 *
0x180016e20  lea     rcx, [rbp+13F0h+OutputString]; this
0x180016e27  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180016e2c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180016e33  call    cs:__imp_OutputDebugStringW
0x180016e39  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180016e3e  jnz     short loc_180016E49
0x180016e40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180016e47  jz      short loc_180016E5A
0x180016e49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016e50  test    rax, rax
0x180016e53  jz      short loc_180016E5A
0x180016e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e5a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180016e5f  jnz     short loc_180016E8D
0x180016e61  mov     rcx, [rbp+13F0h+var_30]
0x180016e68  xor     rcx, rsp; StackCookie
0x180016e6b  call    __security_check_cookie
0x180016e70  mov     rbx, [rsp+14F0h+arg_10]
0x180016e78  add     rsp, 14D0h
0x180016e7f  pop     r15
0x180016e81  pop     r14
0x180016e83  pop     rdi
0x180016e84  pop     rsi
0x180016e85  pop     rbp
0x180016e86  retn
0x180016e87  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180016e8d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180016e92  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
