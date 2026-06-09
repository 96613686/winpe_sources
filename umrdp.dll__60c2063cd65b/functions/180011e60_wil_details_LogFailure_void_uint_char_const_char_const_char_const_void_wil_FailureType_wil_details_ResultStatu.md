# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011e60`
- end: `0x180012154`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000fb78`
- `0x18000fc2c`
- `0x18000fd20`

## callees

- `0x18000bad8`
- `0x18000fac8`
- `0x180010f34`
- `0x180011e60`
- `0x180012810`
- `0x180012830`
- `0x180012844`
- `0x180012860`
- `0x1800139ac`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f83`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800120a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800120a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012116`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012116`

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
0x180011e60  mov     [rsp+arg_10], rbx
0x180011e65  mov     [rsp+arg_8], edx
0x180011e69  mov     [rsp+arg_0], rcx
0x180011e6e  push    rbp
0x180011e6f  push    rsi
0x180011e70  push    rdi
0x180011e71  push    r12
0x180011e73  push    r13
0x180011e75  push    r14
0x180011e77  push    r15
0x180011e79  sub     rsp, 40h
0x180011e7d  mov     r14, [rsp+78h+arg_38]
0x180011e85  xor     eax, eax
0x180011e87  mov     rbx, [rsp+78h+arg_78]
0x180011e8f  xor     ebp, ebp
0x180011e91  mov     r15d, [rsp+78h+arg_30]
0x180011e99  mov     r10, rcx
0x180011e9c  mov     rsi, [rsp+78h+lpOutputString]
0x180011ea4  mov     r12, r9
0x180011ea7  mov     r13, r8
0x180011eaa  mov     ecx, r15d
0x180011ead  mov     [rsi], ax
0x180011eb0  mov     rax, [rsp+78h+arg_60]
0x180011eb8  mov     byte ptr [rax], 0
0x180011ebb  mov     edi, [r14]
0x180011ebe  mov     [rbx+8], edi
0x180011ec1  mov     eax, [r14+4]
0x180011ec5  mov     [rbx+0Ch], eax
0x180011ec8  test    r15d, r15d
0x180011ecb  jz      short loc_180011F33
0x180011ecd  sub     ecx, 1
0x180011ed0  jz      short loc_180011F2A
0x180011ed2  sub     ecx, 1
0x180011ed5  jz      short loc_180011EE5
0x180011ed7  cmp     ecx, 1
0x180011eda  jnz     short loc_180011F3C
0x180011edc  mov     ecx, edi; this
0x180011ede  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011ee3  jmp     short loc_180011F3A
0x180011ee5  test    edi, edi
0x180011ee7  js      short loc_180011F21
0x180011ee9  mov     rax, [rsp+78h+arg_28]
0x180011ef1  mov     edi, 8007029Ch
0x180011ef6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011efa  mov     rcx, r10; int
0x180011efd  mov     [rsp+78h+var_50], rax; __int64
0x180011f02  mov     rax, [rsp+78h+arg_20]
0x180011f0a  mov     [rsp+78h+var_58], rax; __int64
0x180011f0f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011f14  mov     ecx, edi; this
0x180011f16  mov     [rbx+8], edi
0x180011f19  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011f1e  mov     [rbx+0Ch], eax
0x180011f21  mov     ecx, edi; this
0x180011f23  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011f28  jmp     short loc_180011F3A
0x180011f2a  mov     ecx, edi; this
0x180011f2c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011f31  jmp     short loc_180011F3A
0x180011f33  mov     ecx, edi; this
0x180011f35  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011f3a  mov     ebp, eax
0x180011f3c  mov     eax, [rsp+78h+arg_70]
0x180011f43  mov     [rbx+4], eax
0x180011f46  mov     [rbx], r15d
0x180011f49  cmp     dword ptr [r14+8], 1
0x180011f4e  jnz     short loc_180011F56
0x180011f50  or      eax, 8
0x180011f53  mov     [rbx+4], eax
0x180011f56  mov     eax, 1
0x180011f5b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011f63  inc     eax
0x180011f65  xor     edi, edi
0x180011f67  mov     [rbx+10h], eax
0x180011f6a  mov     rax, [rsp+78h+arg_40]
0x180011f72  test    rax, rax
0x180011f75  jz      short loc_180011F7C
0x180011f77  cmp     [rax], di
0x180011f7a  jnz     short loc_180011F7F
0x180011f7c  mov     rax, rdi
0x180011f7f  mov     [rbx+18h], rax
0x180011f83  call    cs:__imp_GetCurrentThreadId
0x180011f89  mov     [rbx+38h], r13
0x180011f8d  xorps   xmm0, xmm0
0x180011f90  mov     [rbx+20h], eax
0x180011f93  mov     eax, [rsp+78h+arg_8]
0x180011f9a  mov     [rbx+40h], eax
0x180011f9d  mov     rax, [rsp+78h+arg_20]
0x180011fa5  mov     [rbx+28h], rax
0x180011fa9  mov     rax, [rsp+78h+arg_28]
0x180011fb1  mov     [rbx+88h], rax
0x180011fb8  mov     rax, [rsp+78h+arg_0]
0x180011fc0  mov     [rbx+90h], rax
0x180011fc7  xor     eax, eax
0x180011fc9  mov     [rbx+44h], ebp
0x180011fcc  mov     [rbx+30h], r12
0x180011fd0  mov     [rbx+48h], rdi
0x180011fd4  movups  xmmword ptr [rbx+68h], xmm0
0x180011fd8  mov     [rbx+78h], rax
0x180011fdc  movups  xmmword ptr [rbx+50h], xmm0
0x180011fe0  mov     [rbx+60h], rax
0x180011fe4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011feb  test    rax, rax
0x180011fee  jz      short loc_180011FF7
0x180011ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ff5  jmp     short loc_180011FFA
0x180011ff7  mov     rax, rdi
0x180011ffa  mov     [rbx+80h], rax
0x180012001  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180012008  test    rax, rax
0x18001200b  jz      short loc_180012015
0x18001200d  mov     rcx, rbx
0x180012010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012015  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001201c  test    rax, rax
0x18001201f  jz      short loc_180012037
0x180012021  mov     rdx, [rsp+78h+arg_60]
0x180012029  mov     r8d, 400h
0x18001202f  mov     rcx, rbx
0x180012032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012037  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001203e  test    rax, rax
0x180012041  jz      short loc_18001204B
0x180012043  mov     rcx, rbx
0x180012046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001204b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012052  test    rax, rax
0x180012055  jz      short loc_180012065
0x180012057  test    byte ptr [rbx+4], 2
0x18001205b  jnz     short loc_180012065
0x18001205d  mov     rcx, rbx
0x180012060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012065  cmp     [rbx+8], edi
0x180012068  jl      short loc_180012086
0x18001206a  cmp     r15d, 3
0x18001206e  jz      short loc_180012076
0x180012070  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180012076  mov     ecx, 8000FFFFh; this
0x18001207b  mov     [rbx+8], ecx
0x18001207e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012083  mov     [rbx+0Ch], eax
0x180012086  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001208d  jnz     short loc_1800120AE
0x18001208f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180012096  test    rax, rax
0x180012099  jz      short loc_1800120A4
0x18001209b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a0  test    al, al
0x1800120a2  jmp     short loc_1800120AC
0x1800120a4  call    cs:__imp_IsDebuggerPresent
0x1800120aa  test    eax, eax
0x1800120ac  jz      short loc_1800120B4
0x1800120ae  test    byte ptr [rbx+4], 2
0x1800120b2  jz      short loc_1800120D8
0x1800120b4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800120bb  test    rax, rax
0x1800120be  jz      short loc_18001211C
0x1800120c0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800120c7  jnz     short loc_18001211C
0x1800120c9  xor     r8d, r8d
0x1800120cc  xor     edx, edx
0x1800120ce  mov     rcx, rbx
0x1800120d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120d6  jmp     short loc_18001211C
0x1800120d8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800120df  mov     ebp, 800h
0x1800120e4  test    rax, rax
0x1800120e7  jz      short loc_180012100
0x1800120e9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800120f0  jnz     short loc_180012100
0x1800120f2  mov     r8d, ebp
0x1800120f5  mov     rdx, rsi
0x1800120f8  mov     rcx, rbx
0x1800120fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012100  cmp     [rsi], di
0x180012103  jnz     short loc_180012113
0x180012105  mov     r8, rbx; unsigned __int64
0x180012108  mov     rdx, rbp; unsigned __int16 *
0x18001210b  mov     rcx, rsi; this
0x18001210e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180012113  mov     rcx, rsi; lpOutputString
0x180012116  call    cs:__imp_OutputDebugStringW
0x18001211c  test    byte ptr [rbx+4], 4
0x180012120  jnz     short loc_18001212B
0x180012122  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180012129  jz      short loc_18001213C
0x18001212b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012132  test    rax, rax
0x180012135  jz      short loc_18001213C
0x180012137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001213c  mov     rbx, [rsp+78h+arg_10]
0x180012144  add     rsp, 40h
0x180012148  pop     r15
0x18001214a  pop     r14
0x18001214c  pop     r13
0x18001214e  pop     r12
0x180012150  pop     rdi
0x180012151  pop     rsi
0x180012152  pop     rbp
0x180012153  retn
```
