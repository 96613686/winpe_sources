# ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbRestoreFlags_&_

- ea: `0x1400cbd18`
- end: `0x1400cbf3a`
- name: `ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbRestoreFlags_&_`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400cb28c`

## callees

- `0x1400315c8`
- `0x14005145c`
- `0x1400ca840`
- `0x1400cbd18`
- `0x1400cbf40`
- `0x140132960`
- `0x140132990`
- `0x14013361c`
- `0x140133a1c`
- `0x140280f80`
- `0x14028372c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbe4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbe93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbe4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbe93`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cbe83`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cbe83`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cbe03`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cbe03`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cbed0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cbed0`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository_____enum_VmbRestoreFlags___(
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
    Thread = CreateThread(0, 0, lambda_c545ec023c3ec298a21eb2d3e6fb5d2d_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
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
0x1400cbd18  push    rbp
0x1400cbd1a  push    rbx
0x1400cbd1b  push    rsi
0x1400cbd1c  push    rdi
0x1400cbd1d  push    r14
0x1400cbd1f  push    r15
0x1400cbd21  lea     rbp, [rsp-2B8h]
0x1400cbd29  sub     rsp, 3B8h
0x1400cbd30  mov     rax, cs:__security_cookie
0x1400cbd37  xor     rax, rsp
0x1400cbd3a  mov     [rbp+2E0h+var_40], rax
0x1400cbd41  mov     rdi, r9
0x1400cbd44  mov     rsi, r8
0x1400cbd47  mov     rbx, rdx
0x1400cbd4a  mov     r14, rcx
0x1400cbd4d  xor     edx, edx; Val
0x1400cbd4f  mov     r8d, 150h; Size
0x1400cbd55  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cbd5c  call    memset_0
0x1400cbd61  lea     r8, [r14+60h]
0x1400cbd65  lea     rdx, [r14+50h]
0x1400cbd69  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbd70  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cbd75  xor     eax, eax
0x1400cbd77  xchg    al, [r14+8]
0x1400cbd7b  xor     eax, eax
0x1400cbd7d  xchg    eax, [r14+1Ch]
0x1400cbd81  mov     dword ptr [r14+20h], 0
0x1400cbd89  mov     [r14+38h], rbx
0x1400cbd8d  mov     [rsp+3E0h+Parameter], r14
0x1400cbd92  mov     [rsp+3E0h+var_3A0], rdi
0x1400cbd97  mov     [rsp+3E0h+var_398], rsi
0x1400cbd9c  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cbda3  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cbda8  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cbdaf  mov     edx, 8; unsigned __int64
0x1400cbdb4  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cbdb8  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cbdbc  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cbdc1  nop
0x1400cbdc2  xor     edx, edx; Val
0x1400cbdc4  mov     r8d, 100h; Size
0x1400cbdca  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cbdcf  call    memset_0
0x1400cbdd4  xor     edi, edi
0x1400cbdd6  xor     esi, esi
0x1400cbdd8  cmp     esi, [r14+24h]
0x1400cbddc  jge     loc_1400CBE75
0x1400cbde2  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cbdeb  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cbdf3  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cbdf8  lea     r8, _lambda_c545ec023c3ec298a21eb2d3e6fb5d2d____lambda_invoker_cdecl_; lpStartAddress
0x1400cbdff  xor     edx, edx; dwStackSize
0x1400cbe01  xor     ecx, ecx; lpThreadAttributes
0x1400cbe03  call    cs:__imp_CreateThread
0x1400cbe0a  nop     dword ptr [rax+rax+00h]
0x1400cbe0f  mov     [rsp+3E0h+var_3B0], rax
0x1400cbe14  movsxd  r15, esi
0x1400cbe17  lea     rbx, [rbp+2E0h+var_290]
0x1400cbe1b  lea     rbx, [rbx+r15*8]
0x1400cbe1f  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cbe24  mov     rcx, rbx
0x1400cbe27  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cbe2c  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cbe31  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cbe36  mov     rcx, [rbx]
0x1400cbe39  lea     rax, [rcx-1]
0x1400cbe3d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cbe41  ja      short loc_1400CBE4E
0x1400cbe43  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cbe48  inc     edi
0x1400cbe4a  inc     esi
0x1400cbe4c  jmp     short loc_1400CBDD8
0x1400cbe4e  call    cs:__imp_GetLastError
0x1400cbe55  nop     dword ptr [rax+rax+00h]
0x1400cbe5a  test    eax, eax
0x1400cbe5c  jle     short loc_1400CBE66
0x1400cbe5e  movzx   eax, ax
0x1400cbe61  or      eax, 80070000h
0x1400cbe66  mov     edx, eax
0x1400cbe68  mov     rcx, r14
0x1400cbe6b  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cbe70  mov     byte ptr [r14+8], 1
0x1400cbe75  xor     ebx, ebx
0x1400cbe77  test    edi, edi
0x1400cbe79  jz      short loc_1400CBEDC
0x1400cbe7b  or      esi, 0FFFFFFFFh
0x1400cbe7e  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cbe83  call    cs:__imp_ResumeThread
0x1400cbe8a  nop     dword ptr [rax+rax+00h]
0x1400cbe8f  cmp     eax, esi
0x1400cbe91  jnz     short loc_1400CBEBA
0x1400cbe93  call    cs:__imp_GetLastError
0x1400cbe9a  nop     dword ptr [rax+rax+00h]
0x1400cbe9f  test    eax, eax
0x1400cbea1  jle     short loc_1400CBEAB
0x1400cbea3  movzx   eax, ax
0x1400cbea6  or      eax, 80070000h
0x1400cbeab  mov     edx, eax
0x1400cbead  mov     rcx, r14
0x1400cbeb0  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cbeb5  mov     byte ptr [r14+8], 1
0x1400cbeba  inc     ebx
0x1400cbebc  cmp     ebx, edi
0x1400cbebe  jb      short loc_1400CBE7E
0x1400cbec0  mov     r9d, esi; dwMilliseconds
0x1400cbec3  mov     r8d, 1; bWaitAll
0x1400cbec9  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cbece  mov     ecx, edi; nCount
0x1400cbed0  call    cs:__imp_WaitForMultipleObjects
0x1400cbed7  nop     dword ptr [rax+rax+00h]
0x1400cbedc  mov     edx, [r14+1Ch]
0x1400cbee0  nop
0x1400cbee1  lea     rcx, [rbp+2E0h+var_190]
0x1400cbee8  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cbeed  mov     ebx, [r14+1Ch]
0x1400cbef1  nop
0x1400cbef2  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cbef9  mov     edx, 8; unsigned __int64
0x1400cbefe  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cbf02  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cbf06  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cbf0b  nop
0x1400cbf0c  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbf13  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cbf18  mov     eax, ebx
0x1400cbf1a  mov     rcx, [rbp+2E0h+var_40]
0x1400cbf21  xor     rcx, rsp; StackCookie
0x1400cbf24  call    __security_check_cookie
0x1400cbf29  add     rsp, 3B8h
0x1400cbf30  pop     r15
0x1400cbf32  pop     r14
0x1400cbf34  pop     rdi
0x1400cbf35  pop     rsi
0x1400cbf36  pop     rbx
0x1400cbf37  pop     rbp
0x1400cbf38  retn
```
