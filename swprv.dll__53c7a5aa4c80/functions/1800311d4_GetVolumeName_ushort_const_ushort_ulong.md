# GetVolumeName(ushort const *,ushort *,ulong)

- ea: `0x1800311d4`
- end: `0x18003127c`
- name: `?GetVolumeName@@YAJPEBGPEAGK@Z`
- size: `168`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeMountPoint, LPWSTR lpszVolumeName)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18002fed8`
- `0x180031034`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800311d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031244`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180031220`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003123a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180031220`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003123a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetVolumeName(LPCWSTR lpszVolumeMountPoint, LPWSTR lpszVolumeName)
{
  unsigned int v4; // ebx
  signed int LastError; // eax
  WCHAR szVolumeName; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v8[526]; // [rsp+22h] [rbp-226h] BYREF

  szVolumeName = 0;
  memset_0(v8, 0, 0x208u);
  if ( !GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, &szVolumeName, 0x105u)
    || (v4 = 0, !GetVolumeNameForVolumeMountPointW(&szVolumeName, lpszVolumeName, 0x105u)) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x1800311d4  mov     [rsp+arg_10], rbx
0x1800311d9  push    rdi
0x1800311da  sub     rsp, 240h
0x1800311e1  mov     rax, cs:__security_cookie
0x1800311e8  xor     rax, rsp
0x1800311eb  mov     [rsp+248h+var_18], rax
0x1800311f3  mov     rdi, rdx
0x1800311f6  mov     rbx, rcx
0x1800311f9  xor     eax, eax
0x1800311fb  lea     rcx, [rsp+248h+var_226]; void *
0x180031200  xor     edx, edx; Val
0x180031202  mov     [rsp+248h+szVolumeName], ax
0x180031207  mov     r8d, 208h; Size
0x18003120d  call    memset_0
0x180031212  mov     r8d, 105h; cchBufferLength
0x180031218  lea     rdx, [rsp+248h+szVolumeName]; lpszVolumeName
0x18003121d  mov     rcx, rbx; lpszVolumeMountPoint
0x180031220  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180031226  test    eax, eax
0x180031228  jz      short loc_180031244
0x18003122a  mov     r8d, 105h; cchBufferLength
0x180031230  lea     rcx, [rsp+248h+szVolumeName]; lpszVolumeMountPoint
0x180031235  mov     rdx, rdi; lpszVolumeName
0x180031238  xor     ebx, ebx
0x18003123a  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180031240  test    eax, eax
0x180031242  jnz     short loc_180031259
0x180031244  call    cs:__imp_GetLastError
0x18003124a  mov     ebx, eax
0x18003124c  test    eax, eax
0x18003124e  jle     short loc_180031259
0x180031250  movzx   ebx, ax
0x180031253  or      ebx, 80070000h
0x180031259  mov     eax, ebx
0x18003125b  mov     rcx, [rsp+248h+var_18]
0x180031263  xor     rcx, rsp; StackCookie
0x180031266  call    __security_check_cookie
0x18003126b  mov     rbx, [rsp+248h+arg_10]
0x180031273  add     rsp, 240h
0x18003127a  pop     rdi
0x18003127b  retn
```
