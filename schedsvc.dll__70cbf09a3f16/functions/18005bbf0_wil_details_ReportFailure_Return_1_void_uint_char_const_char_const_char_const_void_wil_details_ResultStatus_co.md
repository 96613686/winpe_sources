# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18005bbf0`
- end: `0x18005be86`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800568b8`

## callees

- `0x18005bbf0`
- `0x18005d550`
- `0x18005efc4`
- `0x180061078`
- `0x1800616e8`
- `0x18007e68a`
- `0x18007e6d0`
- `0x18007e790`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bc9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bc9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005be20`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005be20`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005bd96`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005bd96`

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
0x18005bbf0  mov     [rsp-8+arg_10], rbx
0x18005bbf5  push    rbp
0x18005bbf6  push    rsi
0x18005bbf7  push    rdi
0x18005bbf8  push    r14
0x18005bbfa  push    r15
0x18005bbfc  lea     rbp, [rsp-13D0h]
0x18005bc04  mov     eax, 14D0h
0x18005bc09  call    _alloca_probe
0x18005bc0e  sub     rsp, rax
0x18005bc11  mov     rax, cs:__security_cookie
0x18005bc18  xor     rax, rsp
0x18005bc1b  mov     [rbp+13F0h+var_30], rax
0x18005bc22  mov     esi, edx
0x18005bc24  mov     r14, rcx
0x18005bc27  mov     rdi, [rbp+13F0h+arg_28]
0x18005bc2e  xor     edx, edx; Val
0x18005bc30  mov     r8d, 98h; Size
0x18005bc36  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18005bc3b  call    memset_0
0x18005bc40  nop
0x18005bc41  xor     r15d, r15d
0x18005bc44  mov     [rbp+13F0h+OutputString], r15w
0x18005bc4c  mov     [rbp+13F0h+var_1430], r15b
0x18005bc50  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18005bc57  mov     ecx, [rdx]; this
0x18005bc59  mov     [rsp+14F0h+var_14C8], ecx
0x18005bc5d  mov     eax, [rdx+4]
0x18005bc60  mov     [rsp+14F0h+var_14C4], eax
0x18005bc64  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005bc69  mov     ebx, eax
0x18005bc6b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18005bc73  mov     ecx, r15d
0x18005bc76  lea     eax, [r15+8]
0x18005bc7a  cmp     dword ptr [rdx+8], 1
0x18005bc7e  cmovz   ecx, eax
0x18005bc81  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18005bc85  lea     ecx, [rax-7]
0x18005bc88  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005bc90  inc     ecx
0x18005bc92  mov     [rsp+14F0h+var_14C0], ecx
0x18005bc96  mov     [rsp+14F0h+var_14B8], r15
0x18005bc9b  call    cs:__imp_GetCurrentThreadId
0x18005bca1  mov     [rsp+14F0h+var_14B0], eax
0x18005bca5  lea     rax, aWil; "wil"
0x18005bcac  mov     [rsp+14F0h+var_1498], rax
0x18005bcb1  mov     [rsp+14F0h+var_1490], esi
0x18005bcb5  mov     [rsp+14F0h+var_148C], ebx
0x18005bcb9  mov     [rsp+14F0h+var_14A8], r15
0x18005bcbe  mov     [rsp+14F0h+var_14A0], r15
0x18005bcc3  mov     [rbp+13F0h+var_1448], rdi
0x18005bcc7  mov     [rbp+13F0h+var_1440], r14
0x18005bccb  mov     [rsp+14F0h+var_1488], r15
0x18005bcd0  xorps   xmm0, xmm0
0x18005bcd3  xor     eax, eax
0x18005bcd5  movups  [rbp+13F0h+var_1468], xmm0
0x18005bcd9  mov     [rbp+13F0h+var_1458], rax
0x18005bcdd  xorps   xmm1, xmm1
0x18005bce0  movups  [rsp+14F0h+var_1480], xmm1
0x18005bce5  mov     [rbp+13F0h+var_1470], rax
0x18005bce9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005bcf0  test    rax, rax
0x18005bcf3  jz      short loc_18005BD00
0x18005bcf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcfa  mov     [rbp+13F0h+var_1450], rax
0x18005bcfe  jmp     short loc_18005BD04
0x18005bd00  mov     [rbp+13F0h+var_1450], r15
0x18005bd04  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005bd0b  test    rax, rax
0x18005bd0e  jz      short loc_18005BD1A
0x18005bd10  lea     rcx, [rsp+14F0h+var_14D0]
0x18005bd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd1a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005bd21  test    rax, rax
0x18005bd24  jz      short loc_18005BD3A
0x18005bd26  mov     r8d, 400h
0x18005bd2c  lea     rdx, [rbp+13F0h+var_1430]
0x18005bd30  lea     rcx, [rsp+14F0h+var_14D0]
0x18005bd35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd3a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005bd41  test    rax, rax
0x18005bd44  jz      short loc_18005BD50
0x18005bd46  lea     rcx, [rsp+14F0h+var_14D0]
0x18005bd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd50  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005bd57  test    rax, rax
0x18005bd5a  jz      short loc_18005BD6D
0x18005bd5c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18005bd61  jnz     short loc_18005BD6D
0x18005bd63  lea     rcx, [rsp+14F0h+var_14D0]
0x18005bd68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd6d  cmp     [rsp+14F0h+var_14C8], r15d
0x18005bd72  jge     loc_18005BE80
0x18005bd78  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18005bd7f  jnz     short loc_18005BDA0
0x18005bd81  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005bd88  test    rax, rax
0x18005bd8b  jz      short loc_18005BD96
0x18005bd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd92  test    al, al
0x18005bd94  jmp     short loc_18005BD9E
0x18005bd96  call    cs:__imp_IsDebuggerPresent
0x18005bd9c  test    eax, eax
0x18005bd9e  jz      short loc_18005BDA7
0x18005bda0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18005bda5  jz      short loc_18005BDCD
0x18005bda7  mov     rax, cs:g_pfnResultLoggingCallback
0x18005bdae  test    rax, rax
0x18005bdb1  jz      short loc_18005BE26
0x18005bdb3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005bdba  jnz     short loc_18005BE26
0x18005bdbc  xor     r8d, r8d
0x18005bdbf  xor     edx, edx
0x18005bdc1  lea     rcx, [rsp+14F0h+var_14D0]
0x18005bdc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdcb  jmp     short loc_18005BE26
0x18005bdcd  mov     ebx, 800h
0x18005bdd2  mov     rax, cs:g_pfnResultLoggingCallback
0x18005bdd9  test    rax, rax
0x18005bddc  jz      short loc_18005BDFB
0x18005bdde  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005bde5  jnz     short loc_18005BDFB
0x18005bde7  mov     r8d, ebx
0x18005bdea  lea     rdx, [rbp+13F0h+OutputString]
0x18005bdf1  lea     rcx, [rsp+14F0h+var_14D0]
0x18005bdf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdfb  cmp     [rbp+13F0h+OutputString], r15w
0x18005be03  jnz     short loc_18005BE19
0x18005be05  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18005be0a  mov     rdx, rbx; unsigned __int16 *
0x18005be0d  lea     rcx, [rbp+13F0h+OutputString]; this
0x18005be14  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005be19  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18005be20  call    cs:__imp_OutputDebugStringW
0x18005be26  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18005be2b  jnz     short loc_18005BE36
0x18005be2d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18005be34  jz      short loc_18005BE48
0x18005be36  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005be3d  test    rax, rax
0x18005be40  jz      short loc_18005BE48
0x18005be42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be47  nop
0x18005be48  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18005be4d  jnz     short loc_18005BE75
0x18005be4f  mov     rcx, [rbp+13F0h+var_30]
0x18005be56  xor     rcx, rsp; StackCookie
0x18005be59  call    __security_check_cookie
0x18005be5e  mov     rbx, [rsp+14F0h+arg_10]
0x18005be66  add     rsp, 14D0h
0x18005be6d  pop     r15
0x18005be6f  pop     r14
0x18005be71  pop     rdi
0x18005be72  pop     rsi
0x18005be73  pop     rbp
0x18005be74  retn
0x18005be75  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18005be7a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18005be80  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
