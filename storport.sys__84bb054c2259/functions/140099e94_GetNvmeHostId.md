# GetNvmeHostId

- ea: `0x140099e94`
- end: `0x14009a07d`
- name: `GetNvmeHostId`
- size: `489`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400a0970`
- `0x140106930`
- `0x14012e1a4`
- `0x1401a4f9c`

## callees

- `0x140099e94`
- `0x14014b400`
- `0x14014bd20`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140099f2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140099f8f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140099f2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140099f8f`
- `ntoskrnl!ExUuidCreate` at `0x140099ff7`
- `ntoskrnl!ExUuidCreate` at `0x140099ff7`
- `ntoskrnl!ZwClose` at `0x14009a043`
- `ntoskrnl!ZwClose` at `0x14009a043`
- `ntoskrnl!ZwOpenKey` at `0x140099f6d`
- `ntoskrnl!ZwOpenKey` at `0x140099f6d`
- `ntoskrnl!ZwQueryValueKey` at `0x140099fc1`
- `ntoskrnl!ZwQueryValueKey` at `0x140099fc1`
- `ntoskrnl!ZwSetValueKey` at `0x14009a029`
- `ntoskrnl!ZwSetValueKey` at `0x14009a029`

## string_xrefs

- `0x140099f20`: `\Registry\Machine\System\CurrentControlSet\Control\StorPort\`

## pseudocode

```c
__int64 __fastcall GetNvmeHostId(_OWORD *a1)
{
  NTSTATUS v2; // ebx
  void *KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  __int128 Buf2; // [rsp+90h] [rbp-70h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v11; // [rsp+A4h] [rbp-5Ch]
  int v12; // [rsp+A8h] [rbp-58h]
  UUID v13; // [rsp+ACh] [rbp-54h]

  KeyHandle = 0;
  ResultLength = 0;
  *a1 = 0;
  v2 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  ValueName = 0;
  Buf2 = 0;
  if ( memcmp(&NvmeHostId, &Buf2, 0x10u) )
    goto LABEL_13;
  if ( NvmeHostIdChecked )
    return (unsigned int)-1073741275;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\StorPort\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"NvmeHostId");
    v2 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x110u, &ResultLength);
    if ( v2 < 0 )
    {
      v2 = ExUuidCreate(&NvmeHostId);
      if ( v2 >= 0 )
        v2 = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, (PVOID)&NvmeHostId, 0x10u);
    }
    else if ( v11 == 3 && v12 == 16 )
    {
      NvmeHostId = v13;
    }
    else
    {
      v2 = -1073739509;
    }
    NvmeHostIdChecked = 1;
    ZwClose(KeyHandle);
    if ( v2 >= 0 )
LABEL_13:
      *a1 = NvmeHostId;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140099e94  push    rbp
0x140099e96  push    rbx
0x140099e97  push    rdi
0x140099e98  push    r15
0x140099e9a  lea     rbp, [rsp-0C8h]
0x140099ea2  sub     rsp, 1C8h
0x140099ea9  mov     rax, cs:__security_cookie
0x140099eb0  xor     rax, rsp
0x140099eb3  mov     [rbp+0E0h+var_30], rax
0x140099eba  xorps   xmm0, xmm0
0x140099ebd  lea     r15, NvmeHostId
0x140099ec4  xor     eax, eax
0x140099ec6  lea     rdx, [rbp+0E0h+Buf2]; Buf2
0x140099eca  mov     rdi, rcx
0x140099ecd  mov     [rsp+1E0h+KeyHandle], rax
0x140099ed2  xorps   xmm1, xmm1
0x140099ed5  mov     [rsp+1E0h+var_1A8], eax
0x140099ed9  movups  xmmword ptr [rcx], xmm0
0x140099edc  lea     r8d, [rax+10h]; Size
0x140099ee0  mov     rcx, r15; Buf1
0x140099ee3  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.ObjectName], xmm0
0x140099ee8  xor     ebx, ebx
0x140099eea  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x140099eee  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.Length], xmm0
0x140099ef3  movups  xmmword ptr [rsp+1E0h+ObjectAttributes+1Ch], xmm0
0x140099ef8  movups  xmmword ptr [rsp+1E0h+ValueName.Length], xmm0
0x140099efd  movups  [rbp+0E0h+Buf2], xmm1
0x140099f01  call    memcmp
0x140099f06  test    eax, eax
0x140099f08  jnz     loc_14009A053
0x140099f0e  cmp     cs:NvmeHostIdChecked, bl
0x140099f14  jz      short loc_140099F20
0x140099f16  mov     ebx, 0C0000225h
0x140099f1b  jmp     loc_14009A05E
0x140099f20  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x140099f27  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x140099f2b  call    cs:__imp_RtlInitUnicodeString
0x140099f32  nop     dword ptr [rax+rax+00h]
0x140099f37  lea     rax, [rbp+0E0h+DestinationString]
0x140099f3b  mov     [rsp+1E0h+ObjectAttributes.Length], 30h ; '0'
0x140099f43  xorps   xmm0, xmm0
0x140099f46  mov     [rsp+1E0h+ObjectAttributes.ObjectName], rax
0x140099f4b  lea     r8, [rsp+1E0h+ObjectAttributes]; ObjectAttributes
0x140099f50  mov     [rsp+1E0h+ObjectAttributes.RootDirectory], rbx
0x140099f55  mov     edx, 2001Fh; DesiredAccess
0x140099f5a  mov     [rsp+1E0h+ObjectAttributes.Attributes], 240h
0x140099f62  lea     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x140099f67  movdqu  xmmword ptr [rsp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140099f6d  call    cs:__imp_ZwOpenKey
0x140099f74  nop     dword ptr [rax+rax+00h]
0x140099f79  mov     ebx, eax
0x140099f7b  test    eax, eax
0x140099f7d  js      loc_14009A05E
0x140099f83  lea     rdx, aNvmehostid; "NvmeHostId"
0x140099f8a  lea     rcx, [rsp+1E0h+ValueName]; DestinationString
0x140099f8f  call    cs:__imp_RtlInitUnicodeString
0x140099f96  nop     dword ptr [rax+rax+00h]
0x140099f9b  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x140099fa0  lea     rax, [rsp+1E0h+var_1A8]
0x140099fa5  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x140099faa  lea     r9, [rbp+0E0h+KeyValueInformation]; KeyValueInformation
0x140099fae  mov     r8d, 2; KeyValueInformationClass
0x140099fb4  mov     [rsp+1E0h+Length], 110h; Length
0x140099fbc  lea     rdx, [rsp+1E0h+ValueName]; ValueName
0x140099fc1  call    cs:__imp_ZwQueryValueKey
0x140099fc8  nop     dword ptr [rax+rax+00h]
0x140099fcd  mov     ebx, eax
0x140099fcf  test    eax, eax
0x140099fd1  js      short loc_140099FF4
0x140099fd3  cmp     [rbp+0E0h+var_13C], 3
0x140099fd7  jnz     short loc_140099FED
0x140099fd9  cmp     [rbp+0E0h+var_138], 10h
0x140099fdd  jnz     short loc_140099FED
0x140099fdf  movups  xmm0, [rbp+0E0h+var_134]
0x140099fe3  movdqu  xmmword ptr cs:NvmeHostId.Data1, xmm0
0x140099feb  jmp     short loc_14009A037
0x140099fed  mov     ebx, 0C000090Bh
0x140099ff2  jmp     short loc_14009A037
0x140099ff4  mov     rcx, r15; Uuid
0x140099ff7  call    cs:__imp_ExUuidCreate
0x140099ffe  nop     dword ptr [rax+rax+00h]
0x14009a003  mov     ebx, eax
0x14009a005  test    eax, eax
0x14009a007  js      short loc_14009A037
0x14009a009  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x14009a00e  lea     rdx, [rsp+1E0h+ValueName]; ValueName
0x14009a013  mov     dword ptr [rsp+1E0h+ResultLength], 10h; DataSize
0x14009a01b  mov     r9d, 3; Type
0x14009a021  xor     r8d, r8d; TitleIndex
0x14009a024  mov     qword ptr [rsp+1E0h+Length], r15; Data
0x14009a029  call    cs:__imp_ZwSetValueKey
0x14009a030  nop     dword ptr [rax+rax+00h]
0x14009a035  mov     ebx, eax
0x14009a037  mov     rcx, [rsp+1E0h+KeyHandle]; Handle
0x14009a03c  mov     cs:NvmeHostIdChecked, 1
0x14009a043  call    cs:__imp_ZwClose
0x14009a04a  nop     dword ptr [rax+rax+00h]
0x14009a04f  test    ebx, ebx
0x14009a051  js      short loc_14009A05E
0x14009a053  movups  xmm0, xmmword ptr cs:NvmeHostId.Data1
0x14009a05a  movdqu  xmmword ptr [rdi], xmm0
0x14009a05e  mov     eax, ebx
0x14009a060  mov     rcx, [rbp+0E0h+var_30]
0x14009a067  xor     rcx, rsp; StackCookie
0x14009a06a  call    __security_check_cookie
0x14009a06f  add     rsp, 1C8h
0x14009a076  pop     r15
0x14009a078  pop     rdi
0x14009a079  pop     rbx
0x14009a07a  pop     rbp
0x14009a07b  retn
```
