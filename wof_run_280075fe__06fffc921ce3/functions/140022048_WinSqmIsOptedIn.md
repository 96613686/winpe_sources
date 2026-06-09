# WinSqmIsOptedIn

- ea: `0x140022048`
- end: `0x14002221a`
- name: `WinSqmIsOptedIn`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002e760`

## callees

- `0x140011560`
- `0x140022048`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400220f3`
- `ntoskrnl!ZwOpenKey` at `0x14002219b`
- `ntoskrnl!ZwOpenKey` at `0x1400220f3`
- `ntoskrnl!ZwOpenKey` at `0x14002219b`
- `ntoskrnl!ZwClose` at `0x140022140`
- `ntoskrnl!ZwClose` at `0x14002215c`
- `ntoskrnl!ZwClose` at `0x1400221ee`
- `ntoskrnl!ZwClose` at `0x140022140`
- `ntoskrnl!ZwClose` at `0x14002215c`
- `ntoskrnl!ZwClose` at `0x1400221ee`
- `ntoskrnl!ZwQueryValueKey` at `0x140022120`
- `ntoskrnl!ZwQueryValueKey` at `0x1400221ca`
- `ntoskrnl!ZwQueryValueKey` at `0x140022120`
- `ntoskrnl!ZwQueryValueKey` at `0x1400221ca`

## string_xrefs

- `0x14002209b`: `\Registry\Machine\Software\Microsoft\SQMClient\Windows`
- `0x140022084`: `\Registry\Machine\Software\Policies\Microsoft\SQMClient\Windows`

## pseudocode

```c
bool WinSqmIsOptedIn()
{
  void *KeyHandle; // [rsp+30h] [rbp-39h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v4[2]; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v5[2]; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+A0h] [rbp+37h] BYREF
  int v8; // [rsp+B0h] [rbp+47h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v8 = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v4[0] = 8388734;
  v4[1] = L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\SQMClient\\Windows";
  v5[0] = 7209068;
  v5[1] = L"\\Registry\\Machine\\Software\\Microsoft\\SQMClient\\Windows";
  *(_QWORD *)&ValueName.Length = 1441812;
  ValueName.Buffer = L"CEIPEnable";
  KeyHandle = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v4;
  KeyValueInformation = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength) >= 0
      && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      goto LABEL_4;
    }
    ZwClose(KeyHandle);
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v5;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength) >= 0
      && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
LABEL_4:
      ZwClose(KeyHandle);
      return HIDWORD(KeyValueInformation) == 1;
    }
    ZwClose(KeyHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x140022048  mov     [rsp-8+arg_0], rdi
0x14002204d  push    rbp
0x14002204e  lea     rbp, [rsp-57h]
0x140022053  sub     rsp, 0C0h
0x14002205a  mov     rax, cs:__security_cookie
0x140022061  xor     rax, rsp
0x140022064  mov     [rbp+57h+var_8], rax
0x140022068  xor     eax, eax
0x14002206a  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140022072  mov     [rbp+57h+var_10], eax
0x140022075  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140022079  xorps   xmm0, xmm0
0x14002207c  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140022084  lea     rax, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Policies"...
0x14002208b  mov     [rbp+57h+var_70], 80007Eh
0x140022093  mov     [rbp+57h+var_68], rax
0x140022097  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002209b  lea     rax, aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x1400220a2  mov     [rbp+57h+var_60], 6E006Ch
0x1400220aa  mov     [rbp+57h+var_58], rax
0x1400220ae  mov     edx, 20019h; DesiredAccess
0x1400220b3  lea     rax, aCeipenable; "CEIPEnable"
0x1400220ba  mov     qword ptr [rbp+57h+ValueName.Length], 160014h
0x1400220c2  mov     [rbp+57h+ValueName.Buffer], rax
0x1400220c6  mov     edi, 14h
0x1400220cb  lea     rax, [rbp+57h+var_70]
0x1400220cf  mov     [rbp+57h+KeyHandle], 0
0x1400220d7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400220db  movups  [rbp+57h+KeyValueInformation], xmm0
0x1400220df  mov     [rbp+57h+var_88], 0
0x1400220e6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400220ee  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400220f3  call    cs:__imp_ZwOpenKey
0x1400220fa  nop     dword ptr [rax+rax+00h]
0x1400220ff  test    eax, eax
0x140022101  js      short loc_140022168
0x140022103  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140022107  lea     rax, [rbp+57h+var_88]
0x14002210b  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140022110  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140022114  lea     r8d, [rdi-12h]; KeyValueInformationClass
0x140022118  mov     [rsp+0C0h+Length], edi; Length
0x14002211c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140022120  call    cs:__imp_ZwQueryValueKey
0x140022127  nop     dword ptr [rax+rax+00h]
0x14002212c  test    eax, eax
0x14002212e  js      short loc_140022158
0x140022130  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140022134  jnz     short loc_140022158
0x140022136  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x14002213a  jnz     short loc_140022158
0x14002213c  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140022140  call    cs:__imp_ZwClose
0x140022147  nop     dword ptr [rax+rax+00h]
0x14002214c  cmp     dword ptr [rbp+57h+KeyValueInformation+0Ch], 1
0x140022150  setz    al
0x140022153  jmp     loc_1400221FC
0x140022158  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002215c  call    cs:__imp_ZwClose
0x140022163  nop     dword ptr [rax+rax+00h]
0x140022168  lea     rax, [rbp+57h+var_60]
0x14002216c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140022173  xorps   xmm0, xmm0
0x140022176  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002217a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002217e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140022186  mov     edx, 20019h; DesiredAccess
0x14002218b  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140022192  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140022196  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002219b  call    cs:__imp_ZwOpenKey
0x1400221a2  nop     dword ptr [rax+rax+00h]
0x1400221a7  test    eax, eax
0x1400221a9  js      short loc_1400221FA
0x1400221ab  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400221af  lea     rax, [rbp+57h+var_88]
0x1400221b3  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1400221b8  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400221bc  mov     r8d, 2; KeyValueInformationClass
0x1400221c2  mov     [rsp+0C0h+Length], edi; Length
0x1400221c6  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400221ca  call    cs:__imp_ZwQueryValueKey
0x1400221d1  nop     dword ptr [rax+rax+00h]
0x1400221d6  test    eax, eax
0x1400221d8  js      short loc_1400221EA
0x1400221da  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1400221de  jnz     short loc_1400221EA
0x1400221e0  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x1400221e4  jz      loc_14002213C
0x1400221ea  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400221ee  call    cs:__imp_ZwClose
0x1400221f5  nop     dword ptr [rax+rax+00h]
0x1400221fa  xor     al, al
0x1400221fc  mov     rcx, [rbp+57h+var_8]
0x140022200  xor     rcx, rsp; StackCookie
0x140022203  call    __security_check_cookie
0x140022208  mov     rdi, [rsp+0C0h+arg_0]
0x140022210  add     rsp, 0C0h
0x140022217  pop     rbp
0x140022218  retn
```
