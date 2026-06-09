# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180010ce8`
- end: `0x180010fe5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001009c`
- `0x1800103f8`

## callees

- `0x1800092b4`
- `0x18000d01c`
- `0x18000f314`
- `0x18000f750`
- `0x180010ce8`
- `0x180011180`
- `0x18001119c`
- `0x1800111b8`
- `0x18001182c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010e0f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010f2e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010f2e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010fa0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010fa0`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x180010ce8  mov     [rsp+arg_10], rbx
0x180010ced  mov     [rsp+arg_8], edx
0x180010cf1  mov     [rsp+arg_0], rcx
0x180010cf6  push    rbp
0x180010cf7  push    rsi
0x180010cf8  push    rdi
0x180010cf9  push    r12
0x180010cfb  push    r13
0x180010cfd  push    r14
0x180010cff  push    r15
0x180010d01  sub     rsp, 40h
0x180010d05  mov     r12, r9
0x180010d08  mov     r13, r8
0x180010d0b  mov     r10, rcx
0x180010d0e  xor     eax, eax
0x180010d10  mov     rsi, [rsp+78h+lpOutputString]
0x180010d18  mov     [rsi], ax
0x180010d1b  mov     rax, [rsp+78h+arg_60]
0x180010d23  mov     byte ptr [rax], 0
0x180010d26  mov     r14, [rsp+78h+arg_38]
0x180010d2e  mov     edi, [r14]
0x180010d31  mov     rbx, [rsp+78h+arg_78]
0x180010d39  mov     [rbx+8], edi
0x180010d3c  mov     eax, [r14+4]
0x180010d40  mov     [rbx+0Ch], eax
0x180010d43  xor     ebp, ebp
0x180010d45  mov     r15d, [rsp+78h+arg_30]
0x180010d4d  mov     ecx, r15d
0x180010d50  test    r15d, r15d
0x180010d53  jz      short loc_180010DBF
0x180010d55  sub     ecx, 1
0x180010d58  jz      short loc_180010DB6
0x180010d5a  sub     ecx, 1
0x180010d5d  jz      short loc_180010D6D
0x180010d5f  cmp     ecx, 1
0x180010d62  jnz     short loc_180010DC8
0x180010d64  mov     ecx, edi; this
0x180010d66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180010d6b  jmp     short loc_180010DC6
0x180010d6d  test    edi, edi
0x180010d6f  js      short loc_180010DAD
0x180010d71  mov     [rsp+78h+var_40], ebp
0x180010d75  mov     edi, 8007029Ch
0x180010d7a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180010d7e  mov     rax, [rsp+78h+arg_28]
0x180010d86  mov     [rsp+78h+var_50], rax; __int64
0x180010d8b  mov     rax, [rsp+78h+arg_20]
0x180010d93  mov     [rsp+78h+var_58], rax; __int64
0x180010d98  mov     rcx, r10; int
0x180010d9b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180010da0  mov     [rbx+8], edi
0x180010da3  mov     ecx, edi; this
0x180010da5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010daa  mov     [rbx+0Ch], eax
0x180010dad  mov     ecx, edi; this
0x180010daf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180010db4  jmp     short loc_180010DC6
0x180010db6  mov     ecx, edi; this
0x180010db8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180010dbd  jmp     short loc_180010DC6
0x180010dbf  mov     ecx, edi; this
0x180010dc1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180010dc6  mov     ebp, eax
0x180010dc8  mov     [rbx], r15d
0x180010dcb  mov     eax, [rsp+78h+arg_70]
0x180010dd2  mov     [rbx+4], eax
0x180010dd5  cmp     dword ptr [r14+8], 1
0x180010dda  jnz     short loc_180010DE2
0x180010ddc  or      eax, 8
0x180010ddf  mov     [rbx+4], eax
0x180010de2  mov     eax, 1
0x180010de7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010def  inc     eax
0x180010df1  mov     [rbx+10h], eax
0x180010df4  mov     rax, [rsp+78h+arg_40]
0x180010dfc  xor     edi, edi
0x180010dfe  test    rax, rax
0x180010e01  jz      short loc_180010E08
0x180010e03  cmp     [rax], di
0x180010e06  jnz     short loc_180010E0B
0x180010e08  mov     rax, rdi
0x180010e0b  mov     [rbx+18h], rax
0x180010e0f  call    cs:__imp_GetCurrentThreadId
0x180010e15  mov     [rbx+20h], eax
0x180010e18  mov     [rbx+38h], r13
0x180010e1c  mov     eax, [rsp+78h+arg_8]
0x180010e23  mov     [rbx+40h], eax
0x180010e26  mov     [rbx+44h], ebp
0x180010e29  mov     rax, [rsp+78h+arg_20]
0x180010e31  mov     [rbx+28h], rax
0x180010e35  mov     [rbx+30h], r12
0x180010e39  mov     rax, [rsp+78h+arg_28]
0x180010e41  mov     [rbx+88h], rax
0x180010e48  mov     rax, [rsp+78h+arg_0]
0x180010e50  mov     [rbx+90h], rax
0x180010e57  mov     [rbx+48h], rdi
0x180010e5b  xorps   xmm0, xmm0
0x180010e5e  xor     eax, eax
0x180010e60  movups  xmmword ptr [rbx+68h], xmm0
0x180010e64  mov     [rbx+78h], rax
0x180010e68  movups  xmmword ptr [rbx+50h], xmm0
0x180010e6c  mov     [rbx+60h], rax
0x180010e70  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010e77  test    rax, rax
0x180010e7a  jz      short loc_180010E83
0x180010e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e81  jmp     short loc_180010E86
0x180010e83  mov     rax, rdi
0x180010e86  mov     [rbx+80h], rax
0x180010e8d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010e94  test    rax, rax
0x180010e97  jz      short loc_180010EA1
0x180010e99  mov     rcx, rbx
0x180010e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ea1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010ea8  test    rax, rax
0x180010eab  jz      short loc_180010EC3
0x180010ead  mov     r8d, 400h
0x180010eb3  mov     rdx, [rsp+78h+arg_60]
0x180010ebb  mov     rcx, rbx
0x180010ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ec3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010eca  test    rax, rax
0x180010ecd  jz      short loc_180010ED7
0x180010ecf  mov     rcx, rbx
0x180010ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ed7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010ede  test    rax, rax
0x180010ee1  jz      short loc_180010EF1
0x180010ee3  test    byte ptr [rbx+4], 2
0x180010ee7  jnz     short loc_180010EF1
0x180010ee9  mov     rcx, rbx
0x180010eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef1  cmp     [rbx+8], edi
0x180010ef4  jl      short loc_180010F10
0x180010ef6  cmp     r15d, 3
0x180010efa  jnz     loc_180010FDF
0x180010f00  mov     ecx, 8000FFFFh; this
0x180010f05  mov     [rbx+8], ecx
0x180010f08  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010f0d  mov     [rbx+0Ch], eax
0x180010f10  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180010f17  jnz     short loc_180010F38
0x180010f19  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010f20  test    rax, rax
0x180010f23  jz      short loc_180010F2E
0x180010f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f2a  test    al, al
0x180010f2c  jmp     short loc_180010F36
0x180010f2e  call    cs:__imp_IsDebuggerPresent
0x180010f34  test    eax, eax
0x180010f36  jz      short loc_180010F3E
0x180010f38  test    byte ptr [rbx+4], 2
0x180010f3c  jz      short loc_180010F62
0x180010f3e  mov     rax, cs:g_pfnResultLoggingCallback
0x180010f45  test    rax, rax
0x180010f48  jz      short loc_180010FA6
0x180010f4a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010f51  jnz     short loc_180010FA6
0x180010f53  xor     r8d, r8d
0x180010f56  xor     edx, edx
0x180010f58  mov     rcx, rbx
0x180010f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f60  jmp     short loc_180010FA6
0x180010f62  mov     ebp, 800h
0x180010f67  mov     rax, cs:g_pfnResultLoggingCallback
0x180010f6e  test    rax, rax
0x180010f71  jz      short loc_180010F8A
0x180010f73  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010f7a  jnz     short loc_180010F8A
0x180010f7c  mov     r8d, ebp
0x180010f7f  mov     rdx, rsi
0x180010f82  mov     rcx, rbx
0x180010f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f8a  cmp     [rsi], di
0x180010f8d  jnz     short loc_180010F9D
0x180010f8f  mov     r8, rbx; unsigned __int64
0x180010f92  mov     rdx, rbp; unsigned __int16 *
0x180010f95  mov     rcx, rsi; this
0x180010f98  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010f9d  mov     rcx, rsi; lpOutputString
0x180010fa0  call    cs:__imp_OutputDebugStringW
0x180010fa6  test    byte ptr [rbx+4], 4
0x180010faa  jnz     short loc_180010FB5
0x180010fac  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180010fb3  jz      short loc_180010FC7
0x180010fb5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010fbc  test    rax, rax
0x180010fbf  jz      short loc_180010FC7
0x180010fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fc6  nop
0x180010fc7  mov     rbx, [rsp+78h+arg_10]
0x180010fcf  add     rsp, 40h
0x180010fd3  pop     r15
0x180010fd5  pop     r14
0x180010fd7  pop     r13
0x180010fd9  pop     r12
0x180010fdb  pop     rdi
0x180010fdc  pop     rsi
0x180010fdd  pop     rbp
0x180010fde  retn
0x180010fdf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
