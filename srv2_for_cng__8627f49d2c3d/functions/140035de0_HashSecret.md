# HashSecret

- ea: `0x140035de0`
- end: `0x140035fd6`
- name: `HashSecret`
- size: `502`
- prototype: `__int64 __fastcall(__int64, __int64, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036530`

## callees

- `0x140035de0`
- `0x1400375fc`
- `0x140038490`
- `0x140038980`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140035e4a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035ea9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035e4a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035ea9`
- `ntoskrnl!ExAllocatePool2` at `0x140035f06`
- `ntoskrnl!ExAllocatePool2` at `0x140035f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035fab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035fab`
- `ntoskrnl!ZwOpenKey` at `0x140035e87`
- `ntoskrnl!ZwOpenKey` at `0x140035e87`
- `ntoskrnl!ZwQueryValueKey` at `0x140035ed5`
- `ntoskrnl!ZwQueryValueKey` at `0x140035f49`
- `ntoskrnl!ZwQueryValueKey` at `0x140035ed5`
- `ntoskrnl!ZwQueryValueKey` at `0x140035f49`
- `ntoskrnl!NtClose` at `0x140035f92`
- `ntoskrnl!NtClose` at `0x140035f92`
- `ksecdd!BCryptHashData` at `0x140035f69`
- `ksecdd!BCryptHashData` at `0x140035f69`

## string_xrefs

- `0x140035e20`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\PeerDist\SecurityManager\Restricted`

## pseudocode

```c
__int64 __fastcall HashSecret(__int64 a1, __int64 a2, void *a3, __int64 a4, _OWORD *a5)
{
  _BYTE *Pool2; // rdi
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  _BYTE *v9; // rsi
  ULONG ResultLength; // [rsp+30h] [rbp-91h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-89h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-81h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-71h] BYREF
  _BYTE KeyValueInformation[80]; // [rsp+80h] [rbp-41h] BYREF

  memset(KeyValueInformation, 0, 0x4Cu);
  KeyHandle = 0;
  Pool2 = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist\\SecurityManager\\Restricted");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( !v7 )
  {
    RtlInitUnicodeString(&DestinationString, L"Seed");
    v8 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x4Cu,
           &ResultLength);
    v7 = v8;
    if ( v8 == -2147483643 || v8 == -1073741789 )
    {
      Pool2 = (_BYTE *)ExAllocatePool2(256, ResultLength, 1752392008);
      if ( !Pool2 )
      {
        v7 = -1073741801;
        goto LABEL_11;
      }
      v9 = Pool2;
      v7 = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             Pool2,
             ResultLength,
             &ResultLength);
    }
    else
    {
      v9 = KeyValueInformation;
    }
    if ( !v7 )
    {
      v7 = BCryptHashData(a3, v9 + 12, *((_DWORD *)v9 + 2), 0);
      if ( !v7 )
        v7 = DeDupFinishHash(a3, a5);
    }
  }
LABEL_11:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x68736148u);
  return v7;
}

```

## disassembly

```asm
0x140035de0  push    rbp
0x140035de2  push    rbx
0x140035de3  push    rsi
0x140035de4  push    rdi
0x140035de5  push    r14
0x140035de7  push    r15
0x140035de9  lea     rbp, [rsp-27h]
0x140035dee  sub     rsp, 0E8h
0x140035df5  mov     rax, cs:__security_cookie
0x140035dfc  xor     rax, rsp
0x140035dff  mov     [rbp+4Fh+var_40], rax
0x140035e03  mov     r15, [rbp+4Fh+arg_20]
0x140035e07  lea     rcx, [rbp+4Fh+KeyValueInformation]; void *
0x140035e0b  mov     r14, r8
0x140035e0e  mov     esi, 4Ch ; 'L'
0x140035e13  mov     r8d, esi; Size
0x140035e16  xor     edx, edx; Val
0x140035e18  call    memset
0x140035e1d  xorps   xmm0, xmm0
0x140035e20  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x140035e27  xor     eax, eax
0x140035e29  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x140035e2e  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x140035e32  mov     [rsp+110h+KeyHandle], rax
0x140035e37  xor     edi, edi
0x140035e39  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x140035e3d  mov     [rsp+110h+var_E0], eax
0x140035e41  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x140035e46  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x140035e4a  call    cs:__imp_RtlInitUnicodeString
0x140035e51  nop     dword ptr [rax+rax+00h]
0x140035e56  lea     rax, [rsp+110h+DestinationString]
0x140035e5b  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x140035e62  xorps   xmm0, xmm0
0x140035e65  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x140035e69  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x140035e6d  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rdi
0x140035e71  mov     edx, 20019h; DesiredAccess
0x140035e76  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x140035e7d  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x140035e82  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140035e87  call    cs:__imp_ZwOpenKey
0x140035e8e  nop     dword ptr [rax+rax+00h]
0x140035e93  mov     ebx, eax
0x140035e95  test    eax, eax
0x140035e97  jnz     loc_140035F88
0x140035e9d  lea     rdx, aSeed; "Seed"
0x140035ea4  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x140035ea9  call    cs:__imp_RtlInitUnicodeString
0x140035eb0  nop     dword ptr [rax+rax+00h]
0x140035eb5  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x140035eba  lea     rax, [rsp+110h+var_E0]
0x140035ebf  mov     [rsp+110h+ResultLength], rax; ResultLength
0x140035ec4  lea     r9, [rbp+4Fh+KeyValueInformation]; KeyValueInformation
0x140035ec8  lea     r8d, [rsi-4Ah]; KeyValueInformationClass
0x140035ecc  mov     [rsp+110h+Length], esi; Length
0x140035ed0  lea     rdx, [rsp+110h+DestinationString]; ValueName
0x140035ed5  call    cs:__imp_ZwQueryValueKey
0x140035edc  nop     dword ptr [rax+rax+00h]
0x140035ee1  mov     ebx, eax
0x140035ee3  cmp     eax, 80000005h
0x140035ee8  jz      short loc_140035EF7
0x140035eea  cmp     eax, 0C0000023h
0x140035eef  jz      short loc_140035EF7
0x140035ef1  lea     rsi, [rbp+4Fh+KeyValueInformation]
0x140035ef5  jmp     short loc_140035F57
0x140035ef7  mov     edx, [rsp+110h+var_E0]
0x140035efb  mov     ecx, 100h
0x140035f00  mov     r8d, 68736148h
0x140035f06  call    cs:__imp_ExAllocatePool2
0x140035f0d  nop     dword ptr [rax+rax+00h]
0x140035f12  mov     rdi, rax
0x140035f15  test    rax, rax
0x140035f18  jnz     short loc_140035F21
0x140035f1a  mov     ebx, 0C0000017h
0x140035f1f  jmp     short loc_140035F88
0x140035f21  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x140035f26  lea     rax, [rsp+110h+var_E0]
0x140035f2b  mov     [rsp+110h+ResultLength], rax; ResultLength
0x140035f30  lea     rdx, [rsp+110h+DestinationString]; ValueName
0x140035f35  mov     eax, [rsp+110h+var_E0]
0x140035f39  mov     r9, rdi; KeyValueInformation
0x140035f3c  mov     r8d, 2; KeyValueInformationClass
0x140035f42  mov     [rsp+110h+Length], eax; Length
0x140035f46  mov     rsi, rdi
0x140035f49  call    cs:__imp_ZwQueryValueKey
0x140035f50  nop     dword ptr [rax+rax+00h]
0x140035f55  mov     ebx, eax
0x140035f57  test    ebx, ebx
0x140035f59  jnz     short loc_140035F88
0x140035f5b  mov     r8d, [rsi+8]; cbInput
0x140035f5f  lea     rdx, [rsi+0Ch]; pbInput
0x140035f63  xor     r9d, r9d; dwFlags
0x140035f66  mov     rcx, r14; hHash
0x140035f69  call    cs:__imp_BCryptHashData
0x140035f70  nop     dword ptr [rax+rax+00h]
0x140035f75  mov     ebx, eax
0x140035f77  test    eax, eax
0x140035f79  jnz     short loc_140035F88
0x140035f7b  mov     rdx, r15
0x140035f7e  mov     rcx, r14
0x140035f81  call    DeDupFinishHash
0x140035f86  mov     ebx, eax
0x140035f88  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x140035f8d  test    rcx, rcx
0x140035f90  jz      short loc_140035F9E
0x140035f92  call    cs:__imp_NtClose
0x140035f99  nop     dword ptr [rax+rax+00h]
0x140035f9e  test    rdi, rdi
0x140035fa1  jz      short loc_140035FB7
0x140035fa3  mov     edx, 68736148h; Tag
0x140035fa8  mov     rcx, rdi; P
0x140035fab  call    cs:__imp_ExFreePoolWithTag
0x140035fb2  nop     dword ptr [rax+rax+00h]
0x140035fb7  mov     eax, ebx
0x140035fb9  mov     rcx, [rbp+4Fh+var_40]
0x140035fbd  xor     rcx, rsp; StackCookie
0x140035fc0  call    __security_check_cookie
0x140035fc5  add     rsp, 0E8h
0x140035fcc  pop     r15
0x140035fce  pop     r14
0x140035fd0  pop     rdi
0x140035fd1  pop     rsi
0x140035fd2  pop     rbx
0x140035fd3  pop     rbp
0x140035fd4  retn
```
