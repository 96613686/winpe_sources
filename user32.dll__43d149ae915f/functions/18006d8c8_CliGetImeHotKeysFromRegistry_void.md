# CliGetImeHotKeysFromRegistry(void)

- ea: `0x18006d8c8`
- end: `0x18006da17`
- name: `?CliGetImeHotKeysFromRegistry@@YAHXZ`
- size: `335`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180056868`

## callees

- `0x180052ba4`
- `0x18006d8c8`
- `0x1800731c0`
- `0x1800736d4`
- `0x180096e00`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x18006d9b3`
- `ntdll!NtEnumerateKey` at `0x18006d9b3`
- `ntdll!RtlOpenCurrentUser` at `0x18006d919`
- `ntdll!RtlOpenCurrentUser` at `0x18006d919`
- `ntdll!NtClose` at `0x18006d9e4`
- `ntdll!NtClose` at `0x18006d9ee`
- `ntdll!NtClose` at `0x18006d9e4`
- `ntdll!NtClose` at `0x18006d9ee`
- `ntdll!NtOpenKey` at `0x18006d980`
- `ntdll!NtOpenKey` at `0x18006d980`
- `ntdll!RtlInitUnicodeString` at `0x18006d947`
- `ntdll!RtlInitUnicodeString` at `0x18006d947`

## pseudocode

```c
__int64 CliGetImeHotKeysFromRegistry(void)
{
  unsigned int v1; // ebx
  ULONG i; // edi
  NTSTATUS v3; // eax
  HANDLE Handle; // [rsp+30h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-41h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-21h] BYREF
  struct _KEY_BASIC_INFORMATION KeyInformation[2]; // [rsp+88h] [rbp+Fh] BYREF

  KeyHandle = 0;
  Handle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( RtlOpenCurrentUser(0x2000000u, &KeyHandle) < 0 )
    return 0;
  if ( (unsigned int)Feature_KeyboardSettings_InputProfileHotKeys__private_IsEnabledDeviceUsageNoInline() )
    CliGetKeyboardHotKeysFromRegistry(KeyHandle);
  RtlInitUnicodeString(&DestinationString, L"Control Panel\\Input Method\\Hot Keys");
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = 0;
  if ( NtOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      ResultLength = 0;
      v3 = NtEnumerateKey(Handle, i, KeyBasicInformation, KeyInformation, 0x38u, &ResultLength);
      if ( v3 < 0 )
      {
        if ( v3 == -2147483622 )
        {
          NtClose(Handle);
          break;
        }
      }
      else if ( (unsigned int)CliSetSingleHotKey(KeyInformation, Handle) )
      {
        v1 = 1;
      }
    }
  }
  NtClose(KeyHandle);
  return v1;
}

```

## disassembly

```asm
0x18006d8c8  mov     [rsp-8+arg_0], rbx
0x18006d8cd  mov     [rsp-8+arg_8], rdi
0x18006d8d2  push    rbp
0x18006d8d3  lea     rbp, [rsp-57h]
0x18006d8d8  sub     rsp, 0D0h
0x18006d8df  mov     rax, cs:__security_cookie
0x18006d8e6  xor     rax, rsp
0x18006d8e9  mov     [rbp+57h+var_10], rax
0x18006d8ed  xorps   xmm0, xmm0
0x18006d8f0  mov     [rbp+57h+KeyHandle], 0
0x18006d8f8  lea     rdx, [rbp+57h+KeyHandle]; KeyHandle
0x18006d8fc  mov     [rbp+57h+Handle], 0
0x18006d904  mov     ecx, 2000000h; DesiredAccess
0x18006d909  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006d90d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006d911  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d915  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006d919  call    cs:__imp_RtlOpenCurrentUser
0x18006d91f  test    eax, eax
0x18006d921  jns     short loc_18006D92A
0x18006d923  xor     eax, eax
0x18006d925  jmp     loc_18006D9F6
0x18006d92a  call    Feature_KeyboardSettings_InputProfileHotKeys__private_IsEnabledDeviceUsageNoInline
0x18006d92f  test    eax, eax
0x18006d931  jz      short loc_18006D93C
0x18006d933  mov     rcx, [rbp+57h+KeyHandle]; void *
0x18006d937  call    ?CliGetKeyboardHotKeysFromRegistry@@YAXPEAX@Z; CliGetKeyboardHotKeysFromRegistry(void *)
0x18006d93c  lea     rdx, aControlPanelIn; "Control Panel\\Input Method\\Hot Keys"
0x18006d943  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006d947  call    cs:__imp_RtlInitUnicodeString
0x18006d94d  mov     rax, [rbp+57h+KeyHandle]
0x18006d951  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006d955  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18006d959  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18006d95d  lea     rax, [rbp+57h+DestinationString]
0x18006d961  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006d968  xorps   xmm0, xmm0
0x18006d96b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006d96f  mov     edx, 20019h; DesiredAccess
0x18006d974  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18006d97b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d980  call    cs:__imp_NtOpenKey
0x18006d986  xor     ebx, ebx
0x18006d988  test    eax, eax
0x18006d98a  js      short loc_18006D9EA
0x18006d98c  xor     edi, edi
0x18006d98e  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18006d992  lea     rax, [rbp+57h+var_90]
0x18006d996  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x18006d99b  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x18006d99f  xor     r8d, r8d; KeyInformationClass
0x18006d9a2  mov     [rsp+0D0h+Length], 38h ; '8'; Length
0x18006d9aa  mov     edx, edi; Index
0x18006d9ac  mov     [rbp+57h+var_90], 0
0x18006d9b3  call    cs:__imp_NtEnumerateKey
0x18006d9b9  test    eax, eax
0x18006d9bb  js      short loc_18006D9D5
0x18006d9bd  mov     rdx, [rbp+57h+Handle]; void *
0x18006d9c1  lea     rcx, [rbp+57h+KeyInformation]; struct _KEY_BASIC_INFORMATION *
0x18006d9c5  call    ?CliSetSingleHotKey@@YAHPEAU_KEY_BASIC_INFORMATION@@PEAX@Z; CliSetSingleHotKey(_KEY_BASIC_INFORMATION *,void *)
0x18006d9ca  test    eax, eax
0x18006d9cc  jz      short loc_18006D9DC
0x18006d9ce  mov     ebx, 1
0x18006d9d3  jmp     short loc_18006D9DC
0x18006d9d5  cmp     eax, 8000001Ah
0x18006d9da  jz      short loc_18006D9E0
0x18006d9dc  inc     edi
0x18006d9de  jmp     short loc_18006D98E
0x18006d9e0  mov     rcx, [rbp+57h+Handle]; Handle
0x18006d9e4  call    cs:__imp_NtClose
0x18006d9ea  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18006d9ee  call    cs:__imp_NtClose
0x18006d9f4  mov     eax, ebx
0x18006d9f6  mov     rcx, [rbp+57h+var_10]
0x18006d9fa  xor     rcx, rsp; StackCookie
0x18006d9fd  call    __security_check_cookie
0x18006da02  lea     r11, [rsp+0D0h+var_s0]
0x18006da0a  mov     rbx, [r11+10h]
0x18006da0e  mov     rdi, [r11+18h]
0x18006da12  mov     rsp, r11
0x18006da15  pop     rbp
0x18006da16  retn
```
