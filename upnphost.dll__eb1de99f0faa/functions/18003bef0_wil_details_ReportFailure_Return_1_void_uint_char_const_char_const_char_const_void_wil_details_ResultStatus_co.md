# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18003bef0`
- end: `0x18003c184`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180039e2c`

## callees

- `0x18003a560`
- `0x18003ae80`
- `0x18003bef0`
- `0x18003f374`
- `0x180041278`
- `0x180044188`
- `0x180044340`
- `0x1800542a0`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bf9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bf9a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c095`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c095`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c11f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c11f`

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
0x18003bef0  mov     [rsp-8+arg_10], rbx
0x18003bef5  push    rbp
0x18003bef6  push    rsi
0x18003bef7  push    rdi
0x18003bef8  push    r14
0x18003befa  push    r15
0x18003befc  lea     rbp, [rsp-13D0h]
0x18003bf04  mov     eax, 14D0h
0x18003bf09  call    _alloca_probe
0x18003bf0e  sub     rsp, rax
0x18003bf11  mov     rax, cs:__security_cookie
0x18003bf18  xor     rax, rsp
0x18003bf1b  mov     [rbp+13F0h+var_30], rax
0x18003bf22  mov     rdi, [rbp+13F0h+arg_28]
0x18003bf29  mov     esi, edx
0x18003bf2b  mov     r14, rcx
0x18003bf2e  xor     edx, edx; Val
0x18003bf30  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18003bf35  mov     r8d, 98h; Size
0x18003bf3b  call    memset_0
0x18003bf40  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18003bf47  xor     r15d, r15d
0x18003bf4a  mov     [rbp+13F0h+OutputString], r15w
0x18003bf52  mov     [rbp+13F0h+var_1430], r15b
0x18003bf56  mov     ecx, [rdx]; this
0x18003bf58  mov     eax, [rdx+4]
0x18003bf5b  mov     [rsp+14F0h+var_14C8], ecx
0x18003bf5f  mov     [rsp+14F0h+var_14C4], eax
0x18003bf63  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003bf68  cmp     dword ptr [rdx+8], 1
0x18003bf6c  mov     ebx, eax
0x18003bf6e  lea     eax, [r15+8]
0x18003bf72  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18003bf7a  mov     ecx, r15d
0x18003bf7d  cmovz   ecx, eax
0x18003bf80  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18003bf84  lea     ecx, [rax-7]
0x18003bf87  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003bf8f  inc     ecx
0x18003bf91  mov     [rsp+14F0h+var_14B8], r15
0x18003bf96  mov     [rsp+14F0h+var_14C0], ecx
0x18003bf9a  call    cs:__imp_GetCurrentThreadId
0x18003bfa0  xorps   xmm0, xmm0
0x18003bfa3  mov     [rsp+14F0h+var_1490], esi
0x18003bfa7  mov     [rsp+14F0h+var_14B0], eax
0x18003bfab  xorps   xmm1, xmm1
0x18003bfae  lea     rax, aWil; "wil"
0x18003bfb5  mov     [rsp+14F0h+var_148C], ebx
0x18003bfb9  mov     [rsp+14F0h+var_1498], rax
0x18003bfbe  xor     eax, eax
0x18003bfc0  mov     [rbp+13F0h+var_1458], rax
0x18003bfc4  mov     [rbp+13F0h+var_1470], rax
0x18003bfc8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003bfcf  mov     [rsp+14F0h+var_14A8], r15
0x18003bfd4  mov     [rsp+14F0h+var_14A0], r15
0x18003bfd9  mov     [rbp+13F0h+var_1448], rdi
0x18003bfdd  mov     [rbp+13F0h+var_1440], r14
0x18003bfe1  mov     [rsp+14F0h+var_1488], r15
0x18003bfe6  movups  [rbp+13F0h+var_1468], xmm0
0x18003bfea  movups  [rsp+14F0h+var_1480], xmm1
0x18003bfef  test    rax, rax
0x18003bff2  jz      short loc_18003BFFF
0x18003bff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bff9  mov     [rbp+13F0h+var_1450], rax
0x18003bffd  jmp     short loc_18003C003
0x18003bfff  mov     [rbp+13F0h+var_1450], r15
0x18003c003  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003c00a  test    rax, rax
0x18003c00d  jz      short loc_18003C019
0x18003c00f  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c019  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003c020  test    rax, rax
0x18003c023  jz      short loc_18003C039
0x18003c025  mov     r8d, 400h
0x18003c02b  lea     rdx, [rbp+13F0h+var_1430]
0x18003c02f  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c039  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c040  test    rax, rax
0x18003c043  jz      short loc_18003C04F
0x18003c045  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c04f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c056  test    rax, rax
0x18003c059  jz      short loc_18003C06C
0x18003c05b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003c060  jnz     short loc_18003C06C
0x18003c062  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c06c  cmp     [rsp+14F0h+var_14C8], r15d
0x18003c071  jge     loc_18003C173
0x18003c077  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18003c07e  jnz     short loc_18003C09F
0x18003c080  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003c087  test    rax, rax
0x18003c08a  jz      short loc_18003C095
0x18003c08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c091  test    al, al
0x18003c093  jmp     short loc_18003C09D
0x18003c095  call    cs:__imp_IsDebuggerPresent
0x18003c09b  test    eax, eax
0x18003c09d  jz      short loc_18003C0A6
0x18003c09f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003c0a4  jz      short loc_18003C0CC
0x18003c0a6  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c0ad  test    rax, rax
0x18003c0b0  jz      short loc_18003C125
0x18003c0b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c0b9  jnz     short loc_18003C125
0x18003c0bb  xor     r8d, r8d
0x18003c0be  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c0c3  xor     edx, edx
0x18003c0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0ca  jmp     short loc_18003C125
0x18003c0cc  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c0d3  mov     ebx, 800h
0x18003c0d8  test    rax, rax
0x18003c0db  jz      short loc_18003C0FA
0x18003c0dd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c0e4  jnz     short loc_18003C0FA
0x18003c0e6  mov     r8d, ebx
0x18003c0e9  lea     rdx, [rbp+13F0h+OutputString]
0x18003c0f0  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0fa  cmp     [rbp+13F0h+OutputString], r15w
0x18003c102  jnz     short loc_18003C118
0x18003c104  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18003c109  mov     rdx, rbx; unsigned __int16 *
0x18003c10c  lea     rcx, [rbp+13F0h+OutputString]; this
0x18003c113  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003c118  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18003c11f  call    cs:__imp_OutputDebugStringW
0x18003c125  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18003c12a  jnz     short loc_18003C135
0x18003c12c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18003c133  jz      short loc_18003C146
0x18003c135  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003c13c  test    rax, rax
0x18003c13f  jz      short loc_18003C146
0x18003c141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c146  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18003c14b  jnz     short loc_18003C179
0x18003c14d  mov     rcx, [rbp+13F0h+var_30]
0x18003c154  xor     rcx, rsp; StackCookie
0x18003c157  call    __security_check_cookie
0x18003c15c  mov     rbx, [rsp+14F0h+arg_10]
0x18003c164  add     rsp, 14D0h
0x18003c16b  pop     r15
0x18003c16d  pop     r14
0x18003c16f  pop     rdi
0x18003c170  pop     rsi
0x18003c171  pop     rbp
0x18003c172  retn
0x18003c173  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003c179  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18003c17e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
