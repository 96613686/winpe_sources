# wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001c41c`
- end: `0x18001c4dc`
- name: `?Stop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `192`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001c044`
- `0x180027180`
- `0x1800271fc`
- `0x180027278`

## callees

- `0x1800019d8`
- `0x18001ba9c`
- `0x18001c024`
- `0x18001c1c8`
- `0x18001c41c`
- `0x18001d2a4`
- `0x18001d4e8`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001c47e`
- `KERNEL32!GetCurrentThreadId` at `0x18001c47e`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  const struct _tlgProvider_t *v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  int v8; // r9d
  DWORD v10; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v11);
  v4 = wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FontEmbeddingTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v10);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v5 = FontEmbeddingTelemetryProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v10 = CurrentThreadId;
      v11 = a2;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v5,
        (unsigned int)&unk_18002D838,
        v7 + 8,
        v8,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v10);
    }
  }
  return wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18001c41c  push    rbx
0x18001c41e  push    rsi
0x18001c41f  push    rdi
0x18001c420  sub     rsp, 40h
0x18001c424  mov     esi, edx
0x18001c426  mov     [rsp+58h+arg_0], 0
0x18001c42e  lea     rdx, [rsp+58h+arg_10]
0x18001c433  mov     rdi, rcx
0x18001c436  call    ?LockExclusive@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c43b  mov     rcx, [rdi+110h]
0x18001c442  lea     r8, [rsp+58h+arg_0]
0x18001c447  mov     edx, esi
0x18001c449  call    ?SetStopResult@?$ActivityData@VFontEmbeddingTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FontEmbeddingTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18001c44e  lea     rcx, [rsp+58h+arg_10]
0x18001c453  mov     bl, al
0x18001c455  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001c45a  test    bl, bl
0x18001c45c  jz      short loc_18001C46F
0x18001c45e  mov     rax, [rdi]
0x18001c461  mov     rcx, rdi
0x18001c464  mov     rax, [rax+8]
0x18001c468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c46d  jmp     short loc_18001C4CD
0x18001c46f  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x18001c474  mov     rbx, rax
0x18001c477  mov     ecx, [rax]
0x18001c479  cmp     ecx, 5
0x18001c47c  jbe     short loc_18001C4CD
0x18001c47e  call    cs:__imp_GetCurrentThreadId
0x18001c484  mov     r8, [rdi+110h]
0x18001c48b  lea     rdx, unk_18002D838
0x18001c492  mov     [rsp+58h+arg_0], eax
0x18001c496  add     r8, 8
0x18001c49a  lea     rax, [rsp+58h+arg_0]
0x18001c49f  mov     [rsp+58h+arg_10], esi
0x18001c4a3  mov     [rsp+58h+var_28], rax
0x18001c4a8  mov     rcx, rbx
0x18001c4ab  lea     rax, [rsp+58h+arg_10]
0x18001c4b0  mov     [rsp+58h+arg_18], 1000000h
0x18001c4b9  mov     [rsp+58h+var_30], rax
0x18001c4be  lea     rax, [rsp+58h+arg_18]
0x18001c4c3  mov     [rsp+58h+var_38], rax
0x18001c4c8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c4cd  mov     rcx, rdi
0x18001c4d0  add     rsp, 40h
0x18001c4d4  pop     rdi
0x18001c4d5  pop     rsi
0x18001c4d6  pop     rbx
0x18001c4d7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
