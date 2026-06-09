# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180013c38`
- end: `0x180013f12`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `730`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18000e3c8`
- `0x18000e718`

## callees

- `0x18000e300`
- `0x180011b64`
- `0x180012eec`
- `0x180013b74`
- `0x180013c38`
- `0x180014e4c`
- `0x180014e70`
- `0x180014e84`
- `0x180014ea0`
- `0x1800167a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013d5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013d5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013ea9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013ea9`

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
  __int64 ModuleName; // rax
  const struct wil::FailureInfo *v26; // r9
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::details::IsDebuggerPresent(v24) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
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
0x180013c38  mov     [rsp+arg_10], rbx
0x180013c3d  mov     [rsp+arg_8], edx
0x180013c41  mov     [rsp+arg_0], rcx
0x180013c46  push    rbp
0x180013c47  push    rsi
0x180013c48  push    rdi
0x180013c49  push    r12
0x180013c4b  push    r13
0x180013c4d  push    r14
0x180013c4f  push    r15
0x180013c51  sub     rsp, 40h
0x180013c55  mov     r12, r9
0x180013c58  mov     r13, r8
0x180013c5b  mov     r10, rcx
0x180013c5e  xor     eax, eax
0x180013c60  mov     rsi, [rsp+78h+lpOutputString]
0x180013c68  mov     [rsi], ax
0x180013c6b  mov     rax, [rsp+78h+arg_60]
0x180013c73  mov     byte ptr [rax], 0
0x180013c76  mov     r14, [rsp+78h+arg_38]
0x180013c7e  mov     edi, [r14]
0x180013c81  mov     rbx, [rsp+78h+arg_78]
0x180013c89  mov     [rbx+8], edi
0x180013c8c  mov     eax, [r14+4]
0x180013c90  mov     [rbx+0Ch], eax
0x180013c93  xor     ebp, ebp
0x180013c95  mov     r15d, [rsp+78h+arg_30]
0x180013c9d  mov     ecx, r15d
0x180013ca0  test    r15d, r15d
0x180013ca3  jz      short loc_180013D0B
0x180013ca5  sub     ecx, 1
0x180013ca8  jz      short loc_180013D02
0x180013caa  sub     ecx, 1
0x180013cad  jz      short loc_180013CBD
0x180013caf  cmp     ecx, 1
0x180013cb2  jnz     short loc_180013D14
0x180013cb4  mov     ecx, edi; this
0x180013cb6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180013cbb  jmp     short loc_180013D12
0x180013cbd  test    edi, edi
0x180013cbf  js      short loc_180013CF9
0x180013cc1  mov     edi, 8007029Ch
0x180013cc6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180013cca  mov     rax, [rsp+78h+arg_28]
0x180013cd2  mov     [rsp+78h+var_50], rax; __int64
0x180013cd7  mov     rax, [rsp+78h+arg_20]
0x180013cdf  mov     [rsp+78h+var_58], rax; __int64
0x180013ce4  mov     rcx, r10; int
0x180013ce7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180013cec  mov     [rbx+8], edi
0x180013cef  mov     ecx, edi; this
0x180013cf1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013cf6  mov     [rbx+0Ch], eax
0x180013cf9  mov     ecx, edi; this
0x180013cfb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180013d00  jmp     short loc_180013D12
0x180013d02  mov     ecx, edi; this
0x180013d04  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013d09  jmp     short loc_180013D12
0x180013d0b  mov     ecx, edi; this
0x180013d0d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180013d12  mov     ebp, eax
0x180013d14  mov     [rbx], r15d
0x180013d17  mov     eax, [rsp+78h+arg_70]
0x180013d1e  mov     [rbx+4], eax
0x180013d21  cmp     dword ptr [r14+8], 1
0x180013d26  jnz     short loc_180013D2E
0x180013d28  or      eax, 8
0x180013d2b  mov     [rbx+4], eax
0x180013d2e  mov     eax, 1
0x180013d33  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013d3b  inc     eax
0x180013d3d  mov     [rbx+10h], eax
0x180013d40  mov     rax, [rsp+78h+arg_40]
0x180013d48  xor     edi, edi
0x180013d4a  test    rax, rax
0x180013d4d  jz      short loc_180013D54
0x180013d4f  cmp     [rax], di
0x180013d52  jnz     short loc_180013D57
0x180013d54  mov     rax, rdi
0x180013d57  mov     [rbx+18h], rax
0x180013d5b  call    cs:__imp_GetCurrentThreadId
0x180013d61  mov     [rbx+20h], eax
0x180013d64  mov     [rbx+38h], r13
0x180013d68  mov     eax, [rsp+78h+arg_8]
0x180013d6f  mov     [rbx+40h], eax
0x180013d72  mov     [rbx+44h], ebp
0x180013d75  mov     rax, [rsp+78h+arg_20]
0x180013d7d  mov     [rbx+28h], rax
0x180013d81  mov     [rbx+30h], r12
0x180013d85  mov     rax, [rsp+78h+arg_28]
0x180013d8d  mov     [rbx+88h], rax
0x180013d94  mov     rax, [rsp+78h+arg_0]
0x180013d9c  mov     [rbx+90h], rax
0x180013da3  mov     [rbx+48h], rdi
0x180013da7  xorps   xmm0, xmm0
0x180013daa  xor     eax, eax
0x180013dac  movups  xmmword ptr [rbx+68h], xmm0
0x180013db0  mov     [rbx+78h], rax
0x180013db4  movups  xmmword ptr [rbx+50h], xmm0
0x180013db8  mov     [rbx+60h], rax
0x180013dbc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013dc3  test    rax, rax
0x180013dc6  jz      short loc_180013DCF
0x180013dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dcd  jmp     short loc_180013DD2
0x180013dcf  mov     rax, rdi
0x180013dd2  mov     [rbx+80h], rax
0x180013dd9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013de0  test    rax, rax
0x180013de3  jz      short loc_180013DED
0x180013de5  mov     rcx, rbx
0x180013de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ded  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013df4  test    rax, rax
0x180013df7  jz      short loc_180013E0F
0x180013df9  mov     r8d, 400h
0x180013dff  mov     rdx, [rsp+78h+arg_60]
0x180013e07  mov     rcx, rbx
0x180013e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e0f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013e16  test    rax, rax
0x180013e19  jz      short loc_180013E23
0x180013e1b  mov     rcx, rbx
0x180013e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e23  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013e2a  test    rax, rax
0x180013e2d  jz      short loc_180013E3D
0x180013e2f  test    byte ptr [rbx+4], 2
0x180013e33  jnz     short loc_180013E3D
0x180013e35  mov     rcx, rbx
0x180013e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e3d  cmp     [rbx+8], edi
0x180013e40  jl      short loc_180013E5C
0x180013e42  cmp     r15d, 3
0x180013e46  jnz     loc_180013F0C
0x180013e4c  mov     ecx, 8000FFFFh; this
0x180013e51  mov     [rbx+8], ecx
0x180013e54  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013e59  mov     [rbx+0Ch], eax
0x180013e5c  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x180013e61  test    al, al
0x180013e63  jz      short loc_180013EB1
0x180013e65  test    byte ptr [rbx+4], 2
0x180013e69  jnz     short loc_180013EB1
0x180013e6b  mov     ebp, 800h
0x180013e70  mov     rax, cs:g_pfnResultLoggingCallback
0x180013e77  test    rax, rax
0x180013e7a  jz      short loc_180013E93
0x180013e7c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013e83  jnz     short loc_180013E93
0x180013e85  mov     r8d, ebp
0x180013e88  mov     rdx, rsi
0x180013e8b  mov     rcx, rbx
0x180013e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e93  cmp     [rsi], di
0x180013e96  jnz     short loc_180013EA6
0x180013e98  mov     r8, rbx; unsigned __int64
0x180013e9b  mov     rdx, rbp; unsigned __int16 *
0x180013e9e  mov     rcx, rsi; this
0x180013ea1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013ea6  mov     rcx, rsi; lpOutputString
0x180013ea9  call    cs:__imp_OutputDebugStringW
0x180013eaf  jmp     short loc_180013ED3
0x180013eb1  mov     rax, cs:g_pfnResultLoggingCallback
0x180013eb8  test    rax, rax
0x180013ebb  jz      short loc_180013ED3
0x180013ebd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013ec4  jnz     short loc_180013ED3
0x180013ec6  xor     r8d, r8d
0x180013ec9  xor     edx, edx
0x180013ecb  mov     rcx, rbx
0x180013ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ed3  test    byte ptr [rbx+4], 4
0x180013ed7  jnz     short loc_180013EE2
0x180013ed9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180013ee0  jz      short loc_180013EF4
0x180013ee2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013ee9  test    rax, rax
0x180013eec  jz      short loc_180013EF4
0x180013eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ef3  nop
0x180013ef4  mov     rbx, [rsp+78h+arg_10]
0x180013efc  add     rsp, 40h
0x180013f00  pop     r15
0x180013f02  pop     r14
0x180013f04  pop     r13
0x180013f06  pop     r12
0x180013f08  pop     rdi
0x180013f09  pop     rsi
0x180013f0a  pop     rbp
0x180013f0b  retn
0x180013f0c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
