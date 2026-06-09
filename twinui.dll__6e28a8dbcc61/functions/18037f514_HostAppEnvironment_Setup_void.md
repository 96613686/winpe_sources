# HostAppEnvironment::Setup(void)

- ea: `0x18037f514`
- end: `0x18037f6f7`
- name: `?Setup@HostAppEnvironment@@QEAAJXZ`
- size: `483`
- prototype: `__int64 __fastcall(HostAppEnvironment *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18037d2b0`
- `0x18037e1ec`

## callees

- `0x180066480`
- `0x1800a80c8`
- `0x1800e6b28`
- `0x1800ead54`
- `0x180106188`
- `0x18037e99c`
- `0x18037ea2c`
- `0x18037eb4c`
- `0x18037ebdc`
- `0x18037f514`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18037f565`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18037f565`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18037f53e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18037f53e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18037f5c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18037f62e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18037f694`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18037f5c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18037f62e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18037f694`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18037f5e2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18037f648`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18037f6ae`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18037f5e2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18037f648`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18037f6ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HostAppEnvironment::Setup(HostAppEnvironment *this)
{
  HANDLE MutexW; // rdi
  HANDLE EventW; // rax
  const char *v4; // r9
  _lambda_aec159daf75c9a566e43618f77172940_ *v6; // rax
  __int64 *v7; // rax
  __int64 v8; // rdi
  DWORD CurrentThreadId; // eax
  _lambda_aec159daf75c9a566e43618f77172940_ *v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 v14; // rcx
  DWORD v15; // eax
  _lambda_aec159daf75c9a566e43618f77172940_ *v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 v20; // rcx
  DWORD v21; // eax
  _lambda_aec159daf75c9a566e43618f77172940_ *v22; // rax
  __int64 v23; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v25; // [rsp+50h] [rbp+20h] BYREF
  char v26; // [rsp+58h] [rbp+28h] BYREF

  if ( !*((_BYTE *)this + 32) )
  {
    MutexW = CreateMutexW(0, 1, L"Global\\Windows.User.OOBE");
    if ( MutexW != *((HANDLE *)this + 1) )
    {
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(this);
      *((_QWORD *)this + 1) = MutexW;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      (char *)this + 16,
      EventW);
    if ( !*((_QWORD *)this + 3) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x62,
               (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\hostappenvironment.cpp",
               v4);
    v6 = _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(
           (_lambda_aec159daf75c9a566e43618f77172940_ *)&v26,
           this);
    v7 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_46c2733e2687afde5245bd084a2f7edf_____lambda_46c2733e2687afde5245bd084a2f7edf___(
                      &v25,
                      v6);
    v8 = *v7;
    *v7 = 0;
    if ( v25 )
    {
      v25 = 0;
      ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAsyncCallbackDispatcher>::Release)();
    }
    CurrentThreadId = GetCurrentThreadId();
    SHTaskPoolQueueTask(1, 0, CurrentThreadId);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v10 = _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(
            (_lambda_aec159daf75c9a566e43618f77172940_ *)&v26,
            this);
    v11 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____lambda_deee8152b7769f5e304c76a887ad1fef___(
                       &v25,
                       v10);
    v13 = *v11;
    *v11 = 0;
    v14 = v25;
    if ( v25 )
    {
      v25 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAsyncCallbackDispatcher>::Release(
        v14,
        v12);
    }
    v15 = GetCurrentThreadId();
    SHTaskPoolQueueTask(0, 0, v15);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v16 = _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(
            (_lambda_aec159daf75c9a566e43618f77172940_ *)&v26,
            this);
    v17 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7b0b85b4ff8a2c75a053dae0df721d9e_____lambda_7b0b85b4ff8a2c75a053dae0df721d9e___(
                       &v25,
                       v16);
    v19 = *v17;
    *v17 = 0;
    v20 = v25;
    if ( v25 )
    {
      v25 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAsyncCallbackDispatcher>::Release(
        v20,
        v18);
    }
    v21 = GetCurrentThreadId();
    SHTaskPoolQueueTask(0, 0, v21);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( !*((_BYTE *)this + 34) )
    {
      v22 = _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(
              (_lambda_aec159daf75c9a566e43618f77172940_ *)&v25,
              this);
      Windows::Internal::ComTaskPool::QueueTask__lambda_983deade1ef85b175d24d05d87d8a1b3___(v23, v22);
    }
    *((_BYTE *)this + 32) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18037f514  mov     [rsp-18h+arg_10], rbx
0x18037f519  push    rbp
0x18037f51a  push    rsi
0x18037f51b  push    rdi
0x18037f51c  mov     rbp, rsp
0x18037f51f  sub     rsp, 30h
0x18037f523  mov     rbx, rcx
0x18037f526  xor     esi, esi
0x18037f528  cmp     [rcx+20h], sil
0x18037f52c  jnz     loc_18037F6E8
0x18037f532  lea     r8, aGlobalWindowsU; "Global\\Windows.User.OOBE"
0x18037f539  lea     edx, [rsi+1]; bInitialOwner
0x18037f53c  xor     ecx, ecx; lpMutexAttributes
0x18037f53e  call    cs:__imp_CreateMutexW
0x18037f544  mov     rdi, rax
0x18037f547  cmp     rax, [rbx+8]
0x18037f54b  jz      short loc_18037F559
0x18037f54d  mov     rcx, rbx
0x18037f550  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18037f555  mov     [rbx+8], rdi
0x18037f559  xor     r9d, r9d; lpName
0x18037f55c  xor     r8d, r8d; bInitialState
0x18037f55f  lea     edx, [r9+1]; bManualReset
0x18037f563  xor     ecx, ecx; lpEventAttributes
0x18037f565  call    cs:__imp_CreateEventW
0x18037f56b  mov     rdx, rax
0x18037f56e  lea     rcx, [rbx+10h]
0x18037f572  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x18037f577  cmp     [rbx+18h], rsi
0x18037f57b  jnz     short loc_18037F597
0x18037f57d  mov     rcx, [rbp+18h]; this
0x18037f581  lea     r8, aShellLibCloude_1; "shell\\lib\\cloudexperiencehostappmanag"...
0x18037f588  mov     edx, 62h ; 'b'; void *
0x18037f58d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18037f592  jmp     loc_18037F6EA
0x18037f597  mov     rdx, rbx; struct CSearchSuggestionsProvider *
0x18037f59a  lea     rcx, [rbp+arg_8]; this
0x18037f59e  call    ??0_lambda_aec159daf75c9a566e43618f77172940_@@QEAA@PEAVCSearchSuggestionsProvider@@@Z; _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(CSearchSuggestionsProvider *)
0x18037f5a3  mov     rdx, rax
0x18037f5a6  lea     rcx, [rbp+arg_0]
0x18037f5aa  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_46c2733e2687afde5245bd084a2f7edf_____lambda_46c2733e2687afde5245bd084a2f7edf___
0x18037f5af  mov     rdi, [rax]
0x18037f5b2  mov     [rax], rsi
0x18037f5b5  mov     rcx, [rbp+arg_0]
0x18037f5b9  test    rcx, rcx
0x18037f5bc  jz      short loc_18037F5C7
0x18037f5be  mov     [rbp+arg_0], rsi
0x18037f5c2  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncCallbackDispatcher@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAsyncCallbackDispatcher>::Release(void)
0x18037f5c7  call    cs:__imp_GetCurrentThreadId
0x18037f5cd  mov     [rsp+30h+var_8], rsi
0x18037f5d2  mov     [rsp+30h+var_10], rdi
0x18037f5d7  xor     r9d, r9d
0x18037f5da  mov     r8d, eax
0x18037f5dd  xor     edx, edx
0x18037f5df  lea     ecx, [rdx+1]
0x18037f5e2  call    cs:__imp_SHTaskPoolQueueTask
0x18037f5e8  nop
0x18037f5e9  test    rdi, rdi
0x18037f5ec  jz      short loc_18037F5FE
0x18037f5ee  mov     rax, [rdi]
0x18037f5f1  mov     rcx, rdi
0x18037f5f4  mov     rax, [rax+10h]
0x18037f5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f5fd  nop
0x18037f5fe  mov     rdx, rbx; struct CSearchSuggestionsProvider *
0x18037f601  lea     rcx, [rbp+arg_8]; this
0x18037f605  call    ??0_lambda_aec159daf75c9a566e43618f77172940_@@QEAA@PEAVCSearchSuggestionsProvider@@@Z; _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(CSearchSuggestionsProvider *)
0x18037f60a  mov     rdx, rax
0x18037f60d  lea     rcx, [rbp+arg_0]
0x18037f611  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____lambda_deee8152b7769f5e304c76a887ad1fef___
0x18037f616  mov     rdi, [rax]
0x18037f619  mov     [rax], rsi
0x18037f61c  mov     rcx, [rbp+arg_0]
0x18037f620  test    rcx, rcx
0x18037f623  jz      short loc_18037F62E
0x18037f625  mov     [rbp+arg_0], rsi
0x18037f629  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncCallbackDispatcher@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAsyncCallbackDispatcher>::Release(void)
0x18037f62e  call    cs:__imp_GetCurrentThreadId
0x18037f634  mov     [rsp+30h+var_8], rsi
0x18037f639  mov     [rsp+30h+var_10], rdi
0x18037f63e  xor     r9d, r9d
0x18037f641  mov     r8d, eax
0x18037f644  xor     edx, edx
0x18037f646  xor     ecx, ecx
0x18037f648  call    cs:__imp_SHTaskPoolQueueTask
0x18037f64e  nop
0x18037f64f  test    rdi, rdi
0x18037f652  jz      short loc_18037F664
0x18037f654  mov     rax, [rdi]
0x18037f657  mov     rcx, rdi
0x18037f65a  mov     rax, [rax+10h]
0x18037f65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f663  nop
0x18037f664  mov     rdx, rbx; struct CSearchSuggestionsProvider *
0x18037f667  lea     rcx, [rbp+arg_8]; this
0x18037f66b  call    ??0_lambda_aec159daf75c9a566e43618f77172940_@@QEAA@PEAVCSearchSuggestionsProvider@@@Z; _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(CSearchSuggestionsProvider *)
0x18037f670  mov     rdx, rax
0x18037f673  lea     rcx, [rbp+arg_0]
0x18037f677  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_7b0b85b4ff8a2c75a053dae0df721d9e_____lambda_7b0b85b4ff8a2c75a053dae0df721d9e___
0x18037f67c  mov     rdi, [rax]
0x18037f67f  mov     [rax], rsi
0x18037f682  mov     rcx, [rbp+arg_0]
0x18037f686  test    rcx, rcx
0x18037f689  jz      short loc_18037F694
0x18037f68b  mov     [rbp+arg_0], rsi
0x18037f68f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncCallbackDispatcher@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAsyncCallbackDispatcher>::Release(void)
0x18037f694  call    cs:__imp_GetCurrentThreadId
0x18037f69a  mov     [rsp+30h+var_8], rsi
0x18037f69f  mov     [rsp+30h+var_10], rdi
0x18037f6a4  xor     r9d, r9d
0x18037f6a7  mov     r8d, eax
0x18037f6aa  xor     edx, edx
0x18037f6ac  xor     ecx, ecx
0x18037f6ae  call    cs:__imp_SHTaskPoolQueueTask
0x18037f6b4  nop
0x18037f6b5  test    rdi, rdi
0x18037f6b8  jz      short loc_18037F6CA
0x18037f6ba  mov     rax, [rdi]
0x18037f6bd  mov     rcx, rdi
0x18037f6c0  mov     rax, [rax+10h]
0x18037f6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f6c9  nop
0x18037f6ca  cmp     [rbx+22h], sil
0x18037f6ce  jnz     short loc_18037F6E4
0x18037f6d0  mov     rdx, rbx; struct CSearchSuggestionsProvider *
0x18037f6d3  lea     rcx, [rbp+arg_0]; this
0x18037f6d7  call    ??0_lambda_aec159daf75c9a566e43618f77172940_@@QEAA@PEAVCSearchSuggestionsProvider@@@Z; _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(CSearchSuggestionsProvider *)
0x18037f6dc  mov     rdx, rax
0x18037f6df  call    Windows__Internal__ComTaskPool__QueueTask__lambda_983deade1ef85b175d24d05d87d8a1b3___
0x18037f6e4  mov     byte ptr [rbx+20h], 1
0x18037f6e8  xor     eax, eax
0x18037f6ea  mov     rbx, [rsp+30h+arg_10]
0x18037f6ef  add     rsp, 30h
0x18037f6f3  pop     rdi
0x18037f6f4  pop     rsi
0x18037f6f5  pop     rbp
0x18037f6f6  retn
```
