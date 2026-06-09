# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::DisableCausality>::OnStart(void)

- ea: `0x18002b8a0`
- end: `0x18002b966`
- name: `?OnStart@?$AsyncOperation@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@VCNoResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@UDisableCausality@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18002b8a0`
- `0x18002f260`
- `0x18002f760`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b8d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b8d7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002b917`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002b917`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::DisableCausality>::OnStart(
        __int64 a1)
{
  unsigned int v2; // ebx
  DWORD CurrentThreadId; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 256) + 8LL))(
         *(_QWORD *)(a1 + 256),
         0,
         0,
         a1 + 280);
  if ( (v2 & 0x80000000) != 0 )
  {
LABEL_5:
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>::TryTransitionToError(
      a1,
      v2);
    return v2;
  }
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 312) = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(
         *(unsigned int *)(a1 + 304),
         *(unsigned int *)(a1 + 308),
         CurrentThreadId,
         0,
         (a1 + 200) & -(__int64)(a1 != 8),
         0);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 248) )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::DisableCausality>::_Run(
      a1 - 8,
      1,
      v2);
    goto LABEL_5;
  }
  return v2;
}

```

## disassembly

```asm
0x18002b8a0  mov     [rsp+arg_0], rbx
0x18002b8a5  mov     [rsp+arg_8], rsi
0x18002b8aa  push    rdi
0x18002b8ab  sub     rsp, 30h
0x18002b8af  mov     rdi, rcx
0x18002b8b2  xor     r8d, r8d
0x18002b8b5  mov     rcx, [rcx+100h]
0x18002b8bc  xor     edx, edx
0x18002b8be  lea     r9, [rdi+118h]
0x18002b8c5  mov     rax, [rcx]
0x18002b8c8  mov     rax, [rax+8]
0x18002b8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8d1  mov     ebx, eax
0x18002b8d3  test    eax, eax
0x18002b8d5  js      short loc_18002B93C
0x18002b8d7  call    cs:__imp_GetCurrentThreadId
0x18002b8dd  lea     rdx, [rdi+0C8h]
0x18002b8e4  mov     [rsp+38h+var_10], 0
0x18002b8ed  lea     rcx, [rdi-8]
0x18002b8f1  mov     [rdi+138h], eax
0x18002b8f7  neg     rcx
0x18002b8fa  mov     ecx, [rdi+130h]
0x18002b900  sbb     r8, r8
0x18002b903  xor     r9d, r9d
0x18002b906  and     r8, rdx
0x18002b909  mov     edx, [rdi+134h]
0x18002b90f  mov     [rsp+38h+var_18], r8
0x18002b914  mov     r8d, eax
0x18002b917  call    cs:__imp_SHTaskPoolQueueTask
0x18002b91d  mov     ebx, eax
0x18002b91f  test    eax, eax
0x18002b921  jns     short loc_18002B946
0x18002b923  mov     eax, [rdi+0F8h]
0x18002b929  test    eax, eax
0x18002b92b  jnz     short loc_18002B958
0x18002b92d  mov     r8d, ebx
0x18002b930  lea     edx, [rax+1]
0x18002b933  lea     rcx, [rdi-8]
0x18002b937  call    ?_Run@?$AsyncOperation@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@VCNoResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@UDisableCausality@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::DisableCausality>::_Run(Windows::Internal::AsyncStage,long)
0x18002b93c  mov     edx, ebx
0x18002b93e  mov     rcx, rdi
0x18002b941  call    ?TryTransitionToError@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00UDisableCausality@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18002b946  mov     rsi, [rsp+38h+arg_8]
0x18002b94b  mov     eax, ebx
0x18002b94d  mov     rbx, [rsp+38h+arg_0]
0x18002b952  add     rsp, 30h
0x18002b956  pop     rdi
0x18002b957  retn
0x18002b958  mov     edx, ebx
0x18002b95a  mov     rcx, rdi
0x18002b95d  call    ?TryTransitionToError@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00UDisableCausality@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18002b962  xor     ebx, ebx
0x18002b964  jmp     short loc_18002B946
```
