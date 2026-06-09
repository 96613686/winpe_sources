# pSetupGetPredefinedKeyPath

- ea: `0x180018290`
- end: `0x1800182db`
- name: `pSetupGetPredefinedKeyPath`
- size: `75`
- prototype: `const wchar_t *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000c944`

## callees

- `0x180018290`

## string_xrefs

- `0x18001829c`: `\REGISTRY\MACHINE`
- `0x1800182ad`: `\REGISTRY\MACHINE\SOFTWARE\Classes`
- `0x1800182be`: `\REGISTRY\USER`
- `0x1800182c8`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Hardware Profiles\Current`

## pseudocode

```c
const wchar_t *__fastcall pSetupGetPredefinedKeyPath(__int64 a1)
{
  const wchar_t *result; // rax

  switch ( a1 )
  {
    case -2147483646LL:
      return L"\\REGISTRY\\MACHINE";
    case -2147483648LL:
      return L"\\REGISTRY\\MACHINE\\SOFTWARE\\Classes";
    case -2147483645LL:
      return L"\\REGISTRY\\USER";
  }
  result = L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Hardware Profiles\\Current";
  if ( a1 != -2147483643 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180018290  mov     rdx, rcx
0x180018293  cmp     rcx, 0FFFFFFFF80000002h
0x18001829a  jnz     short loc_1800182A4
0x18001829c  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE"
0x1800182a3  retn
0x1800182a4  cmp     rdx, 0FFFFFFFF80000000h
0x1800182ab  jnz     short loc_1800182B5
0x1800182ad  lea     rax, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\SOFTWARE\\Classes"
0x1800182b4  retn
0x1800182b5  cmp     rdx, 0FFFFFFFF80000003h
0x1800182bc  jnz     short loc_1800182C6
0x1800182be  lea     rax, aRegistryUser; "\\REGISTRY\\USER"
0x1800182c5  retn
0x1800182c6  xor     ecx, ecx
0x1800182c8  lea     rax, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1800182cf  cmp     rdx, 0FFFFFFFF80000005h
0x1800182d6  cmovnz  rax, rcx
0x1800182da  retn
```
