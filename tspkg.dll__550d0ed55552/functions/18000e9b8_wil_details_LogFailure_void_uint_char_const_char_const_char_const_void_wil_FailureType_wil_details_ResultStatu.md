# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000e9b8`
- end: `0x18000ecb0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000cd24`
- `0x18000d070`

## callees

- `0x18000aab8`
- `0x18000cc64`
- `0x18000e0c4`
- `0x18000e9b8`
- `0x18000f380`
- `0x18000f3a0`
- `0x18000f4f0`
- `0x18000f50c`
- `0x1800108b4`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eadb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eadb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ec6c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ec6c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ebfa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ebfa`

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
0x18000e9b8  mov     [rsp+arg_10], rbx
0x18000e9bd  mov     [rsp+arg_8], edx
0x18000e9c1  mov     [rsp+arg_0], rcx
0x18000e9c6  push    rbp
0x18000e9c7  push    rsi
0x18000e9c8  push    rdi
0x18000e9c9  push    r12
0x18000e9cb  push    r13
0x18000e9cd  push    r14
0x18000e9cf  push    r15
0x18000e9d1  sub     rsp, 40h
0x18000e9d5  mov     r14, [rsp+78h+arg_38]
0x18000e9dd  xor     eax, eax
0x18000e9df  mov     rbx, [rsp+78h+arg_78]
0x18000e9e7  xor     ebp, ebp
0x18000e9e9  mov     r15d, [rsp+78h+arg_30]
0x18000e9f1  mov     r10, rcx
0x18000e9f4  mov     rsi, [rsp+78h+lpOutputString]
0x18000e9fc  mov     r12, r9
0x18000e9ff  mov     r13, r8
0x18000ea02  mov     ecx, r15d
0x18000ea05  mov     [rsi], ax
0x18000ea08  mov     rax, [rsp+78h+arg_60]
0x18000ea10  mov     byte ptr [rax], 0
0x18000ea13  mov     edi, [r14]
0x18000ea16  mov     [rbx+8], edi
0x18000ea19  mov     eax, [r14+4]
0x18000ea1d  mov     [rbx+0Ch], eax
0x18000ea20  test    r15d, r15d
0x18000ea23  jz      short loc_18000EA8B
0x18000ea25  sub     ecx, 1
0x18000ea28  jz      short loc_18000EA82
0x18000ea2a  sub     ecx, 1
0x18000ea2d  jz      short loc_18000EA3D
0x18000ea2f  cmp     ecx, 1
0x18000ea32  jnz     short loc_18000EA94
0x18000ea34  mov     ecx, edi; this
0x18000ea36  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ea3b  jmp     short loc_18000EA92
0x18000ea3d  test    edi, edi
0x18000ea3f  js      short loc_18000EA79
0x18000ea41  mov     rax, [rsp+78h+arg_28]
0x18000ea49  mov     edi, 8007029Ch
0x18000ea4e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ea52  mov     rcx, r10; int
0x18000ea55  mov     [rsp+78h+var_50], rax; __int64
0x18000ea5a  mov     rax, [rsp+78h+arg_20]
0x18000ea62  mov     [rsp+78h+var_58], rax; __int64
0x18000ea67  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ea6c  mov     ecx, edi; this
0x18000ea6e  mov     [rbx+8], edi
0x18000ea71  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ea76  mov     [rbx+0Ch], eax
0x18000ea79  mov     ecx, edi; this
0x18000ea7b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ea80  jmp     short loc_18000EA92
0x18000ea82  mov     ecx, edi; this
0x18000ea84  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ea89  jmp     short loc_18000EA92
0x18000ea8b  mov     ecx, edi; this
0x18000ea8d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ea92  mov     ebp, eax
0x18000ea94  mov     eax, [rsp+78h+arg_70]
0x18000ea9b  mov     [rbx+4], eax
0x18000ea9e  mov     [rbx], r15d
0x18000eaa1  cmp     dword ptr [r14+8], 1
0x18000eaa6  jnz     short loc_18000EAAE
0x18000eaa8  or      eax, 8
0x18000eaab  mov     [rbx+4], eax
0x18000eaae  mov     eax, 1
0x18000eab3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000eabb  inc     eax
0x18000eabd  xor     edi, edi
0x18000eabf  mov     [rbx+10h], eax
0x18000eac2  mov     rax, [rsp+78h+arg_40]
0x18000eaca  test    rax, rax
0x18000eacd  jz      short loc_18000EAD4
0x18000eacf  cmp     [rax], di
0x18000ead2  jnz     short loc_18000EAD7
0x18000ead4  mov     rax, rdi
0x18000ead7  mov     [rbx+18h], rax
0x18000eadb  call    cs:__imp_GetCurrentThreadId
0x18000eae1  mov     [rbx+38h], r13
0x18000eae5  xorps   xmm0, xmm0
0x18000eae8  mov     [rbx+20h], eax
0x18000eaeb  mov     eax, [rsp+78h+arg_8]
0x18000eaf2  mov     [rbx+40h], eax
0x18000eaf5  mov     rax, [rsp+78h+arg_20]
0x18000eafd  mov     [rbx+28h], rax
0x18000eb01  mov     rax, [rsp+78h+arg_28]
0x18000eb09  mov     [rbx+88h], rax
0x18000eb10  mov     rax, [rsp+78h+arg_0]
0x18000eb18  mov     [rbx+90h], rax
0x18000eb1f  xor     eax, eax
0x18000eb21  mov     [rbx+44h], ebp
0x18000eb24  mov     [rbx+30h], r12
0x18000eb28  mov     [rbx+48h], rdi
0x18000eb2c  movups  xmmword ptr [rbx+68h], xmm0
0x18000eb30  mov     [rbx+78h], rax
0x18000eb34  movups  xmmword ptr [rbx+50h], xmm0
0x18000eb38  mov     [rbx+60h], rax
0x18000eb3c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000eb43  test    rax, rax
0x18000eb46  jz      short loc_18000EB4F
0x18000eb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb4d  jmp     short loc_18000EB52
0x18000eb4f  mov     rax, rdi
0x18000eb52  mov     [rbx+80h], rax
0x18000eb59  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000eb60  test    rax, rax
0x18000eb63  jz      short loc_18000EB6D
0x18000eb65  mov     rcx, rbx
0x18000eb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb6d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000eb74  test    rax, rax
0x18000eb77  jz      short loc_18000EB8F
0x18000eb79  mov     rdx, [rsp+78h+arg_60]
0x18000eb81  mov     r8d, 400h
0x18000eb87  mov     rcx, rbx
0x18000eb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb8f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000eb96  test    rax, rax
0x18000eb99  jz      short loc_18000EBA3
0x18000eb9b  mov     rcx, rbx
0x18000eb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eba3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ebaa  test    rax, rax
0x18000ebad  jz      short loc_18000EBBD
0x18000ebaf  test    byte ptr [rbx+4], 2
0x18000ebb3  jnz     short loc_18000EBBD
0x18000ebb5  mov     rcx, rbx
0x18000ebb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebbd  cmp     [rbx+8], edi
0x18000ebc0  jl      short loc_18000EBDC
0x18000ebc2  cmp     r15d, 3
0x18000ebc6  jnz     loc_18000ECAA
0x18000ebcc  mov     ecx, 8000FFFFh; this
0x18000ebd1  mov     [rbx+8], ecx
0x18000ebd4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ebd9  mov     [rbx+0Ch], eax
0x18000ebdc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000ebe3  jnz     short loc_18000EC04
0x18000ebe5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ebec  test    rax, rax
0x18000ebef  jz      short loc_18000EBFA
0x18000ebf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebf6  test    al, al
0x18000ebf8  jmp     short loc_18000EC02
0x18000ebfa  call    cs:__imp_IsDebuggerPresent
0x18000ec00  test    eax, eax
0x18000ec02  jz      short loc_18000EC0A
0x18000ec04  test    byte ptr [rbx+4], 2
0x18000ec08  jz      short loc_18000EC2E
0x18000ec0a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ec11  test    rax, rax
0x18000ec14  jz      short loc_18000EC72
0x18000ec16  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ec1d  jnz     short loc_18000EC72
0x18000ec1f  xor     r8d, r8d
0x18000ec22  xor     edx, edx
0x18000ec24  mov     rcx, rbx
0x18000ec27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec2c  jmp     short loc_18000EC72
0x18000ec2e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ec35  mov     ebp, 800h
0x18000ec3a  test    rax, rax
0x18000ec3d  jz      short loc_18000EC56
0x18000ec3f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ec46  jnz     short loc_18000EC56
0x18000ec48  mov     r8d, ebp
0x18000ec4b  mov     rdx, rsi
0x18000ec4e  mov     rcx, rbx
0x18000ec51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec56  cmp     [rsi], di
0x18000ec59  jnz     short loc_18000EC69
0x18000ec5b  mov     r8, rbx; unsigned __int64
0x18000ec5e  mov     rdx, rbp; unsigned __int16 *
0x18000ec61  mov     rcx, rsi; this
0x18000ec64  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ec69  mov     rcx, rsi; lpOutputString
0x18000ec6c  call    cs:__imp_OutputDebugStringW
0x18000ec72  test    byte ptr [rbx+4], 4
0x18000ec76  jnz     short loc_18000EC81
0x18000ec78  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000ec7f  jz      short loc_18000EC92
0x18000ec81  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ec88  test    rax, rax
0x18000ec8b  jz      short loc_18000EC92
0x18000ec8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec92  mov     rbx, [rsp+78h+arg_10]
0x18000ec9a  add     rsp, 40h
0x18000ec9e  pop     r15
0x18000eca0  pop     r14
0x18000eca2  pop     r13
0x18000eca4  pop     r12
0x18000eca6  pop     rdi
0x18000eca7  pop     rsi
0x18000eca8  pop     rbp
0x18000eca9  retn
0x18000ecaa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
