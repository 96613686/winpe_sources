# WcSetConfiguration

- ea: `0x140035edc`
- end: `0x1400360a7`
- name: `WcSetConfiguration`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400351b4`

## callees

- `0x1400020c4`
- `0x140007c60`
- `0x140035edc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14003607b`
- `ntoskrnl!ZwClose` at `0x14003607b`
- `ntoskrnl!ZwQueryValueKey` at `0x140035fc0`
- `ntoskrnl!ZwQueryValueKey` at `0x140035fc0`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140035f30`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140035f30`

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
  char v8; // [rsp+38h] [rbp-48h]
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
      WPP_GLOBAL_Control->DeviceExtension,
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
0x140035edc  mov     [rsp-8+arg_8], rbx
0x140035ee1  push    rbp
0x140035ee2  mov     rbp, rsp
0x140035ee5  sub     rsp, 80h
0x140035eec  mov     rax, cs:__security_cookie
0x140035ef3  xor     rax, rsp
0x140035ef6  mov     [rbp+var_8], rax
0x140035efa  lea     rax, aDebugoptions; "DebugOptions"
0x140035f01  mov     [rbp+KeyHandle], 0
0x140035f09  mov     [rbp+ValueName.Buffer], rax
0x140035f0d  xor     r9d, r9d
0x140035f10  lea     rax, [rbp+KeyHandle]
0x140035f14  mov     [rbp+var_40], 0
0x140035f1b  xor     edx, edx
0x140035f1d  mov     qword ptr [rsp+80h+Length], rax
0x140035f22  mov     r8d, 20019h
0x140035f28  mov     qword ptr [rbp+ValueName.Length], 1A0018h
0x140035f30  call    cs:__imp_IoOpenDriverRegistryKey
0x140035f37  nop     dword ptr [rax+rax+00h]
0x140035f3c  mov     ebx, eax
0x140035f3e  test    eax, eax
0x140035f40  jns     short loc_140035F9D
0x140035f42  lea     rcx, WPP_RECORDER_INITIALIZED
0x140035f49  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140035f50  jz      loc_140036072
0x140035f56  mov     dword ptr [rsp+80h+var_48], eax
0x140035f5a  mov     r9d, 45h ; 'E'
0x140035f60  mov     dword ptr [rsp+80h+var_50], 0C3Eh
0x140035f68  mov     rcx, cs:WPP_GLOBAL_Control
0x140035f6f  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140035f76  mov     [rsp+80h+ResultLength], rax
0x140035f7b  mov     r8d, 1
0x140035f81  lea     rax, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140035f88  mov     dl, 2
0x140035f8a  mov     qword ptr [rsp+80h+Length], rax
0x140035f8f  mov     rcx, [rcx+40h]
0x140035f93  call    WPP_RECORDER_SF_sDd
0x140035f98  jmp     loc_140036072
0x140035f9d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140035fa1  lea     rax, [rbp+var_40]
0x140035fa5  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140035faa  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x140035fae  mov     r8d, 2; KeyValueInformationClass
0x140035fb4  mov     [rsp+80h+Length], 14h; Length
0x140035fbc  lea     rdx, [rbp+ValueName]; ValueName
0x140035fc0  call    cs:__imp_ZwQueryValueKey
0x140035fc7  nop     dword ptr [rax+rax+00h]
0x140035fcc  mov     ebx, eax
0x140035fce  test    eax, eax
0x140035fd0  jns     short loc_140035FFD
0x140035fd2  lea     rcx, WPP_RECORDER_INITIALIZED
0x140035fd9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140035fe0  jz      loc_140036072
0x140035fe6  mov     dword ptr [rsp+80h+var_48], eax
0x140035fea  mov     r9d, 46h ; 'F'
0x140035ff0  mov     dword ptr [rsp+80h+var_50], 0C4Fh
0x140035ff8  jmp     loc_140035F68
0x140035ffd  mov     eax, [rbp+var_14]
0x140036000  test    al, 1
0x140036002  jz      short loc_14003600B
0x140036004  mov     cs:byte_14000E680, 1
0x14003600b  test    al, 8
0x14003600d  jz      short loc_140036016
0x14003600f  mov     byte ptr cs:qword_14000E6A2+1, 1
0x140036016  test    al, 4
0x140036018  jz      short loc_140036021
0x14003601a  mov     byte ptr cs:qword_14000E6A2, 1
0x140036021  test    al, 40h
0x140036023  jz      short loc_14003602C
0x140036025  mov     byte ptr cs:qword_14000E6A2+2, 1
0x14003602c  test    al, 10h
0x14003602e  jz      short loc_140036037
0x140036030  mov     byte ptr cs:word_14000E6A0+1, 1
0x140036037  test    al, 20h
0x140036039  jz      short loc_140036042
0x14003603b  mov     byte ptr cs:qword_14000E6A2+3, 1
0x140036042  test    al, 2
0x140036044  jz      short loc_14003604D
0x140036046  mov     byte ptr cs:word_14000E6A0, 1
0x14003604d  test    al, al
0x14003604f  jns     short loc_140036058
0x140036051  mov     byte ptr cs:qword_14000E6A2+4, 1
0x140036058  bt      eax, 8
0x14003605c  jnb     short loc_140036065
0x14003605e  mov     byte ptr cs:qword_14000E6A2+5, 1
0x140036065  bt      eax, 9
0x140036069  jnb     short loc_140036072
0x14003606b  mov     byte ptr cs:qword_14000E6A2+6, 1
0x140036072  mov     rcx, [rbp+KeyHandle]; Handle
0x140036076  test    rcx, rcx
0x140036079  jz      short loc_140036087
0x14003607b  call    cs:__imp_ZwClose
0x140036082  nop     dword ptr [rax+rax+00h]
0x140036087  mov     eax, ebx
0x140036089  mov     rcx, [rbp+var_8]
0x14003608d  xor     rcx, rsp; StackCookie
0x140036090  call    __security_check_cookie
0x140036095  mov     rbx, [rsp+80h+arg_8]
0x14003609d  add     rsp, 80h
0x1400360a4  pop     rbp
0x1400360a5  retn
```
