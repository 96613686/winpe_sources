# PortRegistryReadDeviceKey

- ea: `0x1401bdbe8`
- end: `0x1401bddc9`
- name: `PortRegistryReadDeviceKey`
- size: `481`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *KeyHandle)`
- caller_count: `10`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400491a0`
- `0x14004d380`
- `0x14004ff90`
- `0x1400979a0`
- `0x1400c9914`
- `0x1400e7314`
- `0x14011a004`
- `0x140139620`
- `0x14018f540`
- `0x1401a86a8`

## callees

- `0x14014b440`
- `0x14014b800`
- `0x1401bdbe8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1401bdd24`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401bdd24`
- `ntoskrnl!ZwClose` at `0x1401bdd80`
- `ntoskrnl!ZwClose` at `0x1401bdd91`
- `ntoskrnl!ZwClose` at `0x1401bdd80`
- `ntoskrnl!ZwClose` at `0x1401bdd91`
- `ntoskrnl!ZwCreateKey` at `0x1401bdc9e`
- `ntoskrnl!ZwCreateKey` at `0x1401bdc9e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1401bdd35`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1401bdd35`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1401bdd58`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1401bdc29`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1401bdc29`

## string_xrefs

- `0x1401bdcf7`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall PortRegistryReadDeviceKey(
        struct _DEVICE_OBJECT *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *KeyHandle)
{
  _DWORD *v6; // r14
  __int64 v7; // r12
  int v10; // r15d
  NTSTATUS v11; // edi
  _DWORD *v12; // rdi
  PVOID SystemRoutineAddress; // rax
  NTSTATUS v14; // eax
  void *DeviceRegKey; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  void *v20; // [rsp+A0h] [rbp-60h] BYREF
  int v21; // [rsp+A8h] [rbp-58h]
  __int64 v22; // [rsp+B0h] [rbp-50h]
  __int128 *v23; // [rsp+B8h] [rbp-48h]
  int v24; // [rsp+C0h] [rbp-40h]
  __int64 v25; // [rsp+C8h] [rbp-38h]
  int v26; // [rsp+D0h] [rbp-30h]

  v6 = KeyHandle;
  v7 = a4;
  DeviceRegKey = 0;
  v10 = *KeyHandle;
  v11 = IoOpenDeviceRegistryKey(a1, 1u, 0x20019u, &DeviceRegKey);
  if ( v11 < 0 )
    return (unsigned int)v11;
  v12 = DeviceRegKey;
  KeyHandle = 0;
  v17 = 0;
  if ( !a2 )
  {
    KeyHandle = DeviceRegKey;
    goto LABEL_5;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = DeviceRegKey;
  ObjectAttributes.ObjectName = a2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwCreateKey((PHANDLE)&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v11 >= 0 )
  {
    v12 = KeyHandle;
LABEL_5:
    DWORD2(v17) = v10;
    *(_QWORD *)&v17 = *a5;
    memset_0(&v20, 0, 0x70u);
    v21 = 20;
    v24 = 0;
    v20 = &PortpRegQueryRoutine;
    v22 = *(_QWORD *)(a3 + 8);
    v25 = 0;
    v23 = &v17;
    v26 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    v14 = ((__int64 (__fastcall *)(__int64, _DWORD *, void **, __int64, _QWORD))SystemRoutineAddress)(
            0x40000000,
            v12,
            &v20,
            v7,
            0);
    v10 = DWORD2(v17);
    v11 = v14;
    *a5 = v17;
    if ( a2 )
      ZwClose(KeyHandle);
  }
  ZwClose(DeviceRegKey);
  if ( v11 >= 0 )
    *v6 = v10;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1401bdbe8  push    rbp
0x1401bdbea  push    rbx
0x1401bdbeb  push    rsi
0x1401bdbec  push    rdi
0x1401bdbed  push    r12
0x1401bdbef  push    r13
0x1401bdbf1  push    r14
0x1401bdbf3  push    r15
0x1401bdbf5  lea     rbp, [rsp-18h]
0x1401bdbfa  sub     rsp, 118h
0x1401bdc01  mov     r14, [rbp+50h+KeyHandle]
0x1401bdc08  xor     ebx, ebx
0x1401bdc0a  mov     r12d, r9d
0x1401bdc0d  mov     r13, r8
0x1401bdc10  mov     rsi, rdx
0x1401bdc13  mov     [rsp+150h+DeviceRegKey], rbx
0x1401bdc18  lea     r9, [rsp+150h+DeviceRegKey]; DeviceRegKey
0x1401bdc1d  mov     r8d, 20019h; DesiredAccess
0x1401bdc23  mov     r15d, [r14]
0x1401bdc26  lea     edx, [rbx+1]; DevInstKeyType
0x1401bdc29  call    cs:__imp_IoOpenDeviceRegistryKey
0x1401bdc30  nop     dword ptr [rax+rax+00h]
0x1401bdc35  mov     edi, eax
0x1401bdc37  test    eax, eax
0x1401bdc39  js      loc_1401BDDA1
0x1401bdc3f  mov     rdi, [rsp+150h+DeviceRegKey]
0x1401bdc44  xorps   xmm0, xmm0
0x1401bdc47  mov     [rbp+50h+KeyHandle], rbx
0x1401bdc4e  movups  [rsp+150h+var_108], xmm0
0x1401bdc53  test    rsi, rsi
0x1401bdc56  jz      loc_1401BDDB8
0x1401bdc5c  mov     [rsp+150h+Disposition], rbx; Disposition
0x1401bdc61  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1401bdc66  mov     [rsp+150h+CreateOptions], ebx; CreateOptions
0x1401bdc6a  lea     rcx, [rbp+50h+KeyHandle]; KeyHandle
0x1401bdc71  xor     r9d, r9d; TitleIndex
0x1401bdc74  mov     [rsp+150h+Class], rbx; Class
0x1401bdc79  mov     edx, 2001Fh; DesiredAccess
0x1401bdc7e  mov     qword ptr [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1401bdc87  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 240h
0x1401bdc8f  mov     [rsp+150h+ObjectAttributes.RootDirectory], rdi
0x1401bdc94  mov     [rsp+150h+ObjectAttributes.ObjectName], rsi
0x1401bdc99  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401bdc9e  call    cs:__imp_ZwCreateKey
0x1401bdca5  nop     dword ptr [rax+rax+00h]
0x1401bdcaa  mov     edi, eax
0x1401bdcac  test    eax, eax
0x1401bdcae  js      loc_1401BDD8C
0x1401bdcb4  mov     rdi, [rbp+50h+KeyHandle]
0x1401bdcbb  mov     rbx, [rbp+50h+arg_20]
0x1401bdcc2  lea     rcx, [rbp+50h+var_B0]; void *
0x1401bdcc6  xor     edx, edx; Val
0x1401bdcc8  mov     dword ptr [rsp+150h+var_108+8], r15d
0x1401bdccd  mov     rax, [rbx]
0x1401bdcd0  lea     r8d, [rdx+70h]; Size
0x1401bdcd4  mov     qword ptr [rsp+150h+var_108], rax
0x1401bdcd9  call    memset_0
0x1401bdcde  xor     r15d, r15d
0x1401bdce1  mov     [rbp+50h+var_A8], 14h
0x1401bdce8  lea     rax, PortpRegQueryRoutine
0x1401bdcef  mov     [rbp+50h+var_90], r15d
0x1401bdcf3  mov     [rbp+50h+var_B0], rax
0x1401bdcf7  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x1401bdcfe  mov     rax, [r13+8]
0x1401bdd02  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1401bdd07  mov     [rbp+50h+var_A0], rax
0x1401bdd0b  xorps   xmm0, xmm0
0x1401bdd0e  lea     rax, [rsp+150h+var_108]
0x1401bdd13  mov     [rbp+50h+var_88], r15
0x1401bdd17  mov     [rbp+50h+var_98], rax
0x1401bdd1b  mov     [rbp+50h+var_80], r15d
0x1401bdd1f  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x1401bdd24  call    cs:__imp_RtlInitUnicodeString
0x1401bdd2b  nop     dword ptr [rax+rax+00h]
0x1401bdd30  lea     rcx, [rsp+150h+DestinationString]; SystemRoutineName
0x1401bdd35  call    cs:__imp_MmGetSystemRoutineAddress
0x1401bdd3c  nop     dword ptr [rax+rax+00h]
0x1401bdd41  mov     r9, r12
0x1401bdd44  mov     [rsp+150h+Class], r15
0x1401bdd49  test    rax, rax
0x1401bdd4c  lea     r8, [rbp+50h+var_B0]
0x1401bdd50  mov     rdx, rdi
0x1401bdd53  mov     ecx, 40000000h
0x1401bdd58  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1401bdd60  call    _guard_dispatch_icall
0x1401bdd65  mov     r15d, dword ptr [rsp+150h+var_108+8]
0x1401bdd6a  mov     edi, eax
0x1401bdd6c  mov     rax, qword ptr [rsp+150h+var_108]
0x1401bdd71  mov     [rbx], rax
0x1401bdd74  test    rsi, rsi
0x1401bdd77  jz      short loc_1401BDD8C
0x1401bdd79  mov     rcx, [rbp+50h+KeyHandle]; Handle
0x1401bdd80  call    cs:__imp_ZwClose
0x1401bdd87  nop     dword ptr [rax+rax+00h]
0x1401bdd8c  mov     rcx, [rsp+150h+DeviceRegKey]; Handle
0x1401bdd91  call    cs:__imp_ZwClose
0x1401bdd98  nop     dword ptr [rax+rax+00h]
0x1401bdd9d  test    edi, edi
0x1401bdd9f  jns     short loc_1401BDDC4
0x1401bdda1  mov     eax, edi
0x1401bdda3  add     rsp, 118h
0x1401bddaa  pop     r15
0x1401bddac  pop     r14
0x1401bddae  pop     r13
0x1401bddb0  pop     r12
0x1401bddb2  pop     rdi
0x1401bddb3  pop     rsi
0x1401bddb4  pop     rbx
0x1401bddb5  pop     rbp
0x1401bddb6  retn
0x1401bddb8  mov     [rbp+50h+KeyHandle], rdi
0x1401bddbf  jmp     loc_1401BDCBB
0x1401bddc4  mov     [r14], r15d
0x1401bddc7  jmp     short loc_1401BDDA1
```
