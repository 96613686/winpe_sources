# set_file_time_and_close

- ea: `0x1800b30b0`
- end: `0x1800b31ce`
- name: `set_file_time_and_close`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800b09b8`
- `0x1800b205c`

## callees

- `0x1800b30b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800b30ef`
- `KERNEL32!CloseHandle` at `0x1800b319c`
- `KERNEL32!CloseHandle` at `0x1800b30ef`
- `KERNEL32!CloseHandle` at `0x1800b319c`
- `KERNEL32!SetFileTime` at `0x1800b318d`
- `KERNEL32!SetFileTime` at `0x1800b318d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b30d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b30d0`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x1800b312f`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x1800b312f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b3166`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b3166`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800b31b1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800b31b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800b3119`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800b3119`

## pseudocode

```c
int set_file_time_and_close()
{
  char *Value; // rax
  char *v1; // rbx
  WORD v2; // dx
  WORD v3; // cx
  HANDLE FileA; // rax
  void *v5; // rdi
  FILETIME CreationTime; // [rsp+50h] [rbp+8h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp+10h] BYREF

  FileTime = 0;
  CreationTime = 0;
  Value = (char *)TlsGetValue(dwUnZIPTlsIndex);
  v1 = Value;
  if ( Value )
  {
    CloseHandle(*(HANDLE *)(Value + 72178));
    v2 = *((_WORD *)v1 + 2527);
    v3 = *((_WORD *)v1 + 2528);
    *(_QWORD *)(v1 + 72178) = -1;
    DosDateTimeToFileTime(v3, v2, &FileTime);
    LocalFileTimeToFileTime(&FileTime, &CreationTime);
    FileA = CreateFileA(v1 + 4020, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
    v5 = FileA;
    if ( FileA != (HANDLE)-1LL )
    {
      SetFileTime(FileA, &CreationTime, &CreationTime, &CreationTime);
      CloseHandle(v5);
    }
    LODWORD(Value) = SetFileAttributesA(v1 + 4020, *((_DWORD *)v1 + 1135));
  }
  return (int)Value;
}

```

## disassembly

```asm
0x1800b30b0  mov     rax, rsp
0x1800b30b3  mov     [rax+18h], rbx
0x1800b30b7  mov     [rax+20h], rsi
0x1800b30bb  push    rdi
0x1800b30bc  sub     rsp, 40h
0x1800b30c0  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800b30c6  xor     edi, edi
0x1800b30c8  mov     [rax+10h], rdi
0x1800b30cc  mov     [rax+8], rdi
0x1800b30d0  call    cs:__imp_TlsGetValue
0x1800b30d7  nop     dword ptr [rax+rax+00h]
0x1800b30dc  mov     rbx, rax
0x1800b30df  test    rax, rax
0x1800b30e2  jz      loc_1800B31BD
0x1800b30e8  mov     rcx, [rax+119F2h]; hObject
0x1800b30ef  call    cs:__imp_CloseHandle
0x1800b30f6  nop     dword ptr [rax+rax+00h]
0x1800b30fb  movzx   edx, word ptr [rbx+13BEh]; wFatTime
0x1800b3102  lea     r8, [rsp+48h+FileTime]; lpFileTime
0x1800b3107  movzx   ecx, word ptr [rbx+13C0h]; wFatDate
0x1800b310e  mov     qword ptr [rbx+119F2h], 0FFFFFFFFFFFFFFFFh
0x1800b3119  call    cs:__imp_DosDateTimeToFileTime
0x1800b3120  nop     dword ptr [rax+rax+00h]
0x1800b3125  lea     rdx, [rsp+48h+CreationTime]; lpFileTime
0x1800b312a  lea     rcx, [rsp+48h+FileTime]; lpLocalFileTime
0x1800b312f  call    cs:__imp_LocalFileTimeToFileTime
0x1800b3136  nop     dword ptr [rax+rax+00h]
0x1800b313b  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x1800b3140  lea     rsi, [rbx+0FB4h]
0x1800b3147  mov     rcx, rsi; lpFileName
0x1800b314a  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b3152  xor     r9d, r9d; lpSecurityAttributes
0x1800b3155  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800b315d  mov     edx, 0C0000000h; dwDesiredAccess
0x1800b3162  lea     r8d, [rdi+1]; dwShareMode
0x1800b3166  call    cs:__imp_CreateFileA
0x1800b316d  nop     dword ptr [rax+rax+00h]
0x1800b3172  mov     rdi, rax
0x1800b3175  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b3179  jz      short loc_1800B31A8
0x1800b317b  lea     r9, [rsp+48h+CreationTime]; lpLastWriteTime
0x1800b3180  mov     rcx, rax; hFile
0x1800b3183  lea     r8, [rsp+48h+CreationTime]; lpLastAccessTime
0x1800b3188  lea     rdx, [rsp+48h+CreationTime]; lpCreationTime
0x1800b318d  call    cs:__imp_SetFileTime
0x1800b3194  nop     dword ptr [rax+rax+00h]
0x1800b3199  mov     rcx, rdi; hObject
0x1800b319c  call    cs:__imp_CloseHandle
0x1800b31a3  nop     dword ptr [rax+rax+00h]
0x1800b31a8  mov     edx, [rbx+11BCh]; dwFileAttributes
0x1800b31ae  mov     rcx, rsi; lpFileName
0x1800b31b1  call    cs:__imp_SetFileAttributesA
0x1800b31b8  nop     dword ptr [rax+rax+00h]
0x1800b31bd  mov     rbx, [rsp+48h+arg_10]
0x1800b31c2  mov     rsi, [rsp+48h+arg_18]
0x1800b31c7  add     rsp, 40h
0x1800b31cb  pop     rdi
0x1800b31cc  retn
```
