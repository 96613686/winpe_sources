# PathResolveReparsePoints(ushort const *,ushort *,unsigned __int64)

- ea: `0x1805adf14`
- end: `0x1805ae1d4`
- name: `?PathResolveReparsePoints@@YAJPEBGPEAG_K@Z`
- size: `704`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x1802f9bf8`

## callees

- `0x18004e06c`
- `0x18012ced0`
- `0x180133f50`
- `0x18015c5a0`
- `0x1803b1f60`
- `0x1805adf14`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ae199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ae199`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCW` at `0x1805ae0de`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCW` at `0x1805ae0de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ae18a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ae18a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1805ae163`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1805ae163`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1805ae143`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1805ae143`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1805adf6a`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1805adf6a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805adfe5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805adfe5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1805ae0f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1805ae0f7`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1805adf8d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1805adf8d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ae06a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ae06a`

## pseudocode

```c
__int64 __fastcall PathResolveReparsePoints(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HRESULT Error; // ebx
  void *v5; // rcx
  HANDLE FileW; // r12
  WCHAR *v7; // rdi
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rax
  const unsigned __int16 *v10; // r14
  const unsigned __int16 *v11; // r15
  HRESULT v12; // eax
  LPVOID lpOutBuffer; // [rsp+40h] [rbp-4D8h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-4D0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+50h] [rbp-4C8h] BYREF
  WCHAR pszPath[264]; // [rsp+C0h] [rbp-458h] BYREF
  WCHAR pszMore[264]; // [rsp+2D0h] [rbp-248h] BYREF

  if ( (int)StringCchCopyW(pszPath, 0x104u, a1) < 0
    || PathCchAddBackslash(pszPath, 0x104u) < 0
    || !GetVolumeNameForVolumeMountPointW(pszPath, szVolumeName, 0x32u) )
  {
    FileW = CreateFileW(a1, 8u, 7u, 0, 3u, 0x2200000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        return (unsigned int)Error;
    }
    lpOutBuffer = 0;
    Error = CTLocalAllocPolicy::Alloc(v5, 0x40u, 0x4000u, &lpOutBuffer);
    if ( Error < 0 )
    {
LABEL_27:
      CloseHandle(FileW);
      return (unsigned int)Error;
    }
    v7 = (WCHAR *)lpOutBuffer;
    BytesReturned = 0;
    if ( !DeviceIoControl(FileW, 0x900A8u, 0, 0, lpOutBuffer, 0x4000u, &BytesReturned, 0) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_26;
    }
    if ( *(_DWORD *)v7 == -1610612733 )
    {
      v8 = v7[5] >> 1;
      v9 = ((unsigned __int64)v7[4] >> 1) + 8;
    }
    else
    {
      if ( *(_DWORD *)v7 != -1610612724 )
        goto LABEL_25;
      v8 = v7[7] >> 1;
      v9 = ((unsigned __int64)v7[6] >> 1) + 10;
    }
    v10 = &v7[v9];
    if ( v10 )
    {
      v11 = v10 + 4;
      if ( StrCmpNCW(&v7[v9], L"\\??\\", 4) )
        v11 = v10;
      if ( PathIsRelativeW(v11) )
      {
        Error = StringCchCopyNW(pszMore, 0x104u, v11, v8);
        if ( Error < 0 )
          goto LABEL_26;
        Error = StringCchCopyW(a2, 0x104u, a1);
        if ( Error < 0 )
          goto LABEL_26;
        Error = PathCchRemoveFileSpec(a2, 0x104u);
        if ( Error < 0 )
          goto LABEL_26;
        v12 = PathCchAppend(a2, 0x104u, pszMore);
      }
      else
      {
        v12 = StringCchCopyNW(a2, 0x104u, v11, v8);
      }
      Error = v12;
LABEL_26:
      LocalFree(v7);
      goto LABEL_27;
    }
LABEL_25:
    Error = -2147467259;
    goto LABEL_26;
  }
  Error = StringCchCopyW(a2, 0x104u, a1);
  if ( Error >= 0 )
    return 1;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1805adf14  mov     [rsp+arg_10], rbx
0x1805adf19  mov     [rsp+arg_18], rbp
0x1805adf1e  push    rsi
0x1805adf1f  push    rdi
0x1805adf20  push    r12
0x1805adf22  push    r14
0x1805adf24  push    r15
0x1805adf26  sub     rsp, 4F0h
0x1805adf2d  mov     rax, cs:__security_cookie
0x1805adf34  xor     rax, rsp
0x1805adf37  mov     [rsp+518h+var_38], rax
0x1805adf3f  mov     rsi, rdx
0x1805adf42  mov     rbp, rcx
0x1805adf45  mov     r8, rcx; unsigned __int16 *
0x1805adf48  mov     ebx, 104h
0x1805adf4d  mov     edx, ebx; unsigned __int64
0x1805adf4f  lea     rcx, [rsp+518h+pszPath]; unsigned __int16 *
0x1805adf57  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805adf5c  test    eax, eax
0x1805adf5e  js      short loc_1805ADFBE
0x1805adf60  mov     edx, ebx; cchPath
0x1805adf62  lea     rcx, [rsp+518h+pszPath]; pszPath
0x1805adf6a  call    cs:__imp_PathCchAddBackslash
0x1805adf71  nop     dword ptr [rax+rax+00h]
0x1805adf76  test    eax, eax
0x1805adf78  js      short loc_1805ADFBE
0x1805adf7a  mov     r8d, 32h ; '2'; cchBufferLength
0x1805adf80  lea     rdx, [rsp+518h+szVolumeName]; lpszVolumeName
0x1805adf85  lea     rcx, [rsp+518h+pszPath]; lpszVolumeMountPoint
0x1805adf8d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1805adf94  nop     dword ptr [rax+rax+00h]
0x1805adf99  test    eax, eax
0x1805adf9b  jz      short loc_1805ADFBE
0x1805adf9d  mov     r8, rbp; unsigned __int16 *
0x1805adfa0  mov     edx, ebx; unsigned __int64
0x1805adfa2  mov     rcx, rsi; unsigned __int16 *
0x1805adfa5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805adfaa  mov     ebx, eax
0x1805adfac  test    eax, eax
0x1805adfae  js      loc_1805AE1A5
0x1805adfb4  mov     ebx, 1
0x1805adfb9  jmp     loc_1805AE1A5
0x1805adfbe  xor     r9d, r9d; lpSecurityAttributes
0x1805adfc1  mov     [rsp+518h+hTemplateFile], 0; hTemplateFile
0x1805adfca  mov     [rsp+518h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1805adfd2  mov     rcx, rbp; lpFileName
0x1805adfd5  mov     [rsp+518h+dwCreationDisposition], 3; dwCreationDisposition
0x1805adfdd  lea     edx, [r9+8]; dwDesiredAccess
0x1805adfe1  lea     r8d, [r9+7]; dwShareMode
0x1805adfe5  call    cs:__imp_CreateFileW
0x1805adfec  nop     dword ptr [rax+rax+00h]
0x1805adff1  mov     r12, rax
0x1805adff4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805adff8  jnz     short loc_1805AE009
0x1805adffa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805adfff  mov     ebx, eax
0x1805ae001  test    eax, eax
0x1805ae003  js      loc_1805AE1A5
0x1805ae009  mov     edi, 4000h
0x1805ae00e  mov     [rsp+518h+lpOutBuffer], 0
0x1805ae017  mov     r8d, edi; unsigned __int64
0x1805ae01a  lea     r9, [rsp+518h+lpOutBuffer]; void **
0x1805ae01f  mov     edx, 40h ; '@'; unsigned int
0x1805ae024  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1805ae029  mov     ebx, eax
0x1805ae02b  test    eax, eax
0x1805ae02d  js      loc_1805AE196
0x1805ae033  mov     [rsp+518h+lpOverlapped], 0; lpOverlapped
0x1805ae03c  lea     rax, [rsp+518h+BytesReturned]
0x1805ae041  mov     [rsp+518h+hTemplateFile], rax; lpBytesReturned
0x1805ae046  xor     r9d, r9d; nInBufferSize
0x1805ae049  mov     [rsp+518h+dwFlagsAndAttributes], edi; nOutBufferSize
0x1805ae04d  xor     r8d, r8d; lpInBuffer
0x1805ae050  mov     rdi, [rsp+518h+lpOutBuffer]
0x1805ae055  mov     edx, 900A8h; dwIoControlCode
0x1805ae05a  mov     rcx, r12; hDevice
0x1805ae05d  mov     qword ptr [rsp+518h+dwCreationDisposition], rdi; lpOutBuffer
0x1805ae062  mov     [rsp+518h+BytesReturned], 0
0x1805ae06a  call    cs:__imp_DeviceIoControl
0x1805ae071  nop     dword ptr [rax+rax+00h]
0x1805ae076  test    eax, eax
0x1805ae078  jnz     short loc_1805AE089
0x1805ae07a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1805ae07f  mov     ebx, eax
0x1805ae081  test    eax, eax
0x1805ae083  js      loc_1805AE187
0x1805ae089  cmp     dword ptr [rdi], 0A0000003h
0x1805ae08f  jnz     short loc_1805AE0A4
0x1805ae091  movzx   ebx, word ptr [rdi+0Ah]
0x1805ae095  movzx   eax, word ptr [rdi+8]
0x1805ae099  shr     ebx, 1
0x1805ae09b  shr     rax, 1
0x1805ae09e  add     rax, 8
0x1805ae0a2  jmp     short loc_1805AE0C1
0x1805ae0a4  cmp     dword ptr [rdi], 0A000000Ch
0x1805ae0aa  jnz     loc_1805AE182
0x1805ae0b0  movzx   ebx, word ptr [rdi+0Eh]
0x1805ae0b4  movzx   eax, word ptr [rdi+0Ch]
0x1805ae0b8  shr     ebx, 1
0x1805ae0ba  shr     rax, 1
0x1805ae0bd  add     rax, 0Ah
0x1805ae0c1  lea     r14, [rdi+rax*2]
0x1805ae0c5  test    r14, r14
0x1805ae0c8  jz      loc_1805AE182
0x1805ae0ce  mov     r8d, 4; nChar
0x1805ae0d4  lea     rdx, asc_180718E28; "\\??\\"
0x1805ae0db  mov     rcx, r14; pszStr1
0x1805ae0de  call    cs:__imp_StrCmpNCW
0x1805ae0e5  nop     dword ptr [rax+rax+00h]
0x1805ae0ea  test    eax, eax
0x1805ae0ec  lea     r15, [r14+8]
0x1805ae0f0  cmovnz  r15, r14
0x1805ae0f4  mov     rcx, r15; pszPath
0x1805ae0f7  call    cs:__imp_PathIsRelativeW
0x1805ae0fe  nop     dword ptr [rax+rax+00h]
0x1805ae103  mov     r9, rbx; unsigned __int64
0x1805ae106  mov     r8, r15; unsigned __int16 *
0x1805ae109  test    eax, eax
0x1805ae10b  jz      short loc_1805AE171
0x1805ae10d  mov     r14d, 104h
0x1805ae113  lea     rcx, [rsp+518h+pszMore]; unsigned __int16 *
0x1805ae11b  mov     edx, r14d; unsigned __int64
0x1805ae11e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1805ae123  mov     ebx, eax
0x1805ae125  test    eax, eax
0x1805ae127  js      short loc_1805AE187
0x1805ae129  mov     r8, rbp; unsigned __int16 *
0x1805ae12c  mov     edx, r14d; unsigned __int64
0x1805ae12f  mov     rcx, rsi; unsigned __int16 *
0x1805ae132  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805ae137  mov     ebx, eax
0x1805ae139  test    eax, eax
0x1805ae13b  js      short loc_1805AE187
0x1805ae13d  mov     edx, r14d; cchPath
0x1805ae140  mov     rcx, rsi; pszPath
0x1805ae143  call    cs:__imp_PathCchRemoveFileSpec
0x1805ae14a  nop     dword ptr [rax+rax+00h]
0x1805ae14f  mov     ebx, eax
0x1805ae151  test    eax, eax
0x1805ae153  js      short loc_1805AE187
0x1805ae155  lea     r8, [rsp+518h+pszMore]; pszMore
0x1805ae15d  mov     edx, r14d; cchPath
0x1805ae160  mov     rcx, rsi; pszPath
0x1805ae163  call    cs:__imp_PathCchAppend
0x1805ae16a  nop     dword ptr [rax+rax+00h]
0x1805ae16f  jmp     short loc_1805AE17E
0x1805ae171  mov     edx, 104h; unsigned __int64
0x1805ae176  mov     rcx, rsi; unsigned __int16 *
0x1805ae179  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1805ae17e  mov     ebx, eax
0x1805ae180  jmp     short loc_1805AE187
0x1805ae182  mov     ebx, 80004005h
0x1805ae187  mov     rcx, rdi; hMem
0x1805ae18a  call    cs:__imp_LocalFree
0x1805ae191  nop     dword ptr [rax+rax+00h]
0x1805ae196  mov     rcx, r12; hObject
0x1805ae199  call    cs:__imp_CloseHandle
0x1805ae1a0  nop     dword ptr [rax+rax+00h]
0x1805ae1a5  mov     eax, ebx
0x1805ae1a7  mov     rcx, [rsp+518h+var_38]
0x1805ae1af  xor     rcx, rsp; StackCookie
0x1805ae1b2  call    __security_check_cookie
0x1805ae1b7  lea     r11, [rsp+518h+var_28]
0x1805ae1bf  mov     rbx, [r11+40h]
0x1805ae1c3  mov     rbp, [r11+48h]
0x1805ae1c7  mov     rsp, r11
0x1805ae1ca  pop     r15
0x1805ae1cc  pop     r14
0x1805ae1ce  pop     r12
0x1805ae1d0  pop     rdi
0x1805ae1d1  pop     rsi
0x1805ae1d2  retn
```
