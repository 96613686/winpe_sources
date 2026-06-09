# SsOpenDeviceEx

- ea: `0x180013924`
- end: `0x1800139f7`
- name: `SsOpenDeviceEx`
- size: `211`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ea20`

## callees

- `0x18000ae90`
- `0x180013924`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800139af`
- `ntdll!NtOpenFile` at `0x1800139af`
- `ntdll!RtlInitUnicodeString` at `0x18001395c`
- `ntdll!RtlInitUnicodeString` at `0x18001395c`
- `ntdll!NtClose` at `0x1800139ce`
- `ntdll!NtClose` at `0x1800139ce`

## pseudocode

```c
__int64 __fastcall SsOpenDeviceEx(PCWSTR SourceString, __int64 a2, void **a3)
{
  int Status; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *a3 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = NtOpenFile(a3, 0xF01FFu, &ObjectAttributes, &IoStatusBlock, 0, 0);
  if ( Status >= 0 )
  {
    Status = IoStatusBlock.Status;
    if ( IoStatusBlock.Status >= 0 )
      return 0;
  }
  if ( *a3 )
  {
    NtClose(*a3);
    *a3 = 0;
  }
  return NetpNtStatusToApiStatus(Status);
}

```

## disassembly

```asm
0x180013924  mov     [rsp-8+arg_0], rbx
0x180013929  mov     [rsp-8+arg_8], rdi
0x18001392e  push    rbp
0x18001392f  mov     rbp, rsp
0x180013932  sub     rsp, 80h
0x180013939  xorps   xmm0, xmm0
0x18001393c  mov     rdx, rcx; SourceString
0x18001393f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180013943  xor     eax, eax
0x180013945  lea     rcx, [rbp+DestinationString]; DestinationString
0x180013949  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18001394d  mov     rdi, r8
0x180013950  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180013954  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180013958  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18001395c  call    cs:__imp_RtlInitUnicodeString
0x180013962  lea     rax, [rbp+DestinationString]
0x180013966  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x18001396e  xorps   xmm0, xmm0
0x180013971  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180013975  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180013979  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180013980  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180013984  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001398c  mov     edx, 0F01FFh; DesiredAccess
0x180013991  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180013998  mov     rcx, rdi; FileHandle
0x18001399b  mov     qword ptr [rdi], 0
0x1800139a2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800139a7  mov     [rsp+80h+ShareAccess], 0; ShareAccess
0x1800139af  call    cs:__imp_NtOpenFile
0x1800139b5  mov     ebx, eax
0x1800139b7  test    eax, eax
0x1800139b9  js      short loc_1800139C6
0x1800139bb  mov     ebx, dword ptr [rbp+IoStatusBlock]
0x1800139be  test    ebx, ebx
0x1800139c0  js      short loc_1800139C6
0x1800139c2  xor     eax, eax
0x1800139c4  jmp     short loc_1800139E2
0x1800139c6  mov     rcx, [rdi]; Handle
0x1800139c9  test    rcx, rcx
0x1800139cc  jz      short loc_1800139DB
0x1800139ce  call    cs:__imp_NtClose
0x1800139d4  mov     qword ptr [rdi], 0
0x1800139db  mov     ecx, ebx; Status
0x1800139dd  call    NetpNtStatusToApiStatus
0x1800139e2  lea     r11, [rsp+80h+var_s0]
0x1800139ea  mov     rbx, [r11+10h]
0x1800139ee  mov     rdi, [r11+18h]
0x1800139f2  mov     rsp, r11
0x1800139f5  pop     rbp
0x1800139f6  retn
```
