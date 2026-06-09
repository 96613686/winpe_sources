# CreateTracingDirectoryA

- ea: `0x180005ba4`
- end: `0x180005e92`
- name: `CreateTracingDirectoryA`
- size: `750`
- prototype: `ULONG __fastcall(char *String1, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005f70`

## callees

- `0x180005ba4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180005ded`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180005ded`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005c3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005c3d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005bff`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005bff`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180005c1e`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180005c1e`
- `ntdll!RtlFreeHeap` at `0x180005d0a`
- `ntdll!RtlFreeHeap` at `0x180005d0a`
- `ntdll!RtlNtStatusToDosError` at `0x180005d16`
- `ntdll!RtlNtStatusToDosError` at `0x180005d16`
- `ntdll!RtlReleaseRelativeName` at `0x180005cf2`
- `ntdll!RtlReleaseRelativeName` at `0x180005cf2`
- `ntdll!NtCreateFile` at `0x180005ce6`
- `ntdll!NtCreateFile` at `0x180005ce6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180005c32`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180005c32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005d92`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005d92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005df7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005df7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e6f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180005d4e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180005d4e`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180005e66`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180005e66`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x180005d72`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x180005db0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x180005d72`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x180005db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e45`

## pseudocode

```c
ULONG __fastcall CreateTracingDirectoryA(char *String1, PHANDLE FileHandle)
{
  __int64 v2; // rax
  __int64 v5; // rbx
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  ULONG result; // eax
  BOOLEAN v9; // bl
  int v10; // r12d
  PWSTR Buffer; // rdi
  HANDLE ContainingDirectory; // rax
  int v13; // ebx
  DWORD v14; // eax
  DWORD v15; // r15d
  HANDLE ProcessHeap; // rax
  CHAR *v17; // rax
  CHAR *v18; // rdi
  DWORD FinalPathNameByHandleA; // eax
  unsigned int v20; // ecx
  HANDLE v21; // rax
  DWORD LastError; // ebx
  HANDLE v23; // rax
  void *v24; // rcx
  _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-59h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-49h] BYREF
  _RTL_RELATIVE_NAME_U DirectoryInfo; // [rsp+80h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-19h] BYREF
  char FileInformation; // [rsp+130h] [rbp+77h] BYREF

  v2 = -1;
  NtPathName = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&DirectoryInfo, 0, sizeof(DirectoryInfo));
  do
    ++v2;
  while ( String1[v2] );
  v5 = v2 + 1;
  v6 = (WCHAR *)malloc(2 * (v2 + 1));
  v7 = v6;
  if ( !v6 )
    return 8;
  _o_mbstowcs(v6, String1, v5);
  v9 = RtlDosPathNameToNtPathName_U(v7, &NtPathName, 0, &DirectoryInfo);
  free(v7);
  if ( !v9 )
    return 3;
  v10 = 1;
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
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = NtCreateFile(FileHandle, 0xC0010000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 2u, 1u, 0, 0);
  RtlReleaseRelativeName(&DirectoryInfo);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v13 < 0 )
  {
    result = RtlNtStatusToDosError(v13);
    if ( result != 183 )
      return result;
    v10 = 0;
    *FileHandle = CreateFileA(String1, 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
  }
  if ( *FileHandle == (void *)-1LL || (v14 = GetFinalPathNameByHandleA(*FileHandle, 0, 0, 0)) == 0 )
  {
    LastError = GetLastError();
  }
  else
  {
    v15 = v14 + 1;
    ProcessHeap = GetProcessHeap();
    v17 = (CHAR *)HeapAlloc(ProcessHeap, 0, v15);
    v18 = v17;
    if ( v17 )
    {
      FinalPathNameByHandleA = GetFinalPathNameByHandleA(*FileHandle, v17, v15, 0);
      if ( FinalPathNameByHandleA )
      {
        v20 = 0;
        if ( FinalPathNameByHandleA >= 4 && *v18 == 92 && v18[1] == 92 && v18[2] == 63 && v18[3] == 92 )
          v20 = 4;
        if ( !_strnicmp(String1, &v18[v20], FinalPathNameByHandleA - v20) )
        {
          v21 = GetProcessHeap();
          HeapFree(v21, 0, v18);
          return 0;
        }
        LastError = 267;
      }
      else
      {
        LastError = GetLastError();
      }
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v18);
    }
    else
    {
      LastError = 8;
    }
  }
  if ( v10 )
  {
    v24 = *FileHandle;
    FileInformation = 1;
    SetFileInformationByHandle(v24, FileDispositionInfo, &FileInformation, 1u);
  }
  CloseHandle(*FileHandle);
  result = LastError;
  *FileHandle = (void *)-1LL;
  return result;
}

```

## disassembly

```asm
0x180005ba4  push    rbp
0x180005ba6  push    rbx
0x180005ba7  push    rsi
0x180005ba8  push    rdi
0x180005ba9  push    r12
0x180005bab  push    r13
0x180005bad  push    r14
0x180005baf  push    r15
0x180005bb1  lea     rbp, [rsp-1Fh]
0x180005bb6  sub     rsp, 0D8h
0x180005bbd  xorps   xmm0, xmm0
0x180005bc0  xor     eax, eax
0x180005bc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005bc6  xorps   xmm1, xmm1
0x180005bc9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180005bcd  xor     r13d, r13d
0x180005bd0  mov     rsi, rdx
0x180005bd3  mov     r14, rcx
0x180005bd6  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180005bda  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180005bde  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180005be2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180005be6  movups  xmmword ptr [rbp+57h+DirectoryInfo.RelativeName.Length], xmm0
0x180005bea  movups  xmmword ptr [rbp+57h+DirectoryInfo.ContainingDirectory], xmm0
0x180005bee  inc     rax
0x180005bf1  cmp     [rcx+rax], r13b
0x180005bf5  jnz     short loc_180005BEE
0x180005bf7  lea     rbx, [rax+1]
0x180005bfb  lea     rcx, [rbx+rbx]; Size
0x180005bff  call    cs:__imp_malloc
0x180005c05  mov     rdi, rax
0x180005c08  test    rax, rax
0x180005c0b  jnz     short loc_180005C15
0x180005c0d  lea     eax, [rdi+8]
0x180005c10  jmp     loc_180005E7E
0x180005c15  mov     r8, rbx
0x180005c18  mov     rdx, r14
0x180005c1b  mov     rcx, rdi
0x180005c1e  call    cs:__imp__o_mbstowcs
0x180005c24  lea     r9, [rbp+57h+DirectoryInfo]; DirectoryInfo
0x180005c28  xor     r8d, r8d; NtFileNamePart
0x180005c2b  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180005c2f  mov     rcx, rdi; DosPathName
0x180005c32  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180005c38  mov     rcx, rdi; Block
0x180005c3b  mov     bl, al
0x180005c3d  call    cs:__imp_free
0x180005c43  test    bl, bl
0x180005c45  jnz     short loc_180005C51
0x180005c47  mov     eax, 3
0x180005c4c  jmp     loc_180005E7E
0x180005c51  movzx   eax, [rbp+57h+DirectoryInfo.RelativeName.Length]
0x180005c55  mov     r12d, 1
0x180005c5b  mov     rdi, [rbp+57h+NtPathName.Buffer]
0x180005c5f  test    ax, ax
0x180005c62  jz      short loc_180005C84
0x180005c64  mov     [rbp+57h+NtPathName.Length], ax
0x180005c68  mov     eax, dword ptr [rbp+57h+DirectoryInfo.RelativeName.MaximumLength]
0x180005c6b  mov     dword ptr [rbp+57h+NtPathName.MaximumLength], eax
0x180005c6e  movzx   eax, word ptr [rbp+57h+DirectoryInfo.RelativeName+6]
0x180005c72  mov     word ptr [rbp+57h+NtPathName+6], ax
0x180005c76  mov     rax, [rbp+57h+DirectoryInfo.RelativeName.Buffer]
0x180005c7a  mov     [rbp+57h+NtPathName.Buffer], rax
0x180005c7e  mov     rax, [rbp+57h+DirectoryInfo.ContainingDirectory]
0x180005c82  jmp     short loc_180005C8B
0x180005c84  mov     rax, r13
0x180005c87  mov     [rbp+57h+DirectoryInfo.ContainingDirectory], rax
0x180005c8b  mov     [rsp+110h+EaLength], r13d; EaLength
0x180005c90  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180005c94  mov     [rsp+110h+EaBuffer], r13; EaBuffer
0x180005c99  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180005c9d  mov     [rsp+110h+CreateOptions], r12d; CreateOptions
0x180005ca2  xorps   xmm0, xmm0
0x180005ca5  mov     [rsp+110h+CreateDisposition], 2; CreateDisposition
0x180005cad  mov     edx, 0C0010000h; DesiredAccess
0x180005cb2  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180005cb6  mov     rcx, rsi; FileHandle
0x180005cb9  mov     [rsp+110h+ShareAccess], r12d; ShareAccess
0x180005cbe  lea     rax, [rbp+57h+NtPathName]
0x180005cc2  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x180005cca  mov     [rsp+110h+AllocationSize], r13; AllocationSize
0x180005ccf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180005cd6  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180005cdd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180005ce1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005ce6  call    cs:__imp_NtCreateFile
0x180005cec  lea     rcx, [rbp+57h+DirectoryInfo]; RelativeName
0x180005cf0  mov     ebx, eax
0x180005cf2  call    cs:__imp_RtlReleaseRelativeName
0x180005cf8  mov     rcx, gs:60h
0x180005d01  mov     r8, rdi; P
0x180005d04  xor     edx, edx; Flags
0x180005d06  mov     rcx, [rcx+30h]; HeapHandle
0x180005d0a  call    cs:__imp_RtlFreeHeap
0x180005d10  test    ebx, ebx
0x180005d12  jns     short loc_180005D57
0x180005d14  mov     ecx, ebx; Status
0x180005d16  call    cs:__imp_RtlNtStatusToDosError
0x180005d1c  cmp     eax, 0B7h
0x180005d21  jnz     loc_180005E7E
0x180005d27  xor     r9d, r9d; lpSecurityAttributes
0x180005d2a  mov     qword ptr [rsp+110h+ShareAccess], r13; hTemplateFile
0x180005d2f  mov     [rsp+110h+FileAttributes], 2000000h; dwFlagsAndAttributes
0x180005d37  mov     edx, 0C0000000h; dwDesiredAccess
0x180005d3c  mov     rcx, r14; lpFileName
0x180005d3f  mov     dword ptr [rsp+110h+AllocationSize], 3; dwCreationDisposition
0x180005d47  mov     r12d, r13d
0x180005d4a  lea     r8d, [r9+1]; dwShareMode
0x180005d4e  call    cs:__imp_CreateFileA
0x180005d54  mov     [rsi], rax
0x180005d57  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180005d5b  mov     r15d, 4
0x180005d61  jz      loc_180005E45
0x180005d67  mov     rcx, [rsi]; hFile
0x180005d6a  xor     r9d, r9d; dwFlags
0x180005d6d  xor     r8d, r8d; cchFilePath
0x180005d70  xor     edx, edx; lpszFilePath
0x180005d72  call    cs:__imp_GetFinalPathNameByHandleA
0x180005d78  test    eax, eax
0x180005d7a  jz      loc_180005E45
0x180005d80  lea     r15d, [rax+1]
0x180005d84  call    cs:__imp_GetProcessHeap
0x180005d8a  mov     r8d, r15d; dwBytes
0x180005d8d  xor     edx, edx; dwFlags
0x180005d8f  mov     rcx, rax; hHeap
0x180005d92  call    cs:__imp_HeapAlloc
0x180005d98  mov     rdi, rax
0x180005d9b  test    rax, rax
0x180005d9e  jz      loc_180005E3A
0x180005da4  mov     rcx, [rsi]; hFile
0x180005da7  xor     r9d, r9d; dwFlags
0x180005daa  mov     r8d, r15d; cchFilePath
0x180005dad  mov     rdx, rax; lpszFilePath
0x180005db0  call    cs:__imp_GetFinalPathNameByHandleA
0x180005db6  test    eax, eax
0x180005db8  jz      short loc_180005E16
0x180005dba  mov     r15d, 4
0x180005dc0  mov     ecx, r13d
0x180005dc3  cmp     eax, r15d
0x180005dc6  jb      short loc_180005DE0
0x180005dc8  mov     dl, 5Ch ; '\'
0x180005dca  cmp     [rdi], dl
0x180005dcc  jnz     short loc_180005DE0
0x180005dce  cmp     [rdi+1], dl
0x180005dd1  jnz     short loc_180005DE0
0x180005dd3  cmp     byte ptr [rdi+2], 3Fh ; '?'
0x180005dd7  jnz     short loc_180005DE0
0x180005dd9  cmp     [rdi+3], dl
0x180005ddc  cmovz   ecx, r15d
0x180005de0  sub     eax, ecx
0x180005de2  mov     edx, ecx
0x180005de4  mov     r8d, eax; MaxCount
0x180005de7  add     rdx, rdi; String2
0x180005dea  mov     rcx, r14; String1
0x180005ded  call    cs:__imp__strnicmp
0x180005df3  test    eax, eax
0x180005df5  jnz     short loc_180005E0F
0x180005df7  call    cs:__imp_GetProcessHeap
0x180005dfd  mov     r8, rdi; lpMem
0x180005e00  xor     edx, edx; dwFlags
0x180005e02  mov     rcx, rax; hHeap
0x180005e05  call    cs:__imp_HeapFree
0x180005e0b  xor     eax, eax
0x180005e0d  jmp     short loc_180005E7E
0x180005e0f  mov     ebx, 10Bh
0x180005e14  jmp     short loc_180005E24
0x180005e16  call    cs:__imp_GetLastError
0x180005e1c  mov     ebx, eax
0x180005e1e  mov     r15d, 4
0x180005e24  call    cs:__imp_GetProcessHeap
0x180005e2a  mov     r8, rdi; lpMem
0x180005e2d  xor     edx, edx; dwFlags
0x180005e2f  mov     rcx, rax; hHeap
0x180005e32  call    cs:__imp_HeapFree
0x180005e38  jmp     short loc_180005E4D
0x180005e3a  mov     ebx, 8
0x180005e3f  lea     r15d, [rbx-4]
0x180005e43  jmp     short loc_180005E4D
0x180005e45  call    cs:__imp_GetLastError
0x180005e4b  mov     ebx, eax
0x180005e4d  test    r12d, r12d
0x180005e50  jz      short loc_180005E6C
0x180005e52  mov     rcx, [rsi]; hFile
0x180005e55  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180005e59  mov     r9d, 1; dwBufferSize
0x180005e5f  mov     [rbp+57h+FileInformation], 1
0x180005e63  mov     edx, r15d; FileInformationClass
0x180005e66  call    cs:__imp_SetFileInformationByHandle
0x180005e6c  mov     rcx, [rsi]; hObject
0x180005e6f  call    cs:__imp_CloseHandle
0x180005e75  mov     eax, ebx
0x180005e77  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180005e7e  add     rsp, 0D8h
0x180005e85  pop     r15
0x180005e87  pop     r14
0x180005e89  pop     r13
0x180005e8b  pop     r12
0x180005e8d  pop     rdi
0x180005e8e  pop     rsi
0x180005e8f  pop     rbx
0x180005e90  pop     rbp
0x180005e91  retn
```
