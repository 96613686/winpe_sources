# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001cd5c`
- end: `0x18001cfe7`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001a1ec`

## callees

- `0x18001cd5c`
- `0x18001e7a4`
- `0x180020390`
- `0x180021e38`
- `0x1800220dc`
- `0x180032c6a`
- `0x180032c90`
- `0x180032d20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ce09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ce09`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cf87`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cf87`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cefd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cefd`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
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
0x18001cd5c  push    rbp
0x18001cd5e  push    rbx
0x18001cd5f  push    rsi
0x18001cd60  push    rdi
0x18001cd61  push    r12
0x18001cd63  push    r14
0x18001cd65  push    r15
0x18001cd67  lea     rbp, [rsp-13D0h]
0x18001cd6f  mov     eax, 14D0h
0x18001cd74  call    _alloca_probe
0x18001cd79  sub     rsp, rax
0x18001cd7c  mov     rax, cs:__security_cookie
0x18001cd83  xor     rax, rsp
0x18001cd86  mov     [rbp+1400h+var_40], rax
0x18001cd8d  mov     rdi, [rbp+1400h+arg_28]
0x18001cd94  mov     r14, r8
0x18001cd97  mov     esi, edx
0x18001cd99  mov     r15, rcx
0x18001cd9c  xor     edx, edx; Val
0x18001cd9e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18001cda3  mov     r8d, 98h; Size
0x18001cda9  call    memset_0
0x18001cdae  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18001cdb5  xor     r12d, r12d
0x18001cdb8  mov     [rbp+1400h+OutputString], r12w
0x18001cdc0  mov     [rbp+1400h+var_1440], r12b
0x18001cdc4  mov     ecx, [rdx]; this
0x18001cdc6  mov     eax, [rdx+4]
0x18001cdc9  mov     [rsp+1500h+var_14D8], ecx
0x18001cdcd  mov     [rsp+1500h+var_14D4], eax
0x18001cdd1  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001cdd6  cmp     dword ptr [rdx+8], 1
0x18001cdda  mov     ebx, eax
0x18001cddc  lea     eax, [r12+8]
0x18001cde1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18001cde9  mov     ecx, r12d
0x18001cdec  cmovz   ecx, eax
0x18001cdef  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18001cdf3  lea     ecx, [rax-7]
0x18001cdf6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001cdfe  inc     ecx
0x18001ce00  mov     [rsp+1500h+var_14C8], r12
0x18001ce05  mov     [rsp+1500h+var_14D0], ecx
0x18001ce09  call    cs:__imp_GetCurrentThreadId
0x18001ce0f  xorps   xmm0, xmm0
0x18001ce12  mov     [rsp+1500h+var_14A8], r14
0x18001ce17  mov     [rsp+1500h+var_14C0], eax
0x18001ce1b  xorps   xmm1, xmm1
0x18001ce1e  xor     eax, eax
0x18001ce20  mov     [rsp+1500h+var_14A0], esi
0x18001ce24  mov     [rbp+1400h+var_1468], rax
0x18001ce28  mov     [rbp+1400h+var_1480], rax
0x18001ce2c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001ce33  mov     [rsp+1500h+var_149C], ebx
0x18001ce37  mov     [rsp+1500h+var_14B8], r12
0x18001ce3c  mov     [rsp+1500h+var_14B0], r12
0x18001ce41  mov     [rbp+1400h+var_1458], rdi
0x18001ce45  mov     [rbp+1400h+var_1450], r15
0x18001ce49  mov     [rsp+1500h+var_1498], r12
0x18001ce4e  movups  [rbp+1400h+var_1478], xmm0
0x18001ce52  movups  [rsp+1500h+var_1490], xmm1
0x18001ce57  test    rax, rax
0x18001ce5a  jz      short loc_18001CE67
0x18001ce5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce61  mov     [rbp+1400h+var_1460], rax
0x18001ce65  jmp     short loc_18001CE6B
0x18001ce67  mov     [rbp+1400h+var_1460], r12
0x18001ce6b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001ce72  test    rax, rax
0x18001ce75  jz      short loc_18001CE81
0x18001ce77  lea     rcx, [rsp+1500h+var_14E0]
0x18001ce7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce81  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001ce88  test    rax, rax
0x18001ce8b  jz      short loc_18001CEA1
0x18001ce8d  mov     r8d, 400h
0x18001ce93  lea     rdx, [rbp+1400h+var_1440]
0x18001ce97  lea     rcx, [rsp+1500h+var_14E0]
0x18001ce9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cea1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001cea8  test    rax, rax
0x18001ceab  jz      short loc_18001CEB7
0x18001cead  lea     rcx, [rsp+1500h+var_14E0]
0x18001ceb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceb7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001cebe  test    rax, rax
0x18001cec1  jz      short loc_18001CED4
0x18001cec3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001cec8  jnz     short loc_18001CED4
0x18001ceca  lea     rcx, [rsp+1500h+var_14E0]
0x18001cecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ced4  cmp     [rsp+1500h+var_14D8], r12d
0x18001ced9  jge     loc_18001CFD6
0x18001cedf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18001cee6  jnz     short loc_18001CF07
0x18001cee8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001ceef  test    rax, rax
0x18001cef2  jz      short loc_18001CEFD
0x18001cef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cef9  test    al, al
0x18001cefb  jmp     short loc_18001CF05
0x18001cefd  call    cs:__imp_IsDebuggerPresent
0x18001cf03  test    eax, eax
0x18001cf05  jz      short loc_18001CF0E
0x18001cf07  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001cf0c  jz      short loc_18001CF34
0x18001cf0e  mov     rax, cs:g_pfnResultLoggingCallback
0x18001cf15  test    rax, rax
0x18001cf18  jz      short loc_18001CF8D
0x18001cf1a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001cf21  jnz     short loc_18001CF8D
0x18001cf23  xor     r8d, r8d
0x18001cf26  lea     rcx, [rsp+1500h+var_14E0]
0x18001cf2b  xor     edx, edx
0x18001cf2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf32  jmp     short loc_18001CF8D
0x18001cf34  mov     rax, cs:g_pfnResultLoggingCallback
0x18001cf3b  mov     ebx, 800h
0x18001cf40  test    rax, rax
0x18001cf43  jz      short loc_18001CF62
0x18001cf45  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001cf4c  jnz     short loc_18001CF62
0x18001cf4e  mov     r8d, ebx
0x18001cf51  lea     rdx, [rbp+1400h+OutputString]
0x18001cf58  lea     rcx, [rsp+1500h+var_14E0]
0x18001cf5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf62  cmp     [rbp+1400h+OutputString], r12w
0x18001cf6a  jnz     short loc_18001CF80
0x18001cf6c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18001cf71  mov     rdx, rbx; unsigned __int16 *
0x18001cf74  lea     rcx, [rbp+1400h+OutputString]; this
0x18001cf7b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001cf80  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18001cf87  call    cs:__imp_OutputDebugStringW
0x18001cf8d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18001cf92  jnz     short loc_18001CF9D
0x18001cf94  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18001cf9b  jz      short loc_18001CFAE
0x18001cf9d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001cfa4  test    rax, rax
0x18001cfa7  jz      short loc_18001CFAE
0x18001cfa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfae  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18001cfb3  jnz     short loc_18001CFDC
0x18001cfb5  mov     rcx, [rbp+1400h+var_40]
0x18001cfbc  xor     rcx, rsp; StackCookie
0x18001cfbf  call    __security_check_cookie
0x18001cfc4  add     rsp, 14D0h
0x18001cfcb  pop     r15
0x18001cfcd  pop     r14
0x18001cfcf  pop     r12
0x18001cfd1  pop     rdi
0x18001cfd2  pop     rsi
0x18001cfd3  pop     rbx
0x18001cfd4  pop     rbp
0x18001cfd5  retn
0x18001cfd6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001cfdc  lea     rcx, [rsp+1500h+var_14E0]; this
0x18001cfe1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
