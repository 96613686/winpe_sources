# MyRegOpenKey

- ea: `0x1800035c0`
- end: `0x180003648`
- name: `MyRegOpenKey`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800028f4`
- `0x180002aec`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000362b`
- `ntdll!NtOpenKey` at `0x18000362b`
- `ntdll!RtlInitUnicodeString` at `0x1800035f1`
- `ntdll!RtlInitUnicodeString` at `0x1800035f1`

## pseudocode

```c
NTSTATUS __fastcall MyRegOpenKey(void *a1, const WCHAR *a2, void **a3)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtOpenKey(a3, 0x20019u, &ObjectAttributes);
}

```

## disassembly

```asm
0x1800035c0  mov     [rsp-8+arg_0], rbx
0x1800035c5  mov     [rsp-8+arg_8], rdi
0x1800035ca  push    rbp
0x1800035cb  mov     rbp, rsp
0x1800035ce  sub     rsp, 60h
0x1800035d2  xorps   xmm0, xmm0
0x1800035d5  mov     rbx, rcx
0x1800035d8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800035dc  xor     eax, eax
0x1800035de  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800035e2  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800035e6  mov     rdi, r8
0x1800035e9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800035ed  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800035f1  call    cs:__imp_RtlInitUnicodeString
0x1800035f8  nop     dword ptr [rax+rax+00h]
0x1800035fd  lea     rax, [rbp+DestinationString]
0x180003601  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180003608  xorps   xmm0, xmm0
0x18000360b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000360f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180003613  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x180003617  mov     edx, 20019h; DesiredAccess
0x18000361c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180003623  mov     rcx, rdi; KeyHandle
0x180003626  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000362b  call    cs:__imp_NtOpenKey
0x180003632  nop     dword ptr [rax+rax+00h]
0x180003637  mov     rbx, [rsp+60h+arg_0]
0x18000363c  mov     rdi, [rsp+60h+arg_8]
0x180003641  add     rsp, 60h
0x180003645  pop     rbp
0x180003646  retn
```
