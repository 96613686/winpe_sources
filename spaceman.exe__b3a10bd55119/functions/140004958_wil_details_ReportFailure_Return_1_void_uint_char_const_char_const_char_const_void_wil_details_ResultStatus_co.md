# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004958`
- end: `0x140004bec`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140004438`

## callees

- `0x140004958`
- `0x140006834`
- `0x140007ce4`
- `0x140009e50`
- `0x14000a00c`
- `0x14000d1be`
- `0x14000d1f0`
- `0x14000d280`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004a02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004a02`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004b87`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004b87`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004afd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004afd`

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
0x140004958  mov     [rsp-8+arg_10], rbx
0x14000495d  push    rbp
0x14000495e  push    rsi
0x14000495f  push    rdi
0x140004960  push    r14
0x140004962  push    r15
0x140004964  lea     rbp, [rsp-13D0h]
0x14000496c  mov     eax, 14D0h
0x140004971  call    _alloca_probe
0x140004976  sub     rsp, rax
0x140004979  mov     rax, cs:__security_cookie
0x140004980  xor     rax, rsp
0x140004983  mov     [rbp+13F0h+var_30], rax
0x14000498a  mov     rdi, [rbp+13F0h+arg_28]
0x140004991  mov     esi, edx
0x140004993  mov     r14, rcx
0x140004996  xor     edx, edx; Val
0x140004998  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000499d  mov     r8d, 98h; Size
0x1400049a3  call    memset_0
0x1400049a8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400049af  xor     r15d, r15d
0x1400049b2  mov     [rbp+13F0h+OutputString], r15w
0x1400049ba  mov     [rbp+13F0h+var_1430], r15b
0x1400049be  mov     ecx, [rdx]; this
0x1400049c0  mov     eax, [rdx+4]
0x1400049c3  mov     [rsp+14F0h+var_14C8], ecx
0x1400049c7  mov     [rsp+14F0h+var_14C4], eax
0x1400049cb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400049d0  cmp     dword ptr [rdx+8], 1
0x1400049d4  mov     ebx, eax
0x1400049d6  lea     eax, [r15+8]
0x1400049da  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400049e2  mov     ecx, r15d
0x1400049e5  cmovz   ecx, eax
0x1400049e8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400049ec  lea     ecx, [rax-7]
0x1400049ef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400049f7  inc     ecx
0x1400049f9  mov     [rsp+14F0h+var_14B8], r15
0x1400049fe  mov     [rsp+14F0h+var_14C0], ecx
0x140004a02  call    cs:__imp_GetCurrentThreadId
0x140004a08  xorps   xmm0, xmm0
0x140004a0b  mov     [rsp+14F0h+var_1490], esi
0x140004a0f  mov     [rsp+14F0h+var_14B0], eax
0x140004a13  xorps   xmm1, xmm1
0x140004a16  lea     rax, aWil; "wil"
0x140004a1d  mov     [rsp+14F0h+var_148C], ebx
0x140004a21  mov     [rsp+14F0h+var_1498], rax
0x140004a26  xor     eax, eax
0x140004a28  mov     [rbp+13F0h+var_1458], rax
0x140004a2c  mov     [rbp+13F0h+var_1470], rax
0x140004a30  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004a37  mov     [rsp+14F0h+var_14A8], r15
0x140004a3c  mov     [rsp+14F0h+var_14A0], r15
0x140004a41  mov     [rbp+13F0h+var_1448], rdi
0x140004a45  mov     [rbp+13F0h+var_1440], r14
0x140004a49  mov     [rsp+14F0h+var_1488], r15
0x140004a4e  movups  [rbp+13F0h+var_1468], xmm0
0x140004a52  movups  [rsp+14F0h+var_1480], xmm1
0x140004a57  test    rax, rax
0x140004a5a  jz      short loc_140004A67
0x140004a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a61  mov     [rbp+13F0h+var_1450], rax
0x140004a65  jmp     short loc_140004A6B
0x140004a67  mov     [rbp+13F0h+var_1450], r15
0x140004a6b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004a72  test    rax, rax
0x140004a75  jz      short loc_140004A81
0x140004a77  lea     rcx, [rsp+14F0h+var_14D0]
0x140004a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a81  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004a88  test    rax, rax
0x140004a8b  jz      short loc_140004AA1
0x140004a8d  mov     r8d, 400h
0x140004a93  lea     rdx, [rbp+13F0h+var_1430]
0x140004a97  lea     rcx, [rsp+14F0h+var_14D0]
0x140004a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004aa1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004aa8  test    rax, rax
0x140004aab  jz      short loc_140004AB7
0x140004aad  lea     rcx, [rsp+14F0h+var_14D0]
0x140004ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ab7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004abe  test    rax, rax
0x140004ac1  jz      short loc_140004AD4
0x140004ac3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140004ac8  jnz     short loc_140004AD4
0x140004aca  lea     rcx, [rsp+14F0h+var_14D0]
0x140004acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ad4  cmp     [rsp+14F0h+var_14C8], r15d
0x140004ad9  jge     loc_140004BDB
0x140004adf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140004ae6  jnz     short loc_140004B07
0x140004ae8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004aef  test    rax, rax
0x140004af2  jz      short loc_140004AFD
0x140004af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004af9  test    al, al
0x140004afb  jmp     short loc_140004B05
0x140004afd  call    cs:__imp_IsDebuggerPresent
0x140004b03  test    eax, eax
0x140004b05  jz      short loc_140004B0E
0x140004b07  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140004b0c  jz      short loc_140004B34
0x140004b0e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004b15  test    rax, rax
0x140004b18  jz      short loc_140004B8D
0x140004b1a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004b21  jnz     short loc_140004B8D
0x140004b23  xor     r8d, r8d
0x140004b26  lea     rcx, [rsp+14F0h+var_14D0]
0x140004b2b  xor     edx, edx
0x140004b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b32  jmp     short loc_140004B8D
0x140004b34  mov     rax, cs:g_pfnResultLoggingCallback
0x140004b3b  mov     ebx, 800h
0x140004b40  test    rax, rax
0x140004b43  jz      short loc_140004B62
0x140004b45  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004b4c  jnz     short loc_140004B62
0x140004b4e  mov     r8d, ebx
0x140004b51  lea     rdx, [rbp+13F0h+OutputString]
0x140004b58  lea     rcx, [rsp+14F0h+var_14D0]
0x140004b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b62  cmp     [rbp+13F0h+OutputString], r15w
0x140004b6a  jnz     short loc_140004B80
0x140004b6c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140004b71  mov     rdx, rbx; unsigned __int16 *
0x140004b74  lea     rcx, [rbp+13F0h+OutputString]; this
0x140004b7b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004b80  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140004b87  call    cs:__imp_OutputDebugStringW
0x140004b8d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140004b92  jnz     short loc_140004B9D
0x140004b94  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140004b9b  jz      short loc_140004BAE
0x140004b9d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004ba4  test    rax, rax
0x140004ba7  jz      short loc_140004BAE
0x140004ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bae  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140004bb3  jnz     short loc_140004BE1
0x140004bb5  mov     rcx, [rbp+13F0h+var_30]
0x140004bbc  xor     rcx, rsp; StackCookie
0x140004bbf  call    __security_check_cookie
0x140004bc4  mov     rbx, [rsp+14F0h+arg_10]
0x140004bcc  add     rsp, 14D0h
0x140004bd3  pop     r15
0x140004bd5  pop     r14
0x140004bd7  pop     rdi
0x140004bd8  pop     rsi
0x140004bd9  pop     rbp
0x140004bda  retn
0x140004bdb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004be1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140004be6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
