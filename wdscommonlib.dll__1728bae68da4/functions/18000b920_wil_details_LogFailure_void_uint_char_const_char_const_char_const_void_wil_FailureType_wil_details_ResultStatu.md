# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18000b920`
- end: `0x18000bc27`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800093b0`

## callees

- `0x180008dcc`
- `0x18000ae94`
- `0x18000b6a8`
- `0x18000b920`
- `0x18000c34c`
- `0x18000c370`
- `0x18000c4cc`
- `0x18000c4ec`
- `0x18000e5a8`
- `0x180031010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000bb63`
- `KERNEL32!IsDebuggerPresent` at `0x18000bb63`
- `KERNEL32!OutputDebugStringW` at `0x18000bbdc`
- `KERNEL32!OutputDebugStringW` at `0x18000bbdc`
- `KERNEL32!GetCurrentThreadId` at `0x18000ba3f`
- `KERNEL32!GetCurrentThreadId` at `0x18000ba3f`

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
0x18000b920  mov     [rsp+arg_10], rbx
0x18000b925  mov     [rsp+arg_8], edx
0x18000b929  mov     [rsp+arg_0], rcx
0x18000b92e  push    rbp
0x18000b92f  push    rsi
0x18000b930  push    rdi
0x18000b931  push    r12
0x18000b933  push    r13
0x18000b935  push    r14
0x18000b937  push    r15
0x18000b939  sub     rsp, 40h
0x18000b93d  mov     rax, [rsp+78h+arg_60]
0x18000b945  mov     r13, r8
0x18000b948  mov     r15, [rsp+78h+arg_38]
0x18000b950  xor     r8d, r8d
0x18000b953  mov     rbx, [rsp+78h+arg_70]
0x18000b95b  mov     r10, rcx
0x18000b95e  mov     ebp, [rsp+78h+arg_30]
0x18000b965  mov     r12, r9
0x18000b968  mov     r14, [rsp+78h+lpOutputString]
0x18000b970  mov     esi, r8d
0x18000b973  mov     ecx, ebp
0x18000b975  mov     [r14], r8w
0x18000b979  mov     [rax], r8b
0x18000b97c  mov     edi, [r15]
0x18000b97f  mov     [rbx+8], edi
0x18000b982  mov     eax, [r15+4]
0x18000b986  mov     [rbx+0Ch], eax
0x18000b989  test    ebp, ebp
0x18000b98b  jz      short loc_18000B9F6
0x18000b98d  sub     ecx, 1
0x18000b990  jz      short loc_18000B9ED
0x18000b992  sub     ecx, 1
0x18000b995  jz      short loc_18000B9A5
0x18000b997  cmp     ecx, 1
0x18000b99a  jnz     short loc_18000B9FF
0x18000b99c  mov     ecx, edi; this
0x18000b99e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000b9a3  jmp     short loc_18000B9FD
0x18000b9a5  test    edi, edi
0x18000b9a7  js      short loc_18000B9E4
0x18000b9a9  mov     rax, [rsp+78h+arg_28]
0x18000b9b1  mov     edi, 8007029Ch
0x18000b9b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000b9ba  mov     r8, r13; int
0x18000b9bd  mov     [rsp+78h+var_50], rax; __int64
0x18000b9c2  mov     rcx, r10; int
0x18000b9c5  mov     rax, [rsp+78h+arg_20]
0x18000b9cd  mov     [rsp+78h+var_58], rax; __int64
0x18000b9d2  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000b9d7  mov     ecx, edi; this
0x18000b9d9  mov     [rbx+8], edi
0x18000b9dc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b9e1  mov     [rbx+0Ch], eax
0x18000b9e4  mov     ecx, edi; this
0x18000b9e6  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000b9eb  jmp     short loc_18000B9FD
0x18000b9ed  mov     ecx, edi; this
0x18000b9ef  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b9f4  jmp     short loc_18000B9FD
0x18000b9f6  mov     ecx, edi; this
0x18000b9f8  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b9fd  mov     esi, eax
0x18000b9ff  xor     edi, edi
0x18000ba01  mov     [rbx], ebp
0x18000ba03  mov     [rbx+4], edi
0x18000ba06  cmp     dword ptr [r15+8], 1
0x18000ba0b  jnz     short loc_18000BA14
0x18000ba0d  mov     dword ptr [rbx+4], 8
0x18000ba14  mov     eax, 1
0x18000ba19  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000ba21  inc     eax
0x18000ba23  mov     [rbx+10h], eax
0x18000ba26  mov     rax, [rsp+78h+arg_40]
0x18000ba2e  test    rax, rax
0x18000ba31  jz      short loc_18000BA38
0x18000ba33  cmp     [rax], di
0x18000ba36  jnz     short loc_18000BA3B
0x18000ba38  mov     rax, rdi
0x18000ba3b  mov     [rbx+18h], rax
0x18000ba3f  call    cs:__imp_GetCurrentThreadId
0x18000ba46  nop     dword ptr [rax+rax+00h]
0x18000ba4b  mov     [rbx+38h], r13
0x18000ba4f  xorps   xmm0, xmm0
0x18000ba52  mov     [rbx+20h], eax
0x18000ba55  mov     eax, [rsp+78h+arg_8]
0x18000ba5c  mov     [rbx+40h], eax
0x18000ba5f  mov     rax, [rsp+78h+arg_20]
0x18000ba67  mov     [rbx+28h], rax
0x18000ba6b  mov     rax, [rsp+78h+arg_28]
0x18000ba73  mov     [rbx+88h], rax
0x18000ba7a  mov     rax, [rsp+78h+arg_0]
0x18000ba82  mov     [rbx+90h], rax
0x18000ba89  xor     eax, eax
0x18000ba8b  mov     [rbx+44h], esi
0x18000ba8e  mov     [rbx+30h], r12
0x18000ba92  mov     [rbx+48h], rdi
0x18000ba96  movups  xmmword ptr [rbx+68h], xmm0
0x18000ba9a  mov     [rbx+78h], rax
0x18000ba9e  movups  xmmword ptr [rbx+50h], xmm0
0x18000baa2  mov     [rbx+60h], rax
0x18000baa6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000baad  test    rax, rax
0x18000bab0  jz      short loc_18000BAB9
0x18000bab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab7  jmp     short loc_18000BABC
0x18000bab9  mov     rax, rdi
0x18000babc  mov     [rbx+80h], rax
0x18000bac3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000baca  test    rax, rax
0x18000bacd  jz      short loc_18000BAD7
0x18000bacf  mov     rcx, rbx
0x18000bad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bad7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bade  test    rax, rax
0x18000bae1  jz      short loc_18000BAF9
0x18000bae3  mov     rdx, [rsp+78h+arg_60]
0x18000baeb  mov     r8d, 400h
0x18000baf1  mov     rcx, rbx
0x18000baf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bb00  test    rax, rax
0x18000bb03  jz      short loc_18000BB0D
0x18000bb05  mov     rcx, rbx
0x18000bb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb0d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bb14  test    rax, rax
0x18000bb17  jz      short loc_18000BB27
0x18000bb19  test    byte ptr [rbx+4], 2
0x18000bb1d  jnz     short loc_18000BB27
0x18000bb1f  mov     rcx, rbx
0x18000bb22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb27  cmp     [rbx+8], edi
0x18000bb2a  jl      short loc_18000BB45
0x18000bb2c  cmp     ebp, 3
0x18000bb2f  jnz     loc_18000BC21
0x18000bb35  mov     ecx, 8000FFFFh; this
0x18000bb3a  mov     [rbx+8], ecx
0x18000bb3d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bb42  mov     [rbx+0Ch], eax
0x18000bb45  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000bb4c  jnz     short loc_18000BB73
0x18000bb4e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bb55  test    rax, rax
0x18000bb58  jz      short loc_18000BB63
0x18000bb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb5f  test    al, al
0x18000bb61  jmp     short loc_18000BB71
0x18000bb63  call    cs:__imp_IsDebuggerPresent
0x18000bb6a  nop     dword ptr [rax+rax+00h]
0x18000bb6f  test    eax, eax
0x18000bb71  jz      short loc_18000BB79
0x18000bb73  test    byte ptr [rbx+4], 2
0x18000bb77  jz      short loc_18000BB9D
0x18000bb79  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bb80  test    rax, rax
0x18000bb83  jz      short loc_18000BBE8
0x18000bb85  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bb8c  jnz     short loc_18000BBE8
0x18000bb8e  xor     r8d, r8d
0x18000bb91  xor     edx, edx
0x18000bb93  mov     rcx, rbx
0x18000bb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb9b  jmp     short loc_18000BBE8
0x18000bb9d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bba4  mov     esi, 800h
0x18000bba9  test    rax, rax
0x18000bbac  jz      short loc_18000BBC5
0x18000bbae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bbb5  jnz     short loc_18000BBC5
0x18000bbb7  mov     r8d, esi
0x18000bbba  mov     rdx, r14
0x18000bbbd  mov     rcx, rbx
0x18000bbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbc5  cmp     [r14], di
0x18000bbc9  jnz     short loc_18000BBD9
0x18000bbcb  mov     r8, rbx; unsigned __int64
0x18000bbce  mov     rdx, rsi; unsigned __int16 *
0x18000bbd1  mov     rcx, r14; this
0x18000bbd4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000bbd9  mov     rcx, r14; lpOutputString
0x18000bbdc  call    cs:__imp_OutputDebugStringW
0x18000bbe3  nop     dword ptr [rax+rax+00h]
0x18000bbe8  test    byte ptr [rbx+4], 4
0x18000bbec  jnz     short loc_18000BBF7
0x18000bbee  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000bbf5  jz      short loc_18000BC08
0x18000bbf7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bbfe  test    rax, rax
0x18000bc01  jz      short loc_18000BC08
0x18000bc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc08  mov     rbx, [rsp+78h+arg_10]
0x18000bc10  add     rsp, 40h
0x18000bc14  pop     r15
0x18000bc16  pop     r14
0x18000bc18  pop     r13
0x18000bc1a  pop     r12
0x18000bc1c  pop     rdi
0x18000bc1d  pop     rsi
0x18000bc1e  pop     rbp
0x18000bc1f  retn
0x18000bc21  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
