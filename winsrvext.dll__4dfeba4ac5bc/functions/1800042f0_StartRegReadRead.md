# StartRegReadRead

- ea: `0x1800042f0`
- end: `0x18000437b`
- name: `StartRegReadRead`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003650`

## callees

- `0x180003c40`
- `0x1800042f0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000435b`
- `ntdll!NtOpenKey` at `0x18000435b`
- `ntdll!RtlInitUnicodeString` at `0x180004319`
- `ntdll!RtlInitUnicodeString` at `0x180004319`

## string_xrefs

- `0x1800042fc`: `\Registry\Machine\System\CurrentControlSet\Control\PriorityControl`

## pseudocode

```c
void StartRegReadRead()
{
  __int64 v0; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\PriorityControl");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&hKeyPriority, 0x20019u, &ObjectAttributes) >= 0 )
    RegReadApcProcedure(0, 0, v0);
}

```

## disassembly

```asm
0x1800042f0  push    rbp
0x1800042f2  mov     rbp, rsp
0x1800042f5  sub     rsp, 60h
0x1800042f9  xorps   xmm0, xmm0
0x1800042fc  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x180004303  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180004307  xor     eax, eax
0x180004309  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000430d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180004311  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180004315  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180004319  call    cs:__imp_RtlInitUnicodeString
0x180004320  nop     dword ptr [rax+rax+00h]
0x180004325  lea     rax, [rbp+DestinationString]
0x180004329  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180004330  xorps   xmm0, xmm0
0x180004333  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180004337  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000433b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180004343  mov     edx, 20019h; DesiredAccess
0x180004348  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000434f  lea     rcx, hKeyPriority; KeyHandle
0x180004356  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000435b  call    cs:__imp_NtOpenKey
0x180004362  nop     dword ptr [rax+rax+00h]
0x180004367  test    eax, eax
0x180004369  js      short loc_180004374
0x18000436b  xor     edx, edx; IoStatusBlock
0x18000436d  xor     ecx, ecx; ApcContext
0x18000436f  call    RegReadApcProcedure
0x180004374  add     rsp, 60h
0x180004378  pop     rbp
0x180004379  retn
```
