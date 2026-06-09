# SIPolicyFilePathRulesPresent

- ea: `0x18001967c`
- end: `0x180019688`
- name: `SIPolicyFilePathRulesPresent`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180049860`

## pseudocode

```c
bool __fastcall SIPolicyFilePathRulesPresent(__int64 a1)
{
  return (*(_DWORD *)(a1 + 672) & 4) != 0;
}

```

## disassembly

```asm
0x18001967c  mov     eax, [rcx+2A0h]
0x180019682  shr     eax, 2
0x180019685  and     al, 1
0x180019687  retn
```
