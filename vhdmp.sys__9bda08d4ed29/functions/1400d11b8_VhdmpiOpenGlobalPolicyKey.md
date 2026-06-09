# VhdmpiOpenGlobalPolicyKey

- ea: `0x1400d11b8`
- end: `0x1400d12b5`
- name: `VhdmpiOpenGlobalPolicyKey`
- size: `253`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400b88cc`
- `0x1400c92d4`
- `0x1400d12bc`
- `0x1400ee9dc`

## callees

- `0x1400d11b8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400d120e`
- `ntoskrnl!ZwOpenKey` at `0x1400d1269`
- `ntoskrnl!ZwOpenKey` at `0x1400d120e`
- `ntoskrnl!ZwOpenKey` at `0x1400d1269`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d122b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d122b`
- `ntoskrnl!ZwClose` at `0x1400d129d`
- `ntoskrnl!ZwClose` at `0x1400d129d`

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
0x1400d11b8  push    rbp
0x1400d11ba  push    rbx
0x1400d11bb  push    rsi
0x1400d11bc  push    rdi
0x1400d11bd  mov     rbp, rsp
0x1400d11c0  sub     rsp, 68h
0x1400d11c4  xorps   xmm0, xmm0
0x1400d11c7  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400d11cf  mov     rsi, rdx
0x1400d11d2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400d11da  mov     rdi, rcx
0x1400d11dd  mov     [rbp+KeyHandle], 0
0x1400d11e5  lea     rax, StringOut
0x1400d11ec  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400d11f4  mov     edx, 20019h; DesiredAccess
0x1400d11f9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400d11fd  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400d1201  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400d1205  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400d1209  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d120e  call    cs:__imp_ZwOpenKey
0x1400d1215  nop     dword ptr [rax+rax+00h]
0x1400d121a  mov     ebx, eax
0x1400d121c  test    eax, eax
0x1400d121e  js      short loc_1400D1294
0x1400d1220  lea     rdx, aParameters; "Parameters"
0x1400d1227  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400d122b  call    cs:__imp_RtlInitUnicodeString
0x1400d1232  nop     dword ptr [rax+rax+00h]
0x1400d1237  mov     rax, [rbp+KeyHandle]
0x1400d123b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400d123f  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400d1243  xorps   xmm0, xmm0
0x1400d1246  lea     rax, [rbp+DestinationString]
0x1400d124a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400d1251  mov     edx, 20019h; DesiredAccess
0x1400d1256  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400d125a  mov     rcx, rsi; KeyHandle
0x1400d125d  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400d1264  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d1269  call    cs:__imp_ZwOpenKey
0x1400d1270  nop     dword ptr [rax+rax+00h]
0x1400d1275  mov     ebx, eax
0x1400d1277  test    eax, eax
0x1400d1279  jns     short loc_1400D1280
0x1400d127b  xor     ebx, ebx
0x1400d127d  mov     [rsi], rbx
0x1400d1280  test    rdi, rdi
0x1400d1283  jz      short loc_1400D1294
0x1400d1285  mov     rax, [rbp+KeyHandle]
0x1400d1289  xor     ecx, ecx
0x1400d128b  mov     [rdi], rax
0x1400d128e  mov     [rbp+KeyHandle], rcx
0x1400d1292  jmp     short loc_1400D1298
0x1400d1294  mov     rcx, [rbp+KeyHandle]; Handle
0x1400d1298  test    rcx, rcx
0x1400d129b  jz      short loc_1400D12A9
0x1400d129d  call    cs:__imp_ZwClose
0x1400d12a4  nop     dword ptr [rax+rax+00h]
0x1400d12a9  mov     eax, ebx
0x1400d12ab  add     rsp, 68h
0x1400d12af  pop     rdi
0x1400d12b0  pop     rsi
0x1400d12b1  pop     rbx
0x1400d12b2  pop     rbp
0x1400d12b3  retn
```
