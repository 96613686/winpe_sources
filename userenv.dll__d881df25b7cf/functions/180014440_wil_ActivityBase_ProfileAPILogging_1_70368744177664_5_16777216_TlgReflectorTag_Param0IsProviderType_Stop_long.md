# wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180014440`
- end: `0x180014526`
- name: `?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009f74`
- `0x180014c70`
- `0x180014e30`
- `0x18001aa00`

## callees

- `0x180001558`
- `0x180001d68`
- `0x18000d7b8`
- `0x18000d8ec`
- `0x18000ddcc`
- `0x180013d08`
- `0x1800140f8`
- `0x180014440`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800144bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800144bb`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // r9d
  int v12; // [rsp+50h] [rbp+8h] BYREF
  DWORD v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v12);
  v2 = wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileAPILogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v6 = ProfileAPILogging::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v13 = CurrentThreadId;
      v12 = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&unk_1800220D8,
        v9 + 8,
        v10,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x180014440  mov     rax, rsp
0x180014443  mov     [rax+20h], rbx
0x180014447  mov     [rax+10h], edx
0x18001444a  push    rdi
0x18001444b  sub     rsp, 40h
0x18001444f  lea     rdx, [rax+8]
0x180014453  mov     dword ptr [rax+10h], 0
0x18001445a  mov     rdi, rcx
0x18001445d  call    ?LockExclusive@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180014462  mov     rcx, [rdi+110h]
0x180014469  lea     r8, [rsp+48h+arg_8]
0x18001446e  xor     edx, edx
0x180014470  call    ?SetStopResult@?$ActivityData@VProfileAPILogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileAPILogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180014475  lea     rcx, [rsp+48h+arg_0]
0x18001447a  mov     bl, al
0x18001447c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014481  test    bl, bl
0x180014483  jz      short loc_180014496
0x180014485  mov     rax, [rdi]
0x180014488  mov     rcx, rdi
0x18001448b  mov     rax, [rax+8]
0x18001448f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014494  jmp     short loc_180014514
0x180014496  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x18001449b  mov     rbx, rax
0x18001449e  mov     ecx, [rax]
0x1800144a0  cmp     ecx, 5
0x1800144a3  jbe     short loc_180014514
0x1800144a5  mov     rdx, 400000000000h
0x1800144af  mov     rcx, rax
0x1800144b2  call    _tlgKeywordOn
0x1800144b7  test    al, al
0x1800144b9  jz      short loc_180014514
0x1800144bb  call    cs:__imp_GetCurrentThreadId
0x1800144c2  nop     dword ptr [rax+rax+00h]
0x1800144c7  mov     r8, [rdi+110h]
0x1800144ce  lea     rdx, unk_1800220D8
0x1800144d5  mov     [rsp+48h+arg_8], eax
0x1800144d9  add     r8, 8
0x1800144dd  lea     rax, [rsp+48h+arg_8]
0x1800144e2  mov     [rsp+48h+arg_0], 0
0x1800144ea  mov     [rsp+48h+var_18], rax
0x1800144ef  mov     rcx, rbx
0x1800144f2  lea     rax, [rsp+48h+arg_0]
0x1800144f7  mov     [rsp+48h+arg_10], 1000000h
0x180014500  mov     [rsp+48h+var_20], rax
0x180014505  lea     rax, [rsp+48h+arg_10]
0x18001450a  mov     [rsp+48h+var_28], rax
0x18001450f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014514  mov     rcx, rdi
0x180014517  mov     rbx, [rsp+48h+arg_18]
0x18001451c  add     rsp, 40h
0x180014520  pop     rdi
0x180014521  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
