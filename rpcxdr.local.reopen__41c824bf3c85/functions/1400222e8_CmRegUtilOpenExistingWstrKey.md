# CmRegUtilOpenExistingWstrKey

- ea: `0x1400222e8`
- end: `0x14002236d`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140021a78`
- `0x140021df4`

## callees

- `0x1400120a8`
- `0x1400222e8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140022347`
- `ntoskrnl!ZwOpenKey` at `0x140022347`

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
0x1400222e8  mov     [rsp-8+arg_0], rbx
0x1400222ed  push    rbp
0x1400222ee  mov     rbp, rsp
0x1400222f1  sub     rsp, 70h
0x1400222f5  mov     r11, rcx
0x1400222f8  xorps   xmm0, xmm0
0x1400222fb  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400222ff  mov     rbx, r9
0x140022302  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140022306  mov     r10d, r8d
0x140022309  call    WdmlibRtlInitUnicodeStringEx
0x14002230e  test    eax, eax
0x140022310  js      short loc_14002235E
0x140022312  xor     eax, eax
0x140022314  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002231c  mov     [rbp+KeyHandle], rax
0x140022320  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140022324  mov     [rbx], rax
0x140022327  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14002232b  lea     rax, [rbp+DestinationString]
0x14002232f  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140022337  mov     edx, r10d; DesiredAccess
0x14002233a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14002233e  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x140022342  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140022347  call    cs:__imp_ZwOpenKey
0x14002234e  nop     dword ptr [rax+rax+00h]
0x140022353  test    eax, eax
0x140022355  js      short loc_14002235E
0x140022357  mov     rcx, [rbp+KeyHandle]
0x14002235b  mov     [rbx], rcx
0x14002235e  mov     rbx, [rsp+70h+arg_0]
0x140022366  add     rsp, 70h
0x14002236a  pop     rbp
0x14002236b  retn
```
