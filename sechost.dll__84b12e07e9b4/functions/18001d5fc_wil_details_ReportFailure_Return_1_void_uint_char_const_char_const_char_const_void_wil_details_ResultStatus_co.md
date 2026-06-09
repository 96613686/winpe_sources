# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001d5fc`
- end: `0x18001d890`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001b240`

## callees

- `0x1800193f0`
- `0x18001d5fc`
- `0x18001e114`
- `0x18001eec0`
- `0x18001f578`
- `0x18004f91a`
- `0x18004fa50`
- `0x18004fb10`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d82b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d82b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d7a1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d7a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d6a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d6a6`

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
0x18001d5fc  mov     [rsp-8+arg_10], rbx
0x18001d601  push    rbp
0x18001d602  push    rsi
0x18001d603  push    rdi
0x18001d604  push    r14
0x18001d606  push    r15
0x18001d608  lea     rbp, [rsp-13D0h]
0x18001d610  mov     eax, 14D0h
0x18001d615  call    _alloca_probe
0x18001d61a  sub     rsp, rax
0x18001d61d  mov     rax, cs:__security_cookie
0x18001d624  xor     rax, rsp
0x18001d627  mov     [rbp+13F0h+var_30], rax
0x18001d62e  mov     rdi, [rbp+13F0h+arg_28]
0x18001d635  mov     esi, edx
0x18001d637  mov     r14, rcx
0x18001d63a  xor     edx, edx; Val
0x18001d63c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001d641  mov     r8d, 98h; Size
0x18001d647  call    memset_0
0x18001d64c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001d653  xor     r15d, r15d
0x18001d656  mov     [rbp+13F0h+OutputString], r15w
0x18001d65e  mov     [rbp+13F0h+var_1430], r15b
0x18001d662  mov     ecx, [rdx]; this
0x18001d664  mov     eax, [rdx+4]
0x18001d667  mov     [rsp+14F0h+var_14C8], ecx
0x18001d66b  mov     [rsp+14F0h+var_14C4], eax
0x18001d66f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001d674  cmp     dword ptr [rdx+8], 1
0x18001d678  mov     ebx, eax
0x18001d67a  lea     eax, [r15+8]
0x18001d67e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18001d686  mov     ecx, r15d
0x18001d689  cmovz   ecx, eax
0x18001d68c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001d690  lea     ecx, [rax-7]
0x18001d693  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001d69b  inc     ecx
0x18001d69d  mov     [rsp+14F0h+var_14B8], r15
0x18001d6a2  mov     [rsp+14F0h+var_14C0], ecx
0x18001d6a6  call    cs:__imp_GetCurrentThreadId
0x18001d6ac  xorps   xmm0, xmm0
0x18001d6af  mov     [rsp+14F0h+var_1490], esi
0x18001d6b3  mov     [rsp+14F0h+var_14B0], eax
0x18001d6b7  xorps   xmm1, xmm1
0x18001d6ba  lea     rax, aWil; "wil"
0x18001d6c1  mov     [rsp+14F0h+var_148C], ebx
0x18001d6c5  mov     [rsp+14F0h+var_1498], rax
0x18001d6ca  xor     eax, eax
0x18001d6cc  mov     [rbp+13F0h+var_1458], rax
0x18001d6d0  mov     [rbp+13F0h+var_1470], rax
0x18001d6d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001d6db  mov     [rsp+14F0h+var_14A8], r15
0x18001d6e0  mov     [rsp+14F0h+var_14A0], r15
0x18001d6e5  mov     [rbp+13F0h+var_1448], rdi
0x18001d6e9  mov     [rbp+13F0h+var_1440], r14
0x18001d6ed  mov     [rsp+14F0h+var_1488], r15
0x18001d6f2  movups  [rbp+13F0h+var_1468], xmm0
0x18001d6f6  movups  [rsp+14F0h+var_1480], xmm1
0x18001d6fb  test    rax, rax
0x18001d6fe  jz      short loc_18001D70B
0x18001d700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d705  mov     [rbp+13F0h+var_1450], rax
0x18001d709  jmp     short loc_18001D70F
0x18001d70b  mov     [rbp+13F0h+var_1450], r15
0x18001d70f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001d716  test    rax, rax
0x18001d719  jz      short loc_18001D725
0x18001d71b  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d725  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001d72c  test    rax, rax
0x18001d72f  jz      short loc_18001D745
0x18001d731  mov     r8d, 400h
0x18001d737  lea     rdx, [rbp+13F0h+var_1430]
0x18001d73b  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d745  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d74c  test    rax, rax
0x18001d74f  jz      short loc_18001D75B
0x18001d751  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d75b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d762  test    rax, rax
0x18001d765  jz      short loc_18001D778
0x18001d767  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001d76c  jnz     short loc_18001D778
0x18001d76e  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d778  cmp     [rsp+14F0h+var_14C8], r15d
0x18001d77d  jge     loc_18001D87F
0x18001d783  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001d78a  jnz     short loc_18001D7AB
0x18001d78c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001d793  test    rax, rax
0x18001d796  jz      short loc_18001D7A1
0x18001d798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d79d  test    al, al
0x18001d79f  jmp     short loc_18001D7A9
0x18001d7a1  call    cs:__imp_IsDebuggerPresent
0x18001d7a7  test    eax, eax
0x18001d7a9  jz      short loc_18001D7B2
0x18001d7ab  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001d7b0  jz      short loc_18001D7D8
0x18001d7b2  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d7b9  test    rax, rax
0x18001d7bc  jz      short loc_18001D831
0x18001d7be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001d7c5  jnz     short loc_18001D831
0x18001d7c7  xor     r8d, r8d
0x18001d7ca  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d7cf  xor     edx, edx
0x18001d7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d6  jmp     short loc_18001D831
0x18001d7d8  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d7df  mov     ebx, 800h
0x18001d7e4  test    rax, rax
0x18001d7e7  jz      short loc_18001D806
0x18001d7e9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001d7f0  jnz     short loc_18001D806
0x18001d7f2  mov     r8d, ebx
0x18001d7f5  lea     rdx, [rbp+13F0h+OutputString]
0x18001d7fc  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d806  cmp     [rbp+13F0h+OutputString], r15w
0x18001d80e  jnz     short loc_18001D824
0x18001d810  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001d815  mov     rdx, rbx; unsigned __int16 *
0x18001d818  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001d81f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001d824  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001d82b  call    cs:__imp_OutputDebugStringW
0x18001d831  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001d836  jnz     short loc_18001D841
0x18001d838  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001d83f  jz      short loc_18001D852
0x18001d841  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001d848  test    rax, rax
0x18001d84b  jz      short loc_18001D852
0x18001d84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d852  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001d857  jnz     short loc_18001D885
0x18001d859  mov     rcx, [rbp+13F0h+var_30]
0x18001d860  xor     rcx, rsp; StackCookie
0x18001d863  call    __security_check_cookie
0x18001d868  mov     rbx, [rsp+14F0h+arg_10]
0x18001d870  add     rsp, 14D0h
0x18001d877  pop     r15
0x18001d879  pop     r14
0x18001d87b  pop     rdi
0x18001d87c  pop     rsi
0x18001d87d  pop     rbp
0x18001d87e  retn
0x18001d87f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001d885  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001d88a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
