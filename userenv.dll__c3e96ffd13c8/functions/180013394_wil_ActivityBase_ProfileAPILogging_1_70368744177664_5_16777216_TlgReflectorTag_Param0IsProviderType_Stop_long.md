# wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180013394`
- end: `0x180013474`
- name: `?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000965c`
- `0x180013bc0`
- `0x180013d50`
- `0x180018ff4`

## callees

- `0x180001558`
- `0x180001d58`
- `0x18000cc14`
- `0x18000cd68`
- `0x18000d158`
- `0x180012c48`
- `0x180013058`
- `0x180013394`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001340f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001340f`

## pseudocode

```c
void __fastcall wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  int v6; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v10);
  v2 = wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileAPILogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v4 = ProfileAPILogging::Provider(v3);
    v6 = (int)v4;
    if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(v10) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (int)&unk_180021098,
        v8 + 8,
        v9,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180013394  mov     rax, rsp
0x180013397  mov     [rax+20h], rbx
0x18001339b  mov     [rax+10h], edx
0x18001339e  push    rdi
0x18001339f  sub     rsp, 40h
0x1800133a3  lea     rdx, [rax+8]
0x1800133a7  mov     dword ptr [rax+10h], 0
0x1800133ae  mov     rdi, rcx
0x1800133b1  call    ?LockExclusive@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800133b6  mov     rcx, [rdi+110h]
0x1800133bd  lea     r8, [rsp+48h+arg_8]
0x1800133c2  xor     edx, edx
0x1800133c4  call    ?SetStopResult@?$ActivityData@VProfileAPILogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileAPILogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800133c9  lea     rcx, [rsp+48h+arg_0]
0x1800133ce  mov     bl, al
0x1800133d0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800133d5  test    bl, bl
0x1800133d7  jz      short loc_1800133EA
0x1800133d9  mov     rax, [rdi]
0x1800133dc  mov     rcx, rdi
0x1800133df  mov     rax, [rax+8]
0x1800133e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133e8  jmp     short loc_180013462
0x1800133ea  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x1800133ef  mov     rbx, rax
0x1800133f2  mov     ecx, [rax]
0x1800133f4  cmp     ecx, 5
0x1800133f7  jbe     short loc_180013462
0x1800133f9  mov     rdx, 400000000000h
0x180013403  mov     rcx, rax
0x180013406  call    _tlgKeywordOn
0x18001340b  test    al, al
0x18001340d  jz      short loc_180013462
0x18001340f  call    cs:__imp_GetCurrentThreadId
0x180013415  mov     r8, [rdi+110h]
0x18001341c  lea     rdx, unk_180021098
0x180013423  mov     [rsp+48h+arg_8], eax
0x180013427  add     r8, 8
0x18001342b  lea     rax, [rsp+48h+arg_8]
0x180013430  mov     dword ptr [rsp+48h+arg_0], 0
0x180013438  mov     [rsp+48h+var_18], rax
0x18001343d  mov     rcx, rbx
0x180013440  lea     rax, [rsp+48h+arg_0]
0x180013445  mov     [rsp+48h+arg_10], 1000000h
0x18001344e  mov     [rsp+48h+var_20], rax
0x180013453  lea     rax, [rsp+48h+arg_10]
0x180013458  mov     [rsp+48h+var_28], rax
0x18001345d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013462  mov     rcx, rdi
0x180013465  mov     rbx, [rsp+48h+arg_18]
0x18001346a  add     rsp, 40h
0x18001346e  pop     rdi
0x18001346f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
