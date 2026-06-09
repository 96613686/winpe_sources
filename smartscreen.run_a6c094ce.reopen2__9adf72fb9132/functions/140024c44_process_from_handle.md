# process_from_handle

- ea: `0x140024c44`
- end: `0x140024df1`
- name: `process_from_handle`
- size: `429`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140024928`
- `0x140033974`

## callees

- `0x140004370`
- `0x140015e6c`
- `0x140016a4c`
- `0x140016e88`
- `0x14001afa0`
- `0x140024c44`
- `0x140026c20`
- `0x140030510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140024d49`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140024d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024c8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024c9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024c8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024c9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024cac`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140024d03`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140024d03`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140024cdc`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140024cdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  v11 = path_from_process((__int64)v13, *a2);
  std::wstring::operator=(a1 + 24, v11);
  path::~path((path *)v13);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
  return a1;
}

```

## disassembly

```asm
0x140024c44  mov     [rsp-8+arg_10], rbx
0x140024c49  mov     [rsp-8+arg_18], rsi
0x140024c4e  push    rbp
0x140024c4f  push    rdi
0x140024c50  push    r14
0x140024c52  lea     rbp, [rsp-47h]
0x140024c57  sub     rsp, 0A0h
0x140024c5e  mov     rax, cs:__security_cookie
0x140024c65  xor     rax, rsp
0x140024c68  mov     [rbp+57h+var_18], rax
0x140024c6c  mov     r14, rdx
0x140024c6f  mov     rsi, rcx
0x140024c72  mov     [rbp+57h+var_68], rcx
0x140024c76  mov     [rbp+57h+var_40], rdx
0x140024c7a  mov     [rbp+57h+var_70], 0
0x140024c81  cmp     qword ptr [rdx], 0
0x140024c85  jnz     short loc_140024D00
0x140024c87  mov     qword ptr [rdx], 0
0x140024c8e  call    cs:__imp_GetCurrentProcess
0x140024c95  nop     dword ptr [rax+rax+00h]
0x140024c9a  mov     rdi, rax
0x140024c9d  call    cs:__imp_GetCurrentProcess
0x140024ca4  nop     dword ptr [rax+rax+00h]
0x140024ca9  mov     rbx, rax
0x140024cac  call    cs:__imp_GetCurrentProcess
0x140024cb3  nop     dword ptr [rax+rax+00h]
0x140024cb8  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x140024cc0  mov     [rsp+0B0h+bInheritHandle], 0; bInheritHandle
0x140024cc8  mov     [rsp+0B0h+dwDesiredAccess], 0; dwDesiredAccess
0x140024cd0  mov     r9, r14; lpTargetHandle
0x140024cd3  mov     r8, rdi; hTargetProcessHandle
0x140024cd6  mov     rdx, rbx; hSourceHandle
0x140024cd9  mov     rcx, rax; hSourceProcessHandle
0x140024cdc  call    cs:__imp_DuplicateHandle
0x140024ce3  nop     dword ptr [rax+rax+00h]
0x140024ce8  mov     rcx, [rbp+5Fh]; this
0x140024cec  test    eax, eax
0x140024cee  jnz     short loc_140024D00
0x140024cf0  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140024cf7  lea     edx, [rax+73h]; void *
0x140024cfa  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140024d00  mov     rcx, [r14]; Process
0x140024d03  call    cs:__imp_GetProcessId
0x140024d0a  nop     dword ptr [rax+rax+00h]
0x140024d0f  mov     ebx, eax
0x140024d11  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], 0
0x140024d19  mov     qword ptr [rbp+57h+ExitTime.dwLowDateTime], 0
0x140024d21  mov     qword ptr [rbp+57h+KernelTime.dwLowDateTime], 0
0x140024d29  mov     qword ptr [rbp+57h+UserTime.dwLowDateTime], 0
0x140024d31  lea     rax, [rbp+57h+UserTime]
0x140024d35  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax; lpUserTime
0x140024d3a  lea     r9, [rbp+57h+KernelTime]; lpKernelTime
0x140024d3e  lea     r8, [rbp+57h+ExitTime]; lpExitTime
0x140024d42  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x140024d46  mov     rcx, [r14]; hProcess
0x140024d49  call    cs:__imp_GetProcessTimes
0x140024d50  nop     dword ptr [rax+rax+00h]
0x140024d55  mov     rcx, [rbp+5Fh]; this
0x140024d59  test    eax, eax
0x140024d5b  jnz     short loc_140024D6D
0x140024d5d  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140024d64  lea     edx, [rax+7Dh]; void *
0x140024d67  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140024d6d  mov     byte ptr [rsi+10h], 0
0x140024d71  lea     rcx, [rsi+18h]
0x140024d75  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140024d7a  mov     [rbp+57h+var_70], 1
0x140024d81  mov     [rsi], ebx
0x140024d83  mov     rcx, 0FE624E212AC18000h
0x140024d8d  add     rcx, qword ptr [rbp+57h+CreationTime.dwLowDateTime]
0x140024d91  cmp     byte ptr [rsi+10h], 0
0x140024d95  jnz     short loc_140024D9B
0x140024d97  mov     byte ptr [rsi+10h], 1
0x140024d9b  mov     [rsi+8], rcx
0x140024d9f  mov     rdx, [r14]
0x140024da2  lea     rcx, [rbp+57h+var_60]
0x140024da6  call    path_from_process
0x140024dab  lea     rcx, [rsi+18h]
0x140024daf  mov     rdx, rax
0x140024db2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140024db7  lea     rcx, [rbp+57h+var_60]; this
0x140024dbb  call    ??1path@@QEAA@XZ; path::~path(void)
0x140024dc0  nop
0x140024dc1  mov     rcx, r14
0x140024dc4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140024dc9  mov     rax, rsi
0x140024dcc  mov     rcx, [rbp+57h+var_18]
0x140024dd0  xor     rcx, rsp; StackCookie
0x140024dd3  call    __security_check_cookie
0x140024dd8  lea     r11, [rsp+0B0h+var_10]
0x140024de0  mov     rbx, [r11+30h]
0x140024de4  mov     rsi, [r11+38h]
0x140024de8  mov     rsp, r11
0x140024deb  pop     r14
0x140024ded  pop     rdi
0x140024dee  pop     rbp
0x140024def  retn
```
