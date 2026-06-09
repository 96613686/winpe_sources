# ReadRegistryDwordValue

- ea: `0x14000a2f8`
- end: `0x14000a42b`
- name: `ReadRegistryDwordValue`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400381ac`

## callees

- `0x14000a2f8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000a320`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a320`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a34d`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a3c2`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a34d`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a3c2`
- `ntoskrnl!ExAllocatePool2` at `0x14000a38b`
- `ntoskrnl!ExAllocatePool2` at `0x14000a38b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a400`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a400`

## pseudocode

```c
__int64 __fastcall ReadRegistryDwordValue(HANDLE KeyHandle, const WCHAR *a2, _DWORD *a3)
{
  NTSTATUS v5; // eax
  _DWORD *Pool2; // rbx
  NTSTATUS v8; // edi
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+68h] [rbp+20h] BYREF

  ResultLength = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v5 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v5 < 0 && v5 != -2147483643 && v5 != -1073741789 || !ResultLength )
    return 3221225473LL;
  Pool2 = (_DWORD *)ExAllocatePool2(64, ResultLength, 1382901584);
  if ( Pool2 )
  {
    v8 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
    if ( v8 >= 0 && Pool2[3] == 4 && Pool2[1] == 4 )
    {
      *a3 = *(_DWORD *)((char *)Pool2 + (unsigned int)Pool2[2]);
      ExFreePoolWithTag(Pool2, 0);
    }
    else
    {
      ExFreePoolWithTag(Pool2, 0);
      return (unsigned int)-1073741823;
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
0x14000a2f8  mov     rax, rsp
0x14000a2fb  mov     [rax+8], rbx
0x14000a2ff  mov     [rax+10h], rsi
0x14000a303  push    rdi
0x14000a304  sub     rsp, 40h
0x14000a308  mov     rdi, rcx
0x14000a30b  mov     dword ptr [rax+20h], 0
0x14000a312  xorps   xmm0, xmm0
0x14000a315  lea     rcx, [rax-18h]; DestinationString
0x14000a319  movups  xmmword ptr [rax-18h], xmm0
0x14000a31d  mov     rsi, r8
0x14000a320  call    cs:__imp_RtlInitUnicodeString
0x14000a327  nop     dword ptr [rax+rax+00h]
0x14000a32c  xor     r9d, r9d; KeyValueInformation
0x14000a32f  lea     rax, [rsp+48h+arg_18]
0x14000a334  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000a339  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14000a33e  mov     rcx, rdi; KeyHandle
0x14000a341  mov     [rsp+48h+Length], 0; Length
0x14000a349  lea     r8d, [r9+1]; KeyValueInformationClass
0x14000a34d  call    cs:__imp_ZwQueryValueKey
0x14000a354  nop     dword ptr [rax+rax+00h]
0x14000a359  test    eax, eax
0x14000a35b  jns     short loc_14000A36B
0x14000a35d  cmp     eax, 80000005h
0x14000a362  jz      short loc_14000A36B
0x14000a364  cmp     eax, 0C0000023h
0x14000a369  jnz     short loc_14000A373
0x14000a36b  mov     eax, [rsp+48h+arg_18]
0x14000a36f  test    eax, eax
0x14000a371  jnz     short loc_14000A37D
0x14000a373  mov     eax, 0C0000001h
0x14000a378  jmp     loc_14000A41A
0x14000a37d  mov     rdx, rax
0x14000a380  mov     ecx, 40h ; '@'
0x14000a385  mov     r8d, 526D6750h
0x14000a38b  call    cs:__imp_ExAllocatePool2
0x14000a392  nop     dword ptr [rax+rax+00h]
0x14000a397  mov     rbx, rax
0x14000a39a  test    rax, rax
0x14000a39d  jz      short loc_14000A413
0x14000a39f  mov     ecx, [rsp+48h+arg_18]
0x14000a3a3  lea     rax, [rsp+48h+arg_18]
0x14000a3a8  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000a3ad  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14000a3b2  mov     [rsp+48h+Length], ecx; Length
0x14000a3b6  mov     r9, rbx; KeyValueInformation
0x14000a3b9  mov     rcx, rdi; KeyHandle
0x14000a3bc  mov     r8d, 1; KeyValueInformationClass
0x14000a3c2  call    cs:__imp_ZwQueryValueKey
0x14000a3c9  nop     dword ptr [rax+rax+00h]
0x14000a3ce  mov     edi, eax
0x14000a3d0  test    eax, eax
0x14000a3d2  js      short loc_14000A3FB
0x14000a3d4  cmp     dword ptr [rbx+0Ch], 4
0x14000a3d8  jnz     short loc_14000A3FB
0x14000a3da  cmp     dword ptr [rbx+4], 4
0x14000a3de  jnz     short loc_14000A3FB
0x14000a3e0  mov     ecx, [rbx+8]
0x14000a3e3  mov     edx, [rcx+rbx]
0x14000a3e6  mov     rcx, rbx; P
0x14000a3e9  mov     [rsi], edx
0x14000a3eb  xor     edx, edx; Tag
0x14000a3ed  call    cs:__imp_ExFreePoolWithTag
0x14000a3f4  nop     dword ptr [rax+rax+00h]
0x14000a3f9  jmp     short loc_14000A418
0x14000a3fb  xor     edx, edx; Tag
0x14000a3fd  mov     rcx, rbx; P
0x14000a400  call    cs:__imp_ExFreePoolWithTag
0x14000a407  nop     dword ptr [rax+rax+00h]
0x14000a40c  mov     edi, 0C0000001h
0x14000a411  jmp     short loc_14000A418
0x14000a413  mov     edi, 0C000009Ah
0x14000a418  mov     eax, edi
0x14000a41a  mov     rbx, [rsp+48h+arg_0]
0x14000a41f  mov     rsi, [rsp+48h+arg_8]
0x14000a424  add     rsp, 40h
0x14000a428  pop     rdi
0x14000a429  retn
```
