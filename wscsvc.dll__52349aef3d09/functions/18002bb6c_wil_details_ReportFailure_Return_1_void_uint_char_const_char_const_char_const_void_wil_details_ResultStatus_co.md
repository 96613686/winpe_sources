# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18002bb6c`
- end: `0x18002bdf9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002b8ac`

## callees

- `0x18002bb6c`
- `0x18002cb24`
- `0x18002d94c`
- `0x18002e778`
- `0x18002eae4`
- `0x18003fbf2`
- `0x18003fc30`
- `0x18003fcf0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bc1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bc1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002bd0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002bd0e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002bd98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002bd98`

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
0x18002bb6c  push    rbp
0x18002bb6e  push    rbx
0x18002bb6f  push    rsi
0x18002bb70  push    rdi
0x18002bb71  push    r12
0x18002bb73  push    r14
0x18002bb75  push    r15
0x18002bb77  lea     rbp, [rsp-13D0h]
0x18002bb7f  mov     eax, 14D0h
0x18002bb84  call    _alloca_probe
0x18002bb89  sub     rsp, rax
0x18002bb8c  mov     rax, cs:__security_cookie
0x18002bb93  xor     rax, rsp
0x18002bb96  mov     [rbp+1400h+var_40], rax
0x18002bb9d  mov     r14, r8
0x18002bba0  mov     esi, edx
0x18002bba2  mov     r15, rcx
0x18002bba5  mov     rdi, [rbp+1400h+arg_28]
0x18002bbac  xor     edx, edx; Val
0x18002bbae  mov     r8d, 98h; Size
0x18002bbb4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18002bbb9  call    memset_0
0x18002bbbe  nop
0x18002bbbf  xor     r12d, r12d
0x18002bbc2  mov     [rbp+1400h+OutputString], r12w
0x18002bbca  mov     [rbp+1400h+var_1440], r12b
0x18002bbce  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18002bbd5  mov     ecx, [rdx]; this
0x18002bbd7  mov     [rsp+1500h+var_14D8], ecx
0x18002bbdb  mov     eax, [rdx+4]
0x18002bbde  mov     [rsp+1500h+var_14D4], eax
0x18002bbe2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002bbe7  mov     ebx, eax
0x18002bbe9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18002bbf1  mov     ecx, r12d
0x18002bbf4  lea     eax, [r12+8]
0x18002bbf9  cmp     dword ptr [rdx+8], 1
0x18002bbfd  cmovz   ecx, eax
0x18002bc00  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18002bc04  lea     ecx, [rax-7]
0x18002bc07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002bc0f  inc     ecx
0x18002bc11  mov     [rsp+1500h+var_14D0], ecx
0x18002bc15  mov     [rsp+1500h+var_14C8], r12
0x18002bc1a  call    cs:__imp_GetCurrentThreadId
0x18002bc20  mov     [rsp+1500h+var_14C0], eax
0x18002bc24  mov     [rsp+1500h+var_14A8], r14
0x18002bc29  mov     [rsp+1500h+var_14A0], esi
0x18002bc2d  mov     [rsp+1500h+var_149C], ebx
0x18002bc31  mov     [rsp+1500h+var_14B8], r12
0x18002bc36  mov     [rsp+1500h+var_14B0], r12
0x18002bc3b  mov     [rbp+1400h+var_1458], rdi
0x18002bc3f  mov     [rbp+1400h+var_1450], r15
0x18002bc43  mov     [rsp+1500h+var_1498], r12
0x18002bc48  xorps   xmm0, xmm0
0x18002bc4b  xor     eax, eax
0x18002bc4d  movups  [rbp+1400h+var_1478], xmm0
0x18002bc51  mov     [rbp+1400h+var_1468], rax
0x18002bc55  xorps   xmm1, xmm1
0x18002bc58  movups  [rsp+1500h+var_1490], xmm1
0x18002bc5d  mov     [rbp+1400h+var_1480], rax
0x18002bc61  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002bc68  test    rax, rax
0x18002bc6b  jz      short loc_18002BC78
0x18002bc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc72  mov     [rbp+1400h+var_1460], rax
0x18002bc76  jmp     short loc_18002BC7C
0x18002bc78  mov     [rbp+1400h+var_1460], r12
0x18002bc7c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002bc83  test    rax, rax
0x18002bc86  jz      short loc_18002BC92
0x18002bc88  lea     rcx, [rsp+1500h+var_14E0]
0x18002bc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc92  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002bc99  test    rax, rax
0x18002bc9c  jz      short loc_18002BCB2
0x18002bc9e  mov     r8d, 400h
0x18002bca4  lea     rdx, [rbp+1400h+var_1440]
0x18002bca8  lea     rcx, [rsp+1500h+var_14E0]
0x18002bcad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcb2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002bcb9  test    rax, rax
0x18002bcbc  jz      short loc_18002BCC8
0x18002bcbe  lea     rcx, [rsp+1500h+var_14E0]
0x18002bcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcc8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002bccf  test    rax, rax
0x18002bcd2  jz      short loc_18002BCE5
0x18002bcd4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18002bcd9  jnz     short loc_18002BCE5
0x18002bcdb  lea     rcx, [rsp+1500h+var_14E0]
0x18002bce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bce5  cmp     [rsp+1500h+var_14D8], r12d
0x18002bcea  jge     loc_18002BDF3
0x18002bcf0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18002bcf7  jnz     short loc_18002BD18
0x18002bcf9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002bd00  test    rax, rax
0x18002bd03  jz      short loc_18002BD0E
0x18002bd05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd0a  test    al, al
0x18002bd0c  jmp     short loc_18002BD16
0x18002bd0e  call    cs:__imp_IsDebuggerPresent
0x18002bd14  test    eax, eax
0x18002bd16  jz      short loc_18002BD1F
0x18002bd18  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18002bd1d  jz      short loc_18002BD45
0x18002bd1f  mov     rax, cs:g_pfnResultLoggingCallback
0x18002bd26  test    rax, rax
0x18002bd29  jz      short loc_18002BD9E
0x18002bd2b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18002bd32  jnz     short loc_18002BD9E
0x18002bd34  xor     r8d, r8d
0x18002bd37  xor     edx, edx
0x18002bd39  lea     rcx, [rsp+1500h+var_14E0]
0x18002bd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd43  jmp     short loc_18002BD9E
0x18002bd45  mov     ebx, 800h
0x18002bd4a  mov     rax, cs:g_pfnResultLoggingCallback
0x18002bd51  test    rax, rax
0x18002bd54  jz      short loc_18002BD73
0x18002bd56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18002bd5d  jnz     short loc_18002BD73
0x18002bd5f  mov     r8d, ebx
0x18002bd62  lea     rdx, [rbp+1400h+OutputString]
0x18002bd69  lea     rcx, [rsp+1500h+var_14E0]
0x18002bd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd73  cmp     [rbp+1400h+OutputString], r12w
0x18002bd7b  jnz     short loc_18002BD91
0x18002bd7d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18002bd82  mov     rdx, rbx; unsigned __int16 *
0x18002bd85  lea     rcx, [rbp+1400h+OutputString]; this
0x18002bd8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002bd91  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18002bd98  call    cs:__imp_OutputDebugStringW
0x18002bd9e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18002bda3  jnz     short loc_18002BDAE
0x18002bda5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18002bdac  jz      short loc_18002BDC0
0x18002bdae  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002bdb5  test    rax, rax
0x18002bdb8  jz      short loc_18002BDC0
0x18002bdba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdbf  nop
0x18002bdc0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18002bdc5  jnz     short loc_18002BDE8
0x18002bdc7  mov     rcx, [rbp+1400h+var_40]
0x18002bdce  xor     rcx, rsp; StackCookie
0x18002bdd1  call    __security_check_cookie
0x18002bdd6  add     rsp, 14D0h
0x18002bddd  pop     r15
0x18002bddf  pop     r14
0x18002bde1  pop     r12
0x18002bde3  pop     rdi
0x18002bde4  pop     rsi
0x18002bde5  pop     rbx
0x18002bde6  pop     rbp
0x18002bde7  retn
0x18002bde8  lea     rcx, [rsp+1500h+var_14E0]; this
0x18002bded  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002bdf3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
