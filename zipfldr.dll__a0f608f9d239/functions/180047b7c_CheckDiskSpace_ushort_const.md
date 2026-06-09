# CheckDiskSpace(ushort const *)

- ea: `0x180047b7c`
- end: `0x180047c40`
- name: `?CheckDiskSpace@@YAHPEBG@Z`
- size: `196`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002cc30`
- `0x18003fde0`

## callees

- `0x180036f50`
- `0x180047b7c`

## import_xrefs

- `SHLWAPI!PathGetDriveNumberW` at `0x180047bed`
- `SHLWAPI!PathGetDriveNumberW` at `0x180047bed`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180047c0b`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180047c0b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180047bb5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180047bb5`

## pseudocode

```c
BOOL __fastcall CheckDiskSpace(LPCWSTR pszPath)
{
  BOOL result; // eax
  int v3; // ebx
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+20h] [rbp-50h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+28h] [rbp-48h] BYREF
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+30h] [rbp-40h] BYREF
  _OWORD FileInformation[2]; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v8; // [rsp+58h] [rbp-18h]
  WCHAR DirectoryName[4]; // [rsp+60h] [rbp-10h] BYREF

  memset(FileInformation, 0, sizeof(FileInformation));
  v8 = 0;
  result = GetFileAttributesExW(pszPath, GetFileExInfoStandard, FileInformation);
  if ( result )
  {
    v3 = 1;
    FreeBytesAvailableToCaller.QuadPart = 0;
    TotalNumberOfBytes.QuadPart = 0;
    TotalNumberOfFreeBytes.QuadPart = 0;
    wcscpy(DirectoryName, L"_:");
    DirectoryName[0] = PathGetDriveNumberW(pszPath) + 97;
    if ( GetDiskFreeSpaceExW(DirectoryName, &FreeBytesAvailableToCaller, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
      return v8 < TotalNumberOfFreeBytes.QuadPart;
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180047b7c  mov     [rsp-8+arg_8], rbx
0x180047b81  mov     [rsp-8+arg_10], rdi
0x180047b86  push    rbp
0x180047b87  mov     rbp, rsp
0x180047b8a  sub     rsp, 70h
0x180047b8e  mov     rax, cs:__security_cookie
0x180047b95  xor     rax, rsp
0x180047b98  mov     [rbp+var_8], rax
0x180047b9c  xorps   xmm0, xmm0
0x180047b9f  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180047ba3  xor     eax, eax
0x180047ba5  xor     edx, edx; fInfoLevelId
0x180047ba7  movups  [rbp+FileInformation], xmm0
0x180047bab  mov     [rbp+var_18], eax
0x180047bae  mov     rdi, rcx
0x180047bb1  movups  [rbp+var_28], xmm0
0x180047bb5  call    cs:__imp_GetFileAttributesExW
0x180047bbb  test    eax, eax
0x180047bbd  jz      short loc_180047C22
0x180047bbf  mov     ebx, 1
0x180047bc4  mov     qword ptr [rbp+FreeBytesAvailableToCaller], 0
0x180047bcc  mov     rcx, rdi; pszPath
0x180047bcf  mov     qword ptr [rbp+TotalNumberOfBytes], 0
0x180047bd7  mov     qword ptr [rbp+TotalNumberOfFreeBytes], 0
0x180047bdf  mov     [rbp+var_E], 3Ah ; ':'
0x180047be6  lea     eax, [rbx+5Eh]
0x180047be9  mov     [rbp+DirectoryName], ax
0x180047bed  call    cs:__imp_PathGetDriveNumberW
0x180047bf3  add     ax, 61h ; 'a'
0x180047bf7  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180047bfb  lea     r8, [rbp+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x180047bff  mov     [rbp+DirectoryName], ax
0x180047c03  lea     rdx, [rbp+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x180047c07  lea     rcx, [rbp+DirectoryName]; lpDirectoryName
0x180047c0b  call    cs:__imp_GetDiskFreeSpaceExW
0x180047c11  test    eax, eax
0x180047c13  jz      short loc_180047C20
0x180047c15  mov     eax, [rbp+var_18]
0x180047c18  cmp     rax, qword ptr [rbp+TotalNumberOfFreeBytes]
0x180047c1c  sbb     eax, eax
0x180047c1e  and     ebx, eax
0x180047c20  mov     eax, ebx
0x180047c22  mov     rcx, [rbp+var_8]
0x180047c26  xor     rcx, rsp; StackCookie
0x180047c29  call    __security_check_cookie
0x180047c2e  lea     r11, [rsp+70h+var_s0]
0x180047c33  mov     rbx, [r11+18h]
0x180047c37  mov     rdi, [r11+20h]
0x180047c3b  mov     rsp, r11
0x180047c3e  pop     rbp
0x180047c3f  retn
```
