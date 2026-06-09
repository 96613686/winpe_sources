# StorageService::GetStorageCardAppMetadata(_STORAGE_DEVICE_TYPE,ulong,_GUID *)

- ea: `0x180024334`
- end: `0x180024479`
- name: `?GetStorageCardAppMetadata@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAU_GUID@@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800209d4`

## callees

- `0x18000d030`
- `0x180022e78`
- `0x180024334`
- `0x18003b1b4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024456`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024456`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180024387`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180024387`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180024404`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180024404`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800243f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800243f0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002442b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002442b`

## pseudocode

```c
__int64 __fastcall StorageService::GetStorageCardAppMetadata(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4)
{
  int AppMetadataFilePath; // ebx
  DWORD FileAttributesW; // eax
  HANDLE FileW; // rax
  void *v8; // rdi
  __int64 *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Buffer[20]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  NumberOfBytesRead = 0;
  memset(Buffer, 0, sizeof(Buffer));
  AppMetadataFilePath = StorageService::GetAppMetadataFilePath(a1, a2, a3, FileName);
  if ( AppMetadataFilePath >= 0 )
  {
    FileAttributesW = GetFileAttributesW(FileName);
    if ( FileAttributesW == -1 )
      return (unsigned int)-2147467259;
    if ( (FileAttributesW & 0x10) == 0
      || (AppMetadataFilePath = RecursiveUtil::DeleteDirectoryTree(
                                  (RecursiveUtil *)FileName,
                                  (const unsigned __int16 *)1,
                                  0,
                                  0,
                                  0,
                                  dwFlagsAndAttributes),
          AppMetadataFilePath >= 0) )
    {
      FileW = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0, 0);
      v8 = FileW;
      if ( FileW == (HANDLE)-1LL )
        return (unsigned int)-2147467259;
      if ( GetFileSize(FileW, 0) >= 0x14
        && ReadFile(v8, Buffer, 0x14u, &NumberOfBytesRead, 0)
        && NumberOfBytesRead >= 0x14
        && *(_DWORD *)Buffer >= 0x14u )
      {
        *a4 = *(_OWORD *)&Buffer[4];
      }
      else
      {
        AppMetadataFilePath = -2147467259;
      }
      CloseHandle(v8);
    }
  }
  return (unsigned int)AppMetadataFilePath;
}

```

## disassembly

```asm
0x180024334  push    rbp
0x180024336  push    rbx
0x180024337  push    rsi
0x180024338  push    rdi
0x180024339  lea     rbp, [rsp-188h]
0x180024341  sub     rsp, 288h
0x180024348  mov     rax, cs:__security_cookie
0x18002434f  xor     rax, rsp
0x180024352  mov     [rbp+1A0h+var_30], rax
0x180024359  xor     eax, eax
0x18002435b  mov     rsi, r9
0x18002435e  xorps   xmm0, xmm0
0x180024361  mov     [rsp+2A0h+var_248], eax
0x180024365  lea     r9, [rsp+2A0h+FileName]
0x18002436a  mov     [rsp+2A0h+NumberOfBytesRead], eax
0x18002436e  movups  [rsp+2A0h+Buffer], xmm0
0x180024373  call    ?GetAppMetadataFilePath@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAG@Z; StorageService::GetAppMetadataFilePath(_STORAGE_DEVICE_TYPE,ulong,ushort *)
0x180024378  mov     ebx, eax
0x18002437a  test    eax, eax
0x18002437c  js      loc_18002445C
0x180024382  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x180024387  call    cs:__imp_GetFileAttributesW
0x18002438d  cmp     eax, 0FFFFFFFFh
0x180024390  jnz     short loc_18002439C
0x180024392  mov     ebx, 80004005h
0x180024397  jmp     loc_18002445C
0x18002439c  test    al, 10h
0x18002439e  jz      short loc_1800243C7
0x1800243a0  xor     r9d, r9d; struct _FILETIME *
0x1800243a3  mov     qword ptr [rsp+2A0h+dwCreationDisposition], 0; __int64 *
0x1800243ac  xor     r8d, r8d; unsigned int
0x1800243af  lea     rcx, [rsp+2A0h+FileName]; this
0x1800243b4  lea     edx, [r9+1]; unsigned __int16 *
0x1800243b8  call    ?DeleteDirectoryTree@RecursiveUtil@@YAJPEBGKPEAU_FILETIME@@PEA_J2@Z; RecursiveUtil::DeleteDirectoryTree(ushort const *,ulong,_FILETIME *,__int64 *,__int64 *)
0x1800243bd  mov     ebx, eax
0x1800243bf  test    eax, eax
0x1800243c1  js      loc_18002445C
0x1800243c7  mov     [rsp+2A0h+hTemplateFile], 0; hTemplateFile
0x1800243d0  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x1800243d5  mov     dword ptr [rsp+2A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800243dd  xor     r9d, r9d; lpSecurityAttributes
0x1800243e0  xor     r8d, r8d; dwShareMode
0x1800243e3  mov     [rsp+2A0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800243eb  mov     edx, 80000000h; dwDesiredAccess
0x1800243f0  call    cs:__imp_CreateFileW
0x1800243f6  mov     rdi, rax
0x1800243f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800243fd  jz      short loc_180024392
0x1800243ff  xor     edx, edx; lpFileSizeHigh
0x180024401  mov     rcx, rax; hFile
0x180024404  call    cs:__imp_GetFileSize
0x18002440a  cmp     eax, 14h
0x18002440d  jb      short loc_18002444E
0x18002440f  lea     r9, [rsp+2A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180024414  mov     qword ptr [rsp+2A0h+dwCreationDisposition], 0; lpOverlapped
0x18002441d  mov     r8d, 14h; nNumberOfBytesToRead
0x180024423  lea     rdx, [rsp+2A0h+Buffer]; lpBuffer
0x180024428  mov     rcx, rdi; hFile
0x18002442b  call    cs:__imp_ReadFile
0x180024431  test    eax, eax
0x180024433  jz      short loc_18002444E
0x180024435  cmp     [rsp+2A0h+NumberOfBytesRead], 14h
0x18002443a  jb      short loc_18002444E
0x18002443c  cmp     dword ptr [rsp+2A0h+Buffer], 14h
0x180024441  jb      short loc_18002444E
0x180024443  movups  xmm0, [rsp+2A0h+Buffer+4]
0x180024448  movdqu  xmmword ptr [rsi], xmm0
0x18002444c  jmp     short loc_180024453
0x18002444e  mov     ebx, 80004005h
0x180024453  mov     rcx, rdi; hObject
0x180024456  call    cs:__imp_CloseHandle
0x18002445c  mov     eax, ebx
0x18002445e  mov     rcx, [rbp+1A0h+var_30]
0x180024465  xor     rcx, rsp; StackCookie
0x180024468  call    __security_check_cookie
0x18002446d  add     rsp, 288h
0x180024474  pop     rdi
0x180024475  pop     rsi
0x180024476  pop     rbx
0x180024477  pop     rbp
0x180024478  retn
```
