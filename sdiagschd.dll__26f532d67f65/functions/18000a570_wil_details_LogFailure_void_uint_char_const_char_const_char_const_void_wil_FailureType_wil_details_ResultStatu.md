# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18000a570`
- end: `0x18000a878`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008e60`

## callees

- `0x180008878`
- `0x180009b84`
- `0x18000a3a0`
- `0x18000a570`
- `0x18000ada0`
- `0x18000adc0`
- `0x18000add4`
- `0x18000adf4`
- `0x18000c468`
- `0x18000d010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000a7b3`
- `KERNEL32!IsDebuggerPresent` at `0x18000a7b3`
- `KERNEL32!OutputDebugStringW` at `0x18000a82c`
- `KERNEL32!OutputDebugStringW` at `0x18000a82c`
- `KERNEL32!GetCurrentThreadId` at `0x18000a68f`
- `KERNEL32!GetCurrentThreadId` at `0x18000a68f`

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
        unsigned __int64 a15)
{
  unsigned int v17; // edi
  int v18; // esi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  int v22; // edx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  v18 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v17, a2);
        break;
      case 2:
        if ( (v17 & 0x80000000) == 0 )
        {
          v17 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v17, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v17, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v17, a2);
  }
  v18 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  *(_DWORD *)(a15 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 64) = a2;
  *(_DWORD *)(a15 + 68) = v18;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v23);
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v22);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x18000a570  mov     [rsp+arg_10], rbx
0x18000a575  mov     [rsp+arg_8], edx
0x18000a579  mov     [rsp+arg_0], rcx
0x18000a57e  push    rbp
0x18000a57f  push    rsi
0x18000a580  push    rdi
0x18000a581  push    r12
0x18000a583  push    r13
0x18000a585  push    r14
0x18000a587  push    r15
0x18000a589  sub     rsp, 40h
0x18000a58d  mov     r12, r9
0x18000a590  mov     r13, r8
0x18000a593  mov     r10, rcx
0x18000a596  xor     r8d, r8d
0x18000a599  mov     r14, [rsp+78h+lpOutputString]
0x18000a5a1  mov     [r14], r8w
0x18000a5a5  mov     rax, [rsp+78h+arg_60]
0x18000a5ad  mov     [rax], r8b
0x18000a5b0  mov     rbx, [rsp+78h+arg_70]
0x18000a5b8  mov     r15, [rsp+78h+arg_38]
0x18000a5c0  mov     edi, [r15]
0x18000a5c3  mov     [rbx+8], edi
0x18000a5c6  mov     eax, [r15+4]
0x18000a5ca  mov     [rbx+0Ch], eax
0x18000a5cd  mov     esi, r8d
0x18000a5d0  mov     ebp, [rsp+78h+arg_30]
0x18000a5d7  mov     ecx, ebp
0x18000a5d9  test    ebp, ebp
0x18000a5db  jz      short loc_18000A646
0x18000a5dd  sub     ecx, 1
0x18000a5e0  jz      short loc_18000A63D
0x18000a5e2  sub     ecx, 1
0x18000a5e5  jz      short loc_18000A5F5
0x18000a5e7  cmp     ecx, 1
0x18000a5ea  jnz     short loc_18000A64F
0x18000a5ec  mov     ecx, edi; this
0x18000a5ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a5f3  jmp     short loc_18000A64D
0x18000a5f5  test    edi, edi
0x18000a5f7  js      short loc_18000A634
0x18000a5f9  mov     edi, 8007029Ch
0x18000a5fe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a602  mov     rax, [rsp+78h+arg_28]
0x18000a60a  mov     [rsp+78h+var_50], rax; __int64
0x18000a60f  mov     rax, [rsp+78h+arg_20]
0x18000a617  mov     [rsp+78h+var_58], rax; __int64
0x18000a61c  mov     r8, r13; int
0x18000a61f  mov     rcx, r10; int
0x18000a622  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000a627  mov     [rbx+8], edi
0x18000a62a  mov     ecx, edi; this
0x18000a62c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a631  mov     [rbx+0Ch], eax
0x18000a634  mov     ecx, edi; this
0x18000a636  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a63b  jmp     short loc_18000A64D
0x18000a63d  mov     ecx, edi; this
0x18000a63f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a644  jmp     short loc_18000A64D
0x18000a646  mov     ecx, edi; this
0x18000a648  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a64d  mov     esi, eax
0x18000a64f  mov     [rbx], ebp
0x18000a651  xor     edi, edi
0x18000a653  mov     [rbx+4], edi
0x18000a656  cmp     dword ptr [r15+8], 1
0x18000a65b  jnz     short loc_18000A664
0x18000a65d  mov     dword ptr [rbx+4], 8
0x18000a664  mov     eax, 1
0x18000a669  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000a671  inc     eax
0x18000a673  mov     [rbx+10h], eax
0x18000a676  mov     rax, [rsp+78h+arg_40]
0x18000a67e  test    rax, rax
0x18000a681  jz      short loc_18000A688
0x18000a683  cmp     [rax], di
0x18000a686  jnz     short loc_18000A68B
0x18000a688  mov     rax, rdi
0x18000a68b  mov     [rbx+18h], rax
0x18000a68f  call    cs:__imp_GetCurrentThreadId
0x18000a696  nop     dword ptr [rax+rax+00h]
0x18000a69b  mov     [rbx+20h], eax
0x18000a69e  mov     [rbx+38h], r13
0x18000a6a2  mov     eax, [rsp+78h+arg_8]
0x18000a6a9  mov     [rbx+40h], eax
0x18000a6ac  mov     [rbx+44h], esi
0x18000a6af  mov     rax, [rsp+78h+arg_20]
0x18000a6b7  mov     [rbx+28h], rax
0x18000a6bb  mov     [rbx+30h], r12
0x18000a6bf  mov     rax, [rsp+78h+arg_28]
0x18000a6c7  mov     [rbx+88h], rax
0x18000a6ce  mov     rax, [rsp+78h+arg_0]
0x18000a6d6  mov     [rbx+90h], rax
0x18000a6dd  mov     [rbx+48h], rdi
0x18000a6e1  xorps   xmm0, xmm0
0x18000a6e4  xor     eax, eax
0x18000a6e6  movups  xmmword ptr [rbx+68h], xmm0
0x18000a6ea  mov     [rbx+78h], rax
0x18000a6ee  movups  xmmword ptr [rbx+50h], xmm0
0x18000a6f2  mov     [rbx+60h], rax
0x18000a6f6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a6fd  test    rax, rax
0x18000a700  jz      short loc_18000A709
0x18000a702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a707  jmp     short loc_18000A70C
0x18000a709  mov     rax, rdi
0x18000a70c  mov     [rbx+80h], rax
0x18000a713  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a71a  test    rax, rax
0x18000a71d  jz      short loc_18000A727
0x18000a71f  mov     rcx, rbx
0x18000a722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a727  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a72e  test    rax, rax
0x18000a731  jz      short loc_18000A749
0x18000a733  mov     r8d, 400h
0x18000a739  mov     rdx, [rsp+78h+arg_60]
0x18000a741  mov     rcx, rbx
0x18000a744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a749  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a750  test    rax, rax
0x18000a753  jz      short loc_18000A75D
0x18000a755  mov     rcx, rbx
0x18000a758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a75d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a764  test    rax, rax
0x18000a767  jz      short loc_18000A777
0x18000a769  test    byte ptr [rbx+4], 2
0x18000a76d  jnz     short loc_18000A777
0x18000a76f  mov     rcx, rbx
0x18000a772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a777  cmp     [rbx+8], edi
0x18000a77a  jl      short loc_18000A795
0x18000a77c  cmp     ebp, 3
0x18000a77f  jnz     loc_18000A872
0x18000a785  mov     ecx, 8000FFFFh; this
0x18000a78a  mov     [rbx+8], ecx
0x18000a78d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a792  mov     [rbx+0Ch], eax
0x18000a795  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a79c  jnz     short loc_18000A7C3
0x18000a79e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a7a5  test    rax, rax
0x18000a7a8  jz      short loc_18000A7B3
0x18000a7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7af  test    al, al
0x18000a7b1  jmp     short loc_18000A7C1
0x18000a7b3  call    cs:__imp_IsDebuggerPresent
0x18000a7ba  nop     dword ptr [rax+rax+00h]
0x18000a7bf  test    eax, eax
0x18000a7c1  jz      short loc_18000A7C9
0x18000a7c3  test    byte ptr [rbx+4], 2
0x18000a7c7  jz      short loc_18000A7ED
0x18000a7c9  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a7d0  test    rax, rax
0x18000a7d3  jz      short loc_18000A838
0x18000a7d5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a7dc  jnz     short loc_18000A838
0x18000a7de  xor     r8d, r8d
0x18000a7e1  xor     edx, edx
0x18000a7e3  mov     rcx, rbx
0x18000a7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7eb  jmp     short loc_18000A838
0x18000a7ed  mov     esi, 800h
0x18000a7f2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a7f9  test    rax, rax
0x18000a7fc  jz      short loc_18000A815
0x18000a7fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a805  jnz     short loc_18000A815
0x18000a807  mov     r8d, esi
0x18000a80a  mov     rdx, r14
0x18000a80d  mov     rcx, rbx
0x18000a810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a815  cmp     [r14], di
0x18000a819  jnz     short loc_18000A829
0x18000a81b  mov     r8, rbx; unsigned __int64
0x18000a81e  mov     rdx, rsi; unsigned __int16 *
0x18000a821  mov     rcx, r14; this
0x18000a824  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a829  mov     rcx, r14; lpOutputString
0x18000a82c  call    cs:__imp_OutputDebugStringW
0x18000a833  nop     dword ptr [rax+rax+00h]
0x18000a838  test    byte ptr [rbx+4], 4
0x18000a83c  jnz     short loc_18000A847
0x18000a83e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a845  jz      short loc_18000A859
0x18000a847  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a84e  test    rax, rax
0x18000a851  jz      short loc_18000A859
0x18000a853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a858  nop
0x18000a859  mov     rbx, [rsp+78h+arg_10]
0x18000a861  add     rsp, 40h
0x18000a865  pop     r15
0x18000a867  pop     r14
0x18000a869  pop     r13
0x18000a86b  pop     r12
0x18000a86d  pop     rdi
0x18000a86e  pop     rsi
0x18000a86f  pop     rbp
0x18000a870  retn
0x18000a872  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
