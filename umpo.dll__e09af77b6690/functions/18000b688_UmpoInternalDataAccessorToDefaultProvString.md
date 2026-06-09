# UmpoInternalDataAccessorToDefaultProvString

- ea: `0x18000b688`
- end: `0x18000b6a8`
- name: `UmpoInternalDataAccessorToDefaultProvString`
- size: `32`
- prototype: `const wchar_t *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000681c`

## callees

- `0x18000b688`

## pseudocode

```c
const wchar_t *__fastcall UmpoInternalDataAccessorToDefaultProvString(int a1)
{
  const wchar_t *result; // rax

  if ( a1 == 7 )
    return L"ProvAcSettingIndex";
  result = L"ProvDcSettingIndex";
  if ( a1 != 8 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000b688  mov     edx, ecx
0x18000b68a  cmp     ecx, 7
0x18000b68d  jnz     short loc_18000B697
0x18000b68f  lea     rax, aProvacsettingi; "ProvAcSettingIndex"
0x18000b696  retn
0x18000b697  xor     ecx, ecx
0x18000b699  lea     rax, aProvdcsettingi; "ProvDcSettingIndex"
0x18000b6a0  cmp     edx, 8
0x18000b6a3  cmovnz  rax, rcx
0x18000b6a7  retn
```
