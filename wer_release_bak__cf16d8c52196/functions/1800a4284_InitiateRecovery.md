# InitiateRecovery

- ea: `0x1800a4284`
- end: `0x1800a43ba`
- name: `InitiateRecovery`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800a43c0`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180051b64`
- `0x180051b70`
- `0x180051b7c`
- `0x180052d61`
- `0x1800a4284`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThread` at `0x1800a4378`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThread` at `0x1800a4378`
- `ntdll!DbgPrintEx` at `0x1800a42c1`
- `ntdll!DbgPrintEx` at `0x1800a430b`
- `ntdll!DbgPrintEx` at `0x1800a4345`
- `ntdll!DbgPrintEx` at `0x1800a42c1`
- `ntdll!DbgPrintEx` at `0x1800a430b`
- `ntdll!DbgPrintEx` at `0x1800a4345`

## string_xrefs

- `0x1800a42d1`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall InitiateRecovery(HANDLE hProcess, char *a2, __int64 a3)
{
  DWORD CurrentProcessId_0; // eax
  HMODULE ModuleHandleW_0; // rax
  DWORD v7; // ebx
  DWORD v8; // eax
  ULONG (__stdcall *WerpInitiateRemoteRecovery)(PVOID); // rax
  DWORD v10; // eax
  unsigned int v11; // ebx
  DWORD LastError_0; // eax
  char *v13; // [rsp+58h] [rbp+10h] BYREF
  DWORD ThreadId; // [rsp+60h] [rbp+18h] BYREF
  int v15; // [rsp+64h] [rbp+1Ch]

  v15 = HIDWORD(a3);
  v13 = a2;
  ThreadId = 0;
  if ( !hProcess )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR Invalid process handle passed\n", CurrentProcessId_0, 189);
    return 2147942487LL;
  }
  ModuleHandleW_0 = GetModuleHandleW_0(L"kernel32.dll");
  if ( ModuleHandleW_0 )
  {
    WerpInitiateRemoteRecovery = (ULONG (__stdcall *)(PVOID))GetProcAddress_0(
                                                               ModuleHandleW_0,
                                                               "WerpInitiateRemoteRecovery");
    if ( WerpInitiateRemoteRecovery )
    {
      v13 = (char *)CreateRemoteThread(hProcess, 0, 0, WerpInitiateRemoteRecovery, 0, 0, &ThreadId);
      if ( v13 == (char *)-1LL || v13 + 1 == (char *)1 )
      {
        LastError_0 = GetLastError_0();
        v11 = ERROR_HR_FROM_WIN32(LastError_0);
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v13);
      }
      else
      {
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v13);
        return 0;
      }
      return v11;
    }
  }
  else
  {
    v7 = GetLastError_0();
    v8 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR GetModuleHandle failed for kernel32 with %u\n", v8, 4052, v7);
  }
  v10 = GetCurrentProcessId_0();
  DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR WerpGetRecoveryEntryPointInProcess returned NULL\n", v10, 219);
  return (unsigned int)-805306055;
}

```

## disassembly

```asm
0x1800a4284  mov     qword ptr [rsp+ThreadId], r8
0x1800a4289  mov     [rsp+arg_8], rdx
0x1800a428e  push    rbx
0x1800a428f  sub     rsp, 40h
0x1800a4293  mov     [rsp+48h+ThreadId], 0
0x1800a429b  mov     rbx, rcx
0x1800a429e  test    rcx, rcx
0x1800a42a1  jnz     short loc_1800A42D1
0x1800a42a3  call    GetCurrentProcessId_0
0x1800a42a8  mov     r9d, eax
0x1800a42ab  mov     dword ptr [rsp+48h+lpParameter], 0BDh
0x1800a42b3  lea     r8, aWerRecoveryUUE_0; "WER/Recovery/%u:%u: ERROR Invalid proce"...
0x1800a42ba  xor     edx, edx; Level
0x1800a42bc  mov     ecx, 96h; ComponentId
0x1800a42c1  call    cs:__imp_DbgPrintEx
0x1800a42c7  mov     eax, 80070057h
0x1800a42cc  jmp     loc_1800A43B4
0x1800a42d1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800a42d8  call    GetModuleHandleW_0
0x1800a42dd  test    rax, rax
0x1800a42e0  jnz     short loc_1800A4313
0x1800a42e2  call    GetLastError_0
0x1800a42e7  mov     ebx, eax
0x1800a42e9  call    GetCurrentProcessId_0
0x1800a42ee  mov     r9d, eax
0x1800a42f1  mov     [rsp+48h+dwCreationFlags], ebx
0x1800a42f5  lea     r8, aWerCrashapiUUE_9; "WER/CrashAPI/%u:%u: ERROR GetModuleHand"...
0x1800a42fc  mov     dword ptr [rsp+48h+lpParameter], 0FD4h
0x1800a4304  xor     edx, edx; Level
0x1800a4306  mov     ecx, 96h; ComponentId
0x1800a430b  call    cs:__imp_DbgPrintEx
0x1800a4311  jmp     short loc_1800A4327
0x1800a4313  lea     rdx, aWerpinitiatere; "WerpInitiateRemoteRecovery"
0x1800a431a  mov     rcx, rax; hModule
0x1800a431d  call    GetProcAddress_0
0x1800a4322  test    rax, rax
0x1800a4325  jnz     short loc_1800A4352
0x1800a4327  call    GetCurrentProcessId_0
0x1800a432c  mov     r9d, eax
0x1800a432f  mov     dword ptr [rsp+48h+lpParameter], 0DBh
0x1800a4337  lea     r8, aWerRecoveryUUE_4; "WER/Recovery/%u:%u: ERROR WerpGetRecove"...
0x1800a433e  xor     edx, edx; Level
0x1800a4340  mov     ecx, 96h; ComponentId
0x1800a4345  call    cs:__imp_DbgPrintEx
0x1800a434b  mov     ebx, 0D0000139h
0x1800a4350  jmp     short loc_1800A43B2
0x1800a4352  lea     rcx, [rsp+48h+ThreadId]
0x1800a4357  mov     r9, rax; lpStartAddress
0x1800a435a  mov     [rsp+48h+lpThreadId], rcx; lpThreadId
0x1800a435f  xor     r8d, r8d; dwStackSize
0x1800a4362  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800a436a  mov     rcx, rbx; hProcess
0x1800a436d  xor     edx, edx; lpThreadAttributes
0x1800a436f  mov     [rsp+48h+lpParameter], 0; lpParameter
0x1800a4378  call    cs:__imp_CreateRemoteThread
0x1800a437e  mov     [rsp+48h+arg_8], rax
0x1800a4383  inc     rax
0x1800a4386  cmp     rax, 1
0x1800a438a  ja      short loc_1800A43A6
0x1800a438c  call    GetLastError_0
0x1800a4391  mov     ecx, eax; unsigned int
0x1800a4393  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a4398  lea     rcx, [rsp+48h+arg_8]
0x1800a439d  mov     ebx, eax
0x1800a439f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a43a4  jmp     short loc_1800A43B2
0x1800a43a6  lea     rcx, [rsp+48h+arg_8]
0x1800a43ab  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a43b0  xor     ebx, ebx
0x1800a43b2  mov     eax, ebx
0x1800a43b4  add     rsp, 40h
0x1800a43b8  pop     rbx
0x1800a43b9  retn
```
