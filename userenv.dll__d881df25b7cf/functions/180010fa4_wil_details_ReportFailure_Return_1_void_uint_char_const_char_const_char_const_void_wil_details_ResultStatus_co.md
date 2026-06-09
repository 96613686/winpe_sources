# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180010fa4`
- end: `0x18001125d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180010d94`

## callees

- `0x18000e640`
- `0x18000efe0`
- `0x1800100d4`
- `0x180010fa4`
- `0x1800120d0`
- `0x1800126a4`
- `0x180012780`
- `0x18001c7a0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001106a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001106a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011165`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011165`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800111f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800111f5`

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
0x180010fa4  push    rbp
0x180010fa6  push    rbx
0x180010fa7  push    rsi
0x180010fa8  push    rdi
0x180010fa9  push    r12
0x180010fab  push    r14
0x180010fad  push    r15
0x180010faf  lea     rbp, [rsp-13D0h]
0x180010fb7  mov     eax, 14D0h
0x180010fbc  call    _alloca_probe
0x180010fc1  sub     rsp, rax
0x180010fc4  mov     rax, cs:__security_cookie
0x180010fcb  xor     rax, rsp
0x180010fce  mov     [rbp+1400h+var_40], rax
0x180010fd5  mov     rsi, r8
0x180010fd8  mov     edi, edx
0x180010fda  mov     rbx, rcx
0x180010fdd  mov     r14, [rbp+1400h+arg_28]
0x180010fe4  xor     edx, edx; Val
0x180010fe6  mov     r8d, 98h; Size
0x180010fec  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180010ff1  call    memset_0
0x180010ff6  nop
0x180010ff7  xor     r12d, r12d
0x180010ffa  mov     [rbp+1400h+OutputString], r12w
0x180011002  mov     [rbp+1400h+var_1440], r12b
0x180011006  mov     rdx, [rbp+1400h+arg_30]; int
0x18001100d  mov     ecx, [rdx]; this
0x18001100f  mov     [rsp+1500h+var_14D8], ecx
0x180011013  mov     eax, [rdx+4]
0x180011016  mov     [rsp+1500h+var_14D4], eax
0x18001101a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001101f  mov     r15d, eax
0x180011022  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18001102a  mov     ecx, r12d
0x18001102d  lea     eax, [r12+8]
0x180011032  cmp     dword ptr [rdx+8], 1
0x180011036  cmovz   ecx, eax
0x180011039  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18001103d  lea     ecx, [rax-7]
0x180011040  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011048  inc     ecx
0x18001104a  mov     [rsp+1500h+var_14D0], ecx
0x18001104e  mov     rcx, [rbp+1400h+arg_38]
0x180011055  test    rcx, rcx
0x180011058  jz      short loc_180011065
0x18001105a  cmp     [rcx], r12w
0x18001105e  mov     [rsp+1500h+var_14C8], rcx
0x180011063  jnz     short loc_18001106A
0x180011065  mov     [rsp+1500h+var_14C8], r12
0x18001106a  call    cs:__imp_GetCurrentThreadId
0x180011071  nop     dword ptr [rax+rax+00h]
0x180011076  mov     [rsp+1500h+var_14C0], eax
0x18001107a  mov     [rsp+1500h+var_14A8], rsi
0x18001107f  mov     [rsp+1500h+var_14A0], edi
0x180011083  mov     [rsp+1500h+var_149C], r15d
0x180011088  mov     [rsp+1500h+var_14B8], r12
0x18001108d  mov     [rsp+1500h+var_14B0], r12
0x180011092  mov     [rbp+1400h+var_1458], r14
0x180011096  mov     [rbp+1400h+var_1450], rbx
0x18001109a  mov     [rsp+1500h+var_1498], r12
0x18001109f  xorps   xmm0, xmm0
0x1800110a2  xor     eax, eax
0x1800110a4  movups  [rbp+1400h+var_1478], xmm0
0x1800110a8  mov     [rbp+1400h+var_1468], rax
0x1800110ac  xorps   xmm1, xmm1
0x1800110af  movups  [rsp+1500h+var_1490], xmm1
0x1800110b4  mov     [rbp+1400h+var_1480], rax
0x1800110b8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800110bf  test    rax, rax
0x1800110c2  jz      short loc_1800110CF
0x1800110c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110c9  mov     [rbp+1400h+var_1460], rax
0x1800110cd  jmp     short loc_1800110D3
0x1800110cf  mov     [rbp+1400h+var_1460], r12
0x1800110d3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800110da  test    rax, rax
0x1800110dd  jz      short loc_1800110E9
0x1800110df  lea     rcx, [rsp+1500h+var_14E0]
0x1800110e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800110f0  test    rax, rax
0x1800110f3  jz      short loc_180011109
0x1800110f5  mov     r8d, 400h
0x1800110fb  lea     rdx, [rbp+1400h+var_1440]
0x1800110ff  lea     rcx, [rsp+1500h+var_14E0]
0x180011104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011109  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011110  test    rax, rax
0x180011113  jz      short loc_18001111F
0x180011115  lea     rcx, [rsp+1500h+var_14E0]
0x18001111a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001111f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011126  test    rax, rax
0x180011129  jz      short loc_18001113C
0x18001112b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180011130  jnz     short loc_18001113C
0x180011132  lea     rcx, [rsp+1500h+var_14E0]
0x180011137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001113c  cmp     [rsp+1500h+var_14D8], r12d
0x180011141  jge     loc_180011257
0x180011147  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18001114e  jnz     short loc_180011175
0x180011150  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011157  test    rax, rax
0x18001115a  jz      short loc_180011165
0x18001115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011161  test    al, al
0x180011163  jmp     short loc_180011173
0x180011165  call    cs:__imp_IsDebuggerPresent
0x18001116c  nop     dword ptr [rax+rax+00h]
0x180011171  test    eax, eax
0x180011173  jz      short loc_18001117C
0x180011175  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001117a  jz      short loc_1800111A2
0x18001117c  mov     rax, cs:g_pfnResultLoggingCallback
0x180011183  test    rax, rax
0x180011186  jz      short loc_180011201
0x180011188  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001118f  jnz     short loc_180011201
0x180011191  xor     r8d, r8d
0x180011194  xor     edx, edx
0x180011196  lea     rcx, [rsp+1500h+var_14E0]
0x18001119b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111a0  jmp     short loc_180011201
0x1800111a2  mov     ebx, 800h
0x1800111a7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800111ae  test    rax, rax
0x1800111b1  jz      short loc_1800111D0
0x1800111b3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800111ba  jnz     short loc_1800111D0
0x1800111bc  mov     r8d, ebx
0x1800111bf  lea     rdx, [rbp+1400h+OutputString]
0x1800111c6  lea     rcx, [rsp+1500h+var_14E0]
0x1800111cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111d0  cmp     [rbp+1400h+OutputString], r12w
0x1800111d8  jnz     short loc_1800111EE
0x1800111da  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800111df  mov     rdx, rbx; unsigned __int16 *
0x1800111e2  lea     rcx, [rbp+1400h+OutputString]; this
0x1800111e9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800111ee  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800111f5  call    cs:__imp_OutputDebugStringW
0x1800111fc  nop     dword ptr [rax+rax+00h]
0x180011201  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180011206  jnz     short loc_180011211
0x180011208  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18001120f  jz      short loc_180011223
0x180011211  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011218  test    rax, rax
0x18001121b  jz      short loc_180011223
0x18001121d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011222  nop
0x180011223  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180011228  jnz     short loc_18001124C
0x18001122a  mov     rcx, [rbp+1400h+var_40]
0x180011231  xor     rcx, rsp; StackCookie
0x180011234  call    __security_check_cookie
0x180011239  add     rsp, 14D0h
0x180011240  pop     r15
0x180011242  pop     r14
0x180011244  pop     r12
0x180011246  pop     rdi
0x180011247  pop     rsi
0x180011248  pop     rbx
0x180011249  pop     rbp
0x18001124a  retn
0x18001124c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180011251  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180011257  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
