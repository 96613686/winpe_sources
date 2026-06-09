# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x180007a44`
- end: `0x180007b0f`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800070c8`
- `0x18001aa00`

## callees

- `0x180007a44`
- `0x18000d9d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007a7f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007a7f`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180007ac2`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180007ac2`

## pseudocode

```c
_QWORD *__fastcall wil::TryCreateFileCanRecurseIntoDirectory(_QWORD *a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rax
  int v7; // ecx
  __int64 FileInformation; // [rsp+50h] [rbp+8h] BYREF

  FileW = (char *)CreateFileW(a2, 0x80000000, 5u, 0, 3u, 0x2200000u, 0);
  *a1 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileInformation = 0;
    if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u)
      && (FileInformation & 0x10) != 0
      && ((v7 = HIDWORD(FileInformation), (FileInformation & 0x400) == 0)
       || (FileInformation & 0x1000000000000000LL) != 0
       || HIDWORD(FileInformation) == -2147483624) )
    {
      if ( a3 )
      {
        *a3 = FileInformation;
        a3[9] = v7;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a1,
        -1);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180007a44  mov     [rsp+arg_8], rbx
0x180007a49  push    rdi
0x180007a4a  sub     rsp, 40h
0x180007a4e  mov     rax, rdx
0x180007a51  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180007a5a  xor     r9d, r9d; lpSecurityAttributes
0x180007a5d  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180007a65  mov     rbx, r8
0x180007a68  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180007a70  mov     rdi, rcx
0x180007a73  mov     edx, 80000000h; dwDesiredAccess
0x180007a78  mov     rcx, rax; lpFileName
0x180007a7b  lea     r8d, [r9+5]; dwShareMode
0x180007a7f  call    cs:__imp_CreateFileW
0x180007a86  nop     dword ptr [rax+rax+00h]
0x180007a8b  mov     [rdi], rax
0x180007a8e  lea     rdx, [rax-1]
0x180007a92  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180007a96  jbe     short loc_180007AA7
0x180007a98  mov     rbx, [rsp+48h+arg_8]
0x180007a9d  mov     rax, rdi
0x180007aa0  add     rsp, 40h
0x180007aa4  pop     rdi
0x180007aa5  retn
0x180007aa7  mov     r9d, 8; dwBufferSize
0x180007aad  mov     [rsp+48h+FileInformation], 0
0x180007ab6  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x180007abb  mov     rcx, rax; hFile
0x180007abe  lea     edx, [r9+1]; FileInformationClass
0x180007ac2  call    cs:__imp_GetFileInformationByHandleEx
0x180007ac9  nop     dword ptr [rax+rax+00h]
0x180007ace  test    eax, eax
0x180007ad0  jz      short loc_180007ADB
0x180007ad2  mov     rax, [rsp+48h+FileInformation]
0x180007ad7  test    al, 10h
0x180007ad9  jnz     short loc_180007AF5
0x180007adb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007adf  mov     rcx, rdi
0x180007ae2  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180007ae7  jmp     short loc_180007A98
0x180007ae9  test    rbx, rbx
0x180007aec  jz      short loc_180007A98
0x180007aee  mov     [rbx], eax
0x180007af0  mov     [rbx+24h], ecx
0x180007af3  jmp     short loc_180007A98
0x180007af5  mov     ecx, dword ptr [rsp+48h+FileInformation+4]
0x180007af9  bt      eax, 0Ah
0x180007afd  jnb     short loc_180007AE9
0x180007aff  bt      ecx, 1Ch
0x180007b03  jb      short loc_180007AE9
0x180007b05  cmp     ecx, 80000018h
0x180007b0b  jnz     short loc_180007ADB
0x180007b0d  jmp     short loc_180007AE9
```
