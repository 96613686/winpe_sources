# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002b4c`
- end: `0x140002dd9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000262c`

## callees

- `0x140002b4c`
- `0x140004324`
- `0x140006660`
- `0x140007b80`
- `0x140007d54`
- `0x14002e3e2`
- `0x14002e420`
- `0x14002e4e0`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002bfa`
- `KERNEL32!GetCurrentThreadId` at `0x140002bfa`
- `KERNEL32!OutputDebugStringW` at `0x140002d78`
- `KERNEL32!OutputDebugStringW` at `0x140002d78`
- `KERNEL32!IsDebuggerPresent` at `0x140002cee`
- `KERNEL32!IsDebuggerPresent` at `0x140002cee`

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
0x140002b4c  push    rbp
0x140002b4e  push    rbx
0x140002b4f  push    rsi
0x140002b50  push    rdi
0x140002b51  push    r12
0x140002b53  push    r14
0x140002b55  push    r15
0x140002b57  lea     rbp, [rsp-13D0h]
0x140002b5f  mov     eax, 14D0h
0x140002b64  call    _alloca_probe
0x140002b69  sub     rsp, rax
0x140002b6c  mov     rax, cs:__security_cookie
0x140002b73  xor     rax, rsp
0x140002b76  mov     [rbp+1400h+var_40], rax
0x140002b7d  mov     r14, r8
0x140002b80  mov     esi, edx
0x140002b82  mov     r15, rcx
0x140002b85  mov     rdi, [rbp+1400h+arg_28]
0x140002b8c  xor     edx, edx; Val
0x140002b8e  mov     r8d, 98h; Size
0x140002b94  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140002b99  call    memset_0
0x140002b9e  nop
0x140002b9f  xor     r12d, r12d
0x140002ba2  mov     [rbp+1400h+OutputString], r12w
0x140002baa  mov     [rbp+1400h+var_1440], r12b
0x140002bae  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140002bb5  mov     ecx, [rdx]; this
0x140002bb7  mov     [rsp+1500h+var_14D8], ecx
0x140002bbb  mov     eax, [rdx+4]
0x140002bbe  mov     [rsp+1500h+var_14D4], eax
0x140002bc2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002bc7  mov     ebx, eax
0x140002bc9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002bd1  mov     ecx, r12d
0x140002bd4  lea     eax, [r12+8]
0x140002bd9  cmp     dword ptr [rdx+8], 1
0x140002bdd  cmovz   ecx, eax
0x140002be0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002be4  lea     ecx, [rax-7]
0x140002be7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002bef  inc     ecx
0x140002bf1  mov     [rsp+1500h+var_14D0], ecx
0x140002bf5  mov     [rsp+1500h+var_14C8], r12
0x140002bfa  call    cs:__imp_GetCurrentThreadId
0x140002c00  mov     [rsp+1500h+var_14C0], eax
0x140002c04  mov     [rsp+1500h+var_14A8], r14
0x140002c09  mov     [rsp+1500h+var_14A0], esi
0x140002c0d  mov     [rsp+1500h+var_149C], ebx
0x140002c11  mov     [rsp+1500h+var_14B8], r12
0x140002c16  mov     [rsp+1500h+var_14B0], r12
0x140002c1b  mov     [rbp+1400h+var_1458], rdi
0x140002c1f  mov     [rbp+1400h+var_1450], r15
0x140002c23  mov     [rsp+1500h+var_1498], r12
0x140002c28  xorps   xmm0, xmm0
0x140002c2b  xor     eax, eax
0x140002c2d  movups  [rbp+1400h+var_1478], xmm0
0x140002c31  mov     [rbp+1400h+var_1468], rax
0x140002c35  xorps   xmm1, xmm1
0x140002c38  movups  [rsp+1500h+var_1490], xmm1
0x140002c3d  mov     [rbp+1400h+var_1480], rax
0x140002c41  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002c48  test    rax, rax
0x140002c4b  jz      short loc_140002C58
0x140002c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c52  mov     [rbp+1400h+var_1460], rax
0x140002c56  jmp     short loc_140002C5C
0x140002c58  mov     [rbp+1400h+var_1460], r12
0x140002c5c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002c63  test    rax, rax
0x140002c66  jz      short loc_140002C72
0x140002c68  lea     rcx, [rsp+1500h+var_14E0]
0x140002c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c72  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002c79  test    rax, rax
0x140002c7c  jz      short loc_140002C92
0x140002c7e  mov     r8d, 400h
0x140002c84  lea     rdx, [rbp+1400h+var_1440]
0x140002c88  lea     rcx, [rsp+1500h+var_14E0]
0x140002c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c92  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002c99  test    rax, rax
0x140002c9c  jz      short loc_140002CA8
0x140002c9e  lea     rcx, [rsp+1500h+var_14E0]
0x140002ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ca8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002caf  test    rax, rax
0x140002cb2  jz      short loc_140002CC5
0x140002cb4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002cb9  jnz     short loc_140002CC5
0x140002cbb  lea     rcx, [rsp+1500h+var_14E0]
0x140002cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cc5  cmp     [rsp+1500h+var_14D8], r12d
0x140002cca  jge     loc_140002DD3
0x140002cd0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002cd7  jnz     short loc_140002CF8
0x140002cd9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002ce0  test    rax, rax
0x140002ce3  jz      short loc_140002CEE
0x140002ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cea  test    al, al
0x140002cec  jmp     short loc_140002CF6
0x140002cee  call    cs:__imp_IsDebuggerPresent
0x140002cf4  test    eax, eax
0x140002cf6  jz      short loc_140002CFF
0x140002cf8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002cfd  jz      short loc_140002D25
0x140002cff  mov     rax, cs:g_pfnResultLoggingCallback
0x140002d06  test    rax, rax
0x140002d09  jz      short loc_140002D7E
0x140002d0b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002d12  jnz     short loc_140002D7E
0x140002d14  xor     r8d, r8d
0x140002d17  xor     edx, edx
0x140002d19  lea     rcx, [rsp+1500h+var_14E0]
0x140002d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d23  jmp     short loc_140002D7E
0x140002d25  mov     ebx, 800h
0x140002d2a  mov     rax, cs:g_pfnResultLoggingCallback
0x140002d31  test    rax, rax
0x140002d34  jz      short loc_140002D53
0x140002d36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002d3d  jnz     short loc_140002D53
0x140002d3f  mov     r8d, ebx
0x140002d42  lea     rdx, [rbp+1400h+OutputString]
0x140002d49  lea     rcx, [rsp+1500h+var_14E0]
0x140002d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d53  cmp     [rbp+1400h+OutputString], r12w
0x140002d5b  jnz     short loc_140002D71
0x140002d5d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140002d62  mov     rdx, rbx; unsigned __int16 *
0x140002d65  lea     rcx, [rbp+1400h+OutputString]; this
0x140002d6c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002d71  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002d78  call    cs:__imp_OutputDebugStringW
0x140002d7e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140002d83  jnz     short loc_140002D8E
0x140002d85  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002d8c  jz      short loc_140002DA0
0x140002d8e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002d95  test    rax, rax
0x140002d98  jz      short loc_140002DA0
0x140002d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d9f  nop
0x140002da0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002da5  jnz     short loc_140002DC8
0x140002da7  mov     rcx, [rbp+1400h+var_40]
0x140002dae  xor     rcx, rsp; StackCookie
0x140002db1  call    __security_check_cookie
0x140002db6  add     rsp, 14D0h
0x140002dbd  pop     r15
0x140002dbf  pop     r14
0x140002dc1  pop     r12
0x140002dc3  pop     rdi
0x140002dc4  pop     rsi
0x140002dc5  pop     rbx
0x140002dc6  pop     rbp
0x140002dc7  retn
0x140002dc8  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002dcd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002dd3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
