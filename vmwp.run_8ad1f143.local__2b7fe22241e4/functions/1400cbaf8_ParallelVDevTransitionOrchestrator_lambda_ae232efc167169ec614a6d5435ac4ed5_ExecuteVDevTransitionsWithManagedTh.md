# ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags_&_

- ea: `0x1400cbaf8`
- end: `0x1400cbd0f`
- name: `ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags_&_`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400caa88`

## callees

- `0x1400315c8`
- `0x14005145c`
- `0x1400ca840`
- `0x1400cbaf8`
- `0x1400cbf40`
- `0x140132960`
- `0x140132990`
- `0x14013361c`
- `0x140133a1c`
- `0x140280f80`
- `0x14028372c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbc6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbc6b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cbc5a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cbc5a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cbbd9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cbbd9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cbca7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cbca7`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags___(
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
    Thread = CreateThread(0, 0, lambda_1beeb3f5b12b17edc670c5c4fb163e90_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
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
0x1400cbaf8  push    rbp
0x1400cbafa  push    rbx
0x1400cbafb  push    rsi
0x1400cbafc  push    rdi
0x1400cbafd  push    r14
0x1400cbaff  push    r15
0x1400cbb01  lea     rbp, [rsp-2B8h]
0x1400cbb09  sub     rsp, 3B8h
0x1400cbb10  mov     rax, cs:__security_cookie
0x1400cbb17  xor     rax, rsp
0x1400cbb1a  mov     [rbp+2E0h+var_40], rax
0x1400cbb21  mov     rdi, r8
0x1400cbb24  mov     rbx, rdx
0x1400cbb27  mov     rsi, rcx
0x1400cbb2a  xor     edx, edx; Val
0x1400cbb2c  mov     r8d, 150h; Size
0x1400cbb32  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cbb39  call    memset_0
0x1400cbb3e  lea     r8, [rsi+60h]
0x1400cbb42  lea     rdx, [rsi+50h]
0x1400cbb46  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbb4d  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cbb52  xor     eax, eax
0x1400cbb54  xchg    al, [rsi+8]
0x1400cbb57  xor     eax, eax
0x1400cbb59  xchg    eax, [rsi+1Ch]
0x1400cbb5c  mov     dword ptr [rsi+20h], 0
0x1400cbb63  mov     [rsi+38h], rbx
0x1400cbb67  mov     [rsp+3E0h+Parameter], rsi
0x1400cbb6c  mov     [rsp+3E0h+var_3A0], rdi
0x1400cbb71  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cbb78  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cbb7d  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cbb84  mov     edx, 8; unsigned __int64
0x1400cbb89  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cbb8d  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cbb91  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cbb96  nop
0x1400cbb97  xor     edx, edx; Val
0x1400cbb99  mov     r8d, 100h; Size
0x1400cbb9f  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cbba4  call    memset_0
0x1400cbba9  xor     edi, edi
0x1400cbbab  xor     r14d, r14d
0x1400cbbae  cmp     r14d, [rsi+24h]
0x1400cbbb2  jge     loc_1400CBC4B
0x1400cbbb8  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cbbc1  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cbbc9  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cbbce  lea     r8, _lambda_1beeb3f5b12b17edc670c5c4fb163e90____lambda_invoker_cdecl_; lpStartAddress
0x1400cbbd5  xor     edx, edx; dwStackSize
0x1400cbbd7  xor     ecx, ecx; lpThreadAttributes
0x1400cbbd9  call    cs:__imp_CreateThread
0x1400cbbe0  nop     dword ptr [rax+rax+00h]
0x1400cbbe5  mov     [rsp+3E0h+var_3B0], rax
0x1400cbbea  movsxd  r15, r14d
0x1400cbbed  lea     rbx, [rbp+2E0h+var_290]
0x1400cbbf1  lea     rbx, [rbx+r15*8]
0x1400cbbf5  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cbbfa  mov     rcx, rbx
0x1400cbbfd  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cbc02  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cbc07  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cbc0c  mov     rcx, [rbx]
0x1400cbc0f  lea     rax, [rcx-1]
0x1400cbc13  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cbc17  ja      short loc_1400CBC25
0x1400cbc19  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cbc1e  inc     edi
0x1400cbc20  inc     r14d
0x1400cbc23  jmp     short loc_1400CBBAE
0x1400cbc25  call    cs:__imp_GetLastError
0x1400cbc2c  nop     dword ptr [rax+rax+00h]
0x1400cbc31  test    eax, eax
0x1400cbc33  jle     short loc_1400CBC3D
0x1400cbc35  movzx   eax, ax
0x1400cbc38  or      eax, 80070000h
0x1400cbc3d  mov     edx, eax
0x1400cbc3f  mov     rcx, rsi
0x1400cbc42  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cbc47  mov     byte ptr [rsi+8], 1
0x1400cbc4b  xor     ebx, ebx
0x1400cbc4d  test    edi, edi
0x1400cbc4f  jz      short loc_1400CBCB3
0x1400cbc51  or      r14d, 0FFFFFFFFh
0x1400cbc55  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cbc5a  call    cs:__imp_ResumeThread
0x1400cbc61  nop     dword ptr [rax+rax+00h]
0x1400cbc66  cmp     eax, r14d
0x1400cbc69  jnz     short loc_1400CBC91
0x1400cbc6b  call    cs:__imp_GetLastError
0x1400cbc72  nop     dword ptr [rax+rax+00h]
0x1400cbc77  test    eax, eax
0x1400cbc79  jle     short loc_1400CBC83
0x1400cbc7b  movzx   eax, ax
0x1400cbc7e  or      eax, 80070000h
0x1400cbc83  mov     edx, eax
0x1400cbc85  mov     rcx, rsi
0x1400cbc88  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cbc8d  mov     byte ptr [rsi+8], 1
0x1400cbc91  inc     ebx
0x1400cbc93  cmp     ebx, edi
0x1400cbc95  jb      short loc_1400CBC55
0x1400cbc97  mov     r9d, r14d; dwMilliseconds
0x1400cbc9a  mov     r8d, 1; bWaitAll
0x1400cbca0  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cbca5  mov     ecx, edi; nCount
0x1400cbca7  call    cs:__imp_WaitForMultipleObjects
0x1400cbcae  nop     dword ptr [rax+rax+00h]
0x1400cbcb3  mov     edx, [rsi+1Ch]
0x1400cbcb6  nop
0x1400cbcb7  lea     rcx, [rbp+2E0h+var_190]
0x1400cbcbe  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cbcc3  mov     ebx, [rsi+1Ch]
0x1400cbcc6  nop
0x1400cbcc7  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cbcce  mov     edx, 8; unsigned __int64
0x1400cbcd3  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cbcd7  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cbcdb  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cbce0  nop
0x1400cbce1  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbce8  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cbced  mov     eax, ebx
0x1400cbcef  mov     rcx, [rbp+2E0h+var_40]
0x1400cbcf6  xor     rcx, rsp; StackCookie
0x1400cbcf9  call    __security_check_cookie
0x1400cbcfe  add     rsp, 3B8h
0x1400cbd05  pop     r15
0x1400cbd07  pop     r14
0x1400cbd09  pop     rdi
0x1400cbd0a  pop     rsi
0x1400cbd0b  pop     rbx
0x1400cbd0c  pop     rbp
0x1400cbd0d  retn
```
