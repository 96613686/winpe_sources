# ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__

- ea: `0x1400cb888`
- end: `0x1400cba97`
- name: `ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400cb6b4`

## callees

- `0x1400315c8`
- `0x14005145c`
- `0x1400ca840`
- `0x1400cb888`
- `0x1400cbf40`
- `0x140132960`
- `0x140132990`
- `0x14013361c`
- `0x140133a1c`
- `0x140280f80`
- `0x14028372c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb9f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb9f3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb9e2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb9e2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb961`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb961`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cba2f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cba2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__(
        __int64 a1,
        __int64 a2)
{
  DWORD v4; // esi
  int i; // r14d
  char *v6; // rcx
  signed int LastError; // eax
  __int64 v8; // rbx
  signed int v9; // eax
  unsigned int v10; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v16[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v16, 0, sizeof(v16));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v16);
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  `eh vector constructor iterator'(
    v15,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v4 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    Thread = CreateThread(0, 0, lambda_0d9a039c5a7ca7635e2c060b7202f9f6_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v15[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v6 = (char *)v15[i];
    if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
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
    hThread[i] = v6;
    ++v4;
  }
  v8 = 0;
  if ( v4 )
  {
    do
    {
      if ( ResumeThread(hThread[v8]) == -1 )
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v9);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < v4 );
    WaitForMultipleObjects(v4, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16, *(unsigned int *)(a1 + 28));
  v10 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v15,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v16);
  return v10;
}

```

## disassembly

```asm
0x1400cb888  push    rbp
0x1400cb88a  push    rbx
0x1400cb88b  push    rsi
0x1400cb88c  push    rdi
0x1400cb88d  push    r14
0x1400cb88f  push    r15
0x1400cb891  lea     rbp, [rsp-2B8h]
0x1400cb899  sub     rsp, 3B8h
0x1400cb8a0  mov     rax, cs:__security_cookie
0x1400cb8a7  xor     rax, rsp
0x1400cb8aa  mov     [rbp+2E0h+var_40], rax
0x1400cb8b1  mov     rbx, rdx
0x1400cb8b4  mov     rdi, rcx
0x1400cb8b7  xor     edx, edx; Val
0x1400cb8b9  mov     r8d, 150h; Size
0x1400cb8bf  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cb8c6  call    memset_0
0x1400cb8cb  lea     r8, [rdi+60h]
0x1400cb8cf  lea     rdx, [rdi+50h]
0x1400cb8d3  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb8da  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cb8df  xor     eax, eax
0x1400cb8e1  xchg    al, [rdi+8]
0x1400cb8e4  xor     eax, eax
0x1400cb8e6  xchg    eax, [rdi+1Ch]
0x1400cb8e9  mov     dword ptr [rdi+20h], 0
0x1400cb8f0  mov     [rdi+38h], rbx
0x1400cb8f4  mov     [rsp+3E0h+Parameter], rdi
0x1400cb8f9  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cb900  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cb905  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cb90c  mov     edx, 8; unsigned __int64
0x1400cb911  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb915  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb919  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cb91e  nop
0x1400cb91f  xor     edx, edx; Val
0x1400cb921  mov     r8d, 100h; Size
0x1400cb927  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cb92c  call    memset_0
0x1400cb931  xor     esi, esi
0x1400cb933  xor     r14d, r14d
0x1400cb936  cmp     r14d, [rdi+24h]
0x1400cb93a  jge     loc_1400CB9D3
0x1400cb940  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cb949  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cb951  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cb956  lea     r8, _lambda_0d9a039c5a7ca7635e2c060b7202f9f6____lambda_invoker_cdecl_; lpStartAddress
0x1400cb95d  xor     edx, edx; dwStackSize
0x1400cb95f  xor     ecx, ecx; lpThreadAttributes
0x1400cb961  call    cs:__imp_CreateThread
0x1400cb968  nop     dword ptr [rax+rax+00h]
0x1400cb96d  mov     [rsp+3E0h+var_3B0], rax
0x1400cb972  movsxd  r15, r14d
0x1400cb975  lea     rbx, [rbp+2E0h+var_290]
0x1400cb979  lea     rbx, [rbx+r15*8]
0x1400cb97d  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cb982  mov     rcx, rbx
0x1400cb985  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cb98a  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cb98f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cb994  mov     rcx, [rbx]
0x1400cb997  lea     rax, [rcx-1]
0x1400cb99b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cb99f  ja      short loc_1400CB9AD
0x1400cb9a1  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cb9a6  inc     esi
0x1400cb9a8  inc     r14d
0x1400cb9ab  jmp     short loc_1400CB936
0x1400cb9ad  call    cs:__imp_GetLastError
0x1400cb9b4  nop     dword ptr [rax+rax+00h]
0x1400cb9b9  test    eax, eax
0x1400cb9bb  jle     short loc_1400CB9C5
0x1400cb9bd  movzx   eax, ax
0x1400cb9c0  or      eax, 80070000h
0x1400cb9c5  mov     edx, eax
0x1400cb9c7  mov     rcx, rdi
0x1400cb9ca  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb9cf  mov     byte ptr [rdi+8], 1
0x1400cb9d3  xor     ebx, ebx
0x1400cb9d5  test    esi, esi
0x1400cb9d7  jz      short loc_1400CBA3B
0x1400cb9d9  or      r14d, 0FFFFFFFFh
0x1400cb9dd  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cb9e2  call    cs:__imp_ResumeThread
0x1400cb9e9  nop     dword ptr [rax+rax+00h]
0x1400cb9ee  cmp     eax, r14d
0x1400cb9f1  jnz     short loc_1400CBA19
0x1400cb9f3  call    cs:__imp_GetLastError
0x1400cb9fa  nop     dword ptr [rax+rax+00h]
0x1400cb9ff  test    eax, eax
0x1400cba01  jle     short loc_1400CBA0B
0x1400cba03  movzx   eax, ax
0x1400cba06  or      eax, 80070000h
0x1400cba0b  mov     edx, eax
0x1400cba0d  mov     rcx, rdi
0x1400cba10  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cba15  mov     byte ptr [rdi+8], 1
0x1400cba19  inc     ebx
0x1400cba1b  cmp     ebx, esi
0x1400cba1d  jb      short loc_1400CB9DD
0x1400cba1f  mov     r9d, r14d; dwMilliseconds
0x1400cba22  mov     r8d, 1; bWaitAll
0x1400cba28  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cba2d  mov     ecx, esi; nCount
0x1400cba2f  call    cs:__imp_WaitForMultipleObjects
0x1400cba36  nop     dword ptr [rax+rax+00h]
0x1400cba3b  mov     edx, [rdi+1Ch]
0x1400cba3e  nop
0x1400cba3f  lea     rcx, [rbp+2E0h+var_190]
0x1400cba46  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cba4b  mov     ebx, [rdi+1Ch]
0x1400cba4e  nop
0x1400cba4f  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cba56  mov     edx, 8; unsigned __int64
0x1400cba5b  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cba5f  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cba63  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cba68  nop
0x1400cba69  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cba70  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cba75  mov     eax, ebx
0x1400cba77  mov     rcx, [rbp+2E0h+var_40]
0x1400cba7e  xor     rcx, rsp; StackCookie
0x1400cba81  call    __security_check_cookie
0x1400cba86  add     rsp, 3B8h
0x1400cba8d  pop     r15
0x1400cba8f  pop     r14
0x1400cba91  pop     rdi
0x1400cba92  pop     rsi
0x1400cba93  pop     rbx
0x1400cba94  pop     rbp
0x1400cba95  retn
```
