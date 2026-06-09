# WsQueryRegistrySubkeySecurityDescriptor

- ea: `0x18002f09c`
- end: `0x18002f1a9`
- name: `WsQueryRegistrySubkeySecurityDescriptor`
- size: `269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d530`

## callees

- `0x180007604`
- `0x180007710`
- `0x18002f09c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002f119`
- `ntdll!RtlNtStatusToDosError` at `0x18002f119`
- `ntdll!NtClose` at `0x18002f18f`
- `ntdll!NtClose` at `0x18002f18f`
- `ntdll!RtlInitUnicodeString` at `0x18002f0d4`
- `ntdll!RtlInitUnicodeString` at `0x18002f0d4`
- `ntdll!NtOpenKey` at `0x18002f10d`
- `ntdll!NtOpenKey` at `0x18002f10d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002f130`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002f166`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002f130`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002f166`

## pseudocode

```c
__int64 __fastcall WsQueryRegistrySubkeySecurityDescriptor(void **a1, const WCHAR *a2)
{
  int v3; // eax
  ULONG v4; // eax
  unsigned int KeySecurity; // ebx
  HLOCAL v6; // rax
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
    v6 = NetpMemoryAllocate(cbSecurityDescriptor);
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
0x18002f09c  mov     [rsp-8+arg_8], rbx
0x18002f0a1  mov     [rsp-8+arg_18], rdi
0x18002f0a6  push    rbp
0x18002f0a7  mov     rbp, rsp
0x18002f0aa  sub     rsp, 60h
0x18002f0ae  xorps   xmm0, xmm0
0x18002f0b1  xor     eax, eax
0x18002f0b3  mov     [rcx], rax
0x18002f0b6  mov     rdi, rcx
0x18002f0b9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002f0bd  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002f0c1  mov     [rbp+KeyHandle], rax
0x18002f0c5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002f0c9  mov     [rbp+cbSecurityDescriptor], eax
0x18002f0cc  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002f0d0  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18002f0d4  call    cs:__imp_RtlInitUnicodeString
0x18002f0da  lea     rax, [rbp+DestinationString]
0x18002f0de  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002f0e5  xorps   xmm0, xmm0
0x18002f0e8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002f0ec  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002f0f0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002f0f8  mov     edx, 20000h; DesiredAccess
0x18002f0fd  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002f104  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18002f108  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002f10d  call    cs:__imp_NtOpenKey
0x18002f113  test    eax, eax
0x18002f115  jns     short loc_18002F121
0x18002f117  mov     ecx, eax; Status
0x18002f119  call    cs:__imp_RtlNtStatusToDosError
0x18002f11f  jmp     short loc_18002F16C
0x18002f121  mov     rcx, [rbp+KeyHandle]; hKey
0x18002f125  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18002f129  xor     r8d, r8d; pSecurityDescriptor
0x18002f12c  lea     edx, [r8+7]; SecurityInformation
0x18002f130  call    cs:__imp_RegGetKeySecurity
0x18002f136  mov     ebx, eax
0x18002f138  cmp     eax, 7Ah ; 'z'
0x18002f13b  jnz     short loc_18002F16E
0x18002f13d  mov     ecx, [rbp+cbSecurityDescriptor]
0x18002f140  test    ecx, ecx
0x18002f142  jz      short loc_18002F172
0x18002f144  call    NetpMemoryAllocate
0x18002f149  mov     [rdi], rax
0x18002f14c  test    rax, rax
0x18002f14f  jnz     short loc_18002F156
0x18002f151  lea     ebx, [rax+8]
0x18002f154  jmp     short loc_18002F172
0x18002f156  mov     rcx, [rbp+KeyHandle]; hKey
0x18002f15a  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18002f15e  mov     r8, rax; pSecurityDescriptor
0x18002f161  mov     edx, 7; SecurityInformation
0x18002f166  call    cs:__imp_RegGetKeySecurity
0x18002f16c  mov     ebx, eax
0x18002f16e  test    ebx, ebx
0x18002f170  jz      short loc_18002F186
0x18002f172  mov     rcx, [rdi]
0x18002f175  test    rcx, rcx
0x18002f178  jz      short loc_18002F186
0x18002f17a  call    NetpMemoryFree
0x18002f17f  mov     qword ptr [rdi], 0
0x18002f186  mov     rcx, [rbp+KeyHandle]; Handle
0x18002f18a  test    rcx, rcx
0x18002f18d  jz      short loc_18002F195
0x18002f18f  call    cs:__imp_NtClose
0x18002f195  lea     r11, [rsp+60h+var_s0]
0x18002f19a  mov     eax, ebx
0x18002f19c  mov     rbx, [r11+18h]
0x18002f1a0  mov     rdi, [r11+28h]
0x18002f1a4  mov     rsp, r11
0x18002f1a7  pop     rbp
0x18002f1a8  retn
```
