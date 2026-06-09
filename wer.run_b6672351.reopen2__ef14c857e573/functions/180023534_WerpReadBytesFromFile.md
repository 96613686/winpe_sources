# WerpReadBytesFromFile

- ea: `0x180023534`
- end: `0x1800235c0`
- name: `WerpReadBytesFromFile`
- size: `140`
- prototype: `__int64 __fastcall(LPDWORD lpNumberOfBytesRead, HANDLE hFile, LARGE_INTEGER liDistanceToMove, LPVOID lpBuffer, DWORD nNumberOfBytesToRead)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180048188`

## callees

- `0x18001c368`
- `0x180023534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235ab`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180023561`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180023561`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180023588`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180023588`

## pseudocode

```c
__int64 __fastcall WerpReadBytesFromFile(
        LPDWORD lpNumberOfBytesRead,
        HANDLE hFile,
        LARGE_INTEGER liDistanceToMove,
        LPVOID lpBuffer,
        DWORD nNumberOfBytesToRead)
{
  DWORD LastError; // eax

  *lpNumberOfBytesRead = 0;
  if ( SetFilePointerEx(hFile, liDistanceToMove, 0, 0)
    && ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, lpNumberOfBytesRead, 0) )
  {
    return 0;
  }
  LastError = GetLastError();
  return ERROR_HR_FROM_WIN32(LastError);
}

```

## disassembly

```asm
0x180023534  mov     [rsp+arg_0], rbx
0x180023539  mov     [rsp+arg_8], rsi
0x18002353e  push    rdi
0x18002353f  sub     rsp, 30h
0x180023543  mov     rax, r8
0x180023546  mov     dword ptr [rcx], 0
0x18002354c  mov     rbx, rdx
0x18002354f  mov     rsi, r9
0x180023552  mov     rdi, rcx
0x180023555  mov     rdx, rax; liDistanceToMove
0x180023558  mov     rcx, rbx; hFile
0x18002355b  xor     r9d, r9d; dwMoveMethod
0x18002355e  xor     r8d, r8d; lpNewFilePointer
0x180023561  call    cs:__imp_SetFilePointerEx
0x180023568  nop     dword ptr [rax+rax+00h]
0x18002356d  test    eax, eax
0x18002356f  jz      short loc_1800235AB
0x180023571  mov     r8d, [rsp+38h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180023576  mov     r9, rdi; lpNumberOfBytesRead
0x180023579  mov     rdx, rsi; lpBuffer
0x18002357c  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180023585  mov     rcx, rbx; hFile
0x180023588  call    cs:__imp_ReadFile
0x18002358f  nop     dword ptr [rax+rax+00h]
0x180023594  test    eax, eax
0x180023596  jz      short loc_1800235AB
0x180023598  xor     eax, eax
0x18002359a  mov     rbx, [rsp+38h+arg_0]
0x18002359f  mov     rsi, [rsp+38h+arg_8]
0x1800235a4  add     rsp, 30h
0x1800235a8  pop     rdi
0x1800235a9  retn
0x1800235ab  call    cs:__imp_GetLastError
0x1800235b2  nop     dword ptr [rax+rax+00h]
0x1800235b7  mov     ecx, eax; unsigned int
0x1800235b9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800235be  jmp     short loc_18002359A
```
