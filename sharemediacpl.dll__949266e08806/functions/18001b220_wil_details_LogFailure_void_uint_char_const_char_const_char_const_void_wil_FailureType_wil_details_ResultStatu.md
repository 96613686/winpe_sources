# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001b220`
- end: `0x18001b518`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800196fc`

## callees

- `0x180019138`
- `0x18001a8c4`
- `0x18001b05c`
- `0x18001b220`
- `0x18001bac4`
- `0x18001bae0`
- `0x18001baf4`
- `0x18001bb10`
- `0x18001cb88`
- `0x18001e010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18001b4d4`
- `KERNEL32!OutputDebugStringW` at `0x18001b4d4`
- `KERNEL32!IsDebuggerPresent` at `0x18001b462`
- `KERNEL32!IsDebuggerPresent` at `0x18001b462`
- `KERNEL32!GetCurrentThreadId` at `0x18001b343`
- `KERNEL32!GetCurrentThreadId` at `0x18001b343`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x18001b220  mov     [rsp+arg_10], rbx
0x18001b225  mov     [rsp+arg_8], edx
0x18001b229  mov     [rsp+arg_0], rcx
0x18001b22e  push    rbp
0x18001b22f  push    rsi
0x18001b230  push    rdi
0x18001b231  push    r12
0x18001b233  push    r13
0x18001b235  push    r14
0x18001b237  push    r15
0x18001b239  sub     rsp, 40h
0x18001b23d  mov     r14, [rsp+78h+arg_38]
0x18001b245  xor     eax, eax
0x18001b247  mov     rbx, [rsp+78h+arg_78]
0x18001b24f  xor     ebp, ebp
0x18001b251  mov     r15d, [rsp+78h+arg_30]
0x18001b259  mov     r10, rcx
0x18001b25c  mov     rsi, [rsp+78h+lpOutputString]
0x18001b264  mov     r12, r9
0x18001b267  mov     r13, r8
0x18001b26a  mov     ecx, r15d
0x18001b26d  mov     [rsi], ax
0x18001b270  mov     rax, [rsp+78h+arg_60]
0x18001b278  mov     byte ptr [rax], 0
0x18001b27b  mov     edi, [r14]
0x18001b27e  mov     [rbx+8], edi
0x18001b281  mov     eax, [r14+4]
0x18001b285  mov     [rbx+0Ch], eax
0x18001b288  test    r15d, r15d
0x18001b28b  jz      short loc_18001B2F3
0x18001b28d  sub     ecx, 1
0x18001b290  jz      short loc_18001B2EA
0x18001b292  sub     ecx, 1
0x18001b295  jz      short loc_18001B2A5
0x18001b297  cmp     ecx, 1
0x18001b29a  jnz     short loc_18001B2FC
0x18001b29c  mov     ecx, edi; this
0x18001b29e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001b2a3  jmp     short loc_18001B2FA
0x18001b2a5  test    edi, edi
0x18001b2a7  js      short loc_18001B2E1
0x18001b2a9  mov     rax, [rsp+78h+arg_28]
0x18001b2b1  mov     edi, 8007029Ch
0x18001b2b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001b2ba  mov     rcx, r10; int
0x18001b2bd  mov     [rsp+78h+var_50], rax; __int64
0x18001b2c2  mov     rax, [rsp+78h+arg_20]
0x18001b2ca  mov     [rsp+78h+var_58], rax; __int64
0x18001b2cf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001b2d4  mov     ecx, edi; this
0x18001b2d6  mov     [rbx+8], edi
0x18001b2d9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001b2de  mov     [rbx+0Ch], eax
0x18001b2e1  mov     ecx, edi; this
0x18001b2e3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001b2e8  jmp     short loc_18001B2FA
0x18001b2ea  mov     ecx, edi; this
0x18001b2ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001b2f1  jmp     short loc_18001B2FA
0x18001b2f3  mov     ecx, edi; this
0x18001b2f5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001b2fa  mov     ebp, eax
0x18001b2fc  mov     eax, [rsp+78h+arg_70]
0x18001b303  mov     [rbx+4], eax
0x18001b306  mov     [rbx], r15d
0x18001b309  cmp     dword ptr [r14+8], 1
0x18001b30e  jnz     short loc_18001B316
0x18001b310  or      eax, 8
0x18001b313  mov     [rbx+4], eax
0x18001b316  mov     eax, 1
0x18001b31b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001b323  inc     eax
0x18001b325  xor     edi, edi
0x18001b327  mov     [rbx+10h], eax
0x18001b32a  mov     rax, [rsp+78h+arg_40]
0x18001b332  test    rax, rax
0x18001b335  jz      short loc_18001B33C
0x18001b337  cmp     [rax], di
0x18001b33a  jnz     short loc_18001B33F
0x18001b33c  mov     rax, rdi
0x18001b33f  mov     [rbx+18h], rax
0x18001b343  call    cs:__imp_GetCurrentThreadId
0x18001b349  mov     [rbx+38h], r13
0x18001b34d  xorps   xmm0, xmm0
0x18001b350  mov     [rbx+20h], eax
0x18001b353  mov     eax, [rsp+78h+arg_8]
0x18001b35a  mov     [rbx+40h], eax
0x18001b35d  mov     rax, [rsp+78h+arg_20]
0x18001b365  mov     [rbx+28h], rax
0x18001b369  mov     rax, [rsp+78h+arg_28]
0x18001b371  mov     [rbx+88h], rax
0x18001b378  mov     rax, [rsp+78h+arg_0]
0x18001b380  mov     [rbx+90h], rax
0x18001b387  xor     eax, eax
0x18001b389  mov     [rbx+44h], ebp
0x18001b38c  mov     [rbx+30h], r12
0x18001b390  mov     [rbx+48h], rdi
0x18001b394  movups  xmmword ptr [rbx+68h], xmm0
0x18001b398  mov     [rbx+78h], rax
0x18001b39c  movups  xmmword ptr [rbx+50h], xmm0
0x18001b3a0  mov     [rbx+60h], rax
0x18001b3a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001b3ab  test    rax, rax
0x18001b3ae  jz      short loc_18001B3B7
0x18001b3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3b5  jmp     short loc_18001B3BA
0x18001b3b7  mov     rax, rdi
0x18001b3ba  mov     [rbx+80h], rax
0x18001b3c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001b3c8  test    rax, rax
0x18001b3cb  jz      short loc_18001B3D5
0x18001b3cd  mov     rcx, rbx
0x18001b3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001b3dc  test    rax, rax
0x18001b3df  jz      short loc_18001B3F7
0x18001b3e1  mov     rdx, [rsp+78h+arg_60]
0x18001b3e9  mov     r8d, 400h
0x18001b3ef  mov     rcx, rbx
0x18001b3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001b3fe  test    rax, rax
0x18001b401  jz      short loc_18001B40B
0x18001b403  mov     rcx, rbx
0x18001b406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b40b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001b412  test    rax, rax
0x18001b415  jz      short loc_18001B425
0x18001b417  test    byte ptr [rbx+4], 2
0x18001b41b  jnz     short loc_18001B425
0x18001b41d  mov     rcx, rbx
0x18001b420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b425  cmp     [rbx+8], edi
0x18001b428  jl      short loc_18001B444
0x18001b42a  cmp     r15d, 3
0x18001b42e  jnz     loc_18001B512
0x18001b434  mov     ecx, 8000FFFFh; this
0x18001b439  mov     [rbx+8], ecx
0x18001b43c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001b441  mov     [rbx+0Ch], eax
0x18001b444  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001b44b  jnz     short loc_18001B46C
0x18001b44d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001b454  test    rax, rax
0x18001b457  jz      short loc_18001B462
0x18001b459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b45e  test    al, al
0x18001b460  jmp     short loc_18001B46A
0x18001b462  call    cs:__imp_IsDebuggerPresent
0x18001b468  test    eax, eax
0x18001b46a  jz      short loc_18001B472
0x18001b46c  test    byte ptr [rbx+4], 2
0x18001b470  jz      short loc_18001B496
0x18001b472  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b479  test    rax, rax
0x18001b47c  jz      short loc_18001B4DA
0x18001b47e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001b485  jnz     short loc_18001B4DA
0x18001b487  xor     r8d, r8d
0x18001b48a  xor     edx, edx
0x18001b48c  mov     rcx, rbx
0x18001b48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b494  jmp     short loc_18001B4DA
0x18001b496  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b49d  mov     ebp, 800h
0x18001b4a2  test    rax, rax
0x18001b4a5  jz      short loc_18001B4BE
0x18001b4a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001b4ae  jnz     short loc_18001B4BE
0x18001b4b0  mov     r8d, ebp
0x18001b4b3  mov     rdx, rsi
0x18001b4b6  mov     rcx, rbx
0x18001b4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4be  cmp     [rsi], di
0x18001b4c1  jnz     short loc_18001B4D1
0x18001b4c3  mov     r8, rbx; unsigned __int64
0x18001b4c6  mov     rdx, rbp; unsigned __int16 *
0x18001b4c9  mov     rcx, rsi; this
0x18001b4cc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001b4d1  mov     rcx, rsi; lpOutputString
0x18001b4d4  call    cs:__imp_OutputDebugStringW
0x18001b4da  test    byte ptr [rbx+4], 4
0x18001b4de  jnz     short loc_18001B4E9
0x18001b4e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001b4e7  jz      short loc_18001B4FA
0x18001b4e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001b4f0  test    rax, rax
0x18001b4f3  jz      short loc_18001B4FA
0x18001b4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4fa  mov     rbx, [rsp+78h+arg_10]
0x18001b502  add     rsp, 40h
0x18001b506  pop     r15
0x18001b508  pop     r14
0x18001b50a  pop     r13
0x18001b50c  pop     r12
0x18001b50e  pop     rdi
0x18001b50f  pop     rsi
0x18001b510  pop     rbp
0x18001b511  retn
0x18001b512  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
