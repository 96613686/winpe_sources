# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004e30`
- end: `0x180005128`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003958`

## callees

- `0x180003394`
- `0x1800044d4`
- `0x180004c6c`
- `0x180004e30`
- `0x18000536c`
- `0x180005390`
- `0x1800053a4`
- `0x1800053c0`
- `0x180005dac`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f53`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005072`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005072`

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
0x180004e30  mov     [rsp+arg_10], rbx
0x180004e35  mov     [rsp+arg_8], edx
0x180004e39  mov     [rsp+arg_0], rcx
0x180004e3e  push    rbp
0x180004e3f  push    rsi
0x180004e40  push    rdi
0x180004e41  push    r12
0x180004e43  push    r13
0x180004e45  push    r14
0x180004e47  push    r15
0x180004e49  sub     rsp, 40h
0x180004e4d  mov     r14, [rsp+78h+arg_38]
0x180004e55  xor     eax, eax
0x180004e57  mov     rbx, [rsp+78h+arg_78]
0x180004e5f  xor     ebp, ebp
0x180004e61  mov     r15d, [rsp+78h+arg_30]
0x180004e69  mov     r10, rcx
0x180004e6c  mov     rsi, [rsp+78h+lpOutputString]
0x180004e74  mov     r12, r9
0x180004e77  mov     r13, r8
0x180004e7a  mov     ecx, r15d
0x180004e7d  mov     [rsi], ax
0x180004e80  mov     rax, [rsp+78h+arg_60]
0x180004e88  mov     byte ptr [rax], 0
0x180004e8b  mov     edi, [r14]
0x180004e8e  mov     [rbx+8], edi
0x180004e91  mov     eax, [r14+4]
0x180004e95  mov     [rbx+0Ch], eax
0x180004e98  test    r15d, r15d
0x180004e9b  jz      short loc_180004F03
0x180004e9d  sub     ecx, 1
0x180004ea0  jz      short loc_180004EFA
0x180004ea2  sub     ecx, 1
0x180004ea5  jz      short loc_180004EB5
0x180004ea7  cmp     ecx, 1
0x180004eaa  jnz     short loc_180004F0C
0x180004eac  mov     ecx, edi; this
0x180004eae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004eb3  jmp     short loc_180004F0A
0x180004eb5  test    edi, edi
0x180004eb7  js      short loc_180004EF1
0x180004eb9  mov     rax, [rsp+78h+arg_28]
0x180004ec1  mov     edi, 8007029Ch
0x180004ec6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004eca  mov     rcx, r10; int
0x180004ecd  mov     [rsp+78h+var_50], rax; __int64
0x180004ed2  mov     rax, [rsp+78h+arg_20]
0x180004eda  mov     [rsp+78h+var_58], rax; __int64
0x180004edf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004ee4  mov     ecx, edi; this
0x180004ee6  mov     [rbx+8], edi
0x180004ee9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004eee  mov     [rbx+0Ch], eax
0x180004ef1  mov     ecx, edi; this
0x180004ef3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004ef8  jmp     short loc_180004F0A
0x180004efa  mov     ecx, edi; this
0x180004efc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004f01  jmp     short loc_180004F0A
0x180004f03  mov     ecx, edi; this
0x180004f05  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004f0a  mov     ebp, eax
0x180004f0c  mov     eax, [rsp+78h+arg_70]
0x180004f13  mov     [rbx+4], eax
0x180004f16  mov     [rbx], r15d
0x180004f19  cmp     dword ptr [r14+8], 1
0x180004f1e  jnz     short loc_180004F26
0x180004f20  or      eax, 8
0x180004f23  mov     [rbx+4], eax
0x180004f26  mov     eax, 1
0x180004f2b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f33  inc     eax
0x180004f35  xor     edi, edi
0x180004f37  mov     [rbx+10h], eax
0x180004f3a  mov     rax, [rsp+78h+arg_40]
0x180004f42  test    rax, rax
0x180004f45  jz      short loc_180004F4C
0x180004f47  cmp     [rax], di
0x180004f4a  jnz     short loc_180004F4F
0x180004f4c  mov     rax, rdi
0x180004f4f  mov     [rbx+18h], rax
0x180004f53  call    cs:__imp_GetCurrentThreadId
0x180004f59  mov     [rbx+38h], r13
0x180004f5d  xorps   xmm0, xmm0
0x180004f60  mov     [rbx+20h], eax
0x180004f63  mov     eax, [rsp+78h+arg_8]
0x180004f6a  mov     [rbx+40h], eax
0x180004f6d  mov     rax, [rsp+78h+arg_20]
0x180004f75  mov     [rbx+28h], rax
0x180004f79  mov     rax, [rsp+78h+arg_28]
0x180004f81  mov     [rbx+88h], rax
0x180004f88  mov     rax, [rsp+78h+arg_0]
0x180004f90  mov     [rbx+90h], rax
0x180004f97  xor     eax, eax
0x180004f99  mov     [rbx+44h], ebp
0x180004f9c  mov     [rbx+30h], r12
0x180004fa0  mov     [rbx+48h], rdi
0x180004fa4  movups  xmmword ptr [rbx+68h], xmm0
0x180004fa8  mov     [rbx+78h], rax
0x180004fac  movups  xmmword ptr [rbx+50h], xmm0
0x180004fb0  mov     [rbx+60h], rax
0x180004fb4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004fbb  test    rax, rax
0x180004fbe  jz      short loc_180004FC7
0x180004fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc5  jmp     short loc_180004FCA
0x180004fc7  mov     rax, rdi
0x180004fca  mov     [rbx+80h], rax
0x180004fd1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fd8  test    rax, rax
0x180004fdb  jz      short loc_180004FE5
0x180004fdd  mov     rcx, rbx
0x180004fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004fec  test    rax, rax
0x180004fef  jz      short loc_180005007
0x180004ff1  mov     rdx, [rsp+78h+arg_60]
0x180004ff9  mov     r8d, 400h
0x180004fff  mov     rcx, rbx
0x180005002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005007  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000500e  test    rax, rax
0x180005011  jz      short loc_18000501B
0x180005013  mov     rcx, rbx
0x180005016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005022  test    rax, rax
0x180005025  jz      short loc_180005035
0x180005027  test    byte ptr [rbx+4], 2
0x18000502b  jnz     short loc_180005035
0x18000502d  mov     rcx, rbx
0x180005030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005035  cmp     [rbx+8], edi
0x180005038  jl      short loc_180005054
0x18000503a  cmp     r15d, 3
0x18000503e  jnz     loc_180005122
0x180005044  mov     ecx, 8000FFFFh; this
0x180005049  mov     [rbx+8], ecx
0x18000504c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005051  mov     [rbx+0Ch], eax
0x180005054  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000505b  jnz     short loc_18000507C
0x18000505d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005064  test    rax, rax
0x180005067  jz      short loc_180005072
0x180005069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506e  test    al, al
0x180005070  jmp     short loc_18000507A
0x180005072  call    cs:__imp_IsDebuggerPresent
0x180005078  test    eax, eax
0x18000507a  jz      short loc_180005082
0x18000507c  test    byte ptr [rbx+4], 2
0x180005080  jz      short loc_1800050A6
0x180005082  mov     rax, cs:g_pfnResultLoggingCallback
0x180005089  test    rax, rax
0x18000508c  jz      short loc_1800050EA
0x18000508e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005095  jnz     short loc_1800050EA
0x180005097  xor     r8d, r8d
0x18000509a  xor     edx, edx
0x18000509c  mov     rcx, rbx
0x18000509f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a4  jmp     short loc_1800050EA
0x1800050a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050ad  mov     ebp, 800h
0x1800050b2  test    rax, rax
0x1800050b5  jz      short loc_1800050CE
0x1800050b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800050be  jnz     short loc_1800050CE
0x1800050c0  mov     r8d, ebp
0x1800050c3  mov     rdx, rsi
0x1800050c6  mov     rcx, rbx
0x1800050c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ce  cmp     [rsi], di
0x1800050d1  jnz     short loc_1800050E1
0x1800050d3  mov     r8, rbx; unsigned __int64
0x1800050d6  mov     rdx, rbp; unsigned __int16 *
0x1800050d9  mov     rcx, rsi; this
0x1800050dc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800050e1  mov     rcx, rsi; lpOutputString
0x1800050e4  call    cs:__imp_OutputDebugStringW
0x1800050ea  test    byte ptr [rbx+4], 4
0x1800050ee  jnz     short loc_1800050F9
0x1800050f0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800050f7  jz      short loc_18000510A
0x1800050f9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005100  test    rax, rax
0x180005103  jz      short loc_18000510A
0x180005105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510a  mov     rbx, [rsp+78h+arg_10]
0x180005112  add     rsp, 40h
0x180005116  pop     r15
0x180005118  pop     r14
0x18000511a  pop     r13
0x18000511c  pop     r12
0x18000511e  pop     rdi
0x18000511f  pop     rsi
0x180005120  pop     rbp
0x180005121  retn
0x180005122  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
