# SampCreateKeyForPostBootPromote(ulong)

- ea: `0x18006d850`
- end: `0x18006da0c`
- name: `?SampCreateKeyForPostBootPromote@@YAJK@Z`
- size: `444`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800715d0`
- `0x180071af0`
- `0x1800722d0`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x18006d850`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x18006d913`
- `ntdll!NtSetValueKey` at `0x18006d913`
- `ntdll!NtOpenKey` at `0x18006d8cc`
- `ntdll!NtOpenKey` at `0x18006d8cc`
- `ntdll!NtFlushKey` at `0x18006d94a`
- `ntdll!NtFlushKey` at `0x18006d94a`
- `ntdll!NtClose` at `0x18006d97f`
- `ntdll!NtClose` at `0x18006d97f`
- `ntdll!RtlInitUnicodeString` at `0x18006d893`
- `ntdll!RtlInitUnicodeString` at `0x18006d8ee`
- `ntdll!RtlInitUnicodeString` at `0x18006d893`
- `ntdll!RtlInitUnicodeString` at `0x18006d8ee`

## string_xrefs

- `0x18006d874`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 __fastcall SampCreateKeyForPostBootPromote(int a1)
{
  NTSTATUS v1; // eax
  unsigned int v2; // ebx
  NTSTATUS v3; // eax
  PUNICODE_STRING v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int Data; // [rsp+90h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp+18h] BYREF

  Data = a1;
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
  v1 = NtOpenKey(&KeyHandle, 0x10000000u, &ObjectAttributes);
  v2 = v1;
  if ( v1 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v5 = 102;
      v6 = (unsigned int)v1;
      goto LABEL_17;
    }
  }
  else
  {
    RtlInitUnicodeString(&ValueName, L"PostPromoteBoot");
    v3 = NtSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
    v2 = v3;
    if ( v3 < 0 && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 99, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v3);
    if ( NtFlushKey(KeyHandle) < 0
      && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 100, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v2);
    }
    if ( NtClose(KeyHandle) >= 0 )
      goto LABEL_18;
    v4 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v5 = 101;
      v6 = v2;
LABEL_17:
      WPP_SF_d(v4[3].Buffer, v5, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v6);
LABEL_18:
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (*(_DWORD *)(&v4[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v4[3].Buffer, 103, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v2, v2);
  return v2;
}

```

## disassembly

```asm
0x18006d850  mov     [rsp-8+arg_10], rbx
0x18006d855  mov     [rsp-8+arg_18], rdi
0x18006d85a  mov     [rsp-8+arg_0], ecx
0x18006d85e  push    rbp
0x18006d85f  mov     rbp, rsp
0x18006d862  sub     rsp, 80h
0x18006d869  xorps   xmm0, xmm0
0x18006d86c  mov     [rbp+KeyHandle], 0
0x18006d874  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006d87b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006d87f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006d883  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006d887  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d88b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006d88f  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18006d893  call    cs:__imp_RtlInitUnicodeString
0x18006d899  lea     rax, [rbp+DestinationString]
0x18006d89d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006d8a4  xorps   xmm0, xmm0
0x18006d8a7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006d8ab  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006d8af  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18006d8b7  mov     edx, 10000000h; DesiredAccess
0x18006d8bc  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18006d8c3  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18006d8c7  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d8cc  call    cs:__imp_NtOpenKey
0x18006d8d2  lea     rdi, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006d8d9  mov     ebx, eax
0x18006d8db  test    eax, eax
0x18006d8dd  js      loc_18006D9A6
0x18006d8e3  lea     rdx, aPostpromoteboo; "PostPromoteBoot"
0x18006d8ea  lea     rcx, [rbp+ValueName]; DestinationString
0x18006d8ee  call    cs:__imp_RtlInitUnicodeString
0x18006d8f4  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006d8f8  lea     rax, [rbp+arg_0]
0x18006d8fc  mov     r9d, 4; Type
0x18006d902  lea     rdx, [rbp+ValueName]; ValueName
0x18006d906  mov     [rsp+80h+DataSize], r9d; DataSize
0x18006d90b  xor     r8d, r8d; TitleIndex
0x18006d90e  mov     [rsp+80h+Data], rax; Data
0x18006d913  call    cs:__imp_NtSetValueKey
0x18006d919  mov     ebx, eax
0x18006d91b  test    eax, eax
0x18006d91d  jns     short loc_18006D946
0x18006d91f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d926  test    byte ptr [rcx+44h], 80h
0x18006d92a  jz      short loc_18006D946
0x18006d92c  cmp     byte ptr [rcx+41h], 2
0x18006d930  jb      short loc_18006D946
0x18006d932  mov     rcx, [rcx+38h]
0x18006d936  mov     edx, 63h ; 'c'
0x18006d93b  mov     r9d, eax
0x18006d93e  mov     r8, rdi
0x18006d941  call    WPP_SF_d
0x18006d946  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006d94a  call    cs:__imp_NtFlushKey
0x18006d950  test    eax, eax
0x18006d952  jns     short loc_18006D97B
0x18006d954  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d95b  test    byte ptr [rcx+44h], 80h
0x18006d95f  jz      short loc_18006D97B
0x18006d961  cmp     byte ptr [rcx+41h], 2
0x18006d965  jb      short loc_18006D97B
0x18006d967  mov     rcx, [rcx+38h]
0x18006d96b  mov     edx, 64h ; 'd'
0x18006d970  mov     r9d, ebx
0x18006d973  mov     r8, rdi
0x18006d976  call    WPP_SF_d
0x18006d97b  mov     rcx, [rbp+KeyHandle]; Handle
0x18006d97f  call    cs:__imp_NtClose
0x18006d985  test    eax, eax
0x18006d987  jns     short loc_18006D9CD
0x18006d989  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d990  test    byte ptr [rcx+44h], 80h
0x18006d994  jz      short loc_18006D9D4
0x18006d996  cmp     byte ptr [rcx+41h], 2
0x18006d99a  jb      short loc_18006D9D4
0x18006d99c  mov     edx, 65h ; 'e'
0x18006d9a1  mov     r9d, ebx
0x18006d9a4  jmp     short loc_18006D9C1
0x18006d9a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d9ad  test    byte ptr [rcx+44h], 80h
0x18006d9b1  jz      short loc_18006D9D4
0x18006d9b3  cmp     byte ptr [rcx+41h], 2
0x18006d9b7  jb      short loc_18006D9D4
0x18006d9b9  mov     edx, 66h ; 'f'
0x18006d9be  mov     r9d, eax
0x18006d9c1  mov     rcx, [rcx+38h]
0x18006d9c5  mov     r8, rdi
0x18006d9c8  call    WPP_SF_d
0x18006d9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d9d4  test    dword ptr [rcx+44h], 20000h
0x18006d9db  jz      short loc_18006D9F5
0x18006d9dd  mov     rcx, [rcx+38h]
0x18006d9e1  mov     edx, 67h ; 'g'
0x18006d9e6  mov     r9d, ebx
0x18006d9e9  mov     dword ptr [rsp+80h+Data], ebx
0x18006d9ed  mov     r8, rdi
0x18006d9f0  call    WPP_SF_Dd
0x18006d9f5  lea     r11, [rsp+80h+var_s0]
0x18006d9fd  mov     eax, ebx
0x18006d9ff  mov     rbx, [r11+20h]
0x18006da03  mov     rdi, [r11+28h]
0x18006da07  mov     rsp, r11
0x18006da0a  pop     rbp
0x18006da0b  retn
```
