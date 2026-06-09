# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800370e8`
- end: `0x180037375`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002b310`

## callees

- `0x180035590`
- `0x1800361ba`
- `0x1800370e8`
- `0x180037bd4`
- `0x1800386b0`
- `0x180038d88`
- `0x180038e64`
- `0x180075530`
- `0x180078010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180037314`
- `KERNEL32!OutputDebugStringW` at `0x180037314`
- `KERNEL32!IsDebuggerPresent` at `0x18003728a`
- `KERNEL32!IsDebuggerPresent` at `0x18003728a`
- `KERNEL32!GetCurrentThreadId` at `0x180037196`
- `KERNEL32!GetCurrentThreadId` at `0x180037196`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800370e8  push    rbp
0x1800370ea  push    rbx
0x1800370eb  push    rsi
0x1800370ec  push    rdi
0x1800370ed  push    r12
0x1800370ef  push    r14
0x1800370f1  push    r15
0x1800370f3  lea     rbp, [rsp-13D0h]
0x1800370fb  mov     eax, 14D0h
0x180037100  call    _alloca_probe
0x180037105  sub     rsp, rax
0x180037108  mov     rax, cs:__security_cookie
0x18003710f  xor     rax, rsp
0x180037112  mov     [rbp+1400h+var_40], rax
0x180037119  mov     r14, r8
0x18003711c  mov     esi, edx
0x18003711e  mov     r15, rcx
0x180037121  mov     rdi, [rbp+1400h+arg_28]
0x180037128  xor     edx, edx; Val
0x18003712a  mov     r8d, 98h; Size
0x180037130  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180037135  call    memset_0
0x18003713a  nop
0x18003713b  xor     r12d, r12d
0x18003713e  mov     [rbp+1400h+OutputString], r12w
0x180037146  mov     [rbp+1400h+var_1440], r12b
0x18003714a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180037151  mov     ecx, [rdx]; this
0x180037153  mov     [rsp+1500h+var_14D8], ecx
0x180037157  mov     eax, [rdx+4]
0x18003715a  mov     [rsp+1500h+var_14D4], eax
0x18003715e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180037163  mov     ebx, eax
0x180037165  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18003716d  mov     ecx, r12d
0x180037170  lea     eax, [r12+8]
0x180037175  cmp     dword ptr [rdx+8], 1
0x180037179  cmovz   ecx, eax
0x18003717c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180037180  lea     ecx, [rax-7]
0x180037183  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003718b  inc     ecx
0x18003718d  mov     [rsp+1500h+var_14D0], ecx
0x180037191  mov     [rsp+1500h+var_14C8], r12
0x180037196  call    cs:__imp_GetCurrentThreadId
0x18003719c  mov     [rsp+1500h+var_14C0], eax
0x1800371a0  mov     [rsp+1500h+var_14A8], r14
0x1800371a5  mov     [rsp+1500h+var_14A0], esi
0x1800371a9  mov     [rsp+1500h+var_149C], ebx
0x1800371ad  mov     [rsp+1500h+var_14B8], r12
0x1800371b2  mov     [rsp+1500h+var_14B0], r12
0x1800371b7  mov     [rbp+1400h+var_1458], rdi
0x1800371bb  mov     [rbp+1400h+var_1450], r15
0x1800371bf  mov     [rsp+1500h+var_1498], r12
0x1800371c4  xorps   xmm0, xmm0
0x1800371c7  xor     eax, eax
0x1800371c9  movups  [rbp+1400h+var_1478], xmm0
0x1800371cd  mov     [rbp+1400h+var_1468], rax
0x1800371d1  xorps   xmm1, xmm1
0x1800371d4  movups  [rsp+1500h+var_1490], xmm1
0x1800371d9  mov     [rbp+1400h+var_1480], rax
0x1800371dd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800371e4  test    rax, rax
0x1800371e7  jz      short loc_1800371F4
0x1800371e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371ee  mov     [rbp+1400h+var_1460], rax
0x1800371f2  jmp     short loc_1800371F8
0x1800371f4  mov     [rbp+1400h+var_1460], r12
0x1800371f8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800371ff  test    rax, rax
0x180037202  jz      short loc_18003720E
0x180037204  lea     rcx, [rsp+1500h+var_14E0]
0x180037209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003720e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180037215  test    rax, rax
0x180037218  jz      short loc_18003722E
0x18003721a  mov     r8d, 400h
0x180037220  lea     rdx, [rbp+1400h+var_1440]
0x180037224  lea     rcx, [rsp+1500h+var_14E0]
0x180037229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003722e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180037235  test    rax, rax
0x180037238  jz      short loc_180037244
0x18003723a  lea     rcx, [rsp+1500h+var_14E0]
0x18003723f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037244  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003724b  test    rax, rax
0x18003724e  jz      short loc_180037261
0x180037250  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180037255  jnz     short loc_180037261
0x180037257  lea     rcx, [rsp+1500h+var_14E0]
0x18003725c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037261  cmp     [rsp+1500h+var_14D8], r12d
0x180037266  jge     loc_18003736F
0x18003726c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180037273  jnz     short loc_180037294
0x180037275  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003727c  test    rax, rax
0x18003727f  jz      short loc_18003728A
0x180037281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037286  test    al, al
0x180037288  jmp     short loc_180037292
0x18003728a  call    cs:__imp_IsDebuggerPresent
0x180037290  test    eax, eax
0x180037292  jz      short loc_18003729B
0x180037294  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180037299  jz      short loc_1800372C1
0x18003729b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800372a2  test    rax, rax
0x1800372a5  jz      short loc_18003731A
0x1800372a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800372ae  jnz     short loc_18003731A
0x1800372b0  xor     r8d, r8d
0x1800372b3  xor     edx, edx
0x1800372b5  lea     rcx, [rsp+1500h+var_14E0]
0x1800372ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372bf  jmp     short loc_18003731A
0x1800372c1  mov     ebx, 800h
0x1800372c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800372cd  test    rax, rax
0x1800372d0  jz      short loc_1800372EF
0x1800372d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800372d9  jnz     short loc_1800372EF
0x1800372db  mov     r8d, ebx
0x1800372de  lea     rdx, [rbp+1400h+OutputString]
0x1800372e5  lea     rcx, [rsp+1500h+var_14E0]
0x1800372ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372ef  cmp     [rbp+1400h+OutputString], r12w
0x1800372f7  jnz     short loc_18003730D
0x1800372f9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800372fe  mov     rdx, rbx; unsigned __int16 *
0x180037301  lea     rcx, [rbp+1400h+OutputString]; this
0x180037308  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003730d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180037314  call    cs:__imp_OutputDebugStringW
0x18003731a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18003731f  jnz     short loc_18003732A
0x180037321  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180037328  jz      short loc_18003733C
0x18003732a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180037331  test    rax, rax
0x180037334  jz      short loc_18003733C
0x180037336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003733b  nop
0x18003733c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180037341  jnz     short loc_180037364
0x180037343  mov     rcx, [rbp+1400h+var_40]
0x18003734a  xor     rcx, rsp; StackCookie
0x18003734d  call    __security_check_cookie
0x180037352  add     rsp, 14D0h
0x180037359  pop     r15
0x18003735b  pop     r14
0x18003735d  pop     r12
0x18003735f  pop     rdi
0x180037360  pop     rsi
0x180037361  pop     rbx
0x180037362  pop     rbp
0x180037363  retn
0x180037364  lea     rcx, [rsp+1500h+var_14E0]; this
0x180037369  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18003736f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
