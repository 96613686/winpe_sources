# SclRegValueExists

- ea: `0x18000a4a0`
- end: `0x18000a51e`
- name: `SclRegValueExists`
- size: `126`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, const WCHAR *, bool *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002010`
- `0x18000540c`
- `0x1800065f8`
- `0x18000a190`
- `0x18000bc68`

## callees

- `0x18000a4a0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000a4d3`
- `ntdll!RtlInitUnicodeString` at `0x18000a4d3`
- `ntdll!NtQueryValueKey` at `0x18000a4fa`
- `ntdll!NtQueryValueKey` at `0x18000a4fa`

## pseudocode

```c
__int64 __fastcall SclRegValueExists(HANDLE KeyHandle, const WCHAR *a2, bool *a3)
{
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp+8h] BYREF

  ResultLength = 0;
  ValueName = 0;
  if ( !KeyHandle || !a2 || !a3 )
    return 3221225485LL;
  RtlInitUnicodeString(&ValueName, a2);
  *a3 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength) != -1073741772;
  return 0;
}

```

## disassembly

```asm
0x18000a4a0  mov     rax, rsp
0x18000a4a3  mov     [rax+10h], rbx
0x18000a4a7  push    rdi
0x18000a4a8  sub     rsp, 40h
0x18000a4ac  mov     dword ptr [rax+8], 0
0x18000a4b3  xorps   xmm0, xmm0
0x18000a4b6  mov     rbx, r8
0x18000a4b9  mov     rdi, rcx
0x18000a4bc  movups  xmmword ptr [rax-18h], xmm0
0x18000a4c0  test    rcx, rcx
0x18000a4c3  jz      short loc_18000A50E
0x18000a4c5  test    rdx, rdx
0x18000a4c8  jz      short loc_18000A50E
0x18000a4ca  test    rbx, rbx
0x18000a4cd  jz      short loc_18000A50E
0x18000a4cf  lea     rcx, [rax-18h]; DestinationString
0x18000a4d3  call    cs:__imp_RtlInitUnicodeString
0x18000a4d9  xor     r9d, r9d; KeyValueInformation
0x18000a4dc  lea     rax, [rsp+48h+arg_0]
0x18000a4e1  mov     [rsp+48h+ResultLength], rax; ResultLength
0x18000a4e6  lea     rdx, [rsp+48h+ValueName]; ValueName
0x18000a4eb  mov     rcx, rdi; KeyHandle
0x18000a4ee  mov     [rsp+48h+Length], 0; Length
0x18000a4f6  lea     r8d, [r9+2]; KeyValueInformationClass
0x18000a4fa  call    cs:__imp_NtQueryValueKey
0x18000a500  cmp     eax, 0C0000034h
0x18000a505  setnz   al
0x18000a508  mov     [rbx], al
0x18000a50a  xor     eax, eax
0x18000a50c  jmp     short loc_18000A513
0x18000a50e  mov     eax, 0C000000Dh
0x18000a513  mov     rbx, [rsp+48h+arg_8]
0x18000a518  add     rsp, 40h
0x18000a51c  pop     rdi
0x18000a51d  retn
```
