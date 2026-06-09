# WinNatRegOpenKey

- ea: `0x14002fad4`
- end: `0x14002fb86`
- name: `WinNatRegOpenKey`
- size: `178`
- prototype: `NTSTATUS __fastcall(__int64, void **, _BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000dda4`

## callees

- `0x14002fad4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002fb15`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002fb15`
- `ntoskrnl!ZwOpenKey` at `0x14002fb53`
- `ntoskrnl!ZwOpenKey` at `0x14002fb53`

## string_xrefs

- `0x14002faf7`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Winnat`

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
0x14002fad4  mov     [rsp-8+arg_0], rbx
0x14002fad9  mov     [rsp-8+arg_8], rdi
0x14002fade  push    rbp
0x14002fadf  mov     rbp, rsp
0x14002fae2  sub     rsp, 60h
0x14002fae6  xorps   xmm0, xmm0
0x14002fae9  mov     qword ptr [rdx], 0
0x14002faf0  mov     rbx, rdx
0x14002faf3  mov     byte ptr [r8], 0
0x14002faf7  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14002fafe  mov     rdi, r8
0x14002fb01  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002fb05  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14002fb09  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14002fb0d  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002fb11  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002fb15  call    cs:__imp_RtlInitUnicodeString
0x14002fb1c  nop     dword ptr [rax+rax+00h]
0x14002fb21  lea     rax, [rbp+DestinationString]
0x14002fb25  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002fb2c  xorps   xmm0, xmm0
0x14002fb2f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14002fb33  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002fb37  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002fb3f  mov     edx, 20019h; DesiredAccess
0x14002fb44  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14002fb4b  mov     rcx, rbx; KeyHandle
0x14002fb4e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002fb53  call    cs:__imp_ZwOpenKey
0x14002fb5a  nop     dword ptr [rax+rax+00h]
0x14002fb5f  mov     ecx, eax
0x14002fb61  test    eax, eax
0x14002fb63  jns     short loc_14002FB72
0x14002fb65  xor     eax, eax
0x14002fb67  cmp     ecx, 0C0000034h
0x14002fb6d  cmovnz  eax, ecx
0x14002fb70  jmp     short loc_14002FB75
0x14002fb72  mov     byte ptr [rdi], 1
0x14002fb75  mov     rbx, [rsp+60h+arg_0]
0x14002fb7a  mov     rdi, [rsp+60h+arg_8]
0x14002fb7f  add     rsp, 60h
0x14002fb83  pop     rbp
0x14002fb84  retn
```
