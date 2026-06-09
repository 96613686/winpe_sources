# CmRegUtilOpenExistingWstrKey

- ea: `0x140019528`
- end: `0x1400195ad`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140018cb8`
- `0x140019034`

## callees

- `0x140004f04`
- `0x140019528`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140019587`
- `ntoskrnl!ZwOpenKey` at `0x140019587`

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
0x140019528  mov     [rsp-8+arg_0], rbx
0x14001952d  push    rbp
0x14001952e  mov     rbp, rsp
0x140019531  sub     rsp, 70h
0x140019535  mov     r11, rcx
0x140019538  xorps   xmm0, xmm0
0x14001953b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001953f  mov     rbx, r9
0x140019542  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140019546  mov     r10d, r8d
0x140019549  call    WdmlibRtlInitUnicodeStringEx
0x14001954e  test    eax, eax
0x140019550  js      short loc_14001959E
0x140019552  xor     eax, eax
0x140019554  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001955c  mov     [rbp+KeyHandle], rax
0x140019560  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140019564  mov     [rbx], rax
0x140019567  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14001956b  lea     rax, [rbp+DestinationString]
0x14001956f  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140019577  mov     edx, r10d; DesiredAccess
0x14001957a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001957e  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x140019582  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140019587  call    cs:__imp_ZwOpenKey
0x14001958e  nop     dword ptr [rax+rax+00h]
0x140019593  test    eax, eax
0x140019595  js      short loc_14001959E
0x140019597  mov     rcx, [rbp+KeyHandle]
0x14001959b  mov     [rbx], rcx
0x14001959e  mov     rbx, [rsp+70h+arg_0]
0x1400195a6  add     rsp, 70h
0x1400195aa  pop     rbp
0x1400195ab  retn
```
