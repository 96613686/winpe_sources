# PpRegStateUpdateStackCreationSettings

- ea: `0x1400213a0`
- end: `0x140021514`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400202a0`

## callees

- `0x140007dc4`
- `0x140020eb8`
- `0x1400213a0`
- `0x14002161c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140021484`
- `ntoskrnl!ZwClose` at `0x1400214f5`
- `ntoskrnl!ZwClose` at `0x140021484`
- `ntoskrnl!ZwClose` at `0x1400214f5`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140021498`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140021498`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14002140e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14002140e`
- `ntoskrnl!ZwSetValueKey` at `0x1400214e3`
- `ntoskrnl!ZwSetValueKey` at `0x1400214e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002142e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002142e`

## string_xrefs

- `0x1400214a8`: `Security`

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
0x1400213a0  mov     [rsp-8+arg_0], rbx
0x1400213a5  mov     [rsp-8+arg_8], rdi
0x1400213aa  push    rbp
0x1400213ab  mov     rbp, rsp
0x1400213ae  sub     rsp, 60h
0x1400213b2  lea     rax, [rbp+Handle]
0x1400213b6  mov     [rbp+P], 0
0x1400213be  xor     r9d, r9d
0x1400213c1  mov     [rsp+60h+Data], rax
0x1400213c6  xor     r8d, r8d
0x1400213c9  mov     [rbp+KeyHandle], 0
0x1400213d1  mov     rdi, rdx
0x1400213d4  mov     [rbp+Handle], 0
0x1400213dc  call    PiRegStateOpenClassKey
0x1400213e1  test    eax, eax
0x1400213e3  js      loc_140021503
0x1400213e9  cmp     cs:PiRegStateDiscriptor, 0
0x1400213f0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400213f7  jnz     short loc_140021446
0x1400213f9  xor     edx, edx
0x1400213fb  lea     rax, [rbp+P]
0x1400213ff  mov     r9b, 1
0x140021402  mov     [rsp+60h+Data], rax
0x140021407  mov     rcx, rbx
0x14002140a  lea     r8d, [rdx+1]
0x14002140e  call    cs:__imp_SeCaptureSecurityDescriptor
0x140021415  nop     dword ptr [rax+rax+00h]
0x14002141a  test    eax, eax
0x14002141c  js      short loc_14002143C
0x14002141e  mov     rcx, [rbp+P]; P
0x140021422  xor     edx, edx; Tag
0x140021424  mov     cs:PiRegStateDiscriptor, 1
0x14002142e  call    cs:__imp_ExFreePoolWithTag
0x140021435  nop     dword ptr [rax+rax+00h]
0x14002143a  jmp     short loc_140021446
0x14002143c  mov     cs:PiRegStateDiscriptor, 2
0x140021446  mov     rcx, [rbp+Handle]
0x14002144a  lea     rdx, aProperties; "Properties"
0x140021451  xor     eax, eax
0x140021453  cmp     cs:PiRegStateDiscriptor, 1
0x14002145a  cmovnz  rbx, rax
0x14002145e  lea     rax, [rbp+KeyHandle]
0x140021462  mov     [rsp+60h+var_30], rax
0x140021467  mov     qword ptr [rsp+60h+DataSize], 0
0x140021470  mov     [rsp+60h+Data], rbx
0x140021475  mov     [rbp+P], rbx
0x140021479  call    CmRegUtilCreateWstrKey
0x14002147e  mov     rcx, [rbp+Handle]; Handle
0x140021482  mov     ebx, eax
0x140021484  call    cs:__imp_ZwClose
0x14002148b  nop     dword ptr [rax+rax+00h]
0x140021490  test    ebx, ebx
0x140021492  js      short loc_140021501
0x140021494  mov     rcx, [rdi+8]; SecurityDescriptor
0x140021498  call    cs:__imp_RtlLengthSecurityDescriptor
0x14002149f  nop     dword ptr [rax+rax+00h]
0x1400214a4  mov     r11, [rdi+8]
0x1400214a8  lea     rdx, aSecurity; "Security"
0x1400214af  xorps   xmm0, xmm0
0x1400214b2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400214b6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400214ba  mov     r10d, eax
0x1400214bd  call    WdmlibRtlInitUnicodeStringEx
0x1400214c2  mov     ebx, eax
0x1400214c4  test    eax, eax
0x1400214c6  js      short loc_1400214F1
0x1400214c8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400214cc  lea     rdx, [rbp+DestinationString]; ValueName
0x1400214d0  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400214d5  mov     r9d, 3; Type
0x1400214db  xor     r8d, r8d; TitleIndex
0x1400214de  mov     [rsp+60h+Data], r11; Data
0x1400214e3  call    cs:__imp_ZwSetValueKey
0x1400214ea  nop     dword ptr [rax+rax+00h]
0x1400214ef  mov     ebx, eax
0x1400214f1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400214f5  call    cs:__imp_ZwClose
0x1400214fc  nop     dword ptr [rax+rax+00h]
0x140021501  mov     eax, ebx
0x140021503  mov     rbx, [rsp+60h+arg_0]
0x140021508  mov     rdi, [rsp+60h+arg_8]
0x14002150d  add     rsp, 60h
0x140021511  pop     rbp
0x140021512  retn
```
