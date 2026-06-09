# TpmRegistry::CountValuesUnderKey(TpmRegistry::KEY_VALUES)

- ea: `0x1400059fc`
- end: `0x140005a7f`
- name: `?CountValuesUnderKey@TpmRegistry@@SAKW4KEY_VALUES@1@@Z`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006300`
- `0x1400211dc`

## callees

- `0x1400059fc`
- `0x140005a88`
- `0x14001a37c`

## import_xrefs

- `ntoskrnl!ZwEnumerateValueKey` at `0x140005a59`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140005a59`

## pseudocode

```c
__int64 TpmRegistry::CountValuesUnderKey()
{
  ULONG v0; // ebx
  NTSTATUS i; // eax
  ULONG ResultLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  if ( !(unsigned int)TpmRegistry::OpenKey(20, 131097, &KeyHandle) )
  {
    for ( i = ZwEnumerateValueKey(KeyHandle, 0, KeyValueFullInformation, 0, 0, &ResultLength);
          i == -1073741789;
          i = ZwEnumerateValueKey(KeyHandle, v0, KeyValueFullInformation, 0, 0, &ResultLength) )
    {
      ++v0;
    }
  }
  TpmRegistry::CloseKey(KeyHandle);
  return v0;
}

```

## disassembly

```asm
0x1400059fc  mov     rax, rsp
0x1400059ff  mov     [rax+8], ecx
0x140005a02  push    rbx
0x140005a03  sub     rsp, 30h
0x140005a07  xor     ebx, ebx
0x140005a09  lea     r8, [rax+10h]
0x140005a0d  mov     edx, 20019h
0x140005a12  mov     [rax+10h], rbx
0x140005a16  mov     [rax+8], ebx
0x140005a19  lea     ecx, [rbx+14h]
0x140005a1c  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAX@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,void * *)
0x140005a21  test    eax, eax
0x140005a23  jnz     short loc_140005A6C
0x140005a25  lea     rax, [rsp+38h+arg_0]
0x140005a2a  xor     edx, edx
0x140005a2c  mov     [rsp+38h+ResultLength], rax
0x140005a31  mov     [rsp+38h+Length], ebx
0x140005a35  jmp     short loc_140005A4D
0x140005a37  lea     rax, [rsp+38h+arg_0]
0x140005a3c  inc     ebx
0x140005a3e  mov     [rsp+38h+ResultLength], rax; ResultLength
0x140005a43  mov     edx, ebx; Index
0x140005a45  mov     [rsp+38h+Length], 0; Length
0x140005a4d  mov     rcx, [rsp+38h+KeyHandle]; KeyHandle
0x140005a52  xor     r9d, r9d; KeyValueInformation
0x140005a55  lea     r8d, [r9+1]; KeyValueInformationClass
0x140005a59  call    cs:__imp_ZwEnumerateValueKey
0x140005a60  nop     dword ptr [rax+rax+00h]
0x140005a65  cmp     eax, 0C0000023h
0x140005a6a  jz      short loc_140005A37
0x140005a6c  mov     rcx, [rsp+38h+KeyHandle]; void *
0x140005a71  call    ?CloseKey@TpmRegistry@@CAXPEAX@Z; TpmRegistry::CloseKey(void *)
0x140005a76  mov     eax, ebx
0x140005a78  add     rsp, 30h
0x140005a7c  pop     rbx
0x140005a7d  retn
```
