# process_from_handle

- ea: `0x140023aac`
- end: `0x140023c35`
- name: `process_from_handle`
- size: `393`
- prototype: `__int64 __fastcall(__int64, HANDLE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400237a4`
- `0x1400324fc`

## callees

- `0x140004190`
- `0x1400152b8`
- `0x140015e60`
- `0x140016288`
- `0x14001a1b8`
- `0x140023aac`
- `0x140025aa0`
- `0x14002f250`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140023b93`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140023b93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140023af6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140023aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140023b08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140023af6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140023aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140023b08`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140023b53`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140023b53`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140023b32`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140023b32`

## pseudocode

```c
__int64 __fastcall process_from_handle(__int64 a1, HANDLE *a2)
{
  HANDLE CurrentProcess; // rdi
  HANDLE v5; // rbx
  HANDLE v6; // rax
  const char *v7; // r9
  DWORD ProcessId; // ebx
  const char *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rax
  _BYTE v13[32]; // [rsp+50h] [rbp-9h] BYREF
  HANDLE *v14; // [rsp+70h] [rbp+17h]
  struct _FILETIME CreationTime; // [rsp+78h] [rbp+1Fh] BYREF
  struct _FILETIME UserTime; // [rsp+80h] [rbp+27h] BYREF
  struct _FILETIME KernelTime; // [rsp+88h] [rbp+2Fh] BYREF
  struct _FILETIME ExitTime; // [rsp+90h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v14 = a2;
  if ( !*a2 )
  {
    *a2 = 0;
    CurrentProcess = GetCurrentProcess();
    v5 = GetCurrentProcess();
    v6 = GetCurrentProcess();
    if ( !DuplicateHandle(v6, v5, CurrentProcess, a2, 0, 0, 2u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
        v7);
  }
  ProcessId = GetProcessId(*a2);
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  if ( !GetProcessTimes(*a2, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      v9);
  *(_BYTE *)(a1 + 16) = 0;
  std::wstring::wstring(a1 + 24);
  *(_DWORD *)a1 = ProcessId;
  v10 = *(_QWORD *)&CreationTime - 116444736000000000LL;
  if ( !*(_BYTE *)(a1 + 16) )
    *(_BYTE *)(a1 + 16) = 1;
  *(_QWORD *)(a1 + 8) = v10;
  v11 = path_from_process(v13, *a2);
  std::wstring::operator=(a1 + 24, v11);
  path::~path((path *)v13);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
  return a1;
}

```

## disassembly

```asm
0x140023aac  mov     [rsp-8+arg_10], rbx
0x140023ab1  mov     [rsp-8+arg_18], rsi
0x140023ab6  push    rbp
0x140023ab7  push    rdi
0x140023ab8  push    r14
0x140023aba  lea     rbp, [rsp-47h]
0x140023abf  sub     rsp, 0A0h
0x140023ac6  mov     rax, cs:__security_cookie
0x140023acd  xor     rax, rsp
0x140023ad0  mov     [rbp+57h+var_18], rax
0x140023ad4  mov     r14, rdx
0x140023ad7  mov     rsi, rcx
0x140023ada  mov     [rbp+57h+var_68], rcx
0x140023ade  mov     [rbp+57h+var_40], rdx
0x140023ae2  mov     [rbp+57h+var_70], 0
0x140023ae9  cmp     qword ptr [rdx], 0
0x140023aed  jnz     short loc_140023B50
0x140023aef  mov     qword ptr [rdx], 0
0x140023af6  call    cs:__imp_GetCurrentProcess
0x140023afc  mov     rdi, rax
0x140023aff  call    cs:__imp_GetCurrentProcess
0x140023b05  mov     rbx, rax
0x140023b08  call    cs:__imp_GetCurrentProcess
0x140023b0e  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x140023b16  mov     [rsp+0B0h+bInheritHandle], 0; bInheritHandle
0x140023b1e  mov     [rsp+0B0h+dwDesiredAccess], 0; dwDesiredAccess
0x140023b26  mov     r9, r14; lpTargetHandle
0x140023b29  mov     r8, rdi; hTargetProcessHandle
0x140023b2c  mov     rdx, rbx; hSourceHandle
0x140023b2f  mov     rcx, rax; hSourceProcessHandle
0x140023b32  call    cs:__imp_DuplicateHandle
0x140023b38  mov     rcx, [rbp+5Fh]; this
0x140023b3c  test    eax, eax
0x140023b3e  jnz     short loc_140023B50
0x140023b40  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140023b47  lea     edx, [rax+73h]; void *
0x140023b4a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140023b50  mov     rcx, [r14]; Process
0x140023b53  call    cs:__imp_GetProcessId
0x140023b59  mov     ebx, eax
0x140023b5b  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], 0
0x140023b63  mov     qword ptr [rbp+57h+ExitTime.dwLowDateTime], 0
0x140023b6b  mov     qword ptr [rbp+57h+KernelTime.dwLowDateTime], 0
0x140023b73  mov     qword ptr [rbp+57h+UserTime.dwLowDateTime], 0
0x140023b7b  lea     rax, [rbp+57h+UserTime]
0x140023b7f  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax; lpUserTime
0x140023b84  lea     r9, [rbp+57h+KernelTime]; lpKernelTime
0x140023b88  lea     r8, [rbp+57h+ExitTime]; lpExitTime
0x140023b8c  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x140023b90  mov     rcx, [r14]; hProcess
0x140023b93  call    cs:__imp_GetProcessTimes
0x140023b99  mov     rcx, [rbp+5Fh]; this
0x140023b9d  test    eax, eax
0x140023b9f  jnz     short loc_140023BB1
0x140023ba1  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140023ba8  lea     edx, [rax+7Dh]; void *
0x140023bab  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140023bb1  mov     byte ptr [rsi+10h], 0
0x140023bb5  lea     rcx, [rsi+18h]
0x140023bb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140023bbe  mov     [rbp+57h+var_70], 1
0x140023bc5  mov     [rsi], ebx
0x140023bc7  mov     rcx, 0FE624E212AC18000h
0x140023bd1  add     rcx, qword ptr [rbp+57h+CreationTime.dwLowDateTime]
0x140023bd5  cmp     byte ptr [rsi+10h], 0
0x140023bd9  jnz     short loc_140023BDF
0x140023bdb  mov     byte ptr [rsi+10h], 1
0x140023bdf  mov     [rsi+8], rcx
0x140023be3  mov     rdx, [r14]
0x140023be6  lea     rcx, [rbp+57h+var_60]
0x140023bea  call    path_from_process
0x140023bef  lea     rcx, [rsi+18h]
0x140023bf3  mov     rdx, rax
0x140023bf6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140023bfb  lea     rcx, [rbp+57h+var_60]; this
0x140023bff  call    ??1path@@QEAA@XZ; path::~path(void)
0x140023c04  nop
0x140023c05  mov     rcx, r14
0x140023c08  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140023c0d  mov     rax, rsi
0x140023c10  mov     rcx, [rbp+57h+var_18]
0x140023c14  xor     rcx, rsp; StackCookie
0x140023c17  call    __security_check_cookie
0x140023c1c  lea     r11, [rsp+0B0h+var_10]
0x140023c24  mov     rbx, [r11+30h]
0x140023c28  mov     rsi, [r11+38h]
0x140023c2c  mov     rsp, r11
0x140023c2f  pop     r14
0x140023c31  pop     rdi
0x140023c32  pop     rbp
0x140023c33  retn
```
