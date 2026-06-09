# VhdmpiOpenGlobalPolicyKey

- ea: `0x1400d1228`
- end: `0x1400d1325`
- name: `VhdmpiOpenGlobalPolicyKey`
- size: `253`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400b88dc`
- `0x1400c92e4`
- `0x1400d132c`
- `0x1400ee9dc`

## callees

- `0x1400d1228`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400d127e`
- `ntoskrnl!ZwOpenKey` at `0x1400d12d9`
- `ntoskrnl!ZwOpenKey` at `0x1400d127e`
- `ntoskrnl!ZwOpenKey` at `0x1400d12d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d129b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d129b`
- `ntoskrnl!ZwClose` at `0x1400d130d`
- `ntoskrnl!ZwClose` at `0x1400d130d`

## pseudocode

```c
__int64 __fastcall VhdmpiOpenGlobalPolicyKey(void **a1, void **a2)
{
  NTSTATUS v4; // ebx
  void *v5; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+38h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &StringOut;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v4 < 0 )
    goto LABEL_6;
  RtlInitUnicodeString(&DestinationString, L"Parameters");
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(a2, 0x20019u, &ObjectAttributes);
  if ( v4 < 0 )
  {
    v4 = 0;
    *a2 = 0;
  }
  if ( a1 )
  {
    v5 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
  else
  {
LABEL_6:
    v5 = KeyHandle;
  }
  if ( v5 )
    ZwClose(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400d1228  push    rbp
0x1400d122a  push    rbx
0x1400d122b  push    rsi
0x1400d122c  push    rdi
0x1400d122d  mov     rbp, rsp
0x1400d1230  sub     rsp, 68h
0x1400d1234  xorps   xmm0, xmm0
0x1400d1237  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400d123f  mov     rsi, rdx
0x1400d1242  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400d124a  mov     rdi, rcx
0x1400d124d  mov     [rbp+KeyHandle], 0
0x1400d1255  lea     rax, StringOut
0x1400d125c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400d1264  mov     edx, 20019h; DesiredAccess
0x1400d1269  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400d126d  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400d1271  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400d1275  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400d1279  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d127e  call    cs:__imp_ZwOpenKey
0x1400d1285  nop     dword ptr [rax+rax+00h]
0x1400d128a  mov     ebx, eax
0x1400d128c  test    eax, eax
0x1400d128e  js      short loc_1400D1304
0x1400d1290  lea     rdx, aParameters; "Parameters"
0x1400d1297  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400d129b  call    cs:__imp_RtlInitUnicodeString
0x1400d12a2  nop     dword ptr [rax+rax+00h]
0x1400d12a7  mov     rax, [rbp+KeyHandle]
0x1400d12ab  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400d12af  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400d12b3  xorps   xmm0, xmm0
0x1400d12b6  lea     rax, [rbp+DestinationString]
0x1400d12ba  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400d12c1  mov     edx, 20019h; DesiredAccess
0x1400d12c6  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400d12ca  mov     rcx, rsi; KeyHandle
0x1400d12cd  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400d12d4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d12d9  call    cs:__imp_ZwOpenKey
0x1400d12e0  nop     dword ptr [rax+rax+00h]
0x1400d12e5  mov     ebx, eax
0x1400d12e7  test    eax, eax
0x1400d12e9  jns     short loc_1400D12F0
0x1400d12eb  xor     ebx, ebx
0x1400d12ed  mov     [rsi], rbx
0x1400d12f0  test    rdi, rdi
0x1400d12f3  jz      short loc_1400D1304
0x1400d12f5  mov     rax, [rbp+KeyHandle]
0x1400d12f9  xor     ecx, ecx
0x1400d12fb  mov     [rdi], rax
0x1400d12fe  mov     [rbp+KeyHandle], rcx
0x1400d1302  jmp     short loc_1400D1308
0x1400d1304  mov     rcx, [rbp+KeyHandle]; Handle
0x1400d1308  test    rcx, rcx
0x1400d130b  jz      short loc_1400D1319
0x1400d130d  call    cs:__imp_ZwClose
0x1400d1314  nop     dword ptr [rax+rax+00h]
0x1400d1319  mov     eax, ebx
0x1400d131b  add     rsp, 68h
0x1400d131f  pop     rdi
0x1400d1320  pop     rsi
0x1400d1321  pop     rbx
0x1400d1322  pop     rbp
0x1400d1323  retn
```
