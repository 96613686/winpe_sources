# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180015cd8`
- end: `0x180015fd0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180014dc4`
- `0x180015114`

## callees

- `0x180004d34`
- `0x18000511c`
- `0x180005400`
- `0x180014d0c`
- `0x180015cd8`
- `0x1800161cc`
- `0x1800161e8`
- `0x180016204`
- `0x1800168cc`
- `0x180018010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180015f1a`
- `KERNEL32!IsDebuggerPresent` at `0x180015f1a`
- `KERNEL32!OutputDebugStringW` at `0x180015f8c`
- `KERNEL32!OutputDebugStringW` at `0x180015f8c`
- `KERNEL32!GetCurrentThreadId` at `0x180015dfb`
- `KERNEL32!GetCurrentThreadId` at `0x180015dfb`

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
0x180015cd8  mov     [rsp+arg_10], rbx
0x180015cdd  mov     [rsp+arg_8], edx
0x180015ce1  mov     [rsp+arg_0], rcx
0x180015ce6  push    rbp
0x180015ce7  push    rsi
0x180015ce8  push    rdi
0x180015ce9  push    r12
0x180015ceb  push    r13
0x180015ced  push    r14
0x180015cef  push    r15
0x180015cf1  sub     rsp, 40h
0x180015cf5  mov     r14, [rsp+78h+arg_38]
0x180015cfd  xor     eax, eax
0x180015cff  mov     rbx, [rsp+78h+arg_78]
0x180015d07  xor     ebp, ebp
0x180015d09  mov     r15d, [rsp+78h+arg_30]
0x180015d11  mov     r10, rcx
0x180015d14  mov     rsi, [rsp+78h+lpOutputString]
0x180015d1c  mov     r12, r9
0x180015d1f  mov     r13, r8
0x180015d22  mov     ecx, r15d
0x180015d25  mov     [rsi], ax
0x180015d28  mov     rax, [rsp+78h+arg_60]
0x180015d30  mov     byte ptr [rax], 0
0x180015d33  mov     edi, [r14]
0x180015d36  mov     [rbx+8], edi
0x180015d39  mov     eax, [r14+4]
0x180015d3d  mov     [rbx+0Ch], eax
0x180015d40  test    r15d, r15d
0x180015d43  jz      short loc_180015DAB
0x180015d45  sub     ecx, 1
0x180015d48  jz      short loc_180015DA2
0x180015d4a  sub     ecx, 1
0x180015d4d  jz      short loc_180015D5D
0x180015d4f  cmp     ecx, 1
0x180015d52  jnz     short loc_180015DB4
0x180015d54  mov     ecx, edi; this
0x180015d56  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180015d5b  jmp     short loc_180015DB2
0x180015d5d  test    edi, edi
0x180015d5f  js      short loc_180015D99
0x180015d61  mov     rax, [rsp+78h+arg_28]
0x180015d69  mov     edi, 8007029Ch
0x180015d6e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180015d72  mov     rcx, r10; int
0x180015d75  mov     [rsp+78h+var_50], rax; __int64
0x180015d7a  mov     rax, [rsp+78h+arg_20]
0x180015d82  mov     [rsp+78h+var_58], rax; __int64
0x180015d87  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180015d8c  mov     ecx, edi; this
0x180015d8e  mov     [rbx+8], edi
0x180015d91  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015d96  mov     [rbx+0Ch], eax
0x180015d99  mov     ecx, edi; this
0x180015d9b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180015da0  jmp     short loc_180015DB2
0x180015da2  mov     ecx, edi; this
0x180015da4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180015da9  jmp     short loc_180015DB2
0x180015dab  mov     ecx, edi; this
0x180015dad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180015db2  mov     ebp, eax
0x180015db4  mov     eax, [rsp+78h+arg_70]
0x180015dbb  mov     [rbx+4], eax
0x180015dbe  mov     [rbx], r15d
0x180015dc1  cmp     dword ptr [r14+8], 1
0x180015dc6  jnz     short loc_180015DCE
0x180015dc8  or      eax, 8
0x180015dcb  mov     [rbx+4], eax
0x180015dce  mov     eax, 1
0x180015dd3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015ddb  inc     eax
0x180015ddd  xor     edi, edi
0x180015ddf  mov     [rbx+10h], eax
0x180015de2  mov     rax, [rsp+78h+arg_40]
0x180015dea  test    rax, rax
0x180015ded  jz      short loc_180015DF4
0x180015def  cmp     [rax], di
0x180015df2  jnz     short loc_180015DF7
0x180015df4  mov     rax, rdi
0x180015df7  mov     [rbx+18h], rax
0x180015dfb  call    cs:__imp_GetCurrentThreadId
0x180015e01  mov     [rbx+38h], r13
0x180015e05  xorps   xmm0, xmm0
0x180015e08  mov     [rbx+20h], eax
0x180015e0b  mov     eax, [rsp+78h+arg_8]
0x180015e12  mov     [rbx+40h], eax
0x180015e15  mov     rax, [rsp+78h+arg_20]
0x180015e1d  mov     [rbx+28h], rax
0x180015e21  mov     rax, [rsp+78h+arg_28]
0x180015e29  mov     [rbx+88h], rax
0x180015e30  mov     rax, [rsp+78h+arg_0]
0x180015e38  mov     [rbx+90h], rax
0x180015e3f  xor     eax, eax
0x180015e41  mov     [rbx+44h], ebp
0x180015e44  mov     [rbx+30h], r12
0x180015e48  mov     [rbx+48h], rdi
0x180015e4c  movups  xmmword ptr [rbx+68h], xmm0
0x180015e50  mov     [rbx+78h], rax
0x180015e54  movups  xmmword ptr [rbx+50h], xmm0
0x180015e58  mov     [rbx+60h], rax
0x180015e5c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180015e63  test    rax, rax
0x180015e66  jz      short loc_180015E6F
0x180015e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e6d  jmp     short loc_180015E72
0x180015e6f  mov     rax, rdi
0x180015e72  mov     [rbx+80h], rax
0x180015e79  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015e80  test    rax, rax
0x180015e83  jz      short loc_180015E8D
0x180015e85  mov     rcx, rbx
0x180015e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015e94  test    rax, rax
0x180015e97  jz      short loc_180015EAF
0x180015e99  mov     rdx, [rsp+78h+arg_60]
0x180015ea1  mov     r8d, 400h
0x180015ea7  mov     rcx, rbx
0x180015eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eaf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015eb6  test    rax, rax
0x180015eb9  jz      short loc_180015EC3
0x180015ebb  mov     rcx, rbx
0x180015ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ec3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015eca  test    rax, rax
0x180015ecd  jz      short loc_180015EDD
0x180015ecf  test    byte ptr [rbx+4], 2
0x180015ed3  jnz     short loc_180015EDD
0x180015ed5  mov     rcx, rbx
0x180015ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015edd  cmp     [rbx+8], edi
0x180015ee0  jl      short loc_180015EFC
0x180015ee2  cmp     r15d, 3
0x180015ee6  jnz     loc_180015FCA
0x180015eec  mov     ecx, 8000FFFFh; this
0x180015ef1  mov     [rbx+8], ecx
0x180015ef4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015ef9  mov     [rbx+0Ch], eax
0x180015efc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180015f03  jnz     short loc_180015F24
0x180015f05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015f0c  test    rax, rax
0x180015f0f  jz      short loc_180015F1A
0x180015f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f16  test    al, al
0x180015f18  jmp     short loc_180015F22
0x180015f1a  call    cs:__imp_IsDebuggerPresent
0x180015f20  test    eax, eax
0x180015f22  jz      short loc_180015F2A
0x180015f24  test    byte ptr [rbx+4], 2
0x180015f28  jz      short loc_180015F4E
0x180015f2a  mov     rax, cs:g_pfnResultLoggingCallback
0x180015f31  test    rax, rax
0x180015f34  jz      short loc_180015F92
0x180015f36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015f3d  jnz     short loc_180015F92
0x180015f3f  xor     r8d, r8d
0x180015f42  xor     edx, edx
0x180015f44  mov     rcx, rbx
0x180015f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f4c  jmp     short loc_180015F92
0x180015f4e  mov     rax, cs:g_pfnResultLoggingCallback
0x180015f55  mov     ebp, 800h
0x180015f5a  test    rax, rax
0x180015f5d  jz      short loc_180015F76
0x180015f5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015f66  jnz     short loc_180015F76
0x180015f68  mov     r8d, ebp
0x180015f6b  mov     rdx, rsi
0x180015f6e  mov     rcx, rbx
0x180015f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f76  cmp     [rsi], di
0x180015f79  jnz     short loc_180015F89
0x180015f7b  mov     r8, rbx; unsigned __int64
0x180015f7e  mov     rdx, rbp; unsigned __int16 *
0x180015f81  mov     rcx, rsi; this
0x180015f84  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180015f89  mov     rcx, rsi; lpOutputString
0x180015f8c  call    cs:__imp_OutputDebugStringW
0x180015f92  test    byte ptr [rbx+4], 4
0x180015f96  jnz     short loc_180015FA1
0x180015f98  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180015f9f  jz      short loc_180015FB2
0x180015fa1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015fa8  test    rax, rax
0x180015fab  jz      short loc_180015FB2
0x180015fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fb2  mov     rbx, [rsp+78h+arg_10]
0x180015fba  add     rsp, 40h
0x180015fbe  pop     r15
0x180015fc0  pop     r14
0x180015fc2  pop     r13
0x180015fc4  pop     r12
0x180015fc6  pop     rdi
0x180015fc7  pop     rsi
0x180015fc8  pop     rbp
0x180015fc9  retn
0x180015fca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
