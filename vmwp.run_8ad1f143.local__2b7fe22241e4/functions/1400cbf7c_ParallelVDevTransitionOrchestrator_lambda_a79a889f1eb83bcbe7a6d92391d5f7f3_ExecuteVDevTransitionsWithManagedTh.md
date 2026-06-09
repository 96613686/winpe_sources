# ParallelVDevTransitionOrchestrator__lambda_a79a889f1eb83bcbe7a6d92391d5f7f3___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPauseFlags_&_

- ea: `0x1400cbf7c`
- end: `0x1400cc193`
- name: `ParallelVDevTransitionOrchestrator__lambda_a79a889f1eb83bcbe7a6d92391d5f7f3___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPauseFlags_&_`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400cac80`

## callees

- `0x1400315c8`
- `0x14005145c`
- `0x1400ca840`
- `0x1400cbf40`
- `0x1400cbf7c`
- `0x140132960`
- `0x140132990`
- `0x14013361c`
- `0x140133a1c`
- `0x140280f80`
- `0x14028372c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cc0a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cc0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cc0a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cc0ef`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cc0de`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cc0de`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cc05d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cc05d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cc12b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cc12b`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_a79a889f1eb83bcbe7a6d92391d5f7f3___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPauseFlags___(
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
    Thread = CreateThread(0, 0, lambda_439d85307d46fa33d1f31e029a03404e_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
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
0x1400cbf7c  push    rbp
0x1400cbf7e  push    rbx
0x1400cbf7f  push    rsi
0x1400cbf80  push    rdi
0x1400cbf81  push    r14
0x1400cbf83  push    r15
0x1400cbf85  lea     rbp, [rsp-2B8h]
0x1400cbf8d  sub     rsp, 3B8h
0x1400cbf94  mov     rax, cs:__security_cookie
0x1400cbf9b  xor     rax, rsp
0x1400cbf9e  mov     [rbp+2E0h+var_40], rax
0x1400cbfa5  mov     rdi, r8
0x1400cbfa8  mov     rbx, rdx
0x1400cbfab  mov     rsi, rcx
0x1400cbfae  xor     edx, edx; Val
0x1400cbfb0  mov     r8d, 150h; Size
0x1400cbfb6  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cbfbd  call    memset_0
0x1400cbfc2  lea     r8, [rsi+60h]
0x1400cbfc6  lea     rdx, [rsi+50h]
0x1400cbfca  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbfd1  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cbfd6  xor     eax, eax
0x1400cbfd8  xchg    al, [rsi+8]
0x1400cbfdb  xor     eax, eax
0x1400cbfdd  xchg    eax, [rsi+1Ch]
0x1400cbfe0  mov     dword ptr [rsi+20h], 0
0x1400cbfe7  mov     [rsi+38h], rbx
0x1400cbfeb  mov     [rsp+3E0h+Parameter], rsi
0x1400cbff0  mov     [rsp+3E0h+var_3A0], rdi
0x1400cbff5  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cbffc  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cc001  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cc008  mov     edx, 8; unsigned __int64
0x1400cc00d  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cc011  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cc015  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cc01a  nop
0x1400cc01b  xor     edx, edx; Val
0x1400cc01d  mov     r8d, 100h; Size
0x1400cc023  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cc028  call    memset_0
0x1400cc02d  xor     edi, edi
0x1400cc02f  xor     r14d, r14d
0x1400cc032  cmp     r14d, [rsi+24h]
0x1400cc036  jge     loc_1400CC0CF
0x1400cc03c  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cc045  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cc04d  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cc052  lea     r8, _lambda_439d85307d46fa33d1f31e029a03404e____lambda_invoker_cdecl_; lpStartAddress
0x1400cc059  xor     edx, edx; dwStackSize
0x1400cc05b  xor     ecx, ecx; lpThreadAttributes
0x1400cc05d  call    cs:__imp_CreateThread
0x1400cc064  nop     dword ptr [rax+rax+00h]
0x1400cc069  mov     [rsp+3E0h+var_3B0], rax
0x1400cc06e  movsxd  r15, r14d
0x1400cc071  lea     rbx, [rbp+2E0h+var_290]
0x1400cc075  lea     rbx, [rbx+r15*8]
0x1400cc079  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cc07e  mov     rcx, rbx
0x1400cc081  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cc086  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cc08b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cc090  mov     rcx, [rbx]
0x1400cc093  lea     rax, [rcx-1]
0x1400cc097  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cc09b  ja      short loc_1400CC0A9
0x1400cc09d  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cc0a2  inc     edi
0x1400cc0a4  inc     r14d
0x1400cc0a7  jmp     short loc_1400CC032
0x1400cc0a9  call    cs:__imp_GetLastError
0x1400cc0b0  nop     dword ptr [rax+rax+00h]
0x1400cc0b5  test    eax, eax
0x1400cc0b7  jle     short loc_1400CC0C1
0x1400cc0b9  movzx   eax, ax
0x1400cc0bc  or      eax, 80070000h
0x1400cc0c1  mov     edx, eax
0x1400cc0c3  mov     rcx, rsi
0x1400cc0c6  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cc0cb  mov     byte ptr [rsi+8], 1
0x1400cc0cf  xor     ebx, ebx
0x1400cc0d1  test    edi, edi
0x1400cc0d3  jz      short loc_1400CC137
0x1400cc0d5  or      r14d, 0FFFFFFFFh
0x1400cc0d9  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cc0de  call    cs:__imp_ResumeThread
0x1400cc0e5  nop     dword ptr [rax+rax+00h]
0x1400cc0ea  cmp     eax, r14d
0x1400cc0ed  jnz     short loc_1400CC115
0x1400cc0ef  call    cs:__imp_GetLastError
0x1400cc0f6  nop     dword ptr [rax+rax+00h]
0x1400cc0fb  test    eax, eax
0x1400cc0fd  jle     short loc_1400CC107
0x1400cc0ff  movzx   eax, ax
0x1400cc102  or      eax, 80070000h
0x1400cc107  mov     edx, eax
0x1400cc109  mov     rcx, rsi
0x1400cc10c  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cc111  mov     byte ptr [rsi+8], 1
0x1400cc115  inc     ebx
0x1400cc117  cmp     ebx, edi
0x1400cc119  jb      short loc_1400CC0D9
0x1400cc11b  mov     r9d, r14d; dwMilliseconds
0x1400cc11e  mov     r8d, 1; bWaitAll
0x1400cc124  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cc129  mov     ecx, edi; nCount
0x1400cc12b  call    cs:__imp_WaitForMultipleObjects
0x1400cc132  nop     dword ptr [rax+rax+00h]
0x1400cc137  mov     edx, [rsi+1Ch]
0x1400cc13a  nop
0x1400cc13b  lea     rcx, [rbp+2E0h+var_190]
0x1400cc142  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cc147  mov     ebx, [rsi+1Ch]
0x1400cc14a  nop
0x1400cc14b  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cc152  mov     edx, 8; unsigned __int64
0x1400cc157  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cc15b  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cc15f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cc164  nop
0x1400cc165  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cc16c  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cc171  mov     eax, ebx
0x1400cc173  mov     rcx, [rbp+2E0h+var_40]
0x1400cc17a  xor     rcx, rsp; StackCookie
0x1400cc17d  call    __security_check_cookie
0x1400cc182  add     rsp, 3B8h
0x1400cc189  pop     r15
0x1400cc18b  pop     r14
0x1400cc18d  pop     rdi
0x1400cc18e  pop     rsi
0x1400cc18f  pop     rbx
0x1400cc190  pop     rbp
0x1400cc191  retn
```
