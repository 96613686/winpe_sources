# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18006b7e0`
- end: `0x18006ba86`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180056a84`

## callees

- `0x180004424`
- `0x18005de5c`
- `0x18005f060`
- `0x180068f60`
- `0x180069cc8`
- `0x18006b7e0`
- `0x18006cad8`
- `0x1800bf920`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b8a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b8a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006b99b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006b99b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006ba25`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006ba25`

## pseudocode

```c
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
0x18006b7e0  push    rbp
0x18006b7e2  push    rbx
0x18006b7e3  push    rsi
0x18006b7e4  push    rdi
0x18006b7e5  push    r12
0x18006b7e7  push    r14
0x18006b7e9  push    r15
0x18006b7eb  lea     rbp, [rsp-13D0h]
0x18006b7f3  mov     eax, 14D0h
0x18006b7f8  call    _alloca_probe
0x18006b7fd  sub     rsp, rax
0x18006b800  mov     rax, cs:__security_cookie
0x18006b807  xor     rax, rsp
0x18006b80a  mov     [rbp+1400h+var_40], rax
0x18006b811  mov     rsi, r8
0x18006b814  mov     edi, edx
0x18006b816  mov     rbx, rcx
0x18006b819  mov     r14, [rbp+1400h+arg_28]
0x18006b820  xor     edx, edx; Val
0x18006b822  mov     r8d, 98h; Size
0x18006b828  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18006b82d  call    memset_0
0x18006b832  nop
0x18006b833  xor     r12d, r12d
0x18006b836  mov     [rbp+1400h+OutputString], r12w
0x18006b83e  mov     [rbp+1400h+var_1440], r12b
0x18006b842  mov     rdx, [rbp+1400h+arg_30]; int
0x18006b849  mov     ecx, [rdx]; this
0x18006b84b  mov     [rsp+1500h+var_14D8], ecx
0x18006b84f  mov     eax, [rdx+4]
0x18006b852  mov     [rsp+1500h+var_14D4], eax
0x18006b856  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18006b85b  mov     r15d, eax
0x18006b85e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18006b866  mov     ecx, r12d
0x18006b869  lea     eax, [r12+8]
0x18006b86e  cmp     dword ptr [rdx+8], 1
0x18006b872  cmovz   ecx, eax
0x18006b875  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18006b879  lea     ecx, [rax-7]
0x18006b87c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18006b884  inc     ecx
0x18006b886  mov     [rsp+1500h+var_14D0], ecx
0x18006b88a  mov     rcx, [rbp+1400h+arg_38]
0x18006b891  test    rcx, rcx
0x18006b894  jz      short loc_18006B8A1
0x18006b896  cmp     [rcx], r12w
0x18006b89a  mov     [rsp+1500h+var_14C8], rcx
0x18006b89f  jnz     short loc_18006B8A6
0x18006b8a1  mov     [rsp+1500h+var_14C8], r12
0x18006b8a6  call    cs:__imp_GetCurrentThreadId
0x18006b8ac  mov     [rsp+1500h+var_14C0], eax
0x18006b8b0  mov     [rsp+1500h+var_14A8], rsi
0x18006b8b5  mov     [rsp+1500h+var_14A0], edi
0x18006b8b9  mov     [rsp+1500h+var_149C], r15d
0x18006b8be  mov     [rsp+1500h+var_14B8], r12
0x18006b8c3  mov     [rsp+1500h+var_14B0], r12
0x18006b8c8  mov     [rbp+1400h+var_1458], r14
0x18006b8cc  mov     [rbp+1400h+var_1450], rbx
0x18006b8d0  mov     [rsp+1500h+var_1498], r12
0x18006b8d5  xorps   xmm0, xmm0
0x18006b8d8  xor     eax, eax
0x18006b8da  movups  [rbp+1400h+var_1478], xmm0
0x18006b8de  mov     [rbp+1400h+var_1468], rax
0x18006b8e2  xorps   xmm1, xmm1
0x18006b8e5  movups  [rsp+1500h+var_1490], xmm1
0x18006b8ea  mov     [rbp+1400h+var_1480], rax
0x18006b8ee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18006b8f5  test    rax, rax
0x18006b8f8  jz      short loc_18006B905
0x18006b8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8ff  mov     [rbp+1400h+var_1460], rax
0x18006b903  jmp     short loc_18006B909
0x18006b905  mov     [rbp+1400h+var_1460], r12
0x18006b909  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18006b910  test    rax, rax
0x18006b913  jz      short loc_18006B91F
0x18006b915  lea     rcx, [rsp+1500h+var_14E0]
0x18006b91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b91f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18006b926  test    rax, rax
0x18006b929  jz      short loc_18006B93F
0x18006b92b  mov     r8d, 400h
0x18006b931  lea     rdx, [rbp+1400h+var_1440]
0x18006b935  lea     rcx, [rsp+1500h+var_14E0]
0x18006b93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b93f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18006b946  test    rax, rax
0x18006b949  jz      short loc_18006B955
0x18006b94b  lea     rcx, [rsp+1500h+var_14E0]
0x18006b950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b955  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18006b95c  test    rax, rax
0x18006b95f  jz      short loc_18006B972
0x18006b961  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18006b966  jnz     short loc_18006B972
0x18006b968  lea     rcx, [rsp+1500h+var_14E0]
0x18006b96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b972  cmp     [rsp+1500h+var_14D8], r12d
0x18006b977  jge     loc_18006BA80
0x18006b97d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18006b984  jnz     short loc_18006B9A5
0x18006b986  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18006b98d  test    rax, rax
0x18006b990  jz      short loc_18006B99B
0x18006b992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b997  test    al, al
0x18006b999  jmp     short loc_18006B9A3
0x18006b99b  call    cs:__imp_IsDebuggerPresent
0x18006b9a1  test    eax, eax
0x18006b9a3  jz      short loc_18006B9AC
0x18006b9a5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18006b9aa  jz      short loc_18006B9D2
0x18006b9ac  mov     rax, cs:g_pfnResultLoggingCallback
0x18006b9b3  test    rax, rax
0x18006b9b6  jz      short loc_18006BA2B
0x18006b9b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18006b9bf  jnz     short loc_18006BA2B
0x18006b9c1  xor     r8d, r8d
0x18006b9c4  xor     edx, edx
0x18006b9c6  lea     rcx, [rsp+1500h+var_14E0]
0x18006b9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9d0  jmp     short loc_18006BA2B
0x18006b9d2  mov     ebx, 800h
0x18006b9d7  mov     rax, cs:g_pfnResultLoggingCallback
0x18006b9de  test    rax, rax
0x18006b9e1  jz      short loc_18006BA00
0x18006b9e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18006b9ea  jnz     short loc_18006BA00
0x18006b9ec  mov     r8d, ebx
0x18006b9ef  lea     rdx, [rbp+1400h+OutputString]
0x18006b9f6  lea     rcx, [rsp+1500h+var_14E0]
0x18006b9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba00  cmp     [rbp+1400h+OutputString], r12w
0x18006ba08  jnz     short loc_18006BA1E
0x18006ba0a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18006ba0f  mov     rdx, rbx; unsigned __int16 *
0x18006ba12  lea     rcx, [rbp+1400h+OutputString]; this
0x18006ba19  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18006ba1e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18006ba25  call    cs:__imp_OutputDebugStringW
0x18006ba2b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18006ba30  jnz     short loc_18006BA3B
0x18006ba32  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18006ba39  jz      short loc_18006BA4D
0x18006ba3b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18006ba42  test    rax, rax
0x18006ba45  jz      short loc_18006BA4D
0x18006ba47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba4c  nop
0x18006ba4d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18006ba52  jnz     short loc_18006BA75
0x18006ba54  mov     rcx, [rbp+1400h+var_40]
0x18006ba5b  xor     rcx, rsp; StackCookie
0x18006ba5e  call    __security_check_cookie
0x18006ba63  add     rsp, 14D0h
0x18006ba6a  pop     r15
0x18006ba6c  pop     r14
0x18006ba6e  pop     r12
0x18006ba70  pop     rdi
0x18006ba71  pop     rsi
0x18006ba72  pop     rbx
0x18006ba73  pop     rbp
0x18006ba74  retn
0x18006ba75  lea     rcx, [rsp+1500h+var_14E0]; this
0x18006ba7a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18006ba80  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
