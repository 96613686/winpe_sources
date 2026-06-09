# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18000c7f4`
- end: `0x18000cafb`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180009930`

## callees

- `0x18000934c`
- `0x18000b8f0`
- `0x18000c2c4`
- `0x18000c7f4`
- `0x18000d4d4`
- `0x18000d500`
- `0x18000d65c`
- `0x18000d67c`
- `0x180010a38`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c913`
- `KERNEL32!GetCurrentThreadId` at `0x18000c913`
- `KERNEL32!IsDebuggerPresent` at `0x18000ca37`
- `KERNEL32!IsDebuggerPresent` at `0x18000ca37`
- `KERNEL32!OutputDebugStringW` at `0x18000cab0`
- `KERNEL32!OutputDebugStringW` at `0x18000cab0`

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
        unsigned __int64 a15)
{
  int v17; // esi
  unsigned int v18; // edi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  v17 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v17 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 32) = CurrentThreadId;
  *(_DWORD *)(a15 + 64) = a2;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_DWORD *)(a15 + 68) = v17;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18000c7f4  mov     [rsp+arg_10], rbx
0x18000c7f9  mov     [rsp+arg_8], edx
0x18000c7fd  mov     [rsp+arg_0], rcx
0x18000c802  push    rbp
0x18000c803  push    rsi
0x18000c804  push    rdi
0x18000c805  push    r12
0x18000c807  push    r13
0x18000c809  push    r14
0x18000c80b  push    r15
0x18000c80d  sub     rsp, 40h
0x18000c811  mov     rax, [rsp+78h+arg_60]
0x18000c819  mov     r13, r8
0x18000c81c  mov     r15, [rsp+78h+arg_38]
0x18000c824  xor     r8d, r8d
0x18000c827  mov     rbx, [rsp+78h+arg_70]
0x18000c82f  mov     r10, rcx
0x18000c832  mov     ebp, [rsp+78h+arg_30]
0x18000c839  mov     r12, r9
0x18000c83c  mov     r14, [rsp+78h+lpOutputString]
0x18000c844  mov     esi, r8d
0x18000c847  mov     ecx, ebp
0x18000c849  mov     [r14], r8w
0x18000c84d  mov     [rax], r8b
0x18000c850  mov     edi, [r15]
0x18000c853  mov     [rbx+8], edi
0x18000c856  mov     eax, [r15+4]
0x18000c85a  mov     [rbx+0Ch], eax
0x18000c85d  test    ebp, ebp
0x18000c85f  jz      short loc_18000C8CA
0x18000c861  sub     ecx, 1
0x18000c864  jz      short loc_18000C8C1
0x18000c866  sub     ecx, 1
0x18000c869  jz      short loc_18000C879
0x18000c86b  cmp     ecx, 1
0x18000c86e  jnz     short loc_18000C8D3
0x18000c870  mov     ecx, edi; this
0x18000c872  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000c877  jmp     short loc_18000C8D1
0x18000c879  test    edi, edi
0x18000c87b  js      short loc_18000C8B8
0x18000c87d  mov     rax, [rsp+78h+arg_28]
0x18000c885  mov     edi, 8007029Ch
0x18000c88a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000c88e  mov     r8, r13; int
0x18000c891  mov     [rsp+78h+var_50], rax; __int64
0x18000c896  mov     rcx, r10; int
0x18000c899  mov     rax, [rsp+78h+arg_20]
0x18000c8a1  mov     [rsp+78h+var_58], rax; __int64
0x18000c8a6  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000c8ab  mov     ecx, edi; this
0x18000c8ad  mov     [rbx+8], edi
0x18000c8b0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c8b5  mov     [rbx+0Ch], eax
0x18000c8b8  mov     ecx, edi; this
0x18000c8ba  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000c8bf  jmp     short loc_18000C8D1
0x18000c8c1  mov     ecx, edi; this
0x18000c8c3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c8c8  jmp     short loc_18000C8D1
0x18000c8ca  mov     ecx, edi; this
0x18000c8cc  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c8d1  mov     esi, eax
0x18000c8d3  xor     edi, edi
0x18000c8d5  mov     [rbx], ebp
0x18000c8d7  mov     [rbx+4], edi
0x18000c8da  cmp     dword ptr [r15+8], 1
0x18000c8df  jnz     short loc_18000C8E8
0x18000c8e1  mov     dword ptr [rbx+4], 8
0x18000c8e8  mov     eax, 1
0x18000c8ed  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000c8f5  inc     eax
0x18000c8f7  mov     [rbx+10h], eax
0x18000c8fa  mov     rax, [rsp+78h+arg_40]
0x18000c902  test    rax, rax
0x18000c905  jz      short loc_18000C90C
0x18000c907  cmp     [rax], di
0x18000c90a  jnz     short loc_18000C90F
0x18000c90c  mov     rax, rdi
0x18000c90f  mov     [rbx+18h], rax
0x18000c913  call    cs:__imp_GetCurrentThreadId
0x18000c91a  nop     dword ptr [rax+rax+00h]
0x18000c91f  mov     [rbx+38h], r13
0x18000c923  xorps   xmm0, xmm0
0x18000c926  mov     [rbx+20h], eax
0x18000c929  mov     eax, [rsp+78h+arg_8]
0x18000c930  mov     [rbx+40h], eax
0x18000c933  mov     rax, [rsp+78h+arg_20]
0x18000c93b  mov     [rbx+28h], rax
0x18000c93f  mov     rax, [rsp+78h+arg_28]
0x18000c947  mov     [rbx+88h], rax
0x18000c94e  mov     rax, [rsp+78h+arg_0]
0x18000c956  mov     [rbx+90h], rax
0x18000c95d  xor     eax, eax
0x18000c95f  mov     [rbx+44h], esi
0x18000c962  mov     [rbx+30h], r12
0x18000c966  mov     [rbx+48h], rdi
0x18000c96a  movups  xmmword ptr [rbx+68h], xmm0
0x18000c96e  mov     [rbx+78h], rax
0x18000c972  movups  xmmword ptr [rbx+50h], xmm0
0x18000c976  mov     [rbx+60h], rax
0x18000c97a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c981  test    rax, rax
0x18000c984  jz      short loc_18000C98D
0x18000c986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c98b  jmp     short loc_18000C990
0x18000c98d  mov     rax, rdi
0x18000c990  mov     [rbx+80h], rax
0x18000c997  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c99e  test    rax, rax
0x18000c9a1  jz      short loc_18000C9AB
0x18000c9a3  mov     rcx, rbx
0x18000c9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ab  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c9b2  test    rax, rax
0x18000c9b5  jz      short loc_18000C9CD
0x18000c9b7  mov     rdx, [rsp+78h+arg_60]
0x18000c9bf  mov     r8d, 400h
0x18000c9c5  mov     rcx, rbx
0x18000c9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9cd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c9d4  test    rax, rax
0x18000c9d7  jz      short loc_18000C9E1
0x18000c9d9  mov     rcx, rbx
0x18000c9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9e1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c9e8  test    rax, rax
0x18000c9eb  jz      short loc_18000C9FB
0x18000c9ed  test    byte ptr [rbx+4], 2
0x18000c9f1  jnz     short loc_18000C9FB
0x18000c9f3  mov     rcx, rbx
0x18000c9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9fb  cmp     [rbx+8], edi
0x18000c9fe  jl      short loc_18000CA19
0x18000ca00  cmp     ebp, 3
0x18000ca03  jnz     loc_18000CAF5
0x18000ca09  mov     ecx, 8000FFFFh; this
0x18000ca0e  mov     [rbx+8], ecx
0x18000ca11  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ca16  mov     [rbx+0Ch], eax
0x18000ca19  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000ca20  jnz     short loc_18000CA47
0x18000ca22  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ca29  test    rax, rax
0x18000ca2c  jz      short loc_18000CA37
0x18000ca2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca33  test    al, al
0x18000ca35  jmp     short loc_18000CA45
0x18000ca37  call    cs:__imp_IsDebuggerPresent
0x18000ca3e  nop     dword ptr [rax+rax+00h]
0x18000ca43  test    eax, eax
0x18000ca45  jz      short loc_18000CA4D
0x18000ca47  test    byte ptr [rbx+4], 2
0x18000ca4b  jz      short loc_18000CA71
0x18000ca4d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ca54  test    rax, rax
0x18000ca57  jz      short loc_18000CABC
0x18000ca59  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ca60  jnz     short loc_18000CABC
0x18000ca62  xor     r8d, r8d
0x18000ca65  xor     edx, edx
0x18000ca67  mov     rcx, rbx
0x18000ca6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca6f  jmp     short loc_18000CABC
0x18000ca71  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ca78  mov     esi, 800h
0x18000ca7d  test    rax, rax
0x18000ca80  jz      short loc_18000CA99
0x18000ca82  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ca89  jnz     short loc_18000CA99
0x18000ca8b  mov     r8d, esi
0x18000ca8e  mov     rdx, r14
0x18000ca91  mov     rcx, rbx
0x18000ca94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca99  cmp     [r14], di
0x18000ca9d  jnz     short loc_18000CAAD
0x18000ca9f  mov     r8, rbx; unsigned __int64
0x18000caa2  mov     rdx, rsi; unsigned __int16 *
0x18000caa5  mov     rcx, r14; this
0x18000caa8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000caad  mov     rcx, r14; lpOutputString
0x18000cab0  call    cs:__imp_OutputDebugStringW
0x18000cab7  nop     dword ptr [rax+rax+00h]
0x18000cabc  test    byte ptr [rbx+4], 4
0x18000cac0  jnz     short loc_18000CACB
0x18000cac2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000cac9  jz      short loc_18000CADC
0x18000cacb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000cad2  test    rax, rax
0x18000cad5  jz      short loc_18000CADC
0x18000cad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cadc  mov     rbx, [rsp+78h+arg_10]
0x18000cae4  add     rsp, 40h
0x18000cae8  pop     r15
0x18000caea  pop     r14
0x18000caec  pop     r13
0x18000caee  pop     r12
0x18000caf0  pop     rdi
0x18000caf1  pop     rsi
0x18000caf2  pop     rbp
0x18000caf3  retn
0x18000caf5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
