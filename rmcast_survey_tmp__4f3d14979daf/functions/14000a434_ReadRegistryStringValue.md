# ReadRegistryStringValue

- ea: `0x14000a434`
- end: `0x14000a578`
- name: `ReadRegistryStringValue`
- size: `324`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, __int64, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14003815c`

## callees

- `0x14000a434`
- `0x14001d000`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000a467`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a53a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a467`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a53a`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a494`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a509`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a494`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a509`
- `ntoskrnl!ExAllocatePool2` at `0x14000a4d2`
- `ntoskrnl!ExAllocatePool2` at `0x14000a4d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a54d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a54d`

## pseudocode

```c
__int64 __fastcall ReadRegistryStringValue(HANDLE KeyHandle, __int64 a2, struct _UNICODE_STRING *a3)
{
  NTSTATUS v5; // eax
  unsigned int *Pool2; // rdi
  NTSTATUS v8; // ebx
  unsigned int v9; // eax
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+58h] [rbp+10h] BYREF
  int v12; // [rsp+5Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  ResultLength = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, L"SenderFileLocation");
  v5 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v5 < 0 && v5 != -2147483643 && v5 != -1073741789 || !ResultLength )
    return 3221225473LL;
  Pool2 = (unsigned int *)ExAllocatePool2(64, ResultLength, 1382901584);
  if ( Pool2 )
  {
    v8 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
    if ( v8 < 0 || (v9 = Pool2[3], v9 < 2) )
    {
      ExFreePoolWithTag(Pool2, 0);
      return (unsigned int)-1073741823;
    }
    else
    {
      memmove(Pool2, (char *)Pool2 + Pool2[2], v9);
      RtlInitUnicodeString(a3, (PCWSTR)Pool2);
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000a434  mov     rax, rsp
0x14000a437  mov     [rax+8], rbx
0x14000a43b  mov     [rax+18h], rsi
0x14000a43f  mov     [rax+10h], rdx
0x14000a443  push    rdi
0x14000a444  sub     rsp, 40h
0x14000a448  mov     rbx, rcx
0x14000a44b  mov     dword ptr [rax+10h], 0
0x14000a452  xorps   xmm0, xmm0
0x14000a455  lea     rcx, [rax-18h]; DestinationString
0x14000a459  lea     rdx, aSenderfileloca; "SenderFileLocation"
0x14000a460  mov     rsi, r8
0x14000a463  movups  xmmword ptr [rax-18h], xmm0
0x14000a467  call    cs:__imp_RtlInitUnicodeString
0x14000a46e  nop     dword ptr [rax+rax+00h]
0x14000a473  xor     r9d, r9d; KeyValueInformation
0x14000a476  lea     rax, [rsp+48h+arg_8]
0x14000a47b  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000a480  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14000a485  mov     rcx, rbx; KeyHandle
0x14000a488  mov     [rsp+48h+Length], 0; Length
0x14000a490  lea     r8d, [r9+1]; KeyValueInformationClass
0x14000a494  call    cs:__imp_ZwQueryValueKey
0x14000a49b  nop     dword ptr [rax+rax+00h]
0x14000a4a0  test    eax, eax
0x14000a4a2  jns     short loc_14000A4B2
0x14000a4a4  cmp     eax, 80000005h
0x14000a4a9  jz      short loc_14000A4B2
0x14000a4ab  cmp     eax, 0C0000023h
0x14000a4b0  jnz     short loc_14000A4BA
0x14000a4b2  mov     eax, [rsp+48h+arg_8]
0x14000a4b6  test    eax, eax
0x14000a4b8  jnz     short loc_14000A4C4
0x14000a4ba  mov     eax, 0C0000001h
0x14000a4bf  jmp     loc_14000A567
0x14000a4c4  mov     rdx, rax
0x14000a4c7  mov     ecx, 40h ; '@'
0x14000a4cc  mov     r8d, 526D6750h
0x14000a4d2  call    cs:__imp_ExAllocatePool2
0x14000a4d9  nop     dword ptr [rax+rax+00h]
0x14000a4de  mov     rdi, rax
0x14000a4e1  test    rax, rax
0x14000a4e4  jz      short loc_14000A560
0x14000a4e6  mov     ecx, [rsp+48h+arg_8]
0x14000a4ea  lea     rax, [rsp+48h+arg_8]
0x14000a4ef  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000a4f4  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14000a4f9  mov     [rsp+48h+Length], ecx; Length
0x14000a4fd  mov     r9, rdi; KeyValueInformation
0x14000a500  mov     rcx, rbx; KeyHandle
0x14000a503  mov     r8d, 1; KeyValueInformationClass
0x14000a509  call    cs:__imp_ZwQueryValueKey
0x14000a510  nop     dword ptr [rax+rax+00h]
0x14000a515  mov     ebx, eax
0x14000a517  test    eax, eax
0x14000a519  js      short loc_14000A548
0x14000a51b  mov     eax, [rdi+0Ch]
0x14000a51e  cmp     eax, 2
0x14000a521  jb      short loc_14000A548
0x14000a523  mov     edx, [rdi+8]
0x14000a526  mov     r8d, eax; Size
0x14000a529  add     rdx, rdi; Src
0x14000a52c  mov     rcx, rdi; void *
0x14000a52f  call    memmove
0x14000a534  mov     rdx, rdi; SourceString
0x14000a537  mov     rcx, rsi; DestinationString
0x14000a53a  call    cs:__imp_RtlInitUnicodeString
0x14000a541  nop     dword ptr [rax+rax+00h]
0x14000a546  jmp     short loc_14000A565
0x14000a548  xor     edx, edx; Tag
0x14000a54a  mov     rcx, rdi; P
0x14000a54d  call    cs:__imp_ExFreePoolWithTag
0x14000a554  nop     dword ptr [rax+rax+00h]
0x14000a559  mov     ebx, 0C0000001h
0x14000a55e  jmp     short loc_14000A565
0x14000a560  mov     ebx, 0C000009Ah
0x14000a565  mov     eax, ebx
0x14000a567  mov     rbx, [rsp+48h+arg_0]
0x14000a56c  mov     rsi, [rsp+48h+arg_10]
0x14000a571  add     rsp, 40h
0x14000a575  pop     rdi
0x14000a576  retn
```
