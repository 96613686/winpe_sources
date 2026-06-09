# ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags_&_

- ea: `0x1401132b8`
- end: `0x1401134d0`
- name: `ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags_&_`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1401130c4`

## callees

- `0x14003d144`
- `0x14004f6dc`
- `0x1401132b8`
- `0x1401134d8`
- `0x1401141f0`
- `0x14011446c`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011f6fc`
- `0x14011fafc`
- `0x140287308`
- `0x140289ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401133e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14011342c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401133e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14011342c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14011341b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14011341b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14011339a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14011339a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140113468`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140113468`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags___(
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
    v8 = (ULONG (__stdcall *)(PVOID))lambda_861853bfbe5f3f3963e1a328be113e75_::operator_unsigned_long____cdecl___void___();
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
0x1401132b8  push    rbp
0x1401132ba  push    rbx
0x1401132bb  push    rsi
0x1401132bc  push    rdi
0x1401132bd  push    r14
0x1401132bf  push    r15
0x1401132c1  lea     rbp, [rsp-2B8h]
0x1401132c9  sub     rsp, 3B8h
0x1401132d0  mov     rax, cs:__security_cookie
0x1401132d7  xor     rax, rsp
0x1401132da  mov     [rbp+2E0h+var_40], rax
0x1401132e1  mov     rdi, r8
0x1401132e4  mov     rbx, rdx
0x1401132e7  mov     rsi, rcx
0x1401132ea  xor     edx, edx; Val
0x1401132ec  mov     r8d, 150h; Size
0x1401132f2  lea     rcx, [rbp+2E0h+var_190]; void *
0x1401132f9  call    memset_0
0x1401132fe  lea     r8, [rsi+60h]
0x140113302  lea     rdx, [rsi+50h]
0x140113306  lea     rcx, [rbp+2E0h+var_190]; this
0x14011330d  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x140113312  xor     eax, eax
0x140113314  xchg    al, [rsi+8]
0x140113317  xor     eax, eax
0x140113319  xchg    eax, [rsi+1Ch]
0x14011331c  mov     dword ptr [rsi+20h], 0
0x140113323  mov     [rsi+38h], rbx
0x140113327  mov     [rsp+3E0h+Parameter], rsi
0x14011332c  mov     [rsp+3E0h+var_3A0], rdi
0x140113331  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x140113338  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x14011333d  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x140113344  mov     edx, 8; unsigned __int64
0x140113349  lea     r8d, [rdx+18h]; unsigned __int64
0x14011334d  lea     rcx, [rbp+2E0h+var_290]; void *
0x140113351  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140113356  nop
0x140113357  xor     edx, edx; Val
0x140113359  mov     r8d, 100h; Size
0x14011335f  lea     rcx, [rsp+3E0h+hThread]; void *
0x140113364  call    memset_0
0x140113369  xor     edi, edi
0x14011336b  xor     r14d, r14d
0x14011336e  cmp     r14d, [rsi+24h]
0x140113372  jge     loc_14011340C
0x140113378  call    _lambda_861853bfbe5f3f3963e1a328be113e75___operator_unsigned_long____cdecl___void___
0x14011337d  mov     r8, rax; lpStartAddress
0x140113380  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x140113389  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x140113391  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x140113396  xor     edx, edx; dwStackSize
0x140113398  xor     ecx, ecx; lpThreadAttributes
0x14011339a  call    cs:__imp_CreateThread
0x1401133a1  nop     dword ptr [rax+rax+00h]
0x1401133a6  mov     [rsp+3E0h+var_3B0], rax
0x1401133ab  movsxd  r15, r14d
0x1401133ae  lea     rbx, [rbp+2E0h+var_290]
0x1401133b2  lea     rbx, [rbx+r15*8]
0x1401133b6  lea     rdx, [rsp+3E0h+var_3B0]
0x1401133bb  mov     rcx, rbx
0x1401133be  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1401133c3  lea     rcx, [rsp+3E0h+var_3B0]
0x1401133c8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1401133cd  mov     rcx, [rbx]
0x1401133d0  lea     rax, [rcx-1]
0x1401133d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401133d8  ja      short loc_1401133E6
0x1401133da  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1401133df  inc     edi
0x1401133e1  inc     r14d
0x1401133e4  jmp     short loc_14011336E
0x1401133e6  call    cs:__imp_GetLastError
0x1401133ed  nop     dword ptr [rax+rax+00h]
0x1401133f2  test    eax, eax
0x1401133f4  jle     short loc_1401133FE
0x1401133f6  movzx   eax, ax
0x1401133f9  or      eax, 80070000h
0x1401133fe  mov     edx, eax
0x140113400  mov     rcx, rsi
0x140113403  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140113408  mov     byte ptr [rsi+8], 1
0x14011340c  xor     ebx, ebx
0x14011340e  test    edi, edi
0x140113410  jz      short loc_140113474
0x140113412  or      r14d, 0FFFFFFFFh
0x140113416  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x14011341b  call    cs:__imp_ResumeThread
0x140113422  nop     dword ptr [rax+rax+00h]
0x140113427  cmp     eax, r14d
0x14011342a  jnz     short loc_140113452
0x14011342c  call    cs:__imp_GetLastError
0x140113433  nop     dword ptr [rax+rax+00h]
0x140113438  test    eax, eax
0x14011343a  jle     short loc_140113444
0x14011343c  movzx   eax, ax
0x14011343f  or      eax, 80070000h
0x140113444  mov     edx, eax
0x140113446  mov     rcx, rsi
0x140113449  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14011344e  mov     byte ptr [rsi+8], 1
0x140113452  inc     ebx
0x140113454  cmp     ebx, edi
0x140113456  jb      short loc_140113416
0x140113458  mov     r9d, r14d; dwMilliseconds
0x14011345b  mov     r8d, 1; bWaitAll
0x140113461  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x140113466  mov     ecx, edi; nCount
0x140113468  call    cs:__imp_WaitForMultipleObjects
0x14011346f  nop     dword ptr [rax+rax+00h]
0x140113474  mov     edx, [rsi+1Ch]
0x140113477  nop
0x140113478  lea     rcx, [rbp+2E0h+var_190]
0x14011347f  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140113484  mov     ebx, [rsi+1Ch]
0x140113487  nop
0x140113488  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x14011348f  mov     edx, 8; unsigned __int64
0x140113494  lea     r8d, [rdx+18h]; unsigned __int64
0x140113498  lea     rcx, [rbp+2E0h+var_290]; void *
0x14011349c  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1401134a1  nop
0x1401134a2  lea     rcx, [rbp+2E0h+var_190]; this
0x1401134a9  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1401134ae  mov     eax, ebx
0x1401134b0  mov     rcx, [rbp+2E0h+var_40]
0x1401134b7  xor     rcx, rsp; StackCookie
0x1401134ba  call    __security_check_cookie
0x1401134bf  add     rsp, 3B8h
0x1401134c6  pop     r15
0x1401134c8  pop     r14
0x1401134ca  pop     rdi
0x1401134cb  pop     rsi
0x1401134cc  pop     rbx
0x1401134cd  pop     rbp
0x1401134ce  retn
```
