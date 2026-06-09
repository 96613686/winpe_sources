# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180043d78`
- end: `0x180044071`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18004202c`
- `0x180042374`

## callees

- `0x180033a8c`
- `0x180035694`
- `0x180041f74`
- `0x18004364c`
- `0x180043d78`
- `0x1800444d0`
- `0x1800444f0`
- `0x180044504`
- `0x180045160`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043e9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043e9b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180043fba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180043fba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004402c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004402c`

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
0x180043d78  mov     [rsp+arg_10], rbx
0x180043d7d  mov     [rsp+arg_8], edx
0x180043d81  mov     [rsp+arg_0], rcx
0x180043d86  push    rbp
0x180043d87  push    rsi
0x180043d88  push    rdi
0x180043d89  push    r12
0x180043d8b  push    r13
0x180043d8d  push    r14
0x180043d8f  push    r15
0x180043d91  sub     rsp, 40h
0x180043d95  mov     r12, r9
0x180043d98  mov     r13, r8
0x180043d9b  mov     r10, rcx
0x180043d9e  xor     eax, eax
0x180043da0  mov     rsi, [rsp+78h+lpOutputString]
0x180043da8  mov     [rsi], ax
0x180043dab  mov     rax, [rsp+78h+arg_60]
0x180043db3  mov     byte ptr [rax], 0
0x180043db6  mov     r14, [rsp+78h+arg_38]
0x180043dbe  mov     edi, [r14]
0x180043dc1  mov     rbx, [rsp+78h+arg_78]
0x180043dc9  mov     [rbx+8], edi
0x180043dcc  mov     eax, [r14+4]
0x180043dd0  mov     [rbx+0Ch], eax
0x180043dd3  xor     ebp, ebp
0x180043dd5  mov     r15d, [rsp+78h+arg_30]
0x180043ddd  mov     ecx, r15d
0x180043de0  test    r15d, r15d
0x180043de3  jz      short loc_180043E4B
0x180043de5  sub     ecx, 1
0x180043de8  jz      short loc_180043E42
0x180043dea  sub     ecx, 1
0x180043ded  jz      short loc_180043DFD
0x180043def  cmp     ecx, 1
0x180043df2  jnz     short loc_180043E54
0x180043df4  mov     ecx, edi; this
0x180043df6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180043dfb  jmp     short loc_180043E52
0x180043dfd  test    edi, edi
0x180043dff  js      short loc_180043E39
0x180043e01  mov     edi, 8007029Ch
0x180043e06  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180043e0a  mov     rax, [rsp+78h+arg_28]
0x180043e12  mov     [rsp+78h+var_50], rax; __int64
0x180043e17  mov     rax, [rsp+78h+arg_20]
0x180043e1f  mov     [rsp+78h+var_58], rax; __int64
0x180043e24  mov     rcx, r10; int
0x180043e27  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180043e2c  mov     [rbx+8], edi
0x180043e2f  mov     ecx, edi; this
0x180043e31  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180043e36  mov     [rbx+0Ch], eax
0x180043e39  mov     ecx, edi; this
0x180043e3b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180043e40  jmp     short loc_180043E52
0x180043e42  mov     ecx, edi; this
0x180043e44  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180043e49  jmp     short loc_180043E52
0x180043e4b  mov     ecx, edi; this
0x180043e4d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180043e52  mov     ebp, eax
0x180043e54  mov     [rbx], r15d
0x180043e57  mov     eax, [rsp+78h+arg_70]
0x180043e5e  mov     [rbx+4], eax
0x180043e61  cmp     dword ptr [r14+8], 1
0x180043e66  jnz     short loc_180043E6E
0x180043e68  or      eax, 8
0x180043e6b  mov     [rbx+4], eax
0x180043e6e  mov     eax, 1
0x180043e73  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180043e7b  inc     eax
0x180043e7d  mov     [rbx+10h], eax
0x180043e80  mov     rax, [rsp+78h+arg_40]
0x180043e88  xor     edi, edi
0x180043e8a  test    rax, rax
0x180043e8d  jz      short loc_180043E94
0x180043e8f  cmp     [rax], di
0x180043e92  jnz     short loc_180043E97
0x180043e94  mov     rax, rdi
0x180043e97  mov     [rbx+18h], rax
0x180043e9b  call    cs:__imp_GetCurrentThreadId
0x180043ea1  mov     [rbx+20h], eax
0x180043ea4  mov     [rbx+38h], r13
0x180043ea8  mov     eax, [rsp+78h+arg_8]
0x180043eaf  mov     [rbx+40h], eax
0x180043eb2  mov     [rbx+44h], ebp
0x180043eb5  mov     rax, [rsp+78h+arg_20]
0x180043ebd  mov     [rbx+28h], rax
0x180043ec1  mov     [rbx+30h], r12
0x180043ec5  mov     rax, [rsp+78h+arg_28]
0x180043ecd  mov     [rbx+88h], rax
0x180043ed4  mov     rax, [rsp+78h+arg_0]
0x180043edc  mov     [rbx+90h], rax
0x180043ee3  mov     [rbx+48h], rdi
0x180043ee7  xorps   xmm0, xmm0
0x180043eea  xor     eax, eax
0x180043eec  movups  xmmword ptr [rbx+68h], xmm0
0x180043ef0  mov     [rbx+78h], rax
0x180043ef4  movups  xmmword ptr [rbx+50h], xmm0
0x180043ef8  mov     [rbx+60h], rax
0x180043efc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180043f03  test    rax, rax
0x180043f06  jz      short loc_180043F0F
0x180043f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f0d  jmp     short loc_180043F12
0x180043f0f  mov     rax, rdi
0x180043f12  mov     [rbx+80h], rax
0x180043f19  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180043f20  test    rax, rax
0x180043f23  jz      short loc_180043F2D
0x180043f25  mov     rcx, rbx
0x180043f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f2d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180043f34  test    rax, rax
0x180043f37  jz      short loc_180043F4F
0x180043f39  mov     r8d, 400h
0x180043f3f  mov     rdx, [rsp+78h+arg_60]
0x180043f47  mov     rcx, rbx
0x180043f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f4f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043f56  test    rax, rax
0x180043f59  jz      short loc_180043F63
0x180043f5b  mov     rcx, rbx
0x180043f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f63  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043f6a  test    rax, rax
0x180043f6d  jz      short loc_180043F7D
0x180043f6f  test    byte ptr [rbx+4], 2
0x180043f73  jnz     short loc_180043F7D
0x180043f75  mov     rcx, rbx
0x180043f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f7d  cmp     [rbx+8], edi
0x180043f80  jl      short loc_180043F9C
0x180043f82  cmp     r15d, 3
0x180043f86  jnz     loc_18004406B
0x180043f8c  mov     ecx, 8000FFFFh; this
0x180043f91  mov     [rbx+8], ecx
0x180043f94  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180043f99  mov     [rbx+0Ch], eax
0x180043f9c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180043fa3  jnz     short loc_180043FC4
0x180043fa5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180043fac  test    rax, rax
0x180043faf  jz      short loc_180043FBA
0x180043fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fb6  test    al, al
0x180043fb8  jmp     short loc_180043FC2
0x180043fba  call    cs:__imp_IsDebuggerPresent
0x180043fc0  test    eax, eax
0x180043fc2  jz      short loc_180043FCA
0x180043fc4  test    byte ptr [rbx+4], 2
0x180043fc8  jz      short loc_180043FEE
0x180043fca  mov     rax, cs:g_pfnResultLoggingCallback
0x180043fd1  test    rax, rax
0x180043fd4  jz      short loc_180044032
0x180043fd6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180043fdd  jnz     short loc_180044032
0x180043fdf  xor     r8d, r8d
0x180043fe2  xor     edx, edx
0x180043fe4  mov     rcx, rbx
0x180043fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fec  jmp     short loc_180044032
0x180043fee  mov     ebp, 800h
0x180043ff3  mov     rax, cs:g_pfnResultLoggingCallback
0x180043ffa  test    rax, rax
0x180043ffd  jz      short loc_180044016
0x180043fff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180044006  jnz     short loc_180044016
0x180044008  mov     r8d, ebp
0x18004400b  mov     rdx, rsi
0x18004400e  mov     rcx, rbx
0x180044011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044016  cmp     [rsi], di
0x180044019  jnz     short loc_180044029
0x18004401b  mov     r8, rbx; unsigned __int64
0x18004401e  mov     rdx, rbp; unsigned __int16 *
0x180044021  mov     rcx, rsi; this
0x180044024  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180044029  mov     rcx, rsi; lpOutputString
0x18004402c  call    cs:__imp_OutputDebugStringW
0x180044032  test    byte ptr [rbx+4], 4
0x180044036  jnz     short loc_180044041
0x180044038  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004403f  jz      short loc_180044053
0x180044041  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180044048  test    rax, rax
0x18004404b  jz      short loc_180044053
0x18004404d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044052  nop
0x180044053  mov     rbx, [rsp+78h+arg_10]
0x18004405b  add     rsp, 40h
0x18004405f  pop     r15
0x180044061  pop     r14
0x180044063  pop     r13
0x180044065  pop     r12
0x180044067  pop     rdi
0x180044068  pop     rsi
0x180044069  pop     rbp
0x18004406a  retn
0x18004406b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
