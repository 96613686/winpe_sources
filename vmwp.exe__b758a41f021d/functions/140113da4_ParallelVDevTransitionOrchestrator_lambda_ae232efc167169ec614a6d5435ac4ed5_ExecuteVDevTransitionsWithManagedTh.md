# ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags_&_

- ea: `0x140113da4`
- end: `0x140113fbc`
- name: `ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags_&_`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140112cd4`

## callees

- `0x14003d144`
- `0x14004f6dc`
- `0x1401134d8`
- `0x140113da4`
- `0x1401141f0`
- `0x14011423c`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011f6fc`
- `0x14011fafc`
- `0x140287308`
- `0x140289ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113f18`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140113f07`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140113f07`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140113e86`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140113e86`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140113f54`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140113f54`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  DWORD v6; // edi
  int i; // r14d
  ULONG (__stdcall *v8)(PVOID); // rax
  char *v9; // rcx
  signed int LastError; // eax
  __int64 v11; // rbx
  signed int v12; // eax
  unsigned int v13; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v18[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v19[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v19, 0, sizeof(v19));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v19);
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  Parameter[1] = a3;
  `eh vector constructor iterator'(
    v18,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v6 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    v8 = (ULONG (__stdcall *)(PVOID))lambda_8b7c7e0145f9cf0c895a2ec418a59a8b_::operator_unsigned_long____cdecl___void___();
    Thread = CreateThread(0, 0, v8, Parameter, 4u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v18[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v9 = (char *)v18[i];
    if ( (unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
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
    hThread[i] = v9;
    ++v6;
  }
  v11 = 0;
  if ( v6 )
  {
    do
    {
      if ( ResumeThread(hThread[v11]) == -1 )
      {
        v12 = GetLastError();
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v12);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (unsigned int)v11 < v6 );
    WaitForMultipleObjects(v6, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19, *(unsigned int *)(a1 + 28));
  v13 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v18,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v19);
  return v13;
}

```

## disassembly

```asm
0x140113da4  push    rbp
0x140113da6  push    rbx
0x140113da7  push    rsi
0x140113da8  push    rdi
0x140113da9  push    r14
0x140113dab  push    r15
0x140113dad  lea     rbp, [rsp-2B8h]
0x140113db5  sub     rsp, 3B8h
0x140113dbc  mov     rax, cs:__security_cookie
0x140113dc3  xor     rax, rsp
0x140113dc6  mov     [rbp+2E0h+var_40], rax
0x140113dcd  mov     rdi, r8
0x140113dd0  mov     rbx, rdx
0x140113dd3  mov     rsi, rcx
0x140113dd6  xor     edx, edx; Val
0x140113dd8  mov     r8d, 150h; Size
0x140113dde  lea     rcx, [rbp+2E0h+var_190]; void *
0x140113de5  call    memset_0
0x140113dea  lea     r8, [rsi+60h]
0x140113dee  lea     rdx, [rsi+50h]
0x140113df2  lea     rcx, [rbp+2E0h+var_190]; this
0x140113df9  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x140113dfe  xor     eax, eax
0x140113e00  xchg    al, [rsi+8]
0x140113e03  xor     eax, eax
0x140113e05  xchg    eax, [rsi+1Ch]
0x140113e08  mov     dword ptr [rsi+20h], 0
0x140113e0f  mov     [rsi+38h], rbx
0x140113e13  mov     [rsp+3E0h+Parameter], rsi
0x140113e18  mov     [rsp+3E0h+var_3A0], rdi
0x140113e1d  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x140113e24  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x140113e29  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x140113e30  mov     edx, 8; unsigned __int64
0x140113e35  lea     r8d, [rdx+18h]; unsigned __int64
0x140113e39  lea     rcx, [rbp+2E0h+var_290]; void *
0x140113e3d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140113e42  nop
0x140113e43  xor     edx, edx; Val
0x140113e45  mov     r8d, 100h; Size
0x140113e4b  lea     rcx, [rsp+3E0h+hThread]; void *
0x140113e50  call    memset_0
0x140113e55  xor     edi, edi
0x140113e57  xor     r14d, r14d
0x140113e5a  cmp     r14d, [rsi+24h]
0x140113e5e  jge     loc_140113EF8
0x140113e64  call    _lambda_8b7c7e0145f9cf0c895a2ec418a59a8b___operator_unsigned_long____cdecl___void___
0x140113e69  mov     r8, rax; lpStartAddress
0x140113e6c  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x140113e75  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x140113e7d  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x140113e82  xor     edx, edx; dwStackSize
0x140113e84  xor     ecx, ecx; lpThreadAttributes
0x140113e86  call    cs:__imp_CreateThread
0x140113e8d  nop     dword ptr [rax+rax+00h]
0x140113e92  mov     [rsp+3E0h+var_3B0], rax
0x140113e97  movsxd  r15, r14d
0x140113e9a  lea     rbx, [rbp+2E0h+var_290]
0x140113e9e  lea     rbx, [rbx+r15*8]
0x140113ea2  lea     rdx, [rsp+3E0h+var_3B0]
0x140113ea7  mov     rcx, rbx
0x140113eaa  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140113eaf  lea     rcx, [rsp+3E0h+var_3B0]
0x140113eb4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140113eb9  mov     rcx, [rbx]
0x140113ebc  lea     rax, [rcx-1]
0x140113ec0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140113ec4  ja      short loc_140113ED2
0x140113ec6  mov     [rsp+r15*8+3E0h+hThread], rcx
0x140113ecb  inc     edi
0x140113ecd  inc     r14d
0x140113ed0  jmp     short loc_140113E5A
0x140113ed2  call    cs:__imp_GetLastError
0x140113ed9  nop     dword ptr [rax+rax+00h]
0x140113ede  test    eax, eax
0x140113ee0  jle     short loc_140113EEA
0x140113ee2  movzx   eax, ax
0x140113ee5  or      eax, 80070000h
0x140113eea  mov     edx, eax
0x140113eec  mov     rcx, rsi
0x140113eef  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140113ef4  mov     byte ptr [rsi+8], 1
0x140113ef8  xor     ebx, ebx
0x140113efa  test    edi, edi
0x140113efc  jz      short loc_140113F60
0x140113efe  or      r14d, 0FFFFFFFFh
0x140113f02  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x140113f07  call    cs:__imp_ResumeThread
0x140113f0e  nop     dword ptr [rax+rax+00h]
0x140113f13  cmp     eax, r14d
0x140113f16  jnz     short loc_140113F3E
0x140113f18  call    cs:__imp_GetLastError
0x140113f1f  nop     dword ptr [rax+rax+00h]
0x140113f24  test    eax, eax
0x140113f26  jle     short loc_140113F30
0x140113f28  movzx   eax, ax
0x140113f2b  or      eax, 80070000h
0x140113f30  mov     edx, eax
0x140113f32  mov     rcx, rsi
0x140113f35  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140113f3a  mov     byte ptr [rsi+8], 1
0x140113f3e  inc     ebx
0x140113f40  cmp     ebx, edi
0x140113f42  jb      short loc_140113F02
0x140113f44  mov     r9d, r14d; dwMilliseconds
0x140113f47  mov     r8d, 1; bWaitAll
0x140113f4d  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x140113f52  mov     ecx, edi; nCount
0x140113f54  call    cs:__imp_WaitForMultipleObjects
0x140113f5b  nop     dword ptr [rax+rax+00h]
0x140113f60  mov     edx, [rsi+1Ch]
0x140113f63  nop
0x140113f64  lea     rcx, [rbp+2E0h+var_190]
0x140113f6b  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140113f70  mov     ebx, [rsi+1Ch]
0x140113f73  nop
0x140113f74  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x140113f7b  mov     edx, 8; unsigned __int64
0x140113f80  lea     r8d, [rdx+18h]; unsigned __int64
0x140113f84  lea     rcx, [rbp+2E0h+var_290]; void *
0x140113f88  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140113f8d  nop
0x140113f8e  lea     rcx, [rbp+2E0h+var_190]; this
0x140113f95  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x140113f9a  mov     eax, ebx
0x140113f9c  mov     rcx, [rbp+2E0h+var_40]
0x140113fa3  xor     rcx, rsp; StackCookie
0x140113fa6  call    __security_check_cookie
0x140113fab  add     rsp, 3B8h
0x140113fb2  pop     r15
0x140113fb4  pop     r14
0x140113fb6  pop     rdi
0x140113fb7  pop     rsi
0x140113fb8  pop     rbx
0x140113fb9  pop     rbp
0x140113fba  retn
```
