# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180015594`
- end: `0x180015888`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180013ee8`
- `0x180013f98`
- `0x180014088`

## callees

- `0x180012164`
- `0x180013e3c`
- `0x180014cd4`
- `0x180015594`
- `0x180015d7c`
- `0x180015da0`
- `0x180015e60`
- `0x180015e7c`
- `0x180016e1c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001584a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001584a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800157d8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800157d8`

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
0x180015594  mov     [rsp+arg_10], rbx
0x180015599  mov     [rsp+arg_8], edx
0x18001559d  mov     [rsp+arg_0], rcx
0x1800155a2  push    rbp
0x1800155a3  push    rsi
0x1800155a4  push    rdi
0x1800155a5  push    r12
0x1800155a7  push    r13
0x1800155a9  push    r14
0x1800155ab  push    r15
0x1800155ad  sub     rsp, 40h
0x1800155b1  mov     r14, [rsp+78h+arg_38]
0x1800155b9  xor     eax, eax
0x1800155bb  mov     rbx, [rsp+78h+arg_78]
0x1800155c3  xor     ebp, ebp
0x1800155c5  mov     r15d, [rsp+78h+arg_30]
0x1800155cd  mov     r10, rcx
0x1800155d0  mov     rsi, [rsp+78h+lpOutputString]
0x1800155d8  mov     r12, r9
0x1800155db  mov     r13, r8
0x1800155de  mov     ecx, r15d
0x1800155e1  mov     [rsi], ax
0x1800155e4  mov     rax, [rsp+78h+arg_60]
0x1800155ec  mov     byte ptr [rax], 0
0x1800155ef  mov     edi, [r14]
0x1800155f2  mov     [rbx+8], edi
0x1800155f5  mov     eax, [r14+4]
0x1800155f9  mov     [rbx+0Ch], eax
0x1800155fc  test    r15d, r15d
0x1800155ff  jz      short loc_180015667
0x180015601  sub     ecx, 1
0x180015604  jz      short loc_18001565E
0x180015606  sub     ecx, 1
0x180015609  jz      short loc_180015619
0x18001560b  cmp     ecx, 1
0x18001560e  jnz     short loc_180015670
0x180015610  mov     ecx, edi; this
0x180015612  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180015617  jmp     short loc_18001566E
0x180015619  test    edi, edi
0x18001561b  js      short loc_180015655
0x18001561d  mov     rax, [rsp+78h+arg_28]
0x180015625  mov     edi, 8007029Ch
0x18001562a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001562e  mov     rcx, r10; int
0x180015631  mov     [rsp+78h+var_50], rax; __int64
0x180015636  mov     rax, [rsp+78h+arg_20]
0x18001563e  mov     [rsp+78h+var_58], rax; __int64
0x180015643  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180015648  mov     ecx, edi; this
0x18001564a  mov     [rbx+8], edi
0x18001564d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015652  mov     [rbx+0Ch], eax
0x180015655  mov     ecx, edi; this
0x180015657  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001565c  jmp     short loc_18001566E
0x18001565e  mov     ecx, edi; this
0x180015660  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180015665  jmp     short loc_18001566E
0x180015667  mov     ecx, edi; this
0x180015669  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001566e  mov     ebp, eax
0x180015670  mov     eax, [rsp+78h+arg_70]
0x180015677  mov     [rbx+4], eax
0x18001567a  mov     [rbx], r15d
0x18001567d  cmp     dword ptr [r14+8], 1
0x180015682  jnz     short loc_18001568A
0x180015684  or      eax, 8
0x180015687  mov     [rbx+4], eax
0x18001568a  mov     eax, 1
0x18001568f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015697  inc     eax
0x180015699  xor     edi, edi
0x18001569b  mov     [rbx+10h], eax
0x18001569e  mov     rax, [rsp+78h+arg_40]
0x1800156a6  test    rax, rax
0x1800156a9  jz      short loc_1800156B0
0x1800156ab  cmp     [rax], di
0x1800156ae  jnz     short loc_1800156B3
0x1800156b0  mov     rax, rdi
0x1800156b3  mov     [rbx+18h], rax
0x1800156b7  call    cs:__imp_GetCurrentThreadId
0x1800156bd  mov     [rbx+38h], r13
0x1800156c1  xorps   xmm0, xmm0
0x1800156c4  mov     [rbx+20h], eax
0x1800156c7  mov     eax, [rsp+78h+arg_8]
0x1800156ce  mov     [rbx+40h], eax
0x1800156d1  mov     rax, [rsp+78h+arg_20]
0x1800156d9  mov     [rbx+28h], rax
0x1800156dd  mov     rax, [rsp+78h+arg_28]
0x1800156e5  mov     [rbx+88h], rax
0x1800156ec  mov     rax, [rsp+78h+arg_0]
0x1800156f4  mov     [rbx+90h], rax
0x1800156fb  xor     eax, eax
0x1800156fd  mov     [rbx+44h], ebp
0x180015700  mov     [rbx+30h], r12
0x180015704  mov     [rbx+48h], rdi
0x180015708  movups  xmmword ptr [rbx+68h], xmm0
0x18001570c  mov     [rbx+78h], rax
0x180015710  movups  xmmword ptr [rbx+50h], xmm0
0x180015714  mov     [rbx+60h], rax
0x180015718  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001571f  test    rax, rax
0x180015722  jz      short loc_18001572B
0x180015724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015729  jmp     short loc_18001572E
0x18001572b  mov     rax, rdi
0x18001572e  mov     [rbx+80h], rax
0x180015735  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001573c  test    rax, rax
0x18001573f  jz      short loc_180015749
0x180015741  mov     rcx, rbx
0x180015744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015749  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015750  test    rax, rax
0x180015753  jz      short loc_18001576B
0x180015755  mov     rdx, [rsp+78h+arg_60]
0x18001575d  mov     r8d, 400h
0x180015763  mov     rcx, rbx
0x180015766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001576b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015772  test    rax, rax
0x180015775  jz      short loc_18001577F
0x180015777  mov     rcx, rbx
0x18001577a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001577f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015786  test    rax, rax
0x180015789  jz      short loc_180015799
0x18001578b  test    byte ptr [rbx+4], 2
0x18001578f  jnz     short loc_180015799
0x180015791  mov     rcx, rbx
0x180015794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015799  cmp     [rbx+8], edi
0x18001579c  jl      short loc_1800157BA
0x18001579e  cmp     r15d, 3
0x1800157a2  jz      short loc_1800157AA
0x1800157a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800157aa  mov     ecx, 8000FFFFh; this
0x1800157af  mov     [rbx+8], ecx
0x1800157b2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800157b7  mov     [rbx+0Ch], eax
0x1800157ba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800157c1  jnz     short loc_1800157E2
0x1800157c3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800157ca  test    rax, rax
0x1800157cd  jz      short loc_1800157D8
0x1800157cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d4  test    al, al
0x1800157d6  jmp     short loc_1800157E0
0x1800157d8  call    cs:__imp_IsDebuggerPresent
0x1800157de  test    eax, eax
0x1800157e0  jz      short loc_1800157E8
0x1800157e2  test    byte ptr [rbx+4], 2
0x1800157e6  jz      short loc_18001580C
0x1800157e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800157ef  test    rax, rax
0x1800157f2  jz      short loc_180015850
0x1800157f4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800157fb  jnz     short loc_180015850
0x1800157fd  xor     r8d, r8d
0x180015800  xor     edx, edx
0x180015802  mov     rcx, rbx
0x180015805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001580a  jmp     short loc_180015850
0x18001580c  mov     rax, cs:g_pfnResultLoggingCallback
0x180015813  mov     ebp, 800h
0x180015818  test    rax, rax
0x18001581b  jz      short loc_180015834
0x18001581d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015824  jnz     short loc_180015834
0x180015826  mov     r8d, ebp
0x180015829  mov     rdx, rsi
0x18001582c  mov     rcx, rbx
0x18001582f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015834  cmp     [rsi], di
0x180015837  jnz     short loc_180015847
0x180015839  mov     r8, rbx; unsigned __int64
0x18001583c  mov     rdx, rbp; unsigned __int16 *
0x18001583f  mov     rcx, rsi; this
0x180015842  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180015847  mov     rcx, rsi; lpOutputString
0x18001584a  call    cs:__imp_OutputDebugStringW
0x180015850  test    byte ptr [rbx+4], 4
0x180015854  jnz     short loc_18001585F
0x180015856  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001585d  jz      short loc_180015870
0x18001585f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015866  test    rax, rax
0x180015869  jz      short loc_180015870
0x18001586b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015870  mov     rbx, [rsp+78h+arg_10]
0x180015878  add     rsp, 40h
0x18001587c  pop     r15
0x18001587e  pop     r14
0x180015880  pop     r13
0x180015882  pop     r12
0x180015884  pop     rdi
0x180015885  pop     rsi
0x180015886  pop     rbp
0x180015887  retn
```
