# PpRegStateUpdateStackCreationSettings

- ea: `0x140021f60`
- end: `0x1400220d4`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140020e70`

## callees

- `0x1400120a8`
- `0x140021a78`
- `0x140021f60`
- `0x140022288`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140022044`
- `ntoskrnl!ZwClose` at `0x1400220b5`
- `ntoskrnl!ZwClose` at `0x140022044`
- `ntoskrnl!ZwClose` at `0x1400220b5`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140022058`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140022058`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140021fce`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140021fce`
- `ntoskrnl!ZwSetValueKey` at `0x1400220a3`
- `ntoskrnl!ZwSetValueKey` at `0x1400220a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021fee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021fee`

## string_xrefs

- `0x140022068`: `Security`

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
0x140021f60  mov     [rsp-8+arg_0], rbx
0x140021f65  mov     [rsp-8+arg_8], rdi
0x140021f6a  push    rbp
0x140021f6b  mov     rbp, rsp
0x140021f6e  sub     rsp, 60h
0x140021f72  lea     rax, [rbp+Handle]
0x140021f76  mov     [rbp+P], 0
0x140021f7e  xor     r9d, r9d
0x140021f81  mov     [rsp+60h+Data], rax
0x140021f86  xor     r8d, r8d
0x140021f89  mov     [rbp+KeyHandle], 0
0x140021f91  mov     rdi, rdx
0x140021f94  mov     [rbp+Handle], 0
0x140021f9c  call    PiRegStateOpenClassKey
0x140021fa1  test    eax, eax
0x140021fa3  js      loc_1400220C3
0x140021fa9  cmp     cs:PiRegStateDiscriptor, 0
0x140021fb0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140021fb7  jnz     short loc_140022006
0x140021fb9  xor     edx, edx
0x140021fbb  lea     rax, [rbp+P]
0x140021fbf  mov     r9b, 1
0x140021fc2  mov     [rsp+60h+Data], rax
0x140021fc7  mov     rcx, rbx
0x140021fca  lea     r8d, [rdx+1]
0x140021fce  call    cs:__imp_SeCaptureSecurityDescriptor
0x140021fd5  nop     dword ptr [rax+rax+00h]
0x140021fda  test    eax, eax
0x140021fdc  js      short loc_140021FFC
0x140021fde  mov     rcx, [rbp+P]; P
0x140021fe2  xor     edx, edx; Tag
0x140021fe4  mov     cs:PiRegStateDiscriptor, 1
0x140021fee  call    cs:__imp_ExFreePoolWithTag
0x140021ff5  nop     dword ptr [rax+rax+00h]
0x140021ffa  jmp     short loc_140022006
0x140021ffc  mov     cs:PiRegStateDiscriptor, 2
0x140022006  mov     rcx, [rbp+Handle]
0x14002200a  lea     rdx, aProperties; "Properties"
0x140022011  xor     eax, eax
0x140022013  cmp     cs:PiRegStateDiscriptor, 1
0x14002201a  cmovnz  rbx, rax
0x14002201e  lea     rax, [rbp+KeyHandle]
0x140022022  mov     [rsp+60h+var_30], rax
0x140022027  mov     qword ptr [rsp+60h+DataSize], 0
0x140022030  mov     [rsp+60h+Data], rbx
0x140022035  mov     [rbp+P], rbx
0x140022039  call    CmRegUtilCreateWstrKey
0x14002203e  mov     rcx, [rbp+Handle]; Handle
0x140022042  mov     ebx, eax
0x140022044  call    cs:__imp_ZwClose
0x14002204b  nop     dword ptr [rax+rax+00h]
0x140022050  test    ebx, ebx
0x140022052  js      short loc_1400220C1
0x140022054  mov     rcx, [rdi+8]; SecurityDescriptor
0x140022058  call    cs:__imp_RtlLengthSecurityDescriptor
0x14002205f  nop     dword ptr [rax+rax+00h]
0x140022064  mov     r11, [rdi+8]
0x140022068  lea     rdx, aSecurity; "Security"
0x14002206f  xorps   xmm0, xmm0
0x140022072  lea     rcx, [rbp+DestinationString]; DestinationString
0x140022076  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002207a  mov     r10d, eax
0x14002207d  call    WdmlibRtlInitUnicodeStringEx
0x140022082  mov     ebx, eax
0x140022084  test    eax, eax
0x140022086  js      short loc_1400220B1
0x140022088  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002208c  lea     rdx, [rbp+DestinationString]; ValueName
0x140022090  mov     [rsp+60h+DataSize], r10d; DataSize
0x140022095  mov     r9d, 3; Type
0x14002209b  xor     r8d, r8d; TitleIndex
0x14002209e  mov     [rsp+60h+Data], r11; Data
0x1400220a3  call    cs:__imp_ZwSetValueKey
0x1400220aa  nop     dword ptr [rax+rax+00h]
0x1400220af  mov     ebx, eax
0x1400220b1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400220b5  call    cs:__imp_ZwClose
0x1400220bc  nop     dword ptr [rax+rax+00h]
0x1400220c1  mov     eax, ebx
0x1400220c3  mov     rbx, [rsp+60h+arg_0]
0x1400220c8  mov     rdi, [rsp+60h+arg_8]
0x1400220cd  add     rsp, 60h
0x1400220d1  pop     rbp
0x1400220d2  retn
```
