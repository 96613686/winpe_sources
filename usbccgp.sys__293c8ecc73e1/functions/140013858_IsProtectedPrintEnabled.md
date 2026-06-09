# IsProtectedPrintEnabled

- ea: `0x140013858`
- end: `0x140013993`
- name: `IsProtectedPrintEnabled`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140023938`
- `0x1400249d4`

## callees

- `0x140013858`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013970`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013970`
- `ntoskrnl!ZwQueryValueKey` at `0x140013944`
- `ntoskrnl!ZwQueryValueKey` at `0x140013944`
- `ntoskrnl!ZwClose` at `0x14001395f`
- `ntoskrnl!ZwClose` at `0x14001395f`
- `ntoskrnl!ZwOpenKey` at `0x140013915`
- `ntoskrnl!ZwOpenKey` at `0x140013915`
- `ntoskrnl!ExAllocatePool2` at `0x14001389e`
- `ntoskrnl!ExAllocatePool2` at `0x14001389e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400138c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400138d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400138c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400138d8`

## string_xrefs

- `0x1400138b6`: `\Registry\Machine\Software\Policies\Microsoft\Windows NT\Printers\WPP`

## pseudocode

```c
_BOOL8 IsProtectedPrintEnabled()
{
  BOOL v0; // ebx
  _DWORD *Pool2; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Length; // [rsp+A0h] [rbp+20h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+28h] BYREF

  KeyHandle = 0;
  v0 = 0;
  Length = 20;
  DestinationString = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, 44);
  Pool2 = (_DWORD *)ExAllocatePool2(256, 20, 1130525525);
  if ( Pool2 )
  {
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP");
    RtlInitUnicodeString(&ValueName, L"WindowsProtectedPrintMode");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
    {
      if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, Length, &Length) >= 0 )
        v0 = Pool2[3] != 0;
      ZwClose(KeyHandle);
    }
    ExFreePoolWithTag(Pool2, 0);
  }
  return v0;
}

```

## disassembly

```asm
0x140013858  mov     [rsp-18h+arg_10], rbx
0x14001385d  push    rbp
0x14001385e  push    rdi
0x14001385f  push    r14
0x140013861  mov     rbp, rsp
0x140013864  sub     rsp, 80h
0x14001386b  xorps   xmm0, xmm0
0x14001386e  xor     eax, eax
0x140013870  xorps   xmm1, xmm1
0x140013873  mov     [rbp+KeyHandle], rax
0x140013877  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001387b  mov     ecx, 100h
0x140013880  mov     r8d, 43627355h
0x140013886  lea     edx, [rax+14h]
0x140013889  xor     ebx, ebx
0x14001388b  mov     [rbp+arg_0], edx
0x14001388e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140013892  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x140013896  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001389a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001389e  call    cs:__imp_ExAllocatePool2
0x1400138a5  nop     dword ptr [rax+rax+00h]
0x1400138aa  mov     rdi, rax
0x1400138ad  test    rax, rax
0x1400138b0  jz      loc_14001397C
0x1400138b6  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Policies"...
0x1400138bd  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400138c1  call    cs:__imp_RtlInitUnicodeString
0x1400138c8  nop     dword ptr [rax+rax+00h]
0x1400138cd  lea     rdx, aWindowsprotect; "WindowsProtectedPrintMode"
0x1400138d4  lea     rcx, [rbp+ValueName]; DestinationString
0x1400138d8  call    cs:__imp_RtlInitUnicodeString
0x1400138df  nop     dword ptr [rax+rax+00h]
0x1400138e4  lea     rax, [rbp+DestinationString]
0x1400138e8  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400138ef  xorps   xmm0, xmm0
0x1400138f2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400138f6  lea     r14d, [rbx+1]
0x1400138fa  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x1400138fe  mov     edx, r14d; DesiredAccess
0x140013901  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140013908  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001390c  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140013910  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140013915  call    cs:__imp_ZwOpenKey
0x14001391c  nop     dword ptr [rax+rax+00h]
0x140013921  test    eax, eax
0x140013923  js      short loc_14001396B
0x140013925  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140013929  lea     rax, [rbp+arg_0]
0x14001392d  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140013932  lea     r8d, [rbx+2]; KeyValueInformationClass
0x140013936  mov     eax, [rbp+arg_0]
0x140013939  lea     rdx, [rbp+ValueName]; ValueName
0x14001393d  mov     r9, rdi; KeyValueInformation
0x140013940  mov     [rsp+80h+Length], eax; Length
0x140013944  call    cs:__imp_ZwQueryValueKey
0x14001394b  nop     dword ptr [rax+rax+00h]
0x140013950  test    eax, eax
0x140013952  js      short loc_14001395B
0x140013954  cmp     [rdi+0Ch], ebx
0x140013957  cmovnz  ebx, r14d
0x14001395b  mov     rcx, [rbp+KeyHandle]; Handle
0x14001395f  call    cs:__imp_ZwClose
0x140013966  nop     dword ptr [rax+rax+00h]
0x14001396b  xor     edx, edx; Tag
0x14001396d  mov     rcx, rdi; P
0x140013970  call    cs:__imp_ExFreePoolWithTag
0x140013977  nop     dword ptr [rax+rax+00h]
0x14001397c  mov     eax, ebx
0x14001397e  mov     rbx, [rsp+80h+arg_10]
0x140013986  add     rsp, 80h
0x14001398d  pop     r14
0x14001398f  pop     rdi
0x140013990  pop     rbp
0x140013991  retn
```
