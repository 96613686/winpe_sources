# WsQueryRegistrySubkeySecurityDescriptor

- ea: `0x180031cac`
- end: `0x180031dde`
- name: `WsQueryRegistrySubkeySecurityDescriptor`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002fe70`

## callees

- `0x180007cb0`
- `0x180007cd4`
- `0x180031cac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180031d35`
- `ntdll!RtlNtStatusToDosError` at `0x180031d35`
- `ntdll!NtClose` at `0x180031dbd`
- `ntdll!NtClose` at `0x180031dbd`
- `ntdll!RtlInitUnicodeString` at `0x180031ce4`
- `ntdll!RtlInitUnicodeString` at `0x180031ce4`
- `ntdll!NtOpenKey` at `0x180031d23`
- `ntdll!NtOpenKey` at `0x180031d23`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031d52`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031d8e`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031d52`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031d8e`

## pseudocode

```c
__int64 __fastcall WsQueryRegistrySubkeySecurityDescriptor(_QWORD *a1, const WCHAR *a2)
{
  int v3; // eax
  ULONG v4; // eax
  unsigned int KeySecurity; // ebx
  void *v6; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+70h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+20h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  DestinationString = 0;
  cbSecurityDescriptor = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenKey(&KeyHandle, 0x20000u, &ObjectAttributes);
  if ( v3 < 0 )
  {
    v4 = RtlNtStatusToDosError(v3);
LABEL_8:
    KeySecurity = v4;
LABEL_9:
    if ( !KeySecurity )
      goto LABEL_12;
    goto LABEL_10;
  }
  KeySecurity = RegGetKeySecurity((HKEY)KeyHandle, 7u, 0, &cbSecurityDescriptor);
  if ( KeySecurity != 122 )
    goto LABEL_9;
  if ( cbSecurityDescriptor )
  {
    v6 = (void *)NetpMemoryAllocate(cbSecurityDescriptor);
    *a1 = v6;
    if ( v6 )
    {
      v4 = RegGetKeySecurity((HKEY)KeyHandle, 7u, v6, &cbSecurityDescriptor);
      goto LABEL_8;
    }
    KeySecurity = 8;
  }
LABEL_10:
  if ( *a1 )
  {
    NetpMemoryFree(*a1);
    *a1 = 0;
  }
LABEL_12:
  if ( KeyHandle )
    NtClose(KeyHandle);
  return KeySecurity;
}

```

## disassembly

```asm
0x180031cac  mov     [rsp-8+arg_8], rbx
0x180031cb1  mov     [rsp-8+arg_18], rdi
0x180031cb6  push    rbp
0x180031cb7  mov     rbp, rsp
0x180031cba  sub     rsp, 60h
0x180031cbe  xorps   xmm0, xmm0
0x180031cc1  xor     eax, eax
0x180031cc3  mov     [rcx], rax
0x180031cc6  mov     rdi, rcx
0x180031cc9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180031ccd  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031cd1  mov     [rbp+KeyHandle], rax
0x180031cd5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180031cd9  mov     [rbp+cbSecurityDescriptor], eax
0x180031cdc  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180031ce0  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180031ce4  call    cs:__imp_RtlInitUnicodeString
0x180031ceb  nop     dword ptr [rax+rax+00h]
0x180031cf0  lea     rax, [rbp+DestinationString]
0x180031cf4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180031cfb  xorps   xmm0, xmm0
0x180031cfe  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180031d02  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180031d06  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180031d0e  mov     edx, 20000h; DesiredAccess
0x180031d13  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180031d1a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180031d1e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180031d23  call    cs:__imp_NtOpenKey
0x180031d2a  nop     dword ptr [rax+rax+00h]
0x180031d2f  test    eax, eax
0x180031d31  jns     short loc_180031D43
0x180031d33  mov     ecx, eax; Status
0x180031d35  call    cs:__imp_RtlNtStatusToDosError
0x180031d3c  nop     dword ptr [rax+rax+00h]
0x180031d41  jmp     short loc_180031D9A
0x180031d43  mov     rcx, [rbp+KeyHandle]; hKey
0x180031d47  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180031d4b  xor     r8d, r8d; pSecurityDescriptor
0x180031d4e  lea     edx, [r8+7]; SecurityInformation
0x180031d52  call    cs:__imp_RegGetKeySecurity
0x180031d59  nop     dword ptr [rax+rax+00h]
0x180031d5e  mov     ebx, eax
0x180031d60  cmp     eax, 7Ah ; 'z'
0x180031d63  jnz     short loc_180031D9C
0x180031d65  mov     ecx, [rbp+cbSecurityDescriptor]
0x180031d68  test    ecx, ecx
0x180031d6a  jz      short loc_180031DA0
0x180031d6c  call    NetpMemoryAllocate
0x180031d71  mov     [rdi], rax
0x180031d74  test    rax, rax
0x180031d77  jnz     short loc_180031D7E
0x180031d79  lea     ebx, [rax+8]
0x180031d7c  jmp     short loc_180031DA0
0x180031d7e  mov     rcx, [rbp+KeyHandle]; hKey
0x180031d82  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180031d86  mov     r8, rax; pSecurityDescriptor
0x180031d89  mov     edx, 7; SecurityInformation
0x180031d8e  call    cs:__imp_RegGetKeySecurity
0x180031d95  nop     dword ptr [rax+rax+00h]
0x180031d9a  mov     ebx, eax
0x180031d9c  test    ebx, ebx
0x180031d9e  jz      short loc_180031DB4
0x180031da0  mov     rcx, [rdi]
0x180031da3  test    rcx, rcx
0x180031da6  jz      short loc_180031DB4
0x180031da8  call    NetpMemoryFree
0x180031dad  mov     qword ptr [rdi], 0
0x180031db4  mov     rcx, [rbp+KeyHandle]; Handle
0x180031db8  test    rcx, rcx
0x180031dbb  jz      short loc_180031DC9
0x180031dbd  call    cs:__imp_NtClose
0x180031dc4  nop     dword ptr [rax+rax+00h]
0x180031dc9  lea     r11, [rsp+60h+var_s0]
0x180031dce  mov     eax, ebx
0x180031dd0  mov     rbx, [r11+18h]
0x180031dd4  mov     rdi, [r11+28h]
0x180031dd8  mov     rsp, r11
0x180031ddb  pop     rbp
0x180031ddc  retn
```
