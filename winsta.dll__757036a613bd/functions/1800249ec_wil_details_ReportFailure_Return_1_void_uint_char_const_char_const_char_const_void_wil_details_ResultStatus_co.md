# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800249ec`
- end: `0x180024c77`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180024788`

## callees

- `0x1800249ec`
- `0x180026314`
- `0x180026f10`
- `0x180027788`
- `0x180027864`
- `0x18002fe06`
- `0x18002fe40`
- `0x18002ff00`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024a99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024a99`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024c17`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024c17`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024b8d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024b8d`

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
0x1800249ec  push    rbp
0x1800249ee  push    rbx
0x1800249ef  push    rsi
0x1800249f0  push    rdi
0x1800249f1  push    r12
0x1800249f3  push    r14
0x1800249f5  push    r15
0x1800249f7  lea     rbp, [rsp-13D0h]
0x1800249ff  mov     eax, 14D0h
0x180024a04  call    _alloca_probe
0x180024a09  sub     rsp, rax
0x180024a0c  mov     rax, cs:__security_cookie
0x180024a13  xor     rax, rsp
0x180024a16  mov     [rbp+1400h+var_40], rax
0x180024a1d  mov     rdi, [rbp+1400h+arg_28]
0x180024a24  mov     r14, r8
0x180024a27  mov     esi, edx
0x180024a29  mov     r15, rcx
0x180024a2c  xor     edx, edx; Val
0x180024a2e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180024a33  mov     r8d, 98h; Size
0x180024a39  call    memset_0
0x180024a3e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180024a45  xor     r12d, r12d
0x180024a48  mov     [rbp+1400h+OutputString], r12w
0x180024a50  mov     [rbp+1400h+var_1440], r12b
0x180024a54  mov     ecx, [rdx]; this
0x180024a56  mov     eax, [rdx+4]
0x180024a59  mov     [rsp+1500h+var_14D8], ecx
0x180024a5d  mov     [rsp+1500h+var_14D4], eax
0x180024a61  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180024a66  cmp     dword ptr [rdx+8], 1
0x180024a6a  mov     ebx, eax
0x180024a6c  lea     eax, [r12+8]
0x180024a71  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180024a79  mov     ecx, r12d
0x180024a7c  cmovz   ecx, eax
0x180024a7f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180024a83  lea     ecx, [rax-7]
0x180024a86  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180024a8e  inc     ecx
0x180024a90  mov     [rsp+1500h+var_14C8], r12
0x180024a95  mov     [rsp+1500h+var_14D0], ecx
0x180024a99  call    cs:__imp_GetCurrentThreadId
0x180024a9f  xorps   xmm0, xmm0
0x180024aa2  mov     [rsp+1500h+var_14A8], r14
0x180024aa7  mov     [rsp+1500h+var_14C0], eax
0x180024aab  xorps   xmm1, xmm1
0x180024aae  xor     eax, eax
0x180024ab0  mov     [rsp+1500h+var_14A0], esi
0x180024ab4  mov     [rbp+1400h+var_1468], rax
0x180024ab8  mov     [rbp+1400h+var_1480], rax
0x180024abc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180024ac3  mov     [rsp+1500h+var_149C], ebx
0x180024ac7  mov     [rsp+1500h+var_14B8], r12
0x180024acc  mov     [rsp+1500h+var_14B0], r12
0x180024ad1  mov     [rbp+1400h+var_1458], rdi
0x180024ad5  mov     [rbp+1400h+var_1450], r15
0x180024ad9  mov     [rsp+1500h+var_1498], r12
0x180024ade  movups  [rbp+1400h+var_1478], xmm0
0x180024ae2  movups  [rsp+1500h+var_1490], xmm1
0x180024ae7  test    rax, rax
0x180024aea  jz      short loc_180024AF7
0x180024aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024af1  mov     [rbp+1400h+var_1460], rax
0x180024af5  jmp     short loc_180024AFB
0x180024af7  mov     [rbp+1400h+var_1460], r12
0x180024afb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180024b02  test    rax, rax
0x180024b05  jz      short loc_180024B11
0x180024b07  lea     rcx, [rsp+1500h+var_14E0]
0x180024b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b11  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180024b18  test    rax, rax
0x180024b1b  jz      short loc_180024B31
0x180024b1d  mov     r8d, 400h
0x180024b23  lea     rdx, [rbp+1400h+var_1440]
0x180024b27  lea     rcx, [rsp+1500h+var_14E0]
0x180024b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b31  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024b38  test    rax, rax
0x180024b3b  jz      short loc_180024B47
0x180024b3d  lea     rcx, [rsp+1500h+var_14E0]
0x180024b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b47  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024b4e  test    rax, rax
0x180024b51  jz      short loc_180024B64
0x180024b53  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180024b58  jnz     short loc_180024B64
0x180024b5a  lea     rcx, [rsp+1500h+var_14E0]
0x180024b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b64  cmp     [rsp+1500h+var_14D8], r12d
0x180024b69  jge     loc_180024C66
0x180024b6f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180024b76  jnz     short loc_180024B97
0x180024b78  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180024b7f  test    rax, rax
0x180024b82  jz      short loc_180024B8D
0x180024b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b89  test    al, al
0x180024b8b  jmp     short loc_180024B95
0x180024b8d  call    cs:__imp_IsDebuggerPresent
0x180024b93  test    eax, eax
0x180024b95  jz      short loc_180024B9E
0x180024b97  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180024b9c  jz      short loc_180024BC4
0x180024b9e  mov     rax, cs:g_pfnResultLoggingCallback
0x180024ba5  test    rax, rax
0x180024ba8  jz      short loc_180024C1D
0x180024baa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180024bb1  jnz     short loc_180024C1D
0x180024bb3  xor     r8d, r8d
0x180024bb6  lea     rcx, [rsp+1500h+var_14E0]
0x180024bbb  xor     edx, edx
0x180024bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bc2  jmp     short loc_180024C1D
0x180024bc4  mov     rax, cs:g_pfnResultLoggingCallback
0x180024bcb  mov     ebx, 800h
0x180024bd0  test    rax, rax
0x180024bd3  jz      short loc_180024BF2
0x180024bd5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180024bdc  jnz     short loc_180024BF2
0x180024bde  mov     r8d, ebx
0x180024be1  lea     rdx, [rbp+1400h+OutputString]
0x180024be8  lea     rcx, [rsp+1500h+var_14E0]
0x180024bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bf2  cmp     [rbp+1400h+OutputString], r12w
0x180024bfa  jnz     short loc_180024C10
0x180024bfc  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180024c01  mov     rdx, rbx; unsigned __int16 *
0x180024c04  lea     rcx, [rbp+1400h+OutputString]; this
0x180024c0b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180024c10  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180024c17  call    cs:__imp_OutputDebugStringW
0x180024c1d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180024c22  jnz     short loc_180024C2D
0x180024c24  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180024c2b  jz      short loc_180024C3E
0x180024c2d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180024c34  test    rax, rax
0x180024c37  jz      short loc_180024C3E
0x180024c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c3e  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180024c43  jnz     short loc_180024C6C
0x180024c45  mov     rcx, [rbp+1400h+var_40]
0x180024c4c  xor     rcx, rsp; StackCookie
0x180024c4f  call    __security_check_cookie
0x180024c54  add     rsp, 14D0h
0x180024c5b  pop     r15
0x180024c5d  pop     r14
0x180024c5f  pop     r12
0x180024c61  pop     rdi
0x180024c62  pop     rsi
0x180024c63  pop     rbx
0x180024c64  pop     rbp
0x180024c65  retn
0x180024c66  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180024c6c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180024c71  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
