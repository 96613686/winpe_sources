# PfSvWriteBufferEx

- ea: `0x180023244`
- end: `0x180023414`
- name: `PfSvWriteBufferEx`
- size: `464`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, int)`
- caller_count: `22`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180022058`
- `0x1800351f4`
- `0x180050378`
- `0x18005478c`
- `0x18005c2dc`
- `0x180063b74`
- `0x180063c68`
- `0x180068c0c`
- `0x18006bf88`
- `0x180070fb4`
- `0x180074988`
- `0x18007da48`
- `0x180080400`
- `0x180089528`
- `0x180089cac`
- `0x18008a444`
- `0x18008bf30`
- `0x18008da60`
- `0x18008e9a8`
- `0x18008ec94`
- `0x1800add08`
- `0x1800b132c`

## callees

- `0x180023244`
- `0x18002341c`
- `0x180025f6c`
- `0x1800834e8`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180023388`
- `ntdll!NtQueryInformationThread` at `0x180023388`
- `ntdll!RtlNtStatusToDosError` at `0x1800233b3`
- `ntdll!RtlNtStatusToDosError` at `0x1800233b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023407`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002331a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002331a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023359`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023359`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023399`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800232b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800233f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800232b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800233f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800232ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800232ea`

## pseudocode

```c
__int64 __fastcall PfSvWriteBufferEx(LPWSTR pObjectName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, int a4)
{
  DWORD dwFlagsAndAttributes; // ebp
  HANDLE FileW; // rdi
  int v10; // esi
  DWORD LastError; // ebx
  HANDLE v12; // rax
  HANDLE CurrentThread; // rax
  int v15; // eax
  HANDLE v16; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-38h] BYREF
  int ThreadInformation; // [rsp+98h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  dwFlagsAndAttributes = (unsigned __int16)a4 | 0x200000;
  if ( (a4 & 0x20000) == 0 )
    dwFlagsAndAttributes = (unsigned __int16)a4;
  PFSV_PRINTF("// Writing file: %ws\n", pObjectName);
  FileW = CreateFileW(pObjectName, 0xC0000000, 0, 0, 2u, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError != 5 )
      return LastError;
    if ( (unsigned int)PfSvSetAdminOnlyPermissions(pObjectName) )
      return 5;
    FileW = CreateFileW(pObjectName, 0xC0000000, 0, 0, 2u, dwFlagsAndAttributes, 0);
    if ( FileW == (HANDLE)-1LL )
      return GetLastError();
  }
  v10 = 8;
  if ( (a4 & 0x10000) != 0 )
  {
    CurrentThread = GetCurrentThread();
    ThreadInformation = 0;
    v15 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
    if ( v15 < 0 )
      RtlNtStatusToDosError(v15);
    else
      v10 = ThreadInformation;
    v16 = GetCurrentThread();
    PfSetPagePriorityThread(v16);
  }
  if ( WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
    && NumberOfBytesWritten == nNumberOfBytesToWrite )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( v10 != 8 )
  {
    v12 = GetCurrentThread();
    PfSetPagePriorityThread(v12);
  }
  CloseHandle(FileW);
  return LastError;
}

```

## disassembly

```asm
0x180023244  mov     [rsp+arg_0], rbx
0x180023249  mov     [rsp+arg_8], rbp
0x18002324e  push    rsi
0x18002324f  push    rdi
0x180023250  push    r12
0x180023252  push    r14
0x180023254  push    r15
0x180023256  sub     rsp, 50h
0x18002325a  movzx   r10d, r9w
0x18002325e  mov     r12, rdx
0x180023261  mov     rdx, rcx
0x180023264  mov     [rsp+78h+NumberOfBytesWritten], 0
0x18002326c  mov     ebp, r10d
0x18002326f  mov     rsi, rcx
0x180023272  bts     ebp, 15h
0x180023276  lea     rcx, aWritingFileWs; "// Writing file: %ws\n"
0x18002327d  bt      r9d, 11h
0x180023282  mov     r15d, r9d
0x180023285  mov     r14d, r8d
0x180023288  cmovnb  ebp, r10d
0x18002328c  call    PFSV_PRINTF
0x180023291  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18002329a  xor     r9d, r9d; lpSecurityAttributes
0x18002329d  mov     [rsp+78h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x1800232a1  xor     r8d, r8d; dwShareMode
0x1800232a4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800232a9  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x1800232b1  mov     rcx, rsi; lpFileName
0x1800232b4  call    cs:__imp_CreateFileW
0x1800232ba  mov     rdi, rax
0x1800232bd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800232c1  jz      short loc_180023322
0x1800232c3  mov     esi, 8
0x1800232c8  bt      r15d, 10h
0x1800232cd  jb      loc_180023359
0x1800232d3  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800232d8  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x1800232e1  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800232e4  mov     rdx, r12; lpBuffer
0x1800232e7  mov     rcx, rdi; hFile
0x1800232ea  call    cs:__imp_WriteFile
0x1800232f0  test    eax, eax
0x1800232f2  jnz     short loc_18002334E
0x1800232f4  call    cs:__imp_GetLastError
0x1800232fa  mov     ebx, eax
0x1800232fc  cmp     esi, 8
0x1800232ff  jz      short loc_180023311
0x180023301  call    cs:__imp_GetCurrentThread
0x180023307  mov     rcx, rax; ThreadHandle
0x18002330a  mov     edx, esi
0x18002330c  call    PfSetPagePriorityThread
0x180023311  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180023315  jz      short loc_180023333
0x180023317  mov     rcx, rdi; hObject
0x18002331a  call    cs:__imp_CloseHandle
0x180023320  jmp     short loc_180023333
0x180023322  call    cs:__imp_GetLastError
0x180023328  mov     ebx, eax
0x18002332a  cmp     eax, 5
0x18002332d  jz      loc_1800233BB
0x180023333  lea     r11, [rsp+78h+var_28]
0x180023338  mov     eax, ebx
0x18002333a  mov     rbx, [r11+30h]
0x18002333e  mov     rbp, [r11+38h]
0x180023342  mov     rsp, r11
0x180023345  pop     r15
0x180023347  pop     r14
0x180023349  pop     r12
0x18002334b  pop     rdi
0x18002334c  pop     rsi
0x18002334d  retn
0x18002334e  cmp     [rsp+78h+NumberOfBytesWritten], r14d
0x180023353  jnz     short loc_1800232F4
0x180023355  xor     ebx, ebx
0x180023357  jmp     short loc_1800232FC
0x180023359  call    cs:__imp_GetCurrentThread
0x18002335f  mov     r9d, 4; ThreadInformationLength
0x180023365  mov     [rsp+78h+ThreadInformation], 0
0x180023370  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x180023378  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; ReturnLength
0x180023381  mov     rcx, rax; ThreadHandle
0x180023384  lea     edx, [r9+14h]; ThreadInformationClass
0x180023388  call    cs:__imp_NtQueryInformationThread
0x18002338e  test    eax, eax
0x180023390  js      short loc_1800233B1
0x180023392  mov     esi, [rsp+78h+ThreadInformation]
0x180023399  call    cs:__imp_GetCurrentThread
0x18002339f  mov     rcx, rax; ThreadHandle
0x1800233a2  mov     edx, 1
0x1800233a7  call    PfSetPagePriorityThread
0x1800233ac  jmp     loc_1800232D3
0x1800233b1  mov     ecx, eax; Status
0x1800233b3  call    cs:__imp_RtlNtStatusToDosError
0x1800233b9  jmp     short loc_180023399
0x1800233bb  mov     rcx, rsi; pObjectName
0x1800233be  call    PfSvSetAdminOnlyPermissions
0x1800233c3  test    eax, eax
0x1800233c5  jz      short loc_1800233D1
0x1800233c7  mov     ebx, 5
0x1800233cc  jmp     loc_180023333
0x1800233d1  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800233da  xor     r9d, r9d; lpSecurityAttributes
0x1800233dd  mov     [rsp+78h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x1800233e1  xor     r8d, r8d; dwShareMode
0x1800233e4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800233e9  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x1800233f1  mov     rcx, rsi; lpFileName
0x1800233f4  call    cs:__imp_CreateFileW
0x1800233fa  mov     rdi, rax
0x1800233fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023401  jnz     loc_1800232C3
0x180023407  call    cs:__imp_GetLastError
0x18002340d  mov     ebx, eax
0x18002340f  jmp     loc_180023333
```
