# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800069d0`
- end: `0x180006c66`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004c28`

## callees

- `0x180005320`
- `0x180005cac`
- `0x1800069d0`
- `0x1800085b4`
- `0x180009d1c`
- `0x18000b878`
- `0x18000ba84`
- `0x180014fd0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a7b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006b76`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006b76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006c00`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006c00`

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
0x1800069d0  mov     [rsp-8+arg_10], rbx
0x1800069d5  push    rbp
0x1800069d6  push    rsi
0x1800069d7  push    rdi
0x1800069d8  push    r14
0x1800069da  push    r15
0x1800069dc  lea     rbp, [rsp-13D0h]
0x1800069e4  mov     eax, 14D0h
0x1800069e9  call    _alloca_probe
0x1800069ee  sub     rsp, rax
0x1800069f1  mov     rax, cs:__security_cookie
0x1800069f8  xor     rax, rsp
0x1800069fb  mov     [rbp+13F0h+var_30], rax
0x180006a02  mov     esi, edx
0x180006a04  mov     r14, rcx
0x180006a07  mov     rdi, [rbp+13F0h+arg_28]
0x180006a0e  xor     edx, edx; Val
0x180006a10  mov     r8d, 98h; Size
0x180006a16  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006a1b  call    memset_0
0x180006a20  nop
0x180006a21  xor     r15d, r15d
0x180006a24  mov     [rbp+13F0h+OutputString], r15w
0x180006a2c  mov     [rbp+13F0h+var_1430], r15b
0x180006a30  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180006a37  mov     ecx, [rdx]; this
0x180006a39  mov     [rsp+14F0h+var_14C8], ecx
0x180006a3d  mov     eax, [rdx+4]
0x180006a40  mov     [rsp+14F0h+var_14C4], eax
0x180006a44  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006a49  mov     ebx, eax
0x180006a4b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180006a53  mov     ecx, r15d
0x180006a56  lea     eax, [r15+8]
0x180006a5a  cmp     dword ptr [rdx+8], 1
0x180006a5e  cmovz   ecx, eax
0x180006a61  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006a65  lea     ecx, [rax-7]
0x180006a68  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006a70  inc     ecx
0x180006a72  mov     [rsp+14F0h+var_14C0], ecx
0x180006a76  mov     [rsp+14F0h+var_14B8], r15
0x180006a7b  call    cs:__imp_GetCurrentThreadId
0x180006a81  mov     [rsp+14F0h+var_14B0], eax
0x180006a85  lea     rax, aWil; "wil"
0x180006a8c  mov     [rsp+14F0h+var_1498], rax
0x180006a91  mov     [rsp+14F0h+var_1490], esi
0x180006a95  mov     [rsp+14F0h+var_148C], ebx
0x180006a99  mov     [rsp+14F0h+var_14A8], r15
0x180006a9e  mov     [rsp+14F0h+var_14A0], r15
0x180006aa3  mov     [rbp+13F0h+var_1448], rdi
0x180006aa7  mov     [rbp+13F0h+var_1440], r14
0x180006aab  mov     [rsp+14F0h+var_1488], r15
0x180006ab0  xorps   xmm0, xmm0
0x180006ab3  xor     eax, eax
0x180006ab5  movups  [rbp+13F0h+var_1468], xmm0
0x180006ab9  mov     [rbp+13F0h+var_1458], rax
0x180006abd  xorps   xmm1, xmm1
0x180006ac0  movups  [rsp+14F0h+var_1480], xmm1
0x180006ac5  mov     [rbp+13F0h+var_1470], rax
0x180006ac9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006ad0  test    rax, rax
0x180006ad3  jz      short loc_180006AE0
0x180006ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ada  mov     [rbp+13F0h+var_1450], rax
0x180006ade  jmp     short loc_180006AE4
0x180006ae0  mov     [rbp+13F0h+var_1450], r15
0x180006ae4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006aeb  test    rax, rax
0x180006aee  jz      short loc_180006AFA
0x180006af0  lea     rcx, [rsp+14F0h+var_14D0]
0x180006af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006afa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006b01  test    rax, rax
0x180006b04  jz      short loc_180006B1A
0x180006b06  mov     r8d, 400h
0x180006b0c  lea     rdx, [rbp+13F0h+var_1430]
0x180006b10  lea     rcx, [rsp+14F0h+var_14D0]
0x180006b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006b21  test    rax, rax
0x180006b24  jz      short loc_180006B30
0x180006b26  lea     rcx, [rsp+14F0h+var_14D0]
0x180006b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b30  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006b37  test    rax, rax
0x180006b3a  jz      short loc_180006B4D
0x180006b3c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006b41  jnz     short loc_180006B4D
0x180006b43  lea     rcx, [rsp+14F0h+var_14D0]
0x180006b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4d  cmp     [rsp+14F0h+var_14C8], r15d
0x180006b52  jge     loc_180006C60
0x180006b58  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180006b5f  jnz     short loc_180006B80
0x180006b61  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006b68  test    rax, rax
0x180006b6b  jz      short loc_180006B76
0x180006b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b72  test    al, al
0x180006b74  jmp     short loc_180006B7E
0x180006b76  call    cs:__imp_IsDebuggerPresent
0x180006b7c  test    eax, eax
0x180006b7e  jz      short loc_180006B87
0x180006b80  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006b85  jz      short loc_180006BAD
0x180006b87  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b8e  test    rax, rax
0x180006b91  jz      short loc_180006C06
0x180006b93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006b9a  jnz     short loc_180006C06
0x180006b9c  xor     r8d, r8d
0x180006b9f  xor     edx, edx
0x180006ba1  lea     rcx, [rsp+14F0h+var_14D0]
0x180006ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bab  jmp     short loc_180006C06
0x180006bad  mov     ebx, 800h
0x180006bb2  mov     rax, cs:g_pfnResultLoggingCallback
0x180006bb9  test    rax, rax
0x180006bbc  jz      short loc_180006BDB
0x180006bbe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006bc5  jnz     short loc_180006BDB
0x180006bc7  mov     r8d, ebx
0x180006bca  lea     rdx, [rbp+13F0h+OutputString]
0x180006bd1  lea     rcx, [rsp+14F0h+var_14D0]
0x180006bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bdb  cmp     [rbp+13F0h+OutputString], r15w
0x180006be3  jnz     short loc_180006BF9
0x180006be5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006bea  mov     rdx, rbx; unsigned __int16 *
0x180006bed  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006bf4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006bf9  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006c00  call    cs:__imp_OutputDebugStringW
0x180006c06  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006c0b  jnz     short loc_180006C16
0x180006c0d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180006c14  jz      short loc_180006C28
0x180006c16  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006c1d  test    rax, rax
0x180006c20  jz      short loc_180006C28
0x180006c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c27  nop
0x180006c28  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180006c2d  jnz     short loc_180006C55
0x180006c2f  mov     rcx, [rbp+13F0h+var_30]
0x180006c36  xor     rcx, rsp; StackCookie
0x180006c39  call    __security_check_cookie
0x180006c3e  mov     rbx, [rsp+14F0h+arg_10]
0x180006c46  add     rsp, 14D0h
0x180006c4d  pop     r15
0x180006c4f  pop     r14
0x180006c51  pop     rdi
0x180006c52  pop     rsi
0x180006c53  pop     rbp
0x180006c54  retn
0x180006c55  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006c5a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006c60  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
