# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000fcb8`
- end: `0x18000ff4c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f798`

## callees

- `0x18000fcb8`
- `0x180011964`
- `0x180012e14`
- `0x1800147d0`
- `0x18001498c`
- `0x1800157be`
- `0x1800157f0`
- `0x180015880`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000fd62`
- `KERNEL32!GetCurrentThreadId` at `0x18000fd62`
- `KERNEL32!OutputDebugStringW` at `0x18000fee7`
- `KERNEL32!OutputDebugStringW` at `0x18000fee7`
- `KERNEL32!IsDebuggerPresent` at `0x18000fe5d`
- `KERNEL32!IsDebuggerPresent` at `0x18000fe5d`

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
0x18000fcb8  mov     [rsp-8+arg_10], rbx
0x18000fcbd  push    rbp
0x18000fcbe  push    rsi
0x18000fcbf  push    rdi
0x18000fcc0  push    r14
0x18000fcc2  push    r15
0x18000fcc4  lea     rbp, [rsp-13D0h]
0x18000fccc  mov     eax, 14D0h
0x18000fcd1  call    _alloca_probe
0x18000fcd6  sub     rsp, rax
0x18000fcd9  mov     rax, cs:__security_cookie
0x18000fce0  xor     rax, rsp
0x18000fce3  mov     [rbp+13F0h+var_30], rax
0x18000fcea  mov     rdi, [rbp+13F0h+arg_28]
0x18000fcf1  mov     esi, edx
0x18000fcf3  mov     r14, rcx
0x18000fcf6  xor     edx, edx; Val
0x18000fcf8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000fcfd  mov     r8d, 98h; Size
0x18000fd03  call    memset_0
0x18000fd08  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000fd0f  xor     r15d, r15d
0x18000fd12  mov     [rbp+13F0h+OutputString], r15w
0x18000fd1a  mov     [rbp+13F0h+var_1430], r15b
0x18000fd1e  mov     ecx, [rdx]; this
0x18000fd20  mov     eax, [rdx+4]
0x18000fd23  mov     [rsp+14F0h+var_14C8], ecx
0x18000fd27  mov     [rsp+14F0h+var_14C4], eax
0x18000fd2b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000fd30  cmp     dword ptr [rdx+8], 1
0x18000fd34  mov     ebx, eax
0x18000fd36  lea     eax, [r15+8]
0x18000fd3a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000fd42  mov     ecx, r15d
0x18000fd45  cmovz   ecx, eax
0x18000fd48  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000fd4c  lea     ecx, [rax-7]
0x18000fd4f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000fd57  inc     ecx
0x18000fd59  mov     [rsp+14F0h+var_14B8], r15
0x18000fd5e  mov     [rsp+14F0h+var_14C0], ecx
0x18000fd62  call    cs:__imp_GetCurrentThreadId
0x18000fd68  xorps   xmm0, xmm0
0x18000fd6b  mov     [rsp+14F0h+var_1490], esi
0x18000fd6f  mov     [rsp+14F0h+var_14B0], eax
0x18000fd73  xorps   xmm1, xmm1
0x18000fd76  lea     rax, aWil; "wil"
0x18000fd7d  mov     [rsp+14F0h+var_148C], ebx
0x18000fd81  mov     [rsp+14F0h+var_1498], rax
0x18000fd86  xor     eax, eax
0x18000fd88  mov     [rbp+13F0h+var_1458], rax
0x18000fd8c  mov     [rbp+13F0h+var_1470], rax
0x18000fd90  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000fd97  mov     [rsp+14F0h+var_14A8], r15
0x18000fd9c  mov     [rsp+14F0h+var_14A0], r15
0x18000fda1  mov     [rbp+13F0h+var_1448], rdi
0x18000fda5  mov     [rbp+13F0h+var_1440], r14
0x18000fda9  mov     [rsp+14F0h+var_1488], r15
0x18000fdae  movups  [rbp+13F0h+var_1468], xmm0
0x18000fdb2  movups  [rsp+14F0h+var_1480], xmm1
0x18000fdb7  test    rax, rax
0x18000fdba  jz      short loc_18000FDC7
0x18000fdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdc1  mov     [rbp+13F0h+var_1450], rax
0x18000fdc5  jmp     short loc_18000FDCB
0x18000fdc7  mov     [rbp+13F0h+var_1450], r15
0x18000fdcb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000fdd2  test    rax, rax
0x18000fdd5  jz      short loc_18000FDE1
0x18000fdd7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fde1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000fde8  test    rax, rax
0x18000fdeb  jz      short loc_18000FE01
0x18000fded  mov     r8d, 400h
0x18000fdf3  lea     rdx, [rbp+13F0h+var_1430]
0x18000fdf7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe01  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fe08  test    rax, rax
0x18000fe0b  jz      short loc_18000FE17
0x18000fe0d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fe12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe17  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fe1e  test    rax, rax
0x18000fe21  jz      short loc_18000FE34
0x18000fe23  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000fe28  jnz     short loc_18000FE34
0x18000fe2a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fe2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe34  cmp     [rsp+14F0h+var_14C8], r15d
0x18000fe39  jge     loc_18000FF3B
0x18000fe3f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000fe46  jnz     short loc_18000FE67
0x18000fe48  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000fe4f  test    rax, rax
0x18000fe52  jz      short loc_18000FE5D
0x18000fe54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe59  test    al, al
0x18000fe5b  jmp     short loc_18000FE65
0x18000fe5d  call    cs:__imp_IsDebuggerPresent
0x18000fe63  test    eax, eax
0x18000fe65  jz      short loc_18000FE6E
0x18000fe67  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000fe6c  jz      short loc_18000FE94
0x18000fe6e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fe75  test    rax, rax
0x18000fe78  jz      short loc_18000FEED
0x18000fe7a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000fe81  jnz     short loc_18000FEED
0x18000fe83  xor     r8d, r8d
0x18000fe86  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fe8b  xor     edx, edx
0x18000fe8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe92  jmp     short loc_18000FEED
0x18000fe94  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fe9b  mov     ebx, 800h
0x18000fea0  test    rax, rax
0x18000fea3  jz      short loc_18000FEC2
0x18000fea5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000feac  jnz     short loc_18000FEC2
0x18000feae  mov     r8d, ebx
0x18000feb1  lea     rdx, [rbp+13F0h+OutputString]
0x18000feb8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000febd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fec2  cmp     [rbp+13F0h+OutputString], r15w
0x18000feca  jnz     short loc_18000FEE0
0x18000fecc  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000fed1  mov     rdx, rbx; unsigned __int16 *
0x18000fed4  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000fedb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000fee0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000fee7  call    cs:__imp_OutputDebugStringW
0x18000feed  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000fef2  jnz     short loc_18000FEFD
0x18000fef4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000fefb  jz      short loc_18000FF0E
0x18000fefd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ff04  test    rax, rax
0x18000ff07  jz      short loc_18000FF0E
0x18000ff09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff0e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000ff13  jnz     short loc_18000FF41
0x18000ff15  mov     rcx, [rbp+13F0h+var_30]
0x18000ff1c  xor     rcx, rsp; StackCookie
0x18000ff1f  call    __security_check_cookie
0x18000ff24  mov     rbx, [rsp+14F0h+arg_10]
0x18000ff2c  add     rsp, 14D0h
0x18000ff33  pop     r15
0x18000ff35  pop     r14
0x18000ff37  pop     rdi
0x18000ff38  pop     rsi
0x18000ff39  pop     rbp
0x18000ff3a  retn
0x18000ff3b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000ff41  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ff46  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
