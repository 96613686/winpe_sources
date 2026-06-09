# ComputeService::Management::Details::CaptureProcessDump(ushort const *,ComputeService::Management::GuestCrashProcessDump const &,void *)

- ea: `0x14012d08c`
- end: `0x14012d1f0`
- name: `?CaptureProcessDump@Details@Management@ComputeService@@YAJPEBGAEBUGuestCrashProcessDump@23@PEAX@Z`
- size: `356`
- prototype: `int(ComputeService::Management::Details *__hidden this, const unsigned __int16 *, const struct ComputeService::Management::GuestCrashProcessDump *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1401d8b84`

## callees

- `0x140024030`
- `0x140024f6c`
- `0x14012d08c`
- `0x14012d1f8`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14012d137`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14012d137`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14012d1b6`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14012d1b6`
- `api-ms-win-core-debug-minidump-l1-1-0!MiniDumpWriteDump` at `0x14012d169`
- `api-ms-win-core-debug-minidump-l1-1-0!MiniDumpWriteDump` at `0x14012d169`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x14012d0df`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x14012d0df`

## string_xrefs

- `0x14012d115`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14012d185`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`

## pseudocode

```c
__int64 __fastcall ComputeService::Management::Details::CaptureProcessDump(
        ComputeService::Management::Details *this,
        const unsigned __int16 *a2,
        const struct ComputeService::Management::GuestCrashProcessDump *a3,
        void *a4)
{
  const unsigned __int16 *v5; // rcx
  __int64 File2; // rax
  HANDLE v9; // rsi
  unsigned int LastErrorMsg; // ebx
  MINIDUMP_TYPE v11; // ebx
  DWORD ProcessId; // eax
  char FileInformation[8]; // [rsp+40h] [rbp-38h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  hFile = (HANDLE)-1LL;
  v5 = a2 + 4;
  if ( *((_QWORD *)a2 + 4) > 7u )
    v5 = *(const unsigned __int16 **)v5;
  File2 = CreateFile2(v5, 2032127, 5);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    File2);
  v9 = hFile;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v11 = *(_DWORD *)a2;
    ProcessId = GetProcessId(a3);
    if ( MiniDumpWriteDump(a3, ProcessId, v9, v11, 0, 0, 0) )
    {
      LastErrorMsg = 0;
    }
    else
    {
      FileInformation[0] = 1;
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x29D,
                       (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
                       "process: %ws",
                       (const char *)this);
      SetFileInformationByHandle(hFile, FileDispositionInfo, FileInformation, 1u);
    }
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x294,
                     (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
                     "process: %ws",
                     (const char *)this);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x14012d08c  mov     [rsp+arg_18], rbx
0x14012d091  push    rbp
0x14012d092  push    rsi
0x14012d093  push    rdi
0x14012d094  sub     rsp, 60h
0x14012d098  mov     rax, cs:__security_cookie
0x14012d09f  xor     rax, rsp
0x14012d0a2  mov     [rsp+78h+var_28], rax
0x14012d0a7  mov     rdi, rcx
0x14012d0aa  mov     [rsp+78h+hFile], 0FFFFFFFFFFFFFFFFh
0x14012d0b3  lea     rcx, [rdx+8]
0x14012d0b7  mov     rbp, r8
0x14012d0ba  cmp     qword ptr [rcx+18h], 7
0x14012d0bf  mov     rbx, rdx
0x14012d0c2  jbe     short loc_14012D0C7
0x14012d0c4  mov     rcx, [rcx]
0x14012d0c7  mov     r9d, 1
0x14012d0cd  mov     [rsp+78h+ExceptionParam], 0
0x14012d0d6  mov     edx, 1F01FFh
0x14012d0db  lea     r8d, [r9+4]
0x14012d0df  call    cs:__imp_CreateFile2
0x14012d0e6  nop     dword ptr [rax+rax+00h]
0x14012d0eb  mov     rdx, rax
0x14012d0ee  lea     rcx, [rsp+78h+hFile]
0x14012d0f3  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14012d0f8  mov     rsi, [rsp+78h+hFile]
0x14012d0fd  lea     rax, [rsi+1]
0x14012d101  test    rax, 0FFFFFFFFFFFFFFFEh
0x14012d107  jnz     short loc_14012D132
0x14012d109  mov     rcx, [rsp+78h]; this
0x14012d10e  lea     r9, aProcessWs; "process: %ws"
0x14012d115  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14012d11c  mov     [rsp+78h+ExceptionParam], rdi; char *
0x14012d121  mov     edx, 294h; void *
0x14012d126  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14012d12b  mov     ebx, eax
0x14012d12d  jmp     loc_14012D1C6
0x14012d132  mov     ebx, [rbx]
0x14012d134  mov     rcx, rbp; Process
0x14012d137  call    cs:__imp_GetProcessId
0x14012d13e  nop     dword ptr [rax+rax+00h]
0x14012d143  mov     [rsp+78h+CallbackParam], 0; CallbackParam
0x14012d14c  mov     r9d, ebx; DumpType
0x14012d14f  mov     edx, eax; ProcessId
0x14012d151  mov     [rsp+78h+UserStreamParam], 0; UserStreamParam
0x14012d15a  mov     r8, rsi; hFile
0x14012d15d  mov     [rsp+78h+ExceptionParam], 0; ExceptionParam
0x14012d166  mov     rcx, rbp; hProcess
0x14012d169  call    cs:__imp_MiniDumpWriteDump
0x14012d170  nop     dword ptr [rax+rax+00h]
0x14012d175  test    eax, eax
0x14012d177  jnz     short loc_14012D1C4
0x14012d179  mov     rcx, [rsp+78h]; this
0x14012d17e  lea     r9, aProcessWs; "process: %ws"
0x14012d185  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14012d18c  mov     [rsp+78h+ExceptionParam], rdi; char *
0x14012d191  mov     edx, 29Dh; void *
0x14012d196  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14012d19b  mov     rcx, [rsp+78h+hFile]; hFile
0x14012d1a0  lea     r8, [rsp+78h+FileInformation]; lpFileInformation
0x14012d1a5  mov     r9d, 1; dwBufferSize
0x14012d1ab  mov     [rsp+78h+FileInformation], 1
0x14012d1b0  mov     ebx, eax
0x14012d1b2  lea     edx, [r9+3]; FileInformationClass
0x14012d1b6  call    cs:__imp_SetFileInformationByHandle
0x14012d1bd  nop     dword ptr [rax+rax+00h]
0x14012d1c2  jmp     short loc_14012D1C6
0x14012d1c4  xor     ebx, ebx
0x14012d1c6  lea     rcx, [rsp+78h+hFile]; void *
0x14012d1cb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14012d1d0  mov     eax, ebx
0x14012d1d2  mov     rcx, [rsp+78h+var_28]
0x14012d1d7  xor     rcx, rsp; StackCookie
0x14012d1da  call    __security_check_cookie
0x14012d1df  mov     rbx, [rsp+78h+arg_18]
0x14012d1e7  add     rsp, 60h
0x14012d1eb  pop     rdi
0x14012d1ec  pop     rsi
0x14012d1ed  pop     rbp
0x14012d1ee  retn
```
