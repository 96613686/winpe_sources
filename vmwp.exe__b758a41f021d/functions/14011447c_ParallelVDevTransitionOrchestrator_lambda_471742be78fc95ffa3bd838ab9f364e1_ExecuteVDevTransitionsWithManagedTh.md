# ParallelVDevTransitionOrchestrator__lambda_471742be78fc95ffa3bd838ab9f364e1___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbSaveFlags_&_

- ea: `0x14011447c`
- end: `0x14011469f`
- name: `ParallelVDevTransitionOrchestrator__lambda_471742be78fc95ffa3bd838ab9f364e1___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbSaveFlags_&_`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140112ac8`

## callees

- `0x14003d144`
- `0x14004f6dc`
- `0x1401134d8`
- `0x1401141f0`
- `0x14011447c`
- `0x1401146a8`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011f6fc`
- `0x14011fafc`
- `0x140287308`
- `0x140289ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401145b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401145f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401145b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401145f8`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401145e8`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401145e8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140114568`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140114568`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140114635`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140114635`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_471742be78fc95ffa3bd838ab9f364e1___::ExecuteVDevTransitionsWithManagedThreads_VmRepository_____enum_VmbSaveFlags___(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  DWORD v8; // edi
  int i; // esi
  ULONG (__stdcall *v10)(PVOID); // rax
  char *v11; // rcx
  signed int LastError; // eax
  __int64 v13; // rbx
  signed int v14; // eax
  unsigned int v15; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v20[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v21[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v21, 0, sizeof(v21));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v21);
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  Parameter[1] = a4;
  Parameter[2] = a3;
  `eh vector constructor iterator'(
    v20,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v8 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    v10 = (ULONG (__stdcall *)(PVOID))lambda_54eb06ad5ac2237426fe1ef8f81c806e_::operator_unsigned_long____cdecl___void___();
    Thread = CreateThread(0, 0, v10, Parameter, 4u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v20[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v11 = (char *)v20[i];
    if ( (unsigned __int64)(v11 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
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
    hThread[i] = v11;
    ++v8;
  }
  v13 = 0;
  if ( v8 )
  {
    do
    {
      if ( ResumeThread(hThread[v13]) == -1 )
      {
        v14 = GetLastError();
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v14);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < v8 );
    WaitForMultipleObjects(v8, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v21, *(unsigned int *)(a1 + 28));
  v15 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v20,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v21);
  return v15;
}

```

## disassembly

```asm
0x14011447c  push    rbp
0x14011447e  push    rbx
0x14011447f  push    rsi
0x140114480  push    rdi
0x140114481  push    r14
0x140114483  push    r15
0x140114485  lea     rbp, [rsp-2B8h]
0x14011448d  sub     rsp, 3B8h
0x140114494  mov     rax, cs:__security_cookie
0x14011449b  xor     rax, rsp
0x14011449e  mov     [rbp+2E0h+var_40], rax
0x1401144a5  mov     rdi, r9
0x1401144a8  mov     rsi, r8
0x1401144ab  mov     rbx, rdx
0x1401144ae  mov     r14, rcx
0x1401144b1  xor     edx, edx; Val
0x1401144b3  mov     r8d, 150h; Size
0x1401144b9  lea     rcx, [rbp+2E0h+var_190]; void *
0x1401144c0  call    memset_0
0x1401144c5  lea     r8, [r14+60h]
0x1401144c9  lea     rdx, [r14+50h]
0x1401144cd  lea     rcx, [rbp+2E0h+var_190]; this
0x1401144d4  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1401144d9  xor     eax, eax
0x1401144db  xchg    al, [r14+8]
0x1401144df  xor     eax, eax
0x1401144e1  xchg    eax, [r14+1Ch]
0x1401144e5  mov     dword ptr [r14+20h], 0
0x1401144ed  mov     [r14+38h], rbx
0x1401144f1  mov     [rsp+3E0h+Parameter], r14
0x1401144f6  mov     [rsp+3E0h+var_3A0], rdi
0x1401144fb  mov     [rsp+3E0h+var_398], rsi
0x140114500  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x140114507  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x14011450c  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x140114513  mov     edx, 8; unsigned __int64
0x140114518  lea     r8d, [rdx+18h]; unsigned __int64
0x14011451c  lea     rcx, [rbp+2E0h+var_290]; void *
0x140114520  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140114525  nop
0x140114526  xor     edx, edx; Val
0x140114528  mov     r8d, 100h; Size
0x14011452e  lea     rcx, [rsp+3E0h+hThread]; void *
0x140114533  call    memset_0
0x140114538  xor     edi, edi
0x14011453a  xor     esi, esi
0x14011453c  cmp     esi, [r14+24h]
0x140114540  jge     loc_1401145DA
0x140114546  call    _lambda_54eb06ad5ac2237426fe1ef8f81c806e___operator_unsigned_long____cdecl___void___
0x14011454b  mov     r8, rax; lpStartAddress
0x14011454e  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x140114557  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x14011455f  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x140114564  xor     edx, edx; dwStackSize
0x140114566  xor     ecx, ecx; lpThreadAttributes
0x140114568  call    cs:__imp_CreateThread
0x14011456f  nop     dword ptr [rax+rax+00h]
0x140114574  mov     [rsp+3E0h+var_3B0], rax
0x140114579  movsxd  r15, esi
0x14011457c  lea     rbx, [rbp+2E0h+var_290]
0x140114580  lea     rbx, [rbx+r15*8]
0x140114584  lea     rdx, [rsp+3E0h+var_3B0]
0x140114589  mov     rcx, rbx
0x14011458c  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140114591  lea     rcx, [rsp+3E0h+var_3B0]
0x140114596  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14011459b  mov     rcx, [rbx]
0x14011459e  lea     rax, [rcx-1]
0x1401145a2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401145a6  ja      short loc_1401145B3
0x1401145a8  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1401145ad  inc     edi
0x1401145af  inc     esi
0x1401145b1  jmp     short loc_14011453C
0x1401145b3  call    cs:__imp_GetLastError
0x1401145ba  nop     dword ptr [rax+rax+00h]
0x1401145bf  test    eax, eax
0x1401145c1  jle     short loc_1401145CB
0x1401145c3  movzx   eax, ax
0x1401145c6  or      eax, 80070000h
0x1401145cb  mov     edx, eax
0x1401145cd  mov     rcx, r14
0x1401145d0  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1401145d5  mov     byte ptr [r14+8], 1
0x1401145da  xor     ebx, ebx
0x1401145dc  test    edi, edi
0x1401145de  jz      short loc_140114641
0x1401145e0  or      esi, 0FFFFFFFFh
0x1401145e3  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1401145e8  call    cs:__imp_ResumeThread
0x1401145ef  nop     dword ptr [rax+rax+00h]
0x1401145f4  cmp     eax, esi
0x1401145f6  jnz     short loc_14011461F
0x1401145f8  call    cs:__imp_GetLastError
0x1401145ff  nop     dword ptr [rax+rax+00h]
0x140114604  test    eax, eax
0x140114606  jle     short loc_140114610
0x140114608  movzx   eax, ax
0x14011460b  or      eax, 80070000h
0x140114610  mov     edx, eax
0x140114612  mov     rcx, r14
0x140114615  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14011461a  mov     byte ptr [r14+8], 1
0x14011461f  inc     ebx
0x140114621  cmp     ebx, edi
0x140114623  jb      short loc_1401145E3
0x140114625  mov     r9d, esi; dwMilliseconds
0x140114628  mov     r8d, 1; bWaitAll
0x14011462e  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x140114633  mov     ecx, edi; nCount
0x140114635  call    cs:__imp_WaitForMultipleObjects
0x14011463c  nop     dword ptr [rax+rax+00h]
0x140114641  mov     edx, [r14+1Ch]
0x140114645  nop
0x140114646  lea     rcx, [rbp+2E0h+var_190]
0x14011464d  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140114652  mov     ebx, [r14+1Ch]
0x140114656  nop
0x140114657  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x14011465e  mov     edx, 8; unsigned __int64
0x140114663  lea     r8d, [rdx+18h]; unsigned __int64
0x140114667  lea     rcx, [rbp+2E0h+var_290]; void *
0x14011466b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140114670  nop
0x140114671  lea     rcx, [rbp+2E0h+var_190]; this
0x140114678  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x14011467d  mov     eax, ebx
0x14011467f  mov     rcx, [rbp+2E0h+var_40]
0x140114686  xor     rcx, rsp; StackCookie
0x140114689  call    __security_check_cookie
0x14011468e  add     rsp, 3B8h
0x140114695  pop     r15
0x140114697  pop     r14
0x140114699  pop     rdi
0x14011469a  pop     rsi
0x14011469b  pop     rbx
0x14011469c  pop     rbp
0x14011469d  retn
```
