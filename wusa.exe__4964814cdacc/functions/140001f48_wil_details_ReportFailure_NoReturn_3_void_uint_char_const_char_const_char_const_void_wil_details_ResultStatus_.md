# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140001f48`
- end: `0x1400021a8`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140001ce4`

## callees

- `0x140001a63`
- `0x140001f48`
- `0x1400030b4`
- `0x140003850`
- `0x140003f80`
- `0x140004860`
- `0x1400149a0`
- `0x140015010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400020ec`
- `KERNEL32!IsDebuggerPresent` at `0x1400020ec`
- `KERNEL32!OutputDebugStringW` at `0x140002176`
- `KERNEL32!OutputDebugStringW` at `0x140002176`
- `KERNEL32!GetCurrentThreadId` at `0x140001fe9`
- `KERNEL32!GetCurrentThreadId` at `0x140001fe9`

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
0x140001f48  mov     [rsp-8+arg_18], rbx
0x140001f4d  push    rbp
0x140001f4e  push    rsi
0x140001f4f  push    rdi
0x140001f50  push    r12
0x140001f52  push    r13
0x140001f54  push    r14
0x140001f56  push    r15
0x140001f58  lea     rbp, [rsp-13C0h]
0x140001f60  mov     eax, 14C0h
0x140001f65  call    _alloca_probe
0x140001f6a  sub     rsp, rax
0x140001f6d  mov     rsi, [rbp+13F0h+arg_28]
0x140001f74  mov     r15, r8
0x140001f77  mov     r14d, edx
0x140001f7a  mov     r12, rcx
0x140001f7d  xor     edx, edx; Val
0x140001f7f  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140001f84  mov     r8d, 98h; Size
0x140001f8a  call    memset_0
0x140001f8f  mov     rbx, [rbp+13F0h+arg_30]
0x140001f96  xor     r13d, r13d
0x140001f99  mov     [rbp+13F0h+OutputString], r13w
0x140001fa1  mov     [rbp+13F0h+var_1430], r13b
0x140001fa5  mov     ecx, [rbx]; this
0x140001fa7  mov     eax, [rbx+4]
0x140001faa  mov     [rsp+14F0h+var_14C8], ecx
0x140001fae  mov     [rsp+14F0h+var_14C4], eax
0x140001fb2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140001fb7  cmp     dword ptr [rbx+8], 1
0x140001fbb  mov     edi, eax
0x140001fbd  lea     eax, [r13+8]
0x140001fc1  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140001fc9  mov     ecx, r13d
0x140001fcc  cmovz   ecx, eax
0x140001fcf  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140001fd3  lea     ecx, [rax-7]
0x140001fd6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140001fde  inc     ecx
0x140001fe0  mov     [rsp+14F0h+var_14B8], r13
0x140001fe5  mov     [rsp+14F0h+var_14C0], ecx
0x140001fe9  call    cs:__imp_GetCurrentThreadId
0x140001fef  xorps   xmm0, xmm0
0x140001ff2  mov     [rsp+14F0h+var_1498], r15
0x140001ff7  mov     [rsp+14F0h+var_14B0], eax
0x140001ffb  xorps   xmm1, xmm1
0x140001ffe  xor     eax, eax
0x140002000  mov     [rsp+14F0h+var_1490], r14d
0x140002005  mov     [rbp+13F0h+var_1458], rax
0x140002009  mov     [rbp+13F0h+var_1470], rax
0x14000200d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002014  mov     [rsp+14F0h+var_148C], edi
0x140002018  mov     [rsp+14F0h+var_14A8], r13
0x14000201d  mov     [rsp+14F0h+var_14A0], r13
0x140002022  mov     [rbp+13F0h+var_1448], rsi
0x140002026  mov     [rbp+13F0h+var_1440], r12
0x14000202a  mov     [rsp+14F0h+var_1488], r13
0x14000202f  movups  [rbp+13F0h+var_1468], xmm0
0x140002033  movups  [rsp+14F0h+var_1480], xmm1
0x140002038  test    rax, rax
0x14000203b  jz      short loc_140002048
0x14000203d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002042  mov     [rbp+13F0h+var_1450], rax
0x140002046  jmp     short loc_14000204C
0x140002048  mov     [rbp+13F0h+var_1450], r13
0x14000204c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002053  test    rax, rax
0x140002056  jz      short loc_140002062
0x140002058  lea     rcx, [rsp+14F0h+var_14D0]
0x14000205d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002062  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002069  test    rax, rax
0x14000206c  jz      short loc_140002082
0x14000206e  mov     r8d, 400h
0x140002074  lea     rdx, [rbp+13F0h+var_1430]
0x140002078  lea     rcx, [rsp+14F0h+var_14D0]
0x14000207d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002082  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002089  test    rax, rax
0x14000208c  jz      short loc_140002098
0x14000208e  lea     rcx, [rsp+14F0h+var_14D0]
0x140002093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002098  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000209f  test    rax, rax
0x1400020a2  jz      short loc_1400020B5
0x1400020a4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400020a9  jnz     short loc_1400020B5
0x1400020ab  lea     rcx, [rsp+14F0h+var_14D0]
0x1400020b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020b5  cmp     [rsp+14F0h+var_14C8], r13d
0x1400020ba  jl      short loc_1400020CE
0x1400020bc  mov     ecx, 8000FFFFh; this
0x1400020c1  mov     [rsp+14F0h+var_14C8], ecx
0x1400020c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400020ca  mov     [rsp+14F0h+var_14C4], eax
0x1400020ce  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400020d5  jnz     short loc_1400020F6
0x1400020d7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400020de  test    rax, rax
0x1400020e1  jz      short loc_1400020EC
0x1400020e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020e8  test    al, al
0x1400020ea  jmp     short loc_1400020F4
0x1400020ec  call    cs:__imp_IsDebuggerPresent
0x1400020f2  test    eax, eax
0x1400020f4  jz      short loc_1400020FD
0x1400020f6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400020fb  jz      short loc_140002123
0x1400020fd  mov     rax, cs:g_pfnResultLoggingCallback
0x140002104  test    rax, rax
0x140002107  jz      short loc_14000217C
0x140002109  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002110  jnz     short loc_14000217C
0x140002112  xor     r8d, r8d
0x140002115  lea     rcx, [rsp+14F0h+var_14D0]
0x14000211a  xor     edx, edx
0x14000211c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002121  jmp     short loc_14000217C
0x140002123  mov     rax, cs:g_pfnResultLoggingCallback
0x14000212a  mov     ebx, 800h
0x14000212f  test    rax, rax
0x140002132  jz      short loc_140002151
0x140002134  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000213b  jnz     short loc_140002151
0x14000213d  mov     r8d, ebx
0x140002140  lea     rdx, [rbp+13F0h+OutputString]
0x140002147  lea     rcx, [rsp+14F0h+var_14D0]
0x14000214c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002151  cmp     [rbp+13F0h+OutputString], r13w
0x140002159  jnz     short loc_14000216F
0x14000215b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002160  mov     rdx, rbx; unsigned __int16 *
0x140002163  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000216a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000216f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002176  call    cs:__imp_OutputDebugStringW
0x14000217c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002181  jnz     short loc_14000218C
0x140002183  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000218a  jz      short loc_14000219D
0x14000218c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002193  test    rax, rax
0x140002196  jz      short loc_14000219D
0x140002198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000219d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400021a2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
