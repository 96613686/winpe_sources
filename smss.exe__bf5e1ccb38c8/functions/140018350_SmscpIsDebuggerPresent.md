# SmscpIsDebuggerPresent

- ea: `0x140018350`
- end: `0x1400183d9`
- name: `SmscpIsDebuggerPresent`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400069d0`

## callees

- `0x140018350`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1400183b3`
- `ntdll!NtOpenFile` at `0x1400183b3`
- `ntdll!NtClose` at `0x1400183c3`
- `ntdll!NtClose` at `0x1400183c3`

## pseudocode

```c
__int64 SmscpIsDebuggerPresent()
{
  NTSTATUS v0; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF

  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)L":<";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
  if ( v0 >= 0 )
    NtClose(FileHandle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140018350  mov     [rsp-8+arg_8], rbx
0x140018355  push    rbp
0x140018356  mov     rbp, rsp
0x140018359  sub     rsp, 70h
0x14001835d  xor     eax, eax
0x14001835f  mov     [rsp+70h+OpenOptions], 60h ; '`'; OpenOptions
0x140018367  xorps   xmm0, xmm0
0x14001836a  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14001836e  lea     rax, SmscpDebuggerString; ":<"
0x140018375  mov     [rbp+FileHandle], 0
0x14001837d  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140018381  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140018385  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140018389  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140018391  mov     edx, 120089h; DesiredAccess
0x140018396  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14001839e  lea     rcx, [rbp+FileHandle]; FileHandle
0x1400183a2  mov     [rsp+70h+ShareAccess], 5; ShareAccess
0x1400183aa  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400183ae  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400183b3  call    cs:__imp_NtOpenFile
0x1400183b9  mov     ebx, eax
0x1400183bb  test    eax, eax
0x1400183bd  js      short loc_1400183C9
0x1400183bf  mov     rcx, [rbp+FileHandle]; Handle
0x1400183c3  call    cs:__imp_NtClose
0x1400183c9  mov     eax, ebx
0x1400183cb  mov     rbx, [rsp+70h+arg_8]
0x1400183d3  add     rsp, 70h
0x1400183d7  pop     rbp
0x1400183d8  retn
```
