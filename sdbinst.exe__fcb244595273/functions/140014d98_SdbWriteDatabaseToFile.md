# SdbWriteDatabaseToFile

- ea: `0x140014d98`
- end: `0x140014f8b`
- name: `SdbWriteDatabaseToFile`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001a678`

## callees

- `0x14001008c`
- `0x140014d98`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140014e03`
- `msvcrt!_wcsnicmp` at `0x140014e03`
- `ntdll!RtlInitUnicodeString` at `0x140014ded`
- `ntdll!RtlInitUnicodeString` at `0x140014ded`
- `ntdll!RtlFreeHeap` at `0x140014f70`
- `ntdll!RtlFreeHeap` at `0x140014f70`
- `ntdll!ZwClose` at `0x140014f48`
- `ntdll!ZwClose` at `0x140014f48`
- `ntdll!ZwCreateFile` at `0x140014ec9`
- `ntdll!ZwCreateFile` at `0x140014ec9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140014e1a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140014e1a`
- `ntdll!ZwWriteFile` at `0x140014f0c`
- `ntdll!ZwWriteFile` at `0x140014f0c`

## string_xrefs

- `0x140014e2a`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x140014e3c`: `SdbWriteDatabaseToFile`
- `0x140014f29`: `SdbWriteDatabaseToFile`
- `0x140014f18`: `Failed to write file data to disk [%x]`

## pseudocode

```c
__int64 __fastcall SdbWriteDatabaseToFile(__int64 a1, const WCHAR *a2)
{
  int v4; // eax
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING *p_DestinationString; // rax
  NTSTATUS v7; // eax
  __int64 v9; // [rsp+60h] [rbp-19h] BYREF
  PVOID P; // [rsp+68h] [rbp-11h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+77h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+F8h] [rbp+7Fh] BYREF

  v9 = 0;
  ByteOffset.QuadPart = 0;
  FileHandle = 0;
  DestinationString = 0;
  P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
  {
    v4 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &v9, 0, 0);
    v5 = v4;
    if ( v4 < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbWriteDatabaseToFile",
        147,
        "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]",
        a2,
        v4);
      goto LABEL_9;
    }
    p_DestinationString = (struct _UNICODE_STRING *)&v9;
  }
  else
  {
    p_DestinationString = &DestinationString;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = p_DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateFile(&FileHandle, 0xC0100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 5u, 0x60u, 0, 0);
  if ( v5 >= 0 )
  {
    v7 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)(a1 + 8), *(_DWORD *)(a1 + 20), &ByteOffset, 0);
    v5 = v7;
    if ( v7 < 0 )
      AslLogCallPrintf(1, "SdbWriteDatabaseToFile", 185, "Failed to write file data to disk [%x]", v7);
  }
LABEL_9:
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    ZwClose(FileHandle);
    FileHandle = 0;
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140014d98  mov     [rsp-8+arg_0], rbx
0x140014d9d  push    rbp
0x140014d9e  push    rsi
0x140014d9f  push    rdi
0x140014da0  lea     rbp, [rsp-47h]
0x140014da5  sub     rsp, 0C0h
0x140014dac  xorps   xmm0, xmm0
0x140014daf  mov     [rbp+57h+var_70], 0
0x140014db7  mov     rsi, rcx
0x140014dba  mov     qword ptr [rbp+57h+ByteOffset], 0
0x140014dc2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140014dc6  mov     [rbp+57h+FileHandle], 0
0x140014dce  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140014dd2  mov     rdi, rdx
0x140014dd5  mov     [rbp+57h+P], 0
0x140014ddd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140014de1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140014de5  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014de9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140014ded  call    cs:__imp_RtlInitUnicodeString
0x140014df3  mov     r8d, 0Ch; MaxCount
0x140014df9  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x140014e00  mov     rcx, rdi; String1
0x140014e03  call    cs:__imp__wcsnicmp
0x140014e09  test    eax, eax
0x140014e0b  jz      short loc_140014E58
0x140014e0d  xor     r9d, r9d
0x140014e10  lea     rdx, [rbp+57h+var_70]
0x140014e14  xor     r8d, r8d
0x140014e17  mov     rcx, rdi
0x140014e1a  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140014e20  mov     ebx, eax
0x140014e22  test    eax, eax
0x140014e24  jns     short loc_140014E52
0x140014e26  mov     [rsp+0D0h+FileAttributes], eax
0x140014e2a  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x140014e31  mov     r8d, 93h
0x140014e37  mov     [rsp+0D0h+AllocationSize], rdi
0x140014e3c  lea     rdx, aSdbwritedataba_0; "SdbWriteDatabaseToFile"
0x140014e43  mov     ecx, 1
0x140014e48  call    AslLogCallPrintf
0x140014e4d  jmp     loc_140014F3A
0x140014e52  lea     rax, [rbp+57h+var_70]
0x140014e56  jmp     short loc_140014E5C
0x140014e58  lea     rax, [rbp+57h+DestinationString]
0x140014e5c  mov     [rsp+0D0h+EaLength], 0; EaLength
0x140014e64  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140014e68  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x140014e71  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140014e75  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x140014e7d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140014e81  mov     [rsp+0D0h+CreateDisposition], 5; CreateDisposition
0x140014e89  xorps   xmm0, xmm0
0x140014e8c  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x140014e94  mov     edx, 0C0100080h; DesiredAccess
0x140014e99  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x140014ea1  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x140014eaa  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140014eb1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140014eb9  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140014ec0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140014ec4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014ec9  call    cs:__imp_ZwCreateFile
0x140014ecf  mov     ebx, eax
0x140014ed1  test    eax, eax
0x140014ed3  js      short loc_140014F3A
0x140014ed5  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140014ed9  lea     rax, [rbp+57h+ByteOffset]
0x140014edd  mov     qword ptr [rsp+0D0h+CreateOptions], 0; Key
0x140014ee6  xor     r9d, r9d; ApcContext
0x140014ee9  mov     qword ptr [rsp+0D0h+CreateDisposition], rax; ByteOffset
0x140014eee  xor     r8d, r8d; ApcRoutine
0x140014ef1  mov     eax, [rsi+14h]
0x140014ef4  xor     edx, edx; Event
0x140014ef6  mov     [rsp+0D0h+ShareAccess], eax; Length
0x140014efa  mov     rax, [rsi+8]
0x140014efe  mov     qword ptr [rsp+0D0h+FileAttributes], rax; Buffer
0x140014f03  lea     rax, [rbp+57h+IoStatusBlock]
0x140014f07  mov     [rsp+0D0h+AllocationSize], rax; IoStatusBlock
0x140014f0c  call    cs:__imp_ZwWriteFile
0x140014f12  mov     ebx, eax
0x140014f14  test    eax, eax
0x140014f16  jns     short loc_140014F3A
0x140014f18  lea     r9, aFailedToWriteF; "Failed to write file data to disk [%x]"
0x140014f1f  mov     dword ptr [rsp+0D0h+AllocationSize], eax
0x140014f23  mov     r8d, 0B9h
0x140014f29  lea     rdx, aSdbwritedataba_0; "SdbWriteDatabaseToFile"
0x140014f30  mov     ecx, 1
0x140014f35  call    AslLogCallPrintf
0x140014f3a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140014f3e  lea     rax, [rcx-1]
0x140014f42  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140014f46  ja      short loc_140014F56
0x140014f48  call    cs:__imp_ZwClose
0x140014f4e  mov     [rbp+57h+FileHandle], 0
0x140014f56  cmp     [rbp+57h+P], 0
0x140014f5b  jz      short loc_140014F76
0x140014f5d  mov     rcx, gs:60h
0x140014f66  xor     edx, edx; Flags
0x140014f68  mov     r8, [rbp+57h+P]; P
0x140014f6c  mov     rcx, [rcx+30h]; HeapHandle
0x140014f70  call    cs:__imp_RtlFreeHeap
0x140014f76  mov     eax, ebx
0x140014f78  mov     rbx, [rsp+0D0h+arg_0]
0x140014f80  add     rsp, 0C0h
0x140014f87  pop     rdi
0x140014f88  pop     rsi
0x140014f89  pop     rbp
0x140014f8a  retn
```
