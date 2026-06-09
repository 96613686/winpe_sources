# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a020`
- end: `0x18000a2c6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009ca4`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000a020`
- `0x18000b0f4`
- `0x18000c1c0`
- `0x18000ce78`
- `0x18000cff4`
- `0x1800915d0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0e6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a265`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a265`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a1db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a1db`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x18000a020  push    rbp
0x18000a022  push    rbx
0x18000a023  push    rsi
0x18000a024  push    rdi
0x18000a025  push    r12
0x18000a027  push    r14
0x18000a029  push    r15
0x18000a02b  lea     rbp, [rsp-13D0h]
0x18000a033  mov     eax, 14D0h
0x18000a038  call    _alloca_probe
0x18000a03d  sub     rsp, rax
0x18000a040  mov     rax, cs:__security_cookie
0x18000a047  xor     rax, rsp
0x18000a04a  mov     [rbp+1400h+var_40], rax
0x18000a051  mov     rsi, r8
0x18000a054  mov     edi, edx
0x18000a056  mov     rbx, rcx
0x18000a059  mov     r14, [rbp+1400h+arg_28]
0x18000a060  xor     edx, edx; Val
0x18000a062  mov     r8d, 98h; Size
0x18000a068  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000a06d  call    memset_0
0x18000a072  nop
0x18000a073  xor     r12d, r12d
0x18000a076  mov     [rbp+1400h+OutputString], r12w
0x18000a07e  mov     [rbp+1400h+var_1440], r12b
0x18000a082  mov     rdx, [rbp+1400h+arg_30]; int
0x18000a089  mov     ecx, [rdx]; this
0x18000a08b  mov     [rsp+1500h+var_14D8], ecx
0x18000a08f  mov     eax, [rdx+4]
0x18000a092  mov     [rsp+1500h+var_14D4], eax
0x18000a096  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a09b  mov     r15d, eax
0x18000a09e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000a0a6  mov     ecx, r12d
0x18000a0a9  lea     eax, [r12+8]
0x18000a0ae  cmp     dword ptr [rdx+8], 1
0x18000a0b2  cmovz   ecx, eax
0x18000a0b5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000a0b9  lea     ecx, [rax-7]
0x18000a0bc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a0c4  inc     ecx
0x18000a0c6  mov     [rsp+1500h+var_14D0], ecx
0x18000a0ca  mov     rcx, [rbp+1400h+arg_38]
0x18000a0d1  test    rcx, rcx
0x18000a0d4  jz      short loc_18000A0E1
0x18000a0d6  cmp     [rcx], r12w
0x18000a0da  mov     [rsp+1500h+var_14C8], rcx
0x18000a0df  jnz     short loc_18000A0E6
0x18000a0e1  mov     [rsp+1500h+var_14C8], r12
0x18000a0e6  call    cs:__imp_GetCurrentThreadId
0x18000a0ec  mov     [rsp+1500h+var_14C0], eax
0x18000a0f0  mov     [rsp+1500h+var_14A8], rsi
0x18000a0f5  mov     [rsp+1500h+var_14A0], edi
0x18000a0f9  mov     [rsp+1500h+var_149C], r15d
0x18000a0fe  mov     [rsp+1500h+var_14B8], r12
0x18000a103  mov     [rsp+1500h+var_14B0], r12
0x18000a108  mov     [rbp+1400h+var_1458], r14
0x18000a10c  mov     [rbp+1400h+var_1450], rbx
0x18000a110  mov     [rsp+1500h+var_1498], r12
0x18000a115  xorps   xmm0, xmm0
0x18000a118  xor     eax, eax
0x18000a11a  movups  [rbp+1400h+var_1478], xmm0
0x18000a11e  mov     [rbp+1400h+var_1468], rax
0x18000a122  xorps   xmm1, xmm1
0x18000a125  movups  [rsp+1500h+var_1490], xmm1
0x18000a12a  mov     [rbp+1400h+var_1480], rax
0x18000a12e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a135  test    rax, rax
0x18000a138  jz      short loc_18000A145
0x18000a13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a13f  mov     [rbp+1400h+var_1460], rax
0x18000a143  jmp     short loc_18000A149
0x18000a145  mov     [rbp+1400h+var_1460], r12
0x18000a149  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a150  test    rax, rax
0x18000a153  jz      short loc_18000A15F
0x18000a155  lea     rcx, [rsp+1500h+var_14E0]
0x18000a15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a15f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a166  test    rax, rax
0x18000a169  jz      short loc_18000A17F
0x18000a16b  mov     r8d, 400h
0x18000a171  lea     rdx, [rbp+1400h+var_1440]
0x18000a175  lea     rcx, [rsp+1500h+var_14E0]
0x18000a17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a17f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a186  test    rax, rax
0x18000a189  jz      short loc_18000A195
0x18000a18b  lea     rcx, [rsp+1500h+var_14E0]
0x18000a190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a195  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a19c  test    rax, rax
0x18000a19f  jz      short loc_18000A1B2
0x18000a1a1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a1a6  jnz     short loc_18000A1B2
0x18000a1a8  lea     rcx, [rsp+1500h+var_14E0]
0x18000a1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b2  cmp     [rsp+1500h+var_14D8], r12d
0x18000a1b7  jge     loc_18000A2C0
0x18000a1bd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000a1c4  jnz     short loc_18000A1E5
0x18000a1c6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a1cd  test    rax, rax
0x18000a1d0  jz      short loc_18000A1DB
0x18000a1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d7  test    al, al
0x18000a1d9  jmp     short loc_18000A1E3
0x18000a1db  call    cs:__imp_IsDebuggerPresent
0x18000a1e1  test    eax, eax
0x18000a1e3  jz      short loc_18000A1EC
0x18000a1e5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a1ea  jz      short loc_18000A212
0x18000a1ec  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a1f3  test    rax, rax
0x18000a1f6  jz      short loc_18000A26B
0x18000a1f8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000a1ff  jnz     short loc_18000A26B
0x18000a201  xor     r8d, r8d
0x18000a204  xor     edx, edx
0x18000a206  lea     rcx, [rsp+1500h+var_14E0]
0x18000a20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a210  jmp     short loc_18000A26B
0x18000a212  mov     ebx, 800h
0x18000a217  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a21e  test    rax, rax
0x18000a221  jz      short loc_18000A240
0x18000a223  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000a22a  jnz     short loc_18000A240
0x18000a22c  mov     r8d, ebx
0x18000a22f  lea     rdx, [rbp+1400h+OutputString]
0x18000a236  lea     rcx, [rsp+1500h+var_14E0]
0x18000a23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a240  cmp     [rbp+1400h+OutputString], r12w
0x18000a248  jnz     short loc_18000A25E
0x18000a24a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000a24f  mov     rdx, rbx; unsigned __int16 *
0x18000a252  lea     rcx, [rbp+1400h+OutputString]; this
0x18000a259  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a25e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000a265  call    cs:__imp_OutputDebugStringW
0x18000a26b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000a270  jnz     short loc_18000A27B
0x18000a272  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000a279  jz      short loc_18000A28D
0x18000a27b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a282  test    rax, rax
0x18000a285  jz      short loc_18000A28D
0x18000a287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a28c  nop
0x18000a28d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000a292  jnz     short loc_18000A2B5
0x18000a294  mov     rcx, [rbp+1400h+var_40]
0x18000a29b  xor     rcx, rsp; StackCookie
0x18000a29e  call    __security_check_cookie
0x18000a2a3  add     rsp, 14D0h
0x18000a2aa  pop     r15
0x18000a2ac  pop     r14
0x18000a2ae  pop     r12
0x18000a2b0  pop     rdi
0x18000a2b1  pop     rsi
0x18000a2b2  pop     rbx
0x18000a2b3  pop     rbp
0x18000a2b4  retn
0x18000a2b5  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000a2ba  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000a2c0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
