# ParallelVDevTransitionOrchestrator__lambda_a79a889f1eb83bcbe7a6d92391d5f7f3___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPauseFlags_&_

- ea: `0x14011424c`
- end: `0x140114464`
- name: `ParallelVDevTransitionOrchestrator__lambda_a79a889f1eb83bcbe7a6d92391d5f7f3___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPauseFlags_&_`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140112ecc`

## callees

- `0x14003d144`
- `0x14004f6dc`
- `0x1401134d8`
- `0x1401141f0`
- `0x14011424c`
- `0x1401146b8`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011f6fc`
- `0x14011fafc`
- `0x140287308`
- `0x140289ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14011437a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401143c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14011437a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401143c0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401143af`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401143af`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14011432e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14011432e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401143fc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401143fc`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_a79a889f1eb83bcbe7a6d92391d5f7f3___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPauseFlags___(
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
    v8 = (ULONG (__stdcall *)(PVOID))lambda_316c950b0fc81b128eb7540010ca9c07_::operator_unsigned_long____cdecl___void___();
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
0x14011424c  push    rbp
0x14011424e  push    rbx
0x14011424f  push    rsi
0x140114250  push    rdi
0x140114251  push    r14
0x140114253  push    r15
0x140114255  lea     rbp, [rsp-2B8h]
0x14011425d  sub     rsp, 3B8h
0x140114264  mov     rax, cs:__security_cookie
0x14011426b  xor     rax, rsp
0x14011426e  mov     [rbp+2E0h+var_40], rax
0x140114275  mov     rdi, r8
0x140114278  mov     rbx, rdx
0x14011427b  mov     rsi, rcx
0x14011427e  xor     edx, edx; Val
0x140114280  mov     r8d, 150h; Size
0x140114286  lea     rcx, [rbp+2E0h+var_190]; void *
0x14011428d  call    memset_0
0x140114292  lea     r8, [rsi+60h]
0x140114296  lea     rdx, [rsi+50h]
0x14011429a  lea     rcx, [rbp+2E0h+var_190]; this
0x1401142a1  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1401142a6  xor     eax, eax
0x1401142a8  xchg    al, [rsi+8]
0x1401142ab  xor     eax, eax
0x1401142ad  xchg    eax, [rsi+1Ch]
0x1401142b0  mov     dword ptr [rsi+20h], 0
0x1401142b7  mov     [rsi+38h], rbx
0x1401142bb  mov     [rsp+3E0h+Parameter], rsi
0x1401142c0  mov     [rsp+3E0h+var_3A0], rdi
0x1401142c5  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1401142cc  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1401142d1  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1401142d8  mov     edx, 8; unsigned __int64
0x1401142dd  lea     r8d, [rdx+18h]; unsigned __int64
0x1401142e1  lea     rcx, [rbp+2E0h+var_290]; void *
0x1401142e5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1401142ea  nop
0x1401142eb  xor     edx, edx; Val
0x1401142ed  mov     r8d, 100h; Size
0x1401142f3  lea     rcx, [rsp+3E0h+hThread]; void *
0x1401142f8  call    memset_0
0x1401142fd  xor     edi, edi
0x1401142ff  xor     r14d, r14d
0x140114302  cmp     r14d, [rsi+24h]
0x140114306  jge     loc_1401143A0
0x14011430c  call    _lambda_316c950b0fc81b128eb7540010ca9c07___operator_unsigned_long____cdecl___void___
0x140114311  mov     r8, rax; lpStartAddress
0x140114314  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x14011431d  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x140114325  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x14011432a  xor     edx, edx; dwStackSize
0x14011432c  xor     ecx, ecx; lpThreadAttributes
0x14011432e  call    cs:__imp_CreateThread
0x140114335  nop     dword ptr [rax+rax+00h]
0x14011433a  mov     [rsp+3E0h+var_3B0], rax
0x14011433f  movsxd  r15, r14d
0x140114342  lea     rbx, [rbp+2E0h+var_290]
0x140114346  lea     rbx, [rbx+r15*8]
0x14011434a  lea     rdx, [rsp+3E0h+var_3B0]
0x14011434f  mov     rcx, rbx
0x140114352  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140114357  lea     rcx, [rsp+3E0h+var_3B0]
0x14011435c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140114361  mov     rcx, [rbx]
0x140114364  lea     rax, [rcx-1]
0x140114368  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14011436c  ja      short loc_14011437A
0x14011436e  mov     [rsp+r15*8+3E0h+hThread], rcx
0x140114373  inc     edi
0x140114375  inc     r14d
0x140114378  jmp     short loc_140114302
0x14011437a  call    cs:__imp_GetLastError
0x140114381  nop     dword ptr [rax+rax+00h]
0x140114386  test    eax, eax
0x140114388  jle     short loc_140114392
0x14011438a  movzx   eax, ax
0x14011438d  or      eax, 80070000h
0x140114392  mov     edx, eax
0x140114394  mov     rcx, rsi
0x140114397  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14011439c  mov     byte ptr [rsi+8], 1
0x1401143a0  xor     ebx, ebx
0x1401143a2  test    edi, edi
0x1401143a4  jz      short loc_140114408
0x1401143a6  or      r14d, 0FFFFFFFFh
0x1401143aa  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1401143af  call    cs:__imp_ResumeThread
0x1401143b6  nop     dword ptr [rax+rax+00h]
0x1401143bb  cmp     eax, r14d
0x1401143be  jnz     short loc_1401143E6
0x1401143c0  call    cs:__imp_GetLastError
0x1401143c7  nop     dword ptr [rax+rax+00h]
0x1401143cc  test    eax, eax
0x1401143ce  jle     short loc_1401143D8
0x1401143d0  movzx   eax, ax
0x1401143d3  or      eax, 80070000h
0x1401143d8  mov     edx, eax
0x1401143da  mov     rcx, rsi
0x1401143dd  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1401143e2  mov     byte ptr [rsi+8], 1
0x1401143e6  inc     ebx
0x1401143e8  cmp     ebx, edi
0x1401143ea  jb      short loc_1401143AA
0x1401143ec  mov     r9d, r14d; dwMilliseconds
0x1401143ef  mov     r8d, 1; bWaitAll
0x1401143f5  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1401143fa  mov     ecx, edi; nCount
0x1401143fc  call    cs:__imp_WaitForMultipleObjects
0x140114403  nop     dword ptr [rax+rax+00h]
0x140114408  mov     edx, [rsi+1Ch]
0x14011440b  nop
0x14011440c  lea     rcx, [rbp+2E0h+var_190]
0x140114413  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140114418  mov     ebx, [rsi+1Ch]
0x14011441b  nop
0x14011441c  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x140114423  mov     edx, 8; unsigned __int64
0x140114428  lea     r8d, [rdx+18h]; unsigned __int64
0x14011442c  lea     rcx, [rbp+2E0h+var_290]; void *
0x140114430  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140114435  nop
0x140114436  lea     rcx, [rbp+2E0h+var_190]; this
0x14011443d  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x140114442  mov     eax, ebx
0x140114444  mov     rcx, [rbp+2E0h+var_40]
0x14011444b  xor     rcx, rsp; StackCookie
0x14011444e  call    __security_check_cookie
0x140114453  add     rsp, 3B8h
0x14011445a  pop     r15
0x14011445c  pop     r14
0x14011445e  pop     rdi
0x14011445f  pop     rsi
0x140114460  pop     rbx
0x140114461  pop     rbp
0x140114462  retn
```
