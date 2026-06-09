# ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbRestoreFlags_&_

- ea: `0x140113fc4`
- end: `0x1401141e7`
- name: `ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbRestoreFlags_&_`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140113518`

## callees

- `0x14003d144`
- `0x14004f6dc`
- `0x1401134d8`
- `0x140113fc4`
- `0x1401141f0`
- `0x14011422c`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011f6fc`
- `0x14011fafc`
- `0x140287308`
- `0x140289ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401140fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140114140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401140fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140114140`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140114130`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140114130`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1401140b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1401140b0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14011417d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14011417d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository_____enum_VmbRestoreFlags___(
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
    v10 = (ULONG (__stdcall *)(PVOID))lambda_2ba7b0b770393b44f342eb8b6140c5f2_::operator_unsigned_long____cdecl___void___();
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
0x140113fc4  push    rbp
0x140113fc6  push    rbx
0x140113fc7  push    rsi
0x140113fc8  push    rdi
0x140113fc9  push    r14
0x140113fcb  push    r15
0x140113fcd  lea     rbp, [rsp-2B8h]
0x140113fd5  sub     rsp, 3B8h
0x140113fdc  mov     rax, cs:__security_cookie
0x140113fe3  xor     rax, rsp
0x140113fe6  mov     [rbp+2E0h+var_40], rax
0x140113fed  mov     rdi, r9
0x140113ff0  mov     rsi, r8
0x140113ff3  mov     rbx, rdx
0x140113ff6  mov     r14, rcx
0x140113ff9  xor     edx, edx; Val
0x140113ffb  mov     r8d, 150h; Size
0x140114001  lea     rcx, [rbp+2E0h+var_190]; void *
0x140114008  call    memset_0
0x14011400d  lea     r8, [r14+60h]
0x140114011  lea     rdx, [r14+50h]
0x140114015  lea     rcx, [rbp+2E0h+var_190]; this
0x14011401c  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x140114021  xor     eax, eax
0x140114023  xchg    al, [r14+8]
0x140114027  xor     eax, eax
0x140114029  xchg    eax, [r14+1Ch]
0x14011402d  mov     dword ptr [r14+20h], 0
0x140114035  mov     [r14+38h], rbx
0x140114039  mov     [rsp+3E0h+Parameter], r14
0x14011403e  mov     [rsp+3E0h+var_3A0], rdi
0x140114043  mov     [rsp+3E0h+var_398], rsi
0x140114048  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x14011404f  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x140114054  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x14011405b  mov     edx, 8; unsigned __int64
0x140114060  lea     r8d, [rdx+18h]; unsigned __int64
0x140114064  lea     rcx, [rbp+2E0h+var_290]; void *
0x140114068  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x14011406d  nop
0x14011406e  xor     edx, edx; Val
0x140114070  mov     r8d, 100h; Size
0x140114076  lea     rcx, [rsp+3E0h+hThread]; void *
0x14011407b  call    memset_0
0x140114080  xor     edi, edi
0x140114082  xor     esi, esi
0x140114084  cmp     esi, [r14+24h]
0x140114088  jge     loc_140114122
0x14011408e  call    _lambda_2ba7b0b770393b44f342eb8b6140c5f2___operator_unsigned_long____cdecl___void___
0x140114093  mov     r8, rax; lpStartAddress
0x140114096  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x14011409f  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1401140a7  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1401140ac  xor     edx, edx; dwStackSize
0x1401140ae  xor     ecx, ecx; lpThreadAttributes
0x1401140b0  call    cs:__imp_CreateThread
0x1401140b7  nop     dword ptr [rax+rax+00h]
0x1401140bc  mov     [rsp+3E0h+var_3B0], rax
0x1401140c1  movsxd  r15, esi
0x1401140c4  lea     rbx, [rbp+2E0h+var_290]
0x1401140c8  lea     rbx, [rbx+r15*8]
0x1401140cc  lea     rdx, [rsp+3E0h+var_3B0]
0x1401140d1  mov     rcx, rbx
0x1401140d4  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1401140d9  lea     rcx, [rsp+3E0h+var_3B0]
0x1401140de  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1401140e3  mov     rcx, [rbx]
0x1401140e6  lea     rax, [rcx-1]
0x1401140ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401140ee  ja      short loc_1401140FB
0x1401140f0  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1401140f5  inc     edi
0x1401140f7  inc     esi
0x1401140f9  jmp     short loc_140114084
0x1401140fb  call    cs:__imp_GetLastError
0x140114102  nop     dword ptr [rax+rax+00h]
0x140114107  test    eax, eax
0x140114109  jle     short loc_140114113
0x14011410b  movzx   eax, ax
0x14011410e  or      eax, 80070000h
0x140114113  mov     edx, eax
0x140114115  mov     rcx, r14
0x140114118  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14011411d  mov     byte ptr [r14+8], 1
0x140114122  xor     ebx, ebx
0x140114124  test    edi, edi
0x140114126  jz      short loc_140114189
0x140114128  or      esi, 0FFFFFFFFh
0x14011412b  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x140114130  call    cs:__imp_ResumeThread
0x140114137  nop     dword ptr [rax+rax+00h]
0x14011413c  cmp     eax, esi
0x14011413e  jnz     short loc_140114167
0x140114140  call    cs:__imp_GetLastError
0x140114147  nop     dword ptr [rax+rax+00h]
0x14011414c  test    eax, eax
0x14011414e  jle     short loc_140114158
0x140114150  movzx   eax, ax
0x140114153  or      eax, 80070000h
0x140114158  mov     edx, eax
0x14011415a  mov     rcx, r14
0x14011415d  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140114162  mov     byte ptr [r14+8], 1
0x140114167  inc     ebx
0x140114169  cmp     ebx, edi
0x14011416b  jb      short loc_14011412B
0x14011416d  mov     r9d, esi; dwMilliseconds
0x140114170  mov     r8d, 1; bWaitAll
0x140114176  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x14011417b  mov     ecx, edi; nCount
0x14011417d  call    cs:__imp_WaitForMultipleObjects
0x140114184  nop     dword ptr [rax+rax+00h]
0x140114189  mov     edx, [r14+1Ch]
0x14011418d  nop
0x14011418e  lea     rcx, [rbp+2E0h+var_190]
0x140114195  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14011419a  mov     ebx, [r14+1Ch]
0x14011419e  nop
0x14011419f  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1401141a6  mov     edx, 8; unsigned __int64
0x1401141ab  lea     r8d, [rdx+18h]; unsigned __int64
0x1401141af  lea     rcx, [rbp+2E0h+var_290]; void *
0x1401141b3  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1401141b8  nop
0x1401141b9  lea     rcx, [rbp+2E0h+var_190]; this
0x1401141c0  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1401141c5  mov     eax, ebx
0x1401141c7  mov     rcx, [rbp+2E0h+var_40]
0x1401141ce  xor     rcx, rsp; StackCookie
0x1401141d1  call    __security_check_cookie
0x1401141d6  add     rsp, 3B8h
0x1401141dd  pop     r15
0x1401141df  pop     r14
0x1401141e1  pop     rdi
0x1401141e2  pop     rsi
0x1401141e3  pop     rbx
0x1401141e4  pop     rbp
0x1401141e5  retn
```
