# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000cdd4`
- end: `0x18000d068`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000aaac`

## callees

- `0x18000b550`
- `0x18000c1a4`
- `0x18000cdd4`
- `0x18000e0c4`
- `0x18000f50c`
- `0x1800106a8`
- `0x1800108b4`
- `0x18001c5d0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce7e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d003`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d003`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cf79`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cf79`

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
0x18000cdd4  mov     [rsp-8+arg_10], rbx
0x18000cdd9  push    rbp
0x18000cdda  push    rsi
0x18000cddb  push    rdi
0x18000cddc  push    r14
0x18000cdde  push    r15
0x18000cde0  lea     rbp, [rsp-13D0h]
0x18000cde8  mov     eax, 14D0h
0x18000cded  call    _alloca_probe
0x18000cdf2  sub     rsp, rax
0x18000cdf5  mov     rax, cs:__security_cookie
0x18000cdfc  xor     rax, rsp
0x18000cdff  mov     [rbp+13F0h+var_30], rax
0x18000ce06  mov     rdi, [rbp+13F0h+arg_28]
0x18000ce0d  mov     esi, edx
0x18000ce0f  mov     r14, rcx
0x18000ce12  xor     edx, edx; Val
0x18000ce14  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000ce19  mov     r8d, 98h; Size
0x18000ce1f  call    memset_0
0x18000ce24  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000ce2b  xor     r15d, r15d
0x18000ce2e  mov     [rbp+13F0h+OutputString], r15w
0x18000ce36  mov     [rbp+13F0h+var_1430], r15b
0x18000ce3a  mov     ecx, [rdx]; this
0x18000ce3c  mov     eax, [rdx+4]
0x18000ce3f  mov     [rsp+14F0h+var_14C8], ecx
0x18000ce43  mov     [rsp+14F0h+var_14C4], eax
0x18000ce47  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ce4c  cmp     dword ptr [rdx+8], 1
0x18000ce50  mov     ebx, eax
0x18000ce52  lea     eax, [r15+8]
0x18000ce56  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000ce5e  mov     ecx, r15d
0x18000ce61  cmovz   ecx, eax
0x18000ce64  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000ce68  lea     ecx, [rax-7]
0x18000ce6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ce73  inc     ecx
0x18000ce75  mov     [rsp+14F0h+var_14B8], r15
0x18000ce7a  mov     [rsp+14F0h+var_14C0], ecx
0x18000ce7e  call    cs:__imp_GetCurrentThreadId
0x18000ce84  xorps   xmm0, xmm0
0x18000ce87  mov     [rsp+14F0h+var_1490], esi
0x18000ce8b  mov     [rsp+14F0h+var_14B0], eax
0x18000ce8f  xorps   xmm1, xmm1
0x18000ce92  lea     rax, aWil; "wil"
0x18000ce99  mov     [rsp+14F0h+var_148C], ebx
0x18000ce9d  mov     [rsp+14F0h+var_1498], rax
0x18000cea2  xor     eax, eax
0x18000cea4  mov     [rbp+13F0h+var_1458], rax
0x18000cea8  mov     [rbp+13F0h+var_1470], rax
0x18000ceac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ceb3  mov     [rsp+14F0h+var_14A8], r15
0x18000ceb8  mov     [rsp+14F0h+var_14A0], r15
0x18000cebd  mov     [rbp+13F0h+var_1448], rdi
0x18000cec1  mov     [rbp+13F0h+var_1440], r14
0x18000cec5  mov     [rsp+14F0h+var_1488], r15
0x18000ceca  movups  [rbp+13F0h+var_1468], xmm0
0x18000cece  movups  [rsp+14F0h+var_1480], xmm1
0x18000ced3  test    rax, rax
0x18000ced6  jz      short loc_18000CEE3
0x18000ced8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cedd  mov     [rbp+13F0h+var_1450], rax
0x18000cee1  jmp     short loc_18000CEE7
0x18000cee3  mov     [rbp+13F0h+var_1450], r15
0x18000cee7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ceee  test    rax, rax
0x18000cef1  jz      short loc_18000CEFD
0x18000cef3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cefd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cf04  test    rax, rax
0x18000cf07  jz      short loc_18000CF1D
0x18000cf09  mov     r8d, 400h
0x18000cf0f  lea     rdx, [rbp+13F0h+var_1430]
0x18000cf13  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf1d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cf24  test    rax, rax
0x18000cf27  jz      short loc_18000CF33
0x18000cf29  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cf2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf33  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cf3a  test    rax, rax
0x18000cf3d  jz      short loc_18000CF50
0x18000cf3f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000cf44  jnz     short loc_18000CF50
0x18000cf46  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cf4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf50  cmp     [rsp+14F0h+var_14C8], r15d
0x18000cf55  jge     loc_18000D057
0x18000cf5b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000cf62  jnz     short loc_18000CF83
0x18000cf64  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cf6b  test    rax, rax
0x18000cf6e  jz      short loc_18000CF79
0x18000cf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf75  test    al, al
0x18000cf77  jmp     short loc_18000CF81
0x18000cf79  call    cs:__imp_IsDebuggerPresent
0x18000cf7f  test    eax, eax
0x18000cf81  jz      short loc_18000CF8A
0x18000cf83  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000cf88  jz      short loc_18000CFB0
0x18000cf8a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cf91  test    rax, rax
0x18000cf94  jz      short loc_18000D009
0x18000cf96  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cf9d  jnz     short loc_18000D009
0x18000cf9f  xor     r8d, r8d
0x18000cfa2  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cfa7  xor     edx, edx
0x18000cfa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfae  jmp     short loc_18000D009
0x18000cfb0  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cfb7  mov     ebx, 800h
0x18000cfbc  test    rax, rax
0x18000cfbf  jz      short loc_18000CFDE
0x18000cfc1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cfc8  jnz     short loc_18000CFDE
0x18000cfca  mov     r8d, ebx
0x18000cfcd  lea     rdx, [rbp+13F0h+OutputString]
0x18000cfd4  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfde  cmp     [rbp+13F0h+OutputString], r15w
0x18000cfe6  jnz     short loc_18000CFFC
0x18000cfe8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000cfed  mov     rdx, rbx; unsigned __int16 *
0x18000cff0  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000cff7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000cffc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000d003  call    cs:__imp_OutputDebugStringW
0x18000d009  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000d00e  jnz     short loc_18000D019
0x18000d010  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000d017  jz      short loc_18000D02A
0x18000d019  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d020  test    rax, rax
0x18000d023  jz      short loc_18000D02A
0x18000d025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d02a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000d02f  jnz     short loc_18000D05D
0x18000d031  mov     rcx, [rbp+13F0h+var_30]
0x18000d038  xor     rcx, rsp; StackCookie
0x18000d03b  call    __security_check_cookie
0x18000d040  mov     rbx, [rsp+14F0h+arg_10]
0x18000d048  add     rsp, 14D0h
0x18000d04f  pop     r15
0x18000d051  pop     r14
0x18000d053  pop     rdi
0x18000d054  pop     rsi
0x18000d055  pop     rbp
0x18000d056  retn
0x18000d057  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d05d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d062  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
