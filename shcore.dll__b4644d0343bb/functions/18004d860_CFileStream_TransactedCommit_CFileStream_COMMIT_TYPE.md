# CFileStream::_TransactedCommit(CFileStream::COMMIT_TYPE)

- ea: `0x18004d860`
- end: `0x18004daab`
- name: `?_TransactedCommit@CFileStream@@AEAAJW4COMMIT_TYPE@1@@Z`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001a4c0`

## callees

- `0x18001a408`
- `0x18001ac20`
- `0x18001c82c`
- `0x18004d860`
- `0x18005dca8`
- `0x18005de48`
- `0x180066910`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004da62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004da62`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004da2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004da2b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004da59`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004da59`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x18004d908`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x18004d908`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004da14`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004da14`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004d9c9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004d9c9`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x18004d9a2`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x18004d9a2`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004d929`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004d929`

## pseudocode

```c
__int64 __fastcall CFileStream::_TransactedCommit(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rcx
  int v4; // ebx
  HANDLE v5; // rbx
  char v6; // r14
  __int64 v7; // rcx
  const WCHAR *v8; // rax
  const WCHAR *v9; // r15
  const WCHAR *v10; // rcx
  int Error; // eax
  HANDLE FileW; // rbx
  HANDLE hFile; // [rsp+40h] [rbp-40h] BYREF
  DWORD FileSystemFlags; // [rsp+48h] [rbp-38h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-30h] BYREF
  __int128 v17; // [rsp+60h] [rbp-20h]
  __int64 v18; // [rsp+70h] [rbp-10h]

  v1 = a1 + 4272;
  CFileStream::Detach(*(CFileStream **)(a1 + 4272));
  SafeRelease<CFileStream>(v1);
  v3 = *(_QWORD *)(a1 + 4232);
  v18 = 0;
  FileInformation = 0;
  hFile = 0;
  v17 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v3 + 24LL))(v3, &hFile);
  if ( v4 >= 0 )
  {
    v5 = hFile;
    FileSystemFlags = 0;
    if ( !GetVolumeInformationByHandleW(hFile, 0, 0, 0, 0, &FileSystemFlags, 0, 0) || (FileSystemFlags & 8) != 0 )
    {
      v6 = 0;
    }
    else
    {
      v6 = 1;
      GetFileInformationByHandleEx(v5, FileBasicInfo, &FileInformation, 0x28u);
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 4232) + 32LL))(*(_QWORD *)(a1 + 4232));
    v7 = *(_QWORD *)(a1 + 4232);
    *(_QWORD *)(a1 + 4232) = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = *(const WCHAR **)(a1 + 4184);
    v9 = &SourceString;
    v10 = &SourceString;
    *(_BYTE *)(a1 + 4288) = 0;
    if ( v8 )
      v10 = v8;
    if ( ReplaceFileW(v10, *(LPCWSTR *)(a1 + 4248), 0, 2u, 0, 0)
      || (Error = ResultFromKnownLastError(), v4 = Error, Error >= 0) )
    {
      if ( v6 )
      {
        if ( *(_QWORD *)(a1 + 4184) )
          v9 = *(const WCHAR **)(a1 + 4184);
        FileW = CreateFileW(v9, 0xC0000000, 7u, 0, 3u, 0, 0);
        if ( FileW != (HANDLE)-1LL )
        {
          hFile = 0;
          GetSystemTimeAsFileTime((LPFILETIME)&hFile);
          *(_QWORD *)&v17 = (unsigned int)hFile + 20000000LL + ((unsigned __int64)HIDWORD(hFile) << 32);
          SetFileInformationByHandle(FileW, FileBasicInfo, &FileInformation, 0x28u);
          CloseHandle(FileW);
        }
      }
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(a1 + 4248);
      *(_BYTE *)(a1 + 4240) = 0;
      return (unsigned int)CFileStream::OpenFile((CFileStream *)a1);
    }
    else if ( (unsigned int)(Error + 2147023720) > 1 )
    {
      DeleteFileW(*(LPCWSTR *)(a1 + 4248));
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(a1 + 4248);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004d860  mov     [rsp-28h+arg_8], rbx
0x18004d865  mov     [rsp-28h+arg_10], rsi
0x18004d86a  push    rbp
0x18004d86b  push    rdi
0x18004d86c  push    r12
0x18004d86e  push    r14
0x18004d870  push    r15
0x18004d872  mov     rbp, rsp
0x18004d875  sub     rsp, 80h
0x18004d87c  mov     rax, cs:__security_cookie
0x18004d883  xor     rax, rsp
0x18004d886  mov     [rbp+var_8], rax
0x18004d88a  lea     rbx, [rcx+10B0h]
0x18004d891  mov     rdi, rcx
0x18004d894  mov     rcx, [rbx]; this
0x18004d897  call    ?Detach@CFileStream@@QEAAJXZ; CFileStream::Detach(void)
0x18004d89c  mov     rcx, rbx
0x18004d89f  call    ??$SafeRelease@VCFileStream@@@@YAXPEAPEAVCFileStream@@@Z; SafeRelease<CFileStream>(CFileStream * *)
0x18004d8a4  mov     rcx, [rdi+1088h]
0x18004d8ab  lea     rdx, [rbp+hFile]
0x18004d8af  xor     eax, eax
0x18004d8b1  xorps   xmm0, xmm0
0x18004d8b4  mov     [rbp+var_10], rax
0x18004d8b8  xor     r12d, r12d
0x18004d8bb  movups  [rbp+FileInformation], xmm0
0x18004d8bf  mov     [rbp+hFile], r12
0x18004d8c3  movups  [rbp+var_20], xmm0
0x18004d8c7  mov     rax, [rcx]
0x18004d8ca  mov     rax, [rax+18h]
0x18004d8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8d3  mov     ebx, eax
0x18004d8d5  test    eax, eax
0x18004d8d7  js      loc_18004DA81
0x18004d8dd  mov     rbx, [rbp+hFile]
0x18004d8e1  lea     rax, [rbp+FileSystemFlags]
0x18004d8e5  mov     [rsp+80h+nFileSystemNameSize], r12d; nFileSystemNameSize
0x18004d8ea  mov     rcx, rbx; hFile
0x18004d8ed  mov     [rsp+80h+lpFileSystemNameBuffer], r12; lpFileSystemNameBuffer
0x18004d8f2  xor     r9d, r9d; lpVolumeSerialNumber
0x18004d8f5  mov     [rsp+80h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18004d8fa  xor     r8d, r8d; nVolumeNameSize
0x18004d8fd  xor     edx, edx; lpVolumeNameBuffer
0x18004d8ff  mov     [rsp+80h+lpMaximumComponentLength], r12; lpMaximumComponentLength
0x18004d904  mov     [rbp+FileSystemFlags], r12d
0x18004d908  call    cs:__imp_GetVolumeInformationByHandleW
0x18004d90e  test    eax, eax
0x18004d910  jz      short loc_18004D931
0x18004d912  test    byte ptr [rbp+FileSystemFlags], 8
0x18004d916  jnz     short loc_18004D931
0x18004d918  lea     r9d, [r12+28h]; dwBufferSize
0x18004d91d  xor     edx, edx; FileInformationClass
0x18004d91f  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18004d923  mov     rcx, rbx; hFile
0x18004d926  mov     r14b, 1
0x18004d929  call    cs:__imp_GetFileInformationByHandleEx
0x18004d92f  jmp     short loc_18004D934
0x18004d931  mov     r14b, r12b
0x18004d934  mov     rcx, [rdi+1088h]
0x18004d93b  mov     rax, [rcx]
0x18004d93e  mov     rax, [rax+20h]
0x18004d942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d947  mov     rcx, [rdi+1088h]
0x18004d94e  mov     [rdi+1088h], r12
0x18004d955  test    rcx, rcx
0x18004d958  jz      short loc_18004D966
0x18004d95a  mov     rax, [rcx]
0x18004d95d  mov     rax, [rax+10h]
0x18004d961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d966  mov     rax, [rdi+1058h]
0x18004d96d  lea     r15, SourceString
0x18004d974  test    rax, rax
0x18004d977  mov     [rsp+80h+lpFileSystemFlags], r12; lpReserved
0x18004d97c  mov     rcx, r15
0x18004d97f  mov     [rdi+10C0h], r12b
0x18004d986  cmovnz  rcx, rax; lpReplacedFileName
0x18004d98a  mov     [rsp+80h+lpMaximumComponentLength], r12; lpExclude
0x18004d98f  lea     rsi, [rdi+1098h]
0x18004d996  xor     r8d, r8d; lpBackupFileName
0x18004d999  mov     rdx, [rsi]; lpReplacementFileName
0x18004d99c  mov     r9d, 2; dwReplaceFlags
0x18004d9a2  call    cs:__imp_ReplaceFileW
0x18004d9a8  test    eax, eax
0x18004d9aa  jnz     short loc_18004D9DC
0x18004d9ac  call    ResultFromKnownLastError
0x18004d9b1  mov     ebx, eax
0x18004d9b3  test    eax, eax
0x18004d9b5  jns     short loc_18004D9DC
0x18004d9b7  lea     ecx, [rax+7FF8FB68h]
0x18004d9bd  cmp     ecx, 1
0x18004d9c0  jbe     loc_18004DA81
0x18004d9c6  mov     rcx, [rsi]; lpFileName
0x18004d9c9  call    cs:__imp_DeleteFileW
0x18004d9cf  mov     rcx, rsi
0x18004d9d2  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18004d9d7  jmp     loc_18004DA81
0x18004d9dc  test    r14b, r14b
0x18004d9df  jz      loc_18004DA68
0x18004d9e5  mov     rax, [rdi+1058h]
0x18004d9ec  mov     edx, 0C0000000h; dwDesiredAccess
0x18004d9f1  test    rax, rax
0x18004d9f4  mov     [rsp+80h+lpFileSystemNameBuffer], r12; hTemplateFile
0x18004d9f9  mov     dword ptr [rsp+80h+lpFileSystemFlags], r12d; dwFlagsAndAttributes
0x18004d9fe  cmovnz  r15, rax
0x18004da02  mov     dword ptr [rsp+80h+lpMaximumComponentLength], 3; dwCreationDisposition
0x18004da0a  xor     r9d, r9d; lpSecurityAttributes
0x18004da0d  mov     rcx, r15; lpFileName
0x18004da10  lea     r8d, [r9+7]; dwShareMode
0x18004da14  call    cs:__imp_CreateFileW
0x18004da1a  mov     rbx, rax
0x18004da1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004da21  jz      short loc_18004DA68
0x18004da23  lea     rcx, [rbp+hFile]; lpSystemTimeAsFileTime
0x18004da27  mov     [rbp+hFile], r12
0x18004da2b  call    cs:__imp_GetSystemTimeAsFileTime
0x18004da31  mov     r8d, dword ptr [rbp+hFile+4]
0x18004da35  mov     r9d, 28h ; '('; dwBufferSize
0x18004da3b  mov     edx, dword ptr [rbp+hFile]
0x18004da3e  mov     rcx, rbx; hFile
0x18004da41  shl     r8, 20h
0x18004da45  add     rdx, 1312D00h
0x18004da4c  add     r8, rdx
0x18004da4f  xor     edx, edx; FileInformationClass
0x18004da51  mov     qword ptr [rbp+var_20], r8
0x18004da55  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18004da59  call    cs:__imp_SetFileInformationByHandle
0x18004da5f  mov     rcx, rbx; hObject
0x18004da62  call    cs:__imp_CloseHandle
0x18004da68  mov     rcx, rsi
0x18004da6b  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18004da70  mov     rcx, rdi; this
0x18004da73  mov     [rdi+1090h], r12b
0x18004da7a  call    ?OpenFile@CFileStream@@QEAAJXZ; CFileStream::OpenFile(void)
0x18004da7f  mov     ebx, eax
0x18004da81  mov     eax, ebx
0x18004da83  mov     rcx, [rbp+var_8]
0x18004da87  xor     rcx, rsp; StackCookie
0x18004da8a  call    __security_check_cookie
0x18004da8f  lea     r11, [rsp+80h+var_s0]
0x18004da97  mov     rbx, [r11+38h]
0x18004da9b  mov     rsi, [r11+40h]
0x18004da9f  mov     rsp, r11
0x18004daa2  pop     r15
0x18004daa4  pop     r14
0x18004daa6  pop     r12
0x18004daa8  pop     rdi
0x18004daa9  pop     rbp
0x18004daaa  retn
```
