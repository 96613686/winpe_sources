# WriteShutdownReasonToRegistry

- ea: `0x18000a73c`
- end: `0x18000a90b`
- name: `WriteShutdownReasonToRegistry`
- size: `463`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800080b0`

## callees

- `0x18000a73c`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x18000a7fc`
- `ntdll!NtDeleteValueKey` at `0x18000a827`
- `ntdll!NtDeleteValueKey` at `0x18000a898`
- `ntdll!NtDeleteValueKey` at `0x18000a7fc`
- `ntdll!NtDeleteValueKey` at `0x18000a827`
- `ntdll!NtDeleteValueKey` at `0x18000a898`
- `ntdll!NtSetValueKey` at `0x18000a867`
- `ntdll!NtSetValueKey` at `0x18000a8d7`
- `ntdll!NtSetValueKey` at `0x18000a867`
- `ntdll!NtSetValueKey` at `0x18000a8d7`
- `ntdll!NtCreateKey` at `0x18000a7c7`
- `ntdll!NtCreateKey` at `0x18000a7c7`
- `ntdll!RtlInitUnicodeString` at `0x18000a77b`
- `ntdll!RtlInitUnicodeString` at `0x18000a7e8`
- `ntdll!RtlInitUnicodeString` at `0x18000a813`
- `ntdll!RtlInitUnicodeString` at `0x18000a83e`
- `ntdll!RtlInitUnicodeString` at `0x18000a884`
- `ntdll!RtlInitUnicodeString` at `0x18000a77b`
- `ntdll!RtlInitUnicodeString` at `0x18000a7e8`
- `ntdll!RtlInitUnicodeString` at `0x18000a813`
- `ntdll!RtlInitUnicodeString` at `0x18000a83e`
- `ntdll!RtlInitUnicodeString` at `0x18000a884`
- `ntdll!NtClose` at `0x18000a8e9`
- `ntdll!NtClose` at `0x18000a8e9`

## string_xrefs

- `0x18000a768`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Reliability\shutdown`
- `0x18000a808`: `Comment`
- `0x18000a879`: `Comment`

## pseudocode

```c
__int64 __fastcall WriteShutdownReasonToRegistry(int a1, _WORD *a2)
{
  NTSTATUS v3; // ebx
  __int64 v4; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int Data; // [rsp+A0h] [rbp+20h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF

  Data = a1;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Reliability\\shutdown");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v3 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ReasonCode");
    NtDeleteValueKey(KeyHandle, &DestinationString);
    RtlInitUnicodeString(&DestinationString, L"Comment");
    NtDeleteValueKey(KeyHandle, &DestinationString);
    RtlInitUnicodeString(&DestinationString, L"ReasonCode");
    v3 = NtSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
    if ( v3 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"Comment");
      NtDeleteValueKey(KeyHandle, &DestinationString);
      if ( a2 )
      {
        v4 = -1;
        do
          ++v4;
        while ( a2[v4] );
        v3 = NtSetValueKey(KeyHandle, &DestinationString, 0, 1u, a2, 2 * v4 + 2);
      }
    }
    NtClose(KeyHandle);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a73c  mov     [rsp-18h+arg_8], rbx
0x18000a741  mov     [rsp-18h+Data], ecx
0x18000a745  push    rbp
0x18000a746  push    rsi
0x18000a747  push    rdi
0x18000a748  mov     rbp, rsp
0x18000a74b  sub     rsp, 80h
0x18000a752  xorps   xmm0, xmm0
0x18000a755  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a759  mov     rdi, rdx
0x18000a75c  xor     esi, esi
0x18000a75e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000a762  xor     eax, eax
0x18000a764  mov     [rbp+KeyHandle], rsi
0x18000a768  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\Software\\Microsof"...
0x18000a76f  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000a773  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000a777  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000a77b  call    cs:__imp_RtlInitUnicodeString
0x18000a782  nop     dword ptr [rax+rax+00h]
0x18000a787  lea     rax, [rbp+DestinationString]
0x18000a78b  mov     [rsp+80h+Disposition], rsi; Disposition
0x18000a790  xorps   xmm0, xmm0
0x18000a793  mov     [rsp+80h+CreateOptions], esi; CreateOptions
0x18000a797  xor     r9d, r9d; TitleIndex
0x18000a79a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000a79e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000a7a2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000a7a9  mov     edx, 0F003Fh; DesiredAccess
0x18000a7ae  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18000a7b2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18000a7b6  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000a7bd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a7c2  mov     [rsp+80h+Class], rsi; Class
0x18000a7c7  call    cs:__imp_NtCreateKey
0x18000a7ce  nop     dword ptr [rax+rax+00h]
0x18000a7d3  mov     ebx, eax
0x18000a7d5  test    eax, eax
0x18000a7d7  js      loc_18000A8F5
0x18000a7dd  lea     rdx, aReasoncode; "ReasonCode"
0x18000a7e4  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a7e8  call    cs:__imp_RtlInitUnicodeString
0x18000a7ef  nop     dword ptr [rax+rax+00h]
0x18000a7f4  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000a7f8  lea     rdx, [rbp+DestinationString]; ValueName
0x18000a7fc  call    cs:__imp_NtDeleteValueKey
0x18000a803  nop     dword ptr [rax+rax+00h]
0x18000a808  lea     rdx, aComment; "Comment"
0x18000a80f  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a813  call    cs:__imp_RtlInitUnicodeString
0x18000a81a  nop     dword ptr [rax+rax+00h]
0x18000a81f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000a823  lea     rdx, [rbp+DestinationString]; ValueName
0x18000a827  call    cs:__imp_NtDeleteValueKey
0x18000a82e  nop     dword ptr [rax+rax+00h]
0x18000a833  lea     rdx, aReasoncode; "ReasonCode"
0x18000a83a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a83e  call    cs:__imp_RtlInitUnicodeString
0x18000a845  nop     dword ptr [rax+rax+00h]
0x18000a84a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000a84e  lea     r9d, [rsi+4]; Type
0x18000a852  lea     rax, [rbp+Data]
0x18000a856  mov     [rsp+80h+CreateOptions], r9d; DataSize
0x18000a85b  xor     r8d, r8d; TitleIndex
0x18000a85e  mov     [rsp+80h+Class], rax; Data
0x18000a863  lea     rdx, [rbp+DestinationString]; ValueName
0x18000a867  call    cs:__imp_NtSetValueKey
0x18000a86e  nop     dword ptr [rax+rax+00h]
0x18000a873  mov     ebx, eax
0x18000a875  test    eax, eax
0x18000a877  js      short loc_18000A8E5
0x18000a879  lea     rdx, aComment; "Comment"
0x18000a880  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a884  call    cs:__imp_RtlInitUnicodeString
0x18000a88b  nop     dword ptr [rax+rax+00h]
0x18000a890  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000a894  lea     rdx, [rbp+DestinationString]; ValueName
0x18000a898  call    cs:__imp_NtDeleteValueKey
0x18000a89f  nop     dword ptr [rax+rax+00h]
0x18000a8a4  test    rdi, rdi
0x18000a8a7  jz      short loc_18000A8E5
0x18000a8a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a8ad  inc     rax
0x18000a8b0  cmp     [rdi+rax*2], si
0x18000a8b4  jnz     short loc_18000A8AD
0x18000a8b6  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000a8ba  lea     eax, ds:2[rax*2]
0x18000a8c1  mov     [rsp+80h+CreateOptions], eax; DataSize
0x18000a8c5  lea     rdx, [rbp+DestinationString]; ValueName
0x18000a8c9  mov     r9d, 1; Type
0x18000a8cf  mov     [rsp+80h+Class], rdi; Data
0x18000a8d4  xor     r8d, r8d; TitleIndex
0x18000a8d7  call    cs:__imp_NtSetValueKey
0x18000a8de  nop     dword ptr [rax+rax+00h]
0x18000a8e3  mov     ebx, eax
0x18000a8e5  mov     rcx, [rbp+KeyHandle]; Handle
0x18000a8e9  call    cs:__imp_NtClose
0x18000a8f0  nop     dword ptr [rax+rax+00h]
0x18000a8f5  mov     eax, ebx
0x18000a8f7  mov     rbx, [rsp+80h+arg_8]
0x18000a8ff  add     rsp, 80h
0x18000a906  pop     rdi
0x18000a907  pop     rsi
0x18000a908  pop     rbp
0x18000a909  retn
```
