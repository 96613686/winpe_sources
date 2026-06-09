# CmRegUtilOpenExistingWstrKey

- ea: `0x1400216f0`
- end: `0x140021775`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140020eb8`
- `0x140021234`

## callees

- `0x140007dc4`
- `0x1400216f0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14002174f`
- `ntoskrnl!ZwOpenKey` at `0x14002174f`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilOpenExistingWstrKey(__int64 a1, const WCHAR *a2, __int64 a3, void **a4)
{
  NTSTATUS result; // eax
  ACCESS_MASK v6; // r10d
  void *v7; // r11
  void *KeyHandle; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF

  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    KeyHandle = 0;
    *a4 = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = v7;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, v6, &ObjectAttributes);
    if ( result >= 0 )
      *a4 = KeyHandle;
  }
  return result;
}

```

## disassembly

```asm
0x1400216f0  mov     [rsp-8+arg_0], rbx
0x1400216f5  push    rbp
0x1400216f6  mov     rbp, rsp
0x1400216f9  sub     rsp, 70h
0x1400216fd  mov     r11, rcx
0x140021700  xorps   xmm0, xmm0
0x140021703  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021707  mov     rbx, r9
0x14002170a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002170e  mov     r10d, r8d
0x140021711  call    WdmlibRtlInitUnicodeStringEx
0x140021716  test    eax, eax
0x140021718  js      short loc_140021766
0x14002171a  xor     eax, eax
0x14002171c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140021724  mov     [rbp+KeyHandle], rax
0x140021728  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002172c  mov     [rbx], rax
0x14002172f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140021733  lea     rax, [rbp+DestinationString]
0x140021737  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14002173f  mov     edx, r10d; DesiredAccess
0x140021742  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140021746  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x14002174a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002174f  call    cs:__imp_ZwOpenKey
0x140021756  nop     dword ptr [rax+rax+00h]
0x14002175b  test    eax, eax
0x14002175d  js      short loc_140021766
0x14002175f  mov     rcx, [rbp+KeyHandle]
0x140021763  mov     [rbx], rcx
0x140021766  mov     rbx, [rsp+70h+arg_0]
0x14002176e  add     rsp, 70h
0x140021772  pop     rbp
0x140021773  retn
```
