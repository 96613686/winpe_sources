# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800d8148`
- end: `0x1800d8441`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800d6938`
- `0x1800d6c88`

## callees

- `0x1800d6880`
- `0x1800d77f4`
- `0x1800d7f84`
- `0x1800d8148`
- `0x1800d8734`
- `0x1800d8750`
- `0x1800d8764`
- `0x1800d8780`
- `0x1800d91d0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d826b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d826b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800d838a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800d838a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800d83fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800d83fc`

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
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x1800d8148  mov     [rsp+arg_10], rbx
0x1800d814d  mov     [rsp+arg_8], edx
0x1800d8151  mov     [rsp+arg_0], rcx
0x1800d8156  push    rbp
0x1800d8157  push    rsi
0x1800d8158  push    rdi
0x1800d8159  push    r12
0x1800d815b  push    r13
0x1800d815d  push    r14
0x1800d815f  push    r15
0x1800d8161  sub     rsp, 40h
0x1800d8165  mov     r12, r9
0x1800d8168  mov     r13, r8
0x1800d816b  mov     r10, rcx
0x1800d816e  xor     eax, eax
0x1800d8170  mov     rsi, [rsp+78h+lpOutputString]
0x1800d8178  mov     [rsi], ax
0x1800d817b  mov     rax, [rsp+78h+arg_60]
0x1800d8183  mov     byte ptr [rax], 0
0x1800d8186  mov     r14, [rsp+78h+arg_38]
0x1800d818e  mov     edi, [r14]
0x1800d8191  mov     rbx, [rsp+78h+arg_78]
0x1800d8199  mov     [rbx+8], edi
0x1800d819c  mov     eax, [r14+4]
0x1800d81a0  mov     [rbx+0Ch], eax
0x1800d81a3  xor     ebp, ebp
0x1800d81a5  mov     r15d, [rsp+78h+arg_30]
0x1800d81ad  mov     ecx, r15d
0x1800d81b0  test    r15d, r15d
0x1800d81b3  jz      short loc_1800D821B
0x1800d81b5  sub     ecx, 1
0x1800d81b8  jz      short loc_1800D8212
0x1800d81ba  sub     ecx, 1
0x1800d81bd  jz      short loc_1800D81CD
0x1800d81bf  cmp     ecx, 1
0x1800d81c2  jnz     short loc_1800D8224
0x1800d81c4  mov     ecx, edi; this
0x1800d81c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800d81cb  jmp     short loc_1800D8222
0x1800d81cd  test    edi, edi
0x1800d81cf  js      short loc_1800D8209
0x1800d81d1  mov     edi, 8007029Ch
0x1800d81d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800d81da  mov     rax, [rsp+78h+arg_28]
0x1800d81e2  mov     [rsp+78h+var_50], rax; __int64
0x1800d81e7  mov     rax, [rsp+78h+arg_20]
0x1800d81ef  mov     [rsp+78h+var_58], rax; __int64
0x1800d81f4  mov     rcx, r10; int
0x1800d81f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800d81fc  mov     [rbx+8], edi
0x1800d81ff  mov     ecx, edi; this
0x1800d8201  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800d8206  mov     [rbx+0Ch], eax
0x1800d8209  mov     ecx, edi; this
0x1800d820b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800d8210  jmp     short loc_1800D8222
0x1800d8212  mov     ecx, edi; this
0x1800d8214  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800d8219  jmp     short loc_1800D8222
0x1800d821b  mov     ecx, edi; this
0x1800d821d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800d8222  mov     ebp, eax
0x1800d8224  mov     [rbx], r15d
0x1800d8227  mov     eax, [rsp+78h+arg_70]
0x1800d822e  mov     [rbx+4], eax
0x1800d8231  cmp     dword ptr [r14+8], 1
0x1800d8236  jnz     short loc_1800D823E
0x1800d8238  or      eax, 8
0x1800d823b  mov     [rbx+4], eax
0x1800d823e  mov     eax, 1
0x1800d8243  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800d824b  inc     eax
0x1800d824d  mov     [rbx+10h], eax
0x1800d8250  mov     rax, [rsp+78h+arg_40]
0x1800d8258  xor     edi, edi
0x1800d825a  test    rax, rax
0x1800d825d  jz      short loc_1800D8264
0x1800d825f  cmp     [rax], di
0x1800d8262  jnz     short loc_1800D8267
0x1800d8264  mov     rax, rdi
0x1800d8267  mov     [rbx+18h], rax
0x1800d826b  call    cs:__imp_GetCurrentThreadId
0x1800d8271  mov     [rbx+20h], eax
0x1800d8274  mov     [rbx+38h], r13
0x1800d8278  mov     eax, [rsp+78h+arg_8]
0x1800d827f  mov     [rbx+40h], eax
0x1800d8282  mov     [rbx+44h], ebp
0x1800d8285  mov     rax, [rsp+78h+arg_20]
0x1800d828d  mov     [rbx+28h], rax
0x1800d8291  mov     [rbx+30h], r12
0x1800d8295  mov     rax, [rsp+78h+arg_28]
0x1800d829d  mov     [rbx+88h], rax
0x1800d82a4  mov     rax, [rsp+78h+arg_0]
0x1800d82ac  mov     [rbx+90h], rax
0x1800d82b3  mov     [rbx+48h], rdi
0x1800d82b7  xorps   xmm0, xmm0
0x1800d82ba  xor     eax, eax
0x1800d82bc  movups  xmmword ptr [rbx+68h], xmm0
0x1800d82c0  mov     [rbx+78h], rax
0x1800d82c4  movups  xmmword ptr [rbx+50h], xmm0
0x1800d82c8  mov     [rbx+60h], rax
0x1800d82cc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800d82d3  test    rax, rax
0x1800d82d6  jz      short loc_1800D82DF
0x1800d82d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d82dd  jmp     short loc_1800D82E2
0x1800d82df  mov     rax, rdi
0x1800d82e2  mov     [rbx+80h], rax
0x1800d82e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800d82f0  test    rax, rax
0x1800d82f3  jz      short loc_1800D82FD
0x1800d82f5  mov     rcx, rbx
0x1800d82f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d82fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800d8304  test    rax, rax
0x1800d8307  jz      short loc_1800D831F
0x1800d8309  mov     r8d, 400h
0x1800d830f  mov     rdx, [rsp+78h+arg_60]
0x1800d8317  mov     rcx, rbx
0x1800d831a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d831f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800d8326  test    rax, rax
0x1800d8329  jz      short loc_1800D8333
0x1800d832b  mov     rcx, rbx
0x1800d832e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8333  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800d833a  test    rax, rax
0x1800d833d  jz      short loc_1800D834D
0x1800d833f  test    byte ptr [rbx+4], 2
0x1800d8343  jnz     short loc_1800D834D
0x1800d8345  mov     rcx, rbx
0x1800d8348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d834d  cmp     [rbx+8], edi
0x1800d8350  jl      short loc_1800D836C
0x1800d8352  cmp     r15d, 3
0x1800d8356  jnz     loc_1800D843B
0x1800d835c  mov     ecx, 8000FFFFh; this
0x1800d8361  mov     [rbx+8], ecx
0x1800d8364  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800d8369  mov     [rbx+0Ch], eax
0x1800d836c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800d8373  jnz     short loc_1800D8394
0x1800d8375  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800d837c  test    rax, rax
0x1800d837f  jz      short loc_1800D838A
0x1800d8381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8386  test    al, al
0x1800d8388  jmp     short loc_1800D8392
0x1800d838a  call    cs:__imp_IsDebuggerPresent
0x1800d8390  test    eax, eax
0x1800d8392  jz      short loc_1800D839A
0x1800d8394  test    byte ptr [rbx+4], 2
0x1800d8398  jz      short loc_1800D83BE
0x1800d839a  mov     rax, cs:g_pfnResultLoggingCallback
0x1800d83a1  test    rax, rax
0x1800d83a4  jz      short loc_1800D8402
0x1800d83a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800d83ad  jnz     short loc_1800D8402
0x1800d83af  xor     r8d, r8d
0x1800d83b2  xor     edx, edx
0x1800d83b4  mov     rcx, rbx
0x1800d83b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d83bc  jmp     short loc_1800D8402
0x1800d83be  mov     ebp, 800h
0x1800d83c3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800d83ca  test    rax, rax
0x1800d83cd  jz      short loc_1800D83E6
0x1800d83cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800d83d6  jnz     short loc_1800D83E6
0x1800d83d8  mov     r8d, ebp
0x1800d83db  mov     rdx, rsi
0x1800d83de  mov     rcx, rbx
0x1800d83e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d83e6  cmp     [rsi], di
0x1800d83e9  jnz     short loc_1800D83F9
0x1800d83eb  mov     r8, rbx; unsigned __int64
0x1800d83ee  mov     rdx, rbp; unsigned __int16 *
0x1800d83f1  mov     rcx, rsi; this
0x1800d83f4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800d83f9  mov     rcx, rsi; lpOutputString
0x1800d83fc  call    cs:__imp_OutputDebugStringW
0x1800d8402  test    byte ptr [rbx+4], 4
0x1800d8406  jnz     short loc_1800D8411
0x1800d8408  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800d840f  jz      short loc_1800D8423
0x1800d8411  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800d8418  test    rax, rax
0x1800d841b  jz      short loc_1800D8423
0x1800d841d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8422  nop
0x1800d8423  mov     rbx, [rsp+78h+arg_10]
0x1800d842b  add     rsp, 40h
0x1800d842f  pop     r15
0x1800d8431  pop     r14
0x1800d8433  pop     r13
0x1800d8435  pop     r12
0x1800d8437  pop     rdi
0x1800d8438  pop     rsi
0x1800d8439  pop     rbp
0x1800d843a  retn
0x1800d843b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
