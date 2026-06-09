# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004d2c`
- end: `0x180005025`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003ecc`

## callees

- `0x180002554`
- `0x18000293c`
- `0x180002ca0`
- `0x180003908`
- `0x180004d2c`
- `0x1800050d0`
- `0x1800050ec`
- `0x180005108`
- `0x180005910`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e4f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f6e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f6e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004fe0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004fe0`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180004d2c  mov     [rsp+arg_10], rbx
0x180004d31  mov     [rsp+arg_8], edx
0x180004d35  mov     [rsp+arg_0], rcx
0x180004d3a  push    rbp
0x180004d3b  push    rsi
0x180004d3c  push    rdi
0x180004d3d  push    r12
0x180004d3f  push    r13
0x180004d41  push    r14
0x180004d43  push    r15
0x180004d45  sub     rsp, 40h
0x180004d49  mov     r12, r9
0x180004d4c  mov     r13, r8
0x180004d4f  mov     r10, rcx
0x180004d52  xor     eax, eax
0x180004d54  mov     rsi, [rsp+78h+lpOutputString]
0x180004d5c  mov     [rsi], ax
0x180004d5f  mov     rax, [rsp+78h+arg_60]
0x180004d67  mov     byte ptr [rax], 0
0x180004d6a  mov     r14, [rsp+78h+arg_38]
0x180004d72  mov     edi, [r14]
0x180004d75  mov     rbx, [rsp+78h+arg_78]
0x180004d7d  mov     [rbx+8], edi
0x180004d80  mov     eax, [r14+4]
0x180004d84  mov     [rbx+0Ch], eax
0x180004d87  xor     ebp, ebp
0x180004d89  mov     r15d, [rsp+78h+arg_30]
0x180004d91  mov     ecx, r15d
0x180004d94  test    r15d, r15d
0x180004d97  jz      short loc_180004DFF
0x180004d99  sub     ecx, 1
0x180004d9c  jz      short loc_180004DF6
0x180004d9e  sub     ecx, 1
0x180004da1  jz      short loc_180004DB1
0x180004da3  cmp     ecx, 1
0x180004da6  jnz     short loc_180004E08
0x180004da8  mov     ecx, edi; this
0x180004daa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004daf  jmp     short loc_180004E06
0x180004db1  test    edi, edi
0x180004db3  js      short loc_180004DED
0x180004db5  mov     edi, 8007029Ch
0x180004dba  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004dbe  mov     rax, [rsp+78h+arg_28]
0x180004dc6  mov     [rsp+78h+var_50], rax; __int64
0x180004dcb  mov     rax, [rsp+78h+arg_20]
0x180004dd3  mov     [rsp+78h+var_58], rax; __int64
0x180004dd8  mov     rcx, r10; int
0x180004ddb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004de0  mov     [rbx+8], edi
0x180004de3  mov     ecx, edi; this
0x180004de5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004dea  mov     [rbx+0Ch], eax
0x180004ded  mov     ecx, edi; this
0x180004def  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004df4  jmp     short loc_180004E06
0x180004df6  mov     ecx, edi; this
0x180004df8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004dfd  jmp     short loc_180004E06
0x180004dff  mov     ecx, edi; this
0x180004e01  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004e06  mov     ebp, eax
0x180004e08  mov     [rbx], r15d
0x180004e0b  mov     eax, [rsp+78h+arg_70]
0x180004e12  mov     [rbx+4], eax
0x180004e15  cmp     dword ptr [r14+8], 1
0x180004e1a  jnz     short loc_180004E22
0x180004e1c  or      eax, 8
0x180004e1f  mov     [rbx+4], eax
0x180004e22  mov     eax, 1
0x180004e27  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004e2f  inc     eax
0x180004e31  mov     [rbx+10h], eax
0x180004e34  mov     rax, [rsp+78h+arg_40]
0x180004e3c  xor     edi, edi
0x180004e3e  test    rax, rax
0x180004e41  jz      short loc_180004E48
0x180004e43  cmp     [rax], di
0x180004e46  jnz     short loc_180004E4B
0x180004e48  mov     rax, rdi
0x180004e4b  mov     [rbx+18h], rax
0x180004e4f  call    cs:__imp_GetCurrentThreadId
0x180004e55  mov     [rbx+20h], eax
0x180004e58  mov     [rbx+38h], r13
0x180004e5c  mov     eax, [rsp+78h+arg_8]
0x180004e63  mov     [rbx+40h], eax
0x180004e66  mov     [rbx+44h], ebp
0x180004e69  mov     rax, [rsp+78h+arg_20]
0x180004e71  mov     [rbx+28h], rax
0x180004e75  mov     [rbx+30h], r12
0x180004e79  mov     rax, [rsp+78h+arg_28]
0x180004e81  mov     [rbx+88h], rax
0x180004e88  mov     rax, [rsp+78h+arg_0]
0x180004e90  mov     [rbx+90h], rax
0x180004e97  mov     [rbx+48h], rdi
0x180004e9b  xorps   xmm0, xmm0
0x180004e9e  xor     eax, eax
0x180004ea0  movups  xmmword ptr [rbx+68h], xmm0
0x180004ea4  mov     [rbx+78h], rax
0x180004ea8  movups  xmmword ptr [rbx+50h], xmm0
0x180004eac  mov     [rbx+60h], rax
0x180004eb0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004eb7  test    rax, rax
0x180004eba  jz      short loc_180004EC3
0x180004ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec1  jmp     short loc_180004EC6
0x180004ec3  mov     rax, rdi
0x180004ec6  mov     [rbx+80h], rax
0x180004ecd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004ed4  test    rax, rax
0x180004ed7  jz      short loc_180004EE1
0x180004ed9  mov     rcx, rbx
0x180004edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ee8  test    rax, rax
0x180004eeb  jz      short loc_180004F03
0x180004eed  mov     r8d, 400h
0x180004ef3  mov     rdx, [rsp+78h+arg_60]
0x180004efb  mov     rcx, rbx
0x180004efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f03  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f0a  test    rax, rax
0x180004f0d  jz      short loc_180004F17
0x180004f0f  mov     rcx, rbx
0x180004f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f17  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f1e  test    rax, rax
0x180004f21  jz      short loc_180004F31
0x180004f23  test    byte ptr [rbx+4], 2
0x180004f27  jnz     short loc_180004F31
0x180004f29  mov     rcx, rbx
0x180004f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f31  cmp     [rbx+8], edi
0x180004f34  jl      short loc_180004F50
0x180004f36  cmp     r15d, 3
0x180004f3a  jnz     loc_18000501F
0x180004f40  mov     ecx, 8000FFFFh; this
0x180004f45  mov     [rbx+8], ecx
0x180004f48  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004f4d  mov     [rbx+0Ch], eax
0x180004f50  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004f57  jnz     short loc_180004F78
0x180004f59  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004f60  test    rax, rax
0x180004f63  jz      short loc_180004F6E
0x180004f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f6a  test    al, al
0x180004f6c  jmp     short loc_180004F76
0x180004f6e  call    cs:__imp_IsDebuggerPresent
0x180004f74  test    eax, eax
0x180004f76  jz      short loc_180004F7E
0x180004f78  test    byte ptr [rbx+4], 2
0x180004f7c  jz      short loc_180004FA2
0x180004f7e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f85  test    rax, rax
0x180004f88  jz      short loc_180004FE6
0x180004f8a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004f91  jnz     short loc_180004FE6
0x180004f93  xor     r8d, r8d
0x180004f96  xor     edx, edx
0x180004f98  mov     rcx, rbx
0x180004f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa0  jmp     short loc_180004FE6
0x180004fa2  mov     ebp, 800h
0x180004fa7  mov     rax, cs:g_pfnResultLoggingCallback
0x180004fae  test    rax, rax
0x180004fb1  jz      short loc_180004FCA
0x180004fb3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004fba  jnz     short loc_180004FCA
0x180004fbc  mov     r8d, ebp
0x180004fbf  mov     rdx, rsi
0x180004fc2  mov     rcx, rbx
0x180004fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fca  cmp     [rsi], di
0x180004fcd  jnz     short loc_180004FDD
0x180004fcf  mov     r8, rbx; unsigned __int64
0x180004fd2  mov     rdx, rbp; unsigned __int16 *
0x180004fd5  mov     rcx, rsi; this
0x180004fd8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004fdd  mov     rcx, rsi; lpOutputString
0x180004fe0  call    cs:__imp_OutputDebugStringW
0x180004fe6  test    byte ptr [rbx+4], 4
0x180004fea  jnz     short loc_180004FF5
0x180004fec  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004ff3  jz      short loc_180005007
0x180004ff5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004ffc  test    rax, rax
0x180004fff  jz      short loc_180005007
0x180005001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005006  nop
0x180005007  mov     rbx, [rsp+78h+arg_10]
0x18000500f  add     rsp, 40h
0x180005013  pop     r15
0x180005015  pop     r14
0x180005017  pop     r13
0x180005019  pop     r12
0x18000501b  pop     rdi
0x18000501c  pop     rsi
0x18000501d  pop     rbp
0x18000501e  retn
0x18000501f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
