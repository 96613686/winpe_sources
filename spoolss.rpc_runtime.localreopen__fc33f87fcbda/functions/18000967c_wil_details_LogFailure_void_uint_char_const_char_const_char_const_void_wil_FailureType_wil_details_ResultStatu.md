# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000967c`
- end: `0x180009988`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180006cb4`
- `0x180007014`

## callees

- `0x180004f8c`
- `0x180006bf4`
- `0x180008c64`
- `0x18000967c`
- `0x18000a31c`
- `0x18000a340`
- `0x18000a4a4`
- `0x18000a4c4`
- `0x18000c3c0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000979f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000979f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800098c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800098c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000993c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000993c`

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
0x18000967c  mov     [rsp+arg_10], rbx
0x180009681  mov     [rsp+arg_8], edx
0x180009685  mov     [rsp+arg_0], rcx
0x18000968a  push    rbp
0x18000968b  push    rsi
0x18000968c  push    rdi
0x18000968d  push    r12
0x18000968f  push    r13
0x180009691  push    r14
0x180009693  push    r15
0x180009695  sub     rsp, 40h
0x180009699  mov     r12, r9
0x18000969c  mov     r13, r8
0x18000969f  mov     r10, rcx
0x1800096a2  xor     eax, eax
0x1800096a4  mov     rsi, [rsp+78h+lpOutputString]
0x1800096ac  mov     [rsi], ax
0x1800096af  mov     rax, [rsp+78h+arg_60]
0x1800096b7  mov     byte ptr [rax], 0
0x1800096ba  mov     r14, [rsp+78h+arg_38]
0x1800096c2  mov     edi, [r14]
0x1800096c5  mov     rbx, [rsp+78h+arg_78]
0x1800096cd  mov     [rbx+8], edi
0x1800096d0  mov     eax, [r14+4]
0x1800096d4  mov     [rbx+0Ch], eax
0x1800096d7  xor     ebp, ebp
0x1800096d9  mov     r15d, [rsp+78h+arg_30]
0x1800096e1  mov     ecx, r15d
0x1800096e4  test    r15d, r15d
0x1800096e7  jz      short loc_18000974F
0x1800096e9  sub     ecx, 1
0x1800096ec  jz      short loc_180009746
0x1800096ee  sub     ecx, 1
0x1800096f1  jz      short loc_180009701
0x1800096f3  cmp     ecx, 1
0x1800096f6  jnz     short loc_180009758
0x1800096f8  mov     ecx, edi; this
0x1800096fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800096ff  jmp     short loc_180009756
0x180009701  test    edi, edi
0x180009703  js      short loc_18000973D
0x180009705  mov     edi, 8007029Ch
0x18000970a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000970e  mov     rax, [rsp+78h+arg_28]
0x180009716  mov     [rsp+78h+var_50], rax; __int64
0x18000971b  mov     rax, [rsp+78h+arg_20]
0x180009723  mov     [rsp+78h+var_58], rax; __int64
0x180009728  mov     rcx, r10; int
0x18000972b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009730  mov     [rbx+8], edi
0x180009733  mov     ecx, edi; this
0x180009735  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000973a  mov     [rbx+0Ch], eax
0x18000973d  mov     ecx, edi; this
0x18000973f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009744  jmp     short loc_180009756
0x180009746  mov     ecx, edi; this
0x180009748  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000974d  jmp     short loc_180009756
0x18000974f  mov     ecx, edi; this
0x180009751  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009756  mov     ebp, eax
0x180009758  mov     [rbx], r15d
0x18000975b  mov     eax, [rsp+78h+arg_70]
0x180009762  mov     [rbx+4], eax
0x180009765  cmp     dword ptr [r14+8], 1
0x18000976a  jnz     short loc_180009772
0x18000976c  or      eax, 8
0x18000976f  mov     [rbx+4], eax
0x180009772  mov     eax, 1
0x180009777  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000977f  inc     eax
0x180009781  mov     [rbx+10h], eax
0x180009784  mov     rax, [rsp+78h+arg_40]
0x18000978c  xor     edi, edi
0x18000978e  test    rax, rax
0x180009791  jz      short loc_180009798
0x180009793  cmp     [rax], di
0x180009796  jnz     short loc_18000979B
0x180009798  mov     rax, rdi
0x18000979b  mov     [rbx+18h], rax
0x18000979f  call    cs:__imp_GetCurrentThreadId
0x1800097a6  nop     dword ptr [rax+rax+00h]
0x1800097ab  mov     [rbx+20h], eax
0x1800097ae  mov     [rbx+38h], r13
0x1800097b2  mov     eax, [rsp+78h+arg_8]
0x1800097b9  mov     [rbx+40h], eax
0x1800097bc  mov     [rbx+44h], ebp
0x1800097bf  mov     rax, [rsp+78h+arg_20]
0x1800097c7  mov     [rbx+28h], rax
0x1800097cb  mov     [rbx+30h], r12
0x1800097cf  mov     rax, [rsp+78h+arg_28]
0x1800097d7  mov     [rbx+88h], rax
0x1800097de  mov     rax, [rsp+78h+arg_0]
0x1800097e6  mov     [rbx+90h], rax
0x1800097ed  mov     [rbx+48h], rdi
0x1800097f1  xorps   xmm0, xmm0
0x1800097f4  xor     eax, eax
0x1800097f6  movups  xmmword ptr [rbx+68h], xmm0
0x1800097fa  mov     [rbx+78h], rax
0x1800097fe  movups  xmmword ptr [rbx+50h], xmm0
0x180009802  mov     [rbx+60h], rax
0x180009806  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000980d  test    rax, rax
0x180009810  jz      short loc_180009819
0x180009812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009817  jmp     short loc_18000981C
0x180009819  mov     rax, rdi
0x18000981c  mov     [rbx+80h], rax
0x180009823  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000982a  test    rax, rax
0x18000982d  jz      short loc_180009837
0x18000982f  mov     rcx, rbx
0x180009832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009837  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000983e  test    rax, rax
0x180009841  jz      short loc_180009859
0x180009843  mov     r8d, 400h
0x180009849  mov     rdx, [rsp+78h+arg_60]
0x180009851  mov     rcx, rbx
0x180009854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009859  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009860  test    rax, rax
0x180009863  jz      short loc_18000986D
0x180009865  mov     rcx, rbx
0x180009868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000986d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009874  test    rax, rax
0x180009877  jz      short loc_180009887
0x180009879  test    byte ptr [rbx+4], 2
0x18000987d  jnz     short loc_180009887
0x18000987f  mov     rcx, rbx
0x180009882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009887  cmp     [rbx+8], edi
0x18000988a  jl      short loc_1800098A6
0x18000988c  cmp     r15d, 3
0x180009890  jnz     loc_180009982
0x180009896  mov     ecx, 8000FFFFh; this
0x18000989b  mov     [rbx+8], ecx
0x18000989e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800098a3  mov     [rbx+0Ch], eax
0x1800098a6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800098ad  jnz     short loc_1800098D4
0x1800098af  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800098b6  test    rax, rax
0x1800098b9  jz      short loc_1800098C4
0x1800098bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c0  test    al, al
0x1800098c2  jmp     short loc_1800098D2
0x1800098c4  call    cs:__imp_IsDebuggerPresent
0x1800098cb  nop     dword ptr [rax+rax+00h]
0x1800098d0  test    eax, eax
0x1800098d2  jz      short loc_1800098DA
0x1800098d4  test    byte ptr [rbx+4], 2
0x1800098d8  jz      short loc_1800098FE
0x1800098da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800098e1  test    rax, rax
0x1800098e4  jz      short loc_180009948
0x1800098e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800098ed  jnz     short loc_180009948
0x1800098ef  xor     r8d, r8d
0x1800098f2  xor     edx, edx
0x1800098f4  mov     rcx, rbx
0x1800098f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098fc  jmp     short loc_180009948
0x1800098fe  mov     ebp, 800h
0x180009903  mov     rax, cs:g_pfnResultLoggingCallback
0x18000990a  test    rax, rax
0x18000990d  jz      short loc_180009926
0x18000990f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009916  jnz     short loc_180009926
0x180009918  mov     r8d, ebp
0x18000991b  mov     rdx, rsi
0x18000991e  mov     rcx, rbx
0x180009921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009926  cmp     [rsi], di
0x180009929  jnz     short loc_180009939
0x18000992b  mov     r8, rbx; unsigned __int64
0x18000992e  mov     rdx, rbp; unsigned __int16 *
0x180009931  mov     rcx, rsi; this
0x180009934  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009939  mov     rcx, rsi; lpOutputString
0x18000993c  call    cs:__imp_OutputDebugStringW
0x180009943  nop     dword ptr [rax+rax+00h]
0x180009948  test    byte ptr [rbx+4], 4
0x18000994c  jnz     short loc_180009957
0x18000994e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009955  jz      short loc_180009969
0x180009957  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000995e  test    rax, rax
0x180009961  jz      short loc_180009969
0x180009963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009968  nop
0x180009969  mov     rbx, [rsp+78h+arg_10]
0x180009971  add     rsp, 40h
0x180009975  pop     r15
0x180009977  pop     r14
0x180009979  pop     r13
0x18000997b  pop     r12
0x18000997d  pop     rdi
0x18000997e  pop     rsi
0x18000997f  pop     rbp
0x180009980  retn
0x180009982  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
