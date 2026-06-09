# RfsRegSetDWord

- ea: `0x14004ab3c`
- end: `0x14004ac33`
- name: `RfsRegSetDWord`
- size: `247`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004a4f0`
- `0x14004dc10`

## callees

- `0x14004ab3c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14004ab7b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ab8e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ab7b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ab8e`
- `ntoskrnl!ZwSetValueKey` at `0x14004abfc`
- `ntoskrnl!ZwSetValueKey` at `0x14004abfc`
- `ntoskrnl!ZwOpenKey` at `0x14004abcd`
- `ntoskrnl!ZwOpenKey` at `0x14004abcd`
- `ntoskrnl!ZwClose` at `0x14004ac0e`
- `ntoskrnl!ZwClose` at `0x14004ac0e`

## pseudocode

```c
NTSTATUS __fastcall RfsRegSetDWord(PCWSTR SourceString, PCWSTR a2, int a3)
{
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int Data; // [rsp+A0h] [rbp+20h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+28h] BYREF

  Data = a3;
  KeyHandle = 0;
  ValueName = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&ValueName, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 2u, &ObjectAttributes);
  if ( result >= 0 )
  {
    v5 = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
    ZwClose(KeyHandle);
    result = 0;
    if ( v5 < 0 )
      return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14004ab3c  mov     [rsp-8+arg_0], rbx
0x14004ab41  mov     [rsp-8+arg_10], r8d
0x14004ab46  push    rbp
0x14004ab47  mov     rbp, rsp
0x14004ab4a  sub     rsp, 80h
0x14004ab51  xorps   xmm0, xmm0
0x14004ab54  mov     rbx, rdx
0x14004ab57  mov     rdx, rcx; SourceString
0x14004ab5a  xorps   xmm1, xmm1
0x14004ab5d  xor     eax, eax
0x14004ab5f  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004ab63  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14004ab67  mov     [rbp+KeyHandle], rax
0x14004ab6b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14004ab6f  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x14004ab73  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14004ab77  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14004ab7b  call    cs:__imp_RtlInitUnicodeString
0x14004ab82  nop     dword ptr [rax+rax+00h]
0x14004ab87  mov     rdx, rbx; SourceString
0x14004ab8a  lea     rcx, [rbp+ValueName]; DestinationString
0x14004ab8e  call    cs:__imp_RtlInitUnicodeString
0x14004ab95  nop     dword ptr [rax+rax+00h]
0x14004ab9a  lea     rax, [rbp+DestinationString]
0x14004ab9e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14004aba5  xorps   xmm0, xmm0
0x14004aba8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14004abac  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14004abb0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14004abb8  mov     edx, 2; DesiredAccess
0x14004abbd  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14004abc4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14004abc8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14004abcd  call    cs:__imp_ZwOpenKey
0x14004abd4  nop     dword ptr [rax+rax+00h]
0x14004abd9  test    eax, eax
0x14004abdb  js      short loc_14004AC21
0x14004abdd  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14004abe1  lea     rax, [rbp+arg_10]
0x14004abe5  mov     r9d, 4; Type
0x14004abeb  lea     rdx, [rbp+ValueName]; ValueName
0x14004abef  mov     [rsp+80h+DataSize], r9d; DataSize
0x14004abf4  xor     r8d, r8d; TitleIndex
0x14004abf7  mov     [rsp+80h+Data], rax; Data
0x14004abfc  call    cs:__imp_ZwSetValueKey
0x14004ac03  nop     dword ptr [rax+rax+00h]
0x14004ac08  mov     rcx, [rbp+KeyHandle]; Handle
0x14004ac0c  mov     ebx, eax
0x14004ac0e  call    cs:__imp_ZwClose
0x14004ac15  nop     dword ptr [rax+rax+00h]
0x14004ac1a  xor     eax, eax
0x14004ac1c  test    ebx, ebx
0x14004ac1e  cmovs   eax, ebx
0x14004ac21  mov     rbx, [rsp+80h+arg_0]
0x14004ac29  add     rsp, 80h
0x14004ac30  pop     rbp
0x14004ac31  retn
```
