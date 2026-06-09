# PpRegStateUpdateStackCreationSettings

- ea: `0x1400d4b64`
- end: `0x1400d4cd8`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400d43f0`

## callees

- `0x14004f1c0`
- `0x1400d467c`
- `0x1400d4b64`
- `0x1400d4e8c`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1400d4ca7`
- `ntoskrnl!ZwSetValueKey` at `0x1400d4ca7`
- `ntoskrnl!ZwClose` at `0x1400d4c48`
- `ntoskrnl!ZwClose` at `0x1400d4cb9`
- `ntoskrnl!ZwClose` at `0x1400d4c48`
- `ntoskrnl!ZwClose` at `0x1400d4cb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4bf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4bf2`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400d4c5c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400d4c5c`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400d4bd2`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400d4bd2`

## string_xrefs

- `0x1400d4c6c`: `Security`

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
0x1400d4b64  mov     [rsp-8+arg_0], rbx
0x1400d4b69  mov     [rsp-8+arg_8], rdi
0x1400d4b6e  push    rbp
0x1400d4b6f  mov     rbp, rsp
0x1400d4b72  sub     rsp, 60h
0x1400d4b76  lea     rax, [rbp+Handle]
0x1400d4b7a  mov     [rbp+P], 0
0x1400d4b82  xor     r9d, r9d
0x1400d4b85  mov     [rsp+60h+Data], rax
0x1400d4b8a  xor     r8d, r8d
0x1400d4b8d  mov     [rbp+KeyHandle], 0
0x1400d4b95  mov     rdi, rdx
0x1400d4b98  mov     [rbp+Handle], 0
0x1400d4ba0  call    PiRegStateOpenClassKey
0x1400d4ba5  test    eax, eax
0x1400d4ba7  js      loc_1400D4CC7
0x1400d4bad  cmp     cs:PiRegStateDiscriptor, 0
0x1400d4bb4  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400d4bbb  jnz     short loc_1400D4C0A
0x1400d4bbd  xor     edx, edx
0x1400d4bbf  lea     rax, [rbp+P]
0x1400d4bc3  mov     r9b, 1
0x1400d4bc6  mov     [rsp+60h+Data], rax
0x1400d4bcb  mov     rcx, rbx
0x1400d4bce  lea     r8d, [rdx+1]
0x1400d4bd2  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400d4bd9  nop     dword ptr [rax+rax+00h]
0x1400d4bde  test    eax, eax
0x1400d4be0  js      short loc_1400D4C00
0x1400d4be2  mov     rcx, [rbp+P]; P
0x1400d4be6  xor     edx, edx; Tag
0x1400d4be8  mov     cs:PiRegStateDiscriptor, 1
0x1400d4bf2  call    cs:__imp_ExFreePoolWithTag
0x1400d4bf9  nop     dword ptr [rax+rax+00h]
0x1400d4bfe  jmp     short loc_1400D4C0A
0x1400d4c00  mov     cs:PiRegStateDiscriptor, 2
0x1400d4c0a  mov     rcx, [rbp+Handle]
0x1400d4c0e  lea     rdx, aProperties; "Properties"
0x1400d4c15  xor     eax, eax
0x1400d4c17  cmp     cs:PiRegStateDiscriptor, 1
0x1400d4c1e  cmovnz  rbx, rax
0x1400d4c22  lea     rax, [rbp+KeyHandle]
0x1400d4c26  mov     [rsp+60h+var_30], rax
0x1400d4c2b  mov     qword ptr [rsp+60h+DataSize], 0
0x1400d4c34  mov     [rsp+60h+Data], rbx
0x1400d4c39  mov     [rbp+P], rbx
0x1400d4c3d  call    CmRegUtilCreateWstrKey
0x1400d4c42  mov     rcx, [rbp+Handle]; Handle
0x1400d4c46  mov     ebx, eax
0x1400d4c48  call    cs:__imp_ZwClose
0x1400d4c4f  nop     dword ptr [rax+rax+00h]
0x1400d4c54  test    ebx, ebx
0x1400d4c56  js      short loc_1400D4CC5
0x1400d4c58  mov     rcx, [rdi+8]; SecurityDescriptor
0x1400d4c5c  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400d4c63  nop     dword ptr [rax+rax+00h]
0x1400d4c68  mov     r11, [rdi+8]
0x1400d4c6c  lea     rdx, aSecurity; "Security"
0x1400d4c73  xorps   xmm0, xmm0
0x1400d4c76  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400d4c7a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400d4c7e  mov     r10d, eax
0x1400d4c81  call    WdmlibRtlInitUnicodeStringEx
0x1400d4c86  mov     ebx, eax
0x1400d4c88  test    eax, eax
0x1400d4c8a  js      short loc_1400D4CB5
0x1400d4c8c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400d4c90  lea     rdx, [rbp+DestinationString]; ValueName
0x1400d4c94  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400d4c99  mov     r9d, 3; Type
0x1400d4c9f  xor     r8d, r8d; TitleIndex
0x1400d4ca2  mov     [rsp+60h+Data], r11; Data
0x1400d4ca7  call    cs:__imp_ZwSetValueKey
0x1400d4cae  nop     dword ptr [rax+rax+00h]
0x1400d4cb3  mov     ebx, eax
0x1400d4cb5  mov     rcx, [rbp+KeyHandle]; Handle
0x1400d4cb9  call    cs:__imp_ZwClose
0x1400d4cc0  nop     dword ptr [rax+rax+00h]
0x1400d4cc5  mov     eax, ebx
0x1400d4cc7  mov     rbx, [rsp+60h+arg_0]
0x1400d4ccc  mov     rdi, [rsp+60h+arg_8]
0x1400d4cd1  add     rsp, 60h
0x1400d4cd5  pop     rbp
0x1400d4cd6  retn
```
