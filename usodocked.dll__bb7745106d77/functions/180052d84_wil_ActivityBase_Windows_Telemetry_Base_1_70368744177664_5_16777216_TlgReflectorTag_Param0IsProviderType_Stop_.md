# wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180052d84`
- end: `0x180052eab`
- name: `?Stop@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180052ec0`

## callees

- `0x1800020d8`
- `0x18000856c`
- `0x180019bc0`
- `0x180041ba0`
- `0x180041c1c`
- `0x180041cd8`
- `0x180052d84`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052dd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052e23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052e23`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  __int64 v5; // rdi
  int v6; // r9d
  const struct wil::FailureInfo *v7; // rdx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v11[168]; // [rsp+60h] [rbp-A8h] BYREF

  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = a1[34];
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v7);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    v5 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (unsigned int)byte_180081E91,
        a1[34] + 8,
        v6,
        (__int64)&v10,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180052d84  mov     [rsp+arg_8], rbx
0x180052d89  push    rdi
0x180052d8a  sub     rsp, 100h
0x180052d91  mov     rbx, rcx
0x180052d94  lea     rdx, [rsp+108h+SRWLock]
0x180052d99  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180052d9e  mov     rax, [rbx+110h]
0x180052da5  mov     edi, [rax+0F8h]
0x180052dab  cmp     edi, 1
0x180052dae  jl      loc_180052E8E
0x180052db4  cmp     dword ptr [rax+48h], 0
0x180052db8  jl      short loc_180052DC1
0x180052dba  mov     dword ptr [rax+48h], 0
0x180052dc1  dec     edi
0x180052dc3  mov     [rax+0F8h], edi
0x180052dc9  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180052dce  test    rcx, rcx
0x180052dd1  jz      short loc_180052DD9
0x180052dd3  call    cs:__imp_ReleaseSRWLockExclusive
0x180052dd9  test    edi, edi
0x180052ddb  jnz     short loc_180052DF1
0x180052ddd  mov     rax, [rbx]
0x180052de0  mov     rcx, rbx
0x180052de3  mov     rax, [rax+8]
0x180052de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dec  jmp     loc_180052E76
0x180052df1  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180052df6  mov     rdi, [rax+8]
0x180052dfa  mov     eax, [rdi]
0x180052dfc  cmp     eax, 5
0x180052dff  jbe     short loc_180052E76
0x180052e01  mov     rcx, [rdi+18h]
0x180052e05  mov     rax, [rdi+10h]
0x180052e09  mov     rdx, 400000000000h
0x180052e13  test    rdx, rax
0x180052e16  jz      short loc_180052E76
0x180052e18  mov     rax, rcx
0x180052e1b  and     rax, rdx
0x180052e1e  cmp     rax, rcx
0x180052e21  jnz     short loc_180052E76
0x180052e23  call    cs:__imp_GetCurrentThreadId
0x180052e29  mov     [rsp+108h+var_C8], eax
0x180052e2d  mov     dword ptr [rsp+108h+SRWLock], 0
0x180052e35  mov     [rsp+108h+var_B8], 1000000h
0x180052e3e  mov     r8, [rbx+110h]
0x180052e45  add     r8, 8
0x180052e49  lea     rax, [rsp+108h+var_C8]
0x180052e4e  mov     [rsp+108h+var_D8], rax
0x180052e53  lea     rax, [rsp+108h+SRWLock]
0x180052e58  mov     [rsp+108h+var_E0], rax
0x180052e5d  lea     rax, [rsp+108h+var_B8]
0x180052e62  mov     [rsp+108h+var_E8], rax
0x180052e67  lea     rdx, byte_180081E91
0x180052e6e  mov     rcx, rdi
0x180052e71  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180052e76  mov     rcx, rbx
0x180052e79  mov     rbx, [rsp+108h+arg_8]
0x180052e81  add     rsp, 100h
0x180052e88  pop     rdi
0x180052e89  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180052e8e  xor     edx, edx; Val
0x180052e90  mov     r8d, 98h; Size
0x180052e96  lea     rcx, [rsp+108h+var_A8]; void *
0x180052e9b  call    memset_0
0x180052ea0  lea     rcx, [rsp+108h+var_A8]; this
0x180052ea5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
