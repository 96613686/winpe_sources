# CAutoPlayParams::_IsForegroundAppRequestCD(void)

- ea: `0x1802ff51c`
- end: `0x1802ff738`
- name: `?_IsForegroundAppRequestCD@CAutoPlayParams@@AEAAHXZ`
- size: `540`
- prototype: `__int64 __fastcall(CAutoPlayParams *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config`

## callers

- `0x1802fc464`

## callees

- `0x18001a2bc`
- `0x18001aae0`
- `0x18009a838`
- `0x1800b32d4`
- `0x180249490`
- `0x1802ff51c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802ff70a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802ff70a`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1802ff661`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1802ff661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ff6fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ff6fb`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1802ff62c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1802ff62c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802ff5e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802ff5e9`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1802ff67b`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1802ff67b`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1802ff6cd`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1802ff6cd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802ff608`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802ff608`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1802ff6b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1802ff6b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802ff57c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802ff57c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802ff565`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802ff5a5`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802ff5d9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802ff565`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802ff5a5`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1802ff5d9`
- `Windows.Storage!PathIsEqualOrSubFolder` at `0x1802ff6ea`
- `Windows.Storage!PathIsEqualOrSubFolder` at `0x1802ff6ea`

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
0x1802ff51c  push    rbp
0x1802ff51e  push    rbx
0x1802ff51f  push    rsi
0x1802ff520  push    rdi
0x1802ff521  push    r14
0x1802ff523  push    r15
0x1802ff525  lea     rbp, [rsp-368h]
0x1802ff52d  sub     rsp, 468h
0x1802ff534  mov     rax, cs:__security_cookie
0x1802ff53b  xor     rax, rsp
0x1802ff53e  mov     [rbp+390h+var_40], rax
0x1802ff545  mov     r15, rcx
0x1802ff548  xor     edi, edi
0x1802ff54a  mov     rcx, [rcx+28h]
0x1802ff54e  mov     rax, [rcx]
0x1802ff551  mov     rax, [rax+188h]
0x1802ff558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ff55d  test    eax, eax
0x1802ff55f  jz      loc_1802FF716
0x1802ff565  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1802ff56c  nop     dword ptr [rax+rax+00h]
0x1802ff571  mov     rcx, [r15+18h]; pszPath
0x1802ff575  lea     rbx, [rax+108h]
0x1802ff57c  call    cs:__imp_PathGetDriveNumberW
0x1802ff583  nop     dword ptr [rax+rax+00h]
0x1802ff588  mov     edx, eax; int
0x1802ff58a  mov     rcx, rbx; this
0x1802ff58d  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x1802ff592  mov     r14, rax
0x1802ff595  test    rax, rax
0x1802ff598  jz      loc_1802FF716
0x1802ff59e  xor     ebx, ebx
0x1802ff5a0  mov     qword ptr [rsp+490h+ExitCode], rbx
0x1802ff5a5  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1802ff5ac  nop     dword ptr [rax+rax+00h]
0x1802ff5b1  lea     rcx, [rax+38h]; Parameter
0x1802ff5b5  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1802ff5ba  mov     r8, [r14+18h]
0x1802ff5be  mov     esi, 80004005h
0x1802ff5c3  test    r8, r8
0x1802ff5c6  jz      short loc_1802FF5D9
0x1802ff5c8  lea     r9, [rsp+490h+ExitCode]
0x1802ff5cd  call    ??$_AllocString@VCTLocalAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTLocalAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1802ff5d2  mov     rbx, qword ptr [rsp+490h+ExitCode]
0x1802ff5d7  mov     esi, eax
0x1802ff5d9  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1802ff5e0  nop     dword ptr [rax+rax+00h]
0x1802ff5e5  lea     rcx, [rax+38h]; lpCriticalSection
0x1802ff5e9  call    cs:__imp_LeaveCriticalSection
0x1802ff5f0  nop     dword ptr [rax+rax+00h]
0x1802ff5f5  test    esi, esi
0x1802ff5f7  js      loc_1802FF716
0x1802ff5fd  mov     r8d, [r14+14h]; dwProcessId
0x1802ff601  xor     edx, edx; bInheritHandle
0x1802ff603  mov     ecx, 400h; dwDesiredAccess
0x1802ff608  call    cs:__imp_OpenProcess
0x1802ff60f  nop     dword ptr [rax+rax+00h]
0x1802ff614  mov     rsi, rax
0x1802ff617  test    rax, rax
0x1802ff61a  jz      loc_1802FF707
0x1802ff620  lea     rdx, [rsp+490h+ExitCode]; lpExitCode
0x1802ff625  mov     [rsp+490h+ExitCode], edi
0x1802ff629  mov     rcx, rax; hProcess
0x1802ff62c  call    cs:__imp_GetExitCodeProcess
0x1802ff633  nop     dword ptr [rax+rax+00h]
0x1802ff638  test    eax, eax
0x1802ff63a  jz      loc_1802FF6F8
0x1802ff640  cmp     [rsp+490h+ExitCode], 103h
0x1802ff648  jnz     loc_1802FF6F8
0x1802ff64e  mov     r14d, 104h
0x1802ff654  lea     rdx, [rbp+390h+szVolumePathName]; lpszVolumePathName
0x1802ff65b  mov     r8d, r14d; cchBufferLength
0x1802ff65e  mov     rcx, rbx; lpszFileName
0x1802ff661  call    cs:__imp_GetVolumePathNameW
0x1802ff668  nop     dword ptr [rax+rax+00h]
0x1802ff66d  test    eax, eax
0x1802ff66f  jz      short loc_1802FF6C5
0x1802ff671  mov     edx, r14d; cchPath
0x1802ff674  lea     rcx, [rbp+390h+szVolumePathName]; pszPath
0x1802ff67b  call    cs:__imp_PathCchAddBackslash
0x1802ff682  nop     dword ptr [rax+rax+00h]
0x1802ff687  test    eax, eax
0x1802ff689  js      short loc_1802FF6C5
0x1802ff68b  mov     r8, [r15+28h]
0x1802ff68f  lea     rcx, [rsp+490h+String1]; unsigned __int16 *
0x1802ff694  add     r8, 34h ; '4'; unsigned __int16 *
0x1802ff698  mov     edx, r14d; unsigned __int64
0x1802ff69b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802ff6a0  test    eax, eax
0x1802ff6a2  js      short loc_1802FF6C5
0x1802ff6a4  lea     rdx, [rbp+390h+szVolumePathName]; lpString2
0x1802ff6ab  lea     rcx, [rsp+490h+String1]; lpString1
0x1802ff6b0  call    cs:__imp_lstrcmpiW
0x1802ff6b7  nop     dword ptr [rax+rax+00h]
0x1802ff6bc  test    eax, eax
0x1802ff6be  jnz     short loc_1802FF6C5
0x1802ff6c0  lea     edi, [rax+1]
0x1802ff6c3  jmp     short loc_1802FF6F8
0x1802ff6c5  lea     rdx, [rsp+490h+String1]; lpBuffer
0x1802ff6ca  mov     ecx, r14d; nBufferLength
0x1802ff6cd  call    cs:__imp_GetTempPathW
0x1802ff6d4  nop     dword ptr [rax+rax+00h]
0x1802ff6d9  dec     eax
0x1802ff6db  cmp     eax, 102h
0x1802ff6e0  ja      short loc_1802FF6F8
0x1802ff6e2  mov     rdx, rbx
0x1802ff6e5  lea     rcx, [rsp+490h+String1]
0x1802ff6ea  call    cs:__imp_PathIsEqualOrSubFolder
0x1802ff6f1  nop     dword ptr [rax+rax+00h]
0x1802ff6f6  mov     edi, eax
0x1802ff6f8  mov     rcx, rsi; hObject
0x1802ff6fb  call    cs:__imp_CloseHandle
0x1802ff702  nop     dword ptr [rax+rax+00h]
0x1802ff707  mov     rcx, rbx; hMem
0x1802ff70a  call    cs:__imp_LocalFree
0x1802ff711  nop     dword ptr [rax+rax+00h]
0x1802ff716  mov     eax, edi
0x1802ff718  mov     rcx, [rbp+390h+var_40]
0x1802ff71f  xor     rcx, rsp; StackCookie
0x1802ff722  call    __security_check_cookie
0x1802ff727  add     rsp, 468h
0x1802ff72e  pop     r15
0x1802ff730  pop     r14
0x1802ff732  pop     rdi
0x1802ff733  pop     rsi
0x1802ff734  pop     rbx
0x1802ff735  pop     rbp
0x1802ff736  retn
```
