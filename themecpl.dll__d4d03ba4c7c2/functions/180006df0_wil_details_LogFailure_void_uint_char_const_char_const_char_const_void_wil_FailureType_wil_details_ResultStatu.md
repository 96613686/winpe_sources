# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006df0`
- end: `0x1800070fc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800052cc`

## callees

- `0x180004cb0`
- `0x180006374`
- `0x180006c2c`
- `0x180006df0`
- `0x180007450`
- `0x180007470`
- `0x180007484`
- `0x1800074a4`
- `0x1800086c4`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f13`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070b0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070b0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007038`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007038`

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
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x180006df0  mov     [rsp+arg_10], rbx
0x180006df5  mov     [rsp+arg_8], edx
0x180006df9  mov     [rsp+arg_0], rcx
0x180006dfe  push    rbp
0x180006dff  push    rsi
0x180006e00  push    rdi
0x180006e01  push    r12
0x180006e03  push    r13
0x180006e05  push    r14
0x180006e07  push    r15
0x180006e09  sub     rsp, 40h
0x180006e0d  mov     r12, r9
0x180006e10  mov     r13, r8
0x180006e13  mov     r10, rcx
0x180006e16  xor     eax, eax
0x180006e18  mov     rsi, [rsp+78h+lpOutputString]
0x180006e20  mov     [rsi], ax
0x180006e23  mov     rax, [rsp+78h+arg_60]
0x180006e2b  mov     byte ptr [rax], 0
0x180006e2e  mov     r14, [rsp+78h+arg_38]
0x180006e36  mov     edi, [r14]
0x180006e39  mov     rbx, [rsp+78h+arg_78]
0x180006e41  mov     [rbx+8], edi
0x180006e44  mov     eax, [r14+4]
0x180006e48  mov     [rbx+0Ch], eax
0x180006e4b  xor     ebp, ebp
0x180006e4d  mov     r15d, [rsp+78h+arg_30]
0x180006e55  mov     ecx, r15d
0x180006e58  test    r15d, r15d
0x180006e5b  jz      short loc_180006EC3
0x180006e5d  sub     ecx, 1
0x180006e60  jz      short loc_180006EBA
0x180006e62  sub     ecx, 1
0x180006e65  jz      short loc_180006E75
0x180006e67  cmp     ecx, 1
0x180006e6a  jnz     short loc_180006ECC
0x180006e6c  mov     ecx, edi; this
0x180006e6e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006e73  jmp     short loc_180006ECA
0x180006e75  test    edi, edi
0x180006e77  js      short loc_180006EB1
0x180006e79  mov     edi, 8007029Ch
0x180006e7e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006e82  mov     rax, [rsp+78h+arg_28]
0x180006e8a  mov     [rsp+78h+var_50], rax; __int64
0x180006e8f  mov     rax, [rsp+78h+arg_20]
0x180006e97  mov     [rsp+78h+var_58], rax; __int64
0x180006e9c  mov     rcx, r10; int
0x180006e9f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006ea4  mov     [rbx+8], edi
0x180006ea7  mov     ecx, edi; this
0x180006ea9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006eae  mov     [rbx+0Ch], eax
0x180006eb1  mov     ecx, edi; this
0x180006eb3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006eb8  jmp     short loc_180006ECA
0x180006eba  mov     ecx, edi; this
0x180006ebc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ec1  jmp     short loc_180006ECA
0x180006ec3  mov     ecx, edi; this
0x180006ec5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006eca  mov     ebp, eax
0x180006ecc  mov     [rbx], r15d
0x180006ecf  mov     eax, [rsp+78h+arg_70]
0x180006ed6  mov     [rbx+4], eax
0x180006ed9  cmp     dword ptr [r14+8], 1
0x180006ede  jnz     short loc_180006EE6
0x180006ee0  or      eax, 8
0x180006ee3  mov     [rbx+4], eax
0x180006ee6  mov     eax, 1
0x180006eeb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006ef3  inc     eax
0x180006ef5  mov     [rbx+10h], eax
0x180006ef8  mov     rax, [rsp+78h+arg_40]
0x180006f00  xor     edi, edi
0x180006f02  test    rax, rax
0x180006f05  jz      short loc_180006F0C
0x180006f07  cmp     [rax], di
0x180006f0a  jnz     short loc_180006F0F
0x180006f0c  mov     rax, rdi
0x180006f0f  mov     [rbx+18h], rax
0x180006f13  call    cs:__imp_GetCurrentThreadId
0x180006f1a  nop     dword ptr [rax+rax+00h]
0x180006f1f  mov     [rbx+20h], eax
0x180006f22  mov     [rbx+38h], r13
0x180006f26  mov     eax, [rsp+78h+arg_8]
0x180006f2d  mov     [rbx+40h], eax
0x180006f30  mov     [rbx+44h], ebp
0x180006f33  mov     rax, [rsp+78h+arg_20]
0x180006f3b  mov     [rbx+28h], rax
0x180006f3f  mov     [rbx+30h], r12
0x180006f43  mov     rax, [rsp+78h+arg_28]
0x180006f4b  mov     [rbx+88h], rax
0x180006f52  mov     rax, [rsp+78h+arg_0]
0x180006f5a  mov     [rbx+90h], rax
0x180006f61  mov     [rbx+48h], rdi
0x180006f65  xorps   xmm0, xmm0
0x180006f68  xor     eax, eax
0x180006f6a  movups  xmmword ptr [rbx+68h], xmm0
0x180006f6e  mov     [rbx+78h], rax
0x180006f72  movups  xmmword ptr [rbx+50h], xmm0
0x180006f76  mov     [rbx+60h], rax
0x180006f7a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006f81  test    rax, rax
0x180006f84  jz      short loc_180006F8D
0x180006f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f8b  jmp     short loc_180006F90
0x180006f8d  mov     rax, rdi
0x180006f90  mov     [rbx+80h], rax
0x180006f97  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006f9e  test    rax, rax
0x180006fa1  jz      short loc_180006FAB
0x180006fa3  mov     rcx, rbx
0x180006fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fab  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006fb2  test    rax, rax
0x180006fb5  jz      short loc_180006FCD
0x180006fb7  mov     r8d, 400h
0x180006fbd  mov     rdx, [rsp+78h+arg_60]
0x180006fc5  mov     rcx, rbx
0x180006fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fcd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006fd4  test    rax, rax
0x180006fd7  jz      short loc_180006FE1
0x180006fd9  mov     rcx, rbx
0x180006fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006fe8  test    rax, rax
0x180006feb  jz      short loc_180006FFB
0x180006fed  test    byte ptr [rbx+4], 2
0x180006ff1  jnz     short loc_180006FFB
0x180006ff3  mov     rcx, rbx
0x180006ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffb  cmp     [rbx+8], edi
0x180006ffe  jl      short loc_18000701A
0x180007000  cmp     r15d, 3
0x180007004  jnz     loc_1800070F6
0x18000700a  mov     ecx, 8000FFFFh; this
0x18000700f  mov     [rbx+8], ecx
0x180007012  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007017  mov     [rbx+0Ch], eax
0x18000701a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007021  jnz     short loc_180007048
0x180007023  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000702a  test    rax, rax
0x18000702d  jz      short loc_180007038
0x18000702f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007034  test    al, al
0x180007036  jmp     short loc_180007046
0x180007038  call    cs:__imp_IsDebuggerPresent
0x18000703f  nop     dword ptr [rax+rax+00h]
0x180007044  test    eax, eax
0x180007046  jz      short loc_18000704E
0x180007048  test    byte ptr [rbx+4], 2
0x18000704c  jz      short loc_180007072
0x18000704e  mov     rax, cs:g_pfnResultLoggingCallback
0x180007055  test    rax, rax
0x180007058  jz      short loc_1800070BC
0x18000705a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007061  jnz     short loc_1800070BC
0x180007063  xor     r8d, r8d
0x180007066  xor     edx, edx
0x180007068  mov     rcx, rbx
0x18000706b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007070  jmp     short loc_1800070BC
0x180007072  mov     ebp, 800h
0x180007077  mov     rax, cs:g_pfnResultLoggingCallback
0x18000707e  test    rax, rax
0x180007081  jz      short loc_18000709A
0x180007083  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000708a  jnz     short loc_18000709A
0x18000708c  mov     r8d, ebp
0x18000708f  mov     rdx, rsi
0x180007092  mov     rcx, rbx
0x180007095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000709a  cmp     [rsi], di
0x18000709d  jnz     short loc_1800070AD
0x18000709f  mov     r8, rbx; unsigned __int64
0x1800070a2  mov     rdx, rbp; unsigned __int16 *
0x1800070a5  mov     rcx, rsi; this
0x1800070a8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800070ad  mov     rcx, rsi; lpOutputString
0x1800070b0  call    cs:__imp_OutputDebugStringW
0x1800070b7  nop     dword ptr [rax+rax+00h]
0x1800070bc  test    byte ptr [rbx+4], 4
0x1800070c0  jnz     short loc_1800070CB
0x1800070c2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800070c9  jz      short loc_1800070DD
0x1800070cb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800070d2  test    rax, rax
0x1800070d5  jz      short loc_1800070DD
0x1800070d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070dc  nop
0x1800070dd  mov     rbx, [rsp+78h+arg_10]
0x1800070e5  add     rsp, 40h
0x1800070e9  pop     r15
0x1800070eb  pop     r14
0x1800070ed  pop     r13
0x1800070ef  pop     r12
0x1800070f1  pop     rdi
0x1800070f2  pop     rsi
0x1800070f3  pop     rbp
0x1800070f4  retn
0x1800070f6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
