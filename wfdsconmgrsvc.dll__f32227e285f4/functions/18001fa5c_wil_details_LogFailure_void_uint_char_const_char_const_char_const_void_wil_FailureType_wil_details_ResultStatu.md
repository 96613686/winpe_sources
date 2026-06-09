# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001fa5c`
- end: `0x18001fd55`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001d540`
- `0x18001d88c`

## callees

- `0x18001d480`
- `0x18001ee14`
- `0x18001f674`
- `0x18001fa5c`
- `0x180020768`
- `0x180020790`
- `0x1800208e0`
- `0x1800208fc`
- `0x180022314`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fb7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fb7f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001fd10`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001fd10`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fc9e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001fc9e`

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
0x18001fa5c  mov     [rsp+arg_10], rbx
0x18001fa61  mov     [rsp+arg_8], edx
0x18001fa65  mov     [rsp+arg_0], rcx
0x18001fa6a  push    rbp
0x18001fa6b  push    rsi
0x18001fa6c  push    rdi
0x18001fa6d  push    r12
0x18001fa6f  push    r13
0x18001fa71  push    r14
0x18001fa73  push    r15
0x18001fa75  sub     rsp, 40h
0x18001fa79  mov     r12, r9
0x18001fa7c  mov     r13, r8
0x18001fa7f  mov     r10, rcx
0x18001fa82  xor     eax, eax
0x18001fa84  mov     rsi, [rsp+78h+lpOutputString]
0x18001fa8c  mov     [rsi], ax
0x18001fa8f  mov     rax, [rsp+78h+arg_60]
0x18001fa97  mov     byte ptr [rax], 0
0x18001fa9a  mov     r14, [rsp+78h+arg_38]
0x18001faa2  mov     edi, [r14]
0x18001faa5  mov     rbx, [rsp+78h+arg_78]
0x18001faad  mov     [rbx+8], edi
0x18001fab0  mov     eax, [r14+4]
0x18001fab4  mov     [rbx+0Ch], eax
0x18001fab7  xor     ebp, ebp
0x18001fab9  mov     r15d, [rsp+78h+arg_30]
0x18001fac1  mov     ecx, r15d
0x18001fac4  test    r15d, r15d
0x18001fac7  jz      short loc_18001FB2F
0x18001fac9  sub     ecx, 1
0x18001facc  jz      short loc_18001FB26
0x18001face  sub     ecx, 1
0x18001fad1  jz      short loc_18001FAE1
0x18001fad3  cmp     ecx, 1
0x18001fad6  jnz     short loc_18001FB38
0x18001fad8  mov     ecx, edi; this
0x18001fada  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001fadf  jmp     short loc_18001FB36
0x18001fae1  test    edi, edi
0x18001fae3  js      short loc_18001FB1D
0x18001fae5  mov     edi, 8007029Ch
0x18001faea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001faee  mov     rax, [rsp+78h+arg_28]
0x18001faf6  mov     [rsp+78h+var_50], rax; __int64
0x18001fafb  mov     rax, [rsp+78h+arg_20]
0x18001fb03  mov     [rsp+78h+var_58], rax; __int64
0x18001fb08  mov     rcx, r10; int
0x18001fb0b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001fb10  mov     [rbx+8], edi
0x18001fb13  mov     ecx, edi; this
0x18001fb15  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001fb1a  mov     [rbx+0Ch], eax
0x18001fb1d  mov     ecx, edi; this
0x18001fb1f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001fb24  jmp     short loc_18001FB36
0x18001fb26  mov     ecx, edi; this
0x18001fb28  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001fb2d  jmp     short loc_18001FB36
0x18001fb2f  mov     ecx, edi; this
0x18001fb31  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001fb36  mov     ebp, eax
0x18001fb38  mov     [rbx], r15d
0x18001fb3b  mov     eax, [rsp+78h+arg_70]
0x18001fb42  mov     [rbx+4], eax
0x18001fb45  cmp     dword ptr [r14+8], 1
0x18001fb4a  jnz     short loc_18001FB52
0x18001fb4c  or      eax, 8
0x18001fb4f  mov     [rbx+4], eax
0x18001fb52  mov     eax, 1
0x18001fb57  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001fb5f  inc     eax
0x18001fb61  mov     [rbx+10h], eax
0x18001fb64  mov     rax, [rsp+78h+arg_40]
0x18001fb6c  xor     edi, edi
0x18001fb6e  test    rax, rax
0x18001fb71  jz      short loc_18001FB78
0x18001fb73  cmp     [rax], di
0x18001fb76  jnz     short loc_18001FB7B
0x18001fb78  mov     rax, rdi
0x18001fb7b  mov     [rbx+18h], rax
0x18001fb7f  call    cs:__imp_GetCurrentThreadId
0x18001fb85  mov     [rbx+20h], eax
0x18001fb88  mov     [rbx+38h], r13
0x18001fb8c  mov     eax, [rsp+78h+arg_8]
0x18001fb93  mov     [rbx+40h], eax
0x18001fb96  mov     [rbx+44h], ebp
0x18001fb99  mov     rax, [rsp+78h+arg_20]
0x18001fba1  mov     [rbx+28h], rax
0x18001fba5  mov     [rbx+30h], r12
0x18001fba9  mov     rax, [rsp+78h+arg_28]
0x18001fbb1  mov     [rbx+88h], rax
0x18001fbb8  mov     rax, [rsp+78h+arg_0]
0x18001fbc0  mov     [rbx+90h], rax
0x18001fbc7  mov     [rbx+48h], rdi
0x18001fbcb  xorps   xmm0, xmm0
0x18001fbce  xor     eax, eax
0x18001fbd0  movups  xmmword ptr [rbx+68h], xmm0
0x18001fbd4  mov     [rbx+78h], rax
0x18001fbd8  movups  xmmword ptr [rbx+50h], xmm0
0x18001fbdc  mov     [rbx+60h], rax
0x18001fbe0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001fbe7  test    rax, rax
0x18001fbea  jz      short loc_18001FBF3
0x18001fbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbf1  jmp     short loc_18001FBF6
0x18001fbf3  mov     rax, rdi
0x18001fbf6  mov     [rbx+80h], rax
0x18001fbfd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001fc04  test    rax, rax
0x18001fc07  jz      short loc_18001FC11
0x18001fc09  mov     rcx, rbx
0x18001fc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc11  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001fc18  test    rax, rax
0x18001fc1b  jz      short loc_18001FC33
0x18001fc1d  mov     r8d, 400h
0x18001fc23  mov     rdx, [rsp+78h+arg_60]
0x18001fc2b  mov     rcx, rbx
0x18001fc2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc33  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001fc3a  test    rax, rax
0x18001fc3d  jz      short loc_18001FC47
0x18001fc3f  mov     rcx, rbx
0x18001fc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc47  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001fc4e  test    rax, rax
0x18001fc51  jz      short loc_18001FC61
0x18001fc53  test    byte ptr [rbx+4], 2
0x18001fc57  jnz     short loc_18001FC61
0x18001fc59  mov     rcx, rbx
0x18001fc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc61  cmp     [rbx+8], edi
0x18001fc64  jl      short loc_18001FC80
0x18001fc66  cmp     r15d, 3
0x18001fc6a  jnz     loc_18001FD4F
0x18001fc70  mov     ecx, 8000FFFFh; this
0x18001fc75  mov     [rbx+8], ecx
0x18001fc78  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001fc7d  mov     [rbx+0Ch], eax
0x18001fc80  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001fc87  jnz     short loc_18001FCA8
0x18001fc89  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001fc90  test    rax, rax
0x18001fc93  jz      short loc_18001FC9E
0x18001fc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc9a  test    al, al
0x18001fc9c  jmp     short loc_18001FCA6
0x18001fc9e  call    cs:__imp_IsDebuggerPresent
0x18001fca4  test    eax, eax
0x18001fca6  jz      short loc_18001FCAE
0x18001fca8  test    byte ptr [rbx+4], 2
0x18001fcac  jz      short loc_18001FCD2
0x18001fcae  mov     rax, cs:g_pfnResultLoggingCallback
0x18001fcb5  test    rax, rax
0x18001fcb8  jz      short loc_18001FD16
0x18001fcba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001fcc1  jnz     short loc_18001FD16
0x18001fcc3  xor     r8d, r8d
0x18001fcc6  xor     edx, edx
0x18001fcc8  mov     rcx, rbx
0x18001fccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcd0  jmp     short loc_18001FD16
0x18001fcd2  mov     ebp, 800h
0x18001fcd7  mov     rax, cs:g_pfnResultLoggingCallback
0x18001fcde  test    rax, rax
0x18001fce1  jz      short loc_18001FCFA
0x18001fce3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001fcea  jnz     short loc_18001FCFA
0x18001fcec  mov     r8d, ebp
0x18001fcef  mov     rdx, rsi
0x18001fcf2  mov     rcx, rbx
0x18001fcf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcfa  cmp     [rsi], di
0x18001fcfd  jnz     short loc_18001FD0D
0x18001fcff  mov     r8, rbx; unsigned __int64
0x18001fd02  mov     rdx, rbp; unsigned __int16 *
0x18001fd05  mov     rcx, rsi; this
0x18001fd08  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001fd0d  mov     rcx, rsi; lpOutputString
0x18001fd10  call    cs:__imp_OutputDebugStringW
0x18001fd16  test    byte ptr [rbx+4], 4
0x18001fd1a  jnz     short loc_18001FD25
0x18001fd1c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001fd23  jz      short loc_18001FD37
0x18001fd25  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001fd2c  test    rax, rax
0x18001fd2f  jz      short loc_18001FD37
0x18001fd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd36  nop
0x18001fd37  mov     rbx, [rsp+78h+arg_10]
0x18001fd3f  add     rsp, 40h
0x18001fd43  pop     r15
0x18001fd45  pop     r14
0x18001fd47  pop     r13
0x18001fd49  pop     r12
0x18001fd4b  pop     rdi
0x18001fd4c  pop     rsi
0x18001fd4d  pop     rbp
0x18001fd4e  retn
0x18001fd4f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
