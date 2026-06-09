# ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags_&_

- ea: `0x140113720`
- end: `0x140113938`
- name: `ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags_&_`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1401128d0`

## callees

- `0x14003d144`
- `0x14004f6dc`
- `0x1401134d8`
- `0x140113720`
- `0x140113940`
- `0x1401141f0`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011f6fc`
- `0x14011fafc`
- `0x140287308`
- `0x140289ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14011384e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14011384e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140113894`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140113883`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140113883`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140113802`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140113802`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401138d0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401138d0`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags___(
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
    v8 = (ULONG (__stdcall *)(PVOID))lambda_9f59de74433dd7d8ff82dcfb6a7f49d9_::operator_unsigned_long____cdecl___void___();
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
0x140113720  push    rbp
0x140113722  push    rbx
0x140113723  push    rsi
0x140113724  push    rdi
0x140113725  push    r14
0x140113727  push    r15
0x140113729  lea     rbp, [rsp-2B8h]
0x140113731  sub     rsp, 3B8h
0x140113738  mov     rax, cs:__security_cookie
0x14011373f  xor     rax, rsp
0x140113742  mov     [rbp+2E0h+var_40], rax
0x140113749  mov     rdi, r8
0x14011374c  mov     rbx, rdx
0x14011374f  mov     rsi, rcx
0x140113752  xor     edx, edx; Val
0x140113754  mov     r8d, 150h; Size
0x14011375a  lea     rcx, [rbp+2E0h+var_190]; void *
0x140113761  call    memset_0
0x140113766  lea     r8, [rsi+60h]
0x14011376a  lea     rdx, [rsi+50h]
0x14011376e  lea     rcx, [rbp+2E0h+var_190]; this
0x140113775  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x14011377a  xor     eax, eax
0x14011377c  xchg    al, [rsi+8]
0x14011377f  xor     eax, eax
0x140113781  xchg    eax, [rsi+1Ch]
0x140113784  mov     dword ptr [rsi+20h], 0
0x14011378b  mov     [rsi+38h], rbx
0x14011378f  mov     [rsp+3E0h+Parameter], rsi
0x140113794  mov     [rsp+3E0h+var_3A0], rdi
0x140113799  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1401137a0  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1401137a5  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1401137ac  mov     edx, 8; unsigned __int64
0x1401137b1  lea     r8d, [rdx+18h]; unsigned __int64
0x1401137b5  lea     rcx, [rbp+2E0h+var_290]; void *
0x1401137b9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1401137be  nop
0x1401137bf  xor     edx, edx; Val
0x1401137c1  mov     r8d, 100h; Size
0x1401137c7  lea     rcx, [rsp+3E0h+hThread]; void *
0x1401137cc  call    memset_0
0x1401137d1  xor     edi, edi
0x1401137d3  xor     r14d, r14d
0x1401137d6  cmp     r14d, [rsi+24h]
0x1401137da  jge     loc_140113874
0x1401137e0  call    _lambda_9f59de74433dd7d8ff82dcfb6a7f49d9___operator_unsigned_long____cdecl___void___
0x1401137e5  mov     r8, rax; lpStartAddress
0x1401137e8  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1401137f1  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1401137f9  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1401137fe  xor     edx, edx; dwStackSize
0x140113800  xor     ecx, ecx; lpThreadAttributes
0x140113802  call    cs:__imp_CreateThread
0x140113809  nop     dword ptr [rax+rax+00h]
0x14011380e  mov     [rsp+3E0h+var_3B0], rax
0x140113813  movsxd  r15, r14d
0x140113816  lea     rbx, [rbp+2E0h+var_290]
0x14011381a  lea     rbx, [rbx+r15*8]
0x14011381e  lea     rdx, [rsp+3E0h+var_3B0]
0x140113823  mov     rcx, rbx
0x140113826  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x14011382b  lea     rcx, [rsp+3E0h+var_3B0]
0x140113830  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140113835  mov     rcx, [rbx]
0x140113838  lea     rax, [rcx-1]
0x14011383c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140113840  ja      short loc_14011384E
0x140113842  mov     [rsp+r15*8+3E0h+hThread], rcx
0x140113847  inc     edi
0x140113849  inc     r14d
0x14011384c  jmp     short loc_1401137D6
0x14011384e  call    cs:__imp_GetLastError
0x140113855  nop     dword ptr [rax+rax+00h]
0x14011385a  test    eax, eax
0x14011385c  jle     short loc_140113866
0x14011385e  movzx   eax, ax
0x140113861  or      eax, 80070000h
0x140113866  mov     edx, eax
0x140113868  mov     rcx, rsi
0x14011386b  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140113870  mov     byte ptr [rsi+8], 1
0x140113874  xor     ebx, ebx
0x140113876  test    edi, edi
0x140113878  jz      short loc_1401138DC
0x14011387a  or      r14d, 0FFFFFFFFh
0x14011387e  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x140113883  call    cs:__imp_ResumeThread
0x14011388a  nop     dword ptr [rax+rax+00h]
0x14011388f  cmp     eax, r14d
0x140113892  jnz     short loc_1401138BA
0x140113894  call    cs:__imp_GetLastError
0x14011389b  nop     dword ptr [rax+rax+00h]
0x1401138a0  test    eax, eax
0x1401138a2  jle     short loc_1401138AC
0x1401138a4  movzx   eax, ax
0x1401138a7  or      eax, 80070000h
0x1401138ac  mov     edx, eax
0x1401138ae  mov     rcx, rsi
0x1401138b1  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1401138b6  mov     byte ptr [rsi+8], 1
0x1401138ba  inc     ebx
0x1401138bc  cmp     ebx, edi
0x1401138be  jb      short loc_14011387E
0x1401138c0  mov     r9d, r14d; dwMilliseconds
0x1401138c3  mov     r8d, 1; bWaitAll
0x1401138c9  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1401138ce  mov     ecx, edi; nCount
0x1401138d0  call    cs:__imp_WaitForMultipleObjects
0x1401138d7  nop     dword ptr [rax+rax+00h]
0x1401138dc  mov     edx, [rsi+1Ch]
0x1401138df  nop
0x1401138e0  lea     rcx, [rbp+2E0h+var_190]
0x1401138e7  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1401138ec  mov     ebx, [rsi+1Ch]
0x1401138ef  nop
0x1401138f0  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1401138f7  mov     edx, 8; unsigned __int64
0x1401138fc  lea     r8d, [rdx+18h]; unsigned __int64
0x140113900  lea     rcx, [rbp+2E0h+var_290]; void *
0x140113904  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140113909  nop
0x14011390a  lea     rcx, [rbp+2E0h+var_190]; this
0x140113911  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x140113916  mov     eax, ebx
0x140113918  mov     rcx, [rbp+2E0h+var_40]
0x14011391f  xor     rcx, rsp; StackCookie
0x140113922  call    __security_check_cookie
0x140113927  add     rsp, 3B8h
0x14011392e  pop     r15
0x140113930  pop     r14
0x140113932  pop     rdi
0x140113933  pop     rsi
0x140113934  pop     rbx
0x140113935  pop     rbp
0x140113936  retn
```
