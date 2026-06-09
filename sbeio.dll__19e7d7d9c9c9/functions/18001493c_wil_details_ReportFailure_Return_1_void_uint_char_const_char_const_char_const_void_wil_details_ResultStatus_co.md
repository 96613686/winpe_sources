# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001493c`
- end: `0x180014bd0`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001444c`

## callees

- `0x1800015f0`
- `0x180001f1c`
- `0x18001493c`
- `0x18001c244`
- `0x18001fac0`
- `0x180026ea0`
- `0x180026f7c`
- `0x18002a010`
- `0x18002b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180014b6b`
- `KERNEL32!OutputDebugStringW` at `0x180014b6b`
- `KERNEL32!IsDebuggerPresent` at `0x180014ae1`
- `KERNEL32!IsDebuggerPresent` at `0x180014ae1`
- `KERNEL32!GetCurrentThreadId` at `0x1800149e6`
- `KERNEL32!GetCurrentThreadId` at `0x1800149e6`

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
0x18001493c  mov     [rsp-8+arg_10], rbx
0x180014941  push    rbp
0x180014942  push    rsi
0x180014943  push    rdi
0x180014944  push    r14
0x180014946  push    r15
0x180014948  lea     rbp, [rsp-13D0h]
0x180014950  mov     eax, 14D0h
0x180014955  call    _alloca_probe
0x18001495a  sub     rsp, rax
0x18001495d  mov     rax, cs:__security_cookie
0x180014964  xor     rax, rsp
0x180014967  mov     [rbp+13F0h+var_30], rax
0x18001496e  mov     rdi, [rbp+13F0h+arg_28]
0x180014975  mov     esi, edx
0x180014977  mov     r14, rcx
0x18001497a  xor     edx, edx; Val
0x18001497c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180014981  mov     r8d, 98h; Size
0x180014987  call    memset_0
0x18001498c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180014993  xor     r15d, r15d
0x180014996  mov     [rbp+13F0h+OutputString], r15w
0x18001499e  mov     [rbp+13F0h+var_1430], r15b
0x1800149a2  mov     ecx, [rdx]; this
0x1800149a4  mov     eax, [rdx+4]
0x1800149a7  mov     [rsp+14F0h+var_14C8], ecx
0x1800149ab  mov     [rsp+14F0h+var_14C4], eax
0x1800149af  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800149b4  cmp     dword ptr [rdx+8], 1
0x1800149b8  mov     ebx, eax
0x1800149ba  lea     eax, [r15+8]
0x1800149be  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800149c6  mov     ecx, r15d
0x1800149c9  cmovz   ecx, eax
0x1800149cc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800149d0  lea     ecx, [rax-7]
0x1800149d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800149db  inc     ecx
0x1800149dd  mov     [rsp+14F0h+var_14B8], r15
0x1800149e2  mov     [rsp+14F0h+var_14C0], ecx
0x1800149e6  call    cs:__imp_GetCurrentThreadId
0x1800149ec  xorps   xmm0, xmm0
0x1800149ef  mov     [rsp+14F0h+var_1490], esi
0x1800149f3  mov     [rsp+14F0h+var_14B0], eax
0x1800149f7  xorps   xmm1, xmm1
0x1800149fa  lea     rax, aWil; "wil"
0x180014a01  mov     [rsp+14F0h+var_148C], ebx
0x180014a05  mov     [rsp+14F0h+var_1498], rax
0x180014a0a  xor     eax, eax
0x180014a0c  mov     [rbp+13F0h+var_1458], rax
0x180014a10  mov     [rbp+13F0h+var_1470], rax
0x180014a14  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180014a1b  mov     [rsp+14F0h+var_14A8], r15
0x180014a20  mov     [rsp+14F0h+var_14A0], r15
0x180014a25  mov     [rbp+13F0h+var_1448], rdi
0x180014a29  mov     [rbp+13F0h+var_1440], r14
0x180014a2d  mov     [rsp+14F0h+var_1488], r15
0x180014a32  movups  [rbp+13F0h+var_1468], xmm0
0x180014a36  movups  [rsp+14F0h+var_1480], xmm1
0x180014a3b  test    rax, rax
0x180014a3e  jz      short loc_180014A4B
0x180014a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a45  mov     [rbp+13F0h+var_1450], rax
0x180014a49  jmp     short loc_180014A4F
0x180014a4b  mov     [rbp+13F0h+var_1450], r15
0x180014a4f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180014a56  test    rax, rax
0x180014a59  jz      short loc_180014A65
0x180014a5b  lea     rcx, [rsp+14F0h+var_14D0]
0x180014a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a65  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180014a6c  test    rax, rax
0x180014a6f  jz      short loc_180014A85
0x180014a71  mov     r8d, 400h
0x180014a77  lea     rdx, [rbp+13F0h+var_1430]
0x180014a7b  lea     rcx, [rsp+14F0h+var_14D0]
0x180014a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a85  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014a8c  test    rax, rax
0x180014a8f  jz      short loc_180014A9B
0x180014a91  lea     rcx, [rsp+14F0h+var_14D0]
0x180014a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a9b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014aa2  test    rax, rax
0x180014aa5  jz      short loc_180014AB8
0x180014aa7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180014aac  jnz     short loc_180014AB8
0x180014aae  lea     rcx, [rsp+14F0h+var_14D0]
0x180014ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ab8  cmp     [rsp+14F0h+var_14C8], r15d
0x180014abd  jge     loc_180014BBF
0x180014ac3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180014aca  jnz     short loc_180014AEB
0x180014acc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180014ad3  test    rax, rax
0x180014ad6  jz      short loc_180014AE1
0x180014ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014add  test    al, al
0x180014adf  jmp     short loc_180014AE9
0x180014ae1  call    cs:__imp_IsDebuggerPresent
0x180014ae7  test    eax, eax
0x180014ae9  jz      short loc_180014AF2
0x180014aeb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180014af0  jz      short loc_180014B18
0x180014af2  mov     rax, cs:g_pfnResultLoggingCallback
0x180014af9  test    rax, rax
0x180014afc  jz      short loc_180014B71
0x180014afe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180014b05  jnz     short loc_180014B71
0x180014b07  xor     r8d, r8d
0x180014b0a  lea     rcx, [rsp+14F0h+var_14D0]
0x180014b0f  xor     edx, edx
0x180014b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b16  jmp     short loc_180014B71
0x180014b18  mov     rax, cs:g_pfnResultLoggingCallback
0x180014b1f  mov     ebx, 800h
0x180014b24  test    rax, rax
0x180014b27  jz      short loc_180014B46
0x180014b29  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180014b30  jnz     short loc_180014B46
0x180014b32  mov     r8d, ebx
0x180014b35  lea     rdx, [rbp+13F0h+OutputString]
0x180014b3c  lea     rcx, [rsp+14F0h+var_14D0]
0x180014b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b46  cmp     [rbp+13F0h+OutputString], r15w
0x180014b4e  jnz     short loc_180014B64
0x180014b50  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180014b55  mov     rdx, rbx; unsigned __int16 *
0x180014b58  lea     rcx, [rbp+13F0h+OutputString]; this
0x180014b5f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180014b64  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180014b6b  call    cs:__imp_OutputDebugStringW
0x180014b71  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180014b76  jnz     short loc_180014B81
0x180014b78  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180014b7f  jz      short loc_180014B92
0x180014b81  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180014b88  test    rax, rax
0x180014b8b  jz      short loc_180014B92
0x180014b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b92  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180014b97  jnz     short loc_180014BC5
0x180014b99  mov     rcx, [rbp+13F0h+var_30]
0x180014ba0  xor     rcx, rsp; StackCookie
0x180014ba3  call    __security_check_cookie
0x180014ba8  mov     rbx, [rsp+14F0h+arg_10]
0x180014bb0  add     rsp, 14D0h
0x180014bb7  pop     r15
0x180014bb9  pop     r14
0x180014bbb  pop     rdi
0x180014bbc  pop     rsi
0x180014bbd  pop     rbp
0x180014bbe  retn
0x180014bbf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180014bc5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180014bca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
