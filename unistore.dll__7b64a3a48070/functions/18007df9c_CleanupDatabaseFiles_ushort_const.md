# CleanupDatabaseFiles(ushort const *)

- ea: `0x18007df9c`
- end: `0x18007e0f2`
- name: `?CleanupDatabaseFiles@@YAJPEBG@Z`
- size: `342`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180018644`

## callees

- `0x1800068f0`
- `0x1800175c0`
- `0x18006b3dc`
- `0x180073330`
- `0x18007dec0`
- `0x18007df9c`
- `0x18007f9a8`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007e00a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007e0a3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007e00a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007e0a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007dfd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007dfd1`

## string_xrefs

- `0x18007dff2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18007e02b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18007e06d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall CleanupDatabaseFiles(unsigned __int16 *a1)
{
  const unsigned __int16 *v2; // rdx
  HKEY v3; // rcx
  const unsigned __int16 *v4; // r8
  int v5; // ebp
  __int64 v6; // r9
  int v8; // eax
  int USDataFolderPath; // esi
  __int64 v10; // r8
  __int64 v11; // r9
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-228h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v5 = RegistrySetFileTime(v3, v2, v4, SystemTimeAsFileTime);
  if ( v5 < 0 )
  {
    v6 = 777;
LABEL_3:
    Log_UnistoreHREvent_0(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v6);
    return (unsigned int)v5;
  }
  if ( PathFileExistsW(a1) )
  {
    v8 = BackupVolumeData(a1);
    if ( v8 < 0 )
      Log_UnistoreHREvent_0(
        (unsigned int)v8,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        781);
    v5 = wil::RemoveDirectoryRecursiveNoThrow((wil *)a1, (const unsigned __int16 *)1, (void *)0xFFFFFFFFFFFFFFFFLL);
    if ( v5 < 0 )
    {
      v6 = 783;
      goto LABEL_3;
    }
  }
  USDataFolderPath = EnsureDirectory(a1);
  if ( USDataFolderPath < 0 )
  {
    v11 = 786;
LABEL_11:
    Log_UnistoreHREvent_0(
      (unsigned int)USDataFolderPath,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v11);
    return (unsigned int)USDataFolderPath;
  }
  USDataFolderPath = GetUSDataFolderPath(pszPath, 0x104u, v10);
  if ( USDataFolderPath < 0 )
  {
    v11 = 789;
    goto LABEL_11;
  }
  if ( PathFileExistsW(pszPath) )
  {
    USDataFolderPath = wil::RemoveDirectoryRecursiveNoThrow(
                         (wil *)pszPath,
                         (const unsigned __int16 *)1,
                         (void *)0xFFFFFFFFFFFFFFFFLL);
    if ( USDataFolderPath < 0 )
    {
      v11 = 793;
      goto LABEL_11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007df9c  mov     [rsp+arg_8], rbx
0x18007dfa1  mov     [rsp+arg_10], rbp
0x18007dfa6  push    rsi
0x18007dfa7  sub     rsp, 260h
0x18007dfae  mov     rax, cs:__security_cookie
0x18007dfb5  xor     rax, rsp
0x18007dfb8  mov     [rsp+268h+var_18], rax
0x18007dfc0  mov     rsi, rcx
0x18007dfc3  mov     qword ptr [rsp+268h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18007dfcc  lea     rcx, [rsp+268h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007dfd1  call    cs:__imp_GetSystemTimeAsFileTime
0x18007dfd7  mov     r9, qword ptr [rsp+268h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x18007dfdc  call    ?RegistrySetFileTime@@YAJPEAUHKEY__@@PEBG1U_FILETIME@@@Z; RegistrySetFileTime(HKEY__ *,ushort const *,ushort const *,_FILETIME)
0x18007dfe1  mov     ebp, eax
0x18007dfe3  test    eax, eax
0x18007dfe5  jns     short loc_18007E007
0x18007dfe7  mov     r9d, 309h
0x18007dfed  mov     edx, 1
0x18007dff2  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007dff9  mov     ecx, ebp
0x18007dffb  call    Log_UnistoreHREvent_0
0x18007e000  mov     eax, ebp
0x18007e002  jmp     loc_18007E0CD
0x18007e007  mov     rcx, rsi; pszPath
0x18007e00a  call    cs:__imp_PathFileExistsW
0x18007e010  mov     ebx, 1
0x18007e015  test    eax, eax
0x18007e017  jz      short loc_18007E059
0x18007e019  mov     rcx, rsi; unsigned __int16 *
0x18007e01c  call    ?BackupVolumeData@@YAJPEBG@Z; BackupVolumeData(ushort const *)
0x18007e021  test    eax, eax
0x18007e023  jns     short loc_18007E03B
0x18007e025  mov     r9d, 30Dh
0x18007e02b  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007e032  xor     edx, edx
0x18007e034  mov     ecx, eax
0x18007e036  call    Log_UnistoreHREvent_0
0x18007e03b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007e03f  mov     edx, ebx
0x18007e041  mov     rcx, rsi
0x18007e044  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18007e049  mov     ebp, eax
0x18007e04b  test    eax, eax
0x18007e04d  jns     short loc_18007E059
0x18007e04f  mov     r9d, 30Fh
0x18007e055  mov     edx, ebx
0x18007e057  jmp     short loc_18007DFF2
0x18007e059  mov     rcx, rsi; pszPath
0x18007e05c  call    ?EnsureDirectory@@YAJPEBG@Z; EnsureDirectory(ushort const *)
0x18007e061  mov     esi, eax
0x18007e063  test    eax, eax
0x18007e065  jns     short loc_18007E081
0x18007e067  mov     r9d, 312h
0x18007e06d  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007e074  mov     edx, ebx
0x18007e076  mov     ecx, esi
0x18007e078  call    Log_UnistoreHREvent_0
0x18007e07d  mov     eax, esi
0x18007e07f  jmp     short loc_18007E0CD
0x18007e081  mov     edx, 104h; unsigned __int64
0x18007e086  lea     rcx, [rsp+268h+pszPath]; unsigned __int16 *
0x18007e08b  call    ?GetUSDataFolderPath@@YAJPEAG_K@Z; GetUSDataFolderPath(ushort *,unsigned __int64)
0x18007e090  mov     esi, eax
0x18007e092  test    eax, eax
0x18007e094  jns     short loc_18007E09E
0x18007e096  mov     r9d, 315h
0x18007e09c  jmp     short loc_18007E06D
0x18007e09e  lea     rcx, [rsp+268h+pszPath]; pszPath
0x18007e0a3  call    cs:__imp_PathFileExistsW
0x18007e0a9  test    eax, eax
0x18007e0ab  jz      short loc_18007E0CB
0x18007e0ad  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007e0b1  lea     rcx, [rsp+268h+pszPath]
0x18007e0b6  mov     edx, ebx
0x18007e0b8  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18007e0bd  mov     esi, eax
0x18007e0bf  test    eax, eax
0x18007e0c1  jns     short loc_18007E0CB
0x18007e0c3  mov     r9d, 319h
0x18007e0c9  jmp     short loc_18007E06D
0x18007e0cb  xor     eax, eax
0x18007e0cd  mov     rcx, [rsp+268h+var_18]
0x18007e0d5  xor     rcx, rsp; StackCookie
0x18007e0d8  call    __security_check_cookie
0x18007e0dd  lea     r11, [rsp+268h+var_8]
0x18007e0e5  mov     rbx, [r11+18h]
0x18007e0e9  mov     rbp, [r11+20h]
0x18007e0ed  mov     rsp, r11
0x18007e0f0  pop     rsi
0x18007e0f1  retn
```
