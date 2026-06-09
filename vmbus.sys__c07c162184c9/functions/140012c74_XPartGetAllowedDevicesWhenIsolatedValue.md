# XPartGetAllowedDevicesWhenIsolatedValue

- ea: `0x140012c74`
- end: `0x140012d78`
- name: `XPartGetAllowedDevicesWhenIsolatedValue`
- size: `260`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002e0bc`

## callees

- `0x140012c74`
- `0x140017000`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140012d4a`
- `ntoskrnl!ZwClose` at `0x140012d4a`
- `ntoskrnl!ZwOpenKey` at `0x140012cdb`
- `ntoskrnl!ZwOpenKey` at `0x140012cdb`
- `ntoskrnl!ZwQueryValueKey` at `0x140012d0f`
- `ntoskrnl!ZwQueryValueKey` at `0x140012d0f`

## pseudocode

```c
__int64 __fastcall XPartGetAllowedDevicesWhenIsolatedValue(PUNICODE_STRING ValueName, _DWORD *a2)
{
  NTSTATUS v4; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-9h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+70h] [rbp+27h] BYREF
  int v10; // [rsp+74h] [rbp+2Bh]
  int v11; // [rsp+78h] [rbp+2Fh]
  int v12; // [rsp+7Ch] [rbp+33h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a2 = 0;
  ResultLength = 0;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_14001C208;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    v4 = ZwQueryValueKey(KeyHandle, ValueName, KeyValuePartialInformation, KeyValueInformation, 0x10u, &ResultLength);
    if ( v4 >= 0 )
    {
      if ( ResultLength >= 0x10 && v10 == 4 && v11 == 4 )
      {
        v4 = 0;
        *a2 = v12;
      }
      else
      {
        v4 = -1073741788;
      }
    }
    if ( KeyHandle )
      ZwClose(KeyHandle);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140012c74  mov     [rsp-8+arg_10], rbx
0x140012c79  push    rbp
0x140012c7a  push    rsi
0x140012c7b  push    rdi
0x140012c7c  lea     rbp, [rsp-47h]
0x140012c81  sub     rsp, 90h
0x140012c88  mov     rax, cs:__security_cookie
0x140012c8f  xor     rax, rsp
0x140012c92  mov     [rbp+57h+var_20], rax
0x140012c96  xor     eax, eax
0x140012c98  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012ca0  mov     [rdx], eax
0x140012ca2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140012ca6  mov     [rbp+57h+var_70], eax
0x140012ca9  mov     rdi, rdx
0x140012cac  mov     [rbp+57h+KeyHandle], rax
0x140012cb0  mov     rsi, rcx
0x140012cb3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140012cb7  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140012cbb  lea     rax, qword_14001C208
0x140012cc2  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140012cca  xorps   xmm0, xmm0
0x140012ccd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140012cd1  mov     edx, 20019h; DesiredAccess
0x140012cd6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012cdb  call    cs:__imp_ZwOpenKey
0x140012ce2  nop     dword ptr [rax+rax+00h]
0x140012ce7  mov     ebx, eax
0x140012ce9  test    eax, eax
0x140012ceb  js      short loc_140012D56
0x140012ced  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140012cf1  lea     rax, [rbp+57h+var_70]
0x140012cf5  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140012cfa  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140012cfe  mov     r8d, 2; KeyValueInformationClass
0x140012d04  mov     [rsp+0A0h+Length], 10h; Length
0x140012d0c  mov     rdx, rsi; ValueName
0x140012d0f  call    cs:__imp_ZwQueryValueKey
0x140012d16  nop     dword ptr [rax+rax+00h]
0x140012d1b  mov     ebx, eax
0x140012d1d  test    eax, eax
0x140012d1f  js      short loc_140012D41
0x140012d21  cmp     [rbp+57h+var_70], 10h
0x140012d25  jb      short loc_140012D3C
0x140012d27  cmp     [rbp+57h+var_2C], 4
0x140012d2b  jnz     short loc_140012D3C
0x140012d2d  cmp     [rbp+57h+var_28], 4
0x140012d31  jnz     short loc_140012D3C
0x140012d33  mov     eax, [rbp+57h+var_24]
0x140012d36  xor     ebx, ebx
0x140012d38  mov     [rdi], eax
0x140012d3a  jmp     short loc_140012D41
0x140012d3c  mov     ebx, 0C0000024h
0x140012d41  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140012d45  test    rcx, rcx
0x140012d48  jz      short loc_140012D56
0x140012d4a  call    cs:__imp_ZwClose
0x140012d51  nop     dword ptr [rax+rax+00h]
0x140012d56  mov     eax, ebx
0x140012d58  mov     rcx, [rbp+57h+var_20]
0x140012d5c  xor     rcx, rsp; StackCookie
0x140012d5f  call    __security_check_cookie
0x140012d64  mov     rbx, [rsp+0A0h+arg_10]
0x140012d6c  add     rsp, 90h
0x140012d73  pop     rdi
0x140012d74  pop     rsi
0x140012d75  pop     rbp
0x140012d76  retn
```
