# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004994`
- end: `0x180004c1f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004474`

## callees

- `0x180004994`
- `0x180005794`
- `0x180006730`
- `0x1800070a0`
- `0x180007228`
- `0x18001a1d6`
- `0x18001a210`
- `0x18001a2d0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a41`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b35`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bbf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bbf`

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
0x180004994  push    rbp
0x180004996  push    rbx
0x180004997  push    rsi
0x180004998  push    rdi
0x180004999  push    r12
0x18000499b  push    r14
0x18000499d  push    r15
0x18000499f  lea     rbp, [rsp-13D0h]
0x1800049a7  mov     eax, 14D0h
0x1800049ac  call    _alloca_probe
0x1800049b1  sub     rsp, rax
0x1800049b4  mov     rax, cs:__security_cookie
0x1800049bb  xor     rax, rsp
0x1800049be  mov     [rbp+1400h+var_40], rax
0x1800049c5  mov     rdi, [rbp+1400h+arg_28]
0x1800049cc  mov     r14, r8
0x1800049cf  mov     esi, edx
0x1800049d1  mov     r15, rcx
0x1800049d4  xor     edx, edx; Val
0x1800049d6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800049db  mov     r8d, 98h; Size
0x1800049e1  call    memset_0
0x1800049e6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800049ed  xor     r12d, r12d
0x1800049f0  mov     [rbp+1400h+OutputString], r12w
0x1800049f8  mov     [rbp+1400h+var_1440], r12b
0x1800049fc  mov     ecx, [rdx]; this
0x1800049fe  mov     eax, [rdx+4]
0x180004a01  mov     [rsp+1500h+var_14D8], ecx
0x180004a05  mov     [rsp+1500h+var_14D4], eax
0x180004a09  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004a0e  cmp     dword ptr [rdx+8], 1
0x180004a12  mov     ebx, eax
0x180004a14  lea     eax, [r12+8]
0x180004a19  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004a21  mov     ecx, r12d
0x180004a24  cmovz   ecx, eax
0x180004a27  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004a2b  lea     ecx, [rax-7]
0x180004a2e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004a36  inc     ecx
0x180004a38  mov     [rsp+1500h+var_14C8], r12
0x180004a3d  mov     [rsp+1500h+var_14D0], ecx
0x180004a41  call    cs:__imp_GetCurrentThreadId
0x180004a47  xorps   xmm0, xmm0
0x180004a4a  mov     [rsp+1500h+var_14A8], r14
0x180004a4f  mov     [rsp+1500h+var_14C0], eax
0x180004a53  xorps   xmm1, xmm1
0x180004a56  xor     eax, eax
0x180004a58  mov     [rsp+1500h+var_14A0], esi
0x180004a5c  mov     [rbp+1400h+var_1468], rax
0x180004a60  mov     [rbp+1400h+var_1480], rax
0x180004a64  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004a6b  mov     [rsp+1500h+var_149C], ebx
0x180004a6f  mov     [rsp+1500h+var_14B8], r12
0x180004a74  mov     [rsp+1500h+var_14B0], r12
0x180004a79  mov     [rbp+1400h+var_1458], rdi
0x180004a7d  mov     [rbp+1400h+var_1450], r15
0x180004a81  mov     [rsp+1500h+var_1498], r12
0x180004a86  movups  [rbp+1400h+var_1478], xmm0
0x180004a8a  movups  [rsp+1500h+var_1490], xmm1
0x180004a8f  test    rax, rax
0x180004a92  jz      short loc_180004A9F
0x180004a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a99  mov     [rbp+1400h+var_1460], rax
0x180004a9d  jmp     short loc_180004AA3
0x180004a9f  mov     [rbp+1400h+var_1460], r12
0x180004aa3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004aaa  test    rax, rax
0x180004aad  jz      short loc_180004AB9
0x180004aaf  lea     rcx, [rsp+1500h+var_14E0]
0x180004ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ac0  test    rax, rax
0x180004ac3  jz      short loc_180004AD9
0x180004ac5  mov     r8d, 400h
0x180004acb  lea     rdx, [rbp+1400h+var_1440]
0x180004acf  lea     rcx, [rsp+1500h+var_14E0]
0x180004ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ae0  test    rax, rax
0x180004ae3  jz      short loc_180004AEF
0x180004ae5  lea     rcx, [rsp+1500h+var_14E0]
0x180004aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aef  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004af6  test    rax, rax
0x180004af9  jz      short loc_180004B0C
0x180004afb  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004b00  jnz     short loc_180004B0C
0x180004b02  lea     rcx, [rsp+1500h+var_14E0]
0x180004b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b0c  cmp     [rsp+1500h+var_14D8], r12d
0x180004b11  jge     loc_180004C0E
0x180004b17  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004b1e  jnz     short loc_180004B3F
0x180004b20  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004b27  test    rax, rax
0x180004b2a  jz      short loc_180004B35
0x180004b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b31  test    al, al
0x180004b33  jmp     short loc_180004B3D
0x180004b35  call    cs:__imp_IsDebuggerPresent
0x180004b3b  test    eax, eax
0x180004b3d  jz      short loc_180004B46
0x180004b3f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004b44  jz      short loc_180004B6C
0x180004b46  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b4d  test    rax, rax
0x180004b50  jz      short loc_180004BC5
0x180004b52  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b59  jnz     short loc_180004BC5
0x180004b5b  xor     r8d, r8d
0x180004b5e  lea     rcx, [rsp+1500h+var_14E0]
0x180004b63  xor     edx, edx
0x180004b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6a  jmp     short loc_180004BC5
0x180004b6c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b73  mov     ebx, 800h
0x180004b78  test    rax, rax
0x180004b7b  jz      short loc_180004B9A
0x180004b7d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b84  jnz     short loc_180004B9A
0x180004b86  mov     r8d, ebx
0x180004b89  lea     rdx, [rbp+1400h+OutputString]
0x180004b90  lea     rcx, [rsp+1500h+var_14E0]
0x180004b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b9a  cmp     [rbp+1400h+OutputString], r12w
0x180004ba2  jnz     short loc_180004BB8
0x180004ba4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004ba9  mov     rdx, rbx; unsigned __int16 *
0x180004bac  lea     rcx, [rbp+1400h+OutputString]; this
0x180004bb3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004bb8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004bbf  call    cs:__imp_OutputDebugStringW
0x180004bc5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004bca  jnz     short loc_180004BD5
0x180004bcc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004bd3  jz      short loc_180004BE6
0x180004bd5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004bdc  test    rax, rax
0x180004bdf  jz      short loc_180004BE6
0x180004be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004beb  jnz     short loc_180004C14
0x180004bed  mov     rcx, [rbp+1400h+var_40]
0x180004bf4  xor     rcx, rsp; StackCookie
0x180004bf7  call    __security_check_cookie
0x180004bfc  add     rsp, 14D0h
0x180004c03  pop     r15
0x180004c05  pop     r14
0x180004c07  pop     r12
0x180004c09  pop     rdi
0x180004c0a  pop     rsi
0x180004c0b  pop     rbx
0x180004c0c  pop     rbp
0x180004c0d  retn
0x180004c0e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004c14  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004c19  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
