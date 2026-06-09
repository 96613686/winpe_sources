# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800338e0`
- end: `0x180033bd4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18003300c`
- `0x1800330fc`
- `0x180037128`

## callees

- `0x1800311ac`
- `0x180032fa8`
- `0x180033324`
- `0x1800338e0`
- `0x180033d40`
- `0x180033d60`
- `0x180033d74`
- `0x180033d90`
- `0x1800346fc`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033a03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033a03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180033b96`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180033b96`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180033b24`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180033b24`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x1800338e0  mov     [rsp+arg_10], rbx
0x1800338e5  mov     [rsp+arg_8], edx
0x1800338e9  mov     [rsp+arg_0], rcx
0x1800338ee  push    rbp
0x1800338ef  push    rsi
0x1800338f0  push    rdi
0x1800338f1  push    r12
0x1800338f3  push    r13
0x1800338f5  push    r14
0x1800338f7  push    r15
0x1800338f9  sub     rsp, 40h
0x1800338fd  mov     r14, [rsp+78h+arg_38]
0x180033905  xor     eax, eax
0x180033907  mov     rbx, [rsp+78h+arg_78]
0x18003390f  xor     ebp, ebp
0x180033911  mov     r15d, [rsp+78h+arg_30]
0x180033919  mov     r10, rcx
0x18003391c  mov     rsi, [rsp+78h+lpOutputString]
0x180033924  mov     r12, r9
0x180033927  mov     r13, r8
0x18003392a  mov     ecx, r15d
0x18003392d  mov     [rsi], ax
0x180033930  mov     rax, [rsp+78h+arg_60]
0x180033938  mov     byte ptr [rax], 0
0x18003393b  mov     edi, [r14]
0x18003393e  mov     [rbx+8], edi
0x180033941  mov     eax, [r14+4]
0x180033945  mov     [rbx+0Ch], eax
0x180033948  test    r15d, r15d
0x18003394b  jz      short loc_1800339B3
0x18003394d  sub     ecx, 1
0x180033950  jz      short loc_1800339AA
0x180033952  sub     ecx, 1
0x180033955  jz      short loc_180033965
0x180033957  cmp     ecx, 1
0x18003395a  jnz     short loc_1800339BC
0x18003395c  mov     ecx, edi; this
0x18003395e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180033963  jmp     short loc_1800339BA
0x180033965  test    edi, edi
0x180033967  js      short loc_1800339A1
0x180033969  mov     rax, [rsp+78h+arg_28]
0x180033971  mov     edi, 8007029Ch
0x180033976  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003397a  mov     rcx, r10; int
0x18003397d  mov     [rsp+78h+var_50], rax; __int64
0x180033982  mov     rax, [rsp+78h+arg_20]
0x18003398a  mov     [rsp+78h+var_58], rax; __int64
0x18003398f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180033994  mov     ecx, edi; this
0x180033996  mov     [rbx+8], edi
0x180033999  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003399e  mov     [rbx+0Ch], eax
0x1800339a1  mov     ecx, edi; this
0x1800339a3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800339a8  jmp     short loc_1800339BA
0x1800339aa  mov     ecx, edi; this
0x1800339ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800339b1  jmp     short loc_1800339BA
0x1800339b3  mov     ecx, edi; this
0x1800339b5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800339ba  mov     ebp, eax
0x1800339bc  mov     eax, [rsp+78h+arg_70]
0x1800339c3  mov     [rbx+4], eax
0x1800339c6  mov     [rbx], r15d
0x1800339c9  cmp     dword ptr [r14+8], 1
0x1800339ce  jnz     short loc_1800339D6
0x1800339d0  or      eax, 8
0x1800339d3  mov     [rbx+4], eax
0x1800339d6  mov     eax, 1
0x1800339db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800339e3  inc     eax
0x1800339e5  xor     edi, edi
0x1800339e7  mov     [rbx+10h], eax
0x1800339ea  mov     rax, [rsp+78h+arg_40]
0x1800339f2  test    rax, rax
0x1800339f5  jz      short loc_1800339FC
0x1800339f7  cmp     [rax], di
0x1800339fa  jnz     short loc_1800339FF
0x1800339fc  mov     rax, rdi
0x1800339ff  mov     [rbx+18h], rax
0x180033a03  call    cs:__imp_GetCurrentThreadId
0x180033a09  mov     [rbx+38h], r13
0x180033a0d  xorps   xmm0, xmm0
0x180033a10  mov     [rbx+20h], eax
0x180033a13  mov     eax, [rsp+78h+arg_8]
0x180033a1a  mov     [rbx+40h], eax
0x180033a1d  mov     rax, [rsp+78h+arg_20]
0x180033a25  mov     [rbx+28h], rax
0x180033a29  mov     rax, [rsp+78h+arg_28]
0x180033a31  mov     [rbx+88h], rax
0x180033a38  mov     rax, [rsp+78h+arg_0]
0x180033a40  mov     [rbx+90h], rax
0x180033a47  xor     eax, eax
0x180033a49  mov     [rbx+44h], ebp
0x180033a4c  mov     [rbx+30h], r12
0x180033a50  mov     [rbx+48h], rdi
0x180033a54  movups  xmmword ptr [rbx+68h], xmm0
0x180033a58  mov     [rbx+78h], rax
0x180033a5c  movups  xmmword ptr [rbx+50h], xmm0
0x180033a60  mov     [rbx+60h], rax
0x180033a64  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180033a6b  test    rax, rax
0x180033a6e  jz      short loc_180033A77
0x180033a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a75  jmp     short loc_180033A7A
0x180033a77  mov     rax, rdi
0x180033a7a  mov     [rbx+80h], rax
0x180033a81  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180033a88  test    rax, rax
0x180033a8b  jz      short loc_180033A95
0x180033a8d  mov     rcx, rbx
0x180033a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a95  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180033a9c  test    rax, rax
0x180033a9f  jz      short loc_180033AB7
0x180033aa1  mov     rdx, [rsp+78h+arg_60]
0x180033aa9  mov     r8d, 400h
0x180033aaf  mov     rcx, rbx
0x180033ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ab7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180033abe  test    rax, rax
0x180033ac1  jz      short loc_180033ACB
0x180033ac3  mov     rcx, rbx
0x180033ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033acb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180033ad2  test    rax, rax
0x180033ad5  jz      short loc_180033AE5
0x180033ad7  test    byte ptr [rbx+4], 2
0x180033adb  jnz     short loc_180033AE5
0x180033add  mov     rcx, rbx
0x180033ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ae5  cmp     [rbx+8], edi
0x180033ae8  jl      short loc_180033B06
0x180033aea  cmp     r15d, 3
0x180033aee  jz      short loc_180033AF6
0x180033af0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180033af6  mov     ecx, 8000FFFFh; this
0x180033afb  mov     [rbx+8], ecx
0x180033afe  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180033b03  mov     [rbx+0Ch], eax
0x180033b06  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180033b0d  jnz     short loc_180033B2E
0x180033b0f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180033b16  test    rax, rax
0x180033b19  jz      short loc_180033B24
0x180033b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b20  test    al, al
0x180033b22  jmp     short loc_180033B2C
0x180033b24  call    cs:__imp_IsDebuggerPresent
0x180033b2a  test    eax, eax
0x180033b2c  jz      short loc_180033B34
0x180033b2e  test    byte ptr [rbx+4], 2
0x180033b32  jz      short loc_180033B58
0x180033b34  mov     rax, cs:g_pfnResultLoggingCallback
0x180033b3b  test    rax, rax
0x180033b3e  jz      short loc_180033B9C
0x180033b40  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180033b47  jnz     short loc_180033B9C
0x180033b49  xor     r8d, r8d
0x180033b4c  xor     edx, edx
0x180033b4e  mov     rcx, rbx
0x180033b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b56  jmp     short loc_180033B9C
0x180033b58  mov     rax, cs:g_pfnResultLoggingCallback
0x180033b5f  mov     ebp, 800h
0x180033b64  test    rax, rax
0x180033b67  jz      short loc_180033B80
0x180033b69  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180033b70  jnz     short loc_180033B80
0x180033b72  mov     r8d, ebp
0x180033b75  mov     rdx, rsi
0x180033b78  mov     rcx, rbx
0x180033b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b80  cmp     [rsi], di
0x180033b83  jnz     short loc_180033B93
0x180033b85  mov     r8, rbx; unsigned __int64
0x180033b88  mov     rdx, rbp; unsigned __int16 *
0x180033b8b  mov     rcx, rsi; this
0x180033b8e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180033b93  mov     rcx, rsi; lpOutputString
0x180033b96  call    cs:__imp_OutputDebugStringW
0x180033b9c  test    byte ptr [rbx+4], 4
0x180033ba0  jnz     short loc_180033BAB
0x180033ba2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180033ba9  jz      short loc_180033BBC
0x180033bab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180033bb2  test    rax, rax
0x180033bb5  jz      short loc_180033BBC
0x180033bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bbc  mov     rbx, [rsp+78h+arg_10]
0x180033bc4  add     rsp, 40h
0x180033bc8  pop     r15
0x180033bca  pop     r14
0x180033bcc  pop     r13
0x180033bce  pop     r12
0x180033bd0  pop     rdi
0x180033bd1  pop     rsi
0x180033bd2  pop     rbp
0x180033bd3  retn
```
