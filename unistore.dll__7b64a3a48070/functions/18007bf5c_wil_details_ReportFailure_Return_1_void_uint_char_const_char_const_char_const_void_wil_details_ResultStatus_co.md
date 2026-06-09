# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18007bf5c`
- end: `0x18007c1e7`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18007be9c`

## callees

- `0x18007bf5c`
- `0x18007c5b4`
- `0x18007cd50`
- `0x18007d058`
- `0x18007d15c`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c5180`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c009`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007c0fd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007c0fd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18007c187`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18007c187`

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
0x18007bf5c  push    rbp
0x18007bf5e  push    rbx
0x18007bf5f  push    rsi
0x18007bf60  push    rdi
0x18007bf61  push    r12
0x18007bf63  push    r14
0x18007bf65  push    r15
0x18007bf67  lea     rbp, [rsp-13D0h]
0x18007bf6f  mov     eax, 14D0h
0x18007bf74  call    _alloca_probe
0x18007bf79  sub     rsp, rax
0x18007bf7c  mov     rax, cs:__security_cookie
0x18007bf83  xor     rax, rsp
0x18007bf86  mov     [rbp+1400h+var_40], rax
0x18007bf8d  mov     rdi, [rbp+1400h+arg_28]
0x18007bf94  mov     r14, r8
0x18007bf97  mov     esi, edx
0x18007bf99  mov     r15, rcx
0x18007bf9c  xor     edx, edx; Val
0x18007bf9e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18007bfa3  mov     r8d, 98h; Size
0x18007bfa9  call    memset_0
0x18007bfae  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18007bfb5  xor     r12d, r12d
0x18007bfb8  mov     [rbp+1400h+OutputString], r12w
0x18007bfc0  mov     [rbp+1400h+var_1440], r12b
0x18007bfc4  mov     ecx, [rdx]; this
0x18007bfc6  mov     eax, [rdx+4]
0x18007bfc9  mov     [rsp+1500h+var_14D8], ecx
0x18007bfcd  mov     [rsp+1500h+var_14D4], eax
0x18007bfd1  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18007bfd6  cmp     dword ptr [rdx+8], 1
0x18007bfda  mov     ebx, eax
0x18007bfdc  lea     eax, [r12+8]
0x18007bfe1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18007bfe9  mov     ecx, r12d
0x18007bfec  cmovz   ecx, eax
0x18007bfef  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18007bff3  lea     ecx, [rax-7]
0x18007bff6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18007bffe  inc     ecx
0x18007c000  mov     [rsp+1500h+var_14C8], r12
0x18007c005  mov     [rsp+1500h+var_14D0], ecx
0x18007c009  call    cs:__imp_GetCurrentThreadId
0x18007c00f  xorps   xmm0, xmm0
0x18007c012  mov     [rsp+1500h+var_14A8], r14
0x18007c017  mov     [rsp+1500h+var_14C0], eax
0x18007c01b  xorps   xmm1, xmm1
0x18007c01e  xor     eax, eax
0x18007c020  mov     [rsp+1500h+var_14A0], esi
0x18007c024  mov     [rbp+1400h+var_1468], rax
0x18007c028  mov     [rbp+1400h+var_1480], rax
0x18007c02c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18007c033  mov     [rsp+1500h+var_149C], ebx
0x18007c037  mov     [rsp+1500h+var_14B8], r12
0x18007c03c  mov     [rsp+1500h+var_14B0], r12
0x18007c041  mov     [rbp+1400h+var_1458], rdi
0x18007c045  mov     [rbp+1400h+var_1450], r15
0x18007c049  mov     [rsp+1500h+var_1498], r12
0x18007c04e  movups  [rbp+1400h+var_1478], xmm0
0x18007c052  movups  [rsp+1500h+var_1490], xmm1
0x18007c057  test    rax, rax
0x18007c05a  jz      short loc_18007C067
0x18007c05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c061  mov     [rbp+1400h+var_1460], rax
0x18007c065  jmp     short loc_18007C06B
0x18007c067  mov     [rbp+1400h+var_1460], r12
0x18007c06b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18007c072  test    rax, rax
0x18007c075  jz      short loc_18007C081
0x18007c077  lea     rcx, [rsp+1500h+var_14E0]
0x18007c07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c081  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18007c088  test    rax, rax
0x18007c08b  jz      short loc_18007C0A1
0x18007c08d  mov     r8d, 400h
0x18007c093  lea     rdx, [rbp+1400h+var_1440]
0x18007c097  lea     rcx, [rsp+1500h+var_14E0]
0x18007c09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c0a1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007c0a8  test    rax, rax
0x18007c0ab  jz      short loc_18007C0B7
0x18007c0ad  lea     rcx, [rsp+1500h+var_14E0]
0x18007c0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c0b7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007c0be  test    rax, rax
0x18007c0c1  jz      short loc_18007C0D4
0x18007c0c3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18007c0c8  jnz     short loc_18007C0D4
0x18007c0ca  lea     rcx, [rsp+1500h+var_14E0]
0x18007c0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c0d4  cmp     [rsp+1500h+var_14D8], r12d
0x18007c0d9  jge     loc_18007C1D6
0x18007c0df  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18007c0e6  jnz     short loc_18007C107
0x18007c0e8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18007c0ef  test    rax, rax
0x18007c0f2  jz      short loc_18007C0FD
0x18007c0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c0f9  test    al, al
0x18007c0fb  jmp     short loc_18007C105
0x18007c0fd  call    cs:__imp_IsDebuggerPresent
0x18007c103  test    eax, eax
0x18007c105  jz      short loc_18007C10E
0x18007c107  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18007c10c  jz      short loc_18007C134
0x18007c10e  mov     rax, cs:g_pfnResultLoggingCallback
0x18007c115  test    rax, rax
0x18007c118  jz      short loc_18007C18D
0x18007c11a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18007c121  jnz     short loc_18007C18D
0x18007c123  xor     r8d, r8d
0x18007c126  lea     rcx, [rsp+1500h+var_14E0]
0x18007c12b  xor     edx, edx
0x18007c12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c132  jmp     short loc_18007C18D
0x18007c134  mov     rax, cs:g_pfnResultLoggingCallback
0x18007c13b  mov     ebx, 800h
0x18007c140  test    rax, rax
0x18007c143  jz      short loc_18007C162
0x18007c145  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18007c14c  jnz     short loc_18007C162
0x18007c14e  mov     r8d, ebx
0x18007c151  lea     rdx, [rbp+1400h+OutputString]
0x18007c158  lea     rcx, [rsp+1500h+var_14E0]
0x18007c15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c162  cmp     [rbp+1400h+OutputString], r12w
0x18007c16a  jnz     short loc_18007C180
0x18007c16c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18007c171  mov     rdx, rbx; unsigned __int16 *
0x18007c174  lea     rcx, [rbp+1400h+OutputString]; this
0x18007c17b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18007c180  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18007c187  call    cs:__imp_OutputDebugStringW
0x18007c18d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18007c192  jnz     short loc_18007C19D
0x18007c194  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18007c19b  jz      short loc_18007C1AE
0x18007c19d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18007c1a4  test    rax, rax
0x18007c1a7  jz      short loc_18007C1AE
0x18007c1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c1ae  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18007c1b3  jnz     short loc_18007C1DC
0x18007c1b5  mov     rcx, [rbp+1400h+var_40]
0x18007c1bc  xor     rcx, rsp; StackCookie
0x18007c1bf  call    __security_check_cookie
0x18007c1c4  add     rsp, 14D0h
0x18007c1cb  pop     r15
0x18007c1cd  pop     r14
0x18007c1cf  pop     r12
0x18007c1d1  pop     rdi
0x18007c1d2  pop     rsi
0x18007c1d3  pop     rbx
0x18007c1d4  pop     rbp
0x18007c1d5  retn
0x18007c1d6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18007c1dc  lea     rcx, [rsp+1500h+var_14E0]; this
0x18007c1e1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
