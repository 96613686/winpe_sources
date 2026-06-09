# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002dc0`
- end: `0x180003067`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002884`

## callees

- `0x180002dc0`
- `0x1800062d4`
- `0x180008b9c`
- `0x18000b62c`
- `0x18000b818`
- `0x18000d6d2`
- `0x18000d700`
- `0x18000d7c0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180002f6b`
- `KERNEL32!IsDebuggerPresent` at `0x180002f6b`
- `KERNEL32!GetCurrentThreadId` at `0x180002e6a`
- `KERNEL32!GetCurrentThreadId` at `0x180002e6a`
- `KERNEL32!OutputDebugStringW` at `0x180002ffb`
- `KERNEL32!OutputDebugStringW` at `0x180002ffb`

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
0x180002dc0  mov     [rsp-8+arg_10], rbx
0x180002dc5  push    rbp
0x180002dc6  push    rsi
0x180002dc7  push    rdi
0x180002dc8  push    r14
0x180002dca  push    r15
0x180002dcc  lea     rbp, [rsp-13D0h]
0x180002dd4  mov     eax, 14D0h
0x180002dd9  call    _alloca_probe
0x180002dde  sub     rsp, rax
0x180002de1  mov     rax, cs:__security_cookie
0x180002de8  xor     rax, rsp
0x180002deb  mov     [rbp+13F0h+var_30], rax
0x180002df2  mov     rdi, [rbp+13F0h+arg_28]
0x180002df9  mov     esi, edx
0x180002dfb  mov     r14, rcx
0x180002dfe  xor     edx, edx; Val
0x180002e00  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002e05  mov     r8d, 98h; Size
0x180002e0b  call    memset_0
0x180002e10  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002e17  xor     r15d, r15d
0x180002e1a  mov     [rbp+13F0h+OutputString], r15w
0x180002e22  mov     [rbp+13F0h+var_1430], r15b
0x180002e26  mov     ecx, [rdx]; this
0x180002e28  mov     eax, [rdx+4]
0x180002e2b  mov     [rsp+14F0h+var_14C8], ecx
0x180002e2f  mov     [rsp+14F0h+var_14C4], eax
0x180002e33  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002e38  cmp     dword ptr [rdx+8], 1
0x180002e3c  mov     ebx, eax
0x180002e3e  lea     eax, [r15+8]
0x180002e42  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002e4a  mov     ecx, r15d
0x180002e4d  cmovz   ecx, eax
0x180002e50  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002e54  lea     ecx, [rax-7]
0x180002e57  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180002e5f  inc     ecx
0x180002e61  mov     [rsp+14F0h+var_14B8], r15
0x180002e66  mov     [rsp+14F0h+var_14C0], ecx
0x180002e6a  call    cs:__imp_GetCurrentThreadId
0x180002e71  nop     dword ptr [rax+rax+00h]
0x180002e76  xorps   xmm0, xmm0
0x180002e79  mov     [rsp+14F0h+var_1490], esi
0x180002e7d  mov     [rsp+14F0h+var_14B0], eax
0x180002e81  xorps   xmm1, xmm1
0x180002e84  lea     rax, aWil; "wil"
0x180002e8b  mov     [rsp+14F0h+var_148C], ebx
0x180002e8f  mov     [rsp+14F0h+var_1498], rax
0x180002e94  xor     eax, eax
0x180002e96  mov     [rbp+13F0h+var_1458], rax
0x180002e9a  mov     [rbp+13F0h+var_1470], rax
0x180002e9e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002ea5  mov     [rsp+14F0h+var_14A8], r15
0x180002eaa  mov     [rsp+14F0h+var_14A0], r15
0x180002eaf  mov     [rbp+13F0h+var_1448], rdi
0x180002eb3  mov     [rbp+13F0h+var_1440], r14
0x180002eb7  mov     [rsp+14F0h+var_1488], r15
0x180002ebc  movups  [rbp+13F0h+var_1468], xmm0
0x180002ec0  movups  [rsp+14F0h+var_1480], xmm1
0x180002ec5  test    rax, rax
0x180002ec8  jz      short loc_180002ED5
0x180002eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ecf  mov     [rbp+13F0h+var_1450], rax
0x180002ed3  jmp     short loc_180002ED9
0x180002ed5  mov     [rbp+13F0h+var_1450], r15
0x180002ed9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002ee0  test    rax, rax
0x180002ee3  jz      short loc_180002EEF
0x180002ee5  lea     rcx, [rsp+14F0h+var_14D0]
0x180002eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eef  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002ef6  test    rax, rax
0x180002ef9  jz      short loc_180002F0F
0x180002efb  mov     r8d, 400h
0x180002f01  lea     rdx, [rbp+13F0h+var_1430]
0x180002f05  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f0f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002f16  test    rax, rax
0x180002f19  jz      short loc_180002F25
0x180002f1b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f25  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002f2c  test    rax, rax
0x180002f2f  jz      short loc_180002F42
0x180002f31  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002f36  jnz     short loc_180002F42
0x180002f38  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f42  cmp     [rsp+14F0h+var_14C8], r15d
0x180002f47  jge     loc_180003056
0x180002f4d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002f54  jnz     short loc_180002F7B
0x180002f56  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002f5d  test    rax, rax
0x180002f60  jz      short loc_180002F6B
0x180002f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f67  test    al, al
0x180002f69  jmp     short loc_180002F79
0x180002f6b  call    cs:__imp_IsDebuggerPresent
0x180002f72  nop     dword ptr [rax+rax+00h]
0x180002f77  test    eax, eax
0x180002f79  jz      short loc_180002F82
0x180002f7b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002f80  jz      short loc_180002FA8
0x180002f82  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f89  test    rax, rax
0x180002f8c  jz      short loc_180003007
0x180002f8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002f95  jnz     short loc_180003007
0x180002f97  xor     r8d, r8d
0x180002f9a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f9f  xor     edx, edx
0x180002fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa6  jmp     short loc_180003007
0x180002fa8  mov     rax, cs:g_pfnResultLoggingCallback
0x180002faf  mov     ebx, 800h
0x180002fb4  test    rax, rax
0x180002fb7  jz      short loc_180002FD6
0x180002fb9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002fc0  jnz     short loc_180002FD6
0x180002fc2  mov     r8d, ebx
0x180002fc5  lea     rdx, [rbp+13F0h+OutputString]
0x180002fcc  lea     rcx, [rsp+14F0h+var_14D0]
0x180002fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd6  cmp     [rbp+13F0h+OutputString], r15w
0x180002fde  jnz     short loc_180002FF4
0x180002fe0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002fe5  mov     rdx, rbx; unsigned __int16 *
0x180002fe8  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002fef  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002ff4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002ffb  call    cs:__imp_OutputDebugStringW
0x180003002  nop     dword ptr [rax+rax+00h]
0x180003007  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000300c  jnz     short loc_180003017
0x18000300e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003015  jz      short loc_180003028
0x180003017  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000301e  test    rax, rax
0x180003021  jz      short loc_180003028
0x180003023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003028  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000302d  jnz     short loc_18000305C
0x18000302f  mov     rcx, [rbp+13F0h+var_30]
0x180003036  xor     rcx, rsp; StackCookie
0x180003039  call    __security_check_cookie
0x18000303e  mov     rbx, [rsp+14F0h+arg_10]
0x180003046  add     rsp, 14D0h
0x18000304d  pop     r15
0x18000304f  pop     r14
0x180003051  pop     rdi
0x180003052  pop     rsi
0x180003053  pop     rbp
0x180003054  retn
0x180003056  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000305c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003061  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
