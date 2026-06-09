# Diagnostics::Telemetry4Diag::RunCliAnalyze::StartActivity(wchar_t const *)

- ea: `0x180015fb0`
- end: `0x1800160f0`
- name: `?StartActivity@RunCliAnalyze@Telemetry4Diag@Diagnostics@@QEAAXPEB_W@Z`
- size: `320`
- prototype: `void __fastcall(Diagnostics::Telemetry4Diag::RunCliAnalyze *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f290`

## callees

- `0x180001704`
- `0x1800080f8`
- `0x18000bba4`
- `0x180015f28`
- `0x180015fb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001601f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800160d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001601f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800160d6`

## pseudocode

```c
void __fastcall Diagnostics::Telemetry4Diag::RunCliAnalyze::StartActivity(
        Diagnostics::Telemetry4Diag::RunCliAnalyze *this,
        const wchar_t *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdi
  const wchar_t *v7; // rax
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // r9d
  char *v11; // rbx
  _QWORD *Local; // rax
  __int64 v13[5]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14; // [rsp+70h] [rbp+8h] BYREF
  __int64 v15; // [rsp+80h] [rbp+18h] BYREF
  __int64 v16; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = *((_QWORD *)Diagnostics::Telemetry4Diag::Instance() + 1);
  if ( *(_DWORD *)v6 > 5u )
  {
    v5 = 0x400000000000LL;
    if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v15 = (__int64)"1507.2603.28012.0";
      v7 = &psz;
      if ( a2 )
        v7 = a2;
      v16 = (__int64)v7;
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 34);
      LODWORD(v14) = CurrentThreadId;
      v13[0] = 0x1000000;
      if ( !*(_BYTE *)(v9 + 4)
        || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
        && !*(_DWORD *)(v9 + 28)
        && !*(_DWORD *)(v9 + 32)
        && !*(_DWORD *)(v9 + 36) )
      {
        v10 = 0;
      }
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        v6,
        (int)&word_180171CA2,
        v9 + 8,
        v10,
        (__int64)v13,
        (__int64)&v14,
        (const wchar_t **)&v16,
        (const wchar_t **)&v15);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v11 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v4) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v5,
                          v4);
      *(_QWORD *)v11 = Local;
      if ( Local )
      {
        *((_QWORD *)v11 + 2) = *Local;
        *Local = v11;
        *((_DWORD *)v11 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v11 = 0;
    }
  }
}

```

## disassembly

```asm
0x180015fb0  push    rbx
0x180015fb2  push    rsi
0x180015fb3  push    rdi
0x180015fb4  sub     rsp, 50h
0x180015fb8  mov     rsi, rdx
0x180015fbb  mov     rbx, rcx
0x180015fbe  call    ?zInternalStart@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180015fc3  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180015fc8  mov     rdi, [rax+8]
0x180015fcc  cmp     dword ptr [rdi], 5
0x180015fcf  jbe     loc_1800160A3
0x180015fd5  mov     rcx, 400000000000h
0x180015fdf  test    [rdi+10h], rcx
0x180015fe3  jz      loc_1800160A3
0x180015fe9  mov     rax, [rdi+18h]
0x180015fed  and     rax, rcx
0x180015ff0  cmp     rax, [rdi+18h]
0x180015ff4  jnz     loc_1800160A3
0x180015ffa  lea     rax, a15072603280120; "1507.2603.28012.0"
0x180016001  test    rsi, rsi
0x180016004  mov     [rsp+68h+arg_10], rax
0x18001600c  lea     rax, psz
0x180016013  cmovnz  rax, rsi
0x180016017  mov     [rsp+68h+arg_18], rax
0x18001601f  call    cs:__imp_GetCurrentThreadId
0x180016025  mov     r8, [rbx+110h]
0x18001602c  mov     dword ptr [rsp+68h+arg_0], eax
0x180016030  mov     [rsp+68h+var_28], 1000000h
0x180016039  cmp     byte ptr [r8+4], 0
0x18001603e  jz      short loc_18001605F
0x180016040  lea     r9, [r8+18h]
0x180016044  cmp     dword ptr [r9], 0
0x180016048  jnz     short loc_180016062
0x18001604a  cmp     dword ptr [r9+4], 0
0x18001604f  jnz     short loc_180016062
0x180016051  cmp     dword ptr [r9+8], 0
0x180016056  jnz     short loc_180016062
0x180016058  cmp     dword ptr [r9+0Ch], 0
0x18001605d  jnz     short loc_180016062
0x18001605f  xor     r9d, r9d
0x180016062  lea     rax, [rsp+68h+arg_10]
0x18001606a  add     r8, 8
0x18001606e  mov     [rsp+68h+var_30], rax; __int64
0x180016073  lea     rdx, word_180171CA2; int
0x18001607a  lea     rax, [rsp+68h+arg_18]
0x180016082  mov     rcx, rdi; int
0x180016085  mov     [rsp+68h+var_38], rax; __int64
0x18001608a  lea     rax, [rsp+68h+arg_0]
0x18001608f  mov     [rsp+68h+var_40], rax; __int64
0x180016094  lea     rax, [rsp+68h+var_28]
0x180016099  mov     [rsp+68h+var_48], rax; __int64
0x18001609e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x1800160a3  cmp     dword ptr [rbx+138h], 0
0x1800160aa  jnz     short loc_1800160E8
0x1800160ac  add     rbx, 120h
0x1800160b3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800160bb  jz      short loc_1800160E1
0x1800160bd  mov     dl, 1
0x1800160bf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800160c4  mov     [rbx], rax
0x1800160c7  test    rax, rax
0x1800160ca  jz      short loc_1800160E8
0x1800160cc  mov     rcx, [rax]
0x1800160cf  mov     [rbx+10h], rcx
0x1800160d3  mov     [rax], rbx
0x1800160d6  call    cs:__imp_GetCurrentThreadId
0x1800160dc  mov     [rbx+18h], eax
0x1800160df  jmp     short loc_1800160E8
0x1800160e1  mov     qword ptr [rbx], 0
0x1800160e8  add     rsp, 50h
0x1800160ec  pop     rdi
0x1800160ed  pop     rsi
0x1800160ee  pop     rbx
0x1800160ef  retn
```
