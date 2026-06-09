# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000ba80`
- end: `0x18000bd7d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180009f60`
- `0x18000a2cc`
- `0x18000d74c`

## callees

- `0x180009e98`
- `0x18000b0f4`
- `0x18000b890`
- `0x18000ba80`
- `0x18000c170`
- `0x18000c190`
- `0x18000c1a4`
- `0x18000c1c0`
- `0x18000cff4`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bba7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bd38`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bd38`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bcc6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bcc6`

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
0x18000ba80  mov     [rsp+arg_10], rbx
0x18000ba85  mov     [rsp+arg_8], edx
0x18000ba89  mov     [rsp+arg_0], rcx
0x18000ba8e  push    rbp
0x18000ba8f  push    rsi
0x18000ba90  push    rdi
0x18000ba91  push    r12
0x18000ba93  push    r13
0x18000ba95  push    r14
0x18000ba97  push    r15
0x18000ba99  sub     rsp, 40h
0x18000ba9d  mov     r12, r9
0x18000baa0  mov     r13, r8
0x18000baa3  mov     r10, rcx
0x18000baa6  xor     eax, eax
0x18000baa8  mov     rsi, [rsp+78h+lpOutputString]
0x18000bab0  mov     [rsi], ax
0x18000bab3  mov     rax, [rsp+78h+arg_60]
0x18000babb  mov     byte ptr [rax], 0
0x18000babe  mov     r14, [rsp+78h+arg_38]
0x18000bac6  mov     edi, [r14]
0x18000bac9  mov     rbx, [rsp+78h+arg_78]
0x18000bad1  mov     [rbx+8], edi
0x18000bad4  mov     eax, [r14+4]
0x18000bad8  mov     [rbx+0Ch], eax
0x18000badb  xor     ebp, ebp
0x18000badd  mov     r15d, [rsp+78h+arg_30]
0x18000bae5  mov     ecx, r15d
0x18000bae8  test    r15d, r15d
0x18000baeb  jz      short loc_18000BB57
0x18000baed  sub     ecx, 1
0x18000baf0  jz      short loc_18000BB4E
0x18000baf2  sub     ecx, 1
0x18000baf5  jz      short loc_18000BB05
0x18000baf7  cmp     ecx, 1
0x18000bafa  jnz     short loc_18000BB60
0x18000bafc  mov     ecx, edi; this
0x18000bafe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000bb03  jmp     short loc_18000BB5E
0x18000bb05  test    edi, edi
0x18000bb07  js      short loc_18000BB45
0x18000bb09  mov     [rsp+78h+var_40], ebp
0x18000bb0d  mov     edi, 8007029Ch
0x18000bb12  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000bb16  mov     rax, [rsp+78h+arg_28]
0x18000bb1e  mov     [rsp+78h+var_50], rax; __int64
0x18000bb23  mov     rax, [rsp+78h+arg_20]
0x18000bb2b  mov     [rsp+78h+var_58], rax; __int64
0x18000bb30  mov     rcx, r10; int
0x18000bb33  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000bb38  mov     [rbx+8], edi
0x18000bb3b  mov     ecx, edi; this
0x18000bb3d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bb42  mov     [rbx+0Ch], eax
0x18000bb45  mov     ecx, edi; this
0x18000bb47  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000bb4c  jmp     short loc_18000BB5E
0x18000bb4e  mov     ecx, edi; this
0x18000bb50  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bb55  jmp     short loc_18000BB5E
0x18000bb57  mov     ecx, edi; this
0x18000bb59  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bb5e  mov     ebp, eax
0x18000bb60  mov     [rbx], r15d
0x18000bb63  mov     eax, [rsp+78h+arg_70]
0x18000bb6a  mov     [rbx+4], eax
0x18000bb6d  cmp     dword ptr [r14+8], 1
0x18000bb72  jnz     short loc_18000BB7A
0x18000bb74  or      eax, 8
0x18000bb77  mov     [rbx+4], eax
0x18000bb7a  mov     eax, 1
0x18000bb7f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bb87  inc     eax
0x18000bb89  mov     [rbx+10h], eax
0x18000bb8c  mov     rax, [rsp+78h+arg_40]
0x18000bb94  xor     edi, edi
0x18000bb96  test    rax, rax
0x18000bb99  jz      short loc_18000BBA0
0x18000bb9b  cmp     [rax], di
0x18000bb9e  jnz     short loc_18000BBA3
0x18000bba0  mov     rax, rdi
0x18000bba3  mov     [rbx+18h], rax
0x18000bba7  call    cs:__imp_GetCurrentThreadId
0x18000bbad  mov     [rbx+20h], eax
0x18000bbb0  mov     [rbx+38h], r13
0x18000bbb4  mov     eax, [rsp+78h+arg_8]
0x18000bbbb  mov     [rbx+40h], eax
0x18000bbbe  mov     [rbx+44h], ebp
0x18000bbc1  mov     rax, [rsp+78h+arg_20]
0x18000bbc9  mov     [rbx+28h], rax
0x18000bbcd  mov     [rbx+30h], r12
0x18000bbd1  mov     rax, [rsp+78h+arg_28]
0x18000bbd9  mov     [rbx+88h], rax
0x18000bbe0  mov     rax, [rsp+78h+arg_0]
0x18000bbe8  mov     [rbx+90h], rax
0x18000bbef  mov     [rbx+48h], rdi
0x18000bbf3  xorps   xmm0, xmm0
0x18000bbf6  xor     eax, eax
0x18000bbf8  movups  xmmword ptr [rbx+68h], xmm0
0x18000bbfc  mov     [rbx+78h], rax
0x18000bc00  movups  xmmword ptr [rbx+50h], xmm0
0x18000bc04  mov     [rbx+60h], rax
0x18000bc08  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bc0f  test    rax, rax
0x18000bc12  jz      short loc_18000BC1B
0x18000bc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc19  jmp     short loc_18000BC1E
0x18000bc1b  mov     rax, rdi
0x18000bc1e  mov     [rbx+80h], rax
0x18000bc25  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bc2c  test    rax, rax
0x18000bc2f  jz      short loc_18000BC39
0x18000bc31  mov     rcx, rbx
0x18000bc34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc39  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bc40  test    rax, rax
0x18000bc43  jz      short loc_18000BC5B
0x18000bc45  mov     r8d, 400h
0x18000bc4b  mov     rdx, [rsp+78h+arg_60]
0x18000bc53  mov     rcx, rbx
0x18000bc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc5b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bc62  test    rax, rax
0x18000bc65  jz      short loc_18000BC6F
0x18000bc67  mov     rcx, rbx
0x18000bc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc6f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bc76  test    rax, rax
0x18000bc79  jz      short loc_18000BC89
0x18000bc7b  test    byte ptr [rbx+4], 2
0x18000bc7f  jnz     short loc_18000BC89
0x18000bc81  mov     rcx, rbx
0x18000bc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc89  cmp     [rbx+8], edi
0x18000bc8c  jl      short loc_18000BCA8
0x18000bc8e  cmp     r15d, 3
0x18000bc92  jnz     loc_18000BD77
0x18000bc98  mov     ecx, 8000FFFFh; this
0x18000bc9d  mov     [rbx+8], ecx
0x18000bca0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bca5  mov     [rbx+0Ch], eax
0x18000bca8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000bcaf  jnz     short loc_18000BCD0
0x18000bcb1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bcb8  test    rax, rax
0x18000bcbb  jz      short loc_18000BCC6
0x18000bcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc2  test    al, al
0x18000bcc4  jmp     short loc_18000BCCE
0x18000bcc6  call    cs:__imp_IsDebuggerPresent
0x18000bccc  test    eax, eax
0x18000bcce  jz      short loc_18000BCD6
0x18000bcd0  test    byte ptr [rbx+4], 2
0x18000bcd4  jz      short loc_18000BCFA
0x18000bcd6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bcdd  test    rax, rax
0x18000bce0  jz      short loc_18000BD3E
0x18000bce2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bce9  jnz     short loc_18000BD3E
0x18000bceb  xor     r8d, r8d
0x18000bcee  xor     edx, edx
0x18000bcf0  mov     rcx, rbx
0x18000bcf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf8  jmp     short loc_18000BD3E
0x18000bcfa  mov     ebp, 800h
0x18000bcff  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bd06  test    rax, rax
0x18000bd09  jz      short loc_18000BD22
0x18000bd0b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bd12  jnz     short loc_18000BD22
0x18000bd14  mov     r8d, ebp
0x18000bd17  mov     rdx, rsi
0x18000bd1a  mov     rcx, rbx
0x18000bd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd22  cmp     [rsi], di
0x18000bd25  jnz     short loc_18000BD35
0x18000bd27  mov     r8, rbx; unsigned __int64
0x18000bd2a  mov     rdx, rbp; unsigned __int16 *
0x18000bd2d  mov     rcx, rsi; this
0x18000bd30  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000bd35  mov     rcx, rsi; lpOutputString
0x18000bd38  call    cs:__imp_OutputDebugStringW
0x18000bd3e  test    byte ptr [rbx+4], 4
0x18000bd42  jnz     short loc_18000BD4D
0x18000bd44  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000bd4b  jz      short loc_18000BD5F
0x18000bd4d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bd54  test    rax, rax
0x18000bd57  jz      short loc_18000BD5F
0x18000bd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd5e  nop
0x18000bd5f  mov     rbx, [rsp+78h+arg_10]
0x18000bd67  add     rsp, 40h
0x18000bd6b  pop     r15
0x18000bd6d  pop     r14
0x18000bd6f  pop     r13
0x18000bd71  pop     r12
0x18000bd73  pop     rdi
0x18000bd74  pop     rsi
0x18000bd75  pop     rbp
0x18000bd76  retn
0x18000bd77  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
