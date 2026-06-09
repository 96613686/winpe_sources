# DuplicateHandleInPid(void *,ulong,void * *)

- ea: `0x180008460`
- end: `0x18000850d`
- name: `?DuplicateHandleInPid@@YAJPEAXKPEAPEAX@Z`
- size: `173`
- prototype: `signed int __fastcall(HANDLE hSourceHandle, DWORD dwProcessId, LPHANDLE lpTargetHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800065d0`

## callees

- `0x180008460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000848d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000848d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084d4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800084ca`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800084ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800084a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800084a6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000847f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000847f`

## pseudocode

```c
signed int __fastcall DuplicateHandleInPid(HANDLE hSourceHandle, DWORD dwProcessId, LPHANDLE lpTargetHandle)
{
  HANDLE v5; // rdi
  signed int result; // eax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx

  v5 = OpenProcess(0x40u, 0, dwProcessId);
  if ( v5 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, hSourceHandle, v5, lpTargetHandle, 0, 0, 6u) )
    {
      v9 = 0;
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v5);
    return v9;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180008460  mov     [rsp+arg_8], rbx
0x180008465  mov     [rsp+arg_10], rsi
0x18000846a  push    rdi
0x18000846b  sub     rsp, 40h
0x18000846f  mov     rbx, r8
0x180008472  mov     rsi, rcx
0x180008475  mov     r8d, edx; dwProcessId
0x180008478  mov     ecx, 40h ; '@'; dwDesiredAccess
0x18000847d  xor     edx, edx; bInheritHandle
0x18000847f  call    cs:__imp_OpenProcess
0x180008485  mov     rdi, rax
0x180008488  test    rax, rax
0x18000848b  jnz     short loc_1800084A1
0x18000848d  call    cs:__imp_GetLastError
0x180008493  test    eax, eax
0x180008495  jle     short loc_1800084FD
0x180008497  movzx   eax, ax
0x18000849a  or      eax, 80070000h
0x18000849f  jmp     short loc_1800084FD
0x1800084a1  mov     [rsp+48h+arg_0], rbp
0x1800084a6  call    cs:__imp_GetCurrentProcess
0x1800084ac  xor     ebp, ebp
0x1800084ae  mov     [rsp+48h+dwOptions], 6; dwOptions
0x1800084b6  mov     rcx, rax; hSourceProcessHandle
0x1800084b9  mov     [rsp+48h+bInheritHandle], ebp; bInheritHandle
0x1800084bd  mov     r9, rbx; lpTargetHandle
0x1800084c0  mov     [rsp+48h+dwDesiredAccess], ebp; dwDesiredAccess
0x1800084c4  mov     r8, rdi; hTargetProcessHandle
0x1800084c7  mov     rdx, rsi; hSourceHandle
0x1800084ca  call    cs:__imp_DuplicateHandle
0x1800084d0  test    eax, eax
0x1800084d2  jnz     short loc_1800084EB
0x1800084d4  call    cs:__imp_GetLastError
0x1800084da  mov     ebx, eax
0x1800084dc  test    eax, eax
0x1800084de  jle     short loc_1800084ED
0x1800084e0  movzx   ebx, ax
0x1800084e3  or      ebx, 80070000h
0x1800084e9  jmp     short loc_1800084ED
0x1800084eb  mov     ebx, ebp
0x1800084ed  mov     rcx, rdi; hObject
0x1800084f0  call    cs:__imp_CloseHandle
0x1800084f6  mov     rbp, [rsp+48h+arg_0]
0x1800084fb  mov     eax, ebx
0x1800084fd  mov     rbx, [rsp+48h+arg_8]
0x180008502  mov     rsi, [rsp+48h+arg_10]
0x180008507  add     rsp, 40h
0x18000850b  pop     rdi
0x18000850c  retn
```
