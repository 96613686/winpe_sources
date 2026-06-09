# Execution::ExecutionServices::WorkerThreadItem::~WorkerThreadItem(void)

- ea: `0x18007c150`
- end: `0x18007c1cf`
- name: `??1WorkerThreadItem@ExecutionServices@Execution@@UEAA@XZ`
- size: `127`
- prototype: `void __fastcall(Execution::ExecutionServices::WorkerThreadItem *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007c250`

## callees

- `0x180039090`
- `0x18007c150`
- `0x18007d134`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18007c179`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18007c179`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c199`

## pseudocode

```c
void __fastcall Execution::ExecutionServices::WorkerThreadItem::~WorkerThreadItem(
        Execution::ExecutionServices::WorkerThreadItem *this)
{
  bool v1; // zf
  DWORD ThreadId; // ebx
  void *v4; // rcx
  __int64 v5; // rcx

  v1 = *((_QWORD *)this + 6) == 0;
  *(_QWORD *)this = &Execution::ExecutionServices::WorkerThreadItem::`vftable';
  if ( !v1 )
  {
    ThreadId = GetThreadId(*(HANDLE *)(*((_QWORD *)this + 4) + 128LL));
    if ( GetCurrentThreadId() != ThreadId )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
    CloseHandle(v4);
  v5 = *((_QWORD *)this + 6);
  if ( v5 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
}

```

## disassembly

```asm
0x18007c150  mov     [rsp+arg_0], rbx
0x18007c155  push    rdi
0x18007c156  sub     rsp, 20h
0x18007c15a  cmp     qword ptr [rcx+30h], 0
0x18007c15f  lea     rax, ??_7WorkerThreadItem@ExecutionServices@Execution@@6B@; const Execution::ExecutionServices::WorkerThreadItem::`vftable'
0x18007c166  mov     [rcx], rax
0x18007c169  mov     rdi, rcx
0x18007c16c  jz      short loc_18007C190
0x18007c16e  mov     rcx, [rcx+20h]
0x18007c172  mov     rcx, [rcx+80h]; Thread
0x18007c179  call    cs:__imp_GetThreadId
0x18007c17f  mov     ebx, eax
0x18007c181  call    cs:__imp_GetCurrentThreadId
0x18007c187  cmp     eax, ebx
0x18007c189  jz      short loc_18007C190
0x18007c18b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007c190  mov     rcx, [rdi+38h]; hObject
0x18007c194  test    rcx, rcx
0x18007c197  jz      short loc_18007C19F
0x18007c199  call    cs:__imp_CloseHandle
0x18007c19f  mov     rcx, [rdi+30h]
0x18007c1a3  test    rcx, rcx
0x18007c1a6  jz      short loc_18007C1BC
0x18007c1a8  mov     qword ptr [rdi+30h], 0
0x18007c1b0  mov     rax, [rcx]
0x18007c1b3  mov     rax, [rax+10h]
0x18007c1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c1bc  lea     rcx, [rdi+10h]
0x18007c1c0  mov     rbx, [rsp+28h+arg_0]
0x18007c1c5  add     rsp, 20h
0x18007c1c9  pop     rdi
0x18007c1ca  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
