# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18005e824`
- end: `0x18005eacd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18005926c`

## callees

- `0x18005e824`
- `0x180060294`
- `0x180061d84`
- `0x180063fc0`
- `0x180064648`
- `0x1800829fa`
- `0x180082a40`
- `0x180082b00`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e8cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e8cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005ea60`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005ea60`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005e9d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005e9d0`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18005e824  mov     [rsp-8+arg_10], rbx
0x18005e829  push    rbp
0x18005e82a  push    rsi
0x18005e82b  push    rdi
0x18005e82c  push    r14
0x18005e82e  push    r15
0x18005e830  lea     rbp, [rsp-13D0h]
0x18005e838  mov     eax, 14D0h
0x18005e83d  call    _alloca_probe
0x18005e842  sub     rsp, rax
0x18005e845  mov     rax, cs:__security_cookie
0x18005e84c  xor     rax, rsp
0x18005e84f  mov     [rbp+13F0h+var_30], rax
0x18005e856  mov     esi, edx
0x18005e858  mov     r14, rcx
0x18005e85b  mov     rdi, [rbp+13F0h+arg_28]
0x18005e862  xor     edx, edx; Val
0x18005e864  mov     r8d, 98h; Size
0x18005e86a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18005e86f  call    memset_0
0x18005e874  nop
0x18005e875  xor     r15d, r15d
0x18005e878  mov     [rbp+13F0h+OutputString], r15w
0x18005e880  mov     [rbp+13F0h+var_1430], r15b
0x18005e884  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18005e88b  mov     ecx, [rdx]; this
0x18005e88d  mov     [rsp+14F0h+var_14C8], ecx
0x18005e891  mov     eax, [rdx+4]
0x18005e894  mov     [rsp+14F0h+var_14C4], eax
0x18005e898  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005e89d  mov     ebx, eax
0x18005e89f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18005e8a7  mov     ecx, r15d
0x18005e8aa  lea     eax, [r15+8]
0x18005e8ae  cmp     dword ptr [rdx+8], 1
0x18005e8b2  cmovz   ecx, eax
0x18005e8b5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18005e8b9  lea     ecx, [rax-7]
0x18005e8bc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005e8c4  inc     ecx
0x18005e8c6  mov     [rsp+14F0h+var_14C0], ecx
0x18005e8ca  mov     [rsp+14F0h+var_14B8], r15
0x18005e8cf  call    cs:__imp_GetCurrentThreadId
0x18005e8d6  nop     dword ptr [rax+rax+00h]
0x18005e8db  mov     [rsp+14F0h+var_14B0], eax
0x18005e8df  lea     rax, aWil; "wil"
0x18005e8e6  mov     [rsp+14F0h+var_1498], rax
0x18005e8eb  mov     [rsp+14F0h+var_1490], esi
0x18005e8ef  mov     [rsp+14F0h+var_148C], ebx
0x18005e8f3  mov     [rsp+14F0h+var_14A8], r15
0x18005e8f8  mov     [rsp+14F0h+var_14A0], r15
0x18005e8fd  mov     [rbp+13F0h+var_1448], rdi
0x18005e901  mov     [rbp+13F0h+var_1440], r14
0x18005e905  mov     [rsp+14F0h+var_1488], r15
0x18005e90a  xorps   xmm0, xmm0
0x18005e90d  xor     eax, eax
0x18005e90f  movups  [rbp+13F0h+var_1468], xmm0
0x18005e913  mov     [rbp+13F0h+var_1458], rax
0x18005e917  xorps   xmm1, xmm1
0x18005e91a  movups  [rsp+14F0h+var_1480], xmm1
0x18005e91f  mov     [rbp+13F0h+var_1470], rax
0x18005e923  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005e92a  test    rax, rax
0x18005e92d  jz      short loc_18005E93A
0x18005e92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e934  mov     [rbp+13F0h+var_1450], rax
0x18005e938  jmp     short loc_18005E93E
0x18005e93a  mov     [rbp+13F0h+var_1450], r15
0x18005e93e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005e945  test    rax, rax
0x18005e948  jz      short loc_18005E954
0x18005e94a  lea     rcx, [rsp+14F0h+var_14D0]
0x18005e94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e954  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005e95b  test    rax, rax
0x18005e95e  jz      short loc_18005E974
0x18005e960  mov     r8d, 400h
0x18005e966  lea     rdx, [rbp+13F0h+var_1430]
0x18005e96a  lea     rcx, [rsp+14F0h+var_14D0]
0x18005e96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e974  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005e97b  test    rax, rax
0x18005e97e  jz      short loc_18005E98A
0x18005e980  lea     rcx, [rsp+14F0h+var_14D0]
0x18005e985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e98a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005e991  test    rax, rax
0x18005e994  jz      short loc_18005E9A7
0x18005e996  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18005e99b  jnz     short loc_18005E9A7
0x18005e99d  lea     rcx, [rsp+14F0h+var_14D0]
0x18005e9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9a7  cmp     [rsp+14F0h+var_14C8], r15d
0x18005e9ac  jge     loc_18005EAC7
0x18005e9b2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18005e9b9  jnz     short loc_18005E9E0
0x18005e9bb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005e9c2  test    rax, rax
0x18005e9c5  jz      short loc_18005E9D0
0x18005e9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9cc  test    al, al
0x18005e9ce  jmp     short loc_18005E9DE
0x18005e9d0  call    cs:__imp_IsDebuggerPresent
0x18005e9d7  nop     dword ptr [rax+rax+00h]
0x18005e9dc  test    eax, eax
0x18005e9de  jz      short loc_18005E9E7
0x18005e9e0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18005e9e5  jz      short loc_18005EA0D
0x18005e9e7  mov     rax, cs:g_pfnResultLoggingCallback
0x18005e9ee  test    rax, rax
0x18005e9f1  jz      short loc_18005EA6C
0x18005e9f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005e9fa  jnz     short loc_18005EA6C
0x18005e9fc  xor     r8d, r8d
0x18005e9ff  xor     edx, edx
0x18005ea01  lea     rcx, [rsp+14F0h+var_14D0]
0x18005ea06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea0b  jmp     short loc_18005EA6C
0x18005ea0d  mov     ebx, 800h
0x18005ea12  mov     rax, cs:g_pfnResultLoggingCallback
0x18005ea19  test    rax, rax
0x18005ea1c  jz      short loc_18005EA3B
0x18005ea1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005ea25  jnz     short loc_18005EA3B
0x18005ea27  mov     r8d, ebx
0x18005ea2a  lea     rdx, [rbp+13F0h+OutputString]
0x18005ea31  lea     rcx, [rsp+14F0h+var_14D0]
0x18005ea36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea3b  cmp     [rbp+13F0h+OutputString], r15w
0x18005ea43  jnz     short loc_18005EA59
0x18005ea45  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18005ea4a  mov     rdx, rbx; unsigned __int16 *
0x18005ea4d  lea     rcx, [rbp+13F0h+OutputString]; this
0x18005ea54  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005ea59  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18005ea60  call    cs:__imp_OutputDebugStringW
0x18005ea67  nop     dword ptr [rax+rax+00h]
0x18005ea6c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18005ea71  jnz     short loc_18005EA7C
0x18005ea73  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18005ea7a  jz      short loc_18005EA8E
0x18005ea7c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005ea83  test    rax, rax
0x18005ea86  jz      short loc_18005EA8E
0x18005ea88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea8d  nop
0x18005ea8e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18005ea93  jnz     short loc_18005EABC
0x18005ea95  mov     rcx, [rbp+13F0h+var_30]
0x18005ea9c  xor     rcx, rsp; StackCookie
0x18005ea9f  call    __security_check_cookie
0x18005eaa4  mov     rbx, [rsp+14F0h+arg_10]
0x18005eaac  add     rsp, 14D0h
0x18005eab3  pop     r15
0x18005eab5  pop     r14
0x18005eab7  pop     rdi
0x18005eab8  pop     rsi
0x18005eab9  pop     rbp
0x18005eaba  retn
0x18005eabc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18005eac1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18005eac7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
