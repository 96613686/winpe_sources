# GetStatisticsFromRedir

- ea: `0x18000ad90`
- end: `0x18000aec1`
- name: `GetStatisticsFromRedir`
- size: `305`
- prototype: `NTSTATUS __fastcall(PVOID OutputBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000abe0`

## callees

- `0x18000ad90`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000ae56`
- `ntdll!NtCreateFile` at `0x18000ae56`
- `ntdll!NtFsControlFile` at `0x18000ae98`
- `ntdll!NtFsControlFile` at `0x18000ae98`
- `ntdll!NtClose` at `0x18000aea8`
- `ntdll!NtClose` at `0x18000aea8`
- `ntdll!RtlInitUnicodeString` at `0x18000add1`
- `ntdll!RtlInitUnicodeString` at `0x18000add1`

## pseudocode

```c
NTSTATUS __fastcall GetStatisticsFromRedir(PVOID OutputBuffer)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // ebx
  struct _UNICODE_STRING v4; // [rsp+60h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-38h] BYREF
  void *FileHandle; // [rsp+C8h] [rbp+10h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v4 = 0;
  RtlInitUnicodeString(&v4, L"\\Device\\LanmanRedirector");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v4;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtCreateFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0x20u, 0, 0);
  if ( result >= 0 )
  {
    v3 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x1401D0u, 0, 0, OutputBuffer, 0xD8u);
    NtClose(FileHandle);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad90  mov     r11, rsp
0x18000ad93  mov     [r11+8], rbx
0x18000ad97  push    rdi
0x18000ad98  sub     rsp, 0B0h
0x18000ad9f  xorps   xmm0, xmm0
0x18000ada2  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x18000ada9  mov     rbx, rcx
0x18000adac  xor     edi, edi
0x18000adae  movups  xmmword ptr [r11-28h], xmm0
0x18000adb3  xor     eax, eax
0x18000adb5  mov     [r11+10h], rdi
0x18000adb9  lea     rcx, [r11-58h]; DestinationString
0x18000adbd  movups  xmmword ptr [r11-1Ch], xmm0
0x18000adc2  movups  xmmword ptr [rsp+0B8h+IoStatusBlock], xmm0
0x18000adc7  movups  xmmword ptr [r11-38h], xmm0
0x18000adcc  movups  [rsp+0B8h+var_58], xmm0
0x18000add1  call    cs:__imp_RtlInitUnicodeString
0x18000add7  mov     [rsp+0B8h+EaLength], edi; EaLength
0x18000addb  lea     rax, [rsp+0B8h+var_58]
0x18000ade0  mov     [rsp+0B8h+EaBuffer], rdi; EaBuffer
0x18000ade5  lea     r9, [rsp+0B8h+IoStatusBlock]; IoStatusBlock
0x18000adea  mov     [rsp+0B8h+CreateOptions], 20h ; ' '; CreateOptions
0x18000adf2  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x18000adfa  mov     [rsp+0B8h+CreateDisposition], 3; CreateDisposition
0x18000ae02  lea     rcx, [rsp+0B8h+FileHandle]; FileHandle
0x18000ae0a  mov     [rsp+0B8h+ShareAccess], 3; ShareAccess
0x18000ae12  xorps   xmm0, xmm0
0x18000ae15  mov     [rsp+0B8h+FileAttributes], 80h; FileAttributes
0x18000ae1d  mov     edx, 100000h; DesiredAccess
0x18000ae22  mov     [rsp+0B8h+AllocationSize], rdi; AllocationSize
0x18000ae27  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x18000ae32  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rdi
0x18000ae3a  mov     [rsp+0B8h+ObjectAttributes.Attributes], 40h ; '@'
0x18000ae45  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x18000ae4d  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ae56  call    cs:__imp_NtCreateFile
0x18000ae5c  test    eax, eax
0x18000ae5e  js      short loc_18000AEB0
0x18000ae60  mov     rcx, [rsp+0B8h+FileHandle]; FileHandle
0x18000ae68  lea     rax, [rsp+0B8h+IoStatusBlock]
0x18000ae6d  mov     dword ptr [rsp+0B8h+EaBuffer], 0D8h; OutputBufferLength
0x18000ae75  xor     r9d, r9d; ApcContext
0x18000ae78  mov     qword ptr [rsp+0B8h+CreateOptions], rbx; OutputBuffer
0x18000ae7d  xor     r8d, r8d; ApcRoutine
0x18000ae80  mov     [rsp+0B8h+CreateDisposition], edi; InputBufferLength
0x18000ae84  xor     edx, edx; Event
0x18000ae86  mov     qword ptr [rsp+0B8h+ShareAccess], rdi; InputBuffer
0x18000ae8b  mov     [rsp+0B8h+FileAttributes], 1401D0h; FsControlCode
0x18000ae93  mov     [rsp+0B8h+AllocationSize], rax; IoStatusBlock
0x18000ae98  call    cs:__imp_NtFsControlFile
0x18000ae9e  mov     rcx, [rsp+0B8h+FileHandle]; Handle
0x18000aea6  mov     ebx, eax
0x18000aea8  call    cs:__imp_NtClose
0x18000aeae  mov     eax, ebx
0x18000aeb0  mov     rbx, [rsp+0B8h+arg_0]
0x18000aeb8  add     rsp, 0B0h
0x18000aebf  pop     rdi
0x18000aec0  retn
```
