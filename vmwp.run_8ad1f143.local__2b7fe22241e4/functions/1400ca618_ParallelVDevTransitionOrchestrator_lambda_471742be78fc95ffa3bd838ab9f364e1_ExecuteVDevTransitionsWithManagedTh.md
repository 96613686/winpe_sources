# ParallelVDevTransitionOrchestrator__lambda_471742be78fc95ffa3bd838ab9f364e1___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbSaveFlags_&_

- ea: `0x1400ca618`
- end: `0x1400ca83a`
- name: `ParallelVDevTransitionOrchestrator__lambda_471742be78fc95ffa3bd838ab9f364e1___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbSaveFlags_&_`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400ca87c`

## callees

- `0x1400315c8`
- `0x14005145c`
- `0x1400ca618`
- `0x1400ca840`
- `0x1400cbf40`
- `0x140132960`
- `0x140132990`
- `0x14013361c`
- `0x140133a1c`
- `0x140280f80`
- `0x14028372c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ca74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ca793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ca74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ca793`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400ca783`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400ca783`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400ca703`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400ca703`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400ca7d0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400ca7d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_471742be78fc95ffa3bd838ab9f364e1___::ExecuteVDevTransitionsWithManagedThreads_VmRepository_____enum_VmbSaveFlags___(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  DWORD v8; // edi
  int i; // esi
  char *v10; // rcx
  signed int LastError; // eax
  __int64 v12; // rbx
  signed int v13; // eax
  unsigned int v14; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v20[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v20, 0, sizeof(v20));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v20);
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  Parameter[1] = a4;
  Parameter[2] = a3;
  `eh vector constructor iterator'(
    v19,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v8 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    Thread = CreateThread(0, 0, lambda_1e8ca78bb1a037ad4a3196a6ee977c51_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v19[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v10 = (char *)v19[i];
    if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
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
    hThread[i] = v10;
    ++v8;
  }
  v12 = 0;
  if ( v8 )
  {
    do
    {
      if ( ResumeThread(hThread[v12]) == -1 )
      {
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v13);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < v8 );
    WaitForMultipleObjects(v8, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20, *(unsigned int *)(a1 + 28));
  v14 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v19,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v20);
  return v14;
}

```

## disassembly

```asm
0x1400ca618  push    rbp
0x1400ca61a  push    rbx
0x1400ca61b  push    rsi
0x1400ca61c  push    rdi
0x1400ca61d  push    r14
0x1400ca61f  push    r15
0x1400ca621  lea     rbp, [rsp-2B8h]
0x1400ca629  sub     rsp, 3B8h
0x1400ca630  mov     rax, cs:__security_cookie
0x1400ca637  xor     rax, rsp
0x1400ca63a  mov     [rbp+2E0h+var_40], rax
0x1400ca641  mov     rdi, r9
0x1400ca644  mov     rsi, r8
0x1400ca647  mov     rbx, rdx
0x1400ca64a  mov     r14, rcx
0x1400ca64d  xor     edx, edx; Val
0x1400ca64f  mov     r8d, 150h; Size
0x1400ca655  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400ca65c  call    memset_0
0x1400ca661  lea     r8, [r14+60h]
0x1400ca665  lea     rdx, [r14+50h]
0x1400ca669  lea     rcx, [rbp+2E0h+var_190]; this
0x1400ca670  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400ca675  xor     eax, eax
0x1400ca677  xchg    al, [r14+8]
0x1400ca67b  xor     eax, eax
0x1400ca67d  xchg    eax, [r14+1Ch]
0x1400ca681  mov     dword ptr [r14+20h], 0
0x1400ca689  mov     [r14+38h], rbx
0x1400ca68d  mov     [rsp+3E0h+Parameter], r14
0x1400ca692  mov     [rsp+3E0h+var_3A0], rdi
0x1400ca697  mov     [rsp+3E0h+var_398], rsi
0x1400ca69c  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400ca6a3  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400ca6a8  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400ca6af  mov     edx, 8; unsigned __int64
0x1400ca6b4  lea     r8d, [rdx+18h]; unsigned __int64
0x1400ca6b8  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400ca6bc  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400ca6c1  nop
0x1400ca6c2  xor     edx, edx; Val
0x1400ca6c4  mov     r8d, 100h; Size
0x1400ca6ca  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400ca6cf  call    memset_0
0x1400ca6d4  xor     edi, edi
0x1400ca6d6  xor     esi, esi
0x1400ca6d8  cmp     esi, [r14+24h]
0x1400ca6dc  jge     loc_1400CA775
0x1400ca6e2  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400ca6eb  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400ca6f3  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400ca6f8  lea     r8, _lambda_1e8ca78bb1a037ad4a3196a6ee977c51____lambda_invoker_cdecl_; lpStartAddress
0x1400ca6ff  xor     edx, edx; dwStackSize
0x1400ca701  xor     ecx, ecx; lpThreadAttributes
0x1400ca703  call    cs:__imp_CreateThread
0x1400ca70a  nop     dword ptr [rax+rax+00h]
0x1400ca70f  mov     [rsp+3E0h+var_3B0], rax
0x1400ca714  movsxd  r15, esi
0x1400ca717  lea     rbx, [rbp+2E0h+var_290]
0x1400ca71b  lea     rbx, [rbx+r15*8]
0x1400ca71f  lea     rdx, [rsp+3E0h+var_3B0]
0x1400ca724  mov     rcx, rbx
0x1400ca727  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400ca72c  lea     rcx, [rsp+3E0h+var_3B0]
0x1400ca731  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400ca736  mov     rcx, [rbx]
0x1400ca739  lea     rax, [rcx-1]
0x1400ca73d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400ca741  ja      short loc_1400CA74E
0x1400ca743  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400ca748  inc     edi
0x1400ca74a  inc     esi
0x1400ca74c  jmp     short loc_1400CA6D8
0x1400ca74e  call    cs:__imp_GetLastError
0x1400ca755  nop     dword ptr [rax+rax+00h]
0x1400ca75a  test    eax, eax
0x1400ca75c  jle     short loc_1400CA766
0x1400ca75e  movzx   eax, ax
0x1400ca761  or      eax, 80070000h
0x1400ca766  mov     edx, eax
0x1400ca768  mov     rcx, r14
0x1400ca76b  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400ca770  mov     byte ptr [r14+8], 1
0x1400ca775  xor     ebx, ebx
0x1400ca777  test    edi, edi
0x1400ca779  jz      short loc_1400CA7DC
0x1400ca77b  or      esi, 0FFFFFFFFh
0x1400ca77e  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400ca783  call    cs:__imp_ResumeThread
0x1400ca78a  nop     dword ptr [rax+rax+00h]
0x1400ca78f  cmp     eax, esi
0x1400ca791  jnz     short loc_1400CA7BA
0x1400ca793  call    cs:__imp_GetLastError
0x1400ca79a  nop     dword ptr [rax+rax+00h]
0x1400ca79f  test    eax, eax
0x1400ca7a1  jle     short loc_1400CA7AB
0x1400ca7a3  movzx   eax, ax
0x1400ca7a6  or      eax, 80070000h
0x1400ca7ab  mov     edx, eax
0x1400ca7ad  mov     rcx, r14
0x1400ca7b0  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400ca7b5  mov     byte ptr [r14+8], 1
0x1400ca7ba  inc     ebx
0x1400ca7bc  cmp     ebx, edi
0x1400ca7be  jb      short loc_1400CA77E
0x1400ca7c0  mov     r9d, esi; dwMilliseconds
0x1400ca7c3  mov     r8d, 1; bWaitAll
0x1400ca7c9  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400ca7ce  mov     ecx, edi; nCount
0x1400ca7d0  call    cs:__imp_WaitForMultipleObjects
0x1400ca7d7  nop     dword ptr [rax+rax+00h]
0x1400ca7dc  mov     edx, [r14+1Ch]
0x1400ca7e0  nop
0x1400ca7e1  lea     rcx, [rbp+2E0h+var_190]
0x1400ca7e8  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400ca7ed  mov     ebx, [r14+1Ch]
0x1400ca7f1  nop
0x1400ca7f2  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400ca7f9  mov     edx, 8; unsigned __int64
0x1400ca7fe  lea     r8d, [rdx+18h]; unsigned __int64
0x1400ca802  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400ca806  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400ca80b  nop
0x1400ca80c  lea     rcx, [rbp+2E0h+var_190]; this
0x1400ca813  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400ca818  mov     eax, ebx
0x1400ca81a  mov     rcx, [rbp+2E0h+var_40]
0x1400ca821  xor     rcx, rsp; StackCookie
0x1400ca824  call    __security_check_cookie
0x1400ca829  add     rsp, 3B8h
0x1400ca830  pop     r15
0x1400ca832  pop     r14
0x1400ca834  pop     rdi
0x1400ca835  pop     rsi
0x1400ca836  pop     rbx
0x1400ca837  pop     rbp
0x1400ca838  retn
```
