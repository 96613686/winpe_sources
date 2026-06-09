# PpRegStateUpdateStackCreationSettings

- ea: `0x1400d4bd4`
- end: `0x1400d4d48`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400d4460`

## callees

- `0x14004edd0`
- `0x1400d46ec`
- `0x1400d4bd4`
- `0x1400d4efc`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1400d4d17`
- `ntoskrnl!ZwSetValueKey` at `0x1400d4d17`
- `ntoskrnl!ZwClose` at `0x1400d4cb8`
- `ntoskrnl!ZwClose` at `0x1400d4d29`
- `ntoskrnl!ZwClose` at `0x1400d4cb8`
- `ntoskrnl!ZwClose` at `0x1400d4d29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4c62`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4c62`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400d4ccc`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400d4ccc`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400d4c42`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400d4c42`

## string_xrefs

- `0x1400d4cdc`: `Security`

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
0x1400d4bd4  mov     [rsp-8+arg_0], rbx
0x1400d4bd9  mov     [rsp-8+arg_8], rdi
0x1400d4bde  push    rbp
0x1400d4bdf  mov     rbp, rsp
0x1400d4be2  sub     rsp, 60h
0x1400d4be6  lea     rax, [rbp+Handle]
0x1400d4bea  mov     [rbp+P], 0
0x1400d4bf2  xor     r9d, r9d
0x1400d4bf5  mov     [rsp+60h+Data], rax
0x1400d4bfa  xor     r8d, r8d
0x1400d4bfd  mov     [rbp+KeyHandle], 0
0x1400d4c05  mov     rdi, rdx
0x1400d4c08  mov     [rbp+Handle], 0
0x1400d4c10  call    PiRegStateOpenClassKey
0x1400d4c15  test    eax, eax
0x1400d4c17  js      loc_1400D4D37
0x1400d4c1d  cmp     cs:PiRegStateDiscriptor, 0
0x1400d4c24  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400d4c2b  jnz     short loc_1400D4C7A
0x1400d4c2d  xor     edx, edx
0x1400d4c2f  lea     rax, [rbp+P]
0x1400d4c33  mov     r9b, 1
0x1400d4c36  mov     [rsp+60h+Data], rax
0x1400d4c3b  mov     rcx, rbx
0x1400d4c3e  lea     r8d, [rdx+1]
0x1400d4c42  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400d4c49  nop     dword ptr [rax+rax+00h]
0x1400d4c4e  test    eax, eax
0x1400d4c50  js      short loc_1400D4C70
0x1400d4c52  mov     rcx, [rbp+P]; P
0x1400d4c56  xor     edx, edx; Tag
0x1400d4c58  mov     cs:PiRegStateDiscriptor, 1
0x1400d4c62  call    cs:__imp_ExFreePoolWithTag
0x1400d4c69  nop     dword ptr [rax+rax+00h]
0x1400d4c6e  jmp     short loc_1400D4C7A
0x1400d4c70  mov     cs:PiRegStateDiscriptor, 2
0x1400d4c7a  mov     rcx, [rbp+Handle]
0x1400d4c7e  lea     rdx, aProperties; "Properties"
0x1400d4c85  xor     eax, eax
0x1400d4c87  cmp     cs:PiRegStateDiscriptor, 1
0x1400d4c8e  cmovnz  rbx, rax
0x1400d4c92  lea     rax, [rbp+KeyHandle]
0x1400d4c96  mov     [rsp+60h+var_30], rax
0x1400d4c9b  mov     qword ptr [rsp+60h+DataSize], 0
0x1400d4ca4  mov     [rsp+60h+Data], rbx
0x1400d4ca9  mov     [rbp+P], rbx
0x1400d4cad  call    CmRegUtilCreateWstrKey
0x1400d4cb2  mov     rcx, [rbp+Handle]; Handle
0x1400d4cb6  mov     ebx, eax
0x1400d4cb8  call    cs:__imp_ZwClose
0x1400d4cbf  nop     dword ptr [rax+rax+00h]
0x1400d4cc4  test    ebx, ebx
0x1400d4cc6  js      short loc_1400D4D35
0x1400d4cc8  mov     rcx, [rdi+8]; SecurityDescriptor
0x1400d4ccc  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400d4cd3  nop     dword ptr [rax+rax+00h]
0x1400d4cd8  mov     r11, [rdi+8]
0x1400d4cdc  lea     rdx, aSecurity; "Security"
0x1400d4ce3  xorps   xmm0, xmm0
0x1400d4ce6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400d4cea  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400d4cee  mov     r10d, eax
0x1400d4cf1  call    WdmlibRtlInitUnicodeStringEx
0x1400d4cf6  mov     ebx, eax
0x1400d4cf8  test    eax, eax
0x1400d4cfa  js      short loc_1400D4D25
0x1400d4cfc  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400d4d00  lea     rdx, [rbp+DestinationString]; ValueName
0x1400d4d04  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400d4d09  mov     r9d, 3; Type
0x1400d4d0f  xor     r8d, r8d; TitleIndex
0x1400d4d12  mov     [rsp+60h+Data], r11; Data
0x1400d4d17  call    cs:__imp_ZwSetValueKey
0x1400d4d1e  nop     dword ptr [rax+rax+00h]
0x1400d4d23  mov     ebx, eax
0x1400d4d25  mov     rcx, [rbp+KeyHandle]; Handle
0x1400d4d29  call    cs:__imp_ZwClose
0x1400d4d30  nop     dword ptr [rax+rax+00h]
0x1400d4d35  mov     eax, ebx
0x1400d4d37  mov     rbx, [rsp+60h+arg_0]
0x1400d4d3c  mov     rdi, [rsp+60h+arg_8]
0x1400d4d41  add     rsp, 60h
0x1400d4d45  pop     rbp
0x1400d4d46  retn
```
