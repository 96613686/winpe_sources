# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18003c244`
- end: `0x18003c4d8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003bd4c`

## callees

- `0x18001deb0`
- `0x18001e80c`
- `0x18003c244`
- `0x18003d884`
- `0x18003f2d0`
- `0x1800407d0`
- `0x180040988`
- `0x180043580`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c2ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c2ee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c473`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c473`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c3e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c3e9`

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
0x18003c244  mov     [rsp-8+arg_10], rbx
0x18003c249  push    rbp
0x18003c24a  push    rsi
0x18003c24b  push    rdi
0x18003c24c  push    r14
0x18003c24e  push    r15
0x18003c250  lea     rbp, [rsp-13D0h]
0x18003c258  mov     eax, 14D0h
0x18003c25d  call    _alloca_probe
0x18003c262  sub     rsp, rax
0x18003c265  mov     rax, cs:__security_cookie
0x18003c26c  xor     rax, rsp
0x18003c26f  mov     [rbp+13F0h+var_30], rax
0x18003c276  mov     rdi, [rbp+13F0h+arg_28]
0x18003c27d  mov     esi, edx
0x18003c27f  mov     r14, rcx
0x18003c282  xor     edx, edx; Val
0x18003c284  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18003c289  mov     r8d, 98h; Size
0x18003c28f  call    memset_0
0x18003c294  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18003c29b  xor     r15d, r15d
0x18003c29e  mov     [rbp+13F0h+OutputString], r15w
0x18003c2a6  mov     [rbp+13F0h+var_1430], r15b
0x18003c2aa  mov     ecx, [rdx]; this
0x18003c2ac  mov     eax, [rdx+4]
0x18003c2af  mov     [rsp+14F0h+var_14C8], ecx
0x18003c2b3  mov     [rsp+14F0h+var_14C4], eax
0x18003c2b7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003c2bc  cmp     dword ptr [rdx+8], 1
0x18003c2c0  mov     ebx, eax
0x18003c2c2  lea     eax, [r15+8]
0x18003c2c6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18003c2ce  mov     ecx, r15d
0x18003c2d1  cmovz   ecx, eax
0x18003c2d4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18003c2d8  lea     ecx, [rax-7]
0x18003c2db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003c2e3  inc     ecx
0x18003c2e5  mov     [rsp+14F0h+var_14B8], r15
0x18003c2ea  mov     [rsp+14F0h+var_14C0], ecx
0x18003c2ee  call    cs:__imp_GetCurrentThreadId
0x18003c2f4  xorps   xmm0, xmm0
0x18003c2f7  mov     [rsp+14F0h+var_1490], esi
0x18003c2fb  mov     [rsp+14F0h+var_14B0], eax
0x18003c2ff  xorps   xmm1, xmm1
0x18003c302  lea     rax, aWil; "wil"
0x18003c309  mov     [rsp+14F0h+var_148C], ebx
0x18003c30d  mov     [rsp+14F0h+var_1498], rax
0x18003c312  xor     eax, eax
0x18003c314  mov     [rbp+13F0h+var_1458], rax
0x18003c318  mov     [rbp+13F0h+var_1470], rax
0x18003c31c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003c323  mov     [rsp+14F0h+var_14A8], r15
0x18003c328  mov     [rsp+14F0h+var_14A0], r15
0x18003c32d  mov     [rbp+13F0h+var_1448], rdi
0x18003c331  mov     [rbp+13F0h+var_1440], r14
0x18003c335  mov     [rsp+14F0h+var_1488], r15
0x18003c33a  movups  [rbp+13F0h+var_1468], xmm0
0x18003c33e  movups  [rsp+14F0h+var_1480], xmm1
0x18003c343  test    rax, rax
0x18003c346  jz      short loc_18003C353
0x18003c348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c34d  mov     [rbp+13F0h+var_1450], rax
0x18003c351  jmp     short loc_18003C357
0x18003c353  mov     [rbp+13F0h+var_1450], r15
0x18003c357  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003c35e  test    rax, rax
0x18003c361  jz      short loc_18003C36D
0x18003c363  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c36d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003c374  test    rax, rax
0x18003c377  jz      short loc_18003C38D
0x18003c379  mov     r8d, 400h
0x18003c37f  lea     rdx, [rbp+13F0h+var_1430]
0x18003c383  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c38d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c394  test    rax, rax
0x18003c397  jz      short loc_18003C3A3
0x18003c399  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c3aa  test    rax, rax
0x18003c3ad  jz      short loc_18003C3C0
0x18003c3af  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003c3b4  jnz     short loc_18003C3C0
0x18003c3b6  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3c0  cmp     [rsp+14F0h+var_14C8], r15d
0x18003c3c5  jge     loc_18003C4C7
0x18003c3cb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18003c3d2  jnz     short loc_18003C3F3
0x18003c3d4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003c3db  test    rax, rax
0x18003c3de  jz      short loc_18003C3E9
0x18003c3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3e5  test    al, al
0x18003c3e7  jmp     short loc_18003C3F1
0x18003c3e9  call    cs:__imp_IsDebuggerPresent
0x18003c3ef  test    eax, eax
0x18003c3f1  jz      short loc_18003C3FA
0x18003c3f3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003c3f8  jz      short loc_18003C420
0x18003c3fa  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c401  test    rax, rax
0x18003c404  jz      short loc_18003C479
0x18003c406  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c40d  jnz     short loc_18003C479
0x18003c40f  xor     r8d, r8d
0x18003c412  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c417  xor     edx, edx
0x18003c419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c41e  jmp     short loc_18003C479
0x18003c420  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c427  mov     ebx, 800h
0x18003c42c  test    rax, rax
0x18003c42f  jz      short loc_18003C44E
0x18003c431  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c438  jnz     short loc_18003C44E
0x18003c43a  mov     r8d, ebx
0x18003c43d  lea     rdx, [rbp+13F0h+OutputString]
0x18003c444  lea     rcx, [rsp+14F0h+var_14D0]
0x18003c449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c44e  cmp     [rbp+13F0h+OutputString], r15w
0x18003c456  jnz     short loc_18003C46C
0x18003c458  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18003c45d  mov     rdx, rbx; unsigned __int16 *
0x18003c460  lea     rcx, [rbp+13F0h+OutputString]; this
0x18003c467  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003c46c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18003c473  call    cs:__imp_OutputDebugStringW
0x18003c479  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18003c47e  jnz     short loc_18003C489
0x18003c480  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18003c487  jz      short loc_18003C49A
0x18003c489  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003c490  test    rax, rax
0x18003c493  jz      short loc_18003C49A
0x18003c495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c49a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18003c49f  jnz     short loc_18003C4CD
0x18003c4a1  mov     rcx, [rbp+13F0h+var_30]
0x18003c4a8  xor     rcx, rsp; StackCookie
0x18003c4ab  call    __security_check_cookie
0x18003c4b0  mov     rbx, [rsp+14F0h+arg_10]
0x18003c4b8  add     rsp, 14D0h
0x18003c4bf  pop     r15
0x18003c4c1  pop     r14
0x18003c4c3  pop     rdi
0x18003c4c4  pop     rsi
0x18003c4c5  pop     rbp
0x18003c4c6  retn
0x18003c4c7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003c4cd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18003c4d2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
