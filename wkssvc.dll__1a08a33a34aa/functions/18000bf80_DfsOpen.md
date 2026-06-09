# DfsOpen

- ea: `0x18000bf80`
- end: `0x18000bfef`
- name: `DfsOpen`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002fc0c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000bfd6`
- `ntdll!NtOpenFile` at `0x18000bfd6`

## pseudocode

```c
int __fastcall DfsOpen(void **a1)
{
  int result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)LocalDfsName;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(a1, 0x100002u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( result >= 0 )
    return IoStatusBlock.Status;
  return result;
}

```

## disassembly

```asm
0x18000bf80  sub     rsp, 78h
0x18000bf84  xor     eax, eax
0x18000bf86  mov     [rsp+78h+OpenOptions], 20h ; ' '; OpenOptions
0x18000bf8e  xorps   xmm0, xmm0
0x18000bf91  mov     [rsp+78h+ObjectAttributes.RootDirectory], rax
0x18000bf96  lea     rax, LocalDfsName; "\"\""
0x18000bf9d  mov     qword ptr [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x18000bfa6  lea     r9, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x18000bfab  mov     [rsp+78h+ObjectAttributes.ObjectName], rax
0x18000bfb0  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x18000bfb5  mov     qword ptr [rsp+78h+ObjectAttributes.Attributes], 40h ; '@'
0x18000bfbe  mov     edx, 100002h; DesiredAccess
0x18000bfc3  mov     [rsp+78h+ShareAccess], 7; ShareAccess
0x18000bfcb  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x18000bfd0  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000bfd6  call    cs:__imp_NtOpenFile
0x18000bfdd  nop     dword ptr [rax+rax+00h]
0x18000bfe2  test    eax, eax
0x18000bfe4  cmovns  eax, dword ptr [rsp+78h+IoStatusBlock]
0x18000bfe9  add     rsp, 78h
0x18000bfed  retn
```
