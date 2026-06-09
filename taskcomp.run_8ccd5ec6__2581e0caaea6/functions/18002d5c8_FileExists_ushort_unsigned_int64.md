# FileExists(ushort *,unsigned __int64)

- ea: `0x18002d5c8`
- end: `0x18002d70c`
- name: `?FileExists@@YAHPEAG_K@Z`
- size: `324`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002d714`
- `0x18002da70`

## callees

- `0x1800040c0`
- `0x18002d5c8`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002d6af`
- `msvcrt!wcsrchr` at `0x18002d6af`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002d61f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002d61f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002d686`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002d686`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002d653`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002d653`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002d69b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002d69b`

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
0x18002d5c8  mov     [rsp+arg_8], rbx
0x18002d5cd  push    rdi
0x18002d5ce  sub     rsp, 4A0h
0x18002d5d5  mov     rax, cs:__security_cookie
0x18002d5dc  xor     rax, rsp
0x18002d5df  mov     [rsp+4A8h+var_18], rax
0x18002d5e7  mov     rbx, rcx
0x18002d5ea  xor     edx, edx; Val
0x18002d5ec  lea     rcx, [rsp+4A8h+Buffer]; void *
0x18002d5f4  mov     r8d, 20Ah; Size
0x18002d5fa  call    memset_0
0x18002d5ff  mov     edi, 105h
0x18002d604  mov     [rsp+4A8h+FilePart], 0
0x18002d60d  mov     edx, edi; nBufferLength
0x18002d60f  lea     r9, [rsp+4A8h+FilePart]; lpFilePart
0x18002d614  lea     r8, [rsp+4A8h+Buffer]; lpBuffer
0x18002d61c  mov     rcx, rbx; lpFileName
0x18002d61f  call    cs:__imp_GetFullPathNameW
0x18002d626  nop     dword ptr [rax+rax+00h]
0x18002d62b  cmp     eax, 104h
0x18002d630  ja      loc_18002D6E8
0x18002d636  lea     r8, [rsp+4A8h+Buffer]; unsigned __int16 *
0x18002d63e  mov     edx, edi; unsigned __int64
0x18002d640  mov     rcx, rbx; unsigned __int16 *
0x18002d643  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d648  test    eax, eax
0x18002d64a  js      loc_18002D6E8
0x18002d650  mov     rcx, rbx; lpFileName
0x18002d653  call    cs:__imp_GetFileAttributesW
0x18002d65a  nop     dword ptr [rax+rax+00h]
0x18002d65f  cmp     eax, 0FFFFFFFFh
0x18002d662  jz      loc_18002D6E8
0x18002d668  test    al, 10h
0x18002d66a  jnz     short loc_18002D6E8
0x18002d66c  xor     edx, edx; Val
0x18002d66e  lea     rcx, [rsp+4A8h+FindFileData]; void *
0x18002d673  mov     r8d, 250h; Size
0x18002d679  call    memset_0
0x18002d67e  lea     rdx, [rsp+4A8h+FindFileData]; lpFindFileData
0x18002d683  mov     rcx, rbx; lpFileName
0x18002d686  call    cs:__imp_FindFirstFileW
0x18002d68d  nop     dword ptr [rax+rax+00h]
0x18002d692  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d696  jz      short loc_18002D6E8
0x18002d698  mov     rcx, rax; hFindFile
0x18002d69b  call    cs:__imp_FindClose
0x18002d6a2  nop     dword ptr [rax+rax+00h]
0x18002d6a7  mov     edx, 5Ch ; '\'; Ch
0x18002d6ac  mov     rcx, rbx; Str
0x18002d6af  call    cs:__imp_wcsrchr
0x18002d6b6  nop     dword ptr [rax+rax+00h]
0x18002d6bb  test    rax, rax
0x18002d6be  jz      short loc_18002D6E1
0x18002d6c0  mov     rcx, rax
0x18002d6c3  lea     r8, [rsp+4A8h+FindFileData.cFileName]; unsigned __int16 *
0x18002d6c8  sub     rcx, rbx
0x18002d6cb  add     rcx, 2
0x18002d6cf  sar     rcx, 1
0x18002d6d2  sub     rdi, rcx
0x18002d6d5  lea     rcx, [rax+2]; unsigned __int16 *
0x18002d6d9  mov     rdx, rdi; unsigned __int64
0x18002d6dc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d6e1  mov     eax, 1
0x18002d6e6  jmp     short loc_18002D6EA
0x18002d6e8  xor     eax, eax
0x18002d6ea  mov     rcx, [rsp+4A8h+var_18]
0x18002d6f2  xor     rcx, rsp; StackCookie
0x18002d6f5  call    __security_check_cookie
0x18002d6fa  mov     rbx, [rsp+4A8h+arg_8]
0x18002d702  add     rsp, 4A0h
0x18002d709  pop     rdi
0x18002d70a  retn
```
