# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001e84c`
- end: `0x18001eb44`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180018c88`
- `0x18001d898`

## callees

- `0x180018774`
- `0x18001d598`
- `0x18001e114`
- `0x18001e84c`
- `0x18001ee74`
- `0x18001ee90`
- `0x18001eea4`
- `0x18001eec0`
- `0x18001f578`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001eb00`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001eb00`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001ea8e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001ea8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e96f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e96f`

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
0x18001e84c  mov     [rsp+arg_10], rbx
0x18001e851  mov     [rsp+arg_8], edx
0x18001e855  mov     [rsp+arg_0], rcx
0x18001e85a  push    rbp
0x18001e85b  push    rsi
0x18001e85c  push    rdi
0x18001e85d  push    r12
0x18001e85f  push    r13
0x18001e861  push    r14
0x18001e863  push    r15
0x18001e865  sub     rsp, 40h
0x18001e869  mov     r14, [rsp+78h+arg_38]
0x18001e871  xor     eax, eax
0x18001e873  mov     rbx, [rsp+78h+arg_78]
0x18001e87b  xor     ebp, ebp
0x18001e87d  mov     r15d, [rsp+78h+arg_30]
0x18001e885  mov     r10, rcx
0x18001e888  mov     rsi, [rsp+78h+lpOutputString]
0x18001e890  mov     r12, r9
0x18001e893  mov     r13, r8
0x18001e896  mov     ecx, r15d
0x18001e899  mov     [rsi], ax
0x18001e89c  mov     rax, [rsp+78h+arg_60]
0x18001e8a4  mov     byte ptr [rax], 0
0x18001e8a7  mov     edi, [r14]
0x18001e8aa  mov     [rbx+8], edi
0x18001e8ad  mov     eax, [r14+4]
0x18001e8b1  mov     [rbx+0Ch], eax
0x18001e8b4  test    r15d, r15d
0x18001e8b7  jz      short loc_18001E91F
0x18001e8b9  sub     ecx, 1
0x18001e8bc  jz      short loc_18001E916
0x18001e8be  sub     ecx, 1
0x18001e8c1  jz      short loc_18001E8D1
0x18001e8c3  cmp     ecx, 1
0x18001e8c6  jnz     short loc_18001E928
0x18001e8c8  mov     ecx, edi; this
0x18001e8ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001e8cf  jmp     short loc_18001E926
0x18001e8d1  test    edi, edi
0x18001e8d3  js      short loc_18001E90D
0x18001e8d5  mov     rax, [rsp+78h+arg_28]
0x18001e8dd  mov     edi, 8007029Ch
0x18001e8e2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001e8e6  mov     rcx, r10; int
0x18001e8e9  mov     [rsp+78h+var_50], rax; __int64
0x18001e8ee  mov     rax, [rsp+78h+arg_20]
0x18001e8f6  mov     [rsp+78h+var_58], rax; __int64
0x18001e8fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001e900  mov     ecx, edi; this
0x18001e902  mov     [rbx+8], edi
0x18001e905  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001e90a  mov     [rbx+0Ch], eax
0x18001e90d  mov     ecx, edi; this
0x18001e90f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001e914  jmp     short loc_18001E926
0x18001e916  mov     ecx, edi; this
0x18001e918  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001e91d  jmp     short loc_18001E926
0x18001e91f  mov     ecx, edi; this
0x18001e921  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001e926  mov     ebp, eax
0x18001e928  mov     eax, [rsp+78h+arg_70]
0x18001e92f  mov     [rbx+4], eax
0x18001e932  mov     [rbx], r15d
0x18001e935  cmp     dword ptr [r14+8], 1
0x18001e93a  jnz     short loc_18001E942
0x18001e93c  or      eax, 8
0x18001e93f  mov     [rbx+4], eax
0x18001e942  mov     eax, 1
0x18001e947  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001e94f  inc     eax
0x18001e951  xor     edi, edi
0x18001e953  mov     [rbx+10h], eax
0x18001e956  mov     rax, [rsp+78h+arg_40]
0x18001e95e  test    rax, rax
0x18001e961  jz      short loc_18001E968
0x18001e963  cmp     [rax], di
0x18001e966  jnz     short loc_18001E96B
0x18001e968  mov     rax, rdi
0x18001e96b  mov     [rbx+18h], rax
0x18001e96f  call    cs:__imp_GetCurrentThreadId
0x18001e975  mov     [rbx+38h], r13
0x18001e979  xorps   xmm0, xmm0
0x18001e97c  mov     [rbx+20h], eax
0x18001e97f  mov     eax, [rsp+78h+arg_8]
0x18001e986  mov     [rbx+40h], eax
0x18001e989  mov     rax, [rsp+78h+arg_20]
0x18001e991  mov     [rbx+28h], rax
0x18001e995  mov     rax, [rsp+78h+arg_28]
0x18001e99d  mov     [rbx+88h], rax
0x18001e9a4  mov     rax, [rsp+78h+arg_0]
0x18001e9ac  mov     [rbx+90h], rax
0x18001e9b3  xor     eax, eax
0x18001e9b5  mov     [rbx+44h], ebp
0x18001e9b8  mov     [rbx+30h], r12
0x18001e9bc  mov     [rbx+48h], rdi
0x18001e9c0  movups  xmmword ptr [rbx+68h], xmm0
0x18001e9c4  mov     [rbx+78h], rax
0x18001e9c8  movups  xmmword ptr [rbx+50h], xmm0
0x18001e9cc  mov     [rbx+60h], rax
0x18001e9d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001e9d7  test    rax, rax
0x18001e9da  jz      short loc_18001E9E3
0x18001e9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e1  jmp     short loc_18001E9E6
0x18001e9e3  mov     rax, rdi
0x18001e9e6  mov     [rbx+80h], rax
0x18001e9ed  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001e9f4  test    rax, rax
0x18001e9f7  jz      short loc_18001EA01
0x18001e9f9  mov     rcx, rbx
0x18001e9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea01  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001ea08  test    rax, rax
0x18001ea0b  jz      short loc_18001EA23
0x18001ea0d  mov     rdx, [rsp+78h+arg_60]
0x18001ea15  mov     r8d, 400h
0x18001ea1b  mov     rcx, rbx
0x18001ea1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea23  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ea2a  test    rax, rax
0x18001ea2d  jz      short loc_18001EA37
0x18001ea2f  mov     rcx, rbx
0x18001ea32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea37  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ea3e  test    rax, rax
0x18001ea41  jz      short loc_18001EA51
0x18001ea43  test    byte ptr [rbx+4], 2
0x18001ea47  jnz     short loc_18001EA51
0x18001ea49  mov     rcx, rbx
0x18001ea4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea51  cmp     [rbx+8], edi
0x18001ea54  jl      short loc_18001EA70
0x18001ea56  cmp     r15d, 3
0x18001ea5a  jnz     loc_18001EB3E
0x18001ea60  mov     ecx, 8000FFFFh; this
0x18001ea65  mov     [rbx+8], ecx
0x18001ea68  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001ea6d  mov     [rbx+0Ch], eax
0x18001ea70  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001ea77  jnz     short loc_18001EA98
0x18001ea79  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001ea80  test    rax, rax
0x18001ea83  jz      short loc_18001EA8E
0x18001ea85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea8a  test    al, al
0x18001ea8c  jmp     short loc_18001EA96
0x18001ea8e  call    cs:__imp_IsDebuggerPresent
0x18001ea94  test    eax, eax
0x18001ea96  jz      short loc_18001EA9E
0x18001ea98  test    byte ptr [rbx+4], 2
0x18001ea9c  jz      short loc_18001EAC2
0x18001ea9e  mov     rax, cs:g_pfnResultLoggingCallback
0x18001eaa5  test    rax, rax
0x18001eaa8  jz      short loc_18001EB06
0x18001eaaa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001eab1  jnz     short loc_18001EB06
0x18001eab3  xor     r8d, r8d
0x18001eab6  xor     edx, edx
0x18001eab8  mov     rcx, rbx
0x18001eabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eac0  jmp     short loc_18001EB06
0x18001eac2  mov     rax, cs:g_pfnResultLoggingCallback
0x18001eac9  mov     ebp, 800h
0x18001eace  test    rax, rax
0x18001ead1  jz      short loc_18001EAEA
0x18001ead3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001eada  jnz     short loc_18001EAEA
0x18001eadc  mov     r8d, ebp
0x18001eadf  mov     rdx, rsi
0x18001eae2  mov     rcx, rbx
0x18001eae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaea  cmp     [rsi], di
0x18001eaed  jnz     short loc_18001EAFD
0x18001eaef  mov     r8, rbx; unsigned __int64
0x18001eaf2  mov     rdx, rbp; unsigned __int16 *
0x18001eaf5  mov     rcx, rsi; this
0x18001eaf8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001eafd  mov     rcx, rsi; lpOutputString
0x18001eb00  call    cs:__imp_OutputDebugStringW
0x18001eb06  test    byte ptr [rbx+4], 4
0x18001eb0a  jnz     short loc_18001EB15
0x18001eb0c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001eb13  jz      short loc_18001EB26
0x18001eb15  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001eb1c  test    rax, rax
0x18001eb1f  jz      short loc_18001EB26
0x18001eb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb26  mov     rbx, [rsp+78h+arg_10]
0x18001eb2e  add     rsp, 40h
0x18001eb32  pop     r15
0x18001eb34  pop     r14
0x18001eb36  pop     r13
0x18001eb38  pop     r12
0x18001eb3a  pop     rdi
0x18001eb3b  pop     rsi
0x18001eb3c  pop     rbp
0x18001eb3d  retn
0x18001eb3e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
