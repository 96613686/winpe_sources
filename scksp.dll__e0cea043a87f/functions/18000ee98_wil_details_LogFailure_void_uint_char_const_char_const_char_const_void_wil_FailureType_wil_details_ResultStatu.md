# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000ee98`
- end: `0x18000f191`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000c078`
- `0x18000c3d4`

## callees

- `0x18000bfb0`
- `0x18000e0a4`
- `0x18000e924`
- `0x18000ee98`
- `0x18000fe1c`
- `0x18000fe40`
- `0x18000ffc4`
- `0x18000ffe0`
- `0x180012228`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f14c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f14c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f0da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f0da`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x18000ee98  mov     [rsp+arg_10], rbx
0x18000ee9d  mov     [rsp+arg_8], edx
0x18000eea1  mov     [rsp+arg_0], rcx
0x18000eea6  push    rbp
0x18000eea7  push    rsi
0x18000eea8  push    rdi
0x18000eea9  push    r12
0x18000eeab  push    r13
0x18000eead  push    r14
0x18000eeaf  push    r15
0x18000eeb1  sub     rsp, 40h
0x18000eeb5  mov     r12, r9
0x18000eeb8  mov     r13, r8
0x18000eebb  mov     r10, rcx
0x18000eebe  xor     eax, eax
0x18000eec0  mov     rsi, [rsp+78h+lpOutputString]
0x18000eec8  mov     [rsi], ax
0x18000eecb  mov     rax, [rsp+78h+arg_60]
0x18000eed3  mov     byte ptr [rax], 0
0x18000eed6  mov     r14, [rsp+78h+arg_38]
0x18000eede  mov     edi, [r14]
0x18000eee1  mov     rbx, [rsp+78h+arg_78]
0x18000eee9  mov     [rbx+8], edi
0x18000eeec  mov     eax, [r14+4]
0x18000eef0  mov     [rbx+0Ch], eax
0x18000eef3  xor     ebp, ebp
0x18000eef5  mov     r15d, [rsp+78h+arg_30]
0x18000eefd  mov     ecx, r15d
0x18000ef00  test    r15d, r15d
0x18000ef03  jz      short loc_18000EF6B
0x18000ef05  sub     ecx, 1
0x18000ef08  jz      short loc_18000EF62
0x18000ef0a  sub     ecx, 1
0x18000ef0d  jz      short loc_18000EF1D
0x18000ef0f  cmp     ecx, 1
0x18000ef12  jnz     short loc_18000EF74
0x18000ef14  mov     ecx, edi; this
0x18000ef16  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ef1b  jmp     short loc_18000EF72
0x18000ef1d  test    edi, edi
0x18000ef1f  js      short loc_18000EF59
0x18000ef21  mov     edi, 8007029Ch
0x18000ef26  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ef2a  mov     rax, [rsp+78h+arg_28]
0x18000ef32  mov     [rsp+78h+var_50], rax; __int64
0x18000ef37  mov     rax, [rsp+78h+arg_20]
0x18000ef3f  mov     [rsp+78h+var_58], rax; __int64
0x18000ef44  mov     rcx, r10; int
0x18000ef47  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ef4c  mov     [rbx+8], edi
0x18000ef4f  mov     ecx, edi; this
0x18000ef51  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ef56  mov     [rbx+0Ch], eax
0x18000ef59  mov     ecx, edi; this
0x18000ef5b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ef60  jmp     short loc_18000EF72
0x18000ef62  mov     ecx, edi; this
0x18000ef64  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ef69  jmp     short loc_18000EF72
0x18000ef6b  mov     ecx, edi; this
0x18000ef6d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ef72  mov     ebp, eax
0x18000ef74  mov     [rbx], r15d
0x18000ef77  mov     eax, [rsp+78h+arg_70]
0x18000ef7e  mov     [rbx+4], eax
0x18000ef81  cmp     dword ptr [r14+8], 1
0x18000ef86  jnz     short loc_18000EF8E
0x18000ef88  or      eax, 8
0x18000ef8b  mov     [rbx+4], eax
0x18000ef8e  mov     eax, 1
0x18000ef93  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ef9b  inc     eax
0x18000ef9d  mov     [rbx+10h], eax
0x18000efa0  mov     rax, [rsp+78h+arg_40]
0x18000efa8  xor     edi, edi
0x18000efaa  test    rax, rax
0x18000efad  jz      short loc_18000EFB4
0x18000efaf  cmp     [rax], di
0x18000efb2  jnz     short loc_18000EFB7
0x18000efb4  mov     rax, rdi
0x18000efb7  mov     [rbx+18h], rax
0x18000efbb  call    cs:__imp_GetCurrentThreadId
0x18000efc1  mov     [rbx+20h], eax
0x18000efc4  mov     [rbx+38h], r13
0x18000efc8  mov     eax, [rsp+78h+arg_8]
0x18000efcf  mov     [rbx+40h], eax
0x18000efd2  mov     [rbx+44h], ebp
0x18000efd5  mov     rax, [rsp+78h+arg_20]
0x18000efdd  mov     [rbx+28h], rax
0x18000efe1  mov     [rbx+30h], r12
0x18000efe5  mov     rax, [rsp+78h+arg_28]
0x18000efed  mov     [rbx+88h], rax
0x18000eff4  mov     rax, [rsp+78h+arg_0]
0x18000effc  mov     [rbx+90h], rax
0x18000f003  mov     [rbx+48h], rdi
0x18000f007  xorps   xmm0, xmm0
0x18000f00a  xor     eax, eax
0x18000f00c  movups  xmmword ptr [rbx+68h], xmm0
0x18000f010  mov     [rbx+78h], rax
0x18000f014  movups  xmmword ptr [rbx+50h], xmm0
0x18000f018  mov     [rbx+60h], rax
0x18000f01c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f023  test    rax, rax
0x18000f026  jz      short loc_18000F02F
0x18000f028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f02d  jmp     short loc_18000F032
0x18000f02f  mov     rax, rdi
0x18000f032  mov     [rbx+80h], rax
0x18000f039  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f040  test    rax, rax
0x18000f043  jz      short loc_18000F04D
0x18000f045  mov     rcx, rbx
0x18000f048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f04d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f054  test    rax, rax
0x18000f057  jz      short loc_18000F06F
0x18000f059  mov     r8d, 400h
0x18000f05f  mov     rdx, [rsp+78h+arg_60]
0x18000f067  mov     rcx, rbx
0x18000f06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f076  test    rax, rax
0x18000f079  jz      short loc_18000F083
0x18000f07b  mov     rcx, rbx
0x18000f07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f083  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f08a  test    rax, rax
0x18000f08d  jz      short loc_18000F09D
0x18000f08f  test    byte ptr [rbx+4], 2
0x18000f093  jnz     short loc_18000F09D
0x18000f095  mov     rcx, rbx
0x18000f098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f09d  cmp     [rbx+8], edi
0x18000f0a0  jl      short loc_18000F0BC
0x18000f0a2  cmp     r15d, 3
0x18000f0a6  jnz     loc_18000F18B
0x18000f0ac  mov     ecx, 8000FFFFh; this
0x18000f0b1  mov     [rbx+8], ecx
0x18000f0b4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f0b9  mov     [rbx+0Ch], eax
0x18000f0bc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000f0c3  jnz     short loc_18000F0E4
0x18000f0c5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f0cc  test    rax, rax
0x18000f0cf  jz      short loc_18000F0DA
0x18000f0d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0d6  test    al, al
0x18000f0d8  jmp     short loc_18000F0E2
0x18000f0da  call    cs:__imp_IsDebuggerPresent
0x18000f0e0  test    eax, eax
0x18000f0e2  jz      short loc_18000F0EA
0x18000f0e4  test    byte ptr [rbx+4], 2
0x18000f0e8  jz      short loc_18000F10E
0x18000f0ea  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f0f1  test    rax, rax
0x18000f0f4  jz      short loc_18000F152
0x18000f0f6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000f0fd  jnz     short loc_18000F152
0x18000f0ff  xor     r8d, r8d
0x18000f102  xor     edx, edx
0x18000f104  mov     rcx, rbx
0x18000f107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f10c  jmp     short loc_18000F152
0x18000f10e  mov     ebp, 800h
0x18000f113  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f11a  test    rax, rax
0x18000f11d  jz      short loc_18000F136
0x18000f11f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000f126  jnz     short loc_18000F136
0x18000f128  mov     r8d, ebp
0x18000f12b  mov     rdx, rsi
0x18000f12e  mov     rcx, rbx
0x18000f131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f136  cmp     [rsi], di
0x18000f139  jnz     short loc_18000F149
0x18000f13b  mov     r8, rbx; unsigned __int64
0x18000f13e  mov     rdx, rbp; unsigned __int16 *
0x18000f141  mov     rcx, rsi; pszDest
0x18000f144  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f149  mov     rcx, rsi; lpOutputString
0x18000f14c  call    cs:__imp_OutputDebugStringW
0x18000f152  test    byte ptr [rbx+4], 4
0x18000f156  jnz     short loc_18000F161
0x18000f158  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000f15f  jz      short loc_18000F173
0x18000f161  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f168  test    rax, rax
0x18000f16b  jz      short loc_18000F173
0x18000f16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f172  nop
0x18000f173  mov     rbx, [rsp+78h+arg_10]
0x18000f17b  add     rsp, 40h
0x18000f17f  pop     r15
0x18000f181  pop     r14
0x18000f183  pop     r13
0x18000f185  pop     r12
0x18000f187  pop     rdi
0x18000f188  pop     rsi
0x18000f189  pop     rbp
0x18000f18a  retn
0x18000f18b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
