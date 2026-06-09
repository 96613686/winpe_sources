# StorageService::IsValidStorageSenseDrive(ushort *)

- ea: `0x180025e40`
- end: `0x180025ef4`
- name: `?IsValidStorageSenseDrive@StorageService@@IEAAHPEAG@Z`
- size: `180`
- prototype: `int(StorageService *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180027080`

## callees

- `0x180025e40`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025eb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025eb2`
- `ntdll!NtQueryVolumeInformationFile` at `0x180025ea7`
- `ntdll!NtQueryVolumeInformationFile` at `0x180025ea7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025e7f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025e7f`

## pseudocode

```c
__int64 __fastcall StorageService::IsValidStorageSenseDrive(StorageService *this, unsigned __int16 *a2)
{
  unsigned int v2; // edi
  HANDLE FileW; // rax
  void *v4; // rsi
  NTSTATUS v5; // ebx
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF
  __int64 FsInformation; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  FsInformation = 0;
  IoStatusBlock = 0;
  FileW = CreateFileW(a2, 0x80u, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v4 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v5 = NtQueryVolumeInformationFile(FileW, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
    CloseHandle(v4);
    if ( v5 >= 0 )
    {
      if ( (_DWORD)FsInformation == 36 )
      {
        return 1;
      }
      else if ( (_DWORD)FsInformation == 7 )
      {
        return (FsInformation & 0x400000000LL) == 0;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180025e40  mov     rax, rsp
0x180025e43  mov     [rax+10h], rbx
0x180025e47  mov     [rax+18h], rsi
0x180025e4b  mov     [rax+8], rcx
0x180025e4f  push    rdi
0x180025e50  sub     rsp, 50h
0x180025e54  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFFh
0x180025e5c  xor     edi, edi
0x180025e5e  mov     rcx, rdx; lpFileName
0x180025e61  mov     [rax+8], rdi
0x180025e65  mov     edx, 80h; dwDesiredAccess
0x180025e6a  xorps   xmm0, xmm0
0x180025e6d  mov     [rax-30h], edx
0x180025e70  xor     r9d, r9d; lpSecurityAttributes
0x180025e73  lea     r8d, [rdi+3]; dwShareMode
0x180025e77  mov     [rax-38h], r8d
0x180025e7b  movups  xmmword ptr [rax-18h], xmm0
0x180025e7f  call    cs:__imp_CreateFileW
0x180025e85  mov     rsi, rax
0x180025e88  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025e8c  jz      short loc_180025EE2
0x180025e8e  lea     r9d, [rdi+8]; Length
0x180025e92  mov     [rsp+58h+FsInformationClass], 4; FsInformationClass
0x180025e9a  lea     r8, [rsp+58h+FsInformation]; FsInformation
0x180025e9f  mov     rcx, rax; FileHandle
0x180025ea2  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x180025ea7  call    cs:__imp_NtQueryVolumeInformationFile
0x180025ead  mov     rcx, rsi; hObject
0x180025eb0  mov     ebx, eax
0x180025eb2  call    cs:__imp_CloseHandle
0x180025eb8  test    ebx, ebx
0x180025eba  js      short loc_180025EE2
0x180025ebc  cmp     [rsp+58h+FsInformation], 24h ; '$'
0x180025ec1  jnz     short loc_180025ECA
0x180025ec3  mov     edi, 1
0x180025ec8  jmp     short loc_180025EE2
0x180025eca  cmp     [rsp+58h+FsInformation], 7
0x180025ecf  jnz     short loc_180025EE2
0x180025ed1  test    [rsp+58h+arg_4], 4
0x180025ed6  mov     ecx, edi
0x180025ed8  mov     edi, 1
0x180025edd  cmovz   ecx, edi
0x180025ee0  mov     edi, ecx
0x180025ee2  mov     rbx, [rsp+58h+arg_8]
0x180025ee7  mov     eax, edi
0x180025ee9  mov     rsi, [rsp+58h+arg_10]
0x180025eee  add     rsp, 50h
0x180025ef2  pop     rdi
0x180025ef3  retn
```
