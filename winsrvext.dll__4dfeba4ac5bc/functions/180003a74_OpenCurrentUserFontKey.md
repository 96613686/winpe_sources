# OpenCurrentUserFontKey

- ea: `0x180003a74`
- end: `0x180003bb2`
- name: `OpenCurrentUserFontKey`
- size: `318`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004160`

## callees

- `0x180003a74`
- `0x1800138f0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180003b83`
- `ntdll!RtlFreeUnicodeString` at `0x180003b83`
- `ntdll!RtlAppendUnicodeToString` at `0x180003b05`
- `ntdll!RtlAppendUnicodeToString` at `0x180003b05`
- `ntdll!RtlCopyUnicodeString` at `0x180003aed`
- `ntdll!RtlCopyUnicodeString` at `0x180003aed`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180003aa7`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180003aa7`
- `ntdll!NtCreateKey` at `0x180003b70`
- `ntdll!NtCreateKey` at `0x180003b70`

## pseudocode

```c
__int64 OpenCurrentUserFontKey()
{
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  char v5; // [rsp+90h] [rbp-70h] BYREF

  KeyPath = 0;
  appended = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( appended >= 0 )
  {
    *(_QWORD *)&DestinationString.Length = 34078720;
    DestinationString.Buffer = (PWSTR)&v5;
    memset(&ObjectAttributes, 0, 44);
    RtlCopyUnicodeString(&DestinationString, &KeyPath);
    appended = RtlAppendUnicodeToString(&DestinationString, L"\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Fonts");
    if ( appended >= 0 )
    {
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ObjectAttributes.Attributes = 64;
      appended = NtCreateKey(&ghFontRegistryHKCU, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
    }
    RtlFreeUnicodeString(&KeyPath);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180003a74  mov     [rsp-8+arg_0], rbx
0x180003a79  push    rbp
0x180003a7a  lea     rbp, [rsp-1B0h]
0x180003a82  sub     rsp, 2B0h
0x180003a89  mov     rax, cs:__security_cookie
0x180003a90  xor     rax, rsp
0x180003a93  mov     [rbp+1B0h+var_10], rax
0x180003a9a  xorps   xmm0, xmm0
0x180003a9d  lea     rcx, [rsp+2B0h+KeyPath]; KeyPath
0x180003aa2  movups  xmmword ptr [rsp+2B0h+KeyPath.Length], xmm0
0x180003aa7  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180003aae  nop     dword ptr [rax+rax+00h]
0x180003ab3  mov     ebx, eax
0x180003ab5  test    eax, eax
0x180003ab7  js      loc_180003B8F
0x180003abd  xorps   xmm0, xmm0
0x180003ac0  mov     qword ptr [rsp+2B0h+DestinationString.Length], 2080000h
0x180003ac9  xor     eax, eax
0x180003acb  lea     rdx, [rsp+2B0h+KeyPath]; SourceString
0x180003ad0  lea     rax, [rbp+1B0h+var_220]
0x180003ad4  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm0
0x180003ad9  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x180003ade  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x180003ae3  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm0
0x180003ae8  movups  xmmword ptr [rsp+2B0h+ObjectAttributes+1Ch], xmm0
0x180003aed  call    cs:__imp_RtlCopyUnicodeString
0x180003af4  nop     dword ptr [rax+rax+00h]
0x180003af9  lea     rdx, Source; "\\SOFTWARE\\Microsoft\\Windows NT\\Curr"...
0x180003b00  lea     rcx, [rsp+2B0h+DestinationString]; Destination
0x180003b05  call    cs:__imp_RtlAppendUnicodeToString
0x180003b0c  nop     dword ptr [rax+rax+00h]
0x180003b11  mov     ebx, eax
0x180003b13  test    eax, eax
0x180003b15  js      short loc_180003B7E
0x180003b17  lea     rax, [rsp+2B0h+DestinationString]
0x180003b1c  mov     [rsp+2B0h+Disposition], 0; Disposition
0x180003b25  xorps   xmm0, xmm0
0x180003b28  mov     [rsp+2B0h+CreateOptions], 0; CreateOptions
0x180003b30  xor     r9d, r9d; TitleIndex
0x180003b33  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x180003b38  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x180003b3d  mov     [rsp+2B0h+Class], 0; Class
0x180003b46  mov     edx, 20019h; DesiredAccess
0x180003b4b  mov     [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x180003b53  lea     rcx, ghFontRegistryHKCU; KeyHandle
0x180003b5a  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], 0
0x180003b63  movdqu  xmmword ptr [rbp+1B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003b68  mov     [rsp+2B0h+ObjectAttributes.Attributes], 40h ; '@'
0x180003b70  call    cs:__imp_NtCreateKey
0x180003b77  nop     dword ptr [rax+rax+00h]
0x180003b7c  mov     ebx, eax
0x180003b7e  lea     rcx, [rsp+2B0h+KeyPath]; UnicodeString
0x180003b83  call    cs:__imp_RtlFreeUnicodeString
0x180003b8a  nop     dword ptr [rax+rax+00h]
0x180003b8f  mov     eax, ebx
0x180003b91  mov     rcx, [rbp+1B0h+var_10]
0x180003b98  xor     rcx, rsp; StackCookie
0x180003b9b  call    __security_check_cookie
0x180003ba0  mov     rbx, [rsp+2B0h+arg_0]
0x180003ba8  add     rsp, 2B0h
0x180003baf  pop     rbp
0x180003bb0  retn
```
