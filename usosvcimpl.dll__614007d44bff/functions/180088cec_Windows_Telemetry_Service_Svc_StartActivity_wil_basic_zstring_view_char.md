# Windows::Telemetry::Service::Svc::StartActivity(wil::basic_zstring_view<char>)

- ea: `0x180088cec`
- end: `0x180088e46`
- name: `?StartActivity@Svc@Service@Telemetry@Windows@@QEAAXV?$basic_zstring_view@D@wil@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180088e4c`

## callees

- `0x180001e50`
- `0x1800857a8`
- `0x180088cec`
- `0x18008c454`
- `0x18008d0c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088d72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088d72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088da9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088da9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180088d53`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180088d53`

## pseudocode

```c
void __fastcall Windows::Telemetry::Service::Svc::StartActivity(__int64 a1, __int64 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  RTL_SRWLOCK *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // r9d
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-28h] BYREF
  __int64 v13; // [rsp+48h] [rbp-20h] BYREF
  __int64 v14; // [rsp+50h] [rbp-18h] BYREF

  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *((_QWORD *)Windows::Telemetry::ServiceBase::Instance() + 1);
  if ( *(_DWORD *)v5 > 5u
    && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  }
  else
  {
    *(_OWORD *)(v4 + 8) = 0;
  }
  v6 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  v8 = *((_QWORD *)Windows::Telemetry::ServiceBase::Instance() + 1);
  if ( *(_DWORD *)v8 > 5u
    && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
  {
    v13 = *a2;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v14 = 0x1000000;
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = v10 + 24, !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v8,
      (int)byte_180130013,
      v10 + 8,
      v11,
      (__int64)&v14,
      (__int64)&SRWLock,
      (const wchar_t **)&v13);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v7);
}

```

## disassembly

```asm
0x180088cec  mov     rax, rsp
0x180088cef  mov     [rax+10h], rbx
0x180088cf3  mov     [rax+18h], rsi
0x180088cf7  mov     [rax+20h], rdi
0x180088cfb  push    r14
0x180088cfd  sub     rsp, 60h
0x180088d01  mov     rsi, rdx
0x180088d04  mov     qword ptr [rax-28h], 0
0x180088d0c  lea     rdx, [rax-28h]
0x180088d10  mov     rdi, rcx
0x180088d13  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180088d18  mov     rbx, [rdi+110h]
0x180088d1f  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x180088d24  mov     r14, 400000000000h
0x180088d2e  mov     rcx, [rax+8]
0x180088d32  cmp     dword ptr [rcx], 5
0x180088d35  jbe     short loc_180088D5B
0x180088d37  test    [rcx+10h], r14
0x180088d3b  jz      short loc_180088D5B
0x180088d3d  mov     rax, [rcx+18h]
0x180088d41  and     rax, r14
0x180088d44  cmp     rax, [rcx+18h]
0x180088d48  jnz     short loc_180088D5B
0x180088d4a  lea     rdx, [rbx+8]; ActivityId
0x180088d4e  mov     ecx, 3; ControlCode
0x180088d53  call    cs:__imp_EventActivityIdControl
0x180088d59  jmp     short loc_180088D62
0x180088d5b  xorps   xmm0, xmm0
0x180088d5e  movups  xmmword ptr [rbx+8], xmm0
0x180088d62  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180088d67  mov     dword ptr [rbx], 1
0x180088d6d  test    rcx, rcx
0x180088d70  jz      short loc_180088D78
0x180088d72  call    cs:__imp_ReleaseSRWLockExclusive
0x180088d78  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x180088d7d  mov     rbx, [rax+8]
0x180088d81  cmp     dword ptr [rbx], 5
0x180088d84  jbe     loc_180088E1D
0x180088d8a  test    [rbx+10h], r14
0x180088d8e  jz      loc_180088E1D
0x180088d94  mov     rax, [rbx+18h]
0x180088d98  and     rax, r14
0x180088d9b  cmp     rax, [rbx+18h]
0x180088d9f  jnz     short loc_180088E1D
0x180088da1  mov     rax, [rsi]
0x180088da4  mov     [rsp+68h+var_20], rax
0x180088da9  call    cs:__imp_GetCurrentThreadId
0x180088daf  mov     r8, [rdi+110h]
0x180088db6  mov     dword ptr [rsp+68h+SRWLock], eax
0x180088dba  mov     [rsp+68h+var_18], 1000000h
0x180088dc3  cmp     byte ptr [r8+4], 0
0x180088dc8  jz      short loc_180088DE9
0x180088dca  lea     r9, [r8+18h]
0x180088dce  cmp     dword ptr [r9], 0
0x180088dd2  jnz     short loc_180088DEC
0x180088dd4  cmp     dword ptr [r9+4], 0
0x180088dd9  jnz     short loc_180088DEC
0x180088ddb  cmp     dword ptr [r9+8], 0
0x180088de0  jnz     short loc_180088DEC
0x180088de2  cmp     dword ptr [r9+0Ch], 0
0x180088de7  jnz     short loc_180088DEC
0x180088de9  xor     r9d, r9d
0x180088dec  lea     rax, [rsp+68h+var_20]
0x180088df1  add     r8, 8
0x180088df5  mov     [rsp+68h+var_38], rax; __int64
0x180088dfa  lea     rdx, byte_180130013
0x180088e01  lea     rax, [rsp+68h+SRWLock]
0x180088e06  mov     rcx, rbx; int
0x180088e09  mov     [rsp+68h+var_40], rax; __int64
0x180088e0e  lea     rax, [rsp+68h+var_18]
0x180088e13  mov     [rsp+68h+var_48], rax; __int64
0x180088e18  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180088e1d  lea     rcx, [rdi+120h]; this
0x180088e24  cmp     dword ptr [rcx+18h], 0
0x180088e28  jnz     short loc_180088E2F
0x180088e2a  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180088e2f  lea     r11, [rsp+68h+var_8]
0x180088e34  mov     rbx, [r11+18h]
0x180088e38  mov     rsi, [r11+20h]
0x180088e3c  mov     rdi, [r11+28h]
0x180088e40  mov     rsp, r11
0x180088e43  pop     r14
0x180088e45  retn
```
