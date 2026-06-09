# CreateTracingDirectoryW

- ea: `0x180006948`
- end: `0x180006bed`
- name: `CreateTracingDirectoryW`
- size: `677`
- prototype: `ULONG __fastcall(LPCWSTR lpFileName, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006c6c`

## callees

- `0x180006948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006b51`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006b51`
- `ntdll!RtlFreeHeap` at `0x180006a69`
- `ntdll!RtlFreeHeap` at `0x180006a69`
- `ntdll!RtlNtStatusToDosError` at `0x180006a75`
- `ntdll!RtlNtStatusToDosError` at `0x180006a75`
- `ntdll!RtlReleaseRelativeName` at `0x180006a51`
- `ntdll!RtlReleaseRelativeName` at `0x180006a51`
- `ntdll!NtCreateFile` at `0x180006a45`
- `ntdll!NtCreateFile` at `0x180006a45`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180006996`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180006996`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006af3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006af3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ae5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ae5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006aac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006aac`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180006acf`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180006b11`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180006acf`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180006b11`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180006bc1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180006bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ba4`

## pseudocode

```c
ULONG __fastcall CreateTracingDirectoryW(LPCWSTR lpFileName, PHANDLE FileHandle)
{
  ULONG result; // eax
  PWSTR Buffer; // rdi
  int v6; // r14d
  HANDLE ContainingDirectory; // rax
  int v8; // ebx
  DWORD v9; // eax
  DWORD v10; // edi
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v13; // rax
  WCHAR *v14; // rbx
  DWORD FinalPathNameByHandleW; // eax
  unsigned int v16; // ecx
  HANDLE v17; // rax
  DWORD LastError; // edi
  HANDLE v19; // rax
  void *v20; // rcx
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-49h] BYREF
  struct _RTL_RELATIVE_NAME_U DirectoryInfo; // [rsp+80h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-19h] BYREF
  char FileInformation; // [rsp+130h] [rbp+77h] BYREF

  NtPathName = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&DirectoryInfo, 0, sizeof(DirectoryInfo));
  if ( !RtlDosPathNameToNtPathName_U(lpFileName, &NtPathName, 0, &DirectoryInfo) )
    return 3;
  Buffer = NtPathName.Buffer;
  v6 = 1;
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
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtCreateFile(FileHandle, 0xC0010000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 2u, 1u, 0, 0);
  RtlReleaseRelativeName(&DirectoryInfo);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v8 < 0 )
  {
    result = RtlNtStatusToDosError(v8);
    if ( result != 183 )
      return result;
    v6 = 0;
    *FileHandle = CreateFileW(lpFileName, 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
  }
  if ( *FileHandle == (void *)-1LL || (v9 = GetFinalPathNameByHandleW(*FileHandle, 0, 0, 0)) == 0 )
  {
    LastError = GetLastError();
  }
  else
  {
    v10 = v9 + 1;
    v11 = 2LL * (v9 + 1);
    ProcessHeap = GetProcessHeap();
    v13 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v11);
    v14 = v13;
    if ( v13 )
    {
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(*FileHandle, v13, v10, 0);
      if ( FinalPathNameByHandleW )
      {
        v16 = 0;
        if ( FinalPathNameByHandleW >= 4 && *v14 == 92 && v14[1] == 92 && v14[2] == 63 && v14[3] == 92 )
          v16 = 4;
        if ( !(unsigned int)_o__wcsnicmp(lpFileName, &v14[v16], FinalPathNameByHandleW - v16) )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v14);
          return 0;
        }
        LastError = 267;
      }
      else
      {
        LastError = GetLastError();
      }
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v14);
    }
    else
    {
      LastError = 8;
    }
  }
  if ( v6 )
  {
    v20 = *FileHandle;
    FileInformation = 1;
    SetFileInformationByHandle(v20, FileDispositionInfo, &FileInformation, 1u);
  }
  CloseHandle(*FileHandle);
  result = LastError;
  *FileHandle = (void *)-1LL;
  return result;
}

```

## disassembly

```asm
0x180006948  push    rbp
0x18000694a  push    rbx
0x18000694b  push    rsi
0x18000694c  push    rdi
0x18000694d  push    r12
0x18000694f  push    r13
0x180006951  push    r14
0x180006953  push    r15
0x180006955  lea     rbp, [rsp-1Fh]
0x18000695a  sub     rsp, 0D8h
0x180006961  xorps   xmm0, xmm0
0x180006964  lea     r9, [rbp+57h+DirectoryInfo]; DirectoryInfo
0x180006968  mov     rsi, rdx
0x18000696b  xorps   xmm1, xmm1
0x18000696e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006972  xor     eax, eax
0x180006974  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180006978  xor     r8d, r8d; NtFileNamePart
0x18000697b  mov     r15, rcx
0x18000697e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180006982  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180006986  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18000698a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000698e  movups  xmmword ptr [rbp+57h+DirectoryInfo.RelativeName.Length], xmm0
0x180006992  movups  xmmword ptr [rbp+57h+DirectoryInfo.ContainingDirectory], xmm0
0x180006996  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000699c  xor     r12d, r12d
0x18000699f  test    al, al
0x1800069a1  jnz     short loc_1800069AD
0x1800069a3  lea     eax, [r12+3]
0x1800069a8  jmp     loc_180006BD9
0x1800069ad  movzx   eax, [rbp+57h+DirectoryInfo.RelativeName.Length]
0x1800069b1  mov     r13d, 1
0x1800069b7  mov     rdi, [rbp+57h+NtPathName.Buffer]
0x1800069bb  mov     r14d, r13d
0x1800069be  test    ax, ax
0x1800069c1  jz      short loc_1800069E3
0x1800069c3  mov     [rbp+57h+NtPathName.Length], ax
0x1800069c7  mov     eax, dword ptr [rbp+57h+DirectoryInfo.RelativeName.MaximumLength]
0x1800069ca  mov     dword ptr [rbp+57h+NtPathName.MaximumLength], eax
0x1800069cd  movzx   eax, word ptr [rbp+57h+DirectoryInfo.RelativeName+6]
0x1800069d1  mov     word ptr [rbp+57h+NtPathName+6], ax
0x1800069d5  mov     rax, [rbp+57h+DirectoryInfo.RelativeName.Buffer]
0x1800069d9  mov     [rbp+57h+NtPathName.Buffer], rax
0x1800069dd  mov     rax, [rbp+57h+DirectoryInfo.ContainingDirectory]
0x1800069e1  jmp     short loc_1800069EA
0x1800069e3  mov     rax, r12
0x1800069e6  mov     [rbp+57h+DirectoryInfo.ContainingDirectory], rax
0x1800069ea  mov     [rsp+110h+EaLength], r12d; EaLength
0x1800069ef  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800069f3  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x1800069f8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800069fc  mov     [rsp+110h+CreateOptions], r13d; CreateOptions
0x180006a01  xorps   xmm0, xmm0
0x180006a04  mov     [rsp+110h+CreateDisposition], 2; CreateDisposition
0x180006a0c  mov     edx, 0C0010000h; DesiredAccess
0x180006a11  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180006a15  mov     rcx, rsi; FileHandle
0x180006a18  mov     [rsp+110h+ShareAccess], r13d; ShareAccess
0x180006a1d  lea     rax, [rbp+57h+NtPathName]
0x180006a21  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x180006a29  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x180006a2e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180006a35  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180006a3c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006a40  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006a45  call    cs:__imp_NtCreateFile
0x180006a4b  lea     rcx, [rbp+57h+DirectoryInfo]; RelativeName
0x180006a4f  mov     ebx, eax
0x180006a51  call    cs:__imp_RtlReleaseRelativeName
0x180006a57  mov     rcx, gs:60h
0x180006a60  mov     r8, rdi; P
0x180006a63  xor     edx, edx; Flags
0x180006a65  mov     rcx, [rcx+30h]; HeapHandle
0x180006a69  call    cs:__imp_RtlFreeHeap
0x180006a6f  test    ebx, ebx
0x180006a71  jns     short loc_180006AB5
0x180006a73  mov     ecx, ebx; Status
0x180006a75  call    cs:__imp_RtlNtStatusToDosError
0x180006a7b  cmp     eax, 0B7h
0x180006a80  jnz     loc_180006BD9
0x180006a86  mov     qword ptr [rsp+110h+ShareAccess], r12; hTemplateFile
0x180006a8b  xor     r9d, r9d; lpSecurityAttributes
0x180006a8e  mov     [rsp+110h+FileAttributes], 2000000h; dwFlagsAndAttributes
0x180006a96  mov     r8d, r13d; dwShareMode
0x180006a99  mov     edx, 0C0000000h; dwDesiredAccess
0x180006a9e  mov     dword ptr [rsp+110h+AllocationSize], 3; dwCreationDisposition
0x180006aa6  mov     rcx, r15; lpFileName
0x180006aa9  mov     r14d, r12d
0x180006aac  call    cs:__imp_CreateFileW
0x180006ab2  mov     [rsi], rax
0x180006ab5  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180006ab9  mov     ebx, 4
0x180006abe  jz      loc_180006BA4
0x180006ac4  mov     rcx, [rsi]; hFile
0x180006ac7  xor     r9d, r9d; dwFlags
0x180006aca  xor     r8d, r8d; cchFilePath
0x180006acd  xor     edx, edx; lpszFilePath
0x180006acf  call    cs:__imp_GetFinalPathNameByHandleW
0x180006ad5  test    eax, eax
0x180006ad7  jz      loc_180006BA4
0x180006add  lea     edi, [rax+1]
0x180006ae0  mov     ebx, edi
0x180006ae2  add     rbx, rbx
0x180006ae5  call    cs:__imp_GetProcessHeap
0x180006aeb  mov     r8, rbx; dwBytes
0x180006aee  xor     edx, edx; dwFlags
0x180006af0  mov     rcx, rax; hHeap
0x180006af3  call    cs:__imp_HeapAlloc
0x180006af9  mov     rbx, rax
0x180006afc  test    rax, rax
0x180006aff  jz      loc_180006B9D
0x180006b05  mov     rcx, [rsi]; hFile
0x180006b08  xor     r9d, r9d; dwFlags
0x180006b0b  mov     r8d, edi; cchFilePath
0x180006b0e  mov     rdx, rax; lpszFilePath
0x180006b11  call    cs:__imp_GetFinalPathNameByHandleW
0x180006b17  test    eax, eax
0x180006b19  jz      short loc_180006B7A
0x180006b1b  mov     edx, 4
0x180006b20  mov     ecx, r12d
0x180006b23  cmp     eax, edx
0x180006b25  jb      short loc_180006B43
0x180006b27  cmp     word ptr [rbx], 5Ch ; '\'
0x180006b2b  jnz     short loc_180006B43
0x180006b2d  cmp     word ptr [rbx+2], 5Ch ; '\'
0x180006b32  jnz     short loc_180006B43
0x180006b34  cmp     word ptr [rbx+4], 3Fh ; '?'
0x180006b39  jnz     short loc_180006B43
0x180006b3b  cmp     word ptr [rbx+6], 5Ch ; '\'
0x180006b40  cmovz   ecx, edx
0x180006b43  sub     eax, ecx
0x180006b45  mov     r8d, eax
0x180006b48  mov     eax, ecx
0x180006b4a  mov     rcx, r15
0x180006b4d  lea     rdx, [rbx+rax*2]
0x180006b51  call    cs:__imp__o__wcsnicmp
0x180006b57  test    eax, eax
0x180006b59  jnz     short loc_180006B73
0x180006b5b  call    cs:__imp_GetProcessHeap
0x180006b61  mov     r8, rbx; lpMem
0x180006b64  xor     edx, edx; dwFlags
0x180006b66  mov     rcx, rax; hHeap
0x180006b69  call    cs:__imp_HeapFree
0x180006b6f  xor     eax, eax
0x180006b71  jmp     short loc_180006BD9
0x180006b73  mov     edi, 10Bh
0x180006b78  jmp     short loc_180006B82
0x180006b7a  call    cs:__imp_GetLastError
0x180006b80  mov     edi, eax
0x180006b82  call    cs:__imp_GetProcessHeap
0x180006b88  mov     r8, rbx; lpMem
0x180006b8b  xor     edx, edx; dwFlags
0x180006b8d  mov     rcx, rax; hHeap
0x180006b90  call    cs:__imp_HeapFree
0x180006b96  mov     ebx, 4
0x180006b9b  jmp     short loc_180006BAC
0x180006b9d  mov     edi, 8
0x180006ba2  jmp     short loc_180006B96
0x180006ba4  call    cs:__imp_GetLastError
0x180006baa  mov     edi, eax
0x180006bac  test    r14d, r14d
0x180006baf  jz      short loc_180006BC7
0x180006bb1  mov     rcx, [rsi]; hFile
0x180006bb4  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180006bb8  mov     r9d, r13d; dwBufferSize
0x180006bbb  mov     [rbp+57h+FileInformation], r13b
0x180006bbf  mov     edx, ebx; FileInformationClass
0x180006bc1  call    cs:__imp_SetFileInformationByHandle
0x180006bc7  mov     rcx, [rsi]; hObject
0x180006bca  call    cs:__imp_CloseHandle
0x180006bd0  mov     eax, edi
0x180006bd2  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180006bd9  add     rsp, 0D8h
0x180006be0  pop     r15
0x180006be2  pop     r14
0x180006be4  pop     r13
0x180006be6  pop     r12
0x180006be8  pop     rdi
0x180006be9  pop     rsi
0x180006bea  pop     rbx
0x180006beb  pop     rbp
0x180006bec  retn
```
