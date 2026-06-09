# DvReadRegistryValueUINT32

- ea: `0x1400115cc`
- end: `0x1400116cf`
- name: `DvReadRegistryValueUINT32`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020080`

## callees

- `0x1400115cc`
- `0x140011e90`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001168c`
- `ntoskrnl!ZwClose` at `0x14001168c`
- `ntoskrnl!ZwQueryValueKey` at `0x14001165e`
- `ntoskrnl!ZwQueryValueKey` at `0x14001165e`
- `ntoskrnl!ZwOpenKey` at `0x14001162a`
- `ntoskrnl!ZwOpenKey` at `0x14001162a`

## pseudocode

```c
__int64 __fastcall DvReadRegistryValueUINT32(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, _DWORD *a3)
{
  NTSTATUS v5; // ebx
  NTSTATUS v6; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-9h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+70h] [rbp+27h] BYREF
  int v12; // [rsp+74h] [rbp+2Bh]
  int v13; // [rsp+78h] [rbp+2Fh]
  int v14; // [rsp+7Ch] [rbp+33h]

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v5 < 0 )
    return (unsigned int)v5;
  v6 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, KeyValueInformation, 0x10u, &ResultLength);
  v5 = v6;
  if ( v6 >= 0 )
  {
    if ( v12 != 4 || v13 != 4 )
      goto LABEL_5;
    v5 = 0;
    *a3 = v14;
  }
  else if ( v6 == -1073741789 || v6 == -2147483643 )
  {
LABEL_5:
    v5 = -1073741788;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400115cc  mov     [rsp-8+arg_18], rbx
0x1400115d1  push    rbp
0x1400115d2  push    rsi
0x1400115d3  push    rdi
0x1400115d4  lea     rbp, [rsp-47h]
0x1400115d9  sub     rsp, 90h
0x1400115e0  mov     rax, cs:__security_cookie
0x1400115e7  xor     rax, rsp
0x1400115ea  mov     [rbp+57h+var_20], rax
0x1400115ee  xor     eax, eax
0x1400115f0  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x1400115f4  mov     rdi, r8
0x1400115f7  mov     [rbp+57h+KeyHandle], rax
0x1400115fb  mov     rsi, rdx
0x1400115fe  mov     [rbp+57h+var_70], eax
0x140011601  xorps   xmm0, xmm0
0x140011604  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140011608  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001160c  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140011614  mov     edx, 20019h; DesiredAccess
0x140011619  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140011621  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011625  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001162a  call    cs:__imp_ZwOpenKey
0x140011631  nop     dword ptr [rax+rax+00h]
0x140011636  mov     ebx, eax
0x140011638  test    eax, eax
0x14001163a  js      short loc_140011698
0x14001163c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011640  lea     rax, [rbp+57h+var_70]
0x140011644  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140011649  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14001164d  mov     r8d, 2; KeyValueInformationClass
0x140011653  mov     [rsp+0A0h+Length], 10h; Length
0x14001165b  mov     rdx, rsi; ValueName
0x14001165e  call    cs:__imp_ZwQueryValueKey
0x140011665  nop     dword ptr [rax+rax+00h]
0x14001166a  mov     ebx, eax
0x14001166c  test    eax, eax
0x14001166e  jns     short loc_1400116BA
0x140011670  cmp     eax, 0C0000023h
0x140011675  jz      short loc_14001167E
0x140011677  cmp     eax, 80000005h
0x14001167c  jnz     short loc_140011683
0x14001167e  mov     ebx, 0C0000024h
0x140011683  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140011687  test    rcx, rcx
0x14001168a  jz      short loc_140011698
0x14001168c  call    cs:__imp_ZwClose
0x140011693  nop     dword ptr [rax+rax+00h]
0x140011698  mov     eax, ebx
0x14001169a  mov     rcx, [rbp+57h+var_20]
0x14001169e  xor     rcx, rsp; StackCookie
0x1400116a1  call    __security_check_cookie
0x1400116a6  mov     rbx, [rsp+0A0h+arg_18]
0x1400116ae  add     rsp, 90h
0x1400116b5  pop     rdi
0x1400116b6  pop     rsi
0x1400116b7  pop     rbp
0x1400116b8  retn
0x1400116ba  cmp     [rbp+57h+var_2C], 4
0x1400116be  jnz     short loc_14001167E
0x1400116c0  cmp     [rbp+57h+var_28], 4
0x1400116c4  jnz     short loc_14001167E
0x1400116c6  mov     eax, [rbp+57h+var_24]
0x1400116c9  xor     ebx, ebx
0x1400116cb  mov     [rdi], eax
0x1400116cd  jmp     short loc_140011683
```
