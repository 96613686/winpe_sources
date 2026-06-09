# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x180008314`
- end: `0x1800083d2`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `190`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180007a7c`
- `0x180018ff4`

## callees

- `0x180008314`
- `0x18000ccf4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000834f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000834f`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000838b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000838b`

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
0x180008314  mov     [rsp+arg_8], rbx
0x180008319  push    rdi
0x18000831a  sub     rsp, 40h
0x18000831e  mov     rax, rdx
0x180008321  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000832a  xor     r9d, r9d; lpSecurityAttributes
0x18000832d  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180008335  mov     rbx, r8
0x180008338  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180008340  mov     rdi, rcx
0x180008343  mov     edx, 80000000h; dwDesiredAccess
0x180008348  mov     rcx, rax; lpFileName
0x18000834b  lea     r8d, [r9+5]; dwShareMode
0x18000834f  call    cs:__imp_CreateFileW
0x180008355  mov     [rdi], rax
0x180008358  lea     rdx, [rax-1]
0x18000835c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180008360  jbe     short loc_180008370
0x180008362  mov     rbx, [rsp+48h+arg_8]
0x180008367  mov     rax, rdi
0x18000836a  add     rsp, 40h
0x18000836e  pop     rdi
0x18000836f  retn
0x180008370  mov     r9d, 8; dwBufferSize
0x180008376  mov     [rsp+48h+FileInformation], 0
0x18000837f  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x180008384  mov     rcx, rax; hFile
0x180008387  lea     edx, [r9+1]; FileInformationClass
0x18000838b  call    cs:__imp_GetFileInformationByHandleEx
0x180008391  test    eax, eax
0x180008393  jz      short loc_18000839E
0x180008395  mov     rax, [rsp+48h+FileInformation]
0x18000839a  test    al, 10h
0x18000839c  jnz     short loc_1800083B8
0x18000839e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800083a2  mov     rcx, rdi
0x1800083a5  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800083aa  jmp     short loc_180008362
0x1800083ac  test    rbx, rbx
0x1800083af  jz      short loc_180008362
0x1800083b1  mov     [rbx], eax
0x1800083b3  mov     [rbx+24h], ecx
0x1800083b6  jmp     short loc_180008362
0x1800083b8  mov     ecx, dword ptr [rsp+48h+FileInformation+4]
0x1800083bc  bt      eax, 0Ah
0x1800083c0  jnb     short loc_1800083AC
0x1800083c2  bt      ecx, 1Ch
0x1800083c6  jb      short loc_1800083AC
0x1800083c8  cmp     ecx, 80000018h
0x1800083ce  jnz     short loc_18000839E
0x1800083d0  jmp     short loc_1800083AC
```
