# WwanUtilities::DeleteFileOlderThanDays(ushort *,uint)

- ea: `0x180085770`
- end: `0x1800858fc`
- name: `?DeleteFileOlderThanDays@WwanUtilities@@CAKPEAGI@Z`
- size: `396`
- prototype: `unsigned int __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180085904`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180014f1c`
- `0x180085770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800857bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800858b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800857bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800858b7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800858ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800858ad`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800857b3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800857b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800857ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800857ee`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800857fe`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800857fe`

## string_xrefs

- `0x1800857cd`: `WwanUtilities::DeleteFileOlderThanDays`
- `0x18008586b`: `WwanUtilities::DeleteFileOlderThanDays`
- `0x1800858c9`: `WwanUtilities::DeleteFileOlderThanDays`
- `0x180085876`: `File named: %ls is %lld days old; it will be deleted if older than %u days`
- `0x1800858c0`: `Failed to delete file named: %ls`

## pseudocode

```c
__int64 __fastcall WwanUtilities::DeleteFileOlderThanDays(LPCWSTR lpFileName)
{
  DWORD LastError; // eax
  const unsigned __int16 *v3; // r8
  DWORD v4; // ebx
  __int64 v6; // rbx
  unsigned __int64 v7; // rbx
  int v8; // [rsp+28h] [rbp-60h]
  struct _FILETIME FileTime; // [rsp+30h] [rbp-58h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-40h] BYREF
  __int128 v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+68h] [rbp-20h]

  FileInformation = 0;
  v13 = 0;
  v12 = 0;
  FileTime = 0;
  SystemTime = 0;
  if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
  {
    LastError = GetLastError();
    v3 = L"GetFileAttributesEx failed: 0x%x";
LABEL_3:
    v4 = LastError;
    WwanLog::Error("WwanUtilities::DeleteFileOlderThanDays", 0, v3, LastError);
    return v4;
  }
  v6 = *(_QWORD *)((char *)&v12 + 4);
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = GetLastError();
    v3 = L"SystemTimeToFileTime failed: 0x%x";
    goto LABEL_3;
  }
  v8 = 30;
  v7 = (*(_QWORD *)&FileTime - v6) / 0x2710uLL / 0x3E8 / 0x3C / 0x3C / 0x18;
  WwanLog::Info(
    "WwanUtilities::DeleteFileOlderThanDays",
    0,
    L"File named: %ls is %lld days old; it will be deleted if older than %u days",
    lpFileName,
    v7,
    v8);
  if ( v7 >= 0x1E && !DeleteFileW(lpFileName) )
  {
    v4 = GetLastError();
    WwanLog::Error("WwanUtilities::DeleteFileOlderThanDays", 0, L"Failed to delete file named: %ls", lpFileName);
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180085770  mov     [rsp+arg_8], rbx
0x180085775  push    rdi
0x180085776  sub     rsp, 80h
0x18008577d  mov     rax, cs:__security_cookie
0x180085784  xor     rax, rsp
0x180085787  mov     [rsp+88h+var_18], rax
0x18008578c  xorps   xmm0, xmm0
0x18008578f  lea     r8, [rsp+88h+FileInformation]; lpFileInformation
0x180085794  xor     eax, eax
0x180085796  xor     edx, edx; fInfoLevelId
0x180085798  movups  [rsp+88h+FileInformation], xmm0
0x18008579d  mov     [rsp+88h+var_20], eax
0x1800857a1  mov     rdi, rcx
0x1800857a4  movups  [rsp+88h+var_30], xmm0
0x1800857a9  mov     qword ptr [rsp+88h+FileTime.dwLowDateTime], rax
0x1800857ae  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x1800857b3  call    cs:__imp_GetFileAttributesExW
0x1800857b9  test    eax, eax
0x1800857bb  jnz     short loc_1800857E4
0x1800857bd  call    cs:__imp_GetLastError
0x1800857c3  lea     r8, aGetfileattribu_1; "GetFileAttributesEx failed: 0x%x"
0x1800857ca  mov     r9d, eax
0x1800857cd  lea     rcx, aWwanutilitiesD; "WwanUtilities::DeleteFileOlderThanDays"
0x1800857d4  xor     edx, edx; struct _GUID *
0x1800857d6  mov     ebx, eax
0x1800857d8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800857dd  mov     eax, ebx
0x1800857df  jmp     loc_1800858DE
0x1800857e4  mov     rbx, qword ptr [rsp+88h+var_30+4]
0x1800857e9  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x1800857ee  call    cs:__imp_GetSystemTime
0x1800857f4  lea     rdx, [rsp+88h+FileTime]; lpFileTime
0x1800857f9  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x1800857fe  call    cs:__imp_SystemTimeToFileTime
0x180085804  test    eax, eax
0x180085806  jnz     short loc_180085817
0x180085808  call    cs:__imp_GetLastError
0x18008580e  lea     r8, aSystemtimetofi; "SystemTimeToFileTime failed: 0x%x"
0x180085815  jmp     short loc_1800857CA
0x180085817  mov     rcx, qword ptr [rsp+88h+FileTime.dwLowDateTime]
0x18008581c  mov     r8, 8888888888888889h
0x180085826  sub     rcx, rbx
0x180085829  mov     [rsp+88h+var_60], 1Eh
0x180085831  mov     rax, 346DC5D63886594Bh
0x18008583b  mov     r9, rdi
0x18008583e  mul     rcx
0x180085841  mov     rax, 624DD2F1A9FBE77h
0x18008584b  mov     rcx, rdx
0x18008584e  shr     rcx, 0Bh
0x180085852  mul     rcx
0x180085855  mov     rax, r8
0x180085858  sub     rcx, rdx
0x18008585b  shr     rcx, 1
0x18008585e  add     rcx, rdx
0x180085861  shr     rcx, 9
0x180085865  mul     rcx
0x180085868  mov     rax, r8
0x18008586b  lea     rcx, aWwanutilitiesD; "WwanUtilities::DeleteFileOlderThanDays"
0x180085872  shr     rdx, 5
0x180085876  lea     r8, aFileNamedLsIsL; "File named: %ls is %lld days old; it wi"...
0x18008587d  mul     rdx
0x180085880  mov     rax, 0AAAAAAAAAAAAAAABh
0x18008588a  shr     rdx, 5
0x18008588e  mul     rdx
0x180085891  mov     rbx, rdx
0x180085894  xor     edx, edx; struct _GUID *
0x180085896  shr     rbx, 4
0x18008589a  mov     [rsp+88h+var_68], rbx
0x18008589f  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800858a4  cmp     rbx, 1Eh
0x1800858a8  jb      short loc_1800858DC
0x1800858aa  mov     rcx, rdi; lpFileName
0x1800858ad  call    cs:__imp_DeleteFileW
0x1800858b3  test    eax, eax
0x1800858b5  jnz     short loc_1800858DC
0x1800858b7  call    cs:__imp_GetLastError
0x1800858bd  mov     r9, rdi
0x1800858c0  lea     r8, aFailedToDelete_3; "Failed to delete file named: %ls"
0x1800858c7  xor     edx, edx; struct _GUID *
0x1800858c9  lea     rcx, aWwanutilitiesD; "WwanUtilities::DeleteFileOlderThanDays"
0x1800858d0  mov     ebx, eax
0x1800858d2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800858d7  jmp     loc_1800857DD
0x1800858dc  xor     eax, eax
0x1800858de  mov     rcx, [rsp+88h+var_18]
0x1800858e3  xor     rcx, rsp; StackCookie
0x1800858e6  call    __security_check_cookie
0x1800858eb  mov     rbx, [rsp+88h+arg_8]
0x1800858f3  add     rsp, 80h
0x1800858fa  pop     rdi
0x1800858fb  retn
```
