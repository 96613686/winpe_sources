# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004984`
- end: `0x180004c2a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004608`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x180004984`
- `0x180005414`
- `0x180005990`
- `0x18000626c`
- `0x180006348`
- `0x1800265e0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a4a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bc9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bc9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b3f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b3f`

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
0x180004984  push    rbp
0x180004986  push    rbx
0x180004987  push    rsi
0x180004988  push    rdi
0x180004989  push    r12
0x18000498b  push    r14
0x18000498d  push    r15
0x18000498f  lea     rbp, [rsp-13D0h]
0x180004997  mov     eax, 14D0h
0x18000499c  call    _alloca_probe
0x1800049a1  sub     rsp, rax
0x1800049a4  mov     rax, cs:__security_cookie
0x1800049ab  xor     rax, rsp
0x1800049ae  mov     [rbp+1400h+var_40], rax
0x1800049b5  mov     rsi, r8
0x1800049b8  mov     edi, edx
0x1800049ba  mov     rbx, rcx
0x1800049bd  mov     r14, [rbp+1400h+arg_28]
0x1800049c4  xor     edx, edx; Val
0x1800049c6  mov     r8d, 98h; Size
0x1800049cc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800049d1  call    memset_0
0x1800049d6  nop
0x1800049d7  xor     r12d, r12d
0x1800049da  mov     [rbp+1400h+OutputString], r12w
0x1800049e2  mov     [rbp+1400h+var_1440], r12b
0x1800049e6  mov     rdx, [rbp+1400h+arg_30]; int
0x1800049ed  mov     ecx, [rdx]; this
0x1800049ef  mov     [rsp+1500h+var_14D8], ecx
0x1800049f3  mov     eax, [rdx+4]
0x1800049f6  mov     [rsp+1500h+var_14D4], eax
0x1800049fa  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800049ff  mov     r15d, eax
0x180004a02  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004a0a  mov     ecx, r12d
0x180004a0d  lea     eax, [r12+8]
0x180004a12  cmp     dword ptr [rdx+8], 1
0x180004a16  cmovz   ecx, eax
0x180004a19  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004a1d  lea     ecx, [rax-7]
0x180004a20  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004a28  inc     ecx
0x180004a2a  mov     [rsp+1500h+var_14D0], ecx
0x180004a2e  mov     rcx, [rbp+1400h+arg_38]
0x180004a35  test    rcx, rcx
0x180004a38  jz      short loc_180004A45
0x180004a3a  cmp     [rcx], r12w
0x180004a3e  mov     [rsp+1500h+var_14C8], rcx
0x180004a43  jnz     short loc_180004A4A
0x180004a45  mov     [rsp+1500h+var_14C8], r12
0x180004a4a  call    cs:__imp_GetCurrentThreadId
0x180004a50  mov     [rsp+1500h+var_14C0], eax
0x180004a54  mov     [rsp+1500h+var_14A8], rsi
0x180004a59  mov     [rsp+1500h+var_14A0], edi
0x180004a5d  mov     [rsp+1500h+var_149C], r15d
0x180004a62  mov     [rsp+1500h+var_14B8], r12
0x180004a67  mov     [rsp+1500h+var_14B0], r12
0x180004a6c  mov     [rbp+1400h+var_1458], r14
0x180004a70  mov     [rbp+1400h+var_1450], rbx
0x180004a74  mov     [rsp+1500h+var_1498], r12
0x180004a79  xorps   xmm0, xmm0
0x180004a7c  xor     eax, eax
0x180004a7e  movups  [rbp+1400h+var_1478], xmm0
0x180004a82  mov     [rbp+1400h+var_1468], rax
0x180004a86  xorps   xmm1, xmm1
0x180004a89  movups  [rsp+1500h+var_1490], xmm1
0x180004a8e  mov     [rbp+1400h+var_1480], rax
0x180004a92  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004a99  test    rax, rax
0x180004a9c  jz      short loc_180004AA9
0x180004a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa3  mov     [rbp+1400h+var_1460], rax
0x180004aa7  jmp     short loc_180004AAD
0x180004aa9  mov     [rbp+1400h+var_1460], r12
0x180004aad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004ab4  test    rax, rax
0x180004ab7  jz      short loc_180004AC3
0x180004ab9  lea     rcx, [rsp+1500h+var_14E0]
0x180004abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004aca  test    rax, rax
0x180004acd  jz      short loc_180004AE3
0x180004acf  mov     r8d, 400h
0x180004ad5  lea     rdx, [rbp+1400h+var_1440]
0x180004ad9  lea     rcx, [rsp+1500h+var_14E0]
0x180004ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004aea  test    rax, rax
0x180004aed  jz      short loc_180004AF9
0x180004aef  lea     rcx, [rsp+1500h+var_14E0]
0x180004af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004af9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b00  test    rax, rax
0x180004b03  jz      short loc_180004B16
0x180004b05  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004b0a  jnz     short loc_180004B16
0x180004b0c  lea     rcx, [rsp+1500h+var_14E0]
0x180004b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b16  cmp     [rsp+1500h+var_14D8], r12d
0x180004b1b  jge     loc_180004C24
0x180004b21  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004b28  jnz     short loc_180004B49
0x180004b2a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004b31  test    rax, rax
0x180004b34  jz      short loc_180004B3F
0x180004b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b3b  test    al, al
0x180004b3d  jmp     short loc_180004B47
0x180004b3f  call    cs:__imp_IsDebuggerPresent
0x180004b45  test    eax, eax
0x180004b47  jz      short loc_180004B50
0x180004b49  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004b4e  jz      short loc_180004B76
0x180004b50  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b57  test    rax, rax
0x180004b5a  jz      short loc_180004BCF
0x180004b5c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b63  jnz     short loc_180004BCF
0x180004b65  xor     r8d, r8d
0x180004b68  xor     edx, edx
0x180004b6a  lea     rcx, [rsp+1500h+var_14E0]
0x180004b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b74  jmp     short loc_180004BCF
0x180004b76  mov     ebx, 800h
0x180004b7b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b82  test    rax, rax
0x180004b85  jz      short loc_180004BA4
0x180004b87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b8e  jnz     short loc_180004BA4
0x180004b90  mov     r8d, ebx
0x180004b93  lea     rdx, [rbp+1400h+OutputString]
0x180004b9a  lea     rcx, [rsp+1500h+var_14E0]
0x180004b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ba4  cmp     [rbp+1400h+OutputString], r12w
0x180004bac  jnz     short loc_180004BC2
0x180004bae  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004bb3  mov     rdx, rbx; unsigned __int16 *
0x180004bb6  lea     rcx, [rbp+1400h+OutputString]; this
0x180004bbd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004bc2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004bc9  call    cs:__imp_OutputDebugStringW
0x180004bcf  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004bd4  jnz     short loc_180004BDF
0x180004bd6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004bdd  jz      short loc_180004BF1
0x180004bdf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004be6  test    rax, rax
0x180004be9  jz      short loc_180004BF1
0x180004beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf0  nop
0x180004bf1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004bf6  jnz     short loc_180004C19
0x180004bf8  mov     rcx, [rbp+1400h+var_40]
0x180004bff  xor     rcx, rsp; StackCookie
0x180004c02  call    __security_check_cookie
0x180004c07  add     rsp, 14D0h
0x180004c0e  pop     r15
0x180004c10  pop     r14
0x180004c12  pop     r12
0x180004c14  pop     rdi
0x180004c15  pop     rsi
0x180004c16  pop     rbx
0x180004c17  pop     rbp
0x180004c18  retn
0x180004c19  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004c1e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004c24  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
