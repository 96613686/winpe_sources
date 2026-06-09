# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800056dc`
- end: `0x180005982`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004e68`

## callees

- `0x180004120`
- `0x180004c80`
- `0x1800056dc`
- `0x180007af4`
- `0x1800090fc`
- `0x18000b590`
- `0x18000b75c`
- `0x18002ef20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057a2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005921`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005921`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005897`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005897`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x1800056dc  push    rbp
0x1800056de  push    rbx
0x1800056df  push    rsi
0x1800056e0  push    rdi
0x1800056e1  push    r12
0x1800056e3  push    r14
0x1800056e5  push    r15
0x1800056e7  lea     rbp, [rsp-13D0h]
0x1800056ef  mov     eax, 14D0h
0x1800056f4  call    _alloca_probe
0x1800056f9  sub     rsp, rax
0x1800056fc  mov     rax, cs:__security_cookie
0x180005703  xor     rax, rsp
0x180005706  mov     [rbp+1400h+var_40], rax
0x18000570d  mov     rsi, r8
0x180005710  mov     edi, edx
0x180005712  mov     rbx, rcx
0x180005715  mov     r14, [rbp+1400h+arg_28]
0x18000571c  xor     edx, edx; Val
0x18000571e  mov     r8d, 98h; Size
0x180005724  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005729  call    memset_0
0x18000572e  nop
0x18000572f  xor     r12d, r12d
0x180005732  mov     [rbp+1400h+OutputString], r12w
0x18000573a  mov     [rbp+1400h+var_1440], r12b
0x18000573e  mov     rdx, [rbp+1400h+arg_30]; int
0x180005745  mov     ecx, [rdx]; this
0x180005747  mov     [rsp+1500h+var_14D8], ecx
0x18000574b  mov     eax, [rdx+4]
0x18000574e  mov     [rsp+1500h+var_14D4], eax
0x180005752  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005757  mov     r15d, eax
0x18000575a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005762  mov     ecx, r12d
0x180005765  lea     eax, [r12+8]
0x18000576a  cmp     dword ptr [rdx+8], 1
0x18000576e  cmovz   ecx, eax
0x180005771  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005775  lea     ecx, [rax-7]
0x180005778  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005780  inc     ecx
0x180005782  mov     [rsp+1500h+var_14D0], ecx
0x180005786  mov     rcx, [rbp+1400h+arg_38]
0x18000578d  test    rcx, rcx
0x180005790  jz      short loc_18000579D
0x180005792  cmp     [rcx], r12w
0x180005796  mov     [rsp+1500h+var_14C8], rcx
0x18000579b  jnz     short loc_1800057A2
0x18000579d  mov     [rsp+1500h+var_14C8], r12
0x1800057a2  call    cs:__imp_GetCurrentThreadId
0x1800057a8  mov     [rsp+1500h+var_14C0], eax
0x1800057ac  mov     [rsp+1500h+var_14A8], rsi
0x1800057b1  mov     [rsp+1500h+var_14A0], edi
0x1800057b5  mov     [rsp+1500h+var_149C], r15d
0x1800057ba  mov     [rsp+1500h+var_14B8], r12
0x1800057bf  mov     [rsp+1500h+var_14B0], r12
0x1800057c4  mov     [rbp+1400h+var_1458], r14
0x1800057c8  mov     [rbp+1400h+var_1450], rbx
0x1800057cc  mov     [rsp+1500h+var_1498], r12
0x1800057d1  xorps   xmm0, xmm0
0x1800057d4  xor     eax, eax
0x1800057d6  movups  [rbp+1400h+var_1478], xmm0
0x1800057da  mov     [rbp+1400h+var_1468], rax
0x1800057de  xorps   xmm1, xmm1
0x1800057e1  movups  [rsp+1500h+var_1490], xmm1
0x1800057e6  mov     [rbp+1400h+var_1480], rax
0x1800057ea  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800057f1  test    rax, rax
0x1800057f4  jz      short loc_180005801
0x1800057f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057fb  mov     [rbp+1400h+var_1460], rax
0x1800057ff  jmp     short loc_180005805
0x180005801  mov     [rbp+1400h+var_1460], r12
0x180005805  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000580c  test    rax, rax
0x18000580f  jz      short loc_18000581B
0x180005811  lea     rcx, [rsp+1500h+var_14E0]
0x180005816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005822  test    rax, rax
0x180005825  jz      short loc_18000583B
0x180005827  mov     r8d, 400h
0x18000582d  lea     rdx, [rbp+1400h+var_1440]
0x180005831  lea     rcx, [rsp+1500h+var_14E0]
0x180005836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000583b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005842  test    rax, rax
0x180005845  jz      short loc_180005851
0x180005847  lea     rcx, [rsp+1500h+var_14E0]
0x18000584c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005851  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005858  test    rax, rax
0x18000585b  jz      short loc_18000586E
0x18000585d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005862  jnz     short loc_18000586E
0x180005864  lea     rcx, [rsp+1500h+var_14E0]
0x180005869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000586e  cmp     [rsp+1500h+var_14D8], r12d
0x180005873  jge     loc_18000597C
0x180005879  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005880  jnz     short loc_1800058A1
0x180005882  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005889  test    rax, rax
0x18000588c  jz      short loc_180005897
0x18000588e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005893  test    al, al
0x180005895  jmp     short loc_18000589F
0x180005897  call    cs:__imp_IsDebuggerPresent
0x18000589d  test    eax, eax
0x18000589f  jz      short loc_1800058A8
0x1800058a1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800058a6  jz      short loc_1800058CE
0x1800058a8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800058af  test    rax, rax
0x1800058b2  jz      short loc_180005927
0x1800058b4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800058bb  jnz     short loc_180005927
0x1800058bd  xor     r8d, r8d
0x1800058c0  xor     edx, edx
0x1800058c2  lea     rcx, [rsp+1500h+var_14E0]
0x1800058c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058cc  jmp     short loc_180005927
0x1800058ce  mov     ebx, 800h
0x1800058d3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800058da  test    rax, rax
0x1800058dd  jz      short loc_1800058FC
0x1800058df  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800058e6  jnz     short loc_1800058FC
0x1800058e8  mov     r8d, ebx
0x1800058eb  lea     rdx, [rbp+1400h+OutputString]
0x1800058f2  lea     rcx, [rsp+1500h+var_14E0]
0x1800058f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058fc  cmp     [rbp+1400h+OutputString], r12w
0x180005904  jnz     short loc_18000591A
0x180005906  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000590b  mov     rdx, rbx; unsigned __int16 *
0x18000590e  lea     rcx, [rbp+1400h+OutputString]; this
0x180005915  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000591a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005921  call    cs:__imp_OutputDebugStringW
0x180005927  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000592c  jnz     short loc_180005937
0x18000592e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005935  jz      short loc_180005949
0x180005937  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000593e  test    rax, rax
0x180005941  jz      short loc_180005949
0x180005943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005948  nop
0x180005949  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000594e  jnz     short loc_180005971
0x180005950  mov     rcx, [rbp+1400h+var_40]
0x180005957  xor     rcx, rsp; StackCookie
0x18000595a  call    __security_check_cookie
0x18000595f  add     rsp, 14D0h
0x180005966  pop     r15
0x180005968  pop     r14
0x18000596a  pop     r12
0x18000596c  pop     rdi
0x18000596d  pop     rsi
0x18000596e  pop     rbx
0x18000596f  pop     rbp
0x180005970  retn
0x180005971  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005976  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000597c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
