# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009680`
- end: `0x180009927`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009144`

## callees

- `0x180009680`
- `0x18000b8f0`
- `0x18000d67c`
- `0x18001084c`
- `0x180010a38`
- `0x180011a62`
- `0x180011a90`
- `0x180011b50`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000972a`
- `KERNEL32!GetCurrentThreadId` at `0x18000972a`
- `KERNEL32!IsDebuggerPresent` at `0x18000982b`
- `KERNEL32!IsDebuggerPresent` at `0x18000982b`
- `KERNEL32!OutputDebugStringW` at `0x1800098bb`
- `KERNEL32!OutputDebugStringW` at `0x1800098bb`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180009680  mov     [rsp-8+arg_10], rbx
0x180009685  push    rbp
0x180009686  push    rsi
0x180009687  push    rdi
0x180009688  push    r14
0x18000968a  push    r15
0x18000968c  lea     rbp, [rsp-13D0h]
0x180009694  mov     eax, 14D0h
0x180009699  call    _alloca_probe
0x18000969e  sub     rsp, rax
0x1800096a1  mov     rax, cs:__security_cookie
0x1800096a8  xor     rax, rsp
0x1800096ab  mov     [rbp+13F0h+var_30], rax
0x1800096b2  mov     rdi, [rbp+13F0h+arg_28]
0x1800096b9  mov     esi, edx
0x1800096bb  mov     r14, rcx
0x1800096be  xor     edx, edx; Val
0x1800096c0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800096c5  mov     r8d, 98h; Size
0x1800096cb  call    memset_0
0x1800096d0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800096d7  xor     r15d, r15d
0x1800096da  mov     [rbp+13F0h+OutputString], r15w
0x1800096e2  mov     [rbp+13F0h+var_1430], r15b
0x1800096e6  mov     ecx, [rdx]; this
0x1800096e8  mov     eax, [rdx+4]
0x1800096eb  mov     [rsp+14F0h+var_14C8], ecx
0x1800096ef  mov     [rsp+14F0h+var_14C4], eax
0x1800096f3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800096f8  cmp     dword ptr [rdx+8], 1
0x1800096fc  mov     ebx, eax
0x1800096fe  lea     eax, [r15+8]
0x180009702  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000970a  mov     ecx, r15d
0x18000970d  cmovz   ecx, eax
0x180009710  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009714  lea     ecx, [rax-7]
0x180009717  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000971f  inc     ecx
0x180009721  mov     [rsp+14F0h+var_14B8], r15
0x180009726  mov     [rsp+14F0h+var_14C0], ecx
0x18000972a  call    cs:__imp_GetCurrentThreadId
0x180009731  nop     dword ptr [rax+rax+00h]
0x180009736  xorps   xmm0, xmm0
0x180009739  mov     [rsp+14F0h+var_1490], esi
0x18000973d  mov     [rsp+14F0h+var_14B0], eax
0x180009741  xorps   xmm1, xmm1
0x180009744  lea     rax, aWil; "wil"
0x18000974b  mov     [rsp+14F0h+var_148C], ebx
0x18000974f  mov     [rsp+14F0h+var_1498], rax
0x180009754  xor     eax, eax
0x180009756  mov     [rbp+13F0h+var_1458], rax
0x18000975a  mov     [rbp+13F0h+var_1470], rax
0x18000975e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009765  mov     [rsp+14F0h+var_14A8], r15
0x18000976a  mov     [rsp+14F0h+var_14A0], r15
0x18000976f  mov     [rbp+13F0h+var_1448], rdi
0x180009773  mov     [rbp+13F0h+var_1440], r14
0x180009777  mov     [rsp+14F0h+var_1488], r15
0x18000977c  movups  [rbp+13F0h+var_1468], xmm0
0x180009780  movups  [rsp+14F0h+var_1480], xmm1
0x180009785  test    rax, rax
0x180009788  jz      short loc_180009795
0x18000978a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000978f  mov     [rbp+13F0h+var_1450], rax
0x180009793  jmp     short loc_180009799
0x180009795  mov     [rbp+13F0h+var_1450], r15
0x180009799  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800097a0  test    rax, rax
0x1800097a3  jz      short loc_1800097AF
0x1800097a5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800097aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097af  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800097b6  test    rax, rax
0x1800097b9  jz      short loc_1800097CF
0x1800097bb  mov     r8d, 400h
0x1800097c1  lea     rdx, [rbp+13F0h+var_1430]
0x1800097c5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800097ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097cf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800097d6  test    rax, rax
0x1800097d9  jz      short loc_1800097E5
0x1800097db  lea     rcx, [rsp+14F0h+var_14D0]
0x1800097e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097e5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800097ec  test    rax, rax
0x1800097ef  jz      short loc_180009802
0x1800097f1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800097f6  jnz     short loc_180009802
0x1800097f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800097fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009802  cmp     [rsp+14F0h+var_14C8], r15d
0x180009807  jge     loc_180009916
0x18000980d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180009814  jnz     short loc_18000983B
0x180009816  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000981d  test    rax, rax
0x180009820  jz      short loc_18000982B
0x180009822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009827  test    al, al
0x180009829  jmp     short loc_180009839
0x18000982b  call    cs:__imp_IsDebuggerPresent
0x180009832  nop     dword ptr [rax+rax+00h]
0x180009837  test    eax, eax
0x180009839  jz      short loc_180009842
0x18000983b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009840  jz      short loc_180009868
0x180009842  mov     rax, cs:g_pfnResultLoggingCallback
0x180009849  test    rax, rax
0x18000984c  jz      short loc_1800098C7
0x18000984e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009855  jnz     short loc_1800098C7
0x180009857  xor     r8d, r8d
0x18000985a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000985f  xor     edx, edx
0x180009861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009866  jmp     short loc_1800098C7
0x180009868  mov     rax, cs:g_pfnResultLoggingCallback
0x18000986f  mov     ebx, 800h
0x180009874  test    rax, rax
0x180009877  jz      short loc_180009896
0x180009879  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009880  jnz     short loc_180009896
0x180009882  mov     r8d, ebx
0x180009885  lea     rdx, [rbp+13F0h+OutputString]
0x18000988c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009896  cmp     [rbp+13F0h+OutputString], r15w
0x18000989e  jnz     short loc_1800098B4
0x1800098a0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800098a5  mov     rdx, rbx; unsigned __int16 *
0x1800098a8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800098af  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800098b4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800098bb  call    cs:__imp_OutputDebugStringW
0x1800098c2  nop     dword ptr [rax+rax+00h]
0x1800098c7  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800098cc  jnz     short loc_1800098D7
0x1800098ce  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800098d5  jz      short loc_1800098E8
0x1800098d7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800098de  test    rax, rax
0x1800098e1  jz      short loc_1800098E8
0x1800098e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e8  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800098ed  jnz     short loc_18000991C
0x1800098ef  mov     rcx, [rbp+13F0h+var_30]
0x1800098f6  xor     rcx, rsp; StackCookie
0x1800098f9  call    __security_check_cookie
0x1800098fe  mov     rbx, [rsp+14F0h+arg_10]
0x180009906  add     rsp, 14D0h
0x18000990d  pop     r15
0x18000990f  pop     r14
0x180009911  pop     rdi
0x180009912  pop     rsi
0x180009913  pop     rbp
0x180009914  retn
0x180009916  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000991c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009921  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
