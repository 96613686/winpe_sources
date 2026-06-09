# CreateOrOpenKey

- ea: `0x18000587c`
- end: `0x180005926`
- name: `CreateOrOpenKey`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006b7c`

## import_xrefs

- `ntdll!NtCreateKey` at `0x180005904`
- `ntdll!NtCreateKey` at `0x180005904`
- `ntdll!RtlInitUnicodeString` at `0x1800058b7`
- `ntdll!RtlInitUnicodeString` at `0x1800058b7`

## pseudocode

```c
NTSTATUS __fastcall CreateOrOpenKey(void *a1, __int64 a2, void **a3)
{
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtCreateKey(a3, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x18000587c  mov     [rsp-8+arg_0], rbx
0x180005881  mov     [rsp-8+arg_8], rdi
0x180005886  push    rbp
0x180005887  mov     rbp, rsp
0x18000588a  sub     rsp, 80h
0x180005891  xorps   xmm0, xmm0
0x180005894  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000589b  mov     rbx, rcx
0x18000589e  xor     eax, eax
0x1800058a0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800058a4  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800058a8  mov     rdi, r8
0x1800058ab  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800058af  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800058b3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800058b7  call    cs:__imp_RtlInitUnicodeString
0x1800058be  nop     dword ptr [rax+rax+00h]
0x1800058c3  lea     rax, [rbp+DestinationString]
0x1800058c7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800058ce  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800058d2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800058d6  xor     eax, eax
0x1800058d8  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x1800058dc  mov     [rsp+80h+Disposition], rax; Disposition
0x1800058e1  xorps   xmm0, xmm0
0x1800058e4  mov     [rsp+80h+CreateOptions], eax; CreateOptions
0x1800058e8  xor     r9d, r9d; TitleIndex
0x1800058eb  mov     edx, 20006h; DesiredAccess
0x1800058f0  mov     [rsp+80h+Class], rax; Class
0x1800058f5  mov     rcx, rdi; KeyHandle
0x1800058f8  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800058ff  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180005904  call    cs:__imp_NtCreateKey
0x18000590b  nop     dword ptr [rax+rax+00h]
0x180005910  lea     r11, [rsp+80h+var_s0]
0x180005918  mov     rbx, [r11+10h]
0x18000591c  mov     rdi, [r11+18h]
0x180005920  mov     rsp, r11
0x180005923  pop     rbp
0x180005924  retn
```
