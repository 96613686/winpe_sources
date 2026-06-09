# OpenKsecdd(void)

- ea: `0x180014874`
- end: `0x1800148ff`
- name: `?OpenKsecdd@@YAHXZ`
- size: `139`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000cb04`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800148eb`
- `ntdll!NtOpenFile` at `0x1800148eb`
- `ntdll!RtlInitUnicodeString` at `0x1800148a5`
- `ntdll!RtlInitUnicodeString` at `0x1800148a5`

## pseudocode

```c
_BOOL8 OpenKsecdd(void)
{
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  IoStatusBlock = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\Device\\KsecDD");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtOpenFile(&KsecddHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0) >= 0;
}

```

## disassembly

```asm
0x180014874  push    rbp
0x180014876  mov     rbp, rsp
0x180014879  sub     rsp, 80h
0x180014880  xorps   xmm0, xmm0
0x180014883  lea     rdx, aDeviceKsecdd; "\\Device\\KsecDD"
0x18001488a  xorps   xmm1, xmm1
0x18001488d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180014891  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180014895  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180014899  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18001489d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800148a1  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800148a5  call    cs:__imp_RtlInitUnicodeString
0x1800148ab  xor     ecx, ecx
0x1800148ad  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800148b4  mov     [rsp+80h+OpenOptions], ecx; OpenOptions
0x1800148b8  lea     rax, [rbp+DestinationString]
0x1800148bc  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1800148c0  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800148c4  mov     [rbp+ObjectAttributes.Attributes], ecx
0x1800148c7  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800148cb  xorps   xmm0, xmm0
0x1800148ce  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800148d2  lea     rcx, KsecddHandle; FileHandle
0x1800148d9  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x1800148e1  mov     edx, 0C0000000h; DesiredAccess
0x1800148e6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800148eb  call    cs:__imp_NtOpenFile
0x1800148f1  not     eax
0x1800148f3  shr     eax, 1Fh
0x1800148f6  add     rsp, 80h
0x1800148fd  pop     rbp
0x1800148fe  retn
```
