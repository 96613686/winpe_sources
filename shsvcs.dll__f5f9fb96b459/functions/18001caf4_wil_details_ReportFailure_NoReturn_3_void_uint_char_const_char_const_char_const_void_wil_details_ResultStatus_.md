# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001caf4`
- end: `0x18001cd54`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001c890`

## callees

- `0x18001a1f8`
- `0x18001caf4`
- `0x18001e7a4`
- `0x1800201f0`
- `0x180021e38`
- `0x180032c6a`
- `0x180032d20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cd22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cd22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cc98`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cc98`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
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
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
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
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18001caf4  mov     [rsp-8+arg_18], rbx
0x18001caf9  push    rbp
0x18001cafa  push    rsi
0x18001cafb  push    rdi
0x18001cafc  push    r12
0x18001cafe  push    r13
0x18001cb00  push    r14
0x18001cb02  push    r15
0x18001cb04  lea     rbp, [rsp-13C0h]
0x18001cb0c  mov     eax, 14C0h
0x18001cb11  call    _alloca_probe
0x18001cb16  sub     rsp, rax
0x18001cb19  mov     rsi, [rbp+13F0h+arg_28]
0x18001cb20  mov     r15, r8
0x18001cb23  mov     r14d, edx
0x18001cb26  mov     r12, rcx
0x18001cb29  xor     edx, edx; Val
0x18001cb2b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001cb30  mov     r8d, 98h; Size
0x18001cb36  call    memset_0
0x18001cb3b  mov     rbx, [rbp+13F0h+arg_30]
0x18001cb42  xor     r13d, r13d
0x18001cb45  mov     [rbp+13F0h+OutputString], r13w
0x18001cb4d  mov     [rbp+13F0h+var_1430], r13b
0x18001cb51  mov     ecx, [rbx]; this
0x18001cb53  mov     eax, [rbx+4]
0x18001cb56  mov     [rsp+14F0h+var_14C8], ecx
0x18001cb5a  mov     [rsp+14F0h+var_14C4], eax
0x18001cb5e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001cb63  cmp     dword ptr [rbx+8], 1
0x18001cb67  mov     edi, eax
0x18001cb69  lea     eax, [r13+8]
0x18001cb6d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18001cb75  mov     ecx, r13d
0x18001cb78  cmovz   ecx, eax
0x18001cb7b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001cb7f  lea     ecx, [rax-7]
0x18001cb82  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001cb8a  inc     ecx
0x18001cb8c  mov     [rsp+14F0h+var_14B8], r13
0x18001cb91  mov     [rsp+14F0h+var_14C0], ecx
0x18001cb95  call    cs:__imp_GetCurrentThreadId
0x18001cb9b  xorps   xmm0, xmm0
0x18001cb9e  mov     [rsp+14F0h+var_1498], r15
0x18001cba3  mov     [rsp+14F0h+var_14B0], eax
0x18001cba7  xorps   xmm1, xmm1
0x18001cbaa  xor     eax, eax
0x18001cbac  mov     [rsp+14F0h+var_1490], r14d
0x18001cbb1  mov     [rbp+13F0h+var_1458], rax
0x18001cbb5  mov     [rbp+13F0h+var_1470], rax
0x18001cbb9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001cbc0  mov     [rsp+14F0h+var_148C], edi
0x18001cbc4  mov     [rsp+14F0h+var_14A8], r13
0x18001cbc9  mov     [rsp+14F0h+var_14A0], r13
0x18001cbce  mov     [rbp+13F0h+var_1448], rsi
0x18001cbd2  mov     [rbp+13F0h+var_1440], r12
0x18001cbd6  mov     [rsp+14F0h+var_1488], r13
0x18001cbdb  movups  [rbp+13F0h+var_1468], xmm0
0x18001cbdf  movups  [rsp+14F0h+var_1480], xmm1
0x18001cbe4  test    rax, rax
0x18001cbe7  jz      short loc_18001CBF4
0x18001cbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbee  mov     [rbp+13F0h+var_1450], rax
0x18001cbf2  jmp     short loc_18001CBF8
0x18001cbf4  mov     [rbp+13F0h+var_1450], r13
0x18001cbf8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001cbff  test    rax, rax
0x18001cc02  jz      short loc_18001CC0E
0x18001cc04  lea     rcx, [rsp+14F0h+var_14D0]
0x18001cc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc0e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001cc15  test    rax, rax
0x18001cc18  jz      short loc_18001CC2E
0x18001cc1a  mov     r8d, 400h
0x18001cc20  lea     rdx, [rbp+13F0h+var_1430]
0x18001cc24  lea     rcx, [rsp+14F0h+var_14D0]
0x18001cc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc2e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001cc35  test    rax, rax
0x18001cc38  jz      short loc_18001CC44
0x18001cc3a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001cc3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc44  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001cc4b  test    rax, rax
0x18001cc4e  jz      short loc_18001CC61
0x18001cc50  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001cc55  jnz     short loc_18001CC61
0x18001cc57  lea     rcx, [rsp+14F0h+var_14D0]
0x18001cc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc61  cmp     [rsp+14F0h+var_14C8], r13d
0x18001cc66  jl      short loc_18001CC7A
0x18001cc68  mov     ecx, 8000FFFFh; this
0x18001cc6d  mov     [rsp+14F0h+var_14C8], ecx
0x18001cc71  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001cc76  mov     [rsp+14F0h+var_14C4], eax
0x18001cc7a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001cc81  jnz     short loc_18001CCA2
0x18001cc83  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001cc8a  test    rax, rax
0x18001cc8d  jz      short loc_18001CC98
0x18001cc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc94  test    al, al
0x18001cc96  jmp     short loc_18001CCA0
0x18001cc98  call    cs:__imp_IsDebuggerPresent
0x18001cc9e  test    eax, eax
0x18001cca0  jz      short loc_18001CCA9
0x18001cca2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001cca7  jz      short loc_18001CCCF
0x18001cca9  mov     rax, cs:g_pfnResultLoggingCallback
0x18001ccb0  test    rax, rax
0x18001ccb3  jz      short loc_18001CD28
0x18001ccb5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001ccbc  jnz     short loc_18001CD28
0x18001ccbe  xor     r8d, r8d
0x18001ccc1  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ccc6  xor     edx, edx
0x18001ccc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cccd  jmp     short loc_18001CD28
0x18001cccf  mov     rax, cs:g_pfnResultLoggingCallback
0x18001ccd6  mov     ebx, 800h
0x18001ccdb  test    rax, rax
0x18001ccde  jz      short loc_18001CCFD
0x18001cce0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001cce7  jnz     short loc_18001CCFD
0x18001cce9  mov     r8d, ebx
0x18001ccec  lea     rdx, [rbp+13F0h+OutputString]
0x18001ccf3  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ccf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccfd  cmp     [rbp+13F0h+OutputString], r13w
0x18001cd05  jnz     short loc_18001CD1B
0x18001cd07  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001cd0c  mov     rdx, rbx; unsigned __int16 *
0x18001cd0f  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001cd16  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001cd1b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001cd22  call    cs:__imp_OutputDebugStringW
0x18001cd28  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001cd2d  jnz     short loc_18001CD38
0x18001cd2f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001cd36  jz      short loc_18001CD49
0x18001cd38  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001cd3f  test    rax, rax
0x18001cd42  jz      short loc_18001CD49
0x18001cd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd49  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001cd4e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
