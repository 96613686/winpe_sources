# SampDeleteDsDirsToDeleteKey

- ea: `0x180072c90`
- end: `0x180072de4`
- name: `SampDeleteDsDirsToDeleteKey`
- size: `340`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ec7c`
- `0x1800715d0`
- `0x180071780`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x180072c90`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180072d28`
- `ntdll!NtDeleteValueKey` at `0x180072d28`
- `ntdll!NtOpenKey` at `0x180072d03`
- `ntdll!NtOpenKey` at `0x180072d03`
- `ntdll!NtClose` at `0x180072d72`
- `ntdll!NtClose` at `0x180072d72`
- `ntdll!RtlInitUnicodeString` at `0x180072cca`
- `ntdll!RtlInitUnicodeString` at `0x180072d1a`
- `ntdll!RtlInitUnicodeString` at `0x180072cca`
- `ntdll!RtlInitUnicodeString` at `0x180072d1a`

## string_xrefs

- `0x180072cab`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 SampDeleteDsDirsToDeleteKey()
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  PUNICODE_STRING v2; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+10h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\SAMSS");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenKey(&KeyHandle, 0x10000000u, &ObjectAttributes);
  v1 = v0;
  if ( v0 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"DsDirs");
    v1 = NtDeleteValueKey(KeyHandle, &ValueName);
    if ( (int)(v1 + 0x80000000) >= 0
      && v1 != -1073741772
      && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 180, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v1);
    }
    NtClose(KeyHandle);
    goto LABEL_11;
  }
  v2 = WPP_GLOBAL_Control;
  if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 181, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v0);
LABEL_11:
    v2 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v2[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v2[3].Buffer, 182, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v1, v1);
  return v1;
}

```

## disassembly

```asm
0x180072c90  mov     [rsp-8+arg_8], rbx
0x180072c95  push    rbp
0x180072c96  mov     rbp, rsp
0x180072c99  sub     rsp, 80h
0x180072ca0  xorps   xmm0, xmm0
0x180072ca3  mov     [rbp+KeyHandle], 0
0x180072cab  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x180072cb2  lea     rcx, [rbp+DestinationString]; DestinationString
0x180072cb6  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180072cba  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180072cbe  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180072cc2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180072cc6  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x180072cca  call    cs:__imp_RtlInitUnicodeString
0x180072cd0  lea     rax, [rbp+DestinationString]
0x180072cd4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180072cdb  xorps   xmm0, xmm0
0x180072cde  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180072ce2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180072ce6  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180072cee  mov     edx, 10000000h; DesiredAccess
0x180072cf3  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180072cfa  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180072cfe  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180072d03  call    cs:__imp_NtOpenKey
0x180072d09  mov     ebx, eax
0x180072d0b  test    eax, eax
0x180072d0d  js      short loc_180072D7A
0x180072d0f  lea     rdx, aDsdirs; "DsDirs"
0x180072d16  lea     rcx, [rbp+ValueName]; DestinationString
0x180072d1a  call    cs:__imp_RtlInitUnicodeString
0x180072d20  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180072d24  lea     rdx, [rbp+ValueName]; ValueName
0x180072d28  call    cs:__imp_NtDeleteValueKey
0x180072d2e  mov     ecx, 80000000h
0x180072d33  mov     ebx, eax
0x180072d35  add     eax, ecx
0x180072d37  test    ecx, eax
0x180072d39  jnz     short loc_180072D6E
0x180072d3b  cmp     ebx, 0C0000034h
0x180072d41  jz      short loc_180072D6E
0x180072d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d4a  test    byte ptr [rcx+44h], 80h
0x180072d4e  jz      short loc_180072D6E
0x180072d50  cmp     byte ptr [rcx+41h], 2
0x180072d54  jb      short loc_180072D6E
0x180072d56  mov     rcx, [rcx+38h]
0x180072d5a  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180072d61  mov     edx, 0B4h
0x180072d66  mov     r9d, ebx
0x180072d69  call    WPP_SF_d
0x180072d6e  mov     rcx, [rbp+KeyHandle]; Handle
0x180072d72  call    cs:__imp_NtClose
0x180072d78  jmp     short loc_180072DA5
0x180072d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d81  test    byte ptr [rcx+44h], 80h
0x180072d85  jz      short loc_180072DAC
0x180072d87  cmp     byte ptr [rcx+41h], 2
0x180072d8b  jb      short loc_180072DAC
0x180072d8d  mov     rcx, [rcx+38h]
0x180072d91  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180072d98  mov     edx, 0B5h
0x180072d9d  mov     r9d, eax
0x180072da0  call    WPP_SF_d
0x180072da5  mov     rcx, cs:WPP_GLOBAL_Control
0x180072dac  test    dword ptr [rcx+44h], 20000h
0x180072db3  jz      short loc_180072DD1
0x180072db5  mov     rcx, [rcx+38h]
0x180072db9  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180072dc0  mov     edx, 0B6h
0x180072dc5  mov     [rsp+80h+var_60], ebx
0x180072dc9  mov     r9d, ebx
0x180072dcc  call    WPP_SF_Dd
0x180072dd1  mov     eax, ebx
0x180072dd3  mov     rbx, [rsp+80h+arg_8]
0x180072ddb  add     rsp, 80h
0x180072de2  pop     rbp
0x180072de3  retn
```
