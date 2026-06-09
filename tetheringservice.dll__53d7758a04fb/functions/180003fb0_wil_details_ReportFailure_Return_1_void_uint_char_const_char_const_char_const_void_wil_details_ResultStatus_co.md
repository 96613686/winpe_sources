# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003fb0`
- end: `0x18000423d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003a4c`

## callees

- `0x180002590`
- `0x180003088`
- `0x180003fb0`
- `0x1800064a4`
- `0x180007a18`
- `0x18000a040`
- `0x18000a20c`
- `0x180031580`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000405e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000405e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004152`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004152`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800041dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800041dc`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180003fb0  push    rbp
0x180003fb2  push    rbx
0x180003fb3  push    rsi
0x180003fb4  push    rdi
0x180003fb5  push    r12
0x180003fb7  push    r14
0x180003fb9  push    r15
0x180003fbb  lea     rbp, [rsp-13D0h]
0x180003fc3  mov     eax, 14D0h
0x180003fc8  call    _alloca_probe
0x180003fcd  sub     rsp, rax
0x180003fd0  mov     rax, cs:__security_cookie
0x180003fd7  xor     rax, rsp
0x180003fda  mov     [rbp+1400h+var_40], rax
0x180003fe1  mov     r14, r8
0x180003fe4  mov     esi, edx
0x180003fe6  mov     r15, rcx
0x180003fe9  mov     rdi, [rbp+1400h+arg_28]
0x180003ff0  xor     edx, edx; Val
0x180003ff2  mov     r8d, 98h; Size
0x180003ff8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003ffd  call    memset_0
0x180004002  nop
0x180004003  xor     r12d, r12d
0x180004006  mov     [rbp+1400h+OutputString], r12w
0x18000400e  mov     [rbp+1400h+var_1440], r12b
0x180004012  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180004019  mov     ecx, [rdx]; this
0x18000401b  mov     [rsp+1500h+var_14D8], ecx
0x18000401f  mov     eax, [rdx+4]
0x180004022  mov     [rsp+1500h+var_14D4], eax
0x180004026  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000402b  mov     ebx, eax
0x18000402d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004035  mov     ecx, r12d
0x180004038  lea     eax, [r12+8]
0x18000403d  cmp     dword ptr [rdx+8], 1
0x180004041  cmovz   ecx, eax
0x180004044  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004048  lea     ecx, [rax-7]
0x18000404b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004053  inc     ecx
0x180004055  mov     [rsp+1500h+var_14D0], ecx
0x180004059  mov     [rsp+1500h+var_14C8], r12
0x18000405e  call    cs:__imp_GetCurrentThreadId
0x180004064  mov     [rsp+1500h+var_14C0], eax
0x180004068  mov     [rsp+1500h+var_14A8], r14
0x18000406d  mov     [rsp+1500h+var_14A0], esi
0x180004071  mov     [rsp+1500h+var_149C], ebx
0x180004075  mov     [rsp+1500h+var_14B8], r12
0x18000407a  mov     [rsp+1500h+var_14B0], r12
0x18000407f  mov     [rbp+1400h+var_1458], rdi
0x180004083  mov     [rbp+1400h+var_1450], r15
0x180004087  mov     [rsp+1500h+var_1498], r12
0x18000408c  xorps   xmm0, xmm0
0x18000408f  xor     eax, eax
0x180004091  movups  [rbp+1400h+var_1478], xmm0
0x180004095  mov     [rbp+1400h+var_1468], rax
0x180004099  xorps   xmm1, xmm1
0x18000409c  movups  [rsp+1500h+var_1490], xmm1
0x1800040a1  mov     [rbp+1400h+var_1480], rax
0x1800040a5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800040ac  test    rax, rax
0x1800040af  jz      short loc_1800040BC
0x1800040b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b6  mov     [rbp+1400h+var_1460], rax
0x1800040ba  jmp     short loc_1800040C0
0x1800040bc  mov     [rbp+1400h+var_1460], r12
0x1800040c0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800040c7  test    rax, rax
0x1800040ca  jz      short loc_1800040D6
0x1800040cc  lea     rcx, [rsp+1500h+var_14E0]
0x1800040d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040d6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800040dd  test    rax, rax
0x1800040e0  jz      short loc_1800040F6
0x1800040e2  mov     r8d, 400h
0x1800040e8  lea     rdx, [rbp+1400h+var_1440]
0x1800040ec  lea     rcx, [rsp+1500h+var_14E0]
0x1800040f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800040fd  test    rax, rax
0x180004100  jz      short loc_18000410C
0x180004102  lea     rcx, [rsp+1500h+var_14E0]
0x180004107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000410c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004113  test    rax, rax
0x180004116  jz      short loc_180004129
0x180004118  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000411d  jnz     short loc_180004129
0x18000411f  lea     rcx, [rsp+1500h+var_14E0]
0x180004124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004129  cmp     [rsp+1500h+var_14D8], r12d
0x18000412e  jge     loc_180004237
0x180004134  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000413b  jnz     short loc_18000415C
0x18000413d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004144  test    rax, rax
0x180004147  jz      short loc_180004152
0x180004149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414e  test    al, al
0x180004150  jmp     short loc_18000415A
0x180004152  call    cs:__imp_IsDebuggerPresent
0x180004158  test    eax, eax
0x18000415a  jz      short loc_180004163
0x18000415c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004161  jz      short loc_180004189
0x180004163  mov     rax, cs:g_pfnResultLoggingCallback
0x18000416a  test    rax, rax
0x18000416d  jz      short loc_1800041E2
0x18000416f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004176  jnz     short loc_1800041E2
0x180004178  xor     r8d, r8d
0x18000417b  xor     edx, edx
0x18000417d  lea     rcx, [rsp+1500h+var_14E0]
0x180004182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004187  jmp     short loc_1800041E2
0x180004189  mov     ebx, 800h
0x18000418e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004195  test    rax, rax
0x180004198  jz      short loc_1800041B7
0x18000419a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800041a1  jnz     short loc_1800041B7
0x1800041a3  mov     r8d, ebx
0x1800041a6  lea     rdx, [rbp+1400h+OutputString]
0x1800041ad  lea     rcx, [rsp+1500h+var_14E0]
0x1800041b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b7  cmp     [rbp+1400h+OutputString], r12w
0x1800041bf  jnz     short loc_1800041D5
0x1800041c1  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800041c6  mov     rdx, rbx; unsigned __int16 *
0x1800041c9  lea     rcx, [rbp+1400h+OutputString]; this
0x1800041d0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800041d5  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800041dc  call    cs:__imp_OutputDebugStringW
0x1800041e2  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800041e7  jnz     short loc_1800041F2
0x1800041e9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800041f0  jz      short loc_180004204
0x1800041f2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800041f9  test    rax, rax
0x1800041fc  jz      short loc_180004204
0x1800041fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004203  nop
0x180004204  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004209  jnz     short loc_18000422C
0x18000420b  mov     rcx, [rbp+1400h+var_40]
0x180004212  xor     rcx, rsp; StackCookie
0x180004215  call    __security_check_cookie
0x18000421a  add     rsp, 14D0h
0x180004221  pop     r15
0x180004223  pop     r14
0x180004225  pop     r12
0x180004227  pop     rdi
0x180004228  pop     rsi
0x180004229  pop     rbx
0x18000422a  pop     rbp
0x18000422b  retn
0x18000422c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004231  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004237  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
