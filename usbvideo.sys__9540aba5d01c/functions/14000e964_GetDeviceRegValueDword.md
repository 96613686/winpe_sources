# GetDeviceRegValueDword

- ea: `0x14000e964`
- end: `0x14000ec3e`
- name: `GetDeviceRegValueDword`
- size: `730`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e8a8`
- `0x1400156a0`
- `0x14001d244`
- `0x14001d4e0`
- `0x140021fb4`

## callees

- `0x14000e964`
- `0x14001b118`
- `0x14001e184`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000ea38`
- `ntoskrnl!ZwClose` at `0x14000ea38`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e9fa`
- `ntoskrnl!ZwQueryValueKey` at `0x14000eb98`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e9fa`
- `ntoskrnl!ZwQueryValueKey` at `0x14000eb98`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14000e9b5`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14000e9b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e9d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e9d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea51`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000eaba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000eaba`

## pseudocode

```c
__int64 __fastcall GetDeviceRegValueDword(struct _DEVICE_OBJECT *a1, ULONG a2, const WCHAR *a3, _DWORD *a4)
{
  void *v4; // rsi
  NTSTATUS v7; // ebx
  NTSTATUS v8; // eax
  PDEVICE_OBJECT v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  size_t v13; // rbx
  _DWORD *PoolWithTag; // rax
  _DWORD *v15; // rdi
  __int64 v16; // r9
  void *DeviceRegKey; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+20h] BYREF

  v4 = 0;
  DeviceRegKey = 0;
  ResultLength = 0;
  DestinationString = 0;
  if ( a1 && a2 - 1 <= 1 )
  {
    v7 = IoOpenDeviceRegistryKey(a1, a2, 0xF003Fu, &DeviceRegKey);
    if ( v7 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_8;
      v11 = 66;
      v12 = (unsigned int)v7;
      goto LABEL_24;
    }
    RtlInitUnicodeString(&DestinationString, a3);
    v8 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
    v7 = -1073741772;
    if ( !ResultLength )
      goto LABEL_7;
    if ( v8 == -1073741772 )
    {
      v7 = -1073741772;
LABEL_7:
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_8;
      v11 = 67;
      v12 = 3221225524LL;
      goto LABEL_24;
    }
    v13 = ResultLength;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, ResultLength, 0x56425355u);
    v15 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported || !PoolWithTag )
    {
      v4 = PoolWithTag;
      if ( !PoolWithTag )
      {
        v7 = -1073741670;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          goto LABEL_8;
        v11 = 68;
        v12 = 3221225626LL;
        goto LABEL_24;
      }
    }
    else
    {
      memset(PoolWithTag, 0, v13);
      v4 = v15;
    }
    v7 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, v15, ResultLength, &ResultLength);
    if ( v7 >= 0 )
    {
      if ( v15[2] == 4 )
      {
        v16 = (unsigned int)v15[3];
        *a4 = v16;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, v16);
        goto LABEL_8;
      }
      v7 = -1073741811;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v11 = 69;
        v12 = 3221225485LL;
LABEL_24:
        WPP_SF_d(v9->AttachedDevice, v11, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, v12);
      }
    }
  }
  else
  {
    v7 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      return (unsigned int)v7;
    WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice);
  }
LABEL_8:
  if ( DeviceRegKey )
    ZwClose(DeviceRegKey);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x56425355u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000e964  mov     [rsp-18h+arg_8], rbx
0x14000e969  mov     [rsp-18h+arg_10], rsi
0x14000e96e  push    rbp
0x14000e96f  push    rdi
0x14000e970  push    r14
0x14000e972  mov     rbp, rsp
0x14000e975  sub     rsp, 50h
0x14000e979  xor     esi, esi
0x14000e97b  mov     [rbp+DeviceRegKey], 0
0x14000e983  mov     [rbp+arg_0], esi
0x14000e986  xorps   xmm0, xmm0
0x14000e989  mov     r14, r9
0x14000e98c  mov     rdi, r8
0x14000e98f  mov     r10, rcx
0x14000e992  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e996  test    rcx, rcx
0x14000e999  jz      loc_14000EA5F
0x14000e99f  lea     eax, [rdx-1]
0x14000e9a2  cmp     eax, 1
0x14000e9a5  ja      loc_14000EA5F
0x14000e9ab  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x14000e9af  mov     r8d, 0F003Fh; DesiredAccess
0x14000e9b5  call    cs:__imp_IoOpenDeviceRegistryKey
0x14000e9bc  nop     dword ptr [rax+rax+00h]
0x14000e9c1  mov     ebx, eax
0x14000e9c3  test    eax, eax
0x14000e9c5  js      loc_14000EB13
0x14000e9cb  mov     rdx, rdi; SourceString
0x14000e9ce  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e9d2  call    cs:__imp_RtlInitUnicodeString
0x14000e9d9  nop     dword ptr [rax+rax+00h]
0x14000e9de  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x14000e9e2  lea     rax, [rbp+arg_0]
0x14000e9e6  mov     [rsp+50h+ResultLength], rax; ResultLength
0x14000e9eb  lea     r8d, [rsi+2]; KeyValueInformationClass
0x14000e9ef  xor     r9d, r9d; KeyValueInformation
0x14000e9f2  mov     [rsp+50h+Length], esi; Length
0x14000e9f6  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e9fa  call    cs:__imp_ZwQueryValueKey
0x14000ea01  nop     dword ptr [rax+rax+00h]
0x14000ea06  mov     ecx, [rbp+arg_0]
0x14000ea09  mov     ebx, 0C0000034h
0x14000ea0e  test    ecx, ecx
0x14000ea10  jz      short loc_14000EA1C
0x14000ea12  cmp     eax, ebx
0x14000ea14  jnz     loc_14000EAA9
0x14000ea1a  mov     ebx, eax
0x14000ea1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea23  lea     rax, WPP_GLOBAL_Control
0x14000ea2a  cmp     rcx, rax
0x14000ea2d  jnz     short loc_14000EA93
0x14000ea2f  mov     rcx, [rbp+DeviceRegKey]; Handle
0x14000ea33  test    rcx, rcx
0x14000ea36  jz      short loc_14000EA44
0x14000ea38  call    cs:__imp_ZwClose
0x14000ea3f  nop     dword ptr [rax+rax+00h]
0x14000ea44  test    rsi, rsi
0x14000ea47  jz      short loc_14000EA7B
0x14000ea49  mov     edx, 56425355h; Tag
0x14000ea4e  mov     rcx, rsi; P
0x14000ea51  call    cs:__imp_ExFreePoolWithTag
0x14000ea58  nop     dword ptr [rax+rax+00h]
0x14000ea5d  jmp     short loc_14000EA7B
0x14000ea5f  mov     ebx, 0C000000Dh
0x14000ea64  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea6b  lea     rax, WPP_GLOBAL_Control
0x14000ea72  cmp     rcx, rax
0x14000ea75  jnz     loc_14000EC21
0x14000ea7b  lea     r11, [rsp+50h+var_s0]
0x14000ea80  mov     eax, ebx
0x14000ea82  mov     rbx, [r11+28h]
0x14000ea86  mov     rsi, [r11+30h]
0x14000ea8a  mov     rsp, r11
0x14000ea8d  pop     r14
0x14000ea8f  pop     rdi
0x14000ea90  pop     rbp
0x14000ea91  retn
0x14000ea93  cmp     byte ptr [rcx+29h], 4
0x14000ea97  jb      short loc_14000EA2F
0x14000ea99  mov     edx, 43h ; 'C'
0x14000ea9e  mov     r9d, 0C0000034h
0x14000eaa4  jmp     loc_14000EB49
0x14000eaa9  mov     rbx, rcx
0x14000eaac  mov     rdx, rcx; NumberOfBytes
0x14000eaaf  mov     ecx, 401h; PoolType
0x14000eab4  mov     r8d, 56425355h; Tag
0x14000eaba  call    cs:__imp_ExAllocatePoolWithTag
0x14000eac1  nop     dword ptr [rax+rax+00h]
0x14000eac6  cmp     cs:ExPoolZeroingNativelySupported, sil
0x14000eacd  mov     rdi, rax
0x14000ead0  jz      loc_14000EB5E
0x14000ead6  mov     rsi, rdi
0x14000ead9  test    rdi, rdi
0x14000eadc  jnz     loc_14000EB77
0x14000eae2  mov     ebx, 0C000009Ah
0x14000eae7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eaee  lea     rax, WPP_GLOBAL_Control
0x14000eaf5  cmp     rcx, rax
0x14000eaf8  jz      loc_14000EA2F
0x14000eafe  cmp     byte ptr [rcx+29h], 4
0x14000eb02  jb      loc_14000EA2F
0x14000eb08  lea     edx, [rdi+44h]
0x14000eb0b  mov     r9d, 0C000009Ah
0x14000eb11  jmp     short loc_14000EB49
0x14000eb13  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb1a  lea     rax, WPP_GLOBAL_Control
0x14000eb21  cmp     rcx, rax
0x14000eb24  jz      loc_14000EA2F
0x14000eb2a  cmp     byte ptr [rcx+29h], 4
0x14000eb2e  jb      loc_14000EA2F
0x14000eb34  mov     edx, 42h ; 'B'
0x14000eb39  mov     r9d, ebx
0x14000eb3c  jmp     short loc_14000EB49
0x14000eb3e  mov     edx, 45h ; 'E'
0x14000eb43  mov     r9d, 0C000000Dh
0x14000eb49  mov     rcx, [rcx+18h]
0x14000eb4d  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14000eb54  call    WPP_SF_d
0x14000eb59  jmp     loc_14000EA2F
0x14000eb5e  test    rdi, rdi
0x14000eb61  jz      loc_14000EAD6
0x14000eb67  mov     r8, rbx; Size
0x14000eb6a  xor     edx, edx; Val
0x14000eb6c  mov     rcx, rdi; void *
0x14000eb6f  call    memset
0x14000eb74  mov     rsi, rdi
0x14000eb77  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x14000eb7b  lea     rax, [rbp+arg_0]
0x14000eb7f  mov     [rsp+50h+ResultLength], rax; ResultLength
0x14000eb84  lea     rdx, [rbp+DestinationString]; ValueName
0x14000eb88  mov     eax, [rbp+arg_0]
0x14000eb8b  mov     r9, rdi; KeyValueInformation
0x14000eb8e  mov     r8d, 2; KeyValueInformationClass
0x14000eb94  mov     [rsp+50h+Length], eax; Length
0x14000eb98  call    cs:__imp_ZwQueryValueKey
0x14000eb9f  nop     dword ptr [rax+rax+00h]
0x14000eba4  mov     ebx, eax
0x14000eba6  test    eax, eax
0x14000eba8  js      loc_14000EA2F
0x14000ebae  cmp     dword ptr [rdi+8], 4
0x14000ebb2  jz      short loc_14000EBDF
0x14000ebb4  mov     ebx, 0C000000Dh
0x14000ebb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ebc0  lea     rax, WPP_GLOBAL_Control
0x14000ebc7  cmp     rcx, rax
0x14000ebca  jz      loc_14000EA2F
0x14000ebd0  cmp     byte ptr [rcx+29h], 4
0x14000ebd4  jb      loc_14000EA2F
0x14000ebda  jmp     loc_14000EB3E
0x14000ebdf  mov     r9d, [rdi+0Ch]
0x14000ebe3  mov     [r14], r9d
0x14000ebe6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ebed  lea     rax, WPP_GLOBAL_Control
0x14000ebf4  cmp     rcx, rax
0x14000ebf7  jz      loc_14000EA2F
0x14000ebfd  cmp     byte ptr [rcx+29h], 4
0x14000ec01  jb      loc_14000EA2F
0x14000ec07  mov     rcx, [rcx+18h]
0x14000ec0b  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14000ec12  mov     edx, 46h ; 'F'
0x14000ec17  call    WPP_SF_d
0x14000ec1c  jmp     loc_14000EA2F
0x14000ec21  cmp     byte ptr [rcx+29h], 4
0x14000ec25  jb      loc_14000EA7B
0x14000ec2b  mov     rcx, [rcx+18h]
0x14000ec2f  mov     qword ptr [rsp+50h+Length], r10
0x14000ec34  call    WPP_SF_Dq
0x14000ec39  jmp     loc_14000EA2F
```
