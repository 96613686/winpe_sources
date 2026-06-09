# SmpQueryFileExists

- ea: `0x140012078`
- end: `0x1400120f0`
- name: `SmpQueryFileExists`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011ac4`
- `0x140011d24`

## callees

- `0x140012078`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1400120d0`
- `ntdll!NtOpenFile` at `0x1400120d0`
- `ntdll!NtClose` at `0x1400120e2`
- `ntdll!NtClose` at `0x1400120e2`

## pseudocode

```c
char __fastcall SmpQueryFileExists(struct _UNICODE_STRING *a1)
{
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF

  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u) < 0 )
    return 0;
  NtClose(FileHandle);
  return 1;
}

```

## disassembly

```asm
0x140012078  push    rbp
0x14001207a  mov     rbp, rsp
0x14001207d  sub     rsp, 70h
0x140012081  xorps   xmm0, xmm0
0x140012084  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140012088  xor     eax, eax
0x14001208a  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x140012092  lea     rcx, [rbp+FileHandle]; FileHandle
0x140012096  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14001209a  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14001209e  mov     [rbp+FileHandle], 0
0x1400120a6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400120aa  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400120b2  mov     edx, 100080h; DesiredAccess
0x1400120b7  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1400120bf  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400120c3  mov     [rsp+70h+ShareAccess], 3; ShareAccess
0x1400120cb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400120d0  call    cs:__imp_NtOpenFile
0x1400120d6  test    eax, eax
0x1400120d8  jns     short loc_1400120DE
0x1400120da  xor     al, al
0x1400120dc  jmp     short loc_1400120EA
0x1400120de  mov     rcx, [rbp+FileHandle]; Handle
0x1400120e2  call    cs:__imp_NtClose
0x1400120e8  mov     al, 1
0x1400120ea  add     rsp, 70h
0x1400120ee  pop     rbp
0x1400120ef  retn
```
