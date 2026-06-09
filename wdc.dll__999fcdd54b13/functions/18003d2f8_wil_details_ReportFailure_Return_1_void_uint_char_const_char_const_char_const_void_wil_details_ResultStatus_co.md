# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18003d2f8`
- end: `0x18003d583`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800356e4`

## callees

- `0x18003a3c0`
- `0x18003b0ac`
- `0x18003d2f8`
- `0x18003e694`
- `0x18003fd78`
- `0x180041078`
- `0x180041230`
- `0x180084db0`
- `0x180086010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18003d499`
- `KERNEL32!IsDebuggerPresent` at `0x18003d499`
- `KERNEL32!OutputDebugStringW` at `0x18003d523`
- `KERNEL32!OutputDebugStringW` at `0x18003d523`
- `KERNEL32!GetCurrentThreadId` at `0x18003d3a5`
- `KERNEL32!GetCurrentThreadId` at `0x18003d3a5`

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
0x18003d2f8  push    rbp
0x18003d2fa  push    rbx
0x18003d2fb  push    rsi
0x18003d2fc  push    rdi
0x18003d2fd  push    r12
0x18003d2ff  push    r14
0x18003d301  push    r15
0x18003d303  lea     rbp, [rsp-13D0h]
0x18003d30b  mov     eax, 14D0h
0x18003d310  call    _alloca_probe
0x18003d315  sub     rsp, rax
0x18003d318  mov     rax, cs:__security_cookie
0x18003d31f  xor     rax, rsp
0x18003d322  mov     [rbp+1400h+var_40], rax
0x18003d329  mov     rdi, [rbp+1400h+arg_28]
0x18003d330  mov     r14, r8
0x18003d333  mov     esi, edx
0x18003d335  mov     r15, rcx
0x18003d338  xor     edx, edx; Val
0x18003d33a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18003d33f  mov     r8d, 98h; Size
0x18003d345  call    memset_0
0x18003d34a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18003d351  xor     r12d, r12d
0x18003d354  mov     [rbp+1400h+OutputString], r12w
0x18003d35c  mov     [rbp+1400h+var_1440], r12b
0x18003d360  mov     ecx, [rdx]; this
0x18003d362  mov     eax, [rdx+4]
0x18003d365  mov     [rsp+1500h+var_14D8], ecx
0x18003d369  mov     [rsp+1500h+var_14D4], eax
0x18003d36d  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003d372  cmp     dword ptr [rdx+8], 1
0x18003d376  mov     ebx, eax
0x18003d378  lea     eax, [r12+8]
0x18003d37d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18003d385  mov     ecx, r12d
0x18003d388  cmovz   ecx, eax
0x18003d38b  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18003d38f  lea     ecx, [rax-7]
0x18003d392  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003d39a  inc     ecx
0x18003d39c  mov     [rsp+1500h+var_14C8], r12
0x18003d3a1  mov     [rsp+1500h+var_14D0], ecx
0x18003d3a5  call    cs:__imp_GetCurrentThreadId
0x18003d3ab  xorps   xmm0, xmm0
0x18003d3ae  mov     [rsp+1500h+var_14A8], r14
0x18003d3b3  mov     [rsp+1500h+var_14C0], eax
0x18003d3b7  xorps   xmm1, xmm1
0x18003d3ba  xor     eax, eax
0x18003d3bc  mov     [rsp+1500h+var_14A0], esi
0x18003d3c0  mov     [rbp+1400h+var_1468], rax
0x18003d3c4  mov     [rbp+1400h+var_1480], rax
0x18003d3c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003d3cf  mov     [rsp+1500h+var_149C], ebx
0x18003d3d3  mov     [rsp+1500h+var_14B8], r12
0x18003d3d8  mov     [rsp+1500h+var_14B0], r12
0x18003d3dd  mov     [rbp+1400h+var_1458], rdi
0x18003d3e1  mov     [rbp+1400h+var_1450], r15
0x18003d3e5  mov     [rsp+1500h+var_1498], r12
0x18003d3ea  movups  [rbp+1400h+var_1478], xmm0
0x18003d3ee  movups  [rsp+1500h+var_1490], xmm1
0x18003d3f3  test    rax, rax
0x18003d3f6  jz      short loc_18003D403
0x18003d3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3fd  mov     [rbp+1400h+var_1460], rax
0x18003d401  jmp     short loc_18003D407
0x18003d403  mov     [rbp+1400h+var_1460], r12
0x18003d407  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003d40e  test    rax, rax
0x18003d411  jz      short loc_18003D41D
0x18003d413  lea     rcx, [rsp+1500h+var_14E0]
0x18003d418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d41d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003d424  test    rax, rax
0x18003d427  jz      short loc_18003D43D
0x18003d429  mov     r8d, 400h
0x18003d42f  lea     rdx, [rbp+1400h+var_1440]
0x18003d433  lea     rcx, [rsp+1500h+var_14E0]
0x18003d438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d43d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003d444  test    rax, rax
0x18003d447  jz      short loc_18003D453
0x18003d449  lea     rcx, [rsp+1500h+var_14E0]
0x18003d44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d453  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003d45a  test    rax, rax
0x18003d45d  jz      short loc_18003D470
0x18003d45f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18003d464  jnz     short loc_18003D470
0x18003d466  lea     rcx, [rsp+1500h+var_14E0]
0x18003d46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d470  cmp     [rsp+1500h+var_14D8], r12d
0x18003d475  jge     loc_18003D572
0x18003d47b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18003d482  jnz     short loc_18003D4A3
0x18003d484  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003d48b  test    rax, rax
0x18003d48e  jz      short loc_18003D499
0x18003d490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d495  test    al, al
0x18003d497  jmp     short loc_18003D4A1
0x18003d499  call    cs:__imp_IsDebuggerPresent
0x18003d49f  test    eax, eax
0x18003d4a1  jz      short loc_18003D4AA
0x18003d4a3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18003d4a8  jz      short loc_18003D4D0
0x18003d4aa  mov     rax, cs:g_pfnResultLoggingCallback
0x18003d4b1  test    rax, rax
0x18003d4b4  jz      short loc_18003D529
0x18003d4b6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18003d4bd  jnz     short loc_18003D529
0x18003d4bf  xor     r8d, r8d
0x18003d4c2  lea     rcx, [rsp+1500h+var_14E0]
0x18003d4c7  xor     edx, edx
0x18003d4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4ce  jmp     short loc_18003D529
0x18003d4d0  mov     rax, cs:g_pfnResultLoggingCallback
0x18003d4d7  mov     ebx, 800h
0x18003d4dc  test    rax, rax
0x18003d4df  jz      short loc_18003D4FE
0x18003d4e1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18003d4e8  jnz     short loc_18003D4FE
0x18003d4ea  mov     r8d, ebx
0x18003d4ed  lea     rdx, [rbp+1400h+OutputString]
0x18003d4f4  lea     rcx, [rsp+1500h+var_14E0]
0x18003d4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4fe  cmp     [rbp+1400h+OutputString], r12w
0x18003d506  jnz     short loc_18003D51C
0x18003d508  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18003d50d  mov     rdx, rbx; unsigned __int16 *
0x18003d510  lea     rcx, [rbp+1400h+OutputString]; this
0x18003d517  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003d51c  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18003d523  call    cs:__imp_OutputDebugStringW
0x18003d529  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18003d52e  jnz     short loc_18003D539
0x18003d530  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18003d537  jz      short loc_18003D54A
0x18003d539  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003d540  test    rax, rax
0x18003d543  jz      short loc_18003D54A
0x18003d545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d54a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18003d54f  jnz     short loc_18003D578
0x18003d551  mov     rcx, [rbp+1400h+var_40]
0x18003d558  xor     rcx, rsp; StackCookie
0x18003d55b  call    __security_check_cookie
0x18003d560  add     rsp, 14D0h
0x18003d567  pop     r15
0x18003d569  pop     r14
0x18003d56b  pop     r12
0x18003d56d  pop     rdi
0x18003d56e  pop     rsi
0x18003d56f  pop     rbx
0x18003d570  pop     rbp
0x18003d571  retn
0x18003d572  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003d578  lea     rcx, [rsp+1500h+var_14E0]; this
0x18003d57d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
