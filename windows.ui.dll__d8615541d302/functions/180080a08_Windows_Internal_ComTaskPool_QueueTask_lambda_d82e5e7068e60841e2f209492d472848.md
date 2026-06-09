# Windows::Internal::ComTaskPool::QueueTask__lambda_d82e5e7068e60841e2f209492d472848___

- ea: `0x180080a08`
- end: `0x180080a86`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_d82e5e7068e60841e2f209492d472848___`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180082eb0`
- `0x180087d00`

## callees

- `0x180021ee0`
- `0x1800806a8`
- `0x180080a08`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080a3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080a3e`
- `SHCORE!SHTaskPoolQueueTask` at `0x180080a5c`
- `SHCORE!SHTaskPoolQueueTask` at `0x180080a5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask__lambda_d82e5e7068e60841e2f209492d472848___()
{
  __int64 *v0; // rax
  __int64 v1; // rdx
  __int64 v2; // rbx
  __int64 v3; // rcx
  DWORD CurrentThreadId; // eax
  unsigned int v5; // edi
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  v0 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d82e5e7068e60841e2f209492d472848_____lambda_d82e5e7068e60841e2f209492d472848___(&v7);
  v2 = *v0;
  *v0 = 0;
  v3 = v7;
  if ( v7 )
  {
    v7 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(
      v3,
      v1);
  }
  CurrentThreadId = GetCurrentThreadId();
  v5 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return v5;
}

```

## disassembly

```asm
0x180080a08  mov     [rsp+arg_0], rbx
0x180080a0d  push    rdi
0x180080a0e  sub     rsp, 30h
0x180080a12  lea     rcx, [rsp+38h+arg_10]
0x180080a17  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d82e5e7068e60841e2f209492d472848_____lambda_d82e5e7068e60841e2f209492d472848___
0x180080a1c  mov     rbx, [rax]
0x180080a1f  mov     qword ptr [rax], 0
0x180080a26  mov     rcx, [rsp+38h+arg_10]
0x180080a2b  test    rcx, rcx
0x180080a2e  jz      short loc_180080A3E
0x180080a30  mov     [rsp+38h+arg_10], 0
0x180080a39  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(void)
0x180080a3e  call    cs:__imp_GetCurrentThreadId
0x180080a44  mov     [rsp+38h+var_10], 0
0x180080a4d  mov     [rsp+38h+var_18], rbx
0x180080a52  xor     r9d, r9d
0x180080a55  mov     r8d, eax
0x180080a58  xor     edx, edx
0x180080a5a  xor     ecx, ecx
0x180080a5c  call    cs:__imp_SHTaskPoolQueueTask
0x180080a62  mov     edi, eax
0x180080a64  test    rbx, rbx
0x180080a67  jz      short loc_180080A79
0x180080a69  mov     rdx, [rbx]
0x180080a6c  mov     rcx, rbx
0x180080a6f  mov     rax, [rdx+10h]
0x180080a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080a78  nop
0x180080a79  mov     eax, edi
0x180080a7b  mov     rbx, [rsp+38h+arg_0]
0x180080a80  add     rsp, 30h
0x180080a84  pop     rdi
0x180080a85  retn
```
