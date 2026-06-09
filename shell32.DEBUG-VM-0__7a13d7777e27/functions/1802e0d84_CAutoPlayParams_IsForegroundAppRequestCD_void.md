# CAutoPlayParams::_IsForegroundAppRequestCD(void)

- ea: `0x1802e0d84`
- end: `0x1802e0f4b`
- name: `?_IsForegroundAppRequestCD@CAutoPlayParams@@AEAAHXZ`
- size: `455`
- prototype: `__int64 __fastcall(CAutoPlayParams *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config`

## callers

- `0x1802dde5c`

## callees

- `0x180019c34`
- `0x18001bf10`
- `0x1800bfb48`
- `0x1800c0c44`
- `0x180233280`
- `0x1802e0d84`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e0f24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e0f24`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1802e0e9f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1802e0e9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e0f1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e0f1b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1802e0e70`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1802e0e70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802e0e39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802e0e39`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1802e0eb3`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1802e0eb3`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1802e0ef9`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1802e0ef9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802e0e52`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802e0e52`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1802e0ee2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1802e0ee2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802e0dde`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802e0dde`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802e0dcd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802e0e01`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802e0e2f`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802e0dcd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802e0e01`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802e0e2f`
- `Windows.Storage!PathIsEqualOrSubFolder` at `0x1802e0f10`
- `Windows.Storage!PathIsEqualOrSubFolder` at `0x1802e0f10`

## pseudocode

```c
__int64 __fastcall CAutoPlayParams::_IsForegroundAppRequestCD(LPCWSTR *this)
{
  unsigned int IsEqualOrSubFolder; // edi
  CDriveLetterCache *v3; // rbx
  int DriveNumberW; // eax
  struct CDriveLetterData *DriveLetterData; // r14
  WCHAR *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // esi
  int v12; // eax
  __int64 v13; // rax
  HANDLE v14; // rax
  void *v15; // rsi
  DWORD ExitCode[4]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR String1[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+240h] [rbp+140h] BYREF

  IsEqualOrSubFolder = 0;
  if ( (*(unsigned int (__fastcall **)(LPCWSTR))(*(_QWORD *)this[5] + 392LL))(this[5]) )
  {
    v3 = (CDriveLetterCache *)(Global_WindowsStorage_Untyped_MountPoint() + 264);
    DriveNumberW = PathGetDriveNumberW(this[3]);
    DriveLetterData = CDriveLetterCache::GetDriveLetterData(v3, DriveNumberW);
    if ( DriveLetterData )
    {
      v6 = 0;
      *(_QWORD *)ExitCode = 0;
      v7 = Global_WindowsStorage_Untyped_MountPoint();
      CCritSecDelayInitBase::Enter((PVOID)(v7 + 56));
      v10 = *((_QWORD *)DriveLetterData + 3);
      v11 = -2147467259;
      if ( v10 )
      {
        v12 = _AllocString<CTLocalAllocPolicy>(v9, v8, v10, ExitCode);
        v6 = *(WCHAR **)ExitCode;
        v11 = v12;
      }
      v13 = Global_WindowsStorage_Untyped_MountPoint();
      LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 56));
      if ( v11 >= 0 )
      {
        v14 = OpenProcess(0x400u, 0, *((_DWORD *)DriveLetterData + 5));
        v15 = v14;
        if ( v14 )
        {
          ExitCode[0] = 0;
          if ( GetExitCodeProcess(v14, ExitCode) && ExitCode[0] == 259 )
          {
            if ( !GetVolumePathNameW(v6, szVolumePathName, 0x104u)
              || PathCchAddBackslash(szVolumePathName, 0x104u) < 0
              || (int)StringCchCopyW(String1, 0x104u, this[5] + 26) < 0
              || lstrcmpiW(String1, szVolumePathName) )
            {
              if ( GetTempPathW(0x104u, String1) - 1 <= 0x102 )
                IsEqualOrSubFolder = PathIsEqualOrSubFolder(String1, v6);
            }
            else
            {
              IsEqualOrSubFolder = 1;
            }
          }
          CloseHandle(v15);
        }
        LocalFree(v6);
      }
    }
  }
  return IsEqualOrSubFolder;
}

```

## disassembly

```asm
0x1802e0d84  push    rbp
0x1802e0d86  push    rbx
0x1802e0d87  push    rsi
0x1802e0d88  push    rdi
0x1802e0d89  push    r14
0x1802e0d8b  push    r15
0x1802e0d8d  lea     rbp, [rsp-368h]
0x1802e0d95  sub     rsp, 468h
0x1802e0d9c  mov     rax, cs:__security_cookie
0x1802e0da3  xor     rax, rsp
0x1802e0da6  mov     [rbp+390h+var_40], rax
0x1802e0dad  mov     r15, rcx
0x1802e0db0  xor     edi, edi
0x1802e0db2  mov     rcx, [rcx+28h]
0x1802e0db6  mov     rax, [rcx]
0x1802e0db9  mov     rax, [rax+188h]
0x1802e0dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e0dc5  test    eax, eax
0x1802e0dc7  jz      loc_1802E0F2A
0x1802e0dcd  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1802e0dd3  mov     rcx, [r15+18h]; pszPath
0x1802e0dd7  lea     rbx, [rax+108h]
0x1802e0dde  call    cs:__imp_PathGetDriveNumberW
0x1802e0de4  mov     edx, eax; int
0x1802e0de6  mov     rcx, rbx; this
0x1802e0de9  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x1802e0dee  mov     r14, rax
0x1802e0df1  test    rax, rax
0x1802e0df4  jz      loc_1802E0F2A
0x1802e0dfa  xor     ebx, ebx
0x1802e0dfc  mov     qword ptr [rsp+490h+ExitCode], rbx
0x1802e0e01  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1802e0e07  lea     rcx, [rax+38h]; Parameter
0x1802e0e0b  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1802e0e10  mov     r8, [r14+18h]
0x1802e0e14  mov     esi, 80004005h
0x1802e0e19  test    r8, r8
0x1802e0e1c  jz      short loc_1802E0E2F
0x1802e0e1e  lea     r9, [rsp+490h+ExitCode]
0x1802e0e23  call    ??$_AllocString@VCTLocalAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTLocalAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1802e0e28  mov     rbx, qword ptr [rsp+490h+ExitCode]
0x1802e0e2d  mov     esi, eax
0x1802e0e2f  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1802e0e35  lea     rcx, [rax+38h]; lpCriticalSection
0x1802e0e39  call    cs:__imp_LeaveCriticalSection
0x1802e0e3f  test    esi, esi
0x1802e0e41  js      loc_1802E0F2A
0x1802e0e47  mov     r8d, [r14+14h]; dwProcessId
0x1802e0e4b  xor     edx, edx; bInheritHandle
0x1802e0e4d  mov     ecx, 400h; dwDesiredAccess
0x1802e0e52  call    cs:__imp_OpenProcess
0x1802e0e58  mov     rsi, rax
0x1802e0e5b  test    rax, rax
0x1802e0e5e  jz      loc_1802E0F21
0x1802e0e64  lea     rdx, [rsp+490h+ExitCode]; lpExitCode
0x1802e0e69  mov     [rsp+490h+ExitCode], edi
0x1802e0e6d  mov     rcx, rax; hProcess
0x1802e0e70  call    cs:__imp_GetExitCodeProcess
0x1802e0e76  test    eax, eax
0x1802e0e78  jz      loc_1802E0F18
0x1802e0e7e  cmp     [rsp+490h+ExitCode], 103h
0x1802e0e86  jnz     loc_1802E0F18
0x1802e0e8c  mov     r14d, 104h
0x1802e0e92  lea     rdx, [rbp+390h+szVolumePathName]; lpszVolumePathName
0x1802e0e99  mov     r8d, r14d; cchBufferLength
0x1802e0e9c  mov     rcx, rbx; lpszFileName
0x1802e0e9f  call    cs:__imp_GetVolumePathNameW
0x1802e0ea5  test    eax, eax
0x1802e0ea7  jz      short loc_1802E0EF1
0x1802e0ea9  mov     edx, r14d; cchPath
0x1802e0eac  lea     rcx, [rbp+390h+szVolumePathName]; pszPath
0x1802e0eb3  call    cs:__imp_PathCchAddBackslash
0x1802e0eb9  test    eax, eax
0x1802e0ebb  js      short loc_1802E0EF1
0x1802e0ebd  mov     r8, [r15+28h]
0x1802e0ec1  lea     rcx, [rsp+490h+String1]; unsigned __int16 *
0x1802e0ec6  add     r8, 34h ; '4'; unsigned __int16 *
0x1802e0eca  mov     edx, r14d; unsigned __int64
0x1802e0ecd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802e0ed2  test    eax, eax
0x1802e0ed4  js      short loc_1802E0EF1
0x1802e0ed6  lea     rdx, [rbp+390h+szVolumePathName]; lpString2
0x1802e0edd  lea     rcx, [rsp+490h+String1]; lpString1
0x1802e0ee2  call    cs:__imp_lstrcmpiW
0x1802e0ee8  test    eax, eax
0x1802e0eea  jnz     short loc_1802E0EF1
0x1802e0eec  lea     edi, [rax+1]
0x1802e0eef  jmp     short loc_1802E0F18
0x1802e0ef1  lea     rdx, [rsp+490h+String1]; lpBuffer
0x1802e0ef6  mov     ecx, r14d; nBufferLength
0x1802e0ef9  call    cs:__imp_GetTempPathW
0x1802e0eff  dec     eax
0x1802e0f01  cmp     eax, 102h
0x1802e0f06  ja      short loc_1802E0F18
0x1802e0f08  mov     rdx, rbx
0x1802e0f0b  lea     rcx, [rsp+490h+String1]
0x1802e0f10  call    cs:__imp_PathIsEqualOrSubFolder
0x1802e0f16  mov     edi, eax
0x1802e0f18  mov     rcx, rsi; hObject
0x1802e0f1b  call    cs:__imp_CloseHandle
0x1802e0f21  mov     rcx, rbx; hMem
0x1802e0f24  call    cs:__imp_LocalFree
0x1802e0f2a  mov     eax, edi
0x1802e0f2c  mov     rcx, [rbp+390h+var_40]
0x1802e0f33  xor     rcx, rsp; StackCookie
0x1802e0f36  call    __security_check_cookie
0x1802e0f3b  add     rsp, 468h
0x1802e0f42  pop     r15
0x1802e0f44  pop     r14
0x1802e0f46  pop     rdi
0x1802e0f47  pop     rsi
0x1802e0f48  pop     rbx
0x1802e0f49  pop     rbp
0x1802e0f4a  retn
```
