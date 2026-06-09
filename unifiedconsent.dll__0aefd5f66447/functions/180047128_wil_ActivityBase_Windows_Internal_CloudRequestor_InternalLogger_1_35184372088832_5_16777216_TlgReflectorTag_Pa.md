# wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180047128`
- end: `0x180047251`
- name: `?Stop@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `297`
- prototype: ``
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0x180041410`
- `0x180043000`
- `0x1800446f0`
- `0x180049ec0`
- `0x18004b950`
- `0x18004f160`
- `0x180052980`
- `0x180055168`
- `0x180059840`
- `0x180061d10`
- `0x180075b7b`
- `0x1800767de`

## callees

- `0x180001a6c`
- `0x180003384`
- `0x18000e140`
- `0x18004453c`
- `0x18004460c`
- `0x180045c98`
- `0x180047128`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047174`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800471d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800471d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  struct Windows::Internal::CloudRequestor::InternalLogger *v7; // rax
  __int64 v8; // rcx
  _DWORD *v9; // rdi
  int v10; // r9d
  const struct wil::FailureInfo *v11; // rdx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-E8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v15[200]; // [rsp+60h] [rbp-C8h] BYREF

  wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = a1[34];
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v15, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v15, v11);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    v7 = Windows::Internal::CloudRequestor::InternalLogger::Instance();
    v8 = (__int64)v7 + 16;
    if ( !v7 )
      v8 = 8;
    v9 = *(_DWORD **)v8;
    if ( **(_DWORD **)v8 > 5u
      && (*((_QWORD *)v9 + 2) & 0x200000000000LL) != 0
      && (*((_QWORD *)v9 + 3) & 0x200000000000LL) == *((_QWORD *)v9 + 3) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = a2;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)byte_18008D2C1,
        a1[34] + 8,
        v10,
        (__int64)&v14,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180047128  push    rbx
0x18004712a  push    rbp
0x18004712b  push    rsi
0x18004712c  push    rdi
0x18004712d  sub     rsp, 108h
0x180047134  mov     esi, edx
0x180047136  mov     rbx, rcx
0x180047139  lea     rdx, [rsp+128h+SRWLock]
0x18004713e  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180047143  mov     rax, [rbx+110h]
0x18004714a  mov     edi, [rax+0F8h]
0x180047150  cmp     edi, 1
0x180047153  jl      loc_180047234
0x180047159  cmp     dword ptr [rax+48h], 0
0x18004715d  jl      short loc_180047162
0x18004715f  mov     [rax+48h], esi
0x180047162  dec     edi
0x180047164  mov     [rax+0F8h], edi
0x18004716a  mov     rcx, [rsp+128h+SRWLock]; SRWLock
0x18004716f  test    rcx, rcx
0x180047172  jz      short loc_18004717A
0x180047174  call    cs:__imp_ReleaseSRWLockExclusive
0x18004717a  test    edi, edi
0x18004717c  jnz     short loc_180047192
0x18004717e  mov     rax, [rbx]
0x180047181  mov     rcx, rbx
0x180047184  mov     rax, [rax+8]
0x180047188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004718d  jmp     loc_180047221
0x180047192  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180047197  lea     rcx, [rax+10h]
0x18004719b  mov     ebp, 8
0x1800471a0  test    rax, rax
0x1800471a3  cmovz   rcx, rbp
0x1800471a7  mov     rdi, [rcx]
0x1800471aa  mov     eax, [rdi]
0x1800471ac  cmp     eax, 5
0x1800471af  jbe     short loc_180047221
0x1800471b1  mov     rcx, [rdi+18h]
0x1800471b5  mov     rax, [rdi+10h]
0x1800471b9  mov     rdx, 200000000000h
0x1800471c3  test    rdx, rax
0x1800471c6  jz      short loc_180047221
0x1800471c8  mov     rax, rcx
0x1800471cb  and     rax, rdx
0x1800471ce  cmp     rax, rcx
0x1800471d1  jnz     short loc_180047221
0x1800471d3  call    cs:__imp_GetCurrentThreadId
0x1800471d9  mov     [rsp+128h+var_E8], eax
0x1800471dd  mov     dword ptr [rsp+128h+SRWLock], esi
0x1800471e1  mov     [rsp+128h+var_D8], 1000000h
0x1800471ea  mov     r8, [rbx+110h]
0x1800471f1  add     r8, rbp
0x1800471f4  lea     rax, [rsp+128h+var_E8]
0x1800471f9  mov     [rsp+128h+var_F8], rax
0x1800471fe  lea     rax, [rsp+128h+SRWLock]
0x180047203  mov     [rsp+128h+var_100], rax
0x180047208  lea     rax, [rsp+128h+var_D8]
0x18004720d  mov     [rsp+128h+var_108], rax
0x180047212  lea     rdx, byte_18008D2C1
0x180047219  mov     rcx, rdi
0x18004721c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180047221  mov     rcx, rbx
0x180047224  add     rsp, 108h
0x18004722b  pop     rdi
0x18004722c  pop     rsi
0x18004722d  pop     rbp
0x18004722e  pop     rbx
0x18004722f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180047234  xor     edx, edx; Val
0x180047236  mov     r8d, 98h; Size
0x18004723c  lea     rcx, [rsp+128h+var_C8]; void *
0x180047241  call    memset_0
0x180047246  lea     rcx, [rsp+128h+var_C8]; this
0x18004724b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
