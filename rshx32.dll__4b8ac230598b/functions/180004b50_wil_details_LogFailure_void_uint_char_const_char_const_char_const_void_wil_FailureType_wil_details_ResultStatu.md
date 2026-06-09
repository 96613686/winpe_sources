# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004b50`
- end: `0x180004e48`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800035b4`

## callees

- `0x180002ff0`
- `0x1800041f4`
- `0x18000498c`
- `0x180004b50`
- `0x18000508c`
- `0x1800050b0`
- `0x1800050c4`
- `0x1800050e0`
- `0x180005acc`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c73`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004e04`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004e04`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d92`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d92`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x180004b50  mov     [rsp+arg_10], rbx
0x180004b55  mov     [rsp+arg_8], edx
0x180004b59  mov     [rsp+arg_0], rcx
0x180004b5e  push    rbp
0x180004b5f  push    rsi
0x180004b60  push    rdi
0x180004b61  push    r12
0x180004b63  push    r13
0x180004b65  push    r14
0x180004b67  push    r15
0x180004b69  sub     rsp, 40h
0x180004b6d  mov     r14, [rsp+78h+arg_38]
0x180004b75  xor     eax, eax
0x180004b77  mov     rbx, [rsp+78h+arg_78]
0x180004b7f  xor     ebp, ebp
0x180004b81  mov     r15d, [rsp+78h+arg_30]
0x180004b89  mov     r10, rcx
0x180004b8c  mov     rsi, [rsp+78h+lpOutputString]
0x180004b94  mov     r12, r9
0x180004b97  mov     r13, r8
0x180004b9a  mov     ecx, r15d
0x180004b9d  mov     [rsi], ax
0x180004ba0  mov     rax, [rsp+78h+arg_60]
0x180004ba8  mov     byte ptr [rax], 0
0x180004bab  mov     edi, [r14]
0x180004bae  mov     [rbx+8], edi
0x180004bb1  mov     eax, [r14+4]
0x180004bb5  mov     [rbx+0Ch], eax
0x180004bb8  test    r15d, r15d
0x180004bbb  jz      short loc_180004C23
0x180004bbd  sub     ecx, 1
0x180004bc0  jz      short loc_180004C1A
0x180004bc2  sub     ecx, 1
0x180004bc5  jz      short loc_180004BD5
0x180004bc7  cmp     ecx, 1
0x180004bca  jnz     short loc_180004C2C
0x180004bcc  mov     ecx, edi; this
0x180004bce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004bd3  jmp     short loc_180004C2A
0x180004bd5  test    edi, edi
0x180004bd7  js      short loc_180004C11
0x180004bd9  mov     rax, [rsp+78h+arg_28]
0x180004be1  mov     edi, 8007029Ch
0x180004be6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004bea  mov     rcx, r10; int
0x180004bed  mov     [rsp+78h+var_50], rax; __int64
0x180004bf2  mov     rax, [rsp+78h+arg_20]
0x180004bfa  mov     [rsp+78h+var_58], rax; __int64
0x180004bff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004c04  mov     ecx, edi; this
0x180004c06  mov     [rbx+8], edi
0x180004c09  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004c0e  mov     [rbx+0Ch], eax
0x180004c11  mov     ecx, edi; this
0x180004c13  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004c18  jmp     short loc_180004C2A
0x180004c1a  mov     ecx, edi; this
0x180004c1c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004c21  jmp     short loc_180004C2A
0x180004c23  mov     ecx, edi; this
0x180004c25  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004c2a  mov     ebp, eax
0x180004c2c  mov     eax, [rsp+78h+arg_70]
0x180004c33  mov     [rbx+4], eax
0x180004c36  mov     [rbx], r15d
0x180004c39  cmp     dword ptr [r14+8], 1
0x180004c3e  jnz     short loc_180004C46
0x180004c40  or      eax, 8
0x180004c43  mov     [rbx+4], eax
0x180004c46  mov     eax, 1
0x180004c4b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004c53  inc     eax
0x180004c55  xor     edi, edi
0x180004c57  mov     [rbx+10h], eax
0x180004c5a  mov     rax, [rsp+78h+arg_40]
0x180004c62  test    rax, rax
0x180004c65  jz      short loc_180004C6C
0x180004c67  cmp     [rax], di
0x180004c6a  jnz     short loc_180004C6F
0x180004c6c  mov     rax, rdi
0x180004c6f  mov     [rbx+18h], rax
0x180004c73  call    cs:__imp_GetCurrentThreadId
0x180004c79  mov     [rbx+38h], r13
0x180004c7d  xorps   xmm0, xmm0
0x180004c80  mov     [rbx+20h], eax
0x180004c83  mov     eax, [rsp+78h+arg_8]
0x180004c8a  mov     [rbx+40h], eax
0x180004c8d  mov     rax, [rsp+78h+arg_20]
0x180004c95  mov     [rbx+28h], rax
0x180004c99  mov     rax, [rsp+78h+arg_28]
0x180004ca1  mov     [rbx+88h], rax
0x180004ca8  mov     rax, [rsp+78h+arg_0]
0x180004cb0  mov     [rbx+90h], rax
0x180004cb7  xor     eax, eax
0x180004cb9  mov     [rbx+44h], ebp
0x180004cbc  mov     [rbx+30h], r12
0x180004cc0  mov     [rbx+48h], rdi
0x180004cc4  movups  xmmword ptr [rbx+68h], xmm0
0x180004cc8  mov     [rbx+78h], rax
0x180004ccc  movups  xmmword ptr [rbx+50h], xmm0
0x180004cd0  mov     [rbx+60h], rax
0x180004cd4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004cdb  test    rax, rax
0x180004cde  jz      short loc_180004CE7
0x180004ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce5  jmp     short loc_180004CEA
0x180004ce7  mov     rax, rdi
0x180004cea  mov     [rbx+80h], rax
0x180004cf1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004cf8  test    rax, rax
0x180004cfb  jz      short loc_180004D05
0x180004cfd  mov     rcx, rbx
0x180004d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d05  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004d0c  test    rax, rax
0x180004d0f  jz      short loc_180004D27
0x180004d11  mov     rdx, [rsp+78h+arg_60]
0x180004d19  mov     r8d, 400h
0x180004d1f  mov     rcx, rbx
0x180004d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d27  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004d2e  test    rax, rax
0x180004d31  jz      short loc_180004D3B
0x180004d33  mov     rcx, rbx
0x180004d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004d42  test    rax, rax
0x180004d45  jz      short loc_180004D55
0x180004d47  test    byte ptr [rbx+4], 2
0x180004d4b  jnz     short loc_180004D55
0x180004d4d  mov     rcx, rbx
0x180004d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d55  cmp     [rbx+8], edi
0x180004d58  jl      short loc_180004D74
0x180004d5a  cmp     r15d, 3
0x180004d5e  jnz     loc_180004E42
0x180004d64  mov     ecx, 8000FFFFh; this
0x180004d69  mov     [rbx+8], ecx
0x180004d6c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004d71  mov     [rbx+0Ch], eax
0x180004d74  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004d7b  jnz     short loc_180004D9C
0x180004d7d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004d84  test    rax, rax
0x180004d87  jz      short loc_180004D92
0x180004d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8e  test    al, al
0x180004d90  jmp     short loc_180004D9A
0x180004d92  call    cs:__imp_IsDebuggerPresent
0x180004d98  test    eax, eax
0x180004d9a  jz      short loc_180004DA2
0x180004d9c  test    byte ptr [rbx+4], 2
0x180004da0  jz      short loc_180004DC6
0x180004da2  mov     rax, cs:g_pfnResultLoggingCallback
0x180004da9  test    rax, rax
0x180004dac  jz      short loc_180004E0A
0x180004dae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004db5  jnz     short loc_180004E0A
0x180004db7  xor     r8d, r8d
0x180004dba  xor     edx, edx
0x180004dbc  mov     rcx, rbx
0x180004dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc4  jmp     short loc_180004E0A
0x180004dc6  mov     rax, cs:g_pfnResultLoggingCallback
0x180004dcd  mov     ebp, 800h
0x180004dd2  test    rax, rax
0x180004dd5  jz      short loc_180004DEE
0x180004dd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004dde  jnz     short loc_180004DEE
0x180004de0  mov     r8d, ebp
0x180004de3  mov     rdx, rsi
0x180004de6  mov     rcx, rbx
0x180004de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dee  cmp     [rsi], di
0x180004df1  jnz     short loc_180004E01
0x180004df3  mov     r8, rbx; unsigned __int64
0x180004df6  mov     rdx, rbp; unsigned __int16 *
0x180004df9  mov     rcx, rsi; this
0x180004dfc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004e01  mov     rcx, rsi; lpOutputString
0x180004e04  call    cs:__imp_OutputDebugStringW
0x180004e0a  test    byte ptr [rbx+4], 4
0x180004e0e  jnz     short loc_180004E19
0x180004e10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004e17  jz      short loc_180004E2A
0x180004e19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004e20  test    rax, rax
0x180004e23  jz      short loc_180004E2A
0x180004e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e2a  mov     rbx, [rsp+78h+arg_10]
0x180004e32  add     rsp, 40h
0x180004e36  pop     r15
0x180004e38  pop     r14
0x180004e3a  pop     r13
0x180004e3c  pop     r12
0x180004e3e  pop     rdi
0x180004e3f  pop     rsi
0x180004e40  pop     rbp
0x180004e41  retn
0x180004e42  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
