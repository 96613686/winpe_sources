# SyncFileTime(ushort const *,ushort const *,ulong)

- ea: `0x180068f98`
- end: `0x18006906e`
- name: `?SyncFileTime@@YAJPEBG0K@Z`
- size: `214`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180062f3c`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x180068f98`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006904b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006904b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006900b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006900b`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180069033`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180069033`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180068fce`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180068fce`

## pseudocode

```c
__int64 __fastcall SyncFileTime(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int Error; // ebx
  HANDLE FileW; // rdi
  _OWORD FileInformation[2]; // [rsp+40h] [rbp-38h] BYREF
  int v7; // [rsp+60h] [rbp-18h]

  v7 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( GetFileAttributesExW(a1, GetFileExInfoStandard, FileInformation)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( SetFileTime(FileW, (const FILETIME *)((char *)FileInformation + 4), 0, 0) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      CloseHandle(FileW);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180068f98  mov     [rsp+arg_10], rbx
0x180068f9d  push    rdi
0x180068f9e  sub     rsp, 70h
0x180068fa2  mov     rax, cs:__security_cookie
0x180068fa9  xor     rax, rsp
0x180068fac  mov     [rsp+78h+var_10], rax
0x180068fb1  xorps   xmm0, xmm0
0x180068fb4  lea     r8, [rsp+78h+FileInformation]; lpFileInformation
0x180068fb9  mov     rdi, rdx
0x180068fbc  xor     eax, eax
0x180068fbe  xor     edx, edx; fInfoLevelId
0x180068fc0  mov     [rsp+78h+var_18], eax
0x180068fc4  movups  [rsp+78h+FileInformation], xmm0
0x180068fc9  movups  [rsp+78h+var_28], xmm0
0x180068fce  call    cs:__imp_GetFileAttributesExW
0x180068fd4  test    eax, eax
0x180068fd6  jnz     short loc_180068FE3
0x180068fd8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180068fdd  mov     ebx, eax
0x180068fdf  test    eax, eax
0x180068fe1  js      short loc_180069051
0x180068fe3  xor     r9d, r9d; lpSecurityAttributes
0x180068fe6  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180068fef  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180068ff7  mov     edx, 0C0000000h; dwDesiredAccess
0x180068ffc  mov     rcx, rdi; lpFileName
0x180068fff  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180069007  lea     r8d, [r9+1]; dwShareMode
0x18006900b  call    cs:__imp_CreateFileW
0x180069011  mov     rdi, rax
0x180069014  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180069018  jnz     short loc_180069025
0x18006901a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006901f  mov     ebx, eax
0x180069021  test    eax, eax
0x180069023  js      short loc_180069051
0x180069025  xor     r9d, r9d; lpLastWriteTime
0x180069028  lea     rdx, [rsp+78h+FileInformation+4]; lpCreationTime
0x18006902d  xor     r8d, r8d; lpLastAccessTime
0x180069030  mov     rcx, rdi; hFile
0x180069033  call    cs:__imp_SetFileTime
0x180069039  test    eax, eax
0x18006903b  jz      short loc_180069041
0x18006903d  xor     ebx, ebx
0x18006903f  jmp     short loc_180069048
0x180069041  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180069046  mov     ebx, eax
0x180069048  mov     rcx, rdi; hObject
0x18006904b  call    cs:__imp_CloseHandle
0x180069051  mov     eax, ebx
0x180069053  mov     rcx, [rsp+78h+var_10]
0x180069058  xor     rcx, rsp; StackCookie
0x18006905b  call    __security_check_cookie
0x180069060  mov     rbx, [rsp+78h+arg_10]
0x180069068  add     rsp, 70h
0x18006906c  pop     rdi
0x18006906d  retn
```
