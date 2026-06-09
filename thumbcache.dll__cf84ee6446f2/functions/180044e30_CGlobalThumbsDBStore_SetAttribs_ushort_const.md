# CGlobalThumbsDBStore::_SetAttribs(ushort const *)

- ea: `0x180044e30`
- end: `0x180044f0c`
- name: `?_SetAttribs@CGlobalThumbsDBStore@@CAXPEBG@Z`
- size: `220`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180024cbc`

## callees

- `0x18001bfe0`
- `0x18001c054`
- `0x180035830`
- `0x180044e30`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044ed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044ed8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180044e4e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180044e4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044ec9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044ec9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180044e6f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180044e6f`
- `SHELL32!SHChangeNotify` at `0x180044eed`
- `SHELL32!SHChangeNotify` at `0x180044eed`

## pseudocode

```c
void __fastcall CGlobalThumbsDBStore::_SetAttribs(const unsigned __int16 *a1)
{
  DWORD FileAttributesW; // eax
  unsigned __int64 v3; // rdx
  HANDLE FileW; // rax
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x2006) != 0x2006 )
  {
    SetFileAttributesW(a1, 0x2006u);
    if ( (int)StringCchCopyW(FileName, 0x104u, a1) >= 0 && StringCchCatW(FileName, v3, L":encryptable") >= 0 )
    {
      FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0, 0);
      if ( FileW != (HANDLE)-1LL )
        CloseHandle(FileW);
    }
    SHChangeNotify(0x2000, 5u, a1, 0);
  }
}

```

## disassembly

```asm
0x180044e30  push    rbx
0x180044e32  sub     rsp, 260h
0x180044e39  mov     rax, cs:__security_cookie
0x180044e40  xor     rax, rsp
0x180044e43  mov     [rsp+268h+var_18], rax
0x180044e4b  mov     rbx, rcx
0x180044e4e  call    cs:__imp_GetFileAttributesW
0x180044e54  cmp     eax, 0FFFFFFFFh
0x180044e57  jz      loc_180044EF3
0x180044e5d  mov     edx, 2006h; dwFileAttributes
0x180044e62  and     eax, edx
0x180044e64  cmp     eax, edx
0x180044e66  jz      loc_180044EF3
0x180044e6c  mov     rcx, rbx; lpFileName
0x180044e6f  call    cs:__imp_SetFileAttributesW
0x180044e75  mov     r8, rbx; unsigned __int16 *
0x180044e78  lea     rcx, [rsp+268h+FileName]; unsigned __int16 *
0x180044e7d  mov     edx, 104h; unsigned __int64
0x180044e82  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044e87  test    eax, eax
0x180044e89  js      short loc_180044EDE
0x180044e8b  lea     r8, aEncryptable; ":encryptable"
0x180044e92  lea     rcx, [rsp+268h+FileName]; unsigned __int16 *
0x180044e97  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180044e9c  test    eax, eax
0x180044e9e  js      short loc_180044EDE
0x180044ea0  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x180044ea9  lea     rcx, [rsp+268h+FileName]; lpFileName
0x180044eae  mov     [rsp+268h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180044eb6  xor     r9d, r9d; lpSecurityAttributes
0x180044eb9  xor     r8d, r8d; dwShareMode
0x180044ebc  mov     [rsp+268h+dwCreationDisposition], 1; dwCreationDisposition
0x180044ec4  mov     edx, 40000000h; dwDesiredAccess
0x180044ec9  call    cs:__imp_CreateFileW
0x180044ecf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044ed3  jz      short loc_180044EDE
0x180044ed5  mov     rcx, rax; hObject
0x180044ed8  call    cs:__imp_CloseHandle
0x180044ede  xor     r9d, r9d; dwItem2
0x180044ee1  mov     r8, rbx; dwItem1
0x180044ee4  mov     ecx, 2000h; wEventId
0x180044ee9  lea     edx, [r9+5]; uFlags
0x180044eed  call    cs:__imp_SHChangeNotify
0x180044ef3  mov     rcx, [rsp+268h+var_18]
0x180044efb  xor     rcx, rsp; StackCookie
0x180044efe  call    __security_check_cookie
0x180044f03  add     rsp, 260h
0x180044f0a  pop     rbx
0x180044f0b  retn
```
