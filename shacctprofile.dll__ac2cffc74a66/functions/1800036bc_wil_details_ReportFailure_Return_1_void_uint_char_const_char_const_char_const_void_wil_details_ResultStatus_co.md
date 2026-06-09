# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800036bc`
- end: `0x180003950`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800031a4`

## callees

- `0x180002230`
- `0x180002b8e`
- `0x1800036bc`
- `0x1800044d4`
- `0x1800053c0`
- `0x180005cd0`
- `0x180005dac`
- `0x1800096d0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003766`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003766`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800038eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800038eb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003861`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003861`

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
0x1800036bc  mov     [rsp-8+arg_10], rbx
0x1800036c1  push    rbp
0x1800036c2  push    rsi
0x1800036c3  push    rdi
0x1800036c4  push    r14
0x1800036c6  push    r15
0x1800036c8  lea     rbp, [rsp-13D0h]
0x1800036d0  mov     eax, 14D0h
0x1800036d5  call    _alloca_probe
0x1800036da  sub     rsp, rax
0x1800036dd  mov     rax, cs:__security_cookie
0x1800036e4  xor     rax, rsp
0x1800036e7  mov     [rbp+13F0h+var_30], rax
0x1800036ee  mov     rdi, [rbp+13F0h+arg_28]
0x1800036f5  mov     esi, edx
0x1800036f7  mov     r14, rcx
0x1800036fa  xor     edx, edx; Val
0x1800036fc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003701  mov     r8d, 98h; Size
0x180003707  call    memset_0
0x18000370c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003713  xor     r15d, r15d
0x180003716  mov     [rbp+13F0h+OutputString], r15w
0x18000371e  mov     [rbp+13F0h+var_1430], r15b
0x180003722  mov     ecx, [rdx]; this
0x180003724  mov     eax, [rdx+4]
0x180003727  mov     [rsp+14F0h+var_14C8], ecx
0x18000372b  mov     [rsp+14F0h+var_14C4], eax
0x18000372f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003734  cmp     dword ptr [rdx+8], 1
0x180003738  mov     ebx, eax
0x18000373a  lea     eax, [r15+8]
0x18000373e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003746  mov     ecx, r15d
0x180003749  cmovz   ecx, eax
0x18000374c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003750  lea     ecx, [rax-7]
0x180003753  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000375b  inc     ecx
0x18000375d  mov     [rsp+14F0h+var_14B8], r15
0x180003762  mov     [rsp+14F0h+var_14C0], ecx
0x180003766  call    cs:__imp_GetCurrentThreadId
0x18000376c  xorps   xmm0, xmm0
0x18000376f  mov     [rsp+14F0h+var_1490], esi
0x180003773  mov     [rsp+14F0h+var_14B0], eax
0x180003777  xorps   xmm1, xmm1
0x18000377a  lea     rax, aWil; "wil"
0x180003781  mov     [rsp+14F0h+var_148C], ebx
0x180003785  mov     [rsp+14F0h+var_1498], rax
0x18000378a  xor     eax, eax
0x18000378c  mov     [rbp+13F0h+var_1458], rax
0x180003790  mov     [rbp+13F0h+var_1470], rax
0x180003794  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000379b  mov     [rsp+14F0h+var_14A8], r15
0x1800037a0  mov     [rsp+14F0h+var_14A0], r15
0x1800037a5  mov     [rbp+13F0h+var_1448], rdi
0x1800037a9  mov     [rbp+13F0h+var_1440], r14
0x1800037ad  mov     [rsp+14F0h+var_1488], r15
0x1800037b2  movups  [rbp+13F0h+var_1468], xmm0
0x1800037b6  movups  [rsp+14F0h+var_1480], xmm1
0x1800037bb  test    rax, rax
0x1800037be  jz      short loc_1800037CB
0x1800037c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c5  mov     [rbp+13F0h+var_1450], rax
0x1800037c9  jmp     short loc_1800037CF
0x1800037cb  mov     [rbp+13F0h+var_1450], r15
0x1800037cf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800037d6  test    rax, rax
0x1800037d9  jz      short loc_1800037E5
0x1800037db  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800037ec  test    rax, rax
0x1800037ef  jz      short loc_180003805
0x1800037f1  mov     r8d, 400h
0x1800037f7  lea     rdx, [rbp+13F0h+var_1430]
0x1800037fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180003800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003805  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000380c  test    rax, rax
0x18000380f  jz      short loc_18000381B
0x180003811  lea     rcx, [rsp+14F0h+var_14D0]
0x180003816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003822  test    rax, rax
0x180003825  jz      short loc_180003838
0x180003827  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000382c  jnz     short loc_180003838
0x18000382e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003838  cmp     [rsp+14F0h+var_14C8], r15d
0x18000383d  jge     loc_18000393F
0x180003843  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000384a  jnz     short loc_18000386B
0x18000384c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003853  test    rax, rax
0x180003856  jz      short loc_180003861
0x180003858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000385d  test    al, al
0x18000385f  jmp     short loc_180003869
0x180003861  call    cs:__imp_IsDebuggerPresent
0x180003867  test    eax, eax
0x180003869  jz      short loc_180003872
0x18000386b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003870  jz      short loc_180003898
0x180003872  mov     rax, cs:g_pfnResultLoggingCallback
0x180003879  test    rax, rax
0x18000387c  jz      short loc_1800038F1
0x18000387e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003885  jnz     short loc_1800038F1
0x180003887  xor     r8d, r8d
0x18000388a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000388f  xor     edx, edx
0x180003891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003896  jmp     short loc_1800038F1
0x180003898  mov     rax, cs:g_pfnResultLoggingCallback
0x18000389f  mov     ebx, 800h
0x1800038a4  test    rax, rax
0x1800038a7  jz      short loc_1800038C6
0x1800038a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800038b0  jnz     short loc_1800038C6
0x1800038b2  mov     r8d, ebx
0x1800038b5  lea     rdx, [rbp+13F0h+OutputString]
0x1800038bc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c6  cmp     [rbp+13F0h+OutputString], r15w
0x1800038ce  jnz     short loc_1800038E4
0x1800038d0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800038d5  mov     rdx, rbx; unsigned __int16 *
0x1800038d8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800038df  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800038e4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800038eb  call    cs:__imp_OutputDebugStringW
0x1800038f1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800038f6  jnz     short loc_180003901
0x1800038f8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800038ff  jz      short loc_180003912
0x180003901  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003908  test    rax, rax
0x18000390b  jz      short loc_180003912
0x18000390d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003912  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003917  jnz     short loc_180003945
0x180003919  mov     rcx, [rbp+13F0h+var_30]
0x180003920  xor     rcx, rsp; StackCookie
0x180003923  call    __security_check_cookie
0x180003928  mov     rbx, [rsp+14F0h+arg_10]
0x180003930  add     rsp, 14D0h
0x180003937  pop     r15
0x180003939  pop     r14
0x18000393b  pop     rdi
0x18000393c  pop     rsi
0x18000393d  pop     rbp
0x18000393e  retn
0x18000393f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003945  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000394a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
