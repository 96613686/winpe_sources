# GetStatisticsFromRedir

- ea: `0x18000b710`
- end: `0x18000b85a`
- name: `GetStatisticsFromRedir`
- size: `330`
- prototype: `__int64 __fastcall(PVOID OutputBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b520`

## callees

- `0x18000b710`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000b7dc`
- `ntdll!NtCreateFile` at `0x18000b7dc`
- `ntdll!NtFsControlFile` at `0x18000b824`
- `ntdll!NtFsControlFile` at `0x18000b824`
- `ntdll!NtClose` at `0x18000b83a`
- `ntdll!NtClose` at `0x18000b83a`
- `ntdll!RtlInitUnicodeString` at `0x18000b751`
- `ntdll!RtlInitUnicodeString` at `0x18000b751`

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
0x18000b710  mov     r11, rsp
0x18000b713  mov     [r11+8], rbx
0x18000b717  push    rdi
0x18000b718  sub     rsp, 0B0h
0x18000b71f  xorps   xmm0, xmm0
0x18000b722  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x18000b729  mov     rbx, rcx
0x18000b72c  xor     edi, edi
0x18000b72e  movups  xmmword ptr [r11-28h], xmm0
0x18000b733  xor     eax, eax
0x18000b735  mov     [r11+10h], rdi
0x18000b739  lea     rcx, [r11-58h]; DestinationString
0x18000b73d  movups  xmmword ptr [r11-1Ch], xmm0
0x18000b742  movups  xmmword ptr [rsp+0B8h+IoStatusBlock], xmm0
0x18000b747  movups  xmmword ptr [r11-38h], xmm0
0x18000b74c  movups  [rsp+0B8h+var_58], xmm0
0x18000b751  call    cs:__imp_RtlInitUnicodeString
0x18000b758  nop     dword ptr [rax+rax+00h]
0x18000b75d  mov     [rsp+0B8h+EaLength], edi; EaLength
0x18000b761  lea     rax, [rsp+0B8h+var_58]
0x18000b766  mov     [rsp+0B8h+EaBuffer], rdi; EaBuffer
0x18000b76b  lea     r9, [rsp+0B8h+IoStatusBlock]; IoStatusBlock
0x18000b770  mov     [rsp+0B8h+CreateOptions], 20h ; ' '; CreateOptions
0x18000b778  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x18000b780  mov     [rsp+0B8h+CreateDisposition], 3; CreateDisposition
0x18000b788  lea     rcx, [rsp+0B8h+FileHandle]; FileHandle
0x18000b790  mov     [rsp+0B8h+ShareAccess], 3; ShareAccess
0x18000b798  xorps   xmm0, xmm0
0x18000b79b  mov     [rsp+0B8h+FileAttributes], 80h; FileAttributes
0x18000b7a3  mov     edx, 100000h; DesiredAccess
0x18000b7a8  mov     [rsp+0B8h+AllocationSize], rdi; AllocationSize
0x18000b7ad  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x18000b7b8  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rdi
0x18000b7c0  mov     [rsp+0B8h+ObjectAttributes.Attributes], 40h ; '@'
0x18000b7cb  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x18000b7d3  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b7dc  call    cs:__imp_NtCreateFile
0x18000b7e3  nop     dword ptr [rax+rax+00h]
0x18000b7e8  test    eax, eax
0x18000b7ea  js      short loc_18000B848
0x18000b7ec  mov     rcx, [rsp+0B8h+FileHandle]; FileHandle
0x18000b7f4  lea     rax, [rsp+0B8h+IoStatusBlock]
0x18000b7f9  mov     dword ptr [rsp+0B8h+EaBuffer], 0D8h; OutputBufferLength
0x18000b801  xor     r9d, r9d; ApcContext
0x18000b804  mov     qword ptr [rsp+0B8h+CreateOptions], rbx; OutputBuffer
0x18000b809  xor     r8d, r8d; ApcRoutine
0x18000b80c  mov     [rsp+0B8h+CreateDisposition], edi; InputBufferLength
0x18000b810  xor     edx, edx; Event
0x18000b812  mov     qword ptr [rsp+0B8h+ShareAccess], rdi; InputBuffer
0x18000b817  mov     [rsp+0B8h+FileAttributes], 1401D0h; FsControlCode
0x18000b81f  mov     [rsp+0B8h+AllocationSize], rax; IoStatusBlock
0x18000b824  call    cs:__imp_NtFsControlFile
0x18000b82b  nop     dword ptr [rax+rax+00h]
0x18000b830  mov     rcx, [rsp+0B8h+FileHandle]; Handle
0x18000b838  mov     ebx, eax
0x18000b83a  call    cs:__imp_NtClose
0x18000b841  nop     dword ptr [rax+rax+00h]
0x18000b846  mov     eax, ebx
0x18000b848  mov     rbx, [rsp+0B8h+arg_0]
0x18000b850  add     rsp, 0B0h
0x18000b857  pop     rdi
0x18000b858  retn
```
