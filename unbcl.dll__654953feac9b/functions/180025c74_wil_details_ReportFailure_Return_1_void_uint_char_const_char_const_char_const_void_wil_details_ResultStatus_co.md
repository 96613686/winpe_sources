# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180025c74`
- end: `0x180025f08`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002575c`

## callees

- `0x180025c74`
- `0x18002c960`
- `0x18002f4d0`
- `0x180030d80`
- `0x180030f64`
- `0x180068fe6`
- `0x180069020`
- `0x1800690e0`
- `0x18006f010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180025e19`
- `KERNEL32!IsDebuggerPresent` at `0x180025e19`
- `KERNEL32!OutputDebugStringW` at `0x180025ea3`
- `KERNEL32!OutputDebugStringW` at `0x180025ea3`
- `KERNEL32!GetCurrentThreadId` at `0x180025d1e`
- `KERNEL32!GetCurrentThreadId` at `0x180025d1e`

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
0x180025c74  mov     [rsp-8+arg_10], rbx
0x180025c79  push    rbp
0x180025c7a  push    rsi
0x180025c7b  push    rdi
0x180025c7c  push    r14
0x180025c7e  push    r15
0x180025c80  lea     rbp, [rsp-13D0h]
0x180025c88  mov     eax, 14D0h
0x180025c8d  call    _alloca_probe
0x180025c92  sub     rsp, rax
0x180025c95  mov     rax, cs:__security_cookie
0x180025c9c  xor     rax, rsp
0x180025c9f  mov     [rbp+13F0h+var_30], rax
0x180025ca6  mov     rdi, [rbp+13F0h+arg_28]
0x180025cad  mov     esi, edx
0x180025caf  mov     r14, rcx
0x180025cb2  xor     edx, edx; Val
0x180025cb4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180025cb9  mov     r8d, 98h; Size
0x180025cbf  call    memset_0
0x180025cc4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180025ccb  xor     r15d, r15d
0x180025cce  mov     [rbp+13F0h+OutputString], r15w
0x180025cd6  mov     [rbp+13F0h+var_1430], r15b
0x180025cda  mov     ecx, [rdx]; this
0x180025cdc  mov     eax, [rdx+4]
0x180025cdf  mov     [rsp+14F0h+var_14C8], ecx
0x180025ce3  mov     [rsp+14F0h+var_14C4], eax
0x180025ce7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025cec  cmp     dword ptr [rdx+8], 1
0x180025cf0  mov     ebx, eax
0x180025cf2  lea     eax, [r15+8]
0x180025cf6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180025cfe  mov     ecx, r15d
0x180025d01  cmovz   ecx, eax
0x180025d04  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180025d08  lea     ecx, [rax-7]
0x180025d0b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180025d13  inc     ecx
0x180025d15  mov     [rsp+14F0h+var_14B8], r15
0x180025d1a  mov     [rsp+14F0h+var_14C0], ecx
0x180025d1e  call    cs:__imp_GetCurrentThreadId
0x180025d24  xorps   xmm0, xmm0
0x180025d27  mov     [rsp+14F0h+var_1490], esi
0x180025d2b  mov     [rsp+14F0h+var_14B0], eax
0x180025d2f  xorps   xmm1, xmm1
0x180025d32  lea     rax, aWil; "wil"
0x180025d39  mov     [rsp+14F0h+var_148C], ebx
0x180025d3d  mov     [rsp+14F0h+var_1498], rax
0x180025d42  xor     eax, eax
0x180025d44  mov     [rbp+13F0h+var_1458], rax
0x180025d48  mov     [rbp+13F0h+var_1470], rax
0x180025d4c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025d53  mov     [rsp+14F0h+var_14A8], r15
0x180025d58  mov     [rsp+14F0h+var_14A0], r15
0x180025d5d  mov     [rbp+13F0h+var_1448], rdi
0x180025d61  mov     [rbp+13F0h+var_1440], r14
0x180025d65  mov     [rsp+14F0h+var_1488], r15
0x180025d6a  movups  [rbp+13F0h+var_1468], xmm0
0x180025d6e  movups  [rsp+14F0h+var_1480], xmm1
0x180025d73  test    rax, rax
0x180025d76  jz      short loc_180025D83
0x180025d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d7d  mov     [rbp+13F0h+var_1450], rax
0x180025d81  jmp     short loc_180025D87
0x180025d83  mov     [rbp+13F0h+var_1450], r15
0x180025d87  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025d8e  test    rax, rax
0x180025d91  jz      short loc_180025D9D
0x180025d93  lea     rcx, [rsp+14F0h+var_14D0]
0x180025d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d9d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025da4  test    rax, rax
0x180025da7  jz      short loc_180025DBD
0x180025da9  mov     r8d, 400h
0x180025daf  lea     rdx, [rbp+13F0h+var_1430]
0x180025db3  lea     rcx, [rsp+14F0h+var_14D0]
0x180025db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dbd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025dc4  test    rax, rax
0x180025dc7  jz      short loc_180025DD3
0x180025dc9  lea     rcx, [rsp+14F0h+var_14D0]
0x180025dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dd3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025dda  test    rax, rax
0x180025ddd  jz      short loc_180025DF0
0x180025ddf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180025de4  jnz     short loc_180025DF0
0x180025de6  lea     rcx, [rsp+14F0h+var_14D0]
0x180025deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025df0  cmp     [rsp+14F0h+var_14C8], r15d
0x180025df5  jge     loc_180025EF7
0x180025dfb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180025e02  jnz     short loc_180025E23
0x180025e04  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180025e0b  test    rax, rax
0x180025e0e  jz      short loc_180025E19
0x180025e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e15  test    al, al
0x180025e17  jmp     short loc_180025E21
0x180025e19  call    cs:__imp_IsDebuggerPresent
0x180025e1f  test    eax, eax
0x180025e21  jz      short loc_180025E2A
0x180025e23  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180025e28  jz      short loc_180025E50
0x180025e2a  mov     rax, cs:g_pfnResultLoggingCallback
0x180025e31  test    rax, rax
0x180025e34  jz      short loc_180025EA9
0x180025e36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180025e3d  jnz     short loc_180025EA9
0x180025e3f  xor     r8d, r8d
0x180025e42  lea     rcx, [rsp+14F0h+var_14D0]
0x180025e47  xor     edx, edx
0x180025e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e4e  jmp     short loc_180025EA9
0x180025e50  mov     rax, cs:g_pfnResultLoggingCallback
0x180025e57  mov     ebx, 800h
0x180025e5c  test    rax, rax
0x180025e5f  jz      short loc_180025E7E
0x180025e61  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180025e68  jnz     short loc_180025E7E
0x180025e6a  mov     r8d, ebx
0x180025e6d  lea     rdx, [rbp+13F0h+OutputString]
0x180025e74  lea     rcx, [rsp+14F0h+var_14D0]
0x180025e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e7e  cmp     [rbp+13F0h+OutputString], r15w
0x180025e86  jnz     short loc_180025E9C
0x180025e88  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180025e8d  mov     rdx, rbx; unsigned __int16 *
0x180025e90  lea     rcx, [rbp+13F0h+OutputString]; this
0x180025e97  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025e9c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180025ea3  call    cs:__imp_OutputDebugStringW
0x180025ea9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180025eae  jnz     short loc_180025EB9
0x180025eb0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180025eb7  jz      short loc_180025ECA
0x180025eb9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025ec0  test    rax, rax
0x180025ec3  jz      short loc_180025ECA
0x180025ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eca  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180025ecf  jnz     short loc_180025EFD
0x180025ed1  mov     rcx, [rbp+13F0h+var_30]
0x180025ed8  xor     rcx, rsp; StackCookie
0x180025edb  call    __security_check_cookie
0x180025ee0  mov     rbx, [rsp+14F0h+arg_10]
0x180025ee8  add     rsp, 14D0h
0x180025eef  pop     r15
0x180025ef1  pop     r14
0x180025ef3  pop     rdi
0x180025ef4  pop     rsi
0x180025ef5  pop     rbp
0x180025ef6  retn
0x180025ef7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180025efd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180025f02  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
