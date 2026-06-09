# ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags_&_

- ea: `0x1400cb06c`
- end: `0x1400cb283`
- name: `ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags_&_`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400cae78`

## callees

- `0x1400315c8`
- `0x14005145c`
- `0x1400ca840`
- `0x1400cb06c`
- `0x1400cbf40`
- `0x140132960`
- `0x140132990`
- `0x14013361c`
- `0x140133a1c`
- `0x140280f80`
- `0x14028372c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb1df`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb1ce`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb1ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb14d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb14d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cb21b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cb21b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  DWORD v6; // edi
  int i; // r14d
  char *v8; // rcx
  signed int LastError; // eax
  __int64 v10; // rbx
  signed int v11; // eax
  unsigned int v12; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v18[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v18, 0, sizeof(v18));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v18);
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  Parameter[1] = a3;
  `eh vector constructor iterator'(
    v17,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v6 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    Thread = CreateThread(0, 0, lambda_664edb7134184b7e2576fb6f05eaacc8_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v17[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v8 = (char *)v17[i];
    if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(
        a1,
        (unsigned int)LastError);
      *(_BYTE *)(a1 + 8) = 1;
      break;
    }
    hThread[i] = v8;
    ++v6;
  }
  v10 = 0;
  if ( v6 )
  {
    do
    {
      if ( ResumeThread(hThread[v10]) == -1 )
      {
        v11 = GetLastError();
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v11);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < v6 );
    WaitForMultipleObjects(v6, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, *(unsigned int *)(a1 + 28));
  v12 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v17,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v18);
  return v12;
}

```

## disassembly

```asm
0x1400cb06c  push    rbp
0x1400cb06e  push    rbx
0x1400cb06f  push    rsi
0x1400cb070  push    rdi
0x1400cb071  push    r14
0x1400cb073  push    r15
0x1400cb075  lea     rbp, [rsp-2B8h]
0x1400cb07d  sub     rsp, 3B8h
0x1400cb084  mov     rax, cs:__security_cookie
0x1400cb08b  xor     rax, rsp
0x1400cb08e  mov     [rbp+2E0h+var_40], rax
0x1400cb095  mov     rdi, r8
0x1400cb098  mov     rbx, rdx
0x1400cb09b  mov     rsi, rcx
0x1400cb09e  xor     edx, edx; Val
0x1400cb0a0  mov     r8d, 150h; Size
0x1400cb0a6  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cb0ad  call    memset_0
0x1400cb0b2  lea     r8, [rsi+60h]
0x1400cb0b6  lea     rdx, [rsi+50h]
0x1400cb0ba  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb0c1  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cb0c6  xor     eax, eax
0x1400cb0c8  xchg    al, [rsi+8]
0x1400cb0cb  xor     eax, eax
0x1400cb0cd  xchg    eax, [rsi+1Ch]
0x1400cb0d0  mov     dword ptr [rsi+20h], 0
0x1400cb0d7  mov     [rsi+38h], rbx
0x1400cb0db  mov     [rsp+3E0h+Parameter], rsi
0x1400cb0e0  mov     [rsp+3E0h+var_3A0], rdi
0x1400cb0e5  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cb0ec  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cb0f1  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cb0f8  mov     edx, 8; unsigned __int64
0x1400cb0fd  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb101  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb105  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cb10a  nop
0x1400cb10b  xor     edx, edx; Val
0x1400cb10d  mov     r8d, 100h; Size
0x1400cb113  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cb118  call    memset_0
0x1400cb11d  xor     edi, edi
0x1400cb11f  xor     r14d, r14d
0x1400cb122  cmp     r14d, [rsi+24h]
0x1400cb126  jge     loc_1400CB1BF
0x1400cb12c  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cb135  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cb13d  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cb142  lea     r8, _lambda_664edb7134184b7e2576fb6f05eaacc8____lambda_invoker_cdecl_; lpStartAddress
0x1400cb149  xor     edx, edx; dwStackSize
0x1400cb14b  xor     ecx, ecx; lpThreadAttributes
0x1400cb14d  call    cs:__imp_CreateThread
0x1400cb154  nop     dword ptr [rax+rax+00h]
0x1400cb159  mov     [rsp+3E0h+var_3B0], rax
0x1400cb15e  movsxd  r15, r14d
0x1400cb161  lea     rbx, [rbp+2E0h+var_290]
0x1400cb165  lea     rbx, [rbx+r15*8]
0x1400cb169  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cb16e  mov     rcx, rbx
0x1400cb171  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cb176  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cb17b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cb180  mov     rcx, [rbx]
0x1400cb183  lea     rax, [rcx-1]
0x1400cb187  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cb18b  ja      short loc_1400CB199
0x1400cb18d  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cb192  inc     edi
0x1400cb194  inc     r14d
0x1400cb197  jmp     short loc_1400CB122
0x1400cb199  call    cs:__imp_GetLastError
0x1400cb1a0  nop     dword ptr [rax+rax+00h]
0x1400cb1a5  test    eax, eax
0x1400cb1a7  jle     short loc_1400CB1B1
0x1400cb1a9  movzx   eax, ax
0x1400cb1ac  or      eax, 80070000h
0x1400cb1b1  mov     edx, eax
0x1400cb1b3  mov     rcx, rsi
0x1400cb1b6  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb1bb  mov     byte ptr [rsi+8], 1
0x1400cb1bf  xor     ebx, ebx
0x1400cb1c1  test    edi, edi
0x1400cb1c3  jz      short loc_1400CB227
0x1400cb1c5  or      r14d, 0FFFFFFFFh
0x1400cb1c9  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cb1ce  call    cs:__imp_ResumeThread
0x1400cb1d5  nop     dword ptr [rax+rax+00h]
0x1400cb1da  cmp     eax, r14d
0x1400cb1dd  jnz     short loc_1400CB205
0x1400cb1df  call    cs:__imp_GetLastError
0x1400cb1e6  nop     dword ptr [rax+rax+00h]
0x1400cb1eb  test    eax, eax
0x1400cb1ed  jle     short loc_1400CB1F7
0x1400cb1ef  movzx   eax, ax
0x1400cb1f2  or      eax, 80070000h
0x1400cb1f7  mov     edx, eax
0x1400cb1f9  mov     rcx, rsi
0x1400cb1fc  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb201  mov     byte ptr [rsi+8], 1
0x1400cb205  inc     ebx
0x1400cb207  cmp     ebx, edi
0x1400cb209  jb      short loc_1400CB1C9
0x1400cb20b  mov     r9d, r14d; dwMilliseconds
0x1400cb20e  mov     r8d, 1; bWaitAll
0x1400cb214  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cb219  mov     ecx, edi; nCount
0x1400cb21b  call    cs:__imp_WaitForMultipleObjects
0x1400cb222  nop     dword ptr [rax+rax+00h]
0x1400cb227  mov     edx, [rsi+1Ch]
0x1400cb22a  nop
0x1400cb22b  lea     rcx, [rbp+2E0h+var_190]
0x1400cb232  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cb237  mov     ebx, [rsi+1Ch]
0x1400cb23a  nop
0x1400cb23b  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cb242  mov     edx, 8; unsigned __int64
0x1400cb247  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb24b  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb24f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cb254  nop
0x1400cb255  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb25c  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cb261  mov     eax, ebx
0x1400cb263  mov     rcx, [rbp+2E0h+var_40]
0x1400cb26a  xor     rcx, rsp; StackCookie
0x1400cb26d  call    __security_check_cookie
0x1400cb272  add     rsp, 3B8h
0x1400cb279  pop     r15
0x1400cb27b  pop     r14
0x1400cb27d  pop     rdi
0x1400cb27e  pop     rsi
0x1400cb27f  pop     rbx
0x1400cb280  pop     rbp
0x1400cb281  retn
```
