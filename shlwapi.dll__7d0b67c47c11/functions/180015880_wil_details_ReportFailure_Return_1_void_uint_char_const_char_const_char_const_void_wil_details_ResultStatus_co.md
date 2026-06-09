# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180015880`
- end: `0x180015b0b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180011188`

## callees

- `0x180012550`
- `0x180013066`
- `0x180015880`
- `0x180016394`
- `0x180016f80`
- `0x180017698`
- `0x1800177c8`
- `0x1800369b9`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001592d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001592d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015a21`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015a21`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015aab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015aab`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180015880  push    rbp
0x180015882  push    rbx
0x180015883  push    rsi
0x180015884  push    rdi
0x180015885  push    r12
0x180015887  push    r14
0x180015889  push    r15
0x18001588b  lea     rbp, [rsp-13D0h]
0x180015893  mov     eax, 14D0h
0x180015898  call    __chkstk_0
0x18001589d  sub     rsp, rax
0x1800158a0  mov     rax, cs:__security_cookie
0x1800158a7  xor     rax, rsp
0x1800158aa  mov     [rbp+1400h+var_40], rax
0x1800158b1  mov     rdi, [rbp+1400h+arg_28]
0x1800158b8  mov     r14, r8
0x1800158bb  mov     esi, edx
0x1800158bd  mov     r15, rcx
0x1800158c0  xor     edx, edx; Val
0x1800158c2  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800158c7  mov     r8d, 98h; Size
0x1800158cd  call    memset_0
0x1800158d2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800158d9  xor     r12d, r12d
0x1800158dc  mov     [rbp+1400h+OutputString], r12w
0x1800158e4  mov     [rbp+1400h+var_1440], r12b
0x1800158e8  mov     ecx, [rdx]; this
0x1800158ea  mov     eax, [rdx+4]
0x1800158ed  mov     [rsp+1500h+var_14D8], ecx
0x1800158f1  mov     [rsp+1500h+var_14D4], eax
0x1800158f5  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800158fa  cmp     dword ptr [rdx+8], 1
0x1800158fe  mov     ebx, eax
0x180015900  lea     eax, [r12+8]
0x180015905  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18001590d  mov     ecx, r12d
0x180015910  cmovz   ecx, eax
0x180015913  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180015917  lea     ecx, [rax-7]
0x18001591a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015922  inc     ecx
0x180015924  mov     [rsp+1500h+var_14C8], r12
0x180015929  mov     [rsp+1500h+var_14D0], ecx
0x18001592d  call    cs:__imp_GetCurrentThreadId
0x180015933  xorps   xmm0, xmm0
0x180015936  mov     [rsp+1500h+var_14A8], r14
0x18001593b  mov     [rsp+1500h+var_14C0], eax
0x18001593f  xorps   xmm1, xmm1
0x180015942  xor     eax, eax
0x180015944  mov     [rsp+1500h+var_14A0], esi
0x180015948  mov     [rbp+1400h+var_1468], rax
0x18001594c  mov     [rbp+1400h+var_1480], rax
0x180015950  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180015957  mov     [rsp+1500h+var_149C], ebx
0x18001595b  mov     [rsp+1500h+var_14B8], r12
0x180015960  mov     [rsp+1500h+var_14B0], r12
0x180015965  mov     [rbp+1400h+var_1458], rdi
0x180015969  mov     [rbp+1400h+var_1450], r15
0x18001596d  mov     [rsp+1500h+var_1498], r12
0x180015972  movups  [rbp+1400h+var_1478], xmm0
0x180015976  movups  [rsp+1500h+var_1490], xmm1
0x18001597b  test    rax, rax
0x18001597e  jz      short loc_18001598B
0x180015980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015985  mov     [rbp+1400h+var_1460], rax
0x180015989  jmp     short loc_18001598F
0x18001598b  mov     [rbp+1400h+var_1460], r12
0x18001598f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015996  test    rax, rax
0x180015999  jz      short loc_1800159A5
0x18001599b  lea     rcx, [rsp+1500h+var_14E0]
0x1800159a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800159ac  test    rax, rax
0x1800159af  jz      short loc_1800159C5
0x1800159b1  mov     r8d, 400h
0x1800159b7  lea     rdx, [rbp+1400h+var_1440]
0x1800159bb  lea     rcx, [rsp+1500h+var_14E0]
0x1800159c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159c5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800159cc  test    rax, rax
0x1800159cf  jz      short loc_1800159DB
0x1800159d1  lea     rcx, [rsp+1500h+var_14E0]
0x1800159d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800159e2  test    rax, rax
0x1800159e5  jz      short loc_1800159F8
0x1800159e7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800159ec  jnz     short loc_1800159F8
0x1800159ee  lea     rcx, [rsp+1500h+var_14E0]
0x1800159f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159f8  cmp     [rsp+1500h+var_14D8], r12d
0x1800159fd  jge     loc_180015AFA
0x180015a03  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180015a0a  jnz     short loc_180015A2B
0x180015a0c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015a13  test    rax, rax
0x180015a16  jz      short loc_180015A21
0x180015a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a1d  test    al, al
0x180015a1f  jmp     short loc_180015A29
0x180015a21  call    cs:__imp_IsDebuggerPresent
0x180015a27  test    eax, eax
0x180015a29  jz      short loc_180015A32
0x180015a2b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180015a30  jz      short loc_180015A58
0x180015a32  mov     rax, cs:g_pfnResultLoggingCallback
0x180015a39  test    rax, rax
0x180015a3c  jz      short loc_180015AB1
0x180015a3e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180015a45  jnz     short loc_180015AB1
0x180015a47  xor     r8d, r8d
0x180015a4a  lea     rcx, [rsp+1500h+var_14E0]
0x180015a4f  xor     edx, edx
0x180015a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a56  jmp     short loc_180015AB1
0x180015a58  mov     rax, cs:g_pfnResultLoggingCallback
0x180015a5f  mov     ebx, 800h
0x180015a64  test    rax, rax
0x180015a67  jz      short loc_180015A86
0x180015a69  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180015a70  jnz     short loc_180015A86
0x180015a72  mov     r8d, ebx
0x180015a75  lea     rdx, [rbp+1400h+OutputString]
0x180015a7c  lea     rcx, [rsp+1500h+var_14E0]
0x180015a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a86  cmp     [rbp+1400h+OutputString], r12w
0x180015a8e  jnz     short loc_180015AA4
0x180015a90  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180015a95  mov     rdx, rbx; unsigned __int16 *
0x180015a98  lea     rcx, [rbp+1400h+OutputString]; this
0x180015a9f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180015aa4  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180015aab  call    cs:__imp_OutputDebugStringW
0x180015ab1  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180015ab6  jnz     short loc_180015AC1
0x180015ab8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180015abf  jz      short loc_180015AD2
0x180015ac1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015ac8  test    rax, rax
0x180015acb  jz      short loc_180015AD2
0x180015acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ad2  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180015ad7  jnz     short loc_180015B00
0x180015ad9  mov     rcx, [rbp+1400h+var_40]
0x180015ae0  xor     rcx, rsp; StackCookie
0x180015ae3  call    __security_check_cookie
0x180015ae8  add     rsp, 14D0h
0x180015aef  pop     r15
0x180015af1  pop     r14
0x180015af3  pop     r12
0x180015af5  pop     rdi
0x180015af6  pop     rsi
0x180015af7  pop     rbx
0x180015af8  pop     rbp
0x180015af9  retn
0x180015afa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180015b00  lea     rcx, [rsp+1500h+var_14E0]; this
0x180015b05  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
