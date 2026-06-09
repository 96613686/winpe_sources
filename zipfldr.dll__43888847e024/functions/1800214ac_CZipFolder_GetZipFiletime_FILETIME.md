# CZipFolder::GetZipFiletime(_FILETIME *)

- ea: `0x1800214ac`
- end: `0x180021590`
- name: `?GetZipFiletime@CZipFolder@@QEAAJPEAU_FILETIME@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(CZipFolder *__hidden this, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ed94`

## callees

- `0x1800214ac`
- `0x1800352a8`
- `0x180036f50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021556`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180021526`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180021526`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800214f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800214f1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002153a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002153a`

## pseudocode

```c
__int64 __fastcall CZipFolder::GetZipFiletime(const WCHAR *this, struct _FILETIME *a2)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  struct _FILETIME v5; // rax
  unsigned int Error; // ebx
  struct _FILETIME LastWriteTime; // [rsp+40h] [rbp-28h] BYREF
  struct _FILETIME CreationTime; // [rsp+48h] [rbp-20h] BYREF

  FileW = CreateFileW(this + 36, 0x80000000, 1u, 0, 3u, 0, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)-2147024891;
  }
  else
  {
    CreationTime = 0;
    LastWriteTime = 0;
    if ( GetFileTime(FileW, &CreationTime, 0, &LastWriteTime) )
    {
      if ( CompareFileTime(&CreationTime, &LastWriteTime) <= 0 )
      {
        v5 = LastWriteTime;
      }
      else
      {
        v5 = CreationTime;
        LastWriteTime = CreationTime;
      }
      *a2 = v5;
      Error = 0;
    }
    else
    {
      Error = ResultFromLastError();
    }
    CloseHandle(v4);
  }
  return Error;
}

```

## disassembly

```asm
0x1800214ac  mov     [rsp+arg_10], rbx
0x1800214b1  push    rdi
0x1800214b2  sub     rsp, 60h
0x1800214b6  mov     rax, cs:__security_cookie
0x1800214bd  xor     rax, rsp
0x1800214c0  mov     [rsp+68h+var_18], rax
0x1800214c5  xor     r9d, r9d; lpSecurityAttributes
0x1800214c8  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800214d1  mov     rbx, rdx
0x1800214d4  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800214dc  add     rcx, 48h ; 'H'; lpFileName
0x1800214e0  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800214e8  mov     edx, 80000000h; dwDesiredAccess
0x1800214ed  lea     r8d, [r9+1]; dwShareMode
0x1800214f1  call    cs:__imp_CreateFileW
0x1800214f7  mov     rdi, rax
0x1800214fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800214fe  jz      loc_180021589
0x180021504  lea     r9, [rsp+68h+LastWriteTime]; lpLastWriteTime
0x180021509  mov     qword ptr [rsp+68h+CreationTime.dwLowDateTime], 0
0x180021512  xor     r8d, r8d; lpLastAccessTime
0x180021515  mov     qword ptr [rsp+68h+LastWriteTime.dwLowDateTime], 0
0x18002151e  lea     rdx, [rsp+68h+CreationTime]; lpCreationTime
0x180021523  mov     rcx, rax; hFile
0x180021526  call    cs:__imp_GetFileTime
0x18002152c  test    eax, eax
0x18002152e  jz      short loc_180021580
0x180021530  lea     rdx, [rsp+68h+LastWriteTime]; lpFileTime2
0x180021535  lea     rcx, [rsp+68h+CreationTime]; lpFileTime1
0x18002153a  call    cs:__imp_CompareFileTime
0x180021540  test    eax, eax
0x180021542  jle     short loc_180021579
0x180021544  mov     rax, qword ptr [rsp+68h+CreationTime.dwLowDateTime]
0x180021549  mov     qword ptr [rsp+68h+LastWriteTime.dwLowDateTime], rax
0x18002154e  mov     [rbx], rax
0x180021551  xor     ebx, ebx
0x180021553  mov     rcx, rdi; hObject
0x180021556  call    cs:__imp_CloseHandle
0x18002155c  mov     eax, ebx
0x18002155e  mov     rcx, [rsp+68h+var_18]
0x180021563  xor     rcx, rsp; StackCookie
0x180021566  call    __security_check_cookie
0x18002156b  mov     rbx, [rsp+68h+arg_10]
0x180021573  add     rsp, 60h
0x180021577  pop     rdi
0x180021578  retn
0x180021579  mov     rax, qword ptr [rsp+68h+LastWriteTime.dwLowDateTime]
0x18002157e  jmp     short loc_18002154E
0x180021580  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180021585  mov     ebx, eax
0x180021587  jmp     short loc_180021553
0x180021589  mov     ebx, 80070005h
0x18002158e  jmp     short loc_18002155C
```
