# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005f20`
- end: `0x180006223`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800076f8`

## callees

- `0x180004b14`
- `0x180004f80`
- `0x180004f9c`
- `0x180004fb8`
- `0x180004fe0`
- `0x180005220`
- `0x180005f20`
- `0x180006490`
- `0x1800070f0`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006045`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006045`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006164`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006164`

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
  int v19; // esi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
}

```

## disassembly

```asm
0x180005f20  mov     [rsp+arg_10], rbx
0x180005f25  mov     [rsp+arg_8], edx
0x180005f29  mov     [rsp+arg_0], rcx
0x180005f2e  push    rbp
0x180005f2f  push    rsi
0x180005f30  push    rdi
0x180005f31  push    r12
0x180005f33  push    r13
0x180005f35  push    r14
0x180005f37  push    r15
0x180005f39  sub     rsp, 40h
0x180005f3d  mov     r12, r9
0x180005f40  mov     r13, r8
0x180005f43  mov     r10, rcx
0x180005f46  xor     r8d, r8d
0x180005f49  mov     r14, [rsp+78h+lpOutputString]
0x180005f51  mov     [r14], r8w
0x180005f55  mov     rax, [rsp+78h+arg_60]
0x180005f5d  mov     [rax], r8b
0x180005f60  mov     r15, [rsp+78h+arg_38]
0x180005f68  mov     edi, [r15]
0x180005f6b  mov     rbx, [rsp+78h+arg_78]
0x180005f73  mov     [rbx+8], edi
0x180005f76  mov     eax, [r15+4]
0x180005f7a  mov     [rbx+0Ch], eax
0x180005f7d  mov     esi, r8d
0x180005f80  mov     ebp, [rsp+78h+arg_30]
0x180005f87  mov     ecx, ebp
0x180005f89  test    ebp, ebp
0x180005f8b  jz      short loc_180005FF6
0x180005f8d  sub     ecx, 1
0x180005f90  jz      short loc_180005FED
0x180005f92  sub     ecx, 1
0x180005f95  jz      short loc_180005FA5
0x180005f97  cmp     ecx, 1
0x180005f9a  jnz     short loc_180005FFF
0x180005f9c  mov     ecx, edi; this
0x180005f9e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005fa3  jmp     short loc_180005FFD
0x180005fa5  test    edi, edi
0x180005fa7  js      short loc_180005FE4
0x180005fa9  mov     edi, 8007029Ch
0x180005fae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005fb2  mov     rax, [rsp+78h+arg_28]
0x180005fba  mov     [rsp+78h+var_50], rax; __int64
0x180005fbf  mov     rax, [rsp+78h+arg_20]
0x180005fc7  mov     [rsp+78h+var_58], rax; __int64
0x180005fcc  mov     r8, r13; int
0x180005fcf  mov     rcx, r10; int
0x180005fd2  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005fd7  mov     [rbx+8], edi
0x180005fda  mov     ecx, edi; this
0x180005fdc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005fe1  mov     [rbx+0Ch], eax
0x180005fe4  mov     ecx, edi; this
0x180005fe6  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005feb  jmp     short loc_180005FFD
0x180005fed  mov     ecx, edi; this
0x180005fef  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005ff4  jmp     short loc_180005FFD
0x180005ff6  mov     ecx, edi; this
0x180005ff8  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005ffd  mov     esi, eax
0x180005fff  mov     [rbx], ebp
0x180006001  mov     eax, [rsp+78h+arg_70]
0x180006008  mov     [rbx+4], eax
0x18000600b  cmp     dword ptr [r15+8], 1
0x180006010  jnz     short loc_180006018
0x180006012  or      eax, 8
0x180006015  mov     [rbx+4], eax
0x180006018  mov     eax, 1
0x18000601d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006025  inc     eax
0x180006027  mov     [rbx+10h], eax
0x18000602a  mov     rax, [rsp+78h+arg_40]
0x180006032  xor     edi, edi
0x180006034  test    rax, rax
0x180006037  jz      short loc_18000603E
0x180006039  cmp     [rax], di
0x18000603c  jnz     short loc_180006041
0x18000603e  mov     rax, rdi
0x180006041  mov     [rbx+18h], rax
0x180006045  call    cs:__imp_GetCurrentThreadId
0x18000604b  mov     [rbx+20h], eax
0x18000604e  mov     [rbx+38h], r13
0x180006052  mov     eax, [rsp+78h+arg_8]
0x180006059  mov     [rbx+40h], eax
0x18000605c  mov     [rbx+44h], esi
0x18000605f  mov     rax, [rsp+78h+arg_20]
0x180006067  mov     [rbx+28h], rax
0x18000606b  mov     [rbx+30h], r12
0x18000606f  mov     rax, [rsp+78h+arg_28]
0x180006077  mov     [rbx+88h], rax
0x18000607e  mov     rax, [rsp+78h+arg_0]
0x180006086  mov     [rbx+90h], rax
0x18000608d  mov     [rbx+48h], rdi
0x180006091  xorps   xmm0, xmm0
0x180006094  xor     eax, eax
0x180006096  movups  xmmword ptr [rbx+68h], xmm0
0x18000609a  mov     [rbx+78h], rax
0x18000609e  movups  xmmword ptr [rbx+50h], xmm0
0x1800060a2  mov     [rbx+60h], rax
0x1800060a6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800060ad  test    rax, rax
0x1800060b0  jz      short loc_1800060B9
0x1800060b2  call    _guard_dispatch_icall
0x1800060b7  jmp     short loc_1800060BC
0x1800060b9  mov     rax, rdi
0x1800060bc  mov     [rbx+80h], rax
0x1800060c3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800060ca  test    rax, rax
0x1800060cd  jz      short loc_1800060D7
0x1800060cf  mov     rcx, rbx
0x1800060d2  call    _guard_dispatch_icall
0x1800060d7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800060de  test    rax, rax
0x1800060e1  jz      short loc_1800060F9
0x1800060e3  mov     r8d, 400h
0x1800060e9  mov     rdx, [rsp+78h+arg_60]
0x1800060f1  mov     rcx, rbx
0x1800060f4  call    _guard_dispatch_icall
0x1800060f9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006100  test    rax, rax
0x180006103  jz      short loc_18000610D
0x180006105  mov     rcx, rbx
0x180006108  call    _guard_dispatch_icall
0x18000610d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006114  test    rax, rax
0x180006117  jz      short loc_180006127
0x180006119  test    byte ptr [rbx+4], 2
0x18000611d  jnz     short loc_180006127
0x18000611f  mov     rcx, rbx
0x180006122  call    _guard_dispatch_icall
0x180006127  cmp     [rbx+8], edi
0x18000612a  jl      short loc_180006145
0x18000612c  cmp     ebp, 3
0x18000612f  jnz     loc_18000621D
0x180006135  mov     ecx, 8000FFFFh; this
0x18000613a  mov     [rbx+8], ecx
0x18000613d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006142  mov     [rbx+0Ch], eax
0x180006145  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000614c  jnz     short loc_180006175
0x18000614e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006155  test    rax, rax
0x180006158  jz      short loc_180006164
0x18000615a  call    _guard_dispatch_icall
0x18000615f  movzx   ecx, al
0x180006162  jmp     short loc_180006171
0x180006164  call    cs:__imp_IsDebuggerPresent
0x18000616a  mov     ecx, edi
0x18000616c  test    eax, eax
0x18000616e  setnz   cl
0x180006171  test    ecx, ecx
0x180006173  jz      short loc_18000617B
0x180006175  test    byte ptr [rbx+4], 2
0x180006179  jz      short loc_18000619F
0x18000617b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006182  test    rax, rax
0x180006185  jz      short loc_1800061E4
0x180006187  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000618e  jnz     short loc_1800061E4
0x180006190  xor     r8d, r8d
0x180006193  xor     edx, edx
0x180006195  mov     rcx, rbx
0x180006198  call    _guard_dispatch_icall
0x18000619d  jmp     short loc_1800061E4
0x18000619f  mov     esi, 800h
0x1800061a4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800061ab  test    rax, rax
0x1800061ae  jz      short loc_1800061C7
0x1800061b0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800061b7  jnz     short loc_1800061C7
0x1800061b9  mov     r8d, esi
0x1800061bc  mov     rdx, r14
0x1800061bf  mov     rcx, rbx
0x1800061c2  call    _guard_dispatch_icall
0x1800061c7  cmp     [r14], di
0x1800061cb  jnz     short loc_1800061DB
0x1800061cd  mov     r8, rbx; unsigned __int64
0x1800061d0  mov     rdx, rsi; wchar_t *
0x1800061d3  mov     rcx, r14; this
0x1800061d6  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800061db  mov     rcx, r14; lpOutputString
0x1800061de  call    cs:__imp_OutputDebugStringW
0x1800061e4  test    byte ptr [rbx+4], 4
0x1800061e8  jnz     short loc_1800061F3
0x1800061ea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800061f1  jz      short loc_180006205
0x1800061f3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800061fa  test    rax, rax
0x1800061fd  jz      short loc_180006205
0x1800061ff  call    _guard_dispatch_icall
0x180006204  nop
0x180006205  mov     rbx, [rsp+78h+arg_10]
0x18000620d  add     rsp, 40h
0x180006211  pop     r15
0x180006213  pop     r14
0x180006215  pop     r13
0x180006217  pop     r12
0x180006219  pop     rdi
0x18000621a  pop     rsi
0x18000621b  pop     rbp
0x18000621c  retn
0x18000621d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
