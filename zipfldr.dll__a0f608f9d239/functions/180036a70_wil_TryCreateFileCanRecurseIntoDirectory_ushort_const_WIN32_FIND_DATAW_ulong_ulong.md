# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x180036a70`
- end: `0x180036b52`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180036550`

## callees

- `0x180036a70`
- `0x180036f50`
- `0x180046ffc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036aba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036aba`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180036ae7`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180036ae7`

## pseudocode

```c
HANDLE *__fastcall wil::TryCreateFileCanRecurseIntoDirectory(HANDLE *a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rcx
  int v6; // ecx
  __int64 FileInformation; // [rsp+40h] [rbp-18h] BYREF

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
0x180036a70  mov     [rsp+arg_18], rbx
0x180036a75  push    rdi
0x180036a76  sub     rsp, 50h
0x180036a7a  mov     rax, cs:__security_cookie
0x180036a81  xor     rax, rsp
0x180036a84  mov     [rsp+58h+var_10], rax
0x180036a89  mov     rax, rdx
0x180036a8c  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180036a95  xor     r9d, r9d; lpSecurityAttributes
0x180036a98  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180036aa0  mov     rdi, r8
0x180036aa3  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180036aab  mov     rbx, rcx
0x180036aae  mov     edx, 80010000h; dwDesiredAccess
0x180036ab3  mov     rcx, rax; lpFileName
0x180036ab6  lea     r8d, [r9+1]; dwShareMode
0x180036aba  call    cs:__imp_CreateFileW
0x180036ac0  mov     rcx, rax; hFile
0x180036ac3  mov     [rbx], rax
0x180036ac6  dec     rax
0x180036ac9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180036acd  ja      short loc_180036B37
0x180036acf  mov     r9d, 8; dwBufferSize
0x180036ad5  mov     [rsp+58h+FileInformation], 0
0x180036ade  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x180036ae3  lea     edx, [r9+1]; FileInformationClass
0x180036ae7  call    cs:__imp_GetFileInformationByHandleEx
0x180036aed  test    eax, eax
0x180036aef  jz      short loc_180036B1E
0x180036af1  mov     rax, [rsp+58h+FileInformation]
0x180036af6  test    al, 10h
0x180036af8  jz      short loc_180036B1E
0x180036afa  mov     ecx, dword ptr [rsp+58h+FileInformation+4]
0x180036afe  bt      eax, 0Ah
0x180036b02  jnb     short loc_180036B12
0x180036b04  bt      ecx, 1Ch
0x180036b08  jb      short loc_180036B12
0x180036b0a  cmp     ecx, 80000018h
0x180036b10  jnz     short loc_180036B1E
0x180036b12  test    rdi, rdi
0x180036b15  jz      short loc_180036B37
0x180036b17  mov     [rdi], eax
0x180036b19  mov     [rdi+24h], ecx
0x180036b1c  jmp     short loc_180036B37
0x180036b1e  mov     rcx, [rbx]; hObject
0x180036b21  lea     rdx, [rcx-1]
0x180036b25  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180036b29  ja      short loc_180036B30
0x180036b2b  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180036b30  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180036b37  mov     rax, rbx
0x180036b3a  mov     rcx, [rsp+58h+var_10]
0x180036b3f  xor     rcx, rsp; StackCookie
0x180036b42  call    __security_check_cookie
0x180036b47  mov     rbx, [rsp+58h+arg_18]
0x180036b4c  add     rsp, 50h
0x180036b50  pop     rdi
0x180036b51  retn
```
