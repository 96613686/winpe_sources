# Diagnostics::Telemetry4Diag::RunAnalyzerGroup::StartActivity(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180036a08`
- end: `0x180036b3d`
- name: `?StartActivity@RunAnalyzerGroup@Telemetry4Diag@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180048678`

## callees

- `0x180001704`
- `0x1800080f8`
- `0x18000bba4`
- `0x180015f28`
- `0x180036a08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036a6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036b23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036a6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036b23`

## pseudocode

```c
int __fastcall Diagnostics::Telemetry4Diag::RunAnalyzerGroup::StartActivity(__int64 a1, __int64 *a2)
{
  struct Diagnostics::Telemetry4Diag *Local; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // r9d
  __int64 v11; // rbx
  __int64 v13[5]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14; // [rsp+70h] [rbp+8h] BYREF
  __int64 v15; // [rsp+80h] [rbp+18h] BYREF
  __int64 v16; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  Local = Diagnostics::Telemetry4Diag::Instance();
  v7 = *((_QWORD *)Local + 1);
  if ( *(_DWORD *)v7 > 5u )
  {
    v6 = 0x400000000000LL;
    if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 )
    {
      Local = (struct Diagnostics::Telemetry4Diag *)(*(_QWORD *)(v7 + 24) & 0x400000000000LL);
      if ( Local == *(struct Diagnostics::Telemetry4Diag **)(v7 + 24) )
      {
        v15 = (__int64)"1507.2603.28012.0";
        v16 = *a2;
        CurrentThreadId = GetCurrentThreadId();
        v9 = *(_QWORD *)(a1 + 272);
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
        LODWORD(Local) = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
                           v7,
                           (int)&byte_18017269F,
                           (int)v9 + 8,
                           v10,
                           (__int64)v13,
                           (__int64)&v14,
                           (const wchar_t **)&v16,
                           (const wchar_t **)&v15);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v11 = a1 + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v5) = 1;
      Local = (struct Diagnostics::Telemetry4Diag *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                      v6,
                                                      v5);
      *(_QWORD *)v11 = Local;
      if ( Local )
      {
        *(_QWORD *)(v11 + 16) = *(_QWORD *)Local;
        *(_QWORD *)Local = v11;
        LODWORD(Local) = GetCurrentThreadId();
        *(_DWORD *)(v11 + 24) = (_DWORD)Local;
      }
    }
    else
    {
      *(_QWORD *)v11 = 0;
    }
  }
  return (int)Local;
}

```

## disassembly

```asm
0x180036a08  push    rbx
0x180036a0a  push    rsi
0x180036a0b  push    rdi
0x180036a0c  sub     rsp, 50h
0x180036a10  mov     rsi, rdx
0x180036a13  mov     rbx, rcx
0x180036a16  call    ?zInternalStart@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180036a1b  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036a20  mov     rdi, [rax+8]
0x180036a24  cmp     dword ptr [rdi], 5
0x180036a27  jbe     loc_180036AF0
0x180036a2d  mov     rcx, 400000000000h
0x180036a37  test    [rdi+10h], rcx
0x180036a3b  jz      loc_180036AF0
0x180036a41  mov     rax, [rdi+18h]
0x180036a45  and     rax, rcx
0x180036a48  cmp     rax, [rdi+18h]
0x180036a4c  jnz     loc_180036AF0
0x180036a52  lea     rax, a15072603280120; "1507.2603.28012.0"
0x180036a59  mov     [rsp+68h+arg_10], rax
0x180036a61  mov     rax, [rsi]
0x180036a64  mov     [rsp+68h+arg_18], rax
0x180036a6c  call    cs:__imp_GetCurrentThreadId
0x180036a72  mov     r8, [rbx+110h]
0x180036a79  mov     dword ptr [rsp+68h+arg_0], eax
0x180036a7d  mov     [rsp+68h+var_28], 1000000h
0x180036a86  cmp     byte ptr [r8+4], 0
0x180036a8b  jz      short loc_180036AAC
0x180036a8d  lea     r9, [r8+18h]
0x180036a91  cmp     dword ptr [r9], 0
0x180036a95  jnz     short loc_180036AAF
0x180036a97  cmp     dword ptr [r9+4], 0
0x180036a9c  jnz     short loc_180036AAF
0x180036a9e  cmp     dword ptr [r9+8], 0
0x180036aa3  jnz     short loc_180036AAF
0x180036aa5  cmp     dword ptr [r9+0Ch], 0
0x180036aaa  jnz     short loc_180036AAF
0x180036aac  xor     r9d, r9d
0x180036aaf  lea     rax, [rsp+68h+arg_10]
0x180036ab7  add     r8, 8
0x180036abb  mov     [rsp+68h+var_30], rax; __int64
0x180036ac0  lea     rdx, byte_18017269F; int
0x180036ac7  lea     rax, [rsp+68h+arg_18]
0x180036acf  mov     rcx, rdi; int
0x180036ad2  mov     [rsp+68h+var_38], rax; __int64
0x180036ad7  lea     rax, [rsp+68h+arg_0]
0x180036adc  mov     [rsp+68h+var_40], rax; __int64
0x180036ae1  lea     rax, [rsp+68h+var_28]
0x180036ae6  mov     [rsp+68h+var_48], rax; __int64
0x180036aeb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x180036af0  cmp     dword ptr [rbx+138h], 0
0x180036af7  jnz     short loc_180036B35
0x180036af9  add     rbx, 120h
0x180036b00  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180036b08  jz      short loc_180036B2E
0x180036b0a  mov     dl, 1
0x180036b0c  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180036b11  mov     [rbx], rax
0x180036b14  test    rax, rax
0x180036b17  jz      short loc_180036B35
0x180036b19  mov     rcx, [rax]
0x180036b1c  mov     [rbx+10h], rcx
0x180036b20  mov     [rax], rbx
0x180036b23  call    cs:__imp_GetCurrentThreadId
0x180036b29  mov     [rbx+18h], eax
0x180036b2c  jmp     short loc_180036B35
0x180036b2e  mov     qword ptr [rbx], 0
0x180036b35  add     rsp, 50h
0x180036b39  pop     rdi
0x180036b3a  pop     rsi
0x180036b3b  pop     rbx
0x180036b3c  retn
```
