# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18000ade0`
- end: `0x18000b0e7`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008860`

## callees

- `0x18000827c`
- `0x18000a354`
- `0x18000ab68`
- `0x18000ade0`
- `0x18000b80c`
- `0x18000b830`
- `0x18000b98c`
- `0x18000b9ac`
- `0x18000da68`
- `0x180030010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000b023`
- `KERNEL32!IsDebuggerPresent` at `0x18000b023`
- `KERNEL32!OutputDebugStringW` at `0x18000b09c`
- `KERNEL32!OutputDebugStringW` at `0x18000b09c`
- `KERNEL32!GetCurrentThreadId` at `0x18000aeff`
- `KERNEL32!GetCurrentThreadId` at `0x18000aeff`

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
  int v17; // esi
  unsigned int v18; // edi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  v17 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v17 = v19;
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
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 32) = CurrentThreadId;
  *(_DWORD *)(a15 + 64) = a2;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_DWORD *)(a15 + 68) = v17;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18000ade0  mov     [rsp+arg_10], rbx
0x18000ade5  mov     [rsp+arg_8], edx
0x18000ade9  mov     [rsp+arg_0], rcx
0x18000adee  push    rbp
0x18000adef  push    rsi
0x18000adf0  push    rdi
0x18000adf1  push    r12
0x18000adf3  push    r13
0x18000adf5  push    r14
0x18000adf7  push    r15
0x18000adf9  sub     rsp, 40h
0x18000adfd  mov     rax, [rsp+78h+arg_60]
0x18000ae05  mov     r13, r8
0x18000ae08  mov     r15, [rsp+78h+arg_38]
0x18000ae10  xor     r8d, r8d
0x18000ae13  mov     rbx, [rsp+78h+arg_70]
0x18000ae1b  mov     r10, rcx
0x18000ae1e  mov     ebp, [rsp+78h+arg_30]
0x18000ae25  mov     r12, r9
0x18000ae28  mov     r14, [rsp+78h+lpOutputString]
0x18000ae30  mov     esi, r8d
0x18000ae33  mov     ecx, ebp
0x18000ae35  mov     [r14], r8w
0x18000ae39  mov     [rax], r8b
0x18000ae3c  mov     edi, [r15]
0x18000ae3f  mov     [rbx+8], edi
0x18000ae42  mov     eax, [r15+4]
0x18000ae46  mov     [rbx+0Ch], eax
0x18000ae49  test    ebp, ebp
0x18000ae4b  jz      short loc_18000AEB6
0x18000ae4d  sub     ecx, 1
0x18000ae50  jz      short loc_18000AEAD
0x18000ae52  sub     ecx, 1
0x18000ae55  jz      short loc_18000AE65
0x18000ae57  cmp     ecx, 1
0x18000ae5a  jnz     short loc_18000AEBF
0x18000ae5c  mov     ecx, edi; this
0x18000ae5e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ae63  jmp     short loc_18000AEBD
0x18000ae65  test    edi, edi
0x18000ae67  js      short loc_18000AEA4
0x18000ae69  mov     rax, [rsp+78h+arg_28]
0x18000ae71  mov     edi, 8007029Ch
0x18000ae76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ae7a  mov     r8, r13; int
0x18000ae7d  mov     [rsp+78h+var_50], rax; __int64
0x18000ae82  mov     rcx, r10; int
0x18000ae85  mov     rax, [rsp+78h+arg_20]
0x18000ae8d  mov     [rsp+78h+var_58], rax; __int64
0x18000ae92  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000ae97  mov     ecx, edi; this
0x18000ae99  mov     [rbx+8], edi
0x18000ae9c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000aea1  mov     [rbx+0Ch], eax
0x18000aea4  mov     ecx, edi; this
0x18000aea6  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000aeab  jmp     short loc_18000AEBD
0x18000aead  mov     ecx, edi; this
0x18000aeaf  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000aeb4  jmp     short loc_18000AEBD
0x18000aeb6  mov     ecx, edi; this
0x18000aeb8  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000aebd  mov     esi, eax
0x18000aebf  xor     edi, edi
0x18000aec1  mov     [rbx], ebp
0x18000aec3  mov     [rbx+4], edi
0x18000aec6  cmp     dword ptr [r15+8], 1
0x18000aecb  jnz     short loc_18000AED4
0x18000aecd  mov     dword ptr [rbx+4], 8
0x18000aed4  mov     eax, 1
0x18000aed9  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000aee1  inc     eax
0x18000aee3  mov     [rbx+10h], eax
0x18000aee6  mov     rax, [rsp+78h+arg_40]
0x18000aeee  test    rax, rax
0x18000aef1  jz      short loc_18000AEF8
0x18000aef3  cmp     [rax], di
0x18000aef6  jnz     short loc_18000AEFB
0x18000aef8  mov     rax, rdi
0x18000aefb  mov     [rbx+18h], rax
0x18000aeff  call    cs:__imp_GetCurrentThreadId
0x18000af06  nop     dword ptr [rax+rax+00h]
0x18000af0b  mov     [rbx+38h], r13
0x18000af0f  xorps   xmm0, xmm0
0x18000af12  mov     [rbx+20h], eax
0x18000af15  mov     eax, [rsp+78h+arg_8]
0x18000af1c  mov     [rbx+40h], eax
0x18000af1f  mov     rax, [rsp+78h+arg_20]
0x18000af27  mov     [rbx+28h], rax
0x18000af2b  mov     rax, [rsp+78h+arg_28]
0x18000af33  mov     [rbx+88h], rax
0x18000af3a  mov     rax, [rsp+78h+arg_0]
0x18000af42  mov     [rbx+90h], rax
0x18000af49  xor     eax, eax
0x18000af4b  mov     [rbx+44h], esi
0x18000af4e  mov     [rbx+30h], r12
0x18000af52  mov     [rbx+48h], rdi
0x18000af56  movups  xmmword ptr [rbx+68h], xmm0
0x18000af5a  mov     [rbx+78h], rax
0x18000af5e  movups  xmmword ptr [rbx+50h], xmm0
0x18000af62  mov     [rbx+60h], rax
0x18000af66  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000af6d  test    rax, rax
0x18000af70  jz      short loc_18000AF79
0x18000af72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af77  jmp     short loc_18000AF7C
0x18000af79  mov     rax, rdi
0x18000af7c  mov     [rbx+80h], rax
0x18000af83  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000af8a  test    rax, rax
0x18000af8d  jz      short loc_18000AF97
0x18000af8f  mov     rcx, rbx
0x18000af92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af97  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000af9e  test    rax, rax
0x18000afa1  jz      short loc_18000AFB9
0x18000afa3  mov     rdx, [rsp+78h+arg_60]
0x18000afab  mov     r8d, 400h
0x18000afb1  mov     rcx, rbx
0x18000afb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000afc0  test    rax, rax
0x18000afc3  jz      short loc_18000AFCD
0x18000afc5  mov     rcx, rbx
0x18000afc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afcd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000afd4  test    rax, rax
0x18000afd7  jz      short loc_18000AFE7
0x18000afd9  test    byte ptr [rbx+4], 2
0x18000afdd  jnz     short loc_18000AFE7
0x18000afdf  mov     rcx, rbx
0x18000afe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afe7  cmp     [rbx+8], edi
0x18000afea  jl      short loc_18000B005
0x18000afec  cmp     ebp, 3
0x18000afef  jnz     loc_18000B0E1
0x18000aff5  mov     ecx, 8000FFFFh; this
0x18000affa  mov     [rbx+8], ecx
0x18000affd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b002  mov     [rbx+0Ch], eax
0x18000b005  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000b00c  jnz     short loc_18000B033
0x18000b00e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b015  test    rax, rax
0x18000b018  jz      short loc_18000B023
0x18000b01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b01f  test    al, al
0x18000b021  jmp     short loc_18000B031
0x18000b023  call    cs:__imp_IsDebuggerPresent
0x18000b02a  nop     dword ptr [rax+rax+00h]
0x18000b02f  test    eax, eax
0x18000b031  jz      short loc_18000B039
0x18000b033  test    byte ptr [rbx+4], 2
0x18000b037  jz      short loc_18000B05D
0x18000b039  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b040  test    rax, rax
0x18000b043  jz      short loc_18000B0A8
0x18000b045  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b04c  jnz     short loc_18000B0A8
0x18000b04e  xor     r8d, r8d
0x18000b051  xor     edx, edx
0x18000b053  mov     rcx, rbx
0x18000b056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b05b  jmp     short loc_18000B0A8
0x18000b05d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b064  mov     esi, 800h
0x18000b069  test    rax, rax
0x18000b06c  jz      short loc_18000B085
0x18000b06e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b075  jnz     short loc_18000B085
0x18000b077  mov     r8d, esi
0x18000b07a  mov     rdx, r14
0x18000b07d  mov     rcx, rbx
0x18000b080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b085  cmp     [r14], di
0x18000b089  jnz     short loc_18000B099
0x18000b08b  mov     r8, rbx; unsigned __int64
0x18000b08e  mov     rdx, rsi; unsigned __int16 *
0x18000b091  mov     rcx, r14; this
0x18000b094  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b099  mov     rcx, r14; lpOutputString
0x18000b09c  call    cs:__imp_OutputDebugStringW
0x18000b0a3  nop     dword ptr [rax+rax+00h]
0x18000b0a8  test    byte ptr [rbx+4], 4
0x18000b0ac  jnz     short loc_18000B0B7
0x18000b0ae  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000b0b5  jz      short loc_18000B0C8
0x18000b0b7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b0be  test    rax, rax
0x18000b0c1  jz      short loc_18000B0C8
0x18000b0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0c8  mov     rbx, [rsp+78h+arg_10]
0x18000b0d0  add     rsp, 40h
0x18000b0d4  pop     r15
0x18000b0d6  pop     r14
0x18000b0d8  pop     r13
0x18000b0da  pop     r12
0x18000b0dc  pop     rdi
0x18000b0dd  pop     rsi
0x18000b0de  pop     rbp
0x18000b0df  retn
0x18000b0e1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
