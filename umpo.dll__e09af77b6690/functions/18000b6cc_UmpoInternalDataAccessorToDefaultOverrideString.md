# UmpoInternalDataAccessorToDefaultOverrideString

- ea: `0x18000b6cc`
- end: `0x18000b6ec`
- name: `UmpoInternalDataAccessorToDefaultOverrideString`
- size: `32`
- prototype: `const wchar_t *__fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000681c`
- `0x18000cb4c`

## callees

- `0x18000b6cc`

## pseudocode

```c
const wchar_t *__fastcall UmpoInternalDataAccessorToDefaultOverrideString(int a1)
{
  const wchar_t *result; // rax

  if ( a1 == 7 )
    return L"OverrideACSettingIndex";
  result = L"OverrideDCSettingIndex";
  if ( a1 != 8 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000b6cc  mov     edx, ecx
0x18000b6ce  cmp     ecx, 7
0x18000b6d1  jnz     short loc_18000B6DB
0x18000b6d3  lea     rax, aOverrideacsett; "OverrideACSettingIndex"
0x18000b6da  retn
0x18000b6db  xor     ecx, ecx
0x18000b6dd  lea     rax, aOverridedcsett; "OverrideDCSettingIndex"
0x18000b6e4  cmp     edx, 8
0x18000b6e7  cmovnz  rax, rcx
0x18000b6eb  retn
```
