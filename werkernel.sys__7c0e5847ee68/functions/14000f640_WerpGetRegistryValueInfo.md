# WerpGetRegistryValueInfo

- ea: `0x14000f640`
- end: `0x14000f6cf`
- name: `WerpGetRegistryValueInfo`
- size: `143`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f4b8`
- `0x14000f5b4`
- `0x14000f8bc`
- `0x1400122c0`

## callees

- `0x14000d174`
- `0x14000f640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6ab`
- `ntoskrnl!ZwQueryValueKey` at `0x14000f694`
- `ntoskrnl!ZwQueryValueKey` at `0x14000f694`

## pseudocode

```c
__int64 __fastcall WerpGetRegistryValueInfo(HANDLE KeyHandle, PUNICODE_STRING ValueName, _QWORD *a3)
{
  void *Mem; // rdi
  NTSTATUS v7; // ebx
  ULONG ResultLength; // [rsp+70h] [rbp+18h] BYREF

  ResultLength = 0;
  *a3 = 0;
  Mem = (void *)WerpAllocateMem(518, ValueName);
  if ( !Mem )
  {
    v7 = -1073741670;
    goto LABEL_5;
  }
  v7 = ZwQueryValueKey(KeyHandle, ValueName, KeyValuePartialInformation, Mem, 0x206u, &ResultLength);
  if ( v7 < 0 )
  {
    ExFreePoolWithTag(Mem, 0);
LABEL_5:
    Mem = 0;
  }
  *a3 = Mem;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000f640  push    rbx
0x14000f642  push    rbp
0x14000f643  push    rsi
0x14000f644  push    rdi
0x14000f645  sub     rsp, 38h
0x14000f649  mov     rbp, rcx
0x14000f64c  mov     [rsp+58h+arg_10], 0
0x14000f654  mov     ecx, 206h
0x14000f659  mov     qword ptr [r8], 0
0x14000f660  mov     rsi, r8
0x14000f663  mov     rbx, rdx
0x14000f666  call    WerpAllocateMem
0x14000f66b  mov     rdi, rax
0x14000f66e  test    rax, rax
0x14000f671  jz      short loc_14000F6B9
0x14000f673  lea     rax, [rsp+58h+arg_10]
0x14000f678  mov     r9, rdi; KeyValueInformation
0x14000f67b  mov     [rsp+58h+ResultLength], rax; ResultLength
0x14000f680  mov     r8d, 2; KeyValueInformationClass
0x14000f686  mov     rdx, rbx; ValueName
0x14000f689  mov     [rsp+58h+Length], 206h; Length
0x14000f691  mov     rcx, rbp; KeyHandle
0x14000f694  call    cs:__imp_ZwQueryValueKey
0x14000f69b  nop     dword ptr [rax+rax+00h]
0x14000f6a0  mov     ebx, eax
0x14000f6a2  test    eax, eax
0x14000f6a4  jns     short loc_14000F6C0
0x14000f6a6  xor     edx, edx; Tag
0x14000f6a8  mov     rcx, rdi; P
0x14000f6ab  call    cs:__imp_ExFreePoolWithTag
0x14000f6b2  nop     dword ptr [rax+rax+00h]
0x14000f6b7  jmp     short loc_14000F6BE
0x14000f6b9  mov     ebx, 0C000009Ah
0x14000f6be  xor     edi, edi
0x14000f6c0  mov     [rsi], rdi
0x14000f6c3  mov     eax, ebx
0x14000f6c5  add     rsp, 38h
0x14000f6c9  pop     rdi
0x14000f6ca  pop     rsi
0x14000f6cb  pop     rbp
0x14000f6cc  pop     rbx
0x14000f6cd  retn
```
