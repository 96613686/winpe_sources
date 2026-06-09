# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002e1c`
- end: `0x1800030b0`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800028fc`

## callees

- `0x180002e1c`
- `0x180004ce4`
- `0x1800064d4`
- `0x180008230`
- `0x1800083ec`
- `0x18002170a`
- `0x180021740`
- `0x1800217d0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ec6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ec6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000304b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000304b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002fc1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002fc1`

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
0x180002e1c  mov     [rsp-8+arg_10], rbx
0x180002e21  push    rbp
0x180002e22  push    rsi
0x180002e23  push    rdi
0x180002e24  push    r14
0x180002e26  push    r15
0x180002e28  lea     rbp, [rsp-13D0h]
0x180002e30  mov     eax, 14D0h
0x180002e35  call    _alloca_probe
0x180002e3a  sub     rsp, rax
0x180002e3d  mov     rax, cs:__security_cookie
0x180002e44  xor     rax, rsp
0x180002e47  mov     [rbp+13F0h+var_30], rax
0x180002e4e  mov     rdi, [rbp+13F0h+arg_28]
0x180002e55  mov     esi, edx
0x180002e57  mov     r14, rcx
0x180002e5a  xor     edx, edx; Val
0x180002e5c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002e61  mov     r8d, 98h; Size
0x180002e67  call    memset_0
0x180002e6c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002e73  xor     r15d, r15d
0x180002e76  mov     [rbp+13F0h+OutputString], r15w
0x180002e7e  mov     [rbp+13F0h+var_1430], r15b
0x180002e82  mov     ecx, [rdx]; this
0x180002e84  mov     eax, [rdx+4]
0x180002e87  mov     [rsp+14F0h+var_14C8], ecx
0x180002e8b  mov     [rsp+14F0h+var_14C4], eax
0x180002e8f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002e94  cmp     dword ptr [rdx+8], 1
0x180002e98  mov     ebx, eax
0x180002e9a  lea     eax, [r15+8]
0x180002e9e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002ea6  mov     ecx, r15d
0x180002ea9  cmovz   ecx, eax
0x180002eac  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002eb0  lea     ecx, [rax-7]
0x180002eb3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002ebb  inc     ecx
0x180002ebd  mov     [rsp+14F0h+var_14B8], r15
0x180002ec2  mov     [rsp+14F0h+var_14C0], ecx
0x180002ec6  call    cs:__imp_GetCurrentThreadId
0x180002ecc  xorps   xmm0, xmm0
0x180002ecf  mov     [rsp+14F0h+var_1490], esi
0x180002ed3  mov     [rsp+14F0h+var_14B0], eax
0x180002ed7  xorps   xmm1, xmm1
0x180002eda  lea     rax, aWil; "wil"
0x180002ee1  mov     [rsp+14F0h+var_148C], ebx
0x180002ee5  mov     [rsp+14F0h+var_1498], rax
0x180002eea  xor     eax, eax
0x180002eec  mov     [rbp+13F0h+var_1458], rax
0x180002ef0  mov     [rbp+13F0h+var_1470], rax
0x180002ef4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002efb  mov     [rsp+14F0h+var_14A8], r15
0x180002f00  mov     [rsp+14F0h+var_14A0], r15
0x180002f05  mov     [rbp+13F0h+var_1448], rdi
0x180002f09  mov     [rbp+13F0h+var_1440], r14
0x180002f0d  mov     [rsp+14F0h+var_1488], r15
0x180002f12  movups  [rbp+13F0h+var_1468], xmm0
0x180002f16  movups  [rsp+14F0h+var_1480], xmm1
0x180002f1b  test    rax, rax
0x180002f1e  jz      short loc_180002F2B
0x180002f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f25  mov     [rbp+13F0h+var_1450], rax
0x180002f29  jmp     short loc_180002F2F
0x180002f2b  mov     [rbp+13F0h+var_1450], r15
0x180002f2f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002f36  test    rax, rax
0x180002f39  jz      short loc_180002F45
0x180002f3b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f45  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002f4c  test    rax, rax
0x180002f4f  jz      short loc_180002F65
0x180002f51  mov     r8d, 400h
0x180002f57  lea     rdx, [rbp+13F0h+var_1430]
0x180002f5b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f65  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002f6c  test    rax, rax
0x180002f6f  jz      short loc_180002F7B
0x180002f71  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002f82  test    rax, rax
0x180002f85  jz      short loc_180002F98
0x180002f87  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002f8c  jnz     short loc_180002F98
0x180002f8e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f98  cmp     [rsp+14F0h+var_14C8], r15d
0x180002f9d  jge     loc_18000309F
0x180002fa3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002faa  jnz     short loc_180002FCB
0x180002fac  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002fb3  test    rax, rax
0x180002fb6  jz      short loc_180002FC1
0x180002fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fbd  test    al, al
0x180002fbf  jmp     short loc_180002FC9
0x180002fc1  call    cs:__imp_IsDebuggerPresent
0x180002fc7  test    eax, eax
0x180002fc9  jz      short loc_180002FD2
0x180002fcb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002fd0  jz      short loc_180002FF8
0x180002fd2  mov     rax, cs:g_pfnResultLoggingCallback
0x180002fd9  test    rax, rax
0x180002fdc  jz      short loc_180003051
0x180002fde  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002fe5  jnz     short loc_180003051
0x180002fe7  xor     r8d, r8d
0x180002fea  lea     rcx, [rsp+14F0h+var_14D0]
0x180002fef  xor     edx, edx
0x180002ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff6  jmp     short loc_180003051
0x180002ff8  mov     rax, cs:g_pfnResultLoggingCallback
0x180002fff  mov     ebx, 800h
0x180003004  test    rax, rax
0x180003007  jz      short loc_180003026
0x180003009  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003010  jnz     short loc_180003026
0x180003012  mov     r8d, ebx
0x180003015  lea     rdx, [rbp+13F0h+OutputString]
0x18000301c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003026  cmp     [rbp+13F0h+OutputString], r15w
0x18000302e  jnz     short loc_180003044
0x180003030  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003035  mov     rdx, rbx; unsigned __int16 *
0x180003038  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000303f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003044  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000304b  call    cs:__imp_OutputDebugStringW
0x180003051  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003056  jnz     short loc_180003061
0x180003058  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000305f  jz      short loc_180003072
0x180003061  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003068  test    rax, rax
0x18000306b  jz      short loc_180003072
0x18000306d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003072  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003077  jnz     short loc_1800030A5
0x180003079  mov     rcx, [rbp+13F0h+var_30]
0x180003080  xor     rcx, rsp; StackCookie
0x180003083  call    __security_check_cookie
0x180003088  mov     rbx, [rsp+14F0h+arg_10]
0x180003090  add     rsp, 14D0h
0x180003097  pop     r15
0x180003099  pop     r14
0x18000309b  pop     rdi
0x18000309c  pop     rsi
0x18000309d  pop     rbp
0x18000309e  retn
0x18000309f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800030a5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800030aa  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
