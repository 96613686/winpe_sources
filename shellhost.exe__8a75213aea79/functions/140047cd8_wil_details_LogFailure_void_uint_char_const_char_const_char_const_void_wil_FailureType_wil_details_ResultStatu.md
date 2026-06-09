# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140047cd8`
- end: `0x140047fae`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `726`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x1400451bc`
- `0x14004526c`
- `0x14004535c`
- `0x14004ccd4`

## callees

- `0x14004510c`
- `0x140047234`
- `0x1400478bc`
- `0x140047a80`
- `0x140047cd8`
- `0x1400489fc`
- `0x140048a20`
- `0x140048adc`
- `0x140048af8`
- `0x14004a824`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140047dfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140047dfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140047f4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140047f4b`

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
0x140047cd8  mov     [rsp+arg_10], rbx
0x140047cdd  mov     [rsp+arg_8], edx
0x140047ce1  mov     [rsp+arg_0], rcx
0x140047ce6  push    rbp
0x140047ce7  push    rsi
0x140047ce8  push    rdi
0x140047ce9  push    r12
0x140047ceb  push    r13
0x140047ced  push    r14
0x140047cef  push    r15
0x140047cf1  sub     rsp, 40h
0x140047cf5  mov     r12, r9
0x140047cf8  mov     r13, r8
0x140047cfb  mov     r10, rcx
0x140047cfe  xor     eax, eax
0x140047d00  mov     rsi, [rsp+78h+lpOutputString]
0x140047d08  mov     [rsi], ax
0x140047d0b  mov     rax, [rsp+78h+arg_60]
0x140047d13  mov     byte ptr [rax], 0
0x140047d16  mov     r14, [rsp+78h+arg_38]
0x140047d1e  mov     edi, [r14]
0x140047d21  mov     rbx, [rsp+78h+arg_78]
0x140047d29  mov     [rbx+8], edi
0x140047d2c  mov     eax, [r14+4]
0x140047d30  mov     [rbx+0Ch], eax
0x140047d33  xor     ebp, ebp
0x140047d35  mov     r15d, [rsp+78h+arg_30]
0x140047d3d  mov     ecx, r15d
0x140047d40  test    r15d, r15d
0x140047d43  jz      short loc_140047DAB
0x140047d45  sub     ecx, 1
0x140047d48  jz      short loc_140047DA2
0x140047d4a  sub     ecx, 1
0x140047d4d  jz      short loc_140047D5D
0x140047d4f  cmp     ecx, 1
0x140047d52  jnz     short loc_140047DB4
0x140047d54  mov     ecx, edi; this
0x140047d56  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140047d5b  jmp     short loc_140047DB2
0x140047d5d  test    edi, edi
0x140047d5f  js      short loc_140047D99
0x140047d61  mov     edi, 8007029Ch
0x140047d66  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140047d6a  mov     rax, [rsp+78h+arg_28]
0x140047d72  mov     [rsp+78h+var_50], rax; __int64
0x140047d77  mov     rax, [rsp+78h+arg_20]
0x140047d7f  mov     [rsp+78h+var_58], rax; __int64
0x140047d84  mov     rcx, r10; int
0x140047d87  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140047d8c  mov     [rbx+8], edi
0x140047d8f  mov     ecx, edi; this
0x140047d91  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140047d96  mov     [rbx+0Ch], eax
0x140047d99  mov     ecx, edi; this
0x140047d9b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140047da0  jmp     short loc_140047DB2
0x140047da2  mov     ecx, edi; this
0x140047da4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140047da9  jmp     short loc_140047DB2
0x140047dab  mov     ecx, edi; this
0x140047dad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140047db2  mov     ebp, eax
0x140047db4  mov     [rbx], r15d
0x140047db7  mov     eax, [rsp+78h+arg_70]
0x140047dbe  mov     [rbx+4], eax
0x140047dc1  cmp     dword ptr [r14+8], 1
0x140047dc6  jnz     short loc_140047DCE
0x140047dc8  or      eax, 8
0x140047dcb  mov     [rbx+4], eax
0x140047dce  mov     eax, 1
0x140047dd3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140047ddb  inc     eax
0x140047ddd  mov     [rbx+10h], eax
0x140047de0  mov     rax, [rsp+78h+arg_40]
0x140047de8  xor     edi, edi
0x140047dea  test    rax, rax
0x140047ded  jz      short loc_140047DF4
0x140047def  cmp     [rax], di
0x140047df2  jnz     short loc_140047DF7
0x140047df4  mov     rax, rdi
0x140047df7  mov     [rbx+18h], rax
0x140047dfb  call    cs:__imp_GetCurrentThreadId
0x140047e01  mov     [rbx+20h], eax
0x140047e04  mov     [rbx+38h], r13
0x140047e08  mov     eax, [rsp+78h+arg_8]
0x140047e0f  mov     [rbx+40h], eax
0x140047e12  mov     [rbx+44h], ebp
0x140047e15  mov     rax, [rsp+78h+arg_20]
0x140047e1d  mov     [rbx+28h], rax
0x140047e21  mov     [rbx+30h], r12
0x140047e25  mov     rax, [rsp+78h+arg_28]
0x140047e2d  mov     [rbx+88h], rax
0x140047e34  mov     rax, [rsp+78h+arg_0]
0x140047e3c  mov     [rbx+90h], rax
0x140047e43  mov     [rbx+48h], rdi
0x140047e47  xorps   xmm0, xmm0
0x140047e4a  xor     eax, eax
0x140047e4c  movups  xmmword ptr [rbx+68h], xmm0
0x140047e50  mov     [rbx+78h], rax
0x140047e54  movups  xmmword ptr [rbx+50h], xmm0
0x140047e58  mov     [rbx+60h], rax
0x140047e5c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140047e63  test    rax, rax
0x140047e66  jz      short loc_140047E6F
0x140047e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047e6d  jmp     short loc_140047E72
0x140047e6f  mov     rax, rdi
0x140047e72  mov     [rbx+80h], rax
0x140047e79  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140047e80  test    rax, rax
0x140047e83  jz      short loc_140047E8D
0x140047e85  mov     rcx, rbx
0x140047e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047e8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140047e94  test    rax, rax
0x140047e97  jz      short loc_140047EAF
0x140047e99  mov     r8d, 400h
0x140047e9f  mov     rdx, [rsp+78h+arg_60]
0x140047ea7  mov     rcx, rbx
0x140047eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047eaf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140047eb6  test    rax, rax
0x140047eb9  jz      short loc_140047EC3
0x140047ebb  mov     rcx, rbx
0x140047ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047ec3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140047eca  test    rax, rax
0x140047ecd  jz      short loc_140047EDD
0x140047ecf  test    byte ptr [rbx+4], 2
0x140047ed3  jnz     short loc_140047EDD
0x140047ed5  mov     rcx, rbx
0x140047ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047edd  cmp     [rbx+8], edi
0x140047ee0  jl      short loc_140047EFE
0x140047ee2  cmp     r15d, 3
0x140047ee6  jz      short loc_140047EEE
0x140047ee8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140047eee  mov     ecx, 8000FFFFh; this
0x140047ef3  mov     [rbx+8], ecx
0x140047ef6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140047efb  mov     [rbx+0Ch], eax
0x140047efe  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x140047f03  test    al, al
0x140047f05  jz      short loc_140047F53
0x140047f07  test    byte ptr [rbx+4], 2
0x140047f0b  jnz     short loc_140047F53
0x140047f0d  mov     ebp, 800h
0x140047f12  mov     rax, cs:g_pfnResultLoggingCallback
0x140047f19  test    rax, rax
0x140047f1c  jz      short loc_140047F35
0x140047f1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140047f25  jnz     short loc_140047F35
0x140047f27  mov     r8d, ebp
0x140047f2a  mov     rdx, rsi
0x140047f2d  mov     rcx, rbx
0x140047f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f35  cmp     [rsi], di
0x140047f38  jnz     short loc_140047F48
0x140047f3a  mov     r8, rbx; unsigned __int64
0x140047f3d  mov     rdx, rbp; unsigned __int16 *
0x140047f40  mov     rcx, rsi; this
0x140047f43  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140047f48  mov     rcx, rsi; lpOutputString
0x140047f4b  call    cs:__imp_OutputDebugStringW
0x140047f51  jmp     short loc_140047F75
0x140047f53  mov     rax, cs:g_pfnResultLoggingCallback
0x140047f5a  test    rax, rax
0x140047f5d  jz      short loc_140047F75
0x140047f5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140047f66  jnz     short loc_140047F75
0x140047f68  xor     r8d, r8d
0x140047f6b  xor     edx, edx
0x140047f6d  mov     rcx, rbx
0x140047f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f75  test    byte ptr [rbx+4], 4
0x140047f79  jnz     short loc_140047F84
0x140047f7b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140047f82  jz      short loc_140047F96
0x140047f84  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140047f8b  test    rax, rax
0x140047f8e  jz      short loc_140047F96
0x140047f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f95  nop
0x140047f96  mov     rbx, [rsp+78h+arg_10]
0x140047f9e  add     rsp, 40h
0x140047fa2  pop     r15
0x140047fa4  pop     r14
0x140047fa6  pop     r13
0x140047fa8  pop     r12
0x140047faa  pop     rdi
0x140047fab  pop     rsi
0x140047fac  pop     rbp
0x140047fad  retn
```
