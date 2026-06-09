# SetBasicFileInformation

- ea: `0x14000268c`
- end: `0x140002741`
- name: `SetBasicFileInformation`
- size: `181`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001700`

## callees

- `0x14000268c`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x140002716`
- `ntdll!NtSetInformationFile` at `0x140002716`
- `ntdll!NtClose` at `0x140002727`
- `ntdll!NtClose` at `0x140002727`
- `ntdll!NtOpenFile` at `0x1400026f1`
- `ntdll!NtOpenFile` at `0x1400026f1`

## pseudocode

```c
__int64 __fastcall SetBasicFileInformation(struct _UNICODE_STRING *a1, void *a2)
{
  NTSTATUS v3; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF

  ObjectAttributes.ObjectName = a1;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
  if ( v3 >= 0 )
    v3 = NtSetInformationFile(FileHandle, &IoStatusBlock, a2, 0x28u, FileBasicInformation);
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000268c  mov     rax, rsp
0x14000268f  mov     [rax+10h], rbx
0x140002693  mov     [rax+18h], rdi
0x140002697  push    rbp
0x140002698  mov     rbp, rsp
0x14000269b  sub     rsp, 70h
0x14000269f  xorps   xmm0, xmm0
0x1400026a2  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x1400026a6  mov     rdi, rdx
0x1400026a9  mov     dword ptr [rax-50h], 204020h
0x1400026b0  mov     edx, 100100h; DesiredAccess
0x1400026b5  mov     [rbp+FileHandle], 0
0x1400026bd  lea     rcx, [rbp+FileHandle]; FileHandle
0x1400026c1  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400026c9  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1400026cd  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1400026d5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400026d9  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400026e1  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400026e5  mov     dword ptr [rax-58h], 7
0x1400026ec  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400026f1  call    cs:__imp_NtOpenFile
0x1400026f7  mov     ebx, eax
0x1400026f9  test    eax, eax
0x1400026fb  js      short loc_14000271E
0x1400026fd  mov     rcx, [rbp+FileHandle]; FileHandle
0x140002701  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x140002705  mov     r9d, 28h ; '('; Length
0x14000270b  mov     [rsp+70h+FileInformationClass], 4; FileInformationClass
0x140002713  mov     r8, rdi; FileInformation
0x140002716  call    cs:__imp_NtSetInformationFile
0x14000271c  mov     ebx, eax
0x14000271e  mov     rcx, [rbp+FileHandle]; Handle
0x140002722  test    rcx, rcx
0x140002725  jz      short loc_14000272D
0x140002727  call    cs:__imp_NtClose
0x14000272d  lea     r11, [rsp+70h+var_s0]
0x140002732  mov     eax, ebx
0x140002734  mov     rbx, [r11+18h]
0x140002738  mov     rdi, [r11+20h]
0x14000273c  mov     rsp, r11
0x14000273f  pop     rbp
0x140002740  retn
```
