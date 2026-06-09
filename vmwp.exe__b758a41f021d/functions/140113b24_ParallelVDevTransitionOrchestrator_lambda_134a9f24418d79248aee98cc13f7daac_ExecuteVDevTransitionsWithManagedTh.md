# ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__

- ea: `0x140113b24`
- end: `0x140113d34`
- name: `ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140113950`

## callees

- `0x14003d144`
- `0x14004f6dc`
- `0x1401134d8`
- `0x140113b24`
- `0x140113d94`
- `0x1401141f0`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011f6fc`
- `0x14011fafc`
- `0x140287308`
- `0x140289ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113c90`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140113c7f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140113c7f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140113bfe`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140113bfe`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140113ccc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140113ccc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__(
        __int64 a1,
        __int64 a2)
{
  DWORD v4; // esi
  int i; // r14d
  ULONG (__stdcall *v6)(PVOID); // rax
  char *v7; // rcx
  signed int LastError; // eax
  __int64 v9; // rbx
  signed int v10; // eax
  unsigned int v11; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v16[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v17[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v17, 0, sizeof(v17));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v17);
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  `eh vector constructor iterator'(
    v16,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v4 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    v6 = (ULONG (__stdcall *)(PVOID))lambda_239b04fb377517302dc275a63afe40ff_::operator_unsigned_long____cdecl___void___();
    Thread = CreateThread(0, 0, v6, Parameter, 4u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v16[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v7 = (char *)v16[i];
    if ( (unsigned __int64)(v7 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
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
    hThread[i] = v7;
    ++v4;
  }
  v9 = 0;
  if ( v4 )
  {
    do
    {
      if ( ResumeThread(hThread[v9]) == -1 )
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v10);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (unsigned int)v9 < v4 );
    WaitForMultipleObjects(v4, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17, *(unsigned int *)(a1 + 28));
  v11 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v16,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v17);
  return v11;
}

```

## disassembly

```asm
0x140113b24  push    rbp
0x140113b26  push    rbx
0x140113b27  push    rsi
0x140113b28  push    rdi
0x140113b29  push    r14
0x140113b2b  push    r15
0x140113b2d  lea     rbp, [rsp-2B8h]
0x140113b35  sub     rsp, 3B8h
0x140113b3c  mov     rax, cs:__security_cookie
0x140113b43  xor     rax, rsp
0x140113b46  mov     [rbp+2E0h+var_40], rax
0x140113b4d  mov     rbx, rdx
0x140113b50  mov     rdi, rcx
0x140113b53  xor     edx, edx; Val
0x140113b55  mov     r8d, 150h; Size
0x140113b5b  lea     rcx, [rbp+2E0h+var_190]; void *
0x140113b62  call    memset_0
0x140113b67  lea     r8, [rdi+60h]
0x140113b6b  lea     rdx, [rdi+50h]
0x140113b6f  lea     rcx, [rbp+2E0h+var_190]; this
0x140113b76  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x140113b7b  xor     eax, eax
0x140113b7d  xchg    al, [rdi+8]
0x140113b80  xor     eax, eax
0x140113b82  xchg    eax, [rdi+1Ch]
0x140113b85  mov     dword ptr [rdi+20h], 0
0x140113b8c  mov     [rdi+38h], rbx
0x140113b90  mov     [rsp+3E0h+Parameter], rdi
0x140113b95  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x140113b9c  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x140113ba1  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x140113ba8  mov     edx, 8; unsigned __int64
0x140113bad  lea     r8d, [rdx+18h]; unsigned __int64
0x140113bb1  lea     rcx, [rbp+2E0h+var_290]; void *
0x140113bb5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140113bba  nop
0x140113bbb  xor     edx, edx; Val
0x140113bbd  mov     r8d, 100h; Size
0x140113bc3  lea     rcx, [rsp+3E0h+hThread]; void *
0x140113bc8  call    memset_0
0x140113bcd  xor     esi, esi
0x140113bcf  xor     r14d, r14d
0x140113bd2  cmp     r14d, [rdi+24h]
0x140113bd6  jge     loc_140113C70
0x140113bdc  call    _lambda_239b04fb377517302dc275a63afe40ff___operator_unsigned_long____cdecl___void___
0x140113be1  mov     r8, rax; lpStartAddress
0x140113be4  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x140113bed  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x140113bf5  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x140113bfa  xor     edx, edx; dwStackSize
0x140113bfc  xor     ecx, ecx; lpThreadAttributes
0x140113bfe  call    cs:__imp_CreateThread
0x140113c05  nop     dword ptr [rax+rax+00h]
0x140113c0a  mov     [rsp+3E0h+var_3B0], rax
0x140113c0f  movsxd  r15, r14d
0x140113c12  lea     rbx, [rbp+2E0h+var_290]
0x140113c16  lea     rbx, [rbx+r15*8]
0x140113c1a  lea     rdx, [rsp+3E0h+var_3B0]
0x140113c1f  mov     rcx, rbx
0x140113c22  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140113c27  lea     rcx, [rsp+3E0h+var_3B0]
0x140113c2c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140113c31  mov     rcx, [rbx]
0x140113c34  lea     rax, [rcx-1]
0x140113c38  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140113c3c  ja      short loc_140113C4A
0x140113c3e  mov     [rsp+r15*8+3E0h+hThread], rcx
0x140113c43  inc     esi
0x140113c45  inc     r14d
0x140113c48  jmp     short loc_140113BD2
0x140113c4a  call    cs:__imp_GetLastError
0x140113c51  nop     dword ptr [rax+rax+00h]
0x140113c56  test    eax, eax
0x140113c58  jle     short loc_140113C62
0x140113c5a  movzx   eax, ax
0x140113c5d  or      eax, 80070000h
0x140113c62  mov     edx, eax
0x140113c64  mov     rcx, rdi
0x140113c67  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140113c6c  mov     byte ptr [rdi+8], 1
0x140113c70  xor     ebx, ebx
0x140113c72  test    esi, esi
0x140113c74  jz      short loc_140113CD8
0x140113c76  or      r14d, 0FFFFFFFFh
0x140113c7a  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x140113c7f  call    cs:__imp_ResumeThread
0x140113c86  nop     dword ptr [rax+rax+00h]
0x140113c8b  cmp     eax, r14d
0x140113c8e  jnz     short loc_140113CB6
0x140113c90  call    cs:__imp_GetLastError
0x140113c97  nop     dword ptr [rax+rax+00h]
0x140113c9c  test    eax, eax
0x140113c9e  jle     short loc_140113CA8
0x140113ca0  movzx   eax, ax
0x140113ca3  or      eax, 80070000h
0x140113ca8  mov     edx, eax
0x140113caa  mov     rcx, rdi
0x140113cad  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140113cb2  mov     byte ptr [rdi+8], 1
0x140113cb6  inc     ebx
0x140113cb8  cmp     ebx, esi
0x140113cba  jb      short loc_140113C7A
0x140113cbc  mov     r9d, r14d; dwMilliseconds
0x140113cbf  mov     r8d, 1; bWaitAll
0x140113cc5  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x140113cca  mov     ecx, esi; nCount
0x140113ccc  call    cs:__imp_WaitForMultipleObjects
0x140113cd3  nop     dword ptr [rax+rax+00h]
0x140113cd8  mov     edx, [rdi+1Ch]
0x140113cdb  nop
0x140113cdc  lea     rcx, [rbp+2E0h+var_190]
0x140113ce3  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140113ce8  mov     ebx, [rdi+1Ch]
0x140113ceb  nop
0x140113cec  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x140113cf3  mov     edx, 8; unsigned __int64
0x140113cf8  lea     r8d, [rdx+18h]; unsigned __int64
0x140113cfc  lea     rcx, [rbp+2E0h+var_290]; void *
0x140113d00  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140113d05  nop
0x140113d06  lea     rcx, [rbp+2E0h+var_190]; this
0x140113d0d  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x140113d12  mov     eax, ebx
0x140113d14  mov     rcx, [rbp+2E0h+var_40]
0x140113d1b  xor     rcx, rsp; StackCookie
0x140113d1e  call    __security_check_cookie
0x140113d23  add     rsp, 3B8h
0x140113d2a  pop     r15
0x140113d2c  pop     r14
0x140113d2e  pop     rdi
0x140113d2f  pop     rsi
0x140113d30  pop     rbx
0x140113d31  pop     rbp
0x140113d32  retn
```
