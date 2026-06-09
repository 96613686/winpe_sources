# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180048d84`
- end: `0x18004908f`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180047bd8`
- `0x180047f38`

## callees

- `0x1800400dc`
- `0x180047b18`
- `0x180048764`
- `0x180048d84`
- `0x1800496b4`
- `0x1800496e0`
- `0x1800496f4`
- `0x180049714`
- `0x180049dbc`
- `0x18007a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180048fcc`
- `KERNEL32!IsDebuggerPresent` at `0x180048fcc`
- `KERNEL32!OutputDebugStringW` at `0x180049044`
- `KERNEL32!OutputDebugStringW` at `0x180049044`
- `KERNEL32!GetCurrentThreadId` at `0x180048ea7`
- `KERNEL32!GetCurrentThreadId` at `0x180048ea7`

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
0x180048d84  mov     [rsp+arg_10], rbx
0x180048d89  mov     [rsp+arg_8], edx
0x180048d8d  mov     [rsp+arg_0], rcx
0x180048d92  push    rbp
0x180048d93  push    rsi
0x180048d94  push    rdi
0x180048d95  push    r12
0x180048d97  push    r13
0x180048d99  push    r14
0x180048d9b  push    r15
0x180048d9d  sub     rsp, 40h
0x180048da1  mov     r14, [rsp+78h+arg_38]
0x180048da9  xor     eax, eax
0x180048dab  mov     rbx, [rsp+78h+arg_78]
0x180048db3  xor     ebp, ebp
0x180048db5  mov     r15d, [rsp+78h+arg_30]
0x180048dbd  mov     r10, rcx
0x180048dc0  mov     rsi, [rsp+78h+lpOutputString]
0x180048dc8  mov     r12, r9
0x180048dcb  mov     r13, r8
0x180048dce  mov     ecx, r15d
0x180048dd1  mov     [rsi], ax
0x180048dd4  mov     rax, [rsp+78h+arg_60]
0x180048ddc  mov     byte ptr [rax], 0
0x180048ddf  mov     edi, [r14]
0x180048de2  mov     [rbx+8], edi
0x180048de5  mov     eax, [r14+4]
0x180048de9  mov     [rbx+0Ch], eax
0x180048dec  test    r15d, r15d
0x180048def  jz      short loc_180048E57
0x180048df1  sub     ecx, 1
0x180048df4  jz      short loc_180048E4E
0x180048df6  sub     ecx, 1
0x180048df9  jz      short loc_180048E09
0x180048dfb  cmp     ecx, 1
0x180048dfe  jnz     short loc_180048E60
0x180048e00  mov     ecx, edi; this
0x180048e02  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180048e07  jmp     short loc_180048E5E
0x180048e09  test    edi, edi
0x180048e0b  js      short loc_180048E45
0x180048e0d  mov     rax, [rsp+78h+arg_28]
0x180048e15  mov     edi, 8007029Ch
0x180048e1a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180048e1e  mov     rcx, r10; int
0x180048e21  mov     [rsp+78h+var_50], rax; __int64
0x180048e26  mov     rax, [rsp+78h+arg_20]
0x180048e2e  mov     [rsp+78h+var_58], rax; __int64
0x180048e33  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180048e38  mov     ecx, edi; this
0x180048e3a  mov     [rbx+8], edi
0x180048e3d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180048e42  mov     [rbx+0Ch], eax
0x180048e45  mov     ecx, edi; this
0x180048e47  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180048e4c  jmp     short loc_180048E5E
0x180048e4e  mov     ecx, edi; this
0x180048e50  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180048e55  jmp     short loc_180048E5E
0x180048e57  mov     ecx, edi; this
0x180048e59  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180048e5e  mov     ebp, eax
0x180048e60  mov     eax, [rsp+78h+arg_70]
0x180048e67  mov     [rbx+4], eax
0x180048e6a  mov     [rbx], r15d
0x180048e6d  cmp     dword ptr [r14+8], 1
0x180048e72  jnz     short loc_180048E7A
0x180048e74  or      eax, 8
0x180048e77  mov     [rbx+4], eax
0x180048e7a  mov     eax, 1
0x180048e7f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180048e87  inc     eax
0x180048e89  xor     edi, edi
0x180048e8b  mov     [rbx+10h], eax
0x180048e8e  mov     rax, [rsp+78h+arg_40]
0x180048e96  test    rax, rax
0x180048e99  jz      short loc_180048EA0
0x180048e9b  cmp     [rax], di
0x180048e9e  jnz     short loc_180048EA3
0x180048ea0  mov     rax, rdi
0x180048ea3  mov     [rbx+18h], rax
0x180048ea7  call    cs:__imp_GetCurrentThreadId
0x180048eae  nop     dword ptr [rax+rax+00h]
0x180048eb3  mov     [rbx+38h], r13
0x180048eb7  xorps   xmm0, xmm0
0x180048eba  mov     [rbx+20h], eax
0x180048ebd  mov     eax, [rsp+78h+arg_8]
0x180048ec4  mov     [rbx+40h], eax
0x180048ec7  mov     rax, [rsp+78h+arg_20]
0x180048ecf  mov     [rbx+28h], rax
0x180048ed3  mov     rax, [rsp+78h+arg_28]
0x180048edb  mov     [rbx+88h], rax
0x180048ee2  mov     rax, [rsp+78h+arg_0]
0x180048eea  mov     [rbx+90h], rax
0x180048ef1  xor     eax, eax
0x180048ef3  mov     [rbx+44h], ebp
0x180048ef6  mov     [rbx+30h], r12
0x180048efa  mov     [rbx+48h], rdi
0x180048efe  movups  xmmword ptr [rbx+68h], xmm0
0x180048f02  mov     [rbx+78h], rax
0x180048f06  movups  xmmword ptr [rbx+50h], xmm0
0x180048f0a  mov     [rbx+60h], rax
0x180048f0e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180048f15  test    rax, rax
0x180048f18  jz      short loc_180048F21
0x180048f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f1f  jmp     short loc_180048F24
0x180048f21  mov     rax, rdi
0x180048f24  mov     [rbx+80h], rax
0x180048f2b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180048f32  test    rax, rax
0x180048f35  jz      short loc_180048F3F
0x180048f37  mov     rcx, rbx
0x180048f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f3f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180048f46  test    rax, rax
0x180048f49  jz      short loc_180048F61
0x180048f4b  mov     rdx, [rsp+78h+arg_60]
0x180048f53  mov     r8d, 400h
0x180048f59  mov     rcx, rbx
0x180048f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f61  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180048f68  test    rax, rax
0x180048f6b  jz      short loc_180048F75
0x180048f6d  mov     rcx, rbx
0x180048f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f75  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180048f7c  test    rax, rax
0x180048f7f  jz      short loc_180048F8F
0x180048f81  test    byte ptr [rbx+4], 2
0x180048f85  jnz     short loc_180048F8F
0x180048f87  mov     rcx, rbx
0x180048f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f8f  cmp     [rbx+8], edi
0x180048f92  jl      short loc_180048FAE
0x180048f94  cmp     r15d, 3
0x180048f98  jnz     loc_180049089
0x180048f9e  mov     ecx, 8000FFFFh; this
0x180048fa3  mov     [rbx+8], ecx
0x180048fa6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180048fab  mov     [rbx+0Ch], eax
0x180048fae  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180048fb5  jnz     short loc_180048FDC
0x180048fb7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180048fbe  test    rax, rax
0x180048fc1  jz      short loc_180048FCC
0x180048fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fc8  test    al, al
0x180048fca  jmp     short loc_180048FDA
0x180048fcc  call    cs:__imp_IsDebuggerPresent
0x180048fd3  nop     dword ptr [rax+rax+00h]
0x180048fd8  test    eax, eax
0x180048fda  jz      short loc_180048FE2
0x180048fdc  test    byte ptr [rbx+4], 2
0x180048fe0  jz      short loc_180049006
0x180048fe2  mov     rax, cs:g_pfnResultLoggingCallback
0x180048fe9  test    rax, rax
0x180048fec  jz      short loc_180049050
0x180048fee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180048ff5  jnz     short loc_180049050
0x180048ff7  xor     r8d, r8d
0x180048ffa  xor     edx, edx
0x180048ffc  mov     rcx, rbx
0x180048fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049004  jmp     short loc_180049050
0x180049006  mov     rax, cs:g_pfnResultLoggingCallback
0x18004900d  mov     ebp, 800h
0x180049012  test    rax, rax
0x180049015  jz      short loc_18004902E
0x180049017  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004901e  jnz     short loc_18004902E
0x180049020  mov     r8d, ebp
0x180049023  mov     rdx, rsi
0x180049026  mov     rcx, rbx
0x180049029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004902e  cmp     [rsi], di
0x180049031  jnz     short loc_180049041
0x180049033  mov     r8, rbx; unsigned __int64
0x180049036  mov     rdx, rbp; unsigned __int16 *
0x180049039  mov     rcx, rsi; this
0x18004903c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180049041  mov     rcx, rsi; lpOutputString
0x180049044  call    cs:__imp_OutputDebugStringW
0x18004904b  nop     dword ptr [rax+rax+00h]
0x180049050  test    byte ptr [rbx+4], 4
0x180049054  jnz     short loc_18004905F
0x180049056  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004905d  jz      short loc_180049070
0x18004905f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180049066  test    rax, rax
0x180049069  jz      short loc_180049070
0x18004906b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049070  mov     rbx, [rsp+78h+arg_10]
0x180049078  add     rsp, 40h
0x18004907c  pop     r15
0x18004907e  pop     r14
0x180049080  pop     r13
0x180049082  pop     r12
0x180049084  pop     rdi
0x180049085  pop     rsi
0x180049086  pop     rbp
0x180049087  retn
0x180049089  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
