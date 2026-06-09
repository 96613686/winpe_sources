# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x18003bf34`
- end: `0x18003c003`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18003b474`

## callees

- `0x18001dcf4`
- `0x18003bf34`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bf7c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bf7c`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003bfb1`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003bfb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HANDLE *__fastcall wil::TryCreateFileCanRecurseIntoDirectory(HANDLE *a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rax
  int v6; // ecx
  __int64 FileInformation; // [rsp+48h] [rbp-10h] BYREF

  FileW = (char *)CreateFileW(a2, 0x10000u, 1u, 0, 3u, 0x2200000u, 0);
  *a1 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileInformation = 0;
    if ( GetFileInformationByHandleEx(*a1, FileAttributeTagInfo, &FileInformation, 8u)
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
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a1,
        -1);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18003bf34  mov     [rsp+arg_8], rbx
0x18003bf39  mov     [rsp+arg_0], rcx
0x18003bf3e  push    rdi
0x18003bf3f  sub     rsp, 50h
0x18003bf43  mov     rdi, r8
0x18003bf46  mov     rax, rdx
0x18003bf49  mov     rbx, rcx
0x18003bf4c  mov     [rsp+58h+var_18], 0
0x18003bf54  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18003bf5d  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003bf65  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18003bf6d  xor     r9d, r9d; lpSecurityAttributes
0x18003bf70  mov     edx, 10000h; dwDesiredAccess
0x18003bf75  lea     r8d, [r9+1]; dwShareMode
0x18003bf79  mov     rcx, rax; lpFileName
0x18003bf7c  call    cs:__imp_CreateFileW
0x18003bf82  mov     [rbx], rax
0x18003bf85  mov     [rsp+58h+var_18], 1
0x18003bf8d  dec     rax
0x18003bf90  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003bf94  ja      short loc_18003BFF4
0x18003bf96  mov     [rsp+58h+FileInformation], 0
0x18003bf9f  mov     r9d, 8; dwBufferSize
0x18003bfa5  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x18003bfaa  lea     edx, [r9+1]; FileInformationClass
0x18003bfae  mov     rcx, [rbx]; hFile
0x18003bfb1  call    cs:__imp_GetFileInformationByHandleEx
0x18003bfb7  test    eax, eax
0x18003bfb9  jz      short loc_18003BFE8
0x18003bfbb  mov     rax, [rsp+58h+FileInformation]
0x18003bfc0  test    al, 10h
0x18003bfc2  jz      short loc_18003BFE8
0x18003bfc4  mov     ecx, dword ptr [rsp+58h+FileInformation+4]
0x18003bfc8  bt      eax, 0Ah
0x18003bfcc  jnb     short loc_18003BFDC
0x18003bfce  bt      ecx, 1Ch
0x18003bfd2  jb      short loc_18003BFDC
0x18003bfd4  cmp     ecx, 80000018h
0x18003bfda  jnz     short loc_18003BFE8
0x18003bfdc  test    rdi, rdi
0x18003bfdf  jz      short loc_18003BFF4
0x18003bfe1  mov     [rdi], eax
0x18003bfe3  mov     [rdi+24h], ecx
0x18003bfe6  jmp     short loc_18003BFF4
0x18003bfe8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003bfec  mov     rcx, rbx
0x18003bfef  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003bff4  mov     rax, rbx
0x18003bff7  mov     rbx, [rsp+58h+arg_8]
0x18003bffc  add     rsp, 50h
0x18003c000  pop     rdi
0x18003c001  retn
```
