# WcSetConfiguration

- ea: `0x140035ed0`
- end: `0x14003609b`
- name: `WcSetConfiguration`
- size: `459`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400351b4`

## callees

- `0x1400020c4`
- `0x140007c60`
- `0x140035ed0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14003606f`
- `ntoskrnl!ZwClose` at `0x14003606f`
- `ntoskrnl!ZwQueryValueKey` at `0x140035fb4`
- `ntoskrnl!ZwQueryValueKey` at `0x140035fb4`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140035f24`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140035f24`

## pseudocode

```c
__int64 __fastcall WcSetConfiguration(__int64 a1)
{
  int v1; // eax
  int v2; // edx
  unsigned int v3; // ebx
  int v4; // r9d
  NTSTATUS v5; // eax
  char v7; // [rsp+30h] [rbp-50h]
  int v8; // [rsp+38h] [rbp-48h]
  ULONG ResultLength; // [rsp+40h] [rbp-40h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-30h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+60h] [rbp-20h] BYREF
  int v13; // [rsp+6Ch] [rbp-14h]

  KeyHandle = 0;
  ValueName.Buffer = L"DebugOptions";
  ResultLength = 0;
  *(_QWORD *)&ValueName.Length = 1703960;
  v1 = IoOpenDriverRegistryKey(a1, 0, 131097, 0, &KeyHandle);
  v3 = v1;
  if ( v1 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_28;
    v8 = v1;
    v4 = 69;
    v7 = 62;
    goto LABEL_4;
  }
  v5 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength);
  v3 = v5;
  if ( v5 >= 0 )
  {
    if ( (v13 & 1) != 0 )
      byte_14000E680 = 1;
    if ( (v13 & 8) != 0 )
      BYTE1(qword_14000E6A2) = 1;
    if ( (v13 & 4) != 0 )
      LOBYTE(qword_14000E6A2) = 1;
    if ( (v13 & 0x40) != 0 )
      BYTE2(qword_14000E6A2) = 1;
    if ( (v13 & 0x10) != 0 )
      HIBYTE(word_14000E6A0) = 1;
    if ( (v13 & 0x20) != 0 )
      BYTE3(qword_14000E6A2) = 1;
    if ( (v13 & 2) != 0 )
      LOBYTE(word_14000E6A0) = 1;
    if ( (v13 & 0x80u) != 0 )
      BYTE4(qword_14000E6A2) = 1;
    if ( (v13 & 0x100) != 0 )
      BYTE5(qword_14000E6A2) = 1;
    if ( (v13 & 0x200) != 0 )
      BYTE6(qword_14000E6A2) = 1;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = v5;
    v4 = 70;
    v7 = 79;
LABEL_4:
    LOBYTE(v2) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v2,
      1,
      v4,
      (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
      v7,
      v8);
  }
LABEL_28:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x140035ed0  mov     [rsp-8+arg_8], rbx
0x140035ed5  push    rbp
0x140035ed6  mov     rbp, rsp
0x140035ed9  sub     rsp, 80h
0x140035ee0  mov     rax, cs:__security_cookie
0x140035ee7  xor     rax, rsp
0x140035eea  mov     [rbp+var_8], rax
0x140035eee  lea     rax, aDebugoptions; "DebugOptions"
0x140035ef5  mov     [rbp+KeyHandle], 0
0x140035efd  mov     [rbp+ValueName.Buffer], rax
0x140035f01  xor     r9d, r9d
0x140035f04  lea     rax, [rbp+KeyHandle]
0x140035f08  mov     [rbp+var_40], 0
0x140035f0f  xor     edx, edx
0x140035f11  mov     qword ptr [rsp+80h+Length], rax
0x140035f16  mov     r8d, 20019h
0x140035f1c  mov     qword ptr [rbp+ValueName.Length], 1A0018h
0x140035f24  call    cs:__imp_IoOpenDriverRegistryKey
0x140035f2b  nop     dword ptr [rax+rax+00h]
0x140035f30  mov     ebx, eax
0x140035f32  test    eax, eax
0x140035f34  jns     short loc_140035F91
0x140035f36  lea     rcx, WPP_RECORDER_INITIALIZED
0x140035f3d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140035f44  jz      loc_140036066
0x140035f4a  mov     [rsp+80h+var_48], eax
0x140035f4e  mov     r9d, 45h ; 'E'
0x140035f54  mov     dword ptr [rsp+80h+var_50], 0C3Eh
0x140035f5c  mov     rcx, cs:wil_details_featureDescriptors_a
0x140035f63  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140035f6a  mov     [rsp+80h+ResultLength], rax
0x140035f6f  mov     r8d, 1
0x140035f75  lea     rax, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140035f7c  mov     dl, 2
0x140035f7e  mov     qword ptr [rsp+80h+Length], rax
0x140035f83  mov     rcx, [rcx+40h]
0x140035f87  call    WPP_RECORDER_SF_sDd
0x140035f8c  jmp     loc_140036066
0x140035f91  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140035f95  lea     rax, [rbp+var_40]
0x140035f99  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140035f9e  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x140035fa2  mov     r8d, 2; KeyValueInformationClass
0x140035fa8  mov     [rsp+80h+Length], 14h; Length
0x140035fb0  lea     rdx, [rbp+ValueName]; ValueName
0x140035fb4  call    cs:__imp_ZwQueryValueKey
0x140035fbb  nop     dword ptr [rax+rax+00h]
0x140035fc0  mov     ebx, eax
0x140035fc2  test    eax, eax
0x140035fc4  jns     short loc_140035FF1
0x140035fc6  lea     rcx, WPP_RECORDER_INITIALIZED
0x140035fcd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140035fd4  jz      loc_140036066
0x140035fda  mov     [rsp+80h+var_48], eax
0x140035fde  mov     r9d, 46h ; 'F'
0x140035fe4  mov     dword ptr [rsp+80h+var_50], 0C4Fh
0x140035fec  jmp     loc_140035F5C
0x140035ff1  mov     eax, [rbp+var_14]
0x140035ff4  test    al, 1
0x140035ff6  jz      short loc_140035FFF
0x140035ff8  mov     cs:byte_14000E680, 1
0x140035fff  test    al, 8
0x140036001  jz      short loc_14003600A
0x140036003  mov     byte ptr cs:qword_14000E6A2+1, 1
0x14003600a  test    al, 4
0x14003600c  jz      short loc_140036015
0x14003600e  mov     byte ptr cs:qword_14000E6A2, 1
0x140036015  test    al, 40h
0x140036017  jz      short loc_140036020
0x140036019  mov     byte ptr cs:qword_14000E6A2+2, 1
0x140036020  test    al, 10h
0x140036022  jz      short loc_14003602B
0x140036024  mov     byte ptr cs:word_14000E6A0+1, 1
0x14003602b  test    al, 20h
0x14003602d  jz      short loc_140036036
0x14003602f  mov     byte ptr cs:qword_14000E6A2+3, 1
0x140036036  test    al, 2
0x140036038  jz      short loc_140036041
0x14003603a  mov     byte ptr cs:word_14000E6A0, 1
0x140036041  test    al, al
0x140036043  jns     short loc_14003604C
0x140036045  mov     byte ptr cs:qword_14000E6A2+4, 1
0x14003604c  bt      eax, 8
0x140036050  jnb     short loc_140036059
0x140036052  mov     byte ptr cs:qword_14000E6A2+5, 1
0x140036059  bt      eax, 9
0x14003605d  jnb     short loc_140036066
0x14003605f  mov     byte ptr cs:qword_14000E6A2+6, 1
0x140036066  mov     rcx, [rbp+KeyHandle]; Handle
0x14003606a  test    rcx, rcx
0x14003606d  jz      short loc_14003607B
0x14003606f  call    cs:__imp_ZwClose
0x140036076  nop     dword ptr [rax+rax+00h]
0x14003607b  mov     eax, ebx
0x14003607d  mov     rcx, [rbp+var_8]
0x140036081  xor     rcx, rsp; StackCookie
0x140036084  call    __security_check_cookie
0x140036089  mov     rbx, [rsp+80h+arg_8]
0x140036091  add     rsp, 80h
0x140036098  pop     rbp
0x140036099  retn
```
