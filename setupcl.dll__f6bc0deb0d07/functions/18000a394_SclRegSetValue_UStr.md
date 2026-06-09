# SclRegSetValue_UStr

- ea: `0x18000a394`
- end: `0x18000a499`
- name: `SclRegSetValue_UStr`
- size: `261`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, __int64, WCHAR *, unsigned int, PVOID Data, ULONG DataSize, ULONG Type)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a334`
- `0x18000c21c`

## callees

- `0x18000a394`
- `0x18000a524`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x18000a423`
- `ntdll!NtSetValueKey` at `0x18000a423`

## string_xrefs

- `0x18000a46f`: `SclRegSetValue_UStr`

## pseudocode

```c
__int64 __fastcall SclRegSetValue_UStr(
        HANDLE KeyHandle,
        __int64 a2,
        WCHAR *a3,
        unsigned int a4,
        PVOID Data,
        ULONG DataSize,
        ULONG Type)
{
  unsigned __int64 v7; // rbx
  NTSTATUS v9; // eax
  unsigned int v10; // esi
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-18h] BYREF

  v7 = a4;
  if ( !KeyHandle || !a3 && a4 || a4 > 0xFFFE || !Data && DataSize )
    return 3221225485LL;
  ValueName = 0;
  if ( a3 )
  {
    ValueName.Buffer = a3;
    ValueName.Length = a4;
    ValueName.MaximumLength = a4;
  }
  v9 = NtSetValueKey(KeyHandle, &ValueName, 0, Type, Data, DataSize);
  v10 = v9;
  if ( v9 < 0 )
    SclLogGenericMessage(
      0,
      3,
      (int)SclEvent_Generic_Error,
      396,
      (__int64)"SclRegSetValue_UStr",
      "(%lx): Failed to set: %ws ! %.*ws",
      v9,
      L"<key>",
      v7 >> 1,
      a3,
      *(_QWORD *)&ValueName.Length,
      ValueName.Buffer);
  return v10;
}

```

## disassembly

```asm
0x18000a394  mov     [rsp+arg_0], rbx
0x18000a399  mov     [rsp+arg_8], rsi
0x18000a39e  push    rdi
0x18000a39f  sub     rsp, 60h
0x18000a3a3  mov     ebx, r9d
0x18000a3a6  mov     rdi, r8
0x18000a3a9  mov     r10, rcx
0x18000a3ac  test    rcx, rcx
0x18000a3af  jz      loc_18000A484
0x18000a3b5  test    r8, r8
0x18000a3b8  jnz     short loc_18000A3C3
0x18000a3ba  test    r9d, r9d
0x18000a3bd  jnz     loc_18000A484
0x18000a3c3  cmp     ebx, 0FFFEh
0x18000a3c9  ja      loc_18000A484
0x18000a3cf  mov     rcx, [rsp+68h+arg_20]
0x18000a3d7  mov     eax, [rsp+68h+arg_28]
0x18000a3de  test    rcx, rcx
0x18000a3e1  jnz     short loc_18000A3EB
0x18000a3e3  test    eax, eax
0x18000a3e5  jnz     loc_18000A484
0x18000a3eb  xorps   xmm0, xmm0
0x18000a3ee  movups  xmmword ptr [rsp+68h+ValueName.Length], xmm0
0x18000a3f3  test    rdi, rdi
0x18000a3f6  jz      short loc_18000A407
0x18000a3f8  mov     [rsp+68h+ValueName.Buffer], rdi
0x18000a3fd  mov     [rsp+68h+ValueName.Length], bx
0x18000a402  mov     [rsp+68h+ValueName.MaximumLength], bx
0x18000a407  mov     r9d, [rsp+68h+Type]; Type
0x18000a40f  lea     rdx, [rsp+68h+ValueName]; ValueName
0x18000a414  mov     [rsp+68h+DataSize], eax; DataSize
0x18000a418  xor     r8d, r8d; TitleIndex
0x18000a41b  mov     [rsp+68h+Data], rcx; Data
0x18000a420  mov     rcx, r10; KeyHandle
0x18000a423  call    cs:__imp_NtSetValueKey
0x18000a429  mov     esi, eax
0x18000a42b  test    eax, eax
0x18000a42d  jns     short loc_18000A480
0x18000a42f  mov     [rsp+68h+var_20], rdi
0x18000a434  lea     rax, aKey; "<key>"
0x18000a43b  mov     rcx, rbx
0x18000a43e  lea     r8, SclEvent_Generic_Error
0x18000a445  shr     rcx, 1
0x18000a448  mov     r9d, 18Ch
0x18000a44e  mov     [rsp+68h+var_28], rcx
0x18000a453  mov     edx, 3
0x18000a458  mov     [rsp+68h+var_30], rax
0x18000a45d  xor     ecx, ecx
0x18000a45f  lea     rax, aLxFailedToSetW; "(%lx): Failed to set: %ws ! %.*ws"
0x18000a466  mov     [rsp+68h+var_38], esi
0x18000a46a  mov     qword ptr [rsp+68h+DataSize], rax
0x18000a46f  lea     rax, aSclregsetvalue; "SclRegSetValue_UStr"
0x18000a476  mov     [rsp+68h+Data], rax
0x18000a47b  call    SclLogGenericMessage
0x18000a480  mov     eax, esi
0x18000a482  jmp     short loc_18000A489
0x18000a484  mov     eax, 0C000000Dh
0x18000a489  mov     rbx, [rsp+68h+arg_0]
0x18000a48e  mov     rsi, [rsp+68h+arg_8]
0x18000a493  add     rsp, 60h
0x18000a497  pop     rdi
0x18000a498  retn
```
