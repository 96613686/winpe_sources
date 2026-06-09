# Windows::Internal::ComTaskPool::QueueTask<_lambda_aaac285f1682a49811d03760bad078e8_>(Windows::Internal::TaskApartment,_lambda_aaac285f1682a49811d03760bad078e8_ &&)

- ea: `0x18001cb08`
- end: `0x18001cbba`
- name: `??$QueueTask@V_lambda_aaac285f1682a49811d03760bad078e8_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_aaac285f1682a49811d03760bad078e8_@@@Z`
- size: `178`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d2e0`

## callees

- `0x1800175c0`
- `0x18001c714`
- `0x18001cb08`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb5d`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001cb7c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001cb7c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_aaac285f1682a49811d03760bad078e8_>(
        __int64 a1,
        __int64 a2)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v5; // esi
  __int64 v7; // [rsp+58h] [rbp+10h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h]

  v7 = a2;
  v2 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_aaac285f1682a49811d03760bad078e8_>,_lambda_aaac285f1682a49811d03760bad078e8_>(&v7);
  v3 = *v2;
  v8 = *v2;
  *v2 = 0;
  if ( v7 )
  {
    v7 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v5 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v3, 0, 1);
  if ( v3 )
  {
    v8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return v5;
}

```

## disassembly

```asm
0x18001cb08  mov     rax, rsp
0x18001cb0b  mov     [rax+8], rbx
0x18001cb0f  mov     [rax+20h], rsi
0x18001cb13  mov     [rax+10h], rdx
0x18001cb17  push    rdi
0x18001cb18  sub     rsp, 40h
0x18001cb1c  mov     dword ptr [rax-18h], 0
0x18001cb23  lea     rcx, [rax+10h]
0x18001cb27  call    ??$Make@V?$CTaskWrapper@V_lambda_aaac285f1682a49811d03760bad078e8_@@@ComTaskPool@Internal@Windows@@V_lambda_aaac285f1682a49811d03760bad078e8_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_aaac285f1682a49811d03760bad078e8_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_aaac285f1682a49811d03760bad078e8_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_aaac285f1682a49811d03760bad078e8_>,_lambda_aaac285f1682a49811d03760bad078e8_>(_lambda_aaac285f1682a49811d03760bad078e8_ &&)
0x18001cb2c  nop
0x18001cb2d  mov     rbx, [rax]
0x18001cb30  mov     [rsp+48h+arg_10], rbx
0x18001cb35  mov     qword ptr [rax], 0
0x18001cb3c  mov     edi, 1
0x18001cb41  mov     [rsp+48h+var_18], edi
0x18001cb45  mov     rcx, [rsp+48h+arg_8]
0x18001cb4a  test    rcx, rcx
0x18001cb4d  jz      short loc_18001CB5D
0x18001cb4f  mov     [rsp+48h+arg_8], 0
0x18001cb58  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(void)
0x18001cb5d  call    cs:__imp_GetCurrentThreadId
0x18001cb63  mov     [rsp+48h+var_20], 0
0x18001cb6c  mov     [rsp+48h+var_28], rbx
0x18001cb71  xor     r9d, r9d
0x18001cb74  mov     r8d, eax
0x18001cb77  xor     edx, edx
0x18001cb79  lea     ecx, [rdx+3]
0x18001cb7c  call    cs:__imp_SHTaskPoolQueueTask
0x18001cb82  mov     esi, eax
0x18001cb84  and     edi, 0FFFFFFFEh
0x18001cb87  mov     [rsp+48h+var_18], edi
0x18001cb8b  test    rbx, rbx
0x18001cb8e  jz      short loc_18001CBA8
0x18001cb90  mov     [rsp+48h+arg_10], 0
0x18001cb99  mov     rdx, [rbx]
0x18001cb9c  mov     rcx, rbx
0x18001cb9f  mov     rax, [rdx+10h]
0x18001cba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cba8  mov     eax, esi
0x18001cbaa  mov     rbx, [rsp+48h+arg_0]
0x18001cbaf  mov     rsi, [rsp+48h+arg_18]
0x18001cbb4  add     rsp, 40h
0x18001cbb8  pop     rdi
0x18001cbb9  retn
```
