# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x18003f7dc`
- end: `0x18003f8a3`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `199`
- prototype: `HANDLE *__fastcall(HANDLE *, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18003f130`

## callees

- `0x180031b0c`
- `0x18003f7dc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f817`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f817`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003f845`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003f845`

## pseudocode

```c
HANDLE *__fastcall wil::TryCreateFileCanRecurseIntoDirectory(HANDLE *a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rax
  int v6; // ecx
  __int64 FileInformation; // [rsp+50h] [rbp+8h] BYREF

  FileW = (char *)CreateFileW(a2, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
  *a1 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileInformation = 0;
    if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u)
      && (FileInformation & 0x10) != 0
      && ((v6 = HIDWORD(FileInformation), (FileInformation & 0x400) == 0)
       || (FileInformation & 0x1000000000000000LL) != 0
       || HIDWORD(FileInformation) == -2147483624) )
    {
      if ( a3 )
      {
        *a3 = FileInformation;
        a3[9] = v6;
      }
    }
    else
    {
      if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a1);
      *a1 = (HANDLE)-1LL;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18003f7dc  mov     [rsp+arg_8], rbx
0x18003f7e1  push    rdi
0x18003f7e2  sub     rsp, 40h
0x18003f7e6  mov     rax, rdx
0x18003f7e9  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18003f7f2  xor     r9d, r9d; lpSecurityAttributes
0x18003f7f5  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003f7fd  mov     rdi, r8
0x18003f800  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18003f808  mov     rbx, rcx
0x18003f80b  mov     edx, 80010000h; dwDesiredAccess
0x18003f810  mov     rcx, rax; lpFileName
0x18003f813  lea     r8d, [r9+1]; dwShareMode
0x18003f817  call    cs:__imp_CreateFileW
0x18003f81d  mov     [rbx], rax
0x18003f820  lea     rdx, [rax-1]
0x18003f824  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003f828  ja      short loc_18003F895
0x18003f82a  mov     r9d, 8; dwBufferSize
0x18003f830  mov     [rsp+48h+FileInformation], 0
0x18003f839  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x18003f83e  mov     rcx, rax; hFile
0x18003f841  lea     edx, [r9+1]; FileInformationClass
0x18003f845  call    cs:__imp_GetFileInformationByHandleEx
0x18003f84b  test    eax, eax
0x18003f84d  jz      short loc_18003F87C
0x18003f84f  mov     rax, [rsp+48h+FileInformation]
0x18003f854  test    al, 10h
0x18003f856  jz      short loc_18003F87C
0x18003f858  mov     ecx, dword ptr [rsp+48h+FileInformation+4]
0x18003f85c  bt      eax, 0Ah
0x18003f860  jnb     short loc_18003F870
0x18003f862  bt      ecx, 1Ch
0x18003f866  jb      short loc_18003F870
0x18003f868  cmp     ecx, 80000018h
0x18003f86e  jnz     short loc_18003F87C
0x18003f870  test    rdi, rdi
0x18003f873  jz      short loc_18003F895
0x18003f875  mov     [rdi], eax
0x18003f877  mov     [rdi+24h], ecx
0x18003f87a  jmp     short loc_18003F895
0x18003f87c  mov     rcx, [rbx]; hObject
0x18003f87f  lea     rax, [rcx-1]
0x18003f883  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f887  ja      short loc_18003F88E
0x18003f889  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003f88e  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18003f895  mov     rax, rbx
0x18003f898  mov     rbx, [rsp+48h+arg_8]
0x18003f89d  add     rsp, 40h
0x18003f8a1  pop     rdi
0x18003f8a2  retn
```
