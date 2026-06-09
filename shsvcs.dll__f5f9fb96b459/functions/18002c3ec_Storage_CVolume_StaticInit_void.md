# Storage::CVolume::StaticInit(void)

- ea: `0x18002c3ec`
- end: `0x18002c49b`
- name: `?StaticInit@CVolume@Storage@@SAJXZ`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180027e60`

## callees

- `0x18002c3ec`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002c470`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002c470`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18002c440`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18002c440`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c423`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c423`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18002c454`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18002c454`

## pseudocode

```c
__int64 Storage::CVolume::StaticInit(void)
{
  WCHAR szVolumePathName[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR Dst[264]; // [rsp+230h] [rbp-228h] BYREF

  Storage::CVolume::_szSystemVolume = 0;
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%", Dst, 0x104u)
    && GetVolumePathNameW(Dst, szVolumePathName, 0x104u)
    && PathCchAddBackslash(szVolumePathName, 0x104u) >= 0
    && !GetVolumeNameForVolumeMountPointW(szVolumePathName, &Storage::CVolume::_szSystemVolume, 0x32u) )
  {
    Storage::CVolume::_szSystemVolume = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c3ec  sub     rsp, 458h
0x18002c3f3  mov     rax, cs:__security_cookie
0x18002c3fa  xor     rax, rsp
0x18002c3fd  mov     [rsp+458h+var_18], rax
0x18002c405  xor     eax, eax
0x18002c407  lea     rdx, [rsp+458h+Dst]; lpDst
0x18002c40f  mov     r8d, 104h; nSize
0x18002c415  mov     cs:?_szSystemVolume@CVolume@Storage@@0PAGA, ax; ushort near * Storage::CVolume::_szSystemVolume
0x18002c41c  lea     rcx, aSystemroot; "%SystemRoot%"
0x18002c423  call    cs:__imp_ExpandEnvironmentStringsW
0x18002c429  test    eax, eax
0x18002c42b  jz      short loc_18002C481
0x18002c42d  mov     r8d, 104h; cchBufferLength
0x18002c433  lea     rdx, [rsp+458h+szVolumePathName]; lpszVolumePathName
0x18002c438  lea     rcx, [rsp+458h+Dst]; lpszFileName
0x18002c440  call    cs:__imp_GetVolumePathNameW
0x18002c446  test    eax, eax
0x18002c448  jz      short loc_18002C481
0x18002c44a  mov     edx, 104h; cchPath
0x18002c44f  lea     rcx, [rsp+458h+szVolumePathName]; pszPath
0x18002c454  call    cs:__imp_PathCchAddBackslash
0x18002c45a  test    eax, eax
0x18002c45c  js      short loc_18002C481
0x18002c45e  mov     r8d, 32h ; '2'; cchBufferLength
0x18002c464  lea     rdx, ?_szSystemVolume@CVolume@Storage@@0PAGA; lpszVolumeName
0x18002c46b  lea     rcx, [rsp+458h+szVolumePathName]; lpszVolumeMountPoint
0x18002c470  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002c476  test    eax, eax
0x18002c478  jnz     short loc_18002C481
0x18002c47a  mov     cs:?_szSystemVolume@CVolume@Storage@@0PAGA, ax; ushort near * Storage::CVolume::_szSystemVolume
0x18002c481  xor     eax, eax
0x18002c483  mov     rcx, [rsp+458h+var_18]
0x18002c48b  xor     rcx, rsp; StackCookie
0x18002c48e  call    __security_check_cookie
0x18002c493  add     rsp, 458h
0x18002c49a  retn
```
