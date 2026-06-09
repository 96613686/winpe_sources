# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009654`
- end: `0x18000994c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007520`

## callees

- `0x180006f5c`
- `0x180008a04`
- `0x180009270`
- `0x180009654`
- `0x18000a400`
- `0x18000a420`
- `0x18000a5a4`
- `0x18000a5c0`
- `0x18000bc9c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009777`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009896`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009896`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009908`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009908`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x180009654  mov     [rsp+arg_10], rbx
0x180009659  mov     [rsp+arg_8], edx
0x18000965d  mov     [rsp+arg_0], rcx
0x180009662  push    rbp
0x180009663  push    rsi
0x180009664  push    rdi
0x180009665  push    r12
0x180009667  push    r13
0x180009669  push    r14
0x18000966b  push    r15
0x18000966d  sub     rsp, 40h
0x180009671  mov     r14, [rsp+78h+arg_38]
0x180009679  xor     eax, eax
0x18000967b  mov     rbx, [rsp+78h+arg_78]
0x180009683  xor     ebp, ebp
0x180009685  mov     r15d, [rsp+78h+arg_30]
0x18000968d  mov     r10, rcx
0x180009690  mov     rsi, [rsp+78h+lpOutputString]
0x180009698  mov     r12, r9
0x18000969b  mov     r13, r8
0x18000969e  mov     ecx, r15d
0x1800096a1  mov     [rsi], ax
0x1800096a4  mov     rax, [rsp+78h+arg_60]
0x1800096ac  mov     byte ptr [rax], 0
0x1800096af  mov     edi, [r14]
0x1800096b2  mov     [rbx+8], edi
0x1800096b5  mov     eax, [r14+4]
0x1800096b9  mov     [rbx+0Ch], eax
0x1800096bc  test    r15d, r15d
0x1800096bf  jz      short loc_180009727
0x1800096c1  sub     ecx, 1
0x1800096c4  jz      short loc_18000971E
0x1800096c6  sub     ecx, 1
0x1800096c9  jz      short loc_1800096D9
0x1800096cb  cmp     ecx, 1
0x1800096ce  jnz     short loc_180009730
0x1800096d0  mov     ecx, edi; this
0x1800096d2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800096d7  jmp     short loc_18000972E
0x1800096d9  test    edi, edi
0x1800096db  js      short loc_180009715
0x1800096dd  mov     rax, [rsp+78h+arg_28]
0x1800096e5  mov     edi, 8007029Ch
0x1800096ea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800096ee  mov     rcx, r10; int
0x1800096f1  mov     [rsp+78h+var_50], rax; __int64
0x1800096f6  mov     rax, [rsp+78h+arg_20]
0x1800096fe  mov     [rsp+78h+var_58], rax; __int64
0x180009703  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009708  mov     ecx, edi; this
0x18000970a  mov     [rbx+8], edi
0x18000970d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009712  mov     [rbx+0Ch], eax
0x180009715  mov     ecx, edi; this
0x180009717  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000971c  jmp     short loc_18000972E
0x18000971e  mov     ecx, edi; this
0x180009720  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009725  jmp     short loc_18000972E
0x180009727  mov     ecx, edi; this
0x180009729  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000972e  mov     ebp, eax
0x180009730  mov     eax, [rsp+78h+arg_70]
0x180009737  mov     [rbx+4], eax
0x18000973a  mov     [rbx], r15d
0x18000973d  cmp     dword ptr [r14+8], 1
0x180009742  jnz     short loc_18000974A
0x180009744  or      eax, 8
0x180009747  mov     [rbx+4], eax
0x18000974a  mov     eax, 1
0x18000974f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009757  inc     eax
0x180009759  xor     edi, edi
0x18000975b  mov     [rbx+10h], eax
0x18000975e  mov     rax, [rsp+78h+arg_40]
0x180009766  test    rax, rax
0x180009769  jz      short loc_180009770
0x18000976b  cmp     [rax], di
0x18000976e  jnz     short loc_180009773
0x180009770  mov     rax, rdi
0x180009773  mov     [rbx+18h], rax
0x180009777  call    cs:__imp_GetCurrentThreadId
0x18000977d  mov     [rbx+38h], r13
0x180009781  xorps   xmm0, xmm0
0x180009784  mov     [rbx+20h], eax
0x180009787  mov     eax, [rsp+78h+arg_8]
0x18000978e  mov     [rbx+40h], eax
0x180009791  mov     rax, [rsp+78h+arg_20]
0x180009799  mov     [rbx+28h], rax
0x18000979d  mov     rax, [rsp+78h+arg_28]
0x1800097a5  mov     [rbx+88h], rax
0x1800097ac  mov     rax, [rsp+78h+arg_0]
0x1800097b4  mov     [rbx+90h], rax
0x1800097bb  xor     eax, eax
0x1800097bd  mov     [rbx+44h], ebp
0x1800097c0  mov     [rbx+30h], r12
0x1800097c4  mov     [rbx+48h], rdi
0x1800097c8  movups  xmmword ptr [rbx+68h], xmm0
0x1800097cc  mov     [rbx+78h], rax
0x1800097d0  movups  xmmword ptr [rbx+50h], xmm0
0x1800097d4  mov     [rbx+60h], rax
0x1800097d8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800097df  test    rax, rax
0x1800097e2  jz      short loc_1800097EB
0x1800097e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097e9  jmp     short loc_1800097EE
0x1800097eb  mov     rax, rdi
0x1800097ee  mov     [rbx+80h], rax
0x1800097f5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800097fc  test    rax, rax
0x1800097ff  jz      short loc_180009809
0x180009801  mov     rcx, rbx
0x180009804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009809  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009810  test    rax, rax
0x180009813  jz      short loc_18000982B
0x180009815  mov     rdx, [rsp+78h+arg_60]
0x18000981d  mov     r8d, 400h
0x180009823  mov     rcx, rbx
0x180009826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000982b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009832  test    rax, rax
0x180009835  jz      short loc_18000983F
0x180009837  mov     rcx, rbx
0x18000983a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000983f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009846  test    rax, rax
0x180009849  jz      short loc_180009859
0x18000984b  test    byte ptr [rbx+4], 2
0x18000984f  jnz     short loc_180009859
0x180009851  mov     rcx, rbx
0x180009854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009859  cmp     [rbx+8], edi
0x18000985c  jl      short loc_180009878
0x18000985e  cmp     r15d, 3
0x180009862  jnz     loc_180009946
0x180009868  mov     ecx, 8000FFFFh; this
0x18000986d  mov     [rbx+8], ecx
0x180009870  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009875  mov     [rbx+0Ch], eax
0x180009878  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000987f  jnz     short loc_1800098A0
0x180009881  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009888  test    rax, rax
0x18000988b  jz      short loc_180009896
0x18000988d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009892  test    al, al
0x180009894  jmp     short loc_18000989E
0x180009896  call    cs:__imp_IsDebuggerPresent
0x18000989c  test    eax, eax
0x18000989e  jz      short loc_1800098A6
0x1800098a0  test    byte ptr [rbx+4], 2
0x1800098a4  jz      short loc_1800098CA
0x1800098a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800098ad  test    rax, rax
0x1800098b0  jz      short loc_18000990E
0x1800098b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800098b9  jnz     short loc_18000990E
0x1800098bb  xor     r8d, r8d
0x1800098be  xor     edx, edx
0x1800098c0  mov     rcx, rbx
0x1800098c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c8  jmp     short loc_18000990E
0x1800098ca  mov     rax, cs:g_pfnResultLoggingCallback
0x1800098d1  mov     ebp, 800h
0x1800098d6  test    rax, rax
0x1800098d9  jz      short loc_1800098F2
0x1800098db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800098e2  jnz     short loc_1800098F2
0x1800098e4  mov     r8d, ebp
0x1800098e7  mov     rdx, rsi
0x1800098ea  mov     rcx, rbx
0x1800098ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098f2  cmp     [rsi], di
0x1800098f5  jnz     short loc_180009905
0x1800098f7  mov     r8, rbx; unsigned __int64
0x1800098fa  mov     rdx, rbp; unsigned __int16 *
0x1800098fd  mov     rcx, rsi; this
0x180009900  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009905  mov     rcx, rsi; lpOutputString
0x180009908  call    cs:__imp_OutputDebugStringW
0x18000990e  test    byte ptr [rbx+4], 4
0x180009912  jnz     short loc_18000991D
0x180009914  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000991b  jz      short loc_18000992E
0x18000991d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009924  test    rax, rax
0x180009927  jz      short loc_18000992E
0x180009929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000992e  mov     rbx, [rsp+78h+arg_10]
0x180009936  add     rsp, 40h
0x18000993a  pop     r15
0x18000993c  pop     r14
0x18000993e  pop     r13
0x180009940  pop     r12
0x180009942  pop     rdi
0x180009943  pop     rsi
0x180009944  pop     rbp
0x180009945  retn
0x180009946  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
