# SmpReadSafeBootOption

- ea: `0x14000e904`
- end: `0x14000e9ec`
- name: `SmpReadSafeBootOption`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x14000e904`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x14000e9b6`
- `ntdll!NtClose` at `0x14000e9b6`
- `ntdll!NtOpenKey` at `0x14000e974`
- `ntdll!NtOpenKey` at `0x14000e974`
- `ntdll!NtQueryValueKey` at `0x14000e9a9`
- `ntdll!NtQueryValueKey` at `0x14000e9a9`

## pseudocode

```c
__int64 SmpReadSafeBootOption()
{
  NTSTATUS v0; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+70h] [rbp-90h] BYREF
  int v6; // [rsp+7Ch] [rbp-84h]

  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&SmpSafebootOptionKey;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  if ( v0 >= 0 )
  {
    v0 = NtQueryValueKey(
           KeyHandle,
           (PUNICODE_STRING)&SmpSafebootOptionValue,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x200u,
           &ResultLength);
    NtClose(KeyHandle);
    if ( v0 >= 0 )
      SmpSafeBootOption = v6;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000e904  mov     [rsp-8+arg_0], rbx
0x14000e909  push    rbp
0x14000e90a  lea     rbp, [rsp-180h]
0x14000e912  sub     rsp, 280h
0x14000e919  mov     rax, cs:__security_cookie
0x14000e920  xor     rax, rsp
0x14000e923  mov     [rbp+180h+var_10], rax
0x14000e92a  xor     eax, eax
0x14000e92c  mov     [rsp+280h+KeyHandle], 0
0x14000e935  mov     [rsp+280h+var_250], eax
0x14000e939  lea     r8, [rsp+280h+ObjectAttributes]; ObjectAttributes
0x14000e93e  mov     [rsp+280h+ObjectAttributes.RootDirectory], rax
0x14000e943  lea     rcx, [rsp+280h+KeyHandle]; KeyHandle
0x14000e948  lea     rax, SmpSafebootOptionKey
0x14000e94f  mov     qword ptr [rsp+280h+ObjectAttributes.Length], 30h ; '0'
0x14000e958  xorps   xmm0, xmm0
0x14000e95b  mov     [rsp+280h+ObjectAttributes.ObjectName], rax
0x14000e960  mov     edx, 0F003Fh; DesiredAccess
0x14000e965  mov     qword ptr [rsp+280h+ObjectAttributes.Attributes], 40h ; '@'
0x14000e96e  movdqu  xmmword ptr [rsp+280h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e974  call    cs:__imp_NtOpenKey
0x14000e97a  mov     ebx, eax
0x14000e97c  test    eax, eax
0x14000e97e  js      short loc_14000E9CA
0x14000e980  mov     rcx, [rsp+280h+KeyHandle]; KeyHandle
0x14000e985  lea     rax, [rsp+280h+var_250]
0x14000e98a  mov     [rsp+280h+ResultLength], rax; ResultLength
0x14000e98f  lea     r9, [rsp+280h+KeyValueInformation]; KeyValueInformation
0x14000e994  mov     r8d, 2; KeyValueInformationClass
0x14000e99a  mov     [rsp+280h+Length], 200h; Length
0x14000e9a2  lea     rdx, SmpSafebootOptionValue; ValueName
0x14000e9a9  call    cs:__imp_NtQueryValueKey
0x14000e9af  mov     rcx, [rsp+280h+KeyHandle]; Handle
0x14000e9b4  mov     ebx, eax
0x14000e9b6  call    cs:__imp_NtClose
0x14000e9bc  test    ebx, ebx
0x14000e9be  js      short loc_14000E9CA
0x14000e9c0  mov     eax, [rsp+280h+var_204]
0x14000e9c4  mov     cs:SmpSafeBootOption, eax
0x14000e9ca  mov     eax, ebx
0x14000e9cc  mov     rcx, [rbp+180h+var_10]
0x14000e9d3  xor     rcx, rsp; StackCookie
0x14000e9d6  call    __security_check_cookie
0x14000e9db  mov     rbx, [rsp+280h+arg_0]
0x14000e9e3  add     rsp, 280h
0x14000e9ea  pop     rbp
0x14000e9eb  retn
```
