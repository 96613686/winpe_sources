# InitiateRecovery

- ea: `0x1800a8f64`
- end: `0x1800a90b3`
- name: `InitiateRecovery`
- size: `335`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800a90bc`

## callees

- `0x180007fd8`
- `0x18001c368`
- `0x1800540d4`
- `0x1800540e0`
- `0x1800540ec`
- `0x1800552d1`
- `0x1800a8f64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThread` at `0x1800a906a`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThread` at `0x1800a906a`
- `ntdll!DbgPrintEx` at `0x1800a8fa1`
- `ntdll!DbgPrintEx` at `0x1800a8ff1`
- `ntdll!DbgPrintEx` at `0x1800a9031`
- `ntdll!DbgPrintEx` at `0x1800a8fa1`
- `ntdll!DbgPrintEx` at `0x1800a8ff1`
- `ntdll!DbgPrintEx` at `0x1800a9031`

## string_xrefs

- `0x1800a8fb7`: `kernel32.dll`

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
0x1800a8f64  mov     qword ptr [rsp+ThreadId], r8
0x1800a8f69  mov     [rsp+arg_8], rdx
0x1800a8f6e  push    rbx
0x1800a8f6f  sub     rsp, 40h
0x1800a8f73  mov     [rsp+48h+ThreadId], 0
0x1800a8f7b  mov     rbx, rcx
0x1800a8f7e  test    rcx, rcx
0x1800a8f81  jnz     short loc_1800A8FB7
0x1800a8f83  call    GetCurrentProcessId_0
0x1800a8f88  mov     r9d, eax
0x1800a8f8b  mov     dword ptr [rsp+48h+lpParameter], 0BDh
0x1800a8f93  lea     r8, aWerRecoveryUUE_0; "WER/Recovery/%u:%u: ERROR Invalid proce"...
0x1800a8f9a  xor     edx, edx; Level
0x1800a8f9c  mov     ecx, 96h; ComponentId
0x1800a8fa1  call    cs:__imp_DbgPrintEx
0x1800a8fa8  nop     dword ptr [rax+rax+00h]
0x1800a8fad  mov     eax, 80070057h
0x1800a8fb2  jmp     loc_1800A90AC
0x1800a8fb7  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800a8fbe  call    GetModuleHandleW_0
0x1800a8fc3  test    rax, rax
0x1800a8fc6  jnz     short loc_1800A8FFF
0x1800a8fc8  call    GetLastError_0
0x1800a8fcd  mov     ebx, eax
0x1800a8fcf  call    GetCurrentProcessId_0
0x1800a8fd4  mov     r9d, eax
0x1800a8fd7  mov     [rsp+48h+dwCreationFlags], ebx
0x1800a8fdb  lea     r8, aWerCrashapiUUE_9; "WER/CrashAPI/%u:%u: ERROR GetModuleHand"...
0x1800a8fe2  mov     dword ptr [rsp+48h+lpParameter], 0FD4h
0x1800a8fea  xor     edx, edx; Level
0x1800a8fec  mov     ecx, 96h; ComponentId
0x1800a8ff1  call    cs:__imp_DbgPrintEx
0x1800a8ff8  nop     dword ptr [rax+rax+00h]
0x1800a8ffd  jmp     short loc_1800A9013
0x1800a8fff  lea     rdx, aWerpinitiatere; "WerpInitiateRemoteRecovery"
0x1800a9006  mov     rcx, rax; hModule
0x1800a9009  call    GetProcAddress_0
0x1800a900e  test    rax, rax
0x1800a9011  jnz     short loc_1800A9044
0x1800a9013  call    GetCurrentProcessId_0
0x1800a9018  mov     r9d, eax
0x1800a901b  mov     dword ptr [rsp+48h+lpParameter], 0DBh
0x1800a9023  lea     r8, aWerRecoveryUUE_4; "WER/Recovery/%u:%u: ERROR WerpGetRecove"...
0x1800a902a  xor     edx, edx; Level
0x1800a902c  mov     ecx, 96h; ComponentId
0x1800a9031  call    cs:__imp_DbgPrintEx
0x1800a9038  nop     dword ptr [rax+rax+00h]
0x1800a903d  mov     ebx, 0D0000139h
0x1800a9042  jmp     short loc_1800A90AA
0x1800a9044  lea     rcx, [rsp+48h+ThreadId]
0x1800a9049  mov     r9, rax; lpStartAddress
0x1800a904c  mov     [rsp+48h+lpThreadId], rcx; lpThreadId
0x1800a9051  xor     r8d, r8d; dwStackSize
0x1800a9054  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800a905c  mov     rcx, rbx; hProcess
0x1800a905f  xor     edx, edx; lpThreadAttributes
0x1800a9061  mov     [rsp+48h+lpParameter], 0; lpParameter
0x1800a906a  call    cs:__imp_CreateRemoteThread
0x1800a9071  nop     dword ptr [rax+rax+00h]
0x1800a9076  mov     [rsp+48h+arg_8], rax
0x1800a907b  inc     rax
0x1800a907e  cmp     rax, 1
0x1800a9082  ja      short loc_1800A909E
0x1800a9084  call    GetLastError_0
0x1800a9089  mov     ecx, eax; unsigned int
0x1800a908b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a9090  lea     rcx, [rsp+48h+arg_8]
0x1800a9095  mov     ebx, eax
0x1800a9097  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a909c  jmp     short loc_1800A90AA
0x1800a909e  lea     rcx, [rsp+48h+arg_8]
0x1800a90a3  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a90a8  xor     ebx, ebx
0x1800a90aa  mov     eax, ebx
0x1800a90ac  add     rsp, 40h
0x1800a90b0  pop     rbx
0x1800a90b1  retn
```
