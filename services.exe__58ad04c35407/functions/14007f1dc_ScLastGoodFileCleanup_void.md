# ScLastGoodFileCleanup(void)

- ea: `0x14007f1dc`
- end: `0x14007f2bb`
- name: `?ScLastGoodFileCleanup@@YAKXZ`
- size: `223`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140064d34`

## callees

- `0x1400454ec`
- `0x14007f1dc`

## import_xrefs

- `ntdll!NtDeleteFile` at `0x14007f25c`
- `ntdll!NtDeleteFile` at `0x14007f25c`
- `ntdll!NtClose` at `0x14007f2ad`
- `ntdll!NtClose` at `0x14007f2ad`
- `ntdll!RtlInitUnicodeString` at `0x14007f212`
- `ntdll!RtlInitUnicodeString` at `0x14007f223`
- `ntdll!RtlInitUnicodeString` at `0x14007f212`
- `ntdll!RtlInitUnicodeString` at `0x14007f223`
- `ntdll!NtDeleteKey` at `0x14007f2a3`
- `ntdll!NtDeleteKey` at `0x14007f2a3`
- `ntdll!NtOpenKey` at `0x14007f295`
- `ntdll!NtOpenKey` at `0x14007f295`

## string_xrefs

- `0x14007f218`: `\Registry\Machine\System\LastKnownGoodRecovery\LastGood.Tmp`

## pseudocode

```c
__int64 ScLastGoodFileCleanup(void)
{
  __int64 v0; // rdx
  int (*v1)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *); // r8
  void *v2; // r9
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING v5; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+10h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v5 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SystemRoot\\LastGood.Tmp");
  RtlInitUnicodeString(&v5, L"\\Registry\\Machine\\System\\LastKnownGoodRecovery\\LastGood.Tmp");
  ScLastGoodWalkDirectoryTreeBottomUp(&DestinationString, v0, v1, v2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 64;
  NtDeleteFile(&ObjectAttributes);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v5;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) >= 0 )
  {
    NtDeleteKey(KeyHandle);
    NtClose(KeyHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x14007f1dc  push    rbp
0x14007f1de  mov     rbp, rsp
0x14007f1e1  sub     rsp, 70h
0x14007f1e5  xorps   xmm0, xmm0
0x14007f1e8  mov     [rbp+KeyHandle], 0
0x14007f1f0  xorps   xmm1, xmm1
0x14007f1f3  lea     rdx, aSystemrootLast; "\\SystemRoot\\LastGood.Tmp"
0x14007f1fa  lea     rcx, [rbp+DestinationString]; DestinationString
0x14007f1fe  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14007f202  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14007f206  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14007f20a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14007f20e  movups  xmmword ptr [rbp+var_40.Length], xmm1
0x14007f212  call    cs:__imp_RtlInitUnicodeString
0x14007f218  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\LastKnownG"...
0x14007f21f  lea     rcx, [rbp+var_40]; DestinationString
0x14007f223  call    cs:__imp_RtlInitUnicodeString
0x14007f229  lea     rcx, [rbp+DestinationString]; SourceString
0x14007f22d  call    ?ScLastGoodWalkDirectoryTreeBottomUp@@YAKPEAU_UNICODE_STRING@@KP6AJ00KPEAX@Z1@Z; ScLastGoodWalkDirectoryTreeBottomUp(_UNICODE_STRING *,ulong,long (*)(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *),void *)
0x14007f232  lea     rax, [rbp+DestinationString]
0x14007f236  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14007f23d  xorps   xmm0, xmm0
0x14007f240  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14007f244  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x14007f248  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14007f250  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14007f255  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14007f25c  call    cs:__imp_NtDeleteFile
0x14007f262  lea     rax, [rbp+var_40]
0x14007f266  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14007f26d  xorps   xmm0, xmm0
0x14007f270  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14007f274  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14007f278  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14007f280  mov     edx, 0F003Fh; DesiredAccess
0x14007f285  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14007f28c  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14007f290  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14007f295  call    cs:__imp_NtOpenKey
0x14007f29b  test    eax, eax
0x14007f29d  js      short loc_14007F2B3
0x14007f29f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14007f2a3  call    cs:__imp_NtDeleteKey
0x14007f2a9  mov     rcx, [rbp+KeyHandle]; Handle
0x14007f2ad  call    cs:__imp_NtClose
0x14007f2b3  xor     eax, eax
0x14007f2b5  add     rsp, 70h
0x14007f2b9  pop     rbp
0x14007f2ba  retn
```
