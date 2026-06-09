# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000de3c`
- end: `0x18000e148`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000b660`
- `0x18000b9e0`

## callees

- `0x180007b7c`
- `0x180009b44`
- `0x18000a150`
- `0x18000b598`
- `0x18000de3c`
- `0x18000f098`
- `0x18000f250`
- `0x18000f270`
- `0x180010c64`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000df5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000df5f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e084`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e084`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e0fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e0fc`

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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18000de3c  mov     [rsp+arg_10], rbx
0x18000de41  mov     [rsp+arg_8], edx
0x18000de45  mov     [rsp+arg_0], rcx
0x18000de4a  push    rbp
0x18000de4b  push    rsi
0x18000de4c  push    rdi
0x18000de4d  push    r12
0x18000de4f  push    r13
0x18000de51  push    r14
0x18000de53  push    r15
0x18000de55  sub     rsp, 40h
0x18000de59  mov     r12, r9
0x18000de5c  mov     r13, r8
0x18000de5f  mov     r10, rcx
0x18000de62  xor     eax, eax
0x18000de64  mov     rsi, [rsp+78h+lpOutputString]
0x18000de6c  mov     [rsi], ax
0x18000de6f  mov     rax, [rsp+78h+arg_60]
0x18000de77  mov     byte ptr [rax], 0
0x18000de7a  mov     r14, [rsp+78h+arg_38]
0x18000de82  mov     edi, [r14]
0x18000de85  mov     rbx, [rsp+78h+arg_78]
0x18000de8d  mov     [rbx+8], edi
0x18000de90  mov     eax, [r14+4]
0x18000de94  mov     [rbx+0Ch], eax
0x18000de97  xor     ebp, ebp
0x18000de99  mov     r15d, [rsp+78h+arg_30]
0x18000dea1  mov     ecx, r15d
0x18000dea4  test    r15d, r15d
0x18000dea7  jz      short loc_18000DF0F
0x18000dea9  sub     ecx, 1
0x18000deac  jz      short loc_18000DF06
0x18000deae  sub     ecx, 1
0x18000deb1  jz      short loc_18000DEC1
0x18000deb3  cmp     ecx, 1
0x18000deb6  jnz     short loc_18000DF18
0x18000deb8  mov     ecx, edi; this
0x18000deba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000debf  jmp     short loc_18000DF16
0x18000dec1  test    edi, edi
0x18000dec3  js      short loc_18000DEFD
0x18000dec5  mov     edi, 8007029Ch
0x18000deca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000dece  mov     rax, [rsp+78h+arg_28]
0x18000ded6  mov     [rsp+78h+var_50], rax; __int64
0x18000dedb  mov     rax, [rsp+78h+arg_20]
0x18000dee3  mov     [rsp+78h+var_58], rax; __int64
0x18000dee8  mov     rcx, r10; int
0x18000deeb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000def0  mov     [rbx+8], edi
0x18000def3  mov     ecx, edi; this
0x18000def5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000defa  mov     [rbx+0Ch], eax
0x18000defd  mov     ecx, edi; this
0x18000deff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000df04  jmp     short loc_18000DF16
0x18000df06  mov     ecx, edi; this
0x18000df08  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000df0d  jmp     short loc_18000DF16
0x18000df0f  mov     ecx, edi; this
0x18000df11  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000df16  mov     ebp, eax
0x18000df18  mov     [rbx], r15d
0x18000df1b  mov     eax, [rsp+78h+arg_70]
0x18000df22  mov     [rbx+4], eax
0x18000df25  cmp     dword ptr [r14+8], 1
0x18000df2a  jnz     short loc_18000DF32
0x18000df2c  or      eax, 8
0x18000df2f  mov     [rbx+4], eax
0x18000df32  mov     eax, 1
0x18000df37  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000df3f  inc     eax
0x18000df41  mov     [rbx+10h], eax
0x18000df44  mov     rax, [rsp+78h+arg_40]
0x18000df4c  xor     edi, edi
0x18000df4e  test    rax, rax
0x18000df51  jz      short loc_18000DF58
0x18000df53  cmp     [rax], di
0x18000df56  jnz     short loc_18000DF5B
0x18000df58  mov     rax, rdi
0x18000df5b  mov     [rbx+18h], rax
0x18000df5f  call    cs:__imp_GetCurrentThreadId
0x18000df66  nop     dword ptr [rax+rax+00h]
0x18000df6b  mov     [rbx+20h], eax
0x18000df6e  mov     [rbx+38h], r13
0x18000df72  mov     eax, [rsp+78h+arg_8]
0x18000df79  mov     [rbx+40h], eax
0x18000df7c  mov     [rbx+44h], ebp
0x18000df7f  mov     rax, [rsp+78h+arg_20]
0x18000df87  mov     [rbx+28h], rax
0x18000df8b  mov     [rbx+30h], r12
0x18000df8f  mov     rax, [rsp+78h+arg_28]
0x18000df97  mov     [rbx+88h], rax
0x18000df9e  mov     rax, [rsp+78h+arg_0]
0x18000dfa6  mov     [rbx+90h], rax
0x18000dfad  mov     [rbx+48h], rdi
0x18000dfb1  xorps   xmm0, xmm0
0x18000dfb4  xor     eax, eax
0x18000dfb6  movups  xmmword ptr [rbx+68h], xmm0
0x18000dfba  mov     [rbx+78h], rax
0x18000dfbe  movups  xmmword ptr [rbx+50h], xmm0
0x18000dfc2  mov     [rbx+60h], rax
0x18000dfc6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000dfcd  test    rax, rax
0x18000dfd0  jz      short loc_18000DFD9
0x18000dfd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd7  jmp     short loc_18000DFDC
0x18000dfd9  mov     rax, rdi
0x18000dfdc  mov     [rbx+80h], rax
0x18000dfe3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000dfea  test    rax, rax
0x18000dfed  jz      short loc_18000DFF7
0x18000dfef  mov     rcx, rbx
0x18000dff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dff7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000dffe  test    rax, rax
0x18000e001  jz      short loc_18000E019
0x18000e003  mov     r8d, 400h
0x18000e009  mov     rdx, [rsp+78h+arg_60]
0x18000e011  mov     rcx, rbx
0x18000e014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e019  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e020  test    rax, rax
0x18000e023  jz      short loc_18000E02D
0x18000e025  mov     rcx, rbx
0x18000e028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e02d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e034  test    rax, rax
0x18000e037  jz      short loc_18000E047
0x18000e039  test    byte ptr [rbx+4], 2
0x18000e03d  jnz     short loc_18000E047
0x18000e03f  mov     rcx, rbx
0x18000e042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e047  cmp     [rbx+8], edi
0x18000e04a  jl      short loc_18000E066
0x18000e04c  cmp     r15d, 3
0x18000e050  jnz     loc_18000E142
0x18000e056  mov     ecx, 8000FFFFh; this
0x18000e05b  mov     [rbx+8], ecx
0x18000e05e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e063  mov     [rbx+0Ch], eax
0x18000e066  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e06d  jnz     short loc_18000E094
0x18000e06f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e076  test    rax, rax
0x18000e079  jz      short loc_18000E084
0x18000e07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e080  test    al, al
0x18000e082  jmp     short loc_18000E092
0x18000e084  call    cs:__imp_IsDebuggerPresent
0x18000e08b  nop     dword ptr [rax+rax+00h]
0x18000e090  test    eax, eax
0x18000e092  jz      short loc_18000E09A
0x18000e094  test    byte ptr [rbx+4], 2
0x18000e098  jz      short loc_18000E0BE
0x18000e09a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e0a1  test    rax, rax
0x18000e0a4  jz      short loc_18000E108
0x18000e0a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e0ad  jnz     short loc_18000E108
0x18000e0af  xor     r8d, r8d
0x18000e0b2  xor     edx, edx
0x18000e0b4  mov     rcx, rbx
0x18000e0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0bc  jmp     short loc_18000E108
0x18000e0be  mov     ebp, 800h
0x18000e0c3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e0ca  test    rax, rax
0x18000e0cd  jz      short loc_18000E0E6
0x18000e0cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e0d6  jnz     short loc_18000E0E6
0x18000e0d8  mov     r8d, ebp
0x18000e0db  mov     rdx, rsi
0x18000e0de  mov     rcx, rbx
0x18000e0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e6  cmp     [rsi], di
0x18000e0e9  jnz     short loc_18000E0F9
0x18000e0eb  mov     r8, rbx; unsigned __int64
0x18000e0ee  mov     rdx, rbp; unsigned __int16 *
0x18000e0f1  mov     rcx, rsi; this
0x18000e0f4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e0f9  mov     rcx, rsi; lpOutputString
0x18000e0fc  call    cs:__imp_OutputDebugStringW
0x18000e103  nop     dword ptr [rax+rax+00h]
0x18000e108  test    byte ptr [rbx+4], 4
0x18000e10c  jnz     short loc_18000E117
0x18000e10e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e115  jz      short loc_18000E129
0x18000e117  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e11e  test    rax, rax
0x18000e121  jz      short loc_18000E129
0x18000e123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e128  nop
0x18000e129  mov     rbx, [rsp+78h+arg_10]
0x18000e131  add     rsp, 40h
0x18000e135  pop     r15
0x18000e137  pop     r14
0x18000e139  pop     r13
0x18000e13b  pop     r12
0x18000e13d  pop     rdi
0x18000e13e  pop     rsi
0x18000e13f  pop     rbp
0x18000e140  retn
0x18000e142  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
