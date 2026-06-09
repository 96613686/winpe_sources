# SampRemoveAdminPasswordFromRegistry(void)

- ea: `0x1800702bc`
- end: `0x180070401`
- name: `?SampRemoveAdminPasswordFromRegistry@@YAJXZ`
- size: `325`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180070b54`
- `0x1800715d0`
- `0x180071780`
- `0x180072220`
- `0x180073870`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x1800702bc`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180070354`
- `ntdll!NtDeleteValueKey` at `0x180070354`
- `ntdll!NtOpenKey` at `0x18007032f`
- `ntdll!NtOpenKey` at `0x18007032f`
- `ntdll!NtClose` at `0x18007038f`
- `ntdll!NtClose` at `0x18007038f`
- `ntdll!RtlInitUnicodeString` at `0x1800702f6`
- `ntdll!RtlInitUnicodeString` at `0x180070346`
- `ntdll!RtlInitUnicodeString` at `0x1800702f6`
- `ntdll!RtlInitUnicodeString` at `0x180070346`

## string_xrefs

- `0x1800702d7`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 SampRemoveAdminPasswordFromRegistry(void)
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  NTSTATUS v2; // eax
  PUNICODE_STRING v3; // rcx
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
    RtlInitUnicodeString(&ValueName, L"AdminInfo");
    v2 = NtDeleteValueKey(KeyHandle, &ValueName);
    v1 = v2;
    if ( v2 < 0 && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 147, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v2);
    NtClose(KeyHandle);
    goto LABEL_10;
  }
  v3 = WPP_GLOBAL_Control;
  if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 148, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v0);
LABEL_10:
    v3 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v3[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v3[3].Buffer, 149, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v1, v1);
  return v1;
}

```

## disassembly

```asm
0x1800702bc  mov     [rsp-8+arg_8], rbx
0x1800702c1  push    rbp
0x1800702c2  mov     rbp, rsp
0x1800702c5  sub     rsp, 80h
0x1800702cc  xorps   xmm0, xmm0
0x1800702cf  mov     [rbp+KeyHandle], 0
0x1800702d7  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800702de  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800702e2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800702e6  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800702ea  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800702ee  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800702f2  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x1800702f6  call    cs:__imp_RtlInitUnicodeString
0x1800702fc  lea     rax, [rbp+DestinationString]
0x180070300  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180070307  xorps   xmm0, xmm0
0x18007030a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18007030e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180070312  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18007031a  mov     edx, 10000000h; DesiredAccess
0x18007031f  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180070326  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18007032a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007032f  call    cs:__imp_NtOpenKey
0x180070335  mov     ebx, eax
0x180070337  test    eax, eax
0x180070339  js      short loc_180070397
0x18007033b  lea     rdx, aAdmininfo; "AdminInfo"
0x180070342  lea     rcx, [rbp+ValueName]; DestinationString
0x180070346  call    cs:__imp_RtlInitUnicodeString
0x18007034c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180070350  lea     rdx, [rbp+ValueName]; ValueName
0x180070354  call    cs:__imp_NtDeleteValueKey
0x18007035a  mov     ebx, eax
0x18007035c  test    eax, eax
0x18007035e  jns     short loc_18007038B
0x180070360  mov     rcx, cs:WPP_GLOBAL_Control
0x180070367  test    byte ptr [rcx+44h], 80h
0x18007036b  jz      short loc_18007038B
0x18007036d  cmp     byte ptr [rcx+41h], 2
0x180070371  jb      short loc_18007038B
0x180070373  mov     rcx, [rcx+38h]
0x180070377  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18007037e  mov     edx, 93h
0x180070383  mov     r9d, eax
0x180070386  call    WPP_SF_d
0x18007038b  mov     rcx, [rbp+KeyHandle]; Handle
0x18007038f  call    cs:__imp_NtClose
0x180070395  jmp     short loc_1800703C2
0x180070397  mov     rcx, cs:WPP_GLOBAL_Control
0x18007039e  test    byte ptr [rcx+44h], 80h
0x1800703a2  jz      short loc_1800703C9
0x1800703a4  cmp     byte ptr [rcx+41h], 2
0x1800703a8  jb      short loc_1800703C9
0x1800703aa  mov     rcx, [rcx+38h]
0x1800703ae  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x1800703b5  mov     edx, 94h
0x1800703ba  mov     r9d, eax
0x1800703bd  call    WPP_SF_d
0x1800703c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800703c9  test    dword ptr [rcx+44h], 20000h
0x1800703d0  jz      short loc_1800703EE
0x1800703d2  mov     rcx, [rcx+38h]
0x1800703d6  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x1800703dd  mov     edx, 95h
0x1800703e2  mov     [rsp+80h+var_60], ebx
0x1800703e6  mov     r9d, ebx
0x1800703e9  call    WPP_SF_Dd
0x1800703ee  mov     eax, ebx
0x1800703f0  mov     rbx, [rsp+80h+arg_8]
0x1800703f8  add     rsp, 80h
0x1800703ff  pop     rbp
0x180070400  retn
```
