# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180014e78`
- end: `0x18001510c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180014b4c`

## callees

- `0x180004d34`
- `0x180014e78`
- `0x180016204`
- `0x1800167f0`
- `0x1800168cc`
- `0x180016c1e`
- `0x180016c50`
- `0x180016d10`
- `0x180018010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18001501d`
- `KERNEL32!IsDebuggerPresent` at `0x18001501d`
- `KERNEL32!OutputDebugStringW` at `0x1800150a7`
- `KERNEL32!OutputDebugStringW` at `0x1800150a7`
- `KERNEL32!GetCurrentThreadId` at `0x180014f22`
- `KERNEL32!GetCurrentThreadId` at `0x180014f22`

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
0x180014e78  mov     [rsp-8+arg_10], rbx
0x180014e7d  push    rbp
0x180014e7e  push    rsi
0x180014e7f  push    rdi
0x180014e80  push    r14
0x180014e82  push    r15
0x180014e84  lea     rbp, [rsp-13D0h]
0x180014e8c  mov     eax, 14D0h
0x180014e91  call    _alloca_probe
0x180014e96  sub     rsp, rax
0x180014e99  mov     rax, cs:__security_cookie
0x180014ea0  xor     rax, rsp
0x180014ea3  mov     [rbp+13F0h+var_30], rax
0x180014eaa  mov     rdi, [rbp+13F0h+arg_28]
0x180014eb1  mov     esi, edx
0x180014eb3  mov     r14, rcx
0x180014eb6  xor     edx, edx; Val
0x180014eb8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180014ebd  mov     r8d, 98h; Size
0x180014ec3  call    memset_0
0x180014ec8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180014ecf  xor     r15d, r15d
0x180014ed2  mov     [rbp+13F0h+OutputString], r15w
0x180014eda  mov     [rbp+13F0h+var_1430], r15b
0x180014ede  mov     ecx, [rdx]; this
0x180014ee0  mov     eax, [rdx+4]
0x180014ee3  mov     [rsp+14F0h+var_14C8], ecx
0x180014ee7  mov     [rsp+14F0h+var_14C4], eax
0x180014eeb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180014ef0  cmp     dword ptr [rdx+8], 1
0x180014ef4  mov     ebx, eax
0x180014ef6  lea     eax, [r15+8]
0x180014efa  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180014f02  mov     ecx, r15d
0x180014f05  cmovz   ecx, eax
0x180014f08  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180014f0c  lea     ecx, [rax-7]
0x180014f0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180014f17  inc     ecx
0x180014f19  mov     [rsp+14F0h+var_14B8], r15
0x180014f1e  mov     [rsp+14F0h+var_14C0], ecx
0x180014f22  call    cs:__imp_GetCurrentThreadId
0x180014f28  xorps   xmm0, xmm0
0x180014f2b  mov     [rsp+14F0h+var_1490], esi
0x180014f2f  mov     [rsp+14F0h+var_14B0], eax
0x180014f33  xorps   xmm1, xmm1
0x180014f36  lea     rax, aWil; "wil"
0x180014f3d  mov     [rsp+14F0h+var_148C], ebx
0x180014f41  mov     [rsp+14F0h+var_1498], rax
0x180014f46  xor     eax, eax
0x180014f48  mov     [rbp+13F0h+var_1458], rax
0x180014f4c  mov     [rbp+13F0h+var_1470], rax
0x180014f50  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180014f57  mov     [rsp+14F0h+var_14A8], r15
0x180014f5c  mov     [rsp+14F0h+var_14A0], r15
0x180014f61  mov     [rbp+13F0h+var_1448], rdi
0x180014f65  mov     [rbp+13F0h+var_1440], r14
0x180014f69  mov     [rsp+14F0h+var_1488], r15
0x180014f6e  movups  [rbp+13F0h+var_1468], xmm0
0x180014f72  movups  [rsp+14F0h+var_1480], xmm1
0x180014f77  test    rax, rax
0x180014f7a  jz      short loc_180014F87
0x180014f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f81  mov     [rbp+13F0h+var_1450], rax
0x180014f85  jmp     short loc_180014F8B
0x180014f87  mov     [rbp+13F0h+var_1450], r15
0x180014f8b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180014f92  test    rax, rax
0x180014f95  jz      short loc_180014FA1
0x180014f97  lea     rcx, [rsp+14F0h+var_14D0]
0x180014f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fa1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180014fa8  test    rax, rax
0x180014fab  jz      short loc_180014FC1
0x180014fad  mov     r8d, 400h
0x180014fb3  lea     rdx, [rbp+13F0h+var_1430]
0x180014fb7  lea     rcx, [rsp+14F0h+var_14D0]
0x180014fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fc1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014fc8  test    rax, rax
0x180014fcb  jz      short loc_180014FD7
0x180014fcd  lea     rcx, [rsp+14F0h+var_14D0]
0x180014fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fd7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014fde  test    rax, rax
0x180014fe1  jz      short loc_180014FF4
0x180014fe3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180014fe8  jnz     short loc_180014FF4
0x180014fea  lea     rcx, [rsp+14F0h+var_14D0]
0x180014fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ff4  cmp     [rsp+14F0h+var_14C8], r15d
0x180014ff9  jge     loc_180015106
0x180014fff  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180015006  jnz     short loc_180015027
0x180015008  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001500f  test    rax, rax
0x180015012  jz      short loc_18001501D
0x180015014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015019  test    al, al
0x18001501b  jmp     short loc_180015025
0x18001501d  call    cs:__imp_IsDebuggerPresent
0x180015023  test    eax, eax
0x180015025  jz      short loc_18001502E
0x180015027  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001502c  jz      short loc_180015054
0x18001502e  mov     rax, cs:g_pfnResultLoggingCallback
0x180015035  test    rax, rax
0x180015038  jz      short loc_1800150AD
0x18001503a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180015041  jnz     short loc_1800150AD
0x180015043  xor     r8d, r8d
0x180015046  lea     rcx, [rsp+14F0h+var_14D0]
0x18001504b  xor     edx, edx
0x18001504d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015052  jmp     short loc_1800150AD
0x180015054  mov     rax, cs:g_pfnResultLoggingCallback
0x18001505b  mov     ebx, 800h
0x180015060  test    rax, rax
0x180015063  jz      short loc_180015082
0x180015065  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001506c  jnz     short loc_180015082
0x18001506e  mov     r8d, ebx
0x180015071  lea     rdx, [rbp+13F0h+OutputString]
0x180015078  lea     rcx, [rsp+14F0h+var_14D0]
0x18001507d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015082  cmp     [rbp+13F0h+OutputString], r15w
0x18001508a  jnz     short loc_1800150A0
0x18001508c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180015091  mov     rdx, rbx; unsigned __int16 *
0x180015094  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001509b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800150a0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800150a7  call    cs:__imp_OutputDebugStringW
0x1800150ad  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800150b2  jnz     short loc_1800150BD
0x1800150b4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800150bb  jz      short loc_1800150CE
0x1800150bd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800150c4  test    rax, rax
0x1800150c7  jz      short loc_1800150CE
0x1800150c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150ce  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800150d3  jnz     short loc_1800150FB
0x1800150d5  mov     rcx, [rbp+13F0h+var_30]
0x1800150dc  xor     rcx, rsp; StackCookie
0x1800150df  call    __security_check_cookie
0x1800150e4  mov     rbx, [rsp+14F0h+arg_10]
0x1800150ec  add     rsp, 14D0h
0x1800150f3  pop     r15
0x1800150f5  pop     r14
0x1800150f7  pop     rdi
0x1800150f8  pop     rsi
0x1800150f9  pop     rbp
0x1800150fa  retn
0x1800150fb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180015100  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180015106  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
