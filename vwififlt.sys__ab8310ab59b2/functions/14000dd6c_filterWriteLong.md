# filterWriteLong

- ea: `0x14000dd6c`
- end: `0x14000df04`
- name: `filterWriteLong`
- size: `408`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000204c`
- `0x140004d70`

## callees

- `0x14000d91c`
- `0x14000dd6c`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14000de67`
- `ntoskrnl!ZwSetValueKey` at `0x14000de67`
- `ntoskrnl!ZwClose` at `0x14000deb6`
- `ntoskrnl!ZwClose` at `0x14000deb6`
- `ntoskrnl!ZwCreateKey` at `0x14000ddfd`
- `ntoskrnl!ZwCreateKey` at `0x14000ddfd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000de3c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000de3c`

## pseudocode

```c
__int64 __fastcall filterWriteLong(__int64 a1, const WCHAR *a2, int a3)
{
  unsigned int v4; // ebx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+20h] BYREF
  int Data; // [rsp+B0h] [rbp+30h] BYREF

  Data = a3;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 )
  {
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 2232);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = ZwCreateKey(&KeyHandle, 2u, &ObjectAttributes, 0, 0, 0, 0);
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v6 = 245;
LABEL_11:
        WPP_SF_d(v5->AttachedDevice, v6, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
        goto LABEL_12;
      }
      goto LABEL_12;
    }
  }
  else
  {
    KeyHandle = Handle;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  v4 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v6 = 246;
      goto LABEL_11;
    }
  }
LABEL_12:
  if ( KeyHandle && KeyHandle != Handle )
    ZwClose(KeyHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 247, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x14000dd6c  mov     r11, rsp
0x14000dd6f  mov     [r11+10h], rbx
0x14000dd73  mov     [r11+18h], r8d
0x14000dd77  push    rbp
0x14000dd78  push    rdi
0x14000dd79  push    r14
0x14000dd7b  mov     rbp, rsp
0x14000dd7e  sub     rsp, 80h
0x14000dd85  xorps   xmm0, xmm0
0x14000dd88  lea     r14, WPP_GLOBAL_Control
0x14000dd8f  xor     eax, eax
0x14000dd91  mov     rdi, rdx
0x14000dd94  mov     [rbp+KeyHandle], rax
0x14000dd98  mov     rax, cs:Handle
0x14000dd9f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000dda3  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000dda7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000ddab  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000ddaf  test    rcx, rcx
0x14000ddb2  jz      short loc_14000DE31
0x14000ddb4  mov     qword ptr [r11-68h], 0
0x14000ddbc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000ddc0  xor     r9d, r9d; TitleIndex
0x14000ddc3  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14000ddc7  lea     rax, [rcx+8B8h]
0x14000ddce  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x14000ddd6  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000ddda  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000dde1  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000dde8  lea     edx, [r9+2]; DesiredAccess
0x14000ddec  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000ddf0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000ddf5  mov     qword ptr [r11-78h], 0
0x14000ddfd  call    cs:__imp_ZwCreateKey
0x14000de04  nop     dword ptr [rax+rax+00h]
0x14000de09  mov     ebx, eax
0x14000de0b  test    eax, eax
0x14000de0d  jz      short loc_14000DE35
0x14000de0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de16  cmp     rcx, r14
0x14000de19  jz      loc_14000DEA4
0x14000de1f  mov     edx, [rcx+2Ch]
0x14000de22  test    dl, 1
0x14000de25  jz      short loc_14000DEA4
0x14000de27  mov     edx, 0F5h
0x14000de2c  mov     r9d, eax
0x14000de2f  jmp     short loc_14000DE94
0x14000de31  mov     [rbp+KeyHandle], rax
0x14000de35  mov     rdx, rdi; SourceString
0x14000de38  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000de3c  call    cs:__imp_RtlInitUnicodeString
0x14000de43  nop     dword ptr [rax+rax+00h]
0x14000de48  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000de4c  lea     rax, [rbp+arg_10]
0x14000de50  mov     r9d, 4; Type
0x14000de56  lea     rdx, [rbp+DestinationString]; ValueName
0x14000de5a  mov     [rsp+80h+CreateOptions], r9d; DataSize
0x14000de5f  xor     r8d, r8d; TitleIndex
0x14000de62  mov     [rsp+80h+Data], rax; Data
0x14000de67  call    cs:__imp_ZwSetValueKey
0x14000de6e  nop     dword ptr [rax+rax+00h]
0x14000de73  mov     ebx, eax
0x14000de75  test    eax, eax
0x14000de77  jz      short loc_14000DEA4
0x14000de79  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de80  cmp     rcx, r14
0x14000de83  jz      short loc_14000DEA4
0x14000de85  mov     eax, [rcx+2Ch]
0x14000de88  test    al, 1
0x14000de8a  jz      short loc_14000DEA4
0x14000de8c  mov     edx, 0F6h
0x14000de91  mov     r9d, ebx
0x14000de94  mov     rcx, [rcx+18h]
0x14000de98  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000de9f  call    WPP_SF_d
0x14000dea4  mov     rcx, [rbp+KeyHandle]; Handle
0x14000dea8  test    rcx, rcx
0x14000deab  jz      short loc_14000DEC2
0x14000dead  cmp     rcx, cs:Handle
0x14000deb4  jz      short loc_14000DEC2
0x14000deb6  call    cs:__imp_ZwClose
0x14000debd  nop     dword ptr [rax+rax+00h]
0x14000dec2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dec9  cmp     rcx, r14
0x14000decc  jz      short loc_14000DEED
0x14000dece  mov     eax, [rcx+2Ch]
0x14000ded1  test    al, 20h
0x14000ded3  jz      short loc_14000DEED
0x14000ded5  mov     rcx, [rcx+18h]
0x14000ded9  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000dee0  mov     edx, 0F7h
0x14000dee5  mov     r9d, ebx
0x14000dee8  call    WPP_SF_d
0x14000deed  mov     eax, ebx
0x14000deef  mov     rbx, [rsp+80h+arg_8]
0x14000def7  add     rsp, 80h
0x14000defe  pop     r14
0x14000df00  pop     rdi
0x14000df01  pop     rbp
0x14000df02  retn
```
