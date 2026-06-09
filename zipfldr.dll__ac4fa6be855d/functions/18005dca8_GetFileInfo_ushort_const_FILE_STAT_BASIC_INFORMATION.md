# GetFileInfo(ushort const *,_FILE_STAT_BASIC_INFORMATION *)

- ea: `0x18005dca8`
- end: `0x18005de00`
- name: `?GetFileInfo@@YAJPEBGPEAU_FILE_STAT_BASIC_INFORMATION@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _FILE_STAT_BASIC_INFORMATION *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005bb2c`
- `0x18005bd48`
- `0x18005c004`

## callees

- `0x180033aa8`
- `0x18003534c`
- `0x180036f50`
- `0x18005dca8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005dd19`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005dd19`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18005dd52`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18005dd52`
- `api-ms-win-core-file-l2-1-4!GetFileInformationByName` at `0x18005dce0`
- `api-ms-win-core-file-l2-1-4!GetFileInformationByName` at `0x18005dce0`

## string_xrefs

- `0x18005dd61`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFileInfo(LPCWSTR lpFileName, struct _FILE_STAT_BASIC_INFORMATION *a2)
{
  HANDLE FileW; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  unsigned int LastError; // ebx
  HANDLE v9; // [rsp+40h] [rbp+7h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  if ( (unsigned int)GetFileInformationByName(lpFileName, 3, a2) )
    return 0;
  FileW = CreateFileW(lpFileName, 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  v9 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      *(_DWORD *)a2 = FileInformation.nFileIndexLow;
      *((_DWORD *)a2 + 1) = FileInformation.nFileIndexHigh;
      *((_QWORD *)a2 + 1) = FileInformation.ftCreationTime.dwLowDateTime
                          + ((unsigned __int64)FileInformation.ftCreationTime.dwHighDateTime << 32);
      *((_QWORD *)a2 + 2) = FileInformation.ftLastAccessTime.dwLowDateTime
                          + ((unsigned __int64)FileInformation.ftLastAccessTime.dwHighDateTime << 32);
      *((_QWORD *)a2 + 3) = FileInformation.ftLastWriteTime.dwLowDateTime
                          + ((unsigned __int64)FileInformation.ftLastWriteTime.dwHighDateTime << 32);
      *((_DWORD *)a2 + 12) = FileInformation.nFileSizeLow;
      *((_DWORD *)a2 + 13) = FileInformation.nFileSizeHigh;
      *((_DWORD *)a2 + 14) = FileInformation.dwFileAttributes;
      *((_DWORD *)a2 + 16) = FileInformation.nNumberOfLinks;
      *((_QWORD *)a2 + 10) = FileInformation.dwVolumeSerialNumber;
      LastError = 0;
      goto LABEL_9;
    }
    v7 = 1147;
  }
  else
  {
    v7 = 1144;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v7,
                (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
                v6);
LABEL_9:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  return LastError;
}

```

## disassembly

```asm
0x18005dca8  mov     [rsp-8+arg_10], rbx
0x18005dcad  mov     [rsp-8+arg_18], rdi
0x18005dcb2  push    rbp
0x18005dcb3  lea     rbp, [rsp-57h]
0x18005dcb8  sub     rsp, 90h
0x18005dcbf  mov     rax, cs:__security_cookie
0x18005dcc6  xor     rax, rsp
0x18005dcc9  mov     [rbp+57h+var_10], rax
0x18005dccd  mov     rbx, rdx
0x18005dcd0  mov     rdi, rcx
0x18005dcd3  mov     r9d, 68h ; 'h'
0x18005dcd9  mov     r8, rdx
0x18005dcdc  lea     edx, [r9-65h]
0x18005dce0  call    cs:__imp_GetFileInformationByName
0x18005dce6  test    eax, eax
0x18005dce8  jz      short loc_18005DCF1
0x18005dcea  xor     eax, eax
0x18005dcec  jmp     loc_18005DDDF
0x18005dcf1  mov     [rsp+90h+hTemplateFile], 0; hTemplateFile
0x18005dcfa  mov     [rsp+90h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18005dd02  mov     [rsp+90h+dwCreationDisposition], 3; dwCreationDisposition
0x18005dd0a  xor     r9d, r9d; lpSecurityAttributes
0x18005dd0d  mov     edx, 80h; dwDesiredAccess
0x18005dd12  lea     r8d, [r9+7]; dwShareMode
0x18005dd16  mov     rcx, rdi; lpFileName
0x18005dd19  call    cs:__imp_CreateFileW
0x18005dd1f  mov     [rbp+57h+var_50], rax
0x18005dd23  lea     rcx, [rax+1]
0x18005dd27  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18005dd2e  jnz     short loc_18005DD37
0x18005dd30  mov     edx, 478h
0x18005dd35  jmp     short loc_18005DD61
0x18005dd37  xorps   xmm0, xmm0
0x18005dd3a  xor     ecx, ecx
0x18005dd3c  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x18005dd40  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18005dd44  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x18005dd48  mov     [rbp+57h+FileInformation.nFileIndexLow], ecx
0x18005dd4b  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x18005dd4f  mov     rcx, rax; hFile
0x18005dd52  call    cs:__imp_GetFileInformationByHandle
0x18005dd58  test    eax, eax
0x18005dd5a  jnz     short loc_18005DD75
0x18005dd5c  mov     edx, 47Bh; void *
0x18005dd61  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18005dd68  mov     rcx, [rbp+5Fh]; this
0x18005dd6c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005dd71  mov     ebx, eax
0x18005dd73  jmp     short loc_18005DDD4
0x18005dd75  mov     eax, [rbp+57h+FileInformation.nFileIndexLow]
0x18005dd78  mov     [rbx], eax
0x18005dd7a  mov     eax, [rbp+57h+FileInformation.nFileIndexHigh]
0x18005dd7d  mov     [rbx+4], eax
0x18005dd80  mov     ecx, [rbp+57h+FileInformation.ftCreationTime.dwHighDateTime]
0x18005dd83  shl     rcx, 20h
0x18005dd87  mov     eax, [rbp+57h+FileInformation.ftCreationTime.dwLowDateTime]
0x18005dd8a  add     rcx, rax
0x18005dd8d  mov     [rbx+8], rcx
0x18005dd91  mov     ecx, [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime]
0x18005dd94  shl     rcx, 20h
0x18005dd98  mov     eax, [rbp+57h+FileInformation.ftLastAccessTime.dwLowDateTime]
0x18005dd9b  add     rcx, rax
0x18005dd9e  mov     [rbx+10h], rcx
0x18005dda2  mov     ecx, [rbp+57h+FileInformation.ftLastWriteTime.dwHighDateTime]
0x18005dda5  shl     rcx, 20h
0x18005dda9  mov     eax, [rbp+57h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x18005ddac  add     rcx, rax
0x18005ddaf  mov     [rbx+18h], rcx
0x18005ddb3  mov     eax, [rbp+57h+FileInformation.nFileSizeLow]
0x18005ddb6  mov     [rbx+30h], eax
0x18005ddb9  mov     eax, [rbp+57h+FileInformation.nFileSizeHigh]
0x18005ddbc  mov     [rbx+34h], eax
0x18005ddbf  mov     eax, [rbp+57h+FileInformation.dwFileAttributes]
0x18005ddc2  mov     [rbx+38h], eax
0x18005ddc5  mov     eax, [rbp+57h+FileInformation.nNumberOfLinks]
0x18005ddc8  mov     [rbx+40h], eax
0x18005ddcb  mov     eax, [rbp+57h+FileInformation.dwVolumeSerialNumber]
0x18005ddce  mov     [rbx+50h], rax
0x18005ddd2  xor     ebx, ebx
0x18005ddd4  lea     rcx, [rbp+57h+var_50]
0x18005ddd8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005dddd  mov     eax, ebx
0x18005dddf  mov     rcx, [rbp+57h+var_10]
0x18005dde3  xor     rcx, rsp; StackCookie
0x18005dde6  call    __security_check_cookie
0x18005ddeb  lea     r11, [rsp+90h+var_s0]
0x18005ddf3  mov     rbx, [r11+20h]
0x18005ddf7  mov     rdi, [r11+28h]
0x18005ddfb  mov     rsp, r11
0x18005ddfe  pop     rbp
0x18005ddff  retn
```
