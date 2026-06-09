# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400090d4`
- end: `0x14000934d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140008e44`

## callees

- `0x140006314`
- `0x1400090d4`
- `0x140011cc8`
- `0x140012910`
- `0x140014f50`
- `0x140019420`
- `0x14009d330`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140009290`
- `KERNEL32!IsDebuggerPresent` at `0x140009290`
- `KERNEL32!OutputDebugStringW` at `0x14000931a`
- `KERNEL32!OutputDebugStringW` at `0x14000931a`
- `KERNEL32!GetCurrentThreadId` at `0x14000918d`
- `KERNEL32!GetCurrentThreadId` at `0x14000918d`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
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
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1400090d4  mov     [rsp-8+arg_18], rbx
0x1400090d9  push    rbp
0x1400090da  push    rsi
0x1400090db  push    rdi
0x1400090dc  push    r12
0x1400090de  push    r13
0x1400090e0  push    r14
0x1400090e2  push    r15
0x1400090e4  lea     rbp, [rsp-13C0h]
0x1400090ec  mov     eax, 14C0h
0x1400090f1  call    _alloca_probe
0x1400090f6  sub     rsp, rax
0x1400090f9  mov     r14, r8
0x1400090fc  mov     esi, edx
0x1400090fe  mov     rdi, rcx
0x140009101  mov     r15, [rbp+13F0h+arg_28]
0x140009108  xor     edx, edx; Val
0x14000910a  mov     r8d, 98h; Size
0x140009110  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140009115  call    memset_0
0x14000911a  nop
0x14000911b  xor     r13d, r13d
0x14000911e  mov     [rbp+13F0h+OutputString], r13w
0x140009126  mov     [rbp+13F0h+var_1430], r13b
0x14000912a  mov     rbx, [rbp+13F0h+arg_30]
0x140009131  mov     ecx, [rbx]; this
0x140009133  mov     [rsp+14F0h+var_14C8], ecx
0x140009137  mov     eax, [rbx+4]
0x14000913a  mov     [rsp+14F0h+var_14C4], eax
0x14000913e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140009143  mov     r12d, eax
0x140009146  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000914e  mov     ecx, r13d
0x140009151  lea     eax, [r13+8]
0x140009155  cmp     dword ptr [rbx+8], 1
0x140009159  cmovz   ecx, eax
0x14000915c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140009160  lea     ecx, [rax-7]
0x140009163  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000916b  inc     ecx
0x14000916d  mov     [rsp+14F0h+var_14C0], ecx
0x140009171  mov     rcx, [rbp+13F0h+arg_38]
0x140009178  test    rcx, rcx
0x14000917b  jz      short loc_140009188
0x14000917d  cmp     [rcx], r13w
0x140009181  mov     [rsp+14F0h+var_14B8], rcx
0x140009186  jnz     short loc_14000918D
0x140009188  mov     [rsp+14F0h+var_14B8], r13
0x14000918d  call    cs:__imp_GetCurrentThreadId
0x140009193  mov     [rsp+14F0h+var_14B0], eax
0x140009197  mov     [rsp+14F0h+var_1498], r14
0x14000919c  mov     [rsp+14F0h+var_1490], esi
0x1400091a0  mov     [rsp+14F0h+var_148C], r12d
0x1400091a5  mov     [rsp+14F0h+var_14A8], r13
0x1400091aa  mov     [rsp+14F0h+var_14A0], r13
0x1400091af  mov     [rbp+13F0h+var_1448], r15
0x1400091b3  mov     [rbp+13F0h+var_1440], rdi
0x1400091b7  mov     [rsp+14F0h+var_1488], r13
0x1400091bc  xorps   xmm0, xmm0
0x1400091bf  xor     eax, eax
0x1400091c1  movups  [rbp+13F0h+var_1468], xmm0
0x1400091c5  mov     [rbp+13F0h+var_1458], rax
0x1400091c9  xorps   xmm1, xmm1
0x1400091cc  movups  [rsp+14F0h+var_1480], xmm1
0x1400091d1  mov     [rbp+13F0h+var_1470], rax
0x1400091d5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400091dc  test    rax, rax
0x1400091df  jz      short loc_1400091EC
0x1400091e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091e6  mov     [rbp+13F0h+var_1450], rax
0x1400091ea  jmp     short loc_1400091F0
0x1400091ec  mov     [rbp+13F0h+var_1450], r13
0x1400091f0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400091f7  test    rax, rax
0x1400091fa  jz      short loc_140009206
0x1400091fc  lea     rcx, [rsp+14F0h+var_14D0]
0x140009201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009206  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000920d  test    rax, rax
0x140009210  jz      short loc_140009226
0x140009212  mov     r8d, 400h
0x140009218  lea     rdx, [rbp+13F0h+var_1430]
0x14000921c  lea     rcx, [rsp+14F0h+var_14D0]
0x140009221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009226  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000922d  test    rax, rax
0x140009230  jz      short loc_14000923C
0x140009232  lea     rcx, [rsp+14F0h+var_14D0]
0x140009237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000923c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009243  test    rax, rax
0x140009246  jz      short loc_140009259
0x140009248  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000924d  jnz     short loc_140009259
0x14000924f  lea     rcx, [rsp+14F0h+var_14D0]
0x140009254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009259  cmp     [rsp+14F0h+var_14C8], r13d
0x14000925e  jl      short loc_140009272
0x140009260  mov     ecx, 8000FFFFh; this
0x140009265  mov     [rsp+14F0h+var_14C8], ecx
0x140009269  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000926e  mov     [rsp+14F0h+var_14C4], eax
0x140009272  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140009279  jnz     short loc_14000929A
0x14000927b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140009282  test    rax, rax
0x140009285  jz      short loc_140009290
0x140009287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000928c  test    al, al
0x14000928e  jmp     short loc_140009298
0x140009290  call    cs:__imp_IsDebuggerPresent
0x140009296  test    eax, eax
0x140009298  jz      short loc_1400092A1
0x14000929a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000929f  jz      short loc_1400092C7
0x1400092a1  mov     rax, cs:g_pfnResultLoggingCallback
0x1400092a8  test    rax, rax
0x1400092ab  jz      short loc_140009320
0x1400092ad  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400092b4  jnz     short loc_140009320
0x1400092b6  xor     r8d, r8d
0x1400092b9  xor     edx, edx
0x1400092bb  lea     rcx, [rsp+14F0h+var_14D0]
0x1400092c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092c5  jmp     short loc_140009320
0x1400092c7  mov     ebx, 800h
0x1400092cc  mov     rax, cs:g_pfnResultLoggingCallback
0x1400092d3  test    rax, rax
0x1400092d6  jz      short loc_1400092F5
0x1400092d8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400092df  jnz     short loc_1400092F5
0x1400092e1  mov     r8d, ebx
0x1400092e4  lea     rdx, [rbp+13F0h+OutputString]
0x1400092eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1400092f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092f5  cmp     [rbp+13F0h+OutputString], r13w
0x1400092fd  jnz     short loc_140009313
0x1400092ff  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140009304  mov     rdx, rbx; unsigned __int16 *
0x140009307  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000930e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140009313  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000931a  call    cs:__imp_OutputDebugStringW
0x140009320  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140009325  jnz     short loc_140009330
0x140009327  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000932e  jz      short loc_140009342
0x140009330  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140009337  test    rax, rax
0x14000933a  jz      short loc_140009342
0x14000933c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009341  nop
0x140009342  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140009347  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
