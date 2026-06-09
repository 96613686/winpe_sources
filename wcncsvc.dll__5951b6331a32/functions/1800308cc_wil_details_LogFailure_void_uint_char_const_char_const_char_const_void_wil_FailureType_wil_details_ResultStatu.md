# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800308cc`
- end: `0x180030bc5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002d208`

## callees

- `0x18002cc44`
- `0x18002fe84`
- `0x180030620`
- `0x1800308cc`
- `0x1800316b0`
- `0x1800316d0`
- `0x1800317fc`
- `0x180031818`
- `0x18003426c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800309ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800309ef`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180030b80`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180030b80`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180030b0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180030b0e`

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
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
        v27)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x1800308cc  mov     [rsp+arg_10], rbx
0x1800308d1  mov     [rsp+arg_8], edx
0x1800308d5  mov     [rsp+arg_0], rcx
0x1800308da  push    rbp
0x1800308db  push    rsi
0x1800308dc  push    rdi
0x1800308dd  push    r12
0x1800308df  push    r13
0x1800308e1  push    r14
0x1800308e3  push    r15
0x1800308e5  sub     rsp, 40h
0x1800308e9  mov     r12, r9
0x1800308ec  mov     r13, r8
0x1800308ef  mov     r10, rcx
0x1800308f2  xor     eax, eax
0x1800308f4  mov     rsi, [rsp+78h+lpOutputString]
0x1800308fc  mov     [rsi], ax
0x1800308ff  mov     rax, [rsp+78h+arg_60]
0x180030907  mov     byte ptr [rax], 0
0x18003090a  mov     r14, [rsp+78h+arg_38]
0x180030912  mov     edi, [r14]
0x180030915  mov     rbx, [rsp+78h+arg_78]
0x18003091d  mov     [rbx+8], edi
0x180030920  mov     eax, [r14+4]
0x180030924  mov     [rbx+0Ch], eax
0x180030927  xor     ebp, ebp
0x180030929  mov     r15d, [rsp+78h+arg_30]
0x180030931  mov     ecx, r15d
0x180030934  test    r15d, r15d
0x180030937  jz      short loc_18003099F
0x180030939  sub     ecx, 1
0x18003093c  jz      short loc_180030996
0x18003093e  sub     ecx, 1
0x180030941  jz      short loc_180030951
0x180030943  cmp     ecx, 1
0x180030946  jnz     short loc_1800309A8
0x180030948  mov     ecx, edi; this
0x18003094a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003094f  jmp     short loc_1800309A6
0x180030951  test    edi, edi
0x180030953  js      short loc_18003098D
0x180030955  mov     edi, 8007029Ch
0x18003095a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003095e  mov     rax, [rsp+78h+arg_28]
0x180030966  mov     [rsp+78h+var_50], rax; __int64
0x18003096b  mov     rax, [rsp+78h+arg_20]
0x180030973  mov     [rsp+78h+var_58], rax; __int64
0x180030978  mov     rcx, r10; int
0x18003097b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180030980  mov     [rbx+8], edi
0x180030983  mov     ecx, edi; this
0x180030985  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003098a  mov     [rbx+0Ch], eax
0x18003098d  mov     ecx, edi; this
0x18003098f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180030994  jmp     short loc_1800309A6
0x180030996  mov     ecx, edi; this
0x180030998  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003099d  jmp     short loc_1800309A6
0x18003099f  mov     ecx, edi; this
0x1800309a1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800309a6  mov     ebp, eax
0x1800309a8  mov     [rbx], r15d
0x1800309ab  mov     eax, [rsp+78h+arg_70]
0x1800309b2  mov     [rbx+4], eax
0x1800309b5  cmp     dword ptr [r14+8], 1
0x1800309ba  jnz     short loc_1800309C2
0x1800309bc  or      eax, 8
0x1800309bf  mov     [rbx+4], eax
0x1800309c2  mov     eax, 1
0x1800309c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800309cf  inc     eax
0x1800309d1  mov     [rbx+10h], eax
0x1800309d4  mov     rax, [rsp+78h+arg_40]
0x1800309dc  xor     edi, edi
0x1800309de  test    rax, rax
0x1800309e1  jz      short loc_1800309E8
0x1800309e3  cmp     [rax], di
0x1800309e6  jnz     short loc_1800309EB
0x1800309e8  mov     rax, rdi
0x1800309eb  mov     [rbx+18h], rax
0x1800309ef  call    cs:__imp_GetCurrentThreadId
0x1800309f5  mov     [rbx+20h], eax
0x1800309f8  mov     [rbx+38h], r13
0x1800309fc  mov     eax, [rsp+78h+arg_8]
0x180030a03  mov     [rbx+40h], eax
0x180030a06  mov     [rbx+44h], ebp
0x180030a09  mov     rax, [rsp+78h+arg_20]
0x180030a11  mov     [rbx+28h], rax
0x180030a15  mov     [rbx+30h], r12
0x180030a19  mov     rax, [rsp+78h+arg_28]
0x180030a21  mov     [rbx+88h], rax
0x180030a28  mov     rax, [rsp+78h+arg_0]
0x180030a30  mov     [rbx+90h], rax
0x180030a37  mov     [rbx+48h], rdi
0x180030a3b  xorps   xmm0, xmm0
0x180030a3e  xor     eax, eax
0x180030a40  movups  xmmword ptr [rbx+68h], xmm0
0x180030a44  mov     [rbx+78h], rax
0x180030a48  movups  xmmword ptr [rbx+50h], xmm0
0x180030a4c  mov     [rbx+60h], rax
0x180030a50  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180030a57  test    rax, rax
0x180030a5a  jz      short loc_180030A63
0x180030a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a61  jmp     short loc_180030A66
0x180030a63  mov     rax, rdi
0x180030a66  mov     [rbx+80h], rax
0x180030a6d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180030a74  test    rax, rax
0x180030a77  jz      short loc_180030A81
0x180030a79  mov     rcx, rbx
0x180030a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a81  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180030a88  test    rax, rax
0x180030a8b  jz      short loc_180030AA3
0x180030a8d  mov     r8d, 400h
0x180030a93  mov     rdx, [rsp+78h+arg_60]
0x180030a9b  mov     rcx, rbx
0x180030a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030aa3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180030aaa  test    rax, rax
0x180030aad  jz      short loc_180030AB7
0x180030aaf  mov     rcx, rbx
0x180030ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ab7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180030abe  test    rax, rax
0x180030ac1  jz      short loc_180030AD1
0x180030ac3  test    byte ptr [rbx+4], 2
0x180030ac7  jnz     short loc_180030AD1
0x180030ac9  mov     rcx, rbx
0x180030acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ad1  cmp     [rbx+8], edi
0x180030ad4  jl      short loc_180030AF0
0x180030ad6  cmp     r15d, 3
0x180030ada  jnz     loc_180030BBF
0x180030ae0  mov     ecx, 8000FFFFh; this
0x180030ae5  mov     [rbx+8], ecx
0x180030ae8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180030aed  mov     [rbx+0Ch], eax
0x180030af0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180030af7  jnz     short loc_180030B18
0x180030af9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180030b00  test    rax, rax
0x180030b03  jz      short loc_180030B0E
0x180030b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b0a  test    al, al
0x180030b0c  jmp     short loc_180030B16
0x180030b0e  call    cs:__imp_IsDebuggerPresent
0x180030b14  test    eax, eax
0x180030b16  jz      short loc_180030B1E
0x180030b18  test    byte ptr [rbx+4], 2
0x180030b1c  jz      short loc_180030B42
0x180030b1e  mov     rax, cs:g_pfnResultLoggingCallback
0x180030b25  test    rax, rax
0x180030b28  jz      short loc_180030B86
0x180030b2a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180030b31  jnz     short loc_180030B86
0x180030b33  xor     r8d, r8d
0x180030b36  xor     edx, edx
0x180030b38  mov     rcx, rbx
0x180030b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b40  jmp     short loc_180030B86
0x180030b42  mov     ebp, 800h
0x180030b47  mov     rax, cs:g_pfnResultLoggingCallback
0x180030b4e  test    rax, rax
0x180030b51  jz      short loc_180030B6A
0x180030b53  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180030b5a  jnz     short loc_180030B6A
0x180030b5c  mov     r8d, ebp
0x180030b5f  mov     rdx, rsi
0x180030b62  mov     rcx, rbx
0x180030b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b6a  cmp     [rsi], di
0x180030b6d  jnz     short loc_180030B7D
0x180030b6f  mov     r8, rbx; unsigned __int64
0x180030b72  mov     rdx, rbp; unsigned __int16 *
0x180030b75  mov     rcx, rsi; this
0x180030b78  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180030b7d  mov     rcx, rsi; lpOutputString
0x180030b80  call    cs:__imp_OutputDebugStringW
0x180030b86  test    byte ptr [rbx+4], 4
0x180030b8a  jnz     short loc_180030B95
0x180030b8c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180030b93  jz      short loc_180030BA7
0x180030b95  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180030b9c  test    rax, rax
0x180030b9f  jz      short loc_180030BA7
0x180030ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ba6  nop
0x180030ba7  mov     rbx, [rsp+78h+arg_10]
0x180030baf  add     rsp, 40h
0x180030bb3  pop     r15
0x180030bb5  pop     r14
0x180030bb7  pop     r13
0x180030bb9  pop     r12
0x180030bbb  pop     rdi
0x180030bbc  pop     rsi
0x180030bbd  pop     rbp
0x180030bbe  retn
0x180030bbf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
