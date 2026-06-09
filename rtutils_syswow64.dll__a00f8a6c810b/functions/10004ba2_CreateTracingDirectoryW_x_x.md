# CreateTracingDirectoryW(x,x)

- ea: `0x10004ba2`
- end: `0x10004d97`
- name: `_CreateTracingDirectoryW@8`
- size: `501`
- prototype: `ULONG __fastcall(PCWSTR DosPathName, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x10007954`

## callees

- `0x10004ba2`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x10004d16`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x10004d16`
- `ntdll!RtlNtStatusToDosError` at `0x10004c64`
- `ntdll!RtlNtStatusToDosError` at `0x10004c64`
- `ntdll!NtCreateFile` at `0x10004c3a`
- `ntdll!NtCreateFile` at `0x10004c3a`
- `ntdll!RtlFreeHeap` at `0x10004c59`
- `ntdll!RtlFreeHeap` at `0x10004c59`
- `ntdll!RtlReleaseRelativeName` at `0x10004c46`
- `ntdll!RtlReleaseRelativeName` at `0x10004c46`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x10004bd1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x10004bd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10004d2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10004d53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10004d2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10004d53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10004cc4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10004cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10004cbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10004d25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10004d4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10004cbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10004d25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10004d4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10004d84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10004d84`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x10004d7c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x10004d7c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10004c8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10004c8d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x10004ca7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x10004cda`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x10004ca7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x10004cda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004d60`

## pseudocode

```c
ULONG __fastcall CreateTracingDirectoryW(PCWSTR DosPathName, PHANDLE FileHandle)
{
  ULONG result; // eax
  PWSTR Buffer; // edi
  HANDLE ContainingDirectory; // eax
  int v6; // esi
  DWORD FinalPathNameByHandleW; // eax
  DWORD v8; // edi
  HANDLE ProcessHeap; // eax
  WCHAR *v10; // eax
  WCHAR *v11; // esi
  DWORD v12; // eax
  int v13; // ecx
  HANDLE v14; // eax
  DWORD LastError; // edi
  HANDLE v16; // eax
  SIZE_T v17; // [esp-4h] [ebp-5Ch]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [esp+10h] [ebp-48h] BYREF
  struct _RTL_RELATIVE_NAME_U DirectoryInfo; // [esp+28h] [ebp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [esp+38h] [ebp-20h] BYREF
  struct _UNICODE_STRING NtPathName; // [esp+40h] [ebp-18h] BYREF
  int v22; // [esp+48h] [ebp-10h]
  LPCWSTR lpFileName; // [esp+4Ch] [ebp-Ch]
  int v24; // [esp+50h] [ebp-8h]
  char FileInformation; // [esp+57h] [ebp-1h] BYREF

  lpFileName = DosPathName;
  v22 = 1;
  memset(&DirectoryInfo, 0, sizeof(DirectoryInfo));
  v24 = 0;
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, &DirectoryInfo) )
    return 3;
  Buffer = NtPathName.Buffer;
  if ( DirectoryInfo.RelativeName.Length )
  {
    NtPathName = DirectoryInfo.RelativeName;
    ContainingDirectory = DirectoryInfo.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    DirectoryInfo.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 24;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.SecurityQualityOfService = 0;
  v6 = NtCreateFile(FileHandle, 0xC0010000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 2u, 1u, 0, 0);
  RtlReleaseRelativeName(&DirectoryInfo);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v6 < 0 )
  {
    result = RtlNtStatusToDosError(v6);
    if ( result != 183 )
      return result;
    v22 = 0;
    *FileHandle = CreateFileW(lpFileName, 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
  }
  if ( *FileHandle == (void *)-1 || (FinalPathNameByHandleW = GetFinalPathNameByHandleW(*FileHandle, 0, 0, 0)) == 0 )
  {
    LastError = GetLastError();
    goto LABEL_28;
  }
  v8 = FinalPathNameByHandleW + 1;
  v17 = 2 * (FinalPathNameByHandleW + 1);
  ProcessHeap = GetProcessHeap();
  v10 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v17);
  v11 = v10;
  if ( !v10 )
  {
    LastError = 8;
    goto LABEL_28;
  }
  v12 = GetFinalPathNameByHandleW(*FileHandle, v10, v8, 0);
  if ( v12 )
  {
    if ( v12 >= 4 )
    {
      if ( *v11 != 92 || v11[1] != 92 || v11[2] != 63 || v11[3] != 92 )
      {
        v13 = 0;
        goto LABEL_20;
      }
      v24 = 4;
    }
    v13 = v24;
LABEL_20:
    if ( !__o__wcsnicmp(lpFileName, &v11[v13], v12 - v13) )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v11);
      return 0;
    }
    LastError = 267;
    goto LABEL_25;
  }
  LastError = GetLastError();
LABEL_25:
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v11);
LABEL_28:
  if ( v22 )
  {
    FileInformation = 1;
    SetFileInformationByHandle(*FileHandle, FileDispositionInfo, &FileInformation, 1u);
  }
  CloseHandle(*FileHandle);
  *FileHandle = (void *)-1;
  return LastError;
}

```

## disassembly

```asm
0x10004ba2  mov     edi, edi
0x10004ba4  push    ebp
0x10004ba5  mov     ebp, esp
0x10004ba7  sub     esp, 4Ch
0x10004baa  push    ebx
0x10004bab  push    esi
0x10004bac  push    edi
0x10004bad  xor     eax, eax
0x10004baf  mov     [ebp+lpFileName], ecx
0x10004bb2  lea     edi, [ebp+DirectoryInfo]
0x10004bb5  mov     [ebp+var_10], 1
0x10004bbc  stosd
0x10004bbd  xor     esi, esi
0x10004bbf  mov     ebx, edx
0x10004bc1  mov     [ebp+var_8], esi
0x10004bc4  stosd
0x10004bc5  stosd
0x10004bc6  stosd
0x10004bc7  lea     eax, [ebp+DirectoryInfo]
0x10004bca  push    eax; DirectoryInfo
0x10004bcb  push    esi; NtFileNamePart
0x10004bcc  lea     eax, [ebp+NtPathName]
0x10004bcf  push    eax; NtPathName
0x10004bd0  push    ecx; DosPathName
0x10004bd1  call    ds:__imp__RtlDosPathNameToNtPathName_U@16; RtlDosPathNameToNtPathName_U(x,x,x,x)
0x10004bd7  test    al, al
0x10004bd9  jnz     short loc_10004BE3
0x10004bdb  push    3
0x10004bdd  pop     eax
0x10004bde  jmp     loc_10004D92
0x10004be3  mov     ecx, dword ptr [ebp+DirectoryInfo.RelativeName.Length]
0x10004be6  mov     edi, [ebp+NtPathName.Buffer]
0x10004be9  test    cx, cx
0x10004bec  jz      short loc_10004BFC
0x10004bee  mov     eax, [ebp+DirectoryInfo.RelativeName.Buffer]
0x10004bf1  mov     [ebp+NtPathName.Buffer], eax
0x10004bf4  mov     eax, [ebp+DirectoryInfo.ContainingDirectory]
0x10004bf7  mov     dword ptr [ebp+NtPathName.Length], ecx
0x10004bfa  jmp     short loc_10004C01
0x10004bfc  mov     eax, esi
0x10004bfe  mov     [ebp+DirectoryInfo.ContainingDirectory], eax
0x10004c01  push    esi; EaLength
0x10004c02  push    esi; EaBuffer
0x10004c03  push    1; CreateOptions
0x10004c05  push    2; CreateDisposition
0x10004c07  push    1; ShareAccess
0x10004c09  mov     [ebp+ObjectAttributes.RootDirectory], eax
0x10004c0c  lea     eax, [ebp+NtPathName]
0x10004c0f  push    80h; FileAttributes
0x10004c14  push    esi; AllocationSize
0x10004c15  mov     [ebp+ObjectAttributes.ObjectName], eax
0x10004c18  lea     eax, [ebp+IoStatusBlock]
0x10004c1b  push    eax; IoStatusBlock
0x10004c1c  lea     eax, [ebp+ObjectAttributes]
0x10004c1f  mov     [ebp+ObjectAttributes.Length], 18h
0x10004c26  push    eax; ObjectAttributes
0x10004c27  push    0C0010000h; DesiredAccess
0x10004c2c  push    ebx; FileHandle
0x10004c2d  mov     [ebp+ObjectAttributes.Attributes], 40h ; '@'
0x10004c34  mov     [ebp+ObjectAttributes.SecurityDescriptor], esi
0x10004c37  mov     [ebp+ObjectAttributes.SecurityQualityOfService], esi
0x10004c3a  call    ds:__imp__NtCreateFile@44; NtCreateFile(x,x,x,x,x,x,x,x,x,x,x)
0x10004c40  mov     esi, eax
0x10004c42  lea     eax, [ebp+DirectoryInfo]
0x10004c45  push    eax; RelativeName
0x10004c46  call    ds:__imp__RtlReleaseRelativeName@4; RtlReleaseRelativeName(x)
0x10004c4c  mov     ecx, large fs:30h
0x10004c53  push    edi; P
0x10004c54  push    0; Flags
0x10004c56  push    dword ptr [ecx+18h]; HeapHandle
0x10004c59  call    ds:__imp__RtlFreeHeap@12; RtlFreeHeap(x,x,x)
0x10004c5f  test    esi, esi
0x10004c61  jns     short loc_10004C97
0x10004c63  push    esi; Status
0x10004c64  call    ds:__imp__RtlNtStatusToDosError@4; RtlNtStatusToDosError(x)
0x10004c6a  cmp     eax, 0B7h
0x10004c6f  jnz     loc_10004D92
0x10004c75  xor     esi, esi
0x10004c77  push    esi; hTemplateFile
0x10004c78  push    2000000h; dwFlagsAndAttributes
0x10004c7d  push    3; dwCreationDisposition
0x10004c7f  push    esi; lpSecurityAttributes
0x10004c80  push    1; dwShareMode
0x10004c82  push    0C0000000h; dwDesiredAccess
0x10004c87  push    [ebp+lpFileName]; lpFileName
0x10004c8a  mov     [ebp+var_10], esi
0x10004c8d  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x10004c93  mov     [ebx], eax
0x10004c95  jmp     short loc_10004C99
0x10004c97  xor     esi, esi
0x10004c99  cmp     dword ptr [ebx], 0FFFFFFFFh
0x10004c9c  jz      loc_10004D60
0x10004ca2  push    esi; dwFlags
0x10004ca3  push    esi; cchFilePath
0x10004ca4  push    esi; lpszFilePath
0x10004ca5  push    dword ptr [ebx]; hFile
0x10004ca7  call    ds:__imp__GetFinalPathNameByHandleW@16; GetFinalPathNameByHandleW(x,x,x,x)
0x10004cad  mov     edi, eax
0x10004caf  test    edi, edi
0x10004cb1  jz      loc_10004D60
0x10004cb7  inc     edi
0x10004cb8  lea     ecx, [edi+edi]
0x10004cbb  push    ecx; dwBytes
0x10004cbc  push    esi; dwFlags
0x10004cbd  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10004cc3  push    eax; hHeap
0x10004cc4  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x10004cca  mov     esi, eax
0x10004ccc  test    esi, esi
0x10004cce  jz      loc_10004D5B
0x10004cd4  push    0; dwFlags
0x10004cd6  push    edi; cchFilePath
0x10004cd7  push    esi; lpszFilePath
0x10004cd8  push    dword ptr [ebx]; hFile
0x10004cda  call    ds:__imp__GetFinalPathNameByHandleW@16; GetFinalPathNameByHandleW(x,x,x,x)
0x10004ce0  test    eax, eax
0x10004ce2  jz      short loc_10004D41
0x10004ce4  push    4
0x10004ce6  pop     edx
0x10004ce7  cmp     eax, edx
0x10004ce9  jb      short loc_10004D09
0x10004ceb  push    5Ch ; '\'
0x10004ced  pop     ecx
0x10004cee  cmp     [esi], cx
0x10004cf1  jnz     short loc_10004D36
0x10004cf3  cmp     [esi+2], cx
0x10004cf7  jnz     short loc_10004D36
0x10004cf9  cmp     word ptr [esi+4], 3Fh ; '?'
0x10004cfe  jnz     short loc_10004D36
0x10004d00  cmp     [esi+6], cx
0x10004d04  jnz     short loc_10004D36
0x10004d06  mov     [ebp+var_8], edx
0x10004d09  mov     ecx, [ebp+var_8]
0x10004d0c  sub     eax, ecx
0x10004d0e  push    eax
0x10004d0f  lea     eax, [esi+ecx*2]
0x10004d12  push    eax
0x10004d13  push    [ebp+lpFileName]
0x10004d16  call    ds:__imp___o__wcsnicmp
0x10004d1c  add     esp, 0Ch
0x10004d1f  test    eax, eax
0x10004d21  jnz     short loc_10004D3A
0x10004d23  push    esi; lpMem
0x10004d24  push    eax; dwFlags
0x10004d25  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10004d2b  push    eax; hHeap
0x10004d2c  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10004d32  xor     eax, eax
0x10004d34  jmp     short loc_10004D92
0x10004d36  xor     ecx, ecx
0x10004d38  jmp     short loc_10004D0C
0x10004d3a  mov     edi, 10Bh
0x10004d3f  jmp     short loc_10004D49
0x10004d41  call    ds:__imp__GetLastError@0; GetLastError()
0x10004d47  mov     edi, eax
0x10004d49  push    esi; lpMem
0x10004d4a  push    0; dwFlags
0x10004d4c  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10004d52  push    eax; hHeap
0x10004d53  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10004d59  jmp     short loc_10004D68
0x10004d5b  push    8
0x10004d5d  pop     edi
0x10004d5e  jmp     short loc_10004D68
0x10004d60  call    ds:__imp__GetLastError@0; GetLastError()
0x10004d66  mov     edi, eax
0x10004d68  cmp     [ebp+var_10], 0
0x10004d6c  jz      short loc_10004D82
0x10004d6e  push    1; dwBufferSize
0x10004d70  lea     eax, [ebp+FileInformation]
0x10004d73  mov     [ebp+FileInformation], 1
0x10004d77  push    eax; lpFileInformation
0x10004d78  push    4; FileInformationClass
0x10004d7a  push    dword ptr [ebx]; hFile
0x10004d7c  call    ds:__imp__SetFileInformationByHandle@16; SetFileInformationByHandle(x,x,x,x)
0x10004d82  push    dword ptr [ebx]; hObject
0x10004d84  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10004d8a  mov     dword ptr [ebx], 0FFFFFFFFh
0x10004d90  mov     eax, edi
0x10004d92  pop     edi
0x10004d93  pop     esi
0x10004d94  pop     ebx
0x10004d95  leave
0x10004d96  retn
```
