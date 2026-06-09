# WerpDeleteDumpFile

- ea: `0x14000ee80`
- end: `0x14000ef9e`
- name: `WerpDeleteDumpFile`
- size: `286`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000c570`

## callees

- `0x14000ee80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000eecf`
- `ntoskrnl!DbgPrintEx` at `0x14000eecf`
- `ntoskrnl!ZwClose` at `0x14000ef79`
- `ntoskrnl!ZwClose` at `0x14000ef79`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000eee7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000eee7`
- `ntoskrnl!IoCreateFile` at `0x14000ef65`
- `ntoskrnl!IoCreateFile` at `0x14000ef65`

## string_xrefs

- `0x14000eec2`: `WERKERNELHOST: WerpDeleteDumpFile No dump file to delete. \n`

## pseudocode

```c
NTSTATUS __fastcall WerpDeleteDumpFile(__int64 a1)
{
  _WORD *v1; // rbx
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+67h] BYREF

  v1 = (_WORD *)(a1 + 136);
  FileHandle = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !*(_WORD *)(a1 + 136) )
    return DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpDeleteDumpFile No dump file to delete. \n");
  RtlInitUnicodeString(&DestinationString, (PCWSTR)(a1 + 136));
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = IoCreateFile(
             &FileHandle,
             0x110000u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0x80u,
             7u,
             1u,
             0x1000u,
             0,
             0,
             CreateFileTypeNone,
             0,
             0x100u);
  if ( result >= 0 )
  {
    result = ZwClose(FileHandle);
    *v1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000ee80  mov     [rsp-8+arg_8], rbx
0x14000ee85  mov     [rsp-8+arg_10], rdi
0x14000ee8a  push    rbp
0x14000ee8b  lea     rbp, [rsp-57h]
0x14000ee90  sub     rsp, 0C0h
0x14000ee97  xorps   xmm0, xmm0
0x14000ee9a  lea     rbx, [rcx+88h]
0x14000eea1  xor     edi, edi
0x14000eea3  xor     eax, eax
0x14000eea5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000eea9  mov     [rbp+57h+FileHandle], rdi
0x14000eead  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000eeb1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000eeb5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000eeb9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000eebd  cmp     [rbx], di
0x14000eec0  jnz     short loc_14000EEE0
0x14000eec2  lea     r8, aWerkernelhostW_20; "WERKERNELHOST: WerpDeleteDumpFile No du"...
0x14000eec9  lea     edx, [rdi+1]; Level
0x14000eecc  lea     ecx, [rdi+5]; ComponentId
0x14000eecf  call    cs:__imp_DbgPrintEx
0x14000eed6  nop     dword ptr [rax+rax+00h]
0x14000eedb  jmp     loc_14000EF88
0x14000eee0  mov     rdx, rbx; SourceString
0x14000eee3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000eee7  call    cs:__imp_RtlInitUnicodeString
0x14000eeee  nop     dword ptr [rax+rax+00h]
0x14000eef3  mov     [rsp+0C0h+Options], 100h; Options
0x14000eefb  lea     rax, [rbp+57h+DestinationString]
0x14000eeff  mov     [rsp+0C0h+InternalParameters], rdi; InternalParameters
0x14000ef04  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000ef08  mov     [rsp+0C0h+CreateFileType], edi; CreateFileType
0x14000ef0c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000ef10  mov     [rsp+0C0h+EaLength], edi; EaLength
0x14000ef14  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000ef18  mov     [rsp+0C0h+EaBuffer], rdi; EaBuffer
0x14000ef1d  xorps   xmm0, xmm0
0x14000ef20  mov     [rsp+0C0h+CreateOptions], 1000h; CreateOptions
0x14000ef28  mov     edx, 110000h; DesiredAccess
0x14000ef2d  mov     [rsp+0C0h+Disposition], 1; Disposition
0x14000ef35  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x14000ef3d  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x14000ef45  mov     [rsp+0C0h+AllocationSize], rdi; AllocationSize
0x14000ef4a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000ef51  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x14000ef55  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000ef5c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000ef60  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000ef65  call    cs:__imp_IoCreateFile
0x14000ef6c  nop     dword ptr [rax+rax+00h]
0x14000ef71  test    eax, eax
0x14000ef73  js      short loc_14000EF88
0x14000ef75  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000ef79  call    cs:__imp_ZwClose
0x14000ef80  nop     dword ptr [rax+rax+00h]
0x14000ef85  mov     [rbx], di
0x14000ef88  lea     r11, [rsp+0C0h+var_s0]
0x14000ef90  mov     rbx, [r11+18h]
0x14000ef94  mov     rdi, [r11+20h]
0x14000ef98  mov     rsp, r11
0x14000ef9b  pop     rbp
0x14000ef9c  retn
```
