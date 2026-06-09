# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18002fd04`
- end: `0x18002ff98`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002f80c`

## callees

- `0x18002fd04`
- `0x1800311f4`
- `0x180032a70`
- `0x180033e40`
- `0x180033ffc`
- `0x180035b9a`
- `0x180035bd0`
- `0x180035c60`
- `0x180037010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18002fea9`
- `KERNEL32!IsDebuggerPresent` at `0x18002fea9`
- `KERNEL32!OutputDebugStringW` at `0x18002ff33`
- `KERNEL32!OutputDebugStringW` at `0x18002ff33`
- `KERNEL32!GetCurrentThreadId` at `0x18002fdae`
- `KERNEL32!GetCurrentThreadId` at `0x18002fdae`

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
0x18002fd04  mov     [rsp-8+arg_10], rbx
0x18002fd09  push    rbp
0x18002fd0a  push    rsi
0x18002fd0b  push    rdi
0x18002fd0c  push    r14
0x18002fd0e  push    r15
0x18002fd10  lea     rbp, [rsp-13D0h]
0x18002fd18  mov     eax, 14D0h
0x18002fd1d  call    _alloca_probe
0x18002fd22  sub     rsp, rax
0x18002fd25  mov     rax, cs:__security_cookie
0x18002fd2c  xor     rax, rsp
0x18002fd2f  mov     [rbp+13F0h+var_30], rax
0x18002fd36  mov     rdi, [rbp+13F0h+arg_28]
0x18002fd3d  mov     esi, edx
0x18002fd3f  mov     r14, rcx
0x18002fd42  xor     edx, edx; Val
0x18002fd44  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002fd49  mov     r8d, 98h; Size
0x18002fd4f  call    memset_0
0x18002fd54  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18002fd5b  xor     r15d, r15d
0x18002fd5e  mov     [rbp+13F0h+OutputString], r15w
0x18002fd66  mov     [rbp+13F0h+var_1430], r15b
0x18002fd6a  mov     ecx, [rdx]; this
0x18002fd6c  mov     eax, [rdx+4]
0x18002fd6f  mov     [rsp+14F0h+var_14C8], ecx
0x18002fd73  mov     [rsp+14F0h+var_14C4], eax
0x18002fd77  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002fd7c  cmp     dword ptr [rdx+8], 1
0x18002fd80  mov     ebx, eax
0x18002fd82  lea     eax, [r15+8]
0x18002fd86  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18002fd8e  mov     ecx, r15d
0x18002fd91  cmovz   ecx, eax
0x18002fd94  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002fd98  lea     ecx, [rax-7]
0x18002fd9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002fda3  inc     ecx
0x18002fda5  mov     [rsp+14F0h+var_14B8], r15
0x18002fdaa  mov     [rsp+14F0h+var_14C0], ecx
0x18002fdae  call    cs:__imp_GetCurrentThreadId
0x18002fdb4  xorps   xmm0, xmm0
0x18002fdb7  mov     [rsp+14F0h+var_1490], esi
0x18002fdbb  mov     [rsp+14F0h+var_14B0], eax
0x18002fdbf  xorps   xmm1, xmm1
0x18002fdc2  lea     rax, aWil; "wil"
0x18002fdc9  mov     [rsp+14F0h+var_148C], ebx
0x18002fdcd  mov     [rsp+14F0h+var_1498], rax
0x18002fdd2  xor     eax, eax
0x18002fdd4  mov     [rbp+13F0h+var_1458], rax
0x18002fdd8  mov     [rbp+13F0h+var_1470], rax
0x18002fddc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002fde3  mov     [rsp+14F0h+var_14A8], r15
0x18002fde8  mov     [rsp+14F0h+var_14A0], r15
0x18002fded  mov     [rbp+13F0h+var_1448], rdi
0x18002fdf1  mov     [rbp+13F0h+var_1440], r14
0x18002fdf5  mov     [rsp+14F0h+var_1488], r15
0x18002fdfa  movups  [rbp+13F0h+var_1468], xmm0
0x18002fdfe  movups  [rsp+14F0h+var_1480], xmm1
0x18002fe03  test    rax, rax
0x18002fe06  jz      short loc_18002FE13
0x18002fe08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe0d  mov     [rbp+13F0h+var_1450], rax
0x18002fe11  jmp     short loc_18002FE17
0x18002fe13  mov     [rbp+13F0h+var_1450], r15
0x18002fe17  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002fe1e  test    rax, rax
0x18002fe21  jz      short loc_18002FE2D
0x18002fe23  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fe28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe2d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002fe34  test    rax, rax
0x18002fe37  jz      short loc_18002FE4D
0x18002fe39  mov     r8d, 400h
0x18002fe3f  lea     rdx, [rbp+13F0h+var_1430]
0x18002fe43  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fe48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe4d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002fe54  test    rax, rax
0x18002fe57  jz      short loc_18002FE63
0x18002fe59  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fe5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe63  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002fe6a  test    rax, rax
0x18002fe6d  jz      short loc_18002FE80
0x18002fe6f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002fe74  jnz     short loc_18002FE80
0x18002fe76  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fe7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe80  cmp     [rsp+14F0h+var_14C8], r15d
0x18002fe85  jge     loc_18002FF87
0x18002fe8b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18002fe92  jnz     short loc_18002FEB3
0x18002fe94  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002fe9b  test    rax, rax
0x18002fe9e  jz      short loc_18002FEA9
0x18002fea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fea5  test    al, al
0x18002fea7  jmp     short loc_18002FEB1
0x18002fea9  call    cs:__imp_IsDebuggerPresent
0x18002feaf  test    eax, eax
0x18002feb1  jz      short loc_18002FEBA
0x18002feb3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002feb8  jz      short loc_18002FEE0
0x18002feba  mov     rax, cs:g_pfnResultLoggingCallback
0x18002fec1  test    rax, rax
0x18002fec4  jz      short loc_18002FF39
0x18002fec6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002fecd  jnz     short loc_18002FF39
0x18002fecf  xor     r8d, r8d
0x18002fed2  lea     rcx, [rsp+14F0h+var_14D0]
0x18002fed7  xor     edx, edx
0x18002fed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fede  jmp     short loc_18002FF39
0x18002fee0  mov     rax, cs:g_pfnResultLoggingCallback
0x18002fee7  mov     ebx, 800h
0x18002feec  test    rax, rax
0x18002feef  jz      short loc_18002FF0E
0x18002fef1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002fef8  jnz     short loc_18002FF0E
0x18002fefa  mov     r8d, ebx
0x18002fefd  lea     rdx, [rbp+13F0h+OutputString]
0x18002ff04  lea     rcx, [rsp+14F0h+var_14D0]
0x18002ff09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff0e  cmp     [rbp+13F0h+OutputString], r15w
0x18002ff16  jnz     short loc_18002FF2C
0x18002ff18  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002ff1d  mov     rdx, rbx; unsigned __int16 *
0x18002ff20  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002ff27  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002ff2c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002ff33  call    cs:__imp_OutputDebugStringW
0x18002ff39  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002ff3e  jnz     short loc_18002FF49
0x18002ff40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18002ff47  jz      short loc_18002FF5A
0x18002ff49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002ff50  test    rax, rax
0x18002ff53  jz      short loc_18002FF5A
0x18002ff55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff5a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002ff5f  jnz     short loc_18002FF8D
0x18002ff61  mov     rcx, [rbp+13F0h+var_30]
0x18002ff68  xor     rcx, rsp; StackCookie
0x18002ff6b  call    __security_check_cookie
0x18002ff70  mov     rbx, [rsp+14F0h+arg_10]
0x18002ff78  add     rsp, 14D0h
0x18002ff7f  pop     r15
0x18002ff81  pop     r14
0x18002ff83  pop     rdi
0x18002ff84  pop     rsi
0x18002ff85  pop     rbp
0x18002ff86  retn
0x18002ff87  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002ff8d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002ff92  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
