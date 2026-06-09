# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180046854`
- end: `0x180046ae8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800465e4`

## callees

- `0x180046854`
- `0x1800472b4`
- `0x1800481e0`
- `0x180048758`
- `0x180048834`
- `0x180076746`
- `0x1800767a0`
- `0x180076830`
- `0x180077010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800469f9`
- `KERNEL32!IsDebuggerPresent` at `0x1800469f9`
- `KERNEL32!OutputDebugStringW` at `0x180046a83`
- `KERNEL32!OutputDebugStringW` at `0x180046a83`
- `KERNEL32!GetCurrentThreadId` at `0x1800468fe`
- `KERNEL32!GetCurrentThreadId` at `0x1800468fe`

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
0x180046854  mov     [rsp-8+arg_10], rbx
0x180046859  push    rbp
0x18004685a  push    rsi
0x18004685b  push    rdi
0x18004685c  push    r14
0x18004685e  push    r15
0x180046860  lea     rbp, [rsp-13D0h]
0x180046868  mov     eax, 14D0h
0x18004686d  call    _alloca_probe
0x180046872  sub     rsp, rax
0x180046875  mov     rax, cs:__security_cookie
0x18004687c  xor     rax, rsp
0x18004687f  mov     [rbp+13F0h+var_30], rax
0x180046886  mov     rdi, [rbp+13F0h+arg_28]
0x18004688d  mov     esi, edx
0x18004688f  mov     r14, rcx
0x180046892  xor     edx, edx; Val
0x180046894  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180046899  mov     r8d, 98h; Size
0x18004689f  call    memset_0
0x1800468a4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800468ab  xor     r15d, r15d
0x1800468ae  mov     [rbp+13F0h+OutputString], r15w
0x1800468b6  mov     [rbp+13F0h+var_1430], r15b
0x1800468ba  mov     ecx, [rdx]; this
0x1800468bc  mov     eax, [rdx+4]
0x1800468bf  mov     [rsp+14F0h+var_14C8], ecx
0x1800468c3  mov     [rsp+14F0h+var_14C4], eax
0x1800468c7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800468cc  cmp     dword ptr [rdx+8], 1
0x1800468d0  mov     ebx, eax
0x1800468d2  lea     eax, [r15+8]
0x1800468d6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800468de  mov     ecx, r15d
0x1800468e1  cmovz   ecx, eax
0x1800468e4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800468e8  lea     ecx, [rax-7]
0x1800468eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800468f3  inc     ecx
0x1800468f5  mov     [rsp+14F0h+var_14B8], r15
0x1800468fa  mov     [rsp+14F0h+var_14C0], ecx
0x1800468fe  call    cs:__imp_GetCurrentThreadId
0x180046904  xorps   xmm0, xmm0
0x180046907  mov     [rsp+14F0h+var_1490], esi
0x18004690b  mov     [rsp+14F0h+var_14B0], eax
0x18004690f  xorps   xmm1, xmm1
0x180046912  lea     rax, aWil; "wil"
0x180046919  mov     [rsp+14F0h+var_148C], ebx
0x18004691d  mov     [rsp+14F0h+var_1498], rax
0x180046922  xor     eax, eax
0x180046924  mov     [rbp+13F0h+var_1458], rax
0x180046928  mov     [rbp+13F0h+var_1470], rax
0x18004692c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180046933  mov     [rsp+14F0h+var_14A8], r15
0x180046938  mov     [rsp+14F0h+var_14A0], r15
0x18004693d  mov     [rbp+13F0h+var_1448], rdi
0x180046941  mov     [rbp+13F0h+var_1440], r14
0x180046945  mov     [rsp+14F0h+var_1488], r15
0x18004694a  movups  [rbp+13F0h+var_1468], xmm0
0x18004694e  movups  [rsp+14F0h+var_1480], xmm1
0x180046953  test    rax, rax
0x180046956  jz      short loc_180046963
0x180046958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004695d  mov     [rbp+13F0h+var_1450], rax
0x180046961  jmp     short loc_180046967
0x180046963  mov     [rbp+13F0h+var_1450], r15
0x180046967  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004696e  test    rax, rax
0x180046971  jz      short loc_18004697D
0x180046973  lea     rcx, [rsp+14F0h+var_14D0]
0x180046978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004697d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180046984  test    rax, rax
0x180046987  jz      short loc_18004699D
0x180046989  mov     r8d, 400h
0x18004698f  lea     rdx, [rbp+13F0h+var_1430]
0x180046993  lea     rcx, [rsp+14F0h+var_14D0]
0x180046998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004699d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800469a4  test    rax, rax
0x1800469a7  jz      short loc_1800469B3
0x1800469a9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800469ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469b3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800469ba  test    rax, rax
0x1800469bd  jz      short loc_1800469D0
0x1800469bf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800469c4  jnz     short loc_1800469D0
0x1800469c6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800469cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469d0  cmp     [rsp+14F0h+var_14C8], r15d
0x1800469d5  jge     loc_180046AD7
0x1800469db  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800469e2  jnz     short loc_180046A03
0x1800469e4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800469eb  test    rax, rax
0x1800469ee  jz      short loc_1800469F9
0x1800469f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469f5  test    al, al
0x1800469f7  jmp     short loc_180046A01
0x1800469f9  call    cs:__imp_IsDebuggerPresent
0x1800469ff  test    eax, eax
0x180046a01  jz      short loc_180046A0A
0x180046a03  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180046a08  jz      short loc_180046A30
0x180046a0a  mov     rax, cs:g_pfnResultLoggingCallback
0x180046a11  test    rax, rax
0x180046a14  jz      short loc_180046A89
0x180046a16  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180046a1d  jnz     short loc_180046A89
0x180046a1f  xor     r8d, r8d
0x180046a22  lea     rcx, [rsp+14F0h+var_14D0]
0x180046a27  xor     edx, edx
0x180046a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a2e  jmp     short loc_180046A89
0x180046a30  mov     rax, cs:g_pfnResultLoggingCallback
0x180046a37  mov     ebx, 800h
0x180046a3c  test    rax, rax
0x180046a3f  jz      short loc_180046A5E
0x180046a41  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180046a48  jnz     short loc_180046A5E
0x180046a4a  mov     r8d, ebx
0x180046a4d  lea     rdx, [rbp+13F0h+OutputString]
0x180046a54  lea     rcx, [rsp+14F0h+var_14D0]
0x180046a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a5e  cmp     [rbp+13F0h+OutputString], r15w
0x180046a66  jnz     short loc_180046A7C
0x180046a68  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180046a6d  mov     rdx, rbx; unsigned __int16 *
0x180046a70  lea     rcx, [rbp+13F0h+OutputString]; this
0x180046a77  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180046a7c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180046a83  call    cs:__imp_OutputDebugStringW
0x180046a89  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180046a8e  jnz     short loc_180046A99
0x180046a90  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180046a97  jz      short loc_180046AAA
0x180046a99  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180046aa0  test    rax, rax
0x180046aa3  jz      short loc_180046AAA
0x180046aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046aaa  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180046aaf  jnz     short loc_180046ADD
0x180046ab1  mov     rcx, [rbp+13F0h+var_30]
0x180046ab8  xor     rcx, rsp; StackCookie
0x180046abb  call    __security_check_cookie
0x180046ac0  mov     rbx, [rsp+14F0h+arg_10]
0x180046ac8  add     rsp, 14D0h
0x180046acf  pop     r15
0x180046ad1  pop     r14
0x180046ad3  pop     rdi
0x180046ad4  pop     rsi
0x180046ad5  pop     rbp
0x180046ad6  retn
0x180046ad7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180046add  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180046ae2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
