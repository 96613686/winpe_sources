# RaidUnitSetDefaultWriteCachePolicy

- ea: `0x1400cbf18`
- end: `0x1400cc171`
- name: `RaidUnitSetDefaultWriteCachePolicy`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401bcb90`

## callees

- `0x1400cbf18`
- `0x14014b400`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400cbfe2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cbfe2`
- `ntoskrnl!ZwClose` at `0x1400cc128`
- `ntoskrnl!ZwClose` at `0x1400cc13e`
- `ntoskrnl!ZwClose` at `0x1400cc128`
- `ntoskrnl!ZwClose` at `0x1400cc13e`
- `ntoskrnl!ZwOpenKey` at `0x1400cc029`
- `ntoskrnl!ZwOpenKey` at `0x1400cc029`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400cc092`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400cc092`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400cc104`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400cc104`
- `ntoskrnl!ZwCreateKey` at `0x1400cc0c0`
- `ntoskrnl!ZwCreateKey` at `0x1400cc0c0`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400cbfbb`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400cbfbb`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400cbf8d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400cbf8d`

## string_xrefs

- `0x1400cc035`: `UserWriteCacheSetting`

## pseudocode

```c
__int64 __fastcall RaidUnitSetDefaultWriteCachePolicy(__int64 a1)
{
  unsigned int v2; // ebx
  NTSTATUS RegistryValues; // eax
  int ValueData; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  void *DeviceRegKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v10[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v11; // [rsp+A8h] [rbp-58h]
  const WCHAR *v12; // [rsp+B0h] [rbp-50h]
  int *p_ValueData; // [rsp+B8h] [rbp-48h]
  int v14; // [rsp+C0h] [rbp-40h]
  int *v15; // [rsp+C8h] [rbp-38h]
  int v16; // [rsp+D0h] [rbp-30h]

  ValueData = 0;
  DeviceRegKey = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( !a1 || (*(_DWORD *)(a1 + 1952) & 0x10) == 0 )
  {
    v2 = -1056964601;
    goto LABEL_15;
  }
  if ( KeGetCurrentIrql() )
  {
    v2 = -1056964600;
    goto LABEL_15;
  }
  if ( IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(a1 + 8), 1u, 0x2001Fu, &DeviceRegKey) < 0 )
    goto LABEL_6;
  v2 = 0;
  RtlInitUnicodeString(&DestinationString, L"Disk");
  ObjectAttributes.RootDirectory = DeviceRegKey;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes) >= 0 )
  {
    memset_0(v10, 0, 0x150u);
    p_ValueData = &ValueData;
    v11 = 288;
    v15 = &ValueData;
    v12 = L"UserWriteCacheSetting";
    v14 = 67108868;
    v16 = 4;
    RegistryValues = RtlQueryRegistryValuesEx(1073741828, KeyHandle, v10, 0, 0);
    goto LABEL_10;
  }
  RegistryValues = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( RegistryValues < 0 )
  {
LABEL_10:
    if ( RegistryValues != -1073741772 )
      goto LABEL_12;
  }
  ValueData = 1;
  RegistryValues = RtlWriteRegistryValue(0x40000000u, (PCWSTR)KeyHandle, L"UserWriteCacheSetting", 4u, &ValueData, 4u);
LABEL_12:
  if ( RegistryValues < 0 )
LABEL_6:
    v2 = -1056964607;
LABEL_15:
  if ( DeviceRegKey )
    ZwClose(DeviceRegKey);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v2;
}

```

## disassembly

```asm
0x1400cbf18  mov     [rsp-8+arg_8], rbx
0x1400cbf1d  mov     [rsp-8+arg_10], r12
0x1400cbf22  push    rbp
0x1400cbf23  lea     rbp, [rsp-100h]
0x1400cbf2b  sub     rsp, 200h
0x1400cbf32  mov     rax, cs:__security_cookie
0x1400cbf39  xor     rax, rsp
0x1400cbf3c  mov     [rbp+100h+var_10], rax
0x1400cbf43  mov     [rsp+200h+ValueData], 0
0x1400cbf4b  xorps   xmm0, xmm0
0x1400cbf4e  mov     [rsp+200h+DeviceRegKey], 0
0x1400cbf57  mov     rbx, rcx
0x1400cbf5a  mov     [rsp+200h+KeyHandle], 0
0x1400cbf63  movups  xmmword ptr [rsp+200h+ObjectAttributes.Length], xmm0
0x1400cbf68  movups  xmmword ptr [rsp+200h+ObjectAttributes.ObjectName], xmm0
0x1400cbf6d  movups  xmmword ptr [rsp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400cbf72  movups  xmmword ptr [rbp+100h+DestinationString.Length], xmm0
0x1400cbf76  test    rcx, rcx
0x1400cbf79  jz      loc_1400CC119
0x1400cbf7f  mov     eax, [rcx+7A0h]
0x1400cbf85  test    al, 10h
0x1400cbf87  jz      loc_1400CC119
0x1400cbf8d  call    cs:__imp_KeGetCurrentIrql
0x1400cbf94  nop     dword ptr [rax+rax+00h]
0x1400cbf99  test    al, al
0x1400cbf9b  jz      short loc_1400CBFA7
0x1400cbf9d  mov     ebx, 0C1000008h
0x1400cbfa2  jmp     loc_1400CC11E
0x1400cbfa7  mov     rcx, [rbx+8]; DeviceObject
0x1400cbfab  lea     r9, [rsp+200h+DeviceRegKey]; DeviceRegKey
0x1400cbfb0  mov     edx, 1; DevInstKeyType
0x1400cbfb5  mov     r8d, 2001Fh; DesiredAccess
0x1400cbfbb  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400cbfc2  nop     dword ptr [rax+rax+00h]
0x1400cbfc7  test    eax, eax
0x1400cbfc9  jns     short loc_1400CBFD5
0x1400cbfcb  mov     ebx, 0C1000001h
0x1400cbfd0  jmp     loc_1400CC11E
0x1400cbfd5  lea     rdx, aDisk; "Disk"
0x1400cbfdc  xor     ebx, ebx
0x1400cbfde  lea     rcx, [rbp+100h+DestinationString]; DestinationString
0x1400cbfe2  call    cs:__imp_RtlInitUnicodeString
0x1400cbfe9  nop     dword ptr [rax+rax+00h]
0x1400cbfee  mov     rax, [rsp+200h+DeviceRegKey]
0x1400cbff3  lea     r8, [rsp+200h+ObjectAttributes]; ObjectAttributes
0x1400cbff8  mov     [rsp+200h+ObjectAttributes.RootDirectory], rax
0x1400cbffd  lea     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x1400cc002  lea     rax, [rbp+100h+DestinationString]
0x1400cc006  mov     [rsp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400cc00e  xorps   xmm0, xmm0
0x1400cc011  mov     [rsp+200h+ObjectAttributes.ObjectName], rax
0x1400cc016  mov     edx, 2001Fh; DesiredAccess
0x1400cc01b  mov     [rsp+200h+ObjectAttributes.Attributes], 240h
0x1400cc023  movdqu  xmmword ptr [rsp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400cc029  call    cs:__imp_ZwOpenKey
0x1400cc030  nop     dword ptr [rax+rax+00h]
0x1400cc035  lea     r12, ValueName; "UserWriteCacheSetting"
0x1400cc03c  test    eax, eax
0x1400cc03e  js      short loc_1400CC0A0
0x1400cc040  xor     edx, edx; Val
0x1400cc042  lea     rcx, [rbp+100h+var_160]; void *
0x1400cc046  mov     r8d, 150h; Size
0x1400cc04c  call    memset_0
0x1400cc051  mov     rdx, [rsp+200h+KeyHandle]
0x1400cc056  lea     rax, [rsp+200h+ValueData]
0x1400cc05b  mov     [rbp+100h+var_148], rax
0x1400cc05f  lea     r8, [rbp+100h+var_160]
0x1400cc063  lea     rax, [rsp+200h+ValueData]
0x1400cc068  mov     [rbp+100h+var_158], 120h
0x1400cc06f  xor     r9d, r9d
0x1400cc072  mov     [rbp+100h+var_138], rax
0x1400cc076  mov     ecx, 40000004h
0x1400cc07b  mov     [rbp+100h+var_150], r12
0x1400cc07f  mov     [rbp+100h+var_140], 4000004h
0x1400cc086  mov     [rbp+100h+var_130], 4
0x1400cc08d  mov     [rsp+200h+Class], rbx
0x1400cc092  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400cc099  nop     dword ptr [rax+rax+00h]
0x1400cc09e  jmp     short loc_1400CC0D0
0x1400cc0a0  mov     [rsp+200h+Disposition], rbx; Disposition
0x1400cc0a5  lea     r8, [rsp+200h+ObjectAttributes]; ObjectAttributes
0x1400cc0aa  mov     [rsp+200h+CreateOptions], ebx; CreateOptions
0x1400cc0ae  lea     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x1400cc0b3  xor     r9d, r9d; TitleIndex
0x1400cc0b6  mov     [rsp+200h+Class], rbx; Class
0x1400cc0bb  mov     edx, 2001Fh; DesiredAccess
0x1400cc0c0  call    cs:__imp_ZwCreateKey
0x1400cc0c7  nop     dword ptr [rax+rax+00h]
0x1400cc0cc  test    eax, eax
0x1400cc0ce  jns     short loc_1400CC0D7
0x1400cc0d0  cmp     eax, 0C0000034h
0x1400cc0d5  jnz     short loc_1400CC110
0x1400cc0d7  mov     rdx, [rsp+200h+KeyHandle]; Path
0x1400cc0dc  lea     rax, [rsp+200h+ValueData]
0x1400cc0e1  mov     [rsp+200h+CreateOptions], 4; ValueLength
0x1400cc0e9  mov     r9d, 4; ValueType
0x1400cc0ef  mov     r8, r12; ValueName
0x1400cc0f2  mov     [rsp+200h+Class], rax; ValueData
0x1400cc0f7  mov     ecx, 40000000h; RelativeTo
0x1400cc0fc  mov     [rsp+200h+ValueData], 1
0x1400cc104  call    cs:__imp_RtlWriteRegistryValue
0x1400cc10b  nop     dword ptr [rax+rax+00h]
0x1400cc110  test    eax, eax
0x1400cc112  jns     short loc_1400CC11E
0x1400cc114  jmp     loc_1400CBFCB
0x1400cc119  mov     ebx, 0C1000007h
0x1400cc11e  mov     rcx, [rsp+200h+DeviceRegKey]; Handle
0x1400cc123  test    rcx, rcx
0x1400cc126  jz      short loc_1400CC134
0x1400cc128  call    cs:__imp_ZwClose
0x1400cc12f  nop     dword ptr [rax+rax+00h]
0x1400cc134  mov     rcx, [rsp+200h+KeyHandle]; Handle
0x1400cc139  test    rcx, rcx
0x1400cc13c  jz      short loc_1400CC14A
0x1400cc13e  call    cs:__imp_ZwClose
0x1400cc145  nop     dword ptr [rax+rax+00h]
0x1400cc14a  mov     eax, ebx
0x1400cc14c  mov     rcx, [rbp+100h+var_10]
0x1400cc153  xor     rcx, rsp; StackCookie
0x1400cc156  call    __security_check_cookie
0x1400cc15b  lea     r11, [rsp+200h+var_s0]
0x1400cc163  mov     rbx, [r11+18h]
0x1400cc167  mov     r12, [r11+20h]
0x1400cc16b  mov     rsp, r11
0x1400cc16e  pop     rbp
0x1400cc16f  retn
```
