# SclpFileGetLastWriteTime

- ea: `0x180004f5c`
- end: `0x180005055`
- name: `SclpFileGetLastWriteTime`
- size: `249`
- prototype: `__int64 __fastcall(const WCHAR *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800051d8`
- `0x18000548c`

## callees

- `0x180001c74`
- `0x180004f5c`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtClose` at `0x18000502c`
- `ntdll!NtClose` at `0x18000502c`
- `ntdll!NtQueryInformationFile` at `0x180005010`
- `ntdll!NtQueryInformationFile` at `0x180005010`
- `ntdll!NtOpenFile` at `0x180004fea`
- `ntdll!NtOpenFile` at `0x180004fea`

## pseudocode

```c
__int64 __fastcall SclpFileGetLastWriteTime(const WCHAR *a1, _QWORD *a2)
{
  NTSTATUS v3; // ebx
  void *FileHandle; // [rsp+30h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING v7; // [rsp+48h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  __int128 FileInformation; // [rsp+88h] [rbp+1Fh] BYREF
  __int128 v10; // [rsp+98h] [rbp+2Fh]
  __int64 v11; // [rsp+A8h] [rbp+3Fh]

  v11 = 0;
  FileHandle = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  v10 = 0;
  INIT_OBJA_EX((__int64)&ObjectAttributes, &v7, a1, 64, 0);
  v3 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u);
  if ( v3 >= 0 )
  {
    v3 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    if ( v3 >= 0 )
      *a2 = v10;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180004f5c  mov     [rsp-8+arg_10], rbx
0x180004f61  mov     [rsp-8+arg_18], rdi
0x180004f66  push    rbp
0x180004f67  lea     rbp, [rsp-57h]
0x180004f6c  sub     rsp, 0C0h
0x180004f73  mov     rax, cs:__security_cookie
0x180004f7a  xor     rax, rsp
0x180004f7d  mov     [rbp+57h+var_10], rax
0x180004f81  xorps   xmm0, xmm0
0x180004f84  xor     eax, eax
0x180004f86  xorps   xmm1, xmm1
0x180004f89  mov     [rbp+57h+var_18], rax
0x180004f8d  mov     rdi, rdx
0x180004f90  mov     [rbp+57h+FileHandle], rax
0x180004f94  mov     r8, rcx
0x180004f97  mov     qword ptr [rsp+0C0h+ShareAccess], rax
0x180004f9c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180004fa0  lea     r9d, [rax+40h]
0x180004fa4  lea     rdx, [rbp+57h+var_78]
0x180004fa8  lea     rcx, [rbp+57h+ObjectAttributes]
0x180004fac  movups  [rbp+57h+var_78], xmm0
0x180004fb0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180004fb4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180004fb8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180004fbc  movups  [rbp+57h+FileInformation], xmm1
0x180004fc0  movups  [rbp+57h+var_28], xmm1
0x180004fc4  call    INIT_OBJA_EX
0x180004fc9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180004fcd  mov     [rsp+0C0h+OpenOptions], 4020h; OpenOptions
0x180004fd5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180004fd9  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x180004fe1  mov     edx, 100080h; DesiredAccess
0x180004fe6  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180004fea  call    cs:__imp_NtOpenFile
0x180004ff0  mov     ebx, eax
0x180004ff2  test    eax, eax
0x180004ff4  js      short loc_180005023
0x180004ff6  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180004ffa  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180004ffe  mov     r9d, 28h ; '('; Length
0x180005004  mov     [rsp+0C0h+ShareAccess], 4; FileInformationClass
0x18000500c  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180005010  call    cs:__imp_NtQueryInformationFile
0x180005016  mov     ebx, eax
0x180005018  test    eax, eax
0x18000501a  js      short loc_180005023
0x18000501c  mov     rax, qword ptr [rbp+57h+var_28]
0x180005020  mov     [rdi], rax
0x180005023  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180005027  test    rcx, rcx
0x18000502a  jz      short loc_180005032
0x18000502c  call    cs:__imp_NtClose
0x180005032  mov     eax, ebx
0x180005034  mov     rcx, [rbp+57h+var_10]
0x180005038  xor     rcx, rsp; StackCookie
0x18000503b  call    __security_check_cookie
0x180005040  lea     r11, [rsp+0C0h+var_s0]
0x180005048  mov     rbx, [r11+20h]
0x18000504c  mov     rdi, [r11+28h]
0x180005050  mov     rsp, r11
0x180005053  pop     rbp
0x180005054  retn
```
