# Execution::ExecutionServices::~ExecutionServices(void)

- ea: `0x18007c0b8`
- end: `0x18007c14a`
- name: `??1ExecutionServices@Execution@@MEAA@XZ`
- size: `146`
- prototype: `void __fastcall(Execution::ExecutionServices *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007c210`

## callees

- `0x18007c04c`
- `0x18007c0b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007c137`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007c137`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007c0d4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007c0d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c0eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c0eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c0fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c10c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c11b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c0fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c10c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c11b`

## pseudocode

```c
void __fastcall Execution::ExecutionServices::~ExecutionServices(Execution::ExecutionServices *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &Execution::ExecutionServices::`vftable';
  v2 = (void *)*((_QWORD *)this + 14);
  if ( v2 )
  {
    SetEvent(v2);
    v3 = (void *)*((_QWORD *)this + 16);
    if ( v3 )
      WaitForSingleObject(v3, 0x1388u);
  }
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 14);
  if ( v6 )
    CloseHandle(v6);
  utl::list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>::~list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>((char *)this + 88);
  utl::list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>::~list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18007c0b8  push    rbx
0x18007c0ba  sub     rsp, 20h
0x18007c0be  lea     rax, ??_7ExecutionServices@Execution@@6B@; const Execution::ExecutionServices::`vftable'
0x18007c0c5  mov     rbx, rcx
0x18007c0c8  mov     [rcx], rax
0x18007c0cb  mov     rcx, [rcx+70h]; hEvent
0x18007c0cf  test    rcx, rcx
0x18007c0d2  jz      short loc_18007C0F1
0x18007c0d4  call    cs:__imp_SetEvent
0x18007c0da  mov     rcx, [rbx+80h]; hHandle
0x18007c0e1  test    rcx, rcx
0x18007c0e4  jz      short loc_18007C0F1
0x18007c0e6  mov     edx, 1388h; dwMilliseconds
0x18007c0eb  call    cs:__imp_WaitForSingleObject
0x18007c0f1  mov     rcx, [rbx+80h]; hObject
0x18007c0f8  test    rcx, rcx
0x18007c0fb  jz      short loc_18007C103
0x18007c0fd  call    cs:__imp_CloseHandle
0x18007c103  mov     rcx, [rbx+78h]; hObject
0x18007c107  test    rcx, rcx
0x18007c10a  jz      short loc_18007C112
0x18007c10c  call    cs:__imp_CloseHandle
0x18007c112  mov     rcx, [rbx+70h]; hObject
0x18007c116  test    rcx, rcx
0x18007c119  jz      short loc_18007C121
0x18007c11b  call    cs:__imp_CloseHandle
0x18007c121  lea     rcx, [rbx+58h]
0x18007c125  call    ??1?$list@V?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>::~list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>(void)
0x18007c12a  lea     rcx, [rbx+40h]
0x18007c12e  call    ??1?$list@V?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>::~list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>(void)
0x18007c133  lea     rcx, [rbx+10h]; lpCriticalSection
0x18007c137  call    cs:__imp_DeleteCriticalSection
0x18007c13d  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18007c144  add     rsp, 20h
0x18007c148  pop     rbx
0x18007c149  retn
```
