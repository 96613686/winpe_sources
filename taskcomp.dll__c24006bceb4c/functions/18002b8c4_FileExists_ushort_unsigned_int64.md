# FileExists(ushort *,unsigned __int64)

- ea: `0x18002b8c4`
- end: `0x18002b9e1`
- name: `?FileExists@@YAHPEAG_K@Z`
- size: `285`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002b9e8`
- `0x18002bd00`

## callees

- `0x180003ef0`
- `0x18002b8c4`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002b98b`
- `msvcrt!wcsrchr` at `0x18002b98b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002b91b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002b91b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002b96e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002b96e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002b945`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002b945`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002b97d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002b97d`

## pseudocode

```c
__int64 __fastcall FileExists(unsigned __int16 *a1)
{
  DWORD FileAttributesW; // eax
  HANDLE FirstFileW; // rax
  wchar_t *v4; // rax
  LPWSTR FilePart; // [rsp+20h] [rbp-488h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-478h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  FilePart = 0;
  if ( GetFullPathNameW(a1, 0x105u, Buffer, &FilePart) > 0x104 )
    return 0;
  if ( (int)StringCchCopyW(a1, 0x105u, Buffer) < 0 )
    return 0;
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
    return 0;
  if ( (FileAttributesW & 0x10) != 0 )
    return 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a1, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  FindClose(FirstFileW);
  v4 = wcsrchr(a1, 0x5Cu);
  if ( v4 )
    StringCchCopyW(v4 + 1, 261 - (((char *)v4 - (char *)a1 + 2) >> 1), FindFileData.cFileName);
  return 1;
}

```

## disassembly

```asm
0x18002b8c4  mov     [rsp+arg_8], rbx
0x18002b8c9  push    rdi
0x18002b8ca  sub     rsp, 4A0h
0x18002b8d1  mov     rax, cs:__security_cookie
0x18002b8d8  xor     rax, rsp
0x18002b8db  mov     [rsp+4A8h+var_18], rax
0x18002b8e3  mov     rbx, rcx
0x18002b8e6  xor     edx, edx; Val
0x18002b8e8  lea     rcx, [rsp+4A8h+Buffer]; void *
0x18002b8f0  mov     r8d, 20Ah; Size
0x18002b8f6  call    memset_0
0x18002b8fb  mov     edi, 105h
0x18002b900  mov     [rsp+4A8h+FilePart], 0
0x18002b909  mov     edx, edi; nBufferLength
0x18002b90b  lea     r9, [rsp+4A8h+FilePart]; lpFilePart
0x18002b910  lea     r8, [rsp+4A8h+Buffer]; lpBuffer
0x18002b918  mov     rcx, rbx; lpFileName
0x18002b91b  call    cs:__imp_GetFullPathNameW
0x18002b921  cmp     eax, 104h
0x18002b926  ja      loc_18002B9BE
0x18002b92c  lea     r8, [rsp+4A8h+Buffer]; unsigned __int16 *
0x18002b934  mov     edx, edi; unsigned __int64
0x18002b936  mov     rcx, rbx; unsigned __int16 *
0x18002b939  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b93e  test    eax, eax
0x18002b940  js      short loc_18002B9BE
0x18002b942  mov     rcx, rbx; lpFileName
0x18002b945  call    cs:__imp_GetFileAttributesW
0x18002b94b  cmp     eax, 0FFFFFFFFh
0x18002b94e  jz      short loc_18002B9BE
0x18002b950  test    al, 10h
0x18002b952  jnz     short loc_18002B9BE
0x18002b954  xor     edx, edx; Val
0x18002b956  lea     rcx, [rsp+4A8h+FindFileData]; void *
0x18002b95b  mov     r8d, 250h; Size
0x18002b961  call    memset_0
0x18002b966  lea     rdx, [rsp+4A8h+FindFileData]; lpFindFileData
0x18002b96b  mov     rcx, rbx; lpFileName
0x18002b96e  call    cs:__imp_FindFirstFileW
0x18002b974  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b978  jz      short loc_18002B9BE
0x18002b97a  mov     rcx, rax; hFindFile
0x18002b97d  call    cs:__imp_FindClose
0x18002b983  mov     edx, 5Ch ; '\'; Ch
0x18002b988  mov     rcx, rbx; Str
0x18002b98b  call    cs:__imp_wcsrchr
0x18002b991  test    rax, rax
0x18002b994  jz      short loc_18002B9B7
0x18002b996  mov     rcx, rax
0x18002b999  lea     r8, [rsp+4A8h+FindFileData.cFileName]; unsigned __int16 *
0x18002b99e  sub     rcx, rbx
0x18002b9a1  add     rcx, 2
0x18002b9a5  sar     rcx, 1
0x18002b9a8  sub     rdi, rcx
0x18002b9ab  lea     rcx, [rax+2]; unsigned __int16 *
0x18002b9af  mov     rdx, rdi; unsigned __int64
0x18002b9b2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b9b7  mov     eax, 1
0x18002b9bc  jmp     short loc_18002B9C0
0x18002b9be  xor     eax, eax
0x18002b9c0  mov     rcx, [rsp+4A8h+var_18]
0x18002b9c8  xor     rcx, rsp; StackCookie
0x18002b9cb  call    __security_check_cookie
0x18002b9d0  mov     rbx, [rsp+4A8h+arg_8]
0x18002b9d8  add     rsp, 4A0h
0x18002b9df  pop     rdi
0x18002b9e0  retn
```
