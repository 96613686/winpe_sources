# CUsbBusFilter::QueryRegistryData(ushort const *,ushort const *,ulong *)

- ea: `0x1400048d4`
- end: `0x140004a11`
- name: `?QueryRegistryData@CUsbBusFilter@@SAJPEBG0PEAK@Z`
- size: `317`
- prototype: `__int64 __fastcall(PCWSTR SourceString, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003acc`
- `0x14000818c`
- `0x140008ad8`

## callees

- `0x1400048d4`
- `0x14000a9f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400049eb`
- `ntoskrnl!ZwClose` at `0x1400049eb`
- `ntoskrnl!ZwQueryValueKey` at `0x1400049b0`
- `ntoskrnl!ZwQueryValueKey` at `0x1400049b0`
- `ntoskrnl!ZwOpenKey` at `0x14000497b`
- `ntoskrnl!ZwOpenKey` at `0x14000497b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004929`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000493c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004929`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000493c`

## pseudocode

```c
__int64 __fastcall CUsbBusFilter::QueryRegistryData(PCWSTR SourceString, const unsigned __int16 *a2, unsigned int *a3)
{
  NTSTATUS v5; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING v9; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+27h] BYREF

  ResultLength = 0;
  KeyHandle = 0;
  v9 = 0;
  DestinationString = 0;
  KeyValueInformation = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, a2);
  RtlInitUnicodeString(&v9, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v9;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 640;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    v5 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &ResultLength);
    if ( v5 >= 0 )
    {
      if ( ResultLength == 16 && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
      {
        v5 = 0;
        *a3 = HIDWORD(KeyValueInformation);
      }
      else
      {
        v5 = -1073741811;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400048d4  push    rbp
0x1400048d6  push    rbx
0x1400048d7  push    rdi
0x1400048d8  lea     rbp, [rsp-47h]
0x1400048dd  sub     rsp, 0B0h
0x1400048e4  mov     rax, cs:__security_cookie
0x1400048eb  xor     rax, rsp
0x1400048ee  mov     [rbp+57h+var_20], rax
0x1400048f2  xorps   xmm0, xmm0
0x1400048f5  mov     [rbp+57h+var_90], 0
0x1400048fc  mov     rbx, rcx
0x1400048ff  mov     [rbp+57h+KeyHandle], 0
0x140004907  xorps   xmm1, xmm1
0x14000490a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000490e  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x140004912  mov     rdi, r8
0x140004915  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140004919  movups  [rbp+57h+KeyValueInformation], xmm0
0x14000491d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140004921  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140004925  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140004929  call    cs:__imp_RtlInitUnicodeString
0x140004930  nop     dword ptr [rax+rax+00h]
0x140004935  mov     rdx, rbx; SourceString
0x140004938  lea     rcx, [rbp+57h+var_80]; DestinationString
0x14000493c  call    cs:__imp_RtlInitUnicodeString
0x140004943  nop     dword ptr [rax+rax+00h]
0x140004948  lea     rax, [rbp+57h+var_80]
0x14000494c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140004953  xorps   xmm0, xmm0
0x140004956  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000495a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000495e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140004966  mov     edx, 80000000h; DesiredAccess
0x14000496b  mov     [rbp+57h+ObjectAttributes.Attributes], 280h
0x140004972  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140004976  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000497b  call    cs:__imp_ZwOpenKey
0x140004982  nop     dword ptr [rax+rax+00h]
0x140004987  mov     ebx, eax
0x140004989  test    eax, eax
0x14000498b  js      short loc_1400049E2
0x14000498d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140004991  lea     rax, [rbp+57h+var_90]
0x140004995  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14000499a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000499e  mov     r8d, 2; KeyValueInformationClass
0x1400049a4  mov     [rsp+0C0h+Length], 10h; Length
0x1400049ac  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400049b0  call    cs:__imp_ZwQueryValueKey
0x1400049b7  nop     dword ptr [rax+rax+00h]
0x1400049bc  mov     ebx, eax
0x1400049be  test    eax, eax
0x1400049c0  js      short loc_1400049E2
0x1400049c2  cmp     [rbp+57h+var_90], 10h
0x1400049c6  jnz     short loc_1400049DD
0x1400049c8  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x1400049cc  jnz     short loc_1400049DD
0x1400049ce  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1400049d2  jnz     short loc_1400049DD
0x1400049d4  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1400049d7  xor     ebx, ebx
0x1400049d9  mov     [rdi], eax
0x1400049db  jmp     short loc_1400049E2
0x1400049dd  mov     ebx, 0C000000Dh
0x1400049e2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400049e6  test    rcx, rcx
0x1400049e9  jz      short loc_1400049F7
0x1400049eb  call    cs:__imp_ZwClose
0x1400049f2  nop     dword ptr [rax+rax+00h]
0x1400049f7  mov     eax, ebx
0x1400049f9  mov     rcx, [rbp+57h+var_20]
0x1400049fd  xor     rcx, rsp; StackCookie
0x140004a00  call    __security_check_cookie
0x140004a05  add     rsp, 0B0h
0x140004a0c  pop     rdi
0x140004a0d  pop     rbx
0x140004a0e  pop     rbp
0x140004a0f  retn
```
