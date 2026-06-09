# WinNatRegOpenKey

- ea: `0x14002ead4`
- end: `0x14002eb86`
- name: `WinNatRegOpenKey`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000ddd4`

## callees

- `0x14002ead4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002eb15`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002eb15`
- `ntoskrnl!ZwOpenKey` at `0x14002eb53`
- `ntoskrnl!ZwOpenKey` at `0x14002eb53`

## string_xrefs

- `0x14002eaf7`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Winnat`

## pseudocode

```c
NTSTATUS __fastcall WinNatRegOpenKey(__int64 a1, void **a2, _BYTE *a3)
{
  NTSTATUS result; // eax
  NTSTATUS v6; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  *a2 = 0;
  *a3 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\Winnat");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(a2, 0x20019u, &ObjectAttributes);
  v6 = result;
  if ( result >= 0 )
  {
    *a3 = 1;
  }
  else
  {
    result = 0;
    if ( v6 != -1073741772 )
      return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14002ead4  mov     [rsp-8+arg_0], rbx
0x14002ead9  mov     [rsp-8+arg_8], rdi
0x14002eade  push    rbp
0x14002eadf  mov     rbp, rsp
0x14002eae2  sub     rsp, 60h
0x14002eae6  xorps   xmm0, xmm0
0x14002eae9  mov     qword ptr [rdx], 0
0x14002eaf0  mov     rbx, rdx
0x14002eaf3  mov     byte ptr [r8], 0
0x14002eaf7  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14002eafe  mov     rdi, r8
0x14002eb01  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002eb05  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14002eb09  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14002eb0d  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002eb11  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002eb15  call    cs:__imp_RtlInitUnicodeString
0x14002eb1c  nop     dword ptr [rax+rax+00h]
0x14002eb21  lea     rax, [rbp+DestinationString]
0x14002eb25  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002eb2c  xorps   xmm0, xmm0
0x14002eb2f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14002eb33  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002eb37  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002eb3f  mov     edx, 20019h; DesiredAccess
0x14002eb44  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14002eb4b  mov     rcx, rbx; KeyHandle
0x14002eb4e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002eb53  call    cs:__imp_ZwOpenKey
0x14002eb5a  nop     dword ptr [rax+rax+00h]
0x14002eb5f  mov     ecx, eax
0x14002eb61  test    eax, eax
0x14002eb63  jns     short loc_14002EB72
0x14002eb65  xor     eax, eax
0x14002eb67  cmp     ecx, 0C0000034h
0x14002eb6d  cmovnz  eax, ecx
0x14002eb70  jmp     short loc_14002EB75
0x14002eb72  mov     byte ptr [rdi], 1
0x14002eb75  mov     rbx, [rsp+60h+arg_0]
0x14002eb7a  mov     rdi, [rsp+60h+arg_8]
0x14002eb7f  add     rsp, 60h
0x14002eb83  pop     rbp
0x14002eb84  retn
```
