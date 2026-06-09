# VmxpFlushRegistryKey(ushort const *)

- ea: `0x140008fd4`
- end: `0x140009080`
- name: `?VmxpFlushRegistryKey@@YAXPEBG@Z`
- size: `172`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140008eec`
- `0x140008f3c`
- `0x140009670`
- `0x140009718`

## callees

- `0x140008fd4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000900a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000900a`
- `ntoskrnl!ZwFlushKey` at `0x14000905d`
- `ntoskrnl!ZwFlushKey` at `0x14000905d`
- `ntoskrnl!ZwClose` at `0x14000906d`
- `ntoskrnl!ZwClose` at `0x14000906d`
- `ntoskrnl!ZwOpenKey` at `0x140009049`
- `ntoskrnl!ZwOpenKey` at `0x140009049`

## string_xrefs

- `0x140008fef`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
void __fastcall VmxpFlushRegistryKey(const unsigned __int16 *a1)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\VolMgrX");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes) >= 0 )
  {
    ZwFlushKey(KeyHandle);
    ZwClose(KeyHandle);
  }
}

```

## disassembly

```asm
0x140008fd4  mov     [rsp-8+KeyHandle], rcx
0x140008fd9  push    rbp
0x140008fda  mov     rbp, rsp
0x140008fdd  sub     rsp, 60h
0x140008fe1  xorps   xmm1, xmm1
0x140008fe4  mov     [rbp+KeyHandle], 0
0x140008fec  xorps   xmm0, xmm0
0x140008fef  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x140008ff6  lea     rcx, [rbp+DestinationString]; DestinationString
0x140008ffa  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140008ffe  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x140009002  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x140009006  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x14000900a  call    cs:__imp_RtlInitUnicodeString
0x140009011  nop     dword ptr [rax+rax+00h]
0x140009016  lea     rax, [rbp+DestinationString]
0x14000901a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140009021  xorps   xmm0, xmm0
0x140009024  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140009028  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000902c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140009034  mov     edx, 2001Fh; DesiredAccess
0x140009039  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140009040  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140009044  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140009049  call    cs:__imp_ZwOpenKey
0x140009050  nop     dword ptr [rax+rax+00h]
0x140009055  test    eax, eax
0x140009057  js      short loc_140009079
0x140009059  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000905d  call    cs:__imp_ZwFlushKey
0x140009064  nop     dword ptr [rax+rax+00h]
0x140009069  mov     rcx, [rbp+KeyHandle]; Handle
0x14000906d  call    cs:__imp_ZwClose
0x140009074  nop     dword ptr [rax+rax+00h]
0x140009079  add     rsp, 60h
0x14000907d  pop     rbp
0x14000907e  retn
```
