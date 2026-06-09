# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001a1f8`
- end: `0x18001a503`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001810c`

## callees

- `0x180017b24`
- `0x180019614`
- `0x180019ef0`
- `0x18001a1f8`
- `0x18001ae90`
- `0x18001aeb0`
- `0x18001b04c`
- `0x18001b06c`
- `0x18001c710`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a31b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a31b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a4b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a4b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a440`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a440`

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
0x18001a1f8  mov     [rsp+arg_10], rbx
0x18001a1fd  mov     [rsp+arg_8], edx
0x18001a201  mov     [rsp+arg_0], rcx
0x18001a206  push    rbp
0x18001a207  push    rsi
0x18001a208  push    rdi
0x18001a209  push    r12
0x18001a20b  push    r13
0x18001a20d  push    r14
0x18001a20f  push    r15
0x18001a211  sub     rsp, 40h
0x18001a215  mov     r14, [rsp+78h+arg_38]
0x18001a21d  xor     eax, eax
0x18001a21f  mov     rbx, [rsp+78h+arg_78]
0x18001a227  xor     ebp, ebp
0x18001a229  mov     r15d, [rsp+78h+arg_30]
0x18001a231  mov     r10, rcx
0x18001a234  mov     rsi, [rsp+78h+lpOutputString]
0x18001a23c  mov     r12, r9
0x18001a23f  mov     r13, r8
0x18001a242  mov     ecx, r15d
0x18001a245  mov     [rsi], ax
0x18001a248  mov     rax, [rsp+78h+arg_60]
0x18001a250  mov     byte ptr [rax], 0
0x18001a253  mov     edi, [r14]
0x18001a256  mov     [rbx+8], edi
0x18001a259  mov     eax, [r14+4]
0x18001a25d  mov     [rbx+0Ch], eax
0x18001a260  test    r15d, r15d
0x18001a263  jz      short loc_18001A2CB
0x18001a265  sub     ecx, 1
0x18001a268  jz      short loc_18001A2C2
0x18001a26a  sub     ecx, 1
0x18001a26d  jz      short loc_18001A27D
0x18001a26f  cmp     ecx, 1
0x18001a272  jnz     short loc_18001A2D4
0x18001a274  mov     ecx, edi; this
0x18001a276  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001a27b  jmp     short loc_18001A2D2
0x18001a27d  test    edi, edi
0x18001a27f  js      short loc_18001A2B9
0x18001a281  mov     rax, [rsp+78h+arg_28]
0x18001a289  mov     edi, 8007029Ch
0x18001a28e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001a292  mov     rcx, r10; int
0x18001a295  mov     [rsp+78h+var_50], rax; __int64
0x18001a29a  mov     rax, [rsp+78h+arg_20]
0x18001a2a2  mov     [rsp+78h+var_58], rax; __int64
0x18001a2a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001a2ac  mov     ecx, edi; this
0x18001a2ae  mov     [rbx+8], edi
0x18001a2b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a2b6  mov     [rbx+0Ch], eax
0x18001a2b9  mov     ecx, edi; this
0x18001a2bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001a2c0  jmp     short loc_18001A2D2
0x18001a2c2  mov     ecx, edi; this
0x18001a2c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001a2c9  jmp     short loc_18001A2D2
0x18001a2cb  mov     ecx, edi; this
0x18001a2cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001a2d2  mov     ebp, eax
0x18001a2d4  mov     eax, [rsp+78h+arg_70]
0x18001a2db  mov     [rbx+4], eax
0x18001a2de  mov     [rbx], r15d
0x18001a2e1  cmp     dword ptr [r14+8], 1
0x18001a2e6  jnz     short loc_18001A2EE
0x18001a2e8  or      eax, 8
0x18001a2eb  mov     [rbx+4], eax
0x18001a2ee  mov     eax, 1
0x18001a2f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001a2fb  inc     eax
0x18001a2fd  xor     edi, edi
0x18001a2ff  mov     [rbx+10h], eax
0x18001a302  mov     rax, [rsp+78h+arg_40]
0x18001a30a  test    rax, rax
0x18001a30d  jz      short loc_18001A314
0x18001a30f  cmp     [rax], di
0x18001a312  jnz     short loc_18001A317
0x18001a314  mov     rax, rdi
0x18001a317  mov     [rbx+18h], rax
0x18001a31b  call    cs:__imp_GetCurrentThreadId
0x18001a322  nop     dword ptr [rax+rax+00h]
0x18001a327  mov     [rbx+38h], r13
0x18001a32b  xorps   xmm0, xmm0
0x18001a32e  mov     [rbx+20h], eax
0x18001a331  mov     eax, [rsp+78h+arg_8]
0x18001a338  mov     [rbx+40h], eax
0x18001a33b  mov     rax, [rsp+78h+arg_20]
0x18001a343  mov     [rbx+28h], rax
0x18001a347  mov     rax, [rsp+78h+arg_28]
0x18001a34f  mov     [rbx+88h], rax
0x18001a356  mov     rax, [rsp+78h+arg_0]
0x18001a35e  mov     [rbx+90h], rax
0x18001a365  xor     eax, eax
0x18001a367  mov     [rbx+44h], ebp
0x18001a36a  mov     [rbx+30h], r12
0x18001a36e  mov     [rbx+48h], rdi
0x18001a372  movups  xmmword ptr [rbx+68h], xmm0
0x18001a376  mov     [rbx+78h], rax
0x18001a37a  movups  xmmword ptr [rbx+50h], xmm0
0x18001a37e  mov     [rbx+60h], rax
0x18001a382  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001a389  test    rax, rax
0x18001a38c  jz      short loc_18001A395
0x18001a38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a393  jmp     short loc_18001A398
0x18001a395  mov     rax, rdi
0x18001a398  mov     [rbx+80h], rax
0x18001a39f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001a3a6  test    rax, rax
0x18001a3a9  jz      short loc_18001A3B3
0x18001a3ab  mov     rcx, rbx
0x18001a3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3b3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001a3ba  test    rax, rax
0x18001a3bd  jz      short loc_18001A3D5
0x18001a3bf  mov     rdx, [rsp+78h+arg_60]
0x18001a3c7  mov     r8d, 400h
0x18001a3cd  mov     rcx, rbx
0x18001a3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3d5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a3dc  test    rax, rax
0x18001a3df  jz      short loc_18001A3E9
0x18001a3e1  mov     rcx, rbx
0x18001a3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3e9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a3f0  test    rax, rax
0x18001a3f3  jz      short loc_18001A403
0x18001a3f5  test    byte ptr [rbx+4], 2
0x18001a3f9  jnz     short loc_18001A403
0x18001a3fb  mov     rcx, rbx
0x18001a3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a403  cmp     [rbx+8], edi
0x18001a406  jl      short loc_18001A422
0x18001a408  cmp     r15d, 3
0x18001a40c  jnz     loc_18001A4FD
0x18001a412  mov     ecx, 8000FFFFh; this
0x18001a417  mov     [rbx+8], ecx
0x18001a41a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a41f  mov     [rbx+0Ch], eax
0x18001a422  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001a429  jnz     short loc_18001A450
0x18001a42b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001a432  test    rax, rax
0x18001a435  jz      short loc_18001A440
0x18001a437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a43c  test    al, al
0x18001a43e  jmp     short loc_18001A44E
0x18001a440  call    cs:__imp_IsDebuggerPresent
0x18001a447  nop     dword ptr [rax+rax+00h]
0x18001a44c  test    eax, eax
0x18001a44e  jz      short loc_18001A456
0x18001a450  test    byte ptr [rbx+4], 2
0x18001a454  jz      short loc_18001A47A
0x18001a456  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a45d  test    rax, rax
0x18001a460  jz      short loc_18001A4C4
0x18001a462  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a469  jnz     short loc_18001A4C4
0x18001a46b  xor     r8d, r8d
0x18001a46e  xor     edx, edx
0x18001a470  mov     rcx, rbx
0x18001a473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a478  jmp     short loc_18001A4C4
0x18001a47a  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a481  mov     ebp, 800h
0x18001a486  test    rax, rax
0x18001a489  jz      short loc_18001A4A2
0x18001a48b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a492  jnz     short loc_18001A4A2
0x18001a494  mov     r8d, ebp
0x18001a497  mov     rdx, rsi
0x18001a49a  mov     rcx, rbx
0x18001a49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4a2  cmp     [rsi], di
0x18001a4a5  jnz     short loc_18001A4B5
0x18001a4a7  mov     r8, rbx; unsigned __int64
0x18001a4aa  mov     rdx, rbp; unsigned __int16 *
0x18001a4ad  mov     rcx, rsi; this
0x18001a4b0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001a4b5  mov     rcx, rsi; lpOutputString
0x18001a4b8  call    cs:__imp_OutputDebugStringW
0x18001a4bf  nop     dword ptr [rax+rax+00h]
0x18001a4c4  test    byte ptr [rbx+4], 4
0x18001a4c8  jnz     short loc_18001A4D3
0x18001a4ca  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001a4d1  jz      short loc_18001A4E4
0x18001a4d3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001a4da  test    rax, rax
0x18001a4dd  jz      short loc_18001A4E4
0x18001a4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4e4  mov     rbx, [rsp+78h+arg_10]
0x18001a4ec  add     rsp, 40h
0x18001a4f0  pop     r15
0x18001a4f2  pop     r14
0x18001a4f4  pop     r13
0x18001a4f6  pop     r12
0x18001a4f8  pop     rdi
0x18001a4f9  pop     rsi
0x18001a4fa  pop     rbp
0x18001a4fb  retn
0x18001a4fd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
