# ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags_&_

- ea: `0x1400cb494`
- end: `0x1400cb6ab`
- name: `ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags_&_`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400ca420`

## callees

- `0x1400315c8`
- `0x14005145c`
- `0x1400ca840`
- `0x1400cb494`
- `0x1400cbf40`
- `0x140132960`
- `0x140132990`
- `0x14013361c`
- `0x140133a1c`
- `0x140280f80`
- `0x14028372c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb607`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb5f6`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb5f6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb575`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb575`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cb643`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cb643`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags___(
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
    Thread = CreateThread(0, 0, lambda_7eac78071b17182a680488bd3565b140_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
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
0x1400cb494  push    rbp
0x1400cb496  push    rbx
0x1400cb497  push    rsi
0x1400cb498  push    rdi
0x1400cb499  push    r14
0x1400cb49b  push    r15
0x1400cb49d  lea     rbp, [rsp-2B8h]
0x1400cb4a5  sub     rsp, 3B8h
0x1400cb4ac  mov     rax, cs:__security_cookie
0x1400cb4b3  xor     rax, rsp
0x1400cb4b6  mov     [rbp+2E0h+var_40], rax
0x1400cb4bd  mov     rdi, r8
0x1400cb4c0  mov     rbx, rdx
0x1400cb4c3  mov     rsi, rcx
0x1400cb4c6  xor     edx, edx; Val
0x1400cb4c8  mov     r8d, 150h; Size
0x1400cb4ce  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cb4d5  call    memset_0
0x1400cb4da  lea     r8, [rsi+60h]
0x1400cb4de  lea     rdx, [rsi+50h]
0x1400cb4e2  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb4e9  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cb4ee  xor     eax, eax
0x1400cb4f0  xchg    al, [rsi+8]
0x1400cb4f3  xor     eax, eax
0x1400cb4f5  xchg    eax, [rsi+1Ch]
0x1400cb4f8  mov     dword ptr [rsi+20h], 0
0x1400cb4ff  mov     [rsi+38h], rbx
0x1400cb503  mov     [rsp+3E0h+Parameter], rsi
0x1400cb508  mov     [rsp+3E0h+var_3A0], rdi
0x1400cb50d  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cb514  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cb519  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cb520  mov     edx, 8; unsigned __int64
0x1400cb525  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb529  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb52d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cb532  nop
0x1400cb533  xor     edx, edx; Val
0x1400cb535  mov     r8d, 100h; Size
0x1400cb53b  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cb540  call    memset_0
0x1400cb545  xor     edi, edi
0x1400cb547  xor     r14d, r14d
0x1400cb54a  cmp     r14d, [rsi+24h]
0x1400cb54e  jge     loc_1400CB5E7
0x1400cb554  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cb55d  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cb565  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cb56a  lea     r8, _lambda_7eac78071b17182a680488bd3565b140____lambda_invoker_cdecl_; lpStartAddress
0x1400cb571  xor     edx, edx; dwStackSize
0x1400cb573  xor     ecx, ecx; lpThreadAttributes
0x1400cb575  call    cs:__imp_CreateThread
0x1400cb57c  nop     dword ptr [rax+rax+00h]
0x1400cb581  mov     [rsp+3E0h+var_3B0], rax
0x1400cb586  movsxd  r15, r14d
0x1400cb589  lea     rbx, [rbp+2E0h+var_290]
0x1400cb58d  lea     rbx, [rbx+r15*8]
0x1400cb591  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cb596  mov     rcx, rbx
0x1400cb599  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cb59e  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cb5a3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cb5a8  mov     rcx, [rbx]
0x1400cb5ab  lea     rax, [rcx-1]
0x1400cb5af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cb5b3  ja      short loc_1400CB5C1
0x1400cb5b5  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cb5ba  inc     edi
0x1400cb5bc  inc     r14d
0x1400cb5bf  jmp     short loc_1400CB54A
0x1400cb5c1  call    cs:__imp_GetLastError
0x1400cb5c8  nop     dword ptr [rax+rax+00h]
0x1400cb5cd  test    eax, eax
0x1400cb5cf  jle     short loc_1400CB5D9
0x1400cb5d1  movzx   eax, ax
0x1400cb5d4  or      eax, 80070000h
0x1400cb5d9  mov     edx, eax
0x1400cb5db  mov     rcx, rsi
0x1400cb5de  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb5e3  mov     byte ptr [rsi+8], 1
0x1400cb5e7  xor     ebx, ebx
0x1400cb5e9  test    edi, edi
0x1400cb5eb  jz      short loc_1400CB64F
0x1400cb5ed  or      r14d, 0FFFFFFFFh
0x1400cb5f1  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cb5f6  call    cs:__imp_ResumeThread
0x1400cb5fd  nop     dword ptr [rax+rax+00h]
0x1400cb602  cmp     eax, r14d
0x1400cb605  jnz     short loc_1400CB62D
0x1400cb607  call    cs:__imp_GetLastError
0x1400cb60e  nop     dword ptr [rax+rax+00h]
0x1400cb613  test    eax, eax
0x1400cb615  jle     short loc_1400CB61F
0x1400cb617  movzx   eax, ax
0x1400cb61a  or      eax, 80070000h
0x1400cb61f  mov     edx, eax
0x1400cb621  mov     rcx, rsi
0x1400cb624  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb629  mov     byte ptr [rsi+8], 1
0x1400cb62d  inc     ebx
0x1400cb62f  cmp     ebx, edi
0x1400cb631  jb      short loc_1400CB5F1
0x1400cb633  mov     r9d, r14d; dwMilliseconds
0x1400cb636  mov     r8d, 1; bWaitAll
0x1400cb63c  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cb641  mov     ecx, edi; nCount
0x1400cb643  call    cs:__imp_WaitForMultipleObjects
0x1400cb64a  nop     dword ptr [rax+rax+00h]
0x1400cb64f  mov     edx, [rsi+1Ch]
0x1400cb652  nop
0x1400cb653  lea     rcx, [rbp+2E0h+var_190]
0x1400cb65a  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cb65f  mov     ebx, [rsi+1Ch]
0x1400cb662  nop
0x1400cb663  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cb66a  mov     edx, 8; unsigned __int64
0x1400cb66f  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb673  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb677  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cb67c  nop
0x1400cb67d  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb684  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cb689  mov     eax, ebx
0x1400cb68b  mov     rcx, [rbp+2E0h+var_40]
0x1400cb692  xor     rcx, rsp; StackCookie
0x1400cb695  call    __security_check_cookie
0x1400cb69a  add     rsp, 3B8h
0x1400cb6a1  pop     r15
0x1400cb6a3  pop     r14
0x1400cb6a5  pop     rdi
0x1400cb6a6  pop     rsi
0x1400cb6a7  pop     rbx
0x1400cb6a8  pop     rbp
0x1400cb6a9  retn
```
