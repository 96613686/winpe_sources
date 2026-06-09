# Windows::Internal::ComTaskPool::QueueTask<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(Windows::Internal::TaskApartment,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)

- ea: `0x140031184`
- end: `0x140031210`
- name: `??$QueueTask@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140036f4c`

## callees

- `0x14001f700`
- `0x140030f0c`
- `0x140031184`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400311ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400311ba`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1400311df`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1400311df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>()
{
  __int64 *v0; // rax
  __int64 v1; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v3; // edi
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  v0 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(&v5);
  v1 = *v0;
  *v0 = 0;
  if ( v5 )
  {
    v5 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v3 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v1, 0);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return v3;
}

```

## disassembly

```asm
0x140031184  mov     [rsp+arg_0], rbx
0x140031189  push    rdi
0x14003118a  sub     rsp, 30h
0x14003118e  lea     rcx, [rsp+38h+arg_10]
0x140031193  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x140031198  mov     rbx, [rax]
0x14003119b  mov     qword ptr [rax], 0
0x1400311a2  mov     rcx, [rsp+38h+arg_10]
0x1400311a7  test    rcx, rcx
0x1400311aa  jz      short loc_1400311BA
0x1400311ac  mov     [rsp+38h+arg_10], 0
0x1400311b5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1400311ba  call    cs:__imp_GetCurrentThreadId
0x1400311c1  nop     dword ptr [rax+rax+00h]
0x1400311c6  mov     [rsp+38h+var_10], 0
0x1400311cf  mov     [rsp+38h+var_18], rbx
0x1400311d4  xor     r9d, r9d
0x1400311d7  mov     r8d, eax
0x1400311da  xor     edx, edx
0x1400311dc  lea     ecx, [rdx+3]
0x1400311df  call    cs:__imp_SHTaskPoolQueueTask
0x1400311e6  nop     dword ptr [rax+rax+00h]
0x1400311eb  mov     edi, eax
0x1400311ed  test    rbx, rbx
0x1400311f0  jz      short loc_140031202
0x1400311f2  mov     rdx, [rbx]
0x1400311f5  mov     rcx, rbx
0x1400311f8  mov     rax, [rdx+10h]
0x1400311fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031201  nop
0x140031202  mov     eax, edi
0x140031204  mov     rbx, [rsp+38h+arg_0]
0x140031209  add     rsp, 30h
0x14003120d  pop     rdi
0x14003120e  retn
```
