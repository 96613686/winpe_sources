# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000ac9c`
- end: `0x18000af27`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a774`

## callees

- `0x18000ac9c`
- `0x18000caf4`
- `0x18000e02c`
- `0x18000fd40`
- `0x18000ff0c`
- `0x18001b77a`
- `0x18001b7b0`
- `0x18001b840`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad49`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000aec7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000aec7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ae3d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ae3d`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18000ac9c  push    rbp
0x18000ac9e  push    rbx
0x18000ac9f  push    rsi
0x18000aca0  push    rdi
0x18000aca1  push    r12
0x18000aca3  push    r14
0x18000aca5  push    r15
0x18000aca7  lea     rbp, [rsp-13D0h]
0x18000acaf  mov     eax, 14D0h
0x18000acb4  call    _alloca_probe
0x18000acb9  sub     rsp, rax
0x18000acbc  mov     rax, cs:__security_cookie
0x18000acc3  xor     rax, rsp
0x18000acc6  mov     [rbp+1400h+var_40], rax
0x18000accd  mov     rdi, [rbp+1400h+arg_28]
0x18000acd4  mov     r14, r8
0x18000acd7  mov     esi, edx
0x18000acd9  mov     r15, rcx
0x18000acdc  xor     edx, edx; Val
0x18000acde  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000ace3  mov     r8d, 98h; Size
0x18000ace9  call    memset_0
0x18000acee  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000acf5  xor     r12d, r12d
0x18000acf8  mov     [rbp+1400h+OutputString], r12w
0x18000ad00  mov     [rbp+1400h+var_1440], r12b
0x18000ad04  mov     ecx, [rdx]; this
0x18000ad06  mov     eax, [rdx+4]
0x18000ad09  mov     [rsp+1500h+var_14D8], ecx
0x18000ad0d  mov     [rsp+1500h+var_14D4], eax
0x18000ad11  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ad16  cmp     dword ptr [rdx+8], 1
0x18000ad1a  mov     ebx, eax
0x18000ad1c  lea     eax, [r12+8]
0x18000ad21  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000ad29  mov     ecx, r12d
0x18000ad2c  cmovz   ecx, eax
0x18000ad2f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000ad33  lea     ecx, [rax-7]
0x18000ad36  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ad3e  inc     ecx
0x18000ad40  mov     [rsp+1500h+var_14C8], r12
0x18000ad45  mov     [rsp+1500h+var_14D0], ecx
0x18000ad49  call    cs:__imp_GetCurrentThreadId
0x18000ad4f  xorps   xmm0, xmm0
0x18000ad52  mov     [rsp+1500h+var_14A8], r14
0x18000ad57  mov     [rsp+1500h+var_14C0], eax
0x18000ad5b  xorps   xmm1, xmm1
0x18000ad5e  xor     eax, eax
0x18000ad60  mov     [rsp+1500h+var_14A0], esi
0x18000ad64  mov     [rbp+1400h+var_1468], rax
0x18000ad68  mov     [rbp+1400h+var_1480], rax
0x18000ad6c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ad73  mov     [rsp+1500h+var_149C], ebx
0x18000ad77  mov     [rsp+1500h+var_14B8], r12
0x18000ad7c  mov     [rsp+1500h+var_14B0], r12
0x18000ad81  mov     [rbp+1400h+var_1458], rdi
0x18000ad85  mov     [rbp+1400h+var_1450], r15
0x18000ad89  mov     [rsp+1500h+var_1498], r12
0x18000ad8e  movups  [rbp+1400h+var_1478], xmm0
0x18000ad92  movups  [rsp+1500h+var_1490], xmm1
0x18000ad97  test    rax, rax
0x18000ad9a  jz      short loc_18000ADA7
0x18000ad9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada1  mov     [rbp+1400h+var_1460], rax
0x18000ada5  jmp     short loc_18000ADAB
0x18000ada7  mov     [rbp+1400h+var_1460], r12
0x18000adab  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000adb2  test    rax, rax
0x18000adb5  jz      short loc_18000ADC1
0x18000adb7  lea     rcx, [rsp+1500h+var_14E0]
0x18000adbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000adc8  test    rax, rax
0x18000adcb  jz      short loc_18000ADE1
0x18000adcd  mov     r8d, 400h
0x18000add3  lea     rdx, [rbp+1400h+var_1440]
0x18000add7  lea     rcx, [rsp+1500h+var_14E0]
0x18000addc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ade1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ade8  test    rax, rax
0x18000adeb  jz      short loc_18000ADF7
0x18000aded  lea     rcx, [rsp+1500h+var_14E0]
0x18000adf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000adfe  test    rax, rax
0x18000ae01  jz      short loc_18000AE14
0x18000ae03  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000ae08  jnz     short loc_18000AE14
0x18000ae0a  lea     rcx, [rsp+1500h+var_14E0]
0x18000ae0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae14  cmp     [rsp+1500h+var_14D8], r12d
0x18000ae19  jge     loc_18000AF16
0x18000ae1f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000ae26  jnz     short loc_18000AE47
0x18000ae28  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ae2f  test    rax, rax
0x18000ae32  jz      short loc_18000AE3D
0x18000ae34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae39  test    al, al
0x18000ae3b  jmp     short loc_18000AE45
0x18000ae3d  call    cs:__imp_IsDebuggerPresent
0x18000ae43  test    eax, eax
0x18000ae45  jz      short loc_18000AE4E
0x18000ae47  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000ae4c  jz      short loc_18000AE74
0x18000ae4e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ae55  test    rax, rax
0x18000ae58  jz      short loc_18000AECD
0x18000ae5a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000ae61  jnz     short loc_18000AECD
0x18000ae63  xor     r8d, r8d
0x18000ae66  lea     rcx, [rsp+1500h+var_14E0]
0x18000ae6b  xor     edx, edx
0x18000ae6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae72  jmp     short loc_18000AECD
0x18000ae74  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ae7b  mov     ebx, 800h
0x18000ae80  test    rax, rax
0x18000ae83  jz      short loc_18000AEA2
0x18000ae85  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000ae8c  jnz     short loc_18000AEA2
0x18000ae8e  mov     r8d, ebx
0x18000ae91  lea     rdx, [rbp+1400h+OutputString]
0x18000ae98  lea     rcx, [rsp+1500h+var_14E0]
0x18000ae9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aea2  cmp     [rbp+1400h+OutputString], r12w
0x18000aeaa  jnz     short loc_18000AEC0
0x18000aeac  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000aeb1  mov     rdx, rbx; wchar_t *
0x18000aeb4  lea     rcx, [rbp+1400h+OutputString]; this
0x18000aebb  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000aec0  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000aec7  call    cs:__imp_OutputDebugStringW
0x18000aecd  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000aed2  jnz     short loc_18000AEDD
0x18000aed4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000aedb  jz      short loc_18000AEEE
0x18000aedd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000aee4  test    rax, rax
0x18000aee7  jz      short loc_18000AEEE
0x18000aee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeee  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000aef3  jnz     short loc_18000AF1C
0x18000aef5  mov     rcx, [rbp+1400h+var_40]
0x18000aefc  xor     rcx, rsp; StackCookie
0x18000aeff  call    __security_check_cookie
0x18000af04  add     rsp, 14D0h
0x18000af0b  pop     r15
0x18000af0d  pop     r14
0x18000af0f  pop     r12
0x18000af11  pop     rdi
0x18000af12  pop     rsi
0x18000af13  pop     rbx
0x18000af14  pop     rbp
0x18000af15  retn
0x18000af16  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000af1c  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000af21  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
