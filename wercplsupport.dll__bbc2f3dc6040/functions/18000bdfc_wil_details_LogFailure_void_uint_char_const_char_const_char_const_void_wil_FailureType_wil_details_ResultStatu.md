# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000bdfc`
- end: `0x18000c0f4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008df4`

## callees

- `0x1800026e0`
- `0x18000883c`
- `0x18000b2ac`
- `0x18000ba88`
- `0x18000bdfc`
- `0x18000caec`
- `0x18000cc1c`
- `0x18000cc38`
- `0x18000f200`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c0b0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c0b0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c03e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c03e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bf1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bf1f`

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
  wil::details::in1diag4 *v25; // rcx
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
      wil::details::in1diag4::_FailFastImmediate_Unexpected(v25);
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
0x18000bdfc  mov     [rsp+arg_10], rbx
0x18000be01  mov     [rsp+arg_8], edx
0x18000be05  mov     [rsp+arg_0], rcx
0x18000be0a  push    rbp
0x18000be0b  push    rsi
0x18000be0c  push    rdi
0x18000be0d  push    r12
0x18000be0f  push    r13
0x18000be11  push    r14
0x18000be13  push    r15
0x18000be15  sub     rsp, 40h
0x18000be19  mov     r14, [rsp+78h+arg_38]
0x18000be21  xor     eax, eax
0x18000be23  mov     rbx, [rsp+78h+arg_78]
0x18000be2b  xor     ebp, ebp
0x18000be2d  mov     r15d, [rsp+78h+arg_30]
0x18000be35  mov     r10, rcx
0x18000be38  mov     rsi, [rsp+78h+lpOutputString]
0x18000be40  mov     r12, r9
0x18000be43  mov     r13, r8
0x18000be46  mov     ecx, r15d
0x18000be49  mov     [rsi], ax
0x18000be4c  mov     rax, [rsp+78h+arg_60]
0x18000be54  mov     byte ptr [rax], 0
0x18000be57  mov     edi, [r14]
0x18000be5a  mov     [rbx+8], edi
0x18000be5d  mov     eax, [r14+4]
0x18000be61  mov     [rbx+0Ch], eax
0x18000be64  test    r15d, r15d
0x18000be67  jz      short loc_18000BECF
0x18000be69  sub     ecx, 1
0x18000be6c  jz      short loc_18000BEC6
0x18000be6e  sub     ecx, 1
0x18000be71  jz      short loc_18000BE81
0x18000be73  cmp     ecx, 1
0x18000be76  jnz     short loc_18000BED8
0x18000be78  mov     ecx, edi; this
0x18000be7a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000be7f  jmp     short loc_18000BED6
0x18000be81  test    edi, edi
0x18000be83  js      short loc_18000BEBD
0x18000be85  mov     rax, [rsp+78h+arg_28]
0x18000be8d  mov     edi, 8007029Ch
0x18000be92  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000be96  mov     rcx, r10; int
0x18000be99  mov     [rsp+78h+var_50], rax; __int64
0x18000be9e  mov     rax, [rsp+78h+arg_20]
0x18000bea6  mov     [rsp+78h+var_58], rax; __int64
0x18000beab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000beb0  mov     ecx, edi; this
0x18000beb2  mov     [rbx+8], edi
0x18000beb5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000beba  mov     [rbx+0Ch], eax
0x18000bebd  mov     ecx, edi; this
0x18000bebf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000bec4  jmp     short loc_18000BED6
0x18000bec6  mov     ecx, edi; this
0x18000bec8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000becd  jmp     short loc_18000BED6
0x18000becf  mov     ecx, edi; this
0x18000bed1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bed6  mov     ebp, eax
0x18000bed8  mov     eax, [rsp+78h+arg_70]
0x18000bedf  mov     [rbx+4], eax
0x18000bee2  mov     [rbx], r15d
0x18000bee5  cmp     dword ptr [r14+8], 1
0x18000beea  jnz     short loc_18000BEF2
0x18000beec  or      eax, 8
0x18000beef  mov     [rbx+4], eax
0x18000bef2  mov     eax, 1
0x18000bef7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000beff  inc     eax
0x18000bf01  xor     edi, edi
0x18000bf03  mov     [rbx+10h], eax
0x18000bf06  mov     rax, [rsp+78h+arg_40]
0x18000bf0e  test    rax, rax
0x18000bf11  jz      short loc_18000BF18
0x18000bf13  cmp     [rax], di
0x18000bf16  jnz     short loc_18000BF1B
0x18000bf18  mov     rax, rdi
0x18000bf1b  mov     [rbx+18h], rax
0x18000bf1f  call    cs:__imp_GetCurrentThreadId
0x18000bf25  mov     [rbx+38h], r13
0x18000bf29  xorps   xmm0, xmm0
0x18000bf2c  mov     [rbx+20h], eax
0x18000bf2f  mov     eax, [rsp+78h+arg_8]
0x18000bf36  mov     [rbx+40h], eax
0x18000bf39  mov     rax, [rsp+78h+arg_20]
0x18000bf41  mov     [rbx+28h], rax
0x18000bf45  mov     rax, [rsp+78h+arg_28]
0x18000bf4d  mov     [rbx+88h], rax
0x18000bf54  mov     rax, [rsp+78h+arg_0]
0x18000bf5c  mov     [rbx+90h], rax
0x18000bf63  xor     eax, eax
0x18000bf65  mov     [rbx+44h], ebp
0x18000bf68  mov     [rbx+30h], r12
0x18000bf6c  mov     [rbx+48h], rdi
0x18000bf70  movups  xmmword ptr [rbx+68h], xmm0
0x18000bf74  mov     [rbx+78h], rax
0x18000bf78  movups  xmmword ptr [rbx+50h], xmm0
0x18000bf7c  mov     [rbx+60h], rax
0x18000bf80  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bf87  test    rax, rax
0x18000bf8a  jz      short loc_18000BF93
0x18000bf8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf91  jmp     short loc_18000BF96
0x18000bf93  mov     rax, rdi
0x18000bf96  mov     [rbx+80h], rax
0x18000bf9d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bfa4  test    rax, rax
0x18000bfa7  jz      short loc_18000BFB1
0x18000bfa9  mov     rcx, rbx
0x18000bfac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bfb8  test    rax, rax
0x18000bfbb  jz      short loc_18000BFD3
0x18000bfbd  mov     rdx, [rsp+78h+arg_60]
0x18000bfc5  mov     r8d, 400h
0x18000bfcb  mov     rcx, rbx
0x18000bfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfd3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bfda  test    rax, rax
0x18000bfdd  jz      short loc_18000BFE7
0x18000bfdf  mov     rcx, rbx
0x18000bfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bfee  test    rax, rax
0x18000bff1  jz      short loc_18000C001
0x18000bff3  test    byte ptr [rbx+4], 2
0x18000bff7  jnz     short loc_18000C001
0x18000bff9  mov     rcx, rbx
0x18000bffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c001  cmp     [rbx+8], edi
0x18000c004  jl      short loc_18000C020
0x18000c006  cmp     r15d, 3
0x18000c00a  jnz     loc_18000C0EE
0x18000c010  mov     ecx, 8000FFFFh; this
0x18000c015  mov     [rbx+8], ecx
0x18000c018  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c01d  mov     [rbx+0Ch], eax
0x18000c020  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000c027  jnz     short loc_18000C048
0x18000c029  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c030  test    rax, rax
0x18000c033  jz      short loc_18000C03E
0x18000c035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c03a  test    al, al
0x18000c03c  jmp     short loc_18000C046
0x18000c03e  call    cs:__imp_IsDebuggerPresent
0x18000c044  test    eax, eax
0x18000c046  jz      short loc_18000C04E
0x18000c048  test    byte ptr [rbx+4], 2
0x18000c04c  jz      short loc_18000C072
0x18000c04e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c055  test    rax, rax
0x18000c058  jz      short loc_18000C0B6
0x18000c05a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c061  jnz     short loc_18000C0B6
0x18000c063  xor     r8d, r8d
0x18000c066  xor     edx, edx
0x18000c068  mov     rcx, rbx
0x18000c06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c070  jmp     short loc_18000C0B6
0x18000c072  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c079  mov     ebp, 800h
0x18000c07e  test    rax, rax
0x18000c081  jz      short loc_18000C09A
0x18000c083  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c08a  jnz     short loc_18000C09A
0x18000c08c  mov     r8d, ebp
0x18000c08f  mov     rdx, rsi
0x18000c092  mov     rcx, rbx
0x18000c095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c09a  cmp     [rsi], di
0x18000c09d  jnz     short loc_18000C0AD
0x18000c09f  mov     r8, rbx; unsigned __int64
0x18000c0a2  mov     rdx, rbp; unsigned __int16 *
0x18000c0a5  mov     rcx, rsi; this
0x18000c0a8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c0ad  mov     rcx, rsi; lpOutputString
0x18000c0b0  call    cs:__imp_OutputDebugStringW
0x18000c0b6  test    byte ptr [rbx+4], 4
0x18000c0ba  jnz     short loc_18000C0C5
0x18000c0bc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000c0c3  jz      short loc_18000C0D6
0x18000c0c5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c0cc  test    rax, rax
0x18000c0cf  jz      short loc_18000C0D6
0x18000c0d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0d6  mov     rbx, [rsp+78h+arg_10]
0x18000c0de  add     rsp, 40h
0x18000c0e2  pop     r15
0x18000c0e4  pop     r14
0x18000c0e6  pop     r13
0x18000c0e8  pop     r12
0x18000c0ea  pop     rdi
0x18000c0eb  pop     rsi
0x18000c0ec  pop     rbp
0x18000c0ed  retn
0x18000c0ee  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
```
