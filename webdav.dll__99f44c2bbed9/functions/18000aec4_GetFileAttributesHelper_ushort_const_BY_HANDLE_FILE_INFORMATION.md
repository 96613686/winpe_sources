# GetFileAttributesHelper(ushort const *,_BY_HANDLE_FILE_INFORMATION *)

- ea: `0x18000aec4`
- end: `0x18000af5f`
- name: `?GetFileAttributesHelper@@YAJPEBGPEAU_BY_HANDLE_FILE_INFORMATION@@@Z`
- size: `155`
- prototype: `int(const unsigned __int16 *, struct _BY_HANDLE_FILE_INFORMATION *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005334`
- `0x18000ad84`
- `0x18000af68`

## callees

- `0x18000aec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af2f`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000af25`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000af25`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aef7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af47`

## pseudocode

```c
__int64 __fastcall GetFileAttributesHelper(const unsigned __int16 *a1, struct _BY_HANDLE_FILE_INFORMATION *a2)
{
  signed int v2; // ebx
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v6; // eax

  v2 = 0;
  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x2000006u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_12;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_12:
    if ( !GetFileInformationByHandle(FileW, a2) )
    {
      v6 = GetLastError();
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
    }
    CloseHandle(FileW);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000aec4  mov     rax, rsp
0x18000aec7  mov     [rax+8], rbx
0x18000aecb  mov     [rax+10h], rsi
0x18000aecf  push    rdi
0x18000aed0  sub     rsp, 40h
0x18000aed4  xor     ebx, ebx
0x18000aed6  mov     rsi, rdx
0x18000aed9  mov     [rax-18h], rbx
0x18000aedd  xor     r9d, r9d; lpSecurityAttributes
0x18000aee0  mov     dword ptr [rax-20h], 2000006h
0x18000aee7  mov     edx, 80000000h; dwDesiredAccess
0x18000aeec  mov     dword ptr [rax-28h], 3
0x18000aef3  lea     r8d, [rbx+7]; dwShareMode
0x18000aef7  call    cs:__imp_CreateFileW
0x18000aefd  mov     rdi, rax
0x18000af00  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000af04  jnz     short loc_18000AF1F
0x18000af06  call    cs:__imp_GetLastError
0x18000af0c  mov     ebx, eax
0x18000af0e  test    eax, eax
0x18000af10  jle     short loc_18000AF1B
0x18000af12  movzx   ebx, ax
0x18000af15  or      ebx, 80070000h
0x18000af1b  test    ebx, ebx
0x18000af1d  js      short loc_18000AF4D
0x18000af1f  mov     rdx, rsi; lpFileInformation
0x18000af22  mov     rcx, rdi; hFile
0x18000af25  call    cs:__imp_GetFileInformationByHandle
0x18000af2b  test    eax, eax
0x18000af2d  jnz     short loc_18000AF44
0x18000af2f  call    cs:__imp_GetLastError
0x18000af35  mov     ebx, eax
0x18000af37  test    eax, eax
0x18000af39  jle     short loc_18000AF44
0x18000af3b  movzx   ebx, ax
0x18000af3e  or      ebx, 80070000h
0x18000af44  mov     rcx, rdi; hObject
0x18000af47  call    cs:__imp_CloseHandle
0x18000af4d  mov     rsi, [rsp+48h+arg_8]
0x18000af52  mov     eax, ebx
0x18000af54  mov     rbx, [rsp+48h+arg_0]
0x18000af59  add     rsp, 40h
0x18000af5d  pop     rdi
0x18000af5e  retn
```
