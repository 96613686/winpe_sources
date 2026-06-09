# ReserveLocalMajorSequence

- ea: `0x14004dc10`
- end: `0x14004dd8c`
- name: `ReserveLocalMajorSequence`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004d4e8`
- `0x14004dbdc`

## callees

- `0x14004156c`
- `0x14004ab3c`
- `0x14004dc10`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14004dcae`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004dcc1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004dcae`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004dcc1`
- `ntoskrnl!ZwSetValueKey` at `0x14004dd4d`
- `ntoskrnl!ZwSetValueKey` at `0x14004dd4d`
- `ntoskrnl!ZwCreateKey` at `0x14004dd1c`
- `ntoskrnl!ZwCreateKey` at `0x14004dd1c`
- `ntoskrnl!ZwClose` at `0x14004dd5f`
- `ntoskrnl!ZwClose` at `0x14004dd5f`

## string_xrefs

- `0x14004dc47`: `\Registry\Machine\System\CurrentControlSet\Services\SrvNet\Parameters`
- `0x14004dc8e`: `\Registry\Machine\System\CurrentControlSet\Services\SrvNet\Parameters`
- `0x14004dca3`: `\Registry\Machine\System\CurrentControlSet\Services\SrvNet\Parameters`

## pseudocode

```c
__int64 __fastcall ReserveLocalMajorSequence(_DWORD *a1)
{
  NTSTATUS v2; // ebx
  bool v3; // sf
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp+7h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF
  int Data; // [rsp+A0h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+6Fh] BYREF

  *a1 = 0;
  KeyHandle = 0;
  Data = 0;
  ValueName = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (int)RfsRegGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\SrvNet\\Parameters",
              L"MajorSequence") < 0 )
  {
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\SrvNet\\Parameters");
    RtlInitUnicodeString(&ValueName, L"MajorSequence");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = ZwCreateKey(&KeyHandle, 2u, &ObjectAttributes, 0, 0, 0, 0);
    if ( v2 < 0 )
      return (unsigned int)v2;
    v2 = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
    ZwClose(KeyHandle);
    v3 = v2 < 0;
  }
  else
  {
    if ( (unsigned int)++Data >= 0x1000000 )
      Data = 0;
    v2 = RfsRegSetDWord(
           L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\SrvNet\\Parameters",
           L"MajorSequence");
    v3 = v2 < 0;
  }
  if ( !v3 )
    *a1 = Data;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14004dc10  mov     [rsp-8+arg_10], rbx
0x14004dc15  mov     [rsp-8+arg_18], rdi
0x14004dc1a  push    rbp
0x14004dc1b  lea     rbp, [rsp-57h]
0x14004dc20  sub     rsp, 90h
0x14004dc27  xorps   xmm0, xmm0
0x14004dc2a  lea     rbx, aMajorsequence; "MajorSequence"
0x14004dc31  xor     eax, eax
0x14004dc33  lea     r8, [rbp+57h+Data]
0x14004dc37  mov     [rcx], eax
0x14004dc39  mov     rdi, rcx
0x14004dc3c  xorps   xmm1, xmm1
0x14004dc3f  mov     [rbp+57h+KeyHandle], rax
0x14004dc43  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004dc47  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004dc4e  mov     [rbp+57h+Data], eax
0x14004dc51  mov     rdx, rbx; PCWSTR
0x14004dc54  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14004dc58  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14004dc5c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14004dc60  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14004dc64  call    RfsRegGetDWord
0x14004dc69  test    eax, eax
0x14004dc6b  js      short loc_14004DCA3
0x14004dc6d  mov     r8d, [rbp+57h+Data]
0x14004dc71  inc     r8d
0x14004dc74  mov     [rbp+57h+Data], r8d
0x14004dc78  cmp     r8d, 1000000h
0x14004dc7f  jb      short loc_14004DC8B
0x14004dc81  mov     [rbp+57h+Data], 0
0x14004dc88  xor     r8d, r8d
0x14004dc8b  mov     rdx, rbx; PCWSTR
0x14004dc8e  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004dc95  call    RfsRegSetDWord
0x14004dc9a  mov     ebx, eax
0x14004dc9c  test    eax, eax
0x14004dc9e  jmp     loc_14004DD6D
0x14004dca3  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004dcaa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004dcae  call    cs:__imp_RtlInitUnicodeString
0x14004dcb5  nop     dword ptr [rax+rax+00h]
0x14004dcba  mov     rdx, rbx; SourceString
0x14004dcbd  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14004dcc1  call    cs:__imp_RtlInitUnicodeString
0x14004dcc8  nop     dword ptr [rax+rax+00h]
0x14004dccd  xor     r9d, r9d; TitleIndex
0x14004dcd0  mov     [rsp+90h+Disposition], 0; Disposition
0x14004dcd9  lea     rax, [rbp+57h+DestinationString]
0x14004dcdd  mov     [rsp+90h+CreateOptions], 0; CreateOptions
0x14004dce5  xorps   xmm0, xmm0
0x14004dce8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004dcef  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004dcf3  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14004dcfb  lea     edx, [r9+2]; DesiredAccess
0x14004dcff  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14004dd06  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14004dd0a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004dd0e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004dd13  mov     [rsp+90h+Class], 0; Class
0x14004dd1c  call    cs:__imp_ZwCreateKey
0x14004dd23  nop     dword ptr [rax+rax+00h]
0x14004dd28  mov     ebx, eax
0x14004dd2a  test    eax, eax
0x14004dd2c  js      short loc_14004DD74
0x14004dd2e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14004dd32  lea     rax, [rbp+57h+Data]
0x14004dd36  mov     r9d, 4; Type
0x14004dd3c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14004dd40  mov     [rsp+90h+CreateOptions], r9d; DataSize
0x14004dd45  xor     r8d, r8d; TitleIndex
0x14004dd48  mov     [rsp+90h+Class], rax; Data
0x14004dd4d  call    cs:__imp_ZwSetValueKey
0x14004dd54  nop     dword ptr [rax+rax+00h]
0x14004dd59  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14004dd5d  mov     ebx, eax
0x14004dd5f  call    cs:__imp_ZwClose
0x14004dd66  nop     dword ptr [rax+rax+00h]
0x14004dd6b  test    ebx, ebx
0x14004dd6d  js      short loc_14004DD74
0x14004dd6f  mov     eax, [rbp+57h+Data]
0x14004dd72  mov     [rdi], eax
0x14004dd74  lea     r11, [rsp+90h+var_s0]
0x14004dd7c  mov     eax, ebx
0x14004dd7e  mov     rbx, [r11+20h]
0x14004dd82  mov     rdi, [r11+28h]
0x14004dd86  mov     rsp, r11
0x14004dd89  pop     rbp
0x14004dd8a  retn
```
