# SclpStateUpdateRequestField

- ea: `0x18000540c`
- end: `0x180005484`
- name: `SclpStateUpdateRequestField`
- size: `120`
- prototype: `int __fastcall(HANDLE KeyHandle, PCWSTR SourceString, __int64, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180002640`

## callees

- `0x18000540c`
- `0x18000a334`
- `0x18000a4a0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180005465`
- `ntdll!RtlInitUnicodeString` at `0x180005465`
- `ntdll!NtDeleteValueKey` at `0x180005473`
- `ntdll!NtDeleteValueKey` at `0x180005473`

## pseudocode

```c
int __fastcall SclpStateUpdateRequestField(HANDLE KeyHandle, PCWSTR SourceString, __int64 a3, int a4, int a5)
{
  if ( a3 )
    return SclRegSetValue(KeyHandle, SourceString, SourceString, a3, a4, a5);
  else
    return SclRegValueExists(KeyHandle);
}

```

## disassembly

```asm
0x18000540c  mov     [rsp+arg_0], rbx
0x180005411  push    rdi
0x180005412  sub     rsp, 40h
0x180005416  mov     rbx, rdx
0x180005419  mov     rdi, rcx
0x18000541c  test    r8, r8
0x18000541f  jz      short loc_18000543B
0x180005421  mov     eax, [rsp+48h+arg_20]
0x180005425  mov     [rsp+48h+var_20], eax
0x180005429  mov     [rsp+48h+var_28], r9d
0x18000542e  mov     r9, r8
0x180005431  mov     r8, rdx
0x180005434  call    SclRegSetValue
0x180005439  jmp     short loc_180005479
0x18000543b  lea     r8, [rsp+48h+arg_10]
0x180005440  mov     [rsp+48h+arg_10], 0
0x180005445  call    SclRegValueExists
0x18000544a  test    eax, eax
0x18000544c  js      short loc_180005479
0x18000544e  cmp     [rsp+48h+arg_10], 0
0x180005453  jz      short loc_180005479
0x180005455  xorps   xmm0, xmm0
0x180005458  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18000545d  mov     rdx, rbx; SourceString
0x180005460  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180005465  call    cs:__imp_RtlInitUnicodeString
0x18000546b  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x180005470  mov     rcx, rdi; KeyHandle
0x180005473  call    cs:__imp_NtDeleteValueKey
0x180005479  mov     rbx, [rsp+48h+arg_0]
0x18000547e  add     rsp, 40h
0x180005482  pop     rdi
0x180005483  retn
```
