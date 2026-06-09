# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002e444`
- end: `0x18002e745`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180025f10`

## callees

- `0x18002594c`
- `0x18002c960`
- `0x18002d8c8`
- `0x18002e444`
- `0x18002f484`
- `0x18002f4a0`
- `0x18002f4b4`
- `0x18002f4d0`
- `0x180030f64`
- `0x18006f010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18002e68e`
- `KERNEL32!IsDebuggerPresent` at `0x18002e68e`
- `KERNEL32!OutputDebugStringW` at `0x18002e700`
- `KERNEL32!OutputDebugStringW` at `0x18002e700`
- `KERNEL32!GetCurrentThreadId` at `0x18002e56f`
- `KERNEL32!GetCurrentThreadId` at `0x18002e56f`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
0x18002e444  mov     rax, rsp
0x18002e447  mov     [rax+10h], edx
0x18002e44a  mov     [rax+8], rcx
0x18002e44e  push    rbp
0x18002e44f  push    rsi
0x18002e450  push    rdi
0x18002e451  push    r12
0x18002e453  push    r13
0x18002e455  push    r14
0x18002e457  push    r15
0x18002e459  sub     rsp, 50h
0x18002e45d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18002e465  mov     [rax+18h], rbx
0x18002e469  mov     r12, r9
0x18002e46c  mov     r13, r8
0x18002e46f  mov     r10, rcx
0x18002e472  xor     eax, eax
0x18002e474  mov     rsi, [rsp+88h+lpOutputString]
0x18002e47c  mov     [rsi], ax
0x18002e47f  mov     rax, [rsp+88h+arg_60]
0x18002e487  mov     byte ptr [rax], 0
0x18002e48a  mov     r14, [rsp+88h+arg_38]
0x18002e492  mov     edi, [r14]
0x18002e495  mov     rbx, [rsp+88h+arg_78]
0x18002e49d  mov     [rbx+8], edi
0x18002e4a0  mov     eax, [r14+4]
0x18002e4a4  mov     [rbx+0Ch], eax
0x18002e4a7  xor     ebp, ebp
0x18002e4a9  mov     r15d, [rsp+88h+arg_30]
0x18002e4b1  mov     ecx, r15d
0x18002e4b4  test    r15d, r15d
0x18002e4b7  jz      short loc_18002E51F
0x18002e4b9  sub     ecx, 1
0x18002e4bc  jz      short loc_18002E516
0x18002e4be  sub     ecx, 1
0x18002e4c1  jz      short loc_18002E4D1
0x18002e4c3  cmp     ecx, 1
0x18002e4c6  jnz     short loc_18002E528
0x18002e4c8  mov     ecx, edi; this
0x18002e4ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002e4cf  jmp     short loc_18002E526
0x18002e4d1  test    edi, edi
0x18002e4d3  js      short loc_18002E50D
0x18002e4d5  mov     edi, 8007029Ch
0x18002e4da  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18002e4de  mov     rax, [rsp+88h+arg_28]
0x18002e4e6  mov     [rsp+88h+var_60], rax; __int64
0x18002e4eb  mov     rax, [rsp+88h+arg_20]
0x18002e4f3  mov     [rsp+88h+var_68], rax; __int64
0x18002e4f8  mov     rcx, r10; int
0x18002e4fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002e500  mov     [rbx+8], edi
0x18002e503  mov     ecx, edi; this
0x18002e505  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002e50a  mov     [rbx+0Ch], eax
0x18002e50d  mov     ecx, edi; this
0x18002e50f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002e514  jmp     short loc_18002E526
0x18002e516  mov     ecx, edi; this
0x18002e518  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002e51d  jmp     short loc_18002E526
0x18002e51f  mov     ecx, edi; this
0x18002e521  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002e526  mov     ebp, eax
0x18002e528  mov     [rbx], r15d
0x18002e52b  mov     eax, [rsp+88h+arg_70]
0x18002e532  mov     [rbx+4], eax
0x18002e535  cmp     dword ptr [r14+8], 1
0x18002e53a  jnz     short loc_18002E542
0x18002e53c  or      eax, 8
0x18002e53f  mov     [rbx+4], eax
0x18002e542  mov     eax, 1
0x18002e547  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002e54f  inc     eax
0x18002e551  mov     [rbx+10h], eax
0x18002e554  mov     rax, [rsp+88h+arg_40]
0x18002e55c  xor     edi, edi
0x18002e55e  test    rax, rax
0x18002e561  jz      short loc_18002E568
0x18002e563  cmp     [rax], di
0x18002e566  jnz     short loc_18002E56B
0x18002e568  mov     rax, rdi
0x18002e56b  mov     [rbx+18h], rax
0x18002e56f  call    cs:__imp_GetCurrentThreadId
0x18002e575  mov     [rbx+20h], eax
0x18002e578  mov     [rbx+38h], r13
0x18002e57c  mov     eax, [rsp+88h+arg_8]
0x18002e583  mov     [rbx+40h], eax
0x18002e586  mov     [rbx+44h], ebp
0x18002e589  mov     rax, [rsp+88h+arg_20]
0x18002e591  mov     [rbx+28h], rax
0x18002e595  mov     [rbx+30h], r12
0x18002e599  mov     rax, [rsp+88h+arg_28]
0x18002e5a1  mov     [rbx+88h], rax
0x18002e5a8  mov     rax, [rsp+88h+arg_0]
0x18002e5b0  mov     [rbx+90h], rax
0x18002e5b7  mov     [rbx+48h], rdi
0x18002e5bb  xorps   xmm0, xmm0
0x18002e5be  xor     eax, eax
0x18002e5c0  movups  xmmword ptr [rbx+68h], xmm0
0x18002e5c4  mov     [rbx+78h], rax
0x18002e5c8  movups  xmmword ptr [rbx+50h], xmm0
0x18002e5cc  mov     [rbx+60h], rax
0x18002e5d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002e5d7  test    rax, rax
0x18002e5da  jz      short loc_18002E5E3
0x18002e5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5e1  jmp     short loc_18002E5E6
0x18002e5e3  mov     rax, rdi
0x18002e5e6  mov     [rbx+80h], rax
0x18002e5ed  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002e5f4  test    rax, rax
0x18002e5f7  jz      short loc_18002E601
0x18002e5f9  mov     rcx, rbx
0x18002e5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e601  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002e608  test    rax, rax
0x18002e60b  jz      short loc_18002E623
0x18002e60d  mov     r8d, 400h
0x18002e613  mov     rdx, [rsp+88h+arg_60]
0x18002e61b  mov     rcx, rbx
0x18002e61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e623  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002e62a  test    rax, rax
0x18002e62d  jz      short loc_18002E637
0x18002e62f  mov     rcx, rbx
0x18002e632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e637  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002e63e  test    rax, rax
0x18002e641  jz      short loc_18002E651
0x18002e643  test    byte ptr [rbx+4], 2
0x18002e647  jnz     short loc_18002E651
0x18002e649  mov     rcx, rbx
0x18002e64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e651  cmp     [rbx+8], edi
0x18002e654  jl      short loc_18002E670
0x18002e656  cmp     r15d, 3
0x18002e65a  jnz     loc_18002E73F
0x18002e660  mov     ecx, 8000FFFFh; this
0x18002e665  mov     [rbx+8], ecx
0x18002e668  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002e66d  mov     [rbx+0Ch], eax
0x18002e670  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002e677  jnz     short loc_18002E698
0x18002e679  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002e680  test    rax, rax
0x18002e683  jz      short loc_18002E68E
0x18002e685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e68a  test    al, al
0x18002e68c  jmp     short loc_18002E696
0x18002e68e  call    cs:__imp_IsDebuggerPresent
0x18002e694  test    eax, eax
0x18002e696  jz      short loc_18002E69E
0x18002e698  test    byte ptr [rbx+4], 2
0x18002e69c  jz      short loc_18002E6C2
0x18002e69e  mov     rax, cs:g_pfnResultLoggingCallback
0x18002e6a5  test    rax, rax
0x18002e6a8  jz      short loc_18002E706
0x18002e6aa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002e6b1  jnz     short loc_18002E706
0x18002e6b3  xor     r8d, r8d
0x18002e6b6  xor     edx, edx
0x18002e6b8  mov     rcx, rbx
0x18002e6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6c0  jmp     short loc_18002E706
0x18002e6c2  mov     ebp, 800h
0x18002e6c7  mov     rax, cs:g_pfnResultLoggingCallback
0x18002e6ce  test    rax, rax
0x18002e6d1  jz      short loc_18002E6EA
0x18002e6d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002e6da  jnz     short loc_18002E6EA
0x18002e6dc  mov     r8d, ebp
0x18002e6df  mov     rdx, rsi
0x18002e6e2  mov     rcx, rbx
0x18002e6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6ea  cmp     [rsi], di
0x18002e6ed  jnz     short loc_18002E6FD
0x18002e6ef  mov     r8, rbx; unsigned __int64
0x18002e6f2  mov     rdx, rbp; unsigned __int16 *
0x18002e6f5  mov     rcx, rsi; this
0x18002e6f8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002e6fd  mov     rcx, rsi; lpOutputString
0x18002e700  call    cs:__imp_OutputDebugStringW
0x18002e706  test    byte ptr [rbx+4], 4
0x18002e70a  jnz     short loc_18002E715
0x18002e70c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002e713  jz      short loc_18002E727
0x18002e715  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002e71c  test    rax, rax
0x18002e71f  jz      short loc_18002E727
0x18002e721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e726  nop
0x18002e727  mov     rbx, [rsp+88h+arg_10]
0x18002e72f  add     rsp, 50h
0x18002e733  pop     r15
0x18002e735  pop     r14
0x18002e737  pop     r13
0x18002e739  pop     r12
0x18002e73b  pop     rdi
0x18002e73c  pop     rsi
0x18002e73d  pop     rbp
0x18002e73e  retn
0x18002e73f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
