# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004f10`
- end: `0x140005208`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140003358`

## callees

- `0x140002d94`
- `0x140004374`
- `0x140004b0c`
- `0x140004f10`
- `0x140005508`
- `0x140005530`
- `0x140005544`
- `0x140005560`
- `0x14000635c`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005033`
- `KERNEL32!GetCurrentThreadId` at `0x140005033`
- `KERNEL32!OutputDebugStringW` at `0x1400051c4`
- `KERNEL32!OutputDebugStringW` at `0x1400051c4`
- `KERNEL32!IsDebuggerPresent` at `0x140005152`
- `KERNEL32!IsDebuggerPresent` at `0x140005152`

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
0x140004f10  mov     [rsp+arg_10], rbx
0x140004f15  mov     [rsp+arg_8], edx
0x140004f19  mov     [rsp+arg_0], rcx
0x140004f1e  push    rbp
0x140004f1f  push    rsi
0x140004f20  push    rdi
0x140004f21  push    r12
0x140004f23  push    r13
0x140004f25  push    r14
0x140004f27  push    r15
0x140004f29  sub     rsp, 40h
0x140004f2d  mov     r14, [rsp+78h+arg_38]
0x140004f35  xor     eax, eax
0x140004f37  mov     rbx, [rsp+78h+arg_78]
0x140004f3f  xor     ebp, ebp
0x140004f41  mov     r15d, [rsp+78h+arg_30]
0x140004f49  mov     r10, rcx
0x140004f4c  mov     rsi, [rsp+78h+lpOutputString]
0x140004f54  mov     r12, r9
0x140004f57  mov     r13, r8
0x140004f5a  mov     ecx, r15d
0x140004f5d  mov     [rsi], ax
0x140004f60  mov     rax, [rsp+78h+arg_60]
0x140004f68  mov     byte ptr [rax], 0
0x140004f6b  mov     edi, [r14]
0x140004f6e  mov     [rbx+8], edi
0x140004f71  mov     eax, [r14+4]
0x140004f75  mov     [rbx+0Ch], eax
0x140004f78  test    r15d, r15d
0x140004f7b  jz      short loc_140004FE3
0x140004f7d  sub     ecx, 1
0x140004f80  jz      short loc_140004FDA
0x140004f82  sub     ecx, 1
0x140004f85  jz      short loc_140004F95
0x140004f87  cmp     ecx, 1
0x140004f8a  jnz     short loc_140004FEC
0x140004f8c  mov     ecx, edi; this
0x140004f8e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004f93  jmp     short loc_140004FEA
0x140004f95  test    edi, edi
0x140004f97  js      short loc_140004FD1
0x140004f99  mov     rax, [rsp+78h+arg_28]
0x140004fa1  mov     edi, 8007029Ch
0x140004fa6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004faa  mov     rcx, r10; int
0x140004fad  mov     [rsp+78h+var_50], rax; __int64
0x140004fb2  mov     rax, [rsp+78h+arg_20]
0x140004fba  mov     [rsp+78h+var_58], rax; __int64
0x140004fbf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004fc4  mov     ecx, edi; this
0x140004fc6  mov     [rbx+8], edi
0x140004fc9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004fce  mov     [rbx+0Ch], eax
0x140004fd1  mov     ecx, edi; this
0x140004fd3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004fd8  jmp     short loc_140004FEA
0x140004fda  mov     ecx, edi; this
0x140004fdc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004fe1  jmp     short loc_140004FEA
0x140004fe3  mov     ecx, edi; this
0x140004fe5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004fea  mov     ebp, eax
0x140004fec  mov     eax, [rsp+78h+arg_70]
0x140004ff3  mov     [rbx+4], eax
0x140004ff6  mov     [rbx], r15d
0x140004ff9  cmp     dword ptr [r14+8], 1
0x140004ffe  jnz     short loc_140005006
0x140005000  or      eax, 8
0x140005003  mov     [rbx+4], eax
0x140005006  mov     eax, 1
0x14000500b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005013  inc     eax
0x140005015  xor     edi, edi
0x140005017  mov     [rbx+10h], eax
0x14000501a  mov     rax, [rsp+78h+arg_40]
0x140005022  test    rax, rax
0x140005025  jz      short loc_14000502C
0x140005027  cmp     [rax], di
0x14000502a  jnz     short loc_14000502F
0x14000502c  mov     rax, rdi
0x14000502f  mov     [rbx+18h], rax
0x140005033  call    cs:__imp_GetCurrentThreadId
0x140005039  mov     [rbx+38h], r13
0x14000503d  xorps   xmm0, xmm0
0x140005040  mov     [rbx+20h], eax
0x140005043  mov     eax, [rsp+78h+arg_8]
0x14000504a  mov     [rbx+40h], eax
0x14000504d  mov     rax, [rsp+78h+arg_20]
0x140005055  mov     [rbx+28h], rax
0x140005059  mov     rax, [rsp+78h+arg_28]
0x140005061  mov     [rbx+88h], rax
0x140005068  mov     rax, [rsp+78h+arg_0]
0x140005070  mov     [rbx+90h], rax
0x140005077  xor     eax, eax
0x140005079  mov     [rbx+44h], ebp
0x14000507c  mov     [rbx+30h], r12
0x140005080  mov     [rbx+48h], rdi
0x140005084  movups  xmmword ptr [rbx+68h], xmm0
0x140005088  mov     [rbx+78h], rax
0x14000508c  movups  xmmword ptr [rbx+50h], xmm0
0x140005090  mov     [rbx+60h], rax
0x140005094  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000509b  test    rax, rax
0x14000509e  jz      short loc_1400050A7
0x1400050a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050a5  jmp     short loc_1400050AA
0x1400050a7  mov     rax, rdi
0x1400050aa  mov     [rbx+80h], rax
0x1400050b1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400050b8  test    rax, rax
0x1400050bb  jz      short loc_1400050C5
0x1400050bd  mov     rcx, rbx
0x1400050c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050c5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400050cc  test    rax, rax
0x1400050cf  jz      short loc_1400050E7
0x1400050d1  mov     rdx, [rsp+78h+arg_60]
0x1400050d9  mov     r8d, 400h
0x1400050df  mov     rcx, rbx
0x1400050e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050e7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400050ee  test    rax, rax
0x1400050f1  jz      short loc_1400050FB
0x1400050f3  mov     rcx, rbx
0x1400050f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050fb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005102  test    rax, rax
0x140005105  jz      short loc_140005115
0x140005107  test    byte ptr [rbx+4], 2
0x14000510b  jnz     short loc_140005115
0x14000510d  mov     rcx, rbx
0x140005110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005115  cmp     [rbx+8], edi
0x140005118  jl      short loc_140005134
0x14000511a  cmp     r15d, 3
0x14000511e  jnz     loc_140005202
0x140005124  mov     ecx, 8000FFFFh; this
0x140005129  mov     [rbx+8], ecx
0x14000512c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005131  mov     [rbx+0Ch], eax
0x140005134  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000513b  jnz     short loc_14000515C
0x14000513d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005144  test    rax, rax
0x140005147  jz      short loc_140005152
0x140005149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000514e  test    al, al
0x140005150  jmp     short loc_14000515A
0x140005152  call    cs:__imp_IsDebuggerPresent
0x140005158  test    eax, eax
0x14000515a  jz      short loc_140005162
0x14000515c  test    byte ptr [rbx+4], 2
0x140005160  jz      short loc_140005186
0x140005162  mov     rax, cs:g_pfnResultLoggingCallback
0x140005169  test    rax, rax
0x14000516c  jz      short loc_1400051CA
0x14000516e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005175  jnz     short loc_1400051CA
0x140005177  xor     r8d, r8d
0x14000517a  xor     edx, edx
0x14000517c  mov     rcx, rbx
0x14000517f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005184  jmp     short loc_1400051CA
0x140005186  mov     rax, cs:g_pfnResultLoggingCallback
0x14000518d  mov     ebp, 800h
0x140005192  test    rax, rax
0x140005195  jz      short loc_1400051AE
0x140005197  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000519e  jnz     short loc_1400051AE
0x1400051a0  mov     r8d, ebp
0x1400051a3  mov     rdx, rsi
0x1400051a6  mov     rcx, rbx
0x1400051a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051ae  cmp     [rsi], di
0x1400051b1  jnz     short loc_1400051C1
0x1400051b3  mov     r8, rbx; unsigned __int64
0x1400051b6  mov     rdx, rbp; unsigned __int16 *
0x1400051b9  mov     rcx, rsi; this
0x1400051bc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400051c1  mov     rcx, rsi; lpOutputString
0x1400051c4  call    cs:__imp_OutputDebugStringW
0x1400051ca  test    byte ptr [rbx+4], 4
0x1400051ce  jnz     short loc_1400051D9
0x1400051d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400051d7  jz      short loc_1400051EA
0x1400051d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400051e0  test    rax, rax
0x1400051e3  jz      short loc_1400051EA
0x1400051e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051ea  mov     rbx, [rsp+78h+arg_10]
0x1400051f2  add     rsp, 40h
0x1400051f6  pop     r15
0x1400051f8  pop     r14
0x1400051fa  pop     r13
0x1400051fc  pop     r12
0x1400051fe  pop     rdi
0x1400051ff  pop     rsi
0x140005200  pop     rbp
0x140005201  retn
0x140005202  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
