# VMX_DISK_DEVICE::OpenDeviceParameterKey(uchar,void * *)

- ea: `0x140033ce0`
- end: `0x140033dec`
- name: `?OpenDeviceParameterKey@VMX_DISK_DEVICE@@QEAAJEPEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(VMX_DISK_DEVICE *__hidden this, unsigned __int8, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003ca48`
- `0x140046648`

## callees

- `0x140033ce0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140033d52`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033d52`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140033d35`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140033d35`
- `ntoskrnl!ZwClose` at `0x140033da3`
- `ntoskrnl!ZwClose` at `0x140033dcb`
- `ntoskrnl!ZwClose` at `0x140033da3`
- `ntoskrnl!ZwClose` at `0x140033dcb`
- `ntoskrnl!ZwOpenKey` at `0x140033d91`
- `ntoskrnl!ZwOpenKey` at `0x140033d91`

## pseudocode

```c
__int64 __fastcall VMX_DISK_DEVICE::OpenDeviceParameterKey(VMX_DISK_DEVICE *this, __int64 a2, void **a3)
{
  struct _DEVICE_OBJECT *v3; // rcx
  NTSTATUS v5; // ebx
  void *v6; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF
  void *DeviceRegKey; // [rsp+80h] [rbp+20h] BYREF

  *a3 = 0;
  v3 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 2);
  DeviceRegKey = 0;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v5 = IoOpenDeviceRegistryKey(v3, 1u, 0x20019u, &DeviceRegKey);
  if ( v5 < 0 )
    goto LABEL_4;
  RtlInitUnicodeString(&DestinationString, L"volmgrx");
  ObjectAttributes.RootDirectory = DeviceRegKey;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  ZwClose(DeviceRegKey);
  if ( v5 < 0 )
  {
LABEL_4:
    v6 = KeyHandle;
  }
  else
  {
    v6 = 0;
    *a3 = KeyHandle;
    KeyHandle = 0;
  }
  if ( v6 )
    ZwClose(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140033ce0  mov     [rsp-8+arg_8], rbx
0x140033ce5  mov     [rsp-8+arg_18], rdi
0x140033cea  push    rbp
0x140033ceb  mov     rbp, rsp
0x140033cee  sub     rsp, 60h
0x140033cf2  xorps   xmm1, xmm1
0x140033cf5  mov     qword ptr [r8], 0
0x140033cfc  mov     rcx, [rcx+10h]; DeviceObject
0x140033d00  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x140033d04  mov     rdi, r8
0x140033d07  mov     [rbp+DeviceRegKey], 0
0x140033d0f  xorps   xmm0, xmm0
0x140033d12  mov     [rbp+KeyHandle], 0
0x140033d1a  mov     r8d, 20019h; DesiredAccess
0x140033d20  mov     edx, 1; DevInstKeyType
0x140033d25  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140033d29  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x140033d2d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x140033d31  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x140033d35  call    cs:__imp_IoOpenDeviceRegistryKey
0x140033d3c  nop     dword ptr [rax+rax+00h]
0x140033d41  mov     ebx, eax
0x140033d43  test    eax, eax
0x140033d45  js      short loc_140033DC2
0x140033d47  lea     rdx, SourceString; "volmgrx"
0x140033d4e  lea     rcx, [rbp+DestinationString]; DestinationString
0x140033d52  call    cs:__imp_RtlInitUnicodeString
0x140033d59  nop     dword ptr [rax+rax+00h]
0x140033d5e  mov     rax, [rbp+DeviceRegKey]
0x140033d62  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140033d66  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140033d6a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140033d6e  lea     rax, [rbp+DestinationString]
0x140033d72  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140033d79  xorps   xmm0, xmm0
0x140033d7c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140033d80  mov     edx, 0F003Fh; DesiredAccess
0x140033d85  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140033d8c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140033d91  call    cs:__imp_ZwOpenKey
0x140033d98  nop     dword ptr [rax+rax+00h]
0x140033d9d  mov     rcx, [rbp+DeviceRegKey]; Handle
0x140033da1  mov     ebx, eax
0x140033da3  call    cs:__imp_ZwClose
0x140033daa  nop     dword ptr [rax+rax+00h]
0x140033daf  test    ebx, ebx
0x140033db1  js      short loc_140033DC2
0x140033db3  mov     rax, [rbp+KeyHandle]
0x140033db7  xor     ecx, ecx
0x140033db9  mov     [rdi], rax
0x140033dbc  mov     [rbp+KeyHandle], rcx
0x140033dc0  jmp     short loc_140033DC6
0x140033dc2  mov     rcx, [rbp+KeyHandle]; Handle
0x140033dc6  test    rcx, rcx
0x140033dc9  jz      short loc_140033DD7
0x140033dcb  call    cs:__imp_ZwClose
0x140033dd2  nop     dword ptr [rax+rax+00h]
0x140033dd7  lea     r11, [rsp+60h+var_s0]
0x140033ddc  mov     eax, ebx
0x140033dde  mov     rbx, [r11+18h]
0x140033de2  mov     rdi, [r11+28h]
0x140033de6  mov     rsp, r11
0x140033de9  pop     rbp
0x140033dea  retn
```
