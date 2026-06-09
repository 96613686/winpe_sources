# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18002f584`
- end: `0x18002f684`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a0c0`

## callees

- `0x18002736c`
- `0x180029bcc`
- `0x18002a404`
- `0x18002ad90`
- `0x18002ae44`
- `0x18002d3b0`
- `0x18002f584`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f5ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f5ea`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002f605`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002f605`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  unsigned int v2; // ebp
  __int64 *v3; // rax
  __int64 v4; // rsi
  DWORD CurrentThreadId; // eax
  int v6; // edi
  bool v7; // di
  struct Windows::Internal::IAsyncFireCompletion *v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  if ( (int)Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth() <= 4 )
    goto LABEL_11;
  v2 = 0;
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
  v3 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v10,
                    &v9);
  v4 = *v3;
  *v3 = 0;
  if ( v10 )
  {
    v10 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::OnlineId::UserIdentity *>>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v7 = v6 >= 0;
  if ( v9 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v7 )
  {
LABEL_11:
    Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth();
    v2 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 24LL))(a1);
    Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth();
  }
  return v2;
}

```

## disassembly

```asm
0x18002f584  mov     [rsp+arg_0], rbx
0x18002f589  push    rbp
0x18002f58a  push    rsi
0x18002f58b  push    rdi
0x18002f58c  sub     rsp, 30h
0x18002f590  mov     rbx, rcx
0x18002f593  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x18002f598  cmp     eax, 4
0x18002f59b  jle     loc_18002F65A
0x18002f5a1  xor     ebp, ebp
0x18002f5a3  mov     [rsp+48h+arg_8], rbx
0x18002f5a8  lea     rcx, [rsp+48h+arg_8]
0x18002f5ad  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002f5b2  mov     [rsp+48h+arg_8], rbx
0x18002f5b7  lea     rcx, [rsp+48h+arg_8]
0x18002f5bc  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002f5c1  lea     rdx, [rsp+48h+arg_8]
0x18002f5c6  lea     rcx, [rsp+48h+arg_10]
0x18002f5cb  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18002f5d0  mov     rsi, [rax]
0x18002f5d3  mov     [rax], rbp
0x18002f5d6  mov     rcx, [rsp+48h+arg_10]
0x18002f5db  test    rcx, rcx
0x18002f5de  jz      short loc_18002F5EA
0x18002f5e0  mov     [rsp+48h+arg_10], rbp
0x18002f5e5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVUserIdentity@OnlineId@Authentication@Security@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::OnlineId::UserIdentity *>>::Release(void)
0x18002f5ea  call    cs:__imp_GetCurrentThreadId
0x18002f5f0  mov     [rsp+48h+var_20], rbp
0x18002f5f5  mov     [rsp+48h+var_28], rsi
0x18002f5fa  xor     r9d, r9d
0x18002f5fd  mov     r8d, eax
0x18002f600  xor     edx, edx
0x18002f602  lea     ecx, [rdx+3]
0x18002f605  call    cs:__imp_SHTaskPoolQueueTask
0x18002f60b  mov     edi, eax
0x18002f60d  test    rsi, rsi
0x18002f610  jz      short loc_18002F622
0x18002f612  mov     rdx, [rsi]
0x18002f615  mov     rcx, rsi
0x18002f618  mov     rax, [rdx+10h]
0x18002f61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f621  nop
0x18002f622  shr     edi, 1Fh
0x18002f625  xor     dil, 1
0x18002f629  mov     rcx, [rsp+48h+arg_8]
0x18002f62e  test    rcx, rcx
0x18002f631  jz      short loc_18002F640
0x18002f633  mov     rax, [rcx]
0x18002f636  mov     rax, [rax+10h]
0x18002f63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f63f  nop
0x18002f640  test    rbx, rbx
0x18002f643  jz      short loc_18002F655
0x18002f645  mov     rax, [rbx]
0x18002f648  mov     rcx, rbx
0x18002f64b  mov     rax, [rax+10h]
0x18002f64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f654  nop
0x18002f655  test    dil, dil
0x18002f658  jnz     short loc_18002F675
0x18002f65a  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x18002f65f  mov     rax, [rbx]
0x18002f662  mov     rcx, rbx
0x18002f665  mov     rax, [rax+18h]
0x18002f669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f66e  mov     ebp, eax
0x18002f670  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x18002f675  mov     eax, ebp
0x18002f677  mov     rbx, [rsp+48h+arg_0]
0x18002f67c  add     rsp, 30h
0x18002f680  pop     rdi
0x18002f681  pop     rsi
0x18002f682  pop     rbp
0x18002f683  retn
```
