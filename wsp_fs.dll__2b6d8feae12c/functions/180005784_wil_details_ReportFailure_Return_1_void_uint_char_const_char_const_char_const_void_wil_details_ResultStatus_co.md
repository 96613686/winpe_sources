# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005784`
- end: `0x180005a1a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000528c`

## callees

- `0x180002a70`
- `0x180003498`
- `0x180005784`
- `0x180007344`
- `0x180008cd0`
- `0x18000a410`
- `0x18000a63c`
- `0x180099f30`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000582f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000582f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800059b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800059b4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000592a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000592a`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180005784  mov     [rsp-8+arg_10], rbx
0x180005789  push    rbp
0x18000578a  push    rsi
0x18000578b  push    rdi
0x18000578c  push    r14
0x18000578e  push    r15
0x180005790  lea     rbp, [rsp-13D0h]
0x180005798  mov     eax, 14D0h
0x18000579d  call    _alloca_probe
0x1800057a2  sub     rsp, rax
0x1800057a5  mov     rax, cs:__security_cookie
0x1800057ac  xor     rax, rsp
0x1800057af  mov     [rbp+13F0h+var_30], rax
0x1800057b6  mov     esi, edx
0x1800057b8  mov     r14, rcx
0x1800057bb  mov     rdi, [rbp+13F0h+arg_28]
0x1800057c2  xor     edx, edx; Val
0x1800057c4  mov     r8d, 98h; Size
0x1800057ca  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800057cf  call    memset_0
0x1800057d4  nop
0x1800057d5  xor     r15d, r15d
0x1800057d8  mov     [rbp+13F0h+OutputString], r15w
0x1800057e0  mov     [rbp+13F0h+var_1430], r15b
0x1800057e4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800057eb  mov     ecx, [rdx]; this
0x1800057ed  mov     [rsp+14F0h+var_14C8], ecx
0x1800057f1  mov     eax, [rdx+4]
0x1800057f4  mov     [rsp+14F0h+var_14C4], eax
0x1800057f8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800057fd  mov     ebx, eax
0x1800057ff  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180005807  mov     ecx, r15d
0x18000580a  lea     eax, [r15+8]
0x18000580e  cmp     dword ptr [rdx+8], 1
0x180005812  cmovz   ecx, eax
0x180005815  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005819  lea     ecx, [rax-7]
0x18000581c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005824  inc     ecx
0x180005826  mov     [rsp+14F0h+var_14C0], ecx
0x18000582a  mov     [rsp+14F0h+var_14B8], r15
0x18000582f  call    cs:__imp_GetCurrentThreadId
0x180005835  mov     [rsp+14F0h+var_14B0], eax
0x180005839  lea     rax, aWil; "wil"
0x180005840  mov     [rsp+14F0h+var_1498], rax
0x180005845  mov     [rsp+14F0h+var_1490], esi
0x180005849  mov     [rsp+14F0h+var_148C], ebx
0x18000584d  mov     [rsp+14F0h+var_14A8], r15
0x180005852  mov     [rsp+14F0h+var_14A0], r15
0x180005857  mov     [rbp+13F0h+var_1448], rdi
0x18000585b  mov     [rbp+13F0h+var_1440], r14
0x18000585f  mov     [rsp+14F0h+var_1488], r15
0x180005864  xorps   xmm0, xmm0
0x180005867  xor     eax, eax
0x180005869  movups  [rbp+13F0h+var_1468], xmm0
0x18000586d  mov     [rbp+13F0h+var_1458], rax
0x180005871  xorps   xmm1, xmm1
0x180005874  movups  [rsp+14F0h+var_1480], xmm1
0x180005879  mov     [rbp+13F0h+var_1470], rax
0x18000587d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005884  test    rax, rax
0x180005887  jz      short loc_180005894
0x180005889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000588e  mov     [rbp+13F0h+var_1450], rax
0x180005892  jmp     short loc_180005898
0x180005894  mov     [rbp+13F0h+var_1450], r15
0x180005898  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000589f  test    rax, rax
0x1800058a2  jz      short loc_1800058AE
0x1800058a4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800058a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ae  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800058b5  test    rax, rax
0x1800058b8  jz      short loc_1800058CE
0x1800058ba  mov     r8d, 400h
0x1800058c0  lea     rdx, [rbp+13F0h+var_1430]
0x1800058c4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800058c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ce  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800058d5  test    rax, rax
0x1800058d8  jz      short loc_1800058E4
0x1800058da  lea     rcx, [rsp+14F0h+var_14D0]
0x1800058df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800058eb  test    rax, rax
0x1800058ee  jz      short loc_180005901
0x1800058f0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800058f5  jnz     short loc_180005901
0x1800058f7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800058fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005901  cmp     [rsp+14F0h+var_14C8], r15d
0x180005906  jge     loc_180005A14
0x18000590c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180005913  jnz     short loc_180005934
0x180005915  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000591c  test    rax, rax
0x18000591f  jz      short loc_18000592A
0x180005921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005926  test    al, al
0x180005928  jmp     short loc_180005932
0x18000592a  call    cs:__imp_IsDebuggerPresent
0x180005930  test    eax, eax
0x180005932  jz      short loc_18000593B
0x180005934  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005939  jz      short loc_180005961
0x18000593b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005942  test    rax, rax
0x180005945  jz      short loc_1800059BA
0x180005947  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000594e  jnz     short loc_1800059BA
0x180005950  xor     r8d, r8d
0x180005953  xor     edx, edx
0x180005955  lea     rcx, [rsp+14F0h+var_14D0]
0x18000595a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000595f  jmp     short loc_1800059BA
0x180005961  mov     ebx, 800h
0x180005966  mov     rax, cs:g_pfnResultLoggingCallback
0x18000596d  test    rax, rax
0x180005970  jz      short loc_18000598F
0x180005972  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005979  jnz     short loc_18000598F
0x18000597b  mov     r8d, ebx
0x18000597e  lea     rdx, [rbp+13F0h+OutputString]
0x180005985  lea     rcx, [rsp+14F0h+var_14D0]
0x18000598a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000598f  cmp     [rbp+13F0h+OutputString], r15w
0x180005997  jnz     short loc_1800059AD
0x180005999  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000599e  mov     rdx, rbx; wchar_t *
0x1800059a1  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x1800059a8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800059ad  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800059b4  call    cs:__imp_OutputDebugStringW
0x1800059ba  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800059bf  jnz     short loc_1800059CA
0x1800059c1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800059c8  jz      short loc_1800059DC
0x1800059ca  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800059d1  test    rax, rax
0x1800059d4  jz      short loc_1800059DC
0x1800059d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059db  nop
0x1800059dc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800059e1  jnz     short loc_180005A09
0x1800059e3  mov     rcx, [rbp+13F0h+var_30]
0x1800059ea  xor     rcx, rsp; StackCookie
0x1800059ed  call    __security_check_cookie
0x1800059f2  mov     rbx, [rsp+14F0h+arg_10]
0x1800059fa  add     rsp, 14D0h
0x180005a01  pop     r15
0x180005a03  pop     r14
0x180005a05  pop     rdi
0x180005a06  pop     rsi
0x180005a07  pop     rbp
0x180005a08  retn
0x180005a09  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005a0e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005a14  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
