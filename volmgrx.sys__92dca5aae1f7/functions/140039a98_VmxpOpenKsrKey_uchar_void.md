# VmxpOpenKsrKey(uchar,void * *)

- ea: `0x140039a98`
- end: `0x140039b1f`
- name: `?VmxpOpenKsrKey@@YAJEPEAPEAX@Z`
- size: `135`
- prototype: `int(unsigned __int8, void **)`
- caller_count: `3`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400094ac`
- `0x14003ca48`
- `0x140046648`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140039ac9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140039ac9`
- `ntoskrnl!ZwOpenKey` at `0x140039b07`
- `ntoskrnl!ZwOpenKey` at `0x140039b07`

## string_xrefs

- `0x140039ab2`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX\KSR`

## pseudocode

```c
NTSTATUS __fastcall VmxpOpenKsrKey(__int64 a1, void **a2)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\VolMgrX\\KSR");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenKey(a2, 0xF003Fu, &ObjectAttributes);
}

```

## disassembly

```asm
0x140039a98  mov     [rsp-8+arg_0], rbx
0x140039a9d  push    rbp
0x140039a9e  mov     rbp, rsp
0x140039aa1  sub     rsp, 60h
0x140039aa5  xorps   xmm1, xmm1
0x140039aa8  lea     rcx, [rbp+DestinationString]; DestinationString
0x140039aac  mov     rbx, rdx
0x140039aaf  xorps   xmm0, xmm0
0x140039ab2  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140039ab9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140039abd  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x140039ac1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x140039ac5  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x140039ac9  call    cs:__imp_RtlInitUnicodeString
0x140039ad0  nop     dword ptr [rax+rax+00h]
0x140039ad5  lea     rax, [rbp+DestinationString]
0x140039ad9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140039ae0  xorps   xmm0, xmm0
0x140039ae3  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140039ae7  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140039aeb  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140039af3  mov     edx, 0F003Fh; DesiredAccess
0x140039af8  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140039aff  mov     rcx, rbx; KeyHandle
0x140039b02  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140039b07  call    cs:__imp_ZwOpenKey
0x140039b0e  nop     dword ptr [rax+rax+00h]
0x140039b13  mov     rbx, [rsp+60h+arg_0]
0x140039b18  add     rsp, 60h
0x140039b1c  pop     rbp
0x140039b1d  retn
```
