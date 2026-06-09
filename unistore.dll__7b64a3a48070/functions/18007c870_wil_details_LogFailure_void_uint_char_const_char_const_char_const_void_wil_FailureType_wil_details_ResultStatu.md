# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18007c870`
- end: `0x18007cb68`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18007c1f0`
- `0x18007d678`

## callees

- `0x180067234`
- `0x18007bef8`
- `0x18007c5b4`
- `0x18007c870`
- `0x18007cd00`
- `0x18007cd20`
- `0x18007cd34`
- `0x18007cd50`
- `0x18007d15c`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c993`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007cab2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007cab2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18007cb24`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18007cb24`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x18007c870  mov     [rsp+arg_10], rbx
0x18007c875  mov     [rsp+arg_8], edx
0x18007c879  mov     [rsp+arg_0], rcx
0x18007c87e  push    rbp
0x18007c87f  push    rsi
0x18007c880  push    rdi
0x18007c881  push    r12
0x18007c883  push    r13
0x18007c885  push    r14
0x18007c887  push    r15
0x18007c889  sub     rsp, 40h
0x18007c88d  mov     r14, [rsp+78h+arg_38]
0x18007c895  xor     eax, eax
0x18007c897  mov     rbx, [rsp+78h+arg_78]
0x18007c89f  xor     ebp, ebp
0x18007c8a1  mov     r15d, [rsp+78h+arg_30]
0x18007c8a9  mov     r10, rcx
0x18007c8ac  mov     rsi, [rsp+78h+lpOutputString]
0x18007c8b4  mov     r12, r9
0x18007c8b7  mov     r13, r8
0x18007c8ba  mov     ecx, r15d
0x18007c8bd  mov     [rsi], ax
0x18007c8c0  mov     rax, [rsp+78h+arg_60]
0x18007c8c8  mov     byte ptr [rax], 0
0x18007c8cb  mov     edi, [r14]
0x18007c8ce  mov     [rbx+8], edi
0x18007c8d1  mov     eax, [r14+4]
0x18007c8d5  mov     [rbx+0Ch], eax
0x18007c8d8  test    r15d, r15d
0x18007c8db  jz      short loc_18007C943
0x18007c8dd  sub     ecx, 1
0x18007c8e0  jz      short loc_18007C93A
0x18007c8e2  sub     ecx, 1
0x18007c8e5  jz      short loc_18007C8F5
0x18007c8e7  cmp     ecx, 1
0x18007c8ea  jnz     short loc_18007C94C
0x18007c8ec  mov     ecx, edi; this
0x18007c8ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18007c8f3  jmp     short loc_18007C94A
0x18007c8f5  test    edi, edi
0x18007c8f7  js      short loc_18007C931
0x18007c8f9  mov     rax, [rsp+78h+arg_28]
0x18007c901  mov     edi, 8007029Ch
0x18007c906  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18007c90a  mov     rcx, r10; int
0x18007c90d  mov     [rsp+78h+var_50], rax; __int64
0x18007c912  mov     rax, [rsp+78h+arg_20]
0x18007c91a  mov     [rsp+78h+var_58], rax; __int64
0x18007c91f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18007c924  mov     ecx, edi; this
0x18007c926  mov     [rbx+8], edi
0x18007c929  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007c92e  mov     [rbx+0Ch], eax
0x18007c931  mov     ecx, edi; this
0x18007c933  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18007c938  jmp     short loc_18007C94A
0x18007c93a  mov     ecx, edi; this
0x18007c93c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18007c941  jmp     short loc_18007C94A
0x18007c943  mov     ecx, edi; this
0x18007c945  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18007c94a  mov     ebp, eax
0x18007c94c  mov     eax, [rsp+78h+arg_70]
0x18007c953  mov     [rbx+4], eax
0x18007c956  mov     [rbx], r15d
0x18007c959  cmp     dword ptr [r14+8], 1
0x18007c95e  jnz     short loc_18007C966
0x18007c960  or      eax, 8
0x18007c963  mov     [rbx+4], eax
0x18007c966  mov     eax, 1
0x18007c96b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18007c973  inc     eax
0x18007c975  xor     edi, edi
0x18007c977  mov     [rbx+10h], eax
0x18007c97a  mov     rax, [rsp+78h+arg_40]
0x18007c982  test    rax, rax
0x18007c985  jz      short loc_18007C98C
0x18007c987  cmp     [rax], di
0x18007c98a  jnz     short loc_18007C98F
0x18007c98c  mov     rax, rdi
0x18007c98f  mov     [rbx+18h], rax
0x18007c993  call    cs:__imp_GetCurrentThreadId
0x18007c999  mov     [rbx+38h], r13
0x18007c99d  xorps   xmm0, xmm0
0x18007c9a0  mov     [rbx+20h], eax
0x18007c9a3  mov     eax, [rsp+78h+arg_8]
0x18007c9aa  mov     [rbx+40h], eax
0x18007c9ad  mov     rax, [rsp+78h+arg_20]
0x18007c9b5  mov     [rbx+28h], rax
0x18007c9b9  mov     rax, [rsp+78h+arg_28]
0x18007c9c1  mov     [rbx+88h], rax
0x18007c9c8  mov     rax, [rsp+78h+arg_0]
0x18007c9d0  mov     [rbx+90h], rax
0x18007c9d7  xor     eax, eax
0x18007c9d9  mov     [rbx+44h], ebp
0x18007c9dc  mov     [rbx+30h], r12
0x18007c9e0  mov     [rbx+48h], rdi
0x18007c9e4  movups  xmmword ptr [rbx+68h], xmm0
0x18007c9e8  mov     [rbx+78h], rax
0x18007c9ec  movups  xmmword ptr [rbx+50h], xmm0
0x18007c9f0  mov     [rbx+60h], rax
0x18007c9f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18007c9fb  test    rax, rax
0x18007c9fe  jz      short loc_18007CA07
0x18007ca00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ca05  jmp     short loc_18007CA0A
0x18007ca07  mov     rax, rdi
0x18007ca0a  mov     [rbx+80h], rax
0x18007ca11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18007ca18  test    rax, rax
0x18007ca1b  jz      short loc_18007CA25
0x18007ca1d  mov     rcx, rbx
0x18007ca20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ca25  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18007ca2c  test    rax, rax
0x18007ca2f  jz      short loc_18007CA47
0x18007ca31  mov     rdx, [rsp+78h+arg_60]
0x18007ca39  mov     r8d, 400h
0x18007ca3f  mov     rcx, rbx
0x18007ca42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ca47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007ca4e  test    rax, rax
0x18007ca51  jz      short loc_18007CA5B
0x18007ca53  mov     rcx, rbx
0x18007ca56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ca5b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007ca62  test    rax, rax
0x18007ca65  jz      short loc_18007CA75
0x18007ca67  test    byte ptr [rbx+4], 2
0x18007ca6b  jnz     short loc_18007CA75
0x18007ca6d  mov     rcx, rbx
0x18007ca70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ca75  cmp     [rbx+8], edi
0x18007ca78  jl      short loc_18007CA94
0x18007ca7a  cmp     r15d, 3
0x18007ca7e  jnz     loc_18007CB62
0x18007ca84  mov     ecx, 8000FFFFh; this
0x18007ca89  mov     [rbx+8], ecx
0x18007ca8c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007ca91  mov     [rbx+0Ch], eax
0x18007ca94  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18007ca9b  jnz     short loc_18007CABC
0x18007ca9d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18007caa4  test    rax, rax
0x18007caa7  jz      short loc_18007CAB2
0x18007caa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007caae  test    al, al
0x18007cab0  jmp     short loc_18007CABA
0x18007cab2  call    cs:__imp_IsDebuggerPresent
0x18007cab8  test    eax, eax
0x18007caba  jz      short loc_18007CAC2
0x18007cabc  test    byte ptr [rbx+4], 2
0x18007cac0  jz      short loc_18007CAE6
0x18007cac2  mov     rax, cs:g_pfnResultLoggingCallback
0x18007cac9  test    rax, rax
0x18007cacc  jz      short loc_18007CB2A
0x18007cace  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18007cad5  jnz     short loc_18007CB2A
0x18007cad7  xor     r8d, r8d
0x18007cada  xor     edx, edx
0x18007cadc  mov     rcx, rbx
0x18007cadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cae4  jmp     short loc_18007CB2A
0x18007cae6  mov     rax, cs:g_pfnResultLoggingCallback
0x18007caed  mov     ebp, 800h
0x18007caf2  test    rax, rax
0x18007caf5  jz      short loc_18007CB0E
0x18007caf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18007cafe  jnz     short loc_18007CB0E
0x18007cb00  mov     r8d, ebp
0x18007cb03  mov     rdx, rsi
0x18007cb06  mov     rcx, rbx
0x18007cb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb0e  cmp     [rsi], di
0x18007cb11  jnz     short loc_18007CB21
0x18007cb13  mov     r8, rbx; unsigned __int64
0x18007cb16  mov     rdx, rbp; unsigned __int16 *
0x18007cb19  mov     rcx, rsi; this
0x18007cb1c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18007cb21  mov     rcx, rsi; lpOutputString
0x18007cb24  call    cs:__imp_OutputDebugStringW
0x18007cb2a  test    byte ptr [rbx+4], 4
0x18007cb2e  jnz     short loc_18007CB39
0x18007cb30  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18007cb37  jz      short loc_18007CB4A
0x18007cb39  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18007cb40  test    rax, rax
0x18007cb43  jz      short loc_18007CB4A
0x18007cb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb4a  mov     rbx, [rsp+78h+arg_10]
0x18007cb52  add     rsp, 40h
0x18007cb56  pop     r15
0x18007cb58  pop     r14
0x18007cb5a  pop     r13
0x18007cb5c  pop     r12
0x18007cb5e  pop     rdi
0x18007cb5f  pop     rsi
0x18007cb60  pop     rbp
0x18007cb61  retn
0x18007cb62  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
