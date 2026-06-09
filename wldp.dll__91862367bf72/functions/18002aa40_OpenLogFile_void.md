# OpenLogFile(void)

- ea: `0x18002aa40`
- end: `0x18002ab24`
- name: `?OpenLogFile@@YAJXZ`
- size: `228`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002b670`

## callees

- `0x180018434`
- `0x18001942c`
- `0x18002aa40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aaf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aaf0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002aae6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002aae6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002aab7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002aab7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002aa61`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002aa61`

## string_xrefs

- `0x18002aa69`: `%SystemRoot%\System32\CodeIntegrity\Data\Non-Production Errors.txt`
- `0x18002aadc`: `// Security Watermark Test Log\n\n// This log file describes test failures from the Security Watermark Test.\n// If you see this log file, it means that this device is not ready to ship\n// because some of the production self tests are failing.  If this is a pre-production\n// device, this is an expected result and this file can be ignored (or deleted).  If this\n// is supposed to be a production ready device, check the log below to identify tests that\n// are failing, and see the Securit`

## pseudocode

```c
__int64 OpenLogFile(void)
{
  WCHAR *v0; // rdi
  signed int v1; // ebx
  char IsStateSeparationEnabled; // al
  const WCHAR *v3; // rcx
  int v4; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  LPCWSTR lpFileName; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  v1 = 0;
  lpFileName = 0;
  if ( hFile == (HANDLE)-1LL )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v3 = L"%SystemDrive%\\data\\systemdata\\etw\\Non-Production Errors.txt";
    if ( !IsStateSeparationEnabled )
      v3 = L"%SystemRoot%\\System32\\CodeIntegrity\\Data\\Non-Production Errors.txt";
    v4 = ExpandRequiredPaths(v3, (unsigned __int16 **)&lpFileName);
    v0 = (WCHAR *)lpFileName;
    v1 = v4;
    if ( v4 < 0 )
      goto LABEL_10;
    FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    hFile = FileW;
    if ( FileW == (HANDLE)-1LL
      || !WriteFile(
            FileW,
            "// Security Watermark Test Log\r\n"
            "\r\n"
            "// This log file describes test failures from the Security Watermark Test.\r\n"
            "// If you see this log file, it means that this device is not ready to ship\r\n"
            "// because some of the production self tests are failing.  If this is a pre-production\r\n"
            "// device, this is an expected result and this file can be ignored (or deleted).  If this\r\n"
            "// is supposed to be a production ready device, check the log below to identify tests that\r\n"
            "// are failing, and see the Security Watermark documentation for information on how to fix the\r\n"
            "// issues identified by these tests.\r\n"
            "\r\n",
            0x252u,
            0,
            0) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 < 0 )
LABEL_10:
        CloseLogFile();
    }
  }
  LocalFree(v0);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18002aa40  mov     [rsp+arg_8], rbx
0x18002aa45  push    rdi
0x18002aa46  sub     rsp, 40h
0x18002aa4a  xor     edi, edi
0x18002aa4c  xor     ebx, ebx
0x18002aa4e  cmp     cs:hFile, 0FFFFFFFFFFFFFFFFh
0x18002aa56  mov     [rsp+48h+lpFileName], rdi
0x18002aa5b  jnz     loc_18002AB0E
0x18002aa61  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002aa67  test    al, al
0x18002aa69  lea     rdx, Src; "%SystemRoot%\\System32\\CodeIntegrity\\"...
0x18002aa70  lea     rcx, aSystemdriveDat; "%SystemDrive%\\data\\systemdata\\etw\\N"...
0x18002aa77  cmovz   rcx, rdx; lpSrc
0x18002aa7b  lea     rdx, [rsp+48h+lpFileName]; unsigned __int16 **
0x18002aa80  call    ?ExpandRequiredPaths@@YAJPEBGPEAPEAG@Z; ExpandRequiredPaths(ushort const *,ushort * *)
0x18002aa85  mov     rdi, [rsp+48h+lpFileName]
0x18002aa8a  mov     ebx, eax
0x18002aa8c  test    eax, eax
0x18002aa8e  js      short loc_18002AB09
0x18002aa90  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002aa99  xor     r9d, r9d; lpSecurityAttributes
0x18002aa9c  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002aaa4  xor     r8d, r8d; dwShareMode
0x18002aaa7  mov     edx, 40000000h; dwDesiredAccess
0x18002aaac  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18002aab4  mov     rcx, rdi; lpFileName
0x18002aab7  call    cs:__imp_CreateFileW
0x18002aabd  mov     cs:hFile, rax
0x18002aac4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002aac8  jz      short loc_18002AAF0
0x18002aaca  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002aacd  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x18002aad6  mov     r8d, 252h; nNumberOfBytesToWrite
0x18002aadc  lea     rdx, aSecurityWaterm; "// Security Watermark Test Log\r\n\r\n/"...
0x18002aae3  mov     rcx, rax; hFile
0x18002aae6  call    cs:__imp_WriteFile
0x18002aaec  test    eax, eax
0x18002aaee  jnz     short loc_18002AB0E
0x18002aaf0  call    cs:__imp_GetLastError
0x18002aaf6  mov     ebx, eax
0x18002aaf8  test    eax, eax
0x18002aafa  jle     short loc_18002AB05
0x18002aafc  movzx   ebx, ax
0x18002aaff  or      ebx, 80070000h
0x18002ab05  test    ebx, ebx
0x18002ab07  jns     short loc_18002AB0E
0x18002ab09  call    ?CloseLogFile@@YAXXZ; CloseLogFile(void)
0x18002ab0e  mov     rcx, rdi; hMem
0x18002ab11  call    cs:__imp_LocalFree
0x18002ab17  mov     eax, ebx
0x18002ab19  mov     rbx, [rsp+48h+arg_8]
0x18002ab1e  add     rsp, 40h
0x18002ab22  pop     rdi
0x18002ab23  retn
```
