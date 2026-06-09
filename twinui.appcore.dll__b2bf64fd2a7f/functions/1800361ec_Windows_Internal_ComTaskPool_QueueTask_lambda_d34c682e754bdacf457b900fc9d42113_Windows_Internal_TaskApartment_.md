# Windows::Internal::ComTaskPool::QueueTask<_lambda_d34c682e754bdacf457b900fc9d42113_ &>(Windows::Internal::TaskApartment,_lambda_d34c682e754bdacf457b900fc9d42113_ &)

- ea: `0x1800361ec`
- end: `0x18003626b`
- name: `??$QueueTask@AEAV_lambda_d34c682e754bdacf457b900fc9d42113_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@AEAV_lambda_d34c682e754bdacf457b900fc9d42113_@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006f30`

## callees

- `0x1800160c0`
- `0x18003600c`
- `0x1800361ec`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036222`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180036241`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180036241`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask<_lambda_d34c682e754bdacf457b900fc9d42113_ &>()
{
  __int64 *v0; // rax
  __int64 v1; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v3; // edi
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  v0 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_d34c682e754bdacf457b900fc9d42113_ &>,_lambda_d34c682e754bdacf457b900fc9d42113_ &>(&v5);
  v1 = *v0;
  *v0 = 0;
  if ( v5 )
  {
    v5 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v3 = SHTaskPoolQueueTask(3, 0, CurrentThreadId);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return v3;
}

```

## disassembly

```asm
0x1800361ec  mov     [rsp+arg_0], rbx
0x1800361f1  push    rdi
0x1800361f2  sub     rsp, 30h
0x1800361f6  lea     rcx, [rsp+38h+arg_10]
0x1800361fb  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_d34c682e754bdacf457b900fc9d42113_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_d34c682e754bdacf457b900fc9d42113_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_d34c682e754bdacf457b900fc9d42113_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_d34c682e754bdacf457b900fc9d42113_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_d34c682e754bdacf457b900fc9d42113_ &>,_lambda_d34c682e754bdacf457b900fc9d42113_ &>(_lambda_d34c682e754bdacf457b900fc9d42113_ &)
0x180036200  mov     rbx, [rax]
0x180036203  mov     qword ptr [rax], 0
0x18003620a  mov     rcx, [rsp+38h+arg_10]
0x18003620f  test    rcx, rcx
0x180036212  jz      short loc_180036222
0x180036214  mov     [rsp+38h+arg_10], 0
0x18003621d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180036222  call    cs:__imp_GetCurrentThreadId
0x180036228  mov     [rsp+38h+var_10], 0
0x180036231  mov     [rsp+38h+var_18], rbx
0x180036236  xor     r9d, r9d
0x180036239  mov     r8d, eax
0x18003623c  xor     edx, edx
0x18003623e  lea     ecx, [rdx+3]
0x180036241  call    cs:__imp_SHTaskPoolQueueTask
0x180036247  mov     edi, eax
0x180036249  test    rbx, rbx
0x18003624c  jz      short loc_18003625E
0x18003624e  mov     rdx, [rbx]
0x180036251  mov     rcx, rbx
0x180036254  mov     rax, [rdx+10h]
0x180036258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003625d  nop
0x18003625e  mov     eax, edi
0x180036260  mov     rbx, [rsp+38h+arg_0]
0x180036265  add     rsp, 30h
0x180036269  pop     rdi
0x18003626a  retn
```
