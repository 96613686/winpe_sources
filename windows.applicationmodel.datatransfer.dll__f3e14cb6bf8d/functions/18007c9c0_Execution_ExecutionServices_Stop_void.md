# Execution::ExecutionServices::Stop(void)

- ea: `0x18007c9c0`
- end: `0x18007cad4`
- name: `?Stop@ExecutionServices@Execution@@UEAAJXZ`
- size: `276`
- prototype: `__int64 __fastcall(Execution::ExecutionServices *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005504`
- `0x18007c9c0`
- `0x18007d0bc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007ca56`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007ca56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ca95`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ca95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ca6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ca6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ca3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ca3e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18007ca77`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18007ca77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007ca7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007ca7f`

## pseudocode

```c
__int64 __fastcall Execution::ExecutionServices::Stop(Execution::ExecutionServices *this)
{
  _QWORD *v2; // rax
  DWORD ThreadId; // ebx
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  _QWORD *v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  if ( v2 )
  {
    v2[3] = 0;
    *v2 = &Execution::ExecutionServices::WorkerThreadItem::`vftable';
    v2[2] = 0;
    v2[6] = 0;
    v2[7] = 0;
    v2[4] = 0;
    *((_DWORD *)v2 + 10) = 0;
    *((_DWORD *)v2 + 16) = 0;
    *((_DWORD *)v2 + 17) = 1;
    *((_DWORD *)v2 + 2) = 6;
    v7 = v2;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    utl::list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>::push_back(
      (char *)this + 64,
      &v7);
    SetEvent(*((HANDLE *)this + 15));
    *((_DWORD *)this + 34) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    ThreadId = GetThreadId(*((HANDLE *)this + 16));
    if ( GetCurrentThreadId() == ThreadId || !WaitForSingleObject(*((HANDLE *)this + 16), 0xEA60u) )
      v4 = 0;
    else
      v4 = -2147467259;
    v5 = v7;
  }
  else
  {
    v5 = 0;
    v4 = -2147024882;
  }
  if ( v5 )
    (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  return v4;
}

```

## disassembly

```asm
0x18007c9c0  mov     [rsp+arg_0], rbx
0x18007c9c5  push    rdi
0x18007c9c6  sub     rsp, 20h
0x18007c9ca  mov     rdi, rcx
0x18007c9cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007c9d4  mov     ecx, 48h ; 'H'; unsigned __int64
0x18007c9d9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007c9de  test    rax, rax
0x18007c9e1  jz      loc_18007CAAF
0x18007c9e7  mov     qword ptr [rax+18h], 0
0x18007c9ef  lea     rcx, ??_7WorkerThreadItem@ExecutionServices@Execution@@6B@; const Execution::ExecutionServices::WorkerThreadItem::`vftable'
0x18007c9f6  mov     [rax], rcx
0x18007c9f9  lea     rcx, [rdi+10h]; lpCriticalSection
0x18007c9fd  mov     qword ptr [rax+10h], 0
0x18007ca05  mov     qword ptr [rax+30h], 0
0x18007ca0d  mov     qword ptr [rax+38h], 0
0x18007ca15  mov     qword ptr [rax+20h], 0
0x18007ca1d  mov     dword ptr [rax+28h], 0
0x18007ca24  mov     dword ptr [rax+40h], 0
0x18007ca2b  mov     dword ptr [rax+44h], 1
0x18007ca32  mov     dword ptr [rax+8], 6
0x18007ca39  mov     [rsp+28h+arg_8], rax
0x18007ca3e  call    cs:__imp_EnterCriticalSection
0x18007ca44  lea     rcx, [rdi+40h]
0x18007ca48  lea     rdx, [rsp+28h+arg_8]
0x18007ca4d  call    ?push_back@?$list@V?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@@utl@@@utl@@QEAA_NAEBV?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@@Z; utl::list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>::push_back(Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem> const &)
0x18007ca52  mov     rcx, [rdi+78h]; hEvent
0x18007ca56  call    cs:__imp_SetEvent
0x18007ca5c  lea     rcx, [rdi+10h]; lpCriticalSection
0x18007ca60  mov     dword ptr [rdi+88h], 0
0x18007ca6a  call    cs:__imp_LeaveCriticalSection
0x18007ca70  mov     rcx, [rdi+80h]; Thread
0x18007ca77  call    cs:__imp_GetThreadId
0x18007ca7d  mov     ebx, eax
0x18007ca7f  call    cs:__imp_GetCurrentThreadId
0x18007ca85  cmp     eax, ebx
0x18007ca87  jz      short loc_18007CAAB
0x18007ca89  mov     rcx, [rdi+80h]; hHandle
0x18007ca90  mov     edx, 0EA60h; dwMilliseconds
0x18007ca95  call    cs:__imp_WaitForSingleObject
0x18007ca9b  test    eax, eax
0x18007ca9d  jz      short loc_18007CAAB
0x18007ca9f  mov     ebx, 80004005h
0x18007caa4  mov     rcx, [rsp+28h+arg_8]
0x18007caa9  jmp     short loc_18007CAB6
0x18007caab  xor     ebx, ebx
0x18007caad  jmp     short loc_18007CAA4
0x18007caaf  xor     ecx, ecx
0x18007cab1  mov     ebx, 8007000Eh
0x18007cab6  test    rcx, rcx
0x18007cab9  jz      short loc_18007CAC7
0x18007cabb  mov     rdx, [rcx]
0x18007cabe  mov     rax, [rdx+10h]
0x18007cac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cac7  mov     eax, ebx
0x18007cac9  mov     rbx, [rsp+28h+arg_0]
0x18007cace  add     rsp, 20h
0x18007cad2  pop     rdi
0x18007cad3  retn
```
