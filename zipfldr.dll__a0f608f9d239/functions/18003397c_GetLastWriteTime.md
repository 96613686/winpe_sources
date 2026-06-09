# GetLastWriteTime

- ea: `0x18003397c`
- end: `0x180033a9f`
- name: `GetLastWriteTime`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180030350`

## callees

- `0x18003397c`
- `0x180033aa8`
- `0x18003534c`
- `0x180036f50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800339fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800339fe`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180033a2a`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180033a2a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800339c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800339c0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180033a58`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180033a58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetLastWriteTime(LPCWSTR *a1, struct _FILETIME *a2)
{
  char *FileW; // rbx
  const char *v4; // r9
  unsigned int v5; // edi
  const char *v7; // r9
  unsigned int LastError; // ebx
  struct _FILETIME v9; // rax
  char *v10; // [rsp+40h] [rbp-28h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+48h] [rbp-20h] BYREF
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  FileW = (char *)CreateFileW(*a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v10 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    CreationTime = 0;
    LastWriteTime = 0;
    if ( GetFileTime(FileW, &CreationTime, 0, &LastWriteTime) )
    {
      if ( CompareFileTime(&CreationTime, &LastWriteTime) <= 0 )
      {
        v9 = LastWriteTime;
      }
      else
      {
        v9 = CreationTime;
        LastWriteTime = CreationTime;
      }
      *a2 = v9;
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xC9,
                    (unsigned int)"shell\\ext\\zip\\archive\\archivestructure.cpp",
                    v7);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
    return LastError;
  }
  else
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0xC6,
           (unsigned int)"shell\\ext\\zip\\archive\\archivestructure.cpp",
           v4);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    return v5;
  }
}

```

## disassembly

```asm
0x18003397c  mov     [rsp+arg_10], rbx
0x180033981  push    rdi
0x180033982  sub     rsp, 60h
0x180033986  mov     rax, cs:__security_cookie
0x18003398d  xor     rax, rsp
0x180033990  mov     [rsp+68h+var_10], rax
0x180033995  mov     rdi, rdx
0x180033998  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800339a1  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800339a9  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800339b1  xor     r9d, r9d; lpSecurityAttributes
0x1800339b4  mov     edx, 80000000h; dwDesiredAccess
0x1800339b9  lea     r8d, [r9+1]; dwShareMode
0x1800339bd  mov     rcx, [rcx]; lpFileName
0x1800339c0  call    cs:__imp_CreateFileW
0x1800339c6  mov     rbx, rax
0x1800339c9  mov     [rsp+68h+var_28], rax
0x1800339ce  inc     rax
0x1800339d1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800339d7  jnz     short loc_180033A08
0x1800339d9  mov     rcx, [rsp+68h]; this
0x1800339de  lea     r8, aShellExtZipArc_6; "shell\\ext\\zip\\archive\\archivestruct"...
0x1800339e5  mov     edx, 0C6h; void *
0x1800339ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800339ef  mov     edi, eax
0x1800339f1  lea     rcx, [rbx-1]
0x1800339f5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800339f9  ja      short loc_180033A04
0x1800339fb  mov     rcx, rbx; hObject
0x1800339fe  call    cs:__imp_CloseHandle
0x180033a04  mov     eax, edi
0x180033a06  jmp     short loc_180033A84
0x180033a08  mov     qword ptr [rsp+68h+CreationTime.dwLowDateTime], 0
0x180033a11  mov     qword ptr [rsp+68h+LastWriteTime.dwLowDateTime], 0
0x180033a1a  lea     r9, [rsp+68h+LastWriteTime]; lpLastWriteTime
0x180033a1f  xor     r8d, r8d; lpLastAccessTime
0x180033a22  lea     rdx, [rsp+68h+CreationTime]; lpCreationTime
0x180033a27  mov     rcx, rbx; hFile
0x180033a2a  call    cs:__imp_GetFileTime
0x180033a30  test    eax, eax
0x180033a32  jnz     short loc_180033A4E
0x180033a34  mov     rcx, [rsp+68h]; this
0x180033a39  lea     r8, aShellExtZipArc_6; "shell\\ext\\zip\\archive\\archivestruct"...
0x180033a40  mov     edx, 0C9h; void *
0x180033a45  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033a4a  mov     ebx, eax
0x180033a4c  jmp     short loc_180033A78
0x180033a4e  lea     rdx, [rsp+68h+LastWriteTime]; lpFileTime2
0x180033a53  lea     rcx, [rsp+68h+CreationTime]; lpFileTime1
0x180033a58  call    cs:__imp_CompareFileTime
0x180033a5e  test    eax, eax
0x180033a60  jle     short loc_180033A6E
0x180033a62  mov     rax, qword ptr [rsp+68h+CreationTime.dwLowDateTime]
0x180033a67  mov     qword ptr [rsp+68h+LastWriteTime.dwLowDateTime], rax
0x180033a6c  jmp     short loc_180033A73
0x180033a6e  mov     rax, qword ptr [rsp+68h+LastWriteTime.dwLowDateTime]
0x180033a73  mov     [rdi], rax
0x180033a76  xor     ebx, ebx
0x180033a78  lea     rcx, [rsp+68h+var_28]
0x180033a7d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180033a82  mov     eax, ebx
0x180033a84  mov     rcx, [rsp+68h+var_10]
0x180033a89  xor     rcx, rsp; StackCookie
0x180033a8c  call    __security_check_cookie
0x180033a91  mov     rbx, [rsp+68h+arg_10]
0x180033a99  add     rsp, 60h
0x180033a9d  pop     rdi
0x180033a9e  retn
```
