# PpRegStateUpdateStackCreationSettings

- ea: `0x1400191a0`
- end: `0x140019314`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400180b0`

## callees

- `0x140004f04`
- `0x140018cb8`
- `0x1400191a0`
- `0x1400194c8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140019284`
- `ntoskrnl!ZwClose` at `0x1400192f5`
- `ntoskrnl!ZwClose` at `0x140019284`
- `ntoskrnl!ZwClose` at `0x1400192f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001922e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001922e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140019298`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140019298`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001920e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001920e`
- `ntoskrnl!ZwSetValueKey` at `0x1400192e3`
- `ntoskrnl!ZwSetValueKey` at `0x1400192e3`

## string_xrefs

- `0x1400192a8`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r10d
  void *Data; // r11
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h] BYREF

  P = 0;
  KeyHandle = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, (__int64)&Handle);
  if ( (int)result >= 0 )
  {
    v6 = PiRegStateSysAllInherittedSecurityDescriptor;
    if ( !PiRegStateDiscriptor )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        PiRegStateDiscriptor = 2;
      }
      else
      {
        PiRegStateDiscriptor = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( PiRegStateDiscriptor != 1 )
      v6 = 0;
    P = v6;
    WstrKey = CmRegUtilCreateWstrKey(
                (_DWORD)Handle,
                (unsigned int)L"Properties",
                v4,
                v5,
                (__int64)v6,
                0,
                (__int64)&KeyHandle);
    ZwClose(Handle);
    if ( WstrKey >= 0 )
    {
      RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      DestinationString = 0;
      WstrKey = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
      if ( WstrKey >= 0 )
        WstrKey = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
      ZwClose(KeyHandle);
    }
    return (unsigned int)WstrKey;
  }
  return result;
}

```

## disassembly

```asm
0x1400191a0  mov     [rsp-8+arg_0], rbx
0x1400191a5  mov     [rsp-8+arg_8], rdi
0x1400191aa  push    rbp
0x1400191ab  mov     rbp, rsp
0x1400191ae  sub     rsp, 60h
0x1400191b2  lea     rax, [rbp+Handle]
0x1400191b6  mov     [rbp+P], 0
0x1400191be  xor     r9d, r9d
0x1400191c1  mov     [rsp+60h+Data], rax
0x1400191c6  xor     r8d, r8d
0x1400191c9  mov     [rbp+KeyHandle], 0
0x1400191d1  mov     rdi, rdx
0x1400191d4  mov     [rbp+Handle], 0
0x1400191dc  call    PiRegStateOpenClassKey
0x1400191e1  test    eax, eax
0x1400191e3  js      loc_140019303
0x1400191e9  cmp     cs:PiRegStateDiscriptor, 0
0x1400191f0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400191f7  jnz     short loc_140019246
0x1400191f9  xor     edx, edx
0x1400191fb  lea     rax, [rbp+P]
0x1400191ff  mov     r9b, 1
0x140019202  mov     [rsp+60h+Data], rax
0x140019207  mov     rcx, rbx
0x14001920a  lea     r8d, [rdx+1]
0x14001920e  call    cs:__imp_SeCaptureSecurityDescriptor
0x140019215  nop     dword ptr [rax+rax+00h]
0x14001921a  test    eax, eax
0x14001921c  js      short loc_14001923C
0x14001921e  mov     rcx, [rbp+P]; P
0x140019222  xor     edx, edx; Tag
0x140019224  mov     cs:PiRegStateDiscriptor, 1
0x14001922e  call    cs:__imp_ExFreePoolWithTag
0x140019235  nop     dword ptr [rax+rax+00h]
0x14001923a  jmp     short loc_140019246
0x14001923c  mov     cs:PiRegStateDiscriptor, 2
0x140019246  mov     rcx, [rbp+Handle]
0x14001924a  lea     rdx, aProperties; "Properties"
0x140019251  xor     eax, eax
0x140019253  cmp     cs:PiRegStateDiscriptor, 1
0x14001925a  cmovnz  rbx, rax
0x14001925e  lea     rax, [rbp+KeyHandle]
0x140019262  mov     [rsp+60h+var_30], rax
0x140019267  mov     qword ptr [rsp+60h+DataSize], 0
0x140019270  mov     [rsp+60h+Data], rbx
0x140019275  mov     [rbp+P], rbx
0x140019279  call    CmRegUtilCreateWstrKey
0x14001927e  mov     rcx, [rbp+Handle]; Handle
0x140019282  mov     ebx, eax
0x140019284  call    cs:__imp_ZwClose
0x14001928b  nop     dword ptr [rax+rax+00h]
0x140019290  test    ebx, ebx
0x140019292  js      short loc_140019301
0x140019294  mov     rcx, [rdi+8]; SecurityDescriptor
0x140019298  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001929f  nop     dword ptr [rax+rax+00h]
0x1400192a4  mov     r11, [rdi+8]
0x1400192a8  lea     rdx, aSecurity; "Security"
0x1400192af  xorps   xmm0, xmm0
0x1400192b2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400192b6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400192ba  mov     r10d, eax
0x1400192bd  call    WdmlibRtlInitUnicodeStringEx
0x1400192c2  mov     ebx, eax
0x1400192c4  test    eax, eax
0x1400192c6  js      short loc_1400192F1
0x1400192c8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400192cc  lea     rdx, [rbp+DestinationString]; ValueName
0x1400192d0  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400192d5  mov     r9d, 3; Type
0x1400192db  xor     r8d, r8d; TitleIndex
0x1400192de  mov     [rsp+60h+Data], r11; Data
0x1400192e3  call    cs:__imp_ZwSetValueKey
0x1400192ea  nop     dword ptr [rax+rax+00h]
0x1400192ef  mov     ebx, eax
0x1400192f1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400192f5  call    cs:__imp_ZwClose
0x1400192fc  nop     dword ptr [rax+rax+00h]
0x140019301  mov     eax, ebx
0x140019303  mov     rbx, [rsp+60h+arg_0]
0x140019308  mov     rdi, [rsp+60h+arg_8]
0x14001930d  add     rsp, 60h
0x140019311  pop     rbp
0x140019312  retn
```
