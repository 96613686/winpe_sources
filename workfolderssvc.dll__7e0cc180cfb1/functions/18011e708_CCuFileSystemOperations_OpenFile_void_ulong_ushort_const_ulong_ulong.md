# CCuFileSystemOperations::OpenFile(void * *,ulong,ushort const *,ulong,ulong)

- ea: `0x18011e708`
- end: `0x18011e7b8`
- name: `?OpenFile@CCuFileSystemOperations@@SAJPEAPEAXKPEBGKK@Z`
- size: `176`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, ACCESS_MASK DesiredAccess, PCWSTR SourceString, ULONG ShareAccess, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801156d8`
- `0x1801163e0`
- `0x18011a590`
- `0x18011d984`
- `0x18011dce4`
- `0x18012283c`
- `0x180123ad8`

## callees

- `0x18011e708`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18011e79f`
- `ntdll!NtOpenFile` at `0x18011e79f`
- `ntdll!RtlInitUnicodeStringEx` at `0x18011e753`
- `ntdll!RtlInitUnicodeStringEx` at `0x18011e753`

## pseudocode

```c
int __fastcall CCuFileSystemOperations::OpenFile(
        PHANDLE FileHandle,
        ACCESS_MASK DesiredAccess,
        PCWSTR SourceString,
        ULONG ShareAccess,
        unsigned int a5)
{
  int result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-1h] BYREF

  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !FileHandle )
    return -1073741811;
  *FileHandle = 0;
  if ( !SourceString )
    return -1073741811;
  result = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( result >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return NtOpenFile(FileHandle, DesiredAccess, &ObjectAttributes, &IoStatusBlock, ShareAccess, a5 | 0x200000);
  }
  return result;
}

```

## disassembly

```asm
0x18011e708  push    rbp
0x18011e70a  push    rbx
0x18011e70b  push    rsi
0x18011e70c  push    rdi
0x18011e70d  lea     rbp, [rsp-37h]
0x18011e712  sub     rsp, 88h
0x18011e719  xorps   xmm0, xmm0
0x18011e71c  xorps   xmm1, xmm1
0x18011e71f  mov     edi, r9d
0x18011e722  mov     esi, edx
0x18011e724  mov     rbx, rcx
0x18011e727  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18011e72b  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm1
0x18011e72f  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18011e733  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18011e737  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18011e73b  test    rcx, rcx
0x18011e73e  jz      short loc_18011E7A7
0x18011e740  mov     qword ptr [rcx], 0
0x18011e747  test    r8, r8
0x18011e74a  jz      short loc_18011E7A7
0x18011e74c  mov     rdx, r8; SourceString
0x18011e74f  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18011e753  call    cs:__imp_RtlInitUnicodeStringEx
0x18011e759  test    eax, eax
0x18011e75b  js      short loc_18011E7AC
0x18011e75d  lea     rax, [rbp+4Fh+DestinationString]
0x18011e761  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18011e768  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18011e76c  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18011e770  mov     eax, [rbp+4Fh+arg_20]
0x18011e773  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18011e777  bts     eax, 15h
0x18011e77b  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x18011e783  xorps   xmm0, xmm0
0x18011e786  mov     [rsp+0A0h+OpenOptions], eax; OpenOptions
0x18011e78a  mov     edx, esi; DesiredAccess
0x18011e78c  mov     [rsp+0A0h+ShareAccess], edi; ShareAccess
0x18011e790  mov     rcx, rbx; FileHandle
0x18011e793  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18011e79a  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18011e79f  call    cs:__imp_NtOpenFile
0x18011e7a5  jmp     short loc_18011E7AC
0x18011e7a7  mov     eax, 0C000000Dh
0x18011e7ac  add     rsp, 88h
0x18011e7b3  pop     rdi
0x18011e7b4  pop     rsi
0x18011e7b5  pop     rbx
0x18011e7b6  pop     rbp
0x18011e7b7  retn
```
